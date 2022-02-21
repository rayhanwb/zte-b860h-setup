# zte-b860h-setup
Setup untuk ZTE b860h

## Install Armbian
1. Download Image
2. Write image ke microsd (Rufus/Balena Etcher)
3. Buka microsd dan edit file:
    `BOOT/extlinux/extlinux.conf`
    ```txt
    LABEL Armbian
    LINUX /zImage
    INITRD /uInitrd

    # aml s9xxx
    FDT /dtb/amlogic/meson-gxl-s905x-p212.dtb
    APPEND root=LABEL=ROOTFS rootflags=data=writeback rw console=ttyAML0,115200n8 console=tty0 no_console_suspend consoleblank=0 fsck.fix=yes fsck.repair=yes net.ifnames=0
    ```
4. Rename file `u-boot-s905x-s912` menjadi `u-boot.ext`
