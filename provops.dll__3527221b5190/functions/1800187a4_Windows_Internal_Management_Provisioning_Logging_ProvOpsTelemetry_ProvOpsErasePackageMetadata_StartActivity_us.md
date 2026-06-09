# Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsErasePackageMetadata::StartActivity(ushort const *,ushort const *)

- ea: `0x1800187a4`
- end: `0x18001893d`
- name: `?StartActivity@ProvOpsErasePackageMetadata@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@QEAAXPEBG0@Z`
- size: `409`
- prototype: `void __fastcall(Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsErasePackageMetadata *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180017380`

## callees

- `0x180001678`
- `0x180006f50`
- `0x180013200`
- `0x1800187a4`
- `0x180018e0c`
- `0x180033ed0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018818`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018818`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800187f7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800187f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018831`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018831`

## pseudocode

```c
void __fastcall Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsErasePackageMetadata::StartActivity(
        Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsErasePackageMetadata *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v6; // rdi
  RTL_SRWLOCK *v7; // rcx
  const struct _tlgProvider_t *v8; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v10; // r8
  const GUID *v11; // r9
  __int64 v12; // rax
  int v13; // edx
  __int64 v14; // rcx
  int v15; // ecx
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-59h] BYREF
  __int64 v17; // [rsp+38h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+40h] [rbp-49h] BYREF
  __int64 *v19; // [rsp+60h] [rbp-29h]
  __int64 v20; // [rsp+68h] [rbp-21h]
  PSRWLOCK *p_SRWLock; // [rsp+70h] [rbp-19h]
  __int64 v22; // [rsp+78h] [rbp-11h]
  const unsigned __int16 *v23; // [rsp+80h] [rbp-9h]
  int v24; // [rsp+88h] [rbp-1h]
  int v25; // [rsp+8Ch] [rbp+3h]
  const unsigned __int16 *v26; // [rsp+90h] [rbp+7h]
  int v27; // [rsp+98h] [rbp+Fh]
  int v28; // [rsp+9Ch] [rbp+13h]

  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)this,
    &SRWLock);
  v6 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider() <= 5u )
    *(_OWORD *)(v6 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v6 + 8));
  v7 = SRWLock;
  *(_DWORD *)v6 = 1;
  if ( v7 )
    ReleaseSRWLockExclusive(v7);
  v8 = Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider();
  if ( *(_DWORD *)v8 > 5u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v10 = *((_QWORD *)this + 34);
    LODWORD(SRWLock) = CurrentThreadId;
    v17 = 0;
    if ( !*(_BYTE *)(v10 + 4)
      || (v11 = (const GUID *)(v10 + 24), !*(_DWORD *)(v10 + 24))
      && !*(_DWORD *)(v10 + 28)
      && !*(_DWORD *)(v10 + 32)
      && !*(_DWORD *)(v10 + 36) )
    {
      v11 = 0;
    }
    v12 = -1;
    v13 = 2;
    if ( a3 )
    {
      v14 = -1;
      do
        ++v14;
      while ( a3[v14] );
      v15 = 2 * v14 + 2;
    }
    else
    {
      a3 = &word_18003A3A4;
      v15 = 2;
    }
    v26 = a3;
    v27 = v15;
    v28 = 0;
    if ( a2 )
    {
      do
        ++v12;
      while ( a2[v12] );
      v13 = 2 * v12 + 2;
    }
    else
    {
      a2 = &word_18003A3A4;
    }
    v24 = v13;
    p_SRWLock = &SRWLock;
    v23 = a2;
    v19 = &v17;
    v25 = 0;
    v22 = 4;
    v20 = 8;
    tlgWriteTransfer_EventWriteTransfer(
      (__int64)v8,
      (unsigned __int8 *)byte_18003F01D,
      (const GUID *)(v10 + 8),
      v11,
      6u,
      &v18);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsErasePackageMetadata *)((char *)this + 288));
}

```

## disassembly

```asm
0x1800187a4  push    rbp
0x1800187a6  push    rbx
0x1800187a7  push    rsi
0x1800187a8  push    rdi
0x1800187a9  push    r14
0x1800187ab  push    r15
0x1800187ad  lea     rbp, [rsp-2Fh]
0x1800187b2  sub     rsp, 0B8h
0x1800187b9  mov     rax, cs:__security_cookie
0x1800187c0  xor     rax, rsp
0x1800187c3  mov     [rbp+57h+var_40], rax
0x1800187c7  mov     rsi, rdx
0x1800187ca  mov     rbx, r8
0x1800187cd  lea     rdx, [rbp+57h+SRWLock]
0x1800187d1  mov     r14, rcx
0x1800187d4  call    ?LockExclusive@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800187d9  mov     rdi, [r14+110h]
0x1800187e0  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x1800187e5  mov     r9d, [rax]
0x1800187e8  cmp     r9d, 5
0x1800187ec  jbe     short loc_1800187FF
0x1800187ee  lea     rdx, [rdi+8]; ActivityId
0x1800187f2  mov     ecx, 3; ControlCode
0x1800187f7  call    cs:__imp_EventActivityIdControl
0x1800187fd  jmp     short loc_180018806
0x1800187ff  xorps   xmm0, xmm0
0x180018802  movups  xmmword ptr [rdi+8], xmm0
0x180018806  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001880a  xor     r15d, r15d
0x18001880d  mov     dword ptr [rdi], 1
0x180018813  test    rcx, rcx
0x180018816  jz      short loc_18001881E
0x180018818  call    cs:__imp_ReleaseSRWLockExclusive
0x18001881e  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x180018823  mov     rdi, rax
0x180018826  mov     ecx, [rax]
0x180018828  cmp     ecx, 5
0x18001882b  jbe     loc_18001890F
0x180018831  call    cs:__imp_GetCurrentThreadId
0x180018837  mov     r8, [r14+110h]
0x18001883e  mov     dword ptr [rbp+57h+SRWLock], eax
0x180018841  mov     [rbp+57h+var_A8], r15
0x180018845  cmp     [r8+4], r15b
0x180018849  jz      short loc_180018866
0x18001884b  lea     r9, [r8+18h]
0x18001884f  cmp     [r9], r15d
0x180018852  jnz     short loc_180018869
0x180018854  cmp     [r9+4], r15d
0x180018858  jnz     short loc_180018869
0x18001885a  cmp     [r9+8], r15d
0x18001885e  jnz     short loc_180018869
0x180018860  cmp     [r9+0Ch], r15d
0x180018864  jnz     short loc_180018869
0x180018866  mov     r9, r15
0x180018869  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001886d  mov     edx, 2
0x180018872  test    rbx, rbx
0x180018875  jz      short loc_18001888D
0x180018877  mov     rcx, rax
0x18001887a  inc     rcx
0x18001887d  cmp     [rbx+rcx*2], r15w
0x180018882  jnz     short loc_18001887A
0x180018884  lea     ecx, ds:2[rcx*2]
0x18001888b  jmp     short loc_180018896
0x18001888d  lea     rbx, word_18003A3A4
0x180018894  mov     ecx, edx
0x180018896  mov     [rbp+57h+var_50], rbx
0x18001889a  mov     [rbp+57h+var_48], ecx
0x18001889d  mov     [rbp+57h+var_44], r15d
0x1800188a1  test    rsi, rsi
0x1800188a4  jz      short loc_1800188B9
0x1800188a6  inc     rax
0x1800188a9  cmp     [rsi+rax*2], r15w
0x1800188ae  jnz     short loc_1800188A6
0x1800188b0  lea     edx, ds:2[rax*2]
0x1800188b7  jmp     short loc_1800188C0
0x1800188b9  lea     rsi, word_18003A3A4
0x1800188c0  lea     rax, [rbp+57h+SRWLock]
0x1800188c4  mov     [rbp+57h+var_58], edx
0x1800188c7  mov     [rbp+57h+var_70], rax
0x1800188cb  lea     rdx, byte_18003F01D
0x1800188d2  lea     rax, [rbp+57h+var_A8]
0x1800188d6  mov     [rbp+57h+var_60], rsi
0x1800188da  mov     [rbp+57h+var_80], rax
0x1800188de  add     r8, 8
0x1800188e2  lea     rax, [rbp+57h+var_A0]
0x1800188e6  mov     [rbp+57h+var_54], r15d
0x1800188ea  mov     [rsp+0E0h+var_B8], rax
0x1800188ef  mov     rcx, rdi
0x1800188f2  mov     [rsp+0E0h+var_C0], 6
0x1800188fa  mov     [rbp+57h+var_68], 4
0x180018902  mov     [rbp+57h+var_78], 8
0x18001890a  call    _tlgWriteTransfer_EventWriteTransfer
0x18001890f  lea     rcx, [r14+120h]; this
0x180018916  cmp     [rcx+18h], r15d
0x18001891a  jnz     short loc_180018921
0x18001891c  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180018921  mov     rcx, [rbp+57h+var_40]
0x180018925  xor     rcx, rsp; StackCookie
0x180018928  call    __security_check_cookie
0x18001892d  add     rsp, 0B8h
0x180018934  pop     r15
0x180018936  pop     r14
0x180018938  pop     rdi
0x180018939  pop     rsi
0x18001893a  pop     rbx
0x18001893b  pop     rbp
0x18001893c  retn
```
