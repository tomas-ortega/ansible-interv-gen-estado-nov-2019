Vagrant.configure("2") do |ci_machine|
	ci_machine.vm.box = "ubuntu/bionic64"
	ci_machine.vm.box_version = "20191118.0.0"
	ci_machine.vm.hostname = "ci-machine"
	
	ci_machine.vm.provider "virtualbox" do |vb|
		vb.gui = true
		vb.name = "ci-machine"
		vb.memory = "2048"
		vb.cpus = 2

		vb.customize ["modifyvm", :id, "--clipboard", "bidirectional"]
	end
	
	ci_machine.vm.provision "ansible_local" do |ansible|
		ansible.compatibility_mode = "2.0"
		ansible.playbook = "playbook-docker-install.yml"
	end
end







