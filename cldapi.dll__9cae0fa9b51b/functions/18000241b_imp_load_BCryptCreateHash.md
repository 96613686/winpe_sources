# __imp_load_BCryptCreateHash

- ea: `0x18000241b`
- end: `0x180002427`
- name: `__imp_load_BCryptCreateHash`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002330`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x18000241b`

## pseudocode

```c
__int64 load_BCryptCreateHash()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x18000241b  lea     rax, __imp_BCryptCreateHash
0x180002422  jmp     __tailMerge_bcrypt_dll
```
