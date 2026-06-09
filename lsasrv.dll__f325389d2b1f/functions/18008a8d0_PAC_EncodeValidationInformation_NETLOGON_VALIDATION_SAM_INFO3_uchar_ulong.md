# PAC_EncodeValidationInformation(_NETLOGON_VALIDATION_SAM_INFO3 *,uchar * *,ulong *)

- ea: `0x18008a8d0`
- end: `0x18008aa86`
- name: `?PAC_EncodeValidationInformation@@YAJPEAU_NETLOGON_VALIDATION_SAM_INFO3@@PEAPEAEPEAK@Z`
- size: `438`
- prototype: `__int64 __fastcall(struct _NETLOGON_VALIDATION_SAM_INFO3 *, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800b4b50`
- `0x18013b5b4`

## callees

- `0x18008a8d0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008aa52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008aa52`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008a983`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008a983`
- `RPCRT4!I_RpcMapWin32Status` at `0x18008a9d5`
- `RPCRT4!I_RpcMapWin32Status` at `0x18008a9d5`
- `RPCRT4!NdrMesTypeEncode3` at `0x18008aa17`
- `RPCRT4!NdrMesTypeEncode3` at `0x18008aa17`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x18008a969`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x18008a969`
- `RPCRT4!MesIncrementalHandleReset` at `0x18008a9c3`
- `RPCRT4!MesIncrementalHandleReset` at `0x18008a9c3`
- `RPCRT4!MesHandleFree` at `0x18008aa6b`
- `RPCRT4!MesHandleFree` at `0x18008aa6b`
- `RPCRT4!MesEncodeIncrementalHandleCreate` at `0x18008a91d`
- `RPCRT4!MesEncodeIncrementalHandleCreate` at `0x18008a91d`

## pseudocode

```c

```
