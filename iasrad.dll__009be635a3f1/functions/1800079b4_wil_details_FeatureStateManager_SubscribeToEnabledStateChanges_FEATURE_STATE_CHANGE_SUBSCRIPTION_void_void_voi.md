# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x1800079b4`
- end: `0x180007a7b`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `199`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180008120`

## callees

- `0x180003338`
- `0x1800079b4`
- `0x180007b78`
- `0x180009140`
- `0x180030010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x1800079e9`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800079e9`

## string_xrefs

- `0x180007a14`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x1800079b4  mov     [rsp+arg_8], rbx
0x1800079b9  mov     [rsp+arg_10], rbp
0x1800079be  push    rsi
0x1800079bf  push    rdi
0x1800079c0  push    r14
0x1800079c2  sub     rsp, 30h
0x1800079c6  mov     qword ptr [rdx], 0
0x1800079cd  mov     rbp, r9
0x1800079d0  cmp     byte ptr [rcx], 0
0x1800079d3  mov     r14, r8
0x1800079d6  mov     rsi, rdx
0x1800079d9  mov     rdi, rcx
0x1800079dc  jz      loc_180007A68
0x1800079e2  lea     rbx, [rcx+20h]
0x1800079e6  mov     rcx, rbx; SRWLock
0x1800079e9  call    cs:__imp_AcquireSRWLockExclusive
0x1800079ef  mov     [rsp+48h+arg_0], rbx
0x1800079f4  lea     rbx, [rdi+90h]
0x1800079fb  cmp     qword ptr [rbx], 0
0x1800079ff  jnz     short loc_180007A4C
0x180007a01  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180007a08  mov     qword ptr [rbx], 0
0x180007a0f  test    rax, rax
0x180007a12  jnz     short loc_180007A33
0x180007a14  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180007a1b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180007a20  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180007a27  test    rax, rax
0x180007a2a  jnz     short loc_180007A33
0x180007a2c  mov     eax, 0C0000139h
0x180007a31  jmp     short loc_180007A48
0x180007a33  mov     r9, rbx
0x180007a36  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180007a3d  xor     r8d, r8d
0x180007a40  mov     rdx, rdi
0x180007a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a48  test    eax, eax
0x180007a4a  jnz     short loc_180007A5E
0x180007a4c  lea     rcx, [rdi+48h]; this
0x180007a50  mov     r9, rbp; void *
0x180007a53  mov     r8, r14; void (*)(void *)
0x180007a56  mov     rdx, rsi; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180007a59  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180007a5e  lea     rcx, [rsp+48h+arg_0]
0x180007a63  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180007a68  mov     rbx, [rsp+48h+arg_8]
0x180007a6d  mov     rbp, [rsp+48h+arg_10]
0x180007a72  add     rsp, 30h
0x180007a76  pop     r14
0x180007a78  pop     rdi
0x180007a79  pop     rsi
0x180007a7a  retn
```
