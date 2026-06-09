# [thunk]:ATL::CComObject<CCertEncodeBitString>::Release`adjustor{8}' (void)

- ea: `0x180007400`
- end: `0x180007409`
- name: `?Release@?$CComObject@VCCertEncodeBitString@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007370`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCertEncodeBitString>::Release(__int64 a1)
{
  return ATL::CComObject<CCertEncodeBitString>::Release((CCertEncodeBitString *)(a1 - 8));
}

```

## disassembly

```asm
0x180007400  sub     rcx, 8; this
0x180007404  jmp     ?Release@?$CComObject@VCCertEncodeBitString@@@ATL@@UEAAKXZ; ATL::CComObject<CCertEncodeBitString>::Release(void)
```
