=====================================================
sshc - ssh connection manager for command line users
=====================================================
--------------------------------------------------------
licenesed under LGPLv3 terms (see LICENSE file)
--------------------------------------------------------
written in Ruby by Dmitry Geurkov (d.geurkov@gmail.com)
--------------------------------------------------------

How to install?

Do this in command line::

    sudo cp ./sshc /usr/local/bin
    cp ./sshc.config.example ~/.sshc
    chmod 0700 ~/.sshc

Then edit your ``~/.sshc`` and add your connections

How to use?

Basicly it mimics ssh functionality so see man ssh for arguments::

    sshc [ssh arguments] connection [command]

So for example if you've added connection named connection1 to your ``~/.sshc``

To connect to server execute::

    sshc connection1

To connect to server using ssh v2 protocol and do not execute any command::

    sshc -N -2 connection1

To connect to server and forward some ports::

    sshc -L 8080:localhost:8080 connection1

To connect to server and execute command ls::

    sshc connection ls

Also you can sftp to your connection::

    sshc sftp [sftp arguments] connection[:path]

And scp files between your connections::

    sshc scp [scp arguments] [from:]path [to:]path
