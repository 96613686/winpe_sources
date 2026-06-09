# SITE_DATA_OBJECT_CS::SetLoggingSettingsFromConfigStoreData(INativeConfigurationElement *)

- ea: `0x18004d3d4`
- end: `0x18004de2b`
- name: `?SetLoggingSettingsFromConfigStoreData@SITE_DATA_OBJECT_CS@@QEAAJPEAVINativeConfigurationElement@@@Z`
- size: `2647`
- prototype: `__int64 __fastcall(SITE_DATA_OBJECT_CS *__hidden this, struct INativeConfigurationElement *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004c3e0`

## callees

- `0x18004d3d4`
- `0x180052d90`
- `0x180052ec4`
- `0x180052f8c`
- `0x180053908`
- `0x180062010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18004d52e`
- `iisutil!PuDbgPrint` at `0x18004d62a`
- `iisutil!PuDbgPrint` at `0x18004d712`
- `iisutil!PuDbgPrint` at `0x18004d801`
- `iisutil!PuDbgPrint` at `0x18004d8f5`
- `iisutil!PuDbgPrint` at `0x18004d9d3`
- `iisutil!PuDbgPrint` at `0x18004da68`
- `iisutil!PuDbgPrint` at `0x18004db2b`
- `iisutil!PuDbgPrint` at `0x18004dcac`
- `iisutil!PuDbgPrint` at `0x18004ddc3`
- `iisutil!PuDbgPrint` at `0x18004d52e`
- `iisutil!PuDbgPrint` at `0x18004d62a`
- `iisutil!PuDbgPrint` at `0x18004d712`
- `iisutil!PuDbgPrint` at `0x18004d801`
- `iisutil!PuDbgPrint` at `0x18004d8f5`
- `iisutil!PuDbgPrint` at `0x18004d9d3`
- `iisutil!PuDbgPrint` at `0x18004da68`
- `iisutil!PuDbgPrint` at `0x18004db2b`
- `iisutil!PuDbgPrint` at `0x18004dcac`
- `iisutil!PuDbgPrint` at `0x18004ddc3`
- `iisutil!PuDbgPrintError` at `0x18004d470`
- `iisutil!PuDbgPrintError` at `0x18004d470`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004da7e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004db4c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004da7e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004db4c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18004db7e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18004dbac`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18004db7e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18004dbac`

## string_xrefs

- `0x18004d445`: ` Failed reading property \n`
- `0x18004d57a`: ` Failed reading property \n`
- `0x18004d9e8`: `directory`
- `0x18004d459`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\sitestore_cs.cxx`
- `0x18004d4db`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\sitestore_cs.cxx`
- `0x18004d452`: `SITE_DATA_OBJECT_CS::SetLoggingSettingsFromConfigStoreData`
- `0x18004d4d2`: `SITE_DATA_OBJECT_CS::SetLoggingSettingsFromConfigStoreData`
- `0x18004da50`: ` Log File Directory '%S' \n`
- `0x18004dab5`: `customLogPluginClsid`
- `0x18004db65`: ` Failed copying in the { for the guid \n `
- `0x18004dbc5`: ` Failed copying in the } for the guid \n `

## pseudocode

```c
__int64 __fastcall SITE_DATA_OBJECT_CS::SetLoggingSettingsFromConfigStoreData(
        SITE_DATA_OBJECT_CS *this,
        struct INativeConfigurationElement *a2)
{
  __int64 v2; // rax
  int *v3; // r12
  __int64 (__fastcall *v6)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD); // rax
  int v7; // ebx
  const char *v8; // rax
  __int64 v9; // r8
  struct CONFIG_ERROR *v10; // rdx
  const wchar_t *v11; // r13
  const wchar_t *v12; // rax
  unsigned int *v13; // r12
  struct CONFIG_ERROR *v14; // rdx
  const unsigned __int16 *v15; // rdx
  struct CONFIG_ERROR *v16; // rdx
  int v17; // eax
  int v18; // edx
  bool v19; // cl
  unsigned int *v20; // r12
  struct CONFIG_ERROR *v21; // rdx
  int *v22; // r12
  struct CONFIG_ERROR *v23; // rdx
  unsigned int *v24; // r12
  struct CONFIG_ERROR *v25; // rdx
  const wchar_t *v26; // r12
  const wchar_t *v27; // rcx
  unsigned int *v28; // r12
  struct CONFIG_ERROR *v29; // rdx
  __int64 v31; // [rsp+40h] [rbp-18h] BYREF
  __int64 v32; // [rsp+48h] [rbp-10h] BYREF
  struct INativePropertyException *v33; // [rsp+A0h] [rbp+48h] BYREF
  struct CONFIG_ERROR *v34; // [rsp+A8h] [rbp+50h] BYREF
  const unsigned __int16 *v35; // [rsp+B0h] [rbp+58h] BYREF
  __int64 v36; // [rsp+B8h] [rbp+60h] BYREF

  v2 = *(_QWORD *)a2;
  v3 = (int *)((char *)this + 140);
  v35 = 0;
  v32 = 0;
  v6 = *(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(v2 + 72);
  v33 = 0;
  v31 = 0;
  v36 = 0;
  v34 = 0;
  v7 = v6(a2, L"enabled", (char *)this + 140, &v33, 0);
  if ( v7 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_111;
    v8 = " Failed reading property \n";
    v9 = 390;
    goto LABEL_4;
  }
  if ( v33 )
  {
    CONFIG_ERROR::CreateAndInitWithBool(&v34, L"enabled", *v3, v33);
    v10 = v34;
    if ( v34 )
    {
      *((_DWORD *)v34 + 2) = 72;
      CONFIG_ERROR_LIST::Add((SITE_DATA_OBJECT_CS *)((char *)this + 304), v10);
    }
    v34 = 0;
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v33 + 16LL))(v33);
    v33 = 0;
  }
  v11 = L"TRUE";
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
  {
    v12 = L"TRUE";
    if ( !*v3 )
      v12 = L"FALSE";
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_cs.cxx",
      411,
      "SITE_DATA_OBJECT_CS::SetLoggingSettingsFromConfigStoreData",
      " Log Enabled = %S \n ",
      v12);
  }
  v13 = (unsigned int *)((char *)this + 144);
  v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 48LL))(
         a2,
         L"period",
         (char *)this + 144,
         &v33,
         0);
  if ( v7 >= 0 )
  {
    if ( v33 )
    {
      CONFIG_ERROR::CreateAndInitWithLong(&v34, L"period", *v13, v33);
      v14 = v34;
      if ( v34 )
      {
        *((_DWORD *)v34 + 2) = 73;
        CONFIG_ERROR_LIST::Add((SITE_DATA_OBJECT_CS *)((char *)this + 304), v14);
      }
      v34 = 0;
      (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v33 + 16LL))(v33);
      v33 = 0;
    }
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_cs.cxx",
        445,
        "SITE_DATA_OBJECT_CS::SetLoggingSettingsFromConfigStoreData",
        " Log File Period = %u (0x%X) (%d) \n ",
        *v13,
        *v13,
        *v13);
    v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, __int64 *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 56LL))(
           a2,
           L"truncateSize",
           &v32,
           &v33,
           0);
    if ( v7 >= 0 )
    {
      if ( v33 )
      {
        CONFIG_ERROR::CreateAndInitWithInt64(&v34, v15, v32, v33);
        v16 = v34;
        if ( v34 )
        {
          *((_DWORD *)v34 + 2) = 74;
          CONFIG_ERROR_LIST::Add((SITE_DATA_OBJECT_CS *)((char *)this + 304), v16);
        }
        v34 = 0;
        (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v33 + 16LL))(v33);
        v33 = 0;
      }
      v17 = g_dwDebugFlags;
      v18 = v32;
      v19 = (g_dwDebugFlags & 3) != 0;
      *((_DWORD *)this + 37) = v32;
      if ( v19 && (v17 & 0x40000000) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_cs.cxx",
          484,
          "SITE_DATA_OBJECT_CS::SetLoggingSettingsFromConfigStoreData",
          " Log File Trucate Size = %u (0x%X) (%d) \n ",
          v18,
          v18,
          v18);
      v20 = (unsigned int *)((char *)this + 152);
      v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 48LL))(
             a2,
             L"logExtFileFlags",
             (char *)this + 152,
             &v33,
             0);
      if ( v7 >= 0 )
      {
        if ( v33 )
        {
          CONFIG_ERROR::CreateAndInitWithLong(&v34, L"logExtFileFlags", *v20, v33);
          v21 = v34;
          if ( v34 )
          {
            *((_DWORD *)v34 + 2) = 75;
            CONFIG_ERROR_LIST::Add((SITE_DATA_OBJECT_CS *)((char *)this + 304), v21);
          }
          v34 = 0;
          (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v33 + 16LL))(v33);
          v33 = 0;
        }
        if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_cs.cxx",
            517,
            "SITE_DATA_OBJECT_CS::SetLoggingSettingsFromConfigStoreData",
            " Log Ext File Flags = %u (0x%X) (%d) \n ",
            *v20,
            *v20,
            *v20);
        v22 = (int *)((char *)this + 156);
        v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 72LL))(
               a2,
               L"localTimeRollover",
               (char *)this + 156,
               &v33,
               0);
        if ( v7 >= 0 )
        {
          if ( v33 )
          {
            CONFIG_ERROR::CreateAndInitWithBool(&v34, L"localTimeRollover", *v22, v33);
            v23 = v34;
            if ( v34 )
            {
              *((_DWORD *)v34 + 2) = 76;
              CONFIG_ERROR_LIST::Add((SITE_DATA_OBJECT_CS *)((char *)this + 304), v23);
            }
            v34 = 0;
            (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v33 + 16LL))(v33);
            v33 = 0;
          }
          if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
          {
            if ( !*v22 )
              v11 = L"FALSE";
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_cs.cxx",
              548,
              "SITE_DATA_OBJECT_CS::SetLoggingSettingsFromConfigStoreData",
              " Localtime Rollover = %S \n ",
              v11);
          }
          v24 = (unsigned int *)((char *)this + 160);
          v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 48LL))(
                 a2,
                 L"logFormat",
                 (char *)this + 160,
                 &v33,
                 0);
          if ( v7 >= 0 )
          {
            if ( v33 )
            {
              CONFIG_ERROR::CreateAndInitWithLong(&v34, L"logFormat", *v24, v33);
              v25 = v34;
              if ( v34 )
              {
                *((_DWORD *)v34 + 2) = 77;
                CONFIG_ERROR_LIST::Add((SITE_DATA_OBJECT_CS *)((char *)this + 304), v25);
              }
              v34 = 0;
              (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v33 + 16LL))(v33);
              v33 = 0;
            }
            if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
              PuDbgPrint(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_cs.cxx",
                579,
                "SITE_DATA_OBJECT_CS::SetLoggingSettingsFromConfigStoreData",
                " LogFormat = %d \n ",
                *v24);
            v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)a2 + 64LL))(
                   a2,
                   L"directory",
                   &v35,
                   0,
                   0);
            if ( v7 >= 0 )
            {
              v26 = L"NULL";
              if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
              {
                v27 = L"NULL";
                if ( v35 )
                  v27 = v35;
                PuDbgPrint(
                  g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_cs.cxx",
                  598,
                  "SITE_DATA_OBJECT_CS::SetLoggingSettingsFromConfigStoreData",
                  " Log File Directory '%S' \n",
                  v27);
              }
              if ( v35 )
              {
                v7 = STRU::Copy((SITE_DATA_OBJECT_CS *)((char *)this + 224), v35);
                if ( v7 < 0 )
                {
                  if ( (g_dwDebugFlags & 0xF) != 0 )
                  {
                    v9 = 608;
                    goto LABEL_16;
                  }
                  goto LABEL_111;
                }
                v35 = 0;
              }
              v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)a2 + 64LL))(
                     a2,
                     L"customLogPluginClsid",
                     &v35,
                     0,
                     0);
              if ( v7 >= 0 )
              {
                if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
                {
                  if ( v35 )
                    v26 = v35;
                  PuDbgPrint(
                    g_pDebug,
                    "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_cs.cxx",
                    630,
                    "SITE_DATA_OBJECT_CS::SetLoggingSettingsFromConfigStoreData",
                    " Logging Module '%S' \n",
                    v26);
                }
                if ( v35 )
                {
                  v7 = STRU::Copy((SITE_DATA_OBJECT_CS *)((char *)this + 168), L"{");
                  if ( v7 < 0 )
                  {
                    if ( (g_dwDebugFlags & 0xF) != 0 )
                    {
                      v8 = " Failed copying in the { for the guid \n ";
                      v9 = 640;
                      goto LABEL_4;
                    }
                    goto LABEL_111;
                  }
                  v7 = STRU::Append((SITE_DATA_OBJECT_CS *)((char *)this + 168), v35);
                  if ( v7 < 0 )
                  {
                    if ( (g_dwDebugFlags & 0xF) != 0 )
                    {
                      v9 = 650;
                      goto LABEL_16;
                    }
                    goto LABEL_111;
                  }
                  v7 = STRU::Append((SITE_DATA_OBJECT_CS *)((char *)this + 168), L"}");
                  if ( v7 < 0 )
                  {
                    if ( (g_dwDebugFlags & 0xF) != 0 )
                    {
                      v8 = " Failed copying in the } for the guid \n ";
                      v9 = 659;
                      goto LABEL_4;
                    }
                    goto LABEL_111;
                  }
                  v35 = 0;
                }
                v28 = (unsigned int *)((char *)this + 280);
                v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 48LL))(
                       a2,
                       L"logTargetW3C",
                       (char *)this + 280,
                       &v33,
                       0);
                if ( v7 >= 0 )
                {
                  if ( v33 )
                  {
                    CONFIG_ERROR::CreateAndInitWithLong(&v34, L"logTargetW3C", *v28, v33);
                    v29 = v34;
                    if ( v34 )
                    {
                      *((_DWORD *)v34 + 2) = 78;
                      CONFIG_ERROR_LIST::Add((SITE_DATA_OBJECT_CS *)((char *)this + 304), v29);
                    }
                    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v33 + 16LL))(v33);
                    v33 = 0;
                  }
                  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
                    PuDbgPrint(
                      g_pDebug,
                      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_cs.cxx",
                      695,
                      "SITE_DATA_OBJECT_CS::SetLoggingSettingsFromConfigStoreData",
                      " LogTargetW3C = %d \n ",
                      *v28);
                  v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, __int64 *))(*(_QWORD *)a2 + 32LL))(
                         a2,
                         L"customFields",
                         &v36);
                  if ( v7 >= 0 )
                  {
                    v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v36 + 40LL))(v36, &v31);
                    if ( v7 >= 0 )
                    {
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
                      v36 = 0;
                      v7 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v31 + 24LL))(v31, (char *)this + 284);
                      if ( v7 >= 0 )
                      {
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
                        v31 = 0;
                        if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
                          PuDbgPrint(
                            g_pDebug,
                            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_cs.cxx",
                            736,
                            "SITE_DATA_OBJECT_CS::SetLoggingSettingsFromConfigStoreData",
                            " CustomFields Count = %d \n ",
                            *((_DWORD *)this + 71));
                      }
                      else if ( (g_dwDebugFlags & 0xF) != 0 )
                      {
                        v8 = " Failed getting count of custom field in customFields collection \n";
                        v9 = 725;
                        goto LABEL_4;
                      }
                    }
                    else if ( (g_dwDebugFlags & 0xF) != 0 )
                    {
                      v8 = " Failed getting customFields collection \n";
                      v9 = 713;
                      goto LABEL_4;
                    }
                  }
                  else if ( (g_dwDebugFlags & 0xF) != 0 )
                  {
                    v9 = 704;
                    goto LABEL_16;
                  }
                }
                else if ( (g_dwDebugFlags & 0xF) != 0 )
                {
                  v9 = 674;
                  goto LABEL_16;
                }
                goto LABEL_111;
              }
              if ( (g_dwDebugFlags & 0xF) != 0 )
              {
                v9 = 622;
                goto LABEL_16;
              }
            }
            else if ( (g_dwDebugFlags & 0xF) != 0 )
            {
              v9 = 589;
              goto LABEL_16;
            }
          }
          else if ( (g_dwDebugFlags & 0xF) != 0 )
          {
            v9 = 558;
            goto LABEL_16;
          }
        }
        else if ( (g_dwDebugFlags & 0xF) != 0 )
        {
          v9 = 527;
          goto LABEL_16;
        }
      }
      else if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        v9 = 494;
        goto LABEL_16;
      }
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      v9 = 457;
      goto LABEL_16;
    }
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    v9 = 422;
LABEL_16:
    v8 = " Failed reading property \n";
LABEL_4:
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_cs.cxx",
      v9,
      "SITE_DATA_OBJECT_CS::SetLoggingSettingsFromConfigStoreData",
      v7,
      v8);
  }
LABEL_111:
  if ( v33 )
  {
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v33 + 16LL))(v33);
    v33 = 0;
  }
  if ( v36 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    v36 = 0;
  }
  if ( v31 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18004d3d4  push    rbp
0x18004d3d6  push    rbx
0x18004d3d7  push    rsi
0x18004d3d8  push    rdi
0x18004d3d9  push    r12
0x18004d3db  push    r13
0x18004d3dd  push    r14
0x18004d3df  push    r15
0x18004d3e1  mov     rbp, rsp
0x18004d3e4  sub     rsp, 58h
0x18004d3e8  mov     rax, [rdx]
0x18004d3eb  lea     r12, [rcx+8Ch]
0x18004d3f2  xor     r13d, r13d
0x18004d3f5  lea     r9, [rbp+arg_0]
0x18004d3f9  mov     r15, rdx
0x18004d3fc  mov     [rbp+arg_10], r13
0x18004d400  mov     r14, rcx
0x18004d403  mov     [rbp+var_10], r13
0x18004d407  mov     rax, [rax+48h]
0x18004d40b  lea     rdx, aEnabled; "enabled"
0x18004d412  mov     r8, r12
0x18004d415  mov     [rbp+arg_0], r13
0x18004d419  mov     rcx, r15
0x18004d41c  mov     [rbp+var_18], r13
0x18004d420  mov     [rbp+arg_18], r13
0x18004d424  mov     [rbp+arg_8], r13
0x18004d428  mov     [rsp+58h+var_38], r13
0x18004d42d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d432  mov     ebx, eax
0x18004d434  test    eax, eax
0x18004d436  jns     short loc_18004D47B
0x18004d438  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004d43f  jz      loc_18004DDC9
0x18004d445  lea     rax, aFailedReadingP_1; " Failed reading property \n"
0x18004d44c  mov     r8d, 186h
0x18004d452  lea     r9, aSiteDataObject_6; "SITE_DATA_OBJECT_CS::SetLoggingSettings"...
0x18004d459  lea     rdx, aServercommonIn_40; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18004d460  mov     rcx, cs:g_pDebug
0x18004d467  mov     [rsp+58h+var_30], rax
0x18004d46c  mov     dword ptr [rsp+58h+var_38], ebx
0x18004d470  call    cs:__imp_PuDbgPrintError
0x18004d476  jmp     loc_18004DDC9
0x18004d47b  mov     r9, [rbp+arg_0]; struct INativePropertyException *
0x18004d47f  test    r9, r9
0x18004d482  jz      short loc_18004D4CC
0x18004d484  mov     r8d, [r12]; int
0x18004d488  lea     rdx, aEnabled; "enabled"
0x18004d48f  lea     rcx, [rbp+arg_8]; struct CONFIG_ERROR **
0x18004d493  call    ?CreateAndInitWithBool@CONFIG_ERROR@@SAXPEAPEAV1@PEBGHPEAVINativePropertyException@@@Z; CONFIG_ERROR::CreateAndInitWithBool(CONFIG_ERROR * *,ushort const *,int,INativePropertyException *)
0x18004d498  mov     rdx, [rbp+arg_8]; struct CONFIG_ERROR *
0x18004d49c  test    rdx, rdx
0x18004d49f  jz      short loc_18004D4B4
0x18004d4a1  lea     rcx, [r14+130h]; this
0x18004d4a8  mov     dword ptr [rdx+8], 48h ; 'H'
0x18004d4af  call    ?Add@CONFIG_ERROR_LIST@@QEAAXPEAVCONFIG_ERROR@@@Z; CONFIG_ERROR_LIST::Add(CONFIG_ERROR *)
0x18004d4b4  mov     rcx, [rbp+arg_0]
0x18004d4b8  mov     [rbp+arg_8], r13
0x18004d4bc  mov     rax, [rcx]
0x18004d4bf  mov     rax, [rax+10h]
0x18004d4c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d4c8  mov     [rbp+arg_0], r13
0x18004d4cc  mov     eax, cs:g_dwDebugFlags
0x18004d4d2  lea     rdi, aSiteDataObject_6; "SITE_DATA_OBJECT_CS::SetLoggingSettings"...
0x18004d4d9  test    al, 3
0x18004d4db  lea     rsi, aServercommonIn_40; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18004d4e2  lea     rdx, aFalse_1; "FALSE"
0x18004d4e9  setnz   cl
0x18004d4ec  lea     r13, aTrue_1; "TRUE"
0x18004d4f3  bt      eax, 1Eh
0x18004d4f7  setb    al
0x18004d4fa  test    al, cl
0x18004d4fc  jz      short loc_18004D534
0x18004d4fe  cmp     dword ptr [r12], 0
0x18004d503  mov     rax, r13
0x18004d506  mov     rcx, cs:g_pDebug
0x18004d50d  mov     r9, rdi
0x18004d510  cmovz   rax, rdx
0x18004d514  mov     r8d, 19Bh
0x18004d51a  mov     [rsp+58h+var_30], rax
0x18004d51f  mov     rdx, rsi
0x18004d522  lea     rax, aLogEnabledS; " Log Enabled = %S \n "
0x18004d529  mov     [rsp+58h+var_38], rax
0x18004d52e  call    cs:__imp_PuDbgPrint
0x18004d534  mov     rax, [r15]
0x18004d537  lea     r12, [r14+90h]
0x18004d53e  lea     r9, [rbp+arg_0]
0x18004d542  mov     [rsp+58h+var_38], 0
0x18004d54b  mov     r8, r12
0x18004d54e  lea     rdx, aPeriod; "period"
0x18004d555  mov     rcx, r15
0x18004d558  mov     rax, [rax+30h]
0x18004d55c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d561  mov     ebx, eax
0x18004d563  test    eax, eax
0x18004d565  jns     short loc_18004D58C
0x18004d567  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004d56e  jz      loc_18004DDC9
0x18004d574  mov     r8d, 1A6h
0x18004d57a  lea     rax, aFailedReadingP_1; " Failed reading property \n"
0x18004d581  mov     r9, rdi
0x18004d584  mov     rdx, rsi
0x18004d587  jmp     loc_18004D460
0x18004d58c  mov     r9, [rbp+arg_0]; struct INativePropertyException *
0x18004d590  test    r9, r9
0x18004d593  jz      short loc_18004D5E5
0x18004d595  mov     r8d, [r12]; int
0x18004d599  lea     rdx, aPeriod; "period"
0x18004d5a0  lea     rcx, [rbp+arg_8]; struct CONFIG_ERROR **
0x18004d5a4  call    ?CreateAndInitWithLong@CONFIG_ERROR@@SAXPEAPEAV1@PEBGJPEAVINativePropertyException@@@Z; CONFIG_ERROR::CreateAndInitWithLong(CONFIG_ERROR * *,ushort const *,long,INativePropertyException *)
0x18004d5a9  mov     rdx, [rbp+arg_8]; struct CONFIG_ERROR *
0x18004d5ad  test    rdx, rdx
0x18004d5b0  jz      short loc_18004D5C5
0x18004d5b2  lea     rcx, [r14+130h]; this
0x18004d5b9  mov     dword ptr [rdx+8], 49h ; 'I'
0x18004d5c0  call    ?Add@CONFIG_ERROR_LIST@@QEAAXPEAVCONFIG_ERROR@@@Z; CONFIG_ERROR_LIST::Add(CONFIG_ERROR *)
0x18004d5c5  mov     rcx, [rbp+arg_0]
0x18004d5c9  mov     [rbp+arg_8], 0
0x18004d5d1  mov     rax, [rcx]
0x18004d5d4  mov     rax, [rax+10h]
0x18004d5d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d5dd  mov     [rbp+arg_0], 0
0x18004d5e5  mov     eax, cs:g_dwDebugFlags
0x18004d5eb  test    al, 3
0x18004d5ed  setnz   cl
0x18004d5f0  bt      eax, 1Eh
0x18004d5f4  setb    al
0x18004d5f7  test    al, cl
0x18004d5f9  jz      short loc_18004D630
0x18004d5fb  mov     eax, [r12]
0x18004d5ff  mov     r9, rdi
0x18004d602  mov     rcx, cs:g_pDebug
0x18004d609  mov     r8d, 1BDh
0x18004d60f  mov     [rsp+58h+var_20], eax
0x18004d613  mov     rdx, rsi
0x18004d616  mov     [rsp+58h+var_28], eax
0x18004d61a  mov     dword ptr [rsp+58h+var_30], eax
0x18004d61e  lea     rax, aLogFilePeriodU; " Log File Period = %u (0x%X) (%d) \n "
0x18004d625  mov     [rsp+58h+var_38], rax
0x18004d62a  call    cs:__imp_PuDbgPrint
0x18004d630  mov     rax, [r15]
0x18004d633  lea     r9, [rbp+arg_0]
0x18004d637  lea     r8, [rbp+var_10]
0x18004d63b  mov     [rsp+58h+var_38], 0
0x18004d644  lea     rdx, aTruncatesize; "truncateSize"
0x18004d64b  mov     rcx, r15
0x18004d64e  mov     rax, [rax+38h]
0x18004d652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d657  mov     ebx, eax
0x18004d659  test    eax, eax
0x18004d65b  jns     short loc_18004D675
0x18004d65d  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004d664  jz      loc_18004DDC9
0x18004d66a  mov     r8d, 1C9h
0x18004d670  jmp     loc_18004D57A
0x18004d675  mov     r9, [rbp+arg_0]; struct INativePropertyException *
0x18004d679  test    r9, r9
0x18004d67c  jz      short loc_18004D6C7
0x18004d67e  mov     r8, [rbp+var_10]; __int64
0x18004d682  lea     rcx, [rbp+arg_8]; struct CONFIG_ERROR **
0x18004d686  call    ?CreateAndInitWithInt64@CONFIG_ERROR@@SAXPEAPEAV1@PEBG_JPEAVINativePropertyException@@@Z; CONFIG_ERROR::CreateAndInitWithInt64(CONFIG_ERROR * *,ushort const *,__int64,INativePropertyException *)
0x18004d68b  mov     rdx, [rbp+arg_8]; struct CONFIG_ERROR *
0x18004d68f  test    rdx, rdx
0x18004d692  jz      short loc_18004D6A7
0x18004d694  lea     rcx, [r14+130h]; this
0x18004d69b  mov     dword ptr [rdx+8], 4Ah ; 'J'
0x18004d6a2  call    ?Add@CONFIG_ERROR_LIST@@QEAAXPEAVCONFIG_ERROR@@@Z; CONFIG_ERROR_LIST::Add(CONFIG_ERROR *)
0x18004d6a7  mov     rcx, [rbp+arg_0]
0x18004d6ab  mov     [rbp+arg_8], 0
0x18004d6b3  mov     rax, [rcx]
0x18004d6b6  mov     rax, [rax+10h]
0x18004d6ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d6bf  mov     [rbp+arg_0], 0
0x18004d6c7  mov     eax, cs:g_dwDebugFlags
0x18004d6cd  test    al, 3
0x18004d6cf  mov     edx, dword ptr [rbp+var_10]
0x18004d6d2  setnz   cl
0x18004d6d5  mov     [r14+94h], edx
0x18004d6dc  bt      eax, 1Eh
0x18004d6e0  setb    al
0x18004d6e3  test    al, cl
0x18004d6e5  jz      short loc_18004D718
0x18004d6e7  mov     rcx, cs:g_pDebug
0x18004d6ee  lea     rax, aLogFileTrucate; " Log File Trucate Size = %u (0x%X) (%d)"...
0x18004d6f5  mov     [rsp+58h+var_20], edx
0x18004d6f9  mov     r9, rdi
0x18004d6fc  mov     [rsp+58h+var_28], edx
0x18004d700  mov     r8d, 1E4h
0x18004d706  mov     dword ptr [rsp+58h+var_30], edx
0x18004d70a  mov     rdx, rsi
0x18004d70d  mov     [rsp+58h+var_38], rax
0x18004d712  call    cs:__imp_PuDbgPrint
0x18004d718  mov     rax, [r15]
0x18004d71b  lea     r12, [r14+98h]
0x18004d722  lea     r9, [rbp+arg_0]
0x18004d726  mov     [rsp+58h+var_38], 0
0x18004d72f  mov     r8, r12
0x18004d732  lea     rdx, aLogextfileflag; "logExtFileFlags"
0x18004d739  mov     rcx, r15
0x18004d73c  mov     rax, [rax+30h]
0x18004d740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d745  mov     ebx, eax
0x18004d747  test    eax, eax
0x18004d749  jns     short loc_18004D763
0x18004d74b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004d752  jz      loc_18004DDC9
0x18004d758  mov     r8d, 1EEh
0x18004d75e  jmp     loc_18004D57A
0x18004d763  mov     r9, [rbp+arg_0]; struct INativePropertyException *
0x18004d767  test    r9, r9
0x18004d76a  jz      short loc_18004D7BC
0x18004d76c  mov     r8d, [r12]; int
0x18004d770  lea     rdx, aLogextfileflag; "logExtFileFlags"
0x18004d777  lea     rcx, [rbp+arg_8]; struct CONFIG_ERROR **
0x18004d77b  call    ?CreateAndInitWithLong@CONFIG_ERROR@@SAXPEAPEAV1@PEBGJPEAVINativePropertyException@@@Z; CONFIG_ERROR::CreateAndInitWithLong(CONFIG_ERROR * *,ushort const *,long,INativePropertyException *)
0x18004d780  mov     rdx, [rbp+arg_8]; struct CONFIG_ERROR *
0x18004d784  test    rdx, rdx
0x18004d787  jz      short loc_18004D79C
0x18004d789  lea     rcx, [r14+130h]; this
0x18004d790  mov     dword ptr [rdx+8], 4Bh ; 'K'
0x18004d797  call    ?Add@CONFIG_ERROR_LIST@@QEAAXPEAVCONFIG_ERROR@@@Z; CONFIG_ERROR_LIST::Add(CONFIG_ERROR *)
0x18004d79c  mov     rcx, [rbp+arg_0]
0x18004d7a0  mov     [rbp+arg_8], 0
0x18004d7a8  mov     rax, [rcx]
0x18004d7ab  mov     rax, [rax+10h]
0x18004d7af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d7b4  mov     [rbp+arg_0], 0
0x18004d7bc  mov     eax, cs:g_dwDebugFlags
0x18004d7c2  test    al, 3
0x18004d7c4  setnz   cl
0x18004d7c7  bt      eax, 1Eh
0x18004d7cb  setb    al
0x18004d7ce  test    al, cl
0x18004d7d0  jz      short loc_18004D807
0x18004d7d2  mov     eax, [r12]
0x18004d7d6  mov     r9, rdi
0x18004d7d9  mov     rcx, cs:g_pDebug
0x18004d7e0  mov     r8d, 205h
0x18004d7e6  mov     [rsp+58h+var_20], eax
0x18004d7ea  mov     rdx, rsi
0x18004d7ed  mov     [rsp+58h+var_28], eax
0x18004d7f1  mov     dword ptr [rsp+58h+var_30], eax
0x18004d7f5  lea     rax, aLogExtFileFlag; " Log Ext File Flags = %u (0x%X) (%d) \n"...
0x18004d7fc  mov     [rsp+58h+var_38], rax
0x18004d801  call    cs:__imp_PuDbgPrint
0x18004d807  mov     rax, [r15]
0x18004d80a  lea     r12, [r14+9Ch]
0x18004d811  lea     r9, [rbp+arg_0]
0x18004d815  mov     [rsp+58h+var_38], 0
0x18004d81e  mov     r8, r12
0x18004d821  lea     rdx, aLocaltimerollo; "localTimeRollover"
0x18004d828  mov     rcx, r15
0x18004d82b  mov     rax, [rax+48h]
0x18004d82f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d834  mov     ebx, eax
0x18004d836  test    eax, eax
0x18004d838  jns     short loc_18004D852
0x18004d83a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004d841  jz      loc_18004DDC9
0x18004d847  mov     r8d, 20Fh
0x18004d84d  jmp     loc_18004D57A
0x18004d852  mov     r9, [rbp+arg_0]; struct INativePropertyException *
0x18004d856  test    r9, r9
0x18004d859  jz      short loc_18004D8AB
0x18004d85b  mov     r8d, [r12]; int
0x18004d85f  lea     rdx, aLocaltimerollo; "localTimeRollover"
0x18004d866  lea     rcx, [rbp+arg_8]; struct CONFIG_ERROR **
0x18004d86a  call    ?CreateAndInitWithBool@CONFIG_ERROR@@SAXPEAPEAV1@PEBGHPEAVINativePropertyException@@@Z; CONFIG_ERROR::CreateAndInitWithBool(CONFIG_ERROR * *,ushort const *,int,INativePropertyException *)
0x18004d86f  mov     rdx, [rbp+arg_8]; struct CONFIG_ERROR *
0x18004d873  test    rdx, rdx
0x18004d876  jz      short loc_18004D88B
0x18004d878  lea     rcx, [r14+130h]; this
0x18004d87f  mov     dword ptr [rdx+8], 4Ch ; 'L'
0x18004d886  call    ?Add@CONFIG_ERROR_LIST@@QEAAXPEAVCONFIG_ERROR@@@Z; CONFIG_ERROR_LIST::Add(CONFIG_ERROR *)
0x18004d88b  mov     rcx, [rbp+arg_0]
0x18004d88f  mov     [rbp+arg_8], 0
0x18004d897  mov     rax, [rcx]
0x18004d89a  mov     rax, [rax+10h]
0x18004d89e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d8a3  mov     [rbp+arg_0], 0
0x18004d8ab  mov     eax, cs:g_dwDebugFlags
0x18004d8b1  test    al, 3
0x18004d8b3  setnz   cl
0x18004d8b6  bt      eax, 1Eh
0x18004d8ba  setb    al
0x18004d8bd  test    al, cl
0x18004d8bf  jz      short loc_18004D8FB
0x18004d8c1  cmp     dword ptr [r12], 0
0x18004d8c6  lea     rax, aFalse_1; "FALSE"
0x18004d8cd  mov     rcx, cs:g_pDebug
0x18004d8d4  mov     r9, rdi
0x18004d8d7  cmovz   r13, rax
0x18004d8db  mov     r8d, 224h
0x18004d8e1  lea     rax, aLocaltimeRollo; " Localtime Rollover = %S \n "
0x18004d8e8  mov     [rsp+58h+var_30], r13
0x18004d8ed  mov     rdx, rsi
0x18004d8f0  mov     [rsp+58h+var_38], rax
0x18004d8f5  call    cs:__imp_PuDbgPrint
0x18004d8fb  mov     rax, [r15]
0x18004d8fe  lea     r12, [r14+0A0h]
0x18004d905  xor     r13d, r13d
  ... truncated ...
```
