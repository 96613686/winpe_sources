# ??$get_partial_trust_activation_factory_for_user@UOobeSettingsManagerStaticsCore@CloudExperienceHostAPI@winrt@@UIOobeSettingsManager@23@@winrt@@YA?A_PAEBUUser@System@Windows@0@@Z

- ea: `0x18004ce04`
- end: `0x18004cfa4`
- name: `??$get_partial_trust_activation_factory_for_user@UOobeSettingsManagerStaticsCore@CloudExperienceHostAPI@winrt@@UIOobeSettingsManager@23@@winrt@@YA?A_PAEBUUser@System@Windows@0@@Z`
- size: `416`
- prototype: `__int64 __fastcall(winrt *this, struct winrt::Windows::System::User *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18004f420`

## callees

- `0x180003230`
- `0x18000851c`
- `0x18001422c`
- `0x180015544`
- `0x180015694`
- `0x180015964`
- `0x18004c054`
- `0x18004ce04`
- `0x18004d6f8`
- `0x18004df20`
- `0x18004ec04`
- `0x18004f788`
- `0x18005175c`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004ce6b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004ce6b`
- `combase!__imp_RoGetActivationFactoryAsUser` at `0x18004cf41`
- `combase!__imp_RoGetActivationFactoryAsUser` at `0x18004cf41`

## string_xrefs

- `0x18004ce7c`: `onecoreuap\internal\sdk\inc\ActivatePartialTrustComponentForUser.h`
- `0x18004ceda`: `onecoreuap\internal\sdk\inc\ActivatePartialTrustComponentForUser.h`
- `0x18004cf52`: `onecoreuap\internal\sdk\inc\ActivatePartialTrustComponentForUser.h`

## pseudocode

```c
winrt *__fastcall winrt::get_partial_trust_activation_factory_for_user<winrt::CloudExperienceHostAPI::OobeSettingsManagerStaticsCore,winrt::CloudExperienceHostAPI::IOobeSettingsManager>(
        winrt *this,
        struct winrt::Windows::System::User *a2)
{
  void **v4; // rbx
  _QWORD *v5; // rax
  int ActivationFactory; // eax
  int v7; // eax
  __int64 HandleForUser; // rdi
  struct IUnknown *v9; // rdx
  void **v10; // rbx
  _QWORD *v11; // rax
  int ActivationFactoryAsUser; // eax
  void *v13; // rcx
  _QWORD v15[2]; // [rsp+20h] [rbp-48h] BYREF
  _QWORD v16[2]; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v17[40]; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]
  void *Block; // [rsp+A0h] [rbp+38h] BYREF
  HANDLE v20; // [rsp+A8h] [rbp+40h] BYREF

  if ( *(_QWORD *)a2 )
  {
    winrt::ConstrainedLoggedOnUserImpersonator::ConstrainedLoggedOnUserImpersonator(
      (winrt::ConstrainedLoggedOnUserImpersonator *)v17,
      a2);
    winrt::ConstrainedLoggedOnUserImpersonator::DuplicateImpersonationToken((__int64)v17, &v20);
    wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(&Block, v20);
    v7 = AddUserToProcessObject(*(void **)Block);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x41,
        (unsigned int)"onecoreuap\\internal\\sdk\\inc\\ActivatePartialTrustComponentForUser.h",
        (const char *)(unsigned int)v7,
        v15[0]);
    HandleForUser = winrt::Windows::System::Internal::UserManager::GetHandleForUser(a2);
    *(_QWORD *)this = 0;
    v10 = winrt::put_abi(this, v9);
    v16[0] = L"CloudExperienceHostAPI.OobeSettingsManagerStaticsCore";
    v16[1] = 53;
    v11 = (_QWORD *)winrt::hstring::hstring(v15, v16);
    ActivationFactoryAsUser = RoGetActivationFactoryAsUser(
                                *v11,
                                HandleForUser,
                                winrt::impl::guid_v<winrt::CloudExperienceHostAPI::IOobeSettingsManager>,
                                v10);
    if ( ActivationFactoryAsUser < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x48,
        (unsigned int)"onecoreuap\\internal\\sdk\\inc\\ActivatePartialTrustComponentForUser.h",
        (const char *)(unsigned int)ActivationFactoryAsUser,
        v15[0]);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v15);
    v13 = Block;
    Block = 0;
    if ( v13 )
      operator delete(v13);
    winrt::handle_type<winrt::handle_traits>::close(&v20);
    winrt::ConstrainedLoggedOnUserImpersonator::~ConstrainedLoggedOnUserImpersonator((winrt::ConstrainedLoggedOnUserImpersonator *)v17);
  }
  else
  {
    *(_QWORD *)this = 0;
    v4 = winrt::put_abi(this, (struct IUnknown *)a2);
    v15[0] = L"CloudExperienceHostAPI.OobeSettingsManagerStaticsCore";
    v15[1] = 53;
    v5 = (_QWORD *)winrt::hstring::hstring(&Block, v15);
    ActivationFactory = RoGetActivationFactory(
                          *v5,
                          winrt::impl::guid_v<winrt::CloudExperienceHostAPI::IOobeSettingsManager>,
                          v4);
    if ( ActivationFactory < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x50,
        (unsigned int)"onecoreuap\\internal\\sdk\\inc\\ActivatePartialTrustComponentForUser.h",
        (const char *)(unsigned int)ActivationFactory,
        v15[0]);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&Block);
  }
  return this;
}

```

## disassembly

```asm
0x18004ce04  mov     [rsp-20h+arg_0], rcx
0x18004ce09  push    rbp
0x18004ce0a  push    rbx
0x18004ce0b  push    rsi
0x18004ce0c  push    rdi
0x18004ce0d  mov     rbp, rsp
0x18004ce10  sub     rsp, 68h
0x18004ce14  mov     rbx, rdx
0x18004ce17  mov     rsi, rcx
0x18004ce1a  mov     [rbp+arg_8], 1
0x18004ce21  cmp     qword ptr [rdx], 0
0x18004ce25  jnz     short loc_18004CE9D
0x18004ce27  mov     qword ptr [rcx], 0
0x18004ce2e  mov     [rbp+arg_8], 3
0x18004ce35  call    ?put_abi@winrt@@YAPEAPEAXAEAUIUnknown@Foundation@Windows@1@@Z; winrt::put_abi(winrt::Windows::Foundation::IUnknown &)
0x18004ce3a  mov     rbx, rax
0x18004ce3d  lea     rax, aCloudexperienc_48; "CloudExperienceHostAPI.OobeSettingsMana"...
0x18004ce44  mov     [rbp+var_48], rax
0x18004ce48  mov     [rbp+var_40], 35h ; '5'
0x18004ce50  lea     rdx, [rbp+var_48]
0x18004ce54  lea     rcx, [rbp+Block]
0x18004ce58  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x18004ce5d  nop
0x18004ce5e  mov     r8, rbx
0x18004ce61  lea     rdx, ??$guid_v@UIOobeSettingsManager@CloudExperienceHostAPI@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::CloudExperienceHostAPI::IOobeSettingsManager>
0x18004ce68  mov     rcx, [rax]
0x18004ce6b  call    cs:__imp_RoGetActivationFactory
0x18004ce71  mov     rcx, [rbp+20h]; this
0x18004ce75  test    eax, eax
0x18004ce77  jns     short loc_18004CE8E
0x18004ce79  mov     r9d, eax; char *
0x18004ce7c  lea     r8, aOnecoreuapInte_7; "onecoreuap\\internal\\sdk\\inc\\Activat"...
0x18004ce83  mov     edx, 50h ; 'P'; void *
0x18004ce88  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004ce8e  lea     rcx, [rbp+Block]
0x18004ce92  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18004ce97  nop
0x18004ce98  jmp     loc_18004CF98
0x18004ce9d  lea     rcx, [rbp+var_28]; this
0x18004cea1  call    ??0ConstrainedLoggedOnUserImpersonator@winrt@@QEAA@AEBUUser@System@Windows@1@@Z; winrt::ConstrainedLoggedOnUserImpersonator::ConstrainedLoggedOnUserImpersonator(winrt::Windows::System::User const &)
0x18004cea6  nop
0x18004cea7  lea     rdx, [rbp+arg_18]
0x18004ceab  lea     rcx, [rbp+var_28]
0x18004ceaf  call    ?DuplicateImpersonationToken@ConstrainedLoggedOnUserImpersonator@winrt@@QEAA?AU?$handle_type@Uhandle_traits@winrt@@@2@XZ; winrt::ConstrainedLoggedOnUserImpersonator::DuplicateImpersonationToken(void)
0x18004ceb4  nop
0x18004ceb5  mov     rdx, [rbp+arg_18]
0x18004ceb9  lea     rcx, [rbp+Block]
0x18004cebd  call    ??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)
0x18004cec2  nop
0x18004cec3  mov     rcx, [rbp+Block]
0x18004cec7  mov     rcx, [rcx]; void *
0x18004ceca  call    ?AddUserToProcessObject@@YAJPEAX@Z; AddUserToProcessObject(void *)
0x18004cecf  mov     rcx, [rbp+20h]; this
0x18004ced3  test    eax, eax
0x18004ced5  jns     short loc_18004CEEC
0x18004ced7  mov     r9d, eax; char *
0x18004ceda  lea     r8, aOnecoreuapInte_7; "onecoreuap\\internal\\sdk\\inc\\Activat"...
0x18004cee1  mov     edx, 41h ; 'A'; void *
0x18004cee6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004ceec  mov     rcx, rbx; struct winrt::Windows::System::User *
0x18004ceef  call    ?GetHandleForUser@UserManager@Internal@System@Windows@winrt@@SA@AEBUUser@345@@Z; winrt::Windows::System::Internal::UserManager::GetHandleForUser(winrt::Windows::System::User const &)
0x18004cef4  mov     rdi, rax
0x18004cef7  mov     qword ptr [rsi], 0
0x18004cefe  mov     [rbp+arg_8], 0Dh
0x18004cf05  mov     rcx, rsi; this
0x18004cf08  call    ?put_abi@winrt@@YAPEAPEAXAEAUIUnknown@Foundation@Windows@1@@Z; winrt::put_abi(winrt::Windows::Foundation::IUnknown &)
0x18004cf0d  mov     rbx, rax
0x18004cf10  lea     rax, aCloudexperienc_48; "CloudExperienceHostAPI.OobeSettingsMana"...
0x18004cf17  mov     [rbp+var_38], rax
0x18004cf1b  mov     [rbp+var_30], 35h ; '5'
0x18004cf23  lea     rdx, [rbp+var_38]
0x18004cf27  lea     rcx, [rbp+var_48]
0x18004cf2b  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x18004cf30  nop
0x18004cf31  mov     r9, rbx
0x18004cf34  lea     r8, ??$guid_v@UIOobeSettingsManager@CloudExperienceHostAPI@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::CloudExperienceHostAPI::IOobeSettingsManager>
0x18004cf3b  mov     rdx, rdi
0x18004cf3e  mov     rcx, [rax]
0x18004cf41  call    cs:__imp_RoGetActivationFactoryAsUser
0x18004cf47  mov     rcx, [rbp+20h]; this
0x18004cf4b  test    eax, eax
0x18004cf4d  jns     short loc_18004CF64
0x18004cf4f  mov     r9d, eax; char *
0x18004cf52  lea     r8, aOnecoreuapInte_7; "onecoreuap\\internal\\sdk\\inc\\Activat"...
0x18004cf59  mov     edx, 48h ; 'H'; void *
0x18004cf5e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004cf64  lea     rcx, [rbp+var_48]
0x18004cf68  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18004cf6d  nop
0x18004cf6e  mov     rcx, [rbp+Block]; Block
0x18004cf72  mov     [rbp+Block], 0
0x18004cf7a  test    rcx, rcx
0x18004cf7d  jz      short loc_18004CF85
0x18004cf7f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004cf84  nop
0x18004cf85  lea     rcx, [rbp+arg_18]
0x18004cf89  call    ?close@?$handle_type@Uhandle_traits@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::handle_traits>::close(void)
0x18004cf8e  nop
0x18004cf8f  lea     rcx, [rbp+var_28]; this
0x18004cf93  call    ??1ConstrainedLoggedOnUserImpersonator@winrt@@QEAA@XZ; winrt::ConstrainedLoggedOnUserImpersonator::~ConstrainedLoggedOnUserImpersonator(void)
0x18004cf98  mov     rax, rsi
0x18004cf9b  add     rsp, 68h
0x18004cf9f  pop     rdi
0x18004cfa0  pop     rsi
0x18004cfa1  pop     rbx
0x18004cfa2  pop     rbp
0x18004cfa3  retn
```
