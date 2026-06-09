# __imp_load_CertGetCertificateChain

- ea: `0x180001951`
- end: `0x18000195d`
- name: `__imp_load_CertGetCertificateChain`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800018c0`

## import_xrefs

- `CRYPT32!CertGetCertificateChain` at `0x180001951`

## pseudocode

```c
__int64 __fastcall load_CertGetCertificateChain(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_crypt32_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001951  lea     rax, __imp_CertGetCertificateChain
0x180001958  jmp     __tailMerge_crypt32_dll
```
