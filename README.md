# A simple github cli

Author: Robert Nowotniak 2020 <<rnowotniak@gmail.com>>

   Usage:

    ghub  -h | help
    ghub [ list ]
    ghub create [ -d <description> ] [ -p ] <repo_name>
                -p  means create a public repository (private is the default)
    ghub delete <repo_name> [ <repo_name> ... ]
    ghub info <repo_name> [ <repo_name> ... ]

## List repositories

    $ ghub 
    ansiblelab
    dropbox-sync-python
    github-cli
    ParticleSwarmOptimization-vb
    qclib
    qopt
    $ _

## Create repository

    $ ghub create -d 'My cli test repo' Test123
    https://github.com/rnowotniak/Test123
    $ _

Result
(will be instantly reflected in `ghub list` output too):

![create](img/create.png)

## Delete repository

    $ ghub delete Test123
    $ _

    $ ghub delete non-existing
    Not Found
    $ _

## Get repository info

    $ ghub info github-cli | jq -r .description
    A simple CLI for github (repository list/create/delete/info)
    $ _

    $ ghub info saltlab | jq -r .license.name
    GNU General Public License v3.0
    $ _

    $ ghub info ansiblelab | jq -r .updated_at
    2020-03-24T03:30:25Z
    $ _
