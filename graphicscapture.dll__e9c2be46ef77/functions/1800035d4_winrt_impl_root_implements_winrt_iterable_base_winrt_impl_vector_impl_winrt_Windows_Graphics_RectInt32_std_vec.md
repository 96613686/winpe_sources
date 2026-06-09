# winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32,std::allocator<winrt::Windows::Graphics::RectInt32>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Graphics::RectInt32,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Graphics::RectInt32>>::~root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32,std::allocator<winrt::Windows::Graphics::RectInt32>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Graphics::RectInt32,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Graphics::RectInt32>>(void)

- ea: `0x1800035d4`
- end: `0x1800035ed`
- name: `??1?$root_implements@Uiterator@?$iterable_base@U?$vector_impl@URectInt32@Graphics@Windows@winrt@@V?$vector@URectInt32@Graphics@Windows@winrt@@V?$allocator@URectInt32@Graphics@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@4@@impl@winrt@@URectInt32@Graphics@Windows@3@Ucollection_version@23@@winrt@@U?$IIterator@URectInt32@Graphics@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@MEAA@XZ`
- size: `25`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003560`
- `0x180003740`
- `0x180003b80`
- `0x180003c00`
- `0x180003c80`
- `0x180003cbc`
- `0x180014368`
- `0x18001f3a8`
- `0x18001f3f8`
- `0x18001f4cc`

## callees

- `0x180003a84`
- `0x18000645c`

## pseudocode

```c
__int64 winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Graphics::RectInt32,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Graphics::RectInt32>>::~root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Graphics::RectInt32,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Graphics::RectInt32>>()
{
  winrt::impl::root_implements<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureSession,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Graphics::Capture::IGraphicsCaptureSessionStatics>::subtract_final_reference();
  return winrt::impl::atomic_ref_count::operator--(&`winrt::get_module_lock'::`2'::s_lock);
}

```

## disassembly

```asm
0x1800035d4  sub     rsp, 28h
0x1800035d8  call    ?subtract_final_reference@?$root_implements@UGraphicsCaptureSession@factory_implementation@Capture@Graphics@Windows@winrt@@UIActivationFactory@Foundation@56@UIGraphicsCaptureSessionStatics@3456@@impl@winrt@@IEAAIXZ; winrt::impl::root_implements<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureSession,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Graphics::Capture::IGraphicsCaptureSessionStatics>::subtract_final_reference(void)
0x1800035dd  lea     rcx, ?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1800035e4  add     rsp, 28h
0x1800035e8  jmp     ??Fatomic_ref_count@impl@winrt@@QEAAIXZ; winrt::impl::atomic_ref_count::operator--(void)
```
