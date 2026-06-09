# [thunk]:ATL::CComObject<CDocWrapACP>::QueryInterface`adjustor{72}' (_GUID const &,void * *)

- ea: `0x18000a1f0`
- end: `0x18000a1f9`
- name: `?QueryInterface@?$CComObject@VCDocWrapACP@@@ATL@@WEI@EAAJAEBU_GUID@@PEAPEAX@Z`
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
  return ATL::CComObject<CDocWrapACP>::QueryInterface((char *)(a1 - 72), a2, a3);
}

```

## disassembly

```asm
0x18000a1f0  sub     rcx, 48h ; 'H'
0x18000a1f4  jmp     ?QueryInterface@?$CComObject@VCDocWrapACP@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CDocWrapACP>::QueryInterface(_GUID const &,void * *)
```
