# __imp_load_EfsDllLoadUserProfile

- ea: `0x1800026ff`
- end: `0x18000270b`
- name: `__imp_load_EfsDllLoadUserProfile`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllLoadUserProfile` at `0x1800026ff`

## pseudocode

```c
__int64 load_EfsDllLoadUserProfile()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x1800026ff  lea     rax, __imp_EfsDllLoadUserProfile
0x180002706  jmp     __tailMerge_efscore_dll
```
