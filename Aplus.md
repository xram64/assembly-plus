# Documentation for the A+ language

## 1. Data Types
| Name	    | Size		| Purpose		        	 | Range 	           |
|:---------:|:---------:| -------------------------- | ------------------- |
| bool    	| 1 byte    | Boolean			         | `true` or `false`   |
| uint8    	| 1 byte	| 8-bit unsigned integer     | 0 - 255        	   |
| int       | n bytes   | Integer                    |                     |
| string    | n bytes   | String of ASCII characters | N/A                 |


## 2. Syntax

### Basics
All statements occupy one line and must be ended with a semicolon. Exceptions to this are `if` and `while` statements which must be followed by a block enclosed by { and } braces on individual lines.

Comments must be wrapped in /\* and \*/.  
Example: `/* This is a comment. */`

----
### Keywords
| Keyword   | Purpose		        			    | Example 	              |
|:---------:| ------------------------------------- | ----------------------- |
| var     	| Declares a mutable variable.          | `var uint8 foo;`        |
| set     	| Assigns a value to a variable.        | `set foo = 5;`          |
| con	    | Creates a constant.                  	| `con uint8 BAR = 42;`   |
| print	   	| Prints a line to stdout.           	| `print "Hello, world!";`|

### `var`
Use `var uint8 foo;` to declare a uint8 variable named foo. The `var` keyword must always be followed by the variable type. Variables must be declared before they are assigned. Variable names are case-sensitive and must start with a letter.

### `set`
Use `set foo = 5` to set or change the value of foo to 5. `set` may be used to set a variable to a literal value or to an expression.  
Valid expressions (`+` may be replaced with any binary operator):
- `5`         (literal)
- `foo`       (variable)
- `foo + 5`   (variable plus literal)
- `5 + foo`   (literal plus variable)
- `foo + bar` (variable plus variable)
- `5 + 6`     (literal plus literal)

### `con`
Use `con uint8 BAR = 42;` to create a constant named BAR with value 42. The `con` keyword must always be followed by the variable type. Constants must be set when they are declared. Constant names are case-sensitive and must start with a letter.

### `print`
Use `print "Hello, World!";` to print a string to stdout followed by a new line. `print` can print any data type, but will print the ASCII equivalent characters for each byte. String provided to `print` must be contained in double quotes "".  
Use `print foo` to print the contents of a variable.

----
### Control Flow

#### `if`
The condition line of the `if` statement must be wrapped in parentheses ( ) and ended with a colon :. The conditional block must be wrapped in braces { } which must start on the following line.  
Example:  
```
if(foo == 1):
{
    /* Do something */
}
```

#### `while`
The condition line of the `while` statement must be wrapped in parentheses ( ) and ended with a colon :. The conditional block must be wrapped in braces { } which must start on the following line.  
Example:  
```
var uint8 foo;
foo = 0;
while(foo < 10):
{
    /* Do something */
    foo = foo + 1;
}
```

#### `loop`
Loops for the specified number of iterations, which may be a literal or an integer. The iteration expression of the `loop` statement must be wrapped in parentheses ( ) and ended with a colon :. The conditional block must be wrapped in braces { } which must start on the following line.  
Example:  
```
loop(10):
{
    /* Do something */
}
```

----
### Operators
| Operator	| Purpose                       | Example 		|
|:---------:| ----------------------------- | ------------- |
| +		    | Adds two numbers	    	    | `a + b`	    |
| -		    | Subtracts two numbers	        | `a - b` 	    |
| \*	    | Multiplies two numbers	    | `a * b`  	    |
| /	    	| Divides two numbers		    | `a / b`  	    |
| =         | Assignment operator           | `set foo = 5` |
| +=        | Addition-assignment operator  | `set foo += 1`|
| -=        | Subtraction-assignment operator | `set foo -= 2` |