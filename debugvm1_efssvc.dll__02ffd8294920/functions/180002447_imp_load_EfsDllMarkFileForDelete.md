# __imp_load_EfsDllMarkFileForDelete

- ea: `0x180002447`
- end: `0x180002453`
- name: `__imp_load_EfsDllMarkFileForDelete`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EfsDllMarkFileForDelete` at `0x180002447`

## pseudocode

```c
__int64 load_EfsDllMarkFileForDelete()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002447  lea     rax, __imp_EfsDllMarkFileForDelete
0x18000244e  jmp     __tailMerge_efscore_dll
```
