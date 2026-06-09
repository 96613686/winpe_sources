# ATL::IDispatchImpl<IMSMQRuleHandler,&_GUID const IID_IMSMQRuleHandler,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>::GetIDsOfNames(_GUID const &,wchar_t * *,uint,ulong,long *)

- ea: `0x18000e920`
- end: `0x18000e92c`
- name: `?GetIDsOfNames@?$IDispatchImpl@UIMSMQRuleHandler@@$1?IID_IMSMQRuleHandler@@3U_GUID@@B$1?LIBID_MSMQTriggerObjects@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJAEBU_GUID@@PEAPEA_WIKPEAJ@Z`
- size: `12`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, wchar_t **, unsigned int, LCID, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000e994`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IMSMQRuleHandler,&_GUID const IID_IMSMQRuleHandler,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>::GetIDsOfNames(
        __int64 a1,
        const struct _GUID *a2,
        wchar_t **a3,
        unsigned int a4,
        LCID a5,
        int *a6)
{
  return ATL::CComTypeInfoHolder::GetIDsOfNames(
           (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IMSMQRuleHandler,&_GUID const IID_IMSMQRuleHandler,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>::_tih,
           a2,
           a3,
           a4,
           a5,
           a6);
}

```

## disassembly

```asm
0x18000e920  lea     rcx, ?_tih@?$IDispatchImpl@UIMSMQRuleHandler@@$1?IID_IMSMQRuleHandler@@3U_GUID@@B$1?LIBID_MSMQTriggerObjects@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x18000e927  jmp     ?GetIDsOfNames@CComTypeInfoHolder@ATL@@QEAAJAEBU_GUID@@PEAPEA_WIKPEAJ@Z; ATL::CComTypeInfoHolder::GetIDsOfNames(_GUID const &,wchar_t * *,uint,ulong,long *)
```
