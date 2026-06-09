# __imp_load_GdipCreateHBITMAPFromBitmap

- ea: `0x18001744b`
- end: `0x180017457`
- name: `__imp_load_GdipCreateHBITMAPFromBitmap`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180017396`

## import_xrefs

- `gdiplus!GdipCreateHBITMAPFromBitmap` at `0x18001744b`

## pseudocode

```c
__int64 load_GdipCreateHBITMAPFromBitmap()
{
  return _tailMerge_gdiplus_dll();
}

```

## disassembly

```asm
0x18001744b  lea     rax, __imp_GdipCreateHBITMAPFromBitmap
0x180017452  jmp     __tailMerge_gdiplus_dll
```
