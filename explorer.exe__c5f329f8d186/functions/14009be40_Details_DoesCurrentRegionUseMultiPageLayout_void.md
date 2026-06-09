# Details::DoesCurrentRegionUseMultiPageLayout(void)

- ea: `0x14009be40`
- end: `0x14009c520`
- name: `?DoesCurrentRegionUseMultiPageLayout@Details@@YA_NXZ`
- size: `1760`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14019c1cc`

## callees

- `0x14006626c`
- `0x140082820`
- `0x14009ac68`
- `0x14009be40`
- `0x14010e160`
- `0x1401a40ac`
- `0x1401a40e8`
- `0x1401d9010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14009c306`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14009c395`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14009c483`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14009c306`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14009c395`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14009c483`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14009c2e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14009c376`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14009c464`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14009c2e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14009c376`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14009c464`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14009bef1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14009bf37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14009c322`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14009c3b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14009c49f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14009c4d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14009bef1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14009bf37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14009c322`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14009c3b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14009c49f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14009c4d5`

## string_xrefs

- `0x14009beaf`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\PrivacyConsentPolicy.h`
- `0x14009bf20`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\PrivacyConsentPolicy.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char Details::DoesCurrentRegionUseMultiPageLayout(void)
{
  int v0; // eax
  __int64 v1; // rcx
  void (*v2)(void); // rax
  __int64 v3; // rdi
  __int64 (__fastcall *v4)(__int64, HSTRING *); // rbx
  int v5; // eax
  LPCWCH *i; // rbx
  const WCHAR *StringRawBuffer; // rax
  LPCWCH *j; // rbx
  const WCHAR *v9; // rax
  LPCWCH *k; // rbx
  const WCHAR *v11; // rax
  __int64 v12; // rcx
  __int64 v14; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-E0h]
  HSTRING string; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v17; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v18[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v19[10]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v20[70]; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+2D0h] [rbp+1D0h] BYREF
  __int64 v22; // [rsp+2E8h] [rbp+1E8h]
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+228h]

  v17 = 0;
  v22 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Globalization.GeographicRegion",
    0x27u,
    0x26u);
  v0 = Windows::Foundation::ActivateInstance<Windows::Globalization::IGeographicRegion>(v22, &v17);
  if ( v0 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\PrivacyConsentPolicy.h",
      (const char *)(unsigned int)v0,
      bIgnoreCase);
LABEL_3:
    v1 = v17;
    if ( v17 )
    {
      v17 = 0;
      v2 = *(void (**)(void))(*(_QWORD *)v1 + 16LL);
LABEL_25:
      v2();
    }
    return 1;
  }
  string = 0;
  v3 = v17;
  v4 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v17 + 64LL);
  WindowsDeleteString(0);
  string = 0;
  v5 = v4(v3, &string);
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4E,
      (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\PrivacyConsentPolicy.h",
      (const char *)(unsigned int)v5,
      bIgnoreCase);
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_3;
  }
  v20[0] = L"AT";
  v20[1] = L"AUT";
  v20[2] = L"BE";
  v20[3] = L"BEL";
  v20[4] = L"BG";
  v20[5] = L"BGR";
  v20[6] = L"BR";
  v20[7] = L"BRA";
  v20[8] = L"CA";
  v20[9] = L"CAN";
  v20[10] = L"HR";
  v20[11] = L"HRV";
  v20[12] = L"CY";
  v20[13] = L"CYP";
  v20[14] = L"CZ";
  v20[15] = L"CZE";
  v20[16] = L"DK";
  v20[17] = L"DNK";
  v20[18] = L"EE";
  v20[19] = L"EST";
  v20[20] = L"FI";
  v20[21] = L"FIN";
  v20[22] = L"FR";
  v20[23] = L"FRA";
  v20[24] = L"DE";
  v20[25] = L"DEU";
  v20[26] = L"GR";
  v20[27] = L"GRC";
  v20[28] = L"HU";
  v20[29] = L"HUN";
  v20[30] = L"IS";
  v20[31] = L"ISL";
  v20[32] = L"IE";
  v20[33] = L"IRL";
  v20[34] = L"IT";
  v20[35] = L"ITA";
  v20[36] = L"KR";
  v20[37] = L"KOR";
  v20[38] = L"LV";
  v20[39] = L"LVA";
  v20[40] = L"LI";
  v20[41] = L"LIE";
  v20[42] = L"LT";
  v20[43] = L"LTU";
  v20[44] = L"LU";
  v20[45] = L"LUX";
  v20[46] = L"MT";
  v20[47] = L"MLT";
  v20[48] = L"NL";
  v20[49] = L"NLD";
  v20[50] = L"NO";
  v20[51] = L"NOR";
  v20[52] = L"PL";
  v20[53] = L"POL";
  v20[54] = L"PT";
  v20[55] = L"PRT";
  v20[56] = L"RO";
  v20[57] = L"ROU";
  v20[58] = L"SK";
  v20[59] = L"SVK";
  v20[60] = L"SI";
  v20[61] = L"SVN";
  v20[62] = L"ES";
  v20[63] = L"ESP";
  v20[64] = L"SE";
  v20[65] = L"SWE";
  v20[66] = L"CH";
  v20[67] = L"CHE";
  v20[68] = L"GB";
  v20[69] = L"GBR";
  for ( i = (LPCWCH *)v20; i != (LPCWCH *)&hstringHeader; ++i )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    if ( CompareStringOrdinal(StringRawBuffer, -1, *i, -1, 1) == 2 )
    {
LABEL_11:
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_3;
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NewMultiPagePrivacy>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NewMultiPagePrivacy>::GetImpl'::`2'::impl) )
  {
    v18[0] = L"VN";
    v18[1] = L"VNM";
    for ( j = (LPCWCH *)v18; j != v19; ++j )
    {
      v9 = WindowsGetStringRawBuffer(string, 0);
      if ( CompareStringOrdinal(v9, -1, *j, -1, 1) == 2 )
        goto LABEL_11;
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MissingMultiPagePrivacy>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MissingMultiPagePrivacy>::GetImpl'::`2'::impl) )
  {
    v19[0] = L"GF";
    v19[1] = L"GUF";
    v19[2] = L"GP";
    v19[3] = L"GLP";
    v19[4] = L"MQ";
    v19[5] = L"MTQ";
    v19[6] = L"RE";
    v19[7] = L"REU";
    v19[8] = L"YT";
    v19[9] = L"MYT";
    for ( k = (LPCWCH *)v19; k != v20; ++k )
    {
      v11 = WindowsGetStringRawBuffer(string, 0);
      if ( CompareStringOrdinal(v11, -1, *k, -1, 1) == 2 )
      {
        WindowsDeleteString(string);
        string = 0;
        v12 = v17;
        if ( !v17 )
          return 1;
        v17 = 0;
        v2 = *(void (**)(void))(*(_QWORD *)v12 + 16LL);
        goto LABEL_25;
      }
    }
  }
  WindowsDeleteString(string);
  string = 0;
  v14 = v17;
  if ( v17 )
  {
    v17 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  return 0;
}

```

## disassembly

```asm
0x14009be40  push    rbp
0x14009be42  push    rbx
0x14009be43  push    rsi
0x14009be44  push    rdi
0x14009be45  lea     rbp, [rsp-208h]
0x14009be4d  sub     rsp, 308h
0x14009be54  mov     rax, cs:__security_cookie
0x14009be5b  xor     rax, rsp
0x14009be5e  mov     [rbp+220h+var_30], rax
0x14009be65  xor     esi, esi
0x14009be67  mov     [rsp+320h+var_2E8], rsi
0x14009be6c  mov     [rbp+220h+var_38], rsi
0x14009be73  lea     r9d, [rsi+26h]; unsigned int
0x14009be77  lea     r8d, [rsi+27h]; unsigned int
0x14009be7b  lea     rdx, ?RuntimeClass_Windows_Globalization_GeographicRegion@@3QBGB; "Windows.Globalization.GeographicRegion"
0x14009be82  lea     rcx, [rbp+220h+hstringHeader]; hstringHeader
0x14009be89  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x14009be8e  nop
0x14009be8f  lea     rdx, [rsp+320h+var_2E8]
0x14009be94  mov     rcx, [rbp+220h+var_38]
0x14009be9b  call    ??$ActivateInstance@UIGeographicRegion@Globalization@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIGeographicRegion@Globalization@1@@Z; Windows::Foundation::ActivateInstance<Windows::Globalization::IGeographicRegion>(HSTRING__ *,Windows::Globalization::IGeographicRegion * *)
0x14009bea0  nop
0x14009bea1  test    eax, eax
0x14009bea3  jns     short loc_14009BEDE
0x14009bea5  mov     rcx, [rbp+228h]; this
0x14009beac  mov     r9d, eax; char *
0x14009beaf  lea     r8, aShellcommondes_4; "ShellCommonDesktopBase\\Internal\\Shell"...
0x14009beb6  lea     edx, [rsi+4Bh]; void *
0x14009beb9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14009bebe  nop
0x14009bebf  mov     rcx, [rsp+320h+var_2E8]
0x14009bec4  test    rcx, rcx
0x14009bec7  jz      loc_14009C4CC
0x14009becd  mov     [rsp+320h+var_2E8], rsi
0x14009bed2  mov     rax, [rcx]
0x14009bed5  mov     rax, [rax+10h]
0x14009bed9  jmp     loc_14009C4C6
0x14009bede  mov     [rsp+320h+string], rsi
0x14009bee3  mov     rdi, [rsp+320h+var_2E8]
0x14009bee8  mov     rax, [rdi]
0x14009beeb  mov     rbx, [rax+40h]
0x14009beef  xor     ecx, ecx; string
0x14009bef1  call    cs:__imp_WindowsDeleteString
0x14009bef8  nop     dword ptr [rax+rax+00h]
0x14009befd  mov     [rsp+320h+string], rsi
0x14009bf02  lea     rdx, [rsp+320h+string]
0x14009bf07  mov     rcx, rdi
0x14009bf0a  mov     rax, rbx
0x14009bf0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009bf12  test    eax, eax
0x14009bf14  jns     short loc_14009BF4D
0x14009bf16  mov     rcx, [rbp+228h]; this
0x14009bf1d  mov     r9d, eax; char *
0x14009bf20  lea     r8, aShellcommondes_4; "ShellCommonDesktopBase\\Internal\\Shell"...
0x14009bf27  mov     edx, 4Eh ; 'N'; void *
0x14009bf2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14009bf31  nop
0x14009bf32  mov     rcx, [rsp+320h+string]; string
0x14009bf37  call    cs:__imp_WindowsDeleteString
0x14009bf3e  nop     dword ptr [rax+rax+00h]
0x14009bf43  mov     [rsp+320h+string], rsi
0x14009bf48  jmp     loc_14009BEBF
0x14009bf4d  lea     rax, aAt; "AT"
0x14009bf54  mov     [rbp+220h+var_280], rax
0x14009bf58  lea     rax, aAut; "AUT"
0x14009bf5f  mov     [rbp+220h+var_278], rax
0x14009bf63  lea     rax, aBe; "BE"
0x14009bf6a  mov     [rbp+220h+var_270], rax
0x14009bf6e  lea     rax, aBel; "BEL"
0x14009bf75  mov     [rbp+220h+var_268], rax
0x14009bf79  lea     rax, aBg; "BG"
0x14009bf80  mov     [rbp+220h+var_260], rax
0x14009bf84  lea     rax, aBgr; "BGR"
0x14009bf8b  mov     [rbp+220h+var_258], rax
0x14009bf8f  lea     rax, aBr; "BR"
0x14009bf96  mov     [rbp+220h+var_250], rax
0x14009bf9a  lea     rax, aBra; "BRA"
0x14009bfa1  mov     [rbp+220h+var_248], rax
0x14009bfa5  lea     rax, aCa; "CA"
0x14009bfac  mov     [rbp+220h+var_240], rax
0x14009bfb0  lea     rax, aCan; "CAN"
0x14009bfb7  mov     [rbp+220h+var_238], rax
0x14009bfbb  lea     rax, aHr; "HR"
0x14009bfc2  mov     [rbp+220h+var_230], rax
0x14009bfc6  lea     rax, aHrv; "HRV"
0x14009bfcd  mov     [rbp+220h+var_228], rax
0x14009bfd1  lea     rax, aCy; "CY"
0x14009bfd8  mov     [rbp+220h+var_220], rax
0x14009bfdc  lea     rax, aCyp; "CYP"
0x14009bfe3  mov     [rbp+220h+var_218], rax
0x14009bfe7  lea     rax, aCz; "CZ"
0x14009bfee  mov     [rbp+220h+var_210], rax
0x14009bff2  lea     rax, aCze; "CZE"
0x14009bff9  mov     [rbp+220h+var_208], rax
0x14009bffd  lea     rax, aDk; "DK"
0x14009c004  mov     [rbp+220h+var_200], rax
0x14009c008  lea     rax, aDnk; "DNK"
0x14009c00f  mov     [rbp+220h+var_1F8], rax
0x14009c013  lea     rax, aEe; "EE"
0x14009c01a  mov     [rbp+220h+var_1F0], rax
0x14009c01e  lea     rax, aEst; "EST"
0x14009c025  mov     [rbp+220h+var_1E8], rax
0x14009c029  lea     rax, aFi; "FI"
0x14009c030  mov     [rbp+220h+var_1E0], rax
0x14009c034  lea     rax, aFin; "FIN"
0x14009c03b  mov     [rbp+220h+var_1D8], rax
0x14009c03f  lea     rax, aFr; "FR"
0x14009c046  mov     [rbp+220h+var_1D0], rax
0x14009c04a  lea     rax, aFra; "FRA"
0x14009c051  mov     [rbp+220h+var_1C8], rax
0x14009c055  lea     rax, aDe; "DE"
0x14009c05c  mov     [rbp+220h+var_1C0], rax
0x14009c060  lea     rax, aDeu; "DEU"
0x14009c067  mov     [rbp+220h+var_1B8], rax
0x14009c06b  lea     rax, aGr; "GR"
0x14009c072  mov     [rbp+220h+var_1B0], rax
0x14009c076  lea     rax, aGrc; "GRC"
0x14009c07d  mov     [rbp+220h+var_1A8], rax
0x14009c081  lea     rax, aHu; "HU"
0x14009c088  mov     [rbp+220h+var_1A0], rax
0x14009c08f  lea     rax, aHun; "HUN"
0x14009c096  mov     [rbp+220h+var_198], rax
0x14009c09d  lea     rax, aIs; "IS"
0x14009c0a4  mov     [rbp+220h+var_190], rax
0x14009c0ab  lea     rax, aIsl; "ISL"
0x14009c0b2  mov     [rbp+220h+var_188], rax
0x14009c0b9  lea     rax, aIe; "IE"
0x14009c0c0  mov     [rbp+220h+var_180], rax
0x14009c0c7  lea     rax, aIrl; "IRL"
0x14009c0ce  mov     [rbp+220h+var_178], rax
0x14009c0d5  lea     rax, aIt; "IT"
0x14009c0dc  mov     [rbp+220h+var_170], rax
0x14009c0e3  lea     rax, aIta; "ITA"
0x14009c0ea  mov     [rbp+220h+var_168], rax
0x14009c0f1  lea     rax, aKr; "KR"
0x14009c0f8  mov     [rbp+220h+var_160], rax
0x14009c0ff  lea     rax, aKor; "KOR"
0x14009c106  mov     [rbp+220h+var_158], rax
0x14009c10d  lea     rax, aLv; "LV"
0x14009c114  mov     [rbp+220h+var_150], rax
0x14009c11b  lea     rax, aLva; "LVA"
0x14009c122  mov     [rbp+220h+var_148], rax
0x14009c129  lea     rax, aLi; "LI"
0x14009c130  mov     [rbp+220h+var_140], rax
0x14009c137  lea     rax, aLie; "LIE"
0x14009c13e  mov     [rbp+220h+var_138], rax
0x14009c145  lea     rax, aLt; "LT"
0x14009c14c  mov     [rbp+220h+var_130], rax
0x14009c153  lea     rax, aLtu; "LTU"
0x14009c15a  mov     [rbp+220h+var_128], rax
0x14009c161  lea     rax, aLu; "LU"
0x14009c168  mov     [rbp+220h+var_120], rax
0x14009c16f  lea     rax, aLux; "LUX"
0x14009c176  mov     [rbp+220h+var_118], rax
0x14009c17d  lea     rax, aMt; "MT"
0x14009c184  mov     [rbp+220h+var_110], rax
0x14009c18b  lea     rax, aMlt; "MLT"
0x14009c192  mov     [rbp+220h+var_108], rax
0x14009c199  lea     rax, aNl; "NL"
0x14009c1a0  mov     [rbp+220h+var_100], rax
0x14009c1a7  lea     rax, aNld; "NLD"
0x14009c1ae  mov     [rbp+220h+var_F8], rax
0x14009c1b5  lea     rax, aNo; "NO"
0x14009c1bc  mov     [rbp+220h+var_F0], rax
0x14009c1c3  lea     rax, aNor; "NOR"
0x14009c1ca  mov     [rbp+220h+var_E8], rax
0x14009c1d1  lea     rax, aPl; "PL"
0x14009c1d8  mov     [rbp+220h+var_E0], rax
0x14009c1df  lea     rax, aPol; "POL"
0x14009c1e6  mov     [rbp+220h+var_D8], rax
0x14009c1ed  lea     rax, aPt; "PT"
0x14009c1f4  mov     [rbp+220h+var_D0], rax
0x14009c1fb  lea     rax, aPrt; "PRT"
0x14009c202  mov     [rbp+220h+var_C8], rax
0x14009c209  lea     rax, aRo; "RO"
0x14009c210  mov     [rbp+220h+var_C0], rax
0x14009c217  lea     rax, aRou; "ROU"
0x14009c21e  mov     [rbp+220h+var_B8], rax
0x14009c225  lea     rax, aSk; "SK"
0x14009c22c  mov     [rbp+220h+var_B0], rax
0x14009c233  lea     rax, aSvk; "SVK"
0x14009c23a  mov     [rbp+220h+var_A8], rax
0x14009c241  lea     rax, aSi; "SI"
0x14009c248  mov     [rbp+220h+var_A0], rax
0x14009c24f  lea     rax, aSvn; "SVN"
0x14009c256  mov     [rbp+220h+var_98], rax
0x14009c25d  lea     rax, aEs; "ES"
0x14009c264  mov     [rbp+220h+var_90], rax
0x14009c26b  lea     rax, aEsp; "ESP"
0x14009c272  mov     [rbp+220h+var_88], rax
0x14009c279  lea     rax, aSe; "SE"
0x14009c280  mov     [rbp+220h+var_80], rax
0x14009c287  lea     rax, aSwe; "SWE"
0x14009c28e  mov     [rbp+220h+var_78], rax
0x14009c295  lea     rax, aCh; "CH"
0x14009c29c  mov     [rbp+220h+var_70], rax
0x14009c2a3  lea     rax, aChe; "CHE"
0x14009c2aa  mov     [rbp+220h+var_68], rax
0x14009c2b1  lea     rax, aGb; "GB"
0x14009c2b8  mov     [rbp+220h+var_60], rax
0x14009c2bf  lea     rax, aGbr; "GBR"
0x14009c2c6  mov     [rbp+220h+var_58], rax
0x14009c2cd  lea     rbx, [rbp+220h+var_280]
0x14009c2d1  or      edi, 0FFFFFFFFh
0x14009c2d4  lea     rax, [rbp+220h+hstringHeader]
0x14009c2db  cmp     rbx, rax
0x14009c2de  jz      short loc_14009C338
0x14009c2e0  xor     edx, edx; length
0x14009c2e2  mov     rcx, [rsp+320h+string]; string
0x14009c2e7  call    cs:__imp_WindowsGetStringRawBuffer
0x14009c2ee  nop     dword ptr [rax+rax+00h]
0x14009c2f3  mov     [rsp+320h+bIgnoreCase], 1; bIgnoreCase
0x14009c2fb  mov     r9d, edi; cchCount2
0x14009c2fe  mov     r8, [rbx]; lpString2
0x14009c301  mov     edx, edi; cchCount1
0x14009c303  mov     rcx, rax; lpString1
0x14009c306  call    cs:__imp_CompareStringOrdinal
0x14009c30d  nop     dword ptr [rax+rax+00h]
0x14009c312  cmp     eax, 2
0x14009c315  jz      short loc_14009C31D
0x14009c317  add     rbx, 8
0x14009c31b  jmp     short loc_14009C2D4
0x14009c31d  mov     rcx, [rsp+320h+string]; string
0x14009c322  call    cs:__imp_WindowsDeleteString
0x14009c329  nop     dword ptr [rax+rax+00h]
0x14009c32e  mov     [rsp+320h+string], rsi
0x14009c333  jmp     loc_14009BEBF
0x14009c338  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NewMultiPagePrivacy@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NewMultiPagePrivacy@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NewMultiPagePrivacy> `wil::Feature<__WilFeatureTraits_Feature_NewMultiPagePrivacy>::GetImpl(void)'::`2'::impl
0x14009c33f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NewMultiPagePrivacy@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NewMultiPagePrivacy>::__private_IsEnabled(void)
0x14009c344  test    al, al
0x14009c346  jz      short loc_14009C3C7
0x14009c348  lea     rax, aVn; "VN"
0x14009c34f  mov     [rsp+320h+var_2E0], rax
0x14009c354  lea     rax, aVnm; "VNM"
0x14009c35b  mov     [rsp+320h+var_2D8], rax
0x14009c360  lea     rbx, [rsp+320h+var_2E0]
0x14009c365  lea     rax, [rsp+320h+var_2D0]
0x14009c36a  cmp     rbx, rax
0x14009c36d  jz      short loc_14009C3C7
0x14009c36f  xor     edx, edx; length
0x14009c371  mov     rcx, [rsp+320h+string]; string
0x14009c376  call    cs:__imp_WindowsGetStringRawBuffer
0x14009c37d  nop     dword ptr [rax+rax+00h]
0x14009c382  mov     [rsp+320h+bIgnoreCase], 1; bIgnoreCase
0x14009c38a  mov     r9d, edi; cchCount2
0x14009c38d  mov     r8, [rbx]; lpString2
0x14009c390  mov     edx, edi; cchCount1
0x14009c392  mov     rcx, rax; lpString1
0x14009c395  call    cs:__imp_CompareStringOrdinal
0x14009c39c  nop     dword ptr [rax+rax+00h]
0x14009c3a1  cmp     eax, 2
0x14009c3a4  jz      short loc_14009C3AC
0x14009c3a6  add     rbx, 8
0x14009c3aa  jmp     short loc_14009C365
0x14009c3ac  mov     rcx, [rsp+320h+string]; string
0x14009c3b1  call    cs:__imp_WindowsDeleteString
0x14009c3b8  nop     dword ptr [rax+rax+00h]
0x14009c3bd  mov     [rsp+320h+string], rsi
0x14009c3c2  jmp     loc_14009BEBF
0x14009c3c7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MissingMultiPagePrivacy@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MissingMultiPagePrivacy@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MissingMultiPagePrivacy> `wil::Feature<__WilFeatureTraits_Feature_MissingMultiPagePrivacy>::GetImpl(void)'::`2'::impl
0x14009c3ce  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MissingMultiPagePrivacy@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MissingMultiPagePrivacy>::__private_IsEnabled(void)
0x14009c3d3  test    al, al
0x14009c3d5  jz      loc_14009C4D0
0x14009c3db  lea     rax, aGf; "GF"
0x14009c3e2  mov     [rsp+320h+var_2D0], rax
0x14009c3e7  lea     rax, aGuf; "GUF"
0x14009c3ee  mov     [rsp+320h+var_2C8], rax
0x14009c3f3  lea     rax, aGp; "GP"
0x14009c3fa  mov     [rsp+320h+var_2C0], rax
0x14009c3ff  lea     rax, aGlp; "GLP"
0x14009c406  mov     [rsp+320h+var_2B8], rax
0x14009c40b  lea     rax, aMq; "MQ"
0x14009c412  mov     [rsp+320h+var_2B0], rax
0x14009c417  lea     rax, aMtq; "MTQ"
0x14009c41e  mov     [rsp+320h+var_2A8], rax
0x14009c423  lea     rax, aRe; "RE"
0x14009c42a  mov     [rbp+220h+var_2A0], rax
0x14009c42e  lea     rax, aReu; "REU"
0x14009c435  mov     [rbp+220h+var_298], rax
0x14009c439  lea     rax, aYt; "YT"
0x14009c440  mov     [rbp+220h+var_290], rax
0x14009c444  lea     rax, aMyt; "MYT"
0x14009c44b  mov     [rbp+220h+var_288], rax
0x14009c44f  lea     rbx, [rsp+320h+var_2D0]
0x14009c454  lea     rax, [rbp+220h+var_280]
0x14009c458  cmp     rbx, rax
0x14009c45b  jz      short loc_14009C4D0
0x14009c45d  xor     edx, edx; length
0x14009c45f  mov     rcx, [rsp+320h+string]; string
0x14009c464  call    cs:__imp_WindowsGetStringRawBuffer
0x14009c46b  nop     dword ptr [rax+rax+00h]
0x14009c470  mov     [rsp+320h+bIgnoreCase], 1; bIgnoreCase
0x14009c478  mov     r9d, edi; cchCount2
0x14009c47b  mov     r8, [rbx]; lpString2
0x14009c47e  mov     edx, edi; cchCount1
0x14009c480  mov     rcx, rax; lpString1
0x14009c483  call    cs:__imp_CompareStringOrdinal
0x14009c48a  nop     dword ptr [rax+rax+00h]
0x14009c48f  cmp     eax, 2
0x14009c492  jz      short loc_14009C49A
  ... truncated ...
```
