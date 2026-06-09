# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CMSMQRuleHandler>>,ATL::CComCreator<ATL::CComAggObject<CMSMQRuleHandler>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000de90`
- end: `0x18000de9e`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCMSMQRuleHandler@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCMSMQRuleHandler@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000dffc`
- `0x18000e2a0`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CMSMQRuleHandler>>,ATL::CComCreator<ATL::CComAggObject<CMSMQRuleHandler>>>::CreateInstance(
        __int64 a1)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CMSMQRuleHandler>>::CreateInstance();
  else
    return ATL::CComCreator<ATL::CComObject<CMSMQRuleHandler>>::CreateInstance();
}

```

## disassembly

```asm
0x18000de90  test    rcx, rcx
0x18000de93  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCMSMQRuleHandler@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CMSMQRuleHandler>>::CreateInstance(void *,_GUID const &,void * *)
0x18000de99  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCMSMQRuleHandler@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CMSMQRuleHandler>>::CreateInstance(void *,_GUID const &,void * *)
```
