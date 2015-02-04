# -*- mode: ruby -*-
# vi: set ft=ruby :

base_box = "ubuntu/trusty64"

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.define("postgresql") do |pg|
    pg.vm.box = base_box
    pg.ssh.forward_agent = true
    # config.vm.network "forwarded_port", guest: 80, host: 8080
    pg.vm.network "private_network", ip: "192.168.33.10"
    pg.vm.provision "shell", path: "scripts/postgresql/install.sh"
    pg.vm.provision "shell", path: "scripts/postgresql/install-extensions.sh", privileged: false
  end
end
