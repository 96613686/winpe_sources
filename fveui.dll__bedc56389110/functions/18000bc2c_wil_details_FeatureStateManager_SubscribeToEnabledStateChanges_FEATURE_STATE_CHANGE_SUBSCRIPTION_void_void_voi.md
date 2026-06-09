# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000bc2c`
- end: `0x18000bcf3`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `199`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18000c560`

## callees

- `0x18000474c`
- `0x18000bc2c`
- `0x18000bdf0`
- `0x18000dd70`
- `0x18002d010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18000bc61`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000bc61`

## string_xrefs

- `0x18000bc8c`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18000bc2c  mov     [rsp+arg_8], rbx
0x18000bc31  mov     [rsp+arg_10], rbp
0x18000bc36  push    rsi
0x18000bc37  push    rdi
0x18000bc38  push    r14
0x18000bc3a  sub     rsp, 30h
0x18000bc3e  mov     qword ptr [rdx], 0
0x18000bc45  mov     rbp, r9
0x18000bc48  cmp     byte ptr [rcx], 0
0x18000bc4b  mov     r14, r8
0x18000bc4e  mov     rsi, rdx
0x18000bc51  mov     rdi, rcx
0x18000bc54  jz      loc_18000BCE0
0x18000bc5a  lea     rbx, [rcx+20h]
0x18000bc5e  mov     rcx, rbx; SRWLock
0x18000bc61  call    cs:__imp_AcquireSRWLockExclusive
0x18000bc67  mov     [rsp+48h+arg_0], rbx
0x18000bc6c  lea     rbx, [rdi+90h]
0x18000bc73  cmp     qword ptr [rbx], 0
0x18000bc77  jnz     short loc_18000BCC4
0x18000bc79  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000bc80  mov     qword ptr [rbx], 0
0x18000bc87  test    rax, rax
0x18000bc8a  jnz     short loc_18000BCAB
0x18000bc8c  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000bc93  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000bc98  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000bc9f  test    rax, rax
0x18000bca2  jnz     short loc_18000BCAB
0x18000bca4  mov     eax, 0C0000139h
0x18000bca9  jmp     short loc_18000BCC0
0x18000bcab  mov     r9, rbx
0x18000bcae  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000bcb5  xor     r8d, r8d
0x18000bcb8  mov     rdx, rdi
0x18000bcbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcc0  test    eax, eax
0x18000bcc2  jnz     short loc_18000BCD6
0x18000bcc4  lea     rcx, [rdi+48h]; this
0x18000bcc8  mov     r9, rbp; void *
0x18000bccb  mov     r8, r14; void (*)(void *)
0x18000bcce  mov     rdx, rsi; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000bcd1  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000bcd6  lea     rcx, [rsp+48h+arg_0]
0x18000bcdb  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000bce0  mov     rbx, [rsp+48h+arg_8]
0x18000bce5  mov     rbp, [rsp+48h+arg_10]
0x18000bcea  add     rsp, 30h
0x18000bcee  pop     r14
0x18000bcf0  pop     rdi
0x18000bcf1  pop     rsi
0x18000bcf2  retn
```
