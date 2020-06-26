Herbsters Cryptocurrency
========================

Home Page: http://herbsters.com

Block Explorer: http://explorer.herbsters.com

Faucet: http://herbsfaucet.com

Wallet: http://cryptonetwork.host

Mining Pool: http://herbs.cryptonetwork.host

What is herbsters?
----------------

herbsters is an experimental digital currency that enables instant payments to
anyone, anywhere in the world. herbsters uses peer-to-peer technology to operate
with no central authority: managing transactions and issuing money are carried
out collectively by the network. herbsters Core is the name of open source
software which enables the use of this currency.

For more information, as well as an immediately useable, binary version of
the herbsters Core software, see [http://herbsters.com](http://herbsters.com).

License
-------

herbsters Core is released under the terms of the MIT license. See [COPYING](COPYING) for more
information or see https://opensource.org/licenses/MIT.

Development Process
-------------------

Developer IRC can be found on irc.findarea.world at #herbsters.

Working Ubuntu Bionic Beaver 18.04 [ Linux ]
--------------------------------------------

Required Dependency
-------------------

sudo apt-get update

sudo apt-get install git wget

sudo apt-get install build-essential libtool autotools-dev automake pkg-config libevent-dev bsdmainutils python3

sudo add-apt-repository universe

sudo apt-get update

sudo apt-get install libboost-all-dev

sudo apt-get install libdb-dev libdb++-dev

Necessary Openssl Version 1.1.1 Installation
---------------------------------------------

cd ~

wget https://www.openssl.org/source/openssl-1.1.1f.tar.gz

tar -zxf openssl-1.1.1f.tar.gz && cd openssl-1.1.1f

./config

(You may need to run [ sudo apt install make gcc ] before running this command successfully)

make

make test

sudo mv /usr/bin/openssl ~/tmp

sudo make install

sudo ln -s /usr/local/bin/openssl /usr/bin/openssl

sudo ldconfig

Source Installation
-------------------

cd ~

git clone https://github.com/herbsters/herbsters.git

cd ~/herbsters

./autogen.sh

./configure --with-incompatible-bdb

make

edit ~/.profile
---------------

export PATH=$PATH:/home/USERNAME/herbsters/src

create ~/.herbsters/herbsters.conf
----------------------------------

server=1

txindex=1

addnode=149.28.46.64:7999

addnode=45.77.144.188:7999

rpcuser=custom_user_id

rpcpassword=THISWHERETHAT_PWD

rpcport=7998

port=7999

rpcbind=0.0.0.0

rpcallowip=0.0.0.0/0

rpcallowip=127.0.0.1

rpcallowip=149.28.46.64

rpcallowip=45.77.144.188

daemon=1

gen=1

listen=1

paytxfee=0.001

4way=1

Directions
----------

cd ~

mkdir .herbsters

cp herbsters.conf .herbsters

Commands
--------

START: herbstersd -deprecatedrpc=accounts -daemon

DATA: herbsters-cli getinfo

COIN CREDIT: herbsters-cli getbalance

TARGET BLOCK: herbsters-cli getblocktemplate

WALLET ADDRESS: herbsters-cli getaccountaddress ""

SEND COINS: herbsters-cli sendtoaddress "address" amount

MOVE COINS: herbsters-cli move "#" "" amount
