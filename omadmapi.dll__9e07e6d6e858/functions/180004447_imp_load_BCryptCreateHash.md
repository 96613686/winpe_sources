# __imp_load_BCryptCreateHash

- ea: `0x180004447`
- end: `0x180004453`
- name: `__imp_load_BCryptCreateHash`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800043a4`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x180004447`

## pseudocode

```c
__int64 load_BCryptCreateHash()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x180004447  lea     rax, __imp_BCryptCreateHash
0x18000444e  jmp     __tailMerge_bcrypt_dll
```
