# __imp_load_EfsDllDuplicateEncryptionInfoFileSrv

- ea: `0x1800026db`
- end: `0x1800026e7`
- name: `__imp_load_EfsDllDuplicateEncryptionInfoFileSrv`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllDuplicateEncryptionInfoFileSrv` at `0x1800026db`

## pseudocode

```c
__int64 __fastcall load_EfsDllDuplicateEncryptionInfoFileSrv(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_efscore_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800026db  lea     rax, __imp_EfsDllDuplicateEncryptionInfoFileSrv
0x1800026e2  jmp     __tailMerge_efscore_dll
```
