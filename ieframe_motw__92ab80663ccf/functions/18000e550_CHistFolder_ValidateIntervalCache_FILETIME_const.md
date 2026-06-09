# CHistFolder::_ValidateIntervalCache(_FILETIME const *)

- ea: `0x18000e550`
- end: `0x18000f28c`
- name: `?_ValidateIntervalCache@CHistFolder@@IEAAJPEBU_FILETIME@@@Z`
- size: `3388`
- prototype: `__int64 __fastcall(CHistFolder *__hidden this, const struct _FILETIME *)`
- caller_count: `10`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000d928`
- `0x18000e020`
- `0x1800933d8`
- `0x180177400`
- `0x1801777c0`
- `0x180178250`
- `0x180178f50`
- `0x18017a774`
- `0x18017ad64`
- `0x18017b0e8`

## callees

- `0x18000d260`
- `0x18000d928`
- `0x18000e550`
- `0x18001071c`
- `0x1800108e0`
- `0x180010ca4`
- `0x1800110fc`
- `0x180011528`
- `0x180045d20`
- `0x1800623d0`
- `0x18006a7c8`
- `0x180072ccc`
- `0x180082fb0`
- `0x1800c2e80`
- `0x180591f80`
- `0x180594010`

## import_xrefs

- `KERNEL32!CompareFileTime` at `0x18000e9bd`
- `KERNEL32!CompareFileTime` at `0x18000e9da`
- `KERNEL32!CompareFileTime` at `0x18000ea22`
- `KERNEL32!CompareFileTime` at `0x18000ea49`
- `KERNEL32!CompareFileTime` at `0x18000eb64`
- `KERNEL32!CompareFileTime` at `0x18000eb80`
- `KERNEL32!CompareFileTime` at `0x18000eb9b`
- `KERNEL32!CompareFileTime` at `0x18000ecd6`
- `KERNEL32!CompareFileTime` at `0x18000ef59`
- `KERNEL32!CompareFileTime` at `0x18000efaa`
- `KERNEL32!CompareFileTime` at `0x18000efc7`
- `KERNEL32!CompareFileTime` at `0x18000e9bd`
- `KERNEL32!CompareFileTime` at `0x18000e9da`
- `KERNEL32!CompareFileTime` at `0x18000ea22`
- `KERNEL32!CompareFileTime` at `0x18000ea49`
- `KERNEL32!CompareFileTime` at `0x18000eb64`
- `KERNEL32!CompareFileTime` at `0x18000eb80`
- `KERNEL32!CompareFileTime` at `0x18000eb9b`
- `KERNEL32!CompareFileTime` at `0x18000ecd6`
- `KERNEL32!CompareFileTime` at `0x18000ef59`
- `KERNEL32!CompareFileTime` at `0x18000efaa`
- `KERNEL32!CompareFileTime` at `0x18000efc7`
- `KERNEL32!SystemTimeToFileTime` at `0x18000ec5c`
- `KERNEL32!SystemTimeToFileTime` at `0x18000ec5c`
- `KERNEL32!GetLocalTime` at `0x18000ec44`
- `KERNEL32!GetLocalTime` at `0x18000ec44`
- `KERNEL32!FileTimeToSystemTime` at `0x18000eac4`
- `KERNEL32!FileTimeToSystemTime` at `0x18000ed2f`
- `KERNEL32!FileTimeToSystemTime` at `0x18000ed43`
- `KERNEL32!FileTimeToSystemTime` at `0x18000eac4`
- `KERNEL32!FileTimeToSystemTime` at `0x18000ed2f`
- `KERNEL32!FileTimeToSystemTime` at `0x18000ed43`
- `KERNEL32!GetLastError` at `0x18000eeea`
- `KERNEL32!GetLastError` at `0x18000eeea`
- `KERNEL32!ReleaseMutex` at `0x18000e6e8`
- `KERNEL32!ReleaseMutex` at `0x18000e6e8`
- `KERNEL32!WaitForSingleObject` at `0x18000e5ef`
- `KERNEL32!WaitForSingleObject` at `0x18000e5ef`
- `KERNEL32!LeaveCriticalSection` at `0x18000e765`
- `KERNEL32!LeaveCriticalSection` at `0x18000e765`
- `KERNEL32!EnterCriticalSection` at `0x18000e745`
- `KERNEL32!EnterCriticalSection` at `0x18000e745`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x18000f1a7`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x18000f1a7`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x18000e8fd`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x18000e8fd`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x18000edbf`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x18000edbf`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHUnicodeToAnsi` at `0x18000ee8f`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHUnicodeToAnsi` at `0x18000eea9`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHUnicodeToAnsi` at `0x18000ee8f`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHUnicodeToAnsi` at `0x18000eea9`
- `WININET!CreateUrlCacheContainerA` at `0x18000eeda`
- `WININET!CreateUrlCacheContainerA` at `0x18000eeda`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x18000f1fe`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x18000f25c`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x18000f1fe`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x18000f25c`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x18000f1c1`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x18000f1c1`
- `msIso!__imp_?IsoGetNextAppContainer@@YAJW4_IsoEnumeration@@PEAXPEAK@Z` at `0x18000f21b`
- `msIso!__imp_?IsoGetNextAppContainer@@YAJW4_IsoEnumeration@@PEAXPEAK@Z` at `0x18000f277`
- `msIso!__imp_?IsoGetNextAppContainer@@YAJW4_IsoEnumeration@@PEAXPEAK@Z` at `0x18000f21b`
- `msIso!__imp_?IsoGetNextAppContainer@@YAJW4_IsoEnumeration@@PEAXPEAK@Z` at `0x18000f277`

## pseudocode

```c
__int64 __fastcall CHistFolder::_ValidateIntervalCache(CHistFolder *this, const struct _FILETIME *a2)
{
  CHistFolder *v2; // r15
  FILETIME CurrentUserPerceivedDay; // rax
  struct _HSFINTERVAL *v4; // r12
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
  FILETIME v56; // [rsp+78h] [rbp-88h] BYREF
  FILETIME v57; // [rsp+80h] [rbp-80h] BYREF
  FILETIME v58; // [rsp+88h] [rbp-78h] BYREF
  int v59; // [rsp+90h] [rbp-70h]
  FILETIME PreceedingMonday; // [rsp+98h] [rbp-68h] BYREF
  FILETIME FileTime2; // [rsp+A0h] [rbp-60h] BYREF
  CHistFolder *v62; // [rsp+A8h] [rbp-58h]
  struct _FILETIME FileTime; // [rsp+B0h] [rbp-50h] BYREF
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

  v62 = this;
  v2 = this;
  if ( a2 )
    CurrentUserPerceivedDay = *a2;
  else
    CurrentUserPerceivedDay = GetCurrentUserPerceivedDay();
  v4 = 0;
  v57 = CurrentUserPerceivedDay;
  PreceedingMonday = 0;
  n = 0;
  FileTime2 = 0;
  v56 = 0;
  if ( *((_DWORD *)v2 + 24) )
    return 0;
  v5 = 0;
  *((_DWORD *)v2 + 24) = 1;
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
    IntervalCache = CHistFolder::_LoadIntervalCache(v2);
    if ( IntervalCache >= 0 )
    {
      v65 = (struct _FILETIME)(864000000000LL * (*(_QWORD *)&v57 / 864000000000LL + 1));
      if ( *((_QWORD *)v2 + 15) )
        goto LABEL_31;
      for ( i = &off_180595220; ; i += 7 )
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
                            (__int64)v2 + 120);
          if ( IntervalCache != -2147221231 )
            goto LABEL_44;
          break;
        }
      }
      IntervalCache = -2147221231;
      for ( j = 0; j < 2; ++j )
      {
        v12 = (GUID **)*(&funcs_18000E8DA + 2 * j + 1);
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
            IntervalCache = ((__int64 (__fastcall *)(GUID *, _QWORD, GUID *, char *))*(&funcs_18000E8DA + 2 * j))(
                              &CLSID_CUrlHistory,
                              0,
                              &IID_IUrlHistoryPriv,
                              (char *)v2 + 120);
            break;
          }
        }
LABEL_30:
        ;
      }
      if ( IntervalCache == -2147221231 )
        IntervalCache = CoCreateInstance(&CLSID_CUrlHistory, 0, 1u, &IID_IUrlHistoryPriv, (LPVOID *)v2 + 15);
LABEL_44:
      if ( IntervalCache >= 0 )
      {
LABEL_31:
        v66[0].dwLowDateTime = 0;
        dwLowDateTime = 0;
        v15 = 0;
        if ( (int)CHistFolder::_EnsureHistStg(v2) >= 0 )
        {
          v16 = *((_QWORD *)v2 + 15);
          *(_DWORD *)v53 = 0;
          if ( (*(int (__fastcall **)(__int64, char *))(*(_QWORD *)v16 + 112LL))(v16, v53) >= 0 )
          {
            v15 = *(_DWORD *)v53;
            if ( *(int *)v53 < 0 )
              v15 = 0;
          }
        }
        v58 = (FILETIME)(864000000000LL * (1 - v15 + *(_QWORD *)&v57 / 864000000000LL));
        FileTime2 = v58;
        PreceedingMonday = GetPreceedingMonday(&v57);
        for ( k = 0; k < *((_DWORD *)v2 + 21); ++k )
        {
          v18 = *((_QWORD *)v2 + 11) + 60LL * k;
          if ( !*(_WORD *)(v18 + 58) )
          {
            v66[0].dwLowDateTime = 1;
            dwLowDateTime = 1;
            IntervalCache = CHistFolder::_DeleteInterval(v2, (struct _HSFINTERVAL *)v18, 1);
            if ( IntervalCache < 0 )
              goto LABEL_45;
          }
        }
        if ( !CHistFolder::_GetInterval(v2, &PreceedingMonday, 1, (struct _HSFINTERVAL **)&v56) )
        {
          v52 = 1;
          IntervalCache = CHistFolder::_DeleteInterval(v2, *(struct _HSFINTERVAL **)&v56, 1);
          v5 = 1;
          if ( IntervalCache < 0 )
            goto LABEL_15;
          dwLowDateTime = 1;
          v66[0].dwLowDateTime = 1;
        }
        v19 = 0;
        v64 = (char *)v2 + 88;
        v20 = (_QWORD *)((char *)v2 + 88);
        while ( v19 < *((_DWORD *)v2 + 21) )
        {
          v20 = (_QWORD *)((char *)v2 + 88);
          v21 = *((_QWORD *)v2 + 11) + 60LL * v19;
          FileTime1 = *(FILETIME *)v21;
          if ( *(_WORD *)(v21 + 58)
            && (unsigned int)(*(_QWORD *)(v21 + 8) / 864000000000LL) - (unsigned int)(*(_QWORD *)v21 / 864000000000LL) == 1
            && CompareFileTime(&FileTime1, &FileTime2) >= 0
            && CompareFileTime(&FileTime1, &PreceedingMonday) < 0 )
          {
            if ( *v20 )
            {
              for ( m = 0; m < *((_DWORD *)v2 + 21); ++m )
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
            v56 = 0;
            v58 = 0;
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
            v56 = (FILETIME)(864000000000LL * v26);
            v27 = 0;
            v58 = (FILETIME)(864000000000LL
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
                  if ( CompareFileTime(&v56, v30) <= 0 && CompareFileTime(v30, &v58) < 0 )
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
            v67 = (FILETIME)(864000000000LL * (*(_QWORD *)&v56 / 864000000000LL));
            v68 = (FILETIME)(*(_QWORD *)&v67 + 6048000000000LL);
            GetLocalTime(&SystemTime);
            FileTime = 0;
            SystemTimeToFileTime(&SystemTime, &FileTime);
            v66[0] = (FILETIME)(864000000000LL
                              * ((__int64)(FileTime.dwLowDateTime | (HIDWORD(*(unsigned __int64 *)&FileTime) << 32))
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
              CHistFolder::_NotifyInterval(v2, (struct _HSFINTERVAL *)&v67, 8);
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
        v42 = (_QWORD *)((char *)v2 + 88);
        for ( n = PreceedingMonday; ; n.dwHighDateTime = HIDWORD(v48) )
        {
          v43 = CompareFileTime(&n, &v57);
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
              v4 = v44;
              v42 = v64;
              goto LABEL_113;
            }
            dwLowDateTime = v66[0].dwLowDateTime;
            v2 = v62;
            v42 = v64;
          }
          if ( !v43 )
          {
            if ( v4 )
              CHistFolder::_NotifyInterval(v2, v4, 0x20000);
            IntervalCache = CHistFolder::_CreateInterval(v2, &n, 1u);
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
          v2 = v62;
          v48 = 864000000000LL * (*(_QWORD *)&n / 864000000000LL + 1);
          n.dwLowDateTime = 711573504 * (*(_QWORD *)&n / 864000000000LL + 1);
        }
        IntervalCache = CHistFolder::_CleanUpHistory(v2, FileTime2, v65);
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
        IntervalCache = CHistFolder::_LoadIntervalCache(v2);
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
    if ( (int)CHistFolder::_EnsureHistStg(v2) >= 0 )
    {
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v2 + 15) + 104LL))(*((_QWORD *)v2 + 15));
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
  *((_DWORD *)v2 + 24) = 0;
  return result;
}

```

## disassembly

```asm
0x18000e550  push    rbp
0x18000e552  push    r12
0x18000e554  push    r15
0x18000e556  lea     rbp, [rsp-1E0h]
0x18000e55e  sub     rsp, 2E0h
0x18000e565  mov     rax, cs:__security_cookie
0x18000e56c  xor     rax, rsp
0x18000e56f  mov     [rbp+1F0h+var_40], rax
0x18000e576  mov     [rbp+1F0h+var_248], rcx
0x18000e57a  mov     r15, rcx
0x18000e57d  test    rdx, rdx
0x18000e580  jz      loc_18000E884
0x18000e586  mov     rax, [rdx]
0x18000e589  xor     r12d, r12d
0x18000e58c  mov     qword ptr [rbp+1F0h+var_270.dwLowDateTime], rax
0x18000e590  mov     qword ptr [rbp+1F0h+var_258.dwLowDateTime], r12
0x18000e594  mov     qword ptr [rsp+2F0h+var_280.dwLowDateTime], r12
0x18000e599  mov     qword ptr [rbp+1F0h+FileTime2.dwLowDateTime], r12
0x18000e59d  mov     qword ptr [rsp+2F0h+var_278.dwLowDateTime], r12
0x18000e5a2  cmp     [r15+60h], r12d
0x18000e5a6  jnz     loc_18000E68F
0x18000e5ac  mov     [rsp+2F0h+arg_10], rbx
0x18000e5b4  mov     [rsp+2F0h+var_20], rdi
0x18000e5bc  mov     edi, r12d
0x18000e5bf  mov     [rsp+2F0h+var_28], r13
0x18000e5c7  mov     r13d, 1
0x18000e5cd  mov     [r15+60h], r13d
0x18000e5d1  cmp     cs:g_hMutexHistory, rdi
0x18000e5d8  mov     [rsp+2F0h+var_290], r12d
0x18000e5dd  jz      loc_18000E737
0x18000e5e3  mov     rcx, cs:g_hMutexHistory; hHandle
0x18000e5ea  mov     edx, 1D4C0h; dwMilliseconds
0x18000e5ef  call    cs:__imp_WaitForSingleObject
0x18000e5f6  nop     dword ptr [rax+rax+00h]
0x18000e5fb  mov     [rbp+1F0h+var_260], eax
0x18000e5fe  test    eax, eax
0x18000e600  jnz     loc_18000E783
0x18000e606  mov     rcx, r15; this
0x18000e609  call    ?_LoadIntervalCache@CHistFolder@@IEAAJXZ; CHistFolder::_LoadIntervalCache(void)
0x18000e60e  mov     ebx, eax
0x18000e610  test    eax, eax
0x18000e612  js      loc_18000E6D6
0x18000e618  mov     ecx, [rbp+1F0h+var_270.dwLowDateTime]
0x18000e61b  lea     rdi, [r15+78h]
0x18000e61f  mov     eax, [rbp+1F0h+var_270.dwHighDateTime]
0x18000e622  shl     rax, 20h
0x18000e626  or      rax, rcx
0x18000e629  mov     [rsp+2F0h+var_30], r14
0x18000e631  cqo
0x18000e633  mov     [rsp+2F0h+var_18], rsi
0x18000e63b  mov     r14, 0C92A69C000h
0x18000e645  idiv    r14
0x18000e648  inc     rax
0x18000e64b  imul    rax, r14
0x18000e64f  mov     rcx, rax
0x18000e652  mov     [rbp+1F0h+var_230.dwLowDateTime], eax
0x18000e655  sar     rcx, 20h
0x18000e659  mov     [rbp+1F0h+var_230.dwHighDateTime], ecx
0x18000e65c  cmp     [rdi], r12
0x18000e65f  jnz     loc_18000E7DD
0x18000e665  lea     rcx, off_180595220
0x18000e66c  lea     rsi, CLSID_CUrlHistory
0x18000e673  mov     rax, [rcx+8]
0x18000e677  test    rax, rax
0x18000e67a  jz      loc_18000E796
0x18000e680  cmp     rsi, rax
0x18000e683  jz      loc_18000E898
0x18000e689  add     rcx, 38h ; '8'
0x18000e68d  jmp     short loc_18000E673
0x18000e68f  xor     eax, eax
0x18000e691  jmp     loc_18000E71A
0x18000e696  mov     r8, qword ptr [rbp+1F0h+var_230.dwLowDateTime]; struct _FILETIME
0x18000e69a  mov     rcx, r15; this
0x18000e69d  mov     rdx, qword ptr [rbp+1F0h+FileTime2.dwLowDateTime]; struct _FILETIME
0x18000e6a1  call    ?_CleanUpHistory@CHistFolder@@IEAAJU_FILETIME@@0@Z; CHistFolder::_CleanUpHistory(_FILETIME,_FILETIME)
0x18000e6a6  mov     r13d, 1
0x18000e6ac  mov     ebx, eax
0x18000e6ae  cmp     eax, r13d
0x18000e6b1  jz      loc_18000F15C
0x18000e6b7  mov     edi, [rsp+2F0h+var_290]
0x18000e6bb  test    esi, esi
0x18000e6bd  jnz     loc_18000F15F
0x18000e6c3  xor     r12d, r12d
0x18000e6c6  mov     rsi, [rsp+2F0h+var_18]
0x18000e6ce  mov     r14, [rsp+2F0h+var_30]
0x18000e6d6  mov     eax, [rbp+1F0h+var_260]
0x18000e6d9  test    eax, eax
0x18000e6db  jnz     loc_18000F177
0x18000e6e1  mov     rcx, cs:g_hMutexHistory; hMutex
0x18000e6e8  call    cs:__imp_ReleaseMutex
0x18000e6ef  nop     dword ptr [rax+rax+00h]
0x18000e6f4  test    edi, edi
0x18000e6f6  jnz     loc_18000F187
0x18000e6fc  mov     r13, [rsp+2F0h+var_28]
0x18000e704  mov     eax, ebx
0x18000e706  mov     rbx, [rsp+2F0h+arg_10]
0x18000e70e  mov     rdi, [rsp+2F0h+var_20]
0x18000e716  mov     [r15+60h], r12d
0x18000e71a  mov     rcx, [rbp+1F0h+var_40]
0x18000e721  xor     rcx, rsp; StackCookie
0x18000e724  call    __security_check_cookie
0x18000e729  add     rsp, 2E0h
0x18000e730  pop     r15
0x18000e732  pop     r12
0x18000e734  pop     rbp
0x18000e735  retn
0x18000e737  lea     rcx, g_csDll; lpCriticalSection
0x18000e73e  mov     [rbp+1F0h+var_260], 102h
0x18000e745  call    cs:__imp_EnterCriticalSection
0x18000e74c  nop     dword ptr [rax+rax+00h]
0x18000e751  cmp     cs:g_hMutexHistory, rdi
0x18000e758  jz      loc_18000E88E
0x18000e75e  lea     rcx, g_csDll; lpCriticalSection
0x18000e765  call    cs:__imp_LeaveCriticalSection
0x18000e76c  nop     dword ptr [rax+rax+00h]
0x18000e771  cmp     cs:g_hMutexHistory, rdi
0x18000e778  jnz     loc_18000E5E3
0x18000e77e  mov     eax, 102h
0x18000e783  mov     ebx, r12d
0x18000e786  cmp     eax, 80h
0x18000e78b  jnz     loc_18000E6F4
0x18000e791  jmp     loc_18000E606
0x18000e796  mov     ebx, 80040111h
0x18000e79b  lea     r11, funcs_18000E8DA
0x18000e7a2  mov     rax, r12
0x18000e7a5  cmp     rax, 2
0x18000e7a9  jnb     loc_18000E8E1
0x18000e7af  mov     r10, rax
0x18000e7b2  add     r10, r10
0x18000e7b5  mov     rcx, [r11+r10*8+8]
0x18000e7ba  mov     rdx, [rcx]
0x18000e7bd  test    rdx, rdx
0x18000e7c0  jz      short loc_18000E7D8
0x18000e7c2  cmp     rdx, rsi
0x18000e7c5  jz      loc_18000E8BE
0x18000e7cb  mov     rdx, [rcx+8]
0x18000e7cf  add     rcx, 8
0x18000e7d3  test    rdx, rdx
0x18000e7d6  jnz     short loc_18000E7C2
0x18000e7d8  inc     rax
0x18000e7db  jmp     short loc_18000E7A5
0x18000e7dd  mov     rcx, r15; this
0x18000e7e0  mov     [rbp+1F0h+var_228.dwLowDateTime], r12d
0x18000e7e4  mov     esi, r12d
0x18000e7e7  mov     ebx, r12d
0x18000e7ea  call    ?_EnsureHistStg@CHistFolder@@IEAAJXZ; CHistFolder::_EnsureHistStg(void)
0x18000e7ef  test    eax, eax
0x18000e7f1  js      short loc_18000E814
0x18000e7f3  mov     rcx, [rdi]
0x18000e7f6  lea     rdx, [rsp+2F0h+var_28C]
0x18000e7fb  mov     dword ptr [rsp+2F0h+var_28C], r12d
0x18000e800  mov     rax, [rcx]
0x18000e803  mov     rax, [rax+70h]
0x18000e807  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e80c  test    eax, eax
0x18000e80e  jns     loc_18000F106
0x18000e814  mov     ecx, [rbp+1F0h+var_270.dwLowDateTime]
0x18000e817  mov     eax, [rbp+1F0h+var_270.dwHighDateTime]
0x18000e81a  shl     rax, 20h
0x18000e81e  or      rax, rcx
0x18000e821  mov     ecx, r13d
0x18000e824  cqo
0x18000e826  sub     ecx, ebx
0x18000e828  idiv    r14
0x18000e82b  movsxd  rcx, ecx
0x18000e82e  add     rax, rcx
0x18000e831  imul    rax, r14
0x18000e835  mov     rcx, rax
0x18000e838  mov     [rbp+1F0h+var_268.dwLowDateTime], eax
0x18000e83b  sar     rcx, 20h
0x18000e83f  mov     [rbp+1F0h+var_268.dwHighDateTime], ecx
0x18000e842  lea     rcx, [rbp+1F0h+var_270]; struct _FILETIME *
0x18000e846  mov     rax, qword ptr [rbp+1F0h+var_268.dwLowDateTime]
0x18000e84a  mov     qword ptr [rbp+1F0h+FileTime2.dwLowDateTime], rax
0x18000e84e  call    ?GetPreceedingMonday@@YA?AU_FILETIME@@PEBU1@@Z; GetPreceedingMonday(_FILETIME const *)
0x18000e853  mov     qword ptr [rbp+1F0h+var_258.dwLowDateTime], rax
0x18000e857  mov     edi, r12d
0x18000e85a  nop     word ptr [rax+rax+00h]
0x18000e860  cmp     edi, [r15+54h]
0x18000e864  jge     loc_18000E91B
0x18000e86a  movsxd  rax, edi
0x18000e86d  imul    rdx, rax, 3Ch ; '<'
0x18000e871  add     rdx, [r15+58h]; struct _HSFINTERVAL *
0x18000e875  cmp     [rdx+3Ah], r13w
0x18000e87a  jb      loc_18000F0C5
0x18000e880  inc     edi
0x18000e882  jmp     short loc_18000E860
0x18000e884  call    ?GetCurrentUserPerceivedDay@@YA?AU_FILETIME@@XZ; GetCurrentUserPerceivedDay(void)
0x18000e889  jmp     loc_18000E589
0x18000e88e  call    SHCreateSharedMutex
0x18000e893  jmp     loc_18000E75E
0x18000e898  mov     rax, [rcx]
0x18000e89b  lea     r8, IID_IUrlHistoryPriv
0x18000e8a2  mov     r9, rdi
0x18000e8a5  xor     edx, edx
0x18000e8a7  mov     rax, [rax+18h]
0x18000e8ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8b0  mov     ebx, eax
0x18000e8b2  cmp     eax, 80040111h
0x18000e8b7  jnz     short loc_18000E90B
0x18000e8b9  jmp     loc_18000E796
0x18000e8be  cmp     [rcx], r12
0x18000e8c1  jz      loc_18000E7D8
0x18000e8c7  mov     rax, ds:(funcs_18000E8DA - 180596950h)[r11+r10*8]
0x18000e8cb  lea     r8, IID_IUrlHistoryPriv
0x18000e8d2  mov     r9, rdi
0x18000e8d5  xor     edx, edx
0x18000e8d7  mov     rcx, rsi
0x18000e8da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8df  mov     ebx, eax
0x18000e8e1  cmp     ebx, 80040111h
0x18000e8e7  jnz     short loc_18000E90B
0x18000e8e9  lea     r9, IID_IUrlHistoryPriv; riid
0x18000e8f0  mov     [rsp+2F0h+ppv], rdi; ppv
0x18000e8f5  mov     r8d, r13d; dwClsContext
0x18000e8f8  xor     edx, edx; pUnkOuter
0x18000e8fa  mov     rcx, rsi; rclsid
0x18000e8fd  call    cs:__imp_CoCreateInstance
0x18000e904  nop     dword ptr [rax+rax+00h]
0x18000e909  mov     ebx, eax
0x18000e90b  test    ebx, ebx
0x18000e90d  jns     loc_18000E7DD
0x18000e913  mov     edi, r12d
0x18000e916  jmp     loc_18000E6C6
0x18000e91b  lea     r9, [rsp+2F0h+var_278]; struct _HSFINTERVAL **
0x18000e920  mov     r8d, r13d; int
0x18000e923  lea     rdx, [rbp+1F0h+var_258]; struct _FILETIME *
0x18000e927  mov     rcx, r15; this
0x18000e92a  call    ?_GetInterval@CHistFolder@@IEAAJPEBU_FILETIME@@HPEAPEAU_HSFINTERVAL@@@Z; CHistFolder::_GetInterval(_FILETIME const *,int,_HSFINTERVAL * *)
0x18000e92f  test    eax, eax
0x18000e931  jz      loc_18000F115
0x18000e937  lea     rdi, [r15+58h]
0x18000e93b  mov     r14d, r12d
0x18000e93e  mov     [rbp+1F0h+var_238], rdi
0x18000e942  mov     r13, rdi
0x18000e945  mov     rbx, 0C92A69C000h
0x18000e94f  nop
0x18000e950  cmp     r14d, [r15+54h]
0x18000e954  jge     loc_18000EF3C
0x18000e95a  movsxd  rax, r14d
0x18000e95d  lea     r13, [r15+58h]
0x18000e961  imul    r9, rax, 3Ch ; '<'
0x18000e965  add     r9, [r13+0]
0x18000e969  mov     rax, [r9]
0x18000e96c  mov     qword ptr [rsp+2F0h+FileTime1.dwLowDateTime], rax
0x18000e971  cmp     word ptr [r9+3Ah], 1
0x18000e977  jb      loc_18000EAA0
0x18000e97d  mov     ecx, [r9+8]
0x18000e981  mov     eax, [r9+0Ch]
0x18000e985  shl     rax, 20h
0x18000e989  or      rax, rcx
0x18000e98c  mov     ecx, [r9]
0x18000e98f  cqo
0x18000e991  idiv    rbx
0x18000e994  mov     r8, rax
0x18000e997  mov     eax, [r9+4]
0x18000e99b  shl     rax, 20h
0x18000e99f  or      rax, rcx
0x18000e9a2  cqo
0x18000e9a4  idiv    rbx
0x18000e9a7  sub     r8d, eax
0x18000e9aa  cmp     r8d, 1
0x18000e9ae  jnz     loc_18000EAA0
0x18000e9b4  lea     rdx, [rbp+1F0h+FileTime2]; lpFileTime2
0x18000e9b8  lea     rcx, [rsp+2F0h+FileTime1]; lpFileTime1
0x18000e9bd  call    cs:__imp_CompareFileTime
0x18000e9c4  nop     dword ptr [rax+rax+00h]
0x18000e9c9  test    eax, eax
0x18000e9cb  js      loc_18000EAA0
0x18000e9d1  lea     rdx, [rbp+1F0h+var_258]; lpFileTime2
0x18000e9d5  lea     rcx, [rsp+2F0h+FileTime1]; lpFileTime1
0x18000e9da  call    cs:__imp_CompareFileTime
0x18000e9e1  nop     dword ptr [rax+rax+00h]
0x18000e9e6  test    eax, eax
0x18000e9e8  jns     loc_18000EAA0
0x18000e9ee  cmp     [r13+0], r12
0x18000e9f2  jz      loc_18000EAAB
0x18000e9f8  mov     edi, r12d
0x18000e9fb  cmp     edi, [r15+54h]
0x18000e9ff  jge     loc_18000EAA8
0x18000ea05  mov     rbx, [r13+0]
0x18000ea09  movsxd  rax, edi
0x18000ea0c  imul    rsi, rax, 3Ch ; '<'
0x18000ea10  add     rbx, rsi
0x18000ea13  cmp     word ptr [rbx+3Ah], 1
0x18000ea18  jnz     short loc_18000EA32
0x18000ea1a  lea     rdx, [rsp+2F0h+FileTime1]; lpFileTime2
0x18000ea1f  mov     rcx, rbx; lpFileTime1
0x18000ea22  call    cs:__imp_CompareFileTime
0x18000ea29  nop     dword ptr [rax+rax+00h]
0x18000ea2e  test    eax, eax
0x18000ea30  jle     short loc_18000EA40
0x18000ea32  mov     rbx, 0C92A69C000h
0x18000ea3c  inc     edi
0x18000ea3e  jmp     short loc_18000E9FB
0x18000ea40  lea     rdx, [rbx+8]; lpFileTime2
0x18000ea44  lea     rcx, [rsp+2F0h+FileTime1]; lpFileTime1
0x18000ea49  call    cs:__imp_CompareFileTime
0x18000ea50  nop     dword ptr [rax+rax+00h]
0x18000ea55  mov     rbx, 0C92A69C000h
  ... truncated ...
```
