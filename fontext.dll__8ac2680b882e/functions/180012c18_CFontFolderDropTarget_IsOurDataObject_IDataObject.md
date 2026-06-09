# CFontFolderDropTarget::_IsOurDataObject(IDataObject *)

- ea: `0x180012c18`
- end: `0x180012cd2`
- name: `?_IsOurDataObject@CFontFolderDropTarget@@AEAAJPEAUIDataObject@@@Z`
- size: `186`
- prototype: `__int64 __fastcall(CFontFolderDropTarget *__hidden this, struct IDataObject *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800129a0`

## callees

- `0x180012c18`
- `0x180032010`

## import_xrefs

- `KERNEL32!GlobalUnlock` at `0x180012cb5`
- `KERNEL32!GlobalUnlock` at `0x180012cb5`
- `KERNEL32!GlobalLock` at `0x180012c87`
- `KERNEL32!GlobalLock` at `0x180012c87`
- `ole32!ReleaseStgMedium` at `0x180012cbf`
- `ole32!ReleaseStgMedium` at `0x180012cbf`
- `USER32!RegisterClipboardFormatW` at `0x180012c2f`
- `USER32!RegisterClipboardFormatW` at `0x180012c2f`

## string_xrefs

- `0x180012c25`: `Data Source CLSID`

## pseudocode

```c

```
