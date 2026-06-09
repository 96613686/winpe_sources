# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CMSMQPropertyBag>>,ATL::CComCreator<ATL::CComAggObject<CMSMQPropertyBag>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000de70`
- end: `0x18000de7e`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCMSMQPropertyBag@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCMSMQPropertyBag@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000df28`
- `0x18000e1cc`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CMSMQPropertyBag>>,ATL::CComCreator<ATL::CComAggObject<CMSMQPropertyBag>>>::CreateInstance(
        __int64 a1)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CMSMQPropertyBag>>::CreateInstance();
  else
    return ATL::CComCreator<ATL::CComObject<CMSMQPropertyBag>>::CreateInstance();
}

```

## disassembly

```asm
0x18000de70  test    rcx, rcx
0x18000de73  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCMSMQPropertyBag@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CMSMQPropertyBag>>::CreateInstance(void *,_GUID const &,void * *)
0x18000de79  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCMSMQPropertyBag@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CMSMQPropertyBag>>::CreateInstance(void *,_GUID const &,void * *)
```
