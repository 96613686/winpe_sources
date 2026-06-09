# __imp_load_lineOpenA

- ea: `0x180001931`
- end: `0x18000193d`
- name: `__imp_load_lineOpenA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800018a0`

## import_xrefs

- `ext-ms-win-ras-tapi32-l1-1-1!lineOpenA` at `0x180001931`

## pseudocode

```c
__int64 load_lineOpenA()
{
  return _tailMerge_ext_ms_win_ras_tapi32_l1_1_1_dll();
}

```

## disassembly

```asm
0x180001931  lea     rax, __imp_lineOpenA
0x180001938  jmp     __tailMerge_ext_ms_win_ras_tapi32_l1_1_1_dll
```
