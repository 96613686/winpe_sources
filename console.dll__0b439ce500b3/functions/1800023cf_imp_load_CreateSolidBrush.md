# __imp_load_CreateSolidBrush

- ea: `0x1800023cf`
- end: `0x1800023db`
- name: `__imp_load_CreateSolidBrush`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002350`

## import_xrefs

- `ext-ms-win-gdi-draw-l1-1-0!CreateSolidBrush` at `0x1800023cf`

## pseudocode

```c
__int64 load_CreateSolidBrush()
{
  return _tailMerge_ext_ms_win_gdi_draw_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800023cf  lea     rax, __imp_CreateSolidBrush
0x1800023d6  jmp     __tailMerge_ext_ms_win_gdi_draw_l1_1_0_dll
```
