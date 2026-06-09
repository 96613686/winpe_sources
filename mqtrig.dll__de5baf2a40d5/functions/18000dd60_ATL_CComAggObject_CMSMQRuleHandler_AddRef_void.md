# ATL::CComAggObject<CMSMQRuleHandler>::AddRef(void)

- ea: `0x18000dd60`
- end: `0x18000dd69`
- name: `?AddRef@?$CComAggObject@VCMSMQRuleHandler@@@ATL@@UEAAKXZ`
- size: `9`
- prototype: `unsigned int __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000fb0c`

## pseudocode

```c
unsigned int __fastcall ATL::CComAggObject<CMSMQRuleHandler>::AddRef(__int64 a1)
{
  return ATL::SafeIncrementReferenceMultiThread((volatile int *)(a1 + 8));
}

```

## disassembly

```asm
0x18000dd60  add     rcx, 8; volatile int *
0x18000dd64  jmp     ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
```
