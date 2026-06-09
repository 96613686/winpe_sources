# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180009048`
- end: `0x18000910f`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `199`
- prototype: `void __fastcall(RTL_SRWLOCK *this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1800096a0`

## callees

- `0x180003620`
- `0x180009048`
- `0x18000920c`
- `0x18000a140`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000907d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000907d`

## string_xrefs

- `0x1800090a8`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x180009048  mov     [rsp+arg_8], rbx
0x18000904d  mov     [rsp+arg_10], rbp
0x180009052  push    rsi
0x180009053  push    rdi
0x180009054  push    r14
0x180009056  sub     rsp, 30h
0x18000905a  mov     qword ptr [rdx], 0
0x180009061  mov     rbp, r9
0x180009064  cmp     byte ptr [rcx], 0
0x180009067  mov     r14, r8
0x18000906a  mov     rsi, rdx
0x18000906d  mov     rdi, rcx
0x180009070  jz      loc_1800090FC
0x180009076  lea     rbx, [rcx+20h]
0x18000907a  mov     rcx, rbx; SRWLock
0x18000907d  call    cs:__imp_AcquireSRWLockExclusive
0x180009083  mov     [rsp+48h+arg_0], rbx
0x180009088  lea     rbx, [rdi+90h]
0x18000908f  cmp     qword ptr [rbx], 0
0x180009093  jnz     short loc_1800090E0
0x180009095  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000909c  mov     qword ptr [rbx], 0
0x1800090a3  test    rax, rax
0x1800090a6  jnz     short loc_1800090C7
0x1800090a8  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1800090af  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800090b4  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1800090bb  test    rax, rax
0x1800090be  jnz     short loc_1800090C7
0x1800090c0  mov     eax, 0C0000139h
0x1800090c5  jmp     short loc_1800090DC
0x1800090c7  mov     r9, rbx
0x1800090ca  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x1800090d1  xor     r8d, r8d
0x1800090d4  mov     rdx, rdi
0x1800090d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090dc  test    eax, eax
0x1800090de  jnz     short loc_1800090F2
0x1800090e0  lea     rcx, [rdi+48h]; this
0x1800090e4  mov     r9, rbp; void *
0x1800090e7  mov     r8, r14; void (*)(void *)
0x1800090ea  mov     rdx, rsi; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800090ed  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1800090f2  lea     rcx, [rsp+48h+arg_0]
0x1800090f7  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800090fc  mov     rbx, [rsp+48h+arg_8]
0x180009101  mov     rbp, [rsp+48h+arg_10]
0x180009106  add     rsp, 30h
0x18000910a  pop     r14
0x18000910c  pop     rdi
0x18000910d  pop     rsi
0x18000910e  retn
```
