# CUrlHistoryBase::AddUrlAndNotifyCPWithBrowserHandle(ushort const *,ushort const *,ulong,ulong,uint *,ulong *)

- ea: `0x180016710`
- end: `0x1800172c1`
- name: `?AddUrlAndNotifyCPWithBrowserHandle@CUrlHistoryBase@@UEAAJPEBG0KKPEAIPEAK@Z`
- size: `2993`
- prototype: `__int64 __fastcall(CUrlHistoryBase *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180478fa0`

## callees

- `0x1800144d0`
- `0x180014550`
- `0x180016710`
- `0x1800172c8`
- `0x1800178b0`
- `0x1800187f0`
- `0x180024b74`
- `0x180069118`
- `0x18047968c`
- `0x180479d38`
- `0x180591f80`
- `0x180592040`
- `0x180594010`

## import_xrefs

- `SHLWAPI!UrlIsNoHistoryW` at `0x180016f22`
- `SHLWAPI!UrlIsNoHistoryW` at `0x180016f22`
- `KERNEL32!SystemTimeToFileTime` at `0x18001693e`
- `KERNEL32!SystemTimeToFileTime` at `0x18001693e`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180016b7c`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180016b7c`
- `KERNEL32!GetLocalTime` at `0x18001692a`
- `KERNEL32!GetLocalTime` at `0x18001692a`
- `KERNEL32!GetCurrentThreadId` at `0x180016f90`
- `KERNEL32!GetCurrentThreadId` at `0x180016f90`
- `KERNEL32!LeaveCriticalSection` at `0x180016851`
- `KERNEL32!LeaveCriticalSection` at `0x1800168d8`
- `KERNEL32!LeaveCriticalSection` at `0x180016851`
- `KERNEL32!LeaveCriticalSection` at `0x1800168d8`
- `KERNEL32!EnterCriticalSection` at `0x18001681b`
- `KERNEL32!EnterCriticalSection` at `0x1800168a8`
- `KERNEL32!EnterCriticalSection` at `0x18001681b`
- `KERNEL32!EnterCriticalSection` at `0x1800168a8`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpIW` at `0x180016ed9`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpIW` at `0x180016ed9`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180017011`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18001721c`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180017011`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18001721c`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180016c27`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180016c3f`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180016ec2`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180017095`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x1800170ba`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x1800170df`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180017106`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180017129`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x18001717a`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x18001719f`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x1800171c4`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x1800171f0`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180016c27`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180016c3f`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180016ec2`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180017095`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x1800170ba`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x1800170df`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180017106`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180017129`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x18001717a`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x18001719f`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x1800171c4`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x1800171f0`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180016c8e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180016c8e`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x180016792`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x180016792`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet@@YAJKK@Z` at `0x180016fa9`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet@@YAJKK@Z` at `0x180016fc5`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet@@YAJKK@Z` at `0x180016fa9`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet@@YAJKK@Z` at `0x180016fc5`
- `urlmon!CoInternetQueryInfo` at `0x180016a81`
- `urlmon!CoInternetQueryInfo` at `0x180016a81`

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
0x180016710  push    rbp
0x180016712  push    rbx
0x180016713  push    rsi
0x180016714  push    r12
0x180016716  push    r13
0x180016718  push    r14
0x18001671a  push    r15
0x18001671c  lea     rbp, [rsp-16F0h]
0x180016724  mov     eax, 17F0h
0x180016729  call    _alloca_probe
0x18001672e  sub     rsp, rax
0x180016731  mov     rax, cs:__security_cookie
0x180016738  xor     rax, rsp
0x18001673b  mov     [rbp+1720h+var_50], rax
0x180016742  mov     rax, [rbp+1720h+arg_28]
0x180016749  xor     esi, esi
0x18001674b  mov     rbx, [rbp+1720h+arg_30]
0x180016752  mov     r14d, r9d
0x180016755  mov     qword ptr [rbp+1720h+SystemTimeAsFileTime.dwLowDateTime], rcx
0x180016759  mov     r12, r8
0x18001675c  mov     qword ptr [rbp+1720h+SystemTime.wYear], rax
0x180016760  mov     r15, rdx
0x180016763  mov     [rbp+1720h+var_1708], rbx
0x180016767  mov     r13, rcx
0x18001676a  test    rax, rax
0x18001676d  jnz     loc_180016F89
0x180016773  mov     eax, [rbp+1720h+arg_20]
0x180016779  mov     [rbp+1720h+var_1764], esi
0x18001677c  test    eax, eax
0x18001677e  jz      loc_180016F90
0x180016784  xor     r9d, r9d
0x180016787  lea     r8, [rbp+1720h+var_1764]
0x18001678b  mov     edx, eax
0x18001678d  mov     ecx, 203h
0x180016792  call    cs:__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z; LCIEGetTypedComponentFromThread(ulong,ulong,ulong *,_IsoComponent * *)
0x180016799  nop     dword ptr [rax+rax+00h]
0x18001679e  test    eax, eax
0x1800167a0  jns     loc_180016FA1
0x1800167a6  test    r15, r15
0x1800167a9  jz      loc_1800172B7
0x1800167af  cmp     [r15], si
0x1800167b3  jz      loc_1800172B7
0x1800167b9  mov     [rsp+1820h+var_38], rdi
0x1800167c1  mov     rbx, r12
0x1800167c4  mov     [rbp+1720h+var_1710], rbx
0x1800167c8  test    r12, r12
0x1800167cb  jnz     loc_180016ED3
0x1800167d1  add     r13, 20h ; ' '
0x1800167d5  mov     [rbp+1720h+var_16D0], si
0x1800167d9  mov     rcx, r13; lpCriticalSection
0x1800167dc  mov     [rbp+1720h+var_1780], esi
0x1800167df  mov     qword ptr [rbp+1720h+var_1748.dwLowDateTime], rsi
0x1800167e3  mov     rdi, rsi
0x1800167e6  mov     qword ptr [rbp+1720h+FileTime.dwLowDateTime], rsi
0x1800167ea  mov     [rbp+1720h+var_12B0], si
0x1800167f1  mov     [rbp+1720h+var_10A0], si
0x1800167f8  mov     byte ptr [rbp+1720h+var_177C], sil
0x1800167fc  mov     [rbp+1720h+var_14C0], si
0x180016803  mov     [rbp+1720h+pvBuffer], esi
0x180016806  mov     [rbp+1720h+var_1768], esi
0x180016809  mov     [rbp+1720h+var_1750], esi
0x18001680c  mov     [rbp+1720h+var_1718], rsi
0x180016810  mov     [rbp+1720h+var_175C], esi
0x180016813  mov     [rbp+1720h+pv], rsi
0x180016817  mov     [rbp+1720h+var_17A0], rsi
0x18001681b  call    cs:__imp_EnterCriticalSection
0x180016822  nop     dword ptr [rax+rax+00h]
0x180016827  mov     rax, qword ptr [rbp+1720h+SystemTimeAsFileTime.dwLowDateTime]
0x18001682b  add     rax, 48h ; 'H'
0x18001682f  mov     [rbp+1720h+var_1740], rax
0x180016833  cmp     [rax], rsi
0x180016836  jz      loc_180016FF8
0x18001683c  mov     rbx, [rax]
0x18001683f  mov     rcx, rbx
0x180016842  mov     rax, [rbx]
0x180016845  mov     rax, [rax+8]
0x180016849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001684e  mov     rcx, r13; lpCriticalSection
0x180016851  call    cs:__imp_LeaveCriticalSection
0x180016858  nop     dword ptr [rax+rax+00h]
0x18001685d  test    esi, esi
0x18001685f  js      short loc_18001687D
0x180016861  mov     rax, [rbx]
0x180016864  lea     r9, [rbp+1720h+var_17A0]
0x180016868  lea     r8, [rbp+1720h+pv]
0x18001686c  mov     rdx, r15
0x18001686f  mov     rcx, rbx
0x180016872  mov     rax, [rax+20h]
0x180016876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001687b  mov     esi, eax
0x18001687d  test    rbx, rbx
0x180016880  jz      short loc_180016891
0x180016882  mov     rax, [rbx]
0x180016885  mov     rcx, rbx
0x180016888  mov     rax, [rax+10h]
0x18001688c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016891  test    esi, esi
0x180016893  jns     loc_180016CF0
0x180016899  xor     ebx, ebx
0x18001689b  mov     rcx, r13; lpCriticalSection
0x18001689e  mov     [rbp+1720h+pv], rbx
0x1800168a2  mov     esi, ebx
0x1800168a4  mov     [rbp+1720h+var_17A0], rbx
0x1800168a8  call    cs:__imp_EnterCriticalSection
0x1800168af  nop     dword ptr [rax+rax+00h]
0x1800168b4  mov     r12, [rbp+1720h+var_1740]
0x1800168b8  cmp     [r12], rbx
0x1800168bc  jz      loc_180017205
0x1800168c2  mov     rbx, [r12]
0x1800168c6  mov     rcx, rbx
0x1800168c9  mov     rax, [rbx]
0x1800168cc  mov     rax, [rax+8]
0x1800168d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168d5  mov     rcx, r13; lpCriticalSection
0x1800168d8  call    cs:__imp_LeaveCriticalSection
0x1800168df  nop     dword ptr [rax+rax+00h]
0x1800168e4  test    esi, esi
0x1800168e6  jns     loc_180017248
0x1800168ec  test    rbx, rbx
0x1800168ef  jz      short loc_180016900
0x1800168f1  mov     rax, [rbx]
0x1800168f4  mov     rcx, rbx
0x1800168f7  mov     rax, [rax+10h]
0x1800168fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016900  test    esi, esi
0x180016902  js      loc_180016C75
0x180016908  mov     ebx, [rbp+1720h+var_1780]
0x18001690b  mov     r13d, edi
0x18001690e  mov     r12d, [rbp+1720h+var_177C]
0x180016912  mov     r8, [rbp+1720h+var_1710]; unsigned __int16 *
0x180016916  test    r8, r8
0x180016919  jnz     loc_180017269
0x18001691f  xorps   xmm0, xmm0
0x180016922  lea     rcx, [rbp+1720h+SystemTime]; lpSystemTime
0x180016926  movups  xmmword ptr [rbp+1720h+SystemTime.wYear], xmm0
0x18001692a  call    cs:__imp_GetLocalTime
0x180016931  nop     dword ptr [rax+rax+00h]
0x180016936  lea     rdx, [rbp+1720h+FileTime]; lpFileTime
0x18001693a  lea     rcx, [rbp+1720h+SystemTime]; lpSystemTime
0x18001693e  call    cs:__imp_SystemTimeToFileTime
0x180016945  nop     dword ptr [rax+rax+00h]
0x18001694a  test    eax, eax
0x18001694c  jnz     loc_180016F3F
0x180016952  mov     rax, [rbp+1720h+pv]
0x180016956  lea     rcx, [rbp+1720h+var_1750]
0x18001695a  mov     r9, [rbp+1720h+var_17A0]; struct IHistoryData *
0x18001695e  lea     r8, [rbp+1720h+var_16D0]; unsigned __int16 *
0x180016962  mov     [rsp+1820h+pstm], rdi; pstm
0x180016967  mov     [rsp+1820h+var_17C0], rcx; unsigned int *
0x18001696c  lea     rcx, [rbp+1720h+var_1768]
0x180016970  mov     [rsp+1820h+var_17C8], rcx; unsigned int *
0x180016975  lea     rcx, [rbp+1720h+pvBuffer]
0x180016979  mov     [rsp+1820h+var_17D0], rcx; int *
0x18001697e  lea     rcx, [rbp+1720h+var_14C0]
0x180016985  mov     [rsp+1820h+var_17D8], rcx; unsigned __int16 *
0x18001698a  lea     rcx, [rbp+1720h+var_10A0]
0x180016991  mov     [rsp+1820h+var_17E0], rcx; unsigned __int16 *
0x180016996  lea     rcx, [rbp+1720h+var_12B0]
0x18001699d  mov     [rsp+1820h+var_17E8], rcx; unsigned __int16 *
0x1800169a2  lea     rcx, [rbp+1720h+var_1748]
0x1800169a6  mov     qword ptr [rsp+1820h+dwReserved], rcx; struct _FILETIME *
0x1800169ab  lea     rcx, [rbp+1720h+var_1780]; this
0x1800169af  mov     [rsp+1820h+pcbBuffer], rcx; unsigned int *
0x1800169b4  mov     qword ptr [rsp+1820h+cbBuffer], rax; unsigned __int16 *
0x1800169b9  call    ?_UpdateHistoryData@CUrlHistoryBase@@IEAAJPEBG0PEAUIHistoryData@@0PEAIPEAU_FILETIME@@000PEAJPEAK5PEAUIStream@@6@Z; CUrlHistoryBase::_UpdateHistoryData(ushort const *,ushort const *,IHistoryData *,ushort const *,uint *,_FILETIME *,ushort const *,ushort const *,ushort const *,long *,ulong *,ulong *,IStream *,IStream *)
0x1800169be  test    eax, eax
0x1800169c0  js      loc_180016C4B
0x1800169c6  mov     rcx, [rbp+1720h+var_17A0]
0x1800169ca  lea     r8, [rbp+1720h+var_1798]
0x1800169ce  xor     eax, eax
0x1800169d0  xorps   xmm0, xmm0
0x1800169d3  mov     [rbp+1720h+var_1788], rax
0x1800169d7  mov     edx, 9
0x1800169dc  movups  xmmword ptr [rbp+1720h+var_1798], xmm0
0x1800169e0  mov     rax, [rcx]
0x1800169e3  xor     esi, esi
0x1800169e5  mov     rax, [rax+18h]
0x1800169e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169ee  test    eax, eax
0x1800169f0  jns     loc_180016F54
0x1800169f6  test    r14b, 4
0x1800169fa  jz      loc_180016F15
0x180016a00  bts     esi, 1Ch
0x180016a04  mov     ecx, r14d
0x180016a07  or      ecx, 4
0x180016a0a  bt      esi, 1Ch
0x180016a0e  cmovnb  ecx, r14d
0x180016a12  mov     r14d, ecx
0x180016a15  call    GetBrowserProcess
0x180016a1a  lea     ecx, [rax-0Fh]
0x180016a1d  test    ecx, 0FFFFFFF6h
0x180016a23  jnz     short loc_180016A4B
0x180016a25  cmp     eax, 18h
0x180016a28  jz      short loc_180016A4B
0x180016a2a  mov     rcx, r15
0x180016a2d  call    GetUrlSchemeW
0x180016a32  sub     eax, 4
0x180016a35  jz      short loc_180016A9B
0x180016a37  sub     eax, 0Bh
0x180016a3a  jz      short loc_180016A9B
0x180016a3c  sub     eax, 1
0x180016a3f  jz      short loc_180016A9B
0x180016a41  sub     eax, 1
0x180016a44  jz      short loc_180016A97
0x180016a46  cmp     eax, 1
0x180016a49  jz      short loc_180016A9B
0x180016a4b  lea     rax, [rbp+1720h+var_1768]
0x180016a4f  mov     [rsp+1820h+dwReserved], 0; dwReserved
0x180016a57  mov     [rsp+1820h+pcbBuffer], rax; pcbBuffer
0x180016a5c  lea     r9, [rbp+1720h+pvBuffer]; pvBuffer
0x180016a60  xor     r8d, r8d; dwQueryFlags
0x180016a63  mov     [rsp+1820h+cbBuffer], 4; cbBuffer
0x180016a6b  mov     edx, 0Fh; QueryOptions
0x180016a70  mov     [rbp+1720h+pvBuffer], 0
0x180016a77  mov     rcx, r15; pwzUrl
0x180016a7a  mov     [rbp+1720h+var_1768], 0
0x180016a81  call    cs:__imp_CoInternetQueryInfo
0x180016a88  nop     dword ptr [rax+rax+00h]
0x180016a8d  test    eax, eax
0x180016a8f  js      short loc_180016A9B
0x180016a91  cmp     [rbp+1720h+pvBuffer], 0
0x180016a95  jnz     short loc_180016A9B
0x180016a97  btr     esi, 1Ch
0x180016a9b  mov     ebx, esi
0x180016a9d  and     ebx, 0FFFFFFFEh
0x180016aa0  test    sil, 1
0x180016aa4  cmovz   ebx, esi
0x180016aa7  mov     esi, 13h
0x180016aac  test    r14b, 8
0x180016ab0  jnz     loc_180016F80
0x180016ab6  bt      ebx, 1Ch
0x180016aba  jnb     loc_180016F80
0x180016ac0  mov     rcx, [rbp+1720h+var_17A0]
0x180016ac4  lea     r8, [rbp+1720h+pvar]
0x180016ac8  xor     eax, eax
0x180016aca  xorps   xmm0, xmm0
0x180016acd  mov     [rbp+1720h+var_1720], rax
0x180016ad1  mov     edx, 6
0x180016ad6  mov     eax, [rbp+1720h+var_175C]
0x180016ad9  inc     eax
0x180016adb  movups  xmmword ptr [rbp+1720h+pvar], xmm0
0x180016adf  mov     dword ptr [rbp+1720h+pvar+8], eax
0x180016ae2  mov     word ptr [rbp+1720h+pvar], si
0x180016ae6  mov     rax, [rcx]
0x180016ae9  mov     rax, [rax+20h]
0x180016aed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016af2  mov     r15, qword ptr [rbp+1720h+SystemTimeAsFileTime.dwLowDateTime]
0x180016af6  lea     rcx, [rbp+1720h+FileTime]
0x180016afa  mov     r8d, [rbp+1720h+var_1780]
0x180016afe  mov     r9d, r13d
0x180016b01  mov     [rsp+1820h+var_17E8], rcx
0x180016b06  mov     edx, r14d
0x180016b09  lea     rcx, [rbp+1720h+var_1748]
0x180016b0d  mov     rax, [r15]
0x180016b10  mov     qword ptr [rsp+1820h+dwReserved], rcx
0x180016b15  mov     rcx, [rbp+1720h+var_17A0]
0x180016b19  mov     [rsp+1820h+pcbBuffer], rcx
0x180016b1e  mov     rcx, r15
0x180016b21  mov     rax, [rax+0D8h]
0x180016b28  mov     byte ptr [rsp+1820h+cbBuffer], r12b
0x180016b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b32  mov     rcx, [rbp+1720h+var_17A0]
0x180016b36  lea     r8, [rbp+1720h+var_1700]
0x180016b3a  xor     eax, eax
0x180016b3c  xorps   xmm0, xmm0
0x180016b3f  movups  [rbp+1720h+var_1700], xmm0
0x180016b43  mov     [rbp+1720h+var_16F0], rax
0x180016b47  mov     edx, 9
0x180016b4c  mov     word ptr [rbp+1720h+var_1700], si
0x180016b50  mov     dword ptr [rbp+1720h+var_1700+8], ebx
0x180016b53  mov     rax, [rcx]
0x180016b56  mov     rax, [rax+20h]
0x180016b5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b5f  cmp     cs:?s_dwDaysToKeep@CUrlHistoryBase@@0KA, 0; ulong CUrlHistoryBase::s_dwDaysToKeep
0x180016b66  mov     rbx, [rbp+1720h+var_17A0]
0x180016b6a  jz      loc_180017285
0x180016b70  lea     rcx, [rbp+1720h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180016b74  mov     qword ptr [rbp+1720h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180016b7c  call    cs:__imp_GetSystemTimeAsFileTime
0x180016b83  nop     dword ptr [rax+rax+00h]
0x180016b88  mov     rax, [rbx]
0x180016b8b  lea     rdx, [rbp+1720h+SystemTimeAsFileTime]
0x180016b8f  mov     rcx, rbx
0x180016b92  mov     rax, [rax+68h]
0x180016b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b9b  mov     eax, cs:?s_dwDaysToKeep@CUrlHistoryBase@@0KA; ulong CUrlHistoryBase::s_dwDaysToKeep
0x180016ba1  mov     esi, 0FFFFFFFFh
0x180016ba6  add     eax, 6
0x180016ba9  xorps   xmm0, xmm0
0x180016bac  imul    eax, 15180h
0x180016bb2  mov     rcx, rbx
0x180016bb5  movups  xmmword ptr [rbp+1720h+pvar], xmm0
0x180016bb9  imul    r8, rax, 989680h
0x180016bc0  mov     rax, r8
0x180016bc3  cqo
0x180016bc5  idiv    rsi
0x180016bc8  mov     edx, [rbp+1720h+SystemTimeAsFileTime.dwLowDateTime]
0x180016bcb  add     edx, r8d
0x180016bce  lea     r8, [rbp+1720h+pvar]
0x180016bd2  add     edx, eax
  ... truncated ...
```
