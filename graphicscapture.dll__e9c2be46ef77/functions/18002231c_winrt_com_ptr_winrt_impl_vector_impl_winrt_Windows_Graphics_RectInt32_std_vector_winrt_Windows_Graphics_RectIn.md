# winrt::com_ptr<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32,std::allocator<winrt::Windows::Graphics::RectInt32>>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref(void)

- ea: `0x18002231c`
- end: `0x180022360`
- name: `?unconditional_release_ref@?$com_ptr@U?$vector_impl@URectInt32@Graphics@Windows@winrt@@V?$vector@URectInt32@Graphics@Windows@winrt@@V?$allocator@URectInt32@Graphics@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@4@@impl@winrt@@@winrt@@AEAAXXZ`
- size: `68`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001f4cc`

## callees

- `0x18000644c`
- `0x18000645c`
- `0x18002231c`
- `0x180028010`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref(
        __int64 *a1)
{
  __int64 v1; // rbx
  __int64 result; // rax

  v1 = *a1;
  *a1 = 0;
  result = winrt::impl::root_implements<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureSession,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Graphics::Capture::IGraphicsCaptureSessionStatics>::subtract_final_reference(v1);
  if ( !(_DWORD)result )
  {
    result = std::_Atomic_storage<unsigned __int64,8>::store(v1 + 8);
    if ( v1 )
      return (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v1 + 8LL))(v1, 1);
  }
  return result;
}

```

## disassembly

```asm
0x18002231c  push    rbx
0x18002231e  sub     rsp, 20h
0x180022322  mov     rbx, [rcx]
0x180022325  mov     qword ptr [rcx], 0
0x18002232c  mov     rcx, rbx
0x18002232f  call    ?subtract_final_reference@?$root_implements@UGraphicsCaptureSession@factory_implementation@Capture@Graphics@Windows@winrt@@UIActivationFactory@Foundation@56@UIGraphicsCaptureSessionStatics@3456@@impl@winrt@@IEAAIXZ; winrt::impl::root_implements<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureSession,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Graphics::Capture::IGraphicsCaptureSessionStatics>::subtract_final_reference(void)
0x180022334  test    eax, eax
0x180022336  jnz     short loc_18002235A
0x180022338  lea     rcx, [rbx+8]
0x18002233c  call    ?store@?$_Atomic_storage@_K$07@std@@QEAAX_KW4memory_order@2@@Z; std::_Atomic_storage<unsigned __int64,8>::store(unsigned __int64,std::memory_order)
0x180022341  test    rbx, rbx
0x180022344  jz      short loc_18002235A
0x180022346  mov     rax, [rbx]
0x180022349  mov     edx, 1
0x18002234e  mov     rcx, rbx
0x180022351  mov     rax, [rax+8]
0x180022355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002235a  add     rsp, 20h
0x18002235e  pop     rbx
0x18002235f  retn
```
