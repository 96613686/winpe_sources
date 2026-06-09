# DirectUI::Element::RemoveBehavior(IDuiBehavior *)

- ea: `0x140003080`
- end: `0x140003086`
- name: `?RemoveBehavior@Element@DirectUI@@UEAAJPEAUIDuiBehavior@@@Z_0`
- size: `6`
- prototype: `int(DirectUI::Element *__hidden this, struct IDuiBehavior *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `DUI70!?RemoveBehavior@Element@DirectUI@@UEAAJPEAUIDuiBehavior@@@Z` at `0x140003080`

## pseudocode

```c
// attributes: thunk
int __fastcall DirectUI::Element::RemoveBehavior(DirectUI::Element *this, struct IDuiBehavior *a2)
{
  return __imp_?RemoveBehavior@Element@DirectUI@@UEAAJPEAUIDuiBehavior@@@Z(this, a2);
}

```

## disassembly

```asm
0x140003080  jmp     cs:__imp_?RemoveBehavior@Element@DirectUI@@UEAAJPEAUIDuiBehavior@@@Z
```
