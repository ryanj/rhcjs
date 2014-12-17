rhcjs
=====
OpenShift Node.js module for interfacing with OpenShift from Node.js. 

## Usage

### Install
    
    # install module
    npm install --save rhcjs
    
### Usage - Basic Auth
  
    var rhc = require('rhcjs)({
      username : 'test@test.com',
      password : 'test123',
      target : 'openshift.redhat.com', // optional - defaults to openshift.redhat.com
      domain : 'test' // optional - if ommitted derrived from email in username
    });

### Usage - Bearer Auth
    
    var rhc = require('rhcjs)({
      username : 'test@test.com',
      token : '1a2b3c', // bearer auth token
    });

### List Apps
    
    rhc.apps(function(err, res){
      // Res will be an array of apps
    });  
  
### Show App Info
    
    rhc.app.show({ app : 'Some app name' }, function(err, res){
      // Res will be app info
    });  
    
### Create App
    
    rhc.app.create({ name : 'Some app name', cartridge : 'Cartridge to create using' }, function(err, res){
      
    });  

### Configure an app
    
    rhc.app.configure({ app : 'Some app name', auto_deploy : true, deployment_branch : 'master' }, function(err, res){
      
    });  

    
### Delete App
    
    rhc.app.del({ app : 'Some app name' }, function(err, res){
      
    });  

### Add SSH Key to user account
    
    rhc.ssh.add({ name : 'Ssh key name', key : 'SSH key content' }, function(err, res){
      
    });  

### Remove an SSH Key
    
    rhc.ssh.remove({ name : 'Ssh key name' }, function(err, res){
      
    });  

### List cartridges

    rhc.cartridges(function(err, res){
      
    });  
  
### Generate Bearer authentication token (initialise rhcjs using username:password)

    rhc.authorize(function(err, res){
      
    });  
  
    
## Running Tests
  
  npm test
  
