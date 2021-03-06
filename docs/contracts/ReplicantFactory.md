# Avastar Replicant Factory

View Source: [contracts/ReplicantFactory.sol](https://github.com/Dapp-Wizards/Avastars-Contracts/blob/master/contracts/ReplicantFactory.sol)

**ReplicantFactory** **↗ Extends: [PrimeFactory](contracts/PrimeFactory.md)**
**↘ Derived Contracts: [AvastarTeleporter](contracts/AvastarTeleporter.md), [ReplicantFactoryWrapper](contracts/ReplicantFactoryWrapper.md)**

## Contract Members
**Constants & Variables**

```solidity
// public members
uint16 public constant MAX_REPLICANTS_PER_GENERATION;

```

## **Events**

- [NewReplicant](#newreplicant)

### NewReplicant

Event emitted upon the creation of an Avastar Replicant

```solidity
event NewReplicant(
	uint256 id,
	uint256 serial,
	enum AvastarTypes.Generation generation,
	enum AvastarTypes.Gender gender,
	uint256 traits
)
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| id | uint256 | the token ID of the newly minted Replicant | 
| serial | uint256 | the serial of the Replicant | 
| generation | enum AvastarTypes.Generation | the generation of the Replicant | 
| gender | enum AvastarTypes.Gender | the gender of the Replicant | 
| traits | uint256 | the trait hash of the Replicant | 

## **Functions**

- [getReplicantByGenerationAndSerial](#getreplicantbygenerationandserial)
- [getReplicantByTokenId](#getreplicantbytokenid)
- [mintReplicant](#mintreplicant)

### getReplicantByGenerationAndSerial

Get the Avastar Replicant metadata associated with a given Generation and Serial

```solidity
function getReplicantByGenerationAndSerial(enum AvastarTypes.Generation _generation, uint256 _serial)
external view
returns (
	uint256 tokenId,
	uint256 serial,
	uint256 traits,
	enum AvastarTypes.Generation generation,
	enum AvastarTypes.Gender gender,
	uint8 ranking
)
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| _generation | enum AvastarTypes.Generation | the generation of the specified Replicant | 
| _serial | uint256 | the serial of the specified Replicant | 

**Returns**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| tokenId | uint256 | the Replicant's token ID | 
| serial | uint256 | the Replicant's serial | 
| traits | uint256 | the Replicant's trait hash | 
| generation | enum AvastarTypes.Generation | the Replicant's generation | 
| gender | enum AvastarTypes.Gender | the Replicant's gender | 
| ranking | uint8 | the Replicant's ranking | 

### getReplicantByTokenId

Get the Avastar Replicant associated with a given Token ID

```solidity
function getReplicantByTokenId(uint256 _tokenId)
external view
returns (
	uint256 tokenId,
	uint256 serial,
	uint256 traits,
	enum AvastarTypes.Generation generation,
	enum AvastarTypes.Gender gender,
	uint8 ranking
)
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| _tokenId | uint256 | the token ID of the specified Replicant | 

**Returns**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| tokenId | uint256 | the Replicant's token ID | 
| serial | uint256 | the Replicant's serial | 
| traits | uint256 | the Replicant's trait hash | 
| generation | enum AvastarTypes.Generation | the Replicant's generation | 
| gender | enum AvastarTypes.Gender | the Replicant's gender | 
| ranking | uint8 | the Replicant's ranking | 

### mintReplicant

Mint an Avastar Replicant.
Only invokable by minter role, when contract is not paused.
If successful, emits a `NewReplicant` event.

```solidity
function mintReplicant(
	address _owner,
	uint256 _traits,
	enum AvastarTypes.Generation _generation,
	enum AvastarTypes.Gender _gender,
	uint8 _ranking
)
external nonpayable onlyMinter whenNotPaused 
returns (uint256 tokenId, uint256 serial)
```

**Arguments**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| _owner | address | the address of the new Avastar's owner | 
| _traits | uint256 | the new Replicant's trait hash | 
| _generation | enum AvastarTypes.Generation | the new Replicant's generation | 
| _gender | enum AvastarTypes.Gender | the new Replicant's gender | 
| _ranking | uint8 | the new Replicant's rarity ranking | 

**Returns**

| Name        | Type           | Description  |
| ------------- |------------- | -----|
| tokenId | uint256 | the newly minted Replicant's token ID | 
| serial | uint256 | the newly minted Replicant's serial | 

