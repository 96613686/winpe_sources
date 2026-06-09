# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CShellOnWindowManagerIDK>::__private_IsEnabledPreCheck(wil::ReportingKind)

- ea: `0x180004f88`
- end: `0x180005292`
- name: `?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_CShellOnWindowManagerIDK@@@details@wil@@QEAA_NW4ReportingKind@3@@Z`
- size: `778`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800034f0`

## callees

- `0x180002cf0`
- `0x180002d90`
- `0x180004900`
- `0x180004950`
- `0x180004980`
- `0x180004a10`
- `0x180004f88`
- `0x1800055b0`
- `0x1800055d8`
- `0x18000d2a0`
- `0x180015eb8`
- `0x180023ed8`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800050ed`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800051c2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800050ed`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800051c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005197`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800051f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005197`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800051f7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000515d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000515d`

## pseudocode

```c
char __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CShellOnWindowManagerIDK>::__private_IsEnabledPreCheck(
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
  v5 = *(_DWORD *)Feature_CShellOnWindowManagerIDK__descriptor;
  if ( (*(_DWORD *)Feature_CShellOnWindowManagerIDK__descriptor & 4) == 0 )
  {
    v6 = *(_DWORD *)Feature_CShellOnWindowManagerIDK__descriptor;
    if ( (*(_BYTE *)Feature_CShellOnWindowManagerIDK__descriptor & 6) == 6 )
    {
      v5 = *(_DWORD *)Feature_CShellOnWindowManagerIDK__descriptor;
    }
    else
    {
      v7 = wil::details::EnsureSubscribedToFeatureConfigurationChanges((wil::details *)a1);
      v24 = 0;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_CShellOnWindowManagerIDK>::GetCurrentFeatureEnabledState(
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
        v10 = _InterlockedCompareExchange(
                (volatile signed __int32 *)Feature_CShellOnWindowManagerIDK__descriptor,
                v5,
                v6);
        if ( v6 == v10 )
          break;
        v6 = v10;
      }
      if ( (v6 & 4) == 0 )
        wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
          Feature_CShellOnWindowManagerIDK__descriptor,
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
        v21[0] = 22855141;
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
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x15CBDE5, v22[2], v15, a4, v20);
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
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x15CBDE5, ((v5 & 0xFFFFF800) << 20) | 2, 0, a4, v20);
  if ( !v13 )
  {
    if ( g_wil_details_realtimeFeatureUsageHook )
    {
      LOBYTE(a3) = 3;
      g_wil_details_realtimeFeatureUsageHook(22855141, 2, a3);
    }
    if ( g_wil_details_pfnFeatureLoggingHook )
      g_wil_details_pfnFeatureLoggingHook(22855141, &v25, 0, 1, &v23, 0, 0, 1);
  }
  return 1;
}

```

## disassembly

```asm
0x180004f88  mov     byte ptr [rsp-38h+arg_8], dl
0x180004f8c  push    rbp
0x180004f8d  push    rbx
0x180004f8e  push    rsi
0x180004f8f  push    rdi
0x180004f90  push    r13
0x180004f92  push    r14
0x180004f94  push    r15
0x180004f96  mov     rbp, rsp
0x180004f99  sub     rsp, 80h
0x180004fa0  mov     r13, rcx
0x180004fa3  mov     rax, cs:Feature_CShellOnWindowManagerIDK__descriptor
0x180004faa  mov     edi, [rax]
0x180004fac  test    dil, 4
0x180004fb0  jnz     loc_18000505E
0x180004fb6  mov     r14, cs:Feature_CShellOnWindowManagerIDK__descriptor
0x180004fbd  mov     esi, [r14]
0x180004fc0  mov     eax, esi
0x180004fc2  and     eax, 6
0x180004fc5  cmp     al, 6
0x180004fc7  jz      loc_18000505C
0x180004fcd  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180004fd2  mov     r15d, eax
0x180004fd5  mov     [rbp+arg_8], 0
0x180004fdc  lea     r8, [rbp+arg_8]
0x180004fe0  lea     rdx, [rbp+arg_0]
0x180004fe4  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CShellOnWindowManagerIDK@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CShellOnWindowManagerIDK>::GetCurrentFeatureEnabledState(int *)
0x180004fe9  mov     rbx, [rbp+arg_0]
0x180004fed  mov     edi, esi
0x180004fef  cmp     [rbp+arg_8], 0
0x180004ff3  jz      short loc_18000500D
0x180004ff5  test    sil, 2
0x180004ff9  jnz     short loc_18000500D
0x180004ffb  and     edi, 0FFFFF63Eh
0x180005001  mov     eax, ebx
0x180005003  and     eax, 9C1h
0x180005008  or      edi, eax
0x18000500a  or      edi, 2
0x18000500d  test    sil, 4
0x180005011  jnz     short loc_180005023
0x180005013  btr     edi, 0Ah
0x180005017  mov     eax, ebx
0x180005019  and     eax, 400h
0x18000501e  or      edi, eax
0x180005020  or      edi, 4
0x180005023  mov     eax, esi
0x180005025  lock cmpxchg [r14], edi
0x18000502a  jz      short loc_180005030
0x18000502c  mov     esi, eax
0x18000502e  jmp     short loc_180004FED
0x180005030  test    sil, 4
0x180005034  jnz     short loc_180005046
0x180005036  mov     r8d, r15d
0x180005039  mov     edx, 3
0x18000503e  mov     rcx, r14
0x180005041  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180005046  test    dil, 2
0x18000504a  jnz     short loc_18000505E
0x18000504c  and     edi, 0FFFFF63Eh
0x180005052  and     ebx, 9C1h
0x180005058  or      edi, ebx
0x18000505a  jmp     short loc_18000505E
0x18000505c  mov     edi, esi
0x18000505e  xor     eax, eax
0x180005060  mov     [rbp+arg_10], eax
0x180005063  mov     [rbp+arg_14], 3
0x180005069  mov     dword ptr [rbp+arg_0], 3
0x180005070  lea     rbx, [r13+8]
0x180005074  xorps   xmm0, xmm0
0x180005077  movups  xmmword ptr [rbp+var_20], xmm0
0x18000507b  mov     ecx, [rbx]
0x18000507d  mov     edx, ecx
0x18000507f  or      edx, 2
0x180005082  xor     r14d, r14d
0x180005085  cmp     edx, ecx
0x180005087  setz    r14b
0x18000508b  mov     eax, edx
0x18000508d  or      eax, 1
0x180005090  cmp     edx, ecx
0x180005092  cmovnz  edx, eax
0x180005095  mov     eax, ecx
0x180005097  lock cmpxchg [rbx], edx
0x18000509b  jz      short loc_1800050A1
0x18000509d  mov     ecx, eax
0x18000509f  jmp     short loc_18000507D
0x1800050a1  test    cl, 1
0x1800050a4  setz    cl; this
0x1800050a7  test    dl, 1
0x1800050aa  setnz   al
0x1800050ad  test    al, cl
0x1800050af  mov     eax, 0
0x1800050b4  setnz   al
0x1800050b7  mov     esi, [rbp+var_20+4]
0x1800050ba  lea     r15, SRWLock
0x1800050c1  mov     r13d, 15CBDE5h
0x1800050c7  test    eax, eax
0x1800050c9  jz      loc_18000519E
0x1800050cf  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800050d5  test    eax, eax
0x1800050d7  jz      loc_18000519E
0x1800050dd  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800050e2  test    al, al
0x1800050e4  jnz     loc_18000519E
0x1800050ea  mov     rcx, r15; SRWLock
0x1800050ed  call    cs:__imp_AcquireSRWLockExclusive
0x1800050f3  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800050f9  test    eax, eax
0x1800050fb  jz      loc_180005194
0x180005101  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180005106  test    al, al
0x180005108  jnz     loc_180005194
0x18000510e  mov     [rbp+var_30], 15CBDE5h
0x180005116  mov     [rbp+var_28], rbx
0x18000511a  mov     r8d, 10h; unsigned __int64
0x180005120  lea     rdx, [rbp+var_30]; void *
0x180005124  lea     rcx, qword_1800ACD88; this
0x18000512b  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180005130  cmp     cs:byte_1800ACD80, 0
0x180005137  jnz     short loc_180005194
0x180005139  cmp     cs:qword_1800ACD78, 0
0x180005141  jnz     short loc_18000517B
0x180005143  lea     rcx, [rbp+arg_18]; this
0x180005147  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000514c  xor     r8d, r8d; pcbe
0x18000514f  lea     rdx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180005156  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000515d  call    cs:__imp_CreateThreadpoolTimer
0x180005163  mov     rdx, rax
0x180005166  lea     rcx, qword_1800ACD78
0x18000516d  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180005172  lea     rcx, [rbp+arg_18]; this
0x180005176  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000517b  mov     r8d, 493E0h
0x180005181  lea     rdx, byte_1800ACD80
0x180005188  lea     rcx, qword_1800ACD78
0x18000518f  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180005194  mov     rcx, r15; SRWLock
0x180005197  call    cs:__imp_ReleaseSRWLockExclusive
0x18000519d  nop
0x18000519e  test    esi, esi
0x1800051a0  jz      short loc_1800051B0
0x1800051a2  mov     r8d, esi; unsigned int
0x1800051a5  mov     edx, [rbp+var_20+8]; unsigned int
0x1800051a8  mov     ecx, r13d; this
0x1800051ab  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x1800051b0  test    r14d, r14d
0x1800051b3  jnz     short loc_1800051FE
0x1800051b5  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800051bb  test    eax, eax
0x1800051bd  jz      short loc_1800051FE
0x1800051bf  mov     rcx, r15; SRWLock
0x1800051c2  call    cs:__imp_AcquireSRWLockExclusive
0x1800051c8  cmp     cs:qword_1800ACDD0, 0
0x1800051d0  jnz     short loc_1800051F4
0x1800051d2  mov     cs:qword_1800ACDD0, 0
0x1800051dd  or      r8, 0FFFFFFFFFFFFFFFFh; void (*)(void *)
0x1800051e1  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800051e8  lea     rcx, qword_1800ACDD0; this
0x1800051ef  call    ?WilApi_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details::WilApi_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1800051f4  mov     rcx, r15; SRWLock
0x1800051f7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800051fd  nop
0x1800051fe  bt      edi, 0Ah
0x180005202  jnb     short loc_18000521D
0x180005204  and     edi, 0FFFFF800h
0x18000520a  shl     edi, 14h
0x18000520d  or      edi, 2
0x180005210  xor     r8d, r8d; unsigned int
0x180005213  mov     edx, edi; unsigned int
0x180005215  mov     ecx, r13d; this
0x180005218  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18000521d  test    r14d, r14d
0x180005220  jnz     short loc_18000527E
0x180005222  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180005229  test    rax, rax
0x18000522c  jz      short loc_18000523D
0x18000522e  mov     r8b, 3
0x180005231  lea     edx, [r14+2]
0x180005235  mov     ecx, r13d
0x180005238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000523d  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180005244  test    rax, rax
0x180005247  jz      short loc_18000527E
0x180005249  mov     [rsp+80h+var_48], 1
0x180005252  mov     [rsp+80h+var_50], 0
0x180005257  mov     [rsp+80h+var_58], 0
0x180005260  lea     rdx, [rbp+arg_0]
0x180005264  mov     [rsp+80h+var_60], rdx
0x180005269  mov     r9d, 1
0x18000526f  xor     r8d, r8d
0x180005272  lea     rdx, [rbp+arg_10]
0x180005276  mov     ecx, r13d
0x180005279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000527e  mov     al, 1
0x180005280  add     rsp, 80h
0x180005287  pop     r15
0x180005289  pop     r14
0x18000528b  pop     r13
0x18000528d  pop     rdi
0x18000528e  pop     rsi
0x18000528f  pop     rbx
0x180005290  pop     rbp
0x180005291  retn
```
