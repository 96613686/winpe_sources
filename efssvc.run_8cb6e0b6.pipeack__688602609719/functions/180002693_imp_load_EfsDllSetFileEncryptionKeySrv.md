# __imp_load_EfsDllSetFileEncryptionKeySrv

- ea: `0x180002693`
- end: `0x18000269f`
- name: `__imp_load_EfsDllSetFileEncryptionKeySrv`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllSetFileEncryptionKeySrv` at `0x180002693`

## pseudocode

```c
__int64 load_EfsDllSetFileEncryptionKeySrv()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002693  lea     rax, __imp_EfsDllSetFileEncryptionKeySrv
0x18000269a  jmp     __tailMerge_efscore_dll
```
