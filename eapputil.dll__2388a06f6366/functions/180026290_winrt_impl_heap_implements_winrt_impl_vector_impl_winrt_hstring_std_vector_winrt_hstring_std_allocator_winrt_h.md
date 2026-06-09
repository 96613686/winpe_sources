# winrt::impl::heap_implements<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>>::`vector deleting destructor'(uint)

- ea: `0x180026290`
- end: `0x1800262d0`
- name: `??_E?$heap_implements@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@@impl@winrt@@UEAAPEAXI@Z`
- size: `64`
- prototype: `char *__fastcall(char *, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x1800025a0`
- `0x18000d038`
- `0x180025fc8`
- `0x180026290`

## pseudocode

```c
char *__fastcall winrt::impl::heap_implements<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>>::`vector deleting destructor'(
        char *a1,
        char a2)
{
  std::vector<winrt::hstring>::~vector<winrt::hstring>(a1 + 48);
  winrt::impl::root_implements<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Eap::Utility::EapAttribute>>::~root_implements<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Eap::Utility::EapAttribute>>((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180026290  mov     [rsp+arg_0], rbx
0x180026295  push    rdi
0x180026296  sub     rsp, 20h
0x18002629a  mov     rdi, rcx
0x18002629d  mov     ebx, edx
0x18002629f  add     rcx, 30h ; '0'
0x1800262a3  call    ??1?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::hstring>::~vector<winrt::hstring>(void)
0x1800262a8  mov     rcx, rdi
0x1800262ab  call    ??1?$root_implements@U?$vector_impl@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$vector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$allocator@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@6@@impl@winrt@@U?$IVector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@Collections@Foundation@Windows@3@U?$IVectorView@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@5673@U?$IIterable@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@5673@@impl@winrt@@MEAA@XZ; winrt::impl::root_implements<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Eap::Utility::EapAttribute>>::~root_implements<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Eap::Utility::EapAttribute>>(void)
0x1800262b0  test    bl, 1
0x1800262b3  jz      short loc_1800262C2
0x1800262b5  mov     edx, 48h ; 'H'; unsigned __int64
0x1800262ba  mov     rcx, rdi; void *
0x1800262bd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800262c2  mov     rbx, [rsp+28h+arg_0]
0x1800262c7  mov     rax, rdi
0x1800262ca  add     rsp, 20h
0x1800262ce  pop     rdi
0x1800262cf  retn
```
