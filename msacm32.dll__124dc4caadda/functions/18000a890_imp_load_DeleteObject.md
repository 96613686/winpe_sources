# __imp_load_DeleteObject

- ea: `0x18000a890`
- end: `0x18000a89c`
- name: `__imp_load_DeleteObject`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000a811`

## import_xrefs

- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18000a890`

## pseudocode

```c
__int64 load_DeleteObject()
{
  return _tailMerge_ext_ms_win_rtcore_gdi_object_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000a890  lea     rax, __imp_DeleteObject
0x18000a897  jmp     __tailMerge_ext_ms_win_rtcore_gdi_object_l1_1_0_dll
```
