# __imp_load_CryptXmlSign

- ea: `0x180003b93`
- end: `0x180003b9f`
- name: `__imp_load_CryptXmlSign`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180003ade`

## import_xrefs

- `CRYPTXML!CryptXmlSign` at `0x180003b93`

## pseudocode

```c
__int64 load_CryptXmlSign()
{
  return _tailMerge_cryptxml_dll();
}

```

## disassembly

```asm
0x180003b93  lea     rax, __imp_CryptXmlSign
0x180003b9a  jmp     __tailMerge_cryptxml_dll
```
