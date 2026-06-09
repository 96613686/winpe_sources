# [thunk]:ATL::CComContainedObject<CMSDiscRecorderObj>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x180007280`
- end: `0x180007289`
- name: `?QueryInterface@?$CComContainedObject@VCMSDiscRecorderObj@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007260`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMSDiscRecorderObj>::QueryInterface(__int64 a1)
{
  return ATL::CComContainedObject<CMSDiscRecorderObj>::QueryInterface(a1 - 8);
}

```

## disassembly

```asm
0x180007280  sub     rcx, 8
0x180007284  jmp     ?QueryInterface@?$CComContainedObject@VCMSDiscRecorderObj@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComContainedObject<CMSDiscRecorderObj>::QueryInterface(_GUID const &,void * *)
```
