# __imp_load_?RemoveBehavior@Element@DirectUI@@UEAAJPEAUIDuiBehavior@@@Z

- ea: `0x18000358c`
- end: `0x180003598`
- name: `__imp_load_?RemoveBehavior@Element@DirectUI@@UEAAJPEAUIDuiBehavior@@@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800030ff`

## import_xrefs

- `DUI70!?RemoveBehavior@Element@DirectUI@@UEAAJPEAUIDuiBehavior@@@Z` at `0x18000358c`

## pseudocode

```c
__int64 load__RemoveBehavior_Element_DirectUI__UEAAJPEAUIDuiBehavior___Z()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x18000358c  lea     rax, __imp_?RemoveBehavior@Element@DirectUI@@UEAAJPEAUIDuiBehavior@@@Z; DirectUI::Element::RemoveBehavior(IDuiBehavior *)
0x180003593  jmp     __tailMerge_dui70_dll
```
