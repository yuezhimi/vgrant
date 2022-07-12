# -*- mode: ruby -*-
# vi: set ft=ruby :

host_list = [
  {
    :name => "host1",
    :box => "centos/7"
  }
]

Vagrant.configure("2") do |config|

  config.vm.provider "hypery" do |v|
    config.vm.synced_folder ".","/vagrant",type: "smb"
  end
  config.vm.provider "virtualbox" do |_, override|
    config.vm.synced_folder ".","/vagrant",type: "virtualbox"
  end

  host_list.each do |item|
    config.vm.defline item[:name] do |host|
      host.vm.box = item[:box]
    end
  end

end