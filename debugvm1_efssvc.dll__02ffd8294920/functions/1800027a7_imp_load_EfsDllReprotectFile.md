# __imp_load_EfsDllReprotectFile

- ea: `0x1800027a7`
- end: `0x1800027b3`
- name: `__imp_load_EfsDllReprotectFile`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EfsDllReprotectFile` at `0x1800027a7`

## pseudocode

```c
__int64 load_EfsDllReprotectFile()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x1800027a7  lea     rax, __imp_EfsDllReprotectFile
0x1800027ae  jmp     __tailMerge_efscore_dll
```
