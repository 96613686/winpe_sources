# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ViewManagerPhaseout>::__private_IsEnabledPreCheck(wil::ReportingKind)

- ea: `0x180005298`
- end: `0x1800055a2`
- name: `?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_ViewManagerPhaseout@@@details@wil@@QEAA_NW4ReportingKind@3@@Z`
- size: `778`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022d5c`

## callees

- `0x180002cf0`
- `0x180002d90`
- `0x180004900`
- `0x180004950`
- `0x180004980`
- `0x180004a10`
- `0x180005298`
- `0x1800055b0`
- `0x1800055d8`
- `0x18000d2a0`
- `0x180015eb8`
- `0x180023f54`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800053fd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800054d2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800053fd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800054d2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800054a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005507`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800054a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005507`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000546d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000546d`

## pseudocode

```c
char __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ViewManagerPhaseout>::__private_IsEnabledPreCheck(
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
  v5 = *(_DWORD *)Feature_ViewManagerPhaseout__descriptor;
  if ( (*(_DWORD *)Feature_ViewManagerPhaseout__descriptor & 4) == 0 )
  {
    v6 = *(_DWORD *)Feature_ViewManagerPhaseout__descriptor;
    if ( (*(_BYTE *)Feature_ViewManagerPhaseout__descriptor & 6) == 6 )
    {
      v5 = *(_DWORD *)Feature_ViewManagerPhaseout__descriptor;
    }
    else
    {
      v7 = wil::details::EnsureSubscribedToFeatureConfigurationChanges((wil::details *)a1);
      v24 = 0;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_ViewManagerPhaseout>::GetCurrentFeatureEnabledState(
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
        v10 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ViewManagerPhaseout__descriptor, v5, v6);
        if ( v6 == v10 )
          break;
        v6 = v10;
      }
      if ( (v6 & 4) == 0 )
        wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_ViewManagerPhaseout__descriptor, 3, v7);
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
        v21[0] = 26832353;
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
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x1996DE1, v22[2], v15, a4, v20);
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
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x1996DE1, ((v5 & 0xFFFFF800) << 20) | 2, 0, a4, v20);
  if ( !v13 )
  {
    if ( g_wil_details_realtimeFeatureUsageHook )
    {
      LOBYTE(a3) = 3;
      g_wil_details_realtimeFeatureUsageHook(26832353, 2, a3);
    }
    if ( g_wil_details_pfnFeatureLoggingHook )
      g_wil_details_pfnFeatureLoggingHook(26832353, &v25, 0, 1, &v23, 0, 0, 1);
  }
  return 1;
}

```

## disassembly

```asm
0x180005298  mov     byte ptr [rsp-38h+arg_8], dl
0x18000529c  push    rbp
0x18000529d  push    rbx
0x18000529e  push    rsi
0x18000529f  push    rdi
0x1800052a0  push    r13
0x1800052a2  push    r14
0x1800052a4  push    r15
0x1800052a6  mov     rbp, rsp
0x1800052a9  sub     rsp, 80h
0x1800052b0  mov     r13, rcx
0x1800052b3  mov     rax, cs:Feature_ViewManagerPhaseout__descriptor
0x1800052ba  mov     edi, [rax]
0x1800052bc  test    dil, 4
0x1800052c0  jnz     loc_18000536E
0x1800052c6  mov     r14, cs:Feature_ViewManagerPhaseout__descriptor
0x1800052cd  mov     esi, [r14]
0x1800052d0  mov     eax, esi
0x1800052d2  and     eax, 6
0x1800052d5  cmp     al, 6
0x1800052d7  jz      loc_18000536C
0x1800052dd  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800052e2  mov     r15d, eax
0x1800052e5  mov     [rbp+arg_8], 0
0x1800052ec  lea     r8, [rbp+arg_8]
0x1800052f0  lea     rdx, [rbp+arg_0]
0x1800052f4  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ViewManagerPhaseout@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ViewManagerPhaseout>::GetCurrentFeatureEnabledState(int *)
0x1800052f9  mov     rbx, [rbp+arg_0]
0x1800052fd  mov     edi, esi
0x1800052ff  cmp     [rbp+arg_8], 0
0x180005303  jz      short loc_18000531D
0x180005305  test    sil, 2
0x180005309  jnz     short loc_18000531D
0x18000530b  and     edi, 0FFFFF63Eh
0x180005311  mov     eax, ebx
0x180005313  and     eax, 9C1h
0x180005318  or      edi, eax
0x18000531a  or      edi, 2
0x18000531d  test    sil, 4
0x180005321  jnz     short loc_180005333
0x180005323  btr     edi, 0Ah
0x180005327  mov     eax, ebx
0x180005329  and     eax, 400h
0x18000532e  or      edi, eax
0x180005330  or      edi, 4
0x180005333  mov     eax, esi
0x180005335  lock cmpxchg [r14], edi
0x18000533a  jz      short loc_180005340
0x18000533c  mov     esi, eax
0x18000533e  jmp     short loc_1800052FD
0x180005340  test    sil, 4
0x180005344  jnz     short loc_180005356
0x180005346  mov     r8d, r15d
0x180005349  mov     edx, 3
0x18000534e  mov     rcx, r14
0x180005351  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180005356  test    dil, 2
0x18000535a  jnz     short loc_18000536E
0x18000535c  and     edi, 0FFFFF63Eh
0x180005362  and     ebx, 9C1h
0x180005368  or      edi, ebx
0x18000536a  jmp     short loc_18000536E
0x18000536c  mov     edi, esi
0x18000536e  xor     eax, eax
0x180005370  mov     [rbp+arg_10], eax
0x180005373  mov     [rbp+arg_14], 3
0x180005379  mov     dword ptr [rbp+arg_0], 3
0x180005380  lea     rbx, [r13+8]
0x180005384  xorps   xmm0, xmm0
0x180005387  movups  xmmword ptr [rbp+var_20], xmm0
0x18000538b  mov     ecx, [rbx]
0x18000538d  mov     edx, ecx
0x18000538f  or      edx, 2
0x180005392  xor     r14d, r14d
0x180005395  cmp     edx, ecx
0x180005397  setz    r14b
0x18000539b  mov     eax, edx
0x18000539d  or      eax, 1
0x1800053a0  cmp     edx, ecx
0x1800053a2  cmovnz  edx, eax
0x1800053a5  mov     eax, ecx
0x1800053a7  lock cmpxchg [rbx], edx
0x1800053ab  jz      short loc_1800053B1
0x1800053ad  mov     ecx, eax
0x1800053af  jmp     short loc_18000538D
0x1800053b1  test    cl, 1
0x1800053b4  setz    cl; this
0x1800053b7  test    dl, 1
0x1800053ba  setnz   al
0x1800053bd  test    al, cl
0x1800053bf  mov     eax, 0
0x1800053c4  setnz   al
0x1800053c7  mov     esi, [rbp+var_20+4]
0x1800053ca  lea     r15, SRWLock
0x1800053d1  mov     r13d, 1996DE1h
0x1800053d7  test    eax, eax
0x1800053d9  jz      loc_1800054AE
0x1800053df  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800053e5  test    eax, eax
0x1800053e7  jz      loc_1800054AE
0x1800053ed  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800053f2  test    al, al
0x1800053f4  jnz     loc_1800054AE
0x1800053fa  mov     rcx, r15; SRWLock
0x1800053fd  call    cs:__imp_AcquireSRWLockExclusive
0x180005403  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180005409  test    eax, eax
0x18000540b  jz      loc_1800054A4
0x180005411  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180005416  test    al, al
0x180005418  jnz     loc_1800054A4
0x18000541e  mov     [rbp+var_30], 1996DE1h
0x180005426  mov     [rbp+var_28], rbx
0x18000542a  mov     r8d, 10h; unsigned __int64
0x180005430  lea     rdx, [rbp+var_30]; void *
0x180005434  lea     rcx, qword_1800ACD88; this
0x18000543b  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180005440  cmp     cs:byte_1800ACD80, 0
0x180005447  jnz     short loc_1800054A4
0x180005449  cmp     cs:qword_1800ACD78, 0
0x180005451  jnz     short loc_18000548B
0x180005453  lea     rcx, [rbp+arg_18]; this
0x180005457  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000545c  xor     r8d, r8d; pcbe
0x18000545f  lea     rdx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180005466  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000546d  call    cs:__imp_CreateThreadpoolTimer
0x180005473  mov     rdx, rax
0x180005476  lea     rcx, qword_1800ACD78
0x18000547d  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180005482  lea     rcx, [rbp+arg_18]; this
0x180005486  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000548b  mov     r8d, 493E0h
0x180005491  lea     rdx, byte_1800ACD80
0x180005498  lea     rcx, qword_1800ACD78
0x18000549f  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800054a4  mov     rcx, r15; SRWLock
0x1800054a7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800054ad  nop
0x1800054ae  test    esi, esi
0x1800054b0  jz      short loc_1800054C0
0x1800054b2  mov     r8d, esi; unsigned int
0x1800054b5  mov     edx, [rbp+var_20+8]; unsigned int
0x1800054b8  mov     ecx, r13d; this
0x1800054bb  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x1800054c0  test    r14d, r14d
0x1800054c3  jnz     short loc_18000550E
0x1800054c5  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800054cb  test    eax, eax
0x1800054cd  jz      short loc_18000550E
0x1800054cf  mov     rcx, r15; SRWLock
0x1800054d2  call    cs:__imp_AcquireSRWLockExclusive
0x1800054d8  cmp     cs:qword_1800ACDD0, 0
0x1800054e0  jnz     short loc_180005504
0x1800054e2  mov     cs:qword_1800ACDD0, 0
0x1800054ed  or      r8, 0FFFFFFFFFFFFFFFFh; void (*)(void *)
0x1800054f1  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800054f8  lea     rcx, qword_1800ACDD0; this
0x1800054ff  call    ?WilApi_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details::WilApi_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180005504  mov     rcx, r15; SRWLock
0x180005507  call    cs:__imp_ReleaseSRWLockExclusive
0x18000550d  nop
0x18000550e  bt      edi, 0Ah
0x180005512  jnb     short loc_18000552D
0x180005514  and     edi, 0FFFFF800h
0x18000551a  shl     edi, 14h
0x18000551d  or      edi, 2
0x180005520  xor     r8d, r8d; unsigned int
0x180005523  mov     edx, edi; unsigned int
0x180005525  mov     ecx, r13d; this
0x180005528  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18000552d  test    r14d, r14d
0x180005530  jnz     short loc_18000558E
0x180005532  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180005539  test    rax, rax
0x18000553c  jz      short loc_18000554D
0x18000553e  mov     r8b, 3
0x180005541  lea     edx, [r14+2]
0x180005545  mov     ecx, r13d
0x180005548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000554d  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180005554  test    rax, rax
0x180005557  jz      short loc_18000558E
0x180005559  mov     [rsp+80h+var_48], 1
0x180005562  mov     [rsp+80h+var_50], 0
0x180005567  mov     [rsp+80h+var_58], 0
0x180005570  lea     rdx, [rbp+arg_0]
0x180005574  mov     [rsp+80h+var_60], rdx
0x180005579  mov     r9d, 1
0x18000557f  xor     r8d, r8d
0x180005582  lea     rdx, [rbp+arg_10]
0x180005586  mov     ecx, r13d
0x180005589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000558e  mov     al, 1
0x180005590  add     rsp, 80h
0x180005597  pop     r15
0x180005599  pop     r14
0x18000559b  pop     r13
0x18000559d  pop     rdi
0x18000559e  pop     rsi
0x18000559f  pop     rbx
0x1800055a0  pop     rbp
0x1800055a1  retn
```
