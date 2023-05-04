Download Link: https://assignmentchef.com/product/solved-cse-238systems-programming-project-1-binary-data-converter
<br>



The purpose of this assignment is to become more familiar with bit-level representations of integers and floating-point numbers.




In this project, you will implement an application, in C, Java or Python programming language; that takes

<ul>

 <li>a hexadecimal number and</li>

 <li>the data type to be converted, as input and converts the number according to the predefined format and gives the converted data as output.</li>

</ul>




The data type can be any of the following:

<ul>

 <li>signed integer (S)</li>

 <li>unsigned integer (U)</li>

 <li>floating point number (F)</li>

</ul>




The size of the input can be 1, 2, 3 and 4 bytes, if input is other than these sizes then an error message will be given.




<ul>

 <li>If the selected data type is signed integer, your program will convert the number using 2’s complement representation.</li>

 <li>If the selected data type is unsigned integer, number will be converted using unsigned integer representation.</li>

 <li>If the selected data type is floating point number, you will use IEEE-like format. The number of exponent bits according to given data size will be like the following:

  <ul>

   <li>if 1 byte (i.e., 8 bits), 4 bits will be used for exponent part o if 2 bytes (i.e., 16 bits), 6 bits will be used for exponent part o if 3 bytes (i.e., 24 bits), 8 bits will be used for exponent part o if 4 bytes (i.e., 32 bits), 10 bits will be used for exponent part o For each given data size 1 bit will be used for sign and remaining bits will be used for fraction.</li>

   <li>While calculating the mantissa to get the floating-point value, you will only use the first 13 bits of the fraction part (If the data size is 3 or 4 bytes). You will use “round to even” method for rounding fraction bits to 13 bits.</li>

  </ul></li>

</ul>







Details about the program are listed below:

<ul>

 <li>At the beginning of the execution, your program will prompt for the input. If the input has odd number of characters complete it to even by adding 0 to the MSB.

  <ul>

   <li>For example;

    <ul>

     <li>If the number entered is A57, it will be stored as 0A57 and its size is 2 bytes.</li>

     <li>If the number is 12345, it will be stored as 012345, and its size is 3 bytes.</li>

     <li>If the input is 123456789, then an error message is given. (bigger than 4 byte)</li>

     <li>Any inappropriate input results an error message. (Only digits and characters from A to F will be accepted as an input)</li>

    </ul></li>

   <li>After a valid input is taken, the user will be prompted for the data type:</li>

  </ul></li>

</ul>

Example:

Data type: F







<ul>

 <li>And then your program will calculate the decimal value of input with the given information:</li>

</ul>

<strong>Example 1: </strong>

<strong>        Enter the number: 400190F0  </strong>

<strong>Data type: F</strong> o Floating point number is:

<strong>40 01 90 f0, </strong>in binary:<strong> 0100 0000 0000 0001 1001 0000 1111 0000 </strong>

<ul>

 <li>In the specification, we are given that our 4 byte IEEE-like floating point numbers have 10 bits of exponent part, so Bias = 2<sup>10-1 </sup>– 1 = 511:</li>

</ul>

Sign bit = <strong>0 </strong>

Exponent = <strong>(1000000000)<sub>2</sub></strong> <strong>= 512</strong>

<strong>  </strong>Fraction = <strong>0000110010000</strong><strong>11110000</strong> → rounded fraction =<strong> 0000110010001 </strong>mantissa =<strong> 1+1/32+1/64+1/512+1/8192 = 1.0489501953125 </strong>

Decimal value =<strong> (-1)<sup>0</sup> * 1.0489501953125 * 2<sup>512-511</sup> = 2.097900390625 </strong>The printed value will be: <strong>2.09790</strong> <strong>Example 2: </strong>

<ul>

 <li>If the input;</li>

</ul>

<strong>Enter the number: 80180000 </strong>

<strong>Data type: F</strong> o Floating point number is:

<strong>80 18 00 00, </strong>in binary:<strong> 1000 0000 0001 1000 0000 0000 0000 0000 </strong>

<ul>

 <li>In the specification, we are given that our 4 byte IEEE-like floating point numbers have 10 bits of exponent part, so Bias = 2<sup>10-1 </sup>– 1 = 511:</li>

</ul>

Sign bit = <strong>1 </strong>

Exponent = <strong>0000000000 </strong>→<strong> denormalized number</strong>

<strong>                 </strong>Fraction = <strong>1100000000000</strong><strong>00000000</strong> → rounded fraction =<strong> 1100000000000 </strong>

mantissa =<strong> 0+1/2+1/4 = 0.75 </strong>

Decimal value =<strong> (-1)<sup>1</sup> * 0.75 * 2<sup>1-511</sup> = </strong>−<strong>2.23750</strong><strong>222</strong><strong>e</strong>−<strong>154 </strong>

The printed value will be: –<strong>2.23750e-154  </strong>

<strong>Example 3: </strong>

<strong>        Enter the number: 83A  </strong>

<strong>Data type: S</strong> o Floating point number is:

<strong>08 3A, </strong>in binary:<strong> 0000 1000 0011 1010  </strong>

<ul>

 <li>It is positive binary number and it will be directly converted to decimal The printed value will be : <strong>2106 </strong></li>

</ul>







<ul>

 <li>Floating point numbers may be NaN, +0, -0 or infinity. In these cases, the output will be:</li>

 <li>NaN</li>

 <li>∞</li>

 <li>-∞</li>

 <li>0</li>

 <li>-0</li>

</ul>




<ul>

 <li>For the output, the floating-point numbers will have precision of maximum 5 digits after the decimal point.</li>

</ul>




<ul>

 <li><strong><u>You cannot use library functions</u></strong> for the binary to decimal conversions.</li>

</ul>




Your grade will be computed out of a maximum of

For the remaining, you will have a project quiz. The date of this quiz will be announced later.




You will submit the source code of your program using the Canvas service. The file name should include your name and surname, e.g., fatmacorutergin.c




This is an individual project.











