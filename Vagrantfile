# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
    config.vm.box = "geerlingguy/centos7"
    config.vm.hostname = "app.dev"
    config.vm.synced_folder ".", "/srv/salt/", :nfs => true
    config.vm.network "private_network", ip: "10.1.2.10"
    config.vm.provision :salt do |salt|
      salt.masterless = true
      salt.minion_config = "components/saltstack/etc/minion"
      salt.run_highstate = true
    end
  end
