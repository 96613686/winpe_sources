# DXGDEVICE::CreateAllocation(_D3DKMT_CREATEALLOCATION *,uchar,uchar,_DXGSHAREDALLOCOBJECT *,_D3DKM_CREATESTANDARDALLOCATION const *,COREDEVICEACCESS *,uint,_EPROCESS *,uint *,unsigned __int64 *,unsigned __int64 *,_D3DKMT_CREATESTANDARDALLOCATION *,void *,uint)

- ea: `0x140377080`
- end: `0x14037a854`
- name: `?CreateAllocation@DXGDEVICE@@QEAAJPEAU_D3DKMT_CREATEALLOCATION@@EEPEAU_DXGSHAREDALLOCOBJECT@@PEBU_D3DKM_CREATESTANDARDALLOCATION@@PEAVCOREDEVICEACCESS@@IPEAU_EPROCESS@@PEAIPEA_K6PEAU_D3DKMT_CREATESTANDARDALLOCATION@@PEAXI@Z`
- size: `14292`
- prototype: `__int64 __usercall@<rax>(DXGDEVICE *__hidden this@<rcx>, struct _D3DKMT_CREATEALLOCATION *@<rdx>, unsigned __int8@<r8b>, unsigned __int8@<r9b>, struct _DXGSHAREDALLOCOBJECT *, const struct _D3DKM_CREATESTANDARDALLOCATION *, struct COREDEVICEACCESS *, unsigned int, struct _EPROCESS *, unsigned int *, unsigned __int64 *, unsigned __int64 *, struct _D3DKMT_CREATESTANDARDALLOCATION *, void *, unsigned int)`
- caller_count: `4`
- callee_count: `65`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140320f8c`
- `0x14037612c`
- `0x1403c2a5c`
- `0x1403da390`

## callees

- `0x1400091f0`
- `0x14000d990`
- `0x140012540`
- `0x1400146ac`
- `0x140015290`
- `0x14001a38c`
- `0x14001a42c`
- `0x14001a7bc`
- `0x14001a874`
- `0x14001aa04`
- `0x14001ac50`
- `0x14001b9c0`
- `0x14001bd80`
- `0x14001bea0`
- `0x14002dbc0`
- `0x140033f08`
- `0x140034030`
- `0x14003bd18`
- `0x14003bfbc`
- `0x14003bff4`
- `0x14003cb20`
- `0x14003d33c`
- `0x14003f9c0`
- `0x140042e48`
- `0x14004eb04`
- `0x140057688`
- `0x140058ae8`
- `0x14005953c`
- `0x1400674c4`
- `0x14006e240`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x1400a0d00`
- `0x1400a1000`
- `0x140191504`
- `0x14019af20`
- `0x1401dfb74`
- `0x1401e76e0`
- `0x1401e784c`
- `0x1402100b8`
- `0x1402101e4`
- `0x14021d7e8`
- `0x1402461d0`
- `0x1402970b0`
- `0x14032537c`
- `0x14032a5c4`
- `0x14032e980`
- `0x14032fd70`
- `0x14035f174`
- `0x14036e614`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14037a2a3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14037a554`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14037a5f2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14037a2a3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14037a554`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14037a5f2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14037a297`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14037a548`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14037a5e6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14037a297`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14037a548`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14037a5e6`
- `ntoskrnl!ObfDereferenceObject` at `0x140379583`
- `ntoskrnl!ObfDereferenceObject` at `0x140379583`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140379462`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140379d48`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140379462`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140379d48`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14037a822`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14037a822`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1403775a7`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1403775a7`
- `ntoskrnl!MmSectionObjectType` at `0x140379453`
- `ntoskrnl!MmSectionObjectType` at `0x140379d38`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140379284`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140379a78`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140379284`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140379a78`
- `watchdog!WdLogSingleEntry4` at `0x140377b88`
- `watchdog!WdLogSingleEntry4` at `0x140378de9`
- `watchdog!WdLogSingleEntry4` at `0x140379ba1`
- `watchdog!WdLogSingleEntry4` at `0x140377b88`
- `watchdog!WdLogSingleEntry4` at `0x140378de9`
- `watchdog!WdLogSingleEntry4` at `0x140379ba1`
- `watchdog!WdLogSingleEntry2` at `0x140377282`
- `watchdog!WdLogSingleEntry2` at `0x14037776f`
- `watchdog!WdLogSingleEntry2` at `0x140377b2d`
- `watchdog!WdLogSingleEntry2` at `0x140377be2`
- `watchdog!WdLogSingleEntry2` at `0x140377c34`
- `watchdog!WdLogSingleEntry2` at `0x140377ca7`
- `watchdog!WdLogSingleEntry2` at `0x140377e1c`
- `watchdog!WdLogSingleEntry2` at `0x140377f69`
- `watchdog!WdLogSingleEntry2` at `0x14037862a`
- `watchdog!WdLogSingleEntry2` at `0x140378768`
- `watchdog!WdLogSingleEntry2` at `0x1403789f0`
- `watchdog!WdLogSingleEntry2` at `0x140379494`
- `watchdog!WdLogSingleEntry2` at `0x140379533`
- `watchdog!WdLogSingleEntry2` at `0x1403798a1`
- `watchdog!WdLogSingleEntry2` at `0x140379d80`
- `watchdog!WdLogSingleEntry2` at `0x140377282`
- `watchdog!WdLogSingleEntry2` at `0x14037776f`
- `watchdog!WdLogSingleEntry2` at `0x140377b2d`
- `watchdog!WdLogSingleEntry2` at `0x140377be2`
- `watchdog!WdLogSingleEntry2` at `0x140377c34`
- `watchdog!WdLogSingleEntry2` at `0x140377ca7`
- `watchdog!WdLogSingleEntry2` at `0x140377e1c`
- `watchdog!WdLogSingleEntry2` at `0x140377f69`
- `watchdog!WdLogSingleEntry2` at `0x14037862a`
- `watchdog!WdLogSingleEntry2` at `0x140378768`
- `watchdog!WdLogSingleEntry2` at `0x1403789f0`
- `watchdog!WdLogSingleEntry2` at `0x140379494`
- `watchdog!WdLogSingleEntry2` at `0x140379533`
- `watchdog!WdLogSingleEntry2` at `0x1403798a1`
- `watchdog!WdLogSingleEntry2` at `0x140379d80`
- `watchdog!WdLogSingleEntry3` at `0x1403772b9`
- `watchdog!WdLogSingleEntry3` at `0x140377559`
- `watchdog!WdLogSingleEntry3` at `0x140377583`
- `watchdog!WdLogSingleEntry3` at `0x1403778f1`
- `watchdog!WdLogSingleEntry3` at `0x140377bb5`
- `watchdog!WdLogSingleEntry3` at `0x140377d85`
- `watchdog!WdLogSingleEntry3` at `0x140377f22`
- `watchdog!WdLogSingleEntry3` at `0x1403780a2`
- `watchdog!WdLogSingleEntry3` at `0x14037894f`
- `watchdog!WdLogSingleEntry3` at `0x140378993`
- `watchdog!WdLogSingleEntry3` at `0x140378b2c`
- `watchdog!WdLogSingleEntry3` at `0x140378c81`
- `watchdog!WdLogSingleEntry3` at `0x140379be9`
- `watchdog!WdLogSingleEntry3` at `0x1403772b9`
- `watchdog!WdLogSingleEntry3` at `0x140377559`
- `watchdog!WdLogSingleEntry3` at `0x140377583`
- `watchdog!WdLogSingleEntry3` at `0x1403778f1`
- `watchdog!WdLogSingleEntry3` at `0x140377bb5`
- `watchdog!WdLogSingleEntry3` at `0x140377d85`
- `watchdog!WdLogSingleEntry3` at `0x140377f22`
- `watchdog!WdLogSingleEntry3` at `0x1403780a2`
- `watchdog!WdLogSingleEntry3` at `0x14037894f`
- `watchdog!WdLogSingleEntry3` at `0x140378993`
- `watchdog!WdLogSingleEntry3` at `0x140378b2c`
- `watchdog!WdLogSingleEntry3` at `0x140378c81`
- `watchdog!WdLogSingleEntry3` at `0x140379be9`
- `watchdog!WdLogSingleEntry0` at `0x140377186`
- `watchdog!WdLogSingleEntry0` at `0x1403771e8`
- `watchdog!WdLogSingleEntry0` at `0x140377923`
- `watchdog!WdLogSingleEntry0` at `0x140377987`
- `watchdog!WdLogSingleEntry0` at `0x1403781ed`
- `watchdog!WdLogSingleEntry0` at `0x14037855a`
- `watchdog!WdLogSingleEntry0` at `0x140378f8e`
- `watchdog!WdLogSingleEntry0` at `0x140378fae`
- `watchdog!WdLogSingleEntry0` at `0x140379c17`
- `watchdog!WdLogSingleEntry0` at `0x14037a131`
- `watchdog!WdLogSingleEntry0` at `0x14037a206`
- `watchdog!WdLogSingleEntry0` at `0x14037a37a`
- `watchdog!WdLogSingleEntry0` at `0x140377186`
- `watchdog!WdLogSingleEntry0` at `0x1403771e8`
- `watchdog!WdLogSingleEntry0` at `0x140377923`
- `watchdog!WdLogSingleEntry0` at `0x140377987`
- `watchdog!WdLogSingleEntry0` at `0x1403781ed`
- `watchdog!WdLogSingleEntry0` at `0x14037855a`
- `watchdog!WdLogSingleEntry0` at `0x140378f8e`
- `watchdog!WdLogSingleEntry0` at `0x140378fae`
- `watchdog!WdLogSingleEntry0` at `0x140379c17`
- `watchdog!WdLogSingleEntry0` at `0x14037a131`
- `watchdog!WdLogSingleEntry0` at `0x14037a206`
- `watchdog!WdLogSingleEntry0` at `0x14037a37a`
- `watchdog!WdLogSingleEntry1` at `0x1403775c9`
- `watchdog!WdLogSingleEntry1` at `0x140377cfd`
- `watchdog!WdLogSingleEntry1` at `0x140378d5e`
- `watchdog!WdLogSingleEntry1` at `0x140378efe`
- `watchdog!WdLogSingleEntry1` at `0x1403796d7`
- `watchdog!WdLogSingleEntry1` at `0x140379fea`
- `watchdog!WdLogSingleEntry1` at `0x1403775c9`
- `watchdog!WdLogSingleEntry1` at `0x140377cfd`
- `watchdog!WdLogSingleEntry1` at `0x140378d5e`
- `watchdog!WdLogSingleEntry1` at `0x140378efe`
- `watchdog!WdLogSingleEntry1` at `0x1403796d7`
- `watchdog!WdLogSingleEntry1` at `0x140379fea`

## string_xrefs

- `0x140377218`: `!(UserMode && OpenShared)`
- `0x1403780d1`: `Device 0x%I64x: Driver asked to create a shared resource, but resource 0x%p already exists, and is non-shared, returning 0x%I64x`
- `0x14037821d`: `pCreateStandardAllocation->Flags.Primary == 0`
- `0x14037858a`: `0 != (pCreateAllocation->Flags.CreateShared)`
- `0x140378f2d`: `VmBusSendCreateAllocation failed: 0x%I64x`
- `0x140379706`: `VmBusSendMakeResident failed: 0x%I64x`

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
  struct _D3DKMT_CREATEALLOCATION *v17; // r13
  D3DKMT_CREATEALLOCATIONFLAGS Flags; // edx
  struct _PAGED_LOOKASIDE_LIST *v21; // rcx
  __int64 NumAllocations; // rax
  struct _D3DDDI_ALLOCATIONINFO2 *v23; // r14
  unsigned __int64 v24; // rcx
  unsigned __int64 v25; // rax
  signed int v26; // ebx
  __int64 v27; // rax
  unsigned __int64 v28; // rax
  __int64 v29; // rax
  unsigned __int64 v30; // rax
  __int64 v31; // rax
  void **v32; // rdx
  unsigned __int64 v33; // rax
  __int64 v34; // rax
  unsigned __int8 v35; // al
  __int64 v36; // rax
  void **v37; // r8
  __int64 v38; // r8
  char *v39; // rax
  UINT v40; // eax
  UINT v41; // ecx
  struct DXGRESOURCE *v42; // rbx
  char v43; // cl
  UINT v44; // edx
  __int64 v45; // rdx
  UINT Value; // eax
  struct DXGALLOCATION *v47; // rax
  ADAPTER_DISPLAY *v48; // rcx
  struct DXGALLOCATION *v49; // r9
  UINT v50; // edx
  __int64 v51; // rax
  unsigned int v52; // ecx
  D3DKMT_CREATEALLOCATIONFLAGS v53; // r8d
  int v54; // r9d
  struct DXGALLOCATION *hSection; // rcx
  SIZE_T Size; // r8
  int DestructionBuffers; // edi
  struct DXGALLOCATION *v58; // r14
  UINT i; // edi
  __int64 v60; // rax
  __int64 PrivateDriverDataSize; // rcx
  char *v62; // rax
  char *v63; // rcx
  UINT v64; // eax
  void *v65; // rax
  struct DXGALLOCATION *v66; // r9
  D3DKMT_CREATEALLOCATIONFLAGS v67; // eax
  __int64 v68; // rax
  char v69; // cl
  struct _DXGK_ALLOCATIONINFO *v70; // r8
  D3DKMT_CREATEALLOCATIONFLAGS v71; // eax
  unsigned int v72; // edx
  UINT v73; // ebx
  struct DXGALLOCATION *v74; // r13
  _QWORD *v75; // r14
  struct _D3DKMT_CREATEALLOCATION *v76; // rdi
  __int64 v77; // rax
  struct DXGGLOBAL *Global; // rax
  __int64 v79; // rax
  D3DKMT_HANDLE v80; // eax
  D3DKMT_CREATEALLOCATIONFLAGS v81; // eax
  D3DKMT_HANDLE v82; // ecx
  __int64 v83; // rax
  unsigned int *j; // rdx
  UINT v85; // r8d
  struct DXGALLOCATION *v86; // rdx
  struct _D3DKMT_CREATEALLOCATION *v87; // r10
  struct DXGALLOCATION *v88; // rdi
  unsigned int v89; // edx
  __int64 v90; // rcx
  __int64 PrivateRuntimeDataSize; // rax
  __int64 v92; // rcx
  UINT v93; // eax
  unsigned int v94; // ecx
  unsigned __int8 v95; // di
  __int64 v96; // rax
  __int64 v97; // rcx
  __int64 v98; // rcx
  UINT v99; // eax
  void *pStandardAllocation; // rdx
  struct COREDEVICEACCESS *v101; // rax
  struct _EPROCESS *v102; // rcx
  struct _D3DKMT_CREATESTANDARDALLOCATION *v103; // rax
  __int64 v104; // rax
  struct _EPROCESS *v105; // rdx
  void *v106; // rcx
  size_t v107; // r8
  const void *v108; // rdx
  unsigned int v109; // ecx
  struct DXGALLOCATION *v110; // rax
  char v111; // r11
  D3DKMT_CREATEALLOCATIONFLAGS v112; // ecx
  const void *v113; // r10
  void *v114; // r8
  void **v115; // rdx
  unsigned int v116; // r9d
  int Allocation; // eax
  struct _EPROCESS *v118; // rdi
  __int64 v119; // rbx
  _DWORD *v120; // r9
  D3DKMT_CREATEALLOCATIONFLAGS v121; // ecx
  int v122; // eax
  __int64 v123; // rax
  const wchar_t *v124; // r9
  UINT v125; // ecx
  struct DXGALLOCATION *v126; // r13
  __int64 v127; // r10
  __int64 v128; // rcx
  char v129; // r14
  __int64 v130; // rbx
  int v131; // edi
  __int64 v132; // rsi
  unsigned int CurrentProcessId; // eax
  int v134; // ecx
  int v135; // r8d
  struct _EPROCESS *v136; // r10
  UINT n; // ebx
  D3DKMT_CREATEALLOCATIONFLAGS v138; // eax
  unsigned int *v139; // rdi
  struct COREDEVICEACCESS *v140; // r11
  __int64 v141; // rdx
  struct _DXGK_ALLOCATIONINFO *v142; // r8
  int v143; // eax
  NTSTATUS v144; // eax
  __int64 v145; // rbx
  struct COREDEVICEACCESS *v146; // rsi
  __int64 v147; // rax
  int v148; // eax
  __int64 v149; // rbx
  struct COREDEVICEACCESS *v150; // r8
  __int64 v151; // rcx
  struct COREDEVICEACCESS *v152; // r9
  int Resident; // eax
  __int64 v154; // rbx
  __int64 v155; // rdx
  unsigned __int64 v156; // rcx
  struct _D3DKMT_CREATESTANDARDALLOCATION *v157; // r8
  size_t v158; // rcx
  _QWORD *v159; // rdi
  void **v160; // rax
  struct DXGALLOCATION *v161; // rbx
  struct DXGALLOCATION *v162; // rcx
  UINT v163; // edx
  struct _D3DKMT_CREATEALLOCATION *v164; // r14
  __int64 v165; // rdi
  __int64 v166; // rbx
  unsigned int v167; // eax
  int v168; // r8d
  D3DKMT_CREATEALLOCATIONFLAGS v169; // eax
  int v170; // eax
  __int64 v171; // rdi
  D3DKMT_CREATEALLOCATIONFLAGS v172; // ecx
  NTSTATUS v173; // eax
  unsigned int v174; // eax
  struct _D3DKM_CREATESTANDARDALLOCATION *v175; // rdi
  struct DXGALLOCATION *v176; // rdx
  unsigned int v177; // edi
  int v178; // ecx
  int v179; // eax
  unsigned __int8 v180; // al
  D3DGPU_VIRTUAL_ADDRESS BaseAddress; // rcx
  struct _D3DDDI_ALLOCATIONINFO2 *v182; // rsi
  struct DXGALLOCATION *v183; // rbx
  struct DXGPROCESS *v184; // r13
  struct _D3DKMT_CREATEALLOCATION *v185; // rdi
  unsigned __int64 v186; // r14
  DXGPUSHLOCK *v187; // rcx
  struct _DXGSHAREDALLOCOBJECT *v188; // rdx
  __int64 v189; // r9
  __int64 v190; // r14
  unsigned int v191; // r8d
  __int64 v192; // r10
  __int64 v193; // r14
  UINT v194; // ecx
  struct DXGALLOCATION *v195; // rsi
  struct _D3DKMT_CREATEALLOCATION *v196; // r13
  __int64 v197; // rax
  int v198; // eax
  struct _DXGSHAREDALLOCOBJECT *v199; // rcx
  struct _DXGSHAREDALLOCOBJECT *v200; // r8
  __int64 v201; // rdx
  struct _DXGSHAREDALLOCOBJECT *v202; // rcx
  __int64 v203; // rax
  __int64 v204; // r8
  _QWORD *v205; // rdx
  __int64 v206; // rcx
  __int64 v207; // rcx
  char v208; // r14
  int v209; // eax
  __int64 v210; // rcx
  unsigned int v211; // eax
  __int64 v212; // rdx
  struct DXGPROCESS *v213; // r9
  bool v214; // al
  int v215; // r9d
  UINT v216; // ebx
  void **v217; // r14
  struct _D3DKMT_CREATEALLOCATION *v218; // rsi
  int v219; // [rsp+38h] [rbp-350h]
  int Src; // [rsp+40h] [rbp-348h]
  int v221; // [rsp+48h] [rbp-340h]
  int v222; // [rsp+50h] [rbp-338h]
  int v223; // [rsp+58h] [rbp-330h]
  int v224; // [rsp+60h] [rbp-328h]
  int v225; // [rsp+68h] [rbp-320h]
  int v226; // [rsp+70h] [rbp-318h]
  int v227; // [rsp+78h] [rbp-310h]
  int v228; // [rsp+88h] [rbp-300h]
  int v229; // [rsp+90h] [rbp-2F8h]
  int v230; // [rsp+98h] [rbp-2F0h]
  int v231; // [rsp+A0h] [rbp-2E8h]
  int v232; // [rsp+A8h] [rbp-2E0h]
  int v233; // [rsp+B0h] [rbp-2D8h]
  int v234; // [rsp+B8h] [rbp-2D0h]
  int v235; // [rsp+C0h] [rbp-2C8h]
  int v236; // [rsp+C8h] [rbp-2C0h]
  int v237; // [rsp+D0h] [rbp-2B8h]
  int v238; // [rsp+D8h] [rbp-2B0h]
  int v239; // [rsp+E0h] [rbp-2A8h]
  int v240; // [rsp+E8h] [rbp-2A0h]
  char v243; // [rsp+112h] [rbp-276h]
  struct _D3DDDI_ALLOCATIONINFO2 *v244; // [rsp+120h] [rbp-268h]
  struct DXGALLOCATION *v245; // [rsp+128h] [rbp-260h]
  int v246; // [rsp+130h] [rbp-258h]
  unsigned __int8 v247[4]; // [rsp+138h] [rbp-250h] BYREF
  UINT v248; // [rsp+13Ch] [rbp-24Ch]
  struct DXGRESOURCE *v249; // [rsp+140h] [rbp-248h]
  PVOID v250; // [rsp+148h] [rbp-240h] BYREF
  struct DXGALLOCATION *k; // [rsp+150h] [rbp-238h] BYREF
  char v252; // [rsp+158h] [rbp-230h]
  PVOID v253; // [rsp+160h] [rbp-228h] BYREF
  struct DXGPROCESS *Current; // [rsp+168h] [rbp-220h]
  struct _DXGSHAREDALLOCOBJECT *v255; // [rsp+170h] [rbp-218h] BYREF
  unsigned __int8 v256; // [rsp+178h] [rbp-210h]
  unsigned int VidPnSourceId; // [rsp+180h] [rbp-208h]
  char v258; // [rsp+184h] [rbp-204h]
  void **v259; // [rsp+188h] [rbp-200h]
  struct _D3DKMT_CREATESTANDARDALLOCATION *v260; // [rsp+190h] [rbp-1F8h]
  void **v261; // [rsp+198h] [rbp-1F0h]
  struct _DXGK_ALLOCATIONINFO *v262; // [rsp+1A0h] [rbp-1E8h]
  struct COREDEVICEACCESS *v263; // [rsp+1A8h] [rbp-1E0h]
  struct _D3DKM_CREATESTANDARDALLOCATION *v264; // [rsp+1B0h] [rbp-1D8h]
  struct _EPROCESS *m; // [rsp+1B8h] [rbp-1D0h]
  PVOID Object; // [rsp+1C0h] [rbp-1C8h] BYREF
  struct DXGALLOCATION *v267; // [rsp+1C8h] [rbp-1C0h] BYREF
  struct _D3DKMT_CREATEALLOCATION *v268; // [rsp+1D0h] [rbp-1B8h]
  void *v269; // [rsp+1D8h] [rbp-1B0h]
  struct _D3DKMT_CREATEALLOCATION *v270; // [rsp+1E0h] [rbp-1A8h]
  DXGDEVICE *v271; // [rsp+1E8h] [rbp-1A0h]
  struct DXGPROCESS *v272; // [rsp+1F0h] [rbp-198h]
  struct _D3DKMT_CREATEALLOCATION *v273; // [rsp+200h] [rbp-188h]
  DXGDEVICE *v274; // [rsp+210h] [rbp-178h] BYREF
  void *v275; // [rsp+218h] [rbp-170h]
  struct _DXGK_OPENALLOCATIONINFO *v276; // [rsp+220h] [rbp-168h]
  char v277[16]; // [rsp+228h] [rbp-160h] BYREF
  struct DXGRESOURCE *v278; // [rsp+238h] [rbp-150h] BYREF
  int v279; // [rsp+240h] [rbp-148h]
  PVOID Entry; // [rsp+248h] [rbp-140h]
  _QWORD *v281; // [rsp+250h] [rbp-138h]
  unsigned int *v282; // [rsp+258h] [rbp-130h]
  struct _DXGKARG_DESCRIBEALLOCATION v283; // [rsp+260h] [rbp-128h] BYREF
  const struct _D3DKM_CREATESTANDARDALLOCATION *v284; // [rsp+290h] [rbp-F8h]
  struct _PAGED_LOOKASIDE_LIST *v285; // [rsp+298h] [rbp-F0h]
  _BYTE v286[16]; // [rsp+2A0h] [rbp-E8h] BYREF
  _BYTE v287[32]; // [rsp+2B0h] [rbp-D8h] BYREF
  struct D3DDDI_MAPGPUVIRTUALADDRESS v288; // [rsp+2D0h] [rbp-B8h] BYREF

  v17 = a2;
  v268 = a2;
  v264 = a6;
  v271 = this;
  v273 = a2;
  v256 = a3;
  v255 = a5;
  v284 = a6;
  v263 = a7;
  m = a9;
  v282 = a10;
  v250 = a11;
  Object = a12;
  v260 = a13;
  if ( !ADAPTER_RENDER::IsCoreResourceSharedOwner(*((ADAPTER_RENDER **)this + 2)) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 4855;
    DxgkLogInternalTriageEvent(
      0,
      262146,
      -1,
      (unsigned int)L"GetRenderCore()->IsCoreResourceSharedOwner()",
      4855,
      0,
      0,
      0,
      0);
  }
  if ( a3 && a4 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 4860;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"!(UserMode && OpenShared)", 4860, 0, 0, 0, 0);
  }
  v243 = *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 209LL);
  Current = DXGPROCESS::GetCurrent();
  Flags = v17->Flags;
  if ( (*(_WORD *)&Flags & 0x800) != 0 )
  {
    if ( (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 2596LL) & 0x10) == 0 )
    {
      WdLogSingleEntry2(3, this, -1073741811);
      WdLogGlobalForLineNumber = 4869;
      return 3221225485LL;
    }
    if ( (*(_BYTE *)&Flags & 2) == 0 )
    {
      WdLogSingleEntry3(3, this, -1073741811, 1);
      WdLogGlobalForLineNumber = 4874;
      return 3221225485LL;
    }
  }
  v21 = (struct _PAGED_LOOKASIDE_LIST *)*((_QWORD *)this + 2);
  v253 = v21;
  NumAllocations = v17->NumAllocations;
  if ( (unsigned int)NumAllocations <= 5 )
  {
    v39 = (char *)ExAllocateFromPagedLookasideList(v21 + 13);
    v23 = (struct _D3DDDI_ALLOCATIONINFO2 *)v39;
    v244 = (struct _D3DDDI_ALLOCATIONINFO2 *)v39;
    if ( !v39 )
    {
      WdLogSingleEntry1(6, this);
      WdLogGlobalForLineNumber = 4991;
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
    Entry = v39;
    v262 = (struct _DXGK_ALLOCATIONINFO *)(v39 + 720);
    v276 = (struct _DXGK_OPENALLOCATIONINFO *)(v39 + 480);
    v32 = (void **)(v39 + 640);
    v261 = (void **)(v39 + 640);
    v37 = (void **)(v39 + 680);
    v259 = (void **)(v39 + 680);
    v269 = v39;
  }
  else
  {
    v259 = 0;
    v23 = 0;
    v244 = 0;
    v269 = 0;
    v24 = (unsigned int)NumAllocations;
    v25 = 96 * NumAllocations;
    Entry = (PVOID)v25;
    v26 = v25 > 0xFFFFFFFF ? 0xC0000095 : 0;
    if ( v25 <= 0xFFFFFFFF )
    {
      v27 = 96 * v24;
      if ( !is_mul_ok(v24, 0x60u) )
        v27 = -1;
      v23 = (struct _D3DDDI_ALLOCATIONINFO2 *)operator new[](v27, 1265072196, 256);
      v244 = v23;
      v269 = v23;
      v25 = (unsigned __int64)Entry;
    }
    v262 = 0;
    if ( v25 <= 0xFFFFFFFF )
    {
      v28 = 88LL * v17->NumAllocations;
      v26 = v28 > 0xFFFFFFFF ? 0xC0000095 : 0;
      if ( v28 <= 0xFFFFFFFF )
      {
        v29 = 88LL * v17->NumAllocations;
        if ( !is_mul_ok(v17->NumAllocations, 0x58u) )
          v29 = -1;
        v262 = (struct _DXGK_ALLOCATIONINFO *)operator new[](v29, 1265072196, 258);
      }
    }
    v276 = 0;
    if ( v26 >= 0 )
    {
      v30 = 32LL * v17->NumAllocations;
      v26 = v30 > 0xFFFFFFFF ? 0xC0000095 : 0;
      if ( v30 <= 0xFFFFFFFF )
      {
        v31 = 32LL * v17->NumAllocations;
        if ( !is_mul_ok(v17->NumAllocations, 0x20u) )
          v31 = -1;
        v276 = (struct _DXGK_OPENALLOCATIONINFO *)operator new[](v31, 1265072196, 256);
      }
    }
    v32 = 0;
    v261 = 0;
    if ( v26 < 0 || (v33 = 8LL * v17->NumAllocations, v26 = v33 > 0xFFFFFFFF ? 0xC0000095 : 0, v33 > 0xFFFFFFFF) )
    {
      v35 = a3;
      v37 = 0;
    }
    else
    {
      v34 = 8LL * v17->NumAllocations;
      if ( !is_mul_ok(v17->NumAllocations, 8u) )
        v34 = -1;
      v32 = (void **)operator new[](v34, 1265072196, 256);
      v261 = v32;
      v35 = a3;
      if ( a3 )
      {
        v36 = 8LL * v17->NumAllocations;
        if ( !is_mul_ok(v17->NumAllocations, 8u) )
          v36 = -1;
        v37 = (void **)operator new[](v36, 1265072196, 256);
        v259 = v37;
        v35 = a3;
        v32 = v261;
      }
      else
      {
        v37 = 0;
      }
    }
    if ( v26 < 0 || !v23 || !v262 || !v276 || !v32 || (Entry = 0, !v37) && v35 )
    {
      DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v23);
      DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v262);
      DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v276);
      DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v261);
      DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v259);
      v38 = v17->NumAllocations;
      if ( v26 >= 0 )
      {
        v26 = -1073741801;
        WdLogSingleEntry3(3, this, v38, -1073741801);
        WdLogGlobalForLineNumber = 4979;
      }
      else
      {
        WdLogSingleEntry3(3, this, v38, v26);
        WdLogGlobalForLineNumber = 4972;
      }
      return (unsigned int)v26;
    }
  }
  v270 = v17;
  v285 = (struct _PAGED_LOOKASIDE_LIST *)v253;
  v274 = this;
  v272 = Current;
  v275 = 0;
  v40 = v17->NumAllocations;
  v41 = 0;
  if ( a3 )
  {
    if ( v40 )
    {
      do
      {
        v32[v41] = 0;
        v37[v41++] = 0;
      }
      while ( v41 < v17->NumAllocations );
    }
  }
  else if ( v40 )
  {
    do
      v32[v41++] = 0;
    while ( v41 < v17->NumAllocations );
  }
  v245 = 0;
  v267 = 0;
  v247[0] = 0;
  v42 = 0;
  v249 = 0;
  v252 = 0;
  v278 = 0;
  DXGSYNCOBJECTMUTEX::DXGSYNCOBJECTMUTEX((DXGSYNCOBJECTMUTEX *)v286);
  DXGAUTOPUSHLOCK::DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v287, 0, 0);
  if ( a3 )
    RtlCopyFromUser(v23, v17->pAllocationInfo, 96LL * v17->NumAllocations);
  else
    memmove(v23, v17->pAllocationInfo, 96LL * v17->NumAllocations);
  v43 = v243;
  v258 = v243;
  VidPnSourceId = -1;
  if ( (*(_DWORD *)&v17->Flags & 0x10000) != 0 )
  {
    v23->pPrivateDriverData = a14;
    v23->PrivateDriverDataSize = a15;
  }
  v44 = 0;
  v248 = 0;
  if ( v17->NumAllocations )
  {
    while ( 1 )
    {
      v45 = v44;
      if ( (*(_DWORD *)&v17->Flags & 0x800) != 0 )
      {
        Value = v23[v45].Flags.Value;
        if ( (Value & 1) != 0 )
        {
          VidPnSourceId = v23[v45].VidPnSourceId;
          v43 = v243;
          if ( !*((_QWORD *)this + 237) )
          {
            Value &= ~1u;
            v23[v45].Flags.Value = Value;
          }
        }
        if ( (Value & 2) != 0 )
        {
          WdLogSingleEntry2(3, this, -1073741811);
          WdLogGlobalForLineNumber = 5093;
          goto LABEL_96;
        }
      }
      if ( (v23[v45].Flags.Value & 1) == 0 || v43 )
        goto LABEL_83;
      v47 = (struct DXGALLOCATION *)*((_QWORD *)this + 237);
      k = v47;
      if ( !v47 )
        break;
      v48 = (ADAPTER_DISPLAY *)*((_QWORD *)v47 + 406);
      if ( !v48 || !ADAPTER_DISPLAY::IsCoreResourceSharedOwner(v48) )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 5120;
        DxgkLogInternalTriageEvent(
          0,
          262146,
          -1,
          (unsigned int)L"pDisplayAdapter->IsDisplayAdapter() && pDisplayAdapter->GetDisplayCore()->IsCoreResourceSharedOwner()",
          5120,
          0,
          0,
          0,
          0);
      }
      v49 = k;
      if ( *(_DWORD *)(*((_QWORD *)k + 406) + 96LL) != *((_DWORD *)this + 476) )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 5126;
        DxgkLogInternalTriageEvent(
          0,
          262146,
          -1,
          (unsigned int)L"pDisplayAdapter->GetDisplayCore()->GetNumVidPnSources() == this->GetNumVidPnSources()",
          5126,
          0,
          0,
          0,
          0);
        v49 = k;
      }
      v50 = v248;
      v51 = v248;
      v253 = (PVOID)(v51 * 96);
      v52 = v23[v51].VidPnSourceId;
      if ( v52 >= *((_DWORD *)this + 476) )
      {
        WdLogSingleEntry3(3, this, v23[v51].VidPnSourceId, -1073741811);
        WdLogGlobalForLineNumber = 5133;
        goto LABEL_96;
      }
      if ( !*((_DWORD *)this + 116) && !a4 && (*((_DWORD *)Current + 102) & 0x100) == 0 )
      {
        if ( !ADAPTER_DISPLAY::IsVidPnSourceOwner(*((ADAPTER_DISPLAY **)v49 + 406), this, v52) )
        {
          DestructionBuffers = -1071775744;
          v246 = -1071775744;
          WdLogSingleEntry4(3, -1071775744, this, *(unsigned int *)((char *)&v23->VidPnSourceId + (_QWORD)v253), v248);
          WdLogGlobalForLineNumber = 5148;
          goto LABEL_98;
        }
        goto LABEL_83;
      }
LABEL_84:
      if ( (v23[v50].Flags.Value & 3) == 2 )
      {
        WdLogSingleEntry2(3, -1073741811, this);
        WdLogGlobalForLineNumber = 5166;
LABEL_96:
        DestructionBuffers = -1073741811;
        goto LABEL_97;
      }
      v53 = v17->Flags;
      if ( (*(_DWORD *)&v53 & 0x10000) != 0 )
      {
        v54 = *(_DWORD *)&v17->Flags & 0x20;
        if ( (*(_BYTE *)&v53 & 0x20) != 0 && !v23[v50].hSection
          || (*(_DWORD *)&v53 & 0x20000) != 0 && !v23[v50].hSection )
        {
          WdLogSingleEntry2(2, this, -1073741811);
          WdLogGlobalForLineNumber = 5180;
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
          goto LABEL_96;
        }
        if ( (hSection = (struct DXGALLOCATION *)v23[v50].hSection,
              k = hSection,
              Size = v17->pStandardAllocation->ExistingHeapData.Size,
              v253 = (PVOID)Size,
              v54)
          && hSection != (struct DXGALLOCATION *)((unsigned __int64)hSection & 0xFFFFFFFFFFFFF000uLL)
          || Size != (Size & 0xFFFFFFFFFFFFF000uLL) )
        {
          WdLogSingleEntry2(2, hSection, Size);
          WdLogGlobalForLineNumber = 5193;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Existing sysmem must be paged aligned and a multiple of page in size.                    pSysM"
                           "em:0x%I64x, Size:0x%I64x",
            (__int64)k,
            (__int64)v253,
            0,
            0,
            0);
          DestructionBuffers = -1073741811;
LABEL_97:
          v246 = -1073741811;
LABEL_98:
          v58 = 0;
          goto LABEL_398;
        }
      }
      v44 = v50 + 1;
      v248 = v44;
      if ( v44 >= v17->NumAllocations )
        goto LABEL_104;
      v43 = v243;
    }
    if ( (*(_DWORD *)(*((_QWORD *)this + 5) + 408LL) & 0x100) == 0 )
    {
      WdLogSingleEntry3(3, this, v23[v45].VidPnSourceId, -1073741811);
      WdLogGlobalForLineNumber = 5112;
      goto LABEL_96;
    }
LABEL_83:
    v50 = v248;
    goto LABEL_84;
  }
LABEL_104:
  for ( i = 0; i < v17->NumAllocations; ++i )
  {
    v60 = i;
    PrivateDriverDataSize = v23[v60].PrivateDriverDataSize;
    if ( (unsigned int)PrivateDriverDataSize > 0x7FFFFFFF )
    {
      DestructionBuffers = 0;
      v246 = 0;
      WdLogSingleEntry1(3, -1073741811);
      WdLogGlobalForLineNumber = 5211;
      v42 = 0;
      goto LABEL_98;
    }
    if ( v23[v60].pPrivateDriverData && (_DWORD)PrivateDriverDataSize )
    {
      if ( a3 && (*(_DWORD *)&v17->Flags & 0x10000) == 0 )
        PrivateDriverDataSize = (unsigned int)(2 * PrivateDriverDataSize);
      v62 = (char *)operator new[](PrivateDriverDataSize, 1265072196, 258);
      v261[i] = v62;
      if ( !v62 )
      {
        DestructionBuffers = -1073741801;
        v246 = -1073741801;
        WdLogSingleEntry3(3, this, v17->NumAllocations, -1073741801);
        WdLogGlobalForLineNumber = 5253;
LABEL_115:
        v58 = 0;
        goto LABEL_397;
      }
      if ( a3 && (*(_DWORD *)&v17->Flags & 0x10000) == 0 )
      {
        v63 = &v62[v23[i].PrivateDriverDataSize];
        v259[i] = v63;
        RtlCopyFromUser(v63, v23[i].pPrivateDriverData, v23[i].PrivateDriverDataSize);
      }
    }
    else
    {
      v261[i] = 0;
      if ( a3 )
        v259[i] = 0;
    }
  }
  if ( a3 )
  {
    if ( v17->pStandardAllocation )
    {
      v64 = v17->PrivateDriverDataSize;
      if ( v64 )
      {
        v65 = (void *)operator new[](v64, 1265072196, 258);
        v275 = v65;
        if ( !v65 )
        {
          DestructionBuffers = -1073741801;
          v246 = -1073741801;
          WdLogSingleEntry3(3, this, v17->PrivateDriverDataSize, -1073741801);
          WdLogGlobalForLineNumber = 5298;
          goto LABEL_115;
        }
        RtlCopyFromUser(v65, v17->pStandardAllocation, v17->PrivateDriverDataSize);
      }
    }
  }
  DestructionBuffers = DXGDEVICE::OpenResourceObject(
                         this,
                         v17,
                         v23,
                         a4,
                         m,
                         v255,
                         (struct DXGRESOURCEREFERENCE *)&v278,
                         v247,
                         v264,
                         (struct DXGAUTOMUTEX *)v286,
                         (struct DXGAUTOPUSHLOCK *)v287);
  v246 = DestructionBuffers;
  if ( DestructionBuffers < 0 )
    goto LABEL_115;
  v42 = v278;
  v249 = v278;
  if ( v278 && (*((_DWORD *)v278 + 1) & 1) == 0 && (*(_DWORD *)&v17->Flags & 2) != 0 )
  {
    WdLogSingleEntry3(2, this, v278, -1073741811);
    WdLogGlobalForLineNumber = 5351;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Device 0x%I64x: Driver asked to create a shared resource, but resource 0x%p already exists, and is n"
                     "on-shared, returning 0x%I64x",
      (__int64)this,
      (__int64)v42,
      -1073741811,
      0,
      0);
    goto LABEL_96;
  }
  DestructionBuffers = DXGDEVICE::CreateDestructionBuffers(this, v17->NumAllocations, v278, v247[0]);
  v246 = DestructionBuffers;
  if ( DestructionBuffers < 0 )
    goto LABEL_115;
  k = 0;
  DestructionBuffers = DXGDEVICE::CreateAllocationObjects(this, v17->NumAllocations, &v267, v42, &k);
  v246 = DestructionBuffers;
  if ( DestructionBuffers < 0 )
  {
    v58 = v267;
    v245 = v267;
    goto LABEL_398;
  }
  v66 = k;
  v245 = v267;
  if ( k )
  {
    DXGDEVICE::AppendAllocationListToResourceOrDevice(this, v42, v267, k);
    v252 = 1;
  }
  v67 = v17->Flags;
  if ( (*(_WORD *)&v67 & 0x800) != 0 )
  {
    if ( VidPnSourceId != -1 )
    {
      *(_DWORD *)(*((_QWORD *)v42 + 7) + 12LL) |= 0x40u;
      *((_DWORD *)v42 + 1) |= 8u;
      *(_DWORD *)(*((_QWORD *)v42 + 7) + 12LL) ^= ((unsigned __int8)*(_DWORD *)(*((_QWORD *)v42 + 7) + 12LL)
                                                 ^ (unsigned __int8)(*(_DWORD *)&v17->Flags >> 3))
                                                & 0x80;
    }
    goto LABEL_150;
  }
  if ( (*(_WORD *)&v67 & 0x1000) == 0 )
  {
    if ( !v42 )
      goto LABEL_150;
    v68 = *((_QWORD *)v42 + 7);
    if ( !v68 || (*(_BYTE *)(v68 + 12) & 0x60) != 0x60 )
      goto LABEL_150;
LABEL_149:
    *((_DWORD *)v42 + 1) |= 8u;
    goto LABEL_150;
  }
  if ( v264 )
  {
    if ( (*(_DWORD *)v264 & 0x80u) != 0 )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 5417;
      DxgkLogInternalTriageEvent(
        0,
        262146,
        -1,
        (unsigned int)L"pCreateStandardAllocation->Flags.Primary == 0",
        5417,
        0,
        0,
        0,
        0);
    }
    if ( (*(_DWORD *)v264 & 0x100) != 0 )
      goto LABEL_149;
  }
LABEL_150:
  if ( !v243 )
  {
    memset(v262, 0, 88LL * v17->NumAllocations);
    v69 = a4;
    if ( !a4 )
    {
      DestructionBuffers = DXGDEVICE::CreateDriverAllocations(
                             this,
                             v17,
                             v23,
                             v262,
                             v245,
                             v42,
                             v261,
                             v259,
                             v275,
                             v264,
                             a3,
                             v260);
      v246 = DestructionBuffers;
      v69 = 0;
    }
    if ( DestructionBuffers < 0 )
      goto LABEL_180;
    DestructionBuffers = DXGDEVICE::OpenAllocations(
                           this,
                           v17,
                           v23,
                           v245,
                           v276,
                           v261,
                           v259,
                           v275,
                           a3,
                           v69,
                           a8,
                           v282,
                           (unsigned __int64 *)v250);
    v246 = DestructionBuffers;
    if ( DestructionBuffers < 0 )
      goto LABEL_180;
    v70 = v262;
    if ( (*(_DWORD *)&v17->Flags & 8) != 0 )
      v262->Flags.Value |= 0x4000008u;
    v71 = v17->Flags;
    if ( (*(_WORD *)&v71 & 0x100) != 0 )
    {
      v70->Flags.Value = v70->Flags.Value & 0xFEFFFFFB | 0x1000000;
    }
    else if ( (*(_WORD *)&v71 & 0x200) != 0 )
    {
      v70->Flags.Value |= 0x800004u;
    }
    v72 = v70->Flags.Value | 0x800;
    if ( (*(_DWORD *)&v17->Flags & 0x8000) == 0 )
      v72 = v70->Flags.Value & 0xFFFFF7FF;
    v70->Flags.Value = v72;
    if ( (*(_DWORD *)&v17->Flags & 0x80000) != 0 )
      v70->Flags.Value = v72 | 0x1000;
    DestructionBuffers = DXGDEVICE::CreateVidMmAllocations(this, v17, v23, v70, v245, v264, a4, v263);
    v246 = DestructionBuffers;
    if ( DestructionBuffers < 0 )
    {
LABEL_180:
      v58 = v245;
      goto LABEL_398;
    }
    if ( Object )
    {
      LODWORD(v250) = 0;
      if ( v17->NumAllocations )
      {
        v73 = 0;
        v74 = v245;
        v75 = Object;
        v76 = v270;
        do
        {
          v75[v73] = VIDMM_EXPORT::VidMmQueryAllocationSizeInSystemMemory(
                       *(VIDMM_EXPORT **)(*((_QWORD *)this + 2) + 760LL),
                       *((const struct VIDMM_MULTI_ALLOC **)v74 + 3),
                       (*(_DWORD *)&v76->Flags & 0x20) != 0);
          v74 = (struct DXGALLOCATION *)*((_QWORD *)v74 + 8);
          ++v73;
        }
        while ( v73 < v76->NumAllocations );
        v17 = v76;
        v42 = v249;
        DestructionBuffers = v246;
        v23 = v244;
      }
    }
  }
  if ( v247[0] )
  {
    if ( v42 )
    {
      if ( (*((_DWORD *)v42 + 1) & 1) != 0 )
      {
        v77 = *((_QWORD *)v42 + 7);
        if ( !*(_DWORD *)(v77 + 24) && (*(_DWORD *)(v77 + 12) & 8) == 0 )
        {
          DXGGLOBALSHAREMUTEX::DXGGLOBALSHAREMUTEX((DXGGLOBALSHAREMUTEX *)v277);
          DXGAUTOMUTEX::Acquire((DXGAUTOMUTEX *)v277);
          if ( (*(_DWORD *)&v17->Flags & 2) == 0 )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 5555;
            DxgkLogInternalTriageEvent(
              0,
              262146,
              -1,
              (unsigned int)L"0 != (pCreateAllocation->Flags.CreateShared)",
              5555,
              0,
              0,
              0,
              0);
          }
          if ( (*((_DWORD *)Current + 102) & 0x100) != 0 )
          {
            *(_DWORD *)(*((_QWORD *)v42 + 7) + 24LL) = DXGPROCESS::AllocHandleSafe(
                                                         *((_QWORD *)Current + 75),
                                                         *((_QWORD *)v42 + 7),
                                                         2);
            *(_DWORD *)(*((_QWORD *)v42 + 7) + 12LL) |= 0x2000u;
          }
          else
          {
            Global = DXGGLOBAL::GetGlobal();
            *(_DWORD *)(*((_QWORD *)v42 + 7) + 24LL) = DXGGLOBAL::AllocHandle(Global, *((_QWORD *)v42 + 7), 2);
          }
          if ( !*(_DWORD *)(*((_QWORD *)v42 + 7) + 24LL) )
          {
            WdLogSingleEntry2(3, this, -1073741801);
            WdLogGlobalForLineNumber = 5579;
            DestructionBuffers = -1073741801;
            v246 = -1073741801;
            DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX((DXGPROCESSCOPYPROTECTIONMUTEX *)v277);
            goto LABEL_184;
          }
          DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX((DXGPROCESSCOPYPROTECTIONMUTEX *)v277);
        }
      }
    }
    DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(
      (DXGAUTOPUSHLOCKEXCLUSIVE *)&v283,
      (DXGDEVICE *)((char *)this + 240));
    v79 = *((_QWORD *)this + 7);
    if ( v79 )
      *(_QWORD *)(v79 + 32) = v42;
    *((_QWORD *)v42 + 5) = *((_QWORD *)this + 7);
    *((_QWORD *)this + 7) = v42;
    DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)&v283);
  }
  v80 = 0;
  if ( v42 )
    v80 = *((_DWORD *)v42 + 4);
  v17->hResource = v80;
  v81 = v17->Flags;
  if ( ((*(_BYTE *)&v81 & 2) != 0 || a4) && (*(_BYTE *)&v81 & 0x40) == 0 )
    v82 = *(_DWORD *)(*((_QWORD *)v42 + 7) + 24LL);
  else
    v82 = 0;
  v17->hGlobalShare = v82;
  if ( a3 )
  {
    v83 = 0;
    v279 = 0;
    for ( j = (unsigned int *)v245; ; j = (unsigned int *)*((_QWORD *)k + 8) )
    {
      k = (struct DXGALLOCATION *)j;
      if ( (unsigned int)v83 >= v17->NumAllocations )
        break;
      RtlWriteULongToUser((char *)v17->pAllocationInfo + 96 * v83, j[4]);
      v83 = (unsigned int)++v279;
    }
    if ( DestructionBuffers < 0 )
      goto LABEL_184;
  }
  else
  {
    v85 = 0;
    v86 = v245;
    v66 = v245;
    if ( !v17->NumAllocations )
      goto LABEL_206;
    v87 = v270;
    do
    {
      *(&v87->pAllocationInfo->hAllocation + 24 * v85++) = *((_DWORD *)v66 + 4);
      v66 = (struct DXGALLOCATION *)*((_QWORD *)v66 + 8);
    }
    while ( v85 < v87->NumAllocations );
  }
  v86 = v245;
LABEL_206:
  if ( (*(_DWORD *)(*((_QWORD *)v274 + 5) + 408LL) & 0x100) == 0 || *((_DWORD *)this + 476) )
  {
    v248 = 0;
    v88 = v86;
    for ( k = v86; v248 < v17->NumAllocations; k = v88 )
    {
      v89 = *(_DWORD *)(*((_QWORD *)v88 + 6) + 4LL);
      if ( (v89 & 1) != 0 )
      {
        DestructionBuffers = DXGDEVICE::AddPrimaryAllocation(this, v88);
        v246 = DestructionBuffers;
        if ( DestructionBuffers < 0 )
          goto LABEL_184;
        v88 = k;
      }
      else if ( (v89 & 2) != 0 )
      {
        DXGDEVICE::SetDisplayedPrimary(this, (v89 >> 6) & 0xF, v88, 0, 1u);
      }
      ++v248;
      v88 = (struct DXGALLOCATION *)*((_QWORD *)v88 + 8);
    }
  }
  if ( (*(_DWORD *)&v17->Flags & 2) != 0 )
  {
    if ( v17->pPrivateRuntimeData )
    {
      v90 = *((_QWORD *)v42 + 7);
      PrivateRuntimeDataSize = v17->PrivateRuntimeDataSize;
      if ( *(_QWORD *)(v90 + 104) )
      {
        v94 = *(_DWORD *)(v90 + 112);
        if ( v94 != (_DWORD)PrivateRuntimeDataSize )
        {
          DestructionBuffers = -1073741811;
          v246 = -1073741811;
          WdLogSingleEntry3(3, this, PrivateRuntimeDataSize, v94);
          WdLogGlobalForLineNumber = 5740;
          goto LABEL_184;
        }
      }
      else
      {
        *(_QWORD *)(*((_QWORD *)v42 + 7) + 104LL) = operator new[](
                                                      (unsigned int)PrivateRuntimeDataSize,
                                                      1265072196,
                                                      258);
        v92 = *((_QWORD *)v42 + 7);
        v93 = v17->PrivateRuntimeDataSize;
        if ( !*(_QWORD *)(v92 + 104) )
        {
          DestructionBuffers = -1073741801;
          v246 = -1073741801;
          WdLogSingleEntry3(3, this, v93, -1073741801);
          WdLogGlobalForLineNumber = 5727;
          goto LABEL_184;
        }
        *(_DWORD *)(v92 + 112) = v93;
      }
      v95 = a3;
      if ( a3 )
        RtlCopyFromUser(
          *(void **)(*((_QWORD *)v42 + 7) + 104LL),
          (void *)v17->pPrivateRuntimeData,
          v17->PrivateRuntimeDataSize);
      else
        memmove(*(void **)(*((_QWORD *)v42 + 7) + 104LL), v17->pPrivateRuntimeData, v17->PrivateRuntimeDataSize);
      if ( (*(_DWORD *)&v17->Flags & 0x100000) == 0 )
        goto LABEL_229;
      DestructionBuffers = CheckNoKmdAccessPrivateData(
                             v17->PrivateRuntimeDataSize,
                             *(void **)(*((_QWORD *)v42 + 7) + 104LL),
                             0xFF000004);
      v246 = DestructionBuffers;
      if ( DestructionBuffers < 0 )
        goto LABEL_184;
    }
    v95 = a3;
LABEL_229:
    if ( v17->pStandardAllocation )
    {
      v96 = v17->PrivateDriverDataSize;
      if ( (_DWORD)v96 )
      {
        v97 = *((_QWORD *)v42 + 7);
        if ( *(_QWORD *)(v97 + 120) )
        {
          v109 = *(_DWORD *)(v97 + 128);
          if ( v109 != (_DWORD)v96 )
          {
            DestructionBuffers = -1073741811;
            v246 = -1073741811;
            WdLogSingleEntry3(3, this, v96, v109);
            WdLogGlobalForLineNumber = 5806;
            goto LABEL_184;
          }
        }
        else
        {
          *(_QWORD *)(*((_QWORD *)v42 + 7) + 120LL) = operator new[]((unsigned int)v96, 1265072196, 258);
          v98 = *((_QWORD *)v42 + 7);
          v99 = v17->PrivateDriverDataSize;
          if ( !*(_QWORD *)(v98 + 120) )
          {
            DestructionBuffers = -1073741801;
            v246 = -1073741801;
            WdLogSingleEntry3(3, this, v99, -1073741801);
            WdLogGlobalForLineNumber = 5793;
            goto LABEL_184;
          }
          *(_DWORD *)(v98 + 128) = v99;
        }
        pStandardAllocation = v275;
        if ( !v95 )
          pStandardAllocation = v17->pStandardAllocation;
        memmove(*(void **)(*((_QWORD *)v42 + 7) + 120LL), pStandardAllocation, v17->PrivateDriverDataSize);
        if ( (*(_DWORD *)&v17->Flags & 0x100000) != 0 )
        {
          DestructionBuffers = CheckNoKmdAccessPrivateData(
                                 v17->PrivateDriverDataSize,
                                 *(void **)(*((_QWORD *)v42 + 7) + 120LL),
                                 0xFF000001);
          v246 = DestructionBuffers;
          if ( DestructionBuffers < 0 )
            goto LABEL_184;
        }
      }
    }
    v101 = 0;
    v248 = 0;
    v102 = v245;
    for ( m = v245; (unsigned int)v101 < v17->NumAllocations; m = v102 )
    {
      v263 = v101;
      v103 = (struct _D3DKMT_CREATESTANDARDALLOCATION *)(96LL * (_QWORD)v101);
      v260 = v103;
      if ( *(void **)((char *)&v23->pPrivateDriverData + (_QWORD)v103) )
      {
        v104 = operator new[](*(unsigned int *)((char *)&v23->PrivateDriverDataSize + (_QWORD)v103), 1265072196, 258);
        v105 = m;
        *(_QWORD *)(*((_QWORD *)m + 6) + 32LL) = v104;
        v106 = *(void **)(*((_QWORD *)v105 + 6) + 32LL);
        if ( !v106 )
        {
          DestructionBuffers = -1073741801;
          v246 = -1073741801;
          WdLogSingleEntry4(
            3,
            this,
            v248 + 1,
            *(unsigned int *)((char *)&v23->PrivateDriverDataSize + (_QWORD)v260),
            -1073741801);
          WdLogGlobalForLineNumber = 5850;
          goto LABEL_184;
        }
        if ( !a3 || (*(_DWORD *)&v17->Flags & 0x10000) != 0 )
        {
          v107 = *(unsigned int *)((char *)&v23->PrivateDriverDataSize + (_QWORD)v260);
          v108 = *(void **)((char *)&v23->pPrivateDriverData + (_QWORD)v260);
        }
        else
        {
          v107 = *(unsigned int *)((char *)&v23->PrivateDriverDataSize + (_QWORD)v260);
          v108 = v259[(_QWORD)v263];
        }
        memmove(v106, v108, v107);
        *(_DWORD *)(*((_QWORD *)m + 6) + 40LL) = *(UINT *)((char *)&v23->PrivateDriverDataSize + (_QWORD)v260);
        v102 = m;
      }
      v101 = (struct COREDEVICEACCESS *)(v248 + 1);
      v248 = (unsigned int)v101;
      v102 = (struct _EPROCESS *)*((_QWORD *)v102 + 8);
    }
  }
  v110 = *(struct DXGALLOCATION **)(*((_QWORD *)this + 2) + 16LL);
  k = v110;
  *(_QWORD *)v277 = v110;
  if ( !*((_BYTE *)v110 + 209) )
    goto LABEL_354;
  if ( a4 )
    goto LABEL_336;
  LODWORD(v250) = DXGPROCESS::GetHostProcess(*((DXGPROCESS **)v274 + 5));
  if ( !(_DWORD)v250 )
  {
    DestructionBuffers = -1073741823;
    WdLogSingleEntry1(2, -1073741823);
    WdLogGlobalForLineNumber = 5885;
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
    goto LABEL_254;
  }
  v255 = 0;
  if ( !DXGDEVICE::UmdManagesResidency(this) || !v264 || (v111 = 1, (unsigned int)(*((_DWORD *)v264 + 4) - 1) > 2) )
    v111 = 0;
  v112 = v17->Flags;
  if ( (*(_BYTE *)&v112 & 2) != 0 )
    v113 = *(const void **)(*((_QWORD *)v42 + 7) + 104LL);
  else
    v113 = 0;
  v114 = v275;
  if ( a3 )
  {
    v115 = v259;
    if ( (*(_DWORD *)&v112 & 0x10000) == 0 )
      goto LABEL_267;
  }
  else
  {
    v114 = v17->pStandardAllocation;
  }
  v115 = v261;
LABEL_267:
  if ( (*(_BYTE *)&v112 & 2) != 0 )
    v116 = *((_DWORD *)v42 + 5);
  else
    v116 = 0;
  Allocation = DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendCreateAllocation(
                 (struct DXGALLOCATION *)((char *)k + 4792),
                 (unsigned int)v250,
                 *((_DWORD *)this + 118),
                 v116,
                 v17,
                 v23,
                 v115,
                 v114,
                 v113,
                 a3,
                 v111,
                 (unsigned __int8 **)&v255);
  LODWORD(v250) = Allocation;
  v118 = v245;
  if ( !v255 )
  {
    v119 = Allocation;
    WdLogSingleEntry1(2, Allocation);
    WdLogGlobalForLineNumber = 5915;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"VmBusSendCreateAllocation failed: 0x%I64x",
      v119,
      0,
      0,
      0,
      0);
    DestructionBuffers = (int)v250;
    goto LABEL_254;
  }
  v120 = v255;
  v260 = (struct _D3DKMT_CREATESTANDARDALLOCATION *)v255;
  if ( !v42 )
    goto LABEL_281;
  *((_DWORD *)v42 + 5) = *((_DWORD *)v255 + 1);
  v121 = v17->Flags;
  if ( (*(_BYTE *)&v121 & 2) == 0 )
    goto LABEL_281;
  v122 = v120[2];
  if ( (*(_BYTE *)&v121 & 0x40) != 0 )
  {
    if ( v122 )
    {
      WdLogSingleEntry0(1);
      v123 = 5930;
      v124 = L"NULL == pOutput->hGlobalSharedResource";
LABEL_279:
      WdLogGlobalForLineNumber = v123;
      DxgkLogInternalTriageEvent(0, 262146, -1, (_DWORD)v124, v123, 0, 0, 0, 0);
      v120 = v260;
    }
  }
  else if ( !v122 )
  {
    WdLogSingleEntry0(1);
    v123 = 5934;
    v124 = L"pOutput->hGlobalSharedResource";
    goto LABEL_279;
  }
  *(_DWORD *)(*((_QWORD *)v42 + 7) + 28LL) = v120[2];
LABEL_281:
  v281 = 0;
  if ( (*(_DWORD *)&v17->Flags & 2) != 0 && v42 )
    v281 = *(_QWORD **)(*((_QWORD *)v42 + 7) + 136LL);
  v125 = 0;
  v248 = 0;
  if ( v17->NumAllocations )
  {
    v126 = v245;
    do
    {
      *((_DWORD *)v126 + 32) = v120[3];
      v127 = v125;
      *((_DWORD *)v126 + 5) = v120[18 * v125 + 4];
      *((_BYTE *)v126 + 128) |= 4u;
      if ( (*(_DWORD *)&v270->Flags & 0x20020) != 0 && (*(_DWORD *)&v270->Flags & 2) != 0 )
        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v126 + 5) + 56LL) + 200LL) = v120[18 * v125 + 7];
      else
        *((_DWORD *)v126 + 31) = v120[18 * v125 + 7];
      if ( v120[3] & 1 | ((v120[3] & 2) != 0) )
      {
        *((_QWORD *)v126 + 13) = v23[v125].hSection;
        *((_BYTE *)v126 + 128) ^= (*((_BYTE *)v126 + 128) ^ (8 * (v120[18 * v125 + 6] >> 21))) & 8;
      }
      *(_DWORD *)(*((_QWORD *)v126 + 6) + 4LL) ^= (v120[18 * v125 + 6] ^ *(_DWORD *)(*((_QWORD *)v126 + 6) + 4LL)) & 1;
      *(_DWORD *)(*((_QWORD *)v126 + 6) + 4LL) ^= (v120[18 * v125 + 6] ^ *(_DWORD *)(*((_QWORD *)v126 + 6) + 4LL)) & 2;
      *(_DWORD *)(*((_QWORD *)v126 + 6) + 4LL) ^= (v120[18 * v125 + 6] ^ *(_DWORD *)(*((_QWORD *)v126 + 6) + 4LL)) & 4;
      *(_DWORD *)(*((_QWORD *)v126 + 6) + 4LL) ^= (v120[18 * v125 + 6] ^ *(_DWORD *)(*((_QWORD *)v126 + 6) + 4LL)) & 8;
      *(_DWORD *)(*((_QWORD *)v126 + 6) + 4LL) ^= (v120[18 * v125 + 6]
                                                 ^ *(_DWORD *)(*((_QWORD *)v126 + 6) + 4LL))
                                                & 0x20;
      *(_DWORD *)(*((_QWORD *)v126 + 6) + 4LL) ^= (v120[18 * v125 + 6]
                                                 ^ *(_DWORD *)(*((_QWORD *)v126 + 6) + 4LL))
                                                & 0x800;
      *(_DWORD *)(*((_QWORD *)v126 + 6) + 4LL) ^= (v120[18 * v125 + 6]
                                                 ^ *(_DWORD *)(*((_QWORD *)v126 + 6) + 4LL))
                                                & 0x1000;
      *(_DWORD *)(*((_QWORD *)v126 + 6) + 4LL) ^= (v120[18 * v125 + 6]
                                                 ^ *(_DWORD *)(*((_QWORD *)v126 + 6) + 4LL))
                                                & 0x2000;
      *(_DWORD *)(*((_QWORD *)v126 + 6) + 4LL) ^= (v120[18 * v125 + 6]
                                                 ^ *(_DWORD *)(*((_QWORD *)v126 + 6) + 4LL))
                                                & 0x4000;
      *(_DWORD *)(*((_QWORD *)v126 + 6) + 4LL) ^= (v120[18 * v125 + 6]
                                                 ^ *(_DWORD *)(*((_QWORD *)v126 + 6) + 4LL))
                                                & 0x40000;
      *(_DWORD *)(*((_QWORD *)v126 + 6) + 4LL) ^= (v120[18 * v125 + 6]
                                                 ^ *(_DWORD *)(*((_QWORD *)v126 + 6) + 4LL))
                                                & 0x80000;
      *(_DWORD *)(*((_QWORD *)v126 + 6) + 4LL) ^= (v120[18 * v125 + 6]
                                                 ^ *(_DWORD *)(*((_QWORD *)v126 + 6) + 4LL))
                                                & 0x100000;
      *(_DWORD *)(*((_QWORD *)v126 + 6) + 4LL) |= 0x20000u;
      v128 = v125;
      if ( (v23[v127].Flags.Value & 1) != 0 )
      {
        *(_DWORD *)(*((_QWORD *)v126 + 6) + 4LL) ^= ((unsigned __int16)*(_DWORD *)(*((_QWORD *)v126 + 6) + 4LL)
                                                   ^ (unsigned __int16)((unsigned __int16)v23[v128].VidPnSourceId << 6))
                                                  & 0x3C0;
        if ( *((_QWORD *)this + 237) != *(_QWORD *)(*((_QWORD *)this + 2) + 16LL) )
          *(_DWORD *)(*((_QWORD *)v126 + 6) + 4LL) |= 4u;
      }
      if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x1000) != 0 )
      {
        v129 = (*((_DWORD *)v126 + 18) >> 12) & 0x3F;
        v130 = *((_QWORD *)v126 + 6);
        v131 = *((_DWORD *)v126 + 30);
        v132 = *(_QWORD *)(*((_QWORD *)this + 2) + 16LL);
        CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
        McTemplateK0pppqxqqqqqqqpppqqqqqqqqqqtphtp_EtwWriteTransfer(
          v134,
          (unsigned int)EventCreateAdapterAllocation,
          v135,
          CurrentProcessId,
          (char)this,
          v132,
          0,
          v131,
          Src,
          v221,
          v222,
          v223,
          v224,
          v225,
          v226,
          v227,
          v130,
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
          v238,
          v239,
          v240,
          v129,
          0,
          0);
        v23 = v244;
        v120 = v260;
      }
      v125 = v248 + 1;
      v248 = v125;
      v126 = (struct DXGALLOCATION *)*((_QWORD *)v126 + 8);
    }
    while ( v125 < v270->NumAllocations );
    v17 = v270;
    v118 = v245;
  }
  if ( (int)v250 < 0 )
  {
    DestructionBuffers = (int)v250;
    goto LABEL_254;
  }
  v136 = v118;
  m = v118;
  for ( n = 0; ; ++n )
  {
    v248 = n;
    if ( n >= v17->NumAllocations )
      break;
    v138 = v17->Flags;
    if ( (*(_DWORD *)&v138 & 0x10000) == 0 )
      goto LABEL_319;
    if ( (*(_BYTE *)&v138 & 0x20) != 0 )
    {
      v139 = (unsigned int *)v23[n].hSection;
      v282 = v139;
      v140 = (struct COREDEVICEACCESS *)(88LL * n);
      v263 = v140;
      if ( (*((_BYTE *)this + 1917) & 1) == 0 )
      {
        DestructionBuffers = ProcessSysMemAttributes(
                               v139,
                               v120[18 * n + 8],
                               (struct _DXGK_ALLOCATIONINFO *)((char *)v262 + (_QWORD)v140));
        v246 = DestructionBuffers;
        if ( DestructionBuffers < 0 )
          goto LABEL_184;
        v136 = m;
        v140 = v263;
        v139 = v282;
      }
      if ( (*(_DWORD *)&v17->Flags & 2) != 0 )
      {
        v141 = *(_QWORD *)(*((_QWORD *)v136 + 5) + 56LL);
        *(_DWORD *)(v141 + 12) |= 0x200u;
        *(_QWORD *)(v141 + 192) = v139;
        v142 = v262;
        *(_DWORD *)(v141 + 204) = *(UINT *)((char *)&v262->Alignment + (_QWORD)v140);
        v143 = *(UINT *)((char *)&v142->Flags.Value + (_QWORD)v140);
LABEL_316:
        *(_DWORD *)(v141 + 12) ^= ((unsigned __int16)*(_DWORD *)(v141 + 12)
                                 ^ (unsigned __int16)((_WORD)v143 << 9))
                                & 0x800;
      }
    }
    else
    {
      if ( (*(_DWORD *)&v138 & 0x20000) != 0 )
      {
        v263 = (struct COREDEVICEACCESS *)(96LL * n);
        Object = 0;
        v144 = ObReferenceObjectByHandle(
                 *(HANDLE *)((char *)&v23->hSection + (_QWORD)v263),
                 0x20000u,
                 MmSectionObjectType,
                 a3,
                 &Object,
                 0);
        DestructionBuffers = v144;
        v246 = v144;
        if ( v144 < 0 )
        {
          v145 = v144;
          v146 = v263;
          WdLogSingleEntry2(2, *(HANDLE *)((char *)&v23->hSection + (_QWORD)v263), v144);
          WdLogGlobalForLineNumber = 6100;
          v147 = *(__int64 *)((char *)&v23->hSection + (_QWORD)v146);
          goto LABEL_312;
        }
        v250 = Object;
        v263 = (struct COREDEVICEACCESS *)&v262[n];
        v148 = ProcessSectionAttributes(Object, (struct _DXGK_ALLOCATIONINFO *)v263);
        DestructionBuffers = v148;
        v246 = v148;
        if ( v148 < 0 )
        {
          v149 = v148;
          WdLogSingleEntry2(2, this, v148);
          WdLogGlobalForLineNumber = 6110;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Failed to query section attributes. Device=0x%I64x, Status=%I64X",
            (__int64)this,
            v149,
            0,
            0,
            0);
          ObfDereferenceObject(v250);
          goto LABEL_184;
        }
        v136 = m;
        v141 = *(_QWORD *)(*((_QWORD *)m + 5) + 56LL);
        *(_DWORD *)(v141 + 12) |= 0x400u;
        *(_QWORD *)(v141 + 192) = v250;
        v150 = v263;
        *(_DWORD *)(v141 + 204) = *((_DWORD *)v263 + 3);
        v143 = *((_DWORD *)v150 + 16);
        goto LABEL_316;
      }
      if ( (*(_BYTE *)&v138 & 2) != 0 )
        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v136 + 5) + 56LL) + 12LL) ^= ((unsigned __int16)*(_DWORD *)(*(_QWORD *)(*((_QWORD *)v136 + 5) + 56LL) + 12LL)
                                                                        ^ (unsigned __int16)((unsigned __int16)*(_DWORD *)&v262[n].Flags.0 << 9))
                                                                       & 0x800;
    }
LABEL_319:
    v151 = n;
    v152 = (struct COREDEVICEACCESS *)(96LL * n);
    v263 = v152;
    if ( (*(UINT *)((_BYTE *)&v23->Flags.Value + (_QWORD)v152) & 1) != 0 )
    {
      v250 = 0;
      DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v253, v136);
      DXGALLOCATIONREFERENCE::MoveAssign(&v250, &v253);
      DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v253);
      Resident = DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendMakeResident(
                   (DXG_GUEST_VIRTUALGPU_VMBUS *)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 4792LL),
                   *((_DWORD *)Current + 122),
                   *((_DWORD *)this + 118),
                   0,
                   (struct D3DDDI_MAKERESIDENT_FLAGS)3,
                   1u,
                   (const struct DXGALLOCATIONREFERENCE *)&v250,
                   0,
                   0);
      DestructionBuffers = Resident;
      v246 = Resident;
      if ( Resident < 0 )
      {
        v154 = Resident;
        WdLogSingleEntry1(2, Resident);
        WdLogGlobalForLineNumber = 6153;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"VmBusSendMakeResident failed: 0x%I64x",
          v154,
          0,
          0,
          0,
          0);
        DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v250);
        goto LABEL_334;
      }
      DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v250);
      v136 = m;
      v152 = v263;
      v151 = n;
    }
    *(_QWORD *)(*((_QWORD *)v136 + 6) + 16LL) = *((_QWORD *)v136 + 6);
    v155 = *((_QWORD *)v136 + 6);
    v156 = 3 * v151;
    v157 = v260;
    *((_DWORD *)v136 + 30) = v260[v156 + 1].ExistingHeapData.Size;
    *(_QWORD *)(v155 + 112) = LODWORD(v157[v156 + 1].ExistingHeapData.Size);
    *(_OWORD *)(v155 + 64) = *(_OWORD *)&v157[v156 + 1].Flags.0;
    *(_OWORD *)(v155 + 80) = *(_OWORD *)&v157[v156 + 2].ExistingHeapData.Size;
    *(_OWORD *)(v155 + 96) = *(_OWORD *)&v157[v156 + 3].Type;
    v158 = *(unsigned int *)((char *)&v23->PrivateDriverDataSize + (_QWORD)v152);
    LODWORD(v250) = *(UINT *)((char *)&v23->PrivateDriverDataSize + (_QWORD)v152);
    if ( !a3 || (*(_DWORD *)&v17->Flags & 0x10000) != 0 )
    {
      Object = (PVOID)(8LL * n);
      memmove(v23[n].pPrivateDriverData, *(const void **)((char *)v261 + (_QWORD)Object), v158);
    }
    else
    {
      Object = (PVOID)(8LL * n);
      RtlCopyToUser(v23[n].pPrivateDriverData, *(void **)((char *)v259 + (_QWORD)Object), (unsigned int)v158);
    }
    v159 = v281;
    if ( v281 )
    {
      if ( !a3 || (v160 = v259, (*(_DWORD *)&v17->Flags & 0x10000) != 0) )
        v160 = v261;
      memmove((void *)*(v281 - 2), *(const void **)((char *)v160 + (_QWORD)Object), (unsigned int)v250);
      v281 = (_QWORD *)*v159;
    }
    v120 = v260;
    v136 = (struct _EPROCESS *)*((_QWORD *)m + 8);
    m = v136;
  }
  DestructionBuffers = v246;
LABEL_334:
  DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v255);
  if ( DestructionBuffers < 0 )
    goto LABEL_184;
  v110 = k;
LABEL_336:
  if ( *((_BYTE *)v110 + 209) )
  {
    v161 = v245;
    if ( !a4 )
    {
      if ( bTracingEnabled )
      {
        v162 = v245;
        k = v245;
        v163 = 0;
        LODWORD(v250) = 0;
        if ( v17->NumAllocations )
        {
          v164 = v270;
          do
          {
            if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x1000) != 0 )
            {
              v248 = *((_DWORD *)v162 + 5);
              v165 = *((_QWORD *)v162 + 5);
              if ( v165 )
                v253 = *(PVOID *)(v165 + 48);
              else
                v253 = 0;
              if ( v165 )
                Object = (PVOID)*(unsigned int *)(v165 + 16);
              else
                Object = 0;
              *(_QWORD *)v277 = *((unsigned int *)v162 + 4);
              if ( v165 )
                v255 = *(struct _DXGSHAREDALLOCOBJECT **)(v165 + 56);
              else
                v255 = 0;
              v166 = *(_QWORD *)(*((_QWORD *)this + 2) + 16LL);
              v167 = (unsigned int)PsGetCurrentProcessId();
              McTemplateK0ppppppppppppq_EtwWriteTransfer(
                (_DWORD)k,
                (unsigned int)EventCreateDeviceAllocation,
                v168,
                v167,
                (char)this,
                v166,
                (char)k,
                v219,
                v165,
                (char)v255,
                v277[0],
                (char)Object,
                (char)v253,
                v225,
                v226,
                v248);
              v162 = k;
              v163 = (unsigned int)v250;
            }
            LODWORD(v250) = ++v163;
            v162 = (struct DXGALLOCATION *)*((_QWORD *)v162 + 8);
            k = v162;
          }
          while ( v163 < v164->NumAllocations );
          v23 = v244;
          goto LABEL_354;
        }
      }
    }
  }
  else
  {
LABEL_354:
    v161 = v245;
  }
  v169 = v17->Flags;
  if ( (*(_WORD *)&v169 & 0x800) != 0 )
  {
    memset(&v283, 0, sizeof(v283));
    v283.hAllocation = *(HANDLE *)(*((_QWORD *)v161 + 6) + 16LL);
    v170 = ADAPTER_RENDER::DdiDescribeAllocation(*((ADAPTER_RENDER **)this + 2), &v283);
    DestructionBuffers = v170;
    v246 = v170;
    if ( v170 < 0 )
    {
      v58 = v245;
      WdLogSingleEntry4(3, v170, this, *((unsigned int *)v245 + 4), v245);
      WdLogGlobalForLineNumber = 6258;
      goto LABEL_397;
    }
    if ( v283.Format == D3DDDIFMT_UNKNOWN && v283.Height != 1 )
    {
      WdLogSingleEntry3(3, -1073741811, this, v283.Height);
      WdLogGlobalForLineNumber = 6266;
      DestructionBuffers = -1073741811;
LABEL_254:
      v246 = DestructionBuffers;
LABEL_184:
      v58 = v245;
      goto LABEL_397;
    }
    if ( (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)v161 + 5) + 56LL) + 12LL) & 0x20) == 0 )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 6273;
      DxgkLogInternalTriageEvent(
        0,
        262146,
        -1,
        (unsigned int)L"pAllocationObjectList->m_pOwningResource->m_pSharedResource->m_CrossAdapter",
        6273,
        0,
        0,
        0,
        0);
    }
    v171 = *(_QWORD *)(*((_QWORD *)v161 + 5) + 56LL);
    *(_QWORD *)v277 = v171;
    *(_DWORD *)(v171 + 208) = v283.Width;
    *(_DWORD *)(v171 + 212) = v283.Height;
    *(_DWORD *)(v171 + 216) = v283.Format;
    v172 = v17->Flags;
    if ( (*((_BYTE *)this + 1917) & 1) != 0 )
    {
      if ( (*(_DWORD *)&v172 & 0x20000) != 0 )
      {
        v253 = 0;
        v173 = ObReferenceObjectByHandle(v23->hSection, 0x20000u, MmSectionObjectType, a3, &v253, 0);
        *(_QWORD *)(v171 + 192) = v253;
        DestructionBuffers = v173;
        v246 = v173;
        if ( v173 < 0 )
        {
          v145 = v173;
          WdLogSingleEntry2(2, v23->hSection, v173);
          WdLogGlobalForLineNumber = 6310;
          v147 = (__int64)v23->hSection;
LABEL_312:
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Failed to take a reference on hSection:0x%I64x, returning 0x%I64x",
            v147,
            v145,
            0,
            0,
            0);
          goto LABEL_184;
        }
        v171 = *(_QWORD *)v277;
        *(_DWORD *)(*(_QWORD *)v277 + 12LL) |= 0x400u;
      }
    }
    else
    {
      if ( (*(_BYTE *)&v172 & 0x20) == 0 )
      {
        *(_QWORD *)(v171 + 192) = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 2)
                                                                                            + 760LL)
                                                                                + 8LL)
                                                                    + 640LL))(*((_QWORD *)v161 + 3));
        *(_DWORD *)(v171 + 12) |= 0x400u;
      }
      *(_QWORD *)(v171 + 224) = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 2)
                                                                                                  + 760LL)
                                                                                      + 8LL)
                                                                          + 712LL))(
                                  *(_QWORD *)(*((_QWORD *)this + 2) + 768LL),
                                  *((_QWORD *)v161 + 3));
    }
    v174 = VidPnSourceId;
    *(_DWORD *)(v171 + 232) = VidPnSourceId;
    v58 = v245;
    if ( v174 != -1 )
    {
      *(_DWORD *)(v171 + 12) |= 0x40u;
      *(_DWORD *)(v171 + 12) ^= ((unsigned __int8)*(_DWORD *)(v171 + 12)
                               ^ (unsigned __int8)(*(_DWORD *)&v17->Flags >> 3))
                              & 0x80;
    }
LABEL_375:
    v175 = v264;
  }
  else
  {
    v58 = v245;
    if ( (*(_WORD *)&v169 & 0x1000) == 0 )
      goto LABEL_375;
    v175 = v264;
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, struct DXGALLOCATION *))(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 760LL)
                                                                                       + 8LL)
                                                                           + 720LL))(
      *(_QWORD *)(*((_QWORD *)this + 2) + 768LL),
      *((_QWORD *)v245 + 3),
      *((_QWORD *)v264 + 43),
      v66);
  }
  *(_QWORD *)v277 = *((_QWORD *)this + 2);
  if ( DXGADAPTER::IsGpuVirtualAddressingSupported(*(DXGADAPTER **)(*(_QWORD *)v277 + 16LL))
    && v175
    && (*(_DWORD *)v175 & 0x200) == 0
    && (memset(&v288, 0, sizeof(v288)),
        v288.Protection.Value = 1,
        LODWORD(v250) = 0,
        v176 = v58,
        k = v58,
        v17->NumAllocations) )
  {
    while ( 1 )
    {
      v177 = (*((_DWORD *)v176 + 18) >> 12) & 0x3F;
      if ( *((_DWORD *)v264 + 4) == 4 )
      {
        v178 = *(_DWORD *)(*((_QWORD *)v264 + 3) + 12LL);
        if ( ((v178 - 1) & 0xFFFFFFFC) != 0 || v178 == 2 )
        {
          if ( DXGADAPTER::ReplicateGdiContent(*(DXGADAPTER **)(*((_QWORD *)this + 2) + 16LL)) )
            v177 = -1;
          v176 = k;
        }
      }
      v179 = v243
           ? DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendMapGpuVirtualAddress(
               (DXG_GUEST_VIRTUALGPU_VMBUS *)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 4792LL),
               *((_DWORD *)Current + 122),
               this,
               0,
               *((_DWORD *)v176 + 5),
               &v288)
           : VIDMM_EXPORT::VidMmMapGpuVirtualAddress(
               *(VIDMM_EXPORT **)(*(_QWORD *)v277 + 760LL),
               *(struct VIDMM_GLOBAL **)(*(_QWORD *)v277 + 768LL),
               0,
               *((struct VIDMM_MULTI_ALLOC **)v176 + 3),
               &v288,
               0,
               v177);
      DestructionBuffers = v179;
      v246 = v179;
      if ( v179 < 0 )
        break;
      v180 = DXGADAPTER::ReplicateGdiContent(*(DXGADAPTER **)(*((_QWORD *)this + 2) + 16LL));
      BaseAddress = v288.BaseAddress;
      if ( v180 )
        BaseAddress = v288.VirtualAddress;
      v288.BaseAddress = BaseAddress;
      v288.VirtualAddress = 0;
      LODWORD(v250) = (_DWORD)v250 + 1;
      v176 = (struct DXGALLOCATION *)*((_QWORD *)k + 8);
      k = v176;
      if ( (unsigned int)v250 >= v17->NumAllocations )
        goto LABEL_397;
    }
    WdLogSingleEntry1(3, v179);
    WdLogGlobalForLineNumber = 6411;
  }
  else
  {
    DestructionBuffers = v246;
  }
LABEL_397:
  v42 = v249;
LABEL_398:
  v182 = v244;
  DXGAUTOMUTEX::ReleaseIfAcquired((DXGAUTOMUTEX *)v286);
  DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v287);
  if ( DestructionBuffers >= 0 )
  {
    if ( v58 )
    {
      LODWORD(v250) = 0;
      if ( v17->NumAllocations )
      {
        v183 = v245;
        v184 = Current;
        v185 = v270;
        do
        {
          v255 = (struct _DXGSHAREDALLOCOBJECT *)*((_QWORD *)this + 5);
          v186 = *((unsigned int *)v183 + 4);
          v187 = (struct _DXGSHAREDALLOCOBJECT *)((char *)v255 + 248);
          VidPnSourceId = (*((_DWORD *)v183 + 4) >> 6) & 0xFFFFFF;
          if ( (*((_DWORD *)v184 + 102) & 0x100) != 0 )
          {
            DXGPUSHLOCK::AcquireExclusive(v187);
            v188 = v255;
            if ( VidPnSourceId < *((_DWORD *)v255 + 74) )
            {
              v189 = *((_QWORD *)v255 + 35);
              if ( (((unsigned int)v186 >> 25) & 0x60) == (*(_BYTE *)(v189 + 16LL * VidPnSourceId + 8) & 0x60)
                && (*(_DWORD *)(v189 + 16LL * VidPnSourceId + 8) & 0x1F) != 0 )
              {
                v190 = 16 * ((v186 >> 6) & 0xFFFFFF);
                if ( (*(_DWORD *)(v189 + v190 + 8) & 0x2000) == 0 )
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
                  v188 = v255;
                }
                *(_DWORD *)(*((_QWORD *)v188 + 35) + v190 + 8) &= ~0x2000u;
              }
            }
          }
          else
          {
            DXGPUSHLOCK::AcquireExclusive(v187);
            v188 = v255;
            v191 = VidPnSourceId;
            if ( VidPnSourceId < *((_DWORD *)v255 + 74) )
            {
              v192 = *((_QWORD *)v255 + 35);
              if ( (((unsigned int)v186 >> 25) & 0x60) == (*(_BYTE *)(v192 + 16LL * VidPnSourceId + 8) & 0x60)
                && (*(_DWORD *)(v192 + 16LL * VidPnSourceId + 8) & 0x1F) != 0 )
              {
                v193 = 16 * ((v186 >> 6) & 0xFFFFFF);
                if ( (*(_DWORD *)(v192 + v193 + 8) & 0x2000) == 0 )
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
                  v188 = v255;
                  v191 = VidPnSourceId;
                }
                *(_DWORD *)(*((_QWORD *)v188 + 35) + v193 + 8) &= ~0x2000u;
              }
              if ( v191 < *((_DWORD *)v188 + 74) )
                *(_DWORD *)(16LL * v191 + *((_QWORD *)v188 + 35) + 8) &= ~0x4000u;
            }
          }
          *((_QWORD *)v188 + 32) = 0;
          ExReleasePushLockExclusiveEx((char *)v188 + 248, 0);
          KeLeaveCriticalRegion();
          LODWORD(v250) = (_DWORD)v250 + 1;
          v183 = (struct DXGALLOCATION *)*((_QWORD *)v183 + 8);
        }
        while ( (unsigned int)v250 < v185->NumAllocations );
        v17 = v268;
        v42 = v249;
        DestructionBuffers = v246;
        v182 = v244;
      }
    }
    if ( v247[0] )
      DXGPROCESS::CommitResourceHandleSafe(*((DXGPROCESS **)v274 + 5), v42);
    goto LABEL_470;
  }
  if ( v58 )
  {
    if ( !a4 )
    {
      v194 = 0;
      LODWORD(v250) = 0;
      if ( v17->NumAllocations )
      {
        v195 = v58;
        v196 = v270;
        do
        {
          v197 = *((_QWORD *)v195 + 6);
          if ( *(_QWORD *)(v197 + 8) )
          {
            if ( (v198 = *(_DWORD *)(v197 + 4), (v198 & 1) != 0) && !*((_DWORD *)this + 116) || (v198 & 2) != 0 )
            {
              if ( (v198 & 0x10) != 0 )
              {
                WdLogSingleEntry0(1);
                WdLogGlobalForLineNumber = 6484;
                DxgkLogInternalTriageEvent(
                  0,
                  262146,
                  -1,
                  (unsigned int)L"!pAllocation->m_pAllocation->m_Invalidated",
                  6484,
                  0,
                  0,
                  0,
                  0);
              }
              VIDMM_EXPORT::VidMmInvalidateAllocation(
                *(VIDMM_EXPORT **)(*((_QWORD *)this + 2) + 760LL),
                *(struct VIDMM_GLOBAL **)(*((_QWORD *)this + 2) + 768LL),
                *(struct VIDMM_MULTI_GLOBAL_ALLOC **)(*((_QWORD *)v195 + 6) + 8LL));
              *(_DWORD *)(*((_QWORD *)v195 + 6) + 4LL) |= 0x10u;
              v194 = (unsigned int)v250;
            }
          }
          LODWORD(v250) = ++v194;
          v195 = (struct DXGALLOCATION *)*((_QWORD *)v195 + 8);
        }
        while ( v194 < v196->NumAllocations );
        v17 = v268;
        v42 = v249;
        v182 = v244;
      }
    }
  }
  if ( v247[0] )
  {
    DXGRESOURCEREFERENCE::DXGRESOURCEREFERENCE((DXGRESOURCEREFERENCE *)&v253, 0);
    DXGRESOURCEREFERENCE::MoveAssign(&v278, &v253);
    DXGRESOURCEREFERENCE::~DXGRESOURCEREFERENCE((DXGRESOURCEREFERENCE *)&v253);
    DXGDEVICE::RemoveResourceFromDeviceList(this, v42);
    goto LABEL_468;
  }
  if ( v58 )
  {
    if ( v252 )
      DXGDEVICE::RemoveAllocationsWithoutDestroy(this, v42, v58, v17->NumAllocations);
    if ( !v42 || *((_QWORD *)v42 + 7) )
    {
      v199 = v58;
      v255 = v58;
      do
      {
        v200 = (struct _DXGSHAREDALLOCOBJECT *)*((_QWORD *)v199 + 8);
        *(_QWORD *)v277 = v200;
        *((_QWORD *)v199 + 7) = 0;
        *((_QWORD *)v199 + 8) = 0;
        if ( v42 )
        {
          v201 = *((_QWORD *)v42 + 7);
          if ( v201 )
          {
            if ( *(_QWORD *)(*((_QWORD *)v199 + 6) + 48LL) )
            {
              DXGPUSHLOCK::AcquireExclusive((DXGPUSHLOCK *)(v201 + 32));
              --*(_DWORD *)(*((_QWORD *)v42 + 7) + 132LL);
              v202 = v255;
              v203 = *((_QWORD *)v255 + 6) + 48LL;
              v204 = *(_QWORD *)v203;
              if ( *(_QWORD *)(*(_QWORD *)v203 + 8LL) != v203
                || (v205 = *(_QWORD **)(*((_QWORD *)v255 + 6) + 56LL), *v205 != v203) )
              {
                __fastfail(3u);
              }
              *v205 = v204;
              *(_QWORD *)(v204 + 8) = v205;
              *(_QWORD *)(*((_QWORD *)v202 + 6) + 48LL) = 0;
              v206 = *((_QWORD *)v42 + 7);
              *(_QWORD *)(v206 + 40) = 0;
              ExReleasePushLockExclusiveEx(v206 + 32, 0);
              KeLeaveCriticalRegion();
              v199 = v255;
              v200 = *(struct _DXGSHAREDALLOCOBJECT **)v277;
            }
          }
        }
        v255 = v200;
        DXGDEVICE::DestroyAllocations(this, 0, 0, v199, 0, (struct _D3DDDICB_DESTROYALLOCATION2FLAGS)1);
        v199 = v255;
      }
      while ( v255 );
    }
    if ( v42 )
    {
      v207 = *((_QWORD *)v42 + 7);
      if ( !v207 )
      {
        DXGDEVICE::DestroyAllocations(this, v42, 0, v58, 0, (struct _D3DDDICB_DESTROYALLOCATION2FLAGS)1);
        goto LABEL_470;
      }
      v208 = 0;
      DXGPUSHLOCK::AcquireExclusive((DXGPUSHLOCK *)(v207 + 32));
      v209 = *((_DWORD *)v42 + 1);
      if ( (v209 & 0x10) == 0 )
      {
        *((_DWORD *)v42 + 1) = v209 | 0x10;
        v208 = 1;
      }
      v210 = *((_QWORD *)v42 + 7);
      *(_QWORD *)(v210 + 40) = 0;
      ExReleasePushLockExclusiveEx(v210 + 32, 0);
      KeLeaveCriticalRegion();
      if ( v208 )
      {
        DXGDEVICE::RemoveResourceFromDeviceList(this, v42);
        DXGHANDLETABLELOCKEXCLUSIVE::DXGHANDLETABLELOCKEXCLUSIVE((DXGHANDLETABLELOCKEXCLUSIVE *)&v283, Current);
        DXGPROCESS::GetResourceUnsafe(Current, &v274, *((unsigned int *)v42 + 4));
        if ( v274 )
        {
          v211 = (*((_DWORD *)v274 + 4) >> 6) & 0xFFFFFF;
          v212 = v211;
          v213 = Current;
          if ( v211 < *((_DWORD *)Current + 74) )
          {
            v215 = *(_DWORD *)(*((_QWORD *)Current + 35) + 16LL * v211 + 8);
            v214 = ((*((_DWORD *)v274 + 4) >> 25) & 0x60) == (v215 & 0x60) && (v215 & 0x2000) == 0 && (v215 & 0x1F) != 0;
            v213 = Current;
          }
          else
          {
            v214 = 0;
          }
          if ( v214 )
            *(_DWORD *)(16 * v212 + *((_QWORD *)v213 + 35) + 8) |= 0x2000u;
          DXGRESOURCEREFERENCE::DXGRESOURCEREFERENCE((DXGRESOURCEREFERENCE *)&v253, 0);
          DXGRESOURCEREFERENCE::MoveAssign(&v278, &v253);
          DXGRESOURCEREFERENCE::~DXGRESOURCEREFERENCE((DXGRESOURCEREFERENCE *)&v253);
        }
        else
        {
          v208 = 0;
        }
        DXGRESOURCEREFERENCE::~DXGRESOURCEREFERENCE((DXGRESOURCEREFERENCE *)&v274);
        DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)&v283);
        if ( v208 )
LABEL_468:
          DXGDEVICE::DestroyResource(this, v42, 0, (struct _D3DDDICB_DESTROYALLOCATION2FLAGS)1);
      }
    }
  }
LABEL_470:
  v216 = 0;
  v217 = v261;
  if ( v17->NumAllocations )
  {
    v218 = v270;
    do
      DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v217[v216++]);
    while ( v216 < v218->NumAllocations );
    v182 = v244;
  }
  DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v275);
  if ( v17->NumAllocations > 5 )
  {
    DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v182);
    DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v262);
    DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v276);
    DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v217);
    DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v259);
  }
  DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v287);
  DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX((DXGPROCESSCOPYPROTECTIONMUTEX *)v286);
  DXGRESOURCEREFERENCE::~DXGRESOURCEREFERENCE((DXGRESOURCEREFERENCE *)&v278);
  if ( Entry )
    ExFreeToPagedLookasideList(v285 + 13, Entry);
  return (unsigned int)DestructionBuffers;
}

```

## disassembly

```asm
0x140377080  push    rbx
0x140377082  push    rsi
0x140377083  push    rdi
0x140377084  push    r12
0x140377086  push    r13
0x140377088  push    r14
0x14037708a  push    r15
0x14037708c  sub     rsp, 350h
0x140377093  mov     rax, cs:__security_cookie
0x14037709a  xor     rax, rsp
0x14037709d  mov     [rsp+388h+var_48], rax
0x1403770a5  mov     bl, r9b
0x1403770a8  mov     [rsp+388h+var_277], bl
0x1403770af  mov     r14b, r8b
0x1403770b2  mov     [rsp+388h+AccessMode], r8b
0x1403770ba  mov     r13, rdx
0x1403770bd  mov     [rsp+388h+var_1B8], rdx
0x1403770c5  mov     r12, rcx
0x1403770c8  mov     rcx, [rsp+388h+arg_28]
0x1403770d0  mov     [rsp+388h+var_1D8], rcx
0x1403770d8  mov     [rsp+388h+var_1A0], r12
0x1403770e0  mov     [rsp+388h+var_188], rdx
0x1403770e8  mov     [rsp+388h+var_210], r8b
0x1403770f0  mov     [rsp+388h+var_270], bl
0x1403770f7  mov     rax, [rsp+388h+arg_20]
0x1403770ff  mov     [rsp+388h+var_218], rax
0x140377107  mov     [rsp+388h+var_F8], rcx
0x14037710f  mov     rax, [rsp+388h+arg_30]
0x140377117  mov     [rsp+388h+var_1E0], rax
0x14037711f  mov     rax, [rsp+388h+arg_40]
0x140377127  mov     [rsp+388h+var_1D0], rax
0x14037712f  mov     rax, [rsp+388h+arg_48]
0x140377137  mov     [rsp+388h+var_130], rax
0x14037713f  mov     rax, [rsp+388h+arg_50]
0x140377147  mov     [rsp+388h+var_240], rax
0x14037714f  mov     rax, [rsp+388h+arg_58]
0x140377157  mov     [rsp+388h+var_1C8], rax
0x14037715f  mov     rax, [rsp+388h+arg_60]
0x140377167  mov     [rsp+388h+var_1F8], rax
0x14037716f  mov     rcx, [r12+10h]; this
0x140377174  call    ?IsCoreResourceSharedOwner@ADAPTER_RENDER@@QEBAEXZ; ADAPTER_RENDER::IsCoreResourceSharedOwner(void)
0x140377179  xor     r15d, r15d
0x14037717c  test    al, al
0x14037717e  jnz     short loc_1403771D3
0x140377180  lea     esi, [r15+1]
0x140377184  mov     ecx, esi
0x140377186  call    cs:__imp_WdLogSingleEntry0
0x14037718d  nop     dword ptr [rax+rax+00h]
0x140377192  mov     eax, 12F7h
0x140377197  mov     cs:WdLogGlobalForLineNumber, eax
0x14037719d  mov     [rsp+388h+Src], r15
0x1403771a2  mov     [rsp+388h+var_350], r15
0x1403771a7  mov     [rsp+388h+var_358], r15
0x1403771ac  mov     [rsp+388h+HandleInformation], r15
0x1403771b1  mov     [rsp+388h+Object], rax
0x1403771b6  lea     r9, aGetrendercoreI_1; "GetRenderCore()->IsCoreResourceSharedOw"...
0x1403771bd  mov     edi, 0FFFFFFFFh
0x1403771c2  mov     r8d, edi
0x1403771c5  mov     edx, 40002h
0x1403771ca  xor     ecx, ecx
0x1403771cc  call    DxgkLogInternalTriageEvent
0x1403771d1  jmp     short loc_1403771DD
0x1403771d3  mov     esi, 1
0x1403771d8  mov     edi, 0FFFFFFFFh
0x1403771dd  test    r14b, r14b
0x1403771e0  jz      short loc_14037722E
0x1403771e2  test    bl, bl
0x1403771e4  jz      short loc_14037722E
0x1403771e6  mov     ecx, esi
0x1403771e8  call    cs:__imp_WdLogSingleEntry0
0x1403771ef  nop     dword ptr [rax+rax+00h]
0x1403771f4  mov     eax, 12FCh
0x1403771f9  mov     cs:WdLogGlobalForLineNumber, eax
0x1403771ff  mov     [rsp+388h+Src], r15
0x140377204  mov     [rsp+388h+var_350], r15
0x140377209  mov     [rsp+388h+var_358], r15
0x14037720e  mov     [rsp+388h+HandleInformation], r15
0x140377213  mov     [rsp+388h+Object], rax
0x140377218  lea     r9, aUsermodeOpensh; "!(UserMode && OpenShared)"
0x14037721f  mov     r8d, edi
0x140377222  mov     edx, 40002h
0x140377227  xor     ecx, ecx
0x140377229  call    DxgkLogInternalTriageEvent
0x14037722e  mov     rax, [r12+10h]
0x140377233  mov     rcx, [rax+10h]
0x140377237  mov     al, [rcx+0D1h]
0x14037723d  mov     [rsp+388h+var_276], al
0x140377244  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x140377249  mov     [rsp+388h+var_220], rax
0x140377251  mov     edx, [r13+38h]
0x140377255  bt      edx, 0Bh
0x140377259  jnb     short loc_1403772D1
0x14037725b  mov     rcx, [r12+10h]
0x140377260  mov     r8, [rcx+10h]
0x140377264  mov     ecx, [r8+0A24h]
0x14037726b  test    cl, 10h
0x14037726e  jnz     short loc_14037729F
0x140377270  mov     rsi, 0FFFFFFFFC000000Dh
0x140377277  mov     r8, rsi
0x14037727a  mov     rdx, r12
0x14037727d  mov     ecx, 3
0x140377282  call    cs:__imp_WdLogSingleEntry2
0x140377289  nop     dword ptr [rax+rax+00h]
0x14037728e  mov     cs:WdLogGlobalForLineNumber, 1305h
0x140377298  mov     eax, esi
0x14037729a  jmp     loc_14037A830
0x14037729f  test    dl, 2
0x1403772a2  jnz     short loc_1403772D1
0x1403772a4  mov     r9, rsi
0x1403772a7  mov     rsi, 0FFFFFFFFC000000Dh
0x1403772ae  mov     r8, rsi
0x1403772b1  mov     rdx, r12
0x1403772b4  mov     ecx, 3
0x1403772b9  call    cs:__imp_WdLogSingleEntry3
0x1403772c0  nop     dword ptr [rax+rax+00h]
0x1403772c5  mov     cs:WdLogGlobalForLineNumber, 130Ah
0x1403772cf  jmp     short loc_140377298
0x1403772d1  mov     rcx, [r12+10h]
0x1403772d6  mov     [rsp+388h+var_228], rcx
0x1403772de  mov     eax, [r13+2Ch]
0x1403772e2  cmp     eax, 5
0x1403772e5  jbe     loc_1403775A0
0x1403772eb  mov     [rsp+388h+var_200], r15
0x1403772f3  mov     r14, r15
0x1403772f6  mov     [rsp+388h+var_268], r15
0x1403772fe  mov     [rsp+388h+var_1B0], r15
0x140377306  mov     ecx, eax
0x140377308  lea     rax, [rax+rax*2]
0x14037730c  shl     rax, 5
0x140377310  mov     [rsp+388h+Entry], rax
0x140377318  cmp     rdi, rax
0x14037731b  sbb     ebx, ebx
0x14037731d  and     ebx, 0C0000095h
0x140377323  cmp     rax, rdi
0x140377326  ja      short loc_140377369
0x140377328  mov     eax, 60h ; '`'
0x14037732d  mul     rcx
0x140377330  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140377337  cmovb   rax, rcx
0x14037733b  mov     edx, 4B677844h
0x140377340  mov     r8d, 100h
0x140377346  mov     rcx, rax
0x140377349  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14037734e  mov     r14, rax
0x140377351  mov     [rsp+388h+var_268], rax
0x140377359  mov     [rsp+388h+var_1B0], rax
0x140377361  mov     rax, [rsp+388h+Entry]
0x140377369  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14037736d  mov     [rsp+388h+var_1E8], r15
0x140377375  cmp     rax, rdi
0x140377378  ja      short loc_1403773B7
0x14037737a  mov     edx, [r13+2Ch]
0x14037737e  imul    rax, rdx, 58h ; 'X'
0x140377382  cmp     rdi, rax
0x140377385  sbb     ebx, ebx
0x140377387  and     ebx, 0C0000095h
0x14037738d  cmp     rax, rdi
0x140377390  ja      short loc_1403773B7
0x140377392  lea     eax, [rcx+59h]
0x140377395  mul     rdx
0x140377398  cmovb   rax, rcx
0x14037739c  mov     edx, 4B677844h
0x1403773a1  mov     r8d, 102h
0x1403773a7  mov     rcx, rax
0x1403773aa  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1403773af  mov     [rsp+388h+var_1E8], rax
0x1403773b7  mov     [rsp+388h+var_168], r15
0x1403773bf  test    ebx, ebx
0x1403773c1  js      short loc_14037740B
0x1403773c3  mov     ecx, [r13+2Ch]
0x1403773c7  mov     eax, ecx
0x1403773c9  shl     rax, 5
0x1403773cd  cmp     rdi, rax
0x1403773d0  sbb     ebx, ebx
0x1403773d2  and     ebx, 0C0000095h
0x1403773d8  cmp     rax, rdi
0x1403773db  ja      short loc_14037740B
0x1403773dd  mov     eax, 20h ; ' '
0x1403773e2  mul     rcx
0x1403773e5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1403773ec  cmovb   rax, rcx
0x1403773f0  mov     edx, 4B677844h
0x1403773f5  mov     r8d, 100h
0x1403773fb  mov     rcx, rax
0x1403773fe  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140377403  mov     [rsp+388h+var_168], rax
0x14037740b  mov     rdx, r15
0x14037740e  mov     [rsp+388h+var_1F0], rdx
0x140377416  test    ebx, ebx
0x140377418  js      loc_1403774C0
0x14037741e  mov     ecx, [r13+2Ch]
0x140377422  lea     rax, ds:0[rcx*8]
0x14037742a  cmp     rdi, rax
0x14037742d  sbb     ebx, ebx
0x14037742f  and     ebx, 0C0000095h
0x140377435  cmp     rax, rdi
0x140377438  ja      loc_1403774C0
0x14037743e  mov     eax, 8
0x140377443  mul     rcx
0x140377446  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14037744d  cmovb   rax, rcx
0x140377451  mov     edx, 4B677844h
0x140377456  mov     r8d, 100h
0x14037745c  mov     rcx, rax
0x14037745f  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140377464  mov     rdx, rax
0x140377467  mov     [rsp+388h+var_1F0], rax
0x14037746f  mov     al, [rsp+388h+AccessMode]
0x140377476  test    al, al
0x140377478  jz      short loc_1403774CC
0x14037747a  mov     ecx, [r13+2Ch]
0x14037747e  mov     eax, 8
0x140377483  mul     rcx
0x140377486  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14037748d  cmovb   rax, rcx
0x140377491  mov     edx, 4B677844h
0x140377496  mov     r8d, 100h
0x14037749c  mov     rcx, rax
0x14037749f  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1403774a4  mov     r8, rax
0x1403774a7  mov     [rsp+388h+var_200], rax
0x1403774af  mov     al, [rsp+388h+AccessMode]
0x1403774b6  mov     rdx, [rsp+388h+var_1F0]
0x1403774be  jmp     short loc_1403774CF
0x1403774c0  mov     al, [rsp+388h+AccessMode]
0x1403774c7  mov     r8, rdx
0x1403774ca  jmp     short loc_1403774CF
0x1403774cc  mov     r8, r15
0x1403774cf  test    ebx, ebx
0x1403774d1  js      short loc_14037750A
0x1403774d3  test    r14, r14
0x1403774d6  jz      short loc_14037750A
0x1403774d8  cmp     [rsp+388h+var_1E8], r15
0x1403774e0  jz      short loc_14037750A
0x1403774e2  cmp     [rsp+388h+var_168], r15
0x1403774ea  jz      short loc_14037750A
0x1403774ec  test    rdx, rdx
0x1403774ef  jz      short loc_14037750A
0x1403774f1  mov     [rsp+388h+Entry], r15
0x1403774f9  test    r8, r8
0x1403774fc  jnz     loc_140377665
0x140377502  test    al, al
0x140377504  jz      loc_140377665
0x14037750a  mov     rcx, r14; void *
0x14037750d  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x140377512  mov     rcx, [rsp+388h+var_1E8]; void *
0x14037751a  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x14037751f  mov     rcx, [rsp+388h+var_168]; void *
0x140377527  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x14037752c  mov     rcx, [rsp+388h+var_1F0]; void *
0x140377534  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x140377539  mov     rcx, [rsp+388h+var_200]; void *
0x140377541  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x140377546  mov     r8d, [r13+2Ch]
0x14037754a  test    ebx, ebx
0x14037754c  jns     short loc_140377571
0x14037754e  movsxd  r9, ebx
0x140377551  mov     rdx, r12
0x140377554  mov     ecx, 3
0x140377559  call    cs:__imp_WdLogSingleEntry3
0x140377560  nop     dword ptr [rax+rax+00h]
0x140377565  mov     cs:WdLogGlobalForLineNumber, 136Ch
0x14037756f  jmp     short loc_140377599
0x140377571  mov     rbx, 0FFFFFFFFC0000017h
0x140377578  mov     r9, rbx
0x14037757b  mov     rdx, r12
0x14037757e  mov     ecx, 3
0x140377583  call    cs:__imp_WdLogSingleEntry3
0x14037758a  nop     dword ptr [rax+rax+00h]
0x14037758f  mov     cs:WdLogGlobalForLineNumber, 1373h
0x140377599  mov     eax, ebx
0x14037759b  jmp     loc_14037A830
0x1403775a0  add     rcx, 680h; Lookaside
0x1403775a7  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1403775ae  nop     dword ptr [rax+rax+00h]
0x1403775b3  mov     r14, rax
0x1403775b6  mov     [rsp+388h+var_268], rax
0x1403775be  test    rax, rax
0x1403775c1  jnz     short loc_14037761A
0x1403775c3  mov     rdx, r12
0x1403775c6  lea     ecx, [rax+6]
0x1403775c9  call    cs:__imp_WdLogSingleEntry1
0x1403775d0  nop     dword ptr [rax+rax+00h]
0x1403775d5  mov     cs:WdLogGlobalForLineNumber, 137Fh
0x1403775df  mov     [rsp+388h+Src], r15
0x1403775e4  mov     [rsp+388h+var_350], r15
0x1403775e9  mov     [rsp+388h+var_358], r15
0x1403775ee  mov     [rsp+388h+HandleInformation], r15
0x1403775f3  mov     [rsp+388h+Object], r12
0x1403775f8  lea     r9, aDevice0xI64xOu_1; "Device 0x%I64x: Out of memory allocatin"...
0x1403775ff  mov     r8d, edi
0x140377602  mov     edx, 40001h
0x140377607  xor     ecx, ecx
0x140377609  call    DxgkLogInternalTriageEvent
0x14037760e  mov     rax, 0FFFFFFFFC0000017h
0x140377615  jmp     loc_14037A830
0x14037761a  mov     [rsp+388h+Entry], r14
0x140377622  add     rax, 2D0h
0x140377628  mov     [rsp+388h+var_1E8], rax
0x140377630  lea     rax, [r14+1E0h]
  ... truncated ...
```
