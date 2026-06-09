# __imp_load_EfsDllUnloadUserProfile

- ea: `0x1800024e3`
- end: `0x1800024ef`
- name: `__imp_load_EfsDllUnloadUserProfile`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllUnloadUserProfile` at `0x1800024e3`

## pseudocode

```c
__int64 load_EfsDllUnloadUserProfile()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x1800024e3  lea     rax, __imp_EfsDllUnloadUserProfile
0x1800024ea  jmp     __tailMerge_efscore_dll
```
