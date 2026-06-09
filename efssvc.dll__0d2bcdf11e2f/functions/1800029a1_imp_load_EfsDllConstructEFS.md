# __imp_load_EfsDllConstructEFS

- ea: `0x1800029a1`
- end: `0x1800029ad`
- name: `__imp_load_EfsDllConstructEFS`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllConstructEFS` at `0x1800029a1`

## pseudocode

```c
__int64 __fastcall load_EfsDllConstructEFS(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_efscore_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800029a1  lea     rax, __imp_EfsDllConstructEFS
0x1800029a8  jmp     __tailMerge_efscore_dll
```
