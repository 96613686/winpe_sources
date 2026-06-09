# Config::AdWriter::CreateSysVolObjects(void)

- ea: `0x140203d04`
- end: `0x14020430f`
- name: `?CreateSysVolObjects@AdWriter@Config@@QEAAPEAVFrsStatus@@XZ`
- size: `1547`
- prototype: `struct FrsStatus *__fastcall(Config::AdWriter *__hidden this)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1401ec574`

## callees

- `0x1400036a0`
- `0x14000c910`
- `0x14000e34c`
- `0x14001d7e8`
- `0x14001e4e4`
- `0x1400458e0`
- `0x14004be88`
- `0x14004d29c`
- `0x14004e1f0`
- `0x14004f450`
- `0x140050008`
- `0x14005c620`
- `0x1400c9520`
- `0x1400c95bc`
- `0x140105d38`
- `0x14010f988`
- `0x1401b3140`
- `0x1401b9494`
- `0x1401fb004`
- `0x1401fdf10`
- `0x1401ff76c`
- `0x140203d04`
- `0x140204318`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140203f25`
- `KERNEL32!GetCurrentThreadId` at `0x140203fb4`
- `KERNEL32!GetCurrentThreadId` at `0x14020404b`
- `KERNEL32!GetCurrentThreadId` at `0x1402040db`
- `KERNEL32!GetCurrentThreadId` at `0x14020426f`
- `KERNEL32!GetCurrentThreadId` at `0x140203f25`
- `KERNEL32!GetCurrentThreadId` at `0x140203fb4`
- `KERNEL32!GetCurrentThreadId` at `0x14020404b`
- `KERNEL32!GetCurrentThreadId` at `0x1402040db`
- `KERNEL32!GetCurrentThreadId` at `0x14020426f`

## string_xrefs

- `0x140203f4e`: `base\fs\remotefs\frs\src\config\reg.h`
- `0x140203fdd`: `base\fs\remotefs\frs\src\config\reg.h`
- `0x1402040c7`: `base\fs\remotefs\frs\src\config\reg.h`
- `0x140204298`: `base\fs\remotefs\frs\src\config\reg.h`
- `0x140204074`: `base\fs\remotefs\frs\src\ad\adwriter.cpp`
- `0x140203dfa`: `[SYSVOL] Objects already created`
- `0x140203d43`: `Config::AdWriter::CreateSysVolObjects`
- `0x140203d98`: `[SYSVOL] IsDc:%d isSysVolCreated:%d`
- `0x140204157`: `[SYSVOL] Seeding SysVol Commit Flag is set.`
- `0x140203e80`: `[SYSVOL] Promoting SysVol Commit Flag not set`
- `0x140203ebd`: `[SYSVOL] Promoting SysVol Commit Flag is set`
- `0x14020402b`: `[SYSVOL] Failed to delete promoting info`
- `0x140204068`: `Config::AdWriter::CreateSysVolObjects`
- `0x140204207`: `[MIG] Unable to set local state in AD. This can happen if the LocalSettings object is not created yet`
- `0x140204302`: `[SYSVOL] Promoting SysVol Commit Flag is deleted.`
- `0x14020428c`: `Config::RegWriter::DeletePromotingSysVolCommitFlag`
- `0x140203fd1`: `Config::RegWriter::WriteSeedingSysVolConfigValues`
- `0x1402040f8`: `Config::RegWriter::SetSeedingSysVolCommitFlag`
- `0x140203f42`: `Config::RegReader::ReadPromotingSysVolConfigValues`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
struct FrsStatus *__fastcall Config::AdWriter::CreateSysVolObjects(Config::AdWriter *this)
{
  int *v2; // rcx
  __int64 v3; // rbx
  const wchar_t *v4; // rdx
  bool v6; // zf
  Config::RegReader *v7; // rcx
  LPCRITICAL_SECTION v8; // rax
  struct FrsStatus *SysVolConfigValues; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v11; // rcx
  struct FrsStatus *SysVolObjectsWithParams; // rdi
  Config::RegWriter *v13; // rcx
  const unsigned __int16 *v14; // rdx
  Config::RegWriter *v15; // rcx
  struct FrsStatus *v16; // rdi
  DWORD v17; // eax
  __int64 v18; // rcx
  const wchar_t *v19; // rdx
  DWORD v20; // eax
  __int64 v21; // rcx
  ConfigContext *v22; // rcx
  struct FrsStatus *v23; // rdi
  DWORD v24; // eax
  __int64 v25; // rcx
  int v26; // r8d
  Config::RegWriter *v27; // rcx
  Config::RegWriter *v28; // rcx
  struct FrsStatus *v29; // rdi
  DWORD v30; // eax
  __int64 v31; // rcx
  void **v32; // [rsp+50h] [rbp-B0h] BYREF
  void *EventOrDie; // [rsp+58h] [rbp-A8h] BYREF
  const wchar_t *v34; // [rsp+60h] [rbp-A0h]
  unsigned int v35; // [rsp+68h] [rbp-98h] BYREF
  const wchar_t *v36; // [rsp+70h] [rbp-90h] BYREF
  int v37; // [rsp+78h] [rbp-88h]
  int v38; // [rsp+7Ch] [rbp-84h]
  const wchar_t *v39; // [rsp+80h] [rbp-80h]
  struct FrsStatus *v40[3]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v41[96]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v42[96]; // [rsp+100h] [rbp+0h] BYREF

  Config::SYSVOL_PARAMETERS::SYSVOL_PARAMETERS((Config::SYSVOL_PARAMETERS *)v42);
  v2 = (int *)g_DebugLog;
  v3 = 0;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v32 = (void **)L"Config::AdWriter::CreateSysVolObjects";
    EventOrDie = (void *)0x40000050CLL;
    v34 = L"ADWR";
    v35 = *(_DWORD *)(*((_QWORD *)this + 5) + 28LL);
    dbgobj::DbgPrint<unsigned short,int,int>(
      &v32,
      L"[SYSVOL] IsDc:%d isSysVolCreated:%d",
      &v35,
      &Config::AdConfig::isSysVolCreated);
    v2 = (int *)g_DebugLog;
  }
  if ( !*(_DWORD *)(*((_QWORD *)this + 5) + 28LL) )
  {
    if ( !v2 || !v2[16] || v2[14] < 4 )
      goto LABEL_16;
    LODWORD(EventOrDie) = 1295;
    v4 = L"[SYSVOL] Not a DC";
LABEL_15:
    v32 = (void **)L"Config::AdWriter::CreateSysVolObjects";
    HIDWORD(EventOrDie) = 4;
    v34 = L"ADWR";
    dbgobj::DbgPrint<unsigned short>(&v32, v4);
LABEL_16:
    Config::SYSVOL_PARAMETERS::~SYSVOL_PARAMETERS((Config::SYSVOL_PARAMETERS *)v42);
    return 0;
  }
  if ( Config::AdConfig::isSysVolCreated )
  {
    if ( !v2 || !v2[16] || v2[14] < 4 )
      goto LABEL_16;
    LODWORD(EventOrDie) = 1300;
    v4 = L"[SYSVOL] Objects already created";
    goto LABEL_15;
  }
  v40[1] = (struct FrsStatus *)&Config::RegReader::`vftable';
  v6 = (unsigned int)Config::RegReader::IsSysVolCommitFlagSet((Config::RegReader *)v2, L"Promoting SysVols") == 0;
  v8 = g_DebugLog;
  if ( v6 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v32 = (void **)L"Config::AdWriter::CreateSysVolObjects";
      EventOrDie = (void *)0x40000051ELL;
      v34 = L"ADWR";
      dbgobj::DbgPrint<unsigned short>(&v32, L"[SYSVOL] Promoting SysVol Commit Flag not set");
    }
    goto LABEL_42;
  }
  if ( g_DebugLog )
  {
    if ( LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v32 = (void **)L"Config::AdWriter::CreateSysVolObjects";
      EventOrDie = (void *)0x400000522LL;
      v34 = L"ADWR";
      dbgobj::DbgPrint<unsigned short>(&v32, L"[SYSVOL] Promoting SysVol Commit Flag is set");
      v8 = g_DebugLog;
    }
    if ( v8 && LODWORD(v8[1].LockSemaphore) && SLODWORD(v8[1].OwningThread) >= 4 )
    {
      v32 = (void **)L"Config::AdWriter::CreateSysVolObjects";
      EventOrDie = (void *)0x400000527LL;
      v34 = L"ADWR";
      dbgobj::DbgPrint<unsigned short>(&v32, L"[SYSVOL] Creating SysVol objects");
    }
  }
  SysVolConfigValues = Config::RegReader::ReadSysVolConfigValues(
                         v7,
                         L"Promoting SysVols",
                         (struct Config::SYSVOL_PARAMETERS *)v42);
  if ( SysVolConfigValues )
  {
    CurrentThreadId = GetCurrentThreadId();
    SysVolObjectsWithParams = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                    v11,
                                                    *((unsigned int *)SysVolConfigValues + 1),
                                                    *((unsigned int *)SysVolConfigValues + 2),
                                                    *(unsigned int *)SysVolConfigValues,
                                                    "base\\fs\\remotefs\\frs\\src\\config\\reg.h",
                                                    "Config::RegReader::ReadPromotingSysVolConfigValues",
                                                    437,
                                                    CurrentThreadId,
                                                    SysVolConfigValues);
    if ( SysVolObjectsWithParams )
      goto LABEL_41;
  }
  SysVolObjectsWithParams = Config::AdWriter::CreateSysVolObjectsWithParams(
                              this,
                              (struct Config::SYSVOL_PARAMETERS *)v42);
  if ( SysVolObjectsWithParams )
    goto LABEL_41;
  v40[2] = (struct FrsStatus *)&Config::RegWriter::`vftable';
  v16 = Config::RegWriter::WriteSysVolConfigValues(
          v13,
          L"Seeding SysVols",
          (const struct Config::SYSVOL_PARAMETERS *)v42);
  if ( v16 )
  {
    v17 = GetCurrentThreadId();
    SysVolObjectsWithParams = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                    v18,
                                                    *((unsigned int *)v16 + 1),
                                                    *((unsigned int *)v16 + 2),
                                                    *(unsigned int *)v16,
                                                    "base\\fs\\remotefs\\frs\\src\\config\\reg.h",
                                                    "Config::RegWriter::WriteSeedingSysVolConfigValues",
                                                    630,
                                                    v17,
                                                    v16);
    if ( SysVolObjectsWithParams )
      goto LABEL_37;
  }
  v23 = Config::RegWriter::SetSysVolCommitFlag(v15, v14);
  if ( v23 )
  {
    v24 = GetCurrentThreadId();
    SysVolObjectsWithParams = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                    v25,
                                                    *((unsigned int *)v23 + 1),
                                                    *((unsigned int *)v23 + 2),
                                                    *(unsigned int *)v23,
                                                    "base\\fs\\remotefs\\frs\\src\\config\\reg.h",
                                                    "Config::RegWriter::SetSeedingSysVolCommitFlag",
                                                    676,
                                                    v24,
                                                    v23);
  }
  else
  {
    SysVolObjectsWithParams = 0;
  }
  if ( SysVolObjectsWithParams )
    goto LABEL_37;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v32 = (void **)L"Config::AdWriter::CreateSysVolObjects";
    EventOrDie = (void *)0x400000540LL;
    v34 = L"ADWR";
    dbgobj::DbgPrint<unsigned short>(&v32, L"[SYSVOL] Seeding SysVol Commit Flag is set.");
  }
  ConfigContext::SetSeedingSysVolInfo(v22, (struct Config::SYSVOL_PARAMETERS *)v42);
  Config::AdConfig::isSysVolCreated = 1;
  v32 = &ShutdownObject::`vftable';
  LODWORD(v34) = 0;
  EventOrDie = CreateEventOrDie(1, 0);
  Migration::SysVolMigration::SysVolMigration((Migration::SysVolMigration *)v41, (struct ShutdownObject *)&v32, v26);
  v35 = 0;
  SysVolObjectsWithParams = Migration::SysVolUtil::GetLocalStateFromRegistry(
                              (enum Migration::_MIGRATION_STATE *)&v35,
                              1);
  if ( !SysVolObjectsWithParams )
  {
    SysVolObjectsWithParams = (struct FrsStatus *)Migration::SysVolMigration::SetLocalState(v41, v35);
    v40[0] = SysVolObjectsWithParams;
    if ( SysVolObjectsWithParams )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v36 = L"Config::AdWriter::CreateSysVolObjects";
        v37 = 1370;
        v38 = 4;
        v39 = L"ADWR";
        dbgobj::DbgPrint<unsigned short>(
          &v36,
          L"[MIG] Unable to set local state in AD. This can happen if the LocalSettings object is not created yet");
      }
      CLEAR_ERROR(v40);
      SysVolObjectsWithParams = v40[0];
    }
  }
  if ( !SysVolObjectsWithParams && v35 == 3 )
    SysVolObjectsWithParams = Migration::SysVolUtil::RemoveNtfrsDependencyOnNtds();
  if ( (Migration::SysVolMigration::~SysVolMigration((Migration::SysVolMigration *)v41),
        v32 = &ShutdownObject::`vftable',
        CloseHandleEx(&EventOrDie),
        SysVolObjectsWithParams)
    || (v29 = Config::RegWriter::DeleteSysVolCommitFlag(v27, L"Promoting SysVols")) != 0
    && (v30 = GetCurrentThreadId(),
        (SysVolObjectsWithParams = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                         v31,
                                                         *((unsigned int *)v29 + 1),
                                                         *((unsigned int *)v29 + 2),
                                                         *(unsigned int *)v29,
                                                         "base\\fs\\remotefs\\frs\\src\\config\\reg.h",
                                                         "Config::RegWriter::DeletePromotingSysVolCommitFlag",
                                                         688,
                                                         v30,
                                                         v29)) != 0)
    || (SysVolObjectsWithParams = Config::RegWriter::DeletePromotingSysVolSubKeys(v28, 0)) != 0 )
  {
LABEL_37:
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
    {
      v37 = 1400;
      v38 = 2;
      v19 = L"[SYSVOL] Failed to delete promoting info";
LABEL_39:
      v36 = L"Config::AdWriter::CreateSysVolObjects";
      v39 = L"ADWR";
      dbgobj::DbgPrint<unsigned short>(&v36, v19);
    }
  }
  else if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v37 = 1398;
    v38 = 4;
    v19 = L"[SYSVOL] Promoting SysVol Commit Flag is deleted.";
    goto LABEL_39;
  }
  if ( SysVolObjectsWithParams )
  {
LABEL_41:
    v20 = GetCurrentThreadId();
    v3 = FrsStatusList::PushNewError(
           v21,
           *((unsigned int *)SysVolObjectsWithParams + 1),
           *((unsigned int *)SysVolObjectsWithParams + 2),
           *(unsigned int *)SysVolObjectsWithParams,
           "base\\fs\\remotefs\\frs\\src\\ad\\adwriter.cpp",
           "Config::AdWriter::CreateSysVolObjects",
           1404,
           v20,
           SysVolObjectsWithParams);
  }
LABEL_42:
  Config::SYSVOL_PARAMETERS::~SYSVOL_PARAMETERS((Config::SYSVOL_PARAMETERS *)v42);
  return (struct FrsStatus *)v3;
}

```

## disassembly

```asm
0x140203d04  mov     [rsp-8+arg_8], rbx
0x140203d09  mov     [rsp-8+arg_10], rsi
0x140203d0e  push    rbp
0x140203d0f  push    rdi
0x140203d10  push    r12
0x140203d12  push    r14
0x140203d14  push    r15
0x140203d16  lea     rbp, [rsp-70h]
0x140203d1b  sub     rsp, 170h
0x140203d22  mov     rax, cs:__security_cookie
0x140203d29  xor     rax, rsp
0x140203d2c  mov     [rbp+90h+var_30], rax
0x140203d30  mov     rsi, rcx
0x140203d33  lea     rcx, [rbp+90h+var_90]; this
0x140203d37  call    ??0SYSVOL_PARAMETERS@Config@@QEAA@XZ; Config::SYSVOL_PARAMETERS::SYSVOL_PARAMETERS(void)
0x140203d3c  nop
0x140203d3d  mov     r14d, 4
0x140203d43  lea     r15, aConfigAdwriter_23; "Config::AdWriter::CreateSysVolObjects"
0x140203d4a  lea     r12, aAdwr; "ADWR"
0x140203d51  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140203d58  xor     ebx, ebx
0x140203d5a  test    rcx, rcx
0x140203d5d  jz      short loc_140203DB0
0x140203d5f  cmp     [rcx+40h], ebx
0x140203d62  jz      short loc_140203DB0
0x140203d64  cmp     [rcx+38h], r14d
0x140203d68  jl      short loc_140203DB0
0x140203d6a  mov     [rsp+190h+var_140], r15
0x140203d6f  mov     dword ptr [rsp+190h+var_138], 50Ch
0x140203d77  mov     dword ptr [rsp+190h+var_138+4], r14d
0x140203d7c  mov     [rsp+190h+var_130], r12
0x140203d81  mov     rax, [rsi+28h]
0x140203d85  mov     ecx, [rax+1Ch]
0x140203d88  mov     [rsp+190h+var_128], ecx
0x140203d8c  lea     r9, ?isSysVolCreated@AdConfig@Config@@1HA; int Config::AdConfig::isSysVolCreated
0x140203d93  lea     r8, [rsp+190h+var_128]
0x140203d98  lea     rdx, aSysvolIsdcDIss; "[SYSVOL] IsDc:%d isSysVolCreated:%d"
0x140203d9f  lea     rcx, [rsp+190h+var_140]
0x140203da4  call    ??$DbgPrint@GHH@dbgobj@@QEAA_KPEBGAEBH1@Z; dbgobj::DbgPrint<ushort,int,int>(ushort const *,int const &,int const &)
0x140203da9  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; this
0x140203db0  mov     rax, [rsi+28h]
0x140203db4  cmp     [rax+1Ch], ebx
0x140203db7  jnz     short loc_140203DDA
0x140203db9  test    rcx, rcx
0x140203dbc  jz      short loc_140203E1B
0x140203dbe  cmp     [rcx+40h], ebx
0x140203dc1  jz      short loc_140203E1B
0x140203dc3  cmp     [rcx+38h], r14d
0x140203dc7  jl      short loc_140203E1B
0x140203dc9  mov     dword ptr [rsp+190h+var_138], 50Fh
0x140203dd1  lea     rdx, aSysvolNotADc; "[SYSVOL] Not a DC"
0x140203dd8  jmp     short loc_140203E01
0x140203dda  cmp     cs:?isSysVolCreated@AdConfig@Config@@1HA, ebx; int Config::AdConfig::isSysVolCreated
0x140203de0  jz      short loc_140203E2B
0x140203de2  test    rcx, rcx
0x140203de5  jz      short loc_140203E1B
0x140203de7  cmp     [rcx+40h], ebx
0x140203dea  jz      short loc_140203E1B
0x140203dec  cmp     [rcx+38h], r14d
0x140203df0  jl      short loc_140203E1B
0x140203df2  mov     dword ptr [rsp+190h+var_138], 514h
0x140203dfa  lea     rdx, aSysvolObjectsA; "[SYSVOL] Objects already created"
0x140203e01  mov     [rsp+190h+var_140], r15
0x140203e06  mov     dword ptr [rsp+190h+var_138+4], r14d
0x140203e0b  mov     [rsp+190h+var_130], r12
0x140203e10  lea     rcx, [rsp+190h+var_140]
0x140203e15  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x140203e1a  nop
0x140203e1b  lea     rcx, [rbp+90h+var_90]; this
0x140203e1f  call    ??1SYSVOL_PARAMETERS@Config@@QEAA@XZ; Config::SYSVOL_PARAMETERS::~SYSVOL_PARAMETERS(void)
0x140203e24  xor     eax, eax
0x140203e26  jmp     loc_14020409E
0x140203e2b  lea     rax, ??_7RegReader@Config@@6B@; const Config::RegReader::`vftable'
0x140203e32  mov     [rbp+90h+var_100], rax
0x140203e36  lea     rdx, aPromotingSysvo; "Promoting SysVols"
0x140203e3d  call    ?IsSysVolCommitFlagSet@RegReader@Config@@QEAAHPEBG@Z; Config::RegReader::IsSysVolCommitFlagSet(ushort const *)
0x140203e42  test    eax, eax
0x140203e44  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140203e4b  jnz     short loc_140203E96
0x140203e4d  test    rax, rax
0x140203e50  jz      loc_140204092
0x140203e56  cmp     [rax+40h], ebx
0x140203e59  jz      loc_140204092
0x140203e5f  cmp     [rax+38h], r14d
0x140203e63  jl      loc_140204092
0x140203e69  mov     [rsp+190h+var_140], r15
0x140203e6e  mov     dword ptr [rsp+190h+var_138], 51Eh
0x140203e76  mov     dword ptr [rsp+190h+var_138+4], r14d
0x140203e7b  mov     [rsp+190h+var_130], r12
0x140203e80  lea     rdx, aSysvolPromotin; "[SYSVOL] Promoting SysVol Commit Flag n"...
0x140203e87  lea     rcx, [rsp+190h+var_140]
0x140203e8c  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x140203e91  jmp     loc_140204092
0x140203e96  test    rax, rax
0x140203e99  jz      short loc_140203F0D
0x140203e9b  cmp     [rax+40h], ebx
0x140203e9e  jz      short loc_140203ED5
0x140203ea0  cmp     [rax+38h], r14d
0x140203ea4  jl      short loc_140203ED5
0x140203ea6  mov     [rsp+190h+var_140], r15
0x140203eab  mov     dword ptr [rsp+190h+var_138], 522h
0x140203eb3  mov     dword ptr [rsp+190h+var_138+4], r14d
0x140203eb8  mov     [rsp+190h+var_130], r12
0x140203ebd  lea     rdx, aSysvolPromotin_1; "[SYSVOL] Promoting SysVol Commit Flag i"...
0x140203ec4  lea     rcx, [rsp+190h+var_140]
0x140203ec9  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x140203ece  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140203ed5  test    rax, rax
0x140203ed8  jz      short loc_140203F0D
0x140203eda  cmp     [rax+40h], ebx
0x140203edd  jz      short loc_140203F0D
0x140203edf  cmp     [rax+38h], r14d
0x140203ee3  jl      short loc_140203F0D
0x140203ee5  mov     [rsp+190h+var_140], r15
0x140203eea  mov     dword ptr [rsp+190h+var_138], 527h
0x140203ef2  mov     dword ptr [rsp+190h+var_138+4], r14d
0x140203ef7  mov     [rsp+190h+var_130], r12
0x140203efc  lea     rdx, aSysvolCreating; "[SYSVOL] Creating SysVol objects"
0x140203f03  lea     rcx, [rsp+190h+var_140]
0x140203f08  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x140203f0d  lea     r8, [rbp+90h+var_90]; struct Config::SYSVOL_PARAMETERS *
0x140203f11  lea     rdx, aPromotingSysvo; "Promoting SysVols"
0x140203f18  call    ?ReadSysVolConfigValues@RegReader@Config@@QEAAPEAVFrsStatus@@PEBGAEAUSYSVOL_PARAMETERS@2@@Z; Config::RegReader::ReadSysVolConfigValues(ushort const *,Config::SYSVOL_PARAMETERS &)
0x140203f1d  mov     rdi, rax
0x140203f20  test    rax, rax
0x140203f23  jz      short loc_140203F75
0x140203f25  call    cs:__imp_GetCurrentThreadId
0x140203f2c  nop     dword ptr [rax+rax+00h]
0x140203f31  mov     [rsp+190h+var_150], rdi
0x140203f36  mov     [rsp+190h+var_158], eax
0x140203f3a  mov     [rsp+190h+var_160], 1B5h
0x140203f42  lea     rax, aConfigRegreade_1; "Config::RegReader::ReadPromotingSysVolC"...
0x140203f49  mov     [rsp+190h+var_168], rax
0x140203f4e  lea     rax, aBaseFsRemotefs_17; "base\\fs\\remotefs\\frs\\src\\config\\r"...
0x140203f55  mov     [rsp+190h+var_170], rax
0x140203f5a  mov     r9d, [rdi]
0x140203f5d  mov     r8d, [rdi+8]
0x140203f61  mov     edx, [rdi+4]
0x140203f64  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140203f69  mov     rdi, rax
0x140203f6c  test    rax, rax
0x140203f6f  jnz     loc_14020404B
0x140203f75  lea     rdx, [rbp+90h+var_90]; struct Config::SYSVOL_PARAMETERS *
0x140203f79  mov     rcx, rsi; this
0x140203f7c  call    ?CreateSysVolObjectsWithParams@AdWriter@Config@@IEAAPEAVFrsStatus@@AEAUSYSVOL_PARAMETERS@2@@Z; Config::AdWriter::CreateSysVolObjectsWithParams(Config::SYSVOL_PARAMETERS &)
0x140203f81  mov     rdi, rax
0x140203f84  test    rax, rax
0x140203f87  jnz     loc_14020404B
0x140203f8d  lea     rax, ??_7RegWriter@Config@@6B@; const Config::RegWriter::`vftable'
0x140203f94  mov     [rbp+90h+var_F8], rax
0x140203f98  lea     r8, [rbp+90h+var_90]; struct Config::SYSVOL_PARAMETERS *
0x140203f9c  lea     rdx, aSeedingSysvols; "Seeding SysVols"
0x140203fa3  call    ?WriteSysVolConfigValues@RegWriter@Config@@QEAAPEAVFrsStatus@@PEBGAEBUSYSVOL_PARAMETERS@2@@Z; Config::RegWriter::WriteSysVolConfigValues(ushort const *,Config::SYSVOL_PARAMETERS const &)
0x140203fa8  mov     rdi, rax
0x140203fab  test    rax, rax
0x140203fae  jz      loc_1402040C7
0x140203fb4  call    cs:__imp_GetCurrentThreadId
0x140203fbb  nop     dword ptr [rax+rax+00h]
0x140203fc0  mov     [rsp+190h+var_150], rdi
0x140203fc5  mov     [rsp+190h+var_158], eax
0x140203fc9  mov     [rsp+190h+var_160], 276h
0x140203fd1  lea     rax, aConfigRegwrite_14; "Config::RegWriter::WriteSeedingSysVolCo"...
0x140203fd8  mov     [rsp+190h+var_168], rax
0x140203fdd  lea     rsi, aBaseFsRemotefs_17; "base\\fs\\remotefs\\frs\\src\\config\\r"...
0x140203fe4  mov     [rsp+190h+var_170], rsi
0x140203fe9  mov     r9d, [rdi]
0x140203fec  mov     r8d, [rdi+8]
0x140203ff0  mov     edx, [rdi+4]
0x140203ff3  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140203ff8  mov     rdi, rax
0x140203ffb  test    rax, rax
0x140203ffe  jz      loc_1402040CE
0x140204004  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14020400b  test    rax, rax
0x14020400e  jz      short loc_140204046
0x140204010  cmp     [rax+40h], ebx
0x140204013  jz      short loc_140204046
0x140204015  cmp     dword ptr [rax+38h], 2
0x140204019  jl      short loc_140204046
0x14020401b  mov     [rsp+190h+var_118], 578h
0x140204023  mov     [rsp+190h+var_114], 2
0x14020402b  lea     rdx, aSysvolFailedTo; "[SYSVOL] Failed to delete promoting inf"...
0x140204032  mov     [rsp+190h+var_120], r15
0x140204037  mov     [rbp+90h+var_110], r12
0x14020403b  lea     rcx, [rsp+190h+var_120]
0x140204040  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x140204045  nop
0x140204046  test    rdi, rdi
0x140204049  jz      short loc_140204092
0x14020404b  call    cs:__imp_GetCurrentThreadId
0x140204052  nop     dword ptr [rax+rax+00h]
0x140204057  mov     [rsp+190h+var_150], rdi
0x14020405c  mov     [rsp+190h+var_158], eax
0x140204060  mov     [rsp+190h+var_160], 57Ch
0x140204068  lea     rax, aConfigAdwriter_4; "Config::AdWriter::CreateSysVolObjects"
0x14020406f  mov     [rsp+190h+var_168], rax
0x140204074  lea     rax, aBaseFsRemotefs_38; "base\\fs\\remotefs\\frs\\src\\ad\\adwri"...
0x14020407b  mov     [rsp+190h+var_170], rax
0x140204080  mov     r9d, [rdi]
0x140204083  mov     r8d, [rdi+8]
0x140204087  mov     edx, [rdi+4]
0x14020408a  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14020408f  mov     rbx, rax
0x140204092  lea     rcx, [rbp+90h+var_90]; this
0x140204096  call    ??1SYSVOL_PARAMETERS@Config@@QEAA@XZ; Config::SYSVOL_PARAMETERS::~SYSVOL_PARAMETERS(void)
0x14020409b  mov     rax, rbx
0x14020409e  mov     rcx, [rbp+90h+var_30]
0x1402040a2  xor     rcx, rsp; StackCookie
0x1402040a5  call    __security_check_cookie
0x1402040aa  lea     r11, [rsp+190h+var_20]
0x1402040b2  mov     rbx, [r11+38h]
0x1402040b6  mov     rsi, [r11+40h]
0x1402040ba  mov     rsp, r11
0x1402040bd  pop     r15
0x1402040bf  pop     r14
0x1402040c1  pop     r12
0x1402040c3  pop     rdi
0x1402040c4  pop     rbp
0x1402040c5  retn
0x1402040c7  lea     rsi, aBaseFsRemotefs_17; "base\\fs\\remotefs\\frs\\src\\config\\r"...
0x1402040ce  call    ?SetSysVolCommitFlag@RegWriter@Config@@QEAAPEAVFrsStatus@@PEBG@Z; Config::RegWriter::SetSysVolCommitFlag(ushort const *)
0x1402040d3  mov     rdi, rax
0x1402040d6  test    rax, rax
0x1402040d9  jz      short loc_14020411D
0x1402040db  call    cs:__imp_GetCurrentThreadId
0x1402040e2  nop     dword ptr [rax+rax+00h]
0x1402040e7  mov     [rsp+190h+var_150], rdi
0x1402040ec  mov     [rsp+190h+var_158], eax
0x1402040f0  mov     [rsp+190h+var_160], 2A4h
0x1402040f8  lea     rax, aConfigRegwrite_11; "Config::RegWriter::SetSeedingSysVolComm"...
0x1402040ff  mov     [rsp+190h+var_168], rax
0x140204104  mov     [rsp+190h+var_170], rsi
0x140204109  mov     r9d, [rdi]
0x14020410c  mov     r8d, [rdi+8]
0x140204110  mov     edx, [rdi+4]
0x140204113  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140204118  mov     rdi, rax
0x14020411b  jmp     short loc_140204120
0x14020411d  mov     rdi, rbx
0x140204120  test    rdi, rdi
0x140204123  jnz     loc_140204004
0x140204129  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140204130  test    rax, rax
0x140204133  jz      short loc_140204168
0x140204135  cmp     [rax+40h], ebx
0x140204138  jz      short loc_140204168
0x14020413a  cmp     [rax+38h], r14d
0x14020413e  jl      short loc_140204168
0x140204140  mov     [rsp+190h+var_140], r15
0x140204145  mov     dword ptr [rsp+190h+var_138], 540h
0x14020414d  mov     dword ptr [rsp+190h+var_138+4], r14d
0x140204152  mov     [rsp+190h+var_130], r12
0x140204157  lea     rdx, aSysvolSeedingS; "[SYSVOL] Seeding SysVol Commit Flag is "...
0x14020415e  lea     rcx, [rsp+190h+var_140]
0x140204163  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x140204168  lea     rdx, [rbp+90h+var_90]; struct Config::SYSVOL_PARAMETERS *
0x14020416c  call    ?SetSeedingSysVolInfo@ConfigContext@@QEAAXAEAUSYSVOL_PARAMETERS@Config@@@Z; ConfigContext::SetSeedingSysVolInfo(Config::SYSVOL_PARAMETERS &)
0x140204171  mov     edi, 1
0x140204176  mov     cs:?isSysVolCreated@AdConfig@Config@@1HA, edi; int Config::AdConfig::isSysVolCreated
0x14020417c  lea     rsi, ??_7ShutdownObject@@6B@; const ShutdownObject::`vftable'
0x140204183  mov     [rsp+190h+var_140], rsi
0x140204188  mov     dword ptr [rsp+190h+var_130], ebx
0x14020418c  xor     edx, edx; bInitialState
0x14020418e  mov     ecx, edi; bManualReset
0x140204190  call    ?CreateEventOrDie@@YAPEAXHH@Z; CreateEventOrDie(int,int)
0x140204195  mov     [rsp+190h+var_138], rax
0x14020419a  lea     rdx, [rsp+190h+var_140]; struct ShutdownObject *
0x14020419f  lea     rcx, [rbp+90h+var_F0]; this
0x1402041a3  call    ??0SysVolMigration@Migration@@QEAA@AEAVShutdownObject@@H@Z; Migration::SysVolMigration::SysVolMigration(ShutdownObject &,int)
0x1402041a8  nop
0x1402041a9  mov     [rsp+190h+var_128], ebx
0x1402041ad  mov     edx, edi; int
0x1402041af  lea     rcx, [rsp+190h+var_128]; enum Migration::_MIGRATION_STATE *
0x1402041b4  call    ?GetLocalStateFromRegistry@SysVolUtil@Migration@@SAPEAVFrsStatus@@AEAW4_MIGRATION_STATE@2@H@Z; Migration::SysVolUtil::GetLocalStateFromRegistry(Migration::_MIGRATION_STATE &,int)
0x1402041b9  mov     rdi, rax
0x1402041bc  test    rax, rax
0x1402041bf  jnz     short loc_140204225
0x1402041c1  mov     edx, [rsp+190h+var_128]
0x1402041c5  lea     rcx, [rbp+90h+var_F0]
0x1402041c9  call    ?SetLocalState@SysVolMigration@Migration@@QEAAPEAVFrsStatus@@W4_MIGRATION_STATE@2@@Z; Migration::SysVolMigration::SetLocalState(Migration::_MIGRATION_STATE)
0x1402041ce  mov     rdi, rax
0x1402041d1  mov     [rbp+90h+var_108], rax
0x1402041d5  test    rax, rax
0x1402041d8  jz      short loc_140204225
0x1402041da  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1402041e1  test    rax, rax
0x1402041e4  jz      short loc_140204218
0x1402041e6  cmp     [rax+40h], ebx
0x1402041e9  jz      short loc_140204218
0x1402041eb  cmp     [rax+38h], r14d
0x1402041ef  jl      short loc_140204218
0x1402041f1  mov     [rsp+190h+var_120], r15
0x1402041f6  mov     [rsp+190h+var_118], 55Ah
0x1402041fe  mov     [rsp+190h+var_114], r14d
0x140204203  mov     [rbp+90h+var_110], r12
0x140204207  lea     rdx, aMigUnableToSet; "[MIG] Unable to set local state in AD. "...
0x14020420e  lea     rcx, [rsp+190h+var_120]
0x140204213  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x140204218  lea     rcx, [rbp+90h+var_108]; struct FrsStatus **
0x14020421c  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
  ... truncated ...
```
