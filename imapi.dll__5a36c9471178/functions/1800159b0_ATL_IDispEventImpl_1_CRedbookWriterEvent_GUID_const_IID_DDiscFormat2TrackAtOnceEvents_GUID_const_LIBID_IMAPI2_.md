# ATL::IDispEventImpl<1,CRedbookWriterEvent,&_GUID const IID_DDiscFormat2TrackAtOnceEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::GetFuncInfoFromId(_GUID const &,long,ulong,ATL::_ATL_FUNC_INFO &)

- ea: `0x1800159b0`
- end: `0x180015aaf`
- name: `?GetFuncInfoFromId@?$IDispEventImpl@$00VCRedbookWriterEvent@@$1?IID_DDiscFormat2TrackAtOnceEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJAEBU_GUID@@JKAEAU_ATL_FUNC_INFO@2@@Z`
- size: `255`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800154a4`
- `0x1800159b0`
- `0x180015bd8`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::IDispEventImpl<1,CRedbookWriterEvent,&_GUID const IID_DDiscFormat2TrackAtOnceEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::GetFuncInfoFromId(
        __int64 a1,
        __int64 a2,
        int a3,
        LCID a4,
        struct ATL::_ATL_FUNC_INFO *a5)
{
  GUID v6; // xmm1
  struct ITypeInfo *v7; // rbx
  __int64 result; // rax
  const struct _GUID *v9; // rdx
  unsigned int v10; // r9d
  unsigned int FuncInfoFromId; // edi

  if ( off_1800212D8->Data1 == GUID_NULL.Data1
    && *(_DWORD *)&off_1800212D8->Data2 == *(_DWORD *)&GUID_NULL.Data2
    && *(_DWORD *)off_1800212D8->Data4 == *(_DWORD *)GUID_NULL.Data4
    && *(_DWORD *)&off_1800212D8->Data4[4] == *(_DWORD *)&GUID_NULL.Data4[4] )
  {
    ATL::IDispEventImpl<1,CRedbookWriterEvent,&_GUID const IID_DDiscFormat2TrackAtOnceEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::m_InnerLibid = *(GUID *)(a1 + 8);
    v6 = *(GUID *)(a1 + 24);
    off_1800212D8 = &ATL::IDispEventImpl<1,CRedbookWriterEvent,&_GUID const IID_DDiscFormat2TrackAtOnceEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::m_InnerLibid;
    ATL::IDispEventImpl<1,CRedbookWriterEvent,&_GUID const IID_DDiscFormat2TrackAtOnceEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::_tih = &ATL::IDispEventImpl<1,CRedbookWriterEvent,&_GUID const IID_DDiscFormat2TrackAtOnceEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::m_InnerIid;
    ATL::IDispEventImpl<1,CRedbookWriterEvent,&_GUID const IID_DDiscFormat2TrackAtOnceEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::m_InnerIid = v6;
    word_1800212E0 = *(_WORD *)(a1 + 40);
    word_1800212E2 = *(_WORD *)(a1 + 42);
  }
  v7 = qword_1800212E8;
  if ( qword_1800212E8
    || (result = ATL::CComTypeInfoHolder::GetTI(
                   (ATL::CComTypeInfoHolder *)&ATL::IDispEventImpl<1,CRedbookWriterEvent,&_GUID const IID_DDiscFormat2TrackAtOnceEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::_tih,
                   a4),
        (v7 = qword_1800212E8) != 0) )
  {
    ((void (__fastcall *)(struct ITypeInfo *))v7->lpVtbl->AddRef)(v7);
  }
  else if ( (int)result < 0 )
  {
    return result;
  }
  FuncInfoFromId = ATL::AtlGetFuncInfoFromId(v7, v9, a3, v10, a5);
  if ( v7 )
    ((void (__fastcall *)(struct ITypeInfo *))v7->lpVtbl->Release)(v7);
  return FuncInfoFromId;
}

```

## disassembly

```asm
0x1800159b0  mov     [rsp+arg_0], rbx
0x1800159b5  push    rdi
0x1800159b6  sub     rsp, 30h
0x1800159ba  mov     rdx, cs:off_1800212D8
0x1800159c1  mov     edi, r8d
0x1800159c4  mov     eax, cs:GUID_NULL.Data1
0x1800159ca  cmp     [rdx], eax
0x1800159cc  jnz     short loc_180015A39
0x1800159ce  mov     eax, dword ptr cs:GUID_NULL.Data2
0x1800159d4  cmp     [rdx+4], eax
0x1800159d7  jnz     short loc_180015A39
0x1800159d9  mov     eax, dword ptr cs:GUID_NULL.Data4
0x1800159df  cmp     [rdx+8], eax
0x1800159e2  jnz     short loc_180015A39
0x1800159e4  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x1800159ea  cmp     [rdx+0Ch], eax
0x1800159ed  jnz     short loc_180015A39
0x1800159ef  movups  xmm0, xmmword ptr [rcx+8]
0x1800159f3  lea     rax, ?m_InnerLibid@?$IDispEventImpl@$00VCRedbookWriterEvent@@$1?IID_DDiscFormat2TrackAtOnceEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1U_GUID@@A; _GUID ATL::IDispEventImpl<1,CRedbookWriterEvent,&_GUID const IID_DDiscFormat2TrackAtOnceEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::m_InnerLibid
0x1800159fa  movdqu  xmmword ptr cs:?m_InnerLibid@?$IDispEventImpl@$00VCRedbookWriterEvent@@$1?IID_DDiscFormat2TrackAtOnceEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1U_GUID@@A.Data1, xmm0; _GUID ATL::IDispEventImpl<1,CRedbookWriterEvent,&_GUID const IID_DDiscFormat2TrackAtOnceEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::m_InnerLibid ...
0x180015a02  movups  xmm1, xmmword ptr [rcx+18h]
0x180015a06  mov     cs:off_1800212D8, rax
0x180015a0d  lea     rax, ?m_InnerIid@?$IDispEventImpl@$00VCRedbookWriterEvent@@$1?IID_DDiscFormat2TrackAtOnceEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1U_GUID@@A; _GUID ATL::IDispEventImpl<1,CRedbookWriterEvent,&_GUID const IID_DDiscFormat2TrackAtOnceEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::m_InnerIid
0x180015a14  mov     cs:?_tih@?$IDispEventImpl@$00VCRedbookWriterEvent@@$1?IID_DDiscFormat2TrackAtOnceEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A, rax; ATL::CComTypeInfoHolder ATL::IDispEventImpl<1,CRedbookWriterEvent,&_GUID const IID_DDiscFormat2TrackAtOnceEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::_tih
0x180015a1b  movdqu  xmmword ptr cs:?m_InnerIid@?$IDispEventImpl@$00VCRedbookWriterEvent@@$1?IID_DDiscFormat2TrackAtOnceEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1U_GUID@@A.Data1, xmm1; _GUID ATL::IDispEventImpl<1,CRedbookWriterEvent,&_GUID const IID_DDiscFormat2TrackAtOnceEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::m_InnerIid ...
0x180015a23  movzx   eax, word ptr [rcx+28h]
0x180015a27  mov     cs:word_1800212E0, ax
0x180015a2e  movzx   eax, word ptr [rcx+2Ah]
0x180015a32  mov     cs:word_1800212E2, ax
0x180015a39  mov     rbx, cs:qword_1800212E8
0x180015a40  xor     eax, eax
0x180015a42  test    rbx, rbx
0x180015a45  jnz     short loc_180015A62
0x180015a47  mov     edx, r9d; lcid
0x180015a4a  lea     rcx, ?_tih@?$IDispEventImpl@$00VCRedbookWriterEvent@@$1?IID_DDiscFormat2TrackAtOnceEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x180015a51  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x180015a56  mov     rbx, cs:qword_1800212E8
0x180015a5d  test    rbx, rbx
0x180015a60  jz      short loc_180015A73
0x180015a62  mov     rax, [rbx]
0x180015a65  mov     rcx, rbx
0x180015a68  mov     rax, [rax+8]
0x180015a6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a71  jmp     short loc_180015A77
0x180015a73  test    eax, eax
0x180015a75  js      short loc_180015AA4
0x180015a77  mov     rax, [rsp+38h+arg_20]
0x180015a7c  mov     r8d, edi; int
0x180015a7f  mov     rcx, rbx; struct ITypeInfo *
0x180015a82  mov     [rsp+38h+var_18], rax; struct ATL::_ATL_FUNC_INFO *
0x180015a87  call    ?AtlGetFuncInfoFromId@ATL@@YAJPEAUITypeInfo@@AEBU_GUID@@JKAEAU_ATL_FUNC_INFO@1@@Z; ATL::AtlGetFuncInfoFromId(ITypeInfo *,_GUID const &,long,ulong,ATL::_ATL_FUNC_INFO &)
0x180015a8c  mov     edi, eax
0x180015a8e  test    rbx, rbx
0x180015a91  jz      short loc_180015AA2
0x180015a93  mov     rcx, [rbx]
0x180015a96  mov     rax, [rcx+10h]
0x180015a9a  mov     rcx, rbx
0x180015a9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015aa2  mov     eax, edi
0x180015aa4  mov     rbx, [rsp+38h+arg_0]
0x180015aa9  add     rsp, 30h
0x180015aad  pop     rdi
0x180015aae  retn
```
