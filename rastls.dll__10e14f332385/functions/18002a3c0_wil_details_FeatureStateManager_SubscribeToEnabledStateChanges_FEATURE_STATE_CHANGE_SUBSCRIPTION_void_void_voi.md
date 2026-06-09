# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18002a3c0`
- end: `0x18002a487`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `199`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18003b570`

## callees

- `0x18002a3c0`
- `0x18002a4f4`
- `0x18002a63c`
- `0x18003b04c`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a3f5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a3f5`

## string_xrefs

- `0x18002a420`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      || ((NtDllProcedureAddress = (__int64 (*)(void))g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification,
           this[18].Ptr = 0,
           NtDllProcedureAddress)
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
0x18002a3c0  mov     [rsp+arg_8], rbx
0x18002a3c5  mov     [rsp+arg_10], rbp
0x18002a3ca  push    rsi
0x18002a3cb  push    rdi
0x18002a3cc  push    r14
0x18002a3ce  sub     rsp, 30h
0x18002a3d2  mov     qword ptr [rdx], 0
0x18002a3d9  mov     rbp, r9
0x18002a3dc  cmp     byte ptr [rcx], 0
0x18002a3df  mov     r14, r8
0x18002a3e2  mov     rsi, rdx
0x18002a3e5  mov     rdi, rcx
0x18002a3e8  jz      loc_18002A474
0x18002a3ee  lea     rbx, [rcx+20h]
0x18002a3f2  mov     rcx, rbx; SRWLock
0x18002a3f5  call    cs:__imp_AcquireSRWLockExclusive
0x18002a3fb  mov     [rsp+48h+arg_0], rbx
0x18002a400  lea     rbx, [rdi+90h]
0x18002a407  cmp     qword ptr [rbx], 0
0x18002a40b  jnz     short loc_18002A458
0x18002a40d  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18002a414  mov     qword ptr [rbx], 0
0x18002a41b  test    rax, rax
0x18002a41e  jnz     short loc_18002A43F
0x18002a420  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18002a427  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002a42c  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18002a433  test    rax, rax
0x18002a436  jnz     short loc_18002A43F
0x18002a438  mov     eax, 0C0000139h
0x18002a43d  jmp     short loc_18002A454
0x18002a43f  mov     r9, rbx
0x18002a442  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18002a449  xor     r8d, r8d
0x18002a44c  mov     rdx, rdi
0x18002a44f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a454  test    eax, eax
0x18002a456  jnz     short loc_18002A46A
0x18002a458  lea     rcx, [rdi+48h]; this
0x18002a45c  mov     r9, rbp; void *
0x18002a45f  mov     r8, r14; void (*)(void *)
0x18002a462  mov     rdx, rsi; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18002a465  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18002a46a  lea     rcx, [rsp+48h+arg_0]
0x18002a46f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002a474  mov     rbx, [rsp+48h+arg_8]
0x18002a479  mov     rbp, [rsp+48h+arg_10]
0x18002a47e  add     rsp, 30h
0x18002a482  pop     r14
0x18002a484  pop     rdi
0x18002a485  pop     rsi
0x18002a486  retn
```
