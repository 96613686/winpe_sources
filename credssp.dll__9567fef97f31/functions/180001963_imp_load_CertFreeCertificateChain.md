# __imp_load_CertFreeCertificateChain

- ea: `0x180001963`
- end: `0x18000196f`
- name: `__imp_load_CertFreeCertificateChain`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800018c0`

## import_xrefs

- `CRYPT32!CertFreeCertificateChain` at `0x180001963`

## pseudocode

```c
__int64 __fastcall load_CertFreeCertificateChain(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_crypt32_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001963  lea     rax, __imp_CertFreeCertificateChain
0x18000196a  jmp     __tailMerge_crypt32_dll
```
