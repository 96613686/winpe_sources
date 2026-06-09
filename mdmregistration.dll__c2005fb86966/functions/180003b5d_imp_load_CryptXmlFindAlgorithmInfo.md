# __imp_load_CryptXmlFindAlgorithmInfo

- ea: `0x180003b5d`
- end: `0x180003b69`
- name: `__imp_load_CryptXmlFindAlgorithmInfo`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180003ade`

## import_xrefs

- `CRYPTXML!CryptXmlFindAlgorithmInfo` at `0x180003b5d`

## pseudocode

```c
__int64 load_CryptXmlFindAlgorithmInfo()
{
  return _tailMerge_cryptxml_dll();
}

```

## disassembly

```asm
0x180003b5d  lea     rax, __imp_CryptXmlFindAlgorithmInfo
0x180003b64  jmp     __tailMerge_cryptxml_dll
```
