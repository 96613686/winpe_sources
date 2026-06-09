# __imp_load_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ

- ea: `0x180058532`
- end: `0x18005853e`
- name: `__imp_load_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800583ff`

## import_xrefs

- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180058532`

## pseudocode

```c
__int64 load__Destroy_DUIXmlParser_DirectUI__QEAAXXZ()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x180058532  lea     rax, __imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x180058539  jmp     __tailMerge_dui70_dll
```
