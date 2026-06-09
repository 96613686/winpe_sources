# Meet::InstallStep(ShutdownObject &)

- ea: `0x140185024`
- end: `0x140185d83`
- name: `?InstallStep@Meet@@AEAAPEAVFrsStatus@@AEAVShutdownObject@@@Z`
- size: `3423`
- prototype: `struct FrsStatus *__fastcall(Meet *__hidden this, struct ShutdownObject *)`
- caller_count: `1`
- callee_count: `41`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140182d78`

## callees

- `0x1400036a0`
- `0x14000c910`
- `0x14000e34c`
- `0x14002c1c0`
- `0x14006f224`
- `0x14007f9f4`
- `0x14009071c`
- `0x1400923f8`
- `0x14009d478`
- `0x14009d5e0`
- `0x1400aebc0`
- `0x140118934`
- `0x14014be98`
- `0x140164b50`
- `0x14017af28`
- `0x14017b310`
- `0x14017b604`
- `0x14017d05c`
- `0x14017d414`
- `0x14017d448`
- `0x14017e2e8`
- `0x14017fa28`
- `0x140180194`
- `0x140181268`
- `0x1401821ac`
- `0x1401835dc`
- `0x1401838c8`
- `0x140183950`
- `0x1401842fc`
- `0x140184338`
- `0x140185024`
- `0x14018718c`
- `0x140188650`
- `0x140189848`
- `0x14018aa10`
- `0x14018b274`
- `0x14018bf00`
- `0x1401b8a00`
- `0x1401b9494`
- `0x1401bda10`
- `0x140223010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14018533e`
- `KERNEL32!EnterCriticalSection` at `0x14018533e`
- `KERNEL32!GetCurrentThreadId` at `0x1401850b5`
- `KERNEL32!GetCurrentThreadId` at `0x14018524b`
- `KERNEL32!GetCurrentThreadId` at `0x140185cfa`
- `KERNEL32!GetCurrentThreadId` at `0x1401850b5`
- `KERNEL32!GetCurrentThreadId` at `0x14018524b`
- `KERNEL32!GetCurrentThreadId` at `0x140185cfa`

## string_xrefs

- `0x140185326`: `Acquiring the updateChildrenParentLock. updateName:%ws uid:%? gvsn:%? connId:%? csName:%?`
- `0x1401850d6`: `Meet::InstallStep`
- `0x1401852b9`: `Meet::InstallStep`
- `0x140185378`: `Meet::InstallStep`
- `0x140185481`: `Meet::InstallStep`
- `0x140185833`: `Meet::InstallStep`
- `0x140185a61`: `Meet::InstallStep`
- `0x140185b2e`: `Meet::InstallStep`
- `0x1401851a8`: `syncType is SUBORDINATE_SYNC but no valid subordinateMonitor task updateName:%ws uid:%? gvsn:%? connId:%? csName:%?`
- `0x1401858a5`: `Failed download. updateName:%ws uid:%? gvsn:%? connId:%? csName:%? err:%?`
- `0x140185bd1`: `Done installing file updateName:%ws uid:%? gvsn:%? connId:%? csName:%?`
- `0x1401854ee`: `Update version already known, but not subsumed updateName:%ws uid:%? gvsn:%? connId:%? csName:%?`
- `0x140185c64`: `Deleting fid in installing updateName:%ws uid:%? gvsn:%? connId:%? csName:%?`
- `0x140185d17`: `Meet::InstallStep`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
struct FrsStatus *__fastcall Meet::InstallStep(Meet *this, struct ShutdownObject *a2)
{
  __int64 v3; // rsi
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, __int128 *, _QWORD); // rbx
  DWORD CurrentThreadId; // eax
  struct FrsStatus *v7; // r15
  int v8; // r12d
  int v9; // r13d
  unsigned int v10; // eax
  __int64 v11; // rax
  __int64 v12; // rbx
  DWORD v13; // eax
  int v14; // edi
  __int64 v15; // rax
  struct ShutdownObject *v16; // rbx
  struct FrsStatus *v17; // rax
  struct FrsStatus *v18; // rax
  struct FrsStatus *Parent; // rax
  struct FrsStatus *NameRelated; // rax
  struct FrsStatus *v21; // rax
  int v22; // edi
  Meet *v23; // rcx
  int v24; // eax
  Meet *v25; // rcx
  struct Meet::RelatedToUpdate *v26; // r8
  int v27; // r9d
  int v28; // r11d
  struct StageReader *v29; // r10
  int v30; // ebx
  __int64 v31; // rax
  struct ShutdownObject *v32; // rbx
  struct FrsStatus *v33; // rax
  struct FrsStatus *v34; // rcx
  struct FrsStatus *v35; // r9
  struct FrsStatus *v36; // r8
  struct FrsStatus *v37; // rdx
  struct FrsStatus *v38; // rax
  struct StageReader *v39; // r10
  struct FrsStatus *v40; // rax
  struct FrsStatus *v41; // rax
  __int64 v42; // rax
  __int64 v43; // rdi
  __int64 v44; // rbx
  LPCRITICAL_SECTION v45; // rax
  DWORD v46; // eax
  __int64 v47; // rcx
  int v49; // [rsp+50h] [rbp-B0h] BYREF
  struct Db *v50; // [rsp+58h] [rbp-A8h] BYREF
  struct FrsStatus *v51; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v52; // [rsp+68h] [rbp-98h] BYREF
  const wchar_t *v53; // [rsp+70h] [rbp-90h] BYREF
  int v54; // [rsp+78h] [rbp-88h]
  int v55; // [rsp+7Ch] [rbp-84h]
  const wchar_t *v56; // [rsp+80h] [rbp-80h]
  struct FrsStatus *v57; // [rsp+88h] [rbp-78h] BYREF
  __int64 v58; // [rsp+90h] [rbp-70h] BYREF
  int v59; // [rsp+98h] [rbp-68h]
  unsigned int v60; // [rsp+9Ch] [rbp-64h] BYREF
  struct StageReader *v61; // [rsp+A0h] [rbp-60h] BYREF
  int v62[2]; // [rsp+A8h] [rbp-58h] BYREF
  int v63; // [rsp+B0h] [rbp-50h] BYREF
  int v64; // [rsp+B4h] [rbp-4Ch] BYREF
  int v65; // [rsp+B8h] [rbp-48h]
  struct ShutdownObject *v66; // [rsp+C0h] [rbp-40h]
  __int128 v67; // [rsp+C8h] [rbp-38h] BYREF
  int v68; // [rsp+E0h] [rbp-20h] BYREF
  char *v69; // [rsp+E8h] [rbp-18h]
  const wchar_t *v70; // [rsp+F0h] [rbp-10h] BYREF
  int v71; // [rsp+F8h] [rbp-8h]
  int v72; // [rsp+FCh] [rbp-4h]
  const wchar_t *v73; // [rsp+100h] [rbp+0h]
  _BYTE v74[8]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v75[728]; // [rsp+110h] [rbp+10h] BYREF
  int v76; // [rsp+3E8h] [rbp+2E8h]
  wchar_t v77[74]; // [rsp+3F0h] [rbp+2F0h] BYREF
  char v78; // [rsp+484h] [rbp+384h]
  int v79; // [rsp+6C8h] [rbp+5C8h]
  _BYTE v80[688]; // [rsp+6D0h] [rbp+5D0h] BYREF
  _BYTE v81[32]; // [rsp+980h] [rbp+880h] BYREF

  v66 = a2;
  v67 = 0;
  v3 = 0;
  v50 = 0;
  Meet::RelatedToUpdate::RelatedToUpdate((Meet::RelatedToUpdate *)v75);
  Meet::RelatedToUpdate::RelatedToUpdate((Meet::RelatedToUpdate *)v77);
  ID_RECORD::ID_RECORD((ID_RECORD *)v80);
  v61 = 0;
  v49 = 1;
  v63 = 0;
  v60 = 0;
  v58 = 0;
  v59 = 0;
  v65 = 0;
  v4 = *((_QWORD *)this + 100);
  v5 = *(__int64 (__fastcall **)(__int64, __int128 *, _QWORD))(*(_QWORD *)v4 + 32LL);
  CurrentThreadId = GetCurrentThreadId();
  v7 = (struct FrsStatus *)v5(v4, &v67, CurrentThreadId);
  if ( !v7 )
  {
    (*(void (__fastcall **)(_QWORD, struct Db **))(*(_QWORD *)v67 + 48LL))(v67, &v50);
    if ( *((_DWORD *)this + 194) == 2 )
    {
      InConnection::GetSubordinateMonitor(*((_QWORD *)this + 98), (char *)this + 40, (char *)this + 816);
      if ( !*((_QWORD *)this + 102)
        && g_DebugLog
        && LODWORD(g_DebugLog[1].LockSemaphore)
        && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
      {
        v70 = L"Meet::InstallStep";
        v71 = 1574;
        v72 = 2;
        v73 = L"MEET";
        v52 = *(_QWORD *)(*((_QWORD *)this + 99) + 200LL) + 18LL;
        dbgobj::DbgPrint<unsigned short,unsigned short [261],UID,GVSN,_GUID,unsigned short const *>(
          (unsigned int)&v70,
          (unsigned int)L"syncType is SUBORDINATE_SYNC but no valid subordinateMonitor task updateName:%ws uid:%? gvsn:%? "
                         "connId:%? csName:%?",
          (_DWORD)this + 196,
          (_DWORD)this + 40,
          (__int64)this + 64,
          *((_QWORD *)this + 98) + 168LL,
          (__int64)&v52);
      }
    }
  }
  while ( !v7 && v49 && *((_DWORD *)this + 8) == 1 )
  {
    LODWORD(v51) = 0;
    v8 = 0;
    v64 = 0;
    v9 = 0;
    LODWORD(v57) = 0;
    v10 = Settings::GenericDwordSetting::operator()(&Settings::TransactionsInstallMaxCount);
    if ( v60 > v10 )
    {
      *((_DWORD *)this + 8) = 2;
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v53 = L"Meet::InstallStep";
        v54 = 1591;
        v55 = 4;
        v56 = L"MEET";
        v42 = *((_QWORD *)this + 99);
        v43 = v42 + 168;
        v52 = *(_QWORD *)(v42 + 200) + 18LL;
        v44 = *((_QWORD *)this + 98) + 168LL;
        LODWORD(v51) = Settings::GenericDwordSetting::operator()(&Settings::TransactionsInstallMaxCount);
        dbgobj::DbgPrint<unsigned short,unsigned long,unsigned long,unsigned short [261],UID,GVSN,_GUID,unsigned short const *,_GUID>(
          (unsigned int)&v53,
          (_DWORD)this + 196,
          (unsigned int)&v60,
          (unsigned int)&v51,
          (__int64)this + 196,
          (__int64)this + 40,
          (__int64)this + 64,
          v44,
          (__int64)&v52,
          v43);
      }
      break;
    }
    v49 = 0;
    ++v60;
    if ( (*((_BYTE *)this + 192) & 1) == 0 )
    {
      v11 = TombstoneFid(v74, (char *)this + 40);
      std::_Tree<std::_Tset_traits<FileId,std::less<FileId>,std::allocator<FileId>,0>>::insert<0,0>(
        (char *)this + 1056,
        &v70,
        v11);
    }
    v52 = 0;
    if ( *((_DWORD *)this + 214) )
    {
      v12 = *((_QWORD *)this + 99);
      v13 = GetCurrentThreadId();
      CREWLock::AcquireWriteLock((CREWLock *)(v12 + 1008), v13);
      v52 = *((_QWORD *)this + 99) + 1008LL;
      v14 = 1;
      v59 = 1;
    }
    else
    {
      v14 = v59;
    }
    v68 = 0;
    v69 = (char *)this + 1032;
    if ( *((_DWORD *)this + 258) == 2 )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
      {
        v53 = L"Meet::InstallStep";
        v54 = 1634;
        v55 = 5;
        v56 = L"MEET";
        *(_QWORD *)v62 = *(_QWORD *)(*((_QWORD *)this + 99) + 200LL) + 18LL;
        dbgobj::DbgPrint<unsigned short,unsigned short [261],UID,GVSN,_GUID,unsigned short const *>(
          (unsigned int)&v53,
          (unsigned int)L"Acquiring the updateChildrenParentLock. updateName:%ws uid:%? gvsn:%? connId:%? csName:%?",
          (_DWORD)this + 196,
          (_DWORD)this + 40,
          (__int64)this + 64,
          *((_QWORD *)this + 98) + 168LL,
          (__int64)v62);
      }
      EnterCriticalSection(&VolumeManager::updateChildrenParentCS);
      *((_DWORD *)this + 258) = 3;
      v68 = 1;
    }
    Meet::LockFids(this, v50);
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      v53 = L"Meet::InstallStep";
      v54 = 1640;
      v55 = 5;
      v56 = L"MEET";
      dbgobj::DbgPrint<unsigned short>(&v53, L"Start transaction");
    }
    v15 = (*(__int64 (__fastcall **)(struct Db *, _QWORD))(*(_QWORD *)v50 + 16LL))(v50, 0);
    v7 = (struct FrsStatus *)v15;
    if ( *((_DWORD *)this + 8) != 1 )
      goto LABEL_107;
    if ( v15 )
      goto LABEL_107;
    if ( v49 )
      goto LABEL_107;
    v16 = v66;
    v17 = Meet::ProcessUid(this, v66, v50, (struct Meet::RelatedToUpdate *)v75, &v49);
    v7 = v17;
    if ( *((_DWORD *)this + 8) != 1 )
      goto LABEL_107;
    if ( v17 )
      goto LABEL_107;
    if ( v49 )
      goto LABEL_107;
    v18 = Meet::VersionIsKnown(this, v50, &v63);
    v7 = v18;
    if ( *((_DWORD *)this + 8) != 1 || v18 || v49 )
      goto LABEL_107;
    if ( v63 && g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      v53 = L"Meet::InstallStep";
      v54 = 1667;
      v55 = 3;
      v56 = L"MEET";
      *(_QWORD *)v62 = *(_QWORD *)(*((_QWORD *)this + 99) + 200LL) + 18LL;
      dbgobj::DbgPrint<unsigned short,unsigned short [261],UID,GVSN,_GUID,unsigned short const *>(
        (unsigned int)&v53,
        (unsigned int)L"Update version already known, but not subsumed updateName:%ws uid:%? gvsn:%? connId:%? csName:%?",
        (_DWORD)this + 196,
        (_DWORD)this + 40,
        (__int64)this + 64,
        *((_QWORD *)this + 98) + 168LL,
        (__int64)v62);
    }
    Parent = Meet::GetParent(this, v50, (struct Meet::RelatedToUpdate *)v75, (struct ID_RECORD *)v80, &v49);
    v7 = Parent;
    if ( *((_DWORD *)this + 8) != 1 )
      goto LABEL_107;
    if ( Parent )
      goto LABEL_107;
    if ( v49 )
      goto LABEL_107;
    NameRelated = Meet::GetNameRelated(
                    this,
                    (struct DbManagerInstance *)&v67,
                    &v50,
                    (struct Meet::RelatedToUpdate *)v75,
                    (const struct ID_RECORD *)v80,
                    v14,
                    v16,
                    (struct Meet::RelatedToUpdate *)v77,
                    &v49);
    v7 = NameRelated;
    if ( *((_DWORD *)this + 8) != 1 )
      goto LABEL_107;
    if ( NameRelated )
      goto LABEL_107;
    if ( v49 )
      goto LABEL_107;
    v21 = Meet::ReAnimateNameConflict(
            this,
            v50,
            (struct Meet::RelatedToUpdate *)v75,
            (struct Meet::RelatedToUpdate *)v77,
            &v49);
    v7 = v21;
    if ( *((_DWORD *)this + 8) != 1 || v21 || v49 )
      goto LABEL_107;
    v22 = Meet::InstallMoveEnabled(this, (const struct Meet::RelatedToUpdate *)v75);
    v62[0] = v22;
    v24 = Meet::InstallOverwriteEnabled(v23, (const struct Meet::RelatedToUpdate *)v75);
    v29 = v61;
    if ( v24 )
    {
      if ( (*((_BYTE *)this + 192) & 4) != 0 || v61 )
        v30 = 0;
      else
        v30 = (_DWORD)v7 + 1;
    }
    else
    {
      v30 = v58 == 0;
    }
    if ( v22 || v30 )
    {
      v7 = Meet::DownloadGhostedHeaderEnabled(this, (struct Meet::RelatedToUpdate *)v75, v26, v62, &v64, (int *)&v57);
      v29 = v61;
      v28 = v49;
      v27 = v62[0];
      v8 = v64;
      v9 = (int)v57;
    }
    if ( *((_DWORD *)this + 8) != 1 || v7 || v28 )
      goto LABEL_107;
    if ( v27 || v22 && v65 )
    {
      v40 = Meet::InstallMove(
              this,
              v50,
              (struct Meet::RelatedToUpdate *)v75,
              (struct Meet::RelatedToUpdate *)v77,
              (const struct ID_RECORD *)v80);
LABEL_106:
      v7 = v40;
      goto LABEL_107;
    }
    if ( !v30 )
    {
      if ( Meet::InstallOverwriteEnabled(v25, (const struct Meet::RelatedToUpdate *)v75) )
      {
        v40 = Meet::InstallOverwrite(
                this,
                v50,
                v39,
                (struct Meet::RelatedToUpdate *)v75,
                (struct Meet::RelatedToUpdate *)v77,
                (const struct ID_RECORD *)v80);
      }
      else
      {
        if ( v76
          || !v79
          || (v78 & 0x10) == 0
          || !(unsigned int)ID_RECORD::Alive((ID_RECORD *)v77)
          || (*((_BYTE *)this + 192) & 1) == 0
          || (*((_BYTE *)this + 188) & 0x10) == 0 )
        {
          v41 = Meet::InstallRename(
                  this,
                  v50,
                  (struct FileId *)&v58,
                  (struct Meet::RelatedToUpdate *)v75,
                  (struct Meet::RelatedToUpdate *)v77,
                  (const struct ID_RECORD *)v80);
          v7 = v41;
          if ( v41 && *((_DWORD *)v41 + 1) == 112 )
            LODWORD(v51) = 1;
          goto LABEL_107;
        }
        v40 = Meet::UidInherit(
                this,
                v50,
                v59,
                v66,
                (struct Meet::RelatedToUpdate *)v75,
                (struct Meet::RelatedToUpdate *)v77,
                &v49,
                1);
      }
      goto LABEL_106;
    }
    if ( v29 )
    {
      close_delete::close<DbIterator<ID_RECORD>>(v29);
      v61 = 0;
    }
    v58 = 0;
    v31 = (*(__int64 (__fastcall **)(struct Db *, __int64))(*(_QWORD *)v50 + 24LL))(v50, 1);
    v7 = (struct FrsStatus *)v31;
    if ( *((_DWORD *)this + 8) == 1 && !v31 && !v49 )
    {
      (*(void (__fastcall **)(_QWORD, struct Db **))(*(_QWORD *)v67 + 64LL))(v67, &v50);
      v49 = 1;
      v32 = v66;
      if ( v8 )
      {
        v33 = Meet::DownloadGhostedHeader(this, v66, (const struct FileId *)v81, (struct FileId *)&v58);
        v7 = v33;
        v51 = v33;
        if ( v33 )
        {
          v57 = v33;
          v34 = v33;
          v35 = v33;
          v36 = v33;
          do
          {
            v37 = v36;
            if ( *((_DWORD *)v34 + 1) != 9027 )
              break;
            v33 = (struct FrsStatus *)*((_QWORD *)v35 + 6);
            v34 = v33;
            v57 = v33;
            v35 = v33;
            v36 = v33;
            v37 = v33;
          }
          while ( v33 );
          if ( v33 && *((_DWORD *)v37 + 1) == 9304 )
          {
            CLEAR_ERROR(&v51);
            if ( !v22 || v9 )
              v8 = 0;
            else
              v65 = 1;
            v7 = v51;
          }
        }
      }
      if ( !v7 && !v8 )
      {
        v38 = Meet::Download(
                this,
                v32,
                (const struct Meet::RelatedToUpdate *)v75,
                v77,
                (const struct FileId *)v81,
                0,
                &v61,
                (struct FileId *)&v58);
        v7 = v38;
        v51 = v38;
        if ( v38 )
        {
          if ( *((_DWORD *)v38 + 1) == 9047 )
          {
            if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
            {
              v53 = L"Meet::InstallStep";
              v54 = 1810;
              v55 = 5;
              v56 = L"MEET";
              v57 = (struct FrsStatus *)(*(_QWORD *)(*((_QWORD *)this + 99) + 200LL) + 18LL);
              dbgobj::DbgPrint<unsigned short,unsigned short [261],UID,GVSN,_GUID,unsigned short const *,FrsStatus>(
                (unsigned int)&v53,
                (unsigned int)L"Failed download. updateName:%ws uid:%? gvsn:%? connId:%? csName:%? err:%?",
                (_DWORD)this + 196,
                (_DWORD)this + 40,
                (__int64)this + 64,
                *((_QWORD *)this + 98) + 168LL,
                (__int64)&v57,
                (__int64)v38);
            }
            CLEAR_ERROR(&v51);
            v7 = v51;
          }
        }
      }
      (*(void (__fastcall **)(_QWORD, struct Db **))(*(_QWORD *)v67 + 48LL))(v67, &v50);
      goto LABEL_93;
    }
LABEL_107:
    v7 = DbUtil::CommitTransaction(v50, v7, 1);
    if ( (_DWORD)v51 )
      ContentSetManager::ReportDiskFull(*((ContentSetManager **)this + 99), 0);
LABEL_93:
    ScopedUpdateChildrenParentLock::~ScopedUpdateChildrenParentLock((ScopedUpdateChildrenParentLock *)&v68);
    ScopedAttachCrewLock::~ScopedAttachCrewLock((ScopedAttachCrewLock *)&v52);
  }
  if ( v50 )
  {
    (*(void (__fastcall **)(_QWORD, struct Db **))(*(_QWORD *)v67 + 64LL))(v67, &v50);
    v45 = g_DebugLog;
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      v53 = L"Meet::InstallStep";
      v54 = 1870;
      v55 = 5;
      v56 = L"MEET";
      v52 = *(_QWORD *)(*((_QWORD *)this + 99) + 200LL) + 18LL;
      dbgobj::DbgPrint<unsigned short,unsigned short [261],UID,GVSN,_GUID,unsigned short const *>(
        (unsigned int)&v53,
        (unsigned int)L"Done installing file updateName:%ws uid:%? gvsn:%? connId:%? csName:%?",
        (_DWORD)this + 196,
        (_DWORD)this + 40,
        (__int64)this + 64,
        *((_QWORD *)this + 98) + 168LL,
        (__int64)&v52);
      v45 = g_DebugLog;
    }
    if ( v58 )
    {
      if ( v45 && LODWORD(v45[1].LockSemaphore) && SLODWORD(v45[1].OwningThread) >= 4 )
      {
        v53 = L"Meet::InstallStep";
        v54 = 1873;
        v55 = 4;
        v56 = L"MEET";
        v52 = *(_QWORD *)(*((_QWORD *)this + 99) + 200LL) + 18LL;
        dbgobj::DbgPrint<unsigned short,unsigned short [261],UID,GVSN,_GUID,unsigned short const *>(
          (unsigned int)&v53,
          (unsigned int)L"Deleting fid in installing updateName:%ws uid:%? gvsn:%? connId:%? csName:%?",
          (_DWORD)this + 196,
          (_DWORD)this + 40,
          (__int64)this + 64,
          *((_QWORD *)this + 98) + 168LL,
          (__int64)&v52);
      }
      v57 = NtfsFileSystem::Delete(
              (NtfsFileSystem *)Meet::fs,
              (const struct VolumeId *)(*((_QWORD *)this + 99) + 208LL),
              (const struct FileId *)&v58,
              0);
      CLEAR_ERROR(&v57);
      v58 = 0;
    }
    if ( *((_DWORD *)this + 208) )
    {
      if ( v61 )
      {
        close_delete::close<DbIterator<ID_RECORD>>(v61);
        v61 = 0;
      }
      v57 = Staging::Delete(*((Staging **)this + 128), (Meet *)((char *)this + 40), (Meet *)((char *)this + 64));
      CLEAR_ERROR(&v57);
      *((_DWORD *)this + 208) = 0;
      *((_DWORD *)this + 209) = 2;
    }
  }
  if ( v7 )
  {
    v46 = GetCurrentThreadId();
    v3 = FrsStatusList::PushNewError(
           v47,
           *((unsigned int *)v7 + 1),
           *((unsigned int *)v7 + 2),
           *(unsigned int *)v7,
           "base\\fs\\remotefs\\frs\\src\\sync\\meet.cpp",
           "Meet::InstallStep",
           1889,
           v46,
           v7);
  }
  scoped_any<Rdc::RDCIndexReader *,close_delete,null_t,0>::~scoped_any<Rdc::RDCIndexReader *,close_delete,null_t,0>(&v61);
  DbManagerInstance::FinalizeDbManagerInstance((DbManagerInstance *)&v67);
  return (struct FrsStatus *)v3;
}

```

## disassembly

```asm
0x140185024  mov     [rsp-8+arg_10], rbx
0x140185029  push    rbp
0x14018502a  push    rsi
0x14018502b  push    rdi
0x14018502c  push    r12
0x14018502e  push    r13
0x140185030  push    r14
0x140185032  push    r15
0x140185034  lea     rbp, [rsp-8B0h]
0x14018503c  sub     rsp, 9B0h
0x140185043  mov     rax, cs:__security_cookie
0x14018504a  xor     rax, rsp
0x14018504d  mov     [rbp+8E0h+var_40], rax
0x140185054  mov     [rbp+8E0h+var_920], rdx
0x140185058  mov     r14, rcx
0x14018505b  xorps   xmm0, xmm0
0x14018505e  movdqu  [rbp+8E0h+var_918], xmm0
0x140185063  xor     esi, esi
0x140185065  mov     [rsp+9E0h+var_988], rsi
0x14018506a  lea     rcx, [rbp+8E0h+var_8D0]; this
0x14018506e  call    ??0RelatedToUpdate@Meet@@QEAA@XZ; Meet::RelatedToUpdate::RelatedToUpdate(void)
0x140185073  lea     rcx, [rbp+8E0h+var_5F0]; this
0x14018507a  call    ??0RelatedToUpdate@Meet@@QEAA@XZ; Meet::RelatedToUpdate::RelatedToUpdate(void)
0x14018507f  lea     rcx, [rbp+8E0h+var_310]; this
0x140185086  call    ??0ID_RECORD@@QEAA@XZ; ID_RECORD::ID_RECORD(void)
0x14018508b  mov     [rbp+8E0h+var_940], rsi
0x14018508f  mov     [rsp+9E0h+var_990], 1
0x140185097  mov     [rbp+8E0h+var_930], esi
0x14018509a  mov     [rbp+8E0h+var_944], esi
0x14018509d  mov     [rbp+8E0h+var_950], rsi
0x1401850a1  mov     [rbp+8E0h+var_948], esi
0x1401850a4  mov     [rbp+8E0h+var_928], esi
0x1401850a7  mov     rdi, [r14+320h]
0x1401850ae  mov     rax, [rdi]
0x1401850b1  mov     rbx, [rax+20h]
0x1401850b5  call    cs:__imp_GetCurrentThreadId
0x1401850bc  nop     dword ptr [rax+rax+00h]
0x1401850c1  mov     r8d, eax
0x1401850c4  lea     rdx, [rbp+8E0h+var_918]
0x1401850c8  mov     rcx, rdi
0x1401850cb  mov     rax, rbx
0x1401850ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401850d3  mov     r15, rax
0x1401850d6  lea     r12, aMeetInstallste_0; "Meet::InstallStep"
0x1401850dd  lea     r13, aMeet; "MEET"
0x1401850e4  test    rax, rax
0x1401850e7  jnz     loc_1401851B8
0x1401850ed  mov     rcx, qword ptr [rbp+8E0h+var_918]
0x1401850f1  mov     rax, [rcx]
0x1401850f4  lea     rdx, [rsp+9E0h+var_988]
0x1401850f9  mov     rax, [rax+30h]
0x1401850fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140185102  cmp     dword ptr [r14+308h], 2
0x14018510a  jnz     loc_1401851B8
0x140185110  lea     rbx, [r14+330h]
0x140185117  mov     r8, rbx
0x14018511a  lea     rdx, [r14+28h]
0x14018511e  mov     rcx, [r14+310h]
0x140185125  call    ?GetSubordinateMonitor@InConnection@@QEAAXAEBVID_UPDATE@@AEAV?$ScopedRef@VSubordinateMonitor@@@@@Z; InConnection::GetSubordinateMonitor(ID_UPDATE const &,ScopedRef<SubordinateMonitor> &)
0x14018512a  cmp     [rbx], rsi
0x14018512d  jnz     loc_1401851B8
0x140185133  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14018513a  test    rax, rax
0x14018513d  jz      short loc_1401851B8
0x14018513f  cmp     [rax+40h], esi
0x140185142  jz      short loc_1401851B8
0x140185144  cmp     dword ptr [rax+38h], 2
0x140185148  jl      short loc_1401851B8
0x14018514a  mov     [rbp+8E0h+var_8F0], r12
0x14018514e  mov     [rbp+8E0h+var_8E8], 626h
0x140185155  mov     [rbp+8E0h+var_8E4], 2
0x14018515c  mov     [rbp+8E0h+var_8E0], r13
0x140185160  mov     rax, [r14+318h]
0x140185167  mov     rcx, [rax+0C8h]
0x14018516e  add     rcx, 12h
0x140185172  mov     [rsp+9E0h+var_978], rcx
0x140185177  mov     rcx, [r14+310h]
0x14018517e  add     rcx, 0A8h
0x140185185  lea     rax, [r14+40h]
0x140185189  lea     r8, [r14+0C4h]
0x140185190  lea     rdx, [rsp+9E0h+var_978]
0x140185195  mov     [rsp+9E0h+var_9B0], rdx
0x14018519a  mov     [rsp+9E0h+var_9B8], rcx
0x14018519f  mov     [rsp+9E0h+var_9C0], rax
0x1401851a4  lea     r9, [r14+28h]
0x1401851a8  lea     rdx, aSynctypeIsSubo; "syncType is SUBORDINATE_SYNC but no val"...
0x1401851af  lea     rcx, [rbp+8E0h+var_8F0]
0x1401851b3  call    ??$DbgPrint@G$$BY0BAF@GVUID@@VGVSN@@U_GUID@@PEBG@dbgobj@@QEAA_KPEBGAEAY0BAF@$$CBGAEBVUID@@AEBVGVSN@@AEBU_GUID@@AEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort [261],UID,GVSN,_GUID,ushort const *>(ushort const *,ushort const (&)[261],UID const &,GVSN const &,_GUID const &,ushort const * const &)
0x1401851b8  test    r15, r15
0x1401851bb  jnz     loc_140185B27
0x1401851c1  cmp     [rsp+9E0h+var_990], esi
0x1401851c5  jz      loc_140185B27
0x1401851cb  cmp     dword ptr [r14+20h], 1
0x1401851d0  jnz     loc_140185B27
0x1401851d6  mov     dword ptr [rsp+9E0h+var_980], esi
0x1401851da  mov     r12d, esi
0x1401851dd  mov     [rbp+8E0h+var_92C], esi
0x1401851e0  mov     r13d, esi
0x1401851e3  mov     dword ptr [rbp+8E0h+var_958], esi
0x1401851e6  lea     rcx, ?TransactionsInstallMaxCount@Settings@@3VCTransactionsInstallMaxCount@1@A; Settings::CTransactionsInstallMaxCount Settings::TransactionsInstallMaxCount
0x1401851ed  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x1401851f2  mov     ecx, [rbp+8E0h+var_944]
0x1401851f5  cmp     ecx, eax
0x1401851f7  ja      loc_140185A52
0x1401851fd  mov     [rsp+9E0h+var_990], esi
0x140185201  mov     r15d, 1
0x140185207  add     ecx, r15d
0x14018520a  mov     [rbp+8E0h+var_944], ecx
0x14018520d  test    [r14+0C0h], r15b
0x140185214  jnz     short loc_140185236
0x140185216  lea     rdx, [r14+28h]
0x14018521a  lea     rcx, [rbp+8E0h+var_8D8]
0x14018521e  call    TombstoneFid
0x140185223  mov     r8, rax
0x140185226  lea     rdx, [rbp+8E0h+var_8F0]
0x14018522a  lea     rcx, [r14+420h]
0x140185231  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@VFileId@@U?$less@VFileId@@@std@@V?$allocator@VFileId@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@VFileId@@@std@@@std@@@std@@_N@1@AEBVFileId@@@Z; std::_Tree<std::_Tset_traits<FileId,std::less<FileId>,std::allocator<FileId>,0>>::insert<0,0>(FileId const &)
0x140185236  mov     [rsp+9E0h+var_978], rsi
0x14018523b  cmp     [r14+358h], esi
0x140185242  jz      short loc_140185280
0x140185244  mov     rbx, [r14+318h]
0x14018524b  call    cs:__imp_GetCurrentThreadId
0x140185252  nop     dword ptr [rax+rax+00h]
0x140185257  mov     edx, eax; unsigned __int64
0x140185259  lea     rcx, [rbx+3F0h]; this
0x140185260  call    ?AcquireWriteLock@CREWLock@@QEAAX_K@Z; CREWLock::AcquireWriteLock(unsigned __int64)
0x140185265  mov     rax, [r14+318h]
0x14018526c  add     rax, 3F0h
0x140185272  mov     [rsp+9E0h+var_978], rax
0x140185277  mov     edi, r15d
0x14018527a  mov     [rbp+8E0h+var_948], r15d
0x14018527e  jmp     short loc_140185283
0x140185280  mov     edi, [rbp+8E0h+var_948]
0x140185283  mov     [rbp+8E0h+var_900], esi
0x140185286  lea     rbx, [r14+408h]
0x14018528d  mov     [rbp+8E0h+var_8F8], rbx
0x140185291  cmp     dword ptr [rbx], 2
0x140185294  jnz     loc_140185354
0x14018529a  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401852a1  test    rax, rax
0x1401852a4  jz      loc_140185337
0x1401852aa  cmp     [rax+40h], esi
0x1401852ad  jz      loc_140185337
0x1401852b3  cmp     dword ptr [rax+38h], 5
0x1401852b7  jl      short loc_140185337
0x1401852b9  lea     rax, aMeetInstallste_0; "Meet::InstallStep"
0x1401852c0  mov     [rsp+9E0h+var_970], rax
0x1401852c5  mov     [rsp+9E0h+var_968], 662h
0x1401852cd  mov     [rsp+9E0h+var_964], 5
0x1401852d5  lea     rax, aMeet; "MEET"
0x1401852dc  mov     [rbp+8E0h+var_960], rax
0x1401852e0  mov     rax, [r14+318h]
0x1401852e7  mov     rcx, [rax+0C8h]
0x1401852ee  add     rcx, 12h
0x1401852f2  mov     qword ptr [rbp+8E0h+var_938], rcx
0x1401852f6  mov     rcx, [r14+310h]
0x1401852fd  add     rcx, 0A8h
0x140185304  lea     rax, [r14+40h]
0x140185308  lea     r9, [r14+28h]
0x14018530c  lea     r8, [r14+0C4h]
0x140185313  lea     rdx, [rbp+8E0h+var_938]
0x140185317  mov     [rsp+9E0h+var_9B0], rdx
0x14018531c  mov     [rsp+9E0h+var_9B8], rcx
0x140185321  mov     [rsp+9E0h+var_9C0], rax
0x140185326  lea     rdx, aAcquiringTheUp; "Acquiring the updateChildrenParentLock."...
0x14018532d  lea     rcx, [rsp+9E0h+var_970]
0x140185332  call    ??$DbgPrint@G$$BY0BAF@GVUID@@VGVSN@@U_GUID@@PEBG@dbgobj@@QEAA_KPEBGAEAY0BAF@$$CBGAEBVUID@@AEBVGVSN@@AEBU_GUID@@AEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort [261],UID,GVSN,_GUID,ushort const *>(ushort const *,ushort const (&)[261],UID const &,GVSN const &,_GUID const &,ushort const * const &)
0x140185337  lea     rcx, ?updateChildrenParentCS@VolumeManager@@0VScopedCS@@A; lpCriticalSection
0x14018533e  call    cs:__imp_EnterCriticalSection
0x140185345  nop     dword ptr [rax+rax+00h]
0x14018534a  mov     dword ptr [rbx], 3
0x140185350  mov     [rbp+8E0h+var_900], r15d
0x140185354  mov     rdx, [rsp+9E0h+var_988]; struct Db *
0x140185359  mov     rcx, r14; this
0x14018535c  call    ?LockFids@Meet@@AEAAXPEAVDb@@@Z; Meet::LockFids(Db *)
0x140185361  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140185368  test    rax, rax
0x14018536b  jz      short loc_1401853B0
0x14018536d  cmp     [rax+40h], esi
0x140185370  jz      short loc_1401853B0
0x140185372  cmp     dword ptr [rax+38h], 5
0x140185376  jl      short loc_1401853B0
0x140185378  lea     rax, aMeetInstallste_0; "Meet::InstallStep"
0x14018537f  mov     [rsp+9E0h+var_970], rax
0x140185384  mov     [rsp+9E0h+var_968], 668h
0x14018538c  mov     [rsp+9E0h+var_964], 5
0x140185394  lea     rax, aMeet; "MEET"
0x14018539b  mov     [rbp+8E0h+var_960], rax
0x14018539f  lea     rdx, aStartTransacti_0; "Start transaction"
0x1401853a6  lea     rcx, [rsp+9E0h+var_970]
0x1401853ab  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x1401853b0  mov     rcx, [rsp+9E0h+var_988]
0x1401853b5  mov     rax, [rcx]
0x1401853b8  xor     edx, edx
0x1401853ba  mov     rax, [rax+10h]
0x1401853be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401853c3  mov     r15, rax
0x1401853c6  cmp     dword ptr [r14+20h], 1
0x1401853cb  jnz     loc_140185A1F
0x1401853d1  test    rax, rax
0x1401853d4  jnz     loc_140185A1F
0x1401853da  cmp     [rsp+9E0h+var_990], esi
0x1401853de  jnz     loc_140185A1F
0x1401853e4  lea     rax, [rsp+9E0h+var_990]
0x1401853e9  mov     [rsp+9E0h+var_9C0], rax; int *
0x1401853ee  lea     r9, [rbp+8E0h+var_8D0]; struct Meet::RelatedToUpdate *
0x1401853f2  mov     r8, [rsp+9E0h+var_988]; struct Db *
0x1401853f7  mov     rbx, [rbp+8E0h+var_920]
0x1401853fb  mov     rdx, rbx; struct ShutdownObject *
0x1401853fe  mov     rcx, r14; this
0x140185401  call    ?ProcessUid@Meet@@AEAAPEAVFrsStatus@@AEAVShutdownObject@@PEAVDb@@AEAVRelatedToUpdate@1@AEAH@Z; Meet::ProcessUid(ShutdownObject &,Db *,Meet::RelatedToUpdate &,int &)
0x140185406  mov     r15, rax
0x140185409  cmp     dword ptr [r14+20h], 1
0x14018540e  jnz     loc_140185A1F
0x140185414  test    rax, rax
0x140185417  jnz     loc_140185A1F
0x14018541d  cmp     [rsp+9E0h+var_990], esi
0x140185421  jnz     loc_140185A1F
0x140185427  lea     r8, [rbp+8E0h+var_930]; int *
0x14018542b  mov     rdx, [rsp+9E0h+var_988]; struct Db *
0x140185430  mov     rcx, r14; this
0x140185433  call    ?VersionIsKnown@Meet@@AEAAPEAVFrsStatus@@PEAVDb@@AEAH@Z; Meet::VersionIsKnown(Db *,int &)
0x140185438  mov     r15, rax
0x14018543b  cmp     dword ptr [r14+20h], 1
0x140185440  jnz     loc_140185A1F
0x140185446  test    rax, rax
0x140185449  jnz     loc_140185A1F
0x14018544f  cmp     [rsp+9E0h+var_990], esi
0x140185453  jnz     loc_140185A1F
0x140185459  cmp     [rbp+8E0h+var_930], esi
0x14018545c  jz      loc_1401854FF
0x140185462  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140185469  test    rax, rax
0x14018546c  jz      loc_1401854FF
0x140185472  cmp     [rax+40h], esi
0x140185475  jz      loc_1401854FF
0x14018547b  cmp     dword ptr [rax+38h], 3
0x14018547f  jl      short loc_1401854FF
0x140185481  lea     rax, aMeetInstallste_0; "Meet::InstallStep"
0x140185488  mov     [rsp+9E0h+var_970], rax
0x14018548d  mov     [rsp+9E0h+var_968], 683h
0x140185495  mov     [rsp+9E0h+var_964], 3
0x14018549d  lea     rax, aMeet; "MEET"
0x1401854a4  mov     [rbp+8E0h+var_960], rax
0x1401854a8  mov     rax, [r14+318h]
0x1401854af  mov     rcx, [rax+0C8h]
0x1401854b6  add     rcx, 12h
0x1401854ba  mov     qword ptr [rbp+8E0h+var_938], rcx
0x1401854be  mov     rcx, [r14+310h]
0x1401854c5  add     rcx, 0A8h
0x1401854cc  lea     rax, [r14+40h]
0x1401854d0  lea     r9, [r14+28h]
0x1401854d4  lea     r8, [r14+0C4h]
0x1401854db  lea     rdx, [rbp+8E0h+var_938]
0x1401854df  mov     [rsp+9E0h+var_9B0], rdx
0x1401854e4  mov     [rsp+9E0h+var_9B8], rcx
0x1401854e9  mov     [rsp+9E0h+var_9C0], rax
0x1401854ee  lea     rdx, aUpdateVersionA; "Update version already known, but not s"...
0x1401854f5  lea     rcx, [rsp+9E0h+var_970]
0x1401854fa  call    ??$DbgPrint@G$$BY0BAF@GVUID@@VGVSN@@U_GUID@@PEBG@dbgobj@@QEAA_KPEBGAEAY0BAF@$$CBGAEBVUID@@AEBVGVSN@@AEBU_GUID@@AEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort [261],UID,GVSN,_GUID,ushort const *>(ushort const *,ushort const (&)[261],UID const &,GVSN const &,_GUID const &,ushort const * const &)
0x1401854ff  lea     rax, [rsp+9E0h+var_990]
0x140185504  mov     [rsp+9E0h+var_9C0], rax; int *
0x140185509  lea     r9, [rbp+8E0h+var_310]; struct ID_RECORD *
0x140185510  lea     r8, [rbp+8E0h+var_8D0]; struct Meet::RelatedToUpdate *
0x140185514  mov     rdx, [rsp+9E0h+var_988]; struct Db *
0x140185519  mov     rcx, r14; this
0x14018551c  call    ?GetParent@Meet@@AEAAPEAVFrsStatus@@PEAVDb@@AEAVRelatedToUpdate@1@AEAVID_RECORD@@AEAH@Z; Meet::GetParent(Db *,Meet::RelatedToUpdate &,ID_RECORD &,int &)
0x140185521  mov     r15, rax
0x140185524  cmp     dword ptr [r14+20h], 1
0x140185529  jnz     loc_140185A1F
0x14018552f  test    rax, rax
0x140185532  jnz     loc_140185A1F
0x140185538  cmp     [rsp+9E0h+var_990], esi
0x14018553c  jnz     loc_140185A1F
0x140185542  lea     rax, [rsp+9E0h+var_990]
0x140185547  mov     [rsp+9E0h+var_9A0], rax; int *
0x14018554c  lea     rax, [rbp+8E0h+var_5F0]
0x140185553  mov     [rsp+9E0h+var_9A8], rax; struct Meet::RelatedToUpdate *
0x140185558  mov     [rsp+9E0h+var_9B0], rbx; struct ShutdownObject *
0x14018555d  mov     dword ptr [rsp+9E0h+var_9B8], edi; int
0x140185561  lea     rax, [rbp+8E0h+var_310]
0x140185568  mov     [rsp+9E0h+var_9C0], rax; struct ID_RECORD *
0x14018556d  lea     r9, [rbp+8E0h+var_8D0]; struct Meet::RelatedToUpdate *
0x140185571  lea     r8, [rsp+9E0h+var_988]; struct Db **
0x140185576  lea     rdx, [rbp+8E0h+var_918]; struct DbManagerInstance *
0x14018557a  mov     rcx, r14; this
0x14018557d  call    ?GetNameRelated@Meet@@AEAAPEAVFrsStatus@@AEAVDbManagerInstance@@AEAPEAVDb@@AEAVRelatedToUpdate@1@AEBVID_RECORD@@HAEAVShutdownObject@@2AEAH@Z; Meet::GetNameRelated(DbManagerInstance &,Db * &,Meet::RelatedToUpdate &,ID_RECORD const &,int,ShutdownObject &,Meet::RelatedToUpdate &,int &)
0x140185582  mov     r15, rax
0x140185585  cmp     dword ptr [r14+20h], 1
0x14018558a  jnz     loc_140185A1F
0x140185590  test    rax, rax
0x140185593  jnz     loc_140185A1F
0x140185599  cmp     [rsp+9E0h+var_990], esi
0x14018559d  jnz     loc_140185A1F
0x1401855a3  lea     rax, [rsp+9E0h+var_990]
0x1401855a8  mov     [rsp+9E0h+var_9C0], rax; int *
0x1401855ad  lea     r9, [rbp+8E0h+var_5F0]; struct Meet::RelatedToUpdate *
0x1401855b4  lea     r8, [rbp+8E0h+var_8D0]; struct Meet::RelatedToUpdate *
0x1401855b8  mov     rdx, [rsp+9E0h+var_988]; struct Db *
0x1401855bd  mov     rcx, r14; this
  ... truncated ...
```
