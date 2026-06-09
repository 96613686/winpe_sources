# Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::UpgradeClearSettingsGroups::StartActivity(void)

- ea: `0x180018cc4`
- end: `0x180018e03`
- name: `?StartActivity@UpgradeClearSettingsGroups@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@QEAAXXZ`
- size: `319`
- prototype: `void __fastcall(Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::UpgradeClearSettingsGroups *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001b50c`

## callees

- `0x180001678`
- `0x180006f50`
- `0x180013200`
- `0x180018cc4`
- `0x180018e0c`
- `0x180033ed0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018d31`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018d31`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180018d13`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180018d13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018d4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018d4a`

## pseudocode

```c
void __fastcall Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::UpgradeClearSettingsGroups::StartActivity(
        Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::UpgradeClearSettingsGroups *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rdi
  __int64 v4; // r8
  const GUID *v5; // r9
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-9h] BYREF
  __int64 v7; // [rsp+38h] [rbp-1h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+40h] [rbp+7h] BYREF
  __int64 *v9; // [rsp+60h] [rbp+27h]
  __int64 v10; // [rsp+68h] [rbp+2Fh]
  PSRWLOCK *p_SRWLock; // [rsp+70h] [rbp+37h]
  __int64 v12; // [rsp+78h] [rbp+3Fh]

  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)this,
    &SRWLock);
  v2 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider() <= 4u )
    *(_OWORD *)(v2 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  *(_DWORD *)v2 = 1;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v3 = Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider();
  if ( *(_DWORD *)v3 > 4u )
  {
    LODWORD(SRWLock) = GetCurrentThreadId();
    v7 = 0;
    v4 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v4 + 4)
      || (v5 = (const GUID *)(v4 + 24), !*(_DWORD *)(v4 + 24))
      && !*(_DWORD *)(v4 + 28)
      && !*(_DWORD *)(v4 + 32)
      && !*(_DWORD *)(v4 + 36) )
    {
      v5 = 0;
    }
    p_SRWLock = &SRWLock;
    v12 = 4;
    v9 = &v7;
    v10 = 8;
    tlgWriteTransfer_EventWriteTransfer(
      (__int64)v3,
      (unsigned __int8 *)&dword_18003EF0C,
      (const GUID *)(v4 + 8),
      v5,
      4u,
      &v8);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::UpgradeClearSettingsGroups *)((char *)this + 288));
}

```

## disassembly

```asm
0x180018cc4  mov     [rsp-8+arg_8], rbx
0x180018cc9  mov     [rsp-8+arg_10], rdi
0x180018cce  push    rbp
0x180018ccf  lea     rbp, [rsp-57h]
0x180018cd4  sub     rsp, 90h
0x180018cdb  mov     rax, cs:__security_cookie
0x180018ce2  xor     rax, rsp
0x180018ce5  mov     [rbp+57h+var_10], rax
0x180018ce9  mov     rbx, rcx
0x180018cec  lea     rdx, [rbp+57h+SRWLock]
0x180018cf0  call    ?LockExclusive@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180018cf5  mov     rdi, [rbx+110h]
0x180018cfc  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x180018d01  mov     r8d, [rax]
0x180018d04  cmp     r8d, 4
0x180018d08  jbe     short loc_180018D1B
0x180018d0a  lea     rdx, [rdi+8]; ActivityId
0x180018d0e  mov     ecx, 3; ControlCode
0x180018d13  call    cs:__imp_EventActivityIdControl
0x180018d19  jmp     short loc_180018D22
0x180018d1b  xorps   xmm0, xmm0
0x180018d1e  movups  xmmword ptr [rdi+8], xmm0
0x180018d22  mov     dword ptr [rdi], 1
0x180018d28  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180018d2c  test    rcx, rcx
0x180018d2f  jz      short loc_180018D37
0x180018d31  call    cs:__imp_ReleaseSRWLockExclusive
0x180018d37  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x180018d3c  mov     rdi, rax
0x180018d3f  mov     ecx, [rax]
0x180018d41  cmp     ecx, 4
0x180018d44  jbe     loc_180018DCF
0x180018d4a  call    cs:__imp_GetCurrentThreadId
0x180018d50  mov     dword ptr [rbp+57h+SRWLock], eax
0x180018d53  mov     [rbp+57h+var_58], 0
0x180018d5b  mov     r8, [rbx+110h]
0x180018d62  cmp     byte ptr [r8+4], 0
0x180018d67  jz      short loc_180018D88
0x180018d69  lea     r9, [r8+18h]
0x180018d6d  cmp     dword ptr [r9], 0
0x180018d71  jnz     short loc_180018D8B
0x180018d73  cmp     dword ptr [r9+4], 0
0x180018d78  jnz     short loc_180018D8B
0x180018d7a  cmp     dword ptr [r9+8], 0
0x180018d7f  jnz     short loc_180018D8B
0x180018d81  cmp     dword ptr [r9+0Ch], 0
0x180018d86  jnz     short loc_180018D8B
0x180018d88  xor     r9d, r9d
0x180018d8b  lea     rax, [rbp+57h+SRWLock]
0x180018d8f  mov     [rbp+57h+var_20], rax
0x180018d93  mov     [rbp+57h+var_18], 4
0x180018d9b  lea     rax, [rbp+57h+var_58]
0x180018d9f  mov     [rbp+57h+var_30], rax
0x180018da3  mov     [rbp+57h+var_28], 8
0x180018dab  add     r8, 8
0x180018daf  lea     rax, [rbp+57h+var_50]
0x180018db3  mov     [rsp+90h+var_68], rax
0x180018db8  mov     [rsp+90h+var_70], 4
0x180018dc0  lea     rdx, dword_18003EF0C
0x180018dc7  mov     rcx, rdi
0x180018dca  call    _tlgWriteTransfer_EventWriteTransfer
0x180018dcf  lea     rcx, [rbx+120h]; this
0x180018dd6  cmp     dword ptr [rcx+18h], 0
0x180018dda  jnz     short loc_180018DE2
0x180018ddc  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180018de1  nop
0x180018de2  mov     rcx, [rbp+57h+var_10]
0x180018de6  xor     rcx, rsp; StackCookie
0x180018de9  call    __security_check_cookie
0x180018dee  lea     r11, [rsp+90h+var_s0]
0x180018df6  mov     rbx, [r11+18h]
0x180018dfa  mov     rdi, [r11+20h]
0x180018dfe  mov     rsp, r11
0x180018e01  pop     rbp
0x180018e02  retn
```
