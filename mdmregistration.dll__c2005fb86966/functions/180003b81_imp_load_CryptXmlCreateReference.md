# __imp_load_CryptXmlCreateReference

- ea: `0x180003b81`
- end: `0x180003b8d`
- name: `__imp_load_CryptXmlCreateReference`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180003ade`

## import_xrefs

- `CRYPTXML!CryptXmlCreateReference` at `0x180003b81`

## pseudocode

```c
__int64 load_CryptXmlCreateReference()
{
  return _tailMerge_cryptxml_dll();
}

```

## disassembly

```asm
0x180003b81  lea     rax, __imp_CryptXmlCreateReference
0x180003b88  jmp     __tailMerge_cryptxml_dll
```
