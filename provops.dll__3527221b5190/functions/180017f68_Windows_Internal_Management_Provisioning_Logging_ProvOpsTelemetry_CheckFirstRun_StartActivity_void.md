# Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::CheckFirstRun::StartActivity(void)

- ea: `0x180017f68`
- end: `0x1800180a4`
- name: `?StartActivity@CheckFirstRun@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@QEAAXXZ`
- size: `316`
- prototype: `void __fastcall(Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::CheckFirstRun *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180011884`

## callees

- `0x180001678`
- `0x180006f50`
- `0x180013200`
- `0x180017f68`
- `0x180018e0c`
- `0x180033ed0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017fd5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017fd5`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180017fb7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180017fb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017fee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017fee`

## pseudocode

```c
void __fastcall Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::CheckFirstRun::StartActivity(
        Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::CheckFirstRun *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rdi
  __int64 v4; // r8
  __int64 v5; // r9
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-9h] BYREF
  _QWORD v7[9]; // [rsp+38h] [rbp-1h] BYREF

  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)this,
    &SRWLock);
  v2 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider() <= 5u )
    *(_OWORD *)(v2 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  *(_DWORD *)v2 = 1;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v3 = Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider();
  if ( *(_DWORD *)v3 > 5u )
  {
    LODWORD(SRWLock) = GetCurrentThreadId();
    v7[0] = 0;
    v4 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v4 + 4)
      || (v5 = v4 + 24, !*(_DWORD *)(v4 + 24))
      && !*(_DWORD *)(v4 + 28)
      && !*(_DWORD *)(v4 + 32)
      && !*(_DWORD *)(v4 + 36) )
    {
      v5 = 0;
    }
    v7[7] = &SRWLock;
    v7[8] = 4;
    v7[5] = v7;
    v7[6] = 8;
    tlgWriteTransfer_EventWriteTransfer(v3, &dword_180040CA4, v4 + 8, v5);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::CheckFirstRun *)((char *)this + 288));
}

```

## disassembly

```asm
0x180017f68  mov     [rsp-8+arg_8], rbx
0x180017f6d  mov     [rsp-8+arg_10], rdi
0x180017f72  push    rbp
0x180017f73  lea     rbp, [rsp-57h]
0x180017f78  sub     rsp, 90h
0x180017f7f  mov     rax, cs:__security_cookie
0x180017f86  xor     rax, rsp
0x180017f89  mov     [rbp+57h+var_10], rax
0x180017f8d  mov     rbx, rcx
0x180017f90  lea     rdx, [rbp+57h+SRWLock]
0x180017f94  call    ?LockExclusive@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180017f99  mov     rdi, [rbx+110h]
0x180017fa0  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x180017fa5  mov     r8d, [rax]
0x180017fa8  cmp     r8d, 5
0x180017fac  jbe     short loc_180017FBF
0x180017fae  lea     rdx, [rdi+8]; ActivityId
0x180017fb2  mov     ecx, 3; ControlCode
0x180017fb7  call    cs:__imp_EventActivityIdControl
0x180017fbd  jmp     short loc_180017FC6
0x180017fbf  xorps   xmm0, xmm0
0x180017fc2  movups  xmmword ptr [rdi+8], xmm0
0x180017fc6  mov     dword ptr [rdi], 1
0x180017fcc  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180017fd0  test    rcx, rcx
0x180017fd3  jz      short loc_180017FDB
0x180017fd5  call    cs:__imp_ReleaseSRWLockExclusive
0x180017fdb  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x180017fe0  mov     rdi, rax
0x180017fe3  mov     ecx, [rax]
0x180017fe5  cmp     ecx, 5
0x180017fe8  jbe     loc_180018070
0x180017fee  call    cs:__imp_GetCurrentThreadId
0x180017ff4  mov     dword ptr [rbp+57h+SRWLock], eax
0x180017ff7  mov     [rbp+57h+var_58], 0
0x180017fff  mov     r8, [rbx+110h]
0x180018006  cmp     byte ptr [r8+4], 0
0x18001800b  jz      short loc_18001802C
0x18001800d  lea     r9, [r8+18h]
0x180018011  cmp     dword ptr [r9], 0
0x180018015  jnz     short loc_18001802F
0x180018017  cmp     dword ptr [r9+4], 0
0x18001801c  jnz     short loc_18001802F
0x18001801e  cmp     dword ptr [r9+8], 0
0x180018023  jnz     short loc_18001802F
0x180018025  cmp     dword ptr [r9+0Ch], 0
0x18001802a  jnz     short loc_18001802F
0x18001802c  xor     r9d, r9d
0x18001802f  lea     rax, [rbp+57h+SRWLock]
0x180018033  mov     [rbp+57h+var_20], rax
0x180018037  mov     ecx, 4
0x18001803c  mov     [rbp+57h+var_18], rcx
0x180018040  lea     rax, [rbp+57h+var_58]
0x180018044  mov     [rbp+57h+var_30], rax
0x180018048  mov     [rbp+57h+var_28], 8
0x180018050  add     r8, 8
0x180018054  lea     rax, [rbp+57h+var_50]
0x180018058  mov     [rsp+90h+var_68], rax
0x18001805d  mov     [rsp+90h+var_70], ecx
0x180018061  lea     rdx, dword_180040CA4
0x180018068  mov     rcx, rdi
0x18001806b  call    _tlgWriteTransfer_EventWriteTransfer
0x180018070  lea     rcx, [rbx+120h]; this
0x180018077  cmp     dword ptr [rcx+18h], 0
0x18001807b  jnz     short loc_180018083
0x18001807d  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180018082  nop
0x180018083  mov     rcx, [rbp+57h+var_10]
0x180018087  xor     rcx, rsp; StackCookie
0x18001808a  call    __security_check_cookie
0x18001808f  lea     r11, [rsp+90h+var_s0]
0x180018097  mov     rbx, [r11+18h]
0x18001809b  mov     rdi, [r11+20h]
0x18001809f  mov     rsp, r11
0x1800180a2  pop     rbp
0x1800180a3  retn
```
