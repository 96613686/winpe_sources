# CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)

- ea: `0x18001cd7c`
- end: `0x18001ce5a`
- name: `?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z`
- size: `222`
- prototype: `int(HWND, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001e750`
- `0x180029ba4`

## callees

- `0x180006668`
- `0x18001cd7c`
- `0x180031070`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001cdd4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001cdd4`
- `ole32!CoGetObject` at `0x18001ce39`
- `ole32!CoGetObject` at `0x18001ce39`

## pseudocode

```c

```
