# winrt::Windows::Graphics::Capture::implementation::DCompVisualCaptureSessionCore::DCompVisualCaptureSessionCore(winrt::com_ptr<IDCompositionDevice> const &,winrt::com_ptr<IDCompositionVisual> const &,void *)

- ea: `0x180024c34`
- end: `0x180024e6d`
- name: `??0DCompVisualCaptureSessionCore@implementation@Capture@Graphics@Windows@winrt@@QEAA@AEBU?$com_ptr@UIDCompositionDevice@@@5@AEBU?$com_ptr@UIDCompositionVisual@@@5@PEAX@Z`
- size: `569`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001cc30`

## callees

- `0x180006610`
- `0x1800125ec`
- `0x180024c34`
- `0x180028010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall winrt::Windows::Graphics::Capture::implementation::DCompVisualCaptureSessionCore::DCompVisualCaptureSessionCore(
        _QWORD *a1,
        __int64 (__fastcall ****a2)(_QWORD, __int64 *, __int64 *),
        _QWORD *a3,
        __int64 a4)
{
  __int64 *v7; // rdi
  __int64 *v8; // r14
  __int64 (__fastcall ***v9)(_QWORD, __int64 *, __int64 *); // rcx
  __int64 v10; // rbx
  unsigned int v11; // eax
  __int64 (__fastcall *v12)(__int64, __int64 *); // r15
  unsigned int v13; // eax
  __int64 (__fastcall *v14)(__int64, __int64 *); // r15
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  int v23; // [rsp+20h] [rbp-20h] BYREF
  __int128 v24; // [rsp+28h] [rbp-18h]
  char v25; // [rsp+88h] [rbp+48h] BYREF
  __int64 v26; // [rsp+90h] [rbp+50h] BYREF

  *a1 = &winrt::Windows::Graphics::Capture::implementation::DCompVisualCaptureSessionCore::`vftable';
  v7 = a1 + 1;
  a1[1] = 0;
  v8 = a1 + 2;
  a1[2] = 0;
  v9 = *a2;
  v26 = 0;
  if ( v9 )
  {
    v23 = 0;
    v24 = 0;
    v11 = (**v9)(v9, winrt::impl::guid_v<IDCompositionDeviceInternal2>, &v26);
    winrt::check_hresult(&v25, v11, &v23);
    v10 = v26;
  }
  else
  {
    v10 = 0;
  }
  v23 = 0;
  v24 = 0;
  v12 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v10 + 80LL);
  if ( *v7 )
    winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(v7);
  v13 = v12(v10, v7);
  winrt::check_hresult(&v25, v13, &v23);
  v23 = 0;
  v24 = 0;
  v14 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v10 + 72LL);
  if ( *v8 )
    winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(v8);
  v15 = v14(v10, v8);
  winrt::check_hresult(&v25, v15, &v23);
  v23 = 0;
  v24 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)*v7 + 48LL))(*v7, 0);
  winrt::check_hresult(&v25, v16, &v23);
  v23 = 0;
  v24 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)*v8 + 40LL))(*v8, 0);
  winrt::check_hresult(&v25, v17, &v23);
  v23 = 0;
  v24 = 0;
  v18 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)*v8 + 56LL))(*v8, 0);
  winrt::check_hresult(&v25, v18, &v23);
  v23 = 0;
  v24 = 0;
  v19 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)*v8 + 32LL))(*v8, *a3);
  winrt::check_hresult(&v25, v19, &v23);
  v23 = 0;
  v24 = 0;
  v20 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)*v7 + 24LL))(*v7, *v8);
  winrt::check_hresult(&v25, v20, &v23);
  v23 = 0;
  v24 = 0;
  v21 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)*v7 + 32LL))(*v7, a4);
  winrt::check_hresult(&v25, v21, &v23);
  winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(&v26);
  return a1;
}

```

## disassembly

```asm
0x180024c34  mov     [rsp-38h+arg_18], rbx
0x180024c39  mov     [rsp-38h+arg_0], rcx
0x180024c3e  push    rbp
0x180024c3f  push    rsi
0x180024c40  push    rdi
0x180024c41  push    r12
0x180024c43  push    r13
0x180024c45  push    r14
0x180024c47  push    r15
0x180024c49  mov     rbp, rsp
0x180024c4c  sub     rsp, 40h
0x180024c50  mov     r12, r9
0x180024c53  mov     r13, r8
0x180024c56  mov     rsi, rcx
0x180024c59  xor     r8d, r8d
0x180024c5c  lea     rax, ??_7DCompVisualCaptureSessionCore@implementation@Capture@Graphics@Windows@winrt@@6B@; const winrt::Windows::Graphics::Capture::implementation::DCompVisualCaptureSessionCore::`vftable'
0x180024c63  mov     [rcx], rax
0x180024c66  lea     rdi, [rcx+8]
0x180024c6a  mov     [rdi], r8
0x180024c6d  lea     r14, [rcx+10h]
0x180024c71  mov     [r14], r8
0x180024c74  mov     rcx, [rdx]
0x180024c77  mov     [rbp+arg_10], r8
0x180024c7b  test    rcx, rcx
0x180024c7e  jnz     short loc_180024C85
0x180024c80  mov     ebx, r8d
0x180024c83  jmp     short loc_180024CC1
0x180024c85  mov     [rbp+var_20], r8d
0x180024c89  xorps   xmm0, xmm0
0x180024c8c  movdqu  [rbp+var_18], xmm0
0x180024c91  mov     rax, [rcx]
0x180024c94  lea     r8, [rbp+arg_10]
0x180024c98  lea     rdx, ??$guid_v@UIDCompositionDeviceInternal2@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<IDCompositionDeviceInternal2>
0x180024c9f  mov     rax, [rax]
0x180024ca2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ca7  lea     r8, [rbp+var_20]
0x180024cab  mov     edx, eax
0x180024cad  lea     rcx, [rbp+arg_8]
0x180024cb1  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180024cb6  mov     rbx, [rbp+arg_10]
0x180024cba  mov     [rbp+arg_10], rbx
0x180024cbe  xor     r8d, r8d
0x180024cc1  mov     [rbp+var_20], r8d
0x180024cc5  xorps   xmm0, xmm0
0x180024cc8  movdqu  [rbp+var_18], xmm0
0x180024ccd  mov     rax, [rbx]
0x180024cd0  mov     r15, [rax+50h]
0x180024cd4  cmp     [rdi], r8
0x180024cd7  jz      short loc_180024CE1
0x180024cd9  mov     rcx, rdi
0x180024cdc  call    ?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ; winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(void)
0x180024ce1  mov     rdx, rdi
0x180024ce4  mov     rcx, rbx
0x180024ce7  mov     rax, r15
0x180024cea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cef  lea     r8, [rbp+var_20]
0x180024cf3  mov     edx, eax
0x180024cf5  lea     rcx, [rbp+arg_8]
0x180024cf9  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180024cfe  mov     [rbp+var_20], 0
0x180024d05  xorps   xmm0, xmm0
0x180024d08  movdqu  [rbp+var_18], xmm0
0x180024d0d  mov     rax, [rbx]
0x180024d10  mov     r15, [rax+48h]
0x180024d14  cmp     qword ptr [r14], 0
0x180024d18  jz      short loc_180024D22
0x180024d1a  mov     rcx, r14
0x180024d1d  call    ?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ; winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(void)
0x180024d22  mov     rdx, r14
0x180024d25  mov     rcx, rbx
0x180024d28  mov     rax, r15
0x180024d2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d30  lea     r8, [rbp+var_20]
0x180024d34  mov     edx, eax
0x180024d36  lea     rcx, [rbp+arg_8]
0x180024d3a  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180024d3f  xor     ebx, ebx
0x180024d41  mov     [rbp+var_20], ebx
0x180024d44  xorps   xmm0, xmm0
0x180024d47  movdqu  [rbp+var_18], xmm0
0x180024d4c  mov     rcx, [rdi]
0x180024d4f  mov     rax, [rcx]
0x180024d52  xor     edx, edx
0x180024d54  mov     rax, [rax+30h]
0x180024d58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d5d  lea     r8, [rbp+var_20]
0x180024d61  mov     edx, eax
0x180024d63  lea     rcx, [rbp+arg_8]
0x180024d67  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180024d6c  mov     [rbp+var_20], ebx
0x180024d6f  xorps   xmm0, xmm0
0x180024d72  movdqu  [rbp+var_18], xmm0
0x180024d77  mov     rcx, [r14]
0x180024d7a  mov     rax, [rcx]
0x180024d7d  xor     edx, edx
0x180024d7f  mov     rax, [rax+28h]
0x180024d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d88  lea     r8, [rbp+var_20]
0x180024d8c  mov     edx, eax
0x180024d8e  lea     rcx, [rbp+arg_8]
0x180024d92  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180024d97  mov     [rbp+var_20], ebx
0x180024d9a  xorps   xmm0, xmm0
0x180024d9d  movdqu  [rbp+var_18], xmm0
0x180024da2  mov     rcx, [r14]
0x180024da5  mov     rax, [rcx]
0x180024da8  xor     edx, edx
0x180024daa  mov     rax, [rax+38h]
0x180024dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024db3  lea     r8, [rbp+var_20]
0x180024db7  mov     edx, eax
0x180024db9  lea     rcx, [rbp+arg_8]
0x180024dbd  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180024dc2  mov     [rbp+var_20], ebx
0x180024dc5  xorps   xmm0, xmm0
0x180024dc8  movdqu  [rbp+var_18], xmm0
0x180024dcd  mov     rcx, [r14]
0x180024dd0  mov     rax, [rcx]
0x180024dd3  mov     rdx, [r13+0]
0x180024dd7  mov     rax, [rax+20h]
0x180024ddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024de0  lea     r8, [rbp+var_20]
0x180024de4  mov     edx, eax
0x180024de6  lea     rcx, [rbp+arg_8]
0x180024dea  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180024def  mov     [rbp+var_20], ebx
0x180024df2  xorps   xmm0, xmm0
0x180024df5  movdqu  [rbp+var_18], xmm0
0x180024dfa  mov     rcx, [rdi]
0x180024dfd  mov     rax, [rcx]
0x180024e00  mov     rdx, [r14]
0x180024e03  mov     rax, [rax+18h]
0x180024e07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e0c  lea     r8, [rbp+var_20]
0x180024e10  mov     edx, eax
0x180024e12  lea     rcx, [rbp+arg_8]
0x180024e16  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180024e1b  mov     [rbp+var_20], ebx
0x180024e1e  xorps   xmm0, xmm0
0x180024e21  movdqu  [rbp+var_18], xmm0
0x180024e26  mov     rcx, [rdi]
0x180024e29  mov     rax, [rcx]
0x180024e2c  mov     rdx, r12
0x180024e2f  mov     rax, [rax+20h]
0x180024e33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e38  lea     r8, [rbp+var_20]
0x180024e3c  mov     edx, eax
0x180024e3e  lea     rcx, [rbp+arg_8]
0x180024e42  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180024e47  nop
0x180024e48  lea     rcx, [rbp+arg_10]
0x180024e4c  call    ?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ; winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(void)
0x180024e51  nop
0x180024e52  mov     rax, rsi
0x180024e55  mov     rbx, [rsp+40h+arg_18]
0x180024e5d  add     rsp, 40h
0x180024e61  pop     r15
0x180024e63  pop     r14
0x180024e65  pop     r13
0x180024e67  pop     r12
0x180024e69  pop     rdi
0x180024e6a  pop     rsi
0x180024e6b  pop     rbp
0x180024e6c  retn
```
