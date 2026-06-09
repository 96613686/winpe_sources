# __imp_load_BCryptCreateHash

- ea: `0x180002362`
- end: `0x18000236e`
- name: `__imp_load_BCryptCreateHash`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002260`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x180002362`

## pseudocode

```c
__int64 load_BCryptCreateHash()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x180002362  lea     rax, __imp_BCryptCreateHash
0x180002369  jmp     __tailMerge_bcrypt_dll
```
