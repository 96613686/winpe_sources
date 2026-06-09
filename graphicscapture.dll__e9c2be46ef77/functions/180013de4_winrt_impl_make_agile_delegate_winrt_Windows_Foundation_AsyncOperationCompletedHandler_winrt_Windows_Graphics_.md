# winrt::impl::make_agile_delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>>(winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem> const &)

- ea: `0x180013de4`
- end: `0x180013ee2`
- name: `??$make_agile_delegate@U?$AsyncOperationCompletedHandler@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?AU?$AsyncOperationCompletedHandler@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@Foundation@Windows@1@AEBU2341@@Z`
- size: `254`
- prototype: `__int64 __fastcall(winrt::Windows::Foundation::IUnknown *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014898`

## callees

- `0x180001640`
- `0x1800065f0`
- `0x18000e380`
- `0x180012588`
- `0x180012778`
- `0x180013408`
- `0x180013de4`
- `0x180028010`

## pseudocode

```c
winrt::Windows::Foundation::IUnknown *__fastcall winrt::impl::make_agile_delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>>(
        winrt::Windows::Foundation::IUnknown *this,
        _QWORD *a2)
{
  void (__fastcall ***v4)(_QWORD, __int64 *, __int64 *); // rcx
  __int64 v5; // rax
  __int64 v7; // [rsp+20h] [rbp-40h] BYREF
  __int64 v8; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v9[24]; // [rsp+30h] [rbp-30h] BYREF
  __int128 v10; // [rsp+48h] [rbp-18h] BYREF

  v4 = (void (__fastcall ***)(_QWORD, __int64 *, __int64 *))*a2;
  if ( *a2 && (v8 = 0, (**v4)(v4, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v8), v8) )
  {
    winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(&v8);
    *(_QWORD *)this = *a2;
    winrt::Windows::Foundation::IUnknown::add_ref(this);
  }
  else
  {
    v10 = winrt::impl::guid_v<winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>>;
    v7 = 0;
    winrt::impl::get_agile_reference(&v8, &v10, *a2, &v7);
    if ( v7 )
    {
      v5 = _lambda_8deb6f17603d0b78ec09e3578dd09f5a_::_lambda_8deb6f17603d0b78ec09e3578dd09f5a_(v9, &v7, &v10);
      winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>::AsyncOperationCompletedHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>(
        this,
        v5);
    }
    else
    {
      *(_QWORD *)this = *a2;
      winrt::Windows::Foundation::IUnknown::add_ref(this);
    }
    if ( v7 )
      winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(&v7);
  }
  return this;
}

```

## disassembly

```asm
0x180013de4  mov     [rsp-8+arg_10], rbx
0x180013de9  mov     [rsp-8+arg_18], rdi
0x180013dee  push    rbp
0x180013def  mov     rbp, rsp
0x180013df2  sub     rsp, 60h
0x180013df6  mov     rax, cs:__security_cookie
0x180013dfd  xor     rax, rsp
0x180013e00  mov     [rbp+var_8], rax
0x180013e04  mov     rdi, rdx
0x180013e07  mov     rbx, rcx
0x180013e0a  mov     rcx, [rdx]
0x180013e0d  test    rcx, rcx
0x180013e10  jz      short loc_180013E56
0x180013e12  mov     [rbp+var_38], 0
0x180013e1a  mov     rax, [rcx]
0x180013e1d  lea     r8, [rbp+var_38]
0x180013e21  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180013e28  mov     rax, [rax]
0x180013e2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e30  mov     rcx, [rbp+var_38]
0x180013e34  mov     [rbp+var_38], rcx
0x180013e38  test    rcx, rcx
0x180013e3b  jz      short loc_180013E56
0x180013e3d  lea     rcx, [rbp+var_38]
0x180013e41  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x180013e46  mov     rcx, [rdi]
0x180013e49  mov     [rbx], rcx
0x180013e4c  mov     rcx, rbx; this
0x180013e4f  call    ?add_ref@IUnknown@Foundation@Windows@winrt@@AEBAXXZ; winrt::Windows::Foundation::IUnknown::add_ref(void)
0x180013e54  jmp     short loc_180013EC1
0x180013e56  movups  xmm0, cs:??$guid_v@U?$AsyncOperationCompletedHandler@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>>
0x180013e5d  movdqu  [rbp+var_18], xmm0
0x180013e62  mov     [rbp+var_40], 0
0x180013e6a  lea     r9, [rbp+var_40]
0x180013e6e  mov     r8, [rdi]
0x180013e71  lea     rdx, [rbp+var_18]
0x180013e75  lea     rcx, [rbp+var_38]
0x180013e79  call    ?get_agile_reference@impl@winrt@@YA?AUhresult@2@AEBUguid@2@PEAXPEAPEAX@Z; winrt::impl::get_agile_reference(winrt::guid const &,void *,void * *)
0x180013e7e  cmp     [rbp+var_40], 0
0x180013e83  jnz     short loc_180013E95
0x180013e85  mov     rax, [rdi]
0x180013e88  mov     [rbx], rax
0x180013e8b  mov     rcx, rbx; this
0x180013e8e  call    ?add_ref@IUnknown@Foundation@Windows@winrt@@AEBAXXZ; winrt::Windows::Foundation::IUnknown::add_ref(void)
0x180013e93  jmp     short loc_180013EB1
0x180013e95  lea     r8, [rbp+var_18]
0x180013e99  lea     rdx, [rbp+var_40]
0x180013e9d  lea     rcx, [rbp+var_30]
0x180013ea1  call    ??0_lambda_8deb6f17603d0b78ec09e3578dd09f5a_@@QEAA@$$QEAU?$com_ptr@UIAgileReference@impl@winrt@@@winrt@@AEBUguid@2@@Z; _lambda_8deb6f17603d0b78ec09e3578dd09f5a_::_lambda_8deb6f17603d0b78ec09e3578dd09f5a_(winrt::com_ptr<winrt::impl::IAgileReference> &&,winrt::guid const &)
0x180013ea6  mov     rdx, rax
0x180013ea9  mov     rcx, rbx
0x180013eac  call    ??$?0V_lambda_8deb6f17603d0b78ec09e3578dd09f5a_@@@?$AsyncOperationCompletedHandler@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@QEAA@V_lambda_8deb6f17603d0b78ec09e3578dd09f5a_@@@Z; winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>::AsyncOperationCompletedHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>(_lambda_8deb6f17603d0b78ec09e3578dd09f5a_)
0x180013eb1  cmp     [rbp+var_40], 0
0x180013eb6  jz      short loc_180013EC1
0x180013eb8  lea     rcx, [rbp+var_40]
0x180013ebc  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x180013ec1  mov     rax, rbx
0x180013ec4  mov     rcx, [rbp+var_8]
0x180013ec8  xor     rcx, rsp; StackCookie
0x180013ecb  call    __security_check_cookie
0x180013ed0  lea     r11, [rsp+60h+var_s0]
0x180013ed5  mov     rbx, [r11+20h]
0x180013ed9  mov     rdi, [r11+28h]
0x180013edd  mov     rsp, r11
0x180013ee0  pop     rbp
0x180013ee1  retn
```
