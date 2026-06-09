# GetKeyBlobForUserInt(ushort const *,ushort const *,_GUID *,_AP_BLOB *,_FILETIME *)

- ea: `0x18002b9a4`
- end: `0x18002bb2e`
- name: `?GetKeyBlobForUserInt@@YAJPEBG0PEAU_GUID@@PEAU_AP_BLOB@@PEAU_FILETIME@@@Z`
- size: `394`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, UUID *Uuid, struct _AP_BLOB *, struct _FILETIME *lpLastWriteTime)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18002b6dc`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18002b9a4`
- `0x18002bb40`
- `0x180081010`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x18002bb1d`
- `RPCRT4!RpcStringFreeW` at `0x18002bb1d`
- `RPCRT4!UuidToStringW` at `0x18002b9e6`
- `RPCRT4!UuidToStringW` at `0x18002b9e6`

## string_xrefs

- `0x18002b9f3`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18002ba33`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18002baa6`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18002babc`: `ReadFileData`

## pseudocode

```c

```
