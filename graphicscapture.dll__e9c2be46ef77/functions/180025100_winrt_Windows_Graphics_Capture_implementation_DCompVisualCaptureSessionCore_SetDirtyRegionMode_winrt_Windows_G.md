# winrt::Windows::Graphics::Capture::implementation::DCompVisualCaptureSessionCore::SetDirtyRegionMode(winrt::Windows::Graphics::Capture::GraphicsCaptureDirtyRegionMode)

- ea: `0x180025100`
- end: `0x180025179`
- name: `?SetDirtyRegionMode@DCompVisualCaptureSessionCore@implementation@Capture@Graphics@Windows@winrt@@UEAAXW4GraphicsCaptureDirtyRegionMode@3456@@Z`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800022f2`
- `0x1800058c4`
- `0x18000ea0c`
- `0x1800125ec`
- `0x180025100`
- `0x180028010`

## pseudocode

```c
__int64 __fastcall winrt::Windows::Graphics::Capture::implementation::DCompVisualCaptureSessionCore::SetDirtyRegionMode(
        __int64 a1,
        int a2)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  unsigned int v4; // eax
  const struct winrt::impl::slim_source_location *v6; // rax
  int pExceptionObject; // [rsp+20h] [rbp-38h] BYREF
  __int128 v8; // [rsp+28h] [rbp-30h]
  _BYTE v9[32]; // [rsp+38h] [rbp-20h] BYREF
  char v10; // [rsp+68h] [rbp+10h] BYREF

  if ( a2 )
  {
    if ( a2 != 1 )
    {
      v6 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v9);
      winrt::hresult_invalid_argument::hresult_invalid_argument(
        (winrt::hresult_invalid_argument *)&pExceptionObject,
        v6);
      throw (winrt::hresult_invalid_argument *)&pExceptionObject;
    }
    v2 = 2;
  }
  else
  {
    v2 = 1;
  }
  v3 = *(_QWORD *)(a1 + 8);
  pExceptionObject = 0;
  v8 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 72LL))(v3, v2);
  return winrt::check_hresult(&v10, v4, &pExceptionObject);
}

```

## disassembly

```asm
0x180025100  sub     rsp, 58h
0x180025104  test    edx, edx
0x180025106  jz      short loc_180025114
0x180025108  cmp     edx, 1
0x18002510b  jnz     short loc_180025150
0x18002510d  mov     edx, 2
0x180025112  jmp     short loc_180025119
0x180025114  mov     edx, 1
0x180025119  mov     rcx, [rcx+8]
0x18002511d  xorps   xmm0, xmm0
0x180025120  mov     [rsp+58h+pExceptionObject], 0
0x180025128  movdqu  [rsp+58h+var_30], xmm0
0x18002512e  mov     rax, [rcx]
0x180025131  mov     rax, [rax+48h]
0x180025135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002513a  lea     r8, [rsp+58h+pExceptionObject]
0x18002513f  mov     edx, eax
0x180025141  lea     rcx, [rsp+58h+arg_8]
0x180025146  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18002514b  add     rsp, 58h
0x18002514f  retn
0x180025150  lea     rcx, [rsp+58h+var_20]
0x180025155  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18002515a  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18002515d  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180025162  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::impl::slim_source_location const &)
0x180025167  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x18002516e  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180025173  call    _CxxThrowException_0
```
