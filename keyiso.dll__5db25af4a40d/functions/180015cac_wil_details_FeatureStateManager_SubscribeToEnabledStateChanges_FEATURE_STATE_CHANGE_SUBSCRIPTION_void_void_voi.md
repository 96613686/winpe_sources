# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180015cac`
- end: `0x180015d73`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `199`
- prototype: `void __fastcall(RTL_SRWLOCK *this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180016370`

## callees

- `0x18000acac`
- `0x180015cac`
- `0x180015e70`
- `0x180016bf0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015ce1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015ce1`

## string_xrefs

- `0x180015d0c`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(
        RTL_SRWLOCK *this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **a2,
        void (*a3)(void *),
        void *a4)
{
  RTL_SRWLOCK *v8; // rbx
  __int64 (*NtDllProcedureAddress)(void); // rax
  int v10; // eax
  RTL_SRWLOCK *v11; // [rsp+50h] [rbp+8h] BYREF

  *a2 = 0;
  if ( LOBYTE(this->Ptr) )
  {
    v8 = this + 4;
    AcquireSRWLockExclusive(this + 4);
    v11 = v8;
    if ( this[18].Ptr
      || ((this[18].Ptr = 0,
           (NtDllProcedureAddress = (__int64 (*)(void))g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification) != 0)
       || (NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlRegisterFeatureConfigurationChangeNotification"),
           (g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification = (__int64)NtDllProcedureAddress) != 0)
        ? (v10 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(void *), RTL_SRWLOCK *, _QWORD, RTL_SRWLOCK *))NtDllProcedureAddress)(
                   _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_,
                   this,
                   0,
                   &this[18]))
        : (v10 = -1073741511),
          !v10) )
    {
      wil::details_abi::SubscriptionList::SubscribeUnderLock((wil::details_abi::SubscriptionList *)&this[9], a2, a3, a4);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  }
}

```

## disassembly

```asm
0x180015cac  mov     [rsp+arg_8], rbx
0x180015cb1  mov     [rsp+arg_10], rbp
0x180015cb6  push    rsi
0x180015cb7  push    rdi
0x180015cb8  push    r14
0x180015cba  sub     rsp, 30h
0x180015cbe  mov     rbp, r9
0x180015cc1  mov     r14, r8
0x180015cc4  mov     rsi, rdx
0x180015cc7  mov     rdi, rcx
0x180015cca  mov     qword ptr [rdx], 0
0x180015cd1  cmp     byte ptr [rcx], 0
0x180015cd4  jz      loc_180015D60
0x180015cda  lea     rbx, [rcx+20h]
0x180015cde  mov     rcx, rbx; SRWLock
0x180015ce1  call    cs:__imp_AcquireSRWLockExclusive
0x180015ce7  mov     [rsp+48h+arg_0], rbx
0x180015cec  lea     rbx, [rdi+90h]
0x180015cf3  cmp     qword ptr [rbx], 0
0x180015cf7  jnz     short loc_180015D44
0x180015cf9  mov     qword ptr [rbx], 0
0x180015d00  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180015d07  test    rax, rax
0x180015d0a  jnz     short loc_180015D2B
0x180015d0c  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180015d13  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180015d18  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180015d1f  test    rax, rax
0x180015d22  jnz     short loc_180015D2B
0x180015d24  mov     eax, 0C0000139h
0x180015d29  jmp     short loc_180015D40
0x180015d2b  mov     r9, rbx
0x180015d2e  xor     r8d, r8d
0x180015d31  mov     rdx, rdi
0x180015d34  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180015d3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d40  test    eax, eax
0x180015d42  jnz     short loc_180015D56
0x180015d44  lea     rcx, [rdi+48h]; this
0x180015d48  mov     r9, rbp; void *
0x180015d4b  mov     r8, r14; void (*)(void *)
0x180015d4e  mov     rdx, rsi; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180015d51  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180015d56  lea     rcx, [rsp+48h+arg_0]
0x180015d5b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180015d60  mov     rbx, [rsp+48h+arg_8]
0x180015d65  mov     rbp, [rsp+48h+arg_10]
0x180015d6a  add     rsp, 30h
0x180015d6e  pop     r14
0x180015d70  pop     rdi
0x180015d71  pop     rsi
0x180015d72  retn
```
