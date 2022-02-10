Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-18.04"
  config.vm.synced_folder ".", "/vagrant", disabled: true
  config.vm.network "forwarded_port", guest: 80, host: 8080

  config.vm.define "ss-devops-2" do |node|
    node.vm.hostname = "ss-devops-2.local"
    node.vm.provision "ansible" do |ansible|
      ansible.playbook = "ss_devops_2.yml"
    end
  end

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
    vb.cpus = "1"
  end

end
