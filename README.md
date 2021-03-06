syoncloud
=========

Syoncloud Logs processes log files from various applications and many servers.
Syoncloud Logs 0.3 - Community Edition

Copyright (C) 2012 Syoncloud

Introduction

Syoncloud Logs processes log files from various applications and many servers. It includes Syoncloud HBase web client with tree and table view of data. It enables to capture business relevant information from everyday log files generated by web servers, business applications and back office applications. It uses Flume sinks that run on the machines that produce log files.
This data is filtered and relevant events channelled to HBase. HBase NoSQL database is used for actual data analysis. The number of HBase nodes depends on the amount of processed log files. Syoncloud Logs has easy to use installer that includes all necessary components such as Hadoop, Flume, Hbase and Zookeeper.

Requirements

    Syoncloud requires Redhat (Fedora, Centos) style operating system.
    It requires Oracle Java JDK 1.6 or higher.
    There should be at least 1GB disk space on local machine.
    Root or sudo access is required just for installation.
    Make sure that no HBase, Hadoop or Zookeeper instances are running on the local machine. In case you want other instances to be running you have to change default ports during installation process.

Changes in version 0.3

    Syoncloud HBase web client is a part of the installation. It displays tree of HBase tables and column families linked to paginated grid of data.

Changes in version 0.2

    Fixes of installer and scripts regarding SSH configuration.
    Installation of Kerberos.
    Tests on Fedora 17.
    Updated documentation.

Installation

    Make sure that Oracle JDK 1.6 is installed and path is set to java binary. You can use command "which java"
    Under sudo or root start installation by: java -jar ./syoncloud-0.3.jar . If you get an error message that xterm can not be open you have to use root account.
    Accept license and select path to local JDK.
    Select installation path for Syoncloud. All necessary files will be installed in this directory.
    Select pseudo-distributed installation to run all servers on local machine. This mode is intended for evaluation and debugging. For production distributed mode should be used.
    Enter user data
    Syoncloud servers can run as a daemon (service) or regular applications.
    Log processing is done by default by HBase but there is an option to use Hadoop Map/Red as well.
    Enter operating system user name that will be used to run all Syoncloud servers.
    Enter and repeat secure password for given Linux user.
    Enter host name of the local machine and name of local node of Syoncloud.
    There is a list of default ports for HBase, Hadoop, Flume and Zookeeper. You should change the ports in case some of the ports are already used by other running instance of some of the applications.
    Continue to next page and select what type of log files will be processed. There is an example of apache log file with certain structure ($INSTALL_PATH/syoncloud_data/example_log/access_log). Syoncloud can process given log file and store record in 'apacheExample' table in HBase.
    Make sure there are no errors during "Processing" stage of the installation.
    You can start all Syoncloud servers by logging in as Syoncloud user and in its home directory there is a start.sh script.
    You can find index.html file in the installation directory. If you view this file in browser you can see links to webUIs of installed servers.
    You can check log files of all Syoncloud servers in installation directory under logs sub-directory ($INSTALL_PATH/logs).
    During the first start of Syoncloud configuration and data are created for Flume, Hadoop and HBase. You can run given process manually by script populate_syoncloud.sh .

Testing, Implementation, Production

    You can view HBase data using Syoncloud HBase web client. Its usual url is: http://localhost:8180/syoncloud-hbase/ . In order to view your data you can select table and column family in the tree structure.

Components and versions

    Syoncloud HBase Client 0.3
    Flume 0.9.4
    Hadoop 1.0.2
    HBase 0.92.1
    Zookeeper 3.4.3

If you find a bug or need help do not hesitated to write us at info@syoncloud.com