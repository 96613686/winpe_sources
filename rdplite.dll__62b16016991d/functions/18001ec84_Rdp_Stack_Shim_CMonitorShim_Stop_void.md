# Rdp::Stack::Shim::CMonitorShim::Stop(void)

- ea: `0x18001ec84`
- end: `0x18001ef31`
- name: `?Stop@CMonitorShim@Shim@Stack@Rdp@@QEAAXXZ`
- size: `685`
- prototype: `void __fastcall(Rdp::Stack::Shim::CMonitorShim *__hidden this)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018d7c`
- `0x180018f90`

## callees

- `0x18000141c`
- `0x180001574`
- `0x18000b1bc`
- `0x18000cea4`
- `0x18000d858`
- `0x18000db64`
- `0x18000dbf4`
- `0x18000f30c`
- `0x18000fc30`
- `0x18001ec84`
- `0x18001f2e4`
- `0x1800227a0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ece6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001eedf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ece6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001eedf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Rdp::Stack::Shim::CMonitorShim::Stop(Rdp::Stack::Shim::CMonitorShim *this)
{
  char v2; // si
  bool v3; // bl
  bool v4; // di
  char CurrentThreadId; // al
  int v6; // r8d
  int v7; // edx
  int v8; // r8d
  int v9; // r9d
  __int64 ***v10; // rdi
  __int64 **i; // rbx
  __int64 v12; // rcx
  unsigned int v13; // eax
  bool v14; // bl
  char v15; // al
  int v16; // r8d
  int v17; // edx
  int v18; // [rsp+20h] [rbp-58h]
  int v19; // [rsp+20h] [rbp-58h]
  int v20; // [rsp+28h] [rbp-50h]
  char *v21; // [rsp+28h] [rbp-50h]
  char *v22; // [rsp+30h] [rbp-48h]
  char v23[8]; // [rsp+50h] [rbp-28h] BYREF
  _QWORD v24[4]; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]
  int v26; // [rsp+C0h] [rbp+48h] BYREF
  const char *v27; // [rsp+C8h] [rbp+50h] BYREF
  __int128 *v28; // [rsp+D0h] [rbp+58h] BYREF
  const char *v29; // [rsp+D8h] [rbp+60h] BYREF

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
      v18,
      v20,
      12,
      &WPP_9429e1887f2b37205431ce51b91c21ec_Traceguids,
      CurrentThreadId);
  }
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0xB7,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)0x8000FFFFLL,
    *((_BYTE *)this + 248) == 0,
    (bool)"Monitor shim is not started",
    v22);
  if ( (unsigned int)dword_18003C058 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18003C058, 0x470000000000LL) )
  {
    v26 = *(_DWORD *)(*((_QWORD *)this + 29) + 336LL);
    v27 = "Stop monitor shim";
    v28 = &xmmword_18003CA50;
    v29 = "RdpLite";
    *(_QWORD *)v23 = 0x1000000;
    v24[0] = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18003C058,
      (unsigned int)byte_180035E85,
      v8,
      v9,
      (__int64)v24,
      (__int64)v23,
      (__int64)&v29,
      (__int64)&v28,
      (__int64)&v27,
      (__int64)&v26);
  }
  Rdp::Modern::Utils::CInflightRecorder::push0(
    (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    L"MonitorShimStop",
    "Rdp::Stack::Shim::CMonitorShim::Stop",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    0xC1u);
  std::unique_lock<std::mutex>::unique_lock<std::mutex>(v24, (char *)this + 144);
  v10 = (__int64 ***)*((_QWORD *)this + 11);
  for ( i = *v10; i != (__int64 **)v10; i = (__int64 **)*i )
    Rdp::Stack::Shim::CFrameProcessorShim::Stop((Rdp::Stack::Shim::CFrameProcessorShim *)i[3]);
  std::_Hash<std::_Umap_traits<unsigned __int64,wil::com_ptr_t<Rdp::Stack::Shim::CFrameProcessorShim,wil::err_exception_policy>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,wil::com_ptr_t<Rdp::Stack::Shim::CFrameProcessorShim,wil::err_exception_policy>>>,0>>::clear((char *)this + 80);
  v12 = *((_QWORD *)this + 28);
  if ( v12 )
  {
    v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 40LL))(v12);
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0xD4,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
      (const char *)v13,
      (int)"Failed to stop monitor encoding context",
      v21);
    wil::com_ptr_t<IRDPCoreChannelManager,wil::err_exception_policy>::reset((char *)this + 224);
  }
  *((_BYTE *)this + 248) = 0;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
  {
    v2 = 0;
  }
  v14 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v15 = GetCurrentThreadId();
    LOBYTE(v16) = v14;
    LOBYTE(v17) = v2;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v17,
      v16,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v19,
      (int)v21,
      13,
      &WPP_9429e1887f2b37205431ce51b91c21ec_Traceguids,
      v15);
  }
  std::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>::~unique_lock<Rdp::Utils::Synchronization::rundown_mutex>(v24);
}

```

## disassembly

```asm
0x18001ec84  push    rbp
0x18001ec86  push    rbx
0x18001ec87  push    rsi
0x18001ec88  push    rdi
0x18001ec89  push    r12
0x18001ec8b  push    r13
0x18001ec8d  push    r14
0x18001ec8f  push    r15
0x18001ec91  mov     rbp, rsp
0x18001ec94  sub     rsp, 78h
0x18001ec98  mov     r14, rcx
0x18001ec9b  lea     r12, WPP_GLOBAL_Control
0x18001eca2  mov     sil, 1
0x18001eca5  mov     rax, cs:WPP_GLOBAL_Control
0x18001ecac  cmp     rax, r12
0x18001ecaf  jz      short loc_18001ECC2
0x18001ecb1  test    [rax+1Ch], sil
0x18001ecb5  jz      short loc_18001ECC2
0x18001ecb7  cmp     byte ptr [rax+19h], 4
0x18001ecbb  jb      short loc_18001ECC2
0x18001ecbd  mov     bl, sil
0x18001ecc0  jmp     short loc_18001ECC4
0x18001ecc2  xor     bl, bl
0x18001ecc4  lea     r13, WPP_RECORDER_INITIALIZED
0x18001eccb  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18001ecd2  setnz   dil
0x18001ecd6  lea     r15, WPP_9429e1887f2b37205431ce51b91c21ec_Traceguids
0x18001ecdd  test    bl, bl
0x18001ecdf  jnz     short loc_18001ECE6
0x18001ece1  test    dil, dil
0x18001ece4  jz      short loc_18001ED15
0x18001ece6  call    cs:__imp_GetCurrentThreadId
0x18001ecec  mov     dword ptr [rsp+78h+var_38], eax; char
0x18001ecf0  mov     [rsp+78h+MessageGuid], r15; MessageGuid
0x18001ecf5  mov     word ptr [rsp+78h+var_48], 0Ch; char *
0x18001ecfc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ed03  mov     r9, [rcx+28h]; int
0x18001ed07  mov     r8b, dil; int
0x18001ed0a  mov     dl, bl; int
0x18001ed0c  mov     rcx, [rcx+10h]; int
0x18001ed10  call    WPP_RECORDER_AND_TRACE_SF_D
0x18001ed15  cmp     byte ptr [r14+0F8h], 0
0x18001ed1d  setz    al
0x18001ed20  mov     rcx, [rbp+40h]; this
0x18001ed24  lea     rdx, aMonitorShimIsN; "Monitor shim is not started"
0x18001ed2b  mov     [rsp+78h+var_50], rdx; bool
0x18001ed30  mov     [rsp+78h+var_58], al; char
0x18001ed34  mov     r9d, 8000FFFFh; char *
0x18001ed3a  lea     r8, aOnecoreuapTerm_18; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001ed41  mov     edx, 0B7h; void *
0x18001ed46  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001ed4b  mov     eax, cs:dword_18003C058
0x18001ed51  cmp     eax, 4
0x18001ed54  jbe     loc_18001EE05
0x18001ed5a  mov     rdx, 470000000000h
0x18001ed64  lea     rcx, dword_18003C058
0x18001ed6b  call    _tlgKeywordOn
0x18001ed70  test    al, al
0x18001ed72  jz      loc_18001EE05
0x18001ed78  mov     rax, [r14+0E8h]
0x18001ed7f  mov     ecx, [rax+150h]
0x18001ed85  mov     [rbp+arg_0], ecx
0x18001ed88  lea     rax, aStopMonitorShi; "Stop monitor shim"
0x18001ed8f  mov     [rbp+arg_8], rax
0x18001ed93  lea     rax, xmmword_18003CA50
0x18001ed9a  mov     [rbp+arg_10], rax
0x18001ed9e  lea     rax, aRdplite; "RdpLite"
0x18001eda5  mov     [rbp+arg_18], rax
0x18001eda9  mov     qword ptr [rbp+var_28], 1000000h
0x18001edb1  lea     rax, aCheckpoint; "Checkpoint"
0x18001edb8  mov     [rbp+var_20], rax
0x18001edbc  lea     rax, [rbp+arg_0]
0x18001edc0  mov     [rsp+78h+var_30], rax
0x18001edc5  lea     rax, [rbp+arg_8]
0x18001edc9  mov     qword ptr [rsp+78h+var_38], rax
0x18001edce  lea     rax, [rbp+arg_10]
0x18001edd2  mov     [rsp+78h+MessageGuid], rax
0x18001edd7  lea     rax, [rbp+arg_18]
0x18001eddb  mov     [rsp+78h+var_48], rax
0x18001ede0  lea     rax, [rbp+var_28]
0x18001ede4  mov     [rsp+78h+var_50], rax; int
0x18001ede9  lea     rax, [rbp+var_20]
0x18001eded  mov     qword ptr [rsp+78h+var_58], rax
0x18001edf2  lea     rdx, byte_180035E85
0x18001edf9  lea     rcx, dword_18003C058
0x18001ee00  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001ee05  mov     dword ptr [rsp+78h+var_58], 0C1h; unsigned int
0x18001ee0d  lea     r9, aOnecoreuapTerm_18; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001ee14  lea     r8, aRdpStackShimCm; "Rdp::Stack::Shim::CMonitorShim::Stop"
0x18001ee1b  lea     rdx, aMonitorshimsto; "MonitorShimStop"
0x18001ee22  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001ee29  call    ?push0@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1I@Z; Rdp::Modern::Utils::CInflightRecorder::push0(ushort const *,char const *,char const *,uint)
0x18001ee2e  lea     rdx, [r14+90h]
0x18001ee35  lea     rcx, [rbp+var_20]
0x18001ee39  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x18001ee3e  nop
0x18001ee3f  mov     rdi, [r14+58h]
0x18001ee43  mov     rbx, [rdi]
0x18001ee46  cmp     rbx, rdi
0x18001ee49  jz      short loc_18001EE59
0x18001ee4b  mov     rcx, [rbx+18h]; this
0x18001ee4f  call    ?Stop@CFrameProcessorShim@Shim@Stack@Rdp@@QEAAXXZ; Rdp::Stack::Shim::CFrameProcessorShim::Stop(void)
0x18001ee54  mov     rbx, [rbx]
0x18001ee57  jmp     short loc_18001EE46
0x18001ee59  lea     rcx, [r14+50h]
0x18001ee5d  call    ?clear@?$_Hash@V?$_Umap_traits@_KV?$com_ptr_t@VCFrameProcessorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KV?$com_ptr_t@VCFrameProcessorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@4@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<unsigned __int64,wil::com_ptr_t<Rdp::Stack::Shim::CFrameProcessorShim,wil::err_exception_policy>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,wil::com_ptr_t<Rdp::Stack::Shim::CFrameProcessorShim,wil::err_exception_policy>>>,0>>::clear(void)
0x18001ee62  lea     rbx, [r14+0E0h]
0x18001ee69  mov     rcx, [rbx]
0x18001ee6c  test    rcx, rcx
0x18001ee6f  jz      short loc_18001EEA9
0x18001ee71  mov     rax, [rcx]
0x18001ee74  mov     rax, [rax+28h]
0x18001ee78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee7d  mov     rcx, [rbp+40h]; this
0x18001ee81  lea     rdx, aFailedToStopMo; "Failed to stop monitor encoding context"
0x18001ee88  mov     qword ptr [rsp+78h+var_58], rdx; int
0x18001ee8d  mov     r9d, eax; char *
0x18001ee90  lea     r8, aOnecoreuapTerm_18; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001ee97  mov     edx, 0D4h; void *
0x18001ee9c  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001eea1  mov     rcx, rbx
0x18001eea4  call    ?reset@?$com_ptr_t@UIRDPCoreChannelManager@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IRDPCoreChannelManager,wil::err_exception_policy>::reset(void)
0x18001eea9  mov     byte ptr [r14+0F8h], 0
0x18001eeb1  mov     rax, cs:WPP_GLOBAL_Control
0x18001eeb8  cmp     rax, r12
0x18001eebb  jz      short loc_18001EEC9
0x18001eebd  test    [rax+1Ch], sil
0x18001eec1  jz      short loc_18001EEC9
0x18001eec3  cmp     byte ptr [rax+19h], 4
0x18001eec7  jnb     short loc_18001EECC
0x18001eec9  xor     sil, sil
0x18001eecc  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18001eed3  setnz   bl
0x18001eed6  test    sil, sil
0x18001eed9  jnz     short loc_18001EEDF
0x18001eedb  test    bl, bl
0x18001eedd  jz      short loc_18001EF17
0x18001eedf  call    cs:__imp_GetCurrentThreadId
0x18001eee5  mov     dword ptr [rsp+78h+var_38], eax; char
0x18001eee9  lea     rax, WPP_9429e1887f2b37205431ce51b91c21ec_Traceguids
0x18001eef0  mov     [rsp+78h+MessageGuid], rax; MessageGuid
0x18001eef5  mov     word ptr [rsp+78h+var_48], 0Dh; __int16
0x18001eefc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ef03  mov     r9, [rcx+28h]; int
0x18001ef07  mov     r8b, bl; int
0x18001ef0a  mov     dl, sil; int
0x18001ef0d  mov     rcx, [rcx+10h]; int
0x18001ef11  call    WPP_RECORDER_AND_TRACE_SF_D
0x18001ef16  nop
0x18001ef17  lea     rcx, [rbp+var_20]
0x18001ef1b  call    ??1?$unique_lock@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEAA@XZ; std::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>::~unique_lock<Rdp::Utils::Synchronization::rundown_mutex>(void)
0x18001ef20  add     rsp, 78h
0x18001ef24  pop     r15
0x18001ef26  pop     r14
0x18001ef28  pop     r13
0x18001ef2a  pop     r12
0x18001ef2c  pop     rdi
0x18001ef2d  pop     rsi
0x18001ef2e  pop     rbx
0x18001ef2f  pop     rbp
0x18001ef30  retn
```
