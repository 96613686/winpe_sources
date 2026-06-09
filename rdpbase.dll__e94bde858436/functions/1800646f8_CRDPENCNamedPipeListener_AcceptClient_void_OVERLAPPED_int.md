# CRDPENCNamedPipeListener::AcceptClient(void *,_OVERLAPPED *,int *)

- ea: `0x1800646f8`
- end: `0x1800648dc`
- name: `?AcceptClient@CRDPENCNamedPipeListener@@IEAAJPEAXPEAU_OVERLAPPED@@PEAH@Z`
- size: `484`
- prototype: `int(CRDPENCNamedPipeListener *__hidden this, void *, struct _OVERLAPPED *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800652a0`

## callees

- `0x1800018a4`
- `0x1800646f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006472d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800647a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064850`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006472d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800647a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064850`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180064846`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180064846`
- `api-ms-win-core-namedpipe-l1-1-0!ConnectNamedPipe` at `0x180064723`
- `api-ms-win-core-namedpipe-l1-1-0!ConnectNamedPipe` at `0x180064723`

## string_xrefs

- `0x1800647ec`: `Client already connected`

## pseudocode

```c

```
