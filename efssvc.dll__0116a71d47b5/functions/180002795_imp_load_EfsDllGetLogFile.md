# __imp_load_EfsDllGetLogFile

- ea: `0x180002795`
- end: `0x1800027a1`
- name: `__imp_load_EfsDllGetLogFile`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EfsDllGetLogFile` at `0x180002795`

## pseudocode

```c
__int64 load_EfsDllGetLogFile()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002795  lea     rax, __imp_EfsDllGetLogFile
0x18000279c  jmp     __tailMerge_efscore_dll
```
