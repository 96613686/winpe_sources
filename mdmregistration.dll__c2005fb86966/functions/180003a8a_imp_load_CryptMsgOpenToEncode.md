# __imp_load_CryptMsgOpenToEncode

- ea: `0x180003a8a`
- end: `0x180003a96`
- name: `__imp_load_CryptMsgOpenToEncode`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000390f`

## import_xrefs

- `CRYPT32!CryptMsgOpenToEncode` at `0x180003a8a`

## pseudocode

```c
__int64 load_CryptMsgOpenToEncode()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x180003a8a  lea     rax, __imp_CryptMsgOpenToEncode
0x180003a91  jmp     __tailMerge_crypt32_dll
```
