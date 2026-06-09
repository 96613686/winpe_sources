# __imp_load_CertCreateCertificateContext

- ea: `0x180021e72`
- end: `0x180021e7e`
- name: `__imp_load_CertCreateCertificateContext`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180021af7`

## import_xrefs

- `CRYPT32!CertCreateCertificateContext` at `0x180021e72`

## pseudocode

```c
__int64 load_CertCreateCertificateContext()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x180021e72  lea     rax, __imp_CertCreateCertificateContext
0x180021e79  jmp     __tailMerge_crypt32_dll
```
