# APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData(INativeConfigurationElement *)

- ea: `0x180046c7c`
- end: `0x180047e12`
- name: `?SetProcessModelSettingsFromConfigStoreData@APP_POOL_DATA_OBJECT_CS@@QEAAJPEAVINativeConfigurationElement@@@Z`
- size: `4502`
- prototype: `__int64 __fastcall(APP_POOL_DATA_OBJECT_CS *__hidden this, struct INativeConfigurationElement *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180044950`

## callees

- `0x18002e780`
- `0x180046c7c`
- `0x180052d90`
- `0x180052f8c`
- `0x18005304c`
- `0x18005310c`
- `0x180053908`
- `0x180062010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180046e5d`
- `iisutil!PuDbgPrint` at `0x180046f64`
- `iisutil!PuDbgPrint` at `0x180046fbb`
- `iisutil!PuDbgPrint` at `0x1800470c5`
- `iisutil!PuDbgPrint` at `0x1800471cc`
- `iisutil!PuDbgPrint` at `0x1800472f2`
- `iisutil!PuDbgPrint` at `0x1800473d8`
- `iisutil!PuDbgPrint` at `0x1800474be`
- `iisutil!PuDbgPrint` at `0x1800475a4`
- `iisutil!PuDbgPrint` at `0x18004768a`
- `iisutil!PuDbgPrint` at `0x180047778`
- `iisutil!PuDbgPrint` at `0x1800478c1`
- `iisutil!PuDbgPrint` at `0x180047a21`
- `iisutil!PuDbgPrint` at `0x180047b5e`
- `iisutil!PuDbgPrint` at `0x180047c51`
- `iisutil!PuDbgPrint` at `0x180047d41`
- `iisutil!PuDbgPrint` at `0x180046e5d`
- `iisutil!PuDbgPrint` at `0x180046f64`
- `iisutil!PuDbgPrint` at `0x180046fbb`
- `iisutil!PuDbgPrint` at `0x1800470c5`
- `iisutil!PuDbgPrint` at `0x1800471cc`
- `iisutil!PuDbgPrint` at `0x1800472f2`
- `iisutil!PuDbgPrint` at `0x1800473d8`
- `iisutil!PuDbgPrint` at `0x1800474be`
- `iisutil!PuDbgPrint` at `0x1800475a4`
- `iisutil!PuDbgPrint` at `0x18004768a`
- `iisutil!PuDbgPrint` at `0x180047778`
- `iisutil!PuDbgPrint` at `0x1800478c1`
- `iisutil!PuDbgPrint` at `0x180047a21`
- `iisutil!PuDbgPrint` at `0x180047b5e`
- `iisutil!PuDbgPrint` at `0x180047c51`
- `iisutil!PuDbgPrint` at `0x180047d41`
- `iisutil!PuDbgPrintError` at `0x180047da5`
- `iisutil!PuDbgPrintError` at `0x180047da5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004778e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800478d7`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180047a37`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004778e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800478d7`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180047a37`

## string_xrefs

- `0x180046ceb`: ` Failed reading property \n`
- `0x180046e99`: ` Failed reading property \n`
- `0x180046ff7`: ` Failed reading property \n`
- `0x180047101`: ` Failed reading property \n`
- `0x180047208`: ` Failed reading property \n`
- `0x180047334`: ` Failed reading property \n`
- `0x18004741a`: ` Failed reading property \n`
- `0x180047500`: ` Failed reading property \n`
- `0x1800475e6`: ` Failed reading property \n`
- `0x1800476c6`: ` Failed reading property \n`
- `0x18004780e`: ` Failed reading property \n`
- `0x180047979`: ` Failed reading property \n`
- `0x180046cf9`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\apppoolstore_cs.cxx`
- `0x180046e1b`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\apppoolstore_cs.cxx`
- `0x180046cf2`: `APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData`
- `0x180046e12`: `APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData`
- `0x1800477a7`: ` Failed copying string property \n`
- `0x1800478f0`: ` Failed copying string property \n`
- `0x180047a50`: ` Failed copying string property \n`
- `0x180047aa6`: ` Failed reading CS_PROCESS_MODEL_LOAD_USER_PROFILE property \n`
- `0x180047ba0`: ` Failed reading CS_PROCESS_MODEL_SET_PROFILE_ENVIRONMENT property \n`
- `0x180047c93`: ` Failed reading CS_PROCESS_MODEL_MANUAL_GROUP_MEMBERSHIP property \n`
- `0x180047d82`: ` Failed reading CS_PROCESS_MODEL_LOG_EVENT_ON_PROCESS_MODEL property \n`

## pseudocode

```c
__int64 __fastcall APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData(
        APP_POOL_DATA_OBJECT_CS *this,
        struct INativeConfigurationElement *a2)
{
  __int64 v2; // rax
  int *v3; // r12
  __int64 (__fastcall *v6)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD); // rax
  int HashData; // ebx
  __int64 v8; // r8
  struct CONFIG_ERROR *v9; // rdx
  __int64 v10; // r8
  struct INativePropertyException *v11; // r9
  struct CONFIG_ERROR *v12; // rdx
  __int64 v13; // r8
  struct INativePropertyException *v14; // r9
  struct CONFIG_ERROR *v15; // rdx
  int v16; // edx
  const wchar_t *v17; // rax
  __int64 v18; // r8
  struct INativePropertyException *v19; // r9
  struct CONFIG_ERROR *v20; // rdx
  __int64 v21; // r8
  struct INativePropertyException *v22; // r9
  struct CONFIG_ERROR *v23; // rdx
  __int64 v24; // r8
  struct INativePropertyException *v25; // r9
  struct CONFIG_ERROR *v26; // rdx
  int *v27; // r12
  struct CONFIG_ERROR *v28; // rdx
  int *v29; // r12
  struct CONFIG_ERROR *v30; // rdx
  int *v31; // r12
  struct CONFIG_ERROR *v32; // rdx
  int *v33; // r12
  struct CONFIG_ERROR *v34; // rdx
  struct CONFIG_ERROR *v35; // rdx
  unsigned __int16 *v36; // r12
  unsigned __int16 *v37; // rcx
  __int64 v38; // rcx
  char *v39; // rax
  struct CONFIG_ERROR *v40; // rdx
  unsigned __int16 *v41; // rcx
  unsigned int v42; // r8d
  unsigned __int8 *v43; // rdx
  struct CONFIG_ERROR *v44; // rdx
  int *v45; // r13
  struct CONFIG_ERROR *v46; // rdx
  const char *v47; // r12
  const char *v48; // rax
  int *v49; // r13
  struct CONFIG_ERROR *v50; // rdx
  const char *v51; // rax
  int *v52; // r13
  struct CONFIG_ERROR *v53; // rdx
  struct INativePropertyException *v54; // rcx
  struct CONFIG_ERROR *v55; // rdx
  unsigned int v57; // [rsp+20h] [rbp-28h]
  int v58; // [rsp+38h] [rbp-10h]
  struct INativePropertyException *v59; // [rsp+90h] [rbp+48h] BYREF
  struct CONFIG_ERROR *v60; // [rsp+98h] [rbp+50h] BYREF
  unsigned __int16 *v61; // [rsp+A0h] [rbp+58h] BYREF
  __int64 v62; // [rsp+A8h] [rbp+60h] BYREF

  v2 = *(_QWORD *)a2;
  v3 = (int *)((char *)this + 188);
  v61 = 0;
  v62 = 0;
  v6 = *(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(v2 + 72);
  v59 = 0;
  v60 = 0;
  HashData = v6(a2, L"pingingEnabled", (char *)this + 188, &v59, 0);
  if ( HashData < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_180;
    v8 = 639;
    goto LABEL_4;
  }
  if ( v59 )
  {
    CONFIG_ERROR::CreateAndInitWithBool(&v60, L"pingingEnabled", *v3, v59);
    v9 = v60;
    if ( v60 )
    {
      *((_DWORD *)v60 + 2) = 7;
      CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v9);
    }
    v60 = 0;
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v59 + 16LL))(v59);
    v59 = 0;
  }
  HashData = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, __int64 *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 80LL))(
               a2,
               L"pingInterval",
               &v62,
               &v59,
               0);
  if ( HashData < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      v8 = 663;
LABEL_4:
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
        v8,
        "APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData",
        HashData,
        " Failed reading property \n");
    }
LABEL_180:
    v54 = v59;
    if ( v59 )
    {
LABEL_186:
      (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v54 + 16LL))(v54);
      return (unsigned int)HashData;
    }
    return (unsigned int)HashData;
  }
  v10 = v62;
  v11 = v59;
  *((_DWORD *)this + 58) = v62 / 10000000;
  if ( v11 )
  {
    CONFIG_ERROR::CreateAndInitWithRawTimeSpan(&v60, L"pingInterval", v10, v11);
    v12 = v60;
    if ( v60 )
    {
      *((_DWORD *)v60 + 2) = 17;
      CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v12);
    }
    v60 = 0;
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v59 + 16LL))(v59);
    v59 = 0;
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
      686,
      "APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData",
      " Ping Interval in seconds = %u (0x%X) (%d) \n",
      *((_DWORD *)this + 58),
      *((_DWORD *)this + 58),
      v58);
  HashData = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, __int64 *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 80LL))(
               a2,
               L"pingResponseTime",
               &v62,
               &v59,
               0);
  if ( HashData < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
        697,
        "APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData",
        HashData,
        " Failed reading property \n");
    goto LABEL_180;
  }
  v13 = v62;
  v14 = v59;
  *((_DWORD *)this + 59) = v62 / 10000000;
  if ( v14 )
  {
    CONFIG_ERROR::CreateAndInitWithRawTimeSpan(&v60, L"pingResponseTime", v13, v14);
    v15 = v60;
    if ( v60 )
    {
      *((_DWORD *)v60 + 2) = 18;
      CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v15);
    }
    v60 = 0;
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v59 + 16LL))(v59);
    v59 = 0;
  }
  v16 = g_dwDebugFlags;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
      720,
      "APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData",
      " Ping Response Time in seconds = %u (0x%X) \n",
      *((_DWORD *)this + 59),
      *((_DWORD *)this + 59));
    v16 = g_dwDebugFlags;
  }
  if ( (v16 & 3) != 0 && (v16 & 0x40000000) != 0 )
  {
    v17 = L"TRUE";
    if ( !*v3 )
      v17 = L"FALSE";
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
      727,
      "APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData",
      " Ping Enabled = %S \n",
      v17);
  }
  HashData = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, __int64 *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 80LL))(
               a2,
               L"startupTimeLimit",
               &v62,
               &v59,
               0);
  if ( HashData < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
        737,
        "APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData",
        HashData,
        " Failed reading property \n");
    goto LABEL_180;
  }
  v18 = v62;
  v19 = v59;
  *((_DWORD *)this + 56) = v62 / 10000000;
  if ( v19 )
  {
    CONFIG_ERROR::CreateAndInitWithRawTimeSpan(&v60, L"startupTimeLimit", v18, v19);
    v20 = v60;
    if ( v60 )
    {
      *((_DWORD *)v60 + 2) = 15;
      CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v20);
    }
    v60 = 0;
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v59 + 16LL))(v59);
    v59 = 0;
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
      760,
      "APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData",
      " Startup Time Limit in seconds = %u (0x%X) \n",
      *((_DWORD *)this + 56),
      *((_DWORD *)this + 56));
  HashData = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, __int64 *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 80LL))(
               a2,
               L"shutdownTimeLimit",
               &v62,
               &v59,
               0);
  if ( HashData < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
        770,
        "APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData",
        HashData,
        " Failed reading property \n");
    goto LABEL_180;
  }
  v21 = v62;
  v22 = v59;
  *((_DWORD *)this + 57) = v62 / 10000000;
  if ( v22 )
  {
    CONFIG_ERROR::CreateAndInitWithRawTimeSpan(&v60, L"shutdownTimeLimit", v21, v22);
    v23 = v60;
    if ( v60 )
    {
      *((_DWORD *)v60 + 2) = 16;
      CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v23);
    }
    v60 = 0;
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v59 + 16LL))(v59);
    v59 = 0;
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
      793,
      "APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData",
      " Shutdown Time Limit in seconds = %u (0x%X) \n",
      *((_DWORD *)this + 57),
      *((_DWORD *)this + 57));
  HashData = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, __int64 *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 80LL))(
               a2,
               L"idleTimeout",
               &v62,
               &v59,
               0);
  if ( HashData < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
        803,
        "APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData",
        HashData,
        " Failed reading property \n");
    goto LABEL_180;
  }
  v24 = v62;
  v25 = v59;
  *((_DWORD *)this + 45) = v62 / 10000000 / 60;
  if ( v25 )
  {
    CONFIG_ERROR::CreateAndInitWithRawTimeSpan(&v60, L"idleTimeout", v24, v25);
    v26 = v60;
    if ( v60 )
    {
      *((_DWORD *)v60 + 2) = 8;
      CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v26);
    }
    v60 = 0;
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v59 + 16LL))(v59);
    v59 = 0;
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
      826,
      "APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData",
      " Idle Timeout in minutes = %u (0x%X) \n",
      *((_DWORD *)this + 45),
      *((_DWORD *)this + 45));
  v27 = (int *)((char *)this + 184);
  HashData = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 48LL))(
               a2,
               L"idleTimeoutAction",
               (char *)this + 184,
               &v59,
               0);
  if ( HashData < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
        836,
        "APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData",
        HashData,
        " Failed reading property \n");
    goto LABEL_180;
  }
  if ( v59 )
  {
    CONFIG_ERROR::CreateAndInitWithLong(&v60, L"idleTimeoutAction", *v27, v59);
    v28 = v60;
    if ( v60 )
    {
      *((_DWORD *)v60 + 2) = 9;
      CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v28);
    }
    v60 = 0;
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v59 + 16LL))(v59);
    v59 = 0;
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
      858,
      "APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData",
      " idleTimeoutAction = %u (0x%X) \n ",
      *v27,
      *v27);
  v29 = (int *)((char *)this + 176);
  HashData = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 48LL))(
               a2,
               L"maxProcesses",
               (char *)this + 176,
               &v59,
               0);
  if ( HashData < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
        868,
        "APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData",
        HashData,
        " Failed reading property \n");
    goto LABEL_180;
  }
  if ( v59 )
  {
    CONFIG_ERROR::CreateAndInitWithLong(&v60, L"maxProcesses", *v29, v59);
    v30 = v60;
    if ( v60 )
    {
      *((_DWORD *)v60 + 2) = 6;
      CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v30);
    }
    v60 = 0;
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v59 + 16LL))(v59);
    v59 = 0;
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
      890,
      "APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData",
      " Max Processes = %u (0x%X) \n",
      *v29,
      *v29);
  v31 = (int *)((char *)this + 576);
  HashData = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 48LL))(
               a2,
               L"identityType",
               (char *)this + 576,
               &v59,
               0);
  if ( HashData < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
        901,
        "APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData",
        HashData,
        " Failed reading property \n");
    goto LABEL_180;
  }
  if ( v59 )
  {
    CONFIG_ERROR::CreateAndInitWithLong(&v60, L"identityType", *v31, v59);
    v32 = v60;
    if ( v60 )
    {
      *((_DWORD *)v60 + 2) = 30;
      CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v32);
    }
    v60 = 0;
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v59 + 16LL))(v59);
    v59 = 0;
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
      923,
      "APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData",
      " App Pool Identity = %u (0x%X) \n",
      *v31,
      *v31);
  v33 = (int *)((char *)this + 924);
  HashData = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 48LL))(
               a2,
               L"logonType",
               (char *)this + 924,
               &v59,
               0);
  if ( HashData < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
        933,
        "APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData",
        HashData,
        " Failed reading property \n");
    goto LABEL_180;
  }
  if ( v59 )
  {
    CONFIG_ERROR::CreateAndInitWithLong(&v60, L"logonType", *v33, v59);
    v34 = v60;
    if ( v60 )
    {
      *((_DWORD *)v60 + 2) = 45;
      CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v34);
    }
    v60 = 0;
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v59 + 16LL))(v59);
    v59 = 0;
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
      955,
      "APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData",
      " App Pool Logon Type = %u (0x%X) \n",
      *v33,
      *v33);
  HashData = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, unsigned __int16 **, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 64LL))(
               a2,
               L"userName",
               &v61,
               &v59,
               0);
  if ( HashData < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
        965,
        "APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData",
        HashData,
        " Failed reading property \n");
    goto LABEL_180;
  }
  if ( v59 )
  {
    CONFIG_ERROR::CreateAndInitWithString(&v60, L"userName", v61, v59);
    v35 = v60;
    if ( v60 )
    {
      *((_DWORD *)v60 + 2) = 24;
      CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v35);
    }
    v60 = 0;
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v59 + 16LL))(v59);
    v59 = 0;
  }
  v36 = L"NULL";
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
  {
    v37 = L"NULL";
    if ( v61 )
      v37 = v61;
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
      986,
      "APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData",
      " App Pool User Name = '%s' \n",
      (const char *)v37);
  }
  if ( v61 )
  {
    HashData = STRU::Copy((APP_POOL_DATA_OBJECT_CS *)((char *)this + 368), v61);
    if ( HashData < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
          996,
          "APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData",
          HashData,
          " Failed copying string property \n");
      goto LABEL_180;
    }
    v61 = 0;
  }
  v38 = 32;
  v39 = (char *)this + 544;
  do
  {
    *v39++ = 0;
    --v38;
  }
  while ( v38 );
  v57 = 0;
  HashData = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, unsigned __int16 **, struct INativePropertyException **))(*(_QWORD *)a2 + 64LL))(
               a2,
               L"password",
               &v61,
               &v59);
  if ( HashData < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
        1018,
        "APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData",
        HashData,
        " Failed reading property \n");
    goto LABEL_180;
  }
  if ( v59 )
  {
    CONFIG_ERROR::CreateAndInitWithString(&v60, L"password", v61, v59);
    v40 = v60;
    if ( v60 )
    {
      *((_DWORD *)v60 + 2) = 25;
      CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v40);
    }
    v60 = 0;
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v59 + 16LL))(v59);
    v59 = 0;
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
  {
    v41 = L"NULL";
    if ( v61 )
      v41 = v61;
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
      1039,
      "APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData",
      " App Pool User pass = '%s' \n",
      (const char *)v41);
  }
  if ( v61 )
  {
    HashData = STRU::Copy((APP_POOL_DATA_OBJECT_CS *)((char *)this + 424), v61);
    if ( HashData < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
          1049,
          "APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData",
          HashData,
          " Failed copying string property \n");
      goto LABEL_180;
    }
    v42 = 2 * *((_DWORD *)this + 118);
    v43 = (unsigned __int8 *)*((_QWORD *)this + 57);
    v61 = 0;
    HashData = CONFIG_MANAGER::GetHashData(
                 (WEB_ADMIN_SERVICE *)((char *)g_pWebAdminService + 704),
                 v43,
                 v42,
                 (unsigned __int8 *)this + 544,
                 v57);
    if ( HashData < 0 )
      goto LABEL_180;
  }
  HashData = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, unsigned __int16 **, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 64LL))(
               a2,
               L"requestQueueDelegatorIdentity",
               &v61,
               &v59,
               0);
  if ( HashData < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
        1090,
        "APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData",
        HashData,
        " Failed reading property \n");
    goto LABEL_180;
  }
  if ( v59 )
  {
    CONFIG_ERROR::CreateAndInitWithString(&v60, L"requestQueueDelegatorIdentity", v61, v59);
    v44 = v60;
    if ( v60 )
    {
      *((_DWORD *)v60 + 2) = 26;
      CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v44);
    }
    v60 = 0;
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v59 + 16LL))(v59);
    v59 = 0;
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
  {
    if ( v61 )
      v36 = v61;
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
      1111,
      "APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData",
      " App Pool Request Queue Delegator Identity = '%s' \n",
      (const char *)v36);
  }
  if ( v61 )
  {
    HashData = STRU::Copy((APP_POOL_DATA_OBJECT_CS *)((char *)this + 480), v61);
    if ( HashData < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
          1121,
          "APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData",
          HashData,
          " Failed copying string property \n");
      goto LABEL_180;
    }
    v61 = 0;
  }
  v45 = (int *)((char *)this + 536);
  HashData = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 72LL))(
               a2,
               L"loadUserProfile",
               (char *)this + 536,
               &v59,
               0);
  if ( HashData < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
        1135,
        "APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData",
        HashData,
        " Failed reading CS_PROCESS_MODEL_LOAD_USER_PROFILE property \n");
    goto LABEL_180;
  }
  if ( v59 )
  {
    CONFIG_ERROR::CreateAndInitWithBool(&v60, L"loadUserProfile", *v45, v59);
    v46 = v60;
    if ( v60 )
    {
      *((_DWORD *)v60 + 2) = 27;
      CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v46);
    }
    v60 = 0;
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v59 + 16LL))(v59);
    v59 = 0;
  }
  v47 = "TRUE";
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
  {
    v48 = "TRUE";
    if ( !*v45 )
      v48 = "FALSE";
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
      1156,
      "APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData",
      " LoadUserProfile = %s \n",
      v48);
  }
  v49 = (int *)((char *)this + 932);
  HashData = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 72LL))(
               a2,
               L"setProfileEnvironment",
               (char *)this + 932,
               &v59,
               0);
  if ( HashData < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
        1166,
        "APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData",
        HashData,
        " Failed reading CS_PROCESS_MODEL_SET_PROFILE_ENVIRONMENT property \n");
    goto LABEL_180;
  }
  if ( v59 )
  {
    CONFIG_ERROR::CreateAndInitWithBool(&v60, L"setProfileEnvironment", *v49, v59);
    v50 = v60;
    if ( v60 )
    {
      *((_DWORD *)v60 + 2) = 28;
      CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v50);
    }
    v60 = 0;
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v59 + 16LL))(v59);
    v59 = 0;
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
  {
    v51 = "TRUE";
    if ( !*v49 )
      v51 = "FALSE";
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
      1187,
      "APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData",
      " SetProfileEnvironment = %s \n",
      v51);
  }
  v52 = (int *)((char *)this + 540);
  HashData = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 72LL))(
               a2,
               L"manualGroupMembership",
               (char *)this + 540,
               &v59,
               0);
  if ( HashData < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
        1197,
        "APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData",
        HashData,
        " Failed reading CS_PROCESS_MODEL_MANUAL_GROUP_MEMBERSHIP property \n");
    goto LABEL_180;
  }
  if ( v59 )
  {
    CONFIG_ERROR::CreateAndInitWithBool(&v60, L"manualGroupMembership", *v52, v59);
    v53 = v60;
    if ( v60 )
    {
      *((_DWORD *)v60 + 2) = 29;
      CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v53);
    }
    v60 = 0;
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v59 + 16LL))(v59);
    v59 = 0;
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
  {
    if ( !*v52 )
      v47 = "FALSE";
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
      1218,
      "APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData",
      " _fManualGroupMembership = %s \n",
      v47);
  }
  HashData = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 48LL))(
               a2,
               L"logEventOnProcessModel",
               (char *)this + 728,
               &v59,
               0);
  if ( HashData < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
        1228,
        "APP_POOL_DATA_OBJECT_CS::SetProcessModelSettingsFromConfigStoreData",
        HashData,
        " Failed reading CS_PROCESS_MODEL_LOG_EVENT_ON_PROCESS_MODEL property \n");
    goto LABEL_180;
  }
  if ( v59 )
  {
    CONFIG_ERROR::CreateAndInitWithLong(&v60, L"logEventOnProcessModel", *((_DWORD *)this + 182), v59);
    v55 = v60;
    if ( v60 )
    {
      *((_DWORD *)v60 + 2) = 50;
      CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v55);
    }
    v54 = v59;
    goto LABEL_186;
  }
  return (unsigned int)HashData;
}

```

## disassembly

```asm
0x180046c7c  push    rbp
0x180046c7e  push    rbx
0x180046c7f  push    rsi
0x180046c80  push    rdi
0x180046c81  push    r12
0x180046c83  push    r13
0x180046c85  push    r14
0x180046c87  push    r15
0x180046c89  mov     rbp, rsp
0x180046c8c  sub     rsp, 48h
0x180046c90  mov     rax, [rdx]
0x180046c93  lea     r12, [rcx+0BCh]
0x180046c9a  xor     r13d, r13d
0x180046c9d  lea     r9, [rbp+arg_0]
0x180046ca1  mov     r15, rdx
0x180046ca4  mov     [rbp+arg_10], r13
0x180046ca8  mov     rdi, rcx
0x180046cab  mov     [rbp+arg_18], r13
0x180046caf  mov     rax, [rax+48h]
0x180046cb3  lea     rdx, aPingingenabled; "pingingEnabled"
0x180046cba  mov     r8, r12
0x180046cbd  mov     [rbp+arg_0], r13
0x180046cc1  mov     rcx, r15
0x180046cc4  mov     [rbp+arg_8], r13
0x180046cc8  mov     qword ptr [rsp+48h+var_28], r13
0x180046ccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046cd2  mov     ebx, eax
0x180046cd4  test    eax, eax
0x180046cd6  jns     short loc_180046D05
0x180046cd8  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180046cdf  jz      loc_180047DAB
0x180046ce5  mov     r8d, 27Fh
0x180046ceb  lea     rax, aFailedReadingP_1; " Failed reading property \n"
0x180046cf2  lea     r9, aAppPoolDataObj_7; "APP_POOL_DATA_OBJECT_CS::SetProcessMode"...
0x180046cf9  lea     rdx, aServercommonIn_62; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180046d00  jmp     loc_180047D95
0x180046d05  mov     r9, [rbp+arg_0]; struct INativePropertyException *
0x180046d09  test    r9, r9
0x180046d0c  jz      short loc_180046D56
0x180046d0e  mov     r8d, [r12]; int
0x180046d12  lea     rdx, aPingingenabled; "pingingEnabled"
0x180046d19  lea     rcx, [rbp+arg_8]; struct CONFIG_ERROR **
0x180046d1d  call    ?CreateAndInitWithBool@CONFIG_ERROR@@SAXPEAPEAV1@PEBGHPEAVINativePropertyException@@@Z; CONFIG_ERROR::CreateAndInitWithBool(CONFIG_ERROR * *,ushort const *,int,INativePropertyException *)
0x180046d22  mov     rdx, [rbp+arg_8]; struct CONFIG_ERROR *
0x180046d26  test    rdx, rdx
0x180046d29  jz      short loc_180046D3E
0x180046d2b  lea     rcx, [rdi+3E8h]; this
0x180046d32  mov     dword ptr [rdx+8], 7
0x180046d39  call    ?Add@CONFIG_ERROR_LIST@@QEAAXPEAVCONFIG_ERROR@@@Z; CONFIG_ERROR_LIST::Add(CONFIG_ERROR *)
0x180046d3e  mov     rcx, [rbp+arg_0]
0x180046d42  mov     [rbp+arg_8], r13
0x180046d46  mov     rax, [rcx]
0x180046d49  mov     rax, [rax+10h]
0x180046d4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046d52  mov     [rbp+arg_0], r13
0x180046d56  mov     rax, [r15]
0x180046d59  lea     r9, [rbp+arg_0]
0x180046d5d  lea     r8, [rbp+arg_18]
0x180046d61  mov     qword ptr [rsp+48h+var_28], r13
0x180046d66  lea     rdx, aPinginterval; "pingInterval"
0x180046d6d  mov     rcx, r15
0x180046d70  mov     rax, [rax+50h]
0x180046d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046d79  mov     ebx, eax
0x180046d7b  test    eax, eax
0x180046d7d  jns     short loc_180046D97
0x180046d7f  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180046d86  jz      loc_180047DAB
0x180046d8c  mov     r8d, 297h
0x180046d92  jmp     loc_180046CEB
0x180046d97  mov     r8, [rbp+arg_18]; __int64
0x180046d9b  mov     rax, 0D6BF94D5E57A42BDh
0x180046da5  mov     r9, [rbp+arg_0]; struct INativePropertyException *
0x180046da9  imul    r8
0x180046dac  add     rdx, r8
0x180046daf  sar     rdx, 17h
0x180046db3  mov     rax, rdx
0x180046db6  shr     rax, 3Fh
0x180046dba  add     rdx, rax
0x180046dbd  mov     [rdi+0E8h], edx
0x180046dc3  test    r9, r9
0x180046dc6  jz      short loc_180046E0C
0x180046dc8  lea     rdx, aPinginterval; "pingInterval"
0x180046dcf  lea     rcx, [rbp+arg_8]; struct CONFIG_ERROR **
0x180046dd3  call    ?CreateAndInitWithRawTimeSpan@CONFIG_ERROR@@SAXPEAPEAV1@PEBG_JPEAVINativePropertyException@@@Z; CONFIG_ERROR::CreateAndInitWithRawTimeSpan(CONFIG_ERROR * *,ushort const *,__int64,INativePropertyException *)
0x180046dd8  mov     rdx, [rbp+arg_8]; struct CONFIG_ERROR *
0x180046ddc  test    rdx, rdx
0x180046ddf  jz      short loc_180046DF4
0x180046de1  lea     rcx, [rdi+3E8h]; this
0x180046de8  mov     dword ptr [rdx+8], 11h
0x180046def  call    ?Add@CONFIG_ERROR_LIST@@QEAAXPEAVCONFIG_ERROR@@@Z; CONFIG_ERROR_LIST::Add(CONFIG_ERROR *)
0x180046df4  mov     rcx, [rbp+arg_0]
0x180046df8  mov     [rbp+arg_8], r13
0x180046dfc  mov     rax, [rcx]
0x180046dff  mov     rax, [rax+10h]
0x180046e03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046e08  mov     [rbp+arg_0], r13
0x180046e0c  mov     eax, cs:g_dwDebugFlags
0x180046e12  lea     rsi, aAppPoolDataObj_7; "APP_POOL_DATA_OBJECT_CS::SetProcessMode"...
0x180046e19  test    al, 3
0x180046e1b  lea     r14, aServercommonIn_62; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180046e22  setnz   cl
0x180046e25  bt      eax, 1Eh
0x180046e29  setb    al
0x180046e2c  test    al, cl
0x180046e2e  jz      short loc_180046E63
0x180046e30  mov     eax, [rdi+0E8h]
0x180046e36  mov     r9, rsi
0x180046e39  mov     rcx, cs:g_pDebug
0x180046e40  mov     r8d, 2AEh
0x180046e46  mov     [rsp+48h+var_18], eax
0x180046e4a  mov     rdx, r14
0x180046e4d  mov     dword ptr [rsp+48h+var_20], eax
0x180046e51  lea     rax, aPingIntervalIn; " Ping Interval in seconds = %u (0x%X) ("...
0x180046e58  mov     qword ptr [rsp+48h+var_28], rax
0x180046e5d  call    cs:__imp_PuDbgPrint
0x180046e63  mov     rax, [r15]
0x180046e66  lea     r9, [rbp+arg_0]
0x180046e6a  lea     r8, [rbp+arg_18]
0x180046e6e  mov     qword ptr [rsp+48h+var_28], r13
0x180046e73  lea     rdx, aPingresponseti_0; "pingResponseTime"
0x180046e7a  mov     rcx, r15
0x180046e7d  mov     rax, [rax+50h]
0x180046e81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046e86  mov     ebx, eax
0x180046e88  test    eax, eax
0x180046e8a  jns     short loc_180046EAB
0x180046e8c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180046e93  jz      loc_180047DAB
0x180046e99  lea     rax, aFailedReadingP_1; " Failed reading property \n"
0x180046ea0  mov     r8d, 2B9h
0x180046ea6  jmp     loc_180047D8F
0x180046eab  mov     r8, [rbp+arg_18]; __int64
0x180046eaf  mov     rax, 0D6BF94D5E57A42BDh
0x180046eb9  mov     r9, [rbp+arg_0]; struct INativePropertyException *
0x180046ebd  imul    r8
0x180046ec0  add     rdx, r8
0x180046ec3  sar     rdx, 17h
0x180046ec7  mov     rax, rdx
0x180046eca  shr     rax, 3Fh
0x180046ece  add     rdx, rax
0x180046ed1  mov     [rdi+0ECh], edx
0x180046ed7  test    r9, r9
0x180046eda  jz      short loc_180046F20
0x180046edc  lea     rdx, aPingresponseti_0; "pingResponseTime"
0x180046ee3  lea     rcx, [rbp+arg_8]; struct CONFIG_ERROR **
0x180046ee7  call    ?CreateAndInitWithRawTimeSpan@CONFIG_ERROR@@SAXPEAPEAV1@PEBG_JPEAVINativePropertyException@@@Z; CONFIG_ERROR::CreateAndInitWithRawTimeSpan(CONFIG_ERROR * *,ushort const *,__int64,INativePropertyException *)
0x180046eec  mov     rdx, [rbp+arg_8]; struct CONFIG_ERROR *
0x180046ef0  test    rdx, rdx
0x180046ef3  jz      short loc_180046F08
0x180046ef5  lea     rcx, [rdi+3E8h]; this
0x180046efc  mov     dword ptr [rdx+8], 12h
0x180046f03  call    ?Add@CONFIG_ERROR_LIST@@QEAAXPEAVCONFIG_ERROR@@@Z; CONFIG_ERROR_LIST::Add(CONFIG_ERROR *)
0x180046f08  mov     rcx, [rbp+arg_0]
0x180046f0c  mov     [rbp+arg_8], r13
0x180046f10  mov     rax, [rcx]
0x180046f13  mov     rax, [rax+10h]
0x180046f17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046f1c  mov     [rbp+arg_0], r13
0x180046f20  mov     edx, cs:g_dwDebugFlags
0x180046f26  test    dl, 3
0x180046f29  setnz   cl
0x180046f2c  bt      edx, 1Eh
0x180046f30  setb    al
0x180046f33  test    al, cl
0x180046f35  jz      short loc_180046F70
0x180046f37  mov     eax, [rdi+0ECh]
0x180046f3d  mov     r9, rsi
0x180046f40  mov     rcx, cs:g_pDebug
0x180046f47  mov     r8d, 2D0h
0x180046f4d  mov     [rsp+48h+var_18], eax
0x180046f51  mov     rdx, r14
0x180046f54  mov     dword ptr [rsp+48h+var_20], eax
0x180046f58  lea     rax, aPingResponseTi; " Ping Response Time in seconds = %u (0x"...
0x180046f5f  mov     qword ptr [rsp+48h+var_28], rax
0x180046f64  call    cs:__imp_PuDbgPrint
0x180046f6a  mov     edx, cs:g_dwDebugFlags
0x180046f70  test    dl, 3
0x180046f73  setnz   cl
0x180046f76  bt      edx, 1Eh
0x180046f7a  setb    al
0x180046f7d  test    al, cl
0x180046f7f  jz      short loc_180046FC1
0x180046f81  cmp     [r12], r13d
0x180046f85  lea     rcx, aFalse_1; "FALSE"
0x180046f8c  lea     rax, aTrue_1; "TRUE"
0x180046f93  mov     r9, rsi
0x180046f96  cmovz   rax, rcx
0x180046f9a  mov     r8d, 2D7h
0x180046fa0  mov     rcx, cs:g_pDebug
0x180046fa7  mov     rdx, r14
0x180046faa  mov     [rsp+48h+var_20], rax
0x180046faf  lea     rax, aPingEnabledS; " Ping Enabled = %S \n"
0x180046fb6  mov     qword ptr [rsp+48h+var_28], rax
0x180046fbb  call    cs:__imp_PuDbgPrint
0x180046fc1  mov     rax, [r15]
0x180046fc4  lea     r9, [rbp+arg_0]
0x180046fc8  lea     r8, [rbp+arg_18]
0x180046fcc  mov     qword ptr [rsp+48h+var_28], r13
0x180046fd1  lea     rdx, aStartuptimelim; "startupTimeLimit"
0x180046fd8  mov     rcx, r15
0x180046fdb  mov     rax, [rax+50h]
0x180046fdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046fe4  mov     ebx, eax
0x180046fe6  test    eax, eax
0x180046fe8  jns     short loc_180047009
0x180046fea  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180046ff1  jz      loc_180047DAB
0x180046ff7  lea     rax, aFailedReadingP_1; " Failed reading property \n"
0x180046ffe  mov     r8d, 2E1h
0x180047004  jmp     loc_180047D8F
0x180047009  mov     r8, [rbp+arg_18]; __int64
0x18004700d  mov     rax, 0D6BF94D5E57A42BDh
0x180047017  mov     r9, [rbp+arg_0]; struct INativePropertyException *
0x18004701b  imul    r8
0x18004701e  add     rdx, r8
0x180047021  sar     rdx, 17h
0x180047025  mov     rax, rdx
0x180047028  shr     rax, 3Fh
0x18004702c  add     rdx, rax
0x18004702f  mov     [rdi+0E0h], edx
0x180047035  test    r9, r9
0x180047038  jz      short loc_18004707E
0x18004703a  lea     rdx, aStartuptimelim; "startupTimeLimit"
0x180047041  lea     rcx, [rbp+arg_8]; struct CONFIG_ERROR **
0x180047045  call    ?CreateAndInitWithRawTimeSpan@CONFIG_ERROR@@SAXPEAPEAV1@PEBG_JPEAVINativePropertyException@@@Z; CONFIG_ERROR::CreateAndInitWithRawTimeSpan(CONFIG_ERROR * *,ushort const *,__int64,INativePropertyException *)
0x18004704a  mov     rdx, [rbp+arg_8]; struct CONFIG_ERROR *
0x18004704e  test    rdx, rdx
0x180047051  jz      short loc_180047066
0x180047053  lea     rcx, [rdi+3E8h]; this
0x18004705a  mov     dword ptr [rdx+8], 0Fh
0x180047061  call    ?Add@CONFIG_ERROR_LIST@@QEAAXPEAVCONFIG_ERROR@@@Z; CONFIG_ERROR_LIST::Add(CONFIG_ERROR *)
0x180047066  mov     rcx, [rbp+arg_0]
0x18004706a  mov     [rbp+arg_8], r13
0x18004706e  mov     rax, [rcx]
0x180047071  mov     rax, [rax+10h]
0x180047075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004707a  mov     [rbp+arg_0], r13
0x18004707e  mov     eax, cs:g_dwDebugFlags
0x180047084  mov     r12b, 3
0x180047087  test    r12b, al
0x18004708a  setnz   cl
0x18004708d  bt      eax, 1Eh
0x180047091  setb    al
0x180047094  test    al, cl
0x180047096  jz      short loc_1800470CB
0x180047098  mov     eax, [rdi+0E0h]
0x18004709e  mov     r9, rsi
0x1800470a1  mov     rcx, cs:g_pDebug
0x1800470a8  mov     r8d, 2F8h
0x1800470ae  mov     [rsp+48h+var_18], eax
0x1800470b2  mov     rdx, r14
0x1800470b5  mov     dword ptr [rsp+48h+var_20], eax
0x1800470b9  lea     rax, aStartupTimeLim; " Startup Time Limit in seconds = %u (0x"...
0x1800470c0  mov     qword ptr [rsp+48h+var_28], rax
0x1800470c5  call    cs:__imp_PuDbgPrint
0x1800470cb  mov     rax, [r15]
0x1800470ce  lea     r9, [rbp+arg_0]
0x1800470d2  lea     r8, [rbp+arg_18]
0x1800470d6  mov     qword ptr [rsp+48h+var_28], r13
0x1800470db  lea     rdx, aShutdowntimeli; "shutdownTimeLimit"
0x1800470e2  mov     rcx, r15
0x1800470e5  mov     rax, [rax+50h]
0x1800470e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800470ee  mov     ebx, eax
0x1800470f0  test    eax, eax
0x1800470f2  jns     short loc_180047113
0x1800470f4  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800470fb  jz      loc_180047DAB
0x180047101  lea     rax, aFailedReadingP_1; " Failed reading property \n"
0x180047108  mov     r8d, 302h
0x18004710e  jmp     loc_180047D8F
0x180047113  mov     r8, [rbp+arg_18]; __int64
0x180047117  mov     rax, 0D6BF94D5E57A42BDh
0x180047121  mov     r9, [rbp+arg_0]; struct INativePropertyException *
0x180047125  imul    r8
0x180047128  add     rdx, r8
0x18004712b  sar     rdx, 17h
0x18004712f  mov     rax, rdx
0x180047132  shr     rax, 3Fh
0x180047136  add     rdx, rax
0x180047139  mov     [rdi+0E4h], edx
0x18004713f  test    r9, r9
0x180047142  jz      short loc_180047188
0x180047144  lea     rdx, aShutdowntimeli; "shutdownTimeLimit"
0x18004714b  lea     rcx, [rbp+arg_8]; struct CONFIG_ERROR **
0x18004714f  call    ?CreateAndInitWithRawTimeSpan@CONFIG_ERROR@@SAXPEAPEAV1@PEBG_JPEAVINativePropertyException@@@Z; CONFIG_ERROR::CreateAndInitWithRawTimeSpan(CONFIG_ERROR * *,ushort const *,__int64,INativePropertyException *)
0x180047154  mov     rdx, [rbp+arg_8]; struct CONFIG_ERROR *
0x180047158  test    rdx, rdx
0x18004715b  jz      short loc_180047170
0x18004715d  lea     rcx, [rdi+3E8h]; this
0x180047164  mov     dword ptr [rdx+8], 10h
0x18004716b  call    ?Add@CONFIG_ERROR_LIST@@QEAAXPEAVCONFIG_ERROR@@@Z; CONFIG_ERROR_LIST::Add(CONFIG_ERROR *)
0x180047170  mov     rcx, [rbp+arg_0]
0x180047174  mov     [rbp+arg_8], r13
0x180047178  mov     rax, [rcx]
0x18004717b  mov     rax, [rax+10h]
0x18004717f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047184  mov     [rbp+arg_0], r13
0x180047188  mov     eax, cs:g_dwDebugFlags
  ... truncated ...
```
