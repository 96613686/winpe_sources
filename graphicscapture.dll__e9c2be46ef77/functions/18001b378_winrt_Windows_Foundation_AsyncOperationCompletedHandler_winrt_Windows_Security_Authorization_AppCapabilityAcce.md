# winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>::AsyncOperationCompletedHandler<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>(_lambda_b6f4f8afd366bd487add8d033a4c31bd_)

- ea: `0x18001b378`
- end: `0x18001b40e`
- name: `??$?0V_lambda_b6f4f8afd366bd487add8d033a4c31bd_@@@?$AsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@QEAA@V_lambda_b6f4f8afd366bd487add8d033a4c31bd_@@@Z`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001b620`

## callees

- `0x180001640`
- `0x180002158`
- `0x1800065f0`
- `0x18001b378`

## pseudocode

```c
_QWORD *__fastcall winrt::Windows::Foundation::AsyncOperationCompletedHandler<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>::AsyncOperationCompletedHandler<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>(
        _QWORD *a1,
        __int64 a2)
{
  __int64 v4; // rax
  char *v6; // [rsp+28h] [rbp-20h]

  v6 = (char *)operator new(0x28u);
  *((_DWORD *)v6 + 2) = 1;
  v4 = *(_QWORD *)a2;
  *(_QWORD *)a2 = 0;
  *((_QWORD *)v6 + 2) = v4;
  *(_OWORD *)(v6 + 24) = *(_OWORD *)(a2 + 8);
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)v6 = &winrt::impl::delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,_lambda_b6f4f8afd366bd487add8d033a4c31bd_>::`vftable';
  *a1 = v6;
  if ( *(_QWORD *)a2 )
    winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref((__int64 *)a2);
  return a1;
}

```

## disassembly

```asm
0x18001b378  mov     [rsp+arg_10], rbx
0x18001b37d  push    rdi
0x18001b37e  sub     rsp, 40h
0x18001b382  mov     rax, cs:__security_cookie
0x18001b389  xor     rax, rsp
0x18001b38c  mov     [rsp+48h+var_18], rax
0x18001b391  mov     rbx, rdx
0x18001b394  mov     rdi, rcx
0x18001b397  mov     [rsp+48h+var_28], rcx
0x18001b39c  mov     [rsp+48h+var_20], rdx
0x18001b3a1  mov     ecx, 28h ; '('; Size
0x18001b3a6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b3ab  mov     rdx, rax
0x18001b3ae  mov     [rsp+48h+var_20], rax
0x18001b3b3  mov     dword ptr [rax+8], 1
0x18001b3ba  mov     rax, [rbx]
0x18001b3bd  mov     qword ptr [rbx], 0
0x18001b3c4  mov     [rdx+10h], rax
0x18001b3c8  movups  xmm0, xmmword ptr [rbx+8]
0x18001b3cc  movdqu  xmmword ptr [rdx+18h], xmm0
0x18001b3d1  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001b3d8  lea     rax, ??_7?$delegate@U?$AsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@V_lambda_b6f4f8afd366bd487add8d033a4c31bd_@@@impl@winrt@@6B@; const winrt::impl::delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,_lambda_b6f4f8afd366bd487add8d033a4c31bd_>::`vftable'
0x18001b3df  mov     [rdx], rax
0x18001b3e2  mov     [rdi], rdx
0x18001b3e5  cmp     qword ptr [rbx], 0
0x18001b3e9  jz      short loc_18001B3F3
0x18001b3eb  mov     rcx, rbx
0x18001b3ee  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x18001b3f3  mov     rax, rdi
0x18001b3f6  mov     rcx, [rsp+48h+var_18]
0x18001b3fb  xor     rcx, rsp; StackCookie
0x18001b3fe  call    __security_check_cookie
0x18001b403  mov     rbx, [rsp+48h+arg_10]
0x18001b408  add     rsp, 40h
0x18001b40c  pop     rdi
0x18001b40d  retn
```
