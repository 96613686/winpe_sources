# CoCreateInstanceElevated(HWND__ *,_GUID const &,ushort const *,_GUID const &,void * *)

- ea: `0x18001077c`
- end: `0x18001087b`
- name: `?CoCreateInstanceElevated@@YAJPEAUHWND__@@AEBU_GUID@@PEBG1PEAPEAX@Z`
- size: `255`
- prototype: `HRESULT __fastcall(HWND, const struct _GUID *, const unsigned __int16 *, const struct _GUID *, void **ppv)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011bc0`

## callees

- `0x18001077c`
- `0x180010e64`
- `0x18002f3b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800107dc`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800107dc`
- `ole32!CoGetObject` at `0x180010851`
- `ole32!CoGetObject` at `0x180010851`

## pseudocode

```c

```
