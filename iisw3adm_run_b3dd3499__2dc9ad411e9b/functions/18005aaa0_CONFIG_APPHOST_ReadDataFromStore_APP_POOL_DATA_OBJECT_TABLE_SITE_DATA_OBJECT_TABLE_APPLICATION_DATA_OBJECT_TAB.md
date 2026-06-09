# CONFIG_APPHOST::ReadDataFromStore(APP_POOL_DATA_OBJECT_TABLE * *,SITE_DATA_OBJECT_TABLE * *,APPLICATION_DATA_OBJECT_TABLE * *,GLOBAL_DATA_STORE * *,PROTOCOL_DATA_OBJECT_TABLE * *,PROTOCOL_BINDING_TABLE * *)

- ea: `0x18005aaa0`
- end: `0x18005afb2`
- name: `?ReadDataFromStore@CONFIG_APPHOST@@UEAAJPEAPEAVAPP_POOL_DATA_OBJECT_TABLE@@PEAPEAVSITE_DATA_OBJECT_TABLE@@PEAPEAVAPPLICATION_DATA_OBJECT_TABLE@@PEAPEAVGLOBAL_DATA_STORE@@PEAPEAVPROTOCOL_DATA_OBJECT_TABLE@@PEAPEAVPROTOCOL_BINDING_TABLE@@@Z`
- size: `1298`
- prototype: `__int64 __fastcall(CONFIG_APPHOST *__hidden this, struct APP_POOL_DATA_OBJECT_TABLE **, struct SITE_DATA_OBJECT_TABLE **, struct APPLICATION_DATA_OBJECT_TABLE **, struct GLOBAL_DATA_STORE **, struct PROTOCOL_DATA_OBJECT_TABLE **, struct PROTOCOL_BINDING_TABLE **)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18002e114`
- `0x180043c80`
- `0x1800526d0`
- `0x180056fec`
- `0x18005740c`
- `0x180058b64`
- `0x180059a48`
- `0x18005a328`
- `0x18005aaa0`
- `0x18005b0e8`
- `0x180061060`
- `0x180061120`
- `0x180062010`

## import_xrefs

- `iisutil!PuDbgPrintError` at `0x18005abd8`
- `iisutil!PuDbgPrintError` at `0x18005ac5b`
- `iisutil!PuDbgPrintError` at `0x18005acb8`
- `iisutil!PuDbgPrintError` at `0x18005abd8`
- `iisutil!PuDbgPrintError` at `0x18005ac5b`
- `iisutil!PuDbgPrintError` at `0x18005acb8`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18005ab63`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18005ab63`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18005ab3e`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18005ab3e`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18005af87`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18005af87`

## string_xrefs

- `0x18005ac37`: `Failed getting a section from the config store\n`
- `0x18005ace6`: `Failed to load the protocol info\n`
- `0x18005abd1`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\config_apphost.cxx`
- `0x18005ac54`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\config_apphost.cxx`
- `0x18005acad`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\config_apphost.cxx`
- `0x18005abc0`: `CONFIG_APPHOST::ReadDataFromStore`
- `0x18005ac43`: `CONFIG_APPHOST::ReadDataFromStore`
- `0x18005aca1`: `CONFIG_APPHOST::ReadDataFromStore`

## pseudocode

```c
__int64 __fastcall CONFIG_APPHOST::ReadDataFromStore(
        CONFIG_APPHOST *this,
        struct APP_POOL_DATA_OBJECT_TABLE **a2,
        struct SITE_DATA_OBJECT_TABLE **a3,
        struct APPLICATION_DATA_OBJECT_TABLE **a4,
        struct GLOBAL_DATA_STORE **a5,
        struct PROTOCOL_DATA_OBJECT_TABLE **a6,
        struct PROTOCOL_BINDING_TABLE **a7)
{
  signed int v8; // ebx
  struct GLOBAL_DATA_STORE_APPHOST *v9; // rdi
  int FreshSections; // eax
  struct IWebLimits *v11; // r12
  struct ILogSettings *v12; // r15
  struct IEnumApplicationPool *v13; // r13
  struct IEnumListenerAdapter *v14; // r14
  PROTOCOL_BINDING_TABLE *v15; // rcx
  struct APP_POOL_DATA_OBJECT_TABLE_APPHOST *v16; // rax
  struct SITE_DATA_OBJECT_TABLE_APPHOST *v17; // rax
  struct APPLICATION_DATA_OBJECT_TABLE_APPHOST *v18; // rax
  struct PROTOCOL_DATA_OBJECT_TABLE **v19; // rcx
  struct GLOBAL_DATA_STORE_APPHOST *v21; // [rsp+40h] [rbp-C0h] BYREF
  struct APP_POOL_DATA_OBJECT_TABLE_APPHOST *v22; // [rsp+48h] [rbp-B8h] BYREF
  struct SITE_DATA_OBJECT_TABLE_APPHOST *v23; // [rsp+50h] [rbp-B0h] BYREF
  struct APPLICATION_DATA_OBJECT_TABLE_APPHOST *v24; // [rsp+58h] [rbp-A8h] BYREF
  struct PROTOCOL_DATA_OBJECT_TABLE_APPHOST *v25; // [rsp+60h] [rbp-A0h] BYREF
  PROTOCOL_BINDING_TABLE *v26; // [rsp+68h] [rbp-98h] BYREF
  struct IEnumSite *v27; // [rsp+70h] [rbp-90h] BYREF
  struct IWebLimits *v28; // [rsp+78h] [rbp-88h] BYREF
  struct ILogSettings *v29; // [rsp+80h] [rbp-80h] BYREF
  struct IEnumApplicationPool *v30; // [rsp+88h] [rbp-78h] BYREF
  struct IEnumListenerAdapter *v31; // [rsp+90h] [rbp-70h] BYREF
  struct PROTOCOL_BINDING_TABLE **v32; // [rsp+98h] [rbp-68h]
  struct APP_POOL_DATA_OBJECT_TABLE **v33; // [rsp+A0h] [rbp-60h]
  struct SITE_DATA_OBJECT_TABLE **v34; // [rsp+A8h] [rbp-58h]
  struct APPLICATION_DATA_OBJECT_TABLE **v35; // [rsp+B0h] [rbp-50h]
  struct GLOBAL_DATA_STORE **v36; // [rsp+B8h] [rbp-48h]
  struct PROTOCOL_DATA_OBJECT_TABLE **v37; // [rsp+C0h] [rbp-40h]
  _BYTE v38[56]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v39[4]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v40[8256]; // [rsp+120h] [rbp+20h] BYREF

  v36 = a5;
  v37 = a6;
  v32 = a7;
  v35 = a4;
  v34 = a3;
  v33 = a2;
  v26 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v28 = 0;
  v29 = 0;
  v27 = 0;
  v30 = 0;
  v31 = 0;
  MULTISZ::MULTISZ((MULTISZ *)v38);
  v39[1] = -1;
  v39[0] = &BINDING_INFO_WRITER::`vftable';
  v39[2] = 0;
  v39[3] = 0;
  STRU::STRU((STRU *)v40);
  v8 = CONFIG_APPHOST::CreateNewTables(this, &v21, &v22, &v23, &v24, &v25, &v26);
  if ( v8 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_apphost.cxx",
        380,
        "CONFIG_APPHOST::ReadDataFromStore",
        v8,
        "Failed creating new tables\n");
    v9 = v21;
    goto LABEL_40;
  }
  FreshSections = CONFIG_APPHOST::GetFreshSections(this, &v28, &v29, &v27, &v30, &v31);
  v11 = v28;
  v8 = FreshSections;
  v12 = v29;
  v13 = v30;
  v14 = v31;
  if ( FreshSections >= 0 )
  {
    v9 = v21;
    v8 = GLOBAL_DATA_STORE_APPHOST::ReadFromAppHostProvider(v21, v28, v29);
    if ( v8 >= 0 )
    {
      v8 = PROTOCOL_DATA_OBJECT_TABLE_APPHOST::ReadFromAppHostProvider(v25, v14);
      if ( v8 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(struct SITE_DATA_OBJECT_TABLE_APPHOST *, struct IEnumSite *, struct APPLICATION_DATA_OBJECT_TABLE_APPHOST *, _QWORD *, bool, unsigned __int64))(*(_QWORD *)v23 + 16LL))(
               v23,
               v27,
               v24,
               v39,
               *((_DWORD *)this + 2) != 0,
               (unsigned __int64)v38 & -(__int64)(*((_DWORD *)this + 2) != 0));
        if ( v8 >= 0 )
        {
          v8 = (*(__int64 (__fastcall **)(struct APP_POOL_DATA_OBJECT_TABLE_APPHOST *, struct IEnumApplicationPool *, bool, unsigned __int64))(*(_QWORD *)v22 + 16LL))(
                 v22,
                 v13,
                 *((_DWORD *)this + 2) != 0,
                 (unsigned __int64)v38 & -(__int64)(*((_DWORD *)this + 2) != 0));
          if ( v8 >= 0 )
          {
            if ( *((_DWORD *)this + 2) )
              *((_DWORD *)this + 2) = 0;
            if ( !v32
              || ((*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 8LL))(*((_QWORD *)this + 5)),
                  v15 = v26,
                  *((_QWORD *)v26 + 135) = *((_QWORD *)this + 5),
                  *((_QWORD *)v15 + 271) = (char *)v15 + 2176,
                  v8 = PROTOCOL_BINDING_TABLE::PopulateNoLock(v15),
                  v8 >= 0) )
            {
              if ( *((_DWORD *)g_pWebAdminService + 412)
                || (v8 = BINDING_INFO_WRITER::Write((BINDING_INFO_WRITER *)v39), v8 >= 0) )
              {
                v16 = v22;
                v22 = 0;
                *v33 = v16;
                v17 = v23;
                v23 = 0;
                *v34 = v17;
                v18 = v24;
                v24 = 0;
                *v35 = v18;
                v19 = v37;
                *v36 = v9;
                v9 = 0;
                *v19 = v25;
                v25 = 0;
                if ( v32 )
                {
                  *v32 = v26;
                  v26 = 0;
                }
              }
            }
            goto LABEL_30;
          }
          if ( (g_dwDebugFlags & 0xF) != 0 )
            PuDbgPrintError(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_apphost.cxx",
              466,
              "CONFIG_APPHOST::ReadDataFromStore",
              v8,
              "Failed to load the app pool info\n");
        }
        else if ( (g_dwDebugFlags & 0xF) != 0 )
        {
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_apphost.cxx",
            447,
            "CONFIG_APPHOST::ReadDataFromStore",
            v8,
            "Failed to load the site info\n");
        }
      }
      else if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_apphost.cxx",
          425,
          "CONFIG_APPHOST::ReadDataFromStore",
          v8,
          "Failed to load the protocol info\n");
      }
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_apphost.cxx",
        410,
        "CONFIG_APPHOST::ReadDataFromStore",
        v8,
        "Failed to load the global store\n");
    }
    CONFIG_APPHOST::WriteEventLogConfigError(v8);
  }
  else
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_apphost.cxx",
        396,
        "CONFIG_APPHOST::ReadDataFromStore",
        FreshSections,
        "Failed getting a section from the config store\n");
    v9 = v21;
  }
LABEL_30:
  if ( v11 )
    (*(void (__fastcall **)(struct IWebLimits *))(*(_QWORD *)v11 + 16LL))(v11);
  if ( v12 )
    (*(void (__fastcall **)(struct ILogSettings *))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v27 )
    (*(void (__fastcall **)(struct IEnumSite *))(*(_QWORD *)v27 + 16LL))(v27);
  if ( v13 )
    (*(void (__fastcall **)(struct IEnumApplicationPool *))(*(_QWORD *)v13 + 16LL))(v13);
  if ( v14 )
    (*(void (__fastcall **)(struct IEnumListenerAdapter *))(*(_QWORD *)v14 + 16LL))(v14);
LABEL_40:
  if ( v22 )
    (**(void (__fastcall ***)(struct APP_POOL_DATA_OBJECT_TABLE_APPHOST *, __int64))v22)(v22, 1);
  if ( v23 )
    (**(void (__fastcall ***)(struct SITE_DATA_OBJECT_TABLE_APPHOST *, __int64))v23)(v23, 1);
  if ( v24 )
    (**(void (__fastcall ***)(struct APPLICATION_DATA_OBJECT_TABLE_APPHOST *, __int64))v24)(v24, 1);
  if ( v9 )
    (**(void (__fastcall ***)(struct GLOBAL_DATA_STORE_APPHOST *, __int64))v9)(v9, 1);
  if ( v25 )
    (**(void (__fastcall ***)(struct PROTOCOL_DATA_OBJECT_TABLE_APPHOST *, __int64))v25)(v25, 1);
  if ( v26 )
    PROTOCOL_BINDING_TABLE::Dereference(v26);
  BINDING_INFO_WRITER::~BINDING_INFO_WRITER((BINDING_INFO_WRITER *)v39);
  MULTISZ::~MULTISZ((MULTISZ *)v38);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18005aaa0  push    rbp
0x18005aaa2  push    rbx
0x18005aaa3  push    rsi
0x18005aaa4  push    rdi
0x18005aaa5  push    r12
0x18005aaa7  push    r13
0x18005aaa9  push    r14
0x18005aaab  push    r15
0x18005aaad  lea     rbp, [rsp-2078h]
0x18005aab5  mov     eax, 2178h
0x18005aaba  call    _alloca_probe
0x18005aabf  sub     rsp, rax
0x18005aac2  mov     rax, cs:__security_cookie
0x18005aac9  xor     rax, rsp
0x18005aacc  mov     [rbp+20B0h+var_50], rax
0x18005aad3  mov     rax, [rbp+20B0h+arg_20]
0x18005aada  xor     r12d, r12d
0x18005aadd  mov     [rbp+20B0h+var_20F8], rax
0x18005aae1  mov     rsi, rcx
0x18005aae4  mov     rax, [rbp+20B0h+arg_28]
0x18005aaeb  lea     rcx, [rbp+20B0h+var_20E8]
0x18005aaef  mov     [rbp+20B0h+var_20F0], rax
0x18005aaf3  mov     rax, [rbp+20B0h+arg_30]
0x18005aafa  mov     [rbp+20B0h+var_2118], rax
0x18005aafe  mov     [rbp+20B0h+var_2100], r9
0x18005ab02  mov     [rbp+20B0h+var_2108], r8
0x18005ab06  mov     [rbp+20B0h+var_2110], rdx
0x18005ab0a  mov     [rsp+21B0h+var_2148], r12
0x18005ab0f  mov     [rsp+21B0h+var_2170], r12
0x18005ab14  mov     [rsp+21B0h+var_2168], r12
0x18005ab19  mov     [rsp+21B0h+var_2160], r12
0x18005ab1e  mov     [rsp+21B0h+var_2158], r12
0x18005ab23  mov     [rsp+21B0h+var_2150], r12
0x18005ab28  mov     [rsp+21B0h+var_2138], r12
0x18005ab2d  mov     [rbp+20B0h+var_2130], r12
0x18005ab31  mov     [rsp+21B0h+var_2140], r12
0x18005ab36  mov     [rbp+20B0h+var_2128], r12
0x18005ab3a  mov     [rbp+20B0h+var_2120], r12
0x18005ab3e  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x18005ab44  lea     rax, ??_7BINDING_INFO_WRITER@@6B@; const BINDING_INFO_WRITER::`vftable'
0x18005ab4b  mov     [rbp+20B0h+var_20A8], 0FFFFFFFFFFFFFFFFh
0x18005ab53  lea     rcx, [rbp+20B0h+var_2090]
0x18005ab57  mov     [rbp+20B0h+var_20B0], rax
0x18005ab5b  mov     [rbp+20B0h+var_20A0], r12
0x18005ab5f  mov     [rbp+20B0h+var_2098], r12
0x18005ab63  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18005ab69  lea     rax, [rsp+21B0h+var_2148]
0x18005ab6e  mov     rcx, rsi; this
0x18005ab71  mov     [rsp+21B0h+var_2180], rax; struct PROTOCOL_BINDING_TABLE **
0x18005ab76  lea     r9, [rsp+21B0h+var_2160]; struct SITE_DATA_OBJECT_TABLE_APPHOST **
0x18005ab7b  lea     rax, [rsp+21B0h+var_2150]
0x18005ab80  mov     [rsp+21B0h+var_2188], rax; struct PROTOCOL_DATA_OBJECT_TABLE_APPHOST **
0x18005ab85  lea     r8, [rsp+21B0h+var_2168]; struct APP_POOL_DATA_OBJECT_TABLE_APPHOST **
0x18005ab8a  lea     rax, [rsp+21B0h+var_2158]
0x18005ab8f  lea     rdx, [rsp+21B0h+var_2170]; struct GLOBAL_DATA_STORE_APPHOST **
0x18005ab94  mov     [rsp+21B0h+var_2190], rax; struct APPLICATION_DATA_OBJECT_TABLE_APPHOST **
0x18005ab99  call    ?CreateNewTables@CONFIG_APPHOST@@AEAAJPEAPEAVGLOBAL_DATA_STORE_APPHOST@@PEAPEAVAPP_POOL_DATA_OBJECT_TABLE_APPHOST@@PEAPEAVSITE_DATA_OBJECT_TABLE_APPHOST@@PEAPEAVAPPLICATION_DATA_OBJECT_TABLE_APPHOST@@PEAPEAVPROTOCOL_DATA_OBJECT_TABLE_APPHOST@@PEAPEAVPROTOCOL_BINDING_TABLE@@@Z; CONFIG_APPHOST::CreateNewTables(GLOBAL_DATA_STORE_APPHOST * *,APP_POOL_DATA_OBJECT_TABLE_APPHOST * *,SITE_DATA_OBJECT_TABLE_APPHOST * *,APPLICATION_DATA_OBJECT_TABLE_APPHOST * *,PROTOCOL_DATA_OBJECT_TABLE_APPHOST * *,PROTOCOL_BINDING_TABLE * *)
0x18005ab9e  mov     ebx, eax
0x18005aba0  test    eax, eax
0x18005aba2  jns     short loc_18005ABE8
0x18005aba4  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005abab  jz      short loc_18005ABDE
0x18005abad  mov     rcx, cs:g_pDebug
0x18005abb4  lea     rax, aFailedCreating_0; "Failed creating new tables\n"
0x18005abbb  mov     [rsp+21B0h+var_2188], rax
0x18005abc0  lea     r9, aConfigApphostR; "CONFIG_APPHOST::ReadDataFromStore"
0x18005abc7  mov     r8d, 17Ch
0x18005abcd  mov     dword ptr [rsp+21B0h+var_2190], ebx
0x18005abd1  lea     rdx, aServercommonIn_11; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18005abd8  call    cs:__imp_PuDbgPrintError
0x18005abde  mov     rdi, [rsp+21B0h+var_2170]
0x18005abe3  jmp     loc_18005AEF2
0x18005abe8  lea     rax, [rbp+20B0h+var_2120]
0x18005abec  mov     rcx, rsi; this
0x18005abef  mov     [rsp+21B0h+var_2188], rax; struct IEnumListenerAdapter **
0x18005abf4  lea     r9, [rsp+21B0h+var_2140]; struct IEnumSite **
0x18005abf9  lea     rax, [rbp+20B0h+var_2128]
0x18005abfd  lea     r8, [rbp+20B0h+var_2130]; struct ILogSettings **
0x18005ac01  mov     [rsp+21B0h+var_2190], rax; struct IEnumApplicationPool **
0x18005ac06  lea     rdx, [rsp+21B0h+var_2138]; struct IWebLimits **
0x18005ac0b  call    ?GetFreshSections@CONFIG_APPHOST@@AEAAJPEAPEAUIWebLimits@@PEAPEAUILogSettings@@PEAPEAUIEnumSite@@PEAPEAUIEnumApplicationPool@@PEAPEAUIEnumListenerAdapter@@@Z; CONFIG_APPHOST::GetFreshSections(IWebLimits * *,ILogSettings * *,IEnumSite * *,IEnumApplicationPool * *,IEnumListenerAdapter * *)
0x18005ac10  mov     r12, [rsp+21B0h+var_2138]
0x18005ac15  mov     ebx, eax
0x18005ac17  mov     r15, [rbp+20B0h+var_2130]
0x18005ac1b  mov     r13, [rbp+20B0h+var_2128]
0x18005ac1f  mov     r14, [rbp+20B0h+var_2120]
0x18005ac23  test    eax, eax
0x18005ac25  jns     short loc_18005AC6B
0x18005ac27  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005ac2e  jz      short loc_18005AC61
0x18005ac30  mov     rcx, cs:g_pDebug
0x18005ac37  lea     rax, aFailedGettingA; "Failed getting a section from the confi"...
0x18005ac3e  mov     [rsp+21B0h+var_2188], rax
0x18005ac43  lea     r9, aConfigApphostR; "CONFIG_APPHOST::ReadDataFromStore"
0x18005ac4a  mov     r8d, 18Ch
0x18005ac50  mov     dword ptr [rsp+21B0h+var_2190], ebx
0x18005ac54  lea     rdx, aServercommonIn_11; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18005ac5b  call    cs:__imp_PuDbgPrintError
0x18005ac61  mov     rdi, [rsp+21B0h+var_2170]
0x18005ac66  jmp     loc_18005AE8A
0x18005ac6b  mov     rdi, [rsp+21B0h+var_2170]
0x18005ac70  mov     r8, r15; struct ILogSettings *
0x18005ac73  mov     rcx, rdi; this
0x18005ac76  mov     rdx, r12; struct IWebLimits *
0x18005ac79  call    ?ReadFromAppHostProvider@GLOBAL_DATA_STORE_APPHOST@@QEAAJPEAUIWebLimits@@PEAUILogSettings@@@Z; GLOBAL_DATA_STORE_APPHOST::ReadFromAppHostProvider(IWebLimits *,ILogSettings *)
0x18005ac7e  mov     ebx, eax
0x18005ac80  test    eax, eax
0x18005ac82  jns     short loc_18005ACCA
0x18005ac84  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005ac8b  jz      short loc_18005ACBE
0x18005ac8d  lea     rax, aFailedToLoadTh_1; "Failed to load the global store\n"
0x18005ac94  mov     r8d, 19Ah
0x18005ac9a  mov     rcx, cs:g_pDebug
0x18005aca1  lea     r9, aConfigApphostR; "CONFIG_APPHOST::ReadDataFromStore"
0x18005aca8  mov     [rsp+21B0h+var_2188], rax
0x18005acad  lea     rdx, aServercommonIn_11; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18005acb4  mov     dword ptr [rsp+21B0h+var_2190], ebx
0x18005acb8  call    cs:__imp_PuDbgPrintError
0x18005acbe  mov     ecx, ebx; unsigned int
0x18005acc0  call    ?WriteEventLogConfigError@CONFIG_APPHOST@@SAXJ@Z; CONFIG_APPHOST::WriteEventLogConfigError(long)
0x18005acc5  jmp     loc_18005AE8A
0x18005acca  mov     rcx, [rsp+21B0h+var_2150]; this
0x18005accf  mov     rdx, r14; struct IEnumListenerAdapter *
0x18005acd2  call    ?ReadFromAppHostProvider@PROTOCOL_DATA_OBJECT_TABLE_APPHOST@@QEAAJPEAUIEnumListenerAdapter@@@Z; PROTOCOL_DATA_OBJECT_TABLE_APPHOST::ReadFromAppHostProvider(IEnumListenerAdapter *)
0x18005acd7  mov     ebx, eax
0x18005acd9  test    eax, eax
0x18005acdb  jns     short loc_18005ACF5
0x18005acdd  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005ace4  jz      short loc_18005ACBE
0x18005ace6  lea     rax, aFailedToLoadTh; "Failed to load the protocol info\n"
0x18005aced  mov     r8d, 1A9h
0x18005acf3  jmp     short loc_18005AC9A
0x18005acf5  mov     eax, [rsi+8]
0x18005acf8  lea     r9, [rbp+20B0h+var_20B0]
0x18005acfc  mov     r11, [rsp+21B0h+var_2160]
0x18005ad01  neg     eax
0x18005ad03  mov     r8, [rsp+21B0h+var_2158]
0x18005ad08  lea     rax, [rbp+20B0h+var_20E8]
0x18005ad0c  sbb     rdx, rdx
0x18005ad0f  xor     ecx, ecx
0x18005ad11  and     rdx, rax
0x18005ad14  cmp     [rsi+8], ecx
0x18005ad17  mov     r10, [r11]
0x18005ad1a  setnz   cl
0x18005ad1d  mov     [rsp+21B0h+var_2188], rdx
0x18005ad22  mov     rdx, [rsp+21B0h+var_2140]
0x18005ad27  mov     dword ptr [rsp+21B0h+var_2190], ecx
0x18005ad2b  mov     rcx, r11
0x18005ad2e  mov     rax, [r10+10h]
0x18005ad32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ad37  mov     ebx, eax
0x18005ad39  test    eax, eax
0x18005ad3b  jns     short loc_18005AD5C
0x18005ad3d  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005ad44  jz      loc_18005ACBE
0x18005ad4a  lea     rax, aFailedToLoadTh_2; "Failed to load the site info\n"
0x18005ad51  mov     r8d, 1BFh
0x18005ad57  jmp     loc_18005AC9A
0x18005ad5c  mov     eax, [rsi+8]
0x18005ad5f  mov     rdx, r13
0x18005ad62  mov     rcx, [rsp+21B0h+var_2168]
0x18005ad67  neg     eax
0x18005ad69  lea     rax, [rbp+20B0h+var_20E8]
0x18005ad6d  sbb     r9, r9
0x18005ad70  xor     r8d, r8d
0x18005ad73  and     r9, rax
0x18005ad76  mov     r10, [rcx]
0x18005ad79  cmp     [rsi+8], r8d
0x18005ad7d  setnz   r8b
0x18005ad81  mov     rax, [r10+10h]
0x18005ad85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ad8a  mov     ebx, eax
0x18005ad8c  xor     eax, eax
0x18005ad8e  test    ebx, ebx
0x18005ad90  jns     short loc_18005ADB1
0x18005ad92  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005ad99  jz      loc_18005ACBE
0x18005ad9f  lea     rax, aFailedToLoadTh_0; "Failed to load the app pool info\n"
0x18005ada6  mov     r8d, 1D2h
0x18005adac  jmp     loc_18005AC9A
0x18005adb1  cmp     [rsi+8], eax
0x18005adb4  jz      short loc_18005ADB9
0x18005adb6  mov     [rsi+8], eax
0x18005adb9  cmp     [rbp+20B0h+var_2118], rax
0x18005adbd  jz      short loc_18005ADFC
0x18005adbf  mov     rcx, [rsi+28h]
0x18005adc3  mov     rax, [rcx]
0x18005adc6  mov     rax, [rax+8]
0x18005adca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005adcf  mov     rcx, [rsp+21B0h+var_2148]; this
0x18005add4  mov     rax, [rsi+28h]
0x18005add8  mov     [rcx+438h], rax
0x18005addf  lea     rax, [rcx+880h]
0x18005ade6  mov     [rcx+878h], rax
0x18005aded  call    ?PopulateNoLock@PROTOCOL_BINDING_TABLE@@QEAAJXZ; PROTOCOL_BINDING_TABLE::PopulateNoLock(void)
0x18005adf2  mov     ebx, eax
0x18005adf4  test    eax, eax
0x18005adf6  js      loc_18005AE8A
0x18005adfc  mov     rax, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x18005ae03  cmp     dword ptr [rax+670h], 0
0x18005ae0a  jnz     short loc_18005AE1B
0x18005ae0c  lea     rcx, [rbp+20B0h+var_20B0]; this
0x18005ae10  call    ?Write@BINDING_INFO_WRITER@@QEAAJXZ; BINDING_INFO_WRITER::Write(void)
0x18005ae15  mov     ebx, eax
0x18005ae17  test    eax, eax
0x18005ae19  js      short loc_18005AE8A
0x18005ae1b  mov     rax, [rsp+21B0h+var_2168]
0x18005ae20  mov     rcx, [rbp+20B0h+var_2110]
0x18005ae24  mov     [rsp+21B0h+var_2168], 0
0x18005ae2d  mov     [rcx], rax
0x18005ae30  mov     rax, [rsp+21B0h+var_2160]
0x18005ae35  mov     rcx, [rbp+20B0h+var_2108]
0x18005ae39  mov     [rsp+21B0h+var_2160], 0
0x18005ae42  mov     [rcx], rax
0x18005ae45  mov     rax, [rsp+21B0h+var_2158]
0x18005ae4a  mov     rcx, [rbp+20B0h+var_2100]
0x18005ae4e  mov     [rsp+21B0h+var_2158], 0
0x18005ae57  mov     [rcx], rax
0x18005ae5a  mov     rax, [rbp+20B0h+var_20F8]
0x18005ae5e  mov     rcx, [rbp+20B0h+var_20F0]
0x18005ae62  mov     [rax], rdi
0x18005ae65  xor     edi, edi
0x18005ae67  mov     rax, [rsp+21B0h+var_2150]
0x18005ae6c  mov     [rcx], rax
0x18005ae6f  mov     rcx, [rbp+20B0h+var_2118]
0x18005ae73  mov     [rsp+21B0h+var_2150], rdi
0x18005ae78  test    rcx, rcx
0x18005ae7b  jz      short loc_18005AE8A
0x18005ae7d  mov     rax, [rsp+21B0h+var_2148]
0x18005ae82  mov     [rcx], rax
0x18005ae85  mov     [rsp+21B0h+var_2148], rdi
0x18005ae8a  test    r12, r12
0x18005ae8d  jz      short loc_18005AE9F
0x18005ae8f  mov     rax, [r12]
0x18005ae93  mov     rcx, r12
0x18005ae96  mov     rax, [rax+10h]
0x18005ae9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ae9f  test    r15, r15
0x18005aea2  jz      short loc_18005AEB3
0x18005aea4  mov     rax, [r15]
0x18005aea7  mov     rcx, r15
0x18005aeaa  mov     rax, [rax+10h]
0x18005aeae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aeb3  mov     rcx, [rsp+21B0h+var_2140]
0x18005aeb8  test    rcx, rcx
0x18005aebb  jz      short loc_18005AEC9
0x18005aebd  mov     rax, [rcx]
0x18005aec0  mov     rax, [rax+10h]
0x18005aec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aec9  test    r13, r13
0x18005aecc  jz      short loc_18005AEDE
0x18005aece  mov     rax, [r13+0]
0x18005aed2  mov     rcx, r13
0x18005aed5  mov     rax, [rax+10h]
0x18005aed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aede  test    r14, r14
0x18005aee1  jz      short loc_18005AEF2
0x18005aee3  mov     rax, [r14]
0x18005aee6  mov     rcx, r14
0x18005aee9  mov     rax, [rax+10h]
0x18005aeed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aef2  mov     rcx, [rsp+21B0h+var_2168]
0x18005aef7  mov     esi, 1
0x18005aefc  test    rcx, rcx
0x18005aeff  jz      short loc_18005AF0E
0x18005af01  mov     rax, [rcx]
0x18005af04  mov     edx, esi
0x18005af06  mov     rax, [rax]
0x18005af09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005af0e  mov     r11, [rsp+21B0h+var_2160]
0x18005af13  test    r11, r11
0x18005af16  jz      short loc_18005AF28
0x18005af18  mov     rax, [r11]
0x18005af1b  mov     edx, esi
0x18005af1d  mov     rcx, r11
0x18005af20  mov     rax, [rax]
0x18005af23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005af28  mov     rcx, [rsp+21B0h+var_2158]
0x18005af2d  test    rcx, rcx
0x18005af30  jz      short loc_18005AF3F
0x18005af32  mov     rax, [rcx]
0x18005af35  mov     edx, esi
0x18005af37  mov     rax, [rax]
0x18005af3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005af3f  test    rdi, rdi
0x18005af42  jz      short loc_18005AF54
0x18005af44  mov     rax, [rdi]
0x18005af47  mov     edx, esi
0x18005af49  mov     rcx, rdi
0x18005af4c  mov     rax, [rax]
0x18005af4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005af54  mov     rcx, [rsp+21B0h+var_2150]
0x18005af59  test    rcx, rcx
0x18005af5c  jz      short loc_18005AF6B
0x18005af5e  mov     rax, [rcx]
0x18005af61  mov     edx, esi
0x18005af63  mov     rax, [rax]
0x18005af66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005af6b  mov     rcx, [rsp+21B0h+var_2148]; this
0x18005af70  test    rcx, rcx
  ... truncated ...
```
