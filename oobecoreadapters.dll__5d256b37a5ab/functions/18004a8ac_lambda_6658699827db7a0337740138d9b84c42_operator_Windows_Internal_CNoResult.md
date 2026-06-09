# _lambda_6658699827db7a0337740138d9b84c42_::operator()(Windows::Internal::CNoResult &)

- ea: `0x18004a8ac`
- end: `0x18004ac1a`
- name: `??R_lambda_6658699827db7a0337740138d9b84c42_@@QEBAJAEAVCNoResult@Internal@Windows@@@Z`
- size: `878`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18004b480`

## callees

- `0x180002b60`
- `0x1800076b4`
- `0x1800076d4`
- `0x180009760`
- `0x180009814`
- `0x18000a4f8`
- `0x18000b200`
- `0x1800190d8`
- `0x1800388b0`
- `0x180045f2c`
- `0x18004a0cc`
- `0x18004a8ac`
- `0x18004b1e8`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a927`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004abf1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a927`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004abf1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004a8ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004a97e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004a98d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004a8ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004a97e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004a98d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004ab1f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004ab1f`
- `api-ms-win-core-localization-l1-2-3!SetUserGeoName` at `0x18004a8dc`
- `WinLangdb!SetUserLanguagesCore` at `0x18004a9ec`
- `WinLangdb!SetUserLanguagesCore` at `0x18004a9ec`
- `WinLangdb!GetLocaleFromLanguageAndRegion` at `0x18004a9a3`
- `WinLangdb!GetLocaleFromLanguageAndRegion` at `0x18004a9a3`
- `api-ms-win-core-localization-private-l1-1-0!NlsUpdateLocale` at `0x18004aa09`

## string_xrefs

- `0x18004a907`: `shellcommon\shell\oobe\core\components\winrt\ooberegioncore.cpp`
- `0x18004a94b`: `shellcommon\shell\oobe\core\components\winrt\ooberegioncore.cpp`
- `0x18004a9b4`: `shellcommon\shell\oobe\core\components\winrt\ooberegioncore.cpp`
- `0x18004aa2a`: `shellcommon\shell\oobe\core\components\winrt\ooberegioncore.cpp`
- `0x18004aa5d`: `shellcommon\shell\oobe\core\components\winrt\ooberegioncore.cpp`
- `0x18004aaae`: `shellcommon\shell\oobe\core\components\winrt\ooberegioncore.cpp`
- `0x18004ab32`: `shellcommon\shell\oobe\core\components\winrt\ooberegioncore.cpp`
- `0x18004ab85`: `shellcommon\shell\oobe\core\components\winrt\ooberegioncore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall _lambda_6658699827db7a0337740138d9b84c42_::operator()(_QWORD *a1)
{
  unsigned int (__fastcall *v2)(PCWSTR); // rbx
  PCWSTR StringRawBuffer; // rax
  const char *v4; // r9
  int LocaleNameFromDisplayLanguage; // eax
  unsigned int v7; // ebx
  PCWSTR v8; // rbx
  PCWSTR v9; // rax
  int LocaleFromLanguageAndRegion; // eax
  __int64 v11; // rdx
  __int64 (__fastcall *v12)(unsigned __int16 *, __int64); // rax
  unsigned int v13; // eax
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rax
  int v17; // eax
  __int64 *v18; // rcx
  int ActivationFactory; // eax
  __int64 v20; // rax
  int v21; // eax
  __int64 v22; // rdx
  unsigned __int16 *v23; // [rsp+20h] [rbp-60h] BYREF
  __int64 *v24; // [rsp+28h] [rbp-58h] BYREF
  __int64 v25; // [rsp+30h] [rbp-50h] BYREF
  __int64 *v26; // [rsp+38h] [rbp-48h] BYREF
  __int64 v27; // [rsp+40h] [rbp-40h] BYREF
  HSTRING string; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  __int64 v30; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  v2 = *(unsigned int (__fastcall **)(PCWSTR))(*a1 + 104LL);
  if ( !v2 )
    v2 = (unsigned int (__fastcall *)(PCWSTR))SetUserGeoName;
  StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(a1[1] + 8LL), 0);
  if ( !v2(StringRawBuffer) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x94,
             (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\ooberegioncore.cpp",
             v4);
  WindowsDeleteString(0);
  string = 0;
  LocaleNameFromDisplayLanguage = CloudExperienceHostAPI::OobeRegionManagerStaticsCore::GetLocaleNameFromDisplayLanguage(&string);
  v7 = LocaleNameFromDisplayLanguage;
  if ( LocaleNameFromDisplayLanguage >= 0 )
  {
    v23 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v23,
      0);
    v8 = WindowsGetStringRawBuffer(*(HSTRING *)(a1[1] + 8LL), 0);
    v9 = WindowsGetStringRawBuffer(string, 0);
    LocaleFromLanguageAndRegion = GetLocaleFromLanguageAndRegion(v9, v8, 13, &v23);
    v7 = LocaleFromLanguageAndRegion;
    if ( LocaleFromLanguageAndRegion < 0 )
    {
      v11 = 161;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\ooberegioncore.cpp",
        (const char *)(unsigned int)LocaleFromLanguageAndRegion,
        (int)v23);
LABEL_10:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v23);
      goto LABEL_36;
    }
    Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)&hstringHeader, v23);
    LocaleFromLanguageAndRegion = SetUserLanguagesCore(59, hstringHeader.Reserved.Reserved1);
    v7 = LocaleFromLanguageAndRegion;
    if ( LocaleFromLanguageAndRegion < 0 )
    {
      v11 = 162;
      goto LABEL_9;
    }
    v12 = *(__int64 (__fastcall **)(unsigned __int16 *, __int64))(*a1 + 96LL);
    if ( !v12 )
      v12 = (__int64 (__fastcall *)(unsigned __int16 *, __int64))NlsUpdateLocale;
    v13 = v12(v23, 1);
    if ( v13 )
    {
      v7 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xAA,
             (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\ooberegioncore.cpp",
             (const char *)v13,
             (unsigned int)v23);
      goto LABEL_10;
    }
    v26 = 0;
    v15 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<CloudExperienceHostAPI::IOobeKeyboard,Windows::Foundation::Collections::Internal::Vector<CloudExperienceHostAPI::IOobeKeyboard *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<CloudExperienceHostAPI::IOobeKeyboard *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<CloudExperienceHostAPI::IOobeKeyboard *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<CloudExperienceHostAPI::IOobeKeyboard *>>>(
            v14,
            &v26);
    v7 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAF,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\ooberegioncore.cpp",
        (const char *)(unsigned int)v15,
        (int)v23);
LABEL_19:
      wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v26);
      goto LABEL_10;
    }
    v25 = 0;
    v16 = *v26;
    v25 = 0;
    v17 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v16 + 64))(v26, &v25);
    v7 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB1,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\ooberegioncore.cpp",
        (const char *)(unsigned int)v17,
        (int)v23);
LABEL_22:
      wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v25);
      goto LABEL_19;
    }
    v18 = *(__int64 **)(*a1 + 120LL);
    v24 = v18;
    if ( v18 )
    {
      (*(void (__fastcall **)(__int64 *))(*v18 + 8))(v18);
      v18 = v24;
    }
    if ( !v18 )
    {
      v24 = 0;
      v30 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"CloudExperienceHostAPI.OobeKeyboardManagerStaticsCore",
        0x36u,
        0x35u);
      ActivationFactory = RoGetActivationFactory(v30, &GUID_be66109f_b9c6_4f48_b468_bbd48819ac4b, &v24);
      v7 = ActivationFactory;
      if ( ActivationFactory < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB6,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\ooberegioncore.cpp",
          (const char *)(unsigned int)ActivationFactory,
          (int)v23);
LABEL_28:
        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v24);
        goto LABEL_22;
      }
      v18 = v24;
    }
    v27 = 0;
    v20 = *v18;
    v27 = 0;
    v21 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v20 + 56))(v18, v25, &v27);
    v7 = v21;
    if ( v21 >= 0 )
    {
      v21 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(v27);
      v7 = v21;
      if ( v21 >= 0 )
      {
        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v27);
        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v24);
        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v25);
        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v26);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v23);
        v7 = 0;
        goto LABEL_36;
      }
      v22 = 188;
    }
    else
    {
      v22 = 186;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\ooberegioncore.cpp",
      (const char *)(unsigned int)v21,
      (int)v23);
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v27);
    goto LABEL_28;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x97,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\ooberegioncore.cpp",
    (const char *)(unsigned int)LocaleNameFromDisplayLanguage,
    (int)v23);
LABEL_36:
  WindowsDeleteString(string);
  return v7;
}

```

## disassembly

```asm
0x18004a8ac  mov     [rsp-8+arg_8], rbx
0x18004a8b1  mov     [rsp-8+arg_10], rdi
0x18004a8b6  push    rbp
0x18004a8b7  mov     rbp, rsp
0x18004a8ba  sub     rsp, 80h
0x18004a8c1  mov     rax, cs:__security_cookie
0x18004a8c8  xor     rax, rsp
0x18004a8cb  mov     [rbp+var_10], rax
0x18004a8cf  mov     rdi, rcx
0x18004a8d2  mov     rax, [rcx]
0x18004a8d5  mov     rbx, [rax+68h]
0x18004a8d9  test    rbx, rbx
0x18004a8dc  cmovz   rbx, cs:__imp_SetUserGeoName
0x18004a8e4  mov     rcx, [rcx+8]
0x18004a8e8  xor     edx, edx; length
0x18004a8ea  mov     rcx, [rcx+8]; string
0x18004a8ee  call    cs:__imp_WindowsGetStringRawBuffer
0x18004a8f4  mov     rcx, rax
0x18004a8f7  mov     rax, rbx
0x18004a8fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a8ff  test    eax, eax
0x18004a901  jnz     short loc_18004A91D
0x18004a903  mov     rcx, [rbp+8]; this
0x18004a907  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\oobe\\core\\compone"...
0x18004a90e  mov     edx, 94h; void *
0x18004a913  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004a918  jmp     loc_18004ABF9
0x18004a91d  mov     [rbp+string], 0
0x18004a925  xor     ecx, ecx; string
0x18004a927  call    cs:__imp_WindowsDeleteString
0x18004a92d  mov     [rbp+string], 0
0x18004a935  lea     rcx, [rbp+string]; string
0x18004a939  call    ?GetLocaleNameFromDisplayLanguage@OobeRegionManagerStaticsCore@CloudExperienceHostAPI@@CAJPEAPEAUHSTRING__@@@Z; CloudExperienceHostAPI::OobeRegionManagerStaticsCore::GetLocaleNameFromDisplayLanguage(HSTRING__ * *)
0x18004a93e  mov     ebx, eax
0x18004a940  test    eax, eax
0x18004a942  jns     short loc_18004A961
0x18004a944  mov     rcx, [rbp+8]; this
0x18004a948  mov     r9d, eax; char *
0x18004a94b  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\oobe\\core\\compone"...
0x18004a952  mov     edx, 97h; void *
0x18004a957  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a95c  jmp     loc_18004ABED
0x18004a961  mov     [rbp+var_60], 0
0x18004a969  xor     edx, edx
0x18004a96b  lea     rcx, [rbp+var_60]
0x18004a96f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18004a974  mov     rcx, [rdi+8]
0x18004a978  xor     edx, edx; length
0x18004a97a  mov     rcx, [rcx+8]; string
0x18004a97e  call    cs:__imp_WindowsGetStringRawBuffer
0x18004a984  mov     rbx, rax
0x18004a987  xor     edx, edx; length
0x18004a989  mov     rcx, [rbp+string]; string
0x18004a98d  call    cs:__imp_WindowsGetStringRawBuffer
0x18004a993  lea     r9, [rbp+var_60]
0x18004a997  mov     r8d, 0Dh
0x18004a99d  mov     rdx, rbx
0x18004a9a0  mov     rcx, rax
0x18004a9a3  call    cs:__imp_GetLocaleFromLanguageAndRegion
0x18004a9a9  mov     ebx, eax
0x18004a9ab  test    eax, eax
0x18004a9ad  jns     short loc_18004A9D6
0x18004a9af  mov     edx, 0A1h; void *
0x18004a9b4  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\oobe\\core\\compone"...
0x18004a9bb  mov     r9d, eax; char *
0x18004a9be  mov     rcx, [rbp+8]; this
0x18004a9c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a9c7  nop
0x18004a9c8  lea     rcx, [rbp+var_60]
0x18004a9cc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004a9d1  jmp     loc_18004ABED
0x18004a9d6  mov     rdx, [rbp+var_60]; unsigned __int16 *
0x18004a9da  lea     rcx, [rbp+hstringHeader]; this
0x18004a9de  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18004a9e3  mov     ecx, 3Bh ; ';'
0x18004a9e8  mov     rdx, qword ptr [rbp+hstringHeader.Reserved]
0x18004a9ec  call    cs:__imp_SetUserLanguagesCore
0x18004a9f2  mov     ebx, eax
0x18004a9f4  test    eax, eax
0x18004a9f6  jns     short loc_18004A9FF
0x18004a9f8  mov     edx, 0A2h
0x18004a9fd  jmp     short loc_18004A9B4
0x18004a9ff  mov     rax, [rdi]
0x18004aa02  mov     rax, [rax+60h]
0x18004aa06  test    rax, rax
0x18004aa09  cmovz   rax, cs:__imp_NlsUpdateLocale
0x18004aa11  mov     edx, 1
0x18004aa16  mov     rcx, [rbp+var_60]
0x18004aa1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aa1f  test    eax, eax
0x18004aa21  jz      short loc_18004AA3F
0x18004aa23  mov     rcx, [rbp+8]; this
0x18004aa27  mov     r9d, eax; char *
0x18004aa2a  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\oobe\\core\\compone"...
0x18004aa31  mov     edx, 0AAh; void *
0x18004aa36  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004aa3b  mov     ebx, eax
0x18004aa3d  jmp     short loc_18004A9C8
0x18004aa3f  mov     [rbp+var_48], 0
0x18004aa47  lea     rdx, [rbp+var_48]
0x18004aa4b  call    ??$CreateExternalObjectVector@UIOobeKeyboard@CloudExperienceHostAPI@@V?$Vector@PEAUIOobeKeyboard@CloudExperienceHostAPI@@U?$DefaultEqualityPredicate@PEAUIOobeKeyboard@CloudExperienceHostAPI@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIOobeKeyboard@CloudExperienceHostAPI@@@4567@U?$DefaultVectorOptions@PEAUIOobeKeyboard@CloudExperienceHostAPI@@@4567@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAUIOobeKeyboard@CloudExperienceHostAPI@@U?$DefaultEqualityPredicate@PEAUIOobeKeyboard@CloudExperienceHostAPI@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIOobeKeyboard@CloudExperienceHostAPI@@@4567@U?$DefaultVectorOptions@PEAUIOobeKeyboard@CloudExperienceHostAPI@@@4567@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<CloudExperienceHostAPI::IOobeKeyboard,Windows::Foundation::Collections::Internal::Vector<CloudExperienceHostAPI::IOobeKeyboard *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<CloudExperienceHostAPI::IOobeKeyboard *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<CloudExperienceHostAPI::IOobeKeyboard *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<CloudExperienceHostAPI::IOobeKeyboard *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<CloudExperienceHostAPI::IOobeKeyboard *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<CloudExperienceHostAPI::IOobeKeyboard *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<CloudExperienceHostAPI::IOobeKeyboard *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<CloudExperienceHostAPI::IOobeKeyboard *>> * *)
0x18004aa50  mov     ebx, eax
0x18004aa52  test    eax, eax
0x18004aa54  jns     short loc_18004AA7D
0x18004aa56  mov     rcx, [rbp+8]; this
0x18004aa5a  mov     r9d, eax; char *
0x18004aa5d  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\oobe\\core\\compone"...
0x18004aa64  mov     edx, 0AFh; void *
0x18004aa69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004aa6e  nop
0x18004aa6f  lea     rcx, [rbp+var_48]
0x18004aa73  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18004aa78  jmp     loc_18004A9C8
0x18004aa7d  mov     [rbp+var_50], 0
0x18004aa85  mov     rcx, [rbp+var_48]
0x18004aa89  mov     rax, [rcx]
0x18004aa8c  mov     [rbp+var_50], 0
0x18004aa94  lea     rdx, [rbp+var_50]
0x18004aa98  mov     rax, [rax+40h]
0x18004aa9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aaa1  mov     ebx, eax
0x18004aaa3  test    eax, eax
0x18004aaa5  jns     short loc_18004AACB
0x18004aaa7  mov     rcx, [rbp+8]; this
0x18004aaab  mov     r9d, eax; char *
0x18004aaae  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\oobe\\core\\compone"...
0x18004aab5  mov     edx, 0B1h; void *
0x18004aaba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004aabf  nop
0x18004aac0  lea     rcx, [rbp+var_50]
0x18004aac4  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18004aac9  jmp     short loc_18004AA6F
0x18004aacb  mov     rcx, [rdi]
0x18004aace  mov     rcx, [rcx+78h]
0x18004aad2  mov     [rbp+var_58], rcx
0x18004aad6  test    rcx, rcx
0x18004aad9  jz      short loc_18004AAEB
0x18004aadb  mov     rax, [rcx]
0x18004aade  mov     rax, [rax+8]
0x18004aae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aae7  mov     rcx, [rbp+var_58]
0x18004aaeb  test    rcx, rcx
0x18004aaee  jnz     short loc_18004AB56
0x18004aaf0  mov     [rbp+var_58], rcx
0x18004aaf4  mov     [rbp+var_18], rcx
0x18004aaf8  lea     r9d, [rcx+35h]; unsigned int
0x18004aafc  lea     r8d, [rcx+36h]; unsigned int
0x18004ab00  lea     rdx, ?RuntimeClass_CloudExperienceHostAPI_OobeKeyboardManagerStaticsCore@@3QBGB; "CloudExperienceHostAPI.OobeKeyboardMana"...
0x18004ab07  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18004ab0b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004ab10  lea     r8, [rbp+var_58]
0x18004ab14  lea     rdx, _GUID_be66109f_b9c6_4f48_b468_bbd48819ac4b
0x18004ab1b  mov     rcx, [rbp+var_18]
0x18004ab1f  call    cs:__imp_RoGetActivationFactory
0x18004ab25  mov     ebx, eax
0x18004ab27  test    eax, eax
0x18004ab29  jns     short loc_18004AB52
0x18004ab2b  mov     rcx, [rbp+8]; this
0x18004ab2f  mov     r9d, eax; char *
0x18004ab32  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\oobe\\core\\compone"...
0x18004ab39  mov     edx, 0B6h; void *
0x18004ab3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ab43  nop
0x18004ab44  lea     rcx, [rbp+var_58]
0x18004ab48  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18004ab4d  jmp     loc_18004AAC0
0x18004ab52  mov     rcx, [rbp+var_58]
0x18004ab56  mov     [rbp+var_40], 0
0x18004ab5e  mov     rax, [rcx]
0x18004ab61  mov     [rbp+var_40], 0
0x18004ab69  lea     r8, [rbp+var_40]
0x18004ab6d  mov     rdx, [rbp+var_50]
0x18004ab71  mov     rax, [rax+38h]
0x18004ab75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ab7a  mov     ebx, eax
0x18004ab7c  test    eax, eax
0x18004ab7e  jns     short loc_18004ABA4
0x18004ab80  mov     edx, 0BAh; void *
0x18004ab85  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\oobe\\core\\compone"...
0x18004ab8c  mov     r9d, eax; char *
0x18004ab8f  mov     rcx, [rbp+8]; this
0x18004ab93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ab98  nop
0x18004ab99  lea     rcx, [rbp+var_40]
0x18004ab9d  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18004aba2  jmp     short loc_18004AB44
0x18004aba4  mov     rcx, [rbp+var_40]
0x18004aba8  call    ??$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@details@wil@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)
0x18004abad  mov     ebx, eax
0x18004abaf  test    eax, eax
0x18004abb1  jns     short loc_18004ABBA
0x18004abb3  mov     edx, 0BCh
0x18004abb8  jmp     short loc_18004AB85
0x18004abba  lea     rcx, [rbp+var_40]
0x18004abbe  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18004abc3  nop
0x18004abc4  lea     rcx, [rbp+var_58]
0x18004abc8  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18004abcd  nop
0x18004abce  lea     rcx, [rbp+var_50]
0x18004abd2  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18004abd7  nop
0x18004abd8  lea     rcx, [rbp+var_48]
0x18004abdc  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18004abe1  nop
0x18004abe2  lea     rcx, [rbp+var_60]
0x18004abe6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004abeb  xor     ebx, ebx
0x18004abed  mov     rcx, [rbp+string]; string
0x18004abf1  call    cs:__imp_WindowsDeleteString
0x18004abf7  mov     eax, ebx
0x18004abf9  mov     rcx, [rbp+var_10]
0x18004abfd  xor     rcx, rsp; StackCookie
0x18004ac00  call    __security_check_cookie
0x18004ac05  lea     r11, [rsp+80h+var_s0]
0x18004ac0d  mov     rbx, [r11+18h]
0x18004ac11  mov     rdi, [r11+20h]
0x18004ac15  mov     rsp, r11
0x18004ac18  pop     rbp
0x18004ac19  retn
```
