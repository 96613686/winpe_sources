# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CMSMQTriggerSet>>,ATL::CComCreator<ATL::CComAggObject<CMSMQTriggerSet>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000dee0`
- end: `0x18000deee`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCMSMQTriggerSet@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCMSMQTriggerSet@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000e0e4`
- `0x18000e488`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CMSMQTriggerSet>>,ATL::CComCreator<ATL::CComAggObject<CMSMQTriggerSet>>>::CreateInstance(
        __int64 a1)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CMSMQTriggerSet>>::CreateInstance();
  else
    return ATL::CComCreator<ATL::CComObject<CMSMQTriggerSet>>::CreateInstance();
}

```

## disassembly

```asm
0x18000dee0  test    rcx, rcx
0x18000dee3  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCMSMQTriggerSet@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CMSMQTriggerSet>>::CreateInstance(void *,_GUID const &,void * *)
0x18000dee9  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCMSMQTriggerSet@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CMSMQTriggerSet>>::CreateInstance(void *,_GUID const &,void * *)
```
