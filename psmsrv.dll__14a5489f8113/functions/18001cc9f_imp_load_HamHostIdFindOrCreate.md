# __imp_load_HamHostIdFindOrCreate

- ea: `0x18001cc9f`
- end: `0x18001ccab`
- name: `__imp_load_HamHostIdFindOrCreate`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001cc20`

## import_xrefs

- `ext-ms-win-hostactivitymanager-hostidstore-l1-1-0!HamHostIdFindOrCreate` at `0x18001cc9f`

## pseudocode

```c
__int64 load_HamHostIdFindOrCreate()
{
  return _tailMerge_ext_ms_win_hostactivitymanager_hostidstore_l1_1_0_dll();
}

```

## disassembly

```asm
0x18001cc9f  lea     rax, __imp_HamHostIdFindOrCreate
0x18001cca6  jmp     __tailMerge_ext_ms_win_hostactivitymanager_hostidstore_l1_1_0_dll
```
