# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x1800076fc`
- end: `0x1800077c8`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `204`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180007e70`

## callees

- `0x18000376c`
- `0x1800076fc`
- `0x1800078c4`
- `0x180008db8`
- `0x180029010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180007731`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180007731`

## string_xrefs

- `0x18000775c`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
0x1800076fc  mov     [rsp+arg_8], rbx
0x180007701  mov     [rsp+arg_10], rbp
0x180007706  push    rsi
0x180007707  push    rdi
0x180007708  push    r14
0x18000770a  sub     rsp, 30h
0x18000770e  mov     rbp, r9
0x180007711  mov     r14, r8
0x180007714  mov     rsi, rdx
0x180007717  mov     rdi, rcx
0x18000771a  mov     qword ptr [rdx], 0
0x180007721  cmp     byte ptr [rcx], 0
0x180007724  jz      loc_1800077B5
0x18000772a  lea     rbx, [rcx+20h]
0x18000772e  mov     rcx, rbx; SRWLock
0x180007731  call    cs:__imp_AcquireSRWLockExclusive
0x180007737  mov     [rsp+48h+arg_0], rbx
0x18000773c  lea     rbx, [rdi+90h]
0x180007743  cmp     qword ptr [rbx], 0
0x180007747  jnz     short loc_180007792
0x180007749  mov     qword ptr [rbx], 0
0x180007750  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180007757  test    rax, rax
0x18000775a  jnz     short loc_18000777B
0x18000775c  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180007763  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180007768  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000776f  test    rax, rax
0x180007772  jnz     short loc_18000777B
0x180007774  mov     eax, 0C0000139h
0x180007779  jmp     short loc_180007794
0x18000777b  mov     r9, rbx
0x18000777e  xor     r8d, r8d
0x180007781  mov     rdx, rdi
0x180007784  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000778b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007790  jmp     short loc_180007794
0x180007792  xor     eax, eax
0x180007794  test    eax, eax
0x180007796  jnz     short loc_1800077AB
0x180007798  lea     rcx, [rdi+48h]; this
0x18000779c  mov     r9, rbp; void *
0x18000779f  mov     r8, r14; void (*)(void *)
0x1800077a2  mov     rdx, rsi; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800077a5  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1800077aa  nop
0x1800077ab  lea     rcx, [rsp+48h+arg_0]
0x1800077b0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800077b5  mov     rbx, [rsp+48h+arg_8]
0x1800077ba  mov     rbp, [rsp+48h+arg_10]
0x1800077bf  add     rsp, 30h
0x1800077c3  pop     r14
0x1800077c5  pop     rdi
0x1800077c6  pop     rsi
0x1800077c7  retn
```
