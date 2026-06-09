# winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer,std::allocator<winrt::Windows::Storage::Streams::IBuffer>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Storage::Streams::IBuffer>>::RemoveAtEnd(void)

- ea: `0x1800126d0`
- end: `0x1800127d4`
- name: `?RemoveAtEnd@?$produce@U?$vector_impl@UIBuffer@Streams@Storage@Windows@winrt@@V?$vector@UIBuffer@Streams@Storage@Windows@winrt@@V?$allocator@UIBuffer@Streams@Storage@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@U?$IVector@UIBuffer@Streams@Storage@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHXZ`
- size: `260`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000395a`
- `0x18000817c`
- `0x1800083ec`
- `0x18001151c`
- `0x1800126d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Storage::Streams::IBuffer>>::RemoveAtEnd(
        unsigned __int64 a1)
{
  __int64 v1; // rbx
  volatile signed __int32 *v2; // rdi
  char v3; // si
  __int64 v4; // r14
  __int64 v5; // rdx
  __int64 v6; // rdi
  __int64 *v7; // rcx
  const struct winrt::impl::slim_source_location *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // [rsp+20h] [rbp-68h] BYREF
  char v12; // [rsp+28h] [rbp-60h]
  _BYTE pExceptionObject[24]; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v14[64]; // [rsp+48h] [rbp-40h] BYREF
  unsigned int v16; // [rsp+90h] [rbp+8h] BYREF

  v1 = (a1 - 16) & ((unsigned __int128)-(__int128)a1 >> 64);
  v2 = (volatile signed __int32 *)(v1 + 40);
  v12 = 0;
  if ( *(_QWORD *)((v1 & -(__int64)(v1 != -40)) + 0x30) == *(_QWORD *)((v1 & -(__int64)(v1 != -40)) + 0x38) )
  {
    v9 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current((__int64)v14);
    winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)pExceptionObject, v9);
    try
    {
      throw (winrt::hresult_out_of_bounds *)pExceptionObject;
    }
    catch ( ... )
    {
      *(_DWORD *)(v10 + 144) = *(_DWORD *)winrt::to_hresult(&v16);
      return v16;
    }
  }
  v3 = 1;
  _InterlockedAdd(v2, 1u);
  v4 = *(_QWORD *)((v1 & -(__int64)(v2 != 0)) + 0x38);
  v5 = *(_QWORD *)(v4 - 8);
  *(_QWORD *)(v4 - 8) = 0;
  v11 = v5;
  v12 = 1;
  v6 = v1 & -(__int64)(v2 != 0);
  v7 = (__int64 *)(*(_QWORD *)(v6 + 56) - 8LL);
  if ( *v7 )
  {
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(v7);
    v3 = v12;
    v5 = v11;
  }
  *(_QWORD *)(v6 + 56) -= 8LL;
  if ( v3 && v5 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v11);
  return 0;
}

```

## disassembly

```asm
0x1800126d0  push    rbx
0x1800126d2  push    rsi
0x1800126d3  push    rdi
0x1800126d4  push    r14
0x1800126d6  sub     rsp, 68h
0x1800126da  lea     rax, [rcx-10h]
0x1800126de  neg     rcx
0x1800126e1  sbb     rbx, rbx
0x1800126e4  and     rbx, rax
0x1800126e7  lea     rdi, [rbx+28h]
0x1800126eb  mov     [rsp+88h+var_60], 0
0x1800126f0  mov     rax, rdi
0x1800126f3  neg     rax
0x1800126f6  sbb     rcx, rcx
0x1800126f9  and     rcx, rbx
0x1800126fc  mov     rax, [rcx+38h]
0x180012700  cmp     [rcx+30h], rax
0x180012704  jz      loc_1800127AA
0x18001270a  mov     esi, 1
0x18001270f  lock add [rdi], esi
0x180012712  mov     rax, rdi
0x180012715  neg     rax
0x180012718  sbb     rcx, rcx
0x18001271b  and     rcx, rbx
0x18001271e  mov     r14, [rcx+38h]
0x180012722  cmp     [rsp+88h+var_60], 0
0x180012727  jz      short loc_180012740
0x180012729  cmp     [rsp+88h+var_68], 0
0x18001272f  jz      short loc_18001273B
0x180012731  lea     rcx, [rsp+88h+var_68]
0x180012736  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18001273b  mov     [rsp+88h+var_60], 0
0x180012740  mov     rdx, [r14-8]
0x180012744  mov     qword ptr [r14-8], 0
0x18001274c  mov     [rsp+88h+var_68], rdx
0x180012751  mov     [rsp+88h+var_60], sil
0x180012756  neg     rdi
0x180012759  sbb     rdi, rdi
0x18001275c  and     rdi, rbx
0x18001275f  mov     rcx, [rdi+38h]
0x180012763  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180012767  cmp     qword ptr [rcx], 0
0x18001276b  jz      short loc_18001277C
0x18001276d  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180012772  mov     sil, [rsp+88h+var_60]
0x180012777  mov     rdx, [rsp+88h+var_68]
0x18001277c  add     qword ptr [rdi+38h], 0FFFFFFFFFFFFFFF8h
0x180012781  test    sil, sil
0x180012784  jz      short loc_180012795
0x180012786  test    rdx, rdx
0x180012789  jz      short loc_180012795
0x18001278b  lea     rcx, [rsp+88h+var_68]
0x180012790  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180012795  xor     eax, eax
0x180012797  jmp     short loc_1800127A0
0x180012799  mov     eax, [rsp+88h+arg_0]
0x1800127a0  add     rsp, 68h
0x1800127a4  pop     r14
0x1800127a6  pop     rdi
0x1800127a7  pop     rsi
0x1800127a8  pop     rbx
0x1800127a9  retn
0x1800127aa  lea     rcx, [rsp+88h+var_40]
0x1800127af  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800127b4  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x1800127b7  lea     rcx, [rsp+88h+pExceptionObject]; this
0x1800127bc  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x1800127c1  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x1800127c8  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x1800127cd  call    _CxxThrowException_0
```
