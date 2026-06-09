# winrt::single_threaded_vector<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::allocator<winrt::Windows::Internal::Eap::Utility::EapAttribute>>(std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::allocator<winrt::Windows::Internal::Eap::Utility::EapAttribute>> &&)

- ea: `0x180011424`
- end: `0x1800114d2`
- name: `??$single_threaded_vector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$allocator@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@std@@@winrt@@YA?AU?$IVector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@Collections@Foundation@Windows@0@$$QEAV?$vector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$allocator@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@std@@@std@@@Z`
- size: `174`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180012f40`
- `0x18002f008`

## callees

- `0x1800037dc`

## pseudocode

```c
_QWORD *__fastcall winrt::single_threaded_vector<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::allocator<winrt::Windows::Internal::Eap::Utility::EapAttribute>>(
        _QWORD *a1,
        __int64 *a2)
{
  _QWORD *v4; // r9
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  _QWORD *result; // rax

  v4 = operator new(0x48u);
  v4[2] = &winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Eap::Utility::EapAttribute>>::`vftable';
  v4[3] = &winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Eap::Utility::EapAttribute>>::`vftable';
  v4[4] = &winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Eap::Utility::EapAttribute>>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  v4[1] = 1;
  *((_DWORD *)v4 + 10) = 0;
  *v4 = &winrt::impl::heap_implements<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>>::`vftable';
  v5 = *a2;
  v6 = a2[2];
  v7 = a2[1];
  a2[2] = 0;
  a2[1] = 0;
  *a2 = 0;
  v4[6] = v5;
  v4[7] = v7;
  v4[8] = v6;
  *v4 = &winrt::impl::heap_implements<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>>::`vftable';
  result = a1;
  *a1 = v4 + 2;
  return result;
}

```

## disassembly

```asm
0x180011424  mov     [rsp+arg_8], rbx
0x180011429  push    rdi
0x18001142a  sub     rsp, 30h
0x18001142e  mov     rdi, rcx
0x180011431  mov     rbx, rdx
0x180011434  mov     ecx, 48h ; 'H'; Size
0x180011439  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001143e  mov     [rsp+38h+arg_0], rax
0x180011443  mov     r9, rax
0x180011446  lea     r8, [rax+10h]
0x18001144a  lea     rax, ??_7?$produce@U?$vector_impl@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$vector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$allocator@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@6@@impl@winrt@@U?$IVector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@6B@; const winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Eap::Utility::EapAttribute>>::`vftable'
0x180011451  mov     [r8], rax
0x180011454  lea     rax, ??_7?$produce@U?$vector_impl@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$vector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$allocator@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@6@@impl@winrt@@U?$IVectorView@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@6B@; const winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Eap::Utility::EapAttribute>>::`vftable'
0x18001145b  mov     [r8+8], rax
0x18001145f  lea     rax, ??_7?$produce@U?$vector_impl@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$vector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$allocator@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@6@@impl@winrt@@U?$IIterable@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@6B@; const winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Eap::Utility::EapAttribute>>::`vftable'
0x180011466  mov     [r8+10h], rax
0x18001146a  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180011471  mov     qword ptr [r9+8], 1
0x180011479  xor     eax, eax
0x18001147b  mov     [r9+28h], eax
0x18001147f  lea     rax, ??_7?$heap_implements@U?$vector_impl@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$vector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$allocator@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@6@@impl@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>>::`vftable'
0x180011486  mov     [r9], rax
0x180011489  mov     rax, [rbx]
0x18001148c  mov     rdx, [rbx+10h]
0x180011490  mov     rcx, [rbx+8]
0x180011494  mov     qword ptr [rbx+10h], 0
0x18001149c  mov     qword ptr [rbx+8], 0
0x1800114a4  mov     qword ptr [rbx], 0
0x1800114ab  mov     rbx, [rsp+38h+arg_8]
0x1800114b0  mov     [r9+30h], rax
0x1800114b4  lea     rax, ??_7?$heap_implements@U?$vector_impl@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$vector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$allocator@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@6@@impl@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>>::`vftable'
0x1800114bb  mov     [r9+38h], rcx
0x1800114bf  mov     [r9+40h], rdx
0x1800114c3  mov     [r9], rax
0x1800114c6  mov     rax, rdi
0x1800114c9  mov     [rdi], r8
0x1800114cc  add     rsp, 30h
0x1800114d0  pop     rdi
0x1800114d1  retn
```
