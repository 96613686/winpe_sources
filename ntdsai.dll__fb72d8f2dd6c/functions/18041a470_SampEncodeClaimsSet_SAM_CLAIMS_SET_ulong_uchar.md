# SampEncodeClaimsSet(_SAM_CLAIMS_SET *,ulong *,uchar * *)

- ea: `0x18041a470`
- end: `0x18041a6a4`
- name: `?SampEncodeClaimsSet@@YAJPEAU_SAM_CLAIMS_SET@@PEAKPEAPEAE@Z`
- size: `564`
- prototype: `__int64 __fastcall(struct _SAM_CLAIMS_SET *, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18041a20c`

## callees

- `0x18041a470`

## import_xrefs

- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18041a508`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18041a508`
- `RPCRT4!MesHandleFree` at `0x18041a68f`
- `RPCRT4!MesHandleFree` at `0x18041a68f`
- `RPCRT4!I_RpcExceptionFilter` at `0x1804768af`
- `RPCRT4!I_RpcExceptionFilter` at `0x1804768cb`
- `RPCRT4!I_RpcExceptionFilter` at `0x1804768af`
- `RPCRT4!I_RpcExceptionFilter` at `0x1804768cb`
- `RPCRT4!NdrMesTypeEncode3` at `0x18041a644`
- `RPCRT4!NdrMesTypeEncode3` at `0x18041a644`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x18041a56f`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x18041a56f`
- `RPCRT4!MesBufferHandleReset` at `0x18041a609`
- `RPCRT4!MesBufferHandleReset` at `0x18041a609`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18041a5c4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18041a5c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18041a684`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18041a684`

## pseudocode

```c

```
