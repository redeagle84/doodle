* git clone https://github.com/docker/doodle.git

* Mac users:  
    * cd doodle/cheers2019 &&  
    * docker build -t redeagle84/cheers2019 .

* Windows users (use PowerShell):  
    * cd doodle\cheers2019 ;  
    * docker build -t redeagle84/cheers2019 .

* docker run -it --rm redeagle84/cheers2019



* Mac users:  
    * docker login &&
    * docker push redeagle84/cheers2019

* Windows users (use PowerShell):  
    * docker login ;
    * docker push redeagle84/cheers2019

<hr>

>> THE POWERSHELL BREAK MANY OF COMMANDS BELOW, USE CMD IF ON WINDOWS

	cd .\myFolder
	docker rmi -f ImageNameOrHashToRemove	
	docker rm -f ContainerNameOrHashToRemove
	docker images
	docker pull debian
	docker images
	docker ps -a
	docker run -v %CD%\:/mappedToHost --name CntDebGitA -it debian 
		apt-get update
		apt-get upgrade
		apt-get install git
		git --version
		cd /mappedToHost		
		cat << EOF > ./Dockerfile
			FROM debian
			RUN apt-get update && apt-get upgrade -y && apt-get install -y git
		EOF		
		exit 
	dir /B
	docker build -t builtfromdockfile:v1 .
		# SECURITY WARNING: You are building a Docker image from Windows against a non-Windows Docker host. 
		# All files and directories added to build context will have '-rwxr-xr-x' permissions. 
		# It is recommended to double check and reset permissions for sensitive files and directories.
	cd ..
	docker start CntDebGitA
	docker attach CntDebGitA
		git --version
		exit 	
	docker ps -a
	docker images
	docker commit CntDebGitA img-deb-git-b
	docker images
	docker ps -a
	docker run --name CntDebGitB -it img-deb-git-b 
		git --version
		exit 	
	docker ps -a
	docker images
	docker export --output="./CntDebGitB.tar" d0b250e9e3a6 
	docker import ./CntDebGitB.tar img-deb-git-c
	docker run --name CntDebGitC -it img-deb-git-c bash 
		git --version
		exit 	
	docker images
	docker save img-deb-git-c > /tmp/image.tar
	docker save -o ./ImgDebGitC.tar img-deb-git-c
	docker ps -a
	docker images	
	docker load --input ./ImgDebGitC.tar
