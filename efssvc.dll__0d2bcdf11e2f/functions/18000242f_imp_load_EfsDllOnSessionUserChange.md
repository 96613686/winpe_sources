# __imp_load_EfsDllOnSessionUserChange

- ea: `0x18000242f`
- end: `0x18000243b`
- name: `__imp_load_EfsDllOnSessionUserChange`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllOnSessionUserChange` at `0x18000242f`

## pseudocode

```c
__int64 __fastcall load_EfsDllOnSessionUserChange(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_efscore_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000242f  lea     rax, __imp_EfsDllOnSessionUserChange
0x180002436  jmp     __tailMerge_efscore_dll
```
