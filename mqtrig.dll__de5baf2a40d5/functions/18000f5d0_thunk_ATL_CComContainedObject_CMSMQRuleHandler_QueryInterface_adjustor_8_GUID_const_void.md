# [thunk]:ATL::CComContainedObject<CMSMQRuleHandler>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x18000f5d0`
- end: `0x18000f5d9`
- name: `?QueryInterface@?$CComContainedObject@VCMSMQRuleHandler@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000f560`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMSMQRuleHandler>::QueryInterface(__int64 a1, __int64 a2, __int64 a3)
{
  return ATL::CComContainedObject<CMSMQRuleHandler>::QueryInterface(a1 - 8, a2, a3);
}

```

## disassembly

```asm
0x18000f5d0  sub     rcx, 8
0x18000f5d4  jmp     ?QueryInterface@?$CComContainedObject@VCMSMQRuleHandler@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComContainedObject<CMSMQRuleHandler>::QueryInterface(_GUID const &,void * *)
```
