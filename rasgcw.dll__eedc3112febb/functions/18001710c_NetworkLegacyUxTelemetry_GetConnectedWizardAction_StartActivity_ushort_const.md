# NetworkLegacyUxTelemetry::GetConnectedWizardAction::StartActivity(ushort const *)

- ea: `0x18001710c`
- end: `0x180017233`
- name: `?StartActivity@GetConnectedWizardAction@NetworkLegacyUxTelemetry@@QEAAXPEBG@Z`
- size: `295`
- prototype: `void __fastcall(NetworkLegacyUxTelemetry::GetConnectedWizardAction *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180016410`

## callees

- `0x1800019a0`
- `0x180001b0c`
- `0x180014754`
- `0x180015a38`
- `0x1800166d4`
- `0x18001710c`
- `0x18001723c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800171a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800171a5`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180017158`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180017158`

## pseudocode

```c
void __fastcall NetworkLegacyUxTelemetry::GetConnectedWizardAction::StartActivity(
        NetworkLegacyUxTelemetry::GetConnectedWizardAction *this,
        const unsigned __int16 *a2)
{
  __int64 v4; // rbx
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r8
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // r8
  __int64 v9; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  __int64 v12; // r9
  DWORD v13; // [rsp+60h] [rbp+8h] BYREF
  const wchar_t *v14; // [rsp+70h] [rbp+18h] BYREF
  __int64 v15; // [rsp+78h] [rbp+20h] BYREF

  wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &v13);
  v4 = *((_QWORD *)this + 34);
  v5 = NetworkLegacyUxLogging::Provider();
  v6 = *(unsigned int *)v5;
  if ( (unsigned int)v6 > 5 && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL, v6) )
    EventActivityIdControl(3u, (LPGUID)(v4 + 8));
  else
    *(_OWORD *)(v4 + 8) = 0;
  *(_DWORD *)v4 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
  v7 = NetworkLegacyUxLogging::Provider();
  v9 = (__int64)v7;
  if ( *(_DWORD *)v7 > 5u && (unsigned __int8)tlgKeywordOn(v7, 0x400000000000LL, v8) )
  {
    v14 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v11 = *((_QWORD *)this + 34);
    v13 = CurrentThreadId;
    v15 = 0;
    if ( !*(_BYTE *)(v11 + 4)
      || (v12 = v11 + 24, !*(_DWORD *)(v11 + 24))
      && !*(_DWORD *)(v11 + 28)
      && !*(_DWORD *)(v11 + 32)
      && !*(_DWORD *)(v11 + 36) )
    {
      v12 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      v9,
      (__int64)byte_1800431E9,
      v11 + 8,
      v12,
      (__int64)&v15,
      (__int64)&v13,
      &v14);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((NetworkLegacyUxTelemetry::GetConnectedWizardAction *)((char *)this + 288));
}

```

## disassembly

```asm
0x18001710c  push    rbx
0x18001710e  push    rsi
0x18001710f  push    rdi
0x180017110  sub     rsp, 40h
0x180017114  mov     rsi, rdx
0x180017117  mov     rdi, rcx
0x18001711a  lea     rdx, [rsp+58h+arg_0]
0x18001711f  call    ?LockExclusive@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180017124  mov     rbx, [rdi+110h]
0x18001712b  call    ?Provider@NetworkLegacyUxLogging@@SAPEBU_tlgProvider_t@@XZ; NetworkLegacyUxLogging::Provider(void)
0x180017130  mov     r8d, [rax]
0x180017133  cmp     r8d, 5
0x180017137  jbe     short loc_180017160
0x180017139  mov     rdx, 400000000000h
0x180017143  mov     rcx, rax
0x180017146  call    _tlgKeywordOn
0x18001714b  test    al, al
0x18001714d  jz      short loc_180017160
0x18001714f  lea     rdx, [rbx+8]; ActivityId
0x180017153  mov     ecx, 3; ControlCode
0x180017158  call    cs:__imp_EventActivityIdControl
0x18001715e  jmp     short loc_180017167
0x180017160  xorps   xmm0, xmm0
0x180017163  movups  xmmword ptr [rbx+8], xmm0
0x180017167  lea     rcx, [rsp+58h+arg_0]
0x18001716c  mov     dword ptr [rbx], 1
0x180017172  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180017177  call    ?Provider@NetworkLegacyUxLogging@@SAPEBU_tlgProvider_t@@XZ; NetworkLegacyUxLogging::Provider(void)
0x18001717c  mov     rbx, rax
0x18001717f  mov     ecx, [rax]
0x180017181  cmp     ecx, 5
0x180017184  jbe     loc_180017219
0x18001718a  mov     rdx, 400000000000h
0x180017194  mov     rcx, rax
0x180017197  call    _tlgKeywordOn
0x18001719c  test    al, al
0x18001719e  jz      short loc_180017219
0x1800171a0  mov     [rsp+58h+arg_10], rsi
0x1800171a5  call    cs:__imp_GetCurrentThreadId
0x1800171ab  mov     r8, [rdi+110h]
0x1800171b2  mov     [rsp+58h+arg_0], eax
0x1800171b6  mov     [rsp+58h+arg_18], 0
0x1800171bf  cmp     byte ptr [r8+4], 0
0x1800171c4  jz      short loc_1800171E5
0x1800171c6  lea     r9, [r8+18h]
0x1800171ca  cmp     dword ptr [r9], 0
0x1800171ce  jnz     short loc_1800171E8
0x1800171d0  cmp     dword ptr [r9+4], 0
0x1800171d5  jnz     short loc_1800171E8
0x1800171d7  cmp     dword ptr [r9+8], 0
0x1800171dc  jnz     short loc_1800171E8
0x1800171de  cmp     dword ptr [r9+0Ch], 0
0x1800171e3  jnz     short loc_1800171E8
0x1800171e5  xor     r9d, r9d
0x1800171e8  lea     rax, [rsp+58h+arg_10]
0x1800171ed  add     r8, 8
0x1800171f1  mov     [rsp+58h+var_28], rax
0x1800171f6  lea     rdx, byte_1800431E9
0x1800171fd  lea     rax, [rsp+58h+arg_0]
0x180017202  mov     rcx, rbx
0x180017205  mov     [rsp+58h+var_30], rax
0x18001720a  lea     rax, [rsp+58h+arg_18]
0x18001720f  mov     [rsp+58h+var_38], rax
0x180017214  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180017219  lea     rcx, [rdi+120h]; this
0x180017220  cmp     dword ptr [rcx+18h], 0
0x180017224  jnz     short loc_18001722B
0x180017226  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18001722b  add     rsp, 40h
0x18001722f  pop     rdi
0x180017230  pop     rsi
0x180017231  pop     rbx
0x180017232  retn
```
