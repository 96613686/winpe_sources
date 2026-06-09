# __imp_load_RpcRevertToSelf

- ea: `0x180002921`
- end: `0x18000292d`
- name: `__imp_load_RpcRevertToSelf`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180002824`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x180002921`

## pseudocode

```c
__int64 __fastcall load_RpcRevertToSelf(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_rpcrt4_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002921  lea     rax, __imp_RpcRevertToSelf
0x180002928  jmp     __tailMerge_rpcrt4_dll
```
