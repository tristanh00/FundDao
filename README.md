# FundDao

## Contract Features

- The contract enables users to deposit and withdraw funds.
- The contract utilizes a fee structure, with fee percentages designated for the developer (dev), fund operations (fund), owner, and shareholders.
- The contract also allows the owner to execute token swaps via the Uniswap v2 Router.
- Additionally, the owner can transfer tokens or ETH to a recipient address.

## Contract Overview

### Data Structures

- `Depositor`: A struct representing a depositor with fields for the deposited amount, payout, and an active status flag.
- `depositors`: A mapping to associate an address with its respective `Depositor` struct.
- `depositorsList`: An array to keep track of all active depositors.

### Functionality

- `constructor`: Sets initial values for the dev, fund, and owner addresses.
- `onlyDev`, `onlyAdmin`, `onlyOwner`: Modifiers that limit function access to specific roles.
- `updateDev`, `updateFund`, `updateOwner`: Functions to update addresses for the dev, fund, and owner, respectively.
- `updateFees`: Function to adjust the percentages allocated to dev, fund, owner, and shareholders from profits.
- `updateWithdrawal`: Function to control whether withdrawals are allowed.
- `transferTokens`, `transferEth`: Functions for the owner to transfer tokens or ETH to a recipient.
- `swap`: Function for the owner to perform token swaps using the Uniswap V2 Router.
- `deposit`: Allows users to deposit funds into the contract.
- `withdraw`: Allows users to withdraw their profits and optionally their deposited funds, provided withdrawals are allowed.
- `distributeProfits`: Distributes profits between dev, fund, owner, and depositors according to their respective fee percentages.
- `receive`: A fallback function that allows direct ETH deposits.

## Dependencies

- OpenZeppelin Contracts: A library for secure smart contract development.
- Uniswap V2 Router: Interfaces to interact with the Uniswap v2 Router contract for token swaps.

## License

The smart contract is released under the MIT License.
