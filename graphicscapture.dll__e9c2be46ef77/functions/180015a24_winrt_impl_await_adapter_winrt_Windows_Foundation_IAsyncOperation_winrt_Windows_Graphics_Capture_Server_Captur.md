# winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::Server::CapturableItem>,1>::register_completed_callback(std::experimental::coroutine_handle<void>)

- ea: `0x180015a24`
- end: `0x180015ac6`
- name: `?register_completed_callback@?$await_adapter@U?$IAsyncOperation@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@AEAA_NU?$coroutine_handle@X@experimental@std@@@Z`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800137a8`

## callees

- `0x1800065f0`
- `0x1800125ec`
- `0x180013ee8`
- `0x1800142b4`
- `0x18001430c`
- `0x180015a24`
- `0x180028010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::Server::CapturableItem>,1>::register_completed_callback(
        __int64 a1,
        __int64 a2)
{
  __int64 *v4; // rdi
  __int64 v5; // rcx
  __int64 v6; // rbx
  unsigned int v7; // eax
  __int64 result; // rax
  int v9; // [rsp+20h] [rbp-40h] BYREF
  __int128 v10; // [rsp+28h] [rbp-38h]
  _BYTE v11[16]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v12; // [rsp+48h] [rbp-18h]
  __int64 v13; // [rsp+50h] [rbp-10h]
  _BYTE *v14; // [rsp+80h] [rbp+20h] BYREF
  __int64 v15; // [rsp+88h] [rbp+28h] BYREF

  v4 = *(__int64 **)(a1 + 8);
  winrt::impl::resume_apartment_context::resume_apartment_context((winrt::impl::resume_apartment_context *)v11);
  v12 = a1;
  v13 = a2;
  v14 = v11;
  winrt::impl::make_delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::Graphics::Capture::Server::CapturableItem>,winrt::impl::disconnect_aware_handler<1,winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::Server::CapturableItem>,1>>>(
    &v15,
    v11);
  winrt::impl::disconnect_aware_handler<1,winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::Server::CapturableItem>,1>>::~disconnect_aware_handler<1,winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::Server::CapturableItem>,1>>(v11);
  v5 = *v4;
  v9 = 0;
  v10 = 0;
  v6 = v15;
  v7 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 48LL))(v5, v15);
  winrt::check_hresult(&v14, v7, &v9);
  if ( v6 )
    winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(&v15);
  result = *(unsigned __int8 *)(a1 + 24);
  *(_BYTE *)(a1 + 24) = 0;
  return result;
}

```

## disassembly

```asm
0x180015a24  mov     [rsp-18h+arg_10], rbx
0x180015a29  push    rbp
0x180015a2a  push    rsi
0x180015a2b  push    rdi
0x180015a2c  mov     rbp, rsp
0x180015a2f  sub     rsp, 60h
0x180015a33  mov     rbx, rdx
0x180015a36  mov     rsi, rcx
0x180015a39  mov     rdi, [rcx+8]
0x180015a3d  lea     rcx, [rbp+var_28]; this
0x180015a41  call    ??0resume_apartment_context@impl@winrt@@QEAA@XZ; winrt::impl::resume_apartment_context::resume_apartment_context(void)
0x180015a46  mov     [rbp+var_18], rsi
0x180015a4a  mov     [rbp+var_10], rbx
0x180015a4e  lea     rax, [rbp+var_28]
0x180015a52  mov     [rbp+arg_0], rax
0x180015a56  lea     rdx, [rbp+var_28]
0x180015a5a  lea     rcx, [rbp+arg_8]
0x180015a5e  call    ??$make_delegate@U?$AsyncOperationCompletedHandler@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@U?$disconnect_aware_handler@$00U?$await_adapter@U?$IAsyncOperation@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@@impl@4@@impl@winrt@@YA?AU?$AsyncOperationCompletedHandler@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@@Foundation@Windows@1@$$QEAU?$disconnect_aware_handler@$00U?$await_adapter@U?$IAsyncOperation@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@@01@@Z; winrt::impl::make_delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::Graphics::Capture::Server::CapturableItem>,winrt::impl::disconnect_aware_handler<1,winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::Server::CapturableItem>,1>>>(winrt::impl::disconnect_aware_handler<1,winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::Server::CapturableItem>,1>> &&)
0x180015a63  nop
0x180015a64  lea     rcx, [rbp+var_28]
0x180015a68  call    ??1?$disconnect_aware_handler@$00U?$await_adapter@U?$IAsyncOperation@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@@impl@winrt@@QEAA@XZ; winrt::impl::disconnect_aware_handler<1,winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::Server::CapturableItem>,1>>::~disconnect_aware_handler<1,winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::Server::CapturableItem>,1>>(void)
0x180015a6d  nop
0x180015a6e  mov     rcx, [rdi]
0x180015a71  mov     [rbp+var_40], 0
0x180015a78  xorps   xmm0, xmm0
0x180015a7b  movdqu  [rbp+var_38], xmm0
0x180015a80  mov     rax, [rcx]
0x180015a83  mov     rbx, [rbp+arg_8]
0x180015a87  mov     rdx, rbx
0x180015a8a  mov     rax, [rax+30h]
0x180015a8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a93  lea     r8, [rbp+var_40]
0x180015a97  mov     edx, eax
0x180015a99  lea     rcx, [rbp+arg_0]
0x180015a9d  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180015aa2  nop
0x180015aa3  test    rbx, rbx
0x180015aa6  jz      short loc_180015AB1
0x180015aa8  lea     rcx, [rbp+arg_8]
0x180015aac  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x180015ab1  xor     eax, eax
0x180015ab3  xchg    al, [rsi+18h]
0x180015ab6  mov     rbx, [rsp+60h+arg_10]
0x180015abe  add     rsp, 60h
0x180015ac2  pop     rdi
0x180015ac3  pop     rsi
0x180015ac4  pop     rbp
0x180015ac5  retn
```
