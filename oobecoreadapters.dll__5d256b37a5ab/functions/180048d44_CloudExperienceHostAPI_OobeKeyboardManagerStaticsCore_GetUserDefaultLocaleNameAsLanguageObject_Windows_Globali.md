# CloudExperienceHostAPI::OobeKeyboardManagerStaticsCore::GetUserDefaultLocaleNameAsLanguageObject(Windows::Globalization::ILanguage * *)

- ea: `0x180048d44`
- end: `0x180048ec9`
- name: `?GetUserDefaultLocaleNameAsLanguageObject@OobeKeyboardManagerStaticsCore@CloudExperienceHostAPI@@CAJPEAPEAUILanguage@Globalization@Windows@@@Z`
- size: `389`
- prototype: `__int64 __fastcall(struct Windows::Globalization::ILanguage **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180047464`

## callees

- `0x180002b60`
- `0x1800076b4`
- `0x1800076d4`
- `0x180009760`
- `0x1800099bc`
- `0x18000a4f8`
- `0x180048d44`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLocaleName` at `0x180048d79`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLocaleName` at `0x180048d79`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180048dd3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180048dd3`

## string_xrefs

- `0x180048d87`: `shellcommon\shell\oobe\core\components\winrt\oobekeyboardcore.cpp`
- `0x180048de6`: `shellcommon\shell\oobe\core\components\winrt\oobekeyboardcore.cpp`
- `0x180048e69`: `shellcommon\shell\oobe\core\components\winrt\oobekeyboardcore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CloudExperienceHostAPI::OobeKeyboardManagerStaticsCore::GetUserDefaultLocaleNameAsLanguageObject(
        struct Windows::Globalization::ILanguage **a1)
{
  const char *v2; // r9
  int ActivationFactory; // eax
  unsigned int v5; // ebx
  __int64 v6; // rsi
  __int64 (__fastcall *v7)(__int64, __int64, int *); // r14
  __int64 v8; // rbx
  UINT32 v9; // eax
  int v10; // eax
  struct Windows::Globalization::ILanguage *v11; // rax
  int v12[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v13; // [rsp+28h] [rbp-D8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h]
  WCHAR LocaleName[88]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  *a1 = 0;
  if ( !GetUserDefaultLocaleName(LocaleName, 85) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x1B4,
             (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobekeyboardcore.cpp",
             v2);
  v13 = 0;
  v15 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Globalization.Language",
    0x1Fu,
    0x1Eu);
  ActivationFactory = RoGetActivationFactory(v15, &GUID_9b0252ac_0c27_44f8_b792_9793fb66c63e, &v13);
  v5 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    *(_QWORD *)v12 = 0;
    v6 = v13;
    v7 = *(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v13 + 48LL);
    *(_QWORD *)v12 = 0;
    v8 = -1;
    do
      ++v8;
    while ( LocaleName[v8] );
    v15 = 0;
    v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v8);
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, LocaleName, v9, v8);
    v10 = v7(v6, v15, v12);
    v5 = v10;
    if ( v10 >= 0 )
    {
      v11 = *(struct Windows::Globalization::ILanguage **)v12;
      *(_QWORD *)v12 = 0;
      *a1 = v11;
      wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(v12);
      v5 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B8,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobekeyboardcore.cpp",
        (const char *)(unsigned int)v10,
        v12[0]);
      wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(v12);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B6,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobekeyboardcore.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v12[0]);
  }
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v13);
  return v5;
}

```

## disassembly

```asm
0x180048d44  push    rbp
0x180048d46  push    rbx
0x180048d47  push    rsi
0x180048d48  push    rdi
0x180048d49  push    r14
0x180048d4b  push    r15
0x180048d4d  lea     rbp, [rsp-18h]
0x180048d52  sub     rsp, 118h
0x180048d59  mov     rax, cs:__security_cookie
0x180048d60  xor     rax, rsp
0x180048d63  mov     [rbp+40h+var_40], rax
0x180048d67  mov     rdi, rcx
0x180048d6a  xor     r15d, r15d
0x180048d6d  mov     [rcx], r15
0x180048d70  lea     edx, [r15+55h]; cchLocaleName
0x180048d74  lea     rcx, [rsp+140h+LocaleName]; lpLocaleName
0x180048d79  call    cs:__imp_GetUserDefaultLocaleName
0x180048d7f  test    eax, eax
0x180048d81  jnz     short loc_180048D9D
0x180048d83  mov     rcx, [rbp+48h]; this
0x180048d87  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\oobe\\core\\compone"...
0x180048d8e  mov     edx, 1B4h; void *
0x180048d93  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180048d98  jmp     loc_180048EAD
0x180048d9d  mov     [rsp+140h+var_118], r15
0x180048da2  mov     [rsp+140h+var_F8], r15
0x180048da7  mov     r9d, 1Eh; unsigned int
0x180048dad  lea     r8d, [r9+1]; unsigned int
0x180048db1  lea     rdx, ?RuntimeClass_Windows_Globalization_Language@@3QBGB; "Windows.Globalization.Language"
0x180048db8  lea     rcx, [rsp+140h+hstringHeader]; hstringHeader
0x180048dbd  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180048dc2  lea     r8, [rsp+140h+var_118]
0x180048dc7  lea     rdx, _GUID_9b0252ac_0c27_44f8_b792_9793fb66c63e
0x180048dce  mov     rcx, [rsp+140h+var_F8]
0x180048dd3  call    cs:__imp_RoGetActivationFactory
0x180048dd9  mov     ebx, eax
0x180048ddb  test    eax, eax
0x180048ddd  jns     short loc_180048DFC
0x180048ddf  mov     rcx, [rbp+48h]; this
0x180048de3  mov     r9d, eax; char *
0x180048de6  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\oobe\\core\\compone"...
0x180048ded  mov     edx, 1B6h; void *
0x180048df2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048df7  jmp     loc_180048EA1
0x180048dfc  mov     qword ptr [rsp+140h+var_120], r15
0x180048e01  mov     rsi, [rsp+140h+var_118]
0x180048e06  mov     rax, [rsi]
0x180048e09  mov     r14, [rax+30h]
0x180048e0d  mov     qword ptr [rsp+140h+var_120], r15; int
0x180048e12  lea     rax, [rsp+140h+LocaleName]
0x180048e17  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180048e1b  inc     rbx
0x180048e1e  cmp     [rax+rbx*2], r15w
0x180048e23  jnz     short loc_180048E1B
0x180048e25  mov     [rsp+140h+var_F8], r15
0x180048e2a  mov     ecx, ebx; unsigned int
0x180048e2c  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180048e31  mov     r9d, ebx; unsigned int
0x180048e34  mov     r8d, eax; unsigned int
0x180048e37  lea     rdx, [rsp+140h+LocaleName]; sourceString
0x180048e3c  lea     rcx, [rsp+140h+hstringHeader]; hstringHeader
0x180048e41  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180048e46  nop
0x180048e47  lea     r8, [rsp+140h+var_120]
0x180048e4c  mov     rdx, [rsp+140h+var_F8]
0x180048e51  mov     rcx, rsi
0x180048e54  mov     rax, r14
0x180048e57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048e5c  mov     ebx, eax
0x180048e5e  test    eax, eax
0x180048e60  jns     short loc_180048E87
0x180048e62  mov     rcx, [rbp+48h]; this
0x180048e66  mov     r9d, eax; char *
0x180048e69  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\oobe\\core\\compone"...
0x180048e70  mov     edx, 1B8h; void *
0x180048e75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048e7a  nop
0x180048e7b  lea     rcx, [rsp+140h+var_120]
0x180048e80  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180048e85  jmp     short loc_180048EA1
0x180048e87  mov     rax, qword ptr [rsp+140h+var_120]
0x180048e8c  mov     qword ptr [rsp+140h+var_120], r15
0x180048e91  mov     [rdi], rax
0x180048e94  lea     rcx, [rsp+140h+var_120]
0x180048e99  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180048e9e  mov     ebx, r15d
0x180048ea1  lea     rcx, [rsp+140h+var_118]
0x180048ea6  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180048eab  mov     eax, ebx
0x180048ead  mov     rcx, [rbp+40h+var_40]
0x180048eb1  xor     rcx, rsp; StackCookie
0x180048eb4  call    __security_check_cookie
0x180048eb9  add     rsp, 118h
0x180048ec0  pop     r15
0x180048ec2  pop     r14
0x180048ec4  pop     rdi
0x180048ec5  pop     rsi
0x180048ec6  pop     rbx
0x180048ec7  pop     rbp
0x180048ec8  retn
```
