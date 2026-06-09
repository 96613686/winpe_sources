# NhAcceptStreamSocket(_COMPONENT_REFERENCE *,_NH_RCSOCKET *,_NH_RCSOCKET *,_NH_BUFFER *,void (*)(ulong,ulong,_NH_BUFFER *),void *,void *)

- ea: `0x180059b60`
- end: `0x18005a012`
- name: `?NhAcceptStreamSocket@@YAKPEAU_COMPONENT_REFERENCE@@PEAU_NH_RCSOCKET@@1PEAU_NH_BUFFER@@P6AXKK2@ZPEAX4@Z`
- size: `1202`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *, struct _NH_RCSOCKET *, struct _NH_RCSOCKET *, struct _NH_BUFFER *, void (*)(unsigned int, unsigned int, struct _NH_BUFFER *), void *, void *)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x18000bd10`
- `0x18000c1e0`
- `0x18000c3c0`
- `0x18000ca20`
- `0x18000d090`
- `0x180011310`
- `0x18002d050`
- `0x180033910`
- `0x180051f30`
- `0x180052bf4`
- `0x180059b60`
- `0x18005a310`
- `0x18005acd0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180059c3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180059c3b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180059c57`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180059c57`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180059f1f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180059f1f`
- `MSWSOCK!AcceptEx` at `0x180059eee`
- `MSWSOCK!AcceptEx` at `0x180059eee`
- `WS2_32!__imp_WSAGetLastError` at `0x180059f82`
- `WS2_32!__imp_WSAGetLastError` at `0x180059f82`

## pseudocode

```c

```
