# __imp_load_EfsDllFreeUserInfo

- ea: `0x180002627`
- end: `0x180002633`
- name: `__imp_load_EfsDllFreeUserInfo`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllFreeUserInfo` at `0x180002627`

## pseudocode

```c
__int64 load_EfsDllFreeUserInfo()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002627  lea     rax, __imp_EfsDllFreeUserInfo
0x18000262e  jmp     __tailMerge_efscore_dll
```
