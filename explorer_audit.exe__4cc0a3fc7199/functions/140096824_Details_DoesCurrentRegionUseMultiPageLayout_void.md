# Details::DoesCurrentRegionUseMultiPageLayout(void)

- ea: `0x140096824`
- end: `0x140096eb8`
- name: `?DoesCurrentRegionUseMultiPageLayout@Details@@YA_NXZ`
- size: `1684`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14018f948`

## callees

- `0x1400629f4`
- `0x14007ce08`
- `0x1400954e0`
- `0x140096824`
- `0x1401040e0`
- `0x1401a1d04`
- `0x1401a1d40`
- `0x1401db010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140096cd5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140096d52`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140096e2e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140096cd5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140096d52`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140096e2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140096cbc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140096d39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140096e15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140096cbc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140096d39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140096e15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400968d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140096915`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140096ceb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140096d68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140096e44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140096e74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400968d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140096915`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140096ceb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140096d68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140096e44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140096e74`

## string_xrefs

- `0x140096893`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\PrivacyConsentPolicy.h`
- `0x1400968fe`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\PrivacyConsentPolicy.h`

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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NewMultiPagePrivacy>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_NewMultiPagePrivacy>::GetImpl'::`2'::impl) )
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MissingMultiPagePrivacy>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_MissingMultiPagePrivacy>::GetImpl'::`2'::impl) )
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
0x140096824  push    rbp
0x140096826  push    rbx
0x140096827  push    rsi
0x140096828  push    rdi
0x140096829  lea     rbp, [rsp-208h]
0x140096831  sub     rsp, 308h
0x140096838  mov     rax, cs:__security_cookie
0x14009683f  xor     rax, rsp
0x140096842  mov     [rbp+220h+var_30], rax
0x140096849  xor     esi, esi
0x14009684b  mov     [rsp+320h+var_2E8], rsi
0x140096850  mov     [rbp+220h+var_38], rsi
0x140096857  lea     r9d, [rsi+26h]; unsigned int
0x14009685b  lea     r8d, [rsi+27h]; unsigned int
0x14009685f  lea     rdx, ?RuntimeClass_Windows_Globalization_GeographicRegion@@3QBGB; "Windows.Globalization.GeographicRegion"
0x140096866  lea     rcx, [rbp+220h+hstringHeader]; hstringHeader
0x14009686d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x140096872  nop
0x140096873  lea     rdx, [rsp+320h+var_2E8]
0x140096878  mov     rcx, [rbp+220h+var_38]
0x14009687f  call    ??$ActivateInstance@UIGeographicRegion@Globalization@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIGeographicRegion@Globalization@1@@Z; Windows::Foundation::ActivateInstance<Windows::Globalization::IGeographicRegion>(HSTRING__ *,Windows::Globalization::IGeographicRegion * *)
0x140096884  nop
0x140096885  test    eax, eax
0x140096887  jns     short loc_1400968C2
0x140096889  mov     rcx, [rbp+228h]; this
0x140096890  mov     r9d, eax; char *
0x140096893  lea     r8, aShellcommondes_4; "ShellCommonDesktopBase\\Internal\\Shell"...
0x14009689a  lea     edx, [rsi+4Bh]; void *
0x14009689d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400968a2  nop
0x1400968a3  mov     rcx, [rsp+320h+var_2E8]
0x1400968a8  test    rcx, rcx
0x1400968ab  jz      loc_140096E6B
0x1400968b1  mov     [rsp+320h+var_2E8], rsi
0x1400968b6  mov     rax, [rcx]
0x1400968b9  mov     rax, [rax+10h]
0x1400968bd  jmp     loc_140096E65
0x1400968c2  mov     [rsp+320h+string], rsi
0x1400968c7  mov     rdi, [rsp+320h+var_2E8]
0x1400968cc  mov     rax, [rdi]
0x1400968cf  mov     rbx, [rax+40h]
0x1400968d3  xor     ecx, ecx; string
0x1400968d5  call    cs:__imp_WindowsDeleteString
0x1400968db  mov     [rsp+320h+string], rsi
0x1400968e0  lea     rdx, [rsp+320h+string]
0x1400968e5  mov     rcx, rdi
0x1400968e8  mov     rax, rbx
0x1400968eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400968f0  test    eax, eax
0x1400968f2  jns     short loc_140096922
0x1400968f4  mov     rcx, [rbp+228h]; this
0x1400968fb  mov     r9d, eax; char *
0x1400968fe  lea     r8, aShellcommondes_4; "ShellCommonDesktopBase\\Internal\\Shell"...
0x140096905  mov     edx, 4Eh ; 'N'; void *
0x14009690a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14009690f  nop
0x140096910  mov     rcx, [rsp+320h+string]; string
0x140096915  call    cs:__imp_WindowsDeleteString
0x14009691b  mov     [rsp+320h+string], rsi
0x140096920  jmp     short loc_1400968A3
0x140096922  lea     rax, aAt; "AT"
0x140096929  mov     [rbp+220h+var_280], rax
0x14009692d  lea     rax, aAut; "AUT"
0x140096934  mov     [rbp+220h+var_278], rax
0x140096938  lea     rax, aBe; "BE"
0x14009693f  mov     [rbp+220h+var_270], rax
0x140096943  lea     rax, aBel; "BEL"
0x14009694a  mov     [rbp+220h+var_268], rax
0x14009694e  lea     rax, aBg; "BG"
0x140096955  mov     [rbp+220h+var_260], rax
0x140096959  lea     rax, aBgr; "BGR"
0x140096960  mov     [rbp+220h+var_258], rax
0x140096964  lea     rax, aBr; "BR"
0x14009696b  mov     [rbp+220h+var_250], rax
0x14009696f  lea     rax, aBra; "BRA"
0x140096976  mov     [rbp+220h+var_248], rax
0x14009697a  lea     rax, aCa; "CA"
0x140096981  mov     [rbp+220h+var_240], rax
0x140096985  lea     rax, aCan; "CAN"
0x14009698c  mov     [rbp+220h+var_238], rax
0x140096990  lea     rax, aHr; "HR"
0x140096997  mov     [rbp+220h+var_230], rax
0x14009699b  lea     rax, aHrv; "HRV"
0x1400969a2  mov     [rbp+220h+var_228], rax
0x1400969a6  lea     rax, aCy; "CY"
0x1400969ad  mov     [rbp+220h+var_220], rax
0x1400969b1  lea     rax, aCyp; "CYP"
0x1400969b8  mov     [rbp+220h+var_218], rax
0x1400969bc  lea     rax, aCz; "CZ"
0x1400969c3  mov     [rbp+220h+var_210], rax
0x1400969c7  lea     rax, aCze; "CZE"
0x1400969ce  mov     [rbp+220h+var_208], rax
0x1400969d2  lea     rax, aDk; "DK"
0x1400969d9  mov     [rbp+220h+var_200], rax
0x1400969dd  lea     rax, aDnk; "DNK"
0x1400969e4  mov     [rbp+220h+var_1F8], rax
0x1400969e8  lea     rax, aEe; "EE"
0x1400969ef  mov     [rbp+220h+var_1F0], rax
0x1400969f3  lea     rax, aEst; "EST"
0x1400969fa  mov     [rbp+220h+var_1E8], rax
0x1400969fe  lea     rax, aFi; "FI"
0x140096a05  mov     [rbp+220h+var_1E0], rax
0x140096a09  lea     rax, aFin; "FIN"
0x140096a10  mov     [rbp+220h+var_1D8], rax
0x140096a14  lea     rax, aFr; "FR"
0x140096a1b  mov     [rbp+220h+var_1D0], rax
0x140096a1f  lea     rax, aFra; "FRA"
0x140096a26  mov     [rbp+220h+var_1C8], rax
0x140096a2a  lea     rax, aDe; "DE"
0x140096a31  mov     [rbp+220h+var_1C0], rax
0x140096a35  lea     rax, aDeu; "DEU"
0x140096a3c  mov     [rbp+220h+var_1B8], rax
0x140096a40  lea     rax, aGr; "GR"
0x140096a47  mov     [rbp+220h+var_1B0], rax
0x140096a4b  lea     rax, aGrc; "GRC"
0x140096a52  mov     [rbp+220h+var_1A8], rax
0x140096a56  lea     rax, aHu; "HU"
0x140096a5d  mov     [rbp+220h+var_1A0], rax
0x140096a64  lea     rax, aHun; "HUN"
0x140096a6b  mov     [rbp+220h+var_198], rax
0x140096a72  lea     rax, aIs; "IS"
0x140096a79  mov     [rbp+220h+var_190], rax
0x140096a80  lea     rax, aIsl; "ISL"
0x140096a87  mov     [rbp+220h+var_188], rax
0x140096a8e  lea     rax, aIe; "IE"
0x140096a95  mov     [rbp+220h+var_180], rax
0x140096a9c  lea     rax, aIrl; "IRL"
0x140096aa3  mov     [rbp+220h+var_178], rax
0x140096aaa  lea     rax, aIt; "IT"
0x140096ab1  mov     [rbp+220h+var_170], rax
0x140096ab8  lea     rax, aIta; "ITA"
0x140096abf  mov     [rbp+220h+var_168], rax
0x140096ac6  lea     rax, aKr; "KR"
0x140096acd  mov     [rbp+220h+var_160], rax
0x140096ad4  lea     rax, aKor; "KOR"
0x140096adb  mov     [rbp+220h+var_158], rax
0x140096ae2  lea     rax, aLv; "LV"
0x140096ae9  mov     [rbp+220h+var_150], rax
0x140096af0  lea     rax, aLva; "LVA"
0x140096af7  mov     [rbp+220h+var_148], rax
0x140096afe  lea     rax, aLi; "LI"
0x140096b05  mov     [rbp+220h+var_140], rax
0x140096b0c  lea     rax, aLie; "LIE"
0x140096b13  mov     [rbp+220h+var_138], rax
0x140096b1a  lea     rax, aLt; "LT"
0x140096b21  mov     [rbp+220h+var_130], rax
0x140096b28  lea     rax, aLtu; "LTU"
0x140096b2f  mov     [rbp+220h+var_128], rax
0x140096b36  lea     rax, aLu; "LU"
0x140096b3d  mov     [rbp+220h+var_120], rax
0x140096b44  lea     rax, aLux; "LUX"
0x140096b4b  mov     [rbp+220h+var_118], rax
0x140096b52  lea     rax, aMt; "MT"
0x140096b59  mov     [rbp+220h+var_110], rax
0x140096b60  lea     rax, aMlt; "MLT"
0x140096b67  mov     [rbp+220h+var_108], rax
0x140096b6e  lea     rax, aNl; "NL"
0x140096b75  mov     [rbp+220h+var_100], rax
0x140096b7c  lea     rax, aNld; "NLD"
0x140096b83  mov     [rbp+220h+var_F8], rax
0x140096b8a  lea     rax, aNo; "NO"
0x140096b91  mov     [rbp+220h+var_F0], rax
0x140096b98  lea     rax, aNor; "NOR"
0x140096b9f  mov     [rbp+220h+var_E8], rax
0x140096ba6  lea     rax, aPl; "PL"
0x140096bad  mov     [rbp+220h+var_E0], rax
0x140096bb4  lea     rax, aPol; "POL"
0x140096bbb  mov     [rbp+220h+var_D8], rax
0x140096bc2  lea     rax, aPt; "PT"
0x140096bc9  mov     [rbp+220h+var_D0], rax
0x140096bd0  lea     rax, aPrt; "PRT"
0x140096bd7  mov     [rbp+220h+var_C8], rax
0x140096bde  lea     rax, aRo; "RO"
0x140096be5  mov     [rbp+220h+var_C0], rax
0x140096bec  lea     rax, aRou; "ROU"
0x140096bf3  mov     [rbp+220h+var_B8], rax
0x140096bfa  lea     rax, aSk; "SK"
0x140096c01  mov     [rbp+220h+var_B0], rax
0x140096c08  lea     rax, aSvk; "SVK"
0x140096c0f  mov     [rbp+220h+var_A8], rax
0x140096c16  lea     rax, aSi; "SI"
0x140096c1d  mov     [rbp+220h+var_A0], rax
0x140096c24  lea     rax, aSvn; "SVN"
0x140096c2b  mov     [rbp+220h+var_98], rax
0x140096c32  lea     rax, aEs; "ES"
0x140096c39  mov     [rbp+220h+var_90], rax
0x140096c40  lea     rax, aEsp; "ESP"
0x140096c47  mov     [rbp+220h+var_88], rax
0x140096c4e  lea     rax, aSe; "SE"
0x140096c55  mov     [rbp+220h+var_80], rax
0x140096c5c  lea     rax, aSwe; "SWE"
0x140096c63  mov     [rbp+220h+var_78], rax
0x140096c6a  lea     rax, aCh; "CH"
0x140096c71  mov     [rbp+220h+var_70], rax
0x140096c78  lea     rax, aChe; "CHE"
0x140096c7f  mov     [rbp+220h+var_68], rax
0x140096c86  lea     rax, aGb; "GB"
0x140096c8d  mov     [rbp+220h+var_60], rax
0x140096c94  lea     rax, aGbr; "GBR"
0x140096c9b  mov     [rbp+220h+var_58], rax
0x140096ca2  lea     rbx, [rbp+220h+var_280]
0x140096ca6  or      edi, 0FFFFFFFFh
0x140096ca9  lea     rax, [rbp+220h+hstringHeader]
0x140096cb0  cmp     rbx, rax
0x140096cb3  jz      short loc_140096CFB
0x140096cb5  xor     edx, edx; length
0x140096cb7  mov     rcx, [rsp+320h+string]; string
0x140096cbc  call    cs:__imp_WindowsGetStringRawBuffer
0x140096cc2  mov     [rsp+320h+bIgnoreCase], 1; bIgnoreCase
0x140096cca  mov     r9d, edi; cchCount2
0x140096ccd  mov     r8, [rbx]; lpString2
0x140096cd0  mov     edx, edi; cchCount1
0x140096cd2  mov     rcx, rax; lpString1
0x140096cd5  call    cs:__imp_CompareStringOrdinal
0x140096cdb  cmp     eax, 2
0x140096cde  jz      short loc_140096CE6
0x140096ce0  add     rbx, 8
0x140096ce4  jmp     short loc_140096CA9
0x140096ce6  mov     rcx, [rsp+320h+string]; string
0x140096ceb  call    cs:__imp_WindowsDeleteString
0x140096cf1  mov     [rsp+320h+string], rsi
0x140096cf6  jmp     loc_1400968A3
0x140096cfb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NewMultiPagePrivacy@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NewMultiPagePrivacy@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NewMultiPagePrivacy> `wil::Feature<__WilFeatureTraits_Feature_NewMultiPagePrivacy>::GetImpl(void)'::`2'::impl
0x140096d02  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NewMultiPagePrivacy@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NewMultiPagePrivacy>::__private_IsEnabled(void)
0x140096d07  test    al, al
0x140096d09  jz      short loc_140096D78
0x140096d0b  lea     rax, aVn; "VN"
0x140096d12  mov     [rsp+320h+var_2E0], rax
0x140096d17  lea     rax, aVnm; "VNM"
0x140096d1e  mov     [rsp+320h+var_2D8], rax
0x140096d23  lea     rbx, [rsp+320h+var_2E0]
0x140096d28  lea     rax, [rsp+320h+var_2D0]
0x140096d2d  cmp     rbx, rax
0x140096d30  jz      short loc_140096D78
0x140096d32  xor     edx, edx; length
0x140096d34  mov     rcx, [rsp+320h+string]; string
0x140096d39  call    cs:__imp_WindowsGetStringRawBuffer
0x140096d3f  mov     [rsp+320h+bIgnoreCase], 1; bIgnoreCase
0x140096d47  mov     r9d, edi; cchCount2
0x140096d4a  mov     r8, [rbx]; lpString2
0x140096d4d  mov     edx, edi; cchCount1
0x140096d4f  mov     rcx, rax; lpString1
0x140096d52  call    cs:__imp_CompareStringOrdinal
0x140096d58  cmp     eax, 2
0x140096d5b  jz      short loc_140096D63
0x140096d5d  add     rbx, 8
0x140096d61  jmp     short loc_140096D28
0x140096d63  mov     rcx, [rsp+320h+string]; string
0x140096d68  call    cs:__imp_WindowsDeleteString
0x140096d6e  mov     [rsp+320h+string], rsi
0x140096d73  jmp     loc_1400968A3
0x140096d78  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MissingMultiPagePrivacy@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MissingMultiPagePrivacy@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MissingMultiPagePrivacy> `wil::Feature<__WilFeatureTraits_Feature_MissingMultiPagePrivacy>::GetImpl(void)'::`2'::impl
0x140096d7f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MissingMultiPagePrivacy@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MissingMultiPagePrivacy>::__private_IsEnabled(void)
0x140096d84  test    al, al
0x140096d86  jz      loc_140096E6F
0x140096d8c  lea     rax, aGf; "GF"
0x140096d93  mov     [rsp+320h+var_2D0], rax
0x140096d98  lea     rax, aGuf; "GUF"
0x140096d9f  mov     [rsp+320h+var_2C8], rax
0x140096da4  lea     rax, aGp; "GP"
0x140096dab  mov     [rsp+320h+var_2C0], rax
0x140096db0  lea     rax, aGlp; "GLP"
0x140096db7  mov     [rsp+320h+var_2B8], rax
0x140096dbc  lea     rax, aMq; "MQ"
0x140096dc3  mov     [rsp+320h+var_2B0], rax
0x140096dc8  lea     rax, aMtq; "MTQ"
0x140096dcf  mov     [rsp+320h+var_2A8], rax
0x140096dd4  lea     rax, aRe; "RE"
0x140096ddb  mov     [rbp+220h+var_2A0], rax
0x140096ddf  lea     rax, aReu; "REU"
0x140096de6  mov     [rbp+220h+var_298], rax
0x140096dea  lea     rax, aYt; "YT"
0x140096df1  mov     [rbp+220h+var_290], rax
0x140096df5  lea     rax, aMyt; "MYT"
0x140096dfc  mov     [rbp+220h+var_288], rax
0x140096e00  lea     rbx, [rsp+320h+var_2D0]
0x140096e05  lea     rax, [rbp+220h+var_280]
0x140096e09  cmp     rbx, rax
0x140096e0c  jz      short loc_140096E6F
0x140096e0e  xor     edx, edx; length
0x140096e10  mov     rcx, [rsp+320h+string]; string
0x140096e15  call    cs:__imp_WindowsGetStringRawBuffer
0x140096e1b  mov     [rsp+320h+bIgnoreCase], 1; bIgnoreCase
0x140096e23  mov     r9d, edi; cchCount2
0x140096e26  mov     r8, [rbx]; lpString2
0x140096e29  mov     edx, edi; cchCount1
0x140096e2b  mov     rcx, rax; lpString1
0x140096e2e  call    cs:__imp_CompareStringOrdinal
0x140096e34  cmp     eax, 2
0x140096e37  jz      short loc_140096E3F
0x140096e39  add     rbx, 8
0x140096e3d  jmp     short loc_140096E05
0x140096e3f  mov     rcx, [rsp+320h+string]; string
0x140096e44  call    cs:__imp_WindowsDeleteString
0x140096e4a  mov     [rsp+320h+string], rsi
0x140096e4f  mov     rcx, [rsp+320h+var_2E8]
0x140096e54  test    rcx, rcx
0x140096e57  jz      short loc_140096E6B
0x140096e59  mov     [rsp+320h+var_2E8], rsi
0x140096e5e  mov     rdx, [rcx]
  ... truncated ...
```
