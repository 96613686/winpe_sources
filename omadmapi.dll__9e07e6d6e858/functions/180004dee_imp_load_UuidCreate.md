# __imp_load_UuidCreate

- ea: `0x180004dee`
- end: `0x180004dfa`
- name: `__imp_load_UuidCreate`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800041da`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180004dee`

## pseudocode

```c
__int64 load_UuidCreate()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x180004dee  lea     rax, __imp_UuidCreate
0x180004df5  jmp     __tailMerge_rpcrt4_dll
```
