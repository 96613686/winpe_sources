# NhAcceptStreamSocket(_COMPONENT_REFERENCE *,_NH_RCSOCKET *,_NH_RCSOCKET *,_NH_BUFFER *,void (*)(ulong,ulong,_NH_BUFFER *),void *,void *)

- ea: `0x180055870`
- end: `0x180055cff`
- name: `?NhAcceptStreamSocket@@YAKPEAU_COMPONENT_REFERENCE@@PEAU_NH_RCSOCKET@@1PEAU_NH_BUFFER@@P6AXKK2@ZPEAX4@Z`
- size: `1167`
- prototype: `unsigned int __usercall@<eax>(struct _COMPONENT_REFERENCE *@<rcx>, struct _NH_RCSOCKET *@<rdx>, struct _NH_RCSOCKET *@<r8>, struct _NH_BUFFER *@<r9>, void (*)(unsigned int, unsigned int, struct _NH_BUFFER *), void *, void *)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x18000b480`
- `0x18000b900`
- `0x18000bad0`
- `0x18000c110`
- `0x18000c750`
- `0x180010640`
- `0x180020cd0`
- `0x1800312e0`
- `0x18004e0c0`
- `0x18004ed64`
- `0x180055870`
- `0x180055fc0`
- `0x180056900`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005594b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005594b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180055961`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180055961`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180055c19`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180055c19`
- `MSWSOCK!AcceptEx` at `0x180055bf2`
- `MSWSOCK!AcceptEx` at `0x180055bf2`
- `WS2_32!__imp_WSAGetLastError` at `0x180055c75`
- `WS2_32!__imp_WSAGetLastError` at `0x180055c75`

## pseudocode

```c

```
