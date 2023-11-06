# WEB-103 JavaScript Syntax Guide

This syntax guide is meant to be used as an exploratory introduction to some important JavaScript fundamentals. The following will attempt to explain, document and give examples of the following components and concepts:

- Variables
- Data Types
- Comparison Statements
- Boolean Statements
- Arrays
- Objects
- Functions
- Functions & Parameters
- Loops
- Comments


## Variables

The simplest way to describe a variable is to say that it is a container in which data (or information) can be stored as a "value". 
In order to assign a value to a variable, the variable must first be declared. We use the keyword *let* to do so.
In the example below, we are using *let* to declare the letter 'x' as our variable name, and subsequently storing within 'x' the value of 5.

`let x = 5`

Variables must always be declared, and only once. The declarative keyword *const* may also be used instead of *let*. The main difference with the *const* keyword is that the variable's value won't be able to be changed once declared as such.  


#### Notes on Variable Names

Although we can name our variables whatever we want, it's important to use names that are clear, descriptive, easy to read, and make sense within the context of our code and what the variables are being used for. Furthermore, if we need to use more than one word when naming a variable, we must use a grammar syntax rule known as camelCase, in which any words being used *after* the first one must be capitalized. See the example below, where we are using the words 'user', 'profile', and 'data' as our variable name:

`let userProfileData = x`

## Data Types

There are multiple different types of data that can be stored in variables. We will touch on some more of these at greater lengths elsewhere in this guide, but here's an introductory list to some of those relevant data types. The first category consists of what are called *primitive* data types. Here are some we might commonly use: 

1. *strings* - defined as text/characters
 `let name = "John"`

2. *integers* - defined as numbers
 `let a = 1`

3. *boolean* - defined as one of either true or false
    ```
    let x = 1;
    let y = 1;
    let z = 2;
    (x == y ) // true
    (x == z ) // false
    ```

4. *null* - defined as an unknown or empty value
`let x = null`

5. *undefined* - categorized as a value that is effectively unassigned; or, undefined

Another category of variables is known as the *Object Datatype*. These types are slightly more complex in nature in that these datatypes contain several values.

1. *arrays* - defined as a variable containing an index/grouping of more than one value

    ```
    let array = ["John", "Joe", "Jack"]
    ```
2. *objects* - defined as a data collection of various properties and their assigned values
    ```
    let user = {
        age: 25,
        name: "John",
        sex: "male",
    }
    ```


## Comparison Statements 

Comparison statements are a commonly used mathematical operation. We can use them in JS to compare values against each other and effect functions and methods in accordance with the results of the comparison.
Examples of how to write comparisons are as follows:

- greater than/less than: a > b, a < b
- greater than/less than or equal to: a >= b, a <= b
- equal to: a == b  (important! we must use double == to specify equality)
- not equal to: a != b

An example would be a prompt for a user to input their age when signing in to a website in order to confirm or verify legality:

```
let y = prompt("Enter age here")
if (y < 21) { 
alert("You must be 21 years of age to access this site")
}
```

or, alternatively 

```
if (y >= 21) {
    alert("Welcome to the online Casino!")
}
```

## Boolean Statements 

Boolean statements are an extension of comparison statements and are most simply explained as possessing one of two possible results; true, or false. Comparisons will always return one of these two values.  

```
( 2 > 1 )  // result of comparison is *true*
( 2 == 1 ) // result of comparison is *false* 
( 2 != 1 ) // result of comparison is *true*
```

## Arrays

An array is a unique variable, in the sense that it can contain several values. In an earlier example from the Variables section, we declared a variable 'x' and stored a single value in it. An array allows us to store multiple values, as shown in the example below:

`let array = ["John", "Joe", "Jack"]`

We use square brackets for the contents of our array, and we now have 3 values - the names John, Joe and Jack - stored within it. These string data values must be in quotation marks and separated by commas. Each individual value is assigned a sequential index number, starting with 0. So, if we wanted to target a specific value in a method or function, we could do so by using the appropriate index number. Here's a follow up example on how we could target all three of these values separately:

`array[0] = "John"`
`array[1] = "Joe"`
`array[2] = "Jack"`

## Objects 

An object is one type of variable mentioned at the top of this guide. It is similar to an array, but they are more complex in nature than other variables in that they are able to store a multitude of different types of values, specifically designated by what we call *properties*. For the sake of this example, we will demonstrate with a user profile:

```
let user = {
    name: "John",
    sex: "male",
    age: 25,
    job: "carpenter",
}
```

In this example, 'user' is the object. The curly brackets are used to contain the object's properties and their individual values. In this case, everything in the left column is a property (name, sex, age, job), and the right column is where we assign values to those properties, separated by a colon. In order to target a specific property from inside the object, we can do so in one of two ways. Let's use the "name" property in the example below:

`user.name`

or

`user["name"]`

In simplest terms, we use the object name first, followed by the property we wish to isolate.

It is also possible to 'nest' an object within an object. 

```
let user = {
    name: "John",
    sex: "male",
    age: 25,
    job: "carpenter",
    contact: {
        email: "johncarpenter@mail.com";
        phone: "123-456-1234"
    }
}
```
As we can see, there is a child object containing a specific set of data about a user's contact information. We can access this data the same way we would a regular object, as seen below to access the email property contained in the child object:

`user.contact.email` 

## Functions 

A section of code that is meant to perform or execute a particular action is known as a *function*. A simple analogy would be to think of a pressing a button that turns on a light; for example's sake, pressing the button is how a function would be executed.
Writing out a function is done by using the following syntax:

```
function testFunction() {
    // inside these curly brackets is where the executable code is written
}
```

Let's break down the syntax. 
- The first keyword *function* is where and how we designate that the subsequent block of code will in fact be a function. 
- The next component is simply the function's name, which in this case is *testFunction*. This is what we would use to recall the function in other areas of our code.  
- After the name comes a set of round brackets, in which we can place parameters - we'll look at what those are in the next section. These round brackets must always be tethered to the function name, regardless of wether or not we are passing parameters or if they're staying empty.
- Lastly, we use curly brackets as a container for the code we design to be executed. 

So the function is the "button", and the code inside of it is what will turn the light on. Within the curly bracket code we can declare variables, use variables, execute methods, target specific elements, and more. Once our function is written, it can be recalled at any point in the application; therefore eliminating the need to rewrite code every time we want a specific task to be performed. Here's a basic example of a function designed to pop up an alert message:

```
function welcomeMessage() {
    alert("Welcome to our website!")
}
```

In this example, any time the 'welcomeMessage' function is called, it will execute the alert code contained inside of its curly brackets, which in this case will pop up the message contained in quotation marks.


It is otherwise important to keep in mind the difference between local and global variables in relation to our functions. A local variable is one that is declared within the curly brackets and only accessible within the function itself. A function may still use a global variable - which is to say a variable that has been declared outside of the function. However, this doesn't work the other way around. If we declare a local variable for use inside a function, it is then restricted to that function and cannot be calledfor use outside of the curly brackets it is contained in. 

Here are a few basic examples:
```
let x = "Hello"  // example of a global variable, declared outside of the function

function message() {
    alert(x)     // we can pull global variable x into the function to use it here
}
```
```
function message() {
    let x = "Hello";    // example of a local variable declared within the function
    alert(x)            // we can only re-use x inside the function
}
```

## Functions & Parameters 

In the description of Functions above, the third bullet point refers to round brackets, which are a container for what are known as parameters. Parameters are used to pass data into the function. Here's a simple example using two parameters (a,b) in a function designed to execute an addition.

```
function addNumbers(a,b) {
    return (a + b);
}

addNumbers(3, 5) 
```

We are calling the addNumbers function and passing through values of 3 and 5 via our parameters 'a' and 'b', and those values are fed into the function itself, which is designed to add 'a' and 'b'. This will therefore result in a returned value of 8. 

## Loops 
Loops are an effective way of repeating or cycling through the same block of code several times. We'll look at two different kinds of loops we can execute here. 

#### The For Loop 
For Loops are used to loop through a block of code a specified number of times. It uses a set of 3 parts or 'expressions' located in round brackets in order to set conditions for the code to follow:

```
for (expression 1; expression 2; expression 3) {
  // inside these curly brackets is where the executable code is written
}
```
These expressions are all separated by semi-colons, as seen above. The first expression is used to set a variable before the loop begins and is executed once before the subsequent code block. The second will define the conditions under which the loop is designed to run. The third expression is executed in sequence after the previous code block has been run. Let's look at it in more detail:

```
for (let i = 0; i < 5; i++) {
  console.log(i);
}
```
So, in plain english: the variable 'i' begins the loop and is set to zero. The condition we've set is for the loop to run as long as the variable's value is less than 5. Lastly, our variable will increase by one during each loop, until the conditions have been met, at which point the loop will stop. 

#### The While Loop
This loop is used to execute code as long as a specified condition is met - hence the term "while". The code we write will execute while this condition is valid, or "true", and will only stop when it becomes "false". Here's an example of a block of code that
will countdown from 10 to 0:

```
let i = 10
while (i > 0)
{
    console.log(i);  // this line of code is used to show/log the countdown loop in the test console
    i -= 1;
}
```

In sequence, what we've done here is initialized the 'i' variable (known as the iterator) and given it a value of 10. 
Next, the condition for the loop is set in round brackets, and this can be read as "while the value of i is greater than zero". Our loop will run as long is this is true.
Finally, we instruct the code to subtract 1 from the 'i' variable, which it will continue to do on a loop until the aforementioned condition is no longer met. 


## Comments 

There are a few ways to use comments in our JS code.

#### Single Line Comment
To leave a comment on a single line of code, we simply use double forward slashes, seen as // below: 

`// 'sample comment text'`

Anything following the // on that single line of code - as represented by the 'sample comment text' - will then become a comment, including functional code. 


#### Multi-line Comment
Alternatively, if we need to leave a comment spanning multiple lines of code, we can use a combination of a forward slash and a star seen as /* and then a star and a forward slash seen as */ below:

```
 /*  'sample comment text'  
     'sample comment text'
     'sample comment text'  */
```
Anything contained within the two slash + star combinations will become a comment, as represented in the example above by the three lines of 'sample comment text'.

-------

Leaving comments in our code can be useful for a few different reasons.
We are able to use comments to attach instructions or additional details pertaining to specific portions of our code, as demonstrated in the following examples:

`let x = 12  //  x variable declared and assigned the value of '12'`

```
function addReminder() {   // this function is for adding new reminders to the list
    let y = document.getElementById("myInput").value; 
    reminders.push(y)    // y variable pushing its contents into reminders array
    document.getElementById('reminder').innerHTML = ""; 
}
```


Since anything contained within a single or multi line comment isn't recognized in JS as functional code, we can also use the comment feature to effectively disable specific lines or sections of code in order to test, troubleshoot or debug functionality issues within our applications. This is a much more practical alternative to deleting and then re-writing lines of code when trying to solve problems or when testing different features. 