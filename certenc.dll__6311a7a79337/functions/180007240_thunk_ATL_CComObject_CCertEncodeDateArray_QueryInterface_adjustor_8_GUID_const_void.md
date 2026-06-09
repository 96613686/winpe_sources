# [thunk]:ATL::CComObject<CCertEncodeDateArray>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x180007240`
- end: `0x180007249`
- name: `?QueryInterface@?$CComObject@VCCertEncodeDateArray@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007220`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCertEncodeDateArray>::QueryInterface(__int64 a1, __int64 a2, __int64 a3)
{
  return ATL::CComObject<CCertEncodeDateArray>::QueryInterface(a1 - 8, a2, a3);
}

```

## disassembly

```asm
0x180007240  sub     rcx, 8
0x180007244  jmp     ?QueryInterface@?$CComObject@VCCertEncodeDateArray@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CCertEncodeDateArray>::QueryInterface(_GUID const &,void * *)
```
