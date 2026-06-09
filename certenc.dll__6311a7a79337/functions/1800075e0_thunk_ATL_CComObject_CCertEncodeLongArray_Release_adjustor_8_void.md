# [thunk]:ATL::CComObject<CCertEncodeLongArray>::Release`adjustor{8}' (void)

- ea: `0x1800075e0`
- end: `0x1800075e9`
- name: `?Release@?$CComObject@VCCertEncodeLongArray@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007550`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCertEncodeLongArray>::Release(__int64 a1)
{
  return ATL::CComObject<CCertEncodeLongArray>::Release((CCertEncodeLongArray *)(a1 - 8));
}

```

## disassembly

```asm
0x1800075e0  sub     rcx, 8; this
0x1800075e4  jmp     ?Release@?$CComObject@VCCertEncodeLongArray@@@ATL@@UEAAKXZ; ATL::CComObject<CCertEncodeLongArray>::Release(void)
```
