# __imp_load_CryptCreateHash

- ea: `0x180014d69`
- end: `0x180014d75`
- name: `__imp_load_CryptCreateHash`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180014ca2`

## import_xrefs

- `CRYPTSP!CryptCreateHash` at `0x180014d69`

## pseudocode

```c
__int64 load_CryptCreateHash()
{
  return _tailMerge_cryptsp_dll();
}

```

## disassembly

```asm
0x180014d69  lea     rax, __imp_CryptCreateHash
0x180014d70  jmp     __tailMerge_cryptsp_dll
```
