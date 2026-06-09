# DsrCmdStringHelper::CreateGuid(_GUID *,ushort * *)

- ea: `0x1800adcdc`
- end: `0x1800adefb`
- name: `?CreateGuid@DsrCmdStringHelper@@SAJPEAU_GUID@@PEAPEAG@Z`
- size: `543`
- prototype: `__int64 __fastcall(struct _GUID *, RPC_WSTR *String)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800a01b4`
- `0x1800adc60`

## callees

- `0x180008530`
- `0x18000f368`
- `0x180012c7c`
- `0x180044300`
- `0x180046ae8`
- `0x180046b3c`
- `0x1800adcdc`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x1800ade52`
- `RPCRT4!RpcStringFreeW` at `0x1800ade52`
- `RPCRT4!UuidToStringW` at `0x1800ade3a`
- `RPCRT4!UuidToStringW` at `0x1800ade3a`

## string_xrefs

- `0x1800add1d`: `DsrCmdStringHelper::CreateGuid`
- `0x1800addb5`: `DsrCmdStringHelper::CreateGuid`
- `0x1800ade60`: `DsrCmdStringHelper::CreateGuid`
- `0x1800addbc`: `%s: Error creating GUID. CreateGuid failed with error code: 0x%08x.\n`

## pseudocode

```c

```
