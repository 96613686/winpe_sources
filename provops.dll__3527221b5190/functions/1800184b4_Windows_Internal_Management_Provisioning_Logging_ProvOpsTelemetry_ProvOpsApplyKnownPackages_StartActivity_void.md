# Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsApplyKnownPackages::StartActivity(void)

- ea: `0x1800184b4`
- end: `0x180018623`
- name: `?StartActivity@ProvOpsApplyKnownPackages@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@QEAAXXZ`
- size: `367`
- prototype: `void __fastcall(Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsApplyKnownPackages *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180010b40`

## callees

- `0x180001678`
- `0x180006f50`
- `0x180013200`
- `0x1800184b4`
- `0x180018e0c`
- `0x180033ed0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001853c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001853c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001851e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001851e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018575`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018575`

## pseudocode

```c
void __fastcall Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsApplyKnownPackages::StartActivity(
        Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsApplyKnownPackages *this)
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
      v10 = 0;
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
      tlgWriteTransfer_EventWriteTransfer(v5, (unsigned __int8 *)&word_1800405D6, (const GUID *)(v7 + 8), v8, 4u, &v11);
    }
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsApplyKnownPackages *)((char *)this + 288));
}

```

## disassembly

```asm
0x1800184b4  push    rbp
0x1800184b6  push    rbx
0x1800184b7  push    rdi
0x1800184b8  push    r14
0x1800184ba  lea     rbp, [rsp-3Fh]
0x1800184bf  sub     rsp, 98h
0x1800184c6  mov     rax, cs:__security_cookie
0x1800184cd  xor     rax, rsp
0x1800184d0  mov     [rbp+57h+var_30], rax
0x1800184d4  mov     rdi, rcx
0x1800184d7  lea     rdx, [rbp+57h+SRWLock]
0x1800184db  call    ?LockExclusive@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800184e0  mov     rbx, [rdi+110h]
0x1800184e7  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x1800184ec  mov     edx, [rax]
0x1800184ee  mov     r14, 400000000000h
0x1800184f8  cmp     edx, 5
0x1800184fb  jbe     short loc_180018526
0x1800184fd  mov     rcx, [rax+18h]
0x180018501  mov     rax, [rax+10h]
0x180018505  test    r14, rax
0x180018508  jz      short loc_180018526
0x18001850a  mov     rax, rcx
0x18001850d  and     rax, r14
0x180018510  cmp     rax, rcx
0x180018513  jnz     short loc_180018526
0x180018515  lea     rdx, [rbx+8]; ActivityId
0x180018519  mov     ecx, 3; ControlCode
0x18001851e  call    cs:__imp_EventActivityIdControl
0x180018524  jmp     short loc_18001852D
0x180018526  xorps   xmm0, xmm0
0x180018529  movups  xmmword ptr [rbx+8], xmm0
0x18001852d  mov     dword ptr [rbx], 1
0x180018533  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180018537  test    rcx, rcx
0x18001853a  jz      short loc_180018542
0x18001853c  call    cs:__imp_ReleaseSRWLockExclusive
0x180018542  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x180018547  mov     rbx, rax
0x18001854a  mov     ecx, [rax]
0x18001854c  cmp     ecx, 5
0x18001854f  jbe     loc_1800185F7
0x180018555  mov     rax, [rax+18h]
0x180018559  mov     rcx, [rbx+10h]
0x18001855d  test    r14, rcx
0x180018560  jz      loc_1800185F7
0x180018566  mov     rcx, rax
0x180018569  and     rcx, r14
0x18001856c  cmp     rcx, rax
0x18001856f  jnz     loc_1800185F7
0x180018575  call    cs:__imp_GetCurrentThreadId
0x18001857b  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001857e  mov     [rbp+57h+var_78], 0
0x180018586  mov     r8, [rdi+110h]
0x18001858d  cmp     byte ptr [r8+4], 0
0x180018592  jz      short loc_1800185B3
0x180018594  lea     r9, [r8+18h]
0x180018598  cmp     dword ptr [r9], 0
0x18001859c  jnz     short loc_1800185B6
0x18001859e  cmp     dword ptr [r9+4], 0
0x1800185a3  jnz     short loc_1800185B6
0x1800185a5  cmp     dword ptr [r9+8], 0
0x1800185aa  jnz     short loc_1800185B6
0x1800185ac  cmp     dword ptr [r9+0Ch], 0
0x1800185b1  jnz     short loc_1800185B6
0x1800185b3  xor     r9d, r9d
0x1800185b6  lea     rax, [rbp+57h+SRWLock]
0x1800185ba  mov     [rbp+57h+var_40], rax
0x1800185be  mov     ecx, 4
0x1800185c3  mov     [rbp+57h+var_38], rcx
0x1800185c7  lea     rax, [rbp+57h+var_78]
0x1800185cb  mov     [rbp+57h+var_50], rax
0x1800185cf  mov     [rbp+57h+var_48], 8
0x1800185d7  add     r8, 8
0x1800185db  lea     rax, [rbp+57h+var_70]
0x1800185df  mov     [rsp+0B0h+var_88], rax
0x1800185e4  mov     [rsp+0B0h+var_90], ecx
0x1800185e8  lea     rdx, word_1800405D6
0x1800185ef  mov     rcx, rbx
0x1800185f2  call    _tlgWriteTransfer_EventWriteTransfer
0x1800185f7  lea     rcx, [rdi+120h]; this
0x1800185fe  cmp     dword ptr [rcx+18h], 0
0x180018602  jnz     short loc_18001860A
0x180018604  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180018609  nop
0x18001860a  mov     rcx, [rbp+57h+var_30]
0x18001860e  xor     rcx, rsp; StackCookie
0x180018611  call    __security_check_cookie
0x180018616  add     rsp, 98h
0x18001861d  pop     r14
0x18001861f  pop     rdi
0x180018620  pop     rbx
0x180018621  pop     rbp
0x180018622  retn
```
