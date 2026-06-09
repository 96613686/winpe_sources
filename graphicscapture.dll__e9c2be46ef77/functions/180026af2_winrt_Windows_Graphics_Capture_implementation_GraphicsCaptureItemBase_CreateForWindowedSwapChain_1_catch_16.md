# _winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase::CreateForWindowedSwapChain_::_1_::catch$16

- ea: `0x180026af2`
- end: `0x180026b67`
- name: `_winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase::CreateForWindowedSwapChain_::_1_::catch$16`
- size: `117`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800022f2`
- `0x180003330`
- `0x180003384`
- `0x1800058c4`
- `0x18000eafc`
- `0x180026af2`

## pseudocode

```c
void __fastcall __noreturn winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase::CreateForWindowedSwapChain_::_1_::catch_16(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v3; // rbx
  unsigned int *v4; // rax

  if ( *(_DWORD *)(a2[7] + 12LL) == -2147024891 )
  {
    v3 = winrt::impl::slim_source_location::current(a2 + 15);
    winrt::param::hstring::hstring(
      (winrt::param::hstring *)(a2 + 11),
      L"You do not have permission to capture the given window.");
    v4 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)(a2 + 22), -2147024891);
    winrt::hresult_error::hresult_error(a2 + 8, *v4, a2 + 11, v3);
    throw (winrt::hresult_error *)(a2 + 8);
  }
  throw;
}

```

## disassembly

```asm
0x180026af2  mov     [rsp+arg_8], rdx
0x180026af7  push    rbx
0x180026af8  push    rbp
0x180026af9  sub     rsp, 28h
0x180026afd  mov     rbp, rdx
0x180026b00  mov     rax, [rbp+38h]
0x180026b04  cmp     dword ptr [rax+0Ch], 80070005h
0x180026b0b  jnz     short loc_180026B5D
0x180026b0d  lea     rcx, [rbp+78h]
0x180026b11  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180026b16  mov     rbx, rax
0x180026b19  lea     rdx, aYouDoNotHavePe_0; "You do not have permission to capture t"...
0x180026b20  lea     rcx, [rbp+58h]; this
0x180026b24  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180026b29  mov     edx, 80070005h; int
0x180026b2e  lea     rcx, [rbp+0B0h]; this
0x180026b35  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x180026b3a  mov     r9, rbx
0x180026b3d  lea     r8, [rbp+58h]
0x180026b41  mov     edx, [rax]
0x180026b43  lea     rcx, [rbp+40h]
0x180026b47  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180026b4c  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x180026b53  lea     rcx, [rbp+40h]; pExceptionObject
0x180026b57  call    _CxxThrowException_0
0x180026b5d  xor     edx, edx; pThrowInfo
0x180026b5f  xor     ecx, ecx; pExceptionObject
0x180026b61  call    _CxxThrowException_0
```
