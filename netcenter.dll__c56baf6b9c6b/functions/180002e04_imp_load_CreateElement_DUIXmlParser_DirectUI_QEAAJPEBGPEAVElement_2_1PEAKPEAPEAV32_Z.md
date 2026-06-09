# __imp_load_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z

- ea: `0x180002e04`
- end: `0x180002e10`
- name: `__imp_load_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180002c86`

## import_xrefs

- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x180002e04`

## pseudocode

```c
__int64 load__CreateElement_DUIXmlParser_DirectUI__QEAAJPEBGPEAVElement_2_1PEAKPEAPEAV32__Z()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x180002e04  lea     rax, __imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x180002e0b  jmp     __tailMerge_dui70_dll
```
