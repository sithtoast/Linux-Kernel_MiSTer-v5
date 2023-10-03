## Steps for success on https://github.com/MOnSieurFPGA:

+ Install zImage_dtb (in /boot and in /boot/linux for MrMister), reboot
+ Stop MiSTer service with sudo systemctl stop MiSTer
+ Clone repo to MiSTer
+ Browse to directory, run make modules
+ Once complete make modules_install
+ Reboot and enjoy your hardware and if installed, tailscale!

## If you are a bad enough dude to compile your own kernel:
 + export ARCH=arm
 + sudo systemctl stop MiSTer
 This is where you'll need to add any new device drivers since the last update
 + make menuconfig
 + make -j3 zImage
 + make socfpga_cyclone5_de10_nano.dtb
 + cat arch/arm/boot/zImage arch/arm/boot/dts/socfpga_cyclone5_de10_nano.dtb > zImage_dtb
 + sudo cp zImage_dtb /boot/zImage_dtb
 + sudo cp zImage_dtb /boot/linux/zImage_dtb
