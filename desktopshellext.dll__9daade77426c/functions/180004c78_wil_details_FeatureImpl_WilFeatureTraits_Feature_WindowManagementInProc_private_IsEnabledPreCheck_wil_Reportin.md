# wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowManagementInProc>::__private_IsEnabledPreCheck(wil::ReportingKind)

- ea: `0x180004c78`
- end: `0x180004f82`
- name: `?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowManagementInProc@@@details@wil@@QEAA_NW4ReportingKind@3@@Z`
- size: `778`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004b24`

## callees

- `0x180002cf0`
- `0x180002d90`
- `0x180004900`
- `0x180004950`
- `0x180004980`
- `0x180004a10`
- `0x180004c78`
- `0x1800055b0`
- `0x1800055d8`
- `0x18000d2a0`
- `0x180015eb8`
- `0x180023fd0`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004ddd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004eb2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004ddd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004eb2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004e87`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004ee7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004e87`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004ee7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004e4d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004e4d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowManagementInProc>::__private_IsEnabledPreCheck(
        volatile signed __int32 *a1,
        char a2,
        __int64 a3,
        unsigned int a4)
{
  unsigned int v5; // edi
  signed __int32 v6; // esi
  unsigned int v7; // r15d
  __int64 v8; // rcx
  __int16 v9; // bx
  signed __int32 v10; // eax
  wil *i; // rcx
  signed __int32 v12; // edx
  BOOL v13; // r14d
  unsigned __int32 v14; // eax
  unsigned int v15; // esi
  wil *v16; // rcx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  void *v18; // r9
  const char *v20; // [rsp+20h] [rbp-60h]
  _QWORD v21[2]; // [rsp+50h] [rbp-30h] BYREF
  unsigned int v22[4]; // [rsp+60h] [rbp-20h]
  __int64 v23; // [rsp+C0h] [rbp+40h] BYREF
  int v24; // [rsp+C8h] [rbp+48h] BYREF
  int v25; // [rsp+D0h] [rbp+50h] BYREF
  __int16 v26; // [rsp+D4h] [rbp+54h]
  char v27; // [rsp+D8h] [rbp+58h] BYREF

  LOBYTE(v24) = a2;
  v5 = *(_DWORD *)Feature_WindowManagementInProc__descriptor;
  if ( (*(_DWORD *)Feature_WindowManagementInProc__descriptor & 4) == 0 )
  {
    v6 = *(_DWORD *)Feature_WindowManagementInProc__descriptor;
    if ( (*(_BYTE *)Feature_WindowManagementInProc__descriptor & 6) == 6 )
    {
      v5 = *(_DWORD *)Feature_WindowManagementInProc__descriptor;
    }
    else
    {
      v7 = wil::details::EnsureSubscribedToFeatureConfigurationChanges((wil::details *)a1);
      v24 = 0;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowManagementInProc>::GetCurrentFeatureEnabledState(
        v8,
        &v23,
        &v24);
      v9 = v23;
      while ( 1 )
      {
        v5 = v6;
        if ( v24 && (v6 & 2) == 0 )
          v5 = v9 & 0x9C1 | v6 & 0xFFFFF63E | 2;
        if ( (v6 & 4) == 0 )
          v5 = v9 & 0x400 | v5 & 0xFFFFFBFF | 4;
        v10 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_WindowManagementInProc__descriptor, v5, v6);
        if ( v6 == v10 )
          break;
        v6 = v10;
      }
      if ( (v6 & 4) == 0 )
        wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
          Feature_WindowManagementInProc__descriptor,
          3,
          v7);
      if ( (v5 & 2) == 0 )
        v5 = v9 & 0x9C1 | v5 & 0xFFFFF63E;
    }
  }
  v25 = 0;
  v26 = 3;
  LODWORD(v23) = 3;
  *(_OWORD *)v22 = 0;
  for ( i = (wil *)*((unsigned int *)a1 + 2); ; i = (wil *)v14 )
  {
    v12 = (unsigned int)i | 2;
    v13 = ((unsigned int)i | 2) == (_DWORD)i;
    if ( ((unsigned int)i | 2) != (_DWORD)i )
      v12 = (unsigned int)i | 3;
    v14 = _InterlockedCompareExchange(a1 + 2, v12, (signed __int32)i);
    if ( (_DWORD)i == v14 )
      break;
  }
  LOBYTE(i) = ((unsigned __int8)i & 1) == 0;
  v15 = v22[1];
  if ( ((unsigned __int8)i & ((v12 & 1) != 0)) != 0
    && wil::details::g_enabledStateManager
    && !wil::ProcessShutdownInProgress(i) )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( wil::details::g_enabledStateManager )
    {
      if ( !wil::ProcessShutdownInProgress(v16) )
      {
        v21[0] = 24406318;
        v21[1] = a1 + 2;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800ACD88, v21, 0x10u);
        if ( !byte_1800ACD80 )
        {
          if ( !qword_1800ACD78 )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v27);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                &wil::details::g_enabledStateManager,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              (struct _TP_TIMER **)&qword_1800ACD78,
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v27);
          }
          wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)&qword_1800ACD78, &byte_1800ACD80, 300000);
        }
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( v15 )
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x174692E, v22[2], v15, a4, v20);
  if ( !v13 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_1800ACDD0 )
    {
      qword_1800ACDD0 = 0;
      wil::details::WilApi_SubscribeFeatureStateChangeNotification(
        (wil::details *)&qword_1800ACDD0,
        (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **)_lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_,
        (void (*)(void *))0xFFFFFFFFFFFFFFFFLL,
        v18);
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( (v5 & 0x400) != 0 )
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x174692E, ((v5 & 0xFFFFF800) << 20) | 2, 0, a4, v20);
  if ( !v13 )
  {
    if ( g_wil_details_realtimeFeatureUsageHook )
    {
      LOBYTE(a3) = 3;
      g_wil_details_realtimeFeatureUsageHook(24406318, 2, a3);
    }
    if ( g_wil_details_pfnFeatureLoggingHook )
      g_wil_details_pfnFeatureLoggingHook(24406318, &v25, 0, 1, &v23, 0, 0, 1);
  }
  return 1;
}

```

## disassembly

```asm
0x180004c78  mov     byte ptr [rsp-38h+arg_8], dl
0x180004c7c  push    rbp
0x180004c7d  push    rbx
0x180004c7e  push    rsi
0x180004c7f  push    rdi
0x180004c80  push    r13
0x180004c82  push    r14
0x180004c84  push    r15
0x180004c86  mov     rbp, rsp
0x180004c89  sub     rsp, 80h
0x180004c90  mov     r13, rcx
0x180004c93  mov     rax, cs:Feature_WindowManagementInProc__descriptor
0x180004c9a  mov     edi, [rax]
0x180004c9c  test    dil, 4
0x180004ca0  jnz     loc_180004D4E
0x180004ca6  mov     r14, cs:Feature_WindowManagementInProc__descriptor
0x180004cad  mov     esi, [r14]
0x180004cb0  mov     eax, esi
0x180004cb2  and     eax, 6
0x180004cb5  cmp     al, 6
0x180004cb7  jz      loc_180004D4C
0x180004cbd  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180004cc2  mov     r15d, eax
0x180004cc5  mov     [rbp+arg_8], 0
0x180004ccc  lea     r8, [rbp+arg_8]
0x180004cd0  lea     rdx, [rbp+arg_0]
0x180004cd4  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowManagementInProc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowManagementInProc>::GetCurrentFeatureEnabledState(int *)
0x180004cd9  mov     rbx, [rbp+arg_0]
0x180004cdd  mov     edi, esi
0x180004cdf  cmp     [rbp+arg_8], 0
0x180004ce3  jz      short loc_180004CFD
0x180004ce5  test    sil, 2
0x180004ce9  jnz     short loc_180004CFD
0x180004ceb  and     edi, 0FFFFF63Eh
0x180004cf1  mov     eax, ebx
0x180004cf3  and     eax, 9C1h
0x180004cf8  or      edi, eax
0x180004cfa  or      edi, 2
0x180004cfd  test    sil, 4
0x180004d01  jnz     short loc_180004D13
0x180004d03  btr     edi, 0Ah
0x180004d07  mov     eax, ebx
0x180004d09  and     eax, 400h
0x180004d0e  or      edi, eax
0x180004d10  or      edi, 4
0x180004d13  mov     eax, esi
0x180004d15  lock cmpxchg [r14], edi
0x180004d1a  jz      short loc_180004D20
0x180004d1c  mov     esi, eax
0x180004d1e  jmp     short loc_180004CDD
0x180004d20  test    sil, 4
0x180004d24  jnz     short loc_180004D36
0x180004d26  mov     r8d, r15d
0x180004d29  mov     edx, 3
0x180004d2e  mov     rcx, r14
0x180004d31  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180004d36  test    dil, 2
0x180004d3a  jnz     short loc_180004D4E
0x180004d3c  and     edi, 0FFFFF63Eh
0x180004d42  and     ebx, 9C1h
0x180004d48  or      edi, ebx
0x180004d4a  jmp     short loc_180004D4E
0x180004d4c  mov     edi, esi
0x180004d4e  xor     eax, eax
0x180004d50  mov     [rbp+arg_10], eax
0x180004d53  mov     [rbp+arg_14], 3
0x180004d59  mov     dword ptr [rbp+arg_0], 3
0x180004d60  lea     rbx, [r13+8]
0x180004d64  xorps   xmm0, xmm0
0x180004d67  movups  xmmword ptr [rbp+var_20], xmm0
0x180004d6b  mov     ecx, [rbx]
0x180004d6d  mov     edx, ecx
0x180004d6f  or      edx, 2
0x180004d72  xor     r14d, r14d
0x180004d75  cmp     edx, ecx
0x180004d77  setz    r14b
0x180004d7b  mov     eax, edx
0x180004d7d  or      eax, 1
0x180004d80  cmp     edx, ecx
0x180004d82  cmovnz  edx, eax
0x180004d85  mov     eax, ecx
0x180004d87  lock cmpxchg [rbx], edx
0x180004d8b  jz      short loc_180004D91
0x180004d8d  mov     ecx, eax
0x180004d8f  jmp     short loc_180004D6D
0x180004d91  test    cl, 1
0x180004d94  setz    cl; this
0x180004d97  test    dl, 1
0x180004d9a  setnz   al
0x180004d9d  test    al, cl
0x180004d9f  mov     eax, 0
0x180004da4  setnz   al
0x180004da7  mov     esi, [rbp+var_20+4]
0x180004daa  lea     r15, SRWLock
0x180004db1  mov     r13d, 174692Eh
0x180004db7  test    eax, eax
0x180004db9  jz      loc_180004E8E
0x180004dbf  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180004dc5  test    eax, eax
0x180004dc7  jz      loc_180004E8E
0x180004dcd  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180004dd2  test    al, al
0x180004dd4  jnz     loc_180004E8E
0x180004dda  mov     rcx, r15; SRWLock
0x180004ddd  call    cs:__imp_AcquireSRWLockExclusive
0x180004de3  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180004de9  test    eax, eax
0x180004deb  jz      loc_180004E84
0x180004df1  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180004df6  test    al, al
0x180004df8  jnz     loc_180004E84
0x180004dfe  mov     [rbp+var_30], 174692Eh
0x180004e06  mov     [rbp+var_28], rbx
0x180004e0a  mov     r8d, 10h; unsigned __int64
0x180004e10  lea     rdx, [rbp+var_30]; void *
0x180004e14  lea     rcx, qword_1800ACD88; this
0x180004e1b  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180004e20  cmp     cs:byte_1800ACD80, 0
0x180004e27  jnz     short loc_180004E84
0x180004e29  cmp     cs:qword_1800ACD78, 0
0x180004e31  jnz     short loc_180004E6B
0x180004e33  lea     rcx, [rbp+arg_18]; this
0x180004e37  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180004e3c  xor     r8d, r8d; pcbe
0x180004e3f  lea     rdx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180004e46  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180004e4d  call    cs:__imp_CreateThreadpoolTimer
0x180004e53  mov     rdx, rax
0x180004e56  lea     rcx, qword_1800ACD78
0x180004e5d  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180004e62  lea     rcx, [rbp+arg_18]; this
0x180004e66  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180004e6b  mov     r8d, 493E0h
0x180004e71  lea     rdx, byte_1800ACD80
0x180004e78  lea     rcx, qword_1800ACD78
0x180004e7f  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180004e84  mov     rcx, r15; SRWLock
0x180004e87  call    cs:__imp_ReleaseSRWLockExclusive
0x180004e8d  nop
0x180004e8e  test    esi, esi
0x180004e90  jz      short loc_180004EA0
0x180004e92  mov     r8d, esi; unsigned int
0x180004e95  mov     edx, [rbp+var_20+8]; unsigned int
0x180004e98  mov     ecx, r13d; this
0x180004e9b  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180004ea0  test    r14d, r14d
0x180004ea3  jnz     short loc_180004EEE
0x180004ea5  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180004eab  test    eax, eax
0x180004ead  jz      short loc_180004EEE
0x180004eaf  mov     rcx, r15; SRWLock
0x180004eb2  call    cs:__imp_AcquireSRWLockExclusive
0x180004eb8  cmp     cs:qword_1800ACDD0, 0
0x180004ec0  jnz     short loc_180004EE4
0x180004ec2  mov     cs:qword_1800ACDD0, 0
0x180004ecd  or      r8, 0FFFFFFFFFFFFFFFFh; void (*)(void *)
0x180004ed1  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180004ed8  lea     rcx, qword_1800ACDD0; this
0x180004edf  call    ?WilApi_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details::WilApi_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180004ee4  mov     rcx, r15; SRWLock
0x180004ee7  call    cs:__imp_ReleaseSRWLockExclusive
0x180004eed  nop
0x180004eee  bt      edi, 0Ah
0x180004ef2  jnb     short loc_180004F0D
0x180004ef4  and     edi, 0FFFFF800h
0x180004efa  shl     edi, 14h
0x180004efd  or      edi, 2
0x180004f00  xor     r8d, r8d; unsigned int
0x180004f03  mov     edx, edi; unsigned int
0x180004f05  mov     ecx, r13d; this
0x180004f08  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180004f0d  test    r14d, r14d
0x180004f10  jnz     short loc_180004F6E
0x180004f12  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180004f19  test    rax, rax
0x180004f1c  jz      short loc_180004F2D
0x180004f1e  mov     r8b, 3
0x180004f21  lea     edx, [r14+2]
0x180004f25  mov     ecx, r13d
0x180004f28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f2d  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180004f34  test    rax, rax
0x180004f37  jz      short loc_180004F6E
0x180004f39  mov     [rsp+80h+var_48], 1
0x180004f42  mov     [rsp+80h+var_50], 0
0x180004f47  mov     [rsp+80h+var_58], 0
0x180004f50  lea     rdx, [rbp+arg_0]
0x180004f54  mov     [rsp+80h+var_60], rdx
0x180004f59  mov     r9d, 1
0x180004f5f  xor     r8d, r8d
0x180004f62  lea     rdx, [rbp+arg_10]
0x180004f66  mov     ecx, r13d
0x180004f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f6e  mov     al, 1
0x180004f70  add     rsp, 80h
0x180004f77  pop     r15
0x180004f79  pop     r14
0x180004f7b  pop     r13
0x180004f7d  pop     rdi
0x180004f7e  pop     rsi
0x180004f7f  pop     rbx
0x180004f80  pop     rbp
0x180004f81  retn
```
