# __imp_load_CryptXmlOpenToEncode

- ea: `0x180003b6f`
- end: `0x180003b7b`
- name: `__imp_load_CryptXmlOpenToEncode`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180003ade`

## import_xrefs

- `CRYPTXML!CryptXmlOpenToEncode` at `0x180003b6f`

## pseudocode

```c
__int64 load_CryptXmlOpenToEncode()
{
  return _tailMerge_cryptxml_dll();
}

```

## disassembly

```asm
0x180003b6f  lea     rax, __imp_CryptXmlOpenToEncode
0x180003b76  jmp     __tailMerge_cryptxml_dll
```
