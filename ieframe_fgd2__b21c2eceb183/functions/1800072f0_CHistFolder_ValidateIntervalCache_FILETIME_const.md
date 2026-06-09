# CHistFolder::_ValidateIntervalCache(_FILETIME const *)

- ea: `0x1800072f0`
- end: `0x180007fb6`
- name: `?_ValidateIntervalCache@CHistFolder@@IEAAJPEBU_FILETIME@@@Z`
- size: `3270`
- prototype: `__int64 __fastcall(CHistFolder *__hidden this, const struct _FILETIME *)`
- caller_count: `10`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000679c`
- `0x180006e10`
- `0x18008c88c`
- `0x180166240`
- `0x180166680`
- `0x180167000`
- `0x180167bcc`
- `0x1801692d0`
- `0x180169884`
- `0x180169bdc`

## callees

- `0x180006140`
- `0x18000679c`
- `0x1800072f0`
- `0x180009318`
- `0x1800094c0`
- `0x1800097e0`
- `0x180009930`
- `0x180009d18`
- `0x180043df0`
- `0x18005d760`
- `0x180065eb0`
- `0x18007caa8`
- `0x1800bc150`
- `0x18054e310`
- `0x180550010`

## import_xrefs

- `KERNEL32!CompareFileTime` at `0x18000778d`
- `KERNEL32!CompareFileTime` at `0x1800077a4`
- `KERNEL32!CompareFileTime` at `0x1800077e6`
- `KERNEL32!CompareFileTime` at `0x180007807`
- `KERNEL32!CompareFileTime` at `0x180007913`
- `KERNEL32!CompareFileTime` at `0x180007928`
- `KERNEL32!CompareFileTime` at `0x18000793e`
- `KERNEL32!CompareFileTime` at `0x180007a65`
- `KERNEL32!CompareFileTime` at `0x180007cba`
- `KERNEL32!CompareFileTime` at `0x180007d05`
- `KERNEL32!CompareFileTime` at `0x180007d1c`
- `KERNEL32!CompareFileTime` at `0x18000778d`
- `KERNEL32!CompareFileTime` at `0x1800077a4`
- `KERNEL32!CompareFileTime` at `0x1800077e6`
- `KERNEL32!CompareFileTime` at `0x180007807`
- `KERNEL32!CompareFileTime` at `0x180007913`
- `KERNEL32!CompareFileTime` at `0x180007928`
- `KERNEL32!CompareFileTime` at `0x18000793e`
- `KERNEL32!CompareFileTime` at `0x180007a65`
- `KERNEL32!CompareFileTime` at `0x180007cba`
- `KERNEL32!CompareFileTime` at `0x180007d05`
- `KERNEL32!CompareFileTime` at `0x180007d1c`
- `KERNEL32!SystemTimeToFileTime` at `0x180007623`
- `KERNEL32!SystemTimeToFileTime` at `0x1800079f1`
- `KERNEL32!SystemTimeToFileTime` at `0x180007623`
- `KERNEL32!SystemTimeToFileTime` at `0x1800079f1`
- `KERNEL32!GetLocalTime` at `0x18000760f`
- `KERNEL32!GetLocalTime` at `0x1800079df`
- `KERNEL32!GetLocalTime` at `0x18000760f`
- `KERNEL32!GetLocalTime` at `0x1800079df`
- `KERNEL32!FileTimeToSystemTime` at `0x18000787c`
- `KERNEL32!FileTimeToSystemTime` at `0x180007ab8`
- `KERNEL32!FileTimeToSystemTime` at `0x180007ac6`
- `KERNEL32!FileTimeToSystemTime` at `0x18000787c`
- `KERNEL32!FileTimeToSystemTime` at `0x180007ab8`
- `KERNEL32!FileTimeToSystemTime` at `0x180007ac6`
- `KERNEL32!GetLastError` at `0x180007c58`
- `KERNEL32!GetLastError` at `0x180007c58`
- `KERNEL32!ReleaseMutex` at `0x18000747a`
- `KERNEL32!ReleaseMutex` at `0x18000747a`
- `KERNEL32!WaitForSingleObject` at `0x18000739a`
- `KERNEL32!WaitForSingleObject` at `0x18000739a`
- `KERNEL32!LeaveCriticalSection` at `0x1800074ec`
- `KERNEL32!LeaveCriticalSection` at `0x1800074ec`
- `KERNEL32!EnterCriticalSection` at `0x1800074d2`
- `KERNEL32!EnterCriticalSection` at `0x1800074d2`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x180007ef5`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x180007ef5`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x1800076cd`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x1800076cd`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x180007b3c`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x180007b3c`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHUnicodeToAnsi` at `0x180007c0f`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHUnicodeToAnsi` at `0x180007c23`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHUnicodeToAnsi` at `0x180007c0f`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHUnicodeToAnsi` at `0x180007c23`
- `WININET!CreateUrlCacheContainerA` at `0x180007c4e`
- `WININET!CreateUrlCacheContainerA` at `0x180007c4e`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x180007f40`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x180007f92`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x180007f40`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x180007f92`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x180007f09`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x180007f09`
- `msIso!__imp_?IsoGetNextAppContainer@@YAJW4_IsoEnumeration@@PEAXPEAK@Z` at `0x180007f57`
- `msIso!__imp_?IsoGetNextAppContainer@@YAJW4_IsoEnumeration@@PEAXPEAK@Z` at `0x180007fa7`
- `msIso!__imp_?IsoGetNextAppContainer@@YAJW4_IsoEnumeration@@PEAXPEAK@Z` at `0x180007f57`
- `msIso!__imp_?IsoGetNextAppContainer@@YAJW4_IsoEnumeration@@PEAXPEAK@Z` at `0x180007fa7`

## pseudocode

```c
__int64 __fastcall CHistFolder::_ValidateIntervalCache(CHistFolder *this, const struct _FILETIME *a2)
{
  struct _HSFINTERVAL *v2; // r12
  CHistFolder *v3; // r15
  FILETIME v4; // rdx
  unsigned int v5; // edi
  DWORD v6; // eax
  int IntervalCache; // ebx
  __int64 (__fastcall ***i)(CClassFactory *__hidden, const struct _GUID *, void **); // rcx
  GUID *v9; // rax
  __int64 result; // rax
  unsigned __int64 j; // rax
  GUID **v12; // rcx
  GUID *v13; // rdx
  DWORD dwLowDateTime; // esi
  int v15; // ebx
  __int64 v16; // rcx
  int k; // edi
  __int64 v18; // rdx
  int v19; // r14d
  _QWORD *v20; // r13
  __int64 v21; // r9
  int m; // edi
  __int64 v23; // rsi
  __int64 v24; // rbx
  int v25; // r8d
  __int64 v26; // rax
  int v27; // ebx
  __int64 v28; // rdi
  __int64 v29; // rcx
  const FILETIME *v30; // rdi
  __int16 v31; // di
  char *v32; // rdx
  WCHAR *v33; // r9
  __int64 v34; // rcx
  __int64 v35; // r8
  WCHAR *v36; // rax
  __int64 v37; // rcx
  __int64 v38; // rdx
  _WORD *v39; // r9
  const wchar_t *v40; // r8
  signed int LastError; // eax
  _QWORD *v42; // rdi
  LONG v43; // r14d
  struct _HSFINTERVAL *v44; // r15
  int ii; // ebx
  __int64 v46; // rsi
  __int64 v47; // rdi
  __int64 v48; // rax
  unsigned int CurrentProcessManager; // edi
  __int64 v50; // rcx
  __int64 v51; // rcx
  unsigned int v52; // [rsp+60h] [rbp-A0h] BYREF
  char v53[4]; // [rsp+64h] [rbp-9Ch] BYREF
  FILETIME FileTime1; // [rsp+68h] [rbp-98h] BYREF
  FILETIME n; // [rsp+70h] [rbp-90h] BYREF
  struct _FILETIME FileTime; // [rsp+78h] [rbp-88h] BYREF
  FILETIME v57; // [rsp+80h] [rbp-80h] BYREF
  FILETIME v58; // [rsp+88h] [rbp-78h] BYREF
  int v59; // [rsp+90h] [rbp-70h]
  FILETIME PreceedingMonday; // [rsp+98h] [rbp-68h] BYREF
  FILETIME FileTime2; // [rsp+A0h] [rbp-60h] BYREF
  CHistFolder *v62; // [rsp+A8h] [rbp-58h]
  struct _FILETIME v63; // [rsp+B0h] [rbp-50h] BYREF
  char *v64; // [rsp+B8h] [rbp-48h]
  struct _FILETIME v65; // [rsp+C0h] [rbp-40h]
  FILETIME v66[2]; // [rsp+C8h] [rbp-38h] BYREF
  FILETIME v67; // [rsp+D8h] [rbp-28h] BYREF
  FILETIME v68; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR pwszSrc[8]; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v70; // [rsp+F8h] [rbp-8h]
  __int64 v71; // [rsp+108h] [rbp+8h]
  int v72; // [rsp+110h] [rbp+10h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+118h] [rbp+18h] BYREF
  CHAR CachePrefix[32]; // [rsp+128h] [rbp+28h] BYREF
  CHAR pszDst[32]; // [rsp+148h] [rbp+48h] BYREF
  WCHAR pwszDst[8]; // [rsp+168h] [rbp+68h] BYREF
  char v77; // [rsp+178h] [rbp+78h] BYREF
  CHAR pszSrc[272]; // [rsp+1A0h] [rbp+A0h] BYREF

  v2 = 0;
  v62 = this;
  v3 = this;
  if ( a2 )
  {
    v4 = *a2;
  }
  else
  {
    SystemTime = 0;
    GetLocalTime(&SystemTime);
    FileTime = 0;
    SystemTimeToFileTime(&SystemTime, &FileTime);
    v4 = (FILETIME)(864000000000LL
                  * ((__int64)(FileTime.dwLowDateTime | (HIDWORD(*(unsigned __int64 *)&FileTime) << 32))
                   / 864000000000LL));
  }
  v58 = v4;
  PreceedingMonday = 0;
  n = 0;
  FileTime2 = 0;
  v57 = 0;
  if ( *((_DWORD *)v3 + 24) )
    return 0;
  v5 = 0;
  *((_DWORD *)v3 + 24) = 1;
  v52 = 0;
  if ( g_hMutexHistory )
    goto LABEL_5;
  v59 = 258;
  EnterCriticalSection(&g_csDll);
  if ( !g_hMutexHistory )
    SHCreateSharedMutex();
  LeaveCriticalSection(&g_csDll);
  if ( g_hMutexHistory )
  {
LABEL_5:
    v6 = WaitForSingleObject(g_hMutexHistory, 0x1D4C0u);
    v59 = v6;
    if ( !v6 )
      goto LABEL_6;
  }
  else
  {
    v6 = 258;
  }
  IntervalCache = 0;
  if ( v6 == 128 )
  {
LABEL_6:
    IntervalCache = CHistFolder::_LoadIntervalCache(v3);
    if ( IntervalCache >= 0 )
    {
      v65 = (struct _FILETIME)(864000000000LL * (*(_QWORD *)&v58 / 864000000000LL + 1));
      if ( *((_QWORD *)v3 + 15) )
        goto LABEL_31;
      for ( i = &off_180551220; ; i += 7 )
      {
        v9 = (GUID *)i[1];
        if ( !v9 )
          break;
        if ( &CLSID_CUrlHistory == v9 )
        {
          IntervalCache = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(CClassFactory *__hidden, const struct _GUID *, void **), _QWORD, GUID *, __int64))(*i)[3])(
                            i,
                            0,
                            &IID_IUrlHistoryPriv,
                            (__int64)v3 + 120);
          if ( IntervalCache != -2147221231 )
            goto LABEL_44;
          break;
        }
      }
      IntervalCache = -2147221231;
      for ( j = 0; j < 2; ++j )
      {
        v12 = (GUID **)*(&funcs_1800076AA + 2 * j + 1);
        v13 = *v12;
        if ( *v12 )
        {
          while ( v13 != &CLSID_CUrlHistory )
          {
            v13 = v12[1];
            ++v12;
            if ( !v13 )
              goto LABEL_30;
          }
          if ( *v12 )
          {
            IntervalCache = ((__int64 (__fastcall *)(GUID *, _QWORD, GUID *, char *))*(&funcs_1800076AA + 2 * j))(
                              &CLSID_CUrlHistory,
                              0,
                              &IID_IUrlHistoryPriv,
                              (char *)v3 + 120);
            break;
          }
        }
LABEL_30:
        ;
      }
      if ( IntervalCache == -2147221231 )
        IntervalCache = CoCreateInstance(&CLSID_CUrlHistory, 0, 1u, &IID_IUrlHistoryPriv, (LPVOID *)v3 + 15);
LABEL_44:
      if ( IntervalCache >= 0 )
      {
LABEL_31:
        v66[0].dwLowDateTime = 0;
        dwLowDateTime = 0;
        v15 = 0;
        if ( (int)CHistFolder::_EnsureHistStg(v3) >= 0 )
        {
          v16 = *((_QWORD *)v3 + 15);
          *(_DWORD *)v53 = 0;
          if ( (*(int (__fastcall **)(__int64, char *))(*(_QWORD *)v16 + 112LL))(v16, v53) >= 0 )
          {
            v15 = *(_DWORD *)v53;
            if ( *(int *)v53 < 0 )
              v15 = 0;
          }
        }
        FileTime = (struct _FILETIME)(864000000000LL * (1 - v15 + *(_QWORD *)&v58 / 864000000000LL));
        FileTime2 = FileTime;
        PreceedingMonday = GetPreceedingMonday(&v58);
        for ( k = 0; k < *((_DWORD *)v3 + 21); ++k )
        {
          v18 = *((_QWORD *)v3 + 11) + 60LL * k;
          if ( !*(_WORD *)(v18 + 58) )
          {
            v66[0].dwLowDateTime = 1;
            dwLowDateTime = 1;
            IntervalCache = CHistFolder::_DeleteInterval(v3, (struct _HSFINTERVAL *)v18, 1);
            if ( IntervalCache < 0 )
              goto LABEL_45;
          }
        }
        if ( !CHistFolder::_GetInterval(v3, &PreceedingMonday, 1, (struct _HSFINTERVAL **)&v57) )
        {
          v52 = 1;
          IntervalCache = CHistFolder::_DeleteInterval(v3, *(struct _HSFINTERVAL **)&v57, 1);
          v5 = 1;
          if ( IntervalCache < 0 )
            goto LABEL_15;
          dwLowDateTime = 1;
          v66[0].dwLowDateTime = 1;
        }
        v19 = 0;
        v64 = (char *)v3 + 88;
        v20 = (_QWORD *)((char *)v3 + 88);
        while ( v19 < *((_DWORD *)v3 + 21) )
        {
          v20 = (_QWORD *)((char *)v3 + 88);
          v21 = *((_QWORD *)v3 + 11) + 60LL * v19;
          FileTime1 = *(FILETIME *)v21;
          if ( *(_WORD *)(v21 + 58)
            && (unsigned int)(*(_QWORD *)(v21 + 8) / 864000000000LL) - (unsigned int)(*(_QWORD *)v21 / 864000000000LL) == 1
            && CompareFileTime(&FileTime1, &FileTime2) >= 0
            && CompareFileTime(&FileTime1, &PreceedingMonday) < 0 )
          {
            if ( *v20 )
            {
              for ( m = 0; m < *((_DWORD *)v3 + 21); ++m )
              {
                v23 = 60LL * m;
                v24 = v23 + *v20;
                if ( *(_WORD *)(v24 + 58) == 1
                  && CompareFileTime((const FILETIME *)(v23 + *v20), &FileTime1) <= 0
                  && CompareFileTime(&FileTime1, (const FILETIME *)(v24 + 8)) < 0
                  && (unsigned int)(*(_QWORD *)(v23 + *v20 + 8) / 864000000000LL)
                   - (unsigned int)(*(_QWORD *)(v23 + *v20) / 864000000000LL) == 7 )
                {
                  dwLowDateTime = v66[0].dwLowDateTime;
                  goto LABEL_62;
                }
              }
              dwLowDateTime = v66[0].dwLowDateTime;
            }
            v57 = 0;
            FileTime = 0;
            SystemTime = 0;
            if ( FileTimeToSystemTime(&FileTime1, &SystemTime) )
            {
              if ( SystemTime.wDayOfWeek )
                v25 = 1 - SystemTime.wDayOfWeek;
              else
                v25 = -6;
              v26 = v25 + *(_QWORD *)&FileTime1 / 864000000000LL;
            }
            else
            {
              v26 = *(_QWORD *)&FileTime1 / 864000000000LL;
            }
            v57 = (FILETIME)(864000000000LL * v26);
            v27 = 0;
            FileTime = (struct _FILETIME)(864000000000LL
                                        * ((__int64)(((unsigned __int64)(864000000000LL * v26) >> 32 << 32)
                                                   | (unsigned int)(711573504 * v26))
                                         / 864000000000LL
                                         + 7));
            while ( v27 < v19 )
            {
              v28 = 60LL * v27;
              v29 = v28 + *v20;
              if ( *(_WORD *)(v29 + 58) )
              {
                if ( CompareFileTime((const FILETIME *)v29, &FileTime2) >= 0 )
                {
                  v30 = (const FILETIME *)(*v20 + v28);
                  if ( CompareFileTime(&v57, v30) <= 0 && CompareFileTime(v30, &FileTime) < 0 )
                    goto LABEL_62;
                }
              }
              ++v27;
            }
            v71 = 0;
            v72 = 0x10000;
            *(_OWORD *)pwszSrc = 0;
            dwLowDateTime = 1;
            v70 = 0;
            SystemTime = 0;
            v67 = (FILETIME)(864000000000LL * (*(_QWORD *)&v57 / 864000000000LL));
            v68 = (FILETIME)(*(_QWORD *)&v67 + 6048000000000LL);
            GetLocalTime(&SystemTime);
            v63 = 0;
            SystemTimeToFileTime(&SystemTime, &v63);
            v66[0] = (FILETIME)(864000000000LL
                              * ((__int64)(v63.dwLowDateTime | (HIDWORD(*(unsigned __int64 *)&v63) << 32))
                               / 864000000000LL));
            if ( (unsigned int)(*(_QWORD *)&v68 / 864000000000LL) - (unsigned int)(*(_QWORD *)&v67 / 864000000000LL) != 1
              || CompareFileTime(&v67, v66) )
            {
              v31 = 25449;
            }
            else
            {
              v31 = 25444;
            }
            LOWORD(v72) = v31;
            SystemTime = 0;
            *(_OWORD *)&v66[0].dwLowDateTime = 0;
            if ( HIWORD(v72) )
              StringCchPrintfA(v53, 3u, "%02lu", HIWORD(v72));
            else
              v53[0] = 0;
            FileTimeToSystemTime(&v67, &SystemTime);
            FileTimeToSystemTime(&v68, (LPSYSTEMTIME)v66);
            StringCchPrintfA(
              pszSrc,
              0x104u,
              "%s%s%04lu%02lu%02lu%04lu%02lu%02lu",
              "MSHist",
              v53,
              SystemTime.wYear,
              SystemTime.wMonth,
              SystemTime.wDay,
              LOWORD(v66[0].dwLowDateTime),
              HIWORD(v66[0].dwLowDateTime),
              HIWORD(v66[0].dwHighDateTime));
            SHAnsiToUnicode(pszSrc, pwszDst, 25);
            v32 = &v77;
            pwszSrc[0] = 58;
            v33 = &pwszSrc[1];
            v34 = 2147483646;
            v35 = 19;
            while ( v34 && *(_WORD *)v32 )
            {
              *v33 = *(_WORD *)v32;
              v32 += 2;
              ++v33;
              --v34;
              if ( !--v35 )
              {
                --v33;
                break;
              }
            }
            *v33 = 0;
            v36 = pwszSrc;
            v37 = 20;
            while ( *v36 )
            {
              ++v36;
              if ( !--v37 )
                goto LABEL_97;
            }
            v38 = 2147483646;
            v39 = (_WORD *)&v72 - v37;
            v40 = L": ";
            while ( v38 && *v40 )
            {
              *v39++ = *v40++;
              --v38;
              if ( !--v37 )
              {
                --v39;
                break;
              }
            }
            *v39 = 0;
LABEL_97:
            SHUnicodeToAnsi(pwszDst, pszDst, 25);
            SHUnicodeToAnsi(pwszSrc, CachePrefix, 25);
            if ( CreateUrlCacheContainerA(pszDst, CachePrefix, 0, 0, 0, 0xBu, 0, 0) )
            {
              CHistFolder::_NotifyInterval(v3, (struct _HSFINTERVAL *)&v67, 8);
              ++v19;
              v66[0].dwLowDateTime = 1;
            }
            else
            {
              LastError = GetLastError();
              IntervalCache = LastError;
              if ( LastError )
              {
                if ( LastError > 0 )
                  IntervalCache = (unsigned __int16)LastError | 0x80070000;
                if ( IntervalCache < 0 )
                {
                  v5 = v52;
                  goto LABEL_15;
                }
              }
              v66[0].dwLowDateTime = 1;
              ++v19;
            }
          }
          else
          {
LABEL_62:
            ++v19;
          }
        }
        v42 = (_QWORD *)((char *)v3 + 88);
        for ( n = PreceedingMonday; ; n.dwHighDateTime = HIDWORD(v48) )
        {
          v43 = CompareFileTime(&n, &v58);
          if ( v43 > 0 )
            break;
          if ( *v20 )
          {
            v44 = 0;
            for ( ii = 0; ii < *((_DWORD *)v62 + 21); ++ii )
            {
              v46 = 60LL * ii;
              v47 = v46 + *v20;
              if ( *(_WORD *)(v47 + 58) == 1
                && CompareFileTime((const FILETIME *)(v46 + *v20), &n) <= 0
                && CompareFileTime(&n, (const FILETIME *)(v47 + 8)) < 0 )
              {
                v44 = (struct _HSFINTERVAL *)(v46 + *v20);
                if ( (unsigned int)(*((_QWORD *)v44 + 1) / 864000000000LL)
                   - (unsigned int)(*(_QWORD *)v44 / 864000000000LL) == 7 )
                  goto LABEL_112;
              }
            }
            if ( v44 )
            {
LABEL_112:
              dwLowDateTime = v66[0].dwLowDateTime;
              v2 = v44;
              v42 = v64;
              goto LABEL_113;
            }
            dwLowDateTime = v66[0].dwLowDateTime;
            v3 = v62;
            v42 = v64;
          }
          if ( !v43 )
          {
            if ( v2 )
              CHistFolder::_NotifyInterval(v3, v2, 0x20000);
            IntervalCache = CHistFolder::_CreateInterval(v3, &n, 1u);
            if ( IntervalCache < 0 )
            {
              v5 = v52;
              goto LABEL_15;
            }
            dwLowDateTime = 1;
            v66[0].dwLowDateTime = 1;
          }
LABEL_113:
          v20 = v42;
          v3 = v62;
          v48 = 864000000000LL * (*(_QWORD *)&n / 864000000000LL + 1);
          n.dwLowDateTime = 711573504 * (*(_QWORD *)&n / 864000000000LL + 1);
        }
        IntervalCache = CHistFolder::_CleanUpHistory(v3, FileTime2, v65);
        if ( IntervalCache == 1 )
        {
          v5 = 1;
        }
        else
        {
          v5 = v52;
          if ( !dwLowDateTime )
            goto LABEL_15;
        }
        IntervalCache = CHistFolder::_LoadIntervalCache(v3);
        goto LABEL_15;
      }
LABEL_45:
      v5 = 0;
    }
LABEL_15:
    if ( !v59 || v59 == 128 )
      ReleaseMutex(g_hMutexHistory);
  }
  if ( v5 )
  {
    if ( (int)CHistFolder::_EnsureHistStg(v3) >= 0 )
    {
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v3 + 15) + 104LL))(*((_QWORD *)v3 + 15));
      if ( IsProtectedModeProcess() == 1 )
      {
        v52 = 0;
        CurrentProcessManager = IsoGetCurrentProcessManager();
        if ( !(unsigned int)LCIEFindOrCreateProcessManagerAtIL(v50, 123, &v52, 0, 0, 0) )
          IntervalCache = LCIEPostMessageWithoutBuffer(v52, CurrentProcessManager, 0xCE0u, 0);
        v66[0].dwLowDateTime = 0;
        if ( !(unsigned int)IsoGetNextAppContainer(1, &SystemTime, v66) )
        {
          do
          {
            if ( !(unsigned int)LCIEFindOrCreateProcessManagerAtIL(v51, v66[0].dwLowDateTime, &v52, 0, 0, 0) )
              IntervalCache = LCIEPostMessageWithoutBuffer(v52, CurrentProcessManager, 0xCE0u, 0);
          }
          while ( !(unsigned int)IsoGetNextAppContainer(2, &SystemTime, v66) );
        }
      }
    }
  }
  result = (unsigned int)IntervalCache;
  *((_DWORD *)v3 + 24) = 0;
  return result;
}

```

## disassembly

```asm
0x1800072f0  push    rbp
0x1800072f2  push    r12
0x1800072f4  push    r14
0x1800072f6  push    r15
0x1800072f8  lea     rbp, [rsp-1D8h]
0x180007300  sub     rsp, 2D8h
0x180007307  mov     rax, cs:__security_cookie
0x18000730e  xor     rax, rsp
0x180007311  mov     [rbp+1F0h+var_40], rax
0x180007318  xor     r12d, r12d
0x18000731b  mov     [rbp+1F0h+var_248], rcx
0x18000731f  mov     r15, rcx
0x180007322  mov     r14, 0C92A69C000h
0x18000732c  test    rdx, rdx
0x18000732f  jz      loc_180007604
0x180007335  mov     rdx, [rdx]
0x180007338  mov     qword ptr [rbp+1F0h+var_268.dwLowDateTime], rdx
0x18000733c  mov     qword ptr [rbp+1F0h+var_258.dwLowDateTime], r12
0x180007340  mov     qword ptr [rsp+2F0h+var_280.dwLowDateTime], r12
0x180007345  mov     qword ptr [rbp+1F0h+FileTime2.dwLowDateTime], r12
0x180007349  mov     qword ptr [rbp+1F0h+var_270.dwLowDateTime], r12
0x18000734d  cmp     [r15+60h], r12d
0x180007351  jnz     loc_18000742C
0x180007357  mov     [rsp+2F0h+arg_10], rbx
0x18000735f  mov     [rsp+2F0h+var_28], rdi
0x180007367  mov     edi, r12d
0x18000736a  mov     [rsp+2F0h+var_30], r13
0x180007372  mov     r13d, 1
0x180007378  mov     [r15+60h], r13d
0x18000737c  cmp     cs:g_hMutexHistory, rdi
0x180007383  mov     [rsp+2F0h+var_290], r12d
0x180007388  jz      loc_1800074C4
0x18000738e  mov     rcx, cs:g_hMutexHistory; hHandle
0x180007395  mov     edx, 1D4C0h; dwMilliseconds
0x18000739a  call    cs:__imp_WaitForSingleObject
0x1800073a0  mov     [rbp+1F0h+var_260], eax
0x1800073a3  test    eax, eax
0x1800073a5  jnz     loc_180007504
0x1800073ab  mov     rcx, r15; this
0x1800073ae  call    ?_LoadIntervalCache@CHistFolder@@IEAAJXZ; CHistFolder::_LoadIntervalCache(void)
0x1800073b3  mov     ebx, eax
0x1800073b5  test    eax, eax
0x1800073b7  js      loc_180007468
0x1800073bd  mov     ecx, [rbp+1F0h+var_268.dwLowDateTime]
0x1800073c0  lea     rdi, [r15+78h]
0x1800073c4  mov     eax, [rbp+1F0h+var_268.dwHighDateTime]
0x1800073c7  shl     rax, 20h
0x1800073cb  or      rax, rcx
0x1800073ce  mov     [rsp+2F0h+var_20], rsi
0x1800073d6  cqo
0x1800073d8  idiv    r14
0x1800073db  inc     rax
0x1800073de  imul    rax, r14
0x1800073e2  mov     rcx, rax
0x1800073e5  mov     [rbp+1F0h+var_230.dwLowDateTime], eax
0x1800073e8  sar     rcx, 20h
0x1800073ec  mov     [rbp+1F0h+var_230.dwHighDateTime], ecx
0x1800073ef  cmp     [rdi], r12
0x1800073f2  jnz     loc_18000755E
0x1800073f8  lea     rcx, off_180551220
0x1800073ff  lea     rsi, CLSID_CUrlHistory
0x180007406  nop     word ptr [rax+rax+00000000h]
0x180007410  mov     rax, [rcx+8]
0x180007414  test    rax, rax
0x180007417  jz      loc_180007517
0x18000741d  cmp     rsi, rax
0x180007420  jz      loc_180007668
0x180007426  add     rcx, 38h ; '8'
0x18000742a  jmp     short loc_180007410
0x18000742c  xor     eax, eax
0x18000742e  jmp     short loc_1800074A6
0x180007430  mov     r8, qword ptr [rbp+1F0h+var_230.dwLowDateTime]; struct _FILETIME
0x180007434  mov     rcx, r15; this
0x180007437  mov     rdx, qword ptr [rbp+1F0h+FileTime2.dwLowDateTime]; struct _FILETIME
0x18000743b  call    ?_CleanUpHistory@CHistFolder@@IEAAJU_FILETIME@@0@Z; CHistFolder::_CleanUpHistory(_FILETIME,_FILETIME)
0x180007440  mov     r13d, 1
0x180007446  mov     ebx, eax
0x180007448  cmp     eax, r13d
0x18000744b  jz      loc_180007EAA
0x180007451  mov     edi, [rsp+2F0h+var_290]
0x180007455  test    esi, esi
0x180007457  jnz     loc_180007EAD
0x18000745d  xor     r12d, r12d
0x180007460  mov     rsi, [rsp+2F0h+var_20]
0x180007468  mov     eax, [rbp+1F0h+var_260]
0x18000746b  test    eax, eax
0x18000746d  jnz     loc_180007EC5
0x180007473  mov     rcx, cs:g_hMutexHistory; hMutex
0x18000747a  call    cs:__imp_ReleaseMutex
0x180007480  test    edi, edi
0x180007482  jnz     loc_180007ED5
0x180007488  mov     r13, [rsp+2F0h+var_30]
0x180007490  mov     eax, ebx
0x180007492  mov     rbx, [rsp+2F0h+arg_10]
0x18000749a  mov     rdi, [rsp+2F0h+var_28]
0x1800074a2  mov     [r15+60h], r12d
0x1800074a6  mov     rcx, [rbp+1F0h+var_40]
0x1800074ad  xor     rcx, rsp; StackCookie
0x1800074b0  call    __security_check_cookie
0x1800074b5  add     rsp, 2D8h
0x1800074bc  pop     r15
0x1800074be  pop     r14
0x1800074c0  pop     r12
0x1800074c2  pop     rbp
0x1800074c3  retn
0x1800074c4  lea     rcx, g_csDll; lpCriticalSection
0x1800074cb  mov     [rbp+1F0h+var_260], 102h
0x1800074d2  call    cs:__imp_EnterCriticalSection
0x1800074d8  cmp     cs:g_hMutexHistory, rdi
0x1800074df  jz      loc_18000765E
0x1800074e5  lea     rcx, g_csDll; lpCriticalSection
0x1800074ec  call    cs:__imp_LeaveCriticalSection
0x1800074f2  cmp     cs:g_hMutexHistory, rdi
0x1800074f9  jnz     loc_18000738E
0x1800074ff  mov     eax, 102h
0x180007504  mov     ebx, r12d
0x180007507  cmp     eax, 80h
0x18000750c  jnz     loc_180007480
0x180007512  jmp     loc_1800073AB
0x180007517  mov     ebx, 80040111h
0x18000751c  lea     r11, funcs_1800076AA
0x180007523  mov     rax, r12
0x180007526  cmp     rax, 2
0x18000752a  jnb     loc_1800076B1
0x180007530  mov     r10, rax
0x180007533  add     r10, r10
0x180007536  mov     rcx, [r11+r10*8+8]
0x18000753b  mov     rdx, [rcx]
0x18000753e  test    rdx, rdx
0x180007541  jz      short loc_180007559
0x180007543  cmp     rdx, rsi
0x180007546  jz      loc_18000768E
0x18000754c  mov     rdx, [rcx+8]
0x180007550  add     rcx, 8
0x180007554  test    rdx, rdx
0x180007557  jnz     short loc_180007543
0x180007559  inc     rax
0x18000755c  jmp     short loc_180007526
0x18000755e  mov     rcx, r15; this
0x180007561  mov     [rbp+1F0h+var_228.dwLowDateTime], r12d
0x180007565  mov     esi, r12d
0x180007568  mov     ebx, r12d
0x18000756b  call    ?_EnsureHistStg@CHistFolder@@IEAAJXZ; CHistFolder::_EnsureHistStg(void)
0x180007570  test    eax, eax
0x180007572  js      short loc_180007595
0x180007574  mov     rcx, [rdi]
0x180007577  lea     rdx, [rsp+2F0h+var_28C]
0x18000757c  mov     dword ptr [rsp+2F0h+var_28C], r12d
0x180007581  mov     rax, [rcx]
0x180007584  mov     rax, [rax+70h]
0x180007588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000758d  test    eax, eax
0x18000758f  jns     loc_180007E55
0x180007595  mov     ecx, [rbp+1F0h+var_268.dwLowDateTime]
0x180007598  mov     eax, [rbp+1F0h+var_268.dwHighDateTime]
0x18000759b  shl     rax, 20h
0x18000759f  or      rax, rcx
0x1800075a2  mov     ecx, r13d
0x1800075a5  cqo
0x1800075a7  sub     ecx, ebx
0x1800075a9  idiv    r14
0x1800075ac  movsxd  rcx, ecx
0x1800075af  add     rax, rcx
0x1800075b2  imul    rax, r14
0x1800075b6  mov     rcx, rax
0x1800075b9  mov     [rsp+2F0h+FileTime.dwLowDateTime], eax
0x1800075bd  sar     rcx, 20h
0x1800075c1  mov     [rsp+2F0h+FileTime.dwHighDateTime], ecx
0x1800075c5  lea     rcx, [rbp+1F0h+var_268]; struct _FILETIME *
0x1800075c9  mov     rax, qword ptr [rsp+2F0h+FileTime.dwLowDateTime]
0x1800075ce  mov     qword ptr [rbp+1F0h+FileTime2.dwLowDateTime], rax
0x1800075d2  call    ?GetPreceedingMonday@@YA?AU_FILETIME@@PEBU1@@Z; GetPreceedingMonday(_FILETIME const *)
0x1800075d7  mov     qword ptr [rbp+1F0h+var_258.dwLowDateTime], rax
0x1800075db  mov     edi, r12d
0x1800075de  xchg    ax, ax
0x1800075e0  cmp     edi, [r15+54h]
0x1800075e4  jge     loc_1800076E5
0x1800075ea  movsxd  rax, edi
0x1800075ed  imul    rdx, rax, 3Ch ; '<'
0x1800075f1  add     rdx, [r15+58h]; struct _HSFINTERVAL *
0x1800075f5  cmp     [rdx+3Ah], r13w
0x1800075fa  jb      loc_180007E14
0x180007600  inc     edi
0x180007602  jmp     short loc_1800075E0
0x180007604  xorps   xmm0, xmm0
0x180007607  lea     rcx, [rbp+1F0h+SystemTime]; lpSystemTime
0x18000760b  movups  xmmword ptr [rbp+1F0h+SystemTime.wYear], xmm0
0x18000760f  call    cs:__imp_GetLocalTime
0x180007615  lea     rdx, [rsp+2F0h+FileTime]; lpFileTime
0x18000761a  mov     qword ptr [rsp+2F0h+FileTime.dwLowDateTime], r12
0x18000761f  lea     rcx, [rbp+1F0h+SystemTime]; lpSystemTime
0x180007623  call    cs:__imp_SystemTimeToFileTime
0x180007629  mov     rcx, qword ptr [rsp+2F0h+FileTime.dwLowDateTime]
0x18000762e  mov     edx, ecx
0x180007630  mov     rax, rcx
0x180007633  shr     rax, 20h
0x180007637  shl     rax, 20h
0x18000763b  or      rax, rdx
0x18000763e  cqo
0x180007640  idiv    r14
0x180007643  imul    rax, r14
0x180007647  mov     rdx, rax
0x18000764a  mov     eax, eax
0x18000764c  sar     rdx, 20h
0x180007650  mov     edx, edx
0x180007652  shl     rdx, 20h
0x180007656  or      rdx, rax
0x180007659  jmp     loc_180007338
0x18000765e  call    SHCreateSharedMutex
0x180007663  jmp     loc_1800074E5
0x180007668  mov     rax, [rcx]
0x18000766b  lea     r8, IID_IUrlHistoryPriv
0x180007672  mov     r9, rdi
0x180007675  xor     edx, edx
0x180007677  mov     rax, [rax+18h]
0x18000767b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007680  mov     ebx, eax
0x180007682  cmp     eax, 80040111h
0x180007687  jnz     short loc_1800076D5
0x180007689  jmp     loc_180007517
0x18000768e  cmp     [rcx], r12
0x180007691  jz      loc_180007559
0x180007697  mov     rax, ds:(funcs_1800076AA - 180552950h)[r11+r10*8]
0x18000769b  lea     r8, IID_IUrlHistoryPriv
0x1800076a2  mov     r9, rdi
0x1800076a5  xor     edx, edx
0x1800076a7  mov     rcx, rsi
0x1800076aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076af  mov     ebx, eax
0x1800076b1  cmp     ebx, 80040111h
0x1800076b7  jnz     short loc_1800076D5
0x1800076b9  lea     r9, IID_IUrlHistoryPriv; riid
0x1800076c0  mov     [rsp+2F0h+ppv], rdi; ppv
0x1800076c5  mov     r8d, r13d; dwClsContext
0x1800076c8  xor     edx, edx; pUnkOuter
0x1800076ca  mov     rcx, rsi; rclsid
0x1800076cd  call    cs:__imp_CoCreateInstance
0x1800076d3  mov     ebx, eax
0x1800076d5  test    ebx, ebx
0x1800076d7  jns     loc_18000755E
0x1800076dd  mov     edi, r12d
0x1800076e0  jmp     loc_180007460
0x1800076e5  lea     r9, [rbp+1F0h+var_270]; struct _HSFINTERVAL **
0x1800076e9  mov     r8d, r13d; int
0x1800076ec  lea     rdx, [rbp+1F0h+var_258]; struct _FILETIME *
0x1800076f0  mov     rcx, r15; this
0x1800076f3  call    ?_GetInterval@CHistFolder@@IEAAJPEBU_FILETIME@@HPEAPEAU_HSFINTERVAL@@@Z; CHistFolder::_GetInterval(_FILETIME const *,int,_HSFINTERVAL * *)
0x1800076f8  test    eax, eax
0x1800076fa  jz      loc_180007E64
0x180007700  lea     rdi, [r15+58h]
0x180007704  mov     r14d, r12d
0x180007707  mov     [rbp+1F0h+var_238], rdi
0x18000770b  mov     r13, rdi
0x18000770e  mov     rbx, 0C92A69C000h
0x180007718  nop     dword ptr [rax+rax+00000000h]
0x180007720  cmp     r14d, [r15+54h]
0x180007724  jge     loc_180007CA4
0x18000772a  movsxd  rax, r14d
0x18000772d  lea     r13, [r15+58h]
0x180007731  imul    r9, rax, 3Ch ; '<'
0x180007735  add     r9, [r13+0]
0x180007739  mov     rax, [r9]
0x18000773c  mov     qword ptr [rsp+2F0h+FileTime1.dwLowDateTime], rax
0x180007741  cmp     word ptr [r9+3Ah], 1
0x180007747  jb      loc_180007858
0x18000774d  mov     ecx, [r9+8]
0x180007751  mov     eax, [r9+0Ch]
0x180007755  shl     rax, 20h
0x180007759  or      rax, rcx
0x18000775c  mov     ecx, [r9]
0x18000775f  cqo
0x180007761  idiv    rbx
0x180007764  mov     r8, rax
0x180007767  mov     eax, [r9+4]
0x18000776b  shl     rax, 20h
0x18000776f  or      rax, rcx
0x180007772  cqo
0x180007774  idiv    rbx
0x180007777  sub     r8d, eax
0x18000777a  cmp     r8d, 1
0x18000777e  jnz     loc_180007858
0x180007784  lea     rdx, [rbp+1F0h+FileTime2]; lpFileTime2
0x180007788  lea     rcx, [rsp+2F0h+FileTime1]; lpFileTime1
0x18000778d  call    cs:__imp_CompareFileTime
0x180007793  test    eax, eax
0x180007795  js      loc_180007858
0x18000779b  lea     rdx, [rbp+1F0h+var_258]; lpFileTime2
0x18000779f  lea     rcx, [rsp+2F0h+FileTime1]; lpFileTime1
0x1800077a4  call    cs:__imp_CompareFileTime
0x1800077aa  test    eax, eax
0x1800077ac  jns     loc_180007858
0x1800077b2  cmp     [r13+0], r12
0x1800077b6  jz      loc_180007863
0x1800077bc  mov     edi, r12d
0x1800077bf  cmp     edi, [r15+54h]
0x1800077c3  jge     loc_180007860
0x1800077c9  mov     rbx, [r13+0]
0x1800077cd  movsxd  rax, edi
0x1800077d0  imul    rsi, rax, 3Ch ; '<'
0x1800077d4  add     rbx, rsi
  ... truncated ...
```
