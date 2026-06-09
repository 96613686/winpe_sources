# [thunk]:ATL::CComObject<CMSDiscMasterObj>::QueryInterface`adjustor{120}' (_GUID const &,void * *)

- ea: `0x180009160`
- end: `0x180009169`
- name: `?QueryInterface@?$CComObject@VCMSDiscMasterObj@@@ATL@@WHI@EAAJAEBU_GUID@@PEAPEAX@Z`
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
  return ATL::CComObject<CMSDiscMasterObj>::QueryInterface((char *)(a1 - 120), a2, a3);
}

```

## disassembly

```asm
0x180009160  sub     rcx, 78h ; 'x'
0x180009164  jmp     ?QueryInterface@?$CComObject@VCMSDiscMasterObj@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CMSDiscMasterObj>::QueryInterface(_GUID const &,void * *)
```
