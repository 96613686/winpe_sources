# TerminateShellApplication(IProcessLifetimeManagerControl *,ushort const *,LauncherTerminationTelemetry::TerminateShellApplications &)

- ea: `0x140019dd0`
- end: `0x14001a067`
- name: `?TerminateShellApplication@@YAXPEAUIProcessLifetimeManagerControl@@PEBGAEAVTerminateShellApplications@LauncherTerminationTelemetry@@@Z`
- size: `663`
- prototype: `void(struct IProcessLifetimeManagerControl *, const unsigned __int16 *, struct LauncherTerminationTelemetry::TerminateShellApplications *)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x140093c44`

## callees

- `0x14000edcc`
- `0x140019db4`
- `0x140019dd0`
- `0x14001a070`
- `0x14001eba8`
- `0x1400811ac`
- `0x14008194c`
- `0x1400954e0`
- `0x140097920`
- `0x1401044a0`
- `0x140104bd2`
- `0x140104cc8`
- `0x140104ce0`
- `0x14010bb18`
- `0x1401db010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001a007`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001a007`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140019f9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001a029`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140019f9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001a029`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140019e97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140019e97`

## string_xrefs

- `0x140019f01`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\StubImmersiveApplication.h`
- `0x140019feb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall TerminateShellApplication(
        struct IProcessLifetimeManagerControl *a1,
        const unsigned __int16 *a2,
        struct LauncherTerminationTelemetry::TerminateShellApplications *a3)
{
  struct IProcessLifetimeManagerControl *v5; // rsi
  _QWORD *v6; // rax
  _QWORD *v7; // rdi
  const char *v8; // r9
  char *v9; // r14
  __int64 v10; // rcx
  const unsigned __int16 *v11; // rax
  size_t v12; // rsi
  size_t v13; // r12
  char *v14; // rax
  char *v15; // rbx
  void *v16; // rsi
  int v17; // ebx
  _QWORD *v18; // rcx
  int v19; // [rsp+20h] [rbp-30h]
  _QWORD *v20; // [rsp+30h] [rbp-20h] BYREF
  _QWORD *v21; // [rsp+38h] [rbp-18h] BYREF
  __int64 v22; // [rsp+40h] [rbp-10h] BYREF
  char v23; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  int v26; // [rsp+A8h] [rbp+58h] BYREF

  v5 = a1;
  v20 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  v20 = 0;
  v6 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  if ( v6 )
  {
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IImmersiveApplication>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IImmersiveApplication>(v6);
    *v7 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IImmersiveApplication>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *v7 = &StubImmersiveApplication::`vftable';
    v9 = (char *)(v7 + 2);
    v7[2] = 0;
    v21 = v7;
    v22 = 0;
    if ( !a2 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xF89,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v8);
    v10 = 0x7FFFFFFF;
    v11 = a2;
    do
    {
      if ( !*v11 )
        break;
      ++v11;
      --v10;
    }
    while ( v10 );
    v12 = 2 * (v11 - a2);
    v13 = v12 + 2;
    v14 = (char *)CoTaskMemAlloc(v12 + 2);
    v15 = v14;
    if ( v14 )
    {
      if ( v12 )
      {
        if ( v13 < v12 )
        {
          memset_0(v14, 0, v13);
          *(_DWORD *)_o__errno() = 34;
          invalid_parameter_noinfo();
        }
        else
        {
          memcpy_0(v14, a2, v12);
        }
      }
      *(_WORD *)&v15[v12] = 0;
    }
    if ( v9 == &v23 )
    {
      if ( v15 )
        CoTaskMemFree(v15);
    }
    else
    {
      v16 = *(void **)v9;
      if ( *(_QWORD *)v9 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v26);
        CoTaskMemFree(v16);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v26);
      }
      *(_QWORD *)v9 = v15;
    }
    if ( *(_QWORD *)v9 )
    {
      (*(void (__fastcall **)(_QWORD *))(*v7 + 8LL))(v7);
      v20 = v7;
      (*(void (__fastcall **)(_QWORD *))(*v7 + 16LL))(v7);
      v17 = 0;
    }
    else
    {
      v17 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11,
        (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\StubImmersiveApplication.h",
        (const char *)0x8007000ELL,
        v19);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
      Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_bef595b4795dba7a185535ee5e87b99f_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_bef595b4795dba7a185535ee5e87b99f_>>(&v22);
    }
    v5 = a1;
  }
  else
  {
    v17 = -2147024882;
  }
  if ( v17 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x6C,
      (unsigned int)"pcshell\\shell\\explorer\\explorerutils.cpp",
      (const char *)(unsigned int)v17,
      v19);
  }
  else
  {
    v26 = 0;
    if ( (*(int (__fastcall **)(struct IProcessLifetimeManagerControl *, _QWORD *, __int64, int *))(*(_QWORD *)v5 + 96LL))(
           v5,
           v20,
           8,
           &v26) >= 0 )
      LauncherTerminationTelemetry::TerminateShellApplications::TerminationPerformed(a3, a2);
  }
  v18 = v20;
  if ( v20 )
  {
    v20 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v18 + 16LL))(v18);
  }
}

```

## disassembly

```asm
0x140019dd0  mov     [rsp-38h+arg_8], rbx
0x140019dd5  mov     [rsp-38h+arg_0], rcx
0x140019dda  push    rbp
0x140019ddb  push    rsi
0x140019ddc  push    rdi
0x140019ddd  push    r12
0x140019ddf  push    r13
0x140019de1  push    r14
0x140019de3  push    r15
0x140019de5  mov     rbp, rsp
0x140019de8  sub     rsp, 50h
0x140019dec  mov     r13, r8
0x140019def  mov     r15, rdx
0x140019df2  mov     rsi, rcx
0x140019df5  xor     r12d, r12d
0x140019df8  mov     [rbp+var_20], r12
0x140019dfc  lea     rcx, [rbp+var_20]
0x140019e00  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x140019e05  mov     [rbp+var_20], r12
0x140019e09  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140019e10  lea     ecx, [r12+18h]; unsigned __int64
0x140019e15  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140019e1a  mov     rdi, rax
0x140019e1d  test    rax, rax
0x140019e20  jz      loc_140019EEE
0x140019e26  mov     rcx, rax
0x140019e29  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIImmersiveApplication@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IImmersiveApplication>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IImmersiveApplication>(void)
0x140019e2e  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIImmersiveApplication@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IImmersiveApplication>::`vftable'
0x140019e35  mov     [rdi], rcx
0x140019e38  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x140019e3f  test    rcx, rcx
0x140019e42  jnz     loc_140019FDA
0x140019e48  lea     rax, ??_7StubImmersiveApplication@@6B@; const StubImmersiveApplication::`vftable'
0x140019e4f  mov     [rdi], rax
0x140019e52  lea     r14, [rdi+10h]
0x140019e56  mov     [r14], r12
0x140019e59  mov     [rbp+var_18], rdi
0x140019e5d  mov     [rbp+var_10], r12
0x140019e61  mov     rcx, [rbp+38h]; this
0x140019e65  test    r15, r15
0x140019e68  jz      loc_140019FEB
0x140019e6e  mov     ecx, 7FFFFFFFh
0x140019e73  mov     rax, r15
0x140019e76  cmp     [rax], r12w
0x140019e7a  jz      short loc_140019E86
0x140019e7c  add     rax, 2
0x140019e80  sub     rcx, 1
0x140019e84  jnz     short loc_140019E76
0x140019e86  sub     rax, r15
0x140019e89  sar     rax, 1
0x140019e8c  lea     rsi, [rax+rax]
0x140019e90  lea     r12, [rsi+2]
0x140019e94  mov     rcx, r12; cb
0x140019e97  call    cs:__imp_CoTaskMemAlloc
0x140019e9d  mov     rbx, rax
0x140019ea0  test    rax, rax
0x140019ea3  jz      loc_140019F8F
0x140019ea9  test    rsi, rsi
0x140019eac  jz      short loc_140019EC5
0x140019eae  mov     rcx, rax; void *
0x140019eb1  cmp     r12, rsi
0x140019eb4  jb      loc_140019FFD
0x140019eba  mov     r8, rsi; Size
0x140019ebd  mov     rdx, r15; Src
0x140019ec0  call    memcpy_0
0x140019ec5  xor     r12d, r12d
0x140019ec8  mov     [rsi+rbx], r12w
0x140019ecd  lea     rax, [rbp+var_8]
0x140019ed1  cmp     r14, rax
0x140019ed4  jz      loc_140019F97
0x140019eda  mov     rsi, [r14]
0x140019edd  test    rsi, rsi
0x140019ee0  jnz     loc_14001A01D
0x140019ee6  mov     [r14], rbx
0x140019ee9  jmp     loc_140019FA5
0x140019eee  mov     ebx, 8007000Eh
0x140019ef3  jmp     short loc_140019F28
0x140019ef5  mov     rcx, [rbp+38h]; this
0x140019ef9  mov     ebx, 8007000Eh
0x140019efe  mov     r9d, ebx; char *
0x140019f01  lea     r8, aShellcommondes_0; "ShellCommonDesktopBase\\Internal\\Shell"...
0x140019f08  mov     edx, 11h; void *
0x140019f0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140019f12  lea     rcx, [rbp+var_18]
0x140019f16  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x140019f1b  lea     rcx, [rbp+var_10]
0x140019f1f  call    ??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_bef595b4795dba7a185535ee5e87b99f_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_bef595b4795dba7a185535ee5e87b99f_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_bef595b4795dba7a185535ee5e87b99f_>>(void)
0x140019f24  mov     rsi, [rbp+arg_0]
0x140019f28  mov     rcx, [rbp+38h]; this
0x140019f2c  test    ebx, ebx
0x140019f2e  js      loc_14001A03D
0x140019f34  mov     [rbp+arg_18], r12d
0x140019f38  mov     rax, [rsi]
0x140019f3b  lea     r9, [rbp+arg_18]
0x140019f3f  mov     r8d, 8
0x140019f45  mov     rdx, [rbp+var_20]
0x140019f49  mov     rcx, rsi
0x140019f4c  mov     rax, [rax+60h]
0x140019f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019f55  test    eax, eax
0x140019f57  jns     loc_14001A056
0x140019f5d  mov     rcx, [rbp+var_20]
0x140019f61  test    rcx, rcx
0x140019f64  jz      short loc_140019F77
0x140019f66  mov     [rbp+var_20], r12
0x140019f6a  mov     rax, [rcx]
0x140019f6d  mov     rax, [rax+10h]
0x140019f71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019f76  nop
0x140019f77  mov     rbx, [rsp+50h+arg_8]
0x140019f7f  add     rsp, 50h
0x140019f83  pop     r15
0x140019f85  pop     r14
0x140019f87  pop     r13
0x140019f89  pop     r12
0x140019f8b  pop     rdi
0x140019f8c  pop     rsi
0x140019f8d  pop     rbp
0x140019f8e  retn
0x140019f8f  xor     r12d, r12d
0x140019f92  jmp     loc_140019ECD
0x140019f97  test    rbx, rbx
0x140019f9a  jz      short loc_140019FA5
0x140019f9c  mov     rcx, rbx; pv
0x140019f9f  call    cs:__imp_CoTaskMemFree
0x140019fa5  cmp     [r14], r12
0x140019fa8  jz      loc_140019EF5
0x140019fae  mov     rax, [rdi]
0x140019fb1  mov     rcx, rdi
0x140019fb4  mov     rax, [rax+8]
0x140019fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019fbd  nop
0x140019fbe  mov     [rbp+var_20], rdi
0x140019fc2  mov     rax, [rdi]
0x140019fc5  mov     rcx, rdi
0x140019fc8  mov     rax, [rax+10h]
0x140019fcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019fd1  nop
0x140019fd2  mov     ebx, r12d
0x140019fd5  jmp     loc_140019F24
0x140019fda  mov     rax, [rcx]
0x140019fdd  mov     rax, [rax+8]
0x140019fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019fe6  jmp     loc_140019E48
0x140019feb  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140019ff2  mov     edx, 0F89h; void *
0x140019ff7  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140019ffd  mov     r8, r12; Size
0x14001a000  xor     edx, edx; Val
0x14001a002  call    memset_0
0x14001a007  call    cs:__imp__o__errno
0x14001a00d  mov     dword ptr [rax], 22h ; '"'
0x14001a013  call    _invalid_parameter_noinfo
0x14001a018  jmp     loc_140019EC5
0x14001a01d  lea     rcx, [rbp+arg_18]; this
0x14001a021  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14001a026  mov     rcx, rsi; pv
0x14001a029  call    cs:__imp_CoTaskMemFree
0x14001a02f  lea     rcx, [rbp+arg_18]; this
0x14001a033  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14001a038  jmp     loc_140019EE6
0x14001a03d  mov     r9d, ebx; char *
0x14001a040  lea     r8, aPcshellShellEx; "pcshell\\shell\\explorer\\explorerutils"...
0x14001a047  mov     edx, 6Ch ; 'l'; void *
0x14001a04c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14001a051  jmp     loc_140019F5D
0x14001a056  mov     rdx, r15; unsigned __int16 *
0x14001a059  mov     rcx, r13; this
0x14001a05c  call    ?TerminationPerformed@TerminateShellApplications@LauncherTerminationTelemetry@@QEAAXPEBG@Z; LauncherTerminationTelemetry::TerminateShellApplications::TerminationPerformed(ushort const *)
0x14001a061  jmp     loc_140019F5D
```
