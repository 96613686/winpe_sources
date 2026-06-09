# APP_POOL_DATA_OBJECT_APPHOST::SetProcessModelSettingsFromConfigStoreData(IProcessModel *)

- ea: `0x18004acd4`
- end: `0x18004b877`
- name: `?SetProcessModelSettingsFromConfigStoreData@APP_POOL_DATA_OBJECT_APPHOST@@QEAAJPEAUIProcessModel@@@Z`
- size: `2979`
- prototype: `__int64 __fastcall(APP_POOL_DATA_OBJECT_APPHOST *__hidden this, struct IProcessModel *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180048f34`

## callees

- `0x18002e780`
- `0x18004acd4`
- `0x180062010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18004b3ef`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b4d6`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b5d7`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b857`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b3ef`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b4d6`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b5d7`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b857`
- `iisutil!PuDbgPrint` at `0x18004add7`
- `iisutil!PuDbgPrint` at `0x18004ae86`
- `iisutil!PuDbgPrint` at `0x18004af26`
- `iisutil!PuDbgPrint` at `0x18004afc6`
- `iisutil!PuDbgPrint` at `0x18004b066`
- `iisutil!PuDbgPrint` at `0x18004b124`
- `iisutil!PuDbgPrint` at `0x18004b1a6`
- `iisutil!PuDbgPrint` at `0x18004b225`
- `iisutil!PuDbgPrint` at `0x18004b2a4`
- `iisutil!PuDbgPrint` at `0x18004b323`
- `iisutil!PuDbgPrint` at `0x18004b3aa`
- `iisutil!PuDbgPrint` at `0x18004b491`
- `iisutil!PuDbgPrint` at `0x18004b592`
- `iisutil!PuDbgPrint` at `0x18004b686`
- `iisutil!PuDbgPrint` at `0x18004b726`
- `iisutil!PuDbgPrint` at `0x18004b7c3`
- `iisutil!PuDbgPrint` at `0x18004b848`
- `iisutil!PuDbgPrint` at `0x18004add7`
- `iisutil!PuDbgPrint` at `0x18004ae86`
- `iisutil!PuDbgPrint` at `0x18004af26`
- `iisutil!PuDbgPrint` at `0x18004afc6`
- `iisutil!PuDbgPrint` at `0x18004b066`
- `iisutil!PuDbgPrint` at `0x18004b124`
- `iisutil!PuDbgPrint` at `0x18004b1a6`
- `iisutil!PuDbgPrint` at `0x18004b225`
- `iisutil!PuDbgPrint` at `0x18004b2a4`
- `iisutil!PuDbgPrint` at `0x18004b323`
- `iisutil!PuDbgPrint` at `0x18004b3aa`
- `iisutil!PuDbgPrint` at `0x18004b491`
- `iisutil!PuDbgPrint` at `0x18004b592`
- `iisutil!PuDbgPrint` at `0x18004b686`
- `iisutil!PuDbgPrint` at `0x18004b726`
- `iisutil!PuDbgPrint` at `0x18004b7c3`
- `iisutil!PuDbgPrint` at `0x18004b848`
- `iisutil!PuDbgPrintError` at `0x18004ad5b`
- `iisutil!PuDbgPrintError` at `0x18004ad5b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004b3c0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004b4a7`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004b5a8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004b3c0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004b4a7`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004b5a8`

## string_xrefs

- `0x18004ad30`: ` Failed reading property \n`
- `0x18004ae0c`: ` Failed reading property \n`
- `0x18004b3d9`: ` Failed copying string property \n`
- `0x18004b4c0`: ` Failed copying string property \n`
- `0x18004b5c1`: ` Failed copying string property \n`
- `0x18004b611`: ` Failed reading CS_PROCESS_MODEL_LOAD_USER_PROFILE property \n`
- `0x18004b6b8`: ` Failed reading CS_PROCESS_MODEL_SET_PROFILE_ENVIRONMENT property \n`
- `0x18004b758`: ` Failed reading CS_PROCESS_MODEL_MANUAL_GROUP_MEMBERSHIP property \n`
- `0x18004b7f1`: ` Failed reading CS_PROCESS_MODEL_LOG_EVENT_ON_PROCESS_MODEL property \n`
- `0x18004ad44`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\apppoolstore_apphost.cxx`
- `0x18004ad75`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\apppoolstore_apphost.cxx`
- `0x18004ad3d`: `APP_POOL_DATA_OBJECT_APPHOST::SetProcessModelSettingsFromConfigStoreData`
- `0x18004ad6c`: `APP_POOL_DATA_OBJECT_APPHOST::SetProcessModelSettingsFromConfigStoreData`

## pseudocode

```c
__int64 __fastcall APP_POOL_DATA_OBJECT_APPHOST::SetProcessModelSettingsFromConfigStoreData(
        APP_POOL_DATA_OBJECT_APPHOST *this,
        struct IProcessModel *a2)
{
  __int64 v3; // rax
  int HashData; // ebx
  const char *v6; // rax
  __int64 v7; // r8
  int v8; // eax
  BOOL v9; // edx
  bool v10; // zf
  const wchar_t *v11; // rax
  __int64 v12; // rdx
  int v13; // eax
  __int64 v14; // rax
  __int64 v15; // rdx
  int v16; // eax
  __int64 v17; // rax
  __int64 v18; // rdx
  int v19; // eax
  __int64 v20; // rax
  __int64 v21; // rdx
  int v22; // eax
  __int64 v23; // rax
  __int64 v24; // rdx
  int v25; // eax
  BSTR v26; // r12
  BSTR v27; // rcx
  __int64 v28; // rcx
  char *v29; // rax
  BSTR v30; // rcx
  unsigned int v31; // r8d
  unsigned __int8 *v32; // rdx
  int v33; // eax
  const char *v34; // r8
  const char *v35; // r12
  BOOL v36; // edx
  const char *v37; // rax
  int v38; // eax
  BOOL v39; // edx
  const char *v40; // rax
  int v41; // eax
  BOOL v42; // edx
  unsigned int v44; // [rsp+20h] [rbp-20h]
  int v45; // [rsp+38h] [rbp-8h]
  __int16 v46; // [rsp+88h] [rbp+48h] BYREF
  __int64 v47; // [rsp+90h] [rbp+50h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp+58h] BYREF

  bstrString = 0;
  v46 = 0;
  v3 = *(_QWORD *)a2;
  v47 = 0;
  HashData = (*(__int64 (__fastcall **)(struct IProcessModel *, __int16 *))(v3 + 144))(a2, &v46);
  if ( HashData < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_119;
    v6 = " Failed reading property \n";
    v7 = 454;
    goto LABEL_4;
  }
  v8 = g_dwDebugFlags;
  v9 = v46 == -1;
  v10 = (g_dwDebugFlags & 3) == 0;
  *((_DWORD *)this + 47) = v9;
  if ( !v10 && (v8 & 0x40000000) != 0 )
  {
    v11 = L"TRUE";
    if ( !v9 )
      v11 = L"FALSE";
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
      463,
      "APP_POOL_DATA_OBJECT_APPHOST::SetProcessModelSettingsFromConfigStoreData",
      " Ping Enabled = %S \n",
      v11);
  }
  HashData = (*(__int64 (__fastcall **)(struct IProcessModel *, __int64 *))(*(_QWORD *)a2 + 152LL))(a2, &v47);
  if ( HashData >= 0 )
  {
    v12 = v47 / 10000000;
    v13 = g_dwDebugFlags;
    v10 = (g_dwDebugFlags & 3) == 0;
    *((_DWORD *)this + 58) = v47 / 10000000;
    if ( !v10 && (v13 & 0x40000000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
        481,
        "APP_POOL_DATA_OBJECT_APPHOST::SetProcessModelSettingsFromConfigStoreData",
        " Ping Interval in seconds = %u (0x%X) (%d) \n",
        v12,
        v12,
        v45);
    v14 = *(_QWORD *)a2;
    v47 = 0;
    HashData = (*(__int64 (__fastcall **)(struct IProcessModel *, __int64 *))(v14 + 160))(a2, &v47);
    if ( HashData >= 0 )
    {
      v15 = v47 / 10000000;
      v16 = g_dwDebugFlags;
      v10 = (g_dwDebugFlags & 3) == 0;
      *((_DWORD *)this + 59) = v47 / 10000000;
      if ( !v10 && (v16 & 0x40000000) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
          500,
          "APP_POOL_DATA_OBJECT_APPHOST::SetProcessModelSettingsFromConfigStoreData",
          " Ping Response Time in seconds = %u (0x%X) \n",
          v15,
          v15);
      v17 = *(_QWORD *)a2;
      v47 = 0;
      HashData = (*(__int64 (__fastcall **)(struct IProcessModel *, __int64 *))(v17 + 136))(a2, &v47);
      if ( HashData >= 0 )
      {
        v18 = v47 / 10000000;
        v19 = g_dwDebugFlags;
        v10 = (g_dwDebugFlags & 3) == 0;
        *((_DWORD *)this + 56) = v47 / 10000000;
        if ( !v10 && (v19 & 0x40000000) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
            519,
            "APP_POOL_DATA_OBJECT_APPHOST::SetProcessModelSettingsFromConfigStoreData",
            " Startup Time Limit in seconds = %u (0x%X) \n",
            v18,
            v18);
        v20 = *(_QWORD *)a2;
        v47 = 0;
        HashData = (*(__int64 (__fastcall **)(struct IProcessModel *, __int64 *))(v20 + 128))(a2, &v47);
        if ( HashData >= 0 )
        {
          v21 = v47 / 10000000;
          v22 = g_dwDebugFlags;
          v10 = (g_dwDebugFlags & 3) == 0;
          *((_DWORD *)this + 57) = v47 / 10000000;
          if ( !v10 && (v22 & 0x40000000) != 0 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
              538,
              "APP_POOL_DATA_OBJECT_APPHOST::SetProcessModelSettingsFromConfigStoreData",
              " Shutdown Time Limit in seconds = %u (0x%X) \n",
              v21,
              v21);
          v23 = *(_QWORD *)a2;
          v47 = 0;
          HashData = (*(__int64 (__fastcall **)(struct IProcessModel *, __int64 *))(v23 + 112))(a2, &v47);
          if ( HashData >= 0 )
          {
            v24 = v47 / 10000000 / 60;
            v25 = g_dwDebugFlags;
            v10 = (g_dwDebugFlags & 3) == 0;
            *((_DWORD *)this + 45) = v24;
            if ( !v10 && (v25 & 0x40000000) != 0 )
              PuDbgPrint(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
                557,
                "APP_POOL_DATA_OBJECT_APPHOST::SetProcessModelSettingsFromConfigStoreData",
                " Idle Timeout in minutes = %u (0x%X) \n",
                v24,
                v24);
            HashData = (*(__int64 (__fastcall **)(struct IProcessModel *, char *))(*(_QWORD *)a2 + 176LL))(
                         a2,
                         (char *)this + 184);
            if ( HashData >= 0 )
            {
              if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
                PuDbgPrint(
                  g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
                  574,
                  "APP_POOL_DATA_OBJECT_APPHOST::SetProcessModelSettingsFromConfigStoreData",
                  " idleTimeoutAction = %u (0x%X) \n ",
                  *((_DWORD *)this + 46),
                  *((_DWORD *)this + 46));
              HashData = (*(__int64 (__fastcall **)(struct IProcessModel *, char *))(*(_QWORD *)a2 + 120LL))(
                           a2,
                           (char *)this + 176);
              if ( HashData >= 0 )
              {
                if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
                  PuDbgPrint(
                    g_pDebug,
                    "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
                    591,
                    "APP_POOL_DATA_OBJECT_APPHOST::SetProcessModelSettingsFromConfigStoreData",
                    " Max Processes = %u (0x%X) \n",
                    *((_DWORD *)this + 44),
                    *((_DWORD *)this + 44));
                HashData = (*(__int64 (__fastcall **)(struct IProcessModel *, char *))(*(_QWORD *)a2 + 56LL))(
                             a2,
                             (char *)this + 576);
                if ( HashData >= 0 )
                {
                  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
                    PuDbgPrint(
                      g_pDebug,
                      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
                      608,
                      "APP_POOL_DATA_OBJECT_APPHOST::SetProcessModelSettingsFromConfigStoreData",
                      " App Pool Identity = %u (0x%X) \n",
                      *((_DWORD *)this + 144),
                      *((_DWORD *)this + 144));
                  HashData = (*(__int64 (__fastcall **)(struct IProcessModel *, char *))(*(_QWORD *)a2 + 96LL))(
                               a2,
                               (char *)this + 924);
                  if ( HashData >= 0 )
                  {
                    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
                      PuDbgPrint(
                        g_pDebug,
                        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
                        625,
                        "APP_POOL_DATA_OBJECT_APPHOST::SetProcessModelSettingsFromConfigStoreData",
                        " App Pool Logon Type = %u (0x%X) \n",
                        *((_DWORD *)this + 231),
                        *((_DWORD *)this + 231));
                    HashData = (*(__int64 (__fastcall **)(struct IProcessModel *, BSTR *))(*(_QWORD *)a2 + 64LL))(
                                 a2,
                                 &bstrString);
                    if ( HashData >= 0 )
                    {
                      v26 = L"NULL";
                      if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
                      {
                        v27 = L"NULL";
                        if ( bstrString )
                          v27 = bstrString;
                        PuDbgPrint(
                          g_pDebug,
                          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
                          641,
                          "APP_POOL_DATA_OBJECT_APPHOST::SetProcessModelSettingsFromConfigStoreData",
                          " App Pool User Name = '%s' \n",
                          (const char *)v27);
                      }
                      if ( bstrString )
                      {
                        HashData = STRU::Copy((APP_POOL_DATA_OBJECT_APPHOST *)((char *)this + 368), bstrString);
                        if ( HashData < 0 )
                        {
                          if ( (g_dwDebugFlags & 0xF) != 0 )
                          {
                            v6 = " Failed copying string property \n";
                            v7 = 651;
                            goto LABEL_4;
                          }
                          goto LABEL_119;
                        }
                        SysFreeString(bstrString);
                        bstrString = 0;
                      }
                      v28 = 32;
                      v29 = (char *)this + 544;
                      do
                      {
                        *v29++ = 0;
                        --v28;
                      }
                      while ( v28 );
                      HashData = (*(__int64 (__fastcall **)(struct IProcessModel *, BSTR *))(*(_QWORD *)a2 + 72LL))(
                                   a2,
                                   &bstrString);
                      if ( HashData >= 0 )
                      {
                        if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
                        {
                          v30 = L"NULL";
                          if ( bstrString )
                            v30 = bstrString;
                          PuDbgPrint(
                            g_pDebug,
                            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
                            680,
                            "APP_POOL_DATA_OBJECT_APPHOST::SetProcessModelSettingsFromConfigStoreData",
                            " App Pool User pass = '%s' \n",
                            (const char *)v30);
                        }
                        if ( bstrString )
                        {
                          HashData = STRU::Copy((APP_POOL_DATA_OBJECT_APPHOST *)((char *)this + 424), bstrString);
                          if ( HashData < 0 )
                          {
                            if ( (g_dwDebugFlags & 0xF) != 0 )
                            {
                              v6 = " Failed copying string property \n";
                              v7 = 690;
                              goto LABEL_4;
                            }
                            goto LABEL_119;
                          }
                          SysFreeString(bstrString);
                          v31 = 2 * *((_DWORD *)this + 118);
                          v32 = (unsigned __int8 *)*((_QWORD *)this + 57);
                          bstrString = 0;
                          HashData = CONFIG_MANAGER::GetHashData(
                                       (WEB_ADMIN_SERVICE *)((char *)g_pWebAdminService + 704),
                                       v32,
                                       v31,
                                       (unsigned __int8 *)this + 544,
                                       v44);
                          if ( HashData < 0 )
                            goto LABEL_119;
                        }
                        HashData = (*(__int64 (__fastcall **)(struct IProcessModel *, BSTR *))(*(_QWORD *)a2 + 184LL))(
                                     a2,
                                     &bstrString);
                        if ( HashData >= 0 )
                        {
                          if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
                          {
                            if ( bstrString )
                              v26 = bstrString;
                            PuDbgPrint(
                              g_pDebug,
                              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
                              738,
                              "APP_POOL_DATA_OBJECT_APPHOST::SetProcessModelSettingsFromConfigStoreData",
                              " App Pool Request Queue Delegator Account = '%s' \n",
                              (const char *)v26);
                          }
                          if ( bstrString )
                          {
                            HashData = STRU::Copy((APP_POOL_DATA_OBJECT_APPHOST *)((char *)this + 480), bstrString);
                            if ( HashData < 0 )
                            {
                              if ( (g_dwDebugFlags & 0xF) != 0 )
                              {
                                v6 = " Failed copying string property \n";
                                v7 = 748;
                                goto LABEL_4;
                              }
                              goto LABEL_119;
                            }
                            SysFreeString(bstrString);
                            bstrString = 0;
                          }
                          v46 = 0;
                          HashData = (*(__int64 (__fastcall **)(struct IProcessModel *, __int16 *))(*(_QWORD *)a2 + 80LL))(
                                       a2,
                                       &v46);
                          if ( HashData >= 0 )
                          {
                            v33 = g_dwDebugFlags;
                            v34 = "FALSE";
                            v35 = "TRUE";
                            v36 = v46 == -1;
                            v10 = (g_dwDebugFlags & 3) == 0;
                            *((_DWORD *)this + 134) = v36;
                            if ( !v10 && (v33 & 0x40000000) != 0 )
                            {
                              v37 = "TRUE";
                              if ( !v36 )
                                v37 = "FALSE";
                              PuDbgPrint(
                                g_pDebug,
                                "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
                                771,
                                "APP_POOL_DATA_OBJECT_APPHOST::SetProcessModelSettingsFromConfigStoreData",
                                " LoadUserProfile = %s \n",
                                v37);
                            }
                            v46 = 0;
                            HashData = (*(__int64 (__fastcall **)(struct IProcessModel *, __int16 *, const char *))(*(_QWORD *)a2 + 88LL))(
                                         a2,
                                         &v46,
                                         v34);
                            if ( HashData >= 0 )
                            {
                              v38 = g_dwDebugFlags;
                              v39 = v46 == -1;
                              v10 = (g_dwDebugFlags & 3) == 0;
                              *((_DWORD *)this + 233) = v39;
                              if ( !v10 && (v38 & 0x40000000) != 0 )
                              {
                                v40 = "TRUE";
                                if ( !v39 )
                                  v40 = "FALSE";
                                PuDbgPrint(
                                  g_pDebug,
                                  "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
                                  789,
                                  "APP_POOL_DATA_OBJECT_APPHOST::SetProcessModelSettingsFromConfigStoreData",
                                  " SetProfileEnvironment = %s \n",
                                  v40);
                              }
                              v46 = 0;
                              HashData = (*(__int64 (__fastcall **)(struct IProcessModel *, __int16 *))(*(_QWORD *)a2 + 104LL))(
                                           a2,
                                           &v46);
                              if ( HashData >= 0 )
                              {
                                v41 = g_dwDebugFlags;
                                v42 = v46 == -1;
                                v10 = (g_dwDebugFlags & 3) == 0;
                                *((_DWORD *)this + 135) = v42;
                                if ( !v10 && (v41 & 0x40000000) != 0 )
                                {
                                  if ( !v42 )
                                    v35 = "FALSE";
                                  PuDbgPrint(
                                    g_pDebug,
                                    "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
                                    807,
                                    "APP_POOL_DATA_OBJECT_APPHOST::SetProcessModelSettingsFromConfigStoreData",
                                    " _fManualGroupMembership = %s \n",
                                    v35);
                                }
                                HashData = (*(__int64 (__fastcall **)(struct IProcessModel *, char *))(*(_QWORD *)a2 + 168LL))(
                                             a2,
                                             (char *)this + 728);
                                if ( HashData >= 0 )
                                {
                                  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
                                    PuDbgPrint(
                                      g_pDebug,
                                      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
                                      823,
                                      "APP_POOL_DATA_OBJECT_APPHOST::SetProcessModelSettingsFromConfigStoreData",
                                      " App Pool logEventOnProcessModel  = %u (0x%X) \n",
                                      *((_DWORD *)this + 182),
                                      *((_DWORD *)this + 182));
                                }
                                else if ( (g_dwDebugFlags & 0xF) != 0 )
                                {
                                  v6 = " Failed reading CS_PROCESS_MODEL_LOG_EVENT_ON_PROCESS_MODEL property \n";
                                  v7 = 815;
                                  goto LABEL_4;
                                }
                              }
                              else if ( (g_dwDebugFlags & 0xF) != 0 )
                              {
                                v6 = " Failed reading CS_PROCESS_MODEL_MANUAL_GROUP_MEMBERSHIP property \n";
                                v7 = 798;
                                goto LABEL_4;
                              }
                            }
                            else if ( (g_dwDebugFlags & 0xF) != 0 )
                            {
                              v6 = " Failed reading CS_PROCESS_MODEL_SET_PROFILE_ENVIRONMENT property \n";
                              v7 = 780;
                              goto LABEL_4;
                            }
                          }
                          else if ( (g_dwDebugFlags & 0xF) != 0 )
                          {
                            v6 = " Failed reading CS_PROCESS_MODEL_LOAD_USER_PROFILE property \n";
                            v7 = 762;
                            goto LABEL_4;
                          }
                          goto LABEL_119;
                        }
                        if ( (g_dwDebugFlags & 0xF) != 0 )
                        {
                          v7 = 730;
                          goto LABEL_12;
                        }
                      }
                      else if ( (g_dwDebugFlags & 0xF) != 0 )
                      {
                        v7 = 672;
                        goto LABEL_12;
                      }
                    }
                    else if ( (g_dwDebugFlags & 0xF) != 0 )
                    {
                      v7 = 633;
                      goto LABEL_12;
                    }
                  }
                  else if ( (g_dwDebugFlags & 0xF) != 0 )
                  {
                    v7 = 616;
                    goto LABEL_12;
                  }
                }
                else if ( (g_dwDebugFlags & 0xF) != 0 )
                {
                  v7 = 599;
                  goto LABEL_12;
                }
              }
              else if ( (g_dwDebugFlags & 0xF) != 0 )
              {
                v7 = 582;
                goto LABEL_12;
              }
            }
            else if ( (g_dwDebugFlags & 0xF) != 0 )
            {
              v7 = 565;
              goto LABEL_12;
            }
          }
          else if ( (g_dwDebugFlags & 0xF) != 0 )
          {
            v7 = 547;
            goto LABEL_12;
          }
        }
        else if ( (g_dwDebugFlags & 0xF) != 0 )
        {
          v7 = 528;
          goto LABEL_12;
        }
      }
      else if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        v7 = 509;
        goto LABEL_12;
      }
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      v7 = 490;
      goto LABEL_12;
    }
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    v7 = 471;
LABEL_12:
    v6 = " Failed reading property \n";
LABEL_4:
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
      v7,
      "APP_POOL_DATA_OBJECT_APPHOST::SetProcessModelSettingsFromConfigStoreData",
      HashData,
      v6);
  }
LABEL_119:
  if ( bstrString )
    SysFreeString(bstrString);
  return (unsigned int)HashData;
}

```

## disassembly

```asm
0x18004acd4  mov     [rsp-38h+arg_0], rbx
0x18004acd9  push    rbp
0x18004acda  push    rsi
0x18004acdb  push    rdi
0x18004acdc  push    r12
0x18004acde  push    r13
0x18004ace0  push    r14
0x18004ace2  push    r15
0x18004ace4  mov     rbp, rsp
0x18004ace7  sub     rsp, 40h
0x18004aceb  xor     eax, eax
0x18004aced  mov     [rbp+bstrString], 0
0x18004acf5  mov     [rbp+arg_8], ax
0x18004acf9  mov     r14, rdx
0x18004acfc  mov     rax, [rdx]
0x18004acff  mov     r15, rcx
0x18004ad02  lea     rdx, [rbp+arg_8]
0x18004ad06  mov     [rbp+arg_10], 0
0x18004ad0e  mov     rcx, r14
0x18004ad11  mov     rax, [rax+90h]
0x18004ad18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ad1d  mov     ebx, eax
0x18004ad1f  test    eax, eax
0x18004ad21  jns     short loc_18004AD66
0x18004ad23  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004ad2a  jz      loc_18004B84E
0x18004ad30  lea     rax, aFailedReadingP_1; " Failed reading property \n"
0x18004ad37  mov     r8d, 1C6h
0x18004ad3d  lea     r9, aAppPoolDataObj_16; "APP_POOL_DATA_OBJECT_APPHOST::SetProces"...
0x18004ad44  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18004ad4b  mov     rcx, cs:g_pDebug
0x18004ad52  mov     [rsp+40h+var_18], rax
0x18004ad57  mov     [rsp+40h+var_20], ebx
0x18004ad5b  call    cs:__imp_PuDbgPrintError
0x18004ad61  jmp     loc_18004B84E
0x18004ad66  mov     eax, cs:g_dwDebugFlags
0x18004ad6c  lea     rdi, aAppPoolDataObj_16; "APP_POOL_DATA_OBJECT_APPHOST::SetProces"...
0x18004ad73  xor     edx, edx
0x18004ad75  lea     rsi, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18004ad7c  cmp     [rbp+arg_8], 0FFFFh
0x18004ad81  mov     r13b, 3
0x18004ad84  setz    dl
0x18004ad87  test    r13b, al
0x18004ad8a  mov     [r15+0BCh], edx
0x18004ad91  setnz   cl
0x18004ad94  bt      eax, 1Eh
0x18004ad98  setb    al
0x18004ad9b  test    al, cl
0x18004ad9d  jz      short loc_18004ADDD
0x18004ad9f  test    edx, edx
0x18004ada1  lea     rcx, aFalse_1; "FALSE"
0x18004ada8  lea     rax, aTrue_1; "TRUE"
0x18004adaf  mov     r9, rdi
0x18004adb2  cmovz   rax, rcx
0x18004adb6  mov     r8d, 1CFh
0x18004adbc  mov     rcx, cs:g_pDebug
0x18004adc3  mov     rdx, rsi
0x18004adc6  mov     [rsp+40h+var_18], rax
0x18004adcb  lea     rax, aPingEnabledS; " Ping Enabled = %S \n"
0x18004add2  mov     qword ptr [rsp+40h+var_20], rax
0x18004add7  call    cs:__imp_PuDbgPrint
0x18004addd  mov     rax, [r14]
0x18004ade0  lea     rdx, [rbp+arg_10]
0x18004ade4  mov     rcx, r14
0x18004ade7  mov     rax, [rax+98h]
0x18004adee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004adf3  mov     ebx, eax
0x18004adf5  test    eax, eax
0x18004adf7  jns     short loc_18004AE1E
0x18004adf9  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004ae00  jz      loc_18004B84E
0x18004ae06  mov     r8d, 1D7h
0x18004ae0c  lea     rax, aFailedReadingP_1; " Failed reading property \n"
0x18004ae13  mov     r9, rdi
0x18004ae16  mov     rdx, rsi
0x18004ae19  jmp     loc_18004AD4B
0x18004ae1e  mov     r12, 0D6BF94D5E57A42BDh
0x18004ae28  mov     rax, r12
0x18004ae2b  imul    [rbp+arg_10]
0x18004ae2f  add     rdx, [rbp+arg_10]
0x18004ae33  sar     rdx, 17h
0x18004ae37  mov     rax, rdx
0x18004ae3a  shr     rax, 3Fh
0x18004ae3e  add     rdx, rax
0x18004ae41  mov     eax, cs:g_dwDebugFlags
0x18004ae47  test    r13b, al
0x18004ae4a  mov     [r15+0E8h], edx
0x18004ae51  setnz   cl
0x18004ae54  bt      eax, 1Eh
0x18004ae58  setb    al
0x18004ae5b  test    al, cl
0x18004ae5d  jz      short loc_18004AE8C
0x18004ae5f  mov     rcx, cs:g_pDebug
0x18004ae66  lea     rax, aPingIntervalIn; " Ping Interval in seconds = %u (0x%X) ("...
0x18004ae6d  mov     [rsp+40h+var_10], edx
0x18004ae71  mov     r9, rdi
0x18004ae74  mov     dword ptr [rsp+40h+var_18], edx
0x18004ae78  mov     r8d, 1E1h
0x18004ae7e  mov     rdx, rsi
0x18004ae81  mov     qword ptr [rsp+40h+var_20], rax
0x18004ae86  call    cs:__imp_PuDbgPrint
0x18004ae8c  mov     rax, [r14]
0x18004ae8f  lea     rdx, [rbp+arg_10]
0x18004ae93  mov     rcx, r14
0x18004ae96  mov     [rbp+arg_10], 0
0x18004ae9e  mov     rax, [rax+0A0h]
0x18004aea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aeaa  mov     ebx, eax
0x18004aeac  test    eax, eax
0x18004aeae  jns     short loc_18004AEC8
0x18004aeb0  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004aeb7  jz      loc_18004B84E
0x18004aebd  mov     r8d, 1EAh
0x18004aec3  jmp     loc_18004AE0C
0x18004aec8  mov     rax, r12
0x18004aecb  imul    [rbp+arg_10]
0x18004aecf  add     rdx, [rbp+arg_10]
0x18004aed3  sar     rdx, 17h
0x18004aed7  mov     rax, rdx
0x18004aeda  shr     rax, 3Fh
0x18004aede  add     rdx, rax
0x18004aee1  mov     eax, cs:g_dwDebugFlags
0x18004aee7  test    r13b, al
0x18004aeea  mov     [r15+0ECh], edx
0x18004aef1  setnz   cl
0x18004aef4  bt      eax, 1Eh
0x18004aef8  setb    al
0x18004aefb  test    al, cl
0x18004aefd  jz      short loc_18004AF2C
0x18004aeff  mov     rcx, cs:g_pDebug
0x18004af06  lea     rax, aPingResponseTi; " Ping Response Time in seconds = %u (0x"...
0x18004af0d  mov     [rsp+40h+var_10], edx
0x18004af11  mov     r9, rdi
0x18004af14  mov     dword ptr [rsp+40h+var_18], edx
0x18004af18  mov     r8d, 1F4h
0x18004af1e  mov     rdx, rsi
0x18004af21  mov     qword ptr [rsp+40h+var_20], rax
0x18004af26  call    cs:__imp_PuDbgPrint
0x18004af2c  mov     rax, [r14]
0x18004af2f  lea     rdx, [rbp+arg_10]
0x18004af33  mov     rcx, r14
0x18004af36  mov     [rbp+arg_10], 0
0x18004af3e  mov     rax, [rax+88h]
0x18004af45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004af4a  mov     ebx, eax
0x18004af4c  test    eax, eax
0x18004af4e  jns     short loc_18004AF68
0x18004af50  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004af57  jz      loc_18004B84E
0x18004af5d  mov     r8d, 1FDh
0x18004af63  jmp     loc_18004AE0C
0x18004af68  mov     rax, r12
0x18004af6b  imul    [rbp+arg_10]
0x18004af6f  add     rdx, [rbp+arg_10]
0x18004af73  sar     rdx, 17h
0x18004af77  mov     rax, rdx
0x18004af7a  shr     rax, 3Fh
0x18004af7e  add     rdx, rax
0x18004af81  mov     eax, cs:g_dwDebugFlags
0x18004af87  test    r13b, al
0x18004af8a  mov     [r15+0E0h], edx
0x18004af91  setnz   cl
0x18004af94  bt      eax, 1Eh
0x18004af98  setb    al
0x18004af9b  test    al, cl
0x18004af9d  jz      short loc_18004AFCC
0x18004af9f  mov     rcx, cs:g_pDebug
0x18004afa6  lea     rax, aStartupTimeLim; " Startup Time Limit in seconds = %u (0x"...
0x18004afad  mov     [rsp+40h+var_10], edx
0x18004afb1  mov     r9, rdi
0x18004afb4  mov     dword ptr [rsp+40h+var_18], edx
0x18004afb8  mov     r8d, 207h
0x18004afbe  mov     rdx, rsi
0x18004afc1  mov     qword ptr [rsp+40h+var_20], rax
0x18004afc6  call    cs:__imp_PuDbgPrint
0x18004afcc  mov     rax, [r14]
0x18004afcf  lea     rdx, [rbp+arg_10]
0x18004afd3  mov     rcx, r14
0x18004afd6  mov     [rbp+arg_10], 0
0x18004afde  mov     rax, [rax+80h]
0x18004afe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004afea  mov     ebx, eax
0x18004afec  test    eax, eax
0x18004afee  jns     short loc_18004B008
0x18004aff0  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004aff7  jz      loc_18004B84E
0x18004affd  mov     r8d, 210h
0x18004b003  jmp     loc_18004AE0C
0x18004b008  mov     rax, r12
0x18004b00b  imul    [rbp+arg_10]
0x18004b00f  add     rdx, [rbp+arg_10]
0x18004b013  sar     rdx, 17h
0x18004b017  mov     rax, rdx
0x18004b01a  shr     rax, 3Fh
0x18004b01e  add     rdx, rax
0x18004b021  mov     eax, cs:g_dwDebugFlags
0x18004b027  test    r13b, al
0x18004b02a  mov     [r15+0E4h], edx
0x18004b031  setnz   cl
0x18004b034  bt      eax, 1Eh
0x18004b038  setb    al
0x18004b03b  test    al, cl
0x18004b03d  jz      short loc_18004B06C
0x18004b03f  mov     rcx, cs:g_pDebug
0x18004b046  lea     rax, aShutdownTimeLi; " Shutdown Time Limit in seconds = %u (0"...
0x18004b04d  mov     [rsp+40h+var_10], edx
0x18004b051  mov     r9, rdi
0x18004b054  mov     dword ptr [rsp+40h+var_18], edx
0x18004b058  mov     r8d, 21Ah
0x18004b05e  mov     rdx, rsi
0x18004b061  mov     qword ptr [rsp+40h+var_20], rax
0x18004b066  call    cs:__imp_PuDbgPrint
0x18004b06c  mov     rax, [r14]
0x18004b06f  lea     rdx, [rbp+arg_10]
0x18004b073  mov     rcx, r14
0x18004b076  mov     [rbp+arg_10], 0
0x18004b07e  mov     rax, [rax+70h]
0x18004b082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b087  mov     ebx, eax
0x18004b089  test    eax, eax
0x18004b08b  jns     short loc_18004B0A5
0x18004b08d  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004b094  jz      loc_18004B84E
0x18004b09a  mov     r8d, 223h
0x18004b0a0  jmp     loc_18004AE0C
0x18004b0a5  mov     rax, r12
0x18004b0a8  imul    [rbp+arg_10]
0x18004b0ac  mov     rcx, rdx
0x18004b0af  add     rcx, [rbp+arg_10]
0x18004b0b3  sar     rcx, 17h
0x18004b0b7  mov     rax, rcx
0x18004b0ba  shr     rax, 3Fh
0x18004b0be  add     rcx, rax
0x18004b0c1  mov     rax, 8888888888888889h
0x18004b0cb  imul    rcx
0x18004b0ce  add     rdx, rcx
0x18004b0d1  sar     rdx, 5
0x18004b0d5  mov     rax, rdx
0x18004b0d8  shr     rax, 3Fh
0x18004b0dc  add     rdx, rax
0x18004b0df  mov     eax, cs:g_dwDebugFlags
0x18004b0e5  test    r13b, al
0x18004b0e8  mov     [r15+0B4h], edx
0x18004b0ef  setnz   cl
0x18004b0f2  bt      eax, 1Eh
0x18004b0f6  setb    al
0x18004b0f9  test    al, cl
0x18004b0fb  jz      short loc_18004B12A
0x18004b0fd  mov     rcx, cs:g_pDebug
0x18004b104  lea     rax, aIdleTimeoutInM; " Idle Timeout in minutes = %u (0x%X) \n"
0x18004b10b  mov     [rsp+40h+var_10], edx
0x18004b10f  mov     r9, rdi
0x18004b112  mov     dword ptr [rsp+40h+var_18], edx
0x18004b116  mov     r8d, 22Dh
0x18004b11c  mov     rdx, rsi
0x18004b11f  mov     qword ptr [rsp+40h+var_20], rax
0x18004b124  call    cs:__imp_PuDbgPrint
0x18004b12a  mov     rax, [r14]
0x18004b12d  lea     r12, [r15+0B8h]
0x18004b134  mov     rdx, r12
0x18004b137  mov     rcx, r14
0x18004b13a  mov     rax, [rax+0B0h]
0x18004b141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b146  mov     ebx, eax
0x18004b148  test    eax, eax
0x18004b14a  jns     short loc_18004B164
0x18004b14c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004b153  jz      loc_18004B84E
0x18004b159  mov     r8d, 235h
0x18004b15f  jmp     loc_18004AE0C
0x18004b164  mov     eax, cs:g_dwDebugFlags
0x18004b16a  test    r13b, al
0x18004b16d  setnz   cl
0x18004b170  bt      eax, 1Eh
0x18004b174  setb    al
0x18004b177  test    al, cl
0x18004b179  jz      short loc_18004B1AC
0x18004b17b  mov     eax, [r12]
0x18004b17f  mov     r9, rdi
0x18004b182  mov     rcx, cs:g_pDebug
0x18004b189  mov     r8d, 23Eh
0x18004b18f  mov     [rsp+40h+var_10], eax
0x18004b193  mov     rdx, rsi
0x18004b196  mov     dword ptr [rsp+40h+var_18], eax
0x18004b19a  lea     rax, aIdletimeoutact_0; " idleTimeoutAction = %u (0x%X) \n "
0x18004b1a1  mov     qword ptr [rsp+40h+var_20], rax
0x18004b1a6  call    cs:__imp_PuDbgPrint
0x18004b1ac  mov     rax, [r14]
0x18004b1af  lea     r12, [r15+0B0h]
0x18004b1b6  mov     rdx, r12
0x18004b1b9  mov     rcx, r14
0x18004b1bc  mov     rax, [rax+78h]
0x18004b1c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b1c5  mov     ebx, eax
0x18004b1c7  test    eax, eax
0x18004b1c9  jns     short loc_18004B1E3
0x18004b1cb  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004b1d2  jz      loc_18004B84E
0x18004b1d8  mov     r8d, 246h
0x18004b1de  jmp     loc_18004AE0C
  ... truncated ...
```
