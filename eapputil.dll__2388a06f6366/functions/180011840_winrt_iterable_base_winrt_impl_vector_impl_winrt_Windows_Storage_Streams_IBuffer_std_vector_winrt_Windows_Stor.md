# winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer,std::allocator<winrt::Windows::Storage::Streams::IBuffer>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Storage::Streams::IBuffer,winrt::impl::collection_version>::iterator::`vector deleting destructor'(uint)

- ea: `0x180011840`
- end: `0x180011887`
- name: `??_Eiterator@?$iterable_base@U?$vector_impl@UIBuffer@Streams@Storage@Windows@winrt@@V?$vector@UIBuffer@Streams@Storage@Windows@winrt@@V?$allocator@UIBuffer@Streams@Storage@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UIBuffer@Streams@Storage@Windows@3@Ucollection_version@23@@winrt@@UEAAPEAXI@Z`
- size: `71`
- prototype: `char *__fastcall(char *, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800025a0`
- `0x18000d038`
- `0x180011840`
- `0x18001371c`

## pseudocode

```c
char *__fastcall winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Storage::Streams::IBuffer,winrt::impl::collection_version>::iterator::`vector deleting destructor'(
        char *a1,
        char a2)
{
  _QWORD *v4; // rcx

  v4 = a1 + 32;
  if ( *v4 )
    winrt::com_ptr<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref(v4);
  winrt::impl::root_implements<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Eap::Utility::EapAttribute>>::~root_implements<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Eap::Utility::EapAttribute>>((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180011840  mov     [rsp+arg_0], rbx
0x180011845  push    rdi
0x180011846  sub     rsp, 20h
0x18001184a  mov     rbx, rcx
0x18001184d  mov     edi, edx
0x18001184f  add     rcx, 20h ; ' '
0x180011853  cmp     qword ptr [rcx], 0
0x180011857  jz      short loc_18001185E
0x180011859  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@UIBuffer@Streams@Storage@Windows@winrt@@V?$vector@UIBuffer@Streams@Storage@Windows@winrt@@V?$allocator@UIBuffer@Streams@Storage@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref(void)
0x18001185e  mov     rcx, rbx
0x180011861  call    ??1?$root_implements@U?$vector_impl@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$vector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$allocator@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@6@@impl@winrt@@U?$IVector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@Collections@Foundation@Windows@3@U?$IVectorView@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@5673@U?$IIterable@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@5673@@impl@winrt@@MEAA@XZ; winrt::impl::root_implements<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Eap::Utility::EapAttribute>>::~root_implements<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Eap::Utility::EapAttribute>>(void)
0x180011866  test    dil, 1
0x18001186a  jz      short loc_180011879
0x18001186c  mov     edx, 38h ; '8'; unsigned __int64
0x180011871  mov     rcx, rbx; void *
0x180011874  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011879  mov     rax, rbx
0x18001187c  mov     rbx, [rsp+28h+arg_0]
0x180011881  add     rsp, 20h
0x180011885  pop     rdi
0x180011886  retn
```
