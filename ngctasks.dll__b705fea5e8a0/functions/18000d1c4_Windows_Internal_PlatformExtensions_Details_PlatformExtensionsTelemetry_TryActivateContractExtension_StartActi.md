# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StartActivity(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &)

- ea: `0x18000d1c4`
- end: `0x18000d30f`
- name: `?StartActivity@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@56@AEBU_GUID@@@Z`
- size: `331`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x180007f50`

## callees

- `0x18000224c`
- `0x18000247c`
- `0x180008c94`
- `0x18000b39c`
- `0x18000c3bc`
- `0x18000d1c4`
- `0x18000d444`
- `0x18000ec2c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000d21e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000d21e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000d275`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000d275`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d27f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d27f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StartActivity(
        __int64 a1,
        HSTRING a2,
        int a3,
        __int64 a4)
{
  __int64 v8; // rdi
  const struct _tlgProvider_t *v9; // rax
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // rdi
  __int64 v12; // r8
  __int64 v13; // rcx
  DWORD CurrentThreadId; // [rsp+50h] [rbp-28h] BYREF
  __int64 v15; // [rsp+58h] [rbp-20h]
  PCWSTR StringRawBuffer; // [rsp+60h] [rbp-18h] BYREF
  __int64 v17; // [rsp+68h] [rbp-10h] BYREF
  RTL_SRWLOCK *v18; // [rsp+B0h] [rbp+38h] BYREF

  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v18);
  v8 = *(_QWORD *)(a1 + 272);
  v9 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
  if ( *(_DWORD *)v9 > 5u && (unsigned __int8)tlgKeywordOn(v9, 0x400000000000LL) )
    EventActivityIdControl(3u, (LPGUID)(v8 + 8));
  else
    *(_OWORD *)(v8 + 8) = 0;
  *(_DWORD *)v8 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v18);
  v10 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
  v11 = (__int64)v10;
  if ( *(_DWORD *)v10 > 5u && (unsigned __int8)tlgKeywordOn(v10, 0x400000000000LL) )
  {
    v15 = a4;
    LODWORD(v18) = a3;
    StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
    CurrentThreadId = GetCurrentThreadId();
    v17 = 0;
    v12 = *(_QWORD *)(a1 + 272);
    if ( !*(_BYTE *)(v12 + 4) || _tlgGuidIsZero((const struct _GUID *)(v12 + 24)) )
      v13 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      v11,
      (__int64)&unk_1800288D0,
      v12 + 8,
      v13,
      (__int64)&v17,
      (__int64)&CurrentThreadId,
      &StringRawBuffer);
  }
  if ( !*(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
}

```

## disassembly

```asm
0x18000d1c4  push    rbp
0x18000d1c6  push    rbx
0x18000d1c7  push    rsi
0x18000d1c8  push    rdi
0x18000d1c9  push    r14
0x18000d1cb  push    r15
0x18000d1cd  mov     rbp, rsp
0x18000d1d0  sub     rsp, 78h
0x18000d1d4  mov     r14, r9
0x18000d1d7  mov     ebx, r8d
0x18000d1da  mov     r15, rdx
0x18000d1dd  mov     rsi, rcx
0x18000d1e0  lea     rdx, [rbp+arg_0]
0x18000d1e4  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000d1e9  nop
0x18000d1ea  mov     rdi, [rsi+110h]
0x18000d1f1  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x18000d1f6  mov     r8d, [rax]
0x18000d1f9  cmp     r8d, 5
0x18000d1fd  jbe     short loc_18000D226
0x18000d1ff  mov     rdx, 400000000000h
0x18000d209  mov     rcx, rax
0x18000d20c  call    _tlgKeywordOn
0x18000d211  test    al, al
0x18000d213  jz      short loc_18000D226
0x18000d215  lea     rdx, [rdi+8]; ActivityId
0x18000d219  mov     ecx, 3; ControlCode
0x18000d21e  call    cs:__imp_EventActivityIdControl
0x18000d224  jmp     short loc_18000D22D
0x18000d226  xorps   xmm0, xmm0
0x18000d229  movups  xmmword ptr [rdi+8], xmm0
0x18000d22d  mov     dword ptr [rdi], 1
0x18000d233  lea     rcx, [rbp+arg_0]
0x18000d237  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000d23c  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x18000d241  mov     rdi, rax
0x18000d244  mov     ecx, [rax]
0x18000d246  cmp     ecx, 5
0x18000d249  jbe     loc_18000D2F0
0x18000d24f  mov     rdx, 400000000000h
0x18000d259  mov     rcx, rax
0x18000d25c  call    _tlgKeywordOn
0x18000d261  test    al, al
0x18000d263  jz      loc_18000D2F0
0x18000d269  mov     [rbp+var_20], r14
0x18000d26d  mov     dword ptr [rbp+arg_0], ebx
0x18000d270  xor     edx, edx; length
0x18000d272  mov     rcx, r15; string
0x18000d275  call    cs:__imp_WindowsGetStringRawBuffer
0x18000d27b  mov     [rbp+var_18], rax
0x18000d27f  call    cs:__imp_GetCurrentThreadId
0x18000d285  mov     [rbp+var_28], eax
0x18000d288  mov     [rbp+var_10], 0
0x18000d290  mov     r8, [rsi+110h]
0x18000d297  cmp     byte ptr [r8+4], 0
0x18000d29c  jz      short loc_18000D2AB
0x18000d29e  lea     rcx, [r8+18h]; struct _GUID *
0x18000d2a2  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x18000d2a7  test    al, al
0x18000d2a9  jz      short loc_18000D2AD
0x18000d2ab  xor     ecx, ecx
0x18000d2ad  add     r8, 8
0x18000d2b1  lea     rax, [rbp+var_20]
0x18000d2b5  mov     [rsp+78h+var_38], rax
0x18000d2ba  lea     rax, [rbp+arg_0]
0x18000d2be  mov     [rsp+78h+var_40], rax
0x18000d2c3  lea     rax, [rbp+var_18]
0x18000d2c7  mov     [rsp+78h+var_48], rax
0x18000d2cc  lea     rax, [rbp+var_28]
0x18000d2d0  mov     [rsp+78h+var_50], rax
0x18000d2d5  lea     rax, [rbp+var_10]
0x18000d2d9  mov     [rsp+78h+var_58], rax
0x18000d2de  mov     r9, rcx
0x18000d2e1  lea     rdx, unk_1800288D0
0x18000d2e8  mov     rcx, rdi
0x18000d2eb  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18000d2f0  lea     rcx, [rsi+120h]; this
0x18000d2f7  cmp     dword ptr [rcx+18h], 0
0x18000d2fb  jnz     short loc_18000D302
0x18000d2fd  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18000d302  add     rsp, 78h
0x18000d306  pop     r15
0x18000d308  pop     r14
0x18000d30a  pop     rdi
0x18000d30b  pop     rsi
0x18000d30c  pop     rbx
0x18000d30d  pop     rbp
0x18000d30e  retn
```
