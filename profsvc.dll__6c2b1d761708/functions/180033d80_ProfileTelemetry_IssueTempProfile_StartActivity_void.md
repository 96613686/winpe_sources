# ProfileTelemetry::IssueTempProfile::StartActivity(void)

- ea: `0x180033d80`
- end: `0x180033e92`
- name: `?StartActivity@IssueTempProfile@ProfileTelemetry@@QEAAXXZ`
- size: `274`
- prototype: `void __fastcall(ProfileTelemetry::IssueTempProfile *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x18002e1dc`

## callees

- `0x180014c90`
- `0x180017220`
- `0x180023950`
- `0x180024e80`
- `0x18002530c`
- `0x180029cf8`
- `0x180033d80`
- `0x1800367dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033e13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033e13`
- `ntdll!EtwEventActivityIdControl` at `0x180033dc9`
- `ntdll!EtwEventActivityIdControl` at `0x180033dc9`

## pseudocode

```c
void __fastcall ProfileTelemetry::IssueTempProfile::StartActivity(ProfileTelemetry::IssueTempProfile *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rax
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // rdi
  __int64 v6; // r8
  __int64 v7; // rcx
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v9; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<ProfileLogging,1,70368744177664,1,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &CurrentThreadId);
  v2 = *((_QWORD *)this + 34);
  v3 = ProfileLogging::Provider();
  if ( *(_DWORD *)v3 > 1u && (unsigned __int8)tlgKeywordOn(v3, 0x400000000000LL) )
    EtwEventActivityIdControl(3, v2 + 8);
  else
    *(_OWORD *)(v2 + 8) = 0;
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&CurrentThreadId);
  v4 = ProfileLogging::Provider();
  v5 = (__int64)v4;
  if ( *(_DWORD *)v4 > 1u && (unsigned __int8)tlgKeywordOn(v4, 0x400000000000LL) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v9 = 0x1000000;
    v6 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v6 + 4) || _tlgGuidIsZero((const struct _GUID *)(v6 + 24)) )
      v7 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v5,
      (unsigned __int8 *)&word_180073736,
      v6 + 8,
      v7,
      (__int64)&v9,
      (__int64)&CurrentThreadId);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((ProfileTelemetry::IssueTempProfile *)((char *)this + 288));
}

```

## disassembly

```asm
0x180033d80  mov     [rsp+arg_10], rbx
0x180033d85  push    rdi
0x180033d86  sub     rsp, 30h
0x180033d8a  mov     rbx, rcx
0x180033d8d  lea     rdx, [rsp+38h+arg_0]
0x180033d92  call    ?LockExclusive@?$ActivityBase@VProfileLogging@@$00$0EAAAAAAAAAAA@$00$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ProfileLogging,1,70368744177664,1,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180033d97  mov     rdi, [rbx+110h]
0x180033d9e  call    ?Provider@ProfileLogging@@SAPEBU_tlgProvider_t@@XZ; ProfileLogging::Provider(void)
0x180033da3  mov     edx, [rax]
0x180033da5  cmp     edx, 1
0x180033da8  jbe     short loc_180033DD7
0x180033daa  mov     rdx, 400000000000h
0x180033db4  mov     rcx, rax
0x180033db7  call    _tlgKeywordOn
0x180033dbc  test    al, al
0x180033dbe  jz      short loc_180033DD7
0x180033dc0  lea     rdx, [rdi+8]
0x180033dc4  mov     ecx, 3
0x180033dc9  call    cs:__imp_EtwEventActivityIdControl
0x180033dd0  nop     dword ptr [rax+rax+00h]
0x180033dd5  jmp     short loc_180033DDE
0x180033dd7  xorps   xmm0, xmm0
0x180033dda  movups  xmmword ptr [rdi+8], xmm0
0x180033dde  mov     dword ptr [rdi], 1
0x180033de4  lea     rcx, [rsp+38h+arg_0]
0x180033de9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180033dee  call    ?Provider@ProfileLogging@@SAPEBU_tlgProvider_t@@XZ; ProfileLogging::Provider(void)
0x180033df3  mov     rdi, rax
0x180033df6  mov     ecx, [rax]
0x180033df8  cmp     ecx, 1
0x180033dfb  jbe     short loc_180033E73
0x180033dfd  mov     rdx, 400000000000h
0x180033e07  mov     rcx, rax
0x180033e0a  call    _tlgKeywordOn
0x180033e0f  test    al, al
0x180033e11  jz      short loc_180033E73
0x180033e13  call    cs:__imp_GetCurrentThreadId
0x180033e1a  nop     dword ptr [rax+rax+00h]
0x180033e1f  mov     [rsp+38h+arg_0], eax
0x180033e23  mov     [rsp+38h+arg_8], 1000000h
0x180033e2c  mov     r8, [rbx+110h]
0x180033e33  cmp     byte ptr [r8+4], 0
0x180033e38  jz      short loc_180033E47
0x180033e3a  lea     rcx, [r8+18h]; struct _GUID *
0x180033e3e  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180033e43  test    al, al
0x180033e45  jz      short loc_180033E49
0x180033e47  xor     ecx, ecx
0x180033e49  add     r8, 8
0x180033e4d  lea     rax, [rsp+38h+arg_0]
0x180033e52  mov     [rsp+38h+var_10], rax
0x180033e57  lea     rax, [rsp+38h+arg_8]
0x180033e5c  mov     [rsp+38h+var_18], rax
0x180033e61  mov     r9, rcx
0x180033e64  lea     rdx, word_180073736
0x180033e6b  mov     rcx, rdi
0x180033e6e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180033e73  lea     rcx, [rbx+120h]; this
0x180033e7a  cmp     dword ptr [rcx+18h], 0
0x180033e7e  jnz     short loc_180033E86
0x180033e80  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180033e85  nop
0x180033e86  mov     rbx, [rsp+38h+arg_10]
0x180033e8b  add     rsp, 30h
0x180033e8f  pop     rdi
0x180033e90  retn
```
