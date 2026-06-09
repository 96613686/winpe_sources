# __imp_load_DeleteObject

- ea: `0x1800583f3`
- end: `0x1800583ff`
- name: `__imp_load_DeleteObject`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180058374`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800583f3`

## pseudocode

```c
__int64 load_DeleteObject()
{
  return _tailMerge_gdi32_dll();
}

```

## disassembly

```asm
0x1800583f3  lea     rax, __imp_DeleteObject
0x1800583fa  jmp     __tailMerge_gdi32_dll
```
