CMPE 202 Individual Project
Sec 48 & 49

Name : Sharad Nataraj
SJSU ID : 015940002

Github Repository - https://github.com/sharadnatarajSJSU/202Individual-Project

Instructions to Run the application :

Open the command line where the project directory is located and execute below steps
mvn compile
mvn clean install
Execute the below maven command to execute with arguments (Path to where the input file is located and path to where output file should be located) passed via command line
mvn exec:java -Dexec.mainClass=test.RunClient -Dexec.args="<arg1> <arg2 > <arg3> <arg4>"
arg1 – path to the input data (Sample.csv)
arg2 – path to flight details to populate DB (flights.csv)
arg3 – path to Output.csv
arg4 – path to Output.txt
Output.csv contains the successful bookings
Output.txt contains booking errors with the details of the requested booking and appropriate message.

Problem Statement :

Design an application using JAVA that accepts a booking request file and stores it using a static database ( Hashmaps or other structures). The application should read a file with the booking requests, store them, create the booking and output successful bookings as CSV. It should also output unsuccessful booking in another file reasoning why the booking was not successful.

Requirements :

Use at least 3 design patterns.
It should be a maven project with dependencies in pom.xml
Main method should be as runclient
JUnit testing should be implemented.

Functional Requirements

Validate if the requested flight exists.
If the flight exists, validate the number of seats requested for the category.
After this validation, if the booking is valid, calculate the total price (NoOfSeats * price)
Take the card number of the user and validate it using the given rules:
Visa card: has length either 13 or 16. It begins with a 4
Mastercard: has length 16. Begins with 5 and the 2nd digit begins from 1 to 5 inclusive
Discover: length 16, and the first 4 digits begins from 6011
Amex: has length 15 and starts with 3. 2nd digit must be 4 or 7
Any card greater than 19 or not satisfying above conditions is considered invalid.
If the card is valid then modify the available seats for that category and flight number
Then output the CSV list with booking name, flight number, Category, number of seats booked, total price.
In case, it is an incorrect request at any of the steps, generate and output TXT file with the message "Please enter correct booking details for <booking_name>:<reason>" and include the information with incorrect information. For example, Please enter correct booking details for John: invalid flight number.

Design Patterns Used :
Chain of responsibility pattern
Chain of responsibility Is a behavioral pattern that lets you pass requests along a chain of handlers .
In this application, we use this pattern to pass the responsibility of the tasks. For eg : booking function will pass the responsibility of card validation to the validation class. Then based on the validation output the responsibility is passed to the output class or the booking class again.
Singleton Pattern
Singleton is a creational design pattern that lets you ensure that a class has only one instance, while providing a global access point to this instance.
Used for the functionality of reading input files from the command line and confirming booking.
Factory
Used to create output files without exposing the internal details of the structure of the output needed.




Output and Testing








 



Java Class diagram


