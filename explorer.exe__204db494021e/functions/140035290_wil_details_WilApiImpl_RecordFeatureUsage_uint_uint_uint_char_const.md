# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x140035290`
- end: `0x1400355d7`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `839`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x140007ec0`
- `0x1400335d0`
- `0x1400344f0`
- `0x140034b4c`
- `0x140034f58`
- `0x140035290`
- `0x1400355e0`
- `0x140035674`
- `0x140036534`
- `0x1400366c4`
- `0x140084478`
- `0x140086b94`
- `0x140087664`
- `0x140112fc0`
- `0x140113ce0`
- `0x1401d9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140035348`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140035400`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140035348`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140035400`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14003530c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140035380`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14003530c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140035380`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400353e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400353e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400353a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400353a5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140035480`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140035480`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400353c4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140035543`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400353c4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140035543`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::WilApiImpl_RecordFeatureUsage(wil::details *this, __int64 a2, unsigned int a3)
{
  unsigned int v4; // r14d
  __int64 v5; // r8
  unsigned int v6; // ebx
  PSRWLOCK v7; // rdi
  int v8; // eax
  char Ptr; // bl
  struct _TP_TIMER *v10; // rcx
  DWORD LastError; // ebx
  PTP_TIMER v12; // rax
  PTP_TIMER ThreadpoolTimer; // rax
  unsigned int v14; // [rsp+20h] [rbp-48h] BYREF
  __int16 v15; // [rsp+24h] [rbp-44h]
  __int16 v16; // [rsp+26h] [rbp-42h]
  unsigned int v17; // [rsp+28h] [rbp-40h]
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp-38h] BYREF

  v4 = (unsigned int)this;
  v5 = (unsigned int)a2 >> 31;
  LODWORD(a2) = a2 & 0x7FFFFFFF;
  v6 = a2;
  if ( !(_DWORD)this && !a3 && !(_DWORD)a2 )
  {
    if ( !wil::ProcessShutdownInProgress(this)
      && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)&wil::details::g_featureStateManager) )
    {
      wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_14024DFB8[25], qword_14024DFB8);
      wil::details_abi::FeatureStateData::RecordUsage(qword_14024DFB8);
    }
    return;
  }
  if ( (a2 & 0x40000000) != 0 )
  {
    if ( wil::details::g_featureStateManager && !wil::ProcessShutdownInProgress(this) )
    {
      wil::AcquireSRWLockExclusive(&pftDueTime, &qword_14024DFC8);
      v16 = 0;
      v14 = v4;
      v15 = v6;
      v17 = a3;
      wil::details_abi::heap_buffer::push_back(
        (wil::details_abi::heap_buffer *)((char *)&xmmword_14024E080 + 8),
        &v14,
        0xCu);
      if ( !byte_14024DFE0 )
      {
        if ( !qword_14024DFD8 )
        {
          wil::last_error_context::last_error_context((wil::last_error_context *)&v14);
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                              &wil::details::g_featureStateManager,
                              0);
          wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
            &qword_14024DFD8,
            ThreadpoolTimer);
          wil::last_error_context::~last_error_context((wil::last_error_context *)&v14);
        }
        wil::details::EnsureCoalescedTimer_SetTimer(&qword_14024DFD8, &byte_14024DFE0, 5000);
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&pftDueTime);
    }
  }
  else
  {
    if ( !a3 && (_DWORD)a2 != 254 )
    {
      wil_RtlStagingConfig_RecordFeatureUsage(this, a2, v5);
      return;
    }
    if ( wil::details::g_featureStateManager
      && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)&wil::details::g_featureStateManager) )
    {
      v7 = qword_14024DFB8;
      if ( v6 == 254 )
      {
        wil::details_abi::FeatureStateData::RecordUsage(qword_14024DFB8);
LABEL_14:
        if ( !wil::details::g_processShutdownInProgress
          && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
        {
          AcquireSRWLockExclusive(&stru_14024DFC0);
          if ( !byte_14024DFE1 )
          {
            v10 = pti;
            if ( pti
              || (LastError = GetLastError(),
                  v12 = CreateThreadpoolTimer(
                          _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                          &wil::details::g_featureStateManager,
                          0),
                  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
                    &pti,
                    v12),
                  SetLastError(LastError),
                  (v10 = pti) != 0) )
            {
              pftDueTime = (struct _FILETIME)-3000000000LL;
              SetThreadpoolTimer(v10, &pftDueTime, 0, 0x124F8u);
              byte_14024DFE1 = 1;
            }
          }
          ReleaseSRWLockExclusive(&stru_14024DFC0);
        }
        return;
      }
      if ( v6 <= 0xC7 || v6 - 256 <= 0xFF )
      {
        AcquireSRWLockExclusive(qword_14024DFB8);
        if ( v6 <= 7 && (v8 = 204, _bittest(&v8, v6)) || v6 - 256 <= 0x7F )
        {
          wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage((wil::details_abi::RawUsageIndex *)&v7[1]);
          Ptr = (char)v7[8].Ptr;
        }
        else
        {
          Ptr = wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,2>::RecordUsage(
                  &v7[9],
                  v6,
                  v4,
                  a3);
        }
        if ( v7 )
          ReleaseSRWLockExclusive(v7);
        if ( Ptr )
          goto LABEL_14;
      }
    }
  }
}

```

## disassembly

```asm
0x140035290  push    rbx
0x140035292  push    rbp
0x140035293  push    rsi
0x140035294  push    rdi
0x140035295  push    r14
0x140035297  sub     rsp, 40h
0x14003529b  mov     esi, r8d
0x14003529e  mov     r14d, ecx
0x1400352a1  mov     r8d, edx
0x1400352a4  shr     r8d, 1Fh
0x1400352a8  btr     edx, 1Fh
0x1400352ac  mov     ebx, edx
0x1400352ae  test    ecx, ecx
0x1400352b0  jz      loc_140035419
0x1400352b6  bt      ebx, 1Eh
0x1400352ba  jb      loc_1400354C0
0x1400352c0  mov     ebp, 0FEh
0x1400352c5  test    esi, esi
0x1400352c7  jz      loc_14003559D
0x1400352cd  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1400352d4  jz      loc_14003540D
0x1400352da  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x1400352e1  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1400352e6  test    al, al
0x1400352e8  jz      loc_14003540D
0x1400352ee  mov     rdi, cs:qword_14024DFB8
0x1400352f5  cmp     ebx, ebp
0x1400352f7  jz      loc_140035590
0x1400352fd  cmp     ebx, 0C7h
0x140035303  ja      loc_140035498
0x140035309  mov     rcx, rdi; SRWLock
0x14003530c  call    cs:__imp_AcquireSRWLockExclusive
0x140035313  nop     dword ptr [rax+rax+00h]
0x140035318  cmp     ebx, 7
0x14003531b  ja      loc_1400355AF
0x140035321  mov     eax, 0CCh
0x140035326  bt      eax, ebx
0x140035329  jnb     loc_1400355AF
0x14003532f  mov     r8d, r14d
0x140035332  mov     edx, ebx
0x140035334  lea     rcx, [rdi+8]; this
0x140035338  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14003533d  mov     bl, [rdi+40h]
0x140035340  test    rdi, rdi
0x140035343  jz      short loc_140035354
0x140035345  mov     rcx, rdi; SRWLock
0x140035348  call    cs:__imp_ReleaseSRWLockExclusive
0x14003534f  nop     dword ptr [rax+rax+00h]
0x140035354  test    bl, bl
0x140035356  jz      loc_14003540D
0x14003535c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140035363  jnz     loc_14003540D
0x140035369  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140035370  test    rax, rax
0x140035373  jnz     loc_1400354AE
0x140035379  lea     rcx, stru_14024DFC0; SRWLock
0x140035380  call    cs:__imp_AcquireSRWLockExclusive
0x140035387  nop     dword ptr [rax+rax+00h]
0x14003538c  cmp     cs:byte_14024DFE1, 0
0x140035393  jnz     short loc_1400353F9
0x140035395  mov     rcx, cs:pti; pti
0x14003539c  test    rcx, rcx
0x14003539f  jnz     loc_140035463
0x1400353a5  call    cs:__imp_GetLastError
0x1400353ac  nop     dword ptr [rax+rax+00h]
0x1400353b1  mov     ebx, eax
0x1400353b3  xor     r8d, r8d; pcbe
0x1400353b6  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x1400353bd  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1400353c4  call    cs:__imp_CreateThreadpoolTimer
0x1400353cb  nop     dword ptr [rax+rax+00h]
0x1400353d0  mov     rdx, rax
0x1400353d3  lea     rcx, pti
0x1400353da  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1400353df  mov     ecx, ebx; dwErrCode
0x1400353e1  call    cs:__imp_SetLastError
0x1400353e8  nop     dword ptr [rax+rax+00h]
0x1400353ed  mov     rcx, cs:pti
0x1400353f4  test    rcx, rcx
0x1400353f7  jnz     short loc_140035463
0x1400353f9  lea     rcx, stru_14024DFC0; SRWLock
0x140035400  call    cs:__imp_ReleaseSRWLockExclusive
0x140035407  nop     dword ptr [rax+rax+00h]
0x14003540c  nop
0x14003540d  add     rsp, 40h
0x140035411  pop     r14
0x140035413  pop     rdi
0x140035414  pop     rsi
0x140035415  pop     rbp
0x140035416  pop     rbx
0x140035417  retn
0x140035419  test    esi, esi
0x14003541b  jnz     loc_1400352B6
0x140035421  test    ebx, ebx
0x140035423  jnz     loc_1400352B6
0x140035429  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x14003542e  test    al, al
0x140035430  jnz     short loc_14003540D
0x140035432  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x140035439  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14003543e  test    al, al
0x140035440  jz      short loc_14003540D
0x140035442  mov     rdx, cs:qword_14024DFB8; SRWLock
0x140035449  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x140035450  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x140035455  mov     rcx, cs:qword_14024DFB8; SRWLock
0x14003545c  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x140035461  jmp     short loc_14003540D
0x140035463  mov     rax, 0FFFFFFFF4D2FA200h
0x14003546d  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x140035472  mov     r9d, 124F8h; msWindowLength
0x140035478  xor     r8d, r8d; msPeriod
0x14003547b  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x140035480  call    cs:__imp_SetThreadpoolTimer
0x140035487  nop     dword ptr [rax+rax+00h]
0x14003548c  mov     cs:byte_14024DFE1, 1
0x140035493  jmp     loc_1400353F9
0x140035498  lea     eax, [rbx-100h]
0x14003549e  cmp     eax, 0FFh
0x1400354a3  jbe     loc_140035309
0x1400354a9  jmp     loc_14003540D
0x1400354ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400354b3  test    al, al
0x1400354b5  jz      loc_140035379
0x1400354bb  jmp     loc_14003540D
0x1400354c0  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1400354c7  jz      loc_14003540D
0x1400354cd  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1400354d2  test    al, al
0x1400354d4  jnz     loc_14003540D
0x1400354da  lea     rdx, qword_14024DFC8
0x1400354e1  lea     rcx, [rsp+68h+pftDueTime]
0x1400354e6  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1400354eb  xor     eax, eax
0x1400354ed  mov     [rsp+68h+var_42], ax
0x1400354f2  mov     [rsp+68h+var_48], r14d
0x1400354f7  mov     [rsp+68h+var_44], bx
0x1400354fc  mov     [rsp+68h+var_40], esi
0x140035500  lea     r8d, [rax+0Ch]; unsigned __int64
0x140035504  lea     rdx, [rsp+68h+var_48]; void *
0x140035509  lea     rcx, xmmword_14024E080+8; this
0x140035510  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x140035515  cmp     cs:byte_14024DFE0, 0
0x14003551c  jnz     short loc_140035581
0x14003551e  cmp     cs:qword_14024DFD8, 0
0x140035526  jnz     short loc_140035568
0x140035528  lea     rcx, [rsp+68h+var_48]; this
0x14003552d  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140035532  xor     r8d, r8d; pcbe
0x140035535  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x14003553c  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140035543  call    cs:__imp_CreateThreadpoolTimer
0x14003554a  nop     dword ptr [rax+rax+00h]
0x14003554f  mov     rdx, rax
0x140035552  lea     rcx, qword_14024DFD8
0x140035559  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x14003555e  lea     rcx, [rsp+68h+var_48]; this
0x140035563  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140035568  mov     r8d, 1388h
0x14003556e  lea     rdx, byte_14024DFE0
0x140035575  lea     rcx, qword_14024DFD8
0x14003557c  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x140035581  lea     rcx, [rsp+68h+pftDueTime]
0x140035586  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14003558b  jmp     loc_14003540D
0x140035590  mov     rcx, rdi; SRWLock
0x140035593  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x140035598  jmp     loc_14003535C
0x14003559d  cmp     ebx, ebp
0x14003559f  jz      loc_1400352CD
0x1400355a5  call    wil_RtlStagingConfig_RecordFeatureUsage
0x1400355aa  jmp     loc_14003540D
0x1400355af  lea     eax, [rbx-100h]
0x1400355b5  cmp     eax, 7Fh
0x1400355b8  jbe     loc_14003532F
0x1400355be  lea     rcx, [rdi+48h]
0x1400355c2  mov     r9d, esi
0x1400355c5  mov     r8d, r14d
0x1400355c8  mov     edx, ebx
0x1400355ca  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1400355cf  mov     bl, al
0x1400355d1  jmp     loc_140035340
```
