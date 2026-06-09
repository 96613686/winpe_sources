# GLOBAL_DATA_OBJECT_CS::SetLoggingFromConfigStoreData(INativeConfigurationElement *)

- ea: `0x180042e74`
- end: `0x180043c7a`
- name: `?SetLoggingFromConfigStoreData@GLOBAL_DATA_OBJECT_CS@@QEAAJPEAVINativeConfigurationElement@@@Z`
- size: `3590`
- prototype: `__int64 __fastcall(GLOBAL_DATA_OBJECT_CS *__hidden this, struct INativeConfigurationElement *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180042730`

## callees

- `0x180042e74`
- `0x180052d90`
- `0x180052ec4`
- `0x180052f8c`
- `0x18005310c`
- `0x180053908`
- `0x180062010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180042fe2`
- `iisutil!PuDbgPrint` at `0x1800430eb`
- `iisutil!PuDbgPrint` at `0x18004324b`
- `iisutil!PuDbgPrint` at `0x180043332`
- `iisutil!PuDbgPrint` at `0x180043424`
- `iisutil!PuDbgPrint` at `0x180043519`
- `iisutil!PuDbgPrint` at `0x180043645`
- `iisutil!PuDbgPrint` at `0x1800437c5`
- `iisutil!PuDbgPrint` at `0x1800438ab`
- `iisutil!PuDbgPrint` at `0x18004398b`
- `iisutil!PuDbgPrint` at `0x180043a69`
- `iisutil!PuDbgPrint` at `0x180043b94`
- `iisutil!PuDbgPrint` at `0x180042fe2`
- `iisutil!PuDbgPrint` at `0x1800430eb`
- `iisutil!PuDbgPrint` at `0x18004324b`
- `iisutil!PuDbgPrint` at `0x180043332`
- `iisutil!PuDbgPrint` at `0x180043424`
- `iisutil!PuDbgPrint` at `0x180043519`
- `iisutil!PuDbgPrint` at `0x180043645`
- `iisutil!PuDbgPrint` at `0x1800437c5`
- `iisutil!PuDbgPrint` at `0x1800438ab`
- `iisutil!PuDbgPrint` at `0x18004398b`
- `iisutil!PuDbgPrint` at `0x180043a69`
- `iisutil!PuDbgPrint` at `0x180043b94`
- `iisutil!PuDbgPrintError` at `0x180042f1e`
- `iisutil!PuDbgPrintError` at `0x180042f1e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004352c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180043a7f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004352c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180043a7f`

## string_xrefs

- `0x180042ef3`: ` Failed reading property \n`
- `0x18004302c`: ` Failed reading property \n`
- `0x180042f10`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\globalstore_cs.cxx`
- `0x180042f90`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\globalstore_cs.cxx`
- `0x180042f05`: `GLOBAL_DATA_OBJECT_CS::SetLoggingFromConfigStoreData`
- `0x180042f87`: `GLOBAL_DATA_OBJECT_CS::SetLoggingFromConfigStoreData`
- `0x18004343f`: `directory`
- `0x18004347d`: `directory`
- `0x1800439a2`: `directory`
- `0x1800439e0`: `directory`
- `0x180043501`: ` Binary Log File Directory  = '%S' \n`
- `0x180043a58`: ` W3C log File Directory  = '%S' \n`

## pseudocode

```c
__int64 __fastcall GLOBAL_DATA_OBJECT_CS::SetLoggingFromConfigStoreData(
        GLOBAL_DATA_OBJECT_CS *this,
        struct INativeConfigurationElement *a2)
{
  __int64 v2; // rax
  unsigned int *v3; // r15
  __int64 (__fastcall *v6)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD); // rax
  int v7; // ebx
  __int64 v8; // r8
  struct CONFIG_ERROR *v9; // rdx
  const wchar_t *v10; // rax
  int *v11; // r15
  const char *v12; // rax
  struct CONFIG_ERROR *v13; // rdx
  const wchar_t *v14; // rax
  struct CONFIG_ERROR *v15; // rdx
  unsigned int *v16; // r15
  struct CONFIG_ERROR *v17; // rdx
  const unsigned __int16 *v18; // rdx
  struct CONFIG_ERROR *v19; // rdx
  int v20; // eax
  int v21; // edx
  bool v22; // cl
  struct CONFIG_ERROR *v23; // rdx
  unsigned __int16 *v24; // r13
  unsigned __int16 *v25; // rcx
  int *v26; // r15
  struct CONFIG_ERROR *v27; // rdx
  const wchar_t *v28; // rax
  int *v29; // r15
  struct CONFIG_ERROR *v30; // rdx
  const wchar_t *v31; // r12
  const wchar_t *v32; // rax
  unsigned int *v33; // r15
  struct CONFIG_ERROR *v34; // rdx
  const unsigned __int16 *v35; // rdx
  struct CONFIG_ERROR *v36; // rdx
  int v37; // eax
  int v38; // edx
  bool v39; // cl
  struct CONFIG_ERROR *v40; // rdx
  int *v41; // r15
  struct CONFIG_ERROR *v42; // rdx
  struct CONFIG_ERROR *v43; // rdx
  int v45; // [rsp+20h] [rbp-38h]
  const char *v46; // [rsp+28h] [rbp-30h]
  __int64 v47[3]; // [rsp+40h] [rbp-18h] BYREF
  struct INativePropertyException *v48; // [rsp+A0h] [rbp+48h] BYREF
  struct CONFIG_ERROR *v49; // [rsp+A8h] [rbp+50h] BYREF
  __int64 v50; // [rsp+B0h] [rbp+58h] BYREF
  unsigned __int16 *v51; // [rsp+B8h] [rbp+60h] BYREF

  v2 = *(_QWORD *)a2;
  v3 = (unsigned int *)((char *)this + 64);
  v51 = 0;
  v47[0] = 0;
  v50 = 0;
  v6 = *(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(v2 + 48);
  v48 = 0;
  v49 = 0;
  v7 = v6(a2, L"centralLogFileMode", (char *)this + 64, &v48, 0);
  if ( v7 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_157;
    v8 = 314;
    v46 = " Failed reading property \n";
    v45 = v7;
    goto LABEL_4;
  }
  if ( v48 )
  {
    CONFIG_ERROR::CreateAndInitWithLong(&v49, L"centralLogFileMode", *v3, v48);
    v9 = v49;
    if ( v49 )
    {
      *((_DWORD *)v49 + 2) = 52;
      CONFIG_ERROR_LIST::Add((GLOBAL_DATA_OBJECT_CS *)((char *)this + 224), v9);
    }
    v49 = 0;
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v48 + 16LL))(v48);
    v48 = 0;
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
  {
    v10 = L"TRUE";
    if ( !*v3 )
      v10 = L"FALSE";
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\globalstore_cs.cxx",
      336,
      "GLOBAL_DATA_OBJECT_CS::SetLoggingFromConfigStoreData",
      " Central logging mode  = %d \n",
      (_DWORD)v10);
  }
  v11 = (int *)((char *)this + 76);
  v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 72LL))(
         a2,
         L"logInUTF8",
         (char *)this + 76,
         &v48,
         0);
  if ( v7 >= 0 )
  {
    if ( v48 )
    {
      CONFIG_ERROR::CreateAndInitWithBool(&v49, L"logInUTF8", *v11, v48);
      v13 = v49;
      if ( v49 )
      {
        *((_DWORD *)v49 + 2) = 61;
        CONFIG_ERROR_LIST::Add((GLOBAL_DATA_OBJECT_CS *)((char *)this + 224), v13);
      }
      v49 = 0;
      (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v48 + 16LL))(v48);
      v48 = 0;
    }
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
    {
      v14 = L"TRUE";
      if ( !*v11 )
        v14 = L"FALSE";
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\globalstore_cs.cxx",
        368,
        "GLOBAL_DATA_OBJECT_CS::SetLoggingFromConfigStoreData",
        " Log In utf 8  = %S \n",
        v14);
    }
    v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, __int64 *))(*(_QWORD *)a2 + 32LL))(
           a2,
           L"centralBinaryLogFile",
           &v50);
    if ( v7 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        v12 = " Failed to get binary logging settings for global data \n";
        v8 = 377;
        goto LABEL_17;
      }
      goto LABEL_157;
    }
    if ( !v50 )
    {
      v7 = -2147467259;
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_159;
      v8 = 388;
      v46 = " Failed to set limits for central logging data \n";
      v45 = -2147467259;
      goto LABEL_4;
    }
    v7 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)v50 + 72LL))(
           v50,
           L"enabled",
           (char *)this + 68,
           &v48,
           0);
    if ( v7 >= 0 )
    {
      if ( v48 )
      {
        CONFIG_ERROR::CreateAndInitWithBool(&v49, L"enabled", *((_DWORD *)this + 17), v48);
        v15 = v49;
        if ( v49 )
        {
          *((_DWORD *)v49 + 2) = 59;
          CONFIG_ERROR_LIST::Add((GLOBAL_DATA_OBJECT_CS *)((char *)this + 224), v15);
        }
        v49 = 0;
        (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v48 + 16LL))(v48);
        v48 = 0;
      }
      if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\globalstore_cs.cxx",
          421,
          "GLOBAL_DATA_OBJECT_CS::SetLoggingFromConfigStoreData",
          " Binary central logging enabled  = %S \n",
          L"FALSE");
      v16 = (unsigned int *)((char *)this + 136);
      v7 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)v50 + 48LL))(
             v50,
             L"period",
             (char *)this + 136,
             &v48,
             0);
      if ( v7 >= 0 )
      {
        if ( v48 )
        {
          CONFIG_ERROR::CreateAndInitWithLong(&v49, L"period", *v16, v48);
          v17 = v49;
          if ( v49 )
          {
            *((_DWORD *)v49 + 2) = 63;
            CONFIG_ERROR_LIST::Add((GLOBAL_DATA_OBJECT_CS *)((char *)this + 224), v17);
          }
          v49 = 0;
          (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v48 + 16LL))(v48);
          v48 = 0;
        }
        if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\globalstore_cs.cxx",
            453,
            "GLOBAL_DATA_OBJECT_CS::SetLoggingFromConfigStoreData",
            " Binary Log File Period = %u \n",
            *v16);
        v7 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64 *, struct INativePropertyException **, _QWORD))(*(_QWORD *)v50 + 56LL))(
               v50,
               L"truncateSize",
               v47,
               &v48,
               0);
        if ( v7 >= 0 )
        {
          if ( v48 )
          {
            CONFIG_ERROR::CreateAndInitWithInt64(&v49, v18, v47[0], v48);
            v19 = v49;
            if ( v49 )
            {
              *((_DWORD *)v49 + 2) = 64;
              CONFIG_ERROR_LIST::Add((GLOBAL_DATA_OBJECT_CS *)((char *)this + 224), v19);
            }
            v49 = 0;
            (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v48 + 16LL))(v48);
            v48 = 0;
          }
          v20 = g_dwDebugFlags;
          v21 = v47[0];
          v22 = (g_dwDebugFlags & 3) != 0;
          *((_DWORD *)this + 35) = v47[0];
          v47[0] = 0;
          if ( v22 && (v20 & 0x40000000) != 0 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\globalstore_cs.cxx",
              492,
              "GLOBAL_DATA_OBJECT_CS::SetLoggingFromConfigStoreData",
              " Binary Log File Trucate Size = %u (0x%X) (%d) \n",
              v21,
              v21,
              v21);
          v7 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned __int16 **, struct INativePropertyException **, _QWORD))(*(_QWORD *)v50 + 64LL))(
                 v50,
                 L"directory",
                 &v51,
                 &v48,
                 0);
          if ( v7 >= 0 )
          {
            if ( v48 )
            {
              CONFIG_ERROR::CreateAndInitWithString(&v49, L"directory", v51, v48);
              v23 = v49;
              if ( v49 )
              {
                *((_DWORD *)v49 + 2) = 62;
                CONFIG_ERROR_LIST::Add((GLOBAL_DATA_OBJECT_CS *)((char *)this + 224), v23);
              }
              v49 = 0;
              (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v48 + 16LL))(v48);
              v48 = 0;
            }
            v24 = L"NULL";
            if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
            {
              v25 = L"NULL";
              if ( v51 )
                v25 = v51;
              PuDbgPrint(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\globalstore_cs.cxx",
                524,
                "GLOBAL_DATA_OBJECT_CS::SetLoggingFromConfigStoreData",
                " Binary Log File Directory  = '%S' \n",
                v25);
            }
            if ( v51 )
            {
              v7 = STRU::Copy((GLOBAL_DATA_OBJECT_CS *)((char *)this + 80), v51);
              if ( v7 < 0 )
              {
                if ( (g_dwDebugFlags & 0xF) != 0 )
                {
                  v8 = 534;
                  goto LABEL_16;
                }
                goto LABEL_157;
              }
              v51 = 0;
            }
            v26 = (int *)((char *)this + 144);
            v7 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)v50 + 72LL))(
                   v50,
                   L"localTimeRollover",
                   (char *)this + 144,
                   &v48,
                   0);
            if ( v7 >= 0 )
            {
              if ( v48 )
              {
                CONFIG_ERROR::CreateAndInitWithBool(&v49, L"localTimeRollover", *v26, v48);
                v27 = v49;
                if ( v49 )
                {
                  *((_DWORD *)v49 + 2) = 65;
                  CONFIG_ERROR_LIST::Add((GLOBAL_DATA_OBJECT_CS *)((char *)this + 224), v27);
                }
                v49 = 0;
                (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v48 + 16LL))(v48);
                v48 = 0;
              }
              if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
              {
                v28 = L"TRUE";
                if ( !*v26 )
                  v28 = L"FALSE";
                PuDbgPrint(
                  g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\globalstore_cs.cxx",
                  569,
                  "GLOBAL_DATA_OBJECT_CS::SetLoggingFromConfigStoreData",
                  " Binary log local time rollover = %S \n",
                  v28);
              }
              if ( v50 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
                v50 = 0;
              }
              v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, __int64 *))(*(_QWORD *)a2 + 32LL))(
                     a2,
                     L"centralW3CLogFile",
                     &v50);
              if ( v7 < 0 )
              {
                if ( (g_dwDebugFlags & 0xF) != 0 )
                {
                  v12 = " Failed to get w3c logging settings for global data \n";
                  v8 = 585;
                  goto LABEL_17;
                }
                goto LABEL_157;
              }
              if ( !v50 )
              {
                v7 = -2147467259;
                if ( (g_dwDebugFlags & 0xF) == 0 )
                  goto LABEL_159;
                v8 = 596;
                v46 = " Failed to set limits for central logging data \n";
                v45 = -2147467259;
                goto LABEL_4;
              }
              v29 = (int *)((char *)this + 72);
              v7 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)v50 + 72LL))(
                     v50,
                     L"enabled",
                     (char *)this + 72,
                     &v48,
                     0);
              if ( v7 >= 0 )
              {
                if ( v48 )
                {
                  CONFIG_ERROR::CreateAndInitWithBool(&v49, L"enabled", *v29, v48);
                  v30 = v49;
                  if ( v49 )
                  {
                    *((_DWORD *)v49 + 2) = 60;
                    CONFIG_ERROR_LIST::Add((GLOBAL_DATA_OBJECT_CS *)((char *)this + 224), v30);
                  }
                  v49 = 0;
                  (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v48 + 16LL))(v48);
                  v48 = 0;
                }
                v31 = L"TRUE";
                if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
                {
                  v32 = L"TRUE";
                  if ( !*v29 )
                    v32 = L"FALSE";
                  PuDbgPrint(
                    g_pDebug,
                    "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\globalstore_cs.cxx",
                    629,
                    "GLOBAL_DATA_OBJECT_CS::SetLoggingFromConfigStoreData",
                    " W3C central logging enabled  = %S \n",
                    v32);
                }
                v33 = (unsigned int *)((char *)this + 208);
                v7 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)v50 + 48LL))(
                       v50,
                       L"period",
                       (char *)this + 208,
                       &v48,
                       0);
                if ( v7 >= 0 )
                {
                  if ( v48 )
                  {
                    CONFIG_ERROR::CreateAndInitWithLong(&v49, L"period", *v33, v48);
                    v34 = v49;
                    if ( v49 )
                    {
                      *((_DWORD *)v49 + 2) = 67;
                      CONFIG_ERROR_LIST::Add((GLOBAL_DATA_OBJECT_CS *)((char *)this + 224), v34);
                    }
                    v49 = 0;
                    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v48 + 16LL))(v48);
                    v48 = 0;
                  }
                  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
                    PuDbgPrint(
                      g_pDebug,
                      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\globalstore_cs.cxx",
                      661,
                      "GLOBAL_DATA_OBJECT_CS::SetLoggingFromConfigStoreData",
                      " W3C log File Period = %u \n",
                      *v33);
                  v7 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64 *, struct INativePropertyException **, _QWORD))(*(_QWORD *)v50 + 56LL))(
                         v50,
                         L"truncateSize",
                         v47,
                         &v48,
                         0);
                  if ( v7 >= 0 )
                  {
                    if ( v48 )
                    {
                      CONFIG_ERROR::CreateAndInitWithInt64(&v49, v35, v47[0], v48);
                      v36 = v49;
                      if ( v49 )
                      {
                        *((_DWORD *)v49 + 2) = 68;
                        CONFIG_ERROR_LIST::Add((GLOBAL_DATA_OBJECT_CS *)((char *)this + 224), v36);
                      }
                      v49 = 0;
                      (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v48 + 16LL))(v48);
                      v48 = 0;
                    }
                    v37 = g_dwDebugFlags;
                    v38 = v47[0];
                    v39 = (g_dwDebugFlags & 3) != 0;
                    *((_DWORD *)this + 53) = v47[0];
                    if ( v39 && (v37 & 0x40000000) != 0 )
                      PuDbgPrint(
                        g_pDebug,
                        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\globalstore_cs.cxx",
                        699,
                        "GLOBAL_DATA_OBJECT_CS::SetLoggingFromConfigStoreData",
                        " W3C log File Trucate Size = %u (0x%X) (%d) \n",
                        v38,
                        v38,
                        v38);
                    v7 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned __int16 **, struct INativePropertyException **, _QWORD))(*(_QWORD *)v50 + 64LL))(
                           v50,
                           L"directory",
                           &v51,
                           &v48,
                           0);
                    if ( v7 >= 0 )
                    {
                      if ( v48 )
                      {
                        CONFIG_ERROR::CreateAndInitWithString(&v49, L"directory", v51, v48);
                        v40 = v49;
                        if ( v49 )
                        {
                          *((_DWORD *)v49 + 2) = 66;
                          CONFIG_ERROR_LIST::Add((GLOBAL_DATA_OBJECT_CS *)((char *)this + 224), v40);
                        }
                        v49 = 0;
                        (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v48 + 16LL))(v48);
                        v48 = 0;
                      }
                      if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
                      {
                        if ( v51 )
                          v24 = v51;
                        PuDbgPrint(
                          g_pDebug,
                          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\globalstore_cs.cxx",
                          731,
                          "GLOBAL_DATA_OBJECT_CS::SetLoggingFromConfigStoreData",
                          " W3C log File Directory  = '%S' \n",
                          v24);
                      }
                      if ( v51 )
                      {
                        v7 = STRU::Copy((GLOBAL_DATA_OBJECT_CS *)((char *)this + 152), v51);
                        if ( v7 < 0 )
                        {
                          if ( (g_dwDebugFlags & 0xF) != 0 )
                          {
                            v8 = 741;
                            goto LABEL_16;
                          }
                          goto LABEL_157;
                        }
                        v51 = 0;
                      }
                      v41 = (int *)((char *)this + 216);
                      v7 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)v50 + 72LL))(
                             v50,
                             L"localTimeRollover",
                             (char *)this + 216,
                             &v48,
                             0);
                      if ( v7 >= 0 )
                      {
                        if ( v48 )
                        {
                          CONFIG_ERROR::CreateAndInitWithBool(&v49, L"localTimeRollover", *v41, v48);
                          v42 = v49;
                          if ( v49 )
                          {
                            *((_DWORD *)v49 + 2) = 69;
                            CONFIG_ERROR_LIST::Add((GLOBAL_DATA_OBJECT_CS *)((char *)this + 224), v42);
                          }
                          v49 = 0;
                          (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v48 + 16LL))(v48);
                          v48 = 0;
                        }
                        if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
                        {
                          if ( !*v41 )
                            v31 = L"FALSE";
                          PuDbgPrint(
                            g_pDebug,
                            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\globalstore_cs.cxx",
                            776,
                            "GLOBAL_DATA_OBJECT_CS::SetLoggingFromConfigStoreData",
                            " W3C Log local time rollover = %S \n",
                            v31);
                        }
                        v7 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)v50 + 48LL))(
                               v50,
                               L"logExtFileFlags",
                               (char *)this + 220,
                               &v48,
                               0);
                        if ( v7 >= 0 )
                        {
                          if ( v48 )
                          {
                            CONFIG_ERROR::CreateAndInitWithLong(&v49, L"logExtFileFlags", *((_DWORD *)this + 55), v48);
                            v43 = v49;
                            if ( v49 )
                            {
                              *((_DWORD *)v49 + 2) = 70;
                              CONFIG_ERROR_LIST::Add((GLOBAL_DATA_OBJECT_CS *)((char *)this + 224), v43);
                            }
                            (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v48 + 16LL))(v48);
                            v48 = 0;
                          }
                          goto LABEL_157;
                        }
                        if ( (g_dwDebugFlags & 0xF) != 0 )
                        {
                          v8 = 786;
                          goto LABEL_16;
                        }
                      }
                      else if ( (g_dwDebugFlags & 0xF) != 0 )
                      {
                        v8 = 754;
                        goto LABEL_16;
                      }
                      goto LABEL_157;
                    }
                    if ( (g_dwDebugFlags & 0xF) != 0 )
                    {
                      v8 = 709;
                      goto LABEL_16;
                    }
                  }
                  else if ( (g_dwDebugFlags & 0xF) != 0 )
                  {
                    v8 = 671;
                    goto LABEL_16;
                  }
                }
                else if ( (g_dwDebugFlags & 0xF) != 0 )
                {
                  v8 = 639;
                  goto LABEL_16;
                }
              }
              else if ( (g_dwDebugFlags & 0xF) != 0 )
              {
                v8 = 607;
                goto LABEL_16;
              }
            }
            else if ( (g_dwDebugFlags & 0xF) != 0 )
            {
              v8 = 547;
              goto LABEL_16;
            }
          }
          else if ( (g_dwDebugFlags & 0xF) != 0 )
          {
            v8 = 502;
            goto LABEL_16;
          }
        }
        else if ( (g_dwDebugFlags & 0xF) != 0 )
        {
          v8 = 463;
          goto LABEL_16;
        }
      }
      else if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        v8 = 431;
        goto LABEL_16;
      }
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      v8 = 399;
      goto LABEL_16;
    }
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    v8 = 346;
LABEL_16:
    v12 = " Failed reading property \n";
LABEL_17:
    v46 = v12;
    v45 = v7;
LABEL_4:
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\globalstore_cs.cxx",
      v8,
      "GLOBAL_DATA_OBJECT_CS::SetLoggingFromConfigStoreData",
      v45,
      v46);
  }
LABEL_157:
  if ( v50 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    v50 = 0;
  }
LABEL_159:
  if ( v48 )
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v48 + 16LL))(v48);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180042e74  push    rbp
0x180042e76  push    rbx
0x180042e77  push    rsi
0x180042e78  push    rdi
0x180042e79  push    r12
0x180042e7b  push    r13
0x180042e7d  push    r14
0x180042e7f  push    r15
0x180042e81  mov     rbp, rsp
0x180042e84  sub     rsp, 58h
0x180042e88  mov     rax, [rdx]
0x180042e8b  lea     r15, [rcx+40h]
0x180042e8f  mov     r12, rdx
0x180042e92  mov     [rbp+arg_18], 0
0x180042e9a  mov     r14, rcx
0x180042e9d  mov     [rbp+var_18], 0
0x180042ea5  lea     r9, [rbp+arg_0]
0x180042ea9  mov     [rbp+arg_10], 0
0x180042eb1  mov     rax, [rax+30h]
0x180042eb5  lea     rdx, aCentrallogfile; "centralLogFileMode"
0x180042ebc  mov     r8, r15
0x180042ebf  mov     [rbp+arg_0], 0
0x180042ec7  mov     rcx, r12
0x180042eca  mov     [rbp+arg_8], 0
0x180042ed2  mov     [rsp+58h+var_38], 0
0x180042edb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042ee0  mov     ebx, eax
0x180042ee2  test    eax, eax
0x180042ee4  jns     short loc_180042F29
0x180042ee6  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180042eed  jz      loc_180043C35
0x180042ef3  lea     rax, aFailedReadingP_1; " Failed reading property \n"
0x180042efa  mov     r8d, 13Ah
0x180042f00  mov     [rsp+58h+var_30], rax
0x180042f05  lea     r9, aGlobalDataObje; "GLOBAL_DATA_OBJECT_CS::SetLoggingFromCo"...
0x180042f0c  mov     dword ptr [rsp+58h+var_38], ebx
0x180042f10  lea     rdx, aServercommonIn_19; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180042f17  mov     rcx, cs:g_pDebug
0x180042f1e  call    cs:__imp_PuDbgPrintError
0x180042f24  jmp     loc_180043C35
0x180042f29  mov     r9, [rbp+arg_0]; struct INativePropertyException *
0x180042f2d  test    r9, r9
0x180042f30  jz      short loc_180042F81
0x180042f32  mov     r8d, [r15]; int
0x180042f35  lea     rdx, aCentrallogfile; "centralLogFileMode"
0x180042f3c  lea     rcx, [rbp+arg_8]; struct CONFIG_ERROR **
0x180042f40  call    ?CreateAndInitWithLong@CONFIG_ERROR@@SAXPEAPEAV1@PEBGJPEAVINativePropertyException@@@Z; CONFIG_ERROR::CreateAndInitWithLong(CONFIG_ERROR * *,ushort const *,long,INativePropertyException *)
0x180042f45  mov     rdx, [rbp+arg_8]; struct CONFIG_ERROR *
0x180042f49  test    rdx, rdx
0x180042f4c  jz      short loc_180042F61
0x180042f4e  lea     rcx, [r14+0E0h]; this
0x180042f55  mov     dword ptr [rdx+8], 34h ; '4'
0x180042f5c  call    ?Add@CONFIG_ERROR_LIST@@QEAAXPEAVCONFIG_ERROR@@@Z; CONFIG_ERROR_LIST::Add(CONFIG_ERROR *)
0x180042f61  mov     rcx, [rbp+arg_0]
0x180042f65  mov     [rbp+arg_8], 0
0x180042f6d  mov     rax, [rcx]
0x180042f70  mov     rax, [rax+10h]
0x180042f74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042f79  mov     [rbp+arg_0], 0
0x180042f81  mov     eax, cs:g_dwDebugFlags
0x180042f87  lea     rdi, aGlobalDataObje; "GLOBAL_DATA_OBJECT_CS::SetLoggingFromCo"...
0x180042f8e  test    al, 3
0x180042f90  lea     rsi, aServercommonIn_19; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180042f97  lea     rdx, aFalse_1; "FALSE"
0x180042f9e  setnz   cl
0x180042fa1  lea     r13, aTrue_1; "TRUE"
0x180042fa8  bt      eax, 1Eh
0x180042fac  setb    al
0x180042faf  test    al, cl
0x180042fb1  jz      short loc_180042FE8
0x180042fb3  cmp     dword ptr [r15], 0
0x180042fb7  mov     rax, r13
0x180042fba  mov     rcx, cs:g_pDebug
0x180042fc1  mov     r9, rdi
0x180042fc4  cmovz   rax, rdx
0x180042fc8  mov     r8d, 150h
0x180042fce  mov     [rsp+58h+var_30], rax
0x180042fd3  mov     rdx, rsi
0x180042fd6  lea     rax, aCentralLogging; " Central logging mode  = %d \n"
0x180042fdd  mov     [rsp+58h+var_38], rax
0x180042fe2  call    cs:__imp_PuDbgPrint
0x180042fe8  mov     rax, [r12]
0x180042fec  lea     r15, [r14+4Ch]
0x180042ff0  lea     r9, [rbp+arg_0]
0x180042ff4  mov     [rsp+58h+var_38], 0
0x180042ffd  mov     r8, r15
0x180043000  lea     rdx, aLoginutf8; "logInUTF8"
0x180043007  mov     rcx, r12
0x18004300a  mov     rax, [rax+48h]
0x18004300e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043013  mov     ebx, eax
0x180043015  test    eax, eax
0x180043017  jns     short loc_180043047
0x180043019  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180043020  jz      loc_180043C35
0x180043026  mov     r8d, 15Ah
0x18004302c  lea     rax, aFailedReadingP_1; " Failed reading property \n"
0x180043033  mov     [rsp+58h+var_30], rax
0x180043038  mov     dword ptr [rsp+58h+var_38], ebx
0x18004303c  mov     r9, rdi
0x18004303f  mov     rdx, rsi
0x180043042  jmp     loc_180042F17
0x180043047  mov     r9, [rbp+arg_0]; struct INativePropertyException *
0x18004304b  test    r9, r9
0x18004304e  jz      short loc_18004309F
0x180043050  mov     r8d, [r15]; int
0x180043053  lea     rdx, aLoginutf8; "logInUTF8"
0x18004305a  lea     rcx, [rbp+arg_8]; struct CONFIG_ERROR **
0x18004305e  call    ?CreateAndInitWithBool@CONFIG_ERROR@@SAXPEAPEAV1@PEBGHPEAVINativePropertyException@@@Z; CONFIG_ERROR::CreateAndInitWithBool(CONFIG_ERROR * *,ushort const *,int,INativePropertyException *)
0x180043063  mov     rdx, [rbp+arg_8]; struct CONFIG_ERROR *
0x180043067  test    rdx, rdx
0x18004306a  jz      short loc_18004307F
0x18004306c  lea     rcx, [r14+0E0h]; this
0x180043073  mov     dword ptr [rdx+8], 3Dh ; '='
0x18004307a  call    ?Add@CONFIG_ERROR_LIST@@QEAAXPEAVCONFIG_ERROR@@@Z; CONFIG_ERROR_LIST::Add(CONFIG_ERROR *)
0x18004307f  mov     rcx, [rbp+arg_0]
0x180043083  mov     [rbp+arg_8], 0
0x18004308b  mov     rax, [rcx]
0x18004308e  mov     rax, [rax+10h]
0x180043092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043097  mov     [rbp+arg_0], 0
0x18004309f  mov     eax, cs:g_dwDebugFlags
0x1800430a5  test    al, 3
0x1800430a7  setnz   cl
0x1800430aa  bt      eax, 1Eh
0x1800430ae  setb    al
0x1800430b1  test    al, cl
0x1800430b3  jz      short loc_1800430F1
0x1800430b5  cmp     dword ptr [r15], 0
0x1800430b9  lea     rcx, aFalse_1; "FALSE"
0x1800430c0  mov     rax, r13
0x1800430c3  mov     r9, rdi
0x1800430c6  cmovz   rax, rcx
0x1800430ca  mov     r8d, 170h
0x1800430d0  mov     rcx, cs:g_pDebug
0x1800430d7  mov     rdx, rsi
0x1800430da  mov     [rsp+58h+var_30], rax
0x1800430df  lea     rax, aLogInUtf8S; " Log In utf 8  = %S \n"
0x1800430e6  mov     [rsp+58h+var_38], rax
0x1800430eb  call    cs:__imp_PuDbgPrint
0x1800430f1  mov     rax, [r12]
0x1800430f5  lea     r8, [rbp+arg_10]
0x1800430f9  lea     rdx, aCentralbinaryl; "centralBinaryLogFile"
0x180043100  mov     rcx, r12
0x180043103  mov     rax, [rax+20h]
0x180043107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004310c  mov     ebx, eax
0x18004310e  test    eax, eax
0x180043110  jns     short loc_180043131
0x180043112  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180043119  jz      loc_180043C35
0x18004311f  lea     rax, aFailedToGetBin; " Failed to get binary logging settings "...
0x180043126  mov     r8d, 179h
0x18004312c  jmp     loc_180043033
0x180043131  mov     rcx, [rbp+arg_10]
0x180043135  test    rcx, rcx
0x180043138  jnz     short loc_18004316B
0x18004313a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180043141  mov     ebx, 80004005h
0x180043146  jz      loc_180043C52
0x18004314c  lea     rax, aFailedToSetLim; " Failed to set limits for central loggi"...
0x180043153  mov     r8d, 184h
0x180043159  mov     [rsp+58h+var_30], rax
0x18004315e  mov     dword ptr [rsp+58h+var_38], 80004005h
0x180043166  jmp     loc_18004303C
0x18004316b  mov     rax, [rcx]
0x18004316e  lea     r9, [rbp+arg_0]
0x180043172  lea     r8, [r14+44h]
0x180043176  mov     [rsp+58h+var_38], 0
0x18004317f  lea     rdx, aEnabled; "enabled"
0x180043186  mov     rax, [rax+48h]
0x18004318a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004318f  mov     ebx, eax
0x180043191  test    eax, eax
0x180043193  jns     short loc_1800431AD
0x180043195  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004319c  jz      loc_180043C35
0x1800431a2  mov     r8d, 18Fh
0x1800431a8  jmp     loc_18004302C
0x1800431ad  mov     r9, [rbp+arg_0]; struct INativePropertyException *
0x1800431b1  test    r9, r9
0x1800431b4  jz      short loc_180043206
0x1800431b6  mov     r8d, [r14+44h]; int
0x1800431ba  lea     rdx, aEnabled; "enabled"
0x1800431c1  lea     rcx, [rbp+arg_8]; struct CONFIG_ERROR **
0x1800431c5  call    ?CreateAndInitWithBool@CONFIG_ERROR@@SAXPEAPEAV1@PEBGHPEAVINativePropertyException@@@Z; CONFIG_ERROR::CreateAndInitWithBool(CONFIG_ERROR * *,ushort const *,int,INativePropertyException *)
0x1800431ca  mov     rdx, [rbp+arg_8]; struct CONFIG_ERROR *
0x1800431ce  test    rdx, rdx
0x1800431d1  jz      short loc_1800431E6
0x1800431d3  lea     rcx, [r14+0E0h]; this
0x1800431da  mov     dword ptr [rdx+8], 3Bh ; ';'
0x1800431e1  call    ?Add@CONFIG_ERROR_LIST@@QEAAXPEAVCONFIG_ERROR@@@Z; CONFIG_ERROR_LIST::Add(CONFIG_ERROR *)
0x1800431e6  mov     rcx, [rbp+arg_0]
0x1800431ea  mov     [rbp+arg_8], 0
0x1800431f2  mov     rax, [rcx]
0x1800431f5  mov     rax, [rax+10h]
0x1800431f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800431fe  mov     [rbp+arg_0], 0
0x180043206  mov     eax, cs:g_dwDebugFlags
0x18004320c  mov     r13b, 3
0x18004320f  test    r13b, al
0x180043212  setnz   cl
0x180043215  bt      eax, 1Eh
0x180043219  setb    al
0x18004321c  test    al, cl
0x18004321e  jz      short loc_180043251
0x180043220  mov     rcx, cs:g_pDebug
0x180043227  lea     rax, aFalse_1; "FALSE"
0x18004322e  mov     [rsp+58h+var_30], rax
0x180043233  mov     r9, rdi
0x180043236  lea     rax, aBinaryCentralL; " Binary central logging enabled  = %S "...
0x18004323d  mov     r8d, 1A5h
0x180043243  mov     rdx, rsi
0x180043246  mov     [rsp+58h+var_38], rax
0x18004324b  call    cs:__imp_PuDbgPrint
0x180043251  mov     rcx, [rbp+arg_10]
0x180043255  lea     r15, [r14+88h]
0x18004325c  lea     r9, [rbp+arg_0]
0x180043260  mov     [rsp+58h+var_38], 0
0x180043269  mov     r8, r15
0x18004326c  lea     rdx, aPeriod; "period"
0x180043273  mov     rax, [rcx]
0x180043276  mov     rax, [rax+30h]
0x18004327a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004327f  mov     ebx, eax
0x180043281  test    eax, eax
0x180043283  jns     short loc_18004329D
0x180043285  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004328c  jz      loc_180043C35
0x180043292  mov     r8d, 1AFh
0x180043298  jmp     loc_18004302C
0x18004329d  mov     r9, [rbp+arg_0]; struct INativePropertyException *
0x1800432a1  test    r9, r9
0x1800432a4  jz      short loc_1800432F5
0x1800432a6  mov     r8d, [r15]; int
0x1800432a9  lea     rdx, aPeriod; "period"
0x1800432b0  lea     rcx, [rbp+arg_8]; struct CONFIG_ERROR **
0x1800432b4  call    ?CreateAndInitWithLong@CONFIG_ERROR@@SAXPEAPEAV1@PEBGJPEAVINativePropertyException@@@Z; CONFIG_ERROR::CreateAndInitWithLong(CONFIG_ERROR * *,ushort const *,long,INativePropertyException *)
0x1800432b9  mov     rdx, [rbp+arg_8]; struct CONFIG_ERROR *
0x1800432bd  test    rdx, rdx
0x1800432c0  jz      short loc_1800432D5
0x1800432c2  lea     rcx, [r14+0E0h]; this
0x1800432c9  mov     dword ptr [rdx+8], 3Fh ; '?'
0x1800432d0  call    ?Add@CONFIG_ERROR_LIST@@QEAAXPEAVCONFIG_ERROR@@@Z; CONFIG_ERROR_LIST::Add(CONFIG_ERROR *)
0x1800432d5  mov     rcx, [rbp+arg_0]
0x1800432d9  mov     [rbp+arg_8], 0
0x1800432e1  mov     rax, [rcx]
0x1800432e4  mov     rax, [rax+10h]
0x1800432e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800432ed  mov     [rbp+arg_0], 0
0x1800432f5  mov     eax, cs:g_dwDebugFlags
0x1800432fb  test    r13b, al
0x1800432fe  setnz   cl
0x180043301  bt      eax, 1Eh
0x180043305  setb    al
0x180043308  test    al, cl
0x18004330a  jz      short loc_180043338
0x18004330c  mov     eax, [r15]
0x18004330f  mov     r9, rdi
0x180043312  mov     rcx, cs:g_pDebug
0x180043319  mov     r8d, 1C5h
0x18004331f  mov     dword ptr [rsp+58h+var_30], eax
0x180043323  mov     rdx, rsi
0x180043326  lea     rax, aBinaryLogFileP; " Binary Log File Period = %u \n"
0x18004332d  mov     [rsp+58h+var_38], rax
0x180043332  call    cs:__imp_PuDbgPrint
0x180043338  mov     rcx, [rbp+arg_10]
0x18004333c  lea     r9, [rbp+arg_0]
0x180043340  lea     r8, [rbp+var_18]
0x180043344  mov     [rsp+58h+var_38], 0
0x18004334d  lea     rdx, aTruncatesize; "truncateSize"
0x180043354  mov     rax, [rcx]
0x180043357  mov     rax, [rax+38h]
0x18004335b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043360  mov     ebx, eax
0x180043362  test    eax, eax
0x180043364  jns     short loc_18004337E
0x180043366  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004336d  jz      loc_180043C35
0x180043373  mov     r8d, 1CFh
0x180043379  jmp     loc_18004302C
0x18004337e  mov     r9, [rbp+arg_0]; struct INativePropertyException *
0x180043382  test    r9, r9
0x180043385  jz      short loc_1800433D0
0x180043387  mov     r8, [rbp+var_18]; __int64
0x18004338b  lea     rcx, [rbp+arg_8]; struct CONFIG_ERROR **
0x18004338f  call    ?CreateAndInitWithInt64@CONFIG_ERROR@@SAXPEAPEAV1@PEBG_JPEAVINativePropertyException@@@Z; CONFIG_ERROR::CreateAndInitWithInt64(CONFIG_ERROR * *,ushort const *,__int64,INativePropertyException *)
0x180043394  mov     rdx, [rbp+arg_8]; struct CONFIG_ERROR *
0x180043398  test    rdx, rdx
0x18004339b  jz      short loc_1800433B0
0x18004339d  lea     rcx, [r14+0E0h]; this
0x1800433a4  mov     dword ptr [rdx+8], 40h ; '@'
0x1800433ab  call    ?Add@CONFIG_ERROR_LIST@@QEAAXPEAVCONFIG_ERROR@@@Z; CONFIG_ERROR_LIST::Add(CONFIG_ERROR *)
0x1800433b0  mov     rcx, [rbp+arg_0]
0x1800433b4  mov     [rbp+arg_8], 0
0x1800433bc  mov     rax, [rcx]
0x1800433bf  mov     rax, [rax+10h]
0x1800433c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800433c8  mov     [rbp+arg_0], 0
0x1800433d0  mov     eax, cs:g_dwDebugFlags
  ... truncated ...
```
