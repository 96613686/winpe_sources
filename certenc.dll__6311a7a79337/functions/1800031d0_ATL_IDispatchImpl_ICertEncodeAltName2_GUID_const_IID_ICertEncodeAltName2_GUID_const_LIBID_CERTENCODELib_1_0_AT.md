# ATL::IDispatchImpl<ICertEncodeAltName2,&_GUID const IID_ICertEncodeAltName2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x1800031d0`
- end: `0x18000322f`
- name: `?Invoke@?$IDispatchImpl@UICertEncodeAltName2@@$1?IID_ICertEncodeAltName2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `95`
- prototype: `__int64 __usercall@<rax>(struct IDispatch *@<rcx>, int@<edx>, __int16, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180004488`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<ICertEncodeAltName2,&_GUID const IID_ICertEncodeAltName2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>::Invoke(
        struct IDispatch *a1,
        unsigned int a2,
        __int64 a3,
        struct ITypeInfo *a4,
        unsigned __int16 a5,
        struct tagDISPPARAMS *a6,
        struct tagVARIANT *a7,
        struct tagEXCEPINFO *a8,
        unsigned int *a9)
{
  return ATL::CComTypeInfoHolder::Invoke(
           (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<ICertEncodeAltName2,&_GUID const IID_ICertEncodeAltName2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>::_tih,
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
0x1800031d0  mov     r11, rsp
0x1800031d3  sub     rsp, 58h
0x1800031d7  mov     rax, [rsp+58h+arg_40]
0x1800031df  mov     r8d, edx; int
0x1800031e2  mov     [r11-10h], rax
0x1800031e6  mov     rdx, rcx; struct IDispatch *
0x1800031e9  mov     rax, [rsp+58h+arg_38]
0x1800031f1  lea     rcx, ?_tih@?$IDispatchImpl@UICertEncodeAltName2@@$1?IID_ICertEncodeAltName2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x1800031f8  mov     [r11-18h], rax
0x1800031fc  mov     rax, [rsp+58h+arg_30]
0x180003204  mov     [r11-20h], rax
0x180003208  mov     rax, [rsp+58h+arg_28]
0x180003210  mov     [r11-28h], rax
0x180003214  movzx   eax, [rsp+58h+arg_20]
0x18000321c  mov     [rsp+58h+var_30], ax; unsigned __int16
0x180003221  mov     [r11-38h], r9d
0x180003225  call    ?Invoke@CComTypeInfoHolder@ATL@@QEAAJPEAUIDispatch@@JAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z; ATL::CComTypeInfoHolder::Invoke(IDispatch *,long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)
0x18000322a  add     rsp, 58h
0x18000322e  retn
```
