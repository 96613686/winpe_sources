# MvSetLanguageAndRegion(ushort const *,ushort const *,ushort *)

- ea: `0x18002ef84`
- end: `0x18002f796`
- name: `?MvSetLanguageAndRegion@@YAJPEBG0PEAG@Z`
- size: `2066`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800162f0`

## callees

- `0x1800010c8`
- `0x1800011ac`
- `0x180001238`
- `0x1800018ec`
- `0x180001a14`
- `0x1800098dc`
- `0x180009900`
- `0x18000b030`
- `0x18002d8b0`
- `0x18002db60`
- `0x18002e6a8`
- `0x18002e904`
- `0x18002edf0`
- `0x18002ef84`
- `0x18002f79c`
- `0x18004371a`
- `0x180043750`

## import_xrefs

- `msvcrt!wcstok_s` at `0x18002f4f8`
- `msvcrt!wcstok_s` at `0x18002f4f8`
- `msvcrt!_wcsicmp` at `0x18002f6aa`
- `msvcrt!_wcsicmp` at `0x18002f6aa`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002f520`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002f628`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002f747`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002f520`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002f628`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002f747`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002f2de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002f654`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002f2de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002f654`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f27c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f2c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f542`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f57b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f600`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f672`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f76d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f27c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f2c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f542`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f57b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f600`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f672`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f76d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f5bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f5bc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002f1e5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002f1e5`
- `api-ms-win-core-localization-l1-2-0!SetUserGeoID` at `0x18002f13b`
- `api-ms-win-core-localization-l1-2-0!SetUserGeoID` at `0x18002f13b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002f3f3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002f41e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002f449`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002f3f3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002f41e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002f449`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f145`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f145`
- `provdatastore!MvDsGetInfoFromMcc` at `0x18002efe6`
- `provdatastore!MvDsGetInfoFromMcc` at `0x18002efe6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f4b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f615`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f68b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f4b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f615`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f68b`
- `Bcp47Langs!Bcp47Normalize` at `0x18002f5d3`
- `Bcp47Langs!Bcp47Normalize` at `0x18002f5d3`
- `Bcp47Langs!GetUserLanguages` at `0x18002f291`
- `Bcp47Langs!GetUserLanguages` at `0x18002f291`
- `WinLangdb!GetLocaleFromLanguageAndRegion` at `0x18002f48a`
- `WinLangdb!GetLocaleFromLanguageAndRegion` at `0x18002f48a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
int __fastcall MvSetLanguageAndRegion(const unsigned __int16 *a1, wchar_t *a2, unsigned __int16 *a3)
{
  signed int v5; // ebx
  __int64 v6; // r15
  unsigned __int64 v7; // rsi
  int InfoFromMcc; // eax
  __int64 v9; // r8
  unsigned __int16 *v10; // rax
  unsigned int UserLanguages; // edi
  __int64 v12; // rdx
  GEOID v14; // r14d
  __int64 v15; // rdx
  unsigned __int16 *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  signed int LastError; // eax
  unsigned int ValueW; // eax
  const char *v22; // r9
  __int64 v23; // rdx
  __int64 v24; // rdi
  PCWSTR StringRawBuffer; // rax
  __int64 v26; // r9
  __int64 v27; // rdx
  wchar_t *v28; // r8
  WCHAR v29; // cx
  wchar_t *v30; // rcx
  wchar_t *i; // rcx
  __int64 v32; // r9
  WCHAR *v33; // rdi
  int v34; // eax
  const wchar_t *v35; // rcx
  wchar_t *v36; // rax
  int v37; // edx
  unsigned int v38; // r8d
  HRESULT v39; // eax
  int v40; // edx
  unsigned int v41; // r8d
  int v42; // eax
  char *v43; // rax
  const wchar_t *v44; // rcx
  const unsigned __int16 *v45; // rcx
  __int64 v46; // r9
  wchar_t **v47; // rax
  int pdwType; // [rsp+20h] [rbp-E0h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-E0h]
  HSTRING v50; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING string; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Delimiter[2]; // [rsp+58h] [rbp-A8h] BYREF
  UINT32 length; // [rsp+5Ch] [rbp-A4h] BYREF
  int pvData; // [rsp+60h] [rbp-A0h] BYREF
  DWORD pcbData; // [rsp+64h] [rbp-9Ch] BYREF
  wchar_t *Context; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *String1[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v59; // [rsp+80h] [rbp-80h]
  unsigned __int64 v60; // [rsp+88h] [rbp-78h]
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp-70h] BYREF
  HSTRING v62; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 Src[8]; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t String2[88]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v65[88]; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  v5 = 0;
  v6 = 0;
  *(_QWORD *)Src = 0;
  v7 = -1;
  if ( a1 )
  {
    InfoFromMcc = MvDsGetInfoFromMcc(a1, L"iso3166", Src, 4u);
    v5 = InfoFromMcc;
    if ( InfoFromMcc < 0 )
    {
      if ( InfoFromMcc != -2147024894 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x214,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
          (const char *)(unsigned int)InfoFromMcc,
          pdwType);
        return v5;
      }
      v5 = 0;
    }
    else
    {
      v9 = 4;
      v10 = Src;
      do
      {
        if ( !*v10 )
          break;
        ++v10;
        --v9;
      }
      while ( v9 );
      UserLanguages = v9 == 0 ? 0x80070057 : 0;
      v6 = (4 - v9) & -(__int64)(v9 != 0);
      if ( !v9 )
      {
        v12 = 526;
LABEL_8:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v12,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
          (const char *)UserLanguages,
          pdwType);
        return UserLanguages;
      }
      if ( v6 != 2 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x20F,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
          (const char *)0x80070057LL,
          pdwType);
        return -2147024809;
      }
      v14 = MvGeoIdFromIso3166(Src);
      if ( v14 != -1 )
        goto LABEL_24;
    }
  }
  if ( a2 )
  {
    v14 = MvGeoIdFromIccid(a2, Src);
    v15 = 0x7FFFFFFF;
    v16 = Src;
    do
    {
      if ( !*v16 )
        break;
      ++v16;
      --v15;
    }
    while ( v15 );
    UserLanguages = v15 == 0 ? 0x80070057 : 0;
    v6 = (0x7FFFFFFF - v15) & -(__int64)(v15 != 0);
    if ( !v15 )
    {
      v12 = 544;
      goto LABEL_8;
    }
    if ( v14 != -1 )
    {
LABEL_24:
      if ( !SetUserGeoID(v14) )
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
      }
      if ( (unsigned int)dword_18005A000 > 5 )
      {
        length = v5;
        LODWORD(v50) = v14;
        pv = Src;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v17,
          (__int64)&unk_18004FCC8,
          v18,
          v19,
          (__int64 **)&pv,
          (__int64)&v50,
          (__int64)&length);
      }
    }
  }
  pvData = 0;
  pcbData = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Multivariant",
             L"DisableSIMBLD",
             0x10u,
             0,
             &pvData,
             &pcbData);
  v22 = 0;
  if ( ValueW != 2 )
    v22 = (const char *)ValueW;
  if ( (_DWORD)v22 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x23C,
             (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
             v22,
             pdwTypea);
  if ( !pvData )
  {
    memset_0(String2, 0, 0xAAu);
    wcscpy(Delimiter, L";");
    string = 0;
    WindowsDeleteString(0);
    string = 0;
    UserLanguages = GetUserLanguages(Delimiter[0], &string);
    if ( (UserLanguages & 0x80000000) != 0 )
    {
      v23 = 586;
      goto LABEL_38;
    }
    v24 = 2147483646;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v27 = 85;
    v28 = String2;
    do
    {
      if ( !v24 )
        break;
      v29 = *StringRawBuffer;
      if ( !*StringRawBuffer )
        break;
      ++StringRawBuffer;
      *v28++ = v29;
      --v24;
      --v27;
    }
    while ( v27 );
    UserLanguages = v27 == 0 ? 0x8007007A : 0;
    v30 = v28 - 1;
    if ( v27 )
      v30 = v28;
    *v30 = 0;
    if ( !v27 )
    {
      v23 = 588;
LABEL_38:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v23,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
        (const char *)UserLanguages,
        pdwTypea);
LABEL_39:
      if ( string )
        WindowsDeleteString(string);
      return UserLanguages;
    }
    if ( (unsigned int)dword_18005A000 > 4 )
    {
      pv = String2;
      v50 = (HSTRING)a3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (__int64)v30,
        (__int64)&unk_18004FD60,
        (__int64)v28,
        v26,
        (__int64 **)&v50,
        (__int64 **)&pv);
    }
    if ( !a3 || !*a3 )
    {
LABEL_76:
      if ( string )
        WindowsDeleteString(string);
      return 0;
    }
    v60 = 7;
    v59 = 0;
    LOWORD(String1[0]) = 0;
    Context = 0;
    for ( i = a3; ; i = 0 )
    {
      v36 = wcstok_s(i, Delimiter, &Context);
      v33 = v36;
      if ( !v36 )
        break;
      if ( !a2 || MvIsLanguageExcludedForIccid(a2, v36) )
      {
        if ( (unsigned int)dword_18005A000 > 3 )
        {
          v50 = (HSTRING)v33;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (__int64)&dword_18005A000,
            (__int64)&word_18004FBE6,
            0,
            v32,
            (__int64 **)&v50);
        }
      }
      else
      {
        memset_0(v65, 0, 0xAAu);
        if ( !v6 )
        {
          if ( CompareStringOrdinal(v33, -1, L"en", -1, 1) == 2 )
          {
            v33 = L"en-GB";
          }
          else if ( CompareStringOrdinal(v33, -1, L"pt", -1, 1) == 2 )
          {
            v33 = L"pt-PT";
          }
          else
          {
            v34 = CompareStringOrdinal(v33, -1, L"es", -1, 1);
            v35 = L"es-MX";
            if ( v34 != 2 )
              v35 = v33;
            v33 = (WCHAR *)v35;
          }
        }
        pv = 0;
        if ( (int)GetLocaleFromLanguageAndRegion(
                    v33,
                    (unsigned __int64)Src & ((unsigned __int128)-(__int128)(unsigned __int64)v6 >> 64),
                    3 - (unsigned int)(v6 != 0),
                    &pv) >= 0
          && (int)GetAssociatedInstalledMuiLanguageForPhone((PCWSTR)pv, v65) >= 0 )
        {
          v50 = 0;
          WindowsDeleteString(0);
          v50 = 0;
          v62 = 0;
          do
            ++v7;
          while ( *((_WORD *)pv + v7) );
          if ( v7 > 0xFFFFFFFF )
          {
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v37, v38);
            __debugbreak();
          }
          if ( (int)v7 + 1 < (unsigned int)v7 )
          {
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v37, v38);
            JUMPOUT(0x18002F795LL);
          }
          v39 = WindowsCreateStringReference((PCWSTR)pv, v7, &hstringHeader, &v62);
          if ( v39 < 0 )
          {
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v39, v40, v41);
            __debugbreak();
          }
          v42 = Bcp47Normalize(v62, &v50);
          UserLanguages = v42;
          if ( v42 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x28E,
              (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
              (const char *)(unsigned int)v42,
              pdwTypea);
            WindowsDeleteString(v50);
            v50 = 0;
            if ( pv )
              CoTaskMemFree(pv);
            if ( v60 >= 8 )
              operator delete(String1[0]);
            v60 = 7;
            v59 = 0;
            LOWORD(String1[0]) = 0;
            goto LABEL_39;
          }
          length = 0;
          v43 = (char *)WindowsGetStringRawBuffer(v50, &length);
          std::wstring::assign(String1, v43, length);
          WindowsDeleteString(v50);
          v50 = 0;
          if ( pv )
            CoTaskMemFree(pv);
          break;
        }
        if ( pv )
          CoTaskMemFree(pv);
      }
    }
    if ( !v59 )
      goto LABEL_73;
    v44 = (const wchar_t *)String1;
    if ( v60 >= 8 )
      v44 = String1[0];
    if ( !_wcsicmp(v44, String2) )
    {
LABEL_73:
      if ( v60 >= 8 )
        operator delete(String1[0]);
      v60 = 7;
      v59 = 0;
      LOWORD(String1[0]) = 0;
      goto LABEL_76;
    }
    v45 = (const unsigned __int16 *)String1;
    if ( v60 >= 8 )
      v45 = String1[0];
    MvSetCurrentUserProfileLanguages(v45);
    if ( (unsigned int)dword_18005A000 > 5 )
    {
      LODWORD(v50) = v5;
      v47 = String1;
      if ( v60 >= 8 )
        v47 = (wchar_t **)String1[0];
      pv = v47;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (__int64)&dword_18005A000,
        (__int64)&dword_18004FC6C,
        0,
        v46,
        (__int64 **)&pv,
        (__int64)&v50);
    }
    if ( v5 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2AF,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
        (const char *)(unsigned int)v5,
        pdwTypea);
    if ( v60 >= 8 )
      operator delete(String1[0]);
    v60 = 7;
    v59 = 0;
    LOWORD(String1[0]) = 0;
    if ( string )
      WindowsDeleteString(string);
    return v5;
  }
  if ( (unsigned int)dword_18005A000 > 4 )
    tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, word_18004FCAA, 0, 0, 2, &hstringHeader);
  return 0;
}

```

## disassembly

```asm
0x18002ef84  mov     [rsp-8+arg_18], rbx
0x18002ef89  push    rbp
0x18002ef8a  push    rsi
0x18002ef8b  push    rdi
0x18002ef8c  push    r12
0x18002ef8e  push    r13
0x18002ef90  push    r14
0x18002ef92  push    r15
0x18002ef94  lea     rbp, [rsp-130h]
0x18002ef9c  sub     rsp, 230h
0x18002efa3  mov     rax, cs:__security_cookie
0x18002efaa  xor     rax, rsp
0x18002efad  mov     [rbp+160h+var_40], rax
0x18002efb4  mov     r12, r8
0x18002efb7  mov     r13, rdx
0x18002efba  xor     r14d, r14d
0x18002efbd  mov     ebx, r14d
0x18002efc0  mov     r15d, r14d
0x18002efc3  mov     qword ptr [rbp+160h+Src], r14
0x18002efc7  lea     edi, [r14+4]
0x18002efcb  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002efcf  test    rcx, rcx
0x18002efd2  jz      loc_18002F09B
0x18002efd8  mov     r9d, edi
0x18002efdb  lea     r8, [rbp+160h+Src]
0x18002efdf  lea     rdx, ?gc_wszISO3166@@3QBGB; "iso3166"
0x18002efe6  call    cs:__imp_?MvDsGetInfoFromMcc@@YAJPEBG0PEAGK@Z; MvDsGetInfoFromMcc(ushort const *,ushort const *,ushort *,ulong)
0x18002efec  mov     ebx, eax
0x18002efee  test    eax, eax
0x18002eff0  js      loc_18002F101
0x18002eff6  mov     r8d, edi
0x18002eff9  lea     rax, [rbp+160h+Src]
0x18002effd  cmp     [rax], r14w
0x18002f001  jz      short loc_18002F00D
0x18002f003  add     rax, 2
0x18002f007  sub     r8, 1
0x18002f00b  jnz     short loc_18002EFFD
0x18002f00d  mov     rax, r8
0x18002f010  neg     rax
0x18002f013  sbb     edi, edi
0x18002f015  not     edi
0x18002f017  mov     eax, 80070057h
0x18002f01c  and     edi, eax
0x18002f01e  mov     rcx, r8
0x18002f021  mov     edx, 4
0x18002f026  sub     rdx, r8
0x18002f029  neg     rcx
0x18002f02c  sbb     r15, r15
0x18002f02f  and     r15, rdx
0x18002f032  test    r8, r8
0x18002f035  jnz     short loc_18002F059
0x18002f037  mov     edx, 20Eh; void *
0x18002f03c  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002f043  mov     r9d, edi; char *
0x18002f046  mov     rcx, [rbp+168h]; this
0x18002f04d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f052  mov     eax, edi
0x18002f054  jmp     loc_18002F54A
0x18002f059  cmp     r15, 2
0x18002f05d  jz      short loc_18002F084
0x18002f05f  mov     rcx, [rbp+168h]; this
0x18002f066  mov     r9d, eax; char *
0x18002f069  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002f070  mov     edx, 20Fh; void *
0x18002f075  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f07a  mov     eax, 80070057h
0x18002f07f  jmp     loc_18002F54A
0x18002f084  lea     rcx, [rbp+160h+Src]; Src
0x18002f088  call    ?MvGeoIdFromIso3166@@YAJPEBG@Z; MvGeoIdFromIso3166(ushort const *)
0x18002f08d  mov     r14d, eax
0x18002f090  cmp     eax, esi
0x18002f092  jnz     loc_18002F138
0x18002f098  xor     r14d, r14d
0x18002f09b  test    r13, r13
0x18002f09e  jz      loc_18002F1A4
0x18002f0a4  lea     rdx, [rbp+160h+Src]; unsigned __int16 *
0x18002f0a8  mov     rcx, r13; String2
0x18002f0ab  call    ?MvGeoIdFromIccid@@YAJPEBGPEAG@Z; MvGeoIdFromIccid(ushort const *,ushort *)
0x18002f0b0  mov     r14d, eax
0x18002f0b3  mov     r8d, 7FFFFFFFh
0x18002f0b9  mov     edx, r8d
0x18002f0bc  lea     rax, [rbp+160h+Src]
0x18002f0c0  xor     r9d, r9d
0x18002f0c3  cmp     [rax], r9w
0x18002f0c7  jz      short loc_18002F0D3
0x18002f0c9  add     rax, 2
0x18002f0cd  sub     rdx, 1
0x18002f0d1  jnz     short loc_18002F0C3
0x18002f0d3  mov     rax, rdx
0x18002f0d6  neg     rax
0x18002f0d9  sbb     edi, edi
0x18002f0db  not     edi
0x18002f0dd  and     edi, 80070057h
0x18002f0e3  mov     rcx, rdx
0x18002f0e6  sub     r8, rdx
0x18002f0e9  neg     rcx
0x18002f0ec  sbb     r15, r15
0x18002f0ef  and     r15, r8
0x18002f0f2  test    rdx, rdx
0x18002f0f5  jnz     short loc_18002F133
0x18002f0f7  mov     edx, 220h
0x18002f0fc  jmp     loc_18002F03C
0x18002f101  cmp     ebx, 80070002h
0x18002f107  jz      short loc_18002F12B
0x18002f109  mov     rcx, [rbp+168h]; this
0x18002f110  mov     r9d, ebx; char *
0x18002f113  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002f11a  mov     edx, 214h; void *
0x18002f11f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f124  mov     eax, ebx
0x18002f126  jmp     loc_18002F54A
0x18002f12b  mov     ebx, r14d
0x18002f12e  jmp     loc_18002F09B
0x18002f133  cmp     r14d, esi
0x18002f136  jz      short loc_18002F1A1
0x18002f138  mov     ecx, r14d; GeoId
0x18002f13b  call    cs:__imp_SetUserGeoID
0x18002f141  test    eax, eax
0x18002f143  jnz     short loc_18002F15A
0x18002f145  call    cs:__imp_GetLastError
0x18002f14b  mov     ebx, eax
0x18002f14d  test    eax, eax
0x18002f14f  jle     short loc_18002F15A
0x18002f151  movzx   ebx, ax
0x18002f154  or      ebx, 80070000h
0x18002f15a  mov     eax, cs:dword_18005A000
0x18002f160  cmp     eax, 5
0x18002f163  jbe     short loc_18002F1A1
0x18002f165  mov     [rsp+260h+length], ebx
0x18002f169  mov     dword ptr [rsp+260h+var_220], r14d
0x18002f16e  lea     rax, [rbp+160h+Src]
0x18002f172  mov     [rsp+260h+pv], rax
0x18002f177  lea     rax, [rsp+260h+length]
0x18002f17c  mov     [rsp+260h+pcbData], rax
0x18002f181  lea     rax, [rsp+260h+var_220]
0x18002f186  mov     [rsp+260h+pvData], rax
0x18002f18b  lea     rax, [rsp+260h+pv]
0x18002f190  mov     [rsp+260h+pdwType], rax
0x18002f195  lea     rdx, unk_18004FCC8
0x18002f19c  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002f1a1  xor     r14d, r14d
0x18002f1a4  mov     [rsp+260h+var_200], r14d
0x18002f1a9  mov     [rsp+260h+var_1FC], 4
0x18002f1b1  lea     rax, [rsp+260h+var_1FC]
0x18002f1b6  mov     [rsp+260h+pcbData], rax; pcbData
0x18002f1bb  lea     rax, [rsp+260h+var_200]
0x18002f1c0  mov     [rsp+260h+pvData], rax; pvData
0x18002f1c5  mov     [rsp+260h+pdwType], r14; int
0x18002f1ca  mov     r9d, 10h; dwFlags
0x18002f1d0  lea     r8, ?gc_wszDisableSIMBLD@@3QBGB; "DisableSIMBLD"
0x18002f1d7  lea     rdx, ?gc_wszRegMultivariantReadOnly@@3QBGB; "Software\\Microsoft\\Multivariant"
0x18002f1de  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002f1e5  call    cs:__imp_RegGetValueW
0x18002f1eb  mov     r9d, r14d
0x18002f1ee  cmp     eax, 2
0x18002f1f1  cmovnz  r9d, eax; char *
0x18002f1f5  test    r9d, r9d
0x18002f1f8  jz      short loc_18002F217
0x18002f1fa  mov     rcx, [rbp+168h]; this
0x18002f201  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002f208  mov     edx, 23Ch; void *
0x18002f20d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002f212  jmp     loc_18002F54A
0x18002f217  cmp     [rsp+260h+var_200], r14d
0x18002f21c  jz      short loc_18002F25C
0x18002f21e  mov     eax, cs:dword_18005A000
0x18002f224  cmp     eax, 4
0x18002f227  jbe     loc_18002F548
0x18002f22d  lea     rax, [rbp+160h+hstringHeader]
0x18002f231  mov     [rsp+260h+pvData], rax
0x18002f236  mov     dword ptr [rsp+260h+pdwType], 2
0x18002f23e  xor     r9d, r9d
0x18002f241  xor     r8d, r8d
0x18002f244  lea     rdx, word_18004FCAA
0x18002f24b  lea     rcx, dword_18005A000
0x18002f252  call    _tlgWriteTransfer_EventWriteTransfer
0x18002f257  jmp     loc_18002F548
0x18002f25c  xor     edx, edx; Val
0x18002f25e  mov     r8d, 0AAh; Size
0x18002f264  lea     rcx, [rbp+160h+String2]; void *
0x18002f268  call    memset_0
0x18002f26d  mov     dword ptr [rsp+260h+Delimiter], 3Bh ; ';'
0x18002f275  mov     [rsp+260h+string], r14
0x18002f27a  xor     ecx, ecx; string
0x18002f27c  call    cs:__imp_WindowsDeleteString
0x18002f282  mov     [rsp+260h+string], r14
0x18002f287  lea     rdx, [rsp+260h+string]
0x18002f28c  movzx   ecx, [rsp+260h+Delimiter]
0x18002f291  call    cs:__imp_GetUserLanguages
0x18002f297  mov     edi, eax
0x18002f299  test    eax, eax
0x18002f29b  jns     short loc_18002F2D2
0x18002f29d  mov     edx, 24Ah; void *
0x18002f2a2  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002f2a9  mov     r9d, edi; char *
0x18002f2ac  mov     rcx, [rbp+168h]; this
0x18002f2b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f2b8  nop
0x18002f2b9  mov     rcx, [rsp+260h+string]; string
0x18002f2be  test    rcx, rcx
0x18002f2c1  jz      loc_18002F052
0x18002f2c7  call    cs:__imp_WindowsDeleteString
0x18002f2cd  jmp     loc_18002F052
0x18002f2d2  mov     edi, 7FFFFFFEh
0x18002f2d7  xor     edx, edx; length
0x18002f2d9  mov     rcx, [rsp+260h+string]; string
0x18002f2de  call    cs:__imp_WindowsGetStringRawBuffer
0x18002f2e4  mov     edx, 55h ; 'U'
0x18002f2e9  lea     r8, [rbp+160h+String2]
0x18002f2ed  test    rdi, rdi
0x18002f2f0  jz      short loc_18002F30F
0x18002f2f2  movzx   ecx, word ptr [rax]
0x18002f2f5  test    cx, cx
0x18002f2f8  jz      short loc_18002F30F
0x18002f2fa  add     rax, 2
0x18002f2fe  mov     [r8], cx
0x18002f302  add     r8, 2
0x18002f306  dec     rdi
0x18002f309  sub     rdx, 1
0x18002f30d  jnz     short loc_18002F2ED
0x18002f30f  mov     rax, rdx
0x18002f312  neg     rax
0x18002f315  sbb     edi, edi
0x18002f317  not     edi
0x18002f319  and     edi, 8007007Ah
0x18002f31f  lea     rcx, [r8-2]
0x18002f323  test    rdx, rdx
0x18002f326  cmovnz  rcx, r8
0x18002f32a  mov     [rcx], r14w
0x18002f32e  jnz     short loc_18002F33A
0x18002f330  mov     edx, 24Ch
0x18002f335  jmp     loc_18002F2A2
0x18002f33a  mov     eax, cs:dword_18005A000
0x18002f340  cmp     eax, 4
0x18002f343  jbe     short loc_18002F373
0x18002f345  lea     rax, [rbp+160h+String2]
0x18002f349  mov     [rsp+260h+pv], rax
0x18002f34e  mov     [rsp+260h+var_220], r12
0x18002f353  lea     rax, [rsp+260h+pv]
0x18002f358  mov     [rsp+260h+pvData], rax
0x18002f35d  lea     rax, [rsp+260h+var_220]
0x18002f362  mov     [rsp+260h+pdwType], rax
0x18002f367  lea     rdx, unk_18004FD60
0x18002f36e  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18002f373  test    r12, r12
0x18002f376  jz      loc_18002F538
0x18002f37c  cmp     r14w, [r12]
0x18002f381  jz      loc_18002F538
0x18002f387  mov     [rbp+160h+var_1D8], 7
0x18002f38f  mov     [rbp+160h+var_1E0], r14
0x18002f393  mov     word ptr [rsp+260h+String1], r14w
0x18002f399  mov     [rsp+260h+Context], r14
0x18002f39e  mov     rcx, r12
0x18002f3a1  jmp     loc_18002F4EE
0x18002f3a6  test    r13, r13
0x18002f3a9  jz      loc_18002F4BC
0x18002f3af  mov     rdx, rdi; unsigned __int16 *
0x18002f3b2  mov     rcx, r13; String1
0x18002f3b5  call    ?MvIsLanguageExcludedForIccid@@YA_NPEBG0@Z; MvIsLanguageExcludedForIccid(ushort const *,ushort const *)
0x18002f3ba  test    al, al
0x18002f3bc  jnz     loc_18002F4BC
0x18002f3c2  xor     edx, edx; Val
0x18002f3c4  mov     r8d, 0AAh; Size
0x18002f3ca  lea     rcx, [rbp+160h+var_F0]; void *
0x18002f3ce  call    memset_0
0x18002f3d3  test    r15, r15
0x18002f3d6  jnz     loc_18002F460
0x18002f3dc  mov     dword ptr [rsp+260h+pdwType], 1; bIgnoreCase
0x18002f3e4  mov     r9d, esi; cchCount2
0x18002f3e7  lea     r8, aEn; "en"
0x18002f3ee  mov     edx, esi; cchCount1
0x18002f3f0  mov     rcx, rdi; lpString1
0x18002f3f3  call    cs:__imp_CompareStringOrdinal
0x18002f3f9  cmp     eax, 2
0x18002f3fc  jnz     short loc_18002F407
0x18002f3fe  lea     rdi, aEnGb; "en-GB"
0x18002f405  jmp     short loc_18002F460
0x18002f407  mov     dword ptr [rsp+260h+pdwType], 1; bIgnoreCase
0x18002f40f  mov     r9d, esi; cchCount2
0x18002f412  lea     r8, aPt; "pt"
0x18002f419  mov     edx, esi; cchCount1
0x18002f41b  mov     rcx, rdi; lpString1
0x18002f41e  call    cs:__imp_CompareStringOrdinal
0x18002f424  cmp     eax, 2
0x18002f427  jnz     short loc_18002F432
0x18002f429  lea     rdi, aPtPt; "pt-PT"
0x18002f430  jmp     short loc_18002F460
0x18002f432  mov     dword ptr [rsp+260h+pdwType], 1; int
0x18002f43a  mov     r9d, esi; cchCount2
0x18002f43d  lea     r8, aEs; "es"
0x18002f444  mov     edx, esi; cchCount1
0x18002f446  mov     rcx, rdi; lpString1
0x18002f449  call    cs:__imp_CompareStringOrdinal
0x18002f44f  lea     rcx, aEsMx; "es-MX"
0x18002f456  cmp     eax, 2
0x18002f459  cmovnz  rcx, rdi
0x18002f45d  mov     rdi, rcx
0x18002f460  mov     rax, r15
0x18002f463  neg     rax
0x18002f466  sbb     r8d, r8d
  ... truncated ...
```
