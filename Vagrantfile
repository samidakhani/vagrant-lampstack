# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|

  #(1) Operating System
  config.vm.box = "ubuntu/trusty64"
  config.vm.box_check_update = false

  #(2) Provider
  config.vm.provider "virtualbox" do |vb|
    vb.memory = 2048
    vb.cpus = 2
  end

  #(3) Network
  config.vm.network "private_network", guest: 80, host: 8080, ip: "192.168.33.10"

  # (4) Sync Folder
  config.vm.synced_folder "./data", "/var/www/html",:mount_options => ["dmode=777", "fmode=666"] 

  # (5) Provision
  # config.vm.provision "shell", inline: <<-SHELL
  #    apt-get update
  #    apt-get install -y apache2
  # SHELL

  config.vm.provision "shell", path: "bootstrap.sh"
end
