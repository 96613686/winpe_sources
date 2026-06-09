# APP_POOL::SetConfiguration(APP_POOL_DATA_OBJECT *,int)

- ea: `0x180019e7c`
- end: `0x18001a422`
- name: `?SetConfiguration@APP_POOL@@QEAAJPEAVAPP_POOL_DATA_OBJECT@@H@Z`
- size: `1446`
- prototype: `__int64 __fastcall(APP_POOL *__hidden this, struct APP_POOL_DATA_OBJECT *, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000f608`
- `0x1800184ac`

## callees

- `0x180001234`
- `0x180005878`
- `0x180018110`
- `0x1800181ac`
- `0x18001884c`
- `0x180019140`
- `0x180019e7c`
- `0x18001a428`
- `0x180024708`
- `0x180035a64`
- `0x180036614`
- `0x18005543c`
- `0x18005f32c`
- `0x180061060`
- `0x180062010`

## import_xrefs

- `msvcrt!_ultow` at `0x18001a17c`
- `msvcrt!_ultow` at `0x18001a17c`
- `iisutil!PuDbgPrint` at `0x180019f1c`
- `iisutil!PuDbgPrint` at `0x180019f70`
- `iisutil!PuDbgPrint` at `0x18001a328`
- `iisutil!PuDbgPrint` at `0x180019f1c`
- `iisutil!PuDbgPrint` at `0x180019f70`
- `iisutil!PuDbgPrint` at `0x18001a328`
- `iisutil!PuDbgPrintError` at `0x18001a12a`
- `iisutil!PuDbgPrintError` at `0x18001a3c9`
- `iisutil!PuDbgPrintError` at `0x18001a12a`
- `iisutil!PuDbgPrintError` at `0x18001a3c9`

## string_xrefs

- `0x180019edb`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\app_pool.cxx`
- `0x18001a123`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\app_pool.cxx`
- `0x18001a301`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\app_pool.cxx`
- `0x180019f0b`: `New configuration for app pool (ptr: %p; id: %S)\n`
- `0x180019ed4`: `APP_POOL::SetConfiguration`
- `0x18001a111`: `APP_POOL::SetConfiguration`
- `0x18001a2f3`: `APP_POOL::SetConfiguration`
- `0x180019f5f`: `Got good config! (ptr: %p; id: %S)\n`
- `0x18001a3ad`: `Allocating memory for configuration failed\n`
- `0x18001a105`: `Failed to create PROCESS_STARTUP_FACTORY instance.\n`
- `0x18001a317`: `New ContinueConfigUpdate work item (ptr: %p; id: %S; WPChange: %d)\n`

## pseudocode

```c
__int64 __fastcall APP_POOL::SetConfiguration(APP_POOL *this, struct APP_POOL_DATA_OBJECT *a2, int a3)
{
  int v6; // edx
  const wchar_t **v7; // r12
  APP_POOL_CONFIG_STORE *v8; // rax
  APP_POOL_CONFIG_STORE *v9; // rax
  APP_POOL_CONFIG_STORE *v10; // rbx
  __int64 v11; // rcx
  int v12; // eax
  HANDLE *v13; // rcx
  int v14; // r13d
  HANDLE *v15; // rcx
  int v16; // edx
  __int64 v17; // rcx
  int v18; // eax
  int v19; // eax
  int Instance; // r15d
  void (__fastcall ***v21)(_QWORD, __int64); // rcx
  unsigned int v22; // ecx
  unsigned __int16 *v23; // rbx
  signed int IsWow64W3WPAvailable; // eax
  int v25; // ebx
  int v26; // ebx
  _QWORD *v27; // rax
  char *v28; // rdx
  char *v29; // rdi
  char **v30; // rax
  unsigned __int16 *v31; // [rsp+40h] [rbp-40h] BYREF
  int v32; // [rsp+48h] [rbp-38h] BYREF
  int v33; // [rsp+4Ch] [rbp-34h] BYREF
  unsigned __int16 *v34[2]; // [rsp+50h] [rbp-30h] BYREF
  wchar_t Buffer[12]; // [rsp+60h] [rbp-20h] BYREF

  LODWORD(v31) = a3;
  v33 = 0;
  if ( !a2 )
    return 2147942487LL;
  v6 = g_dwDebugFlags;
  v7 = (const wchar_t **)((char *)this + 56);
  if ( (g_dwDebugFlags & 0x30000) != 0 && (g_dwDebugFlags & 3) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool.cxx",
      1207,
      "APP_POOL::SetConfiguration",
      "New configuration for app pool (ptr: %p; id: %S)\n",
      this,
      *v7);
    v6 = g_dwDebugFlags;
  }
  *((_DWORD *)this + 110) = 0;
  if ( (v6 & 3) != 0 && v6 < 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool.cxx",
      1221,
      "APP_POOL::SetConfiguration",
      "Got good config! (ptr: %p; id: %S)\n",
      this,
      *v7);
  v8 = (APP_POOL_CONFIG_STORE *)operator new(0x2F8u);
  if ( v8 && (v9 = APP_POOL_CONFIG_STORE::APP_POOL_CONFIG_STORE(v8), (v10 = v9) != 0) )
  {
    APP_POOL_CONFIG_STORE::Initialize(v9, a2, this);
    v11 = *((_QWORD *)this + 11);
    *((_QWORD *)this + 12) = v11;
    *((_QWORD *)this + 11) = v10;
    v12 = *((_DWORD *)a2 + 254);
    if ( (v12 & 0x40000000) != 0
      || *((_DWORD *)a2 + 144) == 3 && (v12 & 0x6000000) != 0
      || (v12 & 0x38000000) != 0
      || ((v13 = *(HANDLE **)(v11 + 184), v14 = 0, !v13) || !TOKEN_CACHE_ENTRY::QueryPrimaryToken(v13))
      && (v15 = *(HANDLE **)(*((_QWORD *)this + 11) + 184LL)) != 0
      && TOKEN_CACHE_ENTRY::QueryPrimaryToken(v15) )
    {
      ++*((_DWORD *)this + 83);
      v14 = 1;
    }
    APP_POOL::SetConfigurationForProtocolPools(this, a2, v14);
    v17 = *((_QWORD *)this + 12);
    if ( v17 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      *((_QWORD *)this + 12) = 0;
    }
    if ( (*((_BYTE *)a2 + 1020) & 3) != 0 || (v18 = *((_DWORD *)a2 + 254), v18 < 0) || (v18 & 0x1C08) != 0 )
      APP_POOL::HandleJobObjectChanges(this, *((struct APP_POOL_CONFIG_STORE **)this + 11), &v33);
    v19 = *((_DWORD *)a2 + 254);
    if ( (v19 & 0x3020) == 0 )
    {
      Instance = 0;
      if ( (v19 & 0x4000) == 0 )
        goto LABEL_31;
    }
    v21 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 64);
    if ( v21 )
    {
      (**v21)(v21, 1);
      *((_QWORD *)this + 64) = 0;
    }
    Instance = PROCESS_STARTUP_FACTORY::CreateInstance(
                 *(_DWORD *)(*((_QWORD *)this + 11) + 220LL) > 1u,
                 v16,
                 (__int64)g_pWebAdminService + 632,
                 *(_DWORD *)(*((_QWORD *)this + 11) + 244LL),
                 *(_DWORD *)(*((_QWORD *)this + 11) + 248LL),
                 (_QWORD *)this + 64);
    if ( Instance < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool.cxx",
          1346,
          "APP_POOL::SetConfiguration",
          Instance,
          "Failed to create PROCESS_STARTUP_FACTORY instance.\n");
    }
    else
    {
LABEL_31:
      if ( (*((_DWORD *)a2 + 255) & 0x4800) != 0 )
        *((_DWORD *)this + 126) = 0;
      if ( (*((_BYTE *)a2 + 1020) & 4) != 0 )
      {
        v22 = *((_DWORD *)a2 + 148);
        if ( v22 - 1 <= 1 )
        {
          APP_POOL::ProcessStateChangeCommand((__int64)this, v22, 1, 2, 0);
        }
        else
        {
          v23 = (unsigned __int16 *)*v7;
          *(_OWORD *)v34 = 0;
          _ultow(v22, Buffer, 10);
          v34[0] = v23;
          v34[1] = Buffer;
          WEB_ADMIN_SERVICE::LogEvent(g_pWebAdminService, 0x800013B2, 2u, (const unsigned __int16 **const)v34, 0);
        }
      }
      if ( (unsigned int)APP_POOL::IsIdentityAllowed(*((_DWORD *)a2 + 144)) )
      {
        if ( !*(_DWORD *)(*((_QWORD *)this + 11) + 400LL)
          || (v32 = 0,
              IsWow64W3WPAvailable = WORKER_PROCESS::IsWow64W3WPAvailable(&v32),
              v25 = IsWow64W3WPAvailable,
              IsWow64W3WPAvailable >= 0)
          && v32 )
        {
          v26 = 0;
          if ( !(_DWORD)v31
            && !*((_DWORD *)g_pWebAdminService + 412)
            && ((*((_DWORD *)a2 + 254) & 0x6FFDF7) != 0 || (*((_DWORD *)a2 + 255) & 0x6FF800) != 0 || v33 || v14) )
          {
            v26 = 1;
          }
          if ( *((_DWORD *)g_pWebAdminService + 457) == 1 && (*((_DWORD *)this + 30) || *((_DWORD *)this + 88) == 1) )
          {
            if ( (g_dwDebugFlags & 3) != 0 && g_dwDebugFlags < 0 )
              PuDbgPrint(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool.cxx",
                1517,
                "APP_POOL::SetConfiguration",
                "New ContinueConfigUpdate work item (ptr: %p; id: %S; WPChange: %d)\n",
                this,
                *v7,
                v26);
            v27 = operator new(0x40u);
            if ( v27 )
            {
              v27[1] = 0;
              v28 = (char *)(v27 + 6);
              v27[2] = 0;
              v29 = (char *)this + 360;
              v27[3] = 0;
              v27[4] = 0;
              *(_DWORD *)v27 = 2;
              *((_DWORD *)v27 + 10) = v26;
              v27[6] = 0;
              v27[7] = 0;
              v30 = (char **)*((_QWORD *)v29 + 1);
              if ( *v30 != v29 )
                __fastfail(3u);
              *(_QWORD *)v28 = v29;
              *((_QWORD *)v28 + 1) = v30;
              *v30 = v28;
              *((_QWORD *)v29 + 1) = v28;
            }
          }
          else if ( v26 )
          {
            APP_POOL::HandleConfigChangeAffectingWorkerProcesses(this);
          }
        }
        else
        {
          v31 = (unsigned __int16 *)*v7;
          WEB_ADMIN_SERVICE::LogEvent(
            g_pWebAdminService,
            0xC000144E,
            1u,
            (const unsigned __int16 **const)&v31,
            IsWow64W3WPAvailable);
          APP_POOL::ProcessStateChangeCommand((__int64)this, 2, 0, 2, v25);
        }
      }
      else
      {
        v31 = (unsigned __int16 *)*((_QWORD *)a2 + 10);
        WEB_ADMIN_SERVICE::LogEvent(g_pWebAdminService, 0xC000144F, 1u, (const unsigned __int16 **const)&v31, 0);
        APP_POOL::ProcessStateChangeCommand((__int64)this, 2, 0, 2, Instance);
      }
    }
    return 0;
  }
  else
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool.cxx",
        1233,
        "APP_POOL::SetConfiguration",
        -2147024888,
        "Allocating memory for configuration failed\n");
    v31 = (unsigned __int16 *)*((_QWORD *)a2 + 10);
    WEB_ADMIN_SERVICE::LogEvent(g_pWebAdminService, 0xC00013DD, 1u, (const unsigned __int16 **const)&v31, 0x80070008);
    return 2147942408LL;
  }
}

```

## disassembly

```asm
0x180019e7c  mov     [rsp-38h+arg_10], rbx
0x180019e81  push    rbp
0x180019e82  push    rsi
0x180019e83  push    rdi
0x180019e84  push    r12
0x180019e86  push    r13
0x180019e88  push    r14
0x180019e8a  push    r15
0x180019e8c  mov     rbp, rsp
0x180019e8f  sub     rsp, 80h
0x180019e96  mov     rax, cs:__security_cookie
0x180019e9d  xor     rax, rsp
0x180019ea0  mov     [rbp+var_8], rax
0x180019ea4  mov     dword ptr [rbp+var_40], r8d
0x180019ea8  mov     rsi, rdx
0x180019eab  mov     [rbp+var_34], 0
0x180019eb2  mov     rdi, rcx
0x180019eb5  test    rdx, rdx
0x180019eb8  jnz     short loc_180019EC4
0x180019eba  mov     eax, 80070057h
0x180019ebf  jmp     loc_18001A3FB
0x180019ec4  mov     edx, cs:g_dwDebugFlags
0x180019eca  lea     r12, [rcx+38h]
0x180019ece  test    edx, 30000h
0x180019ed4  lea     r14, aAppPoolSetconf; "APP_POOL::SetConfiguration"
0x180019edb  lea     r15, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180019ee2  setnz   cl
0x180019ee5  test    dl, 3
0x180019ee8  setnz   al
0x180019eeb  test    al, cl
0x180019eed  jz      short loc_180019F28
0x180019eef  mov     rax, [r12]
0x180019ef3  mov     r9, r14
0x180019ef6  mov     rcx, cs:g_pDebug
0x180019efd  mov     r8d, 4B7h
0x180019f03  mov     [rsp+80h+var_50], rax
0x180019f08  mov     rdx, r15
0x180019f0b  lea     rax, aNewConfigurati; "New configuration for app pool (ptr: %p"...
0x180019f12  mov     [rsp+80h+var_58], rdi
0x180019f17  mov     qword ptr [rsp+80h+var_60], rax
0x180019f1c  call    cs:__imp_PuDbgPrint
0x180019f22  mov     edx, cs:g_dwDebugFlags
0x180019f28  test    dl, 3
0x180019f2b  mov     dword ptr [rdi+1B8h], 0
0x180019f35  setnz   cl
0x180019f38  bt      edx, 1Fh
0x180019f3c  setb    al
0x180019f3f  test    al, cl
0x180019f41  jz      short loc_180019F76
0x180019f43  mov     rax, [r12]
0x180019f47  mov     r9, r14
0x180019f4a  mov     rcx, cs:g_pDebug
0x180019f51  mov     r8d, 4C5h
0x180019f57  mov     [rsp+80h+var_50], rax
0x180019f5c  mov     rdx, r15
0x180019f5f  lea     rax, aGotGoodConfigP; "Got good config! (ptr: %p; id: %S)\n"
0x180019f66  mov     [rsp+80h+var_58], rdi
0x180019f6b  mov     qword ptr [rsp+80h+var_60], rax
0x180019f70  call    cs:__imp_PuDbgPrint
0x180019f76  mov     ecx, 2F8h; Size
0x180019f7b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019f80  test    rax, rax
0x180019f83  jz      loc_18001A398
0x180019f89  mov     rcx, rax; this
0x180019f8c  call    ??0APP_POOL_CONFIG_STORE@@QEAA@XZ; APP_POOL_CONFIG_STORE::APP_POOL_CONFIG_STORE(void)
0x180019f91  mov     rbx, rax
0x180019f94  test    rax, rax
0x180019f97  jz      loc_18001A398
0x180019f9d  mov     r8, rdi; struct APP_POOL *
0x180019fa0  mov     rdx, rsi; struct APP_POOL_DATA_OBJECT *
0x180019fa3  mov     rcx, rax; this
0x180019fa6  call    ?Initialize@APP_POOL_CONFIG_STORE@@QEAAXPEAVAPP_POOL_DATA_OBJECT@@PEAVAPP_POOL@@@Z; APP_POOL_CONFIG_STORE::Initialize(APP_POOL_DATA_OBJECT *,APP_POOL *)
0x180019fab  mov     rcx, [rdi+58h]
0x180019faf  mov     r14d, 1
0x180019fb5  mov     [rdi+60h], rcx
0x180019fb9  mov     [rdi+58h], rbx
0x180019fbd  mov     eax, [rsi+3F8h]
0x180019fc3  bt      eax, 1Eh
0x180019fc7  jb      short loc_18001A013
0x180019fc9  cmp     dword ptr [rsi+240h], 3
0x180019fd0  jnz     short loc_180019FD9
0x180019fd2  test    eax, 6000000h
0x180019fd7  jnz     short loc_18001A013
0x180019fd9  test    eax, 38000000h
0x180019fde  jnz     short loc_18001A013
0x180019fe0  mov     rcx, [rcx+0B8h]; this
0x180019fe7  xor     r13d, r13d
0x180019fea  test    rcx, rcx
0x180019fed  jz      short loc_180019FF9
0x180019fef  call    ?QueryPrimaryToken@TOKEN_CACHE_ENTRY@@QEAAPEAXXZ; TOKEN_CACHE_ENTRY::QueryPrimaryToken(void)
0x180019ff4  test    rax, rax
0x180019ff7  jnz     short loc_18001A01D
0x180019ff9  mov     rax, [rdi+58h]
0x180019ffd  mov     rcx, [rax+0B8h]; this
0x18001a004  test    rcx, rcx
0x18001a007  jz      short loc_18001A01D
0x18001a009  call    ?QueryPrimaryToken@TOKEN_CACHE_ENTRY@@QEAAPEAXXZ; TOKEN_CACHE_ENTRY::QueryPrimaryToken(void)
0x18001a00e  test    rax, rax
0x18001a011  jz      short loc_18001A01D
0x18001a013  add     [rdi+14Ch], r14d
0x18001a01a  mov     r13d, r14d
0x18001a01d  mov     r8d, r13d; int
0x18001a020  mov     rdx, rsi; struct APP_POOL_DATA_OBJECT *
0x18001a023  mov     rcx, rdi; this
0x18001a026  call    ?SetConfigurationForProtocolPools@APP_POOL@@AEAAXPEAVAPP_POOL_DATA_OBJECT@@H@Z; APP_POOL::SetConfigurationForProtocolPools(APP_POOL_DATA_OBJECT *,int)
0x18001a02b  mov     rcx, [rdi+60h]
0x18001a02f  test    rcx, rcx
0x18001a032  jz      short loc_18001A048
0x18001a034  mov     rax, [rcx]
0x18001a037  mov     rax, [rax+10h]
0x18001a03b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a040  mov     qword ptr [rdi+60h], 0
0x18001a048  test    byte ptr [rsi+3FCh], 3
0x18001a04f  jnz     short loc_18001A062
0x18001a051  mov     eax, [rsi+3F8h]
0x18001a057  test    eax, eax
0x18001a059  js      short loc_18001A062
0x18001a05b  test    eax, 1C08h
0x18001a060  jz      short loc_18001A072
0x18001a062  mov     rdx, [rdi+58h]; struct APP_POOL_CONFIG_STORE *
0x18001a066  lea     r8, [rbp+var_34]; int *
0x18001a06a  mov     rcx, rdi; this
0x18001a06d  call    ?HandleJobObjectChanges@APP_POOL@@AEAAXPEAVAPP_POOL_CONFIG_STORE@@PEAH@Z; APP_POOL::HandleJobObjectChanges(APP_POOL_CONFIG_STORE *,int *)
0x18001a072  mov     eax, [rsi+3F8h]
0x18001a078  test    eax, 3020h
0x18001a07d  jnz     short loc_18001A08C
0x18001a07f  xor     r15d, r15d
0x18001a082  bt      eax, 0Eh
0x18001a086  jnb     loc_18001A135
0x18001a08c  lea     rbx, [rdi+200h]
0x18001a093  mov     rcx, [rbx]
0x18001a096  test    rcx, rcx
0x18001a099  jz      short loc_18001A0B0
0x18001a09b  mov     rax, [rcx]
0x18001a09e  mov     edx, r14d
0x18001a0a1  mov     rax, [rax]
0x18001a0a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0a9  mov     qword ptr [rbx], 0
0x18001a0b0  mov     r9, [rdi+58h]
0x18001a0b4  xor     ecx, ecx
0x18001a0b6  mov     r8, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x18001a0bd  add     r8, 278h
0x18001a0c4  mov     [rsp+80h+var_58], rbx
0x18001a0c9  cmp     [r9+0DCh], r14d
0x18001a0d0  mov     eax, [r9+0F8h]
0x18001a0d7  mov     r9d, [r9+0F4h]
0x18001a0de  setnbe  cl
0x18001a0e1  mov     [rsp+80h+var_60], eax
0x18001a0e5  call    ?CreateInstance@PROCESS_STARTUP_FACTORY@@SAJHKPEAVWAS_PROCESSOR_INFO@@W4NumaNodeAssignment@@W4NumaNodeAffinityMode@@PEAPEAV1@@Z; PROCESS_STARTUP_FACTORY::CreateInstance(int,ulong,WAS_PROCESSOR_INFO *,NumaNodeAssignment,NumaNodeAffinityMode,PROCESS_STARTUP_FACTORY * *)
0x18001a0ea  mov     r15d, eax
0x18001a0ed  test    eax, eax
0x18001a0ef  jns     short loc_18001A135
0x18001a0f1  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001a0f8  jz      loc_18001A394
0x18001a0fe  mov     rcx, cs:g_pDebug
0x18001a105  lea     rax, aFailedToCreate_9; "Failed to create PROCESS_STARTUP_FACTOR"...
0x18001a10c  mov     [rsp+80h+var_58], rax
0x18001a111  lea     r9, aAppPoolSetconf; "APP_POOL::SetConfiguration"
0x18001a118  mov     r8d, 542h
0x18001a11e  mov     [rsp+80h+var_60], r15d
0x18001a123  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001a12a  call    cs:__imp_PuDbgPrintError
0x18001a130  jmp     loc_18001A394
0x18001a135  test    dword ptr [rsi+3FCh], 4800h
0x18001a13f  jz      short loc_18001A14B
0x18001a141  mov     dword ptr [rdi+1F8h], 0
0x18001a14b  test    byte ptr [rsi+3FCh], 4
0x18001a152  mov     ebx, 2
0x18001a157  jz      short loc_18001A1CD
0x18001a159  mov     ecx, [rsi+250h]; Value
0x18001a15f  lea     eax, [rcx-1]
0x18001a162  cmp     eax, r14d
0x18001a165  jbe     short loc_18001A1B5
0x18001a167  mov     rbx, [r12]
0x18001a16b  lea     rdx, [rbp+Buffer]; Buffer
0x18001a16f  xorps   xmm0, xmm0
0x18001a172  mov     r8d, 0Ah; Radix
0x18001a178  movups  xmmword ptr [rbp+var_30], xmm0
0x18001a17c  call    cs:__imp__ultow
0x18001a182  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; this
0x18001a189  lea     rax, [rbp+Buffer]
0x18001a18d  mov     [rbp+var_30], rbx
0x18001a191  lea     r9, [rbp+var_30]; unsigned __int16 **
0x18001a195  mov     ebx, 2
0x18001a19a  mov     [rbp+var_30+8], rax
0x18001a19e  mov     r8d, ebx; unsigned __int16
0x18001a1a1  mov     [rsp+80h+var_60], 0; unsigned int
0x18001a1a9  mov     edx, 800013B2h; unsigned int
0x18001a1ae  call    ?LogEvent@WEB_ADMIN_SERVICE@@QEAAXKGQEAPEBGK@Z; WEB_ADMIN_SERVICE::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18001a1b3  jmp     short loc_18001A1CD
0x18001a1b5  mov     edx, ecx
0x18001a1b7  mov     [rsp+80h+var_60], 0
0x18001a1bf  mov     rcx, rdi
0x18001a1c2  mov     r9d, ebx
0x18001a1c5  mov     r8d, r14d
0x18001a1c8  call    ?ProcessStateChangeCommand@APP_POOL@@QEAAJKHW4HTTP_WRAPPER_PROTOCOL_APPPOOL_STATE_REASON@@J@Z; APP_POOL::ProcessStateChangeCommand(ulong,int,HTTP_WRAPPER_PROTOCOL_APPPOOL_STATE_REASON,long)
0x18001a1cd  mov     ecx, [rsi+240h]; unsigned int
0x18001a1d3  call    ?IsIdentityAllowed@APP_POOL@@SAHK@Z; APP_POOL::IsIdentityAllowed(ulong)
0x18001a1d8  test    eax, eax
0x18001a1da  jnz     short loc_18001A21E
0x18001a1dc  mov     rax, [rsi+50h]
0x18001a1e0  lea     r9, [rbp+var_40]; unsigned __int16 **
0x18001a1e4  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; this
0x18001a1eb  mov     r8d, r14d; unsigned __int16
0x18001a1ee  mov     edx, 0C000144Fh; unsigned int
0x18001a1f3  mov     [rbp+var_40], rax
0x18001a1f7  mov     [rsp+80h+var_60], 0; unsigned int
0x18001a1ff  call    ?LogEvent@WEB_ADMIN_SERVICE@@QEAAXKGQEAPEBGK@Z; WEB_ADMIN_SERVICE::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18001a204  mov     r9d, ebx
0x18001a207  mov     [rsp+80h+var_60], r15d
0x18001a20c  mov     edx, ebx
0x18001a20e  xor     r8d, r8d
0x18001a211  mov     rcx, rdi
0x18001a214  call    ?ProcessStateChangeCommand@APP_POOL@@QEAAJKHW4HTTP_WRAPPER_PROTOCOL_APPPOOL_STATE_REASON@@J@Z; APP_POOL::ProcessStateChangeCommand(ulong,int,HTTP_WRAPPER_PROTOCOL_APPPOOL_STATE_REASON,long)
0x18001a219  jmp     loc_18001A394
0x18001a21e  mov     rax, [rdi+58h]
0x18001a222  xor     r15d, r15d
0x18001a225  cmp     [rax+190h], r15d
0x18001a22c  jz      short loc_18001A27A
0x18001a22e  lea     rcx, [rbp+var_38]; int *
0x18001a232  mov     [rbp+var_38], r15d
0x18001a236  call    ?IsWow64W3WPAvailable@WORKER_PROCESS@@SAJPEAH@Z; WORKER_PROCESS::IsWow64W3WPAvailable(int *)
0x18001a23b  mov     ebx, eax
0x18001a23d  test    eax, eax
0x18001a23f  js      short loc_18001A247
0x18001a241  cmp     [rbp+var_38], r15d
0x18001a245  jnz     short loc_18001A27A
0x18001a247  mov     rcx, [r12]
0x18001a24b  lea     r9, [rbp+var_40]; unsigned __int16 **
0x18001a24f  mov     [rbp+var_40], rcx
0x18001a253  mov     r8d, r14d; unsigned __int16
0x18001a256  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; this
0x18001a25d  mov     edx, 0C000144Eh; unsigned int
0x18001a262  mov     [rsp+80h+var_60], ebx; unsigned int
0x18001a266  call    ?LogEvent@WEB_ADMIN_SERVICE@@QEAAXKGQEAPEBGK@Z; WEB_ADMIN_SERVICE::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18001a26b  mov     r9d, 2
0x18001a271  mov     [rsp+80h+var_60], ebx
0x18001a275  mov     edx, r9d
0x18001a278  jmp     short loc_18001A20E
0x18001a27a  mov     ebx, r15d
0x18001a27d  mov     rax, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x18001a284  cmp     dword ptr [rbp+var_40], r15d
0x18001a288  jnz     short loc_18001A2B9
0x18001a28a  cmp     [rax+670h], r15d
0x18001a291  jnz     short loc_18001A2B9
0x18001a293  test    dword ptr [rsi+3F8h], 6FFDF7h
0x18001a29d  jnz     short loc_18001A2B6
0x18001a29f  test    dword ptr [rsi+3FCh], 6FF800h
0x18001a2a9  jnz     short loc_18001A2B6
0x18001a2ab  cmp     [rbp+var_34], r15d
0x18001a2af  jnz     short loc_18001A2B6
0x18001a2b1  test    r13d, r13d
0x18001a2b4  jz      short loc_18001A2B9
0x18001a2b6  mov     ebx, r14d
0x18001a2b9  cmp     [rax+724h], r14d
0x18001a2c0  jnz     loc_18001A388
0x18001a2c6  cmp     [rdi+78h], r15d
0x18001a2ca  ja      short loc_18001A2D9
0x18001a2cc  cmp     [rdi+160h], r14d
0x18001a2d3  jnz     loc_18001A388
0x18001a2d9  mov     eax, cs:g_dwDebugFlags
0x18001a2df  test    al, 3
0x18001a2e1  setnz   cl
0x18001a2e4  bt      eax, 1Fh
0x18001a2e8  setb    al
0x18001a2eb  test    al, cl
0x18001a2ed  jz      short loc_18001A32E
0x18001a2ef  mov     rax, [r12]
0x18001a2f3  lea     r9, aAppPoolSetconf; "APP_POOL::SetConfiguration"
0x18001a2fa  mov     rcx, cs:g_pDebug
0x18001a301  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001a308  mov     [rsp+80h+var_48], ebx
0x18001a30c  mov     r8d, 5EDh
0x18001a312  mov     [rsp+80h+var_50], rax
0x18001a317  lea     rax, aNewContinuecon; "New ContinueConfigUpdate work item (ptr"...
0x18001a31e  mov     [rsp+80h+var_58], rdi
0x18001a323  mov     qword ptr [rsp+80h+var_60], rax
0x18001a328  call    cs:__imp_PuDbgPrint
0x18001a32e  mov     ecx, 40h ; '@'; Size
0x18001a333  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a338  test    rax, rax
0x18001a33b  jz      short loc_18001A394
0x18001a33d  mov     [rax+8], r15
0x18001a341  lea     rdx, [rax+30h]
0x18001a345  mov     [rax+10h], r15
0x18001a349  add     rdi, 168h
0x18001a350  mov     [rax+18h], r15
0x18001a354  mov     [rax+20h], r15
0x18001a358  mov     dword ptr [rax], 2
0x18001a35e  mov     [rax+28h], ebx
0x18001a361  mov     [rdx], r15
0x18001a364  mov     [rax+38h], r15
0x18001a368  mov     rax, [rdi+8]
0x18001a36c  cmp     [rax], rdi
0x18001a36f  jz      short loc_18001A378
0x18001a371  mov     ecx, 3
0x18001a376  int     29h; Win8: RtlFailFast(ecx)
0x18001a378  mov     [rdx], rdi
0x18001a37b  mov     [rdx+8], rax
0x18001a37f  mov     [rax], rdx
  ... truncated ...
```
