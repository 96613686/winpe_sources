# CmsVolumeContainer::CompactAndCompressContainer(CmsTransactionContext *,unsigned __int64,_MS_COMPRESSION_FORMATS,ushort,ulong,_RANGE_TUPLE const *,unsigned __int64)

- ea: `0x1c00d34d0`
- end: `0x1c00d6e8a`
- name: `?CompactAndCompressContainer@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@_KW4_MS_COMPRESSION_FORMATS@@GKPEBU_RANGE_TUPLE@@1@Z`
- size: `14778`
- prototype: ``
- caller_count: `2`
- callee_count: `71`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1c00c0b98`
- `0x1c00e23e8`

## callees

- `0x1c0004d98`
- `0x1c00059f4`
- `0x1c0014510`
- `0x1c0014760`
- `0x1c002313c`
- `0x1c0023ee4`
- `0x1c0024964`
- `0x1c0025620`
- `0x1c0025f98`
- `0x1c0025fb8`
- `0x1c0025ff0`
- `0x1c00274f4`
- `0x1c0027a38`
- `0x1c002981c`
- `0x1c0029acc`
- `0x1c002a564`
- `0x1c002a87c`
- `0x1c002b8ec`
- `0x1c002bca4`
- `0x1c002c7a0`
- `0x1c002cc80`
- `0x1c002cd38`
- `0x1c002d368`
- `0x1c00341c0`
- `0x1c003552c`
- `0x1c0035848`
- `0x1c0036a10`
- `0x1c003efcc`
- `0x1c003f570`
- `0x1c00439f0`
- `0x1c0047d84`
- `0x1c0050a94`
- `0x1c0057b20`
- `0x1c005a66c`
- `0x1c0067e70`
- `0x1c0068960`
- `0x1c006a644`
- `0x1c006ac80`
- `0x1c006acc0`
- `0x1c006af80`
- `0x1c0090d20`
- `0x1c00b12c0`
- `0x1c00b1354`
- `0x1c00b2fcc`
- `0x1c00b3400`
- `0x1c00b84b4`
- `0x1c00beafc`
- `0x1c00c16dc`
- `0x1c00c2e30`
- `0x1c00ca778`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00d5f63`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00d6584`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00d69f3`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00d5f63`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00d6584`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00d69f3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c00d3fbe`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c00d4014`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c00d4ad9`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c00d4b6d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c00d3fbe`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c00d4014`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c00d4ad9`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c00d4b6d`
- `ntoskrnl!RtlInitializeBitMap` at `0x1c00d3d60`
- `ntoskrnl!RtlInitializeBitMap` at `0x1c00d3dce`
- `ntoskrnl!RtlInitializeBitMap` at `0x1c00d4172`
- `ntoskrnl!RtlInitializeBitMap` at `0x1c00d4239`
- `ntoskrnl!RtlInitializeBitMap` at `0x1c00d68dd`
- `ntoskrnl!RtlInitializeBitMap` at `0x1c00d3d60`
- `ntoskrnl!RtlInitializeBitMap` at `0x1c00d3dce`
- `ntoskrnl!RtlInitializeBitMap` at `0x1c00d4172`
- `ntoskrnl!RtlInitializeBitMap` at `0x1c00d4239`
- `ntoskrnl!RtlInitializeBitMap` at `0x1c00d68dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00d4414`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00d6d1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00d6d81`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00d6da4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00d6e08`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00d6e2c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00d6e50`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00d4414`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00d6d1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00d6d81`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00d6da4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00d6e08`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00d6e2c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00d6e50`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00d42b3`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00d6067`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00d65bf`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00d6a84`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00d42b3`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00d6067`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00d65bf`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00d6a84`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c00d6c8b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c00d6c8b`
- `ntoskrnl!KdDebuggerEnabled` at `0x1c00d39cf`
- `ntoskrnl!KdDebuggerEnabled` at `0x1c00d4753`
- `ntoskrnl!KdDebuggerEnabled` at `0x1c00d4905`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1c00d4253`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1c00d4253`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x1c00d66d2`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x1c00d66d2`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1c00d6729`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1c00d6729`
- `ntoskrnl!RtlNumberOfSetBitsInRange` at `0x1c00d4e8f`
- `ntoskrnl!RtlNumberOfSetBitsInRange` at `0x1c00d4e8f`
- `ntoskrnl!RtlSetAllBits` at `0x1c00d4185`
- `ntoskrnl!RtlSetAllBits` at `0x1c00d68f0`
- `ntoskrnl!RtlSetAllBits` at `0x1c00d4185`
- `ntoskrnl!RtlSetAllBits` at `0x1c00d68f0`
- `ntoskrnl!RtlNumberOfSetBits` at `0x1c00d42e1`
- `ntoskrnl!RtlNumberOfSetBits` at `0x1c00d4a1c`
- `ntoskrnl!RtlNumberOfSetBits` at `0x1c00d4bcb`
- `ntoskrnl!RtlNumberOfSetBits` at `0x1c00d5b49`
- `ntoskrnl!RtlNumberOfSetBits` at `0x1c00d60fa`
- `ntoskrnl!RtlNumberOfSetBits` at `0x1c00d42e1`
- `ntoskrnl!RtlNumberOfSetBits` at `0x1c00d4a1c`
- `ntoskrnl!RtlNumberOfSetBits` at `0x1c00d4bcb`
- `ntoskrnl!RtlNumberOfSetBits` at `0x1c00d5b49`
- `ntoskrnl!RtlNumberOfSetBits` at `0x1c00d60fa`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00d3857`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00d38a8`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00d47d6`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00d6bbe`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00d3857`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00d38a8`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00d47d6`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00d6bbe`
- `HAL!KeQueryPerformanceCounter` at `0x1c00d371a`
- `HAL!KeQueryPerformanceCounter` at `0x1c00d4f01`
- `HAL!KeQueryPerformanceCounter` at `0x1c00d5075`
- `HAL!KeQueryPerformanceCounter` at `0x1c00d50dc`
- `HAL!KeQueryPerformanceCounter` at `0x1c00d5210`
- `HAL!KeQueryPerformanceCounter` at `0x1c00d56e7`
- `HAL!KeQueryPerformanceCounter` at `0x1c00d58da`
- `HAL!KeQueryPerformanceCounter` at `0x1c00d5965`
- `HAL!KeQueryPerformanceCounter` at `0x1c00d5aaa`
- `HAL!KeQueryPerformanceCounter` at `0x1c00d371a`
- `HAL!KeQueryPerformanceCounter` at `0x1c00d4f01`
- `HAL!KeQueryPerformanceCounter` at `0x1c00d5075`
- `HAL!KeQueryPerformanceCounter` at `0x1c00d50dc`
- `HAL!KeQueryPerformanceCounter` at `0x1c00d5210`
- `HAL!KeQueryPerformanceCounter` at `0x1c00d56e7`
- `HAL!KeQueryPerformanceCounter` at `0x1c00d58da`
- `HAL!KeQueryPerformanceCounter` at `0x1c00d5965`
- `HAL!KeQueryPerformanceCounter` at `0x1c00d5aaa`

## pseudocode

```c
__int64 __fastcall CmsVolumeContainer::CompactAndCompressContainer(
        __int64 a1,
        __int64 a2,
        unsigned __int64 a3,
        unsigned int a4,
        __int64 a5,
        unsigned int a6,
        _OWORD *a7,
        signed __int64 a8)
{
  __int64 v8; // rax
  __int64 v9; // r14
  __int64 v10; // r13
  unsigned __int64 v13; // rbx
  char v14; // di
  struct SmsContainer *v15; // r15
  CmsVolume *v16; // rcx
  __int64 v17; // r11
  int v18; // esi
  char v19; // bl
  struct SmsContainer *v20; // r9
  int v21; // eax
  int ContainerReference; // eax
  struct CmsTransactionContext *v23; // rdx
  CmsVolumeContainer *v24; // rcx
  __int64 v25; // r9
  unsigned __int8 v26; // al
  unsigned int v27; // r10d
  int v28; // edx
  __int64 v29; // rax
  char v30; // al
  CmsVolume *v31; // rcx
  CmsVolume *v32; // rbx
  __int64 v33; // rcx
  struct SmsCompactionUndoChain *v34; // r8
  struct SmsContainer *v35; // r12
  struct SmsContainer *v36; // r13
  __int16 v37; // dx
  __int16 v38; // r9
  _QWORD *v39; // r11
  __int64 v40; // rbx
  __int16 v41; // ax
  __int64 v42; // r10
  _QWORD *v43; // r11
  __int64 v44; // rbx
  __int16 v45; // ax
  __int64 v46; // r10
  unsigned __int16 k; // r10
  unsigned int v48; // ecx
  __m128i *v49; // rax
  __int16 v50; // r10
  __int64 v51; // r11
  struct SmsContainer *v52; // r8
  _DWORD *v53; // r8
  char *v54; // r9
  int v55; // r10d
  _DWORD *v56; // rcx
  unsigned int v57; // edx
  unsigned int v58; // eax
  CmsTable *v59; // rcx
  int Row; // eax
  __int64 v61; // rax
  CmsTable *v62; // rcx
  int v63; // eax
  ULONG v64; // r8d
  int v65; // eax
  SmsAllocationRegionEx *v66; // rcx
  SmsAllocationRegionEx *v67; // rbx
  int v68; // eax
  __int64 v69; // rcx
  __int64 v70; // rax
  CmsAllocator *v71; // rcx
  int v72; // eax
  __int64 v73; // rax
  unsigned int v74; // eax
  SIZE_T v75; // rax
  unsigned __int64 v76; // kr00_8
  PVOID PoolWithTag; // rax
  int EmbeddedContainers; // eax
  char *v79; // rax
  CmsContainerRangeMap *v80; // rbx
  char v81; // cl
  unsigned int v82; // edx
  int v83; // eax
  int v84; // eax
  int v85; // eax
  _DWORD *v86; // rbx
  __int64 v87; // rax
  int v88; // eax
  _DWORD *v89; // rsi
  _QWORD *v90; // rdx
  __int64 v91; // rax
  SmsAllocationRegionEx *v92; // rbx
  CmsVolume *v93; // rcx
  struct CmsAllocator *v94; // r8
  ULONG v95; // r12d
  int v96; // eax
  CmsVolume *v97; // rcx
  unsigned __int8 IsVolumeOnSmr; // al
  CmsVolume *v99; // rcx
  CmsVolume *v100; // r9
  unsigned __int64 v101; // rbx
  __m128i v102; // xmm6
  __int64 v103; // r11
  CmsVolume *v104; // rcx
  CmsVolume *v105; // rcx
  union _LCN_TUPLE *v106; // r11
  unsigned __int64 v107; // rsi
  int v108; // r15d
  unsigned int v109; // edi
  unsigned int v110; // ecx
  union _LCN_TUPLE **v111; // rax
  __int64 v112; // rbx
  __int16 v113; // si
  CmsVolume *v114; // r10
  int v115; // ecx
  __int64 v116; // r9
  struct SmsAllocationRegionEx *v117; // r11
  unsigned __int64 v118; // r8
  int v119; // ecx
  struct SmsAllocationRegionEx **v120; // rax
  __int64 v121; // r10
  __int64 v122; // rcx
  int v123; // r10d
  unsigned __int64 v124; // r12
  int v125; // eax
  __int64 v126; // rcx
  __int64 v127; // rax
  int v128; // eax
  CmsVolume *v129; // rcx
  __int64 v130; // rdx
  unsigned __int8 v131; // r9
  unsigned int v132; // ecx
  struct SmsAllocationRegionEx **v133; // rax
  struct SmsAllocationRegionEx *v134; // rcx
  __int64 *v135; // rax
  __int64 v136; // rdx
  CmsVolume *v137; // rcx
  unsigned __int64 v138; // r8
  unsigned __int64 v139; // r9
  unsigned int v140; // r11d
  int v141; // eax
  int v142; // eax
  unsigned __int64 v143; // r9
  struct _RTL_BITMAP *v144; // rsi
  struct _RTL_BITMAP *v145; // rax
  char v146; // dl
  __int64 v147; // rcx
  PVOID v148; // rax
  CmsVolume *v149; // rcx
  ULONG v150; // eax
  int CompressedContainerRangeInternal; // eax
  char v152; // dl
  __int64 *v153; // rbx
  __int64 v154; // rax
  int v155; // eax
  __int64 v156; // rbx
  unsigned __int16 v157; // cx
  int v158; // eax
  int v159; // eax
  unsigned int NextForwardRunSet; // esi
  unsigned __int64 v161; // r13
  char *v162; // rdi
  char *v163; // r15
  unsigned int v164; // eax
  int v165; // esi
  __int64 v166; // rax
  unsigned int v167; // r12d
  unsigned int v168; // ecx
  LARGE_INTEGER v169; // rbx
  char v170; // bl
  unsigned __int64 v171; // rdx
  __int128 v172; // xmm0
  int v173; // eax
  unsigned int v174; // r8d
  int v175; // r10d
  unsigned int v176; // edx
  __int64 v177; // rax
  int v178; // ecx
  __int64 v179; // rdx
  unsigned int v180; // eax
  unsigned int v181; // r8d
  int v182; // ecx
  unsigned int v183; // eax
  int v184; // eax
  LARGE_INTEGER v185; // rax
  __int64 v186; // r10
  LARGE_INTEGER v187; // rbx
  int v188; // eax
  LARGE_INTEGER v189; // rax
  CmsVolume *v190; // rcx
  __int64 v191; // rdx
  __int64 v192; // r9
  signed __int64 v193; // rdx
  __int64 v194; // rcx
  int v195; // eax
  unsigned __int8 v196; // al
  int v197; // r10d
  __int64 v198; // r11
  __int64 v199; // rdx
  LARGE_INTEGER v200; // rax
  unsigned __int8 v201; // al
  char v202; // r10
  unsigned __int64 v203; // rcx
  unsigned __int64 v204; // r8
  unsigned __int64 v205; // rax
  CmsVolume *v206; // rcx
  char v207; // r11
  unsigned __int64 v208; // rax
  __int64 v209; // rcx
  _OWORD *v210; // rbx
  __int128 v211; // xmm1
  __int128 v212; // xmm0
  __int128 v213; // xmm1
  __int64 v214; // rax
  int v215; // eax
  __int64 v216; // rcx
  __int64 v217; // rbx
  __int64 v218; // rax
  unsigned __int64 v219; // rbx
  PVOID v220; // rsi
  int v221; // eax
  int v222; // r12d
  int v223; // eax
  __int64 v224; // rax
  struct SmsContainer *v225; // r12
  LARGE_INTEGER v226; // rax
  __int64 v227; // rdx
  __int64 *v228; // rsi
  int v229; // eax
  unsigned __int64 v230; // r15
  struct SmsContainer *v231; // rsi
  unsigned __int64 v232; // rax
  CmsVolume *v233; // r8
  unsigned __int64 v234; // r12
  int v235; // ecx
  unsigned __int64 v236; // r15
  _DWORD *v237; // r8
  unsigned __int64 v238; // rcx
  unsigned __int64 v239; // rdx
  int v240; // eax
  LARGE_INTEGER v241; // rax
  __int64 v242; // r10
  LARGE_INTEGER v243; // rbx
  unsigned __int64 v244; // r9
  __int64 v245; // rcx
  unsigned __int8 v246; // al
  __int64 v247; // rcx
  LARGE_INTEGER v248; // rax
  CmsVolume *v249; // rcx
  __int64 v250; // rdx
  volatile signed __int64 *v251; // r8
  signed __int64 v252; // rdx
  __int64 v253; // rcx
  _DWORD *v254; // r9
  __int64 *v255; // rsi
  int v256; // eax
  LONGLONG v257; // rax
  int v258; // eax
  unsigned int v259; // r12d
  int updated; // eax
  int v261; // r8d
  __m128i *v262; // rax
  int v263; // eax
  _OWORD *v264; // rbx
  _OWORD *v265; // rax
  int v266; // ecx
  __int64 v267; // xmm1_8
  __m128i *v268; // rax
  unsigned int i; // r8d
  __int64 v270; // rax
  __int64 v271; // rdx
  unsigned int v272; // eax
  int v273; // eax
  int ContainerCompressionRedo; // eax
  __int64 *v275; // rax
  int v276; // ecx
  unsigned __int64 v277; // rbx
  __int64 v278; // rdx
  char v279; // al
  int v280; // eax
  struct SmsContainer *v281; // r8
  unsigned __int64 v282; // rcx
  int v283; // eax
  unsigned __int64 v284; // rax
  int inserted; // eax
  unsigned __int64 v286; // r8
  int v287; // eax
  int v288; // eax
  struct SmsCompactionUndoChain *v289; // rbx
  struct SmsCompactionUndoChain *v290; // rbx
  int v291; // eax
  __int64 v292; // rcx
  __int64 v293; // rax
  void *v294; // rcx
  struct SmsCompactionUndoChain *v295; // rbx
  unsigned int v296; // eax
  unsigned __int64 NextContainerId; // r12
  __int64 v298; // rcx
  int v299; // eax
  int v300; // eax
  int v301; // eax
  unsigned int v302; // r9d
  unsigned int v303; // ecx
  unsigned __int64 v304; // rax
  SmsAllocationRegionEx *v305; // rbx
  int v306; // eax
  int v307; // eax
  _QWORD *v308; // rsi
  unsigned __int64 TotalFree; // rax
  __int64 v310; // rbx
  __int64 v311; // rax
  int v312; // eax
  int v313; // r8d
  __m128i *v314; // rax
  int v315; // eax
  _OWORD *v316; // rbx
  _OWORD *v317; // rax
  __int64 v318; // xmm1_8
  __m128i *v319; // rax
  int v320; // ecx
  unsigned int v321; // r8d
  __int64 v322; // rax
  __int64 v323; // rdx
  unsigned int v324; // eax
  int v325; // eax
  int v326; // eax
  struct SmsCompactionUndoChain *j; // rbx
  int v328; // eax
  int v329; // eax
  unsigned int *v330; // r8
  unsigned int v331; // edx
  unsigned int v332; // eax
  _BYTE *v333; // r12
  int v334; // ecx
  __m128i *v335; // rax
  char *v336; // rbx
  unsigned int v337; // ecx
  __int64 v338; // rax
  __int64 v339; // rcx
  int v340; // ebx
  int v341; // r12d
  SmsAllocationRegionEx *v342; // r15
  unsigned __int64 v343; // rax
  __int64 v344; // r8
  unsigned __int64 v345; // r9
  struct _SmsContainerRangeMapListHead *v346; // rax
  struct CmsTransactionContext *v347; // rdx
  struct SmsContainer *v348; // r8
  SmsAllocationRegionEx *v349; // rbx
  int v350; // eax
  PERESOURCE v351; // rbx
  struct CmsAllocator *v352; // r8
  CmsVolume *v353; // rcx
  CmsVolume *v354; // rcx
  SmsAllocationRegionEx *v355; // rbx
  struct SmsCompactionUndoChain *v356; // rbx
  __int64 v357; // rcx
  __int64 v358; // rax
  __int64 v359; // rdx
  void *v360; // rcx
  volatile signed __int32 *v361; // rax
  CmsAllocator *v362; // rcx
  __int64 v363; // r8
  struct SmsCompactionUndoChain *v364; // rbx
  unsigned __int64 v365; // rdi
  struct _ERESOURCE *v366; // rbx
  char v367; // r12
  unsigned __int64 v368; // r15
  unsigned __int64 v369; // r8
  struct SmsContainer *v370; // r8
  PVOID v371; // rcx
  signed __int64 v372; // rcx
  PVOID v373; // rcx
  signed __int64 v374; // rcx
  CmsContainerRangeMap *v375; // rbx
  unsigned int v376; // edx
  struct _RTL_BITMAP *v378; // [rsp+28h] [rbp-F0h]
  struct _SmsQuickIndex *v379; // [rsp+30h] [rbp-E8h]
  struct _RTL_BITMAP *v380; // [rsp+38h] [rbp-E0h]
  struct _RTL_BITMAP *v381; // [rsp+38h] [rbp-E0h]
  struct _RTL_BITMAP *v382; // [rsp+38h] [rbp-E0h]
  PVOID *v383; // [rsp+40h] [rbp-D8h]
  unsigned int v384; // [rsp+40h] [rbp-D8h]
  unsigned int v385; // [rsp+40h] [rbp-D8h]
  char v386; // [rsp+98h] [rbp-80h]
  char v387; // [rsp+99h] [rbp-7Fh]
  char v388; // [rsp+9Ah] [rbp-7Eh]
  char v389; // [rsp+9Bh] [rbp-7Dh]
  struct SmsContainer *v390; // [rsp+A0h] [rbp-78h] BYREF
  unsigned __int16 v391[2]; // [rsp+A8h] [rbp-70h] BYREF
  char v392; // [rsp+ACh] [rbp-6Ch]
  ULONG v393; // [rsp+B0h] [rbp-68h]
  char v394; // [rsp+B4h] [rbp-64h] BYREF
  bool v395; // [rsp+B5h] [rbp-63h] BYREF
  unsigned __int16 v396; // [rsp+B6h] [rbp-62h]
  unsigned __int16 v397; // [rsp+B8h] [rbp-60h]
  unsigned int v398; // [rsp+BCh] [rbp-5Ch]
  struct SmsContainer *v399; // [rsp+C0h] [rbp-58h]
  char v400; // [rsp+C8h] [rbp-50h] BYREF
  unsigned int v401; // [rsp+D0h] [rbp-48h]
  unsigned __int64 v402; // [rsp+D8h] [rbp-40h]
  PVOID v403; // [rsp+E0h] [rbp-38h]
  SmsAllocationRegionEx *v404; // [rsp+E8h] [rbp-30h] BYREF
  int v405; // [rsp+F0h] [rbp-28h]
  unsigned __int64 v406; // [rsp+F8h] [rbp-20h]
  PVOID P; // [rsp+100h] [rbp-18h]
  int v408; // [rsp+108h] [rbp-10h]
  int v409; // [rsp+10Ch] [rbp-Ch]
  unsigned int v410; // [rsp+110h] [rbp-8h] BYREF
  struct SmsCompactionUndoChain *v411; // [rsp+118h] [rbp+0h] BYREF
  unsigned __int64 v412; // [rsp+120h] [rbp+8h]
  unsigned __int64 v413; // [rsp+128h] [rbp+10h]
  unsigned int v414; // [rsp+130h] [rbp+18h] BYREF
  unsigned int v415; // [rsp+134h] [rbp+1Ch] BYREF
  CmsContainerRangeMap *v416; // [rsp+138h] [rbp+20h]
  unsigned int v417; // [rsp+140h] [rbp+28h] BYREF
  unsigned int *v418; // [rsp+148h] [rbp+30h]
  struct SmsContainer *v419; // [rsp+150h] [rbp+38h] BYREF
  struct SmsContainer *v420; // [rsp+158h] [rbp+40h] BYREF
  int v421; // [rsp+160h] [rbp+48h] BYREF
  int v422; // [rsp+164h] [rbp+4Ch] BYREF
  unsigned int v423; // [rsp+168h] [rbp+50h]
  unsigned int v424; // [rsp+16Ch] [rbp+54h]
  CmsVolumeAnalyzer *v425; // [rsp+170h] [rbp+58h]
  struct SmsContainer *v426; // [rsp+178h] [rbp+60h]
  unsigned __int64 v427; // [rsp+180h] [rbp+68h]
  struct _RTL_BITMAP v428; // [rsp+188h] [rbp+70h] BYREF
  __int64 *v429; // [rsp+198h] [rbp+80h]
  __int64 v430; // [rsp+1A0h] [rbp+88h] BYREF
  void *Src; // [rsp+1A8h] [rbp+90h]
  LARGE_INTEGER PerformanceCounter; // [rsp+1B0h] [rbp+98h]
  _BYTE *v433; // [rsp+1B8h] [rbp+A0h]
  unsigned __int64 v434; // [rsp+1C0h] [rbp+A8h] BYREF
  PERESOURCE Resource; // [rsp+1C8h] [rbp+B0h] BYREF
  PVOID v436; // [rsp+1D0h] [rbp+B8h] BYREF
  __int128 v437; // [rsp+1D8h] [rbp+C0h] BYREF
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+1E8h] [rbp+D0h] BYREF
  _DWORD *v439; // [rsp+1F0h] [rbp+D8h]
  struct SmsContainer *v440; // [rsp+1F8h] [rbp+E0h] BYREF
  PVOID v441; // [rsp+200h] [rbp+E8h]
  _OWORD *v442; // [rsp+208h] [rbp+F0h] BYREF
  struct SmsContainer *v443; // [rsp+210h] [rbp+F8h] BYREF
  struct SmsContainer *v444; // [rsp+218h] [rbp+100h] BYREF
  struct _RTL_BITMAP BitMapHeader; // [rsp+220h] [rbp+108h] BYREF
  struct SmsContainer *v446; // [rsp+230h] [rbp+118h] BYREF
  LARGE_INTEGER v447; // [rsp+238h] [rbp+120h]
  struct SmsContainer *v448; // [rsp+240h] [rbp+128h] BYREF
  __int64 v449; // [rsp+248h] [rbp+130h]
  void *v450; // [rsp+250h] [rbp+138h] BYREF
  struct SmsContainer *v451; // [rsp+258h] [rbp+140h] BYREF
  struct SmsAllocationRegionEx *v452; // [rsp+260h] [rbp+148h] BYREF
  LARGE_INTEGER v453; // [rsp+268h] [rbp+150h]
  struct SmsContainer *v454; // [rsp+270h] [rbp+158h] BYREF
  __int128 v455; // [rsp+278h] [rbp+160h] BYREF
  __int128 v456; // [rsp+288h] [rbp+170h] BYREF
  __int128 v457; // [rsp+298h] [rbp+180h]
  __int128 v458; // [rsp+2A8h] [rbp+190h] BYREF
  char *v459; // [rsp+2B8h] [rbp+1A0h] BYREF
  __int64 v460; // [rsp+2C0h] [rbp+1A8h]
  _DWORD v461[2]; // [rsp+2C8h] [rbp+1B0h] BYREF
  __int64 *v462; // [rsp+2D0h] [rbp+1B8h]
  int v463; // [rsp+2D8h] [rbp+1C0h]
  int v464; // [rsp+2DCh] [rbp+1C4h]
  __int64 *v465; // [rsp+2E0h] [rbp+1C8h]
  _QWORD v466[2]; // [rsp+2E8h] [rbp+1D0h] BYREF
  __int128 v467; // [rsp+2F8h] [rbp+1E0h] BYREF
  __int128 v468; // [rsp+308h] [rbp+1F0h] BYREF
  _QWORD v469[2]; // [rsp+318h] [rbp+200h] BYREF
  _QWORD v470[2]; // [rsp+328h] [rbp+210h] BYREF
  _QWORD v471[2]; // [rsp+338h] [rbp+220h] BYREF
  struct _RTL_BITMAP v472; // [rsp+348h] [rbp+230h] BYREF
  __int64 v473[4]; // [rsp+358h] [rbp+240h] BYREF
  __int128 v474; // [rsp+378h] [rbp+260h] BYREF
  __int128 v475; // [rsp+388h] [rbp+270h] BYREF
  __int128 v476; // [rsp+398h] [rbp+280h] BYREF
  __int128 v477; // [rsp+3A8h] [rbp+290h] BYREF
  __int128 v478; // [rsp+3B8h] [rbp+2A0h] BYREF
  __int128 v479; // [rsp+3C8h] [rbp+2B0h] BYREF
  _BYTE v480[32]; // [rsp+3D8h] [rbp+2C0h] BYREF
  __int128 v481; // [rsp+3F8h] [rbp+2E0h]
  __int64 v482; // [rsp+408h] [rbp+2F0h]
  int v483; // [rsp+410h] [rbp+2F8h]
  __int128 v484; // [rsp+418h] [rbp+300h]
  __int64 v485; // [rsp+428h] [rbp+310h]
  int v486; // [rsp+448h] [rbp+330h]
  _BYTE v487[32]; // [rsp+458h] [rbp+340h] BYREF
  __int128 v488; // [rsp+478h] [rbp+360h]
  __int64 v489; // [rsp+488h] [rbp+370h]
  int v490; // [rsp+490h] [rbp+378h]
  __int128 v491; // [rsp+498h] [rbp+380h]
  __int64 v492; // [rsp+4A8h] [rbp+390h]
  int v493; // [rsp+4C8h] [rbp+3B0h]
  _BYTE v494[32]; // [rsp+4D8h] [rbp+3C0h] BYREF
  __int128 v495; // [rsp+4F8h] [rbp+3E0h]
  __int64 v496; // [rsp+508h] [rbp+3F0h]
  int v497; // [rsp+510h] [rbp+3F8h]
  __int128 v498; // [rsp+518h] [rbp+400h]
  __int64 v499; // [rsp+528h] [rbp+410h]
  int v500; // [rsp+548h] [rbp+430h]
  __int128 v501; // [rsp+558h] [rbp+440h]
  _OWORD v502[4]; // [rsp+568h] [rbp+450h] BYREF
  __int64 v503; // [rsp+5A8h] [rbp+490h] BYREF
  int v504; // [rsp+5B0h] [rbp+498h]
  int v505; // [rsp+5B4h] [rbp+49Ch]
  __int128 v506; // [rsp+5B8h] [rbp+4A0h] BYREF
  __int128 v507; // [rsp+5C8h] [rbp+4B0h] BYREF
  _OWORD v508[4]; // [rsp+5D8h] [rbp+4C0h] BYREF
  __m128i v509; // [rsp+618h] [rbp+500h] BYREF
  __int128 v510; // [rsp+628h] [rbp+510h] BYREF
  _BYTE v511[16]; // [rsp+638h] [rbp+520h] BYREF
  size_t Size; // [rsp+648h] [rbp+530h]
  void *v513; // [rsp+650h] [rbp+538h]
  PVOID v514; // [rsp+658h] [rbp+540h]
  char v515; // [rsp+660h] [rbp+548h]
  int v516; // [rsp+664h] [rbp+54Ch]
  char v517; // [rsp+668h] [rbp+550h] BYREF
  __int64 v518; // [rsp+6A8h] [rbp+590h] BYREF
  __int128 v519; // [rsp+6B0h] [rbp+598h]
  __int64 v520; // [rsp+6C0h] [rbp+5A8h]
  _BYTE v521[16]; // [rsp+6C8h] [rbp+5B0h] BYREF
  size_t v522; // [rsp+6D8h] [rbp+5C0h]
  void *v523; // [rsp+6E0h] [rbp+5C8h]
  PVOID v524; // [rsp+6E8h] [rbp+5D0h]
  char v525; // [rsp+6F0h] [rbp+5D8h]
  int v526; // [rsp+6F4h] [rbp+5DCh]
  _OWORD v527[8]; // [rsp+6F8h] [rbp+5E0h] BYREF
  _OWORD v528[4]; // [rsp+778h] [rbp+660h] BYREF

  v442 = a7;
  v8 = *(_QWORD *)(a1 + 8);
  v9 = a1;
  v460 = a1;
  v10 = a2;
  v449 = a2;
  v427 = a3;
  v425 = *(CmsVolumeAnalyzer **)(v8 + 3064);
  v398 = a4;
  v481 = 0;
  v13 = ((unsigned __int64)v425 + 3432) & -(__int64)(v425 != 0);
  v412 = v13;
  BitMapHeader = 0;
  v14 = 0;
  v390 = 0;
  v402 = ((unsigned __int64)v425 + 3488) & -(__int64)(v425 != 0);
  v440 = 0;
  v514 = &v517;
  v516 = 64;
  v524 = v527;
  v526 = 64;
  v485 = 0;
  v15 = 0;
  v441 = 0;
  v414 = 0;
  v393 = 0;
  v416 = 0;
  Resource = 0;
  v428 = 0;
  v515 = 0;
  v525 = 0;
  v482 = 0;
  v484 = 0;
  v483 = 0;
  v486 = 0;
  v403 = 0;
  P = 0;
  v501 = 0;
  v457 = 0u;
  v506 = 0;
  v455 = 0;
  v458 = 0;
  v467 = 0;
  v437 = 0;
  memset(v528, 0, sizeof(v528));
  memset(&v527[4], 0, 0x40u);
  memset(v502, 0, sizeof(v502));
  memset(v508, 0, sizeof(v508));
  v436 = 0;
  v423 = 0;
  v434 = -1;
  v413 = 0;
  PerformanceCounter.QuadPart = 0;
  v473[3] = 0;
  PerformanceFrequency.QuadPart = 0;
  v453.QuadPart = 0;
  v447.QuadPart = 0;
  v419 = 0;
  v420 = 0;
  v404 = 0;
  v411 = 0;
  v386 = 0;
  v389 = 0;
  v392 = 0;
  v388 = 0;
  v397 = 0;
  v391[0] = 0;
  LOBYTE(v396) = 0;
  v510 = 0;
  v415 = 0;
  v422 = 0;
  v421 = 0;
  v405 = 0;
  KeQueryPerformanceCounter(&PerformanceFrequency);
  CmsVolume::JoinCheckpoint(*(CmsVolume **)(v9 + 8), (struct _SmsCheckpointContext **)&Resource);
  CmsVolume::BeginTopLevelAction(v16, (struct CmsTransactionContext *)v10, (struct _SmsTopLevelAction *)v480, 0, 1);
  v17 = *(_QWORD *)(v9 + 8);
  if ( (unsigned __int64)(3LL * *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v17 + 3024) + 32LL) + 16LL)) >> 1 < *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v17 + 3024) + 32LL) + 8LL) )
  {
    v18 = -1070006270;
LABEL_3:
    v19 = 0;
LABEL_4:
    LODWORD(v20) = 0;
    goto LABEL_47;
  }
  if ( *(_WORD *)(v17 + 1916) <= 3u && (*(_WORD *)(v17 + 1916) != 3 || *(_WORD *)(v17 + 1918) < 2u) )
  {
    v18 = -1073741156;
    goto LABEL_3;
  }
  v21 = *(_DWORD *)(v9 + 112);
  if ( (v21 & 1) == 0 )
  {
    v18 = -1073741637;
    goto LABEL_3;
  }
  LODWORD(v20) = 0;
  if ( (v21 & 2) == 0 )
  {
    v18 = -1073741637;
LABEL_13:
    v19 = 0;
    goto LABEL_47;
  }
  if ( !*(_QWORD *)(v17 + 3032) || (*(_DWORD *)(v17 + 3116) & 0x2000) != 0 )
  {
    v18 = -1073741202;
    goto LABEL_13;
  }
  ContainerReference = CmsVolumeContainer::GetContainerReference(
                         (CmsVolumeContainer *)v9,
                         (struct CmsTransactionContext *)v10,
                         a3,
                         &v390,
                         0,
                         0,
                         0);
  LODWORD(v20) = 0;
  v18 = ContainerReference;
  if ( ContainerReference < 0 )
  {
    v15 = v390;
    goto LABEL_13;
  }
  if ( CmsVolume::IsVolumeOnSmr(*(CmsVolume **)(v9 + 8))
    && v13
    && *(_QWORD *)(v13 + 48) != v25
    && *(_QWORD *)(v13 + 32) != v427 )
  {
    _InterlockedAdd((volatile signed __int32 *)v390 + 22, 0xFFFFFFFF);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v9 + 328), 0, v25 + 32);
    --*(_DWORD *)(v10 + 2824);
    LODWORD(v20) = 0;
LABEL_22:
    v390 = 0;
    v18 = -1073741267;
    goto LABEL_13;
  }
  v15 = v390;
  v399 = v390;
  v26 = CmsVolumeContainer::TryLockContainerExclusive(v24, v23, v390);
  LODWORD(v20) = 0;
  if ( !v26 )
  {
    _InterlockedAdd((volatile signed __int32 *)v15 + 22, 0xFFFFFFFF);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v9 + 328), 0, 0x20u);
    --*(_DWORD *)(v10 + 2824);
    LODWORD(v20) = 0;
    v15 = 0;
    goto LABEL_22;
  }
  v27 = 1;
  v28 = *((_DWORD *)v15 + 143);
  v14 = 1;
  v405 = 1;
  v418 = (unsigned int *)((char *)v15 + 572);
  if ( (v28 & 1) != 0 )
    goto LABEL_492;
  if ( (v28 & 0x200) != 0 )
    goto LABEL_492;
  if ( (v28 & 0x40) != 0 )
    goto LABEL_492;
  if ( (v28 & 0x400) != 0 )
    goto LABEL_492;
  if ( *((int *)v15 + 21) > 0 )
    goto LABEL_492;
  if ( *((_QWORD *)v15 + 74) )
    goto LABEL_492;
  v29 = *((_QWORD *)v15 + 73);
  if ( !v29 || v29 == *((_QWORD *)v15 + 72) && !a4 && !*((_DWORD *)v15 + 150) )
    goto LABEL_492;
  if ( (v28 & 0x80u) != 0 )
    goto LABEL_492;
  v30 = *((_BYTE *)v15 + 24);
  v433 = (char *)v15 + 24;
  if ( (v30 & 4) != 0
    || *((_DWORD *)v15 + 24)
    || (v31 = *(CmsVolume **)(v9 + 8), (v30 & 0x40) == 0) && CmsVolume::IsVolumeOnSmr(v31)
    || (v28 & 8) != 0 )
  {
    LODWORD(v20) = 0;
LABEL_492:
    _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(v9 + 8) + 936LL), v27);
    v18 = -1073741267;
    goto LABEL_493;
  }
  v32 = v31;
  if ( !CmsVolume::IsVolumeOnSmr(v31)
    && (unsigned int)CmsVolume::GetStorageTierForRange(
                       v33,
                       v10,
                       (char *)v15 + (unsigned int)(*(_DWORD *)(v9 + 228) * *(_DWORD *)(v9 + 232)) + 632) != *((_DWORD *)v32 + 871) )
  {
    LODWORD(v20) = 0;
    if ( (_BYTE)KdDebuggerEnabled )
      __debugbreak();
LABEL_45:
    v18 = -1073741267;
    goto LABEL_46;
  }
  if ( CmsVolume::IsVolumeOnSmr(v32) && *v54 < 0 && ((unsigned __int8)v55 & *((_BYTE *)v15 + 25)) != 0 )
  {
    MsSetOkayToResyncSMRBands(v10);
    v18 = -1073741267;
    v19 = 0;
    goto LABEL_4;
  }
  LODWORD(v20) = 0;
  if ( *(_BYTE *)(*((_QWORD *)v32 + 382) + 16LL) )
  {
    v56 = (_DWORD *)((char *)v15 + 632);
    v57 = 0;
    v58 = (unsigned int)(*(_DWORD *)(v9 + 228) * *(_DWORD *)(v9 + 232)) >> 2;
    if ( v58 )
    {
      do
      {
        if ( *v56 )
          goto LABEL_45;
        v57 += v55;
        ++v56;
      }
      while ( v57 < v58 );
      v32 = *(CmsVolume **)(v9 + 8);
    }
  }
  if ( (*v53 & 8) == 0 )
  {
    v506 = *(_OWORD *)((char *)v15 + (unsigned int)(*(_DWORD *)(v9 + 228) * *(_DWORD *)(v9 + 232)) + 632);
    v65 = CmsAllocator::PinBitmapRegion(
            *((CmsAllocator **)v32 + 379),
            (struct CmsTransactionContext *)v10,
            (const struct _RANGE *)&v506,
            &v404);
    LODWORD(v20) = 0;
    v18 = v65;
    if ( v65 < 0 )
      goto LABEL_46;
    if ( !*(_QWORD *)(*(_QWORD *)(v9 + 8) + 2888LL) )
    {
      v67 = v404;
      if ( (*((_BYTE *)v404 + 24) & 0xC) != 0 || SmsAllocationRegionEx::GetTotalFree(v404) == *((_QWORD *)v67 + 1) )
      {
        v18 = -1073741267;
      }
      else if ( v398 == (_DWORD)v20 && !SmsAllocationRegionEx::GetTotalFree(v66) )
      {
        goto LABEL_109;
      }
      if ( v18 < 0 )
        goto LABEL_46;
      v68 = CmsAllocator::TryProtectRegion(v66, v404, 1);
      LODWORD(v20) = 0;
      v18 = v68;
      if ( v68 < 0 )
        goto LABEL_46;
      v69 = *(_QWORD *)(v9 + 8);
      v14 = 3;
      v405 = 3;
      v70 = *(_QWORD *)(v69 + 3056);
      if ( *(_BYTE *)(v70 + 16) )
      {
        v394 = 0;
        v459 = &v394;
        v71 = *(CmsAllocator **)(v70 + 8);
        v400 = 0;
        v473[0] = (__int64)&v459;
        v473[1] = (__int64)&v400;
        v473[2] = (__int64)&v506;
        v72 = CmsAllocator::WalkAllocator__lambda_5c09caec3961b5bbbcbae8324e2a8d6d___(
                v71,
                (struct CmsTransactionContext *)v10,
                (__int64)v473);
        LODWORD(v20) = 0;
        v18 = v72;
        if ( v72 < 0 )
          goto LABEL_46;
        if ( !v394 )
        {
          _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(v9 + 8) + 936LL), 1u);
          v18 = -1073741267;
LABEL_117:
          v15 = v390;
          goto LABEL_46;
        }
        v69 = *(_QWORD *)(v9 + 8);
      }
      if ( *((_QWORD *)v15 + 74)
        || (v73 = *((_QWORD *)v15 + 73)) == 0
        || v73 == *((_QWORD *)v15 + 72) && !v398 && !*((_DWORD *)v15 + 150)
        || (*v418 & 0x80u) != 0
        || (*v433 & 4) != 0
        || *((_DWORD *)v15 + 24) )
      {
        _InterlockedAdd((volatile signed __int32 *)(v69 + 936), 1u);
        v18 = -1073741267;
        goto LABEL_493;
      }
    }
    v74 = *((unsigned __int16 *)v15 + 304);
    v414 = v74;
    if ( v74 )
    {
      v76 = v74;
      v75 = 8LL * v74;
      if ( !is_mul_ok(v76, 8u) )
        v75 = -1;
      PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, v75, 0x6950534Du);
      LODWORD(v20) = 0;
      v441 = PoolWithTag;
      if ( !PoolWithTag )
        goto LABEL_132;
      EmbeddedContainers = CmsVolumeContainer::GetEmbeddedContainers(
                             (CmsVolumeContainer *)v9,
                             (struct CmsTransactionContext *)v10,
                             v15,
                             &v414,
                             (unsigned __int64 *)PoolWithTag);
      LODWORD(v20) = 0;
      v18 = EmbeddedContainers;
      if ( EmbeddedContainers < 0 )
        goto LABEL_46;
    }
    v79 = (char *)ExAllocatePoolWithTag((POOL_TYPE)512, 0x40u, 0x6950534Du);
    LODWORD(v20) = 0;
    v416 = (CmsContainerRangeMap *)v79;
    v80 = (CmsContainerRangeMap *)v79;
    if ( v79 )
    {
      v81 = *(_BYTE *)(*(_QWORD *)(v10 + 32) + 76LL);
      *(_OWORD *)(v79 + 8) = 0;
      *(_OWORD *)(v79 + 24) = 0;
      *(_QWORD *)v79 = 0;
      v79[60] = v81;
      *((_DWORD *)v79 + 14) = 0;
      *(_WORD *)(v79 + 61) = 0;
      *((_QWORD *)v79 + 5) = 0;
      *((_QWORD *)v79 + 6) = 0;
    }
    else
    {
      v80 = 0;
      v416 = 0;
    }
    if ( v80 )
    {
      v18 = CmsContainerRangeMap::InitializeMapIfRequired(v80);
      if ( v18 < 0 )
      {
        CmsContainerRangeMap::`scalar deleting destructor'(v80, v82);
        LODWORD(v20) = 0;
        v416 = 0;
        goto LABEL_46;
      }
      v83 = CmsLookasides::SatisfyReservation(17, 1);
      LODWORD(v20) = 0;
      v18 = v83;
      if ( v83 < 0 )
        goto LABEL_46;
      v421 = 1;
      v84 = CmsLookasides::SatisfyReservation(18, 1);
      LODWORD(v20) = 0;
      v18 = v84;
      if ( v84 < 0 )
        goto LABEL_46;
      v422 = 1;
      v85 = CmsRowWithBuffer::NewLength(
              (CmsRowWithBuffer *)v511,
              0,
              (((*((_QWORD *)v15 + 72) >> 3) + 7) & 0xFFFFFFF8) + 48,
              0x10u,
              0);
      LODWORD(v20) = 0;
      v18 = v85;
      if ( v85 < 0 )
        goto LABEL_46;
      v86 = v513;
      memset(v513, 0, (unsigned int)Size);
      *(_QWORD *)v86 = *((_QWORD *)v15 + 69);
      v86[2] = 0;
      v86[3] = 3;
      *((_BYTE *)v86 + 16) = *(_BYTE *)v9;
      v87 = *(_QWORD *)(v9 + 8);
      Src = (char *)v15 + 552;
      *((_QWORD *)v86 + 3) = *((_QWORD *)v15 + 69) << ((unsigned __int8)*(_DWORD *)(v87 + 76) + 1);
      *((_QWORD *)v86 + 4) = *((_QWORD *)v15 + 72);
      *((_BYTE *)v86 + 40) = 48;
      RtlInitializeBitMap(&BitMapHeader, v86 + 12, *((_DWORD *)v15 + 144));
      RtlSetAllBits(&BitMapHeader);
      v88 = CmsRowWithBuffer::NewLength(
              (CmsRowWithBuffer *)v521,
              0,
              (((*((_QWORD *)v15 + 72) >> 3) + 7) & 0xFFFFFFF8) + 48,
              0x10u,
              0);
      LODWORD(v20) = 0;
      v18 = v88;
      if ( v88 < 0 )
        goto LABEL_46;
      v89 = v523;
      v439 = v523;
      memset(v523, 0, (unsigned int)v522);
      v90 = Src;
      v91 = *(_QWORD *)Src;
      v89[2] = 0;
      *(_QWORD *)v89 = v91;
      v89[3] = 5;
      *((_BYTE *)v89 + 16) = *(_BYTE *)v9;
      *((_QWORD *)v89 + 3) = *v90 << ((unsigned __int8)*(_DWORD *)(*(_QWORD *)(v9 + 8) + 76LL) + 1);
      *((_QWORD *)v89 + 4) = *((_QWORD *)v15 + 72);
      *((_BYTE *)v89 + 40) = 48;
      RtlInitializeBitMap(&v428, v89 + 12, *((_DWORD *)v15 + 144));
      ExAcquirePushLockSharedEx(*(_QWORD *)(v9 + 8) + 3264LL, 0);
      v92 = v404;
      memmove(v428.Buffer, *((const void **)v404 + 6), (unsigned __int64)v428.SizeOfBitMap >> 3);
      v93 = *(CmsVolume **)(v9 + 8);
      v94 = (struct CmsAllocator *)*((_QWORD *)v93 + 379);
      v395 = 0;
      CmsVolume::MaskUnmaskRecentlyDeallocatedTrim(v93, 0, v94, v92, 0, &v395, &v428, 0);
      ExReleasePushLockEx(*(_QWORD *)(v9 + 8) + 3264LL, 0);
      v20 = 0;
      if ( !v395 )
        goto LABEL_145;
LABEL_109:
      v18 = -1073741267;
      goto LABEL_46;
    }
LABEL_132:
    v18 = -1073741670;
    goto LABEL_46;
  }
  v59 = *(CmsTable **)(v9 + 64);
  v461[1] = 0;
  v464 = 0;
  v503 = *((_QWORD *)v15 + 69);
  v462 = &v503;
  v504 = 0;
  v465 = &v503;
  Src = (char *)v15 + 552;
  v505 = 3;
  v461[0] = 16;
  v463 = 16;
  Row = CmsTable::FindRow(
          v59,
          (struct CmsTransactionContext *)v10,
          (struct _CmsRow *)v461,
          (struct CmsRowWithBuffer *)v511,
          (unsigned int)v378);
  LODWORD(v20) = 0;
  v18 = Row;
  if ( Row < 0 )
    goto LABEL_46;
  RtlInitializeBitMap(&BitMapHeader, (PULONG)((char *)v513 + *((unsigned __int8 *)v513 + 40)), *((_DWORD *)v15 + 144));
  v61 = *((_QWORD *)v15 + 69);
  v62 = *(CmsTable **)(v9 + 64);
  v504 = 0;
  v503 = v61;
  v505 = 5;
  v63 = CmsTable::FindRow(
          v62,
          (struct CmsTransactionContext *)v10,
          (struct _CmsRow *)v461,
          (struct CmsRowWithBuffer *)v521,
          (unsigned int)v378);
  LODWORD(v20) = 0;
  v18 = v63;
  if ( v63 < 0 )
    goto LABEL_46;
  v64 = *((_DWORD *)v15 + 144);
  v439 = v523;
  RtlInitializeBitMap(&v428, (PULONG)((char *)v523 + *((unsigned __int8 *)v523 + 40)), v64);
  v20 = 0;
LABEL_145:
  if ( *(_QWORD *)(*(_QWORD *)(v9 + 8) + 2888LL) )
  {
    v95 = 0;
    v208 = (unsigned __int64)v442;
    if ( v442 < v442 + 4 )
    {
      do
      {
        v209 = *(_QWORD *)(v208 + 8);
        if ( !v209 )
          break;
        v95 += v209;
        v208 += 16LL;
      }
      while ( v208 < (unsigned __int64)(v442 + 4) );
    }
    v210 = v502;
    v211 = v442[1];
    v502[0] = *v442;
    v212 = v442[2];
    v502[1] = v211;
    v213 = v442[3];
    v502[2] = v212;
    v502[3] = v213;
    v393 = v95;
    while ( *((_QWORD *)v210 + 1) )
    {
      v214 = *(_QWORD *)(v9 + 8);
      v476 = *v210;
      v215 = CmsVolumeContainer::ContainerRangeToRealRangeUnsafe(*(_QWORD *)(v214 + 3048), v10, &v476, &v458);
      LODWORD(v20) = 0;
      v18 = v215;
      if ( v215 < 0 )
        goto LABEL_46;
      LODWORD(v378) = 64;
      *(_QWORD *)(v10 + 16) |= 0x800000000uLL;
      v18 = CmsAllocator::AllocateRange(*(_QWORD *)(*(_QWORD *)(v9 + 8) + 3032LL), v10, &v458, &v467);
      v20 = 0;
      *(_QWORD *)(v10 + 16) &= ~0x800000000uLL;
      if ( v18 < 0 )
        goto LABEL_46;
      if ( *v210 != v467 )
      {
        v18 = -1073741604;
        goto LABEL_46;
      }
      if ( ++v210 >= (_OWORD *)&v503 )
        break;
    }
    v152 = 1;
    v216 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v9 + 8) + 3032LL) + 60LL) - 1;
    if ( (v216 & *(_QWORD *)&v502[0]) != 0 && (!*(_QWORD *)&v502[1] || (v216 & *(_QWORD *)&v502[1]) != 0) )
      v437 = MsZeroRange;
    else
      v437 = v506;
    goto LABEL_246;
  }
  v95 = RtlNumberOfSetBits(&v428);
  v393 = v95;
  if ( v95 != *((_QWORD *)v15 + 73) )
  {
LABEL_147:
    v18 = -1073741267;
LABEL_148:
    v19 = 0;
    goto LABEL_4;
  }
  if ( v398 )
  {
    v95 = -a6 & (a6 + v95 - 1);
    v393 = v95;
  }
  v96 = CmsDurableLog::ReserveSpaceForRecordOfSize((CmsDurableLog *)(*(_QWORD *)(v9 + 8) + 2608LL), 0x1000u, &v415);
  LODWORD(v20) = 0;
  v18 = v96;
  if ( v96 < 0 )
    goto LABEL_46;
  v97 = *(CmsVolume **)(v9 + 8);
  v413 = v95;
  *((_QWORD *)&v458 + 1) = v95;
  IsVolumeOnSmr = CmsVolume::IsVolumeOnSmr(v97);
  v101 = v402;
  if ( IsVolumeOnSmr && v402 && *(_BYTE *)v402 && *(_DWORD *)(v402 + 4) == v95 )
  {
    v102 = *(__m128i *)(v402 + 24);
    v502[0] = v102;
    v502[1] = *(_OWORD *)(v402 + 40);
    v502[2] = *(_OWORD *)(v402 + 56);
    v502[3] = *(_OWORD *)(v402 + 72);
LABEL_179:
    LOBYTE(v113) = 1;
    goto LABEL_180;
  }
  v496 = 0;
  v495 = 0;
  v497 = 0;
  v498 = 0;
  v499 = 0;
  v500 = 0;
  if ( CmsVolume::IsVolumeOnSmr(v99) && v101 )
  {
    v104 = *(CmsVolume **)(v101 + 152);
    if ( v104 )
    {
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)(v9 + 296), (signed __int64)v104, 0) )
      {
        ExFreePoolWithTag(*(PVOID *)(v101 + 152), 0);
        v103 = 0;
      }
      v15 = v390;
      v95 = v393;
      v399 = v390;
      *(_QWORD *)(v101 + 152) = v103;
    }
    if ( *(_BYTE *)v101 != (_BYTE)v103 )
      CmsVolumeAnalyzer::FreeResumeFromWriteContextLcns(v425, (struct CmsTransactionContext *)v10, 0, 0);
    CmsVolume::BeginTopLevelAction(v104, (struct CmsTransactionContext *)v10, (struct _SmsTopLevelAction *)v494, 0, 1);
  }
  LODWORD(v378) = 64;
  v18 = CmsAllocator::AllocateLcns(*(_QWORD *)(*(_QWORD *)(v9 + 8) + 3032LL), v10, v502, &v458);
  v105 = *(CmsVolume **)(v9 + 8);
  if ( v18 < 0 )
  {
    if ( !CmsVolume::IsVolumeOnSmr(v105) || !v101 )
    {
      v19 = v207;
      goto LABEL_4;
    }
    CmsVolume::AbortTopLevelAction(v206, (struct CmsTransactionContext *)v10, (struct _SmsTopLevelAction *)v494);
    goto LABEL_148;
  }
  if ( !CmsVolume::IsVolumeOnSmr(v105) || !v101 )
  {
    v102 = (__m128i)v502[0];
    goto LABEL_179;
  }
  v107 = v402;
  v108 = (_DWORD)v106 + 1;
  v109 = (unsigned int)v106;
  while ( 1 )
  {
    v110 = (unsigned int)v106;
    v111 = (union _LCN_TUPLE **)v502;
    do
    {
      if ( v111[1] == v106 )
        break;
      v110 += v108;
      v111 += 2;
    }
    while ( v111 < (union _LCN_TUPLE **)&v503 );
    if ( v109 >= v110 )
      break;
    v112 = 2LL * v109;
    v468 = v502[v109];
    v474 = v468;
    CmsVolumeContainer::ContainerRangeToRealRangeUnsafe(v9, v10, &v474, &v468);
    v109 += v108;
    *(_OWORD *)(v107 + 8 * v112 + 88) = v468;
    v106 = 0;
  }
  v14 = v405;
  v101 = v107;
  *(_BYTE *)(v107 + 2) = (_BYTE)v106;
  v113 = v108;
  v114 = *(CmsVolume **)(v9 + 8);
  v115 = *(_DWORD *)(*((_QWORD *)v114 + 379) + 60LL) - v108;
  v15 = v399;
  if ( (v115 & (*(_QWORD *)&v502[0] + *((_QWORD *)&v502[0] + 1))) == 0 )
  {
    v518 = *(_QWORD *)&v502[0];
    v520 = 0;
    v519 = 0;
    CmsVolumeContainer::SetContainerStationaryVolatile(
      (CmsVolumeContainer *)v9,
      (struct CmsTransactionContext *)v10,
      (union _LCN_TUPLE *)&v518,
      v113,
      v106);
    *(_BYTE *)(v101 + 2) = v113;
    v114 = *(CmsVolume **)(v9 + 8);
  }
  CmsVolume::CommitTopLevelAction(v114, (struct CmsTransactionContext *)v10, (struct _SmsTopLevelAction *)v494, 0);
  *(_OWORD *)(v101 + 24) = v502[0];
  *(_OWORD *)(v101 + 40) = v502[1];
  *(_OWORD *)(v101 + 56) = v502[2];
  *(_OWORD *)(v101 + 72) = v502[3];
  *(_DWORD *)(v101 + 4) = v95;
  *(_WORD *)v101 = v113;
  v100 = *(CmsVolume **)(v9 + 8);
  v102 = (__m128i)v502[0];
LABEL_180:
  if ( !CmsVolume::IsVolumeOnSmr(v100) || !v101 || *(_BYTE *)(v101 + 1) == (_BYTE)v117 )
  {
    v118 = v102.m128i_i64[0];
    v123 = *(_DWORD *)(*(_QWORD *)(v116 + 3032) + 60LL);
    if ( ((v102.m128i_i64[0] + _mm_srli_si128(v102, 8).m128i_u64[0]) & (v123 - 1)) != 0 )
      goto LABEL_184;
    v509 = v102;
    v124 = (unsigned __int64)v102.m128i_i64[0] >> ((unsigned __int8)v113 + (unsigned __int8)*(_DWORD *)(v116 + 76));
    v452 = v117;
    v443 = v117;
    v509.m128i_i64[0] = v102.m128i_i64[0] & -v123;
    v125 = CmsVolumeContainer::GetContainerReference(
             (CmsVolumeContainer *)v9,
             (struct CmsTransactionContext *)v10,
             v124,
             &v443,
             v113,
             (unsigned __int8)v117,
             (unsigned __int8)v117);
    LODWORD(v20) = 0;
    v18 = v125;
    if ( v125 < 0
      || (v126 = (unsigned int)(*(_DWORD *)(v9 + 228) * *(_DWORD *)(v9 + 232)),
          v406 = (unsigned __int64)v443,
          v127 = *(_QWORD *)(v9 + 8),
          v509 = *(__m128i *)((char *)v443 + v126 + 632),
          v128 = CmsAllocator::PinBitmapRegion(
                   *(CmsAllocator **)(v127 + 3032),
                   (struct CmsTransactionContext *)v10,
                   (const struct _RANGE *)&v509,
                   &v452),
          LODWORD(v20) = 0,
          v18 = v128,
          v128 < 0) )
    {
      if ( (_BYTE)KdDebuggerEnabled )
        __debugbreak();
      goto LABEL_46;
    }
    _InterlockedAdd((volatile signed __int32 *)(v406 + 88), 0xFFFFFFFF);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v9 + 328), 0, 0x20u);
    --*(_DWORD *)(v10 + 2824);
    v492 = 0;
    v443 = 0;
    v488 = 0;
    v489 = 0;
    v491 = 0;
    v490 = 0;
    v493 = 0;
    CmsVolume::BeginTopLevelAction(v129, (struct CmsTransactionContext *)v10, (struct _SmsTopLevelAction *)v487, 0, 1);
    v130 = *(_QWORD *)(v9 + 64);
    v466[1] = &v442;
    v442 = (_OWORD *)v124;
    LODWORD(v383) = 0;
    v378 = 0;
    v466[0] = 8;
    v18 = CmsTransactionContext::AddRedoRecord(v10, v130, 28, v466);
    if ( v18 < 0 )
    {
      if ( (_BYTE)KdDebuggerEnabled )
        __debugbreak();
      CmsVolume::AbortTopLevelAction(
        *(CmsVolume **)(v9 + 8),
        (struct CmsTransactionContext *)v10,
        (struct _SmsTopLevelAction *)v487);
      v15 = v390;
      goto LABEL_148;
    }
    CmsVolume::CommitTopLevelAction(
      *(CmsVolume **)(v9 + 8),
      (struct CmsTransactionContext *)v10,
      (struct _SmsTopLevelAction *)v487,
      0);
    CmsVolumeContainer::UnreserveContainerAndRegion(
      (CmsVolumeContainer *)v9,
      (struct CmsTransactionContext *)v10,
      v452,
      v131);
    v117 = 0;
    if ( v101 && *(_BYTE *)v101 )
    {
      v95 = v393;
      v15 = v390;
      *(_BYTE *)(v101 + 1) = 1;
      v118 = *(_QWORD *)&v502[0];
      v399 = v15;
      goto LABEL_184;
    }
    v15 = v390;
    v95 = v393;
    v399 = v390;
  }
  v118 = *(_QWORD *)&v502[0];
LABEL_184:
  v119 = (int)v117;
  v120 = (struct SmsAllocationRegionEx **)v502;
  do
  {
    if ( v120[1] == v117 )
      break;
    ++v119;
    v120 += 2;
  }
  while ( v120 < (struct SmsAllocationRegionEx **)&v503 );
  if ( v119 == 2 )
  {
    v121 = *(_QWORD *)(v9 + 8);
    if ( v118 >> (*(_BYTE *)(v121 + 76) + 1) == *(_QWORD *)&v502[1] >> (*(_BYTE *)(v121 + 76) + 1)
      || (v122 = *(int *)(*(_QWORD *)(v121 + 3032) + 60LL),
          (-v122 & (v122 + *(_QWORD *)&v502[1] - 1LL)) != *(_QWORD *)&v502[1]) )
    {
LABEL_190:
      v18 = -1073741436;
      goto LABEL_148;
    }
  }
  else
  {
    v132 = (unsigned int)v117;
    v133 = (struct SmsAllocationRegionEx **)v502;
    do
    {
      if ( v133[1] == v117 )
        break;
      ++v132;
      v133 += 2;
    }
    while ( v133 < (struct SmsAllocationRegionEx **)&v503 );
    if ( v132 > 2 )
      goto LABEL_190;
  }
  v134 = v117;
  v135 = (__int64 *)v502;
  do
  {
    v136 = v135[1];
    if ( !v136 )
      break;
    v134 = (struct SmsAllocationRegionEx *)((char *)v134 + v136);
    v135 += 2;
  }
  while ( v135 < &v503 );
  if ( v134 != (struct SmsAllocationRegionEx *)v413 )
  {
    v18 = -1073740759;
    goto LABEL_148;
  }
  if ( !CmsVolume::IsVolumeOnSmr(*(CmsVolume **)(v9 + 8)) )
  {
    v141 = CmsVolume::ReserveForFailableOperation(
             v137,
             (struct CmsTransactionContext *)v10,
             *((_DWORD *)v137 + 20) - v95,
             (struct SmsReservationUndoRecord *)&v510,
             v140);
    LODWORD(v20) = 0;
    v18 = v141;
    if ( v141 < 0 )
      goto LABEL_46;
    v139 = *(_QWORD *)&v502[1];
    v138 = *(_QWORD *)&v502[0];
  }
  v142 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v9 + 8) + 3032LL) + 60LL) - 1;
  if ( (v142 & v138) != 0 && (!v139 || (v142 & v139) != 0) )
    v437 = MsZeroRange;
  else
    v437 = v506;
  v143 = (unsigned __int64)RtlNumberOfSetBits(&BitMapHeader) << *(_DWORD *)(*(_QWORD *)(v9 + 8) + 64LL);
  v413 = v143;
  v387 = 0;
  if ( v412 && (v144 = *(struct _RTL_BITMAP **)(v412 + 48), (P = v144) != 0) )
  {
    if ( *(_QWORD *)(v412 + 32) != v427
      || *(_DWORD *)(v412 + 4) != *((_DWORD *)v15 + 18)
      || *(_DWORD *)(v412 + 8) != *((_DWORD *)v15 + 19)
      || *(_QWORD *)(v412 + 40) != v143 )
    {
      LODWORD(v20) = 0;
      P = v144;
      *(_QWORD *)(v412 + 48) = 0;
      v18 = -1073741267;
      v389 = 1;
      v19 = 0;
      goto LABEL_47;
    }
    v387 = 1;
  }
  else
  {
    v144 = (struct _RTL_BITMAP *)_InterlockedExchange64((volatile __int64 *)(v9 + 288), 0);
    P = v144;
    if ( !v144 )
    {
      v145 = (struct _RTL_BITMAP *)ExAllocatePoolWithTag(
                                     PagedPool,
                                     (int)(*(_DWORD *)(*(_QWORD *)(v9 + 8) + 80LL) << *(_DWORD *)(*(_QWORD *)(v9 + 8)
                                                                                                + 64LL)),
                                     0x6F63534Du);
      LODWORD(v20) = 0;
      P = v145;
      v144 = v145;
      if ( !v145 )
      {
LABEL_231:
        v18 = -1073741670;
        goto LABEL_117;
      }
    }
    v15 = v390;
    v389 = 1;
    v95 = v393;
    v399 = v390;
    if ( v101 )
      *(_DWORD *)(v101 + 8) = 0;
  }
  if ( !CmsVolume::IsVolumeOnSmr(*(CmsVolume **)(v9 + 8)) || !v101 || (v403 = *(PVOID *)(v101 + 152)) == 0 )
  {
    v403 = (PVOID)_InterlockedExchange64((volatile __int64 *)(v9 + 296), (__int64)v20);
    if ( v403
      || (v148 = ExAllocatePoolWithTag(
                   PagedPool,
                   (int)(*(_DWORD *)(*(_QWORD *)(v9 + 8) + 80LL) << *(_DWORD *)(*(_QWORD *)(v9 + 8) + 64LL)),
                   0x6F63534Du),
          LODWORD(v20) = 0,
          (v403 = v148) != 0) )
    {
      v149 = *(CmsVolume **)(v9 + 8);
      v392 = 1;
      if ( CmsVolume::IsVolumeOnSmr(v149) && v101 )
      {
        *(_DWORD *)(v101 + 8) = (_DWORD)v20;
        v147 = *(_QWORD *)(v9 + 8);
      }
      v15 = v390;
      v95 = v393;
      v399 = v390;
      goto LABEL_243;
    }
    goto LABEL_231;
  }
LABEL_243:
  if ( (*v418 & 2) != 0 )
  {
    v150 = RtlNumberOfSetBits(&BitMapHeader);
    v469[0] = 0;
    v378 = v144;
    v469[1] = (unsigned __int64)v150 << *(_BYTE *)(*(_QWORD *)(v9 + 8) + 64LL);
    CompressedContainerRangeInternal = CmsVolumeContainer::ReadCompressedContainerRangeInternal(v9, v10, v15, v469);
    v20 = 0;
    v18 = CompressedContainerRangeInternal;
    if ( CompressedContainerRangeInternal < 0 )
      goto LABEL_46;
    goto LABEL_245;
  }
  if ( v146 && *(_QWORD *)(v412 + 16) == -1 )
  {
LABEL_245:
    v152 = 1;
    goto LABEL_246;
  }
  v165 = (int)v20;
  v166 = (unsigned int)(*(_DWORD *)(v9 + 228) * *(_DWORD *)(v9 + 232));
  v409 = (int)v20;
  v406 = (unsigned __int64)v15 + v166 + 632;
  if ( (*v433 & 0x40) != 0 && (char)*v433 < 0 )
  {
    v167 = *((_DWORD *)v15 + 10);
    v15 = v390;
  }
  else
  {
    v167 = *(_DWORD *)(v147 + 68) * *(_DWORD *)(v147 + 80);
  }
  PerformanceCounter = KeQueryPerformanceCounter(0);
  v168 = 0;
  v169 = PerformanceCounter;
  v401 = 0;
  if ( *((_DWORD *)v15 + 157) )
  {
    v170 = v387;
    v171 = v406;
    do
    {
      v172 = *(_OWORD *)(v171 + 16LL * v168);
      v455 = v172;
      v457 = v172;
      if ( v170 && v168 < *(_DWORD *)v412 )
      {
        v167 -= *((_QWORD *)&v455 + 1) << *(_DWORD *)(*(_QWORD *)(v9 + 8) + 64LL);
      }
      else
      {
        if ( (*v418 & 8) != 0 )
        {
          LODWORD(v383) = 0;
          v475 = v172;
          v378 = (struct _RTL_BITMAP *)&v455;
          v173 = CmsVolumeContainer::PinContainerRange(v9, v10, &v475, 0);
          LODWORD(v20) = 0;
          v18 = v173;
          if ( v173 < 0 )
            goto LABEL_493;
          v165 = v409;
        }
        v174 = DWORD2(v455);
        v426 = (struct SmsContainer *)v455;
        v424 = DWORD2(v455);
        v408 = v165;
        if ( v170 )
        {
          v175 = *(_DWORD *)(v412 + 28);
          v426 = *(struct SmsContainer **)(v412 + 16);
          v176 = v175 - *(_DWORD *)(v412 + 24);
          v409 = *(_DWORD *)(v412 + 24);
          v177 = *(_QWORD *)(v9 + 8);
          v408 = v175;
          v178 = *(_DWORD *)(v177 + 64);
          v174 = DWORD2(v455) - (v176 >> v178);
          v424 = v174;
          if ( v167 < v176 )
            v167 = 0;
          else
            v167 -= v176 >> v178 << v178;
          v387 = 0;
        }
        while ( v174 && v167 )
        {
          v179 = *(_QWORD *)(v9 + 8);
          v180 = *(_DWORD *)(v9 + 280);
          if ( v180 >= v174 )
            v180 = v174;
          v181 = v167;
          v182 = *(_DWORD *)(v179 + 64);
          v183 = v180 << v182;
          if ( v183 < v167 )
            v181 = v183;
          v184 = *(_DWORD *)(v179 + 68);
          LODWORD(v429) = v181;
          LODWORD(v399) = (-v184 & (v181 + v184 - 1)) >> v182;
          v185 = KeQueryPerformanceCounter(0);
          v186 = *(_QWORD *)(v9 + 8);
          v187 = v185;
          v453 = v185;
          LODWORD(v378) = (_DWORD)v429;
          v188 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))qword_1C0136A58)(
                   *(_QWORD *)(v186 + 48),
                   0,
                   0,
                   (_QWORD)v426 << *(_DWORD *)(v186 + 64));
          LODWORD(v20) = 0;
          v18 = v188;
          if ( v188 < 0 )
            goto LABEL_493;
          v189 = KeQueryPerformanceCounter(0);
          v190 = *(CmsVolume **)(v9 + 8);
          v447 = v189;
          if ( CmsVolume::IsVolumeOnSmr(v190) )
          {
            v193 = v191 - v187.QuadPart;
            _InterlockedExchangeAdd64((volatile signed __int64 *)(v192 + 2320), v193);
            _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(v9 + 8) + 2336LL), 1u);
            v194 = *(_QWORD *)(v9 + 8);
            if ( v193 <= *(_QWORD *)(v194 + 2328) )
              v193 = *(_QWORD *)(v194 + 2328);
            _InterlockedExchange64((volatile __int64 *)(v194 + 2328), v193);
            v192 = *(_QWORD *)(v9 + 8);
          }
          v167 -= (unsigned int)v429;
          v195 = (_DWORD)v399 << *(_DWORD *)(v192 + 64);
          v424 -= (unsigned int)v399;
          v408 += v195;
          v426 = (struct SmsContainer *)((char *)v426 + (unsigned int)v399);
          v196 = CmsVolume::IsVolumeOnSmr((CmsVolume *)v192);
          LODWORD(v20) = 0;
          if ( v196 && v425 && (*((_BYTE *)v425 + 104) & 2) != 0 )
          {
            v204 = v412;
            v18 = -1073741536;
            v15 = v390;
            v205 = v427;
            v389 = 0;
            v388 = 1;
            *((_BYTE *)v390 + 25) |= 4u;
            *(_QWORD *)(v204 + 32) = v205;
            *(_DWORD *)(v204 + 4) = *((_DWORD *)v15 + 18);
            *(_DWORD *)(v204 + 8) = *((_DWORD *)v15 + 19);
            *(_DWORD *)(v204 + 24) = v409;
            *(_DWORD *)v204 = v401;
            *(_QWORD *)(v204 + 40) = v413;
            *(_QWORD *)(v204 + 48) = P;
            *(_QWORD *)(v204 + 16) = v198;
            *(_DWORD *)(v204 + 28) = v197;
            goto LABEL_46;
          }
        }
        v199 = *(_QWORD *)(v9 + 8);
        v165 = (*((_QWORD *)&v457 + 1) << *(_DWORD *)(v199 + 64)) + v409;
        v409 = v165;
        if ( (*v418 & 8) != 0 )
          CmsVolumeContainer::UnpinContainer(
            (CmsVolumeContainer *)v9,
            (struct CmsTransactionContext *)v10,
            (unsigned __int64)v457 >> ((unsigned __int8)*(_DWORD *)(v199 + 76) + 1),
            0);
        v171 = v406;
        v170 = v387;
      }
      v168 = v401 + 1;
      v401 = v168;
    }
    while ( v168 < *((_DWORD *)v15 + 157) );
    v169 = PerformanceCounter;
  }
  v200 = KeQueryPerformanceCounter(0);
  _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(v9 + 8) + 912LL), 1u);
  _InterlockedExchangeAdd(
    (volatile signed __int32 *)(*(_QWORD *)(v9 + 8) + 908LL),
    10000000 * (v200.QuadPart - v169.QuadPart) / PerformanceFrequency.QuadPart);
  v201 = CmsVolume::IsVolumeOnSmr(*(CmsVolume **)(v9 + 8));
  v20 = 0;
  if ( v201 && v425 )
  {
    v203 = v412;
    v15 = v390;
    v389 = 0;
    *(_QWORD *)(v412 + 16) = -1;
    *(_QWORD *)(v203 + 48) = P;
    *(_QWORD *)(v203 + 40) = v413;
    *(_DWORD *)v203 = -1;
    *(_DWORD *)(v203 + 28) = -1;
    *(_DWORD *)(v203 + 24) = -1;
    *(_DWORD *)(v203 + 4) = *((_DWORD *)v15 + 18);
    *(_DWORD *)(v203 + 8) = *((_DWORD *)v15 + 19);
  }
  else
  {
    v15 = v390;
  }
  v95 = v393;
  v152 = v202;
  v399 = v15;
LABEL_246:
  v153 = (__int64 *)v502;
  do
  {
    if ( v153[1] <= (unsigned __int64)v20 )
      break;
    v477 = *(_OWORD *)v153;
    v154 = (unsigned __int8)v396;
    LOBYTE(v396) = v152 + v396;
    v155 = CmsVolumeContainer::ContainerRangeToRealRangeUnsafe(v9, v10, &v477, &v528[v154]);
    v20 = 0;
    v18 = v155;
    if ( v155 < 0 )
      goto LABEL_46;
    v153 += 2;
    v152 = 1;
  }
  while ( v153 < &v503 );
  v156 = (__int64)v20;
  v527[4] = v528[0];
  v527[5] = v528[1];
  v527[6] = v528[2];
  v527[7] = v528[3];
  v508[0] = v502[0];
  v508[1] = v502[1];
  v508[2] = v502[2];
  v508[3] = v502[3];
  v430 = (__int64)v20;
  v417 = (unsigned int)v20;
  if ( v414 )
  {
    v157 = (unsigned __int16)v20;
    v444 = v20;
    v396 = (unsigned __int16)v20;
    do
    {
      v406 = *((_QWORD *)v441 + v157);
      v158 = CmsVolumeContainer::PinContainer(
               (CmsVolumeContainer *)v9,
               (struct CmsTransactionContext *)v10,
               v406,
               &v444,
               v20,
               (unsigned __int8)v20,
               (unsigned __int8)v20);
      LODWORD(v20) = 0;
      v18 = v158;
      if ( v158 < 0 )
        goto LABEL_46;
      if ( !*((_QWORD *)v444 + 73) )
      {
        CmsVolumeContainer::UnpinContainer((CmsVolumeContainer *)v9, (struct CmsTransactionContext *)v10, v406, 0);
        goto LABEL_147;
      }
      if ( v402 && *(_QWORD *)(v402 + 152) )
        LOBYTE(v20) = *(_DWORD *)(v402 + 8) != 0;
      v159 = CmsVolumeContainer::RecompactEmbeddedContainer(
               (CmsVolumeContainer *)v9,
               (struct CmsTransactionContext *)v10,
               v15,
               v444,
               &v428,
               (unsigned __int8 *)P,
               v413,
               (unsigned __int8 *)v403,
               (unsigned __int64)v95 << *(_DWORD *)(*(_QWORD *)(v9 + 8) + 64LL),
               (char)v20,
               &v430,
               (struct _RANGE_TUPLE *)v528,
               (struct _RANGE_TUPLE *)v508,
               &v434,
               v416,
               v391,
               &v411);
      v20 = 0;
      v18 = v159;
      if ( v159 < 0 )
      {
        if ( !v411 || *((struct SmsContainer **)v411 + 1) != v444 )
        {
          CmsVolumeContainer::UnpinContainer((CmsVolumeContainer *)v9, (struct CmsTransactionContext *)v10, v406, 0);
          goto LABEL_148;
        }
        goto LABEL_46;
      }
      v157 = ++v396;
    }
    while ( v396 < v414 );
  }
  NextForwardRunSet = CmsClusterOperations::FindNextForwardRunSet(&v428, 0, &v417);
  if ( NextForwardRunSet )
  {
    v161 = v402;
    v162 = (char *)P;
    v163 = (char *)v403;
    do
    {
      if ( v417 <= v156 )
        v164 = 0;
      else
        v164 = RtlNumberOfSetBitsInRange(&BitMapHeader, (unsigned int)v156, v417 - (unsigned int)v156);
      v217 = v164 + v156;
      v218 = *(_QWORD *)(v9 + 8);
      if ( !*(_QWORD *)(v218 + 2888) && (!v161 || !*(_QWORD *)(v161 + 152) || !*(_DWORD *)(v161 + 8)) )
        memmove(
          &v163[v430 << *(_DWORD *)(v218 + 64)],
          &v162[v217 << *(_DWORD *)(v218 + 64)],
          NextForwardRunSet * *(_DWORD *)(v218 + 68));
      v430 += NextForwardRunSet;
      v156 = NextForwardRunSet + v217;
      NextForwardRunSet = CmsClusterOperations::FindNextForwardRunSet(&v428, NextForwardRunSet + v417, &v417);
    }
    while ( NextForwardRunSet );
    v14 = v405;
    v15 = v399;
    v10 = v449;
  }
  v219 = v402;
  if ( v430 >= v95 || v402 && *(_QWORD *)(v402 + 152) && *(_DWORD *)(v402 + 8) )
  {
    v220 = v403;
  }
  else
  {
    v220 = v403;
    memset(
      (char *)v403 + (v430 << *(_DWORD *)(*(_QWORD *)(v9 + 8) + 64LL)),
      0,
      (v95 - v430) << *(_DWORD *)(*(_QWORD *)(v9 + 8) + 64LL));
  }
  LOBYTE(v20) = 0;
  if ( v398 )
  {
    v383 = &v436;
    LODWORD(v378) = v398;
    v221 = CmsVolumeContainer::CompressContainerBuffer(v9, v398, v220, v95 << *(_DWORD *)(*(_QWORD *)(v9 + 8) + 64LL));
    LODWORD(v20) = 0;
    v18 = v221;
    if ( v221 < 0 )
      goto LABEL_46;
  }
  if ( (*v418 & 2) != 0 )
  {
    v222 = 0;
    if ( *((_DWORD *)v15 + 157) )
    {
      do
      {
        v223 = CmsBPlusTable::AddToDeleteQueue(
                 *(CmsBPlusTable **)(v9 + 64),
                 (struct CmsTransactionContext *)v10,
                 (struct SmsContainer *)((char *)v15
                                       + 16 * v222
                                       + (unsigned int)(*(_DWORD *)(v9 + 232) * *(_DWORD *)(v9 + 228))
                                       + 632),
                 (unsigned __int8)v20,
                 0,
                 0,
                 0,
                 0,
                 0,
                 0);
        LODWORD(v20) = 0;
        v18 = v223;
        if ( v223 < 0 )
          goto LABEL_46;
      }
      while ( (unsigned int)++v222 < *((_DWORD *)v15 + 157) );
    }
  }
  v224 = *(_QWORD *)(v9 + 8);
  if ( !*(_QWORD *)(v224 + 2888) )
  {
    v426 = 0;
    v225 = 0;
    v226 = KeQueryPerformanceCounter(0);
    v227 = *(_QWORD *)(v9 + 8);
    v228 = (__int64 *)v502;
    PerformanceCounter = v226;
    v429 = (__int64 *)v502;
LABEL_351:
    if ( v228[1] )
    {
      LODWORD(v383) = 0;
      HIDWORD(v379) = 0;
      v478 = *(_OWORD *)v228;
      v378 = (struct _RTL_BITMAP *)&v456;
      v456 = 0;
      v229 = CmsVolumeContainer::PinContainerRange(v9, v10, &v478, 1);
      v20 = 0;
      v18 = v229;
      if ( v229 >= 0 )
      {
        v230 = *((_QWORD *)&v456 + 1);
        v231 = v225;
        v406 = *((_QWORD *)&v456 + 1);
        v232 = v456;
        v413 = v456;
        v399 = v225;
        while ( 1 )
        {
          v233 = *(CmsVolume **)(v9 + 8);
          v234 = *(unsigned int *)(v9 + 280);
          v454 = v20;
          v446 = v20;
          v235 = *((_DWORD *)v233 + 16);
          if ( v234 >= v230 )
            v234 = v230;
          v507 = 0;
          v236 = v234 << v235;
          *(_QWORD *)&v507 = v232 << *((_DWORD *)v233 + 16);
          *((_QWORD *)&v507 + 1) = v234 << v235;
          if ( !CmsVolume::IsVolumeOnSmr(v233) )
            goto LABEL_365;
          if ( !v219 || *(struct SmsContainer **)(v219 + 152) == v20 )
            break;
          v238 = *(unsigned int *)(v219 + 8);
          v239 = v234;
          if ( v238 < (unsigned __int64)v231 + v236 )
          {
            if ( v238 <= (unsigned __int64)v231 )
              break;
            v236 = (unsigned int)v238 - (_QWORD)v231;
            v239 = v236 >> v237[16];
            if ( ((v237[17] - 1) & (unsigned int)v236) != 0 )
            {
              v18 = -1073741823;
              goto LABEL_493;
            }
          }
LABEL_381:
          v231 = (struct SmsContainer *)((char *)v231 + v236);
          v232 = v239 + v413;
          v230 = v406 - v239;
          v399 = v231;
          v406 = v230;
          v413 += v239;
          if ( !v230 )
          {
            v255 = v429;
            CmsVolumeContainer::UnpinContainer(
              (CmsVolumeContainer *)v9,
              (struct CmsTransactionContext *)v10,
              (unsigned __int64)*v429 >> ((unsigned __int8)v237[19] + 1),
              0);
            v228 = v255 + 2;
            v227 = *(_QWORD *)(v9 + 8);
            v429 = v228;
            v225 = (struct SmsContainer *)((char *)v426 + (*((_QWORD *)&v456 + 1) << *(_DWORD *)(v227 + 64)));
            v426 = v225;
            if ( v228 < &v503 )
              goto LABEL_351;
            goto LABEL_383;
          }
        }
        v479 = v507;
        v240 = MsAcquireContainerWriteHead(v10, &v479, &v454, &v446);
        LODWORD(v20) = 0;
        v18 = v240;
        if ( v240 < 0 )
          goto LABEL_493;
        v231 = v399;
LABEL_365:
        if ( byte_1C0114F75[12 * (int)CmsVolume::GetStorageTierForRange(*(_QWORD *)(v9 + 8), v10, &v507)]
          || byte_1C0136992 )
        {
          LODWORD(v379) = 0;
          ((void (__fastcall *)(_QWORD, _QWORD, __int64, __int128 *, char *, struct _SmsQuickIndex *))qword_1C0136B40)(
            *(_QWORD *)(*(_QWORD *)(v9 + 8) + 48LL),
            0,
            1,
            &v507,
            (char *)&v507 + 8,
            v379);
        }
        v241 = KeQueryPerformanceCounter(0);
        v242 = *(_QWORD *)(v9 + 8);
        v243 = v241;
        v379 = (struct _SmsQuickIndex *)((char *)v403 + (_QWORD)v231);
        v244 = v413 << *(_DWORD *)(v242 + 64);
        v245 = *(_QWORD *)(v242 + 48);
        v453 = v241;
        LODWORD(v378) = v236;
        v18 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, unsigned __int64))qword_1C0136A60)(v245, 0, 0, v244);
        v246 = CmsVolume::IsVolumeOnSmr(*(CmsVolume **)(v9 + 8));
        LODWORD(v20) = 0;
        if ( v246 && v454 )
        {
          MsReleaseContainerWriteHead(v247, v454, v446);
          LODWORD(v20) = 0;
        }
        if ( v18 < 0 )
          goto LABEL_493;
        v248 = KeQueryPerformanceCounter(0);
        v249 = *(CmsVolume **)(v9 + 8);
        v447 = v248;
        if ( CmsVolume::IsVolumeOnSmr(v249) )
        {
          v252 = v250 - v243.QuadPart;
          _InterlockedExchangeAdd64(v251 + 293, v252);
          _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(v9 + 8) + 2360LL), 1u);
          v253 = *(_QWORD *)(v9 + 8);
          if ( v252 <= *(_QWORD *)(v253 + 2352) )
            v252 = *(_QWORD *)(v253 + 2352);
          _InterlockedExchange64((volatile __int64 *)(v253 + 2352), v252);
          v251 = *(volatile signed __int64 **)(v9 + 8);
        }
        if ( CmsVolume::IsVolumeOnSmr((CmsVolume *)v251) )
        {
          v237 = v254;
          if ( v425 )
          {
            if ( (*((_BYTE *)v425 + 104) & 2) != 0 && v234 < v406 )
            {
              LODWORD(v20) = 0;
              v275 = (__int64 *)v502;
              v276 = 0;
              do
              {
                if ( !v275[1] )
                  break;
                ++v276;
                v275 += 2;
              }
              while ( v275 < &v503 );
              v277 = v402;
              if ( !*(_QWORD *)(v402 + 16) )
              {
                if ( v276 == 2 )
                {
                  v278 = *(_QWORD *)(v9 + 8);
                  goto LABEL_416;
                }
                if ( v276 == 1 )
                {
                  v278 = *(_QWORD *)(v9 + 8);
                  if ( ((*(_DWORD *)(v278 + 80) - 1) & *(_QWORD *)&v502[0]) == 0 )
                  {
LABEL_416:
                    v279 = *(_DWORD *)(v278 + 76) + 1;
                    v448 = 0;
                    v280 = CmsVolumeContainer::PinContainer(
                             (CmsVolumeContainer *)v9,
                             (struct CmsTransactionContext *)v10,
                             *(_QWORD *)&v502[v276 - 1] >> v279,
                             &v448,
                             0,
                             0,
                             0);
                    LODWORD(v20) = 0;
                    v18 = v280;
                    if ( v280 < 0 )
                      goto LABEL_493;
                    v281 = v448;
                    *((_DWORD *)v448 + 143) |= 0x1000u;
                    *(_QWORD *)(v277 + 16) = *((_QWORD *)v281 + 69);
                    CmsVolumeContainer::UnpinContainer(
                      (CmsVolumeContainer *)v9,
                      (struct CmsTransactionContext *)v10,
                      *((_QWORD *)v281 + 69),
                      0);
                    LODWORD(v20) = 0;
                  }
                }
              }
              v18 = -1073741536;
              v282 = v427;
              *(_QWORD *)(v277 + 152) = v403;
              v283 = v236 + (_DWORD)v399;
              v392 = 0;
              v15 = v390;
              *(_DWORD *)(v277 + 8) = v283;
              v284 = v412;
              v388 = 1;
              *((_BYTE *)v15 + 25) |= 4u;
              *(_QWORD *)(v284 + 32) = v282;
              goto LABEL_494;
            }
          }
        }
        v231 = v399;
        v20 = 0;
        v219 = v402;
        goto LABEL_381;
      }
      goto LABEL_493;
    }
LABEL_383:
    v256 = ((__int64 (__fastcall *)(_QWORD))qword_1C0136AB0)(*(_QWORD *)(v227 + 48));
    LODWORD(v20) = 0;
    v18 = v256;
    if ( v256 >= 0 )
    {
      v257 = *(_QWORD *)&KeQueryPerformanceCounter(0) - PerformanceCounter.QuadPart;
      _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(v9 + 8) + 920LL), 1u);
      _InterlockedExchangeAdd(
        (volatile signed __int32 *)(*(_QWORD *)(v9 + 8) + 916LL),
        10000000 * v257 / PerformanceFrequency.QuadPart);
      v224 = *(_QWORD *)(v9 + 8);
      v15 = v390;
      goto LABEL_385;
    }
LABEL_493:
    v15 = v390;
LABEL_494:
    v19 = v386;
    goto LABEL_47;
  }
LABEL_385:
  if ( (*v418 & 8) != 0 )
  {
    if ( (*v418 & 2) != 0 && !*(_QWORD *)(v224 + 2888) )
    {
      v258 = CmsVolumeContainer::DeleteCompressionUnitOffsetsForContainer(
               (CmsVolumeContainer *)v9,
               (struct CmsTransactionContext *)v10,
               v15);
      LODWORD(v20) = 0;
      v18 = v258;
      if ( v258 < 0 )
        goto LABEL_46;
    }
    if ( v398 )
    {
      if ( !*(_QWORD *)(*(_QWORD *)(v9 + 8) + 2888LL) )
      {
        v259 = a6;
        inserted = CmsVolumeContainer::InsertCompressionUnitOffsetsForContainer(
                     (CmsVolumeContainer *)v9,
                     (struct CmsTransactionContext *)v10,
                     v15,
                     a6,
                     (unsigned __int16 *)v436,
                     v423);
        LODWORD(v20) = 0;
        v18 = inserted;
        if ( inserted < 0 )
          goto LABEL_46;
        goto LABEL_393;
      }
      RtlNumberOfSetBits(&v428);
    }
    v259 = a6;
LABEL_393:
    v439[3] = 3;
    updated = CmsTable::UpdateRow(
                *(CmsTable **)(v9 + 64),
                (struct CmsTransactionContext *)v10,
                (struct _CmsRow *)v521,
                0,
                (struct _SmsQuickIndex *)v378);
    LODWORD(v20) = 0;
    v18 = updated;
    if ( updated >= 0 )
    {
      v261 = 0;
      v262 = (__m128i *)v508;
      do
      {
        if ( !v262->m128i_i64[1] )
          break;
        ++v261;
        ++v262;
      }
      while ( v262 < &v509 );
      v263 = CmsRowWithBuffer::NewLength(
               (CmsRowWithBuffer *)v511,
               0,
               *(_DWORD *)(v9 + 232) * *(_DWORD *)(v9 + 228) + 16 * (v261 + 5),
               0x10u,
               0);
      LODWORD(v20) = 0;
      v18 = v263;
      if ( v263 >= 0 )
      {
        v264 = v513;
        memset(v513, 0, (unsigned int)Size);
        v265 = Src;
        v266 = 0;
        *v264 = *(_OWORD *)Src;
        v264[1] = v265[1];
        v264[2] = v265[2];
        v264[3] = v265[3];
        v264[4] = v265[4];
        v267 = *((_QWORD *)v265 + 10);
        v268 = (__m128i *)v508;
        *((_QWORD *)v264 + 10) = v267;
        do
        {
          if ( !v268->m128i_i64[1] )
            break;
          ++v266;
          ++v268;
        }
        while ( v268 < &v509 );
        *((_DWORD *)v264 + 19) = v266;
        for ( i = 0;
              i < *((_DWORD *)v264 + 19);
              *(_OWORD *)((char *)&v264[v271] + (unsigned int)(*(_DWORD *)(v9 + 232) * *(_DWORD *)(v9 + 228))) = v508[v270] )
        {
          v270 = i;
          v271 = i++ + 5LL;
        }
        v272 = v398;
        *((_DWORD *)v264 + 12) = v398;
        *((_DWORD *)v264 + 13) = v259;
        *((_DWORD *)v264 + 5) = *((_DWORD *)v264 + 5) & 0xFFFFFFFD | (v272 != 0 ? 2 : 0);
        v273 = CmsTable::UpdateRow(
                 *(CmsTable **)(v9 + 16),
                 (struct CmsTransactionContext *)v10,
                 (struct _CmsRow *)v511,
                 0,
                 (struct _SmsQuickIndex *)v378);
        LODWORD(v20) = 0;
        v18 = v273;
        if ( v273 >= 0 )
        {
          if ( *(_QWORD *)(*(_QWORD *)(v9 + 8) + 2888LL)
            || (LODWORD(v378) = v398,
                ContainerCompressionRedo = CmsVolumeContainer::GenerateContainerCompressionRedo(v9, v10, v427, 0),
                LODWORD(v20) = 0,
                v18 = ContainerCompressionRedo,
                ContainerCompressionRedo >= 0) )
          {
LABEL_406:
            _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(v9 + 8) + 904LL), 1u);
            goto LABEL_493;
          }
        }
      }
    }
LABEL_46:
    v19 = (char)v20;
    goto LABEL_47;
  }
  v286 = *(_QWORD *)&v502[0] >> ((unsigned __int8)*(_DWORD *)(v224 + 76) + 1);
  v410 = 0;
  v287 = CmsVolumeContainer::PinContainer(
           (CmsVolumeContainer *)v9,
           (struct CmsTransactionContext *)v10,
           v286,
           &v419,
           0,
           0,
           0);
  LODWORD(v20) = 0;
  v18 = v287;
  if ( v287 < 0 )
    goto LABEL_46;
  *((_BYTE *)v419 + 24) |= 1u;
  if ( *(_QWORD *)&v502[1] )
  {
    v288 = CmsVolumeContainer::PinContainer(
             (CmsVolumeContainer *)v9,
             (struct CmsTransactionContext *)v10,
             *(_QWORD *)&v502[1] >> ((unsigned __int8)*(_DWORD *)(*(_QWORD *)(v9 + 8) + 76LL) + 1),
             &v420,
             0,
             0,
             0);
    LODWORD(v20) = 0;
    v18 = v288;
    if ( v288 < 0 )
      goto LABEL_46;
    *((_BYTE *)v420 + 24) |= 1u;
  }
  v289 = v411;
  if ( v411 )
  {
    do
    {
      ExAcquirePushLockExclusiveEx(*((_QWORD *)v289 + 1) + 136LL, 0);
      v289 = *(struct SmsCompactionUndoChain **)v289;
      LODWORD(v20) = 0;
    }
    while ( v289 );
    v290 = v411;
    if ( v411 )
    {
      do
      {
        v291 = CmsTable::UpdateRow(
                 *(CmsTable **)(v9 + 64),
                 (struct CmsTransactionContext *)v10,
                 (struct SmsCompactionUndoChain *)((char *)v290 + 144),
                 0,
                 (struct _SmsQuickIndex *)v378);
        LODWORD(v20) = 0;
        v18 = v291;
        if ( v291 < 0 )
          break;
        ++*(_DWORD *)(*((_QWORD *)v290 + 1) + 80LL);
        *(_BYTE *)(*((_QWORD *)v290 + 1) + 24LL) |= 1u;
        v292 = (unsigned int)(*(_DWORD *)(v9 + 228) * *(_DWORD *)(v9 + 232));
        v293 = *((_QWORD *)v290 + 1);
        *(_OWORD *)(v292 + v293 + 632) = *((_OWORD *)v290 + 1);
        *(_OWORD *)(v292 + v293 + 648) = *((_OWORD *)v290 + 2);
        *(_OWORD *)(v292 + v293 + 664) = *((_OWORD *)v290 + 3);
        *(_OWORD *)(v292 + v293 + 680) = *((_OWORD *)v290 + 4);
        *(_DWORD *)(*((_QWORD *)v290 + 1) + 628LL) = *((unsigned __int16 *)v290 + 129);
        v294 = *(void **)(*((_QWORD *)v290 + 1) + 144LL);
        if ( v294 )
        {
          memmove(
            v294,
            (const void *)(*((_QWORD *)v290 + 21) + *(unsigned __int8 *)(*((_QWORD *)v290 + 21) + 40LL)),
            (unsigned __int64)*(unsigned int *)(*(_QWORD *)(v9 + 8) + 80LL) >> 3);
          LODWORD(v20) = 0;
          *((_BYTE *)v290 + 260) = 1;
        }
        v290 = *(struct SmsCompactionUndoChain **)v290;
      }
      while ( v290 );
      v295 = v411;
      while ( v295 )
      {
        ExReleasePushLockEx(*((_QWORD *)v295 + 1) + 136LL, 0);
        v295 = *(struct SmsCompactionUndoChain **)v295;
        LODWORD(v20) = 0;
      }
    }
    if ( v18 < 0 )
      goto LABEL_494;
  }
  v296 = CmsClusterOperations::FindNextForwardRunSet(&v428, 0, &v410);
  v20 = 0;
  v401 = v296;
  if ( !v296 )
  {
    NextContainerId = a8;
LABEL_469:
    if ( !*(_QWORD *)(*(_QWORD *)(v9 + 8) + 2888LL) )
    {
      LODWORD(v378) = v398;
      v326 = CmsVolumeContainer::GenerateContainerCompressionRedo(v9, v10, v427, NextContainerId);
      LODWORD(v20) = 0;
      v18 = v326;
      if ( v326 < 0 )
        goto LABEL_494;
    }
    for ( j = v411; j; j = *(struct SmsCompactionUndoChain **)j )
    {
      v328 = CmsVolumeContainer::PersistContainerUnsynchronized(
               (CmsVolumeContainer *)v9,
               (struct CmsTransactionContext *)v10,
               *((struct SmsContainer **)j + 1));
      LODWORD(v20) = 0;
      v18 = v328;
      if ( v328 < 0 )
        goto LABEL_494;
    }
    v19 = v386;
    if ( CmsVolume::IsVolumeOnSmr(*(CmsVolume **)(v9 + 8)) )
    {
      if ( !v386 )
        goto LABEL_486;
      v329 = CmsVolumeContainer::GetContainerReference(
               (CmsVolumeContainer *)v9,
               (struct CmsTransactionContext *)v10,
               NextContainerId,
               &v440,
               (unsigned __int8)v20,
               (unsigned __int8)v20,
               (unsigned __int8)v20);
      v20 = 0;
      v18 = v329;
      if ( v329 < 0 )
        goto LABEL_47;
    }
    if ( v386 )
    {
      ExAcquirePushLockExclusiveEx(v9 + 40, 0);
      *(_QWORD *)(*(_QWORD *)(v9 + 32)
                + 8LL
                * (*(_QWORD *)((char *)v15 + (unsigned int)(*(_DWORD *)(v9 + 232) * *(_DWORD *)(v9 + 228)) + 632) >> *(_DWORD *)(*(_QWORD *)(v9 + 8) + 76LL))) = NextContainerId;
      ExReleasePushLockEx(v9 + 40, 0);
      v330 = v418;
      v331 = v398;
      v332 = v398;
      v333 = v433;
      *v433 &= 0x3Fu;
      *((_BYTE *)v15 + 25) &= ~1u;
      *v330 |= 8u;
      *((_WORD *)v15 + 304) = 0;
      *v330 = *v330 & 0xFFFFFFFD | (v332 != 0 ? 2 : 0);
      v334 = 0;
      *((_DWORD *)v15 + 150) = v331;
      *((_DWORD *)v15 + 151) = a6;
      v335 = (__m128i *)v508;
      do
      {
        if ( !v335->m128i_i64[1] )
          break;
        ++v334;
        ++v335;
      }
      while ( v335 < &v509 );
      *((_DWORD *)v15 + 157) = v334;
      v336 = (char *)v15 + (unsigned int)(*(_DWORD *)(v9 + 232) * *(_DWORD *)(v9 + 228));
      memset(v336 + 632, 0, 0x40u);
      v20 = 0;
      v337 = 0;
      if ( *((_DWORD *)v15 + 157) )
      {
        do
        {
          v338 = v337++;
          *(_OWORD *)&v336[16 * v338 + 632] = v508[v338];
        }
        while ( v337 < *((_DWORD *)v15 + 157) );
        v14 = v405;
      }
      v19 = v386;
      *v333 |= 1u;
    }
LABEL_486:
    if ( (struct SmsContainer *)v437 != v20 || *((struct SmsContainer **)&v437 + 1) != v20 )
    {
      ExAcquireAutoExpandPushLockExclusive(*(_QWORD *)(*(_QWORD *)(v9 + 8) + 3424LL), 0);
      v18 = CmsVolumeContainer::AddReservedContainer(
              (CmsVolumeContainer *)v9,
              (struct CmsTransactionContext *)v10,
              (const struct _RANGE *)&v437,
              1u,
              1);
      CmsVolume::ProcessReservationUndo(*(CmsVolume **)(v9 + 8), &v510);
      _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(v9 + 8) + 3368LL), 1u);
      ExReleaseAutoExpandPushLockExclusive(*(_QWORD *)(*(_QWORD *)(v9 + 8) + 3424LL), 0);
      v20 = 0;
      if ( v18 < 0 )
      {
        v15 = v390;
        v18 = 0;
        goto LABEL_47;
      }
      LOBYTE(v20) = 1;
      CmsAllocator::ReserveRegion(v339, v404, 8, v20);
      LODWORD(v20) = 0;
    }
    goto LABEL_406;
  }
  v19 = 1;
  NextContainerId = a8;
  v386 = 1;
  if ( a8 )
  {
    v298 = *(_QWORD *)(*(_QWORD *)(v9 + 8) + 3048LL);
    if ( a8 >= *(_QWORD *)(v298 + 72) )
    {
      *(_BYTE *)(v298 + 372) |= 2u;
      *(_QWORD *)(v298 + 72) = a8 + 1;
    }
  }
  else
  {
    NextContainerId = CmsVolumeContainer::GetNextContainerId((CmsVolumeContainer *)v9);
  }
  if ( v398 != (_DWORD)v20 )
  {
    if ( *(struct SmsContainer **)(*(_QWORD *)(v9 + 8) + 2888LL) == v20 )
    {
      v299 = CmsVolumeContainer::InsertCompressionUnitOffsetsForContainer(
               (CmsVolumeContainer *)v9,
               (struct CmsTransactionContext *)v10,
               v15,
               a6,
               (unsigned __int16 *)v436,
               v423);
      v20 = 0;
      v18 = v299;
      if ( v299 < 0 )
        goto LABEL_47;
    }
    else
    {
      RtlNumberOfSetBits(&v428);
      v20 = 0;
    }
  }
  v300 = CmsTable::InsertRow(
           *(CmsTable **)(v9 + 64),
           (struct CmsTransactionContext *)v10,
           (struct _CmsRow *)v521,
           0x32u,
           (unsigned int)v20,
           v20,
           (struct _SmsPreAllocatedRow *)v380,
           (unsigned int)v383,
           (unsigned __int64 *)v20);
  LODWORD(v20) = 0;
  v18 = v300;
  if ( v300 >= 0 )
  {
    v439[3] = 3;
    v301 = CmsTable::InsertRow(
             *(CmsTable **)(v9 + 64),
             (struct CmsTransactionContext *)v10,
             (struct _CmsRow *)v521,
             0x32u,
             0,
             0,
             (struct _SmsPreAllocatedRow *)v381,
             v384,
             0);
    LODWORD(v20) = 0;
    v18 = v301;
    if ( v301 >= 0 )
    {
      v302 = v410;
      v303 = v401;
      v304 = v434;
      if ( v434 >= *(_QWORD *)v404 + (unsigned __int64)v410 )
        v304 = *(_QWORD *)v404 + v410;
      v434 = v304;
      while ( 1 )
      {
        v397 += v303;
        v305 = v404;
        v470[0] = *(_QWORD *)v404 + v302;
        v470[1] = v303;
        v306 = CmsContainerRangeMap::AddRange(
                 v416,
                 (struct CmsTransactionContext *)v10,
                 (const struct _RANGE *)v470,
                 0,
                 0,
                 0,
                 0,
                 0,
                 0,
                 0);
        LODWORD(v20) = 0;
        v18 = v306;
        if ( v306 < 0 )
          goto LABEL_494;
        v401 = CmsClusterOperations::FindNextForwardRunSet(&v428, v401 + v410, &v410);
        v303 = v401;
        if ( !v401 )
        {
          v307 = CmsRowWithBuffer::NewLength(
                   (CmsRowWithBuffer *)v511,
                   0,
                   *(_DWORD *)(v9 + 232) * *(_DWORD *)(v9 + 228) + 16 * (*((_DWORD *)v15 + 157) + 5),
                   0x10u,
                   0);
          LODWORD(v20) = 0;
          v18 = v307;
          if ( v307 < 0 )
            goto LABEL_494;
          v308 = v513;
          TotalFree = SmsAllocationRegionEx::GetTotalFree(v305);
          v310 = *((_QWORD *)v305 + 1) - v391[0] - v397 - TotalFree;
          memmove(v308, Src, (unsigned int)Size);
          *v308 = NextContainerId;
          v311 = 0;
          *((_WORD *)v308 + 28) = 0;
          if ( v310 >= 0 )
            v311 = v310;
          v308[4] = v311;
          v312 = CmsTable::InsertRow(
                   *(CmsTable **)(v9 + 16),
                   (struct CmsTransactionContext *)v10,
                   (struct _CmsRow *)v511,
                   0x32u,
                   0,
                   0,
                   (struct _SmsPreAllocatedRow *)v382,
                   v385,
                   0);
          LODWORD(v20) = 0;
          v18 = v312;
          if ( v312 < 0 )
            goto LABEL_494;
          v313 = 0;
          v314 = (__m128i *)v508;
          do
          {
            if ( !v314->m128i_i64[1] )
              break;
            ++v313;
            ++v314;
          }
          while ( v314 < &v509 );
          v315 = CmsRowWithBuffer::NewLength(
                   (CmsRowWithBuffer *)v511,
                   0,
                   *(_DWORD *)(v9 + 232) * *(_DWORD *)(v9 + 228) + 16 * (v313 + 5),
                   0x10u,
                   0);
          LODWORD(v20) = 0;
          v18 = v315;
          if ( v315 < 0 )
            goto LABEL_494;
          v316 = v513;
          memset(v513, 0, (unsigned int)Size);
          v317 = Src;
          *v316 = *(_OWORD *)Src;
          v316[1] = v317[1];
          v316[2] = v317[2];
          v316[3] = v317[3];
          v316[4] = v317[4];
          v318 = *((_QWORD *)v317 + 10);
          v319 = (__m128i *)v508;
          *((_QWORD *)v316 + 10) = v318;
          *((_DWORD *)v316 + 5) |= 8u;
          v320 = 0;
          do
          {
            if ( !v319->m128i_i64[1] )
              break;
            ++v320;
            ++v319;
          }
          while ( v319 < &v509 );
          *((_DWORD *)v316 + 19) = v320;
          v321 = 0;
          for ( *((_WORD *)v316 + 28) = 0;
                v321 < *((_DWORD *)v316 + 19);
                *(_OWORD *)((char *)&v316[v323] + (unsigned int)(*(_DWORD *)(v9 + 232) * *(_DWORD *)(v9 + 228))) = v508[v322] )
          {
            v322 = v321;
            v323 = v321++ + 5LL;
          }
          v324 = v398;
          *((_DWORD *)v316 + 12) = v398;
          *((_DWORD *)v316 + 5) = *((_DWORD *)v316 + 5) & 0xFFFFFFFD | (v324 != 0 ? 2 : 0);
          *((_DWORD *)v316 + 13) = a6;
          *((_QWORD *)v316 + 4) -= v391[0];
          v325 = CmsTable::UpdateRow(
                   *(CmsTable **)(v9 + 16),
                   (struct CmsTransactionContext *)v10,
                   (struct _CmsRow *)v511,
                   0,
                   (struct _SmsQuickIndex *)v378);
          LODWORD(v20) = 0;
          v18 = v325;
          if ( v325 < 0 )
            goto LABEL_494;
          goto LABEL_469;
        }
        v302 = v410;
      }
    }
  }
LABEL_47:
  if ( v415 )
  {
    _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)(v9 + 8) + 2896LL), -v415);
    v15 = v390;
    v415 = (unsigned int)v20;
  }
  CmsVolume::ProcessReservationUndo(*(CmsVolume **)(v9 + 8), &v510);
  if ( v18 < 0 )
  {
    v356 = v411;
    if ( !v411 )
      goto LABEL_515;
    do
    {
      ExAcquirePushLockExclusiveEx(*((_QWORD *)v356 + 1) + 136LL, 0);
      *(_DWORD *)(*((_QWORD *)v356 + 1) + 628LL) = *((unsigned __int16 *)v356 + 128);
      v357 = (unsigned int)(*(_DWORD *)(v9 + 232) * *(_DWORD *)(v9 + 228));
      v358 = *((_QWORD *)v356 + 1);
      *(_OWORD *)(v357 + v358 + 632) = *((_OWORD *)v356 + 5);
      *(_OWORD *)(v357 + v358 + 648) = *((_OWORD *)v356 + 6);
      *(_OWORD *)(v357 + v358 + 664) = *((_OWORD *)v356 + 7);
      *(_OWORD *)(v357 + v358 + 680) = *((_OWORD *)v356 + 8);
      if ( *((_BYTE *)v356 + 260) )
      {
        v359 = *((_QWORD *)v356 + 1);
        v360 = *(void **)(v359 + 144);
        _InterlockedCompareExchange64((volatile signed __int64 *)(v359 + 144), 0, (signed __int64)v360);
        CmsLookasides::Free(v360);
      }
      ExReleasePushLockEx(*((_QWORD *)v356 + 1) + 136LL, 0);
      v356 = *(struct SmsCompactionUndoChain **)v356;
    }
    while ( v356 );
    goto LABEL_514;
  }
  *((_BYTE *)v15 + 24) |= 1u;
  *((_WORD *)v15 + 304) = 0;
  if ( !v19 )
  {
    _InterlockedExchangeAdd64((volatile signed __int64 *)v15 + 73, -v397);
    v15 = v390;
  }
  _InterlockedExchangeAdd64((volatile signed __int64 *)v15 + 73, -v391[0]);
  v34 = v411;
  if ( v411 )
  {
    v35 = v420;
    v36 = v419;
    do
    {
      v37 = 0;
      v38 = 0;
      if ( *((_WORD *)v34 + 129) )
      {
        v39 = (_QWORD *)((char *)v34 + 16);
        v40 = *((unsigned __int16 *)v34 + 129);
        do
        {
          v41 = v37 + 1;
          v42 = *v39 >> (*(_BYTE *)(*(_QWORD *)(v9 + 8) + 76LL) + 1);
          if ( v42 != *((_QWORD *)v36 + 69) )
            v41 = v37;
          v37 = v41;
          if ( v420 && v42 == *((_QWORD *)v35 + 69) )
            ++v38;
          v39 += 2;
          --v40;
        }
        while ( v40 );
        v36 = v419;
      }
      if ( *((_WORD *)v34 + 128) )
      {
        v43 = (_QWORD *)((char *)v34 + 80);
        v44 = *((unsigned __int16 *)v34 + 128);
        do
        {
          v45 = v37 - 1;
          v46 = *v43 >> (*(_BYTE *)(*(_QWORD *)(v9 + 8) + 76LL) + 1);
          if ( v46 != *((_QWORD *)v36 + 69) )
            v45 = v37;
          v37 = v45;
          if ( v420 && v46 == *((_QWORD *)v35 + 69) )
            --v38;
          v43 += 2;
          --v44;
        }
        while ( v44 );
        v9 = v460;
        v36 = v419;
      }
      if ( v37 )
        *((_WORD *)v419 + 304) += v37;
      if ( v38 )
        *((_WORD *)v420 + 304) += v38;
      v34 = *(struct SmsCompactionUndoChain **)v34;
    }
    while ( v34 );
    v14 = v405;
    v10 = v449;
  }
  for ( k = 0; ; k = v50 + 1 )
  {
    v48 = 0;
    v49 = (__m128i *)v508;
    do
    {
      if ( !v49->m128i_i64[1] )
        break;
      ++v48;
      ++v49;
    }
    while ( v49 < &v509 );
    if ( k >= v48 )
      break;
    if ( !(unsigned __int8)AreRangesOverlapping<_RANGE>(&v508[k], v502) || (v52 = v419) == 0 )
    {
      if ( !*((_QWORD *)&v502[1] + 1) )
        continue;
      if ( !(unsigned __int8)AreRangesOverlapping<_RANGE>(v51, &v502[1]) )
        continue;
      v52 = v420;
      if ( !v420 )
        continue;
    }
    _InterlockedAdd16((volatile signed __int16 *)v52 + 304, 1u);
  }
  v340 = v397;
  v341 = v397;
  if ( !(v397 + v391[0]) || !v404 )
  {
LABEL_514:
    v15 = v390;
    goto LABEL_515;
  }
  _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(v9 + 8) + 948LL), 1u);
  v342 = v404;
  v343 = SmsAllocationRegionEx::GetTotalFree(v404);
  _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)(v9 + 8) + 944LL), 100 * (v344 - v343) / v345);
  if ( CmsVolume::IsVolumeOnSmr(*(CmsVolume **)(v9 + 8)) )
  {
    v346 = CmsContainerRangeMap::PinInIndex(v416, v434);
    CmsAllocator::UnmaskRangeMapHeadFromFilteredView(*(CmsAllocator **)(*(_QWORD *)(v9 + 8) + 3032LL), v347, v404, v346);
    v15 = v390;
    v471[0] = 0;
    v348 = v390;
    if ( (_WORD)v340 )
      v348 = v440;
    v471[1] = v340 + (unsigned int)v391[0];
    CmsVolumeContainer::AllocateDeallocateRangeSmr(
      (CmsVolumeContainer *)v9,
      (struct CmsTransactionContext *)v10,
      v348,
      (const struct _RANGE *)v471,
      (struct _SmsCheckpointContext *)v378,
      0,
      0,
      0);
  }
  else
  {
    CmsContainerRangeMap::DeleteAll(v416);
    v349 = v404;
    v350 = CmsContainerRangeMap::AddRange(v416, (struct CmsTransactionContext *)v10, v404, 0, 0, 0, 0, 1u, &v421, &v422);
    v472 = 0;
    v18 = v350;
    RtlInitializeBitMap(&v472, *((PULONG *)v349 + 6), *((_DWORD *)v342 + 2));
    RtlSetAllBits(&v472);
    v351 = Resource;
    CmsVolume::MergeIntoRecentlyDeallocated(
      *(CmsVolume **)(v9 + 8),
      (struct _SmsCheckpointState *)&Resource[1].ActiveCount,
      v352,
      v416);
    v353 = *(CmsVolume **)(v9 + 8);
    v450 = 0;
    CmsVolume::LockReservationShared(v353, &v450);
    _InterlockedExchangeAdd64((volatile signed __int64 *)&v351[1].OwnerEntry, *((_QWORD *)v342 + 1));
    if ( v437 != 0 )
    {
      v354 = (CmsVolume *)Resource;
      _InterlockedExchangeAdd64((volatile signed __int64 *)&Resource[1].OwnerEntry.0, *((_QWORD *)v342 + 1));
    }
    CmsVolume::UnlockReservationShared(v354, v450);
    v15 = v390;
  }
  v355 = v404;
  SmsAllocationRegionEx::AdjustFree(v404, v341 + v391[0]);
  CmsAllocator::AdjustAllocatorSummary(
    *(CmsAllocator **)(*(_QWORD *)(v9 + 8) + 3032LL),
    0,
    v341 + (unsigned int)v391[0],
    0,
    0);
  if ( (*((_BYTE *)v355 + 24) & 0xC) == 0 && v425 )
    CmsVolumeAnalyzer::UpdateFillPercentageBitmaps(v425, v355, 0);
LABEL_515:
  if ( v419 )
    CmsVolumeContainer::UnpinContainer(
      (CmsVolumeContainer *)v9,
      (struct CmsTransactionContext *)v10,
      *((_QWORD *)v419 + 69),
      0);
  if ( v420 )
    CmsVolumeContainer::UnpinContainer(
      (CmsVolumeContainer *)v9,
      (struct CmsTransactionContext *)v10,
      *((_QWORD *)v420 + 69),
      0);
  v361 = *(volatile signed __int32 **)(v9 + 8);
  if ( v18 < 0 )
  {
    _InterlockedAdd(v361 + 240, 1u);
    CmsVolume::AbortTopLevelAction(
      *(CmsVolume **)(v9 + 8),
      (struct CmsTransactionContext *)v10,
      (struct _SmsTopLevelAction *)v480);
    v15 = v390;
  }
  else
  {
    CmsVolume::CommitTopLevelAction(
      (CmsVolume *)v361,
      (struct CmsTransactionContext *)v10,
      (struct _SmsTopLevelAction *)v480,
      1u);
  }
  if ( (v14 & 2) != 0 )
    CmsAllocator::TryProtectRegion(v362, v404, 0);
  while ( 1 )
  {
    v364 = v411;
    if ( !v411 )
      break;
    v411 = *(struct SmsCompactionUndoChain **)v411;
    v363 = *((_QWORD *)v364 + 1);
    if ( v363 )
      CmsVolumeContainer::UnpinContainer(
        (CmsVolumeContainer *)v9,
        (struct CmsTransactionContext *)v10,
        *(_QWORD *)(v363 + 552),
        0);
    CmsRowWithBuffer::~CmsRowWithBuffer((struct SmsCompactionUndoChain *)((char *)v364 + 144));
    operator delete(v364);
  }
  if ( (v14 & 1) != 0 )
  {
    SmsContainer::LogActivity(v15, (unsigned int)((_DWORD)v411 + 8), *(_QWORD *)(*(_QWORD *)(v9 + 8) + 1840LL), v18);
    CmsVolumeContainer::UnpinContainerExclusive((CmsVolumeContainer *)v9, (struct CmsTransactionContext *)v10, v15);
  }
  if ( v440 )
  {
    _InterlockedAdd((volatile signed __int32 *)v440 + 22, 0xFFFFFFFF);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v9 + 328), 0, 0x20u);
    --*(_DWORD *)(v10 + 2824);
  }
  v365 = v402;
  v366 = Resource;
  if ( !v402 || !*(_BYTE *)v402 )
    goto LABEL_538;
  if ( v18 >= 0 )
  {
    if ( v386 )
      *(_QWORD *)(v412 + 32) = 0;
    CmsVolumeAnalyzer::FreeResumeFromWriteContextLcns(v425, (struct CmsTransactionContext *)v10, v366 == 0, 1u);
LABEL_538:
    v367 = v388;
    goto LABEL_539;
  }
  v367 = v388;
  if ( !v388 || !*(_QWORD *)(v402 + 152) || !*(_DWORD *)(v402 + 8) )
    CmsVolumeAnalyzer::FreeResumeFromWriteContextLcns(v425, (struct CmsTransactionContext *)v10, Resource == 0, 0);
LABEL_539:
  v368 = v412;
  if ( !v367 )
  {
    if ( v412 )
    {
      v369 = *(_QWORD *)(v412 + 32);
      if ( v369 )
      {
        v451 = 0;
        if ( CmsVolumeContainer::PinContainer(
               (CmsVolumeContainer *)v9,
               (struct CmsTransactionContext *)v10,
               v369,
               &v451,
               0,
               0,
               0) >= 0 )
        {
          v370 = v451;
          *((_BYTE *)v451 + 25) &= ~4u;
          CmsVolumeContainer::UnpinContainer(
            (CmsVolumeContainer *)v9,
            (struct CmsTransactionContext *)v10,
            *((_QWORD *)v370 + 69),
            0);
          *(_QWORD *)(v368 + 32) = 0;
        }
      }
    }
  }
  if ( v366 )
    ExReleaseResourceLite(v366);
  v371 = P;
  if ( !v367 )
  {
    if ( P )
      goto LABEL_559;
    if ( v368 )
    {
      v372 = *(_QWORD *)(v368 + 48);
      if ( v372 )
      {
        if ( _InterlockedCompareExchange64((volatile signed __int64 *)(v9 + 288), v372, 0) )
        {
          v371 = *(PVOID *)(v368 + 48);
LABEL_560:
          ExFreePoolWithTag(v371, 0);
        }
LABEL_561:
        *(_QWORD *)(v368 + 48) = 0;
        goto LABEL_562;
      }
      v371 = P;
    }
  }
  if ( v389 && v371 )
  {
LABEL_559:
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)(v9 + 288), (signed __int64)v371, 0) )
      goto LABEL_560;
    goto LABEL_561;
  }
LABEL_562:
  v373 = v403;
  if ( !v367 )
  {
    if ( v403 )
      goto LABEL_571;
    if ( v365 )
    {
      v374 = *(_QWORD *)(v365 + 152);
      if ( v374 )
      {
        if ( _InterlockedCompareExchange64((volatile signed __int64 *)(v9 + 296), v374, 0) )
        {
          v373 = *(PVOID *)(v365 + 152);
LABEL_572:
          ExFreePoolWithTag(v373, 0);
        }
LABEL_573:
        *(_QWORD *)(v365 + 152) = 0;
        goto LABEL_574;
      }
      v373 = v403;
    }
  }
  if ( v392 && v373 )
  {
LABEL_571:
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)(v9 + 296), (signed __int64)v373, 0) )
      goto LABEL_572;
    goto LABEL_573;
  }
LABEL_574:
  if ( v436 )
    ExFreePoolWithTag(v436, 0);
  v375 = v416;
  if ( v416 )
  {
    CmsContainerRangeMap::DeleteAll(v416);
    CmsContainerRangeMap::`scalar deleting destructor'(v375, v376);
  }
  if ( v422 )
    _InterlockedExchangeAdd((volatile signed __int32 *)(qword_1C0136FA0 + 88), -v422);
  if ( v421 )
    _InterlockedExchangeAdd((volatile signed __int32 *)(qword_1C0136F98 + 88), -v421);
  if ( v441 )
    ExFreePoolWithTag(v441, 0);
  if ( v525 && v524 )
    ExFreePoolWithTag(v524, 0);
  if ( v515 && v514 )
    ExFreePoolWithTag(v514, 0);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x1c00d34d0  mov     rax, rsp
0x1c00d34d3  push    rbp
0x1c00d34d4  push    rbx
0x1c00d34d5  push    rsi
0x1c00d34d6  push    rdi
0x1c00d34d7  push    r12
0x1c00d34d9  push    r13
0x1c00d34db  push    r14
0x1c00d34dd  push    r15
0x1c00d34df  lea     rbp, [rax-708h]
0x1c00d34e6  sub     rsp, 7D8h
0x1c00d34ed  movaps  xmmword ptr [rax-58h], xmm6
0x1c00d34f1  mov     rax, cs:__security_cookie
0x1c00d34f8  xor     rax, rsp
0x1c00d34fb  mov     [rbp+700h+var_60], rax
0x1c00d3502  mov     rax, [rbp+700h+arg_30]
0x1c00d3509  xorps   xmm0, xmm0
0x1c00d350c  mov     [rbp+700h+var_610], rax
0x1c00d3513  xorps   xmm1, xmm1
0x1c00d3516  mov     rax, [rcx+8]
0x1c00d351a  mov     r14, rcx
0x1c00d351d  mov     [rbp+700h+var_558], rcx
0x1c00d3524  mov     r13, rdx
0x1c00d3527  mov     [rbp+700h+var_5D0], rdx
0x1c00d352e  mov     rsi, r8
0x1c00d3531  mov     [rbp+700h+var_698], r8
0x1c00d3535  mov     r12d, r9d
0x1c00d3538  mov     rdx, [rax+0BF8h]
0x1c00d353f  mov     rax, rdx
0x1c00d3542  mov     [rbp+700h+var_6A8], rdx
0x1c00d3546  neg     rax
0x1c00d3549  mov     [rbp+700h+var_75C], r9d
0x1c00d354d  mov     rax, rdx
0x1c00d3550  movdqa  [rbp+700h+var_420], xmm0
0x1c00d3558  sbb     rbx, rbx
0x1c00d355b  lea     rcx, [rdx+0D68h]
0x1c00d3562  and     rbx, rcx
0x1c00d3565  lea     rcx, [rdx+0DA0h]
0x1c00d356c  neg     rax
0x1c00d356f  mov     [rbp+700h+var_6F8], rbx
0x1c00d3573  movups  xmmword ptr [rbp+700h+BitMapHeader.SizeOfBitMap], xmm0
0x1c00d357a  sbb     rax, rax
0x1c00d357d  xor     edi, edi
0x1c00d357f  and     rax, rcx
0x1c00d3582  mov     [rbp+700h+var_778], rdi
0x1c00d3586  mov     [rbp+700h+var_740], rax
0x1c00d358a  xor     edx, edx; Val
0x1c00d358c  lea     rax, [rbp+700h+var_1B0]
0x1c00d3593  mov     [rbp+700h+var_620], rdi
0x1c00d359a  lea     ecx, [rdi+40h]
0x1c00d359d  mov     [rbp+700h+var_1C0], rax
0x1c00d35a4  lea     rax, [rbp+700h+var_120]
0x1c00d35ab  mov     [rbp+700h+var_1B4], ecx
0x1c00d35b1  mov     [rbp+700h+var_130], rax
0x1c00d35b8  mov     r8d, ecx; Size
0x1c00d35bb  xor     eax, eax
0x1c00d35bd  mov     [rbp+700h+var_124], ecx
0x1c00d35c3  lea     rcx, [rbp+700h+var_A0]; void *
0x1c00d35ca  mov     [rbp+700h+var_3F0], rax
0x1c00d35d1  mov     r15d, edi
0x1c00d35d4  mov     [rbp+700h+var_618], rdi
0x1c00d35db  mov     [rbp+700h+var_6E8], edi
0x1c00d35de  mov     [rbp+700h+var_768], edi
0x1c00d35e1  mov     [rbp+700h+var_6E0], rdi
0x1c00d35e5  mov     [rbp+700h+Resource], rdi
0x1c00d35ec  movups  xmmword ptr [rbp+700h+var_690.SizeOfBitMap], xmm1
0x1c00d35f0  mov     [rbp+700h+var_1B8], dil
0x1c00d35f7  mov     [rbp+700h+var_128], dil
0x1c00d35fe  mov     [rbp+700h+var_410], rdi
0x1c00d3605  movups  [rbp+700h+var_400], xmm1
0x1c00d360c  mov     [rbp+700h+var_408], edi
0x1c00d3612  mov     [rbp+700h+var_3D0], edi
0x1c00d3618  mov     [rbp+700h+var_738], rdi
0x1c00d361c  mov     [rbp+700h+P], rdi
0x1c00d3620  movups  [rbp+700h+var_2C0], xmm0
0x1c00d3627  mov     qword ptr [rbp+700h+var_580], rdi
0x1c00d362e  movups  [rbp+700h+var_260], xmm1
0x1c00d3635  mov     qword ptr [rbp+700h+var_580+8], rdi
0x1c00d363c  movups  [rbp+700h+var_5A0], xmm0
0x1c00d3643  movups  [rbp+700h+var_570], xmm1
0x1c00d364a  movups  [rbp+700h+var_520], xmm0
0x1c00d3651  movups  [rbp+700h+var_640], xmm1
0x1c00d3658  call    memset
0x1c00d365d  xor     edx, edx; Val
0x1c00d365f  lea     r8d, [rdi+40h]; Size
0x1c00d3663  lea     rcx, [rbp+700h+var_E0]; void *
0x1c00d366a  call    memset
0x1c00d366f  xor     edx, edx; Val
0x1c00d3671  lea     r8d, [rdi+40h]; Size
0x1c00d3675  lea     rcx, [rbp+700h+var_2B0]; void *
0x1c00d367c  call    memset
0x1c00d3681  xor     edx, edx; Val
0x1c00d3683  lea     r8d, [rdi+40h]; Size
0x1c00d3687  lea     rcx, [rbp+700h+var_240]; void *
0x1c00d368e  call    memset
0x1c00d3693  mov     [rbp+700h+var_648], rdi
0x1c00d369a  or      rax, 0FFFFFFFFFFFFFFFFh
0x1c00d369e  mov     [rbp+700h+var_6B0], edi
0x1c00d36a1  mov     [rbp+700h+var_658], rax
0x1c00d36a8  lea     rcx, [rbp+700h+PerformanceFrequency]; PerformanceFrequency
0x1c00d36af  xor     eax, eax
0x1c00d36b1  mov     [rbp+700h+var_6F0], rdi
0x1c00d36b5  xorps   xmm0, xmm0
0x1c00d36b8  mov     [rbp+700h+var_668], rax
0x1c00d36bf  mov     [rbp+700h+var_4A8], rax
0x1c00d36c6  mov     qword ptr [rbp+700h+PerformanceFrequency], rax
0x1c00d36cd  mov     [rbp+700h+var_5B0], rax
0x1c00d36d4  mov     [rbp+700h+var_5E0], rax
0x1c00d36db  mov     [rbp+700h+var_6C8], rdi
0x1c00d36df  mov     [rbp+700h+var_6C0], rdi
0x1c00d36e3  mov     [rbp+700h+var_730], rdi
0x1c00d36e7  mov     [rbp+700h+var_700], rdi
0x1c00d36eb  mov     [rbp+700h+var_780], dil
0x1c00d36ef  mov     [rbp+700h+var_77D], dil
0x1c00d36f3  mov     [rbp+700h+var_76C], dil
0x1c00d36f7  mov     [rbp+700h+var_77E], dil
0x1c00d36fb  mov     [rbp+700h+var_760], di
0x1c00d36ff  mov     [rbp+700h+var_770], di
0x1c00d3703  mov     byte ptr [rbp+700h+var_762], dil
0x1c00d3707  movups  [rbp+700h+var_1F0], xmm0
0x1c00d370e  mov     [rbp+700h+var_6E4], edi
0x1c00d3711  mov     [rbp+700h+var_6B4], edi
0x1c00d3714  mov     [rbp+700h+var_6B8], edi
0x1c00d3717  mov     [rbp+700h+var_728], edi
0x1c00d371a  call    cs:__imp_KeQueryPerformanceCounter
0x1c00d3721  nop     dword ptr [rax+rax+00h]
0x1c00d3726  mov     rcx, [r14+8]; this
0x1c00d372a  lea     rdx, [rbp+700h+Resource]; struct _SmsCheckpointContext **
0x1c00d3731  call    ?JoinCheckpoint@CmsVolume@@QEAAXPEAPEAU_SmsCheckpointContext@@@Z; CmsVolume::JoinCheckpoint(_SmsCheckpointContext * *)
0x1c00d3736  lea     eax, [rdi+1]
0x1c00d3739  xor     r9d, r9d; unsigned __int8
0x1c00d373c  lea     r8, [rbp+700h+var_440]; struct _SmsTopLevelAction *
0x1c00d3743  mov     byte ptr [rsp+810h+var_7F0], al; char
0x1c00d3747  mov     rdx, r13; struct CmsTransactionContext *
0x1c00d374a  call    ?BeginTopLevelAction@CmsVolume@@QEAAXPEAVCmsTransactionContext@@PEAU_SmsTopLevelAction@@EE@Z; CmsVolume::BeginTopLevelAction(CmsTransactionContext *,_SmsTopLevelAction *,uchar,uchar)
0x1c00d374f  mov     r11, [r14+8]
0x1c00d3753  lea     r8d, [rdi+2]
0x1c00d3757  mov     rax, [r11+0BD0h]
0x1c00d375e  mov     rdx, [rax+20h]
0x1c00d3762  mov     rax, [rdx+10h]
0x1c00d3766  lea     rcx, [rax+rax*2]
0x1c00d376a  shr     rcx, 1
0x1c00d376d  cmp     rcx, [rdx+8]
0x1c00d3771  jnb     short loc_1C00D3783
0x1c00d3773  mov     esi, 0C0390002h
0x1c00d3778  mov     bl, dil
0x1c00d377b  xor     r9d, r9d
0x1c00d377e  jmp     loc_1C00D39E7
0x1c00d3783  mov     ecx, 3
0x1c00d3788  cmp     [r11+77Ch], cx
0x1c00d3790  ja      short loc_1C00D37A5
0x1c00d3792  jnz     short loc_1C00D379E
0x1c00d3794  cmp     [r11+77Eh], r8w
0x1c00d379c  jnb     short loc_1C00D37A5
0x1c00d379e  mov     esi, 0C000029Ch
0x1c00d37a3  jmp     short loc_1C00D3778
0x1c00d37a5  mov     eax, [r14+70h]
0x1c00d37a9  mov     r10d, 1
0x1c00d37af  test    r10b, al
0x1c00d37b2  jnz     short loc_1C00D37BB
0x1c00d37b4  mov     esi, 0C00000BBh
0x1c00d37b9  jmp     short loc_1C00D3778
0x1c00d37bb  xor     r9d, r9d
0x1c00d37be  test    r8b, al
0x1c00d37c1  jnz     short loc_1C00D37D0
0x1c00d37c3  mov     esi, 0C00000BBh
0x1c00d37c8  mov     bl, dil
0x1c00d37cb  jmp     loc_1C00D39E7
0x1c00d37d0  cmp     [r11+0BD8h], r9
0x1c00d37d7  jz      loc_1C00D678B
0x1c00d37dd  test    dword ptr [r11+0C2Ch], 2000h
0x1c00d37e8  jnz     loc_1C00D678B
0x1c00d37ee  mov     byte ptr [rsp+810h+var_7E0], r9b; unsigned __int8
0x1c00d37f3  mov     r8, rsi; unsigned __int64
0x1c00d37f6  mov     byte ptr [rsp+810h+var_7E8], r9b; unsigned __int8
0x1c00d37fb  mov     rdx, r13; struct CmsTransactionContext *
0x1c00d37fe  mov     byte ptr [rsp+810h+var_7F0], r9b; struct _SmsCheckpointContext *
0x1c00d3803  mov     rcx, r14; this
0x1c00d3806  lea     r9, [rbp+700h+var_778]; struct SmsContainer **
0x1c00d380a  call    ?GetContainerReference@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@_KPEAPEAUSmsContainer@@EEE@Z; CmsVolumeContainer::GetContainerReference(CmsTransactionContext *,unsigned __int64,SmsContainer * *,uchar,uchar,uchar)
0x1c00d380f  xor     r9d, r9d
0x1c00d3812  mov     esi, eax
0x1c00d3814  test    eax, eax
0x1c00d3816  js      loc_1C00D6782
0x1c00d381c  mov     rcx, [r14+8]; this
0x1c00d3820  call    ?IsVolumeOnSmr@CmsVolume@@QEAAEXZ; CmsVolume::IsVolumeOnSmr(void)
0x1c00d3825  test    al, al
0x1c00d3827  jz      short loc_1C00D387B
0x1c00d3829  test    rbx, rbx
0x1c00d382c  jz      short loc_1C00D387B
0x1c00d382e  cmp     [rbx+30h], r9
0x1c00d3832  jz      short loc_1C00D387B
0x1c00d3834  mov     rax, [rbp+700h+var_698]
0x1c00d3838  cmp     [rbx+20h], rax
0x1c00d383c  jz      short loc_1C00D387B
0x1c00d383e  mov     rax, [rbp+700h+var_778]
0x1c00d3842  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1c00d3846  lock add [rax+58h], edx
0x1c00d384a  lea     rcx, [r14+148h]; RemoveLock
0x1c00d3851  xor     edx, edx; Tag
0x1c00d3853  lea     r8d, [r9+20h]; RemlockSize
0x1c00d3857  call    cs:__imp_IoReleaseRemoveLockEx
0x1c00d385e  nop     dword ptr [rax+rax+00h]
0x1c00d3863  dec     dword ptr [r13+0B08h]
0x1c00d386a  xor     r9d, r9d
0x1c00d386d  mov     [rbp+700h+var_778], r9
0x1c00d3871  mov     esi, 0C000022Dh
0x1c00d3876  jmp     loc_1C00D37C8
0x1c00d387b  mov     r15, [rbp+700h+var_778]
0x1c00d387f  mov     r8, r15; struct SmsContainer *
0x1c00d3882  mov     [rbp+700h+var_758], r15
0x1c00d3886  call    ?TryLockContainerExclusive@CmsVolumeContainer@@AEAAEPEAVCmsTransactionContext@@PEAUSmsContainer@@@Z; CmsVolumeContainer::TryLockContainerExclusive(CmsTransactionContext *,SmsContainer *)
0x1c00d388b  xor     r9d, r9d
0x1c00d388e  test    al, al
0x1c00d3890  jnz     short loc_1C00D38C3
0x1c00d3892  or      rax, 0FFFFFFFFFFFFFFFFh
0x1c00d3896  lock add [r15+58h], eax
0x1c00d389b  lea     rcx, [r14+148h]; RemoveLock
0x1c00d38a2  xor     edx, edx; Tag
0x1c00d38a4  lea     r8d, [r9+20h]; RemlockSize
0x1c00d38a8  call    cs:__imp_IoReleaseRemoveLockEx
0x1c00d38af  nop     dword ptr [rax+rax+00h]
0x1c00d38b4  dec     dword ptr [r13+0B08h]
0x1c00d38bb  xor     r9d, r9d
0x1c00d38be  mov     r15d, r9d
0x1c00d38c1  jmp     short loc_1C00D386D
0x1c00d38c3  mov     r10d, 1
0x1c00d38c9  lea     r8, [r15+23Ch]
0x1c00d38d0  mov     edx, [r8]
0x1c00d38d3  mov     edi, r10d
0x1c00d38d6  mov     [rbp+700h+var_728], r10d
0x1c00d38da  mov     [rbp+700h+var_6D0], r8
0x1c00d38de  test    r10b, dl
0x1c00d38e1  jnz     loc_1C00D6765
0x1c00d38e7  bt      edx, 9
0x1c00d38eb  jb      loc_1C00D6765
0x1c00d38f1  test    dl, 40h
0x1c00d38f4  jnz     loc_1C00D6765
0x1c00d38fa  bt      edx, 0Ah
0x1c00d38fe  jb      loc_1C00D6765
0x1c00d3904  cmp     [r15+54h], r9d
0x1c00d3908  jg      loc_1C00D6765
0x1c00d390e  cmp     [r15+250h], r9
0x1c00d3915  jnz     loc_1C00D6765
0x1c00d391b  mov     rax, [r15+248h]
0x1c00d3922  test    rax, rax
0x1c00d3925  jz      loc_1C00D6765
0x1c00d392b  cmp     rax, [r15+240h]
0x1c00d3932  jnz     short loc_1C00D3946
0x1c00d3934  test    r12d, r12d
0x1c00d3937  jnz     short loc_1C00D3946
0x1c00d3939  cmp     [r15+258h], r9d
0x1c00d3940  jz      loc_1C00D6765
0x1c00d3946  test    dl, dl
0x1c00d3948  js      loc_1C00D6765
0x1c00d394e  lea     r9, [r15+18h]
0x1c00d3952  mov     al, [r9]
0x1c00d3955  mov     [rbp+700h+var_660], r9
0x1c00d395c  test    al, 4
0x1c00d395e  jnz     loc_1C00D6762
0x1c00d3964  xor     r12d, r12d
0x1c00d3967  cmp     [r15+60h], r12d
0x1c00d396b  jnz     loc_1C00D6762
0x1c00d3971  mov     rcx, [r14+8]; this
0x1c00d3975  test    al, 40h
0x1c00d3977  jnz     short loc_1C00D3986
0x1c00d3979  call    ?IsVolumeOnSmr@CmsVolume@@QEAAEXZ; CmsVolume::IsVolumeOnSmr(void)
0x1c00d397e  test    al, al
0x1c00d3980  jnz     loc_1C00D6762
0x1c00d3986  mov     rsi, rcx
0x1c00d3989  test    dl, 8
0x1c00d398c  jnz     loc_1C00D6762
0x1c00d3992  mov     rbx, rcx
0x1c00d3995  call    ?IsVolumeOnSmr@CmsVolume@@QEAAEXZ; CmsVolume::IsVolumeOnSmr(void)
0x1c00d399a  test    al, al
0x1c00d399c  jnz     loc_1C00D3C31
0x1c00d39a2  mov     eax, [r14+0E8h]
0x1c00d39a9  lea     r8, [r15+278h]
0x1c00d39b0  imul    eax, [r14+0E4h]
0x1c00d39b8  mov     rdx, r13
0x1c00d39bb  add     r8, rax
0x1c00d39be  call    ?GetStorageTierForRange@CmsVolume@@QEAA?AW4_EMS_STORAGE_TIER_MEDIA_TYPE@@PEAVCmsTransactionCore@@PEBU_RANGE@@@Z; CmsVolume::GetStorageTierForRange(CmsTransactionCore *,_RANGE const *)
0x1c00d39c3  cmp     eax, [rbx+0D9Ch]
0x1c00d39c9  jz      loc_1C00D3C20
0x1c00d39cf  mov     rax, cs:KdDebuggerEnabled
0x1c00d39d6  xor     r9d, r9d
0x1c00d39d9  cmp     [rax], r9b
0x1c00d39dc  jz      short loc_1C00D39DF
0x1c00d39de  int     3; Trap to Debugger
0x1c00d39df  mov     esi, 0C000022Dh
0x1c00d39e4  mov     bl, r9b
0x1c00d39e7  mov     ecx, [rbp+700h+var_6E4]
0x1c00d39ea  test    ecx, ecx
0x1c00d39ec  jz      short loc_1C00D3A04
0x1c00d39ee  mov     rax, [r14+8]
0x1c00d39f2  neg     ecx
0x1c00d39f4  lock xadd [rax+0B50h], ecx
0x1c00d39fc  mov     r15, [rbp+700h+var_778]
0x1c00d3a00  mov     [rbp+700h+var_6E4], r9d
0x1c00d3a04  mov     rcx, [r14+8]; this
  ... truncated ...
```
