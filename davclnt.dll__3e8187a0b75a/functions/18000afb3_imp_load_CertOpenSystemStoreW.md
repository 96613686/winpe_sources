# __imp_load_CertOpenSystemStoreW

- ea: `0x18000afb3`
- end: `0x18000afbf`
- name: `__imp_load_CertOpenSystemStoreW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000aeec`

## import_xrefs

- `CRYPT32!CertOpenSystemStoreW` at `0x18000afb3`

## pseudocode

```c
__int64 load_CertOpenSystemStoreW()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x18000afb3  lea     rax, __imp_CertOpenSystemStoreW
0x18000afba  jmp     __tailMerge_crypt32_dll
```
