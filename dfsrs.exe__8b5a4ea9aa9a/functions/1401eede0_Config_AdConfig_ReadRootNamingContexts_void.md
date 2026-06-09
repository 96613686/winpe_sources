# Config::AdConfig::ReadRootNamingContexts(void)

- ea: `0x1401eede0`
- end: `0x1401ef5f7`
- name: `?ReadRootNamingContexts@AdConfig@Config@@IEAAPEAVFrsStatus@@XZ`
- size: `2071`
- prototype: `struct FrsStatus *__fastcall(Config::AdConfig *__hidden this)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1401e27a8`
- `0x1401e29c8`

## callees

- `0x1400036a0`
- `0x14000c910`
- `0x14000cd1c`
- `0x14001bf80`
- `0x14002179c`
- `0x140022d5c`
- `0x1401af7c0`
- `0x1401b9494`
- `0x1401de184`
- `0x1401de240`
- `0x1401de77c`
- `0x1401de7cc`
- `0x1401e44c8`
- `0x1401e4584`
- `0x1401e684c`
- `0x1401eede0`
- `0x1401f3320`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1401eeeaa`
- `KERNEL32!GetCurrentThreadId` at `0x1401eef54`
- `KERNEL32!GetCurrentThreadId` at `0x1401ef092`
- `KERNEL32!GetCurrentThreadId` at `0x1401ef1aa`
- `KERNEL32!GetCurrentThreadId` at `0x1401ef217`
- `KERNEL32!GetCurrentThreadId` at `0x1401ef526`
- `KERNEL32!GetCurrentThreadId` at `0x1401ef575`
- `KERNEL32!GetCurrentThreadId` at `0x1401eeeaa`
- `KERNEL32!GetCurrentThreadId` at `0x1401eef54`
- `KERNEL32!GetCurrentThreadId` at `0x1401ef092`
- `KERNEL32!GetCurrentThreadId` at `0x1401ef1aa`
- `KERNEL32!GetCurrentThreadId` at `0x1401ef217`
- `KERNEL32!GetCurrentThreadId` at `0x1401ef526`
- `KERNEL32!GetCurrentThreadId` at `0x1401ef575`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1401eefbc`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1401eefbc`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1401eefd5`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1401eefd5`

## string_xrefs

- `0x1401eefcb`: `cn=configuration`
- `0x1401eeec7`: `Config::AdConfig::ReadRootNamingContexts`
- `0x1401eef7e`: `Config::AdConfig::ReadRootNamingContexts`
- `0x1401ef1e0`: `Config::AdConfig::ReadRootNamingContexts`
- `0x1401ef543`: `Config::AdConfig::ReadRootNamingContexts`
- `0x1401eef1b`: `Config::AdConfig::ReadRootNamingContexts`
- `0x1401ef055`: `Config::AdConfig::ReadRootNamingContexts`
- `0x1401ef16c`: `Config::AdConfig::ReadRootNamingContexts`
- `0x1401ef271`: `Config::AdConfig::ReadRootNamingContexts`
- `0x1401ef4e3`: `Config::AdConfig::ReadRootNamingContexts`
- `0x1401ef0ed`: `cn=computers`
- `0x1401ef00a`: `cn=services`
- `0x1401ef3f3`: `Computers DN:%ws`
- `0x1401ef355`: `Services DN:%ws`
- `0x1401ef513`: `Failed to get RootDSE, check access rights`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct FrsStatus *__fastcall Config::AdConfig::ReadRootNamingContexts(Config::AdConfig *this)
{
  __int64 v2; // rbx
  struct FrsStatus *started; // r13
  __int64 v4; // rcx
  struct Config::AdAttr *Attr; // rax
  __int64 v6; // r9
  __int64 v7; // r8
  __int64 v8; // rdx
  unsigned int v9; // r14d
  _QWORD *v10; // r15
  _QWORD *v11; // rax
  char v12; // dl
  __int16 v13; // r8
  int v14; // r9d
  const wchar_t *v15; // r12
  wchar_t *v16; // rax
  Config::AdStrAttr *v17; // r15
  const unsigned __int16 *Value; // rax
  Config::AdStrAttr *v19; // rax
  const unsigned __int16 *v20; // rax
  DWORD v21; // eax
  __int64 v22; // rcx
  LPCRITICAL_SECTION v23; // rax
  DWORD v24; // eax
  __int64 v25; // rcx
  wchar_t v27; // [rsp+28h] [rbp-E0h]
  long double v28; // [rsp+30h] [rbp-D8h]
  int v29; // [rsp+38h] [rbp-D0h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C8h]
  unsigned __int16 *v31; // [rsp+48h] [rbp-C0h]
  wchar_t *v32; // [rsp+58h] [rbp-B0h] BYREF
  const wchar_t *v33; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v34; // [rsp+68h] [rbp-A0h]
  const wchar_t *v35; // [rsp+70h] [rbp-98h]
  const wchar_t *v36; // [rsp+78h] [rbp-90h] BYREF
  int v37; // [rsp+80h] [rbp-88h]
  int v38; // [rsp+84h] [rbp-84h]
  const wchar_t *v39; // [rsp+88h] [rbp-80h]
  const wchar_t *v40; // [rsp+90h] [rbp-78h] BYREF
  int v41; // [rsp+98h] [rbp-70h]
  int v42; // [rsp+9Ch] [rbp-6Ch]
  const wchar_t *v43; // [rsp+A0h] [rbp-68h]
  const wchar_t *v44; // [rsp+A8h] [rbp-60h] BYREF
  int v45; // [rsp+B0h] [rbp-58h]
  int v46; // [rsp+B4h] [rbp-54h]
  const wchar_t *v47; // [rsp+B8h] [rbp-50h]
  const wchar_t *v48; // [rsp+C0h] [rbp-48h] BYREF
  int v49; // [rsp+C8h] [rbp-40h]
  int v50; // [rsp+CCh] [rbp-3Ch]
  const wchar_t *v51; // [rsp+D0h] [rbp-38h]
  _BYTE v52[96]; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v53[368]; // [rsp+138h] [rbp+30h] BYREF
  unsigned __int16 *v54; // [rsp+2A8h] [rbp+1A0h] BYREF
  __int64 v55; // [rsp+2B0h] [rbp+1A8h]
  const wchar_t *v56; // [rsp+2B8h] [rbp+1B0h]

  v54 = L"namingContexts";
  v55 = (__int64)L"defaultNamingContext";
  v56 = L"schemaNamingContext";
  Config::AdQuery::AdQuery((Config::AdQuery *)v53);
  Config::AdObject::AdObject((Config::AdObject *)v52);
  v2 = 0;
  started = Config::AdQuery::StartSearch(
              (Config::AdQuery *)v53,
              *((struct Config::AdSession **)this + 5),
              &pServiceName,
              0,
              (const unsigned __int16 **)&v54,
              3u,
              0,
              0,
              L"(objectCategory=*)",
              0x8CA0u);
  if ( started )
  {
    v31 = (unsigned __int16 *)started;
    CurrentThreadId = GetCurrentThreadId();
    v29 = 7475;
LABEL_76:
    v6 = *(unsigned int *)started;
    v7 = *((unsigned int *)started + 2);
    v8 = *((unsigned int *)started + 1);
    goto LABEL_77;
  }
  if ( Config::AdQuery::GetFirstObject((Config::AdQuery *)v53, (struct Config::AdObject *)v52) )
  {
    Attr = Config::AdAttrList::FindAttr((Config::AdAttrList *)v52, L"namingContexts");
    if ( !Attr )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
      {
        v33 = L"Config::AdConfig::ReadRootNamingContexts";
        v34 = 0x200001D3CLL;
        v35 = L"CFAD";
        dbgobj::DbgPrint<unsigned short>(&v33, L"Missing namingContexts attribute");
      }
      v31 = 0;
      CurrentThreadId = GetCurrentThreadId();
      v29 = 7485;
      v6 = 1;
      goto LABEL_10;
    }
    v9 = 0;
    v10 = (_QWORD *)((char *)Attr + 40);
    while ( v9 < (unsigned int)((__int64)(v10[1] - *v10) >> 3) )
    {
      v11 = (_QWORD *)std::vector<ShutdownObject *>::at(v10, v9);
      v15 = (const wchar_t *)o(*v11, v12, v13, v14, v27, v28);
      v16 = wcsstr(v15, L"cn=configuration");
      if ( v16 && v16 == v15 )
      {
        v32 = v16;
        *((_QWORD *)this + 6) = Config::AdDn::Extend((Config::AdDn *)&v32, L"cn=sites");
        *((_QWORD *)this + 7) = Config::AdDn::Extend((Config::AdDn *)&v32, L"cn=services");
        operator delete[](0);
        break;
      }
      ++v9;
    }
    v17 = Config::AdAttrList::FindAttr((Config::AdAttrList *)v52, L"defaultNamingContext");
    if ( !v17 )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
      {
        v33 = L"Config::AdConfig::ReadRootNamingContexts";
        v34 = 0x200001D5BLL;
        v35 = L"CFAD";
        dbgobj::DbgPrint<unsigned short>(&v33, L"Missing defaultNamingContext attribute");
      }
      v31 = 0;
      CurrentThreadId = GetCurrentThreadId();
      v29 = 7516;
LABEL_23:
      v6 = 1;
LABEL_10:
      v7 = 0;
      v8 = 1168;
LABEL_77:
      v2 = FrsStatusList::PushNewError(
             v4,
             v8,
             v7,
             v6,
             "base\\fs\\remotefs\\frs\\src\\ad\\ad.cpp",
             "Config::AdConfig::ReadRootNamingContexts",
             v29,
             CurrentThreadId,
             v31);
      goto LABEL_78;
    }
    operator delete[](*((void **)this + 9));
    *((_QWORD *)this + 9) = 0;
    Value = Config::AdStrAttr::GetValue(v17);
    Config::AdDn::Set((Config::AdConfig *)((char *)this + 88), Value);
    if ( *((_QWORD *)this + 11) )
    {
      operator delete[](*((void **)this + 9));
      *((_QWORD *)this + 9) = 0;
      *((_QWORD *)this + 9) = Config::AdDn::Extend((Config::AdConfig *)((char *)this + 88), L"cn=computers");
      operator delete[](*((void **)this + 8));
      *((_QWORD *)this + 8) = 0;
      *((_QWORD *)this + 8) = Config::AdDn::Extend((Config::AdConfig *)((char *)this + 88), L"cn=system");
      operator delete[](*((void **)this + 10));
      *((_QWORD *)this + 10) = 0;
      *((_QWORD *)this + 10) = Config::AdDn::Extend((Config::AdConfig *)((char *)this + 88), L"ou=domain controllers");
    }
    v19 = Config::AdAttrList::FindAttr((Config::AdAttrList *)v52, L"schemaNamingContext");
    if ( !v19 )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
      {
        v33 = L"Config::AdConfig::ReadRootNamingContexts";
        v34 = 0x200001D7DLL;
        v35 = L"CFAD";
        dbgobj::DbgPrint<unsigned short>(&v33, L"(Ignored) Missing schemaNamingContext attribute");
      }
      v31 = 0;
      CurrentThreadId = GetCurrentThreadId();
      v29 = 7550;
      goto LABEL_23;
    }
    v20 = Config::AdStrAttr::GetValue(v19);
    Config::AdDn::Set((Config::AdConfig *)((char *)this + 96), v20);
    if ( !*((_QWORD *)this + 6)
      || !*((_QWORD *)this + 7)
      || !*((_QWORD *)this + 10)
      || !*((_QWORD *)this + 11)
      || !*((_QWORD *)this + 9)
      || !*((_QWORD *)this + 8)
      || !*((_QWORD *)this + 12) )
    {
      v21 = GetCurrentThreadId();
      started = (struct FrsStatus *)FrsStatusList::PushNewError(
                                      v22,
                                      1168,
                                      0,
                                      1,
                                      "base\\fs\\remotefs\\frs\\src\\ad\\ad.cpp",
                                      "Config::AdConfig::ReadRootNamingContexts",
                                      7561,
                                      v21,
                                      0);
    }
    if ( !_InterlockedCompareExchange(&dword_140319434, 1, 0) )
    {
      v23 = g_DebugLog;
      if ( g_DebugLog )
      {
        if ( LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
        {
          v33 = L"Config::AdConfig::ReadRootNamingContexts";
          v34 = 0x400001D8DLL;
          v35 = L"CFAD";
          v32 = (wchar_t *)*((_QWORD *)this + 11);
          dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v33, L"Default Naming Context DN:%ws", &v32);
          v23 = g_DebugLog;
        }
        if ( v23 )
        {
          if ( LODWORD(v23[1].LockSemaphore) && SLODWORD(v23[1].OwningThread) >= 4 )
          {
            v36 = L"Config::AdConfig::ReadRootNamingContexts";
            v37 = 7566;
            v38 = 4;
            v39 = L"CFAD";
            v32 = (wchar_t *)*((_QWORD *)this + 6);
            dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v36, L"Schema Naming Context DN:%ws", &v32);
            v23 = g_DebugLog;
          }
          if ( v23 )
          {
            if ( LODWORD(v23[1].LockSemaphore) && SLODWORD(v23[1].OwningThread) >= 4 )
            {
              v40 = L"Config::AdConfig::ReadRootNamingContexts";
              v41 = 7568;
              v42 = 4;
              v43 = L"CFAD";
              v32 = (wchar_t *)*((_QWORD *)this + 7);
              dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v40, L"Services DN:%ws", &v32);
              v23 = g_DebugLog;
            }
            if ( v23 )
            {
              if ( LODWORD(v23[1].LockSemaphore) && SLODWORD(v23[1].OwningThread) >= 4 )
              {
                v44 = L"Config::AdConfig::ReadRootNamingContexts";
                v45 = 7569;
                v46 = 4;
                v47 = L"CFAD";
                v32 = (wchar_t *)*((_QWORD *)this + 10);
                dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v44, L"Domain Controllers DN:%ws", &v32);
                v23 = g_DebugLog;
              }
              if ( v23 )
              {
                if ( LODWORD(v23[1].LockSemaphore) && SLODWORD(v23[1].OwningThread) >= 4 )
                {
                  v48 = L"Config::AdConfig::ReadRootNamingContexts";
                  v49 = 7570;
                  v50 = 4;
                  v51 = L"CFAD";
                  v32 = (wchar_t *)*((_QWORD *)this + 9);
                  dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v48, L"Computers DN:%ws", &v32);
                  v23 = g_DebugLog;
                }
                if ( v23 )
                {
                  if ( LODWORD(v23[1].LockSemaphore) && SLODWORD(v23[1].OwningThread) >= 4 )
                  {
                    v54 = L"Config::AdConfig::ReadRootNamingContexts";
                    v55 = 0x400001D93LL;
                    v56 = L"CFAD";
                    v32 = (wchar_t *)*((_QWORD *)this + 8);
                    dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v54, L"System DN:%ws", &v32);
                    v23 = g_DebugLog;
                  }
                  if ( v23 && LODWORD(v23[1].LockSemaphore) && SLODWORD(v23[1].OwningThread) >= 4 )
                  {
                    v54 = L"Config::AdConfig::ReadRootNamingContexts";
                    v55 = 0x400001D94LL;
                    v56 = L"CFAD";
                    v32 = (wchar_t *)*((_QWORD *)this + 6);
                    dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v54, L"Sites DN:%ws", &v32);
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
    {
      v54 = L"Config::AdConfig::ReadRootNamingContexts";
      v55 = 0x200001D9BLL;
      v56 = L"CFAD";
      dbgobj::DbgPrint<unsigned short>(&v54, L"Failed to get RootDSE, check access rights");
    }
    v24 = GetCurrentThreadId();
    started = (struct FrsStatus *)FrsStatusList::PushNewError(
                                    v25,
                                    5,
                                    0,
                                    1,
                                    "base\\fs\\remotefs\\frs\\src\\ad\\ad.cpp",
                                    "Config::AdConfig::ReadRootNamingContexts",
                                    7580,
                                    v24,
                                    0);
  }
  if ( started )
  {
    v31 = (unsigned __int16 *)started;
    CurrentThreadId = GetCurrentThreadId();
    v29 = 7583;
    goto LABEL_76;
  }
LABEL_78:
  Config::AdObject::~AdObject((Config::AdObject *)v52);
  Config::AdQuery::~AdQuery((Config::AdQuery *)v53);
  return (struct FrsStatus *)v2;
}

```

## disassembly

```asm
0x1401eede0  mov     rax, rsp
0x1401eede3  mov     [rax+10h], rbx
0x1401eede7  mov     [rax+18h], rsi
0x1401eedeb  mov     [rax+20h], rdi
0x1401eedef  push    rbp
0x1401eedf0  push    r12
0x1401eedf2  push    r13
0x1401eedf4  push    r14
0x1401eedf6  push    r15
0x1401eedf8  lea     rbp, [rax-1E8h]
0x1401eedff  sub     rsp, 2C0h
0x1401eee06  mov     rax, cs:__security_cookie
0x1401eee0d  xor     rax, rsp
0x1401eee10  mov     [rbp+1E0h+var_28], rax
0x1401eee17  mov     rdi, rcx
0x1401eee1a  lea     rsi, aNamingcontexts; "namingContexts"
0x1401eee21  mov     [rbp+1E0h+var_40], rsi
0x1401eee28  lea     rax, aDefaultnamingc; "defaultNamingContext"
0x1401eee2f  mov     [rbp+1E0h+var_38], rax
0x1401eee36  lea     r12, aSchemanamingco; "schemaNamingContext"
0x1401eee3d  mov     [rbp+1E0h+var_30], r12
0x1401eee44  lea     rcx, [rbp+1E0h+var_1B0]; this
0x1401eee48  call    ??0AdQuery@Config@@QEAA@XZ; Config::AdQuery::AdQuery(void)
0x1401eee4d  nop
0x1401eee4e  lea     rcx, [rbp+1E0h+var_210]; this
0x1401eee52  call    ??0AdObject@Config@@QEAA@XZ; Config::AdObject::AdObject(void)
0x1401eee57  nop
0x1401eee58  mov     [rsp+2E0h+var_298], 8CA0h; unsigned int
0x1401eee60  lea     rax, aObjectcategory_6; "(objectCategory=*)"
0x1401eee67  mov     [rsp+2E0h+var_2A0], rax; unsigned __int16 *
0x1401eee6c  xor     ebx, ebx
0x1401eee6e  mov     [rsp+2E0h+var_2A8], ebx; unsigned int
0x1401eee72  mov     [rsp+2E0h+var_2B0], rbx; unsigned __int16 **
0x1401eee77  mov     [rsp+2E0h+var_2B8], 3; unsigned int
0x1401eee7f  lea     rax, [rbp+1E0h+var_40]
0x1401eee86  mov     [rsp+2E0h+var_2C0], rax; unsigned __int16 **
0x1401eee8b  xor     r9d, r9d; unsigned int
0x1401eee8e  lea     r8, pServiceName; unsigned __int16 *
0x1401eee95  mov     rdx, [rdi+28h]; struct Config::AdSession *
0x1401eee99  lea     rcx, [rbp+1E0h+var_1B0]; this
0x1401eee9d  call    ?StartSearch@AdQuery@Config@@QEAAPEAVFrsStatus@@PEAVAdSession@2@PEBGKPEAPEBGK2K1K@Z; Config::AdQuery::StartSearch(Config::AdSession *,ushort const *,ulong,ushort const * *,ulong,ushort const * *,ulong,ushort const *,ulong)
0x1401eeea2  mov     r13, rax
0x1401eeea5  test    rax, rax
0x1401eeea8  jz      short loc_1401EEEDA
0x1401eeeaa  call    cs:__imp_GetCurrentThreadId
0x1401eeeb1  nop     dword ptr [rax+rax+00h]
0x1401eeeb6  mov     [rsp+2E0h+var_2A0], r13
0x1401eeebb  mov     [rsp+2E0h+var_2A8], eax
0x1401eeebf  mov     dword ptr [rsp+2E0h+var_2B0], 1D33h
0x1401eeec7  lea     r15, aConfigAdconfig_18; "Config::AdConfig::ReadRootNamingContext"...
0x1401eeece  lea     r12, aBaseFsRemotefs_10; "base\\fs\\remotefs\\frs\\src\\ad\\ad.cp"...
0x1401eeed5  jmp     loc_1401EF592
0x1401eeeda  lea     rdx, [rbp+1E0h+var_210]; struct Config::AdObject *
0x1401eeede  lea     rcx, [rbp+1E0h+var_1B0]; this
0x1401eeee2  call    ?GetFirstObject@AdQuery@Config@@QEAAHPEAVAdObject@2@@Z; Config::AdQuery::GetFirstObject(Config::AdObject *)
0x1401eeee7  test    eax, eax
0x1401eeee9  jz      loc_1401EF4CC
0x1401eeeef  mov     rdx, rsi; unsigned __int16 *
0x1401eeef2  lea     rcx, [rbp+1E0h+var_210]; this
0x1401eeef6  call    ?FindAttr@AdAttrList@Config@@QEBAPEAVAdAttr@2@PEBG@Z; Config::AdAttrList::FindAttr(ushort const *)
0x1401eeefb  test    rax, rax
0x1401eeefe  jnz     loc_1401EEF92
0x1401eef04  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401eef0b  test    rax, rax
0x1401eef0e  jz      short loc_1401EEF54
0x1401eef10  cmp     [rax+40h], ebx
0x1401eef13  jz      short loc_1401EEF54
0x1401eef15  cmp     dword ptr [rax+38h], 2
0x1401eef19  jl      short loc_1401EEF54
0x1401eef1b  lea     rsi, aConfigAdconfig_20; "Config::AdConfig::ReadRootNamingContext"...
0x1401eef22  mov     [rsp+2E0h+var_288], rsi
0x1401eef27  mov     dword ptr [rsp+2E0h+var_280], 1D3Ch
0x1401eef2f  mov     dword ptr [rsp+2E0h+var_280+4], 2
0x1401eef37  lea     r14, aCfad; "CFAD"
0x1401eef3e  mov     [rsp+2E0h+var_278], r14
0x1401eef43  lea     rdx, aMissingNamingc; "Missing namingContexts attribute"
0x1401eef4a  lea     rcx, [rsp+2E0h+var_288]
0x1401eef4f  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x1401eef54  call    cs:__imp_GetCurrentThreadId
0x1401eef5b  nop     dword ptr [rax+rax+00h]
0x1401eef60  mov     [rsp+2E0h+var_2A0], rbx
0x1401eef65  mov     [rsp+2E0h+var_2A8], eax
0x1401eef69  mov     dword ptr [rsp+2E0h+var_2B0], 1D3Dh
0x1401eef71  mov     r9d, 1
0x1401eef77  lea     r12, aBaseFsRemotefs_10; "base\\fs\\remotefs\\frs\\src\\ad\\ad.cp"...
0x1401eef7e  lea     r15, aConfigAdconfig_18; "Config::AdConfig::ReadRootNamingContext"...
0x1401eef85  xor     r8d, r8d
0x1401eef88  mov     edx, 490h
0x1401eef8d  jmp     loc_1401EF59E
0x1401eef92  mov     r14d, ebx
0x1401eef95  lea     r15, [rax+28h]
0x1401eef99  mov     esi, 1
0x1401eef9e  mov     rax, [r15+8]
0x1401eefa2  sub     rax, [r15]
0x1401eefa5  sar     rax, 3
0x1401eefa9  cmp     r14d, eax
0x1401eefac  jnb     short loc_1401EF026
0x1401eefae  mov     edx, r14d
0x1401eefb1  mov     rcx, r15
0x1401eefb4  call    ?at@?$vector@PEAVShutdownObject@@V?$allocator@PEAVShutdownObject@@@std@@@std@@QEAAAEAPEAVShutdownObject@@_K@Z; std::vector<ShutdownObject *>::at(unsigned __int64)
0x1401eefb9  mov     rcx, [rax]
0x1401eefbc  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x1401eefc3  nop     dword ptr [rax+rax+00h]
0x1401eefc8  mov     r12, rax
0x1401eefcb  lea     rdx, aCnConfiguratio; "cn=configuration"
0x1401eefd2  mov     rcx, rax; Str
0x1401eefd5  call    cs:__imp_wcsstr
0x1401eefdc  nop     dword ptr [rax+rax+00h]
0x1401eefe1  test    rax, rax
0x1401eefe4  jz      short loc_1401EEFEB
0x1401eefe6  cmp     rax, r12
0x1401eefe9  jz      short loc_1401EEFF0
0x1401eefeb  add     r14d, esi
0x1401eefee  jmp     short loc_1401EEF9E
0x1401eeff0  mov     [rsp+2E0h+var_290], rax
0x1401eeff5  lea     rdx, aCnSites; "cn=sites"
0x1401eeffc  lea     rcx, [rsp+2E0h+var_290]; this
0x1401ef001  call    ?Extend@AdDn@Config@@QEBAPEAGPEBG@Z; Config::AdDn::Extend(ushort const *)
0x1401ef006  mov     [rdi+30h], rax
0x1401ef00a  lea     rdx, aCnServices; "cn=services"
0x1401ef011  lea     rcx, [rsp+2E0h+var_290]; this
0x1401ef016  call    ?Extend@AdDn@Config@@QEBAPEAGPEBG@Z; Config::AdDn::Extend(ushort const *)
0x1401ef01b  mov     [rdi+38h], rax
0x1401ef01f  xor     ecx, ecx; Block
0x1401ef021  call    ??_V@YAXPEAXAEBUZeroFill@@@Z; operator delete[](void *,ZeroFill const &)
0x1401ef026  lea     rdx, aDefaultnamingc; "defaultNamingContext"
0x1401ef02d  lea     rcx, [rbp+1E0h+var_210]; this
0x1401ef031  call    ?FindAttr@AdAttrList@Config@@QEBAPEAVAdAttr@2@PEBG@Z; Config::AdAttrList::FindAttr(ushort const *)
0x1401ef036  mov     r15, rax
0x1401ef039  test    rax, rax
0x1401ef03c  jnz     short loc_1401EF0B7
0x1401ef03e  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401ef045  test    rax, rax
0x1401ef048  jz      short loc_1401EF092
0x1401ef04a  cmp     [rax+40h], ebx
0x1401ef04d  jz      short loc_1401EF092
0x1401ef04f  cmp     dword ptr [rax+38h], 2
0x1401ef053  jl      short loc_1401EF092
0x1401ef055  lea     rsi, aConfigAdconfig_20; "Config::AdConfig::ReadRootNamingContext"...
0x1401ef05c  mov     [rsp+2E0h+var_288], rsi
0x1401ef061  mov     dword ptr [rsp+2E0h+var_280], 1D5Bh
0x1401ef069  mov     dword ptr [rsp+2E0h+var_280+4], 2
0x1401ef071  lea     r14, aCfad; "CFAD"
0x1401ef078  mov     [rsp+2E0h+var_278], r14
0x1401ef07d  lea     rdx, aMissingDefault; "Missing defaultNamingContext attribute"
0x1401ef084  lea     rcx, [rsp+2E0h+var_288]
0x1401ef089  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x1401ef08e  lea     esi, [r15+1]
0x1401ef092  call    cs:__imp_GetCurrentThreadId
0x1401ef099  nop     dword ptr [rax+rax+00h]
0x1401ef09e  mov     [rsp+2E0h+var_2A0], rbx
0x1401ef0a3  mov     [rsp+2E0h+var_2A8], eax
0x1401ef0a7  mov     dword ptr [rsp+2E0h+var_2B0], 1D5Ch
0x1401ef0af  mov     r9d, esi
0x1401ef0b2  jmp     loc_1401EEF77
0x1401ef0b7  mov     rcx, [rdi+48h]; Block
0x1401ef0bb  call    ??_V@YAXPEAXAEBUZeroFill@@@Z; operator delete[](void *,ZeroFill const &)
0x1401ef0c0  mov     [rdi+48h], rbx
0x1401ef0c4  lea     r14, [rdi+58h]
0x1401ef0c8  mov     rcx, r15; this
0x1401ef0cb  call    ?GetValue@AdStrAttr@Config@@QEBAPEBGXZ; Config::AdStrAttr::GetValue(void)
0x1401ef0d0  mov     rdx, rax; unsigned __int16 *
0x1401ef0d3  mov     rcx, r14; this
0x1401ef0d6  call    ?Set@AdDn@Config@@QEAAXPEBG@Z; Config::AdDn::Set(ushort const *)
0x1401ef0db  cmp     [r14], rbx
0x1401ef0de  jz      short loc_1401EF140
0x1401ef0e0  mov     rcx, [rdi+48h]; Block
0x1401ef0e4  call    ??_V@YAXPEAXAEBUZeroFill@@@Z; operator delete[](void *,ZeroFill const &)
0x1401ef0e9  mov     [rdi+48h], rbx
0x1401ef0ed  lea     rdx, aCnComputers; "cn=computers"
0x1401ef0f4  mov     rcx, r14; this
0x1401ef0f7  call    ?Extend@AdDn@Config@@QEBAPEAGPEBG@Z; Config::AdDn::Extend(ushort const *)
0x1401ef0fc  mov     [rdi+48h], rax
0x1401ef100  mov     rcx, [rdi+40h]; Block
0x1401ef104  call    ??_V@YAXPEAXAEBUZeroFill@@@Z; operator delete[](void *,ZeroFill const &)
0x1401ef109  mov     [rdi+40h], rbx
0x1401ef10d  lea     rdx, aCnSystem; "cn=system"
0x1401ef114  mov     rcx, r14; this
0x1401ef117  call    ?Extend@AdDn@Config@@QEBAPEAGPEBG@Z; Config::AdDn::Extend(ushort const *)
0x1401ef11c  mov     [rdi+40h], rax
0x1401ef120  mov     rcx, [rdi+50h]; Block
0x1401ef124  call    ??_V@YAXPEAXAEBUZeroFill@@@Z; operator delete[](void *,ZeroFill const &)
0x1401ef129  mov     [rdi+50h], rbx
0x1401ef12d  lea     rdx, aOuDomainContro; "ou=domain controllers"
0x1401ef134  mov     rcx, r14; this
0x1401ef137  call    ?Extend@AdDn@Config@@QEBAPEAGPEBG@Z; Config::AdDn::Extend(ushort const *)
0x1401ef13c  mov     [rdi+50h], rax
0x1401ef140  lea     rdx, aSchemanamingco; "schemaNamingContext"
0x1401ef147  lea     rcx, [rbp+1E0h+var_210]; this
0x1401ef14b  call    ?FindAttr@AdAttrList@Config@@QEBAPEAVAdAttr@2@PEBG@Z; Config::AdAttrList::FindAttr(ushort const *)
0x1401ef150  test    rax, rax
0x1401ef153  jnz     short loc_1401EF1CC
0x1401ef155  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401ef15c  test    rax, rax
0x1401ef15f  jz      short loc_1401EF1AA
0x1401ef161  cmp     [rax+40h], ebx
0x1401ef164  jz      short loc_1401EF1AA
0x1401ef166  cmp     dword ptr [rax+38h], 2
0x1401ef16a  jl      short loc_1401EF1AA
0x1401ef16c  lea     rsi, aConfigAdconfig_20; "Config::AdConfig::ReadRootNamingContext"...
0x1401ef173  mov     [rsp+2E0h+var_288], rsi
0x1401ef178  mov     dword ptr [rsp+2E0h+var_280], 1D7Dh
0x1401ef180  mov     dword ptr [rsp+2E0h+var_280+4], 2
0x1401ef188  lea     r14, aCfad; "CFAD"
0x1401ef18f  mov     [rsp+2E0h+var_278], r14
0x1401ef194  lea     rdx, aIgnoredMissing; "(Ignored) Missing schemaNamingContext a"...
0x1401ef19b  lea     rcx, [rsp+2E0h+var_288]
0x1401ef1a0  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x1401ef1a5  mov     esi, 1
0x1401ef1aa  call    cs:__imp_GetCurrentThreadId
0x1401ef1b1  nop     dword ptr [rax+rax+00h]
0x1401ef1b6  mov     [rsp+2E0h+var_2A0], rbx
0x1401ef1bb  mov     [rsp+2E0h+var_2A8], eax
0x1401ef1bf  mov     dword ptr [rsp+2E0h+var_2B0], 1D7Eh
0x1401ef1c7  jmp     loc_1401EF0AF
0x1401ef1cc  mov     rcx, rax; this
0x1401ef1cf  call    ?GetValue@AdStrAttr@Config@@QEBAPEBGXZ; Config::AdStrAttr::GetValue(void)
0x1401ef1d4  mov     rdx, rax; unsigned __int16 *
0x1401ef1d7  lea     rcx, [rdi+60h]; this
0x1401ef1db  call    ?Set@AdDn@Config@@QEAAXPEBG@Z; Config::AdDn::Set(ushort const *)
0x1401ef1e0  lea     r15, aConfigAdconfig_18; "Config::AdConfig::ReadRootNamingContext"...
0x1401ef1e7  lea     r12, aBaseFsRemotefs_10; "base\\fs\\remotefs\\frs\\src\\ad\\ad.cp"...
0x1401ef1ee  cmp     [rdi+30h], rbx
0x1401ef1f2  jz      short loc_1401EF217
0x1401ef1f4  cmp     [rdi+38h], rbx
0x1401ef1f8  jz      short loc_1401EF217
0x1401ef1fa  cmp     [rdi+50h], rbx
0x1401ef1fe  jz      short loc_1401EF217
0x1401ef200  cmp     [r14], rbx
0x1401ef203  jz      short loc_1401EF217
0x1401ef205  cmp     [rdi+48h], rbx
0x1401ef209  jz      short loc_1401EF217
0x1401ef20b  cmp     [rdi+40h], rbx
0x1401ef20f  jz      short loc_1401EF217
0x1401ef211  cmp     [rdi+60h], rbx
0x1401ef215  jnz     short loc_1401EF251
0x1401ef217  call    cs:__imp_GetCurrentThreadId
0x1401ef21e  nop     dword ptr [rax+rax+00h]
0x1401ef223  mov     [rsp+2E0h+var_2A0], rbx
0x1401ef228  mov     [rsp+2E0h+var_2A8], eax
0x1401ef22c  mov     dword ptr [rsp+2E0h+var_2B0], 1D89h
0x1401ef234  mov     qword ptr [rsp+2E0h+var_2B8], r15
0x1401ef239  mov     [rsp+2E0h+var_2C0], r12
0x1401ef23e  mov     r9d, esi
0x1401ef241  xor     r8d, r8d
0x1401ef244  mov     edx, 490h
0x1401ef249  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401ef24e  mov     r13, rax
0x1401ef251  xor     eax, eax
0x1401ef253  lock cmpxchg cs:dword_140319434, esi
0x1401ef25b  jnz     loc_1401EF570
0x1401ef261  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401ef268  test    rax, rax
0x1401ef26b  jz      loc_1401EF570
0x1401ef271  lea     rsi, aConfigAdconfig_20; "Config::AdConfig::ReadRootNamingContext"...
0x1401ef278  lea     r14, aCfad; "CFAD"
0x1401ef27f  cmp     [rax+40h], ebx
0x1401ef282  jz      short loc_1401EF2CA
0x1401ef284  cmp     dword ptr [rax+38h], 4
0x1401ef288  jl      short loc_1401EF2CA
0x1401ef28a  mov     [rsp+2E0h+var_288], rsi
0x1401ef28f  mov     dword ptr [rsp+2E0h+var_280], 1D8Dh
0x1401ef297  mov     dword ptr [rsp+2E0h+var_280+4], 4
0x1401ef29f  mov     [rsp+2E0h+var_278], r14
0x1401ef2a4  mov     rax, [rdi+58h]
0x1401ef2a8  mov     [rsp+2E0h+var_290], rax
0x1401ef2ad  lea     r8, [rsp+2E0h+var_290]
0x1401ef2b2  lea     rdx, aDefaultNamingC; "Default Naming Context DN:%ws"
0x1401ef2b9  lea     rcx, [rsp+2E0h+var_288]
0x1401ef2be  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x1401ef2c3  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401ef2ca  test    rax, rax
0x1401ef2cd  jz      loc_1401EF570
0x1401ef2d3  cmp     [rax+40h], ebx
0x1401ef2d6  jz      short loc_1401EF31D
0x1401ef2d8  cmp     dword ptr [rax+38h], 4
0x1401ef2dc  jl      short loc_1401EF31D
0x1401ef2de  mov     [rsp+2E0h+var_270], rsi
0x1401ef2e3  mov     [rsp+2E0h+var_268], 1D8Eh
0x1401ef2eb  mov     [rsp+2E0h+var_264], 4
0x1401ef2f3  mov     [rbp+1E0h+var_260], r14
0x1401ef2f7  mov     rax, [rdi+30h]
0x1401ef2fb  mov     [rsp+2E0h+var_290], rax
0x1401ef300  lea     r8, [rsp+2E0h+var_290]
0x1401ef305  lea     rdx, aSchemaNamingCo; "Schema Naming Context DN:%ws"
0x1401ef30c  lea     rcx, [rsp+2E0h+var_270]
0x1401ef311  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x1401ef316  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401ef31d  test    rax, rax
0x1401ef320  jz      loc_1401EF570
0x1401ef326  cmp     [rax+40h], ebx
0x1401ef329  jz      short loc_1401EF36C
0x1401ef32b  cmp     dword ptr [rax+38h], 4
0x1401ef32f  jl      short loc_1401EF36C
0x1401ef331  mov     [rbp+1E0h+var_258], rsi
0x1401ef335  mov     [rbp+1E0h+var_250], 1D90h
0x1401ef33c  mov     [rbp+1E0h+var_24C], 4
0x1401ef343  mov     [rbp+1E0h+var_248], r14
0x1401ef347  mov     rax, [rdi+38h]
0x1401ef34b  mov     [rsp+2E0h+var_290], rax
  ... truncated ...
```
