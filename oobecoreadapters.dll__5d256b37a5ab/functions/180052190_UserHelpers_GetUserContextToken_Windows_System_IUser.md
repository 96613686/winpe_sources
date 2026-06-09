# UserHelpers::GetUserContextToken(Windows::System::IUser *)

- ea: `0x180052190`
- end: `0x1800522c8`
- name: `?GetUserContextToken@UserHelpers@@YA_KPEAUIUser@System@Windows@@@Z`
- size: `312`
- prototype: `unsigned __int64 __fastcall(UserHelpers *__hidden this, struct Windows::System::IUser *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18005238c`

## callees

- `0x180002b60`
- `0x180003a80`
- `0x180009760`
- `0x18000a4f8`
- `0x180015544`
- `0x180052190`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180052248`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180052248`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800521c6`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800521c6`

## string_xrefs

- `0x1800521dc`: `ShellCommon\internal\Shell\inc\helpers\UserHelpers.h`
- `0x1800521f7`: `ShellCommon\internal\Shell\inc\helpers\UserHelpers.h`
- `0x18005225a`: `ShellCommon\internal\Shell\inc\helpers\UserHelpers.h`
- `0x180052294`: `ShellCommon\internal\Shell\inc\helpers\UserHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UserHelpers::GetUserContextToken(UserHelpers *this, struct Windows::System::IUser *a2)
{
  int v3; // eax
  int ActivationFactory; // eax
  int v5; // eax
  int v7[2]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v8; // [rsp+28h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-38h] BYREF
  __int64 v10; // [rsp+48h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v8 = 0;
  if ( this )
  {
    *(_QWORD *)v7 = 0;
    v10 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.System.Internal.UserManager",
      0x24u,
      0x23u);
    ActivationFactory = RoGetActivationFactory(v10, &GUID_100eb64b_b24c_4c38_8964_720d926d05a4, v7);
    if ( ActivationFactory < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4C,
        (unsigned int)"ShellCommon\\internal\\Shell\\inc\\helpers\\UserHelpers.h",
        (const char *)(unsigned int)ActivationFactory,
        v7[0]);
    v5 = (*(__int64 (__fastcall **)(_QWORD, UserHelpers *, __int64 *))(**(_QWORD **)v7 + 136LL))(
           *(_QWORD *)v7,
           this,
           &v8);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4D,
        (unsigned int)"ShellCommon\\internal\\Shell\\inc\\helpers\\UserHelpers.h",
        (const char *)(unsigned int)v5,
        v7[0]);
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(v7);
  }
  else
  {
    if ( !(unsigned __int8)IsUMgrGetConstrainedUserTokenPresent(0, a2) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x46,
        (unsigned int)"ShellCommon\\internal\\Shell\\inc\\helpers\\UserHelpers.h",
        (const char *)0x80004001LL,
        v7[0]);
    v3 = UMgrQueryUserContext(0, &v8);
    if ( v3 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x42,
        (unsigned int)"ShellCommon\\internal\\Shell\\inc\\helpers\\UserHelpers.h",
        (const char *)(unsigned int)v3,
        v7[0]);
  }
  return v8;
}

```

## disassembly

```asm
0x180052190  push    rbx
0x180052192  sub     rsp, 60h
0x180052196  mov     rax, cs:__security_cookie
0x18005219d  xor     rax, rsp
0x1800521a0  mov     [rsp+68h+var_18], rax
0x1800521a5  mov     rbx, rcx
0x1800521a8  mov     [rsp+68h+var_40], 0
0x1800521b1  test    rcx, rcx
0x1800521b4  jnz     short loc_180052209
0x1800521b6  call    IsUMgrGetConstrainedUserTokenPresent
0x1800521bb  test    al, al
0x1800521bd  jz      short loc_1800521EC
0x1800521bf  lea     rdx, [rsp+68h+var_40]
0x1800521c4  xor     ecx, ecx
0x1800521c6  call    cs:__imp_UMgrQueryUserContext
0x1800521cc  test    eax, eax
0x1800521ce  jns     loc_1800522B0
0x1800521d4  mov     rcx, [rsp+68h]; this
0x1800521d9  mov     r9d, eax; char *
0x1800521dc  lea     r8, aShellcommonInt_0; "ShellCommon\\internal\\Shell\\inc\\help"...
0x1800521e3  lea     edx, [rbx+42h]; void *
0x1800521e6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800521ec  mov     rcx, [rsp+68h]; this
0x1800521f1  mov     r9d, 80004001h; char *
0x1800521f7  lea     r8, aShellcommonInt_0; "ShellCommon\\internal\\Shell\\inc\\help"...
0x1800521fe  mov     edx, 46h ; 'F'; void *
0x180052203  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180052209  mov     qword ptr [rsp+68h+var_48], 0; int
0x180052212  mov     [rsp+68h+var_20], 0
0x18005221b  mov     r9d, 23h ; '#'; unsigned int
0x180052221  lea     r8d, [r9+1]; unsigned int
0x180052225  lea     rdx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x18005222c  lea     rcx, [rsp+68h+hstringHeader]; hstringHeader
0x180052231  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180052236  nop
0x180052237  lea     r8, [rsp+68h+var_48]
0x18005223c  lea     rdx, _GUID_100eb64b_b24c_4c38_8964_720d926d05a4
0x180052243  mov     rcx, [rsp+68h+var_20]
0x180052248  call    cs:__imp_RoGetActivationFactory
0x18005224e  mov     rcx, [rsp+68h]; this
0x180052253  test    eax, eax
0x180052255  jns     short loc_18005226C
0x180052257  mov     r9d, eax; char *
0x18005225a  lea     r8, aShellcommonInt_0; "ShellCommon\\internal\\Shell\\inc\\help"...
0x180052261  mov     edx, 4Ch ; 'L'; void *
0x180052266  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005226c  mov     rcx, qword ptr [rsp+68h+var_48]
0x180052271  mov     rax, [rcx]
0x180052274  lea     r8, [rsp+68h+var_40]
0x180052279  mov     rdx, rbx
0x18005227c  mov     rax, [rax+88h]
0x180052283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052288  mov     rcx, [rsp+68h]; this
0x18005228d  test    eax, eax
0x18005228f  jns     short loc_1800522A6
0x180052291  mov     r9d, eax; char *
0x180052294  lea     r8, aShellcommonInt_0; "ShellCommon\\internal\\Shell\\inc\\help"...
0x18005229b  mov     edx, 4Dh ; 'M'; void *
0x1800522a0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800522a6  lea     rcx, [rsp+68h+var_48]
0x1800522ab  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x1800522b0  mov     rax, [rsp+68h+var_40]
0x1800522b5  mov     rcx, [rsp+68h+var_18]
0x1800522ba  xor     rcx, rsp; StackCookie
0x1800522bd  call    __security_check_cookie
0x1800522c2  add     rsp, 60h
0x1800522c6  pop     rbx
0x1800522c7  retn
```
