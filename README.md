xvdb
====

Visual debug interface for gdb

This is another tilt at the windmill of a graphical interface for gdb.
I'm motivated by a desire to use my typical code quality technique of
stepping through each new line of code in the debugger at least once.
I picked this technique up from 'Writing Solid Code' by Steve Macguire
and it really works, in my experience it saves a lot of testing time
by not requiring so many tests to be written, since many times you
can spot errors in the code execution while stepping through even
though a particular test may not trigger the problem.  Anyway, the
proper tool for this is a debugger which shows you your program state
with the minimum of interaction, so for example xvdb will show you
all locals in each function automatically and display the current
source file.

So this is all vapor ware at the moment.  Current plans are:

Features
--------

* GUI will be single app window with multiple windows inside, individually
  hey can be moved, sized, iconized within the app window.  So somewhat MDI.
  Future maybe we can support pulling sub-windows out or the multiwindow mode.

* Will remember display format per type across functions.

* Considering a 'this' window.

* Considering 'panels'

* Considering user defined display functions.  External functions via DLL, or
  for classes a method of fixed name, eg, XvdbDisplay.  Function would print
  into a char buffer, an arg passed in would be the level of detail.

* Remember unique command lines (per stack frame? why not)

* Promote command lines to command menu, ie macros

Dev Plan
--------

- [ ] GUI
	- [ ]   The big window
	- [ ]   The little window
	      - [ ]     It can be moved and resized.  Nice!
	      - [ ]     It can be minimized.  Whew!
	- [ ]   It has text
	- [ ]   Clicky clicky gives me a line+col location
	- [ ]   Pop up menu
	- [ ]   A command line
	- [ ]   Mouse warping
	- [ ]   Dump to file

Phase 1: talk to gdb via pipe

- [ ] Echo gdb output to term for debug
- [ ] Connect command line
- [ ] Source window
	- [ ]   Click for breakpoint
- [ ] Stack window
- [ ] Command window
	- [ ]   Next/Step
	- [ ]   Restart
	- [ ]   Continue
	- [ ]   Return
- [ ] Locals window
	- [ ]   Display locals
	- [ ]   Identify types
	- [ ]   Format registry
	- [ ]   Formats
		- [ ]     Numeric
		- [ ]     String
		- [ ]     Struct
		- [ ]     Array
- [ ] Globals window
- [ ] Memory window
	- [ ]   Display in hex + ascii format (other encodings? wide chars?)
	- [ ]   Edit memory

