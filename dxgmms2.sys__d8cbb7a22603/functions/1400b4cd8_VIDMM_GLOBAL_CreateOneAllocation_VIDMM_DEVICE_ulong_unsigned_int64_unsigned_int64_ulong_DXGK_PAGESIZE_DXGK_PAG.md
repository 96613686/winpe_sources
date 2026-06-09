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
  __int64 v27; // rcx
  struct VIDMM_PROCESS *v28; // r9
  __int64 v29; // r11
  unsigned __int64 v30; // r12
  __int64 v31; // rax
  __int64 v32; // rcx
  _QWORD *v33; // rax
  _QWORD *v34; // rax
  int v35; // r8d
  __int64 v36; // rax
  const wchar_t *v37; // r9
  char v38; // r14
  __int64 CurrentProcess; // rax
  struct VIDMM_PHYSICAL_ADAPTER *v40; // r10
  int v41; // eax
  unsigned int v42; // edx
  unsigned __int64 v43; // rcx
  __int64 Value; // rbx
  unsigned __int64 v45; // r14
  unsigned int v46; // edx
  unsigned int v47; // ecx
  __int64 v48; // r11
  unsigned int v49; // r10d
  unsigned int v50; // eax
  int v51; // edi
  unsigned int v52; // edx
  unsigned int v53; // r8d
  int v54; // r10d
  int v55; // ecx
  int v56; // eax
  int v57; // eax
  int v58; // edx
  int v59; // ecx
  int v60; // r8d
  const wchar_t *v61; // r9
  UINT v62; // edx
  int v63; // ecx
  int v64; // r8d
  __int64 v65; // rax
  _QWORD *v66; // rax
  __int64 v67; // rax
  struct VIDMM_GLOBAL_ALLOC *v68; // rdx
  int v69; // ecx
  int v70; // r8d
  unsigned int v71; // edx
  VIDMM_GLOBAL *v72; // rcx
  int v73; // edi
  _QWORD *v74; // rbx
  char *v75; // r14
  VIDMM_GLOBAL *v76; // r9
  struct VIDMM_GLOBAL_ALLOC *v77; // rcx
  struct VIDMM_GLOBAL_ALLOC *v78; // r10
  int v79; // ecx
  int v80; // r8d
  __int64 v81; // rax
  unsigned __int64 v82; // rdx
  int v83; // ecx
  int v84; // r8d
  __int64 v85; // r11
  unsigned __int64 v86; // r10
  __int64 v87; // rcx
  int v88; // r9d
  int SyncObject; // eax
  __int64 v90; // rax
  unsigned __int64 v91; // r8
  volatile signed __int32 *v92; // rcx
  int v93; // ecx
  int v94; // r8d
  __int64 v95; // rcx
  struct VIDMM_GLOBAL_ALLOC *v96; // rax
  __int64 v97; // rdx
  _DWORD *v98; // rcx
  struct VIDMM_CROSSADAPTER_ALLOC *v99; // rax
  int CrossAdapterDataDpc; // eax
  unsigned int v101; // r9d
  int v102; // eax
  __int64 v103; // r8
  unsigned __int64 v104; // rdx
  int v105; // ecx
  int v106; // ecx
  int v107; // r8d
  __int64 v108; // rax
  const wchar_t *v109; // r9
  __int64 v110; // rax
  unsigned int v111; // r9d
  __int64 v112; // rax
  int v113; // ecx
  __int64 v114; // rbx
  int v115; // ecx
  int v116; // r8d
  __int64 v117; // r8
  unsigned int v118; // eax
  _DWORD *v119; // r9
  unsigned int v120; // eax
  int v121; // eax
  int v122; // ecx
  int v123; // eax
  unsigned int v124; // ecx
  int v125; // edx
  int v126; // eax
  unsigned int v127; // edx
  _DWORD *v128; // rax
  unsigned int v129; // r8d
  int v130; // edi
  unsigned int v131; // edx
  int v132; // eax
  __int64 v133; // rdi
  unsigned int v134; // edx
  __int64 v135; // rax
  __int64 v136; // rax
  __int64 v137; // r10
  unsigned __int8 v138; // al
  struct VIDMM_GLOBAL_ALLOC *v139; // r11
  unsigned int v140; // ecx
  bool v141; // al
  struct VIDMM_PHYSICAL_ADAPTER *v142; // r10
  unsigned __int64 v143; // rdx
  unsigned __int64 v144; // r9
  struct VIDMM_GLOBAL_ALLOC *v145; // rdi
  unsigned __int64 v146; // rcx
  int v147; // ecx
  int v148; // ecx
  int v149; // eax
  _DWORD *v150; // rax
  unsigned __int64 v151; // rcx
  _BOOL8 v152; // r10
  _BOOL8 v153; // r9
  _DWORD *v154; // rax
  _BOOL8 v155; // r9
  int v156; // ecx
  _BOOL8 v157; // rdx
  __int64 v158; // rcx
  void *v159; // rcx
  struct VIDMM_PHYSICAL_ADAPTER *v160; // rcx
  const struct VIDMM_SEGMENT_BASE *MostPreferredSegment; // rax
  int v162; // r11d
  bool v163; // al
  int v164; // r10d
  unsigned __int64 v165; // rbx
  int LogicalMemory; // eax
  int v167; // ecx
  int v168; // r8d
  __int64 v169; // rdx
  __int64 v170; // rcx
  volatile signed __int32 *v171; // rax
  unsigned int v172; // eax
  bool v173; // zf
  int v174; // edx
  int v175; // ecx
  const struct _DXGK_ALLOCATIONUSAGEHINT *AllocationHint; // rax
  __int64 v177; // rdx
  __int64 v178; // rcx
  __int64 v179; // r8
  __int64 v180; // r9
  int v181; // r10d
  int v182; // ecx
  __int64 v183; // rsi
  struct _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0::$5068715F5D8591D41DA1228877FDA04B::$63766B29C143116E9EC685C38896947D v184; // ecx
  unsigned int CurrentProcessId; // eax
  int v186; // r8d
  __int64 v187; // r8
  unsigned int BucketIdForAllocationSizePow2; // eax
  __int64 v189; // r8
  unsigned int v190; // r9d
  int v192; // r8d
  __int64 v193; // rax
  __int64 i; // rsi
  void *v195; // rcx
  VIDMM_FLIP_QUEUE_REFERENCES *v196; // rcx
  struct VIDMM_CROSSADAPTER_ALLOC *v197; // rdx
  VIDMM_GLOBAL *v198; // rcx
  __int64 v199; // rdx
  int *v200; // r9
  __int64 v201; // rcx
  int v202; // r8d
  int v203; // [rsp+60h] [rbp-130h]
  int v204; // [rsp+110h] [rbp-80h]
  char v205; // [rsp+114h] [rbp-7Ch]
  _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0 v206; // [rsp+118h] [rbp-78h] BYREF
  unsigned int PrivateFormat; // [rsp+11Ch] [rbp-74h]
  char v208; // [rsp+120h] [rbp-70h]
  PVOID P; // [rsp+128h] [rbp-68h]
  struct VIDMM_GLOBAL_ALLOC *v210; // [rsp+130h] [rbp-60h]
  int Version; // [rsp+138h] [rbp-58h]
  int Width; // [rsp+13Ch] [rbp-54h]
  int v213; // [rsp+140h] [rbp-50h]
  struct VIDMM_PHYSICAL_ADAPTER *v214; // [rsp+148h] [rbp-48h]
  unsigned __int64 v215; // [rsp+150h] [rbp-40h] BYREF
  UINT SwizzledFormat; // [rsp+158h] [rbp-38h]
  UINT Height; // [rsp+15Ch] [rbp-34h] BYREF
  __int64 v218; // [rsp+160h] [rbp-30h]
  unsigned __int64 v219; // [rsp+168h] [rbp-28h]
  unsigned __int64 v220; // [rsp+170h] [rbp-20h]
  struct VIDMM_CROSSADAPTER_ALLOC *v221; // [rsp+178h] [rbp-18h]
  struct VIDMM_PROCESS *v222; // [rsp+180h] [rbp-10h]
  __int64 v223; // [rsp+188h] [rbp-8h]
  int v224[2]; // [rsp+190h] [rbp+0h]
  __int64 v225; // [rsp+198h] [rbp+8h]
  __int64 v226; // [rsp+1A0h] [rbp+10h]
  __int64 v227; // [rsp+1A8h] [rbp+18h]
  _DWORD *v228; // [rsp+1B0h] [rbp+20h]
  int v229[32]; // [rsp+1C0h] [rbp+30h] BYREF
  __int64 v233; // [rsp+2B0h] [rbp+120h] BYREF
  va_list va; // [rsp+2B0h] [rbp+120h]
  __int64 v235; // [rsp+2B8h] [rbp+128h]
  __int64 v236; // [rsp+2C0h] [rbp+130h]
  void *v237; // [rsp+2C8h] [rbp+138h]
  __int64 v238; // [rsp+2D0h] [rbp+140h]
  void *v239; // [rsp+2D8h] [rbp+148h]
  __int64 v240; // [rsp+2E0h] [rbp+150h]
  __int64 v241; // [rsp+2E8h] [rbp+158h]
  __int64 v242; // [rsp+2F0h] [rbp+160h]
  __int64 v243; // [rsp+2F8h] [rbp+168h]
  __int64 v244; // [rsp+300h] [rbp+170h]
  struct VIDMM_CROSSADAPTER_ALLOC **v245; // [rsp+308h] [rbp+178h]
  __int64 v246; // [rsp+310h] [rbp+180h]
  _QWORD *v247; // [rsp+318h] [rbp+188h]
  unsigned __int8 *v248; // [rsp+320h] [rbp+190h]
  va_list va1; // [rsp+328h] [rbp+198h] BYREF

  va_start(va1, a12);
  va_start(va, a12);
  v233 = va_arg(va1, _QWORD);
  v235 = va_arg(va1, _QWORD);
  v236 = va_arg(va1, _QWORD);
  v237 = va_arg(va1, void *);
  v238 = va_arg(va1, _QWORD);
  v239 = va_arg(va1, void *);
  v240 = va_arg(va1, _QWORD);
  v241 = va_arg(va1, _QWORD);
  v242 = va_arg(va1, _QWORD);
  v243 = va_arg(va1, _QWORD);
  v244 = va_arg(va1, _QWORD);
  v245 = va_arg(va1, struct VIDMM_CROSSADAPTER_ALLOC **);
  v246 = va_arg(va1, _QWORD);
  v247 = va_arg(va1, _QWORD *);
  v248 = va_arg(va1, unsigned __int8 *);
  v12 = v233;
  v14 = (struct _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0::$5068715F5D8591D41DA1228877FDA04B::$63766B29C143116E9EC685C38896947D)v233;
  v206.0 = (struct _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0::$5068715F5D8591D41DA1228877FDA04B::$63766B29C143116E9EC685C38896947D)v233;
  Current = DXGPROCESS::GetCurrent();
  v219 = (unsigned __int64)Current;
  v19 = Current;
  if ( !v246 || (v20 = *(_DWORD *)(v246 + 176), LOBYTE(v233) = 1, (v20 & 1) != 0) )
    LOBYTE(v233) = 0;
  if ( a2 )
  {
    v21 = (struct VIDMM_PROCESS *)*((_QWORD *)a2 + 1);
  }
  else
  {
    if ( !Current )
    {
      WdLogSingleEntry0(1);
      v36 = 2935;
      v37 = L"pVidMmProcess is not present";
      goto LABEL_479;
    }
    v22 = *((_QWORD *)Current + 8);
    if ( v22 )
      v21 = *(struct VIDMM_PROCESS **)(v22 + 8);
    else
      v21 = 0;
  }
  v23 = v241;
  v222 = v21;
  if ( (unsigned int)v241 <= 2 )
    v23 = 2;
  LODWORD(v241) = v23;
  if ( v19 && (v24 = *((_DWORD *)v19 + 102), (v24 & 0x100) != 0) )
  {
    v208 = 1;
    if ( (v24 & 0x400) == 0 && !v243 && (v12 & 1) != 0 )
    {
      v14 = (struct _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0::$5068715F5D8591D41DA1228877FDA04B::$63766B29C143116E9EC685C38896947D)(*(_DWORD *)&v14 & 0xFFFF7FFF);
      v206.0 = v14;
    }
  }
  else
  {
    v208 = 0;
  }
  if ( g_Feature_ResourcePoolManagement )
  {
    v226 = *((_QWORD *)v21 + 46);
    v225 = 0;
  }
  else
  {
    v225 = *((_QWORD *)v21 + 43);
    v226 = 0;
  }
  v25 = 0;
  v26 = *(_QWORD *)(a1 + 36480);
  if ( *(_DWORD *)(a1 + 3112) != 1 )
    v25 = a3;
  *(_QWORD *)v224 = v25;
  v215 = 0;
  v214 = *(struct VIDMM_PHYSICAL_ADAPTER **)(v26 + 8 * v25);
  v228 = (_DWORD *)*((_QWORD *)v214 + 169);
  VidMmConvertSegmentPreferences((const struct VIDMM_GLOBAL *)a1, a12, (struct VIDMM_SEGMENT_PREFERENCES *)&v215);
  v30 = v215;
  v218 = a6;
  if ( g_IsInternalReleaseOrDbg != (_BYTE)v29 )
  {
    v31 = WdLogNewEntry5_WdTrace(v27);
    v29 = 0;
    *(_QWORD *)(v31 + 24) = a2;
    WdLogGlobalForLineNumber = 3007;
    if ( g_IsInternalReleaseOrDbg )
    {
      v33 = (_QWORD *)WdLogNewEntry5_WdTrace(v32);
      v33[3] = a4;
      v33[4] = a6;
      v33[5] = a9;
      v33[6] = a10;
      WdLogGlobalForLineNumber = 3012;
      v34 = (_QWORD *)WdLogNewEntry5_WdTrace(a10);
      v29 = 0;
      v34[3] = (unsigned int)v30;
      v34[4] = HIDWORD(v215);
      v34[5] = (unsigned int)v14;
      v34[6] = v236;
      WdLogGlobalForLineNumber = 3017;
    }
    v28 = v222;
  }
  *v247 = v29;
  if ( *(_DWORD *)(a1 + 40) < 0x5023u && (*(_DWORD *)&v14 & 0x40000) != 0 )
  {
    WdLogSingleEntry0(1);
    v36 = 3033;
    v37 = L"CpuVisibleOnDemand flag set, but on this driver is supposed to be reserved";
LABEL_479:
    WdLogGlobalForLineNumber = v36;
    DxgkLogInternalTriageEvent(0, 0x40000, v35, (_DWORD)v37, v36, 0, 0, 0);
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
      v36 = 3055;
      v37 = L"HardwareProtected allocations cannot be used with PermanentSysMem, Cached, CrossAdapter, CrossAdapterPrimary"
             ", Protected, ExistingSysMem, ExistingKernelSysMem";
      goto LABEL_479;
    }
    v14 = (struct _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0::$5068715F5D8591D41DA1228877FDA04B::$63766B29C143116E9EC685C38896947D)(*(_DWORD *)&v14 & 0xFFFBFFFE);
    v206.0 = v14;
  }
  if ( (*(_BYTE *)&v14 & 1) != 0 && (*(_DWORD *)&v14 & 0x40000) == 0
    || (LOBYTE(v213) = v29, (*(_BYTE *)&v14 & 0x10) != 0) )
  {
    LOBYTE(v213) = 1;
  }
  v38 = v233;
  if ( (_BYTE)v233 || (*(_BYTE *)&v14 & 8) != 0 || (*(_DWORD *)&v14 & 0x20000) != 0 )
    LOBYTE(v213) = v29;
  if ( (*((_DWORD *)v28 + 40) & 0x40) == 0 )
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
      && !v38
      && !v243
      && !v244 )
    {
      v14 = (struct _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0::$5068715F5D8591D41DA1228877FDA04B::$63766B29C143116E9EC685C38896947D)(*(_DWORD *)&v14 & 0xFFFBFFFF);
      LOBYTE(v213) = 1;
      v206.0 = v14;
    }
  }
  if ( ((*(unsigned int *)&v14 >> 13) & 1) != 0 && (*(_BYTE *)(a1 + 37225) & 8) == 0 )
  {
    WdLogSingleEntry0(1);
    v36 = 3142;
    v37 = L"Drivers must support MapAperture2 to set the MapApertureCpuVisible flag";
    goto LABEL_479;
  }
  if ( !(unsigned __int8)VidMmValidatePreferredSegment(v214, v30, a9) )
  {
    WdLogSingleEntry0(1);
    v36 = 3152;
    v37 = L"Specified preferred segment is invalid. It must be a subset of the supported read segment set";
    goto LABEL_479;
  }
  if ( !dword_1400875B0 || (*(_BYTE *)&v14 & 1) != 0 )
  {
    v42 = a9;
    v40 = v214;
  }
  else
  {
    v40 = v214;
    if ( (v30 & 0x1F) != 0 )
    {
      v42 = 1 << ((v30 & 0x1F) - 1);
      a9 = v42;
    }
    else
    {
      v41 = *((_DWORD *)v214 + 21) & a9;
      if ( !v41 )
        v41 = a9;
      v42 = v41;
      a9 = v41;
    }
  }
  v43 = a4;
  if ( !a4 )
  {
    WdLogSingleEntry0(1);
    v36 = 3193;
    v37 = L"Can't create an allocation of zero size";
    goto LABEL_479;
  }
  if ( ((*(unsigned int *)&v14 >> 13) & 1) != 0 )
  {
    if ( *(int *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 16LL) + 3132LL) < 2900 )
    {
      WdLogSingleEntry0(1);
      v36 = 3203;
      v37 = L"LinkInstanced/MapApertureCpuVisible flag is not supported in WDDM v2.x/<2.9, respectively";
      goto LABEL_479;
    }
    v43 = a4;
  }
  if ( (*(_WORD *)&v14 & 0x1000) != 0 )
  {
    WdLogSingleEntry0(1);
    v36 = 3210;
    v37 = L"PhysicallyContiguous flag is not not currently supported";
    goto LABEL_479;
  }
  if ( (v42 & *((_DWORD *)v40 + 19)) == 0 )
  {
    WdLogSingleEntry0(1);
    v36 = 3223;
LABEL_86:
    v37 = L"Specified segment set references invalid segment";
    goto LABEL_479;
  }
  if ( !v244 && (v42 & *((_DWORD *)v40 + 20)) == 0 )
  {
    WdLogSingleEntry0(1);
    v36 = 3236;
    goto LABEL_86;
  }
  Height = 0;
  LODWORD(v233) = 0;
  if ( !VidMmVerifySupportedSegmentSetAndAdjustFlags(
          v40,
          v42,
          &v206,
          v43,
          a5,
          v243 != 0,
          (struct _VIDMM_VERIFY_SUPPORTED_SEGMENT *)va) )
  {
    WdLogSingleEntry0(1);
    v36 = 3253;
    v37 = L"VidMmVerifySupportedSegmentSetAndAdjustFlags failed";
    goto LABEL_479;
  }
  Value = v206.Value;
  if ( (v206.Value & 0x40000) != 0 )
  {
    if ( (*(_BYTE *)&v206.0 & 1) == 0 )
    {
      WdLogSingleEntry0(1);
      v36 = 3265;
      v37 = L"CpuVisibleOnDemand must also be set in combination with CpuVisible";
      goto LABEL_479;
    }
    if ( (*(_BYTE *)&v206.0 & 2) != 0 || (*(_BYTE *)&v206.0 & 0x20) != 0 || (*(_BYTE *)&v206.0 & 0x10) != 0 )
    {
      WdLogSingleEntry0(1);
      v36 = 3277;
      v37 = L"PermanentSysMem, ExistingKernelSysMem, and ExistingSysMem cannot be used with CpuVisibleOnDemand";
      goto LABEL_479;
    }
  }
  v45 = (unsigned int)v233;
  v46 = a10;
  v220 = a5 & -(__int64)((v233 & 4) != 0);
  if ( a10 )
  {
    if ( (a10 & *((_DWORD *)v214 + 20)) == 0 )
    {
      WdLogSingleEntry0(1);
      v36 = 3303;
      v37 = L"EvictionSegmentSet must be a valid set of driver segments";
      goto LABEL_479;
    }
    if ( (~*((_DWORD *)v214 + 24) & a10) != 0 )
    {
      WdLogSingleEntry0(1);
      v36 = 3314;
      v37 = L"EvictionSegmentSet may only contain system memory segments";
      goto LABEL_479;
    }
    if ( VidMmCheckAnySegmentAllFlags(v214, a10, (struct _DXGK_SEGMENTFLAGS)32) )
    {
      WdLogSingleEntry0(1);
      v36 = 3329;
      v37 = L"Can't use a segment requiring pitch alignment for paging";
      goto LABEL_479;
    }
    v46 = a10;
  }
  v47 = ((unsigned int)Value >> 1) & 1;
  Width = v47;
  if ( v47 )
  {
    if ( (Value & 1) == 0 )
    {
      WdLogSingleEntry0(1);
      v36 = 3346;
      v37 = L"Need to specify the CpuVisible flags in combination with PermanentSysMem";
      goto LABEL_479;
    }
    if ( (Value & 0x20000000) != 0 || (int)Value < 0 || (Value & 0x40000000) != 0 )
    {
      WdLogSingleEntry0(1);
      v36 = 3357;
      v37 = L"Shareable, ManagedPrimary and Primary can't be specified in combination with PermanentSysMem";
      goto LABEL_479;
    }
  }
  v48 = a1;
  v49 = ((unsigned int)Value >> 2) & 1;
  LODWORD(v233) = v49;
  if ( v49 && (Value & 0x800000) == 0 && *(_BYTE *)(a1 + 3202) )
  {
    if ( !VidMmCheckAllSegmentsAllFlags(v214, v46, (struct _DXGK_SEGMENTFLAGS)16) )
    {
      WdLogSingleEntry0(1);
      v36 = 3393;
      v37 = L"Cached allocations must only support cache coherent segments on adapters which have cache coherent aperture "
             "segments available";
      goto LABEL_479;
    }
    v47 = Width;
    v48 = a1;
    v49 = v233;
  }
  v50 = ((unsigned int)Value >> 29) & 1;
  if ( v50 && (v47 || (Value & 8) != 0 || (Value & 0x20) != 0 || (Value & 0x40000000) != 0) )
  {
    WdLogSingleEntry0(1);
    v36 = 3412;
    v37 = L"PermanentSysMem, Protected, ExistingKernelSysMem, or Primary flags can't be specified with Shareable";
    goto LABEL_479;
  }
  v51 = v235;
  if ( (v235 & 1) != 0 && ((v45 & 1) == 0 || !v50) )
  {
    WdLogSingleEntry0(1);
    v36 = 3421;
    v37 = L"ShareBackingStoreWithKmd flag should be set only for shared aperture only allocations";
    goto LABEL_479;
  }
  if ( (Value & 0x100000) != 0 && (!v50 || !v245 || (v45 & 1) == 0) )
  {
    WdLogSingleEntry0(1);
    v36 = 3434;
    v37 = L"Cross adapter allocations must be shareable and support system memory only and SharedResource must be provided";
    goto LABEL_479;
  }
  v227 = 256;
  if ( v243 && (v47 || (Value & 0x100) != 0 || (Value & 0x200) != 0 || (Value & 0x40000000) != 0) )
  {
    WdLogSingleEntry0(1);
    v36 = 3454;
    v37 = L"PermanentSysMem, Overlay, Capture, or Primary flags can't be specified for context allocations";
    goto LABEL_479;
  }
  if ( (((unsigned int)Value >> 26) & 1) != 0 )
  {
    if ( (Value & 8) == 0 )
    {
      WdLogSingleEntry0(1);
      v36 = 3470;
      v37 = L"Protected flag must be specified with CddBitmap";
      goto LABEL_479;
    }
  }
  else if ( (Value & 8) == 0 )
  {
    goto LABEL_155;
  }
  if ( (Value & 1) != 0 && (((unsigned int)Value >> 26) & 1) == 0 && !v243
    || v47
    || v50
    || (Value & 0x10) != 0
    || (Value & 0x20) != 0
    || (int)Value < 0
    || (Value & 0x40000000) != 0 )
  {
    WdLogSingleEntry0(1);
    v36 = 3501;
    v37 = L"CpuVisible, PermanentSysMem, Shareable, ExistingSysMem, ExistingKernelSysMem, ManagedPrimary or Primary flags "
           "can't be specified with Protected";
    goto LABEL_479;
  }
LABEL_155:
  v52 = ((unsigned int)Value >> 4) & 1;
  if ( v52 && (v47 || (Value & 0x20) != 0 || (int)Value < 0 || (Value & 0x40000000) != 0) )
  {
    WdLogSingleEntry0(1);
    v36 = 3521;
    v37 = L"PermanentSysMem, ExistingKernelSysMem, ManagedPrimary or Primary flags can't be specified with ExistingSysMem";
    goto LABEL_479;
  }
  v53 = ((unsigned int)Value >> 5) & 1;
  if ( v53 && (v47 || v50 || v52 || (int)Value < 0 || (Value & 0x40000000) != 0) )
  {
    WdLogSingleEntry0(1);
    v36 = 3543;
    v37 = L"PermanentSysMem, Shareable, ExistingSysMem, ManagedPrimary or Primary flags can't be specified with ExistingKernelSysMem";
    goto LABEL_479;
  }
  if ( (int)Value >= 0 )
  {
    if ( (Value & 0x40000000) != 0 )
    {
      if ( v47
        || v49 && (v55 = *(_DWORD *)(*(_QWORD *)(v48 + 24) + 444LL), (v55 & 0x10) == 0) && (v55 & 8) == 0
        || v52
        || v53 )
      {
        WdLogSingleEntry0(1);
        v36 = 3587;
        v37 = L"PermanentSysMem, Cached, ExistingSysMem, ExistingKernelSysMem and ManagedPrimary flags can't be specified with Primary";
        goto LABEL_479;
      }
      if ( (*(_DWORD *)(*(_QWORD *)(v48 + 24) + 2596LL) & 0x200) == 0 )
        Value = (unsigned int)Value | 1;
      v56 = (unsigned __int8)v213;
      if ( (Value & 1) != 0 )
        v56 = 1;
      LODWORD(Value) = Value | 0x20000000;
      v213 = v56;
    }
  }
  else if ( v47
         || v49 && (v54 = *(_DWORD *)(*(_QWORD *)(v48 + 24) + 444LL), (v54 & 0x10) == 0) && (v54 & 8) == 0
         || v52
         || v53
         || (Value & 0x40000000) != 0 )
  {
    WdLogSingleEntry0(1);
    v36 = 3565;
    v37 = L"PermanentSysMem, Cached, ExistingSysMem, ExistingKernelSysMem and Primary flags can't be specified with ManagedPrimary";
    goto LABEL_479;
  }
  LODWORD(v233) = ((unsigned int)Value >> 28) & 1;
  if ( (_DWORD)v233 )
  {
    v57 = Value & 0xEFFF7FBF;
    v58 = *(_DWORD *)(*(_QWORD *)(v48 + 24) + 444LL);
    if ( (v58 & 8) != 0 || (v58 & 0x10) != 0 )
      v57 = Value & 0xEFFF7FBB;
    if ( v57 )
    {
      WdLogSingleEntry0(1);
      v36 = 3629;
      v37 = L"PagingBuffer can't be combined with any other flags";
      goto LABEL_479;
    }
    if ( (~*((_DWORD *)v214 + 24) & a9) != 0 )
    {
      WdLogSingleEntry0(1);
      v36 = 3639;
      v37 = L"Paging buffer can only be allocated from an aperture segment";
      goto LABEL_479;
    }
  }
  if ( (Value & 0x400000) != 0 )
  {
    if ( (Value & 0x20000000) == 0 )
    {
      WdLogSingleEntry0(1);
      v36 = 3655;
      v37 = L"SectionSupplied should always be Shareable resource";
      goto LABEL_479;
    }
    if ( !v237 )
    {
      WdLogSingleEntry0(1);
      v36 = 3665;
      v37 = L"SectionSupplied resource does not supply the section";
      goto LABEL_479;
    }
  }
  if ( (Value & 0x4000) != 0 )
  {
    if ( (Value & 1) == 0 )
    {
      WdLogSingleEntry0(1);
      v36 = 3677;
      v37 = L"History buffers must specify the CpuVisible flag";
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
      v61 = L"History buffer specifies invalid flag combination. Flags=%d";
      WdLogGlobalForLineNumber = 3693;
LABEL_215:
      DxgkLogInternalTriageEvent(v59, 0x40000, v60, (_DWORD)v61, Value, 0, 0, 0);
      return 3221225485LL;
    }
  }
  if ( v245 )
    v221 = *v245;
  else
    v221 = 0;
  if ( (VIDMM_GLOBAL::_Config & 2) != 0
    && DXGPROCESS::GetCurrent()
    && (*((_DWORD *)DXGPROCESS::GetCurrent() + 102) & 4) != 0
    && !(_DWORD)v233
    && (Value & 0x40000000) == 0 )
  {
    LODWORD(Value) = Value | 0x8000000;
  }
  v205 = 0;
  LOBYTE(v233) = 0;
  LOBYTE(SwizzledFormat) = 0;
  if ( !v208 || v243 )
  {
    Version = 0;
    goto LABEL_238;
  }
  if ( (Value & 0x10) != 0 )
  {
    LOBYTE(v213) = 0;
    Version = 8;
    v206.0 = (struct _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0::$5068715F5D8591D41DA1228877FDA04B::$63766B29C143116E9EC685C38896947D)64;
    goto LABEL_239;
  }
  if ( (Value & 1) == 0 )
  {
    Version = 8;
LABEL_238:
    v206.0 = 0;
    goto LABEL_239;
  }
  if ( (Value & 0x8000) != 0 && (*(_DWORD *)(v219 + 408) & 0x400) == 0 )
  {
    WdLogSingleEntry0(1);
    v36 = 3745;
    v37 = L"Cpu visible paravirtualized allocations cannot be places to aperture segment";
    goto LABEL_479;
  }
  v62 = *(_DWORD *)(v219 + 408) >> 10;
  LOBYTE(v62) = (*(_DWORD *)(v219 + 408) & 0x400) != 0;
  Version = 8;
  SwizzledFormat = v62;
  v206.0 = 0;
  LOBYTE(v233) = v62 ^ 1;
  if ( (Value & 0x20000000) != 0 )
  {
    v205 = 1;
    LOBYTE(v233) = v62 ^ 1;
  }
  else
  {
    SwizzledFormat = v62;
    v205 = v62 ^ 1;
  }
LABEL_239:
  if ( *(int *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 16LL) + 3132LL) >= 3000
    && (Value & 1) != 0
    && (v45 & 2) == 0
    && !v244
    && (Value & 0x40000000) == 0 )
  {
    WdLogSingleEntry1(1, Value);
    v61 = L"CPUVisible allocations must include an aperture segment in the supported segment set";
    WdLogGlobalForLineNumber = 3792;
    goto LABEL_215;
  }
  if ( v238 && (v238 != (v238 & 0xFFFFFFFFFFFFF000uLL) || (a4 & 0xFFF) != 0) )
  {
    WdLogSingleEntry2(1, v238, a4);
    WdLogGlobalForLineNumber = 3810;
    DxgkLogInternalTriageEvent(
      v63,
      0x40000,
      v64,
      (unsigned int)L"Existing sysmem pointer must be paged aligned and a multiple of page in size. pExistingSysMem=0x%.16x, Size=%I64u",
      v238,
      a4,
      0,
      0);
    return 3221225485LL;
  }
  v223 = 0;
  v65 = operator new(400, 825256278, 256);
  P = (PVOID)v65;
  if ( !v65 )
    goto LABEL_477;
  *(_QWORD *)(v65 + 144) = 0;
  *(_QWORD *)(v65 + 152) = 0;
  *(_QWORD *)(v65 + 160) = 0;
  *(_DWORD *)(v65 + 168) = 0;
  *(_QWORD *)(v65 + 192) = 0;
  *(_QWORD *)(v65 + 200) = 0;
  *(_DWORD *)(v65 + 172) = 13;
  *(_DWORD *)(v65 + 176) = 17;
  *(_DWORD *)(v65 + 208) = 0;
  *(_QWORD *)(v65 + 216) = 0;
  *(_QWORD *)(v65 + 320) = 0;
  *(_QWORD *)(v65 + 328) = 0;
  *(_DWORD *)(v65 + 212) = 78;
  *(_DWORD *)(v65 + 336) = 0;
  *(_DWORD *)(v65 + 340) = 18;
  *(_OWORD *)(v65 + 376) = 0;
  v66 = (_QWORD *)(v65 + 96);
  v66[1] = v66;
  *v66 = v66;
  v67 = operator new(56, 842295638, 64);
  v68 = (struct VIDMM_GLOBAL_ALLOC *)P;
  v215 = (unsigned __int64)P + 392;
  *((_QWORD *)P + 49) = v67;
  if ( !v67 )
  {
    _InterlockedIncrement(&dword_1400877B8);
    WdLogSingleEntry0(6);
    WdLogGlobalForLineNumber = 3861;
    DxgkLogInternalTriageEvent(
      v69,
      262145,
      v70,
      (unsigned int)L"Couldn't allocate memory for VIDMM_GLOBAL_ALLOC_NONPAGED",
      3861,
      0,
      0,
      0);
    v73 = -1073741801;
LABEL_252:
    v74 = P;
    v75 = (char *)P;
LABEL_457:
    if ( (*((_DWORD *)v75 + 8) & 0x20) != 0 )
      VIDMM_GLOBAL::UncommitGlobalBackingStore((VIDMM_GLOBAL *)a1, (struct VIDMM_GLOBAL_ALLOC *)v75, 1);
    v193 = *((_QWORD *)v75 + 49);
    if ( v193 )
    {
      if ( *(_QWORD *)(v193 + 32) )
      {
        for ( i = 0; i != 2; ++i )
        {
          v195 = *(void **)(*(_QWORD *)(v74[49] + 32LL) + 8 * i);
          if ( v195 )
            VidSchDestroySyncObject(v195);
        }
        operator delete(*(void **)(*((_QWORD *)v75 + 49) + 32LL));
      }
      v196 = *(VIDMM_FLIP_QUEUE_REFERENCES **)(*((_QWORD *)v75 + 49) + 24LL);
      if ( v196 )
        VIDMM_FLIP_QUEUE_REFERENCES::ReleaseReference(v196, v71);
      operator delete(*((void **)v75 + 49));
    }
    v197 = (struct VIDMM_CROSSADAPTER_ALLOC *)*((_QWORD *)v75 + 45);
    if ( !v197 )
      goto LABEL_472;
    VIDMM_GLOBAL::FreeCrossAdapterDataDpc(v72, v197, (struct VIDMM_GLOBAL_ALLOC *)v75);
    v198 = (VIDMM_GLOBAL *)(unsigned int)_InterlockedDecrement(*((volatile signed __int32 **)v75 + 45));
    if ( !(_DWORD)v198 )
    {
      VIDMM_GLOBAL::DestroyCrossAdapterAllocation(v198, *((struct VIDMM_CROSSADAPTER_ALLOC **)v75 + 45));
      *v245 = 0;
LABEL_472:
      v199 = *(_QWORD *)v75;
      if ( *(_QWORD *)v75 )
      {
        (*(void (__fastcall **)(struct VIDMM_PHYSICAL_ADAPTER *))(*(_QWORD *)v214 + 40LL))(v214);
        *(_QWORD *)v75 = 0;
      }
      VIDMM_GLOBAL_ALLOC::`scalar deleting destructor'(v75, v199);
      return (unsigned int)v73;
    }
    if ( (int)v198 >= 0 )
      goto LABEL_472;
    v200 = (int *)*((_QWORD *)v75 + 45);
    v201 = *v200;
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 66, v200, v201, 0);
    WdLogGlobalForLineNumber = 227;
LABEL_477:
    _InterlockedIncrement(&dword_140087694);
    WdLogSingleEntry0(6);
    WdLogGlobalForLineNumber = 3828;
    DxgkLogInternalTriageEvent(
      0,
      262145,
      v202,
      (unsigned int)L"Couldn't allocate memory for VIDMM_GLOBAL_ALLOC",
      3828,
      0,
      0,
      0);
    return 3221225495LL;
  }
  v76 = (VIDMM_GLOBAL *)a1;
  if ( !*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 744LL) + 65LL) || (Value & 0x80000) != 0 )
  {
    v210 = v68;
    v90 = operator new[](12, 858810710, 64);
    v91 = v215;
    *(_QWORD *)(*(_QWORD *)v215 + 24LL) = v90;
    v92 = *(volatile signed __int32 **)(*(_QWORD *)v91 + 24LL);
    if ( !v92 )
    {
      _InterlockedIncrement(&dword_14008768C);
      WdLogSingleEntry0(6);
      WdLogGlobalForLineNumber = 3943;
      DxgkLogInternalTriageEvent(
        v93,
        262145,
        v94,
        (unsigned int)L"Couldn't allocate displaying reference array for allocation",
        3943,
        0,
        0,
        0);
      v73 = -1073741801;
      goto LABEL_252;
    }
    _InterlockedIncrement(v92);
    v78 = v210;
    v95 = *(_QWORD *)(*(_QWORD *)v91 + 24LL);
    v96 = v210;
    P = v210;
    *(_DWORD *)(v95 + 4) = -((Value & 0x100000) == 0);
    v77 = v96;
LABEL_269:
    v76 = (VIDMM_GLOBAL *)a1;
  }
  else
  {
    if ( (Value & 0x40000000) != 0 || (int)Value < 0 )
    {
      if ( a2 )
      {
        v81 = operator new(176, 858810710, 64);
        v82 = v215;
        *(_QWORD *)(*(_QWORD *)v215 + 32LL) = v81;
        if ( *(_QWORD *)(*(_QWORD *)v82 + 32LL) )
        {
          PrivateFormat = 0;
          Width = 1000 * (v224[0] + 1);
          v210 = (struct VIDMM_GLOBAL_ALLOC *)P;
          while ( 1 )
          {
            memset(v229, 0, 0x50u);
            v85 = PrivateFormat;
            v86 = v215;
            v229[0] = 5;
            v229[1] = 131;
            v87 = *(_QWORD *)(*(_QWORD *)v215 + 32LL);
            *(_QWORD *)&v229[2] = Width * PrivateFormat + 100LL;
            v88 = (PrivateFormat != 1) + 7;
            *(_QWORD *)(v87 + 8LL * PrivateFormat + 16) = *(_QWORD *)&v229[2];
            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v86 + 32LL) + 32LL) = v210;
            SyncObject = VidSchCreateSyncObject(
                           *(_QWORD *)(*(_QWORD *)(a1 + 16) + 744LL),
                           0,
                           v229,
                           v88,
                           0,
                           0,
                           v224[0],
                           (__int64 *)(*(_QWORD *)(*(_QWORD *)v86 + 32LL) + 8 * v85),
                           0,
                           0,
                           0,
                           a2);
            if ( SyncObject < 0 )
              break;
            if ( (int)++PrivateFormat >= 2 )
            {
              v78 = v210;
              v77 = v210;
              goto LABEL_269;
            }
          }
          v75 = (char *)v210;
          v73 = SyncObject;
          v74 = v210;
        }
        else
        {
          _InterlockedIncrement(&dword_14008768C);
          WdLogSingleEntry0(6);
          WdLogGlobalForLineNumber = 3883;
          DxgkLogInternalTriageEvent(
            v83,
            262145,
            v84,
            (unsigned int)L"Couldn't allocate flip fence state for allocation",
            3883,
            0,
            0,
            0);
          v74 = P;
          v75 = (char *)P;
          v73 = -1073741801;
        }
        goto LABEL_457;
      }
      v73 = 0;
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 3872;
      DxgkLogInternalTriageEvent(v79, 0x40000, v80, (unsigned int)L"pVidMmDevice is not present", 3872, 0, 0, 0);
      goto LABEL_252;
    }
    v77 = v68;
    v210 = v68;
    v78 = v68;
  }
  v97 = v236;
  if ( v236 )
  {
    if ( (*(_DWORD *)(v236 + 4) & 0x8000) != 0 )
    {
      v98 = (_DWORD *)((char *)v78 + 24);
      *((_DWORD *)v78 + 6) |= 0x20u;
    }
    else
    {
      v98 = (_DWORD *)((char *)v77 + 24);
    }
    if ( (*(_DWORD *)(v97 + 4) & 0x10000) != 0 )
    {
      *((_DWORD *)v78 + 7) |= 2u;
      v98 = (_DWORD *)((char *)v78 + 24);
      *((_DWORD *)v78 + 6) |= 0x80000u;
    }
    if ( (*(_DWORD *)(v97 + 4) & 0x8000000) != 0 )
      *v98 |= 0x40u;
  }
  v99 = v221;
  *((_QWORD *)v78 + 45) = v221;
  if ( v99 )
  {
    _InterlockedIncrement((volatile signed __int32 *)v99);
    CrossAdapterDataDpc = VIDMM_GLOBAL::AllocateCrossAdapterDataDpc(v76, v99, v78);
    if ( CrossAdapterDataDpc < 0 )
    {
      v73 = CrossAdapterDataDpc;
      goto LABEL_455;
    }
    v78 = v210;
  }
  v101 = 4096;
  PrivateFormat = 4096;
  if ( g_Feature_ResourcePoolManagement )
  {
    v102 = *(_DWORD *)(*(_QWORD *)(v226 + 40) + 112LL) >> 1;
  }
  else
  {
    v102 = v225;
    LOBYTE(v102) = *(_BYTE *)(v225 + 72);
  }
  LOBYTE(v102) = v102 & 1;
  Width = v102;
  if ( (_BYTE)v102 && (!g_Feature_ResourcePoolManagement || !v238 && !v237) )
  {
    v101 = 0x10000;
    PrivateFormat = 0x10000;
  }
  v103 = v101 - 1;
  LODWORD(v221) = v101 - 1;
  v104 = ~v103 & (v103 + a4);
  v219 = v104;
  if ( a4 > v104 )
  {
    WdLogSingleEntry1(1, a4);
    WdLogGlobalForLineNumber = 4036;
    DxgkLogInternalTriageEvent(
      v105,
      0x40000,
      a4,
      (unsigned int)L"Overflow rounding allocation size (0x%08X) to next page boundary",
      a4,
      0,
      0,
      0);
    v73 = -1073741811;
LABEL_291:
    v75 = (char *)v210;
LABEL_456:
    v74 = P;
    goto LABEL_457;
  }
  v215 = ~v103 & (v220 + v101 - 1);
  if ( v220 > v215 )
  {
    WdLogSingleEntry1(1, v220);
    v108 = v220;
    v109 = L"Overflow rounding allocation pitch aligned size (0x%08X) to next page boundary";
    WdLogGlobalForLineNumber = 4050;
LABEL_294:
    DxgkLogInternalTriageEvent(v106, 0x40000, v107, (_DWORD)v109, v108, 0, 0, 0);
LABEL_295:
    v73 = -1073741811;
    goto LABEL_291;
  }
  if ( v104 > 0xFFFF0000 && (*((_DWORD *)v78 + 7) & 2) == 0 )
  {
    WdLogSingleEntry0(1);
    v108 = 4058;
    v109 = L"Can't create an allocation that uses more than 4GB-64kB of system memory";
    WdLogGlobalForLineNumber = 4058;
    goto LABEL_294;
  }
  if ( (*(_BYTE *)(a1 + 37225) & 0x20) != 0 )
  {
    if ( v12 < 0 )
    {
      LODWORD(v220) = -1;
      v204 = -1;
    }
    else
    {
      LODWORD(v220) = a7;
      v110 = (unsigned int)(4096 << a7);
      v111 = 4096 << a8;
      v218 = v110;
      v204 = a8;
      if ( a8 < a7 )
      {
        WdLogSingleEntry2(3, v111, (unsigned int)v110);
        WdLogGlobalForLineNumber = 4098;
        return 3221225485LL;
      }
      if ( ((v110 - 1) & v104) != 0 )
      {
        WdLogSingleEntry2(3, v104, v218);
        WdLogGlobalForLineNumber = 4113;
        return 3221225485LL;
      }
      if ( v111 > v104 )
      {
        WdLogSingleEntry3(3, v218, v111, v104);
        WdLogGlobalForLineNumber = 4128;
        return 3221225485LL;
      }
      LODWORD(v103) = (_DWORD)v221;
      v101 = PrivateFormat;
    }
    PrivateFormat = a11;
    if ( (Value & 0x8000) == 0 )
      goto LABEL_316;
  }
  else
  {
    PrivateFormat = 0;
    LODWORD(v220) = -1;
    v204 = -1;
  }
  if ( (_DWORD)v218 )
  {
    v112 = ~(_DWORD)v103 & (unsigned int)(v103 + v218);
    if ( (unsigned int)v218 > (unsigned int)v112 )
    {
      v114 = (unsigned int)v218;
      WdLogSingleEntry1(1, (unsigned int)v218);
      WdLogGlobalForLineNumber = 4168;
      DxgkLogInternalTriageEvent(
        v115,
        0x40000,
        v116,
        (unsigned int)L"Overflow rounding allocation alignment (0x%08X) to next page boundary",
        v114,
        0,
        0,
        0);
      goto LABEL_295;
    }
  }
  else
  {
    v112 = v101;
  }
  v218 = v112;
  if ( v104 + (unsigned int)v112 < v104 || v215 + (unsigned int)v112 < v215 )
  {
    WdLogSingleEntry4(1, v104, v215, v104, (unsigned int)v112);
    WdLogGlobalForLineNumber = 4186;
    DxgkLogInternalTriageEvent(
      v219,
      0x40000,
      v192,
      (unsigned int)L"Overflow adding alignment to allocation size, Size=%d, PitchAlignedSize=%d, SystemMemorySize=%d, Alignment=%d",
      v219,
      v215,
      v219,
      (unsigned int)v218);
    v73 = -1073741811;
LABEL_455:
    v75 = (char *)v210;
    goto LABEL_456;
  }
LABEL_316:
  if ( (Value & 0x10000000) != 0 )
    LODWORD(Value) = Value | 8;
  if ( (Value & 0x20000000) == 0 || (Value & 0x10) != 0 )
    v113 = 0;
  else
    v113 = 512;
  v117 = v236;
  v118 = v113 | *((_DWORD *)v78 + 7) & 0xFFFFFDFF;
  *((_DWORD *)v78 + 19) = 0;
  *((_DWORD *)v78 + 7) = v118;
  v119 = (_DWORD *)(v117 + 4);
  **((_DWORD **)v78 + 49) = Value;
  *(_DWORD *)(*((_QWORD *)v78 + 49) + 4LL) = v51;
  v120 = *((_DWORD *)v78 + 6) & 0xFFFFFFFD;
  *((_DWORD *)v78 + 18) = 0;
  *((_DWORD *)v78 + 32) = 0;
  *((_QWORD *)v78 + 1) = v117;
  v121 = (v120 | (2 * (v45 & 1))) ^ ((v120 | (2 * (v45 & 1))) ^ ((unsigned int)v45 >> 1)) & 1;
  v122 = v121 ^ (v121 ^ ((unsigned __int8)v213 << 27)) & 0x8000000;
  v123 = (unsigned __int8)v233;
  LODWORD(v221) = v122;
  *((_DWORD *)v78 + 6) = v122;
  v124 = (32 * (unsigned __int8)SwizzledFormat)
       | (16 * v123) & 0xFFFFFFDF
       | v206.Value & 0xFFFFFFCF
       | Version & 0xFFFFFF8F
       | *((_DWORD *)v78 + 7) & 0xFFFFFF87;
  v125 = v124 ^ ((unsigned __int16)v124 ^ (unsigned __int16)((_WORD)v51 << 12)) & 0x1000;
  *((_DWORD *)v78 + 7) = v125;
  if ( v117 && (*v119 & 0x10000000) != 0 )
    v126 = 0x2000;
  else
    v126 = 0;
  v127 = v126 | v125 & 0xFFFFDFFF;
  v128 = (_DWORD *)*((_QWORD *)v78 + 49);
  v129 = (v243 != 0 ? 0x800000 : 0) | (unsigned int)v221 & 0xFF7FFFFB | (v244 != 0 ? 4 : 0);
  v130 = v127 ^ ((unsigned __int16)v127 ^ (unsigned __int16)((_WORD)v51 << 9)) & 0x8000;
  *((_DWORD *)v78 + 6) = v129;
  *((_DWORD *)v78 + 7) = v130;
  v131 = v130 & 0xFFFEFFFF | ((*v128 & 0xC0000100) != 0 ? 0x10000 : 0);
  v173 = v236 == 0;
  *((_DWORD *)v78 + 7) = v131;
  if ( v173 || (*v119 & 0x40000000) == 0 )
    v132 = 0;
  else
    v132 = 0x20000;
  v133 = v244;
  v134 = v132 | v131 & 0xFFFDFFFF;
  *((_DWORD *)v78 + 7) = v134;
  if ( v133 )
  {
    *((_QWORD *)v78 + 8) = v133;
  }
  else if ( v243 )
  {
    *((_QWORD *)v78 + 8) = v243;
  }
  else
  {
    v135 = v246;
    if ( v246 )
    {
      *((_QWORD *)v78 + 8) = v246;
      *((_DWORD *)v78 + 7) = v134 | 0x4000;
      *((_DWORD *)v78 + 6) = v129 & 0xFFFFFF7F | ~((unsigned __int8)*(_DWORD *)(v135 + 176) << 6) & 0x80;
    }
  }
  v136 = VidMmiSelectAllocationHeap(v222, v78, *(unsigned int *)(a1 + 41448));
  *(_QWORD *)(v137 + 232) = v136;
  if ( v136 && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v136 + 120LL))(v136) )
    v138 = v205;
  else
    v138 = 1;
  v139 = v210;
  v140 = (v138 << 7) | *((_DWORD *)v210 + 7) & 0xFFFFFF7F;
  v141 = 0;
  *((_DWORD *)v210 + 7) = v140;
  LOBYTE(v233) = 0;
  if ( (Value & 1) != 0 && (v140 & 0x80u) == 0 && !(_BYTE)Width )
  {
    v141 = ((*(_DWORD *)(*(_QWORD *)(a1 + 24) + 444LL) & 8) != 0 || VidMmCheckForCpuVisibleMemorySegment(v214, a9))
        && !v133
        && (*((_DWORD *)v139 + 6) & 2) == 0;
    LOBYTE(v233) = v141;
  }
  v142 = v214;
  v143 = v215;
  v144 = v219;
  *((_DWORD *)v139 + 7) = (v141 << 10) | *((_DWORD *)v139 + 7) & 0xFFFFFBFF;
  v203 = v224[0];
  v73 = (*(__int64 (__fastcall **)(struct VIDMM_PHYSICAL_ADAPTER *, struct VIDMM_GLOBAL_ALLOC *, unsigned __int64, unsigned __int64, unsigned __int64, _DWORD, int, _DWORD, unsigned int))(*(_QWORD *)v142 + 32LL))(
          v142,
          v139,
          a4,
          v144,
          v143,
          v220,
          v204,
          v218,
          a9);
  if ( v73 < 0 )
    goto LABEL_455;
  v173 = (_BYTE)Width == 0;
  v145 = v210;
  *(_QWORD *)v210 = v223;
  if ( v173 )
  {
    if ( (dword_1400875B4
       || (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 36480) + 8LL * (unsigned int)v224[0]) + 44LL) & 1) != 0)
      && (**(_DWORD **)(*(_QWORD *)(a1 + 24) + 3136LL) & 0x4000) == 0
      && (v45 & 2) != 0
      && v228
      && ((*v228 & 0x200) != 0 || dword_1400875B4 == 2)
      && ((v146 = *(_QWORD *)(v223 + 16), !(_WORD)v146) || v146 > (unsigned int)dword_1400875B8)
      && !(_BYTE)v233 )
    {
      v147 = 0x10000000;
    }
    else
    {
      v147 = 0;
    }
    *((_DWORD *)v145 + 6) = v147 | *((_DWORD *)v145 + 6) & 0xEFFFFFFF;
    if ( g_Feature_Largify64KBPrototype )
    {
      v148 = *((_DWORD *)v145 + 6);
      if ( (v148 & 0x18000000) == 0x18000000 )
      {
        v149 = *((_DWORD *)v145 + 7);
        if ( (v149 & 0x4200) == 0
          && (v148 & 0x800004) == 0
          && (Value & 8) == 0
          && (Value & 0x20000) == 0
          && (Value & 0x8000000) == 0
          && (Value & 0x4000) == 0
          && ((v149 & 0x8000) != 0 || (*(_DWORD *)(*(_QWORD *)(a1 + 24) + 444LL) & 8) != 0)
          && ((*((_BYTE *)v214 + 1350) & 8) != 0
           || (v150 = (_DWORD *)*((_QWORD *)v214 + 169)) != 0 && (*v150 & 0x80u) != 0) )
        {
          *((_DWORD *)v145 + 6) |= 0x20000000u;
        }
      }
    }
  }
  else
  {
    *((_DWORD *)v145 + 6) |= 0x10000000u;
  }
  if ( (*((_DWORD *)v145 + 7) & 0x8000) != 0
    && (*((_DWORD *)v145 + 6) & 0x20000000) == 0
    && (*((_DWORD *)DXGGLOBAL::GetGlobal() + 64) & 0x20) != 0 )
  {
    if ( (*((_DWORD *)v145 + 6) & 0x10000000) != 0 )
    {
      v155 = 1;
      if ( (*((_BYTE *)v214 + 1350) & 8) == 0 )
      {
        v154 = (_DWORD *)*((_QWORD *)v214 + 169);
        if ( !v154 || (*v154 & 0x80u) == 0 )
          v155 = 0;
      }
      v156 = *((_DWORD *)v145 + 6);
      v157 = (v156 & 0x8000000) == 0
          || (*((_DWORD *)v145 + 7) & 0x4200) != 0
          || (v156 & 0x800004) != 0
          || (Value & 8) != 0
          || (Value & 0x20000) != 0
          || (Value & 0x8000000) != 0
          || (Value & 0x4000) != 0;
      WdLogSingleEntry3(4, v157, g_Feature_Largify64KBPrototype, v155);
      WdLogGlobalForLineNumber = 4393;
    }
    else
    {
      v151 = *(_QWORD *)(v223 + 16);
      v152 = !(_WORD)v151 || v151 > (unsigned int)dword_1400875B8;
      v153 = v228 && ((*v228 & 0x200) != 0 || dword_1400875B4 == 2);
      WdLogSingleEntry5(
        4,
        (unsigned int)dword_1400875B4,
        *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 36480) + 8LL * (unsigned int)v224[0]) + 44LL) & 1,
        (v45 >> 1) & 1,
        v153,
        v152);
      WdLogGlobalForLineNumber = 4372;
      WdLogSingleEntry1(4, (unsigned __int8)v233 ^ 1LL);
      WdLogGlobalForLineNumber = 4374;
    }
    __debugbreak();
  }
  v158 = v240;
  if ( v236 )
    v158 = *(_QWORD *)(v236 + 16);
  v75 = (char *)v210;
  *(_QWORD *)(*((_QWORD *)v210 + 49) + 48LL) = v158;
  if ( v237 )
  {
    v159 = v237;
  }
  else
  {
    v159 = (void *)v238;
    if ( !v238 && v239 )
      v159 = v239;
  }
  v73 = VIDMM_GLOBAL::CommitGlobalBackingStore((VIDMM_GLOBAL *)a1, (struct VIDMM_GLOBAL_ALLOC *)v75, v222, v159, v248);
  if ( v73 < 0 )
    goto LABEL_456;
  if ( (Value & 0x4000) != 0 )
    *((_DWORD *)v75 + 6) |= 0x2000000u;
  *((_DWORD *)v75 + 6) ^= (*((_DWORD *)v75 + 6) ^ ((unsigned __int8)v242 << 24)) & 0x1000000;
  *(_DWORD *)(v223 + 56) = v241;
  v160 = v214;
  *((_QWORD *)v75 + 15) = v75 + 112;
  *((_QWORD *)v75 + 14) = v75 + 112;
  LOBYTE(v233) = (*((_DWORD *)v75 + 6) & 2) != 0;
  MostPreferredSegment = (const struct VIDMM_SEGMENT_BASE *)VidMmGetMostPreferredSegment(v160, v30, (__int64 *)va);
  *((_DWORD *)v75 + 6) = v162 ^ (v162 ^ (16 * (unsigned __int8)v233)) & 0x10;
  v163 = VidMmVerifyBudgetGroups(v214, a9, MostPreferredSegment, (struct _VIDMM_VERIFY_BUDGET_GROUPS *)&Height);
  v164 = 0;
  if ( !v163 )
  {
    v73 = -1073741811;
    goto LABEL_456;
  }
  *((_DWORD *)v75 + 6) = ((unsigned __int8)Height << 8) | *((_DWORD *)v75 + 6) & 0xFFFF00FF;
  if ( (Value & 0x10) != 0 || (Value & 0x20) != 0 )
    v75[42] = 1;
  v165 = v219;
  if ( !v244 )
  {
    LogicalMemory = SysMmAllocateLogicalMemory(
                      *(struct SYSMM_ADAPTER **)(*(_QWORD *)(a1 + 24) + 224LL),
                      v219,
                      v75,
                      (void **)v75 + 46);
    v164 = 0;
    v73 = LogicalMemory;
    if ( LogicalMemory < 0 )
    {
      WdLogSingleEntry1(1, v75);
      WdLogGlobalForLineNumber = 4491;
      DxgkLogInternalTriageEvent(
        v167,
        0x40000,
        v168,
        (unsigned int)L"Failed to allocate logical address range for global alloc 0x%.16I64x",
        (__int64)v75,
        0,
        0,
        0);
      goto LABEL_456;
    }
  }
  if ( g_Feature_ResourcePoolManagement )
  {
    v169 = v226;
    v170 = v225;
    *((_QWORD *)v75 + 44) = *(_QWORD *)(v226 + 32) + 384LL * *(unsigned int *)(*(_QWORD *)(a1 + 24) + 240LL);
    v171 = (volatile signed __int32 *)(v169 + 24);
  }
  else
  {
    v172 = VIDMM_GLOBAL::AdapterId((VIDMM_GLOBAL *)a1);
    v169 = v226;
    v170 = v225;
    *((_QWORD *)v75 + 43) = *(_QWORD *)(v225 + 40) + 384LL * v172;
    v171 = (volatile signed __int32 *)(v170 + 36);
  }
  _InterlockedIncrement(v171);
  if ( g_Feature_ResourcePoolManagement == (_BYTE)v164 )
    v173 = *(_DWORD *)(v170 + 32) == v164;
  else
    v173 = *(_DWORD *)(*(_QWORD *)(v169 + 40) + 96LL) == v164;
  if ( !v173
    || (v174 = **((_DWORD **)v75 + 49), (v174 & 0x2003A) != 0)
    || (v175 = *((_DWORD *)v75 + 7), (v175 & 0x10) != 0)
    || (*((_DWORD *)v75 + 6) & 4) != 0
    || (v175 & 2) != 0
    || (v174 & 0x40000000) != 0 )
  {
    LODWORD(v227) = v164;
  }
  *((_DWORD *)v75 + 7) = v227 | *((_DWORD *)v75 + 7) & 0xFFFFFEFF;
  AllocationHint = VidMmGetAllocationHint((const struct VIDMM_GLOBAL_ALLOC *)v75);
  if ( (byte_140087201 & 0x10) != 0 )
  {
    v182 = v181;
    LOBYTE(v183) = v181;
    LOBYTE(v182) = v180 != 0;
    LODWORD(v233) = v182;
    LODWORD(v246) = AllocationHint->v1.Depth;
    LODWORD(v221) = AllocationHint->v1.Pitch;
    Height = AllocationHint->v1.Height;
    Width = AllocationHint->v1.Width;
    LODWORD(v220) = AllocationHint->v1.ByteOffset;
    SwizzledFormat = AllocationHint->v1.SwizzledFormat;
    PrivateFormat = AllocationHint->v1.PrivateFormat;
    v184 = (struct _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0::$5068715F5D8591D41DA1228877FDA04B::$63766B29C143116E9EC685C38896947D)AllocationHint->v1.Flags.Value;
    Version = AllocationHint->Version;
    v228 = (_DWORD *)*((_QWORD *)v75 + 1);
    v215 = *(_QWORD *)(v179 + 24);
    v206.0 = v184;
    if ( a2 )
      v183 = *((_QWORD *)a2 + 3);
    CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
    McTemplateK0pppqxqqqqqqqpppqqqqqqqqqqtphtp_EtwWriteTransfer(
      v215,
      (unsigned int)EventCreateAdapterAllocation,
      v186,
      CurrentProcessId,
      v183,
      v215,
      v12,
      v165,
      v218,
      a10,
      a9,
      v30,
      v203,
      a10,
      v241,
      (char)v75,
      (char)v228);
    LOBYTE(v181) = 0;
  }
  _InterlockedAdd((volatile signed __int32 *)(a1 + 3760), 1u);
  _InterlockedAdd64((volatile signed __int64 *)(a1 + 3768), v165);
  _InterlockedAdd64((volatile signed __int64 *)(a1 + 36448), v165);
  if ( a2 )
  {
    v187 = *((_QWORD *)a2 + 2);
    if ( v187 )
    {
      BucketIdForAllocationSizePow2 = GetBucketIdForAllocationSizePow2(v165, v177, *(_QWORD *)(v187 + 184));
      _InterlockedAdd64((volatile signed __int64 *)(v189 + 8LL * BucketIdForAllocationSizePow2 + 56), v165);
      _InterlockedAdd((volatile signed __int32 *)(v189 + 4LL * BucketIdForAllocationSizePow2 + 232), v190);
      *(_BYTE *)(v189 + 320) = v190;
    }
  }
  if ( g_IsInternalReleaseOrDbg != (_BYTE)v181 )
  {
    *(_QWORD *)(WdLogNewEntry5_WdTrace(v178) + 24) = v75;
    WdLogGlobalForLineNumber = 4610;
  }
  *v247 = v75;
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
