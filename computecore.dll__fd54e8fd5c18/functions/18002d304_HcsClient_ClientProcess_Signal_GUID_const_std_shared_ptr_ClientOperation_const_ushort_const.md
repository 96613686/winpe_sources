# HcsClient::ClientProcess::Signal(_GUID const &,std::shared_ptr<ClientOperation> const &,ushort const *)

- ea: `0x18002d304`
- end: `0x18002d49f`
- name: `?Signal@ClientProcess@HcsClient@@QEAAXAEBU_GUID@@AEBV?$shared_ptr@VClientOperation@@@std@@PEBG@Z`
- size: `411`
- prototype: `__int64 __fastcall(HcsClient::ClientProcess *this)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180017410`
- `0x1800175c0`

## callees

- `0x1800067c0`
- `0x18000b948`
- `0x18001587c`
- `0x18002af88`
- `0x18002c41c`
- `0x18002cd14`
- `0x18002d304`
- `0x180049604`
- `0x180049b6c`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002d453`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002d453`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002d427`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002d427`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18002d44a`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18002d44a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d414`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d414`

## string_xrefs

- `0x18002d48d`: `onecore\vm\compute\dll\lib\core\clientprocess.cpp`
- `0x18002d478`: `onecore\vm\compute\shared\rundownreference\rundownreference.cpp`

## pseudocode

```c

```
