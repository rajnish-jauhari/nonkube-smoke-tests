# Skupper V2 nonkube smoke tests Ansible Project

Skupper V2 nonkube smoke tests using Ansible.
Runs the hello-world example using only nonkube platforms.

The execution is mean to cover the following matrix:

| Command | OS | User | Platform |
| :---- | :---- | :---- | :---- |
| bootstrap | fedora39 | rootless | podman |
| bootstrap | fedora39 | rootless | docker |
| bootstrap | fedora39 | rootless | systemd |
| bootstrap | fedora39 | root | podman |
| bootstrap | fedora39 | root | docker |
| bootstrap | fedora39 | root | systemd |
| bootstrap | rhel9 | rootless | podman |
| bootstrap | rhel9 | rootless | docker |
| bootstrap | rhel9 | rootless | systemd |
| bootstrap | rhel9 | root | podman |
| bootstrap | rhel9 | root | docker |
| bootstrap | rhel9 | root | systemd |
| bootstrap | ubuntu2304 | rootless | podman |
| bootstrap | ubuntu2304 | rootless | docker |
| bootstrap | ubuntu2304 | rootless | systemd |
| bootstrap | ubuntu2304 | root | podman |
| bootstrap | ubuntu2304 | root | docker |
| bootstrap | ubuntu2304 | root | systemd |
| bootstrap.sh | fedora39 | rootless | podman |
| bootstrap.sh | fedora39 | rootless | docker |
| bootstrap.sh | fedora39 | rootless | systemd |
| bootstrap.sh | fedora39 | root | podman |
| bootstrap.sh | fedora39 | root | docker |
| bootstrap.sh | fedora39 | root | systemd |
| bootstrap.sh | rhel9 | rootless | podman |
| bootstrap.sh | rhel9 | rootless | docker |
| bootstrap.sh | rhel9 | rootless | systemd |
| bootstrap.sh | rhel9 | root | podman |
| bootstrap.sh | rhel9 | root | docker |
| bootstrap.sh | rhel9 | root | systemd |
| bootstrap.sh | ubuntu2304 | rootless | podman |
| bootstrap.sh | ubuntu2304 | rootless | docker |
| bootstrap.sh | ubuntu2304 | rootless | systemd |
| bootstrap.sh | ubuntu2304 | root | podman |
| bootstrap.sh | ubuntu2304 | root | docker |
| bootstrap.sh | ubuntu2304 | root | systemd |


**Notes:**

* The bootstrap binary must be built locally and placed under the following
  directory before the playbooks can be executed:
  `collections/ansible_collections/fgiorgetti/nonkube_smoke_tests/roles/run/files/commands/`

* All hosts must be updated accordingly under `inventory/hosts.yml`

* The participant hosts must have the following tools installed and ready to use:
  * Podman
  * Docker (cloud-user must have permission to manage containers)
  * Skupper router (built from sources or installed using RPM)
  * Your user must be able to log in as both root and cloud-user against all hosts

## Included content/ Directory Structure

The directory structure follows best practices recommended by the Ansible community. Feel free to customize this template according to your specific project requirements.

```
 ansible-project/
 |── .devcontainer/
 |    └── docker/
 |        └── devcontainer.json
 |    └── podman/
 |        └── devcontainer.json
 |    └── devcontainer.json
 |── .github/
 |    └── workflows/
 |        └── tests.yml
 |    └── ansible-code-bot.yml
 |── .vscode/
 |    └── extensions.json
 |── collections/
 |   └── requirements.yml
 |   └── ansible_collections/
 |       └── project_org/
 |           └── project_repo/
 |               └── README.md
 |               └── roles/sample_role/
 |                         └── README.md
 |                         └── tasks/main.yml
 |── inventory/
 |   └── groups_vars/
 |   └── host_vars/
 |   └── hosts.yml
 |── ansible-navigator.yml
 |── ansible.cfg
 |── devfile.yaml
 |── linux_playbook.yml
 |── network_playbook.yml
 |── README.md
 |── site.yml
```

## Compatible with Ansible-lint

Tested with ansible-lint >=24.2.0 releases and the current development version of ansible-core.
