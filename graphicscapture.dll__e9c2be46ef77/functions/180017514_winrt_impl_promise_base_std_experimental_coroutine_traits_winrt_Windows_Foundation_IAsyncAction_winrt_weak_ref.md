# winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::weak_ref<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::weak_ref<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>(void)

- ea: `0x180017514`
- end: `0x1800175a2`
- name: `??0?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@U?$weak_ref@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@4@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@QEAA@XZ`
- size: `142`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18001a24c`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180017573`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180017573`

## pseudocode

```c
__int64 __fastcall winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::weak_ref<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::weak_ref<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>(
        __int64 a1)
{
  _QWORD *v2; // rcx

  *(_QWORD *)(a1 + 16) = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::weak_ref<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>::promise_type,winrt::Windows::Foundation::IAsyncAction>::`vftable';
  *(_QWORD *)(a1 + 24) = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::weak_ref<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::weak_ref<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>::promise_type::`vftable';
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_BYTE *)(a1 + 48) = 0;
  v2 = (_QWORD *)(a1 + 56);
  *v2 = 0;
  v2[1] = 0;
  __ExceptionPtrCreate(v2);
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_DWORD *)(a1 + 96) = 0;
  *(_BYTE *)(a1 + 100) = 0;
  return a1;
}

```

## disassembly

```asm
0x180017514  push    rbx
0x180017516  sub     rsp, 20h
0x18001751a  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@U?$weak_ref@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@4@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::weak_ref<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>::promise_type,winrt::Windows::Foundation::IAsyncAction>::`vftable'
0x180017521  mov     rbx, rcx
0x180017524  mov     [rcx+10h], rax
0x180017528  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@U?$weak_ref@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@4@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@experimental@std@@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::weak_ref<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable'
0x18001752f  mov     [rcx+18h], rax
0x180017533  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001753a  lea     rax, ??_7promise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@U?$weak_ref@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@4@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@experimental@std@@6B@; const std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::weak_ref<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>::promise_type::`vftable'
0x180017541  mov     qword ptr [rcx+8], 1
0x180017549  mov     [rcx], rax
0x18001754c  mov     qword ptr [rcx+20h], 0
0x180017554  mov     qword ptr [rcx+28h], 0
0x18001755c  mov     byte ptr [rcx+30h], 0
0x180017560  add     rcx, 38h ; '8'
0x180017564  mov     qword ptr [rcx], 0
0x18001756b  mov     qword ptr [rcx+8], 0
0x180017573  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180017579  xor     eax, eax
0x18001757b  mov     qword ptr [rbx+48h], 0
0x180017583  mov     qword ptr [rbx+50h], 0
0x18001758b  mov     qword ptr [rbx+58h], 0
0x180017593  mov     [rbx+60h], eax
0x180017596  mov     [rbx+64h], al
0x180017599  mov     rax, rbx
0x18001759c  add     rsp, 20h
0x1800175a0  pop     rbx
0x1800175a1  retn
```
