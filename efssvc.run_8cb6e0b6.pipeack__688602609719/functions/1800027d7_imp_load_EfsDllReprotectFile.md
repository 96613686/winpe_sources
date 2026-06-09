# __imp_load_EfsDllReprotectFile

- ea: `0x1800027d7`
- end: `0x1800027e3`
- name: `__imp_load_EfsDllReprotectFile`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllReprotectFile` at `0x1800027d7`

## pseudocode

```c
__int64 load_EfsDllReprotectFile()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x1800027d7  lea     rax, __imp_EfsDllReprotectFile
0x1800027de  jmp     __tailMerge_efscore_dll
```
