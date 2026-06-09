# [thunk]:ATL::CComObject<CCertEncodeCRLDistInfo>::Release`adjustor{8}' (void)

- ea: `0x1800074a0`
- end: `0x1800074a9`
- name: `?Release@?$CComObject@VCCertEncodeCRLDistInfo@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007410`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCertEncodeCRLDistInfo>::Release(__int64 a1)
{
  return ATL::CComObject<CCertEncodeCRLDistInfo>::Release((CCertEncodeCRLDistInfo *)(a1 - 8));
}

```

## disassembly

```asm
0x1800074a0  sub     rcx, 8; this
0x1800074a4  jmp     ?Release@?$CComObject@VCCertEncodeCRLDistInfo@@@ATL@@UEAAKXZ; ATL::CComObject<CCertEncodeCRLDistInfo>::Release(void)
```
