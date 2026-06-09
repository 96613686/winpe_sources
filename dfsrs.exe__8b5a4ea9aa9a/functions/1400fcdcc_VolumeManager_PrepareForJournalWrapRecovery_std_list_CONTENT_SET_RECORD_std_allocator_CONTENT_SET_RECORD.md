# VolumeManager::PrepareForJournalWrapRecovery(std::list<CONTENT_SET_RECORD,std::allocator<CONTENT_SET_RECORD>> &)

- ea: `0x1400fcdcc`
- end: `0x1400fde24`
- name: `?PrepareForJournalWrapRecovery@VolumeManager@@QEAAPEAVFrsStatus@@AEAV?$list@UCONTENT_SET_RECORD@@V?$allocator@UCONTENT_SET_RECORD@@@std@@@std@@@Z`
- size: `4184`
- prototype: `__int64 __fastcall(VolumeManager *this)`
- caller_count: `1`
- callee_count: `42`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400940e4`

## callees

- `0x14000d980`
- `0x14000daa0`
- `0x14000dcc0`
- `0x140011408`
- `0x140022d1c`
- `0x140024964`
- `0x140024c84`
- `0x140024ebc`
- `0x140024ed4`
- `0x14002c2f4`
- `0x1400378fc`
- `0x140040cb8`
- `0x140047e14`
- `0x140047e4c`
- `0x140058128`
- `0x1400727e8`
- `0x140082280`
- `0x1400878b4`
- `0x140087b90`
- `0x1400927ec`
- `0x140092818`
- `0x140092900`
- `0x140092984`
- `0x140096fcc`
- `0x1400a6930`
- `0x1400f116c`
- `0x1400f1258`
- `0x1400f1628`
- `0x1400f1be8`
- `0x1400f3834`
- `0x1400f4584`
- `0x1400f45b4`
- `0x1400f8adc`
- `0x1400fcdcc`
- `0x140105b20`
- `0x14010ee98`
- `0x1401107b4`
- `0x140110b6c`
- `0x1401148bc`
- `0x1401163a4`
- `0x1401b617c`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1400fce6f`
- `KERNEL32!LeaveCriticalSection` at `0x1400fd68c`
- `KERNEL32!LeaveCriticalSection` at `0x1400fd7c2`
- `KERNEL32!LeaveCriticalSection` at `0x1400fdd86`
- `KERNEL32!LeaveCriticalSection` at `0x1400fce6f`
- `KERNEL32!LeaveCriticalSection` at `0x1400fd68c`
- `KERNEL32!LeaveCriticalSection` at `0x1400fd7c2`
- `KERNEL32!LeaveCriticalSection` at `0x1400fdd86`
- `KERNEL32!EnterCriticalSection` at `0x1400fd047`
- `KERNEL32!EnterCriticalSection` at `0x1400fd09d`
- `KERNEL32!EnterCriticalSection` at `0x1400fdd59`
- `KERNEL32!EnterCriticalSection` at `0x1400fd047`
- `KERNEL32!EnterCriticalSection` at `0x1400fd09d`
- `KERNEL32!EnterCriticalSection` at `0x1400fdd59`
- `KERNEL32!GetCurrentThreadId` at `0x1400fd0e8`
- `KERNEL32!GetCurrentThreadId` at `0x1400fd110`
- `KERNEL32!GetCurrentThreadId` at `0x1400fd148`
- `KERNEL32!GetCurrentThreadId` at `0x1400fd96a`
- `KERNEL32!GetCurrentThreadId` at `0x1400fd0e8`
- `KERNEL32!GetCurrentThreadId` at `0x1400fd110`
- `KERNEL32!GetCurrentThreadId` at `0x1400fd148`
- `KERNEL32!GetCurrentThreadId` at `0x1400fd96a`

## string_xrefs

- `0x1400fcef3`: `Preparing for journal wrap recovery. volId:%? volPath:%? volState:%?`
- `0x1400fd030`: `Entering initializeCS ContentSetManager before journal wrap recovery. csId:%? csName:%? rootPath:%? volId:%? volPath:%? volState:%?`
- `0x1400fd4c7`: `Content set not shut down for journal wrap recovery. csId:%? csName:%? rootPath:%? state:%? volId:%? volPath:%? volState:%?`
- `0x1400fd2fc`: `Content processed by journal wrap recovery. csId:%? csName:%? rootPath:%? state:%? volId:%? volPath:%? volState:%?`
- `0x1400fd7ab`: `Leave initialize CS ContentSetManager for journal wrap recovery. csId:%? csName:%? rootPath:%? volId:%? volPath:%? volState:%?`
- `0x1400fd5bf`: `Content set shut down for journal wrap recovery. csId:%? csName:%? rootPath:%? state:%? volId:%? volPath:%? volState:%?`
- `0x1400fdc09`: `Restarting content set shut down for journal wrap recovery since it has completed initial building. csId:%? csName:%? rootPath:%? state:%? volId:%? volPath:%? volState:%?`
- `0x1400fd916`: `Shutting down ContentSetManager for duration of journal wrap recovery. csId:%? csName:%? rootPath:%? volId:%? volPath:%? volState:%?`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall VolumeManager::PrepareForJournalWrapRecovery(VolumeManager *this, __int64 **a2)
{
  __int64 **v2; // r12
  __int64 v4; // rsi
  Config::Volume *v5; // r13
  unsigned int v6; // edi
  __int64 v7; // rbx
  __int64 v8; // r15
  __int64 v9; // rbx
  struct Config::ContentSet *ContentSet; // rax
  const wchar_t *v11; // rcx
  struct FrsStatus *ContentSetsNotBeingDeleted; // rdi
  __int64 v13; // rcx
  __int64 DirWalkerTask; // rax
  __int64 v15; // rcx
  __int64 v16; // rcx
  _QWORD *v17; // rax
  __int64 v18; // r8
  const struct _GUID *v19; // rbx
  struct Config::ContentSet *v20; // rax
  char *v21; // rdx
  __int64 Data4; // r8
  const wchar_t *v23; // rax
  const wchar_t *v24; // rax
  _QWORD *v25; // rax
  __int64 v26; // r8
  int v27; // r15d
  __int64 v28; // rbx
  struct Config::ContentSet *v29; // rax
  int v30; // edx
  int v31; // edx
  int v32; // edx
  int v33; // edx
  int v34; // edx
  int v35; // edx
  LPCRITICAL_SECTION v36; // rax
  char *v37; // rdx
  const wchar_t *v38; // rax
  const wchar_t *v39; // rax
  char *v40; // rdx
  const wchar_t *v41; // rax
  const wchar_t *v42; // rax
  unsigned int v43; // r12d
  __int64 v44; // rbx
  struct Config::ContentSet *v45; // rax
  const wchar_t *v46; // rcx
  unsigned int j; // r15d
  __int64 v48; // rbx
  struct Config::ContentSet *v49; // rax
  const wchar_t *v50; // rcx
  DWORD v51; // eax
  __int64 v52; // rcx
  _QWORD *v54; // rax
  __int64 v55; // r8
  int v56; // r15d
  __int64 v57; // r13
  struct Config::ContentSet *v58; // rax
  struct Config::ContentSet *v59; // rbx
  int v60; // edx
  int v61; // edx
  int v62; // edx
  int v63; // edx
  _QWORD *v64; // rax
  __int64 v65; // rdi
  char *v66; // rdx
  __int64 v67; // r8
  const wchar_t *v68; // rax
  const wchar_t *v69; // rax
  int v70; // eax
  char *v71; // rdx
  const wchar_t *v72; // rax
  const wchar_t *v73; // rax
  int v74; // edi
  __int64 **v75; // rbx
  ContentSetManagerMap *v76; // rdi
  _QWORD *v77; // rax
  __int64 v78; // r8
  const struct _GUID *v79; // rax
  DWORD v80; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+38h] [rbp-C8h]
  DWORD v82; // [rsp+38h] [rbp-C8h]
  __int64 i; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v84; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v85; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v86; // [rsp+68h] [rbp-98h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+70h] [rbp-90h] BYREF
  int v88; // [rsp+78h] [rbp-88h]
  const wchar_t *v89; // [rsp+80h] [rbp-80h] BYREF
  int v90; // [rsp+88h] [rbp-78h]
  int v91; // [rsp+8Ch] [rbp-74h]
  const wchar_t *v92; // [rsp+90h] [rbp-70h]
  const wchar_t *v93; // [rsp+98h] [rbp-68h] BYREF
  int v94; // [rsp+A0h] [rbp-60h]
  int v95; // [rsp+A4h] [rbp-5Ch]
  const wchar_t *v96; // [rsp+A8h] [rbp-58h]
  __int64 v97; // [rsp+B0h] [rbp-50h] BYREF
  Config::Volume *v98; // [rsp+B8h] [rbp-48h] BYREF
  DirWalkerTask *v99; // [rsp+C0h] [rbp-40h] BYREF
  char v100[8]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v101; // [rsp+D0h] [rbp-30h]
  __int64 v102; // [rsp+D8h] [rbp-28h]
  Config::Volume *v103; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v104[2]; // [rsp+F0h] [rbp-10h] BYREF
  ContentSetManagerMap *v105; // [rsp+100h] [rbp+0h]
  char v106[8]; // [rsp+108h] [rbp+8h] BYREF
  const wchar_t *v107; // [rsp+110h] [rbp+10h] BYREF
  int v108; // [rsp+118h] [rbp+18h]
  int v109; // [rsp+11Ch] [rbp+1Ch]
  const wchar_t *v110; // [rsp+120h] [rbp+20h]
  char v111[8]; // [rsp+128h] [rbp+28h] BYREF
  __int64 v112; // [rsp+130h] [rbp+30h]
  __int64 v113; // [rsp+138h] [rbp+38h]
  char v114[8]; // [rsp+148h] [rbp+48h] BYREF
  char v115[8]; // [rsp+150h] [rbp+50h] BYREF
  char v116[8]; // [rsp+158h] [rbp+58h] BYREF
  char v117[8]; // [rsp+160h] [rbp+60h] BYREF
  char v118[8]; // [rsp+168h] [rbp+68h] BYREF
  char v119[8]; // [rsp+170h] [rbp+70h] BYREF
  char v120[8]; // [rsp+178h] [rbp+78h] BYREF
  _BYTE v121[16]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v122[16]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v123[16]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v124[80]; // [rsp+1B0h] [rbp+B0h] BYREF
  struct ContentSetManager *v125; // [rsp+210h] [rbp+110h] BYREF
  __int64 **v126; // [rsp+218h] [rbp+118h]
  __int64 v127; // [rsp+220h] [rbp+120h] BYREF
  struct Config::ContentSet *v128; // [rsp+228h] [rbp+128h] BYREF

  v126 = a2;
  v2 = a2;
  ScopedCrewLock::ScopedCrewLock(v106, (char *)this + 1480);
  std::list<CONTENT_SET_RECORD>::list<CONTENT_SET_RECORD>(v104);
  RefList<ContentSetManager>::RefList<ContentSetManager>(v100);
  RefList<ContentSetManager>::RefList<ContentSetManager>(v111);
  v4 = 0;
  v103 = 0;
  v128 = 0;
  v99 = 0;
  ScopedLock::ScopedLock((ScopedLock *)&lpCriticalSection, (VolumeManager *)((char *)this + 592));
  v5 = (Config::Volume *)Config::ConfigInstance<Config::ContentSet>::Get((char *)this + 232);
  v98 = v5;
  v103 = v5;
  *((_DWORD *)this + 419) = 1;
  --v88;
  LeaveCriticalSection(lpCriticalSection);
  std::list<CONTENT_SET_RECORD>::clear(v2);
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v89 = L"VolumeManager::PrepareForJournalWrapRecovery";
    v90 = 3466;
    v91 = 4;
    v92 = L"VLMG";
    LODWORD(v125) = *((_DWORD *)this + 108);
    v86 = *((_QWORD *)this + 22) + 18LL;
    dbgobj::DbgPrint<unsigned short,_GUID,unsigned short const *,enum BaseVolumeManager::VOLUME_STATE>(
      (unsigned int)&v89,
      (unsigned int)L"Preparing for journal wrap recovery. volId:%? volPath:%? volState:%?",
      (_DWORD)this + 184,
      (unsigned int)&v86,
      (__int64)&v125);
  }
  v105 = (VolumeManager *)((char *)this + 648);
  ContentSetManagerMap::GetAll((char *)this + 648, v100);
  v6 = 0;
  v7 = v102;
  v8 = v101;
  if ( (unsigned int)((v102 - v101) >> 3) )
  {
    do
    {
      v9 = RefList<WorkPath>::GetAt(v100, v6);
      v86 = v9;
      ContentSet = Config::Volume::FindContentSet(v5, (const struct _GUID *)(v9 + 168), 0);
      ScopedRef<Config::ContentSet>::Set(&v128, ContentSet);
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v89 = L"VolumeManager::PrepareForJournalWrapRecovery";
        v90 = 3481;
        v91 = 4;
        v92 = L"VLMG";
        LODWORD(v125) = *((_DWORD *)this + 108);
        i = *((_QWORD *)this + 22) + 18LL;
        if ( v128 )
          v11 = (const wchar_t *)(*((_QWORD *)v128 + 77) + 18LL);
        else
          v11 = L"<Unknown>";
        v97 = (__int64)v11;
        v9 = v86;
        dbgobj::DbgPrint<unsigned short,_GUID,FrsStringImpl<unsigned short,char>,unsigned short const *,_GUID,unsigned short const *,enum BaseVolumeManager::VOLUME_STATE>(
          (unsigned int)&v89,
          (unsigned int)L"Entering initializeCS ContentSetManager before journal wrap recovery. csId:%? csName:%? rootPath"
                         ":%? volId:%? volPath:%? volState:%?",
          v86 + 168,
          v86 + 200,
          (__int64)&v97,
          (__int64)this + 184,
          (__int64)&i,
          (__int64)&v125);
      }
      EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 1376));
      ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v86);
      ++v6;
      v7 = v102;
      v8 = v101;
    }
    while ( v6 < (unsigned int)((v102 - v101) >> 3) );
    v2 = v126;
  }
  ContentSetsNotBeingDeleted = (struct FrsStatus *)DbUtil::GetContentSetsNotBeingDeleted(*((struct DbManager **)this + 73));
  v86 = (__int64)ContentSetsNotBeingDeleted;
  EnterCriticalSection(lpCriticalSection);
  ++v88;
  if ( ContentSetsNotBeingDeleted )
    goto LABEL_78;
  if ( *((_DWORD *)this + 108) == 1 )
    goto LABEL_25;
  if ( *((_DWORD *)this + 108) != 2 )
  {
    switch ( *((_DWORD *)this + 108) )
    {
      case 3:
        DirWalkerTask = VolumeManager::GetDirWalkerTask(this);
        goto LABEL_26;
      case 4:
      case 5:
        CurrentThreadId = GetCurrentThreadId();
        DirWalkerTask = FrsStatusList::PushNewError(
                          v15,
                          9451,
                          0,
                          3,
                          "base\\fs\\remotefs\\frs\\src\\sync\\volumemanager.cpp",
                          "VolumeManager::PrepareForJournalWrapRecovery",
                          3543,
                          CurrentThreadId,
                          0);
        goto LABEL_26;
      case 7:
        v80 = GetCurrentThreadId();
        DirWalkerTask = FrsStatusList::PushNewError(
                          v13,
                          9450,
                          0,
                          3,
                          "base\\fs\\remotefs\\frs\\src\\sync\\volumemanager.cpp",
                          "VolumeManager::PrepareForJournalWrapRecovery",
                          3532,
                          v80,
                          0);
        goto LABEL_26;
    }
LABEL_25:
    v82 = GetCurrentThreadId();
    DirWalkerTask = FrsStatusList::PushNewError(
                      v16,
                      50,
                      0,
                      1,
                      "base\\fs\\remotefs\\frs\\src\\sync\\volumemanager.cpp",
                      "VolumeManager::PrepareForJournalWrapRecovery",
                      3555,
                      v82,
                      0);
LABEL_26:
    ContentSetsNotBeingDeleted = (struct FrsStatus *)DirWalkerTask;
    v86 = DirWalkerTask;
    if ( DirWalkerTask )
      goto LABEL_77;
  }
  ScopedLock::ScopedLock((ScopedLock *)v121, (VolumeManager *)((char *)this + 1408));
  std::list<Filter::FilterToken>::clear((char *)this + 1464);
  for ( i = **v2; ; std::_List_iterator<std::_List_val<std::_List_simple_types<CreditManager::ICallback *>>>::operator++(&i) )
  {
    v17 = (_QWORD *)std::_Tree<std::_Tmap_traits<_GUID,std::set<_GUID>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::set<_GUID>>>,0>>::end(
                      v2,
                      v114);
    if ( v18 == *v17 )
      break;
    v19 = (const struct _GUID *)std::_List_iterator<std::_List_val<std::_List_simple_types<CONTENT_SET_RECORD>>>::operator->(&i);
    std::list<_GUID>::push_front((char *)this + 1464, v19);
    v20 = Config::Volume::FindContentSet(v5, v19, 0);
    ScopedRef<Config::ContentSet>::Set(&v128, v20);
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v89 = L"VolumeManager::PrepareForJournalWrapRecovery";
      v90 = 3577;
      v91 = 4;
      v92 = L"VLMG";
      LODWORD(v125) = *((_DWORD *)this + 108);
      v97 = *((_QWORD *)this + 22) + 18LL;
      v21 = (char *)this + 184;
      Data4 = (__int64)v19[2].Data4;
      if ( v128 )
        v23 = (const wchar_t *)(*((_QWORD *)v128 + 77) + 18LL);
      else
        v23 = L"<Unknown>";
      v84 = v23;
      if ( v128 )
        v24 = Config::StringParam::Get((struct Config::ContentSet *)((char *)v128 + 240));
      else
        v24 = L"<Unknown>";
      v85 = (__int64)v24;
      dbgobj::DbgPrint<unsigned short,_GUID,unsigned short const *,unsigned short const *,enum CONTENT_SET_STATE,_GUID,unsigned short const *,enum BaseVolumeManager::VOLUME_STATE>(
        (unsigned int)&v89,
        (unsigned int)L"Content processed by journal wrap recovery. csId:%? csName:%? rootPath:%? state:%? volId:%? volPat"
                       "h:%? volState:%?",
        (_DWORD)v19,
        (unsigned int)&v85,
        (__int64)&v84,
        Data4,
        (__int64)v21,
        (__int64)&v97,
        (__int64)&v125);
    }
  }
  ScopedLock::~ScopedLock((ScopedLock *)v121);
  ScopedLock::ScopedLock((ScopedLock *)v122, (VolumeManager *)((char *)this + 1336));
  std::list<Filter::FilterToken>::clear((char *)this + 1392);
  ScopedLock::~ScopedLock((ScopedLock *)v122);
  i = **v2;
  while ( 1 )
  {
    v25 = (_QWORD *)std::_Tree<std::_Tmap_traits<_GUID,std::set<_GUID>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::set<_GUID>>>,0>>::end(
                      v2,
                      v115);
    if ( v26 == *v25 )
      break;
    v27 = 0;
    v28 = std::_List_iterator<std::_List_val<std::_List_simple_types<CONTENT_SET_RECORD>>>::operator->(&i);
    v29 = Config::Volume::FindContentSet(v98, (const struct _GUID *)v28, 0);
    ScopedRef<Config::ContentSet>::Set(&v128, v29);
    v30 = *(_DWORD *)(v28 + 40);
    if ( v30 )
    {
      v31 = v30 - 1;
      if ( v31 )
      {
        v32 = v31 - 1;
        if ( v32 )
        {
          v33 = v32 - 1;
          if ( !v33 )
            goto LABEL_49;
          v34 = v33 - 1;
          if ( v34 )
          {
            v35 = v34 - 1;
            if ( v35 )
            {
              if ( v35 == 1 )
LABEL_49:
                v27 = 1;
LABEL_60:
              v36 = g_DebugLog;
              goto LABEL_61;
            }
          }
        }
      }
    }
    v36 = g_DebugLog;
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v93 = L"VolumeManager::PrepareForJournalWrapRecovery";
      v94 = 3618;
      v95 = 4;
      v96 = L"VLMG";
      LODWORD(v127) = *((_DWORD *)this + 108);
      v125 = (struct ContentSetManager *)(*((_QWORD *)this + 22) + 18LL);
      v37 = (char *)this + 184;
      if ( v128 )
        v38 = (const wchar_t *)(*((_QWORD *)v128 + 77) + 18LL);
      else
        v38 = L"<Unknown>";
      v85 = (__int64)v38;
      if ( v128 )
        v39 = Config::StringParam::Get((struct Config::ContentSet *)((char *)v128 + 240));
      else
        v39 = L"<Unknown>";
      v84 = v39;
      dbgobj::DbgPrint<unsigned short,_GUID,unsigned short const *,unsigned short const *,enum CONTENT_SET_STATE,_GUID,unsigned short const *,enum BaseVolumeManager::VOLUME_STATE>(
        (unsigned int)&v93,
        (unsigned int)L"Content set not shut down for journal wrap recovery. csId:%? csName:%? rootPath:%? state:%? volId:"
                       "%? volPath:%? volState:%?",
        v28,
        (unsigned int)&v84,
        (__int64)&v85,
        v28 + 40,
        (__int64)v37,
        (__int64)&v125,
        (__int64)&v127);
      goto LABEL_60;
    }
LABEL_61:
    if ( v27 )
    {
      if ( v36 && LODWORD(v36[1].LockSemaphore) && SLODWORD(v36[1].OwningThread) >= 4 )
      {
        v89 = L"VolumeManager::PrepareForJournalWrapRecovery";
        v90 = 3639;
        v91 = 4;
        v92 = L"VLMG";
        LODWORD(v125) = *((_DWORD *)this + 108);
        v85 = *((_QWORD *)this + 22) + 18LL;
        v40 = (char *)this + 184;
        if ( v128 )
          v41 = (const wchar_t *)(*((_QWORD *)v128 + 77) + 18LL);
        else
          v41 = L"<Unknown>";
        v84 = v41;
        if ( v128 )
          v42 = Config::StringParam::Get((struct Config::ContentSet *)((char *)v128 + 240));
        else
          v42 = L"<Unknown>";
        v97 = (__int64)v42;
        dbgobj::DbgPrint<unsigned short,_GUID,unsigned short const *,unsigned short const *,enum CONTENT_SET_STATE,_GUID,unsigned short const *,enum BaseVolumeManager::VOLUME_STATE>(
          (unsigned int)&v89,
          (unsigned int)L"Content set shut down for journal wrap recovery. csId:%? csName:%? rootPath:%? state:%? volId:%?"
                         " volPath:%? volState:%?",
          v28,
          (unsigned int)&v97,
          (__int64)&v84,
          v28 + 40,
          (__int64)v40,
          (__int64)&v85,
          (__int64)&v125);
      }
      ScopedLock::ScopedLock((ScopedLock *)v123, (VolumeManager *)((char *)this + 1336));
      std::list<_GUID>::push_front((char *)this + 1392, v28);
      ScopedLock::~ScopedLock((ScopedLock *)v123);
      v125 = 0;
      ContentSetManagerMap::Find((VolumeManager *)((char *)this + 648), (const struct _GUID *)v28, &v125);
      if ( v125 )
      {
        RefList<ContentSetManager>::Add(v111);
        ContentSetManagerMap::Delete((VolumeManager *)((char *)this + 648), (const struct _GUID *)v28);
        FilterMan::DeleteContentSetFilter(*((FilterMan **)this + 116), (const struct _GUID *)v28);
      }
      ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v125);
    }
    std::_List_iterator<std::_List_val<std::_List_simple_types<CreditManager::ICallback *>>>::operator++(&i);
    v2 = v126;
  }
  ContentSetsNotBeingDeleted = (struct FrsStatus *)v86;
  v5 = v98;
LABEL_77:
  v7 = v102;
  v8 = v101;
LABEL_78:
  --v88;
  LeaveCriticalSection(lpCriticalSection);
  v43 = 0;
  if ( (unsigned int)((v7 - v8) >> 3) )
  {
    do
    {
      v44 = RefList<WorkPath>::GetAt(v100, v43);
      v127 = v44;
      v45 = Config::Volume::FindContentSet(v5, (const struct _GUID *)(v44 + 168), 0);
      ScopedRef<Config::ContentSet>::Set(&v128, v45);
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v93 = L"VolumeManager::PrepareForJournalWrapRecovery";
        v94 = 3708;
        v95 = 4;
        v96 = L"VLMG";
        LODWORD(v125) = *((_DWORD *)this + 108);
        v85 = *((_QWORD *)this + 22) + 18LL;
        if ( v128 )
          v46 = (const wchar_t *)(*((_QWORD *)v128 + 77) + 18LL);
        else
          v46 = L"<Unknown>";
        v84 = v46;
        v44 = v127;
        dbgobj::DbgPrint<unsigned short,_GUID,FrsStringImpl<unsigned short,char>,unsigned short const *,_GUID,unsigned short const *,enum BaseVolumeManager::VOLUME_STATE>(
          (unsigned int)&v93,
          (unsigned int)L"Leave initialize CS ContentSetManager for journal wrap recovery. csId:%? csName:%? rootPath:%? v"
                         "olId:%? volPath:%? volState:%?",
          v127 + 168,
          v127 + 200,
          (__int64)&v84,
          (__int64)this + 184,
          (__int64)&v85,
          (__int64)&v125);
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(v44 + 1376));
      ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v127);
      ++v43;
    }
    while ( v43 < (unsigned int)((v102 - v101) >> 3) );
    ContentSetsNotBeingDeleted = (struct FrsStatus *)v86;
  }
  for ( j = 0; ; ++j )
  {
    if ( ContentSetsNotBeingDeleted )
      goto LABEL_99;
    if ( j >= (unsigned int)((v113 - v112) >> 3) )
      break;
    v48 = RefList<WorkPath>::GetAt(v111, j);
    v127 = v48;
    v49 = Config::Volume::FindContentSet(v5, (const struct _GUID *)(v48 + 168), 0);
    ScopedRef<Config::ContentSet>::Set(&v128, v49);
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v93 = L"VolumeManager::PrepareForJournalWrapRecovery";
      v94 = 3751;
      v95 = 4;
      v96 = L"VLMG";
      LODWORD(v125) = *((_DWORD *)this + 108);
      v85 = *((_QWORD *)this + 22) + 18LL;
      if ( v128 )
        v50 = (const wchar_t *)(*((_QWORD *)v128 + 77) + 18LL);
      else
        v50 = L"<Unknown>";
      v84 = v50;
      v48 = v127;
      dbgobj::DbgPrint<unsigned short,_GUID,FrsStringImpl<unsigned short,char>,unsigned short const *,_GUID,unsigned short const *,enum BaseVolumeManager::VOLUME_STATE>(
        (unsigned int)&v93,
        (unsigned int)L"Shutting down ContentSetManager for duration of journal wrap recovery. csId:%? csName:%? rootPath:"
                       "%? volId:%? volPath:%? volState:%?",
        v127 + 168,
        v127 + 200,
        (__int64)&v84,
        (__int64)this + 184,
        (__int64)&v85,
        (__int64)&v125);
    }
    Task::ShutDown((Task *)v48, (void *)0xFFFFFFFFFFFFFFFFLL);
    ContentSetManager::InternalFinalizeContentSetManager(v48, 2);
    ContentSetsNotBeingDeleted = DirWalkerTask::AbortJobs(v99, (const struct _GUID *)(v48 + 168));
    ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v127);
  }
  ContentSetsNotBeingDeleted = (struct FrsStatus *)DbUtil::GetContentSetsNotBeingDeleted(*((struct DbManager **)this + 73));
  if ( ContentSetsNotBeingDeleted )
  {
LABEL_99:
    v51 = GetCurrentThreadId();
    v4 = FrsStatusList::PushNewError(
           v52,
           *((unsigned int *)ContentSetsNotBeingDeleted + 1),
           *((unsigned int *)ContentSetsNotBeingDeleted + 2),
           *(unsigned int *)ContentSetsNotBeingDeleted,
           "base\\fs\\remotefs\\frs\\src\\sync\\volumemanager.cpp",
           "VolumeManager::PrepareForJournalWrapRecovery",
           3883,
           v51,
           ContentSetsNotBeingDeleted);
    goto LABEL_100;
  }
  i = *(_QWORD *)v104[0];
  while ( 2 )
  {
    v54 = (_QWORD *)std::_Tree<std::_Tmap_traits<_GUID,std::set<_GUID>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::set<_GUID>>>,0>>::end(
                      v104,
                      v116);
    if ( v55 != *v54 )
    {
      v56 = 0;
      v57 = std::_List_iterator<std::_List_val<std::_List_simple_types<CONTENT_SET_RECORD>>>::operator->(&i);
      v58 = Config::Volume::FindContentSet(v98, (const struct _GUID *)v57, 0);
      ScopedRef<Config::ContentSet>::Set(&v128, v58);
      v59 = v128;
      if ( !v128 )
        goto LABEL_127;
      v60 = *(_DWORD *)(v57 + 40);
      if ( v60 )
      {
        v61 = v60 - 1;
        if ( v61 )
        {
          v62 = v61 - 1;
          if ( v62 )
          {
            v63 = v62 - 1;
            if ( !v63 || (unsigned int)(v63 - 1) > 1 )
              goto LABEL_127;
          }
        }
      }
      v56 = 1;
      ScopedLock::ScopedLock((ScopedLock *)v124, (VolumeManager *)((char *)this + 1336));
      v64 = (_QWORD *)std::_Tree<std::_Tmap_traits<_GUID,std::set<_GUID>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::set<_GUID>>>,0>>::end(
                        (char *)this + 1392,
                        v117);
      v65 = *(_QWORD *)std::find<std::_List_const_iterator<std::_List_val<std::_List_simple_types<_GUID>>>,_GUID>(
                         v118,
                         **((_QWORD **)this + 174),
                         *v64,
                         v57);
      if ( *(_QWORD *)std::_Tree<std::_Tmap_traits<_GUID,std::set<_GUID>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::set<_GUID>>>,0>>::end(
                        (char *)this + 1392,
                        v119) == v65 )
      {
        v56 = 0;
      }
      else
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
        {
          v107 = L"VolumeManager::PrepareForJournalWrapRecovery";
          v108 = 3826;
          v109 = 4;
          v110 = L"VLMG";
          LODWORD(v125) = *((_DWORD *)this + 108);
          v127 = *((_QWORD *)this + 22) + 18LL;
          v66 = (char *)this + 184;
          v67 = v57 + 40;
          v59 = v128;
          if ( v128 )
            v68 = (const wchar_t *)(*((_QWORD *)v128 + 77) + 18LL);
          else
            v68 = L"<Unknown>";
          v85 = (__int64)v68;
          if ( v128 )
            v69 = Config::StringParam::Get((struct Config::ContentSet *)((char *)v128 + 240));
          else
            v69 = L"<Unknown>";
          v84 = v69;
          dbgobj::DbgPrint<unsigned short,_GUID,unsigned short const *,unsigned short const *,enum CONTENT_SET_STATE,_GUID,unsigned short const *,enum BaseVolumeManager::VOLUME_STATE>(
            (unsigned int)&v107,
            (unsigned int)L"Restarting content set shut down for journal wrap recovery since it has completed initial buil"
                           "ding. csId:%? csName:%? rootPath:%? state:%? volId:%? volPath:%? volState:%?",
            v57,
            (unsigned int)&v84,
            (__int64)&v85,
            v67,
            (__int64)v66,
            (__int64)&v127,
            (__int64)&v125);
        }
        std::list<std::pair<void *,Task * *>>::erase((char *)this + 1392, v120, v65);
      }
      ScopedLock::~ScopedLock((ScopedLock *)v124);
      if ( v56 )
      {
        if ( !(unsigned int)Config::BoolParam::Get((struct Config::ContentSet *)((char *)v59 + 1120))
          || (v70 = *((_DWORD *)v59 + 401), v59 = v128, !v70) )
        {
          v56 = 0;
        }
LABEL_127:
        if ( v56 )
        {
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
          {
            v93 = L"VolumeManager::PrepareForJournalWrapRecovery";
            v94 = 3851;
            v95 = 4;
            v96 = L"VLMG";
            LODWORD(v125) = *((_DWORD *)this + 108);
            v127 = *((_QWORD *)this + 22) + 18LL;
            v71 = (char *)this + 184;
            v59 = v128;
            if ( v128 )
              v72 = (const wchar_t *)(*((_QWORD *)v128 + 77) + 18LL);
            else
              v72 = L"<Unknown>";
            v85 = (__int64)v72;
            if ( v128 )
              v73 = Config::StringParam::Get((struct Config::ContentSet *)((char *)v128 + 240));
            else
              v73 = L"<Unknown>";
            v84 = v73;
            dbgobj::DbgPrint<unsigned short,_GUID,unsigned short const *,unsigned short const *,_GUID,unsigned short const *,enum BaseVolumeManager::VOLUME_STATE>(
              (unsigned int)&v93,
              (_DWORD)v71,
              v57,
              (unsigned int)&v84,
              (__int64)&v85,
              (__int64)v71,
              (__int64)&v127,
              (__int64)&v125);
          }
          EnterCriticalSection(lpCriticalSection);
          v74 = ++v88;
          VolumeManager::AddContentSet(this, v59);
          v88 = v74 - 1;
          LeaveCriticalSection(lpCriticalSection);
        }
      }
      std::_List_iterator<std::_List_val<std::_List_simple_types<CreditManager::ICallback *>>>::operator++(&i);
      continue;
    }
    break;
  }
  v75 = v126;
  i = **v126;
  v76 = v105;
  while ( 1 )
  {
    v77 = (_QWORD *)std::_Tree<std::_Tmap_traits<_GUID,std::set<_GUID>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::set<_GUID>>>,0>>::end(
                      v75,
                      &v98);
    if ( v78 == *v77 )
      break;
    v125 = 0;
    v79 = (const struct _GUID *)std::_List_iterator<std::_List_val<std::_List_simple_types<CONTENT_SET_RECORD>>>::operator->(&i);
    ContentSetManagerMap::Find(v76, v79, &v125);
    if ( v125 )
      ContentSetManager::JournalWrapRecoveryStarted(v125);
    ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v125);
    std::_List_iterator<std::_List_val<std::_List_simple_types<CreditManager::ICallback *>>>::operator++(&i);
  }
LABEL_100:
  ScopedLock::~ScopedLock((ScopedLock *)&lpCriticalSection);
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v99);
  ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v128);
  ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v103);
  RefList<ContentSetManager>::~RefList<ContentSetManager>(v111);
  RefList<ContentSetManager>::~RefList<ContentSetManager>(v100);
  std::list<CONTENT_SET_RECORD>::~list<CONTENT_SET_RECORD>(v104);
  ScopedCrewLock::~ScopedCrewLock((ScopedCrewLock *)v106);
  return v4;
}

```

## disassembly

```asm
0x1400fcdcc  mov     [rsp-8+arg_8], rdx
0x1400fcdd1  push    rbp
0x1400fcdd2  push    rbx
0x1400fcdd3  push    rsi
0x1400fcdd4  push    rdi
0x1400fcdd5  push    r12
0x1400fcdd7  push    r13
0x1400fcdd9  push    r14
0x1400fcddb  push    r15
0x1400fcddd  lea     rbp, [rsp-0C8h]
0x1400fcde5  sub     rsp, 1C8h
0x1400fcdec  mov     r12, rdx
0x1400fcdef  mov     r14, rcx
0x1400fcdf2  lea     rdx, [rcx+5C8h]
0x1400fcdf9  lea     rcx, [rbp+100h+var_F8]
0x1400fcdfd  call    ??0ScopedCrewLock@@QEAA@AEAVCREWLock@@UWrite@0@@Z; ScopedCrewLock::ScopedCrewLock(CREWLock &,ScopedCrewLock::Write)
0x1400fce02  nop
0x1400fce03  lea     rcx, [rbp+100h+var_110]
0x1400fce07  call    ??0?$list@UCONTENT_SET_RECORD@@V?$allocator@UCONTENT_SET_RECORD@@@std@@@std@@QEAA@XZ; std::list<CONTENT_SET_RECORD>::list<CONTENT_SET_RECORD>(void)
0x1400fce0c  nop
0x1400fce0d  lea     rcx, [rbp+100h+var_138]
0x1400fce11  call    ??0?$RefList@VContentSetManager@@@@QEAA@XZ; RefList<ContentSetManager>::RefList<ContentSetManager>(void)
0x1400fce16  nop
0x1400fce17  lea     rcx, [rbp+100h+var_D8]
0x1400fce1b  call    ??0?$RefList@VContentSetManager@@@@QEAA@XZ; RefList<ContentSetManager>::RefList<ContentSetManager>(void)
0x1400fce20  nop
0x1400fce21  xor     esi, esi
0x1400fce23  mov     [rbp+100h+var_118], rsi
0x1400fce27  mov     [rbp+100h+arg_18], rsi
0x1400fce2e  mov     [rbp+100h+var_140], rsi
0x1400fce32  lea     rdx, [r14+250h]; struct ScopedCS *
0x1400fce39  lea     rcx, [rsp+200h+lpCriticalSection]; this
0x1400fce3e  call    ??0ScopedLock@@QEAA@AEAVScopedCS@@@Z; ScopedLock::ScopedLock(ScopedCS &)
0x1400fce43  nop
0x1400fce44  lea     rcx, [r14+0E8h]
0x1400fce4b  call    ?Get@?$ConfigInstance@VContentSet@Config@@@Config@@QEAAPEAVContentSet@2@XZ; Config::ConfigInstance<Config::ContentSet>::Get(void)
0x1400fce50  mov     r13, rax
0x1400fce53  mov     [rbp+100h+var_148], rax
0x1400fce57  mov     [rbp+100h+var_118], rax
0x1400fce5b  mov     dword ptr [r14+68Ch], 1
0x1400fce66  dec     [rsp+200h+var_188]
0x1400fce6a  mov     rcx, [rsp+200h+lpCriticalSection]; lpCriticalSection
0x1400fce6f  call    cs:__imp_LeaveCriticalSection
0x1400fce76  nop     dword ptr [rax+rax+00h]
0x1400fce7b  mov     rcx, r12
0x1400fce7e  call    ?clear@?$list@UCONTENT_SET_RECORD@@V?$allocator@UCONTENT_SET_RECORD@@@std@@@std@@QEAAXXZ; std::list<CONTENT_SET_RECORD>::clear(void)
0x1400fce83  lea     rcx, aVolumemanagerP_0; "VolumeManager::PrepareForJournalWrapRec"...
0x1400fce8a  lea     rdx, aVlmg; "VLMG"
0x1400fce91  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400fce98  test    rax, rax
0x1400fce9b  jz      short loc_1400FCF03
0x1400fce9d  cmp     [rax+40h], esi
0x1400fcea0  jz      short loc_1400FCF03
0x1400fcea2  cmp     dword ptr [rax+38h], 4
0x1400fcea6  jl      short loc_1400FCF03
0x1400fcea8  mov     [rbp+100h+var_180], rcx
0x1400fceac  mov     [rbp+100h+var_178], 0D8Ah
0x1400fceb3  mov     [rbp+100h+var_174], 4
0x1400fceba  mov     [rbp+100h+var_170], rdx
0x1400fcebe  mov     eax, [r14+1B0h]
0x1400fcec5  mov     dword ptr [rbp+100h+arg_0], eax
0x1400fcecb  mov     rax, [r14+0B0h]
0x1400fced2  add     rax, 12h
0x1400fced6  mov     [rsp+200h+var_198], rax
0x1400fcedb  lea     r8, [r14+0B8h]
0x1400fcee2  lea     rax, [rbp+100h+arg_0]
0x1400fcee9  mov     [rsp+200h+var_1E0], rax
0x1400fceee  lea     r9, [rsp+200h+var_198]
0x1400fcef3  lea     rdx, aPreparingForJo; "Preparing for journal wrap recovery. vo"...
0x1400fcefa  lea     rcx, [rbp+100h+var_180]
0x1400fcefe  call    ??$DbgPrint@GU_GUID@@PEBGW4VOLUME_STATE@BaseVolumeManager@@@dbgobj@@QEAA_KPEBGAEBU_GUID@@AEBQEBGAEBW4VOLUME_STATE@BaseVolumeManager@@@Z; dbgobj::DbgPrint<ushort,_GUID,ushort const *,BaseVolumeManager::VOLUME_STATE>(ushort const *,_GUID const &,ushort const * const &,BaseVolumeManager::VOLUME_STATE const &)
0x1400fcf03  lea     rax, [r14+288h]
0x1400fcf0a  mov     [rbp+100h+var_100], rax
0x1400fcf0e  lea     rdx, [rbp+100h+var_138]
0x1400fcf12  mov     rcx, rax
0x1400fcf15  call    ?GetAll@ContentSetManagerMap@@QEAAXAEAV?$RefList@VContentSetManager@@@@@Z; ContentSetManagerMap::GetAll(RefList<ContentSetManager> &)
0x1400fcf1a  mov     edi, esi
0x1400fcf1c  mov     rbx, [rbp+100h+var_128]
0x1400fcf20  mov     rax, rbx
0x1400fcf23  mov     r15, [rbp+100h+var_130]
0x1400fcf27  sub     rax, r15
0x1400fcf2a  sar     rax, 3
0x1400fcf2e  test    eax, eax
0x1400fcf30  jz      loc_1400FD081
0x1400fcf36  lea     r12, aVolumemanagerP_0; "VolumeManager::PrepareForJournalWrapRec"...
0x1400fcf3d  mov     edx, edi
0x1400fcf3f  lea     rcx, [rbp+100h+var_138]
0x1400fcf43  call    ?GetAt@?$RefList@VWorkPath@@@@QEBAPEAVWorkPath@@K@Z; RefList<WorkPath>::GetAt(ulong)
0x1400fcf48  mov     rbx, rax
0x1400fcf4b  mov     [rsp+200h+var_198], rax
0x1400fcf50  lea     rdx, [rax+0A8h]; struct _GUID *
0x1400fcf57  xor     r8d, r8d; unsigned int
0x1400fcf5a  mov     rcx, r13; this
0x1400fcf5d  call    ?FindContentSet@Volume@Config@@QEBAPEAVContentSet@2@PEBU_GUID@@K@Z; Config::Volume::FindContentSet(_GUID const *,ulong)
0x1400fcf62  mov     rdx, rax
0x1400fcf65  lea     rcx, [rbp+100h+arg_18]
0x1400fcf6c  call    ?Set@?$ScopedRef@VContentSet@Config@@@@AEAAXPEAVContentSet@Config@@@Z; ScopedRef<Config::ContentSet>::Set(Config::ContentSet *)
0x1400fcf71  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400fcf78  test    rax, rax
0x1400fcf7b  jz      loc_1400FD040
0x1400fcf81  cmp     [rax+40h], esi
0x1400fcf84  jz      loc_1400FD040
0x1400fcf8a  cmp     dword ptr [rax+38h], 4
0x1400fcf8e  jl      loc_1400FD040
0x1400fcf94  mov     [rbp+100h+var_180], r12
0x1400fcf98  mov     [rbp+100h+var_178], 0D99h
0x1400fcf9f  mov     [rbp+100h+var_174], 4
0x1400fcfa6  lea     rax, aVlmg; "VLMG"
0x1400fcfad  mov     [rbp+100h+var_170], rax
0x1400fcfb1  mov     eax, [r14+1B0h]
0x1400fcfb8  mov     dword ptr [rbp+100h+arg_0], eax
0x1400fcfbe  mov     rax, [r14+0B0h]
0x1400fcfc5  add     rax, 12h
0x1400fcfc9  mov     [rsp+200h+var_1B0], rax
0x1400fcfce  lea     rdx, [r14+0B8h]
0x1400fcfd5  mov     rax, [rbp+100h+arg_18]
0x1400fcfdc  test    rax, rax
0x1400fcfdf  jz      short loc_1400FCFEE
0x1400fcfe1  mov     rcx, [rax+268h]
0x1400fcfe8  add     rcx, 12h
0x1400fcfec  jmp     short loc_1400FCFF5
0x1400fcfee  lea     rcx, aUnknown_3; "<Unknown>"
0x1400fcff5  mov     [rbp+100h+var_150], rcx
0x1400fcff9  mov     rbx, [rsp+200h+var_198]
0x1400fcffe  lea     r9, [rbx+0C8h]
0x1400fd005  lea     r8, [rbx+0A8h]
0x1400fd00c  lea     rax, [rbp+100h+arg_0]
0x1400fd013  mov     [rsp+200h+var_1C8], rax
0x1400fd018  lea     rax, [rsp+200h+var_1B0]
0x1400fd01d  mov     [rsp+200h+var_1D0], rax
0x1400fd022  mov     [rsp+200h+var_1D8], rdx
0x1400fd027  lea     rax, [rbp+100h+var_150]
0x1400fd02b  mov     [rsp+200h+var_1E0], rax
0x1400fd030  lea     rdx, aEnteringInitia_0; "Entering initializeCS ContentSetManager"...
0x1400fd037  lea     rcx, [rbp+100h+var_180]
0x1400fd03b  call    ??$DbgPrint@GU_GUID@@V?$FrsStringImpl@GD@@PEBGU1@PEBGW4VOLUME_STATE@BaseVolumeManager@@@dbgobj@@QEAA_KPEBGAEBU_GUID@@AEBV?$FrsStringImpl@GD@@AEBQEBG13AEBW4VOLUME_STATE@BaseVolumeManager@@@Z; dbgobj::DbgPrint<ushort,_GUID,FrsStringImpl<ushort,char>,ushort const *,_GUID,ushort const *,BaseVolumeManager::VOLUME_STATE>(ushort const *,_GUID const &,FrsStringImpl<ushort,char> const &,ushort const * const &,_GUID const &,ushort const * const &,BaseVolumeManager::VOLUME_STATE const &)
0x1400fd040  lea     rcx, [rbx+560h]; lpCriticalSection
0x1400fd047  call    cs:__imp_EnterCriticalSection
0x1400fd04e  nop     dword ptr [rax+rax+00h]
0x1400fd053  nop
0x1400fd054  lea     rcx, [rsp+200h+var_198]
0x1400fd059  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x1400fd05e  inc     edi
0x1400fd060  mov     rbx, [rbp+100h+var_128]
0x1400fd064  mov     rax, rbx
0x1400fd067  mov     r15, [rbp+100h+var_130]
0x1400fd06b  sub     rax, r15
0x1400fd06e  sar     rax, 3
0x1400fd072  cmp     edi, eax
0x1400fd074  jb      loc_1400FCF3D
0x1400fd07a  mov     r12, [rbp+100h+arg_8]
0x1400fd081  mov     rdx, r12
0x1400fd084  mov     rcx, [r14+248h]; struct DbManager *
0x1400fd08b  call    ?GetContentSetsNotBeingDeleted@DbUtil@@SAPEAVFrsStatus@@PEAVDbManager@@AEAV?$list@UCONTENT_SET_RECORD@@V?$allocator@UCONTENT_SET_RECORD@@@std@@@std@@@Z; DbUtil::GetContentSetsNotBeingDeleted(DbManager *,std::list<CONTENT_SET_RECORD> &)
0x1400fd090  mov     rdi, rax
0x1400fd093  mov     [rsp+200h+var_198], rax
0x1400fd098  mov     rcx, [rsp+200h+lpCriticalSection]; lpCriticalSection
0x1400fd09d  call    cs:__imp_EnterCriticalSection
0x1400fd0a4  nop     dword ptr [rax+rax+00h]
0x1400fd0a9  inc     [rsp+200h+var_188]
0x1400fd0ad  test    rdi, rdi
0x1400fd0b0  jnz     loc_1400FD683
0x1400fd0b6  mov     edx, [r14+1B0h]
0x1400fd0bd  sub     edx, 1
0x1400fd0c0  jz      loc_1400FD148
0x1400fd0c6  sub     edx, 1
0x1400fd0c9  jz      loc_1400FD1A0
0x1400fd0cf  sub     edx, 1
0x1400fd0d2  jz      short loc_1400FD13A
0x1400fd0d4  sub     edx, 1
0x1400fd0d7  jz      short loc_1400FD110
0x1400fd0d9  sub     edx, 1
0x1400fd0dc  jz      short loc_1400FD110
0x1400fd0de  sub     edx, 1
0x1400fd0e1  jz      short loc_1400FD148
0x1400fd0e3  cmp     edx, 1
0x1400fd0e6  jnz     short loc_1400FD148
0x1400fd0e8  call    cs:__imp_GetCurrentThreadId
0x1400fd0ef  nop     dword ptr [rax+rax+00h]
0x1400fd0f4  mov     [rsp+200h+var_1C0], rsi
0x1400fd0f9  mov     dword ptr [rsp+200h+var_1C8], eax
0x1400fd0fd  mov     dword ptr [rsp+200h+var_1D0], 0DCCh
0x1400fd105  lea     r9d, [rdi+3]
0x1400fd109  mov     edx, 24EAh
0x1400fd10e  jmp     short loc_1400FD16F
0x1400fd110  call    cs:__imp_GetCurrentThreadId
0x1400fd117  nop     dword ptr [rax+rax+00h]
0x1400fd11c  mov     [rsp+200h+var_1C0], rsi
0x1400fd121  mov     dword ptr [rsp+200h+var_1C8], eax
0x1400fd125  mov     dword ptr [rsp+200h+var_1D0], 0DD7h
0x1400fd12d  mov     r9d, 3
0x1400fd133  mov     edx, 24EBh
0x1400fd138  jmp     short loc_1400FD16F
0x1400fd13a  lea     rdx, [rbp+100h+var_140]
0x1400fd13e  mov     rcx, r14; this
0x1400fd141  call    ?GetDirWalkerTask@VolumeManager@@QEAAPEAVFrsStatus@@AEAV?$ScopedRef@VDirWalkerTask@@@@@Z; VolumeManager::GetDirWalkerTask(ScopedRef<DirWalkerTask> &)
0x1400fd146  jmp     short loc_1400FD18F
0x1400fd148  call    cs:__imp_GetCurrentThreadId
0x1400fd14f  nop     dword ptr [rax+rax+00h]
0x1400fd154  mov     [rsp+200h+var_1C0], rsi
0x1400fd159  mov     dword ptr [rsp+200h+var_1C8], eax
0x1400fd15d  mov     dword ptr [rsp+200h+var_1D0], 0DE3h
0x1400fd165  mov     r9d, 1
0x1400fd16b  lea     edx, [r9+31h]
0x1400fd16f  lea     rax, aVolumemanagerP; "VolumeManager::PrepareForJournalWrapRec"...
0x1400fd176  mov     [rsp+200h+var_1D8], rax
0x1400fd17b  lea     rax, aBaseFsRemotefs_105; "base\\fs\\remotefs\\frs\\src\\sync\\vol"...
0x1400fd182  mov     [rsp+200h+var_1E0], rax
0x1400fd187  xor     r8d, r8d
0x1400fd18a  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400fd18f  mov     rdi, rax
0x1400fd192  mov     [rsp+200h+var_198], rax
0x1400fd197  test    rax, rax
0x1400fd19a  jnz     loc_1400FD67B
0x1400fd1a0  lea     rdx, [r14+580h]; struct ScopedCS *
0x1400fd1a7  lea     rcx, [rbp+100h+var_80]; this
0x1400fd1ae  call    ??0ScopedLock@@QEAA@AEAVScopedCS@@@Z; ScopedLock::ScopedLock(ScopedCS &)
0x1400fd1b3  nop
0x1400fd1b4  lea     r15, [r14+5B8h]
0x1400fd1bb  mov     rcx, r15
0x1400fd1be  call    ?clear@?$list@UFilterToken@Filter@@V?$allocator@UFilterToken@Filter@@@std@@@std@@QEAAXXZ; std::list<Filter::FilterToken>::clear(void)
0x1400fd1c3  mov     r8, [r12]
0x1400fd1c7  mov     r8, [r8]
0x1400fd1ca  mov     [rsp+200h+var_1B0], r8
0x1400fd1cf  lea     rdx, [rbp+100h+var_B8]
0x1400fd1d3  mov     rcx, r12
0x1400fd1d6  call    ?end@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$set@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$set@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@@std@@@std@@@3@$0A@@std@@@std@@QEBA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$set@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@@std@@@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<_GUID,std::set<_GUID>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::set<_GUID>>>,0>>::end(void)
0x1400fd1db  cmp     r8, [rax]
0x1400fd1de  jz      loc_1400FD320
0x1400fd1e4  lea     rcx, [rsp+200h+var_1B0]
0x1400fd1e9  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@UCONTENT_SET_RECORD@@@std@@@std@@@std@@QEBAPEAUCONTENT_SET_RECORD@@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<CONTENT_SET_RECORD>>>::operator->(void)
0x1400fd1ee  mov     rbx, rax
0x1400fd1f1  mov     rdx, rax
0x1400fd1f4  mov     rcx, r15
0x1400fd1f7  call    ?push_front@?$list@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAAXAEBU_GUID@@@Z; std::list<_GUID>::push_front(_GUID const &)
0x1400fd1fc  xor     r8d, r8d; unsigned int
0x1400fd1ff  mov     rdx, rbx; struct _GUID *
0x1400fd202  mov     rcx, r13; this
0x1400fd205  call    ?FindContentSet@Volume@Config@@QEBAPEAVContentSet@2@PEBU_GUID@@K@Z; Config::Volume::FindContentSet(_GUID const *,ulong)
0x1400fd20a  mov     rdx, rax
0x1400fd20d  lea     rcx, [rbp+100h+arg_18]
0x1400fd214  call    ?Set@?$ScopedRef@VContentSet@Config@@@@AEAAXPEAVContentSet@Config@@@Z; ScopedRef<Config::ContentSet>::Set(Config::ContentSet *)
0x1400fd219  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400fd220  test    rcx, rcx
0x1400fd223  jz      loc_1400FD30C
0x1400fd229  cmp     [rcx+40h], esi
0x1400fd22c  jz      loc_1400FD30C
0x1400fd232  cmp     dword ptr [rcx+38h], 4
0x1400fd236  jl      loc_1400FD30C
0x1400fd23c  lea     rax, aVolumemanagerP_0; "VolumeManager::PrepareForJournalWrapRec"...
0x1400fd243  mov     [rbp+100h+var_180], rax
0x1400fd247  mov     [rbp+100h+var_178], 0DF9h
0x1400fd24e  mov     [rbp+100h+var_174], 4
0x1400fd255  lea     rax, aVlmg; "VLMG"
0x1400fd25c  mov     [rbp+100h+var_170], rax
0x1400fd260  mov     eax, [r14+1B0h]
0x1400fd267  mov     dword ptr [rbp+100h+arg_0], eax
0x1400fd26d  mov     rax, [r14+0B0h]
0x1400fd274  add     rax, 12h
0x1400fd278  mov     [rbp+100h+var_150], rax
0x1400fd27c  lea     rdx, [r14+0B8h]
0x1400fd283  lea     r8, [rbx+28h]
0x1400fd287  mov     rcx, [rbp+100h+arg_18]
0x1400fd28e  test    rcx, rcx
0x1400fd291  jz      short loc_1400FD2A0
0x1400fd293  mov     rax, [rcx+268h]
0x1400fd29a  add     rax, 12h
0x1400fd29e  jmp     short loc_1400FD2A7
0x1400fd2a0  lea     rax, aUnknown_3; "<Unknown>"
0x1400fd2a7  mov     [rsp+200h+var_1A8], rax
0x1400fd2ac  test    rcx, rcx
0x1400fd2af  jz      short loc_1400FD2BF
0x1400fd2b1  add     rcx, 0F0h; this
0x1400fd2b8  call    ?Get@StringParam@Config@@QEBAPEBGXZ; Config::StringParam::Get(void)
0x1400fd2bd  jmp     short loc_1400FD2C6
0x1400fd2bf  lea     rax, aUnknown_3; "<Unknown>"
0x1400fd2c6  mov     [rsp+200h+var_1A0], rax
0x1400fd2cb  lea     rax, [rbp+100h+arg_0]
0x1400fd2d2  mov     [rsp+200h+var_1C0], rax
0x1400fd2d7  lea     rax, [rbp+100h+var_150]
0x1400fd2db  mov     [rsp+200h+var_1C8], rax
0x1400fd2e0  mov     [rsp+200h+var_1D0], rdx
0x1400fd2e5  mov     [rsp+200h+var_1D8], r8
0x1400fd2ea  lea     rax, [rsp+200h+var_1A8]
0x1400fd2ef  mov     [rsp+200h+var_1E0], rax
0x1400fd2f4  lea     r9, [rsp+200h+var_1A0]
0x1400fd2f9  mov     r8, rbx
0x1400fd2fc  lea     rdx, aContentProcess; "Content processed by journal wrap recov"...
0x1400fd303  lea     rcx, [rbp+100h+var_180]
0x1400fd307  call    ??$DbgPrint@GU_GUID@@PEBGPEBGW4CONTENT_SET_STATE@@U1@PEBGW4VOLUME_STATE@BaseVolumeManager@@@dbgobj@@QEAA_KPEBGAEBU_GUID@@AEBQEBG2AEBW4CONTENT_SET_STATE@@12AEBW4VOLUME_STATE@BaseVolumeManager@@@Z; dbgobj::DbgPrint<ushort,_GUID,ushort const *,ushort const *,CONTENT_SET_STATE,_GUID,ushort const *,BaseVolumeManager::VOLUME_STATE>(ushort const *,_GUID const &,ushort const * const &,ushort const * const &,CONTENT_SET_STATE const &,_GUID const &,ushort const * const &,BaseVolumeManager::VOLUME_STATE const &)
0x1400fd30c  lea     rcx, [rsp+200h+var_1B0]
0x1400fd311  call    ??E?$_List_iterator@V?$_List_val@U?$_List_simple_types@PEAVICallback@CreditManager@@@std@@@std@@@std@@QEAAAEAV01@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<CreditManager::ICallback *>>>::operator++(void)
0x1400fd316  mov     r8, [rsp+200h+var_1B0]
0x1400fd31b  jmp     loc_1400FD1CF
0x1400fd320  lea     rcx, [rbp+100h+var_80]; this
0x1400fd327  call    ??1ScopedLock@@QEAA@XZ; ScopedLock::~ScopedLock(void)
0x1400fd32c  lea     r13, [r14+538h]
0x1400fd333  mov     rdx, r13; struct ScopedCS *
0x1400fd336  lea     rcx, [rbp+100h+var_70]; this
0x1400fd33d  call    ??0ScopedLock@@QEAA@AEAVScopedCS@@@Z; ScopedLock::ScopedLock(ScopedCS &)
  ... truncated ...
```
