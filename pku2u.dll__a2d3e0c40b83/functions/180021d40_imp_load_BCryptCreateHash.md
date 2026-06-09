# __imp_load_BCryptCreateHash

- ea: `0x180021d40`
- end: `0x180021d4c`
- name: `__imp_load_BCryptCreateHash`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180021caf`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x180021d40`

## pseudocode

```c
__int64 load_BCryptCreateHash()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x180021d40  lea     rax, __imp_BCryptCreateHash
0x180021d47  jmp     __tailMerge_bcrypt_dll
```
