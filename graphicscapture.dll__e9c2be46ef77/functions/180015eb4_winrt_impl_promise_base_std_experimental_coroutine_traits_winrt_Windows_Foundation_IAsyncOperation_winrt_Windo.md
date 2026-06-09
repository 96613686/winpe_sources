# winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Graphics::Capture::implementation::GraphicsCapturePicker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,void>::unhandled_exception(void)

- ea: `0x180015eb4`
- end: `0x180015f37`
- name: `?unhandled_exception@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUGraphicsCapturePicker@implementation@Capture@Graphics@34@@experimental@std@@U?$IAsyncOperation@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEAAXXZ`
- size: `131`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180026645`
- `0x180026fba`

## callees

- `0x180002384`
- `0x180002390`
- `0x1800156f8`
- `0x180015eb4`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180015ef1`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180015ef1`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180015f1f`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180015f1f`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180015f0a`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180015f0a`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180015ee6`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180015ee6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Graphics::Capture::implementation::GraphicsCapturePicker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,void>::unhandled_exception(
        RTL_SRWLOCK *a1)
{
  const void *v2; // rax
  __int128 v3; // [rsp+20h] [rbp-18h] BYREF
  RTL_SRWLOCK *SRWLock; // [rsp+48h] [rbp+10h]

  SRWLock = a1 + 9;
  WINRT_IMPL_AcquireSRWLockExclusive(a1 + 9);
  v2 = (const void *)std::current_exception(&v3);
  __ExceptionPtrAssign(&a1[7], v2);
  __ExceptionPtrDestroy(&v3);
  v3 = 0;
  __ExceptionPtrCopy(&v3, &a1[7]);
  try
  {
    __ExceptionPtrRethrow(&v3);
  }
  catch ( winrt::hresult_canceled )
  {
    std::_Atomic_storage<enum winrt::Windows::Foundation::AsyncStatus,4>::store(&a1[12], 2);
  }
  catch ( ... )
  {
    std::_Atomic_storage<enum winrt::Windows::Foundation::AsyncStatus,4>::store(&a1[12], 3);
  }
  ReleaseSRWLockExclusive_0(SRWLock);
}

```

## disassembly

```asm
0x180015eb4  mov     [rsp+arg_0], rcx
0x180015eb9  push    rbx
0x180015eba  sub     rsp, 30h
0x180015ebe  mov     rbx, rcx
0x180015ec1  add     rcx, 48h ; 'H'; SRWLock
0x180015ec5  mov     [rsp+38h+SRWLock], rcx
0x180015eca  mov     [rsp+38h+arg_10], rcx
0x180015ecf  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180015ed4  nop
0x180015ed5  lea     rcx, [rsp+38h+var_18]
0x180015eda  call    ?current_exception@std@@YA?AVexception_ptr@1@XZ; std::current_exception(void)
0x180015edf  mov     rdx, rax
0x180015ee2  lea     rcx, [rbx+38h]
0x180015ee6  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x180015eec  lea     rcx, [rsp+38h+var_18]
0x180015ef1  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180015ef7  nop
0x180015ef8  xorps   xmm0, xmm0
0x180015efb  movdqu  [rsp+38h+var_18], xmm0
0x180015f01  lea     rdx, [rbx+38h]
0x180015f05  lea     rcx, [rsp+38h+var_18]
0x180015f0a  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180015f10  lea     rax, [rsp+38h+var_18]
0x180015f15  mov     [rsp+38h+arg_18], rax
0x180015f1a  lea     rcx, [rsp+38h+var_18]
0x180015f1f  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x180015f25  nop
0x180015f26  jmp     short $+2
0x180015f28  mov     rcx, [rsp+38h+SRWLock]; SRWLock
0x180015f2d  add     rsp, 30h
0x180015f31  pop     rbx
0x180015f32  jmp     ReleaseSRWLockExclusive_0
```
