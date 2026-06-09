# CDataCollectorSet::Connect(ushort *,ushort *,int)

- ea: `0x18000ef20`
- end: `0x18001000a`
- name: `?Connect@CDataCollectorSet@@MEAAJPEAG0H@Z`
- size: `4330`
- prototype: `__int64 __fastcall(CDataCollectorSet *this, unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18000ef20`
- `0x1800106d0`
- `0x180012ef0`
- `0x180026850`
- `0x18002b3a0`
- `0x180074cf0`
- `0x18007d980`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000f050`
- `msvcrt!_wcsnicmp` at `0x18000f050`
- `msvcrt!_wcsicmp` at `0x18000f450`
- `msvcrt!_wcsicmp` at `0x18000fe4c`
- `msvcrt!_wcsicmp` at `0x18000f450`
- `msvcrt!_wcsicmp` at `0x18000fe4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe8f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f0c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f113`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f15a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f0c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f113`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f15a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f0ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f796`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ff0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ff1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ff2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f0ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f796`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ff0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ff1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ff2c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18000fe85`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18000fe85`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x18000fee4`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x18000fee4`
- `OLEAUT32!__imp_VariantInit` at `0x18000ef9f`
- `OLEAUT32!__imp_VariantInit` at `0x18000efad`
- `OLEAUT32!__imp_VariantInit` at `0x18000efbb`
- `OLEAUT32!__imp_VariantInit` at `0x18000ef9f`
- `OLEAUT32!__imp_VariantInit` at `0x18000efad`
- `OLEAUT32!__imp_VariantInit` at `0x18000efbb`
- `OLEAUT32!__imp_VariantClear` at `0x18000f276`
- `OLEAUT32!__imp_VariantClear` at `0x18000f284`
- `OLEAUT32!__imp_VariantClear` at `0x18000f292`
- `OLEAUT32!__imp_VariantClear` at `0x18000f276`
- `OLEAUT32!__imp_VariantClear` at `0x18000f284`
- `OLEAUT32!__imp_VariantClear` at `0x18000f292`

## string_xrefs

- `0x18000f10c`: `System\CurrentControlSet\Services\SysmonLog`
- `0x18000f153`: `SOFTWARE\CLASSES\CLSID\{9a5dd473-d410-11d1-b829-00c04f94c7c3}`
- `0x18000f0bf`: `System\CurrentControlSet\Services\PLA`
- `0x18000efe7`: `service\`

## pseudocode

```c
__int64 __fastcall CDataCollectorSet::Connect(
        CDataCollectorSet *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        int a4)
{
  int v4; // r12d
  int v6; // esi
  unsigned int v7; // edi
  const wchar_t *v10; // rax
  const wchar_t **v11; // rbx
  size_t v12; // r8
  BOOL v13; // r15d
  LSTATUS v14; // eax
  bool v15; // sf
  LSTATUS v16; // eax
  bool v17; // sf
  LSTATUS v18; // eax
  bool v19; // sf
  int ServerCapsNoRegistry; // ebx
  __int64 v21; // rax
  int v22; // eax
  _QWORD *v23; // rsi
  _QWORD *v24; // r15
  __int64 v25; // rdi
  int v26; // eax
  unsigned int v28; // eax
  int v29; // eax
  __int64 v30; // rcx
  int v31; // eax
  int v32; // eax
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // rax
  bool v36; // zf
  int v37; // ebx
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rax
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v56; // rax
  WCHAR *v57; // rax
  WCHAR *v58; // r12
  DWORD LastError; // eax
  signed int v60; // eax
  unsigned __int16 *i; // rdx
  LSTATUS v62; // eax
  signed int v63; // eax
  int v64; // eax
  int v65; // eax
  int IsEqualServer; // eax
  int phkResult; // [rsp+20h] [rbp-E0h]
  int v68; // [rsp+70h] [rbp-90h] BYREF
  int v69; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v70; // [rsp+80h] [rbp-80h] BYREF
  DWORD nSize; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v72; // [rsp+90h] [rbp-70h] BYREF
  HKEY v73; // [rsp+98h] [rbp-68h] BYREF
  int v74; // [rsp+A0h] [rbp-60h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v76; // [rsp+B0h] [rbp-50h] BYREF
  VARIANTARG pvarg; // [rsp+B8h] [rbp-48h] BYREF
  VARIANTARG v78; // [rsp+D0h] [rbp-30h] BYREF
  VARIANTARG v79; // [rsp+E8h] [rbp-18h] BYREF
  const wchar_t *v80; // [rsp+100h] [rbp+0h] BYREF
  int v81; // [rsp+108h] [rbp+8h]
  const wchar_t *v82; // [rsp+110h] [rbp+10h]
  int v83; // [rsp+118h] [rbp+18h]
  const wchar_t *v84; // [rsp+120h] [rbp+20h]
  int v85; // [rsp+128h] [rbp+28h]
  const wchar_t *v86; // [rsp+130h] [rbp+30h]
  int v87; // [rsp+138h] [rbp+38h]
  const wchar_t *v88; // [rsp+140h] [rbp+40h]
  int v89; // [rsp+148h] [rbp+48h]
  __int64 v90; // [rsp+150h] [rbp+50h]
  int v91; // [rsp+158h] [rbp+58h]
  __int128 v92; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 v93[64]; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int16 v94[64]; // [rsp+1F0h] [rbp+F0h] BYREF
  unsigned __int16 v95[64]; // [rsp+270h] [rbp+170h] BYREF
  unsigned __int16 v96[64]; // [rsp+2F0h] [rbp+1F0h] BYREF
  unsigned __int16 v97[64]; // [rsp+370h] [rbp+270h] BYREF
  unsigned __int16 v98[64]; // [rsp+3F0h] [rbp+2F0h] BYREF
  unsigned __int16 v99[64]; // [rsp+470h] [rbp+370h] BYREF
  unsigned __int16 v100[64]; // [rsp+4F0h] [rbp+3F0h] BYREF
  unsigned __int16 v101[64]; // [rsp+570h] [rbp+470h] BYREF
  unsigned __int16 v102[64]; // [rsp+5F0h] [rbp+4F0h] BYREF
  unsigned __int16 v103[64]; // [rsp+670h] [rbp+570h] BYREF
  unsigned __int16 v104[64]; // [rsp+6F0h] [rbp+5F0h] BYREF
  unsigned __int16 v105[64]; // [rsp+770h] [rbp+670h] BYREF

  v4 = 0;
  v69 = a4;
  v70 = 0;
  v72 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v6 = 0;
  v7 = 0;
  memset(&v79, 0, sizeof(v79));
  v74 = 0;
  memset(&v78, 0, sizeof(v78));
  v76 = 0;
  v92 = 0;
  VariantInit(&pvarg);
  pvarg.llVal = 0;
  VariantInit(&v79);
  v79.llVal = 0;
  VariantInit(&v78);
  v78.llVal = 0;
  if ( a2 )
  {
    v81 = 268435466;
    v82 = L"system\\";
    v10 = L"session\\";
    v80 = L"session\\";
    v84 = L"service\\";
    v11 = &v80;
    v83 = 268435460;
    v86 = L"autosession\\";
    v88 = L"legacy\\";
    v85 = 268435473;
    v87 = 268435488;
    v89 = 268435472;
    v90 = 0;
    v91 = 268435515;
    do
    {
      v12 = -1;
      do
        ++v12;
      while ( v10[v12] );
      if ( !_wcsnicmp(v10, a2, v12) )
        break;
      v10 = v11[2];
      v11 += 2;
    }
    while ( v10 );
    v6 = *((_DWORD *)v11 + 2);
  }
  hKey = 0;
  v13 = 1;
  v73 = 0;
  nSize = 16;
  if ( !a3 || !*a3 || !_wcsicmp(a3, L".") )
    goto LABEL_10;
  v57 = (WCHAR *)PlaiAlloc(2LL * nSize, 1, 0, qword_180147320, phkResult);
  v58 = v57;
  if ( !v57 )
  {
    v4 = 0;
    ServerCapsNoRegistry = -2147024882;
    v70 = 0;
    v68 = -2147024882;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v93, 0x4000000000000800uLL);
      v38 = -1;
      do
        v36 = v93[++v38] == 0;
      while ( !v36 );
      EventingWriteEvent(&g_Eventing, PLA_EVENT_ERROR, 5, &v68, 4, qword_180147320, 1, &v70, 4, "PlaiIsLocalServer", 18);
    }
    goto LABEL_119;
  }
  if ( !GetComputerNameW(v57, &nSize) )
  {
    LastError = GetLastError();
    v60 = PlaiHResultFromWin32(LastError);
    ServerCapsNoRegistry = v60;
    if ( v60 < 0 )
    {
      v68 = 0;
      v70 = v60;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v94, 0x4000000000000800uLL);
        v39 = -1;
        do
          v36 = v94[++v39] == 0;
        while ( !v36 );
        EventingWriteEvent(
          &g_Eventing,
          PLA_EVENT_ERROR,
          5,
          &v70,
          4,
          qword_180147320,
          1,
          &v68,
          4,
          "PlaiIsLocalServer",
          18);
      }
      PlaiFree(v58, 1);
      v4 = 0;
LABEL_119:
      v68 = 0;
      nSize = ServerCapsNoRegistry;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v95, 0x4000000000000800uLL);
        v40 = -1;
        do
          v36 = v95[++v40] == 0;
        while ( !v36 );
        EventingWriteEvent(
          &g_Eventing,
          PLA_EVENT_ERROR,
          5,
          &nSize,
          4,
          qword_180147320,
          1,
          &v68,
          4,
          "PlaGetServerCapabilities",
          25);
      }
LABEL_34:
      if ( v13 )
        goto LABEL_35;
      goto LABEL_83;
    }
  }
  for ( i = a3; *i == 92; ++i )
    ;
  v37 = _wcsicmp(v58, i);
  v13 = v37 == 0;
  PlaiFree(v58, 1);
  if ( !v37 )
  {
    v4 = 0;
LABEL_10:
    v7 = 0x10000000;
    hKey = HKEY_LOCAL_MACHINE;
LABEL_11:
    if ( v73 )
    {
      RegCloseKey(v73);
      v73 = 0;
    }
    v14 = RegOpenKeyExW(hKey, L"System\\CurrentControlSet\\Services\\PLA", 0, 0x20019u, &v73);
    v15 = v14 < 0;
    if ( !v14 )
      goto LABEL_14;
    if ( v14 > 0 )
      v15 = 1;
    if ( !v15 )
LABEL_14:
      v7 |= 0x27u;
    if ( v73 )
    {
      RegCloseKey(v73);
      v73 = 0;
    }
    v16 = RegOpenKeyExW(hKey, L"System\\CurrentControlSet\\Services\\SysmonLog", 0, 0x20019u, &v73);
    v17 = v16 < 0;
    if ( !v16 )
      goto LABEL_21;
    if ( v16 > 0 )
      v17 = 1;
    if ( !v17 )
LABEL_21:
      v7 |= 0x10u;
    if ( v73 )
    {
      RegCloseKey(v73);
      v73 = 0;
    }
    v18 = RegOpenKeyExW(hKey, L"SOFTWARE\\CLASSES\\CLSID\\{9a5dd473-d410-11d1-b829-00c04f94c7c3}", 0, 0x20019u, &v73);
    v19 = v18 < 0;
    if ( !v18 )
      goto LABEL_28;
    if ( v18 > 0 )
      v19 = 1;
    if ( !v19 )
LABEL_28:
      v7 |= 8u;
    ServerCapsNoRegistry = 0;
    if ( !v7 )
      ServerCapsNoRegistry = -2147467262;
    goto LABEL_34;
  }
  ServerCapsNoRegistry = PlaiGetServerCapsNoRegistry(a3, &v70);
  if ( ServerCapsNoRegistry >= 0 )
  {
    v7 = v70;
    v4 = 0;
  }
  else
  {
    v62 = RegConnectRegistryW(a3, HKEY_LOCAL_MACHINE, &hKey);
    v63 = PlaiHResultFromWin32(v62);
    v4 = 0;
    ServerCapsNoRegistry = v63;
    if ( v63 >= 0 )
      goto LABEL_11;
    v68 = 0;
    nSize = v63;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v96, 0x4000000000000800uLL);
      v41 = -1;
      do
        v36 = v96[++v41] == 0;
      while ( !v36 );
      EventingWriteEvent(
        &g_Eventing,
        PLA_EVENT_ERROR,
        5,
        &nSize,
        4,
        qword_180147320,
        1,
        &v68,
        4,
        "PlaGetServerCapabilities",
        25);
    }
    v7 = v70;
  }
LABEL_83:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
LABEL_35:
  if ( v73 )
    RegCloseKey(v73);
  if ( ServerCapsNoRegistry < 0 )
  {
    v68 = 0;
    v74 = ServerCapsNoRegistry;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v97, 0x4000000000000800uLL);
      v42 = -1;
      do
        v36 = v97[++v42] == 0;
      while ( !v36 );
      EventingWriteEvent(
        &g_Eventing,
        PLA_EVENT_ERROR,
        5,
        &v74,
        4,
        qword_180147320,
        1,
        &v68,
        4,
        "CDataCollectorSet::Connect",
        27);
    }
  }
  else
  {
    if ( v6 )
      v7 &= v6;
    v21 = *(_QWORD *)this;
    if ( v69 )
    {
      v22 = (*(__int64 (__fastcall **)(CDataCollectorSet *, _QWORD, __int128 *, unsigned int *))(v21 + 560))(
              this,
              v7,
              &v92,
              &v72);
      ServerCapsNoRegistry = v22;
      if ( v22 < 0 )
      {
        v69 = 0;
        v68 = v22;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_50;
        }
        PlaiWhoAmI(v98, 0x4000000000000800uLL);
        v43 = -1;
        do
          v36 = v98[++v43] == 0;
        while ( !v36 );
        goto LABEL_92;
      }
    }
    else
    {
      v64 = (*(__int64 (__fastcall **)(CDataCollectorSet *, _QWORD, __int128 *, unsigned int *))(v21 + 552))(
              this,
              v7,
              &v92,
              &v72);
      ServerCapsNoRegistry = v64;
      if ( v64 < 0 )
      {
        v69 = 0;
        v68 = v64;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_50;
        }
        PlaiWhoAmI(v99, 0x4000000000000800uLL);
        v44 = -1;
        do
          v36 = v99[++v44] == 0;
        while ( !v36 );
        goto LABEL_92;
      }
    }
    v23 = (_QWORD *)((char *)this + 80);
    v24 = (_QWORD *)((char *)this + 88);
    if ( !*((_QWORD *)this + 10) )
      goto LABEL_43;
    v50 = *v24 - v92;
    if ( *v24 == (_QWORD)v92 )
      v50 = *((_QWORD *)this + 12) - *((_QWORD *)&v92 + 1);
    if ( v50 )
      goto LABEL_140;
    v51 = *v24 - *(_QWORD *)&CLSID_LegacyDataCollectorSet.Data1;
    if ( *v24 == *(_QWORD *)&CLSID_LegacyDataCollectorSet.Data1 )
      v51 = *((_QWORD *)this + 12) - *(_QWORD *)CLSID_LegacyDataCollectorSet.Data4;
    if ( v51 )
    {
      v52 = *v24 - *(_QWORD *)&CLSID_LegacyTraceSession.Data1;
      if ( *v24 == *(_QWORD *)&CLSID_LegacyTraceSession.Data1 )
        v52 = *((_QWORD *)this + 12) - *(_QWORD *)CLSID_LegacyTraceSession.Data4;
      if ( v52 )
      {
        v53 = *v24 - *(_QWORD *)&CLSID_TraceSession.Data1;
        if ( *v24 == *(_QWORD *)&CLSID_TraceSession.Data1 )
          v53 = *((_QWORD *)this + 12) - *(_QWORD *)CLSID_TraceSession.Data4;
        if ( v53 )
        {
          v54 = *v24 - *(_QWORD *)&CLSID_BootTraceSession.Data1;
          if ( *v24 == *(_QWORD *)&CLSID_BootTraceSession.Data1 )
            v54 = *((_QWORD *)this + 12) - *(_QWORD *)CLSID_BootTraceSession.Data4;
          if ( v54 )
          {
            v55 = *v24 - *(_QWORD *)&CLSID_ServerDataCollectorSet.Data1;
            if ( *v24 == *(_QWORD *)&CLSID_ServerDataCollectorSet.Data1 )
              v55 = *((_QWORD *)this + 12) - *(_QWORD *)CLSID_ServerDataCollectorSet.Data4;
            if ( v55 )
            {
              v56 = *v24 - *(_QWORD *)&CLSID_SystemDataCollectorSet.Data1;
              if ( *v24 == *(_QWORD *)&CLSID_SystemDataCollectorSet.Data1 )
                v56 = *((_QWORD *)this + 12) - *(_QWORD *)CLSID_SystemDataCollectorSet.Data4;
              if ( v56 )
              {
                ServerCapsNoRegistry = -2147418113;
                goto LABEL_50;
              }
            }
          }
        }
        if ( *((_DWORD *)this + 26) != v72 )
        {
LABEL_140:
          v4 = 1;
          goto LABEL_43;
        }
        if ( (v7 & 0x10000000) != 0 )
          goto LABEL_50;
        PlaiVariantClear(&v79);
        v65 = (*(__int64 (__fastcall **)(CDataCollectorSet *, CY *))(*(_QWORD *)this + 256LL))(this, &v79.cyVal);
        ServerCapsNoRegistry = v65;
        if ( v65 < 0 )
        {
          v69 = 0;
          v68 = v65;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_50;
          }
          PlaiWhoAmI(v100, 0x4000000000000800uLL);
          v45 = -1;
          do
            v36 = v100[++v45] == 0;
          while ( !v36 );
        }
        else
        {
          v79.vt = 8;
          IsEqualServer = PlaiIsEqualServer(a3, v79.bstrVal, &v74);
          ServerCapsNoRegistry = IsEqualServer;
          if ( IsEqualServer >= 0 )
          {
            LOBYTE(v4) = v74 == 0;
            if ( !v4 )
              goto LABEL_50;
LABEL_43:
            v25 = *v23;
            if ( *v23 )
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v25 + 8LL))(*v23);
            v26 = (**((__int64 (__fastcall ***)(char *, unsigned __int16 *, _QWORD, __int128 *, GUID *, char *))this + 9))(
                    (char *)this + 72,
                    a3,
                    v72,
                    &v92,
                    &IID_IDataCollectorSet,
                    (char *)this + 80);
            ServerCapsNoRegistry = v26;
            if ( v26 >= 0 )
            {
              v28 = v72;
              *(_OWORD *)v24 = v92;
              *((_DWORD *)this + 26) = v28;
              if ( !v4 )
                goto LABEL_48;
              PlaiVariantClear(&pvarg);
              v29 = (*(__int64 (__fastcall **)(__int64, CY *))(*(_QWORD *)v25 + 416LL))(v25, &pvarg.cyVal);
              ServerCapsNoRegistry = v29;
              if ( v29 < 0 )
              {
                v69 = 0;
                v68 = v29;
                if ( (_DWORD)xmmword_180169738
                  && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                  && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                {
                  PlaiWhoAmI(v103, 0x4000000000000800uLL);
                  v47 = -1;
                  do
                    v36 = v103[++v47] == 0;
                  while ( !v36 );
                  goto LABEL_62;
                }
              }
              else
              {
                v30 = *v23;
                pvarg.vt = 8;
                v31 = (*(__int64 (__fastcall **)(__int64, LONGLONG, __int64 *))(*(_QWORD *)v30 + 512LL))(
                        v30,
                        pvarg.llVal,
                        &v76);
                ServerCapsNoRegistry = v31;
                if ( v31 < 0 )
                {
                  v69 = 0;
                  v68 = v31;
                  if ( (_DWORD)xmmword_180169738
                    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                  {
                    PlaiWhoAmI(v104, 0x4000000000000800uLL);
                    v48 = -1;
                    do
                      v36 = v104[++v48] == 0;
                    while ( !v36 );
                    goto LABEL_62;
                  }
                }
                else
                {
                  if ( !*((_DWORD *)this + 27) )
                    goto LABEL_48;
                  PlaiVariantClear(&v78);
                  v32 = (*(__int64 (__fastcall **)(__int64, CY *))(*(_QWORD *)v25 + 408LL))(v25, &v78.cyVal);
                  ServerCapsNoRegistry = v32;
                  if ( v32 >= 0 )
                  {
                    v33 = *v23;
                    v34 = *((_QWORD *)this + 14);
                    v78.vt = 8;
                    ServerCapsNoRegistry = (*(__int64 (__fastcall **)(__int64, LONGLONG, __int64))(*(_QWORD *)v33 + 464LL))(
                                             v33,
                                             v78.llVal,
                                             v34);
                    goto LABEL_48;
                  }
                  v69 = 0;
                  v68 = v32;
                  if ( (_DWORD)xmmword_180169738
                    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                  {
                    PlaiWhoAmI(v105, 0x4000000000000800uLL);
                    v49 = -1;
                    do
                      v36 = v105[++v49] == 0;
                    while ( !v36 );
                    goto LABEL_62;
                  }
                }
              }
            }
            else
            {
              v69 = 0;
              v68 = v26;
              if ( (_DWORD)xmmword_180169738
                && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
              {
                PlaiWhoAmI(v102, 0x4000000000000800uLL);
                v35 = -1;
                do
                  v36 = v102[++v35] == 0;
                while ( !v36 );
LABEL_62:
                EventingWriteEvent(
                  &g_Eventing,
                  PLA_EVENT_ERROR,
                  5,
                  &v68,
                  4,
                  qword_180147320,
                  1,
                  &v69,
                  4,
                  "CDataCollectorSet::Connect",
                  27);
              }
            }
LABEL_48:
            if ( v25 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
            goto LABEL_50;
          }
          v69 = 0;
          v68 = IsEqualServer;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_50;
          }
          PlaiWhoAmI(v101, 0x4000000000000800uLL);
          v46 = -1;
          do
            v36 = v101[++v46] == 0;
          while ( !v36 );
        }
LABEL_92:
        EventingWriteEvent(
          &g_Eventing,
          PLA_EVENT_ERROR,
          5,
          &v68,
          4,
          qword_180147320,
          1,
          &v69,
          4,
          "CDataCollectorSet::Connect",
          27);
      }
    }
  }
LABEL_50:
  if ( v76 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
    v76 = 0;
  }
  VariantClear(&pvarg);
  pvarg.llVal = 0;
  VariantClear(&v78);
  v78.llVal = 0;
  VariantClear(&v79);
  return (unsigned int)ServerCapsNoRegistry;
}

```

## disassembly

```asm
0x18000ef20  mov     [rsp-8+arg_18], rbx
0x18000ef25  push    rbp
0x18000ef26  push    rsi
0x18000ef27  push    rdi
0x18000ef28  push    r12
0x18000ef2a  push    r13
0x18000ef2c  push    r14
0x18000ef2e  push    r15
0x18000ef30  lea     rbp, [rsp-700h]
0x18000ef38  sub     rsp, 800h
0x18000ef3f  mov     rax, cs:__security_cookie
0x18000ef46  xor     rax, rsp
0x18000ef49  mov     [rbp+730h+var_40], rax
0x18000ef50  xor     r12d, r12d
0x18000ef53  mov     [rsp+830h+var_7B8], r9d
0x18000ef58  xorps   xmm0, xmm0
0x18000ef5b  mov     [rbp+730h+var_7B0], r12d
0x18000ef5f  xor     eax, eax
0x18000ef61  mov     [rbp+730h+var_7A0], r12d
0x18000ef65  mov     r14, rcx
0x18000ef68  mov     qword ptr [rbp+730h+pvarg+10h], rax
0x18000ef6c  xorps   xmm1, xmm1
0x18000ef6f  mov     qword ptr [rbp+730h+var_748+10h], rax
0x18000ef73  lea     rcx, [rbp+730h+pvarg]; pvarg
0x18000ef77  mov     qword ptr [rbp+730h+var_760+10h], rax
0x18000ef7b  movups  xmmword ptr [rbp+730h+pvarg], xmm0
0x18000ef7f  mov     esi, r12d
0x18000ef82  mov     edi, r12d
0x18000ef85  movups  xmmword ptr [rbp+730h+var_748], xmm1
0x18000ef89  mov     [rbp+730h+var_790], r12d
0x18000ef8d  mov     r13, r8
0x18000ef90  movups  xmmword ptr [rbp+730h+var_760], xmm0
0x18000ef94  mov     [rbp+730h+var_780], r12
0x18000ef98  mov     r15, rdx
0x18000ef9b  movups  [rbp+730h+var_6D0], xmm0
0x18000ef9f  call    cs:__imp_VariantInit
0x18000efa5  lea     rcx, [rbp+730h+var_748]; pvarg
0x18000efa9  mov     qword ptr [rbp+730h+pvarg+8], r12
0x18000efad  call    cs:__imp_VariantInit
0x18000efb3  lea     rcx, [rbp+730h+var_760]; pvarg
0x18000efb7  mov     qword ptr [rbp+730h+var_748+8], r12
0x18000efbb  call    cs:__imp_VariantInit
0x18000efc1  mov     qword ptr [rbp+730h+var_760+8], r12
0x18000efc5  test    r15, r15
0x18000efc8  jz      loc_18000F06A
0x18000efce  lea     rcx, aSystem; "system\\"
0x18000efd5  mov     [rbp+730h+var_728], 1000000Ah
0x18000efdc  mov     [rbp+730h+var_720], rcx
0x18000efe0  lea     rax, aSession; "session\\"
0x18000efe7  lea     rcx, aService; "service\\"
0x18000efee  mov     [rbp+730h+var_730], rax
0x18000eff2  mov     [rbp+730h+var_710], rcx
0x18000eff6  lea     rbx, [rbp+730h+var_730]
0x18000effa  lea     rcx, aAutosession; "autosession\\"
0x18000f001  mov     [rbp+730h+var_718], 10000004h
0x18000f008  mov     [rbp+730h+var_700], rcx
0x18000f00c  lea     rcx, aLegacy; "legacy\\"
0x18000f013  mov     [rbp+730h+var_6F0], rcx
0x18000f017  mov     [rbp+730h+var_708], 10000011h
0x18000f01e  mov     [rbp+730h+var_6F8], 10000020h
0x18000f025  mov     [rbp+730h+var_6E8], 10000010h
0x18000f02c  mov     [rbp+730h+var_6E0], r12
0x18000f030  mov     [rbp+730h+var_6D8], 1000003Bh
0x18000f037  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18000f03e  xchg    ax, ax
0x18000f040  inc     r8; MaxCount
0x18000f043  cmp     [rax+r8*2], si
0x18000f048  jnz     short loc_18000F040
0x18000f04a  mov     rdx, r15; String2
0x18000f04d  mov     rcx, rax; String1
0x18000f050  call    cs:__imp__wcsnicmp
0x18000f056  test    eax, eax
0x18000f058  jz      short loc_18000F067
0x18000f05a  mov     rax, [rbx+10h]
0x18000f05e  add     rbx, 10h
0x18000f062  test    rax, rax
0x18000f065  jnz     short loc_18000F037
0x18000f067  mov     esi, [rbx+8]
0x18000f06a  mov     [rbp+730h+hKey], r12
0x18000f06e  mov     r15d, 1
0x18000f074  mov     [rbp+730h+var_798], r12
0x18000f078  mov     [rbp+730h+nSize], 10h
0x18000f07f  test    r13, r13
0x18000f082  jz      short loc_18000F08F
0x18000f084  cmp     r12w, [r13+0]
0x18000f089  jnz     loc_18000FE42
0x18000f08f  mov     edi, 10000000h
0x18000f094  mov     [rbp+730h+hKey], 0FFFFFFFF80000002h
0x18000f09c  mov     rcx, [rbp+730h+var_798]; hKey
0x18000f0a0  test    rcx, rcx
0x18000f0a3  jnz     loc_18000FF0E
0x18000f0a9  mov     rcx, [rbp+730h+hKey]; hKey
0x18000f0ad  lea     rax, [rbp+730h+var_798]
0x18000f0b1  mov     r9d, 20019h; samDesired
0x18000f0b7  mov     [rsp+830h+phkResult], rax; phkResult
0x18000f0bc  xor     r8d, r8d; ulOptions
0x18000f0bf  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\PL"...
0x18000f0c6  call    cs:__imp_RegOpenKeyExW
0x18000f0cc  test    eax, eax
0x18000f0ce  jnz     short loc_18000F0D5
0x18000f0d0  or      edi, 27h
0x18000f0d3  jmp     short loc_18000F0E3
0x18000f0d5  jle     short loc_18000F0E1
0x18000f0d7  movzx   eax, ax
0x18000f0da  or      eax, 80070000h
0x18000f0df  test    eax, eax
0x18000f0e1  jns     short loc_18000F0D0
0x18000f0e3  mov     rcx, [rbp+730h+var_798]; hKey
0x18000f0e7  test    rcx, rcx
0x18000f0ea  jz      short loc_18000F0F6
0x18000f0ec  call    cs:__imp_RegCloseKey
0x18000f0f2  mov     [rbp+730h+var_798], r12
0x18000f0f6  mov     rcx, [rbp+730h+hKey]; hKey
0x18000f0fa  lea     rax, [rbp+730h+var_798]
0x18000f0fe  mov     r9d, 20019h; samDesired
0x18000f104  mov     [rsp+830h+phkResult], rax; phkResult
0x18000f109  xor     r8d, r8d; ulOptions
0x18000f10c  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Sy"...
0x18000f113  call    cs:__imp_RegOpenKeyExW
0x18000f119  test    eax, eax
0x18000f11b  jnz     short loc_18000F122
0x18000f11d  or      edi, 10h
0x18000f120  jmp     short loc_18000F130
0x18000f122  jle     short loc_18000F12E
0x18000f124  movzx   eax, ax
0x18000f127  or      eax, 80070000h
0x18000f12c  test    eax, eax
0x18000f12e  jns     short loc_18000F11D
0x18000f130  mov     rcx, [rbp+730h+var_798]; hKey
0x18000f134  test    rcx, rcx
0x18000f137  jnz     loc_18000FF1D
0x18000f13d  mov     rcx, [rbp+730h+hKey]; hKey
0x18000f141  lea     rax, [rbp+730h+var_798]
0x18000f145  mov     r9d, 20019h; samDesired
0x18000f14b  mov     [rsp+830h+phkResult], rax; phkResult
0x18000f150  xor     r8d, r8d; ulOptions
0x18000f153  lea     rdx, aSoftwareClasse; "SOFTWARE\\CLASSES\\CLSID\\{9a5dd473-d41"...
0x18000f15a  call    cs:__imp_RegOpenKeyExW
0x18000f160  test    eax, eax
0x18000f162  jnz     short loc_18000F169
0x18000f164  or      edi, 8
0x18000f167  jmp     short loc_18000F177
0x18000f169  jle     short loc_18000F175
0x18000f16b  movzx   eax, ax
0x18000f16e  or      eax, 80070000h
0x18000f173  test    eax, eax
0x18000f175  jns     short loc_18000F164
0x18000f177  test    edi, edi
0x18000f179  mov     ebx, r12d
0x18000f17c  mov     eax, 80004002h
0x18000f181  cmovz   ebx, eax
0x18000f184  test    r15d, r15d
0x18000f187  jz      loc_18000F789
0x18000f18d  mov     rcx, [rbp+730h+var_798]; hKey
0x18000f191  test    rcx, rcx
0x18000f194  jnz     loc_18000FF2C
0x18000f19a  test    ebx, ebx
0x18000f19c  js      loc_18000FBBF
0x18000f1a2  test    esi, esi
0x18000f1a4  jz      short loc_18000F1A8
0x18000f1a6  and     edi, esi
0x18000f1a8  cmp     [rsp+830h+var_7B8], 0
0x18000f1ad  lea     r9, [rbp+730h+var_7A0]
0x18000f1b1  mov     rax, [r14]
0x18000f1b4  lea     r8, [rbp+730h+var_6D0]
0x18000f1b8  mov     edx, edi
0x18000f1ba  mov     rcx, r14
0x18000f1bd  jz      loc_18000FF37
0x18000f1c3  mov     rax, [rax+230h]
0x18000f1ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1cf  mov     ebx, eax
0x18000f1d1  test    eax, eax
0x18000f1d3  js      loc_18000FBF0
0x18000f1d9  cmp     qword ptr [r14+50h], 0
0x18000f1de  lea     rsi, [r14+50h]
0x18000f1e2  lea     r15, [r14+58h]
0x18000f1e6  jnz     loc_18000FC54
0x18000f1ec  mov     rdi, [rsi]
0x18000f1ef  test    rdi, rdi
0x18000f1f2  jnz     loc_18000FFCB
0x18000f1f8  mov     rax, [r14+48h]
0x18000f1fc  lea     rcx, [r14+48h]
0x18000f200  mov     r8d, [rbp+730h+var_7A0]
0x18000f204  lea     rdx, IID_IDataCollectorSet
0x18000f20b  mov     [rsp+830h+var_808], rsi
0x18000f210  lea     r9, [rbp+730h+var_6D0]
0x18000f214  mov     [rsp+830h+phkResult], rdx
0x18000f219  mov     rdx, r13
0x18000f21c  mov     rax, [rax]
0x18000f21f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f224  mov     ebx, eax
0x18000f226  test    eax, eax
0x18000f228  jns     loc_18000F2C4
0x18000f22e  cmp     dword ptr cs:xmmword_180169738, 0
0x18000f235  mov     [rsp+830h+var_7B8], 0
0x18000f23d  mov     [rsp+830h+var_7C0], eax
0x18000f241  jz      short loc_18000F25A
0x18000f243  mov     rdx, 4000000000000800h; unsigned __int64
0x18000f24d  test    qword ptr cs:xmmword_180169738+8, rdx
0x18000f254  jnz     loc_18000F38A
0x18000f25a  test    rdi, rdi
0x18000f25d  jnz     loc_18000FFDF
0x18000f263  mov     rcx, [rbp+730h+var_780]
0x18000f267  test    rcx, rcx
0x18000f26a  jnz     loc_18000FFF3
0x18000f270  xor     edi, edi
0x18000f272  lea     rcx, [rbp+730h+pvarg]; pvarg
0x18000f276  call    cs:__imp_VariantClear
0x18000f27c  lea     rcx, [rbp+730h+var_760]; pvarg
0x18000f280  mov     qword ptr [rbp+730h+pvarg+8], rdi
0x18000f284  call    cs:__imp_VariantClear
0x18000f28a  lea     rcx, [rbp+730h+var_748]; pvarg
0x18000f28e  mov     qword ptr [rbp+730h+var_760+8], rdi
0x18000f292  call    cs:__imp_VariantClear
0x18000f298  mov     eax, ebx
0x18000f29a  mov     rcx, [rbp+730h+var_40]
0x18000f2a1  xor     rcx, rsp; StackCookie
0x18000f2a4  call    __security_check_cookie
0x18000f2a9  mov     rbx, [rsp+830h+arg_18]
0x18000f2b1  add     rsp, 800h
0x18000f2b8  pop     r15
0x18000f2ba  pop     r14
0x18000f2bc  pop     r13
0x18000f2be  pop     r12
0x18000f2c0  pop     rdi
0x18000f2c1  pop     rsi
0x18000f2c2  pop     rbp
0x18000f2c3  retn
0x18000f2c4  mov     eax, [rbp+730h+var_7A0]
0x18000f2c7  movups  xmm0, [rbp+730h+var_6D0]
0x18000f2cb  movups  xmmword ptr [r15], xmm0
0x18000f2cf  mov     [r14+68h], eax
0x18000f2d3  test    r12d, r12d
0x18000f2d6  jz      short loc_18000F25A
0x18000f2d8  lea     rcx, [rbp+730h+pvarg]; struct tagVARIANT *
0x18000f2dc  call    ?PlaiVariantClear@@YAJPEAUtagVARIANT@@@Z; PlaiVariantClear(tagVARIANT *)
0x18000f2e1  mov     rax, [rdi]
0x18000f2e4  lea     rdx, [rbp+730h+pvarg+8]
0x18000f2e8  mov     rcx, rdi
0x18000f2eb  mov     rax, [rax+1A0h]
0x18000f2f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2f7  mov     ebx, eax
0x18000f2f9  test    eax, eax
0x18000f2fb  js      loc_18000FDA3
0x18000f301  mov     rcx, [rsi]
0x18000f304  lea     r8, [rbp+730h+var_780]
0x18000f308  mov     rdx, qword ptr [rbp+730h+pvarg+8]
0x18000f30c  mov     r15d, 8
0x18000f312  mov     word ptr [rbp+730h+pvarg], r15w
0x18000f317  mov     rax, [rcx]
0x18000f31a  mov     rax, [rax+200h]
0x18000f321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f326  mov     ebx, eax
0x18000f328  test    eax, eax
0x18000f32a  js      loc_18000FDD8
0x18000f330  cmp     dword ptr [r14+6Ch], 0
0x18000f335  jz      loc_18000F25A
0x18000f33b  lea     rcx, [rbp+730h+var_760]; struct tagVARIANT *
0x18000f33f  call    ?PlaiVariantClear@@YAJPEAUtagVARIANT@@@Z; PlaiVariantClear(tagVARIANT *)
0x18000f344  mov     rax, [rdi]
0x18000f347  lea     rdx, [rbp+730h+var_760+8]
0x18000f34b  mov     rcx, rdi
0x18000f34e  mov     rax, [rax+198h]
0x18000f355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f35a  mov     ebx, eax
0x18000f35c  test    eax, eax
0x18000f35e  js      loc_18000FE0D
0x18000f364  mov     rcx, [rsi]
0x18000f367  mov     r8, [r14+70h]
0x18000f36b  mov     rdx, qword ptr [rbp+730h+var_760+8]
0x18000f36f  mov     word ptr [rbp+730h+var_760], r15w
0x18000f374  mov     rax, [rcx]
0x18000f377  mov     rax, [rax+1D0h]
0x18000f37e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f383  mov     ebx, eax
0x18000f385  jmp     loc_18000F25A
0x18000f38a  mov     rax, cs:qword_180169748
0x18000f391  and     rax, rdx
0x18000f394  cmp     cs:qword_180169748, rax
0x18000f39b  jnz     loc_18000F25A
0x18000f3a1  lea     rcx, [rbp+730h+var_240]; unsigned __int16 *
0x18000f3a8  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18000f3ad  lea     rcx, [rbp+730h+var_240]
0x18000f3b4  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000f3bb  nop     dword ptr [rax+rax+00h]
0x18000f3c0  cmp     word ptr [rcx+rax*2+2], 0
0x18000f3c6  lea     rax, [rax+1]
0x18000f3ca  jnz     short loc_18000F3C0
0x18000f3cc  lea     ecx, [rax+rax]
0x18000f3cf  lea     rax, [rbp+730h+var_240]
0x18000f3d6  add     rcx, 2
0x18000f3da  lea     r9, [rsp+830h+var_7C0]
0x18000f3df  mov     [rsp+830h+var_7D0], rcx
0x18000f3e4  lea     rdx, PLA_EVENT_ERROR
0x18000f3eb  mov     [rsp+830h+var_7D8], rax
0x18000f3f0  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18000f3f7  mov     [rsp+830h+var_7E0], 1Bh
0x18000f400  lea     rax, aCdatacollector_16; "CDataCollectorSet::Connect"
0x18000f407  mov     [rsp+830h+var_7E8], rax
0x18000f40c  mov     r8d, 5
  ... truncated ...
```
