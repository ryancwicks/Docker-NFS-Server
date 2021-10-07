# Docker-NFS-Server

Instructions for setting up a NFS server using Docker. Originally from [here](https://sysadmins.co.za/setup-a-nfs-server-with-docker/).

## Setup

Setup a directory to share on your computer/in your WSL instance. 

```
mkdir /tmp/fileshare
```

## Running the container

To run the container:

```
SHARED_DIR=/tmp/fileshare docker-compose up 
```

Add -d if you want it run in the background.

## Connecting to the NFS mount

You can connect to the mount from a linux system by first installing the nfs-client

```
sudo apt install nfs-client
```

You can then mount the share with:

```
sudo mount -v -o vers=4,loud <server ip address>:/ <your local mount point>