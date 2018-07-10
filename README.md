# CentOS 6 minimal Vagrant Box

**Current CentOS Version Used**: 6.9

**Pre-built Vagrant Box**:

  - [`vagrant init vhubert/centos6`](https://app.vagrantup.com/vhubert/boxes/centos6)

This build configuration installs and configures CentOS 6 x86_64 minimal using Ansible, and then generates a Vagrant box file for VirtualBox.

The example can be modified to use more Ansible roles, plays, and included playbooks to fully configure (or partially) configure a box file suitable for deployment for development environments.

## Requirements

The following software must be installed/present on your local machine before you can use Packer to build the Vagrant box file:

  - [Packer](http://www.packer.io/)
  - [Vagrant](http://vagrantup.com/)
  - [VirtualBox](https://www.virtualbox.org/) (if you want to build the VirtualBox box)
  - [VMware Workstation Pro](https://www.vmware.com/products/workstation-pro.html) (if you want to build the VMware Workstation box)
  - [vagrant-vmware-desktop](https://www.vagrantup.com/vmware/index.html) (if you want to build the VMware Workstation box)
  - [Hyper-V](https://www.virtualbox.org/) (if you want to build the Hyper-V box)

## Usage

Make sure all the required software (listed above) is installed, then cd to the directory containing this README.md file, and run:

    $ .\run provider_name

Don't try to use use pare
After a few minutes, Packer should tell you the box was generated successfully, and the box was uploaded to Vagrant Cloud.

> **Note**: This configuration includes a post-processor that pushes the built box to Vagrant Cloud (which requires a `VAGRANT_CLOUD_TOKEN` environment variable to be set); remove the `vagrant-cloud` post-processor from the Packer template to build the box locally and not push it to Vagrant Cloud. You don't need to specify a `version` variable either, if not using the `vagrant-cloud` post-processor.

## Testing built boxes

There's an included Vagrantfile that allows quick testing of the built Vagrant boxes. From this same directory, run one the following command after building the box:

    $ vagrant up

## License

MIT license.

## Author Information

Created in 2018 by [Valentin Hubert]
