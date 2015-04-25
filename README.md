## Requirements
- R
- littler

<br>
## Installation
#### Arch Linux

    yaourt -S r littler

<br>
### Configuration
#### Set location of users library

    sudo groupadd rusers
    sudo usermod -a -G rusers ${USER}

    sudo mkdir -p /usr/local/lib/R/library
    sudo chown ${USER}:rusers /usr/local/lib/R/library

    echo "R_LIBS_USER = \"/usr/local/lib/R/library\"" \
        | tee -a ${HOME}/.Renviron

<br>
### Usage

    ./installr.r <package>

Example:

    ./installr.r gdata
    ./installr.r openxlsx xlsx

<br>
### Problems with rJava on Arch
(problem isn't related to script or littler)

To install rJava you should:

    unset JAVA_HOME           # unset JAVA_HOME variable
    sudo R CMD javareconf     # update R's Java configuration
    ./install.r rJava         # and at the end install rJava

