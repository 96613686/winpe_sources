# winrt::vector_view_base<winrt::impl::vector_impl<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation,std::vector<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation,std::allocator<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation,winrt::impl::collection_version>::GetAt(uint)

- ea: `0x18001fe68`
- end: `0x18001ff06`
- name: `?GetAt@?$vector_view_base@U?$vector_impl@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@V?$vector@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@V?$allocator@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@6@@impl@winrt@@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@3@Ucollection_version@23@@winrt@@QEBA?AUGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@2@I@Z`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18001fd30`
- `0x18001fd80`

## callees

- `0x1800022f2`
- `0x1800058c4`
- `0x18001f2c0`
- `0x18001fe68`

## pseudocode

```c
__int64 __fastcall winrt::vector_view_base<winrt::impl::vector_impl<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation,std::vector<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation,winrt::impl::collection_version>::GetAt(
        __int64 a1,
        __int64 a2,
        unsigned int a3)
{
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // xmm1_8
  __int64 result; // rax
  const struct winrt::impl::slim_source_location *v9; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v11[32]; // [rsp+38h] [rbp-20h] BYREF

  v4 = a1 + 16;
  if ( !a1 )
    v4 = 56;
  v5 = a1 + 8;
  if ( !a1 )
    v5 = 48;
  if ( a3 >= -1431655765 * (unsigned int)((__int64)(*(_QWORD *)v4 - *(_QWORD *)v5) >> 3) )
  {
    v9 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v11);
    winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)pExceptionObject, v9);
    throw (winrt::hresult_out_of_bounds *)pExceptionObject;
  }
  v6 = a1 + 8;
  if ( !a1 )
    v6 = 48;
  v7 = *(_QWORD *)(*(_QWORD *)v6 + 24LL * a3 + 16);
  result = a2;
  *(_OWORD *)a2 = *(_OWORD *)(*(_QWORD *)v6 + 24LL * a3);
  *(_QWORD *)(a2 + 16) = v7;
  return result;
}

```

## disassembly

```asm
0x18001fe68  sub     rsp, 58h
0x18001fe6c  mov     r9, rcx
0x18001fe6f  mov     eax, 38h ; '8'
0x18001fe74  add     rcx, 10h
0x18001fe78  mov     r10, rdx
0x18001fe7b  test    r9, r9
0x18001fe7e  mov     edx, 30h ; '0'
0x18001fe83  cmovz   rcx, rax
0x18001fe87  lea     rax, [r9+8]
0x18001fe8b  cmovz   rax, rdx
0x18001fe8f  mov     rcx, [rcx]
0x18001fe92  sub     rcx, [rax]
0x18001fe95  mov     rax, 0AAAAAAAAAAAAAAABh
0x18001fe9f  sar     rcx, 3
0x18001fea3  imul    rcx, rax
0x18001fea7  cmp     r8d, ecx
0x18001feaa  jnb     short loc_18001FEDD
0x18001feac  mov     eax, r8d
0x18001feaf  lea     rcx, [r9+8]
0x18001feb3  test    r9, r9
0x18001feb6  cmovz   rcx, rdx
0x18001feba  lea     rdx, [rax+rax*2]
0x18001febe  mov     rax, [rcx]
0x18001fec1  movups  xmm0, xmmword ptr [rax+rdx*8]
0x18001fec5  movsd   xmm1, qword ptr [rax+rdx*8+10h]
0x18001fecb  mov     rax, r10
0x18001fece  movups  xmmword ptr [r10], xmm0
0x18001fed2  movsd   qword ptr [r10+10h], xmm1
0x18001fed8  add     rsp, 58h
0x18001fedc  retn
0x18001fedd  lea     rcx, [rsp+58h+var_20]
0x18001fee2  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001fee7  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18001feea  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18001feef  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x18001fef4  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x18001fefb  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001ff00  call    _CxxThrowException_0
```
