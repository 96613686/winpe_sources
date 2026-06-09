# winrt::impl::root_implements<winrt::impl::vector_impl<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation,std::vector<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation,std::allocator<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>>::AddRef(void)

- ea: `0x180004038`
- end: `0x180004069`
- name: `?AddRef@?$root_implements@U?$vector_impl@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@V?$vector@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@V?$allocator@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@6@@impl@winrt@@U?$IVector@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@@Collections@Foundation@Windows@3@U?$IVectorView@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@@5673@U?$IIterable@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@@5673@@impl@winrt@@QEAAIXZ`
- size: `49`
- prototype: ``
- caller_count: `19`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003e90`
- `0x180006164`
- `0x180006338`
- `0x180018080`
- `0x1800180a0`
- `0x1800180f0`
- `0x180018110`
- `0x18001afc4`
- `0x18001b02c`
- `0x18001c9e0`
- `0x18001deb0`
- `0x18001e97c`
- `0x18001f67c`
- `0x18001f690`
- `0x180020d40`
- `0x180020da0`
- `0x180020e10`
- `0x180020e80`
- `0x18002261c`

## callees

- `0x180004038`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<winrt::impl::vector_impl<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation,std::vector<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>>::AddRef(
        __int64 a1)
{
  signed __int64 v1; // rdx
  unsigned int v2; // r8d
  bool v3; // zf
  signed __int64 v4; // rax

  v1 = *(_QWORD *)(a1 + 8);
  while ( v1 >= 0 )
  {
    v2 = v1 + 1;
    v4 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 8), v1 + 1, v1);
    v3 = v1 == v4;
    v1 = v4;
    if ( v3 )
      return v2;
  }
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(2 * v1 + 24));
}

```

## disassembly

```asm
0x180004038  mov     rdx, [rcx+8]
0x18000403c  test    rdx, rdx
0x18000403f  js      short loc_180004055
0x180004041  lea     r8, [rdx+1]
0x180004045  mov     rax, rdx
0x180004048  lock cmpxchg [rcx+8], r8
0x18000404e  mov     rdx, rax
0x180004051  jnz     short loc_18000403C
0x180004053  jmp     short loc_180004065
0x180004055  mov     r8d, 1
0x18000405b  lock xadd [rdx+rdx+18h], r8d
0x180004062  inc     r8d
0x180004065  mov     eax, r8d
0x180004068  retn
```
