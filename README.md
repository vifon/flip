# NAME

flip -- flip the command arguments

# SYNOPSIS

**flip** \[ options \] COMMAND \[ ARGUMENTS ... \]

# DESCRIPTION

**flip** swaps the first two command arguments and executes the
resulting command. The original use-case was reverting the effects of
**mv(1)**.

The arguments swapped are the two left-most arguments that are not
options i.e. do not start with a hyphen. The prefix commands like
**sudo** are taken into consideration, so `sudo mv foo bar` is handled
properly (`sudo mv bar foo`).

# OPTIONS

- `--dry-run`, `-n`

    Only print the flipped command, do not execute anything.

- `--quiet`, `-q`

    Do not print the flipped command before the execution.

# USAGE

    $ touch foo
    $ ls
    foo
    $ mv foo bar
    $ ls
    bar
    $ flip mv foo bar    # or "flip !!"
    mv bar foo
    $ ls
    foo

# AUTHOR

Wojciech 'vifon' Siewierski < wojciech dot siewierski at onet dot pl >

# COPYRIGHT

Copyright (C) 2017  Wojciech Siewierski

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see &lt;http://www.gnu.org/licenses/>.
