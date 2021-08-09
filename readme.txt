SCSI2SD, The SCSI Hard Drive Emulator for retro computing.

SCSI2SD is a modern, solid-state replacement for failed or failing single ended SCSI hard drives. It allows the use of vintage computer hardware long after their mechanical drives fail. The use of SD memory cards solves the problem of transferring data between the vintage computer and a modern PC.

Features

    In-built active terminator.
    Emulates up to 4 SCSI devices
    Supports sector sizes from 64 bytes to 8192 bytes
    Firmware updatable over USB
    Highly configurable over USB
        Selectable SCSI ID
        Selectable parity support
        Enable/disable Unit Attention Condition
        Artificial limits on the SCSI disk size (eg. limit size to 4G to avoid OS bugs) 
        Sector size (can also be set via the SCSI MODE SELECT command, as sent by SCSI format utilities).

Technical Specifications

SCSI Interface
	SCSI-2 Narrow 8-bit 50-pin connector. Supports asynchronous transfers only.
Micro SD Card Interface
	Standard microSDSC (1GB maximum size)
	microSDHC, microSDXC (200+ gigabytes tested)
	Communication is via the SPI protocol at 25MHz.
USB Interface (firmware updates and config)
	USB 2.0 micro-B
Power
	5V via standard floppy-style "Berg" connector
	USB or self-powered using the SCSI host termination power. (All V5.x variants, V5.0, V5.1, V5.2, V5.5)

Performance

As currently implemented:

Transfer size:    512        2048        8192        65536
-------------------------------------------------------
read:			2MB/s     2.1MB/s     2.5MB/s     2.6MB/s
write:			125kB/s   441kB/s     1.5MB/s     2.3MB/s
-------------------------------------------------------


Tested with a 16GB class 10 SD card, via the commands:

 # WRITE TEST
 sudo dd bs=${SIZE} count=100 if=/dev/zero of=/dev/sdX oflag=dsync

 # READ TEST
 sudo dd bs=${SIZE} count=100 if=/dev/sdX of=/dev/null
