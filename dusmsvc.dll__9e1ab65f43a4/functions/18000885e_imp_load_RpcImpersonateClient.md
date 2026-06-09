# __imp_load_RpcImpersonateClient

- ea: `0x18000885e`
- end: `0x18000886a`
- name: `__imp_load_RpcImpersonateClient`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800087cd`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18000885e`

## pseudocode

```c
__int64 load_RpcImpersonateClient()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x18000885e  lea     rax, __imp_RpcImpersonateClient
0x180008865  jmp     __tailMerge_rpcrt4_dll
```
