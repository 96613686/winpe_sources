# VIDMM_GLOBAL::CreateOneAllocation(VIDMM_DEVICE *,ulong,unsigned __int64,unsigned __int64,ulong,_DXGK_PAGESIZE,_DXGK_PAGESIZE,ulong,ulong,ulong,_D3DDDI_SEGMENTPREFERENCE,_DXGK_ALLOCATIONINFOFLAGS,_DXGK_ALLOCATIONINFOFLAGS2,DXGADAPTERALLOCATION const *,void *,void *,void *,ulong,uchar,void *,VIDMM_PAGE_TABLE_BASE *,VIDMM_CROSSADAPTER_ALLOC * *,VIDMM_FENCE_STORAGE_PAGE *,VIDMM_GLOBAL_ALLOC * *,uchar *)

- ea: `0x140105808`
- end: `0x140107a09`
- name: `?CreateOneAllocation@VIDMM_GLOBAL@@QEAAJPEAVVIDMM_DEVICE@@K_K1KW4_DXGK_PAGESIZE@@2KKKU_D3DDDI_SEGMENTPREFERENCE@@U_DXGK_ALLOCATIONINFOFLAGS@@U_DXGK_ALLOCATIONINFOFLAGS2@@PEBVDXGADAPTERALLOCATION@@PEAX77KE7PEAVVIDMM_PAGE_TABLE_BASE@@PEAPEAUVIDMM_CROSSADAPTER_ALLOC@@PEAVVIDMM_FENCE_STORAGE_PAGE@@PEAPEAUVIDMM_GLOBAL_ALLOC@@PEAE@Z`
- size: `8705`
- prototype: ``
- caller_count: `5`
- callee_count: `32`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400311f0`
- `0x1400bc240`
- `0x1400bdbf8`
- `0x140103bfc`
- `0x140105510`

## callees

- `0x1400037a0`
- `0x1400045ec`
- `0x140017380`
- `0x14002f510`
- `0x14003056c`
- `0x140030ae0`
- `0x140030d18`
- `0x140031178`
- `0x1400327b8`
- `0x140032d60`
- `0x140039acc`
- `0x1400472a8`
- `0x140058760`
- `0x140058ac0`
- `0x1400baf4c`
- `0x1400bb59c`
- `0x1400bd658`
- `0x1400e0950`
- `0x1400ef544`
- `0x1401000ac`
- `0x140102e90`
- `0x140102eb4`
- `0x140103068`
- `0x140105808`
- `0x14010aef8`
- `0x14010b314`
- `0x14010b43c`
- `0x14010b490`
- `0x14010f210`
- `0x14010f350`
- `0x140113ab8`
- `0x1401186d8`

## import_xrefs

- `ntoskrnl!PsGetProcessWow64Process` at `0x140105b11`
- `ntoskrnl!PsGetProcessWow64Process` at `0x140105b11`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140107601`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140107601`
- `ntoskrnl!PsGetCurrentProcess` at `0x140105b02`
- `ntoskrnl!PsGetCurrentProcess` at `0x140105b02`
- `watchdog!WdLogSingleEntry3` at `0x140106c8e`
- `watchdog!WdLogSingleEntry3` at `0x140107309`
- `watchdog!WdLogSingleEntry3` at `0x140106c8e`
- `watchdog!WdLogSingleEntry3` at `0x140107309`
- `watchdog!WdLogSingleEntry4` at `0x1401077ba`
- `watchdog!WdLogSingleEntry4` at `0x1401077ba`
- `watchdog!WdLogSingleEntry2` at `0x1401065d6`
- `watchdog!WdLogSingleEntry2` at `0x140106c30`
- `watchdog!WdLogSingleEntry2` at `0x140106c5c`
- `watchdog!WdLogSingleEntry2` at `0x1401065d6`
- `watchdog!WdLogSingleEntry2` at `0x140106c30`
- `watchdog!WdLogSingleEntry2` at `0x140106c5c`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14010596e`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x140105997`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401059d8`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14010777b`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14010596e`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x140105997`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401059d8`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14010777b`
- `watchdog!WdLogSingleEntry5` at `0x14010725a`
- `watchdog!WdLogSingleEntry5` at `0x140107940`
- `watchdog!WdLogSingleEntry5` at `0x14010725a`
- `watchdog!WdLogSingleEntry5` at `0x140107940`
- `watchdog!WdLogSingleEntry0` at `0x140105a3c`
- `watchdog!WdLogSingleEntry0` at `0x140105b90`
- `watchdog!WdLogSingleEntry0` at `0x140105bb2`
- `watchdog!WdLogSingleEntry0` at `0x140105beb`
- `watchdog!WdLogSingleEntry0` at `0x140105c6b`
- `watchdog!WdLogSingleEntry0` at `0x140105cab`
- `watchdog!WdLogSingleEntry0` at `0x140105cd8`
- `watchdog!WdLogSingleEntry0` at `0x140105cfe`
- `watchdog!WdLogSingleEntry0` at `0x140105d30`
- `watchdog!WdLogSingleEntry0` at `0x140105da7`
- `watchdog!WdLogSingleEntry0` at `0x140105dd6`
- `watchdog!WdLogSingleEntry0` at `0x140105e05`
- `watchdog!WdLogSingleEntry0` at `0x140105e58`
- `watchdog!WdLogSingleEntry0` at `0x140105e81`
- `watchdog!WdLogSingleEntry0` at `0x140105eaf`
- `watchdog!WdLogSingleEntry0` at `0x140105ef0`
- `watchdog!WdLogSingleEntry0` at `0x140105f20`
- `watchdog!WdLogSingleEntry0` at `0x140105f7c`
- `watchdog!WdLogSingleEntry0` at `0x140105fd1`
- `watchdog!WdLogSingleEntry0` at `0x140106005`
- `watchdog!WdLogSingleEntry0` at `0x14010603e`
- `watchdog!WdLogSingleEntry0` at `0x140106087`
- `watchdog!WdLogSingleEntry0` at `0x1401060b6`
- `watchdog!WdLogSingleEntry0` at `0x140106105`
- `watchdog!WdLogSingleEntry0` at `0x140106144`
- `watchdog!WdLogSingleEntry0` at `0x14010618b`
- `watchdog!WdLogSingleEntry0` at `0x1401061f0`
- `watchdog!WdLogSingleEntry0` at `0x140106273`
- `watchdog!WdLogSingleEntry0` at `0x1401062cc`
- `watchdog!WdLogSingleEntry0` at `0x1401062fd`
- `watchdog!WdLogSingleEntry0` at `0x140106329`
- `watchdog!WdLogSingleEntry0` at `0x140106353`
- `watchdog!WdLogSingleEntry0` at `0x140106382`
- `watchdog!WdLogSingleEntry0` at `0x1401064d1`
- `watchdog!WdLogSingleEntry0` at `0x1401066fe`
- `watchdog!WdLogSingleEntry0` at `0x1401067a2`
- `watchdog!WdLogSingleEntry0` at `0x140106817`
- `watchdog!WdLogSingleEntry0` at `0x1401069a5`
- `watchdog!WdLogSingleEntry0` at `0x140106bae`
- `watchdog!WdLogSingleEntry0` at `0x140107962`
- `watchdog!WdLogSingleEntry0` at `0x1401079aa`
- `watchdog!WdLogSingleEntry0` at `0x140105a3c`
- `watchdog!WdLogSingleEntry0` at `0x140105b90`
- `watchdog!WdLogSingleEntry0` at `0x140105bb2`
- `watchdog!WdLogSingleEntry0` at `0x140105beb`
- `watchdog!WdLogSingleEntry0` at `0x140105c6b`
- `watchdog!WdLogSingleEntry0` at `0x140105cab`
- `watchdog!WdLogSingleEntry0` at `0x140105cd8`
- `watchdog!WdLogSingleEntry0` at `0x140105cfe`
- `watchdog!WdLogSingleEntry0` at `0x140105d30`
- `watchdog!WdLogSingleEntry0` at `0x140105da7`
- `watchdog!WdLogSingleEntry0` at `0x140105dd6`
- `watchdog!WdLogSingleEntry0` at `0x140105e05`
- `watchdog!WdLogSingleEntry0` at `0x140105e58`
- `watchdog!WdLogSingleEntry0` at `0x140105e81`
- `watchdog!WdLogSingleEntry0` at `0x140105eaf`
- `watchdog!WdLogSingleEntry0` at `0x140105ef0`
- `watchdog!WdLogSingleEntry0` at `0x140105f20`
- `watchdog!WdLogSingleEntry0` at `0x140105f7c`
- `watchdog!WdLogSingleEntry0` at `0x140105fd1`
- `watchdog!WdLogSingleEntry0` at `0x140106005`
- `watchdog!WdLogSingleEntry0` at `0x14010603e`
- `watchdog!WdLogSingleEntry0` at `0x140106087`
- `watchdog!WdLogSingleEntry0` at `0x1401060b6`
- `watchdog!WdLogSingleEntry0` at `0x140106105`
- `watchdog!WdLogSingleEntry0` at `0x140106144`
- `watchdog!WdLogSingleEntry0` at `0x14010618b`
- `watchdog!WdLogSingleEntry0` at `0x1401061f0`
- `watchdog!WdLogSingleEntry0` at `0x140106273`
- `watchdog!WdLogSingleEntry0` at `0x1401062cc`
- `watchdog!WdLogSingleEntry0` at `0x1401062fd`
- `watchdog!WdLogSingleEntry0` at `0x140106329`
- `watchdog!WdLogSingleEntry0` at `0x140106353`
- `watchdog!WdLogSingleEntry0` at `0x140106382`
- `watchdog!WdLogSingleEntry0` at `0x1401064d1`
- `watchdog!WdLogSingleEntry0` at `0x1401066fe`
- `watchdog!WdLogSingleEntry0` at `0x1401067a2`
- `watchdog!WdLogSingleEntry0` at `0x140106817`
- `watchdog!WdLogSingleEntry0` at `0x1401069a5`
- `watchdog!WdLogSingleEntry0` at `0x140106bae`
- `watchdog!WdLogSingleEntry0` at `0x140107962`
- `watchdog!WdLogSingleEntry0` at `0x1401079aa`
- `watchdog!WdLogSingleEntry1` at `0x1401063d0`
- `watchdog!WdLogSingleEntry1` at `0x14010657d`
- `watchdog!WdLogSingleEntry1` at `0x140106adb`
- `watchdog!WdLogSingleEntry1` at `0x140106b49`
- `watchdog!WdLogSingleEntry1` at `0x140106d35`
- `watchdog!WdLogSingleEntry1` at `0x14010727d`
- `watchdog!WdLogSingleEntry1` at `0x14010749e`
- `watchdog!WdLogSingleEntry1` at `0x1401063d0`
- `watchdog!WdLogSingleEntry1` at `0x14010657d`
- `watchdog!WdLogSingleEntry1` at `0x140106adb`
- `watchdog!WdLogSingleEntry1` at `0x140106b49`
- `watchdog!WdLogSingleEntry1` at `0x140106d35`
- `watchdog!WdLogSingleEntry1` at `0x14010727d`
- `watchdog!WdLogSingleEntry1` at `0x14010749e`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x14010791b`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x140105950`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x140105981`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1401059c2`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x14010776f`

## string_xrefs

- `0x140105bc3`: `HardwareProtected allocations cannot be used with PermanentSysMem, Cached, CrossAdapter, CrossAdapterPrimary, Protected, ExistingSysMem, ExistingKernelSysMem`
- `0x140105bfc`: `Specified preferred segment is invalid. It must be a subset of the supported read segment set`
- `0x140105c7c`: `Can't create an allocation of zero size`
- `0x140105cbc`: `LinkInstanced/MapApertureCpuVisible flag is not supported in WDDM v2.x/<2.9, respectively`
- `0x140105de7`: `CpuVisibleOnDemand must also be set in combination with CpuVisible`
- `0x140105f01`: `Need to specify the CpuVisible flags in combination with PermanentSysMem`
- `0x140105f31`: `Shareable, ManagedPrimary and Primary can't be specified in combination with PermanentSysMem`
- `0x140105f8d`: `Cached allocations must only support cache coherent segments on adapters which have cache coherent aperture segments available`
- `0x140106201`: `PermanentSysMem, Cached, ExistingSysMem, ExistingKernelSysMem and Primary flags can't be specified with ManagedPrimary`
- `0x140106284`: `PermanentSysMem, Cached, ExistingSysMem, ExistingKernelSysMem and ManagedPrimary flags can't be specified with Primary`
- `0x1401062dd`: `PagingBuffer can't be combined with any other flags`
- `0x1401063dc`: `History buffer specifies invalid flag combination. Flags=%d`
- `0x140106bbf`: `Can't create an allocation that uses more than 4GB-64kB of system memory`

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
        UINT a11,
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
  __int64 v30; // r10
  char v31; // r11
  unsigned __int64 v32; // r12
  __int64 v33; // rax
  __int64 v34; // rdx
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
  int v47; // ecx
  __int64 Value; // rbx
  unsigned int v49; // r14d
  unsigned int v50; // edx
  unsigned int v51; // ecx
  __int64 v52; // r10
  unsigned int v53; // r11d
  unsigned int v54; // edx
  int v55; // edi
  unsigned int v56; // r8d
  unsigned int v57; // r9d
  int v58; // r11d
  int v59; // ecx
  int v60; // eax
  int v61; // eax
  int v62; // edx
  int v63; // ecx
  int v64; // r8d
  const wchar_t *v65; // r9
  UINT v66; // edx
  int v67; // ecx
  int v68; // r8d
  __int64 v69; // rax
  _QWORD *v70; // rax
  __int64 v71; // rax
  struct VIDMM_GLOBAL_ALLOC *v72; // rdx
  int v73; // ecx
  int v74; // r8d
  unsigned int v75; // edx
  VIDMM_GLOBAL *v76; // rcx
  int LogicalMemory; // edi
  _QWORD *v78; // rbx
  char *v79; // r14
  VIDMM_GLOBAL *v80; // r9
  struct VIDMM_GLOBAL_ALLOC *v81; // rcx
  struct VIDMM_GLOBAL_ALLOC *v82; // r11
  int v83; // ecx
  int v84; // r8d
  __int64 v85; // rax
  unsigned __int64 v86; // rdx
  int v87; // ecx
  int v88; // r8d
  __int64 v89; // r11
  unsigned __int64 v90; // r10
  __int64 v91; // rcx
  int v92; // r9d
  int SyncObject; // eax
  __int64 v94; // rax
  unsigned __int64 v95; // r8
  volatile signed __int32 *v96; // rcx
  int v97; // ecx
  int v98; // r8d
  __int64 v99; // rcx
  struct VIDMM_GLOBAL_ALLOC *v100; // rax
  __int64 v101; // rdx
  _DWORD *v102; // rcx
  struct VIDMM_CROSSADAPTER_ALLOC *v103; // rax
  int CrossAdapterDataDpc; // eax
  int v105; // r10d
  __int64 v106; // r9
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
  int v120; // r10d
  _DWORD *v121; // rax
  __int64 v122; // rdx
  unsigned int v123; // r10d
  UINT v124; // ecx
  unsigned int v125; // r9d
  int v126; // eax
  unsigned int v127; // r9d
  unsigned int v128; // edx
  __int64 v129; // r10
  _DWORD *v130; // rax
  unsigned int v131; // edx
  int v132; // edi
  unsigned int v133; // eax
  __int64 v134; // rdi
  __int64 v135; // rcx
  __int64 v136; // rax
  __int64 v137; // r11
  unsigned __int8 v138; // al
  struct VIDMM_GLOBAL_ALLOC *v139; // r11
  bool v140; // dl
  unsigned int v141; // ecx
  struct VIDMM_PHYSICAL_ADAPTER *v142; // r10
  unsigned __int64 v143; // rdi
  unsigned __int64 v144; // r9
  struct VIDMM_GLOBAL_ALLOC *v145; // rdi
  unsigned __int64 v146; // rcx
  int v147; // ecx
  int v148; // ecx
  int v149; // eax
  _DWORD *v150; // rax
  _DWORD *v151; // rax
  _BOOL8 v152; // r9
  int v153; // ecx
  _BOOL8 v154; // rdx
  __int64 v155; // rcx
  void *v156; // r9
  struct VIDMM_PHYSICAL_ADAPTER *v157; // rcx
  const struct VIDMM_SEGMENT_BASE *MostPreferredSegment; // rax
  int v159; // r11d
  unsigned __int64 v160; // rbx
  int v161; // ecx
  int v162; // r8d
  unsigned int v163; // eax
  __int64 v164; // rcx
  int v165; // edx
  int v166; // ecx
  const struct _DXGK_ALLOCATIONUSAGEHINT *AllocationHint; // rax
  __int64 BucketIdForAllocationSizePow2; // rdx
  __int64 v169; // rcx
  __int64 v170; // r8
  unsigned int v171; // r9d
  UINT v172; // ecx
  __int64 v173; // rsi
  unsigned int CurrentProcessId; // eax
  int v175; // r8d
  __int64 v176; // r8
  __int64 v177; // r8
  unsigned int v178; // r9d
  __int64 v180; // rdi
  int v181; // r8d
  __int64 v182; // rax
  __int64 i; // rsi
  void *v184; // rcx
  VIDMM_FLIP_QUEUE_REFERENCES *v185; // rcx
  struct VIDMM_CROSSADAPTER_ALLOC *v186; // rdx
  VIDMM_GLOBAL *v187; // rcx
  __int64 v188; // rdx
  int v189; // r8d
  int v190; // [rsp+60h] [rbp-130h]
  int v191; // [rsp+110h] [rbp-80h]
  char v192; // [rsp+114h] [rbp-7Ch]
  _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0 v193; // [rsp+118h] [rbp-78h] BYREF
  char v194; // [rsp+11Ch] [rbp-74h]
  PVOID P; // [rsp+120h] [rbp-70h]
  int v196; // [rsp+128h] [rbp-68h]
  UINT ByteOffset; // [rsp+12Ch] [rbp-64h]
  int Height; // [rsp+130h] [rbp-60h]
  struct VIDMM_GLOBAL_ALLOC *v199; // [rsp+138h] [rbp-58h]
  int Format; // [rsp+140h] [rbp-50h]
  struct VIDMM_PHYSICAL_ADAPTER *v201; // [rsp+148h] [rbp-48h]
  unsigned __int64 v202; // [rsp+150h] [rbp-40h] BYREF
  UINT Width; // [rsp+158h] [rbp-38h]
  UINT Pitch; // [rsp+15Ch] [rbp-34h] BYREF
  __int64 v205; // [rsp+160h] [rbp-30h]
  unsigned __int64 v206; // [rsp+168h] [rbp-28h]
  struct VIDMM_PROCESS *v207; // [rsp+170h] [rbp-20h]
  __int64 v208; // [rsp+178h] [rbp-18h]
  __int64 v209; // [rsp+180h] [rbp-10h]
  __int64 v210; // [rsp+188h] [rbp-8h]
  unsigned __int64 v211; // [rsp+190h] [rbp+0h]
  _DWORD *v212; // [rsp+198h] [rbp+8h]
  __int64 v213; // [rsp+1A0h] [rbp+10h]
  struct VIDMM_CROSSADAPTER_ALLOC *v214; // [rsp+1A8h] [rbp+18h]
  _QWORD v215[16]; // [rsp+1B0h] [rbp+20h] BYREF
  __int64 v219; // [rsp+2A0h] [rbp+110h] BYREF
  va_list va; // [rsp+2A0h] [rbp+110h]
  __int64 v221; // [rsp+2A8h] [rbp+118h]
  __int64 v222; // [rsp+2B0h] [rbp+120h]
  void *v223; // [rsp+2B8h] [rbp+128h]
  void *v224; // [rsp+2C0h] [rbp+130h]
  __int64 v225; // [rsp+2C8h] [rbp+138h]
  __int64 v226; // [rsp+2D0h] [rbp+140h]
  __int64 v227; // [rsp+2D8h] [rbp+148h]
  __int64 v228; // [rsp+2E0h] [rbp+150h]
  __int64 v229; // [rsp+2E8h] [rbp+158h]
  struct VIDMM_CROSSADAPTER_ALLOC **v230; // [rsp+2F0h] [rbp+160h]
  __int64 v231; // [rsp+2F8h] [rbp+168h]
  _QWORD *v232; // [rsp+300h] [rbp+170h]
  unsigned __int8 *v233; // [rsp+308h] [rbp+178h]
  va_list va1; // [rsp+310h] [rbp+180h] BYREF

  va_start(va1, a12);
  va_start(va, a12);
  v219 = va_arg(va1, _QWORD);
  v221 = va_arg(va1, _QWORD);
  v222 = va_arg(va1, _QWORD);
  v223 = va_arg(va1, void *);
  v224 = va_arg(va1, void *);
  v225 = va_arg(va1, _QWORD);
  v226 = va_arg(va1, _QWORD);
  v227 = va_arg(va1, _QWORD);
  v228 = va_arg(va1, _QWORD);
  v229 = va_arg(va1, _QWORD);
  v230 = va_arg(va1, struct VIDMM_CROSSADAPTER_ALLOC **);
  v231 = va_arg(va1, _QWORD);
  v232 = va_arg(va1, _QWORD *);
  v233 = va_arg(va1, unsigned __int8 *);
  v12 = v219;
  v14 = (struct _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0::$5068715F5D8591D41DA1228877FDA04B::$63766B29C143116E9EC685C38896947D)v219;
  v193.0 = (struct _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0::$5068715F5D8591D41DA1228877FDA04B::$63766B29C143116E9EC685C38896947D)v219;
  Current = DXGPROCESS::GetCurrent();
  v206 = (unsigned __int64)Current;
  v19 = Current;
  if ( !v231 || (v20 = *(_DWORD *)(v231 + 152), LOBYTE(v219) = 1, (v20 & 1) != 0) )
    LOBYTE(v219) = 0;
  if ( a2 )
  {
    v21 = (struct VIDMM_PROCESS *)*((_QWORD *)a2 + 1);
  }
  else
  {
    if ( !Current )
    {
      WdLogSingleEntry0(1);
      v39 = 2872;
      v40 = L"pVidMmProcess is not present";
      goto LABEL_449;
    }
    v22 = *((_QWORD *)Current + 8);
    if ( v22 )
      v21 = *(struct VIDMM_PROCESS **)(v22 + 8);
    else
      v21 = 0;
  }
  v23 = v226;
  v207 = v21;
  if ( (unsigned int)v226 <= 2 )
    v23 = 2;
  LODWORD(v226) = v23;
  if ( v19 && (v24 = *((_DWORD *)v19 + 102), (v24 & 0x100) != 0) )
  {
    v194 = 1;
    if ( (v24 & 0x400) == 0 && !v228 && (v12 & 1) != 0 )
    {
      v14 = (struct _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0::$5068715F5D8591D41DA1228877FDA04B::$63766B29C143116E9EC685C38896947D)(*(_DWORD *)&v14 & 0xFFFF7FFF);
      v193.0 = v14;
    }
  }
  else
  {
    v194 = 0;
  }
  v25 = 0;
  if ( *(_DWORD *)(a1 + 3112) != 1 )
    v25 = a3;
  v210 = *((_QWORD *)v21 + 42);
  v26 = *(_QWORD *)(a1 + 36480);
  v209 = v25;
  v202 = 0;
  v201 = *(struct VIDMM_PHYSICAL_ADAPTER **)(v26 + 8 * v25);
  v212 = (_DWORD *)*((_QWORD *)v201 + 136);
  VidMmConvertSegmentPreferences((const struct VIDMM_GLOBAL *)a1, a12, (struct VIDMM_SEGMENT_PREFERENCES *)&v202);
  v32 = v202;
  v205 = a6;
  if ( g_IsInternalReleaseOrDbg != (_BYTE)v30 )
  {
    v33 = WdLogNewEntry5_WdTrace(v28, v27);
    v30 = 0;
    *(_QWORD *)(v33 + 24) = a2;
    WdLogGlobalForLineNumber = 2933;
    if ( g_IsInternalReleaseOrDbg )
    {
      v35 = (_QWORD *)WdLogNewEntry5_WdTrace(v28, v34);
      v35[3] = a4;
      v35[4] = a6;
      v35[5] = a9;
      v35[6] = a10;
      WdLogGlobalForLineNumber = 2938;
      v37 = (_QWORD *)WdLogNewEntry5_WdTrace(a10, v36);
      v30 = 0;
      v37[3] = (unsigned int)v32;
      v37[4] = HIDWORD(v202);
      v37[5] = (unsigned int)v14;
      v28 = v222;
      v37[6] = v222;
      WdLogGlobalForLineNumber = 2943;
    }
    v29 = v207;
    v31 = 2;
  }
  *v232 = v30;
  if ( *(_DWORD *)(a1 + 40) < 0x5023u && (*(_DWORD *)&v14 & 0x40000) != 0 )
  {
    WdLogSingleEntry0(1);
    v39 = 2959;
    v40 = L"CpuVisibleOnDemand flag set, but on this driver is supposed to be reserved";
LABEL_449:
    v47 = 0;
    goto LABEL_450;
  }
  if ( (*(_DWORD *)&v14 & 0x20000) != 0 )
  {
    if ( (*(_BYTE *)&v14 & (unsigned __int8)v31) != 0
      || (*(_BYTE *)&v14 & 4) != 0 && (v28 = *(unsigned int *)(*(_QWORD *)(a1 + 24) + 444LL), (v28 & 8) == 0)
      || (*(_DWORD *)&v14 & 0x100000) != 0
      || (*(_DWORD *)&v14 & 0x80000) != 0
      || (*(_BYTE *)&v14 & 8) != 0
      || (*(_BYTE *)&v14 & 0x10) != 0
      || (*(_BYTE *)&v14 & 0x20) != 0 )
    {
      WdLogSingleEntry0(1);
      v39 = 2981;
      v40 = L"HardwareProtected allocations cannot be used with PermanentSysMem, Cached, CrossAdapter, CrossAdapterPrimary"
             ", Protected, ExistingSysMem, ExistingKernelSysMem";
      goto LABEL_449;
    }
    v14 = (struct _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0::$5068715F5D8591D41DA1228877FDA04B::$63766B29C143116E9EC685C38896947D)(*(_DWORD *)&v14 & 0xFFFBFFFE);
    v193.0 = v14;
  }
  if ( (*(_BYTE *)&v14 & 1) != 0 && (*(_DWORD *)&v14 & 0x40000) == 0
    || (LOBYTE(v196) = v30, (*(_BYTE *)&v14 & 0x10) != 0) )
  {
    LOBYTE(v196) = 1;
  }
  v41 = v219;
  if ( (_BYTE)v219 || (*(_BYTE *)&v14 & 8) != 0 || (*(_DWORD *)&v14 & 0x20000) != 0 )
    LOBYTE(v196) = v30;
  if ( (*((_DWORD *)v29 + 38) & 0x40) == 0 )
  {
    CurrentProcess = PsGetCurrentProcess(v28);
    if ( !PsGetProcessWow64Process(CurrentProcess)
      && (*(_DWORD *)&v14 & 0x20000000) == 0
      && (*(_DWORD *)&v14 & 0x40000000) == 0
      && *(int *)&v14 >= 0
      && (*(_DWORD *)&v14 & 0x10000000) == 0
      && (*(_BYTE *)&v14 & 8) == 0
      && (*(_DWORD *)&v14 & 0x400000) == 0
      && (*(_DWORD *)&v14 & 0x20000) == 0
      && !v41
      && !v228
      && !v229 )
    {
      v14 = (struct _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0::$5068715F5D8591D41DA1228877FDA04B::$63766B29C143116E9EC685C38896947D)(*(_DWORD *)&v14 & 0xFFFBFFFF);
      LOBYTE(v196) = 1;
      v193.0 = v14;
    }
  }
  if ( ((*(unsigned int *)&v14 >> 13) & 1) != 0 && (*(_BYTE *)(a1 + 37225) & 8) == 0 )
  {
    WdLogSingleEntry0(1);
    v39 = 3068;
    v40 = L"Drivers must support MapAperture2 to set the MapApertureCpuVisible flag";
    goto LABEL_449;
  }
  if ( !(unsigned __int8)VidMmValidatePreferredSegment(v201, v32, a9) )
  {
    WdLogSingleEntry0(1);
    v39 = 3078;
    v40 = L"Specified preferred segment is invalid. It must be a subset of the supported read segment set";
    goto LABEL_449;
  }
  if ( !dword_1400865E0 || (*(_BYTE *)&v14 & 1) != 0 )
  {
    v45 = a9;
    v43 = v201;
  }
  else
  {
    v43 = v201;
    if ( (v32 & 0x1F) != 0 )
    {
      v45 = 1 << ((v32 & 0x1F) - 1);
      a9 = v45;
    }
    else
    {
      v44 = *((_DWORD *)v201 + 21) & a9;
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
    v39 = 3119;
    v40 = L"Can't create an allocation of zero size";
    goto LABEL_449;
  }
  if ( ((*(unsigned int *)&v14 >> 13) & 1) != 0 )
  {
    if ( *(int *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 16LL) + 3116LL) < 2900 )
    {
      WdLogSingleEntry0(1);
      v39 = 3129;
      v40 = L"LinkInstanced/MapApertureCpuVisible flag is not supported in WDDM v2.x/<2.9, respectively";
      goto LABEL_449;
    }
    v46 = a4;
  }
  if ( (*(_WORD *)&v14 & 0x1000) != 0 )
  {
    WdLogSingleEntry0(1);
    v39 = 3136;
    v40 = L"PhysicallyContiguous flag is not not currently supported";
    goto LABEL_449;
  }
  if ( (v45 & *((_DWORD *)v43 + 19)) == 0 )
  {
    WdLogSingleEntry0(1);
    v39 = 3149;
    v40 = L"Specified segment set references invalid segment";
    goto LABEL_449;
  }
  if ( !v229 && (v45 & *((_DWORD *)v43 + 20)) == 0 )
  {
    WdLogSingleEntry0(1);
    v39 = 3162;
    v40 = L"Specified segment set references invalid segment";
LABEL_450:
    WdLogGlobalForLineNumber = v39;
    DxgkLogInternalTriageEvent(v47, 0x40000, v38, (_DWORD)v40, v39, 0, 0, 0);
    return 3221225485LL;
  }
  Pitch = 0;
  LODWORD(v219) = 0;
  if ( !VidMmVerifySupportedSegmentSetAndAdjustFlags(
          v43,
          v45,
          &v193,
          v46,
          a5,
          v228 != 0,
          (struct _VIDMM_VERIFY_SUPPORTED_SEGMENT *)va) )
  {
    WdLogSingleEntry0(1);
    v39 = 3179;
    v40 = L"VidMmVerifySupportedSegmentSetAndAdjustFlags failed";
    goto LABEL_450;
  }
  Value = v193.Value;
  if ( (v193.Value & 0x40000) != 0 )
  {
    if ( (*(_BYTE *)&v193.0 & 1) == 0 )
    {
      WdLogSingleEntry0(1);
      v39 = 3191;
      v40 = L"CpuVisibleOnDemand must also be set in combination with CpuVisible";
      goto LABEL_450;
    }
    if ( (*(_BYTE *)&v193.0 & 2) != 0 || (*(_BYTE *)&v193.0 & 0x20) != 0 || (*(_BYTE *)&v193.0 & 0x10) != 0 )
    {
      WdLogSingleEntry0(1);
      v39 = 3203;
      v40 = L"PermanentSysMem, ExistingKernelSysMem, and ExistingSysMem cannot be used with CpuVisibleOnDemand";
      goto LABEL_450;
    }
  }
  v49 = v219;
  v50 = a10;
  v211 = a5 & -(__int64)((v219 & 4) != 0);
  if ( a10 )
  {
    if ( (a10 & *((_DWORD *)v201 + 20)) == 0 )
    {
      WdLogSingleEntry0(1);
      v39 = 3229;
      v40 = L"EvictionSegmentSet must be a valid set of driver segments";
      goto LABEL_449;
    }
    if ( (~*((_DWORD *)v201 + 24) & a10) != 0 )
    {
      WdLogSingleEntry0(1);
      v39 = 3240;
      v40 = L"EvictionSegmentSet may only contain system memory segments";
      goto LABEL_449;
    }
    if ( VidMmCheckAnySegmentAllFlags(v201, a10, (struct _DXGK_SEGMENTFLAGS)32) )
    {
      WdLogSingleEntry0(1);
      v39 = 3255;
      v40 = L"Can't use a segment requiring pitch alignment for paging";
      goto LABEL_449;
    }
    v50 = a10;
  }
  v51 = ((unsigned int)Value >> 1) & 1;
  Height = v51;
  if ( v51 )
  {
    if ( (Value & 1) == 0 )
    {
      WdLogSingleEntry0(1);
      v39 = 3272;
      v40 = L"Need to specify the CpuVisible flags in combination with PermanentSysMem";
      goto LABEL_449;
    }
    if ( (Value & 0x20000000) != 0 || (int)Value < 0 || (Value & 0x40000000) != 0 )
    {
      WdLogSingleEntry0(1);
      v39 = 3283;
      v40 = L"Shareable, ManagedPrimary and Primary can't be specified in combination with PermanentSysMem";
      goto LABEL_449;
    }
  }
  v52 = a1;
  v53 = ((unsigned int)Value >> 2) & 1;
  LODWORD(v219) = v53;
  if ( v53 && (Value & 0x800000) == 0 && *(_BYTE *)(a1 + 3202) )
  {
    if ( !VidMmCheckAllSegmentsAllFlags(v201, v50, (struct _DXGK_SEGMENTFLAGS)16) )
    {
      WdLogSingleEntry0(1);
      v39 = 3319;
      v40 = L"Cached allocations must only support cache coherent segments on adapters which have cache coherent aperture "
             "segments available";
      goto LABEL_449;
    }
    v51 = Height;
    v52 = a1;
    v53 = v219;
  }
  v54 = ((unsigned int)Value >> 29) & 1;
  if ( v54 && (v51 || (Value & 8) != 0 || (Value & 0x20) != 0 || (Value & 0x40000000) != 0) )
  {
    WdLogSingleEntry0(1);
    v39 = 3338;
    v40 = L"PermanentSysMem, Protected, ExistingKernelSysMem, or Primary flags can't be specified with Shareable";
    goto LABEL_449;
  }
  v55 = v221;
  if ( (v221 & 1) != 0 && ((v49 & 1) == 0 || !v54) )
  {
    WdLogSingleEntry0(1);
    v39 = 3347;
    v40 = L"ShareBackingStoreWithKmd flag should be set only for shared aperture only allocations";
    goto LABEL_449;
  }
  if ( (Value & 0x100000) != 0 && (!v54 || !v230 || (v49 & 1) == 0) )
  {
    WdLogSingleEntry0(1);
    v39 = 3360;
    v40 = L"Cross adapter allocations must be shareable and support system memory only and SharedResource must be provided";
    goto LABEL_449;
  }
  v213 = 256;
  if ( v228 && (v51 || (Value & 0x100) != 0 || (Value & 0x200) != 0 || (Value & 0x40000000) != 0) )
  {
    WdLogSingleEntry0(1);
    v39 = 3380;
    v40 = L"PermanentSysMem, Overlay, Capture, or Primary flags can't be specified for context allocations";
    goto LABEL_449;
  }
  if ( (((unsigned int)Value >> 26) & 1) != 0 )
  {
    if ( (Value & 8) == 0 )
    {
      WdLogSingleEntry0(1);
      v39 = 3396;
      v40 = L"Protected flag must be specified with CddBitmap";
      goto LABEL_449;
    }
  }
  else if ( (Value & 8) == 0 )
  {
    goto LABEL_151;
  }
  if ( (Value & 1) != 0 && (((unsigned int)Value >> 26) & 1) == 0 && !v228
    || v51
    || v54
    || (Value & 0x10) != 0
    || (Value & 0x20) != 0
    || (int)Value < 0
    || (Value & 0x40000000) != 0 )
  {
    WdLogSingleEntry0(1);
    v39 = 3427;
    v40 = L"CpuVisible, PermanentSysMem, Shareable, ExistingSysMem, ExistingKernelSysMem, ManagedPrimary or Primary flags "
           "can't be specified with Protected";
    goto LABEL_449;
  }
LABEL_151:
  v56 = ((unsigned int)Value >> 4) & 1;
  if ( v56 && (v51 || (Value & 0x20) != 0 || (int)Value < 0 || (Value & 0x40000000) != 0) )
  {
    WdLogSingleEntry0(1);
    v39 = 3447;
    v40 = L"PermanentSysMem, ExistingKernelSysMem, ManagedPrimary or Primary flags can't be specified with ExistingSysMem";
    goto LABEL_449;
  }
  v57 = ((unsigned int)Value >> 5) & 1;
  if ( v57 && (v51 || v54 || v56 || (int)Value < 0 || (Value & 0x40000000) != 0) )
  {
    WdLogSingleEntry0(1);
    v39 = 3469;
    v40 = L"PermanentSysMem, Shareable, ExistingSysMem, ManagedPrimary or Primary flags can't be specified with ExistingKernelSysMem";
    goto LABEL_449;
  }
  if ( (int)Value >= 0 )
  {
    if ( (Value & 0x40000000) != 0 )
    {
      if ( v51
        || v53 && (v59 = *(_DWORD *)(*(_QWORD *)(v52 + 24) + 444LL), (v59 & 0x10) == 0) && (v59 & 8) == 0
        || v56
        || v57 )
      {
        WdLogSingleEntry0(1);
        v39 = 3513;
        v40 = L"PermanentSysMem, Cached, ExistingSysMem, ExistingKernelSysMem and ManagedPrimary flags can't be specified with Primary";
        goto LABEL_449;
      }
      if ( (*(_DWORD *)(*(_QWORD *)(v52 + 24) + 2580LL) & 0x200) == 0 )
        Value = (unsigned int)Value | 1;
      v60 = (unsigned __int8)v196;
      if ( (Value & 1) != 0 )
        v60 = 1;
      LODWORD(Value) = Value | 0x20000000;
      v196 = v60;
    }
  }
  else if ( v51
         || v53 && (v58 = *(_DWORD *)(*(_QWORD *)(v52 + 24) + 444LL), (v58 & 0x10) == 0) && (v58 & 8) == 0
         || v56
         || v57
         || (Value & 0x40000000) != 0 )
  {
    WdLogSingleEntry0(1);
    v39 = 3491;
    v40 = L"PermanentSysMem, Cached, ExistingSysMem, ExistingKernelSysMem and Primary flags can't be specified with ManagedPrimary";
    goto LABEL_449;
  }
  LODWORD(v219) = ((unsigned int)Value >> 28) & 1;
  if ( (_DWORD)v219 )
  {
    v61 = Value & 0xEFFF7FBF;
    v62 = *(_DWORD *)(*(_QWORD *)(v52 + 24) + 444LL);
    if ( (v62 & 8) != 0 || (v62 & 0x10) != 0 )
      v61 = Value & 0xEFFF7FBB;
    if ( v61 )
    {
      WdLogSingleEntry0(1);
      v39 = 3555;
      v40 = L"PagingBuffer can't be combined with any other flags";
      goto LABEL_449;
    }
    if ( (~*((_DWORD *)v201 + 24) & a9) != 0 )
    {
      WdLogSingleEntry0(1);
      v39 = 3565;
      v40 = L"Paging buffer can only be allocated from an aperture segment";
      goto LABEL_449;
    }
  }
  if ( (Value & 0x400000) != 0 )
  {
    if ( (Value & 0x20000000) == 0 )
    {
      WdLogSingleEntry0(1);
      v39 = 3581;
      v40 = L"SectionSupplied should always be Shareable resource";
      goto LABEL_449;
    }
    if ( !v223 )
    {
      WdLogSingleEntry0(1);
      v39 = 3591;
      v40 = L"SectionSupplied resource does not supply the section";
      goto LABEL_449;
    }
  }
  if ( (Value & 0x4000) != 0 )
  {
    if ( (Value & 1) == 0 )
    {
      WdLogSingleEntry0(1);
      v39 = 3603;
      v40 = L"History buffers must specify the CpuVisible flag";
      goto LABEL_449;
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
      v65 = L"History buffer specifies invalid flag combination. Flags=%d";
      WdLogGlobalForLineNumber = 3619;
LABEL_211:
      DxgkLogInternalTriageEvent(v63, 0x40000, v64, (_DWORD)v65, Value, 0, 0, 0);
      return 3221225485LL;
    }
  }
  if ( v230 )
    v214 = *v230;
  else
    v214 = 0;
  if ( (VIDMM_GLOBAL::_Config & 2) != 0
    && DXGPROCESS::GetCurrent()
    && (*((_DWORD *)DXGPROCESS::GetCurrent() + 102) & 4) != 0
    && !(_DWORD)v219
    && (Value & 0x40000000) == 0 )
  {
    LODWORD(Value) = Value | 0x8000000;
  }
  v192 = 0;
  LOBYTE(v219) = 0;
  LOBYTE(Width) = 0;
  if ( !v194 || v228 )
  {
    Format = 0;
    goto LABEL_234;
  }
  if ( (Value & 0x10) != 0 )
  {
    LOBYTE(v196) = 0;
    Format = 8;
    v193.0 = (struct _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0::$5068715F5D8591D41DA1228877FDA04B::$63766B29C143116E9EC685C38896947D)64;
    goto LABEL_235;
  }
  if ( (Value & 1) == 0 )
  {
    Format = 8;
LABEL_234:
    v193.0 = 0;
    goto LABEL_235;
  }
  if ( (Value & 0x8000) != 0 && (*(_DWORD *)(v206 + 408) & 0x400) == 0 )
  {
    WdLogSingleEntry0(1);
    v39 = 3671;
    v40 = L"Cpu visible paravirtualized allocations cannot be places to aperture segment";
    goto LABEL_449;
  }
  v66 = *(_DWORD *)(v206 + 408) >> 10;
  LOBYTE(v66) = (*(_DWORD *)(v206 + 408) & 0x400) != 0;
  Format = 8;
  Width = v66;
  v193.0 = 0;
  LOBYTE(v219) = v66 ^ 1;
  if ( (Value & 0x20000000) != 0 )
  {
    v192 = 1;
    LOBYTE(v219) = v66 ^ 1;
  }
  else
  {
    Width = v66;
    v192 = v66 ^ 1;
  }
LABEL_235:
  if ( *(int *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 16LL) + 3116LL) >= 3000
    && (Value & 1) != 0
    && (v49 & 2) == 0
    && !v229
    && (Value & 0x40000000) == 0 )
  {
    WdLogSingleEntry1(1, Value);
    v65 = L"CPUVisible allocations must include an aperture segment in the supported segment set";
    WdLogGlobalForLineNumber = 3718;
    goto LABEL_211;
  }
  if ( v224 && (v224 != (void *)((unsigned __int64)v224 & 0xFFFFFFFFFFFFF000uLL) || (a4 & 0xFFF) != 0) )
  {
    WdLogSingleEntry2(1, v224, a4);
    WdLogGlobalForLineNumber = 3736;
    DxgkLogInternalTriageEvent(
      v67,
      0x40000,
      v68,
      (unsigned int)L"Existing sysmem pointer must be paged aligned and a multiple of page in size. pExistingSysMem=0x%.16x, Size=%I64u",
      (__int64)v224,
      a4,
      0,
      0);
    return 3221225485LL;
  }
  v208 = 0;
  v69 = operator new(392, 825256278, 256);
  P = (PVOID)v69;
  if ( !v69 )
    goto LABEL_447;
  *(_QWORD *)(v69 + 144) = 0;
  *(_QWORD *)(v69 + 152) = 0;
  *(_QWORD *)(v69 + 160) = 0;
  *(_DWORD *)(v69 + 168) = 0;
  *(_QWORD *)(v69 + 192) = 0;
  *(_QWORD *)(v69 + 200) = 0;
  *(_DWORD *)(v69 + 172) = 13;
  *(_DWORD *)(v69 + 176) = 17;
  *(_DWORD *)(v69 + 208) = 0;
  *(_QWORD *)(v69 + 216) = 0;
  *(_QWORD *)(v69 + 320) = 0;
  *(_QWORD *)(v69 + 328) = 0;
  *(_DWORD *)(v69 + 212) = 78;
  *(_DWORD *)(v69 + 336) = 0;
  *(_DWORD *)(v69 + 340) = 18;
  *(_OWORD *)(v69 + 368) = 0;
  v70 = (_QWORD *)(v69 + 96);
  v70[1] = v70;
  *v70 = v70;
  v71 = operator new(56, 842295638, 64);
  v72 = (struct VIDMM_GLOBAL_ALLOC *)P;
  v202 = (unsigned __int64)P + 384;
  *((_QWORD *)P + 48) = v71;
  if ( !v71 )
  {
    _InterlockedIncrement(&dword_1400867D8);
    WdLogSingleEntry0(6);
    WdLogGlobalForLineNumber = 3787;
    DxgkLogInternalTriageEvent(
      v73,
      262145,
      v74,
      (unsigned int)L"Couldn't allocate memory for VIDMM_GLOBAL_ALLOC_NONPAGED",
      3787,
      0,
      0,
      0);
    LogicalMemory = -1073741801;
LABEL_248:
    v78 = P;
    v79 = (char *)P;
LABEL_427:
    if ( (*((_DWORD *)v79 + 8) & 0x20) != 0 )
      VIDMM_GLOBAL::UncommitGlobalBackingStore((VIDMM_GLOBAL *)a1, (struct VIDMM_GLOBAL_ALLOC *)v79, 1);
    v182 = *((_QWORD *)v79 + 48);
    if ( v182 )
    {
      if ( *(_QWORD *)(v182 + 32) )
      {
        for ( i = 0; i != 2; ++i )
        {
          v184 = *(void **)(*(_QWORD *)(v78[48] + 32LL) + 8 * i);
          if ( v184 )
            VidSchDestroySyncObject(v184);
        }
        operator delete(*(void **)(*((_QWORD *)v79 + 48) + 32LL));
      }
      v185 = *(VIDMM_FLIP_QUEUE_REFERENCES **)(*((_QWORD *)v79 + 48) + 24LL);
      if ( v185 )
        VIDMM_FLIP_QUEUE_REFERENCES::ReleaseReference(v185, v75);
      operator delete(*((void **)v79 + 48));
    }
    v186 = (struct VIDMM_CROSSADAPTER_ALLOC *)*((_QWORD *)v79 + 44);
    if ( !v186 )
      goto LABEL_442;
    VIDMM_GLOBAL::FreeCrossAdapterDataDpc(v76, v186, (struct VIDMM_GLOBAL_ALLOC *)v79);
    v187 = (VIDMM_GLOBAL *)(unsigned int)_InterlockedDecrement(*((volatile signed __int32 **)v79 + 44));
    if ( !(_DWORD)v187 )
    {
      VIDMM_GLOBAL::DestroyCrossAdapterAllocation(v187, *((struct VIDMM_CROSSADAPTER_ALLOC **)v79 + 44));
      *v230 = 0;
LABEL_442:
      v188 = *(_QWORD *)v79;
      if ( *(_QWORD *)v79 )
      {
        (*(void (__fastcall **)(struct VIDMM_PHYSICAL_ADAPTER *))(*(_QWORD *)v201 + 40LL))(v201);
        *(_QWORD *)v79 = 0;
      }
      VIDMM_GLOBAL_ALLOC::`scalar deleting destructor'(v79, v188);
      return (unsigned int)LogicalMemory;
    }
    if ( (int)v187 >= 0 )
      goto LABEL_442;
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 66);
    WdLogGlobalForLineNumber = 222;
LABEL_447:
    _InterlockedIncrement(&dword_1400866B4);
    WdLogSingleEntry0(6);
    WdLogGlobalForLineNumber = 3754;
    DxgkLogInternalTriageEvent(
      0,
      262145,
      v189,
      (unsigned int)L"Couldn't allocate memory for VIDMM_GLOBAL_ALLOC",
      3754,
      0,
      0,
      0);
    return 3221225495LL;
  }
  v80 = (VIDMM_GLOBAL *)a1;
  if ( !*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 744LL) + 65LL) || (Value & 0x80000) != 0 )
  {
    v199 = v72;
    v94 = operator new[](12, 858810710, 64);
    v95 = v202;
    *(_QWORD *)(*(_QWORD *)v202 + 24LL) = v94;
    v96 = *(volatile signed __int32 **)(*(_QWORD *)v95 + 24LL);
    if ( !v96 )
    {
      _InterlockedIncrement(&dword_1400866AC);
      WdLogSingleEntry0(6);
      WdLogGlobalForLineNumber = 3869;
      DxgkLogInternalTriageEvent(
        v97,
        262145,
        v98,
        (unsigned int)L"Couldn't allocate displaying reference array for allocation",
        3869,
        0,
        0,
        0);
      LogicalMemory = -1073741801;
      goto LABEL_248;
    }
    _InterlockedIncrement(v96);
    v82 = v199;
    v99 = *(_QWORD *)(*(_QWORD *)v95 + 24LL);
    v100 = v199;
    P = v199;
    *(_DWORD *)(v99 + 4) = -((Value & 0x100000) == 0);
    v81 = v100;
LABEL_265:
    v80 = (VIDMM_GLOBAL *)a1;
  }
  else
  {
    if ( (Value & 0x40000000) != 0 || (int)Value < 0 )
    {
      if ( a2 )
      {
        v85 = operator new(176, 858810710, 64);
        v86 = v202;
        *(_QWORD *)(*(_QWORD *)v202 + 32LL) = v85;
        if ( *(_QWORD *)(*(_QWORD *)v86 + 32LL) )
        {
          ByteOffset = 0;
          Height = 1000 * (v209 + 1);
          v199 = (struct VIDMM_GLOBAL_ALLOC *)P;
          while ( 1 )
          {
            memset(v215, 0, 0x50u);
            v89 = ByteOffset;
            v90 = v202;
            v215[0] = 0x8300000005LL;
            v91 = *(_QWORD *)(*(_QWORD *)v202 + 32LL);
            v215[1] = Height * ByteOffset + 100LL;
            v92 = (ByteOffset != 1) + 7;
            *(_QWORD *)(v91 + 8LL * ByteOffset + 16) = v215[1];
            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v90 + 32LL) + 32LL) = v199;
            SyncObject = VidSchCreateSyncObject(
                           *(_QWORD *)(*(_QWORD *)(a1 + 16) + 744LL),
                           0,
                           (int *)v215,
                           v92,
                           0,
                           0,
                           v209,
                           (__int64 *)(*(_QWORD *)(*(_QWORD *)v90 + 32LL) + 8 * v89),
                           0,
                           0,
                           0,
                           a2);
            if ( SyncObject < 0 )
              break;
            if ( (int)++ByteOffset >= 2 )
            {
              v82 = v199;
              v81 = v199;
              goto LABEL_265;
            }
          }
          v79 = (char *)v199;
          LogicalMemory = SyncObject;
          v78 = v199;
        }
        else
        {
          _InterlockedIncrement(&dword_1400866AC);
          WdLogSingleEntry0(6);
          WdLogGlobalForLineNumber = 3809;
          DxgkLogInternalTriageEvent(
            v87,
            262145,
            v88,
            (unsigned int)L"Couldn't allocate flip fence state for allocation",
            3809,
            0,
            0,
            0);
          v78 = P;
          v79 = (char *)P;
          LogicalMemory = -1073741801;
        }
        goto LABEL_427;
      }
      LogicalMemory = 0;
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 3798;
      DxgkLogInternalTriageEvent(v83, 0x40000, v84, (unsigned int)L"pVidMmDevice is not present", 3798, 0, 0, 0);
      goto LABEL_248;
    }
    v81 = v72;
    v199 = v72;
    v82 = v72;
  }
  v101 = v222;
  if ( v222 )
  {
    if ( (*(_DWORD *)(v222 + 4) & 0x8000) != 0 )
    {
      v102 = (_DWORD *)((char *)v82 + 24);
      *((_DWORD *)v82 + 6) |= 0x20u;
    }
    else
    {
      v102 = (_DWORD *)((char *)v81 + 24);
    }
    if ( (*(_DWORD *)(v101 + 4) & 0x10000) != 0 )
    {
      *((_DWORD *)v82 + 7) |= 2u;
      v102 = (_DWORD *)((char *)v82 + 24);
      *((_DWORD *)v82 + 6) |= 0x80000u;
    }
    if ( (*(_DWORD *)(v101 + 4) & 0x8000000) != 0 )
      *v102 |= 0x40u;
  }
  v103 = v214;
  *((_QWORD *)v82 + 44) = v214;
  if ( v103 )
  {
    _InterlockedIncrement((volatile signed __int32 *)v103);
    CrossAdapterDataDpc = VIDMM_GLOBAL::AllocateCrossAdapterDataDpc(v80, v103, v82);
    if ( CrossAdapterDataDpc < 0 )
    {
      LogicalMemory = CrossAdapterDataDpc;
      goto LABEL_425;
    }
    v82 = v199;
  }
  v105 = (*(_DWORD *)(v210 + 72) & 1) != 0 ? 0xF000 : 0;
  v106 = (unsigned int)(v105 + 4095);
  v107 = ~v106 & (v106 + a4);
  v202 = v107;
  if ( a4 > v107 )
  {
    WdLogSingleEntry1(1, a4);
    WdLogGlobalForLineNumber = 3934;
    DxgkLogInternalTriageEvent(
      v108,
      0x40000,
      a4,
      (unsigned int)L"Overflow rounding allocation size (0x%08X) to next page boundary",
      a4,
      0,
      0,
      0);
    LogicalMemory = -1073741811;
LABEL_279:
    v79 = (char *)v199;
LABEL_426:
    v78 = P;
    goto LABEL_427;
  }
  v206 = ~v106 & (v211 + (unsigned int)(v105 + 4095));
  if ( v211 > v206 )
  {
    WdLogSingleEntry1(1, v211);
    v111 = v211;
    v112 = L"Overflow rounding allocation pitch aligned size (0x%08X) to next page boundary";
    WdLogGlobalForLineNumber = 3948;
LABEL_282:
    DxgkLogInternalTriageEvent(v109, 0x40000, v110, (_DWORD)v112, v111, 0, 0, 0);
LABEL_283:
    LogicalMemory = -1073741811;
    goto LABEL_279;
  }
  if ( v107 > 0xFFFF0000 && (*((_DWORD *)v82 + 7) & 2) == 0 )
  {
    WdLogSingleEntry0(1);
    v111 = 3956;
    v112 = L"Can't create an allocation that uses more than 4GB-64kB of system memory";
    WdLogGlobalForLineNumber = 3956;
    goto LABEL_282;
  }
  if ( (*(_BYTE *)(a1 + 37225) & 0x20) != 0 )
  {
    if ( v12 < 0 )
    {
      Height = -1;
      v191 = -1;
    }
    else
    {
      Height = a7;
      v113 = (unsigned int)(4096 << a7);
      v114 = 4096 << a8;
      v205 = v113;
      v191 = a8;
      if ( a8 < a7 )
      {
        WdLogSingleEntry2(3, v114, (unsigned int)v113);
        WdLogGlobalForLineNumber = 3996;
        return 3221225485LL;
      }
      if ( ((v113 - 1) & v107) != 0 )
      {
        WdLogSingleEntry2(3, v107, v205);
        WdLogGlobalForLineNumber = 4011;
        return 3221225485LL;
      }
      if ( v114 > v107 )
      {
        WdLogSingleEntry3(3, v205, v114, v107);
        WdLogGlobalForLineNumber = 4026;
        return 3221225485LL;
      }
      LODWORD(v106) = v105 + 4095;
    }
    ByteOffset = a11;
    if ( (Value & 0x8000) == 0 )
      goto LABEL_304;
  }
  else
  {
    ByteOffset = 0;
    Height = -1;
    v191 = -1;
  }
  if ( (_DWORD)v205 )
  {
    v115 = ~(_DWORD)v106 & (unsigned int)(v106 + v205);
    if ( (unsigned int)v205 > (unsigned int)v115 )
    {
      v117 = (unsigned int)v205;
      WdLogSingleEntry1(1, (unsigned int)v205);
      WdLogGlobalForLineNumber = 4066;
      DxgkLogInternalTriageEvent(
        v118,
        0x40000,
        v119,
        (unsigned int)L"Overflow rounding allocation alignment (0x%08X) to next page boundary",
        v117,
        0,
        0,
        0);
      goto LABEL_283;
    }
  }
  else
  {
    v115 = (unsigned int)(v105 + 4096);
  }
  v205 = v115;
  if ( v107 + v115 < v107 || (unsigned int)v115 + v206 < v206 )
  {
    v180 = v206;
    WdLogSingleEntry4(1, v107, v206, v107, (unsigned int)v115);
    WdLogGlobalForLineNumber = 4084;
    DxgkLogInternalTriageEvent(
      v202,
      0x40000,
      v181,
      (unsigned int)L"Overflow adding alignment to allocation size, Size=%d, PitchAlignedSize=%d, SystemMemorySize=%d, Alignment=%d",
      v202,
      v180,
      v202,
      (unsigned int)v205);
    LogicalMemory = -1073741811;
LABEL_425:
    v79 = (char *)v199;
    goto LABEL_426;
  }
LABEL_304:
  if ( (Value & 0x10000000) != 0 )
    LODWORD(Value) = Value | 8;
  if ( (Value & 0x20000000) == 0 || (Value & 0x10) != 0 )
    v116 = 0;
  else
    v116 = 512;
  v120 = (unsigned __int8)v196 << 27;
  *((_DWORD *)v82 + 7) = v116 | *((_DWORD *)v82 + 7) & 0xFFFFFDFF;
  v121 = (_DWORD *)*((_QWORD *)v82 + 48);
  *((_DWORD *)v82 + 19) = 0;
  *v121 = Value;
  *(_DWORD *)(*((_QWORD *)v82 + 48) + 4LL) = v55;
  LODWORD(v121) = *((_DWORD *)v82 + 6) & 0xFFFFFFFD;
  *((_DWORD *)v82 + 18) = 0;
  *((_DWORD *)v82 + 32) = 0;
  v122 = v222;
  LODWORD(v121) = ((unsigned int)v121 | (2 * (v49 & 1))) ^ (((unsigned int)v121 | (2 * (v49 & 1))) ^ (v49 >> 1)) & 1;
  *((_QWORD *)v82 + 1) = v222;
  v123 = (unsigned int)v121 ^ ((unsigned int)v121 ^ v120) & 0x8000000;
  v124 = (16 * (unsigned __int8)v219)
       | v193.Value & 0xFFFFFFEF
       | Format & 0xFFFFFFAF
       | *((_DWORD *)v82 + 7) & 0xFFFFFFA7;
  *((_DWORD *)v82 + 6) = v123;
  v125 = ((32 * (unsigned __int8)Width) | v124 & 0xFFFFFFDF)
       ^ ((unsigned __int16)((32 * (unsigned __int8)Width) | v124 & 0xFFDF)
        ^ (unsigned __int16)((_WORD)v55 << 12))
       & 0x1000;
  *((_DWORD *)v82 + 7) = v125;
  if ( v122 && (*(_DWORD *)(v122 + 4) & 0x10000000) != 0 )
    v126 = 0x2000;
  else
    v126 = 0;
  v127 = v126 | v125 & 0xFFFFDFFF;
  v128 = v123 & 0xFFFFFFFB | (v229 != 0 ? 4 : 0);
  v129 = v228;
  v130 = (_DWORD *)*((_QWORD *)v82 + 48);
  v131 = (v228 != 0 ? 0x800000 : 0) | v128 & 0xFF7FFFFF;
  v132 = v127 ^ ((unsigned __int16)v127 ^ (unsigned __int16)((_WORD)v55 << 9)) & 0x8000;
  *((_DWORD *)v82 + 6) = v131;
  *((_DWORD *)v82 + 7) = v132;
  v133 = v132 & 0xFFFEFFFF | ((*v130 & 0xC0000100) != 0 ? 0x10000 : 0);
  v134 = v229;
  *((_DWORD *)v82 + 7) = v133;
  if ( v134 )
  {
    *((_QWORD *)v82 + 8) = v134;
  }
  else if ( v129 )
  {
    *((_QWORD *)v82 + 8) = v129;
  }
  else
  {
    v135 = v231;
    if ( v231 )
    {
      *((_QWORD *)v82 + 8) = v231;
      *((_DWORD *)v82 + 7) = v133 | 0x4000;
      *((_DWORD *)v82 + 6) = v131 & 0xFFFFFF7F | ~((unsigned __int8)*(_DWORD *)(v135 + 152) << 6) & 0x80;
    }
  }
  v136 = VidMmiSelectAllocationHeap(v207, v82, *(unsigned int *)(a1 + 41448));
  *(_QWORD *)(v137 + 232) = v136;
  if ( v136 && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v136 + 120LL))(v136) )
    v138 = v192;
  else
    v138 = 1;
  v139 = v199;
  v140 = 0;
  LOBYTE(v219) = 0;
  v141 = (v138 << 7) | *((_DWORD *)v199 + 7) & 0xFFFFFF7F;
  *((_DWORD *)v199 + 7) = v141;
  if ( (Value & 1) != 0 && (v141 & 0x80u) == 0 && (*(_DWORD *)(v210 + 72) & 1) == 0 )
  {
    v140 = ((*(_DWORD *)(*(_QWORD *)(a1 + 24) + 444LL) & 8) != 0 || VidMmCheckForCpuVisibleMemorySegment(v201, a9))
        && !v134
        && (*((_DWORD *)v139 + 6) & 2) == 0;
    LOBYTE(v219) = v140;
  }
  v142 = v201;
  v143 = v206;
  v144 = v202;
  *((_DWORD *)v139 + 7) = (v140 << 10) | *((_DWORD *)v139 + 7) & 0xFFFFFBFF;
  v190 = v209;
  LogicalMemory = (*(__int64 (__fastcall **)(struct VIDMM_PHYSICAL_ADAPTER *, struct VIDMM_GLOBAL_ALLOC *, unsigned __int64, unsigned __int64, unsigned __int64, int, int, _DWORD, unsigned int))(*(_QWORD *)v142 + 32LL))(
                    v142,
                    v139,
                    a4,
                    v144,
                    v143,
                    Height,
                    v191,
                    v205,
                    a9);
  if ( LogicalMemory < 0 )
    goto LABEL_425;
  v145 = v199;
  *(_QWORD *)v199 = v208;
  if ( (*(_DWORD *)(v210 + 72) & 1) != 0 )
  {
    *((_DWORD *)v145 + 6) |= 0x10000000u;
  }
  else
  {
    if ( (dword_1400865E4
       || (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 36480) + 8LL * (unsigned int)v209) + 44LL) & 1) != 0)
      && (**(_DWORD **)(*(_QWORD *)(a1 + 24) + 3120LL) & 0x4000) == 0
      && (v49 & 2) != 0
      && v212
      && ((*v212 & 0x200) != 0 || dword_1400865E4 == 2)
      && ((v146 = *(_QWORD *)(v208 + 16), !(_WORD)v146) || v146 > (unsigned int)dword_1400865E8)
      && !(_BYTE)v219 )
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
          && ((*((_BYTE *)v201 + 1086) & 8) != 0
           || (v150 = (_DWORD *)*((_QWORD *)v201 + 136)) != 0 && (*v150 & 0x80u) != 0) )
        {
          *((_DWORD *)v145 + 6) |= 0x20000000u;
        }
      }
    }
  }
  if ( (*((_DWORD *)v145 + 7) & 0x8000) != 0
    && (*((_DWORD *)v145 + 6) & 0x20000000) == 0
    && (*((_DWORD *)DXGGLOBAL::GetGlobal() + 64) & 0x20) != 0 )
  {
    if ( (*((_DWORD *)v145 + 6) & 0x10000000) != 0 )
    {
      v152 = 1;
      if ( (*((_BYTE *)v201 + 1086) & 8) == 0 )
      {
        v151 = (_DWORD *)*((_QWORD *)v201 + 136);
        if ( !v151 || (*v151 & 0x80u) == 0 )
          v152 = 0;
      }
      v153 = *((_DWORD *)v145 + 6);
      v154 = (v153 & 0x8000000) == 0
          || (*((_DWORD *)v145 + 7) & 0x4200) != 0
          || (v153 & 0x800004) != 0
          || (Value & 8) != 0
          || (Value & 0x20000) != 0
          || (Value & 0x8000000) != 0
          || (Value & 0x4000) != 0;
      WdLogSingleEntry3(4, v154, g_Feature_Largify64KBPrototype, v152);
      WdLogGlobalForLineNumber = 4290;
    }
    else
    {
      WdLogSingleEntry5(
        4,
        (unsigned int)dword_1400865E4,
        *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 36480) + 8LL * (unsigned int)v209) + 44LL) & 1);
      WdLogGlobalForLineNumber = 4269;
      WdLogSingleEntry1(4, (unsigned __int8)v219 ^ 1LL);
      WdLogGlobalForLineNumber = 4271;
    }
    __debugbreak();
  }
  if ( v222 )
    v155 = *(_QWORD *)(v222 + 16);
  else
    v155 = v225;
  v79 = (char *)v199;
  *(_QWORD *)(*((_QWORD *)v199 + 48) + 48LL) = v155;
  if ( v223 )
  {
    v156 = v223;
  }
  else
  {
    v156 = 0;
    if ( v224 )
      v156 = v224;
  }
  LogicalMemory = VIDMM_GLOBAL::CommitGlobalBackingStore(
                    (VIDMM_GLOBAL *)a1,
                    (struct VIDMM_GLOBAL_ALLOC *)v79,
                    v207,
                    v156,
                    v233);
  if ( LogicalMemory < 0 )
    goto LABEL_426;
  if ( (Value & 0x4000) != 0 )
    *((_DWORD *)v79 + 6) |= 0x2000000u;
  *((_DWORD *)v79 + 6) ^= (*((_DWORD *)v79 + 6) ^ ((unsigned __int8)v227 << 24)) & 0x1000000;
  *(_DWORD *)(v208 + 56) = v226;
  v157 = v201;
  *((_QWORD *)v79 + 15) = v79 + 112;
  *((_QWORD *)v79 + 14) = v79 + 112;
  LOBYTE(v219) = (*((_DWORD *)v79 + 6) & 2) != 0;
  MostPreferredSegment = (const struct VIDMM_SEGMENT_BASE *)VidMmGetMostPreferredSegment(v157, v32, (__int64 *)va);
  *((_DWORD *)v79 + 6) = v159 ^ (v159 ^ (16 * (unsigned __int8)v219)) & 0x10;
  if ( !VidMmVerifyBudgetGroups(v201, a9, MostPreferredSegment, (struct _VIDMM_VERIFY_BUDGET_GROUPS *)&Pitch) )
  {
    LogicalMemory = -1073741811;
    goto LABEL_426;
  }
  *((_DWORD *)v79 + 6) = ((unsigned __int8)Pitch << 8) | *((_DWORD *)v79 + 6) & 0xFFFF00FF;
  if ( (Value & 0x10) != 0 || (Value & 0x20) != 0 )
    v79[42] = 1;
  v160 = v202;
  if ( !v229 )
  {
    LogicalMemory = SysMmAllocateLogicalMemory(
                      *(struct SYSMM_ADAPTER **)(*(_QWORD *)(a1 + 24) + 224LL),
                      v202,
                      v79,
                      (void **)v79 + 45);
    if ( LogicalMemory < 0 )
    {
      WdLogSingleEntry1(1, v79);
      WdLogGlobalForLineNumber = 4384;
      DxgkLogInternalTriageEvent(
        v161,
        0x40000,
        v162,
        (unsigned int)L"Failed to allocate logical address range for global alloc 0x%.16I64x",
        (__int64)v79,
        0,
        0,
        0);
      goto LABEL_426;
    }
  }
  v163 = VIDMM_GLOBAL::AdapterId((VIDMM_GLOBAL *)a1);
  v164 = v210;
  *((_QWORD *)v79 + 43) = *(_QWORD *)(v210 + 40) + 384LL * v163;
  _InterlockedAdd((volatile signed __int32 *)(v164 + 36), 1u);
  if ( *(_DWORD *)(v164 + 32)
    || (v165 = **((_DWORD **)v79 + 48), (v165 & 0x2003A) != 0)
    || (v166 = *((_DWORD *)v79 + 7), (v166 & 0x10) != 0)
    || (*((_DWORD *)v79 + 6) & 4) != 0
    || (v166 & 2) != 0
    || (v165 & 0x40000000) != 0 )
  {
    LODWORD(v213) = 0;
  }
  *((_DWORD *)v79 + 7) = v213 | *((_DWORD *)v79 + 7) & 0xFFFFFEFF;
  AllocationHint = VidMmGetAllocationHint((const struct VIDMM_GLOBAL_ALLOC *)v79);
  if ( (byte_140086201 & 0x10) != 0 )
  {
    v213 = v208;
    LODWORD(v231) = AllocationHint->v1.Depth;
    Pitch = AllocationHint->v1.Pitch;
    Height = AllocationHint->v1.Height;
    Width = AllocationHint->v1.Width;
    ByteOffset = AllocationHint->v1.ByteOffset;
    v193.0 = (struct _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0::$5068715F5D8591D41DA1228877FDA04B::$63766B29C143116E9EC685C38896947D)AllocationHint->v1.SwizzledFormat;
    Format = AllocationHint->v1.Format;
    v172 = AllocationHint->v1.Flags.Value;
    v212 = (_DWORD *)*((_QWORD *)v79 + 1);
    v211 = *(_QWORD *)(a1 + 24);
    LODWORD(v219) = v170 != 0;
    v196 = v172;
    if ( a2 )
      v173 = *((_QWORD *)a2 + 3);
    else
      LOBYTE(v173) = 0;
    CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
    McTemplateK0pppqxqqqqqqqpppqqqqqqqqqqtphtp_EtwWriteTransfer(
      v211,
      (unsigned int)EventCreateAdapterAllocation,
      v175,
      CurrentProcessId,
      v173,
      v211,
      v12,
      v160,
      v205,
      a10,
      a9,
      v32,
      v190,
      a10,
      v226,
      (char)v79,
      (char)v212);
    v171 = 1;
  }
  _InterlockedAdd((volatile signed __int32 *)(a1 + 3760), v171);
  _InterlockedAdd64((volatile signed __int64 *)(a1 + 3768), v160);
  _InterlockedAdd64((volatile signed __int64 *)(a1 + 36448), v160);
  if ( a2 )
  {
    v176 = *((_QWORD *)a2 + 2);
    if ( v176 )
    {
      BucketIdForAllocationSizePow2 = (unsigned int)GetBucketIdForAllocationSizePow2(
                                                      v160,
                                                      BucketIdForAllocationSizePow2,
                                                      *(_QWORD *)(v176 + 184));
      _InterlockedAdd64((volatile signed __int64 *)(v177 + 8 * BucketIdForAllocationSizePow2 + 56), v160);
      _InterlockedAdd((volatile signed __int32 *)(v177 + 4 * BucketIdForAllocationSizePow2 + 232), v178);
      *(_BYTE *)(v177 + 320) = v178;
    }
  }
  if ( g_IsInternalReleaseOrDbg )
  {
    *(_QWORD *)(WdLogNewEntry5_WdTrace(v169, BucketIdForAllocationSizePow2) + 24) = v79;
    WdLogGlobalForLineNumber = 4477;
  }
  *v232 = v79;
  return 0;
}

```

## disassembly

```asm
0x140105808  mov     rax, rsp
0x14010580b  mov     [rax+18h], rbx
0x14010580f  mov     [rax+20h], r9
0x140105813  mov     [rax+10h], rdx
0x140105817  mov     [rax+8], rcx
0x14010581b  push    rbp
0x14010581c  push    rsi
0x14010581d  push    rdi
0x14010581e  push    r12
0x140105820  push    r13
0x140105822  push    r14
0x140105824  push    r15
0x140105826  lea     rbp, [rsp-70h]
0x14010582b  sub     rsp, 200h
0x140105832  mov     r13d, dword ptr [rbp+0A0h+arg_60]
0x140105839  mov     rsi, r9
0x14010583c  mov     ebx, r13d
0x14010583f  mov     edi, r8d
0x140105842  mov     dword ptr [rbp+0A0h+var_118], ebx
0x140105845  mov     r15, rdx
0x140105848  mov     r14, rcx
0x14010584b  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x140105850  mov     rdx, [rbp+0A0h+arg_B8]
0x140105857  xor     r10d, r10d
0x14010585a  mov     [rbp+0A0h+var_C8], rax
0x14010585e  mov     rcx, rax
0x140105861  mov     r8d, 1
0x140105867  test    rdx, rdx
0x14010586a  jz      short loc_14010587E
0x14010586c  mov     edx, [rdx+98h]
0x140105872  mov     byte ptr [rbp+0A0h+arg_60], r8b
0x140105879  test    r8b, dl
0x14010587c  jz      short loc_140105885
0x14010587e  mov     byte ptr [rbp+0A0h+arg_60], r10b
0x140105885  test    r15, r15
0x140105888  jz      short loc_140105890
0x14010588a  mov     r9, [r15+8]
0x14010588e  jmp     short loc_1401058AB
0x140105890  test    rcx, rcx
0x140105893  jz      loc_1401079A7
0x140105899  mov     rax, [rax+40h]
0x14010589d  test    rax, rax
0x1401058a0  jz      short loc_1401058A8
0x1401058a2  mov     r9, [rax+8]
0x1401058a6  jmp     short loc_1401058AB
0x1401058a8  mov     r9, r10
0x1401058ab  mov     eax, dword ptr [rbp+0A0h+arg_90]
0x1401058b1  mov     r11d, 2
0x1401058b7  cmp     eax, r11d
0x1401058ba  mov     [rbp+0A0h+var_C0], r9
0x1401058be  cmovbe  eax, r11d
0x1401058c2  mov     dword ptr [rbp+0A0h+arg_90], eax
0x1401058c8  test    rcx, rcx
0x1401058cb  jz      short loc_140105900
0x1401058cd  mov     ecx, [rcx+198h]
0x1401058d3  mov     eax, ecx
0x1401058d5  shr     eax, 8
0x1401058d8  test    r8b, al
0x1401058db  jz      short loc_140105900
0x1401058dd  shr     ecx, 0Ah
0x1401058e0  mov     [rbp+0A0h+var_114], r8b
0x1401058e4  test    r8b, cl
0x1401058e7  jnz     short loc_140105904
0x1401058e9  cmp     [rbp+0A0h+arg_A0], r10
0x1401058f0  jnz     short loc_140105904
0x1401058f2  test    r8b, r13b
0x1401058f5  jz      short loc_140105904
0x1401058f7  btr     ebx, 0Fh
0x1401058fb  mov     dword ptr [rbp+0A0h+var_118], ebx
0x1401058fe  jmp     short loc_140105904
0x140105900  mov     [rbp+0A0h+var_114], r10b
0x140105904  mov     rax, [r9+150h]
0x14010590b  mov     ecx, r10d
0x14010590e  cmp     [r14+0C28h], r8d
0x140105915  lea     r8, [rbp+0A0h+var_E0]; struct VIDMM_SEGMENT_PREFERENCES *
0x140105919  mov     edx, dword ptr [rbp+0A0h+arg_58]; struct _D3DDDI_SEGMENTPREFERENCE
0x14010591f  cmovnz  ecx, edi
0x140105922  mov     [rbp+0A0h+var_A8], rax
0x140105926  mov     rax, [r14+8E80h]
0x14010592d  mov     [rbp+0A0h+var_B0], rcx
0x140105931  mov     [rbp+0A0h+var_E0], r10
0x140105935  mov     rax, [rax+rcx*8]
0x140105939  mov     [rbp+0A0h+var_E8], rax
0x14010593d  mov     rcx, [rax+440h]
0x140105944  mov     [rbp+0A0h+var_98], rcx
0x140105948  mov     rcx, r14; struct VIDMM_GLOBAL *
0x14010594b  call    ?VidMmConvertSegmentPreferences@@YAXPEBVVIDMM_GLOBAL@@U_D3DDDI_SEGMENTPREFERENCE@@PEAUVIDMM_SEGMENT_PREFERENCES@@@Z; VidMmConvertSegmentPreferences(VIDMM_GLOBAL const *,_D3DDDI_SEGMENTPREFERENCE,VIDMM_SEGMENT_PREFERENCES *)
0x140105950  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x140105957  mov     edi, [rbp+0A0h+arg_28]
0x14010595d  mov     r12, [rbp+0A0h+var_E0]
0x140105961  mov     [rbp+0A0h+var_D0], rdi
0x140105965  cmp     [rax], r10b
0x140105968  jz      loc_140105A1A
0x14010596e  call    cs:__imp_WdLogNewEntry5_WdTrace
0x140105975  nop     dword ptr [rax+rax+00h]
0x14010597a  xor     r10d, r10d
0x14010597d  mov     [rax+18h], r15
0x140105981  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x140105988  mov     cs:WdLogGlobalForLineNumber, 0B75h
0x140105992  cmp     [rax], r10b
0x140105995  jz      short loc_140105A10
0x140105997  call    cs:__imp_WdLogNewEntry5_WdTrace
0x14010599e  nop     dword ptr [rax+rax+00h]
0x1401059a3  mov     ecx, [rbp+0A0h+arg_40]
0x1401059a9  xor     r10d, r10d
0x1401059ac  mov     [rax+18h], rsi
0x1401059b0  mov     [rax+20h], rdi
0x1401059b4  mov     [rax+28h], rcx
0x1401059b8  mov     ecx, [rbp+0A0h+arg_48]
0x1401059be  mov     [rax+30h], rcx
0x1401059c2  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1401059c9  mov     cs:WdLogGlobalForLineNumber, 0B7Ah
0x1401059d3  cmp     [rax], r10b
0x1401059d6  jz      short loc_140105A10
0x1401059d8  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1401059df  nop     dword ptr [rax+rax+00h]
0x1401059e4  mov     ecx, r12d
0x1401059e7  xor     r10d, r10d
0x1401059ea  mov     [rax+18h], rcx
0x1401059ee  mov     ecx, dword ptr [rbp+0A0h+var_E0+4]
0x1401059f1  mov     [rax+20h], rcx
0x1401059f5  mov     ecx, ebx
0x1401059f7  mov     [rax+28h], rcx
0x1401059fb  mov     rcx, [rbp+0A0h+arg_70]
0x140105a02  mov     [rax+30h], rcx
0x140105a06  mov     cs:WdLogGlobalForLineNumber, 0B7Fh
0x140105a10  mov     r9, [rbp+0A0h+var_C0]
0x140105a14  mov     r11d, 2
0x140105a1a  mov     rax, [rbp+0A0h+arg_C0]
0x140105a21  mov     edi, 40000h
0x140105a26  mov     [rax], r10
0x140105a29  cmp     dword ptr [r14+28h], 5023h
0x140105a31  jnb     short loc_140105A5B
0x140105a33  test    edi, ebx
0x140105a35  jz      short loc_140105A5B
0x140105a37  mov     ecx, 1
0x140105a3c  call    cs:__imp_WdLogSingleEntry0
0x140105a43  nop     dword ptr [rax+rax+00h]
0x140105a48  mov     eax, 0B8Fh
0x140105a4d  lea     r9, aCpuvisibleonde_1; "CpuVisibleOnDemand flag set, but on thi"...
0x140105a54  mov     edx, edi
0x140105a56  jmp     loc_1401079C7
0x140105a5b  mov     esi, 10h
0x140105a60  lea     r15d, [rsi+10h]
0x140105a64  bt      ebx, 11h
0x140105a68  jnb     short loc_140105AC3
0x140105a6a  test    r11b, bl
0x140105a6d  jnz     loc_140105BAD
0x140105a73  test    bl, 4
0x140105a76  jz      short loc_140105A8B
0x140105a78  mov     rax, [r14+18h]
0x140105a7c  mov     ecx, [rax+1BCh]
0x140105a82  test    cl, 8
0x140105a85  jz      loc_140105BAD
0x140105a8b  bt      ebx, 14h
0x140105a8f  jb      loc_140105BAD
0x140105a95  bt      ebx, 13h
0x140105a99  jb      loc_140105BAD
0x140105a9f  test    bl, 8
0x140105aa2  jnz     loc_140105BAD
0x140105aa8  test    sil, bl
0x140105aab  jnz     loc_140105BAD
0x140105ab1  test    r15b, bl
0x140105ab4  jnz     loc_140105BAD
0x140105aba  and     ebx, 0FFFBFFFEh
0x140105ac0  mov     dword ptr [rbp+0A0h+var_118], ebx
0x140105ac3  mov     eax, 1
0x140105ac8  test    al, bl
0x140105aca  jz      short loc_140105AD0
0x140105acc  test    edi, ebx
0x140105ace  jz      short loc_140105AD9
0x140105ad0  mov     byte ptr [rbp+0A0h+var_108], r10b
0x140105ad4  test    sil, bl
0x140105ad7  jz      short loc_140105ADC
0x140105ad9  mov     byte ptr [rbp+0A0h+var_108], al
0x140105adc  mov     r14b, byte ptr [rbp+0A0h+arg_60]
0x140105ae3  test    r14b, r14b
0x140105ae6  jnz     short loc_140105AF3
0x140105ae8  test    bl, 8
0x140105aeb  jnz     short loc_140105AF3
0x140105aed  bt      ebx, 11h
0x140105af1  jnb     short loc_140105AF7
0x140105af3  mov     byte ptr [rbp+0A0h+var_108], r10b
0x140105af7  mov     eax, [r9+98h]
0x140105afe  test    al, 40h
0x140105b00  jnz     short loc_140105B6E
0x140105b02  call    cs:__imp_PsGetCurrentProcess
0x140105b09  nop     dword ptr [rax+rax+00h]
0x140105b0e  mov     rcx, rax
0x140105b11  call    cs:__imp_PsGetProcessWow64Process
0x140105b18  nop     dword ptr [rax+rax+00h]
0x140105b1d  xor     r10d, r10d
0x140105b20  test    rax, rax
0x140105b23  jnz     short loc_140105B6E
0x140105b25  bt      ebx, 1Dh
0x140105b29  jb      short loc_140105B6E
0x140105b2b  bt      ebx, 1Eh
0x140105b2f  jb      short loc_140105B6E
0x140105b31  test    ebx, ebx
0x140105b33  js      short loc_140105B6E
0x140105b35  bt      ebx, 1Ch
0x140105b39  jb      short loc_140105B6E
0x140105b3b  test    bl, 8
0x140105b3e  jnz     short loc_140105B6E
0x140105b40  bt      ebx, 16h
0x140105b44  jb      short loc_140105B6E
0x140105b46  bt      ebx, 11h
0x140105b4a  jb      short loc_140105B6E
0x140105b4c  test    r14b, r14b
0x140105b4f  jnz     short loc_140105B6E
0x140105b51  cmp     [rbp+0A0h+arg_A0], r10
0x140105b58  jnz     short loc_140105B6E
0x140105b5a  cmp     [rbp+0A0h+arg_A8], r10
0x140105b61  jnz     short loc_140105B6E
0x140105b63  btr     ebx, 12h
0x140105b67  mov     byte ptr [rbp+0A0h+var_108], 1
0x140105b6b  mov     dword ptr [rbp+0A0h+var_118], ebx
0x140105b6e  mov     r14d, ebx
0x140105b71  shr     r14d, 0Dh
0x140105b75  and     r14d, 1
0x140105b79  jz      short loc_140105BCF
0x140105b7b  mov     rax, [rbp+0A0h+arg_0]
0x140105b82  test    byte ptr [rax+9169h], 8
0x140105b89  jnz     short loc_140105BCF
0x140105b8b  mov     ecx, 1
0x140105b90  call    cs:__imp_WdLogSingleEntry0
0x140105b97  nop     dword ptr [rax+rax+00h]
0x140105b9c  mov     eax, 0BFCh
0x140105ba1  lea     r9, aDriversMustSup; "Drivers must support MapAperture2 to se"...
0x140105ba8  jmp     loc_140105A54
0x140105bad  mov     ecx, 1
0x140105bb2  call    cs:__imp_WdLogSingleEntry0
0x140105bb9  nop     dword ptr [rax+rax+00h]
0x140105bbe  mov     eax, 0BA5h
0x140105bc3  lea     r9, aHardwareprotec_2; "HardwareProtected allocations cannot be"...
0x140105bca  jmp     loc_140105A54
0x140105bcf  mov     r8d, [rbp+0A0h+arg_40]
0x140105bd6  mov     rdx, r12
0x140105bd9  mov     rcx, [rbp+0A0h+var_E8]
0x140105bdd  call    ?VidMmValidatePreferredSegment@@YA_NPEBUVIDMM_PHYSICAL_ADAPTER@@UVIDMM_SEGMENT_PREFERENCES@@I@Z; VidMmValidatePreferredSegment(VIDMM_PHYSICAL_ADAPTER const *,VIDMM_SEGMENT_PREFERENCES,uint)
0x140105be2  test    al, al
0x140105be4  jnz     short loc_140105C08
0x140105be6  mov     ecx, 1
0x140105beb  call    cs:__imp_WdLogSingleEntry0
0x140105bf2  nop     dword ptr [rax+rax+00h]
0x140105bf7  mov     eax, 0C06h
0x140105bfc  lea     r9, aSpecifiedPrefe; "Specified preferred segment is invalid."...
0x140105c03  jmp     loc_140105A54
0x140105c08  cmp     cs:dword_1400865E0, 0
0x140105c0f  mov     r8d, 1
0x140105c15  jz      short loc_140105C52
0x140105c17  test    r8b, bl
0x140105c1a  jnz     short loc_140105C52
0x140105c1c  mov     r10, [rbp+0A0h+var_E8]
0x140105c20  mov     ecx, r12d
0x140105c23  and     ecx, 1Fh
0x140105c26  jnz     short loc_140105C43
0x140105c28  mov     eax, [rbp+0A0h+arg_40]
0x140105c2e  and     eax, [r10+54h]
0x140105c32  cmovz   eax, [rbp+0A0h+arg_40]
0x140105c39  mov     edx, eax
0x140105c3b  mov     [rbp+0A0h+arg_40], eax
0x140105c41  jmp     short loc_140105C5C
0x140105c43  dec     ecx
0x140105c45  mov     edx, r8d
0x140105c48  shl     edx, cl
0x140105c4a  mov     [rbp+0A0h+arg_40], edx
0x140105c50  jmp     short loc_140105C5C
0x140105c52  mov     edx, [rbp+0A0h+arg_40]; unsigned int
0x140105c58  mov     r10, [rbp+0A0h+var_E8]
0x140105c5c  mov     rcx, [rbp+0A0h+arg_18]
0x140105c63  test    rcx, rcx
0x140105c66  jnz     short loc_140105C88
0x140105c68  mov     ecx, r8d
0x140105c6b  call    cs:__imp_WdLogSingleEntry0
0x140105c72  nop     dword ptr [rax+rax+00h]
0x140105c77  mov     eax, 0C2Fh
0x140105c7c  lea     r9, aCanTCreateAnAl_0; "Can't create an allocation of zero size"
0x140105c83  jmp     loc_140105A54
0x140105c88  test    r14d, r14d
0x140105c8b  jz      short loc_140105CCF
0x140105c8d  mov     rax, [rbp+0A0h+arg_0]
0x140105c94  mov     rax, [rax+10h]
0x140105c98  mov     rcx, [rax+10h]
0x140105c9c  cmp     dword ptr [rcx+0C2Ch], 0B54h
0x140105ca6  jge     short loc_140105CC8
0x140105ca8  mov     ecx, r8d
0x140105cab  call    cs:__imp_WdLogSingleEntry0
0x140105cb2  nop     dword ptr [rax+rax+00h]
0x140105cb7  mov     eax, 0C39h
0x140105cbc  lea     r9, aLinkinstancedM; "LinkInstanced/MapApertureCpuVisible fla"...
0x140105cc3  jmp     loc_140105A54
0x140105cc8  mov     rcx, [rbp+0A0h+arg_18]
0x140105ccf  bt      ebx, 0Ch
0x140105cd3  jnb     short loc_140105CF5
0x140105cd5  mov     ecx, r8d
0x140105cd8  call    cs:__imp_WdLogSingleEntry0
0x140105cdf  nop     dword ptr [rax+rax+00h]
0x140105ce4  mov     eax, 0C40h
0x140105ce9  lea     r9, aPhysicallycont; "PhysicallyContiguous flag is not not cu"...
  ... truncated ...
```
