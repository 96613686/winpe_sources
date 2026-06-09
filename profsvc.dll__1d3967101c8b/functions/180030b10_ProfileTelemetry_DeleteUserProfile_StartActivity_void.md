# ProfileTelemetry::DeleteUserProfile::StartActivity(void)

- ea: `0x180030b10`
- end: `0x180030c1b`
- name: `?StartActivity@DeleteUserProfile@ProfileTelemetry@@QEAAXXZ`
- size: `267`
- prototype: `void __fastcall(ProfileTelemetry::DeleteUserProfile *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180030624`

## callees

- `0x1800121d0`
- `0x180013a80`
- `0x180022204`
- `0x180024208`
- `0x180027dd8`
- `0x180030b10`
- `0x18003695c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180030b78`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180030b78`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030ba3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030ba3`
- `ntdll!EtwEventActivityIdControl` at `0x180030b59`
- `ntdll!EtwEventActivityIdControl` at `0x180030b59`

## pseudocode

```c
void __fastcall ProfileTelemetry::DeleteUserProfile::StartActivity(ProfileTelemetry::DeleteUserProfile *this)
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

  wil::ActivityBase<ProfileLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &SRWLock);
  v2 = *((_QWORD *)this + 34);
  v3 = ProfileLogging::Provider();
  if ( *(_DWORD *)v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x400000000000LL, v4, v5) )
    EtwEventActivityIdControl(3, v2 + 8);
  else
    *(_OWORD *)(v2 + 8) = 0;
  *(_DWORD *)v2 = 1;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v6 = ProfileLogging::Provider();
  v9 = (__int64)v6;
  if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x400000000000LL, v7, v8) )
  {
    LODWORD(SRWLock) = GetCurrentThreadId();
    v13 = 0x1000000;
    v10 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v10 + 4) || _tlgGuidIsZero((const struct _GUID *)(v10 + 24)) )
      v11 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v9,
      (unsigned __int8 *)&unk_18006DBE0,
      v10 + 8,
      v11,
      (__int64)&v13,
      (__int64)&SRWLock);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((ProfileTelemetry::DeleteUserProfile *)((char *)this + 288));
}

```

## disassembly

```asm
0x180030b10  mov     [rsp+arg_10], rbx
0x180030b15  push    rdi
0x180030b16  sub     rsp, 30h
0x180030b1a  mov     rdi, rcx
0x180030b1d  lea     rdx, [rsp+38h+SRWLock]
0x180030b22  call    ?LockExclusive@?$ActivityBase@VProfileLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ProfileLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180030b27  mov     rbx, [rdi+110h]
0x180030b2e  call    ?Provider@ProfileLogging@@SAPEBU_tlgProvider_t@@XZ; ProfileLogging::Provider(void)
0x180030b33  mov     edx, [rax]
0x180030b35  cmp     edx, 5
0x180030b38  jbe     short loc_180030B61
0x180030b3a  mov     rdx, 400000000000h
0x180030b44  mov     rcx, rax
0x180030b47  call    _tlgKeywordOn
0x180030b4c  test    al, al
0x180030b4e  jz      short loc_180030B61
0x180030b50  lea     rdx, [rbx+8]
0x180030b54  mov     ecx, 3
0x180030b59  call    cs:__imp_EtwEventActivityIdControl
0x180030b5f  jmp     short loc_180030B68
0x180030b61  xorps   xmm0, xmm0
0x180030b64  movups  xmmword ptr [rbx+8], xmm0
0x180030b68  mov     dword ptr [rbx], 1
0x180030b6e  mov     rcx, [rsp+38h+SRWLock]; SRWLock
0x180030b73  test    rcx, rcx
0x180030b76  jz      short loc_180030B7E
0x180030b78  call    cs:__imp_ReleaseSRWLockExclusive
0x180030b7e  call    ?Provider@ProfileLogging@@SAPEBU_tlgProvider_t@@XZ; ProfileLogging::Provider(void)
0x180030b83  mov     rbx, rax
0x180030b86  mov     ecx, [rax]
0x180030b88  cmp     ecx, 5
0x180030b8b  jbe     short loc_180030BFD
0x180030b8d  mov     rdx, 400000000000h
0x180030b97  mov     rcx, rax
0x180030b9a  call    _tlgKeywordOn
0x180030b9f  test    al, al
0x180030ba1  jz      short loc_180030BFD
0x180030ba3  call    cs:__imp_GetCurrentThreadId
0x180030ba9  mov     dword ptr [rsp+38h+SRWLock], eax
0x180030bad  mov     [rsp+38h+arg_8], 1000000h
0x180030bb6  mov     r8, [rdi+110h]
0x180030bbd  cmp     byte ptr [r8+4], 0
0x180030bc2  jz      short loc_180030BD1
0x180030bc4  lea     rcx, [r8+18h]; struct _GUID *
0x180030bc8  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180030bcd  test    al, al
0x180030bcf  jz      short loc_180030BD3
0x180030bd1  xor     ecx, ecx
0x180030bd3  add     r8, 8
0x180030bd7  lea     rax, [rsp+38h+SRWLock]
0x180030bdc  mov     [rsp+38h+var_10], rax
0x180030be1  lea     rax, [rsp+38h+arg_8]
0x180030be6  mov     [rsp+38h+var_18], rax
0x180030beb  mov     r9, rcx
0x180030bee  lea     rdx, unk_18006DBE0
0x180030bf5  mov     rcx, rbx
0x180030bf8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180030bfd  lea     rcx, [rdi+120h]; this
0x180030c04  cmp     dword ptr [rcx+18h], 0
0x180030c08  jnz     short loc_180030C10
0x180030c0a  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180030c0f  nop
0x180030c10  mov     rbx, [rsp+38h+arg_10]
0x180030c15  add     rsp, 30h
0x180030c19  pop     rdi
0x180030c1a  retn
```
