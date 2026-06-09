# LsapIsCredentialGuardAllowedToRun(void *)

- ea: `0x1800df734`
- end: `0x1800df9bb`
- name: `?LsapIsCredentialGuardAllowedToRun@@YAEPEAX@Z`
- size: `647`
- prototype: `unsigned __int8 __fastcall(HANDLE EventHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800ec388`

## callees

- `0x180011278`
- `0x1800293c0`
- `0x1800475b0`
- `0x1800df734`
- `0x1800e0334`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800df984`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800df99a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800df984`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800df99a`
- `ntdll!NtSetEvent` at `0x1800df93c`
- `ntdll!NtSetEvent` at `0x1800df93c`
- `RPCRT4!RpcExceptionFilter` at `0x18014b05b`
- `RPCRT4!RpcExceptionFilter` at `0x18014b05b`
- `RPCRT4!NdrClientCall3` at `0x1800df8d3`
- `RPCRT4!NdrClientCall3` at `0x1800df8d3`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800df7ee`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800df7ee`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800df846`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800df846`
- `RPCRT4!RpcStringFreeW` at `0x1800df96e`
- `RPCRT4!RpcStringFreeW` at `0x1800df96e`
- `RPCRT4!RpcBindingFree` at `0x1800df955`
- `RPCRT4!RpcBindingFree` at `0x1800df955`

## pseudocode

```c

```
