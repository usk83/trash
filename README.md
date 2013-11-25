trash
=====

Remove Command using a trash box.

`rm` command removes files/directories from the disk and they are not recoverable.
It is stressful because we are used to benefit from the trash box on a GUI system, Windows, Mac, Linux, etc..

`trash` command brings you the removal command with recoverable files/directories.

# Installation

On Mac, you can install scripts by [Homebrew](https://github.com/mxcl/homebrew):

    $ brew tap rcmdnk/rcmdnkpac
    $ brew install rcmdnk-trash

If you have [brewall](https://github.com/rcmdnk/homebrew-brewall), add following lines to Brewfile:

    tap 'rcmdnk/rcmdnkpac'
    brew 'rcmdnk-trash'

then, do:

    $ brewall install

Or if you write like:

    tapall 'rcmdnk/rcmdnkpac'

and do `brewall install`, you will have all useful scripts in
[rcmdnkpac](https://github.com/rcmdnk/homebrew-rcmdnkpac).

You can also use an install script on the web like:

    $ curl -fsSL https://raw.github.com/rcmdnk/trash/install/install.sh| sh

This will install scripts to `/usr/bin`
and you may be asked root password.

If you want to install other directory, do like:

    $ curl -fsSL https://raw.github.com/rcmdnk/trash/install/install.sh|  prefix=~/usr/local/ sh

Or, simply download scripts and set where you like.
# Usage

    trash [-rficClbv] [-t <trash_box>] <file/directory>
    
    Arguments:
       -r              Remove directory (default: 0)
       -f              Remove w/o confirmation (default: 1)
       -i              Remove w/ confirmation (default: 0)
       -t              Use given trash box instead of ~/.Trash
       -c              Clean up trash box (make it less than MAXTRASHBOXSIZE)
       -C              Clean up trash box (make it empty)
       -l              List up deleted files/directories in the trash box
       -b              Restore (turn Back) the file from the trash box
       -v              List up files/directories in trash box, too
       -h              Print this HELP and exit
    
    To use trash, please specify following variables
    in .bashrc or your setting file like:
    
    export TRASHLIST=~/.trashlist # Where trash list is written
    export TRASHBOX=~/.Trash # Where trash will be moved in
                             # (.Trash is Mac's trash box)
    export MAXTRASHBOXSIZE=1024 # Max trash box size in MB
                                # Used for clean up
    export MAXTRASHSIZE=`echo $MAXTRASHBOXSIZE "*" 0.1|bc -l|cut -d. -f1`
        # Trashes larger than MAXTRASHBOXSIZE will be removed by 'rm' directly

# References

* [rm -rfのプロテクト、コマンドラインでのゴミ箱](http://rcmdnk.github.io/blog/2013/04/23/computer-bash-linux-mac/)



[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/rcmdnk/trash/trend.png)](https://bitdeli.com/free "Bitdeli Badge")
