# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "precise64"
  config.vm.box_url = "http://files.vagrantup.com/precise64.box"

  config.vm.hostname = "jenkins"
  config.vm.network :forwarded_port, guest: 8080, host: 8080
  config.vm.network :private_network, ip: "10.0.0.100"

  config.vm.define "jenkins" do |jenkins|
  end

  config.vm.provider "virtualbox" do |vb|
    vb.name = "jenkins"
    vb.memory = 2048
    vb.cpus = 2
    #vb.gui = true
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "recepies/development.yml"
  end
end
