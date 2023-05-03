Download Link: https://assignmentchef.com/product/solved-cs201-homework-4-bus-database-search
<br>



<h1>Structure of Database Files</h1>

As mentioned before, the database is stored in two different text files. One is only for route records, the other one is for route-time pair records. These two files will be input files to your program. (i.e. your program will read some data from both files)

Name of both input files will be entered by the user of your program. At the beginning of your program, user will be asked to enter an input file name for the route records. If the user enters a name for a file that does not exist, your program should display an appropriate message and ask for the name of a new input file name until the file is successfully opened. After the first input file is opened successfully, your program will ask for another input file name for time records file. The same file opening control check will be performed for this file too. If user enters a name for a file that does not exist, your program should display an appropriate message and ask for the name of a new input file name until the file is successfully opened.

<h1>Route Database File</h1>

The routes input file contains several information fields for each route. For a single route, there are three columns of information on the same line. Each line corresponds to the record of a route. The record structure for each route is described as follows:

Record line starts with a <strong><em>routeID</em></strong>. <em>routeID</em>’s are integer values and they are unique in each line. You will need to store this information to match the routes to times in the next file. It is followed by two strings: <strong><em>routeStart </em></strong>and <strong><em>routeEnd</em></strong>.

The abovementioned record structure, which contains 3 different data items in one line, is just for one route. The input file contains information about several routes. Therefore, there are several such records in the input file. You may assume there is a record in each line of input file, no line is empty. Also please note that the database file is not sorted (ordered).

<h1>Times Database File</h1>

The times database file contains time-route pairs written by that time. For a single time record, there are 2 pieces of information on the same line. The record structure for each route-time pair is described as follows:

<ul>

 <li><strong><em>routeID </em></strong>is a single integer value.</li>

 <li><strong><em>departureTime </em></strong>is a string value. It is in the format 00:00. (ex: 03:02, 16:45 etc.)</li>

</ul>

We assume that <strong>no </strong>time-route pair appears <strong>more than once </strong>in the Times database file. For example, if there is a pair such as <strong><em>Route11 Time1</em></strong><em>, </em>then there will <strong>not </strong>be another pair such as <strong><em>Route11 Time1</em></strong>.

There is no specific order of records in both input files. That means you cannot assume that the records of the input files are ordered according to <strong>r<em>outeID</em></strong>, <strong><em>departureTime </em></strong>or any other data field.

The structure of the input files and the associated rules and assumptions explained above are fixed such that you cannot change them or make any other assumptions. Y<strong>ou can assume that the input files will not be empty. </strong>You may examine the sample input files provided in the <a href="https://drive.google.com/open?id=1v3VdpixMbpLi438xcfL_rmHper4v5ZPP">homework</a> <a href="https://drive.google.com/open?id=1v3VdpixMbpLi438xcfL_rmHper4v5ZPP">google </a><a href="https://drive.google.com/open?id=1v3VdpixMbpLi438xcfL_rmHper4v5ZPP">folder</a> for this homework. Please note that we have multiple input files for multiple scenarios, therefore your code should also work with all these possible outcomes.

<u>Important! There might be any number of white spaces (i.e. blanks) and/or tabs between and after each data item in both files. You should handle it.</u>

<h1>Database Search/Filter</h1>

Database search will basically be searching the routes database file for all routes after a given departure time. First you need to specify a Departure Location for your search. After entering departure location, (as long as it is not EXIT) you will be asked to enter a Departure Time to search for. You should only display the routes that are equal to or after this time. For example, if there are three bus routes from canakkale at times: 10:00, 12:00, 14:00 and the departure time is given as 12:00; then you should only print out the routes at 12:00 and 14:00 to the console.

Your results will contain <strong><u>all </u></strong>routes possible from the given departure location after (or equal to) the given departure time.

To do so, you must first search routes.txt and check each <em>routeStart </em>value to see if it is equal to the departure location given as input. If a match is found, you should store <em>routeID </em>and <em>routeEnd</em>. Then you should check times database file to check if there is a corresponding bus route with that stored <em>routeID</em>. If a record is found, then you should check the time on that record with the user input departure time. If the route time is later than or equal to the departure time, then you should display that search result on a separate line to the console as specified below. The format of this line is as follows:

<ul>

 <li><strong><em>departureLocation </em></strong>is the user’s input,</li>

 <li><strong><em>routeEnd </em></strong>is extracted from the routes database file, <strong><em>busTime </em></strong>is extracted from the times database file.</li>

</ul>

There is <strong><u>only one </u></strong>blank (white space) between each of these words. Please see the sample runs.

There will be any number of such lines, one for each route found, displayed on the console.

After successfully displaying one search result on console, your program will ask parameters for another search until “EXIT” word is entered as a termination command for departure location.

After a termination command, your program will close. You should check the “Sample Runs” below.

<h1></h1>

<h2>Sample Run</h2>

Below, we provide a sample run of the program that you will develop. The italic and bold phrases are inputs taken from the user. You should follow the input order in these examples and the prompts your program will display must be <strong>exactly the same </strong>as in the following examples.

Please enter a filename for route database: <strong><em>r </em></strong>cannot open routes database file

Please enter a filename for route database: <strong><em>routes </em></strong>cannot open routes database file

Please enter a filename for route database: <strong><em>routes.txt </em></strong>Please enter a filename for time database: <strong><em>time.txt </em></strong>cannot open times database file

Please enter a filename for time database: <strong><em>time </em></strong>cannot open times database file

Please enter a filename for time database: <strong><em>times.txt</em></strong>

Please enter departure location: <strong><em>Istanbul </em></strong>Please enter start time of travel: <strong><em>03:45 </em></strong>The search results are:

Istanbul Ankara 12:00

Istanbul Izmir 15:00

Istanbul Trabzon 11:00

Istanbul Trabzon 07:15

Please enter departure location: <strong><em>Adana</em></strong>

Please enter start time of travel: <strong><em>aa:15</em></strong>

Time is not in correct format

Please enter start time of travel: <strong><em>:!A.E</em></strong>

Time is not in correct format

Please enter start time of travel: <strong><em>34:60</em></strong>

Time is not in correct format

Please enter start time of travel: <strong><em>20:80</em></strong>

Time is not in correct format

Please enter start time of travel: <strong><em>29:01</em></strong>

Time is not in correct format

Please enter start time of travel: <strong><em>1:15</em></strong>

Time is not in correct format

Please enter start time of travel: <strong><em>01:15 </em></strong>The search results are:

Adana Ankara 19:00

Adana Ankara 23:45

Adana Ankara 22:00

Please enter departure location: <strong><em>Izmir </em></strong>Please enter start time of travel: <strong><em>14:23 </em></strong>The search results are:

Izmir Istanbul 21:00

Izmir Istanbul 18:00

Izmir Istanbul 16:30

Please enter departure location: <strong><em>Trabzon</em></strong>

Please enter start time of travel: <strong><em>23:00 </em></strong>The search results are:

Please enter departure location: <strong><em>Ankara </em></strong>Please enter start time of travel: <strong><em>13:22 </em></strong>The search results are:

Ankara Adana 14:45

Ankara Adana 18:30

Ankara Istanbul 17:00

Ankara Istanbul 23:00

Ankara Gaziantep 22:45

Ankara Gaziantep 20:30

Please enter departure location: <strong><em>gaziantep </em></strong>Please enter start time of travel: <strong><em>07:30 </em></strong>The search results are:

Please enter departure location: <strong><em>Antalya</em></strong>

Please enter start time of travel: <strong><em>12:00 </em></strong>The search results are:

Please enter departure location: <strong><em>Eskisehir</em></strong>

Please enter start time of travel: <strong><em>10:104</em></strong>

Time is not in correct format

Please enter start time of travel: <strong><em>10:10 </em></strong>The search results are:

Eskisehir Ankara 17:30

Eskisehir Ankara 14:00

Please enter departure location: Izmir

Please enter start time of travel: 19:09

The search results are:

Izmir Istanbul 21:00

Please enter departure location: Gaziantep

Please enter start time of travel: 23:59 The search results are:

Please enter departure location: <strong><em>EXIT</em></strong>


