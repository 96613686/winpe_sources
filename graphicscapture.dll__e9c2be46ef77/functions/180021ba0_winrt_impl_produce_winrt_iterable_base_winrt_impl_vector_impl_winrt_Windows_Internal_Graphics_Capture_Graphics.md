# winrt::impl::produce<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation,std::vector<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation,std::allocator<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>>::get_Current(winrt::impl::struct_Windows_Internal_Graphics_Capture_GraphicsCaptureWindowInformation *)

- ea: `0x180021ba0`
- end: `0x180021c51`
- name: `?get_Current@?$produce@Uiterator@?$iterable_base@U?$vector_impl@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@V?$vector@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@V?$allocator@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@6@@impl@winrt@@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@3@Ucollection_version@23@@winrt@@U?$IIterator@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHPEAUstruct_Windows_Internal_Graphics_Capture_GraphicsCaptureWindowInformation@23@@Z`
- size: `177`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800022f2`
- `0x1800058c4`
- `0x18001f2c0`
- `0x1800219e0`
- `0x180021ba0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation,std::vector<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>>::get_Current(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // xmm1_8
  __int64 result; // rax
  const struct winrt::impl::slim_source_location *v11; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v13[32]; // [rsp+38h] [rbp-20h] BYREF
  int v14; // [rsp+60h] [rbp+8h] BYREF

  v4 = a1 + 16;
  if ( !a1 )
    v4 = 32;
  v5 = a1 + 8;
  if ( !a1 )
    v5 = 24;
  try
  {
    winrt::impl::collection_version::iterator_type::check_version(
      (winrt::impl::collection_version::iterator_type *)v5,
      (const struct winrt::impl::collection_version *)(*(_QWORD *)v4 + 40LL));
    v6 = a1 + 24;
    if ( !a1 )
      v6 = 40;
    v7 = *(_QWORD *)v6;
    v8 = a1 + 32;
    if ( !a1 )
      v8 = 48;
    if ( v7 == *(_QWORD *)v8 )
    {
      v11 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v13);
      winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)pExceptionObject, v11);
      throw (winrt::hresult_out_of_bounds *)pExceptionObject;
    }
    v9 = *(_QWORD *)(v7 + 16);
    *(_OWORD *)a2 = *(_OWORD *)v7;
    *(_QWORD *)(a2 + 16) = v9;
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v14);
  }
  return result;
}

```

## disassembly

```asm
0x180021ba0  mov     [rsp+arg_8], rbx
0x180021ba5  mov     [rsp+arg_10], rsi
0x180021baa  push    rdi
0x180021bab  sub     rsp, 50h
0x180021baf  mov     rdi, rdx
0x180021bb2  mov     rbx, rcx
0x180021bb5  lea     rax, [rcx+10h]
0x180021bb9  mov     ecx, 20h ; ' '
0x180021bbe  test    rbx, rbx
0x180021bc1  cmovz   rax, rcx
0x180021bc5  mov     rdx, [rax]
0x180021bc8  lea     esi, [rcx+8]
0x180021bcb  add     rdx, rsi; struct winrt::impl::collection_version *
0x180021bce  lea     rcx, [rbx+8]
0x180021bd2  lea     eax, [rsi-10h]
0x180021bd5  test    rbx, rbx
0x180021bd8  cmovz   rcx, rax; this
0x180021bdc  call    ?check_version@iterator_type@collection_version@impl@winrt@@QEBAXAEBU234@@Z; winrt::impl::collection_version::iterator_type::check_version(winrt::impl::collection_version const &)
0x180021be1  lea     rax, [rbx+18h]
0x180021be5  test    rbx, rbx
0x180021be8  cmovz   rax, rsi
0x180021bec  mov     rcx, [rax]
0x180021bef  lea     rax, [rbx+20h]
0x180021bf3  lea     edx, [rsi+8]
0x180021bf6  cmovz   rax, rdx
0x180021bfa  cmp     rcx, [rax]
0x180021bfd  jz      short loc_180021C27
0x180021bff  movups  xmm0, xmmword ptr [rcx]
0x180021c02  movsd   xmm1, qword ptr [rcx+10h]
0x180021c07  movups  xmmword ptr [rdi], xmm0
0x180021c0a  movsd   qword ptr [rdi+10h], xmm1
0x180021c0f  xor     eax, eax
0x180021c11  jmp     short loc_180021C17
0x180021c13  mov     eax, [rsp+58h+arg_0]
0x180021c17  mov     rbx, [rsp+58h+arg_8]
0x180021c1c  mov     rsi, [rsp+58h+arg_10]
0x180021c21  add     rsp, 50h
0x180021c25  pop     rdi
0x180021c26  retn
0x180021c27  lea     rcx, [rsp+58h+var_20]
0x180021c2c  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180021c31  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180021c34  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180021c39  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x180021c3e  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x180021c45  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180021c4a  call    _CxxThrowException_0
```
