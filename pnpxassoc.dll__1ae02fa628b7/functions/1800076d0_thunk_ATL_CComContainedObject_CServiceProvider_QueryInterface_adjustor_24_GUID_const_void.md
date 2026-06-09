# [thunk]:ATL::CComContainedObject<CServiceProvider>::QueryInterface`adjustor{24}' (_GUID const &,void * *)

- ea: `0x1800076d0`
- end: `0x1800076d9`
- name: `?QueryInterface@?$CComContainedObject@VCServiceProvider@@@ATL@@WBI@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180007690`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CServiceProvider>::QueryInterface(__int64 a1)
{
  return ATL::CComContainedObject<CServiceProvider>::QueryInterface(a1 - 24);
}

```

## disassembly

```asm
0x1800076d0  sub     rcx, 18h
0x1800076d4  jmp     ?QueryInterface@?$CComContainedObject@VCServiceProvider@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComContainedObject<CServiceProvider>::QueryInterface(_GUID const &,void * *)
```
