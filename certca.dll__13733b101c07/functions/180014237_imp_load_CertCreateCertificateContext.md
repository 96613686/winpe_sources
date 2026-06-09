# __imp_load_CertCreateCertificateContext

- ea: `0x180014237`
- end: `0x180014243`
- name: `__imp_load_CertCreateCertificateContext`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001408b`

## import_xrefs

- `CRYPT32!CertCreateCertificateContext` at `0x180014237`

## pseudocode

```c
__int64 load_CertCreateCertificateContext()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x180014237  lea     rax, __imp_CertCreateCertificateContext
0x18001423e  jmp     __tailMerge_crypt32_dll
```
