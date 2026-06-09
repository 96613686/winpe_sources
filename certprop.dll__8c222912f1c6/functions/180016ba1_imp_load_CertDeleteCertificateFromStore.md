# __imp_load_CertDeleteCertificateFromStore

- ea: `0x180016ba1`
- end: `0x180016bad`
- name: `__imp_load_CertDeleteCertificateFromStore`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180016b22`

## import_xrefs

- `CRYPT32!CertDeleteCertificateFromStore` at `0x180016ba1`

## pseudocode

```c
__int64 load_CertDeleteCertificateFromStore()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x180016ba1  lea     rax, __imp_CertDeleteCertificateFromStore
0x180016ba8  jmp     __tailMerge_crypt32_dll
```
