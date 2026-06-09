# CortanaAppPermissions::GrantUWPAppPermissions(void)

- ea: `0x180060be0`
- end: `0x180060ddf`
- name: `?GrantUWPAppPermissions@CortanaAppPermissions@@YAJXZ`
- size: `511`
- prototype: `__int64 __fastcall(CortanaAppPermissions *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180060418`

## callees

- `0x180002b60`
- `0x1800076d4`
- `0x180009100`
- `0x180009760`
- `0x1800097f4`
- `0x18000a4f8`
- `0x1800522d0`
- `0x1800609e0`
- `0x180060be0`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180060c7c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180060c7c`

## string_xrefs

- `0x180060c5d`: `Windows.Internal.CapabilityAccess.Management.CapabilityConsentManager`
- `0x180060c1f`: `shellcommon\internal\shell\inc\cortana\CortanaAppPermissions.h`
- `0x180060c8f`: `shellcommon\internal\shell\inc\cortana\CortanaAppPermissions.h`
- `0x180060d83`: `shellcommon\internal\shell\inc\cortana\CortanaAppPermissions.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CortanaAppPermissions::GrantUWPAppPermissions(
        CortanaAppPermissions *this,
        struct Windows::System::IUser **a2)
{
  int CurrentUser; // eax
  unsigned int v3; // ebx
  int ActivationFactory; // eax
  unsigned __int64 i; // r14
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, _QWORD, __int64 *); // rbx
  __int64 v8; // rax
  int v9; // eax
  __int64 v10; // rsi
  __int64 (__fastcall *v11)(__int64, _QWORD, __int64, __int64); // rdi
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rdx
  int v16; // [rsp+20h] [rbp-49h]
  __int64 v17; // [rsp+30h] [rbp-39h] BYREF
  __int64 v18; // [rsp+38h] [rbp-31h] BYREF
  __int64 v19; // [rsp+40h] [rbp-29h] BYREF
  UserHelpers *v20; // [rsp+48h] [rbp-21h] BYREF
  __int64 v21; // [rsp+50h] [rbp-19h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-11h] BYREF
  __int64 v23; // [rsp+70h] [rbp+7h]
  _BYTE v24[32]; // [rsp+78h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v20 = 0;
  CurrentUser = UserHelpers::GetCurrentUser((UserHelpers *)&v20, a2);
  v3 = CurrentUser;
  if ( CurrentUser >= 0 )
  {
    UserHelpers::GetUserSidString(&v19, v20);
    v18 = 0;
    v23 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.CapabilityAccess.Management.CapabilityConsentManager",
      0x46u,
      0x45u);
    ActivationFactory = RoGetActivationFactory(v23, &GUID_ef1a89c8_29b1_4ab0_94a7_851b33527a2e, &v18);
    v3 = ActivationFactory;
    if ( ActivationFactory >= 0 )
    {
      for ( i = 0; i < 4; ++i )
      {
        v17 = 0;
        v6 = v18;
        v7 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v18 + 48LL);
        v17 = 0;
        v8 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &off_180087738[i]);
        v9 = v7(v6, *(_QWORD *)(v8 + 24), &v17);
        v3 = v9;
        if ( v9 < 0 )
        {
          v14 = 41;
          goto LABEL_13;
        }
        v10 = v17;
        v11 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64))(*(_QWORD *)v17 + 144LL);
        v12 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &off_180087758)
                        + 24);
        v21 = v19;
        v13 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v24, &v21);
        v9 = v11(v10, *(_QWORD *)(v13 + 24), v12, 1);
        v3 = v9;
        if ( v9 < 0 )
        {
          v14 = 46;
LABEL_13:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v14,
            (unsigned int)"shellcommon\\internal\\shell\\inc\\cortana\\CortanaAppPermissions.h",
            (const char *)(unsigned int)v9,
            v16);
          wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v17);
          goto LABEL_5;
        }
        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v17);
      }
      wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v18);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
      v3 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x23,
        (unsigned int)"shellcommon\\internal\\shell\\inc\\cortana\\CortanaAppPermissions.h",
        (const char *)(unsigned int)ActivationFactory,
        v16);
LABEL_5:
      wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v18);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\cortana\\CortanaAppPermissions.h",
      (const char *)(unsigned int)CurrentUser,
      v16);
  }
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v20);
  return v3;
}

```

## disassembly

```asm
0x180060be0  push    rbp
0x180060be2  push    rbx
0x180060be3  push    rsi
0x180060be4  push    rdi
0x180060be5  push    r14
0x180060be7  lea     rbp, [rsp-37h]
0x180060bec  sub     rsp, 0A0h
0x180060bf3  mov     rax, cs:__security_cookie
0x180060bfa  xor     rax, rsp
0x180060bfd  mov     [rbp+57h+var_28], rax
0x180060c01  mov     [rbp+57h+var_78], 0
0x180060c09  lea     rcx, [rbp+57h+var_78]; this
0x180060c0d  call    ?GetCurrentUser@UserHelpers@@YAJPEAPEAUIUser@System@Windows@@@Z; UserHelpers::GetCurrentUser(Windows::System::IUser * *)
0x180060c12  mov     ebx, eax
0x180060c14  test    eax, eax
0x180060c16  jns     short loc_180060C35
0x180060c18  mov     rcx, [rbp+5Fh]; this
0x180060c1c  mov     r9d, eax; char *
0x180060c1f  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\cort"...
0x180060c26  mov     edx, 1Dh; void *
0x180060c2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180060c30  jmp     loc_180060DBA
0x180060c35  mov     rdx, [rbp+57h+var_78]
0x180060c39  lea     rcx, [rbp+57h+var_80]
0x180060c3d  call    ?GetUserSidString@UserHelpers@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIUser@System@Windows@@@Z; UserHelpers::GetUserSidString(Windows::System::IUser *)
0x180060c42  nop
0x180060c43  mov     [rbp+57h+var_88], 0
0x180060c4b  mov     [rbp+57h+var_50], 0
0x180060c53  mov     r9d, 45h ; 'E'; unsigned int
0x180060c59  lea     r8d, [r9+1]; unsigned int
0x180060c5d  lea     rdx, ?RuntimeClass_Windows_Internal_CapabilityAccess_Management_CapabilityConsentManager@@3QBGB; "Windows.Internal.CapabilityAccess.Manag"...
0x180060c64  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180060c68  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180060c6d  lea     r8, [rbp+57h+var_88]
0x180060c71  lea     rdx, _GUID_ef1a89c8_29b1_4ab0_94a7_851b33527a2e
0x180060c78  mov     rcx, [rbp+57h+var_50]
0x180060c7c  call    cs:__imp_RoGetActivationFactory
0x180060c82  mov     ebx, eax
0x180060c84  test    eax, eax
0x180060c86  jns     short loc_180060CB9
0x180060c88  mov     rcx, [rbp+5Fh]; this
0x180060c8c  mov     r9d, eax; char *
0x180060c8f  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\cort"...
0x180060c96  mov     edx, 23h ; '#'; void *
0x180060c9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180060ca0  nop
0x180060ca1  lea     rcx, [rbp+57h+var_88]
0x180060ca5  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180060caa  nop
0x180060cab  lea     rcx, [rbp+57h+var_80]
0x180060caf  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180060cb4  jmp     loc_180060DBA
0x180060cb9  xor     r14d, r14d
0x180060cbc  cmp     r14, 4
0x180060cc0  jnb     loc_180060DA5
0x180060cc6  mov     [rbp+57h+var_90], 0
0x180060cce  mov     rdi, [rbp+57h+var_88]
0x180060cd2  mov     rax, [rdi]
0x180060cd5  mov     rbx, [rax+30h]
0x180060cd9  mov     [rbp+57h+var_90], 0
0x180060ce1  lea     rax, off_180087738; "microphone"
0x180060ce8  lea     rdx, [rax+r14*8]
0x180060cec  lea     rcx, [rbp+57h+hstringHeader]
0x180060cf0  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180060cf5  nop
0x180060cf6  lea     r8, [rbp+57h+var_90]
0x180060cfa  mov     rdx, [rax+18h]
0x180060cfe  mov     rcx, rdi
0x180060d01  mov     rax, rbx
0x180060d04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060d09  mov     ebx, eax
0x180060d0b  test    eax, eax
0x180060d0d  js      short loc_180060D7E
0x180060d0f  mov     rsi, [rbp+57h+var_90]
0x180060d13  mov     rax, [rsi]
0x180060d16  mov     rdi, [rax+90h]
0x180060d1d  lea     rdx, off_180087758; "Microsoft.549981C3F5F10_8wekyb3d8bbwe"
0x180060d24  lea     rcx, [rbp+57h+hstringHeader]
0x180060d28  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180060d2d  nop
0x180060d2e  mov     rbx, [rax+18h]
0x180060d32  mov     rdx, [rbp+57h+var_80]
0x180060d36  mov     [rbp+57h+var_70], rdx
0x180060d3a  lea     rdx, [rbp+57h+var_70]
0x180060d3e  lea     rcx, [rbp+57h+var_48]
0x180060d42  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180060d47  nop
0x180060d48  mov     r9d, 1
0x180060d4e  mov     r8, rbx
0x180060d51  mov     rdx, [rax+18h]
0x180060d55  mov     rcx, rsi
0x180060d58  mov     rax, rdi
0x180060d5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060d60  mov     ebx, eax
0x180060d62  test    eax, eax
0x180060d64  js      short loc_180060D77
0x180060d66  lea     rcx, [rbp+57h+var_90]
0x180060d6a  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180060d6f  inc     r14
0x180060d72  jmp     loc_180060CBC
0x180060d77  mov     edx, 2Eh ; '.'
0x180060d7c  jmp     short loc_180060D83
0x180060d7e  mov     edx, 29h ; ')'; void *
0x180060d83  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\cort"...
0x180060d8a  mov     r9d, eax; char *
0x180060d8d  mov     rcx, [rbp+5Fh]; this
0x180060d91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180060d96  nop
0x180060d97  lea     rcx, [rbp+57h+var_90]
0x180060d9b  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180060da0  jmp     loc_180060CA1
0x180060da5  lea     rcx, [rbp+57h+var_88]
0x180060da9  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180060dae  nop
0x180060daf  lea     rcx, [rbp+57h+var_80]
0x180060db3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180060db8  xor     ebx, ebx
0x180060dba  lea     rcx, [rbp+57h+var_78]
0x180060dbe  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180060dc3  mov     eax, ebx
0x180060dc5  mov     rcx, [rbp+57h+var_28]
0x180060dc9  xor     rcx, rsp; StackCookie
0x180060dcc  call    __security_check_cookie
0x180060dd1  add     rsp, 0A0h
0x180060dd8  pop     r14
0x180060dda  pop     rdi
0x180060ddb  pop     rsi
0x180060ddc  pop     rbx
0x180060ddd  pop     rbp
0x180060dde  retn
```
