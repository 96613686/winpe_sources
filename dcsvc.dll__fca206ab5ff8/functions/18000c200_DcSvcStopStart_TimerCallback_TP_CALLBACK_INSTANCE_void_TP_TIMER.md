# DcSvcStopStart::TimerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x18000c200`
- end: `0x18000c526`
- name: `?TimerCallback@DcSvcStopStart@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `806`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000947c`
- `0x18000b6b0`
- `0x18000b73c`
- `0x18000bc40`
- `0x18000c120`
- `0x18000c164`
- `0x18000c200`
- `0x18000c52c`
- `0x18000c568`
- `0x18000c854`
- `0x18000dfa8`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000c432`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000c50d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000c432`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000c50d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c28c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c2cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c3b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c3fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c45b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c48e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c28c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c2cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c3b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c3fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c45b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c48e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c2fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c4bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c2fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c4bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c324`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c4e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c324`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c4e5`
- `DeclaredConfigurationAPI!GetOrchestratorEngine` at `0x18000c215`
- `DeclaredConfigurationAPI!GetOrchestratorEngine` at `0x18000c215`

## pseudocode

```c
void __fastcall DcSvcStopStart::TimerCallback(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)
{
  __int64 OrchestratorEngine; // rsi
  unsigned int *v4; // rdx
  int TimerCountToRegistry; // edi
  struct _RTL_CRITICAL_SECTION **v6; // rax
  unsigned int v7; // r14d
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  struct _RTL_CRITICAL_SECTION *v9; // rbx
  struct _RTL_CRITICAL_SECTION *v10; // rbx
  DcSvcStopStart *v11; // rcx
  int v12; // eax
  struct _RTL_CRITICAL_SECTION **v13; // rax
  struct _RTL_CRITICAL_SECTION *v14; // rbx
  DcSvcStopStart *v15; // rcx
  struct _RTL_CRITICAL_SECTION *v16; // rbx
  struct _RTL_CRITICAL_SECTION *v17; // rbx
  struct _RTL_CRITICAL_SECTION *v18; // rbx
  __int128 v19; // [rsp+20h] [rbp-20h] BYREF
  LPVOID pv[2]; // [rsp+30h] [rbp-10h] BYREF
  unsigned int pvData; // [rsp+78h] [rbp+38h] BYREF

  OrchestratorEngine = GetOrchestratorEngine(Instance, Context, Timer);
  pvData = 0;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_Kill_Long_Running_Service>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_Kill_Long_Running_Service>::GetImpl'::`2'::impl) )
  {
    pv[0] = 0;
    TimerCountToRegistry = DcSvcStopStart::GetTimerCountToRegistry(&pvData, v4);
    v6 = tip2::tip_test<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>>::ensure_data((struct _RTL_CRITICAL_SECTION **)pv);
    tip2::details::shared_data<0,0,0>::start((__int64)&(*v6)->LockCount, &v19);
    v7 = pvData;
    v8 = *tip2::tip_test<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>>::ensure_data((struct _RTL_CRITICAL_SECTION **)pv);
    *(_QWORD *)&v19 = v8;
    if ( v8 )
      _InterlockedIncrement(&v8[7].LockCount);
    EnterCriticalSection(v8 + 5);
    ++LODWORD(v8[6].DebugInfo);
    HIDWORD(v8[6].SpinCount) = v7;
    tip2::test_data_control<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>>((struct _RTL_CRITICAL_SECTION **)&v19);
    if ( TimerCountToRegistry < 0 )
    {
      v14 = *tip2::tip_test<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>>::ensure_data((struct _RTL_CRITICAL_SECTION **)pv);
      *(_QWORD *)&v19 = v14;
LABEL_22:
      if ( v14 )
        _InterlockedIncrement(&v14[7].LockCount);
      EnterCriticalSection(v14 + 5);
      ++LODWORD(v14[6].DebugInfo);
      LODWORD(v14[6].SpinCount) = TimerCountToRegistry;
      tip2::test_data_control<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>>((struct _RTL_CRITICAL_SECTION **)&v19);
      goto LABEL_25;
    }
    if ( pvData > 5 )
    {
LABEL_25:
      SvcEngUpdateServiceStatus(3, 0, 0);
      if ( hEvent )
        SetEvent(hEvent);
      v16 = *tip2::tip_test<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>>::ensure_data((struct _RTL_CRITICAL_SECTION **)pv);
      *(_QWORD *)&v19 = v16;
      if ( v16 )
        _InterlockedIncrement(&v16[7].LockCount);
      EnterCriticalSection(v16 + 5);
      ++LODWORD(v16[6].DebugInfo);
      LOBYTE(v16[7].DebugInfo) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>>((struct _RTL_CRITICAL_SECTION **)&v19);
      goto LABEL_30;
    }
    v9 = (struct _RTL_CRITICAL_SECTION *)pv[0];
    if ( pv[0] )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)pv[0] + 5);
      LODWORD(v9[1].SpinCount) |= 0x300u;
      if ( *(_QWORD *)&v9[6].LockCount )
        tip2::details::shared_data<0,0,0>::complete_helper((__int64)&v9->LockCount, 2u);
      if ( v9 != (struct _RTL_CRITICAL_SECTION *)-200LL )
        LeaveCriticalSection(v9 + 5);
      v10 = (struct _RTL_CRITICAL_SECTION *)pv[0];
      if ( pv[0] && _InterlockedExchangeAdd((volatile signed __int32 *)pv[0] + 72, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>::~merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>(v10);
        CoTaskMemFree(v10);
      }
    }
  }
  if ( OrchestratorEngine
    && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)OrchestratorEngine + 64LL))(OrchestratorEngine) )
  {
    if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_Kill_Long_Running_Service>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_Kill_Long_Running_Service>::GetImpl'::`2'::impl) )
    {
      DcSvcStopStart::SetShutdownTimer(v11);
      return;
    }
    v12 = DcSvcStopStart::SetTimerCountToRegistry((DcSvcStopStart *)(pvData + 1));
    pv[0] = 0;
    TimerCountToRegistry = v12;
    v13 = tip2::tip_test<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>>::ensure_data((struct _RTL_CRITICAL_SECTION **)pv);
    tip2::details::shared_data<0,0,0>::start((__int64)&(*v13)->LockCount, &v19);
    v14 = *tip2::tip_test<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>>::ensure_data((struct _RTL_CRITICAL_SECTION **)pv);
    *(_QWORD *)&v19 = v14;
    if ( TimerCountToRegistry >= 0 )
    {
      if ( v14 )
        _InterlockedIncrement(&v14[7].LockCount);
      EnterCriticalSection(v14 + 5);
      ++LODWORD(v14[6].DebugInfo);
      LODWORD(v14[6].SpinCount) = 0;
      tip2::test_data_control<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>>((struct _RTL_CRITICAL_SECTION **)&v19);
      DcSvcStopStart::SetShutdownTimer(v15);
LABEL_30:
      v17 = (struct _RTL_CRITICAL_SECTION *)pv[0];
      if ( pv[0] )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)pv[0] + 5);
        LODWORD(v17[1].SpinCount) |= 0x300u;
        if ( *(_QWORD *)&v17[6].LockCount )
          tip2::details::shared_data<0,0,0>::complete_helper((__int64)&v17->LockCount, 2u);
        if ( v17 != (struct _RTL_CRITICAL_SECTION *)-200LL )
          LeaveCriticalSection(v17 + 5);
        v18 = (struct _RTL_CRITICAL_SECTION *)pv[0];
        if ( pv[0] )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)pv[0] + 72, 0xFFFFFFFF) == 1 )
          {
            tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>::~merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>(v18);
            CoTaskMemFree(v18);
          }
        }
      }
      return;
    }
    goto LABEL_22;
  }
  SvcEngUpdateServiceStatus(3, 0, 0);
  if ( hEvent )
    SetEvent(hEvent);
}

```

## disassembly

```asm
0x18000c200  mov     [rsp-18h+arg_0], rbx
0x18000c205  mov     [rsp-18h+arg_8], rsi
0x18000c20a  push    rbp
0x18000c20b  push    rdi
0x18000c20c  push    r14
0x18000c20e  mov     rbp, rsp
0x18000c211  sub     rsp, 40h
0x18000c215  call    cs:__imp_GetOrchestratorEngine
0x18000c21b  mov     rsi, rax
0x18000c21e  mov     [rbp+pvData], 0
0x18000c225  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeclaredConfiguration_Kill_Long_Running_Service@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_Kill_Long_Running_Service@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_Kill_Long_Running_Service> `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_Kill_Long_Running_Service>::GetImpl(void)'::`2'::impl
0x18000c22c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_Kill_Long_Running_Service@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_Kill_Long_Running_Service>::__private_IsEnabled(void)
0x18000c231  test    al, al
0x18000c233  jz      loc_18000C32A
0x18000c239  lea     rcx, [rbp+pvData]; pvData
0x18000c23d  call    ?GetTimerCountToRegistry@DcSvcStopStart@@YAJPEAK@Z; DcSvcStopStart::GetTimerCountToRegistry(ulong *)
0x18000c242  lea     rcx, [rbp+pv]
0x18000c246  mov     [rbp+pv], 0
0x18000c24e  mov     edi, eax
0x18000c250  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_DcsvcShutdownTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_DcsvcShutdownTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>>::ensure_data(void)
0x18000c255  lea     rdx, [rbp+var_20]
0x18000c259  mov     rcx, [rax]
0x18000c25c  add     rcx, 8
0x18000c260  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x18000c265  mov     r14d, [rbp+pvData]
0x18000c269  lea     rcx, [rbp+pv]
0x18000c26d  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_DcsvcShutdownTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_DcsvcShutdownTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>>::ensure_data(void)
0x18000c272  mov     rbx, [rax]
0x18000c275  mov     qword ptr [rbp+var_20], rbx
0x18000c279  test    rbx, rbx
0x18000c27c  jz      short loc_18000C285
0x18000c27e  lock inc dword ptr [rbx+120h]
0x18000c285  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18000c28c  call    cs:__imp_EnterCriticalSection
0x18000c292  inc     dword ptr [rbx+0F0h]
0x18000c298  lea     rcx, [rbp+var_20]
0x18000c29c  mov     [rbx+114h], r14d
0x18000c2a3  call    ??1?$test_data_control@V?$merged_data@U_tip_DcsvcShutdownTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>>(void)
0x18000c2a8  test    edi, edi
0x18000c2aa  js      loc_18000C3DB
0x18000c2b0  cmp     [rbp+pvData], 5
0x18000c2b4  ja      loc_18000C419
0x18000c2ba  mov     rbx, [rbp+pv]
0x18000c2be  test    rbx, rbx
0x18000c2c1  jz      short loc_18000C32A
0x18000c2c3  lea     rdi, [rbx+0C8h]
0x18000c2ca  mov     rcx, rdi; lpCriticalSection
0x18000c2cd  call    cs:__imp_EnterCriticalSection
0x18000c2d3  or      dword ptr [rbx+48h], 300h
0x18000c2da  cmp     qword ptr [rbx+0F8h], 0
0x18000c2e2  jz      short loc_18000C2F2
0x18000c2e4  mov     edx, 2
0x18000c2e9  lea     rcx, [rbx+8]
0x18000c2ed  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18000c2f2  test    rdi, rdi
0x18000c2f5  jz      short loc_18000C300
0x18000c2f7  mov     rcx, rdi; lpCriticalSection
0x18000c2fa  call    cs:__imp_LeaveCriticalSection
0x18000c300  mov     rbx, [rbp+pv]
0x18000c304  test    rbx, rbx
0x18000c307  jz      short loc_18000C32A
0x18000c309  or      eax, 0FFFFFFFFh
0x18000c30c  lock xadd [rbx+120h], eax
0x18000c314  cmp     eax, 1
0x18000c317  jnz     short loc_18000C32A
0x18000c319  mov     rcx, rbx
0x18000c31c  call    ??1?$merged_data@U_tip_DcsvcShutdownTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>::~merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>(void)
0x18000c321  mov     rcx, rbx; pv
0x18000c324  call    cs:__imp_CoTaskMemFree
0x18000c32a  test    rsi, rsi
0x18000c32d  jz      loc_18000C4F4
0x18000c333  mov     rax, [rsi]
0x18000c336  mov     rcx, rsi
0x18000c339  mov     rax, [rax+40h]
0x18000c33d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c342  test    eax, eax
0x18000c344  jz      loc_18000C4F4
0x18000c34a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeclaredConfiguration_Kill_Long_Running_Service@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_Kill_Long_Running_Service@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_Kill_Long_Running_Service> `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_Kill_Long_Running_Service>::GetImpl(void)'::`2'::impl
0x18000c351  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_Kill_Long_Running_Service@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_Kill_Long_Running_Service>::__private_IsEnabled(void)
0x18000c356  test    al, al
0x18000c358  jz      loc_18000C4ED
0x18000c35e  mov     ecx, [rbp+pvData]
0x18000c361  inc     ecx; this
0x18000c363  call    ?SetTimerCountToRegistry@DcSvcStopStart@@YAJK@Z; DcSvcStopStart::SetTimerCountToRegistry(ulong)
0x18000c368  lea     rcx, [rbp+pv]
0x18000c36c  mov     [rbp+pv], 0
0x18000c374  mov     edi, eax
0x18000c376  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_DcsvcShutdownTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_DcsvcShutdownTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>>::ensure_data(void)
0x18000c37b  lea     rdx, [rbp+var_20]
0x18000c37f  mov     rcx, [rax]
0x18000c382  add     rcx, 8
0x18000c386  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x18000c38b  lea     rcx, [rbp+pv]
0x18000c38f  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_DcsvcShutdownTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_DcsvcShutdownTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>>::ensure_data(void)
0x18000c394  mov     rbx, [rax]
0x18000c397  mov     qword ptr [rbp+var_20], rbx
0x18000c39b  test    edi, edi
0x18000c39d  js      short loc_18000C3EB
0x18000c39f  test    rbx, rbx
0x18000c3a2  jz      short loc_18000C3AB
0x18000c3a4  lock inc dword ptr [rbx+120h]
0x18000c3ab  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18000c3b2  call    cs:__imp_EnterCriticalSection
0x18000c3b8  inc     dword ptr [rbx+0F0h]
0x18000c3be  lea     rcx, [rbp+var_20]
0x18000c3c2  mov     dword ptr [rbx+110h], 0
0x18000c3cc  call    ??1?$test_data_control@V?$merged_data@U_tip_DcsvcShutdownTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>>(void)
0x18000c3d1  call    ?SetShutdownTimer@DcSvcStopStart@@YAHXZ; DcSvcStopStart::SetShutdownTimer(void)
0x18000c3d6  jmp     loc_18000C477
0x18000c3db  lea     rcx, [rbp+pv]
0x18000c3df  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_DcsvcShutdownTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_DcsvcShutdownTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>>::ensure_data(void)
0x18000c3e4  mov     rbx, [rax]
0x18000c3e7  mov     qword ptr [rbp+var_20], rbx
0x18000c3eb  test    rbx, rbx
0x18000c3ee  jz      short loc_18000C3F7
0x18000c3f0  lock inc dword ptr [rbx+120h]
0x18000c3f7  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18000c3fe  call    cs:__imp_EnterCriticalSection
0x18000c404  inc     dword ptr [rbx+0F0h]
0x18000c40a  lea     rcx, [rbp+var_20]
0x18000c40e  mov     [rbx+110h], edi
0x18000c414  call    ??1?$test_data_control@V?$merged_data@U_tip_DcsvcShutdownTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>>(void)
0x18000c419  xor     edx, edx; unsigned int
0x18000c41b  xor     r8d, r8d; unsigned int
0x18000c41e  lea     ecx, [rdx+3]; unsigned int
0x18000c421  call    ?SvcEngUpdateServiceStatus@@YAJKKK@Z; SvcEngUpdateServiceStatus(ulong,ulong,ulong)
0x18000c426  mov     rcx, cs:hEvent; hEvent
0x18000c42d  test    rcx, rcx
0x18000c430  jz      short loc_18000C438
0x18000c432  call    cs:__imp_SetEvent
0x18000c438  lea     rcx, [rbp+pv]
0x18000c43c  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_DcsvcShutdownTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_DcsvcShutdownTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>>::ensure_data(void)
0x18000c441  mov     rbx, [rax]
0x18000c444  mov     qword ptr [rbp+var_20], rbx
0x18000c448  test    rbx, rbx
0x18000c44b  jz      short loc_18000C454
0x18000c44d  lock inc dword ptr [rbx+120h]
0x18000c454  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18000c45b  call    cs:__imp_EnterCriticalSection
0x18000c461  inc     dword ptr [rbx+0F0h]
0x18000c467  lea     rcx, [rbp+var_20]
0x18000c46b  mov     byte ptr [rbx+118h], 1
0x18000c472  call    ??1?$test_data_control@V?$merged_data@U_tip_DcsvcShutdownTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>>(void)
0x18000c477  mov     rbx, [rbp+pv]
0x18000c47b  test    rbx, rbx
0x18000c47e  jz      loc_18000C513
0x18000c484  lea     rdi, [rbx+0C8h]
0x18000c48b  mov     rcx, rdi; lpCriticalSection
0x18000c48e  call    cs:__imp_EnterCriticalSection
0x18000c494  or      dword ptr [rbx+48h], 300h
0x18000c49b  cmp     qword ptr [rbx+0F8h], 0
0x18000c4a3  jz      short loc_18000C4B3
0x18000c4a5  mov     edx, 2
0x18000c4aa  lea     rcx, [rbx+8]
0x18000c4ae  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18000c4b3  test    rdi, rdi
0x18000c4b6  jz      short loc_18000C4C1
0x18000c4b8  mov     rcx, rdi; lpCriticalSection
0x18000c4bb  call    cs:__imp_LeaveCriticalSection
0x18000c4c1  mov     rbx, [rbp+pv]
0x18000c4c5  test    rbx, rbx
0x18000c4c8  jz      short loc_18000C513
0x18000c4ca  or      eax, 0FFFFFFFFh
0x18000c4cd  lock xadd [rbx+120h], eax
0x18000c4d5  cmp     eax, 1
0x18000c4d8  jnz     short loc_18000C513
0x18000c4da  mov     rcx, rbx
0x18000c4dd  call    ??1?$merged_data@U_tip_DcsvcShutdownTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>::~merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>(void)
0x18000c4e2  mov     rcx, rbx; pv
0x18000c4e5  call    cs:__imp_CoTaskMemFree
0x18000c4eb  jmp     short loc_18000C513
0x18000c4ed  call    ?SetShutdownTimer@DcSvcStopStart@@YAHXZ; DcSvcStopStart::SetShutdownTimer(void)
0x18000c4f2  jmp     short loc_18000C513
0x18000c4f4  xor     edx, edx; unsigned int
0x18000c4f6  xor     r8d, r8d; unsigned int
0x18000c4f9  lea     ecx, [rdx+3]; unsigned int
0x18000c4fc  call    ?SvcEngUpdateServiceStatus@@YAJKKK@Z; SvcEngUpdateServiceStatus(ulong,ulong,ulong)
0x18000c501  mov     rcx, cs:hEvent; hEvent
0x18000c508  test    rcx, rcx
0x18000c50b  jz      short loc_18000C513
0x18000c50d  call    cs:__imp_SetEvent
0x18000c513  mov     rbx, [rsp+40h+arg_0]
0x18000c518  mov     rsi, [rsp+40h+arg_8]
0x18000c51d  add     rsp, 40h
0x18000c521  pop     r14
0x18000c523  pop     rdi
0x18000c524  pop     rbp
0x18000c525  retn
```
