# winrt::impl::invoke<winrt::Windows::Foundation::AsyncActionCompletedHandler,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::weak_ref<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>,winrt::Windows::Foundation::AsyncStatus>(winrt::Windows::Foundation::AsyncActionCompletedHandler const &,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::weak_ref<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>::promise_type,winrt::Windows::Foundation::IAsyncAction,void> const &,winrt::Windows::Foundation::AsyncStatus const &)

- ea: `0x180013da4`
- end: `0x180013ddd`
- name: `??$invoke@UAsyncActionCompletedHandler@Foundation@Windows@winrt@@U?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@U?$weak_ref@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@4@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@4@W4AsyncStatus@234@@impl@winrt@@YA_NAEBUAsyncActionCompletedHandler@Foundation@Windows@1@AEBU?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@U?$weak_ref@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@4@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@01@AEBW4AsyncStatus@341@@Z`
- size: `57`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180014898`
- `0x1800154fc`
- `0x180018270`
- `0x18001a5f0`
- `0x18001b98c`

## callees

- `0x180003580`
- `0x180013da4`
- `0x180014598`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall winrt::impl::invoke<winrt::Windows::Foundation::AsyncActionCompletedHandler,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::weak_ref<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>,enum winrt::Windows::Foundation::AsyncStatus>(
        __int64 a1,
        __int64 a2)
{
  winrt::impl *v2; // rcx
  bool result; // al
  __int64 v4; // [rsp+38h] [rbp+10h] BYREF

  v4 = a2 + 16;
  try
  {
    winrt::Windows::Foundation::AsyncActionCompletedHandler::operator()();
    v4 = 0;
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v4);
    result = 1;
  }
  catch ( ... )
  {
    return winrt::impl::report_failed_invoke(v2);
  }
  return result;
}

```

## disassembly

```asm
0x180013da4  sub     rsp, 28h
0x180013da8  lea     rax, [rdx+10h]
0x180013dac  mov     [rsp+28h+arg_8], rax
0x180013db1  lea     rdx, [rsp+28h+arg_8]
0x180013db6  call    ??RAsyncActionCompletedHandler@Foundation@Windows@winrt@@QEBA@AEBUIAsyncAction@123@AEBW4AsyncStatus@123@@Z; winrt::Windows::Foundation::AsyncActionCompletedHandler::operator()(winrt::Windows::Foundation::IAsyncAction const &,winrt::Windows::Foundation::AsyncStatus const &)
0x180013dbb  nop
0x180013dbc  mov     [rsp+28h+arg_8], 0
0x180013dc5  lea     rcx, [rsp+28h+arg_8]
0x180013dca  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180013dcf  nop
0x180013dd0  mov     al, 1
0x180013dd2  jmp     short loc_180013DD8
0x180013dd4  mov     al, byte ptr [rsp+28h+arg_8]
0x180013dd8  add     rsp, 28h
0x180013ddc  retn
```
