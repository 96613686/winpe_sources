# NetworkLegacyUxTelemetry::ConfigureAdvancedSharingSetting::StartActivity(void)

- ea: `0x180008cbc`
- end: `0x180008dd4`
- name: `?StartActivity@ConfigureAdvancedSharingSetting@NetworkLegacyUxTelemetry@@QEAAXXZ`
- size: `280`
- prototype: `void __fastcall(NetworkLegacyUxTelemetry::ConfigureAdvancedSharingSetting *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180009de8`

## callees

- `0x1800013ac`
- `0x180001bac`
- `0x1800070ac`
- `0x1800079f0`
- `0x18000847c`
- `0x180008cbc`
- `0x180008f5c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008d4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008d4d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180008d05`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180008d05`

## pseudocode

```c
void __fastcall NetworkLegacyUxTelemetry::ConfigureAdvancedSharingSetting::StartActivity(
        NetworkLegacyUxTelemetry::ConfigureAdvancedSharingSetting *this)
{
  __int64 v2; // rbx
  const struct _tlgProvider_t *v3; // rax
  const struct _tlgProvider_t *v4; // rax
  int v5; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v7; // r8
  int v8; // r9d
  DWORD v9; // [rsp+40h] [rbp+8h] BYREF
  __int64 v10; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &v9);
  v2 = *((_QWORD *)this + 34);
  v3 = NetworkLegacyUxLogging::Provider();
  if ( *(_DWORD *)v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x400000000000LL) )
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  else
    *(_OWORD *)(v2 + 8) = 0;
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  v4 = NetworkLegacyUxLogging::Provider();
  v5 = (int)v4;
  if ( *(_DWORD *)v4 > 5u && (unsigned __int8)tlgKeywordOn(v4, 0x400000000000LL) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v7 = *((_QWORD *)this + 34);
    v9 = CurrentThreadId;
    v10 = 0;
    if ( !*(_BYTE *)(v7 + 4)
      || (v8 = v7 + 24, !*(_DWORD *)(v7 + 24))
      && !*(_DWORD *)(v7 + 28)
      && !*(_DWORD *)(v7 + 32)
      && !*(_DWORD *)(v7 + 36) )
    {
      v8 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v5,
      (unsigned int)&unk_180021760,
      v7 + 8,
      v8,
      (__int64)&v10,
      (__int64)&v9);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((NetworkLegacyUxTelemetry::ConfigureAdvancedSharingSetting *)((char *)this + 288));
}

```

## disassembly

```asm
0x180008cbc  mov     [rsp+arg_10], rbx
0x180008cc1  push    rdi
0x180008cc2  sub     rsp, 30h
0x180008cc6  lea     rdx, [rsp+38h+arg_0]
0x180008ccb  mov     rdi, rcx
0x180008cce  call    ?LockExclusive@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180008cd3  mov     rbx, [rdi+110h]
0x180008cda  call    ?Provider@NetworkLegacyUxLogging@@SAPEBU_tlgProvider_t@@XZ; NetworkLegacyUxLogging::Provider(void)
0x180008cdf  mov     edx, [rax]
0x180008ce1  cmp     edx, 5
0x180008ce4  jbe     short loc_180008D0D
0x180008ce6  mov     rdx, 400000000000h
0x180008cf0  mov     rcx, rax
0x180008cf3  call    _tlgKeywordOn
0x180008cf8  test    al, al
0x180008cfa  jz      short loc_180008D0D
0x180008cfc  lea     rdx, [rbx+8]; ActivityId
0x180008d00  mov     ecx, 3; ControlCode
0x180008d05  call    cs:__imp_EventActivityIdControl
0x180008d0b  jmp     short loc_180008D14
0x180008d0d  xorps   xmm0, xmm0
0x180008d10  movups  xmmword ptr [rbx+8], xmm0
0x180008d14  lea     rcx, [rsp+38h+arg_0]
0x180008d19  mov     dword ptr [rbx], 1
0x180008d1f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180008d24  call    ?Provider@NetworkLegacyUxLogging@@SAPEBU_tlgProvider_t@@XZ; NetworkLegacyUxLogging::Provider(void)
0x180008d29  mov     rbx, rax
0x180008d2c  mov     ecx, [rax]
0x180008d2e  cmp     ecx, 5
0x180008d31  jbe     loc_180008DB7
0x180008d37  mov     rdx, 400000000000h
0x180008d41  mov     rcx, rax
0x180008d44  call    _tlgKeywordOn
0x180008d49  test    al, al
0x180008d4b  jz      short loc_180008DB7
0x180008d4d  call    cs:__imp_GetCurrentThreadId
0x180008d53  mov     r8, [rdi+110h]
0x180008d5a  mov     [rsp+38h+arg_0], eax
0x180008d5e  mov     [rsp+38h+arg_8], 0
0x180008d67  cmp     byte ptr [r8+4], 0
0x180008d6c  jz      short loc_180008D8D
0x180008d6e  lea     r9, [r8+18h]
0x180008d72  cmp     dword ptr [r9], 0
0x180008d76  jnz     short loc_180008D90
0x180008d78  cmp     dword ptr [r9+4], 0
0x180008d7d  jnz     short loc_180008D90
0x180008d7f  cmp     dword ptr [r9+8], 0
0x180008d84  jnz     short loc_180008D90
0x180008d86  cmp     dword ptr [r9+0Ch], 0
0x180008d8b  jnz     short loc_180008D90
0x180008d8d  xor     r9d, r9d
0x180008d90  lea     rax, [rsp+38h+arg_0]
0x180008d95  add     r8, 8
0x180008d99  mov     [rsp+38h+var_10], rax
0x180008d9e  lea     rdx, unk_180021760
0x180008da5  lea     rax, [rsp+38h+arg_8]
0x180008daa  mov     rcx, rbx
0x180008dad  mov     [rsp+38h+var_18], rax
0x180008db2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180008db7  lea     rcx, [rdi+120h]; this
0x180008dbe  cmp     dword ptr [rcx+18h], 0
0x180008dc2  jnz     short loc_180008DC9
0x180008dc4  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180008dc9  mov     rbx, [rsp+38h+arg_10]
0x180008dce  add     rsp, 30h
0x180008dd2  pop     rdi
0x180008dd3  retn
```
