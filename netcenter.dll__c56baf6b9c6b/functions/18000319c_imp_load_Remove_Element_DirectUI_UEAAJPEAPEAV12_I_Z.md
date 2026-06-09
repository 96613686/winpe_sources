# __imp_load_?Remove@Element@DirectUI@@UEAAJPEAPEAV12@I@Z

- ea: `0x18000319c`
- end: `0x1800031a8`
- name: `__imp_load_?Remove@Element@DirectUI@@UEAAJPEAPEAV12@I@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x180002c86`

## import_xrefs

- `DUI70!?Remove@Element@DirectUI@@UEAAJPEAPEAV12@I@Z` at `0x18000319c`

## pseudocode

```c
__int64 load__Remove_Element_DirectUI__UEAAJPEAPEAV12_I_Z()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x18000319c  lea     rax, __imp_?Remove@Element@DirectUI@@UEAAJPEAPEAV12@I@Z; DirectUI::Element::Remove(DirectUI::Element * *,uint)
0x1800031a3  jmp     __tailMerge_dui70_dll
```
