# __imp_load_DeleteObject

- ea: `0x180002cf5`
- end: `0x180002d01`
- name: `__imp_load_DeleteObject`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002c76`

## import_xrefs

- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180002cf5`

## pseudocode

```c
__int64 load_DeleteObject()
{
  return _tailMerge_ext_ms_win_rtcore_gdi_object_l1_1_0_dll();
}

```

## disassembly

```asm
0x180002cf5  lea     rax, __imp_DeleteObject
0x180002cfc  jmp     __tailMerge_ext_ms_win_rtcore_gdi_object_l1_1_0_dll
```
