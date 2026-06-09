# _lambda_74cfacc3a745e01412f5244e5c79641e_::operator()(Windows::Internal::CBasicResult<uint,0> &)

- ea: `0x18005ba40`
- end: `0x18005bc00`
- name: `??R_lambda_74cfacc3a745e01412f5244e5c79641e_@@QEBAJAEAV?$CBasicResult@I$0A@@Internal@Windows@@@Z`
- size: `448`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18005cb90`

## callees

- `0x180002b60`
- `0x1800076d4`
- `0x180009760`
- `0x18000a4f8`
- `0x18001e230`
- `0x18005ba40`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005bace`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005bace`

## string_xrefs

- `0x18005ba7f`: `shellcommon\shell\oobe\core\components\winrt\usermanagement.cpp`
- `0x18005bae1`: `shellcommon\shell\oobe\core\components\winrt\usermanagement.cpp`
- `0x18005bb26`: `shellcommon\shell\oobe\core\components\winrt\usermanagement.cpp`
- `0x18005bb75`: `shellcommon\shell\oobe\core\components\winrt\usermanagement.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall _lambda_74cfacc3a745e01412f5244e5c79641e_::operator()(__int64 a1, __int64 a2)
{
  unsigned int v3; // ebx
  int ActivationFactory; // eax
  int v5; // eax
  __int64 (__fastcall **v6)(_QWORD, _QWORD, _QWORD); // rax
  int v7; // eax
  __int64 v8; // rdx
  __int64 v10; // [rsp+20h] [rbp-50h] BYREF
  int v11; // [rsp+28h] [rbp-48h] BYREF
  __int64 v12; // [rsp+30h] [rbp-40h] BYREF
  __int64 (__fastcall ***v13)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  __int64 v15; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  if ( (int)VerifyCallerHasCapability((CallerIdentity *)L"userSigninSupport") >= 0 )
  {
    v13 = 0;
    v15 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.System.Internal.UserManager",
      0x24u,
      0x23u);
    ActivationFactory = RoGetActivationFactory(v15, &GUID_252e7f79_acfa_4ea2_9a7e_fa27a8a4d3d9, &v13);
    v3 = ActivationFactory;
    if ( ActivationFactory >= 0 )
    {
      v12 = 0;
      v5 = (**v13)(v13, &GUID_100eb64b_b24c_4c38_8964_720d926d05a4, &v12);
      v3 = v5;
      if ( v5 >= 0 )
      {
        v10 = 0;
        v6 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v13;
        v10 = 0;
        v7 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))v6[11])(v13, &v10);
        v3 = v7;
        if ( v7 >= 0 )
        {
          v11 = 0;
          v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v10 + 56LL))(v10, &v11);
          v3 = v7;
          if ( v7 >= 0 )
          {
            *(_DWORD *)(a2 + 16) = v11;
            wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v10);
            wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v12);
            v3 = 0;
            goto LABEL_14;
          }
          v8 = 117;
        }
        else
        {
          v8 = 115;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v8,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\usermanagement.cpp",
          (const char *)(unsigned int)v7,
          v10);
        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v10);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x70,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\usermanagement.cpp",
          (const char *)(unsigned int)v5,
          v10);
      }
      wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v12);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6E,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\usermanagement.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v10);
    }
LABEL_14:
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v13);
    return v3;
  }
  v3 = -2147024891;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x6B,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\usermanagement.cpp",
    (const char *)0x80070005LL,
    v10);
  return v3;
}

```

## disassembly

```asm
0x18005ba40  mov     [rsp-8+arg_0], rbx
0x18005ba45  mov     [rsp-8+arg_10], rdi
0x18005ba4a  push    rbp
0x18005ba4b  mov     rbp, rsp
0x18005ba4e  sub     rsp, 70h
0x18005ba52  mov     rax, cs:__security_cookie
0x18005ba59  xor     rax, rsp
0x18005ba5c  mov     [rbp+var_10], rax
0x18005ba60  mov     rdi, rdx
0x18005ba63  lea     rcx, aUsersigninsupp; "userSigninSupport"
0x18005ba6a  call    ?VerifyCallerHasCapability@@YAJPEBG@Z; VerifyCallerHasCapability(ushort const *)
0x18005ba6f  test    eax, eax
0x18005ba71  jns     short loc_18005BA95
0x18005ba73  mov     rcx, [rbp+8]; this
0x18005ba77  mov     ebx, 80070005h
0x18005ba7c  mov     r9d, ebx; char *
0x18005ba7f  lea     r8, aShellcommonShe; "shellcommon\\shell\\oobe\\core\\compone"...
0x18005ba86  mov     edx, 6Bh ; 'k'; void *
0x18005ba8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ba90  jmp     loc_18005BBE0
0x18005ba95  mov     [rbp+var_38], 0
0x18005ba9d  mov     [rbp+var_18], 0
0x18005baa5  mov     r9d, 23h ; '#'; unsigned int
0x18005baab  lea     r8d, [r9+1]; unsigned int
0x18005baaf  lea     rdx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x18005bab6  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18005baba  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005babf  lea     r8, [rbp+var_38]
0x18005bac3  lea     rdx, _GUID_252e7f79_acfa_4ea2_9a7e_fa27a8a4d3d9
0x18005baca  mov     rcx, [rbp+var_18]
0x18005bace  call    cs:__imp_RoGetActivationFactory
0x18005bad4  mov     ebx, eax
0x18005bad6  test    eax, eax
0x18005bad8  jns     short loc_18005BAF7
0x18005bada  mov     rcx, [rbp+8]; this
0x18005bade  mov     r9d, eax; char *
0x18005bae1  lea     r8, aShellcommonShe; "shellcommon\\shell\\oobe\\core\\compone"...
0x18005bae8  mov     edx, 6Eh ; 'n'; void *
0x18005baed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005baf2  jmp     loc_18005BBD7
0x18005baf7  mov     [rbp+var_40], 0
0x18005baff  mov     rcx, [rbp+var_38]
0x18005bb03  mov     rax, [rcx]
0x18005bb06  lea     r8, [rbp+var_40]
0x18005bb0a  lea     rdx, _GUID_100eb64b_b24c_4c38_8964_720d926d05a4
0x18005bb11  mov     rax, [rax]
0x18005bb14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bb19  mov     ebx, eax
0x18005bb1b  test    eax, eax
0x18005bb1d  jns     short loc_18005BB46
0x18005bb1f  mov     rcx, [rbp+8]; this
0x18005bb23  mov     r9d, eax; char *
0x18005bb26  lea     r8, aShellcommonShe; "shellcommon\\shell\\oobe\\core\\compone"...
0x18005bb2d  mov     edx, 70h ; 'p'; void *
0x18005bb32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005bb37  nop
0x18005bb38  lea     rcx, [rbp+var_40]
0x18005bb3c  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18005bb41  jmp     loc_18005BBD7
0x18005bb46  mov     [rbp+var_50], 0
0x18005bb4e  mov     rcx, [rbp+var_38]
0x18005bb52  mov     rax, [rcx]
0x18005bb55  mov     [rbp+var_50], 0
0x18005bb5d  lea     rdx, [rbp+var_50]
0x18005bb61  mov     rax, [rax+58h]
0x18005bb65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bb6a  mov     ebx, eax
0x18005bb6c  test    eax, eax
0x18005bb6e  jns     short loc_18005BB94
0x18005bb70  mov     edx, 73h ; 's'; void *
0x18005bb75  lea     r8, aShellcommonShe; "shellcommon\\shell\\oobe\\core\\compone"...
0x18005bb7c  mov     r9d, eax; char *
0x18005bb7f  mov     rcx, [rbp+8]; this
0x18005bb83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005bb88  nop
0x18005bb89  lea     rcx, [rbp+var_50]
0x18005bb8d  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18005bb92  jmp     short loc_18005BB38
0x18005bb94  mov     [rbp+var_48], 0
0x18005bb9b  mov     rcx, [rbp+var_50]
0x18005bb9f  mov     rax, [rcx]
0x18005bba2  lea     rdx, [rbp+var_48]
0x18005bba6  mov     rax, [rax+38h]
0x18005bbaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bbaf  mov     ebx, eax
0x18005bbb1  test    eax, eax
0x18005bbb3  jns     short loc_18005BBBC
0x18005bbb5  mov     edx, 75h ; 'u'
0x18005bbba  jmp     short loc_18005BB75
0x18005bbbc  mov     eax, [rbp+var_48]
0x18005bbbf  mov     [rdi+10h], eax
0x18005bbc2  lea     rcx, [rbp+var_50]
0x18005bbc6  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18005bbcb  nop
0x18005bbcc  lea     rcx, [rbp+var_40]
0x18005bbd0  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18005bbd5  xor     ebx, ebx
0x18005bbd7  lea     rcx, [rbp+var_38]
0x18005bbdb  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18005bbe0  mov     eax, ebx
0x18005bbe2  mov     rcx, [rbp+var_10]
0x18005bbe6  xor     rcx, rsp; StackCookie
0x18005bbe9  call    __security_check_cookie
0x18005bbee  lea     r11, [rsp+70h+var_s0]
0x18005bbf3  mov     rbx, [r11+10h]
0x18005bbf7  mov     rdi, [r11+20h]
0x18005bbfb  mov     rsp, r11
0x18005bbfe  pop     rbp
0x18005bbff  retn
```
