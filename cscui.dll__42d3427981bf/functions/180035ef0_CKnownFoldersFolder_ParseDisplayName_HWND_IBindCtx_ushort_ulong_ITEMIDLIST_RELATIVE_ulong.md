# CKnownFoldersFolder::ParseDisplayName(HWND__ *,IBindCtx *,ushort *,ulong *,_ITEMIDLIST_RELATIVE * *,ulong *)

- ea: `0x180035ef0`
- end: `0x180035fe8`
- name: `?ParseDisplayName@CKnownFoldersFolder@@UEAAJPEAUHWND__@@PEAUIBindCtx@@PEAGPEAKPEAPEAU_ITEMIDLIST_RELATIVE@@3@Z`
- size: `248`
- prototype: `int(CKnownFoldersFolder *__hidden this, HWND, struct IBindCtx *, unsigned __int16 *, unsigned int *, struct _ITEMIDLIST_RELATIVE **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18003565c`
- `0x180035ef0`
- `0x18004c670`
- `0x18004d010`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x180035fbe`
- `SHELL32!__imp_ILFree` at `0x180035fbe`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180035f52`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180035f52`

## pseudocode

```c

```
