# __imp_load_EfsDllGetLogFile

- ea: `0x1800027c5`
- end: `0x1800027d1`
- name: `__imp_load_EfsDllGetLogFile`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllGetLogFile` at `0x1800027c5`

## pseudocode

```c
__int64 load_EfsDllGetLogFile()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x1800027c5  lea     rax, __imp_EfsDllGetLogFile
0x1800027cc  jmp     __tailMerge_efscore_dll
```
