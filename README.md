# Ansible role for Celery


This role will install [celery](http://www.celeryproject.org/), a distributed
task queue. You can also install [Flower](http://flower.readthedocs.org/en/latest/),
a web based monitoring dashboard for celery clusters.

## Tested On

  * Ubuntu 14.04

## Defaults

The `defaults/main.yml` should be pretty clear on the usage and values. The 
version used by defaults are:

  * `celery_user`: www-data
  * `celery_group`: www-data
  * `celery_logdir`: /var/log/celeryd
  * `celery_piddir`: /var/run/celeryd
  * `web_app_dir`: /var/www/html/

## Usage

The tests in the respository should be pretty straight forward, but here are
some examples:

### Celery

playbook.yml:

```
- name: Install and run Celery
  hosts: all
  sudo: True

  vars:
    web_app_dir: /var/www/xxx/coresite/
  
  roles:
    - { role: ansible-celery }

```

## TODO

  * Extract supervisor to it's own role
  * Extend to other distros

