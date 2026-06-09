# CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)

- ea: `0x18003a654`
- end: `0x18003a743`
- name: `?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z`
- size: `239`
- prototype: `int(HWND, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003a74c`

## callees

- `0x1800104c4`
- `0x18003a654`
- `0x18004c670`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003a6b0`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003a6b0`
- `ole32!CoGetObject` at `0x18003a719`
- `ole32!CoGetObject` at `0x18003a719`

## pseudocode

```c

```
