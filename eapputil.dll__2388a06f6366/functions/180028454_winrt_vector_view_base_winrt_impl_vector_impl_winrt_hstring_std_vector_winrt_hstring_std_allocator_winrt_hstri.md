# winrt::vector_view_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::IndexOf(winrt::hstring const &,uint &)

- ea: `0x180028454`
- end: `0x18002851f`
- name: `?IndexOf@?$vector_view_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@QEBA_NAEBUhstring@2@AEAI@Z`
- size: `203`
- prototype: `bool __fastcall(__int64, __int64 *, _DWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800283c0`
- `0x180028410`

## callees

- `0x180025228`
- `0x180028454`

## pseudocode

```c
bool __fastcall winrt::vector_view_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::IndexOf(
        __int64 a1,
        __int64 *a2,
        _DWORD *a3)
{
  __int64 v3; // r14
  __int64 v4; // r15
  __int64 *v8; // rbx
  __int64 *v9; // rsi
  __int64 v10; // rax
  __int64 v11; // rcx
  const wchar_t *v12; // rdx
  __int64 v13; // rax
  size_t v14; // r8
  const wchar_t *v15; // r9
  __int64 v16; // rax
  __int64 v17; // rbx

  v3 = a1 + 8;
  v4 = a1 + 16;
  if ( !a1 )
    v3 = 48;
  if ( !a1 )
    v4 = 56;
  v8 = *(__int64 **)v3;
  v9 = *(__int64 **)v4;
  while ( v8 != v9 )
  {
    v10 = *v8;
    if ( *v8 )
    {
      v11 = *(unsigned int *)(v10 + 4);
      v12 = *(const wchar_t **)(v10 + 16);
    }
    else
    {
      v11 = 0;
      v12 = &Src;
    }
    v13 = *a2;
    if ( *a2 )
    {
      v14 = *(unsigned int *)(v13 + 4);
      v15 = *(const wchar_t **)(v13 + 16);
    }
    else
    {
      v14 = 0;
      v15 = &Src;
    }
    if ( v14 == v11 && (!v14 || !wmemcmp(v15, v12, v14)) )
      break;
    ++v8;
  }
  v16 = a1 + 8;
  v17 = ((__int64)v8 - *(_QWORD *)v3) >> 3;
  *a3 = v17;
  if ( !a1 )
    v16 = 48;
  return (unsigned int)v17 < (unsigned int)((__int64)(*(_QWORD *)v4 - *(_QWORD *)v16) >> 3);
}

```

## disassembly

```asm
0x180028454  push    rbx
0x180028456  push    rbp
0x180028457  push    rsi
0x180028458  push    rdi
0x180028459  push    r12
0x18002845b  push    r13
0x18002845d  push    r14
0x18002845f  push    r15
0x180028461  sub     rsp, 28h
0x180028465  mov     r13d, 30h ; '0'
0x18002846b  lea     r14, [rcx+8]
0x18002846f  test    rcx, rcx
0x180028472  lea     r15, [rcx+10h]
0x180028476  mov     r12, r8
0x180028479  mov     rbp, rdx
0x18002847c  cmovz   r14, r13
0x180028480  mov     rdi, rcx
0x180028483  lea     eax, [r13+8]
0x180028487  cmovz   r15, rax
0x18002848b  mov     rbx, [r14]
0x18002848e  mov     rsi, [r15]
0x180028491  jmp     short loc_1800284E4
0x180028493  mov     rax, [rbx]
0x180028496  test    rax, rax
0x180028499  jz      short loc_1800284A4
0x18002849b  mov     ecx, [rax+4]
0x18002849e  mov     rdx, [rax+10h]
0x1800284a2  jmp     short loc_1800284AD
0x1800284a4  xor     ecx, ecx
0x1800284a6  lea     rdx, Src; S2
0x1800284ad  mov     rax, [rbp+0]
0x1800284b1  test    rax, rax
0x1800284b4  jz      short loc_1800284C0
0x1800284b6  mov     r8d, [rax+4]
0x1800284ba  mov     r9, [rax+10h]
0x1800284be  jmp     short loc_1800284CA
0x1800284c0  xor     r8d, r8d; N
0x1800284c3  lea     r9, Src
0x1800284ca  cmp     r8, rcx
0x1800284cd  jnz     short loc_1800284E0
0x1800284cf  test    r8, r8
0x1800284d2  jz      short loc_1800284E9
0x1800284d4  mov     rcx, r9; S1
0x1800284d7  call    wmemcmp
0x1800284dc  test    eax, eax
0x1800284de  jz      short loc_1800284E9
0x1800284e0  add     rbx, 8
0x1800284e4  cmp     rbx, rsi
0x1800284e7  jnz     short loc_180028493
0x1800284e9  sub     rbx, [r14]
0x1800284ec  lea     rax, [rdi+8]
0x1800284f0  sar     rbx, 3
0x1800284f4  test    rdi, rdi
0x1800284f7  mov     [r12], ebx
0x1800284fb  mov     rcx, [r15]
0x1800284fe  cmovz   rax, r13
0x180028502  sub     rcx, [rax]
0x180028505  sar     rcx, 3
0x180028509  cmp     ebx, ecx
0x18002850b  setb    al
0x18002850e  add     rsp, 28h
0x180028512  pop     r15
0x180028514  pop     r14
0x180028516  pop     r13
0x180028518  pop     r12
0x18002851a  pop     rdi
0x18002851b  pop     rsi
0x18002851c  pop     rbp
0x18002851d  pop     rbx
0x18002851e  retn
```
