# _lambda_1c5b8054ef2dab01625e1110c80e4a36_::operator()(Windows::Internal::CNoResult &)

- ea: `0x180036740`
- end: `0x180036a6d`
- name: `??R_lambda_1c5b8054ef2dab01625e1110c80e4a36_@@QEBAJAEAVCNoResult@Internal@Windows@@@Z`
- size: `813`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800385c0`

## callees

- `0x180002b60`
- `0x1800076b4`
- `0x1800076d4`
- `0x180009760`
- `0x180009814`
- `0x18000a4f8`
- `0x1800117bc`
- `0x180035748`
- `0x1800365c0`
- `0x1800365f0`
- `0x180036740`
- `0x180037378`
- `0x1800388b0`
- `0x180038c24`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180036832`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180036832`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800367f4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800367f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036899`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036899`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800367b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180036864`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800368a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800367b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180036864`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800368a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800368f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800368f9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800367cd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800367cd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180036943`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180036943`
- `Bcp47Langs!Bcp47GetUnIsoRegionCode` at `0x1800368c2`
- `Bcp47Langs!Bcp47GetUnIsoRegionCode` at `0x1800368c2`

## string_xrefs

- `0x180036797`: `shellcommon\shell\oobe\core\components\winrt\oobedisplaylanguagecore.cpp`
- `0x180036807`: `shellcommon\shell\oobe\core\components\winrt\oobedisplaylanguagecore.cpp`
- `0x18003684d`: `shellcommon\shell\oobe\core\components\winrt\oobedisplaylanguagecore.cpp`
- `0x1800368d6`: `shellcommon\shell\oobe\core\components\winrt\oobedisplaylanguagecore.cpp`
- `0x180036956`: `shellcommon\shell\oobe\core\components\winrt\oobedisplaylanguagecore.cpp`
- `0x1800369b4`: `shellcommon\shell\oobe\core\components\winrt\oobedisplaylanguagecore.cpp`
- `0x1800367ed`: `coreglobconfig.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall _lambda_1c5b8054ef2dab01625e1110c80e4a36_::operator()(__int64 a1)
{
  int CurrentUiLanguage; // ebx
  const WCHAR *StringRawBuffer; // rax
  unsigned __int8 v4; // dl
  HMODULE Library; // rax
  const char *v6; // r9
  FARPROC ProcAddress; // rbx
  __int64 v8; // r9
  __int64 v9; // rdx
  PCWSTR v10; // rax
  int v11; // eax
  const unsigned __int16 *v12; // rax
  int UnIsoRegionCode; // eax
  __int64 v14; // r9
  __int64 v15; // rdx
  int ActivationFactory; // eax
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rdx
  unsigned __int8 v20; // dl
  BOOL bIgnoreCase; // [rsp+20h] [rbp-39h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-39h]
  _BYTE v24[8]; // [rsp+30h] [rbp-29h] BYREF
  HSTRING string; // [rsp+38h] [rbp-21h] BYREF
  __int64 v26; // [rsp+40h] [rbp-19h] BYREF
  __int64 v27; // [rsp+48h] [rbp-11h] BYREF
  __int64 *v28; // [rsp+50h] [rbp-9h] BYREF
  HMODULE v29; // [rsp+58h] [rbp-1h] BYREF
  LPCWCH lpString1; // [rsp+60h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v32; // [rsp+80h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  lpString1 = 0;
  *(_OWORD *)&hstringHeader.Reserved.Reserved1 = (unsigned __int64)&lpString1;
  hstringHeader.Reserved.Reserved2[16] = 1;
  CurrentUiLanguage = CloudExperienceHostAPI::OobeDisplayLanguageManagerCore::GetCurrentUiLanguage((unsigned __int16 **)&hstringHeader.Reserved.Reserved2[8]);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&hstringHeader);
  if ( CurrentUiLanguage < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12E,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobedisplaylanguagecore.cpp",
      (const char *)(unsigned int)CurrentUiLanguage,
      bIgnoreCase);
    goto LABEL_32;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)a1, 0);
  if ( CompareStringOrdinal(lpString1, -1, StringRawBuffer, -1, 1) != 2 )
  {
    CloudExperienceHostAPI::OobeLanguageCommitSideEffectsCore::set_RebootRequired(
      *(CloudExperienceHostAPI::OobeLanguageCommitSideEffectsCore **)(a1 + 16),
      v4);
    Library = LoadLibraryExW(L"coreglobconfig.dll", 0, 0x800u);
    v29 = Library;
    if ( !Library )
    {
      CurrentUiLanguage = wil::details::in1diag3::Return_GetLastError(
                            retaddr,
                            (void *)0x139,
                            (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobedisplaylanguagecore.cpp",
                            v6);
LABEL_6:
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v29);
      goto LABEL_32;
    }
    ProcAddress = GetProcAddress(Library, "SetDisplayLanguageCore");
    if ( !ProcAddress )
    {
      CurrentUiLanguage = -2147418113;
      v8 = 2147549183LL;
      v9 = 316;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobedisplaylanguagecore.cpp",
        (const char *)v8,
        bIgnoreCasea);
      goto LABEL_6;
    }
    v10 = WindowsGetStringRawBuffer(*(HSTRING *)a1, 0);
    v11 = ((__int64 (__fastcall *)(PCWSTR, __int64))ProcAddress)(v10, 4);
    CurrentUiLanguage = v11;
    if ( v11 < 0 )
    {
      v8 = (unsigned int)v11;
      v9 = 325;
      goto LABEL_9;
    }
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v29);
  }
  WindowsDeleteString(0);
  string = 0;
  v12 = WindowsGetStringRawBuffer(*(HSTRING *)a1, 0);
  Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)&hstringHeader, v12);
  UnIsoRegionCode = Bcp47GetUnIsoRegionCode(hstringHeader.Reserved.Reserved1, &string);
  CurrentUiLanguage = UnIsoRegionCode;
  if ( UnIsoRegionCode < 0 )
  {
    v14 = (unsigned int)UnIsoRegionCode;
    v15 = 331;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobedisplaylanguagecore.cpp",
      (const char *)v14,
      bIgnoreCasea);
LABEL_16:
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    goto LABEL_32;
  }
  if ( WindowsIsStringEmpty(string) )
  {
    CurrentUiLanguage = -2147418113;
    v14 = 2147549183LL;
    v15 = 332;
    goto LABEL_15;
  }
  v28 = 0;
  v32 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"CloudExperienceHostAPI.OobeRegionManagerStaticsCore",
    0x34u,
    0x33u);
  ActivationFactory = RoGetActivationFactory(v32, &GUID_1b2ae221_7bbf_48db_9768_188a83d21d22, &v28);
  CurrentUiLanguage = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14F,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobedisplaylanguagecore.cpp",
      (const char *)(unsigned int)ActivationFactory,
      bIgnoreCasea);
LABEL_21:
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v28);
    goto LABEL_16;
  }
  v27 = 0;
  v26 = 0;
  v17 = *v28;
  v26 = 0;
  v27 = 0;
  v18 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 *, __int64 *))(v17 + 64))(v28, string, &v27, &v26);
  CurrentUiLanguage = v18;
  if ( v18 < 0 )
  {
    v19 = 339;
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobedisplaylanguagecore.cpp",
      (const char *)(unsigned int)v18,
      bIgnoreCasea);
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v26);
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v27);
    goto LABEL_21;
  }
  v18 = WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(v26);
  CurrentUiLanguage = v18;
  if ( v18 < 0 )
  {
    v19 = 340;
    goto LABEL_24;
  }
  v24[0] = 0;
  v18 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v27 + 48LL))(v27, v24);
  CurrentUiLanguage = v18;
  if ( v18 < 0 )
  {
    v19 = 343;
    goto LABEL_24;
  }
  if ( v24[0] )
    CloudExperienceHostAPI::OobeLanguageCommitSideEffectsCore::set_RebootRequired(
      *(CloudExperienceHostAPI::OobeLanguageCommitSideEffectsCore **)(a1 + 16),
      v20);
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v26);
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v27);
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v28);
  Windows::Internal::String::~String((Windows::Internal::String *)&string);
  CurrentUiLanguage = 0;
LABEL_32:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString1);
  return (unsigned int)CurrentUiLanguage;
}

```

## disassembly

```asm
0x180036740  push    rbp
0x180036742  push    rbx
0x180036743  push    rsi
0x180036744  push    rdi
0x180036745  lea     rbp, [rsp-3Fh]
0x18003674a  sub     rsp, 98h
0x180036751  mov     rax, cs:__security_cookie
0x180036758  xor     rax, rsp
0x18003675b  mov     [rbp+57h+var_28], rax
0x18003675f  mov     rdi, rcx
0x180036762  xor     esi, esi
0x180036764  mov     [rbp+57h+lpString1], rsi
0x180036768  lea     rax, [rbp+57h+lpString1]
0x18003676c  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x180036770  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], rsi
0x180036774  mov     byte ptr [rbp+57h+hstringHeader.Reserved+10h], 1
0x180036778  lea     rcx, [rbp+57h+hstringHeader.Reserved+8]; unsigned __int16 **
0x18003677c  call    ?GetCurrentUiLanguage@OobeDisplayLanguageManagerCore@CloudExperienceHostAPI@@CAJPEAPEAG@Z; CloudExperienceHostAPI::OobeDisplayLanguageManagerCore::GetCurrentUiLanguage(ushort * *)
0x180036781  mov     ebx, eax
0x180036783  lea     rcx, [rbp+57h+hstringHeader]
0x180036787  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18003678c  test    ebx, ebx
0x18003678e  jns     short loc_1800367AD
0x180036790  mov     rcx, [rbp+5Fh]; this
0x180036794  mov     r9d, ebx; char *
0x180036797  lea     r8, aShellcommonShe_18; "shellcommon\\shell\\oobe\\core\\compone"...
0x18003679e  mov     edx, 12Eh; void *
0x1800367a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800367a8  jmp     loc_180036A4A
0x1800367ad  xor     edx, edx; length
0x1800367af  mov     rcx, [rdi]; string
0x1800367b2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800367b8  mov     [rsp+0B0h+bIgnoreCase], 1; int
0x1800367c0  or      edx, 0FFFFFFFFh; cchCount1
0x1800367c3  mov     r9d, edx; cchCount2
0x1800367c6  mov     r8, rax; lpString2
0x1800367c9  mov     rcx, [rbp+57h+lpString1]; lpString1
0x1800367cd  call    cs:__imp_CompareStringOrdinal
0x1800367d3  cmp     eax, 2
0x1800367d6  jz      loc_180036893
0x1800367dc  mov     rcx, [rdi+10h]; this
0x1800367e0  call    ?set_RebootRequired@OobeLanguageCommitSideEffectsCore@CloudExperienceHostAPI@@QEAAXE@Z; CloudExperienceHostAPI::OobeLanguageCommitSideEffectsCore::set_RebootRequired(uchar)
0x1800367e5  xor     edx, edx; hFile
0x1800367e7  mov     r8d, 800h; dwFlags
0x1800367ed  lea     rcx, aCoreglobconfig; "coreglobconfig.dll"
0x1800367f4  call    cs:__imp_LoadLibraryExW
0x1800367fa  mov     [rbp+57h+var_58], rax
0x1800367fe  test    rax, rax
0x180036801  jnz     short loc_180036828
0x180036803  mov     rcx, [rbp+5Fh]; this
0x180036807  lea     r8, aShellcommonShe_18; "shellcommon\\shell\\oobe\\core\\compone"...
0x18003680e  mov     edx, 139h; void *
0x180036813  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180036818  mov     ebx, eax
0x18003681a  lea     rcx, [rbp+57h+var_58]
0x18003681e  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180036823  jmp     loc_180036A4A
0x180036828  lea     rdx, aSetdisplaylang; "SetDisplayLanguageCore"
0x18003682f  mov     rcx, rax; hModule
0x180036832  call    cs:__imp_GetProcAddress
0x180036838  mov     rbx, rax
0x18003683b  test    rax, rax
0x18003683e  jnz     short loc_18003685F
0x180036840  mov     ebx, 8000FFFFh
0x180036845  mov     r9d, ebx; char *
0x180036848  mov     edx, 13Ch; void *
0x18003684d  lea     r8, aShellcommonShe_18; "shellcommon\\shell\\oobe\\core\\compone"...
0x180036854  mov     rcx, [rbp+5Fh]; this
0x180036858  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003685d  jmp     short loc_18003681A
0x18003685f  xor     edx, edx; length
0x180036861  mov     rcx, [rdi]; string
0x180036864  call    cs:__imp_WindowsGetStringRawBuffer
0x18003686a  mov     edx, 4
0x18003686f  mov     rcx, rax
0x180036872  mov     rax, rbx
0x180036875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003687a  mov     ebx, eax
0x18003687c  test    eax, eax
0x18003687e  jns     short loc_18003688A
0x180036880  mov     r9d, eax
0x180036883  mov     edx, 145h
0x180036888  jmp     short loc_18003684D
0x18003688a  lea     rcx, [rbp+57h+var_58]
0x18003688e  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180036893  mov     [rbp+57h+string], rsi
0x180036897  xor     ecx, ecx; string
0x180036899  call    cs:__imp_WindowsDeleteString
0x18003689f  mov     [rbp+57h+string], rsi
0x1800368a3  xor     edx, edx; length
0x1800368a5  mov     rcx, [rdi]; string
0x1800368a8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800368ae  mov     rdx, rax; unsigned __int16 *
0x1800368b1  lea     rcx, [rbp+57h+hstringHeader]; this
0x1800368b5  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x1800368ba  lea     rdx, [rbp+57h+string]
0x1800368be  mov     rcx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x1800368c2  call    cs:__imp_Bcp47GetUnIsoRegionCode
0x1800368c8  mov     ebx, eax
0x1800368ca  test    eax, eax
0x1800368cc  jns     short loc_1800368F5
0x1800368ce  mov     r9d, eax; char *
0x1800368d1  mov     edx, 14Bh; void *
0x1800368d6  lea     r8, aShellcommonShe_18; "shellcommon\\shell\\oobe\\core\\compone"...
0x1800368dd  mov     rcx, [rbp+5Fh]; this
0x1800368e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800368e6  nop
0x1800368e7  lea     rcx, [rbp+57h+string]; this
0x1800368eb  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800368f0  jmp     loc_180036A4A
0x1800368f5  mov     rcx, [rbp+57h+string]; string
0x1800368f9  call    cs:__imp_WindowsIsStringEmpty
0x1800368ff  test    eax, eax
0x180036901  jz      short loc_180036912
0x180036903  mov     ebx, 8000FFFFh
0x180036908  mov     r9d, ebx
0x18003690b  mov     edx, 14Ch
0x180036910  jmp     short loc_1800368D6
0x180036912  mov     [rbp+57h+var_60], rsi
0x180036916  mov     [rbp+57h+var_30], rsi
0x18003691a  mov     r9d, 33h ; '3'; unsigned int
0x180036920  lea     r8d, [r9+1]; unsigned int
0x180036924  lea     rdx, ?RuntimeClass_CloudExperienceHostAPI_OobeRegionManagerStaticsCore@@3QBGB; "CloudExperienceHostAPI.OobeRegionManage"...
0x18003692b  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18003692f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180036934  lea     r8, [rbp+57h+var_60]
0x180036938  lea     rdx, _GUID_1b2ae221_7bbf_48db_9768_188a83d21d22
0x18003693f  mov     rcx, [rbp+57h+var_30]
0x180036943  call    cs:__imp_RoGetActivationFactory
0x180036949  mov     ebx, eax
0x18003694b  test    eax, eax
0x18003694d  jns     short loc_180036976
0x18003694f  mov     rcx, [rbp+5Fh]; this
0x180036953  mov     r9d, eax; char *
0x180036956  lea     r8, aShellcommonShe_18; "shellcommon\\shell\\oobe\\core\\compone"...
0x18003695d  mov     edx, 14Fh; void *
0x180036962  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036967  nop
0x180036968  lea     rcx, [rbp+57h+var_60]
0x18003696c  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180036971  jmp     loc_1800368E7
0x180036976  mov     [rbp+57h+var_68], rsi
0x18003697a  mov     [rbp+57h+var_70], rsi
0x18003697e  mov     rcx, [rbp+57h+var_60]
0x180036982  mov     rax, [rcx]
0x180036985  mov     [rbp+57h+var_70], rsi
0x180036989  mov     [rbp+57h+var_68], rsi
0x18003698d  lea     r9, [rbp+57h+var_70]
0x180036991  lea     r8, [rbp+57h+var_68]
0x180036995  mov     rdx, [rbp+57h+string]
0x180036999  mov     rax, [rax+40h]
0x18003699d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800369a2  mov     ebx, eax
0x1800369a4  test    eax, eax
0x1800369a6  jns     short loc_1800369D6
0x1800369a8  mov     edx, 153h; void *
0x1800369ad  mov     rcx, [rbp+5Fh]; this
0x1800369b1  mov     r9d, eax; char *
0x1800369b4  lea     r8, aShellcommonShe_18; "shellcommon\\shell\\oobe\\core\\compone"...
0x1800369bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800369c0  nop
0x1800369c1  lea     rcx, [rbp+57h+var_70]
0x1800369c5  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x1800369ca  nop
0x1800369cb  lea     rcx, [rbp+57h+var_68]
0x1800369cf  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x1800369d4  jmp     short loc_180036968
0x1800369d6  mov     rcx, [rbp+57h+var_70]
0x1800369da  call    ??$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)
0x1800369df  mov     ebx, eax
0x1800369e1  test    eax, eax
0x1800369e3  jns     short loc_1800369EC
0x1800369e5  mov     edx, 154h
0x1800369ea  jmp     short loc_1800369AD
0x1800369ec  mov     [rbp+57h+var_80], sil
0x1800369f0  mov     rcx, [rbp+57h+var_68]
0x1800369f4  mov     rax, [rcx]
0x1800369f7  lea     rdx, [rbp+57h+var_80]
0x1800369fb  mov     rax, [rax+30h]
0x1800369ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a04  mov     ebx, eax
0x180036a06  test    eax, eax
0x180036a08  jns     short loc_180036A11
0x180036a0a  mov     edx, 157h
0x180036a0f  jmp     short loc_1800369AD
0x180036a11  cmp     [rbp+57h+var_80], sil
0x180036a15  jz      short loc_180036A21
0x180036a17  mov     rcx, [rdi+10h]; this
0x180036a1b  call    ?set_RebootRequired@OobeLanguageCommitSideEffectsCore@CloudExperienceHostAPI@@QEAAXE@Z; CloudExperienceHostAPI::OobeLanguageCommitSideEffectsCore::set_RebootRequired(uchar)
0x180036a20  nop
0x180036a21  lea     rcx, [rbp+57h+var_70]
0x180036a25  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180036a2a  nop
0x180036a2b  lea     rcx, [rbp+57h+var_68]
0x180036a2f  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180036a34  nop
0x180036a35  lea     rcx, [rbp+57h+var_60]
0x180036a39  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180036a3e  nop
0x180036a3f  lea     rcx, [rbp+57h+string]; this
0x180036a43  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180036a48  mov     ebx, esi
0x180036a4a  lea     rcx, [rbp+57h+lpString1]
0x180036a4e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180036a53  mov     eax, ebx
0x180036a55  mov     rcx, [rbp+57h+var_28]
0x180036a59  xor     rcx, rsp; StackCookie
0x180036a5c  call    __security_check_cookie
0x180036a61  add     rsp, 98h
0x180036a68  pop     rdi
0x180036a69  pop     rsi
0x180036a6a  pop     rbx
0x180036a6b  pop     rbp
0x180036a6c  retn
```
