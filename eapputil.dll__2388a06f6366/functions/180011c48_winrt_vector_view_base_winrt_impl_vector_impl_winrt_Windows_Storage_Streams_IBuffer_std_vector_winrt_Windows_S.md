# winrt::vector_view_base<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer,std::allocator<winrt::Windows::Storage::Streams::IBuffer>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Storage::Streams::IBuffer,winrt::impl::collection_version>::GetAt(uint)

- ea: `0x180011c48`
- end: `0x180011cdb`
- name: `?GetAt@?$vector_view_base@U?$vector_impl@UIBuffer@Streams@Storage@Windows@winrt@@V?$vector@UIBuffer@Streams@Storage@Windows@winrt@@V?$allocator@UIBuffer@Streams@Storage@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UIBuffer@Streams@Storage@Windows@3@Ucollection_version@23@@winrt@@QEBA?AUIBuffer@Streams@Storage@Windows@2@I@Z`
- size: `147`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180011b70`
- `0x180011be0`

## callees

- `0x18000395a`
- `0x18000817c`
- `0x18001151c`
- `0x180011c48`
- `0x180033010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall winrt::vector_view_base<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Storage::Streams::IBuffer,winrt::impl::collection_version>::GetAt(
        __int64 a1,
        _QWORD *a2,
        unsigned int a3)
{
  __int64 v3; // r9
  __int64 v5; // rax
  __int64 v6; // r8
  __int64 v7; // rax
  __int64 v8; // rcx
  const struct winrt::impl::slim_source_location *v10; // rax
  _BYTE pExceptionObject[24]; // [rsp+28h] [rbp-40h] BYREF
  _BYTE v12[40]; // [rsp+40h] [rbp-28h] BYREF

  v3 = a3;
  v5 = a1 + 16;
  v6 = a1 + 8;
  if ( !a1 )
  {
    v5 = 56;
    v6 = 48;
  }
  if ( (unsigned int)v3 >= (unsigned int)((__int64)(*(_QWORD *)v5 - *(_QWORD *)v6) >> 3) )
  {
    v10 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current((__int64)v12);
    winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)pExceptionObject, v10);
    throw (winrt::hresult_out_of_bounds *)pExceptionObject;
  }
  _mm_lfence();
  v7 = a1 + 8;
  if ( !a1 )
    v7 = 48;
  v8 = *(_QWORD *)(*(_QWORD *)v7 + 8 * v3);
  *a2 = v8;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
  return a2;
}

```

## disassembly

```asm
0x180011c48  push    rbx
0x180011c4a  sub     rsp, 60h
0x180011c4e  test    rcx, rcx
0x180011c51  mov     r9d, r8d
0x180011c54  mov     rbx, rdx
0x180011c57  lea     rax, [rcx+10h]
0x180011c5b  mov     edx, 38h ; '8'
0x180011c60  lea     r8, [rcx+8]
0x180011c64  cmovz   rax, rdx
0x180011c68  mov     edx, 30h ; '0'
0x180011c6d  cmovz   r8, rdx
0x180011c71  mov     rax, [rax]
0x180011c74  sub     rax, [r8]
0x180011c77  sar     rax, 3
0x180011c7b  cmp     r9d, eax
0x180011c7e  jnb     short loc_180011CB2
0x180011c80  lfence
0x180011c83  test    rcx, rcx
0x180011c86  lea     rax, [rcx+8]
0x180011c8a  cmovz   rax, rdx
0x180011c8e  mov     rax, [rax]
0x180011c91  mov     rcx, [rax+r9*8]
0x180011c95  mov     [rbx], rcx
0x180011c98  test    rcx, rcx
0x180011c9b  jz      short loc_180011CA9
0x180011c9d  mov     rax, [rcx]
0x180011ca0  mov     rax, [rax+8]
0x180011ca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ca9  mov     rax, rbx
0x180011cac  add     rsp, 60h
0x180011cb0  pop     rbx
0x180011cb1  retn
0x180011cb2  lea     rcx, [rsp+68h+var_28]
0x180011cb7  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180011cbc  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180011cbf  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180011cc4  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x180011cc9  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x180011cd0  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180011cd5  call    _CxxThrowException_0
```
