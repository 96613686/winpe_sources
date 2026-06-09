# Rdp::Stack::Graphics::CMonitorConfigChannel::ProcessSetMonitorConfiguration(bool,uint,uint,void const *)

- ea: `0x180016304`
- end: `0x18001665a`
- name: `?ProcessSetMonitorConfiguration@CMonitorConfigChannel@Graphics@Stack@Rdp@@AEAAX_NIIPEBX@Z`
- size: `854`
- prototype: `void __fastcall(Rdp::Stack::Graphics::CMonitorConfigChannel *this, unsigned __int8, unsigned int, unsigned int, struct _RDPCFG_MONITOR_CONFIGURATION *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180015fa0`

## callees

- `0x18000141c`
- `0x1800022b0`
- `0x180003714`
- `0x1800049b8`
- `0x180007b28`
- `0x180009a78`
- `0x180009ab0`
- `0x18000a0e4`
- `0x18000b578`
- `0x18000cea4`
- `0x18000d98c`
- `0x180015c24`
- `0x180015dcc`
- `0x180016304`
- `0x180016660`
- `0x180016ce0`

## string_xrefs

- `0x180016406`: `onecoreuap\termsrv\rdp_bin\win\rdplite\grfxpipeline\monitorconfigchannel.cpp`
- `0x18001658f`: `onecoreuap\termsrv\rdp_bin\win\rdplite\grfxpipeline\monitorconfigchannel.cpp`
- `0x18001636a`: `Client requested monitor configuration update`
- `0x180016410`: `Rdp::Stack::Graphics::CMonitorConfigChannel::ProcessSetMonitorConfiguration`
- `0x180016417`: `MonitorConfigUpdate: Id=%d`
- `0x180016435`: `Buffer size is too small to cast to RDPCFG_MONITOR_CONFIGURATION`
- `0x1800164b0`: `RDPCFG_MONITOR_CONFIGURATION structure has invalid size`
- `0x180016579`: `Unable to move to next RDPCFG_MONITOR_CONFIGURATION because buffer is too small`

## pseudocode

```c
void __fastcall Rdp::Stack::Graphics::CMonitorConfigChannel::ProcessSetMonitorConfiguration(
        Rdp::Stack::Graphics::CMonitorConfigChannel *this,
        unsigned __int8 a2,
        unsigned int a3,
        unsigned int a4,
        struct _RDPCFG_MONITOR_CONFIGURATION *a5)
{
  int v7; // r12d
  int v9; // r8d
  int v10; // r9d
  struct _RDPCFG_MONITOR_CONFIGURATION *v11; // rdi
  unsigned int v12; // r8d
  __int64 v13; // rax
  struct _RDPCFG_MONITOR_CONFIGURATION *v14; // rbx
  __int64 v15; // rdx
  signed int VirtualDesktopInfo; // eax
  bool v17[8]; // [rsp+28h] [rbp-79h]
  char *v18; // [rsp+30h] [rbp-71h]
  char *v19; // [rsp+30h] [rbp-71h]
  char *v20; // [rsp+30h] [rbp-71h]
  char *v21; // [rsp+30h] [rbp-71h]
  __int128 v22; // [rsp+60h] [rbp-41h] BYREF
  __int128 v23; // [rsp+70h] [rbp-31h] BYREF
  __int64 v24; // [rsp+80h] [rbp-21h]
  __int128 v25; // [rsp+88h] [rbp-19h] BYREF
  __int64 v26; // [rsp+98h] [rbp-9h]
  const char *v27; // [rsp+A0h] [rbp-1h] BYREF
  __int128 *v28; // [rsp+A8h] [rbp+7h] BYREF
  char v29[8]; // [rsp+B0h] [rbp+Fh] BYREF
  __int64 v30[7]; // [rsp+B8h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+57h]
  Rdp::Stack::Graphics::CMonitorConfig *v32; // [rsp+100h] [rbp+5Fh] BYREF
  int v33; // [rsp+110h] [rbp+6Fh] BYREF
  int v34; // [rsp+118h] [rbp+77h] BYREF

  v7 = a2;
  if ( (unsigned int)dword_18003C058 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18003C058, 0x470000000000LL) )
  {
    v33 = v7;
    v34 = v9;
    LODWORD(v32) = *(_DWORD *)(*((_QWORD *)this + 15) + 168LL);
    v27 = "Client requested monitor configuration update";
    v28 = &xmmword_18003CA50;
    *(_QWORD *)v29 = "RdpLite";
    v30[0] = 0x1000000;
    *(_QWORD *)&v22 = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18003C058,
      (unsigned int)&dword_18003527C,
      v9,
      v10,
      (__int64)&v22,
      (__int64)v30,
      (__int64)v29,
      (__int64)&v28,
      (__int64)&v27,
      (__int64)&v32,
      (__int64)&v34,
      (__int64)&v33);
  }
  *(_DWORD *)v17 = a3;
  Rdp::Modern::Utils::CInflightRecorder::pushN(
    (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    (wchar_t *)L"MonitorConfigUpdate: Id=%d",
    "Rdp::Stack::Graphics::CMonitorConfigChannel::ProcessSetMonitorConfiguration",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfigchannel.cpp",
    0x11Eu,
    *(_QWORD *)v17);
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x124,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfigchannel.cpp",
    (const char *)0x8007007ALL,
    a4 < 0x18,
    (bool)"Buffer size is too small to cast to RDPCFG_MONITOR_CONFIGURATION",
    v18);
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x12A,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfigchannel.cpp",
    (const char *)0x80070057LL,
    a3 == 0,
    (bool)"Invalid TransactionId value",
    v19);
  v25 = 0;
  v26 = 0;
  v23 = 0;
  v24 = 0;
  v11 = a5;
  while ( 1 )
  {
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x13A,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfigchannel.cpp",
      (const char *)0x8007007ALL,
      a4 < *(_DWORD *)v11,
      (bool)"RDPCFG_MONITOR_CONFIGURATION structure has invalid size",
      v20);
    v32 = (Rdp::Stack::Graphics::CMonitorConfig *)operator new(0x160u);
    v13 = Rdp::Stack::Graphics::CMonitorConfig::CMonitorConfig(v32, v11, v12);
    wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(
      &a5,
      (v13 + 80) & ((unsigned __int128)-(__int128)(unsigned __int64)v13 >> 64));
    v14 = a5;
    if ( *((_QWORD *)&v23 + 1) == v24 )
    {
      std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>::_Emplace_reallocate<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> const &>(
        &v23,
        *((_QWORD *)&v23 + 1),
        &a5);
    }
    else
    {
      wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(
        *((_QWORD *)&v23 + 1),
        a5);
      *((_QWORD *)&v23 + 1) += 8LL;
    }
    *(_QWORD *)&v22 = *((unsigned int *)v11 + 1);
    *((_QWORD *)&v22 + 1) = v14;
    if ( *((_QWORD *)&v25 + 1) == v26 )
    {
      std::vector<Rdp::Stack::RDPLITE_MONITORCONFIG_INFO>::_Emplace_reallocate<Rdp::Stack::RDPLITE_MONITORCONFIG_INFO>(
        &v25,
        *((_QWORD *)&v25 + 1),
        &v22);
    }
    else
    {
      **((_OWORD **)&v25 + 1) = v22;
      *((_QWORD *)&v25 + 1) += 16LL;
    }
    a4 -= *(_DWORD *)v11;
    if ( !a4 )
      break;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x155,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfigchannel.cpp",
      (const char *)0x8007007ALL,
      a4 < 0x18,
      (bool)"Unable to move to next RDPCFG_MONITOR_CONFIGURATION because buffer is too small",
      v21);
    v11 = (struct _RDPCFG_MONITOR_CONFIGURATION *)((char *)v11 + *(unsigned int *)v11);
    wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&a5);
  }
  wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&a5);
  v22 = 0;
  LOBYTE(v15) = v7;
  VirtualDesktopInfo = Rdp::Stack::Graphics::CGrfxPipeline::ProcessMonitorConfig(*((_QWORD *)this + 15), v15, &v25);
  if ( VirtualDesktopInfo >= 0 )
    VirtualDesktopInfo = Rdp::Stack::Graphics::CMonitorConfigChannel::GetVirtualDesktopInfo(
                           this,
                           (struct _RDPCFG_2DRECTANGLE *)&v22);
  Rdp::Stack::Graphics::CMonitorConfigChannel::SendNotifyMonitorConfiguration(
    this,
    a3,
    VirtualDesktopInfo,
    (const struct _RDPCFG_2DRECTANGLE *)&v22);
  if ( (_QWORD)v23 )
  {
    std::_Destroy_range<std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>>(
      v23,
      *((_QWORD *)&v23 + 1));
    std::_Deallocate<16>(v23, (v24 - v23) & 0xFFFFFFFFFFFFFFF8uLL);
    v23 = 0;
    v24 = 0;
  }
  if ( (_QWORD)v25 )
    std::_Deallocate<16>(v25, (v26 - v25) & 0xFFFFFFFFFFFFFFF0uLL);
}

```

## disassembly

```asm
0x180016304  push    rbp
0x180016306  push    rbx
0x180016307  push    rsi
0x180016308  push    rdi
0x180016309  push    r12
0x18001630b  push    r14
0x18001630d  push    r15
0x18001630f  lea     rbp, [rsp-1Fh]
0x180016314  sub     rsp, 0C0h
0x18001631b  mov     r14d, r9d
0x18001631e  mov     r15d, r8d
0x180016321  movzx   r12d, dl
0x180016325  mov     rsi, rcx
0x180016328  mov     eax, cs:dword_18003C058
0x18001632e  cmp     eax, 4
0x180016331  jbe     loc_1800163F9
0x180016337  mov     rdx, 470000000000h
0x180016341  lea     rcx, dword_18003C058
0x180016348  call    _tlgKeywordOn
0x18001634d  test    al, al
0x18001634f  jz      loc_1800163F9
0x180016355  mov     [rbp+4Fh+arg_10], r12d
0x180016359  mov     [rbp+4Fh+arg_18], r8d
0x18001635d  mov     rax, [rsi+78h]
0x180016361  mov     ecx, [rax+0A8h]
0x180016367  mov     dword ptr [rbp+4Fh+arg_0], ecx
0x18001636a  lea     rax, aClientRequeste; "Client requested monitor configuration "...
0x180016371  mov     [rbp+4Fh+var_50], rax
0x180016375  lea     rax, xmmword_18003CA50
0x18001637c  mov     [rbp+4Fh+var_48], rax
0x180016380  lea     rax, aRdplite; "RdpLite"
0x180016387  mov     qword ptr [rbp+4Fh+var_40], rax
0x18001638b  mov     [rbp+4Fh+var_38], 1000000h
0x180016393  lea     rax, aCheckpoint; "Checkpoint"
0x18001639a  mov     qword ptr [rbp+4Fh+var_90], rax
0x18001639e  lea     rax, [rbp+4Fh+arg_10]
0x1800163a2  mov     [rsp+0F0h+var_98], rax
0x1800163a7  lea     rax, [rbp+4Fh+arg_18]
0x1800163ab  mov     [rsp+0F0h+var_A0], rax
0x1800163b0  lea     rax, [rbp+4Fh+arg_0]
0x1800163b4  mov     [rsp+0F0h+var_A8], rax
0x1800163b9  lea     rax, [rbp+4Fh+var_50]
0x1800163bd  mov     [rsp+0F0h+var_B0], rax
0x1800163c2  lea     rax, [rbp+4Fh+var_48]
0x1800163c6  mov     [rsp+0F0h+var_B8], rax
0x1800163cb  lea     rax, [rbp+4Fh+var_40]
0x1800163cf  mov     [rsp+0F0h+var_C0], rax; char *
0x1800163d4  lea     rax, [rbp+4Fh+var_38]
0x1800163d8  mov     qword ptr [rsp+0F0h+var_C8], rax
0x1800163dd  lea     rax, [rbp+4Fh+var_90]
0x1800163e1  mov     qword ptr [rsp+0F0h+var_D0], rax
0x1800163e6  lea     rdx, dword_18003527C
0x1800163ed  lea     rcx, dword_18003C058
0x1800163f4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@66@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800163f9  mov     dword ptr [rsp+0F0h+var_C8], r15d
0x1800163fe  mov     dword ptr [rsp+0F0h+var_D0], 11Eh; unsigned int
0x180016406  lea     rbx, aOnecoreuapTerm_22; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001640d  mov     r9, rbx; char *
0x180016410  lea     r8, aRdpStackGraphi; "Rdp::Stack::Graphics::CMonitorConfigCha"...
0x180016417  lea     rdx, aMonitorconfigu; "MonitorConfigUpdate: Id=%d"
0x18001641e  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x180016425  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18001642a  cmp     r14d, 18h
0x18001642e  setb    al
0x180016431  mov     rcx, [rbp+57h]; this
0x180016435  lea     rdx, aBufferSizeIsTo_0; "Buffer size is too small to cast to RDP"...
0x18001643c  mov     qword ptr [rsp+0F0h+var_C8], rdx; bool
0x180016441  mov     [rsp+0F0h+var_D0], al; char
0x180016445  mov     r9d, 8007007Ah; char *
0x18001644b  mov     r8, rbx; unsigned int
0x18001644e  mov     edx, 124h; void *
0x180016453  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180016458  test    r15d, r15d
0x18001645b  setz    al
0x18001645e  mov     rcx, [rbp+57h]; this
0x180016462  lea     rdx, aInvalidTransac; "Invalid TransactionId value"
0x180016469  mov     qword ptr [rsp+0F0h+var_C8], rdx; bool
0x18001646e  mov     [rsp+0F0h+var_D0], al; char
0x180016472  mov     r9d, 80070057h; char *
0x180016478  mov     r8, rbx; unsigned int
0x18001647b  mov     edx, 12Ah; void *
0x180016480  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180016485  xorps   xmm0, xmm0
0x180016488  movdqu  [rbp+4Fh+var_68], xmm0
0x18001648d  mov     [rbp+4Fh+var_58], 0
0x180016495  movdqu  [rbp+4Fh+var_80], xmm0
0x18001649a  mov     [rbp+4Fh+var_70], 0
0x1800164a2  mov     rdi, [rbp+4Fh+arg_20]
0x1800164a6  cmp     r14d, [rdi]
0x1800164a9  setb    al
0x1800164ac  mov     rcx, [rbp+57h]; this
0x1800164b0  lea     rdx, aRdpcfgMonitorC; "RDPCFG_MONITOR_CONFIGURATION structure "...
0x1800164b7  mov     qword ptr [rsp+0F0h+var_C8], rdx; bool
0x1800164bc  mov     [rsp+0F0h+var_D0], al; char
0x1800164c0  mov     r9d, 8007007Ah; char *
0x1800164c6  mov     r8, rbx; unsigned int
0x1800164c9  mov     edx, 13Ah; void *
0x1800164ce  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800164d3  mov     ecx, 160h; Size
0x1800164d8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800164dd  mov     [rbp+4Fh+arg_0], rax
0x1800164e1  mov     rdx, rdi; struct _RDPCFG_MONITOR_CONFIGURATION *
0x1800164e4  mov     rcx, rax; this
0x1800164e7  call    ??0CMonitorConfig@Graphics@Stack@Rdp@@QEAA@PEBU_RDPCFG_MONITOR_CONFIGURATION@@I@Z; Rdp::Stack::Graphics::CMonitorConfig::CMonitorConfig(_RDPCFG_MONITOR_CONFIGURATION const *,uint)
0x1800164ec  nop
0x1800164ed  lea     rcx, [rax+50h]
0x1800164f1  neg     rax
0x1800164f4  sbb     rdx, rdx
0x1800164f7  and     rdx, rcx
0x1800164fa  lea     rcx, [rbp+4Fh+arg_20]
0x1800164fe  call    ??0?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCMonitorShim@Shim@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(Rdp::Stack::Shim::CMonitorShim *)
0x180016503  nop
0x180016504  mov     rbx, [rbp+4Fh+arg_20]
0x180016508  mov     rax, qword ptr [rbp+4Fh+var_80+8]
0x18001650c  cmp     rax, [rbp+4Fh+var_70]
0x180016510  jz      short loc_180016524
0x180016512  mov     rdx, rbx
0x180016515  mov     rcx, rax
0x180016518  call    ??0?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCMonitorShim@Shim@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(Rdp::Stack::Shim::CMonitorShim *)
0x18001651d  add     qword ptr [rbp+4Fh+var_80+8], 8
0x180016522  jmp     short loc_180016534
0x180016524  lea     r8, [rbp+4Fh+arg_20]
0x180016528  mov     rdx, rax
0x18001652b  lea     rcx, [rbp+4Fh+var_80]
0x18001652f  call    ??$_Emplace_reallocate@AEBV?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@?$vector@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@AEAAPEAV?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAV23@AEBV23@@Z; std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>::_Emplace_reallocate<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> const &>(wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> * const,wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> const &)
0x180016534  mov     eax, [rdi+4]
0x180016537  mov     dword ptr [rbp+4Fh+var_90], eax
0x18001653a  xor     eax, eax
0x18001653c  mov     dword ptr [rbp+4Fh+var_90+4], eax
0x18001653f  mov     qword ptr [rbp+4Fh+var_90+8], rbx
0x180016543  mov     rdx, qword ptr [rbp+4Fh+var_68+8]
0x180016547  cmp     rdx, [rbp+4Fh+var_58]
0x18001654b  jz      short loc_18001655C
0x18001654d  movups  xmm0, [rbp+4Fh+var_90]
0x180016551  movdqu  xmmword ptr [rdx], xmm0
0x180016555  add     qword ptr [rbp+4Fh+var_68+8], 10h
0x18001655a  jmp     short loc_180016569
0x18001655c  lea     r8, [rbp+4Fh+var_90]
0x180016560  lea     rcx, [rbp+4Fh+var_68]
0x180016564  call    ??$_Emplace_reallocate@URDPLITE_MONITORCONFIG_INFO@Stack@Rdp@@@?$vector@URDPLITE_MONITORCONFIG_INFO@Stack@Rdp@@V?$allocator@URDPLITE_MONITORCONFIG_INFO@Stack@Rdp@@@std@@@std@@AEAAPEAURDPLITE_MONITORCONFIG_INFO@Stack@Rdp@@QEAU234@$$QEAU234@@Z; std::vector<Rdp::Stack::RDPLITE_MONITORCONFIG_INFO>::_Emplace_reallocate<Rdp::Stack::RDPLITE_MONITORCONFIG_INFO>(Rdp::Stack::RDPLITE_MONITORCONFIG_INFO * const,Rdp::Stack::RDPLITE_MONITORCONFIG_INFO &&)
0x180016569  sub     r14d, [rdi]
0x18001656c  jz      short loc_1800165B6
0x18001656e  cmp     r14d, 18h
0x180016572  setb    al
0x180016575  mov     rcx, [rbp+57h]; this
0x180016579  lea     rdx, aUnableToMoveTo_1; "Unable to move to next RDPCFG_MONITOR_C"...
0x180016580  mov     qword ptr [rsp+0F0h+var_C8], rdx; bool
0x180016585  mov     [rsp+0F0h+var_D0], al; char
0x180016589  mov     r9d, 8007007Ah; char *
0x18001658f  lea     rbx, aOnecoreuapTerm_22; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180016596  mov     r8, rbx; unsigned int
0x180016599  mov     edx, 155h; void *
0x18001659e  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800165a3  mov     eax, [rdi]
0x1800165a5  add     rdi, rax
0x1800165a8  lea     rcx, [rbp+4Fh+arg_20]
0x1800165ac  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x1800165b1  jmp     loc_1800164A6
0x1800165b6  lea     rcx, [rbp+4Fh+arg_20]
0x1800165ba  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x1800165bf  xorps   xmm0, xmm0
0x1800165c2  movups  [rbp+4Fh+var_90], xmm0
0x1800165c6  lea     r8, [rbp+4Fh+var_68]
0x1800165ca  mov     dl, r12b
0x1800165cd  mov     rcx, [rsi+78h]
0x1800165d1  call    ?ProcessMonitorConfig@CGrfxPipeline@Graphics@Stack@Rdp@@QEAAJ_NAEBV?$vector@URDPLITE_MONITORCONFIG_INFO@Stack@Rdp@@V?$allocator@URDPLITE_MONITORCONFIG_INFO@Stack@Rdp@@@std@@@std@@@Z; Rdp::Stack::Graphics::CGrfxPipeline::ProcessMonitorConfig(bool,std::vector<Rdp::Stack::RDPLITE_MONITORCONFIG_INFO> const &)
0x1800165d6  test    eax, eax
0x1800165d8  js      short loc_1800165E6
0x1800165da  lea     rdx, [rbp+4Fh+var_90]; struct _RDPCFG_2DRECTANGLE *
0x1800165de  mov     rcx, rsi; this
0x1800165e1  call    ?GetVirtualDesktopInfo@CMonitorConfigChannel@Graphics@Stack@Rdp@@AEAAJAEAU_RDPCFG_2DRECTANGLE@@@Z; Rdp::Stack::Graphics::CMonitorConfigChannel::GetVirtualDesktopInfo(_RDPCFG_2DRECTANGLE &)
0x1800165e6  lea     r9, [rbp+4Fh+var_90]; struct _RDPCFG_2DRECTANGLE *
0x1800165ea  mov     r8d, eax; unsigned int
0x1800165ed  mov     edx, r15d; unsigned int
0x1800165f0  mov     rcx, rsi; this
0x1800165f3  call    ?SendNotifyMonitorConfiguration@CMonitorConfigChannel@Graphics@Stack@Rdp@@AEAAXIIAEBU_RDPCFG_2DRECTANGLE@@@Z; Rdp::Stack::Graphics::CMonitorConfigChannel::SendNotifyMonitorConfiguration(uint,uint,_RDPCFG_2DRECTANGLE const &)
0x1800165f8  nop
0x1800165f9  mov     rcx, qword ptr [rbp+4Fh+var_80]
0x1800165fd  test    rcx, rcx
0x180016600  jz      short loc_18001662F
0x180016602  mov     rdx, qword ptr [rbp+4Fh+var_80+8]
0x180016606  call    ??$_Destroy_range@V?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@YAXPEAV?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAV12@AEAV?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>>(wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> *,wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> * const,std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>> &)
0x18001660b  mov     rcx, qword ptr [rbp+4Fh+var_80]
0x18001660f  mov     rdx, [rbp+4Fh+var_70]
0x180016613  sub     rdx, rcx
0x180016616  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18001661a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001661f  xorps   xmm0, xmm0
0x180016622  movdqu  [rbp+4Fh+var_80], xmm0
0x180016627  mov     [rbp+4Fh+var_70], 0
0x18001662f  mov     rcx, qword ptr [rbp+4Fh+var_68]
0x180016633  test    rcx, rcx
0x180016636  jz      short loc_180016648
0x180016638  mov     rdx, [rbp+4Fh+var_58]
0x18001663c  sub     rdx, rcx
0x18001663f  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180016643  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180016648  add     rsp, 0C0h
0x18001664f  pop     r15
0x180016651  pop     r14
0x180016653  pop     r12
0x180016655  pop     rdi
0x180016656  pop     rsi
0x180016657  pop     rbx
0x180016658  pop     rbp
0x180016659  retn
```
