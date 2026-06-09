# NhReadDatagramSocket(_COMPONENT_REFERENCE *,_NH_RCSOCKET *,_NH_BUFFER *,void (*)(ulong,ulong,_NH_BUFFER *),void *,void *)

- ea: `0x18002c140`
- end: `0x18002c4fc`
- name: `?NhReadDatagramSocket@@YAKPEAU_COMPONENT_REFERENCE@@PEAU_NH_RCSOCKET@@PEAU_NH_BUFFER@@P6AXKK2@ZPEAX4@Z`
- size: `956`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *, struct _NH_RCSOCKET *, struct _NH_BUFFER *, void (*)(unsigned int, unsigned int, struct _NH_BUFFER *), void *, void *)`
- caller_count: `17`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000b500`
- `0x180028268`
- `0x18002b3f0`
- `0x18002b960`
- `0x18002bd70`
- `0x18002c510`
- `0x18002eb94`
- `0x180037ce0`
- `0x1800383d0`
- `0x180047a30`
- `0x18004cb30`
- `0x18005cfd0`
- `0x1800678e0`
- `0x180069640`
- `0x180084088`
- `0x1800842fc`
- `0x18008b720`

## callees

- `0x18000bd10`
- `0x18000c1e0`
- `0x18000c3c0`
- `0x18000ca20`
- `0x18000d090`
- `0x18002c140`
- `0x18002d050`
- `0x180052bf4`
- `0x18005ad2c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c20a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c20a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c224`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c224`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002c43e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002c43e`
- `WS2_32!WSARecvFrom` at `0x18002c3f6`
- `WS2_32!WSARecvFrom` at `0x18002c3f6`
- `WS2_32!__imp_WSAGetLastError` at `0x18002c40d`
- `WS2_32!__imp_WSAGetLastError` at `0x18002c40d`

## pseudocode

```c

```
