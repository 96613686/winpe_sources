# winrt::weak_ref<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>::from_com_ref<winrt::Windows::Graphics::Capture::GraphicsCaptureItem const &>(winrt::Windows::Graphics::Capture::GraphicsCaptureItem const &)

- ea: `0x180016d3c`
- end: `0x180016dde`
- name: `??$from_com_ref@AEBUGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@?$weak_ref@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXAEBUGraphicsCaptureItem@Capture@Graphics@Windows@1@@Z`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180017d40`

## callees

- `0x1800065f0`
- `0x1800125ec`
- `0x180016d3c`
- `0x180028010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_UNKNOWN **__fastcall winrt::weak_ref<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>::from_com_ref<winrt::Windows::Graphics::Capture::GraphicsCaptureItem const &>(
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
0x180016d3c  mov     rax, rsp
0x180016d3f  mov     [rax+8], rbx
0x180016d43  mov     [rax+20h], rsi
0x180016d47  push    rdi
0x180016d48  sub     rsp, 40h
0x180016d4c  mov     rbx, rcx
0x180016d4f  mov     rcx, [rdx]
0x180016d52  test    rcx, rcx
0x180016d55  jz      short loc_180016DCE
0x180016d57  mov     dword ptr [rax-28h], 0
0x180016d5e  xorps   xmm0, xmm0
0x180016d61  movdqu  xmmword ptr [rax-20h], xmm0
0x180016d66  mov     qword ptr [rax+10h], 0
0x180016d6e  mov     rax, [rcx]
0x180016d71  lea     r8, [rsp+48h+arg_8]
0x180016d76  lea     rdx, ??$guid_v@UIWeakReferenceSource@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IWeakReferenceSource>
0x180016d7d  mov     rax, [rax]
0x180016d80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d85  mov     rdi, [rsp+48h+arg_8]
0x180016d8a  mov     [rsp+48h+arg_10], rdi
0x180016d8f  mov     rax, [rdi]
0x180016d92  mov     rsi, [rax+18h]
0x180016d96  cmp     qword ptr [rbx], 0
0x180016d9a  jz      short loc_180016DA4
0x180016d9c  mov     rcx, rbx
0x180016d9f  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x180016da4  mov     rdx, rbx
0x180016da7  mov     rcx, rdi
0x180016daa  mov     rax, rsi
0x180016dad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016db2  lea     r8, [rsp+48h+var_28]
0x180016db7  mov     edx, eax
0x180016db9  lea     rcx, [rsp+48h+arg_8]
0x180016dbe  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180016dc3  nop
0x180016dc4  lea     rcx, [rsp+48h+arg_10]
0x180016dc9  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x180016dce  mov     rbx, [rsp+48h+arg_0]
0x180016dd3  mov     rsi, [rsp+48h+arg_18]
0x180016dd8  add     rsp, 40h
0x180016ddc  pop     rdi
0x180016ddd  retn
```
