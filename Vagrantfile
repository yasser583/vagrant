# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  
  config.vm.define "jdc" do |jdc|
    #jdc.vm.box = "geerlingguy/ubuntu1604"
    jnt.vm.box = "ubuntu/xenial64"
    jdc.vm.network :private_network, ip: "192.168.33.39"
    jdc.ssh.insert_key = false
    jdc.vm.hostname = "jenkins.docker"
    jdc.vm.provider :virtualbox do |v|
      v.name = "jenkins_docker"
      v.memory = 2048
      v.cpus = 4
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--ioapic", "on"]
    end
  end

  config.vm.define "jnt" do |jnt|
    #jnt.vm.box = "geerlingguy/ubuntu1604"
    jnt.vm.box = "ubuntu/xenial64"    
    jnt.vm.network :private_network, ip: "192.168.33.40"
    jnt.ssh.insert_key = false
    jnt.vm.hostname = "jenkins.native"
    jnt.vm.provider :virtualbox do |v|
      v.name = "jenkins_native"
      v.memory = 2048
      v.cpus = 4
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--ioapic", "on"]
    end
  end
end

  # Enable provisioning with Ansible.
  #config.vm.provision "ansible" do |ansible|
  #  ansible.playbook = "provisioning/main.yml"
  #end
