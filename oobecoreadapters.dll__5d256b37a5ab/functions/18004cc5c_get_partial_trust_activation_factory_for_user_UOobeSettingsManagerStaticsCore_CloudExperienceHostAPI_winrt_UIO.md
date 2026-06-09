# ??$get_partial_trust_activation_factory_for_user@UOobeSettingsManagerStaticsCore@CloudExperienceHostAPI@winrt@@UIOobePrivacyNoticesManager@23@@winrt@@YA?A_PAEBUUser@System@Windows@0@@Z

- ea: `0x18004cc5c`
- end: `0x18004cdfc`
- name: `??$get_partial_trust_activation_factory_for_user@UOobeSettingsManagerStaticsCore@CloudExperienceHostAPI@winrt@@UIOobePrivacyNoticesManager@23@@winrt@@YA?A_PAEBUUser@System@Windows@0@@Z`
- size: `416`
- prototype: `__int64 __fastcall(winrt *this, struct winrt::Windows::System::User *)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18004f180`
- `0x180051b30`

## callees

- `0x180003230`
- `0x18000851c`
- `0x18001422c`
- `0x180015544`
- `0x180015694`
- `0x180015964`
- `0x18004c054`
- `0x18004cc5c`
- `0x18004d6f8`
- `0x18004df20`
- `0x18004ec04`
- `0x18004f788`
- `0x18005175c`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004ccc3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004ccc3`
- `combase!__imp_RoGetActivationFactoryAsUser` at `0x18004cd99`
- `combase!__imp_RoGetActivationFactoryAsUser` at `0x18004cd99`

## string_xrefs

- `0x18004ccd4`: `onecoreuap\internal\sdk\inc\ActivatePartialTrustComponentForUser.h`
- `0x18004cd32`: `onecoreuap\internal\sdk\inc\ActivatePartialTrustComponentForUser.h`
- `0x18004cdaa`: `onecoreuap\internal\sdk\inc\ActivatePartialTrustComponentForUser.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
winrt *__fastcall winrt::get_partial_trust_activation_factory_for_user<winrt::CloudExperienceHostAPI::OobeSettingsManagerStaticsCore,winrt::CloudExperienceHostAPI::IOobePrivacyNoticesManager>(
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
                                winrt::impl::guid_v<winrt::CloudExperienceHostAPI::IOobePrivacyNoticesManager>,
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
                          winrt::impl::guid_v<winrt::CloudExperienceHostAPI::IOobePrivacyNoticesManager>,
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
0x18004cc5c  mov     [rsp-20h+arg_0], rcx
0x18004cc61  push    rbp
0x18004cc62  push    rbx
0x18004cc63  push    rsi
0x18004cc64  push    rdi
0x18004cc65  mov     rbp, rsp
0x18004cc68  sub     rsp, 68h
0x18004cc6c  mov     rbx, rdx
0x18004cc6f  mov     rsi, rcx
0x18004cc72  mov     [rbp+arg_8], 1
0x18004cc79  cmp     qword ptr [rdx], 0
0x18004cc7d  jnz     short loc_18004CCF5
0x18004cc7f  mov     qword ptr [rcx], 0
0x18004cc86  mov     [rbp+arg_8], 3
0x18004cc8d  call    ?put_abi@winrt@@YAPEAPEAXAEAUIUnknown@Foundation@Windows@1@@Z; winrt::put_abi(winrt::Windows::Foundation::IUnknown &)
0x18004cc92  mov     rbx, rax
0x18004cc95  lea     rax, aCloudexperienc_48; "CloudExperienceHostAPI.OobeSettingsMana"...
0x18004cc9c  mov     [rbp+var_48], rax
0x18004cca0  mov     [rbp+var_40], 35h ; '5'
0x18004cca8  lea     rdx, [rbp+var_48]
0x18004ccac  lea     rcx, [rbp+Block]
0x18004ccb0  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x18004ccb5  nop
0x18004ccb6  mov     r8, rbx
0x18004ccb9  lea     rdx, ??$guid_v@UIOobePrivacyNoticesManager@CloudExperienceHostAPI@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::CloudExperienceHostAPI::IOobePrivacyNoticesManager>
0x18004ccc0  mov     rcx, [rax]
0x18004ccc3  call    cs:__imp_RoGetActivationFactory
0x18004ccc9  mov     rcx, [rbp+20h]; this
0x18004cccd  test    eax, eax
0x18004cccf  jns     short loc_18004CCE6
0x18004ccd1  mov     r9d, eax; char *
0x18004ccd4  lea     r8, aOnecoreuapInte_7; "onecoreuap\\internal\\sdk\\inc\\Activat"...
0x18004ccdb  mov     edx, 50h ; 'P'; void *
0x18004cce0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004cce6  lea     rcx, [rbp+Block]
0x18004ccea  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18004ccef  nop
0x18004ccf0  jmp     loc_18004CDF0
0x18004ccf5  lea     rcx, [rbp+var_28]; this
0x18004ccf9  call    ??0ConstrainedLoggedOnUserImpersonator@winrt@@QEAA@AEBUUser@System@Windows@1@@Z; winrt::ConstrainedLoggedOnUserImpersonator::ConstrainedLoggedOnUserImpersonator(winrt::Windows::System::User const &)
0x18004ccfe  nop
0x18004ccff  lea     rdx, [rbp+arg_18]
0x18004cd03  lea     rcx, [rbp+var_28]
0x18004cd07  call    ?DuplicateImpersonationToken@ConstrainedLoggedOnUserImpersonator@winrt@@QEAA?AU?$handle_type@Uhandle_traits@winrt@@@2@XZ; winrt::ConstrainedLoggedOnUserImpersonator::DuplicateImpersonationToken(void)
0x18004cd0c  nop
0x18004cd0d  mov     rdx, [rbp+arg_18]
0x18004cd11  lea     rcx, [rbp+Block]
0x18004cd15  call    ??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)
0x18004cd1a  nop
0x18004cd1b  mov     rcx, [rbp+Block]
0x18004cd1f  mov     rcx, [rcx]; void *
0x18004cd22  call    ?AddUserToProcessObject@@YAJPEAX@Z; AddUserToProcessObject(void *)
0x18004cd27  mov     rcx, [rbp+20h]; this
0x18004cd2b  test    eax, eax
0x18004cd2d  jns     short loc_18004CD44
0x18004cd2f  mov     r9d, eax; char *
0x18004cd32  lea     r8, aOnecoreuapInte_7; "onecoreuap\\internal\\sdk\\inc\\Activat"...
0x18004cd39  mov     edx, 41h ; 'A'; void *
0x18004cd3e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004cd44  mov     rcx, rbx; struct winrt::Windows::System::User *
0x18004cd47  call    ?GetHandleForUser@UserManager@Internal@System@Windows@winrt@@SA@AEBUUser@345@@Z; winrt::Windows::System::Internal::UserManager::GetHandleForUser(winrt::Windows::System::User const &)
0x18004cd4c  mov     rdi, rax
0x18004cd4f  mov     qword ptr [rsi], 0
0x18004cd56  mov     [rbp+arg_8], 0Dh
0x18004cd5d  mov     rcx, rsi; this
0x18004cd60  call    ?put_abi@winrt@@YAPEAPEAXAEAUIUnknown@Foundation@Windows@1@@Z; winrt::put_abi(winrt::Windows::Foundation::IUnknown &)
0x18004cd65  mov     rbx, rax
0x18004cd68  lea     rax, aCloudexperienc_48; "CloudExperienceHostAPI.OobeSettingsMana"...
0x18004cd6f  mov     [rbp+var_38], rax
0x18004cd73  mov     [rbp+var_30], 35h ; '5'
0x18004cd7b  lea     rdx, [rbp+var_38]
0x18004cd7f  lea     rcx, [rbp+var_48]
0x18004cd83  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x18004cd88  nop
0x18004cd89  mov     r9, rbx
0x18004cd8c  lea     r8, ??$guid_v@UIOobePrivacyNoticesManager@CloudExperienceHostAPI@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::CloudExperienceHostAPI::IOobePrivacyNoticesManager>
0x18004cd93  mov     rdx, rdi
0x18004cd96  mov     rcx, [rax]
0x18004cd99  call    cs:__imp_RoGetActivationFactoryAsUser
0x18004cd9f  mov     rcx, [rbp+20h]; this
0x18004cda3  test    eax, eax
0x18004cda5  jns     short loc_18004CDBC
0x18004cda7  mov     r9d, eax; char *
0x18004cdaa  lea     r8, aOnecoreuapInte_7; "onecoreuap\\internal\\sdk\\inc\\Activat"...
0x18004cdb1  mov     edx, 48h ; 'H'; void *
0x18004cdb6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004cdbc  lea     rcx, [rbp+var_48]
0x18004cdc0  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18004cdc5  nop
0x18004cdc6  mov     rcx, [rbp+Block]; Block
0x18004cdca  mov     [rbp+Block], 0
0x18004cdd2  test    rcx, rcx
0x18004cdd5  jz      short loc_18004CDDD
0x18004cdd7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004cddc  nop
0x18004cddd  lea     rcx, [rbp+arg_18]
0x18004cde1  call    ?close@?$handle_type@Uhandle_traits@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::handle_traits>::close(void)
0x18004cde6  nop
0x18004cde7  lea     rcx, [rbp+var_28]; this
0x18004cdeb  call    ??1ConstrainedLoggedOnUserImpersonator@winrt@@QEAA@XZ; winrt::ConstrainedLoggedOnUserImpersonator::~ConstrainedLoggedOnUserImpersonator(void)
0x18004cdf0  mov     rax, rsi
0x18004cdf3  add     rsp, 68h
0x18004cdf7  pop     rdi
0x18004cdf8  pop     rsi
0x18004cdf9  pop     rbx
0x18004cdfa  pop     rbp
0x18004cdfb  retn
```
