# winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation,std::vector<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation,std::allocator<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>>::InsertAt(uint,winrt::impl::struct_Windows_Internal_Graphics_Capture_GraphicsCaptureWindowInformation)

- ea: `0x180020990`
- end: `0x180020a3b`
- name: `?InsertAt@?$produce@U?$vector_impl@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@V?$vector@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@V?$allocator@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@6@@impl@winrt@@U?$IVector@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIUstruct_Windows_Internal_Graphics_Capture_GraphicsCaptureWindowInformation@23@@Z`
- size: `171`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800022f2`
- `0x1800058c4`
- `0x18001ea94`
- `0x18001f2c0`
- `0x180020990`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation,std::vector<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>>::InsertAt(
        __int64 a1,
        unsigned int a2,
        __int64 a3)
{
  __int64 v3; // r9
  unsigned __int64 v4; // rax
  __int64 v5; // rcx
  __int64 result; // rax
  const struct winrt::impl::slim_source_location *v7; // rax
  int v8; // [rsp+20h] [rbp-48h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+28h] [rbp-40h] BYREF
  _BYTE v10[40]; // [rsp+40h] [rbp-28h] BYREF

  v3 = (a1 - 16) & -(__int64)(a1 != 0);
  v4 = 0xAAAAAAAAAAAAAAABuLL
     * ((__int64)(*(_QWORD *)((v3 & -(__int64)(v3 != -40)) + 0x38) - *(_QWORD *)((v3 & -(__int64)(v3 != -40)) + 0x30)) >> 3);
  if ( a2 > v4 )
  {
    v7 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v10);
    winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)pExceptionObject, v7);
    throw (winrt::hresult_out_of_bounds *)pExceptionObject;
  }
  _InterlockedIncrement((volatile signed __int32 *)(v3 + 40));
  if ( v3 == -40 )
  {
    v3 = 0;
    v5 = 48;
  }
  else
  {
    v5 = v3 + 48;
  }
  try
  {
    std::vector<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>::emplace<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation const &>(
      v5,
      &v8,
      *(_QWORD *)(v3 + 48) + 24LL * a2,
      a3);
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v8);
  }
  return result;
}

```

## disassembly

```asm
0x180020990  sub     rsp, 68h
0x180020994  mov     r10, r8
0x180020997  lea     rax, [rcx-10h]
0x18002099b  neg     rcx
0x18002099e  sbb     r9, r9
0x1800209a1  and     r9, rax
0x1800209a4  lea     r8, [r9+28h]
0x1800209a8  mov     rax, r8
0x1800209ab  neg     rax
0x1800209ae  sbb     rcx, rcx
0x1800209b1  and     rcx, r9
0x1800209b4  mov     edx, edx
0x1800209b6  mov     rax, [rcx+38h]
0x1800209ba  sub     rax, [rcx+30h]
0x1800209be  sar     rax, 3
0x1800209c2  mov     rcx, 0AAAAAAAAAAAAAAABh
0x1800209cc  imul    rax, rcx
0x1800209d0  cmp     rdx, rax
0x1800209d3  ja      short loc_180020A11
0x1800209d5  lock inc dword ptr [r8]
0x1800209d9  test    r8, r8
0x1800209dc  jz      short loc_1800209E4
0x1800209de  lea     rcx, [r9+30h]
0x1800209e2  jmp     short loc_1800209EB
0x1800209e4  xor     r9d, r9d
0x1800209e7  lea     ecx, [r9+30h]
0x1800209eb  lea     rdx, [rdx+rdx*2]
0x1800209ef  mov     rax, [r9+30h]
0x1800209f3  lea     r8, [rax+rdx*8]
0x1800209f7  mov     r9, r10
0x1800209fa  lea     rdx, [rsp+68h+var_48]
0x1800209ff  call    ??$emplace@AEBUGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@@?$vector@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@V?$allocator@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@@std@@@std@@@1@AEBUGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@@Z; std::vector<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>::emplace<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation const &>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>>>,winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation const &)
0x180020a04  xor     eax, eax
0x180020a06  jmp     short loc_180020A0C
0x180020a08  mov     eax, [rsp+68h+var_48]
0x180020a0c  add     rsp, 68h
0x180020a10  retn
0x180020a11  lea     rcx, [rsp+68h+var_28]
0x180020a16  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180020a1b  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180020a1e  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180020a23  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x180020a28  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x180020a2f  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180020a34  call    _CxxThrowException_0
```
