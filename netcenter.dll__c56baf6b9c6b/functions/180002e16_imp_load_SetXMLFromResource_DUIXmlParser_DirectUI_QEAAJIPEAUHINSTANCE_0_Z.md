# __imp_load_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z

- ea: `0x180002e16`
- end: `0x180002e22`
- name: `__imp_load_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180002c86`

## import_xrefs

- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x180002e16`

## pseudocode

```c
__int64 load__SetXMLFromResource_DUIXmlParser_DirectUI__QEAAJIPEAUHINSTANCE____0_Z()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x180002e16  lea     rax, __imp_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z; DirectUI::DUIXmlParser::SetXMLFromResource(uint,HINSTANCE__ *,HINSTANCE__ *)
0x180002e1d  jmp     __tailMerge_dui70_dll
```
