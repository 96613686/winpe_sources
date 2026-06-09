# Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsPublishDeviceProvisioningLogs::StartActivity(void)

- ea: `0x180018944`
- end: `0x180018ab3`
- name: `?StartActivity@ProvOpsPublishDeviceProvisioningLogs@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@QEAAXXZ`
- size: `367`
- prototype: `void __fastcall(Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsPublishDeviceProvisioningLogs *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800145a0`

## callees

- `0x180001678`
- `0x180006f50`
- `0x180013200`
- `0x180018944`
- `0x180018e0c`
- `0x180033ed0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800189cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800189cc`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800189ae`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800189ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018a05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018a05`

## pseudocode

```c
void __fastcall Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsPublishDeviceProvisioningLogs::StartActivity(
        Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsPublishDeviceProvisioningLogs *this)
{
  __int64 v2; // rbx
  const struct _tlgProvider_t *v3; // rax
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // rbx
  __int64 v6; // rax
  __int64 v7; // r8
  const GUID *v8; // r9
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-29h] BYREF
  __int64 v10; // [rsp+38h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+40h] [rbp-19h] BYREF
  __int64 *v12; // [rsp+60h] [rbp+7h]
  __int64 v13; // [rsp+68h] [rbp+Fh]
  PSRWLOCK *p_SRWLock; // [rsp+70h] [rbp+17h]
  __int64 v15; // [rsp+78h] [rbp+1Fh]

  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)this,
    &SRWLock);
  v2 = *((_QWORD *)this + 34);
  v3 = Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider();
  if ( *(_DWORD *)v3 > 5u
    && (*((_QWORD *)v3 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v3 + 3) & 0x400000000000LL) == *((_QWORD *)v3 + 3) )
  {
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  }
  else
  {
    *(_OWORD *)(v2 + 8) = 0;
  }
  *(_DWORD *)v2 = 1;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v4 = Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider();
  v5 = (__int64)v4;
  if ( *(_DWORD *)v4 > 5u )
  {
    v6 = *((_QWORD *)v4 + 3);
    if ( (*(_QWORD *)(v5 + 16) & 0x400000000000LL) != 0 && (v6 & 0x400000000000LL) == v6 )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v10 = 0x1000000;
      v7 = *((_QWORD *)this + 34);
      if ( !*(_BYTE *)(v7 + 4)
        || (v8 = (const GUID *)(v7 + 24), !*(_DWORD *)(v7 + 24))
        && !*(_DWORD *)(v7 + 28)
        && !*(_DWORD *)(v7 + 32)
        && !*(_DWORD *)(v7 + 36) )
      {
        v8 = 0;
      }
      p_SRWLock = &SRWLock;
      v15 = 4;
      v12 = &v10;
      v13 = 8;
      tlgWriteTransfer_EventWriteTransfer(v5, (unsigned __int8 *)byte_18003F7F1, (const GUID *)(v7 + 8), v8, 4u, &v11);
    }
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsPublishDeviceProvisioningLogs *)((char *)this + 288));
}

```

## disassembly

```asm
0x180018944  push    rbp
0x180018946  push    rbx
0x180018947  push    rdi
0x180018948  push    r14
0x18001894a  lea     rbp, [rsp-3Fh]
0x18001894f  sub     rsp, 98h
0x180018956  mov     rax, cs:__security_cookie
0x18001895d  xor     rax, rsp
0x180018960  mov     [rbp+57h+var_30], rax
0x180018964  mov     rdi, rcx
0x180018967  lea     rdx, [rbp+57h+SRWLock]
0x18001896b  call    ?LockExclusive@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180018970  mov     rbx, [rdi+110h]
0x180018977  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x18001897c  mov     edx, [rax]
0x18001897e  mov     r14, 400000000000h
0x180018988  cmp     edx, 5
0x18001898b  jbe     short loc_1800189B6
0x18001898d  mov     rcx, [rax+18h]
0x180018991  mov     rax, [rax+10h]
0x180018995  test    r14, rax
0x180018998  jz      short loc_1800189B6
0x18001899a  mov     rax, rcx
0x18001899d  and     rax, r14
0x1800189a0  cmp     rax, rcx
0x1800189a3  jnz     short loc_1800189B6
0x1800189a5  lea     rdx, [rbx+8]; ActivityId
0x1800189a9  mov     ecx, 3; ControlCode
0x1800189ae  call    cs:__imp_EventActivityIdControl
0x1800189b4  jmp     short loc_1800189BD
0x1800189b6  xorps   xmm0, xmm0
0x1800189b9  movups  xmmword ptr [rbx+8], xmm0
0x1800189bd  mov     dword ptr [rbx], 1
0x1800189c3  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800189c7  test    rcx, rcx
0x1800189ca  jz      short loc_1800189D2
0x1800189cc  call    cs:__imp_ReleaseSRWLockExclusive
0x1800189d2  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x1800189d7  mov     rbx, rax
0x1800189da  mov     ecx, [rax]
0x1800189dc  cmp     ecx, 5
0x1800189df  jbe     loc_180018A87
0x1800189e5  mov     rax, [rax+18h]
0x1800189e9  mov     rcx, [rbx+10h]
0x1800189ed  test    r14, rcx
0x1800189f0  jz      loc_180018A87
0x1800189f6  mov     rcx, rax
0x1800189f9  and     rcx, r14
0x1800189fc  cmp     rcx, rax
0x1800189ff  jnz     loc_180018A87
0x180018a05  call    cs:__imp_GetCurrentThreadId
0x180018a0b  mov     dword ptr [rbp+57h+SRWLock], eax
0x180018a0e  mov     [rbp+57h+var_78], 1000000h
0x180018a16  mov     r8, [rdi+110h]
0x180018a1d  cmp     byte ptr [r8+4], 0
0x180018a22  jz      short loc_180018A43
0x180018a24  lea     r9, [r8+18h]
0x180018a28  cmp     dword ptr [r9], 0
0x180018a2c  jnz     short loc_180018A46
0x180018a2e  cmp     dword ptr [r9+4], 0
0x180018a33  jnz     short loc_180018A46
0x180018a35  cmp     dword ptr [r9+8], 0
0x180018a3a  jnz     short loc_180018A46
0x180018a3c  cmp     dword ptr [r9+0Ch], 0
0x180018a41  jnz     short loc_180018A46
0x180018a43  xor     r9d, r9d
0x180018a46  lea     rax, [rbp+57h+SRWLock]
0x180018a4a  mov     [rbp+57h+var_40], rax
0x180018a4e  mov     ecx, 4
0x180018a53  mov     [rbp+57h+var_38], rcx
0x180018a57  lea     rax, [rbp+57h+var_78]
0x180018a5b  mov     [rbp+57h+var_50], rax
0x180018a5f  mov     [rbp+57h+var_48], 8
0x180018a67  add     r8, 8
0x180018a6b  lea     rax, [rbp+57h+var_70]
0x180018a6f  mov     [rsp+0B0h+var_88], rax
0x180018a74  mov     [rsp+0B0h+var_90], ecx
0x180018a78  lea     rdx, byte_18003F7F1
0x180018a7f  mov     rcx, rbx
0x180018a82  call    _tlgWriteTransfer_EventWriteTransfer
0x180018a87  lea     rcx, [rdi+120h]; this
0x180018a8e  cmp     dword ptr [rcx+18h], 0
0x180018a92  jnz     short loc_180018A9A
0x180018a94  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180018a99  nop
0x180018a9a  mov     rcx, [rbp+57h+var_30]
0x180018a9e  xor     rcx, rsp; StackCookie
0x180018aa1  call    __security_check_cookie
0x180018aa6  add     rsp, 98h
0x180018aad  pop     r14
0x180018aaf  pop     rdi
0x180018ab0  pop     rbx
0x180018ab1  pop     rbp
0x180018ab2  retn
```
