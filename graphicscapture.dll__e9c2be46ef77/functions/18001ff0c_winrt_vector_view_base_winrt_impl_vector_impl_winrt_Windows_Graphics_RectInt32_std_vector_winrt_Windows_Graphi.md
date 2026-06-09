# winrt::vector_view_base<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32,std::allocator<winrt::Windows::Graphics::RectInt32>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Graphics::RectInt32,winrt::impl::collection_version>::GetAt(uint)

- ea: `0x18001ff0c`
- end: `0x18001ff8b`
- name: `?GetAt@?$vector_view_base@U?$vector_impl@URectInt32@Graphics@Windows@winrt@@V?$vector@URectInt32@Graphics@Windows@winrt@@V?$allocator@URectInt32@Graphics@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@4@@impl@winrt@@URectInt32@Graphics@Windows@3@Ucollection_version@23@@winrt@@QEBA?AURectInt32@Graphics@Windows@2@I@Z`
- size: `127`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18001fdd0`
- `0x18001fe20`

## callees

- `0x1800022f2`
- `0x1800058c4`
- `0x18001f2c0`
- `0x18001ff0c`

## pseudocode

```c
_OWORD *__fastcall winrt::vector_view_base<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Graphics::RectInt32,winrt::impl::collection_version>::GetAt(
        __int64 a1,
        _OWORD *a2,
        unsigned int a3)
{
  __int64 v3; // rax
  __int64 v4; // r9
  __int64 v5; // rax
  __int128 v6; // xmm0
  _OWORD *result; // rax
  const struct winrt::impl::slim_source_location *v8; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v10[32]; // [rsp+38h] [rbp-20h] BYREF

  v3 = a1 + 16;
  if ( !a1 )
    v3 = 56;
  v4 = a1 + 8;
  if ( !a1 )
    v4 = 48;
  if ( a3 >= (unsigned int)((__int64)(*(_QWORD *)v3 - *(_QWORD *)v4) >> 4) )
  {
    v8 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v10);
    winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)pExceptionObject, v8);
    throw (winrt::hresult_out_of_bounds *)pExceptionObject;
  }
  v5 = a1 + 8;
  if ( !a1 )
    v5 = 48;
  v6 = *(_OWORD *)(*(_QWORD *)v5 + 16LL * a3);
  result = a2;
  *a2 = v6;
  return result;
}

```

## disassembly

```asm
0x18001ff0c  sub     rsp, 58h
0x18001ff10  test    rcx, rcx
0x18001ff13  lea     rax, [rcx+10h]
0x18001ff17  mov     r9d, 38h ; '8'
0x18001ff1d  mov     r10d, 30h ; '0'
0x18001ff23  cmovz   rax, r9
0x18001ff27  lea     r9, [rcx+8]
0x18001ff2b  cmovz   r9, r10
0x18001ff2f  mov     rax, [rax]
0x18001ff32  sub     rax, [r9]
0x18001ff35  sar     rax, 4
0x18001ff39  cmp     r8d, eax
0x18001ff3c  jnb     short loc_18001FF62
0x18001ff3e  test    rcx, rcx
0x18001ff41  lea     rax, [rcx+8]
0x18001ff45  mov     ecx, r8d
0x18001ff48  cmovz   rax, r10
0x18001ff4c  add     rcx, rcx
0x18001ff4f  mov     rax, [rax]
0x18001ff52  movups  xmm0, xmmword ptr [rax+rcx*8]
0x18001ff56  mov     rax, rdx
0x18001ff59  movdqu  xmmword ptr [rdx], xmm0
0x18001ff5d  add     rsp, 58h
0x18001ff61  retn
0x18001ff62  lea     rcx, [rsp+58h+var_20]
0x18001ff67  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001ff6c  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18001ff6f  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18001ff74  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x18001ff79  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x18001ff80  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001ff85  call    _CxxThrowException_0
```
