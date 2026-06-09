# __imp_load_?Remove@Element@DirectUI@@QEAAJPEAV12@@Z

- ea: `0x180002d74`
- end: `0x180002d80`
- name: `__imp_load_?Remove@Element@DirectUI@@QEAAJPEAV12@@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x180002c86`

## import_xrefs

- `DUI70!?Remove@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x180002d74`

## pseudocode

```c
__int64 load__Remove_Element_DirectUI__QEAAJPEAV12__Z()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x180002d74  lea     rax, __imp_?Remove@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Remove(DirectUI::Element *)
0x180002d7b  jmp     __tailMerge_dui70_dll
```
