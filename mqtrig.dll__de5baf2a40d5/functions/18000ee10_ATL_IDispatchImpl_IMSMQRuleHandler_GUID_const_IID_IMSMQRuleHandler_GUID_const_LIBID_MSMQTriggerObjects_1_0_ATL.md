# ATL::IDispatchImpl<IMSMQRuleHandler,&_GUID const IID_IMSMQRuleHandler,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x18000ee10`
- end: `0x18000ee6f`
- name: `?Invoke@?$IDispatchImpl@UIMSMQRuleHandler@@$1?IID_IMSMQRuleHandler@@3U_GUID@@B$1?LIBID_MSMQTriggerObjects@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `95`
- prototype: `__int64 __fastcall(struct IDispatch *, int, __int64, const struct _GUID *, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000efc8`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IMSMQRuleHandler,&_GUID const IID_IMSMQRuleHandler,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>::Invoke(
        struct IDispatch *a1,
        int a2,
        __int64 a3,
        const struct _GUID *a4,
        unsigned __int16 a5,
        struct tagDISPPARAMS *a6,
        struct tagVARIANT *a7,
        struct tagEXCEPINFO *a8,
        unsigned int *a9)
{
  return ATL::CComTypeInfoHolder::Invoke(
           (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IMSMQRuleHandler,&_GUID const IID_IMSMQRuleHandler,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>::_tih,
           a1,
           a2,
           a4,
           (LCID)a4,
           a5,
           a6,
           a7,
           a8,
           a9);
}

```

## disassembly

```asm
0x18000ee10  mov     r11, rsp
0x18000ee13  sub     rsp, 58h
0x18000ee17  mov     rax, [rsp+58h+arg_40]
0x18000ee1f  mov     r8d, edx; int
0x18000ee22  mov     [r11-10h], rax
0x18000ee26  mov     rdx, rcx; struct IDispatch *
0x18000ee29  mov     rax, [rsp+58h+arg_38]
0x18000ee31  lea     rcx, ?_tih@?$IDispatchImpl@UIMSMQRuleHandler@@$1?IID_IMSMQRuleHandler@@3U_GUID@@B$1?LIBID_MSMQTriggerObjects@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x18000ee38  mov     [r11-18h], rax
0x18000ee3c  mov     rax, [rsp+58h+arg_30]
0x18000ee44  mov     [r11-20h], rax
0x18000ee48  mov     rax, [rsp+58h+arg_28]
0x18000ee50  mov     [r11-28h], rax
0x18000ee54  movzx   eax, [rsp+58h+arg_20]
0x18000ee5c  mov     [rsp+58h+var_30], ax; unsigned __int16
0x18000ee61  mov     [r11-38h], r9d
0x18000ee65  call    ?Invoke@CComTypeInfoHolder@ATL@@QEAAJPEAUIDispatch@@JAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z; ATL::CComTypeInfoHolder::Invoke(IDispatch *,long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)
0x18000ee6a  add     rsp, 58h
0x18000ee6e  retn
```
