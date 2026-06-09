# ReadAllDataFromXML(char *,char *,char *,int,int)

- ea: `0x180021c40`
- end: `0x180022675`
- name: `?ReadAllDataFromXML@@YAJPEAD00HH@Z`
- size: `2613`
- prototype: `__int64 __fastcall(char *, char *, LPCCH lpMultiByteStr, int, int)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001fa58`

## callees

- `0x180008a08`
- `0x180009bd0`
- `0x18000f954`
- `0x18001031c`
- `0x180010580`
- `0x180010714`
- `0x18001b98c`
- `0x18001d614`
- `0x18001e9a8`
- `0x18001eb74`
- `0x180020014`
- `0x18002025c`
- `0x1800204fc`
- `0x18002056c`
- `0x180021c40`
- `0x18002267c`
- `0x180022ab8`
- `0x1800255c4`
- `0x18003099a`
- `0x1800309d0`
- `0x180031010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180022204`
- `msvcrt!_wcsnicmp` at `0x180022204`
- `KERNEL32!WaitForSingleObject` at `0x180021e32`
- `KERNEL32!WaitForSingleObject` at `0x180021e32`
- `KERNEL32!lstrlenW` at `0x180021f11`
- `KERNEL32!lstrlenW` at `0x180021f11`
- `KERNEL32!ReleaseSemaphore` at `0x1800225ac`
- `KERNEL32!ReleaseSemaphore` at `0x1800225ac`
- `KERNEL32!LeaveCriticalSection` at `0x1800224d1`
- `KERNEL32!LeaveCriticalSection` at `0x1800224d1`
- `KERNEL32!EnterCriticalSection` at `0x1800224ac`
- `KERNEL32!EnterCriticalSection` at `0x1800224ac`
- `KERNEL32!GetFileAttributesExW` at `0x18002248a`
- `KERNEL32!GetFileAttributesExW` at `0x18002248a`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x180021cf0`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x180021d0f`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x180021cf0`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x180021d0f`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800223eb`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800223eb`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180021e3f`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180021e3f`
- `IisRTL!PuDbgPrintW` at `0x180021d61`
- `IisRTL!PuDbgPrintW` at `0x180021dc8`
- `IisRTL!PuDbgPrintW` at `0x180021e12`
- `IisRTL!PuDbgPrintW` at `0x1800220a0`
- `IisRTL!PuDbgPrintW` at `0x1800222b1`
- `IisRTL!PuDbgPrintW` at `0x1800223bb`
- `IisRTL!PuDbgPrintW` at `0x180022542`
- `IisRTL!PuDbgPrintW` at `0x180022592`
- `IisRTL!PuDbgPrintW` at `0x180021d61`
- `IisRTL!PuDbgPrintW` at `0x180021dc8`
- `IisRTL!PuDbgPrintW` at `0x180021e12`
- `IisRTL!PuDbgPrintW` at `0x1800220a0`
- `IisRTL!PuDbgPrintW` at `0x1800222b1`
- `IisRTL!PuDbgPrintW` at `0x1800223bb`
- `IisRTL!PuDbgPrintW` at `0x180022542`
- `IisRTL!PuDbgPrintW` at `0x180022592`
- `IISCFG!DllGetSimpleObjectByIDEx` at `0x180021ea2`
- `IISCFG!DllGetSimpleObjectByIDEx` at `0x180021ea2`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x180021f4b`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x180021fda`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x180022446`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x180022641`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x180021f4b`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x180021fda`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x180022446`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x180022641`
- `IISADMIN!RetrieveTracingHandle` at `0x180021cc1`
- `IISADMIN!RetrieveTracingHandle` at `0x180021cc1`

## string_xrefs

- `0x180021d4f`: `[ReadAllDataFromXML] GetUnicodeName failed with hr = 0x%x.\n`
- `0x180021df1`: `[ReadAllDataFromXML] GetUnicodeName failed with hr = 0x%x.\n`
- `0x180021d3d`: `ReadAllDataFromXML`
- `0x180021daa`: `ReadAllDataFromXML`
- `0x180021dff`: `ReadAllDataFromXML`
- `0x180022087`: `ReadAllDataFromXML`
- `0x180022285`: `ReadAllDataFromXML`
- `0x18002238e`: `ReadAllDataFromXML`
- `0x180022520`: `ReadAllDataFromXML`
- `0x180022570`: `ReadAllDataFromXML`
- `0x180021d9e`: `[ReadAllDataFromXML]\nDataFileName:%s\nSchemaFileName:%s\n`
- `0x180021ec7`: `[ReadAllDataFromXML] DllGetSimpleObjectByIDEx failed with hr = 0x%x.\n`
- `0x180021ffb`: `[ReadAllDataFromXML] GetTable failed with hr = 0x%x.\n`
- `0x180022080`: `[ReadAllDataFromXML] Should not be reading from schema bin.\n`
- `0x1800223af`: `[ReadAllDataFromXML] GetColumnValues failed with hr = 0x%x. Table:%s. Read row index:%d.\n`
- `0x1800222a5`: `[ReadAllDataFromXML] Encountered discontinuous location:%s. Ignoring this and all locations below it.\n`
- `0x18002250c`: `[ReadAllDataFromXML] Locking metabase file %s returned 0x%x.\n`

## pseudocode

```c
__int64 __fastcall ReadAllDataFromXML(char *a1, char *a2, LPCCH lpMultiByteStr, int a4, int a5)
{
  WCHAR *v5; // rsi
  unsigned __int16 *v6; // r13
  struct IIS_CRYPTO_STORAGE *v7; // r12
  struct IIS_CRYPTO_STORAGE *v11; // rdx
  struct CEtwTracer *TracingHandle; // rbx
  const CHAR *Str; // rsi
  int UnicodeNameA; // eax
  int v15; // eax
  char v16; // cl
  unsigned int v17; // edx
  int v18; // r14d
  int SimpleObjectByIDEx; // eax
  _DWORD *v20; // rdi
  int v21; // eax
  int v22; // r9d
  int v23; // r14d
  int v24; // eax
  int AdminACL; // eax
  wchar_t *v26; // rdi
  int v27; // r15d
  unsigned int i; // r13d
  int v29; // eax
  wchar_t *v30; // r9
  int v31; // eax
  int v32; // ecx
  BOOL v33; // r14d
  unsigned int v34; // r9d
  int v35; // edx
  int v36; // edi
  int DataObject; // eax
  CMDBaseObject *v38; // rcx
  unsigned int v39; // edi
  unsigned int v40; // r14d
  int v41; // ecx
  char *v42; // rax
  unsigned __int64 v43; // rdi
  struct _FILETIME v44; // rax
  int v45; // eax
  int v46; // eax
  unsigned __int16 *v48; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *v49; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *v50; // [rsp+28h] [rbp-D8h]
  struct _FILETIME *v51; // [rsp+30h] [rbp-D0h]
  unsigned __int16 *v52; // [rsp+38h] [rbp-C8h]
  unsigned __int16 *v53; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *v54; // [rsp+48h] [rbp-B8h]
  int Warning; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpString; // [rsp+58h] [rbp-A8h] BYREF
  int v57; // [rsp+60h] [rbp-A0h] BYREF
  int v58; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned __int16 *v59; // [rsp+68h] [rbp-98h] BYREF
  struct ISimpleTableRead2 *v60; // [rsp+70h] [rbp-90h] BYREF
  int v61; // [rsp+78h] [rbp-88h]
  int v62; // [rsp+7Ch] [rbp-84h]
  int v63; // [rsp+80h] [rbp-80h]
  struct _FILETIME v64; // [rsp+88h] [rbp-78h] BYREF
  char *v65; // [rsp+90h] [rbp-70h]
  __int64 v66; // [rsp+98h] [rbp-68h] BYREF
  int v67; // [rsp+A0h] [rbp-60h] BYREF
  struct IIS_CRYPTO_STORAGE *v68; // [rsp+A8h] [rbp-58h] BYREF
  struct CMDBaseObject *v69; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v70; // [rsp+B8h] [rbp-48h] BYREF
  int v71; // [rsp+C0h] [rbp-40h]
  int v72; // [rsp+C4h] [rbp-3Ch]
  __int64 v73; // [rsp+C8h] [rbp-38h]
  WCHAR *v74; // [rsp+D0h] [rbp-30h]
  int v75; // [rsp+D8h] [rbp-28h]
  int v76; // [rsp+DCh] [rbp-24h]
  int v77; // [rsp+E0h] [rbp-20h]
  int v78; // [rsp+E4h] [rbp-1Ch]
  __int128 FileInformation; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v80; // [rsp+F8h] [rbp-8h] BYREF
  int v81; // [rsp+108h] [rbp+8h]
  _DWORD v82[8]; // [rsp+110h] [rbp+10h] BYREF
  void *v83[4]; // [rsp+130h] [rbp+30h] BYREF
  wchar_t *String1; // [rsp+150h] [rbp+50h]
  _DWORD *v85; // [rsp+158h] [rbp+58h]
  int *v86; // [rsp+168h] [rbp+68h]
  unsigned int v87[10]; // [rsp+180h] [rbp+80h] BYREF

  v63 = a4;
  Warning = 0;
  v5 = 0;
  v58 = 0;
  v6 = 0;
  v66 = 0;
  v7 = 0;
  v60 = 0;
  lpString = 0;
  v59 = 0;
  v69 = 0;
  v68 = 0;
  v64 = 0;
  v57 = 0;
  v62 = 0;
  v65 = a2;
  v67 = 2;
  TracingHandle = RetrieveTracingHandle();
  if ( !g_fcsEditWhileRunningInitialized )
  {
    Warning = -2147418113;
    goto LABEL_87;
  }
  if ( a1 || a2 )
  {
    Str = a2;
    if ( a1 )
      goto LABEL_9;
  }
  else
  {
    Str = STR::QueryStr(g_strRealFileName);
  }
  if ( !lpMultiByteStr )
    lpMultiByteStr = STR::QueryStr(g_strSchemaFileName);
LABEL_9:
  UnicodeNameA = GetUnicodeNameA(Str, (unsigned __int16 **)&lpString);
  Warning = UnicodeNameA;
  if ( UnicodeNameA < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
        2237,
        "ReadAllDataFromXML",
        L"[ReadAllDataFromXML] GetUnicodeName failed with hr = 0x%x.\n",
        UnicodeNameA);
    v5 = (WCHAR *)lpString;
    goto LABEL_87;
  }
  v15 = GetUnicodeNameA(lpMultiByteStr, &v59);
  v16 = g_dwDebugFlags;
  v5 = (WCHAR *)lpString;
  v6 = v59;
  Warning = v15;
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
      2250,
      "ReadAllDataFromXML",
      L"[ReadAllDataFromXML]\nDataFileName:%s\nSchemaFileName:%s\n",
      lpString,
      v59);
    v16 = g_dwDebugFlags;
  }
  if ( Warning < 0 )
  {
    if ( (v16 & 3) != 0 )
    {
      LODWORD(v48) = Warning;
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
        2255,
        "ReadAllDataFromXML",
        L"[ReadAllDataFromXML] GetUnicodeName failed with hr = 0x%x.\n",
        v48);
    }
    goto LABEL_87;
  }
  v61 = -1;
  if ( !v63 )
    WaitForSingleObject(g_hReadSaveSemaphore, 0xFFFFFFFF);
  CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)&g_LockMasterResource);
  v62 = 1;
  InitializeIIS6GlobalsToDefaults(1u, v17, a2);
  Warning = CompileIfNeeded(v5, v6, &v57, TracingHandle);
  if ( Warning >= 0 )
  {
    v18 = v57;
    if ( v57 )
      g_dwLastSchemaChangeNumber = 0;
    SimpleObjectByIDEx = DllGetSimpleObjectByIDEx(1, &IID_ISimpleTableDispenser2, &v66, L"IIS");
    Warning = SimpleObjectByIDEx;
    if ( SimpleObjectByIDEx < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        LODWORD(v48) = SimpleObjectByIDEx;
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
          2329,
          "ReadAllDataFromXML",
          L"[ReadAllDataFromXML] DllGetSimpleObjectByIDEx failed with hr = 0x%x.\n",
          v48);
      }
      goto LABEL_87;
    }
    v70 = *((_QWORD *)g_pGlobalISTHelper + 31);
    v71 = 2;
    v75 = 2;
    v72 = -268435447;
    v73 = 130;
    v74 = v5;
    v76 = -268435455;
    v77 = 130;
    v78 = 2 * lstrlenW(v5) + 2;
    if ( *((_DWORD *)TracingHandle + 2) && (*((_BYTE *)TracingHandle + 40) & 1) != 0 )
    {
      v20 = (_DWORD *)((char *)TracingHandle + 44);
      if ( *((_DWORD *)TracingHandle + 11) >= 4u )
        CEtwTracer::EtwTraceEvent(TracingHandle, (const struct _GUID *)IISAdminStatupGuid, 0x16u);
    }
    else
    {
      v20 = (_DWORD *)((char *)TracingHandle + 44);
    }
    Warning = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *, __int64 *, int *, int, _DWORD, struct ISimpleTableRead2 **))(*(_QWORD *)v66 + 24LL))(
                v66,
                L"METABASE",
                L"MBProperty",
                &v70,
                &v67,
                3,
                0,
                &v60);
    if ( Warning < 0 )
    {
      if ( *((_DWORD *)TracingHandle + 2) && (*((_BYTE *)TracingHandle + 40) & 1) != 0 && *v20 )
        CEtwTracer::EtwTraceEvent(TracingHandle, (const struct _GUID *)IISAdminStatupGuid, 0x18u, &Warning, 4, 0, 0);
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        LODWORD(v49) = Warning;
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
          2380,
          "ReadAllDataFromXML",
          L"[ReadAllDataFromXML] GetTable failed with hr = 0x%x.\n",
          v49);
      }
      goto LABEL_87;
    }
    v21 = InitializeGlobalsFromXML(v60, v5, v6, &v68, a1, v65 != 0, &v64, TracingHandle, a5);
    v7 = v68;
    Warning = v21;
    if ( v21 < 0 )
      goto LABEL_87;
    v57 = 1;
    if ( v18 && (unsigned int)SchemaTreeInTable(v60) )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
          2417,
          "ReadAllDataFromXML",
          L"[ReadAllDataFromXML] Should not be reading from schema bin.\n");
      v23 = 0;
      v57 = 0;
    }
    else
    {
      lpString = 0;
      v24 = ReadMetaObject((struct CMDBaseObject **)&lpString, L"/Schema", &v64, v22);
      if ( v24 >= 0 )
      {
        AdminACL = ReadAdminACL((struct CMDBaseObject *)lpString, v11);
        if ( AdminACL < 0 || (AdminACL = ReadLargestMetaID((struct CMDBaseObject *)lpString, v7), AdminACL < 0) )
        {
          Warning = AdminACL;
          goto LABEL_87;
        }
        v24 = ReadProperties(v7, &v64);
        if ( v24 >= 0 )
          v24 = ReadClasses(v7, &v64);
      }
      Warning = v24;
      if ( v24 < 0 )
        goto LABEL_87;
      v23 = v57;
    }
    v26 = (wchar_t *)L"/";
    v27 = 0;
    lpString = L"/";
    for ( i = 0; ; ++i )
    {
      memset_0(v83, 0, 0x48u);
      v50 = (unsigned __int16 *)v83;
      v82[0] = 0;
      v82[1] = 4;
      v82[2] = 5;
      v82[3] = 2;
      v82[4] = 6;
      v82[5] = 1;
      v82[6] = 3;
      v82[7] = 7;
      v29 = (*(__int64 (__fastcall **)(struct ISimpleTableRead2 *, _QWORD, __int64, _DWORD *))(*(_QWORD *)v60 + 32LL))(
              v60,
              i,
              8,
              v82);
      Warning = v29;
      if ( v29 == -2145318890 )
      {
        Warning = 0;
        goto LABEL_86;
      }
      if ( v29 < 0 )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
        {
          LODWORD(v52) = i;
          LODWORD(v50) = Warning;
          PuDbgPrintW(
            g_pDebug,
            "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
            2473,
            "ReadAllDataFromXML",
            L"[ReadAllDataFromXML] GetColumnValues failed with hr = 0x%x. Table:%s. Read row index:%d.\n",
            v50,
            L"MBProperty",
            v52);
        }
LABEL_86:
        v6 = v59;
        break;
      }
      v30 = String1;
      v31 = *String1;
      v32 = 46 - v31;
      if ( v31 == 46 )
        v32 = -String1[1];
      if ( v32 )
      {
        if ( v23 )
        {
          if ( !_wcsnicmp(String1, L"/Schema", (unsigned int)g_cchSlashSchema) )
            goto LABEL_82;
          v30 = String1;
        }
        v33 = 1;
        if ( *v85 == 9989 )
          v33 = *(_WORD *)v83[0] != 35;
        if ( v61 == *v86 )
        {
          v35 = 0;
          if ( v27 )
            goto LABEL_82;
        }
        else
        {
          v61 = *v86;
          v27 = DiscontinuousLocation(v26, v30);
          if ( v27 )
          {
            if ( (g_dwDebugFlags & 3) != 0 )
              PuDbgPrintW(
                g_pDebug,
                "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
                2513,
                "ReadAllDataFromXML",
                L"[ReadAllDataFromXML] Encountered discontinuous location:%s. Ignoring this and all locations below it.\n",
                String1);
            LogEvent(g_pEventLog, 0x8002C83C, 2u, v34, 13, String1, 0, v52, v53, v54);
            goto LABEL_82;
          }
          v30 = String1;
          v35 = 1;
          lpString = String1;
        }
        v36 = *v30 - 47;
        if ( *v30 == 47 )
          v36 = v30[1];
        if ( v35 )
        {
          if ( v36 )
          {
            DataObject = ReadMetaObject(&v69, v30, &v64, (int)v30);
            Warning = DataObject;
            if ( DataObject < 0 )
              goto LABEL_79;
          }
        }
        if ( v33 )
        {
          v38 = v69;
          if ( !v36 )
            v38 = g_pboMasterRoot;
          DataObject = ReadDataObject(v38, v83, v87, v7, (int)v87);
          Warning = DataObject;
          if ( DataObject < 0 )
          {
LABEL_79:
            if ( DataObject == -2147024882 )
              goto LABEL_86;
            v58 = DataObject;
          }
        }
        v26 = (wchar_t *)lpString;
      }
LABEL_82:
      v23 = v57;
    }
  }
LABEL_87:
  v39 = *(_DWORD *)&g_dwSystemChangeNumber;
  v40 = g_ulHistoryMajorVersionNumber;
  if ( v62 )
    CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)&g_LockMasterResource);
  if ( Warning >= 0 )
  {
    v41 = v58;
    if ( v58 )
    {
      if ( *((_DWORD *)TracingHandle + 2)
        && (*((_BYTE *)TracingHandle + 40) & 1) != 0
        && *((_DWORD *)TracingHandle + 11) >= 3u )
      {
        CEtwTracer::EtwTraceEvent(TracingHandle, (const struct _GUID *)IISAdminStatupGuid, 0x19u, &v58, 4, 0, 0);
        v41 = v58;
      }
      Warning = GetWarning(v41);
    }
    if ( Warning >= 0 )
    {
      v42 = v65;
      g_dwLastSaveChangeNumber = v39;
      if ( !v65 )
      {
        v81 = 0;
        FileInformation = 0;
        v80 = 0;
        v43 = ((unsigned __int64)&v80 + 4) & -(__int64)GetFileAttributesExW(v5, GetFileExInfoStandard, &FileInformation);
        if ( g_fcsEditWhileRunningInitialized )
        {
          EnterCriticalSection(&g_csEditWhileRunning);
          v44 = 0;
          g_ulMostRecentMetabaseVersion = v40;
          if ( v43 )
            v44 = *(struct _FILETIME *)((char *)&v80 + 4);
          g_MostRecentMetabaseFileLastWriteTimeStamp = v44;
          LeaveCriticalSection(&g_csEditWhileRunning);
        }
        v42 = v65;
      }
      if ( Warning >= 0 && !v42 && !g_dwEnableEditWhileRunning )
      {
        v45 = LockMetabaseFile(v5, 0);
        Warning = v45;
        if ( (g_dwDebugFlags & 3) != 0 )
        {
          LODWORD(v51) = v45;
          PuDbgPrintW(
            g_pDebug,
            "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
            2740,
            "ReadAllDataFromXML",
            L"[ReadAllDataFromXML] Locking metabase file %s returned 0x%x.\n",
            v5,
            v51);
        }
        if ( Warning >= 0 )
        {
          v46 = LockMetabaseFile(v6, 1);
          Warning = v46;
          if ( (g_dwDebugFlags & 3) != 0 )
          {
            LODWORD(v51) = v46;
            PuDbgPrintW(
              g_pDebug,
              "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
              2751,
              "ReadAllDataFromXML",
              L"[ReadAllDataFromXML] Locking metabase file %s returned 0x%x.\n",
              v6,
              v51);
          }
        }
      }
    }
  }
  if ( !v63 )
    ReleaseSemaphore(g_hReadSaveSemaphore, 1, 0);
  if ( v60 )
  {
    (*(void (__fastcall **)(struct ISimpleTableRead2 *))(*(_QWORD *)v60 + 16LL))(v60);
    v60 = 0;
  }
  if ( v66 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
    v66 = 0;
  }
  if ( v5 )
    operator delete(v5);
  if ( v6 )
    operator delete(v6);
  if ( v7 )
    IIS_CRYPTO_STORAGE::`scalar deleting destructor'(v7, (unsigned int)v11);
  if ( *((_DWORD *)TracingHandle + 2)
    && (*((_BYTE *)TracingHandle + 40) & 1) != 0
    && *((_DWORD *)TracingHandle + 11) >= 4u )
  {
    CEtwTracer::EtwTraceEvent(TracingHandle, (const struct _GUID *)IISAdminStatupGuid, 0x1Au);
  }
  return (unsigned int)Warning;
}

```

## disassembly

```asm
0x180021c40  mov     [rsp-8+arg_18], rbx
0x180021c45  push    rbp
0x180021c46  push    rsi
0x180021c47  push    rdi
0x180021c48  push    r12
0x180021c4a  push    r13
0x180021c4c  push    r14
0x180021c4e  push    r15
0x180021c50  lea     rbp, [rsp-0B0h]
0x180021c58  sub     rsp, 1B0h
0x180021c5f  mov     rax, cs:__security_cookie
0x180021c66  xor     rax, rsp
0x180021c69  mov     [rbp+0E0h+var_38], rax
0x180021c70  xor     eax, eax
0x180021c72  mov     [rbp+0E0h+var_160], r9d
0x180021c76  mov     [rsp+1E0h+var_190], eax
0x180021c7a  mov     esi, eax
0x180021c7c  mov     [rsp+1E0h+var_17C], eax
0x180021c80  mov     r13d, eax
0x180021c83  mov     [rbp+0E0h+var_148], rax
0x180021c87  mov     r12d, eax
0x180021c8a  mov     [rsp+1E0h+var_170], rax
0x180021c8f  mov     rdi, r8
0x180021c92  mov     [rsp+1E0h+lpString], rax
0x180021c97  mov     r14, rdx
0x180021c9a  mov     [rsp+1E0h+var_178], rax
0x180021c9f  mov     r15, rcx
0x180021ca2  mov     [rbp+0E0h+var_130], rax
0x180021ca6  mov     [rbp+0E0h+var_138], rax
0x180021caa  mov     qword ptr [rbp+0E0h+var_158.dwLowDateTime], rax
0x180021cae  mov     [rsp+1E0h+var_180], eax
0x180021cb2  mov     [rsp+1E0h+var_164], eax
0x180021cb6  mov     [rbp+0E0h+var_150], rdx
0x180021cba  mov     [rbp+0E0h+var_140], 2
0x180021cc1  call    cs:__imp_?RetrieveTracingHandle@@YAPEAVCEtwTracer@@XZ; RetrieveTracingHandle(void)
0x180021cc7  cmp     cs:?g_fcsEditWhileRunningInitialized@@3HA, esi; int g_fcsEditWhileRunningInitialized
0x180021ccd  mov     rbx, rax
0x180021cd0  jnz     short loc_180021CDF
0x180021cd2  mov     [rsp+1E0h+var_190], 8000FFFFh
0x180021cda  jmp     loc_1800223D0
0x180021cdf  test    r15, r15
0x180021ce2  jnz     short loc_180021CFB
0x180021ce4  test    r14, r14
0x180021ce7  jnz     short loc_180021CFB
0x180021ce9  mov     rcx, cs:?g_strRealFileName@@3PEAVSTR@@EA; STR * g_strRealFileName
0x180021cf0  call    cs:__imp_?QueryStr@STR@@QEBAPEADXZ; STR::QueryStr(void)
0x180021cf6  mov     rsi, rax
0x180021cf9  jmp     short loc_180021D03
0x180021cfb  mov     rsi, r14
0x180021cfe  test    r15, r15
0x180021d01  jnz     short loc_180021D18
0x180021d03  test    rdi, rdi
0x180021d06  jnz     short loc_180021D18
0x180021d08  mov     rcx, cs:?g_strSchemaFileName@@3PEAVSTR@@EA; STR * g_strSchemaFileName
0x180021d0f  call    cs:__imp_?QueryStr@STR@@QEBAPEADXZ; STR::QueryStr(void)
0x180021d15  mov     rdi, rax
0x180021d18  lea     rdx, [rsp+1E0h+lpString]; unsigned __int16 **
0x180021d1d  mov     rcx, rsi; lpMultiByteStr
0x180021d20  call    ?GetUnicodeNameA@@YAJPEADPEAPEAG@Z; GetUnicodeNameA(char *,ushort * *)
0x180021d25  mov     [rsp+1E0h+var_190], eax
0x180021d29  test    eax, eax
0x180021d2b  jns     short loc_180021D71
0x180021d2d  test    byte ptr cs:g_dwDebugFlags, 3
0x180021d34  jz      short loc_180021D67
0x180021d36  mov     rcx, cs:g_pDebug
0x180021d3d  lea     r9, aReadalldatafro_0; "ReadAllDataFromXML"
0x180021d44  mov     dword ptr [rsp+1E0h+var_1B8], eax
0x180021d48  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x180021d4f  lea     rax, aReadalldatafro_10; "[ReadAllDataFromXML] GetUnicodeName fai"...
0x180021d56  mov     r8d, 8BDh
0x180021d5c  mov     [rsp+1E0h+var_1C0], rax
0x180021d61  call    cs:__imp_PuDbgPrintW
0x180021d67  mov     rsi, [rsp+1E0h+lpString]
0x180021d6c  jmp     loc_1800223D0
0x180021d71  lea     rdx, [rsp+1E0h+var_178]; unsigned __int16 **
0x180021d76  mov     rcx, rdi; lpMultiByteStr
0x180021d79  call    ?GetUnicodeNameA@@YAJPEADPEAPEAG@Z; GetUnicodeNameA(char *,ushort * *)
0x180021d7e  mov     ecx, cs:g_dwDebugFlags
0x180021d84  mov     rsi, [rsp+1E0h+lpString]
0x180021d89  mov     r13, [rsp+1E0h+var_178]
0x180021d8e  mov     [rsp+1E0h+var_190], eax
0x180021d92  test    cl, 3
0x180021d95  jz      short loc_180021DD4
0x180021d97  mov     rcx, cs:g_pDebug
0x180021d9e  lea     rax, aReadalldatafro_3; "[ReadAllDataFromXML]\nDataFileName:%s\n"...
0x180021da5  mov     [rsp+1E0h+var_1B0], r13
0x180021daa  lea     r9, aReadalldatafro_0; "ReadAllDataFromXML"
0x180021db1  mov     [rsp+1E0h+var_1B8], rsi
0x180021db6  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x180021dbd  mov     r8d, 8CAh
0x180021dc3  mov     [rsp+1E0h+var_1C0], rax
0x180021dc8  call    cs:__imp_PuDbgPrintW
0x180021dce  mov     ecx, cs:g_dwDebugFlags
0x180021dd4  mov     eax, [rsp+1E0h+var_190]
0x180021dd8  xor     edi, edi
0x180021dda  test    eax, eax
0x180021ddc  jns     short loc_180021E1D
0x180021dde  test    cl, 3
0x180021de1  jz      loc_1800223D0
0x180021de7  mov     dword ptr [rsp+1E0h+var_1B8], eax
0x180021deb  mov     r8d, 8CFh
0x180021df1  lea     rax, aReadalldatafro_10; "[ReadAllDataFromXML] GetUnicodeName fai"...
0x180021df8  mov     rcx, cs:g_pDebug
0x180021dff  lea     r9, aReadalldatafro_0; "ReadAllDataFromXML"
0x180021e06  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x180021e0d  mov     [rsp+1E0h+var_1C0], rax
0x180021e12  call    cs:__imp_PuDbgPrintW
0x180021e18  jmp     loc_1800223D0
0x180021e1d  or      eax, 0FFFFFFFFh
0x180021e20  mov     [rsp+1E0h+var_168], eax
0x180021e24  cmp     [rbp+0E0h+var_160], edi
0x180021e27  jnz     short loc_180021E38
0x180021e29  mov     rcx, cs:?g_hReadSaveSemaphore@@3PEAXEA; hHandle
0x180021e30  mov     edx, eax; dwMilliseconds
0x180021e32  call    cs:__imp_WaitForSingleObject
0x180021e38  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180021e3f  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180021e45  mov     eax, 1
0x180021e4a  mov     r8, r14; char *
0x180021e4d  mov     ecx, eax; unsigned int
0x180021e4f  mov     [rsp+1E0h+var_164], eax
0x180021e53  call    ?InitializeIIS6GlobalsToDefaults@@YAJKKPEAD@Z; InitializeIIS6GlobalsToDefaults(ulong,ulong,char *)
0x180021e58  mov     r9, rbx; struct CEtwTracer *
0x180021e5b  mov     [rsp+1E0h+var_190], eax
0x180021e5f  lea     r8, [rsp+1E0h+var_180]; int *
0x180021e64  mov     rdx, r13; unsigned __int16 *
0x180021e67  mov     rcx, rsi; lpString
0x180021e6a  call    ?CompileIfNeeded@@YAJPEAG0PEAHPEAVCEtwTracer@@@Z; CompileIfNeeded(ushort *,ushort *,int *,CEtwTracer *)
0x180021e6f  mov     [rsp+1E0h+var_190], eax
0x180021e73  test    eax, eax
0x180021e75  js      loc_1800223D0
0x180021e7b  mov     r14d, [rsp+1E0h+var_180]
0x180021e80  test    r14d, r14d
0x180021e83  jz      short loc_180021E8B
0x180021e85  mov     cs:?g_dwLastSchemaChangeNumber@@3KA, edi; ulong g_dwLastSchemaChangeNumber
0x180021e8b  lea     r9, aIis; "IIS"
0x180021e92  mov     ecx, 1
0x180021e97  lea     r8, [rbp+0E0h+var_148]
0x180021e9b  lea     rdx, IID_ISimpleTableDispenser2
0x180021ea2  call    cs:__imp_DllGetSimpleObjectByIDEx
0x180021ea8  mov     [rsp+1E0h+var_190], eax
0x180021eac  test    eax, eax
0x180021eae  jns     short loc_180021ED3
0x180021eb0  test    byte ptr cs:g_dwDebugFlags, 3
0x180021eb7  jz      loc_1800223D0
0x180021ebd  mov     dword ptr [rsp+1E0h+var_1B8], eax
0x180021ec1  mov     r8d, 919h
0x180021ec7  lea     rax, aReadalldatafro_1; "[ReadAllDataFromXML] DllGetSimpleObject"...
0x180021ece  jmp     loc_180021DF8
0x180021ed3  mov     rax, cs:?g_pGlobalISTHelper@@3PEAVCWriterGlobalHelper@@EA; CWriterGlobalHelper * g_pGlobalISTHelper
0x180021eda  mov     rcx, [rax+0F8h]
0x180021ee1  mov     eax, 82h
0x180021ee6  mov     [rbp+0E0h+var_128], rcx
0x180021eea  mov     ecx, 2
0x180021eef  mov     [rbp+0E0h+var_120], ecx
0x180021ef2  mov     [rbp+0E0h+var_108], ecx
0x180021ef5  mov     rcx, rsi; lpString
0x180021ef8  mov     [rbp+0E0h+var_11C], 0F0000009h
0x180021eff  mov     [rbp+0E0h+var_118], rax
0x180021f03  mov     [rbp+0E0h+var_110], rsi
0x180021f07  mov     [rbp+0E0h+var_104], 0F0000001h
0x180021f0e  mov     [rbp+0E0h+var_100], eax
0x180021f11  call    cs:__imp_lstrlenW
0x180021f17  lea     eax, ds:2[rax*2]
0x180021f1e  mov     [rbp+0E0h+var_FC], eax
0x180021f21  cmp     [rbx+8], edi
0x180021f24  jz      short loc_180021F53
0x180021f26  test    byte ptr [rbx+28h], 1
0x180021f2a  jz      short loc_180021F53
0x180021f2c  lea     rdi, [rbx+2Ch]
0x180021f30  cmp     dword ptr [rdi], 4
0x180021f33  jb      short loc_180021F57
0x180021f35  xor     r9d, r9d
0x180021f38  mov     [rsp+1E0h+var_1C0], r12
0x180021f3d  lea     rdx, IISAdminStatupGuid
0x180021f44  mov     rcx, rbx
0x180021f47  lea     r8d, [r9+16h]
0x180021f4b  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ; CEtwTracer::EtwTraceEvent(_GUID const *,ulong,...)
0x180021f51  jmp     short loc_180021F57
0x180021f53  lea     rdi, [rbx+2Ch]
0x180021f57  mov     rcx, [rbp+0E0h+var_148]
0x180021f5b  lea     rdx, [rsp+1E0h+var_170]
0x180021f60  mov     [rsp+1E0h+var_1A8], rdx
0x180021f65  lea     r9, [rbp+0E0h+var_128]
0x180021f69  mov     dword ptr [rsp+1E0h+var_1B0], r12d
0x180021f6e  lea     rdx, [rbp+0E0h+var_140]
0x180021f72  mov     dword ptr [rsp+1E0h+var_1B8], 3
0x180021f7a  lea     r8, aMbproperty_0; "MBProperty"
0x180021f81  mov     rax, [rcx]
0x180021f84  mov     [rsp+1E0h+var_1C0], rdx
0x180021f89  lea     rdx, aMetabase; "METABASE"
0x180021f90  mov     rax, [rax+18h]
0x180021f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f99  mov     [rsp+1E0h+var_190], eax
0x180021f9d  test    eax, eax
0x180021f9f  jns     short loc_180022007
0x180021fa1  cmp     [rbx+8], r12d
0x180021fa5  jz      short loc_180021FE0
0x180021fa7  test    byte ptr [rbx+28h], 1
0x180021fab  jz      short loc_180021FE0
0x180021fad  cmp     dword ptr [rdi], 1
0x180021fb0  jb      short loc_180021FE0
0x180021fb2  mov     [rsp+1E0h+var_1B0], r12
0x180021fb7  lea     r9, [rsp+1E0h+var_190]
0x180021fbc  mov     [rsp+1E0h+var_1B8], r12
0x180021fc1  lea     rdx, IISAdminStatupGuid
0x180021fc8  mov     r8d, 18h
0x180021fce  mov     [rsp+1E0h+var_1C0], 4
0x180021fd7  mov     rcx, rbx
0x180021fda  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ; CEtwTracer::EtwTraceEvent(_GUID const *,ulong,...)
0x180021fe0  test    byte ptr cs:g_dwDebugFlags, 3
0x180021fe7  jz      loc_1800223D0
0x180021fed  mov     eax, [rsp+1E0h+var_190]
0x180021ff1  mov     r8d, 94Ch
0x180021ff7  mov     dword ptr [rsp+1E0h+var_1B8], eax
0x180021ffb  lea     rax, aReadalldatafro_2; "[ReadAllDataFromXML] GetTable failed wi"...
0x180022002  jmp     loc_180021DF8
0x180022007  mov     eax, dword ptr [rbp+0E0h+arg_20]
0x18002200d  lea     r9, [rbp+0E0h+var_138]; struct IIS_CRYPTO_STORAGE **
0x180022011  mov     dword ptr [rsp+1E0h+var_1A0], eax; unsigned __int16 *
0x180022015  xor     ecx, ecx
0x180022017  cmp     [rbp+0E0h+var_150], rcx
0x18002201b  lea     rax, [rbp+0E0h+var_158]
0x18002201f  mov     [rsp+1E0h+var_1A8], rbx; unsigned __int16 *
0x180022024  mov     r8, r13; unsigned __int16 *
0x180022027  setnz   cl
0x18002202a  mov     [rsp+1E0h+var_1B0], rax; struct _FILETIME *
0x18002202f  mov     dword ptr [rsp+1E0h+var_1B8], ecx; int
0x180022033  mov     rdx, rsi; unsigned __int16 *
0x180022036  mov     rcx, [rsp+1E0h+var_170]; struct ISimpleTableRead2 *
0x18002203b  mov     [rsp+1E0h+var_1C0], r15; char *
0x180022040  call    ?InitializeGlobalsFromXML@@YAJPEAUISimpleTableRead2@@PEAG1PEAPEAVIIS_CRYPTO_STORAGE@@PEADHPEAU_FILETIME@@PEAVCEtwTracer@@H@Z; InitializeGlobalsFromXML(ISimpleTableRead2 *,ushort *,ushort *,IIS_CRYPTO_STORAGE * *,char *,int,_FILETIME *,CEtwTracer *,int)
0x180022045  mov     r12, [rbp+0E0h+var_138]
0x180022049  mov     [rsp+1E0h+var_190], eax
0x18002204d  test    eax, eax
0x18002204f  js      loc_1800223D0
0x180022055  mov     [rsp+1E0h+var_180], 1
0x18002205d  test    r14d, r14d
0x180022060  jz      short loc_1800220B0
0x180022062  mov     rcx, [rsp+1E0h+var_170]; struct ISimpleTableRead2 *
0x180022067  call    ?SchemaTreeInTable@@YAHPEAUISimpleTableRead2@@@Z; SchemaTreeInTable(ISimpleTableRead2 *)
0x18002206c  test    eax, eax
0x18002206e  jz      short loc_1800220B0
0x180022070  test    byte ptr cs:g_dwDebugFlags, 3
0x180022077  jz      short loc_1800220A6
0x180022079  mov     rcx, cs:g_pDebug
0x180022080  lea     rax, aReadalldatafro_7; "[ReadAllDataFromXML] Should not be read"...
0x180022087  lea     r9, aReadalldatafro_0; "ReadAllDataFromXML"
0x18002208e  mov     [rsp+1E0h+var_1C0], rax
0x180022093  mov     r8d, 971h
0x180022099  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x1800220a0  call    cs:__imp_PuDbgPrintW
0x1800220a6  xor     r14d, r14d
0x1800220a9  mov     [rsp+1E0h+var_180], r14d
0x1800220ae  jmp     short loc_180022126
0x1800220b0  lea     r8, [rbp+0E0h+var_158]; struct _FILETIME *
0x1800220b4  mov     [rsp+1E0h+lpString], 0
0x1800220bd  lea     rdx, aSchema_3; "/Schema"
0x1800220c4  lea     rcx, [rsp+1E0h+lpString]; struct CMDBaseObject **
0x1800220c9  call    ?ReadMetaObject@@YAJAEAPEAVCMDBaseObject@@PEAGPEAU_FILETIME@@H@Z; ReadMetaObject(CMDBaseObject * &,ushort *,_FILETIME *,int)
0x1800220ce  test    eax, eax
0x1800220d0  js      short loc_180022115
0x1800220d2  mov     rcx, [rsp+1E0h+lpString]; this
0x1800220d7  call    ?ReadAdminACL@@YAJPEAVCMDBaseObject@@PEAVIIS_CRYPTO_STORAGE@@@Z; ReadAdminACL(CMDBaseObject *,IIS_CRYPTO_STORAGE *)
0x1800220dc  test    eax, eax
0x1800220de  js      loc_18002226F
0x1800220e4  mov     rcx, [rsp+1E0h+lpString]; this
0x1800220e9  mov     rdx, r12; struct IIS_CRYPTO_STORAGE *
0x1800220ec  call    ?ReadLargestMetaID@@YAJPEAVCMDBaseObject@@PEAVIIS_CRYPTO_STORAGE@@@Z; ReadLargestMetaID(CMDBaseObject *,IIS_CRYPTO_STORAGE *)
0x1800220f1  test    eax, eax
0x1800220f3  js      loc_18002226F
0x1800220f9  lea     rdx, [rbp+0E0h+var_158]; struct _FILETIME *
0x1800220fd  mov     rcx, r12; struct IIS_CRYPTO_STORAGE *
0x180022100  call    ?ReadProperties@@YAJPEAVIIS_CRYPTO_STORAGE@@PEAU_FILETIME@@@Z; ReadProperties(IIS_CRYPTO_STORAGE *,_FILETIME *)
0x180022105  test    eax, eax
0x180022107  js      short loc_180022115
0x180022109  lea     rdx, [rbp+0E0h+var_158]; struct _FILETIME *
0x18002210d  mov     rcx, r12; struct IIS_CRYPTO_STORAGE *
0x180022110  call    ?ReadClasses@@YAJPEAVIIS_CRYPTO_STORAGE@@PEAU_FILETIME@@@Z; ReadClasses(IIS_CRYPTO_STORAGE *,_FILETIME *)
0x180022115  mov     [rsp+1E0h+var_190], eax
0x180022119  test    eax, eax
0x18002211b  js      loc_1800223D0
0x180022121  mov     r14d, [rsp+1E0h+var_180]
0x180022126  lea     rdi, asc_180033DAC; "/"
0x18002212d  xor     r15d, r15d
0x180022130  mov     [rsp+1E0h+lpString], rdi
0x180022135  xor     r13d, r13d
0x180022138  xor     edx, edx; Val
0x18002213a  lea     rcx, [rbp+0E0h+var_B0]; void *
0x18002213e  lea     r8d, [rdx+48h]; Size
0x180022142  call    memset_0
0x180022147  mov     rcx, [rsp+1E0h+var_170]
0x18002214c  lea     rdx, [rbp+0E0h+var_B0]
0x180022150  mov     [rsp+1E0h+var_1B8], rdx
0x180022155  lea     r9, [rbp+0E0h+var_D0]
0x180022159  lea     rdx, [rbp+0E0h+var_60]
0x180022160  mov     [rbp+0E0h+var_D0], 0
0x180022167  mov     [rbp+0E0h+var_CC], 4
0x18002216e  mov     r8d, 8
0x180022174  mov     [rbp+0E0h+var_C8], 5
  ... truncated ...
```
