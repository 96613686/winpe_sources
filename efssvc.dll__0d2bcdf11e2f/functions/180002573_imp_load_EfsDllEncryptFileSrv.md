# __imp_load_EfsDllEncryptFileSrv

- ea: `0x180002573`
- end: `0x18000257f`
- name: `__imp_load_EfsDllEncryptFileSrv`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllEncryptFileSrv` at `0x180002573`

## pseudocode

```c
__int64 __fastcall load_EfsDllEncryptFileSrv(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_efscore_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002573  lea     rax, __imp_EfsDllEncryptFileSrv
0x18000257a  jmp     __tailMerge_efscore_dll
```
