# winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>::AsyncOperationCompletedHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>(_lambda_8deb6f17603d0b78ec09e3578dd09f5a_)

- ea: `0x180013408`
- end: `0x18001349e`
- name: `??$?0V_lambda_8deb6f17603d0b78ec09e3578dd09f5a_@@@?$AsyncOperationCompletedHandler@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@QEAA@V_lambda_8deb6f17603d0b78ec09e3578dd09f5a_@@@Z`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013de4`

## callees

- `0x180001640`
- `0x180002158`
- `0x1800065f0`
- `0x180013408`

## pseudocode

```c
_QWORD *__fastcall winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>::AsyncOperationCompletedHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>(
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
  *(_QWORD *)v6 = &winrt::impl::delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,_lambda_8deb6f17603d0b78ec09e3578dd09f5a_>::`vftable';
  *a1 = v6;
  if ( *(_QWORD *)a2 )
    winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref((__int64 *)a2);
  return a1;
}

```

## disassembly

```asm
0x180013408  mov     [rsp+arg_10], rbx
0x18001340d  push    rdi
0x18001340e  sub     rsp, 40h
0x180013412  mov     rax, cs:__security_cookie
0x180013419  xor     rax, rsp
0x18001341c  mov     [rsp+48h+var_18], rax
0x180013421  mov     rbx, rdx
0x180013424  mov     rdi, rcx
0x180013427  mov     [rsp+48h+var_28], rcx
0x18001342c  mov     [rsp+48h+var_20], rdx
0x180013431  mov     ecx, 28h ; '('; Size
0x180013436  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001343b  mov     rdx, rax
0x18001343e  mov     [rsp+48h+var_20], rax
0x180013443  mov     dword ptr [rax+8], 1
0x18001344a  mov     rax, [rbx]
0x18001344d  mov     qword ptr [rbx], 0
0x180013454  mov     [rdx+10h], rax
0x180013458  movups  xmm0, xmmword ptr [rbx+8]
0x18001345c  movdqu  xmmword ptr [rdx+18h], xmm0
0x180013461  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180013468  lea     rax, ??_7?$delegate@U?$AsyncOperationCompletedHandler@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@V_lambda_8deb6f17603d0b78ec09e3578dd09f5a_@@@impl@winrt@@6B@; const winrt::impl::delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,_lambda_8deb6f17603d0b78ec09e3578dd09f5a_>::`vftable'
0x18001346f  mov     [rdx], rax
0x180013472  mov     [rdi], rdx
0x180013475  cmp     qword ptr [rbx], 0
0x180013479  jz      short loc_180013483
0x18001347b  mov     rcx, rbx
0x18001347e  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x180013483  mov     rax, rdi
0x180013486  mov     rcx, [rsp+48h+var_18]
0x18001348b  xor     rcx, rsp; StackCookie
0x18001348e  call    __security_check_cookie
0x180013493  mov     rbx, [rsp+48h+arg_10]
0x180013498  add     rsp, 40h
0x18001349c  pop     rdi
0x18001349d  retn
```
