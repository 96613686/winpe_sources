# [thunk]:ATL::CComObject<CMSDiscMasterObj>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x180009140`
- end: `0x180009149`
- name: `?QueryInterface@?$CComObject@VCMSDiscMasterObj@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009120`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMSDiscMasterObj>::QueryInterface(__int64 a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObject<CMSDiscMasterObj>::QueryInterface((char *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x180009140  sub     rcx, 8
0x180009144  jmp     ?QueryInterface@?$CComObject@VCMSDiscMasterObj@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CMSDiscMasterObj>::QueryInterface(_GUID const &,void * *)
```
