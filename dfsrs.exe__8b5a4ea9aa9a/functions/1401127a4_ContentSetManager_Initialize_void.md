# ContentSetManager::Initialize(void)

- ea: `0x1401127a4`
- end: `0x1401147cf`
- name: `?Initialize@ContentSetManager@@AEAAXXZ`
- size: `8235`
- prototype: `void __fastcall(ContentSetManager *__hidden this)`
- caller_count: `1`
- callee_count: `105`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140119450`

## callees

- `0x1400036a0`
- `0x1400036d0`
- `0x1400046cc`
- `0x14000c910`
- `0x14000cdc0`
- `0x14000d980`
- `0x14000daa0`
- `0x14000dcc0`
- `0x14000e34c`
- `0x14000ee94`
- `0x140010680`
- `0x14001cfa0`
- `0x140022ce4`
- `0x140022d1c`
- `0x140024868`
- `0x1400248ac`
- `0x1400248f4`
- `0x140024be4`
- `0x140028eec`
- `0x140028fcc`
- `0x14002c110`
- `0x14002c1c0`
- `0x14002c2f4`
- `0x14002c688`
- `0x140031984`
- `0x1400353fc`
- `0x1400370bc`
- `0x1400381dc`
- `0x14003f3a0`
- `0x14003fb40`
- `0x140041814`
- `0x140042d48`
- `0x14004567c`
- `0x140045a64`
- `0x140047e14`
- `0x140047e4c`
- `0x14006a550`
- `0x1400727e8`
- `0x14007f9f4`
- `0x140089c5c`
- `0x14009a000`
- `0x1400af320`
- `0x1400b3858`
- `0x1400b4844`
- `0x1400bf79c`
- `0x1400f8378`
- `0x1400f8adc`
- `0x1400fbda4`
- `0x1400fc960`
- `0x1400ff13c`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x1401128bd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1401141de`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1401128bd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1401141de`
- `KERNEL32!LeaveCriticalSection` at `0x1401142e5`
- `KERNEL32!LeaveCriticalSection` at `0x140114502`
- `KERNEL32!LeaveCriticalSection` at `0x1401146d8`
- `KERNEL32!LeaveCriticalSection` at `0x1401142e5`
- `KERNEL32!LeaveCriticalSection` at `0x140114502`
- `KERNEL32!LeaveCriticalSection` at `0x1401146d8`
- `KERNEL32!EnterCriticalSection` at `0x140114041`
- `KERNEL32!EnterCriticalSection` at `0x14011438a`
- `KERNEL32!EnterCriticalSection` at `0x140114521`
- `KERNEL32!EnterCriticalSection` at `0x140114041`
- `KERNEL32!EnterCriticalSection` at `0x14011438a`
- `KERNEL32!EnterCriticalSection` at `0x140114521`
- `KERNEL32!GetCurrentThreadId` at `0x140112b04`
- `KERNEL32!GetCurrentThreadId` at `0x140112dbf`
- `KERNEL32!GetCurrentThreadId` at `0x14011396c`
- `KERNEL32!GetCurrentThreadId` at `0x140112b04`
- `KERNEL32!GetCurrentThreadId` at `0x140112dbf`
- `KERNEL32!GetCurrentThreadId` at `0x14011396c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140113827`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140113a6e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140113827`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140113a6e`

## string_xrefs

- `0x140114090`: `Update contentInfoHistory`
- `0x1401143d9`: `Update contentInfoHistory`
- `0x14011457e`: `Update contentInfoHistory`
- `0x140114737`: `Failed to mark SysVol as ready, Err:%?`
- `0x1401129b3`: `Initializing. csId:%? csName:%? rootPath:%? state:%? ptr:%p csInfoHistoryGuid:%?`
- `0x140113560`: `DeletedFid`
- `0x140113dbe`: `Initialization pending. Waiting for VolumeManager to delete content set database records. csId:%? csName:%? rootPath:%? state:%? ptr:%p csInfoHistoryGuid:%? Error:%?`
- `0x140113405`: `Walk replica set to initialize or fix up database. csId:%? csName:%? rootPath:%? state:%? ptr:%p csInfoHistoryGuid:%?`
- `0x140113e9a`: `Failed to initialize ContentSetManager csId:%? csName:%? rootPath:%? state:%? ptr:%p csInfoHistoryGuid:%? Error:%?`

## pseudocode

```c
// Hidden C++ exception states: #wind=34
void __fastcall ContentSetManager::Initialize(ContentSetManager *this)
{
  __int64 v2; // rax
  TimeoutCounter *v3; // rcx
  _QWORD *v4; // r12
  __int64 v5; // rbx
  struct FrsStatus *RelativeVolumePathFromFileId; // r14
  __int64 DisplayPath; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  RefCountObject *v10; // rbx
  RefCountObject *v11; // rdx
  DWORD CurrentThreadId; // eax
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // r9
  VolumeManager *v16; // rcx
  __int64 v17; // r9
  ContentSetManager *v18; // rcx
  DWORD v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rax
  struct Db *v22; // rcx
  __int64 v23; // rbx
  FilePath *v24; // rax
  __int64 v25; // rdi
  __int64 v26; // rax
  _QWORD *v27; // r15
  void *v28; // rdi
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  RefCountObject *v32; // rbx
  RefCountObject *v33; // rdx
  int v34; // ebx
  __int64 *v35; // rcx
  __int64 v36; // rax
  struct ContentSetManager *v37; // rbx
  __int64 v38; // r8
  const wchar_t *v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // rbx
  __int64 v42; // rax
  __int64 DfsrResourceName; // rax
  __int64 v44; // rax
  __int64 v45; // rbx
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // r8
  int *v49; // rdx
  struct FrsStatus *updated; // rax
  int v51; // r8d
  __int64 v52; // r11
  struct FrsStatus *v53; // rbx
  DWORD v54; // eax
  __int64 v55; // rcx
  __int64 v56; // rbx
  __int64 v57; // rax
  __int64 v58; // rax
  __int64 v59; // rdx
  ConfigContext *v60; // rcx
  struct Config::Machine *Machine; // rdi
  Dword *v62; // rax
  unsigned int v63; // eax
  Dword *v64; // rax
  __int64 v65; // rdx
  ConfigContext *v66; // rbx
  struct MonitorContext *v67; // rbx
  int v68; // edx
  int v69; // ecx
  int v70; // edx
  struct MonitorContext *v71; // rcx
  int v72; // ecx
  int v73; // ecx
  int v74; // ecx
  int v75; // ecx
  struct MonitorContext *v76; // rbx
  int v77; // edx
  struct MonitorContext *v78; // rcx
  struct MonitorContext *v79; // rbx
  bool v80; // zf
  LPCRITICAL_SECTION v81; // rax
  int v82; // edx
  struct MonitorContext *v83; // rcx
  struct _GUID *v84; // rdx
  ConfigContext *v85; // rcx
  struct FrsStatus *v86; // r8
  unsigned int v87; // [rsp+30h] [rbp-D8h]
  void *v88; // [rsp+50h] [rbp-B8h]
  struct FrsStatus *v89; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v90; // [rsp+70h] [rbp-98h] BYREF
  __int64 v91; // [rsp+78h] [rbp-90h] BYREF
  struct Db *v92; // [rsp+80h] [rbp-88h] BYREF
  int v93; // [rsp+88h] [rbp-80h] BYREF
  int v94; // [rsp+8Ch] [rbp-7Ch] BYREF
  int v95; // [rsp+90h] [rbp-78h] BYREF
  struct _FILETIME v96; // [rsp+98h] [rbp-70h] BYREF
  int v97; // [rsp+A0h] [rbp-68h]
  int v98; // [rsp+A4h] [rbp-64h] BYREF
  int v99; // [rsp+A8h] [rbp-60h] BYREF
  const unsigned __int16 *v100; // [rsp+B0h] [rbp-58h] BYREF
  const unsigned __int16 *v101; // [rsp+B8h] [rbp-50h] BYREF
  int v102; // [rsp+C0h] [rbp-48h] BYREF
  ContentSetManager *v103; // [rsp+C8h] [rbp-40h] BYREF
  unsigned int v104; // [rsp+D0h] [rbp-38h] BYREF
  int v105; // [rsp+D4h] [rbp-34h]
  union _LARGE_INTEGER v106; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v107; // [rsp+E0h] [rbp-28h] BYREF
  __int64 v108; // [rsp+E8h] [rbp-20h] BYREF
  unsigned __int16 *v109; // [rsp+F0h] [rbp-18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+F8h] [rbp-10h] BYREF
  int v111; // [rsp+100h] [rbp-8h] BYREF
  int v112; // [rsp+104h] [rbp-4h] BYREF
  int v113; // [rsp+108h] [rbp+0h] BYREF
  int v114; // [rsp+10Ch] [rbp+4h] BYREF
  RefCountObject *v115; // [rsp+110h] [rbp+8h] BYREF
  __int64 v116; // [rsp+118h] [rbp+10h] BYREF
  RefCountObject *v117; // [rsp+120h] [rbp+18h] BYREF
  struct _FILETIME v118; // [rsp+128h] [rbp+20h] BYREF
  unsigned __int16 *v119; // [rsp+130h] [rbp+28h] BYREF
  DirWalkerTask *v120; // [rsp+138h] [rbp+30h] BYREF
  __int64 v121; // [rsp+140h] [rbp+38h] BYREF
  __int64 v122; // [rsp+148h] [rbp+40h] BYREF
  unsigned __int16 *v123; // [rsp+150h] [rbp+48h] BYREF
  __int64 v124; // [rsp+158h] [rbp+50h] BYREF
  __int64 v125; // [rsp+160h] [rbp+58h] BYREF
  int v126; // [rsp+168h] [rbp+60h] BYREF
  int v127; // [rsp+16Ch] [rbp+64h] BYREF
  int v128; // [rsp+170h] [rbp+68h] BYREF
  void **v129; // [rsp+178h] [rbp+70h] BYREF
  __int64 v130; // [rsp+180h] [rbp+78h] BYREF
  __int64 v131; // [rsp+188h] [rbp+80h] BYREF
  __int64 v132; // [rsp+190h] [rbp+88h] BYREF
  struct Config::Machine *v133; // [rsp+198h] [rbp+90h] BYREF
  ContentSetManager *v134; // [rsp+1A0h] [rbp+98h] BYREF
  ContentSetManager *v135; // [rsp+1A8h] [rbp+A0h] BYREF
  __int64 v136; // [rsp+1B0h] [rbp+A8h] BYREF
  __int64 v137; // [rsp+1B8h] [rbp+B0h] BYREF
  _BYTE v138[16]; // [rsp+1C0h] [rbp+B8h] BYREF
  _BYTE v139[8]; // [rsp+1D0h] [rbp+C8h] BYREF
  _BYTE v140[8]; // [rsp+1D8h] [rbp+D0h] BYREF
  _BYTE v141[8]; // [rsp+1E0h] [rbp+D8h] BYREF
  _BYTE v142[8]; // [rsp+1E8h] [rbp+E0h] BYREF
  _BYTE v143[8]; // [rsp+1F0h] [rbp+E8h] BYREF
  __int64 v144; // [rsp+1F8h] [rbp+F0h] BYREF
  union _LARGE_INTEGER v145; // [rsp+200h] [rbp+F8h] BYREF
  ContentSetManager *v146; // [rsp+208h] [rbp+100h] BYREF
  __int64 v147; // [rsp+210h] [rbp+108h] BYREF
  const unsigned __int16 *v148; // [rsp+218h] [rbp+110h] BYREF
  union _LARGE_INTEGER v149; // [rsp+220h] [rbp+118h] BYREF
  ContentSetManager *v150; // [rsp+228h] [rbp+120h] BYREF
  __int64 v151; // [rsp+230h] [rbp+128h] BYREF
  const unsigned __int16 *v152; // [rsp+238h] [rbp+130h] BYREF
  ContentSetManager *v153; // [rsp+240h] [rbp+138h] BYREF
  __int64 v154; // [rsp+248h] [rbp+140h] BYREF
  const unsigned __int16 *v155; // [rsp+250h] [rbp+148h] BYREF
  ContentSetManager *v156; // [rsp+258h] [rbp+150h] BYREF
  ContentSetManager *v157; // [rsp+260h] [rbp+158h] BYREF
  __int64 v158; // [rsp+268h] [rbp+160h] BYREF
  const unsigned __int16 *v159; // [rsp+270h] [rbp+168h] BYREF
  void *v160; // [rsp+278h] [rbp+170h]
  _BYTE v161[8]; // [rsp+280h] [rbp+178h] BYREF
  _BYTE v162[8]; // [rsp+288h] [rbp+180h] BYREF
  _BYTE v163[16]; // [rsp+290h] [rbp+188h] BYREF
  const wchar_t *v164; // [rsp+2A0h] [rbp+198h] BYREF
  int v165; // [rsp+2A8h] [rbp+1A0h]
  int v166; // [rsp+2ACh] [rbp+1A4h]
  const wchar_t *v167; // [rsp+2B0h] [rbp+1A8h]
  const wchar_t *v168; // [rsp+2B8h] [rbp+1B0h] BYREF
  int v169; // [rsp+2C0h] [rbp+1B8h]
  int v170; // [rsp+2C4h] [rbp+1BCh]
  const wchar_t *v171; // [rsp+2C8h] [rbp+1C0h]
  const wchar_t *v172; // [rsp+2D0h] [rbp+1C8h] BYREF
  int v173; // [rsp+2D8h] [rbp+1D0h]
  int v174; // [rsp+2DCh] [rbp+1D4h]
  const wchar_t *v175; // [rsp+2E0h] [rbp+1D8h]
  const wchar_t *v176; // [rsp+2E8h] [rbp+1E0h] BYREF
  int v177; // [rsp+2F0h] [rbp+1E8h]
  int v178; // [rsp+2F4h] [rbp+1ECh]
  const wchar_t *v179; // [rsp+2F8h] [rbp+1F0h]
  const wchar_t *v180; // [rsp+300h] [rbp+1F8h] BYREF
  int v181; // [rsp+308h] [rbp+200h]
  int v182; // [rsp+30Ch] [rbp+204h]
  const wchar_t *v183; // [rsp+310h] [rbp+208h]
  const wchar_t *v184; // [rsp+318h] [rbp+210h] BYREF
  int v185; // [rsp+320h] [rbp+218h]
  int v186; // [rsp+324h] [rbp+21Ch]
  const wchar_t *v187; // [rsp+328h] [rbp+220h]
  const wchar_t *v188; // [rsp+330h] [rbp+228h] BYREF
  int v189; // [rsp+338h] [rbp+230h]
  int v190; // [rsp+33Ch] [rbp+234h]
  const wchar_t *v191; // [rsp+340h] [rbp+238h]
  const wchar_t *v192; // [rsp+348h] [rbp+240h] BYREF
  int v193; // [rsp+350h] [rbp+248h]
  int v194; // [rsp+354h] [rbp+24Ch]
  const wchar_t *v195; // [rsp+358h] [rbp+250h]
  void **v196; // [rsp+360h] [rbp+258h] BYREF
  _BYTE v197[8]; // [rsp+368h] [rbp+260h] BYREF
  _BYTE v198[16]; // [rsp+370h] [rbp+268h] BYREF
  _BYTE v199[16]; // [rsp+380h] [rbp+278h] BYREF
  _BYTE v200[16]; // [rsp+390h] [rbp+288h] BYREF
  _BYTE v201[16]; // [rsp+3A0h] [rbp+298h] BYREF
  _BYTE v202[16]; // [rsp+3B0h] [rbp+2A8h] BYREF
  __int128 v203; // [rsp+3C0h] [rbp+2B8h] BYREF
  const wchar_t *v204; // [rsp+3D0h] [rbp+2C8h]
  __int128 v205; // [rsp+3E8h] [rbp+2E0h] BYREF
  __int64 v206; // [rsp+3F8h] [rbp+2F0h]
  __int128 v207; // [rsp+400h] [rbp+2F8h] BYREF
  _BYTE v208[40]; // [rsp+410h] [rbp+308h] BYREF
  _BYTE v209[16]; // [rsp+438h] [rbp+330h] BYREF
  __int64 v210; // [rsp+448h] [rbp+340h]
  _BYTE v211[48]; // [rsp+478h] [rbp+370h] BYREF
  _BYTE v212[48]; // [rsp+4A8h] [rbp+3A0h] BYREF
  _BYTE v213[156]; // [rsp+4D8h] [rbp+3D0h] BYREF
  unsigned __int16 v214[266]; // [rsp+574h] [rbp+46Ch] BYREF
  _BYTE v215[32]; // [rsp+788h] [rbp+680h] BYREF
  _BYTE v216[720]; // [rsp+7A8h] [rbp+6A0h] BYREF

  v97 = 0;
  ScopedLock::ScopedLock((ScopedLock *)v202, (ContentSetManager *)((char *)this + 1376));
  memset_0(v209, 0, 0x40u);
  v91 = 0;
  FilePath::FilePath((FilePath *)&v129);
  v92 = 0;
  ID_RECORD::ID_RECORD((ID_RECORD *)v213);
  LODWORD(v90) = 0;
  v205 = *(_OWORD *)((char *)this + 168);
  v206 = 1;
  v95 = 0;
  v203 = 0;
  v204 = 0;
  v106.QuadPart = 0;
  v108 = 0;
  v136 = 0;
  v118 = 0;
  SystemTimeAsFileTime = 0;
  v102 = 0;
  v98 = 0;
  v99 = 0;
  FHandle::FHandle((FHandle *)v138, (struct FileSystem *)ContentSetManager::fs);
  v105 = 0;
  v104 = 0;
  v2 = Config::ConfigInstance<Config::ContentSet>::Get((char *)this + 1120);
  ScopedRef<Config::ContentSet>::Set(&v91, v2);
  v149.QuadPart = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  TimeoutCounter::Sample(v3, (union _LARGE_INTEGER *)this + 161);
  v4 = (_QWORD *)((char *)this + 584);
  *((_QWORD *)this + 73) = 0;
  FrsStringImpl<unsigned short,char>::SetEmpty((char *)this + 1304);
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v164 = L"ContentSetManager::Initialize";
    v165 = 7667;
    v166 = 4;
    v167 = L"CSMG";
    v157 = this;
    v114 = *((_DWORD *)this + 148);
    v158 = *(_QWORD *)(v91 + 616) + 18LL;
    v159 = Config::StringParam::Get((Config::StringParam *)(v91 + 240));
    dbgobj::DbgPrint<unsigned short,_GUID,unsigned short const *,unsigned short const *,enum CONTENT_SET_STATE,unsigned __int64,Guid>(
      (unsigned int)&v164,
      (unsigned int)L"Initializing. csId:%? csName:%? rootPath:%? state:%? ptr:%p csInfoHistoryGuid:%?",
      (_DWORD)this + 168,
      (unsigned int)&v159,
      (__int64)&v158,
      (__int64)&v114,
      (__int64)&v157,
      (__int64)this + 712);
  }
  *((_QWORD *)this + 249) = 0;
  v5 = v91;
  FilePath::Set((FilePath *)&v129, (const unsigned __int16 *)(*(_QWORD *)(v91 + 616) + 18LL));
  FilePath::AppendTrailingBackslash((FilePath *)&v129);
  RelativeVolumePathFromFileId = ContentSetManager::HandleJournalWrapRecovery(this);
  v89 = RelativeVolumePathFromFileId;
  if ( RelativeVolumePathFromFileId )
    goto LABEL_20;
  v115 = 0;
  RefCountObject::AddRef(this);
  v134 = this;
  v89 = (struct FrsStatus *)operator new(0xB8u);
  DisplayPath = FilePath::GetDisplayPath(v5 + 704);
  v8 = FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(v161, DisplayPath);
  v97 = 1;
  v9 = ContentSetManager::DiskFull::DiskFull(v89, &v134, *((_QWORD *)this + 215) + 168LL, v8);
  ScopedRef<VolumeManager::ShutdownRestartTask>::Set(&v115, v9);
  v97 = 0;
  FrsStringImpl<char,unsigned short>::ReleaseBody(v161);
  ScopedLock::ScopedLock((ScopedLock *)v198, (ContentSetManager *)((char *)this + 1432));
  v10 = v115;
  if ( v115 )
  {
    RefCountObject::AddRef(v115);
    v11 = v10;
  }
  else
  {
    v11 = 0;
  }
  ScopedRef<VolumeManager::ShutdownRestartTask>::Set((char *)this + 1488, v11);
  ScopedLock::~ScopedLock((ScopedLock *)v198);
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v134);
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v115);
  if ( !(unsigned int)Config::BoolParam::Get((Config::BoolParam *)(v91 + 1120)) )
  {
    CurrentThreadId = GetCurrentThreadId();
    RelativeVolumePathFromFileId = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                         v13,
                                                         9052,
                                                         0,
                                                         3,
                                                         "base\\fs\\remotefs\\frs\\src\\sync\\contentsetmanager.cpp",
                                                         "ContentSetManager::Initialize",
                                                         7725,
                                                         CurrentThreadId,
                                                         0);
    v89 = RelativeVolumePathFromFileId;
    if ( RelativeVolumePathFromFileId )
      goto LABEL_20;
  }
  RelativeVolumePathFromFileId = ContentSetManager::CheckRootOverlap(this, &v99);
  v89 = RelativeVolumePathFromFileId;
  if ( RelativeVolumePathFromFileId )
    goto LABEL_20;
  RelativeVolumePathFromFileId = ContentSetManager::ExcludeFilesFromBackup(this);
  v89 = RelativeVolumePathFromFileId;
  if ( RelativeVolumePathFromFileId )
    goto LABEL_20;
  (*(void (__fastcall **)(_QWORD, struct Db **))(**((_QWORD **)this + 224) + 48LL))(*((_QWORD *)this + 224), &v92);
  RelativeVolumePathFromFileId = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, _QWORD))(*(_QWORD *)v92 + 16LL))(
                                                       v92,
                                                       0);
  v89 = RelativeVolumePathFromFileId;
  if ( RelativeVolumePathFromFileId )
    goto LABEL_20;
  RelativeVolumePathFromFileId = ContentSetManager::CheckContentSetState(
                                   this,
                                   v92,
                                   &v98,
                                   &v106,
                                   (struct FileId *)&v108,
                                   (struct FileId *)&v136,
                                   &v118,
                                   &v104,
                                   &v102);
  v89 = RelativeVolumePathFromFileId;
  if ( RelativeVolumePathFromFileId
    || (RelativeVolumePathFromFileId = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, int *, __int128 *, _BYTE *))(*(_QWORD *)v92 + 56LL))(
                                                             v92,
                                                             &v95,
                                                             &v205,
                                                             v213),
        (v89 = RelativeVolumePathFromFileId) != 0)
    || (RelativeVolumePathFromFileId = FHandle::OpenPath(
                                         (FHandle *)v138,
                                         (const unsigned __int16 *)(v130 + 18),
                                         0xA0u,
                                         3u,
                                         0x24u),
        (v89 = RelativeVolumePathFromFileId) != 0)
    || (RelativeVolumePathFromFileId = ContentSetManager::CheckContentRoot(
                                         this,
                                         (struct FHandle *)v138,
                                         (struct ID_RECORD *)v213,
                                         v92,
                                         &v95),
        (v89 = RelativeVolumePathFromFileId) != 0) )
  {
LABEL_20:
    if ( v102 )
    {
      v16 = (VolumeManager *)*((_QWORD *)this + 215);
      if ( *((_QWORD *)this + 123) )
      {
        v17 = *((unsigned int *)this + 148);
        v125 = *((_QWORD *)this + 123);
        VolumeManager::RemoveContentSetRootFromReadOnlyDriver(v16, &v125, (char *)this + 168, v17);
        RelativeVolumePathFromFileId = v89;
      }
      else
      {
        VolumeManager::MarkAndSweepReadOnlyContentSetsFromDriver(v16);
      }
    }
    if ( RelativeVolumePathFromFileId )
      goto LABEL_33;
  }
  else if ( v102 )
  {
    v14 = *((_QWORD *)this + 215);
    v15 = *((unsigned int *)this + 148);
    v124 = *((_QWORD *)this + 123);
    VolumeManager::RemoveContentSetRootFromReadOnlyDriver(v14, &v124, (char *)this + 168, v15);
  }
  RelativeVolumePathFromFileId = (struct FrsStatus *)VolumeIdTable::ExtractRelativeVolumePathFromFileId(
                                                       *((_QWORD *)this + 215) + 168LL,
                                                       (char *)this + 984,
                                                       (char *)this + 1624);
  v89 = RelativeVolumePathFromFileId;
  if ( RelativeVolumePathFromFileId )
    goto LABEL_33;
  if ( (unsigned int)ContentSetManager::IsGhosted(this) )
  {
    RelativeVolumePathFromFileId = ContentSetManager::AddContentSetRootToDriver(v18);
    v89 = RelativeVolumePathFromFileId;
    if ( RelativeVolumePathFromFileId )
      goto LABEL_33;
    v105 = 1;
  }
  if ( (unsigned int)ContentSetManager::IsSubordinate(this) )
  {
    if ( (unsigned int)Config::BoolParam::Get((Config::BoolParam *)(v91 + 1160))
      && (v19 = GetCurrentThreadId(),
          RelativeVolumePathFromFileId = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                               v20,
                                                               9075,
                                                               0,
                                                               3,
                                                               "base\\fs\\remotefs\\frs\\src\\sync\\contentsetmanager.cpp",
                                                               "ContentSetManager::Initialize",
                                                               7869,
                                                               v19,
                                                               0),
          (v89 = RelativeVolumePathFromFileId) != 0)
      || (RelativeVolumePathFromFileId = ContentSetManager::AddContentSetRootToReadOnlyDriver(this),
          (v89 = RelativeVolumePathFromFileId) != 0) )
    {
LABEL_33:
      if ( !*(_QWORD *)(*((_QWORD *)this + 163) + 8LL) )
      {
        v21 = FilePath::GetDisplayPath(&v130);
        FrsStringImpl<unsigned short,char>::Set((char *)this + 1304, v21);
      }
      goto LABEL_53;
    }
  }
  if ( v95 )
    goto LABEL_53;
  if ( !*((_DWORD *)this + 148) || *((_DWORD *)this + 148) == 2 || *((_DWORD *)this + 148) == 1 )
  {
    *((_DWORD *)this + 148) = 3;
  }
  else
  {
    if ( *((_DWORD *)this + 148) != 5 && *((_DWORD *)this + 148) != 4 )
      goto LABEL_45;
    *((_DWORD *)this + 148) = 6;
  }
  *v4 = 0;
LABEL_45:
  if ( *v4 )
  {
    RelativeVolumePathFromFileId = v89;
  }
  else
  {
    v116 = 0;
    RelativeVolumePathFromFileId = (struct FrsStatus *)VolumeManager::GetChangeJournal(*((VolumeManager **)this + 215));
    v89 = RelativeVolumePathFromFileId;
    if ( !RelativeVolumePathFromFileId )
    {
      RelativeVolumePathFromFileId = (struct FrsStatus *)(*(__int64 (__fastcall **)(__int64, __int64, __int64, _BYTE *))(*(_QWORD *)v116 + 40LL))(
                                                           v116,
                                                           *((_QWORD *)this + 215) + 168LL,
                                                           *((_QWORD *)this + 215) + 232LL,
                                                           v209);
      v89 = RelativeVolumePathFromFileId;
      *v4 = v210;
    }
    ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v116);
  }
  if ( !RelativeVolumePathFromFileId )
  {
    RelativeVolumePathFromFileId = (struct FrsStatus *)ContentSetManager::CreateRootRecord(
                                                         (__int64)this,
                                                         (FHandle *)v138,
                                                         v92,
                                                         &v205,
                                                         (__int64 *)this + 73,
                                                         *((_DWORD *)this + 148),
                                                         (_QWORD *)((unsigned __int64)&SystemTimeAsFileTime
                                                                  & -(__int64)(v98 != 0)),
                                                         v213);
    v89 = RelativeVolumePathFromFileId;
    if ( !RelativeVolumePathFromFileId )
      ContentSetManager::LogVersionVector(this);
  }
LABEL_53:
  v22 = v92;
  if ( v92 )
  {
    RelativeVolumePathFromFileId = DbUtil::CommitTransaction(v92, RelativeVolumePathFromFileId, 0);
    v89 = RelativeVolumePathFromFileId;
  }
  if ( RelativeVolumePathFromFileId )
    goto LABEL_155;
  if ( !*((_DWORD *)this + 148) && (unsigned int)Config::BoolParam::Get((Config::BoolParam *)(v91 + 1160)) )
    ContentSetManager::ClearPrimaryFlagFromAd(this);
  if ( *((_DWORD *)this + 500) )
  {
    RelativeVolumePathFromFileId = IsLocalSingleReadWriteDc((int *)this + 410);
    v89 = RelativeVolumePathFromFileId;
    if ( RelativeVolumePathFromFileId )
    {
LABEL_155:
      v34 = v90;
      goto LABEL_76;
    }
  }
  if ( !*((_DWORD *)this + 148) && *((_DWORD *)this + 500) )
    ContentSetManager::DeleteSysVolRegKeys(v22);
  SetCache<FileId>::Gc((char *)this + 888, *((_QWORD *)this + 112));
  SetCache<FileId>::Gc((char *)this + 928, *((_QWORD *)this + 117));
  std::list<FilePath>::clear((char *)this + 968);
  v23 = v91;
  v24 = FilePath::FilePath((FilePath *)&v196, (const unsigned __int16 *)(*(_QWORD *)(v91 + 832) + 18LL));
  std::list<FilePath>::push_back((char *)this + 968, v24);
  v196 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(v197);
  RelativeVolumePathFromFileId = ContentSetManager::CreateWorkingDirectories(
                                   this,
                                   (const unsigned __int16 *)(v130 + 18));
  v89 = RelativeVolumePathFromFileId;
  v25 = 0;
  if ( RelativeVolumePathFromFileId )
  {
    v34 = 0;
    goto LABEL_76;
  }
  ScopedLock::ScopedLock((ScopedLock *)v200, (ContentSetManager *)((char *)this + 1320));
  v89 = (struct FrsStatus *)operator new(0x588u);
  v26 = Staging::Staging(v89, (__int64)this + 1120);
  v27 = (_QWORD *)((char *)this + 1504);
  ScopedRef<VolumeManager::ShutdownRestartTask>::Set((char *)this + 1504, v26);
  RelativeVolumePathFromFileId = Staging::Initialize(
                                   *((Staging **)this + 188),
                                   (const struct _GUID *)((char *)this + 168),
                                   (const volatile int *)this + 12,
                                   *((_DWORD *)this + 325));
  v89 = RelativeVolumePathFromFileId;
  if ( RelativeVolumePathFromFileId )
  {
    FrsStringImpl<unsigned short,char>::Set((char *)this + 1304, *(_QWORD *)(v91 + 704) + 18LL);
  }
  else
  {
    *((_DWORD *)this + 325) = 0;
    if ( !(unsigned __int8)VolumeId::operator==(*v27 + 184LL, *((_QWORD *)this + 215) + 168LL) )
    {
      v117 = 0;
      RefCountObject::AddRef(this);
      v135 = this;
      v28 = operator new(0xB8u);
      v160 = v28;
      v29 = FilePath::GetDisplayPath(v23 + 704);
      v30 = FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(v162, v29);
      v97 = 2;
      v31 = ContentSetManager::DiskFull::DiskFull(v28, &v135, *v27 + 184LL, v30);
      ScopedRef<VolumeManager::ShutdownRestartTask>::Set(&v117, v31);
      v97 = 0;
      FrsStringImpl<char,unsigned short>::ReleaseBody(v162);
      ScopedLock::ScopedLock((ScopedLock *)v199, (ContentSetManager *)((char *)this + 1432));
      v32 = v117;
      if ( v117 )
      {
        RefCountObject::AddRef(v117);
        v33 = v32;
      }
      else
      {
        v33 = 0;
      }
      ScopedRef<VolumeManager::ShutdownRestartTask>::Set((char *)this + 1496, v33);
      ScopedLock::~ScopedLock((ScopedLock *)v199);
      ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v135);
      ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v117);
      v25 = 0;
    }
  }
  ScopedLock::~ScopedLock((ScopedLock *)v200);
  if ( RelativeVolumePathFromFileId )
    goto LABEL_75;
  RelativeVolumePathFromFileId = ContentSetManager::CheckStagingOverlap(this, &v99);
  v89 = RelativeVolumePathFromFileId;
  if ( RelativeVolumePathFromFileId )
  {
    if ( !*(_QWORD *)(*((_QWORD *)this + 163) + 8LL) )
      FrsStringImpl<unsigned short,char>::Set((char *)this + 1304, *(_QWORD *)(v91 + 704) + 18LL);
    goto LABEL_75;
  }
  RelativeVolumePathFromFileId = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, _QWORD))(*(_QWORD *)v92 + 16LL))(
                                                       v92,
                                                       0);
  v89 = RelativeVolumePathFromFileId;
  if ( RelativeVolumePathFromFileId )
  {
LABEL_75:
    v34 = v90;
    goto LABEL_76;
  }
  v38 = *((_QWORD *)this + 188);
  if ( *(_QWORD *)(v38 + 256) != v108
    || *(_QWORD *)(v38 + 216) != v106.QuadPart
    || !(unsigned __int8)operator==(v38 + 264, &v118) )
  {
    RelativeVolumePathFromFileId = ContentSetManager::SaveStageInfo(
                                     this,
                                     v92,
                                     (const union _LARGE_INTEGER *)(v38 + 216),
                                     (const struct FileId *)(v38 + 256),
                                     (const struct _FILETIME *)(v38 + 264));
    if ( RelativeVolumePathFromFileId )
    {
      v39 = (const wchar_t *)(*(_QWORD *)(v91 + 704) + 18LL);
LABEL_104:
      FrsStringImpl<unsigned short,char>::Set((char *)this + 1304, v39);
      goto LABEL_105;
    }
  }
  if ( v136 != *((_QWORD *)this + 157) )
  {
    RelativeVolumePathFromFileId = ContentSetManager::SaveDeletedFidInfo(this, v92);
    if ( RelativeVolumePathFromFileId )
    {
      v39 = L"DeletedFid";
      goto LABEL_104;
    }
  }
LABEL_105:
  RelativeVolumePathFromFileId = DbUtil::CommitTransaction(v92, RelativeVolumePathFromFileId, 0);
  v89 = RelativeVolumePathFromFileId;
  v40 = *((_QWORD *)this + 188);
  if ( *(_QWORD *)(v40 + 256) != v108 || *(_QWORD *)(v40 + 216) != v106.QuadPart )
    ContentSetManager::DeleteStageFolder(
      (const struct _GUID *)((char *)this + 168),
      &v106,
      (const struct FileId *)&v108,
      &v118);
  if ( RelativeVolumePathFromFileId )
    goto LABEL_75;
  if ( (unsigned int)Config::BoolParam::Get((Config::BoolParam *)(v91 + 1520)) )
  {
    v119 = &FrsStringImpl<unsigned short,char>::s_Empty;
    if ( !byte_140315A80 )
      _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
    v41 = v91;
    v42 = FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(v140, *(_QWORD *)(v91 + 616) + 18LL);
    DfsrResourceName = Cluster::ClusterUtil::MakeDfsrResourceName(v139, v42);
    FrsStringImpl<unsigned short,char>::Set(&v119, DfsrResourceName);
    FrsStringImpl<char,unsigned short>::ReleaseBody(v139);
    FrsStringImpl<char,unsigned short>::ReleaseBody(v140);
    v44 = FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(v141, *(_QWORD *)(v41 + 704) + 18LL);
    RelativeVolumePathFromFileId = (struct FrsStatus *)Cluster::ClusterUtil::UpdateDfsrResourceStagingPath(
                                                         (__int64)&v119,
                                                         v44);
    v89 = RelativeVolumePathFromFileId;
    FrsStringImpl<char,unsigned short>::ReleaseBody(v141);
    if ( RelativeVolumePathFromFileId )
      ContentSetManager::LogClusterResourceUpdateFailedEvent(this, &v91, RelativeVolumePathFromFileId);
    FrsStringImpl<char,unsigned short>::ReleaseBody(&v119);
    if ( RelativeVolumePathFromFileId )
      goto LABEL_75;
  }
  if ( (unsigned int)Config::BoolParam::Get((Config::BoolParam *)(v91 + 1520)) )
  {
    v109 = &FrsStringImpl<unsigned short,char>::s_Empty;
    if ( !byte_140315A80 )
      _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
    v45 = v91;
    v46 = FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(v143, *(_QWORD *)(v91 + 616) + 18LL);
    v47 = Cluster::ClusterUtil::MakeDfsrResourceName(v142, v46);
    FrsStringImpl<unsigned short,char>::Set(&v109, v47);
    FrsStringImpl<char,unsigned short>::ReleaseBody(v142);
    FrsStringImpl<char,unsigned short>::ReleaseBody(v143);
    if ( (unsigned int)Config::BoolParam::Get((Config::BoolParam *)(v45 + 1200)) )
    {
      v126 = 1;
      v48 = 1;
      v49 = &v126;
    }
    else
    {
      v127 = 1;
      v48 = 0;
      v49 = &v127;
    }
    updated = (struct FrsStatus *)Cluster::ClusterUtil::UpdateDfsrResourceContentSetFlagsBit(&v109, v49, v48);
    RelativeVolumePathFromFileId = updated;
    v89 = updated;
    if ( updated )
      ContentSetManager::LogClusterResourceUpdateFailedEvent(this, &v91, updated);
    FrsStringImpl<char,unsigned short>::ReleaseBody(&v109);
    if ( RelativeVolumePathFromFileId )
      goto LABEL_75;
  }
  RelativeVolumePathFromFileId = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, _QWORD))(*(_QWORD *)v92 + 16LL))(
                                                       v92,
                                                       0);
  v89 = RelativeVolumePathFromFileId;
  if ( RelativeVolumePathFromFileId )
    goto LABEL_75;
  if ( !(unsigned __int8)VolumeId::operator==(*((_QWORD *)this + 188) + 184LL, *((_QWORD *)this + 215) + 168LL) )
    goto LABEL_146;
  v144 = 0;
  v107 = *(_QWORD *)(v52 + 256);
  v131 = 0;
  std::wstring::wstring(v208);
  ID_RECORD::ID_RECORD((ID_RECORD *)v216);
  v132 = 0;
  if ( (unsigned int)_o__wcsicmp(*((_QWORD *)this + 203) + 18LL, L"\\") )
    goto LABEL_133;
  v137 = 0;
  FHandle::FHandle((FHandle *)v163, (struct FileSystem *)ContentSetManager::fs);
  RelativeVolumePathFromFileId = VolumeHandle::Open(
                                   (VolumeHandle *)&v137,
                                   (const struct VolumeId *)(*((_QWORD *)this + 215) + 168LL));
  v89 = RelativeVolumePathFromFileId;
  v53 = RelativeVolumePathFromFileId;
  if ( RelativeVolumePathFromFileId
    || (RelativeVolumePathFromFileId = FHandle::OpenRelative(
                                         (FHandle *)v163,
                                         (const struct VolumeId *)(*((_QWORD *)this + 215) + 168LL),
                                         (ContentSetManager *)((char *)this + 984),
                                         L"System Volume Information",
                                         0xA0u,
                                         v87),
        v89 = RelativeVolumePathFromFileId,
        (v53 = RelativeVolumePathFromFileId) != 0)
    || (RelativeVolumePathFromFileId = FHandle::GetFid((FHandle *)v163, (struct FileId *)&v132),
        v53 = RelativeVolumePathFromFileId,
        (v89 = RelativeVolumePathFromFileId) != 0) )
  {
    FrsStringImpl<unsigned short,char>::Set((char *)this + 1304, L"System Volume Information");
  }
  FHandle::~FHandle((FHandle *)v163);
  VolumeHandle::~VolumeHandle((VolumeHandle *)&v137);
  if ( !v53 )
  {
    v25 = 1;
LABEL_133:
    while ( 1 )
    {
      RelativeVolumePathFromFileId = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, int *, __int64 *, _BYTE *, __int64 *))(*(_QWORD *)v92 + 40LL))(
                                                           v92,
                                                           &v95,
                                                           &v107,
                                                           v216,
                                                           &v144);
      v89 = RelativeVolumePathFromFileId;
      if ( RelativeVolumePathFromFileId )
        break;
      if ( v95 && (v216[152] & 1) != 0 )
      {
        v54 = GetCurrentThreadId();
        RelativeVolumePathFromFileId = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                             v55,
                                                             9025,
                                                             0,
                                                             3,
                                                             "base\\fs\\remotefs\\frs\\src\\sync\\contentsetmanager.cpp",
                                                             "ContentSetManager::Initialize",
                                                             8227,
                                                             v54,
                                                             0);
        v89 = RelativeVolumePathFromFileId;
        if ( (unsigned int)EventThrottle::IsRipe((ContentSetManager *)((char *)this + 992), 0, 0) )
          Staging::LogEventStageInaccessible(*((Staging **)this + 188));
        if ( RelativeVolumePathFromFileId )
          break;
      }
      RelativeVolumePathFromFileId = (struct FrsStatus *)NtfsFileSystem::GetFileInfo(
                                                           ContentSetManager::fs,
                                                           *((_QWORD *)this + 215) + 168LL,
                                                           &v107,
                                                           0,
                                                           &v131,
                                                           v208,
                                                           0,
                                                           0,
                                                           0,
                                                           0);
      v89 = RelativeVolumePathFromFileId;
      if ( RelativeVolumePathFromFileId )
        break;
      v56 = v131;
      if ( v107 == v131 || v25 && v107 == v132 )
        break;
      v57 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v208);
      if ( !(unsigned int)_o__wcsicmp(v57, L"DfsrPrivate") )
        break;
      v107 = v56;
    }
  }
  std::wstring::~wstring(v208);
  if ( RelativeVolumePathFromFileId )
    goto LABEL_75;
LABEL_146:
  if ( !*(_DWORD *)(v91 + 1600) && *((_DWORD *)this + 148) != 3 && *((_DWORD *)this + 148) != 6 )
  {
    RelativeVolumePathFromFileId = v89;
    goto LABEL_75;
  }
  v34 = 1;
  if ( *((_DWORD *)this + 148) == 3 || *((_DWORD *)this + 148) == 6 )
  {
    RelativeVolumePathFromFileId = v89;
  }
  else
  {
    v145.QuadPart = 0;
    RelativeVolumePathFromFileId = ContentSetManager::InsertWalkerJob(
                                     v92,
                                     (const struct _GUID *)((char *)this + 168),
                                     v51,
                                     &v145);
    v89 = RelativeVolumePathFromFileId;
  }
LABEL_76:
  if ( v92 )
  {
    RelativeVolumePathFromFileId = DbUtil::CommitTransaction(v92, RelativeVolumePathFromFileId, 0);
    v89 = RelativeVolumePathFromFileId;
    (*(void (__fastcall **)(_QWORD, struct Db **))(**((_QWORD **)this + 224) + 64LL))(*((_QWORD *)this + 224), &v92);
  }
  if ( !RelativeVolumePathFromFileId )
  {
    v35 = (__int64 *)*((_QWORD *)this + 215);
    v36 = *v35;
    v207 = *(_OWORD *)((char *)this + 168);
    RelativeVolumePathFromFileId = (struct FrsStatus *)(*(__int64 (__fastcall **)(__int64 *, __int128 *))(v36 + 64))(
                                                         v35,
                                                         &v207);
    v89 = RelativeVolumePathFromFileId;
    if ( !RelativeVolumePathFromFileId )
    {
      if ( *((_DWORD *)this + 148) == 1 || *((_DWORD *)this + 148) == 4 )
        ContentSetManager::StartInitialSyncCleanup(this);
      if ( !v34 )
      {
        RelativeVolumePathFromFileId = v89;
        goto LABEL_170;
      }
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v168 = L"ContentSetManager::Initialize";
        v169 = 8309;
        v170 = 4;
        v171 = L"CSMG";
        v146 = this;
        LODWORD(v90) = *((_DWORD *)this + 148);
        v147 = *(_QWORD *)(v91 + 616) + 18LL;
        v148 = Config::StringParam::Get((Config::StringParam *)(v91 + 240));
        dbgobj::DbgPrint<unsigned short,_GUID,unsigned short const *,unsigned short const *,enum CONTENT_SET_STATE,unsigned __int64,Guid>(
          (unsigned int)&v168,
          (unsigned int)L"Walk replica set to initialize or fix up database. csId:%? csName:%? rootPath:%? state:%? ptr:%p"
                         " csInfoHistoryGuid:%?",
          (_DWORD)this + 168,
          (unsigned int)&v148,
          (__int64)&v147,
          (__int64)&v90,
          (__int64)&v146,
          (__int64)this + 712);
      }
      v96 = 0;
      v37 = 0;
      if ( *((_DWORD *)this + 148) == 3 || *((_DWORD *)this + 148) == 6 )
      {
        v37 = this;
        if ( v98 )
          goto LABEL_159;
        if ( (unsigned int)Config::BoolParam::Get((Config::BoolParam *)(v91 + 1160)) && *((_DWORD *)this + 148) != 6 )
        {
          v96 = (struct _FILETIME)2LL;
          goto LABEL_161;
        }
        if ( *((_DWORD *)this + 278) )
          goto LABEL_157;
        if ( *((_DWORD *)this + 410) )
LABEL_159:
          v96 = SystemTimeAsFileTime;
        else
          v96 = (struct _FILETIME)1LL;
LABEL_161:
        v120 = 0;
        RelativeVolumePathFromFileId = (struct FrsStatus *)VolumeManager::GetDirWalkerTask(*((VolumeManager **)this + 215));
        v89 = RelativeVolumePathFromFileId;
        if ( !RelativeVolumePathFromFileId )
        {
          DirWalkerTask::QueueMoveinJob(
            v120,
            (const struct _GUID *)((char *)this + 168),
            (const struct FileId *)v215,
            v214,
            &v149,
            (const struct UID *)v213,
            &v96,
            (ContentSetManager *)((char *)this + 584),
            0,
            v88,
            v37);
          if ( v98 )
          {
            ContentSetManager::LogEvent((char *)this + 168, 1073745930);
          }
          else
          {
            if ( *((_DWORD *)this + 148) == 6 )
              ContentSetManager::LogEvent((char *)this + 168, 2147487758LL);
            RelativeVolumePathFromFileId = v89;
          }
        }
        ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v120);
        if ( RelativeVolumePathFromFileId )
          goto LABEL_171;
LABEL_170:
        v121 = 0;
        RefCountObject::AddRef(this);
        ScopedRef<VolumeManager::ShutdownRestartTask>::Set(&v121, this);
        v160 = operator new(0x78u);
        v58 = ConflictManifest::ConflictManifest(v160, 1);
        ScopedRef<VolumeManager::ShutdownRestartTask>::Set((char *)this + 1872, v58);
        ConflictManifest::InitializeConflictManifest(*((_QWORD *)this + 234), &v121);
        ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v121);
        v122 = 0;
        RefCountObject::AddRef(this);
        ScopedRef<VolumeManager::ShutdownRestartTask>::Set(&v122, this);
        ReplicaSetManager::AddContentSetToReplicaSetManager(*((ReplicaSetManager **)this + 223));
        ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v122);
        goto LABEL_171;
      }
LABEL_157:
      v96 = (struct _FILETIME)3LL;
      goto LABEL_161;
    }
  }
LABEL_171:
  FHandle::Close((FHandle *)v138);
  if ( !RelativeVolumePathFromFileId )
  {
    FrsEvent::Reset(3221231876LL);
    *((_DWORD *)this + 250) = 0;
    if ( *((_DWORD *)this + 382) )
      *((_DWORD *)this + 382) = 0;
    else
      ContentSetManager::LogEvent((char *)this + 168, 1073745826);
    ScopedLock::ScopedLock((ScopedLock *)v201, (ContentSetManager *)((char *)this + 1320));
    if ( !*((_DWORD *)this + 408) )
      *((_DWORD *)this + 408) = 1;
    v72 = *((_DWORD *)this + 148);
    if ( v72 )
    {
      v73 = v72 - 1;
      if ( !v73 || (v74 = v73 - 1) == 0 || (v75 = v74 - 1) != 0 && (unsigned int)(v75 - 1) <= 1 )
      {
        v76 = g_MonitorContext;
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_MonitorContext + 704));
        *((_DWORD *)v76 + 174) = 1;
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
        {
          v188 = L"ContentSetManager::Initialize";
          v189 = 8576;
          v190 = 5;
          v191 = L"CSMG";
          dbgobj::DbgPrint<unsigned short>(&v188, L"Update contentInfoHistory");
        }
        *((_DWORD *)this + 192) = ((unsigned int)VolumeManager::IsContentSetProcessedByJournalWrapRecovery(
                                                   *((VolumeManager **)this + 215),
                                                   (const struct _GUID *)((char *)this + 168)) != 0)
                                + 2;
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
        {
          *(_QWORD *)&v203 = L"ContentSetManager::Initialize";
          *((_QWORD *)&v203 + 1) = 0x500002189LL;
          v204 = L"CSMG";
          v103 = this;
          v94 = *((_DWORD *)this + 148);
          v101 = (const unsigned __int16 *)(*(_QWORD *)(v91 + 616) + 18LL);
          v100 = Config::StringParam::Get((Config::StringParam *)(v91 + 240));
          v93 = *((_DWORD *)this + 192);
          dbgobj::DbgPrint<unsigned short,enum ContentSetInfo::CONTENT_SET_STATE,_GUID,unsigned short const *,unsigned short const *,enum CONTENT_SET_STATE,unsigned __int64,Guid>(
            (unsigned int)&v203,
            v77,
            (unsigned int)&v93,
            (_DWORD)this + 168,
            (__int64)&v100,
            (__int64)&v101,
            (__int64)&v94,
            (__int64)&v103,
            (__int64)this + 712);
        }
        StateHistory::Update(
          (struct MonitorContext *)((char *)g_MonitorContext + 640),
          (ContentSetManager *)((char *)this + 696));
        v78 = g_MonitorContext;
        *((_DWORD *)g_MonitorContext + 174) = 0;
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v78 + 704));
      }
LABEL_251:
      ScopedLock::~ScopedLock((ScopedLock *)v201);
      goto LABEL_252;
    }
    v79 = g_MonitorContext;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_MonitorContext + 704));
    *((_DWORD *)v79 + 174) = 1;
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      v192 = L"ContentSetManager::Initialize";
      v193 = 8535;
      v194 = 5;
      v195 = L"CSMG";
      dbgobj::DbgPrint<unsigned short>(&v192, L"Update contentInfoHistory");
    }
    v80 = (unsigned int)VolumeManager::IsContentSetProcessedByJournalWrapRecovery(
                          *((VolumeManager **)this + 215),
                          (const struct _GUID *)((char *)this + 168)) == 0;
    v81 = g_DebugLog;
    if ( v80 )
    {
      *((_DWORD *)this + 192) = 4;
      if ( v81 && LODWORD(v81[1].LockSemaphore) && SLODWORD(v81[1].OwningThread) >= 5 )
      {
        DWORD2(v203) = 8546;
        goto LABEL_243;
      }
    }
    else
    {
      *((_DWORD *)this + 192) = 3;
      if ( v81 && LODWORD(v81[1].LockSemaphore) && SLODWORD(v81[1].OwningThread) >= 5 )
      {
        DWORD2(v203) = 8539;
LABEL_243:
        v103 = this;
        v204 = L"CSMG";
        HIDWORD(v203) = 5;
        *(_QWORD *)&v203 = L"ContentSetManager::Initialize";
        v94 = *((_DWORD *)this + 148);
        v101 = (const unsigned __int16 *)(*(_QWORD *)(v91 + 616) + 18LL);
        v100 = Config::StringParam::Get((Config::StringParam *)(v91 + 240));
        v93 = *((_DWORD *)this + 192);
        dbgobj::DbgPrint<unsigned short,enum ContentSetInfo::CONTENT_SET_STATE,_GUID,unsigned short const *,unsigned short const *,enum CONTENT_SET_STATE,unsigned __int64,Guid>(
          (unsigned int)&v203,
          v82,
          (unsigned int)&v93,
          (_DWORD)this + 168,
          (__int64)&v100,
          (__int64)&v101,
          (__int64)&v94,
          (__int64)&v103,
          (__int64)this + 712);
      }
    }
    StateHistory::Update(
      (struct MonitorContext *)((char *)g_MonitorContext + 640),
      (ContentSetManager *)((char *)this + 696));
    v83 = g_MonitorContext;
    *((_DWORD *)g_MonitorContext + 174) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v83 + 704));
    if ( *((_DWORD *)this + 500) )
    {
      v86 = ConfigContext::SysVolIsReady(v85, v84);
      v89 = v86;
      if ( v86 )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
        {
          *(_QWORD *)&v203 = L"ContentSetManager::Initialize";
          *((_QWORD *)&v203 + 1) = 0x200002172LL;
          v204 = L"CSMG";
          dbgobj::DbgPrint<unsigned short,FrsStatus>(&v203, L"Failed to mark SysVol as ready, Err:%?", v86);
        }
        CLEAR_ERROR(&v89);
      }
    }
    goto LABEL_251;
  }
  if ( *((_DWORD *)RelativeVolumePathFromFileId + 1) != 9099 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
    {
      v176 = L"ContentSetManager::Initialize";
      v177 = 8424;
      v178 = 2;
      v179 = L"CSMG";
      v153 = this;
      v113 = *((_DWORD *)this + 148);
      v154 = *(_QWORD *)(v91 + 616) + 18LL;
      v155 = Config::StringParam::Get((Config::StringParam *)(v91 + 240));
      RelativeVolumePathFromFileId = v89;
      dbgobj::DbgPrint<unsigned short,_GUID,unsigned short const *,unsigned short const *,enum CONTENT_SET_STATE,unsigned __int64,Guid,FrsStatus>(
        (unsigned int)&v176,
        (unsigned int)L"Failed to initialize ContentSetManager csId:%? csName:%? rootPath:%? state:%? ptr:%p csInfoHistory"
                       "Guid:%? Error:%?",
        (_DWORD)this + 168,
        (unsigned int)&v155,
        (__int64)&v154,
        (__int64)&v113,
        (__int64)&v153,
        (__int64)this + 712,
        (__int64)v89);
    }
    if ( !v99 )
    {
      if ( *((_DWORD *)RelativeVolumePathFromFileId + 1) == 9037
        || *((_DWORD *)RelativeVolumePathFromFileId + 1) == 9052
        || !(unsigned int)EventThrottle::IsRipe((ContentSetManager *)((char *)this + 992), 1, 0) )
      {
        goto LABEL_192;
      }
      if ( *((_DWORD *)RelativeVolumePathFromFileId + 1) == 9061 )
      {
        v123 = &FrsStringImpl<unsigned short,char>::s_Empty;
        if ( !byte_140315A80 )
        {
          _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
          RelativeVolumePathFromFileId = v89;
        }
        v133 = 0;
        Machine = ConfigContext::GetMachine(v60);
        v133 = Machine;
        v62 = Dword::Dword((Dword *)v211, v104, 10);
        FrsStringImpl<unsigned short,char>::Set((char *)this + 1304, v62);
        v63 = Config::BoolParam::Get((struct Config::Machine *)((char *)Machine + 1344));
        v64 = Dword::Dword((Dword *)v212, v63, 10);
        FrsStringImpl<unsigned short,char>::Set(&v123, v64);
        ContentSetManager::LogEvent((char *)this + 168, v65, RelativeVolumePathFromFileId, (char *)this + 1304, &v123);
        ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v133);
        FrsStringImpl<char,unsigned short>::ReleaseBody(&v123);
      }
      else
      {
        ContentSetManager::LogEvent((char *)this + 168, v59, RelativeVolumePathFromFileId);
      }
      v99 = 1;
    }
    *((_DWORD *)this + 382) = 0;
LABEL_192:
    if ( v105 )
      ContentSetManager::RemoveContentSetRootFromDriver(this);
    v66 = g_ConfigContext;
    ConfigContext::Initialize(g_ConfigContext);
    WorkPathTable::Delete((ConfigContext *)((char *)v66 + 400), (const struct _GUID *)((char *)this + 168));
    if ( (unsigned int)Config::BoolParam::Get((Config::BoolParam *)(v91 + 1120)) )
      ContentSetManager::ScheduleRestart(this);
    goto LABEL_196;
  }
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v172 = L"ContentSetManager::Initialize";
    v173 = 8410;
    v174 = 4;
    v175 = L"CSMG";
    v150 = this;
    v128 = *((_DWORD *)this + 148);
    v151 = *(_QWORD *)(v91 + 616) + 18LL;
    v152 = Config::StringParam::Get((Config::StringParam *)(v91 + 240));
    RelativeVolumePathFromFileId = v89;
    dbgobj::DbgPrint<unsigned short,_GUID,unsigned short const *,unsigned short const *,enum CONTENT_SET_STATE,unsigned __int64,Guid,FrsStatus>(
      (unsigned int)&v172,
      (unsigned int)L"Initialization pending. Waiting for VolumeManager to delete content set database records. csId:%? cs"
                     "Name:%? rootPath:%? state:%? ptr:%p csInfoHistoryGuid:%? Error:%?",
      (_DWORD)this + 168,
      (unsigned int)&v152,
      (__int64)&v151,
      (__int64)&v128,
      (__int64)&v150,
      (__int64)this + 712,
      (__int64)v89);
  }
LABEL_196:
  v67 = g_MonitorContext;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_MonitorContext + 704));
  *((_DWORD *)v67 + 174) = 1;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
  {
    v180 = L"ContentSetManager::Initialize";
    v181 = 8485;
    v182 = 5;
    v183 = L"CSMG";
    dbgobj::DbgPrint<unsigned short>(&v180, L"Update contentInfoHistory");
  }
  *((_DWORD *)this + 498) = *((_DWORD *)RelativeVolumePathFromFileId + 1);
  *((_DWORD *)this + 499) = -1073737820;
  if ( (unsigned int)VolumeManager::IsContentSetProcessedByJournalWrapRecovery(
                       *((VolumeManager **)this + 215),
                       (const struct _GUID *)((char *)this + 168)) )
  {
    *((_DWORD *)this + 192) = 3;
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      v184 = L"ContentSetManager::Initialize";
      v185 = 8493;
      v186 = 5;
      v187 = L"CSMG";
      v156 = this;
      v111 = *((_DWORD *)this + 148);
      v100 = (const unsigned __int16 *)(*(_QWORD *)(v91 + 616) + 18LL);
      v101 = Config::StringParam::Get((Config::StringParam *)(v91 + 240));
      v112 = *((_DWORD *)this + 192);
      dbgobj::DbgPrint<unsigned short,enum ContentSetInfo::CONTENT_SET_STATE,_GUID,unsigned short const *,unsigned short const *,enum CONTENT_SET_STATE,unsigned __int64,Guid>(
        (unsigned int)&v184,
        v68,
        (unsigned int)&v112,
        (_DWORD)this + 168,
        (__int64)&v101,
        (__int64)&v100,
        (__int64)&v111,
        (__int64)&v156,
        (__int64)this + 712);
    }
  }
  else if ( *((_DWORD *)this + 192) != 5 )
  {
    *((_DWORD *)this + 192) = 5;
    v69 = *((_DWORD *)this + 499);
    *((_DWORD *)this + 188) = *((_DWORD *)this + 498);
    *((_DWORD *)this + 191) = (unsigned __int16)v69;
    GetSystemTimeAsFileTime((LPFILETIME)((char *)this + 756));
    if ( g_DebugLog )
    {
      if ( LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
      {
        *(_QWORD *)&v203 = L"ContentSetManager::Initialize";
        *((_QWORD *)&v203 + 1) = 0x500002136LL;
        v204 = L"CSMG";
        v103 = this;
        v93 = *((_DWORD *)this + 148);
        v101 = (const unsigned __int16 *)(*(_QWORD *)(v91 + 616) + 18LL);
        v100 = Config::StringParam::Get((Config::StringParam *)(v91 + 240));
        v94 = *((_DWORD *)this + 192);
        dbgobj::DbgPrint<unsigned short,enum ContentSetInfo::CONTENT_SET_STATE,unsigned long,_GUID,unsigned short const *,unsigned short const *,enum CONTENT_SET_STATE,unsigned __int64,Guid>(
          (unsigned int)&v203,
          v70,
          (unsigned int)&v94,
          (_DWORD)this + 1992,
          (__int64)this + 168,
          (__int64)&v100,
          (__int64)&v101,
          (__int64)&v93,
          (__int64)&v103,
          (__int64)this + 712);
      }
    }
  }
  StateHistory::Update(
    (struct MonitorContext *)((char *)g_MonitorContext + 640),
    (ContentSetManager *)((char *)this + 696));
  v71 = g_MonitorContext;
  *((_DWORD *)g_MonitorContext + 174) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v71 + 704));
LABEL_252:
  CLEAR_ERROR(&v89);
  FHandle::~FHandle((FHandle *)v138);
  v129 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v130);
  ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v91);
  ScopedLock::~ScopedLock((ScopedLock *)v202);
}

```

## disassembly

```asm
0x1401127a4  mov     rax, rsp
0x1401127a7  mov     [rax+10h], rbx
0x1401127ab  mov     [rax+18h], rsi
0x1401127af  mov     [rax+20h], rdi
0x1401127b3  push    rbp
0x1401127b4  push    r12
0x1401127b6  push    r13
0x1401127b8  push    r14
0x1401127ba  push    r15
0x1401127bc  lea     rbp, [rax-9A8h]
0x1401127c3  sub     rsp, 0A80h
0x1401127ca  mov     rax, cs:__security_cookie
0x1401127d1  xor     rax, rsp
0x1401127d4  mov     [rbp+9A0h+var_30], rax
0x1401127db  mov     rsi, rcx
0x1401127de  xor     edi, edi
0x1401127e0  mov     [rbp+9A0h+var_A08], edi
0x1401127e3  lea     rdx, [rcx+560h]; struct ScopedCS *
0x1401127ea  lea     rcx, [rbp+9A0h+var_6F8]; this
0x1401127f1  call    ??0ScopedLock@@QEAA@AEAVScopedCS@@@Z; ScopedLock::ScopedLock(ScopedCS &)
0x1401127f6  nop
0x1401127f7  xor     edx, edx; Val
0x1401127f9  lea     r8d, [rdi+40h]; Size
0x1401127fd  lea     rcx, [rbp+9A0h+var_670]; void *
0x140112804  call    memset_0
0x140112809  mov     [rsp+0AA0h+var_A30], rdi
0x14011280e  lea     rcx, [rbp+9A0h+var_930]; this
0x140112812  call    ??0FilePath@@QEAA@XZ; FilePath::FilePath(void)
0x140112817  nop
0x140112818  mov     [rsp+0AA0h+var_A28], rdi
0x14011281d  lea     rcx, [rbp+9A0h+var_5D0]; this
0x140112824  call    ??0ID_RECORD@@QEAA@XZ; ID_RECORD::ID_RECORD(void)
0x140112829  mov     dword ptr [rsp+0AA0h+var_A38], edi
0x14011282d  lea     r15, [rsi+0A8h]
0x140112834  movups  xmm0, xmmword ptr [r15]
0x140112838  movdqu  [rbp+9A0h+var_6C0], xmm0
0x140112840  mov     [rbp+9A0h+var_6B0], 1
0x14011284b  mov     [rbp+9A0h+var_A18], edi
0x14011284e  xorps   xmm0, xmm0
0x140112851  movups  [rbp+9A0h+var_6E8], xmm0
0x140112858  mov     [rbp+9A0h+var_6D8], rdi
0x14011285f  mov     qword ptr [rbp+9A0h+var_9D0], rdi
0x140112863  mov     [rbp+9A0h+var_9C0], rdi
0x140112867  mov     [rbp+9A0h+var_8F8], rdi
0x14011286e  mov     qword ptr [rbp+9A0h+var_980.dwLowDateTime], rdi
0x140112872  mov     qword ptr [rbp+9A0h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x140112876  mov     [rbp+9A0h+var_9E8], edi
0x140112879  mov     [rbp+9A0h+var_A04], edi
0x14011287c  mov     [rbp+9A0h+var_A00], edi
0x14011287f  lea     rdx, ?fs@ContentSetManager@@0VNtfsFileSystem@@A; struct FileSystem *
0x140112886  lea     rcx, [rbp+9A0h+var_8E8]; this
0x14011288d  call    ??0FHandle@@QEAA@PEAVFileSystem@@@Z; FHandle::FHandle(FileSystem *)
0x140112892  nop
0x140112893  mov     [rbp+9A0h+var_9D4], edi
0x140112896  mov     [rbp+9A0h+var_9D8], edi
0x140112899  lea     rcx, [rsi+460h]
0x1401128a0  call    ?Get@?$ConfigInstance@VContentSet@Config@@@Config@@QEAAPEAVContentSet@2@XZ; Config::ConfigInstance<Config::ContentSet>::Get(void)
0x1401128a5  mov     rdx, rax
0x1401128a8  lea     rcx, [rsp+0AA0h+var_A30]
0x1401128ad  call    ?Set@?$ScopedRef@VContentSet@Config@@@@AEAAXPEAVContentSet@Config@@@Z; ScopedRef<Config::ContentSet>::Set(Config::ContentSet *)
0x1401128b2  mov     qword ptr [rbp+9A0h+var_888], rdi
0x1401128b9  lea     rcx, [rbp+9A0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1401128bd  call    cs:__imp_GetSystemTimeAsFileTime
0x1401128c4  nop     dword ptr [rax+rax+00h]
0x1401128c9  lea     rdx, [rsi+508h]; union _LARGE_INTEGER *
0x1401128d0  call    ?Sample@TimeoutCounter@@AEAAXPEAT_LARGE_INTEGER@@@Z; TimeoutCounter::Sample(_LARGE_INTEGER *)
0x1401128d5  lea     r12, [rsi+248h]
0x1401128dc  mov     [r12], rdi
0x1401128e0  lea     r13, [rsi+518h]
0x1401128e7  mov     rcx, r13
0x1401128ea  call    ?SetEmpty@?$FrsStringImpl@GD@@QEAAXXZ; FrsStringImpl<ushort,char>::SetEmpty(void)
0x1401128ef  lea     rcx, aContentsetmana_53; "ContentSetManager::Initialize"
0x1401128f6  lea     rdx, aCsmg; "CSMG"
0x1401128fd  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140112904  test    rax, rax
0x140112907  jz      loc_1401129C6
0x14011290d  cmp     [rax+40h], edi
0x140112910  jz      loc_1401129C6
0x140112916  cmp     dword ptr [rax+38h], 4
0x14011291a  jl      loc_1401129C6
0x140112920  mov     [rbp+9A0h+var_808], rcx
0x140112927  mov     [rbp+9A0h+var_800], 1DF3h
0x140112931  mov     [rbp+9A0h+var_7FC], 4
0x14011293b  mov     [rbp+9A0h+var_7F8], rdx
0x140112942  mov     [rbp+9A0h+var_848], rsi
0x140112949  mov     eax, [rsi+250h]
0x14011294f  mov     [rbp+9A0h+var_99C], eax
0x140112952  mov     rbx, [rsp+0AA0h+var_A30]
0x140112957  mov     rax, [rbx+268h]
0x14011295e  add     rax, 12h
0x140112962  mov     [rbp+9A0h+var_840], rax
0x140112969  lea     rcx, [rbx+0F0h]; this
0x140112970  call    ?Get@StringParam@Config@@QEBAPEBGXZ; Config::StringParam::Get(void)
0x140112975  mov     [rbp+9A0h+var_838], rax
0x14011297c  lea     rax, [rsi+2C8h]
0x140112983  mov     [rsp+0AA0h+var_A68], rax
0x140112988  lea     rax, [rbp+9A0h+var_848]
0x14011298f  mov     [rsp+0AA0h+var_A70], rax
0x140112994  lea     rax, [rbp+9A0h+var_99C]
0x140112998  mov     [rsp+0AA0h+var_A78], rax
0x14011299d  lea     rax, [rbp+9A0h+var_840]
0x1401129a4  mov     [rsp+0AA0h+var_A80], rax
0x1401129a9  lea     r9, [rbp+9A0h+var_838]
0x1401129b0  mov     r8, r15
0x1401129b3  lea     rdx, aInitializingCs; "Initializing. csId:%? csName:%? rootPat"...
0x1401129ba  lea     rcx, [rbp+9A0h+var_808]
0x1401129c1  call    ??$DbgPrint@GU_GUID@@PEBGPEBGW4CONTENT_SET_STATE@@_KVGuid@@@dbgobj@@QEAA_KPEBGAEBU_GUID@@AEBQEBG2AEBW4CONTENT_SET_STATE@@AEB_KAEBVGuid@@@Z; dbgobj::DbgPrint<ushort,_GUID,ushort const *,ushort const *,CONTENT_SET_STATE,unsigned __int64,Guid>(ushort const *,_GUID const &,ushort const * const &,ushort const * const &,CONTENT_SET_STATE const &,unsigned __int64 const &,Guid const &)
0x1401129c6  mov     [rsi+7C8h], rdi
0x1401129cd  mov     rbx, [rsp+0AA0h+var_A30]
0x1401129d2  mov     rdx, [rbx+268h]
0x1401129d9  add     rdx, 12h; unsigned __int16 *
0x1401129dd  lea     rcx, [rbp+9A0h+var_930]; this
0x1401129e1  call    ?Set@FilePath@@QEAAXPEBG@Z; FilePath::Set(ushort const *)
0x1401129e6  lea     rcx, [rbp+9A0h+var_930]; this
0x1401129ea  call    ?AppendTrailingBackslash@FilePath@@QEAAXXZ; FilePath::AppendTrailingBackslash(void)
0x1401129ef  mov     rcx, rsi; this
0x1401129f2  call    ?HandleJournalWrapRecovery@ContentSetManager@@IEAAPEAVFrsStatus@@XZ; ContentSetManager::HandleJournalWrapRecovery(void)
0x1401129f7  mov     r14, rax
0x1401129fa  mov     [rsp+0AA0h+var_A40], rax
0x1401129ff  test    rax, rax
0x140112a02  jnz     loc_140112CF0
0x140112a08  mov     [rbp+9A0h+var_998], rdi
0x140112a0c  mov     rcx, rsi; this
0x140112a0f  call    ?AddRef@RefCountObject@@QEAAJXZ; RefCountObject::AddRef(void)
0x140112a14  mov     [rbp+9A0h+var_908], rsi
0x140112a1b  mov     ecx, 0B8h; Size
0x140112a20  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140112a25  mov     rdi, rax
0x140112a28  mov     [rsp+0AA0h+var_A40], rax
0x140112a2d  lea     rcx, [rbx+2C0h]
0x140112a34  call    ?GetDisplayPath@FilePath@@SAPEBGAEBV?$FrsStringImpl@GD@@@Z; FilePath::GetDisplayPath(FrsStringImpl<ushort,char> const &)
0x140112a39  mov     rdx, rax
0x140112a3c  lea     rcx, [rbp+9A0h+var_828]
0x140112a43  call    ??0?$FrsStringImpl@GD@@QEAA@PEBG@Z; FrsStringImpl<ushort,char>::FrsStringImpl<ushort,char>(ushort const *)
0x140112a48  nop
0x140112a49  mov     [rbp+9A0h+var_A08], 1
0x140112a50  mov     r8, [rsi+6B8h]
0x140112a57  add     r8, 0A8h
0x140112a5e  mov     r9, rax
0x140112a61  lea     rdx, [rbp+9A0h+var_908]
0x140112a68  mov     rcx, rdi
0x140112a6b  call    ??0DiskFull@ContentSetManager@@QEAA@AEAV?$ScopedRef@VContentSetManager@@@@AEBVVolumeId@@AEBV?$FrsStringImpl@GD@@@Z; ContentSetManager::DiskFull::DiskFull(ScopedRef<ContentSetManager> &,VolumeId const &,FrsStringImpl<ushort,char> const &)
0x140112a70  nop
0x140112a71  mov     rdx, rax
0x140112a74  lea     rcx, [rbp+9A0h+var_998]
0x140112a78  call    ?Set@?$ScopedRef@VShutdownRestartTask@VolumeManager@@@@AEAAXPEAVShutdownRestartTask@VolumeManager@@@Z; ScopedRef<VolumeManager::ShutdownRestartTask>::Set(VolumeManager::ShutdownRestartTask *)
0x140112a7d  nop
0x140112a7e  and     [rbp+9A0h+var_A08], r14d
0x140112a82  lea     rcx, [rbp+9A0h+var_828]
0x140112a89  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x140112a8e  lea     rdx, [rsi+598h]; struct ScopedCS *
0x140112a95  lea     rcx, [rbp+9A0h+var_738]; this
0x140112a9c  call    ??0ScopedLock@@QEAA@AEAVScopedCS@@@Z; ScopedLock::ScopedLock(ScopedCS &)
0x140112aa1  nop
0x140112aa2  lea     rdi, [rsi+5D0h]
0x140112aa9  mov     rbx, [rbp+9A0h+var_998]
0x140112aad  test    rbx, rbx
0x140112ab0  jnz     short loc_140112AB6
0x140112ab2  xor     edx, edx
0x140112ab4  jmp     short loc_140112AC1
0x140112ab6  mov     rcx, rbx; this
0x140112ab9  call    ?AddRef@RefCountObject@@QEAAJXZ; RefCountObject::AddRef(void)
0x140112abe  mov     rdx, rbx
0x140112ac1  mov     rcx, rdi
0x140112ac4  call    ?Set@?$ScopedRef@VShutdownRestartTask@VolumeManager@@@@AEAAXPEAVShutdownRestartTask@VolumeManager@@@Z; ScopedRef<VolumeManager::ShutdownRestartTask>::Set(VolumeManager::ShutdownRestartTask *)
0x140112ac9  nop
0x140112aca  lea     rcx, [rbp+9A0h+var_738]; this
0x140112ad1  call    ??1ScopedLock@@QEAA@XZ; ScopedLock::~ScopedLock(void)
0x140112ad6  nop
0x140112ad7  lea     rcx, [rbp+9A0h+var_908]
0x140112ade  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x140112ae3  nop
0x140112ae4  lea     rcx, [rbp+9A0h+var_998]
0x140112ae8  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x140112aed  mov     rcx, [rsp+0AA0h+var_A30]
0x140112af2  add     rcx, 460h; this
0x140112af9  call    ?Get@BoolParam@Config@@QEBA?BHXZ; Config::BoolParam::Get(void)
0x140112afe  xor     edi, edi
0x140112b00  test    eax, eax
0x140112b02  jnz     short loc_140112B5D
0x140112b04  call    cs:__imp_GetCurrentThreadId
0x140112b0b  nop     dword ptr [rax+rax+00h]
0x140112b10  mov     [rsp+0AA0h+var_A60], rdi
0x140112b15  mov     dword ptr [rsp+0AA0h+var_A68], eax
0x140112b19  mov     dword ptr [rsp+0AA0h+var_A70], 1E2Dh
0x140112b21  lea     rbx, aContentsetmana_34; "ContentSetManager::Initialize"
0x140112b28  mov     [rsp+0AA0h+var_A78], rbx
0x140112b2d  lea     rax, aBaseFsRemotefs_85; "base\\fs\\remotefs\\frs\\src\\sync\\con"...
0x140112b34  mov     [rsp+0AA0h+var_A80], rax
0x140112b39  lea     r9d, [rdi+3]
0x140112b3d  xor     r8d, r8d
0x140112b40  mov     edx, 235Ch
0x140112b45  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140112b4a  mov     r14, rax
0x140112b4d  mov     [rsp+0AA0h+var_A40], rax
0x140112b52  test    rax, rax
0x140112b55  jnz     loc_140112CF7
0x140112b5b  jmp     short loc_140112B64
0x140112b5d  lea     rbx, aContentsetmana_34; "ContentSetManager::Initialize"
0x140112b64  lea     rdx, [rbp+9A0h+var_A00]; int *
0x140112b68  mov     rcx, rsi; this
0x140112b6b  call    ?CheckRootOverlap@ContentSetManager@@AEAAPEAVFrsStatus@@AEAH@Z; ContentSetManager::CheckRootOverlap(int &)
0x140112b70  mov     r14, rax
0x140112b73  mov     [rsp+0AA0h+var_A40], rax
0x140112b78  test    rax, rax
0x140112b7b  jnz     loc_140112CF7
0x140112b81  mov     rcx, rsi; this
0x140112b84  call    ?ExcludeFilesFromBackup@ContentSetManager@@AEAAPEAVFrsStatus@@XZ; ContentSetManager::ExcludeFilesFromBackup(void)
0x140112b89  mov     r14, rax
0x140112b8c  mov     [rsp+0AA0h+var_A40], rax
0x140112b91  test    rax, rax
0x140112b94  jnz     loc_140112CF7
0x140112b9a  mov     rcx, [rsi+700h]
0x140112ba1  mov     rax, [rcx]
0x140112ba4  lea     rdx, [rsp+0AA0h+var_A28]
0x140112ba9  mov     rax, [rax+30h]
0x140112bad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140112bb2  mov     rcx, [rsp+0AA0h+var_A28]
0x140112bb7  mov     rax, [rcx]
0x140112bba  xor     edx, edx
0x140112bbc  mov     rax, [rax+10h]
0x140112bc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140112bc5  mov     r14, rax
0x140112bc8  mov     [rsp+0AA0h+var_A40], rax
0x140112bcd  test    rax, rax
0x140112bd0  jnz     loc_140112CF7
0x140112bd6  lea     rax, [rbp+9A0h+var_9E8]
0x140112bda  mov     [rsp+0AA0h+var_A60], rax; int *
0x140112bdf  lea     rax, [rbp+9A0h+var_9D8]
0x140112be3  mov     [rsp+0AA0h+var_A68], rax; unsigned int *
0x140112be8  lea     rax, [rbp+9A0h+var_980]
0x140112bec  mov     [rsp+0AA0h+var_A70], rax; struct _FILETIME *
0x140112bf1  lea     rax, [rbp+9A0h+var_8F8]
0x140112bf8  mov     [rsp+0AA0h+var_A78], rax; struct FileId *
0x140112bfd  lea     rax, [rbp+9A0h+var_9C0]
0x140112c01  mov     [rsp+0AA0h+var_A80], rax; struct FileId *
0x140112c06  lea     r9, [rbp+9A0h+var_9D0]; union _LARGE_INTEGER *
0x140112c0a  lea     r8, [rbp+9A0h+var_A04]; int *
0x140112c0e  mov     rdx, [rsp+0AA0h+var_A28]; struct Db *
0x140112c13  mov     rcx, rsi; this
0x140112c16  call    ?CheckContentSetState@ContentSetManager@@AEAAPEAVFrsStatus@@PEAVDb@@AEAHAEAT_LARGE_INTEGER@@AEAVFileId@@3AEAU_FILETIME@@AEAK1@Z; ContentSetManager::CheckContentSetState(Db *,int &,_LARGE_INTEGER &,FileId &,FileId &,_FILETIME &,ulong &,int &)
0x140112c1b  mov     r14, rax
0x140112c1e  mov     [rsp+0AA0h+var_A40], rax
0x140112c23  test    rax, rax
0x140112c26  jnz     loc_140112CF7
0x140112c2c  mov     rcx, [rsp+0AA0h+var_A28]
0x140112c31  mov     rax, [rcx]
0x140112c34  lea     r9, [rbp+9A0h+var_5D0]
0x140112c3b  lea     r8, [rbp+9A0h+var_6C0]
0x140112c42  lea     rdx, [rbp+9A0h+var_A18]
0x140112c46  mov     rax, [rax+38h]
0x140112c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140112c4f  mov     r14, rax
0x140112c52  mov     [rsp+0AA0h+var_A40], rax
0x140112c57  test    rax, rax
0x140112c5a  jnz     loc_140112CF7
0x140112c60  mov     rdx, [rbp+9A0h+var_928]
0x140112c64  add     rdx, 12h; unsigned __int16 *
0x140112c68  mov     dword ptr [rsp+0AA0h+var_A80], 24h ; '$'; unsigned int
0x140112c70  lea     r9d, [rax+3]; unsigned int
0x140112c74  mov     r8d, 0A0h; unsigned int
0x140112c7a  lea     rcx, [rbp+9A0h+var_8E8]; this
0x140112c81  call    ?OpenPath@FHandle@@QEAAPEAVFrsStatus@@PEBGKKK@Z; FHandle::OpenPath(ushort const *,ulong,ulong,ulong)
0x140112c86  mov     r14, rax
0x140112c89  mov     [rsp+0AA0h+var_A40], rax
0x140112c8e  test    rax, rax
0x140112c91  jnz     short loc_140112CF7
0x140112c93  lea     rax, [rbp+9A0h+var_A18]
0x140112c97  mov     [rsp+0AA0h+var_A80], rax; int *
0x140112c9c  mov     r9, [rsp+0AA0h+var_A28]; struct Db *
0x140112ca1  lea     r8, [rbp+9A0h+var_5D0]; struct ID_RECORD *
0x140112ca8  lea     rdx, [rbp+9A0h+var_8E8]; struct FHandle *
0x140112caf  mov     rcx, rsi; this
0x140112cb2  call    ?CheckContentRoot@ContentSetManager@@AEAAPEAVFrsStatus@@AEAVFHandle@@AEAVID_RECORD@@PEAVDb@@AEAH@Z; ContentSetManager::CheckContentRoot(FHandle &,ID_RECORD &,Db *,int &)
0x140112cb7  mov     r14, rax
0x140112cba  mov     [rsp+0AA0h+var_A40], rax
0x140112cbf  test    rax, rax
0x140112cc2  jnz     short loc_140112CF7
0x140112cc4  cmp     [rbp+9A0h+var_9E8], edi
0x140112cc7  jz      short loc_140112D3F
0x140112cc9  mov     rcx, [rsi+6B8h]
0x140112cd0  mov     r9d, [rsi+250h]
0x140112cd7  mov     rax, [rsi+3D8h]
0x140112cde  mov     [rbp+9A0h+var_950], rax
0x140112ce2  mov     r8, r15
0x140112ce5  lea     rdx, [rbp+9A0h+var_950]
0x140112ce9  call    ?RemoveContentSetRootFromReadOnlyDriver@VolumeManager@@QEAAXVFileId@@AEBU_GUID@@W4CONTENT_SET_STATE@@@Z; VolumeManager::RemoveContentSetRootFromReadOnlyDriver(FileId,_GUID const &,CONTENT_SET_STATE)
0x140112cee  jmp     short loc_140112D3F
0x140112cf0  lea     rbx, aContentsetmana_34; "ContentSetManager::Initialize"
0x140112cf7  cmp     [rbp+9A0h+var_9E8], edi
0x140112cfa  jz      short loc_140112D36
0x140112cfc  mov     rcx, [rsi+6B8h]; this
0x140112d03  cmp     [rsi+3D8h], rdi
0x140112d0a  jz      short loc_140112D31
0x140112d0c  mov     r9d, [rsi+250h]
0x140112d13  mov     rax, [rsi+3D8h]
0x140112d1a  mov     [rbp+9A0h+var_948], rax
0x140112d1e  mov     r8, r15
0x140112d21  lea     rdx, [rbp+9A0h+var_948]
0x140112d25  call    ?RemoveContentSetRootFromReadOnlyDriver@VolumeManager@@QEAAXVFileId@@AEBU_GUID@@W4CONTENT_SET_STATE@@@Z; VolumeManager::RemoveContentSetRootFromReadOnlyDriver(FileId,_GUID const &,CONTENT_SET_STATE)
  ... truncated ...
```
