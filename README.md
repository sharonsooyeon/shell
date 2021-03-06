# shell
CS 240 Final Project: Introduction to Machine Organization with Laboratory

A simple `bash` shell. Interprets command language and manages processes.
  1) Uses process control features of the operating system (`fork`, `execvp`, `waitpid`, etc.)
  2) Manages basic concurrency of foreground and background processes
  3) Uses simple C data structures

In this project, we practiced our debugging skills (using `gdb` and `valgrind`), read documentation to find relevant library functions, and increased our proficiency with C and systems programming.

## To run the program
  1) Clone the repository
  2) Open Terminal and run `./shell`
  3) To exit, type `exit` or ctrl+D

## Implemented commands
  1) Built-in commands: `exit`, `help`, `cd`, and `jobs` (`fg` and `bg`)
  2) Executable commands: `ls` `emacs`, and other executable programs from the filesystem run in a separate process.
  3) `jobs`: reports all background jobs. `fg` and `bg` report jobs in the foreground and background, respectively.

## Example usage
```
> sleep 30 &
[1]+ 4709  Running  sleep 30 &
> sleep 55 &
[2]+ 4828  Running  sleep 55 &
> echo she sells C shells by the C store
she sells C shells by the C store
> echo world                    # ... >=30 seconds
world                           # after sleep 30 &
[1]  4709  Done     sleep 30 &
> cd ..
> man sleep
...
> echo accio                    # ... >=55 seconds
accio                           # after sleep 55 &
[2]  4828  Done     sleep 55 &
>
```
