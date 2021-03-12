## ME4 command line
```
# create disk group or pool
show disks
create vdisk level raid5 disks 0.0-4 VD1
show vdisks


# create initiator
show initiators
set initiator id 21000024ff447e66 nickname a profile standard
set initiator id 21000024ff447eb8 nickname b profile standard

# create host
create host initiators 21000024ff447e66 r610a
create host initiators 21000024ff447eb8 r610b

create host-group hosts r610a,r610b r610

# create volume and mapping
create volume vol1 pool VD1 size 10GB access rw lun 0
create volume vol2 pool VD1 size 1TB access rw lun 1

map volume
map volume vol1,vol2 initiator r610.*.* lun 2
```
