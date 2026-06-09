# __imp_load_RpcImpersonateClient

- ea: `0x18001ee6b`
- end: `0x18001ee77`
- name: `__imp_load_RpcImpersonateClient`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18001ed4f`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18001ee6b`

## pseudocode

```c
__int64 load_RpcImpersonateClient()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x18001ee6b  lea     rax, __imp_RpcImpersonateClient
0x18001ee72  jmp     __tailMerge_rpcrt4_dll
```
