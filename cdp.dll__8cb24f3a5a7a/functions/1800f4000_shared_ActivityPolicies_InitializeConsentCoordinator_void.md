# shared::ActivityPolicies::InitializeConsentCoordinator(void)

- ea: `0x1800f4000`
- end: `0x1800f4433`
- name: `?InitializeConsentCoordinator@ActivityPolicies@shared@@AEBAJXZ`
- size: `1075`
- prototype: `__int64 __fastcall(shared::ActivityPolicies *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800f3c68`

## callees

- `0x180009b48`
- `0x180013da0`
- `0x18001ce80`
- `0x180057654`
- `0x1800ad770`
- `0x1800b19fc`
- `0x1800f4000`
- `0x180149448`
- `0x180190d8c`
- `0x1801f6fb0`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f420b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f4247`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f43c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f420b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f4247`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f43c6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800f4342`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800f4342`

## string_xrefs

- `0x1800f4265`: `Windows.Internal.Security.Authentication.Web.TokenBrokerInternal`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall shared::ActivityPolicies::InitializeConsentCoordinator(shared::ActivityPolicies *this)
{
  char *v2; // rsi
  int ActivationFactory; // ebx
  _QWORD *v5; // rdi
  __int64 (__fastcall ***v6)(_QWORD, GUID *, __int64 *); // rbx
  int v7; // eax
  __int64 v8; // rbx
  __int64 (__fastcall *v9)(__int64, _QWORD *, _QWORD); // r14
  int v10; // eax
  __int64 (__fastcall ***v11)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v12)(_QWORD, GUID *, __int64 *); // rbx
  int v13; // eax
  __int64 (__fastcall ***v14)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v15)(_QWORD, GUID *, __int64 *); // rbx
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, HSTRING *); // rbx
  int v19; // eax
  int v20; // eax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, __int64, HSTRING, __int64 *); // rbx
  int v23; // eax
  __int64 v24; // rbx
  __int64 v25; // rdx
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, __int64, char *); // rbx
  int v28; // [rsp+20h] [rbp-79h]
  HSTRING string; // [rsp+30h] [rbp-69h] BYREF
  __int64 (__fastcall ***v30)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-61h] BYREF
  __int64 v31; // [rsp+40h] [rbp-59h] BYREF
  __int64 v32; // [rsp+48h] [rbp-51h] BYREF
  __int64 v33; // [rsp+50h] [rbp-49h] BYREF
  __int64 v34; // [rsp+58h] [rbp-41h] BYREF
  __int64 v35; // [rsp+60h] [rbp-39h] BYREF
  __int64 v36; // [rsp+68h] [rbp-31h] BYREF
  __int64 (__fastcall ***v37)(_QWORD, GUID *, __int64 *); // [rsp+70h] [rbp-29h] BYREF
  std::_Ref_count_base *v38; // [rsp+78h] [rbp-21h]
  char v39[8]; // [rsp+80h] [rbp-19h] BYREF
  std::_Ref_count_base *v40; // [rsp+88h] [rbp-11h]
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp-9h] BYREF
  __int64 v42; // [rsp+A8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v2 = (char *)this + 184;
  if ( *((_QWORD *)this + 23) )
  {
    ActivationFactory = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D5,
      (unsigned int)"..\\sharedactivitypolicies.cpp",
      (const char *)0x80004003LL,
      v28);
    return (unsigned int)ActivationFactory;
  }
  shared::SharedInstanceManager::GetInstanceThrowIfNull<shared::IUserIdentityManager>(v39);
  v5 = (_QWORD *)((char *)this + 120);
  shared::GetAccountProvider(&v37, v39, v5);
  v31 = 0;
  v6 = v37;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
  v7 = (**v6)(v6, &GUID_661654e2_f44d_4f20_8c2d_4c3a04aa1570, &v31);
  ActivationFactory = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1DD,
      (unsigned int)"..\\sharedactivitypolicies.cpp",
      (const char *)(unsigned int)v7,
      v28);
LABEL_6:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
    if ( v38 )
      std::_Ref_count_base::_Decref(v38);
    if ( v40 )
      std::_Ref_count_base::_Decref(v40);
    return (unsigned int)ActivationFactory;
  }
  v30 = 0;
  v8 = v31;
  v9 = *(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD))(*(_QWORD *)v31 + 24LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v30);
  if ( v5[3] > 0xFu )
    v5 = (_QWORD *)*v5;
  v10 = v9(v8, v5, &v30);
  ActivationFactory = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E0,
      (unsigned int)"..\\sharedactivitypolicies.cpp",
      (const char *)(unsigned int)v10,
      v28);
LABEL_14:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v30);
    goto LABEL_6;
  }
  v32 = 0;
  v11 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v30;
  v12 = (__int64 (__fastcall *)(_QWORD, _QWORD))(*v30)[6];
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
  v13 = v12(v11, &v32);
  ActivationFactory = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E3,
      (unsigned int)"..\\sharedactivitypolicies.cpp",
      (const char *)(unsigned int)v13,
      v28);
LABEL_17:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
    goto LABEL_14;
  }
  v33 = 0;
  v14 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v30;
  v15 = **v30;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
  v16 = v15(v14, &GUID_7b56d6f8_990b_4eb5_94a7_5621f3a8b824, &v33);
  ActivationFactory = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E6,
      (unsigned int)"..\\sharedactivitypolicies.cpp",
      (const char *)(unsigned int)v16,
      v28);
LABEL_20:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
    goto LABEL_17;
  }
  string = 0;
  v17 = v33;
  v18 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v33 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v19 = v18(v17, &string);
  ActivationFactory = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E9,
      (unsigned int)"..\\sharedactivitypolicies.cpp",
      (const char *)(unsigned int)v19,
      v28);
LABEL_23:
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_20;
  }
  v35 = 0;
  v42 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.Security.Authentication.Web.TokenBrokerInternal",
    0x41u,
    0x40u);
  v20 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>>(
          v42,
          &v35);
  ActivationFactory = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EE,
      (unsigned int)"..\\sharedactivitypolicies.cpp",
      (const char *)(unsigned int)v20,
      v28);
LABEL_26:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v35);
    goto LABEL_23;
  }
  v34 = 0;
  v21 = v35;
  v22 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING, __int64 *))(*(_QWORD *)v35 + 72LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
  v23 = v22(v21, v32, string, &v34);
  ActivationFactory = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F5,
      (unsigned int)"..\\sharedactivitypolicies.cpp",
      (const char *)(unsigned int)v23,
      v28);
LABEL_29:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
    goto LABEL_26;
  }
  v36 = 0;
  v42 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.Shell.ConsentUx.UnifiedConsentCoordinator",
    0x3Bu,
    0x3Au);
  v24 = v42;
  Microsoft::WRL::ComPtr<Windows::Internal::Shell::ConsentUx::IUnifiedConsentCoordinatorFactory>::InternalRelease(&v36);
  ActivationFactory = RoGetActivationFactory(v24, &GUID_3e75a43a_baa6_5251_a662_708cf5cbb587, &v36);
  if ( ActivationFactory < 0 )
  {
    v25 = 505;
LABEL_32:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"..\\sharedactivitypolicies.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v28);
    Microsoft::WRL::ComPtr<Windows::Internal::Shell::ConsentUx::IUnifiedConsentCoordinatorFactory>::InternalRelease(&v36);
    goto LABEL_29;
  }
  v26 = v36;
  v27 = *(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)v36 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Internal::Shell::ConsentUx::IUnifiedConsentCoordinatorFactory>::InternalRelease(v2);
  ActivationFactory = v27(v26, v34, v2);
  if ( ActivationFactory < 0 )
  {
    v25 = 507;
    goto LABEL_32;
  }
  Microsoft::WRL::ComPtr<Windows::Internal::Shell::ConsentUx::IUnifiedConsentCoordinatorFactory>::InternalRelease(&v36);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v35);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v30);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
  if ( v38 )
    std::_Ref_count_base::_Decref(v38);
  if ( v40 )
    std::_Ref_count_base::_Decref(v40);
  return 0;
}

```

## disassembly

```asm
0x1800f4000  push    rbp
0x1800f4002  push    rbx
0x1800f4003  push    rsi
0x1800f4004  push    rdi
0x1800f4005  push    r14
0x1800f4007  push    r15
0x1800f4009  lea     rbp, [rsp-2Fh]
0x1800f400e  sub     rsp, 0C8h
0x1800f4015  mov     rax, cs:__security_cookie
0x1800f401c  xor     rax, rsp
0x1800f401f  mov     [rbp+57h+var_40], rax
0x1800f4023  mov     rdi, rcx
0x1800f4026  lea     rsi, [rcx+0B8h]
0x1800f402d  xor     r15d, r15d
0x1800f4030  cmp     [rsi], r15
0x1800f4033  jz      short loc_1800F4059
0x1800f4035  mov     rcx, [rbp+5Fh]; this
0x1800f4039  mov     ebx, 80004003h
0x1800f403e  mov     r9d, ebx; char *
0x1800f4041  lea     r8, aSharedactivity; "..\\sharedactivitypolicies.cpp"
0x1800f4048  mov     edx, 1D5h; void *
0x1800f404d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f4052  mov     eax, ebx
0x1800f4054  jmp     loc_1800F4417
0x1800f4059  lea     rcx, [rbp+57h+var_70]
0x1800f405d  call    ??$GetInstanceThrowIfNull@VIUserIdentityManager@shared@@@SharedInstanceManager@shared@@SA?AV?$shared_ptr@VIUserIdentityManager@shared@@@std@@H@Z; shared::SharedInstanceManager::GetInstanceThrowIfNull<shared::IUserIdentityManager>(int)
0x1800f4062  nop
0x1800f4063  add     rdi, 78h ; 'x'
0x1800f4067  mov     r8, rdi
0x1800f406a  lea     rdx, [rbp+57h+var_70]
0x1800f406e  lea     rcx, [rbp+57h+var_80]
0x1800f4072  call    ?GetAccountProvider@shared@@YA?AV?$shared_ptr@VICDPAccountProvider@@@std@@AEBV?$shared_ptr@VIUserIdentityManager@shared@@@3@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; shared::GetAccountProvider(std::shared_ptr<shared::IUserIdentityManager> const &,std::string const &)
0x1800f4077  nop
0x1800f4078  mov     [rbp+57h+var_B0], r15
0x1800f407c  mov     rbx, [rbp+57h+var_80]
0x1800f4080  lea     rcx, [rbp+57h+var_B0]
0x1800f4084  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800f4089  mov     rax, [rbx]
0x1800f408c  lea     r8, [rbp+57h+var_B0]
0x1800f4090  lea     rdx, _GUID_661654e2_f44d_4f20_8c2d_4c3a04aa1570
0x1800f4097  mov     rcx, rbx
0x1800f409a  mov     rax, [rax]
0x1800f409d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f40a2  mov     ebx, eax
0x1800f40a4  test    eax, eax
0x1800f40a6  jns     short loc_1800F40F1
0x1800f40a8  mov     rcx, [rbp+5Fh]; this
0x1800f40ac  mov     r9d, eax; char *
0x1800f40af  lea     r8, aSharedactivity; "..\\sharedactivitypolicies.cpp"
0x1800f40b6  mov     edx, 1DDh; void *
0x1800f40bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f40c0  nop
0x1800f40c1  lea     rcx, [rbp+57h+var_B0]
0x1800f40c5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800f40ca  nop
0x1800f40cb  mov     rcx, [rbp+57h+var_78]; this
0x1800f40cf  test    rcx, rcx
0x1800f40d2  jz      short loc_1800F40DA
0x1800f40d4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800f40d9  nop
0x1800f40da  mov     rcx, [rbp+57h+var_68]; this
0x1800f40de  test    rcx, rcx
0x1800f40e1  jz      loc_1800F4052
0x1800f40e7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800f40ec  jmp     loc_1800F4052
0x1800f40f1  mov     [rbp+57h+var_B8], r15
0x1800f40f5  mov     rbx, [rbp+57h+var_B0]
0x1800f40f9  mov     rax, [rbx]
0x1800f40fc  mov     r14, [rax+18h]
0x1800f4100  lea     rcx, [rbp+57h+var_B8]
0x1800f4104  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800f4109  cmp     qword ptr [rdi+18h], 0Fh
0x1800f410e  jbe     short loc_1800F4113
0x1800f4110  mov     rdi, [rdi]
0x1800f4113  lea     r8, [rbp+57h+var_B8]
0x1800f4117  mov     rdx, rdi
0x1800f411a  mov     rcx, rbx
0x1800f411d  mov     rax, r14
0x1800f4120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4125  mov     ebx, eax
0x1800f4127  test    eax, eax
0x1800f4129  jns     short loc_1800F4152
0x1800f412b  mov     rcx, [rbp+5Fh]; this
0x1800f412f  mov     r9d, eax; char *
0x1800f4132  lea     r8, aSharedactivity; "..\\sharedactivitypolicies.cpp"
0x1800f4139  mov     edx, 1E0h; void *
0x1800f413e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f4143  nop
0x1800f4144  lea     rcx, [rbp+57h+var_B8]
0x1800f4148  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800f414d  jmp     loc_1800F40C1
0x1800f4152  mov     [rbp+57h+var_A8], r15
0x1800f4156  mov     rdi, [rbp+57h+var_B8]
0x1800f415a  mov     rax, [rdi]
0x1800f415d  mov     rbx, [rax+30h]
0x1800f4161  lea     rcx, [rbp+57h+var_A8]
0x1800f4165  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800f416a  lea     rdx, [rbp+57h+var_A8]
0x1800f416e  mov     rcx, rdi
0x1800f4171  mov     rax, rbx
0x1800f4174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4179  mov     ebx, eax
0x1800f417b  test    eax, eax
0x1800f417d  jns     short loc_1800F41A3
0x1800f417f  mov     rcx, [rbp+5Fh]; this
0x1800f4183  mov     r9d, eax; char *
0x1800f4186  lea     r8, aSharedactivity; "..\\sharedactivitypolicies.cpp"
0x1800f418d  mov     edx, 1E3h; void *
0x1800f4192  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f4197  nop
0x1800f4198  lea     rcx, [rbp+57h+var_A8]
0x1800f419c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800f41a1  jmp     short loc_1800F4144
0x1800f41a3  mov     [rbp+57h+var_A0], r15
0x1800f41a7  mov     rdi, [rbp+57h+var_B8]
0x1800f41ab  mov     rax, [rdi]
0x1800f41ae  mov     rbx, [rax]
0x1800f41b1  lea     rcx, [rbp+57h+var_A0]
0x1800f41b5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800f41ba  lea     r8, [rbp+57h+var_A0]
0x1800f41be  lea     rdx, _GUID_7b56d6f8_990b_4eb5_94a7_5621f3a8b824
0x1800f41c5  mov     rcx, rdi
0x1800f41c8  mov     rax, rbx
0x1800f41cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f41d0  mov     ebx, eax
0x1800f41d2  test    eax, eax
0x1800f41d4  jns     short loc_1800F41FA
0x1800f41d6  mov     rcx, [rbp+5Fh]; this
0x1800f41da  mov     r9d, eax; char *
0x1800f41dd  lea     r8, aSharedactivity; "..\\sharedactivitypolicies.cpp"
0x1800f41e4  mov     edx, 1E6h; void *
0x1800f41e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f41ee  nop
0x1800f41ef  lea     rcx, [rbp+57h+var_A0]
0x1800f41f3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800f41f8  jmp     short loc_1800F4198
0x1800f41fa  mov     [rbp+57h+string], r15
0x1800f41fe  mov     rdi, [rbp+57h+var_A0]
0x1800f4202  mov     rax, [rdi]
0x1800f4205  mov     rbx, [rax+30h]
0x1800f4209  xor     ecx, ecx; string
0x1800f420b  call    cs:__imp_WindowsDeleteString
0x1800f4211  mov     [rbp+57h+string], r15
0x1800f4215  lea     rdx, [rbp+57h+string]
0x1800f4219  mov     rcx, rdi
0x1800f421c  mov     rax, rbx
0x1800f421f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4224  mov     ebx, eax
0x1800f4226  test    eax, eax
0x1800f4228  jns     short loc_1800F4253
0x1800f422a  mov     rcx, [rbp+5Fh]; this
0x1800f422e  mov     r9d, eax; char *
0x1800f4231  lea     r8, aSharedactivity; "..\\sharedactivitypolicies.cpp"
0x1800f4238  mov     edx, 1E9h; void *
0x1800f423d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f4242  nop
0x1800f4243  mov     rcx, [rbp+57h+string]; string
0x1800f4247  call    cs:__imp_WindowsDeleteString
0x1800f424d  mov     [rbp+57h+string], r15
0x1800f4251  jmp     short loc_1800F41EF
0x1800f4253  mov     [rbp+57h+var_90], r15
0x1800f4257  mov     [rbp+57h+var_48], r15
0x1800f425b  mov     r9d, 40h ; '@'; unsigned int
0x1800f4261  lea     r8d, [r9+1]; unsigned int
0x1800f4265  lea     rdx, ?RuntimeClass_Windows_Internal_Security_Authentication_Web_TokenBrokerInternal@@3QBGB; "Windows.Internal.Security.Authenticatio"...
0x1800f426c  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800f4270  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800f4275  lea     rdx, [rbp+57h+var_90]
0x1800f4279  mov     rcx, [rbp+57h+var_48]
0x1800f427d  call    ??$GetActivationFactory@V?$ComPtr@UITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>>)
0x1800f4282  mov     ebx, eax
0x1800f4284  test    eax, eax
0x1800f4286  jns     short loc_1800F42AC
0x1800f4288  mov     rcx, [rbp+5Fh]; this
0x1800f428c  mov     r9d, eax; char *
0x1800f428f  lea     r8, aSharedactivity; "..\\sharedactivitypolicies.cpp"
0x1800f4296  mov     edx, 1EEh; void *
0x1800f429b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f42a0  nop
0x1800f42a1  lea     rcx, [rbp+57h+var_90]
0x1800f42a5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800f42aa  jmp     short loc_1800F4243
0x1800f42ac  mov     [rbp+57h+var_98], r15
0x1800f42b0  mov     rdi, [rbp+57h+var_90]
0x1800f42b4  mov     rax, [rdi]
0x1800f42b7  mov     rbx, [rax+48h]
0x1800f42bb  lea     rcx, [rbp+57h+var_98]
0x1800f42bf  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800f42c4  lea     r9, [rbp+57h+var_98]
0x1800f42c8  mov     r8, [rbp+57h+string]
0x1800f42cc  mov     rdx, [rbp+57h+var_A8]
0x1800f42d0  mov     rcx, rdi
0x1800f42d3  mov     rax, rbx
0x1800f42d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f42db  mov     ebx, eax
0x1800f42dd  test    eax, eax
0x1800f42df  jns     short loc_1800F4305
0x1800f42e1  mov     rcx, [rbp+5Fh]; this
0x1800f42e5  mov     r9d, eax; char *
0x1800f42e8  lea     r8, aSharedactivity; "..\\sharedactivitypolicies.cpp"
0x1800f42ef  mov     edx, 1F5h; void *
0x1800f42f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f42f9  nop
0x1800f42fa  lea     rcx, [rbp+57h+var_98]
0x1800f42fe  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800f4303  jmp     short loc_1800F42A1
0x1800f4305  mov     [rbp+57h+var_88], r15
0x1800f4309  mov     [rbp+57h+var_48], r15
0x1800f430d  mov     r9d, 3Ah ; ':'; unsigned int
0x1800f4313  lea     r8d, [r9+1]; unsigned int
0x1800f4317  lea     rdx, ?RuntimeClass_Windows_Internal_Shell_ConsentUx_UnifiedConsentCoordinator@@3QBGB; "Windows.Internal.Shell.ConsentUx.Unifie"...
0x1800f431e  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800f4322  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800f4327  mov     rbx, [rbp+57h+var_48]
0x1800f432b  lea     rcx, [rbp+57h+var_88]
0x1800f432f  call    ?InternalRelease@?$ComPtr@UIUnifiedConsentCoordinatorFactory@ConsentUx@Shell@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::ConsentUx::IUnifiedConsentCoordinatorFactory>::InternalRelease(void)
0x1800f4334  lea     r8, [rbp+57h+var_88]
0x1800f4338  lea     rdx, _GUID_3e75a43a_baa6_5251_a662_708cf5cbb587
0x1800f433f  mov     rcx, rbx
0x1800f4342  call    cs:__imp_RoGetActivationFactory
0x1800f4348  mov     ebx, eax
0x1800f434a  test    eax, eax
0x1800f434c  jns     short loc_1800F4372
0x1800f434e  mov     edx, 1F9h; void *
0x1800f4353  lea     r8, aSharedactivity; "..\\sharedactivitypolicies.cpp"
0x1800f435a  mov     r9d, ebx; char *
0x1800f435d  mov     rcx, [rbp+5Fh]; this
0x1800f4361  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f4366  nop
0x1800f4367  lea     rcx, [rbp+57h+var_88]
0x1800f436b  call    ?InternalRelease@?$ComPtr@UIUnifiedConsentCoordinatorFactory@ConsentUx@Shell@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::ConsentUx::IUnifiedConsentCoordinatorFactory>::InternalRelease(void)
0x1800f4370  jmp     short loc_1800F42FA
0x1800f4372  mov     rdi, [rbp+57h+var_88]
0x1800f4376  mov     rax, [rdi]
0x1800f4379  mov     rbx, [rax+30h]
0x1800f437d  mov     rcx, rsi
0x1800f4380  call    ?InternalRelease@?$ComPtr@UIUnifiedConsentCoordinatorFactory@ConsentUx@Shell@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::ConsentUx::IUnifiedConsentCoordinatorFactory>::InternalRelease(void)
0x1800f4385  mov     r8, rsi
0x1800f4388  mov     rdx, [rbp+57h+var_98]
0x1800f438c  mov     rcx, rdi
0x1800f438f  mov     rax, rbx
0x1800f4392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4397  mov     ebx, eax
0x1800f4399  test    eax, eax
0x1800f439b  jns     short loc_1800F43A4
0x1800f439d  mov     edx, 1FBh
0x1800f43a2  jmp     short loc_1800F4353
0x1800f43a4  lea     rcx, [rbp+57h+var_88]
0x1800f43a8  call    ?InternalRelease@?$ComPtr@UIUnifiedConsentCoordinatorFactory@ConsentUx@Shell@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::ConsentUx::IUnifiedConsentCoordinatorFactory>::InternalRelease(void)
0x1800f43ad  nop
0x1800f43ae  lea     rcx, [rbp+57h+var_98]
0x1800f43b2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800f43b7  nop
0x1800f43b8  lea     rcx, [rbp+57h+var_90]
0x1800f43bc  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800f43c1  nop
0x1800f43c2  mov     rcx, [rbp+57h+string]; string
0x1800f43c6  call    cs:__imp_WindowsDeleteString
0x1800f43cc  mov     [rbp+57h+string], r15
0x1800f43d0  lea     rcx, [rbp+57h+var_A0]
0x1800f43d4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800f43d9  nop
0x1800f43da  lea     rcx, [rbp+57h+var_A8]
0x1800f43de  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800f43e3  nop
0x1800f43e4  lea     rcx, [rbp+57h+var_B8]
0x1800f43e8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800f43ed  nop
0x1800f43ee  lea     rcx, [rbp+57h+var_B0]
0x1800f43f2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800f43f7  nop
0x1800f43f8  mov     rcx, [rbp+57h+var_78]; this
0x1800f43fc  test    rcx, rcx
0x1800f43ff  jz      short loc_1800F4407
0x1800f4401  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800f4406  nop
0x1800f4407  mov     rcx, [rbp+57h+var_68]; this
0x1800f440b  test    rcx, rcx
0x1800f440e  jz      short loc_1800F4415
0x1800f4410  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800f4415  xor     eax, eax
0x1800f4417  mov     rcx, [rbp+57h+var_40]
0x1800f441b  xor     rcx, rsp; StackCookie
0x1800f441e  call    __security_check_cookie
0x1800f4423  add     rsp, 0C8h
0x1800f442a  pop     r15
0x1800f442c  pop     r14
0x1800f442e  pop     rdi
0x1800f442f  pop     rsi
0x1800f4430  pop     rbx
0x1800f4431  pop     rbp
0x1800f4432  retn
```
