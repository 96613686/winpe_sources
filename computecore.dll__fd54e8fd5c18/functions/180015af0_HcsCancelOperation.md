# HcsCancelOperation

- ea: `0x180015af0`
- end: `0x180015d8d`
- name: `HcsCancelOperation`
- size: `669`
- prototype: `HRESULT __stdcall(HCS_OPERATION operation)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800067c0`
- `0x180007438`
- `0x18000f1b4`
- `0x180013de8`
- `0x1800144a4`
- `0x180014f14`
- `0x180015150`
- `0x18001587c`
- `0x180015af0`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180015baa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180015baa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180015cd5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180015cd5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015c55`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015c55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015c42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015c42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015c4d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015ce5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015c4d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015ce5`

## string_xrefs

- `0x180015d7a`: `onecore\vm\compute\dll\core\src\operation.cpp`
- `0x180015bc3`: `onecore\vm\compute\dll\lib\core\clientoperation.cpp`

## pseudocode

```c

```
