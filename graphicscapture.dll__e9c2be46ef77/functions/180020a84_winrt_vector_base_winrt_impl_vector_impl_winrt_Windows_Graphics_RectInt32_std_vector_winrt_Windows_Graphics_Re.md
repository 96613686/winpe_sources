# winrt::vector_base<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32,std::allocator<winrt::Windows::Graphics::RectInt32>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Graphics::RectInt32>::InsertAt(uint,winrt::Windows::Graphics::RectInt32 const &)

- ea: `0x180020a84`
- end: `0x180020b5b`
- name: `?InsertAt@?$vector_base@U?$vector_impl@URectInt32@Graphics@Windows@winrt@@V?$vector@URectInt32@Graphics@Windows@winrt@@V?$allocator@URectInt32@Graphics@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@4@@impl@winrt@@URectInt32@Graphics@Windows@3@@winrt@@QEAAXIAEBURectInt32@Graphics@Windows@2@@Z`
- size: `215`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180020a50`

## callees

- `0x1800022da`
- `0x1800022f2`
- `0x1800058c4`
- `0x18001e314`
- `0x18001f2c0`
- `0x180020a84`

## pseudocode

```c
__int64 __fastcall winrt::vector_base<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Graphics::RectInt32>::InsertAt(
        volatile signed __int32 *a1,
        unsigned int a2,
        _OWORD *a3)
{
  __int64 v4; // rcx
  bool v5; // zf
  __int64 result; // rax
  char *v7; // r9
  __int64 v8; // r10
  char *v9; // rbx
  __int128 v10; // xmm6
  const void *v11; // rdx
  const struct winrt::impl::slim_source_location *v12; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v14[24]; // [rsp+38h] [rbp-30h] BYREF

  v4 = (__int64)(a1 + 2);
  if ( !a1 )
    v4 = 48;
  if ( a2 > (unsigned __int64)((__int64)(*(_QWORD *)(v4 + 8) - *(_QWORD *)v4) >> 4) )
  {
    v12 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v14);
    winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)pExceptionObject, v12);
    throw (winrt::hresult_out_of_bounds *)pExceptionObject;
  }
  _InterlockedIncrement(a1);
  v5 = a1 == 0;
  result = (__int64)(a1 + 2);
  v7 = *(char **)(v4 + 8);
  if ( v5 )
    result = 48;
  v8 = 16LL * a2;
  v9 = (char *)(v8 + *(_QWORD *)result);
  if ( v7 == *(char **)(v4 + 16) )
    return std::vector<winrt::Windows::Graphics::RectInt32>::_Emplace_reallocate<winrt::Windows::Graphics::RectInt32>(
             v4,
             v8 + *(_QWORD *)result);
  if ( v9 == v7 )
  {
    *(_OWORD *)v7 = *a3;
    *(_QWORD *)(v4 + 8) += 16LL;
  }
  else
  {
    v10 = *a3;
    v11 = (const void *)(v8 + *(_QWORD *)result);
    *(_OWORD *)v7 = *((_OWORD *)v7 - 1);
    *(_QWORD *)(v4 + 8) += 16LL;
    result = (__int64)memmove_0(v9 + 16, v11, v7 - v9 - 16);
    *(_OWORD *)v9 = v10;
  }
  return result;
}

```

## disassembly

```asm
0x180020a84  push    rbx
0x180020a86  sub     rsp, 60h
0x180020a8a  mov     r9, rcx
0x180020a8d  mov     r10d, edx
0x180020a90  add     rcx, 8
0x180020a94  movaps  [rsp+68h+var_18], xmm6
0x180020a99  test    r9, r9
0x180020a9c  mov     r11d, 30h ; '0'
0x180020aa2  cmovz   rcx, r11
0x180020aa6  mov     rax, [rcx+8]
0x180020aaa  sub     rax, [rcx]
0x180020aad  sar     rax, 4
0x180020ab1  cmp     r10, rax
0x180020ab4  ja      short loc_180020B32
0x180020ab6  lock inc dword ptr [r9]
0x180020aba  test    r9, r9
0x180020abd  lea     rax, [r9+8]
0x180020ac1  mov     r9, [rcx+8]
0x180020ac5  cmovz   rax, r11
0x180020ac9  shl     r10, 4
0x180020acd  mov     rbx, [rax]
0x180020ad0  add     rbx, r10
0x180020ad3  cmp     r9, [rcx+10h]
0x180020ad7  jz      short loc_180020B1F
0x180020ad9  cmp     rbx, r9
0x180020adc  jnz     short loc_180020AEE
0x180020ade  movups  xmm0, xmmword ptr [r8]
0x180020ae2  movdqu  xmmword ptr [r9], xmm0
0x180020ae7  add     qword ptr [rcx+8], 10h
0x180020aec  jmp     short loc_180020B27
0x180020aee  movups  xmm6, xmmword ptr [r8]
0x180020af2  mov     r8, r9
0x180020af5  mov     rdx, rbx; Src
0x180020af8  movups  xmm0, xmmword ptr [r9-10h]
0x180020afd  sub     r8, rbx
0x180020b00  add     r8, 0FFFFFFFFFFFFFFF0h; Size
0x180020b04  movdqu  xmmword ptr [r9], xmm0
0x180020b09  add     qword ptr [rcx+8], 10h
0x180020b0e  sub     r9, r8
0x180020b11  mov     rcx, r9; void *
0x180020b14  call    memmove_0
0x180020b19  movdqu  xmmword ptr [rbx], xmm6
0x180020b1d  jmp     short loc_180020B27
0x180020b1f  mov     rdx, rbx
0x180020b22  call    ??$_Emplace_reallocate@URectInt32@Graphics@Windows@winrt@@@?$vector@URectInt32@Graphics@Windows@winrt@@V?$allocator@URectInt32@Graphics@Windows@winrt@@@std@@@std@@AEAAPEAURectInt32@Graphics@Windows@winrt@@QEAU2345@$$QEAU2345@@Z; std::vector<winrt::Windows::Graphics::RectInt32>::_Emplace_reallocate<winrt::Windows::Graphics::RectInt32>(winrt::Windows::Graphics::RectInt32 * const,winrt::Windows::Graphics::RectInt32 &&)
0x180020b27  movaps  xmm6, [rsp+68h+var_18]
0x180020b2c  add     rsp, 60h
0x180020b30  pop     rbx
0x180020b31  retn
0x180020b32  lea     rcx, [rsp+68h+var_30]
0x180020b37  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180020b3c  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180020b3f  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180020b44  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x180020b49  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x180020b50  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180020b55  call    _CxxThrowException_0
```
