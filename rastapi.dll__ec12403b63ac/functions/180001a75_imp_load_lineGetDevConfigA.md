# __imp_load_lineGetDevConfigA

- ea: `0x180001a75`
- end: `0x180001a81`
- name: `__imp_load_lineGetDevConfigA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800018a0`

## import_xrefs

- `ext-ms-win-ras-tapi32-l1-1-1!lineGetDevConfigA` at `0x180001a75`

## pseudocode

```c
__int64 load_lineGetDevConfigA()
{
  return _tailMerge_ext_ms_win_ras_tapi32_l1_1_1_dll();
}

```

## disassembly

```asm
0x180001a75  lea     rax, __imp_lineGetDevConfigA
0x180001a7c  jmp     __tailMerge_ext_ms_win_ras_tapi32_l1_1_1_dll
```
