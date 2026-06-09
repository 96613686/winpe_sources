# ProfileTelemetry::IssueTempProfile::StartActivity(void)

- ea: `0x1800336c8`
- end: `0x1800337d3`
- name: `?StartActivity@IssueTempProfile@ProfileTelemetry@@QEAAXXZ`
- size: `267`
- prototype: `void __fastcall(ProfileTelemetry::IssueTempProfile *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180032ce0`

## callees

- `0x1800121d0`
- `0x180013a80`
- `0x180021ea0`
- `0x180022204`
- `0x180027dd8`
- `0x1800336c8`
- `0x18003695c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033730`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033730`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003375b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003375b`
- `ntdll!EtwEventActivityIdControl` at `0x180033711`
- `ntdll!EtwEventActivityIdControl` at `0x180033711`

## pseudocode

```c
void __fastcall ProfileTelemetry::IssueTempProfile::StartActivity(ProfileTelemetry::IssueTempProfile *this)
{
  __int64 v2; // rbx
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // r8
  __int64 v5; // r9
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rbx
  __int64 v10; // r8
  __int64 v11; // rcx
  PSRWLOCK SRWLock; // [rsp+40h] [rbp+8h] BYREF
  __int64 v13; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<ProfileLogging,1,70368744177664,1,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &SRWLock);
  v2 = *((_QWORD *)this + 34);
  v3 = ProfileLogging::Provider();
  if ( *(_DWORD *)v3 > 1u && (unsigned __int8)tlgKeywordOn(v3, 0x400000000000LL, v4, v5) )
    EtwEventActivityIdControl(3, v2 + 8);
  else
    *(_OWORD *)(v2 + 8) = 0;
  *(_DWORD *)v2 = 1;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v6 = ProfileLogging::Provider();
  v9 = (__int64)v6;
  if ( *(_DWORD *)v6 > 1u && (unsigned __int8)tlgKeywordOn(v6, 0x400000000000LL, v7, v8) )
  {
    LODWORD(SRWLock) = GetCurrentThreadId();
    v13 = 0x1000000;
    v10 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v10 + 4) || _tlgGuidIsZero((const struct _GUID *)(v10 + 24)) )
      v11 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v9,
      (unsigned __int8 *)&word_18007067E,
      v10 + 8,
      v11,
      (__int64)&v13,
      (__int64)&SRWLock);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((ProfileTelemetry::IssueTempProfile *)((char *)this + 288));
}

```

## disassembly

```asm
0x1800336c8  mov     [rsp+arg_10], rbx
0x1800336cd  push    rdi
0x1800336ce  sub     rsp, 30h
0x1800336d2  mov     rdi, rcx
0x1800336d5  lea     rdx, [rsp+38h+SRWLock]
0x1800336da  call    ?LockExclusive@?$ActivityBase@VProfileLogging@@$00$0EAAAAAAAAAAA@$00$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ProfileLogging,1,70368744177664,1,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800336df  mov     rbx, [rdi+110h]
0x1800336e6  call    ?Provider@ProfileLogging@@SAPEBU_tlgProvider_t@@XZ; ProfileLogging::Provider(void)
0x1800336eb  mov     edx, [rax]
0x1800336ed  cmp     edx, 1
0x1800336f0  jbe     short loc_180033719
0x1800336f2  mov     rdx, 400000000000h
0x1800336fc  mov     rcx, rax
0x1800336ff  call    _tlgKeywordOn
0x180033704  test    al, al
0x180033706  jz      short loc_180033719
0x180033708  lea     rdx, [rbx+8]
0x18003370c  mov     ecx, 3
0x180033711  call    cs:__imp_EtwEventActivityIdControl
0x180033717  jmp     short loc_180033720
0x180033719  xorps   xmm0, xmm0
0x18003371c  movups  xmmword ptr [rbx+8], xmm0
0x180033720  mov     dword ptr [rbx], 1
0x180033726  mov     rcx, [rsp+38h+SRWLock]; SRWLock
0x18003372b  test    rcx, rcx
0x18003372e  jz      short loc_180033736
0x180033730  call    cs:__imp_ReleaseSRWLockExclusive
0x180033736  call    ?Provider@ProfileLogging@@SAPEBU_tlgProvider_t@@XZ; ProfileLogging::Provider(void)
0x18003373b  mov     rbx, rax
0x18003373e  mov     ecx, [rax]
0x180033740  cmp     ecx, 1
0x180033743  jbe     short loc_1800337B5
0x180033745  mov     rdx, 400000000000h
0x18003374f  mov     rcx, rax
0x180033752  call    _tlgKeywordOn
0x180033757  test    al, al
0x180033759  jz      short loc_1800337B5
0x18003375b  call    cs:__imp_GetCurrentThreadId
0x180033761  mov     dword ptr [rsp+38h+SRWLock], eax
0x180033765  mov     [rsp+38h+arg_8], 1000000h
0x18003376e  mov     r8, [rdi+110h]
0x180033775  cmp     byte ptr [r8+4], 0
0x18003377a  jz      short loc_180033789
0x18003377c  lea     rcx, [r8+18h]; struct _GUID *
0x180033780  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180033785  test    al, al
0x180033787  jz      short loc_18003378B
0x180033789  xor     ecx, ecx
0x18003378b  add     r8, 8
0x18003378f  lea     rax, [rsp+38h+SRWLock]
0x180033794  mov     [rsp+38h+var_10], rax
0x180033799  lea     rax, [rsp+38h+arg_8]
0x18003379e  mov     [rsp+38h+var_18], rax
0x1800337a3  mov     r9, rcx
0x1800337a6  lea     rdx, word_18007067E
0x1800337ad  mov     rcx, rbx
0x1800337b0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800337b5  lea     rcx, [rdi+120h]; this
0x1800337bc  cmp     dword ptr [rcx+18h], 0
0x1800337c0  jnz     short loc_1800337C8
0x1800337c2  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1800337c7  nop
0x1800337c8  mov     rbx, [rsp+38h+arg_10]
0x1800337cd  add     rsp, 30h
0x1800337d1  pop     rdi
0x1800337d2  retn
```
