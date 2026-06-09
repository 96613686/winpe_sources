# __imp_load_EfsDllSetFileEncryptionKeySrv

- ea: `0x180002693`
- end: `0x18000269f`
- name: `__imp_load_EfsDllSetFileEncryptionKeySrv`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllSetFileEncryptionKeySrv` at `0x180002693`

## pseudocode

```c
__int64 __fastcall load_EfsDllSetFileEncryptionKeySrv(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_efscore_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002693  lea     rax, __imp_EfsDllSetFileEncryptionKeySrv
0x18000269a  jmp     __tailMerge_efscore_dll
```
