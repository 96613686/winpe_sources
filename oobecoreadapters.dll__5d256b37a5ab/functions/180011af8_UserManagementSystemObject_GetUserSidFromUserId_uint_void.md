# UserManagementSystemObject::GetUserSidFromUserId(uint,void * *)

- ea: `0x180011af8`
- end: `0x180011cef`
- name: `?GetUserSidFromUserId@UserManagementSystemObject@@AEAAJIPEAPEAX@Z`
- size: `503`
- prototype: `int(UserManagementSystemObject *__hidden this, unsigned int, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180011800`

## callees

- `0x180002b60`
- `0x1800076b4`
- `0x1800076d4`
- `0x180009760`
- `0x18000a4f8`
- `0x1800117bc`
- `0x180011af8`
- `0x180011db0`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180011c7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180011c7c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180011c88`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180011c88`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180011b5a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180011b5a`

## string_xrefs

- `0x180011b6d`: `shellcommon\shell\oobe\core\components\com\usermanagement.cpp`
- `0x180011bb6`: `shellcommon\shell\oobe\core\components\com\usermanagement.cpp`
- `0x180011c05`: `shellcommon\shell\oobe\core\components\com\usermanagement.cpp`
- `0x180011c59`: `shellcommon\shell\oobe\core\components\com\usermanagement.cpp`
- `0x180011c96`: `shellcommon\shell\oobe\core\components\com\usermanagement.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall UserManagementSystemObject::GetUserSidFromUserId(
        UserManagementSystemObject *this,
        unsigned int a2,
        void **a3)
{
  int ActivationFactory; // eax
  unsigned int LastError; // ebx
  __int64 v7; // rax
  int v8; // eax
  int v9; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64); // rbx
  __int64 v12; // rax
  int v13; // eax
  const WCHAR *StringRawBuffer; // rax
  const char *v15; // r9
  __int64 (__fastcall ***v17)(_QWORD, GUID *, __int64 *); // [rsp+20h] [rbp-50h] BYREF
  __int64 v18; // [rsp+28h] [rbp-48h] BYREF
  HSTRING string; // [rsp+30h] [rbp-40h] BYREF
  __int64 *v20; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  __int64 v22; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  *a3 = 0;
  v20 = 0;
  v22 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.System.Internal.UserManager",
    0x24u,
    0x23u);
  ActivationFactory = RoGetActivationFactory(v22, &GUID_252e7f79_acfa_4ea2_9a7e_fa27a8a4d3d9, &v20);
  LastError = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v17 = 0;
    v7 = *v20;
    v17 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD))(v7 + 96))(v20, a2, &v17);
    LastError = v8;
    if ( v8 >= 0 )
    {
      v18 = 0;
      v9 = (**v17)(v17, &GUID_2a426936_3887_4e38_9b4b_6064463481b8, &v18);
      LastError = v9;
      if ( v9 >= 0 )
      {
        string = 0;
        v10 = v18;
        v11 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v18 + 56LL);
        v12 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::put(&string);
        v13 = v11(v10, v12);
        LastError = v13;
        if ( v13 >= 0 )
        {
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          if ( ConvertStringSidToSidW(StringRawBuffer, a3) )
          {
            Windows::Internal::String::~String((Windows::Internal::String *)&string);
            wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v18);
            wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v17);
            LastError = 0;
            goto LABEL_15;
          }
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x47,
                        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\usermanagement.cpp",
                        v15);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x46,
            (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\usermanagement.cpp",
            (const char *)(unsigned int)v13,
            (int)v17);
        }
        Windows::Internal::String::~String((Windows::Internal::String *)&string);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x43,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\usermanagement.cpp",
          (const char *)(unsigned int)v9,
          (int)v17);
      }
      wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v18);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x41,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\usermanagement.cpp",
        (const char *)(unsigned int)v8,
        (int)v17);
    }
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v17);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\usermanagement.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)v17);
  }
LABEL_15:
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v20);
  return LastError;
}

```

## disassembly

```asm
0x180011af8  mov     [rsp-18h+arg_0], rbx
0x180011afd  push    rbp
0x180011afe  push    rsi
0x180011aff  push    rdi
0x180011b00  mov     rbp, rsp
0x180011b03  sub     rsp, 70h
0x180011b07  mov     rax, cs:__security_cookie
0x180011b0e  xor     rax, rsp
0x180011b11  mov     [rbp+var_10], rax
0x180011b15  mov     rsi, r8
0x180011b18  mov     edi, edx
0x180011b1a  mov     qword ptr [r8], 0
0x180011b21  mov     [rbp+var_38], 0
0x180011b29  mov     [rbp+var_18], 0
0x180011b31  mov     r9d, 23h ; '#'; unsigned int
0x180011b37  lea     r8d, [r9+1]; unsigned int
0x180011b3b  lea     rdx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x180011b42  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180011b46  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180011b4b  lea     r8, [rbp+var_38]
0x180011b4f  lea     rdx, _GUID_252e7f79_acfa_4ea2_9a7e_fa27a8a4d3d9
0x180011b56  mov     rcx, [rbp+var_18]
0x180011b5a  call    cs:__imp_RoGetActivationFactory
0x180011b60  mov     ebx, eax
0x180011b62  test    eax, eax
0x180011b64  jns     short loc_180011B83
0x180011b66  mov     rcx, [rbp+18h]; this
0x180011b6a  mov     r9d, eax; char *
0x180011b6d  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\oobe\\core\\compone"...
0x180011b74  mov     edx, 3Eh ; '>'; void *
0x180011b79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011b7e  jmp     loc_180011CC8
0x180011b83  mov     [rbp+var_50], 0
0x180011b8b  mov     rcx, [rbp+var_38]
0x180011b8f  mov     rax, [rcx]
0x180011b92  mov     [rbp+var_50], 0
0x180011b9a  lea     r8, [rbp+var_50]
0x180011b9e  mov     edx, edi
0x180011ba0  mov     rax, [rax+60h]
0x180011ba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ba9  mov     ebx, eax
0x180011bab  test    eax, eax
0x180011bad  jns     short loc_180011BD6
0x180011baf  mov     rcx, [rbp+18h]; this
0x180011bb3  mov     r9d, eax; char *
0x180011bb6  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\oobe\\core\\compone"...
0x180011bbd  mov     edx, 41h ; 'A'; void *
0x180011bc2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011bc7  nop
0x180011bc8  lea     rcx, [rbp+var_50]
0x180011bcc  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180011bd1  jmp     loc_180011CC8
0x180011bd6  mov     [rbp+var_48], 0
0x180011bde  mov     rcx, [rbp+var_50]
0x180011be2  mov     rax, [rcx]
0x180011be5  lea     r8, [rbp+var_48]
0x180011be9  lea     rdx, _GUID_2a426936_3887_4e38_9b4b_6064463481b8
0x180011bf0  mov     rax, [rax]
0x180011bf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011bf8  mov     ebx, eax
0x180011bfa  test    eax, eax
0x180011bfc  jns     short loc_180011C22
0x180011bfe  mov     rcx, [rbp+18h]; this
0x180011c02  mov     r9d, eax; char *
0x180011c05  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\oobe\\core\\compone"...
0x180011c0c  mov     edx, 43h ; 'C'; void *
0x180011c11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011c16  nop
0x180011c17  lea     rcx, [rbp+var_48]
0x180011c1b  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180011c20  jmp     short loc_180011BC8
0x180011c22  mov     [rbp+string], 0
0x180011c2a  mov     rdi, [rbp+var_48]
0x180011c2e  mov     rax, [rdi]
0x180011c31  mov     rbx, [rax+38h]
0x180011c35  lea     rcx, [rbp+string]
0x180011c39  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHSTRING__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::put(void)
0x180011c3e  mov     rdx, rax
0x180011c41  mov     rcx, rdi
0x180011c44  mov     rax, rbx
0x180011c47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c4c  mov     ebx, eax
0x180011c4e  test    eax, eax
0x180011c50  jns     short loc_180011C76
0x180011c52  mov     rcx, [rbp+18h]; this
0x180011c56  mov     r9d, eax; char *
0x180011c59  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\oobe\\core\\compone"...
0x180011c60  mov     edx, 46h ; 'F'; void *
0x180011c65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011c6a  nop
0x180011c6b  lea     rcx, [rbp+string]; this
0x180011c6f  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180011c74  jmp     short loc_180011C17
0x180011c76  xor     edx, edx; length
0x180011c78  mov     rcx, [rbp+string]; string
0x180011c7c  call    cs:__imp_WindowsGetStringRawBuffer
0x180011c82  mov     rcx, rax; StringSid
0x180011c85  mov     rdx, rsi; Sid
0x180011c88  call    cs:__imp_ConvertStringSidToSidW
0x180011c8e  test    eax, eax
0x180011c90  jnz     short loc_180011CA9
0x180011c92  mov     rcx, [rbp+18h]; this
0x180011c96  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\oobe\\core\\compone"...
0x180011c9d  lea     edx, [rax+47h]; void *
0x180011ca0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011ca5  mov     ebx, eax
0x180011ca7  jmp     short loc_180011C6B
0x180011ca9  lea     rcx, [rbp+string]; this
0x180011cad  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180011cb2  nop
0x180011cb3  lea     rcx, [rbp+var_48]
0x180011cb7  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180011cbc  nop
0x180011cbd  lea     rcx, [rbp+var_50]
0x180011cc1  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180011cc6  xor     ebx, ebx
0x180011cc8  lea     rcx, [rbp+var_38]
0x180011ccc  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180011cd1  mov     eax, ebx
0x180011cd3  mov     rcx, [rbp+var_10]
0x180011cd7  xor     rcx, rsp; StackCookie
0x180011cda  call    __security_check_cookie
0x180011cdf  mov     rbx, [rsp+70h+arg_0]
0x180011ce7  add     rsp, 70h
0x180011ceb  pop     rdi
0x180011cec  pop     rsi
0x180011ced  pop     rbp
0x180011cee  retn
```
