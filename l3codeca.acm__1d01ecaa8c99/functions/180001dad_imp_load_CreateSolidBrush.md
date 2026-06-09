# __imp_load_CreateSolidBrush

- ea: `0x180001dad`
- end: `0x180001db9`
- name: `__imp_load_CreateSolidBrush`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001d2e`

## import_xrefs

- `ext-ms-win-gdi-draw-l1-1-0!CreateSolidBrush` at `0x180001dad`

## pseudocode

```c
__int64 load_CreateSolidBrush()
{
  return _tailMerge_ext_ms_win_gdi_draw_l1_1_0_dll();
}

```

## disassembly

```asm
0x180001dad  lea     rax, __imp_CreateSolidBrush
0x180001db4  jmp     __tailMerge_ext_ms_win_gdi_draw_l1_1_0_dll
```
