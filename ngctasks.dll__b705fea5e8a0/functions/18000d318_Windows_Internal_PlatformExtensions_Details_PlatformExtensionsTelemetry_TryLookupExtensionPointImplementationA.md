# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::StartActivity(HSTRING__ *)

- ea: `0x18000d318`
- end: `0x18000d43b`
- name: `?StartActivity@TryLookupExtensionPointImplementationAcid@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEAUHSTRING__@@@Z`
- size: `291`
- prototype: `void(Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *__hidden this, HSTRING)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x18000e750`

## callees

- `0x180002188`
- `0x18000247c`
- `0x180008c94`
- `0x18000b39c`
- `0x18000c3bc`
- `0x18000d318`
- `0x18000d444`
- `0x18000ec2c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000d365`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000d365`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000d3b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000d3b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d3bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d3bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::StartActivity(
        Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *this,
        HSTRING a2)
{
  __int64 v4; // rbx
  const struct _tlgProvider_t *v5; // rax
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // rbx
  __int64 v8; // r8
  __int64 v9; // rcx
  RTL_SRWLOCK *v10; // [rsp+60h] [rbp+8h] BYREF
  PCWSTR StringRawBuffer; // [rsp+70h] [rbp+18h] BYREF
  __int64 v12; // [rsp+78h] [rbp+20h] BYREF

  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)this,
    &v10);
  v4 = *((_QWORD *)this + 34);
  v5 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
  if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x200000000000LL) )
    EventActivityIdControl(3u, (LPGUID)(v4 + 8));
  else
    *(_OWORD *)(v4 + 8) = 0;
  *(_DWORD *)v4 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  v6 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
  v7 = (__int64)v6;
  if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x200000000000LL) )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
    LODWORD(v10) = GetCurrentThreadId();
    v12 = 0;
    v8 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v8 + 4) || _tlgGuidIsZero((const struct _GUID *)(v8 + 24)) )
      v9 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      v7,
      (__int64)&byte_1800285B7,
      v8 + 8,
      v9,
      (__int64)&v12,
      (__int64)&v10,
      &StringRawBuffer);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *)((char *)this + 288));
}

```

## disassembly

```asm
0x18000d318  push    rbx
0x18000d31a  push    rsi
0x18000d31b  push    rdi
0x18000d31c  sub     rsp, 40h
0x18000d320  mov     rsi, rdx
0x18000d323  mov     rdi, rcx
0x18000d326  lea     rdx, [rsp+58h+arg_0]
0x18000d32b  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000d330  nop
0x18000d331  mov     rbx, [rdi+110h]
0x18000d338  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x18000d33d  mov     r8d, [rax]
0x18000d340  cmp     r8d, 5
0x18000d344  jbe     short loc_18000D36D
0x18000d346  mov     rdx, 200000000000h
0x18000d350  mov     rcx, rax
0x18000d353  call    _tlgKeywordOn
0x18000d358  test    al, al
0x18000d35a  jz      short loc_18000D36D
0x18000d35c  lea     rdx, [rbx+8]; ActivityId
0x18000d360  mov     ecx, 3; ControlCode
0x18000d365  call    cs:__imp_EventActivityIdControl
0x18000d36b  jmp     short loc_18000D374
0x18000d36d  xorps   xmm0, xmm0
0x18000d370  movups  xmmword ptr [rbx+8], xmm0
0x18000d374  mov     dword ptr [rbx], 1
0x18000d37a  lea     rcx, [rsp+58h+arg_0]
0x18000d37f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000d384  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x18000d389  mov     rbx, rax
0x18000d38c  mov     ecx, [rax]
0x18000d38e  cmp     ecx, 5
0x18000d391  jbe     loc_18000D421
0x18000d397  mov     rdx, 200000000000h
0x18000d3a1  mov     rcx, rax
0x18000d3a4  call    _tlgKeywordOn
0x18000d3a9  test    al, al
0x18000d3ab  jz      short loc_18000D421
0x18000d3ad  xor     edx, edx; length
0x18000d3af  mov     rcx, rsi; string
0x18000d3b2  call    cs:__imp_WindowsGetStringRawBuffer
0x18000d3b8  mov     [rsp+58h+arg_10], rax
0x18000d3bd  call    cs:__imp_GetCurrentThreadId
0x18000d3c3  mov     dword ptr [rsp+58h+arg_0], eax
0x18000d3c7  mov     [rsp+58h+arg_18], 0
0x18000d3d0  mov     r8, [rdi+110h]
0x18000d3d7  cmp     byte ptr [r8+4], 0
0x18000d3dc  jz      short loc_18000D3EB
0x18000d3de  lea     rcx, [r8+18h]; struct _GUID *
0x18000d3e2  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x18000d3e7  test    al, al
0x18000d3e9  jz      short loc_18000D3ED
0x18000d3eb  xor     ecx, ecx
0x18000d3ed  add     r8, 8
0x18000d3f1  lea     rax, [rsp+58h+arg_10]
0x18000d3f6  mov     [rsp+58h+var_28], rax
0x18000d3fb  lea     rax, [rsp+58h+arg_0]
0x18000d400  mov     [rsp+58h+var_30], rax
0x18000d405  lea     rax, [rsp+58h+arg_18]
0x18000d40a  mov     [rsp+58h+var_38], rax
0x18000d40f  mov     r9, rcx
0x18000d412  lea     rdx, byte_1800285B7
0x18000d419  mov     rcx, rbx
0x18000d41c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18000d421  lea     rcx, [rdi+120h]; this
0x18000d428  cmp     dword ptr [rcx+18h], 0
0x18000d42c  jnz     short loc_18000D433
0x18000d42e  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18000d433  add     rsp, 40h
0x18000d437  pop     rdi
0x18000d438  pop     rsi
0x18000d439  pop     rbx
0x18000d43a  retn
```
