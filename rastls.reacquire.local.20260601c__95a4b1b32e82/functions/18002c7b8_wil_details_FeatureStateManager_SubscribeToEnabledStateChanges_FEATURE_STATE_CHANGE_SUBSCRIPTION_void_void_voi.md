# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18002c7b8`
- end: `0x18002c886`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `206`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18003e3d0`

## callees

- `0x18002c7b8`
- `0x18002c8f8`
- `0x18002ca50`
- `0x18003de64`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002c7ed`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002c7ed`

## string_xrefs

- `0x18002c81e`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18002c7b8  mov     [rsp+arg_8], rbx
0x18002c7bd  mov     [rsp+arg_10], rbp
0x18002c7c2  push    rsi
0x18002c7c3  push    rdi
0x18002c7c4  push    r14
0x18002c7c6  sub     rsp, 30h
0x18002c7ca  mov     qword ptr [rdx], 0
0x18002c7d1  mov     rbp, r9
0x18002c7d4  cmp     byte ptr [rcx], 0
0x18002c7d7  mov     r14, r8
0x18002c7da  mov     rsi, rdx
0x18002c7dd  mov     rdi, rcx
0x18002c7e0  jz      loc_18002C872
0x18002c7e6  lea     rbx, [rcx+20h]
0x18002c7ea  mov     rcx, rbx; SRWLock
0x18002c7ed  call    cs:__imp_AcquireSRWLockExclusive
0x18002c7f4  nop     dword ptr [rax+rax+00h]
0x18002c7f9  mov     [rsp+48h+arg_0], rbx
0x18002c7fe  lea     rbx, [rdi+90h]
0x18002c805  cmp     qword ptr [rbx], 0
0x18002c809  jnz     short loc_18002C856
0x18002c80b  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18002c812  mov     qword ptr [rbx], 0
0x18002c819  test    rax, rax
0x18002c81c  jnz     short loc_18002C83D
0x18002c81e  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18002c825  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002c82a  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18002c831  test    rax, rax
0x18002c834  jnz     short loc_18002C83D
0x18002c836  mov     eax, 0C0000139h
0x18002c83b  jmp     short loc_18002C852
0x18002c83d  mov     r9, rbx
0x18002c840  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18002c847  xor     r8d, r8d
0x18002c84a  mov     rdx, rdi
0x18002c84d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c852  test    eax, eax
0x18002c854  jnz     short loc_18002C868
0x18002c856  lea     rcx, [rdi+48h]; this
0x18002c85a  mov     r9, rbp; void *
0x18002c85d  mov     r8, r14; void (*)(void *)
0x18002c860  mov     rdx, rsi; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18002c863  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18002c868  lea     rcx, [rsp+48h+arg_0]
0x18002c86d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002c872  mov     rbx, [rsp+48h+arg_8]
0x18002c877  mov     rbp, [rsp+48h+arg_10]
0x18002c87c  add     rsp, 30h
0x18002c880  pop     r14
0x18002c882  pop     rdi
0x18002c883  pop     rsi
0x18002c884  retn
```
