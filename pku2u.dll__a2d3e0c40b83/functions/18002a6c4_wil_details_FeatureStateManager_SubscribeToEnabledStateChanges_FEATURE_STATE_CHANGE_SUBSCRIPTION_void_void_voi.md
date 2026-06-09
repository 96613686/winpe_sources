# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18002a6c4`
- end: `0x18002a78b`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `199`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18002ab10`

## callees

- `0x18001f7b4`
- `0x180027240`
- `0x18002a6c4`
- `0x18002a888`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a6f9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a6f9`

## string_xrefs

- `0x18002a724`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18002a6c4  mov     [rsp+arg_8], rbx
0x18002a6c9  mov     [rsp+arg_10], rbp
0x18002a6ce  push    rsi
0x18002a6cf  push    rdi
0x18002a6d0  push    r14
0x18002a6d2  sub     rsp, 30h
0x18002a6d6  mov     qword ptr [rdx], 0
0x18002a6dd  mov     rbp, r9
0x18002a6e0  cmp     byte ptr [rcx], 0
0x18002a6e3  mov     r14, r8
0x18002a6e6  mov     rsi, rdx
0x18002a6e9  mov     rdi, rcx
0x18002a6ec  jz      loc_18002A778
0x18002a6f2  lea     rbx, [rcx+20h]
0x18002a6f6  mov     rcx, rbx; SRWLock
0x18002a6f9  call    cs:__imp_AcquireSRWLockExclusive
0x18002a6ff  mov     [rsp+48h+arg_0], rbx
0x18002a704  lea     rbx, [rdi+90h]
0x18002a70b  cmp     qword ptr [rbx], 0
0x18002a70f  jnz     short loc_18002A75C
0x18002a711  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18002a718  mov     qword ptr [rbx], 0
0x18002a71f  test    rax, rax
0x18002a722  jnz     short loc_18002A743
0x18002a724  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18002a72b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002a730  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18002a737  test    rax, rax
0x18002a73a  jnz     short loc_18002A743
0x18002a73c  mov     eax, 0C0000139h
0x18002a741  jmp     short loc_18002A758
0x18002a743  mov     r9, rbx
0x18002a746  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18002a74d  xor     r8d, r8d
0x18002a750  mov     rdx, rdi
0x18002a753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a758  test    eax, eax
0x18002a75a  jnz     short loc_18002A76E
0x18002a75c  lea     rcx, [rdi+48h]; this
0x18002a760  mov     r9, rbp; void *
0x18002a763  mov     r8, r14; void (*)(void *)
0x18002a766  mov     rdx, rsi; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18002a769  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18002a76e  lea     rcx, [rsp+48h+arg_0]
0x18002a773  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002a778  mov     rbx, [rsp+48h+arg_8]
0x18002a77d  mov     rbp, [rsp+48h+arg_10]
0x18002a782  add     rsp, 30h
0x18002a786  pop     r14
0x18002a788  pop     rdi
0x18002a789  pop     rsi
0x18002a78a  retn
```
