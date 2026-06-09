# NetworkLegacyUxTelemetry::NetworkCenterOpen::StartActivity(void)

- ea: `0x180011acc`
- end: `0x180011c30`
- name: `?StartActivity@NetworkCenterOpen@NetworkLegacyUxTelemetry@@QEAAXXZ`
- size: `356`
- prototype: `void __fastcall(NetworkLegacyUxTelemetry::NetworkCenterOpen *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000bd00`

## callees

- `0x180001a5c`
- `0x180001a88`
- `0x180002270`
- `0x18000815c`
- `0x18000c940`
- `0x18000f7b0`
- `0x180011acc`
- `0x180011e4c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180011b2f`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180011b2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011b7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011b7a`

## pseudocode

```c
void __fastcall NetworkLegacyUxTelemetry::NetworkCenterOpen::StartActivity(
        NetworkLegacyUxTelemetry::NetworkCenterOpen *this)
{
  __int64 v2; // rbx
  const struct _tlgProvider_t *v3; // rax
  const struct _tlgProvider_t *v4; // rax
  const struct _tlgProvider_t *v5; // rbx
  __int64 v6; // r8
  DWORD CurrentThreadId; // [rsp+30h] [rbp-9h] BYREF
  _QWORD v8[9]; // [rsp+38h] [rbp-1h] BYREF

  wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &CurrentThreadId);
  v2 = *((_QWORD *)this + 34);
  v3 = NetworkLegacyUxLogging::Provider();
  if ( *(_DWORD *)v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x400000000000LL) )
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  else
    *(_OWORD *)(v2 + 8) = 0;
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&CurrentThreadId);
  v4 = NetworkLegacyUxLogging::Provider();
  v5 = v4;
  if ( *(_DWORD *)v4 > 5u && (unsigned __int8)tlgKeywordOn(v4, 0x400000000000LL) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v8[0] = 0;
    v6 = *((_QWORD *)this + 34);
    v8[7] = &CurrentThreadId;
    v8[8] = 4;
    v8[5] = v8;
    v8[6] = 8;
    tlgWriteTransfer_EventWriteTransfer(v5, &unk_18002A50B, v6 + 8);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((NetworkLegacyUxTelemetry::NetworkCenterOpen *)((char *)this + 288));
}

```

## disassembly

```asm
0x180011acc  mov     [rsp-8+arg_8], rbx
0x180011ad1  mov     [rsp-8+arg_10], rdi
0x180011ad6  push    rbp
0x180011ad7  lea     rbp, [rsp-57h]
0x180011adc  sub     rsp, 90h
0x180011ae3  mov     rax, cs:__security_cookie
0x180011aea  xor     rax, rsp
0x180011aed  mov     [rbp+57h+var_10], rax
0x180011af1  mov     rdi, rcx
0x180011af4  lea     rdx, [rbp+57h+var_60]
0x180011af8  call    ?LockExclusive@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180011afd  mov     rbx, [rdi+110h]
0x180011b04  call    ?Provider@NetworkLegacyUxLogging@@SAPEBU_tlgProvider_t@@XZ; NetworkLegacyUxLogging::Provider(void)
0x180011b09  mov     edx, [rax]
0x180011b0b  cmp     edx, 5
0x180011b0e  jbe     short loc_180011B37
0x180011b10  mov     rdx, 400000000000h
0x180011b1a  mov     rcx, rax
0x180011b1d  call    _tlgKeywordOn
0x180011b22  test    al, al
0x180011b24  jz      short loc_180011B37
0x180011b26  lea     rdx, [rbx+8]; ActivityId
0x180011b2a  mov     ecx, 3; ControlCode
0x180011b2f  call    cs:__imp_EventActivityIdControl
0x180011b35  jmp     short loc_180011B3E
0x180011b37  xorps   xmm0, xmm0
0x180011b3a  movups  xmmword ptr [rbx+8], xmm0
0x180011b3e  mov     dword ptr [rbx], 1
0x180011b44  lea     rcx, [rbp+57h+var_60]
0x180011b48  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180011b4d  call    ?Provider@NetworkLegacyUxLogging@@SAPEBU_tlgProvider_t@@XZ; NetworkLegacyUxLogging::Provider(void)
0x180011b52  mov     rbx, rax
0x180011b55  mov     ecx, [rax]
0x180011b57  cmp     ecx, 5
0x180011b5a  jbe     loc_180011BFC
0x180011b60  mov     rdx, 400000000000h
0x180011b6a  mov     rcx, rax
0x180011b6d  call    _tlgKeywordOn
0x180011b72  test    al, al
0x180011b74  jz      loc_180011BFC
0x180011b7a  call    cs:__imp_GetCurrentThreadId
0x180011b80  mov     [rbp+57h+var_60], eax
0x180011b83  mov     [rbp+57h+var_58], 0
0x180011b8b  mov     r8, [rdi+110h]
0x180011b92  cmp     byte ptr [r8+4], 0
0x180011b97  jz      short loc_180011BB8
0x180011b99  lea     r9, [r8+18h]
0x180011b9d  cmp     dword ptr [r9], 0
0x180011ba1  jnz     short loc_180011BBB
0x180011ba3  cmp     dword ptr [r9+4], 0
0x180011ba8  jnz     short loc_180011BBB
0x180011baa  cmp     dword ptr [r9+8], 0
0x180011baf  jnz     short loc_180011BBB
0x180011bb1  cmp     dword ptr [r9+0Ch], 0
0x180011bb6  jnz     short loc_180011BBB
0x180011bb8  xor     r9d, r9d
0x180011bbb  lea     rax, [rbp+57h+var_60]
0x180011bbf  mov     [rbp+57h+var_20], rax
0x180011bc3  mov     ecx, 4
0x180011bc8  mov     [rbp+57h+var_18], rcx
0x180011bcc  lea     rax, [rbp+57h+var_58]
0x180011bd0  mov     [rbp+57h+var_30], rax
0x180011bd4  mov     [rbp+57h+var_28], 8
0x180011bdc  add     r8, 8
0x180011be0  lea     rax, [rbp+57h+var_50]
0x180011be4  mov     [rsp+90h+var_68], rax
0x180011be9  mov     [rsp+90h+var_70], ecx
0x180011bed  lea     rdx, unk_18002A50B
0x180011bf4  mov     rcx, rbx
0x180011bf7  call    _tlgWriteTransfer_EventWriteTransfer
0x180011bfc  lea     rcx, [rdi+120h]; this
0x180011c03  cmp     dword ptr [rcx+18h], 0
0x180011c07  jnz     short loc_180011C0F
0x180011c09  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180011c0e  nop
0x180011c0f  mov     rcx, [rbp+57h+var_10]
0x180011c13  xor     rcx, rsp; StackCookie
0x180011c16  call    __security_check_cookie
0x180011c1b  lea     r11, [rsp+90h+var_s0]
0x180011c23  mov     rbx, [r11+18h]
0x180011c27  mov     rdi, [r11+20h]
0x180011c2b  mov     rsp, r11
0x180011c2e  pop     rbp
0x180011c2f  retn
```
