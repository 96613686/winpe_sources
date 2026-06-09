# __imp_load_EfsDllWriteEncryptedFileWithHeader

- ea: `0x1800024f5`
- end: `0x180002501`
- name: `__imp_load_EfsDllWriteEncryptedFileWithHeader`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllWriteEncryptedFileWithHeader` at `0x1800024f5`

## pseudocode

```c
__int64 load_EfsDllWriteEncryptedFileWithHeader()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x1800024f5  lea     rax, __imp_EfsDllWriteEncryptedFileWithHeader
0x1800024fc  jmp     __tailMerge_efscore_dll
```
