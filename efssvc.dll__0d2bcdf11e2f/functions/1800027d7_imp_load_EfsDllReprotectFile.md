# __imp_load_EfsDllReprotectFile

- ea: `0x1800027d7`
- end: `0x1800027e3`
- name: `__imp_load_EfsDllReprotectFile`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllReprotectFile` at `0x1800027d7`

## pseudocode

```c
__int64 __fastcall load_EfsDllReprotectFile(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_efscore_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800027d7  lea     rax, __imp_EfsDllReprotectFile
0x1800027de  jmp     __tailMerge_efscore_dll
```
