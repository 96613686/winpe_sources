# __imp_load_lineSetDevConfigA

- ea: `0x180001a63`
- end: `0x180001a6f`
- name: `__imp_load_lineSetDevConfigA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800018a0`

## import_xrefs

- `ext-ms-win-ras-tapi32-l1-1-1!lineSetDevConfigA` at `0x180001a63`

## pseudocode

```c
__int64 load_lineSetDevConfigA()
{
  return _tailMerge_ext_ms_win_ras_tapi32_l1_1_1_dll();
}

```

## disassembly

```asm
0x180001a63  lea     rax, __imp_lineSetDevConfigA
0x180001a6a  jmp     __tailMerge_ext_ms_win_ras_tapi32_l1_1_1_dll
```
