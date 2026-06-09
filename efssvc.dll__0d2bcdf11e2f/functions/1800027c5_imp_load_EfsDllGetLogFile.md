# __imp_load_EfsDllGetLogFile

- ea: `0x1800027c5`
- end: `0x1800027d1`
- name: `__imp_load_EfsDllGetLogFile`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllGetLogFile` at `0x1800027c5`

## pseudocode

```c
__int64 __fastcall load_EfsDllGetLogFile(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_efscore_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800027c5  lea     rax, __imp_EfsDllGetLogFile
0x1800027cc  jmp     __tailMerge_efscore_dll
```
