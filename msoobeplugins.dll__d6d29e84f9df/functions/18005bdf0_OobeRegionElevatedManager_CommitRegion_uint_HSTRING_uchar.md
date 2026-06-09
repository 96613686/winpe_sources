# OobeRegionElevatedManager::CommitRegion(uint,HSTRING__ * *,uchar *)

- ea: `0x18005bdf0`
- end: `0x18005c146`
- name: `?CommitRegion@OobeRegionElevatedManager@@UEAAJIPEAPEAUHSTRING__@@PEAE@Z`
- size: `854`
- prototype: `__int64 __fastcall(OobeRegionElevatedManager *this, unsigned __int64, HSTRING *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003470`
- `0x180008524`
- `0x180008544`
- `0x18001ad08`
- `0x18001e9a4`
- `0x18001ea00`
- `0x1800230b0`
- `0x180023574`
- `0x180049f18`
- `0x18004a7d4`
- `0x18004be24`
- `0x1800599d0`
- `0x180059b90`
- `0x180059cc0`
- `0x18005bdf0`
- `0x18005c4a8`
- `0x18005c76c`
- `0x18005ca3c`
- `0x1800b8834`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!SetUserGeoID` at `0x18005be64`
- `api-ms-win-core-localization-l1-2-0!SetUserGeoID` at `0x18005be64`
- `api-ms-win-core-localization-l1-2-0!GetGeoInfoW` at `0x18005bf49`
- `api-ms-win-core-localization-l1-2-0!GetGeoInfoW` at `0x18005bf49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005bef7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c11f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005bef7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c11f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005c0e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005c0e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005bf89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005c053`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005bf89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005c053`
- `WinLangdb!GetLocaleFromLanguageAndRegion` at `0x18005bfa2`
- `WinLangdb!GetLocaleFromLanguageAndRegion` at `0x18005bfa2`
- `WinLangdb!SetUserLanguages` at `0x18005c006`
- `WinLangdb!SetUserLanguages` at `0x18005c006`

## string_xrefs

- `0x18005be3e`: `OobeRegionElevatedManager::CommitRegion`
- `0x18005be76`: `shell\oobe\machine\plugins\adapters\com\ooberegion.cpp`
- `0x18005bea0`: `shell\oobe\machine\plugins\adapters\com\ooberegion.cpp`
- `0x18005bf1d`: `shell\oobe\machine\plugins\adapters\com\ooberegion.cpp`
- `0x18005bf5b`: `shell\oobe\machine\plugins\adapters\com\ooberegion.cpp`
- `0x18005bfb9`: `shell\oobe\machine\plugins\adapters\com\ooberegion.cpp`
- `0x18005c035`: `shell\oobe\machine\plugins\adapters\com\ooberegion.cpp`
- `0x18005c092`: `shell\oobe\machine\plugins\adapters\com\ooberegion.cpp`
- `0x18005be54`: `CommitRegion %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OobeRegionElevatedManager::CommitRegion(
        OobeRegionElevatedManager *this,
        unsigned __int64 a2,
        HSTRING *a3,
        unsigned __int8 *a4)
{
  unsigned __int8 *v4; // r14
  HSTRING *v5; // r15
  unsigned int v6; // esi
  __int64 v7; // rcx
  CloudExperienceHostCoreTelemetry *v8; // rcx
  const char *v9; // r9
  int v11; // eax
  const char *v12; // r9
  int LocaleNameFromDisplayLanguage; // eax
  unsigned int LastError; // edi
  const char *v15; // r9
  PCWSTR StringRawBuffer; // rax
  int LocaleFromLanguageAndRegion; // eax
  int v18; // eax
  int v19; // edi
  HRESULT v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rsi
  __int64 v23; // rdx
  int LangId; // [rsp+20h] [rbp-98h]
  int LangIda; // [rsp+20h] [rbp-98h]
  PCNZWCH sourceString; // [rsp+30h] [rbp-88h] BYREF
  __int64 v27; // [rsp+38h] [rbp-80h] BYREF
  HSTRING string; // [rsp+40h] [rbp-78h] BYREF
  PCNZWCH v29; // [rsp+48h] [rbp-70h] BYREF
  PCWSTR v30; // [rsp+50h] [rbp-68h] BYREF
  _QWORD v31[4]; // [rsp+58h] [rbp-60h] BYREF
  WCHAR GeoData; // [rsp+78h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v4 = a4;
  v5 = a3;
  v6 = a2;
  LODWORD(v27) = a2;
  v29 = (PCNZWCH)a3;
  v30 = (PCWSTR)a4;
  if ( CloudExperienceHostCoreTelemetry::IsEnabled((unsigned __int8)this, a2) )
  {
    wil::details::static_lazy<CloudExperienceHostCoreTelemetry>::get(
      v7,
      _lambda_5eb5719585a1dfff1c0403c1b5c6f80a_::_lambda_invoker_cdecl_);
    CloudExperienceHostCoreTelemetry::GlobalizationState_(v8, "OobeRegionElevatedManager::CommitRegion");
  }
  *v5 = 0;
  *v4 = 0;
  UnattendLogW(0, L"CommitRegion %d", v6);
  if ( !SetUserGeoID(v6) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x36,
             (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\ooberegion.cpp",
             v9);
  v11 = SetDefaultDvdRegionFromCommittedRegion(v6);
  if ( v11 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x39,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\ooberegion.cpp",
      (const char *)(unsigned int)v11,
      LangId);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_IntegratedServicesPolicyControl>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IntegratedServicesPolicyControl>::GetImpl'::`2'::impl) )
  {
    try
    {
      v31[0] = 0;
      Settings::Internal::DeviceRegionStore::SetDeviceRegion((Settings::Internal::DeviceRegionStore *)v31, v6);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v31);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x40,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\ooberegion.cpp",
        v12);
      v6 = v27;
      v5 = (HSTRING *)v29;
      v4 = (unsigned __int8 *)v30;
    }
  }
  string = 0;
  WindowsDeleteString(0);
  string = 0;
  LocaleNameFromDisplayLanguage = OobeRegionElevatedManager::GetLocaleNameFromDisplayLanguage(&string);
  LastError = LocaleNameFromDisplayLanguage;
  if ( LocaleNameFromDisplayLanguage >= 0 )
  {
    if ( GetGeoInfoW(v6, 4u, &GeoData, 3, 0) )
    {
      sourceString = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &sourceString,
        0);
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      LocaleFromLanguageAndRegion = GetLocaleFromLanguageAndRegion(StringRawBuffer, &GeoData, 1, &sourceString);
      LastError = LocaleFromLanguageAndRegion;
      if ( LocaleFromLanguageAndRegion >= 0 )
      {
        UnattendLogW(0, L"Calling SetUserLanguages for paired locale %s", sourceString);
        Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v31, sourceString);
        v18 = SetUserLanguages(59, v31[0]);
        v19 = v18;
        if ( v18 < 0 )
          UnattendLogW(1, L"SetUserLanguages failed [hr=0x%08X]", (unsigned int)v18);
        if ( v19 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x53,
            (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\ooberegion.cpp",
            (const char *)(unsigned int)v19,
            LangIda);
        v27 = 0;
        v30 = WindowsGetStringRawBuffer(string, 0);
        v29 = sourceString;
        v20 = Microsoft::WRL::Details::MakeAndInitialize<CSetLocaleTask,CSetLocaleTask,unsigned short const * &,unsigned short const * &>(
                &v27,
                &v29,
                &v30);
        LastError = v20;
        if ( v20 >= 0 )
        {
          v22 = v27;
          v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 32LL))(v27);
          LastError = v20;
          if ( v20 >= 0 )
          {
            v23 = -1;
            do
              ++v23;
            while ( sourceString[v23] );
            v20 = WindowsCreateString(sourceString, v23, v5);
            LastError = v20;
            if ( v20 >= 0 )
            {
              if ( *(_BYTE *)(v22 + 892) )
                *v4 = 1;
              wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v27);
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&sourceString);
              LastError = 0;
              goto LABEL_31;
            }
            v21 = 89;
          }
          else
          {
            v21 = 87;
          }
        }
        else
        {
          v21 = 86;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v21,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\ooberegion.cpp",
          (const char *)(unsigned int)v20,
          LangIda);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v27);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x50,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\ooberegion.cpp",
          (const char *)(unsigned int)LocaleFromLanguageAndRegion,
          LangIda);
      }
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&sourceString);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x4B,
                    (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\ooberegion.cpp",
                    v15);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\ooberegion.cpp",
      (const char *)(unsigned int)LocaleNameFromDisplayLanguage,
      LangId);
  }
LABEL_31:
  WindowsDeleteString(string);
  return LastError;
}

```

## disassembly

```asm
0x18005bdf0  push    rbx
0x18005bdf2  push    rsi
0x18005bdf3  push    rdi
0x18005bdf4  push    r14
0x18005bdf6  push    r15
0x18005bdf8  sub     rsp, 90h
0x18005bdff  mov     rax, cs:__security_cookie
0x18005be06  xor     rax, rsp
0x18005be09  mov     [rsp+0B8h+var_38], rax
0x18005be11  mov     r14, r9
0x18005be14  mov     r15, r8
0x18005be17  mov     esi, edx
0x18005be19  mov     dword ptr [rsp+0B8h+var_80], edx
0x18005be1d  mov     [rsp+0B8h+var_70], r8
0x18005be22  mov     [rsp+0B8h+var_68], r9
0x18005be27  call    ?IsEnabled@CloudExperienceHostCoreTelemetry@@SA_NE_K@Z; CloudExperienceHostCoreTelemetry::IsEnabled(uchar,unsigned __int64)
0x18005be2c  xor     ebx, ebx
0x18005be2e  test    al, al
0x18005be30  jz      short loc_18005BE4B
0x18005be32  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5eb5719585a1dfff1c0403c1b5c6f80a_@@CA@XZ; _lambda_5eb5719585a1dfff1c0403c1b5c6f80a_::_lambda_invoker_cdecl_(void)
0x18005be39  call    ?get@?$static_lazy@VCloudExperienceHostCoreTelemetry@@@details@wil@@QEAAPEAVCloudExperienceHostCoreTelemetry@@P6AXXZ@Z; wil::details::static_lazy<CloudExperienceHostCoreTelemetry>::get(void (*)(void))
0x18005be3e  lea     rdx, aOoberegionelev; "OobeRegionElevatedManager::CommitRegion"
0x18005be45  call    ?GlobalizationState_@CloudExperienceHostCoreTelemetry@@QEAAXPEBD@Z; CloudExperienceHostCoreTelemetry::GlobalizationState_(char const *)
0x18005be4a  nop
0x18005be4b  mov     [r15], rbx
0x18005be4e  mov     [r14], bl
0x18005be51  mov     r8d, esi
0x18005be54  lea     rdx, aCommitregionD; "CommitRegion %d"
0x18005be5b  xor     ecx, ecx
0x18005be5d  call    UnattendLogW
0x18005be62  mov     ecx, esi; GeoId
0x18005be64  call    cs:__imp_SetUserGeoID
0x18005be6a  test    eax, eax
0x18005be6c  jnz     short loc_18005BE8A
0x18005be6e  mov     rcx, [rsp+0B8h]; this
0x18005be76  lea     r8, aShellOobeMachi_45; "shell\\oobe\\machine\\plugins\\adapters"...
0x18005be7d  lea     edx, [rax+36h]; void *
0x18005be80  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005be85  jmp     loc_18005C127
0x18005be8a  mov     ecx, esi; int
0x18005be8c  call    ?SetDefaultDvdRegionFromCommittedRegion@@YAJJ@Z; SetDefaultDvdRegionFromCommittedRegion(long)
0x18005be91  mov     rcx, [rsp+0B8h]; this
0x18005be99  test    eax, eax
0x18005be9b  jns     short loc_18005BEB1
0x18005be9d  mov     r9d, eax; char *
0x18005bea0  lea     r8, aShellOobeMachi_45; "shell\\oobe\\machine\\plugins\\adapters"...
0x18005bea7  mov     edx, 39h ; '9'; void *
0x18005beac  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005beb1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IntegratedServicesPolicyControl@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IntegratedServicesPolicyControl@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IntegratedServicesPolicyControl> `wil::Feature<__WilFeatureTraits_Feature_IntegratedServicesPolicyControl>::GetImpl(void)'::`2'::impl
0x18005beb8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_IntegratedServicesPolicyControl@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IntegratedServicesPolicyControl>::__private_IsEnabled(void)
0x18005bebd  test    al, al
0x18005bebf  jz      short loc_18005BEF0
0x18005bec1  mov     [rsp+0B8h+var_60], rbx
0x18005bec6  mov     edx, esi; int
0x18005bec8  lea     rcx, [rsp+0B8h+var_60]; this
0x18005becd  call    ?SetDeviceRegion@DeviceRegionStore@Internal@Settings@@QEAAXJ@Z; Settings::Internal::DeviceRegionStore::SetDeviceRegion(long)
0x18005bed2  nop
0x18005bed3  lea     rcx, [rsp+0B8h+var_60]
0x18005bed8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005bedd  nop
0x18005bede  jmp     short loc_18005BEF0
0x18005bee0  xor     ebx, ebx
0x18005bee2  mov     esi, dword ptr [rsp+0B8h+var_80]
0x18005bee6  mov     r15, [rsp+0B8h+var_70]
0x18005beeb  mov     r14, [rsp+0B8h+var_68]
0x18005bef0  mov     [rsp+0B8h+string], rbx
0x18005bef5  xor     ecx, ecx; string
0x18005bef7  call    cs:__imp_WindowsDeleteString
0x18005befd  mov     [rsp+0B8h+string], rbx
0x18005bf02  lea     rcx, [rsp+0B8h+string]; string
0x18005bf07  call    ?GetLocaleNameFromDisplayLanguage@OobeRegionElevatedManager@@CAJPEAPEAUHSTRING__@@@Z; OobeRegionElevatedManager::GetLocaleNameFromDisplayLanguage(HSTRING__ * *)
0x18005bf0c  mov     edi, eax
0x18005bf0e  test    eax, eax
0x18005bf10  jns     short loc_18005BF33
0x18005bf12  mov     rcx, [rsp+0B8h]; this
0x18005bf1a  mov     r9d, eax; char *
0x18005bf1d  lea     r8, aShellOobeMachi_45; "shell\\oobe\\machine\\plugins\\adapters"...
0x18005bf24  mov     edx, 46h ; 'F'; void *
0x18005bf29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005bf2e  jmp     loc_18005C11A
0x18005bf33  mov     word ptr [rsp+0B8h+LangId], bx; int
0x18005bf38  mov     r9d, 3; cchData
0x18005bf3e  lea     r8, [rsp+0B8h+GeoData]; lpGeoData
0x18005bf43  lea     edx, [r9+1]; GeoType
0x18005bf47  mov     ecx, esi; Location
0x18005bf49  call    cs:__imp_GetGeoInfoW
0x18005bf4f  test    eax, eax
0x18005bf51  jnz     short loc_18005BF71
0x18005bf53  mov     rcx, [rsp+0B8h]; this
0x18005bf5b  lea     r8, aShellOobeMachi_45; "shell\\oobe\\machine\\plugins\\adapters"...
0x18005bf62  lea     edx, [rax+4Bh]; void *
0x18005bf65  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005bf6a  mov     edi, eax
0x18005bf6c  jmp     loc_18005C11A
0x18005bf71  mov     [rsp+0B8h+sourceString], rbx
0x18005bf76  xor     edx, edx
0x18005bf78  lea     rcx, [rsp+0B8h+sourceString]
0x18005bf7d  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18005bf82  xor     edx, edx; length
0x18005bf84  mov     rcx, [rsp+0B8h+string]; string
0x18005bf89  call    cs:__imp_WindowsGetStringRawBuffer
0x18005bf8f  lea     r9, [rsp+0B8h+sourceString]
0x18005bf94  mov     r8d, 1
0x18005bf9a  lea     rdx, [rsp+0B8h+GeoData]
0x18005bf9f  mov     rcx, rax
0x18005bfa2  call    cs:__imp_GetLocaleFromLanguageAndRegion
0x18005bfa8  mov     edi, eax
0x18005bfaa  test    eax, eax
0x18005bfac  jns     short loc_18005BFDA
0x18005bfae  mov     rcx, [rsp+0B8h]; this
0x18005bfb6  mov     r9d, eax; char *
0x18005bfb9  lea     r8, aShellOobeMachi_45; "shell\\oobe\\machine\\plugins\\adapters"...
0x18005bfc0  mov     edx, 50h ; 'P'; void *
0x18005bfc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005bfca  nop
0x18005bfcb  lea     rcx, [rsp+0B8h+sourceString]
0x18005bfd0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18005bfd5  jmp     loc_18005C11A
0x18005bfda  mov     r8, [rsp+0B8h+sourceString]
0x18005bfdf  lea     rdx, aCallingSetuser; "Calling SetUserLanguages for paired loc"...
0x18005bfe6  xor     ecx, ecx
0x18005bfe8  call    UnattendLogW
0x18005bfed  mov     rdx, [rsp+0B8h+sourceString]; unsigned __int16 *
0x18005bff2  lea     rcx, [rsp+0B8h+var_60]; this
0x18005bff7  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18005bffc  mov     ecx, 3Bh ; ';'
0x18005c001  mov     rdx, [rsp+0B8h+var_60]
0x18005c006  call    cs:__imp_SetUserLanguages
0x18005c00c  mov     edi, eax
0x18005c00e  test    eax, eax
0x18005c010  jns     short loc_18005C026
0x18005c012  mov     r8d, eax
0x18005c015  lea     rdx, aSetuserlanguag_0; "SetUserLanguages failed [hr=0x%08X]"
0x18005c01c  mov     ecx, 1
0x18005c021  call    UnattendLogW
0x18005c026  mov     rcx, [rsp+0B8h]; this
0x18005c02e  test    edi, edi
0x18005c030  jns     short loc_18005C047
0x18005c032  mov     r9d, edi; char *
0x18005c035  lea     r8, aShellOobeMachi_45; "shell\\oobe\\machine\\plugins\\adapters"...
0x18005c03c  mov     edx, 53h ; 'S'; void *
0x18005c041  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005c046  nop
0x18005c047  mov     [rsp+0B8h+var_80], rbx
0x18005c04c  xor     edx, edx; length
0x18005c04e  mov     rcx, [rsp+0B8h+string]; string
0x18005c053  call    cs:__imp_WindowsGetStringRawBuffer
0x18005c059  mov     [rsp+0B8h+var_68], rax
0x18005c05e  mov     rax, [rsp+0B8h+sourceString]
0x18005c063  mov     [rsp+0B8h+var_70], rax
0x18005c068  lea     r8, [rsp+0B8h+var_68]
0x18005c06d  lea     rdx, [rsp+0B8h+var_70]
0x18005c072  lea     rcx, [rsp+0B8h+var_80]
0x18005c077  call    ??$MakeAndInitialize@VCSetLocaleTask@@V1@AEAPEBGAEAPEBG@Details@WRL@Microsoft@@YAJPEAPEAVCSetLocaleTask@@AEAPEBG1@Z; Microsoft::WRL::Details::MakeAndInitialize<CSetLocaleTask,CSetLocaleTask,ushort const * &,ushort const * &>(CSetLocaleTask * *,ushort const * &,ushort const * &)
0x18005c07c  mov     edi, eax
0x18005c07e  test    eax, eax
0x18005c080  jns     short loc_18005C0AE
0x18005c082  mov     edx, 56h ; 'V'; void *
0x18005c087  mov     rcx, [rsp+0B8h]; this
0x18005c08f  mov     r9d, eax; char *
0x18005c092  lea     r8, aShellOobeMachi_45; "shell\\oobe\\machine\\plugins\\adapters"...
0x18005c099  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c09e  nop
0x18005c09f  lea     rcx, [rsp+0B8h+var_80]
0x18005c0a4  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18005c0a9  jmp     loc_18005BFCB
0x18005c0ae  mov     rsi, [rsp+0B8h+var_80]
0x18005c0b3  mov     rax, [rsi]
0x18005c0b6  mov     rcx, rsi
0x18005c0b9  mov     rax, [rax+20h]
0x18005c0bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c0c2  mov     edi, eax
0x18005c0c4  test    eax, eax
0x18005c0c6  jns     short loc_18005C0CF
0x18005c0c8  mov     edx, 57h ; 'W'
0x18005c0cd  jmp     short loc_18005C087
0x18005c0cf  mov     rcx, [rsp+0B8h+sourceString]; sourceString
0x18005c0d4  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18005c0d8  inc     rdx; length
0x18005c0db  cmp     [rcx+rdx*2], bx
0x18005c0df  jnz     short loc_18005C0D8
0x18005c0e1  mov     r8, r15; string
0x18005c0e4  call    cs:__imp_WindowsCreateString
0x18005c0ea  mov     edi, eax
0x18005c0ec  test    eax, eax
0x18005c0ee  jns     short loc_18005C0F7
0x18005c0f0  mov     edx, 59h ; 'Y'
0x18005c0f5  jmp     short loc_18005C087
0x18005c0f7  cmp     [rsi+37Ch], bl
0x18005c0fd  jz      short loc_18005C103
0x18005c0ff  mov     byte ptr [r14], 1
0x18005c103  lea     rcx, [rsp+0B8h+var_80]
0x18005c108  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18005c10d  nop
0x18005c10e  lea     rcx, [rsp+0B8h+sourceString]
0x18005c113  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18005c118  mov     edi, ebx
0x18005c11a  mov     rcx, [rsp+0B8h+string]; string
0x18005c11f  call    cs:__imp_WindowsDeleteString
0x18005c125  mov     eax, edi
0x18005c127  mov     rcx, [rsp+0B8h+var_38]
0x18005c12f  xor     rcx, rsp; StackCookie
0x18005c132  call    __security_check_cookie
0x18005c137  add     rsp, 90h
0x18005c13e  pop     r15
0x18005c140  pop     r14
0x18005c142  pop     rdi
0x18005c143  pop     rsi
0x18005c144  pop     rbx
0x18005c145  retn
```
