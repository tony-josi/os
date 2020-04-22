## BIOS

When the computer boots, the BIOS doesn't know how to load the OS, so it delegates that task to the boot sector. Thus, the boot sector must be placed in a known, standard location. That location is the first sector of the disk (cylinder 0, head 0, sector 0) and it takes 512 bytes.

To make sure that the "disk is bootable", the BIOS checks that bytes 511 and 512 of the alleged boot sector are bytes 0xAA55.

To compile: `nasm -f bin boot_sect_simple.asm -o boot_sect_simple.bin`

Run: qemu-system-x86_64 boot_sect_simple.bin