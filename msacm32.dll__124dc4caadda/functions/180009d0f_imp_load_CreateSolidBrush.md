# __imp_load_CreateSolidBrush

- ea: `0x180009d0f`
- end: `0x180009d1b`
- name: `__imp_load_CreateSolidBrush`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180009c90`

## import_xrefs

- `ext-ms-win-gdi-draw-l1-1-0!CreateSolidBrush` at `0x180009d0f`

## pseudocode

```c
__int64 load_CreateSolidBrush()
{
  return _tailMerge_ext_ms_win_gdi_draw_l1_1_0_dll();
}

```

## disassembly

```asm
0x180009d0f  lea     rax, __imp_CreateSolidBrush
0x180009d16  jmp     __tailMerge_ext_ms_win_gdi_draw_l1_1_0_dll
```
