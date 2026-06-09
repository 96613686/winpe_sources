# __imp_load_RpcBindingCreateW

- ea: `0x1800028cf`
- end: `0x1800028db`
- name: `__imp_load_RpcBindingCreateW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000245c`

## import_xrefs

- `RPCRT4!RpcBindingCreateW` at `0x1800028cf`

## pseudocode

```c
__int64 load_RpcBindingCreateW()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x1800028cf  lea     rax, __imp_RpcBindingCreateW
0x1800028d6  jmp     __tailMerge_rpcrt4_dll
```
