# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18003ad4c`
- end: `0x18003ae13`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `199`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18003b410`

## callees

- `0x18002d9c8`
- `0x18003ad4c`
- `0x18003af10`
- `0x18003bc60`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003ad81`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003ad81`

## string_xrefs

- `0x18003adac`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18003ad4c  mov     [rsp+arg_8], rbx
0x18003ad51  mov     [rsp+arg_10], rbp
0x18003ad56  push    rsi
0x18003ad57  push    rdi
0x18003ad58  push    r14
0x18003ad5a  sub     rsp, 30h
0x18003ad5e  mov     qword ptr [rdx], 0
0x18003ad65  mov     rbp, r9
0x18003ad68  cmp     byte ptr [rcx], 0
0x18003ad6b  mov     r14, r8
0x18003ad6e  mov     rsi, rdx
0x18003ad71  mov     rdi, rcx
0x18003ad74  jz      loc_18003AE00
0x18003ad7a  lea     rbx, [rcx+20h]
0x18003ad7e  mov     rcx, rbx; SRWLock
0x18003ad81  call    cs:__imp_AcquireSRWLockExclusive
0x18003ad87  mov     [rsp+48h+arg_0], rbx
0x18003ad8c  lea     rbx, [rdi+90h]
0x18003ad93  cmp     qword ptr [rbx], 0
0x18003ad97  jnz     short loc_18003ADE4
0x18003ad99  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18003ada0  mov     qword ptr [rbx], 0
0x18003ada7  test    rax, rax
0x18003adaa  jnz     short loc_18003ADCB
0x18003adac  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18003adb3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18003adb8  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18003adbf  test    rax, rax
0x18003adc2  jnz     short loc_18003ADCB
0x18003adc4  mov     eax, 0C0000139h
0x18003adc9  jmp     short loc_18003ADE0
0x18003adcb  mov     r9, rbx
0x18003adce  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18003add5  xor     r8d, r8d
0x18003add8  mov     rdx, rdi
0x18003addb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ade0  test    eax, eax
0x18003ade2  jnz     short loc_18003ADF6
0x18003ade4  lea     rcx, [rdi+48h]; this
0x18003ade8  mov     r9, rbp; void *
0x18003adeb  mov     r8, r14; void (*)(void *)
0x18003adee  mov     rdx, rsi; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18003adf1  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18003adf6  lea     rcx, [rsp+48h+arg_0]
0x18003adfb  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003ae00  mov     rbx, [rsp+48h+arg_8]
0x18003ae05  mov     rbp, [rsp+48h+arg_10]
0x18003ae0a  add     rsp, 30h
0x18003ae0e  pop     r14
0x18003ae10  pop     rdi
0x18003ae11  pop     rsi
0x18003ae12  retn
```
