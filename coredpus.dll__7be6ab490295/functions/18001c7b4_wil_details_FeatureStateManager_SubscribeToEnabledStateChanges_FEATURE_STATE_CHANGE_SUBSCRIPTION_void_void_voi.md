# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18001c7b4`
- end: `0x18001c882`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `206`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18001cf10`

## callees

- `0x180012260`
- `0x18001c7b4`
- `0x18001c988`
- `0x18001de78`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c7e9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c7e9`

## string_xrefs

- `0x18001c81a`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18001c7b4  mov     [rsp+arg_8], rbx
0x18001c7b9  mov     [rsp+arg_10], rbp
0x18001c7be  push    rsi
0x18001c7bf  push    rdi
0x18001c7c0  push    r14
0x18001c7c2  sub     rsp, 30h
0x18001c7c6  mov     qword ptr [rdx], 0
0x18001c7cd  mov     rbp, r9
0x18001c7d0  cmp     byte ptr [rcx], 0
0x18001c7d3  mov     r14, r8
0x18001c7d6  mov     rsi, rdx
0x18001c7d9  mov     rdi, rcx
0x18001c7dc  jz      loc_18001C86E
0x18001c7e2  lea     rbx, [rcx+20h]
0x18001c7e6  mov     rcx, rbx; SRWLock
0x18001c7e9  call    cs:__imp_AcquireSRWLockExclusive
0x18001c7f0  nop     dword ptr [rax+rax+00h]
0x18001c7f5  mov     [rsp+48h+arg_0], rbx
0x18001c7fa  lea     rbx, [rdi+90h]
0x18001c801  cmp     qword ptr [rbx], 0
0x18001c805  jnz     short loc_18001C852
0x18001c807  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18001c80e  mov     qword ptr [rbx], 0
0x18001c815  test    rax, rax
0x18001c818  jnz     short loc_18001C839
0x18001c81a  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18001c821  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001c826  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18001c82d  test    rax, rax
0x18001c830  jnz     short loc_18001C839
0x18001c832  mov     eax, 0C0000139h
0x18001c837  jmp     short loc_18001C84E
0x18001c839  mov     r9, rbx
0x18001c83c  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18001c843  xor     r8d, r8d
0x18001c846  mov     rdx, rdi
0x18001c849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c84e  test    eax, eax
0x18001c850  jnz     short loc_18001C864
0x18001c852  lea     rcx, [rdi+48h]; this
0x18001c856  mov     r9, rbp; void *
0x18001c859  mov     r8, r14; void (*)(void *)
0x18001c85c  mov     rdx, rsi; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18001c85f  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18001c864  lea     rcx, [rsp+48h+arg_0]
0x18001c869  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001c86e  mov     rbx, [rsp+48h+arg_8]
0x18001c873  mov     rbp, [rsp+48h+arg_10]
0x18001c878  add     rsp, 30h
0x18001c87c  pop     r14
0x18001c87e  pop     rdi
0x18001c87f  pop     rsi
0x18001c880  retn
```
