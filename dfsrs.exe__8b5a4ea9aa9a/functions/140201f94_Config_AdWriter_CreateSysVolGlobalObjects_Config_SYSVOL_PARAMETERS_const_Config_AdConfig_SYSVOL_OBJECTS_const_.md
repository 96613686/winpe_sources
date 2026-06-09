# Config::AdWriter::CreateSysVolGlobalObjects(Config::SYSVOL_PARAMETERS const *,Config::AdConfig::SYSVOL_OBJECTS const *,int)

- ea: `0x140201f94`
- end: `0x140202a47`
- name: `?CreateSysVolGlobalObjects@AdWriter@Config@@IEAAPEAVFrsStatus@@PEBUSYSVOL_PARAMETERS@2@PEBUSYSVOL_OBJECTS@AdConfig@2@H@Z`
- size: `2739`
- prototype: `struct FrsStatus *__fastcall(Config::AdWriter *__hidden this, const struct Config::SYSVOL_PARAMETERS *, const struct Config::AdConfig::SYSVOL_OBJECTS *, int)`
- caller_count: `1`
- callee_count: `33`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x140204318`

## callees

- `0x1400036a0`
- `0x1400036d0`
- `0x14000c910`
- `0x14000e34c`
- `0x14000ee94`
- `0x140010680`
- `0x140014df4`
- `0x14001c030`
- `0x140025594`
- `0x1400255c8`
- `0x14004485c`
- `0x14005c620`
- `0x1400c9520`
- `0x1400c95bc`
- `0x1401af7c0`
- `0x1401b3140`
- `0x1401b8e5c`
- `0x1401b9494`
- `0x1401ba178`
- `0x1401de184`
- `0x1401de480`
- `0x1401de77c`
- `0x1401df160`
- `0x1401df454`
- `0x1401f2d04`
- `0x1401f2d78`
- `0x1401f2e30`
- `0x1401f31f8`
- `0x1401ff488`
- `0x140201520`
- `0x14020174c`
- `0x140201f94`
- `0x140205da8`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14020210f`
- `KERNEL32!GetCurrentThreadId` at `0x14020217b`
- `KERNEL32!GetCurrentThreadId` at `0x140202336`
- `KERNEL32!GetCurrentThreadId` at `0x140202463`
- `KERNEL32!GetCurrentThreadId` at `0x1402026d0`
- `KERNEL32!GetCurrentThreadId` at `0x140202813`
- `KERNEL32!GetCurrentThreadId` at `0x1402029d2`
- `KERNEL32!GetCurrentThreadId` at `0x14020210f`
- `KERNEL32!GetCurrentThreadId` at `0x14020217b`
- `KERNEL32!GetCurrentThreadId` at `0x140202336`
- `KERNEL32!GetCurrentThreadId` at `0x140202463`
- `KERNEL32!GetCurrentThreadId` at `0x1402026d0`
- `KERNEL32!GetCurrentThreadId` at `0x140202813`
- `KERNEL32!GetCurrentThreadId` at `0x1402029d2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140202883`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140202883`

## string_xrefs

- `0x140202514`: `msDFSR-DirectoryFilter`
- `0x1402021a4`: `base\fs\remotefs\frs\src\ad\adwriter.cpp`
- `0x14020235f`: `base\fs\remotefs\frs\src\ad\adwriter.cpp`
- `0x1402026f9`: `base\fs\remotefs\frs\src\ad\adwriter.cpp`
- `0x1402029fb`: `base\fs\remotefs\frs\src\ad\adwriter.cpp`
- `0x140202198`: `Config::AdWriter::CreateSysVolGlobalObjects`
- `0x140202353`: `Config::AdWriter::CreateSysVolGlobalObjects`
- `0x1402026ed`: `Config::AdWriter::CreateSysVolGlobalObjects`
- `0x1402029ef`: `Config::AdWriter::CreateSysVolGlobalObjects`
- `0x140201fe4`: `Config::AdWriter::CreateSysVolGlobalObjects`
- `0x14020202b`: `[SYSVOL] Create sysvol global objects`
- `0x140202529`: `DO_NOT_REMOVE_NtFrs_PreInstall_Directory,NtFrs_PreExisting___See_EventLog`
- `0x14020254f`: `DO_NOT_REMOVE_NtFrs_PreInstall_Directory,NtFrs_PreExisting___See_EventLog`
- `0x140202937`: `[SYSVOL] DFSR-GloablSettings except member objects are created`
- `0x1402028d1`: `[SYSVOL] This is an RODC. No need to create member object in promotion`
- `0x14020298f`: `[SYSVOL] member object is created`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
struct FrsStatus *__fastcall Config::AdWriter::CreateSysVolGlobalObjects(
        Config::AdWriter *this,
        const struct Config::SYSVOL_PARAMETERS *a2,
        const unsigned __int16 **a3)
{
  __int64 v6; // rdi
  struct FrsStatus *AllSysVolRodcMemberObjects; // rsi
  struct FrsStatus *v8; // rax
  unsigned int *v9; // rsi
  __int64 v10; // rbx
  Dword *v11; // rax
  __int64 v12; // rcx
  int v14; // r8d
  unsigned int *v15; // rbx
  DWORD v16; // eax
  __int64 v17; // rcx
  Config::AdStrAttr *v18; // rbx
  struct FrsStatus *v19; // rax
  unsigned int *v20; // rsi
  __int64 v21; // rbx
  Dword *v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rax
  struct FrsStatus *v25; // rax
  unsigned int *v26; // rsi
  __int64 v27; // rbx
  Dword *v28; // rax
  __int64 v29; // rcx
  char v30; // al
  Config::AdStrAttr *v31; // rbx
  Config::AdStrAttr *v32; // rbx
  const unsigned __int16 *v33; // rdx
  struct FrsStatus *v34; // rax
  unsigned int *v35; // rsi
  __int64 v36; // rbx
  Dword *v37; // rax
  __int64 v38; // rcx
  __int64 v39; // rax
  struct FrsStatus *v40; // rax
  __int64 v41; // rbx
  Dword *v42; // rax
  __int64 v43; // rcx
  const wchar_t *v44; // rdx
  __int64 v45; // rcx
  DWORD CurrentThreadId; // [rsp+38h] [rbp-C8h]
  DWORD v48; // [rsp+38h] [rbp-C8h]
  DWORD v49; // [rsp+38h] [rbp-C8h]
  DWORD v50; // [rsp+38h] [rbp-C8h]
  DWORD v51; // [rsp+38h] [rbp-C8h]
  DWORD v52; // [rsp+38h] [rbp-C8h]
  struct FrsStatus *v53; // [rsp+50h] [rbp-B0h] BYREF
  void *v54; // [rsp+58h] [rbp-A8h] BYREF
  Config::AdStrAttr *v55; // [rsp+60h] [rbp-A0h] BYREF
  void *Block; // [rsp+68h] [rbp-98h] BYREF
  void *v57; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v58; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v59[2]; // [rsp+80h] [rbp-80h] BYREF
  void **v60; // [rsp+90h] [rbp-70h] BYREF
  void *EventOrDie; // [rsp+98h] [rbp-68h] BYREF
  int v62; // [rsp+A0h] [rbp-60h]
  _BYTE v63[8]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v64[88]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v65[8]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v66[88]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v67[96]; // [rsp+170h] [rbp+70h] BYREF
  const wchar_t *v68; // [rsp+1D0h] [rbp+D0h] BYREF
  int v69; // [rsp+1D8h] [rbp+D8h]
  int v70; // [rsp+1DCh] [rbp+DCh]
  const wchar_t *v71; // [rsp+1E0h] [rbp+E0h]

  v6 = 0;
  AllSysVolRodcMemberObjects = 0;
  v59[1] = *((_QWORD *)this + 5);
  v59[0] = &Config::AdObjectEditor::`vftable';
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v68 = L"Config::AdWriter::CreateSysVolGlobalObjects";
    v69 = 311;
    v70 = 4;
    v71 = L"ADWR";
    dbgobj::DbgPrint<unsigned short>(&v68, L"[SYSVOL] Create sysvol global objects");
  }
  if ( *((_DWORD *)a2 + 6) )
  {
    v8 = Config::AdObjectEditor::AddObject((Config::AdObjectEditor *)v59, L"msDFSR-GlobalSettings", a3[6], a3[7]);
    v9 = (unsigned int *)v8;
    v53 = v8;
    if ( v8 )
    {
      if ( *((_DWORD *)v8 + 1) != 183 )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
        {
          v68 = L"Config::AdWriter::CreateSysVolGlobalObjects";
          v69 = 330;
          v70 = 2;
          v71 = L"ADWR";
          dbgobj::DbgPrint<unsigned short>(&v68, L"[SYSVOL] Failed to add global settings object");
        }
        v10 = *(_QWORD *)FrsStatusString::FrsStatusString((FrsStatusString *)&Block, (const struct FrsStatus *)v9);
        v11 = Dword::Dword((Dword *)&v68, v9[1], 10);
        FrsEvent::Log(3221233473LL, *((_QWORD *)this + 3), v11, v10);
        operator delete[](Block);
        CurrentThreadId = GetCurrentThreadId();
        return (struct FrsStatus *)FrsStatusList::PushNewError(
                                     v12,
                                     v9[1],
                                     v9[2],
                                     *v9,
                                     "base\\fs\\remotefs\\frs\\src\\ad\\adwriter.cpp",
                                     "Config::AdWriter::CreateSysVolGlobalObjects",
                                     336,
                                     CurrentThreadId,
                                     v9);
      }
      CLEAR_ERROR(&v53);
    }
    else
    {
      v60 = &ShutdownObject::`vftable';
      v62 = 0;
      EventOrDie = CreateEventOrDie(1, 0);
      Migration::SysVolMigration::SysVolMigration((Migration::SysVolMigration *)v67, (struct ShutdownObject *)&v60, v14);
      v15 = (unsigned int *)Migration::SysVolMigration::SetGlobalState(v67);
      if ( v15 )
      {
        v16 = GetCurrentThreadId();
        v6 = FrsStatusList::PushNewError(
               v17,
               v15[1],
               v15[2],
               *v15,
               "base\\fs\\remotefs\\frs\\src\\ad\\adwriter.cpp",
               "Config::AdWriter::CreateSysVolGlobalObjects",
               355,
               v16,
               v15);
        Migration::SysVolMigration::~SysVolMigration((Migration::SysVolMigration *)v67);
        v60 = &ShutdownObject::`vftable';
        CloseHandleEx(&EventOrDie);
        return (struct FrsStatus *)v6;
      }
      Migration::SysVolMigration::~SysVolMigration((Migration::SysVolMigration *)v67);
      v60 = &ShutdownObject::`vftable';
      CloseHandleEx(&EventOrDie);
    }
    Config::AdObject::AdObject((Config::AdObject *)v63);
    Config::AdObject::SetClass((Config::AdObject *)v63, L"msDFSR-ReplicationGroup");
    Config::AdObject::SetCn((Config::AdObject *)v63, a3[8]);
    Config::AdObject::SetDn((Config::AdObject *)v63, a3[9]);
    v57 = operator new(0x48u);
    v18 = (Config::AdStrAttr *)Config::AdStrAttr::AdStrAttr((Config::AdStrAttr *)v57);
    FrsStringImpl<unsigned short,char>::Set((char *)v18 + 16, L"msDFSR-ReplicationGroupType");
    Config::AdStrAttr::SetValue(v18, 1u);
    v54 = v18;
    std::vector<ReplicaSetManager *>::push_back(v64, &v54);
    v19 = Config::AdObjectEditor::AddObject((Config::AdObjectEditor *)v59, (const struct Config::AdObject *)v63);
    v20 = (unsigned int *)v19;
    v53 = v19;
    if ( v19 )
    {
      if ( *((_DWORD *)v19 + 1) != 183 )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
        {
          v68 = L"Config::AdWriter::CreateSysVolGlobalObjects";
          v69 = 381;
          v70 = 2;
          v71 = L"ADWR";
          dbgobj::DbgPrint<unsigned short>(&v68, L"[SYSVOL] Failed to add replication group object");
        }
        v21 = *(_QWORD *)FrsStatusString::FrsStatusString((FrsStatusString *)&v54, (const struct FrsStatus *)v20);
        v22 = Dword::Dword((Dword *)&v68, v20[1], 10);
        FrsEvent::Log(3221233473LL, *((_QWORD *)this + 3), v22, v21);
        operator delete[](v54);
        v48 = GetCurrentThreadId();
        v24 = FrsStatusList::PushNewError(
                v23,
                v20[1],
                v20[2],
                *v20,
                "base\\fs\\remotefs\\frs\\src\\ad\\adwriter.cpp",
                "Config::AdWriter::CreateSysVolGlobalObjects",
                387,
                v48,
                v20);
LABEL_24:
        v6 = v24;
LABEL_25:
        Config::AdObject::~AdObject((Config::AdObject *)v63);
        return (struct FrsStatus *)v6;
      }
      CLEAR_ERROR(&v53);
    }
    v25 = Config::AdObjectEditor::AddObject((Config::AdObjectEditor *)v59, L"msDFSR-Content", a3[10], a3[11]);
    v26 = (unsigned int *)v25;
    v53 = v25;
    if ( v25 )
    {
      if ( *((_DWORD *)v25 + 1) != 183 )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
        {
          v68 = L"Config::AdWriter::CreateSysVolGlobalObjects";
          v69 = 402;
          v70 = 2;
          v71 = L"ADWR";
          dbgobj::DbgPrint<unsigned short>(&v68, L"[SYSVOL] Failed to add content object");
        }
        v27 = *(_QWORD *)FrsStatusString::FrsStatusString((FrsStatusString *)&v54, (const struct FrsStatus *)v26);
        v28 = Dword::Dword((Dword *)&v68, v26[1], 10);
        FrsEvent::Log(3221233473LL, *((_QWORD *)this + 3), v28, v27);
        operator delete[](v54);
        v49 = GetCurrentThreadId();
        v24 = FrsStatusList::PushNewError(
                v29,
                v26[1],
                v26[2],
                *v26,
                "base\\fs\\remotefs\\frs\\src\\ad\\adwriter.cpp",
                "Config::AdWriter::CreateSysVolGlobalObjects",
                408,
                v49,
                v26);
        goto LABEL_24;
      }
      CLEAR_ERROR(&v53);
    }
    Config::AdObject::AdObject((Config::AdObject *)v65);
    Config::AdObject::SetClass((Config::AdObject *)v65, L"msDFSR-ContentSet");
    Config::AdObject::SetCn((Config::AdObject *)v65, a3[14]);
    Config::AdObject::SetDn((Config::AdObject *)v65, a3[15]);
    Block = &FrsStringImpl<unsigned short,char>::s_Empty;
    v30 = byte_140315A80;
    if ( !byte_140315A80 )
    {
      _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
      v30 = 0;
    }
    v58 = &FrsStringImpl<unsigned short,char>::s_Empty;
    if ( !v30 )
      _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
    v55 = (Config::AdStrAttr *)operator new(0x48u);
    v31 = (Config::AdStrAttr *)Config::AdStrAttr::AdStrAttr(v55);
    FrsStringImpl<unsigned short,char>::Set((char *)v31 + 16, L"msDFSR-DirectoryFilter");
    if ( qword_140315A78 )
    {
      v55 = (Config::AdStrAttr *)&FrsStringImpl<unsigned short,char>::s_Empty;
      if ( !byte_140315A80 )
        _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
      FrsStringImpl<unsigned short,char>::Set(
        &v55,
        L"DO_NOT_REMOVE_NtFrs_PreInstall_Directory,NtFrs_PreExisting___See_EventLog");
      FrsStringImpl<unsigned short,char>::Append(&v55, L",");
      FrsStringImpl<unsigned short,char>::Append(&v55, &Block);
      Config::AdStrAttr::SetValue(v31, (const unsigned __int16 *)v55 + 9);
      FrsStringImpl<char,unsigned short>::ReleaseBody(&v55);
    }
    else
    {
      Config::AdStrAttr::SetValue(v31, L"DO_NOT_REMOVE_NtFrs_PreInstall_Directory,NtFrs_PreExisting___See_EventLog");
    }
    v54 = v31;
    std::vector<ReplicaSetManager *>::push_back(v66, &v54);
    v54 = operator new(0x48u);
    v32 = (Config::AdStrAttr *)Config::AdStrAttr::AdStrAttr((Config::AdStrAttr *)v54);
    FrsStringImpl<unsigned short,char>::Set((char *)v32 + 16, L"msDFSR-FileFilter");
    v33 = L"~*,*.TMP,*.BAK";
    if ( qword_140315A78 )
      v33 = &word_140315A82;
    Config::AdStrAttr::SetValue(v32, v33);
    v54 = v32;
    std::vector<ReplicaSetManager *>::push_back(v66, &v54);
    v34 = Config::AdObjectEditor::AddObject((Config::AdObjectEditor *)v59, (const struct Config::AdObject *)v65);
    v35 = (unsigned int *)v34;
    v53 = v34;
    if ( v34 )
    {
      if ( *((_DWORD *)v34 + 1) != 183 )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
        {
          v68 = L"Config::AdWriter::CreateSysVolGlobalObjects";
          v69 = 514;
          v70 = 2;
          v71 = L"ADWR";
          dbgobj::DbgPrint<unsigned short>(&v68, L"[SYSVOL] Failed to add content set object");
        }
        v36 = *(_QWORD *)FrsStatusString::FrsStatusString((FrsStatusString *)&v57, (const struct FrsStatus *)v35);
        v37 = Dword::Dword((Dword *)&v68, v35[1], 10);
        FrsEvent::Log(3221233473LL, *((_QWORD *)this + 3), v37, v36);
        operator delete[](v57);
        v50 = GetCurrentThreadId();
        v39 = FrsStatusList::PushNewError(
                v38,
                v35[1],
                v35[2],
                *v35,
                "base\\fs\\remotefs\\frs\\src\\ad\\adwriter.cpp",
                "Config::AdWriter::CreateSysVolGlobalObjects",
                520,
                v50,
                v35);
LABEL_53:
        v6 = v39;
        FrsStringImpl<char,unsigned short>::ReleaseBody(&v58);
        FrsStringImpl<char,unsigned short>::ReleaseBody(&Block);
        Config::AdObject::~AdObject((Config::AdObject *)v65);
        goto LABEL_25;
      }
      CLEAR_ERROR(&v53);
    }
    v40 = Config::AdObjectEditor::AddObject((Config::AdObjectEditor *)v59, L"msDFSR-Topology", a3[12], a3[13]);
    AllSysVolRodcMemberObjects = v40;
    v53 = v40;
    if ( v40 )
    {
      if ( *((_DWORD *)v40 + 1) != 183 )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
        {
          v68 = L"Config::AdWriter::CreateSysVolGlobalObjects";
          v69 = 536;
          v70 = 2;
          v71 = L"ADWR";
          dbgobj::DbgPrint<unsigned short>(&v68, L"[SYSVOL] Failed to add replication topology group object");
        }
        v41 = *(_QWORD *)FrsStatusString::FrsStatusString((FrsStatusString *)&v57, AllSysVolRodcMemberObjects);
        v42 = Dword::Dword((Dword *)&v68, *((_DWORD *)AllSysVolRodcMemberObjects + 1), 10);
        FrsEvent::Log(3221233473LL, *((_QWORD *)this + 3), v42, v41);
        operator delete[](v57);
        v51 = GetCurrentThreadId();
        v39 = FrsStatusList::PushNewError(
                v43,
                *((unsigned int *)AllSysVolRodcMemberObjects + 1),
                *((unsigned int *)AllSysVolRodcMemberObjects + 2),
                *(unsigned int *)AllSysVolRodcMemberObjects,
                "base\\fs\\remotefs\\frs\\src\\ad\\adwriter.cpp",
                "Config::AdWriter::CreateSysVolGlobalObjects",
                542,
                v51,
                AllSysVolRodcMemberObjects);
        goto LABEL_53;
      }
      CLEAR_ERROR(&v53);
      AllSysVolRodcMemberObjects = v53;
    }
    else
    {
      FrsEvent::Log(1073749824, *((_QWORD *)this + 3));
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v68 = L"Config::AdWriter::CreateSysVolGlobalObjects";
        v69 = 552;
        v70 = 4;
        v71 = L"ADWR";
        dbgobj::DbgPrint<unsigned short>(&v68, L"[SYSVOL] DFSR-GloablSettings except member objects are created");
      }
    }
    FrsStringImpl<char,unsigned short>::ReleaseBody(&v58);
    FrsStringImpl<char,unsigned short>::ReleaseBody(&Block);
    Config::AdObject::~AdObject((Config::AdObject *)v65);
    Config::AdObject::~AdObject((Config::AdObject *)v63);
  }
  if ( (unsigned int)_o__wcsicmp(*((_QWORD *)a2 + 7) + 18LL, L"DcPromo") )
  {
    if ( *((_DWORD *)a2 + 6) )
      AllSysVolRodcMemberObjects = Config::AdWriter::CreateAllSysVolRodcMemberObjects(this);
    goto LABEL_82;
  }
  if ( *(_DWORD *)(*((_QWORD *)this + 5) + 36LL) )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v69 = 572;
      v44 = L"[SYSVOL] This is an RODC. No need to create member object in promotion";
LABEL_79:
      v71 = L"ADWR";
      v70 = 4;
      v68 = L"Config::AdWriter::CreateSysVolGlobalObjects";
      dbgobj::DbgPrint<unsigned short>(&v68, v44);
    }
LABEL_82:
    if ( !AllSysVolRodcMemberObjects )
      return (struct FrsStatus *)v6;
LABEL_83:
    v52 = GetCurrentThreadId();
    return (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v45,
                                 *((unsigned int *)AllSysVolRodcMemberObjects + 1),
                                 *((unsigned int *)AllSysVolRodcMemberObjects + 2),
                                 *(unsigned int *)AllSysVolRodcMemberObjects,
                                 "base\\fs\\remotefs\\frs\\src\\ad\\adwriter.cpp",
                                 "Config::AdWriter::CreateSysVolGlobalObjects",
                                 603,
                                 v52,
                                 AllSysVolRodcMemberObjects);
  }
  AllSysVolRodcMemberObjects = Config::AdWriter::CreateMemberObject(
                                 this,
                                 (const struct Config::AdConfig::SYSVOL_OBJECTS *)a3);
  if ( AllSysVolRodcMemberObjects )
    goto LABEL_83;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v69 = 584;
    v44 = L"[SYSVOL] member object is created";
    goto LABEL_79;
  }
  return (struct FrsStatus *)v6;
}

```

## disassembly

```asm
0x140201f94  mov     [rsp-8+arg_18], rbx
0x140201f99  push    rbp
0x140201f9a  push    rsi
0x140201f9b  push    rdi
0x140201f9c  push    r12
0x140201f9e  push    r13
0x140201fa0  push    r14
0x140201fa2  push    r15
0x140201fa4  lea     rbp, [rsp-110h]
0x140201fac  sub     rsp, 210h
0x140201fb3  mov     rax, cs:__security_cookie
0x140201fba  xor     rax, rsp
0x140201fbd  mov     [rbp+140h+var_40], rax
0x140201fc4  mov     r14, r8
0x140201fc7  mov     r13, rdx
0x140201fca  mov     r15, rcx
0x140201fcd  xor     edi, edi
0x140201fcf  mov     esi, edi
0x140201fd1  mov     rax, [rcx+28h]
0x140201fd5  mov     [rbp+140h+var_1B8], rax
0x140201fd9  lea     rax, ??_7AdObjectEditor@Config@@6B@; const Config::AdObjectEditor::`vftable'
0x140201fe0  mov     [rbp+140h+var_1C0], rax
0x140201fe4  lea     r12, aConfigAdwriter_18; "Config::AdWriter::CreateSysVolGlobalObj"...
0x140201feb  lea     rbx, aAdwr; "ADWR"
0x140201ff2  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140201ff9  test    rax, rax
0x140201ffc  jz      short loc_14020203E
0x140201ffe  cmp     [rax+40h], edi
0x140202001  jz      short loc_14020203E
0x140202003  cmp     dword ptr [rax+38h], 4
0x140202007  jl      short loc_14020203E
0x140202009  mov     [rbp+140h+var_70], r12
0x140202010  mov     [rbp+140h+var_68], 137h
0x14020201a  mov     [rbp+140h+var_64], 4
0x140202024  mov     [rbp+140h+var_60], rbx
0x14020202b  lea     rdx, aSysvolCreateSy_1; "[SYSVOL] Create sysvol global objects"
0x140202032  lea     rcx, [rbp+140h+var_70]
0x140202039  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x14020203e  cmp     [r13+18h], edi
0x140202042  jz      loc_140202874
0x140202048  mov     r9, [r14+38h]; unsigned __int16 *
0x14020204c  mov     r8, [r14+30h]; unsigned __int16 *
0x140202050  lea     rdx, aMsdfsrGlobalse; "msDFSR-GlobalSettings"
0x140202057  lea     rcx, [rbp+140h+var_1C0]; this
0x14020205b  call    ?AddObject@AdObjectEditor@Config@@QEAAPEAVFrsStatus@@PEBG00@Z; Config::AdObjectEditor::AddObject(ushort const *,ushort const *,ushort const *)
0x140202060  mov     rsi, rax
0x140202063  mov     [rsp+240h+var_1F0], rax
0x140202068  test    rax, rax
0x14020206b  jz      loc_140202140
0x140202071  cmp     dword ptr [rax+4], 0B7h
0x140202078  jz      loc_140202131
0x14020207e  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140202085  test    rax, rax
0x140202088  jz      short loc_1402020CA
0x14020208a  cmp     [rax+40h], edi
0x14020208d  jz      short loc_1402020CA
0x14020208f  cmp     dword ptr [rax+38h], 2
0x140202093  jl      short loc_1402020CA
0x140202095  mov     [rbp+140h+var_70], r12
0x14020209c  mov     [rbp+140h+var_68], 14Ah
0x1402020a6  mov     [rbp+140h+var_64], 2
0x1402020b0  mov     [rbp+140h+var_60], rbx
0x1402020b7  lea     rdx, aSysvolFailedTo_6; "[SYSVOL] Failed to add global settings "...
0x1402020be  lea     rcx, [rbp+140h+var_70]
0x1402020c5  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x1402020ca  mov     rdx, rsi; struct FrsStatus *
0x1402020cd  lea     rcx, [rsp+240h+Block]; this
0x1402020d2  call    ??0FrsStatusString@@QEAA@PEBVFrsStatus@@@Z; FrsStatusString::FrsStatusString(FrsStatus const *)
0x1402020d7  nop
0x1402020d8  mov     rbx, [rax]
0x1402020db  mov     r8d, 0Ah; int
0x1402020e1  mov     edx, [rsi+4]; unsigned int
0x1402020e4  lea     rcx, [rbp+140h+var_70]; this
0x1402020eb  call    ??0Dword@@QEAA@KH@Z; Dword::Dword(ulong,int)
0x1402020f0  mov     r9, rbx
0x1402020f3  mov     r8, rax
0x1402020f6  mov     rdx, [r15+18h]
0x1402020fa  mov     ecx, 0C0001F41h
0x1402020ff  call    ?Log@FrsEvent@@SAXW4FrsEventsEnum3@@PEBG11@Z; FrsEvent::Log(FrsEventsEnum3,ushort const *,ushort const *,ushort const *)
0x140202104  nop
0x140202105  mov     rcx, [rsp+240h+Block]; Block
0x14020210a  call    ??_V@YAXPEAXAEBUZeroFill@@@Z; operator delete[](void *,ZeroFill const &)
0x14020210f  call    cs:__imp_GetCurrentThreadId
0x140202116  nop     dword ptr [rax+rax+00h]
0x14020211b  mov     [rsp+240h+var_200], rsi
0x140202120  mov     [rsp+240h+var_208], eax
0x140202124  mov     [rsp+240h+var_210], 150h
0x14020212c  jmp     loc_1402029EF
0x140202131  lea     rcx, [rsp+240h+var_1F0]; struct FrsStatus **
0x140202136  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x14020213b  jmp     loc_1402021F5
0x140202140  lea     rsi, ??_7ShutdownObject@@6B@; const ShutdownObject::`vftable'
0x140202147  mov     [rbp+140h+var_1B0], rsi
0x14020214b  mov     [rbp+140h+var_1A0], edi
0x14020214e  xor     edx, edx; bInitialState
0x140202150  lea     ecx, [rdx+1]; bManualReset
0x140202153  call    ?CreateEventOrDie@@YAPEAXHH@Z; CreateEventOrDie(int,int)
0x140202158  mov     [rbp+140h+var_1A8], rax
0x14020215c  lea     rdx, [rbp+140h+var_1B0]; struct ShutdownObject *
0x140202160  lea     rcx, [rbp+140h+var_D0]; this
0x140202164  call    ??0SysVolMigration@Migration@@QEAA@AEAVShutdownObject@@H@Z; Migration::SysVolMigration::SysVolMigration(ShutdownObject &,int)
0x140202169  nop
0x14020216a  lea     rcx, [rbp+140h+var_D0]
0x14020216e  call    ?SetGlobalState@SysVolMigration@Migration@@QEAAPEAVFrsStatus@@W4_MIGRATION_STATE@2@@Z; Migration::SysVolMigration::SetGlobalState(Migration::_MIGRATION_STATE)
0x140202173  mov     rbx, rax
0x140202176  test    rax, rax
0x140202179  jz      short loc_1402021DE
0x14020217b  call    cs:__imp_GetCurrentThreadId
0x140202182  nop     dword ptr [rax+rax+00h]
0x140202187  mov     [rsp+240h+var_200], rbx
0x14020218c  mov     [rsp+240h+var_208], eax
0x140202190  mov     [rsp+240h+var_210], 163h
0x140202198  lea     rax, aConfigAdwriter_14; "Config::AdWriter::CreateSysVolGlobalObj"...
0x14020219f  mov     [rsp+240h+var_218], rax
0x1402021a4  lea     rax, aBaseFsRemotefs_38; "base\\fs\\remotefs\\frs\\src\\ad\\adwri"...
0x1402021ab  mov     [rsp+240h+var_220], rax
0x1402021b0  mov     r9d, [rbx]
0x1402021b3  mov     r8d, [rbx+8]
0x1402021b7  mov     edx, [rbx+4]
0x1402021ba  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1402021bf  mov     rdi, rax
0x1402021c2  lea     rcx, [rbp+140h+var_D0]; this
0x1402021c6  call    ??1SysVolMigration@Migration@@QEAA@XZ; Migration::SysVolMigration::~SysVolMigration(void)
0x1402021cb  nop
0x1402021cc  mov     [rbp+140h+var_1B0], rsi
0x1402021d0  lea     rcx, [rbp+140h+var_1A8]; void **
0x1402021d4  call    ?CloseHandleEx@@YAXAEAPEAX@Z; CloseHandleEx(void * &)
0x1402021d9  jmp     loc_140202A19
0x1402021de  lea     rcx, [rbp+140h+var_D0]; this
0x1402021e2  call    ??1SysVolMigration@Migration@@QEAA@XZ; Migration::SysVolMigration::~SysVolMigration(void)
0x1402021e7  nop
0x1402021e8  mov     [rbp+140h+var_1B0], rsi
0x1402021ec  lea     rcx, [rbp+140h+var_1A8]; void **
0x1402021f0  call    ?CloseHandleEx@@YAXAEAPEAX@Z; CloseHandleEx(void * &)
0x1402021f5  lea     rcx, [rbp+140h+var_190]; this
0x1402021f9  call    ??0AdObject@Config@@QEAA@XZ; Config::AdObject::AdObject(void)
0x1402021fe  nop
0x1402021ff  lea     rdx, aMsdfsrReplicat; "msDFSR-ReplicationGroup"
0x140202206  lea     rcx, [rbp+140h+var_190]; this
0x14020220a  call    ?SetClass@AdObject@Config@@QEAAXPEBG@Z; Config::AdObject::SetClass(ushort const *)
0x14020220f  mov     rdx, [r14+40h]; unsigned __int16 *
0x140202213  lea     rcx, [rbp+140h+var_190]; this
0x140202217  call    ?SetCn@AdObject@Config@@QEAAXPEBG@Z; Config::AdObject::SetCn(ushort const *)
0x14020221c  mov     rdx, [r14+48h]; unsigned __int16 *
0x140202220  lea     rcx, [rbp+140h+var_190]; this
0x140202224  call    ?SetDn@AdObject@Config@@QEAAXPEBG@Z; Config::AdObject::SetDn(ushort const *)
0x140202229  mov     ecx, 48h ; 'H'; Size
0x14020222e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140202233  mov     [rsp+240h+var_1D0], rax
0x140202238  mov     rcx, rax; this
0x14020223b  call    ??0AdStrAttr@Config@@QEAA@XZ; Config::AdStrAttr::AdStrAttr(void)
0x140202240  mov     rbx, rax
0x140202243  lea     rcx, [rax+10h]
0x140202247  lea     rdx, aMsdfsrReplicat_0; "msDFSR-ReplicationGroupType"
0x14020224e  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Set(ushort const *)
0x140202253  mov     edx, 1; unsigned int
0x140202258  mov     rcx, rbx; this
0x14020225b  call    ?SetValue@AdStrAttr@Config@@QEAAXK@Z; Config::AdStrAttr::SetValue(ulong)
0x140202260  mov     [rsp+240h+var_1E8], rbx
0x140202265  lea     rdx, [rsp+240h+var_1E8]
0x14020226a  lea     rcx, [rbp+140h+var_188]
0x14020226e  call    ?push_back@?$vector@PEAVReplicaSetManager@@V?$allocator@PEAVReplicaSetManager@@@std@@@std@@QEAAXAEBQEAVReplicaSetManager@@@Z; std::vector<ReplicaSetManager *>::push_back(ReplicaSetManager * const &)
0x140202273  lea     rdx, [rbp+140h+var_190]; struct Config::AdObject *
0x140202277  lea     rcx, [rbp+140h+var_1C0]; this
0x14020227b  call    ?AddObject@AdObjectEditor@Config@@QEAAPEAVFrsStatus@@PEBVAdObject@2@@Z; Config::AdObjectEditor::AddObject(Config::AdObject const *)
0x140202280  mov     rsi, rax
0x140202283  mov     [rsp+240h+var_1F0], rax
0x140202288  test    rax, rax
0x14020228b  jz      loc_140202395
0x140202291  cmp     dword ptr [rax+4], 0B7h
0x140202298  jz      loc_14020238B
0x14020229e  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1402022a5  test    rax, rax
0x1402022a8  jz      short loc_1402022F1
0x1402022aa  cmp     [rax+40h], edi
0x1402022ad  jz      short loc_1402022F1
0x1402022af  cmp     dword ptr [rax+38h], 2
0x1402022b3  jl      short loc_1402022F1
0x1402022b5  mov     [rbp+140h+var_70], r12
0x1402022bc  mov     [rbp+140h+var_68], 17Dh
0x1402022c6  mov     [rbp+140h+var_64], 2
0x1402022d0  lea     rax, aAdwr; "ADWR"
0x1402022d7  mov     [rbp+140h+var_60], rax
0x1402022de  lea     rdx, aSysvolFailedTo_5; "[SYSVOL] Failed to add replication grou"...
0x1402022e5  lea     rcx, [rbp+140h+var_70]
0x1402022ec  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x1402022f1  mov     rdx, rsi; struct FrsStatus *
0x1402022f4  lea     rcx, [rsp+240h+var_1E8]; this
0x1402022f9  call    ??0FrsStatusString@@QEAA@PEBVFrsStatus@@@Z; FrsStatusString::FrsStatusString(FrsStatus const *)
0x1402022fe  nop
0x1402022ff  mov     rbx, [rax]
0x140202302  mov     r8d, 0Ah; int
0x140202308  mov     edx, [rsi+4]; unsigned int
0x14020230b  lea     rcx, [rbp+140h+var_70]; this
0x140202312  call    ??0Dword@@QEAA@KH@Z; Dword::Dword(ulong,int)
0x140202317  mov     r9, rbx
0x14020231a  mov     r8, rax
0x14020231d  mov     rdx, [r15+18h]
0x140202321  mov     ecx, 0C0001F41h
0x140202326  call    ?Log@FrsEvent@@SAXW4FrsEventsEnum3@@PEBG11@Z; FrsEvent::Log(FrsEventsEnum3,ushort const *,ushort const *,ushort const *)
0x14020232b  nop
0x14020232c  mov     rcx, [rsp+240h+var_1E8]; Block
0x140202331  call    ??_V@YAXPEAXAEBUZeroFill@@@Z; operator delete[](void *,ZeroFill const &)
0x140202336  call    cs:__imp_GetCurrentThreadId
0x14020233d  nop     dword ptr [rax+rax+00h]
0x140202342  mov     [rsp+240h+var_200], rsi
0x140202347  mov     [rsp+240h+var_208], eax
0x14020234b  mov     [rsp+240h+var_210], 183h
0x140202353  lea     rax, aConfigAdwriter_14; "Config::AdWriter::CreateSysVolGlobalObj"...
0x14020235a  mov     [rsp+240h+var_218], rax
0x14020235f  lea     rax, aBaseFsRemotefs_38; "base\\fs\\remotefs\\frs\\src\\ad\\adwri"...
0x140202366  mov     [rsp+240h+var_220], rax
0x14020236b  mov     r9d, [rsi]
0x14020236e  mov     r8d, [rsi+8]
0x140202372  mov     edx, [rsi+4]
0x140202375  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14020237a  mov     rdi, rax
0x14020237d  lea     rcx, [rbp+140h+var_190]; this
0x140202381  call    ??1AdObject@Config@@QEAA@XZ; Config::AdObject::~AdObject(void)
0x140202386  jmp     loc_140202A19
0x14020238b  lea     rcx, [rsp+240h+var_1F0]; struct FrsStatus **
0x140202390  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x140202395  mov     r9, [r14+58h]; unsigned __int16 *
0x140202399  mov     r8, [r14+50h]; unsigned __int16 *
0x14020239d  lea     rdx, aMsdfsrContent; "msDFSR-Content"
0x1402023a4  lea     rcx, [rbp+140h+var_1C0]; this
0x1402023a8  call    ?AddObject@AdObjectEditor@Config@@QEAAPEAVFrsStatus@@PEBG00@Z; Config::AdObjectEditor::AddObject(ushort const *,ushort const *,ushort const *)
0x1402023ad  mov     rsi, rax
0x1402023b0  mov     [rsp+240h+var_1F0], rax
0x1402023b5  test    rax, rax
0x1402023b8  jz      loc_14020248F
0x1402023be  cmp     dword ptr [rax+4], 0B7h
0x1402023c5  jz      loc_140202485
0x1402023cb  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1402023d2  test    rax, rax
0x1402023d5  jz      short loc_14020241E
0x1402023d7  cmp     [rax+40h], edi
0x1402023da  jz      short loc_14020241E
0x1402023dc  cmp     dword ptr [rax+38h], 2
0x1402023e0  jl      short loc_14020241E
0x1402023e2  mov     [rbp+140h+var_70], r12
0x1402023e9  mov     [rbp+140h+var_68], 192h
0x1402023f3  mov     [rbp+140h+var_64], 2
0x1402023fd  lea     rax, aAdwr; "ADWR"
0x140202404  mov     [rbp+140h+var_60], rax
0x14020240b  lea     rdx, aSysvolFailedTo_12; "[SYSVOL] Failed to add content object"
0x140202412  lea     rcx, [rbp+140h+var_70]
0x140202419  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x14020241e  mov     rdx, rsi; struct FrsStatus *
0x140202421  lea     rcx, [rsp+240h+var_1E8]; this
0x140202426  call    ??0FrsStatusString@@QEAA@PEBVFrsStatus@@@Z; FrsStatusString::FrsStatusString(FrsStatus const *)
0x14020242b  nop
0x14020242c  mov     rbx, [rax]
0x14020242f  mov     r8d, 0Ah; int
0x140202435  mov     edx, [rsi+4]; unsigned int
0x140202438  lea     rcx, [rbp+140h+var_70]; this
0x14020243f  call    ??0Dword@@QEAA@KH@Z; Dword::Dword(ulong,int)
0x140202444  mov     r9, rbx
0x140202447  mov     r8, rax
0x14020244a  mov     rdx, [r15+18h]
0x14020244e  mov     ecx, 0C0001F41h
0x140202453  call    ?Log@FrsEvent@@SAXW4FrsEventsEnum3@@PEBG11@Z; FrsEvent::Log(FrsEventsEnum3,ushort const *,ushort const *,ushort const *)
0x140202458  nop
0x140202459  mov     rcx, [rsp+240h+var_1E8]; Block
0x14020245e  call    ??_V@YAXPEAXAEBUZeroFill@@@Z; operator delete[](void *,ZeroFill const &)
0x140202463  call    cs:__imp_GetCurrentThreadId
0x14020246a  nop     dword ptr [rax+rax+00h]
0x14020246f  mov     [rsp+240h+var_200], rsi
0x140202474  mov     [rsp+240h+var_208], eax
0x140202478  mov     [rsp+240h+var_210], 198h
0x140202480  jmp     loc_140202353
0x140202485  lea     rcx, [rsp+240h+var_1F0]; struct FrsStatus **
0x14020248a  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x14020248f  lea     rcx, [rbp+140h+var_130]; this
0x140202493  call    ??0AdObject@Config@@QEAA@XZ; Config::AdObject::AdObject(void)
0x140202498  nop
0x140202499  lea     rdx, aMsdfsrContents; "msDFSR-ContentSet"
0x1402024a0  lea     rcx, [rbp+140h+var_130]; this
0x1402024a4  call    ?SetClass@AdObject@Config@@QEAAXPEBG@Z; Config::AdObject::SetClass(ushort const *)
0x1402024a9  mov     rdx, [r14+70h]; unsigned __int16 *
0x1402024ad  lea     rcx, [rbp+140h+var_130]; this
0x1402024b1  call    ?SetCn@AdObject@Config@@QEAAXPEBG@Z; Config::AdObject::SetCn(ushort const *)
0x1402024b6  mov     rdx, [r14+78h]; unsigned __int16 *
0x1402024ba  lea     rcx, [rbp+140h+var_130]; this
0x1402024be  call    ?SetDn@AdObject@Config@@QEAAXPEBG@Z; Config::AdObject::SetDn(ushort const *)
0x1402024c3  lea     rsi, ?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1402024ca  mov     [rsp+240h+Block], rsi
0x1402024cf  mov     al, cs:byte_140315A80
0x1402024d5  test    al, al
0x1402024d7  jnz     short loc_1402024E6
0x1402024d9  lock inc cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1402024e0  mov     al, cs:byte_140315A80
0x1402024e6  mov     [rsp+240h+var_1C8], rsi
0x1402024eb  test    al, al
0x1402024ed  jnz     short loc_1402024F6
0x1402024ef  lock inc cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1402024f6  mov     ecx, 48h ; 'H'; Size
0x1402024fb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140202500  mov     [rsp+240h+var_1E0], rax
0x140202505  mov     rcx, rax; this
  ... truncated ...
```
