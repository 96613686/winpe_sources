# Rdp::Stack::Graphics::CGrfxPipeline::Stop(void)

- ea: `0x18000cbc0`
- end: `0x18000ce9d`
- name: `?Stop@CGrfxPipeline@Graphics@Stack@Rdp@@UEAAJXZ`
- size: `733`
- prototype: `__int64 __fastcall(Rdp::Stack::Graphics::CGrfxPipeline *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000141c`
- `0x180001574`
- `0x18000b1bc`
- `0x18000cbc0`
- `0x18000d858`
- `0x18000db64`
- `0x18000dbf4`
- `0x18001205c`
- `0x18001682c`
- `0x18001a5f8`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cc24`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ce51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cc24`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ce51`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Rdp::Stack::Graphics::CGrfxPipeline::Stop(Rdp::Stack::Graphics::CGrfxPipeline *this)
{
  char v2; // di
  bool v3; // si
  bool v4; // r14
  char CurrentThreadId; // al
  int v6; // r8d
  int v7; // edx
  char v8; // cl
  __int64 result; // rax
  int v11; // r8d
  int v12; // r9d
  const char *v13; // r9
  Rdp::Stack::Graphics::CChannelPipeline *v14; // rcx
  Rdp::Stack::Graphics::CChannelPipeline *v15; // rcx
  Rdp::Stack::Graphics::CMonitorConfigChannel *v16; // rcx
  __int64 v17; // rcx
  unsigned int v18; // eax
  Rdp::Stack::Shim::CAdapterShim *v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  bool v22; // bl
  char v23; // al
  int v24; // r8d
  int v25; // edx
  int v26; // [rsp+20h] [rbp-78h]
  int v27; // [rsp+20h] [rbp-78h]
  char *v28; // [rsp+28h] [rbp-70h]
  char v29[8]; // [rsp+50h] [rbp-48h] BYREF
  const char *v30; // [rsp+58h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  int v32; // [rsp+A0h] [rbp+8h] BYREF
  const char *v33; // [rsp+A8h] [rbp+10h] BYREF
  __int128 *v34; // [rsp+B0h] [rbp+18h] BYREF
  const char *v35; // [rsp+B8h] [rbp+20h] BYREF

  v2 = 1;
  v3 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v4 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v6) = v4;
    LOBYTE(v7) = v3;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      v6,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v26,
      (int)v28,
      14,
      &WPP_b6962f5ff1663a860b25e7dc2e0c1fd5_Traceguids,
      CurrentThreadId);
  }
  v8 = *((_BYTE *)this + 92);
  *((_BYTE *)this + 92) = 0;
  if ( !v8 )
    return 1;
  if ( (unsigned int)dword_18003C058 > 4 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_18003C058, 0x470000000000LL) )
    {
      v32 = *((_DWORD *)this + 22);
      v33 = "Stop Grfx pipeline";
      v34 = &xmmword_18003CA50;
      v35 = "RdpLite";
      *(_QWORD *)v29 = 0x1000000;
      v30 = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18003C058,
        (unsigned int)byte_180034F69,
        v11,
        v12,
        (__int64)&v30,
        (__int64)v29,
        (__int64)&v35,
        (__int64)&v34,
        (__int64)&v33,
        (__int64)&v32);
    }
  }
  try
  {
    Rdp::Modern::Utils::CInflightRecorder::push0(
      (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      L"GrfxPipelineStop",
      "Rdp::Stack::Graphics::CGrfxPipeline::Stop",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\grfxpipeline.cpp",
      0x195u);
    v14 = (Rdp::Stack::Graphics::CChannelPipeline *)*((_QWORD *)this + 9);
    if ( v14 )
      Rdp::Stack::Graphics::CChannelPipeline::Stop(v14);
    v15 = (Rdp::Stack::Graphics::CChannelPipeline *)*((_QWORD *)this + 10);
    if ( v15 )
      Rdp::Stack::Graphics::CChannelPipeline::Stop(v15);
    v16 = (Rdp::Stack::Graphics::CMonitorConfigChannel *)*((_QWORD *)this + 8);
    if ( v16 )
      Rdp::Stack::Graphics::CMonitorConfigChannel::Stop(v16);
    v17 = *((_QWORD *)this + 5);
    if ( v17 )
    {
      v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 40LL))(v17);
      wil::details::in1diag3::Log_IfFailedMsg(
        retaddr,
        (void *)0x1B5,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\grfxpipeline.cpp",
        (const char *)v18,
        (int)"Failed to stop driver control object",
        v28);
      wil::com_ptr_t<IRDPCoreChannelManager,wil::err_exception_policy>::reset((char *)this + 40);
    }
    v19 = (Rdp::Stack::Shim::CAdapterShim *)*((_QWORD *)this + 6);
    if ( v19 )
      Rdp::Stack::Shim::CAdapterShim::Stop(v19);
    v20 = *((_QWORD *)this + 8);
    *((_QWORD *)this + 8) = 0;
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v21 = *((_QWORD *)this + 6);
    *((_QWORD *)this + 6) = 0;
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v2 = 0;
    }
    v22 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v23 = GetCurrentThreadId();
      LOBYTE(v24) = v22;
      LOBYTE(v25) = v2;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v25,
        v24,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v27,
        (int)v28,
        15,
        &WPP_b6962f5ff1663a860b25e7dc2e0c1fd5_Traceguids,
        v23);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1C7,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\grfxpipeline.cpp",
                           v13);
  }
  return result;
}

```

## disassembly

```asm
0x18000cbc0  push    rbx
0x18000cbc2  push    rsi
0x18000cbc3  push    rdi
0x18000cbc4  push    r12
0x18000cbc6  push    r13
0x18000cbc8  push    r14
0x18000cbca  push    r15
0x18000cbcc  sub     rsp, 60h
0x18000cbd0  mov     rbx, rcx
0x18000cbd3  lea     r12, WPP_GLOBAL_Control
0x18000cbda  mov     rax, cs:WPP_GLOBAL_Control
0x18000cbe1  mov     edi, 1
0x18000cbe6  cmp     rax, r12
0x18000cbe9  jz      short loc_18000CBFC
0x18000cbeb  test    [rax+1Ch], dil
0x18000cbef  jz      short loc_18000CBFC
0x18000cbf1  cmp     byte ptr [rax+19h], 4
0x18000cbf5  jb      short loc_18000CBFC
0x18000cbf7  mov     sil, dil
0x18000cbfa  jmp     short loc_18000CBFF
0x18000cbfc  xor     sil, sil
0x18000cbff  lea     r13, WPP_RECORDER_INITIALIZED
0x18000cc06  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18000cc0d  setnz   r14b
0x18000cc11  test    sil, sil
0x18000cc14  jnz     short loc_18000CC24
0x18000cc16  test    r14b, r14b
0x18000cc19  jnz     short loc_18000CC24
0x18000cc1b  lea     r15, WPP_b6962f5ff1663a860b25e7dc2e0c1fd5_Traceguids
0x18000cc22  jmp     short loc_18000CC5B
0x18000cc24  call    cs:__imp_GetCurrentThreadId
0x18000cc2a  mov     dword ptr [rsp+98h+var_58], eax; char
0x18000cc2e  lea     r15, WPP_b6962f5ff1663a860b25e7dc2e0c1fd5_Traceguids
0x18000cc35  mov     [rsp+98h+MessageGuid], r15; MessageGuid
0x18000cc3a  mov     [rsp+98h+var_68], 0Eh; __int16
0x18000cc41  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc48  mov     r9, [rcx+28h]; int
0x18000cc4c  mov     r8b, r14b; int
0x18000cc4f  mov     dl, sil; int
0x18000cc52  mov     rcx, [rcx+10h]; int
0x18000cc56  call    WPP_RECORDER_AND_TRACE_SF_D
0x18000cc5b  xor     ecx, ecx
0x18000cc5d  xchg    cl, [rbx+5Ch]
0x18000cc60  test    cl, cl
0x18000cc62  jnz     short loc_18000CC6B
0x18000cc64  mov     eax, edi
0x18000cc66  jmp     loc_18000CE8C
0x18000cc6b  mov     eax, cs:dword_18003C058
0x18000cc71  cmp     eax, 4
0x18000cc74  jbe     loc_18000CD3F
0x18000cc7a  mov     rdx, 470000000000h
0x18000cc84  lea     rcx, dword_18003C058
0x18000cc8b  call    _tlgKeywordOn
0x18000cc90  test    al, al
0x18000cc92  jz      loc_18000CD3F
0x18000cc98  mov     eax, [rbx+58h]
0x18000cc9b  mov     [rsp+98h+arg_0], eax
0x18000cca2  lea     rax, aStopGrfxPipeli; "Stop Grfx pipeline"
0x18000cca9  mov     [rsp+98h+arg_8], rax
0x18000ccb1  lea     rax, xmmword_18003CA50
0x18000ccb8  mov     [rsp+98h+arg_10], rax
0x18000ccc0  lea     rax, aRdplite; "RdpLite"
0x18000ccc7  mov     [rsp+98h+arg_18], rax
0x18000cccf  mov     qword ptr [rsp+98h+var_48], 1000000h
0x18000ccd8  lea     rax, aCheckpoint; "Checkpoint"
0x18000ccdf  mov     [rsp+98h+var_40], rax
0x18000cce4  lea     rax, [rsp+98h+arg_0]
0x18000ccec  mov     [rsp+98h+var_50], rax
0x18000ccf1  lea     rax, [rsp+98h+arg_8]
0x18000ccf9  mov     qword ptr [rsp+98h+var_58], rax
0x18000ccfe  lea     rax, [rsp+98h+arg_10]
0x18000cd06  mov     [rsp+98h+MessageGuid], rax
0x18000cd0b  lea     rax, [rsp+98h+arg_18]
0x18000cd13  mov     qword ptr [rsp+98h+var_68], rax
0x18000cd18  lea     rax, [rsp+98h+var_48]
0x18000cd1d  mov     [rsp+98h+var_70], rax; int
0x18000cd22  lea     rax, [rsp+98h+var_40]
0x18000cd27  mov     qword ptr [rsp+98h+var_78], rax
0x18000cd2c  lea     rdx, byte_180034F69
0x18000cd33  lea     rcx, dword_18003C058
0x18000cd3a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000cd3f  mov     [rsp+98h+var_78], 195h; unsigned int
0x18000cd47  lea     r9, aOnecoreuapTerm_5; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18000cd4e  lea     r8, aRdpStackGraphi_0; "Rdp::Stack::Graphics::CGrfxPipeline::St"...
0x18000cd55  lea     rdx, aGrfxpipelinest; "GrfxPipelineStop"
0x18000cd5c  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18000cd63  call    ?push0@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1I@Z; Rdp::Modern::Utils::CInflightRecorder::push0(ushort const *,char const *,char const *,uint)
0x18000cd68  mov     rcx, [rbx+48h]; this
0x18000cd6c  test    rcx, rcx
0x18000cd6f  jz      short loc_18000CD76
0x18000cd71  call    ?Stop@CChannelPipeline@Graphics@Stack@Rdp@@QEAAXXZ; Rdp::Stack::Graphics::CChannelPipeline::Stop(void)
0x18000cd76  mov     rcx, [rbx+50h]; this
0x18000cd7a  test    rcx, rcx
0x18000cd7d  jz      short loc_18000CD84
0x18000cd7f  call    ?Stop@CChannelPipeline@Graphics@Stack@Rdp@@QEAAXXZ; Rdp::Stack::Graphics::CChannelPipeline::Stop(void)
0x18000cd84  mov     rcx, [rbx+40h]; this
0x18000cd88  test    rcx, rcx
0x18000cd8b  jz      short loc_18000CD92
0x18000cd8d  call    ?Stop@CMonitorConfigChannel@Graphics@Stack@Rdp@@QEAAXXZ; Rdp::Stack::Graphics::CMonitorConfigChannel::Stop(void)
0x18000cd92  mov     rcx, [rbx+28h]
0x18000cd96  test    rcx, rcx
0x18000cd99  jz      short loc_18000CDD8
0x18000cd9b  mov     rax, [rcx]
0x18000cd9e  mov     rax, [rax+28h]
0x18000cda2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cda7  mov     rcx, [rsp+98h]; this
0x18000cdaf  lea     rdx, aFailedToStopDr; "Failed to stop driver control object"
0x18000cdb6  mov     qword ptr [rsp+98h+var_78], rdx; int
0x18000cdbb  mov     r9d, eax; char *
0x18000cdbe  lea     r8, aOnecoreuapTerm_5; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18000cdc5  mov     edx, 1B5h; void *
0x18000cdca  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000cdcf  lea     rcx, [rbx+28h]
0x18000cdd3  call    ?reset@?$com_ptr_t@UIRDPCoreChannelManager@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IRDPCoreChannelManager,wil::err_exception_policy>::reset(void)
0x18000cdd8  mov     rcx, [rbx+30h]; this
0x18000cddc  test    rcx, rcx
0x18000cddf  jz      short loc_18000CDE7
0x18000cde1  call    ?Stop@CAdapterShim@Shim@Stack@Rdp@@QEAAXXZ; Rdp::Stack::Shim::CAdapterShim::Stop(void)
0x18000cde6  nop
0x18000cde7  mov     rcx, [rbx+40h]
0x18000cdeb  mov     qword ptr [rbx+40h], 0
0x18000cdf3  test    rcx, rcx
0x18000cdf6  jz      short loc_18000CE05
0x18000cdf8  mov     rax, [rcx]
0x18000cdfb  mov     rax, [rax+10h]
0x18000cdff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce04  nop
0x18000ce05  mov     rcx, [rbx+30h]
0x18000ce09  mov     qword ptr [rbx+30h], 0
0x18000ce11  test    rcx, rcx
0x18000ce14  jz      short loc_18000CE23
0x18000ce16  mov     rax, [rcx]
0x18000ce19  mov     rax, [rax+10h]
0x18000ce1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce22  nop
0x18000ce23  mov     rax, cs:WPP_GLOBAL_Control
0x18000ce2a  cmp     rax, r12
0x18000ce2d  jz      short loc_18000CE3B
0x18000ce2f  test    [rax+1Ch], dil
0x18000ce33  jz      short loc_18000CE3B
0x18000ce35  cmp     byte ptr [rax+19h], 4
0x18000ce39  jnb     short loc_18000CE3E
0x18000ce3b  xor     dil, dil
0x18000ce3e  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18000ce45  setnz   bl
0x18000ce48  test    dil, dil
0x18000ce4b  jnz     short loc_18000CE51
0x18000ce4d  test    bl, bl
0x18000ce4f  jz      short loc_18000CE81
0x18000ce51  call    cs:__imp_GetCurrentThreadId
0x18000ce57  mov     dword ptr [rsp+98h+var_58], eax; char
0x18000ce5b  mov     [rsp+98h+MessageGuid], r15; MessageGuid
0x18000ce60  mov     [rsp+98h+var_68], 0Fh; __int16
0x18000ce67  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce6e  mov     r9, [rcx+28h]; int
0x18000ce72  mov     r8b, bl; int
0x18000ce75  mov     dl, dil; int
0x18000ce78  mov     rcx, [rcx+10h]; int
0x18000ce7c  call    WPP_RECORDER_AND_TRACE_SF_D
0x18000ce81  xor     eax, eax
0x18000ce83  jmp     short loc_18000CE8C
0x18000ce85  mov     eax, [rsp+98h+arg_0]
0x18000ce8c  add     rsp, 60h
0x18000ce90  pop     r15
0x18000ce92  pop     r14
0x18000ce94  pop     r13
0x18000ce96  pop     r12
0x18000ce98  pop     rdi
0x18000ce99  pop     rsi
0x18000ce9a  pop     rbx
0x18000ce9b  retn
```
