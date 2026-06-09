# APP_POOL_DATA_OBJECT_CS::SetProcessorSettingsFromConfigStoreData(INativeConfigurationElement *)

- ea: `0x180047e18`
- end: `0x180048711`
- name: `?SetProcessorSettingsFromConfigStoreData@APP_POOL_DATA_OBJECT_CS@@QEAAJPEAVINativeConfigurationElement@@@Z`
- size: `2297`
- prototype: `__int64 __fastcall(APP_POOL_DATA_OBJECT_CS *__hidden this, struct INativeConfigurationElement *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180044950`

## callees

- `0x180047e18`
- `0x180052d90`
- `0x180052f8c`
- `0x18005304c`
- `0x180053908`
- `0x180062010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180047f5e`
- `iisutil!PuDbgPrint` at `0x180047fb9`
- `iisutil!PuDbgPrint` at `0x1800480a9`
- `iisutil!PuDbgPrint` at `0x1800481d4`
- `iisutil!PuDbgPrint` at `0x1800482c2`
- `iisutil!PuDbgPrint` at `0x180048440`
- `iisutil!PuDbgPrint` at `0x18004851f`
- `iisutil!PuDbgPrint` at `0x1800485fe`
- `iisutil!PuDbgPrint` at `0x1800486dc`
- `iisutil!PuDbgPrint` at `0x180047f5e`
- `iisutil!PuDbgPrint` at `0x180047fb9`
- `iisutil!PuDbgPrint` at `0x1800480a9`
- `iisutil!PuDbgPrint` at `0x1800481d4`
- `iisutil!PuDbgPrint` at `0x1800482c2`
- `iisutil!PuDbgPrint` at `0x180048440`
- `iisutil!PuDbgPrint` at `0x18004851f`
- `iisutil!PuDbgPrint` at `0x1800485fe`
- `iisutil!PuDbgPrint` at `0x1800486dc`
- `iisutil!PuDbgPrintError` at `0x180047eab`
- `iisutil!PuDbgPrintError` at `0x180047eab`

## string_xrefs

- `0x180047e80`: ` Failed reading property \n`
- `0x180048001`: ` Failed reading property \n`
- `0x180047e94`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\apppoolstore_cs.cxx`
- `0x180047f19`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\apppoolstore_cs.cxx`
- `0x180047e8d`: `APP_POOL_DATA_OBJECT_CS::SetProcessorSettingsFromConfigStoreData`
- `0x180047f0e`: `APP_POOL_DATA_OBJECT_CS::SetProcessorSettingsFromConfigStoreData`
- `0x1800480e5`: ` Failed reading CPU Reset Interval property \n`

## pseudocode

```c
__int64 __fastcall APP_POOL_DATA_OBJECT_CS::SetProcessorSettingsFromConfigStoreData(
        APP_POOL_DATA_OBJECT_CS *this,
        struct INativeConfigurationElement *a2)
{
  __int64 v2; // rax
  unsigned int *v3; // r12
  __int64 (__fastcall *v6)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD); // rax
  int v7; // ebx
  const char *v8; // rax
  __int64 v9; // r8
  struct CONFIG_ERROR *v10; // rdx
  int v11; // r8d
  unsigned int v12; // edx
  unsigned int *v13; // r12
  struct CONFIG_ERROR *v14; // rdx
  __int64 v15; // r8
  struct INativePropertyException *v16; // r9
  struct CONFIG_ERROR *v17; // rdx
  int *v18; // r12
  struct CONFIG_ERROR *v19; // rdx
  const wchar_t *v20; // rax
  struct CONFIG_ERROR *v21; // rdx
  unsigned int *v22; // r12
  struct CONFIG_ERROR *v23; // rdx
  unsigned int *v24; // r12
  struct CONFIG_ERROR *v25; // rdx
  unsigned int *v26; // r12
  struct CONFIG_ERROR *v27; // rdx
  unsigned int *v28; // r12
  struct CONFIG_ERROR *v29; // rdx
  struct INativePropertyException *v31; // [rsp+80h] [rbp+40h] BYREF
  struct CONFIG_ERROR *v32; // [rsp+88h] [rbp+48h] BYREF
  __int64 v33; // [rsp+90h] [rbp+50h] BYREF

  v2 = *(_QWORD *)a2;
  v3 = (unsigned int *)((char *)this + 584);
  v33 = 0;
  v31 = 0;
  v6 = *(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(v2 + 48);
  v32 = 0;
  v7 = v6(a2, L"limit", (char *)this + 584, &v31, 0);
  if ( v7 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_88;
    v8 = " Failed reading property \n";
    v9 = 1835;
    goto LABEL_4;
  }
  if ( v31 )
  {
    CONFIG_ERROR::CreateAndInitWithLong(&v32, L"limit", *v3, v31);
    v10 = v32;
    if ( v32 )
    {
      *((_DWORD *)v32 + 2) = 32;
      CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v10);
    }
    v32 = 0;
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v31 + 16LL))(v31);
    v31 = 0;
  }
  v11 = g_dwDebugFlags;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
      1858,
      "APP_POOL_DATA_OBJECT_CS::SetProcessorSettingsFromConfigStoreData",
      " CPU Limit before conversion = %u (0x%X) (%d) \n ",
      *v3,
      *v3,
      *v3);
    v11 = g_dwDebugFlags;
  }
  v12 = *v3;
  if ( *v3 == 100 )
  {
    *v3 = 0;
    v12 = 0;
  }
  if ( (v11 & 3) != 0 && (v11 & 0x40000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
      1872,
      "APP_POOL_DATA_OBJECT_CS::SetProcessorSettingsFromConfigStoreData",
      " CPU Limit after conversion = %u (0x%X) (%d) \n ",
      v12,
      v12,
      v12);
  v13 = (unsigned int *)((char *)this + 580);
  v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 48LL))(
         a2,
         L"action",
         (char *)this + 580,
         &v31,
         0);
  if ( v7 >= 0 )
  {
    if ( v31 )
    {
      CONFIG_ERROR::CreateAndInitWithLong(&v32, L"action", *v13, v31);
      v14 = v32;
      if ( v32 )
      {
        *((_DWORD *)v32 + 2) = 31;
        CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v14);
      }
      v32 = 0;
      (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v31 + 16LL))(v31);
      v31 = 0;
    }
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
        1905,
        "APP_POOL_DATA_OBJECT_CS::SetProcessorSettingsFromConfigStoreData",
        " CPU Action = %u (0x%X) (%d) \n ",
        *v13,
        *v13,
        *v13);
    v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, __int64 *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 80LL))(
           a2,
           L"resetInterval",
           &v33,
           &v31,
           0);
    if ( v7 >= 0 )
    {
      v15 = v33;
      v16 = v31;
      *((_DWORD *)this + 147) = v33 / 10000000 / 60;
      if ( v16 )
      {
        CONFIG_ERROR::CreateAndInitWithRawTimeSpan(&v32, L"resetInterval", v15, v16);
        v17 = v32;
        if ( v32 )
        {
          *((_DWORD *)v32 + 2) = 33;
          CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v17);
        }
        v32 = 0;
        (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v31 + 16LL))(v31);
        v31 = 0;
      }
      if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
          1940,
          "APP_POOL_DATA_OBJECT_CS::SetProcessorSettingsFromConfigStoreData",
          " CPU Reset Interval = %u (0x%X) (%d) \n ",
          *((_DWORD *)this + 147),
          *((_DWORD *)this + 147),
          *((_DWORD *)this + 147));
      v18 = (int *)((char *)this + 196);
      v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 72LL))(
             a2,
             L"smpAffinitized",
             (char *)this + 196,
             &v31,
             0);
      if ( v7 >= 0 )
      {
        if ( v31 )
        {
          CONFIG_ERROR::CreateAndInitWithBool(&v32, L"smpAffinitized", *v18, v31);
          v19 = v32;
          if ( v32 )
          {
            *((_DWORD *)v32 + 2) = 11;
            CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v19);
          }
          v32 = 0;
          (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v31 + 16LL))(v31);
          v31 = 0;
        }
        if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
        {
          v20 = L"TRUE";
          if ( !*v18 )
            v20 = L"FALSE";
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
            1971,
            "APP_POOL_DATA_OBJECT_CS::SetProcessorSettingsFromConfigStoreData",
            " SMPAffinitized = %S \n",
            v20);
        }
        v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 48LL))(
               a2,
               L"smpProcessorAffinityMask",
               (char *)this + 200,
               &v31,
               0);
        if ( v7 >= 0 )
        {
          if ( v31 )
          {
            CONFIG_ERROR::CreateAndInitWithLong(&v32, L"smpProcessorAffinityMask", *((_DWORD *)this + 50), v31);
            v21 = v32;
            if ( v32 )
            {
              *((_DWORD *)v32 + 2) = 12;
              CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v21);
            }
            v32 = 0;
            (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v31 + 16LL))(v31);
            v31 = 0;
          }
          v22 = (unsigned int *)((char *)this + 204);
          v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 48LL))(
                 a2,
                 L"smpProcessorAffinityMask2",
                 (char *)this + 204,
                 &v31,
                 0);
          if ( v7 >= 0 )
          {
            if ( v31 )
            {
              CONFIG_ERROR::CreateAndInitWithLong(&v32, L"smpProcessorAffinityMask2", *v22, v31);
              v23 = v32;
              if ( v32 )
              {
                *((_DWORD *)v32 + 2) = 13;
                CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v23);
              }
              v32 = 0;
              (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v31 + 16LL))(v31);
              v31 = 0;
            }
            if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
              PuDbgPrint(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
                2027,
                "APP_POOL_DATA_OBJECT_CS::SetProcessorSettingsFromConfigStoreData",
                " Affinity Mask = 0x%X%X \n",
                *v22,
                *((_DWORD *)this + 50));
            v24 = (unsigned int *)((char *)this + 208);
            v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 48LL))(
                   a2,
                   L"processorGroup",
                   (char *)this + 208,
                   &v31,
                   0);
            if ( v7 >= 0 )
            {
              if ( v31 )
              {
                CONFIG_ERROR::CreateAndInitWithLong(&v32, L"processorGroup", *v24, v31);
                v25 = v32;
                if ( v32 )
                {
                  *((_DWORD *)v32 + 2) = 47;
                  CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v25);
                }
                v32 = 0;
                (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v31 + 16LL))(v31);
                v31 = 0;
              }
              if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
                PuDbgPrint(
                  g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
                  2059,
                  "APP_POOL_DATA_OBJECT_CS::SetProcessorSettingsFromConfigStoreData",
                  " ProcessorGroup = %d (0x%X) \n ",
                  *v24,
                  *v24);
              v26 = (unsigned int *)((char *)this + 212);
              v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 48LL))(
                     a2,
                     L"numaNodeAssignment",
                     (char *)this + 212,
                     &v31,
                     0);
              if ( v7 >= 0 )
              {
                if ( v31 )
                {
                  CONFIG_ERROR::CreateAndInitWithLong(&v32, L"numaNodeAssignment", *v26, v31);
                  v27 = v32;
                  if ( v32 )
                  {
                    *((_DWORD *)v32 + 2) = 48;
                    CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v27);
                  }
                  v32 = 0;
                  (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v31 + 16LL))(v31);
                  v31 = 0;
                }
                if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
                  PuDbgPrint(
                    g_pDebug,
                    "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
                    2091,
                    "APP_POOL_DATA_OBJECT_CS::SetProcessorSettingsFromConfigStoreData",
                    " NumaNodeAssignment = %u (0x%X) \n ",
                    *v26,
                    *v26);
                v28 = (unsigned int *)((char *)this + 216);
                v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 48LL))(
                       a2,
                       L"numaNodeAffinityMode",
                       (char *)this + 216,
                       &v31,
                       0);
                if ( v7 >= 0 )
                {
                  if ( v31 )
                  {
                    CONFIG_ERROR::CreateAndInitWithLong(&v32, L"numaNodeAffinityMode", *v28, v31);
                    v29 = v32;
                    if ( v32 )
                    {
                      *((_DWORD *)v32 + 2) = 49;
                      CONFIG_ERROR_LIST::Add((APP_POOL_DATA_OBJECT_CS *)((char *)this + 1000), v29);
                    }
                    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v31 + 16LL))(v31);
                    v31 = 0;
                  }
                  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
                    PuDbgPrint(
                      g_pDebug,
                      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
                      2123,
                      "APP_POOL_DATA_OBJECT_CS::SetProcessorSettingsFromConfigStoreData",
                      " NumaNodeAffinityMode = %u (0x%X) \n ",
                      *v28,
                      *v28);
                }
                else if ( (g_dwDebugFlags & 0xF) != 0 )
                {
                  v9 = 2101;
                  goto LABEL_18;
                }
              }
              else if ( (g_dwDebugFlags & 0xF) != 0 )
              {
                v9 = 2069;
                goto LABEL_18;
              }
            }
            else if ( (g_dwDebugFlags & 0xF) != 0 )
            {
              v9 = 2037;
              goto LABEL_18;
            }
          }
          else if ( (g_dwDebugFlags & 0xF) != 0 )
          {
            v9 = 2005;
            goto LABEL_18;
          }
        }
        else if ( (g_dwDebugFlags & 0xF) != 0 )
        {
          v9 = 1981;
          goto LABEL_18;
        }
      }
      else if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        v9 = 1950;
        goto LABEL_18;
      }
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      v8 = " Failed reading CPU Reset Interval property \n";
      v9 = 1916;
      goto LABEL_4;
    }
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    v9 = 1882;
LABEL_18:
    v8 = " Failed reading property \n";
LABEL_4:
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_cs.cxx",
      v9,
      "APP_POOL_DATA_OBJECT_CS::SetProcessorSettingsFromConfigStoreData",
      v7,
      v8);
  }
LABEL_88:
  if ( v31 )
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v31 + 16LL))(v31);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180047e18  mov     [rsp-38h+arg_18], rbx
0x180047e1d  push    rbp
0x180047e1e  push    rsi
0x180047e1f  push    rdi
0x180047e20  push    r12
0x180047e22  push    r13
0x180047e24  push    r14
0x180047e26  push    r15
0x180047e28  mov     rbp, rsp
0x180047e2b  sub     rsp, 40h
0x180047e2f  mov     rax, [rdx]
0x180047e32  lea     r12, [rcx+248h]
0x180047e39  xor     r13d, r13d
0x180047e3c  lea     r9, [rbp+arg_0]
0x180047e40  mov     r15, rdx
0x180047e43  mov     [rbp+arg_10], r13
0x180047e47  mov     r14, rcx
0x180047e4a  mov     [rbp+arg_0], r13
0x180047e4e  mov     rax, [rax+30h]
0x180047e52  lea     rdx, aLimit; "limit"
0x180047e59  mov     r8, r12
0x180047e5c  mov     [rbp+arg_8], r13
0x180047e60  mov     rcx, r15
0x180047e63  mov     [rsp+40h+var_20], r13
0x180047e68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e6d  mov     ebx, eax
0x180047e6f  test    eax, eax
0x180047e71  jns     short loc_180047EB6
0x180047e73  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180047e7a  jz      loc_1800486E2
0x180047e80  lea     rax, aFailedReadingP_1; " Failed reading property \n"
0x180047e87  mov     r8d, 72Bh
0x180047e8d  lea     r9, aAppPoolDataObj_14; "APP_POOL_DATA_OBJECT_CS::SetProcessorSe"...
0x180047e94  lea     rdx, aServercommonIn_62; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180047e9b  mov     rcx, cs:g_pDebug
0x180047ea2  mov     [rsp+40h+var_18], rax
0x180047ea7  mov     dword ptr [rsp+40h+var_20], ebx
0x180047eab  call    cs:__imp_PuDbgPrintError
0x180047eb1  jmp     loc_1800486E2
0x180047eb6  mov     r9, [rbp+arg_0]; struct INativePropertyException *
0x180047eba  test    r9, r9
0x180047ebd  jz      short loc_180047F07
0x180047ebf  mov     r8d, [r12]; int
0x180047ec3  lea     rdx, aLimit; "limit"
0x180047eca  lea     rcx, [rbp+arg_8]; struct CONFIG_ERROR **
0x180047ece  call    ?CreateAndInitWithLong@CONFIG_ERROR@@SAXPEAPEAV1@PEBGJPEAVINativePropertyException@@@Z; CONFIG_ERROR::CreateAndInitWithLong(CONFIG_ERROR * *,ushort const *,long,INativePropertyException *)
0x180047ed3  mov     rdx, [rbp+arg_8]; struct CONFIG_ERROR *
0x180047ed7  test    rdx, rdx
0x180047eda  jz      short loc_180047EEF
0x180047edc  lea     rcx, [r14+3E8h]; this
0x180047ee3  mov     dword ptr [rdx+8], 20h ; ' '
0x180047eea  call    ?Add@CONFIG_ERROR_LIST@@QEAAXPEAVCONFIG_ERROR@@@Z; CONFIG_ERROR_LIST::Add(CONFIG_ERROR *)
0x180047eef  mov     rcx, [rbp+arg_0]
0x180047ef3  mov     [rbp+arg_8], r13
0x180047ef7  mov     rax, [rcx]
0x180047efa  mov     rax, [rax+10h]
0x180047efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047f03  mov     [rbp+arg_0], r13
0x180047f07  mov     r8d, cs:g_dwDebugFlags
0x180047f0e  lea     rdi, aAppPoolDataObj_14; "APP_POOL_DATA_OBJECT_CS::SetProcessorSe"...
0x180047f15  test    r8b, 3
0x180047f19  lea     rsi, aServercommonIn_62; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180047f20  setnz   cl
0x180047f23  bt      r8d, 1Eh
0x180047f28  setb    al
0x180047f2b  test    al, cl
0x180047f2d  jz      short loc_180047F6B
0x180047f2f  mov     eax, [r12]
0x180047f33  mov     r9, rdi
0x180047f36  mov     rcx, cs:g_pDebug
0x180047f3d  mov     r8d, 742h
0x180047f43  mov     [rsp+40h+var_8], eax
0x180047f47  mov     rdx, rsi
0x180047f4a  mov     [rsp+40h+var_10], eax
0x180047f4e  mov     dword ptr [rsp+40h+var_18], eax
0x180047f52  lea     rax, aCpuLimitBefore; " CPU Limit before conversion = %u (0x%X"...
0x180047f59  mov     [rsp+40h+var_20], rax
0x180047f5e  call    cs:__imp_PuDbgPrint
0x180047f64  mov     r8d, cs:g_dwDebugFlags
0x180047f6b  mov     edx, [r12]
0x180047f6f  cmp     edx, 64h ; 'd'
0x180047f72  jnz     short loc_180047F7B
0x180047f74  mov     [r12], r13d
0x180047f78  mov     edx, r13d
0x180047f7b  test    r8b, 3
0x180047f7f  setnz   cl
0x180047f82  bt      r8d, 1Eh
0x180047f87  setb    al
0x180047f8a  test    al, cl
0x180047f8c  jz      short loc_180047FBF
0x180047f8e  mov     rcx, cs:g_pDebug
0x180047f95  lea     rax, aCpuLimitAfterC; " CPU Limit after conversion = %u (0x%X)"...
0x180047f9c  mov     [rsp+40h+var_8], edx
0x180047fa0  mov     r9, rdi
0x180047fa3  mov     [rsp+40h+var_10], edx
0x180047fa7  mov     r8d, 750h
0x180047fad  mov     dword ptr [rsp+40h+var_18], edx
0x180047fb1  mov     rdx, rsi
0x180047fb4  mov     [rsp+40h+var_20], rax
0x180047fb9  call    cs:__imp_PuDbgPrint
0x180047fbf  mov     rax, [r15]
0x180047fc2  lea     r12, [r14+244h]
0x180047fc9  lea     r9, [rbp+arg_0]
0x180047fcd  mov     [rsp+40h+var_20], r13
0x180047fd2  mov     r8, r12
0x180047fd5  lea     rdx, aAction; "action"
0x180047fdc  mov     rcx, r15
0x180047fdf  mov     rax, [rax+30h]
0x180047fe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047fe8  mov     ebx, eax
0x180047fea  test    eax, eax
0x180047fec  jns     short loc_180048013
0x180047fee  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180047ff5  jz      loc_1800486E2
0x180047ffb  mov     r8d, 75Ah
0x180048001  lea     rax, aFailedReadingP_1; " Failed reading property \n"
0x180048008  mov     r9, rdi
0x18004800b  mov     rdx, rsi
0x18004800e  jmp     loc_180047E9B
0x180048013  mov     r9, [rbp+arg_0]; struct INativePropertyException *
0x180048017  test    r9, r9
0x18004801a  jz      short loc_180048064
0x18004801c  mov     r8d, [r12]; int
0x180048020  lea     rdx, aAction; "action"
0x180048027  lea     rcx, [rbp+arg_8]; struct CONFIG_ERROR **
0x18004802b  call    ?CreateAndInitWithLong@CONFIG_ERROR@@SAXPEAPEAV1@PEBGJPEAVINativePropertyException@@@Z; CONFIG_ERROR::CreateAndInitWithLong(CONFIG_ERROR * *,ushort const *,long,INativePropertyException *)
0x180048030  mov     rdx, [rbp+arg_8]; struct CONFIG_ERROR *
0x180048034  test    rdx, rdx
0x180048037  jz      short loc_18004804C
0x180048039  lea     rcx, [r14+3E8h]; this
0x180048040  mov     dword ptr [rdx+8], 1Fh
0x180048047  call    ?Add@CONFIG_ERROR_LIST@@QEAAXPEAVCONFIG_ERROR@@@Z; CONFIG_ERROR_LIST::Add(CONFIG_ERROR *)
0x18004804c  mov     rcx, [rbp+arg_0]
0x180048050  mov     [rbp+arg_8], r13
0x180048054  mov     rax, [rcx]
0x180048057  mov     rax, [rax+10h]
0x18004805b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048060  mov     [rbp+arg_0], r13
0x180048064  mov     eax, cs:g_dwDebugFlags
0x18004806a  test    al, 3
0x18004806c  setnz   cl
0x18004806f  bt      eax, 1Eh
0x180048073  setb    al
0x180048076  test    al, cl
0x180048078  jz      short loc_1800480AF
0x18004807a  mov     eax, [r12]
0x18004807e  mov     r9, rdi
0x180048081  mov     rcx, cs:g_pDebug
0x180048088  mov     r8d, 771h
0x18004808e  mov     [rsp+40h+var_8], eax
0x180048092  mov     rdx, rsi
0x180048095  mov     [rsp+40h+var_10], eax
0x180048099  mov     dword ptr [rsp+40h+var_18], eax
0x18004809d  lea     rax, aCpuActionU0xXD; " CPU Action = %u (0x%X) (%d) \n "
0x1800480a4  mov     [rsp+40h+var_20], rax
0x1800480a9  call    cs:__imp_PuDbgPrint
0x1800480af  mov     rax, [r15]
0x1800480b2  lea     r9, [rbp+arg_0]
0x1800480b6  lea     r8, [rbp+arg_10]
0x1800480ba  mov     [rsp+40h+var_20], r13
0x1800480bf  lea     rdx, aResetinterval; "resetInterval"
0x1800480c6  mov     rcx, r15
0x1800480c9  mov     rax, [rax+50h]
0x1800480cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800480d2  mov     ebx, eax
0x1800480d4  test    eax, eax
0x1800480d6  jns     short loc_1800480F7
0x1800480d8  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800480df  jz      loc_1800486E2
0x1800480e5  lea     rax, aFailedReadingC; " Failed reading CPU Reset Interval prop"...
0x1800480ec  mov     r8d, 77Ch
0x1800480f2  jmp     loc_180048008
0x1800480f7  mov     r8, [rbp+arg_10]; __int64
0x1800480fb  mov     rax, 0D6BF94D5E57A42BDh
0x180048105  mov     r9, [rbp+arg_0]; struct INativePropertyException *
0x180048109  imul    r8
0x18004810c  lea     rcx, [r8+rdx]
0x180048110  sar     rcx, 17h
0x180048114  mov     rax, rcx
0x180048117  shr     rax, 3Fh
0x18004811b  add     rcx, rax
0x18004811e  mov     rax, 8888888888888889h
0x180048128  imul    rcx
0x18004812b  add     rdx, rcx
0x18004812e  sar     rdx, 5
0x180048132  mov     rax, rdx
0x180048135  shr     rax, 3Fh
0x180048139  add     rdx, rax
0x18004813c  mov     [r14+24Ch], edx
0x180048143  test    r9, r9
0x180048146  jz      short loc_18004818C
0x180048148  lea     rdx, aResetinterval; "resetInterval"
0x18004814f  lea     rcx, [rbp+arg_8]; struct CONFIG_ERROR **
0x180048153  call    ?CreateAndInitWithRawTimeSpan@CONFIG_ERROR@@SAXPEAPEAV1@PEBG_JPEAVINativePropertyException@@@Z; CONFIG_ERROR::CreateAndInitWithRawTimeSpan(CONFIG_ERROR * *,ushort const *,__int64,INativePropertyException *)
0x180048158  mov     rdx, [rbp+arg_8]; struct CONFIG_ERROR *
0x18004815c  test    rdx, rdx
0x18004815f  jz      short loc_180048174
0x180048161  lea     rcx, [r14+3E8h]; this
0x180048168  mov     dword ptr [rdx+8], 21h ; '!'
0x18004816f  call    ?Add@CONFIG_ERROR_LIST@@QEAAXPEAVCONFIG_ERROR@@@Z; CONFIG_ERROR_LIST::Add(CONFIG_ERROR *)
0x180048174  mov     rcx, [rbp+arg_0]
0x180048178  mov     [rbp+arg_8], r13
0x18004817c  mov     rax, [rcx]
0x18004817f  mov     rax, [rax+10h]
0x180048183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048188  mov     [rbp+arg_0], r13
0x18004818c  mov     eax, cs:g_dwDebugFlags
0x180048192  test    al, 3
0x180048194  setnz   cl
0x180048197  bt      eax, 1Eh
0x18004819b  setb    al
0x18004819e  test    al, cl
0x1800481a0  jz      short loc_1800481DA
0x1800481a2  mov     eax, [r14+24Ch]
0x1800481a9  mov     r9, rdi
0x1800481ac  mov     rcx, cs:g_pDebug
0x1800481b3  mov     r8d, 794h
0x1800481b9  mov     [rsp+40h+var_8], eax
0x1800481bd  mov     rdx, rsi
0x1800481c0  mov     [rsp+40h+var_10], eax
0x1800481c4  mov     dword ptr [rsp+40h+var_18], eax
0x1800481c8  lea     rax, aCpuResetInterv; " CPU Reset Interval = %u (0x%X) (%d) \n"...
0x1800481cf  mov     [rsp+40h+var_20], rax
0x1800481d4  call    cs:__imp_PuDbgPrint
0x1800481da  mov     rax, [r15]
0x1800481dd  lea     r12, [r14+0C4h]
0x1800481e4  lea     r9, [rbp+arg_0]
0x1800481e8  mov     [rsp+40h+var_20], r13
0x1800481ed  mov     r8, r12
0x1800481f0  lea     rdx, aSmpaffinitized_0; "smpAffinitized"
0x1800481f7  mov     rcx, r15
0x1800481fa  mov     rax, [rax+48h]
0x1800481fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048203  mov     ebx, eax
0x180048205  test    eax, eax
0x180048207  jns     short loc_180048221
0x180048209  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180048210  jz      loc_1800486E2
0x180048216  mov     r8d, 79Eh
0x18004821c  jmp     loc_180048001
0x180048221  mov     r9, [rbp+arg_0]; struct INativePropertyException *
0x180048225  test    r9, r9
0x180048228  jz      short loc_180048272
0x18004822a  mov     r8d, [r12]; int
0x18004822e  lea     rdx, aSmpaffinitized_0; "smpAffinitized"
0x180048235  lea     rcx, [rbp+arg_8]; struct CONFIG_ERROR **
0x180048239  call    ?CreateAndInitWithBool@CONFIG_ERROR@@SAXPEAPEAV1@PEBGHPEAVINativePropertyException@@@Z; CONFIG_ERROR::CreateAndInitWithBool(CONFIG_ERROR * *,ushort const *,int,INativePropertyException *)
0x18004823e  mov     rdx, [rbp+arg_8]; struct CONFIG_ERROR *
0x180048242  test    rdx, rdx
0x180048245  jz      short loc_18004825A
0x180048247  lea     rcx, [r14+3E8h]; this
0x18004824e  mov     dword ptr [rdx+8], 0Bh
0x180048255  call    ?Add@CONFIG_ERROR_LIST@@QEAAXPEAVCONFIG_ERROR@@@Z; CONFIG_ERROR_LIST::Add(CONFIG_ERROR *)
0x18004825a  mov     rcx, [rbp+arg_0]
0x18004825e  mov     [rbp+arg_8], r13
0x180048262  mov     rax, [rcx]
0x180048265  mov     rax, [rax+10h]
0x180048269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004826e  mov     [rbp+arg_0], r13
0x180048272  mov     eax, cs:g_dwDebugFlags
0x180048278  test    al, 3
0x18004827a  setnz   cl
0x18004827d  bt      eax, 1Eh
0x180048281  setb    al
0x180048284  test    al, cl
0x180048286  jz      short loc_1800482C8
0x180048288  cmp     [r12], r13d
0x18004828c  lea     rcx, aFalse_1; "FALSE"
0x180048293  lea     rax, aTrue_1; "TRUE"
0x18004829a  mov     r9, rdi
0x18004829d  cmovz   rax, rcx
0x1800482a1  mov     r8d, 7B3h
0x1800482a7  mov     rcx, cs:g_pDebug
0x1800482ae  mov     rdx, rsi
0x1800482b1  mov     [rsp+40h+var_18], rax
0x1800482b6  lea     rax, aSmpaffinitized; " SMPAffinitized = %S \n"
0x1800482bd  mov     [rsp+40h+var_20], rax
0x1800482c2  call    cs:__imp_PuDbgPrint
0x1800482c8  mov     rax, [r15]
0x1800482cb  lea     r12, [r14+0C8h]
0x1800482d2  lea     r9, [rbp+arg_0]
0x1800482d6  mov     [rsp+40h+var_20], r13
0x1800482db  mov     r8, r12
0x1800482de  lea     rdx, aSmpprocessoraf_0; "smpProcessorAffinityMask"
0x1800482e5  mov     rcx, r15
0x1800482e8  mov     rax, [rax+30h]
0x1800482ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482f1  mov     ebx, eax
0x1800482f3  test    eax, eax
0x1800482f5  jns     short loc_18004830F
0x1800482f7  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800482fe  jz      loc_1800486E2
0x180048304  mov     r8d, 7BDh
0x18004830a  jmp     loc_180048001
0x18004830f  mov     r9, [rbp+arg_0]; struct INativePropertyException *
0x180048313  test    r9, r9
0x180048316  jz      short loc_180048360
0x180048318  mov     r8d, [r12]; int
0x18004831c  lea     rdx, aSmpprocessoraf_0; "smpProcessorAffinityMask"
0x180048323  lea     rcx, [rbp+arg_8]; struct CONFIG_ERROR **
  ... truncated ...
```
