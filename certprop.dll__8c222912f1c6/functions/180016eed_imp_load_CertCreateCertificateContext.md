# __imp_load_CertCreateCertificateContext

- ea: `0x180016eed`
- end: `0x180016ef9`
- name: `__imp_load_CertCreateCertificateContext`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180016b22`

## import_xrefs

- `CRYPT32!CertCreateCertificateContext` at `0x180016eed`

## pseudocode

```c
__int64 load_CertCreateCertificateContext()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x180016eed  lea     rax, __imp_CertCreateCertificateContext
0x180016ef4  jmp     __tailMerge_crypt32_dll
```
