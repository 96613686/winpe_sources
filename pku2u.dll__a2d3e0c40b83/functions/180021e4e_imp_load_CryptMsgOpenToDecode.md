# __imp_load_CryptMsgOpenToDecode

- ea: `0x180021e4e`
- end: `0x180021e5a`
- name: `__imp_load_CryptMsgOpenToDecode`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180021af7`

## import_xrefs

- `CRYPT32!CryptMsgOpenToDecode` at `0x180021e4e`

## pseudocode

```c
__int64 load_CryptMsgOpenToDecode()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x180021e4e  lea     rax, __imp_CryptMsgOpenToDecode
0x180021e55  jmp     __tailMerge_crypt32_dll
```
