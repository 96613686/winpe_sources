# CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)

- ea: `0x18004449c`
- end: `0x18004457a`
- name: `?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z`
- size: `222`
- prototype: `HRESULT __fastcall(HWND, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180018970`
- `0x180019360`
- `0x180044cd0`
- `0x180045340`
- `0x180046100`
- `0x180046a74`
- `0x18005dd40`

## callees

- `0x18001e1e0`
- `0x1800228e8`
- `0x18004449c`

## import_xrefs

- `ole32!StringFromGUID2` at `0x1800444f4`
- `ole32!StringFromGUID2` at `0x1800444f4`
- `ole32!CoGetObject` at `0x180044559`
- `ole32!CoGetObject` at `0x180044559`

## pseudocode

```c

```
