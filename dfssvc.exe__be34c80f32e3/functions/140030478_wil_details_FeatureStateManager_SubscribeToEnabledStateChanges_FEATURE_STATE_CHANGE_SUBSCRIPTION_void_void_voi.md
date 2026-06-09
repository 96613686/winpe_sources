# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x140030478`
- end: `0x140030540`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `200`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x140031910`

## callees

- `0x140027984`
- `0x140030478`
- `0x140030644`
- `0x140032044`
- `0x14005e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400304aa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400304aa`

## string_xrefs

- `0x1400304d8`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      || ((this[18].Ptr = 0,
           (NtDllProcedureAddress = (__int64 (*)(void))g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification) != 0)
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
0x140030478  mov     [rsp+arg_8], rbx
0x14003047d  mov     [rsp+arg_10], rbp
0x140030482  push    rsi
0x140030483  push    rdi
0x140030484  push    r14
0x140030486  sub     rsp, 30h
0x14003048a  and     qword ptr [rdx], 0
0x14003048e  mov     rbp, r9
0x140030491  cmp     byte ptr [rcx], 0
0x140030494  mov     r14, r8
0x140030497  mov     rsi, rdx
0x14003049a  mov     rdi, rcx
0x14003049d  jz      loc_14003052C
0x1400304a3  lea     rbx, [rcx+20h]
0x1400304a7  mov     rcx, rbx; SRWLock
0x1400304aa  call    cs:__imp_AcquireSRWLockExclusive
0x1400304b1  nop     dword ptr [rax+rax+00h]
0x1400304b6  mov     [rsp+48h+arg_0], rbx
0x1400304bb  lea     rbx, [rdi+90h]
0x1400304c2  cmp     qword ptr [rbx], 0
0x1400304c6  jnz     short loc_140030510
0x1400304c8  and     qword ptr [rbx], 0
0x1400304cc  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x1400304d3  test    rax, rax
0x1400304d6  jnz     short loc_1400304F7
0x1400304d8  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1400304df  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1400304e4  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1400304eb  test    rax, rax
0x1400304ee  jnz     short loc_1400304F7
0x1400304f0  mov     eax, 0C0000139h
0x1400304f5  jmp     short loc_14003050C
0x1400304f7  mov     r9, rbx
0x1400304fa  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x140030501  xor     r8d, r8d
0x140030504  mov     rdx, rdi
0x140030507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003050c  test    eax, eax
0x14003050e  jnz     short loc_140030522
0x140030510  lea     rcx, [rdi+48h]; this
0x140030514  mov     r9, rbp; void *
0x140030517  mov     r8, r14; void (*)(void *)
0x14003051a  mov     rdx, rsi; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x14003051d  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x140030522  lea     rcx, [rsp+48h+arg_0]
0x140030527  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14003052c  mov     rbx, [rsp+48h+arg_8]
0x140030531  mov     rbp, [rsp+48h+arg_10]
0x140030536  add     rsp, 30h
0x14003053a  pop     r14
0x14003053c  pop     rdi
0x14003053d  pop     rsi
0x14003053e  retn
```
