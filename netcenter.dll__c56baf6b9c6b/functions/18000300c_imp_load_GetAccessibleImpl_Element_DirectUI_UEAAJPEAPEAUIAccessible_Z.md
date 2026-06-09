# __imp_load_?GetAccessibleImpl@Element@DirectUI@@UEAAJPEAPEAUIAccessible@@@Z

- ea: `0x18000300c`
- end: `0x180003018`
- name: `__imp_load_?GetAccessibleImpl@Element@DirectUI@@UEAAJPEAPEAUIAccessible@@@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002c86`

## import_xrefs

- `DUI70!?GetAccessibleImpl@Element@DirectUI@@UEAAJPEAPEAUIAccessible@@@Z` at `0x18000300c`

## pseudocode

```c
__int64 load__GetAccessibleImpl_Element_DirectUI__UEAAJPEAPEAUIAccessible___Z()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x18000300c  lea     rax, __imp_?GetAccessibleImpl@Element@DirectUI@@UEAAJPEAPEAUIAccessible@@@Z; DirectUI::Element::GetAccessibleImpl(IAccessible * *)
0x180003013  jmp     __tailMerge_dui70_dll
```
