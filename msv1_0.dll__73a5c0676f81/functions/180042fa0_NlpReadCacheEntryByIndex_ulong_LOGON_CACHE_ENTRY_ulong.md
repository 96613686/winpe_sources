# NlpReadCacheEntryByIndex(ulong,_LOGON_CACHE_ENTRY * *,ulong *)

- ea: `0x180042fa0`
- end: `0x18004311c`
- name: `?NlpReadCacheEntryByIndex@@YAJKPEAPEAU_LOGON_CACHE_ENTRY@@PEAK@Z`
- size: `380`
- prototype: `__int64 __fastcall(unsigned int, struct _LOGON_CACHE_ENTRY **, unsigned int *)`
- caller_count: `5`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180040cf8`
- `0x180040fec`
- `0x180042424`
- `0x180042ccc`
- `0x180042dac`

## callees

- `0x18002fb50`
- `0x180042740`
- `0x180042fa0`
- `0x18006bd74`
- `0x18006d010`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x180043026`
- `ntdll!NtQueryValueKey` at `0x18004308d`
- `ntdll!NtQueryValueKey` at `0x180043026`
- `ntdll!NtQueryValueKey` at `0x18004308d`

## pseudocode

```c

```
