# ATL::IDispatchImpl<IMSMQPropertyBag,&_GUID const IID_IMSMQPropertyBag,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x18000eda0`
- end: `0x18000edff`
- name: `?Invoke@?$IDispatchImpl@UIMSMQPropertyBag@@$1?IID_IMSMQPropertyBag@@3U_GUID@@B$1?LIBID_MSMQTriggerObjects@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `95`
- prototype: `__int64 __fastcall(struct IDispatch *, int, __int64, const struct _GUID *, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000efc8`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IMSMQPropertyBag,&_GUID const IID_IMSMQPropertyBag,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>::Invoke(
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
           (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IMSMQPropertyBag,&_GUID const IID_IMSMQPropertyBag,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>::_tih,
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
0x18000eda0  mov     r11, rsp
0x18000eda3  sub     rsp, 58h
0x18000eda7  mov     rax, [rsp+58h+arg_40]
0x18000edaf  mov     r8d, edx; int
0x18000edb2  mov     [r11-10h], rax
0x18000edb6  mov     rdx, rcx; struct IDispatch *
0x18000edb9  mov     rax, [rsp+58h+arg_38]
0x18000edc1  lea     rcx, ?_tih@?$IDispatchImpl@UIMSMQPropertyBag@@$1?IID_IMSMQPropertyBag@@3U_GUID@@B$1?LIBID_MSMQTriggerObjects@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x18000edc8  mov     [r11-18h], rax
0x18000edcc  mov     rax, [rsp+58h+arg_30]
0x18000edd4  mov     [r11-20h], rax
0x18000edd8  mov     rax, [rsp+58h+arg_28]
0x18000ede0  mov     [r11-28h], rax
0x18000ede4  movzx   eax, [rsp+58h+arg_20]
0x18000edec  mov     [rsp+58h+var_30], ax; unsigned __int16
0x18000edf1  mov     [r11-38h], r9d
0x18000edf5  call    ?Invoke@CComTypeInfoHolder@ATL@@QEAAJPEAUIDispatch@@JAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z; ATL::CComTypeInfoHolder::Invoke(IDispatch *,long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)
0x18000edfa  add     rsp, 58h
0x18000edfe  retn
```
