# SaveKeyBlobForUser(ushort const *,ushort const *,_GUID *,_AP_BLOB *,void *)

- ea: `0x18005dfa0`
- end: `0x18005e0db`
- name: `?SaveKeyBlobForUser@@YAJPEBG0PEAU_GUID@@PEAU_AP_BLOB@@PEAX@Z`
- size: `315`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, UUID *Uuid, LPCVOID *, void *)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x18002b6dc`
- `0x1800545f0`
- `0x1800554d8`
- `0x1800597ac`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x180031f6c`
- `0x18005dfa0`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x18005e0c3`
- `RPCRT4!RpcStringFreeW` at `0x18005e0c3`
- `RPCRT4!UuidToStringW` at `0x18005dfc8`
- `RPCRT4!UuidToStringW` at `0x18005dfc8`

## string_xrefs

- `0x18005dfd5`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005e015`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005e076`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005e091`: `WriteFileData`

## pseudocode

```c

```
