# winrt::vector_view_base<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer,std::allocator<winrt::Windows::Storage::Streams::IBuffer>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Storage::Streams::IBuffer,winrt::impl::collection_version>::GetMany(uint,winrt::array_view<winrt::Windows::Storage::Streams::IBuffer>)

- ea: `0x180011fa0`
- end: `0x180012048`
- name: `?GetMany@?$vector_view_base@U?$vector_impl@UIBuffer@Streams@Storage@Windows@winrt@@V?$vector@UIBuffer@Streams@Storage@Windows@winrt@@V?$allocator@UIBuffer@Streams@Storage@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UIBuffer@Streams@Storage@Windows@3@Ucollection_version@23@@winrt@@QEBAIIU?$array_view@UIBuffer@Streams@Storage@Windows@winrt@@@2@@Z`
- size: `168`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011d80`
- `0x180011e00`

## callees

- `0x1800083ec`
- `0x180011fa0`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall winrt::vector_view_base<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Storage::Streams::IBuffer,winrt::impl::collection_version>::GetMany(
        __int64 a1,
        unsigned int a2,
        __int64 a3)
{
  __int64 v3; // r9
  __int64 v5; // rax
  __int64 v6; // rcx
  unsigned int v8; // esi
  __int64 v9; // rax
  unsigned int v10; // ecx
  unsigned int v11; // ebp
  __int64 *v12; // rbx
  __int64 *i; // rdi
  __int64 v14; // rcx

  v3 = a1 + 16;
  if ( !a1 )
    v3 = 56;
  v5 = a1 + 8;
  if ( !a1 )
    v5 = 48;
  v6 = (__int64)(*(_QWORD *)v3 - *(_QWORD *)v5) >> 3;
  if ( a2 >= (unsigned int)v6 )
    return 0;
  v8 = *(_DWORD *)(a3 + 8);
  v9 = a1 + 8;
  v10 = v6 - a2;
  if ( v8 >= v10 )
    v8 = v10;
  v11 = v8;
  if ( !a1 )
    v9 = 48;
  if ( v8 )
  {
    v12 = *(__int64 **)a3;
    for ( i = (__int64 *)(*(_QWORD *)v9 + 8LL * a2); ; ++i )
    {
      if ( v12 != i )
      {
        if ( *v12 )
          winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(v12);
        v14 = *i;
        *v12 = *i;
        if ( v14 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
      }
      if ( !--v11 )
        break;
      ++v12;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180011fa0  push    rbx
0x180011fa2  push    rbp
0x180011fa3  push    rsi
0x180011fa4  push    rdi
0x180011fa5  sub     rsp, 28h
0x180011fa9  test    rcx, rcx
0x180011fac  lea     r9, [rcx+10h]
0x180011fb0  mov     r10, rcx
0x180011fb3  mov     eax, 38h ; '8'
0x180011fb8  cmovz   r9, rax
0x180011fbc  mov     r11d, 30h ; '0'
0x180011fc2  lea     rax, [rcx+8]
0x180011fc6  cmovz   rax, r11
0x180011fca  mov     rcx, [r9]
0x180011fcd  sub     rcx, [rax]
0x180011fd0  sar     rcx, 3
0x180011fd4  cmp     edx, ecx
0x180011fd6  jb      short loc_180011FDC
0x180011fd8  xor     eax, eax
0x180011fda  jmp     short loc_18001203F
0x180011fdc  mov     esi, [r8+8]
0x180011fe0  lea     rax, [r10+8]
0x180011fe4  sub     ecx, edx
0x180011fe6  cmp     esi, ecx
0x180011fe8  cmovnb  esi, ecx
0x180011feb  test    r10, r10
0x180011fee  mov     ebp, esi
0x180011ff0  cmovz   rax, r11
0x180011ff4  test    esi, esi
0x180011ff6  jz      short loc_18001203D
0x180011ff8  mov     rax, [rax]
0x180011ffb  mov     rbx, [r8]
0x180011ffe  mov     ecx, edx
0x180012000  lea     rdi, [rax+rcx*8]
0x180012004  cmp     rbx, rdi
0x180012007  jz      short loc_18001202E
0x180012009  cmp     qword ptr [rbx], 0
0x18001200d  jz      short loc_180012017
0x18001200f  mov     rcx, rbx
0x180012012  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180012017  mov     rcx, [rdi]
0x18001201a  mov     [rbx], rcx
0x18001201d  test    rcx, rcx
0x180012020  jz      short loc_18001202E
0x180012022  mov     rax, [rcx]
0x180012025  mov     rax, [rax+8]
0x180012029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001202e  add     ebp, 0FFFFFFFFh
0x180012031  jz      short loc_18001203D
0x180012033  add     rbx, 8
0x180012037  add     rdi, 8
0x18001203b  jmp     short loc_180012004
0x18001203d  mov     eax, esi
0x18001203f  add     rsp, 28h
0x180012043  pop     rdi
0x180012044  pop     rsi
0x180012045  pop     rbp
0x180012046  pop     rbx
0x180012047  retn
```
