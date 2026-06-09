# CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)

- ea: `0x1800090f4`
- end: `0x1800091e3`
- name: `?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z`
- size: `239`
- prototype: `int(HWND, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000e564`

## callees

- `0x180002270`
- `0x1800090f4`
- `0x180012458`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180009150`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180009150`
- `ole32!CoGetObject` at `0x1800091b9`
- `ole32!CoGetObject` at `0x1800091b9`

## pseudocode

```c

```
