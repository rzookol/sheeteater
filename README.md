Short:        Power Macintosh emulator for MorphOS
Uploader:     Michal Zukowski
Author:       Michal Zukowski, macemu and SheepShaver contributors
Type:         misc/emu
Version:      0.8
Architecture: ppc-morphos
Requires:     MorphOS, PowerPC with enough RAM, a compatible Mac OS ROM

SheetEater 0.8
===============

SheetEater is a Power Macintosh emulator prepared especially for MorphOS.
It lets you run classic PowerPC versions of Mac OS in a normal MorphOS
window or on a separate screen.

The program is based on the open-source macemu and SheepShaver projects,
with a MorphOS-native interface and a PowerPC-focused execution core.

Main features
-------------

* MorphOS MUI preferences window.
* Window and fullscreen operation.
* Resizable CGXVideo overlay with hardware scaling, when supported.
* Intuition ARGB hardware mouse cursor.
* Software cursor fallback for overlay mode.
* AltiVec-assisted video conversion on compatible processors.
* QuickDraw acceleration for common drawing operations.
* 64 MB JIT code cache and PowerPC MiniJIT acceleration.
* AHI sound output.
* Ethernet, serial, CD-ROM and disk-image support.
* A MorphOS drawer can be mounted as a Mac volume.
* Quiet build and quiet runtime mode for normal everyday use.
* Localized MUI interface through sheeteater.catalog.

Requirements
------------

You need a suitable Power Macintosh ROM and a legal Mac OS installation.
The ROM and system files are not included in this archive.

A G4 or G5 processor is recommended for the AltiVec video path. SheetEater
also runs without AltiVec and automatically selects the safe converter.
The CGXVideo overlay depends on the graphics driver and screen mode. If it
cannot be created, SheetEater falls back to the normal display method and
prints the reason in the log.

Installation
------------

Copy the complete SheetEater drawer to any location and start SheetEater.
Keep the program, its icon, gfx drawer and locale drawer together.

Open Preferences before the first start and select:

* a compatible ROM file;
* a bootable Mac disk image;
* the desired memory size;
* window or fullscreen display;
* optional CGXVideo RGB16PC overlay;
* optional Intuition ARGB hardware cursor.

Preferences are saved as:

  ENV:SheetEater_prefs
  ENVARC:SheetEater_prefs

NVRAM is saved as:

  ENV:SheetEater_XPRAM
  ENVARC:SheetEater_XPRAM



Display notes
-------------

The CGXVideo overlay keeps the emulated Mac framebuffer at its original
resolution. Resizing the window changes only the destination rectangle;
CGXVideo performs the scaling. This avoids expensive software resampling.

The hardware cursor option uses the MorphOS Intuition pointer class. If it
is disabled or unavailable, SheetEater draws the classic Mac cursor into
the overlay correctly.

Quiet operation
---------------

Enable Quiet mode in the GUI to hide normal diagnostic reports. For the
lowest profiling overhead, build the dedicated quiet executable with:


Limitations
-----------

Compatibility depends on the ROM, Mac OS version, extensions and software.
Some applications may require different memory, graphics or networking
settings. Hardware overlay availability depends on the installed MorphOS
graphics driver.

Credits and licence
-------------------

MorphOS version 0.8 and current port work: Michal Zukowski.
Based on macemu, SheepShaver and earlier MorphOS/Basilisk II work by their
respective contributors.

Distributed under the GNU General Public License. See the included source
and licence files for details.
