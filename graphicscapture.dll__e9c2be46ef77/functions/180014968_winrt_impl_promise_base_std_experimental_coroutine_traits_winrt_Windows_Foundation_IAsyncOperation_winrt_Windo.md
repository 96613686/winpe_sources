# winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,void>::ErrorCode(void)

- ea: `0x180014968`
- end: `0x1800149d1`
- name: `?ErrorCode@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@W4GraphicsCaptureAccessKind@Capture@Graphics@34@@experimental@std@@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEAA?AUhresult@3@XZ`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180015830`

## callees

- `0x180002384`
- `0x180002390`
- `0x180005d4c`
- `0x180014968`
- `0x180015d44`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_DWORD *__fastcall winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,enum winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind>::promise_type,winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,void>::ErrorCode(
        RTL_SRWLOCK *a1,
        _DWORD *a2)
{
  RTL_SRWLOCK *v4; // rdi
  int v5; // eax
  _DWORD *result; // rax

  v4 = a1 + 9;
  WINRT_IMPL_AcquireSRWLockExclusive(a1 + 9);
  v5 = std::_Atomic_storage<unsigned int,4>::load(&a1[12], 0);
  try
  {
    winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Graphics::Capture::implementation::GraphicsCapturePicker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,void>::rethrow_if_failed(
      (__int64)a1,
      v5);
    *a2 = 0;
    ReleaseSRWLockExclusive_0(v4);
    result = a2;
  }
  catch ( ... )
  {
    winrt::to_hresult(a2);
    return a2;
  }
  return result;
}

```

## disassembly

```asm
0x180014968  mov     rax, rsp
0x18001496b  mov     [rax+18h], rbx
0x18001496f  mov     [rax+20h], rsi
0x180014973  mov     [rax+10h], rdx
0x180014977  push    rdi
0x180014978  sub     rsp, 20h
0x18001497c  mov     rbx, rdx
0x18001497f  mov     rsi, rcx
0x180014982  lea     rdi, [rcx+48h]
0x180014986  mov     [rax+8], rdi
0x18001498a  mov     rcx, rdi; SRWLock
0x18001498d  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180014992  nop
0x180014993  lea     rcx, [rsi+60h]
0x180014997  xor     edx, edx
0x180014999  call    ?load@?$_Atomic_storage@I$03@std@@QEBAIW4memory_order@2@@Z; std::_Atomic_storage<uint,4>::load(std::memory_order)
0x18001499e  mov     edx, eax
0x1800149a0  mov     rcx, rsi
0x1800149a3  call    ?rethrow_if_failed@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUGraphicsCapturePicker@implementation@Capture@Graphics@34@@experimental@std@@U?$IAsyncOperation@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@IEBAXW4AsyncStatus@Foundation@Windows@3@@Z; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Graphics::Capture::implementation::GraphicsCapturePicker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,void>::rethrow_if_failed(winrt::Windows::Foundation::AsyncStatus)
0x1800149a8  mov     dword ptr [rbx], 0
0x1800149ae  mov     rcx, rdi; SRWLock
0x1800149b1  call    ReleaseSRWLockExclusive_0
0x1800149b6  mov     rax, rbx
0x1800149b9  jmp     short loc_1800149C0
0x1800149bb  mov     rax, [rsp+28h+arg_8]
0x1800149c0  mov     rbx, [rsp+28h+arg_10]
0x1800149c5  mov     rsi, [rsp+28h+arg_18]
0x1800149ca  add     rsp, 20h
0x1800149ce  pop     rdi
0x1800149cf  retn
```
