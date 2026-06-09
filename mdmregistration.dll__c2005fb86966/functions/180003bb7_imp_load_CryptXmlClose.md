# __imp_load_CryptXmlClose

- ea: `0x180003bb7`
- end: `0x180003bc3`
- name: `__imp_load_CryptXmlClose`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180003ade`

## import_xrefs

- `CRYPTXML!CryptXmlClose` at `0x180003bb7`

## pseudocode

```c
__int64 load_CryptXmlClose()
{
  return _tailMerge_cryptxml_dll();
}

```

## disassembly

```asm
0x180003bb7  lea     rax, __imp_CryptXmlClose
0x180003bbe  jmp     __tailMerge_cryptxml_dll
```
