# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x1800156b0`
- end: `0x180015791`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `225`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callees

- `0x18000bd6c`
- `0x18000f11c`
- `0x18001539c`
- `0x180015490`
- `0x1800156b0`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800156fd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800156fd`

## string_xrefs

- `0x180015729`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
void __fastcall wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **a2,
        void (*a3)(void *),
        void *a4)
{
  FARPROC NtDllProcedureAddress; // rax
  int v8; // eax
  RTL_SRWLOCK *v9; // [rsp+70h] [rbp+18h] BYREF

  if ( a3 == (void (*)(void *))-1LL )
  {
    wil::details::FeatureStateManager::SubscribeToUsageFlush(
      (wil::details::FeatureStateManager *)&wil::details::g_featureStateManager,
      this,
      (void (*)(void *))a2);
  }
  else
  {
    *this = 0;
    if ( wil::details::g_featureStateManager )
    {
      AcquireSRWLockExclusive(&stru_1800225C8);
      v9 = &stru_1800225C8;
      if ( qword_180022638
        || ((NtDllProcedureAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification,
             qword_180022638 = 0,
             g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification)
         || (NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlRegisterFeatureConfigurationChangeNotification"),
             (g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification = (__int64)NtDllProcedureAddress) != 0)
          ? (v8 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(void *), void *, _QWORD, __int64 *))NtDllProcedureAddress)(
                    _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_,
                    &wil::details::g_featureStateManager,
                    0,
                    &qword_180022638))
          : (v8 = -1073741511),
            !v8) )
      {
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)qword_1800225F0,
          this,
          (void (*)(void *))a2,
          a3);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
    }
  }
}

```

## disassembly

```asm
0x1800156b0  push    rbx
0x1800156b2  push    rbp
0x1800156b3  push    rsi
0x1800156b4  push    rdi
0x1800156b5  sub     rsp, 38h
0x1800156b9  mov     rdi, r8
0x1800156bc  mov     rsi, rdx
0x1800156bf  mov     rbx, rcx
0x1800156c2  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1800156c6  jnz     short loc_1800156DF
0x1800156c8  mov     r8, rdx; void (*)(void *)
0x1800156cb  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800156ce  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x1800156d5  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x1800156da  jmp     loc_180015788
0x1800156df  mov     qword ptr [rcx], 0
0x1800156e6  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800156ed  jz      loc_180015788
0x1800156f3  lea     rbp, stru_1800225C8
0x1800156fa  mov     rcx, rbp; SRWLock
0x1800156fd  call    cs:__imp_AcquireSRWLockExclusive
0x180015703  cmp     cs:qword_180022638, 0
0x18001570b  mov     [rsp+58h+arg_10], rbp
0x180015710  jnz     short loc_180015769
0x180015712  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180015719  mov     cs:qword_180022638, 0
0x180015724  test    rax, rax
0x180015727  jnz     short loc_180015748
0x180015729  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180015730  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180015735  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18001573c  test    rax, rax
0x18001573f  jnz     short loc_180015748
0x180015741  mov     eax, 0C0000139h
0x180015746  jmp     short loc_180015765
0x180015748  lea     r9, qword_180022638
0x18001574f  xor     r8d, r8d
0x180015752  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180015759  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180015760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015765  test    eax, eax
0x180015767  jnz     short loc_18001577E
0x180015769  mov     r9, rdi; void *
0x18001576c  lea     rcx, qword_1800225F0; this
0x180015773  mov     r8, rsi; void (*)(void *)
0x180015776  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180015779  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18001577e  lea     rcx, [rsp+58h+arg_10]
0x180015783  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180015788  add     rsp, 38h
0x18001578c  pop     rdi
0x18001578d  pop     rsi
0x18001578e  pop     rbp
0x18001578f  pop     rbx
0x180015790  retn
```
