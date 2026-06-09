# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x140017b04`
- end: `0x140017bbf`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `187`
- prototype: `void __fastcall(RTL_SRWLOCK *this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x140017cf0`

## callees

- `0x14000e99c`
- `0x14000eb2c`
- `0x140017b04`
- `0x14001f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140017b34`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140017b34`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140017bac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140017bac`

## string_xrefs

- `0x140017b5a`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x140017b04  push    rbx
0x140017b06  push    rbp
0x140017b07  push    rsi
0x140017b08  push    rdi
0x140017b09  push    r14
0x140017b0b  push    r15
0x140017b0d  sub     rsp, 38h
0x140017b11  mov     qword ptr [rdx], 0
0x140017b18  mov     rbp, r9
0x140017b1b  cmp     byte ptr [rcx], 0
0x140017b1e  mov     r15, r8
0x140017b21  mov     r14, rdx
0x140017b24  mov     rbx, rcx
0x140017b27  jz      loc_140017BB2
0x140017b2d  lea     rdi, [rcx+20h]
0x140017b31  mov     rcx, rdi; SRWLock
0x140017b34  call    cs:__imp_AcquireSRWLockExclusive
0x140017b3a  lea     rsi, [rbx+90h]
0x140017b41  cmp     qword ptr [rsi], 0
0x140017b45  jnz     short loc_140017B92
0x140017b47  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x140017b4e  mov     qword ptr [rsi], 0
0x140017b55  test    rax, rax
0x140017b58  jnz     short loc_140017B79
0x140017b5a  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x140017b61  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x140017b66  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x140017b6d  test    rax, rax
0x140017b70  jnz     short loc_140017B79
0x140017b72  mov     eax, 0C0000139h
0x140017b77  jmp     short loc_140017B8E
0x140017b79  mov     r9, rsi
0x140017b7c  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x140017b83  xor     r8d, r8d
0x140017b86  mov     rdx, rbx
0x140017b89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017b8e  test    eax, eax
0x140017b90  jnz     short loc_140017BA4
0x140017b92  lea     rcx, [rbx+48h]; this
0x140017b96  mov     r9, rbp; void *
0x140017b99  mov     r8, r15; void (*)(void *)
0x140017b9c  mov     rdx, r14; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x140017b9f  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x140017ba4  test    rdi, rdi
0x140017ba7  jz      short loc_140017BB2
0x140017ba9  mov     rcx, rdi; SRWLock
0x140017bac  call    cs:__imp_ReleaseSRWLockExclusive
0x140017bb2  add     rsp, 38h
0x140017bb6  pop     r15
0x140017bb8  pop     r14
0x140017bba  pop     rdi
0x140017bbb  pop     rsi
0x140017bbc  pop     rbp
0x140017bbd  pop     rbx
0x140017bbe  retn
```
