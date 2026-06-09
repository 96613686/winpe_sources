# __imp_load_GdipCreateBitmapFromStream

- ea: `0x180017493`
- end: `0x18001749f`
- name: `__imp_load_GdipCreateBitmapFromStream`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180017396`

## import_xrefs

- `gdiplus!GdipCreateBitmapFromStream` at `0x180017493`

## pseudocode

```c
__int64 load_GdipCreateBitmapFromStream()
{
  return _tailMerge_gdiplus_dll();
}

```

## disassembly

```asm
0x180017493  lea     rax, __imp_GdipCreateBitmapFromStream
0x18001749a  jmp     __tailMerge_gdiplus_dll
```
