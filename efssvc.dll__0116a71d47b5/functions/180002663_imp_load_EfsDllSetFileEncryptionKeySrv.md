# __imp_load_EfsDllSetFileEncryptionKeySrv

- ea: `0x180002663`
- end: `0x18000266f`
- name: `__imp_load_EfsDllSetFileEncryptionKeySrv`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EfsDllSetFileEncryptionKeySrv` at `0x180002663`

## pseudocode

```c
__int64 load_EfsDllSetFileEncryptionKeySrv()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002663  lea     rax, __imp_EfsDllSetFileEncryptionKeySrv
0x18000266a  jmp     __tailMerge_efscore_dll
```
