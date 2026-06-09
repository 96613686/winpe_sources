# ContentSetManager::~ContentSetManager(void)

- ea: `0x14010944c`
- end: `0x14010971c`
- name: `??1ContentSetManager@@MEAA@XZ`
- size: `720`
- prototype: `void __fastcall(ContentSetManager *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, service_task, installer_update`

## callers

- `0x1401099b0`

## callees

- `0x14000daa0`
- `0x14000dd10`
- `0x14000ee94`
- `0x140022d1c`
- `0x14002c2bc`
- `0x14002c2f4`
- `0x14002c434`
- `0x14002c688`
- `0x140047e4c`
- `0x140068058`
- `0x1400727e8`
- `0x1400923f8`
- `0x140106618`
- `0x1401093d4`
- `0x14010944c`
- `0x1401097ec`
- `0x1401447d8`
- `0x140146e9c`
- `0x1401b4c3c`
- `0x1401b8920`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140109559`
- `KERNEL32!DeleteCriticalSection` at `0x140109584`
- `KERNEL32!DeleteCriticalSection` at `0x1401095af`
- `KERNEL32!DeleteCriticalSection` at `0x1401095ce`
- `KERNEL32!DeleteCriticalSection` at `0x1401095f9`
- `KERNEL32!DeleteCriticalSection` at `0x14010963c`
- `KERNEL32!DeleteCriticalSection` at `0x14010964f`
- `KERNEL32!DeleteCriticalSection` at `0x140109662`
- `KERNEL32!DeleteCriticalSection` at `0x140109559`
- `KERNEL32!DeleteCriticalSection` at `0x140109584`
- `KERNEL32!DeleteCriticalSection` at `0x1401095af`
- `KERNEL32!DeleteCriticalSection` at `0x1401095ce`
- `KERNEL32!DeleteCriticalSection` at `0x1401095f9`
- `KERNEL32!DeleteCriticalSection` at `0x14010963c`
- `KERNEL32!DeleteCriticalSection` at `0x14010964f`
- `KERNEL32!DeleteCriticalSection` at `0x140109662`

## string_xrefs

- `0x140109539`: `Content set manager deleted. csId:%? csName:%? rootPath:%? state:%? ptr:%p csInfoHistoryGuid:%?`

## pseudocode

```c
void __fastcall ContentSetManager::~ContentSetManager(ContentSetManager *this)
{
  char *v2; // rdi
  __int64 v3; // rax
  const unsigned __int16 *v4; // [rsp+40h] [rbp-20h] BYREF
  const wchar_t *v5; // [rsp+48h] [rbp-18h] BYREF
  int v6; // [rsp+50h] [rbp-10h]
  int v7; // [rsp+54h] [rbp-Ch]
  const wchar_t *v8; // [rsp+58h] [rbp-8h]
  int v9; // [rsp+80h] [rbp+20h] BYREF
  __int64 v10; // [rsp+88h] [rbp+28h] BYREF
  ContentSetManager *v11; // [rsp+90h] [rbp+30h] BYREF
  __int64 v12; // [rsp+98h] [rbp+38h] BYREF

  *(_QWORD *)this = &ContentSetManager::`vftable'{for `RefCountObject'};
  *((_QWORD *)this + 4) = &ContentSetManager::`vftable'{for `ShutdownObject'};
  v10 = 0;
  v2 = (char *)this + 1120;
  v3 = Config::ConfigInstance<Config::ContentSet>::Get((char *)this + 1120);
  ScopedRef<Config::ContentSet>::Set(&v10, v3);
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
  {
    v5 = L"ContentSetManager::~ContentSetManager";
    v6 = 4811;
    v7 = 5;
    v8 = L"CSMG";
    v11 = this;
    v9 = *((_DWORD *)this + 148);
    v12 = *(_QWORD *)(v10 + 616) + 18LL;
    v4 = Config::StringParam::Get((Config::StringParam *)(v10 + 240));
    dbgobj::DbgPrint<unsigned short,_GUID,unsigned short const *,unsigned short const *,enum CONTENT_SET_STATE,unsigned __int64,Guid>(
      (unsigned int)&v5,
      (unsigned int)L"Content set manager deleted. csId:%? csName:%? rootPath:%? state:%? ptr:%p csInfoHistoryGuid:%?",
      (_DWORD)this + 168,
      (unsigned int)&v4,
      (__int64)&v12,
      (__int64)&v9,
      (__int64)&v11,
      (__int64)this + 712);
  }
  ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v10);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1896));
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>((char *)this + 1880);
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>((char *)this + 1872);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1816));
  DbManagerInstance::FinalizeDbManagerInstance((ContentSetManager *)((char *)this + 1792));
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>((char *)this + 1784);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1728));
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>((char *)this + 1720);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1664));
  std::_Tree<std::_Tmap_traits<_FILETIME,UpdateReference *,std::less<_FILETIME>,std::allocator<std::pair<_FILETIME const,UpdateReference *>>,1>>::~_Tree<std::_Tmap_traits<_FILETIME,UpdateReference *,std::less<_FILETIME>,std::allocator<std::pair<_FILETIME const,UpdateReference *>>,1>>((char *)this + 1648);
  FrsStringImpl<char,unsigned short>::ReleaseBody((char *)this + 1624);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1568));
  RefList<Task>::~RefList<Task>((char *)this + 1536);
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>((char *)this + 1504);
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>((char *)this + 1496);
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>((char *)this + 1488);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1432));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1376));
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 33);
  FrsStringImpl<char,unsigned short>::ReleaseBody((char *)this + 1312);
  FrsStringImpl<char,unsigned short>::ReleaseBody((char *)this + 1304);
  FHandle::~FHandle((ContentSetManager *)((char *)this + 1224));
  FHandle::~FHandle((ContentSetManager *)((char *)this + 1208));
  FHandle::~FHandle((ContentSetManager *)((char *)this + 1192));
  Config::ConfigInstance<Config::ReplicaSet>::~ConfigInstance<Config::ReplicaSet>(v2);
  CREWLock::~CREWLock((ContentSetManager *)((char *)this + 1008));
  RdcCache::~RdcCache((ContentSetManager *)((char *)this + 888));
  ContentSetInfo::~ContentSetInfo((ContentSetManager *)((char *)this + 696));
  InitialSyncManager::~InitialSyncManager((ContentSetManager *)((char *)this + 600));
  UpdateLock::~UpdateLock((ContentSetManager *)((char *)this + 264));
  VolumeId::~VolumeId((ContentSetManager *)((char *)this + 208));
  FrsStringImpl<char,unsigned short>::ReleaseBody((char *)this + 200);
  _InterlockedIncrement(&RefTrace_ContentSetManager::numDestructorCalls);
  Task::~Task(this);
}

```

## disassembly

```asm
0x14010944c  push    rbp
0x14010944e  push    rbx
0x14010944f  push    rdi
0x140109450  mov     rbp, rsp
0x140109453  sub     rsp, 60h
0x140109457  mov     rbx, rcx
0x14010945a  lea     rax, ??_7ContentSetManager@@6BRefCountObject@@@; const ContentSetManager::`vftable'{for `RefCountObject'}
0x140109461  mov     [rcx], rax
0x140109464  lea     rax, ??_7ContentSetManager@@6BShutdownObject@@@; const ContentSetManager::`vftable'{for `ShutdownObject'}
0x14010946b  mov     [rcx+20h], rax
0x14010946f  and     [rbp+arg_8], 0
0x140109474  lea     rdi, [rcx+460h]
0x14010947b  mov     rcx, rdi
0x14010947e  call    ?Get@?$ConfigInstance@VContentSet@Config@@@Config@@QEAAPEAVContentSet@2@XZ; Config::ConfigInstance<Config::ContentSet>::Get(void)
0x140109483  mov     rdx, rax
0x140109486  lea     rcx, [rbp+arg_8]
0x14010948a  call    ?Set@?$ScopedRef@VContentSet@Config@@@@AEAAXPEAVContentSet@Config@@@Z; ScopedRef<Config::ContentSet>::Set(Config::ContentSet *)
0x14010948f  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140109496  test    rax, rax
0x140109499  jz      loc_140109549
0x14010949f  cmp     dword ptr [rax+40h], 0
0x1401094a3  jz      loc_140109549
0x1401094a9  cmp     dword ptr [rax+38h], 5
0x1401094ad  jl      loc_140109549
0x1401094b3  lea     rax, aContentsetmana_12; "ContentSetManager::~ContentSetManager"
0x1401094ba  mov     [rbp+var_18], rax
0x1401094be  mov     [rbp+var_10], 12CBh
0x1401094c5  mov     [rbp+var_C], 5
0x1401094cc  lea     rax, aCsmg; "CSMG"
0x1401094d3  mov     [rbp+var_8], rax
0x1401094d7  mov     [rbp+arg_10], rbx
0x1401094db  mov     eax, [rbx+250h]
0x1401094e1  mov     [rbp+arg_0], eax
0x1401094e4  mov     rcx, [rbp+arg_8]
0x1401094e8  mov     rax, [rcx+268h]
0x1401094ef  add     rax, 12h
0x1401094f3  mov     [rbp+arg_18], rax
0x1401094f7  add     rcx, 0F0h; this
0x1401094fe  call    ?Get@StringParam@Config@@QEBAPEBGXZ; Config::StringParam::Get(void)
0x140109503  mov     [rbp+var_20], rax
0x140109507  lea     rax, [rbx+2C8h]
0x14010950e  lea     r8, [rbx+0A8h]
0x140109515  mov     [rsp+60h+var_28], rax
0x14010951a  lea     rax, [rbp+arg_10]
0x14010951e  mov     [rsp+60h+var_30], rax
0x140109523  lea     rax, [rbp+arg_0]
0x140109527  mov     [rsp+60h+var_38], rax
0x14010952c  lea     rax, [rbp+arg_18]
0x140109530  mov     [rsp+60h+var_40], rax
0x140109535  lea     r9, [rbp+var_20]
0x140109539  lea     rdx, aContentSetMana; "Content set manager deleted. csId:%? cs"...
0x140109540  lea     rcx, [rbp+var_18]
0x140109544  call    ??$DbgPrint@GU_GUID@@PEBGPEBGW4CONTENT_SET_STATE@@_KVGuid@@@dbgobj@@QEAA_KPEBGAEBU_GUID@@AEBQEBG2AEBW4CONTENT_SET_STATE@@AEB_KAEBVGuid@@@Z; dbgobj::DbgPrint<ushort,_GUID,ushort const *,ushort const *,CONTENT_SET_STATE,unsigned __int64,Guid>(ushort const *,_GUID const &,ushort const * const &,ushort const * const &,CONTENT_SET_STATE const &,unsigned __int64 const &,Guid const &)
0x140109549  lea     rcx, [rbp+arg_8]
0x14010954d  call    ??1?$ScopedRef@VReplicaSet@Config@@@@QEAA@XZ; ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(void)
0x140109552  lea     rcx, [rbx+768h]; lpCriticalSection
0x140109559  call    cs:__imp_DeleteCriticalSection
0x140109560  nop     dword ptr [rax+rax+00h]
0x140109565  lea     rcx, [rbx+758h]
0x14010956c  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x140109571  lea     rcx, [rbx+750h]
0x140109578  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x14010957d  lea     rcx, [rbx+718h]; lpCriticalSection
0x140109584  call    cs:__imp_DeleteCriticalSection
0x14010958b  nop     dword ptr [rax+rax+00h]
0x140109590  lea     rcx, [rbx+700h]; this
0x140109597  call    ?FinalizeDbManagerInstance@DbManagerInstance@@QEAAXXZ; DbManagerInstance::FinalizeDbManagerInstance(void)
0x14010959c  lea     rcx, [rbx+6F8h]
0x1401095a3  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x1401095a8  lea     rcx, [rbx+6C0h]; lpCriticalSection
0x1401095af  call    cs:__imp_DeleteCriticalSection
0x1401095b6  nop     dword ptr [rax+rax+00h]
0x1401095bb  lea     rcx, [rbx+6B8h]
0x1401095c2  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x1401095c7  lea     rcx, [rbx+680h]; lpCriticalSection
0x1401095ce  call    cs:__imp_DeleteCriticalSection
0x1401095d5  nop     dword ptr [rax+rax+00h]
0x1401095da  lea     rcx, [rbx+670h]
0x1401095e1  call    ??1?$_Tree@V?$_Tmap_traits@U_FILETIME@@PEAVUpdateReference@@U?$less@U_FILETIME@@@std@@V?$allocator@U?$pair@$$CBU_FILETIME@@PEAVUpdateReference@@@std@@@4@$00@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_FILETIME,UpdateReference *,std::less<_FILETIME>,std::allocator<std::pair<_FILETIME const,UpdateReference *>>,1>>::~_Tree<std::_Tmap_traits<_FILETIME,UpdateReference *,std::less<_FILETIME>,std::allocator<std::pair<_FILETIME const,UpdateReference *>>,1>>(void)
0x1401095e6  lea     rcx, [rbx+658h]
0x1401095ed  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1401095f2  lea     rcx, [rbx+620h]; lpCriticalSection
0x1401095f9  call    cs:__imp_DeleteCriticalSection
0x140109600  nop     dword ptr [rax+rax+00h]
0x140109605  lea     rcx, [rbx+600h]
0x14010960c  call    ??1?$RefList@VTask@@@@UEAA@XZ; RefList<Task>::~RefList<Task>(void)
0x140109611  lea     rcx, [rbx+5E0h]
0x140109618  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x14010961d  lea     rcx, [rbx+5D8h]
0x140109624  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x140109629  lea     rcx, [rbx+5D0h]
0x140109630  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x140109635  lea     rcx, [rbx+598h]; lpCriticalSection
0x14010963c  call    cs:__imp_DeleteCriticalSection
0x140109643  nop     dword ptr [rax+rax+00h]
0x140109648  lea     rcx, [rbx+560h]; lpCriticalSection
0x14010964f  call    cs:__imp_DeleteCriticalSection
0x140109656  nop     dword ptr [rax+rax+00h]
0x14010965b  lea     rcx, [rbx+528h]; lpCriticalSection
0x140109662  call    cs:__imp_DeleteCriticalSection
0x140109669  nop     dword ptr [rax+rax+00h]
0x14010966e  lea     rcx, [rbx+520h]
0x140109675  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x14010967a  lea     rcx, [rbx+518h]
0x140109681  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x140109686  lea     rcx, [rbx+4C8h]; this
0x14010968d  call    ??1FHandle@@UEAA@XZ; FHandle::~FHandle(void)
0x140109692  lea     rcx, [rbx+4B8h]; this
0x140109699  call    ??1FHandle@@UEAA@XZ; FHandle::~FHandle(void)
0x14010969e  lea     rcx, [rbx+4A8h]; this
0x1401096a5  call    ??1FHandle@@UEAA@XZ; FHandle::~FHandle(void)
0x1401096aa  mov     rcx, rdi
0x1401096ad  call    ??1?$ConfigInstance@VReplicaSet@Config@@@Config@@QEAA@XZ; Config::ConfigInstance<Config::ReplicaSet>::~ConfigInstance<Config::ReplicaSet>(void)
0x1401096b2  lea     rcx, [rbx+3F0h]; this
0x1401096b9  call    ??1CREWLock@@QEAA@XZ; CREWLock::~CREWLock(void)
0x1401096be  lea     rcx, [rbx+378h]; this
0x1401096c5  call    ??1RdcCache@@QEAA@XZ; RdcCache::~RdcCache(void)
0x1401096ca  lea     rcx, [rbx+2B8h]; this
0x1401096d1  call    ??1ContentSetInfo@@UEAA@XZ; ContentSetInfo::~ContentSetInfo(void)
0x1401096d6  lea     rcx, [rbx+258h]; this
0x1401096dd  call    ??1InitialSyncManager@@QEAA@XZ; InitialSyncManager::~InitialSyncManager(void)
0x1401096e2  lea     rcx, [rbx+108h]; this
0x1401096e9  call    ??1UpdateLock@@QEAA@XZ; UpdateLock::~UpdateLock(void)
0x1401096ee  lea     rcx, [rbx+0D0h]; this
0x1401096f5  call    ??1VolumeId@@QEAA@XZ; VolumeId::~VolumeId(void)
0x1401096fa  lea     rcx, [rbx+0C8h]
0x140109701  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x140109706  lock inc cs:?numDestructorCalls@RefTrace_ContentSetManager@@1JC; long volatile RefTrace_ContentSetManager::numDestructorCalls
0x14010970d  mov     rcx, rbx; this
0x140109710  add     rsp, 60h
0x140109714  pop     rdi
0x140109715  pop     rbx
0x140109716  pop     rbp
0x140109717  jmp     ??1Task@@UEAA@XZ; Task::~Task(void)
```
