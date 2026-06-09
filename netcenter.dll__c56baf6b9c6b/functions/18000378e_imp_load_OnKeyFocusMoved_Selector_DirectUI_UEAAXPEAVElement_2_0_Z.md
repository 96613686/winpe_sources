# __imp_load_?OnKeyFocusMoved@Selector@DirectUI@@UEAAXPEAVElement@2@0@Z

- ea: `0x18000378e`
- end: `0x18000379a`
- name: `__imp_load_?OnKeyFocusMoved@Selector@DirectUI@@UEAAXPEAVElement@2@0@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002c86`

## import_xrefs

- `DUI70!?OnKeyFocusMoved@Selector@DirectUI@@UEAAXPEAVElement@2@0@Z` at `0x18000378e`

## pseudocode

```c
__int64 load__OnKeyFocusMoved_Selector_DirectUI__UEAAXPEAVElement_2_0_Z()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x18000378e  lea     rax, __imp_?OnKeyFocusMoved@Selector@DirectUI@@UEAAXPEAVElement@2@0@Z; DirectUI::Selector::OnKeyFocusMoved(DirectUI::Element *,DirectUI::Element *)
0x180003795  jmp     __tailMerge_dui70_dll
```
