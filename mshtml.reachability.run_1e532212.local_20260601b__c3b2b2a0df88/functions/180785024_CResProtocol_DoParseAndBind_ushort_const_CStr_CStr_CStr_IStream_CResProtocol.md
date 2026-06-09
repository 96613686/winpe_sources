# CResProtocol::DoParseAndBind(ushort const *,CStr &,CStr &,CStr &,IStream * *,CResProtocol *)

- ea: `0x180785024`
- end: `0x180785b9c`
- name: `?DoParseAndBind@CResProtocol@@SAJPEBGAEAVCStr@@11PEAPEAUIStream@@PEAV1@@Z`
- size: `2936`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct CStr *, struct CStr *, struct CStr *, struct IStream **, struct CResProtocol *)`
- caller_count: `2`
- callee_count: `23`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x1807824f0`
- `0x180f73020`

## callees

- `0x18005e684`
- `0x18006b354`
- `0x1800ea428`
- `0x1803b024c`
- `0x1803e41f0`
- `0x180402d68`
- `0x18053d234`
- `0x1805a7f20`
- `0x18066ddc4`
- `0x1806a55e4`
- `0x1806cb0b4`
- `0x1806cdaac`
- `0x18077b900`
- `0x180785024`
- `0x1807967d0`
- `0x18083c0b4`
- `0x18083c124`
- `0x180b5c9c4`
- `0x180f73170`
- `0x180f731e0`
- `0x1810f6516`
- `0x1810f65c0`
- `0x181104010`

## import_xrefs

- `msvcrt!_itow_s` at `0x1807851c2`
- `msvcrt!_itow_s` at `0x1807851c2`
- `msvcrt!memcpy_s` at `0x180785503`
- `msvcrt!memcpy_s` at `0x180785520`
- `msvcrt!memcpy_s` at `0x18078580c`
- `msvcrt!memcpy_s` at `0x180785503`
- `msvcrt!memcpy_s` at `0x180785520`
- `msvcrt!memcpy_s` at `0x18078580c`
- `KERNEL32!LoadLibraryExW` at `0x180785267`
- `KERNEL32!LoadLibraryExW` at `0x180785267`
- `KERNEL32!WriteFile` at `0x18078597d`
- `KERNEL32!WriteFile` at `0x18078597d`
- `KERNEL32!CreateFileW` at `0x180785953`
- `KERNEL32!CreateFileW` at `0x180785953`
- `KERNEL32!DeleteFileW` at `0x1807859fe`
- `KERNEL32!DeleteFileW` at `0x1807859fe`
- `KERNEL32!CompareStringW` at `0x18078573b`
- `KERNEL32!CompareStringW` at `0x18078573b`
- `KERNEL32!FreeLibrary` at `0x180785ad3`
- `KERNEL32!FreeLibrary` at `0x180785ad3`
- `KERNEL32!CloseHandle` at `0x1807859e5`
- `KERNEL32!CloseHandle` at `0x180785b01`
- `KERNEL32!CloseHandle` at `0x1807859e5`
- `KERNEL32!CloseHandle` at `0x180785b01`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x18078529c`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x18078530d`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x18078529c`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x18078530d`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x1807852ba`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x1807852d4`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x18078532b`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180785345`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x18078535f`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x1807852ba`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x1807852d4`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x18078532b`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180785345`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x18078535f`
- `iertutil!CreateUri` at `0x18078513d`
- `iertutil!CreateUri` at `0x1807855d5`
- `iertutil!CreateUri` at `0x18078513d`
- `iertutil!CreateUri` at `0x1807855d5`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x18078598d`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x18078598d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180785b2b`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180785b2b`
- `urlmon!CoInternetCreateSecurityManager` at `0x18078516c`
- `urlmon!CoInternetCreateSecurityManager` at `0x18078516c`
- `urlmon!CreateAsyncBindCtxEx` at `0x18078555d`
- `urlmon!CreateAsyncBindCtxEx` at `0x18078555d`
- `urlmon!FindMimeFromData` at `0x180785785`
- `urlmon!FindMimeFromData` at `0x180785847`
- `urlmon!FindMimeFromData` at `0x180785785`
- `urlmon!FindMimeFromData` at `0x180785847`
- `urlmon!__imp_IECompatLogEventWithUrl` at `0x180785203`
- `urlmon!__imp_IECompatLogEventWithUrl` at `0x180785203`

## string_xrefs

- `0x1807851f0`: `ResProtocolRestricted`
- `0x1807852b0`: `shdoclc.dll`
- `0x180785321`: `apds.dll`

## pseudocode

```c
__int64 __fastcall CResProtocol::DoParseAndBind(
        const unsigned __int16 *a1,
        struct CStr *a2,
        struct CStr *a3,
        struct CStr *a4,
        struct IStream **a5,
        struct CResProtocol *a6)
{
  rsize_t v6; // r15
  struct IStream *v8; // rdi
  _QWORD *ThreadLocalStoragePointer; // rax
  __int64 v13; // rax
  HRESULT Uri; // ebx
  const WCHAR *v15; // rcx
  int v16; // ecx
  HMODULE v17; // r12
  const WCHAR *FileNameW; // rax
  const WCHAR *v19; // rbx
  const WCHAR *v20; // rax
  const WCHAR *v21; // rbx
  unsigned int v22; // eax
  HINSTANCE v23; // rcx
  __int64 v24; // r8
  _DWORD *Resource; // rsi
  __int64 v26; // rax
  unsigned int v27; // eax
  unsigned int v28; // r14d
  int v29; // r8d
  unsigned __int16 v30; // cx
  int v31; // edx
  unsigned int v32; // eax
  int v33; // edx
  void *v34; // rax
  _DWORD *v35; // rbx
  const WCHAR *v36; // rcx
  CResProtocol *v37; // r13
  IUri *v38; // r14
  int v39; // ebx
  LPWSTR v40; // r12
  const WCHAR *v41; // r8
  const WCHAR *i; // r9
  WCHAR v43; // cx
  unsigned __int16 v44; // r10
  WCHAR v45; // dx
  int v46; // eax
  HRESULT MimeFromData; // ebx
  char v48; // r14
  int v49; // eax
  DWORD v50; // ebx
  void *v51; // rax
  void *v52; // r14
  void *v53; // r8
  CResProtocol *v54; // rbx
  __int64 v55; // rcx
  HANDLE v56; // rax
  bool v57; // al
  __int64 v58; // rax
  __int64 v59; // rcx
  void *v60; // r8
  int Value[2]; // [rsp+58h] [rbp-B0h] BYREF
  IInternetSecurityManager *ppSM; // [rsp+60h] [rbp-A8h] BYREF
  CResProtocol *v64; // [rsp+68h] [rbp-A0h]
  HANDLE hObject; // [rsp+70h] [rbp-98h]
  IUri *ppURI; // [rsp+78h] [rbp-90h] BYREF
  LPBC pBC; // [rsp+80h] [rbp-88h] BYREF
  LPWSTR ppwzMimeOut; // [rsp+88h] [rbp-80h] BYREF
  HMODULE hLibModule; // [rsp+90h] [rbp-78h]
  void *v70; // [rsp+98h] [rbp-70h]
  _QWORD v71[2]; // [rsp+A0h] [rbp-68h] BYREF
  int v72; // [rsp+B0h] [rbp-58h]
  LPCWSTR pwzUrl[2]; // [rsp+B8h] [rbp-50h]
  int v74; // [rsp+C8h] [rbp-40h]
  struct IStream **v75; // [rsp+D0h] [rbp-38h]
  _QWORD Source[2]; // [rsp+D8h] [rbp-30h] BYREF
  wchar_t Buffer[4]; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v78; // [rsp+F0h] [rbp-18h]
  int v79; // [rsp+F8h] [rbp-10h]
  __int128 v80; // [rsp+100h] [rbp-8h]
  int v81; // [rsp+110h] [rbp+8h]
  WCHAR FileName; // [rsp+118h] [rbp+10h] BYREF
  _BYTE v83[526]; // [rsp+11Ah] [rbp+12h] BYREF

  LODWORD(v6) = 0;
  v8 = 0;
  v75 = a5;
  v64 = a6;
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  Value[1] = 0;
  hLibModule = 0;
  v13 = ThreadLocalStoragePointer[(unsigned int)tls_index];
  v70 = 0;
  pBC = 0;
  ppwzMimeOut = 0;
  LODWORD(v13) = *(_DWORD *)(v13 + 12);
  hObject = (HANDLE)-1LL;
  if ( dword_1815CA408 > (int)v13 )
  {
    Init_thread_header(&dword_1815CA408);
    if ( dword_1815CA408 == -1 )
    {
      byte_1815CA40C = (unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_RESTRICT_RES_TO_LMZ) == 0;
      Init_thread_footer(&dword_1815CA408);
    }
  }
  Uri = CrackResUrl(a1, a2, a3, a4);
  if ( Uri )
    goto LABEL_120;
  if ( CStr::Length(a2) >= 0x104 )
  {
    Uri = -2147467259;
    goto LABEL_120;
  }
  if ( byte_1815CA40C )
  {
    v15 = *(const WCHAR **)a2;
    Value[0] = 0;
    ppURI = 0;
    Uri = CreateUri(v15, dwFlags, 0, &ppURI);
    if ( Uri < 0 )
    {
      if ( Uri == -2147024809 )
        Uri = 0;
LABEL_19:
      if ( ppURI )
      {
        ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
        ppURI = 0;
      }
      if ( Uri < 0 )
        goto LABEL_120;
      goto LABEL_22;
    }
    ppSM = 0;
    Value[0] = 4;
    if ( CoInternetCreateSecurityManager(0, &ppSM, 0) < 0
      || (Uri = ((__int64 (__fastcall *)(IInternetSecurityManager *, _QWORD, int *, __int64))ppSM->lpVtbl->MapUrlToZone)(
                  ppSM,
                  *(_QWORD *)a2,
                  Value,
                  2),
          Uri < 0) )
    {
      v16 = Value[0];
    }
    else
    {
      v16 = Value[0];
      if ( !Value[0] )
      {
LABEL_15:
        if ( ppSM )
        {
          ((void (__fastcall *)(IInternetSecurityManager *))ppSM->lpVtbl->Release)(ppSM);
          ppSM = 0;
        }
        goto LABEL_19;
      }
    }
    Uri = -2147024891;
    _itow_s(v16, Buffer, 0x10u, 10);
    if ( g_cmptlgs != 1 && (unsigned int)IECompatLoggingEnabled() )
      IECompatLogEventWithUrl(3221226517LL, L"ResProtocolRestricted", a1, Buffer, 0, 0, 0);
    goto LABEL_15;
  }
LABEL_22:
  hLibModule = LoadLibraryExW(*(LPCWSTR *)a2, 0, 0x60u);
  v17 = hLibModule;
  if ( !hLibModule )
  {
    Uri = -2147023739;
    goto LABEL_120;
  }
  if ( (unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_LOAD_SHDOCLC_RESOURCES)
    && (FileNameW = PathFindFileNameW(*(LPCWSTR *)a2), (v19 = FileNameW) != 0)
    && (!StrCmpICW(FileNameW, L"shdoclc.dll") || !StrCmpICW(v19, L"shdoclc"))
    && (unsigned int)CResProtocol::_IsInsecureHTML(a4)
    || (unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_ALLOW_APDS_REDIRECTION)
    && (v20 = PathFindFileNameW(*(LPCWSTR *)a2), (v21 = v20) != 0)
    && (!StrCmpICW(v20, L"apds.dll") || !StrCmpICW(v21, L"apds"))
    && !StrCmpICW(*(LPCWSTR *)a4, L"redirect.html") )
  {
    Uri = -2147024891;
    goto LABEL_120;
  }
  v22 = CStr::Length(a3);
  v23 = v17;
  if ( v22 )
  {
    v24 = *(_QWORD *)a3;
  }
  else
  {
    Resource = GetResource(
                 v17,
                 *(const unsigned __int16 **)a4,
                 (const unsigned __int16 *)0x17,
                 (unsigned int *)&Value[1]);
    if ( Resource )
      goto LABEL_41;
    v23 = v17;
    v24 = 2110;
  }
  Resource = GetResource(v23, *(const unsigned __int16 **)a4, (const unsigned __int16 *)v24, (unsigned int *)&Value[1]);
  if ( !Resource )
  {
    LODWORD(v6) = Value[1];
    Uri = -2147023739;
    goto LABEL_120;
  }
LABEL_41:
  v26 = *(_QWORD *)a3;
  if ( **(_WORD **)a3 == 35 && *(_WORD *)(v26 + 2) == 50 && !*(_WORD *)(v26 + 4) )
  {
    v6 = (unsigned int)Value[1];
    v27 = 0;
    Value[0] = 0;
    memset(Source, 0, 14);
    if ( Value[1] >= 0x28u && *Resource == 40 )
    {
      v27 = Resource[8];
      v28 = 54;
      v29 = Resource[4];
      v30 = *((_WORD *)Resource + 7);
LABEL_50:
      if ( v30 > 8u )
      {
        v31 = 0;
        if ( v29 == 3 && ((v30 - 16) & 0xFFEF) == 0 )
          v31 = 12;
      }
      else
      {
        if ( !v27 )
          v27 = 1 << v30;
        Uri = ULongLongToULong(4LL * v27, (unsigned int *)Value);
        if ( Uri )
          goto LABEL_120;
        v31 = Value[0];
      }
      LOWORD(Source[0]) = 19778;
      if ( (unsigned int)v6 >= 0xFFFFFFF2 )
      {
        Uri = -2147024362;
        goto LABEL_120;
      }
      v32 = v28 + v31;
      *(_DWORD *)((char *)Source + 2) = v6 + 14;
      v33 = -1;
      *(_DWORD *)((char *)Source + 6) = 0;
      if ( v32 >= v28 )
        v33 = v32;
      Uri = v32 < v28 ? 0x80070216 : 0;
      if ( v32 >= v28 )
      {
        *(_DWORD *)((char *)&Source[1] + 2) = v33;
        v34 = (void *)MemoryProtection::HeapAlloc<1>(g_hProcessHeap, (unsigned int)(v6 + 14));
        v70 = v34;
        v35 = v34;
        if ( !v34 )
          goto LABEL_119;
        memcpy_s(v34, *(unsigned int *)((char *)Source + 2), Source, 0xEu);
        memcpy_s((char *)v35 + 14, *(unsigned int *)((char *)Source + 2) - 14LL, Resource, v6);
        LODWORD(v6) = *(_DWORD *)((char *)Source + 2);
        Resource = v35;
        goto LABEL_66;
      }
LABEL_120:
      v37 = v64;
      if ( v64 )
        goto LABEL_121;
      goto LABEL_126;
    }
    if ( Value[1] >= 0xCu && *Resource == 12 )
    {
      v30 = *((_WORD *)Resource + 5);
      v29 = 0;
      v28 = 26;
      goto LABEL_50;
    }
  }
  else
  {
    LODWORD(v6) = Value[1];
  }
LABEL_66:
  Uri = CreateAsyncBindCtxEx(0, 0, 0, 0, &pBC, 0);
  if ( Uri )
    goto LABEL_120;
  if ( !v64 )
    goto LABEL_115;
  v36 = (const WCHAR *)*((_QWORD *)v64 + 9);
  v71[0] = &CUString::`vftable';
  v72 = 11;
  *(_QWORD *)Buffer = &CUString::`vftable';
  *(_OWORD *)pwzUrl = 0;
  v79 = 11;
  v80 = 0;
  ppSM = 0;
  Value[0] = 0;
  v71[1] = 0;
  v74 = 0;
  v78 = 0;
  v81 = 0;
  Uri = CreateUri(v36, dwFlags, 0, (IUri **)&ppSM);
  if ( Uri < 0 )
  {
    *(_QWORD *)Buffer = &CUString::`vftable';
    CUString::Set((CUString *)Buffer, 0, Uri_PROPERTY_RAW_URI);
    v71[0] = &CUString::`vftable';
    CUString::Set((CUString *)v71, 0, Uri_PROPERTY_RAW_URI);
    v37 = v64;
    goto LABEL_121;
  }
  ((void (__fastcall *)(IInternetSecurityManager *, int *))ppSM->lpVtbl[2].GetSecuritySite)(ppSM, Value);
  CUString::Set((CUString *)v71, (struct IUri *)ppSM, Uri_PROPERTY_PATH);
  v38 = (IUri *)pwzUrl[1];
  v37 = v64;
  ppURI = (IUri *)pwzUrl[1];
  if ( !pwzUrl[1] )
  {
    v38 = (IUri *)*((_QWORD *)v64 + 9);
    ppURI = v38;
  }
  v39 = 0;
  v40 = (LPWSTR)L"text/html";
  if ( !(unsigned int)IsIEResourcePage((struct IUri *)ppSM, 1, 0)
    || (v39 = CUString::Set((CUString *)Buffer, (struct IUri *)ppSM, Uri_PROPERTY_EXTENSION)) != 0
    || (v41 = (const WCHAR *)*((_QWORD *)&v80 + 1)) == 0 )
  {
LABEL_91:
    if ( (Value[0] & 0x10) != 0 && !v39 )
    {
      MimeFromData = FindMimeFromData(pBC, (LPCWSTR)v38, 0, 0, 0, 0, &ppwzMimeOut, 0);
      v48 = 0;
      if ( MimeFromData >= 0 )
        goto LABEL_100;
    }
    v50 = 256;
    if ( (unsigned int)v6 < 0x100 )
      v50 = v6;
    v51 = (void *)MemoryProtection::HeapAlloc<1>(g_hProcessHeap, v50);
    v52 = v51;
    if ( v51 )
    {
      memcpy_s(v51, v50, Resource, v50);
      v40 = (LPWSTR)L"text/html";
      MimeFromData = FindMimeFromData(pBC, (LPCWSTR)ppURI, v52, v50, L"text/html", 0, &ppwzMimeOut, 0);
      MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v52, v53);
      v48 = 0;
      goto LABEL_100;
    }
    Uri = -2147024882;
    goto LABEL_98;
  }
  for ( i = L".dlg"; ; ++i )
  {
    v45 = *v41;
    if ( !*v41 )
    {
      v46 = -(*i != 0);
      goto LABEL_86;
    }
    v43 = *i;
    if ( v45 != *i )
      break;
LABEL_83:
    ++v41;
  }
  v44 = v43 - 65;
  if ( (unsigned __int16)(v45 - 65) > 0x19u )
  {
    if ( v44 > 0x19u )
      goto LABEL_88;
  }
  else
  {
    v45 += 32;
    if ( v44 > 0x19u )
      goto LABEL_82;
  }
  v43 += 32;
LABEL_82:
  if ( v45 == v43 )
    goto LABEL_83;
LABEL_88:
  if ( ((v45 | v43) & 0xFF80) == 0 )
    goto LABEL_91;
  v49 = CompareStringW(0, 0x31001u, v41, -1, i, -1);
  if ( v49 <= 0 )
    goto LABEL_91;
  v46 = v49 - 2;
LABEL_86:
  if ( v46 )
    goto LABEL_91;
  MimeFromData = 0;
  v48 = 1;
LABEL_100:
  if ( ppSM )
  {
    ((void (__fastcall *)(IInternetSecurityManager *))ppSM->lpVtbl->Release)(ppSM);
    ppSM = 0;
  }
  if ( MimeFromData < 0 )
    goto LABEL_106;
  if ( !v48 )
    v40 = ppwzMimeOut;
  Uri = (*(__int64 (__fastcall **)(_QWORD, __int64, LPWSTR))(**((_QWORD **)v37 + 10) + 32LL))(
          *((_QWORD *)v37 + 10),
          22,
          v40);
  if ( !Uri )
  {
LABEL_106:
    *(_QWORD *)Buffer = &CUString::`vftable';
    CUString::Set((CUString *)Buffer, 0, Uri_PROPERTY_RAW_URI);
    v71[0] = &CUString::`vftable';
    CUString::Set((CUString *)v71, 0, Uri_PROPERTY_RAW_URI);
    v54 = v64;
    if ( (*((_BYTE *)v64 + 100) & 0x40) == 0 )
      goto LABEL_115;
    FileName = 0;
    memset_0(v83, 0, 0x208u);
    v55 = *((_QWORD *)v54 + 9);
    Value[1] = 0;
    if ( !(unsigned int)CreateUrlCacheEntryBugW(v55, (unsigned int)v6, 0, &FileName) )
      goto LABEL_112;
    v56 = CreateFileW(&FileName, 0x40000000u, 3u, 0, 2u, 0x80u, 0);
    hObject = v56;
    if ( v56 != (HANDLE)-1LL )
    {
      if ( WriteFile(v56, Resource, v6, (LPDWORD)&Value[1], 0) )
      {
        v57 = LCIEIsCurrentProcessInPrivate();
        if ( (unsigned int)CommitUrlCacheEntryBugW(
                             *((_QWORD *)v54 + 9),
                             (int)&FileName,
                             0,
                             0,
                             ((unsigned __int8)v57 << 17) + 1) )
        {
          (*(void (__fastcall **)(_QWORD, __int64, WCHAR *))(**((_QWORD **)v54 + 10) + 32LL))(
            *((_QWORD *)v54 + 10),
            14,
            &FileName);
          goto LABEL_115;
        }
      }
LABEL_112:
      v56 = hObject;
    }
    if ( FileName )
    {
      CloseHandle(v56);
      hObject = (HANDLE)-1LL;
      DeleteFileW(&FileName);
      DeleteUrlCacheEntryBugW(*((const unsigned __int16 **)v54 + 9));
    }
LABEL_115:
    v58 = MemoryProtection::HeapAlloc<1>(g_hProcessHeap, 40);
    v8 = (struct IStream *)v58;
    if ( v58 )
    {
      *(_QWORD *)(v58 + 32) = 0;
      *(_QWORD *)v58 = &CBaseROStmOnBuffer::`vftable';
      *(_DWORD *)(v58 + 8) = 1;
      *(_QWORD *)v58 = &CBaseROStmOnBuffer::`vftable';
      *(_QWORD *)(v58 + 16) = 0;
      *(_DWORD *)(v58 + 24) = 0;
      Uri = CBaseROStmOnBuffer::Init((CBaseROStmOnBuffer *)v58, (const unsigned __int8 *)Resource, v6);
      if ( !Uri )
      {
        *v75 = v8;
        (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v8 + 8LL))(v8);
      }
      goto LABEL_120;
    }
    v8 = 0;
LABEL_119:
    Uri = -2147024882;
    goto LABEL_120;
  }
LABEL_98:
  *(_QWORD *)Buffer = &CUString::`vftable';
  CUString::Set((CUString *)Buffer, 0, Uri_PROPERTY_RAW_URI);
  v71[0] = &CUString::`vftable';
  CUString::Set((CUString *)v71, 0, Uri_PROPERTY_RAW_URI);
LABEL_121:
  if ( (*((_BYTE *)v37 + 248) & 1) == 0 )
  {
    if ( !Uri )
      CResProtocol::_ReportData(v37, v6);
    v59 = *((_QWORD *)v37 + 10);
    if ( v59 )
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v59 + 48LL))(v59, (unsigned int)Uri, 0, 0);
  }
LABEL_126:
  if ( hLibModule )
    FreeLibrary(hLibModule);
  if ( v8 )
    (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v8 + 16LL))(v8);
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  ReleaseInterface((struct IUnknown *)pBC);
  MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v70, v60);
  CoTaskMemFree(ppwzMimeOut);
  return (unsigned int)Uri;
}

```

## disassembly

```asm
0x180785024  mov     rax, rsp
0x180785027  mov     [rax+20h], r9
0x18078502b  mov     [rax+18h], r8
0x18078502f  mov     [rax+10h], rdx
0x180785033  mov     [rax+8], rcx
0x180785037  push    rbp
0x180785038  push    rbx
0x180785039  push    rsi
0x18078503a  push    rdi
0x18078503b  push    r12
0x18078503d  push    r13
0x18078503f  push    r14
0x180785041  push    r15
0x180785043  lea     rbp, [rax-278h]
0x18078504a  sub     rsp, 338h
0x180785051  mov     rax, cs:__security_cookie
0x180785058  xor     rax, rsp
0x18078505b  mov     [rbp+270h+var_50], rax
0x180785062  mov     rax, [rbp+270h+arg_20]
0x180785069  xor     ebx, ebx
0x18078506b  mov     ecx, cs:_tls_index
0x180785071  mov     r15d, ebx
0x180785074  mov     r14, [rbp+270h+arg_18]
0x18078507b  mov     edi, ebx
0x18078507d  mov     r12, [rbp+270h+arg_0]
0x180785084  mov     rsi, [rbp+270h+arg_8]
0x18078508b  mov     r13, [rbp+270h+arg_10]
0x180785092  mov     [rbp+270h+var_2A8], rax
0x180785096  mov     rax, [rbp+270h+arg_28]
0x18078509d  mov     [rsp+370h+var_310], rax
0x1807850a2  mov     rax, gs:58h
0x1807850ab  mov     edx, 0Ch
0x1807850b0  mov     [rsp+370h+Value+4], ebx
0x1807850b4  mov     [rbp+270h+hLibModule], rbx
0x1807850b8  mov     rax, [rax+rcx*8]
0x1807850bc  mov     [rbp+270h+var_2E0], rbx
0x1807850c0  mov     [rsp+370h+pBC], rbx
0x1807850c5  mov     [rbp+270h+var_2F0], rbx
0x1807850c9  mov     eax, [rax+rdx]
0x1807850cc  cmp     cs:dword_1815CA408, eax
0x1807850d2  mov     [rsp+370h+hObject], 0FFFFFFFFFFFFFFFFh
0x1807850db  jg      loc_180785B5D
0x1807850e1  mov     r9, r14; struct CStr *
0x1807850e4  mov     r8, r13; struct CStr *
0x1807850e7  mov     rdx, rsi; struct CStr *
0x1807850ea  mov     rcx, r12; unsigned __int16 *
0x1807850ed  call    ?CrackResUrl@@YAJPEBGPEAVCStr@@11@Z; CrackResUrl(ushort const *,CStr *,CStr *,CStr *)
0x1807850f2  mov     ebx, eax
0x1807850f4  test    eax, eax
0x1807850f6  jnz     loc_180785A87
0x1807850fc  mov     rcx, rsi; this
0x1807850ff  call    ?Length@CStr@@QEBAIXZ; CStr::Length(void)
0x180785104  cmp     eax, 104h
0x180785109  jb      short loc_180785115
0x18078510b  mov     ebx, 80004005h
0x180785110  jmp     loc_180785A87
0x180785115  xor     eax, eax
0x180785117  cmp     cs:byte_1815CA40C, al
0x18078511d  jz      loc_18078525E
0x180785123  mov     edx, cs:dwFlags; dwFlags
0x180785129  lea     r9, [rsp+370h+ppURI]; ppURI
0x18078512e  mov     rcx, [rsi]; pwzURI
0x180785131  xor     r8d, r8d; dwReserved
0x180785134  mov     [rsp+370h+Value], eax
0x180785138  mov     [rsp+370h+ppURI], rax
0x18078513d  call    cs:__imp_CreateUri
0x180785144  nop     dword ptr [rax+rax+00h]
0x180785149  mov     ebx, eax
0x18078514b  xor     eax, eax
0x18078514d  test    ebx, ebx
0x18078514f  js      loc_18078522F
0x180785155  xor     r8d, r8d; dwReserved
0x180785158  mov     [rsp+370h+ppSM], rax
0x18078515d  lea     rdx, [rsp+370h+ppSM]; ppSM
0x180785162  mov     [rsp+370h+Value], 4
0x18078516a  xor     ecx, ecx; pSP
0x18078516c  call    cs:__imp_CoInternetCreateSecurityManager
0x180785173  nop     dword ptr [rax+rax+00h]
0x180785178  test    eax, eax
0x18078517a  js      short loc_1807851AB
0x18078517c  mov     rcx, [rsp+370h+ppSM]
0x180785181  lea     r8, [rsp+370h+Value]
0x180785186  mov     rdx, [rsi]
0x180785189  mov     r9d, 2
0x18078518f  mov     rax, [rcx]
0x180785192  mov     rax, [rax+28h]
0x180785196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18078519b  mov     ebx, eax
0x18078519d  test    eax, eax
0x18078519f  js      short loc_1807851AB
0x1807851a1  mov     ecx, [rsp+370h+Value]
0x1807851a5  test    ecx, ecx
0x1807851a7  jz      short loc_18078520F
0x1807851a9  jmp     short loc_1807851AF
0x1807851ab  mov     ecx, [rsp+370h+Value]; Value
0x1807851af  mov     r9d, 0Ah; Radix
0x1807851b5  lea     rdx, [rbp+270h+Buffer]; Buffer
0x1807851b9  mov     ebx, 80070005h
0x1807851be  lea     r8d, [r9+6]; BufferCount
0x1807851c2  call    cs:__imp__itow_s
0x1807851c9  nop     dword ptr [rax+rax+00h]
0x1807851ce  cmp     cs:?g_cmptlgs@@3W4CMPTLGS@@A, 1; CMPTLGS g_cmptlgs
0x1807851d5  jz      short loc_18078520F
0x1807851d7  call    ?IECompatLoggingEnabled@@YAHXZ; IECompatLoggingEnabled(void)
0x1807851dc  xor     ecx, ecx
0x1807851de  test    eax, eax
0x1807851e0  jz      short loc_18078520F
0x1807851e2  mov     [rsp+370h+ppwzMimeOut], rcx
0x1807851e7  lea     r9, [rbp+270h+Buffer]
0x1807851eb  mov     qword ptr [rsp+370h+reserved], rcx
0x1807851f0  lea     rdx, aResprotocolres; "ResProtocolRestricted"
0x1807851f7  mov     dword ptr [rsp+370h+ppBC], ecx
0x1807851fb  mov     r8, r12
0x1807851fe  mov     ecx, 0C0000415h
0x180785203  call    cs:__imp_IECompatLogEventWithUrl
0x18078520a  nop     dword ptr [rax+rax+00h]
0x18078520f  mov     rcx, [rsp+370h+ppSM]
0x180785214  xor     r12d, r12d
0x180785217  test    rcx, rcx
0x18078521a  jz      short loc_18078523B
0x18078521c  mov     rax, [rcx]
0x18078521f  mov     rax, [rax+10h]
0x180785223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180785228  mov     [rsp+370h+ppSM], r12
0x18078522d  jmp     short loc_18078523B
0x18078522f  cmp     ebx, 80070057h
0x180785235  cmovz   ebx, eax
0x180785238  xor     r12d, r12d
0x18078523b  mov     rcx, [rsp+370h+ppURI]
0x180785240  test    rcx, rcx
0x180785243  jz      short loc_180785256
0x180785245  mov     rax, [rcx]
0x180785248  mov     rax, [rax+10h]
0x18078524c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180785251  mov     [rsp+370h+ppURI], r12
0x180785256  test    ebx, ebx
0x180785258  js      loc_180785A87
0x18078525e  mov     rcx, [rsi]; lpLibFileName
0x180785261  xor     edx, edx; hFile
0x180785263  lea     r8d, [rdx+60h]; dwFlags
0x180785267  call    cs:__imp_LoadLibraryExW
0x18078526e  nop     dword ptr [rax+rax+00h]
0x180785273  mov     [rbp+270h+hLibModule], rax
0x180785277  mov     r12, rax
0x18078527a  test    rax, rax
0x18078527d  jnz     short loc_180785289
0x18078527f  mov     ebx, 80070485h
0x180785284  jmp     loc_180785A87
0x180785289  lea     rcx, ?FEATURE_LOAD_SHDOCLC_RESOURCES@FCK@@3VCFeatureControlKey@@A; this
0x180785290  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x180785295  test    eax, eax
0x180785297  jz      short loc_1807852FA
0x180785299  mov     rcx, [rsi]; pszPath
0x18078529c  call    cs:__imp_PathFindFileNameW
0x1807852a3  nop     dword ptr [rax+rax+00h]
0x1807852a8  mov     rbx, rax
0x1807852ab  test    rax, rax
0x1807852ae  jz      short loc_1807852FA
0x1807852b0  lea     rdx, aShdoclcDll; "shdoclc.dll"
0x1807852b7  mov     rcx, rax; pszStr1
0x1807852ba  call    cs:__imp_StrCmpICW
0x1807852c1  nop     dword ptr [rax+rax+00h]
0x1807852c6  test    eax, eax
0x1807852c8  jz      short loc_1807852E4
0x1807852ca  lea     rdx, aShdoclc; "shdoclc"
0x1807852d1  mov     rcx, rbx; pszStr1
0x1807852d4  call    cs:__imp_StrCmpICW
0x1807852db  nop     dword ptr [rax+rax+00h]
0x1807852e0  test    eax, eax
0x1807852e2  jnz     short loc_1807852FA
0x1807852e4  mov     rcx, r14; struct CStr *
0x1807852e7  call    ?_IsInsecureHTML@CResProtocol@@CAHAEAVCStr@@@Z; CResProtocol::_IsInsecureHTML(CStr &)
0x1807852ec  test    eax, eax
0x1807852ee  jz      short loc_1807852FA
0x1807852f0  mov     ebx, 80070005h
0x1807852f5  jmp     loc_180785A87
0x1807852fa  lea     rcx, ?FEATURE_ALLOW_APDS_REDIRECTION@FCK@@3VCFeatureControlKey@@A; this
0x180785301  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x180785306  test    eax, eax
0x180785308  jz      short loc_18078536F
0x18078530a  mov     rcx, [rsi]; pszPath
0x18078530d  call    cs:__imp_PathFindFileNameW
0x180785314  nop     dword ptr [rax+rax+00h]
0x180785319  mov     rbx, rax
0x18078531c  test    rax, rax
0x18078531f  jz      short loc_18078536F
0x180785321  lea     rdx, aApdsDll; "apds.dll"
0x180785328  mov     rcx, rax; pszStr1
0x18078532b  call    cs:__imp_StrCmpICW
0x180785332  nop     dword ptr [rax+rax+00h]
0x180785337  test    eax, eax
0x180785339  jz      short loc_180785355
0x18078533b  lea     rdx, aApds; "apds"
0x180785342  mov     rcx, rbx; pszStr1
0x180785345  call    cs:__imp_StrCmpICW
0x18078534c  nop     dword ptr [rax+rax+00h]
0x180785351  test    eax, eax
0x180785353  jnz     short loc_18078536F
0x180785355  mov     rcx, [r14]; pszStr1
0x180785358  lea     rdx, aRedirectHtml; "redirect.html"
0x18078535f  call    cs:__imp_StrCmpICW
0x180785366  nop     dword ptr [rax+rax+00h]
0x18078536b  test    eax, eax
0x18078536d  jz      short loc_1807852F0
0x18078536f  mov     rcx, r13; this
0x180785372  call    ?Length@CStr@@QEBAIXZ; CStr::Length(void)
0x180785377  lea     r9, [rsp+370h+Value+4]; unsigned int *
0x18078537c  mov     rcx, r12; HINSTANCE
0x18078537f  test    eax, eax
0x180785381  jz      short loc_180785389
0x180785383  mov     r8, [r13+0]
0x180785387  jmp     short loc_1807853AD
0x180785389  mov     rdx, [r14]; unsigned __int16 *
0x18078538c  mov     r8d, 17h; unsigned __int16 *
0x180785392  call    ?GetResource@@YAPEAXPEAUHINSTANCE__@@PEBG1PEAK@Z; GetResource(HINSTANCE__ *,ushort const *,ushort const *,ulong *)
0x180785397  mov     rsi, rax
0x18078539a  test    rax, rax
0x18078539d  jnz     short loc_1807853CC
0x18078539f  mov     rcx, r12; HINSTANCE
0x1807853a2  lea     r9, [rsp+370h+Value+4]; unsigned int *
0x1807853a7  mov     r8d, 83Eh; unsigned __int16 *
0x1807853ad  mov     rdx, [r14]; unsigned __int16 *
0x1807853b0  call    ?GetResource@@YAPEAXPEAUHINSTANCE__@@PEBG1PEAK@Z; GetResource(HINSTANCE__ *,ushort const *,ushort const *,ulong *)
0x1807853b5  mov     rsi, rax
0x1807853b8  test    rax, rax
0x1807853bb  jnz     short loc_1807853CC
0x1807853bd  mov     r15d, [rsp+370h+Value+4]
0x1807853c2  mov     ebx, 80070485h
0x1807853c7  jmp     loc_180785A87
0x1807853cc  mov     rax, [r13+0]
0x1807853d0  mov     edx, 8
0x1807853d5  xor     r13d, r13d
0x1807853d8  cmp     word ptr [rax], 23h ; '#'
0x1807853dc  jnz     loc_18078553F
0x1807853e2  cmp     word ptr [rax+2], 32h ; '2'
0x1807853e7  jnz     loc_18078553F
0x1807853ed  cmp     [rax+4], r13w
0x1807853f2  jnz     loc_18078553F
0x1807853f8  mov     r15d, [rsp+370h+Value+4]
0x1807853fd  lea     r9d, [rdx+4]
0x180785401  xor     eax, eax
0x180785403  mov     [rsp+370h+Value], r13d
0x180785408  mov     [rbp+270h+Source], rax
0x18078540c  mov     [rbp+270h+var_298], eax
0x18078540f  mov     [rbp+270h+var_294], ax
0x180785413  cmp     r15d, 28h ; '('
0x180785417  jb      short loc_18078542F
0x180785419  cmp     dword ptr [rsi], 28h ; '('
0x18078541c  jnz     short loc_18078542F
0x18078541e  mov     eax, [rsi+20h]
0x180785421  lea     r14d, [rdx+2Eh]
0x180785425  mov     r8d, [rsi+10h]
0x180785429  movzx   ecx, word ptr [rsi+0Eh]
0x18078542d  jmp     short loc_18078544E
0x18078542f  cmp     r15d, r9d
0x180785432  jb      loc_180785544
0x180785438  cmp     [rsi], r9d
0x18078543b  jnz     loc_180785544
0x180785441  movzx   ecx, word ptr [rsi+0Ah]
0x180785445  mov     r8d, r13d
0x180785448  mov     r14d, 1Ah
0x18078544e  cmp     cx, dx
0x180785451  ja      short loc_18078547E
0x180785453  test    eax, eax
0x180785455  jnz     short loc_18078545E
0x180785457  mov     eax, 1
0x18078545c  shl     eax, cl
0x18078545e  mov     ecx, eax
0x180785460  lea     rdx, [rsp+370h+Value]; unsigned int *
0x180785465  shl     rcx, 2; unsigned __int64
0x180785469  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18078546e  mov     ebx, eax
0x180785470  test    eax, eax
0x180785472  jnz     loc_180785A87
0x180785478  mov     edx, [rsp+370h+Value]
0x18078547c  jmp     short loc_180785497
0x18078547e  mov     edx, r13d
0x180785481  cmp     r8d, 3
0x180785485  jnz     short loc_180785497
0x180785487  sub     cx, 10h
0x18078548b  mov     eax, 0FFEFh
0x180785490  test    ax, cx
0x180785493  cmovz   edx, r9d
0x180785497  lea     ecx, [r15+0Eh]
0x18078549b  mov     eax, 4D42h
0x1807854a0  mov     word ptr [rbp+270h+Source], ax
0x1807854a4  cmp     ecx, 0Eh
0x1807854a7  jb      loc_180785535
0x1807854ad  lea     eax, [r14+rdx]
0x1807854b1  mov     dword ptr [rbp+270h+Source+2], ecx
0x1807854b4  or      edx, 0FFFFFFFFh
0x1807854b7  mov     dword ptr [rbp+270h+Source+6], r13d
0x1807854bb  cmp     eax, r14d
0x1807854be  cmovnb  edx, eax
0x1807854c1  sbb     ebx, ebx
0x1807854c3  and     ebx, 80070216h
0x1807854c9  cmp     eax, r14d
0x1807854cc  jb      loc_180785A87
0x1807854d2  mov     [rbp+270h+var_298+2], edx
0x1807854d5  mov     edx, ecx
  ... truncated ...
```
