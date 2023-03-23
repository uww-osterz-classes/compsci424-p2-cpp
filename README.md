# UWW COMPSCI 424 Program 2 in C++

## Your notes for me

*If you have notes or messages for me, please put them here so I can see them.*

## About this repository and autograding
 
Use this template for Operating Systems Program 2 in C++.

**Your C++ code files must use the extension `.cpp`**, except header files may use the extension `.h`. This will keep things more consistent as I grade.

The included files use a (mostly) typical C++ file structure for a program like this. Feel free to change, add, divide, combine, or delete files; add or combine classes; create more methods; modify the existing methods; and more. Providing correct functionality is more important than having a specific program structure.

If you develop on **washington.uww.edu**, suggested compiler commands are `gcc-5` (C) or `g++-5` (C++).

If you are encountering problems, please commit and push your code, then [email me](osterz@uww.edu) with a description of what's happening. I will look at your repository on GitHub to try to help you debug.

## Advice for C++ programmers

This advice is also posted on the Program 2 page on Canvas. Updates, if any, will be posted there.

You have at least three options for adding concurrency to your program.

1. **Preferred:** The C++11 standard includes a `<thread>` header, and the C11 standard includes a `<thread.h>` header. These might be the easiest and most OS-independent ways to add threads to your C or C++ code. References:
    * [C++ thread support library](https://en.cppreference.com/w/cpp/thread) on cppreference.com
    * [C++ multithreading reference](http://www.cplusplus.com/reference/multithreading/) at cplusplus.com: choose the links to explore the other C++11 thread support libraries
    * [C thread support library](https://en.cppreference.com/w/c/thread) on cppreference.com
    * [Thread Creation - ModernesCPP.com](https://www.modernescpp.com/index.php/thread-creation) (also see other pages available at the "What's Next" link for more example)
    * [Concurrency in C++11](https://www.classes.cs.uchicago.edu/archive/2013/spring/12300-1/labs/lab6/) from University of Chicago
    * Note: The C++20 standard supports a `<semaphore>` header, but please do not use it!
        - Many C++ compilers (including the one I use) do not reliably support C++20 features yet.
        - If you write in C++, plan to implement your own semaphores or use a different synchronization tool (e.g., the `mutex` class from the `<mutex>` standard header).

2. You may use the Pthreads (POSIX Threads) library to make your program multithreaded.

    * Note that Pthreads will probably not work on a Windows system. It will work on Linux if the necessary packages are installed. It may also work on Mac OS.
    * If you use Pthreads, add the option `-lpthread` to your compile command. This will link your code with the Pthreads library. (You will get a cryptic error message if you don't include this option.)
    * Short introduction: [Pthread Primer](http://pages.cs.wisc.edu/~travitch/pthreads_primer.html) from Tristan Ravitch, written while he was a graduate student at UW-Madison.
    * Longer tutorial and/or reference: [POSIX Threads Programming](https://hpc-tutorials.llnl.gov/posix/) from Blaise Barney at Lawrence Livermore National Laboratory. This is widely considered one of the best Pthreads tutorials.

3. You may choose to make your program multiprocess (with the POSIX `fork` and `wait` system calls). Here's a quick overview of [multiprocess programming with `fork` in C or C++](https://ece.uwaterloo.ca/~dwharder/icsrts/Tutorials/fork_exec/) from Douglas Harder at the University of Waterloo.
    * **Important note:** This might only work on a Unix/Linux system. It will not work on Windows (except under the Windows Subsystem for Linux, maybe), and it may not work on Mac OS either.
