# __imp_load_RpcImpersonateClient

- ea: `0x1800023d8`
- end: `0x1800023e4`
- name: `__imp_load_RpcImpersonateClient`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180002359`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x1800023d8`

## pseudocode

```c
__int64 load_RpcImpersonateClient()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x1800023d8  lea     rax, __imp_RpcImpersonateClient
0x1800023df  jmp     __tailMerge_rpcrt4_dll
```
