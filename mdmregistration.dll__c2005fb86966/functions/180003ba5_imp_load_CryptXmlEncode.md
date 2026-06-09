# __imp_load_CryptXmlEncode

- ea: `0x180003ba5`
- end: `0x180003bb1`
- name: `__imp_load_CryptXmlEncode`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180003ade`

## import_xrefs

- `CRYPTXML!CryptXmlEncode` at `0x180003ba5`

## pseudocode

```c
__int64 load_CryptXmlEncode()
{
  return _tailMerge_cryptxml_dll();
}

```

## disassembly

```asm
0x180003ba5  lea     rax, __imp_CryptXmlEncode
0x180003bac  jmp     __tailMerge_cryptxml_dll
```
