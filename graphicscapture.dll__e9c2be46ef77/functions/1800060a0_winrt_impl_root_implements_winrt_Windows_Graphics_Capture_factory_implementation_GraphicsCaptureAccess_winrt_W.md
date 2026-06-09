# winrt::impl::root_implements<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureAccess,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Graphics::Capture::IGraphicsCaptureAccessStatics>::query_interface(winrt::guid const &,void * *)

- ea: `0x1800060a0`
- end: `0x1800060f3`
- name: `?query_interface@?$root_implements@UGraphicsCaptureAccess@factory_implementation@Capture@Graphics@Windows@winrt@@UIActivationFactory@Foundation@56@UIGraphicsCaptureAccessStatics@3456@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z`
- size: `83`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004f00`
- `0x180004f20`
- `0x180004f40`
- `0x180004f60`

## callees

- `0x180003ff0`
- `0x1800060a0`
- `0x180006234`
- `0x180028010`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureAccess,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Graphics::Capture::IGraphicsCaptureAccessStatics>::query_interface(
        __int64 a1,
        _QWORD *a2,
        __int64 *a3)
{
  __int64 v6; // rax

  v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 48LL))(a1);
  *a3 = v6;
  if ( !v6 )
    return winrt::impl::root_implements<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Graphics::RectInt32>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Graphics::RectInt32>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Graphics::RectInt32>>::query_interface_common(
             a1,
             a2,
             a3);
  winrt::impl::root_implements<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureAccess,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Graphics::Capture::IGraphicsCaptureAccessStatics>::AddRef(a1);
  return 0;
}

```

## disassembly

```asm
0x1800060a0  mov     [rsp+arg_0], rbx
0x1800060a5  mov     [rsp+arg_8], rsi
0x1800060aa  push    rdi
0x1800060ab  sub     rsp, 20h
0x1800060af  mov     rax, [rcx]
0x1800060b2  mov     rdi, r8
0x1800060b5  mov     rsi, rdx
0x1800060b8  mov     rbx, rcx
0x1800060bb  mov     rax, [rax+30h]
0x1800060bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060c4  mov     [rdi], rax
0x1800060c7  mov     rcx, rbx
0x1800060ca  test    rax, rax
0x1800060cd  jz      short loc_1800060D8
0x1800060cf  call    ?AddRef@?$root_implements@UGraphicsCaptureAccess@factory_implementation@Capture@Graphics@Windows@winrt@@UIActivationFactory@Foundation@56@UIGraphicsCaptureAccessStatics@3456@@impl@winrt@@QEAAIXZ; winrt::impl::root_implements<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureAccess,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Graphics::Capture::IGraphicsCaptureAccessStatics>::AddRef(void)
0x1800060d4  xor     eax, eax
0x1800060d6  jmp     short loc_1800060E3
0x1800060d8  mov     r8, rdi
0x1800060db  mov     rdx, rsi
0x1800060de  call    ?query_interface_common@?$root_implements@U?$vector_impl@URectInt32@Graphics@Windows@winrt@@V?$vector@URectInt32@Graphics@Windows@winrt@@V?$allocator@URectInt32@Graphics@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@4@@impl@winrt@@U?$IVector@URectInt32@Graphics@Windows@winrt@@@Collections@Foundation@Windows@3@U?$IVectorView@URectInt32@Graphics@Windows@winrt@@@5673@U?$IIterable@URectInt32@Graphics@Windows@winrt@@@5673@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z; winrt::impl::root_implements<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Graphics::RectInt32>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Graphics::RectInt32>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Graphics::RectInt32>>::query_interface_common(winrt::guid const &,void * *)
0x1800060e3  mov     rbx, [rsp+28h+arg_0]
0x1800060e8  mov     rsi, [rsp+28h+arg_8]
0x1800060ed  add     rsp, 20h
0x1800060f1  pop     rdi
0x1800060f2  retn
```
