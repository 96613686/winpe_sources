# HcsClient::ClientProcess::GetInfo(_GUID const &,std::shared_ptr<ClientOperation> const &)

- ea: `0x18002c93c`
- end: `0x18002cb2f`
- name: `?GetInfo@ClientProcess@HcsClient@@QEAAXAEBU_GUID@@AEBV?$shared_ptr@VClientOperation@@@std@@@Z`
- size: `499`
- prototype: `__int64 __fastcall(HcsClient::ClientProcess *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016aa0`

## callees

- `0x1800067c0`
- `0x180006c3c`
- `0x180006d80`
- `0x18000b948`
- `0x18001587c`
- `0x18002af88`
- `0x18002c41c`
- `0x18002c93c`
- `0x18002cd14`
- `0x180049604`
- `0x180049b6c`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002cadb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002cadb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002caaf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002caaf`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18002cad2`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18002cad2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ca87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ca87`

## string_xrefs

- `0x18002cb1d`: `onecore\vm\compute\dll\lib\core\clientprocess.cpp`
- `0x18002cb08`: `onecore\vm\compute\shared\rundownreference\rundownreference.cpp`

## pseudocode

```c

```
