# VIDMM_GLOBAL::CreateOneAllocation(VIDMM_DEVICE *,ulong,unsigned __int64,unsigned __int64,ulong,_DXGK_PAGESIZE,_DXGK_PAGESIZE,ulong,ulong,ulong,_D3DDDI_SEGMENTPREFERENCE,_DXGK_ALLOCATIONINFOFLAGS,_DXGK_ALLOCATIONINFOFLAGS2,DXGADAPTERALLOCATION const *,void *,void *,void *,void *,ulong,uchar,void *,VIDMM_PAGE_TABLE_BASE *,VIDMM_CROSSADAPTER_ALLOC * *,VIDMM_FENCE_STORAGE_PAGE *,VIDMM_GLOBAL_ALLOC * *,uchar *)

- ea: `0x1400b4cd8`
- end: `0x1400b6f62`
- name: `?CreateOneAllocation@VIDMM_GLOBAL@@QEAAJPEAVVIDMM_DEVICE@@K_K1KW4_DXGK_PAGESIZE@@2KKKU_D3DDDI_SEGMENTPREFERENCE@@U_DXGK_ALLOCATIONINFOFLAGS@@U_DXGK_ALLOCATIONINFOFLAGS2@@PEBVDXGADAPTERALLOCATION@@PEAX777KE7PEAVVIDMM_PAGE_TABLE_BASE@@PEAPEAUVIDMM_CROSSADAPTER_ALLOC@@PEAVVIDMM_FENCE_STORAGE_PAGE@@PEAPEAUVIDMM_GLOBAL_ALLOC@@PEAE@Z`
- size: `8842`
- prototype: ``
- caller_count: `5`
- callee_count: `32`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14002ed90`
- `0x1400bfce0`
- `0x1400c1cdc`
- `0x1400f18cc`
- `0x1400f2168`

## callees

- `0x140003490`
- `0x140004268`
- `0x14002c5d0`
- `0x14002dbd0`
- `0x14002e2ac`
- `0x14002e6c0`
- `0x14002e8f8`
- `0x14002ed58`
- `0x140030578`
- `0x140030bd0`
- `0x140038b2c`
- `0x1400475f8`
- `0x140059030`
- `0x140059380`
- `0x1400b4cd8`
- `0x1400be9ec`
- `0x1400bf03c`
- `0x1400c1108`
- `0x1400e8db0`
- `0x1400f4524`
- `0x14010ac5c`
- `0x14010aeb4`
- `0x14010cd20`
- `0x14010ea78`
- `0x14010ee94`
- `0x14010efbc`
- `0x14010f010`
- `0x140112444`
- `0x140119e10`
- `0x14011c214`
- `0x140127dd0`
- `0x14012a910`

## import_xrefs

- `ntoskrnl!PsGetProcessWow64Process` at `0x1400b4ff6`
- `ntoskrnl!PsGetProcessWow64Process` at `0x1400b4ff6`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400b6b57`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400b6b57`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400b4fe7`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400b4fe7`
- `watchdog!WdLogSingleEntry3` at `0x1400b6191`
- `watchdog!WdLogSingleEntry3` at `0x1400b680f`
- `watchdog!WdLogSingleEntry3` at `0x1400b6191`
- `watchdog!WdLogSingleEntry3` at `0x1400b680f`
- `watchdog!WdLogSingleEntry4` at `0x1400b6d0f`
- `watchdog!WdLogSingleEntry4` at `0x1400b6d0f`
- `watchdog!WdLogSingleEntry2` at `0x1400b5a9d`
- `watchdog!WdLogSingleEntry2` at `0x1400b6136`
- `watchdog!WdLogSingleEntry2` at `0x1400b6162`
- `watchdog!WdLogSingleEntry2` at `0x1400b5a9d`
- `watchdog!WdLogSingleEntry2` at `0x1400b6136`
- `watchdog!WdLogSingleEntry2` at `0x1400b6162`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b4e59`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b4e82`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b4ec3`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b6cd7`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b4e59`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b4e82`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b4ec3`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b6cd7`
- `watchdog!WdLogSingleEntry5` at `0x1400b6760`
- `watchdog!WdLogSingleEntry5` at `0x1400b6e99`
- `watchdog!WdLogSingleEntry5` at `0x1400b6760`
- `watchdog!WdLogSingleEntry5` at `0x1400b6e99`
- `watchdog!WdLogSingleEntry0` at `0x1400b4f21`
- `watchdog!WdLogSingleEntry0` at `0x1400b5075`
- `watchdog!WdLogSingleEntry0` at `0x1400b5097`
- `watchdog!WdLogSingleEntry0` at `0x1400b50d2`
- `watchdog!WdLogSingleEntry0` at `0x1400b5152`
- `watchdog!WdLogSingleEntry0` at `0x1400b5192`
- `watchdog!WdLogSingleEntry0` at `0x1400b51bf`
- `watchdog!WdLogSingleEntry0` at `0x1400b51e5`
- `watchdog!WdLogSingleEntry0` at `0x1400b5214`
- `watchdog!WdLogSingleEntry0` at `0x1400b5270`
- `watchdog!WdLogSingleEntry0` at `0x1400b52a2`
- `watchdog!WdLogSingleEntry0` at `0x1400b52d1`
- `watchdog!WdLogSingleEntry0` at `0x1400b5324`
- `watchdog!WdLogSingleEntry0` at `0x1400b534d`
- `watchdog!WdLogSingleEntry0` at `0x1400b537b`
- `watchdog!WdLogSingleEntry0` at `0x1400b53bc`
- `watchdog!WdLogSingleEntry0` at `0x1400b53ec`
- `watchdog!WdLogSingleEntry0` at `0x1400b5448`
- `watchdog!WdLogSingleEntry0` at `0x1400b549d`
- `watchdog!WdLogSingleEntry0` at `0x1400b54d1`
- `watchdog!WdLogSingleEntry0` at `0x1400b550a`
- `watchdog!WdLogSingleEntry0` at `0x1400b5553`
- `watchdog!WdLogSingleEntry0` at `0x1400b5582`
- `watchdog!WdLogSingleEntry0` at `0x1400b55d1`
- `watchdog!WdLogSingleEntry0` at `0x1400b560e`
- `watchdog!WdLogSingleEntry0` at `0x1400b5650`
- `watchdog!WdLogSingleEntry0` at `0x1400b56b7`
- `watchdog!WdLogSingleEntry0` at `0x1400b573a`
- `watchdog!WdLogSingleEntry0` at `0x1400b5793`
- `watchdog!WdLogSingleEntry0` at `0x1400b57c4`
- `watchdog!WdLogSingleEntry0` at `0x1400b57f0`
- `watchdog!WdLogSingleEntry0` at `0x1400b581a`
- `watchdog!WdLogSingleEntry0` at `0x1400b5849`
- `watchdog!WdLogSingleEntry0` at `0x1400b5998`
- `watchdog!WdLogSingleEntry0` at `0x1400b5bc5`
- `watchdog!WdLogSingleEntry0` at `0x1400b5c69`
- `watchdog!WdLogSingleEntry0` at `0x1400b5cde`
- `watchdog!WdLogSingleEntry0` at `0x1400b5e6c`
- `watchdog!WdLogSingleEntry0` at `0x1400b60b4`
- `watchdog!WdLogSingleEntry0` at `0x1400b6ebb`
- `watchdog!WdLogSingleEntry0` at `0x1400b6f03`
- `watchdog!WdLogSingleEntry0` at `0x1400b4f21`
- `watchdog!WdLogSingleEntry0` at `0x1400b5075`
- `watchdog!WdLogSingleEntry0` at `0x1400b5097`
- `watchdog!WdLogSingleEntry0` at `0x1400b50d2`
- `watchdog!WdLogSingleEntry0` at `0x1400b5152`
- `watchdog!WdLogSingleEntry0` at `0x1400b5192`
- `watchdog!WdLogSingleEntry0` at `0x1400b51bf`
- `watchdog!WdLogSingleEntry0` at `0x1400b51e5`
- `watchdog!WdLogSingleEntry0` at `0x1400b5214`
- `watchdog!WdLogSingleEntry0` at `0x1400b5270`
- `watchdog!WdLogSingleEntry0` at `0x1400b52a2`
- `watchdog!WdLogSingleEntry0` at `0x1400b52d1`
- `watchdog!WdLogSingleEntry0` at `0x1400b5324`
- `watchdog!WdLogSingleEntry0` at `0x1400b534d`
- `watchdog!WdLogSingleEntry0` at `0x1400b537b`
- `watchdog!WdLogSingleEntry0` at `0x1400b53bc`
- `watchdog!WdLogSingleEntry0` at `0x1400b53ec`
- `watchdog!WdLogSingleEntry0` at `0x1400b5448`
- `watchdog!WdLogSingleEntry0` at `0x1400b549d`
- `watchdog!WdLogSingleEntry0` at `0x1400b54d1`
- `watchdog!WdLogSingleEntry0` at `0x1400b550a`
- `watchdog!WdLogSingleEntry0` at `0x1400b5553`
- `watchdog!WdLogSingleEntry0` at `0x1400b5582`
- `watchdog!WdLogSingleEntry0` at `0x1400b55d1`
- `watchdog!WdLogSingleEntry0` at `0x1400b560e`
- `watchdog!WdLogSingleEntry0` at `0x1400b5650`
- `watchdog!WdLogSingleEntry0` at `0x1400b56b7`
- `watchdog!WdLogSingleEntry0` at `0x1400b573a`
- `watchdog!WdLogSingleEntry0` at `0x1400b5793`
- `watchdog!WdLogSingleEntry0` at `0x1400b57c4`
- `watchdog!WdLogSingleEntry0` at `0x1400b57f0`
- `watchdog!WdLogSingleEntry0` at `0x1400b581a`
- `watchdog!WdLogSingleEntry0` at `0x1400b5849`
- `watchdog!WdLogSingleEntry0` at `0x1400b5998`
- `watchdog!WdLogSingleEntry0` at `0x1400b5bc5`
- `watchdog!WdLogSingleEntry0` at `0x1400b5c69`
- `watchdog!WdLogSingleEntry0` at `0x1400b5cde`
- `watchdog!WdLogSingleEntry0` at `0x1400b5e6c`
- `watchdog!WdLogSingleEntry0` at `0x1400b60b4`
- `watchdog!WdLogSingleEntry0` at `0x1400b6ebb`
- `watchdog!WdLogSingleEntry0` at `0x1400b6f03`
- `watchdog!WdLogSingleEntry1` at `0x1400b5897`
- `watchdog!WdLogSingleEntry1` at `0x1400b5a44`
- `watchdog!WdLogSingleEntry1` at `0x1400b5fe1`
- `watchdog!WdLogSingleEntry1` at `0x1400b604f`
- `watchdog!WdLogSingleEntry1` at `0x1400b6236`
- `watchdog!WdLogSingleEntry1` at `0x1400b6783`
- `watchdog!WdLogSingleEntry1` at `0x1400b69b3`
- `watchdog!WdLogSingleEntry1` at `0x1400b5897`
- `watchdog!WdLogSingleEntry1` at `0x1400b5a44`
- `watchdog!WdLogSingleEntry1` at `0x1400b5fe1`
- `watchdog!WdLogSingleEntry1` at `0x1400b604f`
- `watchdog!WdLogSingleEntry1` at `0x1400b6236`
- `watchdog!WdLogSingleEntry1` at `0x1400b6783`
- `watchdog!WdLogSingleEntry1` at `0x1400b69b3`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400b6e74`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400b4e3b`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400b4e6c`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400b4ead`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400b6ccb`

## string_xrefs

- `0x1400b50a8`: `HardwareProtected allocations cannot be used with PermanentSysMem, Cached, CrossAdapter, CrossAdapterPrimary, Protected, ExistingSysMem, ExistingKernelSysMem`
- `0x1400b50e3`: `Specified preferred segment is invalid. It must be a subset of the supported read segment set`
- `0x1400b5163`: `Can't create an allocation of zero size`
- `0x1400b51a3`: `LinkInstanced/MapApertureCpuVisible flag is not supported in WDDM v2.x/<2.9, respectively`
- `0x1400b52b3`: `CpuVisibleOnDemand must also be set in combination with CpuVisible`
- `0x1400b53cd`: `Need to specify the CpuVisible flags in combination with PermanentSysMem`
- `0x1400b53fd`: `Shareable, ManagedPrimary and Primary can't be specified in combination with PermanentSysMem`
- `0x1400b5459`: `Cached allocations must only support cache coherent segments on adapters which have cache coherent aperture segments available`
- `0x1400b56c8`: `PermanentSysMem, Cached, ExistingSysMem, ExistingKernelSysMem and Primary flags can't be specified with ManagedPrimary`
- `0x1400b574b`: `PermanentSysMem, Cached, ExistingSysMem, ExistingKernelSysMem and ManagedPrimary flags can't be specified with Primary`
- `0x1400b57a4`: `PagingBuffer can't be combined with any other flags`
- `0x1400b58a3`: `History buffer specifies invalid flag combination. Flags=%d`
- `0x1400b60c5`: `Can't create an allocation that uses more than 4GB-64kB of system memory`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
__int64 VIDMM_GLOBAL::CreateOneAllocation(
        __int64 a1,
        struct VIDMM_DEVICE *a2,
        unsigned int a3,
        unsigned __int64 a4,
        unsigned __int64 a5,
        unsigned int a6,
        int a7,
        int a8,
        unsigned int a9,
        unsigned int a10,
        unsigned int a11,
        _D3DDDI_SEGMENTPREFERENCE a12,
        ...)
{
  __int16 v12; // r13
  struct _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0::$5068715F5D8591D41DA1228877FDA04B::$63766B29C143116E9EC685C38896947D v14; // ebx
  struct DXGPROCESS *Current; // rax
  struct DXGPROCESS *v19; // rcx
  int v20; // edx
  struct VIDMM_PROCESS *v21; // r9
  __int64 v22; // rax
  int v23; // eax
  int v24; // ecx
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  struct VIDMM_PROCESS *v29; // r9
  __int64 v30; // r11
  unsigned __int64 v31; // r12
  __int64 v32; // rax
  __int64 v33; // rdx
  __int64 v34; // rcx
  _QWORD *v35; // rax
  __int64 v36; // rdx
  _QWORD *v37; // rax
  int v38; // r8d
  __int64 v39; // rax
  const wchar_t *v40; // r9
  char v41; // r14
  __int64 CurrentProcess; // rax
  struct VIDMM_PHYSICAL_ADAPTER *v43; // r10
  int v44; // eax
  unsigned int v45; // edx
  unsigned __int64 v46; // rcx
  __int64 Value; // rbx
  unsigned __int64 v48; // r14
  unsigned int v49; // edx
  unsigned int v50; // ecx
  __int64 v51; // r11
  unsigned int v52; // r10d
  unsigned int v53; // eax
  int v54; // edi
  unsigned int v55; // edx
  unsigned int v56; // r8d
  int v57; // r10d
  int v58; // ecx
  int v59; // eax
  int v60; // eax
  int v61; // edx
  int v62; // ecx
  int v63; // r8d
  const wchar_t *v64; // r9
  UINT v65; // edx
  int v66; // ecx
  int v67; // r8d
  __int64 v68; // rax
  _QWORD *v69; // rax
  __int64 v70; // rax
  struct VIDMM_GLOBAL_ALLOC *v71; // rdx
  int v72; // ecx
  int v73; // r8d
  unsigned int v74; // edx
  VIDMM_GLOBAL *v75; // rcx
  int v76; // edi
  _QWORD *v77; // rbx
  char *v78; // r14
  VIDMM_GLOBAL *v79; // r9
  struct VIDMM_GLOBAL_ALLOC *v80; // rcx
  struct VIDMM_GLOBAL_ALLOC *v81; // r10
  int v82; // ecx
  int v83; // r8d
  __int64 v84; // rax
  unsigned __int64 v85; // rdx
  int v86; // ecx
  int v87; // r8d
  __int64 v88; // r11
  unsigned __int64 v89; // r10
  __int64 v90; // rcx
  int v91; // r9d
  int SyncObject; // eax
  __int64 v93; // rax
  unsigned __int64 v94; // r8
  volatile signed __int32 *v95; // rcx
  int v96; // ecx
  int v97; // r8d
  __int64 v98; // rcx
  struct VIDMM_GLOBAL_ALLOC *v99; // rax
  __int64 v100; // rdx
  _DWORD *v101; // rcx
  struct VIDMM_CROSSADAPTER_ALLOC *v102; // rax
  int CrossAdapterDataDpc; // eax
  unsigned int v104; // r9d
  int v105; // eax
  __int64 v106; // r8
  unsigned __int64 v107; // rdx
  int v108; // ecx
  int v109; // ecx
  int v110; // r8d
  __int64 v111; // rax
  const wchar_t *v112; // r9
  __int64 v113; // rax
  unsigned int v114; // r9d
  __int64 v115; // rax
  int v116; // ecx
  __int64 v117; // rbx
  int v118; // ecx
  int v119; // r8d
  __int64 v120; // r8
  unsigned int v121; // eax
  _DWORD *v122; // r9
  unsigned int v123; // eax
  int v124; // eax
  int v125; // ecx
  int v126; // eax
  unsigned int v127; // ecx
  int v128; // edx
  int v129; // eax
  unsigned int v130; // edx
  _DWORD *v131; // rax
  unsigned int v132; // r8d
  int v133; // edi
  unsigned int v134; // edx
  int v135; // eax
  __int64 v136; // rdi
  unsigned int v137; // edx
  __int64 v138; // rax
  struct VIDMM_EXISTINGSYSMEM_HEAP *v139; // rax
  __int64 v140; // r10
  unsigned __int8 v141; // al
  struct VIDMM_GLOBAL_ALLOC *v142; // r11
  unsigned int v143; // ecx
  bool v144; // al
  struct VIDMM_PHYSICAL_ADAPTER *v145; // r10
  unsigned __int64 v146; // rdx
  unsigned __int64 v147; // r9
  struct VIDMM_GLOBAL_ALLOC *v148; // rdi
  unsigned __int64 v149; // rcx
  int v150; // ecx
  int v151; // ecx
  int v152; // eax
  _DWORD *v153; // rax
  unsigned __int64 v154; // rcx
  _BOOL8 v155; // r10
  _BOOL8 v156; // r9
  _DWORD *v157; // rax
  _BOOL8 v158; // r9
  int v159; // ecx
  _BOOL8 v160; // rdx
  __int64 v161; // rcx
  void *v162; // rcx
  struct VIDMM_PHYSICAL_ADAPTER *v163; // rcx
  const struct VIDMM_SEGMENT_BASE *MostPreferredSegment; // rax
  int v165; // r11d
  bool v166; // al
  int v167; // r10d
  unsigned __int64 v168; // rbx
  int LogicalMemory; // eax
  int v170; // ecx
  int v171; // r8d
  __int64 v172; // rdx
  __int64 v173; // rcx
  volatile signed __int32 *v174; // rax
  unsigned int v175; // eax
  bool v176; // zf
  int v177; // edx
  int v178; // ecx
  const struct _DXGK_ALLOCATIONUSAGEHINT *AllocationHint; // rax
  __int64 BucketIdForAllocationSizePow2; // rdx
  __int64 v181; // rcx
  __int64 v182; // r8
  __int64 v183; // r9
  int v184; // r10d
  int v185; // ecx
  __int64 v186; // rsi
  struct _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0::$5068715F5D8591D41DA1228877FDA04B::$63766B29C143116E9EC685C38896947D v187; // ecx
  unsigned int CurrentProcessId; // eax
  int v189; // r8d
  __int64 v190; // r8
  __int64 v191; // r8
  unsigned int v192; // r9d
  int v194; // r8d
  __int64 v195; // rax
  __int64 i; // rsi
  void *v197; // rcx
  VIDMM_FLIP_QUEUE_REFERENCES *v198; // rcx
  struct VIDMM_CROSSADAPTER_ALLOC *v199; // rdx
  VIDMM_GLOBAL *v200; // rcx
  __int64 v201; // rdx
  int *v202; // r9
  __int64 v203; // rcx
  int v204; // r8d
  int v205; // [rsp+60h] [rbp-130h]
  int v206; // [rsp+110h] [rbp-80h]
  char v207; // [rsp+114h] [rbp-7Ch]
  _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0 v208; // [rsp+118h] [rbp-78h] BYREF
  unsigned int PrivateFormat; // [rsp+11Ch] [rbp-74h]
  char v210; // [rsp+120h] [rbp-70h]
  PVOID P; // [rsp+128h] [rbp-68h]
  struct VIDMM_GLOBAL_ALLOC *v212; // [rsp+130h] [rbp-60h]
  int Version; // [rsp+138h] [rbp-58h]
  int Width; // [rsp+13Ch] [rbp-54h]
  int v215; // [rsp+140h] [rbp-50h]
  struct VIDMM_PHYSICAL_ADAPTER *v216; // [rsp+148h] [rbp-48h]
  unsigned __int64 v217; // [rsp+150h] [rbp-40h] BYREF
  UINT SwizzledFormat; // [rsp+158h] [rbp-38h]
  UINT Height; // [rsp+15Ch] [rbp-34h] BYREF
  __int64 v220; // [rsp+160h] [rbp-30h]
  unsigned __int64 v221; // [rsp+168h] [rbp-28h]
  unsigned __int64 v222; // [rsp+170h] [rbp-20h]
  struct VIDMM_CROSSADAPTER_ALLOC *v223; // [rsp+178h] [rbp-18h]
  struct VIDMM_PROCESS *v224; // [rsp+180h] [rbp-10h]
  __int64 v225; // [rsp+188h] [rbp-8h]
  int v226[2]; // [rsp+190h] [rbp+0h]
  __int64 v227; // [rsp+198h] [rbp+8h]
  __int64 v228; // [rsp+1A0h] [rbp+10h]
  __int64 v229; // [rsp+1A8h] [rbp+18h]
  _DWORD *v230; // [rsp+1B0h] [rbp+20h]
  int v231[32]; // [rsp+1C0h] [rbp+30h] BYREF
  __int64 v235; // [rsp+2B0h] [rbp+120h] BYREF
  va_list va; // [rsp+2B0h] [rbp+120h]
  __int64 v237; // [rsp+2B8h] [rbp+128h]
  __int64 v238; // [rsp+2C0h] [rbp+130h]
  void *v239; // [rsp+2C8h] [rbp+138h]
  __int64 v240; // [rsp+2D0h] [rbp+140h]
  void *v241; // [rsp+2D8h] [rbp+148h]
  __int64 v242; // [rsp+2E0h] [rbp+150h]
  __int64 v243; // [rsp+2E8h] [rbp+158h]
  __int64 v244; // [rsp+2F0h] [rbp+160h]
  __int64 v245; // [rsp+2F8h] [rbp+168h]
  __int64 v246; // [rsp+300h] [rbp+170h]
  struct VIDMM_CROSSADAPTER_ALLOC **v247; // [rsp+308h] [rbp+178h]
  __int64 v248; // [rsp+310h] [rbp+180h]
  _QWORD *v249; // [rsp+318h] [rbp+188h]
  unsigned __int8 *v250; // [rsp+320h] [rbp+190h]
  va_list va1; // [rsp+328h] [rbp+198h] BYREF

  va_start(va1, a12);
  va_start(va, a12);
  v235 = va_arg(va1, _QWORD);
  v237 = va_arg(va1, _QWORD);
  v238 = va_arg(va1, _QWORD);
  v239 = va_arg(va1, void *);
  v240 = va_arg(va1, _QWORD);
  v241 = va_arg(va1, void *);
  v242 = va_arg(va1, _QWORD);
  v243 = va_arg(va1, _QWORD);
  v244 = va_arg(va1, _QWORD);
  v245 = va_arg(va1, _QWORD);
  v246 = va_arg(va1, _QWORD);
  v247 = va_arg(va1, struct VIDMM_CROSSADAPTER_ALLOC **);
  v248 = va_arg(va1, _QWORD);
  v249 = va_arg(va1, _QWORD *);
  v250 = va_arg(va1, unsigned __int8 *);
  v12 = v235;
  v14 = (struct _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0::$5068715F5D8591D41DA1228877FDA04B::$63766B29C143116E9EC685C38896947D)v235;
  v208.0 = (struct _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0::$5068715F5D8591D41DA1228877FDA04B::$63766B29C143116E9EC685C38896947D)v235;
  Current = DXGPROCESS::GetCurrent();
  v221 = (unsigned __int64)Current;
  v19 = Current;
  if ( !v248 || (v20 = *(_DWORD *)(v248 + 176), LOBYTE(v235) = 1, (v20 & 1) != 0) )
    LOBYTE(v235) = 0;
  if ( a2 )
  {
    v21 = (struct VIDMM_PROCESS *)*((_QWORD *)a2 + 1);
  }
  else
  {
    if ( !Current )
    {
      WdLogSingleEntry0(1);
      v39 = 2935;
      v40 = L"pVidMmProcess is not present";
      goto LABEL_479;
    }
    v22 = *((_QWORD *)Current + 8);
    if ( v22 )
      v21 = *(struct VIDMM_PROCESS **)(v22 + 8);
    else
      v21 = 0;
  }
  v23 = v243;
  v224 = v21;
  if ( (unsigned int)v243 <= 2 )
    v23 = 2;
  LODWORD(v243) = v23;
  if ( v19 && (v24 = *((_DWORD *)v19 + 102), (v24 & 0x100) != 0) )
  {
    v210 = 1;
    if ( (v24 & 0x400) == 0 && !v245 && (v12 & 1) != 0 )
    {
      v14 = (struct _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0::$5068715F5D8591D41DA1228877FDA04B::$63766B29C143116E9EC685C38896947D)(*(_DWORD *)&v14 & 0xFFFF7FFF);
      v208.0 = v14;
    }
  }
  else
  {
    v210 = 0;
  }
  if ( g_Feature_ResourcePoolManagement )
  {
    v228 = *((_QWORD *)v21 + 46);
    v227 = 0;
  }
  else
  {
    v227 = *((_QWORD *)v21 + 43);
    v228 = 0;
  }
  v25 = 0;
  v26 = *(_QWORD *)(a1 + 36480);
  if ( *(_DWORD *)(a1 + 3112) != 1 )
    v25 = a3;
  *(_QWORD *)v226 = v25;
  v217 = 0;
  v216 = *(struct VIDMM_PHYSICAL_ADAPTER **)(v26 + 8 * v25);
  v230 = (_DWORD *)*((_QWORD *)v216 + 169);
  VidMmConvertSegmentPreferences((const struct VIDMM_GLOBAL *)a1, a12, (struct VIDMM_SEGMENT_PREFERENCES *)&v217);
  v31 = v217;
  v220 = a6;
  if ( g_IsInternalReleaseOrDbg != (_BYTE)v30 )
  {
    v32 = WdLogNewEntry5_WdTrace(v28, v27);
    v30 = 0;
    *(_QWORD *)(v32 + 24) = a2;
    WdLogGlobalForLineNumber = 3007;
    if ( g_IsInternalReleaseOrDbg )
    {
      v35 = (_QWORD *)WdLogNewEntry5_WdTrace(v34, v33);
      v35[3] = a4;
      v35[4] = a6;
      v35[5] = a9;
      v35[6] = a10;
      WdLogGlobalForLineNumber = 3012;
      v37 = (_QWORD *)WdLogNewEntry5_WdTrace(a10, v36);
      v30 = 0;
      v37[3] = (unsigned int)v31;
      v37[4] = HIDWORD(v217);
      v37[5] = (unsigned int)v14;
      v37[6] = v238;
      WdLogGlobalForLineNumber = 3017;
    }
    v29 = v224;
  }
  *v249 = v30;
  if ( *(_DWORD *)(a1 + 40) < 0x5023u && (*(_DWORD *)&v14 & 0x40000) != 0 )
  {
    WdLogSingleEntry0(1);
    v39 = 3033;
    v40 = L"CpuVisibleOnDemand flag set, but on this driver is supposed to be reserved";
LABEL_479:
    WdLogGlobalForLineNumber = v39;
    DxgkLogInternalTriageEvent(0, 0x40000, v38, (_DWORD)v40, v39, 0, 0, 0);
    return 3221225485LL;
  }
  if ( (*(_DWORD *)&v14 & 0x20000) != 0 )
  {
    if ( (*(_BYTE *)&v14 & 2) != 0
      || (*(_BYTE *)&v14 & 4) != 0 && (*(_DWORD *)(*(_QWORD *)(a1 + 24) + 444LL) & 8) == 0
      || (*(_DWORD *)&v14 & 0x100000) != 0
      || (*(_DWORD *)&v14 & 0x80000) != 0
      || (*(_BYTE *)&v14 & 8) != 0
      || (*(_BYTE *)&v14 & 0x10) != 0
      || (*(_BYTE *)&v14 & 0x20) != 0 )
    {
      WdLogSingleEntry0(1);
      v39 = 3055;
      v40 = L"HardwareProtected allocations cannot be used with PermanentSysMem, Cached, CrossAdapter, CrossAdapterPrimary"
             ", Protected, ExistingSysMem, ExistingKernelSysMem";
      goto LABEL_479;
    }
    v14 = (struct _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0::$5068715F5D8591D41DA1228877FDA04B::$63766B29C143116E9EC685C38896947D)(*(_DWORD *)&v14 & 0xFFFBFFFE);
    v208.0 = v14;
  }
  if ( (*(_BYTE *)&v14 & 1) != 0 && (*(_DWORD *)&v14 & 0x40000) == 0
    || (LOBYTE(v215) = v30, (*(_BYTE *)&v14 & 0x10) != 0) )
  {
    LOBYTE(v215) = 1;
  }
  v41 = v235;
  if ( (_BYTE)v235 || (*(_BYTE *)&v14 & 8) != 0 || (*(_DWORD *)&v14 & 0x20000) != 0 )
    LOBYTE(v215) = v30;
  if ( (*((_DWORD *)v29 + 40) & 0x40) == 0 )
  {
    CurrentProcess = PsGetCurrentProcess();
    if ( !PsGetProcessWow64Process(CurrentProcess)
      && (*(_DWORD *)&v14 & 0x20000000) == 0
      && (*(_DWORD *)&v14 & 0x40000000) == 0
      && *(int *)&v14 >= 0
      && (*(_DWORD *)&v14 & 0x10000000) == 0
      && (*(_BYTE *)&v14 & 8) == 0
      && (*(_DWORD *)&v14 & 0x400000) == 0
      && (*(_DWORD *)&v14 & 0x20000) == 0
      && !v41
      && !v245
      && !v246 )
    {
      v14 = (struct _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0::$5068715F5D8591D41DA1228877FDA04B::$63766B29C143116E9EC685C38896947D)(*(_DWORD *)&v14 & 0xFFFBFFFF);
      LOBYTE(v215) = 1;
      v208.0 = v14;
    }
  }
  if ( ((*(unsigned int *)&v14 >> 13) & 1) != 0 && (*(_BYTE *)(a1 + 37225) & 8) == 0 )
  {
    WdLogSingleEntry0(1);
    v39 = 3142;
    v40 = L"Drivers must support MapAperture2 to set the MapApertureCpuVisible flag";
    goto LABEL_479;
  }
  if ( !(unsigned __int8)VidMmValidatePreferredSegment(v216, v31, a9) )
  {
    WdLogSingleEntry0(1);
    v39 = 3152;
    v40 = L"Specified preferred segment is invalid. It must be a subset of the supported read segment set";
    goto LABEL_479;
  }
  if ( !dword_1400875B0 || (*(_BYTE *)&v14 & 1) != 0 )
  {
    v45 = a9;
    v43 = v216;
  }
  else
  {
    v43 = v216;
    if ( (v31 & 0x1F) != 0 )
    {
      v45 = 1 << ((v31 & 0x1F) - 1);
      a9 = v45;
    }
    else
    {
      v44 = *((_DWORD *)v216 + 21) & a9;
      if ( !v44 )
        v44 = a9;
      v45 = v44;
      a9 = v44;
    }
  }
  v46 = a4;
  if ( !a4 )
  {
    WdLogSingleEntry0(1);
    v39 = 3193;
    v40 = L"Can't create an allocation of zero size";
    goto LABEL_479;
  }
  if ( ((*(unsigned int *)&v14 >> 13) & 1) != 0 )
  {
    if ( *(int *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 16LL) + 3132LL) < 2900 )
    {
      WdLogSingleEntry0(1);
      v39 = 3203;
      v40 = L"LinkInstanced/MapApertureCpuVisible flag is not supported in WDDM v2.x/<2.9, respectively";
      goto LABEL_479;
    }
    v46 = a4;
  }
  if ( (*(_WORD *)&v14 & 0x1000) != 0 )
  {
    WdLogSingleEntry0(1);
    v39 = 3210;
    v40 = L"PhysicallyContiguous flag is not not currently supported";
    goto LABEL_479;
  }
  if ( (v45 & *((_DWORD *)v43 + 19)) == 0 )
  {
    WdLogSingleEntry0(1);
    v39 = 3223;
LABEL_86:
    v40 = L"Specified segment set references invalid segment";
    goto LABEL_479;
  }
  if ( !v246 && (v45 & *((_DWORD *)v43 + 20)) == 0 )
  {
    WdLogSingleEntry0(1);
    v39 = 3236;
    goto LABEL_86;
  }
  Height = 0;
  LODWORD(v235) = 0;
  if ( !VidMmVerifySupportedSegmentSetAndAdjustFlags(
          v43,
          v45,
          &v208,
          v46,
          a5,
          v245 != 0,
          (struct _VIDMM_VERIFY_SUPPORTED_SEGMENT *)va) )
  {
    WdLogSingleEntry0(1);
    v39 = 3253;
    v40 = L"VidMmVerifySupportedSegmentSetAndAdjustFlags failed";
    goto LABEL_479;
  }
  Value = v208.Value;
  if ( (v208.Value & 0x40000) != 0 )
  {
    if ( (*(_BYTE *)&v208.0 & 1) == 0 )
    {
      WdLogSingleEntry0(1);
      v39 = 3265;
      v40 = L"CpuVisibleOnDemand must also be set in combination with CpuVisible";
      goto LABEL_479;
    }
    if ( (*(_BYTE *)&v208.0 & 2) != 0 || (*(_BYTE *)&v208.0 & 0x20) != 0 || (*(_BYTE *)&v208.0 & 0x10) != 0 )
    {
      WdLogSingleEntry0(1);
      v39 = 3277;
      v40 = L"PermanentSysMem, ExistingKernelSysMem, and ExistingSysMem cannot be used with CpuVisibleOnDemand";
      goto LABEL_479;
    }
  }
  v48 = (unsigned int)v235;
  v49 = a10;
  v222 = a5 & -(__int64)((v235 & 4) != 0);
  if ( a10 )
  {
    if ( (a10 & *((_DWORD *)v216 + 20)) == 0 )
    {
      WdLogSingleEntry0(1);
      v39 = 3303;
      v40 = L"EvictionSegmentSet must be a valid set of driver segments";
      goto LABEL_479;
    }
    if ( (~*((_DWORD *)v216 + 24) & a10) != 0 )
    {
      WdLogSingleEntry0(1);
      v39 = 3314;
      v40 = L"EvictionSegmentSet may only contain system memory segments";
      goto LABEL_479;
    }
    if ( VidMmCheckAnySegmentAllFlags(v216, a10, (struct _DXGK_SEGMENTFLAGS)32) )
    {
      WdLogSingleEntry0(1);
      v39 = 3329;
      v40 = L"Can't use a segment requiring pitch alignment for paging";
      goto LABEL_479;
    }
    v49 = a10;
  }
  v50 = ((unsigned int)Value >> 1) & 1;
  Width = v50;
  if ( v50 )
  {
    if ( (Value & 1) == 0 )
    {
      WdLogSingleEntry0(1);
      v39 = 3346;
      v40 = L"Need to specify the CpuVisible flags in combination with PermanentSysMem";
      goto LABEL_479;
    }
    if ( (Value & 0x20000000) != 0 || (int)Value < 0 || (Value & 0x40000000) != 0 )
    {
      WdLogSingleEntry0(1);
      v39 = 3357;
      v40 = L"Shareable, ManagedPrimary and Primary can't be specified in combination with PermanentSysMem";
      goto LABEL_479;
    }
  }
  v51 = a1;
  v52 = ((unsigned int)Value >> 2) & 1;
  LODWORD(v235) = v52;
  if ( v52 && (Value & 0x800000) == 0 && *(_BYTE *)(a1 + 3202) )
  {
    if ( !VidMmCheckAllSegmentsAllFlags(v216, v49, (struct _DXGK_SEGMENTFLAGS)16) )
    {
      WdLogSingleEntry0(1);
      v39 = 3393;
      v40 = L"Cached allocations must only support cache coherent segments on adapters which have cache coherent aperture "
             "segments available";
      goto LABEL_479;
    }
    v50 = Width;
    v51 = a1;
    v52 = v235;
  }
  v53 = ((unsigned int)Value >> 29) & 1;
  if ( v53 && (v50 || (Value & 8) != 0 || (Value & 0x20) != 0 || (Value & 0x40000000) != 0) )
  {
    WdLogSingleEntry0(1);
    v39 = 3412;
    v40 = L"PermanentSysMem, Protected, ExistingKernelSysMem, or Primary flags can't be specified with Shareable";
    goto LABEL_479;
  }
  v54 = v237;
  if ( (v237 & 1) != 0 && ((v48 & 1) == 0 || !v53) )
  {
    WdLogSingleEntry0(1);
    v39 = 3421;
    v40 = L"ShareBackingStoreWithKmd flag should be set only for shared aperture only allocations";
    goto LABEL_479;
  }
  if ( (Value & 0x100000) != 0 && (!v53 || !v247 || (v48 & 1) == 0) )
  {
    WdLogSingleEntry0(1);
    v39 = 3434;
    v40 = L"Cross adapter allocations must be shareable and support system memory only and SharedResource must be provided";
    goto LABEL_479;
  }
  v229 = 256;
  if ( v245 && (v50 || (Value & 0x100) != 0 || (Value & 0x200) != 0 || (Value & 0x40000000) != 0) )
  {
    WdLogSingleEntry0(1);
    v39 = 3454;
    v40 = L"PermanentSysMem, Overlay, Capture, or Primary flags can't be specified for context allocations";
    goto LABEL_479;
  }
  if ( (((unsigned int)Value >> 26) & 1) != 0 )
  {
    if ( (Value & 8) == 0 )
    {
      WdLogSingleEntry0(1);
      v39 = 3470;
      v40 = L"Protected flag must be specified with CddBitmap";
      goto LABEL_479;
    }
  }
  else if ( (Value & 8) == 0 )
  {
    goto LABEL_155;
  }
  if ( (Value & 1) != 0 && (((unsigned int)Value >> 26) & 1) == 0 && !v245
    || v50
    || v53
    || (Value & 0x10) != 0
    || (Value & 0x20) != 0
    || (int)Value < 0
    || (Value & 0x40000000) != 0 )
  {
    WdLogSingleEntry0(1);
    v39 = 3501;
    v40 = L"CpuVisible, PermanentSysMem, Shareable, ExistingSysMem, ExistingKernelSysMem, ManagedPrimary or Primary flags "
           "can't be specified with Protected";
    goto LABEL_479;
  }
LABEL_155:
  v55 = ((unsigned int)Value >> 4) & 1;
  if ( v55 && (v50 || (Value & 0x20) != 0 || (int)Value < 0 || (Value & 0x40000000) != 0) )
  {
    WdLogSingleEntry0(1);
    v39 = 3521;
    v40 = L"PermanentSysMem, ExistingKernelSysMem, ManagedPrimary or Primary flags can't be specified with ExistingSysMem";
    goto LABEL_479;
  }
  v56 = ((unsigned int)Value >> 5) & 1;
  if ( v56 && (v50 || v53 || v55 || (int)Value < 0 || (Value & 0x40000000) != 0) )
  {
    WdLogSingleEntry0(1);
    v39 = 3543;
    v40 = L"PermanentSysMem, Shareable, ExistingSysMem, ManagedPrimary or Primary flags can't be specified with ExistingKernelSysMem";
    goto LABEL_479;
  }
  if ( (int)Value >= 0 )
  {
    if ( (Value & 0x40000000) != 0 )
    {
      if ( v50
        || v52 && (v58 = *(_DWORD *)(*(_QWORD *)(v51 + 24) + 444LL), (v58 & 0x10) == 0) && (v58 & 8) == 0
        || v55
        || v56 )
      {
        WdLogSingleEntry0(1);
        v39 = 3587;
        v40 = L"PermanentSysMem, Cached, ExistingSysMem, ExistingKernelSysMem and ManagedPrimary flags can't be specified with Primary";
        goto LABEL_479;
      }
      if ( (*(_DWORD *)(*(_QWORD *)(v51 + 24) + 2596LL) & 0x200) == 0 )
        Value = (unsigned int)Value | 1;
      v59 = (unsigned __int8)v215;
      if ( (Value & 1) != 0 )
        v59 = 1;
      LODWORD(Value) = Value | 0x20000000;
      v215 = v59;
    }
  }
  else if ( v50
         || v52 && (v57 = *(_DWORD *)(*(_QWORD *)(v51 + 24) + 444LL), (v57 & 0x10) == 0) && (v57 & 8) == 0
         || v55
         || v56
         || (Value & 0x40000000) != 0 )
  {
    WdLogSingleEntry0(1);
    v39 = 3565;
    v40 = L"PermanentSysMem, Cached, ExistingSysMem, ExistingKernelSysMem and Primary flags can't be specified with ManagedPrimary";
    goto LABEL_479;
  }
  LODWORD(v235) = ((unsigned int)Value >> 28) & 1;
  if ( (_DWORD)v235 )
  {
    v60 = Value & 0xEFFF7FBF;
    v61 = *(_DWORD *)(*(_QWORD *)(v51 + 24) + 444LL);
    if ( (v61 & 8) != 0 || (v61 & 0x10) != 0 )
      v60 = Value & 0xEFFF7FBB;
    if ( v60 )
    {
      WdLogSingleEntry0(1);
      v39 = 3629;
      v40 = L"PagingBuffer can't be combined with any other flags";
      goto LABEL_479;
    }
    if ( (~*((_DWORD *)v216 + 24) & a9) != 0 )
    {
      WdLogSingleEntry0(1);
      v39 = 3639;
      v40 = L"Paging buffer can only be allocated from an aperture segment";
      goto LABEL_479;
    }
  }
  if ( (Value & 0x400000) != 0 )
  {
    if ( (Value & 0x20000000) == 0 )
    {
      WdLogSingleEntry0(1);
      v39 = 3655;
      v40 = L"SectionSupplied should always be Shareable resource";
      goto LABEL_479;
    }
    if ( !v239 )
    {
      WdLogSingleEntry0(1);
      v39 = 3665;
      v40 = L"SectionSupplied resource does not supply the section";
      goto LABEL_479;
    }
  }
  if ( (Value & 0x4000) != 0 )
  {
    if ( (Value & 1) == 0 )
    {
      WdLogSingleEntry0(1);
      v39 = 3677;
      v40 = L"History buffers must specify the CpuVisible flag";
      goto LABEL_479;
    }
    if ( (Value & 2) != 0
      || (Value & 8) != 0
      || (Value & 0x10) != 0
      || (Value & 0x20) != 0
      || (Value & 0x40) != 0
      || (Value & 0x100) != 0
      || (Value & 0x200) != 0
      || (Value & 0x40000) != 0 )
    {
      WdLogSingleEntry1(1, Value);
      v64 = L"History buffer specifies invalid flag combination. Flags=%d";
      WdLogGlobalForLineNumber = 3693;
LABEL_215:
      DxgkLogInternalTriageEvent(v62, 0x40000, v63, (_DWORD)v64, Value, 0, 0, 0);
      return 3221225485LL;
    }
  }
  if ( v247 )
    v223 = *v247;
  else
    v223 = 0;
  if ( (VIDMM_GLOBAL::_Config & 2) != 0
    && DXGPROCESS::GetCurrent()
    && (*((_DWORD *)DXGPROCESS::GetCurrent() + 102) & 4) != 0
    && !(_DWORD)v235
    && (Value & 0x40000000) == 0 )
  {
    LODWORD(Value) = Value | 0x8000000;
  }
  v207 = 0;
  LOBYTE(v235) = 0;
  LOBYTE(SwizzledFormat) = 0;
  if ( !v210 || v245 )
  {
    Version = 0;
    goto LABEL_238;
  }
  if ( (Value & 0x10) != 0 )
  {
    LOBYTE(v215) = 0;
    Version = 8;
    v208.0 = (struct _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0::$5068715F5D8591D41DA1228877FDA04B::$63766B29C143116E9EC685C38896947D)64;
    goto LABEL_239;
  }
  if ( (Value & 1) == 0 )
  {
    Version = 8;
LABEL_238:
    v208.0 = 0;
    goto LABEL_239;
  }
  if ( (Value & 0x8000) != 0 && (*(_DWORD *)(v221 + 408) & 0x400) == 0 )
  {
    WdLogSingleEntry0(1);
    v39 = 3745;
    v40 = L"Cpu visible paravirtualized allocations cannot be places to aperture segment";
    goto LABEL_479;
  }
  v65 = *(_DWORD *)(v221 + 408) >> 10;
  LOBYTE(v65) = (*(_DWORD *)(v221 + 408) & 0x400) != 0;
  Version = 8;
  SwizzledFormat = v65;
  v208.0 = 0;
  LOBYTE(v235) = v65 ^ 1;
  if ( (Value & 0x20000000) != 0 )
  {
    v207 = 1;
    LOBYTE(v235) = v65 ^ 1;
  }
  else
  {
    SwizzledFormat = v65;
    v207 = v65 ^ 1;
  }
LABEL_239:
  if ( *(int *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 16LL) + 3132LL) >= 3000
    && (Value & 1) != 0
    && (v48 & 2) == 0
    && !v246
    && (Value & 0x40000000) == 0 )
  {
    WdLogSingleEntry1(1, Value);
    v64 = L"CPUVisible allocations must include an aperture segment in the supported segment set";
    WdLogGlobalForLineNumber = 3792;
    goto LABEL_215;
  }
  if ( v240 && (v240 != (v240 & 0xFFFFFFFFFFFFF000uLL) || (a4 & 0xFFF) != 0) )
  {
    WdLogSingleEntry2(1, v240, a4);
    WdLogGlobalForLineNumber = 3810;
    DxgkLogInternalTriageEvent(
      v66,
      0x40000,
      v67,
      (unsigned int)L"Existing sysmem pointer must be paged aligned and a multiple of page in size. pExistingSysMem=0x%.16x, Size=%I64u",
      v240,
      a4,
      0,
      0);
    return 3221225485LL;
  }
  v225 = 0;
  v68 = operator new(400, 825256278, 256);
  P = (PVOID)v68;
  if ( !v68 )
    goto LABEL_477;
  *(_QWORD *)(v68 + 144) = 0;
  *(_QWORD *)(v68 + 152) = 0;
  *(_QWORD *)(v68 + 160) = 0;
  *(_DWORD *)(v68 + 168) = 0;
  *(_QWORD *)(v68 + 192) = 0;
  *(_QWORD *)(v68 + 200) = 0;
  *(_DWORD *)(v68 + 172) = 13;
  *(_DWORD *)(v68 + 176) = 17;
  *(_DWORD *)(v68 + 208) = 0;
  *(_QWORD *)(v68 + 216) = 0;
  *(_QWORD *)(v68 + 320) = 0;
  *(_QWORD *)(v68 + 328) = 0;
  *(_DWORD *)(v68 + 212) = 78;
  *(_DWORD *)(v68 + 336) = 0;
  *(_DWORD *)(v68 + 340) = 18;
  *(_OWORD *)(v68 + 376) = 0;
  v69 = (_QWORD *)(v68 + 96);
  v69[1] = v69;
  *v69 = v69;
  v70 = operator new(56, 842295638, 64);
  v71 = (struct VIDMM_GLOBAL_ALLOC *)P;
  v217 = (unsigned __int64)P + 392;
  *((_QWORD *)P + 49) = v70;
  if ( !v70 )
  {
    _InterlockedIncrement(&dword_1400877B8);
    WdLogSingleEntry0(6);
    WdLogGlobalForLineNumber = 3861;
    DxgkLogInternalTriageEvent(
      v72,
      262145,
      v73,
      (unsigned int)L"Couldn't allocate memory for VIDMM_GLOBAL_ALLOC_NONPAGED",
      3861,
      0,
      0,
      0);
    v76 = -1073741801;
LABEL_252:
    v77 = P;
    v78 = (char *)P;
LABEL_457:
    if ( (*((_DWORD *)v78 + 8) & 0x20) != 0 )
      VIDMM_GLOBAL::UncommitGlobalBackingStore((VIDMM_GLOBAL *)a1, (struct VIDMM_GLOBAL_ALLOC *)v78, 1);
    v195 = *((_QWORD *)v78 + 49);
    if ( v195 )
    {
      if ( *(_QWORD *)(v195 + 32) )
      {
        for ( i = 0; i != 2; ++i )
        {
          v197 = *(void **)(*(_QWORD *)(v77[49] + 32LL) + 8 * i);
          if ( v197 )
            VidSchDestroySyncObject(v197);
        }
        operator delete(*(void **)(*((_QWORD *)v78 + 49) + 32LL));
      }
      v198 = *(VIDMM_FLIP_QUEUE_REFERENCES **)(*((_QWORD *)v78 + 49) + 24LL);
      if ( v198 )
        VIDMM_FLIP_QUEUE_REFERENCES::ReleaseReference(v198, v74);
      operator delete(*((void **)v78 + 49));
    }
    v199 = (struct VIDMM_CROSSADAPTER_ALLOC *)*((_QWORD *)v78 + 45);
    if ( !v199 )
      goto LABEL_472;
    VIDMM_GLOBAL::FreeCrossAdapterDataDpc(v75, v199, (struct VIDMM_GLOBAL_ALLOC *)v78);
    v200 = (VIDMM_GLOBAL *)(unsigned int)_InterlockedDecrement(*((volatile signed __int32 **)v78 + 45));
    if ( !(_DWORD)v200 )
    {
      VIDMM_GLOBAL::DestroyCrossAdapterAllocation(v200, *((struct VIDMM_CROSSADAPTER_ALLOC **)v78 + 45));
      *v247 = 0;
LABEL_472:
      v201 = *(_QWORD *)v78;
      if ( *(_QWORD *)v78 )
      {
        (*(void (__fastcall **)(struct VIDMM_PHYSICAL_ADAPTER *))(*(_QWORD *)v216 + 40LL))(v216);
        *(_QWORD *)v78 = 0;
      }
      VIDMM_GLOBAL_ALLOC::`scalar deleting destructor'(v78, v201);
      return (unsigned int)v76;
    }
    if ( (int)v200 >= 0 )
      goto LABEL_472;
    v202 = (int *)*((_QWORD *)v78 + 45);
    v203 = *v202;
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 66, v202, v203, 0);
    WdLogGlobalForLineNumber = 227;
LABEL_477:
    _InterlockedIncrement(&dword_140087694);
    WdLogSingleEntry0(6);
    WdLogGlobalForLineNumber = 3828;
    DxgkLogInternalTriageEvent(
      0,
      262145,
      v204,
      (unsigned int)L"Couldn't allocate memory for VIDMM_GLOBAL_ALLOC",
      3828,
      0,
      0,
      0);
    return 3221225495LL;
  }
  v79 = (VIDMM_GLOBAL *)a1;
  if ( !*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 744LL) + 65LL) || (Value & 0x80000) != 0 )
  {
    v212 = v71;
    v93 = operator new[](12, 858810710, 64);
    v94 = v217;
    *(_QWORD *)(*(_QWORD *)v217 + 24LL) = v93;
    v95 = *(volatile signed __int32 **)(*(_QWORD *)v94 + 24LL);
    if ( !v95 )
    {
      _InterlockedIncrement(&dword_14008768C);
      WdLogSingleEntry0(6);
      WdLogGlobalForLineNumber = 3943;
      DxgkLogInternalTriageEvent(
        v96,
        262145,
        v97,
        (unsigned int)L"Couldn't allocate displaying reference array for allocation",
        3943,
        0,
        0,
        0);
      v76 = -1073741801;
      goto LABEL_252;
    }
    _InterlockedIncrement(v95);
    v81 = v212;
    v98 = *(_QWORD *)(*(_QWORD *)v94 + 24LL);
    v99 = v212;
    P = v212;
    *(_DWORD *)(v98 + 4) = -((Value & 0x100000) == 0);
    v80 = v99;
LABEL_269:
    v79 = (VIDMM_GLOBAL *)a1;
  }
  else
  {
    if ( (Value & 0x40000000) != 0 || (int)Value < 0 )
    {
      if ( a2 )
      {
        v84 = operator new(176, 858810710, 64);
        v85 = v217;
        *(_QWORD *)(*(_QWORD *)v217 + 32LL) = v84;
        if ( *(_QWORD *)(*(_QWORD *)v85 + 32LL) )
        {
          PrivateFormat = 0;
          Width = 1000 * (v226[0] + 1);
          v212 = (struct VIDMM_GLOBAL_ALLOC *)P;
          while ( 1 )
          {
            memset(v231, 0, 0x50u);
            v88 = PrivateFormat;
            v89 = v217;
            v231[0] = 5;
            v231[1] = 131;
            v90 = *(_QWORD *)(*(_QWORD *)v217 + 32LL);
            *(_QWORD *)&v231[2] = Width * PrivateFormat + 100LL;
            v91 = (PrivateFormat != 1) + 7;
            *(_QWORD *)(v90 + 8LL * PrivateFormat + 16) = *(_QWORD *)&v231[2];
            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v89 + 32LL) + 32LL) = v212;
            SyncObject = VidSchCreateSyncObject(
                           *(_QWORD *)(*(_QWORD *)(a1 + 16) + 744LL),
                           0,
                           v231,
                           v91,
                           0,
                           0,
                           v226[0],
                           (__int64 *)(*(_QWORD *)(*(_QWORD *)v89 + 32LL) + 8 * v88),
                           0,
                           0,
                           0,
                           a2);
            if ( SyncObject < 0 )
              break;
            if ( (int)++PrivateFormat >= 2 )
            {
              v81 = v212;
              v80 = v212;
              goto LABEL_269;
            }
          }
          v78 = (char *)v212;
          v76 = SyncObject;
          v77 = v212;
        }
        else
        {
          _InterlockedIncrement(&dword_14008768C);
          WdLogSingleEntry0(6);
          WdLogGlobalForLineNumber = 3883;
          DxgkLogInternalTriageEvent(
            v86,
            262145,
            v87,
            (unsigned int)L"Couldn't allocate flip fence state for allocation",
            3883,
            0,
            0,
            0);
          v77 = P;
          v78 = (char *)P;
          v76 = -1073741801;
        }
        goto LABEL_457;
      }
      v76 = 0;
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 3872;
      DxgkLogInternalTriageEvent(v82, 0x40000, v83, (unsigned int)L"pVidMmDevice is not present", 3872, 0, 0, 0);
      goto LABEL_252;
    }
    v80 = v71;
    v212 = v71;
    v81 = v71;
  }
  v100 = v238;
  if ( v238 )
  {
    if ( (*(_DWORD *)(v238 + 4) & 0x8000) != 0 )
    {
      v101 = (_DWORD *)((char *)v81 + 24);
      *((_DWORD *)v81 + 6) |= 0x20u;
    }
    else
    {
      v101 = (_DWORD *)((char *)v80 + 24);
    }
    if ( (*(_DWORD *)(v100 + 4) & 0x10000) != 0 )
    {
      *((_DWORD *)v81 + 7) |= 2u;
      v101 = (_DWORD *)((char *)v81 + 24);
      *((_DWORD *)v81 + 6) |= 0x80000u;
    }
    if ( (*(_DWORD *)(v100 + 4) & 0x8000000) != 0 )
      *v101 |= 0x40u;
  }
  v102 = v223;
  *((_QWORD *)v81 + 45) = v223;
  if ( v102 )
  {
    _InterlockedIncrement((volatile signed __int32 *)v102);
    CrossAdapterDataDpc = VIDMM_GLOBAL::AllocateCrossAdapterDataDpc(v79, v102, v81);
    if ( CrossAdapterDataDpc < 0 )
    {
      v76 = CrossAdapterDataDpc;
      goto LABEL_455;
    }
    v81 = v212;
  }
  v104 = 4096;
  PrivateFormat = 4096;
  if ( g_Feature_ResourcePoolManagement )
  {
    v105 = *(_DWORD *)(*(_QWORD *)(v228 + 40) + 112LL) >> 1;
  }
  else
  {
    v105 = v227;
    LOBYTE(v105) = *(_BYTE *)(v227 + 72);
  }
  LOBYTE(v105) = v105 & 1;
  Width = v105;
  if ( (_BYTE)v105 && (!g_Feature_ResourcePoolManagement || !v240 && !v239) )
  {
    v104 = 0x10000;
    PrivateFormat = 0x10000;
  }
  v106 = v104 - 1;
  LODWORD(v223) = v104 - 1;
  v107 = ~v106 & (v106 + a4);
  v221 = v107;
  if ( a4 > v107 )
  {
    WdLogSingleEntry1(1, a4);
    WdLogGlobalForLineNumber = 4036;
    DxgkLogInternalTriageEvent(
      v108,
      0x40000,
      a4,
      (unsigned int)L"Overflow rounding allocation size (0x%08X) to next page boundary",
      a4,
      0,
      0,
      0);
    v76 = -1073741811;
LABEL_291:
    v78 = (char *)v212;
LABEL_456:
    v77 = P;
    goto LABEL_457;
  }
  v217 = ~v106 & (v222 + v104 - 1);
  if ( v222 > v217 )
  {
    WdLogSingleEntry1(1, v222);
    v111 = v222;
    v112 = L"Overflow rounding allocation pitch aligned size (0x%08X) to next page boundary";
    WdLogGlobalForLineNumber = 4050;
LABEL_294:
    DxgkLogInternalTriageEvent(v109, 0x40000, v110, (_DWORD)v112, v111, 0, 0, 0);
LABEL_295:
    v76 = -1073741811;
    goto LABEL_291;
  }
  if ( v107 > 0xFFFF0000 && (*((_DWORD *)v81 + 7) & 2) == 0 )
  {
    WdLogSingleEntry0(1);
    v111 = 4058;
    v112 = L"Can't create an allocation that uses more than 4GB-64kB of system memory";
    WdLogGlobalForLineNumber = 4058;
    goto LABEL_294;
  }
  if ( (*(_BYTE *)(a1 + 37225) & 0x20) != 0 )
  {
    if ( v12 < 0 )
    {
      LODWORD(v222) = -1;
      v206 = -1;
    }
    else
    {
      LODWORD(v222) = a7;
      v113 = (unsigned int)(4096 << a7);
      v114 = 4096 << a8;
      v220 = v113;
      v206 = a8;
      if ( a8 < a7 )
      {
        WdLogSingleEntry2(3, v114, (unsigned int)v113);
        WdLogGlobalForLineNumber = 4098;
        return 3221225485LL;
      }
      if ( ((v113 - 1) & v107) != 0 )
      {
        WdLogSingleEntry2(3, v107, v220);
        WdLogGlobalForLineNumber = 4113;
        return 3221225485LL;
      }
      if ( v114 > v107 )
      {
        WdLogSingleEntry3(3, v220, v114, v107);
        WdLogGlobalForLineNumber = 4128;
        return 3221225485LL;
      }
      LODWORD(v106) = (_DWORD)v223;
      v104 = PrivateFormat;
    }
    PrivateFormat = a11;
    if ( (Value & 0x8000) == 0 )
      goto LABEL_316;
  }
  else
  {
    PrivateFormat = 0;
    LODWORD(v222) = -1;
    v206 = -1;
  }
  if ( (_DWORD)v220 )
  {
    v115 = ~(_DWORD)v106 & (unsigned int)(v106 + v220);
    if ( (unsigned int)v220 > (unsigned int)v115 )
    {
      v117 = (unsigned int)v220;
      WdLogSingleEntry1(1, (unsigned int)v220);
      WdLogGlobalForLineNumber = 4168;
      DxgkLogInternalTriageEvent(
        v118,
        0x40000,
        v119,
        (unsigned int)L"Overflow rounding allocation alignment (0x%08X) to next page boundary",
        v117,
        0,
        0,
        0);
      goto LABEL_295;
    }
  }
  else
  {
    v115 = v104;
  }
  v220 = v115;
  if ( v107 + (unsigned int)v115 < v107 || v217 + (unsigned int)v115 < v217 )
  {
    WdLogSingleEntry4(1, v107, v217, v107, (unsigned int)v115);
    WdLogGlobalForLineNumber = 4186;
    DxgkLogInternalTriageEvent(
      v221,
      0x40000,
      v194,
      (unsigned int)L"Overflow adding alignment to allocation size, Size=%d, PitchAlignedSize=%d, SystemMemorySize=%d, Alignment=%d",
      v221,
      v217,
      v221,
      (unsigned int)v220);
    v76 = -1073741811;
LABEL_455:
    v78 = (char *)v212;
    goto LABEL_456;
  }
LABEL_316:
  if ( (Value & 0x10000000) != 0 )
    LODWORD(Value) = Value | 8;
  if ( (Value & 0x20000000) == 0 || (Value & 0x10) != 0 )
    v116 = 0;
  else
    v116 = 512;
  v120 = v238;
  v121 = v116 | *((_DWORD *)v81 + 7) & 0xFFFFFDFF;
  *((_DWORD *)v81 + 19) = 0;
  *((_DWORD *)v81 + 7) = v121;
  v122 = (_DWORD *)(v120 + 4);
  **((_DWORD **)v81 + 49) = Value;
  *(_DWORD *)(*((_QWORD *)v81 + 49) + 4LL) = v54;
  v123 = *((_DWORD *)v81 + 6) & 0xFFFFFFFD;
  *((_DWORD *)v81 + 18) = 0;
  *((_DWORD *)v81 + 32) = 0;
  *((_QWORD *)v81 + 1) = v120;
  v124 = (v123 | (2 * (v48 & 1))) ^ ((v123 | (2 * (v48 & 1))) ^ ((unsigned int)v48 >> 1)) & 1;
  v125 = v124 ^ (v124 ^ ((unsigned __int8)v215 << 27)) & 0x8000000;
  v126 = (unsigned __int8)v235;
  LODWORD(v223) = v125;
  *((_DWORD *)v81 + 6) = v125;
  v127 = (32 * (unsigned __int8)SwizzledFormat)
       | (16 * v126) & 0xFFFFFFDF
       | v208.Value & 0xFFFFFFCF
       | Version & 0xFFFFFF8F
       | *((_DWORD *)v81 + 7) & 0xFFFFFF87;
  v128 = v127 ^ ((unsigned __int16)v127 ^ (unsigned __int16)((_WORD)v54 << 12)) & 0x1000;
  *((_DWORD *)v81 + 7) = v128;
  if ( v120 && (*v122 & 0x10000000) != 0 )
    v129 = 0x2000;
  else
    v129 = 0;
  v130 = v129 | v128 & 0xFFFFDFFF;
  v131 = (_DWORD *)*((_QWORD *)v81 + 49);
  v132 = (v245 != 0 ? 0x800000 : 0) | (unsigned int)v223 & 0xFF7FFFFB | (v246 != 0 ? 4 : 0);
  v133 = v130 ^ ((unsigned __int16)v130 ^ (unsigned __int16)((_WORD)v54 << 9)) & 0x8000;
  *((_DWORD *)v81 + 6) = v132;
  *((_DWORD *)v81 + 7) = v133;
  v134 = v133 & 0xFFFEFFFF | ((*v131 & 0xC0000100) != 0 ? 0x10000 : 0);
  v176 = v238 == 0;
  *((_DWORD *)v81 + 7) = v134;
  if ( v176 || (*v122 & 0x40000000) == 0 )
    v135 = 0;
  else
    v135 = 0x20000;
  v136 = v246;
  v137 = v135 | v134 & 0xFFFDFFFF;
  *((_DWORD *)v81 + 7) = v137;
  if ( v136 )
  {
    *((_QWORD *)v81 + 8) = v136;
  }
  else if ( v245 )
  {
    *((_QWORD *)v81 + 8) = v245;
  }
  else
  {
    v138 = v248;
    if ( v248 )
    {
      *((_QWORD *)v81 + 8) = v248;
      *((_DWORD *)v81 + 7) = v137 | 0x4000;
      *((_DWORD *)v81 + 6) = v132 & 0xFFFFFF7F | ~((unsigned __int8)*(_DWORD *)(v138 + 176) << 6) & 0x80;
    }
  }
  v139 = VidMmiSelectAllocationHeap((__int64)v224, (__int64)v81, *(_DWORD *)(a1 + 41448));
  *(_QWORD *)(v140 + 232) = v139;
  if ( v139 && (*(unsigned __int8 (__fastcall **)(struct VIDMM_EXISTINGSYSMEM_HEAP *))(*(_QWORD *)v139 + 120LL))(v139) )
    v141 = v207;
  else
    v141 = 1;
  v142 = v212;
  v143 = (v141 << 7) | *((_DWORD *)v212 + 7) & 0xFFFFFF7F;
  v144 = 0;
  *((_DWORD *)v212 + 7) = v143;
  LOBYTE(v235) = 0;
  if ( (Value & 1) != 0 && (v143 & 0x80u) == 0 && !(_BYTE)Width )
  {
    v144 = ((*(_DWORD *)(*(_QWORD *)(a1 + 24) + 444LL) & 8) != 0 || VidMmCheckForCpuVisibleMemorySegment(v216, a9))
        && !v136
        && (*((_DWORD *)v142 + 6) & 2) == 0;
    LOBYTE(v235) = v144;
  }
  v145 = v216;
  v146 = v217;
  v147 = v221;
  *((_DWORD *)v142 + 7) = (v144 << 10) | *((_DWORD *)v142 + 7) & 0xFFFFFBFF;
  v205 = v226[0];
  v76 = (*(__int64 (__fastcall **)(struct VIDMM_PHYSICAL_ADAPTER *, struct VIDMM_GLOBAL_ALLOC *, unsigned __int64, unsigned __int64, unsigned __int64, _DWORD, int, _DWORD, unsigned int))(*(_QWORD *)v145 + 32LL))(
          v145,
          v142,
          a4,
          v147,
          v146,
          v222,
          v206,
          v220,
          a9);
  if ( v76 < 0 )
    goto LABEL_455;
  v176 = (_BYTE)Width == 0;
  v148 = v212;
  *(_QWORD *)v212 = v225;
  if ( v176 )
  {
    if ( (dword_1400875B4
       || (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 36480) + 8LL * (unsigned int)v226[0]) + 44LL) & 1) != 0)
      && (**(_DWORD **)(*(_QWORD *)(a1 + 24) + 3136LL) & 0x4000) == 0
      && (v48 & 2) != 0
      && v230
      && ((*v230 & 0x200) != 0 || dword_1400875B4 == 2)
      && ((v149 = *(_QWORD *)(v225 + 16), !(_WORD)v149) || v149 > (unsigned int)dword_1400875B8)
      && !(_BYTE)v235 )
    {
      v150 = 0x10000000;
    }
    else
    {
      v150 = 0;
    }
    *((_DWORD *)v148 + 6) = v150 | *((_DWORD *)v148 + 6) & 0xEFFFFFFF;
    if ( g_Feature_Largify64KBPrototype )
    {
      v151 = *((_DWORD *)v148 + 6);
      if ( (v151 & 0x18000000) == 0x18000000 )
      {
        v152 = *((_DWORD *)v148 + 7);
        if ( (v152 & 0x4200) == 0
          && (v151 & 0x800004) == 0
          && (Value & 8) == 0
          && (Value & 0x20000) == 0
          && (Value & 0x8000000) == 0
          && (Value & 0x4000) == 0
          && ((v152 & 0x8000) != 0 || (*(_DWORD *)(*(_QWORD *)(a1 + 24) + 444LL) & 8) != 0)
          && ((*((_BYTE *)v216 + 1350) & 8) != 0
           || (v153 = (_DWORD *)*((_QWORD *)v216 + 169)) != 0 && (*v153 & 0x80u) != 0) )
        {
          *((_DWORD *)v148 + 6) |= 0x20000000u;
        }
      }
    }
  }
  else
  {
    *((_DWORD *)v148 + 6) |= 0x10000000u;
  }
  if ( (*((_DWORD *)v148 + 7) & 0x8000) != 0
    && (*((_DWORD *)v148 + 6) & 0x20000000) == 0
    && (*((_DWORD *)DXGGLOBAL::GetGlobal() + 64) & 0x20) != 0 )
  {
    if ( (*((_DWORD *)v148 + 6) & 0x10000000) != 0 )
    {
      v158 = 1;
      if ( (*((_BYTE *)v216 + 1350) & 8) == 0 )
      {
        v157 = (_DWORD *)*((_QWORD *)v216 + 169);
        if ( !v157 || (*v157 & 0x80u) == 0 )
          v158 = 0;
      }
      v159 = *((_DWORD *)v148 + 6);
      v160 = (v159 & 0x8000000) == 0
          || (*((_DWORD *)v148 + 7) & 0x4200) != 0
          || (v159 & 0x800004) != 0
          || (Value & 8) != 0
          || (Value & 0x20000) != 0
          || (Value & 0x8000000) != 0
          || (Value & 0x4000) != 0;
      WdLogSingleEntry3(4, v160, g_Feature_Largify64KBPrototype, v158);
      WdLogGlobalForLineNumber = 4393;
    }
    else
    {
      v154 = *(_QWORD *)(v225 + 16);
      v155 = !(_WORD)v154 || v154 > (unsigned int)dword_1400875B8;
      v156 = v230 && ((*v230 & 0x200) != 0 || dword_1400875B4 == 2);
      WdLogSingleEntry5(
        4,
        (unsigned int)dword_1400875B4,
        *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 36480) + 8LL * (unsigned int)v226[0]) + 44LL) & 1,
        (v48 >> 1) & 1,
        v156,
        v155);
      WdLogGlobalForLineNumber = 4372;
      WdLogSingleEntry1(4, (unsigned __int8)v235 ^ 1LL);
      WdLogGlobalForLineNumber = 4374;
    }
    __debugbreak();
  }
  v161 = v242;
  if ( v238 )
    v161 = *(_QWORD *)(v238 + 16);
  v78 = (char *)v212;
  *(_QWORD *)(*((_QWORD *)v212 + 49) + 48LL) = v161;
  if ( v239 )
  {
    v162 = v239;
  }
  else
  {
    v162 = (void *)v240;
    if ( !v240 && v241 )
      v162 = v241;
  }
  v76 = VIDMM_GLOBAL::CommitGlobalBackingStore((VIDMM_GLOBAL *)a1, (struct VIDMM_GLOBAL_ALLOC *)v78, v224, v162, v250);
  if ( v76 < 0 )
    goto LABEL_456;
  if ( (Value & 0x4000) != 0 )
    *((_DWORD *)v78 + 6) |= 0x2000000u;
  *((_DWORD *)v78 + 6) ^= (*((_DWORD *)v78 + 6) ^ ((unsigned __int8)v244 << 24)) & 0x1000000;
  *(_DWORD *)(v225 + 56) = v243;
  v163 = v216;
  *((_QWORD *)v78 + 15) = v78 + 112;
  *((_QWORD *)v78 + 14) = v78 + 112;
  LOBYTE(v235) = (*((_DWORD *)v78 + 6) & 2) != 0;
  MostPreferredSegment = (const struct VIDMM_SEGMENT_BASE *)VidMmGetMostPreferredSegment(v163, v31, (__int64 *)va);
  *((_DWORD *)v78 + 6) = v165 ^ (v165 ^ (16 * (unsigned __int8)v235)) & 0x10;
  v166 = VidMmVerifyBudgetGroups(v216, a9, MostPreferredSegment, (struct _VIDMM_VERIFY_BUDGET_GROUPS *)&Height);
  v167 = 0;
  if ( !v166 )
  {
    v76 = -1073741811;
    goto LABEL_456;
  }
  *((_DWORD *)v78 + 6) = ((unsigned __int8)Height << 8) | *((_DWORD *)v78 + 6) & 0xFFFF00FF;
  if ( (Value & 0x10) != 0 || (Value & 0x20) != 0 )
    v78[42] = 1;
  v168 = v221;
  if ( !v246 )
  {
    LogicalMemory = SysMmAllocateLogicalMemory(
                      *(struct SYSMM_ADAPTER **)(*(_QWORD *)(a1 + 24) + 224LL),
                      v221,
                      v78,
                      (void **)v78 + 46);
    v167 = 0;
    v76 = LogicalMemory;
    if ( LogicalMemory < 0 )
    {
      WdLogSingleEntry1(1, v78);
      WdLogGlobalForLineNumber = 4491;
      DxgkLogInternalTriageEvent(
        v170,
        0x40000,
        v171,
        (unsigned int)L"Failed to allocate logical address range for global alloc 0x%.16I64x",
        (__int64)v78,
        0,
        0,
        0);
      goto LABEL_456;
    }
  }
  if ( g_Feature_ResourcePoolManagement )
  {
    v172 = v228;
    v173 = v227;
    *((_QWORD *)v78 + 44) = *(_QWORD *)(v228 + 32) + 384LL * *(unsigned int *)(*(_QWORD *)(a1 + 24) + 240LL);
    v174 = (volatile signed __int32 *)(v172 + 24);
  }
  else
  {
    v175 = VIDMM_GLOBAL::AdapterId((VIDMM_GLOBAL *)a1);
    v172 = v228;
    v173 = v227;
    *((_QWORD *)v78 + 43) = *(_QWORD *)(v227 + 40) + 384LL * v175;
    v174 = (volatile signed __int32 *)(v173 + 36);
  }
  _InterlockedIncrement(v174);
  if ( g_Feature_ResourcePoolManagement == (_BYTE)v167 )
    v176 = *(_DWORD *)(v173 + 32) == v167;
  else
    v176 = *(_DWORD *)(*(_QWORD *)(v172 + 40) + 96LL) == v167;
  if ( !v176
    || (v177 = **((_DWORD **)v78 + 49), (v177 & 0x2003A) != 0)
    || (v178 = *((_DWORD *)v78 + 7), (v178 & 0x10) != 0)
    || (*((_DWORD *)v78 + 6) & 4) != 0
    || (v178 & 2) != 0
    || (v177 & 0x40000000) != 0 )
  {
    LODWORD(v229) = v167;
  }
  *((_DWORD *)v78 + 7) = v229 | *((_DWORD *)v78 + 7) & 0xFFFFFEFF;
  AllocationHint = VidMmGetAllocationHint((const struct VIDMM_GLOBAL_ALLOC *)v78);
  if ( (byte_140087201 & 0x10) != 0 )
  {
    v185 = v184;
    LOBYTE(v186) = v184;
    LOBYTE(v185) = v183 != 0;
    LODWORD(v235) = v185;
    LODWORD(v248) = AllocationHint->v1.Depth;
    LODWORD(v223) = AllocationHint->v1.Pitch;
    Height = AllocationHint->v1.Height;
    Width = AllocationHint->v1.Width;
    LODWORD(v222) = AllocationHint->v1.ByteOffset;
    SwizzledFormat = AllocationHint->v1.SwizzledFormat;
    PrivateFormat = AllocationHint->v1.PrivateFormat;
    v187 = (struct _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0::$5068715F5D8591D41DA1228877FDA04B::$63766B29C143116E9EC685C38896947D)AllocationHint->v1.Flags.Value;
    Version = AllocationHint->Version;
    v230 = (_DWORD *)*((_QWORD *)v78 + 1);
    v217 = *(_QWORD *)(v182 + 24);
    v208.0 = v187;
    if ( a2 )
      v186 = *((_QWORD *)a2 + 3);
    CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
    McTemplateK0pppqxqqqqqqqpppqqqqqqqqqqtphtp_EtwWriteTransfer(
      v217,
      (unsigned int)&EventCreateAdapterAllocation,
      v189,
      CurrentProcessId,
      v186,
      v217,
      v12,
      v168,
      v220,
      a10,
      a9,
      v31,
      v205,
      a10,
      v243,
      (char)v78,
      (char)v230);
    LOBYTE(v184) = 0;
  }
  _InterlockedAdd((volatile signed __int32 *)(a1 + 3760), 1u);
  _InterlockedAdd64((volatile signed __int64 *)(a1 + 3768), v168);
  _InterlockedAdd64((volatile signed __int64 *)(a1 + 36448), v168);
  if ( a2 )
  {
    v190 = *((_QWORD *)a2 + 2);
    if ( v190 )
    {
      BucketIdForAllocationSizePow2 = (unsigned int)GetBucketIdForAllocationSizePow2(
                                                      v168,
                                                      BucketIdForAllocationSizePow2,
                                                      *(_QWORD *)(v190 + 184));
      _InterlockedAdd64((volatile signed __int64 *)(v191 + 8 * BucketIdForAllocationSizePow2 + 56), v168);
      _InterlockedAdd((volatile signed __int32 *)(v191 + 4 * BucketIdForAllocationSizePow2 + 232), v192);
      *(_BYTE *)(v191 + 320) = v192;
    }
  }
  if ( g_IsInternalReleaseOrDbg != (_BYTE)v184 )
  {
    *(_QWORD *)(WdLogNewEntry5_WdTrace(v181, BucketIdForAllocationSizePow2) + 24) = v78;
    WdLogGlobalForLineNumber = 4610;
  }
  *v249 = v78;
  return 0;
}

```

## disassembly

```asm
0x1400b4cd8  mov     rax, rsp
0x1400b4cdb  mov     [rax+18h], rbx
0x1400b4cdf  mov     [rax+20h], r9
0x1400b4ce3  mov     [rax+10h], rdx
0x1400b4ce7  mov     [rax+8], rcx
0x1400b4ceb  push    rbp
0x1400b4cec  push    rsi
0x1400b4ced  push    rdi
0x1400b4cee  push    r12
0x1400b4cf0  push    r13
0x1400b4cf2  push    r14
0x1400b4cf4  push    r15
0x1400b4cf6  lea     rbp, [rsp-80h]
0x1400b4cfb  sub     rsp, 210h
0x1400b4d02  mov     r13d, dword ptr [rbp+0B0h+arg_60]
0x1400b4d09  mov     rsi, r9
0x1400b4d0c  mov     ebx, r13d
0x1400b4d0f  mov     edi, r8d
0x1400b4d12  mov     dword ptr [rbp+0B0h+var_128], ebx
0x1400b4d15  mov     r15, rdx
0x1400b4d18  mov     r14, rcx
0x1400b4d1b  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x1400b4d20  mov     rdx, [rbp+0B0h+arg_C0]
0x1400b4d27  xor     r11d, r11d
0x1400b4d2a  mov     [rbp+0B0h+var_D8], rax
0x1400b4d2e  mov     rcx, rax
0x1400b4d31  mov     r8d, 1
0x1400b4d37  test    rdx, rdx
0x1400b4d3a  jz      short loc_1400B4D4E
0x1400b4d3c  mov     edx, [rdx+0B0h]
0x1400b4d42  mov     byte ptr [rbp+0B0h+arg_60], r8b
0x1400b4d49  test    r8b, dl
0x1400b4d4c  jz      short loc_1400B4D55
0x1400b4d4e  mov     byte ptr [rbp+0B0h+arg_60], r11b
0x1400b4d55  test    r15, r15
0x1400b4d58  jz      short loc_1400B4D60
0x1400b4d5a  mov     r9, [r15+8]
0x1400b4d5e  jmp     short loc_1400B4D7B
0x1400b4d60  test    rcx, rcx
0x1400b4d63  jz      loc_1400B6F00
0x1400b4d69  mov     rax, [rax+40h]
0x1400b4d6d  test    rax, rax
0x1400b4d70  jz      short loc_1400B4D78
0x1400b4d72  mov     r9, [rax+8]
0x1400b4d76  jmp     short loc_1400B4D7B
0x1400b4d78  mov     r9, r11
0x1400b4d7b  mov     eax, dword ptr [rbp+0B0h+arg_98]
0x1400b4d81  mov     edx, 2
0x1400b4d86  cmp     eax, edx
0x1400b4d88  mov     [rbp+0B0h+var_C0], r9
0x1400b4d8c  cmovbe  eax, edx
0x1400b4d8f  mov     dword ptr [rbp+0B0h+arg_98], eax
0x1400b4d95  test    rcx, rcx
0x1400b4d98  jz      short loc_1400B4DCD
0x1400b4d9a  mov     ecx, [rcx+198h]
0x1400b4da0  mov     eax, ecx
0x1400b4da2  shr     eax, 8
0x1400b4da5  test    r8b, al
0x1400b4da8  jz      short loc_1400B4DCD
0x1400b4daa  shr     ecx, 0Ah
0x1400b4dad  mov     [rbp+0B0h+var_120], r8b
0x1400b4db1  test    r8b, cl
0x1400b4db4  jnz     short loc_1400B4DD1
0x1400b4db6  cmp     [rbp+0B0h+arg_A8], r11
0x1400b4dbd  jnz     short loc_1400B4DD1
0x1400b4dbf  test    r8b, r13b
0x1400b4dc2  jz      short loc_1400B4DD1
0x1400b4dc4  btr     ebx, 0Fh
0x1400b4dc8  mov     dword ptr [rbp+0B0h+var_128], ebx
0x1400b4dcb  jmp     short loc_1400B4DD1
0x1400b4dcd  mov     [rbp+0B0h+var_120], r11b
0x1400b4dd1  cmp     cs:?g_Feature_ResourcePoolManagement@@3_NA, r11b; bool g_Feature_ResourcePoolManagement
0x1400b4dd8  jz      short loc_1400B4DEB
0x1400b4dda  mov     r10, [r9+170h]
0x1400b4de1  mov     [rbp+0B0h+var_A0], r10
0x1400b4de5  mov     [rbp+0B0h+var_A8], r11
0x1400b4de9  jmp     short loc_1400B4DFA
0x1400b4deb  mov     rax, [r9+158h]
0x1400b4df2  mov     [rbp+0B0h+var_A8], rax
0x1400b4df6  mov     [rbp+0B0h+var_A0], r11
0x1400b4dfa  cmp     [r14+0C28h], r8d
0x1400b4e01  mov     ecx, r11d
0x1400b4e04  mov     rax, [r14+8E80h]
0x1400b4e0b  lea     r8, [rbp+0B0h+var_F0]; struct VIDMM_SEGMENT_PREFERENCES *
0x1400b4e0f  mov     edx, dword ptr [rbp+0B0h+arg_58]; struct _D3DDDI_SEGMENTPREFERENCE
0x1400b4e15  cmovnz  ecx, edi
0x1400b4e18  mov     qword ptr [rbp+0B0h+var_B0], rcx
0x1400b4e1c  mov     [rbp+0B0h+var_F0], r11
0x1400b4e20  mov     rax, [rax+rcx*8]
0x1400b4e24  mov     [rbp+0B0h+var_F8], rax
0x1400b4e28  mov     rcx, [rax+548h]
0x1400b4e2f  mov     [rbp+0B0h+var_90], rcx
0x1400b4e33  mov     rcx, r14; struct VIDMM_GLOBAL *
0x1400b4e36  call    ?VidMmConvertSegmentPreferences@@YAXPEBVVIDMM_GLOBAL@@U_D3DDDI_SEGMENTPREFERENCE@@PEAUVIDMM_SEGMENT_PREFERENCES@@@Z; VidMmConvertSegmentPreferences(VIDMM_GLOBAL const *,_D3DDDI_SEGMENTPREFERENCE,VIDMM_SEGMENT_PREFERENCES *)
0x1400b4e3b  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400b4e42  mov     edi, [rbp+0B0h+arg_28]
0x1400b4e48  mov     r12, [rbp+0B0h+var_F0]
0x1400b4e4c  mov     [rbp+0B0h+var_E0], rdi
0x1400b4e50  cmp     [rax], r11b
0x1400b4e53  jz      loc_1400B4EFF
0x1400b4e59  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400b4e60  nop     dword ptr [rax+rax+00h]
0x1400b4e65  xor     r11d, r11d
0x1400b4e68  mov     [rax+18h], r15
0x1400b4e6c  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400b4e73  mov     cs:WdLogGlobalForLineNumber, 0BBFh
0x1400b4e7d  cmp     [rax], r11b
0x1400b4e80  jz      short loc_1400B4EFB
0x1400b4e82  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400b4e89  nop     dword ptr [rax+rax+00h]
0x1400b4e8e  mov     ecx, [rbp+0B0h+arg_40]
0x1400b4e94  xor     r11d, r11d
0x1400b4e97  mov     [rax+18h], rsi
0x1400b4e9b  mov     [rax+20h], rdi
0x1400b4e9f  mov     [rax+28h], rcx
0x1400b4ea3  mov     ecx, [rbp+0B0h+arg_48]
0x1400b4ea9  mov     [rax+30h], rcx
0x1400b4ead  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400b4eb4  mov     cs:WdLogGlobalForLineNumber, 0BC4h
0x1400b4ebe  cmp     [rax], r11b
0x1400b4ec1  jz      short loc_1400B4EFB
0x1400b4ec3  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400b4eca  nop     dword ptr [rax+rax+00h]
0x1400b4ecf  mov     ecx, r12d
0x1400b4ed2  xor     r11d, r11d
0x1400b4ed5  mov     [rax+18h], rcx
0x1400b4ed9  mov     ecx, dword ptr [rbp+0B0h+var_F0+4]
0x1400b4edc  mov     [rax+20h], rcx
0x1400b4ee0  mov     ecx, ebx
0x1400b4ee2  mov     [rax+28h], rcx
0x1400b4ee6  mov     rcx, [rbp+0B0h+arg_70]
0x1400b4eed  mov     [rax+30h], rcx
0x1400b4ef1  mov     cs:WdLogGlobalForLineNumber, 0BC9h
0x1400b4efb  mov     r9, [rbp+0B0h+var_C0]
0x1400b4eff  mov     rax, [rbp+0B0h+arg_C8]
0x1400b4f06  mov     edi, 40000h
0x1400b4f0b  mov     [rax], r11
0x1400b4f0e  cmp     dword ptr [r14+28h], 5023h
0x1400b4f16  jnb     short loc_1400B4F40
0x1400b4f18  test    edi, ebx
0x1400b4f1a  jz      short loc_1400B4F40
0x1400b4f1c  mov     ecx, 1
0x1400b4f21  call    cs:__imp_WdLogSingleEntry0
0x1400b4f28  nop     dword ptr [rax+rax+00h]
0x1400b4f2d  mov     eax, 0BD9h
0x1400b4f32  lea     r9, aCpuvisibleonde_1; "CpuVisibleOnDemand flag set, but on thi"...
0x1400b4f39  mov     edx, edi
0x1400b4f3b  jmp     loc_1400B6F20
0x1400b4f40  mov     esi, 10h
0x1400b4f45  lea     r15d, [rsi+10h]
0x1400b4f49  bt      ebx, 11h
0x1400b4f4d  jnb     short loc_1400B4FA8
0x1400b4f4f  test    bl, 2
0x1400b4f52  jnz     loc_1400B5092
0x1400b4f58  test    bl, 4
0x1400b4f5b  jz      short loc_1400B4F70
0x1400b4f5d  mov     rax, [r14+18h]
0x1400b4f61  mov     ecx, [rax+1BCh]
0x1400b4f67  test    cl, 8
0x1400b4f6a  jz      loc_1400B5092
0x1400b4f70  bt      ebx, 14h
0x1400b4f74  jb      loc_1400B5092
0x1400b4f7a  bt      ebx, 13h
0x1400b4f7e  jb      loc_1400B5092
0x1400b4f84  test    bl, 8
0x1400b4f87  jnz     loc_1400B5092
0x1400b4f8d  test    sil, bl
0x1400b4f90  jnz     loc_1400B5092
0x1400b4f96  test    r15b, bl
0x1400b4f99  jnz     loc_1400B5092
0x1400b4f9f  and     ebx, 0FFFBFFFEh
0x1400b4fa5  mov     dword ptr [rbp+0B0h+var_128], ebx
0x1400b4fa8  mov     eax, 1
0x1400b4fad  test    al, bl
0x1400b4faf  jz      short loc_1400B4FB5
0x1400b4fb1  test    edi, ebx
0x1400b4fb3  jz      short loc_1400B4FBE
0x1400b4fb5  mov     byte ptr [rbp+0B0h+var_100], r11b
0x1400b4fb9  test    sil, bl
0x1400b4fbc  jz      short loc_1400B4FC1
0x1400b4fbe  mov     byte ptr [rbp+0B0h+var_100], al
0x1400b4fc1  mov     r14b, byte ptr [rbp+0B0h+arg_60]
0x1400b4fc8  test    r14b, r14b
0x1400b4fcb  jnz     short loc_1400B4FD8
0x1400b4fcd  test    bl, 8
0x1400b4fd0  jnz     short loc_1400B4FD8
0x1400b4fd2  bt      ebx, 11h
0x1400b4fd6  jnb     short loc_1400B4FDC
0x1400b4fd8  mov     byte ptr [rbp+0B0h+var_100], r11b
0x1400b4fdc  mov     eax, [r9+0A0h]
0x1400b4fe3  test    al, 40h
0x1400b4fe5  jnz     short loc_1400B5053
0x1400b4fe7  call    cs:__imp_PsGetCurrentProcess
0x1400b4fee  nop     dword ptr [rax+rax+00h]
0x1400b4ff3  mov     rcx, rax
0x1400b4ff6  call    cs:__imp_PsGetProcessWow64Process
0x1400b4ffd  nop     dword ptr [rax+rax+00h]
0x1400b5002  xor     r11d, r11d
0x1400b5005  test    rax, rax
0x1400b5008  jnz     short loc_1400B5053
0x1400b500a  bt      ebx, 1Dh
0x1400b500e  jb      short loc_1400B5053
0x1400b5010  bt      ebx, 1Eh
0x1400b5014  jb      short loc_1400B5053
0x1400b5016  test    ebx, ebx
0x1400b5018  js      short loc_1400B5053
0x1400b501a  bt      ebx, 1Ch
0x1400b501e  jb      short loc_1400B5053
0x1400b5020  test    bl, 8
0x1400b5023  jnz     short loc_1400B5053
0x1400b5025  bt      ebx, 16h
0x1400b5029  jb      short loc_1400B5053
0x1400b502b  bt      ebx, 11h
0x1400b502f  jb      short loc_1400B5053
0x1400b5031  test    r14b, r14b
0x1400b5034  jnz     short loc_1400B5053
0x1400b5036  cmp     [rbp+0B0h+arg_A8], r11
0x1400b503d  jnz     short loc_1400B5053
0x1400b503f  cmp     [rbp+0B0h+arg_B0], r11
0x1400b5046  jnz     short loc_1400B5053
0x1400b5048  btr     ebx, 12h
0x1400b504c  mov     byte ptr [rbp+0B0h+var_100], 1
0x1400b5050  mov     dword ptr [rbp+0B0h+var_128], ebx
0x1400b5053  mov     r14d, ebx
0x1400b5056  shr     r14d, 0Dh
0x1400b505a  and     r14d, 1
0x1400b505e  jz      short loc_1400B50B4
0x1400b5060  mov     rax, [rbp+0B0h+arg_0]
0x1400b5067  test    byte ptr [rax+9169h], 8
0x1400b506e  jnz     short loc_1400B50B4
0x1400b5070  mov     ecx, 1
0x1400b5075  call    cs:__imp_WdLogSingleEntry0
0x1400b507c  nop     dword ptr [rax+rax+00h]
0x1400b5081  mov     eax, 0C46h
0x1400b5086  lea     r9, aDriversMustSup; "Drivers must support MapAperture2 to se"...
0x1400b508d  jmp     loc_1400B4F39
0x1400b5092  mov     ecx, 1
0x1400b5097  call    cs:__imp_WdLogSingleEntry0
0x1400b509e  nop     dword ptr [rax+rax+00h]
0x1400b50a3  mov     eax, 0BEFh
0x1400b50a8  lea     r9, aHardwareprotec_2; "HardwareProtected allocations cannot be"...
0x1400b50af  jmp     loc_1400B4F39
0x1400b50b4  mov     r8d, [rbp+0B0h+arg_40]
0x1400b50bb  mov     rdx, r12
0x1400b50be  mov     rcx, [rbp+0B0h+var_F8]
0x1400b50c2  call    ?VidMmValidatePreferredSegment@@YA_NPEBUVIDMM_PHYSICAL_ADAPTER@@UVIDMM_SEGMENT_PREFERENCES@@I@Z; VidMmValidatePreferredSegment(VIDMM_PHYSICAL_ADAPTER const *,VIDMM_SEGMENT_PREFERENCES,uint)
0x1400b50c7  xor     r8d, r8d
0x1400b50ca  test    al, al
0x1400b50cc  jnz     short loc_1400B50EF
0x1400b50ce  lea     ecx, [r8+1]
0x1400b50d2  call    cs:__imp_WdLogSingleEntry0
0x1400b50d9  nop     dword ptr [rax+rax+00h]
0x1400b50de  mov     eax, 0C50h
0x1400b50e3  lea     r9, aSpecifiedPrefe; "Specified preferred segment is invalid."...
0x1400b50ea  jmp     loc_1400B4F39
0x1400b50ef  cmp     cs:dword_1400875B0, r8d
0x1400b50f6  mov     r9d, 1
0x1400b50fc  jz      short loc_1400B5139
0x1400b50fe  test    r9b, bl
0x1400b5101  jnz     short loc_1400B5139
0x1400b5103  mov     r10, [rbp+0B0h+var_F8]
0x1400b5107  mov     ecx, r12d
0x1400b510a  and     ecx, 1Fh
0x1400b510d  jnz     short loc_1400B512A
0x1400b510f  mov     eax, [rbp+0B0h+arg_40]
0x1400b5115  and     eax, [r10+54h]
0x1400b5119  cmovz   eax, [rbp+0B0h+arg_40]
0x1400b5120  mov     edx, eax
0x1400b5122  mov     [rbp+0B0h+arg_40], eax
0x1400b5128  jmp     short loc_1400B5143
0x1400b512a  dec     ecx
0x1400b512c  mov     edx, r9d
0x1400b512f  shl     edx, cl
0x1400b5131  mov     [rbp+0B0h+arg_40], edx
0x1400b5137  jmp     short loc_1400B5143
0x1400b5139  mov     edx, [rbp+0B0h+arg_40]; unsigned int
0x1400b513f  mov     r10, [rbp+0B0h+var_F8]
0x1400b5143  mov     rcx, [rbp+0B0h+arg_18]
0x1400b514a  test    rcx, rcx
0x1400b514d  jnz     short loc_1400B516F
0x1400b514f  mov     ecx, r9d
0x1400b5152  call    cs:__imp_WdLogSingleEntry0
0x1400b5159  nop     dword ptr [rax+rax+00h]
0x1400b515e  mov     eax, 0C79h
0x1400b5163  lea     r9, aCanTCreateAnAl_0; "Can't create an allocation of zero size"
0x1400b516a  jmp     loc_1400B4F39
0x1400b516f  test    r14d, r14d
0x1400b5172  jz      short loc_1400B51B6
0x1400b5174  mov     rax, [rbp+0B0h+arg_0]
0x1400b517b  mov     rax, [rax+10h]
0x1400b517f  mov     rcx, [rax+10h]
0x1400b5183  cmp     dword ptr [rcx+0C3Ch], 0B54h
0x1400b518d  jge     short loc_1400B51AF
0x1400b518f  mov     ecx, r9d
0x1400b5192  call    cs:__imp_WdLogSingleEntry0
0x1400b5199  nop     dword ptr [rax+rax+00h]
0x1400b519e  mov     eax, 0C83h
0x1400b51a3  lea     r9, aLinkinstancedM; "LinkInstanced/MapApertureCpuVisible fla"...
0x1400b51aa  jmp     loc_1400B4F39
0x1400b51af  mov     rcx, [rbp+0B0h+arg_18]
  ... truncated ...
```
