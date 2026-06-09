# [thunk]:ATL::CComContainedObject<CGameExplorer>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x180002300`
- end: `0x180002309`
- name: `?QueryInterface@?$CComContainedObject@VCGameExplorer@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800022e0`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CGameExplorer>::QueryInterface(__int64 a1)
{
  return ATL::CComContainedObject<CGameExplorer>::QueryInterface(a1 - 8);
}

```

## disassembly

```asm
0x180002300  sub     rcx, 8
0x180002304  jmp     ?QueryInterface@?$CComContainedObject@VCGameExplorer@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComContainedObject<CGameExplorer>::QueryInterface(_GUID const &,void * *)
```
