# InsertMasterKeyCache(void *,_LUID *,ushort const *,_GUID *,uchar *,ulong)

- ea: `0x18000f910`
- end: `0x18000fbae`
- name: `?InsertMasterKeyCache@@YAHPEAXPEAU_LUID@@PEBGPEAU_GUID@@PEAEK@Z`
- size: `670`
- prototype: `__int64 __fastcall(void *, struct _LUID *, const unsigned __int16 *, struct _GUID *, unsigned __int8 *Src, unsigned int Size)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800180cc`
- `0x180018a20`
- `0x1800193c0`
- `0x18002e310`

## callees

- `0x18000bea0`
- `0x18000f910`
- `0x18000fbb4`
- `0x18003c62c`
- `0x18003e010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f9fe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f9fe`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000f9be`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000fa6e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000f9be`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000fa6e`
- `ntdll!RtlEnterCriticalSection` at `0x18000f96a`
- `ntdll!RtlEnterCriticalSection` at `0x18000f96a`
- `ntdll!RtlLeaveCriticalSection` at `0x18000faab`
- `ntdll!RtlLeaveCriticalSection` at `0x18000faab`

## pseudocode

```c

```
