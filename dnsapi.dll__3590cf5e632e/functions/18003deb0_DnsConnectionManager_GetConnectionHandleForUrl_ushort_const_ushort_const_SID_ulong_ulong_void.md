# DnsConnectionManager::GetConnectionHandleForUrl(ushort const *,ushort const *,_SID *,ulong,ulong *,void * *)

- ea: `0x18003deb0`
- end: `0x18003e303`
- name: `?GetConnectionHandleForUrl@DnsConnectionManager@@QEAAJPEBG0PEAU_SID@@KPEAKPEAPEAX@Z`
- size: `1107`
- prototype: `int(DnsConnectionManager *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct _SID *, unsigned int, unsigned int *, void **)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003da6c`
- `0x18006d150`

## callees

- `0x18003deb0`
- `0x18003fcf4`
- `0x18005f8d0`
- `0x180062fe8`
- `0x18008b194`
- `0x18008b5f0`
- `0x1800d6308`
- `0x1800dbfe0`
- `0x1800dc9e0`
- `0x1800dca34`
- `0x1800ddfa8`
- `0x1800de650`
- `0x1800e4010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e1a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e1a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e18c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e23d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e283`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e2bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e18c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e23d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e283`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e2bf`

## pseudocode

```c

```
