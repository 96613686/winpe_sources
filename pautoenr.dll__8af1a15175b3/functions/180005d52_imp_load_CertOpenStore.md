# __imp_load_CertOpenStore

- ea: `0x180005d52`
- end: `0x180005d5e`
- name: `__imp_load_CertOpenStore`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005caf`

## import_xrefs

- `CRYPT32!CertOpenStore` at `0x180005d52`

## pseudocode

```c
__int64 load_CertOpenStore()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x180005d52  lea     rax, __imp_CertOpenStore
0x180005d59  jmp     __tailMerge_crypt32_dll
```
