# __imp_load_EfsDllGetLocalFileName

- ea: `0x18000253d`
- end: `0x180002549`
- name: `__imp_load_EfsDllGetLocalFileName`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllGetLocalFileName` at `0x18000253d`

## pseudocode

```c
__int64 __fastcall load_EfsDllGetLocalFileName(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_efscore_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000253d  lea     rax, __imp_EfsDllGetLocalFileName
0x180002544  jmp     __tailMerge_efscore_dll
```
