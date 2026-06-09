# SITE_DATA_OBJECT_CS::SetLimitSettingsFromConfigStoreData(INativeConfigurationElement *)

- ea: `0x18004d108`
- end: `0x18004d3cc`
- name: `?SetLimitSettingsFromConfigStoreData@SITE_DATA_OBJECT_CS@@QEAAJPEAVINativeConfigurationElement@@@Z`
- size: `708`
- prototype: `__int64 __fastcall(SITE_DATA_OBJECT_CS *__hidden this, struct INativeConfigurationElement *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004c3e0`

## callees

- `0x18004d108`
- `0x180052f8c`
- `0x180053908`
- `0x180062010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18004d248`
- `iisutil!PuDbgPrint` at `0x18004d309`
- `iisutil!PuDbgPrint` at `0x18004d3a2`
- `iisutil!PuDbgPrint` at `0x18004d248`
- `iisutil!PuDbgPrint` at `0x18004d309`
- `iisutil!PuDbgPrint` at `0x18004d3a2`
- `iisutil!PuDbgPrintError` at `0x18004d1a1`
- `iisutil!PuDbgPrintError` at `0x18004d1a1`

## string_xrefs

- `0x18004d17c`: ` Failed reading property \n`
- `0x18004d196`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\sitestore_cs.cxx`
- `0x18004d223`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\sitestore_cs.cxx`
- `0x18004d2fd`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\sitestore_cs.cxx`
- `0x18004d37d`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\sitestore_cs.cxx`
- `0x18004d18a`: `SITE_DATA_OBJECT_CS::SetLimitSettingsFromConfigStoreData`
- `0x18004d215`: `SITE_DATA_OBJECT_CS::SetLimitSettingsFromConfigStoreData`
- `0x18004d2e8`: `SITE_DATA_OBJECT_CS::SetLimitSettingsFromConfigStoreData`
- `0x18004d36f`: `SITE_DATA_OBJECT_CS::SetLimitSettingsFromConfigStoreData`
- `0x18004d287`: ` Failed reading connection timeout property \n`

## pseudocode

```c
__int64 __fastcall SITE_DATA_OBJECT_CS::SetLimitSettingsFromConfigStoreData(
        SITE_DATA_OBJECT_CS *this,
        struct INativeConfigurationElement *a2)
{
  __int64 v2; // rax
  unsigned int *v3; // r15
  int v6; // ebx
  __int64 v7; // r8
  struct CONFIG_ERROR *v8; // rdx
  __int64 v9; // rdx
  int v10; // eax
  bool v11; // zf
  struct INativePropertyException *v13; // [rsp+70h] [rbp+30h] BYREF
  __int64 v14; // [rsp+78h] [rbp+38h] BYREF
  struct CONFIG_ERROR *v15; // [rsp+80h] [rbp+40h] BYREF

  v2 = *(_QWORD *)a2;
  v3 = (unsigned int *)((char *)this + 288);
  v14 = 0;
  v13 = 0;
  v15 = 0;
  v6 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(v2 + 48))(
         a2,
         L"maxBandwidth",
         (char *)this + 288,
         &v13,
         0);
  if ( v6 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_22;
    v7 = 801;
LABEL_4:
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_cs.cxx",
      v7,
      "SITE_DATA_OBJECT_CS::SetLimitSettingsFromConfigStoreData",
      v6,
      " Failed reading property \n");
    goto LABEL_22;
  }
  if ( v13 )
  {
    CONFIG_ERROR::CreateAndInitWithLong(&v15, L"maxBandwidth", *v3, v13);
    v8 = v15;
    if ( v15 )
    {
      *((_DWORD *)v15 + 2) = 80;
      CONFIG_ERROR_LIST::Add((SITE_DATA_OBJECT_CS *)((char *)this + 304), v8);
    }
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v13 + 16LL))(v13);
    v13 = 0;
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_cs.cxx",
      824,
      "SITE_DATA_OBJECT_CS::SetLimitSettingsFromConfigStoreData",
      " Max Bandwidth = %u (0x%X) (%d) \n ",
      *v3,
      *v3,
      *v3);
  v6 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, __int64 *, _QWORD, _QWORD))(*(_QWORD *)a2 + 80LL))(
         a2,
         L"connectionTimeout",
         &v14,
         0,
         0);
  if ( v6 >= 0 )
  {
    v9 = v14 / 10000000;
    v10 = g_dwDebugFlags;
    v11 = (g_dwDebugFlags & 3) == 0;
    *((_DWORD *)this + 74) = v14 / 10000000;
    if ( !v11 && (v10 & 0x40000000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_cs.cxx",
        845,
        "SITE_DATA_OBJECT_CS::SetLimitSettingsFromConfigStoreData",
        " Connection Timeout (as seconds) = %u (0x%X) (%d) \n ",
        v9,
        v9,
        v9);
    v6 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)a2 + 48LL))(
           a2,
           L"maxConnections",
           (char *)this + 292,
           0,
           0);
    if ( v6 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_22;
      v7 = 855;
      goto LABEL_4;
    }
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_cs.cxx",
        866,
        "SITE_DATA_OBJECT_CS::SetLimitSettingsFromConfigStoreData",
        " Max Connections = %u (0x%X) (%d) \n ",
        *((_DWORD *)this + 73),
        *((_DWORD *)this + 73),
        *((_DWORD *)this + 73));
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_cs.cxx",
      834,
      "SITE_DATA_OBJECT_CS::SetLimitSettingsFromConfigStoreData",
      v6,
      " Failed reading connection timeout property \n");
  }
LABEL_22:
  if ( v13 )
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v13 + 16LL))(v13);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18004d108  push    rbp
0x18004d10a  push    rbx
0x18004d10b  push    r13
0x18004d10d  push    r14
0x18004d10f  push    r15
0x18004d111  mov     rbp, rsp
0x18004d114  sub     rsp, 40h
0x18004d118  mov     rax, [rdx]
0x18004d11b  lea     r15, [rcx+120h]
0x18004d122  mov     r14, rdx
0x18004d125  mov     [rbp+arg_8], 0
0x18004d12d  mov     r13, rcx
0x18004d130  mov     [rbp+arg_0], 0
0x18004d138  lea     r9, [rbp+arg_0]
0x18004d13c  mov     [rbp+arg_10], 0
0x18004d144  mov     rax, [rax+30h]
0x18004d148  lea     rdx, aMaxbandwidth_0; "maxBandwidth"
0x18004d14f  mov     r8, r15
0x18004d152  mov     [rsp+40h+var_20], 0
0x18004d15b  mov     rcx, r14
0x18004d15e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d163  mov     ebx, eax
0x18004d165  test    eax, eax
0x18004d167  jns     short loc_18004D1AC
0x18004d169  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004d170  jz      loc_18004D3A8
0x18004d176  mov     r8d, 321h
0x18004d17c  lea     rax, aFailedReadingP_1; " Failed reading property \n"
0x18004d183  mov     rcx, cs:g_pDebug
0x18004d18a  lea     r9, aSiteDataObject_1; "SITE_DATA_OBJECT_CS::SetLimitSettingsFr"...
0x18004d191  mov     [rsp+40h+var_18], rax
0x18004d196  lea     rdx, aServercommonIn_40; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18004d19d  mov     dword ptr [rsp+40h+var_20], ebx
0x18004d1a1  call    cs:__imp_PuDbgPrintError
0x18004d1a7  jmp     loc_18004D3A8
0x18004d1ac  mov     r9, [rbp+arg_0]; struct INativePropertyException *
0x18004d1b0  test    r9, r9
0x18004d1b3  jz      short loc_18004D1FC
0x18004d1b5  mov     r8d, [r15]; int
0x18004d1b8  lea     rdx, aMaxbandwidth_0; "maxBandwidth"
0x18004d1bf  lea     rcx, [rbp+arg_10]; struct CONFIG_ERROR **
0x18004d1c3  call    ?CreateAndInitWithLong@CONFIG_ERROR@@SAXPEAPEAV1@PEBGJPEAVINativePropertyException@@@Z; CONFIG_ERROR::CreateAndInitWithLong(CONFIG_ERROR * *,ushort const *,long,INativePropertyException *)
0x18004d1c8  mov     rdx, [rbp+arg_10]; struct CONFIG_ERROR *
0x18004d1cc  test    rdx, rdx
0x18004d1cf  jz      short loc_18004D1E4
0x18004d1d1  lea     rcx, [r13+130h]; this
0x18004d1d8  mov     dword ptr [rdx+8], 50h ; 'P'
0x18004d1df  call    ?Add@CONFIG_ERROR_LIST@@QEAAXPEAVCONFIG_ERROR@@@Z; CONFIG_ERROR_LIST::Add(CONFIG_ERROR *)
0x18004d1e4  mov     rcx, [rbp+arg_0]
0x18004d1e8  mov     rax, [rcx]
0x18004d1eb  mov     rax, [rax+10h]
0x18004d1ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d1f4  mov     [rbp+arg_0], 0
0x18004d1fc  mov     eax, cs:g_dwDebugFlags
0x18004d202  test    al, 3
0x18004d204  setnz   cl
0x18004d207  bt      eax, 1Eh
0x18004d20b  setb    al
0x18004d20e  test    al, cl
0x18004d210  jz      short loc_18004D24E
0x18004d212  mov     eax, [r15]
0x18004d215  lea     r9, aSiteDataObject_1; "SITE_DATA_OBJECT_CS::SetLimitSettingsFr"...
0x18004d21c  mov     rcx, cs:g_pDebug
0x18004d223  lea     rdx, aServercommonIn_40; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18004d22a  mov     [rsp+40h+var_8], eax
0x18004d22e  mov     r8d, 338h
0x18004d234  mov     [rsp+40h+var_10], eax
0x18004d238  mov     dword ptr [rsp+40h+var_18], eax
0x18004d23c  lea     rax, aMaxBandwidthU0; " Max Bandwidth = %u (0x%X) (%d) \n "
0x18004d243  mov     [rsp+40h+var_20], rax
0x18004d248  call    cs:__imp_PuDbgPrint
0x18004d24e  mov     rax, [r14]
0x18004d251  lea     r8, [rbp+arg_8]
0x18004d255  xor     r9d, r9d
0x18004d258  mov     [rsp+40h+var_20], 0
0x18004d261  lea     rdx, aConnectiontime_0; "connectionTimeout"
0x18004d268  mov     rcx, r14
0x18004d26b  mov     rax, [rax+50h]
0x18004d26f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d274  mov     ebx, eax
0x18004d276  test    eax, eax
0x18004d278  jns     short loc_18004D299
0x18004d27a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004d281  jz      loc_18004D3A8
0x18004d287  lea     rax, aFailedReadingC_3; " Failed reading connection timeout prop"...
0x18004d28e  mov     r8d, 342h
0x18004d294  jmp     loc_18004D183
0x18004d299  mov     rax, 0D6BF94D5E57A42BDh
0x18004d2a3  imul    [rbp+arg_8]
0x18004d2a7  add     rdx, [rbp+arg_8]
0x18004d2ab  sar     rdx, 17h
0x18004d2af  mov     rax, rdx
0x18004d2b2  shr     rax, 3Fh
0x18004d2b6  add     rdx, rax
0x18004d2b9  mov     eax, cs:g_dwDebugFlags
0x18004d2bf  test    al, 3
0x18004d2c1  mov     [r13+128h], edx
0x18004d2c8  setnz   cl
0x18004d2cb  bt      eax, 1Eh
0x18004d2cf  setb    al
0x18004d2d2  test    al, cl
0x18004d2d4  jz      short loc_18004D30F
0x18004d2d6  mov     rcx, cs:g_pDebug
0x18004d2dd  lea     rax, aConnectionTime; " Connection Timeout (as seconds) = %u ("...
0x18004d2e4  mov     [rsp+40h+var_8], edx
0x18004d2e8  lea     r9, aSiteDataObject_1; "SITE_DATA_OBJECT_CS::SetLimitSettingsFr"...
0x18004d2ef  mov     [rsp+40h+var_10], edx
0x18004d2f3  mov     r8d, 34Dh
0x18004d2f9  mov     dword ptr [rsp+40h+var_18], edx
0x18004d2fd  lea     rdx, aServercommonIn_40; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18004d304  mov     [rsp+40h+var_20], rax
0x18004d309  call    cs:__imp_PuDbgPrint
0x18004d30f  mov     rax, [r14]
0x18004d312  lea     r8, [r13+124h]
0x18004d319  xor     r9d, r9d
0x18004d31c  mov     [rsp+40h+var_20], 0
0x18004d325  lea     rdx, aMaxconnections; "maxConnections"
0x18004d32c  mov     rcx, r14
0x18004d32f  mov     rax, [rax+30h]
0x18004d333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d338  mov     ebx, eax
0x18004d33a  test    eax, eax
0x18004d33c  jns     short loc_18004D352
0x18004d33e  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004d345  jz      short loc_18004D3A8
0x18004d347  mov     r8d, 357h
0x18004d34d  jmp     loc_18004D17C
0x18004d352  mov     eax, cs:g_dwDebugFlags
0x18004d358  test    al, 3
0x18004d35a  setnz   cl
0x18004d35d  bt      eax, 1Eh
0x18004d361  setb    al
0x18004d364  test    al, cl
0x18004d366  jz      short loc_18004D3A8
0x18004d368  mov     eax, [r13+124h]
0x18004d36f  lea     r9, aSiteDataObject_1; "SITE_DATA_OBJECT_CS::SetLimitSettingsFr"...
0x18004d376  mov     rcx, cs:g_pDebug
0x18004d37d  lea     rdx, aServercommonIn_40; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18004d384  mov     [rsp+40h+var_8], eax
0x18004d388  mov     r8d, 362h
0x18004d38e  mov     [rsp+40h+var_10], eax
0x18004d392  mov     dword ptr [rsp+40h+var_18], eax
0x18004d396  lea     rax, aMaxConnections; " Max Connections = %u (0x%X) (%d) \n "
0x18004d39d  mov     [rsp+40h+var_20], rax
0x18004d3a2  call    cs:__imp_PuDbgPrint
0x18004d3a8  mov     rcx, [rbp+arg_0]
0x18004d3ac  test    rcx, rcx
0x18004d3af  jz      short loc_18004D3BD
0x18004d3b1  mov     rax, [rcx]
0x18004d3b4  mov     rax, [rax+10h]
0x18004d3b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d3bd  mov     eax, ebx
0x18004d3bf  add     rsp, 40h
0x18004d3c3  pop     r15
0x18004d3c5  pop     r14
0x18004d3c7  pop     r13
0x18004d3c9  pop     rbx
0x18004d3ca  pop     rbp
0x18004d3cb  retn
```
