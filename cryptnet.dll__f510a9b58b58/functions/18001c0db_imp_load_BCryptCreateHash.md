# __imp_load_BCryptCreateHash

- ea: `0x18001c0db`
- end: `0x18001c0e7`
- name: `__imp_load_BCryptCreateHash`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001c05c`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x18001c0db`

## pseudocode

```c
__int64 load_BCryptCreateHash()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x18001c0db  lea     rax, __imp_BCryptCreateHash
0x18001c0e2  jmp     __tailMerge_bcrypt_dll
```
