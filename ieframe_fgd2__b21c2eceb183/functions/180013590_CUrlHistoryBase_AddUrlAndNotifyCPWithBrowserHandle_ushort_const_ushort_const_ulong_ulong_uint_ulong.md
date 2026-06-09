# CUrlHistoryBase::AddUrlAndNotifyCPWithBrowserHandle(ushort const *,ushort const *,ulong,ulong,uint *,ulong *)

- ea: `0x180013590`
- end: `0x180014092`
- name: `?AddUrlAndNotifyCPWithBrowserHandle@CUrlHistoryBase@@UEAAJPEBG0KKPEAIPEAK@Z`
- size: `2818`
- prototype: `__int64 __fastcall(CUrlHistoryBase *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18043e600`

## callees

- `0x180011230`
- `0x1800112ac`
- `0x180013590`
- `0x180014098`
- `0x180014660`
- `0x180015440`
- `0x1800231c4`
- `0x180064c38`
- `0x18043ec8c`
- `0x18043f2cc`
- `0x18054e310`
- `0x18054e3d0`
- `0x180550010`

## import_xrefs

- `SHLWAPI!UrlIsNoHistoryW` at `0x180013d4d`
- `SHLWAPI!UrlIsNoHistoryW` at `0x180013d4d`
- `KERNEL32!SystemTimeToFileTime` at `0x18001379a`
- `KERNEL32!SystemTimeToFileTime` at `0x18001379a`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800139cc`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800139cc`
- `KERNEL32!GetLocalTime` at `0x18001378c`
- `KERNEL32!GetLocalTime` at `0x18001378c`
- `KERNEL32!GetCurrentThreadId` at `0x180013db5`
- `KERNEL32!GetCurrentThreadId` at `0x180013db5`
- `KERNEL32!LeaveCriticalSection` at `0x1800136c5`
- `KERNEL32!LeaveCriticalSection` at `0x180013740`
- `KERNEL32!LeaveCriticalSection` at `0x1800136c5`
- `KERNEL32!LeaveCriticalSection` at `0x180013740`
- `KERNEL32!EnterCriticalSection` at `0x180013695`
- `KERNEL32!EnterCriticalSection` at `0x180013716`
- `KERNEL32!EnterCriticalSection` at `0x180013695`
- `KERNEL32!EnterCriticalSection` at `0x180013716`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpIW` at `0x180013d0a`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpIW` at `0x180013d0a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180013e24`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180013ff3`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180013e24`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180013ff3`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180013a71`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180013a83`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180013cf9`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180013ea2`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180013ec1`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180013ee0`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180013f01`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180013f1e`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180013f69`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180013f88`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180013fa7`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180013fcd`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180013a71`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180013a83`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180013cf9`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180013ea2`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180013ec1`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180013ee0`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180013f01`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180013f1e`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180013f69`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180013f88`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180013fa7`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180013fcd`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180013acc`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180013acc`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x180013612`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x180013612`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet@@YAJKK@Z` at `0x180013dc8`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet@@YAJKK@Z` at `0x180013dde`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet@@YAJKK@Z` at `0x180013dc8`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet@@YAJKK@Z` at `0x180013dde`
- `urlmon!CoInternetQueryInfo` at `0x1800138d7`
- `urlmon!CoInternetQueryInfo` at `0x1800138d7`

## pseudocode

```c
__int64 __fastcall CUrlHistoryBase::AddUrlAndNotifyCPWithBrowserHandle(
        CUrlHistoryBase *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        DWORD a5,
        unsigned int *a6,
        unsigned int *a7)
{
  int Instance; // esi
  DWORD CurrentThreadId; // eax
  unsigned __int16 *v13; // rbx
  struct _RTL_CRITICAL_SECTION *v14; // r13
  struct IStream *pstm; // rdi
  __int64 v16; // rcx
  _QWORD *v17; // rax
  __int64 v18; // rbx
  __int64 v19; // rbx
  int v20; // esi
  __int64 v21; // rcx
  _QWORD *v22; // r12
  unsigned int v23; // ebx
  unsigned int v24; // r13d
  char v25; // r12
  const unsigned __int16 *v26; // rdx
  void **v27; // rdx
  const unsigned __int16 *v28; // rcx
  int **v29; // r8
  int v30; // esi
  unsigned int v31; // esi
  int v32; // ecx
  int BrowserProcess; // eax
  int v34; // eax
  int v35; // eax
  int v36; // eax
  int v37; // eax
  unsigned int v38; // ebx
  struct _FILETIME v39; // r15
  struct IHistoryData *v40; // rbx
  int v41; // eax
  int v42; // edx
  __int64 v43; // rax
  void **v44; // rax
  volatile signed __int32 *v45; // rax
  void *v46; // rcx
  _DWORD *v48; // rbx
  int v49; // eax
  int cbBuffer; // [rsp+20h] [rbp-E0h]
  struct IStream *v51; // [rsp+70h] [rbp-90h]
  struct IHistoryData *v52; // [rsp+80h] [rbp-80h] BYREF
  PROPVARIANT v53[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v54; // [rsp+98h] [rbp-68h]
  unsigned int v55; // [rsp+A0h] [rbp-60h] BYREF
  int v56; // [rsp+A4h] [rbp-5Ch]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+A8h] [rbp-58h] BYREF
  int pvBuffer; // [rsp+B0h] [rbp-50h] BYREF
  int v59; // [rsp+B4h] [rbp-4Ch]
  DWORD pcbBuffer; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int v61; // [rsp+BCh] [rbp-44h] BYREF
  unsigned int v62; // [rsp+C4h] [rbp-3Ch]
  LPVOID pv; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int v64; // [rsp+D0h] [rbp-30h] BYREF
  struct _FILETIME v65; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD *v66; // [rsp+E0h] [rbp-20h]
  struct _FILETIME FileTime; // [rsp+E8h] [rbp-18h] BYREF
  PROPVARIANT pvar[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v69; // [rsp+100h] [rbp+0h]
  struct IUnknown *v70; // [rsp+108h] [rbp+8h] BYREF
  unsigned __int16 *v71; // [rsp+110h] [rbp+10h]
  unsigned int *v72; // [rsp+118h] [rbp+18h]
  __int128 v73; // [rsp+120h] [rbp+20h] BYREF
  __int64 v74; // [rsp+130h] [rbp+30h]
  struct _SYSTEMTIME SystemTime; // [rsp+138h] [rbp+38h] BYREF
  unsigned __int16 v76[264]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int16 v77[264]; // [rsp+360h] [rbp+260h] BYREF
  unsigned __int16 v78[264]; // [rsp+570h] [rbp+470h] BYREF
  unsigned __int16 v79[2088]; // [rsp+780h] [rbp+680h] BYREF

  Instance = 0;
  SystemTimeAsFileTime = (struct _FILETIME)this;
  *(_QWORD *)&SystemTime.wYear = a6;
  v72 = a7;
  if ( a6 )
    *a6 = 0;
  CurrentThreadId = a5;
  v61 = 0;
  if ( !a5 )
    CurrentThreadId = GetCurrentThreadId();
  if ( (int)LCIEGetTypedComponentFromThread(0x203u, CurrentThreadId, &v61, 0) >= 0
    && !LCIEIsComponentSharedFlagValueSet(v61, 0x1000000u)
    && !LCIEIsComponentSharedFlagValueSet(v61, 0x400000u) )
  {
    if ( a7 )
      *a7 = 0;
    return (unsigned int)CUrlHistoryBase::_CacheUrlForPrerender(this, a2, a3, a4);
  }
  if ( a2 && *a2 )
  {
    v13 = a3;
    v71 = a3;
    if ( a3 )
    {
      if ( !StrCmpIW(a3, a2) )
        v13 = 0;
      v71 = v13;
    }
    v14 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
    v76[0] = 0;
    v55 = 0;
    v65 = 0;
    pstm = 0;
    FileTime = 0;
    v78[0] = 0;
    v79[0] = 0;
    LOBYTE(v56) = 0;
    v77[0] = 0;
    pvBuffer = 0;
    pcbBuffer = 0;
    v64 = 0;
    v70 = 0;
    v62 = 0;
    pv = 0;
    v52 = 0;
    EnterCriticalSection(v14);
    v17 = (_QWORD *)(*(_QWORD *)&SystemTimeAsFileTime + 72LL);
    v66 = (_QWORD *)(*(_QWORD *)&SystemTimeAsFileTime + 72LL);
    if ( !*(_QWORD *)(*(_QWORD *)&SystemTimeAsFileTime + 72LL) )
    {
      v18 = 0;
      Instance = CHistoryDataFactory_CreateInstance(v16, *(_QWORD *)&SystemTimeAsFileTime + 72LL);
      if ( Instance < 0 )
      {
LABEL_11:
        LeaveCriticalSection(v14);
        if ( Instance >= 0 )
          Instance = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, LPVOID *, struct IHistoryData **))(*(_QWORD *)v18 + 32LL))(
                       v18,
                       a2,
                       &pv,
                       &v52);
        if ( v18 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        if ( Instance >= 0 )
        {
          v20 = 0;
          if ( !a3 )
            (*(void (__fastcall **)(struct IHistoryData *, __int64, unsigned __int16 *, __int64))(*(_QWORD *)v52 + 56LL))(
              v52,
              16,
              v76,
              260);
          v48 = *(_DWORD **)&SystemTime.wYear;
          v54 = 0;
          *(_OWORD *)v53 = 0;
          if ( *(_QWORD *)&SystemTime.wYear
            && (*(int (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(*(_QWORD *)v52 + 24LL))(
                 v52,
                 18,
                 v53) >= 0
            && LOWORD(v53[0]) )
          {
            *v48 = v53[1];
            PropVariantClear(v53);
          }
          if ( (*(int (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(*(_QWORD *)v52 + 24LL))(
                 v52,
                 6,
                 v53) >= 0
            && LOWORD(v53[0]) )
          {
            v62 = (unsigned int)v53[1];
            PropVariantClear(v53);
          }
          if ( (*(int (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(*(_QWORD *)v52 + 24LL))(
                 v52,
                 23,
                 v53) >= 0
            && LOWORD(v53[0]) )
          {
            v23 = (unsigned int)v53[1];
            v55 = (unsigned int)v53[1];
            PropVariantClear(v53);
          }
          else
          {
            v23 = v55;
          }
          if ( (*(int (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(*(_QWORD *)v52 + 24LL))(
                 v52,
                 24,
                 v53) >= 0
            && LOWORD(v53[0]) )
          {
            v65 = (struct _FILETIME)v53[1];
            PropVariantClear(v53);
          }
          if ( (*(int (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(*(_QWORD *)v52 + 24LL))(
                 v52,
                 39,
                 v53) >= 0
            && LOWORD(v53[0]) )
          {
            v24 = (unsigned int)v53[1];
            PropVariantClear(v53);
          }
          else
          {
            v24 = 0;
          }
          if ( (*(int (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(*(_QWORD *)v52 + 24LL))(
                 v52,
                 34,
                 v53) >= 0
            && LOWORD(v53[0]) )
          {
            v49 = (*(__int64 (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(*(_QWORD *)v52 + 24LL))(
                    v52,
                    40,
                    v53);
            v25 = v56;
            if ( v49 >= 0 && !LOWORD(v53[0]) )
              v25 = 1;
            PropVariantClear(v53);
          }
          else
          {
            v25 = v56;
          }
          (*(void (__fastcall **)(struct IHistoryData *, __int64, unsigned __int16 *, __int64))(*(_QWORD *)v52 + 56LL))(
            v52,
            25,
            v78,
            260);
          (*(void (__fastcall **)(struct IHistoryData *, __int64, unsigned __int16 *, __int64))(*(_QWORD *)v52 + 56LL))(
            v52,
            26,
            v79,
            2084);
          (*(void (__fastcall **)(struct IHistoryData *, __int64, unsigned __int16 *, __int64))(*(_QWORD *)v52 + 56LL))(
            v52,
            27,
            v77,
            260);
          if ( (*(int (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(*(_QWORD *)v52 + 24LL))(
                 v52,
                 28,
                 v53) >= 0
            && LOWORD(v53[0]) )
          {
            pcbBuffer = (DWORD)v53[1];
            PropVariantClear(v53);
          }
          if ( (*(int (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(*(_QWORD *)v52 + 24LL))(
                 v52,
                 32,
                 v53) >= 0
            && LOWORD(v53[0]) )
          {
            pvBuffer = (int)v53[1];
            PropVariantClear(v53);
          }
          if ( (*(int (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(*(_QWORD *)v52 + 24LL))(
                 v52,
                 29,
                 v53) >= 0
            && LOWORD(v53[0]) )
          {
            ATL::AtlComPtrAssign(&v70, (struct IUnknown *)v53[1]);
            PropVariantClear(v53);
            pstm = (struct IStream *)v70;
          }
          if ( (*(int (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(*(_QWORD *)v52 + 24LL))(
                 v52,
                 33,
                 v53) >= 0
            && LOWORD(v53[0]) )
          {
            v64 = (unsigned int)v53[1];
            PropVariantClear(v53);
          }
          goto LABEL_24;
        }
        v19 = 0;
        pv = 0;
        v20 = 0;
        v52 = 0;
        EnterCriticalSection(v14);
        v22 = v66;
        if ( !*v66 )
        {
          v20 = CHistoryDataFactory_CreateInstance(v21, v66);
          if ( v20 < 0 )
            goto LABEL_18;
          if ( (unsigned __int8)IEConfiguration_GetBool(536870913) )
            (*(void (__fastcall **)(struct _FILETIME))(**(_QWORD **)&SystemTimeAsFileTime + 176LL))(SystemTimeAsFileTime);
        }
        v19 = *v22;
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v22 + 8LL))(*v22);
LABEL_18:
        LeaveCriticalSection(v14);
        if ( v20 >= 0 )
          v20 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, LPVOID *, struct IHistoryData **))(*(_QWORD *)v19 + 24LL))(
                  v19,
                  a2,
                  &pv,
                  &v52);
        if ( v19 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        if ( v20 < 0 )
          goto LABEL_58;
        v23 = v55;
        v24 = 0;
        v25 = v56;
LABEL_24:
        if ( v71 )
          StringCchCopyW(v76, 0x104u, v71);
        SystemTime = 0;
        GetLocalTime(&SystemTime);
        if ( SystemTimeToFileTime(&SystemTime, &FileTime) && !v23 )
          v65 = FileTime;
        if ( (int)CUrlHistoryBase::_UpdateHistoryData(
                    (CUrlHistoryBase *)&v55,
                    v26,
                    v76,
                    v52,
                    (const unsigned __int16 *)pv,
                    &v55,
                    &v65,
                    v78,
                    v79,
                    v77,
                    &pvBuffer,
                    &pcbBuffer,
                    &v64,
                    pstm,
                    v51) < 0 )
          goto LABEL_54;
        v54 = 0;
        *(_OWORD *)v53 = 0;
        v30 = 0;
        if ( (*(int (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(*(_QWORD *)v52 + 24LL))(v52, 9, v53) >= 0
          && LOWORD(v53[0]) )
        {
          v30 = (int)v53[1];
        }
        if ( (a4 & 4) != 0 )
        {
          v31 = v30 | 0x10000000;
        }
        else if ( (a4 & 1) == 0 || UrlIsNoHistoryW(a2) )
        {
          v31 = v30 & 0xEFFFFFFF;
        }
        else
        {
          v31 = v30 | 0x10000000;
        }
        v32 = a4 | 4;
        if ( (v31 & 0x10000000) == 0 )
          v32 = a4;
        a4 = v32;
        BrowserProcess = GetBrowserProcess();
        if ( ((BrowserProcess - 15) & 0xFFFFFFF6) == 0 && BrowserProcess != 24 )
        {
          v34 = GetUrlSchemeW(a2) - 4;
          if ( !v34 )
            goto LABEL_43;
          v35 = v34 - 11;
          if ( !v35 )
            goto LABEL_43;
          v36 = v35 - 1;
          if ( !v36 )
            goto LABEL_43;
          v37 = v36 - 1;
          if ( !v37 )
          {
LABEL_42:
            v31 &= ~0x10000000u;
            goto LABEL_43;
          }
          if ( v37 == 1 )
          {
LABEL_43:
            v38 = v31 & 0xFFFFFFFE;
            if ( (v31 & 1) == 0 )
              v38 = v31;
            if ( (a4 & 8) != 0 || (v38 & 0x10000000) == 0 )
            {
              v39 = SystemTimeAsFileTime;
            }
            else
            {
              v69 = 0;
              *(_OWORD *)pvar = 0;
              LODWORD(pvar[1]) = v62 + 1;
              LOWORD(pvar[0]) = 19;
              (*(void (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(*(_QWORD *)v52 + 32LL))(
                v52,
                6,
                pvar);
              v39 = SystemTimeAsFileTime;
              LOBYTE(cbBuffer) = v25;
              (*(void (__fastcall **)(struct _FILETIME, _QWORD, _QWORD, _QWORD, int, struct IHistoryData *, struct _FILETIME *, struct _FILETIME *))(**(_QWORD **)&SystemTimeAsFileTime + 216LL))(
                SystemTimeAsFileTime,
                a4,
                v55,
                v24,
                cbBuffer,
                v52,
                &v65,
                &FileTime);
            }
            v73 = 0;
            v74 = 0;
            LOWORD(v73) = 19;
            DWORD2(v73) = v38;
            (*(void (__fastcall **)(struct IHistoryData *, __int64, __int128 *))(*(_QWORD *)v52 + 32LL))(v52, 9, &v73);
            v40 = v52;
            if ( !CUrlHistoryBase::s_dwDaysToKeep )
              CUrlHistoryBase::s_dwDaysToKeep = CUrlHistoryBase::s_GetDaysToKeep();
            SystemTimeAsFileTime = 0;
            GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
            (*(void (__fastcall **)(struct IHistoryData *, struct _FILETIME *))(*(_QWORD *)v40 + 104LL))(
              v40,
              &SystemTimeAsFileTime);
            *(_OWORD *)pvar = 0;
            v41 = 864000000000LL * (CUrlHistoryBase::s_dwDaysToKeep + 6) / 0xFFFFFFFFLL;
            v42 = v41 + 711573504 * (CUrlHistoryBase::s_dwDaysToKeep + 6) + SystemTimeAsFileTime.dwLowDateTime;
            v59 = SystemTimeAsFileTime.dwHighDateTime + v41;
            v69 = 0;
            v43 = *(_QWORD *)v40;
            pvBuffer = v42;
            if ( (*(int (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(v43 + 24))(v40, 14, pvar) >= 0
              && LOWORD(pvar[0]) )
            {
              pvBuffer = -1;
              v59 = 0x7FFFFFFF;
            }
            (*(void (__fastcall **)(struct IHistoryData *, int *))(*(_QWORD *)v40 + 120LL))(v40, &pvBuffer);
            v20 = (*(__int64 (__fastcall **)(struct IHistoryData *))(*(_QWORD *)v40 + 144LL))(v40);
            PropVariantClear(pvar);
            if ( v20 >= 0 )
              (*(void (__fastcall **)(struct _FILETIME, struct IHistoryData *, _QWORD))(**(_QWORD **)&v39 + 224LL))(
                v39,
                v52,
                v62);
            PropVariantClear(v53);
LABEL_54:
            if ( !g_fGCountRundown
              && ((v44 = g_prgSessionWide) != 0
               || (OpenGlobalCounterFileMappingAndMapMemory(v28, v27, v29), (v44 = g_prgSessionWide) != 0))
              && (v45 = (volatile signed __int32 *)v44 + 11) != 0 )
            {
              _InterlockedIncrement(v45);
            }
            else
            {
              _InterlockedIncrement(&g_cUniqueCounterValue);
            }
LABEL_58:
            if ( v72 )
              *v72 = a4;
            v46 = pv;
            pv = 0;
            CoTaskMemFree(v46);
            if ( pstm )
              (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)pstm + 16LL))(pstm);
            if ( v52 )
              (*(void (__fastcall **)(struct IHistoryData *))(*(_QWORD *)v52 + 16LL))(v52);
            return (unsigned int)v20;
          }
        }
        pvBuffer = 0;
        pcbBuffer = 0;
        if ( CoInternetQueryInfo(a2, QUERY_USES_HISTORYFOLDER, 0, &pvBuffer, 4u, &pcbBuffer, 0) < 0 || pvBuffer )
          goto LABEL_43;
        goto LABEL_42;
      }
      if ( (unsigned __int8)IEConfiguration_GetBool(536870913) )
        (*(void (__fastcall **)(struct _FILETIME))(**(_QWORD **)&SystemTimeAsFileTime + 176LL))(SystemTimeAsFileTime);
      v17 = v66;
    }
    v18 = *v17;
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v17 + 8LL))(*v17);
    goto LABEL_11;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180013590  push    rbp
0x180013592  push    rbx
0x180013593  push    rsi
0x180013594  push    r12
0x180013596  push    r13
0x180013598  push    r14
0x18001359a  push    r15
0x18001359c  lea     rbp, [rsp-16F0h]
0x1800135a4  mov     eax, 17F0h
0x1800135a9  call    _alloca_probe
0x1800135ae  sub     rsp, rax
0x1800135b1  mov     rax, cs:__security_cookie
0x1800135b8  xor     rax, rsp
0x1800135bb  mov     [rbp+1720h+var_50], rax
0x1800135c2  mov     rax, [rbp+1720h+arg_28]
0x1800135c9  xor     esi, esi
0x1800135cb  mov     rbx, [rbp+1720h+arg_30]
0x1800135d2  mov     r14d, r9d
0x1800135d5  mov     qword ptr [rbp+1720h+SystemTimeAsFileTime.dwLowDateTime], rcx
0x1800135d9  mov     r12, r8
0x1800135dc  mov     qword ptr [rbp+1720h+SystemTime.wYear], rax
0x1800135e0  mov     r15, rdx
0x1800135e3  mov     [rbp+1720h+var_1708], rbx
0x1800135e7  mov     r13, rcx
0x1800135ea  test    rax, rax
0x1800135ed  jnz     loc_180013DAE
0x1800135f3  mov     eax, [rbp+1720h+arg_20]
0x1800135f9  mov     [rbp+1720h+var_1764], esi
0x1800135fc  test    eax, eax
0x1800135fe  jz      loc_180013DB5
0x180013604  xor     r9d, r9d
0x180013607  lea     r8, [rbp+1720h+var_1764]
0x18001360b  mov     edx, eax
0x18001360d  mov     ecx, 203h
0x180013612  call    cs:__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z; LCIEGetTypedComponentFromThread(ulong,ulong,ulong *,_IsoComponent * *)
0x180013618  test    eax, eax
0x18001361a  jns     loc_180013DC0
0x180013620  test    r15, r15
0x180013623  jz      loc_180014088
0x180013629  cmp     [r15], si
0x18001362d  jz      loc_180014088
0x180013633  mov     [rsp+1820h+var_38], rdi
0x18001363b  mov     rbx, r12
0x18001363e  mov     [rbp+1720h+var_1710], rbx
0x180013642  test    r12, r12
0x180013645  jnz     loc_180013D04
0x18001364b  add     r13, 20h ; ' '
0x18001364f  mov     [rbp+1720h+var_16D0], si
0x180013653  mov     rcx, r13; lpCriticalSection
0x180013656  mov     [rbp+1720h+var_1780], esi
0x180013659  mov     qword ptr [rbp+1720h+var_1748.dwLowDateTime], rsi
0x18001365d  mov     rdi, rsi
0x180013660  mov     qword ptr [rbp+1720h+FileTime.dwLowDateTime], rsi
0x180013664  mov     [rbp+1720h+var_12B0], si
0x18001366b  mov     [rbp+1720h+var_10A0], si
0x180013672  mov     byte ptr [rbp+1720h+var_177C], sil
0x180013676  mov     [rbp+1720h+var_14C0], si
0x18001367d  mov     [rbp+1720h+pvBuffer], esi
0x180013680  mov     [rbp+1720h+var_1768], esi
0x180013683  mov     [rbp+1720h+var_1750], esi
0x180013686  mov     [rbp+1720h+var_1718], rsi
0x18001368a  mov     [rbp+1720h+var_175C], esi
0x18001368d  mov     [rbp+1720h+pv], rsi
0x180013691  mov     [rbp+1720h+var_17A0], rsi
0x180013695  call    cs:__imp_EnterCriticalSection
0x18001369b  mov     rax, qword ptr [rbp+1720h+SystemTimeAsFileTime.dwLowDateTime]
0x18001369f  add     rax, 48h ; 'H'
0x1800136a3  mov     [rbp+1720h+var_1740], rax
0x1800136a7  cmp     [rax], rsi
0x1800136aa  jz      loc_180013E0B
0x1800136b0  mov     rbx, [rax]
0x1800136b3  mov     rcx, rbx
0x1800136b6  mov     rax, [rbx]
0x1800136b9  mov     rax, [rax+8]
0x1800136bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800136c2  mov     rcx, r13; lpCriticalSection
0x1800136c5  call    cs:__imp_LeaveCriticalSection
0x1800136cb  test    esi, esi
0x1800136cd  js      short loc_1800136EB
0x1800136cf  mov     rax, [rbx]
0x1800136d2  lea     r9, [rbp+1720h+var_17A0]
0x1800136d6  lea     r8, [rbp+1720h+pv]
0x1800136da  mov     rdx, r15
0x1800136dd  mov     rcx, rbx
0x1800136e0  mov     rax, [rax+20h]
0x1800136e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800136e9  mov     esi, eax
0x1800136eb  test    rbx, rbx
0x1800136ee  jz      short loc_1800136FF
0x1800136f0  mov     rax, [rbx]
0x1800136f3  mov     rcx, rbx
0x1800136f6  mov     rax, [rax+10h]
0x1800136fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800136ff  test    esi, esi
0x180013701  jns     loc_180013B27
0x180013707  xor     ebx, ebx
0x180013709  mov     rcx, r13; lpCriticalSection
0x18001370c  mov     [rbp+1720h+pv], rbx
0x180013710  mov     esi, ebx
0x180013712  mov     [rbp+1720h+var_17A0], rbx
0x180013716  call    cs:__imp_EnterCriticalSection
0x18001371c  mov     r12, [rbp+1720h+var_1740]
0x180013720  cmp     [r12], rbx
0x180013724  jz      loc_180013FDC
0x18001372a  mov     rbx, [r12]
0x18001372e  mov     rcx, rbx
0x180013731  mov     rax, [rbx]
0x180013734  mov     rax, [rax+8]
0x180013738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001373d  mov     rcx, r13; lpCriticalSection
0x180013740  call    cs:__imp_LeaveCriticalSection
0x180013746  test    esi, esi
0x180013748  jns     loc_180014019
0x18001374e  test    rbx, rbx
0x180013751  jz      short loc_180013762
0x180013753  mov     rax, [rbx]
0x180013756  mov     rcx, rbx
0x180013759  mov     rax, [rax+10h]
0x18001375d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013762  test    esi, esi
0x180013764  js      loc_180013AB3
0x18001376a  mov     ebx, [rbp+1720h+var_1780]
0x18001376d  mov     r13d, edi
0x180013770  mov     r12d, [rbp+1720h+var_177C]
0x180013774  mov     r8, [rbp+1720h+var_1710]; unsigned __int16 *
0x180013778  test    r8, r8
0x18001377b  jnz     loc_18001403A
0x180013781  xorps   xmm0, xmm0
0x180013784  lea     rcx, [rbp+1720h+SystemTime]; lpSystemTime
0x180013788  movups  xmmword ptr [rbp+1720h+SystemTime.wYear], xmm0
0x18001378c  call    cs:__imp_GetLocalTime
0x180013792  lea     rdx, [rbp+1720h+FileTime]; lpFileTime
0x180013796  lea     rcx, [rbp+1720h+SystemTime]; lpSystemTime
0x18001379a  call    cs:__imp_SystemTimeToFileTime
0x1800137a0  test    eax, eax
0x1800137a2  jnz     loc_180013D64
0x1800137a8  mov     rax, [rbp+1720h+pv]
0x1800137ac  lea     rcx, [rbp+1720h+var_1750]
0x1800137b0  mov     r9, [rbp+1720h+var_17A0]; struct IHistoryData *
0x1800137b4  lea     r8, [rbp+1720h+var_16D0]; unsigned __int16 *
0x1800137b8  mov     [rsp+1820h+pstm], rdi; pstm
0x1800137bd  mov     [rsp+1820h+var_17C0], rcx; unsigned int *
0x1800137c2  lea     rcx, [rbp+1720h+var_1768]
0x1800137c6  mov     [rsp+1820h+var_17C8], rcx; unsigned int *
0x1800137cb  lea     rcx, [rbp+1720h+pvBuffer]
0x1800137cf  mov     [rsp+1820h+var_17D0], rcx; int *
0x1800137d4  lea     rcx, [rbp+1720h+var_14C0]
0x1800137db  mov     [rsp+1820h+var_17D8], rcx; unsigned __int16 *
0x1800137e0  lea     rcx, [rbp+1720h+var_10A0]
0x1800137e7  mov     [rsp+1820h+var_17E0], rcx; unsigned __int16 *
0x1800137ec  lea     rcx, [rbp+1720h+var_12B0]
0x1800137f3  mov     [rsp+1820h+var_17E8], rcx; unsigned __int16 *
0x1800137f8  lea     rcx, [rbp+1720h+var_1748]
0x1800137fc  mov     qword ptr [rsp+1820h+dwReserved], rcx; struct _FILETIME *
0x180013801  lea     rcx, [rbp+1720h+var_1780]; this
0x180013805  mov     [rsp+1820h+pcbBuffer], rcx; unsigned int *
0x18001380a  mov     qword ptr [rsp+1820h+cbBuffer], rax; unsigned __int16 *
0x18001380f  call    ?_UpdateHistoryData@CUrlHistoryBase@@IEAAJPEBG0PEAUIHistoryData@@0PEAIPEAU_FILETIME@@000PEAJPEAK5PEAUIStream@@6@Z; CUrlHistoryBase::_UpdateHistoryData(ushort const *,ushort const *,IHistoryData *,ushort const *,uint *,_FILETIME *,ushort const *,ushort const *,ushort const *,long *,ulong *,ulong *,IStream *,IStream *)
0x180013814  test    eax, eax
0x180013816  js      loc_180013A89
0x18001381c  mov     rcx, [rbp+1720h+var_17A0]
0x180013820  lea     r8, [rbp+1720h+var_1798]
0x180013824  xor     eax, eax
0x180013826  xorps   xmm0, xmm0
0x180013829  mov     [rbp+1720h+var_1788], rax
0x18001382d  mov     edx, 9
0x180013832  movups  xmmword ptr [rbp+1720h+var_1798], xmm0
0x180013836  mov     rax, [rcx]
0x180013839  xor     esi, esi
0x18001383b  mov     rax, [rax+18h]
0x18001383f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013844  test    eax, eax
0x180013846  jns     loc_180013D79
0x18001384c  test    r14b, 4
0x180013850  jz      loc_180013D40
0x180013856  bts     esi, 1Ch
0x18001385a  mov     ecx, r14d
0x18001385d  or      ecx, 4
0x180013860  bt      esi, 1Ch
0x180013864  cmovnb  ecx, r14d
0x180013868  mov     r14d, ecx
0x18001386b  call    GetBrowserProcess
0x180013870  lea     ecx, [rax-0Fh]
0x180013873  test    ecx, 0FFFFFFF6h
0x180013879  jnz     short loc_1800138A1
0x18001387b  cmp     eax, 18h
0x18001387e  jz      short loc_1800138A1
0x180013880  mov     rcx, r15
0x180013883  call    GetUrlSchemeW
0x180013888  sub     eax, 4
0x18001388b  jz      short loc_1800138EB
0x18001388d  sub     eax, 0Bh
0x180013890  jz      short loc_1800138EB
0x180013892  sub     eax, 1
0x180013895  jz      short loc_1800138EB
0x180013897  sub     eax, 1
0x18001389a  jz      short loc_1800138E7
0x18001389c  cmp     eax, 1
0x18001389f  jz      short loc_1800138EB
0x1800138a1  lea     rax, [rbp+1720h+var_1768]
0x1800138a5  mov     [rsp+1820h+dwReserved], 0; dwReserved
0x1800138ad  mov     [rsp+1820h+pcbBuffer], rax; pcbBuffer
0x1800138b2  lea     r9, [rbp+1720h+pvBuffer]; pvBuffer
0x1800138b6  xor     r8d, r8d; dwQueryFlags
0x1800138b9  mov     [rsp+1820h+cbBuffer], 4; cbBuffer
0x1800138c1  mov     edx, 0Fh; QueryOptions
0x1800138c6  mov     [rbp+1720h+pvBuffer], 0
0x1800138cd  mov     rcx, r15; pwzUrl
0x1800138d0  mov     [rbp+1720h+var_1768], 0
0x1800138d7  call    cs:__imp_CoInternetQueryInfo
0x1800138dd  test    eax, eax
0x1800138df  js      short loc_1800138EB
0x1800138e1  cmp     [rbp+1720h+pvBuffer], 0
0x1800138e5  jnz     short loc_1800138EB
0x1800138e7  btr     esi, 1Ch
0x1800138eb  mov     ebx, esi
0x1800138ed  and     ebx, 0FFFFFFFEh
0x1800138f0  test    sil, 1
0x1800138f4  cmovz   ebx, esi
0x1800138f7  mov     esi, 13h
0x1800138fc  test    r14b, 8
0x180013900  jnz     loc_180013DA5
0x180013906  bt      ebx, 1Ch
0x18001390a  jnb     loc_180013DA5
0x180013910  mov     rcx, [rbp+1720h+var_17A0]
0x180013914  lea     r8, [rbp+1720h+pvar]
0x180013918  xor     eax, eax
0x18001391a  xorps   xmm0, xmm0
0x18001391d  mov     [rbp+1720h+var_1720], rax
0x180013921  mov     edx, 6
0x180013926  mov     eax, [rbp+1720h+var_175C]
0x180013929  inc     eax
0x18001392b  movups  xmmword ptr [rbp+1720h+pvar], xmm0
0x18001392f  mov     dword ptr [rbp+1720h+pvar+8], eax
0x180013932  mov     word ptr [rbp+1720h+pvar], si
0x180013936  mov     rax, [rcx]
0x180013939  mov     rax, [rax+20h]
0x18001393d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013942  mov     r15, qword ptr [rbp+1720h+SystemTimeAsFileTime.dwLowDateTime]
0x180013946  lea     rcx, [rbp+1720h+FileTime]
0x18001394a  mov     r8d, [rbp+1720h+var_1780]
0x18001394e  mov     r9d, r13d
0x180013951  mov     [rsp+1820h+var_17E8], rcx
0x180013956  mov     edx, r14d
0x180013959  lea     rcx, [rbp+1720h+var_1748]
0x18001395d  mov     rax, [r15]
0x180013960  mov     qword ptr [rsp+1820h+dwReserved], rcx
0x180013965  mov     rcx, [rbp+1720h+var_17A0]
0x180013969  mov     [rsp+1820h+pcbBuffer], rcx
0x18001396e  mov     rcx, r15
0x180013971  mov     rax, [rax+0D8h]
0x180013978  mov     byte ptr [rsp+1820h+cbBuffer], r12b
0x18001397d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013982  mov     rcx, [rbp+1720h+var_17A0]
0x180013986  lea     r8, [rbp+1720h+var_1700]
0x18001398a  xor     eax, eax
0x18001398c  xorps   xmm0, xmm0
0x18001398f  movups  [rbp+1720h+var_1700], xmm0
0x180013993  mov     [rbp+1720h+var_16F0], rax
0x180013997  mov     edx, 9
0x18001399c  mov     word ptr [rbp+1720h+var_1700], si
0x1800139a0  mov     dword ptr [rbp+1720h+var_1700+8], ebx
0x1800139a3  mov     rax, [rcx]
0x1800139a6  mov     rax, [rax+20h]
0x1800139aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139af  cmp     cs:?s_dwDaysToKeep@CUrlHistoryBase@@0KA, 0; ulong CUrlHistoryBase::s_dwDaysToKeep
0x1800139b6  mov     rbx, [rbp+1720h+var_17A0]
0x1800139ba  jz      loc_180014056
0x1800139c0  lea     rcx, [rbp+1720h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800139c4  mov     qword ptr [rbp+1720h+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800139cc  call    cs:__imp_GetSystemTimeAsFileTime
0x1800139d2  mov     rax, [rbx]
0x1800139d5  lea     rdx, [rbp+1720h+SystemTimeAsFileTime]
0x1800139d9  mov     rcx, rbx
0x1800139dc  mov     rax, [rax+68h]
0x1800139e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139e5  mov     eax, cs:?s_dwDaysToKeep@CUrlHistoryBase@@0KA; ulong CUrlHistoryBase::s_dwDaysToKeep
0x1800139eb  mov     esi, 0FFFFFFFFh
0x1800139f0  add     eax, 6
0x1800139f3  xorps   xmm0, xmm0
0x1800139f6  imul    eax, 15180h
0x1800139fc  mov     rcx, rbx
0x1800139ff  movups  xmmword ptr [rbp+1720h+pvar], xmm0
0x180013a03  imul    r8, rax, 989680h
0x180013a0a  mov     rax, r8
0x180013a0d  cqo
0x180013a0f  idiv    rsi
0x180013a12  mov     edx, [rbp+1720h+SystemTimeAsFileTime.dwLowDateTime]
0x180013a15  add     edx, r8d
0x180013a18  lea     r8, [rbp+1720h+pvar]
0x180013a1c  add     edx, eax
0x180013a1e  add     eax, [rbp+1720h+SystemTimeAsFileTime.dwHighDateTime]
0x180013a21  mov     [rbp+1720h+var_176C], eax
0x180013a24  xor     eax, eax
0x180013a26  mov     [rbp+1720h+var_1720], rax
0x180013a2a  mov     rax, [rbx]
0x180013a2d  mov     [rbp+1720h+pvBuffer], edx
0x180013a30  mov     edx, 0Eh
0x180013a35  mov     rax, [rax+18h]
0x180013a39  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
