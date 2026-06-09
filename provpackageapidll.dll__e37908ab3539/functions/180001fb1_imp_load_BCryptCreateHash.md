# __imp_load_BCryptCreateHash

- ea: `0x180001fb1`
- end: `0x180001fbd`
- name: `__imp_load_BCryptCreateHash`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001e6c`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x180001fb1`

## pseudocode

```c
__int64 load_BCryptCreateHash()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x180001fb1  lea     rax, __imp_BCryptCreateHash
0x180001fb8  jmp     __tailMerge_bcrypt_dll
```
