# __imp_load_CryptCreateHash

- ea: `0x180001f48`
- end: `0x180001f54`
- name: `__imp_load_CryptCreateHash`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001ea5`

## import_xrefs

- `CRYPTSP!CryptCreateHash` at `0x180001f48`

## pseudocode

```c
__int64 load_CryptCreateHash()
{
  return _tailMerge_cryptsp_dll();
}

```

## disassembly

```asm
0x180001f48  lea     rax, __imp_CryptCreateHash
0x180001f4f  jmp     __tailMerge_cryptsp_dll
```
