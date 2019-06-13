# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.
  config.ssh.forward_agent = true
  config.vm.box = "centos/7"

  config.vm.define "opl-nginx" do |machine|
    machine.vm.network "private_network", ip: "192.168.35.10"
    machine.vm.provision :shell, :inline => "sudo sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config; sudo systemctl restart sshd;", run: "always"
    machine.vm.provider "virtualbox" do |node|
        node.name = "opl-nginx"
        node.memory = 512
        node.cpus = 1
    end
   end
end
