Platform Support: POSIX
=======================

Overview
--------
This port targets [POSIX] operating systems (Windows/Cygwin, macOS, Linux,
BSD, etc.) with `gcc`.

[POSIX]: https://en.wikipedia.org/wiki/POSIX


Building with macOS
-------------------
Install Xcode to get LLVM with a gcc wrapper and GNU Make.


Installing Cygwin for 32-bit Windows development
------------------------------------------------
Cygwin is a POSIX environment for Windows systems. It provides a bash
shell and supports many familiar packages from Unix-like operating systems
(like macOS, Linux and OpenBSD). Here are instructions for installing
Cygwin on your PC in order to build and run the XBee sample applications.

Go to <http://cygwin.com/install.html> and download `setup.exe`.

Launch `setup.exe` and accept the default settings:

- Install from Internet
- Install to c:\cygwin for all users
- Use c:\Windows\Temp (or some other temp directory) as the Local Package
  Directory
- Choose a few mirrors for downloading

Select the following packages:

    gcc, gcc-core, gcc-g++, gcc4, gcc4-core, gcc4-g++, binutils, gdb, make

Allow Cygwin to install any dependencies for those packages.

Once installed, launch "Cygwin Bash Shell" and navigate to the directory
where you installed the library. Note that `/cygdrive/c` is the path
to get to your C drive. Go into the `samples/posix` directory and type
`make all`. If you've installed everything correctly, it should build
all of the sample programs.

Note that the executable files you build require support DLL files to
run on systems without Cygwin installed. At minimum, you'll need
`cygwin1.dll` in the same directory as the executable, and possibly
`cyggcc_s-1.dll`. If you're missing a DLL, you'll get a warning with the
missing DLL file's name when you try to launch the program.

To build standalone, Win32-native executables, use the Win32 platform with
MinGW and MSYS (see `ports/win32/README.md`).
