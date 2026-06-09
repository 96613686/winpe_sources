# __imp_load_RpcBindingCreateW

- ea: `0x180007a97`
- end: `0x180007aa3`
- name: `__imp_load_RpcBindingCreateW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800079d0`

## import_xrefs

- `RPCRT4!RpcBindingCreateW` at `0x180007a97`

## pseudocode

```c
__int64 load_RpcBindingCreateW()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x180007a97  lea     rax, __imp_RpcBindingCreateW
0x180007a9e  jmp     __tailMerge_rpcrt4_dll
```
