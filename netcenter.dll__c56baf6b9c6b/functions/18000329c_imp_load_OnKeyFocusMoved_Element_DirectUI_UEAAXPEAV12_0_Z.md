# __imp_load_?OnKeyFocusMoved@Element@DirectUI@@UEAAXPEAV12@0@Z

- ea: `0x18000329c`
- end: `0x1800032a8`
- name: `__imp_load_?OnKeyFocusMoved@Element@DirectUI@@UEAAXPEAV12@0@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002c86`

## import_xrefs

- `DUI70!?OnKeyFocusMoved@Element@DirectUI@@UEAAXPEAV12@0@Z` at `0x18000329c`

## pseudocode

```c
__int64 load__OnKeyFocusMoved_Element_DirectUI__UEAAXPEAV12_0_Z()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x18000329c  lea     rax, __imp_?OnKeyFocusMoved@Element@DirectUI@@UEAAXPEAV12@0@Z; DirectUI::Element::OnKeyFocusMoved(DirectUI::Element *,DirectUI::Element *)
0x1800032a3  jmp     __tailMerge_dui70_dll
```
