# bunsenlabs-cb-upgrade

This script is not intended to be used as a fork to BunsenLabs and what 
they are doing. Instead it is intended to extend the function it was  
intended for. 

To upgrade a existing Crunchbang system to Debian 8 fixing the little things
that need to be done to get it to work properly and install all of BunsenLabs
window dressings, and modifications they have done in there release of GNU/Linux

I even copied this and modified it to my needs :D

This is a collection of files intended to install
an alpha version of BunsenLabs Linux
on a Crunchbang to upgrade to Jessie with BL.

It will use the BunsenLabs repositories on GitHub
to build .deb files, put them in a locally created repository
and install them from there.

The exact content of those files will vary with time,
as will the likelihood of building a viable system.

WARNING: THIS INSTALLER IS FOR TESTING PURPOSES ONLY.
No support will be provided on the forums
for any problems that may occur, though bug reports are welcome!

HOW TO USE

Boot into your Debian Cruncbang System. Go to your browser that you
already should be using then look over to your right then click download
zip.

log in and run these commands, as a normal user:
(A fresh copy of this bunsen-cb-upgrade (netinstall) package will be downloaded.)

unzip it to where ever you choose to. Then go to a tty using Ctrl + Alt + (F4 - F6)
then log in - navagate your way into where you put bunsenlabs-cb-upgrade-master directory.
then run  $./install-bl8 

or

wget https://github.com/userx-bw/bunsenlabs-cb-upgrade/archive/master.tar.gz 
 tar -xpf master.tar.gz
 cd bunsenlabs-cb-upgrade-master
 ./install-bl8
 

The installation process will start.
Follow any prompts that appear on the screen.

There is also a script: upgrade-bunsen-packages
which can be run to upgrade the BunsenLabs packages
without having to reinstall the system.

A folder called .bunsen-netinstall-logs will be added to your home folder.
(The file ~/.bunsen-netinstall-logs/install.log will contain
verbose information about the install process.)
This folder may safely be removed if the installation was successful,
and no issues arose subsequently.

A folder /backup on your root file system will hold backups of
system files replaced during the install.

The script itself has been separated off from the files holding
specific data about the installation. This is intended to make
customization easier. It should not be necessary to edit "install".
Even if the script is upgraded in the future, the same config files
should still work.

FILES IN THIS COLLECTION

README: this file
LICENSE: a copy of the GPL3 license
install: the installation script
bunsen-upgrade-pkgs: script to upgrade the BunsenLabs packages
copyright: GNU licence statement
greeting: message to user
pkgs-recs: packages to install with recommends
pkgs-norecs: packages to install without recommends
extra_repos: repository(ies) to add to /etc/apt/sources.list
sysfiles1: system files to copy in before installing packages (mainly apt-related)
sysfiles2: system files to copy in after installing packages
cbsysfiles1: systems files to copy in after installing packages
cbsysfiles2: system files to copy in after installing packages
preinstall_commands: commands to run before installing packages and files
postinstall_commands: commands to run after installing packages and files
github_install: commands to build .deb files and install them from a local repository
git2deb-bl: script to build .deb files from a git repository
config: sets some directory paths etc
bunsen-netinstall-logs: folder to copy into user's home directory
undo: an experimental script to attempt to return the system to the state it was in before running the install script
I have no idea if that will even work with this as once your Jessie you stay Jessie -- 

This is totally experimental - as this scrpit may or should still work as 
a NetInstall as well. It just adds a automount.plka that you may have to remove
if you have issues with automounting drives after using this for a net install. 

I have not personally tested this modded script with a netinstall, it still
may - should  work as such.  

DEBIAN NETINSTALL HINTS

Installing Debian Jessie by the netinstall CD is
similar to using the standard installer.

Two points to watch if you want to use
this netinstall script afterwards:

1) At the "Set up users and passwords" screen,
do NOT enter a password for root.
Type nothing and press "continue".
Do this again at "Re-enter password to verify".
Enter your own name and password as normal.
You will then be given 'sudo' permissions,
which will be needed in the script.

2) At the "software selection" stage DESELECT EVERYTHING
except "standard system utilities".
You will have a core system only, on which
the netinstall installer will add what is needed.
(Some software items will be marked with an asterisk, indicating that
they have been preselected.
Use the up/down arrows to move, and the spacebar to toggle selection.)

The netinstall download and links to documentation can be found here:
http://www.debian.org/CD/netinst/
