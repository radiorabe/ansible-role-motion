# RaBe Ansible Role Motion

This Role helps install and configure a [motion](http://motion-project.github.io) setup.

Is should be useful as regular role but is also container enabled since it has
about the right surface for it to help us figure out if containers are going
anywhere soon in some of the use cases motion offers.

The role follows the [SemVer 2 spec](https://semver.org/spec/v2.0.0.html).

Adds a motion service to your [Ansible Container](https://github.com/ansible/ansible-container) project. Run the following commands
to install the service:

```
# Set the working directory to your Ansible Container project root
$ cd myproject

# Install the service
$ ansible-container install <USERNAME.ROLE_NAME>
```

## Requirements

- Distro package manager prepared to install `motion` package.
- [Ansible Container](https://github.com/ansible/ansible-container) (optional)
- An existing Ansible Container project. To create a project, simply run the following:
    ```
    # Create an empty project directory
    $ mkdir myproject

    # Set the working directory to the new directory
    $ cd myproject

    # Initialize the project
    $ ansible-contiainer init
    ```

## Role Variables

Motion has lots of templatable variables. Only the most important are mentioned
here. Please check the [defaults(defaults/main.yml] for a complete listing of
configurable variables.

| variable | required | default | comments |
| -------- | -------- | ------- | -------- |
| `motion_install` | no | `yes` | Set to `no` to disable installation of package |
| `motion_package_name` | no | `motion` | |
| `motion_configure` | no | `yes` | Set to `no` to disable configuration of motion package |
| `motion_config_dir` | no | `/etc/motion` |
| `motion_config_file` | no | `/etc/motion/motion.conf` |
| `motion_logfile` | no | |
| `motion_log_level` | no | 6 |
| `motion_log_type` | no | `all` |
| `motion_videodevice` | no | `/dev/video0` |
| `motion_v4l_palette` | no | `17` |
| `motion_input` | no | 1 |
| `motion_width` | no | 320 |
| `motion_height` | no | 240 |
| `motion_framerate` | no | 2 |
| `motion_cameras` | no | `[]` | Configuration for multiple cameras.

### Camera variables

multi-camera setup TBD

| variable | required | default | comments |
| -------- | -------- | ------- | -------- |

```yaml
---
motion_cameras:
- name: camera 1
```

## Dependencies

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

## License

AGPLv3

## Author Information

Copyright (c) 2018 [Radio Bern RaBe](http://www.rabe.ch).
