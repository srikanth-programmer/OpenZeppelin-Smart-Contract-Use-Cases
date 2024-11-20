# OpenZeppelin Smart Contracts Guide

This document provides an organized and comprehensive guide to OpenZeppelin smart contracts, covering their use cases, import statements, and implementation scenarios. Follow this to choose the right contract for your specific use case, optimize for gas, and ensure security.

## Table of Contents

- [Access Control Contracts](#access-control-contracts)
- [Token Contracts](#token-contracts)
- [Security Contracts](#security-contracts)
- [Utilities](#utilities)
- [Governance Contracts](#governance-contracts)
- [Finance Contracts](#finance-contracts)
- [Proxy Contracts](#proxy-contracts)
- [Common Implementations](#common-implementations)

## Access Control Contracts

### 1. AccessControl.sol

**Use Cases:**
- Role-based access control for multiple roles
- Complex permission systems (e.g., admin, moderator, user)
- Need different admin roles for various functions

**Import Statement:**
```solidity
import "@openzeppelin/contracts/access/AccessControl.sol";
```

**Additional Content:** Use grantRole, revokeRole, and hasRole to manage permissions.

### 2. Ownable.sol

**Use Cases:**
- Simple single-owner access control
- Transferable ownership
- Basic admin functionality

**Import Statement:**
```solidity
import "@openzeppelin/contracts/access/Ownable.sol";
```

**Additional Content:** Provides transferOwnership and onlyOwner modifiers.

### 3. IAccessControl.sol

**Use Cases:**
- Custom access control systems
- Create interfaces to interact with AccessControl
- Build role-based systems from scratch

**Import Statement:**
```solidity
import "@openzeppelin/contracts/access/IAccessControl.sol";
```

## Token Contracts

### ERC20 Contracts

#### 1. ERC20.sol

**Use Cases:**
- Basic fungible token creation
- Need standard token functionality (e.g., transfer, approve)

**Import Statement:**
```solidity
import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
```

#### 2. ERC20Burnable.sol

**Use Cases:**
- Enable token burning
- Deflationary token mechanisms

**Import Statement:**
```solidity
import "@openzeppelin/contracts/token/ERC20/extensions/ERC20Burnable.sol";
```

#### 3. ERC20Capped.sol

**Use Cases:**
- Token with a maximum supply limit
- Fixed supply tokens

**Import Statement:**
```solidity
import "@openzeppelin/contracts/token/ERC20/extensions/ERC20Capped.sol";
```

#### 4. ERC20Pausable.sol

**Use Cases:**
- Add emergency stop functionality
- Temporarily freeze transfers

**Import Statement:**
```solidity
import "@openzeppelin/contracts/token/ERC20/extensions/ERC20Pausable.sol";
```

#### 5. ERC20Snapshot.sol

**Use Cases:**
- Maintain historical balances
- Use in dividend distribution or voting systems

**Import Statement:**
```solidity
import "@openzeppelin/contracts/token/ERC20/extensions/ERC20Snapshot.sol";
```

### ERC721 Contracts

#### 1. ERC721.sol

**Use Cases:**
- Basic NFT functionality
- Unique digital assets

**Import Statement:**
```solidity
import "@openzeppelin/contracts/token/ERC721/ERC721.sol";
```

#### 2. ERC721Enumerable.sol

**Use Cases:**
- Enumerate NFTs for marketplaces or stats
- Need to track total supply and ownership

**Import Statement:**
```solidity
import "@openzeppelin/contracts/token/ERC721/extensions/ERC721Enumerable.sol";
```

#### 3. ERC721URIStorage.sol

**Use Cases:**
- Dynamic metadata for NFTs
- Customizable token properties

**Import Statement:**
```solidity
import "@openzeppelin/contracts/token/ERC721/extensions/ERC721URIStorage.sol";
```

### ERC1155 Contracts

#### 1. ERC1155.sol

**Use Cases:**
- Multiple token types (fungible & non-fungible)
- Gaming items or large collections

**Import Statement:**
```solidity
import "@openzeppelin/contracts/token/ERC1155/ERC1155.sol";
```

## Security Contracts

### 1. ReentrancyGuard.sol

**Use Cases:**
- Prevent reentrancy attacks on functions
- Safeguard token transfers and external calls

**Import Statement:**
```solidity
import "@openzeppelin/contracts/security/ReentrancyGuard.sol";
```

### 2. Pausable.sol

**Use Cases:**
- Add an emergency stop mechanism
- Temporary halt critical operations

**Import Statement:**
```solidity
import "@openzeppelin/contracts/security/Pausable.sol";
```

## Utilities

### 1. SafeMath.sol

**Use Cases:**
- Prevent overflow/underflow in versions <0.8.0

**Import Statement:**
```solidity
import "@openzeppelin/contracts/utils/math/SafeMath.sol";
```

### 2. Counters.sol

**Use Cases:**
- Token IDs or incremental counters

**Import Statement:**
```solidity
import "@openzeppelin/contracts/utils/Counters.sol";
```

## Governance Contracts

### 1. Governor.sol

**Use Cases:**
- Implement decentralized voting systems
- On-chain governance for DAOs

**Import Statement:**
```solidity
import "@openzeppelin/contracts/governance/Governor.sol";
```

### 2. TimelockController.sol

**Use Cases:**
- Time-lock administrative functions
- Delayed governance actions for transparency

**Import Statement:**
```solidity
import "@openzeppelin/contracts/governance/TimelockController.sol";
```

## Proxy Contracts

### 1. ERC1967Proxy.sol

**Use Cases:**
- Upgradeable smart contracts

**Import Statement:**
```solidity
import "@openzeppelin/contracts/proxy/ERC1967/ERC1967Proxy.sol";
```

### 2. Clones.sol

**Use Cases:**
- Minimal proxies for gas optimization
- Factory patterns

**Import Statement:**
```solidity
import "@openzeppelin/contracts/proxy/Clones.sol";
```

## Common Implementations

### DeFi Lending Platform

```solidity
import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
import "@openzeppelin/contracts/security/ReentrancyGuard.sol";
import "@openzeppelin/contracts/security/Pausable.sol";
import "@openzeppelin/contracts/access/AccessControl.sol";
```

### NFT Marketplace

```solidity
import "@openzeppelin/contracts/token/ERC721/extensions/ERC721Royalty.sol";
import "@openzeppelin/contracts/security/ReentrancyGuard.sol";
import "@openzeppelin/contracts/access/Ownable.sol";
```

---

This guide serves as a quick reference for integrating OpenZeppelin contracts into your projects. For best practices, always use the latest versions, thoroughly test contracts, and review the official OpenZeppelin Documentation.
