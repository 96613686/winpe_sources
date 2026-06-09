# CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)

- ea: `0x1800bd9c0`
- end: `0x1800bdaaf`
- name: `?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z`
- size: `239`
- prototype: `int(HWND, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800bd950`

## callees

- `0x180013870`
- `0x1800bd9c0`
- `0x1800cf080`

## import_xrefs

- `ole32!CoGetObject` at `0x1800bda85`
- `ole32!CoGetObject` at `0x1800bda85`
- `ole32!StringFromGUID2` at `0x1800bda1c`
- `ole32!StringFromGUID2` at `0x1800bda1c`

## pseudocode

```c

```
