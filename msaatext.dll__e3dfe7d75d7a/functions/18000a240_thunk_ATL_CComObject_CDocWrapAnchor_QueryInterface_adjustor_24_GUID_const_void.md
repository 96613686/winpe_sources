# [thunk]:ATL::CComObject<CDocWrapAnchor>::QueryInterface`adjustor{24}' (_GUID const &,void * *)

- ea: `0x18000a240`
- end: `0x18000a249`
- name: `?QueryInterface@?$CComObject@VCDocWrapAnchor@@@ATL@@WBI@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a200`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CDocWrapAnchor>::QueryInterface(__int64 a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObject<CDocWrapAnchor>::QueryInterface((char *)(a1 - 24), a2, a3);
}

```

## disassembly

```asm
0x18000a240  sub     rcx, 18h
0x18000a244  jmp     ?QueryInterface@?$CComObject@VCDocWrapAnchor@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CDocWrapAnchor>::QueryInterface(_GUID const &,void * *)
```
