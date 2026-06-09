# __imp_load_CertDeleteCertificateFromStore

- ea: `0x180005d9a`
- end: `0x180005da6`
- name: `__imp_load_CertDeleteCertificateFromStore`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005caf`

## import_xrefs

- `CRYPT32!CertDeleteCertificateFromStore` at `0x180005d9a`

## pseudocode

```c
__int64 load_CertDeleteCertificateFromStore()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x180005d9a  lea     rax, __imp_CertDeleteCertificateFromStore
0x180005da1  jmp     __tailMerge_crypt32_dll
```
