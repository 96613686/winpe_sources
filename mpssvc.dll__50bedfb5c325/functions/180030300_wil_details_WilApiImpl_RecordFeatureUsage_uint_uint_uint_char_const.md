# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180030300`
- end: `0x18003066d`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `877`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x18002fedc`
- `0x18002ff40`
- `0x18003012c`
- `0x180030300`
- `0x180030680`
- `0x180031330`
- `0x180032168`
- `0x18006ba5c`
- `0x180079578`
- `0x180079f70`
- `0x18007bdac`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800304b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003055b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800305c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800304b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003055b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800305c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030479`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030586`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800305ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030479`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030586`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800305ec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180030370`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800303dd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003042f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003061e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180030370`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800303dd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003042f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003061e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800303a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800303fd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003054d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800303a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800303fd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003054d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180030498`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800305a5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180030498`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800305a5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::WilApiImpl_RecordFeatureUsage(wil::details *this, __int64 a2, unsigned int a3)
{
  unsigned int v4; // ebp
  __int64 v5; // r8
  unsigned int v6; // ebx
  PSRWLOCK v7; // rdi
  int v8; // eax
  char Ptr; // bl
  RTL_SRWLOCK *v10; // rcx
  DWORD LastError; // ebx
  PTP_TIMER ThreadpoolTimer; // rax
  DWORD v13; // ebx
  PTP_TIMER v14; // rax
  DWORD v15; // esi
  RTL_SRWLOCK *Shared; // rdi
  unsigned int v17; // [rsp+20h] [rbp-38h] BYREF
  __int16 v18; // [rsp+24h] [rbp-34h]
  __int16 v19; // [rsp+26h] [rbp-32h]
  unsigned int v20; // [rsp+28h] [rbp-30h]

  v4 = (unsigned int)this;
  v5 = (unsigned int)a2 >> 31;
  LODWORD(a2) = a2 & 0x7FFFFFFF;
  v6 = a2;
  if ( !(_DWORD)this && !a3 && !(_DWORD)a2 )
  {
    wil::details::FeatureStateManager::FlushUsage((wil::details::FeatureStateManager *)&wil::details::g_featureStateManager);
    return;
  }
  if ( (a2 & 0x40000000) != 0 )
  {
    if ( wil::details::g_featureStateManager && !wil::ProcessShutdownInProgress(this) )
    {
      AcquireSRWLockExclusive(&stru_180130648);
      v19 = 0;
      v17 = v4;
      v18 = v6;
      v20 = a3;
      wil::details_abi::heap_buffer::push_back(
        (wil::details_abi::heap_buffer *)((char *)&xmmword_180130700 + 8),
        &v17,
        0xCu);
      if ( !byte_180130660 )
      {
        if ( !qword_180130658 )
        {
          LastError = GetLastError();
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                              &wil::details::g_featureStateManager,
                              0);
          wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
            &qword_180130658,
            ThreadpoolTimer);
          SetLastError(LastError);
        }
        wil::details::EnsureCoalescedTimer_SetTimer(&qword_180130658, &byte_180130660, 5000);
      }
      v10 = &stru_180130648;
      goto LABEL_17;
    }
  }
  else
  {
    if ( !a3 && (_DWORD)a2 != 254 )
    {
      wil_RtlStagingConfig_RecordFeatureUsage(this, a2, v5);
      return;
    }
    if ( wil::details::g_featureStateManager )
    {
      v7 = qword_180130638;
      if ( qword_180130638 )
        goto LABEL_6;
      v15 = GetLastError();
      if ( qword_180130638 )
        Shared = 0;
      else
        Shared = (RTL_SRWLOCK *)wil::details_abi::ProcessLocalStorage<wil::details_abi::FeatureStateData>::GetShared(&off_180130628);
      AcquireSRWLockExclusive(&stru_180130640);
      if ( !qword_180130638 )
        qword_180130638 = Shared;
      ReleaseSRWLockExclusive(&stru_180130640);
      SetLastError(v15);
      v7 = qword_180130638;
      if ( qword_180130638 )
      {
LABEL_6:
        if ( v6 == 254 )
        {
          wil::details_abi::FeatureStateData::RecordUsage(v7);
        }
        else
        {
          if ( v6 > 0xC7 && v6 - 256 > 0xFF )
            return;
          if ( (AcquireSRWLockExclusive(v7), v6 <= 7) && (v8 = 204, _bittest(&v8, v6)) || v6 - 256 <= 0x7F )
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
          ReleaseSRWLockExclusive(v7);
          if ( !Ptr )
            return;
        }
        if ( !wil::details::g_processShutdownInProgress
          && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
        {
          AcquireSRWLockExclusive(&stru_180130640);
          if ( !byte_180130661 )
          {
            if ( !qword_180130650 )
            {
              v13 = GetLastError();
              v14 = CreateThreadpoolTimer(
                      _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                      &wil::details::g_featureStateManager,
                      0);
              wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
                &qword_180130650,
                v14);
              SetLastError(v13);
            }
            wil::details::EnsureCoalescedTimer_SetTimer(&qword_180130650, &byte_180130661, 300000);
          }
          v10 = &stru_180130640;
LABEL_17:
          ReleaseSRWLockExclusive(v10);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180030300  push    rbx
0x180030302  push    rbp
0x180030303  push    rsi
0x180030304  push    rdi
0x180030305  push    r14
0x180030307  sub     rsp, 30h
0x18003030b  mov     r14d, r8d
0x18003030e  mov     ebp, ecx
0x180030310  mov     r8d, edx
0x180030313  shr     r8d, 1Fh
0x180030317  btr     edx, 1Fh
0x18003031b  mov     ebx, edx
0x18003031d  test    ecx, ecx
0x18003031f  jz      loc_180030509
0x180030325  bt      ebx, 1Eh
0x180030329  jb      loc_180030416
0x18003032f  test    r14d, r14d
0x180030332  jz      loc_180030530
0x180030338  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18003033f  jz      loc_18003040A
0x180030345  mov     rdi, cs:qword_180130638
0x18003034c  test    rdi, rdi
0x18003034f  jz      loc_1800305EC
0x180030355  cmp     ebx, 0FEh
0x18003035b  jz      loc_1800304FC
0x180030361  cmp     ebx, 0C7h
0x180030367  ja      loc_1800304E6
0x18003036d  mov     rcx, rdi; SRWLock
0x180030370  call    cs:__imp_AcquireSRWLockExclusive
0x180030377  nop     dword ptr [rax+rax+00h]
0x18003037c  cmp     ebx, 7
0x18003037f  ja      loc_180030644
0x180030385  mov     eax, 0CCh
0x18003038a  bt      eax, ebx
0x18003038d  jnb     loc_180030644
0x180030393  mov     r8d, ebp
0x180030396  mov     edx, ebx
0x180030398  lea     rcx, [rdi+8]; this
0x18003039c  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800303a1  movzx   ebx, byte ptr [rdi+40h]
0x1800303a5  mov     rcx, rdi; SRWLock
0x1800303a8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800303af  nop     dword ptr [rax+rax+00h]
0x1800303b4  test    bl, bl
0x1800303b6  jz      short loc_18003040A
0x1800303b8  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800303bf  jnz     short loc_18003040A
0x1800303c1  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800303c8  test    rax, rax
0x1800303cb  jz      short loc_1800303D6
0x1800303cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800303d2  test    al, al
0x1800303d4  jnz     short loc_18003040A
0x1800303d6  lea     rcx, stru_180130640; SRWLock
0x1800303dd  call    cs:__imp_AcquireSRWLockExclusive
0x1800303e4  nop     dword ptr [rax+rax+00h]
0x1800303e9  cmp     cs:byte_180130661, 0
0x1800303f0  jz      loc_18003057C
0x1800303f6  lea     rcx, stru_180130640; SRWLock
0x1800303fd  call    cs:__imp_ReleaseSRWLockExclusive
0x180030404  nop     dword ptr [rax+rax+00h]
0x180030409  nop
0x18003040a  add     rsp, 30h
0x18003040e  pop     r14
0x180030410  pop     rdi
0x180030411  pop     rsi
0x180030412  pop     rbp
0x180030413  pop     rbx
0x180030414  retn
0x180030416  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18003041d  jz      short loc_18003040A
0x18003041f  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180030424  test    al, al
0x180030426  jnz     short loc_18003040A
0x180030428  lea     rcx, stru_180130648; SRWLock
0x18003042f  call    cs:__imp_AcquireSRWLockExclusive
0x180030436  nop     dword ptr [rax+rax+00h]
0x18003043b  xor     edi, edi
0x18003043d  mov     [rsp+58h+var_32], di
0x180030442  mov     [rsp+58h+var_38], ebp
0x180030446  mov     [rsp+58h+var_34], bx
0x18003044b  mov     [rsp+58h+var_30], r14d
0x180030450  mov     r8d, 0Ch; unsigned __int64
0x180030456  lea     rdx, [rsp+58h+var_38]; void *
0x18003045b  lea     rcx, xmmword_180130700+8; this
0x180030462  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180030467  cmp     cs:byte_180130660, dil
0x18003046e  jnz     short loc_1800304DA
0x180030470  cmp     cs:qword_180130658, rdi
0x180030477  jnz     short loc_1800304C1
0x180030479  call    cs:__imp_GetLastError
0x180030480  nop     dword ptr [rax+rax+00h]
0x180030485  mov     ebx, eax
0x180030487  xor     r8d, r8d; pcbe
0x18003048a  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180030491  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180030498  call    cs:__imp_CreateThreadpoolTimer
0x18003049f  nop     dword ptr [rax+rax+00h]
0x1800304a4  mov     rdx, rax
0x1800304a7  lea     rcx, qword_180130658
0x1800304ae  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800304b3  mov     ecx, ebx; dwErrCode
0x1800304b5  call    cs:__imp_SetLastError
0x1800304bc  nop     dword ptr [rax+rax+00h]
0x1800304c1  mov     r8d, 1388h
0x1800304c7  lea     rdx, byte_180130660
0x1800304ce  lea     rcx, qword_180130658
0x1800304d5  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800304da  lea     rcx, stru_180130648
0x1800304e1  jmp     loc_1800303FD
0x1800304e6  lea     eax, [rbx-100h]
0x1800304ec  cmp     eax, 0FFh
0x1800304f1  jbe     loc_18003036D
0x1800304f7  jmp     loc_18003040A
0x1800304fc  mov     rcx, rdi; SRWLock
0x1800304ff  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180030504  jmp     loc_1800303B8
0x180030509  test    r14d, r14d
0x18003050c  jnz     loc_180030325
0x180030512  test    ebx, ebx
0x180030514  jnz     loc_180030325
0x18003051a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180030521  add     rsp, 30h
0x180030525  pop     r14
0x180030527  pop     rdi
0x180030528  pop     rsi
0x180030529  pop     rbp
0x18003052a  pop     rbx
0x18003052b  jmp     ?FlushUsage@FeatureStateManager@details@wil@@QEAAXXZ; wil::details::FeatureStateManager::FlushUsage(void)
0x180030530  cmp     ebx, 0FEh
0x180030536  jz      loc_180030338
0x18003053c  call    wil_RtlStagingConfig_RecordFeatureUsage
0x180030541  jmp     loc_18003040A
0x180030546  lea     rcx, stru_180130640; SRWLock
0x18003054d  call    cs:__imp_ReleaseSRWLockExclusive
0x180030554  nop     dword ptr [rax+rax+00h]
0x180030559  mov     ecx, esi; dwErrCode
0x18003055b  call    cs:__imp_SetLastError
0x180030562  nop     dword ptr [rax+rax+00h]
0x180030567  mov     rdi, cs:qword_180130638
0x18003056e  test    rdi, rdi
0x180030571  jz      loc_18003040A
0x180030577  jmp     loc_180030355
0x18003057c  cmp     cs:qword_180130650, 0
0x180030584  jnz     short loc_1800305CE
0x180030586  call    cs:__imp_GetLastError
0x18003058d  nop     dword ptr [rax+rax+00h]
0x180030592  mov     ebx, eax
0x180030594  xor     r8d, r8d; pcbe
0x180030597  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18003059e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800305a5  call    cs:__imp_CreateThreadpoolTimer
0x1800305ac  nop     dword ptr [rax+rax+00h]
0x1800305b1  mov     rdx, rax
0x1800305b4  lea     rcx, qword_180130650
0x1800305bb  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800305c0  mov     ecx, ebx; dwErrCode
0x1800305c2  call    cs:__imp_SetLastError
0x1800305c9  nop     dword ptr [rax+rax+00h]
0x1800305ce  mov     r8d, 493E0h
0x1800305d4  lea     rdx, byte_180130661
0x1800305db  lea     rcx, qword_180130650
0x1800305e2  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800305e7  jmp     loc_1800303F6
0x1800305ec  call    cs:__imp_GetLastError
0x1800305f3  nop     dword ptr [rax+rax+00h]
0x1800305f8  mov     esi, eax
0x1800305fa  cmp     cs:qword_180130638, 0
0x180030602  jz      short loc_180030608
0x180030604  xor     edi, edi
0x180030606  jmp     short loc_180030617
0x180030608  lea     rcx, off_180130628; "WilStaging_02"
0x18003060f  call    ?GetShared@?$ProcessLocalStorage@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAPEAVFeatureStateData@23@XZ; wil::details_abi::ProcessLocalStorage<wil::details_abi::FeatureStateData>::GetShared(void)
0x180030614  mov     rdi, rax
0x180030617  lea     rcx, stru_180130640; SRWLock
0x18003061e  call    cs:__imp_AcquireSRWLockExclusive
0x180030625  nop     dword ptr [rax+rax+00h]
0x18003062a  cmp     cs:qword_180130638, 0
0x180030632  jnz     loc_180030546
0x180030638  mov     cs:qword_180130638, rdi
0x18003063f  jmp     loc_180030546
0x180030644  lea     eax, [rbx-100h]
0x18003064a  cmp     eax, 7Fh
0x18003064d  jbe     loc_180030393
0x180030653  lea     rcx, [rdi+48h]
0x180030657  mov     r9d, r14d
0x18003065a  mov     r8d, ebp
0x18003065d  mov     edx, ebx
0x18003065f  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180030664  movzx   ebx, al
0x180030667  jmp     loc_1800303A5
```
