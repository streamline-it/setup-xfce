Role Name
=========

setup-xfce

Installs Xfce and lightdm as the display manager.

Requirements
------------


Role Variables
--------------

# user list whose purpose is to make sure the gecos field is update so
# the name properly appears under lightdm's user dropdown
setup_xfce_gui_users:
  - username:
    gecos:

# Contents of FreeBSD file under vars
setup_xfce_pkgs:
  - lightdm
  - lightdm-gtk-greeter
  - dbus
  - xfce

setup_xfce_svcs:
  - lightdm

setup_xfce_sysrc_directives:
  - name: lightdm_enable
    value: "YES"
  - name: dbus_enable
    value: "YES"

#command to update pixbuf cache
setup_xfce_pixbuf_update_path: /usr/local/bin/gdk-pixbuf-query-loaders

#command to update mime database
setup_xfce_mime_db_path: /usr/local/bin/update-mime-database

#location of mime database
setup_xfce_mime_data_path: /usr/local/share/mime

#location of mime database
setup_xfce_mime_data_path: /usr/local/share/mime

Dependencies
------------

None

Example Playbook
----------------

    - hosts: servers
      vars:

        xfce_gui_user:
          - username: rich
            gecos: "Rich"

      roles:
         - name: setup-xfce

License
-------

BSD

Author Information
------------------

Rich O'Hara

