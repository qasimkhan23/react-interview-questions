# React & Javascript Interview Questions & Answers

> Click :star:if you like the project. Pull Request are highly appreciated.

### Table of Contents

| No. | Questions                                                                                            |
| --- | ---------------------------------------------------------------------------------------------------- |
|     | **Core React & Javascript**                                                                          |
| 1   | [What is Lexical Scope in javascript?](#what-is-lexical-scope-in-javascript)                         |
| 2   | [Javascript is single threaded or multi threaded?](#Javascript-is-single-threaded-or-multi-threaded) |
| 3   | [How to handle async operations in javascript?](#How-to-handle-async-operations-in-javascript)       |
| 4   | [What is a closure?](#What-is-a-closure)                                                             |
| 5   | [What is function scope and block scope?](#What-is-function-scope-and-block-scope)                   |  |
| 5   | [What will be the answer?](#What-will-be-the-answer)                                                 |

## Core React & Javascript

1.  ### What is Lexical Scope in javascript?

    A Lexical Scope in javascript means that a variable defined outside a function can be accessible inside another function defined after the variable declaration.But the opposite is not true, the variables defined inside a function will not be accessible outside that function.

2.  ### Javascript is single threaded or multi threaded?

    Javascript is a single threaded language. This means it has one call stack and one memory heap. As expected, it executes code in order and must finish executing a piece code before moving onto the next.

3.  ### How to handle async operations in javascript?

    We can handle async operations in javascript using callbacks, promises and async await.

4.  ### What is a closure?

    A closure is a function having access to the parent scope, even after the parent function has closed.

    Example:

    ```
    var add = (function () {

    var counter = 0;
    return function () {counter += 1; return counter}
    })();

    add();
    add();
    add();

    // the counter is now 3
    ```

    Explanation:

    The variable add is assigned the return value of a self-invoking function.

    The self-invoking function only runs once. It sets the counter to zero (0), and returns a function expression.

    This way add becomes a function. The "wonderful" part is that it can access the counter in the parent scope.

    This is called a JavaScript closure. It makes it possible for a function to have "private" variables.

    The counter is protected by the scope of the anonymous function, and can only be changed using the add function.

5.  ### What is function scope and block scope?

    var is a function scope means we can not access the variable outside the function.
    let and const are block scope means we can not access the varible out side the block and a block means curly braces.
    Problems with var:

    ```
    function(){
        var x = 10;
        if(x == 10){
            x = 2
        }
        return x;
        // here the x will be returned with the value 2 because the var is a fucntion scope
    }
    ```

    Solution:

    ```
    fucntion(){
        let x = 10;
        if(x == 10){
            x = 2
        }
        return x;
        // here the x will be returned with the value 10 because the let is fucntion scope and we cannot use it outside the block
    }
    ```

6.  ### What will be the answer?

    Q1:

    ```
    console.log('xyz')
    new Promise(function(resolve){return resolve('abc')})
    console.log('print this line')
    ```

    Answer:

    ```
    xyz
    print this line
    abc
    ```

    Explanation:

    This is because the javascript is sngle threaded and it will perform the synchronous operations first and give the async operation to the webapi by pushing the code into the event loop, when the synchronous code will be finish than the async code will be executed.

    Q2:

    ```
    for(var i=0;i<5;i++){
    setTimeout(function(){console.log(i)},1000);
    }
    ```

    Answer:

    ```
    5
    ```

    Explanation:

    This is because the var will reassign the value instead on redeclaring, if we use let than it will print throughout the loop after 1 second delay
