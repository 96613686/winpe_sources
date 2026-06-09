# Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsCleanupOOBEProvisioningLogs::StartActivity(void)

- ea: `0x18001862c`
- end: `0x18001879b`
- name: `?StartActivity@ProvOpsCleanupOOBEProvisioningLogs@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@QEAAXXZ`
- size: `367`
- prototype: `void __fastcall(Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsCleanupOOBEProvisioningLogs *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180011b88`

## callees

- `0x180001678`
- `0x180006f50`
- `0x180013200`
- `0x18001862c`
- `0x180018e0c`
- `0x180033ed0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800186b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800186b4`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180018696`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180018696`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800186ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800186ed`

## pseudocode

```c
void __fastcall Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsCleanupOOBEProvisioningLogs::StartActivity(
        Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsCleanupOOBEProvisioningLogs *this)
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
      tlgWriteTransfer_EventWriteTransfer(v5, (unsigned __int8 *)byte_180040C21, (const GUID *)(v7 + 8), v8, 4u, &v11);
    }
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsCleanupOOBEProvisioningLogs *)((char *)this + 288));
}

```

## disassembly

```asm
0x18001862c  push    rbp
0x18001862e  push    rbx
0x18001862f  push    rdi
0x180018630  push    r14
0x180018632  lea     rbp, [rsp-3Fh]
0x180018637  sub     rsp, 98h
0x18001863e  mov     rax, cs:__security_cookie
0x180018645  xor     rax, rsp
0x180018648  mov     [rbp+57h+var_30], rax
0x18001864c  mov     rdi, rcx
0x18001864f  lea     rdx, [rbp+57h+SRWLock]
0x180018653  call    ?LockExclusive@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180018658  mov     rbx, [rdi+110h]
0x18001865f  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x180018664  mov     edx, [rax]
0x180018666  mov     r14, 400000000000h
0x180018670  cmp     edx, 5
0x180018673  jbe     short loc_18001869E
0x180018675  mov     rcx, [rax+18h]
0x180018679  mov     rax, [rax+10h]
0x18001867d  test    r14, rax
0x180018680  jz      short loc_18001869E
0x180018682  mov     rax, rcx
0x180018685  and     rax, r14
0x180018688  cmp     rax, rcx
0x18001868b  jnz     short loc_18001869E
0x18001868d  lea     rdx, [rbx+8]; ActivityId
0x180018691  mov     ecx, 3; ControlCode
0x180018696  call    cs:__imp_EventActivityIdControl
0x18001869c  jmp     short loc_1800186A5
0x18001869e  xorps   xmm0, xmm0
0x1800186a1  movups  xmmword ptr [rbx+8], xmm0
0x1800186a5  mov     dword ptr [rbx], 1
0x1800186ab  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800186af  test    rcx, rcx
0x1800186b2  jz      short loc_1800186BA
0x1800186b4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800186ba  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x1800186bf  mov     rbx, rax
0x1800186c2  mov     ecx, [rax]
0x1800186c4  cmp     ecx, 5
0x1800186c7  jbe     loc_18001876F
0x1800186cd  mov     rax, [rax+18h]
0x1800186d1  mov     rcx, [rbx+10h]
0x1800186d5  test    r14, rcx
0x1800186d8  jz      loc_18001876F
0x1800186de  mov     rcx, rax
0x1800186e1  and     rcx, r14
0x1800186e4  cmp     rcx, rax
0x1800186e7  jnz     loc_18001876F
0x1800186ed  call    cs:__imp_GetCurrentThreadId
0x1800186f3  mov     dword ptr [rbp+57h+SRWLock], eax
0x1800186f6  mov     [rbp+57h+var_78], 1000000h
0x1800186fe  mov     r8, [rdi+110h]
0x180018705  cmp     byte ptr [r8+4], 0
0x18001870a  jz      short loc_18001872B
0x18001870c  lea     r9, [r8+18h]
0x180018710  cmp     dword ptr [r9], 0
0x180018714  jnz     short loc_18001872E
0x180018716  cmp     dword ptr [r9+4], 0
0x18001871b  jnz     short loc_18001872E
0x18001871d  cmp     dword ptr [r9+8], 0
0x180018722  jnz     short loc_18001872E
0x180018724  cmp     dword ptr [r9+0Ch], 0
0x180018729  jnz     short loc_18001872E
0x18001872b  xor     r9d, r9d
0x18001872e  lea     rax, [rbp+57h+SRWLock]
0x180018732  mov     [rbp+57h+var_40], rax
0x180018736  mov     ecx, 4
0x18001873b  mov     [rbp+57h+var_38], rcx
0x18001873f  lea     rax, [rbp+57h+var_78]
0x180018743  mov     [rbp+57h+var_50], rax
0x180018747  mov     [rbp+57h+var_48], 8
0x18001874f  add     r8, 8
0x180018753  lea     rax, [rbp+57h+var_70]
0x180018757  mov     [rsp+0B0h+var_88], rax
0x18001875c  mov     [rsp+0B0h+var_90], ecx
0x180018760  lea     rdx, byte_180040C21
0x180018767  mov     rcx, rbx
0x18001876a  call    _tlgWriteTransfer_EventWriteTransfer
0x18001876f  lea     rcx, [rdi+120h]; this
0x180018776  cmp     dword ptr [rcx+18h], 0
0x18001877a  jnz     short loc_180018782
0x18001877c  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180018781  nop
0x180018782  mov     rcx, [rbp+57h+var_30]
0x180018786  xor     rcx, rsp; StackCookie
0x180018789  call    __security_check_cookie
0x18001878e  add     rsp, 98h
0x180018795  pop     r14
0x180018797  pop     rdi
0x180018798  pop     rbx
0x180018799  pop     rbp
0x18001879a  retn
```
