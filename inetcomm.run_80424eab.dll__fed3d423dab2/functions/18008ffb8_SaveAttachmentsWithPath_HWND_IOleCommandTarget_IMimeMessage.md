# SaveAttachmentsWithPath(HWND__ *,IOleCommandTarget *,IMimeMessage *)

- ea: `0x18008ffb8`
- end: `0x180090183`
- name: `?SaveAttachmentsWithPath@@YAJPEAUHWND__@@PEAUIOleCommandTarget@@PEAUIMimeMessage@@@Z`
- size: `459`
- prototype: `__int64 __fastcall(HWND hWndParent, struct IOleCommandTarget *, struct IMimeMessage *)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180023d04`
- `0x180064a10`
- `0x18009034c`

## callees

- `0x1800055bc`
- `0x18008ffb8`
- `0x1800cbe40`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800900fd`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800900fd`
- `OLEAUT32!__imp_SysFreeString` at `0x180090075`
- `OLEAUT32!__imp_SysFreeString` at `0x180090153`
- `OLEAUT32!__imp_SysFreeString` at `0x180090075`
- `OLEAUT32!__imp_SysFreeString` at `0x180090153`
- `OLEAUT32!__imp_VariantInit` at `0x180090000`
- `OLEAUT32!__imp_VariantInit` at `0x180090000`

## pseudocode

```c

```
