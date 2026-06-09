# [thunk]:ATL::CComContainedObject<CMSDiscMasterObj>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x1800090f0`
- end: `0x1800090f9`
- name: `?QueryInterface@?$CComContainedObject@VCMSDiscMasterObj@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800090d0`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMSDiscMasterObj>::QueryInterface(__int64 a1)
{
  return ATL::CComContainedObject<CMSDiscMasterObj>::QueryInterface(a1 - 8);
}

```

## disassembly

```asm
0x1800090f0  sub     rcx, 8
0x1800090f4  jmp     ?QueryInterface@?$CComContainedObject@VCMSDiscMasterObj@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComContainedObject<CMSDiscMasterObj>::QueryInterface(_GUID const &,void * *)
```
