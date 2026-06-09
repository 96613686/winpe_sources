# [thunk]:ATL::CComObject<CCertEncodeCRLDistInfo>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x180007210`
- end: `0x180007219`
- name: `?QueryInterface@?$CComObject@VCCertEncodeCRLDistInfo@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800071f0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCertEncodeCRLDistInfo>::QueryInterface(__int64 a1, __int64 a2, __int64 a3)
{
  return ATL::CComObject<CCertEncodeCRLDistInfo>::QueryInterface(a1 - 8, a2, a3);
}

```

## disassembly

```asm
0x180007210  sub     rcx, 8
0x180007214  jmp     ?QueryInterface@?$CComObject@VCCertEncodeCRLDistInfo@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CCertEncodeCRLDistInfo>::QueryInterface(_GUID const &,void * *)
```
