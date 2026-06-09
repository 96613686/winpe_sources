# __imp_load_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ

- ea: `0x18000255e`
- end: `0x18000256a`
- name: `__imp_load_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800023b4`

## import_xrefs

- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18000255e`

## pseudocode

```c
__int64 load__Destroy_DUIXmlParser_DirectUI__QEAAXXZ()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x18000255e  lea     rax, __imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x180002565  jmp     __tailMerge_dui70_dll
```
