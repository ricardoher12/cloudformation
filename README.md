# Cloud Fromation (WordPress Server)
Scripts to create a WordPress server using a RDS. The AWS's services used are the following:

* CloudFormation
* VPC (Subnets, SecurityGroups)
* RDS (MySql)
* EC2

## RDHRCF file
The rdhrCF.yml file is the master file for the cloud formation, in which all the stacks (VPC, RDS and EC2) stacks are created with their respective parameters.

## VPCCloudFormation file
The VPCCloudFormation.yml is the file in which  VPC, security groups and publics and privates subnets are configurated. With this template only 3 publics and 3 privates subnets are created. This file has the following parameters:

* VPCCidr: The CIRD that you will use in your net
* PublicSubnet1Cidr: the CIDR of the first public subnet
* PublicSubnet2Cidr: the CIDR of the second public subnet
* PublicSubnet3Cidr: the CIDR of the third public subnet
* PrivateSubnet1Cidr: the CIDR of the first private subnet
* PrivateSubnet2Cidr: the CIDR of the second private subnet
* PrivateSubnet3Cidr: the CIDR of the third private subnet

## RDSCloudFormation file
In the RDSCloudFormation.yml the RDS for wordpress is configured. This template has the following parameters:

* DBInstanceID: the database's ID
* DBName: the database's namne
* DBInstanceClass: the instance's type of the EC2 that will be used to create the data base
* DBAllocatedStorage: The storage thar will be available for the database
* DBUsername: the database's username
* DBPassword: the password that will be used to connect to the database
* DBSecurityGroup: the security group that the database will be using
* PrivateSubnetList: the subnets on which the database will be hosted

## EC2CloduFormation file
In the EC2CloduFormation.yml file the EC2 instance for wordpress is configured, this template has the following parameters:

* KeyName: the shh key's name that will be used to connect to the instance, once it's created.
* SecurityGroup: the security group that will be attached to the instance.
* EC2Image: the image that will be used to create the instance.
* InstType: the type of EC2 instance that will be used.
* VPC: the vpc in which the instance will be hosted.
* Subnet: the subnet that will provide the instance's IP address
* InstanceName: the instance's name
* DBName: the db name to which wodrpress will connect tp
* DBUser: the username of the db used for wordpress
* DBPass: the password of the db used for wordpress
* DBHost: the database's url to which wordpress will connect to
* InstName: the EC2 instance's name


## Project Diagram
<img src="/CFScripts/cloduformation.png" alt="Cloud Fromation Diagram"/>