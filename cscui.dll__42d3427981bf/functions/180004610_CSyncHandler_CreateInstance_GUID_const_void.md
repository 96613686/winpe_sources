# CSyncHandler_CreateInstance(_GUID const &,void * *)

- ea: `0x180004610`
- end: `0x1800047d8`
- name: `?CSyncHandler_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `456`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004610`
- `0x18000c1e8`
- `0x18000c804`
- `0x18001101c`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004723`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004723`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180004787`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180004787`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000469d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000469d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800046bf`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800046bf`

## pseudocode

```c

```
