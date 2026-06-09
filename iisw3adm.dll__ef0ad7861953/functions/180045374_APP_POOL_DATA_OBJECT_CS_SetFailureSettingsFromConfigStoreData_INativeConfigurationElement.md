# APP_POOL_DATA_OBJECT_CS::SetFailureSettingsFromConfigStoreData(INativeConfigurationElement *)

- ea: `0x180045374`
- end: `0x180045da9`
- name: `?SetFailureSettingsFromConfigStoreData@APP_POOL_DATA_OBJECT_CS@@QEAAJPEAVINativeConfigurationElement@@@Z`
- size: `2613`
- prototype: `__int64 __fastcall(APP_POOL_DATA_OBJECT_CS *__hidden this, struct INativeConfigurationElement *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180044950`

## callees

- `0x180045374`
- `0x180052d90`
- `0x180052f8c`
- `0x18005304c`
- `0x18005310c`
- `0x180053908`
- `0x180062010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x1800453e6`
- `iisutil!PuDbgPrint` at `0x1800454e6`
- `iisutil!PuDbgPrint` at `0x1800455e0`
- `iisutil!PuDbgPrint` at `0x1800456d9`
- `iisutil!PuDbgPrint` at `0x1800457fc`
- `iisutil!PuDbgPrint` at `0x18004591f`
- `iisutil!PuDbgPrint` at `0x180045a3f`
- `iisutil!PuDbgPrint` at `0x180045b6a`
- `iisutil!PuDbgPrint` at `0x180045c98`
- `iisutil!PuDbgPrint` at `0x180045d7b`
- `iisutil!PuDbgPrint` at `0x1800453e6`
- `iisutil!PuDbgPrint` at `0x1800454e6`
- `iisutil!PuDbgPrint` at `0x1800455e0`
- `iisutil!PuDbgPrint` at `0x1800456d9`
- `iisutil!PuDbgPrint` at `0x1800457fc`
- `iisutil!PuDbgPrint` at `0x18004591f`
- `iisutil!PuDbgPrint` at `0x180045a3f`
- `iisutil!PuDbgPrint` at `0x180045b6a`
- `iisutil!PuDbgPrint` at `0x180045c98`
- `iisutil!PuDbgPrint` at `0x180045d7b`
- `iisutil!PuDbgPrintError` at `0x18004544b`
- `iisutil!PuDbgPrintError` at `0x18004544b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800456ef`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180045812`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180045935`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180045a55`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800456ef`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180045812`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180045935`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180045a55`

## string_xrefs

- `0x180045528`: ` Failed reading property \n`
- `0x180045622`: ` Failed reading property \n`
- `0x180045baf`: ` Failed reading property \n`
- `0x180045cda`: ` Failed reading property \n`
- `0x180045398`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\apppoolstore_cs.cxx`
- `0x1800455cd`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\apppoolstore_cs.cxx`
- `0x180045629`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\apppoolstore_cs.cxx`
- `0x1800456a7`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\apppoolstore_cs.cxx`
- `0x1800457ca`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\apppoolstore_cs.cxx`
- `0x1800458ed`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\apppoolstore_cs.cxx`
- `0x180045a10`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\apppoolstore_cs.cxx`
- `0x180045b5b`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\apppoolstore_cs.cxx`
- `0x180045b72`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\apppoolstore_cs.cxx`
- `0x180045708`: ` Failed copying string property \n`
- `0x18004582b`: ` Failed copying string property \n`
- `0x18004594e`: ` Failed copying string property \n`
- `0x180045a6e`: ` Failed copying string property \n`
- `0x18004538e`: `APP_POOL_DATA_OBJECT_CS::SetFailureSettingsFromConfigStoreData`
- `0x180045428`: ` Failed reading load balancer capabilities property \n`

## pseudocode

```c
__int64 __fastcall APP_POOL_DATA_OBJECT_CS::SetFailureSettingsFromConfigStoreData(
        APP_POOL_DATA_OBJECT_CS *this,
        struct INativeConfigurationElement *a2)
{
  unsigned int *v4; // r14
  int v5; // ebx
  const char *v6; // rax
  __int64 v7; // r8
  struct CONFIG_ERROR *v8; // rdx
  int *v9; // r14
  struct CONFIG_ERROR *v10; // rdx
  const wchar_t *v11; // r15
  const wchar_t *v12; // rax
  struct CONFIG_ERROR *v13; // rdx
  unsigned __int16 *v14; // r14
  unsigned __int16 *v15; // rcx
  struct CONFIG_ERROR *v16; // rdx
  unsigned __int16 *v17; // rcx
  struct CONFIG_ERROR *v18; // rdx
  unsigned __int16 *v19; // rcx
  struct CONFIG_ERROR *v20; // rdx
  int *v21; // r14
  struct CONFIG_ERROR *v22; // rdx
  __int64 v23; // r8
  struct INativePropertyException *v24; // r9
  struct CONFIG_ERROR *v25; // rdx
  unsigned int *v26; // r14
  struct CONFIG_ERROR *v27; // rdx
  struct INativePropertyException *v29; // [rsp+90h] [rbp+48h] BYREF
  struct CONFIG_ERROR *v30; // [rsp+98h] [rbp+50h] BYREF
  unsigned __int16 *v31; // [rsp+A0h] [rbp+58h] BYREF
  __int64 v32; // [rsp+A8h] [rbp+60h] BYREF

  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
      1439,
      "APP_POOL_DATA_OBJECT_CS::SetFailureSettingsFromConfigStoreData",
      " Getting the Capabilities \n");
  v4 = (unsigned int *)((char *)this + 720);
  v5 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 48LL))(
         a2,
         L"loadBalancerCapabilities",
         (char *)this + 720,
         &v29,
         0);
  if ( v5 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_118;
    v6 = " Failed reading load balancer capabilities property \n";
    v7 = 1449;
    goto LABEL_6;
  }
  if ( v29 )
  {
    CONFIG_ERROR::CreateAndInitWithLong(&v30, L"loadBalancerCapabilities", *v4, v29);
    v8 = v30;
    if ( v30 )
    {
      *((_DWORD *)v30 + 2) = 39;
      CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v8);
    }
    v30 = 0;
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v29 + 16LL))(v29);
    v29 = 0;
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
      1471,
      "APP_POOL_DATA_OBJECT_CS::SetFailureSettingsFromConfigStoreData",
      " Load Balancer Type = %u (0x%X) \n",
      *v4,
      *v4);
  v9 = (int *)((char *)this + 220);
  v5 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 72LL))(
         a2,
         L"orphanWorkerProcess",
         (char *)this + 220,
         &v29,
         0);
  if ( v5 >= 0 )
  {
    if ( v29 )
    {
      CONFIG_ERROR::CreateAndInitWithBool(&v30, L"orphanWorkerProcess", *v9, v29);
      v10 = v30;
      if ( v30 )
      {
        *((_DWORD *)v30 + 2) = 14;
        CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v10);
      }
      v30 = 0;
      (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v29 + 16LL))(v29);
      v29 = 0;
    }
    v11 = L"TRUE";
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
    {
      v12 = L"TRUE";
      if ( !*v9 )
        v12 = L"FALSE";
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
        1502,
        "APP_POOL_DATA_OBJECT_CS::SetFailureSettingsFromConfigStoreData",
        " Orphan WP %S \n",
        v12);
    }
    v5 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, unsigned __int16 **, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 64LL))(
           a2,
           L"orphanActionExe",
           &v31,
           &v29,
           0);
    if ( v5 >= 0 )
    {
      if ( v29 )
      {
        CONFIG_ERROR::CreateAndInitWithString(&v30, L"orphanActionExe", v31, v29);
        v13 = v30;
        if ( v30 )
        {
          *((_DWORD *)v30 + 2) = 20;
          CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v13);
        }
        v30 = 0;
        (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v29 + 16LL))(v29);
        v29 = 0;
      }
      v14 = L"NULL";
      if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
      {
        v15 = L"NULL";
        if ( v31 )
          v15 = v31;
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
          1533,
          "APP_POOL_DATA_OBJECT_CS::SetFailureSettingsFromConfigStoreData",
          " Oprhan Exe = '%s' \n",
          (const char *)v15);
      }
      if ( v31 )
      {
        v5 = STRU::Copy((APP_POOL_DATA_OBJECT_CS *)((char *)this + 248), v31);
        if ( v5 < 0 )
        {
          if ( (g_dwDebugFlags & 0xF) != 0 )
          {
            v6 = " Failed copying string property \n";
            v7 = 1543;
            goto LABEL_6;
          }
          goto LABEL_118;
        }
        v31 = 0;
      }
      v5 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, unsigned __int16 **, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 64LL))(
             a2,
             L"orphanActionParams",
             &v31,
             &v29,
             0);
      if ( v5 >= 0 )
      {
        if ( v29 )
        {
          CONFIG_ERROR::CreateAndInitWithString(&v30, L"orphanActionParams", v31, v29);
          v16 = v30;
          if ( v30 )
          {
            *((_DWORD *)v30 + 2) = 21;
            CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v16);
          }
          v30 = 0;
          (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v29 + 16LL))(v29);
          v29 = 0;
        }
        if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
        {
          v17 = L"NULL";
          if ( v31 )
            v17 = v31;
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
            1577,
            "APP_POOL_DATA_OBJECT_CS::SetFailureSettingsFromConfigStoreData",
            " Orphan Arguments = '%s' \n",
            (const char *)v17);
        }
        if ( v31 )
        {
          v5 = STRU::Copy((APP_POOL_DATA_OBJECT_CS *)((char *)this + 304), v31);
          if ( v5 < 0 )
          {
            if ( (g_dwDebugFlags & 0xF) != 0 )
            {
              v6 = " Failed copying string property \n";
              v7 = 1587;
              goto LABEL_6;
            }
            goto LABEL_118;
          }
          v31 = 0;
        }
        v5 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, unsigned __int16 **, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 64LL))(
               a2,
               L"autoShutdownExe",
               &v31,
               &v29,
               0);
        if ( v5 >= 0 )
        {
          if ( v29 )
          {
            CONFIG_ERROR::CreateAndInitWithString(&v30, L"autoShutdownExe", v31, v29);
            v18 = v30;
            if ( v30 )
            {
              *((_DWORD *)v30 + 2) = 37;
              CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v18);
            }
            v30 = 0;
            (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v29 + 16LL))(v29);
            v29 = 0;
          }
          if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
          {
            v19 = L"NULL";
            if ( v31 )
              v19 = v31;
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
              1622,
              "APP_POOL_DATA_OBJECT_CS::SetFailureSettingsFromConfigStoreData",
              " Auto Shutdown Exe = '%s' \n",
              (const char *)v19);
          }
          if ( v31 )
          {
            v5 = STRU::Copy((APP_POOL_DATA_OBJECT_CS *)((char *)this + 608), v31);
            if ( v5 < 0 )
            {
              if ( (g_dwDebugFlags & 0xF) != 0 )
              {
                v6 = " Failed copying string property \n";
                v7 = 1632;
                goto LABEL_6;
              }
              goto LABEL_118;
            }
            v31 = 0;
          }
          v5 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, unsigned __int16 **, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 64LL))(
                 a2,
                 L"autoShutdownParams",
                 &v31,
                 &v29,
                 0);
          if ( v5 >= 0 )
          {
            if ( v29 )
            {
              CONFIG_ERROR::CreateAndInitWithString(&v30, L"autoShutdownParams", v31, v29);
              v20 = v30;
              if ( v30 )
              {
                *((_DWORD *)v30 + 2) = 38;
                CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v20);
              }
              v30 = 0;
              (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v29 + 16LL))(v29);
              v29 = 0;
            }
            if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
            {
              if ( v31 )
                v14 = v31;
              PuDbgPrint(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
                1667,
                "APP_POOL_DATA_OBJECT_CS::SetFailureSettingsFromConfigStoreData",
                " Auto Shutdown arguments = '%s' \n",
                (const char *)v14);
            }
            if ( v31 )
            {
              v5 = STRU::Copy((APP_POOL_DATA_OBJECT_CS *)((char *)this + 664), v31);
              if ( v5 < 0 )
              {
                if ( (g_dwDebugFlags & 0xF) != 0 )
                {
                  v6 = " Failed copying string property \n";
                  v7 = 1678;
                  goto LABEL_6;
                }
                goto LABEL_118;
              }
              v31 = 0;
            }
            v21 = (int *)((char *)this + 192);
            v5 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 72LL))(
                   a2,
                   L"rapidFailProtection",
                   (char *)this + 192,
                   &v29,
                   0);
            if ( v5 >= 0 )
            {
              if ( v29 )
              {
                CONFIG_ERROR::CreateAndInitWithBool(&v30, L"rapidFailProtection", *v21, v29);
                v22 = v30;
                if ( v30 )
                {
                  *((_DWORD *)v30 + 2) = 10;
                  CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v22);
                }
                v30 = 0;
                (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v29 + 16LL))(v29);
                v29 = 0;
              }
              if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
              {
                if ( !*v21 )
                  v11 = L"FALSE";
                PuDbgPrint(
                  g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
                  1713,
                  "APP_POOL_DATA_OBJECT_CS::SetFailureSettingsFromConfigStoreData",
                  " RFP %S \n",
                  v11);
              }
              v5 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, __int64 *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 80LL))(
                     a2,
                     L"rapidFailProtectionInterval",
                     &v32,
                     &v29,
                     0);
              if ( v5 >= 0 )
              {
                v23 = v32;
                v24 = v29;
                *((_DWORD *)this + 150) = v32 / 10000000 / 60;
                if ( v24 )
                {
                  CONFIG_ERROR::CreateAndInitWithRawTimeSpan(&v30, L"rapidFailProtectionInterval", v23, v24);
                  v25 = v30;
                  if ( v30 )
                  {
                    *((_DWORD *)v30 + 2) = 35;
                    CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v25);
                  }
                  v30 = 0;
                  (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v29 + 16LL))(v29);
                  v29 = 0;
                }
                if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
                  PuDbgPrint(
                    g_pDebug,
                    "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
                    1747,
                    "APP_POOL_DATA_OBJECT_CS::SetFailureSettingsFromConfigStoreData",
                    " Rapid Fail Protection Interval = %u (0x%X) \n",
                    *((_DWORD *)this + 150),
                    *((_DWORD *)this + 150));
                v26 = (unsigned int *)((char *)this + 604);
                v5 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 48LL))(
                       a2,
                       L"rapidFailProtectionMaxCrashes",
                       (char *)this + 604,
                       &v29,
                       0);
                if ( v5 >= 0 )
                {
                  if ( v29 )
                  {
                    CONFIG_ERROR::CreateAndInitWithLong(&v30, L"rapidFailProtectionMaxCrashes", *v26, v29);
                    v27 = v30;
                    if ( v30 )
                    {
                      *((_DWORD *)v30 + 2) = 36;
                      CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v27);
                    }
                    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v29 + 16LL))(v29);
                    v29 = 0;
                  }
                  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
                    PuDbgPrint(
                      g_pDebug,
                      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
                      1779,
                      "APP_POOL_DATA_OBJECT_CS::SetFailureSettingsFromConfigStoreData",
                      " Rapid Fail Protection Max Crashes = %u (0x%X) \n",
                      *v26,
                      *v26);
                }
                else if ( (g_dwDebugFlags & 0xF) != 0 )
                {
                  v6 = " Failed reading property \n";
                  v7 = 1757;
                  goto LABEL_6;
                }
              }
              else if ( (g_dwDebugFlags & 0xF) != 0 )
              {
                v6 = " Failed reading property \n";
                v7 = 1724;
                goto LABEL_6;
              }
              goto LABEL_118;
            }
            if ( (g_dwDebugFlags & 0xF) == 0 )
              goto LABEL_118;
            v7 = 1692;
          }
          else
          {
            if ( (g_dwDebugFlags & 0xF) == 0 )
              goto LABEL_118;
            v7 = 1646;
          }
        }
        else
        {
          if ( (g_dwDebugFlags & 0xF) == 0 )
            goto LABEL_118;
          v7 = 1601;
        }
      }
      else
      {
        if ( (g_dwDebugFlags & 0xF) == 0 )
          goto LABEL_118;
        v7 = 1556;
      }
    }
    else
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_118;
      v7 = 1512;
    }
    v6 = " Failed reading property \n";
    goto LABEL_6;
  }
  if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    v6 = " Failed reading property \n";
    v7 = 1481;
LABEL_6:
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
      v7,
      "APP_POOL_DATA_OBJECT_CS::SetFailureSettingsFromConfigStoreData",
      v5,
      v6);
  }
LABEL_118:
  if ( v29 )
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v29 + 16LL))(v29);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180045374  push    rbp
0x180045376  push    rbx
0x180045377  push    rsi
0x180045378  push    rdi
0x180045379  push    r12
0x18004537b  push    r13
0x18004537d  push    r14
0x18004537f  push    r15
0x180045381  mov     rbp, rsp
0x180045384  sub     rsp, 48h
0x180045388  mov     eax, cs:g_dwDebugFlags
0x18004538e  lea     r13, aAppPoolDataObj_11; "APP_POOL_DATA_OBJECT_CS::SetFailureSett"...
0x180045395  xor     r12d, r12d
0x180045398  lea     r15, aServercommonIn_62; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18004539f  test    al, 3
0x1800453a1  mov     [rbp+arg_10], r12
0x1800453a5  mov     rsi, rdx
0x1800453a8  mov     [rbp+arg_18], r12
0x1800453ac  setnz   r8b
0x1800453b0  mov     [rbp+arg_0], r12
0x1800453b4  bt      eax, 1Eh
0x1800453b8  mov     [rbp+arg_8], r12
0x1800453bc  mov     rdi, rcx
0x1800453bf  setb    al
0x1800453c2  test    al, r8b
0x1800453c5  jz      short loc_1800453EC
0x1800453c7  mov     rcx, cs:g_pDebug
0x1800453ce  lea     rax, aGettingTheCapa; " Getting the Capabilities \n"
0x1800453d5  mov     r9, r13
0x1800453d8  mov     [rsp+48h+var_28], rax
0x1800453dd  mov     r8d, 59Fh
0x1800453e3  mov     rdx, r15
0x1800453e6  call    cs:__imp_PuDbgPrint
0x1800453ec  mov     rax, [rsi]
0x1800453ef  lea     r14, [rdi+2D0h]
0x1800453f6  lea     r9, [rbp+arg_0]
0x1800453fa  mov     [rsp+48h+var_28], r12
0x1800453ff  mov     r8, r14
0x180045402  lea     rdx, aLoadbalancerca; "loadBalancerCapabilities"
0x180045409  mov     rcx, rsi
0x18004540c  mov     rax, [rax+30h]
0x180045410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045415  mov     ebx, eax
0x180045417  test    eax, eax
0x180045419  jns     short loc_180045456
0x18004541b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180045422  jz      loc_180045D81
0x180045428  lea     rax, aFailedReadingL; " Failed reading load balancer capabilit"...
0x18004542f  mov     r8d, 5A9h
0x180045435  mov     rdx, r15
0x180045438  mov     rcx, cs:g_pDebug
0x18004543f  mov     r9, r13
0x180045442  mov     [rsp+48h+var_20], rax
0x180045447  mov     dword ptr [rsp+48h+var_28], ebx
0x18004544b  call    cs:__imp_PuDbgPrintError
0x180045451  jmp     loc_180045D81
0x180045456  mov     r9, [rbp+arg_0]; struct INativePropertyException *
0x18004545a  test    r9, r9
0x18004545d  jz      short loc_1800454A6
0x18004545f  mov     r8d, [r14]; int
0x180045462  lea     rdx, aLoadbalancerca; "loadBalancerCapabilities"
0x180045469  lea     rcx, [rbp+arg_8]; struct CONFIG_ERROR **
0x18004546d  call    ?CreateAndInitWithLong@CONFIG_ERROR@@SAXPEAPEAV1@PEBGJPEAVINativePropertyException@@@Z; CONFIG_ERROR::CreateAndInitWithLong(CONFIG_ERROR * *,ushort const *,long,INativePropertyException *)
0x180045472  mov     rdx, [rbp+arg_8]; struct CONFIG_ERROR *
0x180045476  test    rdx, rdx
0x180045479  jz      short loc_18004548E
0x18004547b  lea     rcx, [rdi+3E8h]; this
0x180045482  mov     dword ptr [rdx+8], 27h ; '''
0x180045489  call    ?Add@CONFIG_ERROR_LIST@@QEAAXPEAVCONFIG_ERROR@@@Z; CONFIG_ERROR_LIST::Add(CONFIG_ERROR *)
0x18004548e  mov     rcx, [rbp+arg_0]
0x180045492  mov     [rbp+arg_8], r12
0x180045496  mov     rax, [rcx]
0x180045499  mov     rax, [rax+10h]
0x18004549d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800454a2  mov     [rbp+arg_0], r12
0x1800454a6  mov     eax, cs:g_dwDebugFlags
0x1800454ac  test    al, 3
0x1800454ae  setnz   cl
0x1800454b1  bt      eax, 1Eh
0x1800454b5  setb    al
0x1800454b8  test    al, cl
0x1800454ba  jz      short loc_1800454EC
0x1800454bc  mov     eax, [r14]
0x1800454bf  mov     r9, r13
0x1800454c2  mov     rcx, cs:g_pDebug
0x1800454c9  mov     r8d, 5BFh
0x1800454cf  mov     [rsp+48h+var_18], eax
0x1800454d3  mov     rdx, r15
0x1800454d6  mov     dword ptr [rsp+48h+var_20], eax
0x1800454da  lea     rax, aLoadBalancerTy; " Load Balancer Type = %u (0x%X) \n"
0x1800454e1  mov     [rsp+48h+var_28], rax
0x1800454e6  call    cs:__imp_PuDbgPrint
0x1800454ec  mov     rax, [rsi]
0x1800454ef  lea     r14, [rdi+0DCh]
0x1800454f6  lea     r9, [rbp+arg_0]
0x1800454fa  mov     [rsp+48h+var_28], r12
0x1800454ff  mov     r8, r14
0x180045502  lea     rdx, aOrphanworkerpr; "orphanWorkerProcess"
0x180045509  mov     rcx, rsi
0x18004550c  mov     rax, [rax+48h]
0x180045510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045515  mov     ebx, eax
0x180045517  test    eax, eax
0x180045519  jns     short loc_18004553A
0x18004551b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180045522  jz      loc_180045D81
0x180045528  lea     rax, aFailedReadingP_1; " Failed reading property \n"
0x18004552f  mov     r8d, 5C9h
0x180045535  jmp     loc_180045435
0x18004553a  mov     r9, [rbp+arg_0]; struct INativePropertyException *
0x18004553e  test    r9, r9
0x180045541  jz      short loc_18004558A
0x180045543  mov     r8d, [r14]; int
0x180045546  lea     rdx, aOrphanworkerpr; "orphanWorkerProcess"
0x18004554d  lea     rcx, [rbp+arg_8]; struct CONFIG_ERROR **
0x180045551  call    ?CreateAndInitWithBool@CONFIG_ERROR@@SAXPEAPEAV1@PEBGHPEAVINativePropertyException@@@Z; CONFIG_ERROR::CreateAndInitWithBool(CONFIG_ERROR * *,ushort const *,int,INativePropertyException *)
0x180045556  mov     rdx, [rbp+arg_8]; struct CONFIG_ERROR *
0x18004555a  test    rdx, rdx
0x18004555d  jz      short loc_180045572
0x18004555f  lea     rcx, [rdi+3E8h]; this
0x180045566  mov     dword ptr [rdx+8], 0Eh
0x18004556d  call    ?Add@CONFIG_ERROR_LIST@@QEAAXPEAVCONFIG_ERROR@@@Z; CONFIG_ERROR_LIST::Add(CONFIG_ERROR *)
0x180045572  mov     rcx, [rbp+arg_0]
0x180045576  mov     [rbp+arg_8], r12
0x18004557a  mov     rax, [rcx]
0x18004557d  mov     rax, [rax+10h]
0x180045581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045586  mov     [rbp+arg_0], r12
0x18004558a  mov     eax, cs:g_dwDebugFlags
0x180045590  lea     rdx, aFalse_1; "FALSE"
0x180045597  test    al, 3
0x180045599  lea     r15, aTrue_1; "TRUE"
0x1800455a0  setnz   cl
0x1800455a3  bt      eax, 1Eh
0x1800455a7  setb    al
0x1800455aa  test    al, cl
0x1800455ac  jz      short loc_1800455E6
0x1800455ae  cmp     [r14], r12d
0x1800455b1  mov     rax, r15
0x1800455b4  mov     rcx, cs:g_pDebug
0x1800455bb  mov     r9, r13
0x1800455be  cmovz   rax, rdx
0x1800455c2  mov     r8d, 5DEh
0x1800455c8  mov     [rsp+48h+var_20], rax
0x1800455cd  lea     rdx, aServercommonIn_62; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800455d4  lea     rax, aOrphanWpS; " Orphan WP %S \n"
0x1800455db  mov     [rsp+48h+var_28], rax
0x1800455e0  call    cs:__imp_PuDbgPrint
0x1800455e6  mov     rax, [rsi]
0x1800455e9  lea     r9, [rbp+arg_0]
0x1800455ed  lea     r8, [rbp+arg_10]
0x1800455f1  mov     [rsp+48h+var_28], r12
0x1800455f6  lea     rdx, aOrphanactionex; "orphanActionExe"
0x1800455fd  mov     rcx, rsi
0x180045600  mov     rax, [rax+40h]
0x180045604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045609  mov     ebx, eax
0x18004560b  test    eax, eax
0x18004560d  jns     short loc_180045635
0x18004560f  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180045616  jz      loc_180045D81
0x18004561c  mov     r8d, 5E8h
0x180045622  lea     rax, aFailedReadingP_1; " Failed reading property \n"
0x180045629  lea     rdx, aServercommonIn_62; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180045630  jmp     loc_180045438
0x180045635  mov     r9, [rbp+arg_0]; struct INativePropertyException *
0x180045639  test    r9, r9
0x18004563c  jz      short loc_180045686
0x18004563e  mov     r8, [rbp+arg_10]; unsigned __int16 *
0x180045642  lea     rdx, aOrphanactionex; "orphanActionExe"
0x180045649  lea     rcx, [rbp+arg_8]; struct CONFIG_ERROR **
0x18004564d  call    ?CreateAndInitWithString@CONFIG_ERROR@@SAXPEAPEAV1@PEBG1PEAVINativePropertyException@@@Z; CONFIG_ERROR::CreateAndInitWithString(CONFIG_ERROR * *,ushort const *,ushort const *,INativePropertyException *)
0x180045652  mov     rdx, [rbp+arg_8]; struct CONFIG_ERROR *
0x180045656  test    rdx, rdx
0x180045659  jz      short loc_18004566E
0x18004565b  lea     rcx, [rdi+3E8h]; this
0x180045662  mov     dword ptr [rdx+8], 14h
0x180045669  call    ?Add@CONFIG_ERROR_LIST@@QEAAXPEAVCONFIG_ERROR@@@Z; CONFIG_ERROR_LIST::Add(CONFIG_ERROR *)
0x18004566e  mov     rcx, [rbp+arg_0]
0x180045672  mov     [rbp+arg_8], r12
0x180045676  mov     rax, [rcx]
0x180045679  mov     rax, [rax+10h]
0x18004567d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045682  mov     [rbp+arg_0], r12
0x180045686  mov     eax, cs:g_dwDebugFlags
0x18004568c  lea     r14, aNull_0; "NULL"
0x180045693  test    al, 3
0x180045695  setnz   cl
0x180045698  bt      eax, 1Eh
0x18004569c  setb    al
0x18004569f  test    al, cl
0x1800456a1  jz      short loc_1800456DF
0x1800456a3  mov     rax, [rbp+arg_10]
0x1800456a7  lea     rdx, aServercommonIn_62; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800456ae  test    rax, rax
0x1800456b1  mov     rcx, r14
0x1800456b4  mov     r9, r13
0x1800456b7  mov     r8d, 5FDh
0x1800456bd  cmovnz  rcx, rax
0x1800456c1  lea     rax, aOprhanExeS; " Oprhan Exe = '%s' \n"
0x1800456c8  mov     [rsp+48h+var_20], rcx
0x1800456cd  mov     rcx, cs:g_pDebug
0x1800456d4  mov     [rsp+48h+var_28], rax
0x1800456d9  call    cs:__imp_PuDbgPrint
0x1800456df  mov     rdx, [rbp+arg_10]
0x1800456e3  test    rdx, rdx
0x1800456e6  jz      short loc_18004571E
0x1800456e8  lea     rcx, [rdi+0F8h]
0x1800456ef  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800456f5  mov     ebx, eax
0x1800456f7  test    eax, eax
0x1800456f9  jns     short loc_18004571A
0x1800456fb  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180045702  jz      loc_180045D81
0x180045708  lea     rax, aFailedCopyingS; " Failed copying string property \n"
0x18004570f  mov     r8d, 607h
0x180045715  jmp     loc_180045629
0x18004571a  mov     [rbp+arg_10], r12
0x18004571e  mov     rax, [rsi]
0x180045721  lea     r9, [rbp+arg_0]
0x180045725  lea     r8, [rbp+arg_10]
0x180045729  mov     [rsp+48h+var_28], r12
0x18004572e  lea     rdx, aOrphanactionpa; "orphanActionParams"
0x180045735  mov     rcx, rsi
0x180045738  mov     rax, [rax+40h]
0x18004573c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045741  mov     ebx, eax
0x180045743  test    eax, eax
0x180045745  jns     short loc_18004575F
0x180045747  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004574e  jz      loc_180045D81
0x180045754  mov     r8d, 614h
0x18004575a  jmp     loc_180045622
0x18004575f  mov     r9, [rbp+arg_0]; struct INativePropertyException *
0x180045763  test    r9, r9
0x180045766  jz      short loc_1800457B0
0x180045768  mov     r8, [rbp+arg_10]; unsigned __int16 *
0x18004576c  lea     rdx, aOrphanactionpa; "orphanActionParams"
0x180045773  lea     rcx, [rbp+arg_8]; struct CONFIG_ERROR **
0x180045777  call    ?CreateAndInitWithString@CONFIG_ERROR@@SAXPEAPEAV1@PEBG1PEAVINativePropertyException@@@Z; CONFIG_ERROR::CreateAndInitWithString(CONFIG_ERROR * *,ushort const *,ushort const *,INativePropertyException *)
0x18004577c  mov     rdx, [rbp+arg_8]; struct CONFIG_ERROR *
0x180045780  test    rdx, rdx
0x180045783  jz      short loc_180045798
0x180045785  lea     rcx, [rdi+3E8h]; this
0x18004578c  mov     dword ptr [rdx+8], 15h
0x180045793  call    ?Add@CONFIG_ERROR_LIST@@QEAAXPEAVCONFIG_ERROR@@@Z; CONFIG_ERROR_LIST::Add(CONFIG_ERROR *)
0x180045798  mov     rcx, [rbp+arg_0]
0x18004579c  mov     [rbp+arg_8], r12
0x1800457a0  mov     rax, [rcx]
0x1800457a3  mov     rax, [rax+10h]
0x1800457a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800457ac  mov     [rbp+arg_0], r12
0x1800457b0  mov     eax, cs:g_dwDebugFlags
0x1800457b6  test    al, 3
0x1800457b8  setnz   cl
0x1800457bb  bt      eax, 1Eh
0x1800457bf  setb    al
0x1800457c2  test    al, cl
0x1800457c4  jz      short loc_180045802
0x1800457c6  mov     rax, [rbp+arg_10]
0x1800457ca  lea     rdx, aServercommonIn_62; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800457d1  test    rax, rax
0x1800457d4  mov     rcx, r14
0x1800457d7  mov     r9, r13
0x1800457da  mov     r8d, 629h
0x1800457e0  cmovnz  rcx, rax
0x1800457e4  lea     rax, aOrphanArgument; " Orphan Arguments = '%s' \n"
0x1800457eb  mov     [rsp+48h+var_20], rcx
0x1800457f0  mov     rcx, cs:g_pDebug
0x1800457f7  mov     [rsp+48h+var_28], rax
0x1800457fc  call    cs:__imp_PuDbgPrint
0x180045802  mov     rdx, [rbp+arg_10]
0x180045806  test    rdx, rdx
0x180045809  jz      short loc_180045841
0x18004580b  lea     rcx, [rdi+130h]
0x180045812  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180045818  mov     ebx, eax
0x18004581a  test    eax, eax
0x18004581c  jns     short loc_18004583D
0x18004581e  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180045825  jz      loc_180045D81
0x18004582b  lea     rax, aFailedCopyingS; " Failed copying string property \n"
0x180045832  mov     r8d, 633h
0x180045838  jmp     loc_180045629
0x18004583d  mov     [rbp+arg_10], r12
0x180045841  mov     rax, [rsi]
0x180045844  lea     r9, [rbp+arg_0]
0x180045848  lea     r8, [rbp+arg_10]
0x18004584c  mov     [rsp+48h+var_28], r12
0x180045851  lea     rdx, aAutoshutdownex; "autoShutdownExe"
0x180045858  mov     rcx, rsi
0x18004585b  mov     rax, [rax+40h]
0x18004585f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045864  mov     ebx, eax
0x180045866  test    eax, eax
0x180045868  jns     short loc_180045882
0x18004586a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180045871  jz      loc_180045D81
0x180045877  mov     r8d, 641h
0x18004587d  jmp     loc_180045622
  ... truncated ...
```
