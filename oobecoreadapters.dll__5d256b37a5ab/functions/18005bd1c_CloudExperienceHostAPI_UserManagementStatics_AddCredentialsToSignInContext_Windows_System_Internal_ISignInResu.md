# CloudExperienceHostAPI::UserManagementStatics::AddCredentialsToSignInContext(Windows::System::Internal::ISignInResult *,Windows::System::Internal::ISignInContext *)

- ea: `0x18005bd1c`
- end: `0x18005c102`
- name: `?AddCredentialsToSignInContext@UserManagementStatics@CloudExperienceHostAPI@@CAJPEAUISignInResult@Internal@System@Windows@@PEAUISignInContext@456@@Z`
- size: `998`
- prototype: `__int64 __fastcall(struct Windows::System::Internal::ISignInResult *, struct Windows::System::Internal::ISignInContext *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18005c3c0`

## callees

- `0x180002b60`
- `0x1800041b5`
- `0x1800076b4`
- `0x1800076d4`
- `0x180009760`
- `0x18000a4f8`
- `0x18000daa0`
- `0x1800111c8`
- `0x1800117bc`
- `0x180011db0`
- `0x1800314ac`
- `0x18005b870`
- `0x18005bd1c`
- `0x18005ce80`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005be65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005be65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18005bdf1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18005bdf1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005be27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005be27`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18005bf89`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18005bf89`
- `ext-ms-win-security-credui-l1-1-0!CredPackAuthenticationBufferW` at `0x18005be4c`
- `ext-ms-win-security-credui-l1-1-0!CredPackAuthenticationBufferW` at `0x18005bf1d`
- `ext-ms-win-security-credui-l1-1-0!CredPackAuthenticationBufferW` at `0x18005be4c`
- `ext-ms-win-security-credui-l1-1-0!CredPackAuthenticationBufferW` at `0x18005bf1d`

## string_xrefs

- `0x18005bd74`: `shellcommon\shell\oobe\core\components\winrt\usermanagement.cpp`
- `0x18005bdb9`: `shellcommon\shell\oobe\core\components\winrt\usermanagement.cpp`
- `0x18005be05`: `shellcommon\shell\oobe\core\components\winrt\usermanagement.cpp`
- `0x18005be74`: `shellcommon\shell\oobe\core\components\winrt\usermanagement.cpp`
- `0x18005bee2`: `shellcommon\shell\oobe\core\components\winrt\usermanagement.cpp`
- `0x18005bf2b`: `shellcommon\shell\oobe\core\components\winrt\usermanagement.cpp`
- `0x18005bff4`: `shellcommon\shell\oobe\core\components\winrt\usermanagement.cpp`
- `0x18005c044`: `shellcommon\shell\oobe\core\components\winrt\usermanagement.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CloudExperienceHostAPI::UserManagementStatics::AddCredentialsToSignInContext(
        struct Windows::System::Internal::ISignInResult *a1,
        struct Windows::System::Internal::ISignInContext *a2)
{
  int LastError; // ebx
  __int64 (__fastcall *v5)(struct Windows::System::Internal::ISignInResult *, __int64); // rbx
  __int64 v6; // rax
  int v7; // eax
  HSTRING *v8; // rax
  HRESULT v9; // eax
  __int64 v10; // r9
  __int64 v11; // rdx
  WCHAR *StringRawBuffer; // rdi
  const char *v13; // r9
  void *v14; // rcx
  unsigned int v15; // r10d
  const char *v16; // r9
  int v17; // eax
  __int64 v18; // rdx
  int pcbPackedCredentials; // [rsp+20h] [rbp-49h]
  int pcbPackedCredentialsa; // [rsp+20h] [rbp-49h]
  HSTRING string2; // [rsp+30h] [rbp-39h] BYREF
  HSTRING string; // [rsp+38h] [rbp-31h] BYREF
  __int64 (__fastcall ***v24)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-29h] BYREF
  PBYTE pPackedCredentials; // [rsp+48h] [rbp-21h] BYREF
  DWORD v26; // [rsp+50h] [rbp-19h] BYREF
  unsigned __int64 v27; // [rsp+58h] [rbp-11h] BYREF
  __int64 v28; // [rsp+60h] [rbp-9h] BYREF
  HSTRING string1; // [rsp+68h] [rbp-1h] BYREF
  __int64 v30; // [rsp+70h] [rbp+7h] BYREF
  DWORD v31; // [rsp+78h] [rbp+Fh]
  int v32; // [rsp+7Ch] [rbp+13h]
  PBYTE v33; // [rsp+80h] [rbp+17h]
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp+1Fh] BYREF
  __int64 v35; // [rsp+A0h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
    &string1,
    L".\\",
    -1);
  if ( string1 )
  {
    string2 = 0;
    v5 = *(__int64 (__fastcall **)(struct Windows::System::Internal::ISignInResult *, __int64))(*(_QWORD *)a1 + 48LL);
    v6 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::put(&string2);
    v7 = v5(a1, v6);
    LastError = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC3,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\usermanagement.cpp",
        (const char *)(unsigned int)v7,
        pcbPackedCredentials);
LABEL_5:
      Windows::Internal::String::~String((Windows::Internal::String *)&string2);
      goto LABEL_36;
    }
    string = 0;
    v8 = (HSTRING *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::put(&string);
    v9 = WindowsConcatString(string1, string2, v8);
    LastError = v9;
    if ( v9 >= 0 )
    {
      StringRawBuffer = (WCHAR *)WindowsGetStringRawBuffer(string, 0);
      v26 = 0;
      if ( !CredPackAuthenticationBufferW(0, StringRawBuffer, (LPWSTR)&sourceString, 0, &v26) )
      {
        if ( GetLastError() == 122 )
        {
          pPackedCredentials = 0;
          hstringHeader.Reserved.Reserved1 = &pPackedCredentials;
          hstringHeader.Reserved.Reserved2[16] = 1;
          *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
          v27 = 0;
          LastError = ULongLongMult(v26, 1u, &v27);
          if ( LastError >= 0 )
            LastError = CTCoAllocPolicy::Alloc(v14, v15, v27, (void **)&hstringHeader.Reserved.Reserved2[8]);
          wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::cotaskmem_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::cotaskmem_secure_deleter>>(&hstringHeader);
          if ( LastError >= 0 )
          {
            if ( CredPackAuthenticationBufferW(0, StringRawBuffer, (LPWSTR)&sourceString, pPackedCredentials, &v26) )
            {
              v32 = 0;
              v30 = 0;
              v31 = v26;
              v33 = pPackedCredentials;
              v24 = 0;
              v35 = 0;
              Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                &hstringHeader,
                L"Windows.System.Internal.CredentialSerialization",
                0x30u,
                0x2Fu);
              v24 = 0;
              v27 = 0;
              LastError = RoActivateInstance(v35, &v27);
              if ( LastError >= 0 )
              {
                if ( !memcmp_0(
                        &GUID_c39ab8a5_824f_4acf_92e0_bb53b8a90555,
                        &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
                        0x10u) )
                {
                  v24 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v27;
                }
                else
                {
                  LastError = (**(__int64 (__fastcall ***)(unsigned __int64, GUID *, _QWORD))v27)(
                                v27,
                                &GUID_c39ab8a5_824f_4acf_92e0_bb53b8a90555,
                                &v24);
                  (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v27 + 16LL))(v27);
                }
              }
              if ( LastError >= 0 )
              {
                v28 = 0;
                v17 = (**v24)(v24, &GUID_d67b68f7_dd86_4af5_9046_22bb7b089209, &v28);
                LastError = v17;
                if ( v17 >= 0 )
                {
                  v17 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v28 + 24LL))(v28, &v30);
                  LastError = v17;
                  if ( v17 >= 0 )
                  {
                    v17 = (*(__int64 (__fastcall **)(struct Windows::System::Internal::ISignInContext *, __int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)a2 + 120LL))(
                            a2,
                            v24);
                    LastError = v17;
                    if ( v17 >= 0 )
                    {
                      wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v28);
                      wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v24);
                      wistd::unique_ptr<unsigned char,wil::cotaskmem_secure_deleter>::reset(&pPackedCredentials, 0);
                      Windows::Internal::String::~String((Windows::Internal::String *)&string);
                      Windows::Internal::String::~String((Windows::Internal::String *)&string2);
                      LastError = 0;
                      goto LABEL_36;
                    }
                    v18 = 223;
                  }
                  else
                  {
                    v18 = 221;
                  }
                }
                else
                {
                  v18 = 220;
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v18,
                  (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\usermanagement.cpp",
                  (const char *)(unsigned int)v17,
                  pcbPackedCredentialsa);
                wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v28);
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xD9,
                  (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\usermanagement.cpp",
                  (const char *)(unsigned int)LastError,
                  pcbPackedCredentialsa);
              }
              wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v24);
            }
            else
            {
              LastError = wil::details::in1diag3::Return_GetLastError(
                            retaddr,
                            (void *)0xCF,
                            (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\usermanagement.cpp",
                            v16);
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xCE,
              (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\usermanagement.cpp",
              (const char *)(unsigned int)LastError,
              pcbPackedCredentials);
          }
          wistd::unique_ptr<unsigned char,wil::cotaskmem_secure_deleter>::reset(&pPackedCredentials, 0);
        }
        else
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0xCC,
                        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\usermanagement.cpp",
                        v13);
        }
        goto LABEL_9;
      }
      LastError = -2147418113;
      v10 = 2147549183LL;
      v11 = 203;
    }
    else
    {
      v10 = (unsigned int)v9;
      v11 = 198;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\usermanagement.cpp",
      (const char *)v10,
      pcbPackedCredentials);
LABEL_9:
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    goto LABEL_5;
  }
  LastError = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC0,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\usermanagement.cpp",
    (const char *)0x8007000ELL,
    pcbPackedCredentials);
LABEL_36:
  Windows::Internal::String::~String((Windows::Internal::String *)&string1);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18005bd1c  mov     [rsp-8+arg_10], rbx
0x18005bd21  mov     [rsp-8+arg_18], rsi
0x18005bd26  push    rbp
0x18005bd27  push    rdi
0x18005bd28  push    r14
0x18005bd2a  lea     rbp, [rsp-47h]
0x18005bd2f  sub     rsp, 0B0h
0x18005bd36  mov     rax, cs:__security_cookie
0x18005bd3d  xor     rax, rsp
0x18005bd40  mov     [rbp+57h+var_18], rax
0x18005bd44  mov     rsi, rdx
0x18005bd47  mov     rdi, rcx
0x18005bd4a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18005bd4e  lea     rdx, asc_180098F4C; ".\\"
0x18005bd55  lea     rcx, [rbp+57h+string1]
0x18005bd59  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18005bd5e  nop
0x18005bd5f  xor     r14d, r14d
0x18005bd62  cmp     [rbp+57h+string1], r14
0x18005bd66  jnz     short loc_18005BD8A
0x18005bd68  mov     rcx, [rbp+5Fh]; this
0x18005bd6c  mov     ebx, 8007000Eh
0x18005bd71  mov     r9d, ebx; char *
0x18005bd74  lea     r8, aShellcommonShe; "shellcommon\\shell\\oobe\\core\\compone"...
0x18005bd7b  mov     edx, 0C0h; void *
0x18005bd80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005bd85  jmp     loc_18005C0D3
0x18005bd8a  mov     [rbp+57h+string2], r14
0x18005bd8e  mov     rax, [rdi]
0x18005bd91  mov     rbx, [rax+30h]
0x18005bd95  lea     rcx, [rbp+57h+string2]
0x18005bd99  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHSTRING__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::put(void)
0x18005bd9e  mov     rdx, rax
0x18005bda1  mov     rcx, rdi
0x18005bda4  mov     rax, rbx
0x18005bda7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bdac  mov     ebx, eax
0x18005bdae  test    eax, eax
0x18005bdb0  jns     short loc_18005BDD9
0x18005bdb2  mov     rcx, [rbp+5Fh]; this
0x18005bdb6  mov     r9d, eax; char *
0x18005bdb9  lea     r8, aShellcommonShe; "shellcommon\\shell\\oobe\\core\\compone"...
0x18005bdc0  mov     edx, 0C3h; void *
0x18005bdc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005bdca  nop
0x18005bdcb  lea     rcx, [rbp+57h+string2]; this
0x18005bdcf  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18005bdd4  jmp     loc_18005C0D3
0x18005bdd9  mov     [rbp+57h+string], r14
0x18005bddd  lea     rcx, [rbp+57h+string]
0x18005bde1  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHSTRING__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::put(void)
0x18005bde6  mov     r8, rax; newString
0x18005bde9  mov     rdx, [rbp+57h+string2]; string2
0x18005bded  mov     rcx, [rbp+57h+string1]; string1
0x18005bdf1  call    cs:__imp_WindowsConcatString
0x18005bdf7  mov     ebx, eax
0x18005bdf9  test    eax, eax
0x18005bdfb  jns     short loc_18005BE21
0x18005bdfd  mov     r9d, eax; char *
0x18005be00  mov     edx, 0C6h; void *
0x18005be05  lea     r8, aShellcommonShe; "shellcommon\\shell\\oobe\\core\\compone"...
0x18005be0c  mov     rcx, [rbp+5Fh]; this
0x18005be10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005be15  nop
0x18005be16  lea     rcx, [rbp+57h+string]; this
0x18005be1a  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18005be1f  jmp     short loc_18005BDCB
0x18005be21  xor     edx, edx; length
0x18005be23  mov     rcx, [rbp+57h+string]; string
0x18005be27  call    cs:__imp_WindowsGetStringRawBuffer
0x18005be2d  mov     rdi, rax
0x18005be30  mov     [rbp+57h+var_70], r14d
0x18005be34  lea     rax, [rbp+57h+var_70]
0x18005be38  mov     qword ptr [rsp+0C0h+pcbPackedCredentials], rax; int
0x18005be3d  xor     r9d, r9d; pPackedCredentials
0x18005be40  lea     r8, sourceString; pszPassword
0x18005be47  mov     rdx, rdi; pszUserName
0x18005be4a  xor     ecx, ecx; dwFlags
0x18005be4c  call    cs:__imp_CredPackAuthenticationBufferW
0x18005be52  test    eax, eax
0x18005be54  jz      short loc_18005BE65
0x18005be56  mov     ebx, 8000FFFFh
0x18005be5b  mov     r9d, ebx
0x18005be5e  mov     edx, 0CBh
0x18005be63  jmp     short loc_18005BE05
0x18005be65  call    cs:__imp_GetLastError
0x18005be6b  cmp     eax, 7Ah ; 'z'
0x18005be6e  jz      short loc_18005BE89
0x18005be70  mov     rcx, [rbp+5Fh]; this
0x18005be74  lea     r8, aShellcommonShe; "shellcommon\\shell\\oobe\\core\\compone"...
0x18005be7b  mov     edx, 0CCh; void *
0x18005be80  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005be85  mov     ebx, eax
0x18005be87  jmp     short loc_18005BE16
0x18005be89  mov     [rbp+57h+pPackedCredentials], r14
0x18005be8d  lea     rax, [rbp+57h+pPackedCredentials]
0x18005be91  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x18005be95  mov     r10d, 1
0x18005be9b  mov     byte ptr [rbp+57h+hstringHeader.Reserved+10h], r10b
0x18005be9f  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], r14
0x18005bea3  mov     [rbp+57h+var_68], r14
0x18005bea7  mov     ecx, [rbp+57h+var_70]; unsigned __int64
0x18005beaa  lea     r8, [rbp+57h+var_68]; unsigned __int64 *
0x18005beae  mov     edx, r10d; unsigned __int64
0x18005beb1  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18005beb6  mov     ebx, eax
0x18005beb8  test    eax, eax
0x18005beba  js      short loc_18005BECE
0x18005bebc  lea     r9, [rbp+57h+hstringHeader.Reserved+8]; void **
0x18005bec0  mov     r8, [rbp+57h+var_68]; unsigned __int64
0x18005bec4  mov     edx, r10d; unsigned int
0x18005bec7  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18005becc  mov     ebx, eax
0x18005bece  lea     rcx, [rbp+57h+hstringHeader]
0x18005bed2  call    ??1?$out_param_t@V?$unique_ptr@EUcotaskmem_secure_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::cotaskmem_secure_deleter>>::~out_param_t<wistd::unique_ptr<uchar,wil::cotaskmem_secure_deleter>>(void)
0x18005bed7  test    ebx, ebx
0x18005bed9  jns     short loc_18005BF04
0x18005bedb  mov     rcx, [rbp+5Fh]; this
0x18005bedf  mov     r9d, ebx; char *
0x18005bee2  lea     r8, aShellcommonShe; "shellcommon\\shell\\oobe\\core\\compone"...
0x18005bee9  mov     edx, 0CEh; void *
0x18005beee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005bef3  nop
0x18005bef4  xor     edx, edx
0x18005bef6  lea     rcx, [rbp+57h+pPackedCredentials]
0x18005befa  call    ?reset@?$unique_ptr@EUcotaskmem_secure_deleter@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::cotaskmem_secure_deleter>::reset(uchar *)
0x18005beff  jmp     loc_18005BE16
0x18005bf04  lea     rax, [rbp+57h+var_70]
0x18005bf08  mov     qword ptr [rsp+0C0h+pcbPackedCredentials], rax; int
0x18005bf0d  mov     r9, [rbp+57h+pPackedCredentials]; pPackedCredentials
0x18005bf11  lea     r8, sourceString; pszPassword
0x18005bf18  mov     rdx, rdi; pszUserName
0x18005bf1b  xor     ecx, ecx; dwFlags
0x18005bf1d  call    cs:__imp_CredPackAuthenticationBufferW
0x18005bf23  test    eax, eax
0x18005bf25  jnz     short loc_18005BF40
0x18005bf27  mov     rcx, [rbp+5Fh]; this
0x18005bf2b  lea     r8, aShellcommonShe; "shellcommon\\shell\\oobe\\core\\compone"...
0x18005bf32  mov     edx, 0CFh; void *
0x18005bf37  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005bf3c  mov     ebx, eax
0x18005bf3e  jmp     short loc_18005BEF4
0x18005bf40  mov     [rbp+57h+var_44], r14d
0x18005bf44  mov     [rbp+57h+var_50], r14
0x18005bf48  mov     eax, [rbp+57h+var_70]
0x18005bf4b  mov     [rbp+57h+var_48], eax
0x18005bf4e  mov     rax, [rbp+57h+pPackedCredentials]
0x18005bf52  mov     [rbp+57h+var_40], rax
0x18005bf56  mov     [rbp+57h+var_80], r14
0x18005bf5a  mov     [rbp+57h+var_20], r14
0x18005bf5e  mov     r9d, 2Fh ; '/'; unsigned int
0x18005bf64  lea     r8d, [r9+1]; unsigned int
0x18005bf68  lea     rdx, ?RuntimeClass_Windows_System_Internal_CredentialSerialization@@3QBGB; "Windows.System.Internal.CredentialSeria"...
0x18005bf6f  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18005bf73  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005bf78  nop
0x18005bf79  mov     [rbp+57h+var_80], r14
0x18005bf7d  mov     [rbp+57h+var_68], r14
0x18005bf81  lea     rdx, [rbp+57h+var_68]
0x18005bf85  mov     rcx, [rbp+57h+var_20]
0x18005bf89  call    cs:__imp_RoActivateInstance
0x18005bf8f  mov     ebx, eax
0x18005bf91  test    eax, eax
0x18005bf93  js      short loc_18005BFE9
0x18005bf95  mov     r8d, 10h; Size
0x18005bf9b  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x18005bfa2  lea     rcx, _GUID_c39ab8a5_824f_4acf_92e0_bb53b8a90555; Buf1
0x18005bfa9  call    memcmp_0
0x18005bfae  test    eax, eax
0x18005bfb0  jnz     short loc_18005BFBC
0x18005bfb2  mov     rax, [rbp+57h+var_68]
0x18005bfb6  mov     [rbp+57h+var_80], rax
0x18005bfba  jmp     short loc_18005BFE9
0x18005bfbc  mov     rcx, [rbp+57h+var_68]
0x18005bfc0  mov     rax, [rcx]
0x18005bfc3  lea     r8, [rbp+57h+var_80]
0x18005bfc7  lea     rdx, _GUID_c39ab8a5_824f_4acf_92e0_bb53b8a90555
0x18005bfce  mov     rax, [rax]
0x18005bfd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bfd6  mov     ebx, eax
0x18005bfd8  mov     rcx, [rbp+57h+var_68]
0x18005bfdc  mov     rax, [rcx]
0x18005bfdf  mov     rax, [rax+10h]
0x18005bfe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bfe8  nop
0x18005bfe9  test    ebx, ebx
0x18005bfeb  jns     short loc_18005C014
0x18005bfed  mov     rcx, [rbp+5Fh]; this
0x18005bff1  mov     r9d, ebx; char *
0x18005bff4  lea     r8, aShellcommonShe; "shellcommon\\shell\\oobe\\core\\compone"...
0x18005bffb  mov     edx, 0D9h; void *
0x18005c000  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c005  nop
0x18005c006  lea     rcx, [rbp+57h+var_80]
0x18005c00a  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18005c00f  jmp     loc_18005BEF4
0x18005c014  mov     [rbp+57h+var_60], r14
0x18005c018  mov     rcx, [rbp+57h+var_80]
0x18005c01c  mov     rax, [rcx]
0x18005c01f  lea     r8, [rbp+57h+var_60]
0x18005c023  lea     rdx, _GUID_d67b68f7_dd86_4af5_9046_22bb7b089209
0x18005c02a  mov     rax, [rax]
0x18005c02d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c032  mov     ebx, eax
0x18005c034  test    eax, eax
0x18005c036  jns     short loc_18005C05C
0x18005c038  mov     edx, 0DCh; void *
0x18005c03d  mov     rcx, [rbp+5Fh]; this
0x18005c041  mov     r9d, eax; char *
0x18005c044  lea     r8, aShellcommonShe; "shellcommon\\shell\\oobe\\core\\compone"...
0x18005c04b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c050  nop
0x18005c051  lea     rcx, [rbp+57h+var_60]
0x18005c055  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18005c05a  jmp     short loc_18005C006
0x18005c05c  mov     rcx, [rbp+57h+var_60]
0x18005c060  mov     rax, [rcx]
0x18005c063  lea     rdx, [rbp+57h+var_50]
0x18005c067  mov     rax, [rax+18h]
0x18005c06b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c070  mov     ebx, eax
0x18005c072  test    eax, eax
0x18005c074  jns     short loc_18005C07D
0x18005c076  mov     edx, 0DDh
0x18005c07b  jmp     short loc_18005C03D
0x18005c07d  mov     rax, [rsi]
0x18005c080  mov     rdx, [rbp+57h+var_80]
0x18005c084  mov     rcx, rsi
0x18005c087  mov     rax, [rax+78h]
0x18005c08b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c090  mov     ebx, eax
0x18005c092  test    eax, eax
0x18005c094  jns     short loc_18005C09D
0x18005c096  mov     edx, 0DFh
0x18005c09b  jmp     short loc_18005C03D
0x18005c09d  lea     rcx, [rbp+57h+var_60]
0x18005c0a1  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18005c0a6  nop
0x18005c0a7  lea     rcx, [rbp+57h+var_80]
0x18005c0ab  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18005c0b0  nop
0x18005c0b1  xor     edx, edx
0x18005c0b3  lea     rcx, [rbp+57h+pPackedCredentials]
0x18005c0b7  call    ?reset@?$unique_ptr@EUcotaskmem_secure_deleter@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::cotaskmem_secure_deleter>::reset(uchar *)
0x18005c0bc  nop
0x18005c0bd  lea     rcx, [rbp+57h+string]; this
0x18005c0c1  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18005c0c6  nop
0x18005c0c7  lea     rcx, [rbp+57h+string2]; this
0x18005c0cb  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18005c0d0  mov     ebx, r14d
0x18005c0d3  lea     rcx, [rbp+57h+string1]; this
0x18005c0d7  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18005c0dc  mov     eax, ebx
0x18005c0de  mov     rcx, [rbp+57h+var_18]
0x18005c0e2  xor     rcx, rsp; StackCookie
0x18005c0e5  call    __security_check_cookie
0x18005c0ea  lea     r11, [rsp+0C0h+var_10]
0x18005c0f2  mov     rbx, [r11+30h]
0x18005c0f6  mov     rsi, [r11+38h]
0x18005c0fa  mov     rsp, r11
0x18005c0fd  pop     r14
0x18005c0ff  pop     rdi
0x18005c100  pop     rbp
0x18005c101  retn
```
