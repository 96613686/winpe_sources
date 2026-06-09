# [thunk]:ATL::CComObject<CDocWrapACP>::QueryInterface`adjustor{24}' (_GUID const &,void * *)

- ea: `0x18000a1c0`
- end: `0x18000a1c9`
- name: `?QueryInterface@?$CComObject@VCDocWrapACP@@@ATL@@WBI@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a180`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CDocWrapACP>::QueryInterface(__int64 a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObject<CDocWrapACP>::QueryInterface((char *)(a1 - 24), a2, a3);
}

```

## disassembly

```asm
0x18000a1c0  sub     rcx, 18h
0x18000a1c4  jmp     ?QueryInterface@?$CComObject@VCDocWrapACP@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CDocWrapACP>::QueryInterface(_GUID const &,void * *)
```
