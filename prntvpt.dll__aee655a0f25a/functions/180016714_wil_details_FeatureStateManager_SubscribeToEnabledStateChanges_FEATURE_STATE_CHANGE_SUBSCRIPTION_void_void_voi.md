# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180016714`
- end: `0x1800167db`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `199`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1800170b0`

## callees

- `0x18000d66c`
- `0x180016714`
- `0x1800168d8`
- `0x18001777c`
- `0x180023010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180016749`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180016749`

## string_xrefs

- `0x180016774`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x180016714  mov     [rsp+arg_8], rbx
0x180016719  mov     [rsp+arg_10], rbp
0x18001671e  push    rsi
0x18001671f  push    rdi
0x180016720  push    r14
0x180016722  sub     rsp, 30h
0x180016726  mov     qword ptr [rdx], 0
0x18001672d  mov     rbp, r9
0x180016730  cmp     byte ptr [rcx], 0
0x180016733  mov     r14, r8
0x180016736  mov     rsi, rdx
0x180016739  mov     rdi, rcx
0x18001673c  jz      loc_1800167C8
0x180016742  lea     rbx, [rcx+20h]
0x180016746  mov     rcx, rbx; SRWLock
0x180016749  call    cs:__imp_AcquireSRWLockExclusive
0x18001674f  mov     [rsp+48h+arg_0], rbx
0x180016754  lea     rbx, [rdi+90h]
0x18001675b  cmp     qword ptr [rbx], 0
0x18001675f  jnz     short loc_1800167AC
0x180016761  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180016768  mov     qword ptr [rbx], 0
0x18001676f  test    rax, rax
0x180016772  jnz     short loc_180016793
0x180016774  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18001677b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180016780  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180016787  test    rax, rax
0x18001678a  jnz     short loc_180016793
0x18001678c  mov     eax, 0C0000139h
0x180016791  jmp     short loc_1800167A8
0x180016793  mov     r9, rbx
0x180016796  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18001679d  xor     r8d, r8d
0x1800167a0  mov     rdx, rdi
0x1800167a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167a8  test    eax, eax
0x1800167aa  jnz     short loc_1800167BE
0x1800167ac  lea     rcx, [rdi+48h]; this
0x1800167b0  mov     r9, rbp; void *
0x1800167b3  mov     r8, r14; void (*)(void *)
0x1800167b6  mov     rdx, rsi; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800167b9  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1800167be  lea     rcx, [rsp+48h+arg_0]
0x1800167c3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800167c8  mov     rbx, [rsp+48h+arg_8]
0x1800167cd  mov     rbp, [rsp+48h+arg_10]
0x1800167d2  add     rsp, 30h
0x1800167d6  pop     r14
0x1800167d8  pop     rdi
0x1800167d9  pop     rsi
0x1800167da  retn
```
