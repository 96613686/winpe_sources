# CloudExperienceHostAPI::BackupRestoreManager::_GetDefaultWebAccount(Windows::Security::Credentials::IWebAccount * *)

- ea: `0x18002c984`
- end: `0x18002cb0d`
- name: `?_GetDefaultWebAccount@BackupRestoreManager@CloudExperienceHostAPI@@CAJPEAPEAUIWebAccount@Credentials@Security@Windows@@@Z`
- size: `393`
- prototype: `__int64 __fastcall(struct Windows::Security::Credentials::IWebAccount **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002cc1c`

## callees

- `0x180002b60`
- `0x1800076d4`
- `0x180009760`
- `0x18000a4f8`
- `0x18002031c`
- `0x18002c984`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002c9e1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002c9e1`

## string_xrefs

- `0x18002c9c2`: `Windows.Internal.Security.Authentication.Web.TokenBrokerInternal`
- `0x18002c9f4`: `shellcommon\shell\oobe\core\components\winrt\backuprestoremanager.cpp`
- `0x18002ca3e`: `shellcommon\shell\oobe\core\components\winrt\backuprestoremanager.cpp`
- `0x18002ca99`: `shellcommon\shell\oobe\core\components\winrt\backuprestoremanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CloudExperienceHostAPI::BackupRestoreManager::_GetDefaultWebAccount(
        struct Windows::Security::Credentials::IWebAccount **a1)
{
  int ActivationFactory; // eax
  int DefaultSignInAccount; // ebx
  __int64 v4; // rax
  int v5; // eax
  __int64 v6; // rdi
  unsigned __int64 v7; // r9
  __int64 v8; // rdx
  int v9; // eax
  __int64 v11; // [rsp+20h] [rbp-48h] BYREF
  __int64 v12; // [rsp+28h] [rbp-40h] BYREF
  __int64 *v13; // [rsp+30h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-30h] BYREF
  __int64 v15; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]

  *a1 = 0;
  v13 = 0;
  v15 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.Security.Authentication.Web.TokenBrokerInternal",
    0x41u,
    0x40u);
  ActivationFactory = RoGetActivationFactory(v15, &GUID_07650a66_66ea_489d_aa90_0dabc75f3567, &v13);
  DefaultSignInAccount = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v11 = 0;
    v4 = *v13;
    v11 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v4 + 232))(v13, &v11);
    DefaultSignInAccount = v5;
    if ( v5 >= 0 )
    {
      v12 = 0;
      v6 = v11;
      DefaultSignInAccount = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *>(v11);
      if ( DefaultSignInAccount >= 0 )
        DefaultSignInAccount = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v6 + 64LL))(v6, &v12);
      if ( DefaultSignInAccount >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, struct Windows::Security::Credentials::IWebAccount **))(*(_QWORD *)v12 + 48LL))(
               v12,
               a1);
        DefaultSignInAccount = v9;
        if ( v9 >= 0 )
        {
          wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v12);
          wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v11);
          DefaultSignInAccount = 0;
          goto LABEL_14;
        }
        v7 = (unsigned int)v9;
        v8 = 769;
      }
      else
      {
        v7 = (unsigned int)DefaultSignInAccount;
        v8 = 767;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\backuprestoremanager.cpp",
        (const char *)v7,
        v11);
      wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v12);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2FC,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\backuprestoremanager.cpp",
        (const char *)(unsigned int)v5,
        v11);
    }
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v11);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F9,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\backuprestoremanager.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v11);
  }
LABEL_14:
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v13);
  return (unsigned int)DefaultSignInAccount;
}

```

## disassembly

```asm
0x18002c984  push    rbp
0x18002c986  push    rbx
0x18002c987  push    rsi
0x18002c988  push    rdi
0x18002c989  mov     rbp, rsp
0x18002c98c  sub     rsp, 68h
0x18002c990  mov     rax, cs:__security_cookie
0x18002c997  xor     rax, rsp
0x18002c99a  mov     [rbp+var_10], rax
0x18002c99e  mov     rsi, rcx
0x18002c9a1  mov     qword ptr [rcx], 0
0x18002c9a8  mov     [rbp+var_38], 0
0x18002c9b0  mov     [rbp+var_18], 0
0x18002c9b8  mov     r9d, 40h ; '@'; unsigned int
0x18002c9be  lea     r8d, [r9+1]; unsigned int
0x18002c9c2  lea     rdx, ?RuntimeClass_Windows_Internal_Security_Authentication_Web_TokenBrokerInternal@@3QBGB; "Windows.Internal.Security.Authenticatio"...
0x18002c9c9  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18002c9cd  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002c9d2  lea     r8, [rbp+var_38]
0x18002c9d6  lea     rdx, _GUID_07650a66_66ea_489d_aa90_0dabc75f3567
0x18002c9dd  mov     rcx, [rbp+var_18]
0x18002c9e1  call    cs:__imp_RoGetActivationFactory
0x18002c9e7  mov     ebx, eax
0x18002c9e9  test    eax, eax
0x18002c9eb  jns     short loc_18002CA0A
0x18002c9ed  mov     rcx, [rbp+20h]; this
0x18002c9f1  mov     r9d, eax; char *
0x18002c9f4  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\oobe\\core\\compone"...
0x18002c9fb  mov     edx, 2F9h; void *
0x18002ca00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ca05  jmp     loc_18002CAED
0x18002ca0a  mov     [rbp+var_48], 0
0x18002ca12  mov     rcx, [rbp+var_38]
0x18002ca16  mov     rax, [rcx]
0x18002ca19  mov     [rbp+var_48], 0
0x18002ca21  lea     rdx, [rbp+var_48]
0x18002ca25  mov     rax, [rax+0E8h]
0x18002ca2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ca31  mov     ebx, eax
0x18002ca33  test    eax, eax
0x18002ca35  jns     short loc_18002CA5E
0x18002ca37  mov     rcx, [rbp+20h]; this
0x18002ca3b  mov     r9d, eax; char *
0x18002ca3e  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\oobe\\core\\compone"...
0x18002ca45  mov     edx, 2FCh; void *
0x18002ca4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ca4f  nop
0x18002ca50  lea     rcx, [rbp+var_48]
0x18002ca54  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18002ca59  jmp     loc_18002CAED
0x18002ca5e  mov     [rbp+var_40], 0
0x18002ca66  mov     rdi, [rbp+var_48]
0x18002ca6a  mov     rcx, rdi
0x18002ca6d  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x18002ca72  mov     ebx, eax
0x18002ca74  test    eax, eax
0x18002ca76  js      short loc_18002CA8D
0x18002ca78  mov     rax, [rdi]
0x18002ca7b  lea     rdx, [rbp+var_40]
0x18002ca7f  mov     rcx, rdi
0x18002ca82  mov     rax, [rax+40h]
0x18002ca86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ca8b  mov     ebx, eax
0x18002ca8d  test    ebx, ebx
0x18002ca8f  jns     short loc_18002CAB5
0x18002ca91  mov     r9d, ebx; char *
0x18002ca94  mov     edx, 2FFh; void *
0x18002ca99  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\oobe\\core\\compone"...
0x18002caa0  mov     rcx, [rbp+20h]; this
0x18002caa4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002caa9  nop
0x18002caaa  lea     rcx, [rbp+var_40]
0x18002caae  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18002cab3  jmp     short loc_18002CA50
0x18002cab5  mov     rcx, [rbp+var_40]
0x18002cab9  mov     rax, [rcx]
0x18002cabc  mov     rdx, rsi
0x18002cabf  mov     rax, [rax+30h]
0x18002cac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cac8  mov     ebx, eax
0x18002caca  test    eax, eax
0x18002cacc  jns     short loc_18002CAD8
0x18002cace  mov     r9d, eax
0x18002cad1  mov     edx, 301h
0x18002cad6  jmp     short loc_18002CA99
0x18002cad8  lea     rcx, [rbp+var_40]
0x18002cadc  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18002cae1  nop
0x18002cae2  lea     rcx, [rbp+var_48]
0x18002cae6  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18002caeb  xor     ebx, ebx
0x18002caed  lea     rcx, [rbp+var_38]
0x18002caf1  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18002caf6  mov     eax, ebx
0x18002caf8  mov     rcx, [rbp+var_10]
0x18002cafc  xor     rcx, rsp; StackCookie
0x18002caff  call    __security_check_cookie
0x18002cb04  add     rsp, 68h
0x18002cb08  pop     rdi
0x18002cb09  pop     rsi
0x18002cb0a  pop     rbx
0x18002cb0b  pop     rbp
0x18002cb0c  retn
```
