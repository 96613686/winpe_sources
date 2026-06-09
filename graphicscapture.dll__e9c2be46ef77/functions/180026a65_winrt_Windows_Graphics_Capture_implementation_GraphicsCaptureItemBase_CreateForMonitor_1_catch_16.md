# _winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase::CreateForMonitor_::_1_::catch$16

- ea: `0x180026a65`
- end: `0x180026ada`
- name: `_winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase::CreateForMonitor_::_1_::catch$16`
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
- `0x180026a65`

## pseudocode

```c
void __fastcall __noreturn winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase::CreateForMonitor_::_1_::catch_16(
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
      L"You do not have permission to capture the given monitor.");
    v4 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)(a2 + 21), -2147024891);
    winrt::hresult_error::hresult_error(a2 + 8, *v4, a2 + 11, v3);
    throw (winrt::hresult_error *)(a2 + 8);
  }
  throw;
}

```

## disassembly

```asm
0x180026a65  mov     [rsp+arg_8], rdx
0x180026a6a  push    rbx
0x180026a6b  push    rbp
0x180026a6c  sub     rsp, 28h
0x180026a70  mov     rbp, rdx
0x180026a73  mov     rax, [rbp+38h]
0x180026a77  cmp     dword ptr [rax+0Ch], 80070005h
0x180026a7e  jnz     short loc_180026AD0
0x180026a80  lea     rcx, [rbp+78h]
0x180026a84  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180026a89  mov     rbx, rax
0x180026a8c  lea     rdx, aYouDoNotHavePe; "You do not have permission to capture t"...
0x180026a93  lea     rcx, [rbp+58h]; this
0x180026a97  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180026a9c  mov     edx, 80070005h; int
0x180026aa1  lea     rcx, [rbp+0A8h]; this
0x180026aa8  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x180026aad  mov     r9, rbx
0x180026ab0  lea     r8, [rbp+58h]
0x180026ab4  mov     edx, [rax]
0x180026ab6  lea     rcx, [rbp+40h]
0x180026aba  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180026abf  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x180026ac6  lea     rcx, [rbp+40h]; pExceptionObject
0x180026aca  call    _CxxThrowException_0
0x180026ad0  xor     edx, edx; pThrowInfo
0x180026ad2  xor     ecx, ecx; pExceptionObject
0x180026ad4  call    _CxxThrowException_0
```
