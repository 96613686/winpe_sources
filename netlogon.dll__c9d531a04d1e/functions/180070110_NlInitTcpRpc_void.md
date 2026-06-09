# NlInitTcpRpc(void *)

- ea: `0x180070110`
- end: `0x1800703be`
- name: `?NlInitTcpRpc@@YAXPEAX@Z`
- size: `686`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180007278`
- `0x18000e270`
- `0x18003f648`
- `0x18006eca8`
- `0x180070110`
- `0x1800738d0`
- `0x180082a60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ultoa_s` at `0x18007024c`
- `api-ms-win-crt-private-l1-1-0!_o__ultoa_s` at `0x18007024c`
- `RPCRT4!RpcServerUseProtseqEpExA` at `0x18007026b`
- `RPCRT4!RpcServerUseProtseqEpExA` at `0x18007026b`
- `RPCRT4!RpcServerUseProtseqExW` at `0x18007039e`
- `RPCRT4!RpcServerUseProtseqExW` at `0x18007039e`
- `ntdll!RtlInitString` at `0x1800702be`
- `ntdll!RtlInitString` at `0x1800702be`
- `ntdll!RtlxAnsiStringToUnicodeSize` at `0x1800702c8`
- `ntdll!RtlxAnsiStringToUnicodeSize` at `0x1800702c8`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800702f5`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800702f5`
- `netutils!NetApiBufferFree` at `0x180070349`
- `netutils!NetApiBufferFree` at `0x180070349`
- `netutils!NetApiBufferAllocate` at `0x1800702e0`
- `netutils!NetApiBufferAllocate` at `0x1800702e0`

## string_xrefs

- `0x180070185`: `The value of DcTcpipBacklogLimit is outside the acceptable bounds [%d,%d]. Using default value of %d\n`
- `0x18007035c`: `NlInitTcpRpc thread finished.\n`

## pseudocode

```c

```
