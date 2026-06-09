# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000b698`
- end: `0x18000b75f`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `199`
- prototype: `void __fastcall(RTL_SRWLOCK *this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18000bf10`

## callees

- `0x180006060`
- `0x180007984`
- `0x18000b698`
- `0x18000b85c`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b6cd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b6cd`

## string_xrefs

- `0x18000b6f8`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18000b698  mov     [rsp+arg_8], rbx
0x18000b69d  mov     [rsp+arg_10], rbp
0x18000b6a2  push    rsi
0x18000b6a3  push    rdi
0x18000b6a4  push    r14
0x18000b6a6  sub     rsp, 30h
0x18000b6aa  mov     qword ptr [rdx], 0
0x18000b6b1  mov     rbp, r9
0x18000b6b4  cmp     byte ptr [rcx], 0
0x18000b6b7  mov     r14, r8
0x18000b6ba  mov     rsi, rdx
0x18000b6bd  mov     rdi, rcx
0x18000b6c0  jz      loc_18000B74C
0x18000b6c6  lea     rbx, [rcx+20h]
0x18000b6ca  mov     rcx, rbx; SRWLock
0x18000b6cd  call    cs:__imp_AcquireSRWLockExclusive
0x18000b6d3  mov     [rsp+48h+arg_0], rbx
0x18000b6d8  lea     rbx, [rdi+90h]
0x18000b6df  cmp     qword ptr [rbx], 0
0x18000b6e3  jnz     short loc_18000B730
0x18000b6e5  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000b6ec  mov     qword ptr [rbx], 0
0x18000b6f3  test    rax, rax
0x18000b6f6  jnz     short loc_18000B717
0x18000b6f8  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000b6ff  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000b704  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000b70b  test    rax, rax
0x18000b70e  jnz     short loc_18000B717
0x18000b710  mov     eax, 0C0000139h
0x18000b715  jmp     short loc_18000B72C
0x18000b717  mov     r9, rbx
0x18000b71a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000b721  xor     r8d, r8d
0x18000b724  mov     rdx, rdi
0x18000b727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b72c  test    eax, eax
0x18000b72e  jnz     short loc_18000B742
0x18000b730  lea     rcx, [rdi+48h]; this
0x18000b734  mov     r9, rbp; void *
0x18000b737  mov     r8, r14; void (*)(void *)
0x18000b73a  mov     rdx, rsi; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000b73d  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000b742  lea     rcx, [rsp+48h+arg_0]
0x18000b747  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000b74c  mov     rbx, [rsp+48h+arg_8]
0x18000b751  mov     rbp, [rsp+48h+arg_10]
0x18000b756  add     rsp, 30h
0x18000b75a  pop     r14
0x18000b75c  pop     rdi
0x18000b75d  pop     rsi
0x18000b75e  retn
```
