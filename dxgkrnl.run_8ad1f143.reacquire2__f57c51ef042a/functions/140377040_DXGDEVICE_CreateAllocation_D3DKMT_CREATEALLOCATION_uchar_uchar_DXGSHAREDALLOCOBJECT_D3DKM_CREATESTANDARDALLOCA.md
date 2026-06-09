# DXGDEVICE::CreateAllocation(_D3DKMT_CREATEALLOCATION *,uchar,uchar,_DXGSHAREDALLOCOBJECT *,_D3DKM_CREATESTANDARDALLOCATION const *,COREDEVICEACCESS *,uint,_EPROCESS *,uint *,unsigned __int64 *,unsigned __int64 *,_D3DKMT_CREATESTANDARDALLOCATION *,void *,uint)

- ea: `0x140377040`
- end: `0x14037aa1f`
- name: `?CreateAllocation@DXGDEVICE@@QEAAJPEAU_D3DKMT_CREATEALLOCATION@@EEPEAU_DXGSHAREDALLOCOBJECT@@PEBU_D3DKM_CREATESTANDARDALLOCATION@@PEAVCOREDEVICEACCESS@@IPEAU_EPROCESS@@PEAIPEA_K6PEAU_D3DKMT_CREATESTANDARDALLOCATION@@PEAXI@Z`
- size: `14815`
- prototype: `__int64 __usercall@<rax>(DXGDEVICE *__hidden this@<rcx>, struct _D3DKMT_CREATEALLOCATION *@<rdx>, unsigned __int8@<r8b>, unsigned __int8@<r9b>, struct _DXGSHAREDALLOCOBJECT *, const struct _D3DKM_CREATESTANDARDALLOCATION *, struct COREDEVICEACCESS *, unsigned int, struct _EPROCESS *, unsigned int *, unsigned __int64 *, unsigned __int64 *, struct _D3DKMT_CREATESTANDARDALLOCATION *, void *, unsigned int)`
- caller_count: `4`
- callee_count: `64`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14031a21c`
- `0x1403760ec`
- `0x1403c36ac`
- `0x1403d9f70`

## callees

- `0x140009030`
- `0x14000d7d0`
- `0x140012380`
- `0x1400144ec`
- `0x1400150d0`
- `0x140015458`
- `0x14001a2ec`
- `0x14001a38c`
- `0x14001a71c`
- `0x14001a7d4`
- `0x14001a8d0`
- `0x14001ab20`
- `0x14001b890`
- `0x14001bc50`
- `0x14001bd70`
- `0x14002d9f0`
- `0x140033d38`
- `0x140033e60`
- `0x14003bab8`
- `0x14003bd5c`
- `0x14003c8c0`
- `0x14003d0dc`
- `0x14003f760`
- `0x14004e904`
- `0x140057418`
- `0x140058878`
- `0x1400592cc`
- `0x1400670a4`
- `0x14006dc88`
- `0x1400a0100`
- `0x1400a01e0`
- `0x1400a0240`
- `0x1400a0540`
- `0x14018d504`
- `0x140196f20`
- `0x1401dd804`
- `0x1401e5360`
- `0x1401e54cc`
- `0x14020da68`
- `0x14020db94`
- `0x14021b198`
- `0x140243530`
- `0x140290750`
- `0x14031e60c`
- `0x140323854`
- `0x140327c10`
- `0x140329000`
- `0x140340858`
- `0x140340d50`
- `0x14034599c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140377b34`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403786df`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14037a8ff`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140377b34`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403786df`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14037a8ff`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140377b28`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403786d3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14037a8f3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140377b28`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403786d3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14037a8f3`
- `ntoskrnl!ObfDereferenceObject` at `0x14037932c`
- `ntoskrnl!ObfDereferenceObject` at `0x14037932c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140379df3`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14037a667`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140379df3`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14037a667`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140377659`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140377659`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1403771a6`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1403771a6`
- `ntoskrnl!MmSectionObjectType` at `0x140379de4`
- `ntoskrnl!MmSectionObjectType` at `0x14037a657`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140379c12`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14037a3d5`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140379c12`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14037a3d5`
- `watchdog!WdLogSingleEntry4` at `0x140379010`
- `watchdog!WdLogSingleEntry4` at `0x1403796cb`
- `watchdog!WdLogSingleEntry4` at `0x14037a4f4`
- `watchdog!WdLogSingleEntry4` at `0x140379010`
- `watchdog!WdLogSingleEntry4` at `0x1403796cb`
- `watchdog!WdLogSingleEntry4` at `0x14037a4f4`
- `watchdog!WdLogSingleEntry2` at `0x140377e4b`
- `watchdog!WdLogSingleEntry2` at `0x140377f88`
- `watchdog!WdLogSingleEntry2` at `0x14037810e`
- `watchdog!WdLogSingleEntry2` at `0x140378866`
- `watchdog!WdLogSingleEntry2` at `0x140378c11`
- `watchdog!WdLogSingleEntry2` at `0x140378cfb`
- `watchdog!WdLogSingleEntry2` at `0x140378e96`
- `watchdog!WdLogSingleEntry2` at `0x140378f40`
- `watchdog!WdLogSingleEntry2` at `0x14037906a`
- `watchdog!WdLogSingleEntry2` at `0x14037929f`
- `watchdog!WdLogSingleEntry2` at `0x1403792dc`
- `watchdog!WdLogSingleEntry2` at `0x140379480`
- `watchdog!WdLogSingleEntry2` at `0x140379e29`
- `watchdog!WdLogSingleEntry2` at `0x140379e55`
- `watchdog!WdLogSingleEntry2` at `0x14037a1f6`
- `watchdog!WdLogSingleEntry2` at `0x140377e4b`
- `watchdog!WdLogSingleEntry2` at `0x140377f88`
- `watchdog!WdLogSingleEntry2` at `0x14037810e`
- `watchdog!WdLogSingleEntry2` at `0x140378866`
- `watchdog!WdLogSingleEntry2` at `0x140378c11`
- `watchdog!WdLogSingleEntry2` at `0x140378cfb`
- `watchdog!WdLogSingleEntry2` at `0x140378e96`
- `watchdog!WdLogSingleEntry2` at `0x140378f40`
- `watchdog!WdLogSingleEntry2` at `0x14037906a`
- `watchdog!WdLogSingleEntry2` at `0x14037929f`
- `watchdog!WdLogSingleEntry2` at `0x1403792dc`
- `watchdog!WdLogSingleEntry2` at `0x140379480`
- `watchdog!WdLogSingleEntry2` at `0x140379e29`
- `watchdog!WdLogSingleEntry2` at `0x140379e55`
- `watchdog!WdLogSingleEntry2` at `0x14037a1f6`
- `watchdog!WdLogSingleEntry3` at `0x140378032`
- `watchdog!WdLogSingleEntry3` at `0x140378893`
- `watchdog!WdLogSingleEntry3` at `0x140378b2f`
- `watchdog!WdLogSingleEntry3` at `0x140378b59`
- `watchdog!WdLogSingleEntry3` at `0x140378d64`
- `watchdog!WdLogSingleEntry3` at `0x14037903d`
- `watchdog!WdLogSingleEntry3` at `0x1403790d5`
- `watchdog!WdLogSingleEntry3` at `0x14037910e`
- `watchdog!WdLogSingleEntry3` at `0x1403793ef`
- `watchdog!WdLogSingleEntry3` at `0x140379432`
- `watchdog!WdLogSingleEntry3` at `0x14037959b`
- `watchdog!WdLogSingleEntry3` at `0x140379645`
- `watchdog!WdLogSingleEntry3` at `0x140379785`
- `watchdog!WdLogSingleEntry3` at `0x140378032`
- `watchdog!WdLogSingleEntry3` at `0x140378893`
- `watchdog!WdLogSingleEntry3` at `0x140378b2f`
- `watchdog!WdLogSingleEntry3` at `0x140378b59`
- `watchdog!WdLogSingleEntry3` at `0x140378d64`
- `watchdog!WdLogSingleEntry3` at `0x14037903d`
- `watchdog!WdLogSingleEntry3` at `0x1403790d5`
- `watchdog!WdLogSingleEntry3` at `0x14037910e`
- `watchdog!WdLogSingleEntry3` at `0x1403793ef`
- `watchdog!WdLogSingleEntry3` at `0x140379432`
- `watchdog!WdLogSingleEntry3` at `0x14037959b`
- `watchdog!WdLogSingleEntry3` at `0x140379645`
- `watchdog!WdLogSingleEntry3` at `0x140379785`
- `watchdog!WdLogSingleEntry0` at `0x140377be9`
- `watchdog!WdLogSingleEntry0` at `0x14037841f`
- `watchdog!WdLogSingleEntry0` at `0x140378572`
- `watchdog!WdLogSingleEntry0` at `0x14037879a`
- `watchdog!WdLogSingleEntry0` at `0x1403787f5`
- `watchdog!WdLogSingleEntry0` at `0x140378da9`
- `watchdog!WdLogSingleEntry0` at `0x1403791af`
- `watchdog!WdLogSingleEntry0` at `0x140379936`
- `watchdog!WdLogSingleEntry0` at `0x140379956`
- `watchdog!WdLogSingleEntry0` at `0x14037a53f`
- `watchdog!WdLogSingleEntry0` at `0x14037a760`
- `watchdog!WdLogSingleEntry0` at `0x14037a7b0`
- `watchdog!WdLogSingleEntry0` at `0x140377be9`
- `watchdog!WdLogSingleEntry0` at `0x14037841f`
- `watchdog!WdLogSingleEntry0` at `0x140378572`
- `watchdog!WdLogSingleEntry0` at `0x14037879a`
- `watchdog!WdLogSingleEntry0` at `0x1403787f5`
- `watchdog!WdLogSingleEntry0` at `0x140378da9`
- `watchdog!WdLogSingleEntry0` at `0x1403791af`
- `watchdog!WdLogSingleEntry0` at `0x140379936`
- `watchdog!WdLogSingleEntry0` at `0x140379956`
- `watchdog!WdLogSingleEntry0` at `0x14037a53f`
- `watchdog!WdLogSingleEntry0` at `0x14037a760`
- `watchdog!WdLogSingleEntry0` at `0x14037a7b0`
- `watchdog!WdLogSingleEntry1` at `0x140378b7e`
- `watchdog!WdLogSingleEntry1` at `0x140378fbd`
- `watchdog!WdLogSingleEntry1` at `0x140379721`
- `watchdog!WdLogSingleEntry1` at `0x1403798a5`
- `watchdog!WdLogSingleEntry1` at `0x14037a02a`
- `watchdog!WdLogSingleEntry1` at `0x14037a72b`
- `watchdog!WdLogSingleEntry1` at `0x140378b7e`
- `watchdog!WdLogSingleEntry1` at `0x140378fbd`
- `watchdog!WdLogSingleEntry1` at `0x140379721`
- `watchdog!WdLogSingleEntry1` at `0x1403798a5`
- `watchdog!WdLogSingleEntry1` at `0x14037a02a`
- `watchdog!WdLogSingleEntry1` at `0x14037a72b`

## string_xrefs

- `0x140378825`: `!(UserMode && OpenShared)`
- `0x140378061`: `Device 0x%I64x: Driver asked to create a shared resource, but resource 0x%p already exists, and is non-shared, returning 0x%I64x`
- `0x1403791df`: `pCreateStandardAllocation->Flags.Primary == 0`
- `0x140377c19`: `0 != (pCreateAllocation->Flags.CreateShared)`
- `0x1403798d4`: `VmBusSendCreateAllocation failed: 0x%I64x`
- `0x14037a059`: `VmBusSendMakeResident failed: 0x%I64x`

## pseudocode

```c
__int64 __fastcall DXGDEVICE::CreateAllocation(
        DXGDEVICE *this,
        struct _D3DKMT_CREATEALLOCATION *a2,
        unsigned __int8 a3,
        unsigned __int8 a4,
        struct _DXGSHAREDALLOCOBJECT *a5,
        const struct _D3DKM_CREATESTANDARDALLOCATION *a6,
        struct COREDEVICEACCESS *a7,
        unsigned int a8,
        struct _EPROCESS *a9,
        unsigned int *a10,
        unsigned __int64 *a11,
        unsigned __int64 *a12,
        struct _D3DKMT_CREATESTANDARDALLOCATION *a13,
        void *a14,
        UINT a15)
{
  unsigned __int8 v16; // bl
  struct _D3DKMT_CREATEALLOCATION *v17; // r12
  D3DKMT_CREATEALLOCATIONFLAGS Flags; // edx
  struct _PAGED_LOOKASIDE_LIST *v20; // rcx
  unsigned __int64 NumAllocations; // rax
  char *v22; // rax
  struct _D3DDDI_ALLOCATIONINFO2 *v23; // r14
  void **v24; // rdx
  void **v25; // r8
  UINT i; // eax
  struct DXGRESOURCE *v27; // rbx
  char v28; // r9
  UINT j; // edx
  UINT k; // edi
  int DestructionBuffers; // edi
  struct DXGALLOCATION *v32; // r9
  D3DKMT_CREATEALLOCATIONFLAGS v33; // eax
  D3DKMT_HANDLE v34; // eax
  D3DKMT_CREATEALLOCATIONFLAGS v35; // eax
  D3DKMT_HANDLE v36; // ecx
  UINT v37; // r8d
  struct DXGALLOCATION *v38; // rdi
  struct _D3DKMT_CREATEALLOCATION *v39; // r10
  struct DXGALLOCATION *v40; // rax
  D3DKMT_CREATEALLOCATIONFLAGS v41; // eax
  struct DXGALLOCATION *v42; // r14
  struct _D3DKM_CREATESTANDARDALLOCATION *v43; // rdi
  struct _D3DDDI_ALLOCATIONINFO2 *v44; // rsi
  UINT v45; // ebx
  void **v46; // r14
  UINT v48; // eax
  D3DKMT_CREATEALLOCATIONFLAGS v49; // r8d
  __int64 v50; // rax
  __int64 PrivateDriverDataSize; // rcx
  char *v52; // rax
  struct _D3DKMT_CREATEALLOCATION *v53; // rsi
  char v54; // cl
  struct _DXGK_ALLOCATIONINFO *v55; // r8
  D3DKMT_CREATEALLOCATIONFLAGS v56; // eax
  unsigned int v57; // edx
  UINT v58; // ebx
  struct DXGALLOCATION *v59; // r12
  struct _D3DKMT_CREATEALLOCATION *v60; // rdi
  _QWORD *v61; // r14
  UINT v62; // eax
  unsigned int v63; // edx
  __int64 v64; // rax
  struct DXGALLOCATION *v65; // rbx
  struct DXGALLOCATION *v66; // r12
  struct _D3DKMT_CREATEALLOCATION *v67; // rdi
  __int64 v68; // r13
  unsigned __int64 v69; // r14
  DXGPUSHLOCK *v70; // rcx
  unsigned int v71; // edx
  __int64 v72; // r9
  __int64 v73; // r14
  __int64 v74; // rax
  struct DXGGLOBAL *Global; // rax
  __int64 v76; // rcx
  __int64 PrivateRuntimeDataSize; // rax
  __int64 v78; // rcx
  __int64 v79; // rax
  unsigned __int8 v80; // di
  struct COREDEVICEACCESS *v81; // rax
  struct DXGALLOCATION *v82; // rcx
  __int64 v83; // rax
  unsigned int *m; // rdx
  char *v85; // rcx
  __int64 v86; // rax
  UINT v87; // eax
  void *v88; // rax
  struct _D3DKMT_CREATESTANDARDALLOCATION *v89; // rax
  __int64 v90; // rax
  struct _EPROCESS *v91; // rdx
  void *v92; // rcx
  size_t v93; // r8
  const void *v94; // rdx
  unsigned int v95; // eax
  struct DXGALLOCATION *v96; // rdx
  int v97; // edi
  int v98; // eax
  unsigned __int8 v99; // al
  D3DGPU_VIRTUAL_ADDRESS BaseAddress; // rcx
  UINT v101; // ecx
  struct DXGALLOCATION *v102; // rsi
  struct _D3DKMT_CREATEALLOCATION *v103; // r12
  __int64 v104; // rax
  int v105; // eax
  ADAPTER_DISPLAY *v106; // rcx
  __int64 v107; // r8
  __int64 v108; // r14
  struct DXGALLOCATION *v109; // rcx
  __int64 v110; // rax
  __int64 v111; // r8
  _QWORD *v112; // rdx
  __int64 v113; // rcx
  struct DXGALLOCATION *v114; // rcx
  struct DXGALLOCATION *v115; // r8
  unsigned __int64 v116; // rdx
  __int64 v117; // rax
  __int64 v118; // r10
  int v119; // r9d
  int v120; // ecx
  unsigned __int64 v121; // rcx
  unsigned __int64 v122; // rax
  signed int v123; // ebx
  __int64 v124; // rax
  unsigned __int64 v125; // rax
  __int64 v126; // rax
  unsigned __int64 v127; // rax
  __int64 v128; // rax
  unsigned __int64 v129; // rax
  __int64 v130; // rax
  unsigned __int8 v131; // al
  __int64 v132; // rax
  __int64 v133; // r8
  __int64 v134; // r8
  UINT Value; // eax
  struct DXGALLOCATION *v136; // rax
  struct DXGALLOCATION *v137; // r9
  __int64 v138; // rax
  unsigned int v139; // ecx
  int v140; // r9d
  struct DXGALLOCATION *hSection; // rcx
  SIZE_T Size; // r8
  unsigned int v143; // ecx
  __int64 v144; // rax
  __int64 v145; // rcx
  __int64 v146; // rcx
  UINT v147; // eax
  void *pStandardAllocation; // rdx
  unsigned int v149; // ecx
  char v150; // r11
  D3DKMT_CREATEALLOCATIONFLAGS v151; // ecx
  const void *v152; // r10
  void *v153; // r8
  void **v154; // rdx
  unsigned int v155; // r9d
  int Allocation; // eax
  struct DXGALLOCATION *v157; // rdi
  __int64 v158; // rbx
  _DWORD *v159; // r9
  D3DKMT_CREATEALLOCATIONFLAGS v160; // ecx
  int v161; // eax
  __int64 v162; // rax
  const wchar_t *v163; // r9
  UINT v164; // ecx
  struct DXGALLOCATION *v165; // r12
  __int64 v166; // r10
  __int64 v167; // rcx
  char v168; // r14
  __int64 v169; // rbx
  int v170; // edi
  __int64 v171; // rsi
  unsigned int CurrentProcessId; // eax
  int v173; // ecx
  int v174; // r8d
  struct _EPROCESS *v175; // r10
  UINT n; // ebx
  D3DKMT_CREATEALLOCATIONFLAGS v177; // eax
  unsigned int *v178; // rdi
  struct COREDEVICEACCESS *v179; // r11
  __int64 v180; // rdx
  struct _DXGK_ALLOCATIONINFO *v181; // r8
  int v182; // eax
  NTSTATUS v183; // eax
  __int64 v184; // rbx
  struct COREDEVICEACCESS *v185; // rsi
  __int64 v186; // rax
  struct COREDEVICEACCESS *v187; // r8
  __int64 v188; // rcx
  struct COREDEVICEACCESS *v189; // r9
  int Resident; // eax
  __int64 v191; // rbx
  __int64 v192; // rdx
  unsigned __int64 v193; // rcx
  struct _D3DKMT_CREATESTANDARDALLOCATION *v194; // r8
  size_t v195; // rcx
  _QWORD *v196; // rdi
  void **v197; // rax
  struct DXGALLOCATION *v198; // rcx
  UINT v199; // edx
  __int64 v200; // rax
  __int64 v201; // rbx
  unsigned int v202; // eax
  int v203; // r8d
  int v204; // eax
  struct DXGALLOCATION *v205; // rbx
  __int64 v206; // rdi
  D3DKMT_CREATEALLOCATIONFLAGS v207; // ecx
  NTSTATUS v208; // eax
  unsigned int v209; // eax
  __int64 v210; // rdx
  __int64 v211; // rcx
  char v212; // r14
  int v213; // eax
  __int64 v214; // rcx
  int v215; // [rsp+20h] [rbp-368h]
  int v216; // [rsp+38h] [rbp-350h]
  int Src; // [rsp+40h] [rbp-348h]
  int v218; // [rsp+48h] [rbp-340h]
  int v219; // [rsp+50h] [rbp-338h]
  int v220; // [rsp+58h] [rbp-330h]
  int v221; // [rsp+60h] [rbp-328h]
  int v222; // [rsp+68h] [rbp-320h]
  int v223; // [rsp+70h] [rbp-318h]
  int v224; // [rsp+78h] [rbp-310h]
  int v225; // [rsp+88h] [rbp-300h]
  int v226; // [rsp+90h] [rbp-2F8h]
  int v227; // [rsp+98h] [rbp-2F0h]
  int v228; // [rsp+A0h] [rbp-2E8h]
  int v229; // [rsp+A8h] [rbp-2E0h]
  int v230; // [rsp+B0h] [rbp-2D8h]
  int v231; // [rsp+B8h] [rbp-2D0h]
  int v232; // [rsp+C0h] [rbp-2C8h]
  int v233; // [rsp+C8h] [rbp-2C0h]
  int v234; // [rsp+D0h] [rbp-2B8h]
  int v235; // [rsp+D8h] [rbp-2B0h]
  int v236; // [rsp+E0h] [rbp-2A8h]
  int v237; // [rsp+E8h] [rbp-2A0h]
  char v240; // [rsp+112h] [rbp-276h]
  int v241; // [rsp+120h] [rbp-268h]
  struct _D3DDDI_ALLOCATIONINFO2 *v242; // [rsp+128h] [rbp-260h]
  unsigned __int8 v243[8]; // [rsp+130h] [rbp-258h] BYREF
  struct DXGALLOCATION *v244; // [rsp+138h] [rbp-250h]
  UINT v245; // [rsp+140h] [rbp-248h]
  struct DXGRESOURCE *v246; // [rsp+148h] [rbp-240h]
  PVOID Object; // [rsp+150h] [rbp-238h] BYREF
  struct DXGALLOCATION *v248; // [rsp+158h] [rbp-230h] BYREF
  char v249; // [rsp+160h] [rbp-228h]
  PVOID v250; // [rsp+168h] [rbp-220h] BYREF
  struct _D3DKMT_CREATEALLOCATION *v251; // [rsp+170h] [rbp-218h]
  unsigned __int8 v252; // [rsp+178h] [rbp-210h]
  unsigned int VidPnSourceId; // [rsp+180h] [rbp-208h]
  char v254; // [rsp+184h] [rbp-204h]
  struct DXGPROCESS *Current; // [rsp+188h] [rbp-200h]
  void **v256; // [rsp+190h] [rbp-1F8h]
  struct _D3DKMT_CREATESTANDARDALLOCATION *v257; // [rsp+198h] [rbp-1F0h]
  void **v258; // [rsp+1A0h] [rbp-1E8h]
  struct _DXGK_ALLOCATIONINFO *v259; // [rsp+1A8h] [rbp-1E0h]
  struct COREDEVICEACCESS *v260; // [rsp+1B0h] [rbp-1D8h]
  struct _D3DKM_CREATESTANDARDALLOCATION *v261; // [rsp+1B8h] [rbp-1D0h]
  struct _EPROCESS *v262; // [rsp+1C0h] [rbp-1C8h]
  PVOID v263; // [rsp+1C8h] [rbp-1C0h] BYREF
  struct DXGALLOCATION *v264; // [rsp+1D0h] [rbp-1B8h] BYREF
  struct _D3DKMT_CREATEALLOCATION *v265; // [rsp+1D8h] [rbp-1B0h]
  struct _DXGSHAREDALLOCOBJECT *v266; // [rsp+1E0h] [rbp-1A8h] BYREF
  struct DXGALLOCATION *v267; // [rsp+1E8h] [rbp-1A0h]
  struct _D3DDDI_ALLOCATIONINFO2 *v268; // [rsp+1F0h] [rbp-198h]
  struct DXGPROCESS *v269; // [rsp+1F8h] [rbp-190h]
  struct _D3DKMT_CREATEALLOCATION *v270; // [rsp+200h] [rbp-188h]
  void *v271; // [rsp+210h] [rbp-178h]
  struct _DXGK_OPENALLOCATIONINFO *v272; // [rsp+218h] [rbp-170h]
  DXGDEVICE *v273; // [rsp+220h] [rbp-168h]
  char v274[16]; // [rsp+228h] [rbp-160h] BYREF
  struct DXGRESOURCE *v275; // [rsp+238h] [rbp-150h] BYREF
  int v276; // [rsp+240h] [rbp-148h]
  PVOID Entry; // [rsp+248h] [rbp-140h]
  _QWORD *v278; // [rsp+250h] [rbp-138h]
  unsigned int *v279; // [rsp+258h] [rbp-130h]
  const struct _D3DKM_CREATESTANDARDALLOCATION *v280; // [rsp+260h] [rbp-128h]
  DXGFASTMUTEX *v281; // [rsp+268h] [rbp-120h] BYREF
  char v282; // [rsp+270h] [rbp-118h]
  struct _DXGKARG_DESCRIBEALLOCATION v283; // [rsp+278h] [rbp-110h] BYREF
  struct _PAGED_LOOKASIDE_LIST *v284; // [rsp+2A8h] [rbp-E0h]
  _BYTE v285[32]; // [rsp+2B0h] [rbp-D8h] BYREF
  struct D3DDDI_MAPGPUVIRTUALADDRESS v286; // [rsp+2D0h] [rbp-B8h] BYREF

  v16 = a3;
  v17 = a2;
  v265 = a2;
  v261 = a6;
  v273 = this;
  v270 = a2;
  v252 = a3;
  v266 = a5;
  v280 = a6;
  v260 = a7;
  v262 = a9;
  v279 = a10;
  Object = a11;
  v263 = a12;
  v257 = a13;
  if ( !ADAPTER_RENDER::IsCoreResourceSharedOwner(*((ADAPTER_RENDER **)this + 2)) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 4819;
    DxgkLogInternalTriageEvent(
      0,
      262146,
      -1,
      (unsigned int)L"GetRenderCore()->IsCoreResourceSharedOwner()",
      4819,
      0,
      0,
      0,
      0);
  }
  if ( v16 && a4 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 4824;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"!(UserMode && OpenShared)", 4824, 0, 0, 0, 0);
  }
  v240 = *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 209LL);
  Current = DXGPROCESS::GetCurrent();
  Flags = v17->Flags;
  if ( (*(_WORD *)&Flags & 0x800) == 0 )
    goto LABEL_5;
  if ( (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 2580LL) & 0x10) == 0 )
  {
    WdLogSingleEntry2(3, this);
    WdLogGlobalForLineNumber = 4833;
    return 3221225485LL;
  }
  if ( (*(_BYTE *)&Flags & 2) == 0 )
  {
    WdLogSingleEntry3(3, this, -1073741811, 1);
    WdLogGlobalForLineNumber = 4838;
    return 3221225485LL;
  }
LABEL_5:
  v20 = (struct _PAGED_LOOKASIDE_LIST *)*((_QWORD *)this + 2);
  v250 = v20;
  NumAllocations = v17->NumAllocations;
  if ( (unsigned int)NumAllocations > 5 )
  {
    v256 = 0;
    v23 = 0;
    v242 = 0;
    v268 = 0;
    v121 = NumAllocations;
    v122 = 96 * NumAllocations;
    Entry = (PVOID)v122;
    v123 = v122 > 0xFFFFFFFF ? 0xC0000095 : 0;
    if ( v122 <= 0xFFFFFFFF )
    {
      v124 = 96 * v121;
      if ( !is_mul_ok(v121, 0x60u) )
        v124 = -1;
      v23 = (struct _D3DDDI_ALLOCATIONINFO2 *)operator new[](v124, 1265072196, 256);
      v242 = v23;
      v268 = v23;
      v122 = (unsigned __int64)Entry;
    }
    v259 = 0;
    if ( v122 <= 0xFFFFFFFF )
    {
      v125 = 88LL * v17->NumAllocations;
      v123 = v125 > 0xFFFFFFFF ? 0xC0000095 : 0;
      if ( v125 <= 0xFFFFFFFF )
      {
        v126 = 88LL * v17->NumAllocations;
        if ( !is_mul_ok(v17->NumAllocations, 0x58u) )
          v126 = -1;
        v259 = (struct _DXGK_ALLOCATIONINFO *)operator new[](v126, 1265072196, 258);
      }
    }
    v272 = 0;
    if ( v123 >= 0 )
    {
      v127 = 32LL * v17->NumAllocations;
      v123 = v127 > 0xFFFFFFFF ? 0xC0000095 : 0;
      if ( v127 <= 0xFFFFFFFF )
      {
        v128 = 32LL * v17->NumAllocations;
        if ( !is_mul_ok(v17->NumAllocations, 0x20u) )
          v128 = -1;
        v272 = (struct _DXGK_OPENALLOCATIONINFO *)operator new[](v128, 1265072196, 256);
      }
    }
    v24 = 0;
    v258 = 0;
    if ( v123 < 0 || (v129 = 8LL * v17->NumAllocations, v123 = v129 > 0xFFFFFFFF ? 0xC0000095 : 0, v129 > 0xFFFFFFFF) )
    {
      v131 = a3;
      v25 = 0;
    }
    else
    {
      v130 = 8LL * v17->NumAllocations;
      if ( !is_mul_ok(v17->NumAllocations, 8u) )
        v130 = -1;
      v24 = (void **)operator new[](v130, 1265072196, 256);
      v258 = v24;
      v131 = a3;
      if ( a3 )
      {
        v132 = 8LL * v17->NumAllocations;
        if ( !is_mul_ok(v17->NumAllocations, 8u) )
          v132 = -1;
        v25 = (void **)operator new[](v132, 1265072196, 256);
        v256 = v25;
        v131 = a3;
        v24 = v258;
      }
      else
      {
        v25 = 0;
      }
    }
    if ( v123 < 0 || !v23 || !v259 || !v272 || !v24 || (Entry = 0, !v25) && v131 )
    {
      DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v23);
      DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v259);
      DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v272);
      DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v258);
      DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v256);
      v133 = v17->NumAllocations;
      if ( v123 >= 0 )
      {
        v123 = -1073741801;
        WdLogSingleEntry3(3, this, v133, -1073741801);
        WdLogGlobalForLineNumber = 4943;
      }
      else
      {
        WdLogSingleEntry3(3, this, v133, v123);
        WdLogGlobalForLineNumber = 4936;
      }
      return (unsigned int)v123;
    }
    v16 = a3;
  }
  else
  {
    v22 = (char *)ExAllocateFromPagedLookasideList(v20 + 13);
    v23 = (struct _D3DDDI_ALLOCATIONINFO2 *)v22;
    v242 = (struct _D3DDDI_ALLOCATIONINFO2 *)v22;
    if ( !v22 )
    {
      WdLogSingleEntry1(6);
      WdLogGlobalForLineNumber = 4955;
      DxgkLogInternalTriageEvent(
        0,
        262145,
        -1,
        (unsigned int)L"Device 0x%I64x: Out of memory allocating scratch data",
        (__int64)this,
        0,
        0,
        0,
        0);
      return -1073741801;
    }
    Entry = v22;
    v259 = (struct _DXGK_ALLOCATIONINFO *)(v22 + 720);
    v272 = (struct _DXGK_OPENALLOCATIONINFO *)(v22 + 480);
    v24 = (void **)(v22 + 640);
    v258 = (void **)(v22 + 640);
    v25 = (void **)(v22 + 680);
    v256 = (void **)(v22 + 680);
    v268 = (struct _D3DDDI_ALLOCATIONINFO2 *)v22;
  }
  v251 = v17;
  v284 = (struct _PAGED_LOOKASIDE_LIST *)v250;
  v267 = this;
  v269 = Current;
  v271 = 0;
  for ( i = 0; i < v17->NumAllocations; ++i )
  {
    v24[i] = 0;
    if ( v16 )
      v25[i] = 0;
  }
  v244 = 0;
  v264 = 0;
  v243[0] = 0;
  v27 = 0;
  v246 = 0;
  v249 = 0;
  v275 = 0;
  DXGSYNCOBJECTMUTEX::DXGSYNCOBJECTMUTEX((DXGSYNCOBJECTMUTEX *)&v281);
  DXGAUTOPUSHLOCK::DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v285, 0, 0);
  if ( a3 )
    RtlCopyFromUser(v23, v17->pAllocationInfo, 96LL * v17->NumAllocations);
  else
    memmove(v23, v17->pAllocationInfo, 96LL * v17->NumAllocations);
  v28 = v240;
  v254 = v240;
  VidPnSourceId = -1;
  if ( (*(_DWORD *)&v17->Flags & 0x10000) != 0 )
  {
    v23->pPrivateDriverData = a14;
    v23->PrivateDriverDataSize = a15;
  }
  for ( j = 0; ; ++j )
  {
    v245 = j;
    if ( j >= v17->NumAllocations )
      break;
    if ( (*(_DWORD *)&v17->Flags & 0x800) != 0 )
    {
      v134 = j;
      Value = v23[v134].Flags.Value;
      if ( (Value & 1) != 0 )
      {
        VidPnSourceId = v23[v134].VidPnSourceId;
        v28 = v240;
        if ( !*((_QWORD *)this + 237) )
        {
          Value &= ~1u;
          v23[v134].Flags.Value = Value;
        }
      }
      if ( (Value & 2) != 0 )
      {
        WdLogSingleEntry2(3, this);
        WdLogGlobalForLineNumber = 5057;
        goto LABEL_153;
      }
    }
    if ( (v23[j].Flags.Value & 1) != 0 && !v28 )
    {
      v136 = (struct DXGALLOCATION *)*((_QWORD *)this + 237);
      v248 = v136;
      if ( v136 )
      {
        v106 = (ADAPTER_DISPLAY *)*((_QWORD *)v136 + 404);
        if ( !v106 || !ADAPTER_DISPLAY::IsCoreResourceSharedOwner(v106) )
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 5084;
          DxgkLogInternalTriageEvent(
            0,
            262146,
            -1,
            (unsigned int)L"pDisplayAdapter->IsDisplayAdapter() && pDisplayAdapter->GetDisplayCore()->IsCoreResourceSharedOwner()",
            5084,
            0,
            0,
            0,
            0);
        }
        v137 = v248;
        if ( *(_DWORD *)(*((_QWORD *)v248 + 404) + 96LL) != *((_DWORD *)this + 476) )
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 5090;
          DxgkLogInternalTriageEvent(
            0,
            262146,
            -1,
            (unsigned int)L"pDisplayAdapter->GetDisplayCore()->GetNumVidPnSources() == this->GetNumVidPnSources()",
            5090,
            0,
            0,
            0,
            0);
          v137 = v248;
        }
        j = v245;
        v138 = v245;
        v250 = (PVOID)(v138 * 96);
        v139 = v23[v138].VidPnSourceId;
        if ( v139 >= *((_DWORD *)this + 476) )
        {
          WdLogSingleEntry3(3, this, v23[v138].VidPnSourceId, -1073741811);
          WdLogGlobalForLineNumber = 5097;
          goto LABEL_153;
        }
        if ( !*((_DWORD *)this + 116) && !a4 && (*((_DWORD *)Current + 102) & 0x100) == 0 )
        {
          if ( !ADAPTER_DISPLAY::IsVidPnSourceOwner(*((ADAPTER_DISPLAY **)v137 + 404), this, v139) )
          {
            DestructionBuffers = -1071775744;
            v241 = -1071775744;
            WdLogSingleEntry4(3, -1071775744, this, *(unsigned int *)((char *)&v23->VidPnSourceId + (_QWORD)v250), v245);
            WdLogGlobalForLineNumber = 5112;
            goto LABEL_294;
          }
          j = v245;
        }
      }
      else if ( (*(_DWORD *)(*((_QWORD *)this + 5) + 408LL) & 0x100) == 0 )
      {
        WdLogSingleEntry3(3, this, v23[j].VidPnSourceId, -1073741811);
        WdLogGlobalForLineNumber = 5076;
        goto LABEL_153;
      }
    }
    v48 = v23[j].Flags.Value;
    if ( (v48 & 2) != 0 && (v48 & 1) == 0 )
    {
      WdLogSingleEntry2(3, -1073741811);
      WdLogGlobalForLineNumber = 5130;
      goto LABEL_153;
    }
    v49 = v17->Flags;
    if ( (*(_DWORD *)&v49 & 0x10000) != 0 )
    {
      v140 = *(_DWORD *)&v17->Flags & 0x20;
      if ( (*(_BYTE *)&v49 & 0x20) != 0 && !v23[j].hSection || (*(_DWORD *)&v49 & 0x20000) != 0 && !v23[j].hSection )
      {
        WdLogSingleEntry2(2, this);
        WdLogGlobalForLineNumber = 5144;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Device 0x%I64x: ExistingSysMem pointer or Section Handle not specified, returning 0x%I64x",
          (__int64)this,
          -1073741811,
          0,
          0,
          0);
LABEL_153:
        DestructionBuffers = -1073741811;
LABEL_292:
        v241 = -1073741811;
LABEL_294:
        v42 = 0;
        goto LABEL_47;
      }
      hSection = (struct DXGALLOCATION *)v23[j].hSection;
      v248 = hSection;
      Size = v17->pStandardAllocation->ExistingHeapData.Size;
      v250 = (PVOID)Size;
      if ( v140 && hSection != (struct DXGALLOCATION *)((unsigned __int64)hSection & 0xFFFFFFFFFFFFF000uLL)
        || Size != (Size & 0xFFFFFFFFFFFFF000uLL) )
      {
        WdLogSingleEntry2(2, hSection);
        WdLogGlobalForLineNumber = 5157;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Existing sysmem must be paged aligned and a multiple of page in size.                    pSysMem"
                         ":0x%I64x, Size:0x%I64x",
          (__int64)v248,
          (__int64)v250,
          0,
          0,
          0);
        DestructionBuffers = -1073741811;
        goto LABEL_292;
      }
    }
    v28 = v240;
  }
  for ( k = 0; k < v17->NumAllocations; ++k )
  {
    v50 = k;
    PrivateDriverDataSize = v23[v50].PrivateDriverDataSize;
    if ( (unsigned int)PrivateDriverDataSize > 0x7FFFFFFF )
    {
      DestructionBuffers = 0;
      v241 = 0;
      WdLogSingleEntry1(3);
      WdLogGlobalForLineNumber = 5175;
      v27 = 0;
      goto LABEL_294;
    }
    if ( v23[v50].pPrivateDriverData && (_DWORD)PrivateDriverDataSize )
    {
      if ( a3 && (*(_DWORD *)&v17->Flags & 0x10000) == 0 )
        PrivateDriverDataSize = (unsigned int)(2 * PrivateDriverDataSize);
      v52 = (char *)operator new[](PrivateDriverDataSize, 1265072196, 258);
      v258[k] = v52;
      if ( !v52 )
      {
        DestructionBuffers = -1073741801;
        v241 = -1073741801;
        WdLogSingleEntry3(3, this, v17->NumAllocations, -1073741801);
        WdLogGlobalForLineNumber = 5217;
        goto LABEL_300;
      }
      if ( a3 && (*(_DWORD *)&v17->Flags & 0x10000) == 0 )
      {
        v85 = &v52[v23[k].PrivateDriverDataSize];
        v256[k] = v85;
        RtlCopyFromUser(v85, v23[k].pPrivateDriverData, v23[k].PrivateDriverDataSize);
      }
    }
    else
    {
      v258[k] = 0;
      if ( a3 )
        v256[k] = 0;
    }
  }
  if ( a3 )
  {
    if ( v17->pStandardAllocation )
    {
      v87 = v17->PrivateDriverDataSize;
      if ( v87 )
      {
        v88 = (void *)operator new[](v87, 1265072196, 258);
        v271 = v88;
        if ( !v88 )
        {
          DestructionBuffers = -1073741801;
          v241 = -1073741801;
          WdLogSingleEntry3(3, this, v17->PrivateDriverDataSize, -1073741801);
          WdLogGlobalForLineNumber = 5262;
          goto LABEL_300;
        }
        RtlCopyFromUser(v88, v17->pStandardAllocation, v17->PrivateDriverDataSize);
      }
    }
  }
  DestructionBuffers = DXGDEVICE::OpenResourceObject(
                         this,
                         v17,
                         v23,
                         a4,
                         v262,
                         v266,
                         (struct DXGRESOURCEREFERENCE *)&v275,
                         v243,
                         v261,
                         (struct DXGAUTOMUTEX *)&v281,
                         (struct DXGAUTOPUSHLOCK *)v285);
  v241 = DestructionBuffers;
  if ( DestructionBuffers < 0 )
    goto LABEL_300;
  v27 = v275;
  v246 = v275;
  if ( v275 && (*((_DWORD *)v275 + 1) & 1) == 0 && (*(_DWORD *)&v17->Flags & 2) != 0 )
  {
    WdLogSingleEntry3(2, this, v275, -1073741811);
    WdLogGlobalForLineNumber = 5315;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Device 0x%I64x: Driver asked to create a shared resource, but resource 0x%p already exists, and is n"
                     "on-shared, returning 0x%I64x",
      (__int64)this,
      (__int64)v27,
      -1073741811,
      0,
      0);
    goto LABEL_153;
  }
  DestructionBuffers = DXGDEVICE::CreateDestructionBuffers(this, v17->NumAllocations, v275, v243[0]);
  v241 = DestructionBuffers;
  if ( DestructionBuffers < 0 )
  {
LABEL_300:
    v42 = 0;
    goto LABEL_46;
  }
  v248 = 0;
  DestructionBuffers = DXGDEVICE::CreateAllocationObjects(this, v17->NumAllocations, &v264, v27, &v248);
  v241 = DestructionBuffers;
  if ( DestructionBuffers < 0 )
  {
    v42 = v264;
    v244 = v264;
    goto LABEL_47;
  }
  v32 = v248;
  v244 = v264;
  if ( v248 )
  {
    DXGDEVICE::AppendAllocationListToResourceOrDevice(this, v27, v264, v248);
    v249 = 1;
  }
  v33 = v17->Flags;
  if ( (*(_WORD *)&v33 & 0x800) != 0 )
  {
    if ( VidPnSourceId != -1 )
    {
      *(_DWORD *)(*((_QWORD *)v27 + 7) + 12LL) |= 0x40u;
      *((_DWORD *)v27 + 1) |= 8u;
      *(_DWORD *)(*((_QWORD *)v27 + 7) + 12LL) ^= ((unsigned __int8)*(_DWORD *)(*((_QWORD *)v27 + 7) + 12LL)
                                                 ^ (unsigned __int8)(*(_DWORD *)&v17->Flags >> 3))
                                                & 0x80;
    }
  }
  else if ( (*(_WORD *)&v33 & 0x1000) != 0 )
  {
    if ( v261 )
    {
      if ( (*(_DWORD *)v261 & 0x80u) != 0 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 5381;
        DxgkLogInternalTriageEvent(
          0,
          262146,
          -1,
          (unsigned int)L"pCreateStandardAllocation->Flags.Primary == 0",
          5381,
          0,
          0,
          0,
          0);
      }
      if ( (*(_DWORD *)v261 & 0x100) != 0 )
        goto LABEL_156;
    }
  }
  else if ( v27 )
  {
    v86 = *((_QWORD *)v27 + 7);
    if ( v86 )
    {
      if ( (*(_BYTE *)(v86 + 12) & 0x60) == 0x60 )
LABEL_156:
        *((_DWORD *)v27 + 1) |= 8u;
    }
  }
  if ( !v240 )
  {
    memset(v259, 0, 88LL * v17->NumAllocations);
    v54 = a4;
    if ( !a4 )
    {
      DestructionBuffers = DXGDEVICE::CreateDriverAllocations(
                             this,
                             v17,
                             v23,
                             v259,
                             v244,
                             v27,
                             v258,
                             v256,
                             v271,
                             v261,
                             a3,
                             v257);
      v241 = DestructionBuffers;
      v54 = 0;
    }
    if ( DestructionBuffers < 0 )
      goto LABEL_311;
    DestructionBuffers = DXGDEVICE::OpenAllocations(
                           this,
                           v17,
                           v23,
                           v244,
                           v272,
                           v258,
                           v256,
                           v271,
                           a3,
                           v54,
                           a8,
                           v279,
                           (unsigned __int64 *)Object);
    v241 = DestructionBuffers;
    if ( DestructionBuffers < 0 )
      goto LABEL_311;
    v55 = v259;
    if ( (*(_DWORD *)&v17->Flags & 8) != 0 )
      v259->Flags.Value |= 0x4000008u;
    v56 = v17->Flags;
    if ( (*(_WORD *)&v56 & 0x100) != 0 )
    {
      v55->Flags.Value = v55->Flags.Value & 0xFEFFFFFB | 0x1000000;
    }
    else if ( (*(_WORD *)&v56 & 0x200) != 0 )
    {
      v55->Flags.Value |= 0x800004u;
    }
    v57 = v55->Flags.Value | 0x800;
    if ( (*(_DWORD *)&v17->Flags & 0x8000) == 0 )
      v57 = v55->Flags.Value & 0xFFFFF7FF;
    v55->Flags.Value = v57;
    if ( (*(_DWORD *)&v17->Flags & 0x80000) != 0 )
      v55->Flags.Value = v57 | 0x1000;
    DestructionBuffers = DXGDEVICE::CreateVidMmAllocations(this, v17, v23, v55, v244, v261, a4, v260);
    v241 = DestructionBuffers;
    if ( DestructionBuffers < 0 )
    {
LABEL_311:
      v42 = v244;
      goto LABEL_47;
    }
    if ( v263 )
    {
      LODWORD(Object) = 0;
      if ( v17->NumAllocations )
      {
        v58 = 0;
        v59 = v244;
        v60 = v251;
        v61 = v263;
        do
        {
          v61[v58] = VIDMM_EXPORT::VidMmQueryAllocationSizeInSystemMemory(
                       *(VIDMM_EXPORT **)(*((_QWORD *)this + 2) + 760LL),
                       *((const struct VIDMM_MULTI_ALLOC **)v59 + 3),
                       (*(_DWORD *)&v60->Flags & 0x20) != 0);
          v59 = (struct DXGALLOCATION *)*((_QWORD *)v59 + 8);
          ++v58;
        }
        while ( v58 < v60->NumAllocations );
        v17 = v60;
        v27 = v246;
        DestructionBuffers = v241;
        v23 = v242;
      }
    }
  }
  if ( v243[0] )
  {
    if ( v27 )
    {
      if ( (*((_DWORD *)v27 + 1) & 1) != 0 )
      {
        v74 = *((_QWORD *)v27 + 7);
        if ( !*(_DWORD *)(v74 + 24) && (*(_DWORD *)(v74 + 12) & 8) == 0 )
        {
          DXGGLOBALSHAREMUTEX::DXGGLOBALSHAREMUTEX((DXGGLOBALSHAREMUTEX *)v274);
          DXGAUTOMUTEX::Acquire((DXGAUTOMUTEX *)v274);
          if ( (*(_DWORD *)&v17->Flags & 2) == 0 )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 5519;
            DxgkLogInternalTriageEvent(
              0,
              262146,
              -1,
              (unsigned int)L"0 != (pCreateAllocation->Flags.CreateShared)",
              5519,
              0,
              0,
              0,
              0);
          }
          if ( (*((_DWORD *)Current + 102) & 0x100) != 0 )
          {
            *(_DWORD *)(*((_QWORD *)v27 + 7) + 24LL) = DXGPROCESS::AllocHandleSafe(
                                                         *((_QWORD *)Current + 75),
                                                         *((_QWORD *)v27 + 7),
                                                         2);
            *(_DWORD *)(*((_QWORD *)v27 + 7) + 12LL) |= 0x2000u;
          }
          else
          {
            Global = DXGGLOBAL::GetGlobal();
            *(_DWORD *)(*((_QWORD *)v27 + 7) + 24LL) = DXGGLOBAL::AllocHandle(Global, *((_QWORD *)v27 + 7), 2);
          }
          if ( !*(_DWORD *)(*((_QWORD *)v27 + 7) + 24LL) )
          {
            WdLogSingleEntry2(3, this);
            WdLogGlobalForLineNumber = 5543;
            DestructionBuffers = -1073741801;
            v241 = -1073741801;
            DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX((DXGPROCESSCOPYPROTECTIONMUTEX *)v274);
            goto LABEL_316;
          }
          DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX((DXGPROCESSCOPYPROTECTIONMUTEX *)v274);
        }
      }
    }
    DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(
      (DXGAUTOPUSHLOCKEXCLUSIVE *)&v283,
      (DXGDEVICE *)((char *)this + 240));
    v64 = *((_QWORD *)this + 7);
    if ( v64 )
      *(_QWORD *)(v64 + 32) = v27;
    *((_QWORD *)v27 + 5) = *((_QWORD *)this + 7);
    *((_QWORD *)this + 7) = v27;
    DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)&v283);
  }
  v34 = 0;
  if ( v27 )
    v34 = *((_DWORD *)v27 + 4);
  v17->hResource = v34;
  v35 = v17->Flags;
  if ( ((*(_BYTE *)&v35 & 2) != 0 || a4) && (*(_BYTE *)&v35 & 0x40) == 0 )
    v36 = *(_DWORD *)(*((_QWORD *)v27 + 7) + 24LL);
  else
    v36 = 0;
  v17->hGlobalShare = v36;
  if ( a3 )
  {
    v83 = 0;
    v276 = 0;
    for ( m = (unsigned int *)v244; ; m = (unsigned int *)*((_QWORD *)v248 + 8) )
    {
      v248 = (struct DXGALLOCATION *)m;
      if ( (unsigned int)v83 >= v17->NumAllocations )
        break;
      RtlWriteULongToUser((char *)v17->pAllocationInfo + 96 * v83, m[4]);
      v83 = (unsigned int)++v276;
    }
    if ( DestructionBuffers < 0 )
      goto LABEL_316;
    v38 = v244;
    goto LABEL_36;
  }
  v37 = 0;
  v38 = v244;
  v32 = v244;
  if ( !v17->NumAllocations )
  {
LABEL_36:
    v39 = v251;
    goto LABEL_37;
  }
  v39 = v251;
  do
  {
    *(&v39->pAllocationInfo->hAllocation + 24 * v37++) = *((_DWORD *)v32 + 4);
    v32 = (struct DXGALLOCATION *)*((_QWORD *)v32 + 8);
  }
  while ( v37 < v39->NumAllocations );
LABEL_37:
  if ( (*(_DWORD *)(*((_QWORD *)v267 + 5) + 408LL) & 0x100) == 0 || *((_DWORD *)this + 476) )
  {
    v62 = 0;
    while ( 1 )
    {
      v248 = v38;
      v245 = v62;
      if ( v62 >= v39->NumAllocations )
      {
        v38 = v244;
        break;
      }
      v63 = *(_DWORD *)(*((_QWORD *)v38 + 6) + 4LL);
      if ( (v63 & 1) != 0 )
      {
        DestructionBuffers = DXGDEVICE::AddPrimaryAllocation(this, v38);
        v241 = DestructionBuffers;
        if ( DestructionBuffers < 0 )
          goto LABEL_316;
        v38 = v248;
      }
      else
      {
        if ( (v63 & 2) == 0 )
          goto LABEL_98;
        DXGDEVICE::SetDisplayedPrimary(this, (v63 >> 6) & 0xF, v38, 0, 1u);
      }
      v39 = v251;
LABEL_98:
      v62 = v245 + 1;
      v38 = (struct DXGALLOCATION *)*((_QWORD *)v38 + 8);
    }
  }
  if ( (*(_DWORD *)&v17->Flags & 2) == 0 )
    goto LABEL_40;
  if ( v17->pPrivateRuntimeData )
  {
    v76 = *((_QWORD *)v27 + 7);
    PrivateRuntimeDataSize = v17->PrivateRuntimeDataSize;
    if ( *(_QWORD *)(v76 + 104) )
    {
      v143 = *(_DWORD *)(v76 + 112);
      if ( v143 != (_DWORD)PrivateRuntimeDataSize )
      {
        DestructionBuffers = -1073741811;
        v241 = -1073741811;
        WdLogSingleEntry3(3, this, PrivateRuntimeDataSize, v143);
        WdLogGlobalForLineNumber = 5704;
        goto LABEL_316;
      }
    }
    else
    {
      *(_QWORD *)(*((_QWORD *)v27 + 7) + 104LL) = operator new[]((unsigned int)PrivateRuntimeDataSize, 1265072196, 258);
      v78 = *((_QWORD *)v27 + 7);
      v79 = v17->PrivateRuntimeDataSize;
      if ( !*(_QWORD *)(v78 + 104) )
      {
        DestructionBuffers = -1073741801;
        v241 = -1073741801;
        WdLogSingleEntry3(3, this, v79, -1073741801);
        WdLogGlobalForLineNumber = 5691;
        goto LABEL_316;
      }
      *(_DWORD *)(v78 + 112) = v79;
    }
    v80 = a3;
    if ( a3 )
      RtlCopyFromUser(
        *(void **)(*((_QWORD *)v27 + 7) + 104LL),
        (void *)v17->pPrivateRuntimeData,
        v17->PrivateRuntimeDataSize);
    else
      memmove(*(void **)(*((_QWORD *)v27 + 7) + 104LL), v17->pPrivateRuntimeData, v17->PrivateRuntimeDataSize);
    if ( (*(_DWORD *)&v17->Flags & 0x100000) == 0 )
      goto LABEL_138;
    DestructionBuffers = CheckNoKmdAccessPrivateData(
                           v17->PrivateRuntimeDataSize,
                           *(void **)(*((_QWORD *)v27 + 7) + 104LL),
                           0xFF000004);
    v241 = DestructionBuffers;
    if ( DestructionBuffers < 0 )
      goto LABEL_316;
  }
  v80 = a3;
LABEL_138:
  if ( v17->pStandardAllocation )
  {
    v144 = v17->PrivateDriverDataSize;
    if ( (_DWORD)v144 )
    {
      v145 = *((_QWORD *)v27 + 7);
      if ( *(_QWORD *)(v145 + 120) )
      {
        v149 = *(_DWORD *)(v145 + 128);
        if ( v149 != (_DWORD)v144 )
        {
          DestructionBuffers = -1073741811;
          v241 = -1073741811;
          WdLogSingleEntry3(3, this, v144, v149);
          WdLogGlobalForLineNumber = 5770;
          goto LABEL_316;
        }
      }
      else
      {
        *(_QWORD *)(*((_QWORD *)v27 + 7) + 120LL) = operator new[]((unsigned int)v144, 1265072196, 258);
        v146 = *((_QWORD *)v27 + 7);
        v147 = v17->PrivateDriverDataSize;
        if ( !*(_QWORD *)(v146 + 120) )
        {
          DestructionBuffers = -1073741801;
          v241 = -1073741801;
          WdLogSingleEntry3(3, this, v147, -1073741801);
          WdLogGlobalForLineNumber = 5757;
          goto LABEL_316;
        }
        *(_DWORD *)(v146 + 128) = v147;
      }
      pStandardAllocation = v271;
      if ( !v80 )
        pStandardAllocation = v17->pStandardAllocation;
      memmove(*(void **)(*((_QWORD *)v27 + 7) + 120LL), pStandardAllocation, v17->PrivateDriverDataSize);
      if ( (*(_DWORD *)&v17->Flags & 0x100000) != 0 )
      {
        DestructionBuffers = CheckNoKmdAccessPrivateData(
                               v17->PrivateDriverDataSize,
                               *(void **)(*((_QWORD *)v27 + 7) + 120LL),
                               0xFF000001);
        v241 = DestructionBuffers;
        if ( DestructionBuffers < 0 )
          goto LABEL_316;
      }
    }
  }
  v81 = 0;
  v38 = v244;
  v82 = v244;
  v39 = v251;
  while ( 1 )
  {
    v262 = v82;
    v245 = (unsigned int)v81;
    if ( (unsigned int)v81 >= v39->NumAllocations )
      break;
    v260 = v81;
    v89 = (struct _D3DKMT_CREATESTANDARDALLOCATION *)(96LL * (_QWORD)v81);
    v257 = v89;
    if ( *(void **)((char *)&v23->pPrivateDriverData + (_QWORD)v89) )
    {
      v90 = operator new[](*(unsigned int *)((char *)&v23->PrivateDriverDataSize + (_QWORD)v89), 1265072196, 258);
      v91 = v262;
      *(_QWORD *)(*((_QWORD *)v262 + 6) + 32LL) = v90;
      v92 = *(void **)(*((_QWORD *)v91 + 6) + 32LL);
      if ( !v92 )
      {
        DestructionBuffers = -1073741801;
        v241 = -1073741801;
        WdLogSingleEntry4(
          3,
          this,
          v245 + 1,
          *(unsigned int *)((char *)&v23->PrivateDriverDataSize + (_QWORD)v257),
          -1073741801);
        WdLogGlobalForLineNumber = 5814;
        goto LABEL_316;
      }
      if ( !a3 || (*(_DWORD *)&v17->Flags & 0x10000) != 0 )
      {
        v93 = *(unsigned int *)((char *)&v23->PrivateDriverDataSize + (_QWORD)v257);
        v94 = *(void **)((char *)&v23->pPrivateDriverData + (_QWORD)v257);
      }
      else
      {
        v93 = *(unsigned int *)((char *)&v23->PrivateDriverDataSize + (_QWORD)v257);
        v94 = v256[(_QWORD)v260];
      }
      memmove(v92, v94, v93);
      *(_DWORD *)(*((_QWORD *)v262 + 6) + 40LL) = *(UINT *)((char *)&v23->PrivateDriverDataSize + (_QWORD)v257);
      v82 = v262;
      v39 = v251;
    }
    v81 = (struct COREDEVICEACCESS *)(v245 + 1);
    v82 = (struct DXGALLOCATION *)*((_QWORD *)v82 + 8);
  }
LABEL_40:
  v40 = *(struct DXGALLOCATION **)(*((_QWORD *)this + 2) + 16LL);
  v248 = v40;
  *(_QWORD *)v274 = v40;
  if ( !*((_BYTE *)v40 + 209) )
    goto LABEL_41;
  if ( a4 )
    goto LABEL_429;
  LODWORD(Object) = DXGPROCESS::GetHostProcess(*((DXGPROCESS **)v267 + 5));
  if ( !(_DWORD)Object )
  {
    DestructionBuffers = -1073741823;
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 5849;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Failed to get host adapter process, returning 0x%I64x",
      -1073741823,
      0,
      0,
      0,
      0);
LABEL_350:
    v241 = DestructionBuffers;
    goto LABEL_316;
  }
  v266 = 0;
  if ( !DXGDEVICE::UmdManagesResidency(this) || !v261 || (v150 = 1, (unsigned int)(*((_DWORD *)v261 + 4) - 1) > 2) )
    v150 = 0;
  v151 = v17->Flags;
  if ( (*(_BYTE *)&v151 & 2) != 0 )
    v152 = *(const void **)(*((_QWORD *)v27 + 7) + 104LL);
  else
    v152 = 0;
  v153 = v271;
  if ( a3 )
  {
    v154 = v256;
    if ( (*(_DWORD *)&v151 & 0x10000) == 0 )
      goto LABEL_362;
  }
  else
  {
    v153 = v17->pStandardAllocation;
  }
  v154 = v258;
LABEL_362:
  if ( (*(_BYTE *)&v151 & 2) != 0 )
    v155 = *((_DWORD *)v27 + 5);
  else
    v155 = 0;
  Allocation = DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendCreateAllocation(
                 (struct DXGALLOCATION *)((char *)v248 + 4776),
                 (unsigned int)Object,
                 *((_DWORD *)this + 118),
                 v155,
                 v17,
                 v23,
                 v154,
                 v153,
                 v152,
                 a3,
                 v150,
                 (unsigned __int8 **)&v266);
  LODWORD(Object) = Allocation;
  v157 = v244;
  if ( !v266 )
  {
    v158 = Allocation;
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 5879;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"VmBusSendCreateAllocation failed: 0x%I64x",
      v158,
      0,
      0,
      0,
      0);
    DestructionBuffers = (int)Object;
    goto LABEL_350;
  }
  v159 = v266;
  v257 = (struct _D3DKMT_CREATESTANDARDALLOCATION *)v266;
  if ( !v27 )
    goto LABEL_376;
  *((_DWORD *)v27 + 5) = *((_DWORD *)v266 + 1);
  v160 = v17->Flags;
  if ( (*(_BYTE *)&v160 & 2) == 0 )
    goto LABEL_376;
  v161 = v159[2];
  if ( (*(_BYTE *)&v160 & 0x40) != 0 )
  {
    if ( v161 )
    {
      WdLogSingleEntry0(1);
      v162 = 5894;
      v163 = L"NULL == pOutput->hGlobalSharedResource";
LABEL_374:
      WdLogGlobalForLineNumber = v162;
      DxgkLogInternalTriageEvent(0, 262146, -1, (_DWORD)v163, v162, 0, 0, 0, 0);
      v159 = v257;
    }
  }
  else if ( !v161 )
  {
    WdLogSingleEntry0(1);
    v162 = 5898;
    v163 = L"pOutput->hGlobalSharedResource";
    goto LABEL_374;
  }
  *(_DWORD *)(*((_QWORD *)v27 + 7) + 28LL) = v159[2];
LABEL_376:
  v278 = 0;
  if ( (*(_DWORD *)&v17->Flags & 2) != 0 && v27 )
    v278 = *(_QWORD **)(*((_QWORD *)v27 + 7) + 136LL);
  v164 = 0;
  v245 = 0;
  if ( v17->NumAllocations )
  {
    v165 = v157;
    do
    {
      *((_DWORD *)v165 + 32) = v159[3];
      v166 = v164;
      *((_DWORD *)v165 + 5) = v159[18 * v164 + 4];
      *((_BYTE *)v165 + 128) |= 4u;
      if ( (*(_DWORD *)&v251->Flags & 0x20020) != 0 && (*(_DWORD *)&v251->Flags & 2) != 0 )
        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v165 + 5) + 56LL) + 200LL) = v159[18 * v164 + 7];
      else
        *((_DWORD *)v165 + 31) = v159[18 * v164 + 7];
      if ( v159[3] & 1 | ((v159[3] & 2) != 0) )
      {
        *((_QWORD *)v165 + 13) = v23[v164].hSection;
        *((_BYTE *)v165 + 128) ^= (*((_BYTE *)v165 + 128) ^ (8 * (v159[18 * v164 + 6] >> 21))) & 8;
      }
      *(_DWORD *)(*((_QWORD *)v165 + 6) + 4LL) ^= (v159[18 * v164 + 6] ^ *(_DWORD *)(*((_QWORD *)v165 + 6) + 4LL)) & 1;
      *(_DWORD *)(*((_QWORD *)v165 + 6) + 4LL) ^= (v159[18 * v164 + 6] ^ *(_DWORD *)(*((_QWORD *)v165 + 6) + 4LL)) & 2;
      *(_DWORD *)(*((_QWORD *)v165 + 6) + 4LL) ^= (v159[18 * v164 + 6] ^ *(_DWORD *)(*((_QWORD *)v165 + 6) + 4LL)) & 4;
      *(_DWORD *)(*((_QWORD *)v165 + 6) + 4LL) ^= (v159[18 * v164 + 6] ^ *(_DWORD *)(*((_QWORD *)v165 + 6) + 4LL)) & 8;
      *(_DWORD *)(*((_QWORD *)v165 + 6) + 4LL) ^= (v159[18 * v164 + 6]
                                                 ^ *(_DWORD *)(*((_QWORD *)v165 + 6) + 4LL))
                                                & 0x20;
      *(_DWORD *)(*((_QWORD *)v165 + 6) + 4LL) ^= (v159[18 * v164 + 6]
                                                 ^ *(_DWORD *)(*((_QWORD *)v165 + 6) + 4LL))
                                                & 0x800;
      *(_DWORD *)(*((_QWORD *)v165 + 6) + 4LL) ^= (v159[18 * v164 + 6]
                                                 ^ *(_DWORD *)(*((_QWORD *)v165 + 6) + 4LL))
                                                & 0x1000;
      *(_DWORD *)(*((_QWORD *)v165 + 6) + 4LL) ^= (v159[18 * v164 + 6]
                                                 ^ *(_DWORD *)(*((_QWORD *)v165 + 6) + 4LL))
                                                & 0x2000;
      *(_DWORD *)(*((_QWORD *)v165 + 6) + 4LL) ^= (v159[18 * v164 + 6]
                                                 ^ *(_DWORD *)(*((_QWORD *)v165 + 6) + 4LL))
                                                & 0x4000;
      *(_DWORD *)(*((_QWORD *)v165 + 6) + 4LL) ^= (v159[18 * v164 + 6]
                                                 ^ *(_DWORD *)(*((_QWORD *)v165 + 6) + 4LL))
                                                & 0x40000;
      *(_DWORD *)(*((_QWORD *)v165 + 6) + 4LL) ^= (v159[18 * v164 + 6]
                                                 ^ *(_DWORD *)(*((_QWORD *)v165 + 6) + 4LL))
                                                & 0x80000;
      *(_DWORD *)(*((_QWORD *)v165 + 6) + 4LL) ^= (v159[18 * v164 + 6]
                                                 ^ *(_DWORD *)(*((_QWORD *)v165 + 6) + 4LL))
                                                & 0x100000;
      *(_DWORD *)(*((_QWORD *)v165 + 6) + 4LL) |= 0x20000u;
      v167 = v164;
      if ( (v23[v166].Flags.Value & 1) != 0 )
      {
        *(_DWORD *)(*((_QWORD *)v165 + 6) + 4LL) ^= ((unsigned __int16)*(_DWORD *)(*((_QWORD *)v165 + 6) + 4LL)
                                                   ^ (unsigned __int16)((unsigned __int16)v23[v167].VidPnSourceId << 6))
                                                  & 0x3C0;
        if ( *((_QWORD *)this + 237) != *(_QWORD *)(*((_QWORD *)this + 2) + 16LL) )
          *(_DWORD *)(*((_QWORD *)v165 + 6) + 4LL) |= 4u;
      }
      if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x1000) != 0 )
      {
        v168 = (*((_DWORD *)v165 + 18) >> 12) & 0x3F;
        v169 = *((_QWORD *)v165 + 6);
        v170 = *((_DWORD *)v165 + 30);
        v171 = *(_QWORD *)(*((_QWORD *)this + 2) + 16LL);
        CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
        McTemplateK0pppqxqqqqqqqpppqqqqqqqqqqtphtp_EtwWriteTransfer(
          v173,
          (unsigned int)EventCreateAdapterAllocation,
          v174,
          CurrentProcessId,
          (char)this,
          v171,
          0,
          v170,
          Src,
          v218,
          v219,
          v220,
          v221,
          v222,
          v223,
          v224,
          v169,
          v225,
          v226,
          v227,
          v228,
          v229,
          v230,
          v231,
          v232,
          v233,
          v234,
          v235,
          v236,
          v237,
          v168,
          0,
          0);
        v23 = v242;
        v159 = v257;
      }
      v164 = v245 + 1;
      v245 = v164;
      v165 = (struct DXGALLOCATION *)*((_QWORD *)v165 + 8);
    }
    while ( v164 < v251->NumAllocations );
    v17 = v251;
    v157 = v244;
  }
  if ( (int)Object < 0 )
  {
    DestructionBuffers = (int)Object;
    goto LABEL_350;
  }
  v175 = v157;
  v262 = v157;
  for ( n = 0; ; ++n )
  {
    v245 = n;
    if ( n >= v17->NumAllocations )
      break;
    v177 = v17->Flags;
    if ( (*(_DWORD *)&v177 & 0x10000) == 0 )
      goto LABEL_412;
    if ( (*(_BYTE *)&v177 & 0x20) != 0 )
    {
      v178 = (unsigned int *)v23[n].hSection;
      v279 = v178;
      v179 = (struct COREDEVICEACCESS *)(88LL * n);
      v260 = v179;
      if ( (*((_BYTE *)this + 1917) & 1) == 0 )
      {
        DestructionBuffers = ProcessSysMemAttributes(
                               v178,
                               v159[18 * n + 8],
                               (struct _DXGK_ALLOCATIONINFO *)((char *)v259 + (_QWORD)v179));
        v241 = DestructionBuffers;
        if ( DestructionBuffers < 0 )
          goto LABEL_316;
        v175 = v262;
        v179 = v260;
        v178 = v279;
      }
      if ( (*(_DWORD *)&v17->Flags & 2) != 0 )
      {
        v180 = *(_QWORD *)(*((_QWORD *)v175 + 5) + 56LL);
        *(_DWORD *)(v180 + 12) |= 0x200u;
        *(_QWORD *)(v180 + 192) = v178;
        v181 = v259;
        *(_DWORD *)(v180 + 204) = *(UINT *)((char *)&v259->Alignment + (_QWORD)v179);
        v182 = *(UINT *)((char *)&v181->Flags.Value + (_QWORD)v179);
LABEL_409:
        *(_DWORD *)(v180 + 12) ^= ((unsigned __int16)*(_DWORD *)(v180 + 12)
                                 ^ (unsigned __int16)((_WORD)v182 << 9))
                                & 0x800;
      }
    }
    else
    {
      if ( (*(_DWORD *)&v177 & 0x20000) != 0 )
      {
        v260 = (struct COREDEVICEACCESS *)(96LL * n);
        v263 = 0;
        v183 = ObReferenceObjectByHandle(
                 *(HANDLE *)((char *)&v23->hSection + (_QWORD)v260),
                 0x20000u,
                 MmSectionObjectType,
                 a3,
                 &v263,
                 0);
        DestructionBuffers = v183;
        v241 = v183;
        if ( v183 < 0 )
        {
          v184 = v183;
          v185 = v260;
          WdLogSingleEntry2(2, *(HANDLE *)((char *)&v23->hSection + (_QWORD)v260));
          WdLogGlobalForLineNumber = 6064;
          v186 = *(__int64 *)((char *)&v23->hSection + (_QWORD)v185);
          goto LABEL_406;
        }
        Object = v263;
        v260 = (struct COREDEVICEACCESS *)&v259[n];
        DestructionBuffers = ProcessSectionAttributes(v263, (struct _DXGK_ALLOCATIONINFO *)v260);
        v241 = DestructionBuffers;
        if ( DestructionBuffers < 0 )
        {
          WdLogSingleEntry2(2, this);
          WdLogGlobalForLineNumber = 6074;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Failed to query section attributes. Device=0x%I64x, Status=%I64X",
            (__int64)this,
            DestructionBuffers,
            0,
            0,
            0);
          ObfDereferenceObject(Object);
          goto LABEL_316;
        }
        v175 = v262;
        v180 = *(_QWORD *)(*((_QWORD *)v262 + 5) + 56LL);
        *(_DWORD *)(v180 + 12) |= 0x400u;
        *(_QWORD *)(v180 + 192) = Object;
        v187 = v260;
        *(_DWORD *)(v180 + 204) = *((_DWORD *)v260 + 3);
        v182 = *((_DWORD *)v187 + 16);
        goto LABEL_409;
      }
      if ( (*(_BYTE *)&v177 & 2) != 0 )
        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v175 + 5) + 56LL) + 12LL) ^= ((unsigned __int16)*(_DWORD *)(*(_QWORD *)(*((_QWORD *)v175 + 5) + 56LL) + 12LL)
                                                                        ^ (unsigned __int16)((unsigned __int16)*(_DWORD *)&v259[n].Flags.0 << 9))
                                                                       & 0x800;
    }
LABEL_412:
    v188 = n;
    v189 = (struct COREDEVICEACCESS *)(96LL * n);
    v260 = v189;
    if ( (*(UINT *)((_BYTE *)&v23->Flags.Value + (_QWORD)v189) & 1) != 0 )
    {
      Object = 0;
      DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v250, v175);
      DXGALLOCATIONREFERENCE::MoveAssign(&Object, &v250);
      DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v250);
      Resident = DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendMakeResident(
                   (DXG_GUEST_VIRTUALGPU_VMBUS *)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 4776LL),
                   *((_DWORD *)Current + 122),
                   *((_DWORD *)this + 118),
                   0,
                   (struct D3DDDI_MAKERESIDENT_FLAGS)3,
                   1u,
                   (const struct DXGALLOCATIONREFERENCE *)&Object,
                   0,
                   0);
      DestructionBuffers = Resident;
      v241 = Resident;
      if ( Resident < 0 )
      {
        v191 = Resident;
        WdLogSingleEntry1(2);
        WdLogGlobalForLineNumber = 6117;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"VmBusSendMakeResident failed: 0x%I64x",
          v191,
          0,
          0,
          0,
          0);
        DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&Object);
        goto LABEL_427;
      }
      DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&Object);
      v175 = v262;
      v189 = v260;
      v188 = n;
    }
    *(_QWORD *)(*((_QWORD *)v175 + 6) + 16LL) = *((_QWORD *)v175 + 6);
    v192 = *((_QWORD *)v175 + 6);
    v193 = 3 * v188;
    v194 = v257;
    *((_DWORD *)v175 + 30) = v257[v193 + 1].ExistingHeapData.Size;
    *(_QWORD *)(v192 + 112) = LODWORD(v194[v193 + 1].ExistingHeapData.Size);
    *(_OWORD *)(v192 + 64) = *(_OWORD *)&v194[v193 + 1].Flags.0;
    *(_OWORD *)(v192 + 80) = *(_OWORD *)&v194[v193 + 2].ExistingHeapData.Size;
    *(_OWORD *)(v192 + 96) = *(_OWORD *)&v194[v193 + 3].Type;
    v195 = *(unsigned int *)((char *)&v23->PrivateDriverDataSize + (_QWORD)v189);
    LODWORD(Object) = *(UINT *)((char *)&v23->PrivateDriverDataSize + (_QWORD)v189);
    if ( !a3 || (*(_DWORD *)&v17->Flags & 0x10000) != 0 )
    {
      v263 = (PVOID)(8LL * n);
      memmove(v23[n].pPrivateDriverData, *(const void **)((char *)v258 + (_QWORD)v263), v195);
    }
    else
    {
      v263 = (PVOID)(8LL * n);
      RtlCopyToUser(v23[n].pPrivateDriverData, *(void **)((char *)v256 + (_QWORD)v263), (unsigned int)v195);
    }
    v196 = v278;
    if ( v278 )
    {
      if ( !a3 || (v197 = v256, (*(_DWORD *)&v17->Flags & 0x10000) != 0) )
        v197 = v258;
      memmove((void *)*(v278 - 2), *(const void **)((char *)v197 + (_QWORD)v263), (unsigned int)Object);
      v278 = (_QWORD *)*v196;
    }
    v159 = v257;
    v175 = (struct _EPROCESS *)*((_QWORD *)v262 + 8);
    v262 = v175;
  }
  DestructionBuffers = v241;
LABEL_427:
  DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v266);
  if ( DestructionBuffers < 0 )
    goto LABEL_316;
  v38 = v244;
  v40 = v248;
  v39 = v251;
LABEL_429:
  if ( *((_BYTE *)v40 + 209) )
  {
    if ( !a4 )
    {
      if ( bTracingEnabled )
      {
        v198 = v38;
        v248 = v38;
        v199 = 0;
        LODWORD(Object) = 0;
        if ( v17->NumAllocations )
        {
          do
          {
            if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x1000) != 0 )
            {
              v245 = *((_DWORD *)v198 + 5);
              v200 = *((_QWORD *)v198 + 5);
              v280 = (const struct _D3DKM_CREATESTANDARDALLOCATION *)v200;
              if ( v200 )
                v250 = *(PVOID *)(v200 + 48);
              else
                v250 = 0;
              if ( v200 )
                v263 = (PVOID)*(unsigned int *)(v200 + 16);
              else
                v263 = 0;
              *(_QWORD *)v274 = *((unsigned int *)v198 + 4);
              if ( v200 )
                v266 = *(struct _DXGSHAREDALLOCOBJECT **)(v200 + 56);
              else
                v266 = 0;
              v201 = *(_QWORD *)(*((_QWORD *)this + 2) + 16LL);
              v202 = (unsigned int)PsGetCurrentProcessId();
              McTemplateK0ppppppppppppq_EtwWriteTransfer(
                (_DWORD)v248,
                (unsigned int)EventCreateDeviceAllocation,
                v203,
                v202,
                (char)this,
                v201,
                (char)v248,
                v216,
                (char)v280,
                (char)v266,
                v274[0],
                (char)v263,
                (char)v250,
                v222,
                v223,
                v245);
              v198 = v248;
              v199 = (unsigned int)Object;
              v39 = v251;
            }
            LODWORD(Object) = ++v199;
            v198 = (struct DXGALLOCATION *)*((_QWORD *)v198 + 8);
            v248 = v198;
          }
          while ( v199 < v39->NumAllocations );
        }
      }
    }
  }
LABEL_41:
  v41 = v17->Flags;
  if ( (*(_WORD *)&v41 & 0x800) == 0 )
  {
    v42 = v244;
    if ( (*(_WORD *)&v41 & 0x1000) == 0 )
      goto LABEL_43;
    v43 = v261;
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, struct DXGALLOCATION *))(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 760LL)
                                                                                       + 8LL)
                                                                           + 720LL))(
      *(_QWORD *)(*((_QWORD *)this + 2) + 768LL),
      *((_QWORD *)v244 + 3),
      *((_QWORD *)v261 + 43),
      v32);
    goto LABEL_44;
  }
  memset(&v283, 0, sizeof(v283));
  v283.hAllocation = *(HANDLE *)(*((_QWORD *)v38 + 6) + 16LL);
  v204 = ADAPTER_RENDER::DdiDescribeAllocation(*((ADAPTER_RENDER **)this + 2), &v283);
  DestructionBuffers = v204;
  v241 = v204;
  if ( v204 < 0 )
  {
    v42 = v244;
    WdLogSingleEntry4(3, v204, this, *((unsigned int *)v244 + 4), v244);
    WdLogGlobalForLineNumber = 6222;
    goto LABEL_46;
  }
  if ( v283.Format == D3DDDIFMT_UNKNOWN && v283.Height != 1 )
  {
    WdLogSingleEntry3(3, -1073741811, this, v283.Height);
    WdLogGlobalForLineNumber = 6230;
    DestructionBuffers = -1073741811;
    goto LABEL_350;
  }
  v205 = v244;
  if ( (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)v244 + 5) + 56LL) + 12LL) & 0x20) == 0 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 6237;
    DxgkLogInternalTriageEvent(
      0,
      262146,
      -1,
      (unsigned int)L"pAllocationObjectList->m_pOwningResource->m_pSharedResource->m_CrossAdapter",
      6237,
      0,
      0,
      0,
      0);
  }
  v206 = *(_QWORD *)(*((_QWORD *)v205 + 5) + 56LL);
  *(_QWORD *)v274 = v206;
  *(_DWORD *)(v206 + 208) = v283.Width;
  *(_DWORD *)(v206 + 212) = v283.Height;
  *(_DWORD *)(v206 + 216) = v283.Format;
  v207 = v17->Flags;
  if ( (*((_BYTE *)this + 1917) & 1) == 0 )
  {
    if ( (*(_BYTE *)&v207 & 0x20) == 0 )
    {
      *(_QWORD *)(v206 + 192) = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 760LL)
                                                                              + 8LL)
                                                                  + 640LL))(*((_QWORD *)v205 + 3));
      *(_DWORD *)(v206 + 12) |= 0x400u;
    }
    *(_QWORD *)(v206 + 224) = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 2)
                                                                                                + 760LL)
                                                                                    + 8LL)
                                                                        + 712LL))(
                                *(_QWORD *)(*((_QWORD *)this + 2) + 768LL),
                                *((_QWORD *)v205 + 3));
    goto LABEL_459;
  }
  if ( (*(_DWORD *)&v207 & 0x20000) != 0 )
  {
    v250 = 0;
    v208 = ObReferenceObjectByHandle(v23->hSection, 0x20000u, MmSectionObjectType, a3, &v250, 0);
    *(_QWORD *)(v206 + 192) = v250;
    DestructionBuffers = v208;
    v241 = v208;
    if ( v208 >= 0 )
    {
      v206 = *(_QWORD *)v274;
      *(_DWORD *)(*(_QWORD *)v274 + 12LL) |= 0x400u;
      goto LABEL_459;
    }
    v184 = v208;
    WdLogSingleEntry2(2, v23->hSection);
    WdLogGlobalForLineNumber = 6274;
    v186 = (__int64)v23->hSection;
LABEL_406:
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Failed to take a reference on hSection:0x%I64x, returning 0x%I64x",
      v186,
      v184,
      0,
      0,
      0);
LABEL_316:
    v42 = v244;
    goto LABEL_46;
  }
LABEL_459:
  v209 = VidPnSourceId;
  *(_DWORD *)(v206 + 232) = VidPnSourceId;
  v42 = v244;
  if ( v209 != -1 )
  {
    *(_DWORD *)(v206 + 12) |= 0x40u;
    *(_DWORD *)(v206 + 12) ^= ((unsigned __int8)*(_DWORD *)(v206 + 12)
                             ^ (unsigned __int8)(*(_DWORD *)&v17->Flags >> 3))
                            & 0x80;
  }
LABEL_43:
  v43 = v261;
LABEL_44:
  *(_QWORD *)v274 = *((_QWORD *)this + 2);
  if ( DXGADAPTER::IsGpuVirtualAddressingSupported(*(DXGADAPTER **)(*(_QWORD *)v274 + 16LL))
    && v43
    && (*(_DWORD *)v43 & 0x200) == 0 )
  {
    memset(&v286, 0, sizeof(v286));
    v286.Protection.Value = 1;
    v95 = 0;
    v96 = v42;
    DestructionBuffers = v241;
    while ( 1 )
    {
      v248 = v96;
      LODWORD(Object) = v95;
      if ( v95 >= v251->NumAllocations )
        break;
      v97 = (*((_DWORD *)v96 + 18) >> 12) & 0x3F;
      if ( *((_DWORD *)v261 + 4) == 4 )
      {
        v120 = *(_DWORD *)(*((_QWORD *)v261 + 3) + 12LL);
        if ( ((v120 - 1) & 0xFFFFFFFC) != 0 || v120 == 2 )
        {
          if ( DXGADAPTER::ReplicateGdiContent(*(DXGADAPTER **)(*((_QWORD *)this + 2) + 16LL)) )
            v97 = -1;
          v96 = v248;
        }
      }
      if ( v240 )
      {
        v98 = DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendMapGpuVirtualAddress(
                (DXG_GUEST_VIRTUALGPU_VMBUS *)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 4776LL),
                *((_DWORD *)Current + 122),
                this,
                0,
                *((_DWORD *)v96 + 5),
                &v286);
      }
      else
      {
        LOBYTE(v215) = 0;
        v98 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, struct D3DDDI_MAPGPUVIRTUALADDRESS *, int, int))(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v274 + 760LL) + 8LL) + 752LL))(
                *(_QWORD *)(*(_QWORD *)v274 + 768LL),
                0,
                *((_QWORD *)v96 + 3),
                &v286,
                v215,
                v97);
      }
      DestructionBuffers = v98;
      v241 = v98;
      if ( v98 < 0 )
      {
        WdLogSingleEntry1(3);
        WdLogGlobalForLineNumber = 6375;
        break;
      }
      v99 = DXGADAPTER::ReplicateGdiContent(*(DXGADAPTER **)(*((_QWORD *)this + 2) + 16LL));
      BaseAddress = v286.BaseAddress;
      if ( v99 )
        BaseAddress = v286.VirtualAddress;
      v286.BaseAddress = BaseAddress;
      v286.VirtualAddress = 0;
      v95 = (_DWORD)Object + 1;
      v96 = (struct DXGALLOCATION *)*((_QWORD *)v248 + 8);
    }
  }
  else
  {
    DestructionBuffers = v241;
  }
LABEL_46:
  v27 = v246;
LABEL_47:
  v44 = v242;
  if ( v282 )
  {
    v282 = 0;
    DXGFASTMUTEX::Release(v281);
  }
  DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v285);
  if ( DestructionBuffers >= 0 )
  {
    if ( v42 )
    {
      LODWORD(Object) = 0;
      if ( v17->NumAllocations )
      {
        v65 = v244;
        v66 = v267;
        v67 = v251;
        do
        {
          v68 = *((_QWORD *)v66 + 5);
          v69 = *((unsigned int *)v65 + 4);
          v70 = (DXGPUSHLOCK *)(v68 + 248);
          VidPnSourceId = (*((_DWORD *)v65 + 4) >> 6) & 0xFFFFFF;
          if ( (*((_DWORD *)Current + 102) & 0x100) != 0 )
          {
            DXGPUSHLOCK::AcquireExclusive(v70);
            if ( VidPnSourceId < *(_DWORD *)(v68 + 296) )
            {
              v107 = *(_QWORD *)(v68 + 280);
              if ( (((unsigned int)v69 >> 25) & 0x60) == (*(_BYTE *)(v107 + 16LL * VidPnSourceId + 8) & 0x60)
                && (*(_DWORD *)(v107 + 16LL * VidPnSourceId + 8) & 0x1F) != 0 )
              {
                v108 = 16 * ((v69 >> 6) & 0xFFFFFF);
                if ( (*(_DWORD *)(v107 + v108 + 8) & 0x2000) == 0 )
                {
                  WdLogSingleEntry0(1);
                  WdLogGlobalForLineNumber = 224;
                  DxgkLogInternalTriageEvent(
                    0,
                    262146,
                    -1,
                    (unsigned int)L"m_pEntryTable[GetIndex(hObject)].Destroyed",
                    224,
                    0,
                    0,
                    0,
                    0);
                }
                *(_DWORD *)(*(_QWORD *)(v68 + 280) + v108 + 8) &= ~0x2000u;
              }
            }
          }
          else
          {
            DXGPUSHLOCK::AcquireExclusive(v70);
            v71 = VidPnSourceId;
            if ( VidPnSourceId < *(_DWORD *)(v68 + 296) )
            {
              v72 = *(_QWORD *)(v68 + 280);
              if ( (((unsigned int)v69 >> 25) & 0x60) == (*(_BYTE *)(v72 + 16LL * VidPnSourceId + 8) & 0x60)
                && (*(_DWORD *)(v72 + 16LL * VidPnSourceId + 8) & 0x1F) != 0 )
              {
                v73 = 16 * ((v69 >> 6) & 0xFFFFFF);
                if ( (*(_DWORD *)(v72 + v73 + 8) & 0x2000) == 0 )
                {
                  WdLogSingleEntry0(1);
                  WdLogGlobalForLineNumber = 224;
                  DxgkLogInternalTriageEvent(
                    0,
                    262146,
                    -1,
                    (unsigned int)L"m_pEntryTable[GetIndex(hObject)].Destroyed",
                    224,
                    0,
                    0,
                    0,
                    0);
                  v71 = VidPnSourceId;
                }
                *(_DWORD *)(*(_QWORD *)(v68 + 280) + v73 + 8) &= ~0x2000u;
              }
              if ( v71 < *(_DWORD *)(v68 + 296) )
                *(_DWORD *)(16LL * v71 + *(_QWORD *)(v68 + 280) + 8) &= ~0x4000u;
            }
          }
          *(_QWORD *)(v68 + 256) = 0;
          ExReleasePushLockExclusiveEx(v68 + 248, 0);
          KeLeaveCriticalRegion();
          LODWORD(Object) = (_DWORD)Object + 1;
          v65 = (struct DXGALLOCATION *)*((_QWORD *)v65 + 8);
        }
        while ( (unsigned int)Object < v67->NumAllocations );
        v17 = v265;
        v27 = v246;
        DestructionBuffers = v241;
        v44 = v242;
      }
    }
    if ( v243[0] )
      DXGPROCESS::CommitResourceHandleSafe(*((DXGPROCESS **)v267 + 5), v27);
    goto LABEL_53;
  }
  if ( v42 )
  {
    if ( !a4 )
    {
      v101 = 0;
      LODWORD(Object) = 0;
      if ( v17->NumAllocations )
      {
        v102 = v42;
        v103 = v251;
        do
        {
          v104 = *((_QWORD *)v102 + 6);
          if ( *(_QWORD *)(v104 + 8) )
          {
            if ( (v105 = *(_DWORD *)(v104 + 4), (v105 & 1) != 0) && !*((_DWORD *)this + 116) || (v105 & 2) != 0 )
            {
              if ( (v105 & 0x10) != 0 )
              {
                WdLogSingleEntry0(1);
                WdLogGlobalForLineNumber = 6458;
                DxgkLogInternalTriageEvent(
                  0,
                  262146,
                  -1,
                  (unsigned int)L"!pAllocation->m_pAllocation->m_Invalidated",
                  6458,
                  0,
                  0,
                  0,
                  0);
              }
              VIDMM_EXPORT::VidMmInvalidateAllocation(
                *(VIDMM_EXPORT **)(*((_QWORD *)this + 2) + 760LL),
                *(struct VIDMM_GLOBAL **)(*((_QWORD *)this + 2) + 768LL),
                *(struct VIDMM_MULTI_GLOBAL_ALLOC **)(*((_QWORD *)v102 + 6) + 8LL));
              *(_DWORD *)(*((_QWORD *)v102 + 6) + 4LL) |= 0x10u;
              v101 = (unsigned int)Object;
            }
          }
          LODWORD(Object) = ++v101;
          v102 = (struct DXGALLOCATION *)*((_QWORD *)v102 + 8);
        }
        while ( v101 < v103->NumAllocations );
        v17 = v265;
        v27 = v246;
        v44 = v242;
      }
    }
  }
  if ( v243[0] )
  {
    DXGRESOURCEREFERENCE::DXGRESOURCEREFERENCE((DXGRESOURCEREFERENCE *)&v250, 0);
    DXGRESOURCEREFERENCE::MoveAssign(&v275, &v250);
    DXGRESOURCEREFERENCE::~DXGRESOURCEREFERENCE((DXGRESOURCEREFERENCE *)&v250);
    DXGDEVICE::RemoveResourceFromDeviceList(this, v27);
    goto LABEL_484;
  }
  if ( v42 )
  {
    if ( v249 )
      DXGDEVICE::RemoveAllocationsWithoutDestroy(this, v27, v42, v17->NumAllocations);
    if ( !v27 || *((_QWORD *)v27 + 7) )
    {
      v114 = v42;
      v267 = v42;
      do
      {
        v115 = (struct DXGALLOCATION *)*((_QWORD *)v114 + 8);
        *(_QWORD *)v274 = v115;
        *((_QWORD *)v114 + 7) = 0;
        *((_QWORD *)v114 + 8) = 0;
        if ( v27 )
        {
          v210 = *((_QWORD *)v27 + 7);
          if ( v210 )
          {
            if ( *(_QWORD *)(*((_QWORD *)v114 + 6) + 48LL) )
            {
              DXGPUSHLOCK::AcquireExclusive((DXGPUSHLOCK *)(v210 + 32));
              --*(_DWORD *)(*((_QWORD *)v27 + 7) + 132LL);
              v109 = v267;
              v110 = *((_QWORD *)v267 + 6) + 48LL;
              v111 = *(_QWORD *)v110;
              if ( *(_QWORD *)(*(_QWORD *)v110 + 8LL) != v110
                || (v112 = *(_QWORD **)(*((_QWORD *)v267 + 6) + 56LL), *v112 != v110) )
              {
                __fastfail(3u);
              }
              *v112 = v111;
              *(_QWORD *)(v111 + 8) = v112;
              *(_QWORD *)(*((_QWORD *)v109 + 6) + 48LL) = 0;
              v113 = *((_QWORD *)v27 + 7);
              *(_QWORD *)(v113 + 40) = 0;
              ExReleasePushLockExclusiveEx(v113 + 32, 0);
              KeLeaveCriticalRegion();
              v114 = v267;
              v115 = *(struct DXGALLOCATION **)v274;
            }
          }
        }
        v267 = v115;
        DXGDEVICE::DestroyAllocations(this, 0, 0, v114, 0, (struct _D3DDDICB_DESTROYALLOCATION2FLAGS)1);
        v114 = v267;
      }
      while ( v267 );
    }
    if ( v27 )
    {
      v211 = *((_QWORD *)v27 + 7);
      if ( !v211 )
      {
        DXGDEVICE::DestroyAllocations(this, v27, 0, v42, 0, (struct _D3DDDICB_DESTROYALLOCATION2FLAGS)1);
        goto LABEL_53;
      }
      v212 = 0;
      DXGPUSHLOCK::AcquireExclusive((DXGPUSHLOCK *)(v211 + 32));
      v213 = *((_DWORD *)v27 + 1);
      if ( (v213 & 0x10) == 0 )
      {
        *((_DWORD *)v27 + 1) = v213 | 0x10;
        v212 = 1;
      }
      v214 = *((_QWORD *)v27 + 7);
      *(_QWORD *)(v214 + 40) = 0;
      ExReleasePushLockExclusiveEx(v214 + 32, 0);
      KeLeaveCriticalRegion();
      if ( v212 )
      {
        DXGDEVICE::RemoveResourceFromDeviceList(this, v27);
        DXGHANDLETABLELOCKEXCLUSIVE::DXGHANDLETABLELOCKEXCLUSIVE((DXGHANDLETABLELOCKEXCLUSIVE *)&v283, Current);
        DXGPROCESS::GetResourceUnsafe(Current, &v248, *((unsigned int *)v27 + 4));
        if ( v248 )
        {
          v116 = *((unsigned int *)v248 + 4);
          v117 = (*((_DWORD *)v248 + 4) >> 6) & 0xFFFFFF;
          if ( (unsigned int)v117 < *((_DWORD *)Current + 74) )
          {
            v118 = *((_QWORD *)Current + 35);
            v119 = *(_DWORD *)(v118 + 16 * v117 + 8);
            if ( (((unsigned int)v116 >> 25) & 0x60) == (*(_BYTE *)(v118 + 16 * v117 + 8) & 0x60)
              && (v119 & 0x2000) == 0
              && (v119 & 0x1F) != 0 )
            {
              *(_DWORD *)(16 * ((v116 >> 6) & 0xFFFFFF) + v118 + 8) |= 0x2000u;
            }
          }
          DXGRESOURCEREFERENCE::DXGRESOURCEREFERENCE((DXGRESOURCEREFERENCE *)&v250, 0);
          DXGRESOURCEREFERENCE::MoveAssign(&v275, &v250);
          DXGRESOURCEREFERENCE::~DXGRESOURCEREFERENCE((DXGRESOURCEREFERENCE *)&v250);
        }
        else
        {
          v212 = 0;
        }
        DXGRESOURCEREFERENCE::~DXGRESOURCEREFERENCE((DXGRESOURCEREFERENCE *)&v248);
        DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)&v283);
        if ( v212 )
LABEL_484:
          DXGDEVICE::DestroyResource(this, v27, 0, (struct _D3DDDICB_DESTROYALLOCATION2FLAGS)1);
      }
    }
  }
LABEL_53:
  v45 = 0;
  v46 = v258;
  if ( v17->NumAllocations )
  {
    v53 = v251;
    do
      DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v46[v45++]);
    while ( v45 < v53->NumAllocations );
    v44 = v242;
  }
  DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v271);
  if ( v17->NumAllocations > 5 )
  {
    DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v44);
    DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v259);
    DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v272);
    DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v46);
    DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v256);
  }
  DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v285);
  DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX((DXGPROCESSCOPYPROTECTIONMUTEX *)&v281);
  DXGRESOURCEREFERENCE::~DXGRESOURCEREFERENCE((DXGRESOURCEREFERENCE *)&v275);
  if ( Entry )
    ExFreeToPagedLookasideList(v284 + 13, Entry);
  return (unsigned int)DestructionBuffers;
}

```

## disassembly

```asm
0x140377040  push    rbx
0x140377042  push    rsi
0x140377043  push    rdi
0x140377044  push    r12
0x140377046  push    r13
0x140377048  push    r14
0x14037704a  push    r15
0x14037704c  sub     rsp, 350h
0x140377053  mov     rax, cs:__security_cookie
0x14037705a  xor     rax, rsp
0x14037705d  mov     [rsp+388h+var_48], rax
0x140377065  mov     r14b, r9b
0x140377068  mov     [rsp+388h+var_277], r9b
0x140377070  mov     bl, r8b
0x140377073  mov     [rsp+388h+AccessMode], bl
0x14037707a  mov     r12, rdx
0x14037707d  mov     [rsp+388h+var_1B0], rdx
0x140377085  mov     r13, rcx
0x140377088  mov     rcx, [rsp+388h+arg_28]
0x140377090  mov     [rsp+388h+var_1D0], rcx
0x140377098  mov     [rsp+388h+var_168], r13
0x1403770a0  mov     [rsp+388h+var_188], rdx
0x1403770a8  mov     [rsp+388h+var_210], bl
0x1403770af  mov     [rsp+388h+var_270], r9b
0x1403770b7  mov     rax, [rsp+388h+arg_20]
0x1403770bf  mov     [rsp+388h+var_1A8], rax
0x1403770c7  mov     [rsp+388h+var_128], rcx
0x1403770cf  mov     rax, [rsp+388h+arg_30]
0x1403770d7  mov     [rsp+388h+var_1D8], rax
0x1403770df  mov     rax, [rsp+388h+arg_40]
0x1403770e7  mov     [rsp+388h+var_1C8], rax
0x1403770ef  mov     rax, [rsp+388h+arg_48]
0x1403770f7  mov     [rsp+388h+var_130], rax
0x1403770ff  mov     rax, [rsp+388h+arg_50]
0x140377107  mov     [rsp+388h+Object], rax
0x14037710f  mov     rax, [rsp+388h+arg_58]
0x140377117  mov     [rsp+388h+var_1C0], rax
0x14037711f  mov     rax, [rsp+388h+arg_60]
0x140377127  mov     [rsp+388h+var_1F0], rax
0x14037712f  mov     rcx, [r13+10h]; this
0x140377133  call    ?IsCoreResourceSharedOwner@ADAPTER_RENDER@@QEBAEXZ; ADAPTER_RENDER::IsCoreResourceSharedOwner(void)
0x140377138  xor     r15d, r15d
0x14037713b  test    al, al
0x14037713d  jz      loc_140378793
0x140377143  lea     esi, [r15+1]
0x140377147  mov     edi, 0FFFFFFFFh
0x14037714c  test    bl, bl
0x14037714e  jnz     loc_1403787EA
0x140377154  mov     rax, [r13+10h]
0x140377158  mov     rcx, [rax+10h]
0x14037715c  mov     al, [rcx+0D1h]
0x140377162  mov     [rsp+388h+var_276], al
0x140377169  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x14037716e  mov     [rsp+388h+var_200], rax
0x140377176  mov     edx, [r12+38h]
0x14037717b  bt      edx, 0Bh
0x14037717f  jb      loc_140378840
0x140377185  mov     rcx, [r13+10h]
0x140377189  mov     [rsp+388h+var_220], rcx
0x140377191  mov     eax, [r12+2Ch]
0x140377196  cmp     eax, 5
0x140377199  ja      loc_1403788BB
0x14037719f  add     rcx, 680h; Lookaside
0x1403771a6  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1403771ad  nop     dword ptr [rax+rax+00h]
0x1403771b2  mov     r14, rax
0x1403771b5  mov     [rsp+388h+var_260], rax
0x1403771bd  test    rax, rax
0x1403771c0  jz      loc_140378B76
0x1403771c6  mov     [rsp+388h+Entry], rax
0x1403771ce  add     rax, 2D0h
0x1403771d4  mov     [rsp+388h+var_1E0], rax
0x1403771dc  lea     rax, [r14+1E0h]
0x1403771e3  mov     [rsp+388h+var_170], rax
0x1403771eb  lea     rdx, [r14+280h]
0x1403771f2  mov     [rsp+388h+var_1E8], rdx
0x1403771fa  lea     r8, [r14+2A8h]
0x140377201  mov     [rsp+388h+var_1F8], r8
0x140377209  mov     [rsp+388h+var_198], r14
0x140377211  mov     [rsp+388h+var_218], r12
0x140377219  mov     rax, [rsp+388h+var_220]
0x140377221  mov     [rsp+388h+var_E0], rax
0x140377229  mov     [rsp+388h+var_1A0], r13
0x140377231  mov     rax, [rsp+388h+var_200]
0x140377239  mov     [rsp+388h+var_190], rax
0x140377241  mov     [rsp+388h+var_178], r15
0x140377249  mov     eax, r15d
0x14037724c  cmp     [r12+2Ch], r15d
0x140377251  ja      loc_140377B82
0x140377257  mov     rax, r15
0x14037725a  mov     [rsp+388h+var_250], rax
0x140377262  mov     [rsp+388h+var_1B8], rax
0x14037726a  mov     [rsp+388h+var_258], r15b
0x140377272  mov     rbx, r15
0x140377275  mov     [rsp+388h+var_240], rbx
0x14037727d  mov     [rsp+388h+var_228], r15b
0x140377285  mov     [rsp+388h+var_150], r15
0x14037728d  lea     rcx, [rsp+388h+var_120]; this
0x140377295  call    ??0DXGSYNCOBJECTMUTEX@@QEAA@XZ; DXGSYNCOBJECTMUTEX::DXGSYNCOBJECTMUTEX(void)
0x14037729a  xor     r8d, r8d; bool
0x14037729d  xor     edx, edx; struct DXGPUSHLOCK *
0x14037729f  lea     rcx, [rsp+388h+var_D8]; this
0x1403772a7  call    ??0DXGAUTOPUSHLOCK@@QEAA@QEAVDXGPUSHLOCK@@_N@Z; DXGAUTOPUSHLOCK::DXGAUTOPUSHLOCK(DXGPUSHLOCK * const,bool)
0x1403772ac  cmp     [rsp+388h+AccessMode], r15b
0x1403772b4  jnz     loc_140378BDB
0x1403772ba  mov     eax, [r12+2Ch]
0x1403772bf  lea     r8, [rax+rax*2]
0x1403772c3  shl     r8, 5; Size
0x1403772c7  mov     rdx, [r12+30h]; Src
0x1403772cc  mov     rcx, r14; void *
0x1403772cf  call    memmove
0x1403772d4  mov     r9b, [rsp+388h+var_276]
0x1403772dc  mov     [rsp+388h+var_204], r9b
0x1403772e4  mov     [rsp+388h+var_208], edi
0x1403772eb  test    dword ptr [r12+38h], 10000h
0x1403772f4  jnz     loc_140378C8D
0x1403772fa  mov     edx, r15d
0x1403772fd  mov     [rsp+388h+var_248], edx
0x140377304  cmp     edx, [r12+2Ch]
0x140377309  jb      loc_14037766D
0x14037730f  mov     edi, r15d
0x140377312  cmp     edi, [r12+2Ch]
0x140377317  jb      loc_1403776CA
0x14037731d  cmp     [rsp+388h+AccessMode], r15b
0x140377325  jnz     loc_1403780A5
0x14037732b  lea     rax, [rsp+388h+var_D8]
0x140377333  mov     [rsp+388h+var_338], rax; struct DXGAUTOPUSHLOCK *
0x140377338  lea     rax, [rsp+388h+var_120]
0x140377340  mov     [rsp+388h+var_340], rax; struct DXGAUTOMUTEX *
0x140377345  mov     rax, [rsp+388h+var_1D0]
0x14037734d  mov     [rsp+388h+Src], rax; struct _D3DKM_CREATESTANDARDALLOCATION *
0x140377352  lea     rax, [rsp+388h+var_258]
0x14037735a  mov     [rsp+388h+var_350], rax; unsigned __int8 *
0x14037735f  lea     rax, [rsp+388h+var_150]
0x140377367  mov     [rsp+388h+var_358], rax; struct DXGRESOURCEREFERENCE *
0x14037736c  mov     rax, [rsp+388h+var_1A8]
0x140377374  mov     [rsp+388h+HandleInformation], rax; struct _DXGSHAREDALLOCOBJECT *
0x140377379  mov     rax, [rsp+388h+var_1C8]
0x140377381  mov     qword ptr [rsp+388h+var_368], rax; struct _EPROCESS *
0x140377386  mov     r9b, [rsp+388h+var_277]; unsigned __int8
0x14037738e  mov     r8, r14; struct _D3DDDI_ALLOCATIONINFO2 *
0x140377391  mov     rdx, r12; struct _D3DKMT_CREATEALLOCATION *
0x140377394  mov     rcx, r13; this
0x140377397  call    ?OpenResourceObject@DXGDEVICE@@QEAAJPEAU_D3DKMT_CREATEALLOCATION@@PEAU_D3DDDI_ALLOCATIONINFO2@@EPEAU_EPROCESS@@PEAU_DXGSHAREDALLOCOBJECT@@PEAVDXGRESOURCEREFERENCE@@PEAEPEBU_D3DKM_CREATESTANDARDALLOCATION@@PEAVDXGAUTOMUTEX@@PEAVDXGAUTOPUSHLOCK@@@Z; DXGDEVICE::OpenResourceObject(_D3DKMT_CREATEALLOCATION *,_D3DDDI_ALLOCATIONINFO2 *,uchar,_EPROCESS *,_DXGSHAREDALLOCOBJECT *,DXGRESOURCEREFERENCE *,uchar *,_D3DKM_CREATESTANDARDALLOCATION const *,DXGAUTOMUTEX *,DXGAUTOPUSHLOCK *)
0x14037739c  mov     edi, eax
0x14037739e  mov     [rsp+388h+var_268], rdi
0x1403773a6  test    eax, eax
0x1403773a8  js      loc_140379124
0x1403773ae  mov     rbx, [rsp+388h+var_150]
0x1403773b6  mov     [rsp+388h+var_240], rbx
0x1403773be  test    rbx, rbx
0x1403773c1  jnz     loc_140378004
0x1403773c7  movzx   r9d, [rsp+388h+var_258]; int
0x1403773d0  mov     r8, rbx; struct DXGRESOURCE *
0x1403773d3  mov     edx, [r12+2Ch]; unsigned int
0x1403773d8  mov     rcx, r13; this
0x1403773db  call    ?CreateDestructionBuffers@DXGDEVICE@@QEAAJIPEAVDXGRESOURCE@@H@Z; DXGDEVICE::CreateDestructionBuffers(uint,DXGRESOURCE *,int)
0x1403773e0  mov     edi, eax
0x1403773e2  mov     [rsp+388h+var_268], rdi
0x1403773ea  test    eax, eax
0x1403773ec  js      loc_140379124
0x1403773f2  mov     [rsp+388h+var_230], r15
0x1403773fa  lea     rax, [rsp+388h+var_230]
0x140377402  mov     qword ptr [rsp+388h+var_368], rax; struct DXGALLOCATION **
0x140377407  mov     r9, rbx; struct DXGRESOURCE *
0x14037740a  lea     r8, [rsp+388h+var_1B8]; struct DXGALLOCATION **
0x140377412  mov     edx, [r12+2Ch]; unsigned int
0x140377417  mov     rcx, r13; this
0x14037741a  call    ?CreateAllocationObjects@DXGDEVICE@@QEAAJIPEAPEAVDXGALLOCATION@@PEAVDXGRESOURCE@@0@Z; DXGDEVICE::CreateAllocationObjects(uint,DXGALLOCATION * *,DXGRESOURCE *,DXGALLOCATION * *)
0x14037741f  mov     edi, eax
0x140377421  mov     [rsp+388h+var_268], rdi
0x140377429  test    eax, eax
0x14037742b  js      loc_14037A746
0x140377431  mov     r9, [rsp+388h+var_230]; struct DXGALLOCATION *
0x140377439  mov     rax, [rsp+388h+var_1B8]
0x140377441  mov     [rsp+388h+var_250], rax
0x140377449  test    r9, r9
0x14037744c  jnz     loc_140377CFC
0x140377452  mov     eax, [r12+38h]
0x140377457  bt      eax, 0Bh
0x14037745b  jb      loc_140379157
0x140377461  bt      eax, 0Ch
0x140377465  jb      loc_140379196
0x14037746b  test    rbx, rbx
0x14037746e  jnz     loc_140378081
0x140377474  cmp     [rsp+388h+var_276], r15b
0x14037747c  jz      loc_14037776A
0x140377482  cmp     [rsp+388h+var_258], r15b
0x14037748a  jnz     loc_1403779B4
0x140377490  mov     eax, r15d
0x140377493  test    rbx, rbx
0x140377496  jnz     loc_140379360
0x14037749c  mov     [r12+4], eax
0x1403774a1  mov     eax, [r12+38h]
0x1403774a6  test    al, 2
0x1403774a8  jz      loc_140379368
0x1403774ae  test    al, 40h
0x1403774b0  jz      loc_14037937B
0x1403774b6  mov     ecx, r15d
0x1403774b9  mov     [r12+8], ecx
0x1403774be  cmp     [rsp+388h+AccessMode], r15b
0x1403774c6  jnz     loc_140377DDB
0x1403774cc  mov     r8d, r15d
0x1403774cf  mov     rdi, [rsp+388h+var_250]
0x1403774d7  mov     r9, rdi
0x1403774da  cmp     [r12+2Ch], r15d
0x1403774df  ja      loc_140377EE1
0x1403774e5  mov     r10, [rsp+388h+var_218]
0x1403774ed  mov     rax, [rsp+388h+var_1A0]
0x1403774f5  mov     rcx, [rax+28h]
0x1403774f9  mov     eax, [rcx+198h]
0x1403774ff  shr     eax, 8
0x140377502  test    sil, al
0x140377505  jz      loc_140377967
0x14037750b  cmp     [r13+770h], r15d
0x140377512  jnz     loc_140377967
0x140377518  mov     eax, [r12+38h]
0x14037751d  test    al, 2
0x14037751f  jnz     loc_140377D17
0x140377525  mov     rax, [r13+10h]
0x140377529  mov     rax, [rax+10h]
0x14037752d  mov     [rsp+388h+var_230], rax
0x140377535  mov     qword ptr [rsp+388h+var_160], rax
0x14037753d  cmp     [rax+0D1h], r15b
0x140377544  jnz     loc_1403796E6
0x14037754a  mov     eax, [r12+38h]
0x14037754f  bt      eax, 0Bh
0x140377553  jb      loc_14037A48E
0x140377559  mov     r14, [rsp+388h+var_250]
0x140377561  bt      eax, 0Ch
0x140377565  jb      loc_14037A6E4
0x14037756b  mov     ebx, 0FFFFFFFFh
0x140377570  mov     rdi, [rsp+388h+var_1D0]
0x140377578  mov     rax, [r13+10h]
0x14037757c  mov     qword ptr [rsp+388h+var_160], rax
0x140377584  mov     rcx, [rax+10h]; this
0x140377588  call    ?IsGpuVirtualAddressingSupported@DXGADAPTER@@QEBAEXZ; DXGADAPTER::IsGpuVirtualAddressingSupported(void)
0x14037758d  test    al, al
0x14037758f  jnz     loc_140378246
0x140377595  mov     rdi, [rsp+388h+var_268]
0x14037759d  mov     rbx, [rsp+388h+var_240]
0x1403775a5  mov     rsi, [rsp+388h+var_260]
0x1403775ad  cmp     [rsp+388h+var_118], r15b
0x1403775b5  jnz     loc_1403783A7
0x1403775bb  lea     rcx, [rsp+388h+var_D8]; this
0x1403775c3  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x1403775c8  test    edi, edi
0x1403775ca  js      loc_14037A802
0x1403775d0  test    r14, r14
0x1403775d3  jnz     loc_140377A26
0x1403775d9  cmp     [rsp+388h+var_258], r15b
0x1403775e1  jnz     loc_140377F12
0x1403775e7  mov     ebx, r15d
0x1403775ea  mov     r14, [rsp+388h+var_1E8]
0x1403775f2  cmp     [r12+2Ch], r15d
0x1403775f7  ja      loc_140377743
0x1403775fd  mov     rcx, [rsp+388h+var_178]; void *
0x140377605  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x14037760a  cmp     dword ptr [r12+2Ch], 5
0x140377610  ja      loc_14037A9C0
0x140377616  lea     rcx, [rsp+388h+var_D8]; this
0x14037761e  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x140377623  lea     rcx, [rsp+388h+var_120]; this
0x14037762b  call    ??1DXGPROCESSCOPYPROTECTIONMUTEX@@QEAA@XZ; DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX(void)
0x140377630  lea     rcx, [rsp+388h+var_150]; this
0x140377638  call    ??1DXGRESOURCEREFERENCE@@QEAA@XZ; DXGRESOURCEREFERENCE::~DXGRESOURCEREFERENCE(void)
0x14037763d  mov     rdx, [rsp+388h+Entry]; Entry
0x140377645  test    rdx, rdx
0x140377648  jz      short loc_140377665
0x14037764a  mov     rcx, [rsp+388h+var_E0]
0x140377652  add     rcx, 680h; Lookaside
0x140377659  call    cs:__imp_ExFreeToPagedLookasideList
0x140377660  nop     dword ptr [rax+rax+00h]
0x140377665  mov     eax, edi
0x140377667  jmp     loc_14037A9FC
0x14037766d  mov     ecx, edx
0x14037766f  test    dword ptr [r12+38h], 800h
0x140377678  jnz     loc_140378CA9
0x14037767e  lea     r8, [rcx+rcx*2]
0x140377682  shl     r8, 5
0x140377686  mov     eax, [r8+r14+20h]
0x14037768b  test    sil, al
0x14037768e  jnz     loc_140378D16
0x140377694  mov     eax, edx
0x140377696  lea     rcx, [rax+rax*2]
0x14037769a  shl     rcx, 5
0x14037769e  mov     eax, [rcx+r14+20h]
0x1403776a3  test    al, 2
0x1403776a5  jnz     loc_140378E7B
0x1403776ab  mov     r8d, [r12+38h]
0x1403776b0  bt      r8d, 10h
0x1403776b5  jb      loc_140378EB1
0x1403776bb  add     edx, esi
0x1403776bd  mov     r9b, [rsp+388h+var_276]
0x1403776c5  jmp     loc_1403772FD
0x1403776ca  mov     ebx, edi
0x1403776cc  lea     rax, [rbx+rbx*2]
0x1403776d0  shl     rax, 5
0x1403776d4  mov     ecx, [rax+r14+18h]
0x1403776d9  cmp     ecx, 7FFFFFFFh
  ... truncated ...
```
