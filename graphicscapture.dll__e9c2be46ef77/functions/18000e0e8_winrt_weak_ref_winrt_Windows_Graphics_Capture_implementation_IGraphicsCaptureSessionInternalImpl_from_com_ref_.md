# winrt::weak_ref<winrt::Windows::Graphics::Capture::implementation::IGraphicsCaptureSessionInternalImpl>::from_com_ref<winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::IGraphicsCaptureSessionInternalImpl> const &>(winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::IGraphicsCaptureSessionInternalImpl> const &)

- ea: `0x18000e0e8`
- end: `0x18000e18a`
- name: `??$from_com_ref@AEBU?$com_ptr@UIGraphicsCaptureSessionInternalImpl@implementation@Capture@Graphics@Windows@winrt@@@winrt@@@?$weak_ref@UIGraphicsCaptureSessionInternalImpl@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXAEBU?$com_ptr@UIGraphicsCaptureSessionInternalImpl@implementation@Capture@Graphics@Windows@winrt@@@1@@Z`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000f51c`

## callees

- `0x1800065f0`
- `0x18000e0e8`
- `0x1800125ec`
- `0x180028010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_UNKNOWN **__fastcall winrt::weak_ref<winrt::Windows::Graphics::Capture::implementation::IGraphicsCaptureSessionInternalImpl>::from_com_ref<winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::IGraphicsCaptureSessionInternalImpl> const &>(
        __int64 *a1,
        void (__fastcall ****a2)(_QWORD, __int64 *, __int64 *))
{
  _UNKNOWN **result; // rax
  void (__fastcall ***v4)(_QWORD, __int64 *, __int64 *); // rcx
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, __int64 *); // rsi
  unsigned int v7; // eax
  int v8; // [rsp+20h] [rbp-28h] BYREF
  __int128 v9; // [rsp+28h] [rbp-20h]
  _UNKNOWN *retaddr; // [rsp+48h] [rbp+0h] BYREF
  __int64 v11; // [rsp+58h] [rbp+10h] BYREF
  __int64 v12; // [rsp+60h] [rbp+18h] BYREF

  result = &retaddr;
  v4 = *a2;
  if ( *a2 )
  {
    v8 = 0;
    v9 = 0;
    v11 = 0;
    (**v4)(v4, &winrt::impl::guid_v<winrt::impl::IWeakReferenceSource>, &v11);
    v5 = v11;
    v12 = v11;
    v6 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 24LL);
    if ( *a1 )
      winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(a1);
    v7 = v6(v5, a1);
    winrt::check_hresult(&v11, v7, &v8);
    return (_UNKNOWN **)winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(&v12);
  }
  return result;
}

```

## disassembly

```asm
0x18000e0e8  mov     rax, rsp
0x18000e0eb  mov     [rax+8], rbx
0x18000e0ef  mov     [rax+20h], rsi
0x18000e0f3  push    rdi
0x18000e0f4  sub     rsp, 40h
0x18000e0f8  mov     rbx, rcx
0x18000e0fb  mov     rcx, [rdx]
0x18000e0fe  test    rcx, rcx
0x18000e101  jz      short loc_18000E17A
0x18000e103  mov     dword ptr [rax-28h], 0
0x18000e10a  xorps   xmm0, xmm0
0x18000e10d  movdqu  xmmword ptr [rax-20h], xmm0
0x18000e112  mov     qword ptr [rax+10h], 0
0x18000e11a  mov     rax, [rcx]
0x18000e11d  lea     r8, [rsp+48h+arg_8]
0x18000e122  lea     rdx, ??$guid_v@UIWeakReferenceSource@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IWeakReferenceSource>
0x18000e129  mov     rax, [rax]
0x18000e12c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e131  mov     rdi, [rsp+48h+arg_8]
0x18000e136  mov     [rsp+48h+arg_10], rdi
0x18000e13b  mov     rax, [rdi]
0x18000e13e  mov     rsi, [rax+18h]
0x18000e142  cmp     qword ptr [rbx], 0
0x18000e146  jz      short loc_18000E150
0x18000e148  mov     rcx, rbx
0x18000e14b  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x18000e150  mov     rdx, rbx
0x18000e153  mov     rcx, rdi
0x18000e156  mov     rax, rsi
0x18000e159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e15e  lea     r8, [rsp+48h+var_28]
0x18000e163  mov     edx, eax
0x18000e165  lea     rcx, [rsp+48h+arg_8]
0x18000e16a  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000e16f  nop
0x18000e170  lea     rcx, [rsp+48h+arg_10]
0x18000e175  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x18000e17a  mov     rbx, [rsp+48h+arg_0]
0x18000e17f  mov     rsi, [rsp+48h+arg_18]
0x18000e184  add     rsp, 40h
0x18000e188  pop     rdi
0x18000e189  retn
```
