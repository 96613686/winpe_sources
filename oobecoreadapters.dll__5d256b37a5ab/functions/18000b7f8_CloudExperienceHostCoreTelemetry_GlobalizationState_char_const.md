# CloudExperienceHostCoreTelemetry::GlobalizationState_(char const *)

- ea: `0x18000b7f8`
- end: `0x18000b9b0`
- name: `?GlobalizationState_@CloudExperienceHostCoreTelemetry@@QEAAXPEBD@Z`
- size: `440`
- prototype: `void __fastcall(CloudExperienceHostCoreTelemetry *__hidden this, const char *)`
- caller_count: `9`
- callee_count: `7`
- tags: ``

## callers

- `0x18000b6b0`
- `0x180035080`
- `0x180037080`
- `0x180037480`
- `0x18003a6a0`
- `0x180047ff0`
- `0x180048960`
- `0x18004ae30`
- `0x18004b5f0`

## callees

- `0x18000172c`
- `0x1800017f8`
- `0x180002b60`
- `0x1800036e4`
- `0x18000b7f8`
- `0x18000ba0c`
- `0x18000ba44`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetGeoInfoW` at `0x18000b8d9`
- `api-ms-win-core-localization-l1-2-0!GetGeoInfoW` at `0x18000b8d9`
- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x18000b8c1`
- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x18000b8c1`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x18000b88e`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x18000b88e`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18000b8a2`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18000b8a2`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLocaleName` at `0x18000b846`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLocaleName` at `0x18000b846`
- `api-ms-win-core-localization-l1-2-2!GetSystemDefaultLocaleName` at `0x18000b86f`
- `api-ms-win-core-localization-l1-2-2!GetSystemDefaultLocaleName` at `0x18000b86f`

## pseudocode

```c
void __fastcall CloudExperienceHostCoreTelemetry::GlobalizationState_(
        CloudExperienceHostCoreTelemetry *this,
        const char *a2)
{
  int UserDefaultLocaleName; // eax
  unsigned __int64 v4; // r8
  int SystemDefaultLocaleName; // eax
  unsigned __int64 v6; // r8
  LANGID ThreadUILanguage; // ax
  int LocaleInfoW; // eax
  unsigned __int64 v9; // r8
  GEOID UserGeoID; // eax
  const struct _tlgProvider_t *v11; // rax
  int v12; // r8d
  int v13; // r9d
  __int64 v14; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR *v15; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR *v16; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR *v17; // [rsp+68h] [rbp-98h] BYREF
  WCHAR *v18; // [rsp+70h] [rbp-90h] BYREF
  const char *v19; // [rsp+78h] [rbp-88h] BYREF
  WCHAR GeoData[2]; // [rsp+80h] [rbp-80h] BYREF
  __int16 v21; // [rsp+84h] [rbp-7Ch]
  WCHAR LCData[88]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR v23[88]; // [rsp+140h] [rbp+40h] BYREF
  WCHAR LocaleName[88]; // [rsp+1F0h] [rbp+F0h] BYREF

  memset_0(LocaleName, 0, 0xAAu);
  UserDefaultLocaleName = GetUserDefaultLocaleName(LocaleName, 85);
  CloudExperienceHostCoreTelemetry::PrintLastErrorIfZero(UserDefaultLocaleName, LocaleName, v4);
  memset_0(v23, 0, 0xAAu);
  SystemDefaultLocaleName = GetSystemDefaultLocaleName(v23, 85);
  CloudExperienceHostCoreTelemetry::PrintLastErrorIfZero(SystemDefaultLocaleName, v23, v6);
  memset_0(LCData, 0, 0xAAu);
  ThreadUILanguage = GetThreadUILanguage();
  LocaleInfoW = GetLocaleInfoW(ThreadUILanguage, 0x5Cu, LCData, 85);
  CloudExperienceHostCoreTelemetry::PrintLastErrorIfZero(LocaleInfoW, LCData, v9);
  *(_DWORD *)GeoData = 0;
  v21 = 0;
  UserGeoID = GetUserGeoID(0x10u);
  GetGeoInfoW(UserGeoID, 4u, GeoData, 3, 0);
  v11 = CloudExperienceHostCoreLogging::Provider();
  if ( *(_DWORD *)v11 > 5u )
  {
    if ( (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL, v11) )
    {
      v14 = 0x1000000;
      v15 = GeoData;
      v19 = a2;
      v16 = LCData;
      v17 = v23;
      v18 = LocaleName;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        v12,
        (unsigned int)word_18009B502,
        v12,
        v13,
        (__int64)&v19,
        (__int64)&v18,
        (__int64)&v17,
        (__int64)&v16,
        (__int64)&v15,
        (__int64)&v14);
    }
  }
}

```

## disassembly

```asm
0x18000b7f8  mov     [rsp-8+arg_0], rbx
0x18000b7fd  mov     [rsp-8+arg_8], rdi
0x18000b802  push    rbp
0x18000b803  lea     rbp, [rsp-1B0h]
0x18000b80b  sub     rsp, 2B0h
0x18000b812  mov     rax, cs:__security_cookie
0x18000b819  xor     rax, rsp
0x18000b81c  mov     [rbp+1B0h+var_10], rax
0x18000b823  mov     rdi, rdx
0x18000b826  lea     rcx, [rbp+1B0h+LocaleName]; void *
0x18000b82d  mov     ebx, 0AAh
0x18000b832  xor     edx, edx; Val
0x18000b834  mov     r8d, ebx; Size
0x18000b837  call    memset_0
0x18000b83c  lea     edx, [rbx-55h]; cchLocaleName
0x18000b83f  lea     rcx, [rbp+1B0h+LocaleName]; lpLocaleName
0x18000b846  call    cs:__imp_GetUserDefaultLocaleName
0x18000b84c  mov     ecx, eax; int
0x18000b84e  lea     rdx, [rbp+1B0h+LocaleName]; unsigned __int16 *
0x18000b855  call    ?PrintLastErrorIfZero@CloudExperienceHostCoreTelemetry@@CAXHPEAG_K@Z; CloudExperienceHostCoreTelemetry::PrintLastErrorIfZero(int,ushort *,unsigned __int64)
0x18000b85a  mov     r8d, ebx; Size
0x18000b85d  lea     rcx, [rbp+1B0h+var_170]; void *
0x18000b861  xor     edx, edx; Val
0x18000b863  call    memset_0
0x18000b868  lea     edx, [rbx-55h]; cchLocaleName
0x18000b86b  lea     rcx, [rbp+1B0h+var_170]; lpLocaleName
0x18000b86f  call    cs:__imp_GetSystemDefaultLocaleName
0x18000b875  mov     ecx, eax; int
0x18000b877  lea     rdx, [rbp+1B0h+var_170]; unsigned __int16 *
0x18000b87b  call    ?PrintLastErrorIfZero@CloudExperienceHostCoreTelemetry@@CAXHPEAG_K@Z; CloudExperienceHostCoreTelemetry::PrintLastErrorIfZero(int,ushort *,unsigned __int64)
0x18000b880  mov     r8d, ebx; Size
0x18000b883  lea     rcx, [rbp+1B0h+LCData]; void *
0x18000b887  xor     edx, edx; Val
0x18000b889  call    memset_0
0x18000b88e  call    cs:__imp_GetThreadUILanguage
0x18000b894  movzx   ecx, ax; Locale
0x18000b897  lea     r9d, [rbx-55h]; cchData
0x18000b89b  lea     r8, [rbp+1B0h+LCData]; lpLCData
0x18000b89f  lea     edx, [rbx-4Eh]; LCType
0x18000b8a2  call    cs:__imp_GetLocaleInfoW
0x18000b8a8  mov     ecx, eax; int
0x18000b8aa  lea     rdx, [rbp+1B0h+LCData]; unsigned __int16 *
0x18000b8ae  call    ?PrintLastErrorIfZero@CloudExperienceHostCoreTelemetry@@CAXHPEAG_K@Z; CloudExperienceHostCoreTelemetry::PrintLastErrorIfZero(int,ushort *,unsigned __int64)
0x18000b8b3  xor     eax, eax
0x18000b8b5  xor     ebx, ebx
0x18000b8b7  mov     dword ptr [rbp+1B0h+GeoData], eax
0x18000b8ba  mov     [rbp+1B0h+var_22C], ax
0x18000b8be  lea     ecx, [rax+10h]; GeoClass
0x18000b8c1  call    cs:__imp_GetUserGeoID
0x18000b8c7  lea     r9d, [rbx+3]; cchData
0x18000b8cb  mov     [rsp+2B0h+LangId], bx; LangId
0x18000b8d0  mov     ecx, eax; Location
0x18000b8d2  lea     r8, [rbp+1B0h+GeoData]; lpGeoData
0x18000b8d6  lea     edx, [rbx+4]; GeoType
0x18000b8d9  call    cs:__imp_GetGeoInfoW
0x18000b8df  call    ?Provider@CloudExperienceHostCoreLogging@@SAPEBU_tlgProvider_t@@XZ; CloudExperienceHostCoreLogging::Provider(void)
0x18000b8e4  mov     r8, rax
0x18000b8e7  mov     ecx, [rax]
0x18000b8e9  cmp     ecx, 5
0x18000b8ec  jbe     loc_18000B98C
0x18000b8f2  mov     rdx, 400000000000h
0x18000b8fc  mov     rcx, rax
0x18000b8ff  call    _tlgKeywordOn
0x18000b904  test    al, al
0x18000b906  jz      loc_18000B98C
0x18000b90c  lea     rax, [rbp+1B0h+GeoData]
0x18000b910  mov     [rsp+2B0h+var_260], 1000000h
0x18000b919  mov     [rsp+2B0h+var_258], rax
0x18000b91e  lea     rdx, word_18009B502
0x18000b925  lea     rax, [rbp+1B0h+LCData]
0x18000b929  mov     [rsp+2B0h+var_238], rdi
0x18000b92e  mov     [rsp+2B0h+var_250], rax
0x18000b933  mov     rcx, r8
0x18000b936  lea     rax, [rbp+1B0h+var_170]
0x18000b93a  mov     [rsp+2B0h+var_248], rax
0x18000b93f  lea     rax, [rbp+1B0h+LocaleName]
0x18000b946  mov     [rsp+2B0h+var_240], rax
0x18000b94b  lea     rax, [rsp+2B0h+var_260]
0x18000b950  mov     [rsp+2B0h+var_268], rax
0x18000b955  lea     rax, [rsp+2B0h+var_258]
0x18000b95a  mov     [rsp+2B0h+var_270], rax
0x18000b95f  lea     rax, [rsp+2B0h+var_250]
0x18000b964  mov     [rsp+2B0h+var_278], rax
0x18000b969  lea     rax, [rsp+2B0h+var_248]
0x18000b96e  mov     [rsp+2B0h+var_280], rax
0x18000b973  lea     rax, [rsp+2B0h+var_240]
0x18000b978  mov     [rsp+2B0h+var_288], rax
0x18000b97d  lea     rax, [rsp+2B0h+var_238]
0x18000b982  mov     qword ptr [rsp+2B0h+LangId], rax
0x18000b987  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U2@U2@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@444AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x18000b98c  mov     rcx, [rbp+1B0h+var_10]
0x18000b993  xor     rcx, rsp; StackCookie
0x18000b996  call    __security_check_cookie
0x18000b99b  lea     r11, [rsp+2B0h+var_s0]
0x18000b9a3  mov     rbx, [r11+10h]
0x18000b9a7  mov     rdi, [r11+18h]
0x18000b9ab  mov     rsp, r11
0x18000b9ae  pop     rbp
0x18000b9af  retn
```
