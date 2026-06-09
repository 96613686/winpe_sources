# __imp_load_JetCreateTableColumnIndex2W

- ea: `0x180002c5e`
- end: `0x180002c6a`
- name: `__imp_load_JetCreateTableColumnIndex2W`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002abf`

## import_xrefs

- `ESENT!JetCreateTableColumnIndex2W` at `0x180002c5e`

## pseudocode

```c
__int64 load_JetCreateTableColumnIndex2W()
{
  return _tailMerge_esent_dll();
}

```

## disassembly

```asm
0x180002c5e  lea     rax, __imp_JetCreateTableColumnIndex2W
0x180002c65  jmp     __tailMerge_esent_dll
```
