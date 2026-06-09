# __imp_load_EfsDllUnloadUserProfile

- ea: `0x1800024e3`
- end: `0x1800024ef`
- name: `__imp_load_EfsDllUnloadUserProfile`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllUnloadUserProfile` at `0x1800024e3`

## pseudocode

```c
__int64 __fastcall load_EfsDllUnloadUserProfile(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_efscore_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800024e3  lea     rax, __imp_EfsDllUnloadUserProfile
0x1800024ea  jmp     __tailMerge_efscore_dll
```
