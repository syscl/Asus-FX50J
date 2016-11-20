OS X/macOS on Asus FX50J(X/K Series)
====================================


This project targets at giving the relatively complete functional OS X for both Asus FX50JX and FX50JK. Before you start, there's a brief introduction of how to finish powering up OS X on your laptop:

1. Create a vanilla installation disk(removable disk).
2. Install Clover with UEFI only and UEFI64Drivers to the installation disk just created. 
3. Replace the origin Clover folder with the one under my Git/Asus-FX50J/CLOVER.
4. Install OS X.
5. Once you finish installation of OS X, you can do the following steps to finish the post installation of OS X.

How to use deploy.sh?
----------------

Download the latest version installation package/directory by entering the following command in a terminal window:

```sh
git clone https://github.com/syscl/Asus-FX50J
```
This will download the whole installation directory to your current directory(./) and the next step is to change the permissions of the file (add +x) so that it can be run.


```sh
chmod +x ./Asus-FX50J/deploy.sh
```


Run the script in a terminal windows by(Note: You should dump the ACPI tables by pressing F4/Fn+F4 under Clover first and then execute the following command lines):

```sh
cd Asus-FX50J
./deploy.sh
```

Reboot your OS X to see the change. If you have any problem about the script, try to run deploy in DEBUG mode by 
```sh
./deploy.sh -d
```

Note: For two finger scrolling you need to change the speed of the Scrolling once to get it work and also have to enable them in Trackpad preferences.

Change Log
----------------
2016-11-20

- Correct internal display connector type from LVDS <02 00 00 00> to eDP <00 04 00 00> credit syscl

2016-9-19

- Fixed a bug that will cause Realtek usb wifi fail to turn off, then
causing the sleep panic.
- Added SSDT-rmne.aml for USB Wi-Fi to access AppStore.
- Updated related kexts to latest version.
- Updated to Clover r3751.
- Added umnt pairing with mnt to unmount disk easily.

2016-6-28

- Added i7-4710HQ, i7-4720HQ for FX50J(X/K).
- Removed redundant SSDT-rnme.aml.
- More improvements on FX50J(X/K).
- First commit.
