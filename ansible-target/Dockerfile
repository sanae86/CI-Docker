FROM sanae86/ubunutu-ssh-server
MAINTAINER sanae "https://github.com/sanae86"


# create user - ansible - for ssh access and enable sudo operations
RUN apt-get update && \
	apt-get -y install sudo && \
	groupadd -r ansible && \
    useradd -rmg ansible ansible && \
    echo 'ansible:ansible' |chpasswd && \
    echo 'ansible ALL=(ALL) NOPASSWD: ALL' >> /etc/sudoers && \
    ln /usr/bin/python3 /usr/bin/python  && \
    apt-get clean && \
	rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* 
RUN su - ansible -c "mkdir ~/.ssh"