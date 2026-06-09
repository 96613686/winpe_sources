# __imp_load_EfsDllFreeUserInfo

- ea: `0x1800025f7`
- end: `0x180002603`
- name: `__imp_load_EfsDllFreeUserInfo`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EfsDllFreeUserInfo` at `0x1800025f7`

## pseudocode

```c
__int64 load_EfsDllFreeUserInfo()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x1800025f7  lea     rax, __imp_EfsDllFreeUserInfo
0x1800025fe  jmp     __tailMerge_efscore_dll
```
