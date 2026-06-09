# winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::allocator<winrt::Windows::Internal::Eap::Utility::EapAttribute>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Eap::Utility::EapAttribute>>::First(void * *)

- ea: `0x180011aa0`
- end: `0x180011b61`
- name: `?First@?$produce@U?$vector_impl@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$vector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$allocator@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@6@@impl@winrt@@U?$IIterable@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHPEAPEAX@Z`
- size: `193`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800037dc`
- `0x180011aa0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Eap::Utility::EapAttribute>>::First(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v3; // rbx
  _DWORD *v4; // rdx
  signed __int64 v5; // rax
  signed __int64 v6; // rtt
  __int64 result; // rax
  int v8; // [rsp+30h] [rbp+8h] BYREF

  *a2 = 0;
  if ( !a1 || (v3 = a1 - 32, a1 == -8) )
    v3 = 0;
  try
  {
    v4 = operator new(0x38u);
    v4[6] = *(_DWORD *)(v3 + 40);
    *((_QWORD *)v4 + 2) = &winrt::impl::produce<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Storage::Streams::IBuffer,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Storage::Streams::IBuffer>>::`vftable';
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    *((_QWORD *)v4 + 1) = 1;
    *(_QWORD *)v4 = &winrt::impl::heap_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Internal::Eap::Utility::EapAttribute,winrt::impl::collection_version>::iterator>::`vftable';
    *((_QWORD *)v4 + 4) = 0;
    *((_QWORD *)v4 + 5) = *(_QWORD *)(v3 + 48);
    *((_QWORD *)v4 + 6) = *(_QWORD *)(v3 + 56);
    if ( v3 )
    {
      *((_QWORD *)v4 + 4) = v3;
      v5 = *(_QWORD *)(v3 + 8);
      while ( v5 >= 0 )
      {
        v6 = v5;
        v5 = _InterlockedCompareExchange64((volatile signed __int64 *)(v3 + 8), v5 + 1, v5);
        if ( v6 == v5 )
          goto LABEL_11;
      }
      _InterlockedIncrement((volatile signed __int32 *)(2 * v5 + 24));
    }
LABEL_11:
    *(_QWORD *)v4 = &winrt::impl::heap_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Internal::Eap::Utility::EapAttribute,winrt::impl::collection_version>::iterator>::`vftable';
    *a2 = v4 + 4;
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v8);
  }
  return result;
}

```

## disassembly

```asm
0x180011aa0  mov     [rsp+arg_8], rbx
0x180011aa5  push    rdi
0x180011aa6  sub     rsp, 20h
0x180011aaa  mov     rdi, rdx
0x180011aad  mov     qword ptr [rdx], 0
0x180011ab4  test    rcx, rcx
0x180011ab7  jz      short loc_180011AC6
0x180011ab9  lea     rbx, [rcx-20h]
0x180011abd  lea     rax, [rbx+28h]
0x180011ac1  test    rax, rax
0x180011ac4  jnz     short loc_180011AC8
0x180011ac6  xor     ebx, ebx
0x180011ac8  mov     ecx, 38h ; '8'; Size
0x180011acd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011ad2  mov     rdx, rax
0x180011ad5  mov     ecx, [rbx+28h]
0x180011ad8  nop
0x180011ad9  mov     [rax+18h], ecx
0x180011adc  lea     r8, [rax+10h]
0x180011ae0  lea     rax, ??_7?$produce@Uiterator@?$iterable_base@U?$vector_impl@UIBuffer@Streams@Storage@Windows@winrt@@V?$vector@UIBuffer@Streams@Storage@Windows@winrt@@V?$allocator@UIBuffer@Streams@Storage@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UIBuffer@Streams@Storage@Windows@3@Ucollection_version@23@@winrt@@U?$IIterator@UIBuffer@Streams@Storage@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@6B@; const winrt::impl::produce<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Storage::Streams::IBuffer,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Storage::Streams::IBuffer>>::`vftable'
0x180011ae7  mov     [r8], rax
0x180011aea  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180011af1  mov     qword ptr [rdx+8], 1
0x180011af9  lea     rax, ??_7?$heap_implements@Uiterator@?$iterable_base@U?$vector_impl@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$vector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$allocator@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@6@@impl@winrt@@UEapAttribute@Utility@Eap@Internal@Windows@3@Ucollection_version@23@@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Internal::Eap::Utility::EapAttribute,winrt::impl::collection_version>::iterator>::`vftable'
0x180011b00  mov     [rdx], rax
0x180011b03  mov     qword ptr [rdx+20h], 0
0x180011b0b  mov     rax, [rbx+30h]
0x180011b0f  mov     [rdx+28h], rax
0x180011b13  mov     rax, [rbx+38h]
0x180011b17  mov     [rdx+30h], rax
0x180011b1b  test    rbx, rbx
0x180011b1e  jz      short loc_180011B40
0x180011b20  mov     [rdx+20h], rbx
0x180011b24  mov     rax, [rbx+8]
0x180011b28  test    rax, rax
0x180011b2b  js      short loc_180011B3B
0x180011b2d  lea     rcx, [rax+1]
0x180011b31  lock cmpxchg [rbx+8], rcx
0x180011b37  jnz     short loc_180011B28
0x180011b39  jmp     short loc_180011B40
0x180011b3b  lock inc dword ptr [rax+rax+18h]
0x180011b40  lea     rax, ??_7?$heap_implements@Uiterator@?$iterable_base@U?$vector_impl@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$vector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$allocator@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@6@@impl@winrt@@UEapAttribute@Utility@Eap@Internal@Windows@3@Ucollection_version@23@@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Internal::Eap::Utility::EapAttribute,winrt::impl::collection_version>::iterator>::`vftable'
0x180011b47  mov     [rdx], rax
0x180011b4a  mov     [rdi], r8
0x180011b4d  xor     eax, eax
0x180011b4f  jmp     short loc_180011B55
0x180011b51  mov     eax, [rsp+28h+arg_0]
0x180011b55  mov     rbx, [rsp+28h+arg_8]
0x180011b5a  add     rsp, 20h
0x180011b5e  pop     rdi
0x180011b5f  retn
```
