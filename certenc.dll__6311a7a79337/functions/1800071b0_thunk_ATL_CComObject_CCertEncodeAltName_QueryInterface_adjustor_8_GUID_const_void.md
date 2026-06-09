# [thunk]:ATL::CComObject<CCertEncodeAltName>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x1800071b0`
- end: `0x1800071b9`
- name: `?QueryInterface@?$CComObject@VCCertEncodeAltName@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007190`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCertEncodeAltName>::QueryInterface(__int64 a1, __int64 a2, __int64 a3)
{
  return ATL::CComObject<CCertEncodeAltName>::QueryInterface(a1 - 8, a2, a3);
}

```

## disassembly

```asm
0x1800071b0  sub     rcx, 8
0x1800071b4  jmp     ?QueryInterface@?$CComObject@VCCertEncodeAltName@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CCertEncodeAltName>::QueryInterface(_GUID const &,void * *)
```
