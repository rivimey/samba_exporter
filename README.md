Ansible Role: samba\_exporter
==========================

Install and configure Prometheus samba\_exporter.

Requirements
------------

An Ansible 2.2 or higher installation.<br />

Role Variables
--------------

Available variables are listed below, along with default values (see defaults/main.yml):

    samba_exporter_release_url: ""

Directory to which the samba\_exporter binaries will be symlinked.

    samba_exporter_listen_address: "127.0.0.1:9922"

The samba\_exporter WebServer listen ip address and port.<br/>
**NOTE**: the samba\_exporter metrics will be available at `{{ samba_exporter_listen_address }}/metrics`.

Directory used by the samba\_exporter's textfile collector to look for `*.prom` metrics files to be
exposed by the exporter.
See https://github.com/prometheus/samba_exporter#textfile-collector.

    samba_exporter_additional_cli_args: ""

Additional command-line arguments to be added to the samba\_exporter service unit.
For the complete refence of the available CLI arguments please refer to the output
of the `samba_exporter --help` command.

Dependencies
------------

None.

Example Playbooks
-----------------

    $ cat playbook.yml
    - name: "Install and configure Prometheus samba\_exporter"
      hosts: all
      roles:
        - { role: rivimey.samba_exporter }

License
-------

MIT

Author Information
------------------

Andrea Tosatto ([@\_hilbert\_](https://twitter.com/_hilbert_))
