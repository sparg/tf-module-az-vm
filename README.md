## Module VM

### Structure
- **main.tf**
- **variables.tf**
- **outputs.tf**

### Usage module

Virtual Machine
```hcl
module "virtual_machine" {
  source = "git@github.com:Sparg/tf-module-az-vm.git?ref=<release-tag>"

  instance            = var.instance
  resource_group_name = var.resource_group
  location            = var.location
  vm_size             = var.vm_size
  admin_username      = var.admin_username
  public_ssh_key      = var.public_key
  environment         = var.environment

  image_publisher = var.image_publisher
  image_offer     = var.image_offer
  image_sku       = var.image_sku
  image_version   = var.image_version

  computer_name = var.computer_name

  # network
  subnet_id = var.subnet_id
}
```

### Outputs module

Virtual Machine
- `id`
- `network_interface_id`
- `public_ip_address`
