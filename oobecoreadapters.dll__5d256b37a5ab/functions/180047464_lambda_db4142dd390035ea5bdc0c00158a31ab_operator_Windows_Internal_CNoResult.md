# _lambda_db4142dd390035ea5bdc0c00158a31ab_::operator()(Windows::Internal::CNoResult &)

- ea: `0x180047464`
- end: `0x180047858`
- name: `??R_lambda_db4142dd390035ea5bdc0c00158a31ab_@@QEBAJAEAVCNoResult@Internal@Windows@@@Z`
- size: `1012`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800493b0`

## callees

- `0x180002b60`
- `0x1800076d4`
- `0x180009760`
- `0x18000a4f8`
- `0x18000b098`
- `0x180045a60`
- `0x180046e48`
- `0x180047464`
- `0x180048d44`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047663`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800476b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047663`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800476b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004769e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004769e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800474d4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800474d4`

## string_xrefs

- `0x180047529`: `shellcommon\shell\oobe\core\components\winrt\oobekeyboardcore.cpp`
- `0x18004756c`: `shellcommon\shell\oobe\core\components\winrt\oobekeyboardcore.cpp`
- `0x1800475c1`: `shellcommon\shell\oobe\core\components\winrt\oobekeyboardcore.cpp`
- `0x180047687`: `shellcommon\shell\oobe\core\components\winrt\oobekeyboardcore.cpp`
- `0x1800476dc`: `shellcommon\shell\oobe\core\components\winrt\oobekeyboardcore.cpp`
- `0x180047755`: `shellcommon\shell\oobe\core\components\winrt\oobekeyboardcore.cpp`
- `0x1800477c7`: `shellcommon\shell\oobe\core\components\winrt\oobekeyboardcore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall _lambda_db4142dd390035ea5bdc0c00158a31ab_::operator()(__int64 **a1)
{
  int ActivationFactory; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // rbx
  __int64 (__fastcall *v6)(__int64, __int64 **); // rdi
  __int64 *v7; // rcx
  int UserDefaultLocaleNameAsLanguageObject; // eax
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // rdx
  unsigned int i; // esi
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HSTRING *); // rbx
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 *v21; // rcx
  __int64 v22; // rax
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rdx
  __int64 *v29; // [rsp+20h] [rbp-59h] BYREF
  struct Windows::Globalization::ILanguage *v30; // [rsp+28h] [rbp-51h] BYREF
  __int64 *v31; // [rsp+30h] [rbp-49h] BYREF
  __int64 *v32; // [rsp+38h] [rbp-41h] BYREF
  __int64 v33; // [rsp+40h] [rbp-39h] BYREF
  __int64 v34; // [rsp+48h] [rbp-31h] BYREF
  unsigned int v35; // [rsp+50h] [rbp-29h] BYREF
  int v36; // [rsp+54h] [rbp-25h] BYREF
  HSTRING string; // [rsp+58h] [rbp-21h] BYREF
  __int64 v38; // [rsp+60h] [rbp-19h] BYREF
  PCWSTR StringRawBuffer; // [rsp+68h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-9h] BYREF
  __int64 v41; // [rsp+88h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  wil::com_ptr_t<Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager,wil::err_exception_policy>::com_ptr_t<Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager,wil::err_exception_policy>(
    &v32,
    a1 + 1);
  if ( v32 )
    goto LABEL_10;
  v38 = 0;
  v41 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.UI.Internal.Text.Core.CoreKeyboardInputProfileManager",
    0x3Eu,
    0x3Du);
  ActivationFactory = RoGetActivationFactory(v41, &GUID_d0380bbe_201e_4a70_8eff_bb52f7996cae, &v38);
  v3 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v5 = v38;
    v6 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v38 + 48LL);
    v7 = v32;
    v32 = 0;
    if ( v7 )
      (*(void (__fastcall **)(__int64 *))(*v7 + 16))(v7);
    ActivationFactory = v6(v5, &v32);
    v3 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      v4 = 378;
      goto LABEL_8;
    }
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v38);
LABEL_10:
    v30 = 0;
    UserDefaultLocaleNameAsLanguageObject = CloudExperienceHostAPI::OobeKeyboardManagerStaticsCore::GetUserDefaultLocaleNameAsLanguageObject(&v30);
    v3 = UserDefaultLocaleNameAsLanguageObject;
    if ( UserDefaultLocaleNameAsLanguageObject < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17F,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobekeyboardcore.cpp",
        (const char *)(unsigned int)UserDefaultLocaleNameAsLanguageObject,
        (int)v29);
LABEL_12:
      wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v30);
      goto LABEL_45;
    }
    v29 = 0;
    v9 = *v32;
    v29 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64 *, struct Windows::Globalization::ILanguage *, __int64 **))(v9 + 128))(
            v32,
            v30,
            &v29);
    v3 = v10;
    if ( v10 < 0 )
    {
      v11 = 385;
LABEL_15:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobekeyboardcore.cpp",
        (const char *)(unsigned int)v10,
        (int)v29);
LABEL_16:
      wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v29);
      goto LABEL_12;
    }
    v35 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v29 + 56))(v29, &v35);
    v3 = v10;
    if ( v10 < 0 )
    {
      v11 = 389;
      goto LABEL_15;
    }
    for ( i = 0; i < v35; ++i )
    {
      v33 = 0;
      v13 = *v29;
      v33 = 0;
      v14 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v13 + 48))(v29, i, &v33);
      v3 = v14;
      if ( v14 < 0 )
      {
        v20 = 393;
        goto LABEL_28;
      }
      v14 = (*(__int64 (__fastcall **)(__int64 *, __int64))(**a1 + 104))(*a1, v33);
      v3 = v14;
      if ( v14 < 0 )
      {
        v20 = 394;
LABEL_28:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v20,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobekeyboardcore.cpp",
          (const char *)(unsigned int)v14,
          (int)v29);
        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v33);
        goto LABEL_16;
      }
      string = 0;
      v15 = v33;
      v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v33 + 192LL);
      WindowsDeleteString(0);
      string = 0;
      v17 = v16(v15, &string);
      if ( v17 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x18D,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobekeyboardcore.cpp",
          (const char *)(unsigned int)v17,
          (int)v29);
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      CloudExperienceHostCoreTelemetry::CoreEvent2<char const (&)[133],unsigned short const (&)[43],unsigned short const *>(
        v19,
        v18,
        &StringRawBuffer);
      WindowsDeleteString(string);
      string = 0;
      wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v33);
    }
    v36 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64 *, int *))(**a1 + 56))(*a1, &v36);
    v3 = v10;
    if ( v10 < 0 )
    {
      v11 = 403;
      goto LABEL_15;
    }
    if ( v36 )
    {
      v31 = 0;
      v21 = *a1;
      v22 = **a1;
      v31 = 0;
      v23 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v22 + 64))(v21, &v31);
      v3 = v23;
      if ( v23 < 0 )
      {
        v24 = 411;
LABEL_34:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v24,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobekeyboardcore.cpp",
          (const char *)(unsigned int)v23,
          (int)v29);
LABEL_35:
        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v31);
        goto LABEL_16;
      }
      v23 = (*(__int64 (__fastcall **)(__int64 *, __int64 *, __int64))(*v32 + 112))(v32, v31, 64);
      v3 = v23;
      if ( v23 < 0 )
      {
        v24 = 412;
        goto LABEL_34;
      }
      v34 = 0;
      v25 = *v31;
      v34 = 0;
      v26 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v25 + 48))(v31, 0, &v34);
      v3 = v26;
      if ( v26 < 0 )
      {
        v27 = 416;
LABEL_40:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v27,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobekeyboardcore.cpp",
          (const char *)(unsigned int)v26,
          (int)v29);
        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v34);
        goto LABEL_35;
      }
      v26 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v32 + 104))(v32, v34);
      v3 = v26;
      if ( v26 < 0 )
      {
        v27 = 417;
        goto LABEL_40;
      }
      wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v34);
      wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v31);
    }
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v29);
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v30);
    v3 = 0;
    goto LABEL_45;
  }
  v4 = 377;
LABEL_8:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobekeyboardcore.cpp",
    (const char *)(unsigned int)ActivationFactory,
    (int)v29);
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v38);
LABEL_45:
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v32);
  return v3;
}

```

## disassembly

```asm
0x180047464  push    rbp
0x180047466  push    rbx
0x180047467  push    rsi
0x180047468  push    rdi
0x180047469  push    r14
0x18004746b  push    r15
0x18004746d  lea     rbp, [rsp-2Fh]
0x180047472  sub     rsp, 0A8h
0x180047479  mov     rax, cs:__security_cookie
0x180047480  xor     rax, rsp
0x180047483  mov     [rbp+57h+var_40], rax
0x180047487  mov     r14, rcx
0x18004748a  lea     rdx, [rcx+8]
0x18004748e  lea     rcx, [rbp+57h+var_98]
0x180047492  call    ??0?$com_ptr_t@UICoreKeyboardInputProfileManager@Core@Text@Internal@UI@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager,wil::err_exception_policy>::com_ptr_t<Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager,wil::err_exception_policy>(wil::com_ptr_t<Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager,wil::err_exception_policy> const &)
0x180047497  nop
0x180047498  xor     r15d, r15d
0x18004749b  cmp     [rbp+57h+var_98], r15
0x18004749f  jnz     loc_180047552
0x1800474a5  mov     [rbp+57h+var_70], r15
0x1800474a9  mov     [rbp+57h+var_48], r15
0x1800474ad  lea     r9d, [r15+3Dh]; unsigned int
0x1800474b1  lea     r8d, [r15+3Eh]; unsigned int
0x1800474b5  lea     rdx, ?RuntimeClass_Windows_UI_Internal_Text_Core_CoreKeyboardInputProfileManager@@3QBGB; "Windows.UI.Internal.Text.Core.CoreKeybo"...
0x1800474bc  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800474c0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800474c5  lea     r8, [rbp+57h+var_70]
0x1800474c9  lea     rdx, _GUID_d0380bbe_201e_4a70_8eff_bb52f7996cae
0x1800474d0  mov     rcx, [rbp+57h+var_48]
0x1800474d4  call    cs:__imp_RoGetActivationFactory
0x1800474da  mov     ebx, eax
0x1800474dc  test    eax, eax
0x1800474de  jns     short loc_1800474E7
0x1800474e0  mov     edx, 179h
0x1800474e5  jmp     short loc_180047526
0x1800474e7  mov     rbx, [rbp+57h+var_70]
0x1800474eb  mov     rax, [rbx]
0x1800474ee  mov     rdi, [rax+30h]
0x1800474f2  mov     rcx, [rbp+57h+var_98]
0x1800474f6  mov     [rbp+57h+var_98], r15
0x1800474fa  test    rcx, rcx
0x1800474fd  jz      short loc_18004750C
0x1800474ff  mov     rdx, [rcx]
0x180047502  mov     rax, [rdx+10h]
0x180047506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004750b  nop
0x18004750c  lea     rdx, [rbp+57h+var_98]
0x180047510  mov     rcx, rbx
0x180047513  mov     rax, rdi
0x180047516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004751b  mov     ebx, eax
0x18004751d  test    eax, eax
0x18004751f  jns     short loc_180047548
0x180047521  mov     edx, 17Ah; void *
0x180047526  mov     r9d, eax; char *
0x180047529  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\oobe\\core\\compone"...
0x180047530  mov     rcx, [rbp+5Fh]; this
0x180047534  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047539  nop
0x18004753a  lea     rcx, [rbp+57h+var_70]
0x18004753e  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180047543  jmp     loc_180047831
0x180047548  lea     rcx, [rbp+57h+var_70]
0x18004754c  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180047551  nop
0x180047552  mov     [rbp+57h+var_A8], r15
0x180047556  lea     rcx, [rbp+57h+var_A8]; struct Windows::Globalization::ILanguage **
0x18004755a  call    ?GetUserDefaultLocaleNameAsLanguageObject@OobeKeyboardManagerStaticsCore@CloudExperienceHostAPI@@CAJPEAPEAUILanguage@Globalization@Windows@@@Z; CloudExperienceHostAPI::OobeKeyboardManagerStaticsCore::GetUserDefaultLocaleNameAsLanguageObject(Windows::Globalization::ILanguage * *)
0x18004755f  mov     ebx, eax
0x180047561  test    eax, eax
0x180047563  jns     short loc_18004758C
0x180047565  mov     rcx, [rbp+5Fh]; this
0x180047569  mov     r9d, eax; char *
0x18004756c  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\oobe\\core\\compone"...
0x180047573  mov     edx, 17Fh; void *
0x180047578  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004757d  nop
0x18004757e  lea     rcx, [rbp+57h+var_A8]
0x180047582  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180047587  jmp     loc_180047831
0x18004758c  mov     [rbp+57h+var_B0], r15
0x180047590  mov     rcx, [rbp+57h+var_98]
0x180047594  mov     rax, [rcx]
0x180047597  mov     [rbp+57h+var_B0], r15
0x18004759b  lea     r8, [rbp+57h+var_B0]
0x18004759f  mov     rdx, [rbp+57h+var_A8]
0x1800475a3  mov     rax, [rax+80h]
0x1800475aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800475af  mov     ebx, eax
0x1800475b1  test    eax, eax
0x1800475b3  jns     short loc_1800475D9
0x1800475b5  mov     edx, 181h; void *
0x1800475ba  mov     rcx, [rbp+5Fh]; this
0x1800475be  mov     r9d, eax; char *
0x1800475c1  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\oobe\\core\\compone"...
0x1800475c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800475cd  nop
0x1800475ce  lea     rcx, [rbp+57h+var_B0]
0x1800475d2  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x1800475d7  jmp     short loc_18004757E
0x1800475d9  mov     [rbp+57h+var_80], r15d
0x1800475dd  mov     rcx, [rbp+57h+var_B0]
0x1800475e1  mov     rax, [rcx]
0x1800475e4  lea     rdx, [rbp+57h+var_80]
0x1800475e8  mov     rax, [rax+38h]
0x1800475ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800475f1  mov     ebx, eax
0x1800475f3  test    eax, eax
0x1800475f5  jns     short loc_1800475FE
0x1800475f7  mov     edx, 185h
0x1800475fc  jmp     short loc_1800475BA
0x1800475fe  mov     esi, r15d
0x180047601  cmp     esi, [rbp+57h+var_80]
0x180047604  jnb     loc_1800476FE
0x18004760a  mov     [rbp+57h+var_90], r15
0x18004760e  mov     rcx, [rbp+57h+var_B0]
0x180047612  mov     rax, [rcx]
0x180047615  mov     [rbp+57h+var_90], r15
0x180047619  lea     r8, [rbp+57h+var_90]
0x18004761d  mov     edx, esi
0x18004761f  mov     rax, [rax+30h]
0x180047623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047628  mov     ebx, eax
0x18004762a  test    eax, eax
0x18004762c  js      loc_1800476D7
0x180047632  mov     rcx, [r14]
0x180047635  mov     rax, [rcx]
0x180047638  mov     rdx, [rbp+57h+var_90]
0x18004763c  mov     rax, [rax+68h]
0x180047640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047645  mov     ebx, eax
0x180047647  test    eax, eax
0x180047649  js      loc_1800476D0
0x18004764f  mov     [rbp+57h+string], r15
0x180047653  mov     rdi, [rbp+57h+var_90]
0x180047657  mov     rax, [rdi]
0x18004765a  mov     rbx, [rax+0C0h]
0x180047661  xor     ecx, ecx; string
0x180047663  call    cs:__imp_WindowsDeleteString
0x180047669  mov     [rbp+57h+string], r15
0x18004766d  lea     rdx, [rbp+57h+string]
0x180047671  mov     rcx, rdi
0x180047674  mov     rax, rbx
0x180047677  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004767c  mov     rcx, [rbp+5Fh]; this
0x180047680  test    eax, eax
0x180047682  jns     short loc_180047698
0x180047684  mov     r9d, eax; char *
0x180047687  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\oobe\\core\\compone"...
0x18004768e  mov     edx, 18Dh; void *
0x180047693  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180047698  xor     edx, edx; length
0x18004769a  mov     rcx, [rbp+57h+string]; string
0x18004769e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800476a4  mov     [rbp+57h+var_68], rax
0x1800476a8  lea     r8, [rbp+57h+var_68]
0x1800476ac  call    ??$CoreEvent2@AEAY0IF@$$CBDAEAY0CL@$$CBGPEBG@CloudExperienceHostCoreTelemetry@@SAXAEAY0IF@$$CBDAEAY0CL@$$CBG$$QEAPEBG@Z; CloudExperienceHostCoreTelemetry::CoreEvent2<char const (&)[133],ushort const (&)[43],ushort const *>(char const (&)[133],ushort const (&)[43],ushort const * &&)
0x1800476b1  nop
0x1800476b2  mov     rcx, [rbp+57h+string]; string
0x1800476b6  call    cs:__imp_WindowsDeleteString
0x1800476bc  mov     [rbp+57h+string], r15
0x1800476c0  lea     rcx, [rbp+57h+var_90]
0x1800476c4  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x1800476c9  inc     esi
0x1800476cb  jmp     loc_180047601
0x1800476d0  mov     edx, 18Ah
0x1800476d5  jmp     short loc_1800476DC
0x1800476d7  mov     edx, 189h; void *
0x1800476dc  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\oobe\\core\\compone"...
0x1800476e3  mov     r9d, eax; char *
0x1800476e6  mov     rcx, [rbp+5Fh]; this
0x1800476ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800476ef  nop
0x1800476f0  lea     rcx, [rbp+57h+var_90]
0x1800476f4  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x1800476f9  jmp     loc_1800475CE
0x1800476fe  mov     [rbp+57h+var_7C], r15d
0x180047702  mov     rcx, [r14]
0x180047705  mov     rax, [rcx]
0x180047708  lea     rdx, [rbp+57h+var_7C]
0x18004770c  mov     rax, [rax+38h]
0x180047710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047715  mov     ebx, eax
0x180047717  test    eax, eax
0x180047719  jns     short loc_180047725
0x18004771b  mov     edx, 193h
0x180047720  jmp     loc_1800475BA
0x180047725  cmp     [rbp+57h+var_7C], r15d
0x180047729  jz      loc_18004781B
0x18004772f  mov     [rbp+57h+var_A0], r15
0x180047733  mov     rcx, [r14]
0x180047736  mov     rax, [rcx]
0x180047739  mov     [rbp+57h+var_A0], r15
0x18004773d  lea     rdx, [rbp+57h+var_A0]
0x180047741  mov     rax, [rax+40h]
0x180047745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004774a  mov     ebx, eax
0x18004774c  test    eax, eax
0x18004774e  jns     short loc_180047777
0x180047750  mov     edx, 19Bh; void *
0x180047755  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\oobe\\core\\compone"...
0x18004775c  mov     r9d, eax; char *
0x18004775f  mov     rcx, [rbp+5Fh]; this
0x180047763  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047768  nop
0x180047769  lea     rcx, [rbp+57h+var_A0]
0x18004776d  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180047772  jmp     loc_1800475CE
0x180047777  mov     rcx, [rbp+57h+var_98]
0x18004777b  mov     rax, [rcx]
0x18004777e  mov     r8d, 40h ; '@'
0x180047784  mov     rdx, [rbp+57h+var_A0]
0x180047788  mov     rax, [rax+70h]
0x18004778c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047791  mov     ebx, eax
0x180047793  test    eax, eax
0x180047795  jns     short loc_18004779E
0x180047797  mov     edx, 19Ch
0x18004779c  jmp     short loc_180047755
0x18004779e  mov     [rbp+57h+var_88], r15
0x1800477a2  mov     rcx, [rbp+57h+var_A0]
0x1800477a6  mov     rax, [rcx]
0x1800477a9  mov     [rbp+57h+var_88], r15
0x1800477ad  lea     r8, [rbp+57h+var_88]
0x1800477b1  xor     edx, edx
0x1800477b3  mov     rax, [rax+30h]
0x1800477b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800477bc  mov     ebx, eax
0x1800477be  test    eax, eax
0x1800477c0  jns     short loc_1800477E6
0x1800477c2  mov     edx, 1A0h; void *
0x1800477c7  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\oobe\\core\\compone"...
0x1800477ce  mov     r9d, eax; char *
0x1800477d1  mov     rcx, [rbp+5Fh]; this
0x1800477d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800477da  nop
0x1800477db  lea     rcx, [rbp+57h+var_88]
0x1800477df  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x1800477e4  jmp     short loc_180047769
0x1800477e6  mov     rcx, [rbp+57h+var_98]
0x1800477ea  mov     rax, [rcx]
0x1800477ed  mov     rdx, [rbp+57h+var_88]
0x1800477f1  mov     rax, [rax+68h]
0x1800477f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800477fa  mov     ebx, eax
0x1800477fc  test    eax, eax
0x1800477fe  jns     short loc_180047807
0x180047800  mov     edx, 1A1h
0x180047805  jmp     short loc_1800477C7
0x180047807  lea     rcx, [rbp+57h+var_88]
0x18004780b  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180047810  nop
0x180047811  lea     rcx, [rbp+57h+var_A0]
0x180047815  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18004781a  nop
0x18004781b  lea     rcx, [rbp+57h+var_B0]
0x18004781f  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180047824  nop
0x180047825  lea     rcx, [rbp+57h+var_A8]
0x180047829  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18004782e  mov     ebx, r15d
0x180047831  lea     rcx, [rbp+57h+var_98]
0x180047835  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18004783a  mov     eax, ebx
0x18004783c  mov     rcx, [rbp+57h+var_40]
0x180047840  xor     rcx, rsp; StackCookie
0x180047843  call    __security_check_cookie
0x180047848  add     rsp, 0A8h
0x18004784f  pop     r15
0x180047851  pop     r14
0x180047853  pop     rdi
0x180047854  pop     rsi
0x180047855  pop     rbx
0x180047856  pop     rbp
0x180047857  retn
```
