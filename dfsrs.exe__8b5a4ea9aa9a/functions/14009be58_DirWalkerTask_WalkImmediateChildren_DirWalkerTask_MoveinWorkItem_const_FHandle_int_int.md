# DirWalkerTask::WalkImmediateChildren(DirWalkerTask::MoveinWorkItem const &,FHandle *,int &,int &)

- ea: `0x14009be58`
- end: `0x14009ccf6`
- name: `?WalkImmediateChildren@DirWalkerTask@@AEAAPEAVFrsStatus@@AEBVMoveinWorkItem@1@PEAVFHandle@@AEAH2@Z`
- size: `3742`
- prototype: `struct FrsStatus *__usercall@<rax>(DirWalkerTask *__hidden this@<rcx>, const struct DirWalkerTask::MoveinWorkItem *@<rdx>, struct FHandle *@<r8>, int *@<r9>, int *)`
- caller_count: `1`
- callee_count: `38`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140098db4`

## callees

- `0x1400036a0`
- `0x1400046cc`
- `0x14000cdc0`
- `0x14000d980`
- `0x14000dcc0`
- `0x14000e34c`
- `0x140024868`
- `0x140024be4`
- `0x140028fcc`
- `0x14002a6d0`
- `0x14002c160`
- `0x14002c1c0`
- `0x14002c2f4`
- `0x1400379f8`
- `0x140037a70`
- `0x140037f58`
- `0x1400381a8`
- `0x140038468`
- `0x140038564`
- `0x140085aa0`
- `0x1400896e8`
- `0x140089a78`
- `0x14009071c`
- `0x140091f78`
- `0x140096294`
- `0x1400977d0`
- `0x14009789c`
- `0x1400987dc`
- `0x140099c70`
- `0x140099d38`
- `0x14009b188`
- `0x14009bc14`
- `0x14009be58`
- `0x14009cd78`
- `0x1400f92bc`
- `0x140115dd4`
- `0x1401b9494`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14009bf20`
- `KERNEL32!GetCurrentThreadId` at `0x14009c040`
- `KERNEL32!GetCurrentThreadId` at `0x14009c51f`
- `KERNEL32!GetCurrentThreadId` at `0x14009c709`
- `KERNEL32!GetCurrentThreadId` at `0x14009cc75`
- `KERNEL32!GetCurrentThreadId` at `0x14009bf20`
- `KERNEL32!GetCurrentThreadId` at `0x14009c040`
- `KERNEL32!GetCurrentThreadId` at `0x14009c51f`
- `KERNEL32!GetCurrentThreadId` at `0x14009c709`
- `KERNEL32!GetCurrentThreadId` at `0x14009cc75`

## string_xrefs

- `0x14009c181`: `Skipping name:%ws (fid:%?) (moved to another directory)`
- `0x14009c827`: `Skipping name:%ws (fid:%?) (moved to another directory)`
- `0x14009c5f8`: `Ghosted file deleted:%ws (fid:%?)`
- `0x14009c136`: `DirWalkerTask::WalkImmediateChildren`
- `0x14009c2dc`: `DirWalkerTask::WalkImmediateChildren`
- `0x14009c3da`: `DirWalkerTask::WalkImmediateChildren`
- `0x14009c5bc`: `DirWalkerTask::WalkImmediateChildren`
- `0x14009c7eb`: `DirWalkerTask::WalkImmediateChildren`
- `0x14009c9b8`: `DirWalkerTask::WalkImmediateChildren`
- `0x14009cc1b`: `DirWalkerTask::WalkImmediateChildren`
- `0x14009c05d`: `DirWalkerTask::WalkImmediateChildren`
- `0x14009c53c`: `DirWalkerTask::WalkImmediateChildren`
- `0x14009c6d8`: `DirWalkerTask::WalkImmediateChildren`
- `0x14009cc9c`: `DirWalkerTask::WalkImmediateChildren`
- `0x14009c307`: `ID_RECORD in content set being deleted:%?`
- `0x14009ca01`: `Moving between a content set being deleted to an alive onename:%ws (fid:%?)`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
struct FrsStatus *__fastcall DirWalkerTask::WalkImmediateChildren(
        DirWalkerTask *this,
        const struct DirWalkerTask::MoveinWorkItem *a2,
        struct FHandle *a3,
        int *a4,
        int *a5)
{
  __int64 v7; // rdi
  int v8; // r13d
  int v9; // r12d
  unsigned int *UsnConsumer; // rbx
  __int64 v11; // rcx
  __int64 v12; // rax
  struct FrsStatus *v13; // rax
  int v14; // r14d
  struct FrsStatus *v15; // rbx
  struct FrsStatus *OneRecord; // rsi
  __int64 v17; // r13
  int v18; // ebx
  int v19; // eax
  DWORD v20; // eax
  __int64 v21; // rcx
  __int64 v22; // rdx
  const struct DirWalkerTask::MoveinWorkItem *v23; // rbx
  struct FrsStatus *Parent; // rax
  int v25; // r12d
  __int64 *v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rax
  const wchar_t *v29; // rax
  ContentSetManager *v30; // rcx
  int *v31; // rbx
  int v32; // r13d
  int v33; // edx
  const struct DirWalkerTask::MoveinWorkItem *v34; // r13
  const struct DirWalkerTask::MoveinWorkItem *v35; // r12
  __int64 v36; // rbx
  ID_RECORD *v37; // rax
  __int64 v38; // rax
  __int64 v39; // rdx
  DWORD v40; // eax
  __int64 v41; // rcx
  struct FrsStatus *v42; // rax
  const wchar_t *v43; // rdx
  __int64 *v44; // rcx
  __int64 v45; // rbx
  ID_RECORD *v46; // rax
  DWORD v47; // eax
  __int64 v48; // rcx
  struct FrsStatus *v49; // rax
  int v50; // r12d
  const unsigned __int16 *v51; // rax
  struct FrsStatus *v52; // rbx
  struct FrsStatus *v53; // rax
  __int64 v54; // rdx
  int v55; // ecx
  int v56; // edx
  const unsigned __int16 *v57; // rax
  int v58; // r8d
  struct DirWalkerTask::Job *v59; // rdx
  struct DirWalkerTask::MoveinWorkItem *v60; // rbx
  __int64 v61; // rcx
  DWORD CurrentThreadId; // [rsp+38h] [rbp-C8h]
  DWORD v64; // [rsp+38h] [rbp-C8h]
  int v65; // [rsp+60h] [rbp-A0h]
  int v66; // [rsp+64h] [rbp-9Ch]
  int v67; // [rsp+68h] [rbp-98h] BYREF
  int v68; // [rsp+6Ch] [rbp-94h]
  struct FrsStatus *v69; // [rsp+70h] [rbp-90h] BYREF
  __int64 v70; // [rsp+78h] [rbp-88h] BYREF
  __int64 v71; // [rsp+80h] [rbp-80h] BYREF
  __int64 v72; // [rsp+88h] [rbp-78h] BYREF
  const struct DirWalkerTask::MoveinWorkItem *v73; // [rsp+90h] [rbp-70h]
  char v74[8]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v75; // [rsp+A0h] [rbp-60h]
  __int64 v76; // [rsp+A8h] [rbp-58h] BYREF
  int v77; // [rsp+B0h] [rbp-50h]
  __int64 v78; // [rsp+B8h] [rbp-48h] BYREF
  int *v79; // [rsp+C0h] [rbp-40h]
  int v80; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v81; // [rsp+D0h] [rbp-30h] BYREF
  int *v82; // [rsp+D8h] [rbp-28h]
  _QWORD v83[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v84; // [rsp+F0h] [rbp-10h]
  __int64 v85; // [rsp+F8h] [rbp-8h] BYREF
  struct _GUID *v86; // [rsp+100h] [rbp+0h]
  const wchar_t *v87; // [rsp+108h] [rbp+8h] BYREF
  int v88; // [rsp+110h] [rbp+10h]
  int v89; // [rsp+114h] [rbp+14h]
  const wchar_t *v90; // [rsp+118h] [rbp+18h]
  _BYTE v91[16]; // [rsp+120h] [rbp+20h] BYREF
  char v92[16]; // [rsp+130h] [rbp+30h] BYREF
  char v93[16]; // [rsp+140h] [rbp+40h] BYREF
  char v94[16]; // [rsp+150h] [rbp+50h] BYREF
  char v95[16]; // [rsp+160h] [rbp+60h] BYREF
  char v96[712]; // [rsp+170h] [rbp+70h] BYREF
  char v97[712]; // [rsp+438h] [rbp+338h] BYREF
  __int128 v98; // [rsp+700h] [rbp+600h] BYREF
  const wchar_t *v99; // [rsp+710h] [rbp+610h]
  __int64 v100[2]; // [rsp+718h] [rbp+618h] BYREF
  const wchar_t *v101; // [rsp+728h] [rbp+628h]
  __int64 v102[4]; // [rsp+730h] [rbp+630h] BYREF
  _BYTE SystemTimeAsFileTime[20]; // [rsp+750h] [rbp+650h] BYREF
  __int128 v104; // [rsp+764h] [rbp+664h] BYREF
  int v105; // [rsp+774h] [rbp+674h]
  GUID v106; // [rsp+780h] [rbp+680h] BYREF
  char v107; // [rsp+7F9h] [rbp+6F9h]
  __int128 v108; // [rsp+810h] [rbp+710h] BYREF
  const wchar_t *v109; // [rsp+820h] [rbp+720h]
  _QWORD v110[9]; // [rsp+858h] [rbp+758h] BYREF
  char v111; // [rsp+8A4h] [rbp+7A4h]
  char v112; // [rsp+AD0h] [rbp+9D0h]
  _BYTE v113[720]; // [rsp+AE0h] [rbp+9E0h] BYREF

  v82 = a4;
  v73 = a2;
  v79 = a5;
  v83[0] = &FIterator::`vftable';
  v83[1] = (char *)this + 560;
  v7 = 0;
  v84 = 0;
  v86 = (struct _GUID *)(*((_QWORD *)a2 + 1) + 80LL);
  v8 = 0;
  v66 = 0;
  v9 = 0;
  v65 = 0;
  v68 = 0;
  memset_0(&v106, 0, 0x88u);
  *a5 = 0;
  v106 = Guid::ZeroedGuid;
  v107 = 0;
  v81 = 0;
  UsnConsumer = (unsigned int *)VolumeManager::GetUsnConsumer(*((_QWORD *)this + 22), &v81);
  if ( UsnConsumer )
  {
    CurrentThreadId = GetCurrentThreadId();
    v12 = FrsStatusList::PushNewError(
            v11,
            UsnConsumer[1],
            UsnConsumer[2],
            *UsnConsumer,
            "base\\fs\\remotefs\\frs\\src\\db\\dirwalker.cpp",
            "DirWalkerTask::WalkImmediateChildren",
            1803,
            CurrentThreadId,
            UsnConsumer);
LABEL_137:
    v7 = v12;
    goto LABEL_138;
  }
  v13 = FIterator::OpenHandle((FIterator *)v83, a3);
  v14 = 1;
  while ( 1 )
  {
    v15 = v13;
    v69 = v13;
    OneRecord = v13;
    if ( FIterator::AtEnd((FIterator *)v83) || *((_DWORD *)this + 12) || v15 )
      break;
    v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v84 + 32LL))(v84);
    v70 = *(_QWORD *)(v17 + 72);
    v72 = 0;
    LODWORD(v69) = 1;
    v18 = Db::TryLock(*((Db **)this + 56), (const struct FileId *)&v70, (const enum FidLockMan::Type *)&v69);
    ID_RECORD::ID_RECORD((ID_RECORD *)&v108);
    ID_RECORD::ID_RECORD((ID_RECORD *)v113);
    v67 = 0;
    v78 = 0;
    memset(SystemTimeAsFileTime, 0, sizeof(SystemTimeAsFileTime));
    v104 = 0;
    v105 = 0;
    std::wstring::wstring(v102);
    v19 = *(_DWORD *)(v17 + 56);
    LODWORD(v69) = v19 & 0x10;
    LODWORD(v76) = v19 & 0x400;
    std::set<DirWalkerTask::Job *>::set<DirWalkerTask::Job *>(v74);
    LODWORD(v71) = 1;
    v77 = 0;
    if ( v18 )
    {
      std::_Tree<std::_Tset_traits<FileId,std::less<FileId>,std::allocator<FileId>,0>>::insert<0,0>(v74, v92, &v70);
    }
    else
    {
      v20 = GetCurrentThreadId();
      OneRecord = (struct FrsStatus *)FrsStatusList::PushNewError(
                                        v21,
                                        9049,
                                        0,
                                        (unsigned int)((_DWORD)OneRecord + 3),
                                        "base\\fs\\remotefs\\frs\\src\\db\\dirwalker.cpp",
                                        "DirWalkerTask::WalkImmediateChildren",
                                        1842,
                                        v20,
                                        0);
    }
    if ( OneRecord )
    {
      v23 = v73;
    }
    else
    {
      OneRecord = (struct FrsStatus *)(*(__int64 (__fastcall **)(char *, char *, __int64 *, __int64 *, __int64 *, __int64 *, _QWORD, _QWORD, _BYTE *, _QWORD))(*((_QWORD *)this + 70) + 208LL))(
                                        (char *)this + 560,
                                        (char *)this + 224,
                                        &v70,
                                        &v78,
                                        &v72,
                                        v102,
                                        0,
                                        0,
                                        SystemTimeAsFileTime,
                                        0);
      v23 = v73;
      if ( !OneRecord )
      {
        if ( v72 != *((_QWORD *)v73 + 6) )
        {
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
          {
            v100[0] = (__int64)L"DirWalkerTask::WalkImmediateChildren";
            v100[1] = 0x400000748LL;
            v101 = L"DIRW";
            v69 = (struct FrsStatus *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v102);
            dbgobj::DbgPrint<unsigned short,unsigned short const *,FileId>(
              v100,
              L"Skipping name:%ws (fid:%?) (moved to another directory)",
              &v69,
              &v70);
          }
          std::_Tree<std::_Tset_traits<FileId,std::less<FileId>,std::allocator<FileId>,0>>::~_Tree<std::_Tset_traits<FileId,std::less<FileId>,std::allocator<FileId>,0>>(
            v74,
            v22);
          goto LABEL_18;
        }
        Parent = DirWalkerTask::LockGetParent(this, (const struct FileId *)&v72, (struct ID_RECORD *)v113);
        OneRecord = Parent;
        if ( Parent )
        {
          if ( *((_DWORD *)Parent + 1) == 9049 )
          {
            v66 = 1;
          }
          else if ( *((_DWORD *)Parent + 1) == 2 )
          {
            v65 = 1;
          }
        }
        else
        {
          std::_Tree<std::_Tset_traits<FileId,std::less<FileId>,std::allocator<FileId>,0>>::insert<0,0>(v74, v93, &v72);
        }
      }
    }
    v25 = 0;
    *(_OWORD *)v100 = 0;
    v101 = 0;
    if ( OneRecord )
      goto LABEL_93;
    v26 = (__int64 *)*((_QWORD *)this + 56);
    v27 = *v26;
    v85 = 0;
    OneRecord = (struct FrsStatus *)(*(__int64 (__fastcall **)(__int64 *, int *, __int64 *, __int128 *, __int64 *))(v27 + 40))(
                                      v26,
                                      &v67,
                                      &v70,
                                      &v108,
                                      &v85);
    if ( !OneRecord && v67 )
    {
      v28 = v110[0] - *(_QWORD *)&v106.Data1;
      if ( v110[0] == *(_QWORD *)&v106.Data1 )
        v28 = v110[1] - *(_QWORD *)v106.Data4;
      if ( !v28
        || (v80 = 0,
            (OneRecord = (struct FrsStatus *)(*(__int64 (__fastcall **)(_QWORD, int *, _QWORD *, GUID *))(**((_QWORD **)this + 56) + 80LL))(
                                               *((_QWORD *)this + 56),
                                               &v80,
                                               v110,
                                               &v106)) == 0) )
      {
        if ( v67 )
        {
          if ( v107 )
          {
            v25 = 1;
            v67 = 0;
            if ( g_DebugLog )
            {
              if ( LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
              {
                v87 = L"DirWalkerTask::WalkImmediateChildren";
                v88 = 1931;
                v89 = 4;
                v90 = L"DIRW";
                dbgobj::DbgPrint<unsigned short,ID_RECORD>(&v87, L"ID_RECORD in content set being deleted:%?", &v108);
              }
            }
          }
        }
      }
    }
    if ( OneRecord )
      goto LABEL_93;
    if ( v67 )
    {
      *(_OWORD *)v100 = v108;
      v29 = v109;
      v101 = v109;
    }
    else
    {
      if ( !(_DWORD)v76 || *(_DWORD *)(v17 + 64) != -2147483630 )
        goto LABEL_70;
      v77 = 1;
      v30 = *(ContentSetManager **)(*((_QWORD *)v23 + 1) + 8LL);
      if ( !v30 || (unsigned int)ContentSetManager::IsPrimary(v30) )
      {
        OneRecord = (struct FrsStatus *)(*(__int64 (__fastcall **)(char *, __int64, __int64 *, _QWORD))(*((_QWORD *)this + 70) + 128LL))(
                                          (char *)this + 560,
                                          *((_QWORD *)this + 22) + 168LL,
                                          &v70,
                                          0);
        if ( !OneRecord )
        {
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
          {
            v100[0] = (__int64)L"DirWalkerTask::WalkImmediateChildren";
            v100[1] = 0x40000079BLL;
            v101 = L"DIRW";
            v42 = (struct FrsStatus *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v102);
            v43 = L"Ghosted file deleted:%ws (fid:%?)";
            v44 = v100;
            goto LABEL_68;
          }
LABEL_69:
          std::_Tree<std::_Tset_traits<FileId,std::less<FileId>,std::allocator<FileId>,0>>::~_Tree<std::_Tset_traits<FileId,std::less<FileId>,std::allocator<FileId>,0>>(
            v74,
            v39);
          v9 = v65;
LABEL_18:
          v8 = v66;
          goto LABEL_119;
        }
LABEL_93:
        if ( v75 )
          FidLockMan::UnlockEx(
            (FidLockMan *)(*(_QWORD *)(*((_QWORD *)this + 56) + 8LL) + 8LL),
            *((struct Db **)this + 56));
LABEL_95:
        v34 = v73;
        goto LABEL_96;
      }
      v29 = v109;
    }
    if ( v67 && v29 == (const wchar_t *)1 )
    {
LABEL_49:
      v31 = v79;
      v32 = v71;
LABEL_50:
      if ( !v67 )
        goto LABEL_59;
      if ( (v112 & 2) != 0 )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
        {
          *(_QWORD *)&v98 = L"DirWalkerTask::WalkImmediateChildren";
          *((_QWORD *)&v98 + 1) = 0x4000007C2LL;
          v99 = L"DIRW";
          v71 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v102);
          dbgobj::DbgPrint<unsigned short,ID_RECORD,unsigned short const *,FileId,Usn,FileId,UID,unsigned long>(
            (unsigned int)&v98,
            v33,
            (unsigned int)&v108,
            (unsigned int)&v71,
            (__int64)&v70,
            (__int64)&v78,
            (__int64)&v72,
            (__int64)v113,
            (__int64)&v104 + 12);
        }
        v34 = v73;
        OneRecord = (struct FrsStatus *)DirWalkerTask::Validate(
                                          this,
                                          (struct _GUID *)(*((_QWORD *)v73 + 1) + 48LL),
                                          (struct _FILETIME)SystemTimeAsFileTime,
                                          (__int64)&v78,
                                          (__int64)v102,
                                          (__int64)&v67);
        if ( OneRecord )
          goto LABEL_96;
        *v31 = 1;
        v32 = 0;
      }
      if ( !v67 )
      {
LABEL_59:
        if ( !v25 )
          goto LABEL_107;
        v35 = v73;
        v36 = *((_QWORD *)v73 + 1);
        v37 = ID_RECORD::ID_RECORD((ID_RECORD *)v97, (const struct ID_RECORD *)&v108);
        v38 = DirWalkerTask::TombstoneFilteredContent(this, v37, v36);
        OneRecord = (struct FrsStatus *)v38;
        if ( !v38 && (v111 & 0x10) != 0 )
        {
          v68 = 1;
          v40 = GetCurrentThreadId();
          v38 = FrsStatusList::PushNewError(
                  v41,
                  9037,
                  0,
                  3,
                  "base\\fs\\remotefs\\frs\\src\\db\\dirwalker.cpp",
                  "DirWalkerTask::WalkImmediateChildren",
                  2047,
                  v40,
                  0);
          OneRecord = (struct FrsStatus *)v38;
        }
        if ( !v38 )
        {
          LODWORD(v71) = 1;
          if ( (unsigned int)Db::TryLock(
                               *((Db **)this + 56),
                               (const struct FileId *)&v70,
                               (const enum FidLockMan::Type *)&v71) )
          {
            std::_Tree<std::_Tset_traits<FileId,std::less<FileId>,std::allocator<FileId>,0>>::insert<0,0>(
              v74,
              v94,
              &v70);
LABEL_78:
            OneRecord = (struct FrsStatus *)(*(__int64 (__fastcall **)(char *, char *, __int64 *, __int64 *, __int64 *, __int64 *, _QWORD, _QWORD, _BYTE *, _QWORD))(*((_QWORD *)this + 70) + 208LL))(
                                              (char *)this + 560,
                                              (char *)this + 224,
                                              &v70,
                                              &v78,
                                              &v72,
                                              v102,
                                              0,
                                              0,
                                              SystemTimeAsFileTime,
                                              0);
          }
          else
          {
            v47 = GetCurrentThreadId();
            OneRecord = (struct FrsStatus *)FrsStatusList::PushNewError(
                                              v48,
                                              9049,
                                              0,
                                              3,
                                              "base\\fs\\remotefs\\frs\\src\\db\\dirwalker.cpp",
                                              "DirWalkerTask::WalkImmediateChildren",
                                              2059,
                                              v47,
                                              0);
            if ( !OneRecord )
              goto LABEL_78;
          }
        }
        if ( !OneRecord )
        {
          if ( v72 != *((_QWORD *)v35 + 6) )
          {
            if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
            {
              *(_QWORD *)&v98 = L"DirWalkerTask::WalkImmediateChildren";
              *((_QWORD *)&v98 + 1) = 0x400000828LL;
              v99 = L"DIRW";
              v42 = (struct FrsStatus *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v102);
              v43 = L"Skipping name:%ws (fid:%?) (moved to another directory)";
              v44 = (__int64 *)&v98;
LABEL_68:
              v69 = v42;
              dbgobj::DbgPrint<unsigned short,unsigned short const *,FileId>(v44, v43, &v69, &v70);
            }
            goto LABEL_69;
          }
          v49 = DirWalkerTask::LockGetParent(this, (const struct FileId *)&v72, (struct ID_RECORD *)v113);
          OneRecord = v49;
          if ( v49 )
          {
            if ( *((_DWORD *)v49 + 1) == 9049 )
            {
              v66 = 1;
            }
            else if ( *((_DWORD *)v49 + 1) == 2 )
            {
              v65 = 1;
            }
          }
          else
          {
            std::_Tree<std::_Tset_traits<FileId,std::less<FileId>,std::allocator<FileId>,0>>::insert<0,0>(
              v74,
              v95,
              &v72);
            if ( !v67 )
            {
LABEL_107:
              v34 = v73;
              OneRecord = (struct FrsStatus *)DirWalkerTask::CreateOneRecord(
                                                this,
                                                (__int64)v102,
                                                (__int64)&v78,
                                                (__int64)SystemTimeAsFileTime,
                                                v77,
                                                (__int64)v100);
              if ( !OneRecord )
                *v79 = 1;
              goto LABEL_96;
            }
          }
        }
      }
      if ( v32 )
        goto LABEL_93;
      goto LABEL_95;
    }
LABEL_70:
    if ( !(unsigned int)DirWalkerTask::NotToReplicate(
                          (_DWORD)this,
                          v81,
                          (unsigned int)v102,
                          (unsigned int)&v70,
                          (struct FileId *)&v72,
                          (__int64)v113,
                          HIDWORD(v104),
                          v86) )
      goto LABEL_49;
    if ( !v67 )
    {
      FidLockMan::UnlockEx((FidLockMan *)(*(_QWORD *)(*((_QWORD *)this + 56) + 8LL) + 8LL), *((struct Db **)this + 56));
      goto LABEL_69;
    }
    v34 = v73;
    v45 = *((_QWORD *)v73 + 1);
    v46 = ID_RECORD::ID_RECORD((ID_RECORD *)v96, (const struct ID_RECORD *)&v108);
    OneRecord = (struct FrsStatus *)DirWalkerTask::TombstoneFilteredContent(this, v46, v45);
    if ( !OneRecord )
    {
      v31 = v79;
      *v79 = 1;
      v32 = 0;
      goto LABEL_50;
    }
LABEL_96:
    v50 = (int)v69;
    if ( !OneRecord && (_DWORD)v69 && !(_DWORD)v76 )
    {
      v51 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v102);
      v52 = DirWalkerTask::NewMoveinWorkItem(
              (const struct DirWalkerTask::MoveinWorkItem *)((char *)v34 + 56),
              *((struct DirWalkerTask::Job **)v34 + 1),
              (const struct UID *)v100,
              (const struct FileId *)&v70,
              (const struct DirWalkerTask::MoveinWorkItem *)((char *)v34 + 56),
              v51,
              1,
              0,
              0);
      ScopedLock::ScopedLock((ScopedLock *)v91, (DirWalkerTask *)((char *)this + 344));
      v69 = v52;
      std::list<DirectoryHandle *>::push_front((char *)this + 312, &v69);
      ScopedLock::~ScopedLock((ScopedLock *)v91);
    }
    v53 = DirWalkerTask::CommitIfLong(this, OneRecord);
    OneRecord = v53;
    v69 = v53;
    if ( v53 )
    {
      if ( *((_DWORD *)v53 + 1) == 9014 )
      {
        std::_Tree<std::_Tset_traits<FileId,std::less<FileId>,std::allocator<FileId>,0>>::~_Tree<std::_Tset_traits<FileId,std::less<FileId>,std::allocator<FileId>,0>>(
          v74,
          v54);
        std::wstring::~wstring(v102);
        v9 = v65;
        v8 = v66;
        break;
      }
      if ( *((_DWORD *)v53 + 1) == 9099
        && g_DebugLog
        && LODWORD(g_DebugLog[1].LockSemaphore)
        && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        *(_QWORD *)&v98 = L"DirWalkerTask::WalkImmediateChildren";
        *((_QWORD *)&v98 + 1) = 0x400000889LL;
        v99 = L"DIRW";
        v76 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v102);
        dbgobj::DbgPrint<unsigned short,unsigned short const *,FileId>(
          &v98,
          L"Moving between a content set being deleted to an alive onename:%ws (fid:%?)",
          &v76,
          &v70);
        v55 = v65;
        v56 = v68;
      }
      else
      {
        v56 = v68;
        v55 = v65;
      }
      if ( (unsigned int)(*((_DWORD *)OneRecord + 1) - 2) > 1 && !v55 && !v56 )
      {
        v57 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v102);
        v98 = 0;
        v99 = 0;
        v60 = DirWalkerTask::NewMoveinWorkItem(
                (DirWalkerTask *)(v58 == 0),
                v59,
                (const struct UID *)&v98,
                (const struct FileId *)&v70,
                (const struct DirWalkerTask::MoveinWorkItem *)((char *)v34 + 56),
                v57,
                v50,
                v58 == 0,
                v58 != 0);
        v76 = (__int64)v60;
        std::list<IUpdateTask *>::push_back((char *)this + 328, &v76);
        ++*((_DWORD *)v60 + 18);
      }
      CLEAR_ERROR(&v69);
      OneRecord = v69;
    }
    v8 = v66;
    v9 = v65;
    if ( v66 || v65 || v68 )
    {
      std::_Tree<std::_Tset_traits<FileId,std::less<FileId>,std::allocator<FileId>,0>>::~_Tree<std::_Tset_traits<FileId,std::less<FileId>,std::allocator<FileId>,0>>(
        v74,
        v54);
      std::wstring::~wstring(v102);
      break;
    }
    std::_Tree<std::_Tset_traits<FileId,std::less<FileId>,std::allocator<FileId>,0>>::~_Tree<std::_Tset_traits<FileId,std::less<FileId>,std::allocator<FileId>,0>>(
      v74,
      v54);
LABEL_119:
    std::wstring::~wstring(v102);
    v13 = FIterator::Next((FIterator *)v83);
  }
  if ( !OneRecord )
  {
    if ( (!FIterator::AtEnd((FIterator *)v83) || v8 || v68) && !v9 )
      v14 = 0;
    *v82 = v14;
    goto LABEL_138;
  }
  *v82 = 0;
  if ( *((_DWORD *)OneRecord + 1) != 9014 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      *(_QWORD *)&v98 = L"DirWalkerTask::WalkImmediateChildren";
      *((_QWORD *)&v98 + 1) = 0x3000008C7LL;
      v99 = L"DIRW";
      dbgobj::DbgPrint<unsigned short,FrsStatus>(&v98, L"Error:%?", OneRecord);
    }
    CLEAR_ERROR(&v69);
    OneRecord = v69;
  }
  if ( OneRecord )
  {
    v64 = GetCurrentThreadId();
    v12 = FrsStatusList::PushNewError(
            v61,
            *((unsigned int *)OneRecord + 1),
            *((unsigned int *)OneRecord + 2),
            *(unsigned int *)OneRecord,
            "base\\fs\\remotefs\\frs\\src\\db\\dirwalker.cpp",
            "DirWalkerTask::WalkImmediateChildren",
            2252,
            v64,
            OneRecord);
    goto LABEL_137;
  }
LABEL_138:
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v81);
  FIterator::~FIterator((FIterator *)v83);
  return (struct FrsStatus *)v7;
}

```

## disassembly

```asm
0x14009be58  push    rbp
0x14009be5a  push    rbx
0x14009be5b  push    rsi
0x14009be5c  push    rdi
0x14009be5d  push    r12
0x14009be5f  push    r13
0x14009be61  push    r14
0x14009be63  push    r15
0x14009be65  lea     rbp, [rsp-0CC8h]
0x14009be6d  sub     rsp, 0DC8h
0x14009be74  mov     rax, cs:__security_cookie
0x14009be7b  xor     rax, rsp
0x14009be7e  mov     [rbp+0D00h+var_50], rax
0x14009be85  mov     [rbp+0D00h+var_D28], r9
0x14009be89  mov     rsi, r8
0x14009be8c  mov     [rbp+0D00h+var_D70], rdx
0x14009be90  mov     r15, rcx
0x14009be93  mov     rbx, [rbp+0D00h+arg_20]
0x14009be9a  mov     [rbp+0D00h+var_D40], rbx
0x14009be9e  lea     rcx, ??_7FIterator@@6B@; const FIterator::`vftable'
0x14009bea5  mov     [rbp+0D00h+var_D20], rcx
0x14009bea9  lea     rcx, [r15+230h]
0x14009beb0  mov     [rbp+0D00h+var_D18], rcx
0x14009beb4  xor     edi, edi
0x14009beb6  mov     [rbp+0D00h+var_D10], rdi
0x14009beba  mov     rax, [rdx+8]
0x14009bebe  add     rax, 50h ; 'P'
0x14009bec2  mov     [rbp+0D00h+var_D00], rax
0x14009bec6  mov     r13d, edi
0x14009bec9  mov     [rsp+0E00h+var_D9C], edi
0x14009becd  mov     r12d, edi
0x14009bed0  mov     [rsp+0E00h+var_DA0], edi
0x14009bed4  mov     dword ptr [rsp+0E00h+var_D98+4], edi
0x14009bed8  xor     edx, edx; Val
0x14009beda  mov     r8d, 88h; Size
0x14009bee0  lea     rcx, [rbp+0D00h+var_680]; void *
0x14009bee7  call    memset_0
0x14009beec  mov     [rbx], edi
0x14009beee  movups  xmm0, xmmword ptr cs:?ZeroedGuid@Guid@@2U_GUID@@B.Data1; _GUID const Guid::ZeroedGuid ...
0x14009bef5  movdqu  xmmword ptr [rbp+0D00h+var_680.Data1], xmm0
0x14009befd  mov     [rbp+0D00h+var_607], dil
0x14009bf04  mov     [rbp+0D00h+var_D30], rdi
0x14009bf08  lea     rdx, [rbp+0D00h+var_D30]
0x14009bf0c  mov     rcx, [r15+0B0h]
0x14009bf13  call    ?GetUsnConsumer@VolumeManager@@QEAAPEAVFrsStatus@@AEAV?$ScopedRef@VUsnConsumerInterface@@@@@Z; VolumeManager::GetUsnConsumer(ScopedRef<UsnConsumerInterface> &)
0x14009bf18  mov     rbx, rax
0x14009bf1b  test    rax, rax
0x14009bf1e  jz      short loc_14009BF4C
0x14009bf20  call    cs:__imp_GetCurrentThreadId
0x14009bf27  nop     dword ptr [rax+rax+00h]
0x14009bf2c  mov     [rsp+0E00h+var_DC0], rbx
0x14009bf31  mov     dword ptr [rsp+0E00h+var_DC8], eax
0x14009bf35  mov     dword ptr [rsp+0E00h+var_DD0], 70Bh
0x14009bf3d  mov     r9d, [rbx]
0x14009bf40  mov     r8d, [rbx+8]
0x14009bf44  mov     edx, [rbx+4]
0x14009bf47  jmp     loc_14009CC9C
0x14009bf4c  mov     rdx, rsi; struct FHandle *
0x14009bf4f  lea     rcx, [rbp+0D00h+var_D20]; this
0x14009bf53  call    ?OpenHandle@FIterator@@QEAAPEAVFrsStatus@@PEAVFHandle@@@Z; FIterator::OpenHandle(FHandle *)
0x14009bf58  mov     r14d, 1
0x14009bf5e  mov     rbx, rax
0x14009bf61  mov     [rsp+0E00h+var_D90], rax
0x14009bf66  mov     rsi, rax
0x14009bf69  lea     rcx, [rbp+0D00h+var_D20]; this
0x14009bf6d  call    ?AtEnd@FIterator@@QEBA_NXZ; FIterator::AtEnd(void)
0x14009bf72  test    al, al
0x14009bf74  jnz     loc_14009CBC4
0x14009bf7a  cmp     [r15+30h], edi
0x14009bf7e  jnz     loc_14009CBC4
0x14009bf84  test    rbx, rbx
0x14009bf87  jnz     loc_14009CBC4
0x14009bf8d  mov     rcx, [rbp+0D00h+var_D10]
0x14009bf91  mov     rax, [rcx]
0x14009bf94  mov     rax, [rax+20h]
0x14009bf98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009bf9d  mov     r13, rax
0x14009bfa0  mov     rcx, [rax+48h]
0x14009bfa4  mov     [rsp+0E00h+var_D88], rcx
0x14009bfa9  mov     [rbp+0D00h+var_D78], rdi
0x14009bfad  mov     dword ptr [rsp+0E00h+var_D90], r14d
0x14009bfb2  lea     r8, [rsp+0E00h+var_D90]; enum FidLockMan::Type *
0x14009bfb7  lea     rdx, [rsp+0E00h+var_D88]; struct FileId *
0x14009bfbc  mov     rcx, [r15+1C0h]; this
0x14009bfc3  call    ?TryLock@Db@@QEAAHAEBVFileId@@AEBW4Type@FidLockMan@@@Z; Db::TryLock(FileId const &,FidLockMan::Type const &)
0x14009bfc8  mov     ebx, eax
0x14009bfca  lea     rcx, [rbp+0D00h+var_5F0]; this
0x14009bfd1  call    ??0ID_RECORD@@QEAA@XZ; ID_RECORD::ID_RECORD(void)
0x14009bfd6  lea     rcx, [rbp+0D00h+var_320]; this
0x14009bfdd  call    ??0ID_RECORD@@QEAA@XZ; ID_RECORD::ID_RECORD(void)
0x14009bfe2  mov     dword ptr [rsp+0E00h+var_D98], edi
0x14009bfe6  mov     [rbp+0D00h+var_D48], rdi
0x14009bfea  mov     dword ptr [rbp+0D00h+var_6B0], edi
0x14009bff0  xorps   xmm0, xmm0
0x14009bff3  xor     eax, eax
0x14009bff5  movups  xmmword ptr [rbp+0D00h+var_6B0+4], xmm0
0x14009bffc  movups  [rbp+0D00h+var_69C], xmm0
0x14009c003  mov     [rbp+0D00h+var_68C], eax
0x14009c009  lea     rcx, [rbp+0D00h+var_6D0]
0x14009c010  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x14009c015  nop
0x14009c016  mov     eax, [r13+38h]
0x14009c01a  mov     ecx, eax
0x14009c01c  and     ecx, 10h
0x14009c01f  mov     dword ptr [rsp+0E00h+var_D90], ecx
0x14009c023  and     eax, 400h
0x14009c028  mov     dword ptr [rbp+0D00h+var_D58], eax
0x14009c02b  lea     rcx, [rbp+0D00h+var_D68]
0x14009c02f  call    ??0?$set@PEAVJob@DirWalkerTask@@U?$less@PEAVJob@DirWalkerTask@@@std@@V?$allocator@PEAVJob@DirWalkerTask@@@4@@std@@QEAA@XZ; std::set<DirWalkerTask::Job *>::set<DirWalkerTask::Job *>(void)
0x14009c034  nop
0x14009c035  mov     dword ptr [rbp+0D00h+var_D80], r14d
0x14009c039  mov     [rbp+0D00h+var_D50], edi
0x14009c03c  test    ebx, ebx
0x14009c03e  jnz     short loc_14009C08B
0x14009c040  call    cs:__imp_GetCurrentThreadId
0x14009c047  nop     dword ptr [rax+rax+00h]
0x14009c04c  mov     [rsp+0E00h+var_DC0], rdi
0x14009c051  mov     dword ptr [rsp+0E00h+var_DC8], eax
0x14009c055  mov     dword ptr [rsp+0E00h+var_DD0], 732h
0x14009c05d  lea     rax, aDirwalkertaskW; "DirWalkerTask::WalkImmediateChildren"
0x14009c064  mov     [rsp+0E00h+var_DD8], rax
0x14009c069  lea     rax, aBaseFsRemotefs_90; "base\\fs\\remotefs\\frs\\src\\db\\dirwa"...
0x14009c070  mov     qword ptr [rsp+0E00h+SystemTimeAsFileTime.dwLowDateTime], rax
0x14009c075  lea     r9d, [rsi+3]
0x14009c079  xor     r8d, r8d
0x14009c07c  mov     edx, 2359h
0x14009c081  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14009c086  mov     rsi, rax
0x14009c089  jmp     short loc_14009C09D
0x14009c08b  lea     r8, [rsp+0E00h+var_D88]
0x14009c090  lea     rdx, [rbp+0D00h+var_CD0]
0x14009c094  lea     rcx, [rbp+0D00h+var_D68]
0x14009c098  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@VFileId@@U?$less@VFileId@@@std@@V?$allocator@VFileId@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@VFileId@@@std@@@std@@@std@@_N@1@AEBVFileId@@@Z; std::_Tree<std::_Tset_traits<FileId,std::less<FileId>,std::allocator<FileId>,0>>::insert<0,0>(FileId const &)
0x14009c09d  test    rsi, rsi
0x14009c0a0  jnz     loc_14009C1F4
0x14009c0a6  lea     rcx, [r15+230h]
0x14009c0ad  mov     rax, [rcx]
0x14009c0b0  lea     rdx, [r15+0E0h]
0x14009c0b7  mov     [rsp+0E00h+var_DB8], rdi
0x14009c0bc  lea     r8, [rbp+0D00h+var_6B0]
0x14009c0c3  mov     [rsp+0E00h+var_DC0], r8
0x14009c0c8  mov     [rsp+0E00h+var_DC8], rdi
0x14009c0cd  mov     [rsp+0E00h+var_DD0], rdi
0x14009c0d2  lea     r8, [rbp+0D00h+var_6D0]
0x14009c0d9  mov     [rsp+0E00h+var_DD8], r8
0x14009c0de  lea     r8, [rbp+0D00h+var_D78]
0x14009c0e2  mov     qword ptr [rsp+0E00h+SystemTimeAsFileTime.dwLowDateTime], r8
0x14009c0e7  lea     r9, [rbp+0D00h+var_D48]
0x14009c0eb  lea     r8, [rsp+0E00h+var_D88]
0x14009c0f0  mov     rax, [rax+0D0h]
0x14009c0f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009c0fc  mov     rsi, rax
0x14009c0ff  mov     rbx, [rbp+0D00h+var_D70]
0x14009c103  test    rax, rax
0x14009c106  jnz     loc_14009C1F8
0x14009c10c  mov     rax, [rbx+30h]
0x14009c110  cmp     [rbp+0D00h+var_D78], rax
0x14009c114  setnz   al
0x14009c117  test    al, al
0x14009c119  jz      loc_14009C1A9
0x14009c11f  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14009c126  test    rax, rax
0x14009c129  jz      short loc_14009C195
0x14009c12b  cmp     [rax+40h], edi
0x14009c12e  jz      short loc_14009C195
0x14009c130  cmp     dword ptr [rax+38h], 4
0x14009c134  jl      short loc_14009C195
0x14009c136  lea     rax, aDirwalkertaskW_0; "DirWalkerTask::WalkImmediateChildren"
0x14009c13d  mov     [rbp+0D00h+var_6E8], rax
0x14009c144  mov     dword ptr [rbp+0D00h+var_6E8+8], 748h
0x14009c14e  mov     dword ptr [rbp+0D00h+var_6E8+0Ch], 4
0x14009c158  lea     rax, aDirw; "DIRW"
0x14009c15f  mov     [rbp+0D00h+var_6D8], rax
0x14009c166  lea     rcx, [rbp+0D00h+var_6D0]
0x14009c16d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14009c172  mov     [rsp+0E00h+var_D90], rax
0x14009c177  lea     r9, [rsp+0E00h+var_D88]
0x14009c17c  lea     r8, [rsp+0E00h+var_D90]
0x14009c181  lea     rdx, aSkippingNameWs_0; "Skipping name:%ws (fid:%?) (moved to an"...
0x14009c188  lea     rcx, [rbp+0D00h+var_6E8]
0x14009c18f  call    ??$DbgPrint@GPEBGVFileId@@@dbgobj@@QEAA_KPEBGAEBQEBGAEBVFileId@@@Z; dbgobj::DbgPrint<ushort,ushort const *,FileId>(ushort const *,ushort const * const &,FileId const &)
0x14009c194  nop
0x14009c195  lea     rcx, [rbp+0D00h+var_D68]
0x14009c199  call    ??1?$_Tree@V?$_Tset_traits@VFileId@@U?$less@VFileId@@@std@@V?$allocator@VFileId@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<FileId,std::less<FileId>,std::allocator<FileId>,0>>::~_Tree<std::_Tset_traits<FileId,std::less<FileId>,std::allocator<FileId>,0>>(void)
0x14009c19e  nop
0x14009c19f  mov     r13d, [rsp+0E00h+var_D9C]
0x14009c1a4  jmp     loc_14009CB72
0x14009c1a9  lea     r8, [rbp+0D00h+var_320]; struct ID_RECORD *
0x14009c1b0  lea     rdx, [rbp+0D00h+var_D78]; struct FileId *
0x14009c1b4  mov     rcx, r15; this
0x14009c1b7  call    ?LockGetParent@DirWalkerTask@@AEAAPEAVFrsStatus@@AEBVFileId@@AEAVID_RECORD@@@Z; DirWalkerTask::LockGetParent(FileId const &,ID_RECORD &)
0x14009c1bc  mov     rsi, rax
0x14009c1bf  test    rax, rax
0x14009c1c2  jz      short loc_14009C1E1
0x14009c1c4  cmp     dword ptr [rax+4], 2359h
0x14009c1cb  jnz     short loc_14009C1D4
0x14009c1cd  mov     [rsp+0E00h+var_D9C], r14d
0x14009c1d2  jmp     short loc_14009C1F8
0x14009c1d4  cmp     dword ptr [rax+4], 2
0x14009c1d8  jnz     short loc_14009C1F8
0x14009c1da  mov     [rsp+0E00h+var_DA0], r14d
0x14009c1df  jmp     short loc_14009C1F8
0x14009c1e1  lea     r8, [rbp+0D00h+var_D78]
0x14009c1e5  lea     rdx, [rbp+0D00h+var_CC0]
0x14009c1e9  lea     rcx, [rbp+0D00h+var_D68]
0x14009c1ed  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@VFileId@@U?$less@VFileId@@@std@@V?$allocator@VFileId@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@VFileId@@@std@@@std@@@std@@_N@1@AEBVFileId@@@Z; std::_Tree<std::_Tset_traits<FileId,std::less<FileId>,std::allocator<FileId>,0>>::insert<0,0>(FileId const &)
0x14009c1f2  jmp     short loc_14009C1F8
0x14009c1f4  mov     rbx, [rbp+0D00h+var_D70]
0x14009c1f8  mov     r12d, edi
0x14009c1fb  xorps   xmm0, xmm0
0x14009c1fe  movups  xmmword ptr [rbp+0D00h+var_6E8], xmm0
0x14009c205  mov     [rbp+0D00h+var_6D8], rdi
0x14009c20c  test    rsi, rsi
0x14009c20f  jnz     loc_14009C8B9
0x14009c215  mov     rcx, [r15+1C0h]
0x14009c21c  mov     rax, [rcx]
0x14009c21f  mov     [rbp+0D00h+var_D08], rdi
0x14009c223  lea     rdx, [rbp+0D00h+var_D08]
0x14009c227  mov     qword ptr [rsp+0E00h+SystemTimeAsFileTime.dwLowDateTime], rdx
0x14009c22c  lea     r9, [rbp+0D00h+var_5F0]
0x14009c233  lea     r8, [rsp+0E00h+var_D88]
0x14009c238  lea     rdx, [rsp+0E00h+var_D98]
0x14009c23d  mov     rax, [rax+28h]
0x14009c241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009c246  mov     rsi, rax
0x14009c249  test    rax, rax
0x14009c24c  jnz     loc_14009C317
0x14009c252  cmp     dword ptr [rsp+0E00h+var_D98], edi
0x14009c256  jz      loc_14009C317
0x14009c25c  mov     rax, [rbp+0D00h+var_5A8]
0x14009c263  sub     rax, qword ptr [rbp+0D00h+var_680.Data1]
0x14009c26a  jnz     short loc_14009C27A
0x14009c26c  mov     rax, [rbp+0D00h+var_5A0]
0x14009c273  sub     rax, qword ptr [rbp+0D00h+var_680.Data4]
0x14009c27a  test    rax, rax
0x14009c27d  jz      short loc_14009C2AF
0x14009c27f  mov     [rbp+0D00h+var_D38], edi
0x14009c282  mov     rcx, [r15+1C0h]
0x14009c289  mov     rax, [rcx]
0x14009c28c  lea     r9, [rbp+0D00h+var_680]
0x14009c293  lea     r8, [rbp+0D00h+var_5A8]
0x14009c29a  lea     rdx, [rbp+0D00h+var_D38]
0x14009c29e  mov     rax, [rax+50h]
0x14009c2a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009c2a7  mov     rsi, rax
0x14009c2aa  test    rax, rax
0x14009c2ad  jnz     short loc_14009C317
0x14009c2af  cmp     dword ptr [rsp+0E00h+var_D98], edi
0x14009c2b3  jz      short loc_14009C317
0x14009c2b5  cmp     [rbp+0D00h+var_607], dil
0x14009c2bc  jz      short loc_14009C317
0x14009c2be  mov     r12d, r14d
0x14009c2c1  mov     dword ptr [rsp+0E00h+var_D98], edi
0x14009c2c5  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14009c2cc  test    rax, rax
0x14009c2cf  jz      short loc_14009C317
0x14009c2d1  cmp     [rax+40h], edi
0x14009c2d4  jz      short loc_14009C317
0x14009c2d6  cmp     dword ptr [rax+38h], 4
0x14009c2da  jl      short loc_14009C317
0x14009c2dc  lea     rax, aDirwalkertaskW_0; "DirWalkerTask::WalkImmediateChildren"
0x14009c2e3  mov     [rbp+0D00h+var_CF8], rax
0x14009c2e7  mov     [rbp+0D00h+var_CF0], 78Bh
0x14009c2ee  mov     [rbp+0D00h+var_CEC], 4
0x14009c2f5  lea     rax, aDirw; "DIRW"
0x14009c2fc  mov     [rbp+0D00h+var_CE8], rax
0x14009c300  lea     r8, [rbp+0D00h+var_5F0]
0x14009c307  lea     rdx, aIdRecordInCont; "ID_RECORD in content set being deleted:"...
0x14009c30e  lea     rcx, [rbp+0D00h+var_CF8]
0x14009c312  call    ??$DbgPrint@GVID_RECORD@@@dbgobj@@QEAA_KPEBGAEBVID_RECORD@@@Z; dbgobj::DbgPrint<ushort,ID_RECORD>(ushort const *,ID_RECORD const &)
0x14009c317  test    rsi, rsi
0x14009c31a  jnz     loc_14009C8B9
0x14009c320  cmp     dword ptr [rsp+0E00h+var_D98], edi
0x14009c324  jz      short loc_14009C345
0x14009c326  movaps  xmm0, [rbp+0D00h+var_5F0]
0x14009c32d  movdqu  xmmword ptr [rbp+0D00h+var_6E8], xmm0
0x14009c335  mov     rax, [rbp+0D00h+var_5E0]
0x14009c33c  mov     [rbp+0D00h+var_6D8], rax
0x14009c343  jmp     short loc_14009C385
0x14009c345  cmp     dword ptr [rbp+0D00h+var_D58], edi
0x14009c348  jz      loc_14009C62F
0x14009c34e  cmp     dword ptr [r13+40h], 80000012h
0x14009c356  jnz     loc_14009C62F
0x14009c35c  mov     [rbp+0D00h+var_D50], r14d
0x14009c360  mov     rax, [rbx+8]
0x14009c364  mov     rcx, [rax+8]; this
0x14009c368  test    rcx, rcx
0x14009c36b  jz      loc_14009C56D
0x14009c371  call    ?IsPrimary@ContentSetManager@@QEAAHXZ; ContentSetManager::IsPrimary(void)
0x14009c376  test    eax, eax
0x14009c378  jnz     loc_14009C56D
0x14009c37e  mov     rax, [rbp+0D00h+var_5E0]
0x14009c385  cmp     dword ptr [rsp+0E00h+var_D98], edi
0x14009c389  jz      loc_14009C62F
0x14009c38f  cmp     rax, r14
0x14009c392  jnz     loc_14009C62F
0x14009c398  mov     rbx, [rbp+0D00h+var_D40]
0x14009c39c  mov     r13d, dword ptr [rbp+0D00h+var_D80]
0x14009c3a0  cmp     dword ptr [rsp+0E00h+var_D98], edi
0x14009c3a4  jz      loc_14009C4CE
  ... truncated ...
```
