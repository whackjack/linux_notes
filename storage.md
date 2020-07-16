# Disk/storage commands


Check physical sector size of disk:

`lsblk -o NAME,PHY-SEC`

Check disk usage:

`df -h /dev/sd*`

Check file sizes:

`du -ha /foo`

Sort directories by size (top 5):

`du -a | sort -n -r | head -n 5`

## SMART commands

Short test:

`smartctl -t short /dev/sdX`

Long test:

`smartctl -t long /dev/sdX`

Conveyance test:

`smartctl -t conveyance /dev/sdX`

View test results:

`smartctl -A /dev/sdX`

## Hard drive bad block test (runs for a long time!)

512 or 4k sector size, destructive test

`badblocks -b 512 -c 65536 -ws /dev/sdX`

`badblocks -b 4096 -c 65536 -ws /dev/sdX`

* -b - block size
* -c - number of blocks to test at once
* -w - write test (4 passes) Destructive!
* -s - show progress

## Links to resources

Hard-drive burn-in testing: https://www.ixsystems.com/community/resources/hard-drive-burn-in-testing.92/
Bad blocks explanation: https://superuser.com/a/798883
