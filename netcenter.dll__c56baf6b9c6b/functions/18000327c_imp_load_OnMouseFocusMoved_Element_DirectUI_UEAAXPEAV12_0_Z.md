# __imp_load_?OnMouseFocusMoved@Element@DirectUI@@UEAAXPEAV12@0@Z

- ea: `0x18000327c`
- end: `0x180003288`
- name: `__imp_load_?OnMouseFocusMoved@Element@DirectUI@@UEAAXPEAV12@0@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002c86`

## import_xrefs

- `DUI70!?OnMouseFocusMoved@Element@DirectUI@@UEAAXPEAV12@0@Z` at `0x18000327c`

## pseudocode

```c
__int64 load__OnMouseFocusMoved_Element_DirectUI__UEAAXPEAV12_0_Z()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x18000327c  lea     rax, __imp_?OnMouseFocusMoved@Element@DirectUI@@UEAAXPEAV12@0@Z; DirectUI::Element::OnMouseFocusMoved(DirectUI::Element *,DirectUI::Element *)
0x180003283  jmp     __tailMerge_dui70_dll
```
