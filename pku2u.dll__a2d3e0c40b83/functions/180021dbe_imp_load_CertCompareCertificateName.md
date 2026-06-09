# __imp_load_CertCompareCertificateName

- ea: `0x180021dbe`
- end: `0x180021dca`
- name: `__imp_load_CertCompareCertificateName`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180021af7`

## import_xrefs

- `CRYPT32!CertCompareCertificateName` at `0x180021dbe`

## pseudocode

```c
__int64 load_CertCompareCertificateName()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x180021dbe  lea     rax, __imp_CertCompareCertificateName
0x180021dc5  jmp     __tailMerge_crypt32_dll
```
