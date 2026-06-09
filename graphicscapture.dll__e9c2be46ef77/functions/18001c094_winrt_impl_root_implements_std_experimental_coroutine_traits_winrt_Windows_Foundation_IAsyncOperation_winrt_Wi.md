# winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,winrt::Windows::Foundation::IAsyncInfo>::query_interface(winrt::guid const &,void * *)

- ea: `0x18001c094`
- end: `0x18001c10d`
- name: `?query_interface@?$root_implements@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@W4GraphicsCaptureAccessKind@Capture@Graphics@34@@experimental@std@@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@UIAsyncInfo@678@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001bc50`
- `0x18001bc70`

## callees

- `0x180003ff0`
- `0x180006234`
- `0x18001c094`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,enum winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind>::promise_type,winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,winrt::Windows::Foundation::IAsyncInfo>::query_interface(
        __int64 a1,
        _QWORD *a2,
        __int64 *a3)
{
  __int64 v5; // rcx
  __int64 v6; // rdx

  if ( *a2 == winrt::impl::guid_v<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>
    && a2[1] == 0x3D4D133448C4CE84LL )
  {
    v5 = a1 + 16;
LABEL_4:
    v6 = v5 & ((unsigned __int128)-(__int128)(unsigned __int64)a1 >> 64);
    goto LABEL_9;
  }
  if ( *a2 == winrt::impl::guid_v<winrt::Windows::Foundation::IAsyncInfo> && a2[1] == 0x46000000000000C0LL )
  {
    v5 = a1 + 24;
    goto LABEL_4;
  }
  v6 = 0;
LABEL_9:
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
0x18001c094  sub     rsp, 28h
0x18001c098  mov     rax, [rdx]
0x18001c09b  mov     r10, rdx
0x18001c09e  cmp     rax, cs:??$guid_v@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>
0x18001c0a5  mov     r9, rcx
0x18001c0a8  jnz     short loc_18001C0C9
0x18001c0aa  mov     rax, [rdx+8]
0x18001c0ae  cmp     rax, cs:qword_18002DC50
0x18001c0b5  jnz     short loc_18001C0C9
0x18001c0b7  add     rcx, 10h
0x18001c0bb  mov     rax, r9
0x18001c0be  neg     rax
0x18001c0c1  sbb     rdx, rdx
0x18001c0c4  and     rdx, rcx
0x18001c0c7  jmp     short loc_18001C0EA
0x18001c0c9  mov     rax, [rdx]
0x18001c0cc  cmp     rax, cs:??$guid_v@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IAsyncInfo>
0x18001c0d3  jnz     short loc_18001C0E8
0x18001c0d5  mov     rax, [rdx+8]
0x18001c0d9  cmp     rax, cs:qword_18002D680
0x18001c0e0  jnz     short loc_18001C0E8
0x18001c0e2  add     rcx, 18h
0x18001c0e6  jmp     short loc_18001C0BB
0x18001c0e8  xor     edx, edx
0x18001c0ea  mov     [r8], rdx
0x18001c0ed  mov     rcx, r9
0x18001c0f0  test    rdx, rdx
0x18001c0f3  jz      short loc_18001C101
0x18001c0f5  call    ?AddRef@?$root_implements@UGraphicsCaptureAccess@factory_implementation@Capture@Graphics@Windows@winrt@@UIActivationFactory@Foundation@56@UIGraphicsCaptureAccessStatics@3456@@impl@winrt@@QEAAIXZ; winrt::impl::root_implements<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureAccess,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Graphics::Capture::IGraphicsCaptureAccessStatics>::AddRef(void)
0x18001c0fa  xor     eax, eax
0x18001c0fc  add     rsp, 28h
0x18001c100  retn
0x18001c101  mov     rdx, r10
0x18001c104  add     rsp, 28h
0x18001c108  jmp     ?query_interface_common@?$root_implements@U?$vector_impl@URectInt32@Graphics@Windows@winrt@@V?$vector@URectInt32@Graphics@Windows@winrt@@V?$allocator@URectInt32@Graphics@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@4@@impl@winrt@@U?$IVector@URectInt32@Graphics@Windows@winrt@@@Collections@Foundation@Windows@3@U?$IVectorView@URectInt32@Graphics@Windows@winrt@@@5673@U?$IIterable@URectInt32@Graphics@Windows@winrt@@@5673@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z; winrt::impl::root_implements<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Graphics::RectInt32>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Graphics::RectInt32>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Graphics::RectInt32>>::query_interface_common(winrt::guid const &,void * *)
```
