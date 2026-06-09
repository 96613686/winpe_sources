# __imp_load_CreateXmlReaderInputWithEncodingName

- ea: `0x1800038f9`
- end: `0x180003905`
- name: `__imp_load_CreateXmlReaderInputWithEncodingName`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18000387a`

## import_xrefs

- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x1800038f9`

## pseudocode

```c
__int64 load_CreateXmlReaderInputWithEncodingName()
{
  return _tailMerge_xmllite_dll();
}

```

## disassembly

```asm
0x1800038f9  lea     rax, __imp_CreateXmlReaderInputWithEncodingName
0x180003900  jmp     __tailMerge_xmllite_dll
```
