# __imp_load_EfsDllLoadUserProfile

- ea: `0x1800026ff`
- end: `0x18000270b`
- name: `__imp_load_EfsDllLoadUserProfile`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllLoadUserProfile` at `0x1800026ff`

## pseudocode

```c
__int64 __fastcall load_EfsDllLoadUserProfile(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_efscore_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800026ff  lea     rax, __imp_EfsDllLoadUserProfile
0x180002706  jmp     __tailMerge_efscore_dll
```
