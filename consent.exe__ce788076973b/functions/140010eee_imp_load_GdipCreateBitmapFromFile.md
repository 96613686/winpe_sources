# __imp_load_GdipCreateBitmapFromFile

- ea: `0x140010eee`
- end: `0x140010efa`
- name: `__imp_load_GdipCreateBitmapFromFile`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140010e6f`

## import_xrefs

- `gdiplus!GdipCreateBitmapFromFile` at `0x140010eee`

## pseudocode

```c
__int64 load_GdipCreateBitmapFromFile()
{
  return _tailMerge_gdiplus_dll();
}

```

## disassembly

```asm
0x140010eee  lea     rax, __imp_GdipCreateBitmapFromFile
0x140010ef5  jmp     __tailMerge_gdiplus_dll
```
