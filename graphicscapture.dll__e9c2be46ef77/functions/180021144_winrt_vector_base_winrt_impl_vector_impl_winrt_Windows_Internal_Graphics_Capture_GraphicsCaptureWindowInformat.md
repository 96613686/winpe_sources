# winrt::vector_base<winrt::impl::vector_impl<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation,std::vector<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation,std::allocator<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>::RemoveAt(uint)

- ea: `0x180021144`
- end: `0x1800211de`
- name: `?RemoveAt@?$vector_base@U?$vector_impl@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@V?$vector@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@V?$allocator@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@6@@impl@winrt@@UGraphicsCaptureWindowInformation@Capture@Graphics@Internal@Windows@3@@winrt@@QEAAXI@Z`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800210d0`

## callees

- `0x1800022da`
- `0x1800022f2`
- `0x1800058c4`
- `0x18001f2c0`
- `0x180021144`

## pseudocode

```c
void *__fastcall winrt::vector_base<winrt::impl::vector_impl<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation,std::vector<winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Internal::Graphics::Capture::GraphicsCaptureWindowInformation>::RemoveAt(
        volatile signed __int32 *a1,
        unsigned int a2)
{
  __int64 v2; // r9
  __int64 v3; // rbx
  void *result; // rax
  const struct winrt::impl::slim_source_location *v5; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v7[32]; // [rsp+38h] [rbp-20h] BYREF

  v2 = (__int64)(a1 + 2);
  if ( !a1 )
    v2 = 48;
  if ( a2 >= 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*(_QWORD *)(v2 + 8) - *(_QWORD *)v2) >> 3) )
  {
    v5 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v7);
    winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)pExceptionObject, v5);
    throw (winrt::hresult_out_of_bounds *)pExceptionObject;
  }
  _InterlockedIncrement(a1);
  v3 = (__int64)(a1 + 4);
  if ( !a1 )
    v3 = 56;
  result = memmove_0(
             (void *)(*(_QWORD *)v2 + 24LL * a2),
             (const void *)(*(_QWORD *)v2 + 24LL * a2 + 24),
             *(_QWORD *)v3 - (*(_QWORD *)v2 + 24LL * a2 + 24));
  *(_QWORD *)v3 -= 24LL;
  return result;
}

```

## disassembly

```asm
0x180021144  push    rbx
0x180021146  sub     rsp, 50h
0x18002114a  test    rcx, rcx
0x18002114d  lea     r9, [rcx+8]
0x180021151  mov     eax, 30h ; '0'
0x180021156  mov     r8, rcx
0x180021159  cmovz   r9, rax
0x18002115d  mov     ecx, edx
0x18002115f  mov     rdx, 0AAAAAAAAAAAAAAABh
0x180021169  mov     rax, [r9+8]
0x18002116d  sub     rax, [r9]
0x180021170  sar     rax, 3
0x180021174  imul    rax, rdx
0x180021178  cmp     rcx, rax
0x18002117b  jnb     short loc_1800211B5
0x18002117d  lock inc dword ptr [r8]
0x180021181  mov     rax, [r9]
0x180021184  lea     rbx, [r8+10h]
0x180021188  test    r8, r8
0x18002118b  lea     rcx, [rcx+rcx*2]
0x18002118f  lea     rcx, [rax+rcx*8]; void *
0x180021193  mov     eax, 38h ; '8'
0x180021198  cmovz   rbx, rax
0x18002119c  lea     rdx, [rcx+18h]; Src
0x1800211a0  mov     r8, [rbx]
0x1800211a3  sub     r8, rdx; Size
0x1800211a6  call    memmove_0
0x1800211ab  add     qword ptr [rbx], 0FFFFFFFFFFFFFFE8h
0x1800211af  add     rsp, 50h
0x1800211b3  pop     rbx
0x1800211b4  retn
0x1800211b5  lea     rcx, [rsp+58h+var_20]
0x1800211ba  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800211bf  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x1800211c2  lea     rcx, [rsp+58h+pExceptionObject]; this
0x1800211c7  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x1800211cc  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x1800211d3  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800211d8  call    _CxxThrowException_0
```
