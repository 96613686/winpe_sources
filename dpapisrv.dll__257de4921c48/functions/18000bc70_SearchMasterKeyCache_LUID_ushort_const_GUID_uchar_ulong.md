# SearchMasterKeyCache(_LUID *,ushort const *,_GUID *,uchar * *,ulong *)

- ea: `0x18000bc70`
- end: `0x18000be98`
- name: `?SearchMasterKeyCache@@YAHPEAU_LUID@@PEBGPEAU_GUID@@PEAPEAEPEAK@Z`
- size: `552`
- prototype: `__int64 __fastcall(struct _LUID *, const unsigned __int16 *, struct _GUID *, unsigned __int8 **, unsigned int *)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000e9c0`
- `0x180018a20`
- `0x1800193c0`
- `0x18002d8f0`

## callees

- `0x18000bc70`
- `0x18000bea0`
- `0x18003c62c`
- `0x18003e010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000bdd2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000bdd2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000bdac`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000bdac`
- `ntdll!RtlEnterCriticalSection` at `0x18000bc92`
- `ntdll!RtlEnterCriticalSection` at `0x18000bc92`
- `ntdll!RtlLeaveCriticalSection` at `0x18000bd02`
- `ntdll!RtlLeaveCriticalSection` at `0x18000bd02`

## pseudocode

```c

```
