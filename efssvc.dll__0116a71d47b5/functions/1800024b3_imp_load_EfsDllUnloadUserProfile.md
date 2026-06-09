# __imp_load_EfsDllUnloadUserProfile

- ea: `0x1800024b3`
- end: `0x1800024bf`
- name: `__imp_load_EfsDllUnloadUserProfile`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EfsDllUnloadUserProfile` at `0x1800024b3`

## pseudocode

```c
__int64 load_EfsDllUnloadUserProfile()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x1800024b3  lea     rax, __imp_EfsDllUnloadUserProfile
0x1800024ba  jmp     __tailMerge_efscore_dll
```
