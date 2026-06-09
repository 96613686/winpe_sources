# winrt::impl::root_implements<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32,std::allocator<winrt::Windows::Graphics::RectInt32>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Graphics::RectInt32>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Graphics::RectInt32>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Graphics::RectInt32>>::query_interface_common(winrt::guid const &,void * *)

- ea: `0x180006234`
- end: `0x180006331`
- name: `?query_interface_common@?$root_implements@U?$vector_impl@URectInt32@Graphics@Windows@winrt@@V?$vector@URectInt32@Graphics@Windows@winrt@@V?$allocator@URectInt32@Graphics@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@4@@impl@winrt@@U?$IVector@URectInt32@Graphics@Windows@winrt@@@Collections@Foundation@Windows@3@U?$IVectorView@URectInt32@Graphics@Windows@winrt@@@5673@U?$IIterable@URectInt32@Graphics@Windows@winrt@@@5673@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z`
- size: `253`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800060a0`
- `0x1800060fc`
- `0x1800061cc`
- `0x1800159a4`
- `0x18001c094`

## callees

- `0x180003ff0`
- `0x180005d68`
- `0x180005e08`
- `0x180006234`
- `0x180028010`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Graphics::RectInt32>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Graphics::RectInt32>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Graphics::RectInt32>>::query_interface_common(
        __int64 a1,
        _QWORD *a2,
        __int64 *a3)
{
  __int64 (*v5)(void); // rax
  __int64 weak_ref; // rax
  __int64 v8; // rax
  __int64 (**v9)(void); // r9
  __int64 v10; // rax

  if ( *a2 == winrt::impl::guid_v<winrt::Windows::Foundation::IUnknown> && a2[1] == 0x46000000000000C0LL )
    goto LABEL_3;
  if ( *a2 == winrt::impl::guid_v<winrt::Windows::Foundation::IInspectable> && a2[1] == 0x901E1065AAD75A9CuLL )
  {
    v5 = *(__int64 (**)(void))(*(_QWORD *)a1 + 56LL);
    goto LABEL_4;
  }
  if ( *a2 == winrt::impl::guid_v<winrt::impl::IWeakReferenceSource> && a2[1] == 0x46000000000000C0LL )
  {
    weak_ref = winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Graphics::Capture::implementation::GraphicsCapturePicker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Foundation::IAsyncInfo>::make_weak_ref();
    *a3 = weak_ref;
    return weak_ref == 0 ? 0x8007000E : 0;
  }
  else
  {
    if ( *a2 == winrt::impl::guid_v<winrt::impl::IAgileObject> && a2[1] == 0x905B8FCA64EEFFC0uLL )
    {
LABEL_3:
      v5 = *(__int64 (**)(void))(*(_QWORD *)a1 + 24LL);
LABEL_4:
      *a3 = v5();
      winrt::impl::root_implements<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureAccess,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Graphics::Capture::IGraphicsCaptureAccessStatics>::AddRef(a1);
      return 0;
    }
    v8 = *a2 - winrt::impl::guid_v<winrt::impl::IMarshal>;
    if ( *a2 == winrt::impl::guid_v<winrt::impl::IMarshal> )
      v8 = a2[1] - 0x46000000000000C0LL;
    v9 = *(__int64 (***)(void))a1;
    if ( v8 )
    {
      return (*v9)();
    }
    else
    {
      v10 = v9[3]();
      return winrt::impl::make_marshaler(v10, a3);
    }
  }
}

```

## disassembly

```asm
0x180006234  mov     [rsp+arg_0], rbx
0x180006239  push    rdi
0x18000623a  sub     rsp, 20h
0x18000623e  mov     rax, [rdx]
0x180006241  mov     rdi, r8
0x180006244  cmp     rax, cs:??$guid_v@UIUnknown@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IUnknown>
0x18000624b  mov     rbx, rcx
0x18000624e  jnz     short loc_18000627B
0x180006250  mov     rax, [rdx+8]
0x180006254  cmp     rax, cs:qword_18002C738
0x18000625b  jnz     short loc_18000627B
0x18000625d  mov     rax, [rcx]
0x180006260  mov     rax, [rax+18h]
0x180006264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006269  mov     rcx, rbx
0x18000626c  mov     [rdi], rax
0x18000626f  call    ?AddRef@?$root_implements@UGraphicsCaptureAccess@factory_implementation@Capture@Graphics@Windows@winrt@@UIActivationFactory@Foundation@56@UIGraphicsCaptureAccessStatics@3456@@impl@winrt@@QEAAIXZ; winrt::impl::root_implements<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureAccess,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Graphics::Capture::IGraphicsCaptureAccessStatics>::AddRef(void)
0x180006274  xor     eax, eax
0x180006276  jmp     loc_180006326
0x18000627b  mov     rax, [rdx]
0x18000627e  cmp     rax, cs:??$guid_v@UIInspectable@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IInspectable>
0x180006285  jnz     short loc_18000629D
0x180006287  mov     rax, [rdx+8]
0x18000628b  cmp     rax, cs:qword_18002C6F8
0x180006292  jnz     short loc_18000629D
0x180006294  mov     rax, [rcx]
0x180006297  mov     rax, [rax+38h]
0x18000629b  jmp     short loc_180006264
0x18000629d  mov     rax, [rdx]
0x1800062a0  cmp     rax, cs:??$guid_v@UIWeakReferenceSource@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IWeakReferenceSource>
0x1800062a7  jnz     short loc_1800062CC
0x1800062a9  mov     rax, [rdx+8]
0x1800062ad  cmp     rax, cs:qword_18002C718
0x1800062b4  jnz     short loc_1800062CC
0x1800062b6  call    ?make_weak_ref@?$root_implements@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUGraphicsCapturePicker@implementation@Capture@Graphics@34@@experimental@std@@U?$IAsyncOperation@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@UIAsyncInfo@678@@impl@winrt@@AEAAPEAUIWeakReferenceSource@23@XZ; winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Graphics::Capture::implementation::GraphicsCapturePicker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Foundation::IAsyncInfo>::make_weak_ref(void)
0x1800062bb  mov     [rdi], rax
0x1800062be  neg     rax
0x1800062c1  sbb     eax, eax
0x1800062c3  not     eax
0x1800062c5  and     eax, 8007000Eh
0x1800062ca  jmp     short loc_180006326
0x1800062cc  mov     rax, [rdx]
0x1800062cf  cmp     rax, cs:??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x1800062d6  jnz     short loc_1800062E9
0x1800062d8  mov     rax, [rdx+8]
0x1800062dc  cmp     rax, cs:qword_18002C888
0x1800062e3  jz      loc_18000625D
0x1800062e9  mov     rax, [rdx]
0x1800062ec  sub     rax, cs:??$guid_v@UIMarshal@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IMarshal>
0x1800062f3  jnz     short loc_180006300
0x1800062f5  mov     rax, [rdx+8]
0x1800062f9  sub     rax, cs:qword_18002C728
0x180006300  mov     r9, [rcx]
0x180006303  test    rax, rax
0x180006306  jnz     short loc_18000631E
0x180006308  mov     rax, [r9+18h]
0x18000630c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006311  mov     rcx, rax
0x180006314  mov     rdx, rdi
0x180006317  call    ?make_marshaler@impl@winrt@@YAHPEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@12@PEAPEAX@Z; winrt::impl::make_marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *,void * *)
0x18000631c  jmp     short loc_180006326
0x18000631e  mov     rax, [r9]
0x180006321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006326  mov     rbx, [rsp+28h+arg_0]
0x18000632b  add     rsp, 20h
0x18000632f  pop     rdi
0x180006330  retn
```
