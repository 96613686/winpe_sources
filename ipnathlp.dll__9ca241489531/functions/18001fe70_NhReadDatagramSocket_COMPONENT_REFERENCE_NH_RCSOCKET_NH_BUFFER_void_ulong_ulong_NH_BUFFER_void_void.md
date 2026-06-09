# NhReadDatagramSocket(_COMPONENT_REFERENCE *,_NH_RCSOCKET *,_NH_BUFFER *,void (*)(ulong,ulong,_NH_BUFFER *),void *,void *)

- ea: `0x18001fe70`
- end: `0x180020209`
- name: `?NhReadDatagramSocket@@YAKPEAU_COMPONENT_REFERENCE@@PEAU_NH_RCSOCKET@@PEAU_NH_BUFFER@@P6AXKK2@ZPEAX4@Z`
- size: `921`
- prototype: `unsigned int __usercall@<eax>(struct _COMPONENT_REFERENCE *@<rcx>, struct _NH_RCSOCKET *@<rdx>, struct _NH_BUFFER *@<r8>, void (*)(unsigned int, unsigned int, struct _NH_BUFFER *)@<r9>, void *, void *)`
- caller_count: `17`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000ad20`
- `0x18001f180`
- `0x18001f6c0`
- `0x18001fac0`
- `0x180020210`
- `0x180025dd8`
- `0x18002a53c`
- `0x180035220`
- `0x180035874`
- `0x180044020`
- `0x180048ef4`
- `0x180058a10`
- `0x180062c20`
- `0x180064760`
- `0x18007dc48`
- `0x18007dea4`
- `0x180084dc0`

## callees

- `0x18000b480`
- `0x18000b900`
- `0x18000bad0`
- `0x18000c110`
- `0x18000c750`
- `0x18001fe70`
- `0x180020cd0`
- `0x18004ed64`
- `0x180056958`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ff3a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ff3a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ff4e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ff4e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180020152`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180020152`
- `WS2_32!WSARecvFrom` at `0x18002011a`
- `WS2_32!WSARecvFrom` at `0x18002011a`
- `WS2_32!__imp_WSAGetLastError` at `0x180020127`
- `WS2_32!__imp_WSAGetLastError` at `0x180020127`

## pseudocode

```c

```
