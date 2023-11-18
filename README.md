# kali-boot-animation-change
Plymouth theme

###################################################################################################################
First step install plymouth

then go /usr/local/bin
and create file plymouth-prev 
and paste
#!/bin/bash
 
check_root () {
  if [ ! $(id -u) -eq 0 ]; then
    echo "Please run as root"
    exit
  fi
}
check_root
DURATION=$1
if [ $# -ne 1 ]; 
then
  DURATION=5
fi
plymouthd; plymouth --show-splash
for ((i=0; i<$DURATION; i++)); do
  plymouth --update=duration$i;
  sleep 1;
done;
plymouth --quit

#########################

after that
copy theme to usr/share/plymouth/theme
command 
plymouth-set-default-theme --help
plymouth-set-default-theme -l
plymouth-set-default-theme
plymouth-set-default-theme -R themename
