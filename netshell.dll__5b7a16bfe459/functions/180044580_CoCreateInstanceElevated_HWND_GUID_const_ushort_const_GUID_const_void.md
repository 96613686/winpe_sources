# CoCreateInstanceElevated(HWND__ *,_GUID const &,ushort const *,_GUID const &,void * *)

- ea: `0x180044580`
- end: `0x180044678`
- name: `?CoCreateInstanceElevated@@YAJPEAUHWND__@@AEBU_GUID@@PEBG1PEAPEAX@Z`
- size: `248`
- prototype: `HRESULT __fastcall(HWND, const struct _GUID *, const unsigned __int16 *, const struct _GUID *, void **ppv)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180046a74`

## callees

- `0x18001e1e0`
- `0x1800228e8`
- `0x180044580`

## import_xrefs

- `ole32!StringFromGUID2` at `0x1800445df`
- `ole32!StringFromGUID2` at `0x1800445df`
- `ole32!CoGetObject` at `0x180044650`
- `ole32!CoGetObject` at `0x180044650`

## pseudocode

```c

```
