# std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Graphics::Capture::implementation::GraphicsCapturePicker *>::promise_type::promise_type(void)

- ea: `0x180014214`
- end: `0x1800142ac`
- name: `??0promise_type@?$coroutine_traits@U?$IAsyncOperation@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUGraphicsCapturePicker@implementation@Capture@Graphics@34@@experimental@std@@QEAA@XZ`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180015194`

## callees

- `0x180002da8`
- `0x1800134a4`
- `0x1800140fc`
- `0x180014120`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180014266`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180014266`

## pseudocode

```c
__int64 __fastcall std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Graphics::Capture::implementation::GraphicsCapturePicker *>::promise_type::promise_type(
        __int64 a1)
{
  __int64 result; // rax

  winrt::impl::producers_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Graphics::Capture::implementation::GraphicsCapturePicker *>::promise_type,std::tuple<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Foundation::IAsyncInfo>>::producers_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Graphics::Capture::implementation::GraphicsCapturePicker *>::promise_type,std::tuple<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Foundation::IAsyncInfo>>(a1 + 16);
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  std::atomic<unsigned __int64>::atomic<unsigned __int64>(a1 + 8);
  *(_QWORD *)a1 = &winrt::implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Graphics::Capture::implementation::GraphicsCapturePicker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Foundation::IAsyncInfo>::`vftable';
  winrt::cancellable_promise::cancellable_promise((winrt::cancellable_promise *)(a1 + 32));
  *(_QWORD *)a1 = &winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Graphics::Capture::implementation::GraphicsCapturePicker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,void>::`vftable';
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  __ExceptionPtrCreate((void *)(a1 + 56));
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  std::atomic<unsigned int>::atomic<unsigned int>(a1 + 96);
  *(_BYTE *)(a1 + 100) = 0;
  *(_QWORD *)a1 = &std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Graphics::Capture::implementation::GraphicsCapturePicker *>::promise_type::`vftable';
  result = a1;
  *(_QWORD *)(a1 + 104) = 0;
  return result;
}

```

## disassembly

```asm
0x180014214  push    rbx
0x180014216  sub     rsp, 20h
0x18001421a  mov     rbx, rcx
0x18001421d  add     rcx, 10h
0x180014221  call    ??0?$producers_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUGraphicsCapturePicker@implementation@Capture@Graphics@34@@experimental@std@@V?$tuple@U?$IAsyncOperation@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@UIAsyncInfo@234@@4@@impl@winrt@@QEAA@XZ; winrt::impl::producers_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Graphics::Capture::implementation::GraphicsCapturePicker *>::promise_type,std::tuple<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Foundation::IAsyncInfo>>::producers_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Graphics::Capture::implementation::GraphicsCapturePicker *>::promise_type,std::tuple<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Foundation::IAsyncInfo>>(void)
0x180014226  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001422d  lea     rcx, [rbx+8]
0x180014231  call    ??0?$atomic@_K@std@@QEAA@_K@Z; std::atomic<unsigned __int64>::atomic<unsigned __int64>(unsigned __int64)
0x180014236  lea     rcx, ??_7?$implements@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUGraphicsCapturePicker@implementation@Capture@Graphics@34@@experimental@std@@U?$IAsyncOperation@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@UIAsyncInfo@678@@winrt@@6B@; const winrt::implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Graphics::Capture::implementation::GraphicsCapturePicker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Foundation::IAsyncInfo>::`vftable'
0x18001423d  mov     [rbx], rcx
0x180014240  lea     rcx, [rbx+20h]; this
0x180014244  call    ??0cancellable_promise@winrt@@QEAA@XZ; winrt::cancellable_promise::cancellable_promise(void)
0x180014249  lea     rcx, ??_7?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUGraphicsCapturePicker@implementation@Capture@Graphics@34@@experimental@std@@U?$IAsyncOperation@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Graphics::Capture::implementation::GraphicsCapturePicker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,void>::`vftable'
0x180014250  mov     [rbx], rcx
0x180014253  lea     rcx, [rbx+38h]
0x180014257  mov     qword ptr [rcx], 0
0x18001425e  mov     qword ptr [rcx+8], 0
0x180014266  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18001426c  mov     qword ptr [rbx+48h], 0
0x180014274  lea     rcx, [rbx+60h]
0x180014278  mov     qword ptr [rbx+50h], 0
0x180014280  mov     qword ptr [rbx+58h], 0
0x180014288  call    ??$?0I$0A@@?$atomic@I@std@@QEAA@XZ; std::atomic<uint>::atomic<uint>(void)
0x18001428d  lea     rax, ??_7promise_type@?$coroutine_traits@U?$IAsyncOperation@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUGraphicsCapturePicker@implementation@Capture@Graphics@34@@experimental@std@@6B@; const std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Graphics::Capture::implementation::GraphicsCapturePicker *>::promise_type::`vftable'
0x180014294  mov     byte ptr [rbx+64h], 0
0x180014298  mov     [rbx], rax
0x18001429b  mov     rax, rbx
0x18001429e  mov     qword ptr [rbx+68h], 0
0x1800142a6  add     rsp, 20h
0x1800142aa  pop     rbx
0x1800142ab  retn
```
