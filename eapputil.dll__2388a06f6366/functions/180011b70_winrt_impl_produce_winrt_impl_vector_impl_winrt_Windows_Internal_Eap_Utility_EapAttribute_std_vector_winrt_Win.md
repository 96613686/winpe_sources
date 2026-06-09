# winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::allocator<winrt::Windows::Internal::Eap::Utility::EapAttribute>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Eap::Utility::EapAttribute>>::GetAt(uint,void * *)

- ea: `0x180011b70`
- end: `0x180011bcf`
- name: `?GetAt@?$produce@U?$vector_impl@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$vector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$allocator@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@6@@impl@winrt@@U?$IVector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIPEAPEAX@Z`
- size: `95`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800083ec`
- `0x180011b70`
- `0x180011c48`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Eap::Utility::EapAttribute>>::GetAt(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 *v4; // rax
  __int64 v5; // rcx
  __int64 result; // rax
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF

  *a3 = 0;
  try
  {
    v4 = (__int64 *)winrt::vector_view_base<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Storage::Streams::IBuffer,winrt::impl::collection_version>::GetAt();
    v5 = *v4;
    *v4 = 0;
    *a3 = v5;
    if ( v7 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v7);
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v7);
  }
  return result;
}

```

## disassembly

```asm
0x180011b70  push    rbx
0x180011b72  sub     rsp, 20h
0x180011b76  mov     rbx, r8
0x180011b79  mov     rax, rcx
0x180011b7c  mov     qword ptr [r8], 0
0x180011b83  add     rcx, 18h
0x180011b87  mov     r8d, 28h ; '('
0x180011b8d  test    rax, rax
0x180011b90  cmovz   rcx, r8
0x180011b94  mov     r8d, edx
0x180011b97  lea     rdx, [rsp+28h+arg_0]
0x180011b9c  call    ?GetAt@?$vector_view_base@U?$vector_impl@UIBuffer@Streams@Storage@Windows@winrt@@V?$vector@UIBuffer@Streams@Storage@Windows@winrt@@V?$allocator@UIBuffer@Streams@Storage@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UIBuffer@Streams@Storage@Windows@3@Ucollection_version@23@@winrt@@QEBA?AUIBuffer@Streams@Storage@Windows@2@I@Z; winrt::vector_view_base<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Storage::Streams::IBuffer,winrt::impl::collection_version>::GetAt(uint)
0x180011ba1  mov     rcx, [rax]
0x180011ba4  mov     qword ptr [rax], 0
0x180011bab  mov     [rbx], rcx
0x180011bae  cmp     [rsp+28h+arg_0], 0
0x180011bb4  jz      short loc_180011BC0
0x180011bb6  lea     rcx, [rsp+28h+arg_0]
0x180011bbb  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180011bc0  xor     eax, eax
0x180011bc2  jmp     short loc_180011BC8
0x180011bc4  mov     eax, dword ptr [rsp+28h+arg_0]
0x180011bc8  add     rsp, 20h
0x180011bcc  pop     rbx
0x180011bcd  retn
```
