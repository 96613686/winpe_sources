# InitializeRouting(_REG_FAX_SERVICE *)

- ea: `0x140043484`
- end: `0x1400444f1`
- name: `?InitializeRouting@@YAHPEAU_REG_FAX_SERVICE@@@Z`
- size: `4205`
- prototype: `__int64 __fastcall(struct _REG_FAX_SERVICE *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x1400472a0`

## callees

- `0x140002c43`
- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x140004b98`
- `0x140004ce4`
- `0x140004df0`
- `0x140024850`
- `0x140043484`
- `0x1400447a4`
- `0x140044efc`
- `0x140065d14`
- `0x140065dbc`
- `0x140065df8`
- `0x140066334`
- `0x140067168`
- `0x140067238`
- `0x140070f1c`
- `0x1400818b0`
- `0x140085010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1400443cd`
- `KERNEL32!FreeLibrary` at `0x1400443cd`
- `KERNEL32!GetLastError` at `0x1400439cb`
- `KERNEL32!GetLastError` at `0x140043bba`
- `KERNEL32!GetLastError` at `0x140043d5e`
- `KERNEL32!GetLastError` at `0x140043ff2`
- `KERNEL32!GetLastError` at `0x140044043`
- `KERNEL32!GetLastError` at `0x1400440e7`
- `KERNEL32!GetLastError` at `0x140044147`
- `KERNEL32!GetLastError` at `0x140044188`
- `KERNEL32!GetLastError` at `0x140044220`
- `KERNEL32!GetLastError` at `0x14004427a`
- `KERNEL32!GetLastError` at `0x1400439cb`
- `KERNEL32!GetLastError` at `0x140043bba`
- `KERNEL32!GetLastError` at `0x140043d5e`
- `KERNEL32!GetLastError` at `0x140043ff2`
- `KERNEL32!GetLastError` at `0x140044043`
- `KERNEL32!GetLastError` at `0x1400440e7`
- `KERNEL32!GetLastError` at `0x140044147`
- `KERNEL32!GetLastError` at `0x140044188`
- `KERNEL32!GetLastError` at `0x140044220`
- `KERNEL32!GetLastError` at `0x14004427a`
- `KERNEL32!LoadLibraryW` at `0x1400439bb`
- `KERNEL32!LoadLibraryW` at `0x1400439bb`
- `KERNEL32!GetProcessHeap` at `0x140043b90`
- `KERNEL32!GetProcessHeap` at `0x140043b90`
- `KERNEL32!HeapCreate` at `0x140043ba5`
- `KERNEL32!HeapCreate` at `0x140043ba5`
- `KERNEL32!GetProcAddress` at `0x140043a8b`
- `KERNEL32!GetProcAddress` at `0x140043aa0`
- `KERNEL32!GetProcAddress` at `0x140043ab9`
- `KERNEL32!GetProcAddress` at `0x140043ad2`
- `KERNEL32!GetProcAddress` at `0x140043aeb`
- `KERNEL32!GetProcAddress` at `0x140043b4a`
- `KERNEL32!GetProcAddress` at `0x140043f32`
- `KERNEL32!GetProcAddress` at `0x140043a8b`
- `KERNEL32!GetProcAddress` at `0x140043aa0`
- `KERNEL32!GetProcAddress` at `0x140043ab9`
- `KERNEL32!GetProcAddress` at `0x140043ad2`
- `KERNEL32!GetProcAddress` at `0x140043aeb`
- `KERNEL32!GetProcAddress` at `0x140043b4a`
- `KERNEL32!GetProcAddress` at `0x140043f32`
- `KERNEL32!HeapDestroy` at `0x1400443eb`
- `KERNEL32!HeapDestroy` at `0x1400443eb`
- `msvcrt!_wcsicmp` at `0x140043930`
- `msvcrt!_wcsicmp` at `0x140043949`
- `msvcrt!_wcsicmp` at `0x140043dd0`
- `msvcrt!_wcsicmp` at `0x140043930`
- `msvcrt!_wcsicmp` at `0x140043949`
- `msvcrt!_wcsicmp` at `0x140043dd0`
- `msvcrt!_wsplitpath_s` at `0x14004387a`
- `msvcrt!_wsplitpath_s` at `0x14004387a`
- `ole32!IIDFromString` at `0x140043f00`
- `ole32!IIDFromString` at `0x140043f00`

## string_xrefs

- `0x140043b3e`: `FaxExtInitializeConfig`

## pseudocode

```c
__int64 __fastcall InitializeRouting(struct _REG_FAX_SERVICE *a1)
{
  struct _REG_FAX_SERVICE *v1; // r14
  unsigned int v2; // ebx
  _DWORD *v3; // rax
  __int64 v4; // rsi
  __int64 *v5; // r14
  unsigned int v6; // r12d
  __int64 v7; // r15
  const WCHAR *v8; // r8
  WCHAR *v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rcx
  WCHAR v12; // r9
  signed int v13; // ebx
  WCHAR *v14; // rax
  const WCHAR *v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rcx
  WCHAR *v18; // r8
  WCHAR v19; // r9
  WCHAR *v20; // rax
  const WCHAR *v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rdx
  WCHAR *v24; // r8
  WCHAR v25; // r9
  WCHAR *v26; // rax
  CMapDeviceId *v27; // rcx
  _DWORD *v28; // r12
  HMODULE LibraryW; // rax
  DWORD LastError; // eax
  int FileVersion; // eax
  unsigned int (__fastcall **v32)(_QWORD, int *); // rbx
  FARPROC ProcAddress; // rax
  FARPROC v34; // rax
  HANDLE ProcessHeap; // rax
  DWORD v36; // eax
  __int64 (__fastcall *v37)(DWORD (__stdcall *)(DWORD, FAX_ENUM_DEVICE_ID_SOURCE, LPCWSTR, LPBYTE *, LPDWORD), DWORD (__stdcall *)(HINSTANCE, DWORD, FAX_ENUM_DEVICE_ID_SOURCE, LPCWSTR, LPBYTE, DWORD), HANDLE (__stdcall *)(HINSTANCE, DWORD, FAX_ENUM_DEVICE_ID_SOURCE, LPCWSTR, PFAX_EXT_CONFIG_CHANGE), DWORD (__stdcall *)(HANDLE), void (__stdcall *)(void *), wchar_t *, size_t, wchar_t *); // rax
  int *v38; // rdx
  DWORD v39; // eax
  __int64 v40; // rcx
  __int64 v41; // r13
  __int64 v42; // rax
  __int64 v43; // r12
  __int64 v44; // rcx
  GUID *v45; // rax
  GUID *v46; // r15
  __int64 v47; // rcx
  unsigned __int16 *v48; // rax
  __int64 v49; // rax
  __int64 v50; // rcx
  unsigned __int16 *v51; // rax
  __int64 v52; // rax
  LPVOID *Data4; // rbx
  __int64 v54; // rcx
  unsigned __int16 *v55; // rax
  __int64 v56; // rax
  DWORD v57; // r13d
  const CHAR *v58; // rax
  CHAR *v59; // r13
  FARPROC v60; // rax
  GUID **v61; // rax
  _QWORD *v62; // r8
  __int64 v63; // r9
  unsigned int v64; // r10d
  _QWORD *v65; // rdx
  _QWORD *v66; // rcx
  int v67; // edx
  int v68; // r8d
  CHAR *v69; // r12
  CMapDeviceId *v70; // rcx
  __int64 v71; // rdx
  __int64 v72; // r9
  DWORD v73; // eax
  int v74; // eax
  unsigned __int16 *v75; // rbx
  int v76; // eax
  unsigned __int16 *v77; // r8
  HMODULE v78; // rcx
  void *v79; // rcx
  LPVOID *v80; // r14
  LPVOID *v81; // r15
  LPVOID *v82; // rbx
  __int64 *v83; // rax
  wchar_t *Filename; // [rsp+28h] [rbp-5E0h]
  size_t FilenameCount; // [rsp+30h] [rbp-5D8h]
  wchar_t *Ext; // [rsp+38h] [rbp-5D0h]
  unsigned int v88; // [rsp+50h] [rbp-5B8h]
  const CHAR *lpMem; // [rsp+58h] [rbp-5B0h]
  HMODULE hModule; // [rsp+68h] [rbp-5A0h]
  __int64 v91; // [rsp+70h] [rbp-598h]
  __int64 v92; // [rsp+78h] [rbp-590h]
  int v93; // [rsp+78h] [rbp-590h]
  unsigned int v94; // [rsp+80h] [rbp-588h]
  _QWORD *v96; // [rsp+A8h] [rbp-560h]
  _DWORD *v97; // [rsp+B0h] [rbp-558h]
  _QWORD *v99; // [rsp+E0h] [rbp-528h]
  __int128 v100; // [rsp+E8h] [rbp-520h] BYREF
  __int128 v101; // [rsp+F8h] [rbp-510h]
  __int128 v102; // [rsp+108h] [rbp-500h]
  int v103; // [rsp+120h] [rbp-4E8h] BYREF
  __int64 (__fastcall *v104)(int, const unsigned __int16 *, struct _GUID *); // [rsp+128h] [rbp-4E0h]
  __int64 (__fastcall *v105)(int, const unsigned __int16 *); // [rsp+130h] [rbp-4D8h]
  __int64 (__fastcall *v106)(int, int, unsigned __int16 *, unsigned int *); // [rsp+138h] [rbp-4D0h]
  __int64 (__fastcall *v107)(unsigned int, struct _GUID *, int (*)(unsigned int, struct _GUID *, struct _GUID *, const unsigned __int16 *, void *), void *); // [rsp+140h] [rbp-4C8h]
  __int64 (__fastcall *v108)(int, const unsigned __int16 *, unsigned __int8 *, unsigned int); // [rsp+148h] [rbp-4C0h]
  __int64 (__fastcall *v109)(); // [rsp+150h] [rbp-4B8h]
  __int64 (__fastcall *v110)(LPVOID); // [rsp+158h] [rbp-4B0h]
  __int64 v111; // [rsp+160h] [rbp-4A8h]
  int v112; // [rsp+170h] [rbp-498h]
  unsigned __int16 v113[14]; // [rsp+174h] [rbp-494h] BYREF
  int v114; // [rsp+190h] [rbp-478h]
  unsigned __int16 v115[14]; // [rsp+194h] [rbp-474h] BYREF
  int v116; // [rsp+1B0h] [rbp-458h]
  unsigned __int16 v117[14]; // [rsp+1B4h] [rbp-454h] BYREF
  wchar_t String1[256]; // [rsp+1D0h] [rbp-438h] BYREF
  wchar_t v119[256]; // [rsp+3D0h] [rbp-238h] BYREF

  v1 = a1;
  v100 = 0;
  v101 = 0;
  v102 = 0;
  memset_0(&v103, 0, 0x48u);
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids);
  }
  LODWORD(v100) = 48;
  *((_QWORD *)&v100 + 1) = FaxRouteAddFile;
  *(_QWORD *)&v101 = FaxRouteDeleteFile;
  *((_QWORD *)&v101 + 1) = FaxRouteGetFile;
  *(_QWORD *)&v102 = FaxRouteEnumFiles;
  *((_QWORD *)&v102 + 1) = FaxRouteModifyRoutingData;
  v103 = 72;
  v104 = FaxRouteAddFile;
  v105 = FaxRouteDeleteFile;
  v106 = FaxRouteGetFile;
  v107 = FaxRouteEnumFiles;
  v108 = FaxRouteModifyRoutingData;
  v109 = GetReceiptsConfiguration;
  v110 = FreeReceiptsConfiguration;
  v111 = *((_QWORD *)g_pFaxConfig + 12);
  v2 = 0;
  while ( 1 )
  {
    v94 = v2;
    if ( v2 >= *((_DWORD *)v1 + 6) )
      break;
    memset_0(String1, 0, sizeof(String1));
    memset_0(v119, 0, sizeof(v119));
    v3 = (_DWORD *)pMemAlloc(0x6A0u);
    v97 = v3;
    v4 = (__int64)v3;
    if ( !v3 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids,
          *(_QWORD *)(*((_QWORD *)v1 + 2) + 40LL * v2 + 8));
      }
      v5 = (__int64 *)((char *)a1 + 16);
      v6 = v2;
      goto LABEL_182;
    }
    v6 = v2;
    v88 = v2;
    memset_0(v3, 0, 0x690u);
    v96 = (_QWORD *)(v4 + 1680);
    v99 = (_QWORD *)(v4 + 1680);
    *(_QWORD *)(v4 + 1688) = v4 + 1680;
    *(_QWORD *)(v4 + 1680) = v4 + 1680;
    v7 = 40LL * v2;
    v91 = v7;
    v5 = (__int64 *)((char *)v1 + 16);
    v8 = &Class;
    if ( *(_QWORD *)(v7 + *v5) )
      v8 = *(const WCHAR **)(v7 + *v5);
    v9 = (WCHAR *)(v4 + 52);
    v92 = v4 + 52;
    v10 = 2147483646;
    v11 = 260;
    do
    {
      if ( !v10 )
        break;
      v12 = *v8;
      if ( !*v8 )
        break;
      ++v8;
      *v9++ = v12;
      --v10;
      --v11;
    }
    while ( v11 );
    v13 = v11 == 0 ? 0x8007007A : 0;
    v14 = v9 - 1;
    if ( v11 )
      v14 = v9;
    *v14 = 0;
    if ( !v11 )
      goto LABEL_47;
    v15 = &Class;
    if ( *(_QWORD *)(*v5 + v7 + 8) )
      v15 = *(const WCHAR **)(*v5 + v7 + 8);
    v16 = 2147483646;
    v17 = 260;
    v18 = (WCHAR *)(v4 + 572);
    do
    {
      if ( !v16 )
        break;
      v19 = *v15;
      if ( !*v15 )
        break;
      ++v15;
      *v18++ = v19;
      --v16;
      --v17;
    }
    while ( v17 );
    v13 = v17 == 0 ? 0x8007007A : 0;
    v20 = v18 - 1;
    if ( v17 )
      v20 = v18;
    *v20 = 0;
    if ( v17 )
    {
      v21 = &Class;
      if ( *(_QWORD *)(*v5 + v7 + 16) )
        v21 = *(const WCHAR **)(*v5 + v7 + 16);
      v22 = 2147483646;
      v23 = 260;
      v24 = (WCHAR *)(v4 + 1092);
      do
      {
        if ( !v22 )
          break;
        v25 = *v21;
        if ( !*v21 )
          break;
        ++v21;
        *v24++ = v25;
        --v22;
        --v23;
      }
      while ( v23 );
      v26 = v24 - 1;
      if ( v23 )
        v26 = v24;
      *v26 = 0;
      v13 = v23 == 0 ? 0x8007007A : 0;
      if ( v23 && _wsplitpath_s((const wchar_t *)(v4 + 572), 0, 0, 0, 0, String1, 0x100u, v119, 0x100u) )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids);
          v27 = WPP_GLOBAL_Control;
        }
        v13 = -2147467259;
      }
      else
      {
        v27 = WPP_GLOBAL_Control;
      }
    }
    else
    {
LABEL_47:
      v27 = WPP_GLOBAL_Control;
    }
    if ( v13 < 0 )
    {
      if ( v27 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v27 + 28) & 4) != 0 && *((_BYTE *)v27 + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)v27 + 2), 15, &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids, (unsigned int)v13);
      *(_DWORD *)(v4 + 24) = 6;
      if ( (v13 & 0x1FFF0000) == 0x70000 )
        v13 = (unsigned __int16)v13;
      goto LABEL_181;
    }
    if ( !_wcsicmp(String1, L"FXSROUTE") && !_wcsicmp(v119, L".DLL") )
      *(_DWORD *)(v4 + 1624) = 1;
    v28 = (_DWORD *)(v4 + 1624);
    if ( *(_DWORD *)(v4 + 1624) && !v111 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids,
          *(_QWORD *)(*v5 + v7 + 8));
      }
LABEL_64:
      v6 = v88;
      goto LABEL_182;
    }
    LibraryW = LoadLibraryW(*(LPCWSTR *)(*v5 + v7 + 8));
    hModule = LibraryW;
    if ( !LibraryW )
    {
      LastError = GetLastError();
      v13 = LastError;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          (unsigned int)&WPP_4d881010f3a23632d10eb614fe27c918_Traceguids,
          *(_QWORD *)(*v5 + v7 + 8),
          LastError);
      }
      *(_DWORD *)(v4 + 24) = 4;
      goto LABEL_180;
    }
    *(_QWORD *)(v4 + 16) = LibraryW;
    *(_DWORD *)(v4 + 32) = 20;
    FileVersion = GetFileVersion(*(LPCWSTR *)(*v5 + v7 + 8));
    if ( FileVersion
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        (unsigned int)&WPP_4d881010f3a23632d10eb614fe27c918_Traceguids,
        *(_QWORD *)(*v5 + v7 + 8),
        FileVersion);
    }
    v32 = (unsigned int (__fastcall **)(_QWORD, int *))(v4 + 1632);
    *(_QWORD *)(v4 + 1632) = GetProcAddress(hModule, "FaxRouteInitialize");
    *(_QWORD *)(v4 + 1640) = GetProcAddress(hModule, "FaxRouteGetRoutingInfo");
    *(_QWORD *)(v4 + 1648) = GetProcAddress(hModule, "FaxRouteSetRoutingInfo");
    *(_QWORD *)(v4 + 1656) = GetProcAddress(hModule, "FaxRouteDeviceEnable");
    ProcAddress = GetProcAddress(hModule, "FaxRouteDeviceChangeNotification");
    *(_QWORD *)(v4 + 1664) = ProcAddress;
    if ( !*(_QWORD *)(v4 + 1632)
      || !*(_QWORD *)(v4 + 1640)
      || !*(_QWORD *)(v4 + 1648)
      || !ProcAddress
      || !*(_QWORD *)(v4 + 1656) )
    {
      v73 = GetLastError();
      v13 = v73;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          (unsigned int)&WPP_4d881010f3a23632d10eb614fe27c918_Traceguids,
          *(_QWORD *)(*v5 + v7),
          v73);
      }
      *(_DWORD *)(v4 + 24) = 5;
      goto LABEL_180;
    }
    v34 = GetProcAddress(hModule, "FaxExtInitializeConfig");
    *(_QWORD *)(v4 + 1672) = v34;
    if ( !v34
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids, v92);
    }
    if ( *v28 )
      ProcessHeap = GetProcessHeap();
    else
      ProcessHeap = HeapCreate(0, 0x19000u, 0x200000u);
    *(_QWORD *)(v4 + 1616) = ProcessHeap;
    if ( !ProcessHeap )
    {
      v36 = GetLastError();
      v13 = v36;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids, v36);
      }
      goto LABEL_94;
    }
    v37 = *(__int64 (__fastcall **)(DWORD (__stdcall *)(DWORD, FAX_ENUM_DEVICE_ID_SOURCE, LPCWSTR, LPBYTE *, LPDWORD), DWORD (__stdcall *)(HINSTANCE, DWORD, FAX_ENUM_DEVICE_ID_SOURCE, LPCWSTR, LPBYTE, DWORD), HANDLE (__stdcall *)(HINSTANCE, DWORD, FAX_ENUM_DEVICE_ID_SOURCE, LPCWSTR, PFAX_EXT_CONFIG_CHANGE), DWORD (__stdcall *)(HANDLE), void (__stdcall *)(void *), wchar_t *, size_t, wchar_t *))(v4 + 1672);
    if ( v37 )
    {
      v13 = v37(
              FaxExtGetData,
              FaxExtSetData,
              FaxExtRegisterForEvents,
              FaxExtUnregisterForEvents,
              MIDL_user_free,
              Filename,
              FilenameCount,
              Ext);
      if ( v13 < 0 )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_DS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            (unsigned int)&WPP_4d881010f3a23632d10eb614fe27c918_Traceguids,
            v13,
            v92);
        }
        *(_DWORD *)(v4 + 24) = 6;
        goto LABEL_180;
      }
      v32 = (unsigned int (__fastcall **)(_QWORD, int *))(v4 + 1632);
    }
    v38 = &v103;
    if ( !*v28 )
      v38 = (int *)&v100;
    v6 = v88;
    if ( !(*v32)(*(_QWORD *)(v4 + 1616), v38) )
    {
      v39 = GetLastError();
      v13 = v39;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids, v39);
      }
      *(_DWORD *)(v4 + 24) = 6;
      goto LABEL_181;
    }
    v40 = *v5;
    v41 = v7;
    if ( *(_DWORD *)(*v5 + v7 + 24) )
    {
      v42 = 0;
      v93 = 0;
      do
      {
        v43 = 5 * v42;
        if ( _wcsicmp(
               *(const wchar_t **)(*(_QWORD *)(v40 + v41 + 32) + 40 * v42 + 16),
               L"{6bbf7bfe-9af2-11d0-abf7-00c04fd91a4e}")
          || (unsigned int)IsServerSku(v44) )
        {
          v45 = (GUID *)pMemAlloc(0x60u);
          v46 = v45;
          if ( !v45 )
          {
            v13 = GetLastError();
            if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                25,
                &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids,
                *(_QWORD *)(*(_QWORD *)(*v5 + v41 + 32) + 8 * v43 + 8));
            }
LABEL_94:
            *(_DWORD *)(v4 + 24) = 1;
LABEL_180:
            v6 = v88;
LABEL_181:
            *(_DWORD *)(v4 + 28) = v13;
LABEL_182:
            if ( v4 )
            {
              v112 = *(_DWORD *)(v4 + 28);
              v113[0] = 0;
              v74 = StringCchPrintfW(v113, 0xCu, L"%ld");
              v75 = v113;
            }
            else
            {
              v114 = 14;
              v115[0] = 0;
              v74 = StringCchPrintfW(v115, 0xCu, L"%ld", 14);
              v75 = v115;
            }
            if ( v74 < 0 )
              v75 = 0;
            if ( v4 )
            {
              v116 = *(_DWORD *)(v4 + 24);
              v117[0] = 0;
              v76 = StringCchPrintfW(v117, 0xCu, L"%ld");
              v77 = v117;
              if ( v76 < 0 )
                v77 = 0;
            }
            else
            {
              v77 = 0;
            }
            Ext = v75;
            FilenameCount = (size_t)v77;
            Filename = *(wchar_t **)(*v5 + 40LL * v6 + 8);
            FaxLog(1, 1, 4, 3221257508LL);
            if ( v4 )
            {
              v78 = *(HMODULE *)(v4 + 16);
              if ( v78 )
              {
                FreeLibrary(v78);
                *(_QWORD *)(v4 + 16) = 0;
              }
              v79 = *(void **)(v4 + 1616);
              if ( v79 && !*(_DWORD *)(v4 + 1624) )
              {
                HeapDestroy(v79);
                *(_QWORD *)(v4 + 1616) = 0;
              }
              v80 = (LPVOID *)(v4 + 1680);
              v81 = *(LPVOID **)(v4 + 1680);
              while ( v81 != v80 )
              {
                v82 = v81;
                v81 = (LPVOID *)*v81;
                pMemFree(v82[8]);
                pMemFree(v82[7]);
                pMemFree(v82[9]);
                pMemFree(v82);
              }
              *(_QWORD *)(v4 + 1688) = v80;
              *v80 = v80;
              goto LABEL_202;
            }
            goto LABEL_204;
          }
          memset_0(v45, 0, 0x58u);
          *(_QWORD *)v46[5].Data4 = v4;
          v46[3].Data1 = *(_DWORD *)(*(_QWORD *)(*v5 + v41 + 32) + 8 * v43 + 32);
          v47 = *(_QWORD *)(*v5 + v41 + 32);
          v48 = (unsigned __int16 *)&Class;
          if ( *(_QWORD *)(v47 + 8 * v43) )
            v48 = *(unsigned __int16 **)(v47 + 8 * v43);
          v49 = StringDup(v48);
          *(_QWORD *)&v46[4].Data1 = v49;
          if ( !v49 )
          {
            v57 = GetLastError();
            if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                26,
                &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids,
                *(_QWORD *)(*(_QWORD *)(*v5 + v91 + 32) + 8 * v43 + 8));
            }
            Data4 = (LPVOID *)v46[3].Data4;
LABEL_168:
            v69 = 0;
LABEL_169:
            *(_DWORD *)(v4 + 24) = 1;
LABEL_170:
            v97[7] = v57;
            pMemFree(*(LPVOID *)&v46[4].Data1);
            pMemFree(*Data4);
            pMemFree(*(LPVOID *)v46[4].Data4);
            pMemFree(v46);
            pMemFree(v69);
            goto LABEL_64;
          }
          v50 = *(_QWORD *)(*v5 + v41 + 32);
          v51 = (unsigned __int16 *)&Class;
          if ( *(_QWORD *)(v50 + 8 * v43 + 8) )
            v51 = *(unsigned __int16 **)(v50 + 8 * v43 + 8);
          v52 = StringDup(v51);
          Data4 = (LPVOID *)v46[3].Data4;
          *(_QWORD *)v46[3].Data4 = v52;
          if ( !v52 )
          {
            v57 = GetLastError();
            v70 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_168;
            }
            v71 = 27;
            v72 = *(_QWORD *)(*(_QWORD *)(*v5 + v91 + 32) + 8 * v43 + 8);
LABEL_158:
            WPP_SF_S(*((_QWORD *)v70 + 2), v71, &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids, v72);
            goto LABEL_168;
          }
          v54 = *(_QWORD *)(*v5 + v41 + 32);
          v55 = (unsigned __int16 *)&Class;
          if ( *(_QWORD *)(v54 + 8 * v43 + 24) )
            v55 = *(unsigned __int16 **)(v54 + 8 * v43 + 24);
          v56 = StringDup(v55);
          *(_QWORD *)v46[4].Data4 = v56;
          if ( !v56 )
          {
            v57 = GetLastError();
            v70 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_168;
            }
            v71 = 28;
            v72 = *(_QWORD *)(*(_QWORD *)(*v5 + v91 + 32) + 8 * v43 + 24);
            goto LABEL_158;
          }
          v57 = IIDFromString(*(LPCOLESTR *)(*(_QWORD *)(*v5 + v41 + 32) + 8 * v43 + 16), v46 + 2);
          if ( v57 )
          {
            if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                29,
                (unsigned int)&WPP_4d881010f3a23632d10eb614fe27c918_Traceguids,
                *(_QWORD *)(*(_QWORD *)(*v5 + v91 + 32) + 8 * v43 + 16),
                v57);
            }
            *(_DWORD *)(v4 + 24) = 2;
            v69 = 0;
            goto LABEL_170;
          }
          v58 = (const CHAR *)UnicodeStringToAnsiString((LPCWCH)*Data4);
          v59 = (CHAR *)v58;
          lpMem = v58;
          if ( !v58 )
          {
            v57 = GetLastError();
            if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                30,
                &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids,
                *Data4);
            }
            v69 = 0;
            goto LABEL_169;
          }
          v60 = GetProcAddress(hModule, v58);
          *(_QWORD *)&v46[5].Data1 = v60;
          if ( !v60 )
          {
            v57 = GetLastError();
            if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
            {
              v69 = (CHAR *)lpMem;
            }
            else
            {
              v69 = (CHAR *)lpMem;
              if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                WPP_SF_sl(*((_QWORD *)WPP_GLOBAL_Control + 2), v67, v68, (_DWORD)lpMem, v57);
            }
            *(_DWORD *)(v4 + 24) = 5;
            goto LABEL_170;
          }
          pMemFree(v59);
          v61 = *(GUID ***)(v4 + 1688);
          *(_QWORD *)&v46->Data1 = v96;
          *(_QWORD *)v46->Data4 = v61;
          *v61 = v46;
          *(_QWORD *)(v4 + 1688) = v46;
          v41 = v91;
        }
        else if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids);
        }
        v42 = (unsigned int)(v93 + 1);
        v93 = v42;
        v40 = *v5;
      }
      while ( (unsigned int)v42 < *(_DWORD *)(*v5 + v41 + 24) );
    }
    *(_QWORD *)(v4 + 24) = 0;
    v62 = (_QWORD *)*v96;
    if ( (_QWORD *)*v96 != v99 )
    {
      v63 = qword_1400A1588;
      v64 = g_dwCountRoutingMethods;
      do
      {
        v65 = v62;
        v62 = (_QWORD *)*v62;
        v66 = (_QWORD *)v63;
        v63 = (__int64)(v65 + 2);
        v65[2] = &g_lstRoutingMethods;
        v65[3] = v66;
        *v66 = v65 + 2;
        qword_1400A1588 = (__int64)(v65 + 2);
        ++v64;
      }
      while ( v62 != v99 );
      g_dwCountRoutingMethods = v64;
    }
LABEL_202:
    if ( v4 )
    {
      v83 = (__int64 *)qword_1400A1550;
      *(_QWORD *)v97 = &g_lstRoutingExtensions;
      *((_QWORD *)v97 + 1) = v83;
      *v83 = v4;
      qword_1400A1550 = v4;
    }
LABEL_204:
    v2 = v94 + 1;
    v1 = a1;
  }
  SortMethodPriorities();
  if ( !g_dwCountRoutingMethods
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids);
  }
  return 1;
}

```

## disassembly

```asm
0x140043484  mov     [rsp+arg_8], rbx
0x140043489  mov     [rsp+arg_10], rsi
0x14004348e  push    rdi
0x14004348f  push    r12
0x140043491  push    r13
0x140043493  push    r14
0x140043495  push    r15
0x140043497  sub     rsp, 5E0h
0x14004349e  mov     rax, cs:__security_cookie
0x1400434a5  xor     rax, rsp
0x1400434a8  mov     [rsp+608h+var_38], rax
0x1400434b0  mov     r14, rcx
0x1400434b3  mov     [rsp+608h+var_580], rcx
0x1400434bb  mov     [rsp+608h+var_568], rcx
0x1400434c3  mov     [rsp+608h+var_550], rcx
0x1400434cb  xor     edi, edi
0x1400434cd  mov     [rsp+608h+var_5A4], edi
0x1400434d1  xorps   xmm0, xmm0
0x1400434d4  movups  [rsp+608h+var_520], xmm0
0x1400434dc  movups  [rsp+608h+var_510], xmm0
0x1400434e4  movups  [rsp+608h+var_500], xmm0
0x1400434ec  lea     ebx, [rdi+48h]
0x1400434ef  mov     r8d, ebx; Size
0x1400434f2  xor     edx, edx; Val
0x1400434f4  lea     rcx, [rsp+608h+var_4E8]; void *
0x1400434fc  call    memset_0
0x140043501  lea     r13, WPP_GLOBAL_Control
0x140043508  mov     rcx, cs:WPP_GLOBAL_Control
0x14004350f  cmp     rcx, r13
0x140043512  jz      short loc_140043533
0x140043514  test    byte ptr [rcx+1Ch], 4
0x140043518  jz      short loc_140043533
0x14004351a  cmp     byte ptr [rcx+19h], 5
0x14004351e  jb      short loc_140043533
0x140043520  lea     edx, [rdi+0Ch]
0x140043523  lea     r8, WPP_4d881010f3a23632d10eb614fe27c918_Traceguids
0x14004352a  mov     rcx, [rcx+10h]
0x14004352e  call    WPP_SF_
0x140043533  mov     dword ptr [rsp+608h+var_520], 30h ; '0'
0x14004353e  lea     r9, ?FaxRouteAddFile@@YAJKPEBGPEAU_GUID@@@Z; FaxRouteAddFile(ulong,ushort const *,_GUID *)
0x140043545  mov     qword ptr [rsp+608h+var_520+8], r9
0x14004354d  lea     r8, ?FaxRouteDeleteFile@@YAJKPEBG@Z; FaxRouteDeleteFile(ulong,ushort const *)
0x140043554  mov     qword ptr [rsp+608h+var_510], r8
0x14004355c  lea     rdx, ?FaxRouteGetFile@@YAHKKPEAGPEAK@Z; FaxRouteGetFile(ulong,ulong,ushort *,ulong *)
0x140043563  mov     qword ptr [rsp+608h+var_510+8], rdx
0x14004356b  lea     rcx, ?FaxRouteEnumFiles@@YAHKPEAU_GUID@@P6AHK00PEBGPEAX@Z2@Z; FaxRouteEnumFiles(ulong,_GUID *,int (*)(ulong,_GUID *,_GUID *,ushort const *,void *),void *)
0x140043572  mov     qword ptr [rsp+608h+var_500], rcx
0x14004357a  lea     rax, ?FaxRouteModifyRoutingData@@YAHKPEBGPEAEK@Z; FaxRouteModifyRoutingData(ulong,ushort const *,uchar *,ulong)
0x140043581  mov     qword ptr [rsp+608h+var_500+8], rax
0x140043589  mov     [rsp+608h+var_4E8], ebx
0x140043590  mov     [rsp+608h+var_4E0], r9
0x140043598  mov     [rsp+608h+var_4D8], r8
0x1400435a0  mov     [rsp+608h+var_4D0], rdx
0x1400435a8  mov     [rsp+608h+var_4C8], rcx
0x1400435b0  mov     [rsp+608h+var_4C0], rax
0x1400435b8  lea     rax, GetReceiptsConfiguration
0x1400435bf  mov     [rsp+608h+var_4B8], rax
0x1400435c7  lea     rax, FreeReceiptsConfiguration
0x1400435ce  mov     [rsp+608h+var_4B0], rax
0x1400435d6  mov     rax, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x1400435dd  mov     rcx, [rax+60h]
0x1400435e1  mov     [rsp+608h+var_4A8], rcx
0x1400435e9  mov     ebx, edi
0x1400435eb  mov     [rsp+608h+var_588], ebx
0x1400435f2  cmp     ebx, [r14+18h]
0x1400435f6  jnb     loc_140044485
0x1400435fc  xor     edx, edx; Val
0x1400435fe  mov     r8d, 200h; Size
0x140043604  lea     rcx, [rsp+608h+String1]; void *
0x14004360c  call    memset_0
0x140043611  xor     edx, edx; Val
0x140043613  mov     r8d, 200h; Size
0x140043619  lea     rcx, [rsp+608h+var_238]; void *
0x140043621  call    memset_0
0x140043626  mov     ecx, 6A0h; dwBytes
0x14004362b  call    pMemAlloc
0x140043630  mov     [rsp+608h+var_558], rax
0x140043638  mov     rsi, rax
0x14004363b  mov     [rsp+608h+lpMem], rax
0x140043640  test    rax, rax
0x140043643  jnz     short loc_140043693
0x140043645  mov     rcx, cs:WPP_GLOBAL_Control
0x14004364c  cmp     rcx, r13
0x14004364f  jz      short loc_14004367F
0x140043651  test    byte ptr [rcx+1Ch], 4
0x140043655  jz      short loc_14004367F
0x140043657  cmp     byte ptr [rcx+19h], 2
0x14004365b  jb      short loc_14004367F
0x14004365d  mov     eax, ebx
0x14004365f  lea     r8, [rax+rax*4]
0x140043663  mov     r9, [r14+10h]
0x140043667  lea     edx, [rsi+0Dh]
0x14004366a  mov     r9, [r9+r8*8+8]
0x14004366f  lea     r8, WPP_4d881010f3a23632d10eb614fe27c918_Traceguids
0x140043676  mov     rcx, [rcx+10h]
0x14004367a  call    WPP_SF_S
0x14004367f  mov     r14, [rsp+608h+var_550]
0x140043687  add     r14, 10h
0x14004368b  mov     r12d, ebx
0x14004368e  jmp     loc_1400442C9
0x140043693  mov     r12d, ebx
0x140043696  mov     [rsp+608h+var_5B8], ebx
0x14004369a  xor     edx, edx; Val
0x14004369c  mov     r8d, 690h; Size
0x1400436a2  mov     rcx, rax; void *
0x1400436a5  call    memset_0
0x1400436aa  lea     rax, [rsi+690h]
0x1400436b1  mov     [rsp+608h+var_560], rax
0x1400436b9  mov     [rsp+608h+var_528], rax
0x1400436c1  mov     [rsi+698h], rax
0x1400436c8  mov     [rax], rax
0x1400436cb  mov     eax, ebx
0x1400436cd  lea     rcx, [rax+rax*4]
0x1400436d1  lea     r15, ds:0[rcx*8]
0x1400436d9  mov     [rsp+608h+var_598], r15
0x1400436de  add     r14, 10h
0x1400436e2  mov     [rsp+608h+var_570], r14
0x1400436ea  mov     rax, [r14]
0x1400436ed  lea     r8, Class
0x1400436f4  cmp     [r15+rax], rdi
0x1400436f8  cmovnz  r8, [r15+rax]
0x1400436fd  lea     rdx, [rsi+34h]
0x140043701  mov     [rsp+608h+var_590], rdx
0x140043706  mov     eax, 7FFFFFFEh
0x14004370b  mov     ecx, 104h
0x140043710  test    rax, rax
0x140043713  jz      short loc_140043734
0x140043715  movzx   r9d, word ptr [r8]
0x140043719  test    r9w, r9w
0x14004371d  jz      short loc_140043734
0x14004371f  add     r8, 2
0x140043723  mov     [rdx], r9w
0x140043727  add     rdx, 2
0x14004372b  dec     rax
0x14004372e  sub     rcx, 1
0x140043732  jnz     short loc_140043710
0x140043734  mov     rax, rcx
0x140043737  neg     rax
0x14004373a  sbb     ebx, ebx
0x14004373c  not     ebx
0x14004373e  and     ebx, 8007007Ah
0x140043744  lea     rax, [rdx-2]
0x140043748  test    rcx, rcx
0x14004374b  cmovnz  rax, rdx
0x14004374f  mov     [rax], di
0x140043752  jz      loc_1400438C8
0x140043758  mov     rax, [r14]
0x14004375b  lea     rdx, Class
0x140043762  cmp     [rax+r15+8], rdi
0x140043767  cmovnz  rdx, [rax+r15+8]
0x14004376d  lea     r10, [rsi+23Ch]
0x140043774  mov     eax, 7FFFFFFEh
0x140043779  mov     ecx, 104h
0x14004377e  mov     r8, r10
0x140043781  test    rax, rax
0x140043784  jz      short loc_1400437A5
0x140043786  movzx   r9d, word ptr [rdx]
0x14004378a  test    r9w, r9w
0x14004378e  jz      short loc_1400437A5
0x140043790  add     rdx, 2
0x140043794  mov     [r8], r9w
0x140043798  add     r8, 2
0x14004379c  dec     rax
0x14004379f  sub     rcx, 1
0x1400437a3  jnz     short loc_140043781
0x1400437a5  mov     rax, rcx
0x1400437a8  neg     rax
0x1400437ab  sbb     ebx, ebx
0x1400437ad  not     ebx
0x1400437af  and     ebx, 8007007Ah
0x1400437b5  lea     rax, [r8-2]
0x1400437b9  test    rcx, rcx
0x1400437bc  cmovnz  rax, r8
0x1400437c0  mov     [rax], di
0x1400437c3  jz      loc_1400438C8
0x1400437c9  mov     rax, [r14]
0x1400437cc  lea     rcx, Class
0x1400437d3  cmp     [rax+r15+10h], rdi
0x1400437d8  cmovnz  rcx, [rax+r15+10h]
0x1400437de  mov     eax, 7FFFFFFEh
0x1400437e3  mov     edx, 104h
0x1400437e8  lea     r8, [rsi+444h]
0x1400437ef  test    rax, rax
0x1400437f2  jz      short loc_140043813
0x1400437f4  movzx   r9d, word ptr [rcx]
0x1400437f8  test    r9w, r9w
0x1400437fc  jz      short loc_140043813
0x1400437fe  add     rcx, 2
0x140043802  mov     [r8], r9w
0x140043806  add     r8, 2
0x14004380a  dec     rax
0x14004380d  sub     rdx, 1
0x140043811  jnz     short loc_1400437EF
0x140043813  lea     rax, [r8-2]
0x140043817  test    rdx, rdx
0x14004381a  cmovnz  rax, r8
0x14004381e  mov     [rax], di
0x140043821  mov     rax, rdx
0x140043824  neg     rax
0x140043827  sbb     ebx, ebx
0x140043829  not     ebx
0x14004382b  and     ebx, 8007007Ah
0x140043831  mov     [rsp+608h+var_5A8], ebx
0x140043835  test    rdx, rdx
0x140043838  jz      loc_1400438BF
0x14004383e  mov     [rsp+608h+ExtCount], 100h; ExtCount
0x140043847  lea     rax, [rsp+608h+var_238]
0x14004384f  mov     [rsp+608h+Ext], rax; Ext
0x140043854  mov     [rsp+608h+FilenameCount], 100h; FilenameCount
0x14004385d  lea     rax, [rsp+608h+String1]
0x140043865  mov     [rsp+608h+Filename], rax; Filename
0x14004386a  mov     [rsp+608h+DirCount], rdi; DirCount
0x14004386f  xor     r9d, r9d; Dir
0x140043872  xor     r8d, r8d; DriveCount
0x140043875  xor     edx, edx; Drive
0x140043877  mov     rcx, r10; FullPath
0x14004387a  call    cs:__imp__wsplitpath_s
0x140043880  test    eax, eax
0x140043882  jz      short loc_1400438BF
0x140043884  mov     rcx, cs:WPP_GLOBAL_Control
0x14004388b  cmp     rcx, r13
0x14004388e  jz      short loc_1400438B8
0x140043890  test    byte ptr [rcx+1Ch], 4
0x140043894  jz      short loc_1400438B8
0x140043896  cmp     byte ptr [rcx+19h], 2
0x14004389a  jb      short loc_1400438B8
0x14004389c  mov     edx, 0Eh
0x1400438a1  lea     r8, WPP_4d881010f3a23632d10eb614fe27c918_Traceguids
0x1400438a8  mov     rcx, [rcx+10h]
0x1400438ac  call    WPP_SF_
0x1400438b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400438b8  mov     ebx, 80004005h
0x1400438bd  jmp     short loc_1400438CF
0x1400438bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400438c6  jmp     short loc_1400438D3
0x1400438c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400438cf  mov     [rsp+608h+var_5A8], ebx
0x1400438d3  test    ebx, ebx
0x1400438d5  jns     short loc_140043921
0x1400438d7  cmp     rcx, r13
0x1400438da  jz      short loc_140043900
0x1400438dc  test    byte ptr [rcx+1Ch], 4
0x1400438e0  jz      short loc_140043900
0x1400438e2  cmp     byte ptr [rcx+19h], 2
0x1400438e6  jb      short loc_140043900
0x1400438e8  mov     edx, 0Fh
0x1400438ed  mov     r9d, ebx
0x1400438f0  lea     r8, WPP_4d881010f3a23632d10eb614fe27c918_Traceguids
0x1400438f7  mov     rcx, [rcx+10h]
0x1400438fb  call    WPP_SF_d
0x140043900  mov     dword ptr [rsi+18h], 6
0x140043907  mov     eax, ebx
0x140043909  and     eax, 1FFF0000h
0x14004390e  cmp     eax, 70000h
0x140043913  jnz     loc_1400442C6
0x140043919  movzx   ebx, bx
0x14004391c  jmp     loc_1400442C6
0x140043921  lea     rdx, aFxsroute; "FXSROUTE"
0x140043928  lea     rcx, [rsp+608h+String1]; String1
0x140043930  call    cs:__imp__wcsicmp
0x140043936  test    eax, eax
0x140043938  jnz     short loc_14004395D
0x14004393a  lea     rdx, aDll; ".DLL"
0x140043941  lea     rcx, [rsp+608h+var_238]; String1
0x140043949  call    cs:__imp__wcsicmp
0x14004394f  test    eax, eax
0x140043951  jnz     short loc_14004395D
0x140043953  mov     dword ptr [rsi+658h], 1
0x14004395d  lea     r12, [rsi+658h]
0x140043964  cmp     [r12], edi
0x140043968  jz      short loc_1400439B3
0x14004396a  cmp     [rsp+608h+var_4A8], rdi
0x140043972  jnz     short loc_1400439B3
0x140043974  mov     rcx, cs:WPP_GLOBAL_Control
0x14004397b  cmp     rcx, r13
0x14004397e  jz      short loc_1400439A9
0x140043980  test    byte ptr [rcx+1Ch], 4
0x140043984  jz      short loc_1400439A9
0x140043986  cmp     byte ptr [rcx+19h], 2
0x14004398a  jb      short loc_1400439A9
0x14004398c  mov     r9, [r14]
0x14004398f  mov     edx, 10h
0x140043994  mov     r9, [r9+r15+8]
0x140043999  lea     r8, WPP_4d881010f3a23632d10eb614fe27c918_Traceguids
0x1400439a0  mov     rcx, [rcx+10h]
0x1400439a4  call    WPP_SF_S
0x1400439a9  mov     r12d, [rsp+608h+var_5B8]
0x1400439ae  jmp     loc_1400442C9
0x1400439b3  mov     rcx, [r14]
0x1400439b6  mov     rcx, [rcx+r15+8]; lpLibFileName
0x1400439bb  call    cs:__imp_LoadLibraryW
0x1400439c1  mov     [rsp+608h+hModule], rax
0x1400439c6  test    rax, rax
0x1400439c9  jnz     short loc_140043A18
0x1400439cb  call    cs:__imp_GetLastError
0x1400439d1  mov     ebx, eax
0x1400439d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400439da  cmp     rcx, r13
0x1400439dd  jz      short loc_140043A0C
0x1400439df  test    byte ptr [rcx+1Ch], 4
  ... truncated ...
```
