# ChangeSystemLocale(IXMLDOMDocument2 *)

- ea: `0x18000ba98`
- end: `0x18000c1df`
- name: `?ChangeSystemLocale@@YAJPEAUIXMLDOMDocument2@@@Z`
- size: `1863`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x18000dce0`

## callees

- `0x1800062b0`
- `0x18000a860`
- `0x18000aa10`
- `0x18000aa9c`
- `0x18000ac20`
- `0x18000accc`
- `0x18000ba98`
- `0x18000ce98`
- `0x18000d020`
- `0x18000d5d0`
- `0x18000d610`
- `0x18000da60`
- `0x18000e5f0`
- `0x18000e844`
- `0x18000f3d0`
- `0x18000f464`
- `0x18000f4d4`
- `0x180012dc8`
- `0x1800245e0`
- `0x18002a150`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be6b`
- `api-ms-win-core-localization-l1-2-0!IsValidLocale` at `0x18000bd45`
- `api-ms-win-core-localization-l1-2-0!IsValidLocale` at `0x18000bd45`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18000bc22`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18000bc5f`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18000bc89`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18000bd62`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18000bdf4`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18000be61`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18000bc22`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18000bc5f`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18000bc89`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18000bd62`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18000bdf4`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18000be61`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18000bd1a`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18000bd1a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c194`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c194`
- `KERNEL32!NlsCheckPolicy` at `0x18000bd01`
- `KERNEL32!NlsCheckPolicy` at `0x18000bd01`
- `KERNEL32!lstrcmpW` at `0x18000bd8a`
- `KERNEL32!lstrcmpW` at `0x18000bd8a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ChangeSystemLocale(struct IXMLDOMDocument2 *a1)
{
  WCHAR *v2; // r14
  unsigned int v3; // r8d
  int Attribute; // ebx
  HRESULT (__stdcall *selectSingleNode)(IXMLDOMDocument2 *, BSTR, IXMLDOMNode **); // rsi
  _bstr_t *v6; // rbx
  _bstr_t *v7; // rax
  __int64 **v8; // rax
  __int64 v9; // rdx
  unsigned int v10; // edi
  unsigned int LastError; // eax
  unsigned int v12; // r8d
  __int64 v13; // rdx
  unsigned __int16 ***v14; // rax
  unsigned __int16 *v15; // rdx
  __int64 v16; // r8
  LCID v17; // eax
  LCID v18; // r15d
  __int64 v19; // rsi
  __int64 v20; // rcx
  __int64 v21; // r9
  DWORD v22; // eax
  unsigned int v23; // r8d
  __int64 v24; // rdx
  __int64 v25; // r9
  unsigned int v26; // eax
  unsigned int v27; // r8d
  __int64 v28; // rdx
  DWORD v29; // edi
  __int64 v30; // r9
  int v31; // eax
  wil::details::in1diag3 *v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // r9
  __int64 v35; // r9
  __int64 v36; // r9
  __int64 v37; // r9
  __int64 v38; // r9
  int v39; // eax
  __int64 v40; // r9
  int v41; // eax
  unsigned int v42; // edx
  LPCWSTR lpName; // [rsp+20h] [rbp-E0h] BYREF
  struct IXMLDOMNode *v45; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v46[8]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v47[8]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v48[16]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v49[42]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR String1[88]; // [rsp+1A0h] [rbp+A0h] BYREF
  WCHAR LCData[88]; // [rsp+250h] [rbp+150h] BYREF
  WCHAR v52[88]; // [rsp+300h] [rbp+200h] BYREF
  WCHAR v53[88]; // [rsp+3B0h] [rbp+2B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4B8h] [rbp+3B8h]

  v45 = 0;
  v2 = 0;
  lpName = 0;
  wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v49,
    "ChangeSystemLocale");
  v49[0] = &IntlCplTraceLoggingTelemetry::ChangeSystemLocale::`vftable';
  IntlCplTraceLoggingTelemetry::ChangeSystemLocale::StartActivity((IntlCplTraceLoggingTelemetry::ChangeSystemLocale *)v49);
  if ( a1 )
  {
    selectSingleNode = a1->lpVtbl->selectSingleNode;
    v6 = _bstr_t::_bstr_t((_bstr_t *)v46, "//");
    v7 = _bstr_t::_bstr_t((_bstr_t *)v48, L"gs:SystemLocale");
    v8 = (__int64 **)_bstr_t::operator+(v6, v47, v7);
    if ( *v8 )
      v9 = **v8;
    else
      v9 = 0;
    Attribute = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, __int64, struct IXMLDOMNode **))selectSingleNode)(
                  a1,
                  v9,
                  &v45);
    _bstr_t::_Free((_bstr_t *)v47);
    _bstr_t::_Free((_bstr_t *)v48);
    _bstr_t::_Free((_bstr_t *)v46);
    v10 = 1;
    if ( Attribute == 1 )
    {
      Attribute = 0;
      goto LABEL_82;
    }
    if ( !(unsigned int)CheckHR(Attribute) )
      goto LABEL_82;
    if ( !g_bAdmin_Privileges )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x4D3,
        (unsigned int)"shell\\osshell\\cpls\\intl\\cme.cpp",
        (const char *)0x80070005LL,
        (int)lpName);
      wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v49, 0x80070005);
      goto LABEL_88;
    }
    if ( !GetLocaleInfoW(0x800u, 0x1004u, LCData, 85) )
    {
      LastError = GetLastError();
      v13 = 1253;
LABEL_13:
      wil::details::in1diag3::Log_Win32(retaddr, (void *)v13, v12, (const char *)LastError, (unsigned int)lpName);
      goto LABEL_82;
    }
    if ( !GetLocaleInfoW(0x800u, 0x1011u, v53, 85) )
    {
      LastError = GetLastError();
      v13 = 1261;
      goto LABEL_13;
    }
    if ( !GetLocaleInfoW(0x800u, 0xBu, v52, 85) )
    {
      LastError = GetLastError();
      v13 = 1269;
      goto LABEL_13;
    }
    v14 = (unsigned __int16 ***)_bstr_t::_bstr_t((_bstr_t *)v46, NAME_ATTR);
    if ( *v14 )
      v15 = **v14;
    else
      v15 = 0;
    Attribute = GetAttribute(v45, v15, (unsigned __int16 **)&lpName);
    _bstr_t::_Free((_bstr_t *)v46);
    if ( Attribute == 1 || !(unsigned int)CheckHR(Attribute) )
    {
      v2 = (WCHAR *)lpName;
      goto LABEL_82;
    }
    v2 = (WCHAR *)lpName;
    if ( (unsigned int)NlsCheckPolicy(lpName, 258, v16) != 1260 )
    {
      v17 = LocaleNameToLCID(v2, 0);
      v18 = v17;
      v19 = -1;
      v20 = -1;
      do
        ++v20;
      while ( v2[v20] );
      if ( (_DWORD)v20 && v17 && IsValidLocale(v17, 2u) )
      {
        if ( !GetLocaleInfoW(v18, 0x1004u, String1, 85) )
        {
          LastError = GetLastError();
          v13 = 1312;
          goto LABEL_13;
        }
        if ( lstrcmpW(String1, L"0") )
        {
          v21 = -1;
          do
            ++v21;
          while ( String1[v21] );
          LastError = WriteValueToRegistry(g_szCodePages, c_szAcpValName, (BYTE *)String1, 2 * (int)v21 + 2);
          if ( LastError )
          {
            v13 = 1332;
            goto LABEL_13;
          }
          if ( !GetLocaleInfoW(v18, 0x1011u, String1, 85) )
          {
            v22 = GetLastError();
            v24 = 1345;
            goto LABEL_45;
          }
          v25 = -1;
          do
            ++v25;
          while ( String1[v25] );
          v26 = WriteValueToRegistry(g_szCodePages, c_szMaccpValName, (BYTE *)String1, 2 * (int)v25 + 2);
          if ( v26 )
          {
            v28 = 1357;
LABEL_64:
            wil::details::in1diag3::Log_Win32(retaddr, (void *)v28, v27, (const char *)v26, (unsigned int)lpName);
            goto LABEL_65;
          }
          if ( !GetLocaleInfoW(v18, 0xBu, String1, 85) )
          {
            v22 = GetLastError();
            v24 = 1366;
LABEL_45:
            v29 = v22;
            wil::details::in1diag3::Log_Win32(retaddr, (void *)v24, v23, (const char *)v22, (unsigned int)lpName);
            if ( !v29 )
              goto LABEL_82;
LABEL_65:
            v36 = -1;
            do
              ++v36;
            while ( LCData[v36] );
            WriteValueToRegistry(g_szCodePages, c_szAcpValName, (BYTE *)LCData, 2 * v36 + 2);
            v37 = -1;
            do
              ++v37;
            while ( v52[v37] );
            WriteValueToRegistry(g_szCodePages, c_szOemcpValName, (BYTE *)v52, 2 * v37 + 2);
            v38 = -1;
            do
              ++v38;
            while ( v53[v38] );
            WriteValueToRegistry(g_szCodePages, c_szMaccpValName, (BYTE *)v53, 2 * v38 + 2);
            v39 = StringCchPrintfW(String1, 0x55u, L"%.4x", 2048);
            if ( v39 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x5B7,
                (unsigned int)"shell\\osshell\\cpls\\intl\\cme.cpp",
                (const char *)(unsigned int)v39,
                (int)lpName);
            v40 = -1;
            do
              ++v40;
            while ( String1[v40] );
            WriteValueToRegistry(c_szLanguages, c_szLangValName, (BYTE *)String1, 2 * v40 + 2);
            v41 = StringCchPrintfW(String1, 0x55u, L"%.8x", 2048);
            Attribute = v41;
            if ( v41 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x5BF,
                (unsigned int)"shell\\osshell\\cpls\\intl\\cme.cpp",
                (const char *)(unsigned int)v41,
                (int)lpName);
            do
              ++v19;
            while ( String1[v19] );
            WriteValueToRegistry(
              L"System\\CurrentControlSet\\Control\\Nls\\Locale",
              c_szLocaleValName,
              (BYTE *)String1,
              2 * v19 + 2);
            goto LABEL_82;
          }
          v30 = -1;
          do
            ++v30;
          while ( String1[v30] );
          v26 = WriteValueToRegistry(g_szCodePages, c_szOemcpValName, (BYTE *)String1, 2 * (int)v30 + 2);
          if ( v26 )
          {
            v28 = 1376;
            goto LABEL_64;
          }
          v31 = StringCchPrintfW(String1, 0x55u, L"%.4x", v18);
          Attribute = v31;
          v32 = retaddr;
          if ( v31 < 0 )
          {
            v33 = 1384;
LABEL_53:
            wil::details::in1diag3::_Log_Hr(
              v32,
              (void *)v33,
              (unsigned int)"shell\\osshell\\cpls\\intl\\cme.cpp",
              (const char *)(unsigned int)v31,
              (int)lpName);
            goto LABEL_82;
          }
          v34 = -1;
          do
            ++v34;
          while ( String1[v34] );
          v26 = WriteValueToRegistry(c_szLanguages, c_szLangValName, (BYTE *)String1, 2 * (int)v34 + 2);
          if ( v26 )
          {
            v28 = 1395;
            goto LABEL_64;
          }
          v31 = StringCchPrintfW(String1, 0x55u, L"%.8x", v18);
          Attribute = v31;
          v32 = retaddr;
          if ( v31 < 0 )
          {
            v33 = 1401;
            goto LABEL_53;
          }
          v35 = -1;
          do
            ++v35;
          while ( String1[v35] );
          v26 = WriteValueToRegistry(
                  L"System\\CurrentControlSet\\Control\\Nls\\Locale",
                  c_szLocaleValName,
                  (BYTE *)String1,
                  2 * (int)v35 + 2);
          if ( v26 )
          {
            v28 = 1412;
            goto LABEL_64;
          }
          if ( (unsigned int)Intl_ChangeSystemFontLinking(v2) )
          {
            Input_InstallLayout(0, v2, 0);
            goto LABEL_82;
          }
        }
      }
    }
    Attribute = 1;
    goto LABEL_82;
  }
  Attribute = -2147024809;
  wil::details::in1diag3::Log_Hr(retaddr, (void *)0x4BD, v3, (const char *)0x80070057LL, (int)lpName);
LABEL_82:
  ReleaseDomNode(&v45);
  if ( v2 )
    SysFreeString(v2);
  if ( Attribute >= 0 )
    v42 = 0;
  else
    v42 = Attribute;
  wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v49, v42);
  v10 = Attribute;
LABEL_88:
  IntlCplTraceLoggingTelemetry::ChangeSystemLocale::~ChangeSystemLocale((IntlCplTraceLoggingTelemetry::ChangeSystemLocale *)v49);
  return v10;
}

```

## disassembly

```asm
0x18000ba98  push    rbp
0x18000ba9a  push    rbx
0x18000ba9b  push    rsi
0x18000ba9c  push    rdi
0x18000ba9d  push    r12
0x18000ba9f  push    r13
0x18000baa1  push    r14
0x18000baa3  push    r15
0x18000baa5  lea     rbp, [rsp-378h]
0x18000baad  sub     rsp, 478h
0x18000bab4  mov     rax, cs:__security_cookie
0x18000babb  xor     rax, rsp
0x18000babe  mov     [rbp+3B0h+var_50], rax
0x18000bac5  mov     rdi, rcx
0x18000bac8  xor     r12d, r12d
0x18000bacb  mov     [rsp+4B0h+var_488], r12
0x18000bad0  mov     r14d, r12d
0x18000bad3  mov     [rsp+4B0h+lpName], r12; int
0x18000bad8  lea     rdx, aChangesystemlo; "ChangeSystemLocale"
0x18000badf  lea     rcx, [rsp+4B0h+var_460]
0x18000bae4  call    ??0?$ActivityBase@VIntlCplTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000bae9  lea     rax, ??_7ChangeSystemLocale@IntlCplTraceLoggingTelemetry@@6B@; const IntlCplTraceLoggingTelemetry::ChangeSystemLocale::`vftable'
0x18000baf0  mov     [rsp+4B0h+var_460], rax
0x18000baf5  lea     rcx, [rsp+4B0h+var_460]; this
0x18000bafa  call    ?StartActivity@ChangeSystemLocale@IntlCplTraceLoggingTelemetry@@QEAAXXZ; IntlCplTraceLoggingTelemetry::ChangeSystemLocale::StartActivity(void)
0x18000baff  nop
0x18000bb00  test    rdi, rdi
0x18000bb03  jnz     short loc_18000BB23
0x18000bb05  mov     ebx, 80070057h
0x18000bb0a  mov     rcx, [rbp+3B8h]; this
0x18000bb11  mov     r9d, ebx; char *
0x18000bb14  mov     edx, 4BDh; void *
0x18000bb19  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18000bb1e  jmp     loc_18000C182
0x18000bb23  mov     rax, [rdi]
0x18000bb26  mov     rsi, [rax+128h]
0x18000bb2d  lea     rdx, asc_180030760; "//"
0x18000bb34  lea     rcx, [rsp+4B0h+var_480]; this
0x18000bb39  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x18000bb3e  mov     rbx, rax
0x18000bb41  lea     rdx, aGsSystemlocale; "gs:SystemLocale"
0x18000bb48  lea     rcx, [rsp+4B0h+var_470]; this
0x18000bb4d  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000bb52  nop
0x18000bb53  mov     r8, rax
0x18000bb56  lea     rdx, [rsp+4B0h+var_478]
0x18000bb5b  mov     rcx, rbx
0x18000bb5e  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x18000bb63  nop
0x18000bb64  mov     rdx, [rax]
0x18000bb67  test    rdx, rdx
0x18000bb6a  jz      short loc_18000BB71
0x18000bb6c  mov     rdx, [rdx]
0x18000bb6f  jmp     short loc_18000BB74
0x18000bb71  mov     rdx, r12
0x18000bb74  lea     r8, [rsp+4B0h+var_488]
0x18000bb79  mov     rcx, rdi
0x18000bb7c  mov     rax, rsi
0x18000bb7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb84  mov     ebx, eax
0x18000bb86  lea     rcx, [rsp+4B0h+var_478]; this
0x18000bb8b  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000bb90  nop
0x18000bb91  lea     rcx, [rsp+4B0h+var_470]; this
0x18000bb96  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000bb9b  nop
0x18000bb9c  lea     rcx, [rsp+4B0h+var_480]; this
0x18000bba1  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000bba6  mov     edi, 1
0x18000bbab  cmp     ebx, edi
0x18000bbad  jnz     short loc_18000BBB7
0x18000bbaf  mov     ebx, r12d
0x18000bbb2  jmp     loc_18000C182
0x18000bbb7  mov     ecx, ebx; int
0x18000bbb9  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000bbbe  test    eax, eax
0x18000bbc0  jz      loc_18000C182
0x18000bbc6  cmp     cs:?g_bAdmin_Privileges@@3HA, r12d; int g_bAdmin_Privileges
0x18000bbcd  setz    al
0x18000bbd0  mov     rcx, [rbp+3B8h]; this
0x18000bbd7  test    al, al
0x18000bbd9  jz      short loc_18000BC05
0x18000bbdb  mov     ebx, 80070005h
0x18000bbe0  mov     r9d, ebx; char *
0x18000bbe3  lea     r8, aShellOsshellCp_0; "shell\\osshell\\cpls\\intl\\cme.cpp"
0x18000bbea  mov     edx, 4D3h; void *
0x18000bbef  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000bbf4  mov     edx, ebx
0x18000bbf6  lea     rcx, [rsp+4B0h+var_460]
0x18000bbfb  call    ?Stop@?$ActivityBase@VIntlCplTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000bc00  jmp     loc_18000C1B0
0x18000bc05  mov     r9d, 55h ; 'U'; cchData
0x18000bc0b  lea     r8, [rbp+3B0h+LCData]; lpLCData
0x18000bc12  mov     r13d, 1004h
0x18000bc18  mov     edx, r13d; LCType
0x18000bc1b  mov     esi, 800h
0x18000bc20  mov     ecx, esi; Locale
0x18000bc22  call    cs:__imp_GetLocaleInfoW
0x18000bc28  test    eax, eax
0x18000bc2a  jnz     short loc_18000BC4B
0x18000bc2c  call    cs:__imp_GetLastError
0x18000bc32  mov     edx, 4E5h; void *
0x18000bc37  mov     rcx, [rbp+3B8h]; this
0x18000bc3e  mov     r9d, eax; char *
0x18000bc41  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18000bc46  jmp     loc_18000C182
0x18000bc4b  mov     r9d, 55h ; 'U'; cchData
0x18000bc51  lea     r8, [rbp+3B0h+var_100]; lpLCData
0x18000bc58  mov     edx, 1011h; LCType
0x18000bc5d  mov     ecx, esi; Locale
0x18000bc5f  call    cs:__imp_GetLocaleInfoW
0x18000bc65  test    eax, eax
0x18000bc67  jnz     short loc_18000BC76
0x18000bc69  call    cs:__imp_GetLastError
0x18000bc6f  mov     edx, 4EDh
0x18000bc74  jmp     short loc_18000BC37
0x18000bc76  mov     r9d, 55h ; 'U'; cchData
0x18000bc7c  lea     r8, [rbp+3B0h+var_1B0]; lpLCData
0x18000bc83  lea     edx, [r9-4Ah]; LCType
0x18000bc87  mov     ecx, esi; Locale
0x18000bc89  call    cs:__imp_GetLocaleInfoW
0x18000bc8f  test    eax, eax
0x18000bc91  jnz     short loc_18000BCA0
0x18000bc93  call    cs:__imp_GetLastError
0x18000bc99  mov     edx, 4F5h
0x18000bc9e  jmp     short loc_18000BC37
0x18000bca0  lea     rdx, ?NAME_ATTR@@3PAGA; "Name"
0x18000bca7  lea     rcx, [rsp+4B0h+var_480]; this
0x18000bcac  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000bcb1  nop
0x18000bcb2  mov     rdx, [rax]
0x18000bcb5  test    rdx, rdx
0x18000bcb8  jz      short loc_18000BCBF
0x18000bcba  mov     rdx, [rdx]
0x18000bcbd  jmp     short loc_18000BCC2
0x18000bcbf  mov     rdx, r12; unsigned __int16 *
0x18000bcc2  lea     r8, [rsp+4B0h+lpName]; unsigned __int16 **
0x18000bcc7  mov     rcx, [rsp+4B0h+var_488]; struct IXMLDOMNode *
0x18000bccc  call    ?GetAttribute@@YAJPEAUIXMLDOMNode@@PEAGPEAPEAG@Z; GetAttribute(IXMLDOMNode *,ushort *,ushort * *)
0x18000bcd1  mov     ebx, eax
0x18000bcd3  lea     rcx, [rsp+4B0h+var_480]; this
0x18000bcd8  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000bcdd  cmp     ebx, edi
0x18000bcdf  jz      loc_18000C17D
0x18000bce5  mov     ecx, ebx; int
0x18000bce7  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000bcec  test    eax, eax
0x18000bcee  jz      loc_18000C17D
0x18000bcf4  mov     edx, 102h
0x18000bcf9  mov     r14, [rsp+4B0h+lpName]
0x18000bcfe  mov     rcx, r14
0x18000bd01  call    cs:__imp_NlsCheckPolicy
0x18000bd07  cmp     eax, 4ECh
0x18000bd0c  jnz     short loc_18000BD15
0x18000bd0e  mov     ebx, edi
0x18000bd10  jmp     loc_18000C182
0x18000bd15  xor     edx, edx; dwFlags
0x18000bd17  mov     rcx, r14; lpName
0x18000bd1a  call    cs:__imp_LocaleNameToLCID
0x18000bd20  mov     r15d, eax
0x18000bd23  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000bd27  mov     rcx, rsi
0x18000bd2a  inc     rcx
0x18000bd2d  cmp     [r14+rcx*2], r12w
0x18000bd32  jnz     short loc_18000BD2A
0x18000bd34  test    ecx, ecx
0x18000bd36  jz      short loc_18000BD0E
0x18000bd38  test    r15d, r15d
0x18000bd3b  jz      short loc_18000BD0E
0x18000bd3d  mov     edx, 2; dwFlags
0x18000bd42  mov     ecx, r15d; Locale
0x18000bd45  call    cs:__imp_IsValidLocale
0x18000bd4b  test    eax, eax
0x18000bd4d  jz      short loc_18000BD0E
0x18000bd4f  mov     r9d, 55h ; 'U'; cchData
0x18000bd55  lea     r8, [rbp+3B0h+String1]; lpLCData
0x18000bd5c  mov     edx, r13d; LCType
0x18000bd5f  mov     ecx, r15d; Locale
0x18000bd62  call    cs:__imp_GetLocaleInfoW
0x18000bd68  test    eax, eax
0x18000bd6a  jnz     short loc_18000BD7C
0x18000bd6c  call    cs:__imp_GetLastError
0x18000bd72  mov     edx, 520h
0x18000bd77  jmp     loc_18000BC37
0x18000bd7c  lea     rdx, a0; "0"
0x18000bd83  lea     rcx, [rbp+3B0h+String1]; lpString1
0x18000bd8a  call    cs:__imp_lstrcmpW
0x18000bd90  test    eax, eax
0x18000bd92  jz      loc_18000BD0E
0x18000bd98  lea     rax, [rbp+3B0h+String1]
0x18000bd9f  mov     r9, rsi
0x18000bda2  inc     r9
0x18000bda5  cmp     [rax+r9*2], r12w
0x18000bdaa  jnz     short loc_18000BDA2
0x18000bdac  lea     r9d, ds:2[r9*2]; cbData
0x18000bdb4  lea     r8, [rbp+3B0h+String1]; lpData
0x18000bdbb  lea     rdx, ?c_szAcpValName@@3PAGA; "ACP"
0x18000bdc2  lea     rcx, ?g_szCodePages@@3PAGA; "SYSTEM\\CurrentControlSet\\Control\\Nls"...
0x18000bdc9  call    ?WriteValueToRegistry@@YAKPEBG00K@Z; WriteValueToRegistry(ushort const *,ushort const *,ushort const *,ulong)
0x18000bdce  test    eax, eax
0x18000bdd0  jz      short loc_18000BDDC
0x18000bdd2  mov     edx, 534h
0x18000bdd7  jmp     loc_18000BC37
0x18000bddc  mov     r13d, 55h ; 'U'
0x18000bde2  mov     r9d, r13d; cchData
0x18000bde5  lea     r8, [rbp+3B0h+String1]; lpLCData
0x18000bdec  mov     edx, 1011h; LCType
0x18000bdf1  mov     ecx, r15d; Locale
0x18000bdf4  call    cs:__imp_GetLocaleInfoW
0x18000bdfa  test    eax, eax
0x18000bdfc  jnz     short loc_18000BE0B
0x18000bdfe  call    cs:__imp_GetLastError
0x18000be04  mov     edx, 541h
0x18000be09  jmp     short loc_18000BE76
0x18000be0b  lea     rax, [rbp+3B0h+String1]
0x18000be12  mov     r9, rsi
0x18000be15  inc     r9
0x18000be18  cmp     [rax+r9*2], r12w
0x18000be1d  jnz     short loc_18000BE15
0x18000be1f  lea     r9d, ds:2[r9*2]; cbData
0x18000be27  lea     r8, [rbp+3B0h+String1]; lpData
0x18000be2e  lea     rdx, ?c_szMaccpValName@@3PAGA; "MACCP"
0x18000be35  lea     rcx, ?g_szCodePages@@3PAGA; "SYSTEM\\CurrentControlSet\\Control\\Nls"...
0x18000be3c  call    ?WriteValueToRegistry@@YAKPEBG00K@Z; WriteValueToRegistry(ushort const *,ushort const *,ushort const *,ulong)
0x18000be41  test    eax, eax
0x18000be43  jz      short loc_18000BE4F
0x18000be45  mov     edx, 54Dh
0x18000be4a  jmp     loc_18000BFCB
0x18000be4f  mov     r9d, r13d; cchData
0x18000be52  lea     r8, [rbp+3B0h+String1]; lpLCData
0x18000be59  mov     edx, 0Bh; LCType
0x18000be5e  mov     ecx, r15d; Locale
0x18000be61  call    cs:__imp_GetLocaleInfoW
0x18000be67  test    eax, eax
0x18000be69  jnz     short loc_18000BE94
0x18000be6b  call    cs:__imp_GetLastError
0x18000be71  mov     edx, 556h; void *
0x18000be76  mov     edi, eax
0x18000be78  mov     r9d, eax; char *
0x18000be7b  mov     rcx, [rbp+3B8h]; this
0x18000be82  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18000be87  test    edi, edi
0x18000be89  jz      loc_18000C182
0x18000be8f  jmp     loc_18000BFDA
0x18000be94  lea     rax, [rbp+3B0h+String1]
0x18000be9b  mov     r9, rsi
0x18000be9e  inc     r9
0x18000bea1  cmp     [rax+r9*2], r12w
0x18000bea6  jnz     short loc_18000BE9E
0x18000bea8  lea     r9d, ds:2[r9*2]; cbData
0x18000beb0  lea     r8, [rbp+3B0h+String1]; lpData
0x18000beb7  lea     rdx, ?c_szOemcpValName@@3PAGA; "OEMCP"
0x18000bebe  lea     rcx, ?g_szCodePages@@3PAGA; "SYSTEM\\CurrentControlSet\\Control\\Nls"...
0x18000bec5  call    ?WriteValueToRegistry@@YAKPEBG00K@Z; WriteValueToRegistry(ushort const *,ushort const *,ushort const *,ulong)
0x18000beca  test    eax, eax
0x18000becc  jz      short loc_18000BED8
0x18000bece  mov     edx, 560h
0x18000bed3  jmp     loc_18000BFCB
0x18000bed8  mov     r9d, r15d
0x18000bedb  lea     r8, a4x; "%.4x"
0x18000bee2  mov     rdx, r13; unsigned __int64
0x18000bee5  lea     rcx, [rbp+3B0h+String1]; unsigned __int16 *
0x18000beec  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000bef1  mov     ebx, eax
0x18000bef3  mov     rcx, [rbp+3B8h]; this
0x18000befa  test    eax, eax
0x18000befc  jns     short loc_18000BF17
0x18000befe  mov     edx, 568h; void *
0x18000bf03  lea     r8, aShellOsshellCp_0; "shell\\osshell\\cpls\\intl\\cme.cpp"
0x18000bf0a  mov     r9d, eax; char *
0x18000bf0d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000bf12  jmp     loc_18000C182
0x18000bf17  lea     rax, [rbp+3B0h+String1]
0x18000bf1e  mov     r9, rsi
0x18000bf21  inc     r9
0x18000bf24  cmp     [rax+r9*2], r12w
0x18000bf29  jnz     short loc_18000BF21
0x18000bf2b  lea     r9d, ds:2[r9*2]; cbData
0x18000bf33  lea     r8, [rbp+3B0h+String1]; lpData
0x18000bf3a  lea     rdx, ?c_szLangValName@@3PAGA; "Default"
0x18000bf41  lea     rcx, ?c_szLanguages@@3PAGA; "System\\CurrentControlSet\\Control\\Nls"...
0x18000bf48  call    ?WriteValueToRegistry@@YAKPEBG00K@Z; WriteValueToRegistry(ushort const *,ushort const *,ushort const *,ulong)
0x18000bf4d  test    eax, eax
0x18000bf4f  jz      short loc_18000BF58
0x18000bf51  mov     edx, 573h
0x18000bf56  jmp     short loc_18000BFCB
0x18000bf58  mov     r9d, r15d
0x18000bf5b  lea     r8, a8x; "%.8x"
0x18000bf62  mov     rdx, r13; unsigned __int64
0x18000bf65  lea     rcx, [rbp+3B0h+String1]; unsigned __int16 *
0x18000bf6c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000bf71  mov     ebx, eax
0x18000bf73  mov     rcx, [rbp+3B8h]
0x18000bf7a  test    eax, eax
0x18000bf7c  jns     short loc_18000BF88
0x18000bf7e  mov     edx, 579h
0x18000bf83  jmp     loc_18000BF03
0x18000bf88  lea     rax, [rbp+3B0h+String1]
0x18000bf8f  mov     r9, rsi
0x18000bf92  inc     r9
  ... truncated ...
```
