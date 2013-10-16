#windows_firewall
[![Build
Status](https://secure.travis-ci.org/liamjbennett/puppet-windows_firewall.png)](http://travis-ci.org/liamjbennett/puppet-windows_firewall)
[![Dependency
Status](https://gemnasium.com/liamjbennett/puppet-windows_firewall.png)](http://gemnasium.com/liamjbennett/puppet-windows_firewall)

####Table of Contents

##Overview
Puppet module to manage the Microsoft Windows Firewall

##Module Description

##Setup

**What windows_firewall affects:**

*
*
*

###Beginning with windows_firewall

The windows_firewall class has some defaults that can be overridden, for instance if you wanted to disable to windows firewall

	class { 'windows_firewall': ensure => 'stopped' }

## Allow port/protocol example ##
    windows_firewall::exception { 'WINRM':
      ensure       => present,
      direction    => 'in',
      action       => 'Allow',
      enabled      => 'yes',
      protocol     => 'TCP',
      port         => '5985',
      key_name     => 'WINRM-HTTP-In-TCP',
      display_name => 'Windows Remote Management HTTP-In',
      description  => 'Inbound rule for Windows Remote Management via WS-Management. [TCP 5985]',
    }

## Allow program example ##
   windows_firewall::exception { 'myapp':
     ensure       => present,
     direction    => 'in',
     action       => 'Allow',
     enabled      => 'yes',
     program      => 'C:\\myapp.exe',
     display_name => 'My App',
     description  => 'Inbound rule for My App',
   }

##Usage

###Classes and Defined Types

...

####Class: `windows_firewall`

...

####Defined Type: `windows_firewall::exception`

...

##Limitations

...

##Development

### Overview

...

### Running tests

This project contains tests for [rspec-puppet](http://rspec-puppet.com/) to verify functionality. For in-depth information please see their respective documentation.

Quickstart:

    gem install bundler
    bundle install
    bundle exec rake spec

##Copyright and License

Copyright (C) 2013 Liam Bennett - liamjbennett@gmail.com 

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

  http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
