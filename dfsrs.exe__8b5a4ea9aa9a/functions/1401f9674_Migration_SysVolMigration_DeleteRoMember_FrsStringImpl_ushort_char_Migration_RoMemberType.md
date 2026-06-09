# Migration::SysVolMigration::DeleteRoMember(FrsStringImpl<ushort,char> &,Migration::RoMemberType)

- ea: `0x1401f9674`
- end: `0x1401f9e60`
- name: `?DeleteRoMember@SysVolMigration@Migration@@QEAAPEAVFrsStatus@@AEAV?$FrsStringImpl@GD@@W4RoMemberType@2@@Z`
- size: `2028`
- prototype: `__int64 __fastcall(Migration::SysVolMigration *this)`
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1401fcb2c`

## callees

- `0x14000e34c`
- `0x14000ee94`
- `0x14001c6c0`
- `0x14001cfa0`
- `0x1401b90b4`
- `0x1401b9494`
- `0x1401f5f80`
- `0x1401f6034`
- `0x1401f60d4`
- `0x1401f6188`
- `0x1401f624c`
- `0x1401f6bd4`
- `0x1401f7f60`
- `0x1401f8ba4`
- `0x1401f9674`
- `0x1401fa3a8`
- `0x1401fa544`
- `0x1401facd8`
- `0x1401faec0`
- `0x1401fb404`
- `0x1401fc2fc`
- `0x1402014e0`
- `0x140205868`
- `0x1402058c8`
- `0x1402059ec`
- `0x140205a34`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1401f97f6`
- `KERNEL32!GetCurrentThreadId` at `0x1401f9826`
- `KERNEL32!GetCurrentThreadId` at `0x1401f9ceb`
- `KERNEL32!GetCurrentThreadId` at `0x1401f9d1c`
- `KERNEL32!GetCurrentThreadId` at `0x1401f9d9c`
- `KERNEL32!GetCurrentThreadId` at `0x1401f9df9`
- `KERNEL32!GetCurrentThreadId` at `0x1401f97f6`
- `KERNEL32!GetCurrentThreadId` at `0x1401f9826`
- `KERNEL32!GetCurrentThreadId` at `0x1401f9ceb`
- `KERNEL32!GetCurrentThreadId` at `0x1401f9d1c`
- `KERNEL32!GetCurrentThreadId` at `0x1401f9d9c`
- `KERNEL32!GetCurrentThreadId` at `0x1401f9df9`

## string_xrefs

- `0x1401f96a8`: `Migration::SysVolMigration::DeleteRoMember`
- `0x1401f97a9`: `Migration::SysVolMigration::DeleteRoMember`
- `0x1401f99d5`: `Migration::SysVolMigration::DeleteRoMember`
- `0x1401f9ad4`: `Migration::SysVolMigration::DeleteRoMember`
- `0x1401f9be0`: `Migration::SysVolMigration::DeleteRoMember`
- `0x1401f9cb8`: `Migration::SysVolMigration::DeleteRoMember`
- `0x1401f9d6f`: `Migration::SysVolMigration::DeleteRoMember`
- `0x1401f9848`: `Migration::SysVolMigration::DeleteRoMember`
- `0x1401f9dbe`: `Migration::SysVolMigration::DeleteRoMember`
- `0x1401f9e16`: `Migration::SysVolMigration::DeleteRoMember`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Migration::SysVolMigration::DeleteRoMember(Migration::SysVolMigration *this, __int64 *a2, int a3)
{
  __int64 v5; // rbx
  struct FrsStatus *GlobalState; // rdi
  const wchar_t *v7; // rdx
  __int64 v8; // rcx
  struct FrsStatus *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rcx
  int i; // eax
  int v13; // r14d
  struct DS_DOMAIN_CONTROLLER_INFO_3W *Dc; // rax
  int v15; // eax
  struct FrsStatus *v16; // rax
  int v17; // edx
  int v18; // eax
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rcx
  FrsStatus *v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rcx
  DWORD v26; // eax
  __int64 v27; // rcx
  DWORD CurrentThreadId; // [rsp+40h] [rbp-41h]
  DWORD v30; // [rsp+40h] [rbp-41h]
  DWORD v31; // [rsp+40h] [rbp-41h]
  DWORD v32; // [rsp+40h] [rbp-41h]
  DWORD v33; // [rsp+40h] [rbp-41h]
  int v34; // [rsp+58h] [rbp-29h] BYREF
  struct FrsStatus *v35; // [rsp+60h] [rbp-21h] BYREF
  const wchar_t *v36; // [rsp+68h] [rbp-19h] BYREF
  int v37; // [rsp+70h] [rbp-11h]
  int v38; // [rsp+74h] [rbp-Dh]
  const wchar_t *v39; // [rsp+78h] [rbp-9h]
  _BYTE v40[8]; // [rsp+80h] [rbp-1h] BYREF
  const wchar_t *v41; // [rsp+88h] [rbp+7h] BYREF
  __int64 v42; // [rsp+90h] [rbp+Fh]
  __int64 v43; // [rsp+98h] [rbp+17h]
  unsigned __int16 *v44; // [rsp+A0h] [rbp+1Fh] BYREF
  _BYTE v45[16]; // [rsp+A8h] [rbp+27h] BYREF
  int v46; // [rsp+F8h] [rbp+77h] BYREF
  int v47; // [rsp+100h] [rbp+7Fh] BYREF

  v46 = a3;
  v5 = 0;
  GlobalState = 0;
  v35 = 0;
  v7 = L"SYSM";
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v41 = L"Migration::SysVolMigration::DeleteRoMember";
    v42 = 0x40000111DLL;
    v43 = (__int64)L"SYSM";
    dbgobj::DbgPrint<unsigned short,enum Migration::RoMemberType>(&v41, L"SYSM", &v46);
  }
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD, const wchar_t *))(**((_QWORD **)this + 10) + 48LL))(
         *((_QWORD *)this + 10),
         v7)
    || (GlobalState = Migration::SysVolMigration::IsLocalComputerLongHornLevelReplicaDc(this), (v35 = GlobalState) == 0) )
  {
    if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 48LL))(*((_QWORD *)this + 10)) )
    {
      GlobalState = Migration::SysVolMigration::Connect(this);
      v35 = GlobalState;
    }
  }
  v47 = 0;
  if ( GlobalState )
    goto LABEL_99;
  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 48LL))(*((_QWORD *)this + 10)) )
  {
    GlobalState = Migration::SysVolMigration::GetGlobalState(this, (enum Migration::_MIGRATION_STATE *)&v47);
    v35 = GlobalState;
    if ( GlobalState )
      goto LABEL_99;
  }
  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 48LL))(*((_QWORD *)this + 10)) )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v36 = L"Migration::SysVolMigration::DeleteRoMember";
      v37 = 4401;
      v38 = 4;
      v39 = L"SYSM";
      dbgobj::DbgPrint<unsigned short,enum Migration::_MIGRATION_STATE>(&v36, L"[MIG] Current global state is %?", &v47);
    }
    if ( v46 == 2 )
    {
      if ( !v47 )
        goto LABEL_24;
      CurrentThreadId = GetCurrentThreadId();
      v9 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v8,
                                 9506,
                                 0,
                                 3,
                                 "base\\fs\\remotefs\\frs\\src\\ad\\migration.cpp",
                                 "Migration::SysVolMigration::DeleteRoMember",
                                 4405,
                                 CurrentThreadId,
                                 0);
    }
    else
    {
      if ( v46 != 1 || v47 == 3 )
        goto LABEL_24;
      v30 = GetCurrentThreadId();
      v9 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v10,
                                 9504,
                                 0,
                                 3,
                                 "base\\fs\\remotefs\\frs\\src\\ad\\migration.cpp",
                                 "Migration::SysVolMigration::DeleteRoMember",
                                 4410,
                                 v30,
                                 0);
    }
    GlobalState = v9;
    v35 = v9;
    if ( v9 )
    {
LABEL_99:
      v26 = GetCurrentThreadId();
      return FrsStatusList::PushNewError(
               v27,
               *((unsigned int *)GlobalState + 1),
               *((unsigned int *)GlobalState + 2),
               *(unsigned int *)GlobalState,
               "base\\fs\\remotefs\\frs\\src\\ad\\migration.cpp",
               "Migration::SysVolMigration::DeleteRoMember",
               4516,
               v26,
               GlobalState);
    }
  }
LABEL_24:
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 48LL))(*((_QWORD *)this + 10)) )
    return v5;
  v11 = *a2;
  if ( *(_QWORD *)(*a2 + 8) )
  {
    v34 = 0;
    GlobalState = Migration::SysVolUtil::GetComputerDcRole((const unsigned __int16 *)(v11 + 18), (int *)&v35, &v34);
    if ( GlobalState
      || (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 48LL))(*((_QWORD *)this + 10))
      || !v34 )
    {
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 48LL))(*((_QWORD *)this + 10)) )
        goto LABEL_98;
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
      {
        v36 = L"Migration::SysVolMigration::DeleteRoMember";
        v37 = 4509;
        v38 = 2;
        v39 = L"SYSM";
        dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,enum Migration::RoMemberType>(
          &v36,
          v24,
          a2,
          &v46);
      }
      v33 = GetCurrentThreadId();
      v22 = (FrsStatus *)FrsStatusList::PushNewError(
                           v25,
                           9503,
                           0,
                           3,
                           "base\\fs\\remotefs\\frs\\src\\ad\\migration.cpp",
                           "Migration::SysVolMigration::DeleteRoMember",
                           4510,
                           v33,
                           0);
      goto LABEL_96;
    }
    v34 = 10;
    GlobalState = (struct FrsStatus *)Migration::SysVolMigration::GetLocalState(this, a2, &v34);
    if ( GlobalState
      && !(*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 48LL))(*((_QWORD *)this + 10)) )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
      {
        v36 = L"Migration::SysVolMigration::DeleteRoMember";
        v37 = 4482;
        v38 = 3;
        v39 = L"SYSM";
        dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,FrsStatus>(
          &v36,
          L"[MIG] (Ignored) Failed to get local state of %?. Error:%?",
          a2,
          GlobalState);
      }
      goto LABEL_98;
    }
    v18 = v46;
    if ( v46 == 2 )
    {
      if ( v34 != 9 )
        goto LABEL_80;
      if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 48LL))(*((_QWORD *)this + 10)) )
      {
        v19 = Migration::SysVolMigration::DeleteDfsrMemberObject(this, this, a2);
        goto LABEL_79;
      }
      v18 = v46;
    }
    if ( v18 != 1
      || v34 != 7
      || (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 48LL))(*((_QWORD *)this + 10)) )
    {
LABEL_80:
      if ( !GlobalState )
        return v5;
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 48LL))(*((_QWORD *)this + 10)) )
        goto LABEL_98;
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
      {
        v36 = L"Migration::SysVolMigration::DeleteRoMember";
        v37 = 4494;
        v38 = 2;
        v39 = L"SYSM";
        dbgobj::DbgPrint<unsigned short,enum Migration::RoMemberType,FrsStringImpl<unsigned short,char>>(
          &v36,
          v20,
          &v46,
          a2);
      }
      if ( v46 == 2 )
      {
        v31 = GetCurrentThreadId();
        v22 = (FrsStatus *)FrsStatusList::PushNewError(
                             v21,
                             9507,
                             0,
                             3,
                             "base\\fs\\remotefs\\frs\\src\\ad\\migration.cpp",
                             "Migration::SysVolMigration::DeleteRoMember",
                             4498,
                             v31,
                             0);
      }
      else
      {
        if ( v46 != 1 )
          goto LABEL_98;
        v32 = GetCurrentThreadId();
        v22 = (FrsStatus *)FrsStatusList::PushNewError(
                             v23,
                             9505,
                             0,
                             3,
                             "base\\fs\\remotefs\\frs\\src\\ad\\migration.cpp",
                             "Migration::SysVolMigration::DeleteRoMember",
                             4502,
                             v32,
                             0);
      }
LABEL_96:
      if ( v22 )
        GlobalState = FrsStatus::AppendError(v22, GlobalState);
      goto LABEL_98;
    }
    v19 = Migration::SysVolMigration::DeleteNtFrsSettings(this, this, a2, 1);
LABEL_79:
    GlobalState = (struct FrsStatus *)v19;
    goto LABEL_80;
  }
  v44 = &FrsStringImpl<unsigned short,char>::s_Empty;
  if ( !byte_140315A80 )
    _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
  GlobalState = (struct FrsStatus *)Migration::SysVolUtil::GetLsaDomainName(&v44);
  v41 = 0;
  v42 = 0;
  v43 = 3;
  if ( !GlobalState
    && ((*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 48LL))(*((_QWORD *)this + 10))
     || (GlobalState = (struct FrsStatus *)Config::DsDcIter::Initialize(&v41, *((_QWORD *)this + 1), &v44, 1)) == 0)
    && !(*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 48LL))(*((_QWORD *)this + 10)) )
  {
    for ( i = Config::DsDcIter::Begin((Config::DsDcIter *)&v41); ; i = Config::DsDcIter::NextDc((Config::DsDcIter *)&v41) )
    {
      v13 = i;
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 48LL))(*((_QWORD *)this + 10)) || !v13 )
        goto LABEL_60;
      Dc = Config::DsDcIter::GetDc((Config::DsDcIter *)&v41);
      FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(v45, Dc->DnsHostName);
      Migration::GetComputerNameFromHostName(v40, v45);
      v34 = 10;
      GlobalState = (struct FrsStatus *)Migration::SysVolMigration::GetLocalState(this, v40, &v34);
      v35 = GlobalState;
      if ( !GlobalState
        || (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 48LL))(*((_QWORD *)this + 10)) )
      {
        break;
      }
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
      {
        v36 = L"Migration::SysVolMigration::DeleteRoMember";
        v37 = 4443;
        v38 = 3;
        v39 = L"SYSM";
        dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,FrsStatus>(
          &v36,
          L"[MIG] (Ignored) Failed to get local state of %?. Error:%?",
          v40,
          GlobalState);
      }
      CLEAR_ERROR(&v35);
      FrsStringImpl<char,unsigned short>::ReleaseBody(v40);
      GlobalState = v35;
LABEL_59:
      FrsStringImpl<char,unsigned short>::ReleaseBody(v45);
    }
    v15 = v46;
    if ( v46 == 2 )
    {
      if ( v34 != 9 )
        goto LABEL_58;
      if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 48LL))(*((_QWORD *)this + 10)) )
      {
        v16 = (struct FrsStatus *)Migration::SysVolMigration::DeleteDfsrMemberObject(this, this, v40);
LABEL_51:
        GlobalState = v16;
        v35 = v16;
        if ( v16
          && !(*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 48LL))(*((_QWORD *)this + 10)) )
        {
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
          {
            v36 = L"Migration::SysVolMigration::DeleteRoMember";
            v37 = 4460;
            v38 = 3;
            v39 = L"SYSM";
            dbgobj::DbgPrint<unsigned short,enum Migration::RoMemberType,FrsStringImpl<unsigned short,char>,FrsStatus>(
              (unsigned int)&v36,
              v17,
              (unsigned int)&v46,
              (unsigned int)v40,
              (__int64)GlobalState);
          }
          CLEAR_ERROR(&v35);
          GlobalState = v35;
        }
        goto LABEL_58;
      }
      v15 = v46;
    }
    if ( v15 == 1
      && v34 == 7
      && !(*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 48LL))(*((_QWORD *)this + 10)) )
    {
      v16 = (struct FrsStatus *)Migration::SysVolMigration::DeleteNtFrsSettings(this, this, v40, 1);
      goto LABEL_51;
    }
LABEL_58:
    FrsStringImpl<char,unsigned short>::ReleaseBody(v40);
    goto LABEL_59;
  }
LABEL_60:
  Config::DsDcIter::Release((Config::DsDcIter *)&v41);
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v44);
LABEL_98:
  if ( GlobalState )
    goto LABEL_99;
  return v5;
}

```

## disassembly

```asm
0x1401f9674  mov     rax, rsp
0x1401f9677  mov     [rax+8], rbx
0x1401f967b  mov     [rax+10h], rsi
0x1401f967f  mov     [rax+18h], r8d
0x1401f9683  push    rbp
0x1401f9684  push    rdi
0x1401f9685  push    r12
0x1401f9687  push    r14
0x1401f9689  push    r15
0x1401f968b  lea     rbp, [rax-5Fh]
0x1401f968f  sub     rsp, 0B0h
0x1401f9696  mov     r14, rdx
0x1401f9699  mov     rsi, rcx
0x1401f969c  xor     ebx, ebx
0x1401f969e  mov     edi, ebx
0x1401f96a0  mov     [rbp+57h+var_78], rbx
0x1401f96a4  lea     r15d, [rbx+4]
0x1401f96a8  lea     rcx, aMigrationSysvo_99; "Migration::SysVolMigration::DeleteRoMem"...
0x1401f96af  lea     rdx, aSysm; "SYSM"
0x1401f96b6  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401f96bd  test    rax, rax
0x1401f96c0  jz      short loc_1401F96ED
0x1401f96c2  cmp     [rax+40h], ebx
0x1401f96c5  jz      short loc_1401F96ED
0x1401f96c7  cmp     [rax+38h], r15d
0x1401f96cb  jl      short loc_1401F96ED
0x1401f96cd  mov     [rbp+57h+var_50], rcx
0x1401f96d1  mov     dword ptr [rbp+57h+var_48], 111Dh
0x1401f96d8  mov     dword ptr [rbp+57h+var_48+4], r15d
0x1401f96dc  mov     [rbp+57h+var_40], rdx
0x1401f96e0  lea     r8, [rbp+57h+arg_10]
0x1401f96e4  lea     rcx, [rbp+57h+var_50]
0x1401f96e8  call    ??$DbgPrint@GW4RoMemberType@Migration@@@dbgobj@@QEAA_KPEBGAEBW4RoMemberType@Migration@@@Z; dbgobj::DbgPrint<ushort,Migration::RoMemberType>(ushort const *,Migration::RoMemberType const &)
0x1401f96ed  mov     rcx, [rsi+50h]
0x1401f96f1  mov     rax, [rcx]
0x1401f96f4  mov     rax, [rax+30h]
0x1401f96f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401f96fd  test    al, al
0x1401f96ff  jnz     short loc_1401F9715
0x1401f9701  mov     rcx, rsi; this
0x1401f9704  call    ?IsLocalComputerLongHornLevelReplicaDc@SysVolMigration@Migration@@QEAAPEAVFrsStatus@@XZ; Migration::SysVolMigration::IsLocalComputerLongHornLevelReplicaDc(void)
0x1401f9709  mov     rdi, rax
0x1401f970c  mov     [rbp+57h+var_78], rax
0x1401f9710  test    rax, rax
0x1401f9713  jnz     short loc_1401F9738
0x1401f9715  mov     rcx, [rsi+50h]
0x1401f9719  mov     rax, [rcx]
0x1401f971c  mov     rax, [rax+30h]
0x1401f9720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401f9725  test    al, al
0x1401f9727  jnz     short loc_1401F9738
0x1401f9729  mov     rcx, rsi; this
0x1401f972c  call    ?Connect@SysVolMigration@Migration@@AEAAPEAVFrsStatus@@XZ; Migration::SysVolMigration::Connect(void)
0x1401f9731  mov     rdi, rax
0x1401f9734  mov     [rbp+57h+var_78], rax
0x1401f9738  mov     [rbp+57h+arg_18], ebx
0x1401f973b  test    rdi, rdi
0x1401f973e  jnz     loc_1401F9DF9
0x1401f9744  mov     rcx, [rsi+50h]
0x1401f9748  mov     rax, [rcx]
0x1401f974b  mov     rax, [rax+30h]
0x1401f974f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401f9754  test    al, al
0x1401f9756  jnz     short loc_1401F9774
0x1401f9758  lea     rdx, [rbp+57h+arg_18]; enum Migration::_MIGRATION_STATE *
0x1401f975c  mov     rcx, rsi; this
0x1401f975f  call    ?GetGlobalState@SysVolMigration@Migration@@QEAAPEAVFrsStatus@@AEAW4_MIGRATION_STATE@2@@Z; Migration::SysVolMigration::GetGlobalState(Migration::_MIGRATION_STATE &)
0x1401f9764  mov     rdi, rax
0x1401f9767  mov     [rbp+57h+var_78], rax
0x1401f976b  test    rax, rax
0x1401f976e  jnz     loc_1401F9DF9
0x1401f9774  mov     rcx, [rsi+50h]
0x1401f9778  mov     rax, [rcx]
0x1401f977b  mov     rax, [rax+30h]
0x1401f977f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401f9784  mov     r12d, 3
0x1401f978a  test    al, al
0x1401f978c  jnz     loc_1401F987D
0x1401f9792  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401f9799  test    rax, rax
0x1401f979c  jz      short loc_1401F97E0
0x1401f979e  cmp     [rax+40h], ebx
0x1401f97a1  jz      short loc_1401F97E0
0x1401f97a3  cmp     [rax+38h], r15d
0x1401f97a7  jl      short loc_1401F97E0
0x1401f97a9  lea     rax, aMigrationSysvo_99; "Migration::SysVolMigration::DeleteRoMem"...
0x1401f97b0  mov     [rbp+57h+var_70], rax
0x1401f97b4  mov     [rbp+57h+var_68], 1131h
0x1401f97bb  mov     [rbp+57h+var_64], r15d
0x1401f97bf  lea     r15, aSysm; "SYSM"
0x1401f97c6  mov     [rbp+57h+var_60], r15
0x1401f97ca  lea     r8, [rbp+57h+arg_18]
0x1401f97ce  lea     rdx, aMigCurrentGlob; "[MIG] Current global state is %?"
0x1401f97d5  lea     rcx, [rbp+57h+var_70]
0x1401f97d9  call    ??$DbgPrint@GW4_MIGRATION_STATE@Migration@@@dbgobj@@QEAA_KPEBGAEBW4_MIGRATION_STATE@Migration@@@Z; dbgobj::DbgPrint<ushort,Migration::_MIGRATION_STATE>(ushort const *,Migration::_MIGRATION_STATE const &)
0x1401f97de  jmp     short loc_1401F97E7
0x1401f97e0  lea     r15, aSysm; "SYSM"
0x1401f97e7  cmp     [rbp+57h+arg_10], 2
0x1401f97eb  jnz     short loc_1401F981A
0x1401f97ed  cmp     [rbp+57h+arg_18], ebx
0x1401f97f0  jz      loc_1401F9884
0x1401f97f6  call    cs:__imp_GetCurrentThreadId
0x1401f97fd  nop     dword ptr [rax+rax+00h]
0x1401f9802  mov     [rsp+0D0h+var_90], rbx
0x1401f9807  mov     dword ptr [rsp+0D0h+var_98], eax
0x1401f980b  mov     [rsp+0D0h+var_A0], 1135h
0x1401f9813  mov     edx, 2522h
0x1401f9818  jmp     short loc_1401F9848
0x1401f981a  cmp     [rbp+57h+arg_10], 1
0x1401f981e  jnz     short loc_1401F9884
0x1401f9820  cmp     [rbp+57h+arg_18], r12d
0x1401f9824  jz      short loc_1401F9884
0x1401f9826  call    cs:__imp_GetCurrentThreadId
0x1401f982d  nop     dword ptr [rax+rax+00h]
0x1401f9832  mov     [rsp+0D0h+var_90], rbx
0x1401f9837  mov     dword ptr [rsp+0D0h+var_98], eax
0x1401f983b  mov     [rsp+0D0h+var_A0], 113Ah
0x1401f9843  mov     edx, 2520h
0x1401f9848  lea     rax, aMigrationSysvo_102; "Migration::SysVolMigration::DeleteRoMem"...
0x1401f984f  mov     qword ptr [rsp+0D0h+var_A8], rax
0x1401f9854  lea     rax, aBaseFsRemotefs_99; "base\\fs\\remotefs\\frs\\src\\ad\\migra"...
0x1401f985b  mov     [rsp+0D0h+var_B0], rax
0x1401f9860  mov     r9d, r12d
0x1401f9863  xor     r8d, r8d
0x1401f9866  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401f986b  mov     rdi, rax
0x1401f986e  mov     [rbp+57h+var_78], rax
0x1401f9872  test    rax, rax
0x1401f9875  jnz     loc_1401F9DF9
0x1401f987b  jmp     short loc_1401F9884
0x1401f987d  lea     r15, aSysm; "SYSM"
0x1401f9884  mov     rcx, [rsi+50h]
0x1401f9888  mov     rax, [rcx]
0x1401f988b  mov     rax, [rax+30h]
0x1401f988f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401f9894  test    al, al
0x1401f9896  jnz     loc_1401F9E40
0x1401f989c  mov     rcx, [r14]
0x1401f989f  cmp     [rcx+8], rbx
0x1401f98a3  jnz     loc_1401F9B4A
0x1401f98a9  lea     rax, ?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1401f98b0  mov     [rbp+57h+var_38], rax
0x1401f98b4  cmp     cs:byte_140315A80, bl
0x1401f98ba  jnz     short loc_1401F98C3
0x1401f98bc  lock inc cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1401f98c3  lea     rcx, [rbp+57h+var_38]
0x1401f98c7  call    ?GetLsaDomainName@SysVolUtil@Migration@@SAPEAVFrsStatus@@AEAV?$FrsStringImpl@GD@@@Z; Migration::SysVolUtil::GetLsaDomainName(FrsStringImpl<ushort,char> &)
0x1401f98cc  mov     rdi, rax
0x1401f98cf  mov     [rbp+57h+var_50], rbx
0x1401f98d3  mov     [rbp+57h+var_48], rbx
0x1401f98d7  mov     [rbp+57h+var_40], 3
0x1401f98df  test    rax, rax
0x1401f98e2  jnz     loc_1401F9B32
0x1401f98e8  mov     rcx, [rsi+50h]
0x1401f98ec  mov     rax, [rcx]
0x1401f98ef  mov     rax, [rax+30h]
0x1401f98f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401f98f8  test    al, al
0x1401f98fa  jnz     short loc_1401F991D
0x1401f98fc  lea     r9d, [rdi+1]
0x1401f9900  lea     r8, [rbp+57h+var_38]
0x1401f9904  mov     rdx, [rsi+8]
0x1401f9908  lea     rcx, [rbp+57h+var_50]
0x1401f990c  call    ?Initialize@DsDcIter@Config@@QEAAPEAVFrsStatus@@PEAXAEBV?$FrsStringImpl@GD@@W4DCTYPE@12@@Z; Config::DsDcIter::Initialize(void *,FrsStringImpl<ushort,char> const &,Config::DsDcIter::DCTYPE)
0x1401f9911  mov     rdi, rax
0x1401f9914  test    rax, rax
0x1401f9917  jnz     loc_1401F9B32
0x1401f991d  mov     rcx, [rsi+50h]
0x1401f9921  mov     rax, [rcx]
0x1401f9924  mov     rax, [rax+30h]
0x1401f9928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401f992d  test    al, al
0x1401f992f  jnz     loc_1401F9B32
0x1401f9935  lea     rcx, [rbp+57h+var_50]; this
0x1401f9939  call    ?Begin@DsDcIter@Config@@QEAAHXZ; Config::DsDcIter::Begin(void)
0x1401f993e  mov     r14d, eax
0x1401f9941  mov     rcx, [rsi+50h]
0x1401f9945  mov     rdx, [rcx]
0x1401f9948  mov     rax, [rdx+30h]
0x1401f994c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401f9951  test    al, al
0x1401f9953  jnz     loc_1401F9B32
0x1401f9959  test    r14d, r14d
0x1401f995c  jz      loc_1401F9B32
0x1401f9962  lea     rcx, [rbp+57h+var_50]; this
0x1401f9966  call    ?GetDc@DsDcIter@Config@@QEBAPEAUDS_DOMAIN_CONTROLLER_INFO_3W@@XZ; Config::DsDcIter::GetDc(void)
0x1401f996b  mov     rdx, [rax+8]
0x1401f996f  lea     rcx, [rbp+57h+var_30]
0x1401f9973  call    ??0?$FrsStringImpl@GD@@QEAA@PEBG@Z; FrsStringImpl<ushort,char>::FrsStringImpl<ushort,char>(ushort const *)
0x1401f9978  nop
0x1401f9979  lea     rdx, [rbp+57h+var_30]
0x1401f997d  lea     rcx, [rbp+57h+var_58]
0x1401f9981  call    ?GetComputerNameFromHostName@Migration@@YA?AV?$FrsStringImpl@GD@@AEBV2@@Z; Migration::GetComputerNameFromHostName(FrsStringImpl<ushort,char> const &)
0x1401f9986  nop
0x1401f9987  mov     [rbp+57h+var_80], 0Ah
0x1401f998e  lea     r8, [rbp+57h+var_80]
0x1401f9992  lea     rdx, [rbp+57h+var_58]
0x1401f9996  mov     rcx, rsi
0x1401f9999  call    ?GetLocalState@SysVolMigration@Migration@@QEAAPEAVFrsStatus@@AEAV?$FrsStringImpl@GD@@AEAW4_MIGRATION_STATE@2@@Z; Migration::SysVolMigration::GetLocalState(FrsStringImpl<ushort,char> &,Migration::_MIGRATION_STATE &)
0x1401f999e  mov     rdi, rax
0x1401f99a1  mov     [rbp+57h+var_78], rax
0x1401f99a5  test    rax, rax
0x1401f99a8  jz      short loc_1401F9A23
0x1401f99aa  mov     rcx, [rsi+50h]
0x1401f99ae  mov     rax, [rcx]
0x1401f99b1  mov     rax, [rax+30h]
0x1401f99b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401f99ba  test    al, al
0x1401f99bc  jnz     short loc_1401F9A23
0x1401f99be  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401f99c5  test    rax, rax
0x1401f99c8  jz      short loc_1401F9A06
0x1401f99ca  cmp     [rax+40h], ebx
0x1401f99cd  jz      short loc_1401F9A06
0x1401f99cf  cmp     [rax+38h], r12d
0x1401f99d3  jl      short loc_1401F9A06
0x1401f99d5  lea     rax, aMigrationSysvo_99; "Migration::SysVolMigration::DeleteRoMem"...
0x1401f99dc  mov     [rbp+57h+var_70], rax
0x1401f99e0  mov     [rbp+57h+var_68], 115Bh
0x1401f99e7  mov     [rbp+57h+var_64], r12d
0x1401f99eb  mov     [rbp+57h+var_60], r15
0x1401f99ef  mov     r9, rdi
0x1401f99f2  lea     r8, [rbp+57h+var_58]
0x1401f99f6  lea     rdx, aMigIgnoredFail_2; "[MIG] (Ignored) Failed to get local sta"...
0x1401f99fd  lea     rcx, [rbp+57h+var_70]
0x1401f9a01  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@VFrsStatus@@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@AEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>,FrsStatus>(ushort const *,FrsStringImpl<ushort,char> const &,FrsStatus const &)
0x1401f9a06  lea     rcx, [rbp+57h+var_78]; struct FrsStatus **
0x1401f9a0a  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x1401f9a0f  nop
0x1401f9a10  lea     rcx, [rbp+57h+var_58]
0x1401f9a14  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1401f9a19  nop
0x1401f9a1a  mov     rdi, [rbp+57h+var_78]
0x1401f9a1e  jmp     loc_1401F9B1B
0x1401f9a23  mov     eax, [rbp+57h+arg_10]
0x1401f9a26  cmp     eax, 2
0x1401f9a29  jnz     short loc_1401F9A5D
0x1401f9a2b  cmp     [rbp+57h+var_80], 9
0x1401f9a2f  jnz     loc_1401F9B11
0x1401f9a35  mov     rcx, [rsi+50h]
0x1401f9a39  mov     rax, [rcx]
0x1401f9a3c  mov     rax, [rax+30h]
0x1401f9a40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401f9a45  test    al, al
0x1401f9a47  jnz     short loc_1401F9A5A
0x1401f9a49  lea     r8, [rbp+57h+var_58]
0x1401f9a4d  mov     rdx, rsi
0x1401f9a50  mov     rcx, rsi
0x1401f9a53  call    ?DeleteDfsrMemberObject@SysVolMigration@Migration@@QEAAPEAVFrsStatus@@PEAVAdSession@Config@@AEBV?$FrsStringImpl@GD@@@Z; Migration::SysVolMigration::DeleteDfsrMemberObject(Config::AdSession *,FrsStringImpl<ushort,char> const &)
0x1401f9a58  jmp     short loc_1401F9A9D
0x1401f9a5a  mov     eax, [rbp+57h+arg_10]
0x1401f9a5d  cmp     eax, 1
0x1401f9a60  jnz     loc_1401F9B11
0x1401f9a66  cmp     [rbp+57h+var_80], 7
0x1401f9a6a  jnz     loc_1401F9B11
0x1401f9a70  mov     rcx, [rsi+50h]
0x1401f9a74  mov     rax, [rcx]
0x1401f9a77  mov     rax, [rax+30h]
0x1401f9a7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401f9a80  test    al, al
0x1401f9a82  jnz     loc_1401F9B11
0x1401f9a88  mov     r9d, 1
0x1401f9a8e  lea     r8, [rbp+57h+var_58]
0x1401f9a92  mov     rdx, rsi
0x1401f9a95  mov     rcx, rsi
0x1401f9a98  call    ?DeleteNtFrsSettings@SysVolMigration@Migration@@AEAAPEAVFrsStatus@@PEAVAdSession@Config@@AEBV?$FrsStringImpl@GD@@H@Z; Migration::SysVolMigration::DeleteNtFrsSettings(Config::AdSession *,FrsStringImpl<ushort,char> const &,int)
0x1401f9a9d  mov     rdi, rax
0x1401f9aa0  mov     [rbp+57h+var_78], rax
0x1401f9aa4  test    rax, rax
0x1401f9aa7  jz      short loc_1401F9B11
0x1401f9aa9  mov     rcx, [rsi+50h]
0x1401f9aad  mov     rax, [rcx]
0x1401f9ab0  mov     rax, [rax+30h]
0x1401f9ab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401f9ab9  test    al, al
0x1401f9abb  jnz     short loc_1401F9B11
0x1401f9abd  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401f9ac4  test    rax, rax
0x1401f9ac7  jz      short loc_1401F9B04
0x1401f9ac9  cmp     [rax+40h], ebx
0x1401f9acc  jz      short loc_1401F9B04
0x1401f9ace  cmp     [rax+38h], r12d
0x1401f9ad2  jl      short loc_1401F9B04
0x1401f9ad4  lea     rax, aMigrationSysvo_99; "Migration::SysVolMigration::DeleteRoMem"...
0x1401f9adb  mov     [rbp+57h+var_70], rax
0x1401f9adf  mov     [rbp+57h+var_68], 116Ch
0x1401f9ae6  mov     [rbp+57h+var_64], r12d
0x1401f9aea  mov     [rbp+57h+var_60], r15
0x1401f9aee  mov     [rsp+0D0h+var_B0], rdi
0x1401f9af3  lea     r9, [rbp+57h+var_58]
0x1401f9af7  lea     r8, [rbp+57h+arg_10]
0x1401f9afb  lea     rcx, [rbp+57h+var_70]
0x1401f9aff  call    ??$DbgPrint@GW4RoMemberType@Migration@@V?$FrsStringImpl@GD@@VFrsStatus@@@dbgobj@@QEAA_KPEBGAEBW4RoMemberType@Migration@@AEBV?$FrsStringImpl@GD@@AEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,Migration::RoMemberType,FrsStringImpl<ushort,char>,FrsStatus>(ushort const *,Migration::RoMemberType const &,FrsStringImpl<ushort,char> const &,FrsStatus const &)
0x1401f9b04  lea     rcx, [rbp+57h+var_78]; struct FrsStatus **
0x1401f9b08  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x1401f9b0d  mov     rdi, [rbp+57h+var_78]
0x1401f9b11  lea     rcx, [rbp+57h+var_58]
0x1401f9b15  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1401f9b1a  nop
0x1401f9b1b  lea     rcx, [rbp+57h+var_30]
  ... truncated ...
```
