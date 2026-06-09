# __imp_load_CreateFontIndirectW

- ea: `0x18000252d`
- end: `0x180002539`
- name: `__imp_load_CreateFontIndirectW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002411`

## import_xrefs

- `ext-ms-win-gdi-font-l1-1-0!CreateFontIndirectW` at `0x18000252d`

## pseudocode

```c
__int64 load_CreateFontIndirectW()
{
  return _tailMerge_ext_ms_win_gdi_font_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000252d  lea     rax, __imp_CreateFontIndirectW
0x180002534  jmp     __tailMerge_ext_ms_win_gdi_font_l1_1_0_dll
```
