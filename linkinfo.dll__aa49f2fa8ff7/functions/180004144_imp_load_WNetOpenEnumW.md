# __imp_load_WNetOpenEnumW

- ea: `0x180004144`
- end: `0x180004150`
- name: `__imp_load_WNetOpenEnumW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003fe0`

## import_xrefs

- `MPR!WNetOpenEnumW` at `0x180004144`

## pseudocode

```c
__int64 load_WNetOpenEnumW()
{
  return _tailMerge_mpr_dll();
}

```

## disassembly

```asm
0x180004144  lea     rax, __imp_WNetOpenEnumW
0x18000414b  jmp     __tailMerge_mpr_dll
```
