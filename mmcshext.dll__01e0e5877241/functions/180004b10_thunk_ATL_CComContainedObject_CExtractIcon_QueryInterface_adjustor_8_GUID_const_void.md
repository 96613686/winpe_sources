# [thunk]:ATL::CComContainedObject<CExtractIcon>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x180004b10`
- end: `0x180004b19`
- name: `?QueryInterface@?$CComContainedObject@VCExtractIcon@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004ab0`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CExtractIcon>::QueryInterface(__int64 a1, struct _GUID *a2, char **a3)
{
  return ATL::CComContainedObject<CExtractIcon>::QueryInterface((char *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x180004b10  sub     rcx, 8; void *
0x180004b14  jmp     ?QueryInterface@?$CComContainedObject@VCExtractIcon@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComContainedObject<CExtractIcon>::QueryInterface(_GUID const &,void * *)
```
