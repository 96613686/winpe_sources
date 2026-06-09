# APP_POOL_DATA_OBJECT_APPHOST::SetProcessorSettingsFromConfigStoreData(ICpu *)

- ea: `0x18004b880`
- end: `0x18004bdfa`
- name: `?SetProcessorSettingsFromConfigStoreData@APP_POOL_DATA_OBJECT_APPHOST@@QEAAJPEAUICpu@@@Z`
- size: `1402`
- prototype: `__int64 __fastcall(APP_POOL_DATA_OBJECT_APPHOST *__hidden this, struct ICpu *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180048f34`

## callees

- `0x18004b880`
- `0x180062010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18004b964`
- `iisutil!PuDbgPrint` at `0x18004b9c0`
- `iisutil!PuDbgPrint` at `0x18004ba4e`
- `iisutil!PuDbgPrint` at `0x18004bb17`
- `iisutil!PuDbgPrint` at `0x18004bbae`
- `iisutil!PuDbgPrint` at `0x18004bc66`
- `iisutil!PuDbgPrint` at `0x18004bce3`
- `iisutil!PuDbgPrint` at `0x18004bd60`
- `iisutil!PuDbgPrint` at `0x18004bdd9`
- `iisutil!PuDbgPrint` at `0x18004b964`
- `iisutil!PuDbgPrint` at `0x18004b9c0`
- `iisutil!PuDbgPrint` at `0x18004ba4e`
- `iisutil!PuDbgPrint` at `0x18004bb17`
- `iisutil!PuDbgPrint` at `0x18004bbae`
- `iisutil!PuDbgPrint` at `0x18004bc66`
- `iisutil!PuDbgPrint` at `0x18004bce3`
- `iisutil!PuDbgPrint` at `0x18004bd60`
- `iisutil!PuDbgPrint` at `0x18004bdd9`
- `iisutil!PuDbgPrintError` at `0x18004b903`
- `iisutil!PuDbgPrintError` at `0x18004b903`

## string_xrefs

- `0x18004b8d8`: ` Failed reading property \n`
- `0x18004b9f8`: ` Failed reading property \n`
- `0x18004ba7b`: ` Failed reading CPU Reset Interval property \n`
- `0x18004b8ec`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\apppoolstore_apphost.cxx`
- `0x18004b920`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\apppoolstore_apphost.cxx`
- `0x18004b8e5`: `APP_POOL_DATA_OBJECT_APPHOST::SetProcessorSettingsFromConfigStoreData`
- `0x18004b915`: `APP_POOL_DATA_OBJECT_APPHOST::SetProcessorSettingsFromConfigStoreData`

## pseudocode

```c
__int64 __fastcall APP_POOL_DATA_OBJECT_APPHOST::SetProcessorSettingsFromConfigStoreData(
        APP_POOL_DATA_OBJECT_APPHOST *this,
        struct ICpu *a2)
{
  int *v2; // r15
  int v5; // ebx
  const char *v6; // rax
  __int64 v7; // r8
  int v8; // r8d
  int v9; // edx
  __int64 v10; // rdx
  int v11; // eax
  bool v12; // zf
  int v13; // eax
  BOOL v14; // edx
  const wchar_t *v15; // rax
  __int16 v17; // [rsp+70h] [rbp+8h] BYREF
  __int64 v18; // [rsp+78h] [rbp+10h] BYREF

  v18 = 0;
  v17 = 0;
  v2 = (int *)((char *)this + 584);
  v5 = (*(__int64 (__fastcall **)(struct ICpu *, char *))(*(_QWORD *)a2 + 56LL))(a2, (char *)this + 584);
  if ( v5 >= 0 )
  {
    v8 = g_dwDebugFlags;
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
    {
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
        1224,
        "APP_POOL_DATA_OBJECT_APPHOST::SetProcessorSettingsFromConfigStoreData",
        " CPU Limit before conversion = %u (0x%X) (%d) \n ",
        *v2,
        *v2,
        *v2);
      v8 = g_dwDebugFlags;
    }
    v9 = *v2;
    if ( *v2 == 100 )
    {
      *v2 = 0;
      v9 = 0;
    }
    if ( (v8 & 3) != 0 && (v8 & 0x40000000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
        1238,
        "APP_POOL_DATA_OBJECT_APPHOST::SetProcessorSettingsFromConfigStoreData",
        " CPU Limit after conversion = %u (0x%X) (%d) \n ",
        v9,
        v9,
        v9);
    v5 = (*(__int64 (__fastcall **)(struct ICpu *, char *))(*(_QWORD *)a2 + 64LL))(a2, (char *)this + 580);
    if ( v5 >= 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
          1256,
          "APP_POOL_DATA_OBJECT_APPHOST::SetProcessorSettingsFromConfigStoreData",
          " CPU Action = %u (0x%X) (%d) \n ",
          *((_DWORD *)this + 145),
          *((_DWORD *)this + 145),
          *((_DWORD *)this + 145));
      v5 = (*(__int64 (__fastcall **)(struct ICpu *, __int64 *))(*(_QWORD *)a2 + 72LL))(a2, &v18);
      if ( v5 < 0 )
      {
        if ( (g_dwDebugFlags & 0xF) == 0 )
          return (unsigned int)v5;
        v6 = " Failed reading CPU Reset Interval property \n";
        v7 = 1264;
        goto LABEL_4;
      }
      v10 = v18 / 10000000 / 60;
      v11 = g_dwDebugFlags;
      v12 = (g_dwDebugFlags & 3) == 0;
      *((_DWORD *)this + 147) = v10;
      if ( !v12 && (v11 & 0x40000000) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
          1275,
          "APP_POOL_DATA_OBJECT_APPHOST::SetProcessorSettingsFromConfigStoreData",
          " CPU Reset Interval = %u (0x%X) (%d) \n ",
          v10,
          v10,
          v10);
      v5 = (*(__int64 (__fastcall **)(struct ICpu *, __int16 *))(*(_QWORD *)a2 + 80LL))(a2, &v17);
      if ( v5 >= 0 )
      {
        v13 = g_dwDebugFlags;
        v14 = v17 == -1;
        v12 = (g_dwDebugFlags & 3) == 0;
        *((_DWORD *)this + 49) = v14;
        if ( !v12 && (v13 & 0x40000000) != 0 )
        {
          v15 = L"TRUE";
          if ( !v14 )
            v15 = L"FALSE";
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
            1292,
            "APP_POOL_DATA_OBJECT_APPHOST::SetProcessorSettingsFromConfigStoreData",
            " SMPAffinitized = %S \n",
            v15);
        }
        v5 = (*(__int64 (__fastcall **)(struct ICpu *, char *))(*(_QWORD *)a2 + 88LL))(a2, (char *)this + 200);
        if ( v5 >= 0 )
        {
          v5 = (*(__int64 (__fastcall **)(struct ICpu *, char *))(*(_QWORD *)a2 + 88LL))(a2, (char *)this + 204);
          if ( v5 >= 0 )
          {
            if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
              PuDbgPrint(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
                1318,
                "APP_POOL_DATA_OBJECT_APPHOST::SetProcessorSettingsFromConfigStoreData",
                " Affinity Mask = 0x%X%X \n",
                *((_DWORD *)this + 51),
                *((_DWORD *)this + 50));
            v5 = (*(__int64 (__fastcall **)(struct ICpu *, char *))(*(_QWORD *)a2 + 104LL))(a2, (char *)this + 208);
            if ( v5 >= 0 )
            {
              if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
                PuDbgPrint(
                  g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
                  1335,
                  "APP_POOL_DATA_OBJECT_APPHOST::SetProcessorSettingsFromConfigStoreData",
                  " ProcessorGroup = %d (0x%X) \n ",
                  *((_DWORD *)this + 52),
                  *((_DWORD *)this + 52));
              v5 = (*(__int64 (__fastcall **)(struct ICpu *, char *))(*(_QWORD *)a2 + 112LL))(a2, (char *)this + 212);
              if ( v5 >= 0 )
              {
                if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
                  PuDbgPrint(
                    g_pDebug,
                    "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
                    1352,
                    "APP_POOL_DATA_OBJECT_APPHOST::SetProcessorSettingsFromConfigStoreData",
                    " NumaNodeAssignment = %u (0x%X) \n ",
                    *((_DWORD *)this + 53),
                    *((_DWORD *)this + 53));
                v5 = (*(__int64 (__fastcall **)(struct ICpu *, char *))(*(_QWORD *)a2 + 120LL))(a2, (char *)this + 216);
                if ( v5 >= 0 )
                {
                  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
                    PuDbgPrint(
                      g_pDebug,
                      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
                      1369,
                      "APP_POOL_DATA_OBJECT_APPHOST::SetProcessorSettingsFromConfigStoreData",
                      " NumaNodeAffinityMode = %u (0x%X) \n ",
                      *((_DWORD *)this + 54),
                      *((_DWORD *)this + 54));
                  return (unsigned int)v5;
                }
                if ( (g_dwDebugFlags & 0xF) == 0 )
                  return (unsigned int)v5;
                v7 = 1360;
              }
              else
              {
                if ( (g_dwDebugFlags & 0xF) == 0 )
                  return (unsigned int)v5;
                v7 = 1343;
              }
            }
            else
            {
              if ( (g_dwDebugFlags & 0xF) == 0 )
                return (unsigned int)v5;
              v7 = 1326;
            }
          }
          else
          {
            if ( (g_dwDebugFlags & 0xF) == 0 )
              return (unsigned int)v5;
            v7 = 1309;
          }
        }
        else
        {
          if ( (g_dwDebugFlags & 0xF) == 0 )
            return (unsigned int)v5;
          v7 = 1300;
        }
      }
      else
      {
        if ( (g_dwDebugFlags & 0xF) == 0 )
          return (unsigned int)v5;
        v7 = 1283;
      }
    }
    else
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
        return (unsigned int)v5;
      v7 = 1246;
    }
    v6 = " Failed reading property \n";
    goto LABEL_4;
  }
  if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    v6 = " Failed reading property \n";
    v7 = 1214;
LABEL_4:
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
      v7,
      "APP_POOL_DATA_OBJECT_APPHOST::SetProcessorSettingsFromConfigStoreData",
      v5,
      v6);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18004b880  mov     [rsp+arg_10], rbx
0x18004b885  mov     [rsp+arg_18], rbp
0x18004b88a  push    rsi
0x18004b88b  push    rdi
0x18004b88c  push    r12
0x18004b88e  push    r14
0x18004b890  push    r15
0x18004b892  sub     rsp, 40h
0x18004b896  xor     eax, eax
0x18004b898  mov     [rsp+68h+arg_8], 0
0x18004b8a1  mov     [rsp+68h+arg_0], ax
0x18004b8a6  lea     r15, [rcx+248h]
0x18004b8ad  mov     rax, [rdx]
0x18004b8b0  mov     r14, rdx
0x18004b8b3  mov     rbp, rcx
0x18004b8b6  mov     rdx, r15
0x18004b8b9  mov     rcx, r14
0x18004b8bc  mov     rax, [rax+38h]
0x18004b8c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b8c5  mov     ebx, eax
0x18004b8c7  test    eax, eax
0x18004b8c9  jns     short loc_18004B90E
0x18004b8cb  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004b8d2  jz      loc_18004BDDF
0x18004b8d8  lea     rax, aFailedReadingP_1; " Failed reading property \n"
0x18004b8df  mov     r8d, 4BEh
0x18004b8e5  lea     r9, aAppPoolDataObj_13; "APP_POOL_DATA_OBJECT_APPHOST::SetProces"...
0x18004b8ec  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18004b8f3  mov     rcx, cs:g_pDebug
0x18004b8fa  mov     [rsp+68h+var_40], rax
0x18004b8ff  mov     dword ptr [rsp+68h+var_48], ebx
0x18004b903  call    cs:__imp_PuDbgPrintError
0x18004b909  jmp     loc_18004BDDF
0x18004b90e  mov     r8d, cs:g_dwDebugFlags
0x18004b915  lea     rdi, aAppPoolDataObj_13; "APP_POOL_DATA_OBJECT_APPHOST::SetProces"...
0x18004b91c  test    r8b, 3
0x18004b920  lea     rsi, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18004b927  setnz   cl
0x18004b92a  bt      r8d, 1Eh
0x18004b92f  setb    al
0x18004b932  test    al, cl
0x18004b934  jz      short loc_18004B971
0x18004b936  mov     eax, [r15]
0x18004b939  mov     r9, rdi
0x18004b93c  mov     rcx, cs:g_pDebug
0x18004b943  mov     r8d, 4C8h
0x18004b949  mov     [rsp+68h+var_30], eax
0x18004b94d  mov     rdx, rsi
0x18004b950  mov     [rsp+68h+var_38], eax
0x18004b954  mov     dword ptr [rsp+68h+var_40], eax
0x18004b958  lea     rax, aCpuLimitBefore; " CPU Limit before conversion = %u (0x%X"...
0x18004b95f  mov     [rsp+68h+var_48], rax
0x18004b964  call    cs:__imp_PuDbgPrint
0x18004b96a  mov     r8d, cs:g_dwDebugFlags
0x18004b971  mov     edx, [r15]
0x18004b974  cmp     edx, 64h ; 'd'
0x18004b977  jnz     short loc_18004B982
0x18004b979  mov     dword ptr [r15], 0
0x18004b980  xor     edx, edx
0x18004b982  test    r8b, 3
0x18004b986  setnz   cl
0x18004b989  bt      r8d, 1Eh
0x18004b98e  setb    al
0x18004b991  test    al, cl
0x18004b993  jz      short loc_18004B9C6
0x18004b995  mov     rcx, cs:g_pDebug
0x18004b99c  lea     rax, aCpuLimitAfterC; " CPU Limit after conversion = %u (0x%X)"...
0x18004b9a3  mov     [rsp+68h+var_30], edx
0x18004b9a7  mov     r9, rdi
0x18004b9aa  mov     [rsp+68h+var_38], edx
0x18004b9ae  mov     r8d, 4D6h
0x18004b9b4  mov     dword ptr [rsp+68h+var_40], edx
0x18004b9b8  mov     rdx, rsi
0x18004b9bb  mov     [rsp+68h+var_48], rax
0x18004b9c0  call    cs:__imp_PuDbgPrint
0x18004b9c6  mov     rax, [r14]
0x18004b9c9  lea     r15, [rbp+244h]
0x18004b9d0  mov     rdx, r15
0x18004b9d3  mov     rcx, r14
0x18004b9d6  mov     rax, [rax+40h]
0x18004b9da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b9df  mov     ebx, eax
0x18004b9e1  test    eax, eax
0x18004b9e3  jns     short loc_18004BA0A
0x18004b9e5  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004b9ec  jz      loc_18004BDDF
0x18004b9f2  mov     r8d, 4DEh
0x18004b9f8  lea     rax, aFailedReadingP_1; " Failed reading property \n"
0x18004b9ff  mov     r9, rdi
0x18004ba02  mov     rdx, rsi
0x18004ba05  jmp     loc_18004B8F3
0x18004ba0a  mov     eax, cs:g_dwDebugFlags
0x18004ba10  test    al, 3
0x18004ba12  setnz   cl
0x18004ba15  bt      eax, 1Eh
0x18004ba19  setb    al
0x18004ba1c  test    al, cl
0x18004ba1e  jz      short loc_18004BA54
0x18004ba20  mov     eax, [r15]
0x18004ba23  mov     r9, rdi
0x18004ba26  mov     rcx, cs:g_pDebug
0x18004ba2d  mov     r8d, 4E8h
0x18004ba33  mov     [rsp+68h+var_30], eax
0x18004ba37  mov     rdx, rsi
0x18004ba3a  mov     [rsp+68h+var_38], eax
0x18004ba3e  mov     dword ptr [rsp+68h+var_40], eax
0x18004ba42  lea     rax, aCpuActionU0xXD; " CPU Action = %u (0x%X) (%d) \n "
0x18004ba49  mov     [rsp+68h+var_48], rax
0x18004ba4e  call    cs:__imp_PuDbgPrint
0x18004ba54  mov     rax, [r14]
0x18004ba57  lea     rdx, [rsp+68h+arg_8]
0x18004ba5c  mov     rcx, r14
0x18004ba5f  mov     rax, [rax+48h]
0x18004ba63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ba68  mov     ebx, eax
0x18004ba6a  test    eax, eax
0x18004ba6c  jns     short loc_18004BA8D
0x18004ba6e  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004ba75  jz      loc_18004BDDF
0x18004ba7b  lea     rax, aFailedReadingC; " Failed reading CPU Reset Interval prop"...
0x18004ba82  mov     r8d, 4F0h
0x18004ba88  jmp     loc_18004B9FF
0x18004ba8d  mov     rax, 0D6BF94D5E57A42BDh
0x18004ba97  imul    [rsp+68h+arg_8]
0x18004ba9c  mov     rcx, rdx
0x18004ba9f  add     rcx, [rsp+68h+arg_8]
0x18004baa4  sar     rcx, 17h
0x18004baa8  mov     rax, rcx
0x18004baab  shr     rax, 3Fh
0x18004baaf  add     rcx, rax
0x18004bab2  mov     rax, 8888888888888889h
0x18004babc  imul    rcx
0x18004babf  add     rdx, rcx
0x18004bac2  sar     rdx, 5
0x18004bac6  mov     rax, rdx
0x18004bac9  shr     rax, 3Fh
0x18004bacd  add     rdx, rax
0x18004bad0  mov     eax, cs:g_dwDebugFlags
0x18004bad6  test    al, 3
0x18004bad8  mov     [rbp+24Ch], edx
0x18004bade  setnz   cl
0x18004bae1  bt      eax, 1Eh
0x18004bae5  setb    al
0x18004bae8  test    al, cl
0x18004baea  jz      short loc_18004BB1D
0x18004baec  mov     rcx, cs:g_pDebug
0x18004baf3  lea     rax, aCpuResetInterv; " CPU Reset Interval = %u (0x%X) (%d) \n"...
0x18004bafa  mov     [rsp+68h+var_30], edx
0x18004bafe  mov     r9, rdi
0x18004bb01  mov     [rsp+68h+var_38], edx
0x18004bb05  mov     r8d, 4FBh
0x18004bb0b  mov     dword ptr [rsp+68h+var_40], edx
0x18004bb0f  mov     rdx, rsi
0x18004bb12  mov     [rsp+68h+var_48], rax
0x18004bb17  call    cs:__imp_PuDbgPrint
0x18004bb1d  mov     rax, [r14]
0x18004bb20  lea     rdx, [rsp+68h+arg_0]
0x18004bb25  mov     rcx, r14
0x18004bb28  mov     rax, [rax+50h]
0x18004bb2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bb31  mov     ebx, eax
0x18004bb33  test    eax, eax
0x18004bb35  jns     short loc_18004BB4F
0x18004bb37  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004bb3e  jz      loc_18004BDDF
0x18004bb44  mov     r8d, 503h
0x18004bb4a  jmp     loc_18004B9F8
0x18004bb4f  mov     eax, cs:g_dwDebugFlags
0x18004bb55  xor     edx, edx
0x18004bb57  cmp     [rsp+68h+arg_0], 0FFFFh
0x18004bb5d  setz    dl
0x18004bb60  test    al, 3
0x18004bb62  mov     [rbp+0C4h], edx
0x18004bb68  setnz   cl
0x18004bb6b  bt      eax, 1Eh
0x18004bb6f  setb    al
0x18004bb72  test    al, cl
0x18004bb74  jz      short loc_18004BBB4
0x18004bb76  test    edx, edx
0x18004bb78  lea     rcx, aFalse_1; "FALSE"
0x18004bb7f  lea     rax, aTrue_1; "TRUE"
0x18004bb86  mov     r9, rdi
0x18004bb89  cmovz   rax, rcx
0x18004bb8d  mov     r8d, 50Ch
0x18004bb93  mov     rcx, cs:g_pDebug
0x18004bb9a  mov     rdx, rsi
0x18004bb9d  mov     [rsp+68h+var_40], rax
0x18004bba2  lea     rax, aSmpaffinitized; " SMPAffinitized = %S \n"
0x18004bba9  mov     [rsp+68h+var_48], rax
0x18004bbae  call    cs:__imp_PuDbgPrint
0x18004bbb4  mov     rax, [r14]
0x18004bbb7  lea     r15, [rbp+0C8h]
0x18004bbbe  mov     rdx, r15
0x18004bbc1  mov     rcx, r14
0x18004bbc4  mov     rax, [rax+58h]
0x18004bbc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bbcd  mov     ebx, eax
0x18004bbcf  test    eax, eax
0x18004bbd1  jns     short loc_18004BBEB
0x18004bbd3  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004bbda  jz      loc_18004BDDF
0x18004bbe0  mov     r8d, 514h
0x18004bbe6  jmp     loc_18004B9F8
0x18004bbeb  mov     rax, [r14]
0x18004bbee  lea     r12, [rbp+0CCh]
0x18004bbf5  mov     rdx, r12
0x18004bbf8  mov     rcx, r14
0x18004bbfb  mov     rax, [rax+58h]
0x18004bbff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bc04  mov     ebx, eax
0x18004bc06  test    eax, eax
0x18004bc08  jns     short loc_18004BC22
0x18004bc0a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004bc11  jz      loc_18004BDDF
0x18004bc17  mov     r8d, 51Dh
0x18004bc1d  jmp     loc_18004B9F8
0x18004bc22  mov     eax, cs:g_dwDebugFlags
0x18004bc28  test    al, 3
0x18004bc2a  setnz   cl
0x18004bc2d  bt      eax, 1Eh
0x18004bc31  setb    al
0x18004bc34  test    al, cl
0x18004bc36  jz      short loc_18004BC6C
0x18004bc38  mov     eax, [r15]
0x18004bc3b  mov     r9, rdi
0x18004bc3e  mov     rcx, cs:g_pDebug
0x18004bc45  mov     r8d, 526h
0x18004bc4b  mov     [rsp+68h+var_38], eax
0x18004bc4f  mov     rdx, rsi
0x18004bc52  mov     eax, [r12]
0x18004bc56  mov     dword ptr [rsp+68h+var_40], eax
0x18004bc5a  lea     rax, aAffinityMask0x; " Affinity Mask = 0x%X%X \n"
0x18004bc61  mov     [rsp+68h+var_48], rax
0x18004bc66  call    cs:__imp_PuDbgPrint
0x18004bc6c  mov     rax, [r14]
0x18004bc6f  lea     r15, [rbp+0D0h]
0x18004bc76  mov     rdx, r15
0x18004bc79  mov     rcx, r14
0x18004bc7c  mov     rax, [rax+68h]
0x18004bc80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bc85  mov     ebx, eax
0x18004bc87  test    eax, eax
0x18004bc89  jns     short loc_18004BCA3
0x18004bc8b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004bc92  jz      loc_18004BDDF
0x18004bc98  mov     r8d, 52Eh
0x18004bc9e  jmp     loc_18004B9F8
0x18004bca3  mov     eax, cs:g_dwDebugFlags
0x18004bca9  test    al, 3
0x18004bcab  setnz   cl
0x18004bcae  bt      eax, 1Eh
0x18004bcb2  setb    al
0x18004bcb5  test    al, cl
0x18004bcb7  jz      short loc_18004BCE9
0x18004bcb9  mov     eax, [r15]
0x18004bcbc  mov     r9, rdi
0x18004bcbf  mov     rcx, cs:g_pDebug
0x18004bcc6  mov     r8d, 537h
0x18004bccc  mov     [rsp+68h+var_38], eax
0x18004bcd0  mov     rdx, rsi
0x18004bcd3  mov     dword ptr [rsp+68h+var_40], eax
0x18004bcd7  lea     rax, aProcessorgroup; " ProcessorGroup = %d (0x%X) \n "
0x18004bcde  mov     [rsp+68h+var_48], rax
0x18004bce3  call    cs:__imp_PuDbgPrint
0x18004bce9  mov     rax, [r14]
0x18004bcec  lea     r15, [rbp+0D4h]
0x18004bcf3  mov     rdx, r15
0x18004bcf6  mov     rcx, r14
0x18004bcf9  mov     rax, [rax+70h]
0x18004bcfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bd02  mov     ebx, eax
0x18004bd04  test    eax, eax
0x18004bd06  jns     short loc_18004BD20
0x18004bd08  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004bd0f  jz      loc_18004BDDF
0x18004bd15  mov     r8d, 53Fh
0x18004bd1b  jmp     loc_18004B9F8
0x18004bd20  mov     eax, cs:g_dwDebugFlags
0x18004bd26  test    al, 3
0x18004bd28  setnz   cl
0x18004bd2b  bt      eax, 1Eh
0x18004bd2f  setb    al
0x18004bd32  test    al, cl
0x18004bd34  jz      short loc_18004BD66
0x18004bd36  mov     eax, [r15]
0x18004bd39  mov     r9, rdi
0x18004bd3c  mov     rcx, cs:g_pDebug
0x18004bd43  mov     r8d, 548h
0x18004bd49  mov     [rsp+68h+var_38], eax
0x18004bd4d  mov     rdx, rsi
0x18004bd50  mov     dword ptr [rsp+68h+var_40], eax
0x18004bd54  lea     rax, aNumanodeassign; " NumaNodeAssignment = %u (0x%X) \n "
0x18004bd5b  mov     [rsp+68h+var_48], rax
0x18004bd60  call    cs:__imp_PuDbgPrint
0x18004bd66  mov     rax, [r14]
0x18004bd69  lea     rdx, [rbp+0D8h]
0x18004bd70  mov     rcx, r14
0x18004bd73  mov     rax, [rax+78h]
0x18004bd77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bd7c  mov     ebx, eax
  ... truncated ...
```
