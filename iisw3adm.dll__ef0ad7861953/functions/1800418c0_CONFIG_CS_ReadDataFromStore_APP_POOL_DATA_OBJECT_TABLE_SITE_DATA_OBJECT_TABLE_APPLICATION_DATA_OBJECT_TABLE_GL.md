# CONFIG_CS::ReadDataFromStore(APP_POOL_DATA_OBJECT_TABLE * *,SITE_DATA_OBJECT_TABLE * *,APPLICATION_DATA_OBJECT_TABLE * *,GLOBAL_DATA_STORE * *,PROTOCOL_DATA_OBJECT_TABLE * *,PROTOCOL_BINDING_TABLE * *)

- ea: `0x1800418c0`
- end: `0x180041cec`
- name: `?ReadDataFromStore@CONFIG_CS@@UEAAJPEAPEAVAPP_POOL_DATA_OBJECT_TABLE@@PEAPEAVSITE_DATA_OBJECT_TABLE@@PEAPEAVAPPLICATION_DATA_OBJECT_TABLE@@PEAPEAVGLOBAL_DATA_STORE@@PEAPEAVPROTOCOL_DATA_OBJECT_TABLE@@PEAPEAVPROTOCOL_BINDING_TABLE@@@Z`
- size: `1068`
- prototype: `__int64 __fastcall(CONFIG_CS *__hidden this, struct APP_POOL_DATA_OBJECT_TABLE **, struct SITE_DATA_OBJECT_TABLE **, struct APPLICATION_DATA_OBJECT_TABLE **, struct GLOBAL_DATA_STORE **, struct PROTOCOL_DATA_OBJECT_TABLE **, struct PROTOCOL_BINDING_TABLE **)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180040f9c`
- `0x1800412b0`
- `0x1800418c0`
- `0x180042730`
- `0x180044950`
- `0x18004c3e0`
- `0x180051f08`
- `0x180056fec`
- `0x18005740c`
- `0x180061060`
- `0x180061120`
- `0x180062010`

## import_xrefs

- `iisutil!PuDbgPrintError` at `0x1800419d4`
- `iisutil!PuDbgPrintError` at `0x180041a62`
- `iisutil!PuDbgPrintError` at `0x180041ac3`
- `iisutil!PuDbgPrintError` at `0x1800419d4`
- `iisutil!PuDbgPrintError` at `0x180041a62`
- `iisutil!PuDbgPrintError` at `0x180041ac3`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180041953`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180041953`

## string_xrefs

- `0x1800419cd`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\config_cs.cxx`
- `0x180041a5b`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\config_cs.cxx`
- `0x180041ab8`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\config_cs.cxx`
- `0x1800419bc`: `CONFIG_CS::ReadDataFromStore`
- `0x180041a4a`: `CONFIG_CS::ReadDataFromStore`
- `0x180041aac`: `CONFIG_CS::ReadDataFromStore`
- `0x180041a3e`: `Failed getting a section from the config store\n`
- `0x180041aee`: `Failed to load the protocol info\n`

## pseudocode

```c
__int64 __fastcall CONFIG_CS::ReadDataFromStore(
        CONFIG_CS *this,
        struct APP_POOL_DATA_OBJECT_TABLE **a2,
        struct SITE_DATA_OBJECT_TABLE **a3,
        struct APPLICATION_DATA_OBJECT_TABLE **a4,
        struct GLOBAL_DATA_STORE **a5,
        struct PROTOCOL_DATA_OBJECT_TABLE **a6)
{
  CONFIG_CS *v7; // rcx
  int v8; // ebx
  struct GLOBAL_DATA_STORE_CS *v9; // rdi
  int FreshSections; // eax
  struct INativeConfigurationElement *v11; // r13
  struct INativeConfigurationElement *v12; // r15
  struct INativeConfigurationElement *v13; // r12
  struct INativeConfigurationElement *v14; // r14
  struct INativeConfigurationElement *v15; // rsi
  struct APP_POOL_DATA_OBJECT_TABLE_CS *v16; // rax
  struct SITE_DATA_OBJECT_TABLE_CS *v17; // rax
  struct APPLICATION_DATA_OBJECT_TABLE_CS *v18; // rax
  struct PROTOCOL_DATA_OBJECT_TABLE **v19; // rcx
  struct GLOBAL_DATA_STORE_CS *v21; // [rsp+30h] [rbp-D0h] BYREF
  struct APP_POOL_DATA_OBJECT_TABLE_CS *v22; // [rsp+38h] [rbp-C8h] BYREF
  struct SITE_DATA_OBJECT_TABLE_CS *v23; // [rsp+40h] [rbp-C0h] BYREF
  struct APPLICATION_DATA_OBJECT_TABLE_CS *v24; // [rsp+48h] [rbp-B8h] BYREF
  struct PROTOCOL_DATA_OBJECT_TABLE_CS *v25; // [rsp+50h] [rbp-B0h] BYREF
  struct INativeConfigurationElement *v26; // [rsp+58h] [rbp-A8h] BYREF
  struct INativeConfigurationElement *v27; // [rsp+60h] [rbp-A0h] BYREF
  struct INativeConfigurationElement *v28; // [rsp+68h] [rbp-98h] BYREF
  struct INativeConfigurationElement *v29; // [rsp+70h] [rbp-90h] BYREF
  struct INativeConfigurationElement *v30; // [rsp+78h] [rbp-88h] BYREF
  struct APP_POOL_DATA_OBJECT_TABLE **v31; // [rsp+80h] [rbp-80h]
  struct SITE_DATA_OBJECT_TABLE **v32; // [rsp+88h] [rbp-78h]
  struct APPLICATION_DATA_OBJECT_TABLE **v33; // [rsp+90h] [rbp-70h]
  struct GLOBAL_DATA_STORE **v34; // [rsp+98h] [rbp-68h]
  struct PROTOCOL_DATA_OBJECT_TABLE **v35; // [rsp+A0h] [rbp-60h]
  _QWORD v36[4]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v37[8256]; // [rsp+D0h] [rbp-30h] BYREF

  v34 = a5;
  v35 = a6;
  v36[0] = &BINDING_INFO_WRITER::`vftable';
  v33 = a4;
  v32 = a3;
  v31 = a2;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v36[1] = -1;
  v36[2] = 0;
  v36[3] = 0;
  STRU::STRU((STRU *)v37);
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v8 = CONFIG_CS::CreateNewTables(v7, &v21, &v22, &v23, &v24, &v25);
  if ( v8 >= 0 )
  {
    FreshSections = CONFIG_CS::GetFreshSections(this, &v26, &v27, &v28, &v29, &v30);
    v11 = v26;
    v8 = FreshSections;
    v12 = v27;
    v13 = v28;
    v14 = v29;
    v15 = v30;
    if ( FreshSections >= 0 )
    {
      v9 = v21;
      v8 = GLOBAL_DATA_STORE_CS::ReadFromConfigSystem(v21, v26, v27);
      if ( v8 >= 0 )
      {
        v8 = PROTOCOL_DATA_OBJECT_TABLE_CS::ReadFromConfigSystem(v25, v15);
        if ( v8 >= 0 )
        {
          v8 = APP_POOL_DATA_OBJECT_TABLE_CS::ReadFromConfigSystem(v22, v14);
          if ( v8 >= 0 )
          {
            v8 = SITE_DATA_OBJECT_TABLE_CS::ReadFromConfigSystem(v23, v13, v24, (struct BINDING_INFO_WRITER *)v36);
            if ( v8 >= 0 )
            {
              if ( *((_DWORD *)g_pWebAdminService + 412)
                || (v8 = BINDING_INFO_WRITER::Write((BINDING_INFO_WRITER *)v36), v8 >= 0) )
              {
                v16 = v22;
                v22 = 0;
                *v31 = v16;
                v17 = v23;
                v23 = 0;
                *v32 = v17;
                v18 = v24;
                v24 = 0;
                *v33 = v18;
                v19 = v35;
                *v34 = v9;
                v9 = 0;
                *v19 = v25;
                v25 = 0;
              }
            }
            else if ( (g_dwDebugFlags & 0xF) != 0 )
            {
              PuDbgPrintError(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_cs.cxx",
                333,
                "CONFIG_CS::ReadDataFromStore",
                v8,
                "Failed to load the app pool info\n");
            }
          }
          else if ( (g_dwDebugFlags & 0xF) != 0 )
          {
            PuDbgPrintError(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_cs.cxx",
              317,
              "CONFIG_CS::ReadDataFromStore",
              v8,
              "Failed to load the app pool info\n");
          }
        }
        else if ( (g_dwDebugFlags & 0xF) != 0 )
        {
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_cs.cxx",
            304,
            "CONFIG_CS::ReadDataFromStore",
            v8,
            "Failed to load the protocol info\n");
        }
      }
      else if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_cs.cxx",
          291,
          "CONFIG_CS::ReadDataFromStore",
          v8,
          "Failed to load the global store\n");
      }
    }
    else
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_cs.cxx",
          276,
          "CONFIG_CS::ReadDataFromStore",
          FreshSections,
          "Failed getting a section from the config store\n");
      v9 = v21;
    }
    if ( v11 )
      (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v11 + 16LL))(v11);
    if ( v12 )
      (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v12 + 16LL))(v12);
    if ( v13 )
      (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v13 + 16LL))(v13);
    if ( v14 )
      (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v14 + 16LL))(v14);
    if ( v15 )
      (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v15 + 16LL))(v15);
  }
  else
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_cs.cxx",
        260,
        "CONFIG_CS::ReadDataFromStore",
        v8,
        "Failed creating new tables\n");
    v9 = v21;
  }
  if ( v22 )
    (**(void (__fastcall ***)(struct APP_POOL_DATA_OBJECT_TABLE_CS *, __int64))v22)(v22, 1);
  if ( v23 )
    (**(void (__fastcall ***)(struct SITE_DATA_OBJECT_TABLE_CS *, __int64))v23)(v23, 1);
  if ( v24 )
    (**(void (__fastcall ***)(struct APPLICATION_DATA_OBJECT_TABLE_CS *, __int64))v24)(v24, 1);
  if ( v9 )
    (**(void (__fastcall ***)(struct GLOBAL_DATA_STORE_CS *, __int64))v9)(v9, 1);
  if ( v25 )
    (**(void (__fastcall ***)(struct PROTOCOL_DATA_OBJECT_TABLE_CS *, __int64))v25)(v25, 1);
  BINDING_INFO_WRITER::~BINDING_INFO_WRITER((BINDING_INFO_WRITER *)v36);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800418c0  push    rbp
0x1800418c2  push    rbx
0x1800418c3  push    rsi
0x1800418c4  push    rdi
0x1800418c5  push    r12
0x1800418c7  push    r13
0x1800418c9  push    r14
0x1800418cb  push    r15
0x1800418cd  lea     rbp, [rsp-2028h]
0x1800418d5  mov     eax, 2128h
0x1800418da  call    _alloca_probe
0x1800418df  sub     rsp, rax
0x1800418e2  mov     rax, cs:__security_cookie
0x1800418e9  xor     rax, rsp
0x1800418ec  mov     [rbp+2060h+var_50], rax
0x1800418f3  mov     rax, [rbp+2060h+arg_20]
0x1800418fa  xor     r13d, r13d
0x1800418fd  mov     [rbp+2060h+var_20C8], rax
0x180041901  mov     rdi, rcx
0x180041904  mov     rax, [rbp+2060h+arg_28]
0x18004190b  lea     rcx, [rbp+2060h+var_2090]
0x18004190f  mov     [rbp+2060h+var_20C0], rax
0x180041913  lea     rax, ??_7BINDING_INFO_WRITER@@6B@; const BINDING_INFO_WRITER::`vftable'
0x18004191a  mov     [rbp+2060h+var_20B0], rax
0x18004191e  mov     [rbp+2060h+var_20D0], r9
0x180041922  mov     [rbp+2060h+var_20D8], r8
0x180041926  mov     [rbp+2060h+var_20E0], rdx
0x18004192a  mov     [rsp+2160h+var_2130], r13
0x18004192f  mov     [rsp+2160h+var_2128], r13
0x180041934  mov     [rsp+2160h+var_2120], r13
0x180041939  mov     [rsp+2160h+var_2118], r13
0x18004193e  mov     [rsp+2160h+var_2110], r13
0x180041943  mov     [rbp+2060h+var_20A8], 0FFFFFFFFFFFFFFFFh
0x18004194b  mov     [rbp+2060h+var_20A0], r13
0x18004194f  mov     [rbp+2060h+var_2098], r13
0x180041953  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180041959  lea     rax, [rsp+2160h+var_2110]
0x18004195e  mov     [rsp+2160h+var_2108], r13
0x180041963  mov     [rsp+2160h+var_2138], rax; struct PROTOCOL_DATA_OBJECT_TABLE_CS **
0x180041968  lea     r9, [rsp+2160h+var_2120]; struct SITE_DATA_OBJECT_TABLE_CS **
0x18004196d  lea     rax, [rsp+2160h+var_2118]
0x180041972  mov     [rsp+2160h+var_2100], r13
0x180041977  lea     r8, [rsp+2160h+var_2128]; struct APP_POOL_DATA_OBJECT_TABLE_CS **
0x18004197c  mov     [rsp+2160h+var_2140], rax; struct APPLICATION_DATA_OBJECT_TABLE_CS **
0x180041981  lea     rdx, [rsp+2160h+var_2130]; struct GLOBAL_DATA_STORE_CS **
0x180041986  mov     [rsp+2160h+var_20F8], r13
0x18004198b  mov     [rsp+2160h+var_20F0], r13
0x180041990  mov     [rsp+2160h+var_20E8], r13
0x180041995  call    ?CreateNewTables@CONFIG_CS@@AEAAJPEAPEAVGLOBAL_DATA_STORE_CS@@PEAPEAVAPP_POOL_DATA_OBJECT_TABLE_CS@@PEAPEAVSITE_DATA_OBJECT_TABLE_CS@@PEAPEAVAPPLICATION_DATA_OBJECT_TABLE_CS@@PEAPEAVPROTOCOL_DATA_OBJECT_TABLE_CS@@@Z; CONFIG_CS::CreateNewTables(GLOBAL_DATA_STORE_CS * *,APP_POOL_DATA_OBJECT_TABLE_CS * *,SITE_DATA_OBJECT_TABLE_CS * *,APPLICATION_DATA_OBJECT_TABLE_CS * *,PROTOCOL_DATA_OBJECT_TABLE_CS * *)
0x18004199a  mov     ebx, eax
0x18004199c  test    eax, eax
0x18004199e  jns     short loc_1800419E4
0x1800419a0  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800419a7  jz      short loc_1800419DA
0x1800419a9  mov     rcx, cs:g_pDebug
0x1800419b0  lea     rax, aFailedCreating_0; "Failed creating new tables\n"
0x1800419b7  mov     [rsp+2160h+var_2138], rax
0x1800419bc  lea     r9, aConfigCsReadda; "CONFIG_CS::ReadDataFromStore"
0x1800419c3  mov     r8d, 104h
0x1800419c9  mov     dword ptr [rsp+2160h+var_2140], ebx
0x1800419cd  lea     rdx, aServercommonIn_30; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800419d4  call    cs:__imp_PuDbgPrintError
0x1800419da  mov     rdi, [rsp+2160h+var_2130]
0x1800419df  jmp     loc_180041C48
0x1800419e4  lea     rax, [rsp+2160h+var_20E8]
0x1800419e9  mov     rcx, rdi; this
0x1800419ec  mov     [rsp+2160h+var_2138], rax; struct INativeConfigurationElement **
0x1800419f1  lea     r9, [rsp+2160h+var_20F8]; struct INativeConfigurationElement **
0x1800419f6  lea     rax, [rsp+2160h+var_20F0]
0x1800419fb  lea     r8, [rsp+2160h+var_2100]; struct INativeConfigurationElement **
0x180041a00  mov     [rsp+2160h+var_2140], rax; struct INativeConfigurationElement **
0x180041a05  lea     rdx, [rsp+2160h+var_2108]; struct INativeConfigurationElement **
0x180041a0a  call    ?GetFreshSections@CONFIG_CS@@AEAAJPEAPEAVINativeConfigurationElement@@0000@Z; CONFIG_CS::GetFreshSections(INativeConfigurationElement * *,INativeConfigurationElement * *,INativeConfigurationElement * *,INativeConfigurationElement * *,INativeConfigurationElement * *)
0x180041a0f  mov     r13, [rsp+2160h+var_2108]
0x180041a14  mov     ebx, eax
0x180041a16  mov     r15, [rsp+2160h+var_2100]
0x180041a1b  mov     r12, [rsp+2160h+var_20F8]
0x180041a20  mov     r14, [rsp+2160h+var_20F0]
0x180041a25  mov     rsi, [rsp+2160h+var_20E8]
0x180041a2a  test    eax, eax
0x180041a2c  jns     short loc_180041A72
0x180041a2e  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180041a35  jz      short loc_180041A68
0x180041a37  mov     rcx, cs:g_pDebug
0x180041a3e  lea     rax, aFailedGettingA; "Failed getting a section from the confi"...
0x180041a45  mov     [rsp+2160h+var_2138], rax
0x180041a4a  lea     r9, aConfigCsReadda; "CONFIG_CS::ReadDataFromStore"
0x180041a51  mov     r8d, 114h
0x180041a57  mov     dword ptr [rsp+2160h+var_2140], ebx
0x180041a5b  lea     rdx, aServercommonIn_30; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180041a62  call    cs:__imp_PuDbgPrintError
0x180041a68  mov     rdi, [rsp+2160h+var_2130]
0x180041a6d  jmp     loc_180041BE2
0x180041a72  mov     rdi, [rsp+2160h+var_2130]
0x180041a77  mov     r8, r15; struct INativeConfigurationElement *
0x180041a7a  mov     rcx, rdi; this
0x180041a7d  mov     rdx, r13; struct INativeConfigurationElement *
0x180041a80  call    ?ReadFromConfigSystem@GLOBAL_DATA_STORE_CS@@QEAAJPEAVINativeConfigurationElement@@0@Z; GLOBAL_DATA_STORE_CS::ReadFromConfigSystem(INativeConfigurationElement *,INativeConfigurationElement *)
0x180041a85  mov     ebx, eax
0x180041a87  test    eax, eax
0x180041a89  jns     short loc_180041ACE
0x180041a8b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180041a92  jz      loc_180041BE2
0x180041a98  lea     rax, aFailedToLoadTh_1; "Failed to load the global store\n"
0x180041a9f  mov     r8d, 123h
0x180041aa5  mov     rcx, cs:g_pDebug
0x180041aac  lea     r9, aConfigCsReadda; "CONFIG_CS::ReadDataFromStore"
0x180041ab3  mov     [rsp+2160h+var_2138], rax
0x180041ab8  lea     rdx, aServercommonIn_30; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180041abf  mov     dword ptr [rsp+2160h+var_2140], ebx
0x180041ac3  call    cs:__imp_PuDbgPrintError
0x180041ac9  jmp     loc_180041BE2
0x180041ace  mov     rcx, [rsp+2160h+var_2110]; this
0x180041ad3  mov     rdx, rsi; struct INativeConfigurationElement *
0x180041ad6  call    ?ReadFromConfigSystem@PROTOCOL_DATA_OBJECT_TABLE_CS@@QEAAJPEAVINativeConfigurationElement@@@Z; PROTOCOL_DATA_OBJECT_TABLE_CS::ReadFromConfigSystem(INativeConfigurationElement *)
0x180041adb  mov     ebx, eax
0x180041add  test    eax, eax
0x180041adf  jns     short loc_180041AFD
0x180041ae1  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180041ae8  jz      loc_180041BE2
0x180041aee  lea     rax, aFailedToLoadTh; "Failed to load the protocol info\n"
0x180041af5  mov     r8d, 130h
0x180041afb  jmp     short loc_180041AA5
0x180041afd  mov     rcx, [rsp+2160h+var_2128]; this
0x180041b02  mov     rdx, r14; struct INativeConfigurationElement *
0x180041b05  call    ?ReadFromConfigSystem@APP_POOL_DATA_OBJECT_TABLE_CS@@QEAAJPEAVINativeConfigurationElement@@@Z; APP_POOL_DATA_OBJECT_TABLE_CS::ReadFromConfigSystem(INativeConfigurationElement *)
0x180041b0a  mov     ebx, eax
0x180041b0c  test    eax, eax
0x180041b0e  jns     short loc_180041B2F
0x180041b10  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180041b17  jz      loc_180041BE2
0x180041b1d  lea     rax, aFailedToLoadTh_0; "Failed to load the app pool info\n"
0x180041b24  mov     r8d, 13Dh
0x180041b2a  jmp     loc_180041AA5
0x180041b2f  mov     r8, [rsp+2160h+var_2118]; struct APPLICATION_DATA_OBJECT_TABLE_CS *
0x180041b34  lea     r9, [rbp+2060h+var_20B0]; struct BINDING_INFO_WRITER *
0x180041b38  mov     rcx, [rsp+2160h+var_2120]; this
0x180041b3d  mov     rdx, r12; struct INativeConfigurationElement *
0x180041b40  call    ?ReadFromConfigSystem@SITE_DATA_OBJECT_TABLE_CS@@QEAAJPEAVINativeConfigurationElement@@PEAVAPPLICATION_DATA_OBJECT_TABLE_CS@@PEAVBINDING_INFO_WRITER@@@Z; SITE_DATA_OBJECT_TABLE_CS::ReadFromConfigSystem(INativeConfigurationElement *,APPLICATION_DATA_OBJECT_TABLE_CS *,BINDING_INFO_WRITER *)
0x180041b45  mov     ebx, eax
0x180041b47  test    eax, eax
0x180041b49  jns     short loc_180041B6A
0x180041b4b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180041b52  jz      loc_180041BE2
0x180041b58  lea     rax, aFailedToLoadTh_0; "Failed to load the app pool info\n"
0x180041b5f  mov     r8d, 14Dh
0x180041b65  jmp     loc_180041AA5
0x180041b6a  mov     rax, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x180041b71  cmp     dword ptr [rax+670h], 0
0x180041b78  jnz     short loc_180041B89
0x180041b7a  lea     rcx, [rbp+2060h+var_20B0]; this
0x180041b7e  call    ?Write@BINDING_INFO_WRITER@@QEAAJXZ; BINDING_INFO_WRITER::Write(void)
0x180041b83  mov     ebx, eax
0x180041b85  test    eax, eax
0x180041b87  js      short loc_180041BE2
0x180041b89  mov     rax, [rsp+2160h+var_2128]
0x180041b8e  mov     rcx, [rbp+2060h+var_20E0]
0x180041b92  mov     [rsp+2160h+var_2128], 0
0x180041b9b  mov     [rcx], rax
0x180041b9e  mov     rax, [rsp+2160h+var_2120]
0x180041ba3  mov     rcx, [rbp+2060h+var_20D8]
0x180041ba7  mov     [rsp+2160h+var_2120], 0
0x180041bb0  mov     [rcx], rax
0x180041bb3  mov     rax, [rsp+2160h+var_2118]
0x180041bb8  mov     rcx, [rbp+2060h+var_20D0]
0x180041bbc  mov     [rsp+2160h+var_2118], 0
0x180041bc5  mov     [rcx], rax
0x180041bc8  mov     rax, [rbp+2060h+var_20C8]
0x180041bcc  mov     rcx, [rbp+2060h+var_20C0]
0x180041bd0  mov     [rax], rdi
0x180041bd3  xor     edi, edi
0x180041bd5  mov     rax, [rsp+2160h+var_2110]
0x180041bda  mov     [rcx], rax
0x180041bdd  mov     [rsp+2160h+var_2110], rdi
0x180041be2  test    r13, r13
0x180041be5  jz      short loc_180041BF7
0x180041be7  mov     rax, [r13+0]
0x180041beb  mov     rcx, r13
0x180041bee  mov     rax, [rax+10h]
0x180041bf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041bf7  test    r15, r15
0x180041bfa  jz      short loc_180041C0B
0x180041bfc  mov     rax, [r15]
0x180041bff  mov     rcx, r15
0x180041c02  mov     rax, [rax+10h]
0x180041c06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041c0b  test    r12, r12
0x180041c0e  jz      short loc_180041C20
0x180041c10  mov     rax, [r12]
0x180041c14  mov     rcx, r12
0x180041c17  mov     rax, [rax+10h]
0x180041c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041c20  test    r14, r14
0x180041c23  jz      short loc_180041C34
0x180041c25  mov     rax, [r14]
0x180041c28  mov     rcx, r14
0x180041c2b  mov     rax, [rax+10h]
0x180041c2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041c34  test    rsi, rsi
0x180041c37  jz      short loc_180041C48
0x180041c39  mov     rax, [rsi]
0x180041c3c  mov     rcx, rsi
0x180041c3f  mov     rax, [rax+10h]
0x180041c43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041c48  mov     rcx, [rsp+2160h+var_2128]
0x180041c4d  mov     esi, 1
0x180041c52  test    rcx, rcx
0x180041c55  jz      short loc_180041C64
0x180041c57  mov     rax, [rcx]
0x180041c5a  mov     edx, esi
0x180041c5c  mov     rax, [rax]
0x180041c5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041c64  mov     rcx, [rsp+2160h+var_2120]
0x180041c69  test    rcx, rcx
0x180041c6c  jz      short loc_180041C7B
0x180041c6e  mov     rax, [rcx]
0x180041c71  mov     edx, esi
0x180041c73  mov     rax, [rax]
0x180041c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041c7b  mov     rcx, [rsp+2160h+var_2118]
0x180041c80  test    rcx, rcx
0x180041c83  jz      short loc_180041C92
0x180041c85  mov     rax, [rcx]
0x180041c88  mov     edx, esi
0x180041c8a  mov     rax, [rax]
0x180041c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041c92  test    rdi, rdi
0x180041c95  jz      short loc_180041CA7
0x180041c97  mov     rax, [rdi]
0x180041c9a  mov     edx, esi
0x180041c9c  mov     rcx, rdi
0x180041c9f  mov     rax, [rax]
0x180041ca2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041ca7  mov     rcx, [rsp+2160h+var_2110]
0x180041cac  test    rcx, rcx
0x180041caf  jz      short loc_180041CBE
0x180041cb1  mov     rax, [rcx]
0x180041cb4  mov     edx, esi
0x180041cb6  mov     rax, [rax]
0x180041cb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041cbe  lea     rcx, [rbp+2060h+var_20B0]; this
0x180041cc2  call    ??1BINDING_INFO_WRITER@@UEAA@XZ; BINDING_INFO_WRITER::~BINDING_INFO_WRITER(void)
0x180041cc7  mov     eax, ebx
0x180041cc9  mov     rcx, [rbp+2060h+var_50]
0x180041cd0  xor     rcx, rsp; StackCookie
0x180041cd3  call    __security_check_cookie
0x180041cd8  add     rsp, 2128h
0x180041cdf  pop     r15
0x180041ce1  pop     r14
0x180041ce3  pop     r13
0x180041ce5  pop     r12
0x180041ce7  pop     rdi
0x180041ce8  pop     rsi
0x180041ce9  pop     rbx
0x180041cea  pop     rbp
0x180041ceb  retn
```
