Vagrant.configure("2") do |config|
  config.vm.provision "shell", path: "bootstrap.sh"

  config.vm.define "server1" do |server1|
    server1.vm.box = "ubuntu/bionic64"
    server1.vm.network "public_network", ip: "192.168.0.101"
    server1.vm.provider "virtualbox" do |vb|
      vb.memory = "1024" 
    end
     server1.vm.synced_folder "./data", "/home/vagrant/data"

    # shell script to install Ansible
    server1.vm.provision "shell", inline: <<-SHELL
      #!/bin/bash
      apt-get update
      apt-get install -y software-properties-common
      apt-add-repository --yes --update ppa:ansible/ansible
      apt-get install -y ansible
    SHELL
  end

  config.vm.define "server2" do |server2|
    server2.vm.box = "ubuntu/bionic64"
    server2.vm.network "public_network", ip: "192.168.0.102"
    server2.vm.provider "virtualbox" do |vb|
      vb.memory = "1024" 
    end
  end

  config.vm.define "server3" do |server3|
    server3.vm.box = "ubuntu/bionic64"
    server3.vm.network "public_network", ip: "192.168.0.103"
    server3.vm.provider "virtualbox" do |vb|
      vb.memory = "1024" 
    end
  end

  config.vm.define "server4" do |server4|
    server4.vm.box = "ubuntu/bionic64"
    server4.vm.network "public_network", ip: "192.168.0.104"
    server4.vm.provider "virtualbox" do |vb|
      vb.memory = "1024" 
    end
  end
end
