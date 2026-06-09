# DoesUserRegionRequireConsents(bool *,PrivacyConsentSettingsVersion *)

- ea: `0x1400627f4`
- end: `0x1400629ed`
- name: `?DoesUserRegionRequireConsents@@YAJPEA_NPEAW4PrivacyConsentSettingsVersion@@@Z`
- size: `505`
- prototype: `__int64 __fastcall(bool *, enum PrivacyConsentSettingsVersion *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14006277c`

## callees

- `0x1400627f4`
- `0x1400629f4`
- `0x1400954e0`
- `0x1401040e0`
- `0x1401db010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400629d6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400629d6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1400628cd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1400628cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400628b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400628b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14006286f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400628ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140062978`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400629a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14006286f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400628ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140062978`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400629a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140062839`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140062839`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DoesUserRegionRequireConsents(bool *a1, enum PrivacyConsentSettingsVersion *a2)
{
  wchar_t **i; // rdi
  HRESULT v5; // eax
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, HSTRING *); // rbx
  int v10; // eax
  const WCHAR *v11; // rbx
  const WCHAR *StringRawBuffer; // rax
  __int64 v13; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-50h]
  __int64 v18; // [rsp+30h] [rbp-40h] BYREF
  HSTRING v19; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  HSTRING string; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v18 = 0;
  string = 0;
  v5 = WindowsCreateStringReference(L"Windows.Globalization.GeographicRegion", 0x26u, &hstringHeader, &string);
  if ( v5 >= 0 )
  {
    v6 = Windows::Foundation::ActivateInstance<Windows::Globalization::IGeographicRegion>(string, &v18);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCF,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\PrivacyConsentHelpers.h",
        (const char *)(unsigned int)v6,
        bIgnoreCase);
      v15 = v18;
      if ( v18 )
      {
        v18 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      }
    }
    else
    {
      v19 = 0;
      v8 = v18;
      v9 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v18 + 64LL);
      WindowsDeleteString(0);
      v19 = 0;
      v10 = v9(v8, &v19);
      v7 = v10;
      if ( v10 >= 0 )
      {
        for ( i = &`DoesUserRegionRequireConsents'::`2'::RegionPrivacyRequirements; ; i += 2 )
        {
          if ( i == (wchar_t **)&AccessibilitySettingsTraceLogging::`vftable' )
          {
            *a1 = 0;
            if ( a2 )
              *(_DWORD *)a2 = 0;
            goto LABEL_9;
          }
          v11 = *i;
          StringRawBuffer = WindowsGetStringRawBuffer(v19, 0);
          if ( CompareStringOrdinal(StringRawBuffer, -1, v11, -1, 1) == 2 )
            break;
        }
        *a1 = 1;
        if ( a2 )
          goto LABEL_22;
        goto LABEL_9;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD2,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\PrivacyConsentHelpers.h",
        (const char *)(unsigned int)v10,
        bIgnoreCase);
      WindowsDeleteString(v19);
      v19 = 0;
      v16 = v18;
      if ( v18 )
      {
        v18 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      }
    }
    return v7;
  }
  RaiseException(v5, 1u, 0, 0);
LABEL_22:
  *(_DWORD *)a2 = *((_DWORD *)i + 2);
LABEL_9:
  WindowsDeleteString(v19);
  v19 = 0;
  v13 = v18;
  if ( v18 )
  {
    v18 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  return 0;
}

```

## disassembly

```asm
0x1400627f4  mov     [rsp-28h+arg_10], rbx
0x1400627f9  push    rbp
0x1400627fa  push    rsi
0x1400627fb  push    rdi
0x1400627fc  push    r14
0x1400627fe  push    r15
0x140062800  mov     rbp, rsp
0x140062803  sub     rsp, 70h
0x140062807  mov     rax, cs:__security_cookie
0x14006280e  xor     rax, rsp
0x140062811  mov     [rbp+var_10], rax
0x140062815  mov     rsi, rdx
0x140062818  mov     r14, rcx
0x14006281b  xor     r15d, r15d
0x14006281e  mov     [rbp+var_40], r15
0x140062822  mov     [rbp+string], r15
0x140062826  lea     r9, [rbp+string]; string
0x14006282a  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14006282e  lea     edx, [r15+26h]; length
0x140062832  lea     rcx, ?RuntimeClass_Windows_Globalization_GeographicRegion@@3QBGB; "Windows.Globalization.GeographicRegion"
0x140062839  call    cs:__imp_WindowsCreateStringReference
0x14006283f  test    eax, eax
0x140062841  js      loc_1400629CA
0x140062847  lea     rdx, [rbp+var_40]
0x14006284b  mov     rcx, [rbp+string]
0x14006284f  call    ??$ActivateInstance@UIGeographicRegion@Globalization@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIGeographicRegion@Globalization@1@@Z; Windows::Foundation::ActivateInstance<Windows::Globalization::IGeographicRegion>(HSTRING__ *,Windows::Globalization::IGeographicRegion * *)
0x140062854  mov     ebx, eax
0x140062856  test    eax, eax
0x140062858  js      loc_140062935
0x14006285e  mov     [rbp+var_38], r15
0x140062862  mov     rdi, [rbp+var_40]
0x140062866  mov     rax, [rdi]
0x140062869  mov     rbx, [rax+40h]
0x14006286d  xor     ecx, ecx; string
0x14006286f  call    cs:__imp_WindowsDeleteString
0x140062875  mov     [rbp+var_38], r15
0x140062879  lea     rdx, [rbp+var_38]
0x14006287d  mov     rcx, rdi
0x140062880  mov     rax, rbx
0x140062883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140062888  mov     ebx, eax
0x14006288a  test    eax, eax
0x14006288c  js      loc_140062987
0x140062892  lea     rdi, ?RegionPrivacyRequirements@?1??DoesUserRegionRequireConsents@@YAJPEA_NPEAW4PrivacyConsentSettingsVersion@@@Z@4QBU_unnamed_type_RegionPrivacyRequirements_@?1??1@YAJ01@Z@B; `DoesUserRegionRequireConsents(bool *,PrivacyConsentSettingsVersion *)'::`2'::_unnamed_type_RegionPrivacyRequirements_ const near * const `DoesUserRegionRequireConsents(bool *,PrivacyConsentSettingsVersion *)'::`2'::RegionPrivacyRequirements
0x140062899  lea     rax, ??_7AccessibilitySettingsTraceLogging@@6B@; const AccessibilitySettingsTraceLogging::`vftable'
0x1400628a0  cmp     rdi, rax
0x1400628a3  jz      loc_14006296C
0x1400628a9  mov     rbx, [rdi]
0x1400628ac  xor     edx, edx; length
0x1400628ae  mov     rcx, [rbp+var_38]; string
0x1400628b2  call    cs:__imp_WindowsGetStringRawBuffer
0x1400628b8  mov     [rsp+70h+bIgnoreCase], 1; bIgnoreCase
0x1400628c0  or      r9d, 0FFFFFFFFh; cchCount2
0x1400628c4  mov     r8, rbx; lpString2
0x1400628c7  or      edx, r9d; cchCount1
0x1400628ca  mov     rcx, rax; lpString1
0x1400628cd  call    cs:__imp_CompareStringOrdinal
0x1400628d3  cmp     eax, 2
0x1400628d6  jz      short loc_1400628DE
0x1400628d8  add     rdi, 10h
0x1400628dc  jmp     short loc_140062899
0x1400628de  mov     byte ptr [r14], 1
0x1400628e2  test    rsi, rsi
0x1400628e5  jnz     loc_1400629DD
0x1400628eb  mov     rcx, [rbp+var_38]; string
0x1400628ef  call    cs:__imp_WindowsDeleteString
0x1400628f5  mov     [rbp+var_38], r15
0x1400628f9  mov     rcx, [rbp+var_40]
0x1400628fd  test    rcx, rcx
0x140062900  jz      short loc_140062913
0x140062902  mov     [rbp+var_40], r15
0x140062906  mov     rax, [rcx]
0x140062909  mov     rax, [rax+10h]
0x14006290d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140062912  nop
0x140062913  xor     eax, eax
0x140062915  mov     rcx, [rbp+var_10]
0x140062919  xor     rcx, rsp; StackCookie
0x14006291c  call    __security_check_cookie
0x140062921  mov     rbx, [rsp+70h+arg_10]
0x140062929  add     rsp, 70h
0x14006292d  pop     r15
0x14006292f  pop     r14
0x140062931  pop     rdi
0x140062932  pop     rsi
0x140062933  pop     rbp
0x140062934  retn
0x140062935  mov     rcx, [rbp+28h]; this
0x140062939  mov     r9d, ebx; char *
0x14006293c  lea     r8, aOnecoreuapInte_15; "onecoreuap\\internal\\shell\\inc\\Priva"...
0x140062943  mov     edx, 0CFh; void *
0x140062948  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006294d  nop
0x14006294e  mov     rcx, [rbp+var_40]
0x140062952  test    rcx, rcx
0x140062955  jz      short loc_140062968
0x140062957  mov     [rbp+var_40], r15
0x14006295b  mov     rax, [rcx]
0x14006295e  mov     rax, [rax+10h]
0x140062962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140062967  nop
0x140062968  mov     eax, ebx
0x14006296a  jmp     short loc_140062915
0x14006296c  mov     [r14], r15b
0x14006296f  test    rsi, rsi
0x140062972  jnz     short loc_1400629E7
0x140062974  mov     rcx, [rbp+var_38]; string
0x140062978  call    cs:__imp_WindowsDeleteString
0x14006297e  mov     [rbp+var_38], r15
0x140062982  jmp     loc_1400628F9
0x140062987  mov     rcx, [rbp+28h]; this
0x14006298b  mov     r9d, ebx; char *
0x14006298e  lea     r8, aOnecoreuapInte_15; "onecoreuap\\internal\\shell\\inc\\Priva"...
0x140062995  mov     edx, 0D2h; void *
0x14006299a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006299f  nop
0x1400629a0  mov     rcx, [rbp+var_38]; string
0x1400629a4  call    cs:__imp_WindowsDeleteString
0x1400629aa  mov     [rbp+var_38], r15
0x1400629ae  mov     rcx, [rbp+var_40]
0x1400629b2  test    rcx, rcx
0x1400629b5  jz      short loc_1400629C8
0x1400629b7  mov     [rbp+var_40], r15
0x1400629bb  mov     rax, [rcx]
0x1400629be  mov     rax, [rax+10h]
0x1400629c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400629c7  nop
0x1400629c8  jmp     short loc_140062968
0x1400629ca  xor     r9d, r9d; lpArguments
0x1400629cd  xor     r8d, r8d; nNumberOfArguments
0x1400629d0  lea     edx, [r9+1]; dwExceptionFlags
0x1400629d4  mov     ecx, eax; dwExceptionCode
0x1400629d6  call    cs:__imp_RaiseException
0x1400629dc  nop
0x1400629dd  mov     eax, [rdi+8]
0x1400629e0  mov     [rsi], eax
0x1400629e2  jmp     loc_1400628EB
0x1400629e7  mov     [rsi], r15d
0x1400629ea  jmp     short loc_140062974
```
