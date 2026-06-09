# winrt::impl::root_implements<winrt::impl::vector_impl<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation,std::vector<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation,std::allocator<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>>::NonDelegatingGetRuntimeClassName(void * *)

- ea: `0x180004cc0`
- end: `0x180004d00`
- name: `?NonDelegatingGetRuntimeClassName@?$root_implements@U?$vector_impl@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@V?$vector@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@V?$allocator@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@6@@impl@winrt@@U?$IVector@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@@Collections@Foundation@Windows@3@U?$IVectorView@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@@5673@U?$IIterable@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@@5673@@impl@winrt@@IEAAHPEAPEAX@Z`
- size: `64`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x1800048d0`
- `0x1800048f0`
- `0x180004910`
- `0x180004930`
- `0x1800219c8`

## callees

- `0x180004cc0`
- `0x180005834`
- `0x180028010`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<winrt::impl::vector_impl<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation,std::vector<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>>::NonDelegatingGetRuntimeClassName(
        __int64 a1,
        _QWORD *a2)
{
  __int64 *v3; // rax
  __int64 v4; // rcx
  __int64 result; // rax
  int v6; // [rsp+30h] [rbp+8h] BYREF

  try
  {
    v3 = (__int64 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
    v4 = *v3;
    *v3 = 0;
    *a2 = v4;
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v6);
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v6);
  }
  return result;
}

```

## disassembly

```asm
0x180004cc0  push    rbx
0x180004cc2  sub     rsp, 20h
0x180004cc6  mov     rbx, rdx
0x180004cc9  mov     rax, [rcx]
0x180004ccc  lea     rdx, [rsp+28h+arg_0]
0x180004cd1  mov     rax, [rax+28h]
0x180004cd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cda  mov     rcx, [rax]
0x180004cdd  mov     qword ptr [rax], 0
0x180004ce4  mov     [rbx], rcx
0x180004ce7  lea     rcx, [rsp+28h+arg_0]
0x180004cec  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180004cf1  xor     eax, eax
0x180004cf3  jmp     short loc_180004CF9
0x180004cf5  mov     eax, [rsp+28h+arg_0]
0x180004cf9  add     rsp, 20h
0x180004cfd  pop     rbx
0x180004cfe  retn
```
