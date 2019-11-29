# What is Zcoin?
 Zcoin is a privacy focused cryptocurrency that utilizes zero-knowledge proofs which allows users to destroy coins and then redeem them later for brand new ones with no transaction history. It was the first project to implement the Zerocoin protocol and has now transitioned to the Sigma protocol which has no trusted setup and small proof sizes. Zcoin also utilises Dandelion++ to obscure the originating IP of transactions without relying on any external services such as Tor/i2P.

Zcoin developed and utilizes Merkle Tree Proofs (MTP) as its Proof-of-Work algorithm which aims to be memory hard with fast verification.

# Running with Docker
If you are already familiar with Docker, then running Zcoin with Docker might be the the easier method for you. To run Zcoin using this method, first install Docker. After this you may continue with the following instructions.

Please note that we currently don't support the GUI when running with Docker. Therefore, you can only use RPC (via HTTP or the zcoin-cli utility) to interact with Zcoin via this method.

Pull our latest official Docker image:

    docker pull zcoinofficial/zcoind
### Start Zcoin daemon:

    docker run --detach --name zcoind zcoinofficial/zcoind
### View current block count (this might take a while since the daemon needs to find other nodes and download blocks first):

    docker exec zcoind zcoin-cli getblockcount
### View connected nodes:

    docker exec zcoind zcoin-cli getpeerinfo
### Stop daemon:

    docker stop zcoind
### Backup wallet:

    docker cp zcoind:/home/zcoind/.zcoin/wallet.dat .
### Start daemon again:

    docker start zcoind
