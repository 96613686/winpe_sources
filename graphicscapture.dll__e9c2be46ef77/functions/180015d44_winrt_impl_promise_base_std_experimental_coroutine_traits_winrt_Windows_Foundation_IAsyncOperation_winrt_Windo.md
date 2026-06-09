# winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Graphics::Capture::implementation::GraphicsCapturePicker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,void>::rethrow_if_failed(winrt::Windows::Foundation::AsyncStatus)

- ea: `0x180015d44`
- end: `0x180015d83`
- name: `?rethrow_if_failed@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUGraphicsCapturePicker@implementation@Capture@Graphics@34@@experimental@std@@U?$IAsyncOperation@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@IEBAXW4AsyncStatus@Foundation@Windows@3@@Z`
- size: `63`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180014968`
- `0x180014b54`
- `0x18001bae4`

## callees

- `0x180015d44`

## import_xrefs

- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180015d77`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180015d77`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180015d62`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180015d62`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Graphics::Capture::implementation::GraphicsCapturePicker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,void>::rethrow_if_failed(
        __int64 a1,
        int a2)
{
  __int128 v2; // [rsp+20h] [rbp-18h] BYREF

  if ( (unsigned int)(a2 - 2) <= 1 )
  {
    v2 = 0;
    __ExceptionPtrCopy(&v2, (const void *)(a1 + 56));
    __ExceptionPtrRethrow(&v2);
  }
}

```

## disassembly

```asm
0x180015d44  sub     rsp, 38h
0x180015d48  lea     eax, [rdx-2]
0x180015d4b  cmp     eax, 1
0x180015d4e  ja      short loc_180015D7E
0x180015d50  xorps   xmm0, xmm0
0x180015d53  movdqu  [rsp+38h+var_18], xmm0
0x180015d59  lea     rdx, [rcx+38h]
0x180015d5d  lea     rcx, [rsp+38h+var_18]
0x180015d62  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180015d68  lea     rax, [rsp+38h+var_18]
0x180015d6d  mov     [rsp+38h+arg_10], rax
0x180015d72  lea     rcx, [rsp+38h+var_18]
0x180015d77  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x180015d7d  nop
0x180015d7e  add     rsp, 38h
0x180015d82  retn
```
