# winrt::com_ptr<winrt::impl::vector_impl<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation,std::vector<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation,std::allocator<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref(void)

- ea: `0x1800222dc`
- end: `0x180022314`
- name: `?unconditional_release_ref@?$com_ptr@U?$vector_impl@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@V?$vector@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@V?$allocator@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@6@@impl@winrt@@@winrt@@AEAAXXZ`
- size: `56`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f4a0`
- `0x180022a88`
- `0x180022ae8`
- `0x180023f40`

## callees

- `0x180006494`
- `0x1800222dc`
- `0x180028010`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<winrt::impl::vector_impl<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation,std::vector<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref(
        _QWORD **a1)
{
  _QWORD *v1; // rbx
  __int64 result; // rax

  v1 = *a1;
  *a1 = 0;
  result = winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::weak_ref<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>::promise_type,winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Foundation::IAsyncInfo>::subtract_final_reference(v1);
  if ( !(_DWORD)result )
  {
    v1[1] = 1;
    return (*(__int64 (__fastcall **)(_QWORD *))(*v1 + 8LL))(v1);
  }
  return result;
}

```

## disassembly

```asm
0x1800222dc  push    rbx
0x1800222de  sub     rsp, 20h
0x1800222e2  mov     rbx, [rcx]
0x1800222e5  mov     qword ptr [rcx], 0
0x1800222ec  mov     rcx, rbx
0x1800222ef  call    ?subtract_final_reference@?$root_implements@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@U?$weak_ref@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@4@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@UIAsyncInfo@678@@impl@winrt@@IEAAIXZ; winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::weak_ref<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>::promise_type,winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Foundation::IAsyncInfo>::subtract_final_reference(void)
0x1800222f4  test    eax, eax
0x1800222f6  jnz     short loc_18002230E
0x1800222f8  lea     edx, [rax+1]
0x1800222fb  mov     rcx, rbx
0x1800222fe  mov     [rbx+8], rdx
0x180022302  mov     rax, [rbx]
0x180022305  mov     rax, [rax+8]
0x180022309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002230e  add     rsp, 20h
0x180022312  pop     rbx
0x180022313  retn
```
