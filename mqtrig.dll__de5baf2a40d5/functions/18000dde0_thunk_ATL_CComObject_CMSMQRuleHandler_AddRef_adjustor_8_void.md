# [thunk]:ATL::CComObject<CMSMQRuleHandler>::AddRef`adjustor{8}' (void)

- ea: `0x18000dde0`
- end: `0x18000dde9`
- name: `?AddRef@?$CComObject@VCMSMQRuleHandler@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000ddd0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMSMQRuleHandler>::AddRef(__int64 a1)
{
  return ATL::CComObject<CMSMQTriggerSet>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x18000dde0  sub     rcx, 8
0x18000dde4  jmp     ?AddRef@?$CComObject@VCMSMQTriggerSet@@@ATL@@UEAAKXZ; ATL::CComObject<CMSMQTriggerSet>::AddRef(void)
```
