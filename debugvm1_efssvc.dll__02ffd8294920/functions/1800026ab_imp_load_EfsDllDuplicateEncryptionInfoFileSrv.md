# __imp_load_EfsDllDuplicateEncryptionInfoFileSrv

- ea: `0x1800026ab`
- end: `0x1800026b7`
- name: `__imp_load_EfsDllDuplicateEncryptionInfoFileSrv`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EfsDllDuplicateEncryptionInfoFileSrv` at `0x1800026ab`

## pseudocode

```c
__int64 load_EfsDllDuplicateEncryptionInfoFileSrv()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x1800026ab  lea     rax, __imp_EfsDllDuplicateEncryptionInfoFileSrv
0x1800026b2  jmp     __tailMerge_efscore_dll
```
