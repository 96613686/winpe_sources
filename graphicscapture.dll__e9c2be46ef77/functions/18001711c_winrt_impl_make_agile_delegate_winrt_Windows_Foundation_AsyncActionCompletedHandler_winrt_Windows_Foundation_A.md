# winrt::impl::make_agile_delegate<winrt::Windows::Foundation::AsyncActionCompletedHandler>(winrt::Windows::Foundation::AsyncActionCompletedHandler const &)

- ea: `0x18001711c`
- end: `0x18001721c`
- name: `??$make_agile_delegate@UAsyncActionCompletedHandler@Foundation@Windows@winrt@@@impl@winrt@@YA?AUAsyncActionCompletedHandler@Foundation@Windows@1@AEBU2341@@Z`
- size: `256`
- prototype: `__int64 __fastcall(winrt::Windows::Foundation::IUnknown *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018270`

## callees

- `0x180001640`
- `0x180002459`
- `0x1800065f0`
- `0x180012588`
- `0x180016054`
- `0x18001711c`
- `0x180028010`

## pseudocode

```c
winrt::Windows::Foundation::IUnknown *__fastcall winrt::impl::make_agile_delegate<winrt::Windows::Foundation::AsyncActionCompletedHandler>(
        winrt::Windows::Foundation::IUnknown *this,
        _QWORD *a2)
{
  void (__fastcall ***v4)(_QWORD, __int64 *, __int64 *); // rcx
  __int64 v5; // rax
  __int64 v7; // [rsp+20h] [rbp-40h] BYREF
  __int64 v8; // [rsp+28h] [rbp-38h] BYREF
  __int64 v9; // [rsp+30h] [rbp-30h] BYREF
  __int128 v10; // [rsp+38h] [rbp-28h]
  __int128 v11; // [rsp+48h] [rbp-18h] BYREF

  v4 = (void (__fastcall ***)(_QWORD, __int64 *, __int64 *))*a2;
  if ( *a2 && (v8 = 0, (**v4)(v4, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v8), v8) )
  {
    winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(&v8);
    *(_QWORD *)this = *a2;
    winrt::Windows::Foundation::IUnknown::add_ref(this);
  }
  else
  {
    v11 = winrt::impl::guid_v<winrt::Windows::Foundation::AsyncActionCompletedHandler>;
    v7 = 0;
    ((void (__fastcall *)(_QWORD, __int128 *, _QWORD, __int64 *))WINRT_IMPL_RoGetAgileReference)(0, &v11, *a2, &v7);
    v5 = v7;
    if ( v7 )
    {
      v7 = 0;
      v9 = v5;
      v10 = v11;
      winrt::Windows::Foundation::AsyncActionCompletedHandler::AsyncActionCompletedHandler(this, &v9);
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
0x18001711c  mov     [rsp-8+arg_10], rbx
0x180017121  mov     [rsp-8+arg_18], rdi
0x180017126  push    rbp
0x180017127  mov     rbp, rsp
0x18001712a  sub     rsp, 60h
0x18001712e  mov     rax, cs:__security_cookie
0x180017135  xor     rax, rsp
0x180017138  mov     [rbp+var_8], rax
0x18001713c  mov     rdi, rdx
0x18001713f  mov     rbx, rcx
0x180017142  mov     rcx, [rdx]
0x180017145  test    rcx, rcx
0x180017148  jz      short loc_18001718E
0x18001714a  mov     [rbp+var_38], 0
0x180017152  mov     rax, [rcx]
0x180017155  lea     r8, [rbp+var_38]
0x180017159  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180017160  mov     rax, [rax]
0x180017163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017168  mov     rcx, [rbp+var_38]
0x18001716c  mov     [rbp+var_38], rcx
0x180017170  test    rcx, rcx
0x180017173  jz      short loc_18001718E
0x180017175  lea     rcx, [rbp+var_38]
0x180017179  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x18001717e  mov     rcx, [rdi]
0x180017181  mov     [rbx], rcx
0x180017184  mov     rcx, rbx; this
0x180017187  call    ?add_ref@IUnknown@Foundation@Windows@winrt@@AEBAXXZ; winrt::Windows::Foundation::IUnknown::add_ref(void)
0x18001718c  jmp     short loc_1800171FB
0x18001718e  movups  xmm0, cs:??$guid_v@UAsyncActionCompletedHandler@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::AsyncActionCompletedHandler>
0x180017195  movdqu  [rbp+var_18], xmm0
0x18001719a  mov     [rbp+var_40], 0
0x1800171a2  lea     r9, [rbp+var_40]
0x1800171a6  mov     r8, [rdi]
0x1800171a9  lea     rdx, [rbp+var_18]
0x1800171ad  xor     ecx, ecx
0x1800171af  call    WINRT_IMPL_RoGetAgileReference
0x1800171b4  mov     rax, [rbp+var_40]
0x1800171b8  mov     rcx, rbx; this
0x1800171bb  test    rax, rax
0x1800171be  jnz     short loc_1800171CD
0x1800171c0  mov     rax, [rdi]
0x1800171c3  mov     [rbx], rax
0x1800171c6  call    ?add_ref@IUnknown@Foundation@Windows@winrt@@AEBAXXZ; winrt::Windows::Foundation::IUnknown::add_ref(void)
0x1800171cb  jmp     short loc_1800171EB
0x1800171cd  mov     [rbp+var_40], 0
0x1800171d5  mov     [rbp+var_30], rax
0x1800171d9  movups  xmm0, [rbp+var_18]
0x1800171dd  movdqu  [rbp+var_28], xmm0
0x1800171e2  lea     rdx, [rbp+var_30]
0x1800171e6  call    ??$?0V_lambda_dc4921c5914f1dac0ac69065375e73ef_@@@AsyncActionCompletedHandler@Foundation@Windows@winrt@@QEAA@V_lambda_dc4921c5914f1dac0ac69065375e73ef_@@@Z; winrt::Windows::Foundation::AsyncActionCompletedHandler::AsyncActionCompletedHandler(_lambda_dc4921c5914f1dac0ac69065375e73ef_)
0x1800171eb  cmp     [rbp+var_40], 0
0x1800171f0  jz      short loc_1800171FB
0x1800171f2  lea     rcx, [rbp+var_40]
0x1800171f6  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x1800171fb  mov     rax, rbx
0x1800171fe  mov     rcx, [rbp+var_8]
0x180017202  xor     rcx, rsp; StackCookie
0x180017205  call    __security_check_cookie
0x18001720a  lea     r11, [rsp+60h+var_s0]
0x18001720f  mov     rbx, [r11+20h]
0x180017213  mov     rdi, [r11+28h]
0x180017217  mov     rsp, r11
0x18001721a  pop     rbp
0x18001721b  retn
```
