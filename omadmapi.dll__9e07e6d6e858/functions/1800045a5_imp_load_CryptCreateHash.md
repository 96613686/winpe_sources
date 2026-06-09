# __imp_load_CryptCreateHash

- ea: `0x1800045a5`
- end: `0x1800045b1`
- name: `__imp_load_CryptCreateHash`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004514`

## import_xrefs

- `CRYPTSP!CryptCreateHash` at `0x1800045a5`

## pseudocode

```c
__int64 load_CryptCreateHash()
{
  return _tailMerge_cryptsp_dll();
}

```

## disassembly

```asm
0x1800045a5  lea     rax, __imp_CryptCreateHash
0x1800045ac  jmp     __tailMerge_cryptsp_dll
```
