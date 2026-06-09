# __imp_load_BCryptCreateHash

- ea: `0x18000559d`
- end: `0x1800055a9`
- name: `__imp_load_BCryptCreateHash`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800054c4`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x18000559d`

## pseudocode

```c
__int64 load_BCryptCreateHash()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x18000559d  lea     rax, __imp_BCryptCreateHash
0x1800055a4  jmp     __tailMerge_bcrypt_dll
```
