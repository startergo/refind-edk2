# Building rEFInd with EDKII on OS X

This repository contains EDKII build information files (DSC and DEC) for building rEFInd in the context of the EDKII. The author of rEFInd has provided a Makefile for building rEFInd using the GCC toolchain and the EDKII on Linux, but there are a number of `ld` and `gcc` options used that are incompatible with the Mac OS X toolchain. Rather than do the right thing and figure out what the appropriate options are, I've just dumped the rEFInd source into a new *Package* in the EDKII and added DSC and DEC files to get it to build on OS X.

This works for me on Mac OS X 10.7.4 with Xcode 4.4 and its command line tools.

## Building

1. Prepare and build your EDKII environment (outside of the scope of this document).

2. Clone this repository into the root directory of the EDKII.

        $ cd /path/to/edk2
        $ git clone -b MemLog https://github.com/jief666/refind-edk2.git RefindPkg

3. Download the latest version of the [rEFInd source](http://sourceforge.net/projects/refind/files/) into the RefindPkg directory and unpack it.

        $ cd RefindPkg
        $ git clone -b MemLog git://git.code.sf.net/u/jief7/refind refind-master
        
4. Build the package.

        $ cd ..
        $ source edksetup.sh
        $ cd RefindPkg
        $ ./ebuild
