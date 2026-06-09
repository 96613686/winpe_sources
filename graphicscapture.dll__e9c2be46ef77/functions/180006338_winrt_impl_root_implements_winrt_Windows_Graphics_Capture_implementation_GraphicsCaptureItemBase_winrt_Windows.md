# winrt::impl::root_implements<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase,winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::cloaked<winrt::Windows::Graphics::Capture::implementation::IFireClosedEvent>>::query_interface_common(winrt::guid const &,void * *)

- ea: `0x180006338`
- end: `0x180006435`
- name: `?query_interface_common@?$root_implements@UGraphicsCaptureItemBase@implementation@Capture@Graphics@Windows@winrt@@UGraphicsCaptureItem@3456@U?$cloaked@UIFireClosedEvent@implementation@Capture@Graphics@Windows@winrt@@@6@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z`
- size: `253`
- prototype: ``
- caller_count: `9`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180006164`
- `0x18001afc4`
- `0x18001b02c`
- `0x18001deb0`
- `0x180020d40`
- `0x180020da0`
- `0x180020e10`
- `0x180020e80`
- `0x18002261c`

## callees

- `0x180004038`
- `0x180005d68`
- `0x180005e08`
- `0x180006338`
- `0x180028010`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase,winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::cloaked<winrt::Windows::Graphics::Capture::implementation::IFireClosedEvent>>::query_interface_common(
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
      winrt::impl::root_implements<winrt::impl::vector_impl<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation,std::vector<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>>::AddRef(a1);
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
0x180006338  mov     [rsp+arg_0], rbx
0x18000633d  push    rdi
0x18000633e  sub     rsp, 20h
0x180006342  mov     rax, [rdx]
0x180006345  mov     rdi, r8
0x180006348  cmp     rax, cs:??$guid_v@UIUnknown@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IUnknown>
0x18000634f  mov     rbx, rcx
0x180006352  jnz     short loc_18000637F
0x180006354  mov     rax, [rdx+8]
0x180006358  cmp     rax, cs:qword_18002C738
0x18000635f  jnz     short loc_18000637F
0x180006361  mov     rax, [rcx]
0x180006364  mov     rax, [rax+18h]
0x180006368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000636d  mov     rcx, rbx
0x180006370  mov     [rdi], rax
0x180006373  call    ?AddRef@?$root_implements@U?$vector_impl@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@V?$vector@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@V?$allocator@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@6@@impl@winrt@@U?$IVector@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@@Collections@Foundation@Windows@3@U?$IVectorView@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@@5673@U?$IIterable@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@@5673@@impl@winrt@@QEAAIXZ; winrt::impl::root_implements<winrt::impl::vector_impl<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation,std::vector<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>>::AddRef(void)
0x180006378  xor     eax, eax
0x18000637a  jmp     loc_18000642A
0x18000637f  mov     rax, [rdx]
0x180006382  cmp     rax, cs:??$guid_v@UIInspectable@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IInspectable>
0x180006389  jnz     short loc_1800063A1
0x18000638b  mov     rax, [rdx+8]
0x18000638f  cmp     rax, cs:qword_18002C6F8
0x180006396  jnz     short loc_1800063A1
0x180006398  mov     rax, [rcx]
0x18000639b  mov     rax, [rax+38h]
0x18000639f  jmp     short loc_180006368
0x1800063a1  mov     rax, [rdx]
0x1800063a4  cmp     rax, cs:??$guid_v@UIWeakReferenceSource@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IWeakReferenceSource>
0x1800063ab  jnz     short loc_1800063D0
0x1800063ad  mov     rax, [rdx+8]
0x1800063b1  cmp     rax, cs:qword_18002C718
0x1800063b8  jnz     short loc_1800063D0
0x1800063ba  call    ?make_weak_ref@?$root_implements@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUGraphicsCapturePicker@implementation@Capture@Graphics@34@@experimental@std@@U?$IAsyncOperation@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@UIAsyncInfo@678@@impl@winrt@@AEAAPEAUIWeakReferenceSource@23@XZ; winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Graphics::Capture::implementation::GraphicsCapturePicker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Foundation::IAsyncInfo>::make_weak_ref(void)
0x1800063bf  mov     [rdi], rax
0x1800063c2  neg     rax
0x1800063c5  sbb     eax, eax
0x1800063c7  not     eax
0x1800063c9  and     eax, 8007000Eh
0x1800063ce  jmp     short loc_18000642A
0x1800063d0  mov     rax, [rdx]
0x1800063d3  cmp     rax, cs:??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x1800063da  jnz     short loc_1800063ED
0x1800063dc  mov     rax, [rdx+8]
0x1800063e0  cmp     rax, cs:qword_18002C888
0x1800063e7  jz      loc_180006361
0x1800063ed  mov     rax, [rdx]
0x1800063f0  sub     rax, cs:??$guid_v@UIMarshal@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IMarshal>
0x1800063f7  jnz     short loc_180006404
0x1800063f9  mov     rax, [rdx+8]
0x1800063fd  sub     rax, cs:qword_18002C728
0x180006404  mov     r9, [rcx]
0x180006407  test    rax, rax
0x18000640a  jnz     short loc_180006422
0x18000640c  mov     rax, [r9+18h]
0x180006410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006415  mov     rcx, rax
0x180006418  mov     rdx, rdi
0x18000641b  call    ?make_marshaler@impl@winrt@@YAHPEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@12@PEAPEAX@Z; winrt::impl::make_marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *,void * *)
0x180006420  jmp     short loc_18000642A
0x180006422  mov     rax, [r9]
0x180006425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000642a  mov     rbx, [rsp+28h+arg_0]
0x18000642f  add     rsp, 20h
0x180006433  pop     rdi
0x180006434  retn
```
