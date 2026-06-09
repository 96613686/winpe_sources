# Rdp::Avenc::Raw::CRawProcessor::Start(IUnknown *)

- ea: `0x18003bf80`
- end: `0x18003c354`
- name: `?Start@CRawProcessor@Raw@Avenc@Rdp@@UEAAJPEAUIUnknown@@@Z`
- size: `980`
- prototype: `__int64 __fastcall(Rdp::Avenc::Raw::CRawProcessor *__hidden this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800019f0`
- `0x18000e848`
- `0x18000ec04`
- `0x180011490`
- `0x180012580`
- `0x180012618`
- `0x1800126b0`
- `0x1800153f8`
- `0x180015480`
- `0x18003bf80`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003bfe4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c2f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003bfe4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c2f3`

## string_xrefs

- `0x18003c03e`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\common/ProcessorBase.h`
- `0x18003c103`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\common/ProcessorBase.h`
- `0x18003c14b`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\common/ProcessorBase.h`
- `0x18003c17f`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\common/ProcessorBase.h`
- `0x18003c341`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Rdp::Avenc::Raw::CRawProcessor::Start(Rdp::Avenc::Raw::CRawProcessor *this, struct IUnknown *a2)
{
  char v4; // bl
  bool v5; // si
  bool v6; // r14
  char CurrentThreadId; // al
  int v8; // r8d
  int v9; // edx
  Rdp::Utils::Props **v10; // rsi
  int v11; // eax
  struct _GUID *v12; // r9
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rdx
  unsigned int Guid; // eax
  unsigned int *v17; // r9
  unsigned int UInt32; // eax
  struct IPropertyStore *v19; // rdx
  struct _LUID *v20; // r9
  unsigned int Luid; // eax
  int v22; // r8d
  int v23; // r9d
  const char *v24; // r9
  bool v25; // di
  char v26; // al
  int v27; // r8d
  int v28; // edx
  __int64 result; // rax
  int v30; // [rsp+20h] [rbp-98h]
  int v31; // [rsp+20h] [rbp-98h]
  int v32; // [rsp+28h] [rbp-90h]
  char *v33; // [rsp+28h] [rbp-90h]
  char *v34; // [rsp+28h] [rbp-90h]
  int v35; // [rsp+28h] [rbp-90h]
  const char *v36; // [rsp+60h] [rbp-58h] BYREF
  int v37[2]; // [rsp+68h] [rbp-50h] BYREF
  struct _tagpropertykey v38; // [rsp+70h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  __int64 v40; // [rsp+C0h] [rbp+8h] BYREF
  __int64 v41; // [rsp+C8h] [rbp+10h] BYREF
  const char *v42; // [rsp+D0h] [rbp+18h] BYREF
  int *v43; // [rsp+D8h] [rbp+20h] BYREF

  v4 = 1;
  v5 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v6 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v8) = v6;
    LOBYTE(v9) = v5;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      v8,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v30,
      v32,
      10,
      &WPP_9fd2a530fe4f38971d9b2d15cc14ffcc_Traceguids,
      CurrentThreadId);
  }
  try
  {
    v10 = (Rdp::Utils::Props **)((char *)this + 32);
    wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(
      retaddr,
      196,
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      2147549183LL);
    v40 = 0;
    v11 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
            a2,
            &GUID_d446623d_bea3_4095_bb2e_25ff7e09a37a,
            &v40);
    if ( v11 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v11,
        (_DWORD)this + 32);
    v13 = v40;
    v14 = 0;
    v40 = 0;
    v15 = *((_QWORD *)this + 5);
    *((_QWORD *)this + 5) = v13;
    if ( v15 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      v14 = v40;
    }
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v38.fmtid = 0;
    Guid = Rdp::Utils::Props::IPropertyStore_GetGuid(*v10, (struct IPropertyStore *)&PKEY_Activity_Id, &v38, v12);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0xD1,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      (const char *)Guid,
      (int)"Failed to retrieve PKEY_Activity_Id property",
      "PropertyStore is not initialized");
    *(GUID *)&xmmword_1800C21A0 = v38.fmtid;
    UInt32 = Rdp::Utils::Props::IPropertyStore_GetUInt32(
               *v10,
               (struct IPropertyStore *)&PKEY_Session_Id,
               (const struct _tagpropertykey *)this + 4,
               v17);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0xDD,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      (const char *)UInt32,
      (int)"Failed to retrieve PKEY_Session_Id property",
      v33);
    Luid = Rdp::Utils::Props::IPropertyStore_GetLuid(
             *v10,
             v19,
             (const struct _tagpropertykey *)((char *)this + 72),
             v20);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0xE7,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      (const char *)Luid,
      (int)"Failed to retrieve PKEY_Terminal_Luid property",
      v34);
    *((_BYTE *)this + 176) = 1;
    if ( (unsigned int)dword_1800C1058 > 4
      && (qword_1800C1068 & 0x470000000000LL) != 0
      && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
    {
      v41 = *((_QWORD *)this + 9);
      LODWORD(v40) = *((_DWORD *)this + 20);
      v42 = "Start Raw processor";
      v43 = &xmmword_1800C21A0;
      v36 = "RdpAvenc";
      *(_QWORD *)v37 = 0x1000000;
      *(_QWORD *)&v38.fmtid.Data1 = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)&dword_1800AF80C,
        v22,
        v23,
        (__int64)&v38,
        (__int64)v37,
        (__int64)&v36,
        (__int64)&v43,
        (__int64)&v42,
        (__int64)&v40,
        (__int64)&v41);
    }
    Rdp::Modern::Utils::CInflightRecorder::pushN(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      (wchar_t *)L"RawProcessorStart",
      "Rdp::Avenc::Raw::CRawProcessor::Start",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rawprocessor\\rawprocessor.cpp",
      0x3Eu);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v4 = 0;
    }
    v25 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v26 = GetCurrentThreadId();
      LOBYTE(v27) = v25;
      LOBYTE(v28) = v4;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v28,
        v27,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v31,
        v35,
        11,
        &WPP_9fd2a530fe4f38971d9b2d15cc14ffcc_Traceguids,
        v26);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x43,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rawprocessor\\rawprocessor.cpp",
                           v24);
  }
  return result;
}

```

## disassembly

```asm
0x18003bf80  push    rbx
0x18003bf82  push    rsi
0x18003bf83  push    rdi
0x18003bf84  push    r12
0x18003bf86  push    r14
0x18003bf88  push    r15
0x18003bf8a  sub     rsp, 88h
0x18003bf91  mov     r15, rdx
0x18003bf94  mov     rdi, rcx
0x18003bf97  lea     rcx, WPP_GLOBAL_Control
0x18003bf9e  mov     rax, cs:WPP_GLOBAL_Control
0x18003bfa5  mov     bl, 1
0x18003bfa7  cmp     rax, rcx
0x18003bfaa  jz      short loc_18003BFBC
0x18003bfac  test    [rax+1Ch], bl
0x18003bfaf  jz      short loc_18003BFBC
0x18003bfb1  cmp     byte ptr [rax+19h], 4
0x18003bfb5  jb      short loc_18003BFBC
0x18003bfb7  mov     sil, bl
0x18003bfba  jmp     short loc_18003BFBF
0x18003bfbc  xor     sil, sil
0x18003bfbf  lea     rax, WPP_RECORDER_INITIALIZED
0x18003bfc6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003bfcd  setnz   r14b
0x18003bfd1  test    sil, sil
0x18003bfd4  jnz     short loc_18003BFE4
0x18003bfd6  test    r14b, r14b
0x18003bfd9  jnz     short loc_18003BFE4
0x18003bfdb  lea     r12, WPP_9fd2a530fe4f38971d9b2d15cc14ffcc_Traceguids
0x18003bfe2  jmp     short loc_18003C01B
0x18003bfe4  call    cs:__imp_GetCurrentThreadId
0x18003bfea  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x18003bfee  lea     r12, WPP_9fd2a530fe4f38971d9b2d15cc14ffcc_Traceguids
0x18003bff5  mov     [rsp+0B8h+MessageGuid], r12; MessageGuid
0x18003bffa  mov     [rsp+0B8h+var_88], 0Ah; __int16
0x18003c001  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c008  mov     r9, [rcx+28h]; int
0x18003c00c  mov     r8b, r14b; int
0x18003c00f  mov     dl, sil; int
0x18003c012  mov     rcx, [rcx+10h]; int
0x18003c016  call    WPP_RECORDER_AND_TRACE_SF_D
0x18003c01b  lea     rsi, [rdi+20h]
0x18003c01f  mov     rcx, [rsp+0B8h]
0x18003c027  lea     rax, aPropertystoreI; "PropertyStore is not initialized"
0x18003c02e  mov     [rsp+0B8h+var_90], rax; char *
0x18003c033  mov     qword ptr [rsp+0B8h+var_98], rsi; int
0x18003c038  mov     r9d, 8000FFFFh
0x18003c03e  lea     r8, aOnecoreuapTerm_44; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18003c045  mov     edx, 0C4h
0x18003c04a  call    ??$Throw_HrIfNullMsg@V?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDJAEBV?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@2@1ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(void *,uint,char const *,long,wil::com_ptr_t<IPropertyStore,wil::err_exception_policy> const &,char const *,...)
0x18003c04f  mov     [rsp+0B8h+arg_0], 0
0x18003c05b  mov     rax, [r15]
0x18003c05e  lea     r8, [rsp+0B8h+arg_0]
0x18003c066  lea     rdx, _GUID_d446623d_bea3_4095_bb2e_25ff7e09a37a
0x18003c06d  mov     rcx, r15
0x18003c070  mov     rax, [rax]
0x18003c073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c078  mov     rcx, [rsp+0B8h]; this
0x18003c080  test    eax, eax
0x18003c082  js      loc_18003C33E
0x18003c088  mov     rax, [rsp+0B8h+arg_0]
0x18003c090  xor     ecx, ecx
0x18003c092  mov     [rsp+0B8h+arg_0], rcx
0x18003c09a  mov     rdx, [rdi+28h]
0x18003c09e  mov     [rdi+28h], rax
0x18003c0a2  test    rdx, rdx
0x18003c0a5  jz      short loc_18003C0BE
0x18003c0a7  mov     rax, [rdx]
0x18003c0aa  mov     rcx, rdx
0x18003c0ad  mov     rax, [rax+10h]
0x18003c0b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c0b6  mov     rcx, [rsp+0B8h+arg_0]
0x18003c0be  test    rcx, rcx
0x18003c0c1  jz      short loc_18003C0D0
0x18003c0c3  mov     rax, [rcx]
0x18003c0c6  mov     rax, [rax+10h]
0x18003c0ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c0cf  nop
0x18003c0d0  xorps   xmm0, xmm0
0x18003c0d3  movups  xmmword ptr [rsp+0B8h+var_48.fmtid.Data1], xmm0
0x18003c0d8  lea     r8, [rsp+0B8h+var_48]; struct _tagpropertykey *
0x18003c0dd  lea     rdx, PKEY_Activity_Id; struct IPropertyStore *
0x18003c0e4  mov     rcx, [rsi]; this
0x18003c0e7  call    ?IPropertyStore_GetGuid@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAU_GUID@@@Z; Rdp::Utils::Props::IPropertyStore_GetGuid(IPropertyStore *,_tagpropertykey const &,_GUID *)
0x18003c0ec  mov     rcx, [rsp+0B8h]; this
0x18003c0f4  lea     rdx, aFailedToRetrie_17; "Failed to retrieve PKEY_Activity_Id pro"...
0x18003c0fb  mov     qword ptr [rsp+0B8h+var_98], rdx; int
0x18003c100  mov     r9d, eax; char *
0x18003c103  lea     r8, aOnecoreuapTerm_44; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18003c10a  mov     edx, 0D1h; void *
0x18003c10f  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003c114  movups  xmm0, xmmword ptr [rsp+0B8h+var_48.fmtid.Data1]
0x18003c119  movdqu  cs:xmmword_1800C21A0, xmm0
0x18003c121  lea     r8, [rdi+50h]; struct _tagpropertykey *
0x18003c125  lea     rdx, PKEY_Session_Id; struct IPropertyStore *
0x18003c12c  mov     rcx, [rsi]; this
0x18003c12f  call    ?IPropertyStore_GetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAI@Z; Rdp::Utils::Props::IPropertyStore_GetUInt32(IPropertyStore *,_tagpropertykey const &,uint *)
0x18003c134  mov     rcx, [rsp+0B8h]; this
0x18003c13c  lea     rdx, aFailedToRetrie_19; "Failed to retrieve PKEY_Session_Id prop"...
0x18003c143  mov     qword ptr [rsp+0B8h+var_98], rdx; int
0x18003c148  mov     r9d, eax; char *
0x18003c14b  lea     r8, aOnecoreuapTerm_44; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18003c152  mov     edx, 0DDh; void *
0x18003c157  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003c15c  lea     r8, [rdi+48h]; struct _tagpropertykey *
0x18003c160  mov     rcx, [rsi]; this
0x18003c163  call    ?IPropertyStore_GetLuid@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAU_LUID@@@Z; Rdp::Utils::Props::IPropertyStore_GetLuid(IPropertyStore *,_tagpropertykey const &,_LUID *)
0x18003c168  mov     rcx, [rsp+0B8h]; this
0x18003c170  lea     rdx, aFailedToRetrie_12; "Failed to retrieve PKEY_Terminal_Luid p"...
0x18003c177  mov     qword ptr [rsp+0B8h+var_98], rdx; int
0x18003c17c  mov     r9d, eax; char *
0x18003c17f  lea     r8, aOnecoreuapTerm_44; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18003c186  mov     edx, 0E7h; void *
0x18003c18b  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003c190  mov     [rdi+0B0h], bl
0x18003c196  mov     eax, cs:dword_1800C1058
0x18003c19c  cmp     eax, 4
0x18003c19f  jbe     loc_18003C28F
0x18003c1a5  mov     rcx, cs:qword_1800C1070
0x18003c1ac  mov     rax, cs:qword_1800C1068
0x18003c1b3  mov     rdx, 470000000000h
0x18003c1bd  test    rdx, rax
0x18003c1c0  jz      loc_18003C28F
0x18003c1c6  mov     rax, rcx
0x18003c1c9  and     rax, rdx
0x18003c1cc  cmp     rax, rcx
0x18003c1cf  jnz     loc_18003C28F
0x18003c1d5  mov     rax, [rdi+48h]
0x18003c1d9  mov     [rsp+0B8h+arg_8], rax
0x18003c1e1  mov     eax, [rdi+50h]
0x18003c1e4  mov     dword ptr [rsp+0B8h+arg_0], eax
0x18003c1eb  lea     rax, aStartRawProces; "Start Raw processor"
0x18003c1f2  mov     [rsp+0B8h+arg_10], rax
0x18003c1fa  lea     rax, xmmword_1800C21A0
0x18003c201  mov     [rsp+0B8h+arg_18], rax
0x18003c209  lea     rax, aRdpavenc; "RdpAvenc"
0x18003c210  mov     [rsp+0B8h+var_58], rax
0x18003c215  mov     qword ptr [rsp+0B8h+var_50], 1000000h
0x18003c21e  lea     rax, aCheckpoint; "Checkpoint"
0x18003c225  mov     qword ptr [rsp+0B8h+var_48.fmtid.Data1], rax
0x18003c22a  lea     rax, [rsp+0B8h+arg_8]
0x18003c232  mov     [rsp+0B8h+var_68], rax
0x18003c237  lea     rax, [rsp+0B8h+arg_0]
0x18003c23f  mov     [rsp+0B8h+var_70], rax
0x18003c244  lea     rax, [rsp+0B8h+arg_10]
0x18003c24c  mov     qword ptr [rsp+0B8h+var_78], rax
0x18003c251  lea     rax, [rsp+0B8h+arg_18]
0x18003c259  mov     [rsp+0B8h+MessageGuid], rax
0x18003c25e  lea     rax, [rsp+0B8h+var_58]
0x18003c263  mov     qword ptr [rsp+0B8h+var_88], rax
0x18003c268  lea     rax, [rsp+0B8h+var_50]
0x18003c26d  mov     [rsp+0B8h+var_90], rax; int
0x18003c272  lea     rax, [rsp+0B8h+var_48]
0x18003c277  mov     qword ptr [rsp+0B8h+var_98], rax
0x18003c27c  lea     rdx, dword_1800AF80C
0x18003c283  lea     rcx, dword_1800C1058
0x18003c28a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18003c28f  mov     [rsp+0B8h+var_98], 3Eh ; '>'; int
0x18003c297  lea     r9, aOnecoreuapTerm_42; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18003c29e  lea     r8, aRdpAvencRawCra_7; "Rdp::Avenc::Raw::CRawProcessor::Start"
0x18003c2a5  lea     rdx, aRawprocessorst_0; "RawProcessorStart"
0x18003c2ac  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18003c2b3  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18003c2b8  mov     rax, cs:WPP_GLOBAL_Control
0x18003c2bf  lea     rcx, WPP_GLOBAL_Control
0x18003c2c6  cmp     rax, rcx
0x18003c2c9  jz      short loc_18003C2D6
0x18003c2cb  test    [rax+1Ch], bl
0x18003c2ce  jz      short loc_18003C2D6
0x18003c2d0  cmp     byte ptr [rax+19h], 4
0x18003c2d4  jnb     short loc_18003C2D8
0x18003c2d6  xor     bl, bl
0x18003c2d8  lea     rax, WPP_RECORDER_INITIALIZED
0x18003c2df  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003c2e6  setnz   dil
0x18003c2ea  test    bl, bl
0x18003c2ec  jnz     short loc_18003C2F3
0x18003c2ee  test    dil, dil
0x18003c2f1  jz      short loc_18003C322
0x18003c2f3  call    cs:__imp_GetCurrentThreadId
0x18003c2f9  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x18003c2fd  mov     [rsp+0B8h+MessageGuid], r12; MessageGuid
0x18003c302  mov     [rsp+0B8h+var_88], 0Bh; __int16
0x18003c309  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c310  mov     r9, [rcx+28h]; int
0x18003c314  mov     r8b, dil; int
0x18003c317  mov     dl, bl; int
0x18003c319  mov     rcx, [rcx+10h]; int
0x18003c31d  call    WPP_RECORDER_AND_TRACE_SF_D
0x18003c322  xor     eax, eax
0x18003c324  jmp     short loc_18003C32D
0x18003c326  mov     eax, dword ptr [rsp+0B8h+arg_0]
0x18003c32d  add     rsp, 88h
0x18003c334  pop     r15
0x18003c336  pop     r14
0x18003c338  pop     r12
0x18003c33a  pop     rdi
0x18003c33b  pop     rsi
0x18003c33c  pop     rbx
0x18003c33d  retn
0x18003c33e  mov     r9d, eax; char *
0x18003c341  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003c348  mov     edx, 1CBEh; void *
0x18003c34d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
