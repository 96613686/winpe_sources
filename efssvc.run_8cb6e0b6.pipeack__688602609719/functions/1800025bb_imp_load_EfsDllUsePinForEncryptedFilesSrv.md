# __imp_load_EfsDllUsePinForEncryptedFilesSrv

- ea: `0x1800025bb`
- end: `0x1800025c7`
- name: `__imp_load_EfsDllUsePinForEncryptedFilesSrv`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllUsePinForEncryptedFilesSrv` at `0x1800025bb`

## pseudocode

```c
__int64 load_EfsDllUsePinForEncryptedFilesSrv()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x1800025bb  lea     rax, __imp_EfsDllUsePinForEncryptedFilesSrv
0x1800025c2  jmp     __tailMerge_efscore_dll
```
