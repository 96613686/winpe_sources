# Details::DoesCurrentRegionUseMultiPageLayout(void)

- ea: `0x180095448`
- end: `0x180095ade`
- name: `?DoesCurrentRegionUseMultiPageLayout@Details@@YA_NXZ`
- size: `1686`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009a0ec`

## callees

- `0x180003470`
- `0x180008544`
- `0x180042068`
- `0x180094994`
- `0x180095448`
- `0x18009a51c`
- `0x18009a558`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800958ed`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180095959`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180095a23`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800958ed`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180095959`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180095a23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800954f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095539`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095a40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095a70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095a85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095a9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800954f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095539`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095a40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095a70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095a85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095a9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800958d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180095940`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180095a0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800958d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180095940`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180095a0a`

## string_xrefs

- `0x1800954b7`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\PrivacyConsentPolicy.h`
- `0x180095522`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\PrivacyConsentPolicy.h`

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
  LPCWCH *v6; // rbx
  const WCHAR *StringRawBuffer; // rax
  LPCWCH *v8; // rbx
  const WCHAR *v9; // rax
  LPCWCH *v10; // rbx
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
  if ( v0 >= 0 )
  {
    string = 0;
    v3 = v17;
    v4 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v17 + 64LL);
    WindowsDeleteString(0);
    string = 0;
    v5 = v4(v3, &string);
    if ( v5 >= 0 )
    {
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
      v6 = (LPCWCH *)v20;
      while ( 1 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        if ( CompareStringOrdinal(StringRawBuffer, -1, *v6, -1, 1) == 2 )
          break;
        if ( ++v6 == (LPCWCH *)&hstringHeader )
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NewMultiPagePrivacy>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NewMultiPagePrivacy>::GetImpl'::`2'::impl) )
          {
            v18[0] = L"VN";
            v18[1] = L"VNM";
            v8 = (LPCWCH *)v18;
            do
            {
              v9 = WindowsGetStringRawBuffer(string, 0);
              if ( CompareStringOrdinal(v9, -1, *v8, -1, 1) == 2 )
                goto LABEL_21;
              ++v8;
            }
            while ( v8 != v19 );
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
            v10 = (LPCWCH *)v19;
            while ( 1 )
            {
              v11 = WindowsGetStringRawBuffer(string, 0);
              if ( CompareStringOrdinal(v11, -1, *v10, -1, 1) == 2 )
                break;
              if ( ++v10 == v20 )
                goto LABEL_18;
            }
LABEL_21:
            WindowsDeleteString(string);
            string = 0;
            goto LABEL_3;
          }
LABEL_18:
          WindowsDeleteString(string);
          string = 0;
          v12 = v17;
          if ( v17 )
          {
            v17 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
          }
          return 0;
        }
      }
      WindowsDeleteString(string);
      string = 0;
      v14 = v17;
      if ( !v17 )
        return 1;
      v17 = 0;
      v2 = *(void (**)(void))(*(_QWORD *)v14 + 16LL);
      goto LABEL_25;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4E,
      (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\PrivacyConsentPolicy.h",
      (const char *)(unsigned int)v5,
      bIgnoreCase);
    WindowsDeleteString(string);
    string = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\PrivacyConsentPolicy.h",
      (const char *)(unsigned int)v0,
      bIgnoreCase);
  }
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

```

## disassembly

```asm
0x180095448  push    rbp
0x18009544a  push    rbx
0x18009544b  push    rsi
0x18009544c  push    rdi
0x18009544d  lea     rbp, [rsp-208h]
0x180095455  sub     rsp, 308h
0x18009545c  mov     rax, cs:__security_cookie
0x180095463  xor     rax, rsp
0x180095466  mov     [rbp+220h+var_30], rax
0x18009546d  xor     esi, esi
0x18009546f  mov     [rsp+320h+var_2E8], rsi
0x180095474  mov     [rbp+220h+var_38], rsi
0x18009547b  lea     r9d, [rsi+26h]; unsigned int
0x18009547f  lea     r8d, [rsi+27h]; unsigned int
0x180095483  lea     rdx, ?RuntimeClass_Windows_Globalization_GeographicRegion@@3QBGB; "Windows.Globalization.GeographicRegion"
0x18009548a  lea     rcx, [rbp+220h+hstringHeader]; hstringHeader
0x180095491  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180095496  nop
0x180095497  lea     rdx, [rsp+320h+var_2E8]
0x18009549c  mov     rcx, [rbp+220h+var_38]
0x1800954a3  call    ??$ActivateInstance@UIGeographicRegion@Globalization@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIGeographicRegion@Globalization@1@@Z; Windows::Foundation::ActivateInstance<Windows::Globalization::IGeographicRegion>(HSTRING__ *,Windows::Globalization::IGeographicRegion * *)
0x1800954a8  nop
0x1800954a9  test    eax, eax
0x1800954ab  jns     short loc_1800954E6
0x1800954ad  mov     rcx, [rbp+228h]; this
0x1800954b4  mov     r9d, eax; char *
0x1800954b7  lea     r8, aShellcommondes; "ShellCommonDesktopBase\\Internal\\Shell"...
0x1800954be  lea     edx, [rsi+4Bh]; void *
0x1800954c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800954c6  nop
0x1800954c7  mov     rcx, [rsp+320h+var_2E8]
0x1800954cc  test    rcx, rcx
0x1800954cf  jz      loc_180095AC1
0x1800954d5  mov     [rsp+320h+var_2E8], rsi
0x1800954da  mov     rax, [rcx]
0x1800954dd  mov     rax, [rax+10h]
0x1800954e1  jmp     loc_180095ABB
0x1800954e6  mov     [rsp+320h+string], rsi
0x1800954eb  mov     rdi, [rsp+320h+var_2E8]
0x1800954f0  mov     rax, [rdi]
0x1800954f3  mov     rbx, [rax+40h]
0x1800954f7  xor     ecx, ecx; string
0x1800954f9  call    cs:__imp_WindowsDeleteString
0x1800954ff  mov     [rsp+320h+string], rsi
0x180095504  lea     rdx, [rsp+320h+string]
0x180095509  mov     rcx, rdi
0x18009550c  mov     rax, rbx
0x18009550f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095514  test    eax, eax
0x180095516  jns     short loc_180095546
0x180095518  mov     rcx, [rbp+228h]; this
0x18009551f  mov     r9d, eax; char *
0x180095522  lea     r8, aShellcommondes; "ShellCommonDesktopBase\\Internal\\Shell"...
0x180095529  mov     edx, 4Eh ; 'N'; void *
0x18009552e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180095533  nop
0x180095534  mov     rcx, [rsp+320h+string]; string
0x180095539  call    cs:__imp_WindowsDeleteString
0x18009553f  mov     [rsp+320h+string], rsi
0x180095544  jmp     short loc_1800954C7
0x180095546  lea     rax, aAt; "AT"
0x18009554d  mov     [rbp+220h+var_280], rax
0x180095551  lea     rax, aAut; "AUT"
0x180095558  mov     [rbp+220h+var_278], rax
0x18009555c  lea     rax, aBe; "BE"
0x180095563  mov     [rbp+220h+var_270], rax
0x180095567  lea     rax, aBel; "BEL"
0x18009556e  mov     [rbp+220h+var_268], rax
0x180095572  lea     rax, aBg; "BG"
0x180095579  mov     [rbp+220h+var_260], rax
0x18009557d  lea     rax, aBgr; "BGR"
0x180095584  mov     [rbp+220h+var_258], rax
0x180095588  lea     rax, aBr; "BR"
0x18009558f  mov     [rbp+220h+var_250], rax
0x180095593  lea     rax, aBra; "BRA"
0x18009559a  mov     [rbp+220h+var_248], rax
0x18009559e  lea     rax, aCa; "CA"
0x1800955a5  mov     [rbp+220h+var_240], rax
0x1800955a9  lea     rax, aCan; "CAN"
0x1800955b0  mov     [rbp+220h+var_238], rax
0x1800955b4  lea     rax, aHr; "HR"
0x1800955bb  mov     [rbp+220h+var_230], rax
0x1800955bf  lea     rax, aHrv; "HRV"
0x1800955c6  mov     [rbp+220h+var_228], rax
0x1800955ca  lea     rax, aCy; "CY"
0x1800955d1  mov     [rbp+220h+var_220], rax
0x1800955d5  lea     rax, aCyp; "CYP"
0x1800955dc  mov     [rbp+220h+var_218], rax
0x1800955e0  lea     rax, aCz; "CZ"
0x1800955e7  mov     [rbp+220h+var_210], rax
0x1800955eb  lea     rax, aCze; "CZE"
0x1800955f2  mov     [rbp+220h+var_208], rax
0x1800955f6  lea     rax, aDk; "DK"
0x1800955fd  mov     [rbp+220h+var_200], rax
0x180095601  lea     rax, aDnk; "DNK"
0x180095608  mov     [rbp+220h+var_1F8], rax
0x18009560c  lea     rax, aEe; "EE"
0x180095613  mov     [rbp+220h+var_1F0], rax
0x180095617  lea     rax, aEst; "EST"
0x18009561e  mov     [rbp+220h+var_1E8], rax
0x180095622  lea     rax, aFi; "FI"
0x180095629  mov     [rbp+220h+var_1E0], rax
0x18009562d  lea     rax, aFin; "FIN"
0x180095634  mov     [rbp+220h+var_1D8], rax
0x180095638  lea     rax, aFr; "FR"
0x18009563f  mov     [rbp+220h+var_1D0], rax
0x180095643  lea     rax, aFra; "FRA"
0x18009564a  mov     [rbp+220h+var_1C8], rax
0x18009564e  lea     rax, aDe; "DE"
0x180095655  mov     [rbp+220h+var_1C0], rax
0x180095659  lea     rax, aDeu; "DEU"
0x180095660  mov     [rbp+220h+var_1B8], rax
0x180095664  lea     rax, aGr; "GR"
0x18009566b  mov     [rbp+220h+var_1B0], rax
0x18009566f  lea     rax, aGrc; "GRC"
0x180095676  mov     [rbp+220h+var_1A8], rax
0x18009567a  lea     rax, aHu; "HU"
0x180095681  mov     [rbp+220h+var_1A0], rax
0x180095688  lea     rax, aHun; "HUN"
0x18009568f  mov     [rbp+220h+var_198], rax
0x180095696  lea     rax, aIs; "IS"
0x18009569d  mov     [rbp+220h+var_190], rax
0x1800956a4  lea     rax, aIsl; "ISL"
0x1800956ab  mov     [rbp+220h+var_188], rax
0x1800956b2  lea     rax, aIe; "IE"
0x1800956b9  mov     [rbp+220h+var_180], rax
0x1800956c0  lea     rax, aIrl; "IRL"
0x1800956c7  mov     [rbp+220h+var_178], rax
0x1800956ce  lea     rax, aIt; "IT"
0x1800956d5  mov     [rbp+220h+var_170], rax
0x1800956dc  lea     rax, aIta; "ITA"
0x1800956e3  mov     [rbp+220h+var_168], rax
0x1800956ea  lea     rax, aKr; "KR"
0x1800956f1  mov     [rbp+220h+var_160], rax
0x1800956f8  lea     rax, aKor; "KOR"
0x1800956ff  mov     [rbp+220h+var_158], rax
0x180095706  lea     rax, aLv; "LV"
0x18009570d  mov     [rbp+220h+var_150], rax
0x180095714  lea     rax, aLva; "LVA"
0x18009571b  mov     [rbp+220h+var_148], rax
0x180095722  lea     rax, aLi; "LI"
0x180095729  mov     [rbp+220h+var_140], rax
0x180095730  lea     rax, aLie; "LIE"
0x180095737  mov     [rbp+220h+var_138], rax
0x18009573e  lea     rax, aLt; "LT"
0x180095745  mov     [rbp+220h+var_130], rax
0x18009574c  lea     rax, aLtu; "LTU"
0x180095753  mov     [rbp+220h+var_128], rax
0x18009575a  lea     rax, aLu; "LU"
0x180095761  mov     [rbp+220h+var_120], rax
0x180095768  lea     rax, aLux; "LUX"
0x18009576f  mov     [rbp+220h+var_118], rax
0x180095776  lea     rax, aMt; "MT"
0x18009577d  mov     [rbp+220h+var_110], rax
0x180095784  lea     rax, aMlt; "MLT"
0x18009578b  mov     [rbp+220h+var_108], rax
0x180095792  lea     rax, aNl; "NL"
0x180095799  mov     [rbp+220h+var_100], rax
0x1800957a0  lea     rax, aNld; "NLD"
0x1800957a7  mov     [rbp+220h+var_F8], rax
0x1800957ae  lea     rax, aNo; "NO"
0x1800957b5  mov     [rbp+220h+var_F0], rax
0x1800957bc  lea     rax, aNor; "NOR"
0x1800957c3  mov     [rbp+220h+var_E8], rax
0x1800957ca  lea     rax, aPl; "PL"
0x1800957d1  mov     [rbp+220h+var_E0], rax
0x1800957d8  lea     rax, aPol; "POL"
0x1800957df  mov     [rbp+220h+var_D8], rax
0x1800957e6  lea     rax, aPt; "PT"
0x1800957ed  mov     [rbp+220h+var_D0], rax
0x1800957f4  lea     rax, aPrt; "PRT"
0x1800957fb  mov     [rbp+220h+var_C8], rax
0x180095802  lea     rax, aRo; "RO"
0x180095809  mov     [rbp+220h+var_C0], rax
0x180095810  lea     rax, aRou; "ROU"
0x180095817  mov     [rbp+220h+var_B8], rax
0x18009581e  lea     rax, aSk; "SK"
0x180095825  mov     [rbp+220h+var_B0], rax
0x18009582c  lea     rax, aSvk; "SVK"
0x180095833  mov     [rbp+220h+var_A8], rax
0x18009583a  lea     rax, aSi; "SI"
0x180095841  mov     [rbp+220h+var_A0], rax
0x180095848  lea     rax, aSvn; "SVN"
0x18009584f  mov     [rbp+220h+var_98], rax
0x180095856  lea     rax, aEs; "ES"
0x18009585d  mov     [rbp+220h+var_90], rax
0x180095864  lea     rax, aEsp; "ESP"
0x18009586b  mov     [rbp+220h+var_88], rax
0x180095872  lea     rax, aSe; "SE"
0x180095879  mov     [rbp+220h+var_80], rax
0x180095880  lea     rax, aSwe; "SWE"
0x180095887  mov     [rbp+220h+var_78], rax
0x18009588e  lea     rax, aCh; "CH"
0x180095895  mov     [rbp+220h+var_70], rax
0x18009589c  lea     rax, aChe; "CHE"
0x1800958a3  mov     [rbp+220h+var_68], rax
0x1800958aa  lea     rax, aGb; "GB"
0x1800958b1  mov     [rbp+220h+var_60], rax
0x1800958b8  lea     rax, aGbr; "GBR"
0x1800958bf  mov     [rbp+220h+var_58], rax
0x1800958c6  lea     rbx, [rbp+220h+var_280]
0x1800958ca  or      edi, 0FFFFFFFFh
0x1800958cd  xor     edx, edx; length
0x1800958cf  mov     rcx, [rsp+320h+string]; string
0x1800958d4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800958da  mov     [rsp+320h+bIgnoreCase], 1; bIgnoreCase
0x1800958e2  mov     r9d, edi; cchCount2
0x1800958e5  mov     r8, [rbx]; lpString2
0x1800958e8  mov     edx, edi; cchCount1
0x1800958ea  mov     rcx, rax; lpString1
0x1800958ed  call    cs:__imp_CompareStringOrdinal
0x1800958f3  cmp     eax, 2
0x1800958f6  jz      loc_180095A95
0x1800958fc  add     rbx, 8
0x180095900  lea     rax, [rbp+220h+hstringHeader]
0x180095907  cmp     rbx, rax
0x18009590a  jnz     short loc_1800958CD
0x18009590c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NewMultiPagePrivacy@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NewMultiPagePrivacy@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NewMultiPagePrivacy> `wil::Feature<__WilFeatureTraits_Feature_NewMultiPagePrivacy>::GetImpl(void)'::`2'::impl
0x180095913  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NewMultiPagePrivacy@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NewMultiPagePrivacy>::__private_IsEnabled(void)
0x180095918  test    al, al
0x18009591a  jz      short loc_180095976
0x18009591c  lea     rax, aVn; "VN"
0x180095923  mov     [rsp+320h+var_2E0], rax
0x180095928  lea     rax, aVnm; "VNM"
0x18009592f  mov     [rsp+320h+var_2D8], rax
0x180095934  lea     rbx, [rsp+320h+var_2E0]
0x180095939  xor     edx, edx; length
0x18009593b  mov     rcx, [rsp+320h+string]; string
0x180095940  call    cs:__imp_WindowsGetStringRawBuffer
0x180095946  mov     [rsp+320h+bIgnoreCase], 1; bIgnoreCase
0x18009594e  mov     r9d, edi; cchCount2
0x180095951  mov     r8, [rbx]; lpString2
0x180095954  mov     edx, edi; cchCount1
0x180095956  mov     rcx, rax; lpString1
0x180095959  call    cs:__imp_CompareStringOrdinal
0x18009595f  cmp     eax, 2
0x180095962  jz      loc_180095A6B
0x180095968  add     rbx, 8
0x18009596c  lea     rax, [rsp+320h+var_2D0]
0x180095971  cmp     rbx, rax
0x180095974  jnz     short loc_180095939
0x180095976  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MissingMultiPagePrivacy@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MissingMultiPagePrivacy@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MissingMultiPagePrivacy> `wil::Feature<__WilFeatureTraits_Feature_MissingMultiPagePrivacy>::GetImpl(void)'::`2'::impl
0x18009597d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MissingMultiPagePrivacy@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MissingMultiPagePrivacy>::__private_IsEnabled(void)
0x180095982  test    al, al
0x180095984  jz      loc_180095A3B
0x18009598a  lea     rax, aGf; "GF"
0x180095991  mov     [rsp+320h+var_2D0], rax
0x180095996  lea     rax, aGuf; "GUF"
0x18009599d  mov     [rsp+320h+var_2C8], rax
0x1800959a2  lea     rax, aGp; "GP"
0x1800959a9  mov     [rsp+320h+var_2C0], rax
0x1800959ae  lea     rax, aGlp; "GLP"
0x1800959b5  mov     [rsp+320h+var_2B8], rax
0x1800959ba  lea     rax, aMq; "MQ"
0x1800959c1  mov     [rsp+320h+var_2B0], rax
0x1800959c6  lea     rax, aMtq; "MTQ"
0x1800959cd  mov     [rsp+320h+var_2A8], rax
0x1800959d2  lea     rax, aRe; "RE"
0x1800959d9  mov     [rbp+220h+var_2A0], rax
0x1800959dd  lea     rax, aReu; "REU"
0x1800959e4  mov     [rbp+220h+var_298], rax
0x1800959e8  lea     rax, aYt; "YT"
0x1800959ef  mov     [rbp+220h+var_290], rax
0x1800959f3  lea     rax, aMyt; "MYT"
0x1800959fa  mov     [rbp+220h+var_288], rax
0x1800959fe  lea     rbx, [rsp+320h+var_2D0]
0x180095a03  xor     edx, edx; length
0x180095a05  mov     rcx, [rsp+320h+string]; string
0x180095a0a  call    cs:__imp_WindowsGetStringRawBuffer
0x180095a10  mov     [rsp+320h+bIgnoreCase], 1; bIgnoreCase
0x180095a18  mov     r9d, edi; cchCount2
0x180095a1b  mov     r8, [rbx]; lpString2
0x180095a1e  mov     edx, edi; cchCount1
0x180095a20  mov     rcx, rax; lpString1
0x180095a23  call    cs:__imp_CompareStringOrdinal
0x180095a29  cmp     eax, 2
0x180095a2c  jz      short loc_180095A80
0x180095a2e  add     rbx, 8
0x180095a32  lea     rax, [rbp+220h+var_280]
0x180095a36  cmp     rbx, rax
0x180095a39  jnz     short loc_180095A03
0x180095a3b  mov     rcx, [rsp+320h+string]; string
0x180095a40  call    cs:__imp_WindowsDeleteString
0x180095a46  mov     [rsp+320h+string], rsi
0x180095a4b  mov     rcx, [rsp+320h+var_2E8]
0x180095a50  test    rcx, rcx
0x180095a53  jz      short loc_180095A67
0x180095a55  mov     [rsp+320h+var_2E8], rsi
0x180095a5a  mov     rax, [rcx]
0x180095a5d  mov     rax, [rax+10h]
0x180095a61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095a66  nop
0x180095a67  xor     al, al
0x180095a69  jmp     short loc_180095AC3
0x180095a6b  mov     rcx, [rsp+320h+string]; string
0x180095a70  call    cs:__imp_WindowsDeleteString
0x180095a76  mov     [rsp+320h+string], rsi
0x180095a7b  jmp     loc_1800954C7
0x180095a80  mov     rcx, [rsp+320h+string]; string
0x180095a85  call    cs:__imp_WindowsDeleteString
  ... truncated ...
```
