# __imp_load_EfsDllConstructEFS

- ea: `0x1800029a1`
- end: `0x1800029ad`
- name: `__imp_load_EfsDllConstructEFS`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllConstructEFS` at `0x1800029a1`

## pseudocode

```c
__int64 load_EfsDllConstructEFS()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x1800029a1  lea     rax, __imp_EfsDllConstructEFS
0x1800029a8  jmp     __tailMerge_efscore_dll
```
