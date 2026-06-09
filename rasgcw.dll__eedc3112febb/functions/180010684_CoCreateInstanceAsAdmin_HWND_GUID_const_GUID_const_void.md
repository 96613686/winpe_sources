# CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)

- ea: `0x180010684`
- end: `0x180010773`
- name: `?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z`
- size: `239`
- prototype: `HRESULT __fastcall(HWND, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011bc0`

## callees

- `0x180010684`
- `0x180010e64`
- `0x18002f3b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800106e0`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800106e0`
- `ole32!CoGetObject` at `0x180010749`
- `ole32!CoGetObject` at `0x180010749`

## pseudocode

```c

```
