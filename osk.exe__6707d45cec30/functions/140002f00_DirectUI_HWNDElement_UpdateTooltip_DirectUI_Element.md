# DirectUI::HWNDElement::UpdateTooltip(DirectUI::Element *)

- ea: `0x140002f00`
- end: `0x140002f06`
- name: `?UpdateTooltip@HWNDElement@DirectUI@@UEAAXPEAVElement@2@@Z_0`
- size: `6`
- prototype: `void(DirectUI::HWNDElement *__hidden this, struct DirectUI::Element *)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `DUI70!?UpdateTooltip@HWNDElement@DirectUI@@UEAAXPEAVElement@2@@Z` at `0x140002f00`

## pseudocode

```c
// attributes: thunk
void __fastcall DirectUI::HWNDElement::UpdateTooltip(DirectUI::HWNDElement *this, struct DirectUI::Element *a2)
{
  __imp_?UpdateTooltip@HWNDElement@DirectUI@@UEAAXPEAVElement@2@@Z(this, a2);
}

```

## disassembly

```asm
0x140002f00  jmp     cs:__imp_?UpdateTooltip@HWNDElement@DirectUI@@UEAAXPEAVElement@2@@Z
```
