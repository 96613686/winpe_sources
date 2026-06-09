# __imp_load_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z

- ea: `0x18000253a`
- end: `0x180002546`
- name: `__imp_load_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800023b4`

## import_xrefs

- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18000253a`

## pseudocode

```c
__int64 load__CreateElement_DUIXmlParser_DirectUI__QEAAJPEBGPEAVElement_2_1PEAKPEAPEAV32__Z()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x18000253a  lea     rax, __imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x180002541  jmp     __tailMerge_dui70_dll
```
