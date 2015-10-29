# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"

  config.vm.network "private_network", ip: "192.168.33.10"
  config.vm.hostname = "node-webcrawler.dev"

  config.vm.synced_folder "src/", "/var/www/node-webcrawler.dev", create: true, type: "rsync", mount_options: ['dmode=777','fmode=755']

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provisioning/setup.yml"
    ansible.limit = "all"
  end

end
