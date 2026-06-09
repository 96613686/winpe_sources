# __imp_load_CreateXmlWriter

- ea: `0x180023c45`
- end: `0x180023c51`
- name: `__imp_load_CreateXmlWriter`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180023b17`

## import_xrefs

- `XmlLite!CreateXmlWriter` at `0x180023c45`

## pseudocode

```c
__int64 load_CreateXmlWriter()
{
  return _tailMerge_xmllite_dll();
}

```

## disassembly

```asm
0x180023c45  lea     rax, __imp_CreateXmlWriter
0x180023c4c  jmp     __tailMerge_xmllite_dll
```
