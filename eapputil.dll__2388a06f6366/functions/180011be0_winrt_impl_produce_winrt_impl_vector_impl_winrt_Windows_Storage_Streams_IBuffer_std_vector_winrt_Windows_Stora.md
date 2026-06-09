# winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer,std::allocator<winrt::Windows::Storage::Streams::IBuffer>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Storage::Streams::IBuffer>>::GetAt(uint,void * *)

- ea: `0x180011be0`
- end: `0x180011c3f`
- name: `?GetAt@?$produce@U?$vector_impl@UIBuffer@Streams@Storage@Windows@winrt@@V?$vector@UIBuffer@Streams@Storage@Windows@winrt@@V?$allocator@UIBuffer@Streams@Storage@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@U?$IVectorView@UIBuffer@Streams@Storage@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIPEAPEAX@Z`
- size: `95`
- prototype: `__int64 __fastcall(__int64, unsigned int, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800083ec`
- `0x180011be0`
- `0x180011c48`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Storage::Streams::IBuffer>>::GetAt(
        __int64 a1,
        unsigned int a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  __int64 *v6; // rax
  __int64 v7; // rcx
  __int64 v9; // [rsp+30h] [rbp+8h] BYREF

  *a3 = 0;
  v5 = a1 + 16;
  if ( !a1 )
    v5 = 40;
  v6 = (__int64 *)winrt::vector_view_base<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Storage::Streams::IBuffer,winrt::impl::collection_version>::GetAt(
                    v5,
                    &v9,
                    a2);
  v7 = *v6;
  *v6 = 0;
  *a3 = v7;
  if ( v9 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v9);
  return 0;
}

```

## disassembly

```asm
0x180011be0  push    rbx
0x180011be2  sub     rsp, 20h
0x180011be6  mov     rbx, r8
0x180011be9  mov     rax, rcx
0x180011bec  mov     qword ptr [r8], 0
0x180011bf3  add     rcx, 10h
0x180011bf7  mov     r8d, 28h ; '('
0x180011bfd  test    rax, rax
0x180011c00  cmovz   rcx, r8
0x180011c04  mov     r8d, edx
0x180011c07  lea     rdx, [rsp+28h+arg_0]
0x180011c0c  call    ?GetAt@?$vector_view_base@U?$vector_impl@UIBuffer@Streams@Storage@Windows@winrt@@V?$vector@UIBuffer@Streams@Storage@Windows@winrt@@V?$allocator@UIBuffer@Streams@Storage@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UIBuffer@Streams@Storage@Windows@3@Ucollection_version@23@@winrt@@QEBA?AUIBuffer@Streams@Storage@Windows@2@I@Z; winrt::vector_view_base<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Storage::Streams::IBuffer,winrt::impl::collection_version>::GetAt(uint)
0x180011c11  mov     rcx, [rax]
0x180011c14  mov     qword ptr [rax], 0
0x180011c1b  mov     [rbx], rcx
0x180011c1e  cmp     [rsp+28h+arg_0], 0
0x180011c24  jz      short loc_180011C30
0x180011c26  lea     rcx, [rsp+28h+arg_0]
0x180011c2b  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180011c30  xor     eax, eax
0x180011c32  jmp     short loc_180011C38
0x180011c34  mov     eax, dword ptr [rsp+28h+arg_0]
0x180011c38  add     rsp, 20h
0x180011c3c  pop     rbx
0x180011c3d  retn
```
