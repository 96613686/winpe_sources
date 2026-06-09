# Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsAddPkg::StartActivity(void)

- ea: `0x18001833c`
- end: `0x1800184ab`
- name: `?StartActivity@ProvOpsAddPkg@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@QEAAXXZ`
- size: `367`
- prototype: `void __fastcall(Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsAddPkg *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000f8d0`

## callees

- `0x180001678`
- `0x180006f50`
- `0x180013200`
- `0x18001833c`
- `0x180018e0c`
- `0x180033ed0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800183c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800183c4`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800183a6`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800183a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800183fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800183fd`

## pseudocode

```c
void __fastcall Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsAddPkg::StartActivity(
        Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsAddPkg *this)
{
  __int64 v2; // rbx
  const struct _tlgProvider_t *v3; // rax
  const struct _tlgProvider_t *v4; // rax
  const struct _tlgProvider_t *v5; // rbx
  __int64 v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-29h] BYREF
  _QWORD v10[9]; // [rsp+38h] [rbp-21h] BYREF

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
  v5 = v4;
  if ( *(_DWORD *)v4 > 5u )
  {
    v6 = *((_QWORD *)v4 + 3);
    if ( (*((_QWORD *)v5 + 2) & 0x400000000000LL) != 0 && (v6 & 0x400000000000LL) == v6 )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v10[0] = 0;
      v7 = *((_QWORD *)this + 34);
      if ( !*(_BYTE *)(v7 + 4)
        || (v8 = v7 + 24, !*(_DWORD *)(v7 + 24))
        && !*(_DWORD *)(v7 + 28)
        && !*(_DWORD *)(v7 + 32)
        && !*(_DWORD *)(v7 + 36) )
      {
        v8 = 0;
      }
      v10[7] = &SRWLock;
      v10[8] = 4;
      v10[5] = v10;
      v10[6] = 8;
      tlgWriteTransfer_EventWriteTransfer(v5, qword_18003EFD8, v7 + 8, v8);
    }
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsAddPkg *)((char *)this + 288));
}

```

## disassembly

```asm
0x18001833c  push    rbp
0x18001833e  push    rbx
0x18001833f  push    rdi
0x180018340  push    r14
0x180018342  lea     rbp, [rsp-3Fh]
0x180018347  sub     rsp, 98h
0x18001834e  mov     rax, cs:__security_cookie
0x180018355  xor     rax, rsp
0x180018358  mov     [rbp+57h+var_30], rax
0x18001835c  mov     rdi, rcx
0x18001835f  lea     rdx, [rbp+57h+SRWLock]
0x180018363  call    ?LockExclusive@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180018368  mov     rbx, [rdi+110h]
0x18001836f  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x180018374  mov     edx, [rax]
0x180018376  mov     r14, 400000000000h
0x180018380  cmp     edx, 5
0x180018383  jbe     short loc_1800183AE
0x180018385  mov     rcx, [rax+18h]
0x180018389  mov     rax, [rax+10h]
0x18001838d  test    r14, rax
0x180018390  jz      short loc_1800183AE
0x180018392  mov     rax, rcx
0x180018395  and     rax, r14
0x180018398  cmp     rax, rcx
0x18001839b  jnz     short loc_1800183AE
0x18001839d  lea     rdx, [rbx+8]; ActivityId
0x1800183a1  mov     ecx, 3; ControlCode
0x1800183a6  call    cs:__imp_EventActivityIdControl
0x1800183ac  jmp     short loc_1800183B5
0x1800183ae  xorps   xmm0, xmm0
0x1800183b1  movups  xmmword ptr [rbx+8], xmm0
0x1800183b5  mov     dword ptr [rbx], 1
0x1800183bb  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800183bf  test    rcx, rcx
0x1800183c2  jz      short loc_1800183CA
0x1800183c4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800183ca  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x1800183cf  mov     rbx, rax
0x1800183d2  mov     ecx, [rax]
0x1800183d4  cmp     ecx, 5
0x1800183d7  jbe     loc_18001847F
0x1800183dd  mov     rax, [rax+18h]
0x1800183e1  mov     rcx, [rbx+10h]
0x1800183e5  test    r14, rcx
0x1800183e8  jz      loc_18001847F
0x1800183ee  mov     rcx, rax
0x1800183f1  and     rcx, r14
0x1800183f4  cmp     rcx, rax
0x1800183f7  jnz     loc_18001847F
0x1800183fd  call    cs:__imp_GetCurrentThreadId
0x180018403  mov     dword ptr [rbp+57h+SRWLock], eax
0x180018406  mov     [rbp+57h+var_78], 0
0x18001840e  mov     r8, [rdi+110h]
0x180018415  cmp     byte ptr [r8+4], 0
0x18001841a  jz      short loc_18001843B
0x18001841c  lea     r9, [r8+18h]
0x180018420  cmp     dword ptr [r9], 0
0x180018424  jnz     short loc_18001843E
0x180018426  cmp     dword ptr [r9+4], 0
0x18001842b  jnz     short loc_18001843E
0x18001842d  cmp     dword ptr [r9+8], 0
0x180018432  jnz     short loc_18001843E
0x180018434  cmp     dword ptr [r9+0Ch], 0
0x180018439  jnz     short loc_18001843E
0x18001843b  xor     r9d, r9d
0x18001843e  lea     rax, [rbp+57h+SRWLock]
0x180018442  mov     [rbp+57h+var_40], rax
0x180018446  mov     ecx, 4
0x18001844b  mov     [rbp+57h+var_38], rcx
0x18001844f  lea     rax, [rbp+57h+var_78]
0x180018453  mov     [rbp+57h+var_50], rax
0x180018457  mov     [rbp+57h+var_48], 8
0x18001845f  add     r8, 8
0x180018463  lea     rax, [rbp+57h+var_70]
0x180018467  mov     [rsp+0B0h+var_88], rax
0x18001846c  mov     [rsp+0B0h+var_90], ecx
0x180018470  lea     rdx, qword_18003EFD8
0x180018477  mov     rcx, rbx
0x18001847a  call    _tlgWriteTransfer_EventWriteTransfer
0x18001847f  lea     rcx, [rdi+120h]; this
0x180018486  cmp     dword ptr [rcx+18h], 0
0x18001848a  jnz     short loc_180018492
0x18001848c  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180018491  nop
0x180018492  mov     rcx, [rbp+57h+var_30]
0x180018496  xor     rcx, rsp; StackCookie
0x180018499  call    __security_check_cookie
0x18001849e  add     rsp, 98h
0x1800184a5  pop     r14
0x1800184a7  pop     rdi
0x1800184a8  pop     rbx
0x1800184a9  pop     rbp
0x1800184aa  retn
```
