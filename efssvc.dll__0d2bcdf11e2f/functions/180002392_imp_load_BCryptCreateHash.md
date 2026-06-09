# __imp_load_BCryptCreateHash

- ea: `0x180002392`
- end: `0x18000239e`
- name: `__imp_load_BCryptCreateHash`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002290`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x180002392`

## pseudocode

```c
__int64 load_BCryptCreateHash()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x180002392  lea     rax, __imp_BCryptCreateHash
0x180002399  jmp     __tailMerge_bcrypt_dll
```
