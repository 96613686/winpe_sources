# PAC_EncodeCredentialData(_SECPKG_SUPPLEMENTAL_CRED_ARRAY *,uchar * *,ulong *)

- ea: `0x180033540`
- end: `0x1800336bb`
- name: `?PAC_EncodeCredentialData@@YAJPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@PEAPEAEPEAK@Z`
- size: `379`
- prototype: `__int64 __fastcall(struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *, unsigned __int8 **, unsigned int *)`
- caller_count: `7`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180032fd0`
- `0x18005b210`
- `0x1800b84b8`
- `0x1800b8ef4`
- `0x1800b9360`
- `0x1800bf6f4`
- `0x1800ca0d0`

## callees

- `0x1800069a0`
- `0x1800093f0`
- `0x180033540`

## import_xrefs

- `RPCRT4!MesIncrementalHandleReset` at `0x180033617`
- `RPCRT4!MesIncrementalHandleReset` at `0x180033617`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x1800335cd`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x1800335cd`
- `RPCRT4!NdrMesTypeEncode3` at `0x18003365c`
- `RPCRT4!NdrMesTypeEncode3` at `0x18003365c`
- `RPCRT4!MesEncodeIncrementalHandleCreate` at `0x18003358a`
- `RPCRT4!MesEncodeIncrementalHandleCreate` at `0x18003358a`
- `RPCRT4!MesHandleFree` at `0x18003369d`
- `RPCRT4!MesHandleFree` at `0x18003369d`
- `RPCRT4!I_RpcMapWin32Status` at `0x180033623`
- `RPCRT4!I_RpcMapWin32Status` at `0x180033623`

## pseudocode

```c

```
