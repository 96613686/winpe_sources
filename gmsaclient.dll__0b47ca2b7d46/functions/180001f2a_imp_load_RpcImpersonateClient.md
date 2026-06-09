# __imp_load_RpcImpersonateClient

- ea: `0x180001f2a`
- end: `0x180001f36`
- name: `__imp_load_RpcImpersonateClient`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180001d71`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180001f2a`

## pseudocode

```c
__int64 load_RpcImpersonateClient()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x180001f2a  lea     rax, __imp_RpcImpersonateClient
0x180001f31  jmp     __tailMerge_rpcrt4_dll
```
