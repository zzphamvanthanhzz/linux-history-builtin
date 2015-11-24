1_history -c: clear ~/.bash_history
history -w: flush history to the bash_history file

Why: As noted above, history -c empties the file ~/.bash_history. It is important to note that bash shell does not immediately flush history to the bash_history file. So, it is important to (1) flush the history to the file, and (2) clear the history, in all terminals. That's what the commands above do. 
 

2_Understanding Bash His history:
http://www.symkat.com/understanding-bash-history

*History is maintained both in a ~/.bash_history and in ram. History contained in ramis only written after a user log out of his session.

*History variables:
-HISTFILE: location of the history file. When the bash is logged out of, the content of the history command will be written to this file.

-HISTFILESIZE: maximum number of lines that may be in history file. 
When bash writes to the history file, the oldest commands that go over this maximum number will be deleted.

-HISTCONTROL: contains instructions for what should be ignored when added to the history file.

+ignorespace: any line that begins with one or more spaces will not be added to history FILE

+ignoredups: lines that match the previous entry in history are not saved

+ignoreboth: both ignorespace and ignoredups

+Not Defined: no controls will be applied before the line is entered into history.

-HISTSIZE: contains maximum number of lines that be contained in the in-ram version of history.



3_Bang Bang:
 1999  history | tail -n10
 2000  exit
 2001  history | grep 20
 2002  tail -f ~/.bash_history 
 2003  58 198
 2004  12 52
 2005  58 198
 2006  12 30
 2007  12 235 zdeploy
 2008  history

!-2 : last two command  (2007)
!! : last command (2008)
!1 : first command in history


4_How history command work:http://blog.pluralsight.com/how-to-use-bash-command-line-history

[thanhpv@ThinkPad-T450:~] $ type history
history is a shell builtin

http://www.linuxnix.com/what-is-a-built-in-command-in-linux/: 


5_Linux built-in command:
*A built-in command is simply a command that the shell carries out itself, instead of interpreting it as a request to load and run some other program.
*First, it's usually faster, because loading and running a program takes time.
*Secondly, a built-in command can affect the internal state of the shell. Example: cd must be built-in, because an external program can't change the current directory of the shell.  

**************************************************************************************************************************************************************
*****************************http://www.gnu.org/software/bash/manual/html_node/Shell-Builtin-Commands.html****************************************************
**************************************************************************************************************************************************************

6_history source code:
bash/builtins/history.def

