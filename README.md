Download Link: https://assignmentchef.com/product/solved-cop4600-ex-3-console-debugging
<br>
<h1></h1>

In most cases, you’ve written C/C++ code that was definitely broken, and it led to hours of hair pulling, and mundane searching for a simple issue that could have been easily identified by larger scaled debugging tools. Well thanks to GDB, there’s less monotony! This exercise will teach you the fundamental, and very powerful tools that the GNU Debugger offers. You will analyze, deconstruct, and debug given programs to help you learn the necessary skills of using a console debugger that will help you with future projects, and any code that you will write. At the end of the exercise, you’ll submit several annotated screenshots.<strong> </strong>

<h1>Structure</h1>

This exercise will follow this basic structure:

<ul>

 <li>Install <strong>GDB 9.1</strong> and its utilities</li>

 <li>Research on how to utilize GDB and its commands, a helpful link will be provided</li>

 <li>Create a simple program, and play around with GDB’s features</li>

 <li>Debug <strong><em>c</em></strong> and explain the issue encountered / what it was trying to do 5) Analyze <strong><em>password</em></strong> by digging through its code in order to obtain the key</li>

</ul>




<strong> </strong>

<h1>Installation (GDB)</h1>

Within Reptilian, use the <strong>apt-get </strong>command to update the Linux package list, and install GDB

<strong>$</strong> <strong>sudo apt update </strong>

<strong>$</strong> <strong>sudo apt install gdb</strong>

<strong> </strong>

Test GDB to make sure that it’s the correct version by prompting it:

<strong>$</strong> <strong>gdb -version</strong>




<strong><em> </em></strong>

<strong><em> </em></strong>

<strong><em>Your output should look something like this </em></strong>

<strong><em> </em></strong>

<strong> </strong>

<h1>Utilizing GDB</h1>

Utilizing the debugger is actually quite simple, in order to start up the debugger on a sample program <strong><em>myProgram </em></strong>we would type:

<strong> </strong>

<strong>$</strong> <strong>gdb myProgram</strong>

<strong> </strong>

From there, we can learn more about GDB and how to use it by keying:




<strong>(gdb)</strong> <strong>help</strong>




We highly suggest you reference the bottom link to the GDB manual, and the help command if you ever get stuck, or want to learn more about its features. Using the debugging tool follows a simple guideline that will be outlined below:

<ul>

 <li>Run the program and analyze what it’s doing</li>

 <li>Set up necessary breakpoints, and step through the program</li>

 <li>Find the issues utilizing the various tools that GDB offers</li>

</ul>

<strong> </strong>

<strong> </strong>

<strong> </strong>

<h2>Running</h2>

To run the code, simply key in:

<strong>(gdb)</strong> <strong>run</strong>

This will run the code as your normal shell would, except it will point out several helpful debugging hints whenever you compile your program with the “<strong>-g</strong>” flag.










<h2>Breaking</h2>

After running the code, you may choose an address, or function name in which you want to place your breakpoint:

<h3>(gdb)break main</h3>

This will place a breakpoint inside the program at the address of main, and from there, you will be able to step through the code, or run whatever code the method contains

<strong> </strong>




<h2>Stepping</h2>

The most useful command next to creating breakpoints, stepping allows the user to step through each line of code to find what the outputs are, and what possible issues the code contains:

<strong>(gdb)</strong> <strong>step</strong>

After stepping through the program, you may delete the breakpoints that are not necessary to you

<h3>(gdb)delete</h3>

<h2>Useful Commands</h2>

<ul>

 <li><strong>run </strong></li>

 <li><strong>break </strong></li>

 <li><strong>step </strong></li>

 <li><strong>delete </strong></li>

 <li><strong>next </strong></li>

 <li><strong>up </strong></li>

 <li><strong>down </strong></li>

 <li><strong>print </strong></li>

 <li><strong>info </strong></li>

 <li><strong>quit </strong></li>

</ul>

<strong> </strong>

<h1>Application</h1>

Now that we have learned some basic commands, it’s time to apply our newfound knowledge to debug some programs that you will make, and that we provide




<h2>Part 1 – Simple Program</h2>

Create your own <strong><em>“Hello World”</em></strong> program and play around with the capabilities of GDB. When you’re done, <u>take a screenshot of your program being run in GDB with a breakpoint being set in</u> <strong><u>main</u></strong><u>.</u>

Compiling your program uses these commands:

<strong>$</strong> <strong>gcc -o myProggy.o myProggy.c</strong>

<strong>$</strong> <strong>gcc -g -o myProggy.o myProggy.c</strong>

<strong> </strong>

<h2>Part 2 – Process Table</h2>

Download the <strong><em>process.c </em></strong>code from the source folder of the exercise and compile it with the commands given at the bottom of this page. This program emulates a (very) rudimentary process table, however, there’s a catch. Inside the program is a bug, and you must use the GDB to find the issue.

When you’re done, you’re going to <u>take a screenshot of the issue in GDB, explain why it broke</u> <u>the code (in a canvas submission comment), fix the code (only one line), and submit another</u> <u>screenshot of the working code’s output.</u>

To compile <strong><em>process.c</em></strong>

<strong>$</strong> <strong>gcc -w -g -o process process.c -lpthread -lrt</strong>

<h2>Part 3 – Password</h2>

Download the source file <strong><em>password</em></strong> from the same folder as <strong><em>process.c</em></strong>. As you will notice, this file is an output, and it was compiled <strong>without</strong> debugging symbols. In order to complete this part, you will need to use GDB to find a password that is hidden WITHIN the program itself (you should start by decompiling that code). Look into the <strong><em>info </em></strong>of the program to see what it contains. See if you can track its motion through compilation. You will take a screenshot of <strong>where</strong> you found the password <strong>before</strong> decoding it, and the message received <strong>after</strong> typing in the correct password.

<strong><u>Hint:</u></strong> Use a HEX translator, like the one provided at the bottom of the page

<strong> </strong>