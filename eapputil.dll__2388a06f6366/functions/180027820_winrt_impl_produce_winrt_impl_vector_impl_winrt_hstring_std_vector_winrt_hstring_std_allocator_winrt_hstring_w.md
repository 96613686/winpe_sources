# winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IIterable<winrt::hstring>>::First(void * *)

- ea: `0x180027820`
- end: `0x1800278e1`
- name: `?First@?$produce@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IIterable@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHPEAPEAX@Z`
- size: `193`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800037dc`
- `0x180027820`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IIterable<winrt::hstring>>::First(
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
  *((_QWORD *)v4 + 2) = &winrt::impl::produce<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *((_QWORD *)v4 + 1) = 1;
  *(_QWORD *)v4 = &winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator::`vftable';
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
  *(_QWORD *)v4 = &winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator::`vftable';
  *a2 = v4 + 4;
  return 0;
}

```

## disassembly

```asm
0x180027820  mov     [rsp+arg_8], rbx
0x180027825  push    rdi
0x180027826  sub     rsp, 20h
0x18002782a  mov     rdi, rdx
0x18002782d  mov     qword ptr [rdx], 0
0x180027834  test    rcx, rcx
0x180027837  jz      short loc_180027846
0x180027839  lea     rbx, [rcx-20h]
0x18002783d  lea     rax, [rbx+28h]
0x180027841  test    rax, rax
0x180027844  jnz     short loc_180027848
0x180027846  xor     ebx, ebx
0x180027848  mov     ecx, 38h ; '8'; Size
0x18002784d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180027852  mov     rdx, rax
0x180027855  mov     ecx, [rbx+28h]
0x180027858  nop
0x180027859  mov     [rax+18h], ecx
0x18002785c  lea     r8, [rax+10h]
0x180027860  lea     rax, ??_7?$produce@Uiterator@?$iterable_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@U?$IIterator@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@6B@; const winrt::impl::produce<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::`vftable'
0x180027867  mov     [r8], rax
0x18002786a  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180027871  mov     qword ptr [rdx+8], 1
0x180027879  lea     rax, ??_7iterator@?$iterable_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@6B@; const winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator::`vftable'
0x180027880  mov     [rdx], rax
0x180027883  mov     qword ptr [rdx+20h], 0
0x18002788b  mov     rax, [rbx+30h]
0x18002788f  mov     [rdx+28h], rax
0x180027893  mov     rax, [rbx+38h]
0x180027897  mov     [rdx+30h], rax
0x18002789b  test    rbx, rbx
0x18002789e  jz      short loc_1800278C0
0x1800278a0  mov     [rdx+20h], rbx
0x1800278a4  mov     rax, [rbx+8]
0x1800278a8  test    rax, rax
0x1800278ab  js      short loc_1800278BB
0x1800278ad  lea     rcx, [rax+1]
0x1800278b1  lock cmpxchg [rbx+8], rcx
0x1800278b7  jnz     short loc_1800278A8
0x1800278b9  jmp     short loc_1800278C0
0x1800278bb  lock inc dword ptr [rax+rax+18h]
0x1800278c0  lea     rax, ??_7iterator@?$iterable_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@6B@; const winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator::`vftable'
0x1800278c7  mov     [rdx], rax
0x1800278ca  mov     [rdi], r8
0x1800278cd  xor     eax, eax
0x1800278cf  jmp     short loc_1800278D5
0x1800278d1  mov     eax, [rsp+28h+arg_0]
0x1800278d5  mov     rbx, [rsp+28h+arg_8]
0x1800278da  add     rsp, 20h
0x1800278de  pop     rdi
0x1800278df  retn
```
