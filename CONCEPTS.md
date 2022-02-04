
## Introduction
- https://xord.com/publications/hyperledger-fabric-architecture-a-deep-dive/

## System ChainCodes
- https://medium.com/coinmonks/system-chaincodes-in-hyperledger-fabric-vscc-escc-lscc-cscc-a48db4d24dc3

## Offchain Storage
- https://deeptiman.medium.com/offchain-storage-in-hyperledger-fabric-77e28bd99e0c
- https://hackernoon.com/making-a-case-for-offchain-storage-in-hyperledger-fabric-deep-dive-2f8g32v0

## Preventing Key Collisions
- https://medium.com/@gatakka/how-to-prevent-key-collisions-in-hyperledger-fabric-chaincode-303700716733

## Concurrency in Chaincodes
- Reference >> https://ibm.github.io/hlf-internals/shim-architecture/interaction-flow/transaction-processing/
- Transaction proposals are executed asynchronously leaving main thread to process other requests
- Chaincode initialisation and transaction execution is handled differently

## Lifecycle of Chaincode
- Chaincode setup, gRPC communication, protocol execution, interfacing, configuration, business logic
- deserialisation (unmarshalling) of the ChaincodeInput instance from the ChaincodeMessage payload;
- creation of a new instance of the ChaincodeStub and configuration of the transaction context 
- It comprises of channel identifier, transaction identifier, input (i.e. ChaincodeInput) and signed proposal;
- invocation of the Chaincode.Init(ChaincodeStub) or Chaincode.Invoke(ChaincodeStub) method.

## Chaincode and gRPC
- bidirectional communication stream with the peer

## Chaincode and Shim concepts
- The shim is responsible for starting and coordinating the interaction between the Chaincode implementation and the peer the process is connected to. 