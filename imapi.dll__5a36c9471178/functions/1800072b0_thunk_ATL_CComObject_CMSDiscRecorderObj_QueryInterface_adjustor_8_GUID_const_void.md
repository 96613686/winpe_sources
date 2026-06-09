# [thunk]:ATL::CComObject<CMSDiscRecorderObj>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x1800072b0`
- end: `0x1800072b9`
- name: `?QueryInterface@?$CComObject@VCMSDiscRecorderObj@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007290`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMSDiscRecorderObj>::QueryInterface(__int64 a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObject<CMSDiscRecorderObj>::QueryInterface((char *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x1800072b0  sub     rcx, 8
0x1800072b4  jmp     ?QueryInterface@?$CComObject@VCMSDiscRecorderObj@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CMSDiscRecorderObj>::QueryInterface(_GUID const &,void * *)
```
