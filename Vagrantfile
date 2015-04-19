# -*- mode: ruby -*-
# vi: set ft=ruby :

#makecert -r -pe -n CN="tsubasus-vagrant" -sky exchange vagrant-azure.cer -sv vagrant-azure.pvk
#pvk2pfx -pvk vagrant-azure.pvk -spc vagrant-azure.cer -pfx vagrant-azure.pfx
#openssl pkcs12 -in vagrant-azure.pfx -out vagrant-azure.pem -nodes

VM_NAME = "tbkubuntu"
VM_USER_NAME = "azureuser"
VM_PASSWORD = "@zureDaisuki"

Vagrant.configure("2") do |config|
  config.vm.box = "azure"
  config.vm.box_url = "https://github.com/msopentech/vagrant-azure/raw/master/dummy.box"
  
  #config.vm.provision "shell", inline: $script
  #config.vm.provision "shell" do |s|
  #  s.inline = "ipconfig $1"
  #  s.args   = "all"
  #end
  
  #config.vm.synced_folder ".", "/vagrant", type: "rsync"
  
  config.ssh.username = VM_USER_NAME
  config.ssh.password = VM_PASSWORD
  
  config.vm.provider :azure do |azure|
      azure.mgmt_certificate = 'C:\\Users\\azureuser\\.azure\\vagrant-azure.pem'
      azure.mgmt_endpoint = 'https://management.core.windows.net'
      azure.subscription_id = 'd139531a-f704-485c-a74d-f4426b95f9f9'
      #azure.storage_acct_name = 'tbkvirtualmachinestorage'
      
      azure.vm_image = 'b39f27a8b8c64d52b05eac6a62ebad85__Ubuntu-14_10-amd64-server-20150416-en-us-30GB'
      azure.vm_user = VM_USER_NAME
      azure.vm_password = VM_PASSWORD
      azure.vm_size = 'Small' # ExtraSmall,Small,Medium,Large,ExtraLarge,A6,A7
      
      azure.vm_name = VM_NAME
      azure.cloud_service_name = VM_NAME # *.cloudapp.net
      #azure.deployment_name = VM_NAME
      azure.vm_location = 'Japan West'
      #azure.private_key_file = ''
      #azure.certificate_file = ''
      
      #azure.ssh_port = '22' # default '22'
      
      #azure.winrm_transport = [ 'http', 'https' ] # this will open up winrm ports on both http (5985) and http (5986) ports
      #azure.winrm_https_port = 'A VALID PUBLIC PORT' # customize the winrm https port, instead of 5986
      #azure.winrm_http_port = 'A VALID PUBLIC PORT' # customize the winrm http port, insted of 5985
      
      azure.tcp_endpoints = '80'
  end
end
