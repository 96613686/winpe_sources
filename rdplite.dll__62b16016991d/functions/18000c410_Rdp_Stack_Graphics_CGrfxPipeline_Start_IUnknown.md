# Rdp::Stack::Graphics::CGrfxPipeline::Start(IUnknown *)

- ea: `0x18000c410`
- end: `0x18000cb35`
- name: `?Start@CGrfxPipeline@Graphics@Stack@Rdp@@UEAAJPEAUIUnknown@@@Z`
- size: `1829`
- prototype: `__int64 __fastcall(Rdp::Stack::Graphics::CGrfxPipeline *__hidden this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000141c`
- `0x180001574`
- `0x1800036f0`
- `0x180003714`
- `0x180004cb4`
- `0x180009a2c`
- `0x18000a3f4`
- `0x18000af58`
- `0x18000aff0`
- `0x18000b0ac`
- `0x18000b130`
- `0x18000b1bc`
- `0x18000bef0`
- `0x18000c010`
- `0x18000c410`
- `0x18000cb3c`
- `0x18000cea4`
- `0x18000cef0`
- `0x18000cf28`
- `0x18000d98c`
- `0x18000db64`
- `0x18000dbf4`
- `0x180011c64`
- `0x180011db0`
- `0x18001367c`
- `0x180016738`
- `0x180028334`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c48f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000caa1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c48f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000caa1`

## string_xrefs

- `0x18000c656`: `Failed to retrieve PKEY_EncodingDllGuid property`
- `0x18000c7bb`: `Failed to set PKEY_InProcEncodingProcessorClsid property`
- `0x18000c7f6`: `Failed to set PKEY_OutProcEncodingProcessorClsid property`
- `0x18000c8e2`: `Failed to update static frame re-encode count`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Rdp::Stack::Graphics::CGrfxPipeline::Start(
        Rdp::Stack::Graphics::CGrfxPipeline *this,
        struct IUnknown *a2)
{
  char v3; // bl
  bool v4; // si
  bool v5; // r14
  char CurrentThreadId; // al
  int v7; // r8d
  int v8; // edx
  Rdp::Utils::Props **v9; // r14
  unsigned int *v10; // r9
  unsigned int UInt32; // eax
  int v12; // r8d
  int v13; // r9d
  struct _GUID *v14; // r9
  unsigned int Guid; // eax
  struct _GUID *v16; // r9
  unsigned int v17; // eax
  __int64 *v18; // rax
  int v19; // eax
  const struct _GUID *v20; // r9
  unsigned int v21; // eax
  const struct _GUID *v22; // r9
  unsigned int v23; // eax
  _QWORD *v24; // r15
  struct Rdp::Stack::IDriverControl **v25; // r8
  unsigned int v26; // eax
  unsigned int v27; // r9d
  unsigned int v28; // eax
  unsigned int v29; // eax
  __int64 *v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rdx
  Rdp::Stack::Graphics::CGraphicsChannel *v33; // rsi
  const unsigned __int16 *v34; // rax
  __int64 *v35; // rax
  Rdp::Stack::Graphics::CChannelPipeline *v36; // rsi
  const unsigned __int16 *v37; // rax
  __int64 v38; // rax
  __int64 v39; // rsi
  const char *v40; // r9
  bool v41; // di
  char v42; // al
  int v43; // r8d
  int v44; // edx
  __int64 result; // rax
  unsigned int v46; // eax
  int v47; // [rsp+20h] [rbp-D8h]
  int v48; // [rsp+20h] [rbp-D8h]
  int v49; // [rsp+28h] [rbp-D0h]
  char *v50; // [rsp+28h] [rbp-D0h]
  char *v51; // [rsp+28h] [rbp-D0h]
  char *v52; // [rsp+28h] [rbp-D0h]
  char *v53; // [rsp+28h] [rbp-D0h]
  char *v54; // [rsp+28h] [rbp-D0h]
  char *v55; // [rsp+28h] [rbp-D0h]
  char *v56; // [rsp+28h] [rbp-D0h]
  char *v57; // [rsp+28h] [rbp-D0h]
  char *v58; // [rsp+30h] [rbp-C8h]
  int v59; // [rsp+50h] [rbp-A8h] BYREF
  struct _tagpropertykey Buf1; // [rsp+58h] [rbp-A0h] BYREF
  _BYTE v61[24]; // [rsp+70h] [rbp-88h] BYREF
  __int128 *v62; // [rsp+88h] [rbp-70h] BYREF
  char v63[8]; // [rsp+90h] [rbp-68h] BYREF
  char v64[8]; // [rsp+98h] [rbp-60h] BYREF
  __int128 v65; // [rsp+A0h] [rbp-58h] BYREF
  struct _tagpropertykey v66; // [rsp+B0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v3 = 1;
  v4 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v5 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v7) = v5;
    LOBYTE(v8) = v4;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      v7,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v47,
      v49,
      12,
      &WPP_b6962f5ff1663a860b25e7dc2e0c1fd5_Traceguids,
      CurrentThreadId);
  }
  v9 = (Rdp::Utils::Props **)((char *)this + 24);
  try
  {
    wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(
      (_DWORD)retaddr,
      187,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\grfxpipeline.cpp",
      -2147418113,
      (__int64)this + 24);
    UInt32 = Rdp::Utils::Props::IPropertyStore_GetUInt32(
               *v9,
               (struct IPropertyStore *)&PKEY_Session_Id,
               (const struct _tagpropertykey *)((char *)this + 88),
               v10);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0xC5,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\grfxpipeline.cpp",
      (const char *)UInt32,
      (int)"Failed to retrieve PKEY_Session_Id property",
      "PropertyStore is not initialized");
    if ( (unsigned int)dword_18003C058 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18003C058, 0x470000000000LL) )
    {
      v59 = *((_DWORD *)this + 22);
      *(_QWORD *)&v61[16] = "Start Grfx pipeline";
      v62 = &xmmword_18003CA50;
      *(_QWORD *)v63 = "RdpLite";
      *(_QWORD *)v64 = 0x1000000;
      *(_QWORD *)&Buf1.fmtid.Data1 = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18003C058,
        (unsigned int)byte_180034FC9,
        v12,
        v13,
        (__int64)&Buf1,
        (__int64)v64,
        (__int64)v63,
        (__int64)&v62,
        (__int64)&v61[16],
        (__int64)&v59);
    }
    Rdp::Modern::Utils::CInflightRecorder::pushN(
      (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      (wchar_t *)L"GrfxPipelineStart",
      "Rdp::Stack::Graphics::CGrfxPipeline::Start",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\grfxpipeline.cpp",
      0xCFu);
    Buf1.fmtid = (GUID)xmmword_18002F220;
    Guid = Rdp::Utils::Props::IPropertyStore_GetGuid(*v9, (struct IPropertyStore *)&PKEY_EncodingDllGuid, &Buf1, v14);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0xDA,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\grfxpipeline.cpp",
      (const char *)Guid,
      (int)"Failed to retrieve PKEY_EncodingDllGuid property",
      v50);
    *(_OWORD *)v61 = xmmword_18002F220;
    v17 = Rdp::Utils::Props::IPropertyStore_GetGuid(
            *v9,
            (struct IPropertyStore *)&PKEY_EncodingScenarioGuid,
            (const struct _tagpropertykey *)v61,
            v16);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0xE5,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\grfxpipeline.cpp",
      (const char *)v17,
      (int)"Failed to retrieve PKEY_EncodingScenarioGuid property",
      v51);
    v66.fmtid = (GUID)xmmword_18002F220;
    v65 = xmmword_18002F220;
    if ( !memcmp_0(&Buf1, &GUID_RdpAvenc, 0x10u) )
    {
      v18 = qword_18003C680;
      do
      {
        if ( *(_OWORD *)v18 == *(_OWORD *)v61 )
          break;
        v18 += 6;
      }
      while ( v18 != qword_18003C770 );
      if ( v18 == qword_18003C770 || !v18 )
      {
        v46 = wil::verify_hresult<long>(2147943568LL);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0xF6,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\grfxpipeline.cpp",
          (const char *)v46,
          (int)"Encoding processor is not found",
          v52);
      }
      v66.fmtid = (GUID)*((_OWORD *)v18 + 1);
      v65 = *((_OWORD *)v18 + 2);
    }
    else
    {
      v65 = *(_OWORD *)v61;
    }
    v19 = memcmp_0(&v65, &xmmword_18002F220, 0x10u);
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x108,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\grfxpipeline.cpp",
      (const char *)0x80070057LL,
      v19 == 0,
      (bool)"Encoding processor is not specified",
      v58);
    v21 = Rdp::Utils::Props::IPropertyStore_SetCLSID(
            *v9,
            (struct IPropertyStore *)&PKEY_InProcEncodingProcessorClsid,
            &v66,
            v20);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x112,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\grfxpipeline.cpp",
      (const char *)v21,
      (int)"Failed to set PKEY_InProcEncodingProcessorClsid property",
      v53);
    v23 = Rdp::Utils::Props::IPropertyStore_SetCLSID(
            *v9,
            (struct IPropertyStore *)&PKEY_OutProcEncodingProcessorClsid,
            (const struct _tagpropertykey *)&v65,
            v22);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x11C,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\grfxpipeline.cpp",
      (const char *)v23,
      (int)"Failed to set PKEY_OutProcEncodingProcessorClsid property",
      v54);
    v24 = (_QWORD *)((char *)this + 40);
    wil::com_ptr_t<IRDPCoreChannelManager,wil::err_exception_policy>::reset((char *)this + 40);
    Rdp::Stack::Driver::Bind(*v9, (struct IPropertyStore *)this + 5, v25);
    *((_BYTE *)this + 92) = 1;
    v26 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v24 + 32LL))(*v24);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x129,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\grfxpipeline.cpp",
      (const char *)v26,
      (int)"Failed to start driver control object",
      v55);
    Rdp::Stack::Graphics::CGrfxPipeline::SerializeConfigPropertyStore((Rdp::Stack::Graphics::CGrfxPipeline *)((char *)this - 80));
    Rdp::Stack::Graphics::CGrfxPipeline::SerializeGrfxChannelCapsPropertyStore((Rdp::Stack::Graphics::CGrfxPipeline *)((char *)this - 80));
    if ( !memcmp_0(&v65, &CLSID_HevcProcessor, 0x10u) )
    {
      v28 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
              *v9,
              (struct IPropertyStore *)&PKEY_StaticFrameReencodeCount,
              (const struct _tagpropertykey *)3,
              v27);
      wil::details::in1diag3::Log_IfFailedMsg(
        retaddr,
        (void *)0x13C,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\grfxpipeline.cpp",
        (const char *)v28,
        (int)"Failed to retrieve PKEY_StaticFrameReencodeCount property",
        v56);
      v29 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v24 + 72LL))(*v24);
      wil::details::in1diag3::Log_IfFailedMsg(
        retaddr,
        (void *)0x13F,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\grfxpipeline.cpp",
        (const char *)v29,
        (int)"Failed to update static frame re-encode count",
        v57);
    }
    if ( memcmp_0(&v66, &xmmword_18002F220, 0x10u) )
      Rdp::Stack::Graphics::CGrfxPipeline::StartEncodingShim((Rdp::Stack::Graphics::CGrfxPipeline *)((char *)this - 80));
    if ( !memcmp_0(&Buf1, &GUID_RdpAvenc, 0x10u) )
    {
      v30 = qword_18003C770;
      v31 = *((_QWORD *)&v65 + 1);
      v32 = v65;
      do
      {
        if ( *(_OWORD *)v30 == v65 )
          break;
        v30 += 2;
      }
      while ( v30 != qword_18003C7B0 );
      if ( v30 != qword_18003C7B0 && v30 )
      {
        v33 = (Rdp::Stack::Graphics::CGraphicsChannel *)*((_QWORD *)this + 9);
        v34 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(*(_QWORD *)*v24 + 80LL))(
                                          *v24,
                                          v65,
                                          qword_18003C7B0);
        Rdp::Stack::Graphics::CGraphicsChannel::Start(v33, v34);
        v31 = *((_QWORD *)&v65 + 1);
        v32 = v65;
      }
      v35 = qword_18003C7B0;
      do
      {
        if ( *v35 == v32 && v35[1] == v31 )
          break;
        v35 += 2;
      }
      while ( v35 != &`__local_stdio_printf_options'::`2'::_OptionsStorage );
      if ( v35 != &`__local_stdio_printf_options'::`2'::_OptionsStorage && v35 )
      {
        v36 = (Rdp::Stack::Graphics::CChannelPipeline *)*((_QWORD *)this + 10);
        v37 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(*(_QWORD *)*v24 + 80LL))(
                                          *v24,
                                          v32,
                                          &`__local_stdio_printf_options'::`2'::_OptionsStorage);
        *((_BYTE *)v36 + 832) = 1;
        Rdp::Stack::Graphics::CChannelPipeline::StartFileIoRead(
          v36,
          v37,
          &GUID_AvencFileIoChannelCursor,
          (unsigned int *)1);
      }
    }
    *(_QWORD *)&Buf1.fmtid.Data1 = operator new(0x80u);
    v38 = Rdp::Stack::Graphics::CMonitorConfigChannel::CMonitorConfigChannel(
            *(Rdp::Stack::Graphics::CMonitorConfigChannel **)&Buf1.fmtid.Data1,
            (struct IPropertyStore *)*v9,
            (Rdp::Stack::Graphics::CGrfxPipeline *)((char *)this - 80));
    v39 = *((_QWORD *)this + 8);
    *((_QWORD *)this + 8) = v38;
    if ( v38 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 8LL))(v38);
    if ( v39 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    Rdp::Stack::Graphics::CMonitorConfigChannel::Start(
      *((Rdp::Stack::Graphics::CMonitorConfigChannel **)this + 8),
      *((struct IRDPCoreChannelManager **)this + 7));
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v3 = 0;
    }
    v41 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v42 = GetCurrentThreadId();
      LOBYTE(v43) = v41;
      LOBYTE(v44) = v3;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v44,
        v43,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v48,
        (int)v56,
        13,
        &WPP_b6962f5ff1663a860b25e7dc2e0c1fd5_Traceguids,
        v42);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x174,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\grfxpipeline.cpp",
                           v40);
  }
  return result;
}

```

## disassembly

```asm
0x18000c410  mov     [rsp+arg_8], rbx
0x18000c415  mov     [rsp+arg_10], rsi
0x18000c41a  push    rdi
0x18000c41b  push    r12
0x18000c41d  push    r13
0x18000c41f  push    r14
0x18000c421  push    r15
0x18000c423  sub     rsp, 0D0h
0x18000c42a  mov     rax, cs:__security_cookie
0x18000c431  xor     rax, rsp
0x18000c434  mov     [rsp+0C0h], rax
0x18000c43c  mov     rdi, rcx
0x18000c43f  lea     rcx, WPP_GLOBAL_Control
0x18000c446  mov     rax, cs:WPP_GLOBAL_Control
0x18000c44d  mov     ebx, 1
0x18000c452  cmp     rax, rcx
0x18000c455  jz      short loc_18000C467
0x18000c457  test    [rax+1Ch], bl
0x18000c45a  jz      short loc_18000C467
0x18000c45c  cmp     byte ptr [rax+19h], 4
0x18000c460  jb      short loc_18000C467
0x18000c462  mov     sil, bl
0x18000c465  jmp     short loc_18000C46A
0x18000c467  xor     sil, sil
0x18000c46a  lea     rax, WPP_RECORDER_INITIALIZED
0x18000c471  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18000c478  setnz   r14b
0x18000c47c  test    sil, sil
0x18000c47f  jnz     short loc_18000C48F
0x18000c481  test    r14b, r14b
0x18000c484  jnz     short loc_18000C48F
0x18000c486  lea     r13, WPP_b6962f5ff1663a860b25e7dc2e0c1fd5_Traceguids
0x18000c48d  jmp     short loc_18000C4C6
0x18000c48f  call    cs:__imp_GetCurrentThreadId
0x18000c495  mov     dword ptr [rsp+0F8h+var_B8], eax; char
0x18000c499  lea     r13, WPP_b6962f5ff1663a860b25e7dc2e0c1fd5_Traceguids
0x18000c4a0  mov     [rsp+0F8h+MessageGuid], r13; MessageGuid
0x18000c4a5  mov     word ptr [rsp+0F8h+var_C8], 0Ch; __int16
0x18000c4ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4b3  mov     r9, [rcx+28h]; int
0x18000c4b7  mov     r8b, r14b; int
0x18000c4ba  mov     dl, sil; int
0x18000c4bd  mov     rcx, [rcx+10h]; int
0x18000c4c1  call    WPP_RECORDER_AND_TRACE_SF_D
0x18000c4c6  lea     r14, [rdi+18h]
0x18000c4ca  mov     rcx, [rsp+0F8h]
0x18000c4d2  lea     rax, aPropertystoreI; "PropertyStore is not initialized"
0x18000c4d9  mov     [rsp+0F8h+var_D0], rax; char *
0x18000c4de  mov     qword ptr [rsp+0F8h+var_D8], r14
0x18000c4e3  mov     r9d, 8000FFFFh
0x18000c4e9  lea     r12, aOnecoreuapTerm_5; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18000c4f0  mov     r8, r12
0x18000c4f3  mov     edx, 0BBh
0x18000c4f8  call    ??$Throw_HrIfNullMsg@V?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDJAEBV?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@2@1ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(void *,uint,char const *,long,wil::com_ptr_t<IPropertyStore,wil::err_exception_policy> const &,char const *,...)
0x18000c4fd  lea     r8, [rdi+58h]; struct _tagpropertykey *
0x18000c501  lea     rdx, PKEY_Session_Id; struct IPropertyStore *
0x18000c508  mov     rcx, [r14]; this
0x18000c50b  call    ?IPropertyStore_GetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAI@Z; Rdp::Utils::Props::IPropertyStore_GetUInt32(IPropertyStore *,_tagpropertykey const &,uint *)
0x18000c510  mov     rcx, [rsp+0F8h]; this
0x18000c518  lea     rdx, aFailedToRetrie_14; "Failed to retrieve PKEY_Session_Id prop"...
0x18000c51f  mov     qword ptr [rsp+0F8h+var_D8], rdx; int
0x18000c524  mov     r9d, eax; char *
0x18000c527  mov     r8, r12; unsigned int
0x18000c52a  mov     edx, 0C5h; void *
0x18000c52f  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000c534  mov     eax, cs:dword_18003C058
0x18000c53a  cmp     eax, 4
0x18000c53d  jbe     loc_18000C608
0x18000c543  mov     rdx, 470000000000h
0x18000c54d  lea     rcx, dword_18003C058
0x18000c554  call    _tlgKeywordOn
0x18000c559  test    al, al
0x18000c55b  jz      loc_18000C608
0x18000c561  mov     eax, [rdi+58h]
0x18000c564  mov     [rsp+0F8h+var_A8], eax
0x18000c568  lea     rax, aStartGrfxPipel; "Start Grfx pipeline"
0x18000c56f  mov     qword ptr [rsp+0F8h+var_88+10h], rax
0x18000c577  lea     rax, xmmword_18003CA50
0x18000c57e  mov     [rsp+0F8h+var_70], rax
0x18000c586  lea     rax, aRdplite; "RdpLite"
0x18000c58d  mov     qword ptr [rsp+0F8h+var_68], rax
0x18000c595  mov     qword ptr [rsp+0F8h+var_60], 1000000h
0x18000c5a1  lea     rax, aCheckpoint; "Checkpoint"
0x18000c5a8  mov     qword ptr [rsp+0F8h+Buf1], rax
0x18000c5ad  lea     rax, [rsp+0F8h+var_A8]
0x18000c5b2  mov     [rsp+0F8h+var_B0], rax
0x18000c5b7  lea     rax, [rsp+0F8h+var_88+10h]
0x18000c5bf  mov     qword ptr [rsp+0F8h+var_B8], rax
0x18000c5c4  lea     rax, [rsp+0F8h+var_70]
0x18000c5cc  mov     [rsp+0F8h+MessageGuid], rax
0x18000c5d1  lea     rax, [rsp+0F8h+var_68]
0x18000c5d9  mov     [rsp+0F8h+var_C8], rax; char *
0x18000c5de  lea     rax, [rsp+0F8h+var_60]
0x18000c5e6  mov     [rsp+0F8h+var_D0], rax; char *
0x18000c5eb  lea     rax, [rsp+0F8h+Buf1]
0x18000c5f0  mov     qword ptr [rsp+0F8h+var_D8], rax
0x18000c5f5  lea     rdx, byte_180034FC9
0x18000c5fc  lea     rcx, dword_18003C058
0x18000c603  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000c608  mov     dword ptr [rsp+0F8h+var_D8], 0CFh; unsigned int
0x18000c610  mov     r9, r12; char *
0x18000c613  lea     r8, aRdpStackGraphi_2; "Rdp::Stack::Graphics::CGrfxPipeline::St"...
0x18000c61a  lea     rdx, aGrfxpipelinest_0; "GrfxPipelineStart"
0x18000c621  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18000c628  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18000c62d  movups  xmm0, cs:xmmword_18002F220
0x18000c634  movdqu  [rsp+0F8h+Buf1], xmm0
0x18000c63a  lea     r8, [rsp+0F8h+Buf1]; struct _tagpropertykey *
0x18000c63f  lea     rdx, PKEY_EncodingDllGuid; struct IPropertyStore *
0x18000c646  mov     rcx, [r14]; this
0x18000c649  call    ?IPropertyStore_GetGuid@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAU_GUID@@@Z; Rdp::Utils::Props::IPropertyStore_GetGuid(IPropertyStore *,_tagpropertykey const &,_GUID *)
0x18000c64e  mov     rcx, [rsp+0F8h]; this
0x18000c656  lea     rdx, aFailedToRetrie_16; "Failed to retrieve PKEY_EncodingDllGuid"...
0x18000c65d  mov     qword ptr [rsp+0F8h+var_D8], rdx; int
0x18000c662  mov     r9d, eax; char *
0x18000c665  mov     r8, r12; unsigned int
0x18000c668  mov     edx, 0DAh; void *
0x18000c66d  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000c672  movups  xmm0, cs:xmmword_18002F220
0x18000c679  movdqu  xmmword ptr [rsp+0F8h+var_88], xmm0
0x18000c67f  lea     r8, [rsp+0F8h+var_88]; struct _tagpropertykey *
0x18000c684  lea     rdx, PKEY_EncodingScenarioGuid; struct IPropertyStore *
0x18000c68b  mov     rcx, [r14]; this
0x18000c68e  call    ?IPropertyStore_GetGuid@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAU_GUID@@@Z; Rdp::Utils::Props::IPropertyStore_GetGuid(IPropertyStore *,_tagpropertykey const &,_GUID *)
0x18000c693  mov     rcx, [rsp+0F8h]; this
0x18000c69b  lea     rdx, aFailedToRetrie_8; "Failed to retrieve PKEY_EncodingScenari"...
0x18000c6a2  mov     qword ptr [rsp+0F8h+var_D8], rdx; int
0x18000c6a7  mov     r9d, eax; char *
0x18000c6aa  mov     r8, r12; unsigned int
0x18000c6ad  mov     edx, 0E5h; void *
0x18000c6b2  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000c6b7  movups  xmm0, cs:xmmword_18002F220
0x18000c6be  movdqu  xmmword ptr [rsp+0F8h+var_58.pid], xmm0
0x18000c6c7  movdqu  xmmword ptr [rsp+0F8h+var_58.fmtid.Data1], xmm0
0x18000c6d0  mov     esi, 10h
0x18000c6d5  mov     r8d, esi; Size
0x18000c6d8  lea     rdx, GUID_RdpAvenc; Buf2
0x18000c6df  lea     rcx, [rsp+0F8h+Buf1]; Buf1
0x18000c6e4  call    memcmp_0
0x18000c6e9  test    eax, eax
0x18000c6eb  jnz     short loc_18000C747
0x18000c6ed  lea     rax, qword_18003C680
0x18000c6f4  lea     r8, qword_18003C770
0x18000c6fb  mov     rcx, qword ptr [rsp+0F8h+var_88+8]
0x18000c700  mov     rdx, qword ptr [rsp+0F8h+var_88]
0x18000c705  cmp     [rax], rdx
0x18000c708  jnz     short loc_18000C710
0x18000c70a  cmp     [rax+8], rcx
0x18000c70e  jz      short loc_18000C719
0x18000c710  add     rax, 30h ; '0'
0x18000c714  cmp     rax, r8
0x18000c717  jnz     short loc_18000C705
0x18000c719  cmp     rax, r8
0x18000c71c  jz      loc_18000CB05
0x18000c722  test    rax, rax
0x18000c725  jz      loc_18000CB05
0x18000c72b  movups  xmm0, xmmword ptr [rax+10h]
0x18000c72f  movdqu  xmmword ptr [rsp+0F8h+var_58.pid], xmm0
0x18000c738  movups  xmm1, xmmword ptr [rax+20h]
0x18000c73c  movdqu  xmmword ptr [rsp+0F8h+var_58.fmtid.Data1], xmm1
0x18000c745  jmp     short loc_18000C755
0x18000c747  movaps  xmm0, xmmword ptr [rsp+0F8h+var_88]
0x18000c74c  movdqa  xmmword ptr [rsp+0F8h+var_58.fmtid.Data1], xmm0
0x18000c755  mov     r8, rsi; Size
0x18000c758  lea     rdx, xmmword_18002F220; Buf2
0x18000c75f  lea     rcx, [rsp+0F8h+var_58]; Buf1
0x18000c767  call    memcmp_0
0x18000c76c  test    eax, eax
0x18000c76e  setz    al
0x18000c771  mov     rcx, [rsp+0F8h]; this
0x18000c779  lea     rdx, aEncodingProces; "Encoding processor is not specified"
0x18000c780  mov     [rsp+0F8h+var_D0], rdx; int
0x18000c785  mov     [rsp+0F8h+var_D8], al; char
0x18000c789  mov     r9d, 80070057h; char *
0x18000c78f  mov     r8, r12; unsigned int
0x18000c792  mov     edx, 108h; void *
0x18000c797  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18000c79c  lea     r8, [rsp+0F8h+var_58.pid]; struct _tagpropertykey *
0x18000c7a4  lea     rdx, PKEY_InProcEncodingProcessorClsid; struct IPropertyStore *
0x18000c7ab  mov     rcx, [r14]; this
0x18000c7ae  call    ?IPropertyStore_SetCLSID@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@AEBU_GUID@@@Z; Rdp::Utils::Props::IPropertyStore_SetCLSID(IPropertyStore *,_tagpropertykey const &,_GUID const &)
0x18000c7b3  mov     rcx, [rsp+0F8h]; this
0x18000c7bb  lea     rdx, aFailedToSetPke_21; "Failed to set PKEY_InProcEncodingProces"...
0x18000c7c2  mov     qword ptr [rsp+0F8h+var_D8], rdx; int
0x18000c7c7  mov     r9d, eax; char *
0x18000c7ca  mov     r8, r12; unsigned int
0x18000c7cd  mov     edx, 112h; void *
0x18000c7d2  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000c7d7  lea     r8, [rsp+0F8h+var_58]; struct _tagpropertykey *
0x18000c7df  lea     rdx, PKEY_OutProcEncodingProcessorClsid; struct IPropertyStore *
0x18000c7e6  mov     rcx, [r14]; this
0x18000c7e9  call    ?IPropertyStore_SetCLSID@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@AEBU_GUID@@@Z; Rdp::Utils::Props::IPropertyStore_SetCLSID(IPropertyStore *,_tagpropertykey const &,_GUID const &)
0x18000c7ee  mov     rcx, [rsp+0F8h]; this
0x18000c7f6  lea     rdx, aFailedToSetPke_11; "Failed to set PKEY_OutProcEncodingProce"...
0x18000c7fd  mov     qword ptr [rsp+0F8h+var_D8], rdx; int
0x18000c802  mov     r9d, eax; char *
0x18000c805  mov     r8, r12; unsigned int
0x18000c808  mov     edx, 11Ch; void *
0x18000c80d  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000c812  lea     r15, [rdi+28h]
0x18000c816  mov     rcx, r15
0x18000c819  call    ?reset@?$com_ptr_t@UIRDPCoreChannelManager@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IRDPCoreChannelManager,wil::err_exception_policy>::reset(void)
0x18000c81e  mov     rdx, r15; struct IPropertyStore *
0x18000c821  mov     rcx, [r14]; this
0x18000c824  call    ?Bind@Driver@Stack@Rdp@@YAXPEAUIPropertyStore@@PEAPEAUIDriverControl@23@@Z; Rdp::Stack::Driver::Bind(IPropertyStore *,Rdp::Stack::IDriverControl * *)
0x18000c829  mov     eax, ebx
0x18000c82b  xchg    al, [rdi+5Ch]
0x18000c82e  mov     rcx, [r15]
0x18000c831  mov     rax, [rcx]
0x18000c834  mov     rax, [rax+20h]
0x18000c838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c83d  mov     rcx, [rsp+0F8h]; this
0x18000c845  lea     rdx, aFailedToStartD; "Failed to start driver control object"
0x18000c84c  mov     qword ptr [rsp+0F8h+var_D8], rdx; int
0x18000c851  mov     r9d, eax; char *
0x18000c854  mov     r8, r12; unsigned int
0x18000c857  mov     edx, 129h; void *
0x18000c85c  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000c861  lea     r12, [rdi-50h]
0x18000c865  mov     rcx, r12; this
0x18000c868  call    ?SerializeConfigPropertyStore@CGrfxPipeline@Graphics@Stack@Rdp@@AEAAXXZ; Rdp::Stack::Graphics::CGrfxPipeline::SerializeConfigPropertyStore(void)
0x18000c86d  mov     rcx, r12; this
0x18000c870  call    ?SerializeGrfxChannelCapsPropertyStore@CGrfxPipeline@Graphics@Stack@Rdp@@AEAAXXZ; Rdp::Stack::Graphics::CGrfxPipeline::SerializeGrfxChannelCapsPropertyStore(void)
0x18000c875  mov     r8, rsi; Size
0x18000c878  lea     rdx, CLSID_HevcProcessor; Buf2
0x18000c87f  lea     rcx, [rsp+0F8h+var_58]; Buf1
0x18000c887  call    memcmp_0
0x18000c88c  test    eax, eax
0x18000c88e  jnz     short loc_18000C902
0x18000c890  lea     r8d, [rax+3]; struct _tagpropertykey *
0x18000c894  lea     rdx, PKEY_StaticFrameReencodeCount; struct IPropertyStore *
0x18000c89b  mov     rcx, [r14]; this
0x18000c89e  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x18000c8a3  mov     rcx, [rsp+0F8h]; this
0x18000c8ab  lea     rdx, aFailedToRetrie_3; "Failed to retrieve PKEY_StaticFrameReen"...
0x18000c8b2  mov     qword ptr [rsp+0F8h+var_D8], rdx; int
0x18000c8b7  mov     r9d, eax; char *
0x18000c8ba  lea     r8, aOnecoreuapTerm_5; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18000c8c1  mov     edx, 13Ch; void *
0x18000c8c6  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000c8cb  mov     rcx, [r15]
0x18000c8ce  mov     rax, [rcx]
0x18000c8d1  mov     rax, [rax+48h]
0x18000c8d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8da  mov     rcx, [rsp+0F8h]; this
0x18000c8e2  lea     rdx, aFailedToUpdate; "Failed to update static frame re-encode"...
0x18000c8e9  mov     qword ptr [rsp+0F8h+var_D8], rdx; int
0x18000c8ee  mov     r9d, eax; char *
0x18000c8f1  lea     r8, aOnecoreuapTerm_5; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18000c8f8  mov     edx, 13Fh; void *
0x18000c8fd  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000c902  mov     r8, rsi; Size
0x18000c905  lea     rdx, xmmword_18002F220; Buf2
0x18000c90c  lea     rcx, [rsp+0F8h+var_58.pid]; Buf1
0x18000c914  call    memcmp_0
0x18000c919  test    eax, eax
0x18000c91b  jz      short loc_18000C925
0x18000c91d  mov     rcx, r12; this
0x18000c920  call    ?StartEncodingShim@CGrfxPipeline@Graphics@Stack@Rdp@@AEAAXXZ; Rdp::Stack::Graphics::CGrfxPipeline::StartEncodingShim(void)
0x18000c925  mov     r8, rsi; Size
0x18000c928  lea     rdx, GUID_RdpAvenc; Buf2
0x18000c92f  lea     rcx, [rsp+0F8h+Buf1]; Buf1
0x18000c934  call    memcmp_0
0x18000c939  test    eax, eax
0x18000c93b  jnz     loc_18000CA0A
0x18000c941  lea     rax, qword_18003C770
0x18000c948  lea     r8, qword_18003C7B0
0x18000c94f  mov     rcx, qword ptr [rsp+0F8h+var_58.fmtid.Data4]
0x18000c957  mov     rdx, qword ptr [rsp+0F8h+var_58.fmtid.Data1]
0x18000c95f  cmp     [rax], rdx
0x18000c962  jnz     short loc_18000C96A
0x18000c964  cmp     [rax+8], rcx
0x18000c968  jz      short loc_18000C972
0x18000c96a  add     rax, rsi
0x18000c96d  cmp     rax, r8
0x18000c970  jnz     short loc_18000C95F
0x18000c972  cmp     rax, r8
0x18000c975  jz      short loc_18000C9AF
0x18000c977  test    rax, rax
0x18000c97a  jz      short loc_18000C9AF
0x18000c97c  mov     rsi, [rdi+48h]
0x18000c980  mov     rcx, [r15]
0x18000c983  mov     rax, [rcx]
0x18000c986  mov     rax, [rax+50h]
0x18000c98a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c98f  mov     rdx, rax; unsigned __int16 *
0x18000c992  mov     rcx, rsi; this
0x18000c995  call    ?Start@CGraphicsChannel@Graphics@Stack@Rdp@@QEAAXPEBG@Z; Rdp::Stack::Graphics::CGraphicsChannel::Start(ushort const *)
0x18000c99a  mov     rcx, qword ptr [rsp+0F8h+var_58.fmtid.Data4]
0x18000c9a2  mov     rdx, qword ptr [rsp+0F8h+var_58.fmtid.Data1]
0x18000c9aa  mov     esi, 10h
0x18000c9af  lea     rax, qword_18003C7B0
0x18000c9b6  lea     r8, ?_OptionsStorage@?1??__local_stdio_printf_options@@9@4_KA; unsigned __int64 `__local_stdio_printf_options'::`2'::_OptionsStorage
0x18000c9bd  cmp     [rax], rdx
0x18000c9c0  jnz     short loc_18000C9C8
0x18000c9c2  cmp     [rax+8], rcx
0x18000c9c6  jz      short loc_18000C9D0
0x18000c9c8  add     rax, rsi
0x18000c9cb  cmp     rax, r8
0x18000c9ce  jnz     short loc_18000C9BD
  ... truncated ...
```
