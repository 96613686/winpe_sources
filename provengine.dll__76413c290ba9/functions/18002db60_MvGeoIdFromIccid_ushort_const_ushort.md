# MvGeoIdFromIccid(ushort const *,ushort *)

- ea: `0x18002db60`
- end: `0x18002e6a2`
- name: `?MvGeoIdFromIccid@@YAJPEBGPEAG@Z`
- size: `2882`
- prototype: `__int64 __fastcall(wchar_t *String2, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18002ef84`

## callees

- `0x1800011ac`
- `0x1800021b4`
- `0x18000adec`
- `0x180020bb4`
- `0x1800211f0`
- `0x180021cd8`
- `0x180021cf4`
- `0x18002d5a4`
- `0x18002d6b0`
- `0x18002d7d8`
- `0x18002db60`
- `0x18002e6a8`
- `0x18002f850`
- `0x18002f9bc`
- `0x18002f9f4`
- `0x180033630`
- `0x180043726`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18002df34`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18002dfa8`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18002df34`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18002dfa8`
- `msvcrt!_wcsnicmp` at `0x18002dc91`
- `msvcrt!_wcsnicmp` at `0x18002dc91`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002dddb`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002e488`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002e4d6`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002dddb`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002e488`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002e4d6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002dc03`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002dc03`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002dc62`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002dd3e`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002dc62`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002dd3e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dd9d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e498`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dd9d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e498`
- `api-ms-win-core-localization-l1-2-0!GetGeoInfoW` at `0x18002e140`
- `api-ms-win-core-localization-l1-2-0!GetGeoInfoW` at `0x18002e140`
- `XmlLite!CreateXmlReader` at `0x18002deb0`
- `XmlLite!CreateXmlReader` at `0x18002deb0`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18002de8a`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18002de8a`

## string_xrefs

- `0x18002ddf5`: `IccidToRegionTablePath`
- `0x18002de37`: `IccidToRegionTablePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall MvGeoIdFromIccid(wchar_t *String2, unsigned __int16 *a2)
{
  unsigned int v4; // eax
  DWORD v5; // ebx
  DWORD v6; // edi
  LSTATUS v7; // eax
  __int64 v8; // rax
  BYTE *v9; // rcx
  __int64 v10; // rdx
  WCHAR *v11; // r8
  WCHAR v12; // r9
  WCHAR *v13; // rcx
  __int64 v14; // r9
  unsigned int v15; // ebx
  int Configuration; // eax
  WCHAR *v18; // r15
  int v19; // eax
  __int64 v20; // r9
  HRESULT v21; // eax
  HRESULT v22; // eax
  int v23; // eax
  int v24; // eax
  _QWORD *v25; // rax
  __int64 v26; // rdx
  unsigned __int64 v27; // rcx
  unsigned __int64 v28; // rcx
  unsigned __int64 v29; // rbx
  __int64 v30; // rax
  void *v31; // rax
  _QWORD *v32; // rax
  __int64 v33; // rcx
  const wchar_t *v34; // r9
  __int64 v35; // rdx
  unsigned __int16 *v36; // r8
  wchar_t v37; // ax
  __int64 v38; // r9
  unsigned __int16 *v39; // rcx
  unsigned int v40; // r14d
  int v41; // eax
  int v42; // eax
  __int64 v43; // rax
  GEOID v44; // eax
  __int64 v45; // rax
  WCHAR *v46; // rcx
  __int64 v47; // rdx
  WCHAR v48; // r9
  unsigned __int16 *v49; // rcx
  wchar_t *v50; // rbx
  int v51; // eax
  DWORD v52; // ebx
  unsigned __int16 *v53; // rdi
  const unsigned __int16 **v54; // rax
  __int64 v55; // rbx
  int v56; // eax
  unsigned __int16 *v57; // rsi
  __int64 v58; // rdi
  __int64 v59; // rbx
  unsigned __int16 *v60; // rdx
  unsigned __int16 v61; // ax
  unsigned __int16 *v62; // rcx
  int v63; // eax
  int v64; // eax
  _QWORD *v65; // rbx
  int v66; // eax
  void *v67; // rcx
  IStream *v68; // rcx
  int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchValueName; // [rsp+44h] [rbp-BCh] BYREF
  int v73; // [rsp+48h] [rbp-B8h] BYREF
  void *ppvObject; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v75; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v76; // [rsp+60h] [rbp-A0h]
  int v77; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *String1; // [rsp+70h] [rbp-90h] BYREF
  __int128 v79; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v80; // [rsp+88h] [rbp-78h]
  __int64 v81; // [rsp+90h] [rbp-70h]
  __int64 v82; // [rsp+98h] [rbp-68h]
  HKEY hKey; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v84; // [rsp+A8h] [rbp-58h] BYREF
  IStream *ppstm; // [rsp+B0h] [rbp-50h] BYREF
  BYTE Data[8]; // [rsp+B8h] [rbp-48h] BYREF
  WCHAR GeoData[4]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v88[2]; // [rsp+C8h] [rbp-38h] BYREF
  wchar_t v89; // [rsp+CCh] [rbp-34h]
  WCHAR ValueName[8]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v91; // [rsp+E0h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  if ( a2 )
    *a2 = 0;
  *(_DWORD *)v88 = *(_DWORD *)L"89";
  v89 = a89[2];
  if ( !CheckDigits(String2, v88, 2u) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7E,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
      (const char *)0x80070057LL,
      phkResult);
  v76 = 0;
  v75 = (_QWORD *)std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,std::wstring>>>::_Buyheadnode(retaddr);
  hKey = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Multivariant\\IccidToRegionOverrides", 0, 1u, &hKey);
  if ( v4 != 2 )
  {
    if ( v4 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x86,
        (int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
        (const char *)v4,
        phkResulta);
    v5 = 0;
    v6 = 0;
    cchValueName = 21;
    cbData = 8;
    v7 = RegEnumValueW(hKey, 0, ValueName, &cchValueName, 0, 0, Data, &cbData);
    if ( v7 != 259 )
    {
      do
      {
        if ( !v7 && cchValueName > v5 && !_wcsnicmp(ValueName, String2, cchValueName) )
        {
          *(_WORD *)&Data[6] = 0;
          v8 = 2147483646;
          v9 = Data;
          v10 = 4;
          v11 = GeoData;
          do
          {
            if ( !v8 )
              break;
            v12 = *(_WORD *)v9;
            if ( !*(_WORD *)v9 )
              break;
            v9 += 2;
            *v11++ = v12;
            --v8;
            --v10;
          }
          while ( v10 );
          v13 = v11 - 1;
          if ( v10 )
            v13 = v11;
          *v13 = 0;
          if ( !v10 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xA2,
              (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
              (const char *)0x8007007ALL,
              phkResulta);
          v5 = cchValueName;
        }
        ++v6;
        cchValueName = 21;
        cbData = 8;
        v7 = RegEnumValueW(hKey, v6, ValueName, &cchValueName, 0, 0, Data, &cbData);
      }
      while ( v7 != 259 );
      if ( v5 )
      {
        if ( (unsigned int)dword_18005A000 > 4 )
        {
          *(_QWORD *)Data = GeoData;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (__int64)&dword_18005A000,
            (__int64)byte_18004FD35,
            0,
            v14,
            (__int64 **)Data);
        }
        v15 = MvGeoIdFromIso3166(GeoData);
        if ( hKey )
          RegCloseKey(hKey);
        std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Erase(
          &v75,
          v75[1]);
        v75[1] = v75;
        *v75 = v75;
        v75[2] = v75;
        v76 = 0;
        operator delete(v75);
        return v15;
      }
    }
  }
  cbData = 0;
  Configuration = MvGetConfiguration((char *)L"IccidToRegionTablePath", 0, &cbData);
  if ( Configuration < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB4,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
      (const char *)(unsigned int)Configuration,
      phkResulta);
  *(_OWORD *)ValueName = 0;
  v91 = 0;
  if ( (unsigned __int64)cbData >> 1 )
    std::vector<unsigned short>::_Reallocate(ValueName, (unsigned __int64)cbData >> 1);
  v18 = *(WCHAR **)ValueName;
  v19 = MvGetConfiguration((char *)L"IccidToRegionTablePath", *(PVOID *)ValueName, &cbData);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB8,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
      (const char *)(unsigned int)v19,
      phkResulta);
  if ( (unsigned int)dword_18005A000 > 4 )
  {
    *(_QWORD *)GeoData = v18;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)&dword_18005A000,
      (__int64)byte_18004FC13,
      0,
      v20,
      (__int64 **)GeoData);
  }
  ppstm = 0;
  v21 = SHCreateStreamOnFileW(v18, 0, &ppstm);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBF,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
      (const char *)(unsigned int)v21,
      phkResulta);
  ppvObject = 0;
  v22 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC2,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
      (const char *)(unsigned int)v22,
      phkResulta);
  v23 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC3,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
      (const char *)(unsigned int)v23,
      phkResulta);
  v24 = (*(__int64 (__fastcall **)(void *, IStream *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, ppstm);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC4,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
      (const char *)(unsigned int)v24,
      phkResulta);
  *(_QWORD *)GeoData = &v79;
  v79 = 0;
  v80 = 0;
  v81 = 0;
  v82 = 0;
  v25 = operator new(0x10u);
  if ( !v25 )
  {
    std::_Xbad_alloc();
    __debugbreak();
  }
  *(_QWORD *)&v79 = v25;
  *v25 = 0;
  v25[1] = 0;
  *(_QWORD *)v79 = &v79;
  v26 = v82;
  v27 = v80;
  if ( v80 <= v82 + 1 )
  {
    std::deque<IccidSegment>::_Growmap(&v79);
    v26 = v82;
    v27 = v80;
  }
  v28 = v27 - 1;
  v81 &= v28;
  v29 = v28 & (v81 + v26);
  v30 = *((_QWORD *)&v79 + 1);
  if ( !*(_QWORD *)(*((_QWORD *)&v79 + 1) + 8 * v29) )
  {
    v31 = operator new(0x18u);
    if ( !v31 )
    {
      std::_Xbad_alloc();
      __debugbreak();
    }
    *(_QWORD *)(*((_QWORD *)&v79 + 1) + 8 * v29) = v31;
    v30 = *((_QWORD *)&v79 + 1);
  }
  v32 = *(_QWORD **)(v30 + 8 * v29);
  *v32 = String2;
  v32[1] = 2;
  v33 = 2147483646;
  v34 = L"ZZ";
  v35 = 4;
  v36 = (unsigned __int16 *)(v32 + 2);
  do
  {
    if ( !v33 )
      break;
    v37 = *v34;
    if ( !*v34 )
      break;
    ++v34;
    *v36++ = v37;
    --v33;
    --v35;
  }
  while ( v35 );
  v38 = v35 == 0 ? 0x8007007A : 0;
  v39 = v36 - 1;
  if ( v35 )
    v39 = v36;
  *v39 = 0;
  if ( !v35 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x34,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
      (const char *)v38,
      phkResulta);
  ++v82;
  String1 = 0;
  v84 = 0;
  v77 = 0;
  v73 = 0;
  v40 = -1;
  while ( 1 )
  {
    v66 = (*(__int64 (__fastcall **)(void *, int *, unsigned __int16 *, __int64))(*(_QWORD *)ppvObject + 48LL))(
            ppvObject,
            &v77,
            v36,
            v38);
    if ( v66 || v40 != -1 )
      break;
    switch ( v77 )
    {
      case 1:
        if ( !v73 )
        {
          v63 = (*(__int64 (__fastcall **)(void *, wchar_t **, _QWORD))(*(_QWORD *)ppvObject + 112LL))(
                  ppvObject,
                  &String1,
                  0);
          if ( v63 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xDF,
              (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
              (const char *)(unsigned int)v63,
              phkResulta);
          if ( !wcscmp_0(String1, L"Segment") )
          {
            if ( *(_QWORD *)(std::stack<IccidSegment>::top(&v79) + 8) )
            {
              v65 = (_QWORD *)std::stack<IccidSegment>::top(&v79);
              *(_QWORD *)Data = *v65 + 2LL * *(_QWORD *)(std::stack<IccidSegment>::top(&v79) + 8);
              std::stack<IccidSegment>::emplace<unsigned short const *>(&v79, Data);
            }
            else
            {
              v64 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 192LL))(ppvObject, &v73);
              if ( v64 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0xE5,
                  (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
                  (const char *)(unsigned int)v64,
                  phkResulta);
            }
          }
        }
        break;
      case 3:
        if ( !v73 )
        {
          v50 = String1;
          if ( !wcscmp_0(String1, L"Digits") )
          {
            if ( *(_QWORD *)(std::stack<IccidSegment>::top(&v79) + 8) )
            {
              v50 = String1;
              goto LABEL_84;
            }
            cbData = 0;
            v51 = (*(__int64 (__fastcall **)(void *, unsigned __int16 **, DWORD *))(*(_QWORD *)ppvObject + 128LL))(
                    ppvObject,
                    &v84,
                    &cbData);
            if ( v51 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0xFA,
                (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
                (const char *)(unsigned int)v51,
                phkResulta);
            v52 = cbData;
            v53 = v84;
            v54 = (const unsigned __int16 **)std::stack<IccidSegment>::top(&v79);
            if ( CheckDigits(*v54, v53, v52) )
            {
              v55 = cbData;
              *(_QWORD *)(std::stack<IccidSegment>::top(&v79) + 8) = v55;
            }
          }
          else
          {
LABEL_84:
            if ( !wcscmp_0(v50, L"Region") )
            {
              v56 = (*(__int64 (__fastcall **)(void *, unsigned __int16 **, _QWORD))(*(_QWORD *)ppvObject + 128LL))(
                      ppvObject,
                      &v84,
                      0);
              if ( v56 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x103,
                  (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
                  (const char *)(unsigned int)v56,
                  phkResulta);
              v57 = v84;
              v58 = 2147483646;
              v59 = 4;
              v60 = (unsigned __int16 *)(std::stack<IccidSegment>::top(&v79) + 16);
              do
              {
                if ( !v58 )
                  break;
                v61 = *v57;
                if ( !*v57 )
                  break;
                ++v57;
                *v60++ = v61;
                --v58;
                --v59;
              }
              while ( v59 );
              v38 = v59 == 0 ? 0x8007007A : 0;
              v62 = v60 - 1;
              if ( v59 )
                v62 = v60;
              *v62 = 0;
              if ( !v59 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x105,
                  (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
                  (const char *)v38,
                  phkResulta);
            }
          }
        }
        break;
      case 15:
        if ( !v73 )
          goto LABEL_58;
        cbData = 0;
        v41 = (*(__int64 (__fastcall **)(void *, DWORD *))(*(_QWORD *)ppvObject + 192LL))(ppvObject, &cbData);
        if ( v41 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x10D,
            (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
            (const char *)(unsigned int)v41,
            phkResulta);
        if ( cbData == v73 )
        {
LABEL_58:
          v42 = (*(__int64 (__fastcall **)(void *, wchar_t **, _QWORD))(*(_QWORD *)ppvObject + 112LL))(
                  ppvObject,
                  &String1,
                  0);
          if ( v42 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x117,
              (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
              (const char *)(unsigned int)v42,
              phkResulta);
          if ( !wcscmp_0(String1, L"Segment") )
          {
            if ( *(_QWORD *)(std::stack<IccidSegment>::top(&v79) + 8) )
            {
              v43 = std::stack<IccidSegment>::top(&v79);
              v44 = MvGeoIdFromIso3166((const unsigned __int16 *)(v43 + 16));
              v40 = v44;
              if ( v44 != -1 )
              {
                if ( !GetGeoInfoW(v44, 4u, GeoData, 4, 0) )
                  wil::details::in1diag3::Throw_GetLastError(
                    retaddr,
                    (void *)0x121,
                    (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
                    (const char *)v38);
                if ( a2 )
                {
                  v45 = 2147483646;
                  v46 = GeoData;
                  v47 = 4;
                  v36 = a2;
                  do
                  {
                    if ( !v45 )
                      break;
                    v48 = *v46;
                    if ( !*v46 )
                      break;
                    ++v46;
                    *v36++ = v48;
                    --v45;
                    --v47;
                  }
                  while ( v47 );
                  v38 = v47 == 0 ? 0x8007007A : 0;
                  v49 = v36 - 1;
                  if ( v47 )
                    v49 = v36;
                  *v49 = 0;
                  if ( !v47 )
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0x125,
                      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
                      (const char *)v38,
                      phkResulta);
                }
                if ( (unsigned int)dword_18005A000 > 4 )
                {
                  *(_QWORD *)Data = GeoData;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
                    (__int64)&dword_18005A000,
                    (__int64)byte_18004FBB5,
                    0,
                    v38,
                    (__int64 **)Data);
                }
              }
            }
            else
            {
              if ( v82 )
              {
                if ( !--v82 )
                  v81 = 0;
              }
              v73 = 0;
            }
          }
        }
        break;
    }
  }
  if ( v66 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13F,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
      (const char *)(unsigned int)v66,
      phkResulta);
  std::deque<_CategoryNode *>::~deque<_CategoryNode *>(&v79);
  v67 = ppvObject;
  if ( ppvObject )
  {
    ppvObject = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v67 + 16LL))(v67);
  }
  v68 = ppstm;
  if ( ppstm )
  {
    ppstm = 0;
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)v68 + 16LL))(v68);
  }
  if ( v18 )
    operator delete(v18);
  if ( hKey )
    RegCloseKey(hKey);
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Erase(
    &v75,
    v75[1]);
  v75[1] = v75;
  *v75 = v75;
  v75[2] = v75;
  v76 = 0;
  operator delete(v75);
  return v40;
}

```

## disassembly

```asm
0x18002db60  mov     [rsp-8+arg_10], rbx
0x18002db65  push    rbp
0x18002db66  push    rsi
0x18002db67  push    rdi
0x18002db68  push    r12
0x18002db6a  push    r13
0x18002db6c  push    r14
0x18002db6e  push    r15
0x18002db70  lea     rbp, [rsp-10h]
0x18002db75  sub     rsp, 110h
0x18002db7c  mov     rax, cs:__security_cookie
0x18002db83  xor     rax, rsp
0x18002db86  mov     [rbp+40h+var_40], rax
0x18002db8a  mov     r12, rdx
0x18002db8d  mov     rsi, rcx
0x18002db90  xor     r13d, r13d
0x18002db93  test    rdx, rdx
0x18002db96  jz      short loc_18002DB9C
0x18002db98  mov     [rdx], r13w
0x18002db9c  mov     eax, dword ptr cs:a89; "89"
0x18002dba2  mov     dword ptr [rbp+40h+var_78], eax
0x18002dba5  movzx   eax, word ptr cs:a89+4; ""
0x18002dbac  mov     [rbp+40h+var_74], ax
0x18002dbb0  mov     r8d, 2; unsigned __int64
0x18002dbb6  lea     rdx, [rbp+40h+var_78]; unsigned __int16 *
0x18002dbba  call    ?CheckDigits@@YA_NPEBG0_K@Z; CheckDigits(ushort const *,ushort const *,unsigned __int64)
0x18002dbbf  mov     rcx, [rbp+48h]; this
0x18002dbc3  test    al, al
0x18002dbc5  jz      loc_18002E543
0x18002dbcb  mov     [rsp+140h+var_E8], r13
0x18002dbd0  mov     [rsp+140h+var_E0], r13
0x18002dbd5  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,std::wstring>>>::_Buyheadnode(void)
0x18002dbda  mov     [rsp+140h+var_E8], rax
0x18002dbdf  mov     [rbp+40h+hKey], r13
0x18002dbe3  lea     rax, [rbp+40h+hKey]
0x18002dbe7  mov     [rsp+140h+phkResult], rax; int
0x18002dbec  mov     r9d, 1; samDesired
0x18002dbf2  xor     r8d, r8d; ulOptions
0x18002dbf5  lea     rdx, ?gc_wszRegIccidOverrides@@3QBGB; "Software\\Microsoft\\Multivariant\\Icci"...
0x18002dbfc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002dc03  call    cs:__imp_RegOpenKeyExW
0x18002dc09  cmp     eax, 2
0x18002dc0c  jz      loc_18002DDE9
0x18002dc12  mov     rcx, [rbp+48h]; this
0x18002dc16  test    eax, eax
0x18002dc18  jnz     loc_18002E55B
0x18002dc1e  mov     ebx, r13d
0x18002dc21  mov     edi, r13d
0x18002dc24  lea     r14d, [rax+15h]
0x18002dc28  mov     [rsp+140h+cchValueName], r14d
0x18002dc2d  lea     r15d, [rax+8]
0x18002dc31  mov     [rsp+140h+cbData], r15d
0x18002dc36  lea     rax, [rsp+140h+cbData]
0x18002dc3b  mov     [rsp+140h+lpcbData], rax; lpcbData
0x18002dc40  lea     rax, [rbp+40h+Data]
0x18002dc44  mov     [rsp+140h+lpData], rax; lpData
0x18002dc49  mov     [rsp+140h+lpType], r13; lpType
0x18002dc4e  mov     [rsp+140h+phkResult], r13; int
0x18002dc53  lea     r9, [rsp+140h+cchValueName]; lpcchValueName
0x18002dc58  lea     r8, [rbp+40h+ValueName]; lpValueName
0x18002dc5c  xor     edx, edx; dwIndex
0x18002dc5e  mov     rcx, [rbp+40h+hKey]; hKey
0x18002dc62  call    cs:__imp_RegEnumValueW
0x18002dc68  cmp     eax, 103h
0x18002dc6d  jz      loc_18002DDE9
0x18002dc73  test    eax, eax
0x18002dc75  jnz     loc_18002DD06
0x18002dc7b  cmp     [rsp+140h+cchValueName], ebx
0x18002dc7f  jbe     loc_18002DD06
0x18002dc85  mov     r8d, [rsp+140h+cchValueName]; MaxCount
0x18002dc8a  mov     rdx, rsi; String2
0x18002dc8d  lea     rcx, [rbp+40h+ValueName]; String1
0x18002dc91  call    cs:__imp__wcsnicmp
0x18002dc97  test    eax, eax
0x18002dc99  jnz     short loc_18002DD06
0x18002dc9b  mov     word ptr [rbp+40h+Data+6], r13w
0x18002dca0  mov     eax, 7FFFFFFEh
0x18002dca5  lea     rcx, [rbp+40h+Data]
0x18002dca9  mov     edx, 4
0x18002dcae  lea     r8, [rbp+40h+GeoData]
0x18002dcb2  test    rax, rax
0x18002dcb5  jz      short loc_18002DCD6
0x18002dcb7  movzx   r9d, word ptr [rcx]
0x18002dcbb  test    r9w, r9w
0x18002dcbf  jz      short loc_18002DCD6
0x18002dcc1  add     rcx, 2
0x18002dcc5  mov     [r8], r9w
0x18002dcc9  add     r8, 2
0x18002dccd  dec     rax
0x18002dcd0  sub     rdx, 1
0x18002dcd4  jnz     short loc_18002DCB2
0x18002dcd6  mov     rax, rdx
0x18002dcd9  neg     rax
0x18002dcdc  sbb     r9d, r9d
0x18002dcdf  not     r9d
0x18002dce2  and     r9d, 8007007Ah; char *
0x18002dce9  lea     rcx, [r8-2]
0x18002dced  test    rdx, rdx
0x18002dcf0  cmovnz  rcx, r8
0x18002dcf4  mov     [rcx], r13w
0x18002dcf8  mov     rcx, [rbp+48h]; this
0x18002dcfc  jz      loc_18002E570
0x18002dd02  mov     ebx, [rsp+140h+cchValueName]
0x18002dd06  inc     edi
0x18002dd08  mov     [rsp+140h+cchValueName], r14d
0x18002dd0d  mov     [rsp+140h+cbData], r15d
0x18002dd12  lea     rax, [rsp+140h+cbData]
0x18002dd17  mov     [rsp+140h+lpcbData], rax; lpcbData
0x18002dd1c  lea     rax, [rbp+40h+Data]
0x18002dd20  mov     [rsp+140h+lpData], rax; lpData
0x18002dd25  mov     [rsp+140h+lpType], r13; lpType
0x18002dd2a  mov     [rsp+140h+phkResult], r13; lpReserved
0x18002dd2f  lea     r9, [rsp+140h+cchValueName]; lpcchValueName
0x18002dd34  lea     r8, [rbp+40h+ValueName]; lpValueName
0x18002dd38  mov     edx, edi; dwIndex
0x18002dd3a  mov     rcx, [rbp+40h+hKey]; hKey
0x18002dd3e  call    cs:__imp_RegEnumValueW
0x18002dd44  cmp     eax, 103h
0x18002dd49  jnz     loc_18002DC73
0x18002dd4f  test    ebx, ebx
0x18002dd51  jz      loc_18002DDE9
0x18002dd57  mov     eax, cs:dword_18005A000
0x18002dd5d  cmp     eax, 4
0x18002dd60  jbe     short loc_18002DD89
0x18002dd62  lea     rax, [rbp+40h+GeoData]
0x18002dd66  mov     qword ptr [rbp+40h+Data], rax
0x18002dd6a  lea     rax, [rbp+40h+Data]
0x18002dd6e  mov     [rsp+140h+phkResult], rax
0x18002dd73  xor     r8d, r8d
0x18002dd76  lea     rdx, byte_18004FD35
0x18002dd7d  lea     rcx, dword_18005A000
0x18002dd84  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18002dd89  lea     rcx, [rbp+40h+GeoData]; Src
0x18002dd8d  call    ?MvGeoIdFromIso3166@@YAJPEBG@Z; MvGeoIdFromIso3166(ushort const *)
0x18002dd92  mov     ebx, eax
0x18002dd94  mov     rcx, [rbp+40h+hKey]; hKey
0x18002dd98  test    rcx, rcx
0x18002dd9b  jz      short loc_18002DDA4
0x18002dd9d  call    cs:__imp_RegCloseKey
0x18002dda3  nop
0x18002dda4  mov     rdx, [rsp+140h+var_E8]
0x18002dda9  mov     rdx, [rdx+8]
0x18002ddad  lea     rcx, [rsp+140h+var_E8]
0x18002ddb2  call    ?_Erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Erase(std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *)
0x18002ddb7  mov     rax, [rsp+140h+var_E8]
0x18002ddbc  mov     [rax+8], rax
0x18002ddc0  mov     rax, [rsp+140h+var_E8]
0x18002ddc5  mov     [rax], rax
0x18002ddc8  mov     rax, [rsp+140h+var_E8]
0x18002ddcd  mov     [rax+10h], rax
0x18002ddd1  mov     [rsp+140h+var_E0], r13
0x18002ddd6  mov     rcx, [rsp+140h+var_E8]
0x18002dddb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002dde1  nop
0x18002dde2  mov     eax, ebx
0x18002dde4  jmp     loc_18002E4E0
0x18002dde9  mov     [rsp+140h+cbData], r13d
0x18002ddee  lea     r8, [rsp+140h+cbData]; unsigned int *
0x18002ddf3  xor     edx, edx; pvData
0x18002ddf5  lea     rcx, ?gc_wszIccidToRegionPath@@3QBGB; "IccidToRegionTablePath"
0x18002ddfc  call    ?MvGetConfiguration@@YAJPEBGPEAEPEAK@Z; MvGetConfiguration(ushort const *,uchar *,ulong *)
0x18002de01  mov     rcx, [rbp+48h]; this
0x18002de05  test    eax, eax
0x18002de07  js      loc_18002E582
0x18002de0d  xorps   xmm0, xmm0
0x18002de10  movdqu  xmmword ptr [rbp+40h+ValueName], xmm0
0x18002de15  mov     [rbp+40h+var_60], r13
0x18002de19  mov     edx, [rsp+140h+cbData]
0x18002de1d  shr     rdx, 1
0x18002de20  jz      short loc_18002DE2B
0x18002de22  lea     rcx, [rbp+40h+ValueName]
0x18002de26  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x18002de2b  lea     r8, [rsp+140h+cbData]; unsigned int *
0x18002de30  mov     r15, qword ptr [rbp+40h+ValueName]
0x18002de34  mov     rdx, r15; pvData
0x18002de37  lea     rcx, ?gc_wszIccidToRegionPath@@3QBGB; "IccidToRegionTablePath"
0x18002de3e  call    ?MvGetConfiguration@@YAJPEBGPEAEPEAK@Z; MvGetConfiguration(ushort const *,uchar *,ulong *)
0x18002de43  mov     rcx, [rbp+48h]; this
0x18002de47  test    eax, eax
0x18002de49  js      loc_18002E597
0x18002de4f  mov     eax, cs:dword_18005A000
0x18002de55  cmp     eax, 4
0x18002de58  jbe     short loc_18002DE7D
0x18002de5a  mov     qword ptr [rbp+40h+GeoData], r15
0x18002de5e  lea     rax, [rbp+40h+GeoData]
0x18002de62  mov     [rsp+140h+phkResult], rax; int
0x18002de67  xor     r8d, r8d
0x18002de6a  lea     rdx, byte_18004FC13
0x18002de71  lea     rcx, dword_18005A000
0x18002de78  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18002de7d  mov     [rbp+40h+ppstm], r13
0x18002de81  lea     r8, [rbp+40h+ppstm]; ppstm
0x18002de85  xor     edx, edx; grfMode
0x18002de87  mov     rcx, r15; pszFile
0x18002de8a  call    cs:__imp_SHCreateStreamOnFileW
0x18002de90  mov     rcx, [rbp+48h]; this
0x18002de94  test    eax, eax
0x18002de96  js      loc_18002E5AC
0x18002de9c  mov     [rsp+140h+ppvObject], r13
0x18002dea1  xor     r8d, r8d; pMalloc
0x18002dea4  lea     rdx, [rsp+140h+ppvObject]; ppvObject
0x18002dea9  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x18002deb0  call    cs:__imp_CreateXmlReader
0x18002deb6  mov     rcx, [rbp+48h]; this
0x18002deba  test    eax, eax
0x18002debc  js      loc_18002E5C1
0x18002dec2  mov     rcx, [rsp+140h+ppvObject]
0x18002dec7  mov     rax, [rcx]
0x18002deca  xor     r8d, r8d
0x18002decd  lea     edx, [r8+4]
0x18002ded1  mov     rax, [rax+28h]
0x18002ded5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002deda  mov     rcx, [rbp+48h]; this
0x18002dede  test    eax, eax
0x18002dee0  js      loc_18002E5D6
0x18002dee6  mov     rcx, [rsp+140h+ppvObject]
0x18002deeb  mov     rax, [rcx]
0x18002deee  mov     rdx, [rbp+40h+ppstm]
0x18002def2  mov     rax, [rax+18h]
0x18002def6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002defb  mov     rcx, [rbp+48h]; this
0x18002deff  test    eax, eax
0x18002df01  js      loc_18002E5EB
0x18002df07  lea     rax, [rsp+140h+var_C8]
0x18002df0c  mov     qword ptr [rbp+40h+GeoData], rax
0x18002df10  xorps   xmm0, xmm0
0x18002df13  movdqu  [rsp+140h+var_C8], xmm0
0x18002df19  mov     [rbp+40h+var_B8], r13
0x18002df1d  mov     [rbp+40h+var_B0], r13
0x18002df21  mov     [rbp+40h+var_A8], r13
0x18002df25  mov     ecx, 10h; Size
0x18002df2a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002df2f  test    rax, rax
0x18002df32  jnz     short loc_18002DF3B
0x18002df34  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18002df3a  int     3; Trap to Debugger
0x18002df3b  mov     qword ptr [rsp+140h+var_C8], rax
0x18002df40  mov     [rax], r13
0x18002df43  mov     [rax+8], r13
0x18002df47  lea     rcx, [rsp+140h+var_C8]
0x18002df4c  mov     rax, qword ptr [rsp+140h+var_C8]
0x18002df51  mov     [rax], rcx
0x18002df54  mov     rdx, [rbp+40h+var_A8]
0x18002df58  lea     rax, [rdx+1]
0x18002df5c  mov     rcx, [rbp+40h+var_B8]
0x18002df60  cmp     rcx, rax
0x18002df63  ja      short loc_18002DF77
0x18002df65  lea     rcx, [rsp+140h+var_C8]
0x18002df6a  call    ?_Growmap@?$deque@UIccidSegment@@V?$allocator@UIccidSegment@@@std@@@std@@IEAAX_K@Z; std::deque<IccidSegment>::_Growmap(unsigned __int64)
0x18002df6f  mov     rdx, [rbp+40h+var_A8]
0x18002df73  mov     rcx, [rbp+40h+var_B8]
0x18002df77  dec     rcx
0x18002df7a  mov     rax, [rbp+40h+var_B0]
0x18002df7e  and     rax, rcx
0x18002df81  mov     [rbp+40h+var_B0], rax
0x18002df85  lea     rbx, [rax+rdx]
0x18002df89  and     rbx, rcx
0x18002df8c  mov     rax, qword ptr [rbp+40h+var_C8+8]
0x18002df90  cmp     [rax+rbx*8], r13
0x18002df94  jnz     short loc_18002DFBB
0x18002df96  mov     ecx, 18h; Size
0x18002df9b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002dfa0  mov     rcx, rax
0x18002dfa3  test    rax, rax
0x18002dfa6  jnz     short loc_18002DFAF
0x18002dfa8  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18002dfae  int     3; Trap to Debugger
0x18002dfaf  mov     rax, qword ptr [rbp+40h+var_C8+8]
0x18002dfb3  mov     [rax+rbx*8], rcx
0x18002dfb7  mov     rax, qword ptr [rbp+40h+var_C8+8]
0x18002dfbb  mov     rax, [rax+rbx*8]
0x18002dfbf  mov     [rax], rsi
0x18002dfc2  mov     qword ptr [rax+8], 2
0x18002dfca  mov     ecx, 7FFFFFFEh
0x18002dfcf  lea     r9, aZz; "ZZ"
0x18002dfd6  mov     edx, 4
0x18002dfdb  lea     r8, [rax+10h]
0x18002dfdf  test    rcx, rcx
0x18002dfe2  jz      short loc_18002E002
0x18002dfe4  movzx   eax, word ptr [r9]
0x18002dfe8  test    ax, ax
0x18002dfeb  jz      short loc_18002E002
0x18002dfed  add     r9, 2
0x18002dff1  mov     [r8], ax
0x18002dff5  add     r8, 2
0x18002dff9  dec     rcx
0x18002dffc  sub     rdx, 1
0x18002e000  jnz     short loc_18002DFDF
0x18002e002  mov     rax, rdx
0x18002e005  neg     rax
0x18002e008  sbb     r9d, r9d
0x18002e00b  not     r9d
0x18002e00e  and     r9d, 8007007Ah; char *
0x18002e015  lea     rcx, [r8-2]
0x18002e019  test    rdx, rdx
0x18002e01c  cmovnz  rcx, r8
0x18002e020  mov     [rcx], r13w
0x18002e024  mov     rcx, [rbp+48h]; this
0x18002e028  jz      loc_18002E600
0x18002e02e  inc     [rbp+40h+var_A8]
  ... truncated ...
```
