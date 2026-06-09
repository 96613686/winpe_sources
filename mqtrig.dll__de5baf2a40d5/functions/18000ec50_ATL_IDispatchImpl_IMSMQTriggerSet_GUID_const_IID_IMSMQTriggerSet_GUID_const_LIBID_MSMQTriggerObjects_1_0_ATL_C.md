# ATL::IDispatchImpl<IMSMQTriggerSet,&_GUID const IID_IMSMQTriggerSet,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x18000ec50`
- end: `0x18000ec5c`
- name: `?GetTypeInfo@?$IDispatchImpl@UIMSMQTriggerSet@@$1?IID_IMSMQTriggerSet@@3U_GUID@@B$1?LIBID_MSMQTriggerObjects@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `12`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, struct ITypeInfo **)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000ec84`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IMSMQTriggerSet,&_GUID const IID_IMSMQTriggerSet,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        struct ITypeInfo **a4)
{
  return ATL::CComTypeInfoHolder::GetTypeInfo(
           (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IMSMQTriggerSet,&_GUID const IID_IMSMQTriggerSet,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>::_tih,
           a2,
           a3,
           a4);
}

```

## disassembly

```asm
0x18000ec50  lea     rcx, ?_tih@?$IDispatchImpl@UIMSMQTriggerSet@@$1?IID_IMSMQTriggerSet@@3U_GUID@@B$1?LIBID_MSMQTriggerObjects@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x18000ec57  jmp     ?GetTypeInfo@CComTypeInfoHolder@ATL@@QEAAJIKPEAPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::GetTypeInfo(uint,ulong,ITypeInfo * *)
```
