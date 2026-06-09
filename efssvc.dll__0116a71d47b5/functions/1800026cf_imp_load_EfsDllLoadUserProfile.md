# __imp_load_EfsDllLoadUserProfile

- ea: `0x1800026cf`
- end: `0x1800026db`
- name: `__imp_load_EfsDllLoadUserProfile`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EfsDllLoadUserProfile` at `0x1800026cf`

## pseudocode

```c
__int64 load_EfsDllLoadUserProfile()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x1800026cf  lea     rax, __imp_EfsDllLoadUserProfile
0x1800026d6  jmp     __tailMerge_efscore_dll
```
