Download Link: https://assignmentchef.com/product/solved-csis3280-assignment-1-random-algebraic-expression-generator
<br>
You are asked to write a PHP program to generate randomly an algebraic expression. If you forgot what an algebraic expression is, this is an example of an algebraic expression: 6x -5 + 7x – 3x<sup>2 </sup>. You can read more about the <a href="https://en.wikipedia.org/wiki/Algebraic_expression">algebraic</a> <a href="https://en.wikipedia.org/wiki/Algebraic_expression">expressions at Wikipedia</a><a href="https://en.wikipedia.org/wiki/Algebraic_expression">.</a>

The main idea is to generate randomly an algebraic exprssion with mutiple terms, then a student will simplify that expression. For example, a student can simplify <strong><em>6x -5 + 7x – 3x<sup>2</sup></em></strong>    to     <strong><em>-3x<sup>2 </sup>+ 13x – 5 </em></strong>

In fact, the goal is to write a web app that students can use to practice simiplification of algebraic expressions.

In assignment1, your taks is only to generate the expression. You <u>do not need to work on</u> the checking whether the answer of the user is correct or not.

<strong>Requirement: </strong>

<ol>

 <li>Create a php file and call it <strong><em>php</em></strong>. In this file, define two functions:

  <ol>

   <li><strong>display_html_head</strong>: this function has 1 input parameter which is the title of the HTML file. The function does not return any value. In this function, use HEREdoc to print doctype, &lt;html&gt;, &lt;head&gt;, &lt;title&gt;, and &lt;body&gt; of a HTML file. Note that when you call this function, you must pass the title of the document that you want to display inside &lt;title&gt; and &lt;/title&gt; tags</li>

   <li><strong>display_html_foot:</strong> this function does not have any input parameter and it does not return any value. Using a HEREdoc, print end tags for &lt;/body&gt; and &lt;/html&gt;</li>

  </ol></li>

 <li>Create another php file, as your main php code, and use <strong><em>require</em></strong> to add lib.php to this main code.</li>

 <li>Define a global variable called This variable stores the degree of the algebraic expression that we are going to generate (the greatest exponent in an algebraic expression is the degree of that expression. For example, degree of <strong><em>x+3</em></strong> is 1 and the degree of <strong><em>x<sup>2</sup> + 3x – 1</em></strong> is 2). We want to write a program that by changing the value of this variable, the program automatically generates an expression of that degree. Therefore, the final program will be fully parametric based on the degree parameter.</li>

 <li>Define another global variable called This variable stores the number of the terms that we want to generate in the expression. Num_of_terms depends on the degree of the expression. We use the following formula:</li>

</ol>

<strong>Num_of_terms = 2 x degree + 3 </strong>

It means that if the degree is 1, we will generate 5 terms (e.g.  9x-1+x-5x+1). If the degree is  2, we generate 7 terms (e.g.  x+14x<sup>2</sup>-6+x<sup>2</sup>-2x-8x<sup>2</sup>-4)

<ol start="5">

 <li>Define a function called This function has only 1 input parameter, degree, and it returns a two-dimensional array called terms: in the first row of this 2D array we store coefficients and in the second row we store exponents.</li>

</ol>

In this function use <strong>rand()</strong> pre-defined function of PHP to generate a random number for coefficients and exponents of the terms. Coefficient can be between -20 and 20 <strong><u>excluding 0</u></strong> (a coefficient cannot be zero). Exponents can be from 0 to degree value. For example, if the degree is 2, exponents can be from 0 to 2 (i.e., 0, 1, and 2).

<ol start="6">

 <li>Define a function called This function checks if the generated expression meets some requirements. This function has 2 input parameters, 2D-array terms, and degree, and it returns a Boolean value. To make the generated expression interesting for practice of the student, we require that there must be <u>at least</u> 2 terms from each degree in our expression. For example, the expression 2x + 3 – 1 + 5 – 2 does not meet the requirement because there is 1 term of degree 1 (2x) and there are 4 terms of degree 0 (3, -1, 5, and -2). But 2x + 3 – 1 + 5x – 2 meets the requirement because there are at least two terms of degree 1, (2x and 5x) and three terms of degree 0 (3, -1, and -2). Note that your function must work for all degrees. It means if the current value of the global variable <strong><em>degree </em></strong>is 3, the generated expression meets requirements if there are at least 2 terms of degree 3, at least 2 terms of degree 2, at least 2 terms of degree 1 and at least 2 terms of degree 0. For example, 2x<sup>3</sup>-5x+3-7x<sup>2</sup>+x-4x<sup>3</sup>-6+3x<sup>2</sup>+5  meets requirements, and your function must return true for this expression.</li>

 <li>Define a function called This function receives the 2D array of terms as input and prints the formatted expression on the HTML file. This function does not return any value. Some point to implement in your <strong><em>print_expression</em></strong> function:</li>

</ol>




<ol>

 <li>If the first term is positive, we do not put a plus sign before it. For example, we do not print <strong><em>+3 – 5x + 7 </em></strong>instead we print<strong><em> 3 – 5x + 7</em></strong>, however if the first term is negative, we display minus sign:<strong><em> -6x + 6 – 2x</em></strong></li>

 <li>When a coefficient is one, it is omitted (e.g. 1x<sup>2</sup> is written x<sup>2</sup>).</li>

 <li>When the exponent (power) is one, it is omitted (e.g., x<sup>1</sup> is written x)</li>

 <li>When the exponent is zero, the result is always 1 (e.g., 3x<sup>0</sup> is written 3, since x<sup>0</sup> is always 1).</li>

 <li>You can use &lt;sup&gt; HTML tag for displaying an exponent.</li>

 <li>You can use abs predefined function for finding absolute value of a coefficient.</li>

</ol>

<ol start="8">

 <li>Define a function called This function has one parameter, degree, and it does not return any value. The task of this function is to generate an expression and then verify if it meets the requirements. If it meets, display it, else repeat until an expression that meets the requirement is generated. In this function, you call <strong>generate_expression</strong>, <strong>meets_requirements</strong>, and <strong>print_expression</strong> inside a loop.</li>

 <li>On top of your code, after the global variables, call <strong><em>display_html_head</em></strong>, <strong><em>display_expression</em></strong>, and <strong><em>display_html_foot</em></strong> The details of how to call these functions with passing values to them is left to you.</li>

 <li><strong>IMPORANT</strong>: you must write your program such that by changing ONLY THE VALUE of degree global variable, your program generates a random expression of that degree. (You must not change any other part of your code.)</li>

</ol>