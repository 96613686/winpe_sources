# __imp_load_EfsDllUsePinForEncryptedFilesSrv

- ea: `0x1800025bb`
- end: `0x1800025c7`
- name: `__imp_load_EfsDllUsePinForEncryptedFilesSrv`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllUsePinForEncryptedFilesSrv` at `0x1800025bb`

## pseudocode

```c
__int64 __fastcall load_EfsDllUsePinForEncryptedFilesSrv(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_efscore_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800025bb  lea     rax, __imp_EfsDllUsePinForEncryptedFilesSrv
0x1800025c2  jmp     __tailMerge_efscore_dll
```
