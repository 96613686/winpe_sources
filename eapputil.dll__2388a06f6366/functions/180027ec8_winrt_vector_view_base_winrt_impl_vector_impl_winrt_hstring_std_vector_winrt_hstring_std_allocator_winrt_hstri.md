# winrt::vector_view_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::GetMany(uint,winrt::array_view<winrt::hstring>)

- ea: `0x180027ec8`
- end: `0x180027f63`
- name: `?GetMany@?$vector_view_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@QEBAIIU?$array_view@Uhstring@winrt@@@2@@Z`
- size: `155`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180027cd0`
- `0x180027d50`

## callees

- `0x180017fb8`
- `0x180027ec8`

## pseudocode

```c
__int64 __fastcall winrt::vector_view_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::GetMany(
        __int64 a1,
        unsigned int a2,
        __int64 *a3)
{
  __int64 v3; // r9
  __int64 v5; // rax
  __int64 v6; // rcx
  unsigned int v8; // esi
  __int64 v9; // rax
  unsigned int v10; // ecx
  __int64 v11; // rbx
  __int64 v12; // rdi
  __int64 v13; // rbx
  unsigned int v14; // ebp

  v3 = a1 + 16;
  if ( !a1 )
    v3 = 56;
  v5 = a1 + 8;
  if ( !a1 )
    v5 = 48;
  v6 = (__int64)(*(_QWORD *)v3 - *(_QWORD *)v5) >> 3;
  if ( a2 >= (unsigned int)v6 )
    return 0;
  v8 = *((_DWORD *)a3 + 2);
  v9 = a1 + 8;
  v10 = v6 - a2;
  if ( v8 >= v10 )
    v8 = v10;
  if ( !a1 )
    v9 = 48;
  if ( v8 )
  {
    v11 = *a3;
    v12 = *(_QWORD *)v9 + 8LL * a2;
    winrt::hstring::operator=(*a3, v12);
    v13 = v11 + 8;
    v14 = v8 - 1;
    if ( v8 != 1 )
    {
      do
      {
        v12 += 8;
        winrt::hstring::operator=(v13, v12);
        v13 += 8;
        --v14;
      }
      while ( v14 );
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180027ec8  push    rbx
0x180027eca  push    rbp
0x180027ecb  push    rsi
0x180027ecc  push    rdi
0x180027ecd  sub     rsp, 28h
0x180027ed1  test    rcx, rcx
0x180027ed4  lea     r9, [rcx+10h]
0x180027ed8  mov     r10, rcx
0x180027edb  mov     eax, 38h ; '8'
0x180027ee0  cmovz   r9, rax
0x180027ee4  mov     r11d, 30h ; '0'
0x180027eea  lea     rax, [rcx+8]
0x180027eee  cmovz   rax, r11
0x180027ef2  mov     rcx, [r9]
0x180027ef5  sub     rcx, [rax]
0x180027ef8  sar     rcx, 3
0x180027efc  cmp     edx, ecx
0x180027efe  jb      short loc_180027F04
0x180027f00  xor     eax, eax
0x180027f02  jmp     short loc_180027F5A
0x180027f04  mov     esi, [r8+8]
0x180027f08  lea     rax, [r10+8]
0x180027f0c  sub     ecx, edx
0x180027f0e  cmp     esi, ecx
0x180027f10  cmovnb  esi, ecx
0x180027f13  test    r10, r10
0x180027f16  cmovz   rax, r11
0x180027f1a  test    esi, esi
0x180027f1c  jz      short loc_180027F58
0x180027f1e  mov     rax, [rax]
0x180027f21  mov     rbx, [r8]
0x180027f24  mov     ecx, edx
0x180027f26  lea     rdi, [rax+rcx*8]
0x180027f2a  mov     rcx, rbx
0x180027f2d  mov     rdx, rdi
0x180027f30  call    ??4hstring@winrt@@QEAAAEAU01@AEBU01@@Z; winrt::hstring::operator=(winrt::hstring const &)
0x180027f35  add     rbx, 8
0x180027f39  lea     ebp, [rsi-1]
0x180027f3c  test    ebp, ebp
0x180027f3e  jz      short loc_180027F58
0x180027f40  add     rdi, 8
0x180027f44  mov     rcx, rbx
0x180027f47  mov     rdx, rdi
0x180027f4a  call    ??4hstring@winrt@@QEAAAEAU01@AEBU01@@Z; winrt::hstring::operator=(winrt::hstring const &)
0x180027f4f  add     rbx, 8
0x180027f53  add     ebp, 0FFFFFFFFh
0x180027f56  jnz     short loc_180027F40
0x180027f58  mov     eax, esi
0x180027f5a  add     rsp, 28h
0x180027f5e  pop     rdi
0x180027f5f  pop     rsi
0x180027f60  pop     rbp
0x180027f61  pop     rbx
0x180027f62  retn
```
