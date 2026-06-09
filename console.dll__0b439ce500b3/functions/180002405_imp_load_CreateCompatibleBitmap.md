# __imp_load_CreateCompatibleBitmap

- ea: `0x180002405`
- end: `0x180002411`
- name: `__imp_load_CreateCompatibleBitmap`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002350`

## import_xrefs

- `ext-ms-win-gdi-draw-l1-1-0!CreateCompatibleBitmap` at `0x180002405`

## pseudocode

```c
__int64 load_CreateCompatibleBitmap()
{
  return _tailMerge_ext_ms_win_gdi_draw_l1_1_0_dll();
}

```

## disassembly

```asm
0x180002405  lea     rax, __imp_CreateCompatibleBitmap
0x18000240c  jmp     __tailMerge_ext_ms_win_gdi_draw_l1_1_0_dll
```
