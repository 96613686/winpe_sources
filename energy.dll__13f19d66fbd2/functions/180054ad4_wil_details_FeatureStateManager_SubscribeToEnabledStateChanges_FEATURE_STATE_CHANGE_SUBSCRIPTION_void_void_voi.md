# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180054ad4`
- end: `0x180054b9b`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `199`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180055190`

## callees

- `0x18003e2e4`
- `0x180054ad4`
- `0x180054c98`
- `0x1800559b0`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180054b09`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180054b09`

## string_xrefs

- `0x180054b34`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x180054ad4  mov     [rsp+arg_8], rbx
0x180054ad9  mov     [rsp+arg_10], rbp
0x180054ade  push    rsi
0x180054adf  push    rdi
0x180054ae0  push    r14
0x180054ae2  sub     rsp, 30h
0x180054ae6  mov     qword ptr [rdx], 0
0x180054aed  mov     rbp, r9
0x180054af0  cmp     byte ptr [rcx], 0
0x180054af3  mov     r14, r8
0x180054af6  mov     rsi, rdx
0x180054af9  mov     rdi, rcx
0x180054afc  jz      loc_180054B88
0x180054b02  lea     rbx, [rcx+20h]
0x180054b06  mov     rcx, rbx; SRWLock
0x180054b09  call    cs:__imp_AcquireSRWLockExclusive
0x180054b0f  mov     [rsp+48h+arg_0], rbx
0x180054b14  lea     rbx, [rdi+90h]
0x180054b1b  cmp     qword ptr [rbx], 0
0x180054b1f  jnz     short loc_180054B6C
0x180054b21  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180054b28  mov     qword ptr [rbx], 0
0x180054b2f  test    rax, rax
0x180054b32  jnz     short loc_180054B53
0x180054b34  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180054b3b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180054b40  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180054b47  test    rax, rax
0x180054b4a  jnz     short loc_180054B53
0x180054b4c  mov     eax, 0C0000139h
0x180054b51  jmp     short loc_180054B68
0x180054b53  mov     r9, rbx
0x180054b56  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180054b5d  xor     r8d, r8d
0x180054b60  mov     rdx, rdi
0x180054b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054b68  test    eax, eax
0x180054b6a  jnz     short loc_180054B7E
0x180054b6c  lea     rcx, [rdi+48h]; this
0x180054b70  mov     r9, rbp; void *
0x180054b73  mov     r8, r14; void (*)(void *)
0x180054b76  mov     rdx, rsi; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180054b79  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180054b7e  lea     rcx, [rsp+48h+arg_0]
0x180054b83  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180054b88  mov     rbx, [rsp+48h+arg_8]
0x180054b8d  mov     rbp, [rsp+48h+arg_10]
0x180054b92  add     rsp, 30h
0x180054b96  pop     r14
0x180054b98  pop     rdi
0x180054b99  pop     rsi
0x180054b9a  retn
```
