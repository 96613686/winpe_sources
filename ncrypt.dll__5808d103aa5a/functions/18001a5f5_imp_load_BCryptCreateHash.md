# __imp_load_BCryptCreateHash

- ea: `0x18001a5f5`
- end: `0x18001a601`
- name: `__imp_load_BCryptCreateHash`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001a4e6`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x18001a5f5`

## pseudocode

```c
__int64 load_BCryptCreateHash()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x18001a5f5  lea     rax, __imp_BCryptCreateHash
0x18001a5fc  jmp     __tailMerge_bcrypt_dll
```
