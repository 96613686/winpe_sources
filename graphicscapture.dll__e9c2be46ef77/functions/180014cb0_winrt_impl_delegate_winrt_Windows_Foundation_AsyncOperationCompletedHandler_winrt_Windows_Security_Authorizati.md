# winrt::impl::delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,_lambda_b6f4f8afd366bd487add8d033a4c31bd_>::Invoke(void *,int)

- ea: `0x180014cb0`
- end: `0x180014d2b`
- name: `?Invoke@?$delegate@U?$AsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@V_lambda_b6f4f8afd366bd487add8d033a4c31bd_@@@impl@winrt@@UEAAHPEAXH@Z`
- size: `123`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800065f0`
- `0x180012804`
- `0x180014598`
- `0x180014cb0`
- `0x180028010`

## pseudocode

```c
__int64 __fastcall winrt::impl::delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,_lambda_b6f4f8afd366bd487add8d033a4c31bd_>::Invoke(
        __int64 a1,
        struct IUnknown *a2,
        int a3)
{
  __int64 v4; // rdi
  void (__fastcall *v5)(__int64, __int64, void **); // rbx
  void **v6; // rax
  __int64 v8; // [rsp+40h] [rbp+8h] BYREF
  struct IUnknown *v9; // [rsp+48h] [rbp+10h] BYREF
  int v10; // [rsp+50h] [rbp+18h] BYREF

  v10 = a3;
  v9 = a2;
  v8 = 0;
  v4 = *(_QWORD *)(a1 + 16);
  v5 = *(void (__fastcall **)(__int64, __int64, void **))(*(_QWORD *)v4 + 24LL);
  v6 = winrt::put_abi((winrt *)&v8, a2);
  v5(v4, a1 + 24, v6);
  winrt::Windows::Foundation::AsyncActionCompletedHandler::operator()(&v8, &v9, &v10);
  if ( v8 )
    winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(&v8);
  return 0;
}

```

## disassembly

```asm
0x180014cb0  mov     r11, rsp
0x180014cb3  mov     [r11+18h], r8d
0x180014cb7  mov     [r11+10h], rdx
0x180014cbb  push    rbx
0x180014cbc  push    rsi
0x180014cbd  push    rdi
0x180014cbe  sub     rsp, 20h
0x180014cc2  mov     rsi, rcx
0x180014cc5  mov     qword ptr [r11+8], 0
0x180014ccd  mov     rdi, [rcx+10h]
0x180014cd1  mov     rax, [rdi]
0x180014cd4  mov     rbx, [rax+18h]
0x180014cd8  lea     rcx, [r11+8]; this
0x180014cdc  call    ?put_abi@winrt@@YAPEAPEAXAEAUIUnknown@Foundation@Windows@1@@Z; winrt::put_abi(winrt::Windows::Foundation::IUnknown &)
0x180014ce1  lea     rdx, [rsi+18h]
0x180014ce5  mov     r8, rax
0x180014ce8  mov     rcx, rdi
0x180014ceb  mov     rax, rbx
0x180014cee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cf3  lea     r8, [rsp+38h+arg_10]
0x180014cf8  lea     rdx, [rsp+38h+arg_8]
0x180014cfd  lea     rcx, [rsp+38h+arg_0]
0x180014d02  call    ??RAsyncActionCompletedHandler@Foundation@Windows@winrt@@QEBA@AEBUIAsyncAction@123@AEBW4AsyncStatus@123@@Z; winrt::Windows::Foundation::AsyncActionCompletedHandler::operator()(winrt::Windows::Foundation::IAsyncAction const &,winrt::Windows::Foundation::AsyncStatus const &)
0x180014d07  nop
0x180014d08  cmp     [rsp+38h+arg_0], 0
0x180014d0e  jz      short loc_180014D1A
0x180014d10  lea     rcx, [rsp+38h+arg_0]
0x180014d15  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x180014d1a  xor     eax, eax
0x180014d1c  jmp     short loc_180014D22
0x180014d1e  mov     eax, dword ptr [rsp+38h+arg_0]
0x180014d22  add     rsp, 20h
0x180014d26  pop     rdi
0x180014d27  pop     rsi
0x180014d28  pop     rbx
0x180014d29  retn
```
