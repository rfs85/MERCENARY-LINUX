# MERCENARY-LINUX

Link for Download: https://sourceforge.net/projects/mercenary-linux/files/VmwareWorkstation11/Mercenary.tar.gz/download

SHA1:d6c4f6bcfe11dc2238427587b7b24ad2baa57029 | 
MD5:dcb26a177f233ace22e947a0a2f5fcbc

MERCENARY Linux Distro is Built specifically for Cyber Hunt Team Operators
# DEFAULT CREDENTIALS:
USERNAME: mercenary                                                                                                    PASSWORD: mercenary

# OVERVIEW
The MERCENARY Linux Distro is Built specifically for Cyber Hunt Team Operators. This is the first iteration of this distro, with several tools, including Mercenary Hunt Framework being added with the next release (04/2016). This Distro contains many of the most well known and open-source respected malware analysis tools all conveniently installed on one system. Some of the tools included are: mercenary hunt framework**soon (MHF), SIFT, wmic-exe, radare2, viper, pescanner, jsdetox, volatility, maltrieve, rekall, mastiff, v8, crits, bro, netsniff-ng, wireshark, chopshop & Much More. Many of these run within prebuilt dockerized containers. This distro is a premium toolkit for any network, system, or malware analysis expert!

# DOCKERS...

# Radare2
Run the following command: 
sudo docker run --rm -it -v /your/working/directory:/home/nonroot/workdir remnux/radare2 bash  
Then run rd2 or other Radare2 commands inside the container.   This Dockerfile is based on the instructions documented in the official Radare2 Dockerfile file.

# Pescanner
This Dockerfile represents a Docker image that encapsulates the pescanner tool created by Michael Ligh for performing static analysis of suspicious Windows PE files. The image is using the version of the tool that was modified by Glenn P. Edwards Jr. to introduce imphash support. The original version was distributed with the book Malware Analyst Cookbook. The Dockerfile was contributed to the REMnux collection by Adric Net. The Docker image built by this file includes: Ubuntu base,apt in python-magic, yara, python-yara, pip, clamav (all in multiverse) capabilities.yara, userdb.txt, pescanner.py, pefile 
pydams via libdasm (needed for imphash calculations) To run this image after installing Docker, use a command like this, replacing ~/workdir with the path to your working directory on the underlying host:
sudo docker run --rm -it -v /your/working/directory:/home/nonroot/workdir remnux/pescanner bash
This will launch the bash shell in the container, at which point you can run the "pescanner" command to scan the desired file. 

# Mastiff
This Docker image encapsulates the MASTIFF static analysis framework by The MASTIFF Project at KoreLogic.
To run this image after installing Docker, use a command like this, replacing "~/mastiff-workdir" with the path to the location of your MASTIFFF directory:
sudo docker run --rm -it -v /your/working/directory:/home/nonroot/workdir remnux/mastiff
then run mas.py in the container with the desired parameters.

# Jsdetox
This Dockerfile represents a Docker image that encapsulates the JSDetox malware analysis tool for JavaScript deobfuscation by @sven_t. To run JSDetox after installing Docker, use the following command:
sudo docker run --rm -p 3000:3000 remnux/jsdetox
Then, connect to http://localhost:3000 using your web browser.
To stop JSDetox, use "sudo docker ps -l" to obtain the container ID, then use the "sudo docker stop *container-id*" and wait about a minute.

# CRITs
This Docker image encapsulates the Collaborative Research Into Threats (CRITs) malware and threat repository by The MITRE Corporation.
To run this image after installing Docker, use a command like this, replacing “~/crits-data" with the path to the location for storing CRITs data, indefinitely:
sudo docker run --rm -it -v /your/working/directory:/home/nonroot/workdir -p 8443:8443 remnux/crits 
After launching the container, give it some time to start up. Then, when you see the info about temporary logon credentials, connect to https://localhost:8443 using your web browser.

# VIPER
This Dockerfile represents a Docker image that encapsulates the Viper binary analysis and management framework by Claudio Guarnieri (@botherder).
To run this image after installing Docker, use a command like this to launch the Viper web interface, replacing "~/viper-workdir" with the path to the location of your Viper Viper data directory:
sudo docker run --rm -p 9090:9090 -v /your/working/directory:/home/nonroot/workdir remnux/viper
If you want to launch the Viper command-line tool instead of its web interface, run Bash in the container like this, then issue the desired ./viper.py command:
sudo docker run --rm -it -v /your/working/directory:/home/nonroot/workdir remnux/viper bash

# MALTRIEVE
This Docker image encapsulates the Maltrieve tool created by Kyle Maxwell (@krmaxwell) for retrieving malware samples.
This Dockerfile is based heavily on the one from Kyle's Maltrieve repository, which is maintained by Michael Boman.
To run this image after installing Docker, use a command like this,/home/cpt91/RemnuxWorkDir
This is where the downloaded malware samples will be deposited.
sudo docker run --rm -it -v /your/working/directory:/archive remnux/maltrieve 
This will launch Maltrieve without any parameters, directing the tool to retrieve
malware samples and save them to the ~/RemnuxWorkDir directory.
If you wish to specify command-line parameters to Maltrieve, then launch it like this:
sudo docker run --rm -it -v /your/working/directory:/archive remnux/maltrieve bash
This will launch the bash shell in the container, at which point you can run the command
"maltrieve", specifying optional command-line parameters if you wish.


# V8
This Docker image encapsulates the command-line tool "d8" from Google's V8 JavaScript Engine.
To run this image after installing Docker, use a command like this, replacing "/your/working/directory" with the path to the location of the files you'd like to examine within the container:
sudo docker run --rm -it -v /your/working/directory:/home/nonroot/files remnux/v8 bash
Once you've activated the container using the command above, you can run the command-line version of V8 by typing the "d8" command (e.g., "d8 -f /your/working/directory/file.js"). To use the pre-defined JavaScript object definitions, supply a command like "d8 -f ~/objects.js /your/working/directory/file.js".

# REKALL
This Dockerfile represents a Docker image that encapsulates the Rekall Memory Forensic Framework. To run this image after installing Docker, use a command like this:
sudo docker run --rm -it -v /your/working/directory:/home/nonroot/files remnux/rekall bash
then run "rekall" in the container with the desired parameters.
Before running the command above, create the "files" directory on your host and make it world-accessible (e.g., "chmod a+xwr /your/working/directory").
To use Rekall's web console, invoke the container with the -p parameter to give your host access to the container's TCP port 8000 like this:
sudo docker run --rm -it -p 8000:8000 -v /your/working/directory:/home/nonroot/files remnux/rekall
Then connect to http://localhost:8000 using a web browser from your host.

# VOLATILITY
This Dockerfile represents a Docker image that encapsulates the Volatility Framework for memory forensics by the Volatility Foundation. To run this image after installing Docker, use a command like this:
sudo docker run --rm -it -v /your/working/directory/memdumps:/home/nonroot/memdumps remnux/volatility bash
then run vol.py in the container with the desired parameters.
Before running the command above, create the "memdumps" directory on your host and make it world-accessible (e.g., chmod a+xwr /your/working/directory/memdumps).
