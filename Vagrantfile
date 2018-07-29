# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure('2') do |config|
MYNAME="rails-dev-box"
  config.vm.box      = 'ubuntu/bionic64' # 18.04
  config.vm.hostname = MYNAME

  config.vm.network :forwarded_port, guest: 3000, host: 3000

  config.vm.provider "virtualbox" do |v|
	      v.name = MYNAME
	        end

    config.vm.define MYNAME do |t|
	      end

      config.vm.provider :virtualbox do |vb|
	          vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
		    end

  config.vm.provision :shell, path: 'bootstrap.sh', keep_color: true

  config.vm.provider 'virtualbox' do |v|
    v.memory = ENV.fetch('RAILS_DEV_BOX_RAM', 2048).to_i
    v.cpus   = ENV.fetch('RAILS_DEV_BOX_CPUS', 2).to_i
  end
end
