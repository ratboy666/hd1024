# hd1024
Altair-Duino 5MB HD with 1024 directory entries

The "Altair-Duino" has a hard disk simulation that uses a hard disk
from Mike Douglas: https://deramp.com/downloads/altair/software/hard_disk/CPM/
The problem with the hard disk image there (HDCPM22v16-48K.DSK) is that it
nly supports a very limited (256) number of directory entries. The image here
supports 1024 directory entries.

Altair Duino page is: https://adwaterandstir.com/ This is a very nice kit
Altair 8800 (blinking lights, speed, etc.). It can simulate floppy and
hard disk. This project just patches the hard disk bios to support
more directory entries -- sorry, no source, I "hot patched" this.

In Mike Douglas' version of MOVCPMH.COM (everything in hex):

2583 - OPTIONS

  10 enable interrupts

  01 execute command on cold start

  02 execute command on warm start

2584 - default iobyte

2530 - dph for hard disk

  2537 -ff  03 ff 00 - allow 1024 directory entries

