ansible-steamcmd
=========

![Ansible Role](https://img.shields.io/ansible/role/42112.svg?color=blue) ![Ansible Quality Score](https://img.shields.io/ansible/quality/42112.svg?color=blue) ![Ansible Role](https://img.shields.io/ansible/role/d/42112.svg?color=blue)

Description
------------
Ansible role to install/update SteamCMD.  

This role will make SteamCMD available to all users with sudo permissions.  
The SteamCMD commands itself will always run as a system user called `steam`.  
The same user should be used to run any games servers.

Get this role
------------
```bash
ansible-galaxy install --roles-path ./roles/ siw36.ansible_steamcmd
```

Example Playbook
----------------

Install SteamCMD on all hosts in the `game-servers` group.  

```yaml
- hosts: game-servers
  roles:
     - siw36.ansible-steamcmd
```

Usage after installation  
------------
Update SteamCMD itself and exit:
```bash
sudo steamcmd +quit
```
Install a game server:  
```bash
sudo mkdir /home/steam/<game_name>
sudo chown steam:steam /home/steam/<game_name>
sudo steamcmd +login anonymous +force_install_dir /home/steam/<game_name> +app_update <app_id> +quit
```

Requirements
------------

The user used on the remote host must have permissions to execute `sudo` commands without being prompted for password confirmation.

License
-------

GNU General Public License v3.0

Author Information
------------------

Created by Robin 'siw36' Klussmann (07/2019)
