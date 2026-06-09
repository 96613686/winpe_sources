# Meet::InstallTombstone(Db *,Meet::RelatedToUpdate &)

- ea: `0x140185d8c`
- end: `0x140186a3b`
- name: `?InstallTombstone@Meet@@AEAAPEAVFrsStatus@@PEAVDb@@AEAVRelatedToUpdate@1@@Z`
- size: `3247`
- prototype: `struct FrsStatus *__fastcall(Meet *__hidden this, struct Db *, struct Meet::RelatedToUpdate *)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140188650`

## callees

- `0x1400036a0`
- `0x14000c910`
- `0x14000dd10`
- `0x1400249a4`
- `0x14002a15c`
- `0x14002a6d0`
- `0x14006a550`
- `0x14006f224`
- `0x1400923f8`
- `0x140115e28`
- `0x14011efbc`
- `0x14017af28`
- `0x14017b008`
- `0x14017c55c`
- `0x14017df64`
- `0x140182c88`
- `0x140185d8c`
- `0x1401877d0`
- `0x14018842c`
- `0x140188f68`
- `0x14018aa10`
- `0x14018bdfc`
- `0x14018bf00`
- `0x1401b9494`
- `0x1401bda10`
- `0x140223010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1401868fd`
- `KERNEL32!LeaveCriticalSection` at `0x1401868fd`
- `KERNEL32!EnterCriticalSection` at `0x140186862`
- `KERNEL32!EnterCriticalSection` at `0x140186862`
- `KERNEL32!GetCurrentThreadId` at `0x140185de5`
- `KERNEL32!GetCurrentThreadId` at `0x1401869bd`
- `KERNEL32!GetCurrentThreadId` at `0x140185de5`
- `KERNEL32!GetCurrentThreadId` at `0x1401869bd`

## string_xrefs

- `0x1401868a9`: `Update syncInfoHistory`
- `0x1401864e5`: `Updating database. updateName:%ws uid:%? gvsn:%? connId:%? csName:%?`
- `0x1401866e7`: `Updating database. updateName:%ws uid:%? gvsn:%? connId:%? csName:%?`
- `0x14018681d`: `Updating database. updateName:%ws uid:%? gvsn:%? connId:%? csName:%?`
- `0x140185e12`: `Meet::InstallTombstone`
- `0x140185f3f`: `Meet::InstallTombstone`
- `0x140185ff9`: `Meet::InstallTombstone`
- `0x1401860eb`: `Meet::InstallTombstone`
- `0x1401861c0`: `Meet::InstallTombstone`
- `0x1401862b9`: `Meet::InstallTombstone`
- `0x140186339`: `Meet::InstallTombstone`
- `0x14018647d`: `Meet::InstallTombstone`
- `0x14018653d`: `Meet::InstallTombstone`
- `0x140186677`: `Meet::InstallTombstone`
- `0x1401867af`: `Meet::InstallTombstone`
- `0x140186846`: `Meet::InstallTombstone`
- `0x140185e9f`: `Checking whether deleted resource should be re-animated updateName:%ws uid:%? gvsn:%? connId:%? csName:%?`
- `0x140186156`: `Tombstoning children if the update forces it updateName:%ws uid:%? gvsn:%? connId:%? csName:%?`
- `0x14018622b`: `Inserting the update into the database updateName:%ws uid:%? gvsn:%? connId:%? csName:%?`
- `0x140185faf`: `Update GVSN already known updateName:%ws uid:%? gvsn:%? connId:%? csName:%?`
- `0x140186064`: `Moving out existing content updateName:%ws uid:%? gvsn:%? connId:%? csName:%?`
- `0x14018699d`: `-> DONE Install Tombstone complete updateName:%ws uid:%? gvsn:%? connId:%? csName:%? csId:%?`
- `0x1401869da`: `Meet::InstallTombstone`
- `0x140186300`: `Skipping update of name conflicting tombstone %?`
- `0x1401865b5`: `Record has never replicated out; assigning it a new version recordUid:%? updateName:%ws uid:%? gvsn:%? connId:%? csName:%?`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct FrsStatus *__fastcall Meet::InstallTombstone(Meet *this, struct Db *a2, struct Meet::RelatedToUpdate *a3)
{
  __int64 v6; // r14
  int v7; // r13d
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int128 *, _QWORD); // rbx
  DWORD CurrentThreadId; // eax
  struct FrsStatus *v11; // rdi
  LPCRITICAL_SECTION v12; // rdx
  LPCRITICAL_SECTION v13; // rdx
  Meet *v14; // rcx
  int v15; // ecx
  int v16; // eax
  struct FrsStatus *inserted; // rax
  unsigned int v18; // eax
  Meet *v19; // rcx
  __int64 v20; // rax
  const struct UID *v21; // r8
  struct ID_RECORD *v22; // r9
  unsigned int v23; // eax
  __int64 v24; // rax
  struct MonitorContext *v25; // rbx
  struct _RTL_CRITICAL_SECTION *v26; // rcx
  __int64 v27; // rax
  DWORD v28; // eax
  __int64 v29; // rcx
  int v31; // [rsp+20h] [rbp-E0h]
  __int64 v32; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v33; // [rsp+58h] [rbp-A8h] BYREF
  int v34; // [rsp+60h] [rbp-A0h]
  int v35; // [rsp+64h] [rbp-9Ch]
  const wchar_t *v36; // [rsp+68h] [rbp-98h]
  const wchar_t *v37; // [rsp+70h] [rbp-90h] BYREF
  int v38; // [rsp+78h] [rbp-88h]
  int v39; // [rsp+7Ch] [rbp-84h]
  const wchar_t *v40; // [rsp+80h] [rbp-80h]
  int v41; // [rsp+88h] [rbp-78h] BYREF
  __int64 v42; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v43[8]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v44; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v45[56]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v46[24]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v47[108]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v48; // [rsp+174h] [rbp+74h]
  __int64 v49; // [rsp+3A0h] [rbp+2A0h]

  v6 = 0;
  v42 = 0;
  v7 = 0;
  v44 = 0;
  v8 = *((_QWORD *)this + 100);
  v9 = *(__int64 (__fastcall **)(__int64, __int128 *, _QWORD))(*(_QWORD *)v8 + 32LL);
  CurrentThreadId = GetCurrentThreadId();
  v11 = (struct FrsStatus *)v9(v8, &v44, CurrentThreadId);
  if ( v11 )
    goto LABEL_115;
  if ( *((_DWORD *)this + 8) != 1 )
    goto LABEL_18;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
  {
    v33 = L"Meet::InstallTombstone";
    v34 = 5240;
    v35 = 5;
    v36 = L"MEET";
    v32 = *(_QWORD *)(*((_QWORD *)this + 99) + 200LL) + 18LL;
    dbgobj::DbgPrint<unsigned short,unsigned short [261],UID,GVSN,_GUID,unsigned short const *>(
      (unsigned int)&v33,
      (unsigned int)L"Checking whether deleted resource should be re-animated updateName:%ws uid:%? gvsn:%? connId:%? csName:%?",
      (_DWORD)this + 196,
      (_DWORD)this + 40,
      (__int64)this + 64,
      *((_QWORD *)this + 98) + 168LL,
      (__int64)&v32);
  }
  v11 = Meet::ReAnimate(this, (struct DbManagerInstance *)&v44, a2, a3);
  if ( v11 )
    goto LABEL_115;
  if ( *((_DWORD *)this + 8) != 1 || *((_DWORD *)a3 + 182) || *((_DWORD *)this + 194) != 2 )
    goto LABEL_18;
  v41 = 0;
  v11 = Meet::VersionIsKnown(this, a2, &v41);
  if ( v11 )
  {
LABEL_115:
    v28 = GetCurrentThreadId();
    v6 = FrsStatusList::PushNewError(
           v29,
           *((unsigned int *)v11 + 1),
           *((unsigned int *)v11 + 2),
           *(unsigned int *)v11,
           "base\\fs\\remotefs\\frs\\src\\sync\\meet.cpp",
           "Meet::InstallTombstone",
           5422,
           v28,
           v11);
    goto LABEL_116;
  }
  if ( v41 )
  {
    v12 = g_DebugLog;
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      v33 = L"Meet::InstallTombstone";
      v34 = 5257;
      v35 = 3;
      v36 = L"MEET";
      v32 = *(_QWORD *)(*((_QWORD *)this + 99) + 200LL) + 18LL;
      dbgobj::DbgPrint<unsigned short,unsigned short [261],UID,GVSN,_GUID,unsigned short const *>(
        (unsigned int)&v33,
        (unsigned int)L"Update GVSN already known updateName:%ws uid:%? gvsn:%? connId:%? csName:%?",
        (_DWORD)this + 196,
        (_DWORD)this + 40,
        (__int64)this + 64,
        *((_QWORD *)this + 98) + 168LL,
        (__int64)&v32);
      v12 = g_DebugLog;
    }
    *((_DWORD *)this + 8) = 3;
  }
  else
  {
LABEL_18:
    v12 = g_DebugLog;
  }
  if ( *((_DWORD *)this + 8) == 1 )
  {
    if ( v12 && LODWORD(v12[1].LockSemaphore) && SLODWORD(v12[1].OwningThread) >= 5 )
    {
      v37 = L"Meet::InstallTombstone";
      v38 = 5264;
      v39 = 5;
      v40 = L"MEET";
      v32 = *(_QWORD *)(*((_QWORD *)this + 99) + 200LL) + 18LL;
      dbgobj::DbgPrint<unsigned short,unsigned short [261],UID,GVSN,_GUID,unsigned short const *>(
        (unsigned int)&v37,
        (unsigned int)L"Moving out existing content updateName:%ws uid:%? gvsn:%? connId:%? csName:%?",
        (_DWORD)this + 196,
        (_DWORD)this + 40,
        (__int64)this + 64,
        *((_QWORD *)this + 98) + 168LL,
        (__int64)&v32);
    }
    v11 = Meet::MoveOut(this, a2, a3, (struct Usn *)&v42, 0);
    if ( v11 )
      goto LABEL_115;
    v13 = g_DebugLog;
    if ( *((_DWORD *)this + 8) == 1 )
    {
      if ( (*((_BYTE *)this + 192) & 2) != 0 && *((_DWORD *)a3 + 182) && (unsigned int)ID_RECORD::Alive(a3) )
      {
        if ( v13 && LODWORD(v13[1].LockSemaphore) && SLODWORD(v13[1].OwningThread) >= 5 )
        {
          v37 = L"Meet::InstallTombstone";
          v38 = 5273;
          v39 = 5;
          v40 = L"MEET";
          v32 = *(_QWORD *)(*((_QWORD *)this + 99) + 200LL) + 18LL;
          dbgobj::DbgPrint<unsigned short,unsigned short [261],UID,GVSN,_GUID,unsigned short const *>(
            (unsigned int)&v37,
            (unsigned int)L"Tombstoning children if the update forces it updateName:%ws uid:%? gvsn:%? connId:%? csName:%?",
            (_DWORD)this + 196,
            (_DWORD)this + 40,
            (__int64)this + 64,
            *((_QWORD *)this + 98) + 168LL,
            (__int64)&v32);
        }
        *((_QWORD *)a3 + 85) = v42;
        v11 = Meet::DeleteChildren(this, a2, a3, *((_DWORD *)this + 47) & 0x10);
        if ( v11 )
          goto LABEL_115;
        v13 = g_DebugLog;
      }
      if ( *((_DWORD *)this + 8) == 1 )
      {
        if ( v13 && LODWORD(v13[1].LockSemaphore) && SLODWORD(v13[1].OwningThread) >= 5 )
        {
          v37 = L"Meet::InstallTombstone";
          v38 = 5283;
          v39 = 5;
          v40 = L"MEET";
          v32 = *(_QWORD *)(*((_QWORD *)this + 99) + 200LL) + 18LL;
          dbgobj::DbgPrint<unsigned short,unsigned short [261],UID,GVSN,_GUID,unsigned short const *>(
            (unsigned int)&v37,
            (unsigned int)L"Inserting the update into the database updateName:%ws uid:%? gvsn:%? connId:%? csName:%?",
            (_DWORD)this + 196,
            (_DWORD)this + 40,
            (__int64)this + 64,
            *((_QWORD *)this + 98) + 168LL,
            (__int64)&v32);
        }
        VolumeId::VolumeId((VolumeId *)v45, (const struct VolumeId *)(*((_QWORD *)this + 99) + 208LL));
        TombstoneFid(v43, (char *)this + 40);
        ID_RECORD::ID_RECORD((ID_RECORD *)v46, (Meet *)((char *)this + 40), (const struct FileId *)v43, &v42);
        if ( !*((_DWORD *)a3 + 182) )
        {
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
          {
            v37 = L"Meet::InstallTombstone";
            v38 = 5407;
            v39 = 4;
            v40 = L"MEET";
            v32 = *(_QWORD *)(*((_QWORD *)this + 99) + 200LL) + 18LL;
            dbgobj::DbgPrint<unsigned short,unsigned short [261],UID,GVSN,_GUID,unsigned short const *>(
              (unsigned int)&v37,
              (unsigned int)L"Updating database. updateName:%ws uid:%? gvsn:%? connId:%? csName:%?",
              (_DWORD)this + 196,
              (_DWORD)this + 40,
              (__int64)this + 64,
              *((_QWORD *)this + 98) + 168LL,
              (__int64)&v32);
          }
          inserted = Meet::InsertIdRecord(v14, a2, (struct ID_RECORD *)v46);
LABEL_105:
          v11 = inserted;
          if ( inserted )
            goto LABEL_114;
          goto LABEL_106;
        }
        Settings::GenericDwordSetting::operator()(&Settings::DirtyShutdownClockValue);
        v15 = *((_DWORD *)this + 48);
        if ( (v15 & 2) != 0 && (*((_BYTE *)this + 188) & 0x10) != 0 && (*((_BYTE *)a3 + 152) & 1) != 0 )
        {
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
          {
            v37 = L"Meet::InstallTombstone";
            v38 = 5299;
            v39 = 4;
            v40 = L"MEET";
            dbgobj::DbgPrint<unsigned short,ID_RECORD>(&v37, L"Skipping update of name conflicting tombstone %?", a3);
          }
LABEL_106:
          v25 = g_MonitorContext;
          EnterCriticalSection((LPCRITICAL_SECTION)g_MonitorContext + 15);
          *((_DWORD *)v25 + 148) = 1;
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
          {
            v37 = L"Meet::InstallTombstone";
            v38 = 5412;
            v39 = 5;
            v40 = L"MEET";
            dbgobj::DbgPrint<unsigned short>(&v37, L"Update syncInfoHistory");
          }
          ++*(_DWORD *)(*((_QWORD *)this + 98) + 732LL);
          StateHistory::Update(
            (struct MonitorContext *)((char *)g_MonitorContext + 536),
            (struct HistoryRecord *)(*((_QWORD *)this + 98) + 536LL));
          v26 = (struct _RTL_CRITICAL_SECTION *)g_MonitorContext;
          *((_DWORD *)g_MonitorContext + 148) = 0;
          LeaveCriticalSection(v26 + 15);
          *((_DWORD *)this + 8) = 3;
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
          {
            v37 = L"Meet::InstallTombstone";
            v38 = 5418;
            v39 = 4;
            v40 = L"MEET";
            v27 = *((_QWORD *)this + 99);
            v32 = *(_QWORD *)(v27 + 200) + 18LL;
            dbgobj::DbgPrint<unsigned short,unsigned short [261],UID,GVSN,_GUID,unsigned short const *,_GUID>(
              (unsigned int)&v37,
              (unsigned int)L"-> DONE Install Tombstone complete updateName:%ws uid:%? gvsn:%? connId:%? csName:%? csId:%?",
              (_DWORD)this + 196,
              (_DWORD)this + 40,
              (__int64)this + 64,
              *((_QWORD *)this + 98) + 168LL,
              (__int64)&v32,
              v27 + 168);
          }
LABEL_114:
          VolumeId::~VolumeId((VolumeId *)v45);
          if ( v11 )
            goto LABEL_115;
          goto LABEL_116;
        }
        v16 = *((_DWORD *)this + 194);
        if ( v16 == 2 )
        {
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
          {
            v33 = L"Meet::InstallTombstone";
            v34 = 5302;
            v35 = 4;
            v36 = L"MEET";
            dbgobj::DbgPrint<unsigned short,GVSN>(&v33, L"LDB Deleting ID Record. uid:%?", (char *)this + 40);
          }
          inserted = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, char *, _QWORD))(*(_QWORD *)a2 + 176LL))(
                                           a2,
                                           (char *)this + 40,
                                           0);
          goto LABEL_105;
        }
        if ( v16 == 1 )
        {
          if ( (*((_BYTE *)a3 + 704) & 1) == 0 )
          {
            if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
            {
              v33 = L"Meet::InstallTombstone";
              v34 = 5344;
              v35 = 3;
              v36 = L"MEET";
              v32 = *(_QWORD *)(*((_QWORD *)this + 99) + 200LL) + 18LL;
              dbgobj::DbgPrint<unsigned short,UID,unsigned short [261],UID,GVSN,_GUID,unsigned short const *>(
                (unsigned int)&v33,
                (unsigned int)L"Record has never replicated out; assigning it a new version recordUid:%? updateName:%ws ui"
                               "d:%? gvsn:%? connId:%? csName:%?",
                (_DWORD)a3,
                (_DWORD)this + 196,
                (__int64)this + 40,
                (__int64)this + 64,
                *((_QWORD *)this + 98) + 168LL,
                (__int64)&v32);
            }
            v7 = 1;
          }
          if ( (*((_BYTE *)this + 192) & 0x10) == 0
            || (unsigned int)ContentSetManager::IsSubordinate(*((ContentSetManager **)this + 99)) )
          {
            if ( !v7 )
            {
              if ( !(unsigned int)ContentSetManager::IsSubordinate(*((ContentSetManager **)this + 99))
                || *((_DWORD *)this + 9) == 5
                || !*((_DWORD *)a3 + 182) )
              {
                goto LABEL_96;
              }
              v19 = (Meet *)v44;
              v24 = *((_QWORD *)a3 + 3) - *(_QWORD *)(v44 + 312);
              if ( !v24 )
                v24 = *((_QWORD *)a3 + 4) - *(_QWORD *)(v44 + 320);
              if ( v24 )
              {
LABEL_96:
                v49 = *((_QWORD *)a3 + 86);
                if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 4 )
                  goto LABEL_70;
                v34 = 5381;
                goto LABEL_69;
              }
            }
          }
          else
          {
            v32 = v48;
            v23 = Settings::GenericDwordSetting::operator()(&Settings::DirtyShutdownClockValue);
            v32 += v23;
            v48 = v32;
          }
          v11 = Meet::NewGvsn(this, a2, (struct Meet::RelatedToUpdate *)((char *)a3 + 24));
          if ( v11 )
            goto LABEL_114;
          if ( !(unsigned int)ContentSetManager::IsSubordinate(*((ContentSetManager **)this + 99)) )
            *((_DWORD *)a3 + 176) |= 0x20u;
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
          {
            v33 = L"Meet::InstallTombstone";
            v34 = 5401;
            v35 = 4;
            v36 = L"MEET";
            v32 = *(_QWORD *)(*((_QWORD *)this + 99) + 200LL) + 18LL;
            dbgobj::DbgPrint<unsigned short,unsigned short [261],UID,GVSN,_GUID,unsigned short const *>(
              (unsigned int)&v33,
              (unsigned int)L"Updating database. updateName:%ws uid:%? gvsn:%? connId:%? csName:%?",
              (_DWORD)this + 196,
              (_DWORD)this + 40,
              (__int64)this + 64,
              *((_QWORD *)this + 98) + 168LL,
              (__int64)&v32);
          }
          v22 = a3;
          v21 = a3;
          goto LABEL_71;
        }
        if ( (v15 & 0x10) == 0 || (unsigned int)ContentSetManager::IsSubordinate(*((ContentSetManager **)this + 99)) )
        {
          if ( !(unsigned int)ContentSetManager::IsSubordinate(*((ContentSetManager **)this + 99))
            || *((_DWORD *)this + 9) == 5
            || !*((_DWORD *)a3 + 182) )
          {
            goto LABEL_65;
          }
          v19 = (Meet *)v44;
          v20 = *((_QWORD *)a3 + 3) - *(_QWORD *)(v44 + 312);
          if ( !v20 )
            v20 = *((_QWORD *)a3 + 4) - *(_QWORD *)(v44 + 320);
          if ( v20 )
          {
LABEL_65:
            v49 = *((_QWORD *)a3 + 86);
            if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 4 )
              goto LABEL_70;
            v34 = 5338;
LABEL_69:
            v33 = L"Meet::InstallTombstone";
            v35 = 4;
            v36 = L"MEET";
            v32 = *(_QWORD *)(*((_QWORD *)this + 99) + 200LL) + 18LL;
            dbgobj::DbgPrint<unsigned short,unsigned short [261],UID,GVSN,_GUID,unsigned short const *>(
              (unsigned int)&v33,
              (unsigned int)L"Updating database. updateName:%ws uid:%? gvsn:%? connId:%? csName:%?",
              (_DWORD)this + 196,
              (_DWORD)this + 40,
              (__int64)this + 64,
              *((_QWORD *)this + 98) + 168LL,
              (__int64)&v32);
LABEL_70:
            v21 = (Meet *)((char *)this + 40);
            v22 = (struct ID_RECORD *)v46;
LABEL_71:
            inserted = Meet::UpdateIdRecord(v19, a2, v21, v22, v31);
            goto LABEL_105;
          }
        }
        else
        {
          v32 = v48;
          v18 = Settings::GenericDwordSetting::operator()(&Settings::DirtyShutdownClockValue);
          v32 += v18;
          v48 = v32;
        }
        v11 = Meet::NewGvsn(this, a2, (struct GVSN *)v47);
        if ( v11 )
          goto LABEL_114;
        goto LABEL_65;
      }
    }
  }
LABEL_116:
  DbManagerInstance::FinalizeDbManagerInstance((DbManagerInstance *)&v44);
  return (struct FrsStatus *)v6;
}

```

## disassembly

```asm
0x140185d8c  mov     [rsp-8+arg_18], rbx
0x140185d91  push    rbp
0x140185d92  push    rsi
0x140185d93  push    rdi
0x140185d94  push    r12
0x140185d96  push    r13
0x140185d98  push    r14
0x140185d9a  push    r15
0x140185d9c  lea     rbp, [rsp-2D0h]
0x140185da4  sub     rsp, 3D0h
0x140185dab  mov     rax, cs:__security_cookie
0x140185db2  xor     rax, rsp
0x140185db5  mov     [rbp+300h+var_40], rax
0x140185dbc  mov     r15, r8
0x140185dbf  mov     r12, rdx
0x140185dc2  mov     rsi, rcx
0x140185dc5  xor     r14d, r14d
0x140185dc8  mov     [rbp+300h+var_370], r14
0x140185dcc  mov     r13d, r14d
0x140185dcf  xorps   xmm0, xmm0
0x140185dd2  movdqu  [rbp+300h+var_360], xmm0
0x140185dd7  mov     rdi, [rcx+320h]
0x140185dde  mov     rax, [rdi]
0x140185de1  mov     rbx, [rax+20h]
0x140185de5  call    cs:__imp_GetCurrentThreadId
0x140185dec  nop     dword ptr [rax+rax+00h]
0x140185df1  mov     r8d, eax
0x140185df4  lea     rdx, [rbp+300h+var_360]
0x140185df8  mov     rcx, rdi
0x140185dfb  mov     rax, rbx
0x140185dfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140185e03  mov     rdi, rax
0x140185e06  test    rax, rax
0x140185e09  jnz     loc_1401869BD
0x140185e0f  lea     ebx, [rax+5]
0x140185e12  lea     rcx, aMeetInstalltom; "Meet::InstallTombstone"
0x140185e19  lea     rdx, aMeet; "MEET"
0x140185e20  cmp     dword ptr [rsi+20h], 1
0x140185e24  jnz     loc_140185FD0
0x140185e2a  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140185e31  test    rax, rax
0x140185e34  jz      short loc_140185EB0
0x140185e36  cmp     [rax+40h], r14d
0x140185e3a  jz      short loc_140185EB0
0x140185e3c  cmp     [rax+38h], ebx
0x140185e3f  jl      short loc_140185EB0
0x140185e41  mov     [rsp+400h+var_3A8], rcx
0x140185e46  mov     [rsp+400h+var_3A0], 1478h
0x140185e4e  mov     [rsp+400h+var_39C], ebx
0x140185e52  mov     [rsp+400h+var_398], rdx
0x140185e57  mov     rax, [rsi+318h]
0x140185e5e  mov     rcx, [rax+0C8h]
0x140185e65  add     rcx, 12h
0x140185e69  mov     [rsp+400h+var_3B0], rcx
0x140185e6e  mov     rcx, [rsi+310h]
0x140185e75  add     rcx, 0A8h
0x140185e7c  lea     rax, [rsi+40h]
0x140185e80  lea     r9, [rsi+28h]
0x140185e84  lea     r8, [rsi+0C4h]
0x140185e8b  lea     rdx, [rsp+400h+var_3B0]
0x140185e90  mov     [rsp+400h+var_3D0], rdx
0x140185e95  mov     [rsp+400h+var_3D8], rcx
0x140185e9a  mov     [rsp+400h+var_3E0], rax
0x140185e9f  lea     rdx, aCheckingWhethe; "Checking whether deleted resource shoul"...
0x140185ea6  lea     rcx, [rsp+400h+var_3A8]
0x140185eab  call    ??$DbgPrint@G$$BY0BAF@GVUID@@VGVSN@@U_GUID@@PEBG@dbgobj@@QEAA_KPEBGAEAY0BAF@$$CBGAEBVUID@@AEBVGVSN@@AEBU_GUID@@AEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort [261],UID,GVSN,_GUID,ushort const *>(ushort const *,ushort const (&)[261],UID const &,GVSN const &,_GUID const &,ushort const * const &)
0x140185eb0  mov     r9, r15; struct Meet::RelatedToUpdate *
0x140185eb3  mov     r8, r12; struct Db *
0x140185eb6  lea     rdx, [rbp+300h+var_360]; struct DbManagerInstance *
0x140185eba  mov     rcx, rsi; this
0x140185ebd  call    ?ReAnimate@Meet@@AEAAPEAVFrsStatus@@AEAVDbManagerInstance@@PEAVDb@@AEAVRelatedToUpdate@1@@Z; Meet::ReAnimate(DbManagerInstance &,Db *,Meet::RelatedToUpdate &)
0x140185ec2  mov     rdi, rax
0x140185ec5  test    rax, rax
0x140185ec8  jnz     loc_1401869BD
0x140185ece  cmp     dword ptr [rsi+20h], 1
0x140185ed2  jnz     loc_140185FD0
0x140185ed8  cmp     [r15+2D8h], r14d
0x140185edf  jnz     loc_140185FD0
0x140185ee5  cmp     dword ptr [rsi+308h], 2
0x140185eec  jnz     loc_140185FD0
0x140185ef2  mov     [rbp+300h+var_378], r14d
0x140185ef6  lea     r8, [rbp+300h+var_378]; int *
0x140185efa  mov     rdx, r12; struct Db *
0x140185efd  mov     rcx, rsi; this
0x140185f00  call    ?VersionIsKnown@Meet@@AEAAPEAVFrsStatus@@PEAVDb@@AEAH@Z; Meet::VersionIsKnown(Db *,int &)
0x140185f05  mov     rdi, rax
0x140185f08  test    rax, rax
0x140185f0b  jnz     loc_1401869BD
0x140185f11  cmp     [rbp+300h+var_378], r14d
0x140185f15  jz      loc_140185FD0
0x140185f1b  mov     rdx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140185f22  test    rdx, rdx
0x140185f25  jz      loc_140185FC7
0x140185f2b  cmp     [rdx+40h], r14d
0x140185f2f  jz      loc_140185FC7
0x140185f35  cmp     dword ptr [rdx+38h], 3
0x140185f39  jl      loc_140185FC7
0x140185f3f  lea     rax, aMeetInstalltom; "Meet::InstallTombstone"
0x140185f46  mov     [rsp+400h+var_3A8], rax
0x140185f4b  mov     [rsp+400h+var_3A0], 1489h
0x140185f53  mov     [rsp+400h+var_39C], 3
0x140185f5b  lea     rax, aMeet; "MEET"
0x140185f62  mov     [rsp+400h+var_398], rax
0x140185f67  mov     rax, [rsi+318h]
0x140185f6e  mov     rcx, [rax+0C8h]
0x140185f75  add     rcx, 12h
0x140185f79  mov     [rsp+400h+var_3B0], rcx
0x140185f7e  mov     rcx, [rsi+310h]
0x140185f85  add     rcx, 0A8h
0x140185f8c  lea     rax, [rsi+40h]
0x140185f90  lea     r9, [rsi+28h]
0x140185f94  lea     r8, [rsi+0C4h]
0x140185f9b  lea     rdx, [rsp+400h+var_3B0]
0x140185fa0  mov     [rsp+400h+var_3D0], rdx
0x140185fa5  mov     [rsp+400h+var_3D8], rcx
0x140185faa  mov     [rsp+400h+var_3E0], rax
0x140185faf  lea     rdx, aUpdateGvsnAlre; "Update GVSN already known updateName:%w"...
0x140185fb6  lea     rcx, [rsp+400h+var_3A8]
0x140185fbb  call    ??$DbgPrint@G$$BY0BAF@GVUID@@VGVSN@@U_GUID@@PEBG@dbgobj@@QEAA_KPEBGAEAY0BAF@$$CBGAEBVUID@@AEBVGVSN@@AEBU_GUID@@AEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort [261],UID,GVSN,_GUID,ushort const *>(ushort const *,ushort const (&)[261],UID const &,GVSN const &,_GUID const &,ushort const * const &)
0x140185fc0  mov     rdx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140185fc7  mov     dword ptr [rsi+20h], 3
0x140185fce  jmp     short loc_140185FD7
0x140185fd0  mov     rdx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140185fd7  cmp     dword ptr [rsi+20h], 1
0x140185fdb  jnz     loc_140186A04
0x140185fe1  test    rdx, rdx
0x140185fe4  jz      loc_140186075
0x140185fea  cmp     [rdx+40h], r14d
0x140185fee  jz      loc_140186075
0x140185ff4  cmp     [rdx+38h], ebx
0x140185ff7  jl      short loc_140186075
0x140185ff9  lea     rax, aMeetInstalltom; "Meet::InstallTombstone"
0x140186000  mov     [rsp+400h+var_390], rax
0x140186005  mov     [rsp+400h+var_388], 1490h
0x14018600d  mov     [rsp+400h+var_384], ebx
0x140186011  lea     rax, aMeet; "MEET"
0x140186018  mov     [rbp+300h+var_380], rax
0x14018601c  mov     rax, [rsi+318h]
0x140186023  mov     rcx, [rax+0C8h]
0x14018602a  add     rcx, 12h
0x14018602e  mov     [rsp+400h+var_3B0], rcx
0x140186033  mov     rcx, [rsi+310h]
0x14018603a  add     rcx, 0A8h
0x140186041  lea     rax, [rsi+40h]
0x140186045  lea     r9, [rsi+28h]
0x140186049  lea     r8, [rsi+0C4h]
0x140186050  lea     rdx, [rsp+400h+var_3B0]
0x140186055  mov     [rsp+400h+var_3D0], rdx
0x14018605a  mov     [rsp+400h+var_3D8], rcx
0x14018605f  mov     [rsp+400h+var_3E0], rax
0x140186064  lea     rdx, aMovingOutExist; "Moving out existing content updateName:"...
0x14018606b  lea     rcx, [rsp+400h+var_390]
0x140186070  call    ??$DbgPrint@G$$BY0BAF@GVUID@@VGVSN@@U_GUID@@PEBG@dbgobj@@QEAA_KPEBGAEAY0BAF@$$CBGAEBVUID@@AEBVGVSN@@AEBU_GUID@@AEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort [261],UID,GVSN,_GUID,ushort const *>(ushort const *,ushort const (&)[261],UID const &,GVSN const &,_GUID const &,ushort const * const &)
0x140186075  mov     [rsp+400h+var_3E0], r14; struct _FILETIME *
0x14018607a  lea     r9, [rbp+300h+var_370]; struct Usn *
0x14018607e  mov     r8, r15; struct Meet::RelatedToUpdate *
0x140186081  mov     rdx, r12; struct Db *
0x140186084  mov     rcx, rsi; this
0x140186087  call    ?MoveOut@Meet@@AEAAPEAVFrsStatus@@PEAVDb@@AEAVRelatedToUpdate@1@AEAVUsn@@PEAU_FILETIME@@@Z; Meet::MoveOut(Db *,Meet::RelatedToUpdate &,Usn &,_FILETIME *)
0x14018608c  mov     rdi, rax
0x14018608f  test    rax, rax
0x140186092  jnz     loc_1401869BD
0x140186098  mov     rdx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14018609f  cmp     dword ptr [rsi+20h], 1
0x1401860a3  jnz     loc_140186A04
0x1401860a9  test    byte ptr [rsi+0C0h], 2
0x1401860b0  jz      loc_14018619E
0x1401860b6  cmp     [r15+2D8h], r14d
0x1401860bd  jz      loc_14018619E
0x1401860c3  mov     rcx, r15; this
0x1401860c6  call    ?Alive@ID_RECORD@@QEBAHXZ; ID_RECORD::Alive(void)
0x1401860cb  test    eax, eax
0x1401860cd  jz      loc_14018619E
0x1401860d3  test    rdx, rdx
0x1401860d6  jz      loc_140186167
0x1401860dc  cmp     [rdx+40h], r14d
0x1401860e0  jz      loc_140186167
0x1401860e6  cmp     [rdx+38h], ebx
0x1401860e9  jl      short loc_140186167
0x1401860eb  lea     rax, aMeetInstalltom; "Meet::InstallTombstone"
0x1401860f2  mov     [rsp+400h+var_390], rax
0x1401860f7  mov     [rsp+400h+var_388], 1499h
0x1401860ff  mov     [rsp+400h+var_384], ebx
0x140186103  lea     rax, aMeet; "MEET"
0x14018610a  mov     [rbp+300h+var_380], rax
0x14018610e  mov     rax, [rsi+318h]
0x140186115  mov     rcx, [rax+0C8h]
0x14018611c  add     rcx, 12h
0x140186120  mov     [rsp+400h+var_3B0], rcx
0x140186125  mov     rcx, [rsi+310h]
0x14018612c  add     rcx, 0A8h
0x140186133  lea     rax, [rsi+40h]
0x140186137  lea     r9, [rsi+28h]
0x14018613b  lea     r8, [rsi+0C4h]
0x140186142  lea     rdx, [rsp+400h+var_3B0]
0x140186147  mov     [rsp+400h+var_3D0], rdx
0x14018614c  mov     [rsp+400h+var_3D8], rcx
0x140186151  mov     [rsp+400h+var_3E0], rax
0x140186156  lea     rdx, aTombstoningChi; "Tombstoning children if the update forc"...
0x14018615d  lea     rcx, [rsp+400h+var_390]
0x140186162  call    ??$DbgPrint@G$$BY0BAF@GVUID@@VGVSN@@U_GUID@@PEBG@dbgobj@@QEAA_KPEBGAEAY0BAF@$$CBGAEBVUID@@AEBVGVSN@@AEBU_GUID@@AEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort [261],UID,GVSN,_GUID,ushort const *>(ushort const *,ushort const (&)[261],UID const &,GVSN const &,_GUID const &,ushort const * const &)
0x140186167  mov     rax, [rbp+300h+var_370]
0x14018616b  mov     [r15+2A8h], rax
0x140186172  mov     r9d, [rsi+0BCh]
0x140186179  and     r9d, 10h; int
0x14018617d  mov     r8, r15; struct ID_RECORD *
0x140186180  mov     rdx, r12; struct Db *
0x140186183  mov     rcx, rsi; this
0x140186186  call    ?DeleteChildren@Meet@@AEAAPEAVFrsStatus@@PEAVDb@@AEAVID_RECORD@@H@Z; Meet::DeleteChildren(Db *,ID_RECORD &,int)
0x14018618b  mov     rdi, rax
0x14018618e  test    rax, rax
0x140186191  jnz     loc_1401869BD
0x140186197  mov     rdx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14018619e  cmp     dword ptr [rsi+20h], 1
0x1401861a2  jnz     loc_140186A04
0x1401861a8  test    rdx, rdx
0x1401861ab  jz      loc_14018623C
0x1401861b1  cmp     [rdx+40h], r14d
0x1401861b5  jz      loc_14018623C
0x1401861bb  cmp     [rdx+38h], ebx
0x1401861be  jl      short loc_14018623C
0x1401861c0  lea     rax, aMeetInstalltom; "Meet::InstallTombstone"
0x1401861c7  mov     [rsp+400h+var_390], rax
0x1401861cc  mov     [rsp+400h+var_388], 14A3h
0x1401861d4  mov     [rsp+400h+var_384], ebx
0x1401861d8  lea     rax, aMeet; "MEET"
0x1401861df  mov     [rbp+300h+var_380], rax
0x1401861e3  mov     rax, [rsi+318h]
0x1401861ea  mov     rcx, [rax+0C8h]
0x1401861f1  add     rcx, 12h
0x1401861f5  mov     [rsp+400h+var_3B0], rcx
0x1401861fa  mov     rcx, [rsi+310h]
0x140186201  add     rcx, 0A8h
0x140186208  lea     rax, [rsi+40h]
0x14018620c  lea     r9, [rsi+28h]
0x140186210  lea     r8, [rsi+0C4h]
0x140186217  lea     rdx, [rsp+400h+var_3B0]
0x14018621c  mov     [rsp+400h+var_3D0], rdx
0x140186221  mov     [rsp+400h+var_3D8], rcx
0x140186226  mov     [rsp+400h+var_3E0], rax
0x14018622b  lea     rdx, aInsertingTheUp; "Inserting the update into the database "...
0x140186232  lea     rcx, [rsp+400h+var_390]
0x140186237  call    ??$DbgPrint@G$$BY0BAF@GVUID@@VGVSN@@U_GUID@@PEBG@dbgobj@@QEAA_KPEBGAEAY0BAF@$$CBGAEBVUID@@AEBVGVSN@@AEBU_GUID@@AEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort [261],UID,GVSN,_GUID,ushort const *>(ushort const *,ushort const (&)[261],UID const &,GVSN const &,_GUID const &,ushort const * const &)
0x14018623c  mov     rdx, [rsi+318h]
0x140186243  add     rdx, 0D0h; struct VolumeId *
0x14018624a  lea     rcx, [rbp+300h+var_348]; this
0x14018624e  call    ??0VolumeId@@QEAA@AEBV0@@Z; VolumeId::VolumeId(VolumeId const &)
0x140186253  nop
0x140186254  lea     rbx, [rsi+28h]
0x140186258  mov     rdx, rbx
0x14018625b  lea     rcx, [rbp+300h+var_368]
0x14018625f  call    TombstoneFid
0x140186264  lea     r9, [rbp+300h+var_370]; __int64 *
0x140186268  lea     r8, [rbp+300h+var_368]; struct FileId *
0x14018626c  mov     rdx, rbx; struct ID_UPDATE *
0x14018626f  lea     rcx, [rbp+300h+var_310]; this
0x140186273  call    ??0ID_RECORD@@QEAA@AEBVID_UPDATE@@AEBVFileId@@AEB_J@Z; ID_RECORD::ID_RECORD(ID_UPDATE const &,FileId const &,__int64 const &)
0x140186278  cmp     [r15+2D8h], r14d
0x14018627f  jz      loc_14018678F
0x140186285  lea     rbx, ?DirtyShutdownClockValue@Settings@@3VCDirtyShutdownClockValue@1@A; Settings::CDirtyShutdownClockValue Settings::DirtyShutdownClockValue
0x14018628c  mov     rcx, rbx
0x14018628f  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x140186294  mov     ecx, [rsi+0C0h]
0x14018629a  test    cl, 2
0x14018629d  jz      short loc_140186316
0x14018629f  test    byte ptr [rsi+0BCh], 10h
0x1401862a6  jz      short loc_140186316
0x1401862a8  test    byte ptr [r15+98h], 1
0x1401862b0  jz      short loc_140186316
0x1401862b2  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401862b9  lea     r12, aMeetInstalltom; "Meet::InstallTombstone"
0x1401862c0  lea     r13, aMeet; "MEET"
0x1401862c7  test    rax, rax
0x1401862ca  jz      loc_140186854
0x1401862d0  cmp     [rax+40h], r14d
0x1401862d4  jz      loc_140186854
0x1401862da  cmp     dword ptr [rax+38h], 4
0x1401862de  jl      loc_140186854
0x1401862e4  mov     [rsp+400h+var_390], r12
0x1401862e9  mov     [rsp+400h+var_388], 14B3h
0x1401862f1  mov     [rsp+400h+var_384], 4
0x1401862f9  mov     [rbp+300h+var_380], r13
0x1401862fd  mov     r8, r15
0x140186300  lea     rdx, aSkippingUpdate; "Skipping update of name conflicting tom"...
0x140186307  lea     rcx, [rsp+400h+var_390]
0x14018630c  call    ??$DbgPrint@GVID_RECORD@@@dbgobj@@QEAA_KPEBGAEBVID_RECORD@@@Z; dbgobj::DbgPrint<ushort,ID_RECORD>(ushort const *,ID_RECORD const &)
0x140186311  jmp     loc_140186854
0x140186316  mov     eax, [rsi+308h]
0x14018631c  cmp     eax, 2
0x14018631f  jnz     short loc_140186395
0x140186321  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140186328  test    rax, rax
0x14018632b  jz      short loc_140186376
0x14018632d  cmp     [rax+40h], r14d
0x140186331  jz      short loc_140186376
0x140186333  cmp     dword ptr [rax+38h], 4
0x140186337  jl      short loc_140186376
0x140186339  lea     rax, aMeetInstalltom; "Meet::InstallTombstone"
0x140186340  mov     [rsp+400h+var_3A8], rax
0x140186345  mov     [rsp+400h+var_3A0], 14B6h
  ... truncated ...
```
