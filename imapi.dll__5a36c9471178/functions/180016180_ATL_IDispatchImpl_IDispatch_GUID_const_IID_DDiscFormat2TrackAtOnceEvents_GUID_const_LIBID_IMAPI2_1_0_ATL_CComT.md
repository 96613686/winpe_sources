# ATL::IDispatchImpl<IDispatch,&_GUID const IID_DDiscFormat2TrackAtOnceEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x180016180`
- end: `0x18001621b`
- name: `?Invoke@?$IDispatchImpl@UIDispatch@@$1?IID_DDiscFormat2TrackAtOnceEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180015bd8`
- `0x180016180`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IDispatch,&_GUID const IID_DDiscFormat2TrackAtOnceEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::Invoke(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        LCID a4,
        unsigned __int16 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  __int64 v11; // rcx
  __int64 result; // rax

  v11 = qword_1800212A8;
  if ( !qword_1800212A8 || (result = 0, !qword_1800212B8) )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IDispatch,&_GUID const IID_DDiscFormat2TrackAtOnceEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::_tih,
               a4);
    v11 = qword_1800212A8;
  }
  if ( v11 )
    return (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, __int64, __int64, __int64, __int64))(*(_QWORD *)v11 + 88LL))(
             v11,
             a1,
             a2,
             a5,
             a6,
             a7,
             a8,
             a9);
  return result;
}

```

## disassembly

```asm
0x180016180  mov     [rsp+arg_0], rbx
0x180016185  push    rdi
0x180016186  sub     rsp, 50h
0x18001618a  mov     rdi, rcx
0x18001618d  mov     ebx, edx
0x18001618f  mov     rcx, cs:qword_1800212A8
0x180016196  test    rcx, rcx
0x180016199  jz      short loc_1800161A6
0x18001619b  xor     eax, eax
0x18001619d  cmp     cs:qword_1800212B8, rax
0x1800161a4  jnz     short loc_1800161BC
0x1800161a6  mov     edx, r9d; lcid
0x1800161a9  lea     rcx, ?_tih@?$IDispatchImpl@UIDispatch@@$1?IID_DDiscFormat2TrackAtOnceEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x1800161b0  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x1800161b5  mov     rcx, cs:qword_1800212A8
0x1800161bc  test    rcx, rcx
0x1800161bf  jz      short loc_180016210
0x1800161c1  mov     rdx, [rsp+58h+arg_40]
0x1800161c9  mov     r8d, ebx
0x1800161cc  mov     rax, [rcx]
0x1800161cf  movzx   r9d, [rsp+58h+arg_20]
0x1800161d8  mov     [rsp+58h+var_20], rdx
0x1800161dd  mov     rdx, [rsp+58h+arg_38]
0x1800161e5  mov     rax, [rax+58h]
0x1800161e9  mov     [rsp+58h+var_28], rdx
0x1800161ee  mov     rdx, [rsp+58h+arg_30]
0x1800161f6  mov     [rsp+58h+var_30], rdx
0x1800161fb  mov     rdx, [rsp+58h+arg_28]
0x180016203  mov     [rsp+58h+var_38], rdx
0x180016208  mov     rdx, rdi
0x18001620b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016210  mov     rbx, [rsp+58h+arg_0]
0x180016215  add     rsp, 50h
0x180016219  pop     rdi
0x18001621a  retn
```
