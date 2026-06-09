# __imp_load_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z

- ea: `0x180002e3a`
- end: `0x180002e46`
- name: `__imp_load_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180002c86`

## import_xrefs

- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x180002e3a`

## pseudocode

```c
__int64 load__Create_DUIXmlParser_DirectUI__SAJPEAPEAV12_P6APEAVValue_2_PEBGPEAX_Z2P6AX11H2_Z2_Z()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x180002e3a  lea     rax, __imp_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z; DirectUI::DUIXmlParser::Create(DirectUI::DUIXmlParser * *,DirectUI::Value * (*)(ushort const *,void *),void *,void (*)(ushort const *,ushort const *,int,void *),void *)
0x180002e41  jmp     __tailMerge_dui70_dll
```
