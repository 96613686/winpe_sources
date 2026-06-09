# __imp_load_DeleteObject

- ea: `0x1800021b0`
- end: `0x1800021bc`
- name: `__imp_load_DeleteObject`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002131`

## import_xrefs

- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800021b0`

## pseudocode

```c
__int64 load_DeleteObject()
{
  return _tailMerge_ext_ms_win_rtcore_gdi_object_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800021b0  lea     rax, __imp_DeleteObject
0x1800021b7  jmp     __tailMerge_ext_ms_win_rtcore_gdi_object_l1_1_0_dll
```
