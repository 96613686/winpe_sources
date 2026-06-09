# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x14001aabc`
- end: `0x14001ab88`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `204`
- prototype: `void __fastcall(RTL_SRWLOCK *this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x14001b1c0`

## callees

- `0x140017254`
- `0x14001aabc`
- `0x14001ac84`
- `0x14001c088`
- `0x140020010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14001aaf1`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14001aaf1`

## string_xrefs

- `0x14001ab1c`: `RtlRegisterFeatureConfigurationChangeNotification`

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
    if ( this[18].Ptr )
    {
      v10 = 0;
    }
    else
    {
      this[18].Ptr = 0;
      NtDllProcedureAddress = (__int64 (*)(void))g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      if ( g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
        || (NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlRegisterFeatureConfigurationChangeNotification"),
            (g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification = (__int64)NtDllProcedureAddress) != 0) )
      {
        v10 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(void *), RTL_SRWLOCK *, _QWORD, RTL_SRWLOCK *))NtDllProcedureAddress)(
                _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_,
                this,
                0,
                &this[18]);
      }
      else
      {
        v10 = -1073741511;
      }
    }
    if ( !v10 )
      wil::details_abi::SubscriptionList::SubscribeUnderLock((wil::details_abi::SubscriptionList *)&this[9], a2, a3, a4);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  }
}

```

## disassembly

```asm
0x14001aabc  mov     [rsp+arg_8], rbx
0x14001aac1  mov     [rsp+arg_10], rbp
0x14001aac6  push    rsi
0x14001aac7  push    rdi
0x14001aac8  push    r14
0x14001aaca  sub     rsp, 30h
0x14001aace  mov     rbp, r9
0x14001aad1  mov     r14, r8
0x14001aad4  mov     rsi, rdx
0x14001aad7  mov     rdi, rcx
0x14001aada  mov     qword ptr [rdx], 0
0x14001aae1  cmp     byte ptr [rcx], 0
0x14001aae4  jz      loc_14001AB75
0x14001aaea  lea     rbx, [rcx+20h]
0x14001aaee  mov     rcx, rbx; SRWLock
0x14001aaf1  call    cs:__imp_AcquireSRWLockExclusive
0x14001aaf7  mov     [rsp+48h+arg_0], rbx
0x14001aafc  lea     rbx, [rdi+90h]
0x14001ab03  cmp     qword ptr [rbx], 0
0x14001ab07  jnz     short loc_14001AB52
0x14001ab09  mov     qword ptr [rbx], 0
0x14001ab10  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x14001ab17  test    rax, rax
0x14001ab1a  jnz     short loc_14001AB3B
0x14001ab1c  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14001ab23  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14001ab28  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14001ab2f  test    rax, rax
0x14001ab32  jnz     short loc_14001AB3B
0x14001ab34  mov     eax, 0C0000139h
0x14001ab39  jmp     short loc_14001AB54
0x14001ab3b  mov     r9, rbx
0x14001ab3e  xor     r8d, r8d
0x14001ab41  mov     rdx, rdi
0x14001ab44  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x14001ab4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ab50  jmp     short loc_14001AB54
0x14001ab52  xor     eax, eax
0x14001ab54  test    eax, eax
0x14001ab56  jnz     short loc_14001AB6B
0x14001ab58  lea     rcx, [rdi+48h]; this
0x14001ab5c  mov     r9, rbp; void *
0x14001ab5f  mov     r8, r14; void (*)(void *)
0x14001ab62  mov     rdx, rsi; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x14001ab65  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x14001ab6a  nop
0x14001ab6b  lea     rcx, [rsp+48h+arg_0]
0x14001ab70  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14001ab75  mov     rbx, [rsp+48h+arg_8]
0x14001ab7a  mov     rbp, [rsp+48h+arg_10]
0x14001ab7f  add     rsp, 30h
0x14001ab83  pop     r14
0x14001ab85  pop     rdi
0x14001ab86  pop     rsi
0x14001ab87  retn
```
