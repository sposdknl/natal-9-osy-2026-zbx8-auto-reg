IMAGE_NAME = "bento/debian-13"

Vagrant.configure("2") do |config|
    config.ssh.insert_key = false

    config.vm.provider "virtualbox" do |v|
        v.memory = 4096
        v.cpus = 4
    end

    config.vm.define "debian" do |debian|
        debian.vm.box = IMAGE_NAME
        debian.vm.network "forwarded_port", guest: 22, host: 2206, host_ip: "127.0.0.1"
        debian.vm.hostname = "debian13"
        debian.vm.provision "shell", path:"zabbix-agent-install.sh" 
        debian.vm.provision "shell", path:"zabbix-agent-conf.sh" 
    end

end
