# __imp_load_RpcBindingToStringBindingW

- ea: `0x1800028c7`
- end: `0x1800028d3`
- name: `__imp_load_RpcBindingToStringBindingW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002824`

## import_xrefs

- `RPCRT4!RpcBindingToStringBindingW` at `0x1800028c7`

## pseudocode

```c
__int64 __fastcall load_RpcBindingToStringBindingW(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_rpcrt4_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800028c7  lea     rax, __imp_RpcBindingToStringBindingW
0x1800028ce  jmp     __tailMerge_rpcrt4_dll
```
