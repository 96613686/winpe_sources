# Rdp::Avenc::RdpProg::CRdpProgProcessor::Stop(void)

- ea: `0x180064d90`
- end: `0x180065142`
- name: `?Stop@CRdpProgProcessor@RdpProg@Avenc@Rdp@@UEAAJXZ`
- size: `946`
- prototype: `__int64 __fastcall(Rdp::Avenc::RdpProg::CRdpProgProcessor *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops`

## callees

- `0x1800019f0`
- `0x1800069a0`
- `0x18000cf44`
- `0x18000d13c`
- `0x1800103c0`
- `0x180010bc8`
- `0x1800146bc`
- `0x1800152c4`
- `0x180015480`
- `0x180022c9c`
- `0x180025884`
- `0x180026f90`
- `0x180064d90`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180064fc5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180064fc5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180064df5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800650d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180064df5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800650d7`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x18006508f`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x18006508f`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180064fd2`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180064fd2`

## pseudocode

```c
__int64 __fastcall Rdp::Avenc::RdpProg::CRdpProgProcessor::Stop(Rdp::Avenc::RdpProg::CRdpProgProcessor *this)
{
  char v2; // si
  bool v3; // di
  bool v4; // r14
  char CurrentThreadId; // al
  int v6; // r8d
  int v7; // edx
  int v8; // r8d
  int v9; // r9d
  const char *v11; // r9
  __int64 v12; // rcx
  volatile signed __int32 *v13; // rdi
  _QWORD *v14; // rdi
  void *v15; // rcx
  bool v16; // bl
  char v17; // al
  int v18; // r8d
  int v19; // edx
  __int64 result; // rax
  int v21; // [rsp+20h] [rbp-98h]
  int v22; // [rsp+20h] [rbp-98h]
  int v23; // [rsp+28h] [rbp-90h]
  int v24; // [rsp+28h] [rbp-90h]
  char *v25; // [rsp+30h] [rbp-88h]
  const char *v26; // [rsp+60h] [rbp-58h] BYREF
  int v27[2]; // [rsp+68h] [rbp-50h] BYREF
  _OWORD v28[4]; // [rsp+70h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  int v30; // [rsp+C0h] [rbp+8h] BYREF
  __int64 v31; // [rsp+C8h] [rbp+10h] BYREF
  const char *v32; // [rsp+D0h] [rbp+18h] BYREF
  int *v33; // [rsp+D8h] [rbp+20h] BYREF

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
      v21,
      v23,
      12,
      &WPP_6cd37b947aa232b475ac322cdbaf3e27_Traceguids,
      CurrentThreadId);
  }
  try
  {
    LOBYTE(v21) = *((_BYTE *)this + 176) == 0;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x5F,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogprocessor.cpp",
      (const char *)0x8000FFFFLL,
      v21,
      (bool)"Processor is not started",
      v25);
    if ( (unsigned int)dword_1800C1058 > 4
      && (qword_1800C1068 & 0x470000000000LL) != 0
      && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
    {
      v31 = *((_QWORD *)this + 9);
      v30 = *((_DWORD *)this + 20);
      v32 = "Stop RdpProg processor";
      v33 = &xmmword_1800C21A0;
      v26 = "RdpAvenc";
      *(_QWORD *)v27 = 0x1000000;
      *(_QWORD *)&v28[0] = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)byte_1800B4EA1,
        v8,
        v9,
        (__int64)v28,
        (__int64)v27,
        (__int64)&v26,
        (__int64)&v33,
        (__int64)&v32,
        (__int64)&v30,
        (__int64)&v31);
    }
    Rdp::Modern::Utils::CInflightRecorder::push0(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      L"RdpProgProcessorStop",
      "Rdp::Avenc::RdpProg::CRdpProgProcessor::Stop",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogprocessor.cpp",
      0x6Au);
    if ( (unsigned int)mtx_do_lock((char *)this + 264) )
      std::_Throw_Cpp_error(5);
    if ( *((_DWORD *)this + 85) == 0x7FFFFFFF )
    {
      *((_DWORD *)this + 85) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    *((_BYTE *)this + 416) = 0;
    if ( (*((_DWORD *)this + 85))-- == 1 )
    {
      *((_DWORD *)this + 84) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)this + 35);
    }
    WakeAllConditionVariable((PCONDITION_VARIABLE)this + 44);
    if ( *((_DWORD *)this + 64) )
      std::thread::join((Rdp::Avenc::RdpProg::CRdpProgProcessor *)((char *)this + 248));
    v12 = *((_QWORD *)this + 24);
    if ( v12 )
    {
      Rdp::Utils::Perf::details::CPerfMonLogger<&_GUID RDPPerfMonCountersGuid>::RemoveSession(
        v12,
        *((unsigned int *)this + 20));
      v28[0] = 0;
      std::shared_ptr<Rdp::Utils::Perf::CPerfMonSession>::operator=((char *)this + 232, v28);
      v13 = (volatile signed __int32 *)*((_QWORD *)&v28[0] + 1);
      if ( *((_QWORD *)&v28[0] + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v28[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
          if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
        }
      }
      v14 = (_QWORD *)*((_QWORD *)this + 24);
      *((_QWORD *)this + 24) = 0;
      if ( v14 )
      {
        std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Rdp::Utils::Graphics::CSharedFence>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Rdp::Utils::Graphics::CSharedFence>>>>>>>(v14 + 9);
        std::list<std::pair<void * const,std::shared_ptr<Rdp::Utils::Graphics::CSharedTexture>>>::~list<std::pair<void * const,std::shared_ptr<Rdp::Utils::Graphics::CSharedTexture>>>(v14 + 7);
        v15 = (void *)v14[5];
        if ( v15 )
          PerfStopProvider(v15);
        operator delete(v14);
      }
    }
    *((_BYTE *)this + 176) = 0;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v2 = 0;
    }
    v16 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v17 = GetCurrentThreadId();
      LOBYTE(v18) = v16;
      LOBYTE(v19) = v2;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v19,
        v18,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v22,
        v24,
        13,
        &WPP_6cd37b947aa232b475ac322cdbaf3e27_Traceguids,
        v17);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x80,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogprocessor.cpp",
                           v11);
  }
  return result;
}

```

## disassembly

```asm
0x180064d90  push    rbx
0x180064d92  push    rsi
0x180064d93  push    rdi
0x180064d94  push    r12
0x180064d96  push    r13
0x180064d98  push    r14
0x180064d9a  push    r15
0x180064d9c  sub     rsp, 80h
0x180064da3  mov     rbx, rcx
0x180064da6  lea     r12, WPP_GLOBAL_Control
0x180064dad  mov     rax, cs:WPP_GLOBAL_Control
0x180064db4  mov     sil, 1
0x180064db7  cmp     rax, r12
0x180064dba  jz      short loc_180064DCD
0x180064dbc  test    [rax+1Ch], sil
0x180064dc0  jz      short loc_180064DCD
0x180064dc2  cmp     byte ptr [rax+19h], 4
0x180064dc6  jb      short loc_180064DCD
0x180064dc8  mov     dil, sil
0x180064dcb  jmp     short loc_180064DD0
0x180064dcd  xor     dil, dil
0x180064dd0  lea     r13, WPP_RECORDER_INITIALIZED
0x180064dd7  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180064dde  setnz   r14b
0x180064de2  test    dil, dil
0x180064de5  jnz     short loc_180064DF5
0x180064de7  test    r14b, r14b
0x180064dea  jnz     short loc_180064DF5
0x180064dec  lea     r15, WPP_6cd37b947aa232b475ac322cdbaf3e27_Traceguids
0x180064df3  jmp     short loc_180064E2C
0x180064df5  call    cs:__imp_GetCurrentThreadId
0x180064dfb  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x180064dff  lea     r15, WPP_6cd37b947aa232b475ac322cdbaf3e27_Traceguids
0x180064e06  mov     [rsp+0B8h+MessageGuid], r15; MessageGuid
0x180064e0b  mov     word ptr [rsp+0B8h+var_88], 0Ch; char *
0x180064e12  mov     rcx, cs:WPP_GLOBAL_Control
0x180064e19  mov     r9, [rcx+28h]; int
0x180064e1d  mov     r8b, r14b; int
0x180064e20  mov     dl, dil; int
0x180064e23  mov     rcx, [rcx+10h]; int
0x180064e27  call    WPP_RECORDER_AND_TRACE_SF_D
0x180064e2c  cmp     byte ptr [rbx+0B0h], 0
0x180064e33  setz    al
0x180064e36  mov     rcx, [rsp+0B8h]; this
0x180064e3e  lea     rdx, aProcessorIsNot; "Processor is not started"
0x180064e45  mov     qword ptr [rsp+0B8h+var_90], rdx; bool
0x180064e4a  mov     byte ptr [rsp+0B8h+var_98], al; int
0x180064e4e  mov     r9d, 8000FFFFh; char *
0x180064e54  lea     r8, aOnecoreuapTerm_19; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180064e5b  mov     edx, 5Fh ; '_'; void *
0x180064e60  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180064e65  mov     eax, cs:dword_1800C1058
0x180064e6b  cmp     eax, 4
0x180064e6e  jbe     loc_180064F5E
0x180064e74  mov     rcx, cs:qword_1800C1070
0x180064e7b  mov     rax, cs:qword_1800C1068
0x180064e82  mov     rdx, 470000000000h
0x180064e8c  test    rdx, rax
0x180064e8f  jz      loc_180064F5E
0x180064e95  mov     rax, rcx
0x180064e98  and     rax, rdx
0x180064e9b  cmp     rax, rcx
0x180064e9e  jnz     loc_180064F5E
0x180064ea4  mov     rax, [rbx+48h]
0x180064ea8  mov     [rsp+0B8h+arg_8], rax
0x180064eb0  mov     eax, [rbx+50h]
0x180064eb3  mov     [rsp+0B8h+arg_0], eax
0x180064eba  lea     rax, aStopRdpprogPro; "Stop RdpProg processor"
0x180064ec1  mov     [rsp+0B8h+arg_10], rax
0x180064ec9  lea     rax, xmmword_1800C21A0
0x180064ed0  mov     [rsp+0B8h+arg_18], rax
0x180064ed8  lea     rax, aRdpavenc; "RdpAvenc"
0x180064edf  mov     [rsp+0B8h+var_58], rax
0x180064ee4  mov     qword ptr [rsp+0B8h+var_50], 1000000h
0x180064eed  lea     rax, aCheckpoint; "Checkpoint"
0x180064ef4  mov     qword ptr [rsp+0B8h+var_48], rax
0x180064ef9  lea     rax, [rsp+0B8h+arg_8]
0x180064f01  mov     [rsp+0B8h+var_68], rax
0x180064f06  lea     rax, [rsp+0B8h+arg_0]
0x180064f0e  mov     [rsp+0B8h+var_70], rax
0x180064f13  lea     rax, [rsp+0B8h+arg_10]
0x180064f1b  mov     qword ptr [rsp+0B8h+var_78], rax
0x180064f20  lea     rax, [rsp+0B8h+arg_18]
0x180064f28  mov     [rsp+0B8h+MessageGuid], rax
0x180064f2d  lea     rax, [rsp+0B8h+var_58]
0x180064f32  mov     [rsp+0B8h+var_88], rax
0x180064f37  lea     rax, [rsp+0B8h+var_50]
0x180064f3c  mov     qword ptr [rsp+0B8h+var_90], rax; int
0x180064f41  lea     rax, [rsp+0B8h+var_48]
0x180064f46  mov     qword ptr [rsp+0B8h+var_98], rax
0x180064f4b  lea     rdx, byte_1800B4EA1
0x180064f52  lea     rcx, dword_1800C1058
0x180064f59  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180064f5e  mov     [rsp+0B8h+var_98], 6Ah ; 'j'; int
0x180064f66  lea     r9, aOnecoreuapTerm_19; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180064f6d  lea     r8, aRdpAvencRdppro; "Rdp::Avenc::RdpProg::CRdpProgProcessor:"...
0x180064f74  lea     rdx, aRdpprogprocess_0; "RdpProgProcessorStop"
0x180064f7b  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x180064f82  call    ?push0@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1I@Z; Rdp::Modern::Utils::CInflightRecorder::push0(ushort const *,char const *,char const *,uint)
0x180064f87  lea     rdi, [rbx+108h]
0x180064f8e  mov     rcx, rdi
0x180064f91  call    mtx_do_lock
0x180064f96  test    eax, eax
0x180064f98  jnz     loc_180065125
0x180064f9e  cmp     dword ptr [rdi+4Ch], 7FFFFFFFh
0x180064fa5  jz      loc_18006512F
0x180064fab  xor     eax, eax
0x180064fad  xchg    al, [rbx+1A0h]
0x180064fb3  or      r14d, 0FFFFFFFFh
0x180064fb7  add     [rdi+4Ch], r14d
0x180064fbb  jnz     short loc_180064FCB
0x180064fbd  mov     [rdi+48h], r14d
0x180064fc1  lea     rcx, [rdi+10h]; SRWLock
0x180064fc5  call    cs:__imp_ReleaseSRWLockExclusive
0x180064fcb  lea     rcx, [rbx+160h]; ConditionVariable
0x180064fd2  call    cs:__imp_WakeAllConditionVariable
0x180064fd8  lea     rcx, [rbx+0F8h]; this
0x180064fdf  cmp     dword ptr [rcx+8], 0
0x180064fe3  jz      short loc_180064FEA
0x180064fe5  call    ?join@thread@std@@QEAAXXZ; std::thread::join(void)
0x180064fea  mov     rcx, [rbx+0C0h]
0x180064ff1  test    rcx, rcx
0x180064ff4  jz      loc_1800650A2
0x180064ffa  mov     edx, [rbx+50h]
0x180064ffd  call    ?RemoveSession@?$CPerfMonLogger@$1?RDPPerfMonCountersGuid@@3U_GUID@@A@details@Perf@Utils@Rdp@@QEAAXI@Z; Rdp::Utils::Perf::details::CPerfMonLogger<&_GUID RDPPerfMonCountersGuid>::RemoveSession(uint)
0x180065002  xorps   xmm0, xmm0
0x180065005  movdqu  [rsp+0B8h+var_48], xmm0
0x18006500b  lea     rcx, [rbx+0E8h]
0x180065012  lea     rdx, [rsp+0B8h+var_48]
0x180065017  call    ??4?$shared_ptr@VCPerfMonSession@Perf@Utils@Rdp@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Rdp::Utils::Perf::CPerfMonSession>::operator=(std::shared_ptr<Rdp::Utils::Perf::CPerfMonSession> &&)
0x18006501c  mov     rdi, qword ptr [rsp+0B8h+var_48+8]
0x180065021  test    rdi, rdi
0x180065024  jz      short loc_18006505D
0x180065026  mov     eax, r14d
0x180065029  lock xadd [rdi+8], eax
0x18006502e  add     eax, r14d
0x180065031  jnz     short loc_18006505D
0x180065033  mov     rax, [rdi]
0x180065036  mov     rcx, rdi
0x180065039  mov     rax, [rax]
0x18006503c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065041  mov     eax, r14d
0x180065044  lock xadd [rdi+0Ch], eax
0x180065049  add     eax, r14d
0x18006504c  jnz     short loc_18006505D
0x18006504e  mov     rax, [rdi]
0x180065051  mov     rcx, rdi
0x180065054  mov     rax, [rax+8]
0x180065058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006505d  mov     rdi, [rbx+0C0h]
0x180065064  mov     qword ptr [rbx+0C0h], 0
0x18006506f  test    rdi, rdi
0x180065072  jz      short loc_1800650A2
0x180065074  lea     rcx, [rdi+48h]
0x180065078  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAXV?$shared_ptr@VCSharedFence@Graphics@Utils@Rdp@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Rdp::Utils::Graphics::CSharedFence>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Rdp::Utils::Graphics::CSharedFence>>>>>>>(void)
0x18006507d  lea     rcx, [rdi+38h]
0x180065081  call    ??1?$list@U?$pair@QEAXV?$shared_ptr@VCSharedTexture@Graphics@Utils@Rdp@@@std@@@std@@V?$allocator@U?$pair@QEAXV?$shared_ptr@VCSharedTexture@Graphics@Utils@Rdp@@@std@@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<void * const,std::shared_ptr<Rdp::Utils::Graphics::CSharedTexture>>>::~list<std::pair<void * const,std::shared_ptr<Rdp::Utils::Graphics::CSharedTexture>>>(void)
0x180065086  mov     rcx, [rdi+28h]; ProviderHandle
0x18006508a  test    rcx, rcx
0x18006508d  jz      short loc_180065095
0x18006508f  call    cs:__imp_PerfStopProvider
0x180065095  mov     edx, 0C0h
0x18006509a  mov     rcx, rdi; Block
0x18006509d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800650a2  mov     byte ptr [rbx+0B0h], 0
0x1800650a9  mov     rax, cs:WPP_GLOBAL_Control
0x1800650b0  cmp     rax, r12
0x1800650b3  jz      short loc_1800650C1
0x1800650b5  test    [rax+1Ch], sil
0x1800650b9  jz      short loc_1800650C1
0x1800650bb  cmp     byte ptr [rax+19h], 4
0x1800650bf  jnb     short loc_1800650C4
0x1800650c1  xor     sil, sil
0x1800650c4  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1800650cb  setnz   bl
0x1800650ce  test    sil, sil
0x1800650d1  jnz     short loc_1800650D7
0x1800650d3  test    bl, bl
0x1800650d5  jz      short loc_180065107
0x1800650d7  call    cs:__imp_GetCurrentThreadId
0x1800650dd  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x1800650e1  mov     [rsp+0B8h+MessageGuid], r15; MessageGuid
0x1800650e6  mov     word ptr [rsp+0B8h+var_88], 0Dh; __int16
0x1800650ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800650f4  mov     r9, [rcx+28h]; int
0x1800650f8  mov     r8b, bl; int
0x1800650fb  mov     dl, sil; int
0x1800650fe  mov     rcx, [rcx+10h]; int
0x180065102  call    WPP_RECORDER_AND_TRACE_SF_D
0x180065107  xor     eax, eax
0x180065109  jmp     short loc_180065112
0x18006510b  mov     eax, [rsp+0B8h+arg_0]
0x180065112  add     rsp, 80h
0x180065119  pop     r15
0x18006511b  pop     r14
0x18006511d  pop     r13
0x18006511f  pop     r12
0x180065121  pop     rdi
0x180065122  pop     rsi
0x180065123  pop     rbx
0x180065124  retn
0x180065125  mov     ecx, 5; int
0x18006512a  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18006512f  mov     dword ptr [rdi+4Ch], 7FFFFFFEh
0x180065136  mov     ecx, 6; int
0x18006513b  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
