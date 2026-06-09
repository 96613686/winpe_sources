# __imp_load_CreateXmlReader

- ea: `0x18000390b`
- end: `0x180003917`
- name: `__imp_load_CreateXmlReader`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18000387a`

## import_xrefs

- `XmlLite!CreateXmlReader` at `0x18000390b`

## pseudocode

```c
__int64 load_CreateXmlReader()
{
  return _tailMerge_xmllite_dll();
}

```

## disassembly

```asm
0x18000390b  lea     rax, __imp_CreateXmlReader
0x180003912  jmp     __tailMerge_xmllite_dll
```
