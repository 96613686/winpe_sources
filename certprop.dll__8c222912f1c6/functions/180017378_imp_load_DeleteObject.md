# __imp_load_DeleteObject

- ea: `0x180017378`
- end: `0x180017384`
- name: `__imp_load_DeleteObject`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800172f9`

## import_xrefs

- `GDI32!DeleteObject` at `0x180017378`

## pseudocode

```c
__int64 load_DeleteObject()
{
  return _tailMerge_gdi32_dll();
}

```

## disassembly

```asm
0x180017378  lea     rax, __imp_DeleteObject
0x18001737f  jmp     __tailMerge_gdi32_dll
```
