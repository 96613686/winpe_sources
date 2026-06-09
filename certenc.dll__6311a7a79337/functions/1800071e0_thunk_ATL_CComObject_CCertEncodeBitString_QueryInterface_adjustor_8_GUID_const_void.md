# [thunk]:ATL::CComObject<CCertEncodeBitString>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x1800071e0`
- end: `0x1800071e9`
- name: `?QueryInterface@?$CComObject@VCCertEncodeBitString@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800071c0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCertEncodeBitString>::QueryInterface(__int64 a1, __int64 a2, __int64 a3)
{
  return ATL::CComObject<CCertEncodeBitString>::QueryInterface(a1 - 8, a2, a3);
}

```

## disassembly

```asm
0x1800071e0  sub     rcx, 8
0x1800071e4  jmp     ?QueryInterface@?$CComObject@VCCertEncodeBitString@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CCertEncodeBitString>::QueryInterface(_GUID const &,void * *)
```
