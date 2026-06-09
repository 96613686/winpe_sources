# __imp_load_EfsDllMarkFileForDelete

- ea: `0x180002477`
- end: `0x180002483`
- name: `__imp_load_EfsDllMarkFileForDelete`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllMarkFileForDelete` at `0x180002477`

## pseudocode

```c
__int64 load_EfsDllMarkFileForDelete()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002477  lea     rax, __imp_EfsDllMarkFileForDelete
0x18000247e  jmp     __tailMerge_efscore_dll
```
