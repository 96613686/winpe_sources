# __imp_load_EfsDllWriteEncryptedFileWithHeader

- ea: `0x1800024c5`
- end: `0x1800024d1`
- name: `__imp_load_EfsDllWriteEncryptedFileWithHeader`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EfsDllWriteEncryptedFileWithHeader` at `0x1800024c5`

## pseudocode

```c
__int64 load_EfsDllWriteEncryptedFileWithHeader()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x1800024c5  lea     rax, __imp_EfsDllWriteEncryptedFileWithHeader
0x1800024cc  jmp     __tailMerge_efscore_dll
```
