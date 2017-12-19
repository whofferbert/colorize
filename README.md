# colorize

This perl utility can colorize text at the command line based on rules that you define.

The colorization happens via ANSI escape sequences.

The rules are based on perl regex.

This was written to ease the eyes of people who have to work at the CLI and look at logs a lot.

Requires the following to run:

Perl 5.010

Getopt::Long

File::Basename


```perl
$ ./colorize -h

  This program colorizes text at the command line based on a ruleset that you can provide it. 
  It requires either piped input, or a provided filename.

    Basic Usage: colorize [options] /path/to/file
                 ... | colorize [options]

  Options:

    -use-ruleset [/path/to/ruleset.rules]
      Use the specified ruleset for colorization, instead of the defaults in ./colorize.d

    -add-ruleset [/path/to/ruleset.rules]
      Use the specified ruleset for colorization, in addition to the defaults in ./colorize.d

    -use-ruleset-dir [/path/to/ruleset.d/]
      Use the specified ruleset directory, instead of the default: ./colorize.d

    -less
      View the output in less

    -show-colors
      Print the available color pallette

    -help       Print this help.

  Examples:

    # show the available colors
    colorize -show-colors
 
    # colorize some grep results and view with less
    dmesg | grep -Ei "warn|err" | colorize -less
 
    # Look at the contents of a script in less
    colorize ./colorize -less
 
    # Another way to use less and preserve colors...
    colorize ./colorize | less -r
 

```
