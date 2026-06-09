# APP_POOL_DATA_OBJECT_CS::SetGenericSettingsFromConfigStoreData(INativeConfigurationElement *)

- ea: `0x180045db0`
- end: `0x18004677f`
- name: `?SetGenericSettingsFromConfigStoreData@APP_POOL_DATA_OBJECT_CS@@QEAAJPEAVINativeConfigurationElement@@@Z`
- size: `2511`
- prototype: `__int64 __fastcall(APP_POOL_DATA_OBJECT_CS *__hidden this, struct INativeConfigurationElement *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180044950`

## callees

- `0x180045db0`
- `0x180052d90`
- `0x180052f8c`
- `0x180053908`
- `0x180062010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180045f14`
- `iisutil!PuDbgPrint` at `0x180045fa3`
- `iisutil!PuDbgPrint` at `0x180046047`
- `iisutil!PuDbgPrint` at `0x180046108`
- `iisutil!PuDbgPrint` at `0x1800461ff`
- `iisutil!PuDbgPrint` at `0x1800462f6`
- `iisutil!PuDbgPrint` at `0x1800463dc`
- `iisutil!PuDbgPrint` at `0x180046464`
- `iisutil!PuDbgPrint` at `0x18004656f`
- `iisutil!PuDbgPrint` at `0x18004666f`
- `iisutil!PuDbgPrint` at `0x180046751`
- `iisutil!PuDbgPrint` at `0x180045f14`
- `iisutil!PuDbgPrint` at `0x180045fa3`
- `iisutil!PuDbgPrint` at `0x180046047`
- `iisutil!PuDbgPrint` at `0x180046108`
- `iisutil!PuDbgPrint` at `0x1800461ff`
- `iisutil!PuDbgPrint` at `0x1800462f6`
- `iisutil!PuDbgPrint` at `0x1800463dc`
- `iisutil!PuDbgPrint` at `0x180046464`
- `iisutil!PuDbgPrint` at `0x18004656f`
- `iisutil!PuDbgPrint` at `0x18004666f`
- `iisutil!PuDbgPrint` at `0x180046751`
- `iisutil!PuDbgPrintError` at `0x180045e5d`
- `iisutil!PuDbgPrintError` at `0x1800465d1`
- `iisutil!PuDbgPrintError` at `0x180045e5d`
- `iisutil!PuDbgPrintError` at `0x1800465d1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180045fb4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180046058`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180046475`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180045fb4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180046058`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180046475`

## string_xrefs

- `0x180045e4d`: ` Failed reading property \n`
- `0x180045e32`: `APP_POOL_DATA_OBJECT_CS::SetGenericSettingsFromConfigStoreData`
- `0x180045ec7`: `APP_POOL_DATA_OBJECT_CS::SetGenericSettingsFromConfigStoreData`
- `0x180045e3f`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\apppoolstore_cs.cxx`
- `0x180045ed1`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\apppoolstore_cs.cxx`
- `0x180046278`: `passAnonymousToken`
- `0x180046309`: `passAnonymousToken`
- `0x1800462ea`: ` PassAnonymousToken = %S \n`
- `0x1800463f5`: `CLRConfigFile`
- `0x180046458`: ` CLR Config File = %S \n`
- `0x18004658e`: `enableConfigurationOverride`
- `0x1800465e3`: `enableConfigurationOverride`
- `0x1800465ae`: ` Failed reading 'enableConfigurationOverride' property \n`
- `0x18004665b`: ` Enable Configuration Override = %S \n`

## pseudocode

```c
__int64 __fastcall APP_POOL_DATA_OBJECT_CS::SetGenericSettingsFromConfigStoreData(
        APP_POOL_DATA_OBJECT_CS *this,
        struct INativeConfigurationElement *a2)
{
  __int64 v2; // rax
  int *v3; // r12
  __int64 (__fastcall *v6)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD); // rax
  int v7; // ebx
  __int64 v8; // r8
  struct CONFIG_ERROR *v9; // rdx
  int *v10; // r12
  const wchar_t *v11; // r13
  const wchar_t *v12; // rax
  struct CONFIG_ERROR *v13; // rdx
  int *v14; // r12
  const wchar_t *v15; // rax
  struct CONFIG_ERROR *v16; // rdx
  int *v17; // r12
  const wchar_t *v18; // rax
  struct CONFIG_ERROR *v19; // rdx
  int *v20; // r12
  struct CONFIG_ERROR *v21; // rdx
  const wchar_t *v22; // rax
  int *v23; // rbx
  int v24; // eax
  struct CONFIG_ERROR *v25; // rdx
  int *v26; // r12
  struct CONFIG_ERROR *v27; // rdx
  const unsigned __int16 *v29; // [rsp+40h] [rbp-18h] BYREF
  struct INativePropertyException *v30; // [rsp+A0h] [rbp+48h] BYREF
  struct CONFIG_ERROR *v31; // [rsp+A8h] [rbp+50h] BYREF
  const unsigned __int16 *v32; // [rsp+B0h] [rbp+58h] BYREF
  const unsigned __int16 *v33; // [rsp+B8h] [rbp+60h] BYREF

  v2 = *(_QWORD *)a2;
  v3 = (int *)((char *)this + 360);
  v32 = 0;
  v33 = 0;
  v29 = 0;
  v6 = *(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(v2 + 48);
  v30 = 0;
  v31 = 0;
  v7 = v6(a2, L"queueLength", (char *)this + 360, &v30, 0);
  if ( v7 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_98;
    v8 = 60;
    goto LABEL_4;
  }
  if ( v30 )
  {
    CONFIG_ERROR::CreateAndInitWithLong(&v31, L"queueLength", *v3, v30);
    v9 = v31;
    if ( v31 )
    {
      *((_DWORD *)v31 + 2) = 22;
      CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v9);
    }
    v31 = 0;
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v30 + 16LL))(v30);
    v30 = 0;
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
      83,
      "APP_POOL_DATA_OBJECT_CS::SetGenericSettingsFromConfigStoreData",
      " Queue Length = %u (0x%X) \n",
      *v3,
      *v3);
  v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)a2 + 64LL))(
         a2,
         L"managedRuntimeVersion",
         &v32,
         0,
         0);
  if ( v7 >= 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
        101,
        "APP_POOL_DATA_OBJECT_CS::SetGenericSettingsFromConfigStoreData",
        " Clr Version = %S \n",
        v32);
    v7 = STRU::Copy((APP_POOL_DATA_OBJECT_CS *)((char *)this + 744), v32);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)a2 + 64LL))(
             a2,
             L"managedRuntimeLoader",
             &v33,
             0,
             0);
      if ( v7 >= 0 )
      {
        if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
            124,
            "APP_POOL_DATA_OBJECT_CS::SetGenericSettingsFromConfigStoreData",
            " Clr Loader = %S \n",
            v33);
        v7 = STRU::Copy((APP_POOL_DATA_OBJECT_CS *)((char *)this + 800), v33);
        if ( v7 >= 0 )
        {
          v10 = (int *)((char *)this + 732);
          v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 72LL))(
                 a2,
                 L"enable32BitAppOnWin64",
                 (char *)this + 732,
                 &v30,
                 0);
          if ( v7 >= 0 )
          {
            v11 = L"TRUE";
            if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
            {
              v12 = L"TRUE";
              if ( !*v10 )
                v12 = L"FALSE";
              PuDbgPrint(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
                148,
                "APP_POOL_DATA_OBJECT_CS::SetGenericSettingsFromConfigStoreData",
                " Enable32bitAppOnWin64 = %S \n",
                v12);
            }
            if ( v30 )
            {
              CONFIG_ERROR::CreateAndInitWithBool(&v31, L"enable32BitAppOnWin64", *v10, v30);
              v13 = v31;
              if ( v31 )
              {
                *((_DWORD *)v31 + 2) = 41;
                CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v13);
              }
              v31 = 0;
              (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v30 + 16LL))(v30);
              v30 = 0;
            }
            v14 = (int *)((char *)this + 736);
            v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 72LL))(
                   a2,
                   L"enableEmulationOnWinArm64",
                   (char *)this + 736,
                   &v30,
                   0);
            if ( v7 >= 0 )
            {
              if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
              {
                v15 = L"TRUE";
                if ( !*v14 )
                  v15 = L"FALSE";
                PuDbgPrint(
                  g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
                  180,
                  "APP_POOL_DATA_OBJECT_CS::SetGenericSettingsFromConfigStoreData",
                  " EnableEmulationOnWinArm64 = %S \n",
                  v15);
              }
              if ( v30 )
              {
                CONFIG_ERROR::CreateAndInitWithBool(&v31, L"enableEmulationOnWinArm64", *v14, v30);
                v16 = v31;
                if ( v31 )
                {
                  *((_DWORD *)v31 + 2) = 42;
                  CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v16);
                }
                v31 = 0;
                (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v30 + 16LL))(v30);
                v30 = 0;
              }
              v17 = (int *)((char *)this + 916);
              v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 72LL))(
                     a2,
                     L"passAnonymousToken",
                     (char *)this + 916,
                     &v30,
                     0);
              if ( v7 >= 0 )
              {
                if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
                {
                  v18 = L"TRUE";
                  if ( !*v17 )
                    v18 = L"FALSE";
                  PuDbgPrint(
                    g_pDebug,
                    "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
                    212,
                    "APP_POOL_DATA_OBJECT_CS::SetGenericSettingsFromConfigStoreData",
                    " PassAnonymousToken = %S \n",
                    v18);
                }
                if ( v30 )
                {
                  CONFIG_ERROR::CreateAndInitWithBool(&v31, L"passAnonymousToken", *v17, v30);
                  v19 = v31;
                  if ( v31 )
                  {
                    *((_DWORD *)v31 + 2) = 43;
                    CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v19);
                  }
                  v31 = 0;
                  (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v30 + 16LL))(v30);
                  v30 = 0;
                }
                v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)a2 + 48LL))(
                       a2,
                       L"managedPipelineMode",
                       (char *)this + 912,
                       0,
                       0);
                if ( v7 >= 0 )
                {
                  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
                    PuDbgPrint(
                      g_pDebug,
                      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
                      242,
                      "APP_POOL_DATA_OBJECT_CS::SetGenericSettingsFromConfigStoreData",
                      " Pipeline mode = %u \n",
                      *((_DWORD *)this + 228));
                  v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)a2 + 64LL))(
                         a2,
                         L"CLRConfigFile",
                         &v29,
                         0,
                         0);
                  if ( v7 >= 0 )
                  {
                    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
                      PuDbgPrint(
                        g_pDebug,
                        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
                        259,
                        "APP_POOL_DATA_OBJECT_CS::SetGenericSettingsFromConfigStoreData",
                        " CLR Config File = %S \n",
                        v29);
                    v7 = STRU::Copy((APP_POOL_DATA_OBJECT_CS *)((char *)this + 856), v29);
                    if ( v7 >= 0 )
                    {
                      v20 = (int *)((char *)this + 596);
                      v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 72LL))(
                             a2,
                             L"autoStart",
                             (char *)this + 596,
                             &v30,
                             0);
                      if ( v7 >= 0 )
                      {
                        if ( v30 )
                        {
                          CONFIG_ERROR::CreateAndInitWithBool(&v31, L"autoStart", *v20, v30);
                          v21 = v31;
                          if ( v31 )
                          {
                            *((_DWORD *)v31 + 2) = 34;
                            CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v21);
                          }
                          v31 = 0;
                          (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v30 + 16LL))(v30);
                          v30 = 0;
                        }
                        if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
                        {
                          v22 = L"TRUE";
                          if ( !*v20 )
                            v22 = L"FALSE";
                          PuDbgPrint(
                            g_pDebug,
                            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
                            295,
                            "APP_POOL_DATA_OBJECT_CS::SetGenericSettingsFromConfigStoreData",
                            " Auto Start = %S \n",
                            v22);
                        }
                        v23 = (int *)((char *)this + 920);
                        v24 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 72LL))(
                                a2,
                                L"enableConfigurationOverride",
                                (char *)this + 920,
                                &v30,
                                0);
                        if ( v24 < 0 && (g_dwDebugFlags & 0xF) != 0 )
                          PuDbgPrintError(
                            g_pDebug,
                            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
                            308,
                            "APP_POOL_DATA_OBJECT_CS::SetGenericSettingsFromConfigStoreData",
                            v24,
                            " Failed reading 'enableConfigurationOverride' property \n");
                        if ( v30 )
                        {
                          CONFIG_ERROR::CreateAndInitWithBool(&v31, L"enableConfigurationOverride", *v23, v30);
                          v25 = v31;
                          if ( v31 )
                          {
                            *((_DWORD *)v31 + 2) = 44;
                            CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v25);
                          }
                          v31 = 0;
                          (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v30 + 16LL))(v30);
                          v30 = 0;
                        }
                        if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
                        {
                          if ( !*v23 )
                            v11 = L"FALSE";
                          PuDbgPrint(
                            g_pDebug,
                            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
                            328,
                            "APP_POOL_DATA_OBJECT_CS::SetGenericSettingsFromConfigStoreData",
                            " Enable Configuration Override = %S \n",
                            v11);
                        }
                        v26 = (int *)((char *)this + 928);
                        v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 48LL))(
                               a2,
                               L"startMode",
                               (char *)this + 928,
                               &v30,
                               0);
                        if ( v7 >= 0 )
                        {
                          if ( v30 )
                          {
                            CONFIG_ERROR::CreateAndInitWithLong(&v31, L"startMode", *v26, v30);
                            v27 = v31;
                            if ( v31 )
                            {
                              *((_DWORD *)v31 + 2) = 46;
                              CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v27);
                            }
                            (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v30 + 16LL))(v30);
                            v30 = 0;
                          }
                          if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
                            PuDbgPrint(
                              g_pDebug,
                              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
                              359,
                              "APP_POOL_DATA_OBJECT_CS::SetGenericSettingsFromConfigStoreData",
                              " Start mode = %u \n",
                              *v26);
                        }
                        else if ( (g_dwDebugFlags & 0xF) != 0 )
                        {
                          v8 = 338;
                          goto LABEL_4;
                        }
                      }
                      else if ( (g_dwDebugFlags & 0xF) != 0 )
                      {
                        v8 = 274;
                        goto LABEL_4;
                      }
                    }
                  }
                  else if ( (g_dwDebugFlags & 0xF) != 0 )
                  {
                    v8 = 252;
                    goto LABEL_4;
                  }
                }
                else if ( (g_dwDebugFlags & 0xF) != 0 )
                {
                  v8 = 235;
                  goto LABEL_4;
                }
              }
              else if ( (g_dwDebugFlags & 0xF) != 0 )
              {
                v8 = 204;
                goto LABEL_4;
              }
            }
            else if ( (g_dwDebugFlags & 0xF) != 0 )
            {
              v8 = 172;
              goto LABEL_4;
            }
          }
          else if ( (g_dwDebugFlags & 0xF) != 0 )
          {
            v8 = 140;
            goto LABEL_4;
          }
        }
      }
      else if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        v8 = 116;
        goto LABEL_4;
      }
    }
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    v8 = 93;
LABEL_4:
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
      v8,
      "APP_POOL_DATA_OBJECT_CS::SetGenericSettingsFromConfigStoreData",
      v7,
      " Failed reading property \n");
  }
LABEL_98:
  if ( v30 )
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v30 + 16LL))(v30);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180045db0  push    rbp
0x180045db2  push    rbx
0x180045db3  push    rsi
0x180045db4  push    rdi
0x180045db5  push    r12
0x180045db7  push    r13
0x180045db9  push    r14
0x180045dbb  push    r15
0x180045dbd  mov     rbp, rsp
0x180045dc0  sub     rsp, 58h
0x180045dc4  mov     rax, [rdx]
0x180045dc7  lea     r12, [rcx+168h]
0x180045dce  mov     r15, rdx
0x180045dd1  mov     [rbp+arg_10], 0
0x180045dd9  mov     r14, rcx
0x180045ddc  mov     [rbp+arg_18], 0
0x180045de4  lea     r9, [rbp+arg_0]
0x180045de8  mov     [rbp+var_18], 0
0x180045df0  mov     rax, [rax+30h]
0x180045df4  lea     rdx, aQueuelength; "queueLength"
0x180045dfb  mov     r8, r12
0x180045dfe  mov     [rbp+arg_0], 0
0x180045e06  mov     rcx, r15
0x180045e09  mov     [rbp+arg_8], 0
0x180045e11  mov     [rsp+58h+var_38], 0
0x180045e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045e1f  mov     ebx, eax
0x180045e21  test    eax, eax
0x180045e23  jns     short loc_180045E68
0x180045e25  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180045e2c  jz      loc_180046757
0x180045e32  lea     r9, aAppPoolDataObj_17; "APP_POOL_DATA_OBJECT_CS::SetGenericSett"...
0x180045e39  mov     r8d, 3Ch ; '<'
0x180045e3f  lea     rdx, aServercommonIn_62; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180045e46  mov     rcx, cs:g_pDebug
0x180045e4d  lea     rax, aFailedReadingP_1; " Failed reading property \n"
0x180045e54  mov     [rsp+58h+var_30], rax
0x180045e59  mov     dword ptr [rsp+58h+var_38], ebx
0x180045e5d  call    cs:__imp_PuDbgPrintError
0x180045e63  jmp     loc_180046757
0x180045e68  mov     r9, [rbp+arg_0]; struct INativePropertyException *
0x180045e6c  test    r9, r9
0x180045e6f  jz      short loc_180045EC1
0x180045e71  mov     r8d, [r12]; int
0x180045e75  lea     rdx, aQueuelength; "queueLength"
0x180045e7c  lea     rcx, [rbp+arg_8]; struct CONFIG_ERROR **
0x180045e80  call    ?CreateAndInitWithLong@CONFIG_ERROR@@SAXPEAPEAV1@PEBGJPEAVINativePropertyException@@@Z; CONFIG_ERROR::CreateAndInitWithLong(CONFIG_ERROR * *,ushort const *,long,INativePropertyException *)
0x180045e85  mov     rdx, [rbp+arg_8]; struct CONFIG_ERROR *
0x180045e89  test    rdx, rdx
0x180045e8c  jz      short loc_180045EA1
0x180045e8e  lea     rcx, [r14+3E8h]; this
0x180045e95  mov     dword ptr [rdx+8], 16h
0x180045e9c  call    ?Add@CONFIG_ERROR_LIST@@QEAAXPEAVCONFIG_ERROR@@@Z; CONFIG_ERROR_LIST::Add(CONFIG_ERROR *)
0x180045ea1  mov     rcx, [rbp+arg_0]
0x180045ea5  mov     [rbp+arg_8], 0
0x180045ead  mov     rax, [rcx]
0x180045eb0  mov     rax, [rax+10h]
0x180045eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045eb9  mov     [rbp+arg_0], 0
0x180045ec1  mov     eax, cs:g_dwDebugFlags
0x180045ec7  lea     rdi, aAppPoolDataObj_17; "APP_POOL_DATA_OBJECT_CS::SetGenericSett"...
0x180045ece  mov     r13b, 3
0x180045ed1  lea     rsi, aServercommonIn_62; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180045ed8  test    r13b, al
0x180045edb  setnz   cl
0x180045ede  bt      eax, 1Eh
0x180045ee2  setb    al
0x180045ee5  test    al, cl
0x180045ee7  jz      short loc_180045F1A
0x180045ee9  mov     eax, [r12]
0x180045eed  mov     r9, rdi
0x180045ef0  mov     rcx, cs:g_pDebug
0x180045ef7  mov     r8d, 53h ; 'S'
0x180045efd  mov     [rsp+58h+var_28], eax
0x180045f01  mov     rdx, rsi
0x180045f04  mov     dword ptr [rsp+58h+var_30], eax
0x180045f08  lea     rax, aQueueLengthU0x; " Queue Length = %u (0x%X) \n"
0x180045f0f  mov     [rsp+58h+var_38], rax
0x180045f14  call    cs:__imp_PuDbgPrint
0x180045f1a  mov     rax, [r15]
0x180045f1d  lea     r8, [rbp+arg_10]
0x180045f21  xor     r9d, r9d
0x180045f24  mov     [rsp+58h+var_38], 0
0x180045f2d  lea     rdx, aManagedruntime_0; "managedRuntimeVersion"
0x180045f34  mov     rcx, r15
0x180045f37  mov     rax, [rax+40h]
0x180045f3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045f40  mov     ebx, eax
0x180045f42  test    eax, eax
0x180045f44  jns     short loc_180045F64
0x180045f46  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180045f4d  jz      loc_180046757
0x180045f53  mov     r8d, 5Dh ; ']'
0x180045f59  mov     r9, rdi
0x180045f5c  mov     rdx, rsi
0x180045f5f  jmp     loc_180045E46
0x180045f64  mov     eax, cs:g_dwDebugFlags
0x180045f6a  test    r13b, al
0x180045f6d  setnz   cl
0x180045f70  bt      eax, 1Eh
0x180045f74  setb    al
0x180045f77  test    al, cl
0x180045f79  jz      short loc_180045FA9
0x180045f7b  mov     rax, [rbp+arg_10]
0x180045f7f  mov     r9, rdi
0x180045f82  mov     rcx, cs:g_pDebug
0x180045f89  mov     r8d, 65h ; 'e'
0x180045f8f  mov     [rsp+58h+var_30], rax
0x180045f94  mov     rdx, rsi
0x180045f97  lea     rax, aClrVersionS; " Clr Version = %S \n"
0x180045f9e  mov     [rsp+58h+var_38], rax
0x180045fa3  call    cs:__imp_PuDbgPrint
0x180045fa9  mov     rdx, [rbp+arg_10]
0x180045fad  lea     rcx, [r14+2E8h]
0x180045fb4  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180045fba  mov     ebx, eax
0x180045fbc  test    eax, eax
0x180045fbe  js      loc_180046757
0x180045fc4  mov     rax, [r15]
0x180045fc7  lea     r8, [rbp+arg_18]
0x180045fcb  xor     r9d, r9d
0x180045fce  mov     [rsp+58h+var_38], 0
0x180045fd7  lea     rdx, aManagedruntime; "managedRuntimeLoader"
0x180045fde  mov     rcx, r15
0x180045fe1  mov     rax, [rax+40h]
0x180045fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045fea  mov     ebx, eax
0x180045fec  test    eax, eax
0x180045fee  jns     short loc_180046008
0x180045ff0  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180045ff7  jz      loc_180046757
0x180045ffd  mov     r8d, 74h ; 't'
0x180046003  jmp     loc_180045F59
0x180046008  mov     eax, cs:g_dwDebugFlags
0x18004600e  test    r13b, al
0x180046011  setnz   cl
0x180046014  bt      eax, 1Eh
0x180046018  setb    al
0x18004601b  test    al, cl
0x18004601d  jz      short loc_18004604D
0x18004601f  mov     rax, [rbp+arg_18]
0x180046023  mov     r9, rdi
0x180046026  mov     rcx, cs:g_pDebug
0x18004602d  mov     r8d, 7Ch ; '|'
0x180046033  mov     [rsp+58h+var_30], rax
0x180046038  mov     rdx, rsi
0x18004603b  lea     rax, aClrLoaderS; " Clr Loader = %S \n"
0x180046042  mov     [rsp+58h+var_38], rax
0x180046047  call    cs:__imp_PuDbgPrint
0x18004604d  mov     rdx, [rbp+arg_18]
0x180046051  lea     rcx, [r14+320h]
0x180046058  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18004605e  mov     ebx, eax
0x180046060  test    eax, eax
0x180046062  js      loc_180046757
0x180046068  mov     rax, [r15]
0x18004606b  lea     r12, [r14+2DCh]
0x180046072  lea     r9, [rbp+arg_0]
0x180046076  mov     [rsp+58h+var_38], 0
0x18004607f  mov     r8, r12
0x180046082  lea     rdx, aEnable32bitapp_1; "enable32BitAppOnWin64"
0x180046089  mov     rcx, r15
0x18004608c  mov     rax, [rax+48h]
0x180046090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046095  mov     ebx, eax
0x180046097  test    eax, eax
0x180046099  jns     short loc_1800460B3
0x18004609b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800460a2  jz      loc_180046757
0x1800460a8  mov     r8d, 8Ch
0x1800460ae  jmp     loc_180045F59
0x1800460b3  mov     eax, cs:g_dwDebugFlags
0x1800460b9  lea     rdx, aFalse_1; "FALSE"
0x1800460c0  test    r13b, al
0x1800460c3  lea     r13, aTrue_1; "TRUE"
0x1800460ca  setnz   cl
0x1800460cd  bt      eax, 1Eh
0x1800460d1  setb    al
0x1800460d4  test    al, cl
0x1800460d6  jz      short loc_18004610E
0x1800460d8  cmp     dword ptr [r12], 0
0x1800460dd  mov     rax, r13
0x1800460e0  mov     rcx, cs:g_pDebug
0x1800460e7  mov     r9, rdi
0x1800460ea  cmovz   rax, rdx
0x1800460ee  mov     r8d, 94h
0x1800460f4  mov     [rsp+58h+var_30], rax
0x1800460f9  mov     rdx, rsi
0x1800460fc  lea     rax, aEnable32bitapp_0; " Enable32bitAppOnWin64 = %S \n"
0x180046103  mov     [rsp+58h+var_38], rax
0x180046108  call    cs:__imp_PuDbgPrint
0x18004610e  mov     r9, [rbp+arg_0]; struct INativePropertyException *
0x180046112  test    r9, r9
0x180046115  jz      short loc_180046167
0x180046117  mov     r8d, [r12]; int
0x18004611b  lea     rdx, aEnable32bitapp_1; "enable32BitAppOnWin64"
0x180046122  lea     rcx, [rbp+arg_8]; struct CONFIG_ERROR **
0x180046126  call    ?CreateAndInitWithBool@CONFIG_ERROR@@SAXPEAPEAV1@PEBGHPEAVINativePropertyException@@@Z; CONFIG_ERROR::CreateAndInitWithBool(CONFIG_ERROR * *,ushort const *,int,INativePropertyException *)
0x18004612b  mov     rdx, [rbp+arg_8]; struct CONFIG_ERROR *
0x18004612f  test    rdx, rdx
0x180046132  jz      short loc_180046147
0x180046134  lea     rcx, [r14+3E8h]; this
0x18004613b  mov     dword ptr [rdx+8], 29h ; ')'
0x180046142  call    ?Add@CONFIG_ERROR_LIST@@QEAAXPEAVCONFIG_ERROR@@@Z; CONFIG_ERROR_LIST::Add(CONFIG_ERROR *)
0x180046147  mov     rcx, [rbp+arg_0]
0x18004614b  mov     [rbp+arg_8], 0
0x180046153  mov     rax, [rcx]
0x180046156  mov     rax, [rax+10h]
0x18004615a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004615f  mov     [rbp+arg_0], 0
0x180046167  mov     rax, [r15]
0x18004616a  lea     r12, [r14+2E0h]
0x180046171  lea     r9, [rbp+arg_0]
0x180046175  mov     [rsp+58h+var_38], 0
0x18004617e  mov     r8, r12
0x180046181  lea     rdx, aEnableemulatio_0; "enableEmulationOnWinArm64"
0x180046188  mov     rcx, r15
0x18004618b  mov     rax, [rax+48h]
0x18004618f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046194  mov     ebx, eax
0x180046196  test    eax, eax
0x180046198  jns     short loc_1800461B2
0x18004619a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800461a1  jz      loc_180046757
0x1800461a7  mov     r8d, 0ACh
0x1800461ad  jmp     loc_180045F59
0x1800461b2  mov     eax, cs:g_dwDebugFlags
0x1800461b8  test    al, 3
0x1800461ba  setnz   cl
0x1800461bd  bt      eax, 1Eh
0x1800461c1  setb    al
0x1800461c4  test    al, cl
0x1800461c6  jz      short loc_180046205
0x1800461c8  cmp     dword ptr [r12], 0
0x1800461cd  lea     rcx, aFalse_1; "FALSE"
0x1800461d4  mov     rax, r13
0x1800461d7  mov     r9, rdi
0x1800461da  cmovz   rax, rcx
0x1800461de  mov     r8d, 0B4h
0x1800461e4  mov     rcx, cs:g_pDebug
0x1800461eb  mov     rdx, rsi
0x1800461ee  mov     [rsp+58h+var_30], rax
0x1800461f3  lea     rax, aEnableemulatio; " EnableEmulationOnWinArm64 = %S \n"
0x1800461fa  mov     [rsp+58h+var_38], rax
0x1800461ff  call    cs:__imp_PuDbgPrint
0x180046205  mov     r9, [rbp+arg_0]; struct INativePropertyException *
0x180046209  test    r9, r9
0x18004620c  jz      short loc_18004625E
0x18004620e  mov     r8d, [r12]; int
0x180046212  lea     rdx, aEnableemulatio_0; "enableEmulationOnWinArm64"
0x180046219  lea     rcx, [rbp+arg_8]; struct CONFIG_ERROR **
0x18004621d  call    ?CreateAndInitWithBool@CONFIG_ERROR@@SAXPEAPEAV1@PEBGHPEAVINativePropertyException@@@Z; CONFIG_ERROR::CreateAndInitWithBool(CONFIG_ERROR * *,ushort const *,int,INativePropertyException *)
0x180046222  mov     rdx, [rbp+arg_8]; struct CONFIG_ERROR *
0x180046226  test    rdx, rdx
0x180046229  jz      short loc_18004623E
0x18004622b  lea     rcx, [r14+3E8h]; this
0x180046232  mov     dword ptr [rdx+8], 2Ah ; '*'
0x180046239  call    ?Add@CONFIG_ERROR_LIST@@QEAAXPEAVCONFIG_ERROR@@@Z; CONFIG_ERROR_LIST::Add(CONFIG_ERROR *)
0x18004623e  mov     rcx, [rbp+arg_0]
0x180046242  mov     [rbp+arg_8], 0
0x18004624a  mov     rax, [rcx]
0x18004624d  mov     rax, [rax+10h]
0x180046251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046256  mov     [rbp+arg_0], 0
0x18004625e  mov     rax, [r15]
0x180046261  lea     r12, [r14+394h]
0x180046268  lea     r9, [rbp+arg_0]
0x18004626c  mov     [rsp+58h+var_38], 0
0x180046275  mov     r8, r12
0x180046278  lea     rdx, aPassanonymoust; "passAnonymousToken"
0x18004627f  mov     rcx, r15
0x180046282  mov     rax, [rax+48h]
0x180046286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004628b  mov     ebx, eax
0x18004628d  test    eax, eax
0x18004628f  jns     short loc_1800462A9
0x180046291  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180046298  jz      loc_180046757
0x18004629e  mov     r8d, 0CCh
0x1800462a4  jmp     loc_180045F59
0x1800462a9  mov     eax, cs:g_dwDebugFlags
0x1800462af  test    al, 3
0x1800462b1  setnz   cl
0x1800462b4  bt      eax, 1Eh
0x1800462b8  setb    al
0x1800462bb  test    al, cl
0x1800462bd  jz      short loc_1800462FC
0x1800462bf  cmp     dword ptr [r12], 0
0x1800462c4  lea     rcx, aFalse_1; "FALSE"
0x1800462cb  mov     rax, r13
0x1800462ce  mov     r9, rdi
0x1800462d1  cmovz   rax, rcx
0x1800462d5  mov     r8d, 0D4h
0x1800462db  mov     rcx, cs:g_pDebug
0x1800462e2  mov     rdx, rsi
0x1800462e5  mov     [rsp+58h+var_30], rax
0x1800462ea  lea     rax, aPassanonymoust_0; " PassAnonymousToken = %S \n"
0x1800462f1  mov     [rsp+58h+var_38], rax
0x1800462f6  call    cs:__imp_PuDbgPrint
0x1800462fc  mov     r9, [rbp+arg_0]; struct INativePropertyException *
  ... truncated ...
```
