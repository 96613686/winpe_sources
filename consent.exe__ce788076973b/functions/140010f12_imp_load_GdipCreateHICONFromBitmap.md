# __imp_load_GdipCreateHICONFromBitmap

- ea: `0x140010f12`
- end: `0x140010f1e`
- name: `__imp_load_GdipCreateHICONFromBitmap`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140010e6f`

## import_xrefs

- `gdiplus!GdipCreateHICONFromBitmap` at `0x140010f12`

## pseudocode

```c
__int64 load_GdipCreateHICONFromBitmap()
{
  return _tailMerge_gdiplus_dll();
}

```

## disassembly

```asm
0x140010f12  lea     rax, __imp_GdipCreateHICONFromBitmap
0x140010f19  jmp     __tailMerge_gdiplus_dll
```
