# winrt::impl::make_agile_delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>(winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus> const &)

- ea: `0x18001b620`
- end: `0x18001b71e`
- name: `??$make_agile_delegate@U?$AsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?AU?$AsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@1@AEBU2341@@Z`
- size: `254`
- prototype: `__int64 __fastcall(winrt::Windows::Foundation::IUnknown *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001b98c`

## callees

- `0x180001640`
- `0x1800065f0`
- `0x18000e380`
- `0x180012588`
- `0x180012778`
- `0x18001b378`
- `0x18001b620`
- `0x180028010`

## pseudocode

```c
winrt::Windows::Foundation::IUnknown *__fastcall winrt::impl::make_agile_delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>(
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
    v10 = winrt::impl::guid_v<winrt::Windows::Foundation::AsyncOperationCompletedHandler<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>;
    v7 = 0;
    winrt::impl::get_agile_reference(&v8, &v10, *a2, &v7);
    if ( v7 )
    {
      v5 = _lambda_8deb6f17603d0b78ec09e3578dd09f5a_::_lambda_8deb6f17603d0b78ec09e3578dd09f5a_(v9, &v7, &v10);
      winrt::Windows::Foundation::AsyncOperationCompletedHandler<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>::AsyncOperationCompletedHandler<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>(
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
0x18001b620  mov     [rsp-8+arg_10], rbx
0x18001b625  mov     [rsp-8+arg_18], rdi
0x18001b62a  push    rbp
0x18001b62b  mov     rbp, rsp
0x18001b62e  sub     rsp, 60h
0x18001b632  mov     rax, cs:__security_cookie
0x18001b639  xor     rax, rsp
0x18001b63c  mov     [rbp+var_8], rax
0x18001b640  mov     rdi, rdx
0x18001b643  mov     rbx, rcx
0x18001b646  mov     rcx, [rdx]
0x18001b649  test    rcx, rcx
0x18001b64c  jz      short loc_18001B692
0x18001b64e  mov     [rbp+var_38], 0
0x18001b656  mov     rax, [rcx]
0x18001b659  lea     r8, [rbp+var_38]
0x18001b65d  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001b664  mov     rax, [rax]
0x18001b667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b66c  mov     rcx, [rbp+var_38]
0x18001b670  mov     [rbp+var_38], rcx
0x18001b674  test    rcx, rcx
0x18001b677  jz      short loc_18001B692
0x18001b679  lea     rcx, [rbp+var_38]
0x18001b67d  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x18001b682  mov     rcx, [rdi]
0x18001b685  mov     [rbx], rcx
0x18001b688  mov     rcx, rbx; this
0x18001b68b  call    ?add_ref@IUnknown@Foundation@Windows@winrt@@AEBAXXZ; winrt::Windows::Foundation::IUnknown::add_ref(void)
0x18001b690  jmp     short loc_18001B6FD
0x18001b692  movups  xmm0, cs:??$guid_v@U?$AsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>
0x18001b699  movdqu  [rbp+var_18], xmm0
0x18001b69e  mov     [rbp+var_40], 0
0x18001b6a6  lea     r9, [rbp+var_40]
0x18001b6aa  mov     r8, [rdi]
0x18001b6ad  lea     rdx, [rbp+var_18]
0x18001b6b1  lea     rcx, [rbp+var_38]
0x18001b6b5  call    ?get_agile_reference@impl@winrt@@YA?AUhresult@2@AEBUguid@2@PEAXPEAPEAX@Z; winrt::impl::get_agile_reference(winrt::guid const &,void *,void * *)
0x18001b6ba  cmp     [rbp+var_40], 0
0x18001b6bf  jnz     short loc_18001B6D1
0x18001b6c1  mov     rax, [rdi]
0x18001b6c4  mov     [rbx], rax
0x18001b6c7  mov     rcx, rbx; this
0x18001b6ca  call    ?add_ref@IUnknown@Foundation@Windows@winrt@@AEBAXXZ; winrt::Windows::Foundation::IUnknown::add_ref(void)
0x18001b6cf  jmp     short loc_18001B6ED
0x18001b6d1  lea     r8, [rbp+var_18]
0x18001b6d5  lea     rdx, [rbp+var_40]
0x18001b6d9  lea     rcx, [rbp+var_30]
0x18001b6dd  call    ??0_lambda_8deb6f17603d0b78ec09e3578dd09f5a_@@QEAA@$$QEAU?$com_ptr@UIAgileReference@impl@winrt@@@winrt@@AEBUguid@2@@Z; _lambda_8deb6f17603d0b78ec09e3578dd09f5a_::_lambda_8deb6f17603d0b78ec09e3578dd09f5a_(winrt::com_ptr<winrt::impl::IAgileReference> &&,winrt::guid const &)
0x18001b6e2  mov     rdx, rax
0x18001b6e5  mov     rcx, rbx
0x18001b6e8  call    ??$?0V_lambda_b6f4f8afd366bd487add8d033a4c31bd_@@@?$AsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@QEAA@V_lambda_b6f4f8afd366bd487add8d033a4c31bd_@@@Z; winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>::AsyncOperationCompletedHandler<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>(_lambda_b6f4f8afd366bd487add8d033a4c31bd_)
0x18001b6ed  cmp     [rbp+var_40], 0
0x18001b6f2  jz      short loc_18001B6FD
0x18001b6f4  lea     rcx, [rbp+var_40]
0x18001b6f8  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x18001b6fd  mov     rax, rbx
0x18001b700  mov     rcx, [rbp+var_8]
0x18001b704  xor     rcx, rsp; StackCookie
0x18001b707  call    __security_check_cookie
0x18001b70c  lea     r11, [rsp+60h+var_s0]
0x18001b711  mov     rbx, [r11+20h]
0x18001b715  mov     rdi, [r11+28h]
0x18001b719  mov     rsp, r11
0x18001b71c  pop     rbp
0x18001b71d  retn
```
