# Project Notes

All this project does is to hold the Open API specs for the GoKabam Project

## What this does and current progress

* To start with,  I have a few sample sagger and md files
  * The docs will be multilingual,
    * so the md files will have locale extentions
    * The YAML keys will all be mapped to translation keys , the specs will be built with the actual words in other places
    * YAML files will have a final erb extension to the text is put in place
* I need to serve the md files from the /md/ path , using their relative directory structure from swagger root
  * The md files will each have a brief single line comment with it at the top, which is used to make the link text
  * The md files will also have notes not meant for being part of the public documents
    * See below for how that is handled
* Next I will add in a route to combine all the yaml files to just one big one,and have the md comments linked in by url
* Then I will auto generate the html docs from the single yml file
* After that I will substitute out the links of the md files from everything but the code and put in the html generated content from the md
  * The Code samples will have the links preserved, which have brief text
* Finally, I will have some git hooks so when I commit any changes to this api spec, the docs and code samples will be automatically gnerated and pushed to the correct repositories
  * Docs will be build in two versions
  * Public version:
    * All Language documents will be built automatically
    * English only for the private note version, which goes in a seperate repo
  * Both versions will be pushed to servers for being on the web


### Issues to solve


## Install Notes

This was the first rails 5 project I have done. So I changed up my usual gems for this not so bulky rails client, in practice for making other apps later.

* I did not want to use rubyracer, but node, which I installed from nvm, locally on my account, on Ubuntu.

  And the rubymine and local rails server did not pick it up

  To make it work:

    ```
    EXECJS_RUNTIME=Node
     in the environment variables for the rubymine debug configeration

    and I made a symlink

    `sudo ln -s  /home/will/.nvm/versions/node/v6.11.2/bin/node /usr/local/bin/node`

    but that will change when I update node, so I will have to go in and delete the symlink and redo it using the path

    `which node`
    ```
   If putting on production will have to use the server settings there to point to node






