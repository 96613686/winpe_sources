# __imp_load_I_RpcBindingIsServerLocal

- ea: `0x1800028b5`
- end: `0x1800028c1`
- name: `__imp_load_I_RpcBindingIsServerLocal`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002824`

## import_xrefs

- `RPCRT4!I_RpcBindingIsServerLocal` at `0x1800028b5`

## pseudocode

```c
__int64 __fastcall load_I_RpcBindingIsServerLocal(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_rpcrt4_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800028b5  lea     rax, __imp_I_RpcBindingIsServerLocal
0x1800028bc  jmp     __tailMerge_rpcrt4_dll
```
