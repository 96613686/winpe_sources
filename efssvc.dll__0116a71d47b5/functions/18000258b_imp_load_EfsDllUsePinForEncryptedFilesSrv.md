# __imp_load_EfsDllUsePinForEncryptedFilesSrv

- ea: `0x18000258b`
- end: `0x180002597`
- name: `__imp_load_EfsDllUsePinForEncryptedFilesSrv`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EfsDllUsePinForEncryptedFilesSrv` at `0x18000258b`

## pseudocode

```c
__int64 load_EfsDllUsePinForEncryptedFilesSrv()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x18000258b  lea     rax, __imp_EfsDllUsePinForEncryptedFilesSrv
0x180002592  jmp     __tailMerge_efscore_dll
```
