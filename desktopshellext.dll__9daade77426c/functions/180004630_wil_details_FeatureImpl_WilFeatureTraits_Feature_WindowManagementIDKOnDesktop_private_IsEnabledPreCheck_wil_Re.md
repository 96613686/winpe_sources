# wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowManagementIDKOnDesktop>::__private_IsEnabledPreCheck(wil::ReportingKind)

- ea: `0x180004630`
- end: `0x1800048f7`
- name: `?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowManagementIDKOnDesktop@@@details@wil@@QEAA_NW4ReportingKind@3@@Z`
- size: `711`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800035b0`
- `0x180004b24`
- `0x180022d5c`

## callees

- `0x180002d90`
- `0x180004630`
- `0x180004900`
- `0x180004950`
- `0x180004980`
- `0x180004a10`
- `0x18000d2a0`
- `0x1800111b8`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800047dd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800048af`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800047dd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800048af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800047cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004819`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800047cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004819`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004775`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004775`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800047a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800047a5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000478e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000478e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowManagementIDKOnDesktop>::__private_IsEnabledPreCheck(
        __int64 a1,
        char a2,
        __int64 a3,
        unsigned int a4)
{
  int v5; // ebx
  volatile signed __int32 *v6; // rdi
  wil *i; // rcx
  signed __int32 v8; // edx
  BOOL v9; // esi
  unsigned __int32 v10; // eax
  DWORD LastError; // edi
  struct _TP_TIMER *ThreadpoolTimer; // rax
  void *v14; // r9
  unsigned int v15; // edx
  wil *v16; // rcx
  const char *v17; // [rsp+20h] [rbp-78h]
  _QWORD v18[2]; // [rsp+50h] [rbp-48h] BYREF
  unsigned int v19[4]; // [rsp+60h] [rbp-38h]
  int v20; // [rsp+A0h] [rbp+8h] BYREF
  __int16 v21; // [rsp+A4h] [rbp+Ch]
  int v22; // [rsp+A8h] [rbp+10h] BYREF
  __int64 v23; // [rsp+B0h] [rbp+18h]
  char v24; // [rsp+B8h] [rbp+20h] BYREF

  LOBYTE(v22) = a2;
  v5 = *(_DWORD *)Feature_WindowManagementIDKOnDesktop__descriptor;
  if ( (*(_DWORD *)Feature_WindowManagementIDKOnDesktop__descriptor & 4) == 0 )
  {
    v23 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowManagementIDKOnDesktop>::GetCachedFeatureEnabledState(
                       a1,
                       &v24);
    LOWORD(v5) = v23;
  }
  v20 = 0;
  v21 = 3;
  v22 = 3;
  v6 = (volatile signed __int32 *)(a1 + 8);
  *(_OWORD *)v19 = 0;
  for ( i = (wil *)*(unsigned int *)v6; ; i = (wil *)v10 )
  {
    v8 = (unsigned int)i | 2;
    v9 = ((unsigned int)i | 2) == (_DWORD)i;
    if ( ((unsigned int)i | 2) != (_DWORD)i )
      v8 = (unsigned int)i | 3;
    v10 = _InterlockedCompareExchange(v6, v8, (signed __int32)i);
    if ( (_DWORD)i == v10 )
      break;
  }
  if ( (v8 & 1) != 0
    && ((unsigned __int8)i & 1) == 0
    && wil::details::g_enabledStateManager
    && !wil::ProcessShutdownInProgress(i) )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( wil::details::g_enabledStateManager )
    {
      if ( !wil::ProcessShutdownInProgress(v16) )
      {
        v18[0] = 30629240;
        v18[1] = v6;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800ACD88, v18, 0x10u);
        if ( !byte_1800ACD80 )
        {
          if ( !qword_1800ACD78 )
          {
            LastError = GetLastError();
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                &wil::details::g_enabledStateManager,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              (struct _TP_TIMER **)&qword_1800ACD78,
              ThreadpoolTimer);
            SetLastError(LastError);
          }
          wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)&qword_1800ACD78, &byte_1800ACD80, 300000);
        }
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( v19[1] )
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x1D35D78, v19[2], v19[1], a4, v17);
  if ( !v9 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_1800ACDD0 )
    {
      qword_1800ACDD0 = 0;
      wil::details::WilApi_SubscribeFeatureStateChangeNotification(
        (wil::details *)&qword_1800ACDD0,
        (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **)_lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_,
        (void (*)(void *))0xFFFFFFFFFFFFFFFFLL,
        v14);
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( (v5 & 0x400) != 0 )
  {
    v15 = 2;
    if ( (v5 & 0x800) != 0 )
      v15 = -2147483646;
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x1D35D78, v15, 0, a4, v17);
  }
  if ( !v9 )
  {
    if ( g_wil_details_realtimeFeatureUsageHook )
    {
      LOBYTE(a3) = 3;
      g_wil_details_realtimeFeatureUsageHook(30629240, 2, a3);
    }
    if ( g_wil_details_pfnFeatureLoggingHook )
      g_wil_details_pfnFeatureLoggingHook(30629240, &v20, 0, 1, &v22, 0, 0, 1);
  }
  return 1;
}

```

## disassembly

```asm
0x180004630  mov     byte ptr [rsp+arg_8], dl
0x180004634  push    rbx
0x180004635  push    rsi
0x180004636  push    rdi
0x180004637  sub     rsp, 80h
0x18000463e  mov     rdi, rcx
0x180004641  mov     rbx, cs:Feature_WindowManagementIDKOnDesktop__descriptor
0x180004648  mov     ebx, [rbx]
0x18000464a  test    bl, 4
0x18000464d  jz      loc_18000487C
0x180004653  xor     eax, eax
0x180004655  mov     [rsp+98h+arg_0], eax
0x18000465c  mov     [rsp+98h+arg_4], 3
0x180004666  mov     [rsp+98h+arg_8], 3
0x180004671  add     rdi, 8
0x180004675  xorps   xmm0, xmm0
0x180004678  movups  xmmword ptr [rsp+98h+var_38], xmm0
0x18000467d  mov     ecx, [rdi]; this
0x18000467f  mov     edx, ecx
0x180004681  or      edx, 2
0x180004684  xor     esi, esi
0x180004686  cmp     edx, ecx
0x180004688  setz    sil
0x18000468c  mov     eax, edx
0x18000468e  or      eax, 1
0x180004691  cmp     edx, ecx
0x180004693  cmovnz  edx, eax
0x180004696  mov     eax, ecx
0x180004698  lock cmpxchg [rdi], edx
0x18000469c  jz      short loc_1800046A2
0x18000469e  mov     ecx, eax
0x1800046a0  jmp     short loc_18000467F
0x1800046a2  test    dl, 1
0x1800046a5  setnz   dl
0x1800046a8  test    cl, 1
0x1800046ab  setz    al
0x1800046ae  test    al, dl
0x1800046b0  mov     eax, 0
0x1800046b5  setnz   al
0x1800046b8  test    eax, eax
0x1800046ba  jz      short loc_1800046CA
0x1800046bc  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800046c2  test    eax, eax
0x1800046c4  jnz     loc_18000489B
0x1800046ca  cmp     [rsp+98h+var_38+4], 0
0x1800046cf  ja      loc_1800048D5
0x1800046d5  test    esi, esi
0x1800046d7  jnz     short loc_1800046E7
0x1800046d9  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800046df  test    eax, eax
0x1800046e1  jnz     loc_1800047D6
0x1800046e7  bt      ebx, 0Ah
0x1800046eb  jb      loc_180004824
0x1800046f1  test    esi, esi
0x1800046f3  jnz     short loc_18000475E
0x1800046f5  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x1800046fc  test    rax, rax
0x1800046ff  jz      short loc_180004713
0x180004701  mov     r8b, 3
0x180004704  mov     edx, 2
0x180004709  mov     ecx, 1D35D78h
0x18000470e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004713  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000471a  test    rax, rax
0x18000471d  jz      short loc_18000475E
0x18000471f  mov     [rsp+98h+var_60], 1
0x180004728  mov     [rsp+98h+var_68], 0
0x18000472d  mov     [rsp+98h+var_70], 0
0x180004736  lea     rdx, [rsp+98h+arg_8]
0x18000473e  mov     [rsp+98h+var_78], rdx
0x180004743  mov     r9d, 1
0x180004749  xor     r8d, r8d
0x18000474c  lea     rdx, [rsp+98h+arg_0]
0x180004754  mov     ecx, 1D35D78h
0x180004759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000475e  mov     al, 1
0x180004760  add     rsp, 80h
0x180004767  pop     rdi
0x180004768  pop     rsi
0x180004769  pop     rbx
0x18000476a  retn
0x18000476b  cmp     cs:qword_1800ACD78, 0
0x180004773  jnz     short loc_1800047AB
0x180004775  call    cs:__imp_GetLastError
0x18000477b  mov     edi, eax
0x18000477d  xor     r8d, r8d; pcbe
0x180004780  lea     rdx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180004787  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000478e  call    cs:__imp_CreateThreadpoolTimer
0x180004794  mov     rdx, rax
0x180004797  lea     rcx, qword_1800ACD78
0x18000479e  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800047a3  mov     ecx, edi; dwErrCode
0x1800047a5  call    cs:__imp_SetLastError
0x1800047ab  mov     r8d, 493E0h
0x1800047b1  lea     rdx, byte_1800ACD80
0x1800047b8  lea     rcx, qword_1800ACD78
0x1800047bf  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800047c4  lea     rcx, SRWLock; SRWLock
0x1800047cb  call    cs:__imp_ReleaseSRWLockExclusive
0x1800047d1  jmp     loc_1800046CA
0x1800047d6  lea     rcx, SRWLock; SRWLock
0x1800047dd  call    cs:__imp_AcquireSRWLockExclusive
0x1800047e3  cmp     cs:qword_1800ACDD0, 0
0x1800047eb  jnz     short loc_180004812
0x1800047ed  mov     cs:qword_1800ACDD0, 0
0x1800047f8  mov     r8, 0FFFFFFFFFFFFFFFFh; void (*)(void *)
0x1800047ff  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180004806  lea     rcx, qword_1800ACDD0; this
0x18000480d  call    ?WilApi_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details::WilApi_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180004812  lea     rcx, SRWLock; SRWLock
0x180004819  call    cs:__imp_ReleaseSRWLockExclusive
0x18000481f  jmp     loc_1800046E7
0x180004824  mov     edx, 2; unsigned int
0x180004829  bt      ebx, 0Bh
0x18000482d  jb      loc_1800048ED
0x180004833  xor     r8d, r8d; unsigned int
0x180004836  mov     ecx, 1D35D78h; this
0x18000483b  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180004840  jmp     loc_1800046F1
0x180004845  mov     [rsp+98h+var_48], 1D35D78h
0x18000484e  mov     [rsp+98h+var_40], rdi
0x180004853  mov     r8d, 10h; unsigned __int64
0x180004859  lea     rdx, [rsp+98h+var_48]; void *
0x18000485e  lea     rcx, qword_1800ACD88; this
0x180004865  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000486a  cmp     cs:byte_1800ACD80, 0
0x180004871  jnz     loc_1800047C4
0x180004877  jmp     loc_18000476B
0x18000487c  lea     rdx, [rsp+98h+arg_18]
0x180004884  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowManagementIDKOnDesktop@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowManagementIDKOnDesktop>::GetCachedFeatureEnabledState(void)
0x180004889  mov     rdx, [rax]
0x18000488c  mov     [rsp+98h+arg_10], rdx
0x180004894  mov     ebx, edx
0x180004896  jmp     loc_180004653
0x18000489b  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800048a0  test    al, al
0x1800048a2  jnz     loc_1800046CA
0x1800048a8  lea     rcx, SRWLock; SRWLock
0x1800048af  call    cs:__imp_AcquireSRWLockExclusive
0x1800048b5  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800048bb  test    eax, eax
0x1800048bd  jz      loc_1800047C4
0x1800048c3  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800048c8  test    al, al
0x1800048ca  jnz     loc_1800047C4
0x1800048d0  jmp     loc_180004845
0x1800048d5  mov     r8d, [rsp+98h+var_38+4]; unsigned int
0x1800048da  mov     edx, [rsp+98h+var_38+8]; unsigned int
0x1800048de  mov     ecx, 1D35D78h; this
0x1800048e3  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x1800048e8  jmp     loc_1800046D5
0x1800048ed  mov     edx, 80000002h
0x1800048f2  jmp     loc_180004833
```
