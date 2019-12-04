rundeck_cfg_projects
=========

This ansible role aims to add/remove projects to rundeck with its API.

Requirements
------------

Rundeck is installed and accessible. You need admin password and user credentials.

Please replace this **{{ ansible_eth0.ipv4.address }}** in 00_rudeck_auth.yml as your needs.
Role Variables
--------------
```yaml
rundeck_user_login: "admin"
rundeck_user_password: "mysuperpassword"
rundeck_docker_container_name: "rundeck-web"


remove_project: false

###### Project config with resources type file
rundeck_project_name: 'project_one'
rundeck_project_description: 'My project description'
rundeck_project_ssh_authentication: "privateKey"
rundeck_project_ssh_keypath: "/home/rundeck/.ssh/id_rsa"
rundeck_resources_source_1_config_file: "/home/rundeck/projects/{{ rundeck_project_name }}/etc/resources.xml"
rundeck_resources_source_1_config_format: "resourcexml"
rundeck_resources_source_1_config_generateFileAutomatically: "true"
rundeck_resources_source_1_file: "/home/rundeck/projects/{{ rundeck_project_name }}/etc/resources.xml"
rundeck_resources_source_1_format: "resourcexml"
rundeck_resources_source_1_generateFileAutomatically: "true"
rundeck_resources_source_1_includeServerNode: "true"
rundeck_resources_source_1_requireFileExists: "true"
rundeck_resources_source_1_type: "file"

####### Dictionary nodes
nodes:
  - { name: "mickey", description: "my first node", tags: 'centos', hostname: "192.168.1.10", osArch: "i386", osFamily: "unix", osName: "Darwin", osVersion: "9.2.2", username: "ansible_user" }
  - { name: "pluto", description: "my second node", tags: 'front', hostname: "192.168.1.11", osArch: "i386", osFamily: "unix", osName: "Darwin", osVersion: "9.2.2", username: "ansible_user" }


```
Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
