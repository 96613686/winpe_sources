# StandbyMonitor::ProcessClientActivity(StandbyMonitor::ClientActivity)

- ea: `0x180015710`
- end: `0x180015aaa`
- name: `?ProcessClientActivity@StandbyMonitor@@YAXW4ClientActivity@1@@Z`
- size: `922`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `95`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180011960`
- `0x180013770`
- `0x180015e90`
- `0x180017d10`
- `0x18005eb20`
- `0x18006a620`
- `0x18006aa50`
- `0x180072720`
- `0x180072b30`
- `0x18007ebb0`
- `0x1800837d0`
- `0x180083b90`
- `0x180083c70`
- `0x180083e80`
- `0x1800842a0`
- `0x1800843d0`
- `0x1800844e0`
- `0x1800845c0`
- `0x180084ca0`
- `0x180084d90`
- `0x1800863e0`
- `0x180089060`
- `0x18008d410`
- `0x18008de90`
- `0x18008fc40`
- `0x1800909f0`
- `0x18009dc10`
- `0x18009e050`
- `0x1800a31d0`
- `0x1800a3290`
- `0x1800a4e30`
- `0x1800a6ed0`
- `0x1800bf1b0`
- `0x1800bf3f0`
- `0x1800bf5c0`
- `0x1800bf950`
- `0x1800bfb30`
- `0x1800c0050`
- `0x1800c04f0`
- `0x1800c0720`
- `0x1800c0840`
- `0x1800c0900`
- `0x1800c09f0`
- `0x1800c3e10`
- `0x1800c48e0`
- `0x1800c4e00`
- `0x1800c5ac0`
- `0x1800c5cd0`
- `0x1800c5d20`
- `0x1800c5e90`

## callees

- `0x180015710`
- `0x180015ab0`
- `0x180015ae8`
- `0x18006f500`
- `0x1800a88a0`
- `0x1800a9738`
- `0x18011e6bc`
- `0x18011e760`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001587e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001587e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180015778`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180015778`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800158ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015a30`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800158ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015a30`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180015743`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180015743`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800158cf`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800158cf`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001595c`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001595c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800159d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800159d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800159a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800159b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800159a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800159b4`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800157a8`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800157a8`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180015a0d`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180015a0d`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall StandbyMonitor::ProcessClientActivity(int a1)
{
  DWORD ProcessId; // r14d
  volatile signed __int32 *v3; // rbx
  __int64 v4; // rdi
  const char *v5; // r9
  __int64 v6; // r8
  void *v7; // [rsp+30h] [rbp-F8h] BYREF
  __m128i si128; // [rsp+40h] [rbp-E8h]
  void *v9[3]; // [rsp+50h] [rbp-D8h] BYREF
  unsigned __int64 v10; // [rsp+68h] [rbp-C0h]
  __int64 RpcCallAttributes; // [rsp+70h] [rbp-B8h] BYREF
  void *v12[3]; // [rsp+78h] [rbp-B0h] BYREF
  unsigned __int64 v13; // [rsp+90h] [rbp-98h]
  void *v14; // [rsp+98h] [rbp-90h] BYREF
  unsigned __int64 v15; // [rsp+B0h] [rbp-78h]
  DWORD v16; // [rsp+B8h] [rbp-70h]
  int v17; // [rsp+BCh] [rbp-6Ch]
  void *ppInterface; // [rsp+E0h] [rbp-48h] BYREF
  HANDLE Process; // [rsp+E8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  ProcessId = 0;
  AcquireSRWLockShared(&StandbyMonitor::details::Singleton<StandbyMonitor::StandbyMonitor>::s_lock);
  v3 = (volatile signed __int32 *)qword_1801C7098;
  if ( qword_1801C7098 )
  {
    _InterlockedIncrement((volatile signed __int32 *)qword_1801C7098 + 2);
    v3 = (volatile signed __int32 *)qword_1801C7098;
  }
  v4 = StandbyMonitor::details::Singleton<StandbyMonitor::StandbyMonitor>::s_instance;
  ReleaseSRWLockShared(&StandbyMonitor::details::Singleton<StandbyMonitor::StandbyMonitor>::s_lock);
  try
  {
    if ( !v4 )
    {
LABEL_28:
      if ( v3 && _InterlockedExchangeAdd(v3 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v3)(v3);
        std::_Ref_count_base::_Decwref((std::_Ref_count_base *)v3);
      }
      return;
    }
    if ( a1 == 96 )
    {
      RpcCallAttributes = 0x1000000002LL;
      memset_0(v12, 0, 0x68u);
      if ( !RpcServerInqCallAttributesW(0, &RpcCallAttributes) )
      {
        ProcessId = v15;
        goto LABEL_12;
      }
    }
    else
    {
      ppInterface = 0;
      if ( CoGetCallContext(&GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541, &ppInterface) >= 0 )
      {
        Process = 0;
        if ( (*(int (__fastcall **)(void *, __int64, HANDLE *))(*(_QWORD *)ppInterface + 24LL))(
               ppInterface,
               4096,
               &Process) >= 0 )
        {
          ProcessId = GetProcessId(Process);
          if ( Process )
            CloseHandle(Process);
          if ( ppInterface )
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppInterface + 16LL))(ppInterface);
        }
        else
        {
          if ( Process )
            CloseHandle(Process);
          if ( ppInterface )
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppInterface + 16LL))(ppInterface);
        }
        goto LABEL_12;
      }
      if ( ppInterface )
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppInterface + 16LL))(ppInterface);
    }
    ProcessId = GetCurrentProcessId();
LABEL_12:
    if ( a1 == 96 )
      off_1801BE0B0((StandbyMonitor *)v9);
    else
      off_1801BE0B8((StandbyMonitor *)v9);
    off_1801BE0A8(&v7, ProcessId);
    RpcCallAttributes = v4;
    std::string::string(v12, v9);
    std::string::string(&v14, v6);
    v16 = ProcessId;
    v17 = a1;
    EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 24));
    Process = (HANDLE)(v4 + 24);
    if ( *(_BYTE *)(v4 + 288) )
    {
      if ( v4 != -24 )
        LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 24));
    }
    else
    {
      if ( *(_DWORD *)(v4 + 16) == 1 )
        std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__StandbyMonitor::ProcessClientActivity_::_6_::_lambda_1___(
          v4 + 168,
          &RpcCallAttributes);
      else
        std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__StandbyMonitor::ProcessClientActivity_::_6_::_lambda_1___(
          v4 + 248,
          &RpcCallAttributes);
      if ( v4 != -24 )
        LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 24));
      _InterlockedIncrement64((volatile signed __int64 *)(v4 + 152));
      SubmitThreadpoolWork(*(PTP_WORK *)(v4 + 144));
    }
    if ( v15 > 0xF )
      std::_Deallocate<16>(v14, v15 + 1);
    if ( v13 > 0xF )
      std::_Deallocate<16>(v12[0], v13 + 1);
    if ( si128.m128i_i64[1] > 0xFuLL )
      std::_Deallocate<16>(v7, si128.m128i_i64[1] + 1);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v7) = 0;
    if ( v10 > 0xF )
      std::_Deallocate<16>(v9[0], v10 + 1);
    goto LABEL_28;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x2EC,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\standby\\lib\\standbymonitor.cpp",
      v5);
  }
}

```

## disassembly

```asm
0x180015710  push    rbx
0x180015712  push    rsi
0x180015713  push    rdi
0x180015714  push    r14
0x180015716  sub     rsp, 108h
0x18001571d  mov     rax, cs:__security_cookie
0x180015724  xor     rax, rsp
0x180015727  mov     [rsp+128h+var_38], rax
0x18001572f  mov     esi, ecx
0x180015731  xor     r14d, r14d
0x180015734  xorps   xmm0, xmm0
0x180015737  movups  [rsp+128h+var_108], xmm0
0x18001573c  lea     rcx, ?s_lock@?$Singleton@VStandbyMonitor@1@@details@StandbyMonitor@@0Vsrwlock@wil@@A; SRWLock
0x180015743  call    cs:__imp_AcquireSRWLockShared
0x180015749  mov     rbx, cs:qword_1801C7098
0x180015750  test    rbx, rbx
0x180015753  jz      short loc_180015760
0x180015755  lock inc dword ptr [rbx+8]
0x180015759  mov     rbx, cs:qword_1801C7098
0x180015760  mov     rdi, cs:?s_instance@?$Singleton@VStandbyMonitor@1@@details@StandbyMonitor@@0V?$shared_ptr@VStandbyMonitor@1@@std@@A; std::shared_ptr<StandbyMonitor::StandbyMonitor> StandbyMonitor::details::Singleton<StandbyMonitor::StandbyMonitor>::s_instance
0x180015767  mov     qword ptr [rsp+128h+var_108], rdi
0x18001576c  mov     qword ptr [rsp+128h+var_108+8], rbx
0x180015771  lea     rcx, ?s_lock@?$Singleton@VStandbyMonitor@1@@details@StandbyMonitor@@0Vsrwlock@wil@@A; SRWLock
0x180015778  call    cs:__imp_ReleaseSRWLockShared
0x18001577e  nop
0x18001577f  test    rdi, rdi
0x180015782  jz      loc_18001592B
0x180015788  cmp     esi, 60h ; '`'
0x18001578b  jz      loc_1800159E4
0x180015791  mov     [rsp+128h+ppInterface], r14
0x180015799  lea     rdx, [rsp+128h+ppInterface]; ppInterface
0x1800157a1  lea     rcx, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541; riid
0x1800157a8  call    cs:__imp_CoGetCallContext
0x1800157ae  test    eax, eax
0x1800157b0  js      loc_1800159BC
0x1800157b6  mov     [rsp+128h+Process], r14
0x1800157be  mov     rcx, [rsp+128h+ppInterface]
0x1800157c6  mov     rax, [rcx]
0x1800157c9  lea     r8, [rsp+128h+Process]
0x1800157d1  mov     edx, 1000h
0x1800157d6  mov     rax, [rax+18h]
0x1800157da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157df  mov     rcx, [rsp+128h+Process]; hObject
0x1800157e7  test    eax, eax
0x1800157e9  jns     loc_18001595C
0x1800157ef  test    rcx, rcx
0x1800157f2  jnz     loc_1800159A9
0x1800157f8  mov     rcx, [rsp+128h+ppInterface]
0x180015800  test    rcx, rcx
0x180015803  jz      short loc_180015812
0x180015805  mov     rax, [rcx]
0x180015808  mov     rax, [rax+10h]
0x18001580c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015811  nop
0x180015812  lea     rcx, [rsp+128h+var_D8]
0x180015817  cmp     esi, 60h ; '`'
0x18001581a  jnz     loc_180015A3B
0x180015820  mov     rax, cs:off_1801BE0B0
0x180015827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001582c  nop
0x18001582d  mov     edx, r14d
0x180015830  lea     rcx, [rsp+128h+var_F8]
0x180015835  mov     rax, cs:off_1801BE0A8
0x18001583c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015841  mov     r8, rax
0x180015844  mov     [rsp+128h+RpcCallAttributes], rdi
0x180015849  lea     rdx, [rsp+128h+var_D8]
0x18001584e  lea     rcx, [rsp+128h+var_B0]
0x180015853  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@$$QEAV01@@Z; std::string::string(std::string &&)
0x180015858  mov     rdx, r8
0x18001585b  lea     rcx, [rsp+128h+var_90]
0x180015863  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@$$QEAV01@@Z; std::string::string(std::string &&)
0x180015868  mov     [rsp+128h+var_70], r14d
0x180015870  mov     [rsp+128h+var_6C], esi
0x180015877  lea     rsi, [rdi+18h]
0x18001587b  mov     rcx, rsi; lpCriticalSection
0x18001587e  call    cs:__imp_EnterCriticalSection
0x180015884  mov     [rsp+128h+Process], rsi
0x18001588c  lea     rcx, [rdi+0A8h]
0x180015893  cmp     byte ptr [rcx+78h], 0
0x180015897  jnz     loc_180015A24
0x18001589d  lea     rdx, [rsp+128h+RpcCallAttributes]
0x1800158a2  cmp     dword ptr [rdi+10h], 1
0x1800158a6  jnz     loc_180015A4C
0x1800158ac  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__StandbyMonitor__ProcessClientActivity____6____lambda_1___
0x1800158b1  nop
0x1800158b2  test    rsi, rsi
0x1800158b5  jz      short loc_1800158C0
0x1800158b7  mov     rcx, rsi; lpCriticalSection
0x1800158ba  call    cs:__imp_LeaveCriticalSection
0x1800158c0  lock inc qword ptr [rdi+98h]
0x1800158c8  mov     rcx, [rdi+90h]; pwk
0x1800158cf  call    cs:__imp_SubmitThreadpoolWork
0x1800158d5  nop
0x1800158d6  mov     rdx, [rsp+128h+var_78]
0x1800158de  cmp     rdx, 0Fh
0x1800158e2  ja      loc_180015A5A
0x1800158e8  mov     rdx, [rsp+128h+var_98]
0x1800158f0  cmp     rdx, 0Fh
0x1800158f4  ja      loc_180015A6F
0x1800158fa  mov     rdx, [rsp+128h+var_E0]
0x1800158ff  cmp     rdx, 0Fh
0x180015903  ja      loc_180015A81
0x180015909  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180015911  movdqu  xmmword ptr [rsp+40h], xmm0
0x180015917  mov     byte ptr [rsp+128h+var_F8], 0
0x18001591c  mov     rdx, [rsp+128h+var_C0]
0x180015921  cmp     rdx, 0Fh
0x180015925  ja      loc_180015A93
0x18001592b  test    rbx, rbx
0x18001592e  jz      short loc_18001593F
0x180015930  mov     eax, 0FFFFFFFFh
0x180015935  lock xadd [rbx+8], eax
0x18001593a  cmp     eax, 1
0x18001593d  jz      short loc_180015991
0x18001593f  mov     rcx, [rsp+128h+var_38]
0x180015947  xor     rcx, rsp; StackCookie
0x18001594a  call    __security_check_cookie
0x18001594f  add     rsp, 108h
0x180015956  pop     r14
0x180015958  pop     rdi
0x180015959  pop     rsi
0x18001595a  pop     rbx
0x18001595b  retn
0x18001595c  call    cs:__imp_GetProcessId
0x180015962  mov     r14d, eax
0x180015965  mov     rcx, [rsp+128h+Process]; hObject
0x18001596d  test    rcx, rcx
0x180015970  jnz     short loc_1800159B4
0x180015972  mov     rcx, [rsp+128h+ppInterface]
0x18001597a  test    rcx, rcx
0x18001597d  jz      short loc_18001598C
0x18001597f  mov     rax, [rcx]
0x180015982  mov     rax, [rax+10h]
0x180015986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001598b  nop
0x18001598c  jmp     loc_180015812
0x180015991  mov     rax, [rbx]
0x180015994  mov     rcx, rbx
0x180015997  mov     rax, [rax]
0x18001599a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001599f  mov     rcx, rbx; this
0x1800159a2  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x1800159a7  jmp     short loc_18001593F
0x1800159a9  call    cs:__imp_CloseHandle
0x1800159af  jmp     loc_1800157F8
0x1800159b4  call    cs:__imp_CloseHandle
0x1800159ba  jmp     short loc_180015972
0x1800159bc  mov     rcx, [rsp+128h+ppInterface]
0x1800159c4  test    rcx, rcx
0x1800159c7  jz      short loc_1800159D6
0x1800159c9  mov     rax, [rcx]
0x1800159cc  mov     rax, [rax+10h]
0x1800159d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159d5  nop
0x1800159d6  call    cs:__imp_GetCurrentProcessId
0x1800159dc  mov     r14d, eax
0x1800159df  jmp     loc_180015812
0x1800159e4  mov     dword ptr [rsp+128h+RpcCallAttributes], 2
0x1800159ec  mov     dword ptr [rsp+128h+RpcCallAttributes+4], 10h
0x1800159f4  xor     edx, edx; Val
0x1800159f6  mov     r8d, 68h ; 'h'; Size
0x1800159fc  lea     rcx, [rsp+128h+var_B0]; void *
0x180015a01  call    memset_0
0x180015a06  lea     rdx, [rsp+128h+RpcCallAttributes]; RpcCallAttributes
0x180015a0b  xor     ecx, ecx; ClientBinding
0x180015a0d  call    cs:__imp_RpcServerInqCallAttributesW
0x180015a13  test    eax, eax
0x180015a15  jnz     short loc_1800159D6
0x180015a17  mov     r14d, dword ptr [rsp+128h+var_78]
0x180015a1f  jmp     loc_180015812
0x180015a24  test    rsi, rsi
0x180015a27  jz      loc_1800158D6
0x180015a2d  mov     rcx, rsi; lpCriticalSection
0x180015a30  call    cs:__imp_LeaveCriticalSection
0x180015a36  jmp     loc_1800158D6
0x180015a3b  mov     rax, cs:off_1801BE0B8
0x180015a42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a47  jmp     loc_18001582D
0x180015a4c  add     rcx, 50h ; 'P'
0x180015a50  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__StandbyMonitor__ProcessClientActivity____6____lambda_1___
0x180015a55  jmp     loc_1800158B2
0x180015a5a  inc     rdx
0x180015a5d  mov     rcx, [rsp+128h+var_90]
0x180015a65  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180015a6a  jmp     loc_1800158E8
0x180015a6f  inc     rdx
0x180015a72  mov     rcx, [rsp+128h+var_B0]
0x180015a77  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180015a7c  jmp     loc_1800158FA
0x180015a81  inc     rdx
0x180015a84  mov     rcx, [rsp+128h+var_F8]
0x180015a89  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180015a8e  jmp     loc_180015909
0x180015a93  inc     rdx
0x180015a96  mov     rcx, [rsp+128h+var_D8]
0x180015a9b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180015aa0  jmp     loc_18001592B
0x180015aa5  jmp     loc_18001593F
```
