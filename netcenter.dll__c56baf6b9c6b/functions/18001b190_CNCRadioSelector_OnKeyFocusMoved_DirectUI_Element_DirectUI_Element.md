# CNCRadioSelector::OnKeyFocusMoved(DirectUI::Element *,DirectUI::Element *)

- ea: `0x18001b190`
- end: `0x18001b1a8`
- name: `?OnKeyFocusMoved@CNCRadioSelector@@UEAAXPEAVElement@DirectUI@@0@Z`
- size: `24`
- prototype: `void __fastcall(CNCRadioSelector *__hidden this, struct DirectUI::Element *, struct DirectUI::Element *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001b190`

## import_xrefs

- `DUI70!?OnKeyFocusMoved@Selector@DirectUI@@UEAAXPEAVElement@2@0@Z` at `0x18001b19d`
- `DUI70!?OnKeyFocusMoved@Selector@DirectUI@@UEAAXPEAVElement@2@0@Z` at `0x18001b19d`

## pseudocode

```c
void __fastcall CNCRadioSelector::OnKeyFocusMoved(
        CNCRadioSelector *this,
        struct DirectUI::Element *a2,
        struct DirectUI::Element *a3)
{
  if ( !*((_DWORD *)this + 50) )
    DirectUI::Selector::OnKeyFocusMoved(this, a2, a3);
}

```

## disassembly

```asm
0x18001b190  sub     rsp, 28h
0x18001b194  cmp     dword ptr [rcx+0C8h], 0
0x18001b19b  jnz     short loc_18001B1A3
0x18001b19d  call    cs:__imp_?OnKeyFocusMoved@Selector@DirectUI@@UEAAXPEAVElement@2@0@Z; DirectUI::Selector::OnKeyFocusMoved(DirectUI::Element *,DirectUI::Element *)
0x18001b1a3  add     rsp, 28h
0x18001b1a7  retn
```
