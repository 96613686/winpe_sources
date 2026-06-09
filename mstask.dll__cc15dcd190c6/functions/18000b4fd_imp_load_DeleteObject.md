# __imp_load_DeleteObject

- ea: `0x18000b4fd`
- end: `0x18000b509`
- name: `__imp_load_DeleteObject`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000aed3`

## import_xrefs

- `GDI32!DeleteObject` at `0x18000b4fd`

## pseudocode

```c
__int64 load_DeleteObject()
{
  return _tailMerge_gdi32_dll();
}

```

## disassembly

```asm
0x18000b4fd  lea     rax, __imp_DeleteObject
0x18000b504  jmp     __tailMerge_gdi32_dll
```
