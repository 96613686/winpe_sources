# HcsClient::ClientComputeSystem::Shutdown(_GUID const &,std::shared_ptr<ClientOperation> const &,ushort const *)

- ea: `0x180038384`
- end: `0x1800385e5`
- name: `?Shutdown@ClientComputeSystem@HcsClient@@QEAA_NAEBU_GUID@@AEBV?$shared_ptr@VClientOperation@@@std@@PEBG@Z`
- size: `609`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001b950`

## callees

- `0x1800067c0`
- `0x180007438`
- `0x18000b948`
- `0x18001587c`
- `0x18001589c`
- `0x18002af88`
- `0x18002c380`
- `0x180034d98`
- `0x180035344`
- `0x180038384`
- `0x1800392ec`
- `0x180049604`
- `0x180049b6c`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180038591`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180038591`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180038565`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180038565`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180038588`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180038588`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800384c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800384c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800384b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800384b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800384c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038552`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800384c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038552`

## string_xrefs

- `0x1800385d3`: `onecore\vm\compute\dll\lib\core\clientsystem.cpp`
- `0x1800385be`: `onecore\vm\compute\shared\rundownreference\rundownreference.cpp`

## pseudocode

```c

```
