# __imp_load_CreatePropertySheetPageW

- ea: `0x180003011`
- end: `0x18000301d`
- name: `__imp_load_CreatePropertySheetPageW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002c25`

## import_xrefs

- `COMCTL32!CreatePropertySheetPageW` at `0x180003011`

## pseudocode

```c
__int64 load_CreatePropertySheetPageW()
{
  return _tailMerge_comctl32_dll();
}

```

## disassembly

```asm
0x180003011  lea     rax, __imp_CreatePropertySheetPageW
0x180003018  jmp     __tailMerge_comctl32_dll
```
