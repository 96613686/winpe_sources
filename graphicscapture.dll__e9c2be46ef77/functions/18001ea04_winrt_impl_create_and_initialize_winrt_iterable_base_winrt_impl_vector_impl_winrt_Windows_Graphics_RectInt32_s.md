# winrt::impl::create_and_initialize<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32,std::allocator<winrt::Windows::Graphics::RectInt32>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Graphics::RectInt32,winrt::impl::collection_version>::iterator,winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32,std::allocator<winrt::Windows::Graphics::RectInt32>>,winrt::impl::single_threaded_collection_base> *>(winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32,std::allocator<winrt::Windows::Graphics::RectInt32>>,winrt::impl::single_threaded_collection_base> * &&)

- ea: `0x18001ea04`
- end: `0x18001ea8e`
- name: `??$create_and_initialize@Uiterator@?$iterable_base@U?$vector_impl@URectInt32@Graphics@Windows@winrt@@V?$vector@URectInt32@Graphics@Windows@winrt@@V?$allocator@URectInt32@Graphics@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@4@@impl@winrt@@URectInt32@Graphics@Windows@3@Ucollection_version@23@@winrt@@PEAU?$vector_impl@URectInt32@Graphics@Windows@winrt@@V?$vector@URectInt32@Graphics@Windows@winrt@@V?$allocator@URectInt32@Graphics@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@4@@impl@3@@impl@winrt@@YAPEAUiterator@?$iterable_base@U?$vector_impl@URectInt32@Graphics@Windows@winrt@@V?$vector@URectInt32@Graphics@Windows@winrt@@V?$allocator@URectInt32@Graphics@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@4@@impl@winrt@@URectInt32@Graphics@Windows@3@Ucollection_version@23@@1@$$QEAPEAU?$vector_impl@URectInt32@Graphics@Windows@winrt@@V?$vector@URectInt32@Graphics@Windows@winrt@@V?$allocator@URectInt32@Graphics@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@4@@01@@Z`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001fcc0`

## callees

- `0x180002158`
- `0x180002da8`
- `0x180003ff0`
- `0x180005d4c`
- `0x18001ea04`
- `0x18001ef2c`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::create_and_initialize<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Graphics::RectInt32,winrt::impl::collection_version>::iterator,winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32>,winrt::impl::single_threaded_collection_base> *>(
        _QWORD *a1)
{
  int v2; // eax
  __int64 v3; // r9
  __int64 v4; // r9
  __int64 v5; // r8
  _QWORD *v6; // r9

  operator new(0x38u);
  v2 = std::_Atomic_storage<unsigned int,4>::load(*a1 + 40LL, 5);
  *(_DWORD *)(v3 + 24) = v2;
  winrt::impl::producers_base<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Graphics::RectInt32,winrt::impl::collection_version>::iterator,std::tuple<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Graphics::RectInt32>>>::producers_base<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Graphics::RectInt32,winrt::impl::collection_version>::iterator,std::tuple<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Graphics::RectInt32>>>(v3 + 16);
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  std::atomic<unsigned __int64>::atomic<unsigned __int64>(v4 + 8);
  *v6 = &winrt::impl::heap_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Graphics::RectInt32,winrt::impl::collection_version>::iterator>::`vftable';
  v6[4] = 0;
  v6[5] = *(_QWORD *)(v5 + 48);
  v6[6] = *(_QWORD *)(v5 + 56);
  if ( v5 )
  {
    v6[4] = v5;
    winrt::impl::root_implements<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureAccess,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Graphics::Capture::IGraphicsCaptureAccessStatics>::AddRef(v5);
  }
  *v6 = &winrt::impl::heap_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Graphics::RectInt32,winrt::impl::collection_version>::iterator>::`vftable';
  return v6;
}

```

## disassembly

```asm
0x18001ea04  push    rbx
0x18001ea06  sub     rsp, 20h
0x18001ea0a  mov     rbx, rcx
0x18001ea0d  mov     ecx, 38h ; '8'; Size
0x18001ea12  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ea17  mov     r8, [rbx]
0x18001ea1a  mov     edx, 5
0x18001ea1f  mov     r9, rax
0x18001ea22  lea     rcx, [r8+28h]
0x18001ea26  call    ?load@?$_Atomic_storage@I$03@std@@QEBAIW4memory_order@2@@Z; std::_Atomic_storage<uint,4>::load(std::memory_order)
0x18001ea2b  lea     rcx, [r9+10h]
0x18001ea2f  mov     [r9+18h], eax
0x18001ea33  call    ??0?$producers_base@Uiterator@?$iterable_base@U?$vector_impl@URectInt32@Graphics@Windows@winrt@@V?$vector@URectInt32@Graphics@Windows@winrt@@V?$allocator@URectInt32@Graphics@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@4@@impl@winrt@@URectInt32@Graphics@Windows@3@Ucollection_version@23@@winrt@@V?$tuple@U?$IIterator@URectInt32@Graphics@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@std@@@impl@winrt@@QEAA@XZ; winrt::impl::producers_base<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Graphics::RectInt32,winrt::impl::collection_version>::iterator,std::tuple<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Graphics::RectInt32>>>::producers_base<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Graphics::RectInt32,winrt::impl::collection_version>::iterator,std::tuple<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Graphics::RectInt32>>>(void)
0x18001ea38  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001ea3f  lea     rcx, [r9+8]
0x18001ea43  call    ??0?$atomic@_K@std@@QEAA@_K@Z; std::atomic<unsigned __int64>::atomic<unsigned __int64>(unsigned __int64)
0x18001ea48  lea     rcx, ??_7?$heap_implements@Uiterator@?$iterable_base@U?$vector_impl@URectInt32@Graphics@Windows@winrt@@V?$vector@URectInt32@Graphics@Windows@winrt@@V?$allocator@URectInt32@Graphics@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@4@@impl@winrt@@URectInt32@Graphics@Windows@3@Ucollection_version@23@@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Graphics::RectInt32,winrt::impl::collection_version>::iterator>::`vftable'
0x18001ea4f  mov     [r9], rcx
0x18001ea52  mov     qword ptr [r9+20h], 0
0x18001ea5a  mov     rax, [r8+30h]
0x18001ea5e  mov     [r9+28h], rax
0x18001ea62  mov     rax, [r8+38h]
0x18001ea66  mov     [r9+30h], rax
0x18001ea6a  test    r8, r8
0x18001ea6d  jz      short loc_18001EA7B
0x18001ea6f  mov     rcx, r8
0x18001ea72  mov     [r9+20h], r8
0x18001ea76  call    ?AddRef@?$root_implements@UGraphicsCaptureAccess@factory_implementation@Capture@Graphics@Windows@winrt@@UIActivationFactory@Foundation@56@UIGraphicsCaptureAccessStatics@3456@@impl@winrt@@QEAAIXZ; winrt::impl::root_implements<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureAccess,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Graphics::Capture::IGraphicsCaptureAccessStatics>::AddRef(void)
0x18001ea7b  lea     rax, ??_7?$heap_implements@Uiterator@?$iterable_base@U?$vector_impl@URectInt32@Graphics@Windows@winrt@@V?$vector@URectInt32@Graphics@Windows@winrt@@V?$allocator@URectInt32@Graphics@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@4@@impl@winrt@@URectInt32@Graphics@Windows@3@Ucollection_version@23@@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Graphics::RectInt32,winrt::impl::collection_version>::iterator>::`vftable'
0x18001ea82  mov     [r9], rax
0x18001ea85  mov     rax, r9
0x18001ea88  add     rsp, 20h
0x18001ea8c  pop     rbx
0x18001ea8d  retn
```
