# [qemu](#qemu)

Install qemu.

|Travis|GitHub|Quality|Downloads|Version|
|------|------|-------|---------|-------|
|[![travis](https://travis-ci.com/robertdebock/ansible-role-qemu.svg?branch=master)](https://travis-ci.com/robertdebock/ansible-role-qemu)|[![github](https://github.com/robertdebock/ansible-role-qemu/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-qemu/actions)|[![quality](https://img.shields.io/ansible/quality/)](https://galaxy.ansible.com/robertdebock/qemu)|[![downloads](https://img.shields.io/ansible/role/d/)](https://galaxy.ansible.com/robertdebock/qemu)|[![Version](https://img.shields.io/github/release/robertdebock/ansible-role-qemu.svg)](https://github.com/robertdebock/ansible-role-qemu/releases/)|

## [Example Playbook](#example-playbook)

This example is taken from `molecule/resources/converge.yml` and is tested on each push, pull request and release.
```yaml
---
- name: converge
  hosts: all
  become: yes
  gather_facts: yes

  roles:
    - role: robertdebock.qemu
      qemu_systems:
        - qemu-system-x86
```

The machine needs to be prepared in CI this is done using `molecule/resources/prepare.yml`:
```yaml
---
- name: prepare
  hosts: all
  become: yes
  gather_facts: no

  roles:
    - role: robertdebock.bootstrap
```

Also see a [full explanation and example](https://robertdebock.nl/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

These variables are set in `defaults/main.yml`:
```yaml
---
# defaults file for qemu

# A list of qemu systems to install.
# qemu_systems:
#   - qemu-system-aarch64
#   - qemu-system-aarch64-core
#   - qemu-system-alpha
#   - qemu-system-alpha-core
#   - qemu-system-arm
#   - qemu-system-arm-core
#   - qemu-system-avr
#   - qemu-system-avr-core
#   - qemu-system-cris
#   - qemu-system-cris-core
#   - qemu-system-hppa
#   - qemu-system-hppa-core
#   - qemu-system-lm32
#   - qemu-system-lm32-core
#   - qemu-system-m68k
#   - qemu-system-m68k-core
#   - qemu-system-microblaze
#   - qemu-system-microblaze-core
#   - qemu-system-mips
#   - qemu-system-mips-core
#   - qemu-system-moxie
#   - qemu-system-moxie-core
#   - qemu-system-nios2
#   - qemu-system-nios2-core
#   - qemu-system-or1k
#   - qemu-system-or1k-core
#   - qemu-system-ppc
#   - qemu-system-ppc-core
#   - qemu-system-riscv
#   - qemu-system-riscv-core
#   - qemu-system-rx
#   - qemu-system-rx-core
#   - qemu-system-s390x
#   - qemu-system-s390x-core
#   - qemu-system-sh4
#   - qemu-system-sh4-core
#   - qemu-system-sparc
#   - qemu-system-sparc-core
#   - qemu-system-tricore
#   - qemu-system-tricore-core
#   - qemu-system-unicore32
#   - qemu-system-unicore32-core
#   - qemu-system-x86
#   - qemu-system-x86-core
#   - qemu-system-xtensa
#   - qemu-system-xtensa-core
```

## [Requirements](#requirements)

- Access to a repository containing packages, likely on the internet.
- A recent version of Ansible. (Tests run on the current, previous and next release of Ansible.)

## [Status of requirements](#status-of-requirements)

| Requirement | Travis | GitHub |
|-------------|--------|--------|
| [robertdebock.bootstrap](https://galaxy.ansible.com/robertdebock/bootstrap) | [![Build Status Travis](https://travis-ci.com/robertdebock/ansible-role-bootstrap.svg?branch=master)](https://travis-ci.com/robertdebock/ansible-role-bootstrap) | [![Build Status GitHub](https://github.com/robertdebock/ansible-role-bootstrap/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-bootstrap/actions) |

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://robertdebock.nl/) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/robertdebock/drawings/artifacts/qemu.png "Dependency")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/robertdebock):

|container|tags|
|---------|----|
|alpine|all|
|amazon|all|
|el|7, 8|
|debian|all|
|fedora|all|
|opensuse|all|
|ubuntu|all|

The minimum version of Ansible required is 2.9, tests have been done to:

- The previous version.
- The current version.
- The development version.



## [Testing](#testing)

[Unit tests](https://travis-ci.com/robertdebock/ansible-role-qemu) are done on every commit, pull request, release and periodically.

If you find issues, please register them in [GitHub](https://github.com/robertdebock/ansible-role-qemu/issues)

Testing is done using [Tox](https://tox.readthedocs.io/en/latest/) and [Molecule](https://github.com/ansible/molecule):

[Tox](https://tox.readthedocs.io/en/latest/) tests multiple ansible versions.
[Molecule](https://github.com/ansible/molecule) tests multiple distributions.

To test using the defaults (any installed ansible version, namespace: `robertdebock`, image: `fedora`, tag: `latest`):

```
molecule test

# Or select a specific image:
image=ubuntu molecule test
# Or select a specific image and a specific tag:
image="debian" tag="stable" tox
```

Or you can test multiple versions of Ansible, and select images:
Tox allows multiple versions of Ansible to be tested. To run the default (namespace: `robertdebock`, image: `fedora`, tag: `latest`) tests:

```
tox

# To run CentOS (namespace: `robertdebock`, tag: `latest`)
image="centos" tox
# Or customize more:
image="debian" tag="stable" tox
```

## [License](#license)

Apache-2.0


## [Author Information](#author-information)

[Robert de Bock](https://robertdebock.nl/)

Please consider [sponsoring me](https://github.com/sponsors/robertdebock).
