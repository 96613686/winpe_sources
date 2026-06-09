# winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer,std::allocator<winrt::Windows::Storage::Streams::IBuffer>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Storage::Streams::IBuffer>>::First(void * *)

- ea: `0x18002c5a0`
- end: `0x18002c661`
- name: `?First@?$produce@U?$vector_impl@UIBuffer@Streams@Storage@Windows@winrt@@V?$vector@UIBuffer@Streams@Storage@Windows@winrt@@V?$allocator@UIBuffer@Streams@Storage@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@U?$IIterable@UIBuffer@Streams@Storage@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHPEAPEAX@Z`
- size: `193`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800037dc`
- `0x18002c5a0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Storage::Streams::IBuffer>>::First(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v3; // rbx
  _DWORD *v4; // rdx
  signed __int64 v5; // rax
  signed __int64 v6; // rtt

  *a2 = 0;
  if ( !a1 || (v3 = a1 - 32, a1 == -8) )
    v3 = 0;
  v4 = operator new(0x38u);
  v4[6] = *(_DWORD *)(v3 + 40);
  *((_QWORD *)v4 + 2) = &winrt::impl::produce<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Storage::Streams::IBuffer,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Storage::Streams::IBuffer>>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *((_QWORD *)v4 + 1) = 1;
  *(_QWORD *)v4 = &winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Storage::Streams::IBuffer,winrt::impl::collection_version>::iterator::`vftable';
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
        goto LABEL_10;
    }
    _InterlockedIncrement((volatile signed __int32 *)(2 * v5 + 24));
  }
LABEL_10:
  *(_QWORD *)v4 = &winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Storage::Streams::IBuffer,winrt::impl::collection_version>::iterator::`vftable';
  *a2 = v4 + 4;
  return 0;
}

```

## disassembly

```asm
0x18002c5a0  mov     [rsp+arg_8], rbx
0x18002c5a5  push    rdi
0x18002c5a6  sub     rsp, 20h
0x18002c5aa  mov     rdi, rdx
0x18002c5ad  mov     qword ptr [rdx], 0
0x18002c5b4  test    rcx, rcx
0x18002c5b7  jz      short loc_18002C5C6
0x18002c5b9  lea     rbx, [rcx-20h]
0x18002c5bd  lea     rax, [rbx+28h]
0x18002c5c1  test    rax, rax
0x18002c5c4  jnz     short loc_18002C5C8
0x18002c5c6  xor     ebx, ebx
0x18002c5c8  mov     ecx, 38h ; '8'; Size
0x18002c5cd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002c5d2  mov     rdx, rax
0x18002c5d5  mov     ecx, [rbx+28h]
0x18002c5d8  nop
0x18002c5d9  mov     [rax+18h], ecx
0x18002c5dc  lea     r8, [rax+10h]
0x18002c5e0  lea     rax, ??_7?$produce@Uiterator@?$iterable_base@U?$vector_impl@UIBuffer@Streams@Storage@Windows@winrt@@V?$vector@UIBuffer@Streams@Storage@Windows@winrt@@V?$allocator@UIBuffer@Streams@Storage@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UIBuffer@Streams@Storage@Windows@3@Ucollection_version@23@@winrt@@U?$IIterator@UIBuffer@Streams@Storage@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@6B@; const winrt::impl::produce<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Storage::Streams::IBuffer,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Storage::Streams::IBuffer>>::`vftable'
0x18002c5e7  mov     [r8], rax
0x18002c5ea  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18002c5f1  mov     qword ptr [rdx+8], 1
0x18002c5f9  lea     rax, ??_7iterator@?$iterable_base@U?$vector_impl@UIBuffer@Streams@Storage@Windows@winrt@@V?$vector@UIBuffer@Streams@Storage@Windows@winrt@@V?$allocator@UIBuffer@Streams@Storage@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UIBuffer@Streams@Storage@Windows@3@Ucollection_version@23@@winrt@@6B@; const winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Storage::Streams::IBuffer,winrt::impl::collection_version>::iterator::`vftable'
0x18002c600  mov     [rdx], rax
0x18002c603  mov     qword ptr [rdx+20h], 0
0x18002c60b  mov     rax, [rbx+30h]
0x18002c60f  mov     [rdx+28h], rax
0x18002c613  mov     rax, [rbx+38h]
0x18002c617  mov     [rdx+30h], rax
0x18002c61b  test    rbx, rbx
0x18002c61e  jz      short loc_18002C640
0x18002c620  mov     [rdx+20h], rbx
0x18002c624  mov     rax, [rbx+8]
0x18002c628  test    rax, rax
0x18002c62b  js      short loc_18002C63B
0x18002c62d  lea     rcx, [rax+1]
0x18002c631  lock cmpxchg [rbx+8], rcx
0x18002c637  jnz     short loc_18002C628
0x18002c639  jmp     short loc_18002C640
0x18002c63b  lock inc dword ptr [rax+rax+18h]
0x18002c640  lea     rax, ??_7iterator@?$iterable_base@U?$vector_impl@UIBuffer@Streams@Storage@Windows@winrt@@V?$vector@UIBuffer@Streams@Storage@Windows@winrt@@V?$allocator@UIBuffer@Streams@Storage@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UIBuffer@Streams@Storage@Windows@3@Ucollection_version@23@@winrt@@6B@; const winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Storage::Streams::IBuffer,winrt::impl::collection_version>::iterator::`vftable'
0x18002c647  mov     [rdx], rax
0x18002c64a  mov     [rdi], r8
0x18002c64d  xor     eax, eax
0x18002c64f  jmp     short loc_18002C655
0x18002c651  mov     eax, [rsp+28h+arg_0]
0x18002c655  mov     rbx, [rsp+28h+arg_8]
0x18002c65a  add     rsp, 20h
0x18002c65e  pop     rdi
0x18002c65f  retn
```
