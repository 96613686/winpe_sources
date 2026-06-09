# winrt::vector_view_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::GetAt(uint)

- ea: `0x180027a08`
- end: `0x180027acf`
- name: `?GetAt@?$vector_view_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@QEBA?AUhstring@2@I@Z`
- size: `199`
- prototype: `struct winrt::impl::shared_hstring_header **__fastcall(__int64, struct winrt::impl::shared_hstring_header **, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800278f0`
- `0x180027980`

## callees

- `0x18000395a`
- `0x180007eac`
- `0x18000817c`
- `0x180008274`
- `0x18001151c`
- `0x180027a08`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::vector_view_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::GetAt(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2,
        unsigned int a3)
{
  __int64 v3; // r9
  __int64 v5; // rax
  __int64 v6; // r8
  __int64 v7; // rax
  struct winrt::impl::shared_hstring_header *v8; // rdi
  unsigned int v9; // esi
  const void *v10; // rbx
  const struct winrt::impl::slim_source_location *v12; // rax
  _BYTE pExceptionObject[24]; // [rsp+28h] [rbp-60h] BYREF
  _BYTE v14[72]; // [rsp+40h] [rbp-48h] BYREF

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
    v12 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current((__int64)v14);
    winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)pExceptionObject, v12);
    throw (winrt::hresult_out_of_bounds *)pExceptionObject;
  }
  _mm_lfence();
  v7 = a1 + 8;
  if ( !a1 )
    v7 = 48;
  v8 = *(struct winrt::impl::shared_hstring_header **)(*(_QWORD *)v7 + 8 * v3);
  if ( v8 )
  {
    if ( (*(_BYTE *)v8 & 1) == 0 )
    {
      _InterlockedIncrement((volatile signed __int32 *)v8 + 6);
      goto LABEL_12;
    }
    v9 = *((_DWORD *)v8 + 1);
    if ( v9 )
    {
      v10 = (const void *)*((_QWORD *)v8 + 2);
      v8 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)v9, 0x30u);
      memcpy_s((char *)v8 + 28, 2LL * v9, v10, 2LL * v9);
      goto LABEL_12;
    }
  }
  v8 = 0;
LABEL_12:
  *a2 = v8;
  return a2;
}

```

## disassembly

```asm
0x180027a08  push    rbx
0x180027a0a  push    rsi
0x180027a0b  push    rdi
0x180027a0c  push    r14
0x180027a0e  sub     rsp, 68h
0x180027a12  test    rcx, rcx
0x180027a15  mov     r9d, r8d
0x180027a18  mov     r14, rdx
0x180027a1b  lea     rax, [rcx+10h]
0x180027a1f  mov     edx, 38h ; '8'
0x180027a24  lea     r8, [rcx+8]
0x180027a28  cmovz   rax, rdx
0x180027a2c  mov     edx, 30h ; '0'; unsigned int
0x180027a31  cmovz   r8, rdx
0x180027a35  mov     rax, [rax]
0x180027a38  sub     rax, [r8]
0x180027a3b  sar     rax, 3
0x180027a3f  cmp     r9d, eax
0x180027a42  jnb     short loc_180027AA6
0x180027a44  lfence
0x180027a47  test    rcx, rcx
0x180027a4a  lea     rax, [rcx+8]
0x180027a4e  cmovz   rax, rdx
0x180027a52  mov     rax, [rax]
0x180027a55  mov     rdi, [rax+r9*8]
0x180027a59  test    rdi, rdi
0x180027a5c  jnz     short loc_180027A62
0x180027a5e  xor     edi, edi
0x180027a60  jmp     short loc_180027A96
0x180027a62  test    byte ptr [rdi], 1
0x180027a65  jnz     short loc_180027A6D
0x180027a67  lock inc dword ptr [rdi+18h]
0x180027a6b  jmp     short loc_180027A96
0x180027a6d  mov     esi, [rdi+4]
0x180027a70  test    esi, esi
0x180027a72  jz      short loc_180027A5E
0x180027a74  mov     rbx, [rdi+10h]
0x180027a78  mov     ecx, esi; this
0x180027a7a  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180027a7f  mov     edx, esi
0x180027a81  mov     r8, rbx; Source
0x180027a84  add     rdx, rdx; DestinationSize
0x180027a87  mov     rdi, rax
0x180027a8a  mov     r9, rdx; SourceSize
0x180027a8d  lea     rcx, [rax+1Ch]; Destination
0x180027a91  call    memcpy_s
0x180027a96  mov     [r14], rdi
0x180027a99  mov     rax, r14
0x180027a9c  add     rsp, 68h
0x180027aa0  pop     r14
0x180027aa2  pop     rdi
0x180027aa3  pop     rsi
0x180027aa4  pop     rbx
0x180027aa5  retn
0x180027aa6  lea     rcx, [rsp+88h+var_48]
0x180027aab  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180027ab0  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180027ab3  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180027ab8  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x180027abd  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x180027ac4  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180027ac9  call    _CxxThrowException_0
```
