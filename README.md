# porosity
## Alternatives
As you can see Porosity is now unmaintained, we recommend [JEB Decompiler for smart-contracts](https://www.pnfsoftware.com/blog/ethereum-smart-contract-decompiler/) by Nicolas Failliere as an alternative.

Why is it unmaintained? After some initial research on Ethereum Smart-Contracts and Ethereum Virtual Machine, I came to the conclusion that the foundation of Ethereum were not strong enough to be a sustainable long term and that spending time on it was a waste of time. We will surely see alternative languages that will take over Ethereum for the smart-contract platforms.
The most shocking part is that decades of work on secure languages and secure virtual machines has been done prior the existance of Ethereum (and other DLT languages/platforms) and it had been totally ignored from the beginning.  

We also recommend you to read @msuiche blogpost from December 2017 on the [future of smart-contract languages](https://blog.comae.io/smart-contract-languages-development-to-follow-992e30774b39).

## Getting Started

Platform         | Status
-----------------|-----------
Windows          | [![Build Status](https://comae.visualstudio.com/_apis/public/build/definitions/13b58962-60a0-48ed-879d-f56575385e2e/4/badge)](https://comae.visualstudio.com/_apis/public/build/definitions/13b58962-60a0-48ed-879d-f56575385e2e/4/badge)
Linux.           | Supported
Mac OS X.        | Supported

## Overview
Ethereum is gaining a significant popularity in the blockchain community, mainly due to fact that it is design in a way that enables developers to write decentralized applications (Dapps) and smart-contract using blockchain technology.


Ethereum blockchain is a consensus-based globally executed virtual machine, also referred as  Ethereum Virtual Machine (EVM) by implemented its own micro-kernel supporting a handful number of instructions, its own stack, memory and storage. This enables the radical new concept of distributed applications.


Contracts live on the blockchain in an Ethereum-specific binary format (EVM const unknown4060b25e = '2.0.0'
const unknownc311c523 = 1

def storage:
  stor0 is mapping of uint256 at storage 0
  stor1 is mapping of uint8 at storage 1
  owner is addr at storage 2
  unknowncd7c0326Address is addr at storage 3
  name is array of uint256 at storage 4
  symbol is array of uint256 at storage 5
  totalSupply is mapping of uint256 at storage 6
  unknownf923e8c3 is array of uint256 at storage 7
  uri is array of uint256 at storage 8
  stor9 is uint8 at storage 9
  stor10 is mapping of uint8 at storage 10
  creator is mapping of addr at storage 11

def name() payable: 
  return name[0 len name.length]

def uri(uint256 _id) payable: 
  return uri[_id][0 len uri[_id].length]

def creator(uint256 _tokenId) payable: 
  require calldata.size - 4 >= 32
  return creator[_tokenId]

def unknown73505d35(addr _param1) payable: 
  require calldata.size - 4 >= 32
  return bool(stor10[_param1])

def owner() payable: 
  return owner

def symbol() payable: 
  return symbol[0 len symbol.length]

def totalSupply(uint256 _id) payable: 
  require calldata.size - 4 >= 32
  return totalSupply[_id]

def unknowncd7c0326() payable: 
  return unknowncd7c0326Address

def unknownf923e8c3() payable: 
  return unknownf923e8c3[0 len unknownf923e8c3.length]

#
#  Regular functions
#

def _fallback() payable: # default function
  revert

def isOwner() payable: 
  return (caller == owner)

def exists(uint256 _tokenId) payable: 
  require calldata.size - 4 >= 32
  return (totalSupply[_tokenId] > 0)

def supportsInterface(bytes4 _interfaceId) payable: 
  require calldata.size - 4 >= 32
  if Mask(32, 224, _interfaceId) != 0x1ffc9a700000000000000000000000000000000000000000000000000000000:
      if Mask(32, 224, _interfaceId) != 0xd9b67a2600000000000000000000000000000000000000000000000000000000:
          return 0
  return 1

def setApprovalForAll(address _to, bool _approved) payable: 
  require calldata.size - 4 >= 64
  stor1[caller][addr(_to)] = uint8(_approved)
  log ApprovalForAll(
        address owner=_approved,
        address operator=caller,
        bool approved=_to)

def isApprovedForAll(address _owner, address _operator) payable: 
  require calldata.size - 4 >= 64
  if not stor10[addr(_operator)]:
      require ext_code.size(unknowncd7c0326Address)
      static call unknowncd7c0326Address.proxies(address param1) with:
              gas gas_remaining wei
             args _owner
      if not ext_call.success:
          revert with ext_call.return_data[0 len return_data.size]
      require return_data.size >= 32
      if ext_call.return_data_operator:
          return bool(stor1[addr(_owner)][addr(_operator)])
  return 1

def unknownd26ea6c0(addr _param1) payable: 
  require calldata.size - 4 >= 32
  if owner != caller:
      if not stor10[caller]:
          require ext_code.size(unknowncd7c0326Address)
          static call unknowncd7c0326Address.proxies(address param1) with:
                  gas gas_remaining wei
                 args owner
          if not ext_call.success:
              revert with ext_call.return_data[0 len return_data.size]
          require return_data.size >= 32
          if ext_call.return_data[12 len 20] != caller:
              revert with 0x8c379a000000000000000000000000000000000000000000000000000000000, 
                          32,
                          46,
                          0x44455243313135355472616461626c65236f6e6c794f776e65723a2043414c4c45525f49535f4e4f545f4f574e45,
                          mem[210 len 18]
  unknowncd7c0326Address = _param1

def unknown9e037eea(addr _param1) payable: 
  require calldata.size - 4 >= 32
  if owner != caller:
      if not stor10[caller]:
          require ext_code.size(unknowncd7c0326Address)
          static call unknowncd7c0326Address.proxies(address param1) with:
                  gas gas_remaining wei
                 args owner
          if not ext_call.success:
              revert with ext_call.return_data[0 len return_data.size]
          require return_data.size >= 32
          if ext_call.return_data[12 len 20] != caller:
              revert with 0x8c379a000000000000000000000000000000000000000000000000000000000, 
                          32,
                          46,
                          0x44455243313135355472616461626c65236f6e6c794f776e65723a2043414c4c45525f49535f4e4f545f4f574e45,
                          mem[210 len 18]
  stor10[addr(_param1)] = 0

def unknowna50aa5c3(addr _param1) payable: 
  require calldata.size - 4 >= 32
  if owner != caller:
      if not stor10[caller]:
          require ext_code.size(unknowncd7c0326Address)
          static call unknowncd7c0326Address.proxies(address param1) with:
                  gas gas_remaining wei
                 args owner
          if not ext_call.success:
              revert with ext_call.return_data[0 len return_data.size]
          require return_data.size >= 32
          if ext_call.return_data[12 len 20] != caller:
              revert with 0x8c379a000000000000000000000000000000000000000000000000000000000, 
                          32,
                          46,
                          0x44455243313135355472616461626c65236f6e6c794f776e65723a2043414c4c45525f49535f4e4f545f4f574e45,
                          mem[210 len 18]
  stor10[addr(_param1)] = 1

def renounceOwnership() payable: 
  if owner != caller:
      if not stor10[caller]:
          require ext_code.size(unknowncd7c0326Address)
          static call unknowncd7c0326Address.proxies(address param1) with:
                  gas gas_remaining wei
                 args owner
          if not ext_call.success:
              revert with ext_call.return_data[0 len return_data.size]
          require return_data.size >= 32
          if ext_call.return_data[12 len 20] != caller:
              revert with 0x8c379a000000000000000000000000000000000000000000000000000000000, 
                          32,
                          46,
                          0x44455243313135355472616461626c65236f6e6c794f776e65723a2043414c4c45525f49535f4e4f545f4f574e45,
                          mem[210 len 18]
  log OwnershipTransferred(
        address previousOwner=owner,
        address newOwner=0)
  owner = 0

def unknown24d88785(array _param1) payable: 
  require calldata.size - 4 >= 32
  require _param1 <= 4294967296
  require _param1 + 36 <= calldata.size
  require _param1.length <= 4294967296 and _param1 + _param1.length + 36 <= calldata.size
  if owner != caller:
      if not stor10[caller]:
          require ext_code.size(unknowncd7c0326Address)
          static call unknowncd7c0326Address.proxies(address param1) with:
                  gas gas_remaining wei
                 args owner
          if not ext_call.success:
              revert with ext_call.return_data[0 len return_data.size]
          require return_data.size >= 32
          if ext_call.return_data[12 len 20] != caller:
              revert with 0, 
                          32,
                          46,
                          0x44455243313135355472616461626c65236f6e6c794f776e65723a2043414c4c45525f49535f4e4f545f4f574e45,
                          mem[ceil32(_param1.length) + 242 len 18]
  unknownf923e8c3[] = Array(len=_param1.length, data=_param1[all])

def transferOwnership(address _newOwner) payable: 
  require calldata.size - 4 >= 32
  if owner != caller:
      if not stor10[caller]:
          require ext_code.size(unknowncd7c0326Address)
          static call unknowncd7c0326Address.proxies(address param1) with:
                  gas gas_remaining wei
                 args owner
          if not ext_call.success:
              revert with ext_call.return_data[0 len return_data.size]
          require return_data.size >= 32
          if ext_call.return_data[12 len 20] != caller:
              revert with 0x8c379a000000000000000000000000000000000000000000000000000000000, 
                          32,
                          46,
                          0x44455243313135355472616461626c65236f6e6c794f776e65723a2043414c4c45525f49535f4e4f545f4f574e45,
                          mem[210 len 18]
  if not _newOwner:
      revert with 0x8c379a000000000000000000000000000000000000000000000000000000000, 
                  32,
                  38,
                  0x544f776e61626c653a206e6577206f776e657220697320746865207a65726f20616464726573,
                  mem[202 len 26]
  log OwnershipTransferred(
        address previousOwner=owner,
        address newOwner=_newOwner)
  owner = _newOwner

def balanceOf(address _owner, uint256 _cardId) payable: 
  require calldata.size - 4 >= 64
  if not creator[_cardId]:
      if uint64(_cardId) != _owner:
          if not stor10[addr(_owner)]:
              require ext_code.size(unknowncd7c0326Address)
              static call unknowncd7c0326Address.proxies(address param1) with:
                      gas gas_remaining wei
                     args uint64(_cardId)
              if not ext_call.success:
                  revert with ext_call.return_data[0 len return_data.size]
              require return_data.size >= 32
              if ext_call.return_data_owner:
                  return stor0[addr(_owner)][_cardId]
  else:
      if creator[_cardId] != _owner:
          if not stor10[addr(_owner)]:
              require ext_code.size(unknowncd7c0326Address)
              static call unknowncd7c0326Address.proxies(address param1) with:
                      gas gas_remaining wei
                     args creator[_cardId]
              if not ext_call.success:
                  revert with ext_call.return_data[0 len return_data.size]
              require return_data.size >= 32
              if ext_call.return_data_owner:
                  return stor0[addr(_owner)][_cardId]
  if totalSupply[_cardId] > _cardId % 1099511627776:
      revert with 0, 'SafeMath#sub: UNDERFLOW'
  if stor0[addr(_owner)][_cardId] + (_cardId % 1099511627776) - totalSupply[_cardId] < stor0[addr(_owner)][_cardId]:
      revert with 0, 'SafeMath#add: OVERFLOW'
  return (stor0[addr(_owner)][_cardId] + (_cardId % 1099511627776) - totalSupply[_cardId])

def unknown91686f53(uint256 _param1, addr _param2) payable: 
  require calldata.size - 4 >= 64
  if not creator[_param1]:
      if uint64(_param1) != caller:
          if not stor10[caller]:
              require ext_code.size(unknowncd7c0326Address)
              static call unknowncd7c0326Address.proxies(address param1) with:
                      gas gas_remaining wei
                     args uint64(_param1)
              if not ext_call.success:
                  revert with ext_call.return_data[0 len return_data.size]
              require return_data.size >= 32
              if ext_call.return_data[12 len 20] != caller:
                  revert with 0x8c379a000000000000000000000000000000000000000000000000000000000, 
                              32,
                              53,
                              0x454173736574436f6e74726163745368617265642363726561746f724f6e6c793a204f4e4c595f43524541544f525f414c4c4f5745,
                              mem[217 len 11]
  else:
      if creator[_param1] != caller:
          if not stor10[caller]:
              require ext_code.size(unknowncd7c0326Address)
              static call unknowncd7c0326Address.proxies(address param1) with:
                      gas gas_remaining wei
                     args creator[_param1]
              if not ext_call.success:
                  revert with ext_call.return_data[0 len return_data.size]
              require return_data.size >= 32
              if ext_call.return_data[12 len 20] != caller:
                  revert with 0x8c379a000000000000000000000000000000000000000000000000000000000, 
                              32,
                              53,
                              0x454173736574436f6e74726163745368617265642363726561746f724f6e6c793a204f4e4c595f43524541544f525f414c4c4f5745,
                              mem[217 len 11]
  if not _param2:
      revert with 0x8c379a000000000000000000000000000000000000000000000000000000000, 
                  32,
                  48,
                  0x734173736574436f6e74726163745368617265642373657443726561746f723a20494e56414c49445f41444452455353,
                  mem[212 len 16]
  creator[_param1] = _param2
  log 0x39071c63: _param1, _param2

def balanceOfBatch(address[] _param1, uint256[] _param2) payable: 
  require calldata.size - 4 >= 64
  require _param1 <= 4294967296
  require _param1 + 36 <= calldata.size
  require _param1.length <= 4294967296 and _param1 + (32 * _param1.length) + 36 <= calldata.size
  mem[128 len 32 * _param1.length] = call.data[_param1 + 36 len 32 * _param1.length]
  require _param2 <= 4294967296
  require _param2 + 36 <= calldata.size
  require _param2.length <= 4294967296 and _param2 + (32 * _param2.length) + 36 <= calldata.size
  mem[(32 * _param1.length) + 128] = _param2.length
  mem[(32 * _param1.length) + 160 len 32 * _param2.length] = call.data[_param2 + 36 len 32 * _param2.length]
  if _param1.length != _param2.length:
      revert with 0, 
                  32,
                  44,
                  0x54455243313135352362616c616e63654f6642617463683a20494e56414c49445f41525241595f4c454e4754,
                  mem[(32 * _param1.length) + (32 * _param2.length) + 272 len 20]
  mem[(32 * _param1.length) + (32 * _param2.length) + 160] = _param1.length
  if _param1.length:
      mem[(32 * _param1.length) + (32 * _param2.length) + 192 len 32 * _param1.length] = code.data * _param1.length]
  idx = 0
  while idx < _param1.length:
      require idx < _param1.length
      require idx < _param2.length
      mem[0] = mem[(32 * idx) + (32 * _param1.length) + 160]
      mem[32] = sha3(mem[(32 * idx) + 140 len 20], 0)
      require idx < _param1.length
      mem[(32 * idx) + (32 * _param1.length) + (32 * _param2.length) + 192] = stor0[mem[(32 * idx) + 140 len 20]][mem[(32 * idx) + (32 * _param1.length) + 160]]
      idx = idx + 1
      continue 
  mem[(64 * _param1.length) + (32 * _param2.length) + 192] = 32
  mem[(64 * _param1.length) + (32 * _param2.length) + 224] = _param1.length
  mem[(64 * _param1.length) + (32 * _param2.length) + 256 len floor32(_param1.length)] = mem[(32 * _param1.length) + (32 * _param2.length) + 192 len floor32(_param1.length)]
  return memory
    from (64 * _param1.length) + (32 * _param2.length) + 192
     len (161 * _param1.length) + 64

def setURI(uint256 _id, string _uri) payable: 
  require calldata.size - 4 >= 64
  require _uri <= 4294967296
  require _uri + 36 <= calldata.size
  require _uri.length <= 4294967296 and _uri + _uri.length + 36 <= calldata.size
  mem[128 len _uri.length] = _uri[all]
  mem[_uri.length + 128] = 0
  if not creator[_id]:
      if uint64(_id) == caller:
          uri[_id][] = Array(len=_uri.length, data=_uri[all])
          mem[ceil32(_uri.length) + 128] = 32
          mem[ceil32(_uri.length) + 160] = _uri.length
          mem[ceil32(_uri.length) + 192 len ceil32(_uri.length)] = _uri[all], mem[_uri.length + 128 len ceil32(_uri.length) - _uri.length]
          if not _uri.length % 32:
              log 0x6bb7ff70: Mask(8 * -ceil32(_uri.length) + _uri.length + 32, 0, 0), mem[_uri.length + 160 len ceil32(_uri.length) + -_uri.length + 32], Mask(8 * _uri.length, -(8 * _uri.length) + 256, _uri[all], mem[_uri.length + 128 len ceil32(_uri.length) - _uri.length]) << (8 * _uri.length) - 256, _id
          else:
              mem[floor32(_uri.length) + ceil32(_uri.length) + 192] = mem[floor32(_uri.length) + ceil32(_uri.length) + -(_uri.length % 32) + 224 len _uri.length % 32]
              log 0x6bb7ff70: Mask(8 * -ceil32(_uri.length) + _uri.length + 32, 0, 0), mem[_uri.length + 160 len ceil32(_uri.length) + -_uri.length + 32], Mask(8 * ceil32(_uri.length), -(8 * ceil32(_uri.length)) + 256, _uri[all], mem[_uri.length + 128 len ceil32(_uri.length) - _uri.length]) << (8 * ceil32(_uri.length)) - 256, mem[(2 * ceil32(_uri.length)) + 192 len floor32(_uri.length) + -ceil32(_uri.length) + 32], _id
      else:
          if stor10[caller]:
              uri[_id][] = Array(len=_uri.length, data=_uri[all])
              mem[ceil32(_uri.length) + 128] = 32
              mem[ceil32(_uri.length) + 160] = _uri.length
              mem[ceil32(_uri.length) + 192 len ceil32(_uri.length)] = _uri[all], mem[_uri.length + 128 len ceil32(_uri.length) - _uri.length]
              if not _uri.length % 32:
                  log 0x6bb7ff70: Mask(8 * -ceil32(_uri.length) + _uri.length + 32, 0, 0), mem[_uri.length + 160 len ceil32(_uri.length) + -_uri.length + 32], Mask(8 * _uri.length, -(8 * _uri.length) + 256, _uri[all], mem[_uri.length + 128 len ceil32(_uri.length) - _uri.length]) << (8 * _uri.length) - 256, _id
              else:
                  mem[floor32(_uri.length) + ceil32(_uri.length) + 192] = mem[floor32(_uri.length) + ceil32(_uri.length) + -(_uri.length % 32) + 224 len _uri.length % 32]
                  log 0x6bb7ff70: Mask(8 * -ceil32(_uri.length) + _uri.length + 32, 0, 0), mem[_uri.length + 160 len ceil32(_uri.length) + -_uri.length + 32], Mask(8 * ceil32(_uri.length), -(8 * ceil32(_uri.length)) + 256, _uri[all], mem[_uri.length + 128 len ceil32(_uri.length) - _uri.length]) << (8 * ceil32(_uri.length)) - 256, mem[(2 * ceil32(_uri.length)) + 192 len floor32(_uri.length) + -ceil32(_uri.length) + 32], _id
          else:
              require ext_code.size(unknowncd7c0326Address)
              static call unknowncd7c0326Address.proxies(address param1) with:
                      gas gas_remaining wei
                     args uint64(_id)
              if not ext_call.success:
                  revert with ext_call.return_data[0 len return_data.size]
              require return_data.size >= 32
              if ext_call.return_data[12 len 20] != caller:
                  revert with 0, 
                              32,
                              53,
                              0x454173736574436f6e74726163745368617265642363726561746f724f6e6c793a204f4e4c595f43524541544f525f414c4c4f5745,
                              mem[ceil32(_uri.length) + 249 len 11]
              uri[_id][] = Array(len=_uri.length, data=_uri[all])
              mem[ceil32(_uri.length) + 128] = 32
              mem[ceil32(_uri.length) + 192 len ceil32(_uri.length)] = _uri[all], mem[_uri.length + 128 len ceil32(_uri.length) - _uri.length]
              if not _uri.length % 32:
                  log 0x6bb7ff70: 0, 32, _uri.length, Mask(8 * _uri.length, -(8 * _uri.length) + 256, _uri[all], mem[_uri.length + 128 len ceil32(_uri.length) - _uri.length]) << (8 * _uri.length) - 256, _id
              else:
                  mem[floor32(_uri.length) + ceil32(_uri.length) + 192] = mem[floor32(_uri.length) + ceil32(_uri.length) + -(_uri.length % 32) + 224 len _uri.length % 32]
                  log 0x6bb7ff70: 0, 32, _uri.length, Mask(8 * ceil32(_uri.length), -(8 * ceil32(_uri.length)) + 256, _uri[all], mem[_uri.length + 128 len ceil32(_uri.length) - _uri.length]) << (8 * ceil32(_uri.length)) - 256, mem[(2 * ceil32(_uri.length)) + 192 len floor32(_uri.length) + -ceil32(_uri.length) + 32], _id
  else:
      if creator[_id] == caller:
          uri[_id][] = Array(len=_uri.length, data=_uri[all])
          mem[ceil32(_uri.length) + 128] = 32
          mem[ceil32(_uri.length) + 160] = _uri.length
          mem[ceil32(_uri.length) + 192 len ceil32(_uri.length)] = _uri[all], mem[_uri.length + 128 len ceil32(_uri.length) - _uri.length]
          if not _uri.length % 32:
              log 0x6bb7ff70: Mask(8 * -ceil32(_uri.length) + _uri.length + 32, 0, 0), mem[_uri.length + 160 len ceil32(_uri.length) + -_uri.length + 32], Mask(8 * _uri.length, -(8 * _uri.length) + 256, _uri[all], mem[_uri.length + 128 len ceil32(_uri.length) - _uri.length]) << (8 * _uri.length) - 256, _id
          else:
              mem[floor32(_uri.length) + ceil32(_uri.length) + 192] = mem[floor32(_uri.length) + ceil32(_uri.length) + -(_uri.length % 32) + 224 len _uri.length % 32]
              log 0x6bb7ff70: Mask(8 * -ceil32(_uri.length) + _uri.length + 32, 0, 0), mem[_uri.length + 160 len ceil32(_uri.length) + -_uri.length + 32], Mask(8 * ceil32(_uri.length), -(8 * ceil32(_uri.length)) + 256, _uri[all], mem[_uri.length + 128 len ceil32(_uri.length) - _uri.length]) << (8 * ceil32(_uri.length)) - 256, mem[(2 * ceil32(_uri.length)) + 192 len floor32(_uri.length) + -ceil32(_uri.length) + 32], _id
      else:
          if stor10[caller]:
              uri[_id][] = Array(len=_uri.length, data=_uri[all])
              mem[ceil32(_uri.length) + 128] = 32
              mem[ceil32(_uri.length) + 160] = _uri.length
              mem[ceil32(_uri.length) + 192 len ceil32(_uri.length)] = _uri[all], mem[_uri.length + 128 len ceil32(_uri.length) - _uri.length]
              if not _uri.length % 32:
                  log 0x6bb7ff70: Mask(8 * -ceil32(_uri.length) + _uri.length + 32, 0, 0), mem[_uri.length + 160 len ceil32(_uri.length) + -_uri.length + 32], Mask(8 * _uri.length, -(8 * _uri.length) + 256, _uri[all], mem[_uri.length + 128 len ceil32(_uri.length) - _uri.length]) << (8 * _uri.length) - 256, _id
              else:
                  mem[floor32(_uri.length) + ceil32(_uri.length) + 192] = mem[floor32(_uri.length) + ceil32(_uri.length) + -(_uri.length % 32) + 224 len _uri.length % 32]
                  log 0x6bb7ff70: Mask(8 * -ceil32(_uri.length) + _uri.length + 32, 0, 0), mem[_uri.length + 160 len ceil32(_uri.length) + -_uri.length + 32], Mask(8 * ceil32(_uri.length), -(8 * ceil32(_uri.length)) + 256, _uri[all], mem[_uri.length + 128 len ceil32(_uri.length) - _uri.length]) << (8 * ceil32(_uri.length)) - 256, mem[(2 * ceil32(_uri.length)) + 192 len floor32(_uri.length) + -ceil32(_uri.length) + 32], _id
          else:
              require ext_code.size(unknowncd7c0326Address)
              static call unknowncd7c0326Address.proxies(address param1) with:
                      gas gas_remaining wei
                     args creator[_id]
              if not ext_call.success:
                  revert with ext_call.return_data[0 len return_data.size]
              require return_data.size >= 32
              if ext_call.return_data[12 len 20] != caller:
                  revert with 0, 
                              32,
                              53,
                              0x454173736574436f6e74726163745368617265642363726561746f724f6e6c793a204f4e4c595f43524541544f525f414c4c4f5745,
                              mem[ceil32(_uri.length) + 249 len 11]
              uri[_id][] = Array(len=_uri.length, data=_uri[all])
              mem[ceil32(_uri.length) + 128] = 32
              mem[ceil32(_uri.length) + 192 len ceil32(_uri.length)] = _uri[all], mem[_uri.length + 128 len ceil32(_uri.length) - _uri.length]
              if not _uri.length % 32:
                  log 0x6bb7ff70: 0, 32, _uri.length, Mask(8 * _uri.length, -(8 * _uri.length) + 256, _uri[all], mem[_uri.length + 128 len ceil32(_uri.length) - _uri.length]) << (8 * _uri.length) - 256, _id
              else:
                  mem[floor32(_uri.length) + ceil32(_uri.length) + 192] = mem[floor32(_uri.length) + ceil32(_uri.length) + -(_uri.length % 32) + 224 len _uri.length % 32]
                  log 0x6bb7ff70: 0, 32, _uri.length, Mask(8 * ceil32(_uri.length), -(8 * ceil32(_uri.length)) + 256, _uri[all], mem[_uri.length + 128 len ceil32(_uri.length) - _uri.length]) << (8 * ceil32(_uri.length)) - 256, mem[(2 * ceil32(_uri.length)) + 192 len floor32(_uri.length) + -ceil32(_uri.length) + 32], _id

def safeBatchTransferFrom(address _from, address _to, uint256[] _ids, uint256[] _values, bytes _data) payable: 
  require calldata.size - 4 >= 160
  require _ids <= 4294967296
  require _ids + 36 <= calldata.size
  require _ids.length <= 4294967296 and _ids + (32 * _ids.length) + 36 <= calldata.size
  mem[128 len 32 * _ids.length] = call.data[_ids + 36 len 32 * _ids.length]
  require _values <= 4294967296
  require _values + 36 <= calldata.size
  require _values.length <= 4294967296 and _values + (32 * _values.length) + 36 <= calldata.size
  mem[(32 * _ids.length) + 128] = _values.length
  mem[(32 * _ids.length) + 160 len 32 * _values.length] = call.data[_values + 36 len 32 * _values.length]
  require _data <= 4294967296
  require _data + 36 <= calldata.size
  require _data.length <= 4294967296 and _data + _data.length + 36 <= calldata.size
  mem[(32 * _ids.length) + (32 * _values.length) + 160] = _data.length
  mem[(32 * _ids.length) + (32 * _values.length) + 192 len _data.length] = _data[all]
  mem[(32 * _ids.length) + (32 * _values.length) + _data.length + 192] = 0
  if caller == _from:
      if not _to:
          revert with 0, 
                      32,
                      48,
                      0x4845524331313535237361666542617463685472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                      mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 308 len 16]
      if _ids.length != _values.length:
          revert with 0, 
                      32,
                      53,
                      0x5245524331313535235f7361666542617463685472616e7366657246726f6d3a20494e56414c49445f4152524159535f4c454e4754,
                      mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 313 len 11]
      idx = 0
      while idx < _ids.length:
          require idx < _values.length
          require idx < _ids.length
          if mem[(32 * idx) + (32 * _ids.length) + 160] > stor0[addr(_from)][mem[(32 * idx) + 128]]:
              revert with 0, 'SafeMath#sub: UNDERFLOW'
          require idx < _ids.length
          stor0[addr(_from)][mem[(32 * idx) + 128]] -= mem[(32 * idx) + (32 * _ids.length) + 160]
          require idx < _values.length
          require idx < _ids.length
          if stor0[addr(_to)][mem[(32 * idx) + 128]] + mem[(32 * idx) + (32 * _ids.length) + 160] < stor0[addr(_to)][mem[(32 * idx) + 128]]:
              revert with 0, 'SafeMath#add: OVERFLOW'
          require idx < _ids.length
          mem[0] = mem[(32 * idx) + 128]
          mem[32] = sha3(addr(_to), 0)
          stor0[addr(_to)][mem[(32 * idx) + 128]] += mem[(32 * idx) + (32 * _ids.length) + 160]
          idx = idx + 1
          continue 
      mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 192] = 64
      mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 288 len floor32(_ids.length)] = call.data[_ids + 36 len floor32(_ids.length)]
      mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 224] = (32 * _ids.length) + 96
      mem[(64 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 288] = _values.length
      mem[(64 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 320 len floor32(_values.length)] = call.data[_values + 36 len floor32(_values.length)]
      log 0x4a39dc06: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[(32 * _ids.length) + (32 * _values.length) + _data.length + 224 len ceil32(_data.length) + -_data.length + 32], _ids.length, call.data[_ids + 36 len floor32(_ids.length)], mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + floor32(_ids.length) + 288 len (32 * _ids.length) + (32 * _values.length) + -floor32(_ids.length) + 32], caller, _from, _to
  else:
      if stor10[caller]:
          if not _to:
              revert with 0, 
                          32,
                          48,
                          0x4845524331313535237361666542617463685472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                          mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 308 len 16]
          if _ids.length != _values.length:
              revert with 0, 
                          32,
                          53,
                          0x5245524331313535235f7361666542617463685472616e7366657246726f6d3a20494e56414c49445f4152524159535f4c454e4754,
                          mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 313 len 11]
          idx = 0
          while idx < _ids.length:
              require idx < _values.length
              require idx < _ids.length
              if mem[(32 * idx) + (32 * _ids.length) + 160] > stor0[addr(_from)][mem[(32 * idx) + 128]]:
                  revert with 0, 'SafeMath#sub: UNDERFLOW'
              require idx < _ids.length
              stor0[addr(_from)][mem[(32 * idx) + 128]] -= mem[(32 * idx) + (32 * _ids.length) + 160]
              require idx < _values.length
              require idx < _ids.length
              if stor0[addr(_to)][mem[(32 * idx) + 128]] + mem[(32 * idx) + (32 * _ids.length) + 160] < stor0[addr(_to)][mem[(32 * idx) + 128]]:
                  revert with 0, 'SafeMath#add: OVERFLOW'
              require idx < _ids.length
              mem[0] = mem[(32 * idx) + 128]
              mem[32] = sha3(addr(_to), 0)
              stor0[addr(_to)][mem[(32 * idx) + 128]] += mem[(32 * idx) + (32 * _ids.length) + 160]
              idx = idx + 1
              continue 
          mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 192] = 64
          mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 288 len floor32(_ids.length)] = call.data[_ids + 36 len floor32(_ids.length)]
          mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 224] = (32 * _ids.length) + 96
          mem[(64 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 288] = _values.length
          mem[(64 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 320 len floor32(_values.length)] = call.data[_values + 36 len floor32(_values.length)]
          log 0x4a39dc06: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[(32 * _ids.length) + (32 * _values.length) + _data.length + 224 len ceil32(_data.length) + -_data.length + 32], _ids.length, call.data[_ids + 36 len floor32(_ids.length)], mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + floor32(_ids.length) + 288 len (32 * _ids.length) + (32 * _values.length) + -floor32(_ids.length) + 32], caller, _from, _to
      else:
          mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 196] = _from
          require ext_code.size(unknowncd7c0326Address)
          static call unknowncd7c0326Address.proxies(address param1) with:
                  gas gas_remaining wei
                 args _from
          mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 192] = ext_call.return_data[0]
          if not ext_call.success:
              revert with ext_call.return_data[0 len return_data.size]
          require return_data.size >= 32
          if ext_call.return_data[12 len 20] != caller:
              if not stor1[addr(_from)][caller]:
                  revert with 0, 
                              32,
                              47,
                              0x4845524331313535237361666542617463685472616e7366657246726f6d3a20494e56414c49445f4f50455241544f,
                              mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 307 len 17]
          if not _to:
              revert with 0, 
                          32,
                          48,
                          0x4845524331313535237361666542617463685472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                          mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 308 len 16]
          if _ids.length != _values.length:
              revert with 0, 
                          32,
                          53,
                          0x5245524331313535235f7361666542617463685472616e7366657246726f6d3a20494e56414c49445f4152524159535f4c454e4754,
                          mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 313 len 11]
          idx = 0
          while idx < _ids.length:
              require idx < _values.length
              require idx < _ids.length
              if mem[(32 * idx) + (32 * _ids.length) + 160] > stor0[addr(_from)][mem[(32 * idx) + 128]]:
                  revert with 0, 'SafeMath#sub: UNDERFLOW'
              require idx < _ids.length
              stor0[addr(_from)][mem[(32 * idx) + 128]] -= mem[(32 * idx) + (32 * _ids.length) + 160]
              require idx < _values.length
              require idx < _ids.length
              if stor0[addr(_to)][mem[(32 * idx) + 128]] + mem[(32 * idx) + (32 * _ids.length) + 160] < stor0[addr(_to)][mem[(32 * idx) + 128]]:
                  revert with 0, 'SafeMath#add: OVERFLOW'
              require idx < _ids.length
              mem[0] = mem[(32 * idx) + 128]
              mem[32] = sha3(addr(_to), 0)
              stor0[addr(_to)][mem[(32 * idx) + 128]] += mem[(32 * idx) + (32 * _ids.length) + 160]
              idx = idx + 1
              continue 
          mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 288 len floor32(_ids.length)] = call.data[_ids + 36 len floor32(_ids.length)]
          mem[(64 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 288] = _values.length
          mem[(64 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 320 len floor32(_values.length)] = call.data[_values + 36 len floor32(_values.length)]
          log 0x4a39dc06: 0, 64, (32 * _ids.length) + 96, _ids.length, call.data[_ids + 36 len floor32(_ids.length)], mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + floor32(_ids.length) + 288 len (32 * _ids.length) + (32 * _values.length) + -floor32(_ids.length) + 32], caller, _from, _to
  if ext_code.hash(_to):
      if ext_code.hash(_to) != 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
          mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 192] = 0xbc197c8100000000000000000000000000000000000000000000000000000000
          mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 388 len floor32(_ids.length)] = call.data[_ids + 36 len floor32(_ids.length)]
          mem[(64 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 388] = _values.length
          mem[(64 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 420 len floor32(_values.length)] = call.data[_values + 36 len floor32(_values.length)]
          mem[(64 * _values.length) + (64 * _ids.length) + ceil32(_data.length) + 420] = _data.length
          mem[(64 * _values.length) + (64 * _ids.length) + ceil32(_data.length) + 452 len ceil32(_data.length)] = _data[all], mem[(32 * _ids.length) + (32 * _values.length) + _data.length + 192 len ceil32(_data.length) - _data.length]
          if not _data.length % 32:
              require ext_code.size(_to)
              call _to with:
                   gas gas_remaining wei
                  args caller, addr(_from), Array(len=_ids.length, data=call.data[_ids + 36 len floor32(_ids.length)], mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + floor32(_ids.length) + 388 len (32 * _ids.length) + (32 * _values.length) + _data.length + -floor32(_ids.length) + 64]), (32 * _ids.length) + 192, (32 * _values.length) + (32 * _ids.length) + 224
          else:
              mem[floor32(_data.length) + (64 * _values.length) + (64 * _ids.length) + ceil32(_data.length) + 452] = mem[floor32(_data.length) + (64 * _values.length) + (64 * _ids.length) + ceil32(_data.length) + -(_data.length % 32) + 484 len _data.length % 32]
              require ext_code.size(_to)
              call _to with:
                   gas gas_remaining wei
                  args caller, addr(_from), Array(len=_ids.length, data=call.data[_ids + 36 len floor32(_ids.length)], mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + floor32(_ids.length) + 388 len (32 * _ids.length) + (32 * _values.length) + floor32(_data.length) + -floor32(_ids.length) + 96]), (32 * _ids.length) + 192, (32 * _values.length) + (32 * _ids.length) + 224
          if not ext_call.success:
              revert with ext_call.return_data[0 len return_data.size]
          require return_data.size >= 32
          if Mask(32, 224, ext_call.return_data[0]) != 0xbc197c8100000000000000000000000000000000000000000000000000000000:
              revert with 0, 
                          32,
                          63,
                          0x5245524331313535235f63616c6c6f6e45524331313535426174636852656365697665643a20494e56414c49445f4f4e5f524543454956455f4d4553534147,
                          uint8((32 * _ids.length) + 192)

def unknownb48ab8b6(addr _param1, array _param2, array _param3, array _param4) payable: 
  require calldata.size - 4 >= 128
  require _param2 <= 4294967296
  require _param2 + 36 <= calldata.size
  require _param2.length <= 4294967296 and _param2 + (32 * _param2.length) + 36 <= calldata.size
  mem[96] = _param2.length
  mem[128 len 32 * _param2.length] = call.data[_param2 + 36 len 32 * _param2.length]
  require _param3 <= 4294967296
  require _param3 + 36 <= calldata.size
  require _param3.length <= 4294967296 and _param3 + (32 * _param3.length) + 36 <= calldata.size
  mem[(32 * _param2.length) + 128] = _param3.length
  mem[(32 * _param2.length) + 160 len 32 * _param3.length] = call.data[_param3 + 36 len 32 * _param3.length]
  require _param4 <= 4294967296
  require _param4 + 36 <= calldata.size
  require _param4.length <= 4294967296 and _param4 + _param4.length + 36 <= calldata.size
  mem[64] = (32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 192
  mem[(32 * _param2.length) + (32 * _param3.length) + 160] = _param4.length
  mem[(32 * _param2.length) + (32 * _param3.length) + 192 len _param4.length] = _param4[all]
  mem[(32 * _param2.length) + (32 * _param3.length) + _param4.length + 192] = 0
  if not stor9:
      revert with 0, 'ReentrancyGuard: reentrant call'
  stor9 = 0
  idx = 0
  while idx < _param2.length:
      require idx < _param2.length
      _240 = mem[(32 * idx) + 128]
      require idx < _param3.length
      _243 = mem[(32 * idx) + (32 * _param2.length) + 160]
      if not creator[mem[(32 * idx) + 128]]:
          if mem[(32 * idx) + 140 len 8] == caller:
              mem[0] = mem[(32 * idx) + 128]
              mem[32] = 6
              if totalSupply[mem[(32 * idx) + 128]] > mem[(32 * idx) + 155 len 5]:
                  revert with 0, 'SafeMath#sub: UNDERFLOW'
              if mem[(32 * idx) + 155 len 5] - totalSupply[mem[(32 * idx) + 128]] < mem[(32 * idx) + (32 * _param2.length) + 160]:
                  revert with 0, 
                              32,
                              53,
                              0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a20535550504c595f45584345454445,
                              mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 313 len 11]
          else:
              if stor10[caller]:
                  mem[0] = mem[(32 * idx) + 128]
                  mem[32] = 6
                  if totalSupply[mem[(32 * idx) + 128]] > mem[(32 * idx) + 155 len 5]:
                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                  if mem[(32 * idx) + 155 len 5] - totalSupply[mem[(32 * idx) + 128]] < mem[(32 * idx) + (32 * _param2.length) + 160]:
                      revert with 0, 
                                  32,
                                  53,
                                  0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a20535550504c595f45584345454445,
                                  mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 313 len 11]
              else:
                  mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 196] = mem[(32 * idx) + 140 len 8]
                  require ext_code.size(unknowncd7c0326Address)
                  static call unknowncd7c0326Address.proxies(address param1) with:
                          gas gas_remaining wei
                         args (Mask(64, 96, _240) >> 96)
                  mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 192] = ext_call.return_data[0]
                  if not ext_call.success:
                      revert with ext_call.return_data[0 len return_data.size]
                  require return_data.size >= 32
                  if addr(ext_call.return_data) != caller:
                      revert with 0, 
                                  32,
                                  58,
                                  0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a204f4e4c595f43524541544f525f414c4c4f5745,
                                  mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 318 len 6]
                  mem[0] = _240
                  mem[32] = 6
                  if totalSupply[_240] > _240 % 1099511627776:
                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                  if (_240 % 1099511627776) - totalSupply[_240] < _243:
                      revert with 0, 
                                  32,
                                  53,
                                  0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a20535550504c595f45584345454445,
                                  mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 313 len 11]
      else:
          if creator[mem[(32 * idx) + 128]] == caller:
              mem[0] = mem[(32 * idx) + 128]
              mem[32] = 6
              if totalSupply[mem[(32 * idx) + 128]] > mem[(32 * idx) + 155 len 5]:
                  revert with 0, 'SafeMath#sub: UNDERFLOW'
              if mem[(32 * idx) + 155 len 5] - totalSupply[mem[(32 * idx) + 128]] < mem[(32 * idx) + (32 * _param2.length) + 160]:
                  revert with 0, 
                              32,
                              53,
                              0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a20535550504c595f45584345454445,
                              mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 313 len 11]
          else:
              _246 = sha3(mem[(32 * idx) + 128], 11)
              if stor10[caller]:
                  mem[0] = mem[(32 * idx) + 128]
                  mem[32] = 6
                  if totalSupply[mem[(32 * idx) + 128]] > mem[(32 * idx) + 155 len 5]:
                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                  if mem[(32 * idx) + 155 len 5] - totalSupply[mem[(32 * idx) + 128]] < mem[(32 * idx) + (32 * _param2.length) + 160]:
                      revert with 0, 
                                  32,
                                  53,
                                  0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a20535550504c595f45584345454445,
                                  mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 313 len 11]
              else:
                  mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 196] = creator[mem[(32 * idx) + 128]]
                  require ext_code.size(unknowncd7c0326Address)
                  static call unknowncd7c0326Address.proxies(address param1) with:
                          gas gas_remaining wei
                         args addr(stor[_246])
                  mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 192] = ext_call.return_data[0]
                  if not ext_call.success:
                      revert with ext_call.return_data[0 len return_data.size]
                  require return_data.size >= 32
                  if addr(ext_call.return_data) != caller:
                      revert with 0, 
                                  32,
                                  58,
                                  0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a204f4e4c595f43524541544f525f414c4c4f5745,
                                  mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 318 len 6]
                  mem[0] = _240
                  mem[32] = 6
                  if totalSupply[_240] > _240 % 1099511627776:
                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                  if (_240 % 1099511627776) - totalSupply[_240] < _243:
                      revert with 0, 
                                  32,
                                  53,
                                  0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a20535550504c595f45584345454445,
                                  mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 313 len 11]
      idx = idx + 1
      continue 
  if _param2.length != _param3.length:
      revert with 0, 
                  32,
                  48,
                  0x48455243313135355472616461626c652362617463684d696e743a20494e56414c49445f4152524159535f4c454e4754,
                  mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 308 len 16]
  require 0 < _param2.length
  idx = 0
  while idx < _param2.length:
      require idx < _param2.length
      if mem[(32 * idx) + 140 len 8] != mem[140 len 8]:
          revert with 0, 
                      32,
                      55,
                      0x52455243313135355472616461626c652362617463684d696e743a204d554c5449504c455f4f524947494e535f4e4f545f414c4c4f5745,
                      mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 315 len 9]
      require idx < _param3.length
      if stor0[addr(_param1)][mem[(32 * idx) + 128]] + mem[(32 * idx) + (32 * _param2.length) + 160] < stor0[addr(_param1)][mem[(32 * idx) + 128]]:
          revert with 0, 'SafeMath#add: OVERFLOW'
      stor0[addr(_param1)][mem[(32 * idx) + 128]] += mem[(32 * idx) + (32 * _param2.length) + 160]
      require idx < _param3.length
      if totalSupply[mem[(32 * idx) + 128]] + mem[(32 * idx) + (32 * _param2.length) + 160] < totalSupply[mem[(32 * idx) + 128]]:
          revert with 0, 'SafeMath#add: OVERFLOW'
      mem[0] = mem[(32 * idx) + 128]
      mem[32] = 6
      totalSupply[mem[(32 * idx) + 128]] += mem[(32 * idx) + (32 * _param2.length) + 160]
      idx = idx + 1
      continue 
  mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 192] = 64
  mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 256] = _param2.length
  mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 288 len floor32(_param2.length)] = call.data[_param2 + 36 len floor32(_param2.length)]
  mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 224] = (32 * _param2.length) + 96
  mem[(64 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 288] = _param3.length
  mem[(64 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 320 len floor32(_param3.length)] = call.data[_param3 + 36 len floor32(_param3.length)]
  log 0x4a39dc06: Array(len=_param2.length, data=call.data[_param2 + 36 len floor32(_param2.length)], mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + floor32(_param2.length) + 288 len (32 * _param2.length) + (32 * _param3.length) + -floor32(_param2.length) + 32]), (32 * _param2.length) + 96, caller, mem1
  if not ext_code.hash(_param1):
      if _param4.length > 1:
          idx = 0
          while idx < _param2.length:
              require idx < mem[96]
              _921 = mem[(32 * idx) + 128]
              mem[32] = 8
              mem[0] = sha3(mem[(32 * idx) + 128], 8)
              uri[mem[(32 * idx) + 128]] = (2 * mem[(32 * _param2.length) + (32 * _param3.length) + 160]) + 1
              t = sha3(sha3(mem[(32 * idx) + 128], 8))
              s = (32 * _param2.length) + (32 * _param3.length) + 192
              while (32 * _param2.length) + (32 * _param3.length) + mem[(32 * _param2.length) + (32 * _param3.length) + 160] + 192 > s:
                  uint256(stor[t]) = mem[s]
                  t = t + 1
                  s = s + 32
                  continue 
              s = sha3(sha3(mem[(32 * idx) + 128], 8)) + (Mask(251, 0, mem[(32 * _param2.length) + (32 * _param3.length) + 160] + 31) >> 5)
              while sha3(sha3(mem[(32 * idx) + 128], 8)) + (uri[mem[(32 * idx) + 128]].length + 31 / 32) > s:
                  uint256(stor[s]) = 0
                  s = s + 1
                  continue 
              _1189 = mem[64]
              mem[mem[64]] = 32
              mem[mem[64] + 32] = mem[(32 * _param2.length) + (32 * _param3.length) + 160]
              _1191 = mem[(32 * _param2.length) + (32 * _param3.length) + 160]
              s = 0
              while s < _1191:
                  mem[_1189 + s + 64] = mem[(32 * _param2.length) + (32 * _param3.length) + s + 192]
                  s = s + 32
                  continue 
              if not _1191 % 32:
                  log 0x6bb7ff70: mem[memem
              else:
                  mem[floor32(_1191) + _1189 + 64] = mem[floor32(_1191) + _1189 + -(_1191 % 32) + 96 len _1191 % 32]
                  log 0x6bb7ff70: mem[memem
              idx = idx + 1
              continue 
  else:
      if ext_code.hash(_param1) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
          if _param4.length > 1:
              idx = 0
              while idx < _param2.length:
                  require idx < mem[96]
                  _922 = mem[(32 * idx) + 128]
                  mem[32] = 8
                  mem[0] = sha3(mem[(32 * idx) + 128], 8)
                  uri[mem[(32 * idx) + 128]] = (2 * mem[(32 * _param2.length) + (32 * _param3.length) + 160]) + 1
                  t = sha3(sha3(mem[(32 * idx) + 128], 8))
                  s = (32 * _param2.length) + (32 * _param3.length) + 192
                  while (32 * _param2.length) + (32 * _param3.length) + mem[(32 * _param2.length) + (32 * _param3.length) + 160] + 192 > s:
                      uint256(stor[t]) = mem[s]
                      t = t + 1
                      s = s + 32
                      continue 
                  s = sha3(sha3(mem[(32 * idx) + 128], 8)) + (Mask(251, 0, mem[(32 * _param2.length) + (32 * _param3.length) + 160] + 31) >> 5)
                  while sha3(sha3(mem[(32 * idx) + 128], 8)) + (uri[mem[(32 * idx) + 128]].length + 31 / 32) > s:
                      uint256(stor[s]) = 0
                      s = s + 1
                      continue 
                  _1192 = mem[64]
                  mem[mem[64]] = 32
                  mem[mem[64] + 32] = mem[(32 * _param2.length) + (32 * _param3.length) + 160]
                  _1194 = mem[(32 * _param2.length) + (32 * _param3.length) + 160]
                  s = 0
                  while s < _1194:
                      mem[_1192 + s + 64] = mem[(32 * _param2.length) + (32 * _param3.length) + s + 192]
                      s = s + 32
                      continue 
                  if not _1194 % 32:
                      log 0x6bb7ff70: mem[memem
                  else:
                      mem[floor32(_1194) + _1192 + 64] = mem[floor32(_1194) + _1192 + -(_1194 % 32) + 96 len _1194 % 32]
                      log 0x6bb7ff70: mem[memem
                  idx = idx + 1
                  continue 
      else:
          mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 192] = 0xbc197c8100000000000000000000000000000000000000000000000000000000
          mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 196] = caller
          mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 228] = mem[140 len 8]
          mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 260] = 160
          mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 356] = _param2.length
          mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 388 len floor32(_param2.length)] = call.data[_param2 + 36 len floor32(_param2.length)]
          mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 292] = (32 * _param2.length) + 192
          mem[(64 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 388] = _param3.length
          mem[(64 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 420 len floor32(_param3.length)] = call.data[_param3 + 36 len floor32(_param3.length)]
          mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 324] = (32 * _param3.length) + (32 * _param2.length) + 224
          mem[(64 * _param3.length) + (64 * _param2.length) + ceil32(_param4.length) + 420] = _param4.length
          mem[(64 * _param3.length) + (64 * _param2.length) + ceil32(_param4.length) + 452 len ceil32(_param4.length)] = _param4[all], mem[(32 * _param2.length) + (32 * _param3.length) + _param4.length + 192 len ceil32(_param4.length) - _param4.length]
          if not _param4.length % 32:
              require ext_code.size(_param1)
              call _param1.onERC1155BatchReceived(address param1, address param2, uint256[] param3, uint256[] param4, bytes param5) with:
                   gas gas_remaining wei
                  args caller, mem[140 len 8], Array(len=_param2.length, data=call.data[_param2 + 36 len floor32(_param2.length)], mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + floor32(_param2.length) + 388 len (32 * _param2.length) + (32 * _param3.length) + _param4.length + -floor32(_param2.length) + 64]), (32 * _param2.length) + 192, (32 * _param3.length) + (32 * _param2.length) + 224
              mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 192] = ext_call.return_data[0]
              if not ext_call.success:
                  revert with ext_call.return_data[0 len return_data.size]
              require return_data.size >= 32
              if Mask(32, 224, ext_call.return_data[0]) != 0xbc197c8100000000000000000000000000000000000000000000000000000000:
                  revert with 0, 
                              32,
                              63,
                              0x5245524331313535235f63616c6c6f6e45524331313535426174636852656365697665643a20494e56414c49445f4f4e5f524543454956455f4d4553534147,
                              uint8((32 * _param2.length) + 192)
              if _param4.length > 1:
                  idx = 0
                  while idx < _param2.length:
                      require idx < mem[96]
                      _1281 = mem[(32 * idx) + 128]
                      mem[32] = 8
                      mem[0] = sha3(mem[(32 * idx) + 128], 8)
                      uri[mem[(32 * idx) + 128]] = (2 * mem[(32 * _param2.length) + (32 * _param3.length) + 160]) + 1
                      t = sha3(sha3(mem[(32 * idx) + 128], 8))
                      s = (32 * _param2.length) + (32 * _param3.length) + 192
                      while (32 * _param2.length) + (32 * _param3.length) + mem[(32 * _param2.length) + (32 * _param3.length) + 160] + 192 > s:
                          uint256(stor[t]) = mem[s]
                          t = t + 1
                          s = s + 32
                          continue 
                      s = sha3(sha3(mem[(32 * idx) + 128], 8)) + (Mask(251, 0, mem[(32 * _param2.length) + (32 * _param3.length) + 160] + 31) >> 5)
                      while sha3(sha3(mem[(32 * idx) + 128], 8)) + (uri[mem[(32 * idx) + 128]].length + 31 / 32) > s:
                          uint256(stor[s]) = 0
                          s = s + 1
                          continue 
                      _1397 = mem[64]
                      mem[mem[64]] = 32
                      mem[mem[64] + 32] = mem[(32 * _param2.length) + (32 * _param3.length) + 160]
                      _1399 = mem[(32 * _param2.length) + (32 * _param3.length) + 160]
                      s = 0
                      while s < _1399:
                          mem[_1397 + s + 64] = mem[(32 * _param2.length) + (32 * _param3.length) + s + 192]
                          s = s + 32
                          continue 
                      if not _1399 % 32:
                          log 0x6bb7ff70: mem[memem
                      else:
                          mem[floor32(_1399) + _1397 + 64] = mem[floor32(_1399) + _1397 + -(_1399 % 32) + 96 len _1399 % 32]
                          log 0x6bb7ff70: mem[memem
                      idx = idx + 1
                      continue 
          else:
              mem[floor32(_param4.length) + (64 * _param3.length) + (64 * _param2.length) + ceil32(_param4.length) + 452] = mem[floor32(_param4.length) + (64 * _param3.length) + (64 * _param2.length) + ceil32(_param4.length) + -(_param4.length % 32) + 484 len _param4.length % 32]
              require ext_code.size(_param1)
              call _param1.onERC1155BatchReceived(address param1, address param2, uint256[] param3, uint256[] param4, bytes param5) with:
                   gas gas_remaining wei
                  args caller, mem[140 len 8], Array(len=_param2.length, data=call.data[_param2 + 36 len floor32(_param2.length)], mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + floor32(_param2.length) + 388 len (32 * _param2.length) + (32 * _param3.length) + floor32(_param4.length) + -floor32(_param2.length) + 96]), (32 * _param2.length) + 192, (32 * _param3.length) + (32 * _param2.length) + 224
              mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 192] = ext_call.return_data[0]
              if not ext_call.success:
                  revert with ext_call.return_data[0 len return_data.size]
              require return_data.size >= 32
              if Mask(32, 224, ext_call.return_data[0]) != 0xbc197c8100000000000000000000000000000000000000000000000000000000:
                  revert with 0, 
                              32,
                              63,
                              0x5245524331313535235f63616c6c6f6e45524331313535426174636852656365697665643a20494e56414c49445f4f4e5f524543454956455f4d4553534147,
                              uint8((32 * _param2.length) + 192)
              if _param4.length > 1:
                  idx = 0
                  while idx < _param2.length:
                      require idx < mem[96]
                      _1282 = mem[(32 * idx) + 128]
                      mem[32] = 8
                      mem[0] = sha3(mem[(32 * idx) + 128], 8)
                      uri[mem[(32 * idx) + 128]] = (2 * mem[(32 * _param2.length) + (32 * _param3.length) + 160]) + 1
                      t = sha3(sha3(mem[(32 * idx) + 128], 8))
                      s = (32 * _param2.length) + (32 * _param3.length) + 192
                      while (32 * _param2.length) + (32 * _param3.length) + mem[(32 * _param2.length) + (32 * _param3.length) + 160] + 192 > s:
                          uint256(stor[t]) = mem[s]
                          t = t + 1
                          s = s + 32
                          continue 
                      s = sha3(sha3(mem[(32 * idx) + 128], 8)) + (Mask(251, 0, mem[(32 * _param2.length) + (32 * _param3.length) + 160] + 31) >> 5)
                      while sha3(sha3(mem[(32 * idx) + 128], 8)) + (uri[mem[(32 * idx) + 128]].length + 31 / 32) > s:
                          uint256(stor[s]) = 0
                          s = s + 1
                          continue 
                      _1400 = mem[64]
                      mem[mem[64]] = 32
                      mem[mem[64] + 32] = mem[(32 * _param2.length) + (32 * _param3.length) + 160]
                      _1402 = mem[(32 * _param2.length) + (32 * _param3.length) + 160]
                      s = 0
                      while s < _1402:
                          mem[_1400 + s + 64] = mem[(32 * _param2.length) + (32 * _param3.length) + s + 192]
                          s = s + 32
                          continue 
                      if not _1402 % 32:
                          log 0x6bb7ff70: mem[memem
                      else:
                          mem[floor32(_1402) + _1400 + 64] = mem[floor32(_1402) + _1400 + -(_1402 % 32) + 96 len _1402 % 32]
                          log 0x6bb7ff70: mem[memem
                      idx = idx + 1
                      continue 
  stor9 = 1

def unknown731133e9(addr _param1, uint256 _param2, uint256 _param3, array _param4) payable: 
  require calldata.size - 4 >= 128
  require _param4 <= 4294967296
  require _param4 + 36 <= calldata.size
  require _param4.length <= 4294967296 and _param4 + _param4.length + 36 <= calldata.size
  mem[128 len _param4.length] = _param4[all]
  mem[_param4.length + 128] = 0
  if not stor9:
      revert with 0, 'ReentrancyGuard: reentrant call'
  stor9 = 0
  if not creator[_param2]:
      if uint64(_param2) == caller:
          if totalSupply[_param2] > _param2 % 1099511627776:
              revert with 0, 'SafeMath#sub: UNDERFLOW'
          if (_param2 % 1099511627776) - totalSupply[_param2] < _param3:
              revert with 0, 
                          32,
                          53,
                          0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a20535550504c595f45584345454445,
                          mem[ceil32(_param4.length) + 249 len 11]
          if stor0[addr(_param1)][_param2] + _param3 < stor0[addr(_param1)][_param2]:
              revert with 0, 'SafeMath#add: OVERFLOW'
          stor0[addr(_param1)][_param2] += _param3
          if totalSupply[_param2] + _param3 < totalSupply[_param2]:
              revert with 0, 'SafeMath#add: OVERFLOW'
          totalSupply[_param2] += _param3
          mem[ceil32(_param4.length) + 128] = _param2
          mem[ceil32(_param4.length) + 160] = _param3
          log 0xc3d58168: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len -_param4.length + ceil32(_param4.length) + 32], caller, uint64(_param2), _param1
          if not ext_code.hash(_param1):
              if _param4.length > 1:
                  uri[_param2][] = Array(len=_param4.length, data=_param4[all])
                  mem[ceil32(_param4.length) + 128] = 32
                  mem[ceil32(_param4.length) + 160] = _param4.length
                  mem[ceil32(_param4.length) + 192 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                  if not _param4.length % 32:
                      log 0x6bb7ff70: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len ceil32(_param4.length) + -_param4.length + 32], Mask(8 * _param4.length, -(8 * _param4.length) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * _param4.length) - 256, _param2
                  else:
                      mem[floor32(_param4.length) + ceil32(_param4.length) + 192] = mem[floor32(_param4.length) + ceil32(_param4.length) + -(_param4.length % 32) + 224 len _param4.length % 32]
                      log 0x6bb7ff70: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len ceil32(_param4.length) + -_param4.length + 32], Mask(8 * ceil32(_param4.length), -(8 * ceil32(_param4.length)) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * ceil32(_param4.length)) - 256, mem[(2 * ceil32(_param4.length)) + 192 len floor32(_param4.length) + -ceil32(_param4.length) + 32], _param2
          else:
              if ext_code.hash(_param1) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                  if _param4.length > 1:
                      uri[_param2][] = Array(len=_param4.length, data=_param4[all])
                      mem[ceil32(_param4.length) + 128] = 32
                      mem[ceil32(_param4.length) + 160] = _param4.length
                      mem[ceil32(_param4.length) + 192 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                      if not _param4.length % 32:
                          log 0x6bb7ff70: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len ceil32(_param4.length) + -_param4.length + 32], Mask(8 * _param4.length, -(8 * _param4.length) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * _param4.length) - 256, _param2
                      else:
                          mem[floor32(_param4.length) + ceil32(_param4.length) + 192] = mem[floor32(_param4.length) + ceil32(_param4.length) + -(_param4.length % 32) + 224 len _param4.length % 32]
                          log 0x6bb7ff70: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len ceil32(_param4.length) + -_param4.length + 32], Mask(8 * ceil32(_param4.length), -(8 * ceil32(_param4.length)) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * ceil32(_param4.length)) - 256, mem[(2 * ceil32(_param4.length)) + 192 len floor32(_param4.length) + -ceil32(_param4.length) + 32], _param2
              else:
                  mem[ceil32(_param4.length) + 128] = 0xf23a6e6100000000000000000000000000000000000000000000000000000000
                  mem[ceil32(_param4.length) + 196] = _param2
                  mem[ceil32(_param4.length) + 228] = _param3
                  mem[ceil32(_param4.length) + 260] = 160
                  mem[ceil32(_param4.length) + 292] = _param4.length
                  mem[ceil32(_param4.length) + 324 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                  require ext_code.size(_param1)
                  call _param1 with:
                       gas gas_remaining wei
                      args caller, _param2 << 192, _param2, _param3, Array(len=_param4.length, data=_param4[all])
                  if not ext_call.success:
                      revert with ext_call.return_data[0 len return_data.size]
                  require return_data.size >= 32
                  if Mask(32, 224, ext_call.return_data[0]) != 0xf23a6e6100000000000000000000000000000000000000000000000000000000:
                      revert with 0, 
                                  32,
                                  58,
                                  0x4545524331313535235f63616c6c6f6e4552433131353552656365697665643a20494e56414c49445f4f4e5f524543454956455f4d4553534147,
                                  _param3 % 281474976710656
                  if _param4.length > 1:
                      uri[_param2][] = Array(len=_param4.length, data=_param4[all])
                      mem[ceil32(_param4.length) + 128] = 32
                      mem[ceil32(_param4.length) + 192 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                      if not _param4.length % 32:
                          log 0x6bb7ff70: 0, 32, _param4.length, Mask(8 * _param4.length, -(8 * _param4.length) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * _param4.length) - 256, _param2
                      else:
                          mem[floor32(_param4.length) + ceil32(_param4.length) + 192] = mem[floor32(_param4.length) + ceil32(_param4.length) + -(_param4.length % 32) + 224 len _param4.length % 32]
                          log 0x6bb7ff70: 0, 32, _param4.length, Mask(8 * ceil32(_param4.length), -(8 * ceil32(_param4.length)) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * ceil32(_param4.length)) - 256, mem[(2 * ceil32(_param4.length)) + 192 len floor32(_param4.length) + -ceil32(_param4.length) + 32], _param2
      else:
          if stor10[caller]:
              if totalSupply[_param2] > _param2 % 1099511627776:
                  revert with 0, 'SafeMath#sub: UNDERFLOW'
              if (_param2 % 1099511627776) - totalSupply[_param2] < _param3:
                  revert with 0, 
                              32,
                              53,
                              0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a20535550504c595f45584345454445,
                              mem[ceil32(_param4.length) + 249 len 11]
              if stor0[addr(_param1)][_param2] + _param3 < stor0[addr(_param1)][_param2]:
                  revert with 0, 'SafeMath#add: OVERFLOW'
              stor0[addr(_param1)][_param2] += _param3
              if totalSupply[_param2] + _param3 < totalSupply[_param2]:
                  revert with 0, 'SafeMath#add: OVERFLOW'
              totalSupply[_param2] += _param3
              mem[ceil32(_param4.length) + 128] = _param2
              mem[ceil32(_param4.length) + 160] = _param3
              log 0xc3d58168: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len -_param4.length + ceil32(_param4.length) + 32], caller, uint64(_param2), _param1
              if not ext_code.hash(_param1):
                  if _param4.length > 1:
                      uri[_param2][] = Array(len=_param4.length, data=_param4[all])
                      mem[ceil32(_param4.length) + 128] = 32
                      mem[ceil32(_param4.length) + 160] = _param4.length
                      mem[ceil32(_param4.length) + 192 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                      if not _param4.length % 32:
                          log 0x6bb7ff70: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len ceil32(_param4.length) + -_param4.length + 32], Mask(8 * _param4.length, -(8 * _param4.length) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * _param4.length) - 256, _param2
                      else:
                          mem[floor32(_param4.length) + ceil32(_param4.length) + 192] = mem[floor32(_param4.length) + ceil32(_param4.length) + -(_param4.length % 32) + 224 len _param4.length % 32]
                          log 0x6bb7ff70: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len ceil32(_param4.length) + -_param4.length + 32], Mask(8 * ceil32(_param4.length), -(8 * ceil32(_param4.length)) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * ceil32(_param4.length)) - 256, mem[(2 * ceil32(_param4.length)) + 192 len floor32(_param4.length) + -ceil32(_param4.length) + 32], _param2
              else:
                  if ext_code.hash(_param1) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                      if _param4.length > 1:
                          uri[_param2][] = Array(len=_param4.length, data=_param4[all])
                          mem[ceil32(_param4.length) + 128] = 32
                          mem[ceil32(_param4.length) + 160] = _param4.length
                          mem[ceil32(_param4.length) + 192 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                          if not _param4.length % 32:
                              log 0x6bb7ff70: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len ceil32(_param4.length) + -_param4.length + 32], Mask(8 * _param4.length, -(8 * _param4.length) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * _param4.length) - 256, _param2
                          else:
                              mem[floor32(_param4.length) + ceil32(_param4.length) + 192] = mem[floor32(_param4.length) + ceil32(_param4.length) + -(_param4.length % 32) + 224 len _param4.length % 32]
                              log 0x6bb7ff70: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len ceil32(_param4.length) + -_param4.length + 32], Mask(8 * ceil32(_param4.length), -(8 * ceil32(_param4.length)) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * ceil32(_param4.length)) - 256, mem[(2 * ceil32(_param4.length)) + 192 len floor32(_param4.length) + -ceil32(_param4.length) + 32], _param2
                  else:
                      mem[ceil32(_param4.length) + 128] = 0xf23a6e6100000000000000000000000000000000000000000000000000000000
                      mem[ceil32(_param4.length) + 196] = _param2
                      mem[ceil32(_param4.length) + 228] = _param3
                      mem[ceil32(_param4.length) + 260] = 160
                      mem[ceil32(_param4.length) + 292] = _param4.length
                      mem[ceil32(_param4.length) + 324 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                      require ext_code.size(_param1)
                      call _param1 with:
                           gas gas_remaining wei
                          args caller, _param2 << 192, _param2, _param3, Array(len=_param4.length, data=_param4[all])
                      if not ext_call.success:
                          revert with ext_call.return_data[0 len return_data.size]
                      require return_data.size >= 32
                      if Mask(32, 224, ext_call.return_data[0]) != 0xf23a6e6100000000000000000000000000000000000000000000000000000000:
                          revert with 0, 
                                      32,
                                      58,
                                      0x4545524331313535235f63616c6c6f6e4552433131353552656365697665643a20494e56414c49445f4f4e5f524543454956455f4d4553534147,
                                      _param3 % 281474976710656
                      if _param4.length > 1:
                          uri[_param2][] = Array(len=_param4.length, data=_param4[all])
                          mem[ceil32(_param4.length) + 128] = 32
                          mem[ceil32(_param4.length) + 192 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                          if not _param4.length % 32:
                              log 0x6bb7ff70: 0, 32, _param4.length, Mask(8 * _param4.length, -(8 * _param4.length) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * _param4.length) - 256, _param2
                          else:
                              mem[floor32(_param4.length) + ceil32(_param4.length) + 192] = mem[floor32(_param4.length) + ceil32(_param4.length) + -(_param4.length % 32) + 224 len _param4.length % 32]
                              log 0x6bb7ff70: 0, 32, _param4.length, Mask(8 * ceil32(_param4.length), -(8 * ceil32(_param4.length)) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * ceil32(_param4.length)) - 256, mem[(2 * ceil32(_param4.length)) + 192 len floor32(_param4.length) + -ceil32(_param4.length) + 32], _param2
          else:
              require ext_code.size(unknowncd7c0326Address)
              static call unknowncd7c0326Address.proxies(address param1) with:
                      gas gas_remaining wei
                     args uint64(_param2)
              if not ext_call.success:
                  revert with ext_call.return_data[0 len return_data.size]
              require return_data.size >= 32
              if ext_call.return_data[12 len 20] != caller:
                  revert with 0, 
                              32,
                              58,
                              0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a204f4e4c595f43524541544f525f414c4c4f5745,
                              mem[ceil32(_param4.length) + 254 len 6]
              if totalSupply[_param2] > _param2 % 1099511627776:
                  revert with 0, 'SafeMath#sub: UNDERFLOW'
              if (_param2 % 1099511627776) - totalSupply[_param2] < _param3:
                  revert with 0, 
                              32,
                              53,
                              0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a20535550504c595f45584345454445,
                              mem[ceil32(_param4.length) + 249 len 11]
              if stor0[addr(_param1)][_param2] + _param3 < stor0[addr(_param1)][_param2]:
                  revert with 0, 'SafeMath#add: OVERFLOW'
              stor0[addr(_param1)][_param2] += _param3
              if totalSupply[_param2] + _param3 < totalSupply[_param2]:
                  revert with 0, 'SafeMath#add: OVERFLOW'
              totalSupply[_param2] += _param3
              log 0xc3d58168: 0, Mask(224, 0, _param2), _param3, caller, uint64(_param2), _param1
              if ext_code.hash(_param1):
                  if ext_code.hash(_param1) != 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                      mem[ceil32(_param4.length) + 128] = 0xf23a6e6100000000000000000000000000000000000000000000000000000000
                      mem[ceil32(_param4.length) + 196] = _param2
                      mem[ceil32(_param4.length) + 228] = _param3
                      mem[ceil32(_param4.length) + 260] = 160
                      mem[ceil32(_param4.length) + 292] = _param4.length
                      mem[ceil32(_param4.length) + 324 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                      require ext_code.size(_param1)
                      call _param1 with:
                           gas gas_remaining wei
                          args caller, _param2 << 192, _param2, _param3, Array(len=_param4.length, data=_param4[all])
                      if not ext_call.success:
                          revert with ext_call.return_data[0 len return_data.size]
                      require return_data.size >= 32
                      if Mask(32, 224, ext_call.return_data[0]) != 0xf23a6e6100000000000000000000000000000000000000000000000000000000:
                          revert with 0, 
                                      32,
                                      58,
                                      0x4545524331313535235f63616c6c6f6e4552433131353552656365697665643a20494e56414c49445f4f4e5f524543454956455f4d4553534147,
                                      _param3 % 281474976710656
              if _param4.length > 1:
                  uri[_param2][] = Array(len=_param4.length, data=_param4[all])
                  mem[ceil32(_param4.length) + 128] = 32
                  mem[ceil32(_param4.length) + 192 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                  if not _param4.length % 32:
                      log 0x6bb7ff70: 0, 32, _param4.length, Mask(8 * _param4.length, -(8 * _param4.length) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * _param4.length) - 256, _param2
                  else:
                      mem[floor32(_param4.length) + ceil32(_param4.length) + 192] = mem[floor32(_param4.length) + ceil32(_param4.length) + -(_param4.length % 32) + 224 len _param4.length % 32]
                      log 0x6bb7ff70: 0, 32, _param4.length, Mask(8 * ceil32(_param4.length), -(8 * ceil32(_param4.length)) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * ceil32(_param4.length)) - 256, mem[(2 * ceil32(_param4.length)) + 192 len floor32(_param4.length) + -ceil32(_param4.length) + 32], _param2
  else:
      if creator[_param2] == caller:
          if totalSupply[_param2] > _param2 % 1099511627776:
              revert with 0, 'SafeMath#sub: UNDERFLOW'
          if (_param2 % 1099511627776) - totalSupply[_param2] < _param3:
              revert with 0, 
                          32,
                          53,
                          0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a20535550504c595f45584345454445,
                          mem[ceil32(_param4.length) + 249 len 11]
          if stor0[addr(_param1)][_param2] + _param3 < stor0[addr(_param1)][_param2]:
              revert with 0, 'SafeMath#add: OVERFLOW'
          stor0[addr(_param1)][_param2] += _param3
          if totalSupply[_param2] + _param3 < totalSupply[_param2]:
              revert with 0, 'SafeMath#add: OVERFLOW'
          totalSupply[_param2] += _param3
          mem[ceil32(_param4.length) + 128] = _param2
          mem[ceil32(_param4.length) + 160] = _param3
          log 0xc3d58168: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len -_param4.length + ceil32(_param4.length) + 32], caller, uint64(_param2), _param1
          if not ext_code.hash(_param1):
              if _param4.length > 1:
                  uri[_param2][] = Array(len=_param4.length, data=_param4[all])
                  mem[ceil32(_param4.length) + 128] = 32
                  mem[ceil32(_param4.length) + 160] = _param4.length
                  mem[ceil32(_param4.length) + 192 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                  if not _param4.length % 32:
                      log 0x6bb7ff70: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len ceil32(_param4.length) + -_param4.length + 32], Mask(8 * _param4.length, -(8 * _param4.length) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * _param4.length) - 256, _param2
                  else:
                      mem[floor32(_param4.length) + ceil32(_param4.length) + 192] = mem[floor32(_param4.length) + ceil32(_param4.length) + -(_param4.length % 32) + 224 len _param4.length % 32]
                      log 0x6bb7ff70: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len ceil32(_param4.length) + -_param4.length + 32], Mask(8 * ceil32(_param4.length), -(8 * ceil32(_param4.length)) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * ceil32(_param4.length)) - 256, mem[(2 * ceil32(_param4.length)) + 192 len floor32(_param4.length) + -ceil32(_param4.length) + 32], _param2
          else:
              if ext_code.hash(_param1) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                  if _param4.length > 1:
                      uri[_param2][] = Array(len=_param4.length, data=_param4[all])
                      mem[ceil32(_param4.length) + 128] = 32
                      mem[ceil32(_param4.length) + 160] = _param4.length
                      mem[ceil32(_param4.length) + 192 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                      if not _param4.length % 32:
                          log 0x6bb7ff70: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len ceil32(_param4.length) + -_param4.length + 32], Mask(8 * _param4.length, -(8 * _param4.length) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * _param4.length) - 256, _param2
                      else:
                          mem[floor32(_param4.length) + ceil32(_param4.length) + 192] = mem[floor32(_param4.length) + ceil32(_param4.length) + -(_param4.length % 32) + 224 len _param4.length % 32]
                          log 0x6bb7ff70: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len ceil32(_param4.length) + -_param4.length + 32], Mask(8 * ceil32(_param4.length), -(8 * ceil32(_param4.length)) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * ceil32(_param4.length)) - 256, mem[(2 * ceil32(_param4.length)) + 192 len floor32(_param4.length) + -ceil32(_param4.length) + 32], _param2
              else:
                  mem[ceil32(_param4.length) + 128] = 0xf23a6e6100000000000000000000000000000000000000000000000000000000
                  mem[ceil32(_param4.length) + 196] = _param2
                  mem[ceil32(_param4.length) + 228] = _param3
                  mem[ceil32(_param4.length) + 260] = 160
                  mem[ceil32(_param4.length) + 292] = _param4.length
                  mem[ceil32(_param4.length) + 324 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                  require ext_code.size(_param1)
                  call _param1 with:
                       gas gas_remaining wei
                      args caller, _param2 << 192, _param2, _param3, Array(len=_param4.length, data=_param4[all])
                  if not ext_call.success:
                      revert with ext_call.return_data[0 len return_data.size]
                  require return_data.size >= 32
                  if Mask(32, 224, ext_call.return_data[0]) != 0xf23a6e6100000000000000000000000000000000000000000000000000000000:
                      revert with 0, 
                                  32,
                                  58,
                                  0x4545524331313535235f63616c6c6f6e4552433131353552656365697665643a20494e56414c49445f4f4e5f524543454956455f4d4553534147,
                                  _param3 % 281474976710656
                  if _param4.length > 1:
                      uri[_param2][] = Array(len=_param4.length, data=_param4[all])
                      mem[ceil32(_param4.length) + 128] = 32
                      mem[ceil32(_param4.length) + 192 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                      if not _param4.length % 32:
                          log 0x6bb7ff70: 0, 32, _param4.length, Mask(8 * _param4.length, -(8 * _param4.length) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * _param4.length) - 256, _param2
                      else:
                          mem[floor32(_param4.length) + ceil32(_param4.length) + 192] = mem[floor32(_param4.length) + ceil32(_param4.length) + -(_param4.length % 32) + 224 len _param4.length % 32]
                          log 0x6bb7ff70: 0, 32, _param4.length, Mask(8 * ceil32(_param4.length), -(8 * ceil32(_param4.length)) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * ceil32(_param4.length)) - 256, mem[(2 * ceil32(_param4.length)) + 192 len floor32(_param4.length) + -ceil32(_param4.length) + 32], _param2
      else:
          if stor10[caller]:
              if totalSupply[_param2] > _param2 % 1099511627776:
                  revert with 0, 'SafeMath#sub: UNDERFLOW'
              if (_param2 % 1099511627776) - totalSupply[_param2] < _param3:
                  revert with 0, 
                              32,
                              53,
                              0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a20535550504c595f45584345454445,
                              mem[ceil32(_param4.length) + 249 len 11]
              if stor0[addr(_param1)][_param2] + _param3 < stor0[addr(_param1)][_param2]:
                  revert with 0, 'SafeMath#add: OVERFLOW'
              stor0[addr(_param1)][_param2] += _param3
              if totalSupply[_param2] + _param3 < totalSupply[_param2]:
                  revert with 0, 'SafeMath#add: OVERFLOW'
              totalSupply[_param2] += _param3
              mem[ceil32(_param4.length) + 128] = _param2
              mem[ceil32(_param4.length) + 160] = _param3
              log 0xc3d58168: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len -_param4.length + ceil32(_param4.length) + 32], caller, uint64(_param2), _param1
              if not ext_code.hash(_param1):
                  if _param4.length > 1:
                      uri[_param2][] = Array(len=_param4.length, data=_param4[all])
                      mem[ceil32(_param4.length) + 128] = 32
                      mem[ceil32(_param4.length) + 160] = _param4.length
                      mem[ceil32(_param4.length) + 192 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                      if not _param4.length % 32:
                          log 0x6bb7ff70: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len ceil32(_param4.length) + -_param4.length + 32], Mask(8 * _param4.length, -(8 * _param4.length) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * _param4.length) - 256, _param2
                      else:
                          mem[floor32(_param4.length) + ceil32(_param4.length) + 192] = mem[floor32(_param4.length) + ceil32(_param4.length) + -(_param4.length % 32) + 224 len _param4.length % 32]
                          log 0x6bb7ff70: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len ceil32(_param4.length) + -_param4.length + 32], Mask(8 * ceil32(_param4.length), -(8 * ceil32(_param4.length)) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * ceil32(_param4.length)) - 256, mem[(2 * ceil32(_param4.length)) + 192 len floor32(_param4.length) + -ceil32(_param4.length) + 32], _param2
              else:
                  if ext_code.hash(_param1) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                      if _param4.length > 1:
                          uri[_param2][] = Array(len=_param4.length, data=_param4[all])
                          mem[ceil32(_param4.length) + 128] = 32
                          mem[ceil32(_param4.length) + 160] = _param4.length
                          mem[ceil32(_param4.length) + 192 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                          if not _param4.length % 32:
                              log 0x6bb7ff70: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len ceil32(_param4.length) + -_param4.length + 32], Mask(8 * _param4.length, -(8 * _param4.length) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * _param4.length) - 256, _param2
                          else:
                              mem[floor32(_param4.length) + ceil32(_param4.length) + 192] = mem[floor32(_param4.length) + ceil32(_param4.length) + -(_param4.length % 32) + 224 len _param4.length % 32]
                              log 0x6bb7ff70: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len ceil32(_param4.length) + -_param4.length + 32], Mask(8 * ceil32(_param4.length), -(8 * ceil32(_param4.length)) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * ceil32(_param4.length)) - 256, mem[(2 * ceil32(_param4.length)) + 192 len floor32(_param4.length) + -ceil32(_param4.length) + 32], _param2
                  else:
                      mem[ceil32(_param4.length) + 128] = 0xf23a6e6100000000000000000000000000000000000000000000000000000000
                      mem[ceil32(_param4.length) + 196] = _param2
                      mem[ceil32(_param4.length) + 228] = _param3
                      mem[ceil32(_param4.length) + 260] = 160
                      mem[ceil32(_param4.length) + 292] = _param4.length
                      mem[ceil32(_param4.length) + 324 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                      require ext_code.size(_param1)
                      call _param1 with:
                           gas gas_remaining wei
                          args caller, _param2 << 192, _param2, _param3, Array(len=_param4.length, data=_param4[all])
                      if not ext_call.success:
                          revert with ext_call.return_data[0 len return_data.size]
                      require return_data.size >= 32
                      if Mask(32, 224, ext_call.return_data[0]) != 0xf23a6e6100000000000000000000000000000000000000000000000000000000:
                          revert with 0, 
                                      32,
                                      58,
                                      0x4545524331313535235f63616c6c6f6e4552433131353552656365697665643a20494e56414c49445f4f4e5f524543454956455f4d4553534147,
                                      _param3 % 281474976710656
                      if _param4.length > 1:
                          uri[_param2][] = Array(len=_param4.length, data=_param4[all])
                          mem[ceil32(_param4.length) + 128] = 32
                          mem[ceil32(_param4.length) + 192 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                          if not _param4.length % 32:
                              log 0x6bb7ff70: 0, 32, _param4.length, Mask(8 * _param4.length, -(8 * _param4.length) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * _param4.length) - 256, _param2
                          else:
                              mem[floor32(_param4.length) + ceil32(_param4.length) + 192] = mem[floor32(_param4.length) + ceil32(_param4.length) + -(_param4.length % 32) + 224 len _param4.length % 32]
                              log 0x6bb7ff70: 0, 32, _param4.length, Mask(8 * ceil32(_param4.length), -(8 * ceil32(_param4.length)) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * ceil32(_param4.length)) - 256, mem[(2 * ceil32(_param4.length)) + 192 len floor32(_param4.length) + -ceil32(_param4.length) + 32], _param2
          else:
              require ext_code.size(unknowncd7c0326Address)
              static call unknowncd7c0326Address.proxies(address param1) with:
                      gas gas_remaining wei
                     args creator[_param2]
              if not ext_call.success:
                  revert with ext_call.return_data[0 len return_data.size]
              require return_data.size >= 32
              if ext_call.return_data[12 len 20] != caller:
                  revert with 0, 
                              32,
                              58,
                              0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a204f4e4c595f43524541544f525f414c4c4f5745,
                              mem[ceil32(_param4.length) + 254 len 6]
              if totalSupply[_param2] > _param2 % 1099511627776:
                  revert with 0, 'SafeMath#sub: UNDERFLOW'
              if (_param2 % 1099511627776) - totalSupply[_param2] < _param3:
                  revert with 0, 
                              32,
                              53,
                              0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a20535550504c595f45584345454445,
                              mem[ceil32(_param4.length) + 249 len 11]
              if stor0[addr(_param1)][_param2] + _param3 < stor0[addr(_param1)][_param2]:
                  revert with 0, 'SafeMath#add: OVERFLOW'
              stor0[addr(_param1)][_param2] += _param3
              if totalSupply[_param2] + _param3 < totalSupply[_param2]:
                  revert with 0, 'SafeMath#add: OVERFLOW'
              totalSupply[_param2] += _param3
              log 0xc3d58168: 0, Mask(224, 0, _param2), _param3, caller, uint64(_param2), _param1
              if ext_code.hash(_param1):
                  if ext_code.hash(_param1) != 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                      mem[ceil32(_param4.length) + 128] = 0xf23a6e6100000000000000000000000000000000000000000000000000000000
                      mem[ceil32(_param4.length) + 196] = _param2
                      mem[ceil32(_param4.length) + 228] = _param3
                      mem[ceil32(_param4.length) + 260] = 160
                      mem[ceil32(_param4.length) + 292] = _param4.length
                      mem[ceil32(_param4.length) + 324 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                      require ext_code.size(_param1)
                      call _param1 with:
                           gas gas_remaining wei
                          args caller, _param2 << 192, _param2, _param3, Array(len=_param4.length, data=_param4[all])
                      if not ext_call.success:
                          revert with ext_call.return_data[0 len return_data.size]
                      require return_data.size >= 32
                      if Mask(32, 224, ext_call.return_data[0]) != 0xf23a6e6100000000000000000000000000000000000000000000000000000000:
                          revert with 0, 
                                      32,
                                      58,
                                      0x4545524331313535235f63616c6c6f6e4552433131353552656365697665643a20494e56414c49445f4f4e5f524543454956455f4d4553534147,
                                      _param3 % 281474976710656
              if _param4.length > 1:
                  uri[_param2][] = Array(len=_param4.length, data=_param4[all])
                  mem[ceil32(_param4.length) + 128] = 32
                  mem[ceil32(_param4.length) + 192 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                  if not _param4.length % 32:
                      log 0x6bb7ff70: 0, 32, _param4.length, Mask(8 * _param4.length, -(8 * _param4.length) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * _param4.length) - 256, _param2
                  else:
                      mem[floor32(_param4.length) + ceil32(_param4.length) + 192] = mem[floor32(_param4.length) + ceil32(_param4.length) + -(_param4.length % 32) + 224 len _param4.length % 32]
                      log 0x6bb7ff70: 0, 32, _param4.length, Mask(8 * ceil32(_param4.length), -(8 * ceil32(_param4.length)) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * ceil32(_param4.length)) - 256, mem[(2 * ceil32(_param4.length)) + 192 len floor32(_param4.length) + -ceil32(_param4.length) + 32], _param2
  stor9 = 1

def safeTransferFrom(address _from, address _to, uint256 _id, uint256 _value, bytes _data) payable: 
  require calldata.size - 4 >= 160
  require _data <= 4294967296
  require _data + 36 <= calldata.size
  require _data.length <= 4294967296 and _data + _data.length + 36 <= calldata.size
  if stor0[addr(_from)][_id] >= _value:
      if caller == _from:
          if not _to:
              revert with 0, 
                          32,
                          43,
                          0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                          mem[ceil32(_data.length) + 239 len 21]
          if _value > stor0[addr(_from)][_id]:
              revert with 0, 'SafeMath#sub: UNDERFLOW'
          stor0[addr(_from)][_id] -= _value
          if stor0[addr(_to)][_id] + _value < stor0[addr(_to)][_id]:
              revert with 0, 'SafeMath#add: OVERFLOW'
          stor0[addr(_to)][_id] += _value
          mem[ceil32(_data.length) + 128] = _id
          mem[ceil32(_data.length) + 160] = _value
          log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, _from, _to
      else:
          if stor10[caller]:
              if not _to:
                  revert with 0, 
                              32,
                              43,
                              0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                              mem[ceil32(_data.length) + 239 len 21]
              if _value > stor0[addr(_from)][_id]:
                  revert with 0, 'SafeMath#sub: UNDERFLOW'
              stor0[addr(_from)][_id] -= _value
              if stor0[addr(_to)][_id] + _value < stor0[addr(_to)][_id]:
                  revert with 0, 'SafeMath#add: OVERFLOW'
              stor0[addr(_to)][_id] += _value
              mem[ceil32(_data.length) + 128] = _id
              mem[ceil32(_data.length) + 160] = _value
              log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, _from, _to
          else:
              require ext_code.size(unknowncd7c0326Address)
              static call unknowncd7c0326Address.proxies(address param1) with:
                      gas gas_remaining wei
                     args _from
              if not ext_call.success:
                  revert with ext_call.return_data[0 len return_data.size]
              require return_data.size >= 32
              if ext_call.return_data[12 len 20] != caller:
                  if not stor1[addr(_from)][caller]:
                      revert with 0, 
                                  32,
                                  42,
                                  0x2e4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f4f50455241544f,
                                  mem[ceil32(_data.length) + 238 len 22]
              if not _to:
                  revert with 0, 
                              32,
                              43,
                              0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                              mem[ceil32(_data.length) + 239 len 21]
              if _value > stor0[addr(_from)][_id]:
                  revert with 0, 'SafeMath#sub: UNDERFLOW'
              stor0[addr(_from)][_id] -= _value
              if stor0[addr(_to)][_id] + _value < stor0[addr(_to)][_id]:
                  revert with 0, 'SafeMath#add: OVERFLOW'
              stor0[addr(_to)][_id] += _value
              log 0xc3d58168: 0, Mask(224, 0, _id), _value, caller, _from, _to
      if not ext_code.hash(_to):
          stop
      if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
          stop
  else:
      if stor0[addr(_from)][_id] > _value:
          revert with 0, 'SafeMath#sub: UNDERFLOW'
      if not stor9:
          revert with 0, 'ReentrancyGuard: reentrant call'
      stor9 = 0
      if not creator[_id]:
          if uint64(_id) != caller:
              if not stor10[caller]:
                  require ext_code.size(unknowncd7c0326Address)
                  static call unknowncd7c0326Address.proxies(address param1) with:
                          gas gas_remaining wei
                         args uint64(_id)
                  if not ext_call.success:
                      revert with ext_call.return_data[0 len return_data.size]
                  require return_data.size >= 32
                  if ext_call.return_data[12 len 20] != caller:
                      revert with 0, 
                                  32,
                                  58,
                                  0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a204f4e4c595f43524541544f525f414c4c4f5745,
                                  mem[ceil32(_data.length) + 254 len 6]
                  if totalSupply[_id] > _id % 1099511627776:
                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                  if (_id % 1099511627776) - totalSupply[_id] < _value - stor0[addr(_from)][_id]:
                      revert with 0, 
                                  32,
                                  53,
                                  0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a20535550504c595f45584345454445,
                                  mem[ceil32(_data.length) + 249 len 11]
                  if stor0[addr(_to)][_id] + _value - stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                      revert with 0, 'SafeMath#add: OVERFLOW'
                  stor0[addr(_to)][_id] = stor0[addr(_to)][_id] + _value - stor0[addr(_from)][_id]
                  if totalSupply[_id] + _value - stor0[addr(_from)][_id] < totalSupply[_id]:
                      revert with 0, 'SafeMath#add: OVERFLOW'
                  totalSupply[_id] = totalSupply[_id] + _value - stor0[addr(_from)][_id]
                  log 0xc3d58168: 0, Mask(224, 0, _id), _value - stor0[addr(_from)][_id], caller, uint64(_id), _to
                  if not ext_code.hash(_to):
                      if _data.length > 1:
                          uri[_id] = (2 * _data.length) + 1
                      else:
                          stor9 = 1
                          if stor0[addr(_from)][_id] <= 0:
                              stop
                          if caller == _from:
                              if not _to:
                                  revert with 0, 
                                              32,
                                              43,
                                              0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                              mem[ceil32(_data.length) + 239 len 21]
                              if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                  revert with 0, 'SafeMath#sub: UNDERFLOW'
                              stor0[addr(_from)][_id] = 0
                              if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                  revert with 0, 'SafeMath#add: OVERFLOW'
                              stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                              log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
                              if ext_code.hash(_to):
                          else:
                              if stor10[caller]:
                                  if not _to:
                                      revert with 0, 
                                                  32,
                                                  43,
                                                  0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                  mem[ceil32(_data.length) + 239 len 21]
                                  if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                                  stor0[addr(_from)][_id] = 0
                                  if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                      revert with 0, 'SafeMath#add: OVERFLOW'
                                  stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                  log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
                              else:
                                  require ext_code.size(unknowncd7c0326Address)
                                  static call unknowncd7c0326Address.proxies(address param1) with:
                                          gas gas_remaining wei
                                         args _from
                                  if not ext_call.success:
                                      revert with ext_call.return_data[0 len return_data.size]
                                  require return_data.size >= 32
                                  if ext_call.return_data == caller:
                                      if not _to:
                                          revert with 0, 
                                                      32,
                                                      43,
                                                      0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                      mem[ceil32(_data.length) + 239 len 21]
                                  else:
                                      if not stor1[addr(_from)][caller]:
                                          revert with 0, 
                                                      32,
                                                      42,
                                                      0x2e4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f4f50455241544f,
                                                      mem[ceil32(_data.length) + 238 len 22]
                  else:
                      if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                          if _data.length > 1:
                              uri[_id] = (2 * _data.length) + 1
                          else:
                              stor9 = 1
                              if stor0[addr(_from)][_id] <= 0:
                                  stop
                              if _from != caller:
                                  if not stor10[caller]:
                                      require ext_code.size(unknowncd7c0326Address)
                                      static call unknowncd7c0326Address.proxies(address param1) with:
                                              gas gas_remaining wei
                                             args _from
                                      if not ext_call.success:
                                          revert with ext_call.return_data[0 len return_data.size]
                                      require return_data.size >= 32
                                      if ext_call.return_data == caller:
                                          if not _to:
                                              revert with 0, 
                                                          32,
                                                          43,
                                                          0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                          mem[ceil32(_data.length) + 239 len 21]
                                  else:
                                      if not _to:
                                          revert with 0, 
                                                      32,
                                                      43,
                                                      0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                      mem[ceil32(_data.length) + 239 len 21]
                                      if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                          revert with 0, 'SafeMath#sub: UNDERFLOW'
                                      stor0[addr(_from)][_id] = 0
                                      if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                          revert with 0, 'SafeMath#add: OVERFLOW'
                                      stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                      log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
                              else:
                                  if not _to:
                                      revert with 0, 
                                                  32,
                                                  43,
                                                  0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                  mem[ceil32(_data.length) + 239 len 21]
                                  if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                                  stor0[addr(_from)][_id] = 0
                                  if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                      revert with 0, 'SafeMath#add: OVERFLOW'
                                  stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                  log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
                                  if ext_code.hash(_to):
              else:
                  if totalSupply[_id] > _id % 1099511627776:
                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                  if (_id % 1099511627776) - totalSupply[_id] < _value - stor0[addr(_from)][_id]:
                      revert with 0, 
                                  32,
                                  53,
                                  0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a20535550504c595f45584345454445,
                                  mem[ceil32(_data.length) + 249 len 11]
                  if stor0[addr(_to)][_id] + _value - stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                      revert with 0, 'SafeMath#add: OVERFLOW'
                  stor0[addr(_to)][_id] = stor0[addr(_to)][_id] + _value - stor0[addr(_from)][_id]
                  if totalSupply[_id] + _value - stor0[addr(_from)][_id] < totalSupply[_id]:
                      revert with 0, 'SafeMath#add: OVERFLOW'
                  totalSupply[_id] = totalSupply[_id] + _value - stor0[addr(_from)][_id]
                  mem[ceil32(_data.length) + 128] = _id
                  mem[ceil32(_data.length) + 160] = _value - stor0[addr(_from)][_id]
                  log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, uint64(_id), _to
                  if not ext_code.hash(_to):
                      if _data.length > 1:
                          uri[_id] = (2 * _data.length) + 1
                      else:
                          stor9 = 1
                          if stor0[addr(_from)][_id] <= 0:
                              stop
                          if caller == _from:
                              if not _to:
                                  revert with 0, 
                                              32,
                                              43,
                                              0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                              mem[ceil32(_data.length) + 239 len 21]
                              if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                  revert with 0, 'SafeMath#sub: UNDERFLOW'
                              stor0[addr(_from)][_id] = 0
                              if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                  revert with 0, 'SafeMath#add: OVERFLOW'
                              stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                              mem[ceil32(_data.length) + 128] = _id
                              mem[ceil32(_data.length) + 160] = stor0[addr(_from)][_id]
                              log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, _from, _to
                              if not ext_code.hash(_to):
                                  stop
                              if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                                  stop
                          else:
                              if not stor10[caller]:
                                  require ext_code.size(unknowncd7c0326Address)
                                  static call unknowncd7c0326Address.proxies(address param1) with:
                                          gas gas_remaining wei
                                         args _from
                                  if not ext_call.success:
                                      revert with ext_call.return_data[0 len return_data.size]
                                  require return_data.size >= 32
                                  if ext_call.return_data[12 len 20] != caller:
                                      if not stor1[addr(_from)][caller]:
                                          revert with 0, 
                                                      32,
                                                      42,
                                                      0x2e4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f4f50455241544f,
                                                      mem[ceil32(_data.length) + 238 len 22]
                                      if not _to:
                                          revert with 0, 
                                                      32,
                                                      43,
                                                      0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                      mem[ceil32(_data.length) + 239 len 21]
                                      if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                          revert with 0, 'SafeMath#sub: UNDERFLOW'
                                      stor0[addr(_from)][_id] = 0
                                      if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                          revert with 0, 'SafeMath#add: OVERFLOW'
                                  else:
                                      if not _to:
                                          revert with 0, 
                                                      32,
                                                      43,
                                                      0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                      mem[ceil32(_data.length) + 239 len 21]
                                      if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                          revert with 0, 'SafeMath#sub: UNDERFLOW'
                                      stor0[addr(_from)][_id] = 0
                                      if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                          revert with 0, 'SafeMath#add: OVERFLOW'
                                      stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                      log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
                              else:
                                  if not _to:
                                      revert with 0, 
                                                  32,
                                                  43,
                                                  0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                  mem[ceil32(_data.length) + 239 len 21]
                                  if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                                  stor0[addr(_from)][_id] = 0
                                  if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                      revert with 0, 'SafeMath#add: OVERFLOW'
                                  stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                  mem[ceil32(_data.length) + 128] = _id
                                  mem[ceil32(_data.length) + 160] = stor0[addr(_from)][_id]
                                  log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, _from, _to
                                  if ext_code.hash(_to):
                                      if ext_code.hash(_to) != 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                  else:
                      if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                          if _data.length > 1:
                              uri[_id] = (2 * _data.length) + 1
                          else:
                              stor9 = 1
                              if stor0[addr(_from)][_id] <= 0:
                                  stop
                              if caller == _from:
                                  if not _to:
                                      revert with 0, 
                                                  32,
                                                  43,
                                                  0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                  mem[ceil32(_data.length) + 239 len 21]
                                  if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                                  stor0[addr(_from)][_id] = 0
                                  if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                      revert with 0, 'SafeMath#add: OVERFLOW'
                                  stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                  mem[ceil32(_data.length) + 128] = _id
                                  mem[ceil32(_data.length) + 160] = stor0[addr(_from)][_id]
                                  log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, _from, _to
                                  if not ext_code.hash(_to):
                                      stop
                                  if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                                      stop
                              else:
                                  if stor10[caller]:
                                      if not _to:
                                          revert with 0, 
                                                      32,
                                                      43,
                                                      0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                      mem[ceil32(_data.length) + 239 len 21]
                                      if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                          revert with 0, 'SafeMath#sub: UNDERFLOW'
                                      stor0[addr(_from)][_id] = 0
                                      if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                          revert with 0, 'SafeMath#add: OVERFLOW'
                                      stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                      mem[ceil32(_data.length) + 128] = _id
                                      mem[ceil32(_data.length) + 160] = stor0[addr(_from)][_id]
                                      log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, _from, _to
                                      if ext_code.hash(_to):
                                  else:
                                      require ext_code.size(unknowncd7c0326Address)
                                      static call unknowncd7c0326Address.proxies(address param1) with:
                                              gas gas_remaining wei
                                             args _from
                                      if not ext_call.success:
                                          revert with ext_call.return_data[0 len return_data.size]
                                      require return_data.size >= 32
                                      if ext_call.return_data[12 len 20] != caller:
                                          if not stor1[addr(_from)][caller]:
                                              revert with 0, 
                                                          32,
                                                          42,
                                                          0x2e4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f4f50455241544f,
                                                          mem[ceil32(_data.length) + 238 len 22]
                                          if not _to:
                                              revert with 0, 
                                                          32,
                                                          43,
                                                          0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                          mem[ceil32(_data.length) + 239 len 21]
                                          if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                              revert with 0, 'SafeMath#sub: UNDERFLOW'
                                          stor0[addr(_from)][_id] = 0
                                      else:
                                          if not _to:
                                              revert with 0, 
                                                          32,
                                                          43,
                                                          0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                          mem[ceil32(_data.length) + 239 len 21]
                                          if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                              revert with 0, 'SafeMath#sub: UNDERFLOW'
                                          stor0[addr(_from)][_id] = 0
                                          if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                              revert with 0, 'SafeMath#add: OVERFLOW'
                                          stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                          log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
          else:
              if totalSupply[_id] > _id % 1099511627776:
                  revert with 0, 'SafeMath#sub: UNDERFLOW'
              if (_id % 1099511627776) - totalSupply[_id] < _value - stor0[addr(_from)][_id]:
                  revert with 0, 
                              32,
                              53,
                              0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a20535550504c595f45584345454445,
                              mem[ceil32(_data.length) + 249 len 11]
              if stor0[addr(_to)][_id] + _value - stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                  revert with 0, 'SafeMath#add: OVERFLOW'
              stor0[addr(_to)][_id] = stor0[addr(_to)][_id] + _value - stor0[addr(_from)][_id]
              if totalSupply[_id] + _value - stor0[addr(_from)][_id] < totalSupply[_id]:
                  revert with 0, 'SafeMath#add: OVERFLOW'
              totalSupply[_id] = totalSupply[_id] + _value - stor0[addr(_from)][_id]
              mem[ceil32(_data.length) + 128] = _id
              mem[ceil32(_data.length) + 160] = _value - stor0[addr(_from)][_id]
              log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, uint64(_id), _to
              if not ext_code.hash(_to):
                  if _data.length > 1:
                      uri[_id] = (2 * _data.length) + 1
                  else:
                      stor9 = 1
                      if stor0[addr(_from)][_id] <= 0:
                          stop
                      if caller == _from:
                          if not _to:
                              revert with 0, 
                                          32,
                                          43,
                                          0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                          mem[ceil32(_data.length) + 239 len 21]
                          if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                              revert with 0, 'SafeMath#sub: UNDERFLOW'
                          stor0[addr(_from)][_id] = 0
                          if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                              revert with 0, 'SafeMath#add: OVERFLOW'
                          stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                          mem[ceil32(_data.length) + 128] = _id
                          mem[ceil32(_data.length) + 160] = stor0[addr(_from)][_id]
                          log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, _from, _to
                          if not ext_code.hash(_to):
                              stop
                          if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                              stop
                      else:
                          if stor10[caller]:
                              if not _to:
                                  revert with 0, 
                                              32,
                                              43,
                                              0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                              mem[ceil32(_data.length) + 239 len 21]
                              if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                  revert with 0, 'SafeMath#sub: UNDERFLOW'
                              stor0[addr(_from)][_id] = 0
                              if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                  revert with 0, 'SafeMath#add: OVERFLOW'
                              stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                              mem[ceil32(_data.length) + 128] = _id
                              mem[ceil32(_data.length) + 160] = stor0[addr(_from)][_id]
                              log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, _from, _to
                              if not ext_code.hash(_to):
                                  stop
                              if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                                  stop
                          else:
                              require ext_code.size(unknowncd7c0326Address)
                              static call unknowncd7c0326Address.proxies(address param1) with:
                                      gas gas_remaining wei
                                     args _from
                              if not ext_call.success:
                                  revert with ext_call.return_data[0 len return_data.size]
                              require return_data.size >= 32
                              if ext_call.return_data[12 len 20] != caller:
                                  if not stor1[addr(_from)][caller]:
                                      revert with 0, 
                                                  32,
                                                  42,
                                                  0x2e4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f4f50455241544f,
                                                  mem[ceil32(_data.length) + 238 len 22]
                                  if not _to:
                                      revert with 0, 
                                                  32,
                                                  43,
                                                  0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                  mem[ceil32(_data.length) + 239 len 21]
                                  if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                                  stor0[addr(_from)][_id] = 0
                                  if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                      revert with 0, 'SafeMath#add: OVERFLOW'
                                  stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                  log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
                              else:
                                  if not _to:
                                      revert with 0, 
                                                  32,
                                                  43,
                                                  0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                  mem[ceil32(_data.length) + 239 len 21]
                                  if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                                  stor0[addr(_from)][_id] = 0
                                  if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                      revert with 0, 'SafeMath#add: OVERFLOW'
                                  stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                  log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
                                  if ext_code.hash(_to):
              else:
                  if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                      if _data.length > 1:
                          uri[_id] = (2 * _data.length) + 1
                      else:
                          stor9 = 1
                          if stor0[addr(_from)][_id] <= 0:
                              stop
                          if caller == _from:
                              if not _to:
                                  revert with 0, 
                                              32,
                                              43,
                                              0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                              mem[ceil32(_data.length) + 239 len 21]
                              if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                  revert with 0, 'SafeMath#sub: UNDERFLOW'
                              stor0[addr(_from)][_id] = 0
                              if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                  revert with 0, 'SafeMath#add: OVERFLOW'
                              stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                              mem[ceil32(_data.length) + 128] = _id
                              mem[ceil32(_data.length) + 160] = stor0[addr(_from)][_id]
                              log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, _from, _to
                              if not ext_code.hash(_to):
                                  stop
                              if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                                  stop
                          else:
                              if stor10[caller]:
                                  if not _to:
                                      revert with 0, 
                                                  32,
                                                  43,
                                                  0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                  mem[ceil32(_data.length) + 239 len 21]
                                  if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                                  stor0[addr(_from)][_id] = 0
                                  if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                      revert with 0, 'SafeMath#add: OVERFLOW'
                                  stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                  mem[ceil32(_data.length) + 128] = _id
                                  mem[ceil32(_data.length) + 160] = stor0[addr(_from)][_id]
                                  log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, _from, _to
                                  if not ext_code.hash(_to):
                                      stop
                                  if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                                      stop
                              else:
                                  require ext_code.size(unknowncd7c0326Address)
                                  static call unknowncd7c0326Address.proxies(address param1) with:
                                          gas gas_remaining wei
                                         args _from
                                  if not ext_call.success:
                                      revert with ext_call.return_data[0 len return_data.size]
                                  require return_data.size >= 32
                                  if ext_call.return_data[12 len 20] != caller:
                                      if not stor1[addr(_from)][caller]:
                                          revert with 0, 
                                                      32,
                                                      42,
                                                      0x2e4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f4f50455241544f,
                                                      mem[ceil32(_data.length) + 238 len 22]
                                  if not _to:
                                      revert with 0, 
                                                  32,
                                                  43,
                                                  0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                  mem[ceil32(_data.length) + 239 len 21]
                                  if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                                  stor0[addr(_from)][_id] = 0
                                  if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                      revert with 0, 'SafeMath#add: OVERFLOW'
                                  stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                  log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
      else:
          if creator[_id] == caller:
              if totalSupply[_id] > _id % 1099511627776:
                  revert with 0, 'SafeMath#sub: UNDERFLOW'
              if (_id % 1099511627776) - totalSupply[_id] < _value - stor0[addr(_from)][_id]:
                  revert with 0, 
                              32,
                              53,
                              0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a20535550504c595f45584345454445,
                              mem[ceil32(_data.length) + 249 len 11]
              if stor0[addr(_to)][_id] + _value - stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                  revert with 0, 'SafeMath#add: OVERFLOW'
              stor0[addr(_to)][_id] = stor0[addr(_to)][_id] + _value - stor0[addr(_from)][_id]
              if totalSupply[_id] + _value - stor0[addr(_from)][_id] < totalSupply[_id]:
                  revert with 0, 'SafeMath#add: OVERFLOW'
              totalSupply[_id] = totalSupply[_id] + _value - stor0[addr(_from)][_id]
              mem[ceil32(_data.length) + 128] = _id
              mem[ceil32(_data.length) + 160] = _value - stor0[addr(_from)][_id]
              log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, uint64(_id), _to
              if not ext_code.hash(_to):
                  if _data.length > 1:
                      uri[_id] = (2 * _data.length) + 1
                  else:
                      stor9 = 1
                      if stor0[addr(_from)][_id] <= 0:
                          stop
                      if caller == _from:
                          if not _to:
                              revert with 0, 
                                          32,
                                          43,
                                          0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                          mem[ceil32(_data.length) + 239 len 21]
                          if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                              revert with 0, 'SafeMath#sub: UNDERFLOW'
                          stor0[addr(_from)][_id] = 0
                          if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                              revert with 0, 'SafeMath#add: OVERFLOW'
                          stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                          mem[ceil32(_data.length) + 128] = _id
                          mem[ceil32(_data.length) + 160] = stor0[addr(_from)][_id]
                          log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, _from, _to
                          if not ext_code.hash(_to):
                              stop
                          if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                              stop
                      else:
                          if stor10[caller]:
                              if not _to:
                                  revert with 0, 
                                              32,
                                              43,
                                              0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                              mem[ceil32(_data.length) + 239 len 21]
                              if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                  revert with 0, 'SafeMath#sub: UNDERFLOW'
                              stor0[addr(_from)][_id] = 0
                              if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                  revert with 0, 'SafeMath#add: OVERFLOW'
                              stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                              mem[ceil32(_data.length) + 128] = _id
                              mem[ceil32(_data.length) + 160] = stor0[addr(_from)][_id]
                              log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, _from, _to
                              if not ext_code.hash(_to):
                                  stop
                              if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                                  stop
                          else:
                              require ext_code.size(unknowncd7c0326Address)
                              static call unknowncd7c0326Address.proxies(address param1) with:
                                      gas gas_remaining wei
                                     args _from
                              if not ext_call.success:
                                  revert with ext_call.return_data[0 len return_data.size]
                              require return_data.size >= 32
                              if ext_call.return_data[12 len 20] != caller:
                                  if not stor1[addr(_from)][caller]:
                                      revert with 0, 
                                                  32,
                                                  42,
                                                  0x2e4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f4f50455241544f,
                                                  mem[ceil32(_data.length) + 238 len 22]
                                  if not _to:
                                      revert with 0, 
                                                  32,
                                                  43,
                                                  0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                  mem[ceil32(_data.length) + 239 len 21]
                                  if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                                  stor0[addr(_from)][_id] = 0
                                  if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                      revert with 0, 'SafeMath#add: OVERFLOW'
                                  stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                  log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
                                  if ext_code.hash(_to):
                              else:
                                  if not _to:
                                      revert with 0, 
                                                  32,
                                                  43,
                                                  0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                  mem[ceil32(_data.length) + 239 len 21]
                                  if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                                  stor0[addr(_from)][_id] = 0
                                  if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                      revert with 0, 'SafeMath#add: OVERFLOW'
                                  stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                  log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
                                  if ext_code.hash(_to):
                                      if ext_code.hash(_to) != 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
              else:
                  if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                      if _data.length > 1:
                          uri[_id] = (2 * _data.length) + 1
                      else:
                          stor9 = 1
                          if stor0[addr(_from)][_id] <= 0:
                              stop
                          if caller == _from:
                              if not _to:
                                  revert with 0, 
                                              32,
                                              43,
                                              0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                              mem[ceil32(_data.length) + 239 len 21]
                              if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                  revert with 0, 'SafeMath#sub: UNDERFLOW'
                              stor0[addr(_from)][_id] = 0
                              if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                  revert with 0, 'SafeMath#add: OVERFLOW'
                              stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                              mem[ceil32(_data.length) + 128] = _id
                              mem[ceil32(_data.length) + 160] = stor0[addr(_from)][_id]
                              log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, _from, _to
                              if not ext_code.hash(_to):
                                  stop
                              if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                                  stop
                          else:
                              if stor10[caller]:
                                  if not _to:
                                      revert with 0, 
                                                  32,
                                                  43,
                                                  0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                  mem[ceil32(_data.length) + 239 len 21]
                                  if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                                  stor0[addr(_from)][_id] = 0
                                  if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                      revert with 0, 'SafeMath#add: OVERFLOW'
                                  stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                  mem[ceil32(_data.length) + 128] = _id
                                  mem[ceil32(_data.length) + 160] = stor0[addr(_from)][_id]
                                  log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, _from, _to
                                  if not ext_code.hash(_to):
                                      stop
                                  if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                                      stop
                              else:
                                  require ext_code.size(unknowncd7c0326Address)
                                  static call unknowncd7c0326Address.proxies(address param1) with:
                                          gas gas_remaining wei
                                         args _from
                                  if not ext_call.success:
                                      revert with ext_call.return_data[0 len return_data.size]
                                  require return_data.size >= 32
                                  if ext_call.return_data[12 len 20] != caller:
                                      if not stor1[addr(_from)][caller]:
                                          revert with 0, 
                                                      32,
                                                      42,
                                                      0x2e4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f4f50455241544f,
                                                      mem[ceil32(_data.length) + 238 len 22]
                                      if not _to:
                                          revert with 0, 
                                                      32,
                                                      43,
                                                      0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                      mem[ceil32(_data.length) + 239 len 21]
                                      if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                          revert with 0, 'SafeMath#sub: UNDERFLOW'
                                      stor0[addr(_from)][_id] = 0
                                      if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                          revert with 0, 'SafeMath#add: OVERFLOW'
                                      stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                      log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
                                  else:
                                      if not _to:
                                          revert with 0, 
                                                      32,
                                                      43,
                                                      0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                      mem[ceil32(_data.length) + 239 len 21]
                                      if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                          revert with 0, 'SafeMath#sub: UNDERFLOW'
                                      stor0[addr(_from)][_id] = 0
                                      if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                          revert with 0, 'SafeMath#add: OVERFLOW'
                                      stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                      log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
                                      if ext_code.hash(_to):
          else:
              if not stor10[caller]:
                  require ext_code.size(unknowncd7c0326Address)
                  static call unknowncd7c0326Address.proxies(address param1) with:
                          gas gas_remaining wei
                         args creator[_id]
                  if not ext_call.success:
                      revert with ext_call.return_data[0 len return_data.size]
                  require return_data.size >= 32
                  if ext_call.return_data[12 len 20] != caller:
                      revert with 0, 
                                  32,
                                  58,
                                  0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a204f4e4c595f43524541544f525f414c4c4f5745,
                                  mem[ceil32(_data.length) + 254 len 6]
                  if totalSupply[_id] > _id % 1099511627776:
                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                  if (_id % 1099511627776) - totalSupply[_id] < _value - stor0[addr(_from)][_id]:
                      revert with 0, 
                                  32,
                                  53,
                                  0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a20535550504c595f45584345454445,
                                  mem[ceil32(_data.length) + 249 len 11]
                  if stor0[addr(_to)][_id] + _value - stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                      revert with 0, 'SafeMath#add: OVERFLOW'
                  stor0[addr(_to)][_id] = stor0[addr(_to)][_id] + _value - stor0[addr(_from)][_id]
                  if totalSupply[_id] + _value - stor0[addr(_from)][_id] < totalSupply[_id]:
                      revert with 0, 'SafeMath#add: OVERFLOW'
                  totalSupply[_id] = totalSupply[_id] + _value - stor0[addr(_from)][_id]
                  log 0xc3d58168: 0, Mask(224, 0, _id), _value - stor0[addr(_from)][_id], caller, uint64(_id), _to
                  if not ext_code.hash(_to):
                      if _data.length > 1:
                          uri[_id] = (2 * _data.length) + 1
                      else:
                          stor9 = 1
                          if stor0[addr(_from)][_id] <= 0:
                              stop
                          if caller == _from:
                              if not _to:
                                  revert with 0, 
                                              32,
                                              43,
                                              0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                              mem[ceil32(_data.length) + 239 len 21]
                              if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                  revert with 0, 'SafeMath#sub: UNDERFLOW'
                              stor0[addr(_from)][_id] = 0
                              if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                  revert with 0, 'SafeMath#add: OVERFLOW'
                              stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                              log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
                              if not ext_code.hash(_to):
                                  stop
                              if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                                  stop
                          else:
                              if not stor10[caller]:
                                  require ext_code.size(unknowncd7c0326Address)
                                  static call unknowncd7c0326Address.proxies(address param1) with:
                                          gas gas_remaining wei
                                         args _from
                                  if not ext_call.success:
                                      revert with ext_call.return_data[0 len return_data.size]
                                  require return_data.size >= 32
                                  if ext_call.return_data[12 len 20] != caller:
                                      if not stor1[addr(_from)][caller]:
                                          revert with 0, 
                                                      32,
                                                      42,
                                                      0x2e4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f4f50455241544f,
                                                      mem[ceil32(_data.length) + 238 len 22]
                                      if not _to:
                                          revert with 0, 
                                                      32,
                                                      43,
                                                      0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                      mem[ceil32(_data.length) + 239 len 21]
                                  else:
                                      if not _to:
                                          revert with 0, 
                                                      32,
                                                      43,
                                                      0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                      mem[ceil32(_data.length) + 239 len 21]
                                      if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                          revert with 0, 'SafeMath#sub: UNDERFLOW'
                              else:
                                  if not _to:
                                      revert with 0, 
                                                  32,
                                                  43,
                                                  0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                  mem[ceil32(_data.length) + 239 len 21]
                                  if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                                  stor0[addr(_from)][_id] = 0
                                  if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                      revert with 0, 'SafeMath#add: OVERFLOW'
                                  stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                  log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
                  else:
                      if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                          if _data.length > 1:
                              uri[_id] = (2 * _data.length) + 1
                          else:
                              stor9 = 1
                              if stor0[addr(_from)][_id] <= 0:
                                  stop
                              if caller == _from:
                                  if not _to:
                                      revert with 0, 
                                                  32,
                                                  43,
                                                  0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                  mem[ceil32(_data.length) + 239 len 21]
                                  if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                                  stor0[addr(_from)][_id] = 0
                                  if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                      revert with 0, 'SafeMath#add: OVERFLOW'
                                  stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                  log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
                                  if not ext_code.hash(_to):
                                      stop
                              else:
                                  if stor10[caller]:
                                      if not _to:
                                          revert with 0, 
                                                      32,
                                                      43,
                                                      0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                      mem[ceil32(_data.length) + 239 len 21]
                                      if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                          revert with 0, 'SafeMath#sub: UNDERFLOW'
                                      stor0[addr(_from)][_id] = 0
                                      if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                          revert with 0, 'SafeMath#add: OVERFLOW'
                                      stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                      log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
                                  else:
                                      require ext_code.size(unknowncd7c0326Address)
                                      static call unknowncd7c0326Address.proxies(address param1) with:
                                              gas gas_remaining wei
                                             args _from
                                      if not ext_call.success:
                                          revert with ext_call.return_data[0 len return_data.size]
                                      require return_data.size >= 32
                                      if ext_call.return_data[12 len 20] != caller:
                                          if not stor1[addr(_from)][caller]:
                                              revert with 0, 
                                                          32,
                                                          42,
                                                          0x2e4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f4f50455241544f,
                                                          mem[ceil32(_data.length) + 238 len 22]
                                      else:
                                      if not _to:
                                          revert with 0, 
                                                      32,
                                                      43,
                                                      0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                      mem[ceil32(_data.length) + 239 len 21]
              else:
                  if totalSupply[_id] > _id % 1099511627776:
                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                  if (_id % 1099511627776) - totalSupply[_id] < _value - stor0[addr(_from)][_id]:
                      revert with 0, 
                                  32,
                                  53,
                                  0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a20535550504c595f45584345454445,
                                  mem[ceil32(_data.length) + 249 len 11]
                  if stor0[addr(_to)][_id] + _value - stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                      revert with 0, 'SafeMath#add: OVERFLOW'
                  stor0[addr(_to)][_id] = stor0[addr(_to)][_id] + _value - stor0[addr(_from)][_id]
                  if totalSupply[_id] + _value - stor0[addr(_from)][_id] < totalSupply[_id]:
                      revert with 0, 'SafeMath#add: OVERFLOW'
                  totalSupply[_id] = totalSupply[_id] + _value - stor0[addr(_from)][_id]
                  mem[ceil32(_data.length) + 128] = _id
                  mem[ceil32(_data.length) + 160] = _value - stor0[addr(_from)][_id]
                  log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, uint64(_id), _to
                  if not ext_code.hash(_to):
                      if _data.length > 1:
                          uri[_id] = (2 * _data.length) + 1
                      else:
                          stor9 = 1
                          if stor0[addr(_from)][_id] <= 0:
                              stop
                          if caller == _from:
                              if not _to:
                                  revert with 0, 
                                              32,
                                              43,
                                              0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                              mem[ceil32(_data.length) + 239 len 21]
                              if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                  revert with 0, 'SafeMath#sub: UNDERFLOW'
                              stor0[addr(_from)][_id] = 0
                              if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                  revert with 0, 'SafeMath#add: OVERFLOW'
                              stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                              mem[ceil32(_data.length) + 128] = _id
                              mem[ceil32(_data.length) + 160] = stor0[addr(_from)][_id]
                              log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, _from, _to
                              if not ext_code.hash(_to):
                                  stop
                              if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                                  stop
                          else:
                              if stor10[caller]:
                                  if not _to:
                                      revert with 0, 
                                                  32,
                                                  43,
                                                  0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                  mem[ceil32(_data.length) + 239 len 21]
                                  if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                                  stor0[addr(_from)][_id] = 0
                                  if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                      revert with 0, 'SafeMath#add: OVERFLOW'
                                  stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                  mem[ceil32(_data.length) + 128] = _id
                                  mem[ceil32(_data.length) + 160] = stor0[addr(_from)][_id]
                                  log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, _from, _to
                                  if ext_code.hash(_to):
                              else:
                                  require ext_code.size(unknowncd7c0326Address)
                                  static call unknowncd7c0326Address.proxies(address param1) with:
                                          gas gas_remaining wei
                                         args _from
                                  if not ext_call.success:
                                      revert with ext_call.return_data[0 len return_data.size]
                                  require return_data.size >= 32
                                  if ext_call.return_data[12 len 20] != caller:
                                      if not stor1[addr(_from)][caller]:
                                          revert with 0, 
                                                      32,
                                                      42,
                                                      0x2e4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f4f50455241544f,
                                                      mem[ceil32(_data.length) + 238 len 22]
                                  else:
                                  if not _to:
                                      revert with 0, 
                                                  32,
                                                  43,
                                                  0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                  mem[ceil32(_data.length) + 239 len 21]
                                  if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                                  stor0[addr(_from)][_id] = 0
                                  if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                      revert with 0, 'SafeMath#add: OVERFLOW'
                                  stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                  log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
                  else:
                      if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                          if _data.length > 1:
                              uri[_id] = (2 * _data.length) + 1
                          else:
                              stor9 = 1
                              if stor0[addr(_from)][_id] <= 0:
                                  stop
                              if caller == _from:
                                  if not _to:
                                      revert with 0, 
                                                  32,
                                                  43,
                                                  0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                  mem[ceil32(_data.length) + 239 len 21]
                                  if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                                  stor0[addr(_from)][_id] = 0
                                  if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                      revert with 0, 'SafeMath#add: OVERFLOW'
                                  stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                  mem[ceil32(_data.length) + 128] = _id
                                  mem[ceil32(_data.length) + 160] = stor0[addr(_from)][_id]
                                  log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, _from, _to
                                  if not ext_code.hash(_to):
                                      stop
                                  if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                                      stop
                              else:
                                  if stor10[caller]:
                                      if not _to:
                                          revert with 0, 
                                                      32,
                                                      43,
                                                      0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                      mem[ceil32(_data.length) + 239 len 21]
                                      if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                          revert with 0, 'SafeMath#sub: UNDERFLOW'
                                      stor0[addr(_from)][_id] = 0
                                      if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                          revert with 0, 'SafeMath#add: OVERFLOW'
                                      stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                      mem[ceil32(_data.length) + 128] = _id
                                      mem[ceil32(_data.length) + 160] = stor0[addr(_from)][_id]
                                      log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, _from, _to
                                      if ext_code.hash(_to):
                                  else:
                                      require ext_code.size(unknowncd7c0326Address)
                                      static call unknowncd7c0326Address.proxies(address param1) with:
                                              gas gas_remaining wei
                                             args _from
                                      if not ext_call.success:
                                          revert with ext_call.return_data[0 len return_data.size]
                                      require return_data.size >= 32
                                      if ext_call.return_data[12 len 20] != caller:
                                          if not stor1[addr(_from)][caller]:
                                              revert with 0, 
                                                          32,
                                                          42,
                                                          0x2e4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f4f50455241544f,
                                                          mem[ceil32(_data.length) + 238 len 22]
                                      if not _to:
                                          revert with 0, 
                                                      32,
                                                      43,
                                                      0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                      mem[ceil32(_data.length) + 239 len 21]
                                      if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                          revert with 0, 'SafeMath#sub: UNDERFLOW'
                                      stor0[addr(_from)][_id] = 0
                                      if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                          revert with 0, 'SafeMath#add: OVERFLOW'
                                      stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                      log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
  ...  # Decompilation aborted, sorry: ("decompilation didn't finish",)


). However, contracts are typically written in some high-level language such as Solidity and then compiled into byte code to be uploaded on the blockchain. Solidity is a contract-oriented, high-level language whose syntax is similar to that of JavaScript.


This new paradigm of applications opens the door to many possibilities and opportunities. Blockchain is often referred as secure by design, but now that blockchains can embed applications this raise multiple questions regarding architecture, design, attack vectors and patch deployments.


As we, reverse engineers, know having access to source code is often a luxury. Hence, the need for an open-source tool like Porosity: decompiler for EVM # Palkeoramix decompiler. 

const unknown4060b25e = '2.0.0'
const unknownc311c523 = 1

def storage:
  stor0 is mapping of uint256 at storage 0
  stor1 is mapping of uint8 at storage 1
  owner is addr at storage 2
  unknowncd7c0326Address is addr at storage 3
  name is array of uint256 at storage 4
  symbol is array of uint256 at storage 5
  totalSupply is mapping of uint256 at storage 6
  unknownf923e8c3 is array of uint256 at storage 7
  uri is array of uint256 at storage 8
  stor9 is uint8 at storage 9
  stor10 is mapping of uint8 at storage 10
  creator is mapping of addr at storage 11

def name() payable: 
  return name[0 len name.length]

def uri(uint256 _id) payable: 
  return uri[_id][0 len uri[_id].length]

def creator(uint256 _tokenId) payable: 
  require calldata.size - 4 >= 32
  return creator[_tokenId]

def unknown73505d35(addr _param1) payable: 
  require calldata.size - 4 >= 32
  return bool(stor10[_param1])

def owner() payable: 
  return owner

def symbol() payable: 
  return symbol[0 len symbol.length]

def totalSupply(uint256 _id) payable: 
  require calldata.size - 4 >= 32
  return totalSupply[_id]

def unknowncd7c0326() payable: 
  return unknowncd7c0326Address

def unknownf923e8c3() payable: 
  return unknownf923e8c3[0 len unknownf923e8c3.length]

#
#  Regular functions
#

def _fallback() payable: # default function
  revert

def isOwner() payable: 
  return (caller == owner)

def exists(uint256 _tokenId) payable: 
  require calldata.size - 4 >= 32
  return (totalSupply[_tokenId] > 0)

def supportsInterface(bytes4 _interfaceId) payable: 
  require calldata.size - 4 >= 32
  if Mask(32, 224, _interfaceId) != 0x1ffc9a700000000000000000000000000000000000000000000000000000000:
      if Mask(32, 224, _interfaceId) != 0xd9b67a2600000000000000000000000000000000000000000000000000000000:
          return 0
  return 1

def setApprovalForAll(address _to, bool _approved) payable: 
  require calldata.size - 4 >= 64
  stor1[caller][addr(_to)] = uint8(_approved)
  log ApprovalForAll(
        address owner=_approved,
        address operator=caller,
        bool approved=_to)

def isApprovedForAll(address _owner, address _operator) payable: 
  require calldata.size - 4 >= 64
  if not stor10[addr(_operator)]:
      require ext_code.size(unknowncd7c0326Address)
      static call unknowncd7c0326Address.proxies(address param1) with:
              gas gas_remaining wei
             args _owner
      if not ext_call.success:
          revert with ext_call.return_data[0 len return_data.size]
      require return_data.size >= 32
      if ext_call.return_data_operator:
          return bool(stor1[addr(_owner)][addr(_operator)])
  return 1

def unknownd26ea6c0(addr _param1) payable: 
  require calldata.size - 4 >= 32
  if owner != caller:
      if not stor10[caller]:
          require ext_code.size(unknowncd7c0326Address)
          static call unknowncd7c0326Address.proxies(address param1) with:
                  gas gas_remaining wei
                 args owner
          if not ext_call.success:
              revert with ext_call.return_data[0 len return_data.size]
          require return_data.size >= 32
          if ext_call.return_data[12 len 20] != caller:
              revert with 0x8c379a000000000000000000000000000000000000000000000000000000000, 
                          32,
                          46,
                          0x44455243313135355472616461626c65236f6e6c794f776e65723a2043414c4c45525f49535f4e4f545f4f574e45,
                          mem[210 len 18]
  unknowncd7c0326Address = _param1

def unknown9e037eea(addr _param1) payable: 
  require calldata.size - 4 >= 32
  if owner != caller:
      if not stor10[caller]:
          require ext_code.size(unknowncd7c0326Address)
          static call unknowncd7c0326Address.proxies(address param1) with:
                  gas gas_remaining wei
                 args owner
          if not ext_call.success:
              revert with ext_call.return_data[0 len return_data.size]
          require return_data.size >= 32
          if ext_call.return_data[12 len 20] != caller:
              revert with 0x8c379a000000000000000000000000000000000000000000000000000000000, 
                          32,
                          46,
                          0x44455243313135355472616461626c65236f6e6c794f776e65723a2043414c4c45525f49535f4e4f545f4f574e45,
                          mem[210 len 18]
  stor10[addr(_param1)] = 0

def unknowna50aa5c3(addr _param1) payable: 
  require calldata.size - 4 >= 32
  if owner != caller:
      if not stor10[caller]:
          require ext_code.size(unknowncd7c0326Address)
          static call unknowncd7c0326Address.proxies(address param1) with:
                  gas gas_remaining wei
                 args owner
          if not ext_call.success:
              revert with ext_call.return_data[0 len return_data.size]
          require return_data.size >= 32
          if ext_call.return_data[12 len 20] != caller:
              revert with 0x8c379a000000000000000000000000000000000000000000000000000000000, 
                          32,
                          46,
                          0x44455243313135355472616461626c65236f6e6c794f776e65723a2043414c4c45525f49535f4e4f545f4f574e45,
                          mem[210 len 18]
  stor10[addr(_param1)] = 1

def renounceOwnership() payable: 
  if owner != caller:
      if not stor10[caller]:
          require ext_code.size(unknowncd7c0326Address)
          static call unknowncd7c0326Address.proxies(address param1) with:
                  gas gas_remaining wei
                 args owner
          if not ext_call.success:
              revert with ext_call.return_data[0 len return_data.size]
          require return_data.size >= 32
          if ext_call.return_data[12 len 20] != caller:
              revert with 0x8c379a000000000000000000000000000000000000000000000000000000000, 
                          32,
                          46,
                          0x44455243313135355472616461626c65236f6e6c794f776e65723a2043414c4c45525f49535f4e4f545f4f574e45,
                          mem[210 len 18]
  log OwnershipTransferred(
        address previousOwner=owner,
        address newOwner=0)
  owner = 0

def unknown24d88785(array _param1) payable: 
  require calldata.size - 4 >= 32
  require _param1 <= 4294967296
  require _param1 + 36 <= calldata.size
  require _param1.length <= 4294967296 and _param1 + _param1.length + 36 <= calldata.size
  if owner != caller:
      if not stor10[caller]:
          require ext_code.size(unknowncd7c0326Address)
          static call unknowncd7c0326Address.proxies(address param1) with:
                  gas gas_remaining wei
                 args owner
          if not ext_call.success:
              revert with ext_call.return_data[0 len return_data.size]
          require return_data.size >= 32
          if ext_call.return_data[12 len 20] != caller:
              revert with 0, 
                          32,
                          46,
                          0x44455243313135355472616461626c65236f6e6c794f776e65723a2043414c4c45525f49535f4e4f545f4f574e45,
                          mem[ceil32(_param1.length) + 242 len 18]
  unknownf923e8c3[] = Array(len=_param1.length, data=_param1[all])

def transferOwnership(address _newOwner) payable: 
  require calldata.size - 4 >= 32
  if owner != caller:
      if not stor10[caller]:
          require ext_code.size(unknowncd7c0326Address)
          static call unknowncd7c0326Address.proxies(address param1) with:
                  gas gas_remaining wei
                 args owner
          if not ext_call.success:
              revert with ext_call.return_data[0 len return_data.size]
          require return_data.size >= 32
          if ext_call.return_data[12 len 20] != caller:
              revert with 0x8c379a000000000000000000000000000000000000000000000000000000000, 
                          32,
                          46,
                          0x44455243313135355472616461626c65236f6e6c794f776e65723a2043414c4c45525f49535f4e4f545f4f574e45,
                          mem[210 len 18]
  if not _newOwner:
      revert with 0x8c379a000000000000000000000000000000000000000000000000000000000, 
                  32,
                  38,
                  0x544f776e61626c653a206e6577206f776e657220697320746865207a65726f20616464726573,
                  mem[202 len 26]
  log OwnershipTransferred(
        address previousOwner=owner,
        address newOwner=_newOwner)
  owner = _newOwner

def balanceOf(address _owner, uint256 _cardId) payable: 
  require calldata.size - 4 >= 64
  if not creator[_cardId]:
      if uint64(_cardId) != _owner:
          if not stor10[addr(_owner)]:
              require ext_code.size(unknowncd7c0326Address)
              static call unknowncd7c0326Address.proxies(address param1) with:
                      gas gas_remaining wei
                     args uint64(_cardId)
              if not ext_call.success:
                  revert with ext_call.return_data[0 len return_data.size]
              require return_data.size >= 32
              if ext_call.return_data_owner:
                  return stor0[addr(_owner)][_cardId]
  else:
      if creator[_cardId] != _owner:
          if not stor10[addr(_owner)]:
              require ext_code.size(unknowncd7c0326Address)
              static call unknowncd7c0326Address.proxies(address param1) with:
                      gas gas_remaining wei
                     args creator[_cardId]
              if not ext_call.success:
                  revert with ext_call.return_data[0 len return_data.size]
              require return_data.size >= 32
              if ext_call.return_data_owner:
                  return stor0[addr(_owner)][_cardId]
  if totalSupply[_cardId] > _cardId % 1099511627776:
      revert with 0, 'SafeMath#sub: UNDERFLOW'
  if stor0[addr(_owner)][_cardId] + (_cardId % 1099511627776) - totalSupply[_cardId] < stor0[addr(_owner)][_cardId]:
      revert with 0, 'SafeMath#add: OVERFLOW'
  return (stor0[addr(_owner)][_cardId] + (_cardId % 1099511627776) - totalSupply[_cardId])

def unknown91686f53(uint256 _param1, addr _param2) payable: 
  require calldata.size - 4 >= 64
  if not creator[_param1]:
      if uint64(_param1) != caller:
          if not stor10[caller]:
              require ext_code.size(unknowncd7c0326Address)
              static call unknowncd7c0326Address.proxies(address param1) with:
                      gas gas_remaining wei
                     args uint64(_param1)
              if not ext_call.success:
                  revert with ext_call.return_data[0 len return_data.size]
              require return_data.size >= 32
              if ext_call.return_data[12 len 20] != caller:
                  revert with 0x8c379a000000000000000000000000000000000000000000000000000000000, 
                              32,
                              53,
                              0x454173736574436f6e74726163745368617265642363726561746f724f6e6c793a204f4e4c595f43524541544f525f414c4c4f5745,
                              mem[217 len 11]
  else:
      if creator[_param1] != caller:
          if not stor10[caller]:
              require ext_code.size(unknowncd7c0326Address)
              static call unknowncd7c0326Address.proxies(address param1) with:
                      gas gas_remaining wei
                     args creator[_param1]
              if not ext_call.success:
                  revert with ext_call.return_data[0 len return_data.size]
              require return_data.size >= 32
              if ext_call.return_data[12 len 20] != caller:
                  revert with 0x8c379a000000000000000000000000000000000000000000000000000000000, 
                              32,
                              53,
                              0x454173736574436f6e74726163745368617265642363726561746f724f6e6c793a204f4e4c595f43524541544f525f414c4c4f5745,
                              mem[217 len 11]
  if not _param2:
      revert with 0x8c379a000000000000000000000000000000000000000000000000000000000, 
                  32,
                  48,
                  0x734173736574436f6e74726163745368617265642373657443726561746f723a20494e56414c49445f41444452455353,
                  mem[212 len 16]
  creator[_param1] = _param2
  log 0x39071c63: _param1, _param2

def balanceOfBatch(address[] _param1, uint256[] _param2) payable: 
  require calldata.size - 4 >= 64
  require _param1 <= 4294967296
  require _param1 + 36 <= calldata.size
  require _param1.length <= 4294967296 and _param1 + (32 * _param1.length) + 36 <= calldata.size
  mem[128 len 32 * _param1.length] = call.data[_param1 + 36 len 32 * _param1.length]
  require _param2 <= 4294967296
  require _param2 + 36 <= calldata.size
  require _param2.length <= 4294967296 and _param2 + (32 * _param2.length) + 36 <= calldata.size
  mem[(32 * _param1.length) + 128] = _param2.length
  mem[(32 * _param1.length) + 160 len 32 * _param2.length] = call.data[_param2 + 36 len 32 * _param2.length]
  if _param1.length != _param2.length:
      revert with 0, 
                  32,
                  44,
                  0x54455243313135352362616c616e63654f6642617463683a20494e56414c49445f41525241595f4c454e4754,
                  mem[(32 * _param1.length) + (32 * _param2.length) + 272 len 20]
  mem[(32 * _param1.length) + (32 * _param2.length) + 160] = _param1.length
  if _param1.length:
      mem[(32 * _param1.length) + (32 * _param2.length) + 192 len 32 * _param1.length] = code.data * _param1.length]
  idx = 0
  while idx < _param1.length:
      require idx < _param1.length
      require idx < _param2.length
      mem[0] = mem[(32 * idx) + (32 * _param1.length) + 160]
      mem[32] = sha3(mem[(32 * idx) + 140 len 20], 0)
      require idx < _param1.length
      mem[(32 * idx) + (32 * _param1.length) + (32 * _param2.length) + 192] = stor0[mem[(32 * idx) + 140 len 20]][mem[(32 * idx) + (32 * _param1.length) + 160]]
      idx = idx + 1
      continue 
  mem[(64 * _param1.length) + (32 * _param2.length) + 192] = 32
  mem[(64 * _param1.length) + (32 * _param2.length) + 224] = _param1.length
  mem[(64 * _param1.length) + (32 * _param2.length) + 256 len floor32(_param1.length)] = mem[(32 * _param1.length) + (32 * _param2.length) + 192 len floor32(_param1.length)]
  return memory
    from (64 * _param1.length) + (32 * _param2.length) + 192
     len (161 * _param1.length) + 64

def setURI(uint256 _id, string _uri) payable: 
  require calldata.size - 4 >= 64
  require _uri <= 4294967296
  require _uri + 36 <= calldata.size
  require _uri.length <= 4294967296 and _uri + _uri.length + 36 <= calldata.size
  mem[128 len _uri.length] = _uri[all]
  mem[_uri.length + 128] = 0
  if not creator[_id]:
      if uint64(_id) == caller:
          uri[_id][] = Array(len=_uri.length, data=_uri[all])
          mem[ceil32(_uri.length) + 128] = 32
          mem[ceil32(_uri.length) + 160] = _uri.length
          mem[ceil32(_uri.length) + 192 len ceil32(_uri.length)] = _uri[all], mem[_uri.length + 128 len ceil32(_uri.length) - _uri.length]
          if not _uri.length % 32:
              log 0x6bb7ff70: Mask(8 * -ceil32(_uri.length) + _uri.length + 32, 0, 0), mem[_uri.length + 160 len ceil32(_uri.length) + -_uri.length + 32], Mask(8 * _uri.length, -(8 * _uri.length) + 256, _uri[all], mem[_uri.length + 128 len ceil32(_uri.length) - _uri.length]) << (8 * _uri.length) - 256, _id
          else:
              mem[floor32(_uri.length) + ceil32(_uri.length) + 192] = mem[floor32(_uri.length) + ceil32(_uri.length) + -(_uri.length % 32) + 224 len _uri.length % 32]
              log 0x6bb7ff70: Mask(8 * -ceil32(_uri.length) + _uri.length + 32, 0, 0), mem[_uri.length + 160 len ceil32(_uri.length) + -_uri.length + 32], Mask(8 * ceil32(_uri.length), -(8 * ceil32(_uri.length)) + 256, _uri[all], mem[_uri.length + 128 len ceil32(_uri.length) - _uri.length]) << (8 * ceil32(_uri.length)) - 256, mem[(2 * ceil32(_uri.length)) + 192 len floor32(_uri.length) + -ceil32(_uri.length) + 32], _id
      else:
          if stor10[caller]:
              uri[_id][] = Array(len=_uri.length, data=_uri[all])
              mem[ceil32(_uri.length) + 128] = 32
              mem[ceil32(_uri.length) + 160] = _uri.length
              mem[ceil32(_uri.length) + 192 len ceil32(_uri.length)] = _uri[all], mem[_uri.length + 128 len ceil32(_uri.length) - _uri.length]
              if not _uri.length % 32:
                  log 0x6bb7ff70: Mask(8 * -ceil32(_uri.length) + _uri.length + 32, 0, 0), mem[_uri.length + 160 len ceil32(_uri.length) + -_uri.length + 32], Mask(8 * _uri.length, -(8 * _uri.length) + 256, _uri[all], mem[_uri.length + 128 len ceil32(_uri.length) - _uri.length]) << (8 * _uri.length) - 256, _id
              else:
                  mem[floor32(_uri.length) + ceil32(_uri.length) + 192] = mem[floor32(_uri.length) + ceil32(_uri.length) + -(_uri.length % 32) + 224 len _uri.length % 32]
                  log 0x6bb7ff70: Mask(8 * -ceil32(_uri.length) + _uri.length + 32, 0, 0), mem[_uri.length + 160 len ceil32(_uri.length) + -_uri.length + 32], Mask(8 * ceil32(_uri.length), -(8 * ceil32(_uri.length)) + 256, _uri[all], mem[_uri.length + 128 len ceil32(_uri.length) - _uri.length]) << (8 * ceil32(_uri.length)) - 256, mem[(2 * ceil32(_uri.length)) + 192 len floor32(_uri.length) + -ceil32(_uri.length) + 32], _id
          else:
              require ext_code.size(unknowncd7c0326Address)
              static call unknowncd7c0326Address.proxies(address param1) with:
                      gas gas_remaining wei
                     args uint64(_id)
              if not ext_call.success:
                  revert with ext_call.return_data[0 len return_data.size]
              require return_data.size >= 32
              if ext_call.return_data[12 len 20] != caller:
                  revert with 0, 
                              32,
                              53,
                              0x454173736574436f6e74726163745368617265642363726561746f724f6e6c793a204f4e4c595f43524541544f525f414c4c4f5745,
                              mem[ceil32(_uri.length) + 249 len 11]
              uri[_id][] = Array(len=_uri.length, data=_uri[all])
              mem[ceil32(_uri.length) + 128] = 32
              mem[ceil32(_uri.length) + 192 len ceil32(_uri.length)] = _uri[all], mem[_uri.length + 128 len ceil32(_uri.length) - _uri.length]
              if not _uri.length % 32:
                  log 0x6bb7ff70: 0, 32, _uri.length, Mask(8 * _uri.length, -(8 * _uri.length) + 256, _uri[all], mem[_uri.length + 128 len ceil32(_uri.length) - _uri.length]) << (8 * _uri.length) - 256, _id
              else:
                  mem[floor32(_uri.length) + ceil32(_uri.length) + 192] = mem[floor32(_uri.length) + ceil32(_uri.length) + -(_uri.length % 32) + 224 len _uri.length % 32]
                  log 0x6bb7ff70: 0, 32, _uri.length, Mask(8 * ceil32(_uri.length), -(8 * ceil32(_uri.length)) + 256, _uri[all], mem[_uri.length + 128 len ceil32(_uri.length) - _uri.length]) << (8 * ceil32(_uri.length)) - 256, mem[(2 * ceil32(_uri.length)) + 192 len floor32(_uri.length) + -ceil32(_uri.length) + 32], _id
  else:
      if creator[_id] == caller:
          uri[_id][] = Array(len=_uri.length, data=_uri[all])
          mem[ceil32(_uri.length) + 128] = 32
          mem[ceil32(_uri.length) + 160] = _uri.length
          mem[ceil32(_uri.length) + 192 len ceil32(_uri.length)] = _uri[all], mem[_uri.length + 128 len ceil32(_uri.length) - _uri.length]
          if not _uri.length % 32:
              log 0x6bb7ff70: Mask(8 * -ceil32(_uri.length) + _uri.length + 32, 0, 0), mem[_uri.length + 160 len ceil32(_uri.length) + -_uri.length + 32], Mask(8 * _uri.length, -(8 * _uri.length) + 256, _uri[all], mem[_uri.length + 128 len ceil32(_uri.length) - _uri.length]) << (8 * _uri.length) - 256, _id
          else:
              mem[floor32(_uri.length) + ceil32(_uri.length) + 192] = mem[floor32(_uri.length) + ceil32(_uri.length) + -(_uri.length % 32) + 224 len _uri.length % 32]
              log 0x6bb7ff70: Mask(8 * -ceil32(_uri.length) + _uri.length + 32, 0, 0), mem[_uri.length + 160 len ceil32(_uri.length) + -_uri.length + 32], Mask(8 * ceil32(_uri.length), -(8 * ceil32(_uri.length)) + 256, _uri[all], mem[_uri.length + 128 len ceil32(_uri.length) - _uri.length]) << (8 * ceil32(_uri.length)) - 256, mem[(2 * ceil32(_uri.length)) + 192 len floor32(_uri.length) + -ceil32(_uri.length) + 32], _id
      else:
          if stor10[caller]:
              uri[_id][] = Array(len=_uri.length, data=_uri[all])
              mem[ceil32(_uri.length) + 128] = 32
              mem[ceil32(_uri.length) + 160] = _uri.length
              mem[ceil32(_uri.length) + 192 len ceil32(_uri.length)] = _uri[all], mem[_uri.length + 128 len ceil32(_uri.length) - _uri.length]
              if not _uri.length % 32:
                  log 0x6bb7ff70: Mask(8 * -ceil32(_uri.length) + _uri.length + 32, 0, 0), mem[_uri.length + 160 len ceil32(_uri.length) + -_uri.length + 32], Mask(8 * _uri.length, -(8 * _uri.length) + 256, _uri[all], mem[_uri.length + 128 len ceil32(_uri.length) - _uri.length]) << (8 * _uri.length) - 256, _id
              else:
                  mem[floor32(_uri.length) + ceil32(_uri.length) + 192] = mem[floor32(_uri.length) + ceil32(_uri.length) + -(_uri.length % 32) + 224 len _uri.length % 32]
                  log 0x6bb7ff70: Mask(8 * -ceil32(_uri.length) + _uri.length + 32, 0, 0), mem[_uri.length + 160 len ceil32(_uri.length) + -_uri.length + 32], Mask(8 * ceil32(_uri.length), -(8 * ceil32(_uri.length)) + 256, _uri[all], mem[_uri.length + 128 len ceil32(_uri.length) - _uri.length]) << (8 * ceil32(_uri.length)) - 256, mem[(2 * ceil32(_uri.length)) + 192 len floor32(_uri.length) + -ceil32(_uri.length) + 32], _id
          else:
              require ext_code.size(unknowncd7c0326Address)
              static call unknowncd7c0326Address.proxies(address param1) with:
                      gas gas_remaining wei
                     args creator[_id]
              if not ext_call.success:
                  revert with ext_call.return_data[0 len return_data.size]
              require return_data.size >= 32
              if ext_call.return_data[12 len 20] != caller:
                  revert with 0, 
                              32,
                              53,
                              0x454173736574436f6e74726163745368617265642363726561746f724f6e6c793a204f4e4c595f43524541544f525f414c4c4f5745,
                              mem[ceil32(_uri.length) + 249 len 11]
              uri[_id][] = Array(len=_uri.length, data=_uri[all])
              mem[ceil32(_uri.length) + 128] = 32
              mem[ceil32(_uri.length) + 192 len ceil32(_uri.length)] = _uri[all], mem[_uri.length + 128 len ceil32(_uri.length) - _uri.length]
              if not _uri.length % 32:
                  log 0x6bb7ff70: 0, 32, _uri.length, Mask(8 * _uri.length, -(8 * _uri.length) + 256, _uri[all], mem[_uri.length + 128 len ceil32(_uri.length) - _uri.length]) << (8 * _uri.length) - 256, _id
              else:
                  mem[floor32(_uri.length) + ceil32(_uri.length) + 192] = mem[floor32(_uri.length) + ceil32(_uri.length) + -(_uri.length % 32) + 224 len _uri.length % 32]
                  log 0x6bb7ff70: 0, 32, _uri.length, Mask(8 * ceil32(_uri.length), -(8 * ceil32(_uri.length)) + 256, _uri[all], mem[_uri.length + 128 len ceil32(_uri.length) - _uri.length]) << (8 * ceil32(_uri.length)) - 256, mem[(2 * ceil32(_uri.length)) + 192 len floor32(_uri.length) + -ceil32(_uri.length) + 32], _id

def safeBatchTransferFrom(address _from, address _to, uint256[] _ids, uint256[] _values, bytes _data) payable: 
  require calldata.size - 4 >= 160
  require _ids <= 4294967296
  require _ids + 36 <= calldata.size
  require _ids.length <= 4294967296 and _ids + (32 * _ids.length) + 36 <= calldata.size
  mem[128 len 32 * _ids.length] = call.data[_ids + 36 len 32 * _ids.length]
  require _values <= 4294967296
  require _values + 36 <= calldata.size
  require _values.length <= 4294967296 and _values + (32 * _values.length) + 36 <= calldata.size
  mem[(32 * _ids.length) + 128] = _values.length
  mem[(32 * _ids.length) + 160 len 32 * _values.length] = call.data[_values + 36 len 32 * _values.length]
  require _data <= 4294967296
  require _data + 36 <= calldata.size
  require _data.length <= 4294967296 and _data + _data.length + 36 <= calldata.size
  mem[(32 * _ids.length) + (32 * _values.length) + 160] = _data.length
  mem[(32 * _ids.length) + (32 * _values.length) + 192 len _data.length] = _data[all]
  mem[(32 * _ids.length) + (32 * _values.length) + _data.length + 192] = 0
  if caller == _from:
      if not _to:
          revert with 0, 
                      32,
                      48,
                      0x4845524331313535237361666542617463685472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                      mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 308 len 16]
      if _ids.length != _values.length:
          revert with 0, 
                      32,
                      53,
                      0x5245524331313535235f7361666542617463685472616e7366657246726f6d3a20494e56414c49445f4152524159535f4c454e4754,
                      mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 313 len 11]
      idx = 0
      while idx < _ids.length:
          require idx < _values.length
          require idx < _ids.length
          if mem[(32 * idx) + (32 * _ids.length) + 160] > stor0[addr(_from)][mem[(32 * idx) + 128]]:
              revert with 0, 'SafeMath#sub: UNDERFLOW'
          require idx < _ids.length
          stor0[addr(_from)][mem[(32 * idx) + 128]] -= mem[(32 * idx) + (32 * _ids.length) + 160]
          require idx < _values.length
          require idx < _ids.length
          if stor0[addr(_to)][mem[(32 * idx) + 128]] + mem[(32 * idx) + (32 * _ids.length) + 160] < stor0[addr(_to)][mem[(32 * idx) + 128]]:
              revert with 0, 'SafeMath#add: OVERFLOW'
          require idx < _ids.length
          mem[0] = mem[(32 * idx) + 128]
          mem[32] = sha3(addr(_to), 0)
          stor0[addr(_to)][mem[(32 * idx) + 128]] += mem[(32 * idx) + (32 * _ids.length) + 160]
          idx = idx + 1
          continue 
      mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 192] = 64
      mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 288 len floor32(_ids.length)] = call.data[_ids + 36 len floor32(_ids.length)]
      mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 224] = (32 * _ids.length) + 96
      mem[(64 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 288] = _values.length
      mem[(64 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 320 len floor32(_values.length)] = call.data[_values + 36 len floor32(_values.length)]
      log 0x4a39dc06: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[(32 * _ids.length) + (32 * _values.length) + _data.length + 224 len ceil32(_data.length) + -_data.length + 32], _ids.length, call.data[_ids + 36 len floor32(_ids.length)], mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + floor32(_ids.length) + 288 len (32 * _ids.length) + (32 * _values.length) + -floor32(_ids.length) + 32], caller, _from, _to
  else:
      if stor10[caller]:
          if not _to:
              revert with 0, 
                          32,
                          48,
                          0x4845524331313535237361666542617463685472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                          mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 308 len 16]
          if _ids.length != _values.length:
              revert with 0, 
                          32,
                          53,
                          0x5245524331313535235f7361666542617463685472616e7366657246726f6d3a20494e56414c49445f4152524159535f4c454e4754,
                          mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 313 len 11]
          idx = 0
          while idx < _ids.length:
              require idx < _values.length
              require idx < _ids.length
              if mem[(32 * idx) + (32 * _ids.length) + 160] > stor0[addr(_from)][mem[(32 * idx) + 128]]:
                  revert with 0, 'SafeMath#sub: UNDERFLOW'
              require idx < _ids.length
              stor0[addr(_from)][mem[(32 * idx) + 128]] -= mem[(32 * idx) + (32 * _ids.length) + 160]
              require idx < _values.length
              require idx < _ids.length
              if stor0[addr(_to)][mem[(32 * idx) + 128]] + mem[(32 * idx) + (32 * _ids.length) + 160] < stor0[addr(_to)][mem[(32 * idx) + 128]]:
                  revert with 0, 'SafeMath#add: OVERFLOW'
              require idx < _ids.length
              mem[0] = mem[(32 * idx) + 128]
              mem[32] = sha3(addr(_to), 0)
              stor0[addr(_to)][mem[(32 * idx) + 128]] += mem[(32 * idx) + (32 * _ids.length) + 160]
              idx = idx + 1
              continue 
          mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 192] = 64
          mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 288 len floor32(_ids.length)] = call.data[_ids + 36 len floor32(_ids.length)]
          mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 224] = (32 * _ids.length) + 96
          mem[(64 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 288] = _values.length
          mem[(64 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 320 len floor32(_values.length)] = call.data[_values + 36 len floor32(_values.length)]
          log 0x4a39dc06: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[(32 * _ids.length) + (32 * _values.length) + _data.length + 224 len ceil32(_data.length) + -_data.length + 32], _ids.length, call.data[_ids + 36 len floor32(_ids.length)], mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + floor32(_ids.length) + 288 len (32 * _ids.length) + (32 * _values.length) + -floor32(_ids.length) + 32], caller, _from, _to
      else:
          mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 196] = _from
          require ext_code.size(unknowncd7c0326Address)
          static call unknowncd7c0326Address.proxies(address param1) with:
                  gas gas_remaining wei
                 args _from
          mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 192] = ext_call.return_data[0]
          if not ext_call.success:
              revert with ext_call.return_data[0 len return_data.size]
          require return_data.size >= 32
          if ext_call.return_data[12 len 20] != caller:
              if not stor1[addr(_from)][caller]:
                  revert with 0, 
                              32,
                              47,
                              0x4845524331313535237361666542617463685472616e7366657246726f6d3a20494e56414c49445f4f50455241544f,
                              mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 307 len 17]
          if not _to:
              revert with 0, 
                          32,
                          48,
                          0x4845524331313535237361666542617463685472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                          mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 308 len 16]
          if _ids.length != _values.length:
              revert with 0, 
                          32,
                          53,
                          0x5245524331313535235f7361666542617463685472616e7366657246726f6d3a20494e56414c49445f4152524159535f4c454e4754,
                          mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 313 len 11]
          idx = 0
          while idx < _ids.length:
              require idx < _values.length
              require idx < _ids.length
              if mem[(32 * idx) + (32 * _ids.length) + 160] > stor0[addr(_from)][mem[(32 * idx) + 128]]:
                  revert with 0, 'SafeMath#sub: UNDERFLOW'
              require idx < _ids.length
              stor0[addr(_from)][mem[(32 * idx) + 128]] -= mem[(32 * idx) + (32 * _ids.length) + 160]
              require idx < _values.length
              require idx < _ids.length
              if stor0[addr(_to)][mem[(32 * idx) + 128]] + mem[(32 * idx) + (32 * _ids.length) + 160] < stor0[addr(_to)][mem[(32 * idx) + 128]]:
                  revert with 0, 'SafeMath#add: OVERFLOW'
              require idx < _ids.length
              mem[0] = mem[(32 * idx) + 128]
              mem[32] = sha3(addr(_to), 0)
              stor0[addr(_to)][mem[(32 * idx) + 128]] += mem[(32 * idx) + (32 * _ids.length) + 160]
              idx = idx + 1
              continue 
          mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 288 len floor32(_ids.length)] = call.data[_ids + 36 len floor32(_ids.length)]
          mem[(64 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 288] = _values.length
          mem[(64 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 320 len floor32(_values.length)] = call.data[_values + 36 len floor32(_values.length)]
          log 0x4a39dc06: 0, 64, (32 * _ids.length) + 96, _ids.length, call.data[_ids + 36 len floor32(_ids.length)], mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + floor32(_ids.length) + 288 len (32 * _ids.length) + (32 * _values.length) + -floor32(_ids.length) + 32], caller, _from, _to
  if ext_code.hash(_to):
      if ext_code.hash(_to) != 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
          mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 192] = 0xbc197c8100000000000000000000000000000000000000000000000000000000
          mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 388 len floor32(_ids.length)] = call.data[_ids + 36 len floor32(_ids.length)]
          mem[(64 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 388] = _values.length
          mem[(64 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + 420 len floor32(_values.length)] = call.data[_values + 36 len floor32(_values.length)]
          mem[(64 * _values.length) + (64 * _ids.length) + ceil32(_data.length) + 420] = _data.length
          mem[(64 * _values.length) + (64 * _ids.length) + ceil32(_data.length) + 452 len ceil32(_data.length)] = _data[all], mem[(32 * _ids.length) + (32 * _values.length) + _data.length + 192 len ceil32(_data.length) - _data.length]
          if not _data.length % 32:
              require ext_code.size(_to)
              call _to with:
                   gas gas_remaining wei
                  args caller, addr(_from), Array(len=_ids.length, data=call.data[_ids + 36 len floor32(_ids.length)], mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + floor32(_ids.length) + 388 len (32 * _ids.length) + (32 * _values.length) + _data.length + -floor32(_ids.length) + 64]), (32 * _ids.length) + 192, (32 * _values.length) + (32 * _ids.length) + 224
          else:
              mem[floor32(_data.length) + (64 * _values.length) + (64 * _ids.length) + ceil32(_data.length) + 452] = mem[floor32(_data.length) + (64 * _values.length) + (64 * _ids.length) + ceil32(_data.length) + -(_data.length % 32) + 484 len _data.length % 32]
              require ext_code.size(_to)
              call _to with:
                   gas gas_remaining wei
                  args caller, addr(_from), Array(len=_ids.length, data=call.data[_ids + 36 len floor32(_ids.length)], mem[(32 * _ids.length) + (32 * _values.length) + ceil32(_data.length) + floor32(_ids.length) + 388 len (32 * _ids.length) + (32 * _values.length) + floor32(_data.length) + -floor32(_ids.length) + 96]), (32 * _ids.length) + 192, (32 * _values.length) + (32 * _ids.length) + 224
          if not ext_call.success:
              revert with ext_call.return_data[0 len return_data.size]
          require return_data.size >= 32
          if Mask(32, 224, ext_call.return_data[0]) != 0xbc197c8100000000000000000000000000000000000000000000000000000000:
              revert with 0, 
                          32,
                          63,
                          0x5245524331313535235f63616c6c6f6e45524331313535426174636852656365697665643a20494e56414c49445f4f4e5f524543454956455f4d4553534147,
                          uint8((32 * _ids.length) + 192)

def unknownb48ab8b6(addr _param1, array _param2, array _param3, array _param4) payable: 
  require calldata.size - 4 >= 128
  require _param2 <= 4294967296
  require _param2 + 36 <= calldata.size
  require _param2.length <= 4294967296 and _param2 + (32 * _param2.length) + 36 <= calldata.size
  mem[96] = _param2.length
  mem[128 len 32 * _param2.length] = call.data[_param2 + 36 len 32 * _param2.length]
  require _param3 <= 4294967296
  require _param3 + 36 <= calldata.size
  require _param3.length <= 4294967296 and _param3 + (32 * _param3.length) + 36 <= calldata.size
  mem[(32 * _param2.length) + 128] = _param3.length
  mem[(32 * _param2.length) + 160 len 32 * _param3.length] = call.data[_param3 + 36 len 32 * _param3.length]
  require _param4 <= 4294967296
  require _param4 + 36 <= calldata.size
  require _param4.length <= 4294967296 and _param4 + _param4.length + 36 <= calldata.size
  mem[64] = (32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 192
  mem[(32 * _param2.length) + (32 * _param3.length) + 160] = _param4.length
  mem[(32 * _param2.length) + (32 * _param3.length) + 192 len _param4.length] = _param4[all]
  mem[(32 * _param2.length) + (32 * _param3.length) + _param4.length + 192] = 0
  if not stor9:
      revert with 0, 'ReentrancyGuard: reentrant call'
  stor9 = 0
  idx = 0
  while idx < _param2.length:
      require idx < _param2.length
      _240 = mem[(32 * idx) + 128]
      require idx < _param3.length
      _243 = mem[(32 * idx) + (32 * _param2.length) + 160]
      if not creator[mem[(32 * idx) + 128]]:
          if mem[(32 * idx) + 140 len 8] == caller:
              mem[0] = mem[(32 * idx) + 128]
              mem[32] = 6
              if totalSupply[mem[(32 * idx) + 128]] > mem[(32 * idx) + 155 len 5]:
                  revert with 0, 'SafeMath#sub: UNDERFLOW'
              if mem[(32 * idx) + 155 len 5] - totalSupply[mem[(32 * idx) + 128]] < mem[(32 * idx) + (32 * _param2.length) + 160]:
                  revert with 0, 
                              32,
                              53,
                              0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a20535550504c595f45584345454445,
                              mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 313 len 11]
          else:
              if stor10[caller]:
                  mem[0] = mem[(32 * idx) + 128]
                  mem[32] = 6
                  if totalSupply[mem[(32 * idx) + 128]] > mem[(32 * idx) + 155 len 5]:
                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                  if mem[(32 * idx) + 155 len 5] - totalSupply[mem[(32 * idx) + 128]] < mem[(32 * idx) + (32 * _param2.length) + 160]:
                      revert with 0, 
                                  32,
                                  53,
                                  0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a20535550504c595f45584345454445,
                                  mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 313 len 11]
              else:
                  mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 196] = mem[(32 * idx) + 140 len 8]
                  require ext_code.size(unknowncd7c0326Address)
                  static call unknowncd7c0326Address.proxies(address param1) with:
                          gas gas_remaining wei
                         args (Mask(64, 96, _240) >> 96)
                  mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 192] = ext_call.return_data[0]
                  if not ext_call.success:
                      revert with ext_call.return_data[0 len return_data.size]
                  require return_data.size >= 32
                  if addr(ext_call.return_data) != caller:
                      revert with 0, 
                                  32,
                                  58,
                                  0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a204f4e4c595f43524541544f525f414c4c4f5745,
                                  mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 318 len 6]
                  mem[0] = _240
                  mem[32] = 6
                  if totalSupply[_240] > _240 % 1099511627776:
                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                  if (_240 % 1099511627776) - totalSupply[_240] < _243:
                      revert with 0, 
                                  32,
                                  53,
                                  0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a20535550504c595f45584345454445,
                                  mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 313 len 11]
      else:
          if creator[mem[(32 * idx) + 128]] == caller:
              mem[0] = mem[(32 * idx) + 128]
              mem[32] = 6
              if totalSupply[mem[(32 * idx) + 128]] > mem[(32 * idx) + 155 len 5]:
                  revert with 0, 'SafeMath#sub: UNDERFLOW'
              if mem[(32 * idx) + 155 len 5] - totalSupply[mem[(32 * idx) + 128]] < mem[(32 * idx) + (32 * _param2.length) + 160]:
                  revert with 0, 
                              32,
                              53,
                              0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a20535550504c595f45584345454445,
                              mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 313 len 11]
          else:
              _246 = sha3(mem[(32 * idx) + 128], 11)
              if stor10[caller]:
                  mem[0] = mem[(32 * idx) + 128]
                  mem[32] = 6
                  if totalSupply[mem[(32 * idx) + 128]] > mem[(32 * idx) + 155 len 5]:
                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                  if mem[(32 * idx) + 155 len 5] - totalSupply[mem[(32 * idx) + 128]] < mem[(32 * idx) + (32 * _param2.length) + 160]:
                      revert with 0, 
                                  32,
                                  53,
                                  0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a20535550504c595f45584345454445,
                                  mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 313 len 11]
              else:
                  mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 196] = creator[mem[(32 * idx) + 128]]
                  require ext_code.size(unknowncd7c0326Address)
                  static call unknowncd7c0326Address.proxies(address param1) with:
                          gas gas_remaining wei
                         args addr(stor[_246])
                  mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 192] = ext_call.return_data[0]
                  if not ext_call.success:
                      revert with ext_call.return_data[0 len return_data.size]
                  require return_data.size >= 32
                  if addr(ext_call.return_data) != caller:
                      revert with 0, 
                                  32,
                                  58,
                                  0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a204f4e4c595f43524541544f525f414c4c4f5745,
                                  mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 318 len 6]
                  mem[0] = _240
                  mem[32] = 6
                  if totalSupply[_240] > _240 % 1099511627776:
                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                  if (_240 % 1099511627776) - totalSupply[_240] < _243:
                      revert with 0, 
                                  32,
                                  53,
                                  0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a20535550504c595f45584345454445,
                                  mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 313 len 11]
      idx = idx + 1
      continue 
  if _param2.length != _param3.length:
      revert with 0, 
                  32,
                  48,
                  0x48455243313135355472616461626c652362617463684d696e743a20494e56414c49445f4152524159535f4c454e4754,
                  mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 308 len 16]
  require 0 < _param2.length
  idx = 0
  while idx < _param2.length:
      require idx < _param2.length
      if mem[(32 * idx) + 140 len 8] != mem[140 len 8]:
          revert with 0, 
                      32,
                      55,
                      0x52455243313135355472616461626c652362617463684d696e743a204d554c5449504c455f4f524947494e535f4e4f545f414c4c4f5745,
                      mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 315 len 9]
      require idx < _param3.length
      if stor0[addr(_param1)][mem[(32 * idx) + 128]] + mem[(32 * idx) + (32 * _param2.length) + 160] < stor0[addr(_param1)][mem[(32 * idx) + 128]]:
          revert with 0, 'SafeMath#add: OVERFLOW'
      stor0[addr(_param1)][mem[(32 * idx) + 128]] += mem[(32 * idx) + (32 * _param2.length) + 160]
      require idx < _param3.length
      if totalSupply[mem[(32 * idx) + 128]] + mem[(32 * idx) + (32 * _param2.length) + 160] < totalSupply[mem[(32 * idx) + 128]]:
          revert with 0, 'SafeMath#add: OVERFLOW'
      mem[0] = mem[(32 * idx) + 128]
      mem[32] = 6
      totalSupply[mem[(32 * idx) + 128]] += mem[(32 * idx) + (32 * _param2.length) + 160]
      idx = idx + 1
      continue 
  mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 192] = 64
  mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 256] = _param2.length
  mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 288 len floor32(_param2.length)] = call.data[_param2 + 36 len floor32(_param2.length)]
  mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 224] = (32 * _param2.length) + 96
  mem[(64 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 288] = _param3.length
  mem[(64 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 320 len floor32(_param3.length)] = call.data[_param3 + 36 len floor32(_param3.length)]
  log 0x4a39dc06: Array(len=_param2.length, data=call.data[_param2 + 36 len floor32(_param2.length)], mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + floor32(_param2.length) + 288 len (32 * _param2.length) + (32 * _param3.length) + -floor32(_param2.length) + 32]), (32 * _param2.length) + 96, caller, mem1
  if not ext_code.hash(_param1):
      if _param4.length > 1:
          idx = 0
          while idx < _param2.length:
              require idx < mem[96]
              _921 = mem[(32 * idx) + 128]
              mem[32] = 8
              mem[0] = sha3(mem[(32 * idx) + 128], 8)
              uri[mem[(32 * idx) + 128]] = (2 * mem[(32 * _param2.length) + (32 * _param3.length) + 160]) + 1
              t = sha3(sha3(mem[(32 * idx) + 128], 8))
              s = (32 * _param2.length) + (32 * _param3.length) + 192
              while (32 * _param2.length) + (32 * _param3.length) + mem[(32 * _param2.length) + (32 * _param3.length) + 160] + 192 > s:
                  uint256(stor[t]) = mem[s]
                  t = t + 1
                  s = s + 32
                  continue 
              s = sha3(sha3(mem[(32 * idx) + 128], 8)) + (Mask(251, 0, mem[(32 * _param2.length) + (32 * _param3.length) + 160] + 31) >> 5)
              while sha3(sha3(mem[(32 * idx) + 128], 8)) + (uri[mem[(32 * idx) + 128]].length + 31 / 32) > s:
                  uint256(stor[s]) = 0
                  s = s + 1
                  continue 
              _1189 = mem[64]
              mem[mem[64]] = 32
              mem[mem[64] + 32] = mem[(32 * _param2.length) + (32 * _param3.length) + 160]
              _1191 = mem[(32 * _param2.length) + (32 * _param3.length) + 160]
              s = 0
              while s < _1191:
                  mem[_1189 + s + 64] = mem[(32 * _param2.length) + (32 * _param3.length) + s + 192]
                  s = s + 32
                  continue 
              if not _1191 % 32:
                  log 0x6bb7ff70: mem[memem
              else:
                  mem[floor32(_1191) + _1189 + 64] = mem[floor32(_1191) + _1189 + -(_1191 % 32) + 96 len _1191 % 32]
                  log 0x6bb7ff70: mem[memem
              idx = idx + 1
              continue 
  else:
      if ext_code.hash(_param1) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
          if _param4.length > 1:
              idx = 0
              while idx < _param2.length:
                  require idx < mem[96]
                  _922 = mem[(32 * idx) + 128]
                  mem[32] = 8
                  mem[0] = sha3(mem[(32 * idx) + 128], 8)
                  uri[mem[(32 * idx) + 128]] = (2 * mem[(32 * _param2.length) + (32 * _param3.length) + 160]) + 1
                  t = sha3(sha3(mem[(32 * idx) + 128], 8))
                  s = (32 * _param2.length) + (32 * _param3.length) + 192
                  while (32 * _param2.length) + (32 * _param3.length) + mem[(32 * _param2.length) + (32 * _param3.length) + 160] + 192 > s:
                      uint256(stor[t]) = mem[s]
                      t = t + 1
                      s = s + 32
                      continue 
                  s = sha3(sha3(mem[(32 * idx) + 128], 8)) + (Mask(251, 0, mem[(32 * _param2.length) + (32 * _param3.length) + 160] + 31) >> 5)
                  while sha3(sha3(mem[(32 * idx) + 128], 8)) + (uri[mem[(32 * idx) + 128]].length + 31 / 32) > s:
                      uint256(stor[s]) = 0
                      s = s + 1
                      continue 
                  _1192 = mem[64]
                  mem[mem[64]] = 32
                  mem[mem[64] + 32] = mem[(32 * _param2.length) + (32 * _param3.length) + 160]
                  _1194 = mem[(32 * _param2.length) + (32 * _param3.length) + 160]
                  s = 0
                  while s < _1194:
                      mem[_1192 + s + 64] = mem[(32 * _param2.length) + (32 * _param3.length) + s + 192]
                      s = s + 32
                      continue 
                  if not _1194 % 32:
                      log 0x6bb7ff70: mem[memem
                  else:
                      mem[floor32(_1194) + _1192 + 64] = mem[floor32(_1194) + _1192 + -(_1194 % 32) + 96 len _1194 % 32]
                      log 0x6bb7ff70: mem[memem
                  idx = idx + 1
                  continue 
      else:
          mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 192] = 0xbc197c8100000000000000000000000000000000000000000000000000000000
          mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 196] = caller
          mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 228] = mem[140 len 8]
          mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 260] = 160
          mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 356] = _param2.length
          mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 388 len floor32(_param2.length)] = call.data[_param2 + 36 len floor32(_param2.length)]
          mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 292] = (32 * _param2.length) + 192
          mem[(64 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 388] = _param3.length
          mem[(64 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 420 len floor32(_param3.length)] = call.data[_param3 + 36 len floor32(_param3.length)]
          mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 324] = (32 * _param3.length) + (32 * _param2.length) + 224
          mem[(64 * _param3.length) + (64 * _param2.length) + ceil32(_param4.length) + 420] = _param4.length
          mem[(64 * _param3.length) + (64 * _param2.length) + ceil32(_param4.length) + 452 len ceil32(_param4.length)] = _param4[all], mem[(32 * _param2.length) + (32 * _param3.length) + _param4.length + 192 len ceil32(_param4.length) - _param4.length]
          if not _param4.length % 32:
              require ext_code.size(_param1)
              call _param1.onERC1155BatchReceived(address param1, address param2, uint256[] param3, uint256[] param4, bytes param5) with:
                   gas gas_remaining wei
                  args caller, mem[140 len 8], Array(len=_param2.length, data=call.data[_param2 + 36 len floor32(_param2.length)], mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + floor32(_param2.length) + 388 len (32 * _param2.length) + (32 * _param3.length) + _param4.length + -floor32(_param2.length) + 64]), (32 * _param2.length) + 192, (32 * _param3.length) + (32 * _param2.length) + 224
              mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 192] = ext_call.return_data[0]
              if not ext_call.success:
                  revert with ext_call.return_data[0 len return_data.size]
              require return_data.size >= 32
              if Mask(32, 224, ext_call.return_data[0]) != 0xbc197c8100000000000000000000000000000000000000000000000000000000:
                  revert with 0, 
                              32,
                              63,
                              0x5245524331313535235f63616c6c6f6e45524331313535426174636852656365697665643a20494e56414c49445f4f4e5f524543454956455f4d4553534147,
                              uint8((32 * _param2.length) + 192)
              if _param4.length > 1:
                  idx = 0
                  while idx < _param2.length:
                      require idx < mem[96]
                      _1281 = mem[(32 * idx) + 128]
                      mem[32] = 8
                      mem[0] = sha3(mem[(32 * idx) + 128], 8)
                      uri[mem[(32 * idx) + 128]] = (2 * mem[(32 * _param2.length) + (32 * _param3.length) + 160]) + 1
                      t = sha3(sha3(mem[(32 * idx) + 128], 8))
                      s = (32 * _param2.length) + (32 * _param3.length) + 192
                      while (32 * _param2.length) + (32 * _param3.length) + mem[(32 * _param2.length) + (32 * _param3.length) + 160] + 192 > s:
                          uint256(stor[t]) = mem[s]
                          t = t + 1
                          s = s + 32
                          continue 
                      s = sha3(sha3(mem[(32 * idx) + 128], 8)) + (Mask(251, 0, mem[(32 * _param2.length) + (32 * _param3.length) + 160] + 31) >> 5)
                      while sha3(sha3(mem[(32 * idx) + 128], 8)) + (uri[mem[(32 * idx) + 128]].length + 31 / 32) > s:
                          uint256(stor[s]) = 0
                          s = s + 1
                          continue 
                      _1397 = mem[64]
                      mem[mem[64]] = 32
                      mem[mem[64] + 32] = mem[(32 * _param2.length) + (32 * _param3.length) + 160]
                      _1399 = mem[(32 * _param2.length) + (32 * _param3.length) + 160]
                      s = 0
                      while s < _1399:
                          mem[_1397 + s + 64] = mem[(32 * _param2.length) + (32 * _param3.length) + s + 192]
                          s = s + 32
                          continue 
                      if not _1399 % 32:
                          log 0x6bb7ff70: mem[memem
                      else:
                          mem[floor32(_1399) + _1397 + 64] = mem[floor32(_1399) + _1397 + -(_1399 % 32) + 96 len _1399 % 32]
                          log 0x6bb7ff70: mem[memem
                      idx = idx + 1
                      continue 
          else:
              mem[floor32(_param4.length) + (64 * _param3.length) + (64 * _param2.length) + ceil32(_param4.length) + 452] = mem[floor32(_param4.length) + (64 * _param3.length) + (64 * _param2.length) + ceil32(_param4.length) + -(_param4.length % 32) + 484 len _param4.length % 32]
              require ext_code.size(_param1)
              call _param1.onERC1155BatchReceived(address param1, address param2, uint256[] param3, uint256[] param4, bytes param5) with:
                   gas gas_remaining wei
                  args caller, mem[140 len 8], Array(len=_param2.length, data=call.data[_param2 + 36 len floor32(_param2.length)], mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + floor32(_param2.length) + 388 len (32 * _param2.length) + (32 * _param3.length) + floor32(_param4.length) + -floor32(_param2.length) + 96]), (32 * _param2.length) + 192, (32 * _param3.length) + (32 * _param2.length) + 224
              mem[(32 * _param2.length) + (32 * _param3.length) + ceil32(_param4.length) + 192] = ext_call.return_data[0]
              if not ext_call.success:
                  revert with ext_call.return_data[0 len return_data.size]
              require return_data.size >= 32
              if Mask(32, 224, ext_call.return_data[0]) != 0xbc197c8100000000000000000000000000000000000000000000000000000000:
                  revert with 0, 
                              32,
                              63,
                              0x5245524331313535235f63616c6c6f6e45524331313535426174636852656365697665643a20494e56414c49445f4f4e5f524543454956455f4d4553534147,
                              uint8((32 * _param2.length) + 192)
              if _param4.length > 1:
                  idx = 0
                  while idx < _param2.length:
                      require idx < mem[96]
                      _1282 = mem[(32 * idx) + 128]
                      mem[32] = 8
                      mem[0] = sha3(mem[(32 * idx) + 128], 8)
                      uri[mem[(32 * idx) + 128]] = (2 * mem[(32 * _param2.length) + (32 * _param3.length) + 160]) + 1
                      t = sha3(sha3(mem[(32 * idx) + 128], 8))
                      s = (32 * _param2.length) + (32 * _param3.length) + 192
                      while (32 * _param2.length) + (32 * _param3.length) + mem[(32 * _param2.length) + (32 * _param3.length) + 160] + 192 > s:
                          uint256(stor[t]) = mem[s]
                          t = t + 1
                          s = s + 32
                          continue 
                      s = sha3(sha3(mem[(32 * idx) + 128], 8)) + (Mask(251, 0, mem[(32 * _param2.length) + (32 * _param3.length) + 160] + 31) >> 5)
                      while sha3(sha3(mem[(32 * idx) + 128], 8)) + (uri[mem[(32 * idx) + 128]].length + 31 / 32) > s:
                          uint256(stor[s]) = 0
                          s = s + 1
                          continue 
                      _1400 = mem[64]
                      mem[mem[64]] = 32
                      mem[mem[64] + 32] = mem[(32 * _param2.length) + (32 * _param3.length) + 160]
                      _1402 = mem[(32 * _param2.length) + (32 * _param3.length) + 160]
                      s = 0
                      while s < _1402:
                          mem[_1400 + s + 64] = mem[(32 * _param2.length) + (32 * _param3.length) + s + 192]
                          s = s + 32
                          continue 
                      if not _1402 % 32:
                          log 0x6bb7ff70: mem[memem
                      else:
                          mem[floor32(_1402) + _1400 + 64] = mem[floor32(_1402) + _1400 + -(_1402 % 32) + 96 len _1402 % 32]
                          log 0x6bb7ff70: mem[memem
                      idx = idx + 1
                      continue 
  stor9 = 1

def unknown731133e9(addr _param1, uint256 _param2, uint256 _param3, array _param4) payable: 
  require calldata.size - 4 >= 128
  require _param4 <= 4294967296
  require _param4 + 36 <= calldata.size
  require _param4.length <= 4294967296 and _param4 + _param4.length + 36 <= calldata.size
  mem[128 len _param4.length] = _param4[all]
  mem[_param4.length + 128] = 0
  if not stor9:
      revert with 0, 'ReentrancyGuard: reentrant call'
  stor9 = 0
  if not creator[_param2]:
      if uint64(_param2) == caller:
          if totalSupply[_param2] > _param2 % 1099511627776:
              revert with 0, 'SafeMath#sub: UNDERFLOW'
          if (_param2 % 1099511627776) - totalSupply[_param2] < _param3:
              revert with 0, 
                          32,
                          53,
                          0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a20535550504c595f45584345454445,
                          mem[ceil32(_param4.length) + 249 len 11]
          if stor0[addr(_param1)][_param2] + _param3 < stor0[addr(_param1)][_param2]:
              revert with 0, 'SafeMath#add: OVERFLOW'
          stor0[addr(_param1)][_param2] += _param3
          if totalSupply[_param2] + _param3 < totalSupply[_param2]:
              revert with 0, 'SafeMath#add: OVERFLOW'
          totalSupply[_param2] += _param3
          mem[ceil32(_param4.length) + 128] = _param2
          mem[ceil32(_param4.length) + 160] = _param3
          log 0xc3d58168: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len -_param4.length + ceil32(_param4.length) + 32], caller, uint64(_param2), _param1
          if not ext_code.hash(_param1):
              if _param4.length > 1:
                  uri[_param2][] = Array(len=_param4.length, data=_param4[all])
                  mem[ceil32(_param4.length) + 128] = 32
                  mem[ceil32(_param4.length) + 160] = _param4.length
                  mem[ceil32(_param4.length) + 192 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                  if not _param4.length % 32:
                      log 0x6bb7ff70: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len ceil32(_param4.length) + -_param4.length + 32], Mask(8 * _param4.length, -(8 * _param4.length) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * _param4.length) - 256, _param2
                  else:
                      mem[floor32(_param4.length) + ceil32(_param4.length) + 192] = mem[floor32(_param4.length) + ceil32(_param4.length) + -(_param4.length % 32) + 224 len _param4.length % 32]
                      log 0x6bb7ff70: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len ceil32(_param4.length) + -_param4.length + 32], Mask(8 * ceil32(_param4.length), -(8 * ceil32(_param4.length)) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * ceil32(_param4.length)) - 256, mem[(2 * ceil32(_param4.length)) + 192 len floor32(_param4.length) + -ceil32(_param4.length) + 32], _param2
          else:
              if ext_code.hash(_param1) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                  if _param4.length > 1:
                      uri[_param2][] = Array(len=_param4.length, data=_param4[all])
                      mem[ceil32(_param4.length) + 128] = 32
                      mem[ceil32(_param4.length) + 160] = _param4.length
                      mem[ceil32(_param4.length) + 192 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                      if not _param4.length % 32:
                          log 0x6bb7ff70: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len ceil32(_param4.length) + -_param4.length + 32], Mask(8 * _param4.length, -(8 * _param4.length) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * _param4.length) - 256, _param2
                      else:
                          mem[floor32(_param4.length) + ceil32(_param4.length) + 192] = mem[floor32(_param4.length) + ceil32(_param4.length) + -(_param4.length % 32) + 224 len _param4.length % 32]
                          log 0x6bb7ff70: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len ceil32(_param4.length) + -_param4.length + 32], Mask(8 * ceil32(_param4.length), -(8 * ceil32(_param4.length)) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * ceil32(_param4.length)) - 256, mem[(2 * ceil32(_param4.length)) + 192 len floor32(_param4.length) + -ceil32(_param4.length) + 32], _param2
              else:
                  mem[ceil32(_param4.length) + 128] = 0xf23a6e6100000000000000000000000000000000000000000000000000000000
                  mem[ceil32(_param4.length) + 196] = _param2
                  mem[ceil32(_param4.length) + 228] = _param3
                  mem[ceil32(_param4.length) + 260] = 160
                  mem[ceil32(_param4.length) + 292] = _param4.length
                  mem[ceil32(_param4.length) + 324 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                  require ext_code.size(_param1)
                  call _param1 with:
                       gas gas_remaining wei
                      args caller, _param2 << 192, _param2, _param3, Array(len=_param4.length, data=_param4[all])
                  if not ext_call.success:
                      revert with ext_call.return_data[0 len return_data.size]
                  require return_data.size >= 32
                  if Mask(32, 224, ext_call.return_data[0]) != 0xf23a6e6100000000000000000000000000000000000000000000000000000000:
                      revert with 0, 
                                  32,
                                  58,
                                  0x4545524331313535235f63616c6c6f6e4552433131353552656365697665643a20494e56414c49445f4f4e5f524543454956455f4d4553534147,
                                  _param3 % 281474976710656
                  if _param4.length > 1:
                      uri[_param2][] = Array(len=_param4.length, data=_param4[all])
                      mem[ceil32(_param4.length) + 128] = 32
                      mem[ceil32(_param4.length) + 192 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                      if not _param4.length % 32:
                          log 0x6bb7ff70: 0, 32, _param4.length, Mask(8 * _param4.length, -(8 * _param4.length) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * _param4.length) - 256, _param2
                      else:
                          mem[floor32(_param4.length) + ceil32(_param4.length) + 192] = mem[floor32(_param4.length) + ceil32(_param4.length) + -(_param4.length % 32) + 224 len _param4.length % 32]
                          log 0x6bb7ff70: 0, 32, _param4.length, Mask(8 * ceil32(_param4.length), -(8 * ceil32(_param4.length)) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * ceil32(_param4.length)) - 256, mem[(2 * ceil32(_param4.length)) + 192 len floor32(_param4.length) + -ceil32(_param4.length) + 32], _param2
      else:
          if stor10[caller]:
              if totalSupply[_param2] > _param2 % 1099511627776:
                  revert with 0, 'SafeMath#sub: UNDERFLOW'
              if (_param2 % 1099511627776) - totalSupply[_param2] < _param3:
                  revert with 0, 
                              32,
                              53,
                              0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a20535550504c595f45584345454445,
                              mem[ceil32(_param4.length) + 249 len 11]
              if stor0[addr(_param1)][_param2] + _param3 < stor0[addr(_param1)][_param2]:
                  revert with 0, 'SafeMath#add: OVERFLOW'
              stor0[addr(_param1)][_param2] += _param3
              if totalSupply[_param2] + _param3 < totalSupply[_param2]:
                  revert with 0, 'SafeMath#add: OVERFLOW'
              totalSupply[_param2] += _param3
              mem[ceil32(_param4.length) + 128] = _param2
              mem[ceil32(_param4.length) + 160] = _param3
              log 0xc3d58168: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len -_param4.length + ceil32(_param4.length) + 32], caller, uint64(_param2), _param1
              if not ext_code.hash(_param1):
                  if _param4.length > 1:
                      uri[_param2][] = Array(len=_param4.length, data=_param4[all])
                      mem[ceil32(_param4.length) + 128] = 32
                      mem[ceil32(_param4.length) + 160] = _param4.length
                      mem[ceil32(_param4.length) + 192 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                      if not _param4.length % 32:
                          log 0x6bb7ff70: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len ceil32(_param4.length) + -_param4.length + 32], Mask(8 * _param4.length, -(8 * _param4.length) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * _param4.length) - 256, _param2
                      else:
                          mem[floor32(_param4.length) + ceil32(_param4.length) + 192] = mem[floor32(_param4.length) + ceil32(_param4.length) + -(_param4.length % 32) + 224 len _param4.length % 32]
                          log 0x6bb7ff70: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len ceil32(_param4.length) + -_param4.length + 32], Mask(8 * ceil32(_param4.length), -(8 * ceil32(_param4.length)) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * ceil32(_param4.length)) - 256, mem[(2 * ceil32(_param4.length)) + 192 len floor32(_param4.length) + -ceil32(_param4.length) + 32], _param2
              else:
                  if ext_code.hash(_param1) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                      if _param4.length > 1:
                          uri[_param2][] = Array(len=_param4.length, data=_param4[all])
                          mem[ceil32(_param4.length) + 128] = 32
                          mem[ceil32(_param4.length) + 160] = _param4.length
                          mem[ceil32(_param4.length) + 192 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                          if not _param4.length % 32:
                              log 0x6bb7ff70: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len ceil32(_param4.length) + -_param4.length + 32], Mask(8 * _param4.length, -(8 * _param4.length) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * _param4.length) - 256, _param2
                          else:
                              mem[floor32(_param4.length) + ceil32(_param4.length) + 192] = mem[floor32(_param4.length) + ceil32(_param4.length) + -(_param4.length % 32) + 224 len _param4.length % 32]
                              log 0x6bb7ff70: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len ceil32(_param4.length) + -_param4.length + 32], Mask(8 * ceil32(_param4.length), -(8 * ceil32(_param4.length)) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * ceil32(_param4.length)) - 256, mem[(2 * ceil32(_param4.length)) + 192 len floor32(_param4.length) + -ceil32(_param4.length) + 32], _param2
                  else:
                      mem[ceil32(_param4.length) + 128] = 0xf23a6e6100000000000000000000000000000000000000000000000000000000
                      mem[ceil32(_param4.length) + 196] = _param2
                      mem[ceil32(_param4.length) + 228] = _param3
                      mem[ceil32(_param4.length) + 260] = 160
                      mem[ceil32(_param4.length) + 292] = _param4.length
                      mem[ceil32(_param4.length) + 324 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                      require ext_code.size(_param1)
                      call _param1 with:
                           gas gas_remaining wei
                          args caller, _param2 << 192, _param2, _param3, Array(len=_param4.length, data=_param4[all])
                      if not ext_call.success:
                          revert with ext_call.return_data[0 len return_data.size]
                      require return_data.size >= 32
                      if Mask(32, 224, ext_call.return_data[0]) != 0xf23a6e6100000000000000000000000000000000000000000000000000000000:
                          revert with 0, 
                                      32,
                                      58,
                                      0x4545524331313535235f63616c6c6f6e4552433131353552656365697665643a20494e56414c49445f4f4e5f524543454956455f4d4553534147,
                                      _param3 % 281474976710656
                      if _param4.length > 1:
                          uri[_param2][] = Array(len=_param4.length, data=_param4[all])
                          mem[ceil32(_param4.length) + 128] = 32
                          mem[ceil32(_param4.length) + 192 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                          if not _param4.length % 32:
                              log 0x6bb7ff70: 0, 32, _param4.length, Mask(8 * _param4.length, -(8 * _param4.length) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * _param4.length) - 256, _param2
                          else:
                              mem[floor32(_param4.length) + ceil32(_param4.length) + 192] = mem[floor32(_param4.length) + ceil32(_param4.length) + -(_param4.length % 32) + 224 len _param4.length % 32]
                              log 0x6bb7ff70: 0, 32, _param4.length, Mask(8 * ceil32(_param4.length), -(8 * ceil32(_param4.length)) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * ceil32(_param4.length)) - 256, mem[(2 * ceil32(_param4.length)) + 192 len floor32(_param4.length) + -ceil32(_param4.length) + 32], _param2
          else:
              require ext_code.size(unknowncd7c0326Address)
              static call unknowncd7c0326Address.proxies(address param1) with:
                      gas gas_remaining wei
                     args uint64(_param2)
              if not ext_call.success:
                  revert with ext_call.return_data[0 len return_data.size]
              require return_data.size >= 32
              if ext_call.return_data[12 len 20] != caller:
                  revert with 0, 
                              32,
                              58,
                              0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a204f4e4c595f43524541544f525f414c4c4f5745,
                              mem[ceil32(_param4.length) + 254 len 6]
              if totalSupply[_param2] > _param2 % 1099511627776:
                  revert with 0, 'SafeMath#sub: UNDERFLOW'
              if (_param2 % 1099511627776) - totalSupply[_param2] < _param3:
                  revert with 0, 
                              32,
                              53,
                              0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a20535550504c595f45584345454445,
                              mem[ceil32(_param4.length) + 249 len 11]
              if stor0[addr(_param1)][_param2] + _param3 < stor0[addr(_param1)][_param2]:
                  revert with 0, 'SafeMath#add: OVERFLOW'
              stor0[addr(_param1)][_param2] += _param3
              if totalSupply[_param2] + _param3 < totalSupply[_param2]:
                  revert with 0, 'SafeMath#add: OVERFLOW'
              totalSupply[_param2] += _param3
              log 0xc3d58168: 0, Mask(224, 0, _param2), _param3, caller, uint64(_param2), _param1
              if ext_code.hash(_param1):
                  if ext_code.hash(_param1) != 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                      mem[ceil32(_param4.length) + 128] = 0xf23a6e6100000000000000000000000000000000000000000000000000000000
                      mem[ceil32(_param4.length) + 196] = _param2
                      mem[ceil32(_param4.length) + 228] = _param3
                      mem[ceil32(_param4.length) + 260] = 160
                      mem[ceil32(_param4.length) + 292] = _param4.length
                      mem[ceil32(_param4.length) + 324 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                      require ext_code.size(_param1)
                      call _param1 with:
                           gas gas_remaining wei
                          args caller, _param2 << 192, _param2, _param3, Array(len=_param4.length, data=_param4[all])
                      if not ext_call.success:
                          revert with ext_call.return_data[0 len return_data.size]
                      require return_data.size >= 32
                      if Mask(32, 224, ext_call.return_data[0]) != 0xf23a6e6100000000000000000000000000000000000000000000000000000000:
                          revert with 0, 
                                      32,
                                      58,
                                      0x4545524331313535235f63616c6c6f6e4552433131353552656365697665643a20494e56414c49445f4f4e5f524543454956455f4d4553534147,
                                      _param3 % 281474976710656
              if _param4.length > 1:
                  uri[_param2][] = Array(len=_param4.length, data=_param4[all])
                  mem[ceil32(_param4.length) + 128] = 32
                  mem[ceil32(_param4.length) + 192 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                  if not _param4.length % 32:
                      log 0x6bb7ff70: 0, 32, _param4.length, Mask(8 * _param4.length, -(8 * _param4.length) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * _param4.length) - 256, _param2
                  else:
                      mem[floor32(_param4.length) + ceil32(_param4.length) + 192] = mem[floor32(_param4.length) + ceil32(_param4.length) + -(_param4.length % 32) + 224 len _param4.length % 32]
                      log 0x6bb7ff70: 0, 32, _param4.length, Mask(8 * ceil32(_param4.length), -(8 * ceil32(_param4.length)) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * ceil32(_param4.length)) - 256, mem[(2 * ceil32(_param4.length)) + 192 len floor32(_param4.length) + -ceil32(_param4.length) + 32], _param2
  else:
      if creator[_param2] == caller:
          if totalSupply[_param2] > _param2 % 1099511627776:
              revert with 0, 'SafeMath#sub: UNDERFLOW'
          if (_param2 % 1099511627776) - totalSupply[_param2] < _param3:
              revert with 0, 
                          32,
                          53,
                          0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a20535550504c595f45584345454445,
                          mem[ceil32(_param4.length) + 249 len 11]
          if stor0[addr(_param1)][_param2] + _param3 < stor0[addr(_param1)][_param2]:
              revert with 0, 'SafeMath#add: OVERFLOW'
          stor0[addr(_param1)][_param2] += _param3
          if totalSupply[_param2] + _param3 < totalSupply[_param2]:
              revert with 0, 'SafeMath#add: OVERFLOW'
          totalSupply[_param2] += _param3
          mem[ceil32(_param4.length) + 128] = _param2
          mem[ceil32(_param4.length) + 160] = _param3
          log 0xc3d58168: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len -_param4.length + ceil32(_param4.length) + 32], caller, uint64(_param2), _param1
          if not ext_code.hash(_param1):
              if _param4.length > 1:
                  uri[_param2][] = Array(len=_param4.length, data=_param4[all])
                  mem[ceil32(_param4.length) + 128] = 32
                  mem[ceil32(_param4.length) + 160] = _param4.length
                  mem[ceil32(_param4.length) + 192 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                  if not _param4.length % 32:
                      log 0x6bb7ff70: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len ceil32(_param4.length) + -_param4.length + 32], Mask(8 * _param4.length, -(8 * _param4.length) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * _param4.length) - 256, _param2
                  else:
                      mem[floor32(_param4.length) + ceil32(_param4.length) + 192] = mem[floor32(_param4.length) + ceil32(_param4.length) + -(_param4.length % 32) + 224 len _param4.length % 32]
                      log 0x6bb7ff70: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len ceil32(_param4.length) + -_param4.length + 32], Mask(8 * ceil32(_param4.length), -(8 * ceil32(_param4.length)) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * ceil32(_param4.length)) - 256, mem[(2 * ceil32(_param4.length)) + 192 len floor32(_param4.length) + -ceil32(_param4.length) + 32], _param2
          else:
              if ext_code.hash(_param1) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                  if _param4.length > 1:
                      uri[_param2][] = Array(len=_param4.length, data=_param4[all])
                      mem[ceil32(_param4.length) + 128] = 32
                      mem[ceil32(_param4.length) + 160] = _param4.length
                      mem[ceil32(_param4.length) + 192 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                      if not _param4.length % 32:
                          log 0x6bb7ff70: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len ceil32(_param4.length) + -_param4.length + 32], Mask(8 * _param4.length, -(8 * _param4.length) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * _param4.length) - 256, _param2
                      else:
                          mem[floor32(_param4.length) + ceil32(_param4.length) + 192] = mem[floor32(_param4.length) + ceil32(_param4.length) + -(_param4.length % 32) + 224 len _param4.length % 32]
                          log 0x6bb7ff70: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len ceil32(_param4.length) + -_param4.length + 32], Mask(8 * ceil32(_param4.length), -(8 * ceil32(_param4.length)) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * ceil32(_param4.length)) - 256, mem[(2 * ceil32(_param4.length)) + 192 len floor32(_param4.length) + -ceil32(_param4.length) + 32], _param2
              else:
                  mem[ceil32(_param4.length) + 128] = 0xf23a6e6100000000000000000000000000000000000000000000000000000000
                  mem[ceil32(_param4.length) + 196] = _param2
                  mem[ceil32(_param4.length) + 228] = _param3
                  mem[ceil32(_param4.length) + 260] = 160
                  mem[ceil32(_param4.length) + 292] = _param4.length
                  mem[ceil32(_param4.length) + 324 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                  require ext_code.size(_param1)
                  call _param1 with:
                       gas gas_remaining wei
                      args caller, _param2 << 192, _param2, _param3, Array(len=_param4.length, data=_param4[all])
                  if not ext_call.success:
                      revert with ext_call.return_data[0 len return_data.size]
                  require return_data.size >= 32
                  if Mask(32, 224, ext_call.return_data[0]) != 0xf23a6e6100000000000000000000000000000000000000000000000000000000:
                      revert with 0, 
                                  32,
                                  58,
                                  0x4545524331313535235f63616c6c6f6e4552433131353552656365697665643a20494e56414c49445f4f4e5f524543454956455f4d4553534147,
                                  _param3 % 281474976710656
                  if _param4.length > 1:
                      uri[_param2][] = Array(len=_param4.length, data=_param4[all])
                      mem[ceil32(_param4.length) + 128] = 32
                      mem[ceil32(_param4.length) + 192 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                      if not _param4.length % 32:
                          log 0x6bb7ff70: 0, 32, _param4.length, Mask(8 * _param4.length, -(8 * _param4.length) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * _param4.length) - 256, _param2
                      else:
                          mem[floor32(_param4.length) + ceil32(_param4.length) + 192] = mem[floor32(_param4.length) + ceil32(_param4.length) + -(_param4.length % 32) + 224 len _param4.length % 32]
                          log 0x6bb7ff70: 0, 32, _param4.length, Mask(8 * ceil32(_param4.length), -(8 * ceil32(_param4.length)) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * ceil32(_param4.length)) - 256, mem[(2 * ceil32(_param4.length)) + 192 len floor32(_param4.length) + -ceil32(_param4.length) + 32], _param2
      else:
          if stor10[caller]:
              if totalSupply[_param2] > _param2 % 1099511627776:
                  revert with 0, 'SafeMath#sub: UNDERFLOW'
              if (_param2 % 1099511627776) - totalSupply[_param2] < _param3:
                  revert with 0, 
                              32,
                              53,
                              0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a20535550504c595f45584345454445,
                              mem[ceil32(_param4.length) + 249 len 11]
              if stor0[addr(_param1)][_param2] + _param3 < stor0[addr(_param1)][_param2]:
                  revert with 0, 'SafeMath#add: OVERFLOW'
              stor0[addr(_param1)][_param2] += _param3
              if totalSupply[_param2] + _param3 < totalSupply[_param2]:
                  revert with 0, 'SafeMath#add: OVERFLOW'
              totalSupply[_param2] += _param3
              mem[ceil32(_param4.length) + 128] = _param2
              mem[ceil32(_param4.length) + 160] = _param3
              log 0xc3d58168: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len -_param4.length + ceil32(_param4.length) + 32], caller, uint64(_param2), _param1
              if not ext_code.hash(_param1):
                  if _param4.length > 1:
                      uri[_param2][] = Array(len=_param4.length, data=_param4[all])
                      mem[ceil32(_param4.length) + 128] = 32
                      mem[ceil32(_param4.length) + 160] = _param4.length
                      mem[ceil32(_param4.length) + 192 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                      if not _param4.length % 32:
                          log 0x6bb7ff70: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len ceil32(_param4.length) + -_param4.length + 32], Mask(8 * _param4.length, -(8 * _param4.length) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * _param4.length) - 256, _param2
                      else:
                          mem[floor32(_param4.length) + ceil32(_param4.length) + 192] = mem[floor32(_param4.length) + ceil32(_param4.length) + -(_param4.length % 32) + 224 len _param4.length % 32]
                          log 0x6bb7ff70: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len ceil32(_param4.length) + -_param4.length + 32], Mask(8 * ceil32(_param4.length), -(8 * ceil32(_param4.length)) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * ceil32(_param4.length)) - 256, mem[(2 * ceil32(_param4.length)) + 192 len floor32(_param4.length) + -ceil32(_param4.length) + 32], _param2
              else:
                  if ext_code.hash(_param1) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                      if _param4.length > 1:
                          uri[_param2][] = Array(len=_param4.length, data=_param4[all])
                          mem[ceil32(_param4.length) + 128] = 32
                          mem[ceil32(_param4.length) + 160] = _param4.length
                          mem[ceil32(_param4.length) + 192 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                          if not _param4.length % 32:
                              log 0x6bb7ff70: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len ceil32(_param4.length) + -_param4.length + 32], Mask(8 * _param4.length, -(8 * _param4.length) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * _param4.length) - 256, _param2
                          else:
                              mem[floor32(_param4.length) + ceil32(_param4.length) + 192] = mem[floor32(_param4.length) + ceil32(_param4.length) + -(_param4.length % 32) + 224 len _param4.length % 32]
                              log 0x6bb7ff70: Mask(8 * -ceil32(_param4.length) + _param4.length + 32, 0, 0), mem[_param4.length + 160 len ceil32(_param4.length) + -_param4.length + 32], Mask(8 * ceil32(_param4.length), -(8 * ceil32(_param4.length)) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * ceil32(_param4.length)) - 256, mem[(2 * ceil32(_param4.length)) + 192 len floor32(_param4.length) + -ceil32(_param4.length) + 32], _param2
                  else:
                      mem[ceil32(_param4.length) + 128] = 0xf23a6e6100000000000000000000000000000000000000000000000000000000
                      mem[ceil32(_param4.length) + 196] = _param2
                      mem[ceil32(_param4.length) + 228] = _param3
                      mem[ceil32(_param4.length) + 260] = 160
                      mem[ceil32(_param4.length) + 292] = _param4.length
                      mem[ceil32(_param4.length) + 324 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                      require ext_code.size(_param1)
                      call _param1 with:
                           gas gas_remaining wei
                          args caller, _param2 << 192, _param2, _param3, Array(len=_param4.length, data=_param4[all])
                      if not ext_call.success:
                          revert with ext_call.return_data[0 len return_data.size]
                      require return_data.size >= 32
                      if Mask(32, 224, ext_call.return_data[0]) != 0xf23a6e6100000000000000000000000000000000000000000000000000000000:
                          revert with 0, 
                                      32,
                                      58,
                                      0x4545524331313535235f63616c6c6f6e4552433131353552656365697665643a20494e56414c49445f4f4e5f524543454956455f4d4553534147,
                                      _param3 % 281474976710656
                      if _param4.length > 1:
                          uri[_param2][] = Array(len=_param4.length, data=_param4[all])
                          mem[ceil32(_param4.length) + 128] = 32
                          mem[ceil32(_param4.length) + 192 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                          if not _param4.length % 32:
                              log 0x6bb7ff70: 0, 32, _param4.length, Mask(8 * _param4.length, -(8 * _param4.length) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * _param4.length) - 256, _param2
                          else:
                              mem[floor32(_param4.length) + ceil32(_param4.length) + 192] = mem[floor32(_param4.length) + ceil32(_param4.length) + -(_param4.length % 32) + 224 len _param4.length % 32]
                              log 0x6bb7ff70: 0, 32, _param4.length, Mask(8 * ceil32(_param4.length), -(8 * ceil32(_param4.length)) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * ceil32(_param4.length)) - 256, mem[(2 * ceil32(_param4.length)) + 192 len floor32(_param4.length) + -ceil32(_param4.length) + 32], _param2
          else:
              require ext_code.size(unknowncd7c0326Address)
              static call unknowncd7c0326Address.proxies(address param1) with:
                      gas gas_remaining wei
                     args creator[_param2]
              if not ext_call.success:
                  revert with ext_call.return_data[0 len return_data.size]
              require return_data.size >= 32
              if ext_call.return_data[12 len 20] != caller:
                  revert with 0, 
                              32,
                              58,
                              0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a204f4e4c595f43524541544f525f414c4c4f5745,
                              mem[ceil32(_param4.length) + 254 len 6]
              if totalSupply[_param2] > _param2 % 1099511627776:
                  revert with 0, 'SafeMath#sub: UNDERFLOW'
              if (_param2 % 1099511627776) - totalSupply[_param2] < _param3:
                  revert with 0, 
                              32,
                              53,
                              0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a20535550504c595f45584345454445,
                              mem[ceil32(_param4.length) + 249 len 11]
              if stor0[addr(_param1)][_param2] + _param3 < stor0[addr(_param1)][_param2]:
                  revert with 0, 'SafeMath#add: OVERFLOW'
              stor0[addr(_param1)][_param2] += _param3
              if totalSupply[_param2] + _param3 < totalSupply[_param2]:
                  revert with 0, 'SafeMath#add: OVERFLOW'
              totalSupply[_param2] += _param3
              log 0xc3d58168: 0, Mask(224, 0, _param2), _param3, caller, uint64(_param2), _param1
              if ext_code.hash(_param1):
                  if ext_code.hash(_param1) != 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                      mem[ceil32(_param4.length) + 128] = 0xf23a6e6100000000000000000000000000000000000000000000000000000000
                      mem[ceil32(_param4.length) + 196] = _param2
                      mem[ceil32(_param4.length) + 228] = _param3
                      mem[ceil32(_param4.length) + 260] = 160
                      mem[ceil32(_param4.length) + 292] = _param4.length
                      mem[ceil32(_param4.length) + 324 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                      require ext_code.size(_param1)
                      call _param1 with:
                           gas gas_remaining wei
                          args caller, _param2 << 192, _param2, _param3, Array(len=_param4.length, data=_param4[all])
                      if not ext_call.success:
                          revert with ext_call.return_data[0 len return_data.size]
                      require return_data.size >= 32
                      if Mask(32, 224, ext_call.return_data[0]) != 0xf23a6e6100000000000000000000000000000000000000000000000000000000:
                          revert with 0, 
                                      32,
                                      58,
                                      0x4545524331313535235f63616c6c6f6e4552433131353552656365697665643a20494e56414c49445f4f4e5f524543454956455f4d4553534147,
                                      _param3 % 281474976710656
              if _param4.length > 1:
                  uri[_param2][] = Array(len=_param4.length, data=_param4[all])
                  mem[ceil32(_param4.length) + 128] = 32
                  mem[ceil32(_param4.length) + 192 len ceil32(_param4.length)] = _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]
                  if not _param4.length % 32:
                      log 0x6bb7ff70: 0, 32, _param4.length, Mask(8 * _param4.length, -(8 * _param4.length) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * _param4.length) - 256, _param2
                  else:
                      mem[floor32(_param4.length) + ceil32(_param4.length) + 192] = mem[floor32(_param4.length) + ceil32(_param4.length) + -(_param4.length % 32) + 224 len _param4.length % 32]
                      log 0x6bb7ff70: 0, 32, _param4.length, Mask(8 * ceil32(_param4.length), -(8 * ceil32(_param4.length)) + 256, _param4[all], mem[_param4.length + 128 len ceil32(_param4.length) - _param4.length]) << (8 * ceil32(_param4.length)) - 256, mem[(2 * ceil32(_param4.length)) + 192 len floor32(_param4.length) + -ceil32(_param4.length) + 32], _param2
  stor9 = 1

def safeTransferFrom(address _from, address _to, uint256 _id, uint256 _value, bytes _data) payable: 
  require calldata.size - 4 >= 160
  require _data <= 4294967296
  require _data + 36 <= calldata.size
  require _data.length <= 4294967296 and _data + _data.length + 36 <= calldata.size
  if stor0[addr(_from)][_id] >= _value:
      if caller == _from:
          if not _to:
              revert with 0, 
                          32,
                          43,
                          0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                          mem[ceil32(_data.length) + 239 len 21]
          if _value > stor0[addr(_from)][_id]:
              revert with 0, 'SafeMath#sub: UNDERFLOW'
          stor0[addr(_from)][_id] -= _value
          if stor0[addr(_to)][_id] + _value < stor0[addr(_to)][_id]:
              revert with 0, 'SafeMath#add: OVERFLOW'
          stor0[addr(_to)][_id] += _value
          mem[ceil32(_data.length) + 128] = _id
          mem[ceil32(_data.length) + 160] = _value
          log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, _from, _to
      else:
          if stor10[caller]:
              if not _to:
                  revert with 0, 
                              32,
                              43,
                              0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                              mem[ceil32(_data.length) + 239 len 21]
              if _value > stor0[addr(_from)][_id]:
                  revert with 0, 'SafeMath#sub: UNDERFLOW'
              stor0[addr(_from)][_id] -= _value
              if stor0[addr(_to)][_id] + _value < stor0[addr(_to)][_id]:
                  revert with 0, 'SafeMath#add: OVERFLOW'
              stor0[addr(_to)][_id] += _value
              mem[ceil32(_data.length) + 128] = _id
              mem[ceil32(_data.length) + 160] = _value
              log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, _from, _to
          else:
              require ext_code.size(unknowncd7c0326Address)
              static call unknowncd7c0326Address.proxies(address param1) with:
                      gas gas_remaining wei
                     args _from
              if not ext_call.success:
                  revert with ext_call.return_data[0 len return_data.size]
              require return_data.size >= 32
              if ext_call.return_data[12 len 20] != caller:
                  if not stor1[addr(_from)][caller]:
                      revert with 0, 
                                  32,
                                  42,
                                  0x2e4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f4f50455241544f,
                                  mem[ceil32(_data.length) + 238 len 22]
              if not _to:
                  revert with 0, 
                              32,
                              43,
                              0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                              mem[ceil32(_data.length) + 239 len 21]
              if _value > stor0[addr(_from)][_id]:
                  revert with 0, 'SafeMath#sub: UNDERFLOW'
              stor0[addr(_from)][_id] -= _value
              if stor0[addr(_to)][_id] + _value < stor0[addr(_to)][_id]:
                  revert with 0, 'SafeMath#add: OVERFLOW'
              stor0[addr(_to)][_id] += _value
              log 0xc3d58168: 0, Mask(224, 0, _id), _value, caller, _from, _to
      if not ext_code.hash(_to):
          stop
      if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
          stop
  else:
      if stor0[addr(_from)][_id] > _value:
          revert with 0, 'SafeMath#sub: UNDERFLOW'
      if not stor9:
          revert with 0, 'ReentrancyGuard: reentrant call'
      stor9 = 0
      if not creator[_id]:
          if uint64(_id) != caller:
              if not stor10[caller]:
                  require ext_code.size(unknowncd7c0326Address)
                  static call unknowncd7c0326Address.proxies(address param1) with:
                          gas gas_remaining wei
                         args uint64(_id)
                  if not ext_call.success:
                      revert with ext_call.return_data[0 len return_data.size]
                  require return_data.size >= 32
                  if ext_call.return_data[12 len 20] != caller:
                      revert with 0, 
                                  32,
                                  58,
                                  0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a204f4e4c595f43524541544f525f414c4c4f5745,
                                  mem[ceil32(_data.length) + 254 len 6]
                  if totalSupply[_id] > _id % 1099511627776:
                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                  if (_id % 1099511627776) - totalSupply[_id] < _value - stor0[addr(_from)][_id]:
                      revert with 0, 
                                  32,
                                  53,
                                  0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a20535550504c595f45584345454445,
                                  mem[ceil32(_data.length) + 249 len 11]
                  if stor0[addr(_to)][_id] + _value - stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                      revert with 0, 'SafeMath#add: OVERFLOW'
                  stor0[addr(_to)][_id] = stor0[addr(_to)][_id] + _value - stor0[addr(_from)][_id]
                  if totalSupply[_id] + _value - stor0[addr(_from)][_id] < totalSupply[_id]:
                      revert with 0, 'SafeMath#add: OVERFLOW'
                  totalSupply[_id] = totalSupply[_id] + _value - stor0[addr(_from)][_id]
                  log 0xc3d58168: 0, Mask(224, 0, _id), _value - stor0[addr(_from)][_id], caller, uint64(_id), _to
                  if not ext_code.hash(_to):
                      if _data.length > 1:
                          uri[_id] = (2 * _data.length) + 1
                      else:
                          stor9 = 1
                          if stor0[addr(_from)][_id] <= 0:
                              stop
                          if caller == _from:
                              if not _to:
                                  revert with 0, 
                                              32,
                                              43,
                                              0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                              mem[ceil32(_data.length) + 239 len 21]
                              if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                  revert with 0, 'SafeMath#sub: UNDERFLOW'
                              stor0[addr(_from)][_id] = 0
                              if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                  revert with 0, 'SafeMath#add: OVERFLOW'
                              stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                              log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
                              if ext_code.hash(_to):
                          else:
                              if stor10[caller]:
                                  if not _to:
                                      revert with 0, 
                                                  32,
                                                  43,
                                                  0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                  mem[ceil32(_data.length) + 239 len 21]
                                  if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                                  stor0[addr(_from)][_id] = 0
                                  if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                      revert with 0, 'SafeMath#add: OVERFLOW'
                                  stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                  log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
                              else:
                                  require ext_code.size(unknowncd7c0326Address)
                                  static call unknowncd7c0326Address.proxies(address param1) with:
                                          gas gas_remaining wei
                                         args _from
                                  if not ext_call.success:
                                      revert with ext_call.return_data[0 len return_data.size]
                                  require return_data.size >= 32
                                  if ext_call.return_data == caller:
                                      if not _to:
                                          revert with 0, 
                                                      32,
                                                      43,
                                                      0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                      mem[ceil32(_data.length) + 239 len 21]
                                  else:
                                      if not stor1[addr(_from)][caller]:
                                          revert with 0, 
                                                      32,
                                                      42,
                                                      0x2e4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f4f50455241544f,
                                                      mem[ceil32(_data.length) + 238 len 22]
                  else:
                      if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                          if _data.length > 1:
                              uri[_id] = (2 * _data.length) + 1
                          else:
                              stor9 = 1
                              if stor0[addr(_from)][_id] <= 0:
                                  stop
                              if _from != caller:
                                  if not stor10[caller]:
                                      require ext_code.size(unknowncd7c0326Address)
                                      static call unknowncd7c0326Address.proxies(address param1) with:
                                              gas gas_remaining wei
                                             args _from
                                      if not ext_call.success:
                                          revert with ext_call.return_data[0 len return_data.size]
                                      require return_data.size >= 32
                                      if ext_call.return_data == caller:
                                          if not _to:
                                              revert with 0, 
                                                          32,
                                                          43,
                                                          0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                          mem[ceil32(_data.length) + 239 len 21]
                                  else:
                                      if not _to:
                                          revert with 0, 
                                                      32,
                                                      43,
                                                      0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                      mem[ceil32(_data.length) + 239 len 21]
                                      if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                          revert with 0, 'SafeMath#sub: UNDERFLOW'
                                      stor0[addr(_from)][_id] = 0
                                      if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                          revert with 0, 'SafeMath#add: OVERFLOW'
                                      stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                      log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
                              else:
                                  if not _to:
                                      revert with 0, 
                                                  32,
                                                  43,
                                                  0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                  mem[ceil32(_data.length) + 239 len 21]
                                  if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                                  stor0[addr(_from)][_id] = 0
                                  if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                      revert with 0, 'SafeMath#add: OVERFLOW'
                                  stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                  log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
                                  if ext_code.hash(_to):
              else:
                  if totalSupply[_id] > _id % 1099511627776:
                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                  if (_id % 1099511627776) - totalSupply[_id] < _value - stor0[addr(_from)][_id]:
                      revert with 0, 
                                  32,
                                  53,
                                  0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a20535550504c595f45584345454445,
                                  mem[ceil32(_data.length) + 249 len 11]
                  if stor0[addr(_to)][_id] + _value - stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                      revert with 0, 'SafeMath#add: OVERFLOW'
                  stor0[addr(_to)][_id] = stor0[addr(_to)][_id] + _value - stor0[addr(_from)][_id]
                  if totalSupply[_id] + _value - stor0[addr(_from)][_id] < totalSupply[_id]:
                      revert with 0, 'SafeMath#add: OVERFLOW'
                  totalSupply[_id] = totalSupply[_id] + _value - stor0[addr(_from)][_id]
                  mem[ceil32(_data.length) + 128] = _id
                  mem[ceil32(_data.length) + 160] = _value - stor0[addr(_from)][_id]
                  log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, uint64(_id), _to
                  if not ext_code.hash(_to):
                      if _data.length > 1:
                          uri[_id] = (2 * _data.length) + 1
                      else:
                          stor9 = 1
                          if stor0[addr(_from)][_id] <= 0:
                              stop
                          if caller == _from:
                              if not _to:
                                  revert with 0, 
                                              32,
                                              43,
                                              0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                              mem[ceil32(_data.length) + 239 len 21]
                              if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                  revert with 0, 'SafeMath#sub: UNDERFLOW'
                              stor0[addr(_from)][_id] = 0
                              if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                  revert with 0, 'SafeMath#add: OVERFLOW'
                              stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                              mem[ceil32(_data.length) + 128] = _id
                              mem[ceil32(_data.length) + 160] = stor0[addr(_from)][_id]
                              log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, _from, _to
                              if not ext_code.hash(_to):
                                  stop
                              if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                                  stop
                          else:
                              if not stor10[caller]:
                                  require ext_code.size(unknowncd7c0326Address)
                                  static call unknowncd7c0326Address.proxies(address param1) with:
                                          gas gas_remaining wei
                                         args _from
                                  if not ext_call.success:
                                      revert with ext_call.return_data[0 len return_data.size]
                                  require return_data.size >= 32
                                  if ext_call.return_data[12 len 20] != caller:
                                      if not stor1[addr(_from)][caller]:
                                          revert with 0, 
                                                      32,
                                                      42,
                                                      0x2e4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f4f50455241544f,
                                                      mem[ceil32(_data.length) + 238 len 22]
                                      if not _to:
                                          revert with 0, 
                                                      32,
                                                      43,
                                                      0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                      mem[ceil32(_data.length) + 239 len 21]
                                      if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                          revert with 0, 'SafeMath#sub: UNDERFLOW'
                                      stor0[addr(_from)][_id] = 0
                                      if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                          revert with 0, 'SafeMath#add: OVERFLOW'
                                  else:
                                      if not _to:
                                          revert with 0, 
                                                      32,
                                                      43,
                                                      0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                      mem[ceil32(_data.length) + 239 len 21]
                                      if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                          revert with 0, 'SafeMath#sub: UNDERFLOW'
                                      stor0[addr(_from)][_id] = 0
                                      if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                          revert with 0, 'SafeMath#add: OVERFLOW'
                                      stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                      log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
                              else:
                                  if not _to:
                                      revert with 0, 
                                                  32,
                                                  43,
                                                  0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                  mem[ceil32(_data.length) + 239 len 21]
                                  if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                                  stor0[addr(_from)][_id] = 0
                                  if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                      revert with 0, 'SafeMath#add: OVERFLOW'
                                  stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                  mem[ceil32(_data.length) + 128] = _id
                                  mem[ceil32(_data.length) + 160] = stor0[addr(_from)][_id]
                                  log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, _from, _to
                                  if ext_code.hash(_to):
                                      if ext_code.hash(_to) != 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                  else:
                      if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                          if _data.length > 1:
                              uri[_id] = (2 * _data.length) + 1
                          else:
                              stor9 = 1
                              if stor0[addr(_from)][_id] <= 0:
                                  stop
                              if caller == _from:
                                  if not _to:
                                      revert with 0, 
                                                  32,
                                                  43,
                                                  0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                  mem[ceil32(_data.length) + 239 len 21]
                                  if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                                  stor0[addr(_from)][_id] = 0
                                  if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                      revert with 0, 'SafeMath#add: OVERFLOW'
                                  stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                  mem[ceil32(_data.length) + 128] = _id
                                  mem[ceil32(_data.length) + 160] = stor0[addr(_from)][_id]
                                  log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, _from, _to
                                  if not ext_code.hash(_to):
                                      stop
                                  if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                                      stop
                              else:
                                  if stor10[caller]:
                                      if not _to:
                                          revert with 0, 
                                                      32,
                                                      43,
                                                      0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                      mem[ceil32(_data.length) + 239 len 21]
                                      if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                          revert with 0, 'SafeMath#sub: UNDERFLOW'
                                      stor0[addr(_from)][_id] = 0
                                      if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                          revert with 0, 'SafeMath#add: OVERFLOW'
                                      stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                      mem[ceil32(_data.length) + 128] = _id
                                      mem[ceil32(_data.length) + 160] = stor0[addr(_from)][_id]
                                      log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, _from, _to
                                      if ext_code.hash(_to):
                                  else:
                                      require ext_code.size(unknowncd7c0326Address)
                                      static call unknowncd7c0326Address.proxies(address param1) with:
                                              gas gas_remaining wei
                                             args _from
                                      if not ext_call.success:
                                          revert with ext_call.return_data[0 len return_data.size]
                                      require return_data.size >= 32
                                      if ext_call.return_data[12 len 20] != caller:
                                          if not stor1[addr(_from)][caller]:
                                              revert with 0, 
                                                          32,
                                                          42,
                                                          0x2e4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f4f50455241544f,
                                                          mem[ceil32(_data.length) + 238 len 22]
                                          if not _to:
                                              revert with 0, 
                                                          32,
                                                          43,
                                                          0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                          mem[ceil32(_data.length) + 239 len 21]
                                          if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                              revert with 0, 'SafeMath#sub: UNDERFLOW'
                                          stor0[addr(_from)][_id] = 0
                                      else:
                                          if not _to:
                                              revert with 0, 
                                                          32,
                                                          43,
                                                          0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                          mem[ceil32(_data.length) + 239 len 21]
                                          if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                              revert with 0, 'SafeMath#sub: UNDERFLOW'
                                          stor0[addr(_from)][_id] = 0
                                          if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                              revert with 0, 'SafeMath#add: OVERFLOW'
                                          stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                          log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
          else:
              if totalSupply[_id] > _id % 1099511627776:
                  revert with 0, 'SafeMath#sub: UNDERFLOW'
              if (_id % 1099511627776) - totalSupply[_id] < _value - stor0[addr(_from)][_id]:
                  revert with 0, 
                              32,
                              53,
                              0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a20535550504c595f45584345454445,
                              mem[ceil32(_data.length) + 249 len 11]
              if stor0[addr(_to)][_id] + _value - stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                  revert with 0, 'SafeMath#add: OVERFLOW'
              stor0[addr(_to)][_id] = stor0[addr(_to)][_id] + _value - stor0[addr(_from)][_id]
              if totalSupply[_id] + _value - stor0[addr(_from)][_id] < totalSupply[_id]:
                  revert with 0, 'SafeMath#add: OVERFLOW'
              totalSupply[_id] = totalSupply[_id] + _value - stor0[addr(_from)][_id]
              mem[ceil32(_data.length) + 128] = _id
              mem[ceil32(_data.length) + 160] = _value - stor0[addr(_from)][_id]
              log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, uint64(_id), _to
              if not ext_code.hash(_to):
                  if _data.length > 1:
                      uri[_id] = (2 * _data.length) + 1
                  else:
                      stor9 = 1
                      if stor0[addr(_from)][_id] <= 0:
                          stop
                      if caller == _from:
                          if not _to:
                              revert with 0, 
                                          32,
                                          43,
                                          0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                          mem[ceil32(_data.length) + 239 len 21]
                          if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                              revert with 0, 'SafeMath#sub: UNDERFLOW'
                          stor0[addr(_from)][_id] = 0
                          if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                              revert with 0, 'SafeMath#add: OVERFLOW'
                          stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                          mem[ceil32(_data.length) + 128] = _id
                          mem[ceil32(_data.length) + 160] = stor0[addr(_from)][_id]
                          log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, _from, _to
                          if not ext_code.hash(_to):
                              stop
                          if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                              stop
                      else:
                          if stor10[caller]:
                              if not _to:
                                  revert with 0, 
                                              32,
                                              43,
                                              0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                              mem[ceil32(_data.length) + 239 len 21]
                              if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                  revert with 0, 'SafeMath#sub: UNDERFLOW'
                              stor0[addr(_from)][_id] = 0
                              if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                  revert with 0, 'SafeMath#add: OVERFLOW'
                              stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                              mem[ceil32(_data.length) + 128] = _id
                              mem[ceil32(_data.length) + 160] = stor0[addr(_from)][_id]
                              log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, _from, _to
                              if not ext_code.hash(_to):
                                  stop
                              if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                                  stop
                          else:
                              require ext_code.size(unknowncd7c0326Address)
                              static call unknowncd7c0326Address.proxies(address param1) with:
                                      gas gas_remaining wei
                                     args _from
                              if not ext_call.success:
                                  revert with ext_call.return_data[0 len return_data.size]
                              require return_data.size >= 32
                              if ext_call.return_data[12 len 20] != caller:
                                  if not stor1[addr(_from)][caller]:
                                      revert with 0, 
                                                  32,
                                                  42,
                                                  0x2e4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f4f50455241544f,
                                                  mem[ceil32(_data.length) + 238 len 22]
                                  if not _to:
                                      revert with 0, 
                                                  32,
                                                  43,
                                                  0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                  mem[ceil32(_data.length) + 239 len 21]
                                  if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                                  stor0[addr(_from)][_id] = 0
                                  if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                      revert with 0, 'SafeMath#add: OVERFLOW'
                                  stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                  log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
                              else:
                                  if not _to:
                                      revert with 0, 
                                                  32,
                                                  43,
                                                  0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                  mem[ceil32(_data.length) + 239 len 21]
                                  if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                                  stor0[addr(_from)][_id] = 0
                                  if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                      revert with 0, 'SafeMath#add: OVERFLOW'
                                  stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                  log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
                                  if ext_code.hash(_to):
              else:
                  if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                      if _data.length > 1:
                          uri[_id] = (2 * _data.length) + 1
                      else:
                          stor9 = 1
                          if stor0[addr(_from)][_id] <= 0:
                              stop
                          if caller == _from:
                              if not _to:
                                  revert with 0, 
                                              32,
                                              43,
                                              0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                              mem[ceil32(_data.length) + 239 len 21]
                              if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                  revert with 0, 'SafeMath#sub: UNDERFLOW'
                              stor0[addr(_from)][_id] = 0
                              if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                  revert with 0, 'SafeMath#add: OVERFLOW'
                              stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                              mem[ceil32(_data.length) + 128] = _id
                              mem[ceil32(_data.length) + 160] = stor0[addr(_from)][_id]
                              log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, _from, _to
                              if not ext_code.hash(_to):
                                  stop
                              if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                                  stop
                          else:
                              if stor10[caller]:
                                  if not _to:
                                      revert with 0, 
                                                  32,
                                                  43,
                                                  0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                  mem[ceil32(_data.length) + 239 len 21]
                                  if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                                  stor0[addr(_from)][_id] = 0
                                  if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                      revert with 0, 'SafeMath#add: OVERFLOW'
                                  stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                  mem[ceil32(_data.length) + 128] = _id
                                  mem[ceil32(_data.length) + 160] = stor0[addr(_from)][_id]
                                  log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, _from, _to
                                  if not ext_code.hash(_to):
                                      stop
                                  if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                                      stop
                              else:
                                  require ext_code.size(unknowncd7c0326Address)
                                  static call unknowncd7c0326Address.proxies(address param1) with:
                                          gas gas_remaining wei
                                         args _from
                                  if not ext_call.success:
                                      revert with ext_call.return_data[0 len return_data.size]
                                  require return_data.size >= 32
                                  if ext_call.return_data[12 len 20] != caller:
                                      if not stor1[addr(_from)][caller]:
                                          revert with 0, 
                                                      32,
                                                      42,
                                                      0x2e4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f4f50455241544f,
                                                      mem[ceil32(_data.length) + 238 len 22]
                                  if not _to:
                                      revert with 0, 
                                                  32,
                                                  43,
                                                  0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                  mem[ceil32(_data.length) + 239 len 21]
                                  if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                                  stor0[addr(_from)][_id] = 0
                                  if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                      revert with 0, 'SafeMath#add: OVERFLOW'
                                  stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                  log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
      else:
          if creator[_id] == caller:
              if totalSupply[_id] > _id % 1099511627776:
                  revert with 0, 'SafeMath#sub: UNDERFLOW'
              if (_id % 1099511627776) - totalSupply[_id] < _value - stor0[addr(_from)][_id]:
                  revert with 0, 
                              32,
                              53,
                              0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a20535550504c595f45584345454445,
                              mem[ceil32(_data.length) + 249 len 11]
              if stor0[addr(_to)][_id] + _value - stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                  revert with 0, 'SafeMath#add: OVERFLOW'
              stor0[addr(_to)][_id] = stor0[addr(_to)][_id] + _value - stor0[addr(_from)][_id]
              if totalSupply[_id] + _value - stor0[addr(_from)][_id] < totalSupply[_id]:
                  revert with 0, 'SafeMath#add: OVERFLOW'
              totalSupply[_id] = totalSupply[_id] + _value - stor0[addr(_from)][_id]
              mem[ceil32(_data.length) + 128] = _id
              mem[ceil32(_data.length) + 160] = _value - stor0[addr(_from)][_id]
              log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, uint64(_id), _to
              if not ext_code.hash(_to):
                  if _data.length > 1:
                      uri[_id] = (2 * _data.length) + 1
                  else:
                      stor9 = 1
                      if stor0[addr(_from)][_id] <= 0:
                          stop
                      if caller == _from:
                          if not _to:
                              revert with 0, 
                                          32,
                                          43,
                                          0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                          mem[ceil32(_data.length) + 239 len 21]
                          if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                              revert with 0, 'SafeMath#sub: UNDERFLOW'
                          stor0[addr(_from)][_id] = 0
                          if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                              revert with 0, 'SafeMath#add: OVERFLOW'
                          stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                          mem[ceil32(_data.length) + 128] = _id
                          mem[ceil32(_data.length) + 160] = stor0[addr(_from)][_id]
                          log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, _from, _to
                          if not ext_code.hash(_to):
                              stop
                          if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                              stop
                      else:
                          if stor10[caller]:
                              if not _to:
                                  revert with 0, 
                                              32,
                                              43,
                                              0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                              mem[ceil32(_data.length) + 239 len 21]
                              if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                  revert with 0, 'SafeMath#sub: UNDERFLOW'
                              stor0[addr(_from)][_id] = 0
                              if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                  revert with 0, 'SafeMath#add: OVERFLOW'
                              stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                              mem[ceil32(_data.length) + 128] = _id
                              mem[ceil32(_data.length) + 160] = stor0[addr(_from)][_id]
                              log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, _from, _to
                              if not ext_code.hash(_to):
                                  stop
                              if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                                  stop
                          else:
                              require ext_code.size(unknowncd7c0326Address)
                              static call unknowncd7c0326Address.proxies(address param1) with:
                                      gas gas_remaining wei
                                     args _from
                              if not ext_call.success:
                                  revert with ext_call.return_data[0 len return_data.size]
                              require return_data.size >= 32
                              if ext_call.return_data[12 len 20] != caller:
                                  if not stor1[addr(_from)][caller]:
                                      revert with 0, 
                                                  32,
                                                  42,
                                                  0x2e4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f4f50455241544f,
                                                  mem[ceil32(_data.length) + 238 len 22]
                                  if not _to:
                                      revert with 0, 
                                                  32,
                                                  43,
                                                  0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                  mem[ceil32(_data.length) + 239 len 21]
                                  if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                                  stor0[addr(_from)][_id] = 0
                                  if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                      revert with 0, 'SafeMath#add: OVERFLOW'
                                  stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                  log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
                                  if ext_code.hash(_to):
                              else:
                                  if not _to:
                                      revert with 0, 
                                                  32,
                                                  43,
                                                  0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                  mem[ceil32(_data.length) + 239 len 21]
                                  if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                                  stor0[addr(_from)][_id] = 0
                                  if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                      revert with 0, 'SafeMath#add: OVERFLOW'
                                  stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                  log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
                                  if ext_code.hash(_to):
                                      if ext_code.hash(_to) != 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
              else:
                  if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                      if _data.length > 1:
                          uri[_id] = (2 * _data.length) + 1
                      else:
                          stor9 = 1
                          if stor0[addr(_from)][_id] <= 0:
                              stop
                          if caller == _from:
                              if not _to:
                                  revert with 0, 
                                              32,
                                              43,
                                              0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                              mem[ceil32(_data.length) + 239 len 21]
                              if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                  revert with 0, 'SafeMath#sub: UNDERFLOW'
                              stor0[addr(_from)][_id] = 0
                              if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                  revert with 0, 'SafeMath#add: OVERFLOW'
                              stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                              mem[ceil32(_data.length) + 128] = _id
                              mem[ceil32(_data.length) + 160] = stor0[addr(_from)][_id]
                              log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, _from, _to
                              if not ext_code.hash(_to):
                                  stop
                              if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                                  stop
                          else:
                              if stor10[caller]:
                                  if not _to:
                                      revert with 0, 
                                                  32,
                                                  43,
                                                  0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                  mem[ceil32(_data.length) + 239 len 21]
                                  if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                                  stor0[addr(_from)][_id] = 0
                                  if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                      revert with 0, 'SafeMath#add: OVERFLOW'
                                  stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                  mem[ceil32(_data.length) + 128] = _id
                                  mem[ceil32(_data.length) + 160] = stor0[addr(_from)][_id]
                                  log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, _from, _to
                                  if not ext_code.hash(_to):
                                      stop
                                  if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                                      stop
                              else:
                                  require ext_code.size(unknowncd7c0326Address)
                                  static call unknowncd7c0326Address.proxies(address param1) with:
                                          gas gas_remaining wei
                                         args _from
                                  if not ext_call.success:
                                      revert with ext_call.return_data[0 len return_data.size]
                                  require return_data.size >= 32
                                  if ext_call.return_data[12 len 20] != caller:
                                      if not stor1[addr(_from)][caller]:
                                          revert with 0, 
                                                      32,
                                                      42,
                                                      0x2e4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f4f50455241544f,
                                                      mem[ceil32(_data.length) + 238 len 22]
                                      if not _to:
                                          revert with 0, 
                                                      32,
                                                      43,
                                                      0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                      mem[ceil32(_data.length) + 239 len 21]
                                      if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                          revert with 0, 'SafeMath#sub: UNDERFLOW'
                                      stor0[addr(_from)][_id] = 0
                                      if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                          revert with 0, 'SafeMath#add: OVERFLOW'
                                      stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                      log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
                                  else:
                                      if not _to:
                                          revert with 0, 
                                                      32,
                                                      43,
                                                      0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                      mem[ceil32(_data.length) + 239 len 21]
                                      if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                          revert with 0, 'SafeMath#sub: UNDERFLOW'
                                      stor0[addr(_from)][_id] = 0
                                      if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                          revert with 0, 'SafeMath#add: OVERFLOW'
                                      stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                      log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
                                      if ext_code.hash(_to):
          else:
              if not stor10[caller]:
                  require ext_code.size(unknowncd7c0326Address)
                  static call unknowncd7c0326Address.proxies(address param1) with:
                          gas gas_remaining wei
                         args creator[_id]
                  if not ext_call.success:
                      revert with ext_call.return_data[0 len return_data.size]
                  require return_data.size >= 32
                  if ext_call.return_data[12 len 20] != caller:
                      revert with 0, 
                                  32,
                                  58,
                                  0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a204f4e4c595f43524541544f525f414c4c4f5745,
                                  mem[ceil32(_data.length) + 254 len 6]
                  if totalSupply[_id] > _id % 1099511627776:
                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                  if (_id % 1099511627776) - totalSupply[_id] < _value - stor0[addr(_from)][_id]:
                      revert with 0, 
                                  32,
                                  53,
                                  0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a20535550504c595f45584345454445,
                                  mem[ceil32(_data.length) + 249 len 11]
                  if stor0[addr(_to)][_id] + _value - stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                      revert with 0, 'SafeMath#add: OVERFLOW'
                  stor0[addr(_to)][_id] = stor0[addr(_to)][_id] + _value - stor0[addr(_from)][_id]
                  if totalSupply[_id] + _value - stor0[addr(_from)][_id] < totalSupply[_id]:
                      revert with 0, 'SafeMath#add: OVERFLOW'
                  totalSupply[_id] = totalSupply[_id] + _value - stor0[addr(_from)][_id]
                  log 0xc3d58168: 0, Mask(224, 0, _id), _value - stor0[addr(_from)][_id], caller, uint64(_id), _to
                  if not ext_code.hash(_to):
                      if _data.length > 1:
                          uri[_id] = (2 * _data.length) + 1
                      else:
                          stor9 = 1
                          if stor0[addr(_from)][_id] <= 0:
                              stop
                          if caller == _from:
                              if not _to:
                                  revert with 0, 
                                              32,
                                              43,
                                              0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                              mem[ceil32(_data.length) + 239 len 21]
                              if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                  revert with 0, 'SafeMath#sub: UNDERFLOW'
                              stor0[addr(_from)][_id] = 0
                              if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                  revert with 0, 'SafeMath#add: OVERFLOW'
                              stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                              log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
                              if not ext_code.hash(_to):
                                  stop
                              if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                                  stop
                          else:
                              if not stor10[caller]:
                                  require ext_code.size(unknowncd7c0326Address)
                                  static call unknowncd7c0326Address.proxies(address param1) with:
                                          gas gas_remaining wei
                                         args _from
                                  if not ext_call.success:
                                      revert with ext_call.return_data[0 len return_data.size]
                                  require return_data.size >= 32
                                  if ext_call.return_data[12 len 20] != caller:
                                      if not stor1[addr(_from)][caller]:
                                          revert with 0, 
                                                      32,
                                                      42,
                                                      0x2e4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f4f50455241544f,
                                                      mem[ceil32(_data.length) + 238 len 22]
                                      if not _to:
                                          revert with 0, 
                                                      32,
                                                      43,
                                                      0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                      mem[ceil32(_data.length) + 239 len 21]
                                  else:
                                      if not _to:
                                          revert with 0, 
                                                      32,
                                                      43,
                                                      0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                      mem[ceil32(_data.length) + 239 len 21]
                                      if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                          revert with 0, 'SafeMath#sub: UNDERFLOW'
                              else:
                                  if not _to:
                                      revert with 0, 
                                                  32,
                                                  43,
                                                  0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                  mem[ceil32(_data.length) + 239 len 21]
                                  if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                                  stor0[addr(_from)][_id] = 0
                                  if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                      revert with 0, 'SafeMath#add: OVERFLOW'
                                  stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                  log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
                  else:
                      if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                          if _data.length > 1:
                              uri[_id] = (2 * _data.length) + 1
                          else:
                              stor9 = 1
                              if stor0[addr(_from)][_id] <= 0:
                                  stop
                              if caller == _from:
                                  if not _to:
                                      revert with 0, 
                                                  32,
                                                  43,
                                                  0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                  mem[ceil32(_data.length) + 239 len 21]
                                  if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                                  stor0[addr(_from)][_id] = 0
                                  if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                      revert with 0, 'SafeMath#add: OVERFLOW'
                                  stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                  log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
                                  if not ext_code.hash(_to):
                                      stop
                              else:
                                  if stor10[caller]:
                                      if not _to:
                                          revert with 0, 
                                                      32,
                                                      43,
                                                      0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                      mem[ceil32(_data.length) + 239 len 21]
                                      if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                          revert with 0, 'SafeMath#sub: UNDERFLOW'
                                      stor0[addr(_from)][_id] = 0
                                      if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                          revert with 0, 'SafeMath#add: OVERFLOW'
                                      stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                      log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
                                  else:
                                      require ext_code.size(unknowncd7c0326Address)
                                      static call unknowncd7c0326Address.proxies(address param1) with:
                                              gas gas_remaining wei
                                             args _from
                                      if not ext_call.success:
                                          revert with ext_call.return_data[0 len return_data.size]
                                      require return_data.size >= 32
                                      if ext_call.return_data[12 len 20] != caller:
                                          if not stor1[addr(_from)][caller]:
                                              revert with 0, 
                                                          32,
                                                          42,
                                                          0x2e4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f4f50455241544f,
                                                          mem[ceil32(_data.length) + 238 len 22]
                                      else:
                                      if not _to:
                                          revert with 0, 
                                                      32,
                                                      43,
                                                      0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                      mem[ceil32(_data.length) + 239 len 21]
              else:
                  if totalSupply[_id] > _id % 1099511627776:
                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                  if (_id % 1099511627776) - totalSupply[_id] < _value - stor0[addr(_from)][_id]:
                      revert with 0, 
                                  32,
                                  53,
                                  0x444173736574436f6e7472616374536861726564235f726571756972654d696e7461626c653a20535550504c595f45584345454445,
                                  mem[ceil32(_data.length) + 249 len 11]
                  if stor0[addr(_to)][_id] + _value - stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                      revert with 0, 'SafeMath#add: OVERFLOW'
                  stor0[addr(_to)][_id] = stor0[addr(_to)][_id] + _value - stor0[addr(_from)][_id]
                  if totalSupply[_id] + _value - stor0[addr(_from)][_id] < totalSupply[_id]:
                      revert with 0, 'SafeMath#add: OVERFLOW'
                  totalSupply[_id] = totalSupply[_id] + _value - stor0[addr(_from)][_id]
                  mem[ceil32(_data.length) + 128] = _id
                  mem[ceil32(_data.length) + 160] = _value - stor0[addr(_from)][_id]
                  log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, uint64(_id), _to
                  if not ext_code.hash(_to):
                      if _data.length > 1:
                          uri[_id] = (2 * _data.length) + 1
                      else:
                          stor9 = 1
                          if stor0[addr(_from)][_id] <= 0:
                              stop
                          if caller == _from:
                              if not _to:
                                  revert with 0, 
                                              32,
                                              43,
                                              0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                              mem[ceil32(_data.length) + 239 len 21]
                              if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                  revert with 0, 'SafeMath#sub: UNDERFLOW'
                              stor0[addr(_from)][_id] = 0
                              if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                  revert with 0, 'SafeMath#add: OVERFLOW'
                              stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                              mem[ceil32(_data.length) + 128] = _id
                              mem[ceil32(_data.length) + 160] = stor0[addr(_from)][_id]
                              log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, _from, _to
                              if not ext_code.hash(_to):
                                  stop
                              if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                                  stop
                          else:
                              if stor10[caller]:
                                  if not _to:
                                      revert with 0, 
                                                  32,
                                                  43,
                                                  0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                  mem[ceil32(_data.length) + 239 len 21]
                                  if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                                  stor0[addr(_from)][_id] = 0
                                  if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                      revert with 0, 'SafeMath#add: OVERFLOW'
                                  stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                  mem[ceil32(_data.length) + 128] = _id
                                  mem[ceil32(_data.length) + 160] = stor0[addr(_from)][_id]
                                  log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, _from, _to
                                  if ext_code.hash(_to):
                              else:
                                  require ext_code.size(unknowncd7c0326Address)
                                  static call unknowncd7c0326Address.proxies(address param1) with:
                                          gas gas_remaining wei
                                         args _from
                                  if not ext_call.success:
                                      revert with ext_call.return_data[0 len return_data.size]
                                  require return_data.size >= 32
                                  if ext_call.return_data[12 len 20] != caller:
                                      if not stor1[addr(_from)][caller]:
                                          revert with 0, 
                                                      32,
                                                      42,
                                                      0x2e4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f4f50455241544f,
                                                      mem[ceil32(_data.length) + 238 len 22]
                                  else:
                                  if not _to:
                                      revert with 0, 
                                                  32,
                                                  43,
                                                  0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                  mem[ceil32(_data.length) + 239 len 21]
                                  if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                                  stor0[addr(_from)][_id] = 0
                                  if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                      revert with 0, 'SafeMath#add: OVERFLOW'
                                  stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                  log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
                  else:
                      if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                          if _data.length > 1:
                              uri[_id] = (2 * _data.length) + 1
                          else:
                              stor9 = 1
                              if stor0[addr(_from)][_id] <= 0:
                                  stop
                              if caller == _from:
                                  if not _to:
                                      revert with 0, 
                                                  32,
                                                  43,
                                                  0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                  mem[ceil32(_data.length) + 239 len 21]
                                  if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                      revert with 0, 'SafeMath#sub: UNDERFLOW'
                                  stor0[addr(_from)][_id] = 0
                                  if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                      revert with 0, 'SafeMath#add: OVERFLOW'
                                  stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                  mem[ceil32(_data.length) + 128] = _id
                                  mem[ceil32(_data.length) + 160] = stor0[addr(_from)][_id]
                                  log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, _from, _to
                                  if not ext_code.hash(_to):
                                      stop
                                  if ext_code.hash(_to) == 0xc5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470:
                                      stop
                              else:
                                  if stor10[caller]:
                                      if not _to:
                                          revert with 0, 
                                                      32,
                                                      43,
                                                      0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                      mem[ceil32(_data.length) + 239 len 21]
                                      if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                          revert with 0, 'SafeMath#sub: UNDERFLOW'
                                      stor0[addr(_from)][_id] = 0
                                      if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                          revert with 0, 'SafeMath#add: OVERFLOW'
                                      stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                      mem[ceil32(_data.length) + 128] = _id
                                      mem[ceil32(_data.length) + 160] = stor0[addr(_from)][_id]
                                      log 0xc3d58168: Mask(8 * -ceil32(_data.length) + _data.length + 32, 0, 0), mem[_data.length + 160 len -_data.length + ceil32(_data.length) + 32], caller, _from, _to
                                      if ext_code.hash(_to):
                                  else:
                                      require ext_code.size(unknowncd7c0326Address)
                                      static call unknowncd7c0326Address.proxies(address param1) with:
                                              gas gas_remaining wei
                                             args _from
                                      if not ext_call.success:
                                          revert with ext_call.return_data[0 len return_data.size]
                                      require return_data.size >= 32
                                      if ext_call.return_data[12 len 20] != caller:
                                          if not stor1[addr(_from)][caller]:
                                              revert with 0, 
                                                          32,
                                                          42,
                                                          0x2e4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f4f50455241544f,
                                                          mem[ceil32(_data.length) + 238 len 22]
                                      if not _to:
                                          revert with 0, 
                                                      32,
                                                      43,
                                                      0xfe4552433131353523736166655472616e7366657246726f6d3a20494e56414c49445f524543495049454e,
                                                      mem[ceil32(_data.length) + 239 len 21]
                                      if stor0[addr(_from)][_id] > stor0[addr(_from)][_id]:
                                          revert with 0, 'SafeMath#sub: UNDERFLOW'
                                      stor0[addr(_from)][_id] = 0
                                      if stor0[addr(_to)][_id] + stor0[addr(_from)][_id] < stor0[addr(_to)][_id]:
                                          revert with 0, 'SafeMath#add: OVERFLOW'
                                      stor0[addr(_to)][_id] += stor0[addr(_from)][_id]
                                      log 0xc3d58168: 0, Mask(224, 0, _id), stor0[addr(_from)][_id], caller, _from, _to
  ...  # Decompilation aborted, sorry: ("decompilation didn't finish",)
 into readable Solidity-syntax contracts – to enable static and dynamic analysis of compiled contracts but also vulnerability discovery.

## Getting Started
First you can either compile your own Ethereum contract or analyze public contract from [Etherscan](https://etherscan.io/address/0x8d12a197cb00d4747a1fe03395095ce2a5cc6819#code).

`more .\vulnerable.sol`
```
contract SendBalance {
    mapping ( address => uint ) userBalances ;
    bool withdrawn = false ;

    function getBalance (address u) constant returns ( uint ){
        return userBalances [u];
    }

    function addToBalance () {
        userBalances[msg.sender] += msg.value ;
    }

    function withdrawBalance (){
        if (!(msg.sender.call.gas(0x1111).value (
            userBalances [msg . sender ])())) { throw ; }
        userBalances [msg.sender ] = 0;
    }
}
```
`solc --abi -o output vulnerable.sol`

`solc --bin -o output vulnerable.sol`

`solc --bin-runtime -o output vulnerable.sol`

`$abi = Get-Content .\output\SendBalance.abi`

`$bin = Get-Content .\output\SendBalance.bin`

`$binRuntime = Get-Content .\output\SendBalance.bin-runtime`

`echo $abi`
```
[{"constant":false,"inputs":[],"name":"withdrawBalance","outputs":[],"type":"function"},{"constant":false,"inputs":[],"name":"addToBalance","outputs":[],"type":"function"},{"constant":true,"inputs":[{"name":"u","type":"address"}],"name":"ge
tBalance","outputs":[{"name":"","type":"uint256"}],"type":"function"}]
```
`echo $bin`
```
60606040526000600160006101000a81548160ff021916908302179055506101bb8061002b6000396000f360606040526000357c0100000000000000000000000000000000000000000000000000000000900480635fd8c7101461004f578063c0e317fb1461005e578063f8b2cb4f1461006d5761004d56
5b005b61005c6004805050610099565b005b61006b600480505061013e565b005b610083600480803590602001909190505061017d565b6040518082815260200191505060405180910390f35b3373ffffffffffffffffffffffffffffffffffffffff16611111600060005060003373ffffffffffffffff
ffffffffffffffffffffffff16815260200190815260200160002060005054604051809050600060405180830381858888f19350505050151561010657610002565b6000600060005060003373ffffffffffffffffffffffffffffffffffffffff168152602001908152602001600020600050819055505b
565b34600060005060003373ffffffffffffffffffffffffffffffffffffffff1681526020019081526020016000206000828282505401925050819055505b565b6000600060005060008373ffffffffffffffffffffffffffffffffffffffff1681526020019081526020016000206000505490506101b6
565b91905056
```
`echo $binRuntime`
```
60606040526000357c0100000000000000000000000000000000000000000000000000000000900480635fd8c7101461004f578063c0e317fb1461005e578063f8b2cb4f1461006d5761004d565b005b61005c6004805050610099565b005b61006b600480505061013e565b005b61008360048080359060
2001909190505061017d565b6040518082815260200191505060405180910390f35b3373ffffffffffffffffffffffffffffffffffffffff16611111600060005060003373ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060005054604051809050600060405180
830381858888f19350505050151561010657610002565b6000600060005060003373ffffffffffffffffffffffffffffffffffffffff168152602001908152602001600020600050819055505b565b34600060005060003373ffffffffffffffffffffffffffffffffffffffff1681526020019081526020
016000206000828282505401925050819055505b565b6000600060005060008373ffffffffffffffffffffffffffffffffffffffff1681526020019081526020016000206000505490506101b6565b91905056
```

## Using Porosity
### List functions 
You can get the list of all the functions from the dispatch routine using the `--list` option.

`porosity --code $code --abi $abi --list --verbose 0`

```
Porosity v0.1 (https://www.comae.io)
Matt Suiche, Comae Technologies <support@comae.io>
The Ethereum bytecode commandline decompiler.
Decompiles the given Ethereum input bytecode and outputs the Solidity code.

Attempting to parse ABI definition...
Success.
[+] Hash: 0x0A19B14A (trade) (1 references)
[+] Hash: 0x0B927666 (order) (1 references)
[+] Hash: 0x19774D43 (orderFills) (1 references)
[+] Hash: 0x278B8C0E (cancelOrder) (1 references)
[+] Hash: 0x2E1A7D4D (withdraw) (1 references)
[+] Hash: 0x338B5DEA (depositToken) (1 references)
[+] Hash: 0x46BE96C3 (amountFilled) (1 references)
[+] Hash: 0x508493BC (tokens) (1 references)
[+] Hash: 0x54D03B5C (changeFeeMake) (1 references)
[+] Hash: 0x57786394 (feeMake) (1 references)
[+] Hash: 0x5E1D7AE4 (changeFeeRebate) (1 references)
[+] Hash: 0x65E17C9D (feeAccount) (1 references)
[+] Hash: 0x6C86888B (testTrade) (1 references)
[+] Hash: 0x71FFCB16 (changeFeeAccount) (1 references)
[+] Hash: 0x731C2F81 (feeRebate) (1 references)
[+] Hash: 0x8823A9C0 (changeFeeTake) (1 references)
[+] Hash: 0x8F283970 (changeAdmin) (1 references)
[+] Hash: 0x9E281A98 (withdrawToken) (1 references)
[+] Hash: 0xBB5F4629 (orders) (1 references)
[+] Hash: 0xC281309E (feeTake) (1 references)
[+] Hash: 0xD0E30DB0 (deposit) (1 references)
[+] Hash: 0xE8F6BC2E (changeAccountLevelsAddr) (1 references)
[+] Hash: 0xF3412942 (accountLevelsAddr) (1 references)
[+] Hash: 0xF7888AEC (balanceOf) (1 references)
[+] Hash: 0xF851A440 (admin) (1 references)
[+] Hash: 0xFB6E155F (availableVolume) (1 references)
```
### Disassemble
Using the `--disassm` option, you will be able to display the assembly code.

`porosity --abi $abi --code $code --disassm`


<details>
    <summary>click here to view <b>Disassembly</b></summary>

```
Porosity v0.1 (https://www.comae.io)
Matt Suiche, Comae Technologies <support@comae.io>
The Ethereum bytecode commandline decompiler.
Decompiles the given Ethereum input bytecode and outputs the Solidity code.

Attempting to parse ABI definition...
Success.
Contract::setABI: Name: withdrawBalance()
Contract::setABI: signature: 0x5fd8c710
Contract::setABI: Name: addToBalance()
Contract::setABI: signature: 0xc0e317fb
Contract::setABI: Name: getBalance(address)
Contract::setABI: signature: 0xf8b2cb4f


- Total byte code size: 0x1bb (443)


loc_00000000:
0x00000000 60 60                      PUSH1 60
0x00000002 60 40                      PUSH1 40
0x00000004 52                         MSTORE
0x00000005 60 00                      PUSH1 00
0x00000007 35                         CALLDATALOAD
0x00000008 7c 00  00  00  00  +      PUSH29 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 01
0x00000026 90                         SWAP1
0x00000027 04                         DIV
0x00000028 80                         DUP1
0x00000029 63 10  c7  d8  5f          PUSH4 10 c7 d8 5f
0x0000002e 14                         EQ
0x0000002f 61 4f  00                  PUSH2 4f 00
0x00000032 57                         JUMPI

loc_00000033:
0x00000033 80                         DUP1
0x00000034 63 fb  17  e3  c0          PUSH4 fb 17 e3 c0
0x00000039 14                         EQ
0x0000003a 61 5e  00                  PUSH2 5e 00
0x0000003d 57                         JUMPI

loc_0000003e:
0x0000003e 80                         DUP1
0x0000003f 63 4f  cb  b2  f8          PUSH4 4f cb b2 f8
0x00000044 14                         EQ
0x00000045 61 6d  00                  PUSH2 6d 00
0x00000048 57                         JUMPI

loc_00000049:
0x00000049 61 4d  00                  PUSH2 4d 00
0x0000004c 56                         JUMP

loc_0000004d:
0x0000004d 5b                         JUMPDEST
0x0000004e 00                         STOP

withdrawBalance():
0x0000004f 5b                         JUMPDEST
0x00000050 61 5c  00                  PUSH2 5c 00
0x00000053 60 04                      PUSH1 04
0x00000055 80                         DUP1
0x00000056 50                         POP
0x00000057 50                         POP
0x00000058 61 99  00                  PUSH2 99 00
0x0000005b 56                         JUMP

loc_0000005c:
0x0000005c 5b                         JUMPDEST
0x0000005d 00                         STOP

addToBalance():
0x0000005e 5b                         JUMPDEST
0x0000005f 61 6b  00                  PUSH2 6b 00
0x00000062 60 04                      PUSH1 04
0x00000064 80                         DUP1
0x00000065 50                         POP
0x00000066 50                         POP
0x00000067 61 3e  01                  PUSH2 3e 01
0x0000006a 56                         JUMP

loc_0000006b:
0x0000006b 5b                         JUMPDEST
0x0000006c 00                         STOP

getBalance(address):
0x0000006d 5b                         JUMPDEST
0x0000006e 61 83  00                  PUSH2 83 00
0x00000071 60 04                      PUSH1 04
0x00000073 80                         DUP1
0x00000074 80                         DUP1
0x00000075 35                         CALLDATALOAD
0x00000076 90                         SWAP1
0x00000077 60 20                      PUSH1 20
0x00000079 01                         ADD
0x0000007a 90                         SWAP1
0x0000007b 91                         SWAP2
0x0000007c 90                         SWAP1
0x0000007d 50                         POP
0x0000007e 50                         POP
0x0000007f 61 7d  01                  PUSH2 7d 01
0x00000082 56                         JUMP

loc_00000083:
0x00000083 5b                         JUMPDEST
0x00000084 60 40                      PUSH1 40
0x00000086 51                         MLOAD
0x00000087 80                         DUP1
0x00000088 82                         DUP3
0x00000089 81                         DUP2
0x0000008a 52                         MSTORE
0x0000008b 60 20                      PUSH1 20
0x0000008d 01                         ADD
0x0000008e 91                         SWAP2
0x0000008f 50                         POP
0x00000090 50                         POP
0x00000091 60 40                      PUSH1 40
0x00000093 51                         MLOAD
0x00000094 80                         DUP1
0x00000095 91                         SWAP2
0x00000096 03                         SUB
0x00000097 90                         SWAP1
0x00000098 f3                         RETURN

loc_00000099:
0x00000099 5b                         JUMPDEST
0x0000009a 33                         CALLER
0x0000009b 73 ff  ff  ff  ff  +      PUSH20 ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff
0x000000b0 16                         AND
0x000000b1 61 11  11                  PUSH2 11 11
0x000000b4 60 00                      PUSH1 00
0x000000b6 60 00                      PUSH1 00
0x000000b8 50                         POP
0x000000b9 60 00                      PUSH1 00
0x000000bb 33                         CALLER
0x000000bc 73 ff  ff  ff  ff  +      PUSH20 ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff
0x000000d1 16                         AND
0x000000d2 81                         DUP2
0x000000d3 52                         MSTORE
0x000000d4 60 20                      PUSH1 20
0x000000d6 01                         ADD
0x000000d7 90                         SWAP1
0x000000d8 81                         DUP2
0x000000d9 52                         MSTORE
0x000000da 60 20                      PUSH1 20
0x000000dc 01                         ADD
0x000000dd 60 00                      PUSH1 00
0x000000df 20                         SHA3
0x000000e0 60 00                      PUSH1 00
0x000000e2 50                         POP
0x000000e3 54                         SLOAD
0x000000e4 60 40                      PUSH1 40
0x000000e6 51                         MLOAD
0x000000e7 80                         DUP1
0x000000e8 90                         SWAP1
0x000000e9 50                         POP
0x000000ea 60 00                      PUSH1 00
0x000000ec 60 40                      PUSH1 40
0x000000ee 51                         MLOAD
0x000000ef 80                         DUP1
0x000000f0 83                         DUP4
0x000000f1 03                         SUB
0x000000f2 81                         DUP2
0x000000f3 85                         DUP6
0x000000f4 88                         DUP9
0x000000f5 88                         DUP9
0x000000f6 f1                         CALL
0x000000f7 93                         SWAP4
0x000000f8 50                         POP
0x000000f9 50                         POP
0x000000fa 50                         POP
0x000000fb 50                         POP
0x000000fc 15                         ISZERO
0x000000fd 15                         ISZERO
0x000000fe 61 06  01                  PUSH2 06 01
0x00000101 57                         JUMPI

loc_00000102:
0x00000102 61 02  00                  PUSH2 02 00
0x00000105 56                         JUMP

loc_00000106:
0x00000106 5b                         JUMPDEST
0x00000107 60 00                      PUSH1 00
0x00000109 60 00                      PUSH1 00
0x0000010b 60 00                      PUSH1 00
0x0000010d 50                         POP
0x0000010e 60 00                      PUSH1 00
0x00000110 33                         CALLER
0x00000111 73 ff  ff  ff  ff  +      PUSH20 ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff
0x00000126 16                         AND
0x00000127 81                         DUP2
0x00000128 52                         MSTORE
0x00000129 60 20                      PUSH1 20
0x0000012b 01                         ADD
0x0000012c 90                         SWAP1
0x0000012d 81                         DUP2
0x0000012e 52                         MSTORE
0x0000012f 60 20                      PUSH1 20
0x00000131 01                         ADD
0x00000132 60 00                      PUSH1 00
0x00000134 20                         SHA3
0x00000135 60 00                      PUSH1 00
0x00000137 50                         POP
0x00000138 81                         DUP2
0x00000139 90                         SWAP1
0x0000013a 55                         SSTORE
0x0000013b 50                         POP

loc_0000013c:
0x0000013c 5b                         JUMPDEST
0x0000013d 56                         JUMP

loc_0000013e:
0x0000013e 5b                         JUMPDEST
0x0000013f 34                         CALLVALUE
0x00000140 60 00                      PUSH1 00
0x00000142 60 00                      PUSH1 00
0x00000144 50                         POP
0x00000145 60 00                      PUSH1 00
0x00000147 33                         CALLER
0x00000148 73 ff  ff  ff  ff  +      PUSH20 ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff
0x0000015d 16                         AND
0x0000015e 81                         DUP2
0x0000015f 52                         MSTORE
0x00000160 60 20                      PUSH1 20
0x00000162 01                         ADD
0x00000163 90                         SWAP1
0x00000164 81                         DUP2
0x00000165 52                         MSTORE
0x00000166 60 20                      PUSH1 20
0x00000168 01                         ADD
0x00000169 60 00                      PUSH1 00
0x0000016b 20                         SHA3
0x0000016c 60 00                      PUSH1 00
0x0000016e 82                         DUP3
0x0000016f 82                         DUP3
0x00000170 82                         DUP3
0x00000171 50                         POP
0x00000172 54                         SLOAD
0x00000173 01                         ADD
0x00000174 92                         SWAP3
0x00000175 50                         POP
0x00000176 50                         POP
0x00000177 81                         DUP2
0x00000178 90                         SWAP1
0x00000179 55                         SSTORE
0x0000017a 50                         POP

loc_0000017b:
0x0000017b 5b                         JUMPDEST
0x0000017c 56                         JUMP

loc_0000017d:
0x0000017d 5b                         JUMPDEST
0x0000017e 60 00                      PUSH1 00
0x00000180 60 00                      PUSH1 00
0x00000182 60 00                      PUSH1 00
0x00000184 50                         POP
0x00000185 60 00                      PUSH1 00
0x00000187 83                         DUP4
0x00000188 73 ff  ff  ff  ff  +      PUSH20 ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff
0x0000019d 16                         AND
0x0000019e 81                         DUP2
0x0000019f 52                         MSTORE
0x000001a0 60 20                      PUSH1 20
0x000001a2 01                         ADD
0x000001a3 90                         SWAP1
0x000001a4 81                         DUP2
0x000001a5 52                         MSTORE
0x000001a6 60 20                      PUSH1 20
0x000001a8 01                         ADD
0x000001a9 60 00                      PUSH1 00
0x000001ab 20                         SHA3
0x000001ac 60 00                      PUSH1 00
0x000001ae 50                         POP
0x000001af 54                         SLOAD
0x000001b0 90                         SWAP1
0x000001b1 50                         POP
0x000001b2 61 b6  01                  PUSH2 b6 01
0x000001b5 56                         JUMP

loc_000001b6:
0x000001b6 5b                         JUMPDEST
0x000001b7 91                         SWAP2
0x000001b8 90                         SWAP1
0x000001b9 50                         POP
0x000001ba 56                         JUMP
```

</details>

### Decompilation
The `--decompile` option will decompile the given function or contract and attempt to highlight vulnerabilities.

`porosity --abi $abi --code $code --decompile --verbose 0`

<details>
    <summary>click here to view <b>Decompilation</b></summary>

```
Porosity v0.1 (https://www.comae.io)
Matt Suiche, Comae Technologies <support@comae.io>
The Ethereum bytecode commandline decompiler.
Decompiles the given Ethereum input bytecode and outputs the Solidity code.

Attempting to parse ABI definition...
Success.

Hash: 0x5FD8C710
function withdrawBalance() {
      if (msg.sender.call.gas(4369).value(store[msg.sender])()) {
         store[msg.sender] = 0x0;
      }
}


L3 (D8193): Potential reetrant vulnerability found.

LOC: 5
Hash: 0xC0E317FB
function addToBalance() {
      store[msg.sender] = store[msg.sender] + msg.value;
      return;
}


LOC: 4
Hash: 0xF8B2CB4F
function getBalance(address) {
      return store[arg_4];
}


LOC: 3
```

</details>

## Develop

### OSX

`cd porosity/porosity/`

`make`

*Note*: you may need to install [boost c++](http://www.boost.org/) dependency.

Using HomeBrew:
`brew install boost`

Using MacPorts:
`sudo port install boost`
