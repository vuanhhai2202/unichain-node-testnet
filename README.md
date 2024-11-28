# unichain-node-testnet
code chạy
1. update
2. 
sudo apt update && sudo apt upgrade -y

sudo apt install docker.io

sudo apt install curl

sudo curl -L "https://github.com/docker/compose/releases/download/v2.20.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose

git clone https://github.com/Uniswap/unichain-node

cd unichain-node

nano .env.sepolia

https://ethereum-sepolia-rpc.publicnode.com
https://ethereum-sepolia-beacon-api.publicnode.com

2. chạy node:
   
docker-compose up -d

3. check curl
curl -d '{"id":1,"jsonrpc":"2.0","method":"eth_getBlockByNumber","params":["latest",false]}' \
  -H "Content-Type: application/json" http://localhost:8545

- check log unichain op node 
docker logs unichain-node-op-node-1

- check log unichain nodeexecution client
docker logs unichain-node-execution-client-1

- Khởi động lại
docker-compose down
docker-compose up -d

4. lấy privekey để nhập vào ví okx:

cat ~/unichain-node/geth-data/geth/nodekey (nếu không được thì vào thẳng thư mục copy)

5. deploy contract
[ -f "unichain.sh" ] && rm unichain.sh; wget -q https://raw.githubusercontent.com/zunxbt/unichain/refs/heads/main/unichain.sh && chmod +x unichain.sh && ./unichain.sh

điền privekey và tên token là xong
6. xong

7. nếu lỗi premision thì thêm sudo vào trước mỗi câu lệnh
