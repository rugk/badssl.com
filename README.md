[![badssl.com](badssl.com.png)](https://badssl.com)

Visit [`badssl.com`](https://badssl.com/) for a list of test subdomains, including:

- [`self-signed.badssl.com`](https://self-signed.badssl.com)
- [`expired.badssl.com`](https://expired.badssl.com)
- [`sha1.badssl.com`](https://sha1.badssl.com)
- [`mixed.badssl.com`](https://mixed.badssl.com)
- [`rc4.badssl.com`](https://rc4.badssl.com)
- [`hsts.badssl.com`](https://hsts.badssl.com)

## Server Setup

Stock Ubuntu VM, DNS A records for `badssl.com.` and `*.badssl.com.` pointing to the VM.

### Commands

    sudo apt-get update ; sudo apt-get install git nginx
    git clone https://github.com/lgarron/badssl.com && cd badssl.com

    sudo make install
    sudo service nginx restart

### Docker version


    sudo apt-get update ; sudo apt-get install docker.io
    git clone https://github.com/lgarron/badssl.com && cd badssl.com

    sudo docker build --no-cache -t badssl .
    sudo docker run -d -p 80:80 -p 443:443 --name badssl badssl

## Disclaimer

`badssl.com` is maintained for *manual* testing of security UI in web clients.

The functionality of any given subdomain is likely to be stable, but note that anything may change without notice. If you would like a documented guarantee for a particular use case, please file an issue. (Alternatively, you could make a fork and host your own copy.)