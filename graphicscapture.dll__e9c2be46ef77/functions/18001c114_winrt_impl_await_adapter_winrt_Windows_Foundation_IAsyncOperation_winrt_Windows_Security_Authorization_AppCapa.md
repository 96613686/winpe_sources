# winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1>::register_completed_callback(std::experimental::coroutine_handle<void>)

- ea: `0x18001c114`
- end: `0x18001c1b6`
- name: `?register_completed_callback@?$await_adapter@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@AEAA_NU?$coroutine_handle@X@experimental@std@@@Z`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001b414`

## callees

- `0x1800065f0`
- `0x1800125ec`
- `0x1800142b4`
- `0x18001430c`
- `0x18001b724`
- `0x18001c114`
- `0x180028010`

## pseudocode

```c
__int64 __fastcall winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1>::register_completed_callback(
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
  winrt::impl::make_delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,winrt::impl::disconnect_aware_handler<1,winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1>>>(
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
0x18001c114  mov     [rsp-18h+arg_10], rbx
0x18001c119  push    rbp
0x18001c11a  push    rsi
0x18001c11b  push    rdi
0x18001c11c  mov     rbp, rsp
0x18001c11f  sub     rsp, 60h
0x18001c123  mov     rbx, rdx
0x18001c126  mov     rsi, rcx
0x18001c129  mov     rdi, [rcx+8]
0x18001c12d  lea     rcx, [rbp+var_28]; this
0x18001c131  call    ??0resume_apartment_context@impl@winrt@@QEAA@XZ; winrt::impl::resume_apartment_context::resume_apartment_context(void)
0x18001c136  mov     [rbp+var_18], rsi
0x18001c13a  mov     [rbp+var_10], rbx
0x18001c13e  lea     rax, [rbp+var_28]
0x18001c142  mov     [rbp+arg_0], rax
0x18001c146  lea     rdx, [rbp+var_28]
0x18001c14a  lea     rcx, [rbp+arg_8]
0x18001c14e  call    ??$make_delegate@U?$AsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@U?$disconnect_aware_handler@$00U?$await_adapter@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@@impl@4@@impl@winrt@@YA?AU?$AsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@1@$$QEAU?$disconnect_aware_handler@$00U?$await_adapter@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@@01@@Z; winrt::impl::make_delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,winrt::impl::disconnect_aware_handler<1,winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1>>>(winrt::impl::disconnect_aware_handler<1,winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1>> &&)
0x18001c153  nop
0x18001c154  lea     rcx, [rbp+var_28]
0x18001c158  call    ??1?$disconnect_aware_handler@$00U?$await_adapter@U?$IAsyncOperation@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@@impl@winrt@@QEAA@XZ; winrt::impl::disconnect_aware_handler<1,winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::Server::CapturableItem>,1>>::~disconnect_aware_handler<1,winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::Server::CapturableItem>,1>>(void)
0x18001c15d  nop
0x18001c15e  mov     rcx, [rdi]
0x18001c161  mov     [rbp+var_40], 0
0x18001c168  xorps   xmm0, xmm0
0x18001c16b  movdqu  [rbp+var_38], xmm0
0x18001c170  mov     rax, [rcx]
0x18001c173  mov     rbx, [rbp+arg_8]
0x18001c177  mov     rdx, rbx
0x18001c17a  mov     rax, [rax+30h]
0x18001c17e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c183  lea     r8, [rbp+var_40]
0x18001c187  mov     edx, eax
0x18001c189  lea     rcx, [rbp+arg_0]
0x18001c18d  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001c192  nop
0x18001c193  test    rbx, rbx
0x18001c196  jz      short loc_18001C1A1
0x18001c198  lea     rcx, [rbp+arg_8]
0x18001c19c  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x18001c1a1  xor     eax, eax
0x18001c1a3  xchg    al, [rsi+18h]
0x18001c1a6  mov     rbx, [rsp+60h+arg_10]
0x18001c1ae  add     rsp, 60h
0x18001c1b2  pop     rdi
0x18001c1b3  pop     rsi
0x18001c1b4  pop     rbp
0x18001c1b5  retn
```
