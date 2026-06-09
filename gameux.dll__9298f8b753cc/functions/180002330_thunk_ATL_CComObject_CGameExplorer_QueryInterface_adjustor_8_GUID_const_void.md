# [thunk]:ATL::CComObject<CGameExplorer>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x180002330`
- end: `0x180002339`
- name: `?QueryInterface@?$CComObject@VCGameExplorer@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002310`

## pseudocode

```c
int __fastcall ATL::CComObject<CGameExplorer>::QueryInterface(__int64 a1, const struct _GUID *a2, void **a3)
{
  return ATL::CComObject<CGameExplorer>::QueryInterface((void *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x180002330  sub     rcx, 8
0x180002334  jmp     ?QueryInterface@?$CComObject@VCGameExplorer@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CGameExplorer>::QueryInterface(_GUID const &,void * *)
```
