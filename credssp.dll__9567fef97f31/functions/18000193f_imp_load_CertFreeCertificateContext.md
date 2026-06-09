# __imp_load_CertFreeCertificateContext

- ea: `0x18000193f`
- end: `0x18000194b`
- name: `__imp_load_CertFreeCertificateContext`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800018c0`

## import_xrefs

- `CRYPT32!CertFreeCertificateContext` at `0x18000193f`

## pseudocode

```c
__int64 __fastcall load_CertFreeCertificateContext(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_crypt32_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000193f  lea     rax, __imp_CertFreeCertificateContext
0x180001946  jmp     __tailMerge_crypt32_dll
```
