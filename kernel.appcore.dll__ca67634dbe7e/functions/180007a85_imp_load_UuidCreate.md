# __imp_load_UuidCreate

- ea: `0x180007a85`
- end: `0x180007a91`
- name: `__imp_load_UuidCreate`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800079d0`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180007a85`

## pseudocode

```c
__int64 load_UuidCreate()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x180007a85  lea     rax, __imp_UuidCreate
0x180007a8c  jmp     __tailMerge_rpcrt4_dll
```
