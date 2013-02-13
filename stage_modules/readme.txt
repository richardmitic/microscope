
Notes on LabView for Prior.

Included is a set of LabView Vis which expose
some of the functionality of the Prior DLL and
Active X controls. A main Vi, named TopLevel.vi,
which demonstrates the use of the sub-Vis is
also included. This is the Vi to run from
LabView.

In general, the vis use the methods and
properties of the Active X controls in the
Prior DLL. These Vis hide some of the details
of Active X programming and provide the power
of Prior.DLL in a way which will be familliar
to the casual LabView programmer.
Consult the Proir DLL help file
for complete documentation of all the
available commands and features.

Using the Vis-

IScanOpen.vi must be called first to initialize
and connect to Prior.DLL. IScanOpen.vi also makes
available all the methods and properties of the
IScan class. In a similar way, IFilterOpen.vi,
IStageOpen.vi and IZOpen.vi are called to enable
these methods. At the end of the program, the
various close vis are called close up the system
and free resources. Note that IscanClose.vi must
be called last, as it shuts down the connection
to Prior.DLL

Direct Active X Programming in LabView -
LabView provides support for using Active X controls
directly. Below is a step by step procedure for
linking up to the Prior.DLL and accessing the
methods directly, for those programmers who wish
to do so.

1) Starting on a front panel, select and place an
Automation Refnum, from the Refnum palette.

2) Right click on the refnum, choose
Select ActiveX Class. A dialog opens up allowing
Library and Object selection.
For the Type Library select
Prior 1.34 Type Library Version 1.22 (not the Active X
library displayed just below).
Check the box for Show Creatable Objects Only.
For this example, select Scan(Prior.Scan.1)
On the front panel the Refnum is now labeled
PRIORLib.IScan.

3) Go to the block diagram.
Select an Automation Open icon and place it
on the block diagram.
These icons are located under the
Communication->Active X palette.
Wire the Refnum to the Open icon.

4) Select an Invoke Node from the palette, and
place it on the block diagram. Wire it to the
Open Icon. The Invoke Node label changes to
IScan. Click on Method, and all methods become
available. Select Connect as this one needs to
be called first in any system. Connect requires
an input parameter. Use 1 if your system uses a
controller on COM1, use 0 if you have a PCI board.

You can now use Invoke Nodes and Property Nodes
freely as your software system requires.
Note that most property nodes can be set to
Read or Write, just like local variables.

