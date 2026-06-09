# RpcServerUseProtseqIfExW

- ea: `0x1800a9f90`
- end: `0x1800aa095`
- name: `RpcServerUseProtseqIfExW`
- size: `261`
- prototype: `RPC_STATUS __stdcall(RPC_WSTR Protseq, unsigned int MaxCalls, RPC_IF_HANDLE IfSpec, void *SecurityDescriptor, PRPC_POLICY Policy)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800aa0a0`
- `0x1800b5f50`

## callees

- `0x18002499c`
- `0x18006e400`
- `0x1800a4710`
- `0x1800a9f90`

## import_xrefs

- `ntdll!_wcsnicmp` at `0x1800aa02e`
- `ntdll!_wcsnicmp` at `0x1800aa02e`
- `ntdll!RtlFreeUnicodeString` at `0x1800aa03d`
- `ntdll!RtlFreeUnicodeString` at `0x1800aa06c`
- `ntdll!RtlFreeUnicodeString` at `0x1800aa03d`
- `ntdll!RtlFreeUnicodeString` at `0x1800aa06c`

## pseudocode

```c

```
