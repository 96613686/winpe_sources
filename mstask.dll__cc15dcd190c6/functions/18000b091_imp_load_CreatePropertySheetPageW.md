# __imp_load_CreatePropertySheetPageW

- ea: `0x18000b091`
- end: `0x18000b09d`
- name: `__imp_load_CreatePropertySheetPageW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000af5e`

## import_xrefs

- `COMCTL32!CreatePropertySheetPageW` at `0x18000b091`

## pseudocode

```c
__int64 load_CreatePropertySheetPageW()
{
  return _tailMerge_comctl32_dll();
}

```

## disassembly

```asm
0x18000b091  lea     rax, __imp_CreatePropertySheetPageW
0x18000b098  jmp     __tailMerge_comctl32_dll
```
