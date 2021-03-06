# Lab 100 -  Installation of Golden Gate for BigData

![](images/100/image100_0.png)

## Before You Begin

### Introduction
Installation of Golden Gate for Big Data simplifies your data integration by working with on-premises and cloud data source/targets and accepting data in any shape or format. This lab will guide you on how to Install Goldengate for BigData.

### Objectives
- Installation of Golden Gate for Big Data 12.3.2.1

### Time to Complete
Approximately 30 minutes

### What Do You Need?
Your will need:
- Golden Gate for Big Data 12.3.2.1
- Java jdk1.8

### STEP 1: Access Ravello Image or Cloud Mchine via putty

In this step you will use putty client to connect to Oracle Cloud Compte environment, to get started with the installation of Oracle GoldenGate Big Data.

1. Connect to Oracle Compute instance with public ip and private key

![](images/100/image100_1.png)

2. Load the private key given to you by the instructor in the putty 

![](images/100/image100_2.png)

3. Enter the username as opc and you would be logged in

![](images/100/image100_3.png)


### STEP 2: Verify and Prepare the Instance for GoldenGate For BigData Installation

1. Create a Directory to install the Goldengate for bigdata. Here we have created /u01/app/ggbd_home1

```
[opc@gg4bd-target01 ~]$ sudo su - oracle
Last login: Fri May  3 09:30:10 GMT 2019 on pts/0
[oracle@gg4bd-target01 ~]$ mkdir /u01/app/ggbd_home1
```

2. Sudo into the oracle user and Verify the environment variables as java jdk would be already installed and environment variables should be set already. Below are the sample environment variables.

```
export GGBD_HOME=/u01/app/ggbd_home1
export JAVA_HOME=/u01/app/jdk1.8.0_211
export JRE_HOME=/u01/app/jdk1.8.0_211/jre
export PATH=/usr/sbin:${JAVA_HOME}/bin:${JRE_HOME}/bin:${PATH}:.
export LD_LIBRARY_PATH=$JAVA_HOME/jre/lib/amd64/server:$JAVA_HOME/lib
export CLASSPATH=$JAVA_HOME/lib:/u01/app/ggbd_home1/ggjava
```

3. From the terminal screen change to the Downloads directory and You will fine the Goldengate for bigdata software there.

```
[oracle@gg4bd-target01 ~]$ cd ~/Downloads/
[oracle@gg4bd-target01 Downloads]$ ls -lrt
total 731840
-rwxr-xr-x. 1 oracle oracle  95212174 May  3 09:28 OGG_BigData_Linux_x64_12.3.2.1.1.zip
[oracle@gg4bd-target01 Downloads]$
```

4. Copy this Goldengate for Bigdata software into the directory you created in step 1 for installation.

```
[oracle@gg4bd-target01 Downloads]$ cd ~/Downloads/
[oracle@gg4bd-target01 Downloads]$ ls -lrt
total 92984
-rwxr-xr-x. 1 oracle oracle  95212174 May  3 09:28 OGG_BigData_Linux_x64_12.3.2.1.1.zip
[oracle@gg4bd-target01 Downloads]$ cp OGG_BigData_Linux_x64_12.3.2.1.1.zip /u01/app/ggbd_home1/
```

### STEP 3: Install Goldengate For Bigdata and start the manager process

1. Now got the the directory where you copied the software file and unzip the Goldengate for Bigdata

![](images/100/image100_4.png)

2. Once you Unzip the file , you will get a tar file. Untar the file OGG_BigData_Linux_x64_12.3.2.1.1.tar

![](images/100/image100_5.png)

3. After this Log into GG Commandline interface with ./ggsci. And use the command create subdirs 

![](images/100/image100_6.png)

4. Now we need to give a port to Goldengate manager process and start it. use edir param mgr and add a port as show in the below picture and start the manager process.

```
PORT 7100
ACCESSRULE, PROG *, IPADDR *, ALLOW
```
![](images/100/image100_7.png)


You have completed lab 100! Great Job!