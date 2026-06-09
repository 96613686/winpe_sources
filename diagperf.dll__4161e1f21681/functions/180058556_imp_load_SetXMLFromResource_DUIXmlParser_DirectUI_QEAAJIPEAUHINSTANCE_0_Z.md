# __imp_load_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z

- ea: `0x180058556`
- end: `0x180058562`
- name: `__imp_load_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800583ff`

## import_xrefs

- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x180058556`

## pseudocode

```c
__int64 load__SetXMLFromResource_DUIXmlParser_DirectUI__QEAAJIPEAUHINSTANCE____0_Z()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x180058556  lea     rax, __imp_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z; DirectUI::DUIXmlParser::SetXMLFromResource(uint,HINSTANCE__ *,HINSTANCE__ *)
0x18005855d  jmp     __tailMerge_dui70_dll
```
