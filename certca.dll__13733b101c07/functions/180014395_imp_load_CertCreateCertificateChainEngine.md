# __imp_load_CertCreateCertificateChainEngine

- ea: `0x180014395`
- end: `0x1800143a1`
- name: `__imp_load_CertCreateCertificateChainEngine`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001408b`

## import_xrefs

- `CRYPT32!CertCreateCertificateChainEngine` at `0x180014395`

## pseudocode

```c
__int64 load_CertCreateCertificateChainEngine()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x180014395  lea     rax, __imp_CertCreateCertificateChainEngine
0x18001439c  jmp     __tailMerge_crypt32_dll
```
