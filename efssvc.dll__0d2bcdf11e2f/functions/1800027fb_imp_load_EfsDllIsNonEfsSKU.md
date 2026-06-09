# __imp_load_EfsDllIsNonEfsSKU

- ea: `0x1800027fb`
- end: `0x180002807`
- name: `__imp_load_EfsDllIsNonEfsSKU`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllIsNonEfsSKU` at `0x1800027fb`

## pseudocode

```c
__int64 __fastcall load_EfsDllIsNonEfsSKU(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_efscore_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800027fb  lea     rax, __imp_EfsDllIsNonEfsSKU
0x180002802  jmp     __tailMerge_efscore_dll
```
