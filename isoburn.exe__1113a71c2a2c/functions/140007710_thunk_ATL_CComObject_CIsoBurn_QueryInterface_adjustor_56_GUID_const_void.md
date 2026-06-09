# [thunk]:ATL::CComObject<CIsoBurn>::QueryInterface`adjustor{56}' (_GUID const &,void * *)

- ea: `0x140007710`
- end: `0x140007719`
- name: `?QueryInterface@?$CComObject@VCIsoBurn@@@ATL@@WDI@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400076f0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CIsoBurn>::QueryInterface(__int64 a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObject<CIsoBurn>::QueryInterface((char *)(a1 - 56), a2, a3);
}

```

## disassembly

```asm
0x140007710  sub     rcx, 38h ; '8'
0x140007714  jmp     ?QueryInterface@?$CComObject@VCIsoBurn@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CIsoBurn>::QueryInterface(_GUID const &,void * *)
```
