# TerminateShellApplication(IProcessLifetimeManagerControl *,ushort const *,LauncherTerminationTelemetry::TerminateShellApplications &)

- ea: `0x140069780`
- end: `0x140069a30`
- name: `?TerminateShellApplication@@YAXPEAUIProcessLifetimeManagerControl@@PEBGAEAVTerminateShellApplications@LauncherTerminationTelemetry@@@Z`
- size: `688`
- prototype: `void(struct IProcessLifetimeManagerControl *, const unsigned __int16 *, struct LauncherTerminationTelemetry::TerminateShellApplications *)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x14009933c`

## callees

- `0x140012594`
- `0x14001b2c8`
- `0x140029b80`
- `0x140069780`
- `0x140069a38`
- `0x140086b94`
- `0x140087664`
- `0x14009ac68`
- `0x14009cf08`
- `0x14010e520`
- `0x14010ec86`
- `0x14010ed78`
- `0x14010ed90`
- `0x140115e5c`
- `0x1401d9010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400699c4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400699c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140069956`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400699ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140069956`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400699ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140069847`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140069847`

## string_xrefs

- `0x1400698b7`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\StubImmersiveApplication.h`
- `0x1400699a8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
      Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_6858217e680efffc32c2175d71a62a97_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_6858217e680efffc32c2175d71a62a97_>>(&v22);
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
0x140069780  mov     [rsp-38h+arg_8], rbx
0x140069785  mov     [rsp-38h+arg_0], rcx
0x14006978a  push    rbp
0x14006978b  push    rsi
0x14006978c  push    rdi
0x14006978d  push    r12
0x14006978f  push    r13
0x140069791  push    r14
0x140069793  push    r15
0x140069795  mov     rbp, rsp
0x140069798  sub     rsp, 50h
0x14006979c  mov     r13, r8
0x14006979f  mov     r15, rdx
0x1400697a2  mov     rsi, rcx
0x1400697a5  xor     r12d, r12d
0x1400697a8  mov     [rbp+var_20], r12
0x1400697ac  lea     rcx, [rbp+var_20]
0x1400697b0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1400697b5  mov     [rbp+var_20], r12
0x1400697b9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400697c0  lea     ecx, [r12+18h]; unsigned __int64
0x1400697c5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400697ca  mov     rdi, rax
0x1400697cd  test    rax, rax
0x1400697d0  jz      loc_1400698A4
0x1400697d6  mov     rcx, rax
0x1400697d9  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIImmersiveApplication@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IImmersiveApplication>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IImmersiveApplication>(void)
0x1400697de  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIImmersiveApplication@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IImmersiveApplication>::`vftable'
0x1400697e5  mov     [rdi], rcx
0x1400697e8  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1400697ef  test    rcx, rcx
0x1400697f2  jnz     loc_140069997
0x1400697f8  lea     rax, ??_7StubImmersiveApplication@@6B@; const StubImmersiveApplication::`vftable'
0x1400697ff  mov     [rdi], rax
0x140069802  lea     r14, [rdi+10h]
0x140069806  mov     [r14], r12
0x140069809  mov     [rbp+var_18], rdi
0x14006980d  mov     [rbp+var_10], r12
0x140069811  mov     rcx, [rbp+38h]; this
0x140069815  test    r15, r15
0x140069818  jz      loc_1400699A8
0x14006981e  mov     ecx, 7FFFFFFFh
0x140069823  mov     rax, r15
0x140069826  cmp     [rax], r12w
0x14006982a  jz      short loc_140069836
0x14006982c  add     rax, 2
0x140069830  sub     rcx, 1
0x140069834  jnz     short loc_140069826
0x140069836  sub     rax, r15
0x140069839  sar     rax, 1
0x14006983c  lea     rsi, [rax+rax]
0x140069840  lea     r12, [rsi+2]
0x140069844  mov     rcx, r12; cb
0x140069847  call    cs:__imp_CoTaskMemAlloc
0x14006984e  nop     dword ptr [rax+rax+00h]
0x140069853  mov     rbx, rax
0x140069856  test    rax, rax
0x140069859  jz      loc_140069946
0x14006985f  test    rsi, rsi
0x140069862  jz      short loc_14006987B
0x140069864  mov     rcx, rax; void *
0x140069867  cmp     r12, rsi
0x14006986a  jb      loc_1400699BA
0x140069870  mov     r8, rsi; Size
0x140069873  mov     rdx, r15; Src
0x140069876  call    memcpy_0
0x14006987b  xor     r12d, r12d
0x14006987e  mov     [rsi+rbx], r12w
0x140069883  lea     rax, [rbp+var_8]
0x140069887  cmp     r14, rax
0x14006988a  jz      loc_14006994E
0x140069890  mov     rsi, [r14]
0x140069893  test    rsi, rsi
0x140069896  jnz     loc_1400699E0
0x14006989c  mov     [r14], rbx
0x14006989f  jmp     loc_140069962
0x1400698a4  mov     ebx, 8007000Eh
0x1400698a9  jmp     short loc_1400698DE
0x1400698ab  mov     rcx, [rbp+38h]; this
0x1400698af  mov     ebx, 8007000Eh
0x1400698b4  mov     r9d, ebx; char *
0x1400698b7  lea     r8, aShellcommondes_0; "ShellCommonDesktopBase\\Internal\\Shell"...
0x1400698be  mov     edx, 11h; void *
0x1400698c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400698c8  lea     rcx, [rbp+var_18]
0x1400698cc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1400698d1  lea     rcx, [rbp+var_10]
0x1400698d5  call    ??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_6858217e680efffc32c2175d71a62a97_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_6858217e680efffc32c2175d71a62a97_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_6858217e680efffc32c2175d71a62a97_>>(void)
0x1400698da  mov     rsi, [rbp+arg_0]
0x1400698de  mov     rcx, [rbp+38h]; this
0x1400698e2  test    ebx, ebx
0x1400698e4  js      loc_140069A06
0x1400698ea  mov     [rbp+arg_18], r12d
0x1400698ee  mov     rax, [rsi]
0x1400698f1  lea     r9, [rbp+arg_18]
0x1400698f5  mov     r8d, 8
0x1400698fb  mov     rdx, [rbp+var_20]
0x1400698ff  mov     rcx, rsi
0x140069902  mov     rax, [rax+60h]
0x140069906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006990b  test    eax, eax
0x14006990d  jns     loc_140069A1F
0x140069913  mov     rcx, [rbp+var_20]
0x140069917  test    rcx, rcx
0x14006991a  jz      short loc_14006992D
0x14006991c  mov     [rbp+var_20], r12
0x140069920  mov     rax, [rcx]
0x140069923  mov     rax, [rax+10h]
0x140069927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006992c  nop
0x14006992d  mov     rbx, [rsp+50h+arg_8]
0x140069935  add     rsp, 50h
0x140069939  pop     r15
0x14006993b  pop     r14
0x14006993d  pop     r13
0x14006993f  pop     r12
0x140069941  pop     rdi
0x140069942  pop     rsi
0x140069943  pop     rbp
0x140069944  retn
0x140069946  xor     r12d, r12d
0x140069949  jmp     loc_140069883
0x14006994e  test    rbx, rbx
0x140069951  jz      short loc_140069962
0x140069953  mov     rcx, rbx; pv
0x140069956  call    cs:__imp_CoTaskMemFree
0x14006995d  nop     dword ptr [rax+rax+00h]
0x140069962  cmp     [r14], r12
0x140069965  jz      loc_1400698AB
0x14006996b  mov     rax, [rdi]
0x14006996e  mov     rcx, rdi
0x140069971  mov     rax, [rax+8]
0x140069975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006997a  nop
0x14006997b  mov     [rbp+var_20], rdi
0x14006997f  mov     rax, [rdi]
0x140069982  mov     rcx, rdi
0x140069985  mov     rax, [rax+10h]
0x140069989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006998e  nop
0x14006998f  mov     ebx, r12d
0x140069992  jmp     loc_1400698DA
0x140069997  mov     rax, [rcx]
0x14006999a  mov     rax, [rax+8]
0x14006999e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400699a3  jmp     loc_1400697F8
0x1400699a8  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400699af  mov     edx, 0F89h; void *
0x1400699b4  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1400699ba  mov     r8, r12; Size
0x1400699bd  xor     edx, edx; Val
0x1400699bf  call    memset_0
0x1400699c4  call    cs:__imp__o__errno
0x1400699cb  nop     dword ptr [rax+rax+00h]
0x1400699d0  mov     dword ptr [rax], 22h ; '"'
0x1400699d6  call    _invalid_parameter_noinfo
0x1400699db  jmp     loc_14006987B
0x1400699e0  lea     rcx, [rbp+arg_18]; this
0x1400699e4  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1400699e9  mov     rcx, rsi; pv
0x1400699ec  call    cs:__imp_CoTaskMemFree
0x1400699f3  nop     dword ptr [rax+rax+00h]
0x1400699f8  lea     rcx, [rbp+arg_18]; this
0x1400699fc  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140069a01  jmp     loc_14006989C
0x140069a06  mov     r9d, ebx; char *
0x140069a09  lea     r8, aPcshellShellEx; "pcshell\\shell\\explorer\\explorerutils"...
0x140069a10  mov     edx, 6Ch ; 'l'; void *
0x140069a15  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140069a1a  jmp     loc_140069913
0x140069a1f  mov     rdx, r15; unsigned __int16 *
0x140069a22  mov     rcx, r13; this
0x140069a25  call    ?TerminationPerformed@TerminateShellApplications@LauncherTerminationTelemetry@@QEAAXPEBG@Z; LauncherTerminationTelemetry::TerminateShellApplications::TerminationPerformed(ushort const *)
0x140069a2a  jmp     loc_140069913
```
