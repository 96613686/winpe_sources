# [thunk]:ATL::CComContainedObject<CMSDiscMasterObj>::QueryInterface`adjustor{16}' (_GUID const &,void * *)

- ea: `0x180009100`
- end: `0x180009109`
- name: `?QueryInterface@?$CComContainedObject@VCMSDiscMasterObj@@@ATL@@WBA@EAAJAEBU_GUID@@PEAPEAX@Z`
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
  return ATL::CComContainedObject<CMSDiscMasterObj>::QueryInterface(a1 - 16);
}

```

## disassembly

```asm
0x180009100  sub     rcx, 10h
0x180009104  jmp     ?QueryInterface@?$CComContainedObject@VCMSDiscMasterObj@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComContainedObject<CMSDiscMasterObj>::QueryInterface(_GUID const &,void * *)
```
