# winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,void>::GetResults(void)

- ea: `0x18001bae4`
- end: `0x18001bb54`
- name: `?GetResults@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@W4GraphicsCaptureAccessKind@Capture@Graphics@34@@experimental@std@@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEAA@XZ`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001bab0`

## callees

- `0x1800022f2`
- `0x180002384`
- `0x180002390`
- `0x1800058c4`
- `0x1800141c4`
- `0x180015d44`
- `0x18001bae4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,enum winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind>::promise_type,winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,void>::GetResults(
        __int64 a1)
{
  RTL_SRWLOCK *v2; // rdi
  int v3; // edx
  unsigned int v4; // ebx
  const struct winrt::impl::slim_source_location *v6; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v8[32]; // [rsp+38h] [rbp-20h] BYREF

  v2 = (RTL_SRWLOCK *)(a1 + 72);
  WINRT_IMPL_AcquireSRWLockExclusive((PSRWLOCK)(a1 + 72));
  v3 = *(_DWORD *)(a1 + 96);
  if ( v3 != 1 )
  {
    winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Graphics::Capture::implementation::GraphicsCapturePicker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,void>::rethrow_if_failed(
      a1,
      v3);
    v6 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v8);
    winrt::hresult_illegal_method_call::hresult_illegal_method_call(
      (winrt::hresult_illegal_method_call *)pExceptionObject,
      v6);
    throw (winrt::hresult_illegal_method_call *)pExceptionObject;
  }
  v4 = *(_DWORD *)(a1 + 104);
  ReleaseSRWLockExclusive_0(v2);
  return v4;
}

```

## disassembly

```asm
0x18001bae4  mov     [rsp+arg_8], rbx
0x18001bae9  push    rdi
0x18001baea  sub     rsp, 50h
0x18001baee  mov     rbx, rcx
0x18001baf1  lea     rdi, [rcx+48h]
0x18001baf5  mov     [rsp+58h+arg_0], rdi
0x18001bafa  mov     rcx, rdi; SRWLock
0x18001bafd  call    WINRT_IMPL_AcquireSRWLockExclusive
0x18001bb02  nop
0x18001bb03  mov     edx, [rbx+60h]
0x18001bb06  cmp     edx, 1
0x18001bb09  jnz     short loc_18001BB23
0x18001bb0b  mov     ebx, [rbx+68h]
0x18001bb0e  mov     rcx, rdi; SRWLock
0x18001bb11  call    ReleaseSRWLockExclusive_0
0x18001bb16  mov     eax, ebx
0x18001bb18  mov     rbx, [rsp+58h+arg_8]
0x18001bb1d  add     rsp, 50h
0x18001bb21  pop     rdi
0x18001bb22  retn
0x18001bb23  mov     rcx, rbx
0x18001bb26  call    ?rethrow_if_failed@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUGraphicsCapturePicker@implementation@Capture@Graphics@34@@experimental@std@@U?$IAsyncOperation@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@IEBAXW4AsyncStatus@Foundation@Windows@3@@Z; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Graphics::Capture::implementation::GraphicsCapturePicker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,void>::rethrow_if_failed(winrt::Windows::Foundation::AsyncStatus)
0x18001bb2b  lea     rcx, [rsp+58h+var_20]
0x18001bb30  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001bb35  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18001bb38  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18001bb3d  call    ??0hresult_illegal_method_call@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_method_call::hresult_illegal_method_call(winrt::impl::slim_source_location const &)
0x18001bb42  lea     rdx, _TI2?AUhresult_illegal_method_call@winrt@@; pThrowInfo
0x18001bb49  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001bb4e  call    _CxxThrowException_0
```
