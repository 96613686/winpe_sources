# winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(std::vector<winrt::hstring,std::allocator<winrt::hstring>> &&)

- ea: `0x180025c1c`
- end: `0x180025cca`
- name: `??$single_threaded_vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@winrt@@YA?AU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@0@$$QEAV?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@@Z`
- size: `174`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180026bb4`
- `0x18002caf0`

## callees

- `0x1800037dc`

## pseudocode

```c
_QWORD *__fastcall winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(
        _QWORD *a1,
        __int64 *a2)
{
  _QWORD *v4; // r9
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  _QWORD *result; // rax

  v4 = operator new(0x48u);
  v4[2] = &winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>>::`vftable';
  v4[3] = &winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>>::`vftable';
  v4[4] = &winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IIterable<winrt::hstring>>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  v4[1] = 1;
  *((_DWORD *)v4 + 10) = 0;
  *v4 = &winrt::impl::heap_implements<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>>::`vftable';
  v5 = *a2;
  v6 = a2[2];
  v7 = a2[1];
  a2[2] = 0;
  a2[1] = 0;
  *a2 = 0;
  v4[6] = v5;
  v4[7] = v7;
  v4[8] = v6;
  *v4 = &winrt::impl::heap_implements<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>>::`vftable';
  result = a1;
  *a1 = v4 + 2;
  return result;
}

```

## disassembly

```asm
0x180025c1c  mov     [rsp+arg_8], rbx
0x180025c21  push    rdi
0x180025c22  sub     rsp, 30h
0x180025c26  mov     rdi, rcx
0x180025c29  mov     rbx, rdx
0x180025c2c  mov     ecx, 48h ; 'H'; Size
0x180025c31  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025c36  mov     [rsp+38h+arg_0], rax
0x180025c3b  mov     r9, rax
0x180025c3e  lea     r8, [rax+10h]
0x180025c42  lea     rax, ??_7?$produce@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@6B@; const winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>>::`vftable'
0x180025c49  mov     [r8], rax
0x180025c4c  lea     rax, ??_7?$produce@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IVectorView@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@6B@; const winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>>::`vftable'
0x180025c53  mov     [r8+8], rax
0x180025c57  lea     rax, ??_7?$produce@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IIterable@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@6B@; const winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IIterable<winrt::hstring>>::`vftable'
0x180025c5e  mov     [r8+10h], rax
0x180025c62  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180025c69  mov     qword ptr [r9+8], 1
0x180025c71  xor     eax, eax
0x180025c73  mov     [r9+28h], eax
0x180025c77  lea     rax, ??_7?$heap_implements@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>>::`vftable'
0x180025c7e  mov     [r9], rax
0x180025c81  mov     rax, [rbx]
0x180025c84  mov     rdx, [rbx+10h]
0x180025c88  mov     rcx, [rbx+8]
0x180025c8c  mov     qword ptr [rbx+10h], 0
0x180025c94  mov     qword ptr [rbx+8], 0
0x180025c9c  mov     qword ptr [rbx], 0
0x180025ca3  mov     rbx, [rsp+38h+arg_8]
0x180025ca8  mov     [r9+30h], rax
0x180025cac  lea     rax, ??_7?$heap_implements@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>>::`vftable'
0x180025cb3  mov     [r9+38h], rcx
0x180025cb7  mov     [r9+40h], rdx
0x180025cbb  mov     [r9], rax
0x180025cbe  mov     rax, rdi
0x180025cc1  mov     [rdi], r8
0x180025cc4  add     rsp, 30h
0x180025cc8  pop     rdi
0x180025cc9  retn
```
