# __imp_load_RpcImpersonateClient

- ea: `0x18000290f`
- end: `0x18000291b`
- name: `__imp_load_RpcImpersonateClient`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180002824`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18000290f`

## pseudocode

```c
__int64 load_RpcImpersonateClient()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x18000290f  lea     rax, __imp_RpcImpersonateClient
0x180002916  jmp     __tailMerge_rpcrt4_dll
```
