# __imp_load_HamHostIdFindOrCreate

- ea: `0x1800077f9`
- end: `0x180007805`
- name: `__imp_load_HamHostIdFindOrCreate`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000777a`

## import_xrefs

- `ext-ms-win-hostactivitymanager-hostidstore-l1-1-0!HamHostIdFindOrCreate` at `0x1800077f9`

## pseudocode

```c
__int64 load_HamHostIdFindOrCreate()
{
  return _tailMerge_ext_ms_win_hostactivitymanager_hostidstore_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800077f9  lea     rax, __imp_HamHostIdFindOrCreate
0x180007800  jmp     __tailMerge_ext_ms_win_hostactivitymanager_hostidstore_l1_1_0_dll
```
