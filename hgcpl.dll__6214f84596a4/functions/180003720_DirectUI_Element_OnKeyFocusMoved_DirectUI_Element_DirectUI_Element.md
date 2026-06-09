# DirectUI::Element::OnKeyFocusMoved(DirectUI::Element *,DirectUI::Element *)

- ea: `0x180003720`
- end: `0x180003726`
- name: `?OnKeyFocusMoved@Element@DirectUI@@UEAAXPEAV12@0@Z_0`
- size: `6`
- prototype: `void(DirectUI::Element *__hidden this, struct DirectUI::Element *, struct DirectUI::Element *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `DUI70!?OnKeyFocusMoved@Element@DirectUI@@UEAAXPEAV12@0@Z` at `0x180003720`

## pseudocode

```c
// attributes: thunk
void __fastcall DirectUI::Element::OnKeyFocusMoved(
        DirectUI::Element *this,
        struct DirectUI::Element *a2,
        struct DirectUI::Element *a3)
{
  __imp_?OnKeyFocusMoved@Element@DirectUI@@UEAAXPEAV12@0@Z(this, a2, a3);
}

```

## disassembly

```asm
0x180003720  jmp     cs:__imp_?OnKeyFocusMoved@Element@DirectUI@@UEAAXPEAV12@0@Z
```
