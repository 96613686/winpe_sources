# OutConnectionContentSetContext::OpenFile(int,ID_UPDATE &,__MIDL___MIDL_itf_frstransport_0000_0000_0009 *,Rdc::MyFRS_RDC_FILEINFO *,ScopedRef<FRS_SERVER_CONTEXT> &,unsigned __int64,unsigned __int64,SyncInfo *,FrsStringImpl<ushort,char> const &)

- ea: `0x140172518`
- end: `0x140173ea6`
- name: `?OpenFile@OutConnectionContentSetContext@@QEAAPEAVFrsStatus@@HAEAVID_UPDATE@@PEAW4__MIDL___MIDL_itf_frstransport_0000_0000_0009@@PEAUMyFRS_RDC_FILEINFO@Rdc@@AEAV?$ScopedRef@VFRS_SERVER_CONTEXT@@@@_K4PEAVSyncInfo@@AEBV?$FrsStringImpl@GD@@@Z`
- size: `6542`
- prototype: `__int64 __usercall@<rax>(OutConnectionContentSetContext *this@<rcx>, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `70`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140172170`

## callees

- `0x1400036a0`
- `0x1400036d0`
- `0x14000c910`
- `0x14000cdc0`
- `0x14000daa0`
- `0x14000e34c`
- `0x140022d1c`
- `0x140024be4`
- `0x140028fcc`
- `0x14002c160`
- `0x14002c1c0`
- `0x14002c2f4`
- `0x1400370bc`
- `0x1400391c4`
- `0x140047e4c`
- `0x14004d52c`
- `0x14006a428`
- `0x14006a550`
- `0x14006d538`
- `0x14006f224`
- `0x1400727e8`
- `0x140088ad0`
- `0x1400985ec`
- `0x14009d478`
- `0x14009d5e0`
- `0x1400f44dc`
- `0x1400fedf4`
- `0x140109280`
- `0x14010942c`
- `0x140109aa4`
- `0x140111058`
- `0x140111380`
- `0x140115844`
- `0x140115bb8`
- `0x14011734c`
- `0x140118934`
- `0x14011dc98`
- `0x14011fe04`
- `0x140120464`
- `0x140120928`
- `0x14012c9ac`
- `0x140139aa8`
- `0x14014d6d8`
- `0x14014dd90`
- `0x14014e03c`
- `0x14014e09c`
- `0x140151744`
- `0x1401521d8`
- `0x140152280`
- `0x14016e4f0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x140173bc8`
- `KERNEL32!LeaveCriticalSection` at `0x140173bc8`
- `KERNEL32!EnterCriticalSection` at `0x1401739c8`
- `KERNEL32!EnterCriticalSection` at `0x140173b28`
- `KERNEL32!EnterCriticalSection` at `0x1401739c8`
- `KERNEL32!EnterCriticalSection` at `0x140173b28`
- `KERNEL32!GetCurrentThreadId` at `0x140172963`
- `KERNEL32!GetCurrentThreadId` at `0x1401729c6`
- `KERNEL32!GetCurrentThreadId` at `0x140172a3f`
- `KERNEL32!GetCurrentThreadId` at `0x140172b74`
- `KERNEL32!GetCurrentThreadId` at `0x140172bb7`
- `KERNEL32!GetCurrentThreadId` at `0x140172e46`
- `KERNEL32!GetCurrentThreadId` at `0x140173474`
- `KERNEL32!GetCurrentThreadId` at `0x140173dda`
- `KERNEL32!GetCurrentThreadId` at `0x140172963`
- `KERNEL32!GetCurrentThreadId` at `0x1401729c6`
- `KERNEL32!GetCurrentThreadId` at `0x140172a3f`
- `KERNEL32!GetCurrentThreadId` at `0x140172b74`
- `KERNEL32!GetCurrentThreadId` at `0x140172bb7`
- `KERNEL32!GetCurrentThreadId` at `0x140172e46`
- `KERNEL32!GetCurrentThreadId` at `0x140173474`
- `KERNEL32!GetCurrentThreadId` at `0x140173dda`

## string_xrefs

- `0x140173a1f`: `Update syncInfoHistory`
- `0x140173b78`: `Update syncInfoHistory`
- `0x140172695`: `OutConnectionContentSetContext::OpenFile`
- `0x140172747`: `OutConnectionContentSetContext::OpenFile`
- `0x14017283c`: `OutConnectionContentSetContext::OpenFile`
- `0x140172924`: `OutConnectionContentSetContext::OpenFile`
- `0x140172ada`: `OutConnectionContentSetContext::OpenFile`
- `0x140172b28`: `OutConnectionContentSetContext::OpenFile`
- `0x140172cb0`: `OutConnectionContentSetContext::OpenFile`
- `0x140173186`: `OutConnectionContentSetContext::OpenFile`
- `0x140173432`: `OutConnectionContentSetContext::OpenFile`
- `0x1401734f9`: `OutConnectionContentSetContext::OpenFile`
- `0x14017370c`: `OutConnectionContentSetContext::OpenFile`
- `0x14017381c`: `OutConnectionContentSetContext::OpenFile`
- `0x1401738a5`: `OutConnectionContentSetContext::OpenFile`
- `0x140173935`: `OutConnectionContentSetContext::OpenFile`
- `0x140173d70`: `OutConnectionContentSetContext::OpenFile`
- `0x140172b64`: `Cannot service request for resource because resource is ghosted. uid:%? requestedGVSN:%?`
- `0x140172985`: `OutConnectionContentSetContext::OpenFile`
- `0x1401729e3`: `OutConnectionContentSetContext::OpenFile`
- `0x140172e30`: `OutConnectionContentSetContext::OpenFile`
- `0x14017325c`: `OutConnectionContentSetContext::OpenFile`
- `0x140173491`: `OutConnectionContentSetContext::OpenFile`
- `0x140173df7`: `OutConnectionContentSetContext::OpenFile`
- `0x140172b0a`: `Unsupported configuration encountered. Two spokes are directly connected`
- `0x14017373e`: `WRITE_FILE_TO_STAGE record.simData=(%?,%?)`
- `0x140173464`: `FILE_IS_STAGED UPDATED record.simData=(%?,%?)`
- `0x14017352b`: `FILE_IS_STAGED UPDATED record.simData=(%?,%?)`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall OutConnectionContentSetContext::OpenFile(
        ContentSetManager **this,
        BOOL a2,
        ID_UPDATE *a3,
        unsigned int *a4,
        __int64 a5,
        __int64 a6,
        unsigned __int64 a7,
        unsigned __int64 a8,
        struct HistoryRecord *a9,
        VolumeManager *a10)
{
  __int64 v11; // r13
  _QWORD *v12; // r15
  __int64 v13; // rdi
  VolumeManager *v14; // r14
  StageWriter *v15; // rbx
  struct IMarshalFileReader *v16; // rsi
  struct FrsStatus *Staging; // r12
  __int64 v18; // rax
  unsigned __int64 v19; // rdx
  const wchar_t *v20; // r8
  int v21; // eax
  unsigned __int64 *v22; // rdx
  int v23; // edx
  int v24; // ecx
  int v25; // r10d
  __int64 v26; // rcx
  __int64 v27; // rax
  ContentSetManager **v28; // rcx
  ID_UPDATE *v29; // r10
  DWORD v30; // eax
  __int64 v31; // rcx
  __int64 v32; // rcx
  ContentSetManager **v33; // rax
  ID_UPDATE *v34; // r10
  unsigned int v35; // ecx
  LPCRITICAL_SECTION v36; // rax
  __int64 v37; // rcx
  __int64 v38; // rcx
  unsigned int *v39; // rbx
  struct FrsStatus *StageReaderOrWriter; // rax
  ContentSetManager **v41; // rdi
  OutConnectionContentSetContext *v42; // rcx
  int v43; // eax
  unsigned int v44; // edx
  __int64 v45; // rdi
  DWORD v46; // eax
  __int64 v47; // rcx
  struct FrsStatus *v48; // rax
  ID_UPDATE *v49; // r8
  int v50; // eax
  __int64 v51; // rcx
  bool v52; // zf
  int v53; // eax
  struct Reader *v54; // rdi
  unsigned int v55; // eax
  char *v56; // rax
  char *v57; // rsi
  struct FrsStatus *v58; // rdi
  struct FrsStatus *v59; // rdx
  int v60; // r8d
  int v61; // r9d
  __int64 v62; // r11
  StageReader *v63; // rsi
  __int64 v64; // rdi
  __int64 v65; // rdi
  const volatile int *v66; // rax
  int v67; // r8d
  int v68; // r9d
  XpressCompressReader *v69; // rax
  StageReader *v70; // rdi
  _QWORD *v71; // rax
  struct ContentSetManager *v72; // r12
  unsigned int v73; // r13d
  const volatile int *v74; // rsi
  StageReader *v75; // rax
  void *v76; // rdi
  struct Reader *UncompressReader; // rax
  int v78; // edi
  DWORD v79; // eax
  __int64 v80; // rcx
  __int64 v81; // rax
  struct StageReader *v82; // rbx
  _QWORD *v83; // rax
  unsigned int v84; // r12d
  const volatile int *v85; // rsi
  void *v86; // rdi
  struct Writer *CompressWriter; // rax
  void *v88; // r9
  struct Reader *v89; // rdi
  struct IMarshalFileReader *v90; // r8
  unsigned int v91; // edx
  ContentSetManager **v92; // rbx
  __int64 v93; // rbx
  Rdc::SyncServerState *v94; // rcx
  void (__fastcall ***v95)(_QWORD, __int64); // rcx
  struct MonitorContext *v96; // rbx
  ContentSetManager **v97; // rsi
  struct HistoryRecord *v98; // rdx
  struct FrsStatus *v99; // rax
  struct FrsStatus *v100; // rax
  struct MonitorContext *v101; // rbx
  struct _RTL_CRITICAL_SECTION *v102; // rcx
  const unsigned __int16 *v103; // rdi
  __int64 v104; // rax
  const unsigned __int16 *v105; // rbx
  __int64 v106; // rax
  const unsigned __int16 *v107; // rax
  const unsigned __int16 *v108; // rdx
  const unsigned __int16 *v109; // r9
  ID_UPDATE *v110; // r9
  int v111; // r8d
  ID_UPDATE *v112; // rcx
  _OWORD *v113; // rax
  __int64 v114; // rdx
  DWORD v115; // eax
  __int64 v116; // rcx
  int v118; // [rsp+20h] [rbp-E0h]
  struct Rdc::SyncServerState **v119; // [rsp+28h] [rbp-D8h]
  DWORD CurrentThreadId; // [rsp+38h] [rbp-C8h]
  DWORD v121; // [rsp+38h] [rbp-C8h]
  DWORD v122; // [rsp+38h] [rbp-C8h]
  DWORD v123; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v124; // [rsp+48h] [rbp-B8h]
  unsigned int v126; // [rsp+60h] [rbp-A0h]
  BOOL v127; // [rsp+68h] [rbp-98h] BYREF
  ID_UPDATE *v128; // [rsp+70h] [rbp-90h]
  StageWriter *v129; // [rsp+78h] [rbp-88h] BYREF
  struct StageReader *v130; // [rsp+80h] [rbp-80h] BYREF
  StageReader *v131; // [rsp+88h] [rbp-78h]
  struct FrsStatus *v132; // [rsp+90h] [rbp-70h] BYREF
  const wchar_t *v133; // [rsp+98h] [rbp-68h] BYREF
  int v134; // [rsp+A0h] [rbp-60h]
  int v135; // [rsp+A4h] [rbp-5Ch]
  const wchar_t *v136; // [rsp+A8h] [rbp-58h]
  int v137; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v138; // [rsp+B8h] [rbp-48h]
  unsigned int v139; // [rsp+C0h] [rbp-40h]
  struct IMarshalFileReader *v140; // [rsp+C8h] [rbp-38h] BYREF
  struct FrsStatus *v141; // [rsp+D0h] [rbp-30h] BYREF
  struct Reader *v142; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v143; // [rsp+E0h] [rbp-20h]
  int v144; // [rsp+E8h] [rbp-18h] BYREF
  int v145; // [rsp+ECh] [rbp-14h]
  int v146; // [rsp+F0h] [rbp-10h]
  unsigned int v147; // [rsp+F4h] [rbp-Ch] BYREF
  struct ContentSetManager **v148; // [rsp+F8h] [rbp-8h]
  VolumeManager *v149; // [rsp+100h] [rbp+0h] BYREF
  struct Reader *v150; // [rsp+108h] [rbp+8h]
  struct IMarshalFileReader *v151; // [rsp+110h] [rbp+10h] BYREF
  struct SeekReader *v152; // [rsp+118h] [rbp+18h] BYREF
  __int64 v153; // [rsp+120h] [rbp+20h] BYREF
  _QWORD *v154; // [rsp+128h] [rbp+28h] BYREF
  VolumeManager *v155; // [rsp+130h] [rbp+30h] BYREF
  struct FrsStatus *v156; // [rsp+138h] [rbp+38h] BYREF
  struct HistoryRecord *v157; // [rsp+140h] [rbp+40h]
  VolumeManager *v158; // [rsp+148h] [rbp+48h] BYREF
  unsigned int *v159; // [rsp+150h] [rbp+50h]
  unsigned __int64 v160; // [rsp+158h] [rbp+58h]
  __int64 v161; // [rsp+160h] [rbp+60h] BYREF
  const wchar_t *v162; // [rsp+168h] [rbp+68h] BYREF
  int v163; // [rsp+170h] [rbp+70h]
  int v164; // [rsp+174h] [rbp+74h]
  const wchar_t *v165; // [rsp+178h] [rbp+78h]
  const wchar_t *v166; // [rsp+180h] [rbp+80h] BYREF
  int v167; // [rsp+188h] [rbp+88h]
  int v168; // [rsp+18Ch] [rbp+8Ch]
  const wchar_t *v169; // [rsp+190h] [rbp+90h]
  const wchar_t *v170; // [rsp+198h] [rbp+98h] BYREF
  int v171; // [rsp+1A0h] [rbp+A0h]
  int v172; // [rsp+1A4h] [rbp+A4h]
  const wchar_t *v173; // [rsp+1A8h] [rbp+A8h]
  const wchar_t *v174; // [rsp+1B0h] [rbp+B0h] BYREF
  int v175; // [rsp+1B8h] [rbp+B8h]
  int v176; // [rsp+1BCh] [rbp+BCh]
  const wchar_t *v177; // [rsp+1C0h] [rbp+C0h]
  __int128 v178; // [rsp+1C8h] [rbp+C8h] BYREF
  const wchar_t *v179; // [rsp+1D8h] [rbp+D8h]
  const wchar_t *v180; // [rsp+1E8h] [rbp+E8h] BYREF
  int v181; // [rsp+1F0h] [rbp+F0h]
  int v182; // [rsp+1F4h] [rbp+F4h]
  const wchar_t *v183; // [rsp+1F8h] [rbp+F8h]
  _BYTE v184[24]; // [rsp+210h] [rbp+110h] BYREF
  __int128 v185; // [rsp+228h] [rbp+128h] BYREF
  const wchar_t *v186; // [rsp+238h] [rbp+138h]
  char v187[24]; // [rsp+240h] [rbp+140h] BYREF
  struct _GUID v188; // [rsp+258h] [rbp+158h] BYREF
  _BYTE v189[20]; // [rsp+268h] [rbp+168h] BYREF
  _OWORD v190[2]; // [rsp+27Ch] [rbp+17Ch] BYREF
  char v191; // [rsp+2A8h] [rbp+1A8h]
  unsigned __int16 v192[266]; // [rsp+2ACh] [rbp+1ACh] BYREF
  _BYTE v193[32]; // [rsp+4C0h] [rbp+3C0h] BYREF
  _QWORD v194[92]; // [rsp+4E0h] [rbp+3E0h] BYREF
  __int128 v195; // [rsp+7C0h] [rbp+6C0h]

  v159 = a4;
  v128 = a3;
  v127 = a2;
  v138 = a6;
  v143 = a7;
  v160 = a8;
  v157 = a9;
  v155 = a10;
  v11 = 0;
  v141 = 0;
  v12 = 0;
  v154 = 0;
  v161 = 0;
  v13 = 0;
  v153 = 0;
  v14 = 0;
  v149 = 0;
  v131 = 0;
  v130 = 0;
  v15 = 0;
  v129 = 0;
  v142 = 0;
  v140 = 0;
  ID_RECORD::ID_RECORD((ID_RECORD *)v184);
  v126 = 3;
  v139 = 3;
  v144 = 0;
  v137 = 0;
  v147 = 0;
  v156 = 0;
  v150 = 0;
  v152 = 0;
  v16 = 0;
  v151 = 0;
  v145 = 0;
  v146 = 1;
  *(_QWORD *)(*(_QWORD *)a6 + 320LL) = 0;
  *(_QWORD *)(*(_QWORD *)a6 + 312LL) = 0;
  Staging = OutConnectionContentSetContext::MarkContextInUse((OutConnectionContentSetContext *)this);
  v148 = this + 7;
  if ( Staging )
  {
    v146 = 0;
  }
  else
  {
    v18 = Config::ConfigInstance<Config::ContentSet>::Get((char *)this[7] + 1120);
    ScopedRef<Config::ContentSet>::Set(&v154, v18);
    Staging = (struct FrsStatus *)ContentSetManager::GetStaging(*v148, &v153);
    v12 = v154;
    v13 = v153;
  }
  v19 = (unsigned __int64)L"OutConnectionContentSetContext::OpenFile";
  v20 = L"OUTC";
  if ( (*((_BYTE *)v128 + 152) & 8) != 0
    && g_DebugLog
    && LODWORD(g_DebugLog[1].LockSemaphore)
    && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
  {
    v162 = L"OutConnectionContentSetContext::OpenFile";
    v163 = 1769;
    v164 = 5;
    v165 = L"OUTC";
    dbgobj::DbgPrint<unsigned short,UID,GVSN>(
      &v162,
      L"Received request for ghosted data. uid:%? requestedGVSN:%?",
      v128,
      (char *)v128 + 24);
  }
  if ( !Staging )
  {
    Staging = (struct FrsStatus *)ContentSetManager::GetVolumeManager(*v148, &v149, v20);
    if ( Staging )
    {
      v14 = v149;
    }
    else
    {
      v21 = Settings::GenericDwordSetting::operator()(&Settings::DebugVolumeManagerRefCount);
      v14 = v149;
      if ( v21 && g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
      {
        v166 = L"OutConnectionContentSetContext::OpenFile";
        v167 = 1783;
        v168 = 5;
        v169 = L"OUTC";
        v158 = v149;
        dbgobj::DbgPrint<unsigned short,unsigned __int64>(
          &v166,
          L"[VMREF] Added reference to volume manager. ptr:%p",
          &v158);
      }
      if ( !*((_DWORD *)this + 12) )
      {
        if ( a5 )
        {
          v22 = (unsigned __int64 *)(a5 + 8);
          v132 = (struct FrsStatus *)(a5 + 8);
        }
        else
        {
          v22 = (unsigned __int64 *)&v156;
          v132 = (struct FrsStatus *)8;
        }
        Staging = OutConnectionContentSetContext::GetUpdatedRecord(
                    (OutConnectionContentSetContext *)this,
                    *v148,
                    v128,
                    0,
                    (struct ID_RECORD *)v184,
                    v22);
        if ( !Staging && a5 && (*((_BYTE *)v128 + 152) & 4) == 0 )
        {
          Rdc::MyFRS_RDC_FILEINFO::ComputeRecursionDepth((Rdc::MyFRS_RDC_FILEINFO *)a5, *(_QWORD *)v132);
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
          {
            v170 = L"OutConnectionContentSetContext::OpenFile";
            v171 = 1802;
            v172 = 5;
            v173 = L"OUTC";
            dbgobj::DbgPrint<unsigned short,int,unsigned __int64,unsigned char>(
              (unsigned int)&v170,
              v19,
              (unsigned int)&v127,
              (_DWORD)v132,
              a5 + 20);
          }
          v127 = v127 && (*(_QWORD *)v132 & 0xFFFFFFFFFFFFFC00uLL) > 0x10000 && *(_BYTE *)(a5 + 20);
        }
      }
    }
  }
  if ( (v191 & 1) == 0 )
    goto LABEL_103;
  if ( Staging )
    goto LABEL_208;
  if ( (*((_BYTE *)v128 + 152) & 8) != 0 && !(unsigned __int8)GVSN::operator==((char *)v128 + 24, &v185, v20) )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      v133 = L"OutConnectionContentSetContext::OpenFile";
      v134 = 1834;
      v135 = 3;
      v136 = L"OUTC";
      dbgobj::DbgPrint<unsigned short,UID,GVSN,GVSN>((unsigned int)&v133, v23, v25, v24, (__int64)&v185);
    }
    CurrentThreadId = GetCurrentThreadId();
    v27 = FrsStatusList::PushNewError(
            v26,
            9029,
            0,
            3,
            "base\\fs\\remotefs\\frs\\src\\sync\\outconnection.cpp",
            "OutConnectionContentSetContext::OpenFile",
            1845,
            CurrentThreadId,
            0);
    goto LABEL_42;
  }
  if ( (unsigned int)ID_RECORD::Alive((ID_RECORD *)v184) )
    goto LABEL_46;
  v30 = GetCurrentThreadId();
  Staging = (struct FrsStatus *)FrsStatusList::PushNewError(
                                  v31,
                                  170,
                                  1,
                                  1,
                                  "base\\fs\\remotefs\\frs\\src\\sync\\outconnection.cpp",
                                  "OutConnectionContentSetContext::OpenFile",
                                  1856,
                                  v30,
                                  0);
  if ( Staging )
  {
LABEL_208:
    v41 = this;
    goto LABEL_209;
  }
  v29 = v128;
LABEL_46:
  v19 = *((unsigned int *)v29 + 38);
  if ( (v19 & 0xC) != 0 && (unsigned int)ContentSetManager::IsGhosted(this[7]) )
  {
    v121 = GetCurrentThreadId();
    v27 = FrsStatusList::PushNewError(
            v32,
            9309,
            0,
            3,
            "base\\fs\\remotefs\\frs\\src\\sync\\outconnection.cpp",
            "OutConnectionContentSetContext::OpenFile",
            1867,
            v121,
            0);
LABEL_42:
    Staging = (struct FrsStatus *)v27;
    v28 = this;
LABEL_104:
    v45 = a5;
    goto LABEL_105;
  }
  v33 = this;
  if ( !*((_DWORD *)this + 12) )
  {
    if ( Settings::GhostingEnabled )
    {
      Staging = ContentSetManager::IsFileGhosted(this[7], (struct FileId *)v193, &v144, &v137, &v147);
      if ( Staging )
      {
LABEL_103:
        v28 = this;
        goto LABEL_104;
      }
      v34 = v128;
      v35 = *((_DWORD *)v128 + 38);
      if ( v144 )
      {
        v36 = g_DebugLog;
        if ( (v35 & 4) != 0 )
        {
          if ( !g_DebugLog )
          {
LABEL_62:
            v122 = GetCurrentThreadId();
            v27 = FrsStatusList::PushNewError(
                    v37,
                    9303,
                    0,
                    3,
                    "base\\fs\\remotefs\\frs\\src\\sync\\outconnection.cpp",
                    "OutConnectionContentSetContext::OpenFile",
                    1910,
                    v122,
                    0);
            goto LABEL_42;
          }
          if ( LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
          {
            v133 = L"OutConnectionContentSetContext::OpenFile";
            v134 = 1902;
            v135 = 2;
            v136 = L"OUTC";
            dbgobj::DbgPrint<unsigned short>(
              &v133,
              L"Unsupported configuration encountered. Two spokes are directly connected");
            v36 = g_DebugLog;
            v34 = v128;
          }
        }
        if ( v36 && LODWORD(v36[1].LockSemaphore) && SLODWORD(v36[1].OwningThread) >= 2 )
        {
          v133 = L"OutConnectionContentSetContext::OpenFile";
          v134 = 1905;
          v135 = 2;
          v136 = L"OUTC";
          dbgobj::DbgPrint<unsigned short,UID,GVSN>(
            &v133,
            L"Cannot service request for resource because resource is ghosted. uid:%? requestedGVSN:%?",
            v34,
            (char *)v34 + 24);
        }
        goto LABEL_62;
      }
      v19 = v35;
      if ( (v35 & 4) != 0 )
      {
        if ( v137 )
        {
          v137 = (v147 & 0xFFFFFFDF) != 0 ? v137 : 0;
          if ( v137 )
          {
            v123 = GetCurrentThreadId();
            v27 = FrsStatusList::PushNewError(
                    v38,
                    9304,
                    0,
                    3,
                    "base\\fs\\remotefs\\frs\\src\\sync\\outconnection.cpp",
                    "OutConnectionContentSetContext::OpenFile",
                    1963,
                    v123,
                    0);
            goto LABEL_42;
          }
        }
      }
      v33 = this;
    }
    if ( !*((_DWORD *)v33 + 12) && (v19 & 0xC) == 0 && a5 )
    {
      v39 = v159;
      if ( !*v159 && v127 )
        *v159 = 1;
      v118 = (*((__int64 (__fastcall **)(ContentSetManager **))v33[4] + 5))(v33 + 4);
      StageReaderOrWriter = (struct FrsStatus *)Staging::GetStageReaderOrWriter(v13, v184, *v39, v12);
      Staging = StageReaderOrWriter;
      v132 = StageReaderOrWriter;
      v15 = v129;
      if ( !StageReaderOrWriter )
      {
        v131 = v130;
        v42 = (OutConnectionContentSetContext *)v139;
        v126 = v139;
        goto LABEL_88;
      }
      if ( *((_DWORD *)StageReaderOrWriter + 1) == 1816 )
      {
        v126 = 3;
        if ( v129 )
        {
          StageWriter::`scalar deleting destructor'(v129, v19);
          v15 = 0;
          v129 = 0;
        }
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
        {
          v133 = L"OutConnectionContentSetContext::OpenFile";
          v134 = 2001;
          v135 = 4;
          v136 = L"OUTC";
          dbgobj::DbgPrint<unsigned short,FrsStatus>(&v133, L"(Ignored) Failed to stage file: %?", Staging);
        }
        CLEAR_ERROR(&v132);
        Staging = v132;
      }
      else
      {
        v126 = v139;
      }
      v131 = v130;
      if ( Staging )
      {
        v41 = this;
LABEL_96:
        if ( v126 == 1 )
        {
          OutConnectionContentSetContext::AbortStage((OutConnectionContentSetContext *)v41, v15);
          if ( v15 )
          {
            StageWriter::`scalar deleting destructor'(v15, v19);
            v15 = 0;
            v129 = 0;
          }
        }
        goto LABEL_209;
      }
    }
  }
  v42 = (OutConnectionContentSetContext *)v126;
LABEL_88:
  v41 = this;
  if ( !*((_DWORD *)this + 12) )
  {
    v43 = *((_DWORD *)v128 + 38);
    if ( (v43 & 8) != 0 )
    {
      Staging = OutConnectionContentSetContext::GetGhostedFileDataReader(
                  v42,
                  this[7],
                  (const struct ID_RECORD *)v184,
                  v143,
                  v160,
                  &v152);
      v150 = v152;
    }
    else if ( (v43 & 4) != 0 )
    {
      Staging = OutConnectionContentSetContext::GetGhostedFileHeaderReader(
                  v42,
                  this[7],
                  (const struct ID_RECORD *)v184,
                  &v151);
      v16 = v151;
    }
    else if ( (_DWORD)v42 != 2 )
    {
      Staging = OutConnectionContentSetContext::GetReplicaReader(v42, this[7], (const struct ID_RECORD *)v184, 0, &v140);
      v142 = v140;
    }
  }
  if ( Staging )
    goto LABEL_96;
  if ( *((_DWORD *)this + 12) )
  {
LABEL_101:
    if ( v15 )
    {
      OutConnectionContentSetContext::AbortStage((OutConnectionContentSetContext *)v41, v15);
      StageWriter::`scalar deleting destructor'(v15, v44);
      v15 = 0;
      v129 = 0;
    }
    goto LABEL_103;
  }
  if ( v126 != 1 )
  {
    if ( v126 == 2 )
    {
      Staging = StageReader::GetUncompressedFileSize(v131, (unsigned __int64 *)(a5 + 8));
      if ( Staging )
        goto LABEL_209;
      goto LABEL_115;
    }
    v49 = v128;
    if ( v126 != 3 || (v50 = *((_DWORD *)v128 + 38), (v50 & 8) != 0) || (v50 & 4) != 0 )
    {
      v51 = a5;
      goto LABEL_117;
    }
  }
  Staging = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Reader *, __int64))(*(_QWORD *)v142 + 72LL))(
                                  v142,
                                  a5 + 8);
  if ( Staging )
    goto LABEL_209;
  v55 = Settings::GenericDwordSetting::operator()(&Settings::StagingThrottleBytes);
  v51 = a5;
  if ( *(_QWORD *)(a5 + 8) < (unsigned __int64)v55 )
    goto LABEL_116;
  Staging = VolumeManager::AcquireStagingThread(v14, (const struct ShutdownObject *)(this + 4));
  if ( Staging )
    goto LABEL_209;
  v145 = 1;
LABEL_115:
  v51 = a5;
LABEL_116:
  v49 = v128;
LABEL_117:
  if ( v51 )
    *(_QWORD *)v51 = *(_QWORD *)(v51 + 8);
  if ( (*((_BYTE *)v49 + 152) & 0xC) == 0 )
  {
    Rdc::MyFRS_RDC_FILEINFO::ComputeRecursionDepth((Rdc::MyFRS_RDC_FILEINFO *)v51, *(_QWORD *)(v51 + 8));
    v51 = a5;
    if ( !v127
      || (*(_QWORD *)(a5 + 8) & 0xFFFFFFFFFFFFFC00uLL) <= 0x10000
      || (v52 = *(_BYTE *)(a5 + 20) == 0, v127 = 1, v52) )
    {
      v127 = 0;
    }
    v49 = v128;
  }
  if ( *((_DWORD *)this + 12) )
  {
LABEL_209:
    v49 = (ID_UPDATE *)(v41 + 6);
    if ( *((_DWORD *)v41 + 12) )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
      {
        v174 = L"OutConnectionContentSetContext::OpenFile";
        v175 = 2404;
        v176 = 5;
        v177 = L"OUTC";
        dbgobj::DbgPrint<unsigned short,int,FrsStatus>(&v174, v19, v49, Staging);
      }
      goto LABEL_101;
    }
LABEL_146:
    v63 = v131;
LABEL_147:
    v64 = a5;
    goto LABEL_148;
  }
  if ( v126 != 1 )
  {
    v19 = v126 - 2;
    if ( v126 == 2 )
    {
      if ( v127 )
      {
        v72 = this[7];
        v73 = *(unsigned __int8 *)(v51 + 20);
        v74 = (const volatile int *)(*((__int64 (__fastcall **)(char *, unsigned __int64, ID_UPDATE *))this[4] + 5))(
                                      (char *)this + 32,
                                      v19,
                                      v49);
        v75 = v131;
        *((_DWORD *)v131 + 45) = 1;
        v76 = *(void **)(*((_QWORD *)v75 + 12) + 32LL);
        UncompressReader = StageReader::GetUncompressReader(v75);
        Rdc::StagingClosure::StagingClosure(
          (Rdc::StagingClosure *)v194,
          UncompressReader,
          0,
          v76,
          v74,
          v73,
          (const struct __MIDL___MIDL_itf_frstransport_0000_0000_0010 *)(a5 + 28),
          (const struct ID_UPDATE *)v184,
          v72);
        v63 = v131;
        Staging = StageReader::Serialize(v131, (struct Staging::IClosure *)v194);
        v178 = v185;
        v179 = v186;
        v11 = 0;
        v78 = 0;
        if ( !Staging )
        {
          do
          {
            if ( v78 >= 2 )
              break;
            Staging = OutConnectionContentSetContext::GetUpdatedRecord(
                        (OutConnectionContentSetContext *)this,
                        this[7],
                        v128,
                        v78,
                        (struct ID_RECORD *)v184,
                        (unsigned __int64 *)(a5 + 8));
            if ( !Staging )
            {
              if ( (unsigned __int8)GVSN::operator==(&v178, &v185, v49) )
              {
                if ( !HASH::IsNull((HASH *)v189) )
                  goto LABEL_173;
              }
              else
              {
                if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
                {
                  v133 = L"OutConnectionContentSetContext::OpenFile";
                  v134 = 2316;
                  v135 = 5;
                  v136 = L"OUTC";
                  dbgobj::DbgPrint<unsigned short,RdcSimilarityData,HASH>(
                    &v133,
                    L"FILE_IS_STAGED UPDATED record.simData=(%?,%?)",
                    v190,
                    v189);
                }
                v79 = GetCurrentThreadId();
                Staging = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                v80,
                                                9024,
                                                0,
                                                3,
                                                "base\\fs\\remotefs\\frs\\src\\sync\\outconnection.cpp",
                                                "OutConnectionContentSetContext::OpenFile",
                                                2320,
                                                v79,
                                                0);
              }
            }
            ++v78;
          }
          while ( !Staging );
          if ( Staging )
            goto LABEL_177;
LABEL_173:
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
          {
            v133 = L"OutConnectionContentSetContext::OpenFile";
            v134 = 2334;
            v135 = 5;
            v136 = L"OUTC";
            dbgobj::DbgPrint<unsigned short,RdcSimilarityData,HASH>(
              &v133,
              L"FILE_IS_STAGED UPDATED record.simData=(%?,%?)",
              v190,
              v189);
          }
        }
LABEL_177:
        v194[0] = &Staging::IClosure::`vftable';
      }
      else
      {
        *(_BYTE *)(v51 + 20) = 0;
        v70 = v131;
        *((_DWORD *)v131 + 45) = 1;
        Staging = (struct FrsStatus *)(*(__int64 (__fastcall **)(_QWORD, _QWORD, ID_UPDATE *))(**((_QWORD **)v70 + 12)
                                                                                             + 40LL))(
                                        *((_QWORD *)v70 + 12),
                                        0,
                                        v49);
        v71 = operator new(0x10u);
        v143 = (unsigned __int64)v71;
        v63 = 0;
        v130 = 0;
        v19 = (unsigned __int64)&StageSeekReader::`vftable';
        *v71 = &StageSeekReader::`vftable';
        v71[1] = v70;
        *(_QWORD *)(*(_QWORD *)v138 + 320LL) = v71;
      }
      goto LABEL_147;
    }
    if ( v126 == 3 )
    {
      v53 = *((_DWORD *)v49 + 38);
      if ( (v53 & 8) != 0 )
      {
        v152 = 0;
        v54 = v150;
      }
      else if ( (v53 & 4) != 0 )
      {
        v54 = v16;
        v151 = 0;
      }
      else
      {
        *(_BYTE *)(v51 + 20) = 0;
        if ( HASH::IsNull((HASH *)v189) )
        {
          v132 = 0;
          RefCountObject::AddRef((RefCountObject *)this);
          ScopedRef<VolumeManager::ShutdownRestartTask>::Set(&v132, this);
          v56 = (char *)operator new(0x2E8u);
          v150 = (struct Reader *)v56;
          v143 = (unsigned __int64)v56;
          v140 = 0;
          *(_QWORD *)v56 = &SaveHashReader::`vftable';
          v57 = v56 + 8;
          *((_QWORD *)v56 + 1) = 0;
          *((_QWORD *)v56 + 2) = v142;
          *((_DWORD *)v56 + 6) = 1;
          ID_RECORD::ID_RECORD((ID_RECORD *)(v56 + 32), (const struct ID_RECORD *)v184);
          v58 = v132;
          if ( v132 )
          {
            RefCountObject::AddRef(v132);
            v59 = v58;
          }
          else
          {
            v59 = 0;
          }
          ScopedRef<VolumeManager::ShutdownRestartTask>::Set(v57, v59);
          ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v132);
          v54 = v150;
          v49 = v128;
        }
        else
        {
          v54 = v142;
          v140 = 0;
        }
      }
      if ( v54 )
      {
        if ( (unsigned int)ID_UPDATE::IsFileCompressed(v49, (const struct Config::ContentSet *)v12) )
        {
          v143 = (unsigned __int64)operator new(0x90C8u);
          XpressCompressReader::XpressCompressReader((XpressCompressReader *)v143, v54, v60, v61, v118);
          *(_QWORD *)v62 = &XpressNoCompressReader::`vftable';
          *(_DWORD *)(v62 + 37056) = 0;
          *(_QWORD *)(*(_QWORD *)v138 + 320LL) = v62;
        }
        else
        {
          v143 = (unsigned __int64)operator new(0x90C8u);
          v69 = XpressCompressReader::XpressCompressReader((XpressCompressReader *)v143, v54, v67, v68, v118);
          *(_QWORD *)(*(_QWORD *)v138 + 320LL) = v69;
        }
      }
    }
    goto LABEL_146;
  }
  if ( v127 )
  {
    Staging = StageWriter::ReserveSpace(v15, (const unsigned __int64 *)(v51 + 8));
    if ( !Staging )
    {
      v84 = *(unsigned __int8 *)(a5 + 20);
      v85 = (const volatile int *)(*((__int64 (__fastcall **)(char *))this[4] + 5))((char *)this + 32);
      v86 = *(void **)(*((_QWORD *)v15 + 13) + 16LL);
      CompressWriter = StageWriter::GetCompressWriter(v15);
      v88 = v86;
      v89 = v142;
      Rdc::StagingClosure::StagingClosure(
        (Rdc::StagingClosure *)v194,
        v142,
        CompressWriter,
        v88,
        v85,
        v84,
        (const struct __MIDL___MIDL_itf_frstransport_0000_0000_0010 *)(a5 + 28),
        (const struct ID_UPDATE *)v184,
        0);
      Staging = StageWriter::Serialize(v15, (struct Staging::IClosure *)v194);
      v190[0] = v195;
      if ( !Staging )
      {
        v90 = v89;
        v41 = this;
        Staging = OutConnectionContentSetContext::StageFileComplete(
                    (OutConnectionContentSetContext *)this,
                    (struct ID_RECORD *)v184,
                    v90,
                    v15,
                    &v130,
                    &v141);
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
        {
          v133 = L"OutConnectionContentSetContext::OpenFile";
          v134 = 2241;
          v135 = 5;
          v136 = L"OUTC";
          dbgobj::DbgPrint<unsigned short,RdcSimilarityData,HASH>(
            &v133,
            L"WRITE_FILE_TO_STAGE record.simData=(%?,%?)",
            v190,
            v189);
        }
        v63 = v130;
        goto LABEL_196;
      }
      v41 = this;
    }
    OutConnectionContentSetContext::AbortStage((OutConnectionContentSetContext *)v41, v15);
    v63 = v131;
LABEL_196:
    if ( v15 )
    {
      StageWriter::`scalar deleting destructor'(v15, v19);
      v15 = 0;
      v129 = 0;
    }
    if ( v142 )
    {
      close_delete::close<DbIterator<ID_RECORD>>(v142);
      v140 = 0;
    }
    if ( Staging )
    {
      if ( *((_DWORD *)Staging + 1) == 112 )
        ContentSetManager::ReportDiskFull(v41[7], 1);
      CLEAR_ERROR(&v141);
    }
    else
    {
      Staging = v141;
    }
    goto LABEL_205;
  }
  *(_BYTE *)(v51 + 20) = 0;
  v81 = OutConnectionContentSetContext::WriteFileToStage(
          (OutConnectionContentSetContext *)this,
          (struct ID_RECORD *)v184,
          &v130);
  Staging = (struct FrsStatus *)v81;
  if ( v81 )
  {
    if ( *(_DWORD *)(v81 + 4) == 112 )
      ContentSetManager::ReportDiskFull(this[7], 1);
    v63 = v130;
    v15 = v129;
    goto LABEL_147;
  }
  if ( *((_DWORD *)this + 12) )
  {
    v63 = v130;
  }
  else
  {
    v82 = v130;
    *((_DWORD *)v130 + 45) = 1;
    Staging = (struct FrsStatus *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v82 + 12) + 40LL))(
                                    *((_QWORD *)v82 + 12),
                                    0);
    v83 = operator new(0x10u);
    v143 = (unsigned __int64)v83;
    v63 = 0;
    v130 = 0;
    v19 = (unsigned __int64)&StageSeekReader::`vftable';
    *v83 = &StageSeekReader::`vftable';
    v83[1] = v82;
    *(_QWORD *)(*(_QWORD *)v138 + 320LL) = v83;
  }
  v15 = v129;
LABEL_205:
  v64 = a5;
  if ( !Staging && v63 )
    Staging = StageReader::GetUncompressedFileSize(v63, (unsigned __int64 *)a5);
LABEL_148:
  if ( v145 )
    VolumeManager::ReleaseStagingThread(v14);
  v28 = this;
  if ( Staging || *((_DWORD *)this + 12) || *(_QWORD *)(*(_QWORD *)v138 + 320LL) )
    goto LABEL_104;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
  {
    v180 = L"OutConnectionContentSetContext::OpenFile";
    v181 = 2423;
    v182 = 5;
    v183 = L"OUTC";
    dbgobj::DbgPrint<unsigned short,UID,GVSN,unsigned short [261],unsigned __int64,_GUID,FrsStringImpl<unsigned short,char>>(
      (unsigned int)&v180,
      (unsigned int)L"Prepare to serve over RDC uid:%? gvsn:%? fileName:%s fileSize:%d  connId:%? rgName:%?",
      (unsigned int)v184,
      (unsigned int)&v185,
      (__int64)v192,
      v64 + 8,
      (__int64)(this + 8),
      (__int64)this[28] + 72);
  }
  v65 = *(_QWORD *)v138 + 312LL;
  v66 = (const volatile int *)(*((__int64 (__fastcall **)(char *, unsigned __int64, ID_UPDATE *))this[4] + 5))(
                                (char *)this + 32,
                                v19,
                                v49);
  v130 = 0;
  v119 = (struct Rdc::SyncServerState **)v65;
  v45 = a5;
  Staging = Rdc::SyncServerState::CreateSyncServerState(
              (struct OutConnectionContentSetContext *)this,
              v63,
              &v188,
              v66,
              (struct _FRS_RDC_FILEINFO *)a5,
              v119);
  v28 = this;
LABEL_105:
  if ( *((_DWORD *)v28 + 12) )
  {
    v46 = GetCurrentThreadId();
    if ( Staging )
    {
      v48 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                  v47,
                                  9079,
                                  0,
                                  3,
                                  "base\\fs\\remotefs\\frs\\src\\sync\\outconnection.cpp",
                                  "OutConnectionContentSetContext::OpenFile",
                                  2445,
                                  v46,
                                  0);
      Staging = PROPAGATE_ERROR_WITH_NEW_STATUS(Staging, v48);
    }
    else
    {
      Staging = (struct FrsStatus *)FrsStatusList::PushNewError(
                                      v47,
                                      9079,
                                      0,
                                      3,
                                      "base\\fs\\remotefs\\frs\\src\\sync\\outconnection.cpp",
                                      "OutConnectionContentSetContext::OpenFile",
                                      2448,
                                      v46,
                                      0);
      if ( v15 )
      {
        OutConnectionContentSetContext::AbortStage((OutConnectionContentSetContext *)this, v15);
        StageWriter::`scalar deleting destructor'(v15, v91);
        v129 = 0;
      }
    }
    v92 = this;
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v180 = L"OutConnectionContentSetContext::OpenFile";
      v181 = 2460;
      v182 = 4;
      v183 = L"OUTC";
      dbgobj::DbgPrint<unsigned short,UID,GVSN,unsigned short [261],_GUID,FrsStringImpl<unsigned short,char>>(
        (unsigned int)&v180,
        v19,
        (unsigned int)v184,
        (unsigned int)&v185,
        (__int64)v192,
        (__int64)(this + 8),
        (__int64)this[28] + 72);
    }
  }
  else
  {
    v92 = this;
  }
  if ( Staging )
  {
    if ( *((_DWORD *)Staging + 1) == 32 )
      ContentSetManager::LogSharingViolationEvent(v92[7], v184, v193, 2147487952LL, 0);
    v93 = v138;
    v94 = *(Rdc::SyncServerState **)(*(_QWORD *)v138 + 312LL);
    if ( v94 )
      Rdc::SyncServerState::`scalar deleting destructor'(v94, v19);
    *(_QWORD *)(*(_QWORD *)v93 + 312LL) = 0;
    v95 = *(void (__fastcall ****)(_QWORD, __int64))(*(_QWORD *)v93 + 320LL);
    if ( v95 )
      (**v95)(v95, 1);
    *(_QWORD *)(*(_QWORD *)v93 + 320LL) = 0;
    v96 = g_MonitorContext;
    EnterCriticalSection((LPCRITICAL_SECTION)g_MonitorContext + 15);
    *((_DWORD *)v96 + 148) = 1;
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      v180 = L"OutConnectionContentSetContext::OpenFile";
      v181 = 2521;
      v182 = 5;
      v183 = L"OUTC";
      dbgobj::DbgPrint<unsigned short>(&v180, L"Update syncInfoHistory");
    }
    v97 = this;
    if ( !*((_DWORD *)this + 12) )
    {
      v98 = v157;
      ++*((_DWORD *)v157 + 46);
LABEL_252:
      StateHistory::Update((struct MonitorContext *)((char *)g_MonitorContext + 536), v98);
    }
  }
  else
  {
    if ( v45 )
      v99 = *(struct FrsStatus **)v45;
    else
      v99 = 0;
    v141 = v99;
    if ( !v99 )
    {
      if ( v45 )
        v100 = *(struct FrsStatus **)(v45 + 8);
      else
        v100 = v156;
      v141 = v100;
    }
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      *(_QWORD *)&v178 = L"OutConnectionContentSetContext::OpenFile";
      *((_QWORD *)&v178 + 1) = 0x4000009BFLL;
      v179 = L"OUTC";
      dbgobj::DbgPrint<unsigned short,UID,GVSN,unsigned short [261],unsigned __int64,_GUID,FrsStringImpl<unsigned short,char>>(
        (unsigned int)&v178,
        (unsigned int)L"Sent file uid:%? gvsn:%? name:%? fileSize:%d connId:%? rgName:%?",
        (unsigned int)v184,
        (unsigned int)&v185,
        (__int64)v192,
        (__int64)&v141,
        (__int64)(v92 + 8),
        (__int64)v92[28] + 72);
    }
    v101 = g_MonitorContext;
    EnterCriticalSection((LPCRITICAL_SECTION)g_MonitorContext + 15);
    *((_DWORD *)v101 + 148) = 1;
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      *(_QWORD *)&v178 = L"OutConnectionContentSetContext::OpenFile";
      *((_QWORD *)&v178 + 1) = 0x5000009C7LL;
      v179 = L"OUTC";
      dbgobj::DbgPrint<unsigned short>(&v178, L"Update syncInfoHistory");
    }
    v97 = this;
    if ( !*((_DWORD *)this + 12) )
    {
      v98 = v157;
      ++*((_DWORD *)v157 + 43);
      goto LABEL_252;
    }
  }
  v102 = (struct _RTL_CRITICAL_SECTION *)g_MonitorContext;
  *((_DWORD *)g_MonitorContext + 148) = 0;
  LeaveCriticalSection(v102 + 15);
  if ( v12 )
  {
    v103 = (const unsigned __int16 *)(*(_QWORD *)v155 + 18LL);
    v104 = GVSN::ToString(v187, &v180);
    v105 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v104);
    v106 = GVSN::ToString(v184, &v178);
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v106);
    v107 = Config::StringParam::Get((Config::StringParam *)(v12 + 30));
    FrsEvent::Audit(
      Staging == 0,
      0x40001B5Au,
      (const unsigned __int16 *)(v12[77] + 18LL),
      v107,
      v109,
      v192,
      v108,
      v105,
      v103,
      v124);
    std::wstring::~wstring(&v178);
    std::wstring::~wstring(&v180);
  }
  if ( !Staging )
  {
    v110 = v128;
    v111 = *((_DWORD *)v128 + 38);
    v112 = v128;
    v113 = v184;
    v114 = 5;
    do
    {
      *(_OWORD *)v112 = *v113;
      *((_OWORD *)v112 + 1) = v113[1];
      *((_OWORD *)v112 + 2) = v113[2];
      *((_OWORD *)v112 + 3) = v113[3];
      *((_OWORD *)v112 + 4) = v113[4];
      *((_OWORD *)v112 + 5) = v113[5];
      *((_OWORD *)v112 + 6) = v113[6];
      v112 = (ID_UPDATE *)((char *)v112 + 128);
      *((_OWORD *)v112 - 1) = v113[7];
      v113 += 8;
      --v114;
    }
    while ( v114 );
    *(_OWORD *)v112 = *v113;
    *((_OWORD *)v112 + 1) = v113[1];
    *((_QWORD *)v112 + 4) = *((_QWORD *)v113 + 4);
    *((_DWORD *)v110 + 38) ^= ((unsigned __int8)v111
                             ^ (unsigned __int8)*((_DWORD *)v110 + 38))
                            & 4
                            ^ ((unsigned __int8)v111
                             ^ *((_BYTE *)v110 + 152)
                             ^ ((unsigned __int8)v111
                              ^ (unsigned __int8)*((_DWORD *)v110 + 38))
                             & 4)
                            & 8;
  }
  if ( v14 )
  {
    if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugVolumeManagerRefCount)
      && g_DebugLog
      && LODWORD(g_DebugLog[1].LockSemaphore)
      && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      *(_QWORD *)&v178 = L"OutConnectionContentSetContext::OpenFile";
      *((_QWORD *)&v178 + 1) = 0x500000A0ELL;
      v179 = L"OUTC";
      v155 = v14;
      dbgobj::DbgPrint<unsigned short,unsigned __int64>(
        &v178,
        L"[VMREF] Release reference to volume manager. ptr:%p",
        &v155);
    }
    ScopedRef<VolumeManager::ShutdownRestartTask>::Set(&v149, 0);
  }
  if ( v146 )
    DfsrZeroSignalSemaphore::ReleaseRefCount((DfsrZeroSignalSemaphore *)(v97 + 14));
  if ( Staging )
  {
    v115 = GetCurrentThreadId();
    v11 = FrsStatusList::PushNewError(
            v116,
            *((unsigned int *)Staging + 1),
            *((unsigned int *)Staging + 2),
            *(unsigned int *)Staging,
            "base\\fs\\remotefs\\frs\\src\\sync\\outconnection.cpp",
            "OutConnectionContentSetContext::OpenFile",
            2580,
            v115,
            Staging);
  }
  scoped_any<Rdc::RDCIndexReader *,close_delete,null_t,0>::~scoped_any<Rdc::RDCIndexReader *,close_delete,null_t,0>(&v151);
  scoped_any<SimilarityTraitsTableDisk::TraitsDumpStateDisk *,close_delete,null_t,0>::~scoped_any<SimilarityTraitsTableDisk::TraitsDumpStateDisk *,close_delete,null_t,0>(&v152);
  scoped_any<Rdc::RDCIndexReader *,close_delete,null_t,0>::~scoped_any<Rdc::RDCIndexReader *,close_delete,null_t,0>(&v140);
  scoped_any<StageWriter *,close_delete,null_t,0>::~scoped_any<StageWriter *,close_delete,null_t,0>(&v129);
  scoped_any<Rdc::RDCIndexReader *,close_delete,null_t,0>::~scoped_any<Rdc::RDCIndexReader *,close_delete,null_t,0>(&v130);
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v149);
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v153);
  ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v161);
  ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v154);
  return v11;
}

```

## disassembly

```asm
0x140172518  push    rbp
0x14017251a  push    rbx
0x14017251b  push    rsi
0x14017251c  push    rdi
0x14017251d  push    r12
0x14017251f  push    r13
0x140172521  push    r14
0x140172523  push    r15
0x140172525  lea     rbp, [rsp-6F8h]
0x14017252d  sub     rsp, 7F8h
0x140172534  mov     rax, cs:__security_cookie
0x14017253b  xor     rax, rsp
0x14017253e  mov     [rbp+730h+var_50], rax
0x140172545  mov     [rbp+730h+var_6E0], r9
0x140172549  mov     [rsp+830h+var_7C0], r8
0x14017254e  mov     r12, rcx
0x140172551  mov     [rsp+830h+var_7D8], rcx
0x140172556  mov     [rsp+830h+var_7C8], edx
0x14017255a  mov     rax, [rbp+730h+arg_20]
0x140172561  mov     [rsp+830h+var_7E0], rax
0x140172566  mov     rax, [rbp+730h+arg_28]
0x14017256d  mov     [rbp+730h+var_778], rax
0x140172571  mov     rax, [rbp+730h+arg_30]
0x140172578  mov     [rbp+730h+var_750], rax
0x14017257c  mov     rax, [rbp+730h+arg_38]
0x140172583  mov     [rbp+730h+var_6D8], rax
0x140172587  mov     rax, [rbp+730h+arg_40]
0x14017258e  mov     [rbp+730h+var_6F0], rax
0x140172592  mov     rax, [rbp+730h+arg_48]
0x140172599  mov     [rbp+730h+var_700], rax
0x14017259d  xor     r13d, r13d
0x1401725a0  mov     [rbp+730h+var_760], r13
0x1401725a4  mov     r15d, r13d
0x1401725a7  mov     [rbp+730h+var_708], r13
0x1401725ab  mov     [rbp+730h+var_6D0], r13
0x1401725af  mov     edi, r13d
0x1401725b2  mov     [rbp+730h+var_710], r13
0x1401725b6  mov     r14d, r13d
0x1401725b9  mov     [rbp+730h+var_730], r13
0x1401725bd  mov     eax, r13d
0x1401725c0  mov     [rbp+730h+var_7A8], rax
0x1401725c4  mov     [rbp+730h+var_7B0], rax
0x1401725c8  mov     ebx, r13d
0x1401725cb  mov     [rsp+830h+var_7B8], rbx
0x1401725d0  mov     [rbp+730h+var_758], rax
0x1401725d4  mov     [rbp+730h+var_768], rax
0x1401725d8  lea     rcx, [rbp+730h+var_620]; this
0x1401725df  call    ??0ID_RECORD@@QEAA@XZ; ID_RECORD::ID_RECORD(void)
0x1401725e4  lea     eax, [r13+3]
0x1401725e8  mov     dword ptr [rsp+830h+var_7D0], eax
0x1401725ec  mov     [rbp+730h+var_770], eax
0x1401725ef  mov     [rbp+730h+var_748], r13d
0x1401725f3  mov     [rbp+730h+var_780], r13d
0x1401725f7  mov     [rbp+730h+var_73C], r13d
0x1401725fb  mov     [rbp+730h+var_6F8], r13
0x1401725ff  mov     eax, r13d
0x140172602  mov     [rbp+730h+var_728], rax
0x140172606  mov     [rbp+730h+var_718], rax
0x14017260a  mov     esi, r13d
0x14017260d  mov     [rbp+730h+var_720], r13
0x140172611  mov     [rbp+730h+var_744], r13d
0x140172615  mov     [rbp+730h+var_740], 1
0x14017261c  mov     rcx, [rbp+730h+var_778]
0x140172620  mov     rax, [rcx]
0x140172623  mov     [rax+140h], r13
0x14017262a  mov     rax, [rcx]
0x14017262d  mov     [rax+138h], r13
0x140172634  mov     rcx, r12; this
0x140172637  call    ?MarkContextInUse@OutConnectionContentSetContext@@AEAAPEAVFrsStatus@@XZ; OutConnectionContentSetContext::MarkContextInUse(void)
0x14017263c  mov     r12, rax
0x14017263f  mov     rax, [rsp+830h+var_7D8]
0x140172644  add     rax, 38h ; '8'
0x140172648  mov     [rbp+730h+var_738], rax
0x14017264c  test    r12, r12
0x14017264f  jz      short loc_140172657
0x140172651  mov     [rbp+730h+var_740], r13d
0x140172655  jmp     short loc_140172695
0x140172657  mov     rcx, [rax]
0x14017265a  add     rcx, 460h
0x140172661  call    ?Get@?$ConfigInstance@VContentSet@Config@@@Config@@QEAAPEAVContentSet@2@XZ; Config::ConfigInstance<Config::ContentSet>::Get(void)
0x140172666  mov     rdx, rax
0x140172669  lea     rcx, [rbp+730h+var_708]
0x14017266d  call    ?Set@?$ScopedRef@VContentSet@Config@@@@AEAAXPEAVContentSet@Config@@@Z; ScopedRef<Config::ContentSet>::Set(Config::ContentSet *)
0x140172672  lea     rdx, [rbp+730h+var_710]
0x140172676  mov     rcx, [rbp+730h+var_738]
0x14017267a  mov     rcx, [rcx]
0x14017267d  call    ?GetStaging@ContentSetManager@@QEAAPEAVFrsStatus@@AEAV?$ScopedRef@VStaging@@@@@Z; ContentSetManager::GetStaging(ScopedRef<Staging> &)
0x140172682  mov     r12, rax
0x140172685  mov     rax, [rbp+730h+var_738]
0x140172689  mov     [rbp+730h+var_738], rax
0x14017268d  mov     r15, [rbp+730h+var_708]
0x140172691  mov     rdi, [rbp+730h+var_710]
0x140172695  lea     rdx, aOutconnectionc_35; "OutConnectionContentSetContext::OpenFil"...
0x14017269c  lea     r8, aOutc; "OUTC"
0x1401726a3  mov     rcx, [rsp+830h+var_7C0]
0x1401726a8  test    byte ptr [rcx+98h], 8
0x1401726af  jz      short loc_1401726F6
0x1401726b1  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401726b8  test    rax, rax
0x1401726bb  jz      short loc_1401726F6
0x1401726bd  cmp     [rax+40h], r13d
0x1401726c1  jz      short loc_1401726F6
0x1401726c3  cmp     dword ptr [rax+38h], 5
0x1401726c7  jl      short loc_1401726F6
0x1401726c9  mov     [rbp+730h+var_6C8], rdx
0x1401726cd  mov     [rbp+730h+var_6C0], 6E9h
0x1401726d4  mov     [rbp+730h+var_6BC], 5
0x1401726db  mov     [rbp+730h+var_6B8], r8
0x1401726df  lea     r9, [rcx+18h]
0x1401726e3  mov     r8, rcx
0x1401726e6  lea     rdx, aReceivedReques; "Received request for ghosted data. uid:"...
0x1401726ed  lea     rcx, [rbp+730h+var_6C8]
0x1401726f1  call    ??$DbgPrint@GVUID@@VGVSN@@@dbgobj@@QEAA_KPEBGAEBVUID@@AEBVGVSN@@@Z; dbgobj::DbgPrint<ushort,UID,GVSN>(ushort const *,UID const &,GVSN const &)
0x1401726f6  test    r12, r12
0x1401726f9  jnz     loc_1401728CB
0x1401726ff  lea     rdx, [rbp+730h+var_730]
0x140172703  mov     rax, [rbp+730h+var_738]
0x140172707  mov     rcx, [rax]
0x14017270a  call    ?GetVolumeManager@ContentSetManager@@QEAAPEAVFrsStatus@@AEAV?$ScopedRef@VVolumeManager@@@@@Z; ContentSetManager::GetVolumeManager(ScopedRef<VolumeManager> &)
0x14017270f  mov     r12, rax
0x140172712  test    rax, rax
0x140172715  jnz     loc_1401728C7
0x14017271b  lea     rcx, ?DebugVolumeManagerRefCount@Settings@@3VCDebugVolumeManagerRefCount@1@A; Settings::CDebugVolumeManagerRefCount Settings::DebugVolumeManagerRefCount
0x140172722  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x140172727  mov     r14, [rbp+730h+var_730]
0x14017272b  test    eax, eax
0x14017272d  jz      short loc_140172792
0x14017272f  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140172736  test    rax, rax
0x140172739  jz      short loc_140172792
0x14017273b  cmp     [rax+40h], r13d
0x14017273f  jz      short loc_140172792
0x140172741  cmp     dword ptr [rax+38h], 5
0x140172745  jl      short loc_140172792
0x140172747  lea     rax, aOutconnectionc_35; "OutConnectionContentSetContext::OpenFil"...
0x14017274e  mov     [rbp+730h+var_6B0], rax
0x140172755  mov     [rbp+730h+var_6A8], 6F7h
0x14017275f  mov     [rbp+730h+var_6A4], 5
0x140172769  lea     rax, aOutc; "OUTC"
0x140172770  mov     [rbp+730h+var_6A0], rax
0x140172777  mov     [rbp+730h+var_6E8], r14
0x14017277b  lea     r8, [rbp+730h+var_6E8]
0x14017277f  lea     rdx, aVmrefAddedRefe; "[VMREF] Added reference to volume manag"...
0x140172786  lea     rcx, [rbp+730h+var_6B0]
0x14017278d  call    ??$DbgPrint@G_K@dbgobj@@QEAA_KPEBGAEB_K@Z; dbgobj::DbgPrint<ushort,unsigned __int64>(ushort const *,unsigned __int64 const &)
0x140172792  mov     rax, [rsp+830h+var_7D8]
0x140172797  cmp     [rax+30h], r13d
0x14017279b  jnz     loc_1401728CB
0x1401727a1  mov     rcx, [rsp+830h+var_7E0]
0x1401727a6  test    rcx, rcx
0x1401727a9  jz      short loc_1401727B5
0x1401727ab  lea     rdx, [rcx+8]
0x1401727af  mov     [rbp+730h+var_7A0], rdx
0x1401727b3  jmp     short loc_1401727C1
0x1401727b5  lea     rdx, [rbp+730h+var_6F8]
0x1401727b9  add     rcx, 8
0x1401727bd  mov     [rbp+730h+var_7A0], rcx
0x1401727c1  mov     [rsp+830h+var_808], rdx; unsigned __int64 *
0x1401727c6  lea     rcx, [rbp+730h+var_620]
0x1401727cd  mov     [rsp+830h+var_810], rcx; struct ID_RECORD *
0x1401727d2  xor     r9d, r9d; int
0x1401727d5  mov     r8, [rsp+830h+var_7C0]; struct ID_UPDATE *
0x1401727da  mov     rcx, [rbp+730h+var_738]
0x1401727de  mov     rdx, [rcx]; struct ContentSetManager *
0x1401727e1  mov     rcx, rax; this
0x1401727e4  call    ?GetUpdatedRecord@OutConnectionContentSetContext@@AEAAPEAVFrsStatus@@PEAVContentSetManager@@AEBVID_UPDATE@@HAEAVID_RECORD@@AEA_K@Z; OutConnectionContentSetContext::GetUpdatedRecord(ContentSetManager *,ID_UPDATE const &,int,ID_RECORD &,unsigned __int64 &)
0x1401727e9  mov     r12, rax
0x1401727ec  test    rax, rax
0x1401727ef  jnz     loc_1401728CB
0x1401727f5  mov     rax, [rsp+830h+var_7E0]
0x1401727fa  test    rax, rax
0x1401727fd  jz      loc_1401728CB
0x140172803  mov     rcx, [rsp+830h+var_7C0]
0x140172808  test    byte ptr [rcx+98h], 4
0x14017280f  jnz     loc_1401728CB
0x140172815  mov     rdx, [rbp+730h+var_7A0]
0x140172819  mov     rdx, [rdx]; unsigned __int64
0x14017281c  mov     rcx, rax; this
0x14017281f  call    ?ComputeRecursionDepth@MyFRS_RDC_FILEINFO@Rdc@@QEAAX_K@Z; Rdc::MyFRS_RDC_FILEINFO::ComputeRecursionDepth(unsigned __int64)
0x140172824  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14017282b  test    rax, rax
0x14017282e  jz      short loc_14017288F
0x140172830  cmp     [rax+40h], r13d
0x140172834  jz      short loc_14017288F
0x140172836  cmp     dword ptr [rax+38h], 5
0x14017283a  jl      short loc_14017288F
0x14017283c  lea     rax, aOutconnectionc_35; "OutConnectionContentSetContext::OpenFil"...
0x140172843  mov     [rbp+730h+var_698], rax
0x14017284a  mov     [rbp+730h+var_690], 70Ah
0x140172854  mov     [rbp+730h+var_68C], 5
0x14017285e  lea     rax, aOutc; "OUTC"
0x140172865  mov     [rbp+730h+var_688], rax
0x14017286c  mov     rax, [rsp+830h+var_7E0]
0x140172871  add     rax, 14h
0x140172875  mov     [rsp+830h+var_810], rax
0x14017287a  mov     r9, [rbp+730h+var_7A0]
0x14017287e  lea     r8, [rsp+830h+var_7C8]
0x140172883  lea     rcx, [rbp+730h+var_698]
0x14017288a  call    ??$DbgPrint@GH_KE@dbgobj@@QEAA_KPEBGAEBHAEB_KAEBE@Z; dbgobj::DbgPrint<ushort,int,unsigned __int64,uchar>(ushort const *,int const &,unsigned __int64 const &,uchar const &)
0x14017288f  cmp     [rsp+830h+var_7C8], r13d
0x140172894  jz      short loc_1401728C0
0x140172896  mov     rax, [rbp+730h+var_7A0]
0x14017289a  mov     rax, [rax]
0x14017289d  and     rax, 0FFFFFFFFFFFFFC00h
0x1401728a3  cmp     rax, 10000h
0x1401728a9  jbe     short loc_1401728C0
0x1401728ab  mov     rax, [rsp+830h+var_7E0]
0x1401728b0  cmp     [rax+14h], r13b
0x1401728b4  jbe     short loc_1401728C0
0x1401728b6  mov     [rsp+830h+var_7C8], 1
0x1401728be  jmp     short loc_1401728CB
0x1401728c0  mov     [rsp+830h+var_7C8], r13d
0x1401728c5  jmp     short loc_1401728CB
0x1401728c7  mov     r14, [rbp+730h+var_730]
0x1401728cb  test    [rbp+730h+var_588], 1
0x1401728d2  jz      loc_140172E2B
0x1401728d8  test    r12, r12
0x1401728db  jnz     loc_1401737E6
0x1401728e1  mov     r10, [rsp+830h+var_7C0]
0x1401728e6  test    byte ptr [r10+98h], 8
0x1401728ee  jz      loc_1401729B6
0x1401728f4  lea     rcx, [r10+18h]
0x1401728f8  lea     rdx, [rbp+730h+var_608]
0x1401728ff  call    ??8GVSN@@QEBA_NAEBV0@@Z; GVSN::operator==(GVSN const &)
0x140172904  test    al, al
0x140172906  jnz     loc_1401729B6
0x14017290c  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140172913  test    rax, rax
0x140172916  jz      short loc_140172963
0x140172918  cmp     [rax+40h], r13d
0x14017291c  jz      short loc_140172963
0x14017291e  cmp     dword ptr [rax+38h], 3
0x140172922  jl      short loc_140172963
0x140172924  lea     rax, aOutconnectionc_35; "OutConnectionContentSetContext::OpenFil"...
0x14017292b  mov     [rbp+730h+var_798], rax
0x14017292f  mov     [rbp+730h+var_790], 72Ah
0x140172936  mov     [rbp+730h+var_78C], 3
0x14017293d  lea     rax, aOutc; "OUTC"
0x140172944  mov     [rbp+730h+var_788], rax
0x140172948  lea     rax, [rbp+730h+var_608]
0x14017294f  mov     [rsp+830h+var_810], rax
0x140172954  mov     r9, rcx
0x140172957  mov     r8, r10
0x14017295a  lea     rcx, [rbp+730h+var_798]
0x14017295e  call    ??$DbgPrint@GVUID@@VGVSN@@V2@@dbgobj@@QEAA_KPEBGAEBVUID@@AEBVGVSN@@2@Z; dbgobj::DbgPrint<ushort,UID,GVSN,GVSN>(ushort const *,UID const &,GVSN const &,GVSN const &)
0x140172963  call    cs:__imp_GetCurrentThreadId
0x14017296a  nop     dword ptr [rax+rax+00h]
0x14017296f  mov     [rsp+830h+var_7F0], r13
0x140172974  mov     dword ptr [rsp+830h+var_7F8], eax
0x140172978  mov     dword ptr [rsp+830h+var_800], 735h
0x140172980  mov     edx, 2345h
0x140172985  lea     rsi, aOutconnectionc_22; "OutConnectionContentSetContext::OpenFil"...
0x14017298c  mov     [rsp+830h+var_808], rsi
0x140172991  lea     rax, aBaseFsRemotefs_21; "base\\fs\\remotefs\\frs\\src\\sync\\out"...
0x140172998  xor     r8d, r8d
0x14017299b  lea     r9d, [r8+3]
0x14017299f  mov     [rsp+830h+var_810], rax
0x1401729a4  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401729a9  mov     r12, rax
0x1401729ac  mov     rcx, [rsp+830h+var_7D8]
0x1401729b1  jmp     loc_140172E37
0x1401729b6  lea     rcx, [rbp+730h+var_620]; this
0x1401729bd  call    ?Alive@ID_RECORD@@QEBAHXZ; ID_RECORD::Alive(void)
0x1401729c2  test    eax, eax
0x1401729c4  jnz     short loc_140172A21
0x1401729c6  call    cs:__imp_GetCurrentThreadId
0x1401729cd  nop     dword ptr [rax+rax+00h]
0x1401729d2  mov     [rsp+830h+var_7F0], r13
0x1401729d7  mov     dword ptr [rsp+830h+var_7F8], eax
0x1401729db  mov     dword ptr [rsp+830h+var_800], 740h
0x1401729e3  lea     rax, aOutconnectionc_22; "OutConnectionContentSetContext::OpenFil"...
0x1401729ea  mov     [rsp+830h+var_808], rax
0x1401729ef  lea     rax, aBaseFsRemotefs_21; "base\\fs\\remotefs\\frs\\src\\sync\\out"...
0x1401729f6  mov     [rsp+830h+var_810], rax
0x1401729fb  mov     eax, 1
0x140172a00  mov     r9d, eax
0x140172a03  mov     r8d, eax
0x140172a06  mov     edx, 0AAh
0x140172a0b  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140172a10  mov     r12, rax
0x140172a13  test    rax, rax
0x140172a16  jnz     loc_1401737E6
0x140172a1c  mov     r10, [rsp+830h+var_7C0]
0x140172a21  mov     edx, [r10+98h]
0x140172a28  test    dl, 0Ch
0x140172a2b  jz      short loc_140172A66
0x140172a2d  mov     rax, [rsp+830h+var_7D8]
0x140172a32  mov     rcx, [rax+38h]; this
0x140172a36  call    ?IsGhosted@ContentSetManager@@QEAAHXZ; ContentSetManager::IsGhosted(void)
0x140172a3b  test    eax, eax
0x140172a3d  jz      short loc_140172A66
0x140172a3f  call    cs:__imp_GetCurrentThreadId
0x140172a46  nop     dword ptr [rax+rax+00h]
0x140172a4b  mov     [rsp+830h+var_7F0], r13
0x140172a50  mov     dword ptr [rsp+830h+var_7F8], eax
0x140172a54  mov     dword ptr [rsp+830h+var_800], 74Bh
0x140172a5c  mov     edx, 245Dh
0x140172a61  jmp     loc_140172985
0x140172a66  mov     rax, [rsp+830h+var_7D8]
0x140172a6b  cmp     [rax+30h], r13d
  ... truncated ...
```
