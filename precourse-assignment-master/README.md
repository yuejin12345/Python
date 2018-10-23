# Dunder Data Pre-course Assignment
This repository contains a pre-course assignment that is intended to get everyone on the same page upon entering the class so we can quickly dive into the material. It will cover...  

1. Course Overview
2. Environment setup with Anaconda
3. Installation and basics of git/github
4. Intro to Jupyter notebooks
5. Intro to the Python programming language

# Course Overview

## Course Assumptions
There is virtually no pre-requisite knowledge assumed for this course other than a desire to get better at making sense of data. That said, this pre-course will cover quite a lot of material and it is expected that all students come to class with a good understanding of it.

## Pre-Course Assessment
When you have finished this pre-course assignment, please go the [assessment folder](assessment), read the instructions, and take the assessment.

## Course Objective
Welcome to the universe of 'making sense of data'. It spans a gigantic amount of academic disciplines and careers and would take many lifetimes to ingest into a human brain. There are many starting places for an introductory course such as this one. If we can divide this universe into four major sections that encompass all that happens within a data analysis, we might come up with the following:

1. Obtaining data
1. Exploring data
1. Learning from data
1. Building data products

All the sections have both theory (or convention/heuristics) and tools (software) that deliver the results. This class will cover just a small corner of exploring data by concentrating on a specific tool (pandas) to manipulate and analyze data. While there are many tools that can be used to explore data, it is vital to become an expert in at least one so that any data exploratory task is within your capabilities. Put another way, it is more valuable to become 90% capable in one tool than 30% capable in 10 tools. Once you go deep with one tool, you can easily obtain the same skill level in another as usually (for the high-level data science tools), there are only small differences in syntax and functionality.

Becoming a Pandas expert in one week is a difficult task. The library has seemingly endless capabilities. It is not important to learn every operation available to the pandas library. It is a hinderance to learning actual data analysis when you learn esoteric Pandas methods that are only used in very rare situations. A better strategy is to learn the most common, useful, and efficient operations. In technical jargon, we want to learn the **idiomatic** way to write Pandas to produce the results we want.

# Course Expectation

The overall expectation upon course completion is for you to be able to take any dataset and systematically produce an analysis that uncovers the primary insights. Your final analysis will be available in a report detailed with explanations, data operations, visualizations, and basic machine learning.

It is common when applying for data science positions to be faced with a take-home assignment where you are given a dataset with the requirement that you deliver a report. This course is designed so that you can excel in these situations.

# Setting up the Environment

One of the largest hurdles beginners face is setting up an environment that they can quickly get up and running and analyzing data.

### Objectives

1. Understand the difference between interactive computing and executing a file
1. Ensure that Anaconda is installed properly with Python 3
1. Know what a path is and why its useful
1. Understand the difference between a Python, iPython, Jupyter Notebook, and Jupyter Lab
1. Know how to execute a Python file from the command line
1. Be aware of Anaconda Navigator
1. Most important Jupyter Notebook tips

# Interactive Computing vs Executing a File

### Interactive Computing
Nearly all the work that we will do in class will be done **interactively**, meaning that we will be typing one, or at most a few lines of code into an **input** area and executing it. The result will be displayed in an **output** area.

### Executing a Python File
The other way we can execute Python code is by writing it within a file and then executing the entire contents of that file.

### Interactive Computing for Data Science
Interactive computing is the most popular way to analyze data using Python. You can get instant feedback which will direct how the analysis progresses.

### Writing Code in Files to Build Software
All software has code written in a text file. This code is executed in its entirety. You cannot add or change code once the file has been executed. Although most tutorials (including this one) will use an interactive environment to do data science, you will eventually need to take your exploratory work from an interactive session and put it in inside of a file.

# Installing Anaconda with Python 3
Anaconda is the name of a distribution of Python created by a company with the same name (formerly Continuum Analytics). It is currently the most popular distribution of Python for data science and contains all the popular libraries plus some extra software. 

* Please download [Anaconda with Python 3][1] now

### Reason for Python 3 and not Python 2
Jan 1, 2020 will mark the last day that Python 2 will be officially supported. Python 3 is the present and future and nearly all serious development will use it. 

# Testing for Successful Installation

Let's ensure that you the Anaconda distribution got installed correctly and that you are indeed running the latest version of Python 3.

## Windows Users
Open up the program **`Anaconda Prompt`**. This program will look very similar to the normal **`Command Prompt`** but will place the destination of the latest Python 3 version at the beginning of the path.

## Mac/Linux Users
Open up a terminal

## All Users

1. Type **`python`** at the prompt
2. Ensure that in the header you see Python version 3.X where X >= 6 
![][2]
3. If you don't see this header with the three arrow **`>>>`** prompts and instead see an error, then we need to troubleshoot here.

## Troubleshooting

### Windows
The error message that you will see is **`'python' is not recognized as an internal or external command...`**

Make sure you are running the **`Anaconda Prompt`** and not the normal **`Command Prompt`**. 

If you are in **`Anaconda Prompt`** and still getting this message then see the optional installation below

### Mac/Linux
The error message you should have received is **`python: command not found`**. Let's try and find out where Python is installed on your machine.

1. Run the command: **`$ which -a python`**    
![][4]
1. This outputs a list of all the locations where there is an executable file with the name **`python`**
1. This location must be contained in something called the **path**. The path is a list (separated by colons) containing directories to look through to find executable files
2. Let's output the path with the command: **`echo $PATH`**
![][5]
1. My path contains the directory (**`/Users/Ted/Anaconda/bin`**) from above so running the command **`python`** works for me.
1. If your path does not have the directory outputted from step 1 then we will need to edit a file called **`.bash_profile`** (or **`.profile`** on some linux machines)
1. Make sure you are in your home directory and run the command:
> **`nano .bash_profile`**
1. This will open up the file **`.bash_profile`**, which may be empty
2. Add the following line inside of it: **`export PATH="/Users/Ted/anaconda3/bin:$PATH"`** (use your Anaconda directory)
3. Exit (**`ctrl + x`**) and make sure to save
4. Close and reopen the terminal and execute: **`echo $PATH`**
5. The path should be updated with the Anaconda directory prepended to the front
6. Again, type in **`python`** and you should be good to go
7. **`.bash_profile`** is itself a file of commands that get executed each time you open a new terminal.

## Optional (Advanced) Installation for Windows Users
It is possible to run Python from the **`Command Prompt`** directly in Windows. If you so desire, [manually configure][3] your **Command Prompt**.

# More on the path (all operating systems)
The path is a list of directories that the computer will search in order, from left to right, to find an executable program with the name you entered on the command line. It is possible to have many executables with the same name but in different folders. The first one found will be the one executed.

### Displaying the path
* Windows: **`path`** or **`set %PATH%`**
* Mac/Linux **`echo $PATH`**

### Finding the location of a program
* Windows: **` where program_name`**
* Mac\Linux: **`which program_name`**

### Editing the path
* Windows: Use the [set (or setx)][6] command or from a [GUI][7]
* Mac\Linux: By editing the **`.bash_profile`** as seen above

# Python vs IPython
**`python`** and **`ipython`** are both executable programs that run Python interactively from the command line. The **`python`** command runs the default interpreter, which comes prepackaged with Python. There is almost no reason to ever run this program. It has been surpassed by **`ipython`** (interactive Python) which you also run from the command line. IPython adds lots of functionality such as syntax highlighting and special commands.

# IPython vs Jupyter Notebook
The Jupyter Notebook is a browser based version of IPython. Instead of being stuck within the confines of the command line, you are given a powerful web application that allows you to intertwine code, text, and images. [See this][8] for more details of the internals.

![][9]

# Jupyter Lab
[Jupyter Lab][11] is yet another interactive browser-based program that allows you to have windows for notebooks, terminals, data previews, and text editors all on one screen.  It is the "next-generation user interface for Project Jupyter".

# Executing Python Files
An entire file of Python code can be executed either from the command line or from within this notebook. We execute the file by placing the location of the file after the **`python`** command. For instance, if you are in the home directory of this repository, run the following on the command line to play a number guessing game.

**`python scripts/guess_number.py`**

# Anaconda Navigator vs Command Line
Anaconda comes with a simple GUI to launch Jupyter Notebooks and Labs and several other programs. This is just a point and click method for doing the same thing on the command line.

# Git and Github
Since you have access to this repository you have already successfully created a github account. To get the most out of this course you will need to install [git][12], a very popular open-source version control system that takes snapshots in time of what your current project looks like. Git itself can be very complex and there are many books written on just how to use git but we don't need anything except the very basics for our purposes. 

## Version Control
Version control is terminology used for a system (software) that tracks the changes of files over time. If you have never heard of version control I strongly recommend reading [this short intro][13] on the git main site.

## Git vs Github 
Github is a private company that hosts your git repositories online for others to view and collaborate with. Git is your local version control system that keeps track of all local file changes. In this course, you will be using Github to bring our online repositories to your local machines where you will make changes(i.e. complete the assignments) and push those changes back to us where we will be able view and comment on your assignments.  

### Let's get started with git!
1. [Download and install Git.][14] Git comes pre-installed with Macs but you'll probably want to upgrade to the latest version. You can run command **`git --version`** to see the current version.
2. **Windows users only** - During installation you will see the following window. Make sure the middle option is checked so you can run git from the command prompt. ![][16]
3. If you've never set up Git before, you need to set your username and email. [Go here][15] and follow the short instructions.
4. Fork this repository by going to the top right corner of this page and clicking fork.
5. Clone this repository to your local computer. Above the file listings towards the top of this page you will see a green button with the words 'clone or download' in it. Click that button and click the small clipboard icon with the URL of this repo with .git appended to it. This will copy the url.
6. Create a directory on your local machine that you'd like to save all your work for this class. Perhaps call it `Dunder Data Pre-Course`
7. Open a terminal and **`cd`** into that directory. Run the command `git clone https://github.com/<your username>/precourse-assignment.git`. Use your copied url here. Make sure you are using the URL with **your Github username**. This will pull all the files down into your local file system. You now have an exact replica of what you are reading here on github.

### Submitting your first assignment on github

1. For this pre-course assignment, you will be modifying only the `.ipynb` files.
1. As you are making changes to your files locally, it is a good idea to be continually committing your changes and pushing them to github.
1. Run `git add <filename>.ipynb` to tell Git this is the file you would like to be committing
1. If you have edited multiple .ipynb files you can simply write `git add *.ipynb` to add all the .ipynb files to the index (index is a term for the staging area - the area right before you commit and take the snapshot)
1. Run `git commit -m "I have finished the section on lists"` to **commit** your file locally and 'take a snapshot'. Always add messages to your commits with `-m "<your message here>"`
1. Run `git push origin master` to push your changes to your remote repository on github. Check github to make sure the remote files were changed
1. repeat steps 3-6 several times during the pre-course assignment to ensure you don't lose your changes

## Git Tutorials
* Corey Schafer has a [good tutorial on Git][17] that I recommend watching. It only covers Git itself and not Github.
* Practice writing git commands on the [tryGit][18] website.
* You can always read the [documentation][19]. It is very thorough, though dense and not suited for beginners.

# Repository Files
 As you can see at the top of this page, there are multiple files in this repository. 

1. The README file that you are reading right now
1. The `.ipynb` files where all the magic happens
1. A resources section with lots of places to get help and learn more
1. A section on getting started on spaced repetition - a proven method to help retain knowledge for longer periods of time.

# Other Programming Environments
There are many other environments to write Python code for data science. Check out the [environments](environments.md) document for more info on setting up sublime, installing PyCharm educational edition and executing Python scripts.

# The Actual Assignment!
OK, so you've installed Anaconda and git and are ready for your pre-course assignment. To begin learning...

1. Open a terminal
2. `cd` into the directory where this repository is located (the place you cloned this repository)
3. Run the command `jupyter notebook`
4. A new browser tab will open up located at `localhost:8888` with a listing of all the files in this repository. 
5. Click on `1. Intro Jupyter Notebook.ipynb` and a Jupyter notebook will open that will walk you through the entire assignment.
6. Complete each numbered notebook
7. Check your answers as you go by opening the precourse solutions notebook only AFTER you have attempted the problems on your own
8. It is mandatory that you complete the precourse. We will immediate begin learning pandas on day 1.
9. Check out the resources when finished

# Extra Python Assignment
After completing the assignments in the Jupyter notebooks, it is highly recommended to read and complete the exercises in the book [Think Python 2nd Edition](http://greenteapress.com/wp/think-python-2e/). The book is free to download and covers all the material in the notebooks plus quite a bit more. You can find many of the solutions in [this github repository](https://github.com/AllenDowney/ThinkPython2/tree/master/code).

Remember to always be committing. Please finish the assignment before the start of the course. Answers will be provided a few days prior to the course.

## Resources
https://github.com/tdpetrou/precourse-assignment/blob/master/resources.md


[1]: https://www.anaconda.com/download
[2]: images/pythonterminal.png
[3]: https://medium.com/@GalarnykMichael/install-python-on-windows-anaconda-c63c7c3d1444
[4]: images/which_python.png
[5]: images/path_mac.png
[6]: https://stackoverflow.com/questions/9546324/adding-directory-to-path-environment-variable-in-windows
[7]: https://www.computerhope.com/issues/ch000549.htm
[8]: http://jupyter.readthedocs.io/en/latest/architecture/how_jupyter_ipython_work.html
[9]: images/jupyter_internal.png
[10]: images/windows_anaconda_check.png
[11]: http://jupyterlab.readthedocs.io/en/stable/
[12]: https://git-scm.com/book/en/v2/Getting-Started-Git-Basics
[13]: https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control
[14]: https://git-scm.com/download
[15]: https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup#Your-Identity
[16]: /images/git_windows.png
[17]: https://www.youtube.com/watch?v=HVsySz-h9r4
[18]: https://try.github.io
[19]: https://git-scm.com/book/en/v2

