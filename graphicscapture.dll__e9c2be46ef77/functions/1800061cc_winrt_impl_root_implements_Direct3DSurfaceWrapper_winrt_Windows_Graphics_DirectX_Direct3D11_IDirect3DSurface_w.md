# winrt::impl::root_implements<Direct3DSurfaceWrapper,winrt::Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface,winrt::cloaked<Windows::Graphics::DirectX::Direct3D11::IDirect3DDxgiInterfaceAccess>>::query_interface(winrt::guid const &,void * *)

- ea: `0x1800061cc`
- end: `0x18000622b`
- name: `?query_interface@?$root_implements@UDirect3DSurfaceWrapper@@UIDirect3DSurface@Direct3D11@DirectX@Graphics@Windows@winrt@@U?$cloaked@UIDirect3DDxgiInterfaceAccess@Direct3D11@DirectX@Graphics@Windows@@@7@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004ef0`

## callees

- `0x180003ff0`
- `0x1800061cc`
- `0x180006234`
- `0x180028010`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<Direct3DSurfaceWrapper,winrt::Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface,winrt::cloaked<Windows::Graphics::DirectX::Direct3D11::IDirect3DDxgiInterfaceAccess>>::query_interface(
        __int64 a1,
        _QWORD *a2,
        __int64 *a3)
{
  __int64 v3; // rbx
  __int64 v6; // rax

  v3 = a1;
  if ( !a1 )
    a1 = 16;
  v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 48LL))(a1);
  *a3 = v6;
  if ( !v6 )
    return winrt::impl::root_implements<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Graphics::RectInt32>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Graphics::RectInt32>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Graphics::RectInt32>>::query_interface_common(
             v3,
             a2,
             a3);
  winrt::impl::root_implements<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureAccess,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Graphics::Capture::IGraphicsCaptureAccessStatics>::AddRef(v3);
  return 0;
}

```

## disassembly

```asm
0x1800061cc  mov     [rsp+arg_0], rbx
0x1800061d1  mov     [rsp+arg_8], rsi
0x1800061d6  push    rdi
0x1800061d7  sub     rsp, 20h
0x1800061db  test    rcx, rcx
0x1800061de  mov     eax, 10h
0x1800061e3  mov     rbx, rcx
0x1800061e6  mov     rdi, r8
0x1800061e9  cmovz   rcx, rax
0x1800061ed  mov     rsi, rdx
0x1800061f0  mov     rax, [rcx]
0x1800061f3  mov     rax, [rax+30h]
0x1800061f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061fc  mov     [rdi], rax
0x1800061ff  mov     rcx, rbx
0x180006202  test    rax, rax
0x180006205  jz      short loc_180006210
0x180006207  call    ?AddRef@?$root_implements@UGraphicsCaptureAccess@factory_implementation@Capture@Graphics@Windows@winrt@@UIActivationFactory@Foundation@56@UIGraphicsCaptureAccessStatics@3456@@impl@winrt@@QEAAIXZ; winrt::impl::root_implements<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureAccess,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Graphics::Capture::IGraphicsCaptureAccessStatics>::AddRef(void)
0x18000620c  xor     eax, eax
0x18000620e  jmp     short loc_18000621B
0x180006210  mov     r8, rdi
0x180006213  mov     rdx, rsi
0x180006216  call    ?query_interface_common@?$root_implements@U?$vector_impl@URectInt32@Graphics@Windows@winrt@@V?$vector@URectInt32@Graphics@Windows@winrt@@V?$allocator@URectInt32@Graphics@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@4@@impl@winrt@@U?$IVector@URectInt32@Graphics@Windows@winrt@@@Collections@Foundation@Windows@3@U?$IVectorView@URectInt32@Graphics@Windows@winrt@@@5673@U?$IIterable@URectInt32@Graphics@Windows@winrt@@@5673@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z; winrt::impl::root_implements<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Graphics::RectInt32>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Graphics::RectInt32>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Graphics::RectInt32>>::query_interface_common(winrt::guid const &,void * *)
0x18000621b  mov     rbx, [rsp+28h+arg_0]
0x180006220  mov     rsi, [rsp+28h+arg_8]
0x180006225  add     rsp, 20h
0x180006229  pop     rdi
0x18000622a  retn
```
