# This repo contains my Pritunl VPN server ansible roles and playbook

---------------------------------------------------------

[Ansible](https://www.ansible.com/)

## How to deploy

1. Configure your inventory

2. Deploy

    ```bash
    ansible-playbook full_server.yml -i inventory/inventory.ini
    ```

## How to setup Pritunl

1. Log in to your server and:

    ```bash
    pritunl setup-key
    ```

2. Access to http://IP_ADRESS/ and enter values obtained before

3. Next you would be asked about username and password

    To obtain username and password:

    ```bash
    pritunl default-password
    ```

4. Next enter:
    - Username
    - Password
    - Lets Encrypt Domain (IP.sslip.io for example)

5. Enter with new creds to https://IP.sslip.io

6. Internal setup:

    - Setup new organization `Users` -> `Add Organization`
    - Setup new vpn server `Servers` -> `Add Server` and set listener port from `pritunl clients server port` [playbook](pritunl.yml)
    - Attach organization to server
    - Start vpn server
    - To setup custom routes stop vpn server in GUI and add them
    - Setup users `Users` -> `Add User`

## This repo contains few roles:

1. firewalld by David Roble

2. [pritunl by thehunt33r](https://github.com/thehunt33r/ansible-role-pritunl)

3. [liquidprompt](https://github.com/nojhan/liquidprompt.git) role by [Perry Kollmorgen](https://github.com/perryk)

4. ansible-role-epel-basic-soft by me


