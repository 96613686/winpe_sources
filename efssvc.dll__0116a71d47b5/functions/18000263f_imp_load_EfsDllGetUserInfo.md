# __imp_load_EfsDllGetUserInfo

- ea: `0x18000263f`
- end: `0x18000264b`
- name: `__imp_load_EfsDllGetUserInfo`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EfsDllGetUserInfo` at `0x18000263f`

## pseudocode

```c
__int64 load_EfsDllGetUserInfo()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x18000263f  lea     rax, __imp_EfsDllGetUserInfo
0x180002646  jmp     __tailMerge_efscore_dll
```
