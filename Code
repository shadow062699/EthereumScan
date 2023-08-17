from eth_account import Account
from web3 import Web3
import time

# Create an instance of the Web3 class connected to the desired network
w3 = Web3(Web3.HTTPProvider("https://mainnet.infura.io/v3/4e779a6e40c14cfabd41fcc6a612e413"))

# Infinite loop to continuously generate keys and check balances
while True:
    # Generate a random private key
    private_key = Account.create()._private_key.hex()

    # Derive the Ethereum address from the private key
    address = Account.from_key(private_key).address

    # Check the balance of the address
    balance = w3.eth.get_balance(address)

    # Convert the balance from wei to Ether
    balance_ether = w3.from_wei(balance, 'ether')

    print(f"Private Key: {private_key}")
    print(f"Address: {address}")
    print(f"Balance: {balance_ether} Ether")

    # Check if balance is above 0.10 Ether
    if balance_ether > 0.10:
        break

    # Wait for some time before generating the next key
    time.sleep(5)  # Adjust the delay as needed
