# Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::CreateProvisioningSession::StartActivity(void)

- ea: `0x1800180ac`
- end: `0x1800181eb`
- name: `?StartActivity@CreateProvisioningSession@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@QEAAXXZ`
- size: `319`
- prototype: `void __fastcall(Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::CreateProvisioningSession *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180011de4`

## callees

- `0x180001678`
- `0x180006f50`
- `0x180013200`
- `0x1800180ac`
- `0x180018e0c`
- `0x180033ed0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018119`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018119`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800180fb`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800180fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018132`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018132`

## pseudocode

```c
void __fastcall Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::CreateProvisioningSession::StartActivity(
        Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::CreateProvisioningSession *this)
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
    tlgWriteTransfer_EventWriteTransfer(v3, &unk_18003EE38, v4 + 8, v5);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::CreateProvisioningSession *)((char *)this + 288));
}

```

## disassembly

```asm
0x1800180ac  mov     [rsp-8+arg_8], rbx
0x1800180b1  mov     [rsp-8+arg_10], rdi
0x1800180b6  push    rbp
0x1800180b7  lea     rbp, [rsp-57h]
0x1800180bc  sub     rsp, 90h
0x1800180c3  mov     rax, cs:__security_cookie
0x1800180ca  xor     rax, rsp
0x1800180cd  mov     [rbp+57h+var_10], rax
0x1800180d1  mov     rbx, rcx
0x1800180d4  lea     rdx, [rbp+57h+SRWLock]
0x1800180d8  call    ?LockExclusive@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800180dd  mov     rdi, [rbx+110h]
0x1800180e4  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x1800180e9  mov     r8d, [rax]
0x1800180ec  cmp     r8d, 4
0x1800180f0  jbe     short loc_180018103
0x1800180f2  lea     rdx, [rdi+8]; ActivityId
0x1800180f6  mov     ecx, 3; ControlCode
0x1800180fb  call    cs:__imp_EventActivityIdControl
0x180018101  jmp     short loc_18001810A
0x180018103  xorps   xmm0, xmm0
0x180018106  movups  xmmword ptr [rdi+8], xmm0
0x18001810a  mov     dword ptr [rdi], 1
0x180018110  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180018114  test    rcx, rcx
0x180018117  jz      short loc_18001811F
0x180018119  call    cs:__imp_ReleaseSRWLockExclusive
0x18001811f  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x180018124  mov     rdi, rax
0x180018127  mov     ecx, [rax]
0x180018129  cmp     ecx, 4
0x18001812c  jbe     loc_1800181B7
0x180018132  call    cs:__imp_GetCurrentThreadId
0x180018138  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001813b  mov     [rbp+57h+var_58], 0
0x180018143  mov     r8, [rbx+110h]
0x18001814a  cmp     byte ptr [r8+4], 0
0x18001814f  jz      short loc_180018170
0x180018151  lea     r9, [r8+18h]
0x180018155  cmp     dword ptr [r9], 0
0x180018159  jnz     short loc_180018173
0x18001815b  cmp     dword ptr [r9+4], 0
0x180018160  jnz     short loc_180018173
0x180018162  cmp     dword ptr [r9+8], 0
0x180018167  jnz     short loc_180018173
0x180018169  cmp     dword ptr [r9+0Ch], 0
0x18001816e  jnz     short loc_180018173
0x180018170  xor     r9d, r9d
0x180018173  lea     rax, [rbp+57h+SRWLock]
0x180018177  mov     [rbp+57h+var_20], rax
0x18001817b  mov     [rbp+57h+var_18], 4
0x180018183  lea     rax, [rbp+57h+var_58]
0x180018187  mov     [rbp+57h+var_30], rax
0x18001818b  mov     [rbp+57h+var_28], 8
0x180018193  add     r8, 8
0x180018197  lea     rax, [rbp+57h+var_50]
0x18001819b  mov     [rsp+90h+var_68], rax
0x1800181a0  mov     [rsp+90h+var_70], 4
0x1800181a8  lea     rdx, unk_18003EE38
0x1800181af  mov     rcx, rdi
0x1800181b2  call    _tlgWriteTransfer_EventWriteTransfer
0x1800181b7  lea     rcx, [rbx+120h]; this
0x1800181be  cmp     dword ptr [rcx+18h], 0
0x1800181c2  jnz     short loc_1800181CA
0x1800181c4  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1800181c9  nop
0x1800181ca  mov     rcx, [rbp+57h+var_10]
0x1800181ce  xor     rcx, rsp; StackCookie
0x1800181d1  call    __security_check_cookie
0x1800181d6  lea     r11, [rsp+90h+var_s0]
0x1800181de  mov     rbx, [r11+18h]
0x1800181e2  mov     rdi, [r11+20h]
0x1800181e6  mov     rsp, r11
0x1800181e9  pop     rbp
0x1800181ea  retn
```
