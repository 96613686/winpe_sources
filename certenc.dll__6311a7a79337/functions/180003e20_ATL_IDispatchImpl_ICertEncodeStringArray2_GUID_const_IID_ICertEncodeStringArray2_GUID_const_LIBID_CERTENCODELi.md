# ATL::IDispatchImpl<ICertEncodeStringArray2,&_GUID const IID_ICertEncodeStringArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x180003e20`
- end: `0x180003e7f`
- name: `?Invoke@?$IDispatchImpl@UICertEncodeStringArray2@@$1?IID_ICertEncodeStringArray2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `95`
- prototype: `__int64 __usercall@<rax>(struct IDispatch *@<rcx>, int@<edx>, __int16, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180004488`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<ICertEncodeStringArray2,&_GUID const IID_ICertEncodeStringArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>::Invoke(
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
           (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<ICertEncodeStringArray2,&_GUID const IID_ICertEncodeStringArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>::_tih,
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
0x180003e20  mov     r11, rsp
0x180003e23  sub     rsp, 58h
0x180003e27  mov     rax, [rsp+58h+arg_40]
0x180003e2f  mov     r8d, edx; int
0x180003e32  mov     [r11-10h], rax
0x180003e36  mov     rdx, rcx; struct IDispatch *
0x180003e39  mov     rax, [rsp+58h+arg_38]
0x180003e41  lea     rcx, ?_tih@?$IDispatchImpl@UICertEncodeStringArray2@@$1?IID_ICertEncodeStringArray2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x180003e48  mov     [r11-18h], rax
0x180003e4c  mov     rax, [rsp+58h+arg_30]
0x180003e54  mov     [r11-20h], rax
0x180003e58  mov     rax, [rsp+58h+arg_28]
0x180003e60  mov     [r11-28h], rax
0x180003e64  movzx   eax, [rsp+58h+arg_20]
0x180003e6c  mov     [rsp+58h+var_30], ax; unsigned __int16
0x180003e71  mov     [r11-38h], r9d
0x180003e75  call    ?Invoke@CComTypeInfoHolder@ATL@@QEAAJPEAUIDispatch@@JAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z; ATL::CComTypeInfoHolder::Invoke(IDispatch *,long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)
0x180003e7a  add     rsp, 58h
0x180003e7e  retn
```
