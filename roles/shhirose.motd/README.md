# Role Name

[![Github](https://img.shields.io/badge/github-shhirose%2Fansible--motd-brightgreen.svg)](https://github.com/shhirose/ansible-motd)
[![Ansible galaxy](https://img.shields.io/badge/ansible--galaxy-shhirose%2Fmotd-brightgreen.svg)](https://galaxy.ansible.com/shhirose/motd/)
[![Build Status](https://travis-ci.org/shhirose/ansible-motd.svg?branch=master)](https://travis-ci.org/shhirose/ansible-motd)
[![MIT License](http://img.shields.io/badge/license-MIT-blue.svg?style=flat)](LICENSE)

This is Ansible role for motd setting for RedHat Enterprise Linux, Debian, and Ubuntu.

## Requirements

None

# Role Variables

```
shhirose_motd_content: ''
shhirose_motd_shell_results: []
  # - ''
shhirose_motd_shell_after: ''
```

## Variable parameters

### shhirose_motd

| key | required | default | type | values | notes |
| --- | --- | --- | --- | --- | --- |
| content | no |  | string |  | This is content for `/etc/motd`. |
| shell_results | no |  | array |  | This is an array for shell command. |
| shell_after | no |  | string |  | This is content after shell_results. |

## Dependencies

None

## Example Playbook

```
- hosts: servers
  become: yes
  roles:
    - shhirose.motd
  vars:
    shhirose_motd_content: |-
      xx      xx  xxxxxx  xxxxxx  xxxx
      xxxx  xxxx  xx  xx    xx    xx  xx
      xx xxxx xx  xx  xx    xx    xx  xx
      xx  xx  xx  xxxxxx    xx    xxxx
    shhirose_motd_shell_results:
      - 'echo -n "kernel: "; uname -r'
    shhirose_motd_shell_after: 'author: shhirose'
```

## License

MIT
