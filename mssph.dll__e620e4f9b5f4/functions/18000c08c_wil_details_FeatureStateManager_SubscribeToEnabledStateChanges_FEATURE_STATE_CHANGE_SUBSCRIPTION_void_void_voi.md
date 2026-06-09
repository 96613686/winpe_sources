# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000c08c`
- end: `0x18000c147`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `187`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180015370`

## callees

- `0x18000c08c`
- `0x18000d720`
- `0x180014e80`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c0bc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c0bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c134`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c134`

## string_xrefs

- `0x18000c0e2`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(
        RTL_SRWLOCK *this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **a2,
        void (*a3)(void *),
        void *a4)
{
  RTL_SRWLOCK *v8; // rdi
  __int64 (*NtDllProcedureAddress)(void); // rax
  int v10; // eax

  *a2 = 0;
  if ( LOBYTE(this->Ptr) )
  {
    v8 = this + 4;
    AcquireSRWLockExclusive(this + 4);
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
    if ( v8 )
      ReleaseSRWLockExclusive(v8);
  }
}

```

## disassembly

```asm
0x18000c08c  push    rbx
0x18000c08e  push    rbp
0x18000c08f  push    rsi
0x18000c090  push    rdi
0x18000c091  push    r14
0x18000c093  push    r15
0x18000c095  sub     rsp, 38h
0x18000c099  mov     qword ptr [rdx], 0
0x18000c0a0  mov     rbp, r9
0x18000c0a3  cmp     byte ptr [rcx], 0
0x18000c0a6  mov     r15, r8
0x18000c0a9  mov     r14, rdx
0x18000c0ac  mov     rbx, rcx
0x18000c0af  jz      loc_18000C13A
0x18000c0b5  lea     rdi, [rcx+20h]
0x18000c0b9  mov     rcx, rdi; SRWLock
0x18000c0bc  call    cs:__imp_AcquireSRWLockExclusive
0x18000c0c2  lea     rsi, [rbx+90h]
0x18000c0c9  cmp     qword ptr [rsi], 0
0x18000c0cd  jnz     short loc_18000C11A
0x18000c0cf  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000c0d6  mov     qword ptr [rsi], 0
0x18000c0dd  test    rax, rax
0x18000c0e0  jnz     short loc_18000C101
0x18000c0e2  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000c0e9  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000c0ee  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000c0f5  test    rax, rax
0x18000c0f8  jnz     short loc_18000C101
0x18000c0fa  mov     eax, 0C0000139h
0x18000c0ff  jmp     short loc_18000C116
0x18000c101  mov     r9, rsi
0x18000c104  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000c10b  xor     r8d, r8d
0x18000c10e  mov     rdx, rbx
0x18000c111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c116  test    eax, eax
0x18000c118  jnz     short loc_18000C12C
0x18000c11a  lea     rcx, [rbx+48h]; this
0x18000c11e  mov     r9, rbp; void *
0x18000c121  mov     r8, r15; void (*)(void *)
0x18000c124  mov     rdx, r14; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000c127  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000c12c  test    rdi, rdi
0x18000c12f  jz      short loc_18000C13A
0x18000c131  mov     rcx, rdi; SRWLock
0x18000c134  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c13a  add     rsp, 38h
0x18000c13e  pop     r15
0x18000c140  pop     r14
0x18000c142  pop     rdi
0x18000c143  pop     rsi
0x18000c144  pop     rbp
0x18000c145  pop     rbx
0x18000c146  retn
```
