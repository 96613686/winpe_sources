# __imp_load_GdipCreateBitmapFromHBITMAP

- ea: `0x18001746f`
- end: `0x18001747b`
- name: `__imp_load_GdipCreateBitmapFromHBITMAP`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180017396`

## import_xrefs

- `gdiplus!GdipCreateBitmapFromHBITMAP` at `0x18001746f`

## pseudocode

```c
__int64 load_GdipCreateBitmapFromHBITMAP()
{
  return _tailMerge_gdiplus_dll();
}

```

## disassembly

```asm
0x18001746f  lea     rax, __imp_GdipCreateBitmapFromHBITMAP
0x180017476  jmp     __tailMerge_gdiplus_dll
```
