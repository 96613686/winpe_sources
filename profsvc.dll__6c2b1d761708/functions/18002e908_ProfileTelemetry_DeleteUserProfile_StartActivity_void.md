# ProfileTelemetry::DeleteUserProfile::StartActivity(void)

- ea: `0x18002e908`
- end: `0x18002ea1a`
- name: `?StartActivity@DeleteUserProfile@ProfileTelemetry@@QEAAXXZ`
- size: `274`
- prototype: `void __fastcall(ProfileTelemetry::DeleteUserProfile *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x18002eae0`

## callees

- `0x180014c90`
- `0x180017220`
- `0x180023950`
- `0x18002530c`
- `0x18002682c`
- `0x180029cf8`
- `0x18002e908`
- `0x1800367dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e99b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e99b`
- `ntdll!EtwEventActivityIdControl` at `0x18002e951`
- `ntdll!EtwEventActivityIdControl` at `0x18002e951`

## pseudocode

```c
void __fastcall ProfileTelemetry::DeleteUserProfile::StartActivity(ProfileTelemetry::DeleteUserProfile *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rax
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // rdi
  __int64 v6; // r8
  __int64 v7; // rcx
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v9; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<ProfileLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &CurrentThreadId);
  v2 = *((_QWORD *)this + 34);
  v3 = ProfileLogging::Provider();
  if ( *(_DWORD *)v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x400000000000LL) )
    EtwEventActivityIdControl(3, v2 + 8);
  else
    *(_OWORD *)(v2 + 8) = 0;
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&CurrentThreadId);
  v4 = ProfileLogging::Provider();
  v5 = (__int64)v4;
  if ( *(_DWORD *)v4 > 5u && (unsigned __int8)tlgKeywordOn(v4, 0x400000000000LL) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v9 = 0x1000000;
    v6 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v6 + 4) || _tlgGuidIsZero((const struct _GUID *)(v6 + 24)) )
      v7 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v5,
      (unsigned __int8 *)&unk_180070C98,
      v6 + 8,
      v7,
      (__int64)&v9,
      (__int64)&CurrentThreadId);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((ProfileTelemetry::DeleteUserProfile *)((char *)this + 288));
}

```

## disassembly

```asm
0x18002e908  mov     [rsp+arg_10], rbx
0x18002e90d  push    rdi
0x18002e90e  sub     rsp, 30h
0x18002e912  mov     rbx, rcx
0x18002e915  lea     rdx, [rsp+38h+arg_0]
0x18002e91a  call    ?LockExclusive@?$ActivityBase@VProfileLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ProfileLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002e91f  mov     rdi, [rbx+110h]
0x18002e926  call    ?Provider@ProfileLogging@@SAPEBU_tlgProvider_t@@XZ; ProfileLogging::Provider(void)
0x18002e92b  mov     edx, [rax]
0x18002e92d  cmp     edx, 5
0x18002e930  jbe     short loc_18002E95F
0x18002e932  mov     rdx, 400000000000h
0x18002e93c  mov     rcx, rax
0x18002e93f  call    _tlgKeywordOn
0x18002e944  test    al, al
0x18002e946  jz      short loc_18002E95F
0x18002e948  lea     rdx, [rdi+8]
0x18002e94c  mov     ecx, 3
0x18002e951  call    cs:__imp_EtwEventActivityIdControl
0x18002e958  nop     dword ptr [rax+rax+00h]
0x18002e95d  jmp     short loc_18002E966
0x18002e95f  xorps   xmm0, xmm0
0x18002e962  movups  xmmword ptr [rdi+8], xmm0
0x18002e966  mov     dword ptr [rdi], 1
0x18002e96c  lea     rcx, [rsp+38h+arg_0]
0x18002e971  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002e976  call    ?Provider@ProfileLogging@@SAPEBU_tlgProvider_t@@XZ; ProfileLogging::Provider(void)
0x18002e97b  mov     rdi, rax
0x18002e97e  mov     ecx, [rax]
0x18002e980  cmp     ecx, 5
0x18002e983  jbe     short loc_18002E9FB
0x18002e985  mov     rdx, 400000000000h
0x18002e98f  mov     rcx, rax
0x18002e992  call    _tlgKeywordOn
0x18002e997  test    al, al
0x18002e999  jz      short loc_18002E9FB
0x18002e99b  call    cs:__imp_GetCurrentThreadId
0x18002e9a2  nop     dword ptr [rax+rax+00h]
0x18002e9a7  mov     [rsp+38h+arg_0], eax
0x18002e9ab  mov     [rsp+38h+arg_8], 1000000h
0x18002e9b4  mov     r8, [rbx+110h]
0x18002e9bb  cmp     byte ptr [r8+4], 0
0x18002e9c0  jz      short loc_18002E9CF
0x18002e9c2  lea     rcx, [r8+18h]; struct _GUID *
0x18002e9c6  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x18002e9cb  test    al, al
0x18002e9cd  jz      short loc_18002E9D1
0x18002e9cf  xor     ecx, ecx
0x18002e9d1  add     r8, 8
0x18002e9d5  lea     rax, [rsp+38h+arg_0]
0x18002e9da  mov     [rsp+38h+var_10], rax
0x18002e9df  lea     rax, [rsp+38h+arg_8]
0x18002e9e4  mov     [rsp+38h+var_18], rax
0x18002e9e9  mov     r9, rcx
0x18002e9ec  lea     rdx, unk_180070C98
0x18002e9f3  mov     rcx, rdi
0x18002e9f6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18002e9fb  lea     rcx, [rbx+120h]; this
0x18002ea02  cmp     dword ptr [rcx+18h], 0
0x18002ea06  jnz     short loc_18002EA0E
0x18002ea08  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18002ea0d  nop
0x18002ea0e  mov     rbx, [rsp+38h+arg_10]
0x18002ea13  add     rsp, 30h
0x18002ea17  pop     rdi
0x18002ea18  retn
```
