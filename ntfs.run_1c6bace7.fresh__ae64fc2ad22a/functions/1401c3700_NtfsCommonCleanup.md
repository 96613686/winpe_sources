# NtfsCommonCleanup

- ea: `0x1401c3700`
- end: `0x1401c9a35`
- name: `NtfsCommonCleanup`
- size: `25397`
- prototype: `__int64 __fastcall(int)`
- caller_count: `3`
- callee_count: `95`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140015d10`
- `0x1401c30e0`
- `0x1401c3320`

## callees

- `0x140007ea0`
- `0x1400082b0`
- `0x14000c290`
- `0x14000c450`
- `0x14000cb00`
- `0x14000d1e0`
- `0x14000d510`
- `0x14000ea70`
- `0x14000eaa0`
- `0x140012e70`
- `0x14001c8c0`
- `0x14001c910`
- `0x14001ca10`
- `0x14001e810`
- `0x140020524`
- `0x14002066c`
- `0x140020de0`
- `0x1400210e0`
- `0x14002b320`
- `0x14002f4c4`
- `0x140030a80`
- `0x1400331f8`
- `0x140033620`
- `0x140034560`
- `0x14003ba34`
- `0x14003c454`
- `0x14003c804`
- `0x1400410a8`
- `0x14004173c`
- `0x140059250`
- `0x140059370`
- `0x1400596c0`
- `0x1400c6844`
- `0x1400f8ee0`
- `0x1401250b0`
- `0x1401261d0`
- `0x140129fb0`
- `0x14012ba70`
- `0x14012baf8`
- `0x14012d150`
- `0x14012f39c`
- `0x14012f930`
- `0x140130550`
- `0x1401321c0`
- `0x140138c20`
- `0x14013c2d0`
- `0x140140380`
- `0x1401413b0`
- `0x1401419ec`
- `0x140141e40`

## import_xrefs

- `ntoskrnl!FsRtlCheckOplock` at `0x1401c47d6`
- `ntoskrnl!FsRtlCheckOplock` at `0x1401c49a1`
- `ntoskrnl!FsRtlCheckOplock` at `0x1401c47d6`
- `ntoskrnl!FsRtlCheckOplock` at `0x1401c49a1`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401c68c4`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401c68c4`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401c96c8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1402af8fa`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401c96c8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1402af8fa`
- `ntoskrnl!CcUninitializeCacheMap` at `0x1401c4c72`
- `ntoskrnl!CcUninitializeCacheMap` at `0x1401c4c72`
- `ntoskrnl!KeBugCheckEx` at `0x1401c450d`
- `ntoskrnl!KeBugCheckEx` at `0x1401c450d`
- `ntoskrnl!CcPurgeCacheSection` at `0x1401c93a3`
- `ntoskrnl!CcPurgeCacheSection` at `0x1401c93a3`
- `ntoskrnl!FsRtlAddToTunnelCacheEx` at `0x1401c5004`
- `ntoskrnl!FsRtlAddToTunnelCacheEx` at `0x1401c629c`
- `ntoskrnl!FsRtlAddToTunnelCacheEx` at `0x1401c72c4`
- `ntoskrnl!FsRtlAddToTunnelCacheEx` at `0x1401c5004`
- `ntoskrnl!FsRtlAddToTunnelCacheEx` at `0x1401c629c`
- `ntoskrnl!FsRtlAddToTunnelCacheEx` at `0x1401c72c4`
- `ntoskrnl!MmFlushImageSection` at `0x1401c77fe`
- `ntoskrnl!MmFlushImageSection` at `0x1401c7948`
- `ntoskrnl!MmFlushImageSection` at `0x1401c77fe`
- `ntoskrnl!MmFlushImageSection` at `0x1401c7948`
- `ntoskrnl!FsRtlNotifyFilterChangeDirectoryLite` at `0x1401c78ef`
- `ntoskrnl!FsRtlNotifyFilterChangeDirectoryLite` at `0x1401c78ef`
- `ntoskrnl!FsRtlNotifyCleanup` at `0x1401c7e95`
- `ntoskrnl!FsRtlNotifyCleanup` at `0x1401c7ee9`
- `ntoskrnl!FsRtlNotifyCleanup` at `0x1401c7e95`
- `ntoskrnl!FsRtlNotifyCleanup` at `0x1401c7ee9`
- `ntoskrnl!FsRtlDeleteKeyFromTunnelCache` at `0x1401c5930`
- `ntoskrnl!FsRtlDeleteKeyFromTunnelCache` at `0x1401c5930`
- `ntoskrnl!FsRtlFastUnlockAll` at `0x1401c454e`
- `ntoskrnl!FsRtlFastUnlockAll` at `0x1401c454e`
- `ntoskrnl!IoGetRequestorProcess` at `0x1401c4536`
- `ntoskrnl!IoGetRequestorProcess` at `0x1401c4536`
- `ntoskrnl!FsRtlHeatLogIo` at `0x1401c6615`
- `ntoskrnl!FsRtlHeatLogIo` at `0x1401c6615`
- `ntoskrnl!MmForceSectionClosed` at `0x1401c6078`
- `ntoskrnl!MmForceSectionClosed` at `0x1401c93d1`
- `ntoskrnl!MmForceSectionClosed` at `0x1401c6078`
- `ntoskrnl!MmForceSectionClosed` at `0x1401c93d1`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1401c99bf`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1402afa9d`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1401c99bf`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1402afa9d`
- `ntoskrnl!IoRaiseInformationalHardError` at `0x1402cba49`
- `ntoskrnl!IoRaiseInformationalHardError` at `0x1402cba49`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x1401c46ba`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x1401c46ba`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1401c96f7`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1402af927`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1401c96f7`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1402af927`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401c54cd`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401c54cd`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401c9722`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401c992c`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402af94f`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402af9f7`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401c9722`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401c992c`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402af94f`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402af9f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401c99d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402afabf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401c99d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402afabf`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c6b6f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c6d69`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c712c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c761a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c7a78`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c7a95`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c901e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c90e3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c9304`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c9423`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c6b6f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c6d69`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c712c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c761a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c7a78`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c7a95`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c901e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c90e3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c9304`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c9423`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c6c4a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c6f90`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c715e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c7720`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c7afe`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c7b19`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c906e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c9124`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c926b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c936f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c93f5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c946c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c990a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402af49d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402af4c1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402af9d4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c6c4a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c6f90`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c715e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c7720`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c7afe`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c7b19`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c906e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c9124`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c926b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c936f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c93f5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c946c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c990a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402af49d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402af4c1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402af9d4`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1401c3cc7`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1401c3e59`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1401c42f8`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1401c3cc7`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1401c3e59`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1401c42f8`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402cba20`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402cba20`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402cba62`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402cba62`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1401c8a8e`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1401c8dda`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1401c8a8e`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1401c8dda`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401c922e`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401c922e`

## string_xrefs

- `0x1401c671f`: `NtfsCommonCleanup`

## pseudocode

```c
__int64 __fastcall NtfsCommonCleanup(__int64 a1, IRP *a2)
{
  __int64 v3; // rsi
  __int64 PostIrpRoutine; // rbx
  struct _FILE_OBJECT *FileObject; // r15
  __int64 v6; // r8
  __int64 v7; // r13
  PSECTION_OBJECT_POINTERS SectionObjectPointer; // rdx
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r12
  __int64 v12; // rdi
  unsigned int v13; // ecx
  __int64 v14; // rdx
  __int64 v15; // rax
  int v16; // r9d
  char *v17; // rcx
  ULONG *p_Flags; // rdi
  __int64 v19; // r14
  __int64 v20; // rax
  __int64 v21; // rcx
  int v22; // ecx
  __int64 v23; // rax
  __int64 v24; // r8
  __int64 v25; // rdx
  int v26; // eax
  __int64 v27; // rdx
  int v28; // eax
  char v29; // al
  __int64 v30; // r8
  __int64 v31; // r8
  int v32; // r9d
  int v33; // eax
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // rax
  __int64 v37; // rax
  char *v38; // rcx
  _BYTE *v39; // rcx
  __int64 v40; // rdx
  int v41; // eax
  __int64 v42; // r9
  __int64 v43; // rcx
  __int64 v44; // rdx
  int v45; // eax
  unsigned int v46; // eax
  int v47; // edi
  __int64 v48; // rdx
  __int64 v49; // rcx
  int v50; // eax
  int v51; // r10d
  __int64 v52; // rcx
  __int64 v53; // r8
  __int64 v54; // r9
  FILE_LOCK *v55; // rdi
  struct _KPROCESS *RequestorProcess; // rax
  int v57; // edx
  __int64 v58; // rcx
  int v59; // eax
  BOOLEAN IsFastIoPossible; // al
  __int64 v61; // rax
  __int64 v62; // rcx
  char v63; // dl
  __int64 v64; // rcx
  int v65; // eax
  __int64 v66; // rdi
  __int64 v67; // rcx
  char updated; // al
  char v69; // cl
  int v70; // ecx
  int v71; // r8d
  int v72; // eax
  int v73; // r8d
  __int64 v74; // rcx
  __int64 v75; // r8
  char v76; // al
  int v77; // eax
  __int64 v78; // rdi
  int v79; // ecx
  __int64 v80; // r8
  __int64 v81; // rdx
  char v82; // al
  __int64 v83; // r8
  __int64 v84; // rdx
  _QWORD *ActivityIdThread; // rax
  PIRP v86; // rax
  __int64 v87; // rax
  __int64 v88; // r13
  __int64 v89; // rdx
  int v90; // eax
  __int64 v91; // r8
  int v92; // r8d
  __int64 v93; // rdi
  int v94; // ecx
  __int64 v95; // r8
  __int64 v96; // rdx
  char v97; // al
  int v98; // eax
  char v99; // al
  __int64 v100; // r8
  __int64 v101; // rcx
  int v102; // eax
  __int64 v103; // rcx
  __int64 v104; // rcx
  int v105; // eax
  __int64 v106; // rax
  SECTION_OBJECT_POINTERS *v107; // rcx
  int v108; // edx
  __int64 v109; // rcx
  int v110; // eax
  __int64 v111; // r8
  __int64 v112; // rdi
  __int64 v113; // r8
  unsigned int v114; // ecx
  __int64 v115; // rdx
  __int64 v116; // rax
  int v117; // r8d
  int v118; // r9d
  __int64 v119; // rdx
  __int64 v120; // rdx
  int v121; // r12d
  __int64 v122; // r8
  int ActivityIdIrp; // eax
  char *v124; // rcx
  unsigned int v125; // r12d
  __int64 NextChildScb; // rax
  __int64 v127; // rcx
  int v128; // r8d
  __int64 v129; // rax
  __int64 v130; // r12
  int v131; // ecx
  __int64 v132; // r8
  __int64 Scb; // rdx
  char *v134; // rcx
  char *v135; // rcx
  char v136; // dl
  __int64 v137; // rax
  unsigned int v138; // ecx
  int v139; // r12d
  __int64 v140; // r10
  __int64 v141; // rcx
  __int64 *v142; // rax
  __int64 v143; // rdi
  int v144; // eax
  int v145; // eax
  int v146; // r8d
  __int64 v147; // rcx
  __int64 v148; // rax
  char v149; // di
  __int64 v150; // rdi
  __int64 v151; // rdx
  int v152; // eax
  __int64 MatchingLcbPair; // rax
  char *v154; // rcx
  __int64 v155; // rax
  __int64 v156; // rdi
  __int64 v157; // rcx
  char *v158; // rcx
  __int64 v159; // rdi
  __int64 v160; // rcx
  __int64 v161; // rax
  __int64 v162; // rax
  __int64 v163; // rax
  __int64 NextParentLcb; // rax
  _QWORD *i; // rcx
  __int64 v166; // rax
  __int16 v167; // di
  __int64 v168; // rdx
  char j; // al
  _DWORD *v170; // rax
  int v171; // r8d
  int v172; // r8d
  __int64 v173; // rcx
  int v174; // r8d
  __int64 v175; // rdx
  int v176; // r8d
  signed __int64 v177; // r10
  signed __int64 v178; // r9
  __int64 v179; // rcx
  int v180; // edx
  __int64 v181; // r8
  __int64 v182; // r8
  char v183; // di
  char v184; // al
  __int64 v185; // r8
  __int64 v186; // rax
  __int64 v187; // rcx
  int v188; // edx
  __int64 v189; // rax
  __int64 v190; // rcx
  __int64 v191; // rdx
  __int64 v192; // rdx
  __int64 v193; // rax
  __int64 v195; // rcx
  __int64 v196; // rax
  _QWORD *v197; // rax
  char v198; // di
  __int64 v199; // r14
  __int64 v200; // rdi
  __int64 v201; // r8
  __int64 v202; // r9
  __int64 v203; // r8
  int v204; // eax
  POPLOCK_WAIT_COMPLETE_ROUTINE CompletionRoutine; // [rsp+20h] [rbp-328h]
  POPLOCK_WAIT_COMPLETE_ROUTINE CompletionRoutinea; // [rsp+20h] [rbp-328h]
  int v207; // [rsp+30h] [rbp-318h]
  int v208; // [rsp+30h] [rbp-318h]
  size_t Size; // [rsp+38h] [rbp-310h]
  int v210; // [rsp+70h] [rbp-2D8h]
  char v211; // [rsp+70h] [rbp-2D8h]
  char v212; // [rsp+70h] [rbp-2D8h]
  char v213; // [rsp+70h] [rbp-2D8h]
  char v214; // [rsp+73h] [rbp-2D5h]
  int v215[2]; // [rsp+78h] [rbp-2D0h] BYREF
  char v216[8]; // [rsp+80h] [rbp-2C8h] BYREF
  __int64 v217; // [rsp+88h] [rbp-2C0h] BYREF
  unsigned int v218; // [rsp+90h] [rbp-2B8h]
  __int64 v219; // [rsp+98h] [rbp-2B0h] BYREF
  PVOID FsContext; // [rsp+A0h] [rbp-2A8h] BYREF
  __int64 v221; // [rsp+A8h] [rbp-2A0h]
  __int64 v222; // [rsp+B0h] [rbp-298h] BYREF
  char v223; // [rsp+B8h] [rbp-290h]
  __int64 v224; // [rsp+C0h] [rbp-288h]
  char v225; // [rsp+C8h] [rbp-280h]
  struct _FILE_OBJECT *v226; // [rsp+D0h] [rbp-278h]
  char v227; // [rsp+D8h] [rbp-270h]
  char v228; // [rsp+D9h] [rbp-26Fh]
  PIRP Irp; // [rsp+E0h] [rbp-268h]
  unsigned int v230; // [rsp+E8h] [rbp-260h]
  __int64 v231; // [rsp+F0h] [rbp-258h] BYREF
  __int64 v232; // [rsp+F8h] [rbp-250h]
  char v233; // [rsp+100h] [rbp-248h]
  char v234; // [rsp+101h] [rbp-247h]
  char v235; // [rsp+102h] [rbp-246h]
  char v236; // [rsp+103h] [rbp-245h]
  __int64 Fcb; // [rsp+108h] [rbp-240h]
  _QWORD *v238; // [rsp+110h] [rbp-238h]
  int v239; // [rsp+118h] [rbp-230h]
  int v240; // [rsp+11Ch] [rbp-22Ch]
  unsigned int v241; // [rsp+120h] [rbp-228h]
  __int64 Lcb; // [rsp+128h] [rbp-220h]
  __int64 v243; // [rsp+130h] [rbp-218h]
  PLARGE_INTEGER TruncateSize; // [rsp+138h] [rbp-210h]
  int v245; // [rsp+140h] [rbp-208h]
  int v246; // [rsp+144h] [rbp-204h]
  int v247; // [rsp+148h] [rbp-200h]
  unsigned int v248; // [rsp+14Ch] [rbp-1FCh]
  unsigned int v249; // [rsp+150h] [rbp-1F8h]
  __int64 v250; // [rsp+158h] [rbp-1F0h]
  __int64 v251; // [rsp+160h] [rbp-1E8h]
  __int128 v252; // [rsp+168h] [rbp-1E0h] BYREF
  int v253; // [rsp+178h] [rbp-1D0h]
  unsigned int v254; // [rsp+17Ch] [rbp-1CCh]
  __int64 v255; // [rsp+180h] [rbp-1C8h]
  __int128 v256; // [rsp+188h] [rbp-1C0h] BYREF
  __int64 v257[12]; // [rsp+1A0h] [rbp-1A8h] BYREF
  __int64 v258; // [rsp+200h] [rbp-148h] BYREF
  __int64 v259; // [rsp+208h] [rbp-140h] BYREF
  __int128 v260; // [rsp+210h] [rbp-138h] BYREF
  IRP *v261; // [rsp+220h] [rbp-128h]
  __int64 v262[24]; // [rsp+230h] [rbp-118h] BYREF
  __int128 v263; // [rsp+2F0h] [rbp-58h] BYREF
  __int64 v264; // [rsp+300h] [rbp-48h]
  __int128 v265; // [rsp+308h] [rbp-40h] BYREF

  v3 = a1;
  v221 = a1;
  Irp = a2;
  PostIrpRoutine = 0;
  v218 = 0;
  v240 = 0;
  v219 = 0;
  *(_QWORD *)v215 = 0;
  v217 = 0;
  FsContext = 0;
  v231 = 0;
  v222 = 0;
  memset(v257, 0, 0x58u);
  v259 = 0;
  v216[0] = 0;
  memset(v262, 0, sizeof(v262));
  v210 = 12;
  a2->IoStatus.Information = 2;
  v262[1] = (__int64)&v262[4];
  v262[3] = (__int64)&v262[7];
  LODWORD(v262[0]) = 1572864;
  LODWORD(v262[2]) = 3407872;
  FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  v226 = FileObject;
  v230 = NtfsDecodeFileObject(
           v3,
           (_DWORD)FileObject,
           (unsigned int)&v219,
           (unsigned int)v215,
           (__int64)&v217,
           (__int64)&FsContext,
           0);
  if ( ((v230 - 1) & 0xFFFFFFFB) == 0 )
  {
    FileObject->Flags |= 0x4000u;
    NtfsCompleteCleanupRequest(v3, Irp, v218);
    return v218;
  }
  v261 = a2;
  Fcb = 0;
  v232 = 0;
  v7 = 0;
  v251 = 0;
  Lcb = 0;
  v243 = 0;
  v238 = 0;
  TruncateSize = 0;
  SectionObjectPointer = FileObject->SectionObjectPointer;
  if ( SectionObjectPointer != (PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v217 + 288) + 16LL)
    && *(_DWORD *)(v217 + 256) == 128
    && (SectionObjectPointer[1].ImageSectionObject
     || (v196 = *(_QWORD *)(v217 + 528)) != 0
     && (v197 = *(_QWORD **)(v196 + 112)) != 0
     && SectionObjectPointer == (PSECTION_OBJECT_POINTERS)(*v197 + 16LL)) )
  {
    BYTE2(v210) = 64;
  }
  BYTE1(v210) = 4 * (*((_BYTE *)FsContext + 4) & 8);
  *(_DWORD *)(v3 + 272) = *((_DWORD *)FsContext + 25);
  if ( *((_QWORD *)FsContext + 10) || (dword_1400956B8 & 0x10000000) != 0 )
  {
    LOBYTE(v210) = 8;
    if ( *((_QWORD *)FsContext + 10) )
      LOBYTE(v210) = 0;
  }
  v9 = v219;
  if ( v230 != 4 )
  {
    if ( (*(_DWORD *)(v3 + 12) & 0x100) != 0 )
    {
      LOBYTE(v6) = 1;
      NtfsAcquireExclusiveVcb(v3, v219, v6);
      goto LABEL_8;
    }
LABEL_7:
    LOBYTE(v6) = 1;
    NtfsAcquireSharedVcb(v3, v219, v6);
LABEL_8:
    LODWORD(v11) = 512;
    goto LABEL_9;
  }
  if ( (*(_DWORD *)(v219 + 4) & 2) == 0
    || (struct _FILE_OBJECT *)(*(_QWORD *)(v219 + 1472) & 0xFFFFFFFFFFFFFFFEuLL) != FileObject )
  {
    goto LABEL_7;
  }
  LODWORD(v11) = 512;
  if ( (*(_DWORD *)(v3 + 12) & 0x200) != 0 )
  {
    NtfsAcquireCheckpointSynchronization(v3, v219, 82);
    LOBYTE(v210) = v210 | 1;
    v9 = v219;
  }
  LOBYTE(v6) = 1;
  NtfsAcquireExclusiveVcb(v3, v9, v6);
LABEL_9:
  if ( (*(_DWORD *)(v219 + 4) & 0x8000823) == 1 && (*(_DWORD *)(*(_QWORD *)v215 + 4LL) & 0x80u) == 0 )
    BYTE2(v210) |= 8u;
  if ( (*(_DWORD *)(v219 + 4) & 0x2000020) != 0 || (*(_DWORD *)(*(_QWORD *)v215 + 4LL) & 0x8000000) != 0 )
    BYTE2(v210) |= 0x10u;
  if ( (*(_DWORD *)(v219 + 4) & 0x4000000) != 0 )
    BYTE1(v210) |= 8u;
  v12 = *(_QWORD *)v215;
  if ( *(_QWORD *)(*(_QWORD *)v215 + 112LL) )
  {
    LOBYTE(v10) = 1;
    if ( (unsigned __int8)NtfsAcquirePagingResourceExclusive(v3, *(_QWORD *)v215, v10) )
    {
      v13 = 0;
      v249 = 0;
      while ( v13 < 2 )
      {
        v14 = v3 + 8LL * v13;
        v15 = *(_QWORD *)(v14 + 48);
        if ( !v15 || v15 == v12 )
        {
          *(_QWORD *)(v14 + 48) = v12;
          break;
        }
        v249 = ++v13;
      }
    }
LABEL_20:
    NtfsAcquireExclusiveFcb(v3, *(_QWORD *)(v217 + 184), v217, 8);
    goto LABEL_21;
  }
  NtfsAcquireExclusiveFcb(v3, *(_QWORD *)(v217 + 184), v217, 8);
  if ( *(_QWORD *)(*(_QWORD *)v215 + 112LL) )
  {
    NtfsReleaseFcbEx(v3, *(_QWORD *)(v217 + 184), 0);
    v112 = *(_QWORD *)v215;
    LOBYTE(v113) = 1;
    if ( (unsigned __int8)NtfsAcquirePagingResourceExclusive(v3, *(_QWORD *)v215, v113) )
    {
      v114 = 0;
      v248 = 0;
      while ( v114 < 2 )
      {
        v115 = v3 + 8LL * v114;
        v116 = *(_QWORD *)(v115 + 48);
        if ( !v116 || v116 == v112 )
        {
          *(_QWORD *)(v115 + 48) = v112;
          goto LABEL_20;
        }
        v248 = ++v114;
      }
    }
    goto LABEL_20;
  }
LABEL_21:
  v17 = (char *)FsContext + 8;
  if ( (*((_DWORD *)FsContext + 2) & 0x100) == 0 )
    goto LABEL_22;
  while ( 1 )
  {
    ClearFlagInterlocked(v17, 256);
    --*(_DWORD *)(v217 + 448);
LABEL_22:
    if ( (*((_DWORD *)FsContext + 2) & 0x8000) != 0 )
    {
      --*(_DWORD *)(v217 + 544);
      ClearFlagInterlocked((char *)FsContext + 8, 0x8000);
    }
    p_Flags = &FileObject->Flags;
    *(_QWORD *)&v256 = &FileObject->Flags;
    if ( (FileObject->Flags & 0x800000) != 0 )
      NtfsBypassIoDisableCore(v3, FileObject);
    v19 = *((_QWORD *)FsContext + 9);
    v224 = v19;
    v250 = v19;
    v231 = v19;
    if ( v19 )
    {
      if ( (*(_DWORD *)(v19 + 4) & 2) != 0 )
      {
        v19 = PostIrpRoutine;
        v224 = PostIrpRoutine;
        v231 = PostIrpRoutine;
        ClearFlagInterlocked((char *)FsContext + 4, 0x40000);
      }
      else
      {
        v20 = *(_QWORD *)(v19 + 24);
        v222 = v20;
        if ( v20 )
          Fcb = *(_QWORD *)(v20 + 184);
      }
    }
    if ( (*((_DWORD *)FsContext + 1) & 0x100) != 0 && v230 == 2 )
      TxfUnmarkObjectAsClfsLog(v217);
    if ( ((unsigned int)v11 & *((_DWORD *)FsContext + 2)) != 0 )
    {
      v125 = PostIrpRoutine;
      v253 = PostIrpRoutine;
      v247 = PostIrpRoutine;
      v241 = PostIrpRoutine;
      v246 = PostIrpRoutine;
      *(_QWORD *)&v252 = PostIrpRoutine;
      *(_DWORD *)(*(_QWORD *)v215 + 4LL) &= ~0x40000000u;
      ClearFlagInterlocked((char *)FsContext + 8, 512);
      _InterlockedDecrement((volatile signed __int32 *)(v219 + 276));
      while ( 1 )
      {
        NextChildScb = NtfsGetNextChildScb(*(_QWORD *)v215, v252, 1);
        *(_QWORD *)&v252 = NextChildScb;
        if ( !NextChildScb )
          break;
        v117 = PostIrpRoutine;
        v247 = PostIrpRoutine;
        v118 = PostIrpRoutine;
        v246 = PostIrpRoutine;
        v119 = *(_QWORD *)(NextChildScb + 480);
        if ( v119 == NextChildScb + 480 )
          v120 = PostIrpRoutine;
        else
          v120 = v119 - 40;
        while ( v120 )
        {
          if ( (*(_DWORD *)(v120 + 8) & 4) == 0 )
            v247 = --v117;
          if ( (*(_DWORD *)(v120 + 4) & 0x80000) == 0 && !*(_WORD *)(*(_QWORD *)(v120 + 112) + 75LL) )
            v246 = ++v118;
          v127 = *(_QWORD *)(v120 + 40);
          v120 = PostIrpRoutine;
          if ( NextChildScb + 480 != v127 )
            v120 = v127 - 40;
        }
        v125 += v117;
        v253 = v125;
        v241 += v118;
      }
      _InterlockedAdd((volatile signed __int32 *)(v219 + 268), v125);
      _InterlockedAdd((volatile signed __int32 *)(v219 + 264), v241);
    }
    if ( (v210 & 0x80000) == 0 )
      goto LABEL_46;
    v21 = *((_QWORD *)FsContext + 10);
    if ( v21 && (*(_DWORD *)(v21 + 4) & 2) == 0 )
    {
      v128 = PostIrpRoutine;
      LOBYTE(v128) = *(_DWORD *)(v21 + 36) == (_DWORD)PostIrpRoutine;
      LOBYTE(v16) = 1;
      v218 = TxfSetupTransactionContextFromCcb(v3, (_DWORD)FileObject, v128, v16, PostIrpRoutine);
      if ( (v218 & 0x80000000) != 0 )
      {
        v231 = PostIrpRoutine;
        HIBYTE(v210) |= 0x20u;
        ClearFlagInterlocked((char *)FsContext + 4, 0x40000);
        if ( !*(_DWORD *)(*((_QWORD *)FsContext + 10) + 36LL) )
        {
          v150 = *(_QWORD *)(*(_QWORD *)v215 + 328LL);
          ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v150 + 136), 1u);
          v232 = v150;
          v151 = *(_QWORD *)(v150 + 24);
          if ( v151
            && *(_QWORD *)(v151 + 232) == *(_QWORD *)(*((_QWORD *)FsContext + 10) + 56LL)
            && (*(_DWORD *)(v150 + 4) & 0x2000000) == 0 )
          {
            HIBYTE(v210) |= 8u;
            if ( v19 )
            {
              v152 = *(_DWORD *)(v19 + 4);
              if ( (v152 & 2) == 0 )
              {
                if ( (v152 & 1) != 0
                  || (*(_BYTE *)(*(_QWORD *)(v19 + 192) + 65LL) & 3) != 0
                  && (*(_DWORD *)(*(_QWORD *)(v19 + 48) + 4LL) & 0x20) != 0 )
                {
                  MatchingLcbPair = NtfsFindMatchingLcbPair(v19, 0);
                  ++*(_WORD *)(*(_QWORD *)v215 + 188LL);
                  ++*(_DWORD *)(v150 + 20);
                  if ( MatchingLcbPair )
                    ClearFlagInterlocked(MatchingLcbPair + 4, 1);
                  ClearFlagInterlocked(v19 + 4, 1);
                  if ( (*(_BYTE *)(*(_QWORD *)(v19 + 192) + 65LL) & 3) != 0 )
                    *(_DWORD *)(*(_QWORD *)v215 + 4LL) &= ~0x20u;
                }
                if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)v215 + 328LL) + 4LL) & 0x800) == 0 )
                  HIBYTE(v210) |= 4u;
              }
            }
            v19 = PostIrpRoutine;
            v224 = PostIrpRoutine;
          }
          ExReleaseResourceLite(*(PERESOURCE *)(v150 + 136));
          v232 = PostIrpRoutine;
        }
        v218 = PostIrpRoutine;
        v232 = PostIrpRoutine;
      }
      else if ( !*(_DWORD *)(*((_QWORD *)FsContext + 10) + 36LL) )
      {
        HIBYTE(v210) |= 2u;
        ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v215 + 328LL) + 136LL), 1u);
        v129 = *(_QWORD *)(*(_QWORD *)v215 + 328LL);
        v232 = v129;
        if ( v250 )
        {
          if ( (*(_DWORD *)(v250 + 4) & 2) != 0 )
          {
            Lcb = v250;
            HIBYTE(v210) |= 1u;
          }
          else
          {
            Lcb = v19;
            v214 = HIBYTE(v210) | 1;
            if ( (*((_DWORD *)FsContext + 1) & 0x40002) == 0x40002 )
            {
              v233 = 0;
              v236 = 0;
              if ( (*(_DWORD *)(v19 + 4) & 1) != 0
                || (*(_BYTE *)(*(_QWORD *)(v19 + 192) + 65LL) & 3) != 0
                && (*(_DWORD *)(*(_QWORD *)(v19 + 48) + 4LL) & 0x20) != 0 )
              {
                v135 = (char *)FsContext + 8;
                if ( (*((_DWORD *)FsContext + 2) & 0x20000) != 0 )
                  SetFlagInterlocked(v135, 0x10000);
                else
                  ClearFlagInterlocked(v135, 0x10000);
              }
              else if ( (*(_DWORD *)(*(_QWORD *)v215 + 176LL) & 0x10000000) == 0
                     || (unsigned __int8)NtfsIsLinkDeleteable(v3, v215[0]) )
              {
                --*(_WORD *)(*(_QWORD *)v215 + 188LL);
                SetFlagInterlocked(v19 + 4, 1);
                v134 = (char *)FsContext + 8;
                if ( (*((_DWORD *)FsContext + 2) & 0x20000) != 0 )
                  SetFlagInterlocked(v134, 0x10000);
                else
                  ClearFlagInterlocked(v134, 0x10000);
                BYTE2(v210) |= 0x20u;
                --*(_DWORD *)(*(_QWORD *)(*(_QWORD *)v215 + 328LL) + 20LL);
                if ( (*(_BYTE *)(*(_QWORD *)(v19 + 192) + 65LL) & 3) != 0 )
                  *(_DWORD *)(*(_QWORD *)v215 + 4LL) |= 0x20u;
              }
            }
            v136 = v214 | 0x10;
            HIBYTE(v210) = v214 | 0x10;
            if ( (*(_DWORD *)(v19 + 4) & 1) == 0
              && ((*(_BYTE *)(*(_QWORD *)(v19 + 192) + 65LL) & 3) == 0
               || (*(_DWORD *)(*(_QWORD *)(v19 + 48) + 4LL) & 0x20) == 0) )
            {
              goto LABEL_597;
            }
            v137 = NtfsFindMatchingLcbPair(v19, 0);
            v138 = *(_DWORD *)(v19 + 32);
            v254 = v138;
            if ( v137 )
            {
              v138 += *(_DWORD *)(v137 + 32);
              v254 = v138;
            }
            v136 = HIBYTE(v210);
            if ( v138 > 1 )
            {
LABEL_597:
              v136 &= ~0x10u;
              HIBYTE(v210) = v136;
            }
            if ( (v136 & 0x10) != 0
              && *(_WORD *)(*(_QWORD *)v215 + 190LL) == 1
              && *(_WORD *)(*(_QWORD *)(*(_QWORD *)v215 + 328LL) + 144LL) > 1u )
            {
              HIBYTE(v210) = v136 & 0xEF;
              *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v215 + 328LL) + 4LL) |= 0x800u;
            }
          }
        }
        else if ( *(_WORD *)(v129 + 144) == 1 && (*(_DWORD *)(v129 + 4) & 0x800) != 0 )
        {
          v252 = 0;
          HIBYTE(v210) |= 0x10u;
          memset(v257, 0, 0x58u);
          LOBYTE(v210) = v210 | 0x10;
          LOBYTE(v207) = 0;
          if ( !(unsigned __int8)NtfsLookupInFileRecord(
                                   v3,
                                   *(_QWORD *)v215,
                                   *(_QWORD *)v215 + 8LL,
                                   48,
                                   PostIrpRoutine,
                                   PostIrpRoutine,
                                   v207,
                                   PostIrpRoutine,
                                   PostIrpRoutine,
                                   v257) )
          {
            NtfsAttachCorruption_BadOrOrphanFRS(v3, 2, 460131, 0, *(_QWORD *)v215 + 8LL, *(__int64 *)v215, 0);
            NtfsAttachRepairInfoPriv(v3, 256, 0, 0xFB00070563LL);
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(v3, 3221225730LL, 460131);
            NtfsRaiseStatusInternal(v3, -1073741566, v215[0] + 8, v215[0], 460131);
LABEL_517:
            v121 = -1072037844;
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(0, 3222929452LL, 460523);
            v218 = -1072037844;
LABEL_520:
            TxfRaiseAndAbortAtTopLevelPriv(
              v3,
              v255,
              0,
              0,
              0,
              v121,
              (__int64)"NtfsCommonCleanup",
              (__int64)"Cleanup.c",
              1786);
          }
          v130 = v257[0] + *(unsigned __int16 *)(v257[0] + 20);
          ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v215 + 328LL) + 136LL));
          v232 = PostIrpRoutine;
          v131 = *(_DWORD *)(*(_QWORD *)v215 + 8LL);
          if ( v131 == 5 || (v132 = *(_QWORD *)(*(_QWORD *)v215 + 320LL), *(_DWORD *)(v132 + 88) == v131) )
            v132 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v215 + 96LL) + 6248LL);
          Fcb = NtfsCreateFcb(v3, v219, v132, *(_QWORD *)v130, 66, PostIrpRoutine);
          Scb = NtfsCreateScb(v3, Fcb, 160, (unsigned int)&NtfsFileNameIndex, 0, PostIrpRoutine, PostIrpRoutine);
          v222 = Scb;
          if ( (*(_DWORD *)(Scb + 200) & 0x200) != 0 )
          {
            NtfsSnapshotScb(v3, Scb);
            LODWORD(Scb) = v222;
          }
          *((_QWORD *)&v252 + 1) = v130 + 66;
          LOWORD(v252) = 2 * *(unsigned __int8 *)(v130 + 64);
          WORD1(v252) = v252;
          Lcb = NtfsCreateLcb(v3, Scb, v215[0], (unsigned int)&v252, *(_BYTE *)(v130 + 65), PostIrpRoutine);
          v216[0] = 1;
          ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v215 + 328LL) + 136LL), 1u);
          v232 = *(_QWORD *)(*(_QWORD *)v215 + 328LL);
        }
        ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v215 + 328LL) + 136LL));
        v232 = PostIrpRoutine;
        if ( (v210 & 0x10000000) != 0 )
        {
          v245 = 18;
          v255 = PostIrpRoutine;
          v139 = 18;
          if ( v216[0] )
            v139 = 22;
          v245 = v139;
          if ( (*((_DWORD *)FsContext + 1) & 1) != 0 )
            v245 = v139 | 1;
          LOBYTE(v262[23]) = 0;
          v140 = *(_QWORD *)(v217 + 184);
          if ( *(_WORD *)(v140 + 190) == 1 )
          {
            NtfsPostUsnChangeWithOverrideOption(
              v3,
              v140,
              -2147483136,
              0,
              PostIrpRoutine,
              PostIrpRoutine,
              PostIrpRoutine);
          }
          else
          {
            v141 = PostIrpRoutine;
            if ( (*(_BYTE *)(*(_QWORD *)(Lcb + 192) + 65LL) & 3) != 2 )
              v141 = *(_QWORD *)(Lcb + 192);
            NtfsPostUsnChangeWithOverrideOption(v3, v140, -2147418112, 0, PostIrpRoutine, PostIrpRoutine, v141);
            NtfsUpdateFileTimestampsForChange(*(_QWORD *)(v217 + 184), FsContext, 0);
          }
          if ( *(int *)(v219 + 4) < 0 || (v142 = &v262[14], (*p_Flags & 0x20000) != 0) )
            v142 = (__int64 *)PostIrpRoutine;
          TxfDeleteFile(v3, *(_QWORD *)(v217 + 184), PostIrpRoutine, (__int64)v262, (__int64)v142);
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v215 + 328LL) + 4LL) &= ~0x800u;
          v121 = v218;
          if ( v218 )
          {
            if ( v218 != -1073741608 || (*(_DWORD *)(*(_QWORD *)(v255 + 208) + 136LL) & 0x1000) == 0 )
              goto LABEL_520;
            goto LABEL_517;
          }
          if ( v216[0] || *(_DWORD *)(v3 + 28) )
          {
            NtfsUpdateFcbTimestamps(Fcb, 2684354576LL);
          }
          else
          {
            NtfsAcquireExclusiveScbEx(v3, v222, 0);
            v216[0] = 1;
            NtfsUpdateFcbTimestamps(Fcb, 2684354576LL);
            NtfsReleaseFcbEx(v3, *(_QWORD *)(v222 + 184), 0);
            v216[0] = 0;
          }
          if ( !v218 )
          {
            if ( *(int *)(v219 + 4) >= 0 && (*p_Flags & 0x20000) == 0 )
            {
              v143 = Lcb;
              NtfsGetTunneledData(v3, *(_QWORD *)v215, *(unsigned __int8 *)(*(_QWORD *)(Lcb + 192) + 65LL), &v262[14]);
              if ( FsContext )
                v144 = *((_DWORD *)FsContext + 1);
              else
                v144 = PostIrpRoutine;
              if ( (v144 & 0x4000000) != 0 || (v145 = 1, (*(_DWORD *)(*(_QWORD *)(v222 + 184) + 16LL) & 0x400) == 0) )
                v145 = PostIrpRoutine;
              FsRtlAddToTunnelCacheEx(
                v219 + 4720,
                *(_QWORD *)(*(_QWORD *)(v222 + 184) + 8LL),
                v262,
                &v262[2],
                *(_BYTE *)(*(_QWORD *)(v143 + 192) + 65LL) & 2 | v145,
                80,
                &v262[14]);
            }
            if ( (v210 & 0x2000) == 0 && *(_WORD *)v217 != 1796 )
            {
              v146 = PostIrpRoutine;
              LOBYTE(v146) = *(_WORD *)v217 == 1795;
              NtfsReportDirNotify(
                v3,
                *((_QWORD *)FsContext + 9),
                v219,
                (_DWORD)FsContext + 16,
                *((unsigned __int16 *)FsContext + 16),
                PostIrpRoutine,
                v146 + 1,
                2,
                Fcb,
                PostIrpRoutine);
            }
          }
        }
        if ( (*((_DWORD *)FsContext + 1) & 2) != 0
          && ((*(_DWORD *)(*(_QWORD *)(*(_QWORD *)v215 + 328LL) + 4LL) & 0x800) != 0 || (v210 & 0x10000000) != 0) )
        {
          ClearFlagInterlocked((char *)FsContext + 4, 0x40000);
        }
        else if ( *(_DWORD *)(v217 + 256) == 128 )
        {
          if ( *(_WORD *)(v217 + 264) )
          {
            v147 = *(_QWORD *)(v217 + 528);
            if ( *(_DWORD *)(v147 + 36) == 1 )
            {
              LOBYTE(v122) = 1;
              v148 = TxfCurrentWritableVersion(v147, 0, v122);
              v7 = v148;
              v251 = v148;
              if ( v148 )
              {
                if ( (*(_DWORD *)(v148 + 8) & 4) == 0
                  && (*(_DWORD *)(*(_QWORD *)(v217 + 528) + 24LL) & 1) == 0
                  && ((*(_DWORD *)(v217 + 200) & 2) != 0 || (*((_DWORD *)FsContext + 1) & 0x40000) != 0) )
                {
                  v149 = v210;
                  if ( (v210 & 0x10) != 0 )
                  {
                    NtfsCleanupAttributeContext(v3, v257);
                    v149 = v210;
                  }
                  memset(v257, 0, 0x58u);
                  LOBYTE(v210) = v149 | 0x10;
                  LOBYTE(v207) = 0;
                  if ( !(unsigned __int8)NtfsLookupInFileRecord(
                                           v3,
                                           *(_QWORD *)(v217 + 184),
                                           *(_QWORD *)(v217 + 184) + 8LL,
                                           *(unsigned int *)(v217 + 256),
                                           v217 + 264,
                                           PostIrpRoutine,
                                           v207,
                                           PostIrpRoutine,
                                           PostIrpRoutine,
                                           v257)
                    && (*(_DWORD *)(v217 + 512) & 4) == 0 )
                  {
                    PostIrpRoutine = 0xA9000707AFLL;
                    NtfsAttachCorruption_BadOrOrphanFRS(
                      v3,
                      2,
                      460719,
                      0,
                      *(_QWORD *)(v217 + 184) + 8LL,
                      *(_QWORD *)(v217 + 184),
                      0);
                    NtfsAttachRepairInfoPriv(v3, 512, 0, 0xA9000707AFLL);
                    if ( NtfsStatusDebugFlags )
                      NtfsStatusTraceAndDebugInternal(v3, 3221225730LL, 460719);
                    NtfsRaiseStatusInternal(
                      v3,
                      -1073741566,
                      *(_QWORD *)(v217 + 184) + 8,
                      *(_QWORD *)(v217 + 184),
                      460719);
                  }
                  TxfOverwriteAttribute(v3);
                  BYTE2(v210) |= 0x80u;
                }
              }
            }
          }
        }
        if ( v7 )
          TxfDereferenceTxfVscb((PVOID)v7);
      }
    }
    if ( (v210 & 0x100000) != 0 || !(unsigned __int8)NtfsIsFileStillValid(*(_QWORD *)v215) )
    {
LABEL_46:
      v11 = 1797;
      goto LABEL_47;
    }
    v22 = *((_DWORD *)FsContext + 1);
    if ( (v22 & 0x40000) != 0 )
    {
      if ( (v22 & 2) == 0 )
      {
        v159 = v217;
        v243 = v217;
        _InterlockedIncrement((volatile signed __int32 *)(v217 + 212));
        v212 = v210 | 0x80;
        if ( !(unsigned __int8)TxfCantFlushDefaultReaderImageSection(v159, 0) )
        {
          v160 = *(_QWORD *)(v159 + 288);
          if ( !*(_QWORD *)(v160 + 32) || MmFlushImageSection((PSECTION_OBJECT_POINTERS)(v160 + 16), MmFlushForDelete) )
          {
            SetFlagInterlocked(v217 + 200, 2);
            BYTE2(v210) |= 0x20u;
          }
        }
        _InterlockedDecrement((volatile signed __int32 *)(v159 + 212));
        LOBYTE(v210) = v212 & 0x7F;
        goto LABEL_464;
      }
      v234 = 0;
      v235 = 0;
      if ( (*(_DWORD *)(v19 + 4) & 1) != 0
        || (*(_BYTE *)(*(_QWORD *)(v19 + 192) + 65LL) & 3) != 0
        && (*(_DWORD *)(*(_QWORD *)(v19 + 48) + 4LL) & 0x20) != 0 )
      {
        v154 = (char *)FsContext + 8;
        if ( (*((_DWORD *)FsContext + 2) & 0x20000) != 0 )
          SetFlagInterlocked(v154, 0x10000);
        else
          ClearFlagInterlocked(v154, 0x10000);
        goto LABEL_464;
      }
      v103 = *(_QWORD *)v215;
      if ( (*(_DWORD *)(*(_QWORD *)v215 + 176LL) & 0x10000000) != 0 )
      {
        if ( !(unsigned __int8)NtfsIsLinkDeleteable(v3, v215[0]) )
        {
LABEL_464:
          ClearFlagInterlocked((char *)FsContext + 4, 0x40000);
          goto LABEL_37;
        }
        v103 = *(_QWORD *)v215;
      }
      v243 = PostIrpRoutine;
      while ( 1 )
      {
        v155 = NtfsGetNextChildScb(v103, v243, 0);
        v156 = v155;
        v243 = v155;
        if ( !v155 )
          break;
        _InterlockedIncrement((volatile signed __int32 *)(v155 + 212));
        v211 = v210 | 0x80;
        if ( *(_DWORD *)(v155 + 256) == 128 && (*(_DWORD *)(v155 + 512) & 0x1000040) == 0 )
        {
          if ( (unsigned __int8)TxfCantFlushDefaultReaderImageSection(v155, 0)
            || (v157 = *(_QWORD *)(v156 + 288), *(_QWORD *)(v157 + 32))
            && !MmFlushImageSection((PSECTION_OBJECT_POINTERS)(v157 + 16), MmFlushForDelete) )
          {
            _InterlockedDecrement((volatile signed __int32 *)(v156 + 212));
            LOBYTE(v210) = v211 & 0x7F;
            break;
          }
        }
        _InterlockedDecrement((volatile signed __int32 *)(v156 + 212));
        LOBYTE(v210) = v211 & 0x7F;
        v103 = *(_QWORD *)v215;
      }
      if ( !v243 )
      {
        if ( (*(_BYTE *)(*(_QWORD *)(v19 + 192) + 65LL) & 3) != 0 )
          *(_DWORD *)(*(_QWORD *)v215 + 4LL) |= 0x20u;
        --*(_WORD *)(*(_QWORD *)v215 + 188LL);
        SetFlagInterlocked(v19 + 4, 1);
        v158 = (char *)FsContext + 8;
        if ( (*((_DWORD *)FsContext + 2) & 0x20000) != 0 )
          SetFlagInterlocked(v158, 0x10000);
        else
          ClearFlagInterlocked(v158, 0x10000);
        BYTE2(v210) |= 0x20u;
        if ( (*(_DWORD *)(*(_QWORD *)v215 + 176LL) & 0x10000000) != 0 )
          FsRtlNotifyFilterChangeDirectoryLite(
            v217 + 768,
            v217 + 752,
            0,
            0,
            PostIrpRoutine,
            PostIrpRoutine,
            PostIrpRoutine,
            PostIrpRoutine,
            PostIrpRoutine);
      }
      goto LABEL_464;
    }
LABEL_37:
    v11 = 1797;
    if ( (v210 & 0x200000) != 0 )
    {
      if ( (v45 = *(_DWORD *)(v217 + 256), v45 == 128) && *(_WORD *)v217 == 1797
        || v45 == 160
        && *(_WORD *)(v217 + 264) == 8
        && **(_QWORD **)(v217 + 272) == 0x30003300490024LL
        && (unsigned __int16)(*(_WORD *)v217 - 1795) <= 1u )
      {
        v46 = FsRtlCheckOplockEx(
                (POPLOCK)(v217 + 88),
                Irp,
                0x20u,
                (PVOID)v3,
                NtfsOplockComplete,
                NtfsCleanupOplockPrePostIrp);
        v218 = v46;
        if ( v46 )
        {
          if ( v46 == 259 )
          {
            Irp = (PIRP)PostIrpRoutine;
            v3 = PostIrpRoutine;
            v221 = PostIrpRoutine;
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(0, 871, 461121);
            v44 = 871;
            v218 = 871;
            goto LABEL_958;
          }
          if ( NtfsStatusDebugFlags
            && (((v46 - 294) & 0xFFFFFFFA) != 0 || v46 == 295)
            && v46 < 0xFFFFFFED
            && v46 != -1073741802
            && v46 != -1073741807
            && v46 + 2147483643 > 1
            && v46 != -1073741608 )
          {
            NtfsStatusTraceAndDebugInternal(0, v46, 461130);
          }
        }
      }
    }
    if ( *(_WORD *)(*(_QWORD *)v215 + 188LL) || *(_DWORD *)(*(_QWORD *)v215 + 20LL) != 1 )
    {
      if ( (*(_DWORD *)(v217 + 200) & 2) != 0 )
      {
        v23 = *(_QWORD *)(*(_QWORD *)v215 + 328LL);
        if ( v23 && (*(_DWORD *)(v23 + 4) & 1) != 0 )
        {
          if ( (v210 & 0x10000000) == 0 && (v210 & 0x2000000) != 0 && *(_DWORD *)(*(_QWORD *)(v217 + 528) + 36LL) == 1 )
            BYTE1(v210) |= 4u;
        }
        else if ( *(_DWORD *)(v217 + 208) == 1 && (*(_DWORD *)(v217 + 512) & 0x200000) == 0 )
        {
          BYTE1(v210) |= 4u;
        }
      }
    }
    else
    {
      BYTE1(v210) |= 1u;
    }
LABEL_47:
    switch ( v230 )
    {
      case 2u:
        if ( (*(_DWORD *)(v217 + 200) & 0x20) == 0
          && (v210 & 0x80000) != 0
          && (v210 & 0x100000) == 0
          && (unsigned __int8)NtfsIsFileStillValid(*(_QWORD *)(v217 + 184)) )
        {
          NtfsUpdateScbFromAttribute(v3, v217, 0);
        }
        NtfsClearSfioReservation(v3, (_DWORD)Irp, (_DWORD)FileObject, v219, v217, (__int64)FsContext);
        NtfsSnapshotScb(v3, v217);
        v27 = v217;
        v28 = *(_DWORD *)(v217 + 256);
        if ( v28 == 128 && *(_WORD *)v217 == 1797
          || v28 == 160
          && *(_WORD *)(v217 + 264) == 8
          && **(_QWORD **)(v217 + 272) == 0x30003300490024LL
          && (unsigned __int16)(*(_WORD *)v217 - 1795) <= 1u )
        {
          FsRtlCheckOplock((POPLOCK)(v217 + 88), Irp, 0, 0, (POPLOCK_FS_PREPOST_IRP)PostIrpRoutine);
          v27 = v217;
        }
        if ( *(_WORD *)v27 == 1797 && *(_QWORD *)(v27 + 584) )
        {
          v55 = *(FILE_LOCK **)(v27 + 584);
          RequestorProcess = IoGetRequestorProcess(Irp);
          FsRtlFastUnlockAll(v55, FileObject, RequestorProcess, 0);
          v27 = v217;
        }
        if ( (*(_DWORD *)(*(_QWORD *)(v27 + 192) + 4LL) & 0x4000005) == 1
          && *(_WORD *)v27 == 1797
          && (IsFastIoPossible = FsRtlOplockIsFastIoPossible((POPLOCK)(v27 + 88)), v27 = v217, IsFastIoPossible) )
        {
          if ( *(_DWORD *)(v217 + 452)
            || (v61 = *(_QWORD *)(v217 + 584)) != 0 && *(_BYTE *)(v61 + 16)
            || (v62 = *(_QWORD *)(v217 + 192), (*(_DWORD *)(v62 + 4) & 0x2000000) != 0)
            || (*(_DWORD *)(v217 + 512) & 0x4000000) != 0
            || *(_QWORD *)(v217 + 528)
            || *(_QWORD *)(v62 + 40) )
          {
            v29 = 2;
          }
          else
          {
            v29 = 1;
          }
        }
        else
        {
          v29 = PostIrpRoutine;
        }
        *(_BYTE *)(v27 + 5) = v29;
        if ( (v210 & 0x80000) == 0 || (v210 & 0x100000) != 0 || !(unsigned __int8)NtfsIsFileStillValid(*(_QWORD *)v215) )
        {
          FileObject->Flags |= 0x4000u;
          if ( (v210 & 0x80000) == 0 || !(unsigned __int8)NtfsIsFileStillValid(*(_QWORD *)v215) )
          {
            v11 = (__int64)&NtfsLarge0;
            TruncateSize = &NtfsLarge0;
          }
          goto LABEL_90;
        }
        LOBYTE(v30) = 1;
        NtfsUpdateScbFromFileObject(FileObject, v217, v30);
        FileObject->Flags |= 0x4000u;
        if ( v218 )
          goto LABEL_90;
        if ( !v19
          || ((v32 = *(_DWORD *)(v19 + 4), (v32 & 1) != 0)
           || (*(_BYTE *)(*(_QWORD *)(v19 + 192) + 65LL) & 3) != 0
           && (*(_DWORD *)(*(_QWORD *)(v19 + 48) + 4LL) & 0x20) != 0)
          && *(_DWORD *)(v19 + 188) == 1 )
        {
          if ( (v210 & 0x100) != 0 && (*(_DWORD *)(*(_QWORD *)v215 + 4LL) & 0x8000) != 0 )
          {
            NtfsPostSpecial(v3, v219, (unsigned int)NtfsDeleteUsnSpecial, v219 + 2144, 13);
            BYTE1(v210) &= ~1u;
            ++*(_WORD *)(*(_QWORD *)v215 + 188LL);
            *(_DWORD *)(*(_QWORD *)v215 + 4LL) &= ~0x20u;
            if ( v19 )
            {
              ClearFlagInterlocked(v19 + 4, 1);
            }
            else
            {
              while ( 1 )
              {
                NextParentLcb = NtfsGetNextParentLcb(v3, *(_QWORD *)v215, v19);
                v19 = NextParentLcb;
                v224 = NextParentLcb;
                if ( !NextParentLcb )
                  break;
                ClearFlagInterlocked(NextParentLcb + 4, 1);
              }
            }
            goto LABEL_77;
          }
          if ( (v210 & 0x100) != 0 )
          {
            if ( v19 )
            {
              v238 = (_QWORD *)v19;
            }
            else
            {
              for ( i = *(_QWORD **)(*(_QWORD *)v215 + 48LL); i != (_QWORD *)(*(_QWORD *)v215 + 48LL); i = (_QWORD *)*i )
              {
                v238 = i - 7;
                if ( (*((_DWORD *)i - 13) & 2) == 0 )
                {
                  v75 = *(i - 4);
                  v222 = v75;
                  if ( v75 )
                    Fcb = *(_QWORD *)(v75 + 184);
                  goto LABEL_318;
                }
              }
            }
            v75 = v222;
LABEL_318:
            if ( v75 )
            {
              v76 = v210;
            }
            else
            {
              while ( 1 )
              {
                v260 = 0;
                memset(v257, 0, 0x58u);
                LOBYTE(v210) = v210 | 0x10;
                v238 = (_QWORD *)PostIrpRoutine;
                LOBYTE(v207) = 0;
                if ( (unsigned __int8)NtfsLookupInFileRecord(
                                        v3,
                                        *(_QWORD *)v215,
                                        *(_QWORD *)v215 + 8LL,
                                        48,
                                        PostIrpRoutine,
                                        PostIrpRoutine,
                                        v207,
                                        PostIrpRoutine,
                                        PostIrpRoutine,
                                        v257) )
                  break;
                PostIrpRoutine = 0xFD00070D48LL;
                NtfsAttachCorruption_BadOrOrphanFRS(v3, 2, 462152, 0, *(_QWORD *)v215 + 8LL, *(__int64 *)v215, 0);
                NtfsAttachRepairInfoPriv(v3, 256, 0, 0xFD00070D48LL);
                if ( NtfsStatusDebugFlags )
                  NtfsStatusTraceAndDebugInternal(v3, 3221225730LL, 462152);
                NtfsRaiseStatusInternal(v3, -1073741566, v215[0] + 8, v215[0], 462152);
              }
              v78 = v257[0] + *(unsigned __int16 *)(v257[0] + 20);
              v79 = *(_DWORD *)(*(_QWORD *)v215 + 8LL);
              if ( v79 == 5 || (v80 = *(_QWORD *)(*(_QWORD *)v215 + 320LL), *(_DWORD *)(v80 + 88) == v79) )
                v80 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v215 + 96LL) + 6248LL);
              Fcb = NtfsCreateFcb(v3, v219, v80, *(_QWORD *)v78, 66, PostIrpRoutine);
              v81 = NtfsCreateScb(v3, Fcb, 160, (unsigned int)&NtfsFileNameIndex, 0, PostIrpRoutine, PostIrpRoutine);
              v222 = v81;
              if ( (*(_DWORD *)(v81 + 200) & 0x200) != 0 )
              {
                NtfsSnapshotScb(v3, v81);
                LODWORD(v81) = v222;
              }
              *((_QWORD *)&v260 + 1) = v78 + 66;
              LOWORD(v260) = 2 * *(unsigned __int8 *)(v78 + 64);
              WORD1(v260) = v260;
              NtfsCreateLcb(v3, v81, v215[0], (unsigned int)&v260, *(_BYTE *)(v78 + 65), PostIrpRoutine);
              v216[0] = 1;
              NtfsCleanupAttributeContext(v3, v257);
              v76 = v210 & 0xEF;
              v75 = v222;
            }
            LOBYTE(v210) = v76 & 0xFB;
            LOBYTE(v262[23]) = 0;
            if ( (v210 & 0x2000) != 0
              || !v75
              || !*((_QWORD *)FsContext + 9)
              || *(int *)(v219 + 4) < 0
              || (FileObject->Flags & 0x20000) != 0 )
            {
              NtfsDeleteFile(v3, v215[0], (__int64)v262, PostIrpRoutine);
            }
            else
            {
              NtfsDeleteFile(v3, v215[0], (__int64)v262, (__int64)&v262[14]);
              NtfsGetTunneledData(
                v3,
                *(_QWORD *)v215,
                *(unsigned __int8 *)(*(_QWORD *)(*((_QWORD *)FsContext + 9) + 192LL) + 65LL),
                &v262[14]);
              if ( (*((_DWORD *)FsContext + 1) & 0x4000000) != 0
                || (*(_DWORD *)(*(_QWORD *)(v222 + 184) + 16LL) & 0x400) == 0 )
              {
                v77 = PostIrpRoutine;
              }
              else
              {
                v77 = 1;
              }
              FsRtlAddToTunnelCacheEx(
                v219 + 4720,
                *(_QWORD *)(*(_QWORD *)(v222 + 184) + 8LL),
                v262,
                &v262[2],
                (BYTE1(v262[23]) != 0 ? 2 : 0) | v77,
                80,
                &v262[14]);
            }
            --*(_WORD *)(*(_QWORD *)v215 + 190LL);
            LOBYTE(v210) = v210 | 0x20;
            v238 = (_QWORD *)PostIrpRoutine;
            if ( !v218 )
            {
              v82 = BYTE1(v210);
              if ( (v210 & 0x2000) == 0 )
              {
                NtfsReportDirNotify(
                  v3,
                  *((_QWORD *)FsContext + 9),
                  v219,
                  (_DWORD)FsContext + 16,
                  *((unsigned __int16 *)FsContext + 16),
                  PostIrpRoutine,
                  1,
                  2,
                  Fcb,
                  PostIrpRoutine);
                v82 = BYTE1(v210);
              }
              BYTE1(v210) = v82 | 2;
              ClearFlagInterlocked((char *)FsContext + 4, 112);
              TruncateSize = &NtfsLarge0;
            }
LABEL_77:
            if ( (v210 & 0x4000) != 0 || (v210 & 0x100) != 0 || v210 < 0 )
              FsRtlCheckOplockEx(
                (POPLOCK)(v222 + 88),
                Irp,
                0x50u,
                0,
                (POPLOCK_WAIT_COMPLETE_ROUTINE)PostIrpRoutine,
                (POPLOCK_FS_PREPOST_IRP)PostIrpRoutine);
            if ( *(_DWORD *)(v217 + 208) != 1 && (v210 & 0x800000) == 0 || !*(_WORD *)(*(_QWORD *)v215 + 188LL) || v218 )
            {
LABEL_86:
              v11 = 4294967288LL;
LABEL_87:
              if ( !v218 && *(_DWORD *)(v217 + 208) == 1 )
              {
                if ( *(_WORD *)(*(_QWORD *)v215 + 188LL) )
                {
                  if ( (v210 & 0x400) == 0
                    && FileObject->SectionObjectPointer == (PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v217 + 288) + 16LL) )
                  {
                    v65 = *(_DWORD *)(v217 + 256);
                    if ( v65 )
                    {
                      if ( (v65 != 32 || *(_QWORD *)(v217 + 184) != *(_QWORD *)(*(_QWORD *)(v219 + 48) + 184LL))
                        && (*(_DWORD *)(v217 + 200) & 1) != 0 )
                      {
                        BYTE2(v210) |= 1u;
                        if ( (v210 & 0x40000000) == 0
                          && (v210 & 0x4000) == 0
                          && (*(_DWORD *)(*(_QWORD *)v215 + 4LL) & 0x100) == 0 )
                        {
                          NtfsPrepareForUpdateDuplicate(v3, v215[0], (unsigned int)&v231, (unsigned int)&v222, 1, 0);
                        }
                        v88 = v217;
                        if ( (*(_DWORD *)(v217 + 200) & 8) != 0 )
                        {
                          if ( ((*(_DWORD *)(v217 + 32) + 7) & 0xFFFFFFF8) < *(_DWORD *)(v217 + 24) )
                          {
                            v183 = v210;
                            if ( (v210 & 0x10) != 0 )
                            {
                              NtfsCleanupAttributeContext(v3, v257);
                              v183 = v210;
                              v88 = v217;
                            }
                            memset(v257, 0, 0x58u);
                            LOBYTE(v210) = v183 | 0x10;
                            LOBYTE(v207) = 0;
                            v184 = NtfsLookupInFileRecord(
                                     v3,
                                     *(_QWORD *)(v88 + 184),
                                     *(_QWORD *)(v88 + 184) + 8LL,
                                     *(unsigned int *)(v88 + 256),
                                     v88 + 264,
                                     PostIrpRoutine,
                                     v207,
                                     PostIrpRoutine,
                                     PostIrpRoutine,
                                     v257);
                            v185 = v217;
                            if ( !v184 && (*(_DWORD *)(v217 + 512) & 4) == 0 )
                            {
                              PostIrpRoutine = 0xA90007115CLL;
                              NtfsAttachCorruption_BadOrOrphanFRS(
                                v3,
                                2,
                                463196,
                                0,
                                *(_QWORD *)(v217 + 184) + 8LL,
                                *(_QWORD *)(v217 + 184),
                                0);
                              NtfsAttachRepairInfoPriv(v3, 512, 0, 0xA90007115CLL);
                              if ( NtfsStatusDebugFlags )
                                NtfsStatusTraceAndDebugInternal(v3, 3221225730LL, 463196);
                              NtfsRaiseStatusInternal(
                                v3,
                                -1073741566,
                                *(_QWORD *)(v217 + 184) + 8,
                                *(_QWORD *)(v217 + 184),
                                463196);
                            }
                            LODWORD(CompletionRoutinea) = PostIrpRoutine;
                            NtfsChangeAttributeValue(
                              v3,
                              v215[0],
                              *(_DWORD *)(v185 + 32),
                              0,
                              (SIZE_T)CompletionRoutinea,
                              1,
                              1,
                              0,
                              0,
                              v257);
                            v31 = 512;
                            v186 = v217;
                            v187 = (*(_DWORD *)(v217 + 32) + 7) & 0xFFFFFFF8;
                            v188 = *(_DWORD *)(v217 + 200);
                            if ( (v188 & 0x20000) != 0
                              && *(_QWORD *)(v217 + 24) > v187
                              && *(_QWORD *)(v217 + 464) > v187 )
                            {
                              if ( (v188 & 0x200) != 0 )
                                v186 = v217;
                              *(_QWORD *)(v186 + 464) = v187;
                              v186 = v217;
                            }
                            *(_QWORD *)(v186 + 24) = v187;
                            *(_QWORD *)(v217 + 472) = v187;
                            v88 = v217;
                          }
                        }
                        else
                        {
                          v31 = *(_QWORD *)(v217 + 24);
                          if ( v31 )
                          {
                            v89 = *(unsigned int *)(v219 + 480);
                            v11 = (v89 + *(_QWORD *)(v217 + 32)) >> *(_BYTE *)(v219 + 488);
                            if ( (v89 + v31) >> *(_BYTE *)(v219 + 488) != v11 )
                            {
                              if ( (*(_DWORD *)(v217 + 200) & 0x20000) == 0
                                || MmCanFileBeTruncated(FileObject->SectionObjectPointer, (PLARGE_INTEGER)(v217 + 32)) )
                              {
                                NtfsDeleteAllocation(v3, 0x7FFFFFFFFFFFFFFFLL, 1, 1);
                              }
                              else if ( (v210 & 8) != 0 )
                              {
                                *(_DWORD *)(v217 + 200) &= ~1u;
                                BYTE2(v210) &= ~1u;
                              }
                              v88 = v217;
                            }
                            v259 = *(_QWORD *)(v88 + 32);
                            TruncateSize = (PLARGE_INTEGER)&v259;
                          }
                        }
                        LOBYTE(v31) = 1;
                        NtfsUpdateScbFromFileObject(FileObject, v88, v31);
                      }
                    }
                  }
                }
              }
              v33 = *(_DWORD *)(v217 + 204);
              if ( v33 )
              {
                if ( *(_DWORD *)(v217 + 208) == v33 + 1
                  && !*(_DWORD *)(v217 + 452)
                  && (*((_BYTE *)FsContext + 104) & 7) != 0 )
                {
                  v189 = *(_QWORD *)(v217 + 288);
                  if ( *(_QWORD *)(v189 + 16) )
                  {
                    if ( !*(_QWORD *)(v189 + 32)
                      && (FileObject->Flags & 8) == 0
                      && !v218
                      && MmCanFileBeTruncated((PSECTION_OBJECT_POINTERS)(v189 + 16), 0)
                      && (*(_DWORD *)(*(_QWORD *)(v217 + 184) + 4LL) & 0x100) == 0
                      && (v210 & 0x4000) == 0 )
                    {
                      NtfsCheckpointCurrentTransaction(v3);
                      if ( v216[0] )
                      {
                        NtfsReleaseFcbEx(v3, *(_QWORD *)(v222 + 184), 0);
                        v216[0] = 0;
                      }
                      NtfsReleaseSharedResources(v3);
                      NtfsFlushAndPurgeScb(v3, v217, 0);
                      *(_DWORD *)(v3 + 24) = PostIrpRoutine;
                    }
                  }
                }
              }
              v27 = *(_QWORD *)v215;
              if ( *(_DWORD *)(*(_QWORD *)v215 + 24LL) == 1
                && (v210 & 4) != 0
                && *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v215 + 96LL) + 8428LL) <= (unsigned int)NtfsMaxDelayCloseCount
                && !v218
                && (*(_DWORD *)(*(_QWORD *)v215 + 4LL) & 4) == 0
                && (*(_DWORD *)(v217 + 200) & 0x1000000) == 0 )
              {
                SetFlagInterlocked(v217 + 200, 0x200000);
              }
              goto LABEL_90;
            }
            if ( (v210 & 0x400) == 0 && (v210 & 0x800000) == 0 )
            {
              if ( *(_DWORD *)(v217 + 256) && (*(_DWORD *)(v217 + 200) & 4) != 0 )
              {
                if ( (v210 & 0x40000000) == 0
                  && (v210 & 0x4000) == 0
                  && (*(_DWORD *)(*(_QWORD *)v215 + 4LL) & 0x100) == 0 )
                {
                  NtfsPrepareForUpdateDuplicate(v3, v215[0], (unsigned int)&v231, (unsigned int)&v222, 1, 0);
                }
                if ( (*(_DWORD *)(v217 + 200) & 8) != 0 )
                {
                  memset(v257, 0, 0x58u);
                  LOBYTE(v210) = v210 | 0x10;
                  LOBYTE(v207) = 0;
                  v99 = NtfsLookupInFileRecord(
                          v3,
                          *(_QWORD *)(v217 + 184),
                          *(_QWORD *)(v217 + 184) + 8LL,
                          *(unsigned int *)(v217 + 256),
                          v217 + 264,
                          PostIrpRoutine,
                          v207,
                          PostIrpRoutine,
                          PostIrpRoutine,
                          v257);
                  v100 = v217;
                  if ( !v99 && (*(_DWORD *)(v217 + 512) & 4) == 0 )
                  {
                    PostIrpRoutine = 0xA900071091LL;
                    NtfsAttachCorruption_BadOrOrphanFRS(
                      v3,
                      2,
                      462993,
                      0,
                      *(_QWORD *)(v217 + 184) + 8LL,
                      *(_QWORD *)(v217 + 184),
                      0);
                    NtfsAttachRepairInfoPriv(v3, 512, 0, 0xA900071091LL);
                    if ( NtfsStatusDebugFlags )
                      NtfsStatusTraceAndDebugInternal(v3, 3221225730LL, 462993);
                    NtfsRaiseStatusInternal(
                      v3,
                      -1073741566,
                      *(_QWORD *)(v217 + 184) + 8,
                      *(_QWORD *)(v217 + 184),
                      462993);
                  }
                  LODWORD(CompletionRoutine) = PostIrpRoutine;
                  NtfsChangeAttributeValue(
                    v3,
                    v215[0],
                    *(_DWORD *)(v100 + 32),
                    0,
                    (SIZE_T)CompletionRoutine,
                    1,
                    1,
                    0,
                    0,
                    v257);
                  v84 = v217;
                  v11 = 4294967288LL;
                  if ( ((*(_DWORD *)(v217 + 32) + 7) & 0xFFFFFFF8) != *(_DWORD *)(v217 + 24) )
                  {
                    v101 = (*(_DWORD *)(v217 + 32) + 7) & 0xFFFFFFF8;
                    v102 = *(_DWORD *)(v217 + 200);
                    if ( (v102 & 0x20000) != 0 && *(_QWORD *)(v217 + 24) > v101 && *(_QWORD *)(v217 + 464) > v101 )
                    {
                      if ( (v102 & 0x200) != 0 )
                        v84 = v217;
                      *(_QWORD *)(v84 + 464) = v101;
                      v84 = v217;
                    }
                    *(_QWORD *)(v84 + 24) = v101;
                    v84 = v217;
                  }
                }
                else
                {
                  NtfsWriteFileSizes(v3, v217, 0, 0, 1, 1);
                  v11 = 4294967288LL;
                  v84 = v217;
                }
                LOBYTE(v83) = 1;
                NtfsUpdateScbFromFileObject(FileObject, v84, v83);
                goto LABEL_87;
              }
              goto LABEL_86;
            }
            if ( (v210 & 0x40000000) != 0
              || !*(_QWORD *)(*(_QWORD *)v215 + 120LL)
              || (v210 & 0x4000) != 0
              || (*(_DWORD *)(*(_QWORD *)v215 + 4LL) & 0x100) != 0 )
            {
              v167 = 2;
            }
            else
            {
              NtfsPrepareForUpdateDuplicate(v3, v215[0], (unsigned int)&v231, (unsigned int)&v222, 1, 0);
              v167 = 2;
            }
            if ( *(_DWORD *)(v217 + 256) )
            {
              if ( (v210 & 0x10) != 0 )
                NtfsCleanupAttributeContext(v3, v257);
              if ( *(_DWORD *)(v217 + 256) == 128
                && ((*(_DWORD *)(v217 + 200) & 0x6000000) != 0 || *(_QWORD *)(v217 + 632) == -1)
                && xmmword_1400957B0 )
              {
                xmmword_1400957B0(v3, *(_QWORD *)v215);
              }
              memset(v257, 0, 0x58u);
              v213 = v210 | 0x10;
              LOBYTE(v207) = 0;
              if ( (unsigned __int8)NtfsLookupInFileRecord(
                                      v3,
                                      *(_QWORD *)(v217 + 184),
                                      *(_QWORD *)(v217 + 184) + 8LL,
                                      *(unsigned int *)(v217 + 256),
                                      v217 + 264,
                                      PostIrpRoutine,
                                      v207,
                                      PostIrpRoutine,
                                      PostIrpRoutine,
                                      v257)
                || (*(_DWORD *)(v217 + 512) & 4) != 0 )
              {
                v167 = *(_WORD *)(v257[0] + 12);
                goto LABEL_796;
              }
              PostIrpRoutine = 0xA900070F88LL;
              NtfsAttachCorruption_BadOrOrphanFRS(
                v3,
                2,
                462728,
                0,
                *(_QWORD *)(v217 + 184) + 8LL,
                *(_QWORD *)(v217 + 184),
                0);
              NtfsAttachRepairInfoPriv(v3, 512, 0, 0xA900070F88LL);
              if ( NtfsStatusDebugFlags )
                NtfsStatusTraceAndDebugInternal(v3, 3221225730LL, 462728);
              NtfsRaiseStatusInternal(v3, -1073741566, *(_QWORD *)(v217 + 184) + 8, *(_QWORD *)(v217 + 184), 462728);
LABEL_801:
              LODWORD(Size) = PostIrpRoutine;
              for ( j = NtfsLookupExternalAttribute(
                          v3,
                          *(_QWORD *)(v168 + 184),
                          *(_DWORD *)(v168 + 256),
                          (PCUNICODE_STRING)(v168 + 264),
                          PostIrpRoutine,
                          0,
                          (void *)PostIrpRoutine,
                          Size,
                          (__int64)v257);
                    j;
                    j = NtfsLookupInFileRecord(
                          v3,
                          *(_QWORD *)(v217 + 184),
                          0,
                          *(unsigned int *)(v217 + 256),
                          v217 + 264,
                          PostIrpRoutine,
                          v208,
                          PostIrpRoutine,
                          PostIrpRoutine,
                          v257) )
              {
LABEL_796:
                NtfsDeleteAttributeRecord(v3, *(_QWORD *)v215, 15, v257);
                v168 = v217;
                if ( v257[5] )
                  goto LABEL_801;
                LOBYTE(v208) = 0;
              }
              NtfsCleanupAttributeContext(v3, v257);
              LOBYTE(v210) = v213 & 0xEF;
              if ( v167 >= 0 && *(__int16 *)(v217 + 460) >= 0
                || (unsigned __int8)NtfsIsSparseStreamRemaining(v3, v215[0]) )
              {
                v172 = 0x200000;
              }
              else
              {
                v170 = (_DWORD *)NtfsAddStructToRollbackList(v3, 1827, *(_QWORD *)v215, 1);
                v171 = ~v170[11] & 0x200;
                v170[11] |= v171;
                v170[10] |= v171 & *(_DWORD *)(*(_QWORD *)v215 + 176LL);
                v170[1] |= 0x10u;
                *(_DWORD *)(*(_QWORD *)v215 + 176LL) &= ~0x200u;
                *(_DWORD *)(*(_QWORD *)v215 + 184LL) |= 4u;
                *(_DWORD *)(*(_QWORD *)v215 + 4LL) |= 0x10u;
                *(_QWORD *)(v3 + 16) |= 4uLL;
                v172 = 2129920;
              }
              NtfsPostUsnChangeWithOverrideOption(v3, v215[0], v172, 0, PostIrpRoutine, PostIrpRoutine, PostIrpRoutine);
            }
            if ( !v218 )
            {
              if ( (v210 & 0x800000) != 0 )
              {
                v258 = PostIrpRoutine;
                v258 = TxfWriteAttributeLogRecord(
                         v3,
                         v215[0],
                         *(_DWORD *)(v217 + 256),
                         (int)v217 + 264,
                         PostIrpRoutine,
                         PostIrpRoutine,
                         PostIrpRoutine,
                         PostIrpRoutine,
                         16);
                TxfUpdateTxfDataAttributeMembers(
                  v3,
                  v215[0],
                  PostIrpRoutine,
                  PostIrpRoutine,
                  (*(_DWORD *)(*(_QWORD *)v215 + 4LL) & 0x100000) == 0,
                  (__int64)&v258,
                  PostIrpRoutine,
                  PostIrpRoutine,
                  PostIrpRoutine,
                  PostIrpRoutine,
                  PostIrpRoutine);
              }
              NtfsCheckpointCurrentTransaction(v3);
              LOBYTE(v210) = v210 | 0x40;
            }
            if ( *(_BYTE *)(v217 + 460) || (*(_DWORD *)(v217 + 512) & 1) != 0 )
              *(_QWORD *)(v217 + 464) = PostIrpRoutine;
            if ( (*(_DWORD *)(v217 + 200) & 0x20000) != 0 && *(__int64 *)(v217 + 24) > 0 && *(__int64 *)(v217 + 464) > 0 )
              *(_QWORD *)(v217 + 464) = PostIrpRoutine;
            *(_QWORD *)(v217 + 24) = PostIrpRoutine;
            v173 = v217;
            v174 = *(_DWORD *)(v217 + 200);
            if ( (v174 & 0x20000) == 0 || *(__int64 *)(v217 + 32) >= 0 )
              goto LABEL_847;
            v175 = PostIrpRoutine;
            if ( *(__int64 *)(v217 + 464) <= 0 )
              v175 = *(_QWORD *)(v217 + 464);
            if ( v175 <= *(_QWORD *)(v217 + 40) )
            {
LABEL_847:
              *(_QWORD *)(v173 + 32) = PostIrpRoutine;
              v179 = v217;
              if ( (*(_DWORD *)(v217 + 200) & 0x200) != 0 )
                v179 = v217;
              v180 = *(_DWORD *)(v179 + 200);
              if ( (v180 & 0x20000) == 0 )
                goto LABEL_862;
              v181 = *(_QWORD *)(v179 + 464);
              if ( v181 >= 0 )
              {
                if ( *(__int64 *)(v179 + 40) <= 0 )
                  goto LABEL_862;
                if ( *(_QWORD *)(*(_QWORD *)(v179 + 288) + 16LL) )
                {
                  if ( v181 <= 0 )
                    goto LABEL_862;
                  if ( (v180 & 0x200) == 0 )
                  {
LABEL_861:
                    *(_QWORD *)(v179 + 464) = PostIrpRoutine;
                    v179 = v217;
LABEL_862:
                    *(_QWORD *)(v179 + 40) = PostIrpRoutine;
                    *(_DWORD *)(v217 + 256) = PostIrpRoutine;
                    if ( (v210 & 0x800000) == 0 || (*(_DWORD *)(*(_QWORD *)(v217 + 528) + 24LL) & 1) != 0 )
                    {
                      *(_DWORD *)(v217 + 512) |= 0x440u;
                      TruncateSize = &NtfsLarge0;
                    }
                    else
                    {
                      *(_DWORD *)(v217 + 512) |= 0x200000u;
                      *(_DWORD *)(*(_QWORD *)(v217 + 528) + 24LL) |= 2u;
                    }
                    *(_DWORD *)(v217 + 512) &= 0xFFFFE5FF;
                    NtfsUpdateFileTimestampsForChange(*(_QWORD *)v215, FsContext, 0x400000);
                    FileObject->Flags &= ~0x4000u;
                    LOBYTE(v182) = 1;
                    NtfsUpdateScbFromFileObject(FileObject, v217, v182);
                    FileObject->Flags |= 0x4000u;
                    v11 = 4294967288LL;
                    goto LABEL_87;
                  }
                }
                else if ( (v180 & 0x200) == 0 || !v181 )
                {
                  goto LABEL_861;
                }
              }
              else if ( (v180 & 0x200) == 0 )
              {
                goto LABEL_861;
              }
              v179 = v217;
              goto LABEL_861;
            }
            if ( (v174 & 0x200) != 0 )
              v173 = v217;
            v176 = *(_DWORD *)(v173 + 200);
            if ( (v176 & 0x20000) != 0 )
            {
              v177 = *(_QWORD *)(v173 + 464);
              if ( v177 < v175 )
              {
                if ( (v176 & 0x200) == 0 )
                  goto LABEL_845;
                goto LABEL_844;
              }
              if ( *(_QWORD *)(v173 + 40) > v175 )
              {
                if ( *(_QWORD *)(*(_QWORD *)(v173 + 288) + 16LL) )
                {
                  if ( v175 == 0x7FFFFFFFFFFFFFFFLL )
                  {
                    if ( (v176 & 0x200) != 0 && v177 != 0x7FFFFFFFFFFFFFFFLL )
                      v173 = v217;
                    *(_QWORD *)(v173 + 464) = 0x7FFFFFFFFFFFFFFFLL;
                    v173 = v217;
                  }
                  else
                  {
                    v178 = (v175 + 4095) & 0xFFFFFFFFFFFFF000uLL;
                    if ( v178 < v177 )
                    {
                      if ( (v176 & 0x200) != 0 )
                        v173 = v217;
                      *(_QWORD *)(v173 + 464) = v178;
                      v173 = v217;
                    }
                  }
                  goto LABEL_846;
                }
                if ( (v176 & 0x200) == 0 || v177 == v175 )
                  goto LABEL_845;
LABEL_844:
                v173 = v217;
LABEL_845:
                *(_QWORD *)(v173 + 464) = v175;
                v173 = v217;
              }
            }
LABEL_846:
            *(_QWORD *)(v173 + 40) = v175;
            v173 = v217;
            goto LABEL_847;
          }
          if ( !v19 )
            goto LABEL_77;
          BYTE1(v210) |= 0x40u;
          if ( (v210 & 0x10000000) != 0 )
          {
            v66 = (__int64)v238;
          }
          else
          {
            v166 = NtfsFindMatchingLcbPair(v19, 0);
            v66 = v166;
            v238 = (_QWORD *)v166;
            if ( v166 && *(_DWORD *)(v166 + 188) )
              BYTE1(v210) &= ~0x40u;
          }
          if ( (v210 & 0x4000) != 0 && *(_WORD *)(*(_QWORD *)v215 + 190LL) > 1u )
          {
            NtfsAcquireExclusiveScbEx(v3, v222, 0);
            v216[0] = 1;
            v108 = v215[0];
            if ( *(_QWORD *)(*(_QWORD *)v215 + 120LL) )
            {
              NtfsAcquireSharedFcb(v3, *(_QWORD *)(*(_QWORD *)(v219 + 160) + 184LL), *(_QWORD *)(v219 + 160), 0);
              LOBYTE(v210) = v210 | 2;
              NtfsAcquireQuotaControl(v3, *(_QWORD *)(*(_QWORD *)v215 + 120LL));
              v108 = v215[0];
            }
            LOBYTE(v210) = v210 & 0xFB;
            if ( (v210 & 0x10000000) != 0 )
            {
              NtfsCheckpointCurrentTransaction(v3);
              LOBYTE(v210) = v210 | 0x20;
            }
            else
            {
              v109 = PostIrpRoutine;
              if ( (*(_BYTE *)(*(_QWORD *)(v19 + 192) + 65LL) & 3) != 2 )
                v109 = *(_QWORD *)(v19 + 192);
              NtfsPostUsnChangeWithOverrideOption(v3, v108, -2147418112, 0, PostIrpRoutine, PostIrpRoutine, v109);
              LOBYTE(v262[23]) = 0;
              if ( (v210 & 0x2000) != 0 || *(int *)(v219 + 4) < 0 || (FileObject->Flags & 0x20000) != 0 )
              {
                NtfsRemoveLink(v3, v215[0], (__int64)v262, PostIrpRoutine);
              }
              else
              {
                NtfsRemoveLink(v3, v215[0], (__int64)v262, (__int64)&v262[14]);
                NtfsGetTunneledData(v3, *(_QWORD *)v215, *(unsigned __int8 *)(*(_QWORD *)(v19 + 192) + 65LL), &v262[14]);
                if ( (*((_DWORD *)FsContext + 1) & 0x4000000) != 0
                  || (v110 = 1, (*(_DWORD *)(*(_QWORD *)(v222 + 184) + 16LL) & 0x400) == 0) )
                {
                  v110 = PostIrpRoutine;
                }
                FsRtlAddToTunnelCacheEx(
                  v219 + 4720,
                  *(_QWORD *)(*(_QWORD *)(v222 + 184) + 8LL),
                  v262,
                  &v262[2],
                  v110 | *(_BYTE *)(*(_QWORD *)(v19 + 192) + 65LL) & 2,
                  80,
                  &v262[14]);
              }
              NtfsCheckpointCurrentTransaction(v3);
              LOBYTE(v210) = v210 | 0x20;
              --*(_WORD *)(*(_QWORD *)v215 + 190LL);
              NtfsRemovePrefix(v3, v19);
              if ( (*(_DWORD *)(v19 + 4) & 0x20) != 0 )
              {
                NtfsRemoveHashEntry(
                  v3,
                  *(_QWORD *)(*(_QWORD *)(v19 + 48) + 96LL) + 4968LL,
                  *(unsigned int *)(v19 + 184),
                  v19);
                *(_DWORD *)(v19 + 184) = PostIrpRoutine;
                ClearFlagInterlocked(v19 + 4, 32);
              }
              SetFlagInterlocked(v19 + 4, 2);
              *(_DWORD *)(v19 + 180) = PostIrpRoutine;
              *(_DWORD *)(v19 + 156) = PostIrpRoutine;
              if ( v66 )
              {
                NtfsRemovePrefix(v3, v66);
                if ( (*(_DWORD *)(v66 + 4) & 0x20) != 0 )
                {
                  NtfsRemoveHashEntry(
                    v3,
                    *(_QWORD *)(*(_QWORD *)(v66 + 48) + 96LL) + 4968LL,
                    *(unsigned int *)(v66 + 184),
                    v66);
                  *(_DWORD *)(v66 + 184) = PostIrpRoutine;
                  ClearFlagInterlocked(v66 + 4, 32);
                }
                SetFlagInterlocked(v66 + 4, 2);
                *(_DWORD *)(v66 + 180) = PostIrpRoutine;
                *(_DWORD *)(v66 + 156) = PostIrpRoutine;
              }
            }
            NtfsUpdateFcbTimestamps(Fcb, 2684354576LL);
            if ( (v210 & 0x2000) == 0 && (v218 & 0x80000000) == 0 && (v210 & 0x10000000) == 0 )
              NtfsReportDirNotify(
                v3,
                *((_QWORD *)FsContext + 9),
                v219,
                (_DWORD)FsContext + 16,
                *((unsigned __int16 *)FsContext + 16),
                PostIrpRoutine,
                1,
                2,
                Fcb,
                PostIrpRoutine);
            v231 = PostIrpRoutine;
            if ( (v218 & 0x80000000) == 0 )
              NtfsUpdateFileTimestampsForChange(*(_QWORD *)v215, FsContext, 0);
            FileObject->Flags &= ~0x4000u;
            LOBYTE(v111) = 1;
            NtfsUpdateScbFromFileObject(FileObject, v217, v111);
            FileObject->Flags |= 0x4000u;
            goto LABEL_77;
          }
          if ( (v210 & 0x4000) == 0 )
            goto LABEL_77;
          BYTE1(v210) &= ~0x40u;
          if ( (*(_DWORD *)(*(_QWORD *)v215 + 176LL) & 0x10000000) != 0
            || (*((_DWORD *)FsContext + 2) & 0x10000) == 0 && !*(_QWORD *)(*(_QWORD *)v215 + 352LL) )
          {
            goto LABEL_77;
          }
          if ( (*(_DWORD *)(v19 + 4) & 0x40) != 0 )
            goto LABEL_77;
          if ( *(_QWORD *)(v3 + 400) )
            goto LABEL_77;
          v67 = *(_QWORD *)(v219 + 200);
          if ( *(_QWORD *)(v19 + 24) == v67 || !v67 )
            goto LABEL_77;
        }
        else
        {
          if ( (*(_DWORD *)(v19 + 4) & 1) == 0
            && ((*(_BYTE *)(*(_QWORD *)(v19 + 192) + 65LL) & 3) == 0
             || (*(_DWORD *)(*(_QWORD *)(v19 + 48) + 4LL) & 0x20) == 0) )
          {
            goto LABEL_77;
          }
          v31 = (__int64)FsContext;
          if ( (*((_DWORD *)FsContext + 2) & 0x10000) == 0 || (v32 & 0x40) != 0 )
            goto LABEL_77;
          if ( *(_QWORD *)(v3 + 400) )
            goto LABEL_77;
          v74 = *(_QWORD *)(v219 + 200);
          if ( *(_QWORD *)(v19 + 24) == v74 || !v74 )
            goto LABEL_77;
        }
        NtfsRenameToPrivateDir(v3, (__int64)FsContext, v19, v222, (__int64)v216);
        HIBYTE(v210) |= 0x80u;
        goto LABEL_77;
      case 3u:
        goto LABEL_49;
      case 4u:
        FileObject->Flags |= 0x4000u;
        if ( *((_BYTE *)FsContext + 88) == 4 && (*((_DWORD *)FsContext + 1) & 0x400) != 0 )
        {
          v228 = 0;
          v227 = 0;
          ExAcquireResourceExclusiveLite((PERESOURCE)(v219 + 6800), 1u);
          v228 = 1;
          ExAcquireResourceExclusiveLite(&stru_1400953C0, 1u);
          v227 = 1;
          ClearFlagInterlocked((char *)FsContext + 4, 1024);
          *(_DWORD *)(v219 + 6904) &= ~2u;
          *(_QWORD *)(v219 + 6928) = PostIrpRoutine;
          if ( !--dword_140095450 )
            NtfsSendGlobalCorruptionActionEvent(v3);
          ExReleaseResourceLite(&stru_1400953C0);
          ExReleaseResourceLite((PERESOURCE)(v219 + 6800));
        }
        v27 = v219;
        if ( *(struct _FILE_OBJECT **)(v219 + 1480) == FileObject )
        {
          v161 = *(_QWORD *)(v219 + 72);
          if ( v161 )
          {
            NtfsAcquireExclusiveFcb(v3, *(_QWORD *)(v161 + 184), *(_QWORD *)(v219 + 72), 0);
            *(_QWORD *)(v219 + 5368) = 0x7FFFFFFFFFFFFFFFLL;
            *(_QWORD *)(v219 + 5376) = PostIrpRoutine;
            *(_QWORD *)(v219 + 1480) = PostIrpRoutine;
            NtfsReleaseFcbEx(v3, *(_QWORD *)(*(_QWORD *)(v219 + 72) + 184LL), 0);
            v27 = v219;
          }
        }
        if ( (*(_DWORD *)(v27 + 4) & 2) == 0
          || (struct _FILE_OBJECT *)(*(_QWORD *)(v27 + 1472) & 0xFFFFFFFFFFFFFFFEuLL) != FileObject )
        {
          goto LABEL_90;
        }
        v90 = *(_DWORD *)(v3 + 12);
        if ( (v90 & 0x200) == 0 )
        {
          *(_DWORD *)(v3 + 12) = v90 | 0x200;
          NtfsRaiseStatusInternal(v3, -1073741608, 0, 0, 461358);
          goto LABEL_407;
        }
        if ( *(struct _FILE_OBJECT **)(v27 + 1472) == (struct _FILE_OBJECT *)((char *)&FileObject->Type + 1) )
        {
          NtfsSendBeginDismountEvent(v3, v27, 0, 3);
          if ( (*(_DWORD *)(v219 + 24) & 0x40000) != 0 )
          {
            v162 = *(_QWORD *)(v219 + 64);
            if ( !v162 || (*(_DWORD *)(v162 + 200) & 0x20000) != 0 )
              NtfsPurgeLogFile(v219, v3);
          }
          NtfsPerformDismountOnVcb((PVOID)v3, 3, PostIrpRoutine);
          goto LABEL_733;
        }
        if ( (FileObject->Flags & 0x1000) != 0 )
        {
          if ( (v210 & 0x80000) != 0 && (v210 & 0x100000) == 0 )
          {
            if ( (unsigned __int8)NtfsIsFileStillValid(*(_QWORD *)v215) )
            {
              NtfsReleaseFcbEx(v3, *(_QWORD *)(v217 + 184), 0);
              NtfsFlushVolume(v3);
              NtfsAcquireExclusiveFcb(v3, *(_QWORD *)(v217 + 184), v217, 8);
            }
            v27 = v219;
          }
          if ( *(_DWORD *)(v27 + 256) == 1 )
          {
            v27 = v219;
            if ( *(_DWORD *)(v219 + 260) - *(_DWORD *)(v219 + 268) == 1 )
            {
              NtfsSendBeginDismountEvent(v3, v219, 0, 3);
              NtfsPerformDismountOnVcb((PVOID)v3, 3, PostIrpRoutine);
              v27 = v219;
            }
          }
          else
          {
LABEL_733:
            v27 = v219;
          }
        }
        ClearFlagInterlocked(v27 + 4, 32770);
        *(_QWORD *)(v219 + 1472) = PostIrpRoutine;
        BYTE2(v210) |= 2u;
        if ( (BYTE2(v210) & 0x18) == 8 && (unsigned __int8)NtfsIsFileStillValid(*(_QWORD *)v215) && !v218 )
        {
          if ( *(_DWORD *)(v219 + 2156) == -1073741202 )
          {
            *(_DWORD *)(v219 + 2156) = PostIrpRoutine;
            NtfsPostSpecial(v3, v219, (unsigned int)NtfsDeleteUsnSpecial, v219 + 2144, 13);
          }
          if ( !v218 )
          {
            v27 = v219;
            if ( (*(_DWORD *)(v219 + 4504) & 0xE00) != 0 && (*(_DWORD *)(v219 + 4504) & 0x40) != 0 )
              NtfsPostRepairQuotaIndex(v3);
          }
        }
        goto LABEL_90;
    }
    if ( v230 != 6 )
    {
      if ( (!v3 || (*(_DWORD *)(v3 + 16) & 0x100000LL) == 0)
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x800) != 0 )
      {
        McTemplateU0q_EtwWriteTransfer(&NtfsLog_Context, cleanup_c4599, v230);
      }
      KeBugCheckEx(0x24u, 0xAD000711FCuLL, (int)v230, 0, PostIrpRoutine);
    }
LABEL_49:
    NtfsSnapshotScb(v3, v217);
    v25 = v217;
    v26 = *(_DWORD *)(v217 + 256);
    if ( v26 == 128 && *(_WORD *)v217 == 1797
      || v26 == 160
      && *(_WORD *)(v217 + 264) == 8
      && **(_QWORD **)(v217 + 272) == 0x30003300490024LL
      && (unsigned __int16)(*(_WORD *)v217 - 1795) <= 1u )
    {
      FsRtlCheckOplock((POPLOCK)(v217 + 88), Irp, 0, 0, (POPLOCK_FS_PREPOST_IRP)PostIrpRoutine);
      v25 = v217;
    }
    LOBYTE(v24) = 1;
    NtfsUpdateScbFromFileObject(FileObject, v25, v24);
    FileObject->Flags |= 0x4000u;
    if ( (*((_DWORD *)FsContext + 1) & 0x800000) != 0 )
    {
      if ( v230 == 6 )
      {
        FsRtlNotifyCleanup(*(PNOTIFY_SYNC *)(v219 + 1464), (PLIST_ENTRY)(v219 + 1448), FsContext);
        ClearFlagInterlocked((char *)FsContext + 4, 0x800000);
        _InterlockedDecrement((volatile signed __int32 *)(v219 + 2440));
      }
      else
      {
        FsRtlNotifyCleanup(*(PNOTIFY_SYNC *)(v217 + 768), (PLIST_ENTRY)(v217 + 752), FsContext);
        ClearFlagInterlocked((char *)FsContext + 4, 0x800000);
        _InterlockedDecrement((volatile signed __int32 *)(v219 + 2436));
      }
    }
    if ( (v210 & 0x80000) != 0
      && (v210 & 0x100000) == 0
      && *(_WORD *)v217 == 1795
      && (unsigned __int8)NtfsIsFileStillValid(*(_QWORD *)v215) )
    {
      if ( (v210 & 0x100) == 0 )
      {
        if ( v19
          && ((v57 = *(_DWORD *)(v19 + 4), (v57 & 1) != 0)
           || (*(_BYTE *)(*(_QWORD *)(v19 + 192) + 65LL) & 3) != 0
           && (*(_DWORD *)(*(_QWORD *)(v19 + 48) + 4LL) & 0x20) != 0)
          && ((*((_DWORD *)FsContext + 2) & 0x10000) != 0 || *(_QWORD *)(*(_QWORD *)v215 + 352LL))
          && (v57 & 0x40) == 0
          && !*(_QWORD *)(v3 + 400)
          && (v58 = *(_QWORD *)(v219 + 200), *(_QWORD *)(v19 + 24) != v58)
          && v58 )
        {
          NtfsRenameToPrivateDir(v3, (__int64)FsContext, v19, v222, (__int64)v216);
          HIBYTE(v210) |= 0x80u;
        }
        else
        {
          v27 = *(_QWORD *)v215;
          if ( *(_DWORD *)(*(_QWORD *)v215 + 24LL) == 1
            && (v210 & 4) != 0
            && *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v215 + 96LL) + 8428LL) <= (unsigned int)NtfsMaxDelayCloseCount
            && (*(_DWORD *)(v217 + 200) & 0x1000000) == 0 )
          {
            SetFlagInterlocked(v217 + 200, 0x200000);
          }
        }
LABEL_59:
        if ( (v210 & 0x100) != 0 || v210 < 0 )
          FsRtlCheckOplockEx(
            (POPLOCK)(v222 + 88),
            Irp,
            0x50u,
            0,
            (POPLOCK_WAIT_COMPLETE_ROUTINE)PostIrpRoutine,
            (POPLOCK_FS_PREPOST_IRP)PostIrpRoutine);
        goto LABEL_90;
      }
LABEL_407:
      if ( v19 )
      {
        v238 = (_QWORD *)v19;
        if ( (*(_DWORD *)(v19 + 4) & 2) != 0 )
        {
          v238 = (_QWORD *)PostIrpRoutine;
          v19 = PostIrpRoutine;
          v224 = PostIrpRoutine;
          v91 = PostIrpRoutine;
          v222 = PostIrpRoutine;
          goto LABEL_410;
        }
      }
      else
      {
        v163 = NtfsGetNextParentLcb(v3, *(_QWORD *)v215, 0);
        v238 = (_QWORD *)v163;
        if ( v163 )
        {
          v91 = *(_QWORD *)(v163 + 24);
          v222 = v91;
          if ( v91 )
            Fcb = *(_QWORD *)(v91 + 184);
          goto LABEL_410;
        }
      }
      v91 = v222;
LABEL_410:
      if ( !v91 )
      {
        while ( 1 )
        {
          v256 = 0;
          memset(v257, 0, 0x58u);
          LOBYTE(v210) = v210 | 0x10;
          LOBYTE(v207) = 0;
          if ( (unsigned __int8)NtfsLookupInFileRecord(
                                  v3,
                                  *(_QWORD *)v215,
                                  *(_QWORD *)v215 + 8LL,
                                  48,
                                  PostIrpRoutine,
                                  PostIrpRoutine,
                                  v207,
                                  PostIrpRoutine,
                                  PostIrpRoutine,
                                  v257) )
            break;
          PostIrpRoutine = 0xFC00070B5DLL;
          NtfsAttachCorruption_BadOrOrphanFRS(v3, 2, 461661, 0, *(_QWORD *)v215 + 8LL, *(__int64 *)v215, 0);
          NtfsAttachRepairInfoPriv(v3, 256, 0, 0xFC00070B5DLL);
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(v3, 3221225730LL, 461661);
          NtfsRaiseStatusInternal(v3, -1073741566, v215[0] + 8, v215[0], 461661);
        }
        v93 = v257[0] + *(unsigned __int16 *)(v257[0] + 20);
        v94 = *(_DWORD *)(*(_QWORD *)v215 + 8LL);
        if ( v94 == 5 || (v95 = *(_QWORD *)(*(_QWORD *)v215 + 320LL), *(_DWORD *)(v95 + 88) == v94) )
          v95 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v215 + 96LL) + 6248LL);
        Fcb = NtfsCreateFcb(v3, v219, v95, *(_QWORD *)v93, 66, PostIrpRoutine);
        v96 = NtfsCreateScb(v3, Fcb, 160, (unsigned int)&NtfsFileNameIndex, 0, PostIrpRoutine, PostIrpRoutine);
        v222 = v96;
        if ( (*(_DWORD *)(v96 + 200) & 0x200) != 0 )
        {
          NtfsSnapshotScb(v3, v96);
          LODWORD(v96) = v222;
        }
        *((_QWORD *)&v256 + 1) = v93 + 66;
        LOWORD(v256) = 2 * *(unsigned __int8 *)(v93 + 64);
        WORD1(v256) = v256;
        NtfsCreateLcb(v3, v96, v215[0], (unsigned int)&v256, *(_BYTE *)(v93 + 65), PostIrpRoutine);
        v216[0] = 1;
        NtfsCleanupAttributeContext(v3, v257);
        LOBYTE(v210) = v210 & 0xEF;
      }
      NtfsDeleteFile(v3, v215[0], PostIrpRoutine, PostIrpRoutine);
      --*(_WORD *)(*(_QWORD *)v215 + 190LL);
      LOBYTE(v210) = v210 | 0x20;
      v92 = v219;
      if ( *(int *)(v219 + 4) >= 0 )
      {
        FsRtlDeleteKeyFromTunnelCache((TUNNEL *)(v219 + 4720), *(_QWORD *)(*(_QWORD *)v215 + 8LL));
        v92 = v219;
      }
      v238 = (_QWORD *)PostIrpRoutine;
      if ( !v218 )
      {
        v97 = BYTE1(v210);
        if ( (v210 & 0x2000) == 0 )
        {
          NtfsReportDirNotify(
            v3,
            *((_QWORD *)FsContext + 9),
            v92,
            (_DWORD)FsContext + 16,
            *((unsigned __int16 *)FsContext + 16),
            PostIrpRoutine,
            2,
            2,
            Fcb,
            PostIrpRoutine);
          v97 = BYTE1(v210);
        }
        BYTE1(v210) = v97 | 2;
        ClearFlagInterlocked((char *)FsContext + 4, 112);
      }
      goto LABEL_59;
    }
LABEL_90:
    if ( v230 == 4 )
    {
      v11 = 4;
      v7 = 8;
      goto LABEL_117;
    }
    v34 = *(_QWORD *)(*(_QWORD *)v215 + 192LL);
    if ( *(_QWORD *)(*(_QWORD *)v215 + 152LL) != v34 )
    {
      v59 = *(_DWORD *)(*(_QWORD *)v215 + 4LL);
      if ( (v59 & 0x10) != 0 )
      {
        *(_QWORD *)(*(_QWORD *)v215 + 152LL) = v34;
      }
      else
      {
        if ( (v59 & 1) != 0 || !(unsigned __int8)NtfsCheckLastAccess(v3, *(_QWORD *)v215) )
          goto LABEL_92;
        *(_DWORD *)(*(_QWORD *)v215 + 4LL) |= 0x10u;
      }
      *(_DWORD *)(*(_QWORD *)v215 + 184LL) |= 0x20u;
    }
LABEL_92:
    if ( (v210 & 0x80000) == 0 || (v210 & 0x100000) != 0 || !(unsigned __int8)NtfsIsFileStillValid(*(_QWORD *)v215) )
      goto LABEL_93;
    if ( (*(_DWORD *)(*(_QWORD *)v215 + 4LL) & 0x10) == 0 || v218 || (v210 & 0x20000000) != 0 )
    {
      v47 = 512;
      v11 = 8;
    }
    else
    {
      NtfsUpdateStandardInformation(v3, v215[0]);
      v47 = 512;
      v11 = 8;
    }
    v48 = v231;
    if ( ((*(_DWORD *)(*(_QWORD *)v215 + 184LL) & 0xD00000FC) != 0
       || v231 && (*(_DWORD *)(v231 + 180) & 0xD00000FC) != 0 && ((*(_DWORD *)(v231 + 4) & 0x40) == 0 || v210 >= 0))
      && !v218
      && (*(_DWORD *)(*(_QWORD *)v215 + 4LL) & 0x100) == 0 )
    {
      v63 = 0;
      v223 = 0;
      if ( (*(_DWORD *)(*(_QWORD *)v215 + 4LL) & 0x20000) != 0
        || v222 && ((v64 = *(_QWORD *)(v222 + 184), (*(_DWORD *)(v64 + 4) & 0x20000) != 0) || *(int *)(v64 + 176) < 0) )
      {
        v223 = 1;
      }
      else
      {
        if ( (v210 & 0x4000) == 0 )
        {
          updated = 0;
          v225 = 0;
          v69 = HIBYTE(v210);
          if ( (v210 & 0x40000000) != 0 )
          {
            v48 = v231;
          }
          else
          {
            updated = NtfsPrepareForUpdateDuplicate(v3, v215[0], (unsigned int)&v231, (unsigned int)&v222, 1, 1);
            v225 = updated;
            v48 = v231;
            if ( v231 && (*(_DWORD *)(v231 + 4) & 0x40) != 0 )
            {
              v69 = HIBYTE(v210);
              if ( v210 < 0 )
                updated = PostIrpRoutine;
              v225 = updated;
            }
            else
            {
              v69 = HIBYTE(v210);
            }
          }
          if ( !updated || (v69 & 0x40) != 0 )
          {
            v223 = 1;
            goto LABEL_168;
          }
          v63 = NtfsUpdateDuplicateInfo(v3, v215[0]);
          v223 = v63;
        }
        if ( !v63 )
          BYTE2(v210) |= 4u;
      }
      v48 = v231;
    }
LABEL_168:
    if ( (v210 & 0x2000) == 0 && !v218 )
    {
      v239 = PostIrpRoutine;
      if ( (v210 & 0x40000) != 0 && (v210 & 0x4000) == 0 || (*(_DWORD *)(*(_QWORD *)v215 + 184LL) & 0x100) != 0 )
      {
        v70 = v48 ? *(_DWORD *)(v48 + 180) : PostIrpRoutine;
        v71 = *(_DWORD *)(*(_QWORD *)v215 + 184LL);
        if ( ((v70 | v71) & 0x40000000) != 0 )
        {
          if ( v48 )
            v98 = *(_DWORD *)(v48 + 180);
          else
            LOWORD(v98) = PostIrpRoutine;
          v73 = ((unsigned __int16)v98 | (unsigned __int16)v71) & 0x1F4 | 8;
        }
        else
        {
          if ( v48 )
            v72 = *(_DWORD *)(v48 + 180);
          else
            LOWORD(v72) = PostIrpRoutine;
          v73 = ((unsigned __int16)v72 | (unsigned __int16)v71) & 0x1FC;
        }
        v239 = v73;
        if ( v73 )
          NtfsReportDirNotify(
            v3,
            *((_QWORD *)FsContext + 9),
            v219,
            (_DWORD)FsContext + 16,
            *((unsigned __int16 *)FsContext + 16),
            PostIrpRoutine,
            v73,
            3,
            Fcb,
            PostIrpRoutine);
      }
      *(_DWORD *)(*(_QWORD *)v215 + 184LL) &= ~0x100u;
      v49 = v217;
      if ( *(_WORD *)(v217 + 264) && *(_DWORD *)(v217 + 256) == 128 )
      {
        v50 = *(_DWORD *)(v217 + 512);
        if ( (v50 & 0x1C00) != 0 )
        {
          v239 = PostIrpRoutine;
          if ( (v50 & 0x400) != 0 )
          {
            v239 = 512;
            v51 = 7;
          }
          else
          {
            v47 = PostIrpRoutine;
            if ( (v50 & 0x800) != 0 )
              v47 = 1024;
            v239 = v47;
            if ( (v50 & 0x1000) != 0 )
            {
              v47 |= 0x800u;
              v239 = v47;
            }
            v51 = 8;
          }
          NtfsReportDirNotify(
            v3,
            *((_QWORD *)FsContext + 9),
            v219,
            (_DWORD)FsContext + 16,
            *((unsigned __int16 *)FsContext + 16),
            v217 + 264,
            v47,
            v51,
            Fcb,
            PostIrpRoutine);
          v49 = v217;
        }
        *(_DWORD *)(v217 + 512) = *(_DWORD *)(v49 + 512) & 0xFFFFE1FF;
      }
    }
LABEL_93:
    *(_DWORD *)(*(_QWORD *)v215 + 4LL) &= ~0x10u;
    if ( v216[0] && (v210 & 0x4000) == 0 )
    {
      NtfsReleaseFcbEx(v3, *(_QWORD *)(v222 + 184), 0);
      v216[0] = 0;
    }
    if ( FileObject->PrivateCacheMap || TruncateSize )
      CcUninitializeCacheMap(FileObject, TruncateSize, 0);
    if ( (v210 & 0x10) != 0 )
    {
      NtfsCleanupAttributeContext(v3, v257);
      LOBYTE(v210) = v210 & 0xEF;
    }
    v35 = *(_QWORD *)v215;
    v36 = *(_QWORD *)(*(_QWORD *)v215 + 328LL);
    if ( v36 )
      v27 = *(_QWORD *)(v36 + 24);
    else
      v27 = PostIrpRoutine;
    if ( v27 == *(_QWORD *)(v3 + 400)
      && (*(_DWORD *)(*(_QWORD *)v215 + 20LL) == 1 && (!v36 || !*(_QWORD *)(v36 + 24))
       || (v210 & 0x2000000) != 0 && *(_WORD *)(v36 + 144) == 1) )
    {
      v37 = *(_QWORD *)(*(_QWORD *)v215 + 296LL);
      if ( v37 )
      {
        if ( *(_DWORD *)(v37 + 248) || *(_QWORD *)(v3 + 240) == *(_QWORD *)v215 && *(_DWORD *)(v3 + 256) )
        {
          v27 = PostIrpRoutine;
          while ( 1 )
          {
            v87 = NtfsGetNextChildScb(v35, v27, 1);
            v27 = v87;
            if ( !v87 )
            {
              NtfsPostUsnChangeWithOverrideOption(
                v3,
                v215[0],
                0x80000000,
                0,
                PostIrpRoutine,
                PostIrpRoutine,
                PostIrpRoutine);
              v35 = *(_QWORD *)v215;
              v7 = 8;
              goto LABEL_107;
            }
            if ( (*(_BYTE *)(v87 + 4) & 0x20) != 0 && (*(_DWORD *)(v87 + 200) & 0x40000) != 0 )
              break;
            v35 = *(_QWORD *)v215;
          }
          v35 = *(_QWORD *)v215;
        }
      }
    }
    v7 = 8;
LABEL_107:
    if ( *(_QWORD *)(v3 + 240) && !v218 )
    {
      NtfsWriteUsnJournalChanges(v3);
      NtfsCheckpointCurrentTransaction(v3);
      v35 = *(_QWORD *)v215;
    }
    if ( v218 == -1073741608 || v218 == -1073741432 )
      break;
    if ( !v218 || (v210 & 8) != 0 )
    {
      if ( (*(_DWORD *)(v217 + 200) & 4) != 0 && *(_DWORD *)(v217 + 208) == 1 )
      {
        v11 = 4;
        ClearFlagInterlocked(v217 + 200, 4);
        v35 = *(_QWORD *)v215;
      }
      else
      {
        v11 = 4;
      }
      if ( (v210 & 0x10000) != 0 )
      {
        ClearFlagInterlocked(v217 + 200, 1);
        v35 = *(_QWORD *)v215;
      }
      if ( (v210 & 0x2000000) == 0 )
        goto LABEL_116;
    }
    else
    {
      *(_DWORD *)(v217 + 512) |= 0x20000000u;
      BYTE1(v210) |= 0x80u;
      if ( (*(_DWORD *)(v3 + 16) & 0x100000LL) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 1) != 0 )
      {
        McTemplateU0q_EtwWriteTransfer(&NtfsLog_Context, cleanup_c5039, v218);
      }
      NtfsRaiseStatusInternal(v3, 0, 0, 0, 463797);
    }
    ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(v35 + 328) + 136LL), 1u);
    v190 = *(_QWORD *)v215;
    v191 = *(_QWORD *)(*(_QWORD *)v215 + 328LL);
    v232 = v191;
    if ( *(_WORD *)(v191 + 144) == 1 && (*(_DWORD *)(v191 + 4) & 0x10000) == 0 )
    {
      if ( *(_WORD *)(*(_QWORD *)v215 + 188LL) > 1u )
      {
        ExReleaseResourceLite(*(PERESOURCE *)(v191 + 136));
        v232 = PostIrpRoutine;
        TxfLogFcbInfoRecord(v3, *(_QWORD *)(v3 + 400), v215[0], 0, 1, PostIrpRoutine);
        ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v215 + 328LL) + 136LL), 1u);
        v190 = *(_QWORD *)v215;
        v232 = *(_QWORD *)(*(_QWORD *)v215 + 328LL);
      }
      *(_DWORD *)(*(_QWORD *)(v190 + 328) + 4LL) |= 0x10000u;
      v190 = *(_QWORD *)v215;
    }
    ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(v190 + 328) + 136LL));
    v232 = PostIrpRoutine;
    v35 = *(_QWORD *)v215;
LABEL_116:
    if ( *(_DWORD *)(v35 + 20) == 1 )
    {
      v27 = *(unsigned int *)(v35 + 8);
      if ( (_DWORD)v27 == 5 || *(_DWORD *)(*(_QWORD *)(v35 + 320) + 88LL) == (_DWORD)v27 )
      {
        v52 = *(_QWORD *)(v35 + 320);
        if ( v52 != *(_QWORD *)(*(_QWORD *)(v52 + 16) + 6248LL) )
        {
          if ( (unsigned __int8)TxfMarkRmForShutdown(v52) )
          {
            _InterlockedOr((volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)v215 + 320LL) + 136LL), 4u);
            TxfQueueDelayedRmWorkItem(*(_QWORD *)(*(_QWORD *)v215 + 320LL), v27, v53, v54);
          }
        }
      }
    }
LABEL_117:
    if ( v218 != -1073741608 && v218 != -1073741432 )
    {
      if ( !v218 || (v210 & 8) != 0 )
      {
        v38 = (char *)FsContext + 128;
        if ( !*((_QWORD *)FsContext + 16) )
          goto LABEL_121;
      }
      else
      {
        *(_DWORD *)(v217 + 512) |= 0x20000000u;
        if ( (!v3 || (*(_DWORD *)(v3 + 16) & 0x100000LL) == 0)
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 1) != 0 )
        {
          McTemplateU0q_EtwWriteTransfer(&NtfsLog_Context, cleanup_c5206, v218);
        }
        NtfsRaiseStatusInternal(v3, 0, 0, 0, 463964);
      }
      if ( xmmword_140095790 )
        xmmword_140095790(v38, 0);
LABEL_121:
      if ( *(_DWORD *)(v217 + 208) == 1 && *(_QWORD *)(v217 + 536) && xmmword_140095790 )
      {
        LOBYTE(v27) = 1;
        xmmword_140095790(v217 + 536, v27);
      }
      if ( !*(_QWORD *)(v3 + 400)
        && *(_DWORD *)(v217 + 208) == 1
        && *(_QWORD *)(v217 + 504)
        && (*(_BYTE *)(v217 + 4) & 0x20) != 0
        && (dword_1400956B8 & 0x10000000) != 0 )
      {
        v265 = 0;
        NtfsCoherencyFlushAndPurgeCache(v3, v217, 0, 0, &v265, PostIrpRoutine);
      }
      if ( (*(_DWORD *)(v3 + 8) & 1) != 0 )
        NtfsPersistStorageReserveChanges(v3);
      *(_DWORD *)(v3 + 12) |= 0x8000000u;
      SetFlagInterlocked((char *)FsContext + 4, 0x8000);
      if ( (v210 & 0x4000) != 0 || (v210 & 0x10000000) != 0 )
        *(_DWORD *)(*(_QWORD *)v215 + 4LL) &= ~0x4000u;
      if ( (v210 & 0x100) != 0 && (*(_DWORD *)(v219 + 8204) & 4) != 0 && v230 - 2 <= 1 )
      {
        *(_QWORD *)&v265 = 0;
        v263 = 0;
        v264 = 0;
        *((_QWORD *)&v265 + 1) = PostIrpRoutine;
        *(_QWORD *)&v265 = *(_QWORD *)(*(_QWORD *)(v217 + 184) + 8LL);
        if ( Irp )
        {
          ActivityIdIrp = IoGetActivityIdIrp(Irp, (char *)&v263 + 8);
          v124 = (char *)&v263 + 8;
          if ( ActivityIdIrp < 0 )
            v124 = (char *)PostIrpRoutine;
          *(_QWORD *)&v263 = v124;
        }
        else
        {
          ActivityIdThread = (_QWORD *)IoGetActivityIdThread();
          if ( ActivityIdThread )
            goto LABEL_508;
          *(_QWORD *)&v263 = PostIrpRoutine;
        }
        goto LABEL_509;
      }
      goto LABEL_128;
    }
    if ( NtfsStatusDebugFlags && v218 - 298 > 1 && v218 != -1073741608 && v218 + 2147483643 > 1 )
      NtfsStatusTraceAndDebugInternal(v3, v218, 463950);
    NtfsRaiseStatusInternal(v3, v218, 0, 0, 463950);
  }
  if ( NtfsStatusDebugFlags && v218 - 298 > 1 && v218 != -1073741608 && v218 + 2147483643 > 1 )
    NtfsStatusTraceAndDebugInternal(v3, v218, 463782);
  ActivityIdThread = (_QWORD *)NtfsRaiseStatusInternal(v3, v218, 0, 0, 463782);
LABEL_508:
  *((_QWORD *)&v263 + 1) = *ActivityIdThread;
  v264 = ActivityIdThread[1];
  *(_QWORD *)&v263 = (char *)&v263 + 8;
LABEL_509:
  FsRtlHeatLogIo(v219 + 8200, Irp, &v265, 0, v263);
LABEL_128:
  if ( (v210 & 0x100) != 0 || (v210 & 0x4000) != 0 || (v210 & 0x10000000) != 0 )
  {
    if ( (v210 & 0x10000000) != 0 )
      v19 = Lcb;
    if ( (v210 & 0x100) != 0 || (*(_BYTE *)(*(_QWORD *)(v19 + 192) + 65LL) & 3) != 0 )
      *(_DWORD *)(*(_QWORD *)v215 + 4LL) &= ~0x20u;
  }
  if ( (v210 & 0x100) != 0 || (v210 & 0x4000) != 0 || (v210 & 0x400) != 0 || v210 < 0 || (v210 & 0x10000000) != 0 )
  {
    v86 = Irp;
    Irp->IoStatus.Information = PostIrpRoutine;
    if ( (v210 & 0x10000000) != 0 )
    {
      ExAcquireResourceSharedLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v215 + 328LL) + 136LL), 1u);
      v192 = *(_QWORD *)v215;
      if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)v215 + 328LL) + 4LL) & 0x200000) != 0 )
        v7 = v11;
      v261->IoStatus.Information = v7;
      ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(v192 + 328) + 136LL));
    }
    else if ( (v210 & 0x100) != 0 )
    {
      v86->IoStatus.Information = v11;
    }
    else if ( (v210 & 0x4000) != 0 )
    {
      Irp->IoStatus.Information = 8;
    }
    else if ( v210 < 0 )
    {
      Irp->IoStatus.Information = 36;
    }
    if ( (v210 & 0x400) != 0 )
      Irp->IoStatus.Information |= 0x10uLL;
  }
  v39 = FsContext;
  if ( *((_QWORD *)FsContext + 10) && ((v210 & 0x1000000) != 0 || (v210 & 0x4000000) != 0) )
  {
    --*(_DWORD *)(v250 + 32);
    v39 = FsContext;
  }
  if ( (v210 & 0x40000) != 0 && (v210 & 0x4000) == 0 && (*(_DWORD *)(v3 + 436) & 0x80008) == 0 )
  {
    NtfsUpdateLcbDuplicateInfo(*(_QWORD *)v215, v231);
    *(_DWORD *)(*(_QWORD *)v215 + 184LL) = PostIrpRoutine;
    v39 = FsContext;
  }
  if ( (*((_DWORD *)v39 + 1) & 8) != 0 )
  {
    v40 = 1;
  }
  else
  {
    v40 = (unsigned int)PostIrpRoutine;
    if ( v39[88] == 4 )
      v40 = 2;
  }
  NtfsRemoveShareAccess(FileObject, v40, v217, v250);
  if ( *((int *)FsContext + 1) >= 0 || (*((_DWORD *)FsContext + 2) & 2) != 0 )
    v41 = PostIrpRoutine;
  else
    v41 = 1;
  NtfsDecrementCleanupCounts(v3, v217, v250, FileObject->Flags & 8, v41);
  if ( (*((_DWORD *)FsContext + 2) & 0x80000) != 0 )
  {
    _InterlockedDecrement((volatile signed __int32 *)(v219 + 272));
    ClearFlagInterlocked((char *)FsContext + 8, 0x80000);
  }
  v238 = (_QWORD *)PostIrpRoutine;
  v224 = PostIrpRoutine;
  v43 = *((_QWORD *)FsContext + 10);
  if ( v43 )
  {
    if ( *(_DWORD *)(v43 + 36) )
    {
      ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v215 + 328LL) + 136LL), 1u);
      v232 = *(_QWORD *)(*(_QWORD *)v215 + 328LL);
      --*(_DWORD *)(*(_QWORD *)(*((_QWORD *)FsContext + 10) + 8LL) + 12LL);
      v193 = *(_QWORD *)(*((_QWORD *)FsContext + 10) + 8LL);
      if ( *(_DWORD *)(v193 + 12) || (*(_DWORD *)(v193 + 8) & 1) == 0 )
      {
        ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v215 + 328LL) + 136LL));
        v232 = PostIrpRoutine;
      }
      else
      {
        ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v215 + 328LL) + 136LL));
        v232 = PostIrpRoutine;
        if ( !CcPurgeCacheSection(
                (PSECTION_OBJECT_POINTERS)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)FsContext + 10) + 8LL) + 24LL) + 16LL),
                0,
                0,
                0) )
          MmForceSectionClosed(
            (PSECTION_OBJECT_POINTERS)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)FsContext + 10) + 8LL) + 24LL) + 16LL),
            1u);
      }
    }
    if ( (v210 & 0x2000000) != 0 || (v210 & 0x8000000) != 0 )
    {
      ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v215 + 328LL) + 136LL), 1u);
      --*(_WORD *)(*(_QWORD *)(*(_QWORD *)v215 + 328LL) + 144LL);
      --*(_DWORD *)(*(_QWORD *)(v217 + 528) + 36LL);
      ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v215 + 328LL) + 136LL));
    }
    v104 = *((_QWORD *)FsContext + 10);
    v105 = *(_DWORD *)(v104 + 4);
    if ( (v105 & 2) == 0 )
    {
      *(_DWORD *)(v104 + 4) = v105 | 8;
      v106 = *(_QWORD *)(v3 + 400);
      if ( v106 )
        _InterlockedDecrement((volatile signed __int32 *)(v106 + 448));
    }
  }
  if ( (v210 & 0x200) != 0 )
  {
    v107 = (SECTION_OBJECT_POINTERS *)(*(_QWORD *)(v217 + 288) + 16LL);
    if ( v107->DataSectionObject )
    {
      if ( !MmForceSectionClosed(v107, 1u) )
        BYTE1(v210) &= ~2u;
    }
  }
  if ( (*((_DWORD *)FsContext + 1) & 0x8000000) != 0 )
  {
    ClearFlagInterlocked((char *)FsContext + 4, 0x8000000);
    *(_DWORD *)(v217 + 512) &= ~2u;
  }
  if ( (*((_DWORD *)FsContext + 2) & 0x1000) != 0 )
  {
    ClearFlagInterlocked((char *)FsContext + 8, 4096);
    *(_DWORD *)(*(_QWORD *)v215 + 16LL) &= ~2u;
  }
  if ( (*((_DWORD *)FsContext + 2) & 0x400) != 0 )
  {
    ClearFlagInterlocked((char *)FsContext + 8, 1024);
    --*(_DWORD *)(v217 + 220);
  }
  if ( v230 != 4 && *(_QWORD *)(*(_QWORD *)v215 + 120LL) && (*(_DWORD *)(*(_QWORD *)v215 + 4LL) & 1) != 0 )
    NtfsDereferenceQuotaControlBlock(v219, *(_QWORD *)v215 + 120LL, 0);
  v44 = v218;
  if ( v218 )
  {
    if ( (*(_DWORD *)(v3 + 16) & 0x100000LL) == 0
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 1) != 0 )
    {
      McTemplateU0q_EtwWriteTransfer(&NtfsLog_Context, cleanup_c5778, v218);
    }
    *(_DWORD *)(v3 + 24) = PostIrpRoutine;
    NtfsRaiseStatusInternal(v3, 0, 0, 0, 464543);
  }
LABEL_958:
  if ( (_DWORD)v44 != 871 )
  {
    if ( (v210 & 0x200) != 0 && (*(_DWORD *)(*(_QWORD *)v215 + 4LL) & 0x40) != 0 )
    {
      v198 = 0;
      ExAcquirePushLockExclusiveEx(v219 + 656, 0);
      v199 = *(_QWORD *)v215;
      if ( (*(_DWORD *)(*(_QWORD *)v215 + 4LL) & 0x40) != 0 )
      {
        v200 = *(_QWORD *)(*(_QWORD *)v215 + 96LL);
        RtlAvlRemoveNode(v200 + 1344, *(_QWORD *)(*(_QWORD *)v215 + 104LL) + 256LL);
        --*(_DWORD *)(v200 + 1352);
        *(_DWORD *)(v199 + 4) &= ~0x40u;
        v198 = 1;
      }
      ExReleasePushLockEx(v219 + 656, 0);
      if ( v198 )
      {
        LOBYTE(v201) = 1;
        NtfsDereferenceMftView(*(_QWORD *)(*(_QWORD *)v215 + 96LL), *(_QWORD *)v215 + 8LL, v201);
      }
    }
    v195 = *((_QWORD *)FsContext + 10);
    if ( v195 )
      *(_DWORD *)(v195 + 4) &= ~0x40u;
    if ( v232 )
      ExReleaseResourceLite(*(PERESOURCE *)(v232 + 136));
    if ( (v210 & 0x1000) != 0 )
    {
      ExReleasePushLockEx(v219 + 656, 0);
      BYTE1(v210) &= ~0x10u;
    }
    if ( (v210 & 2) != 0 )
      NtfsReleaseFcbEx(v3, *(_QWORD *)(*(_QWORD *)(v219 + 160) + 184LL), 0);
    NtfsReleaseVcb(v3, v219);
    if ( (v210 & 1) != 0 )
    {
      NtfsReleaseCheckpointSynchronization(v3, v219, 18);
      LOBYTE(v210) = v210 & 0xFE;
    }
    if ( (v210 & 0x10) != 0 )
      NtfsCleanupAttributeContext(v3, v257);
    if ( (v210 & 0x20000) != 0 )
    {
      NtfsReleaseFcbEx(v3, *(_QWORD *)(v217 + 184), 0);
      FsRtlNotifyVolumeEvent(FileObject, 5u);
    }
    v44 = v218;
  }
  if ( (__int64 *)v262[3] != &v262[7] )
  {
    ExFreePoolWithTag((PVOID)v262[3], 0);
    v44 = v218;
  }
  if ( (v210 & 0x80u) != 0 )
  {
    _InterlockedDecrement((volatile signed __int32 *)(v243 + 212));
    v44 = v218;
  }
  if ( (v210 & 0x800) != 0 && (int)v44 >= 0 )
  {
    if ( (_DWORD)v44 != 871 )
    {
      if ( v230 != 4
        && (v210 & 0x80000) != 0
        && (v210 & 0x100000) == 0
        && ((v210 & 0x100) != 0
         || (v210 & 0x400) != 0
         || (v210 & 0x4000) != 0
         || (*((_WORD *)FsContext + 52) & 0x912) != 0) )
      {
        if ( NtfsStatusDebugFlags
          && (_DWORD)v44
          && (_DWORD)v44 != 294
          && (unsigned int)(v44 - 298) > 1
          && (unsigned int)(v44 + 2147483643) > 1
          && (_DWORD)v44 != 259 )
        {
          NtfsStatusTraceAndDebugInternal(v3, v44, 464898);
        }
        LOBYTE(v42) = 1;
        NtfsExtendedCompleteRequestInternal(v3, 0, v218, v42, 1);
        LOBYTE(v202) = (*(_DWORD *)(v219 + 24) & 0x100) != 0 ? 3 : 0;
        LOBYTE(v203) = 9;
        v204 = NtfsIoCallSelf(0, FileObject, v203, v202);
        if ( v204 != -1073741533 )
          LODWORD(PostIrpRoutine) = v204;
        if ( (int)PostIrpRoutine < 0 )
        {
          if ( (unsigned int)(PostIrpRoutine + 1073741662) > 1
            && (unsigned int)(PostIrpRoutine + 1073741806) > 2
            && (_DWORD)PostIrpRoutine != -2147483626
            && (_DWORD)PostIrpRoutine != -1073741643 )
          {
            LODWORD(PostIrpRoutine) = -1073700734;
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(0, 3221266562LL, 464935);
          }
          ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)v215 + 104LL) + 8LL));
          IoRaiseInformationalHardError(PostIrpRoutine, (PUNICODE_STRING)FsContext + 1, Irp->Tail.Overlay.Thread);
          ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)v215 + 104LL) + 8LL));
        }
        LODWORD(v44) = v218;
      }
      goto LABEL_964;
    }
  }
  else
  {
LABEL_964:
    if ( (_DWORD)v44 != 871 )
    {
      NtfsCompleteCleanupRequest(v3, Irp, (unsigned int)v44);
      LODWORD(v44) = v218;
    }
  }
  return (unsigned int)v44;
}

```

## disassembly

```asm
0x1401c3700  mov     r11, rsp
0x1401c3703  mov     [r11+18h], rbx
0x1401c3707  mov     [r11+20h], rsi
0x1401c370b  push    rdi
0x1401c370c  push    r12
0x1401c370e  push    r13
0x1401c3710  push    r14
0x1401c3712  push    r15
0x1401c3714  sub     rsp, 320h
0x1401c371b  mov     rax, cs:__security_cookie
0x1401c3722  xor     rax, rsp
0x1401c3725  mov     [rsp+348h+var_30], rax
0x1401c372d  mov     rdi, rdx
0x1401c3730  mov     rsi, rcx
0x1401c3733  mov     [r11-2A0h], rcx
0x1401c373a  mov     [r11-268h], rdx
0x1401c3741  xor     ebx, ebx
0x1401c3743  mov     [rsp+348h+var_2B8], ebx
0x1401c374a  mov     [rsp+348h+var_22C], ebx
0x1401c3751  mov     [r11-2B0h], rbx
0x1401c3758  mov     qword ptr [rsp+348h+var_2D0], rbx
0x1401c375d  mov     [r11-2C0h], rbx
0x1401c3764  mov     [r11-2A8h], rbx
0x1401c376b  mov     [r11-258h], rbx
0x1401c3772  mov     [r11-298h], rbx
0x1401c3779  xor     edx, edx; Val
0x1401c377b  mov     r8d, 58h ; 'X'; Size
0x1401c3781  lea     rcx, [r11-1A8h]; void *
0x1401c3788  call    memset
0x1401c378d  mov     [rsp+348h+var_140], rbx
0x1401c3795  mov     [rsp+348h+var_2C8], bl
0x1401c379c  xor     edx, edx; Val
0x1401c379e  mov     r8d, 0C0h; Size
0x1401c37a4  lea     rcx, [rsp+348h+var_118]; void *
0x1401c37ac  call    memset
0x1401c37b1  mov     [rsp+348h+var_2D8], rbx
0x1401c37b6  mov     byte ptr [rsp+348h+var_2D8], 0Ch
0x1401c37bb  and     byte ptr [rsp+348h+var_2D8+3], 0BFh
0x1401c37c0  mov     qword ptr [rdi+38h], 2
0x1401c37c8  lea     rax, [rsp+348h+var_F8]
0x1401c37d0  mov     [rsp+348h+var_110], rax
0x1401c37d8  lea     rax, [rsp+348h+var_E0]
0x1401c37e0  mov     [rsp+348h+P], rax
0x1401c37e8  mov     dword ptr [rsp+348h+var_118], 180000h
0x1401c37f3  mov     [rsp+348h+var_108], 340000h
0x1401c37fe  mov     rax, [rdi+0B8h]
0x1401c3805  mov     r15, [rax+30h]
0x1401c3809  mov     [rsp+348h+var_278], r15
0x1401c3811  mov     byte ptr [rsp+348h+var_318], bl
0x1401c3815  lea     rax, [rsp+348h+FsContext]
0x1401c381d  mov     [rsp+348h+PostIrpRoutine], rax
0x1401c3822  lea     rax, [rsp+348h+var_2C0]
0x1401c382a  mov     [rsp+348h+CompletionRoutine], rax
0x1401c382f  lea     r9, [rsp+348h+var_2D0]
0x1401c3834  lea     r8, [rsp+348h+var_2B0]
0x1401c383c  mov     rdx, r15
0x1401c383f  mov     rcx, rsi
0x1401c3842  call    NtfsDecodeFileObject
0x1401c3847  mov     [rsp+348h+var_260], eax
0x1401c384e  dec     eax
0x1401c3850  test    eax, 0FFFFFFFBh
0x1401c3855  jz      loc_1401C9A05
0x1401c385b  mov     [rsp+348h+var_128], rdi
0x1401c3863  mov     [rsp+348h+var_240], rbx
0x1401c386b  mov     [rsp+348h+var_250], rbx
0x1401c3873  mov     r13d, ebx
0x1401c3876  mov     [rsp+348h+var_1E8], rbx
0x1401c387e  mov     [rsp+348h+var_220], rbx
0x1401c3886  mov     [rsp+348h+var_218], rbx
0x1401c388e  mov     [rsp+348h+var_238], rbx
0x1401c3896  mov     [rsp+348h+TruncateSize], rbx
0x1401c389e  mov     rdx, [r15+28h]
0x1401c38a2  mov     rcx, [rsp+348h+var_2C0]
0x1401c38aa  mov     rax, [rcx+120h]
0x1401c38b1  add     rax, 10h
0x1401c38b5  cmp     rdx, rax
0x1401c38b8  jnz     loc_1401C9657
0x1401c38be  mov     rdx, [rsp+348h+FsContext]
0x1401c38c6  movzx   ecx, byte ptr [rdx+4]
0x1401c38ca  and     cl, 8
0x1401c38cd  shl     cl, 2
0x1401c38d0  movzx   eax, byte ptr [rsp+348h+var_2D8+1]
0x1401c38d5  and     al, 0DFh
0x1401c38d7  or      cl, al
0x1401c38d9  mov     byte ptr [rsp+348h+var_2D8+1], cl
0x1401c38dd  mov     eax, [rdx+64h]
0x1401c38e0  mov     [rsi+110h], eax
0x1401c38e6  mov     rcx, [rsp+348h+FsContext]
0x1401c38ee  cmp     [rcx+50h], rbx
0x1401c38f2  jnz     loc_1401C9867
0x1401c38f8  test    cs:dword_1400956B8, 10000000h
0x1401c3902  jnz     loc_1401C9867
0x1401c3908  mov     rdx, [rsp+348h+var_2B0]
0x1401c3910  cmp     [rsp+348h+var_260], 4
0x1401c3918  jz      loc_1401C9887
0x1401c391e  test    dword ptr [rsi+0Ch], 100h
0x1401c3925  jnz     loc_1401C98D6
0x1401c392b  mov     r8b, 1
0x1401c392e  mov     rcx, rsi
0x1401c3931  call    NtfsAcquireSharedVcb
0x1401c3936  mov     r12d, 200h
0x1401c393c  mov     rax, [rsp+348h+var_2B0]
0x1401c3944  mov     ecx, [rax+4]
0x1401c3947  and     ecx, 8000823h
0x1401c394d  cmp     ecx, 1
0x1401c3950  jz      loc_1401C963D
0x1401c3956  mov     rax, [rsp+348h+var_2B0]
0x1401c395e  test    dword ptr [rax+4], 2000020h
0x1401c3965  jnz     loc_1401C98E6
0x1401c396b  mov     rax, qword ptr [rsp+348h+var_2D0]
0x1401c3970  mov     ecx, [rax+4]
0x1401c3973  bt      ecx, 1Bh
0x1401c3977  jb      loc_1401C98E6
0x1401c397d  mov     rax, [rsp+348h+var_2B0]
0x1401c3985  test    dword ptr [rax+4], 4000000h
0x1401c398c  jnz     loc_1401C98F0
0x1401c3992  mov     rdi, qword ptr [rsp+348h+var_2D0]
0x1401c3997  mov     rcx, rsi
0x1401c399a  cmp     qword ptr [rdi+70h], 0
0x1401c399f  jz      loc_1401C64FC
0x1401c39a5  mov     r8b, 1
0x1401c39a8  mov     rdx, rdi
0x1401c39ab  call    NtfsAcquirePagingResourceExclusive
0x1401c39b0  test    al, al
0x1401c39b2  jz      short loc_1401C39E0
0x1401c39b4  mov     [rsp+348h+var_1F8], ebx
0x1401c39bb  mov     ecx, ebx
0x1401c39bd  mov     [rsp+348h+var_1F8], ebx
0x1401c39c4  cmp     ecx, 2
0x1401c39c7  jnb     short loc_1401C39E0
0x1401c39c9  mov     eax, ecx
0x1401c39cb  lea     rdx, [rsi+rax*8]
0x1401c39cf  mov     rax, [rdx+30h]
0x1401c39d3  test    rax, rax
0x1401c39d6  jnz     loc_1401C5358
0x1401c39dc  mov     [rdx+30h], rdi
0x1401c39e0  mov     r9d, 8
0x1401c39e6  mov     rdx, [rsp+348h+var_2C0]
0x1401c39ee  mov     r8, rdx
0x1401c39f1  mov     rdx, [rdx+0B8h]
0x1401c39f8  mov     rcx, rsi
0x1401c39fb  call    NtfsAcquireExclusiveFcb
0x1401c3a00  mov     rcx, [rsp+348h+FsContext]
0x1401c3a08  add     rcx, 8
0x1401c3a0c  test    dword ptr [rcx], 100h
0x1401c3a12  jnz     loc_1401C6970
0x1401c3a18  mov     rax, [rsp+348h+FsContext]
0x1401c3a20  test    dword ptr [rax+8], 8000h
0x1401c3a27  jnz     loc_1401C698D
0x1401c3a2d  lea     rdi, [r15+50h]
0x1401c3a31  mov     qword ptr [rsp+348h+var_1C0], rdi
0x1401c3a39  test    dword ptr [rdi], 800000h
0x1401c3a3f  jnz     loc_1401C69B6
0x1401c3a45  mov     rdx, [rsp+348h+FsContext]
0x1401c3a4d  mov     r14, [rdx+48h]
0x1401c3a51  mov     [rsp+348h+var_288], r14
0x1401c3a59  mov     [rsp+348h+var_1F0], r14
0x1401c3a61  mov     [rsp+348h+var_258], r14
0x1401c3a69  test    r14, r14
0x1401c3a6c  jz      short loc_1401C3A9A
0x1401c3a6e  mov     eax, [r14+4]
0x1401c3a72  test    al, 2
0x1401c3a74  jnz     loc_1401C69C6
0x1401c3a7a  mov     rax, [r14+18h]
0x1401c3a7e  mov     [rsp+348h+var_298], rax
0x1401c3a86  test    rax, rax
0x1401c3a89  jz      short loc_1401C3A9A
0x1401c3a8b  mov     rax, [rax+0B8h]
0x1401c3a92  mov     [rsp+348h+var_240], rax
0x1401c3a9a  mov     rdx, [rsp+348h+FsContext]
0x1401c3aa2  test    dword ptr [rdx+4], 100h
0x1401c3aa9  jnz     loc_1401C56C9
0x1401c3aaf  mov     rax, [rsp+348h+FsContext]
0x1401c3ab7  test    [rax+8], r12d
0x1401c3abb  jnz     loc_1401C69EC
0x1401c3ac1  test    byte ptr [rsp+348h+var_2D8+2], 8
0x1401c3ac6  jz      loc_1401C3B9C
0x1401c3acc  mov     rax, [rsp+348h+FsContext]
0x1401c3ad4  mov     rcx, [rax+50h]
0x1401c3ad8  test    rcx, rcx
0x1401c3adb  jnz     loc_1401C6B08
0x1401c3ae1  mov     r12d, 2
0x1401c3ae7  mov     r13d, 703h
0x1401c3aed  test    byte ptr [rsp+348h+var_2D8+2], 10h
0x1401c3af2  jnz     loc_1401C3BA2
0x1401c3af8  mov     rcx, qword ptr [rsp+348h+var_2D0]
0x1401c3afd  call    NtfsIsFileStillValid
0x1401c3b02  test    al, al
0x1401c3b04  jz      loc_1401C3BA2
0x1401c3b0a  mov     rax, [rsp+348h+FsContext]
0x1401c3b12  mov     ecx, [rax+4]
0x1401c3b15  bt      ecx, 12h
0x1401c3b19  jb      loc_1401C5F22
0x1401c3b1f  mov     r12d, 705h
0x1401c3b25  test    byte ptr [rsp+348h+var_2D8+2], 20h
0x1401c3b2a  jnz     loc_1401C4295
0x1401c3b30  mov     rdi, 30003300490024h
0x1401c3b3a  mov     rcx, qword ptr [rsp+348h+var_2D0]
0x1401c3b3f  cmp     word ptr [rcx+0BCh], 0
0x1401c3b47  jz      loc_1401C5805
0x1401c3b4d  mov     r9, [rsp+348h+var_2C0]
0x1401c3b55  mov     eax, [r9+0C8h]
0x1401c3b5c  test    al, 2
0x1401c3b5e  jz      short loc_1401C3BB2
0x1401c3b60  mov     rax, [rcx+148h]
0x1401c3b67  test    rax, rax
0x1401c3b6a  jz      loc_1401C79E9
0x1401c3b70  mov     eax, [rax+4]
0x1401c3b73  test    al, 1
0x1401c3b75  jz      loc_1401C79E9
0x1401c3b7b  movzx   eax, byte ptr [rsp+348h+var_2D8+3]
0x1401c3b80  test    al, 10h
0x1401c3b82  jnz     short loc_1401C3BB2
0x1401c3b84  test    al, 2
0x1401c3b86  jz      short loc_1401C3BB2
0x1401c3b88  mov     rax, [r9+210h]
0x1401c3b8f  cmp     dword ptr [rax+24h], 1
0x1401c3b93  jnz     short loc_1401C3BB2
0x1401c3b95  or      byte ptr [rsp+348h+var_2D8+1], 4
0x1401c3b9a  jmp     short loc_1401C3BB2
0x1401c3b9c  mov     r13d, 703h
0x1401c3ba2  mov     rdi, 30003300490024h
0x1401c3bac  mov     r12d, 705h
0x1401c3bb2  mov     r9d, 400h
0x1401c3bb8  mov     ecx, [rsp+348h+var_260]
0x1401c3bbf  cmp     ecx, 2
0x1401c3bc2  jz      loc_1401C3CD8
0x1401c3bc8  sub     ecx, 3
0x1401c3bcb  jnz     loc_1401C44C5
0x1401c3bd1  mov     rdx, [rsp+348h+var_2C0]
0x1401c3bd9  mov     rcx, rsi
0x1401c3bdc  call    NtfsSnapshotScb
0x1401c3be1  mov     rdx, [rsp+348h+var_2C0]
0x1401c3be9  mov     eax, [rdx+100h]
0x1401c3bef  cmp     eax, 80h
0x1401c3bf4  jz      loc_1401C7E66
0x1401c3bfa  cmp     eax, 0A0h
0x1401c3bff  jz      loc_1401C4790
0x1401c3c05  mov     r8b, 1
0x1401c3c08  mov     rcx, r15
0x1401c3c0b  call    NtfsUpdateScbFromFileObject
0x1401c3c10  mov     eax, [r15+50h]
0x1401c3c14  bts     eax, 0Eh
0x1401c3c18  mov     [r15+50h], eax
0x1401c3c1c  mov     r8, [rsp+348h+FsContext]; FsContext
0x1401c3c24  test    dword ptr [r8+4], 800000h
0x1401c3c2c  jnz     loc_1401C7E75
0x1401c3c32  movzx   eax, byte ptr [rsp+348h+var_2D8+2]
0x1401c3c37  test    al, 8
0x1401c3c39  jz      loc_1401C3F11
0x1401c3c3f  test    al, 10h
0x1401c3c41  jnz     loc_1401C3F11
0x1401c3c47  mov     rax, [rsp+348h+var_2C0]
0x1401c3c4f  cmp     [rax], r13w
0x1401c3c53  jnz     loc_1401C3F11
0x1401c3c59  mov     rcx, qword ptr [rsp+348h+var_2D0]
0x1401c3c5e  call    NtfsIsFileStillValid
0x1401c3c63  test    al, al
0x1401c3c65  jz      loc_1401C3F11
0x1401c3c6b  test    byte ptr [rsp+348h+var_2D8+1], 1
0x1401c3c70  jnz     loc_1401C58AA
0x1401c3c76  test    r14, r14
0x1401c3c79  jnz     loc_1401C4570
0x1401c3c7f  mov     rdx, qword ptr [rsp+348h+var_2D0]
0x1401c3c84  cmp     dword ptr [rdx+18h], 1
0x1401c3c88  jz      loc_1401C536F
0x1401c3c8e  test    byte ptr [rsp+348h+var_2D8+1], 1
0x1401c3c93  jnz     short loc_1401C3CA0
0x1401c3c95  test    byte ptr [rsp+348h+var_2D8+3], 80h
0x1401c3c9a  jz      loc_1401C3F11
0x1401c3ca0  mov     rcx, [rsp+348h+var_298]
0x1401c3ca8  add     rcx, 58h ; 'X'; Oplock
0x1401c3cac  mov     [rsp+348h+PostIrpRoutine], rbx; PostIrpRoutine
0x1401c3cb1  mov     [rsp+348h+CompletionRoutine], rbx; CompletionRoutine
0x1401c3cb6  xor     r9d, r9d; Context
0x1401c3cb9  mov     r8d, 50h ; 'P'; Flags
0x1401c3cbf  mov     rdx, [rsp+348h+Irp]; Irp
0x1401c3cc7  call    cs:__imp_FsRtlCheckOplockEx
0x1401c3cce  nop     dword ptr [rax+rax+00h]
0x1401c3cd3  jmp     loc_1401C3F11
0x1401c3cd8  mov     r9, [rsp+348h+var_2C0]
0x1401c3ce0  mov     eax, [r9+0C8h]
0x1401c3ce7  test    al, 20h
0x1401c3ce9  jz      loc_1401C7FEF
0x1401c3cef  mov     rax, [rsp+348h+FsContext]
0x1401c3cf7  mov     [rsp+348h+PostIrpRoutine], rax
0x1401c3cfc  mov     rax, [rsp+348h+var_2C0]
0x1401c3d04  mov     [rsp+348h+CompletionRoutine], rax
0x1401c3d09  mov     r9, [rsp+348h+var_2B0]
0x1401c3d11  mov     r8, r15
0x1401c3d14  mov     rdx, [rsp+348h+Irp]
0x1401c3d1c  mov     rcx, rsi
0x1401c3d1f  call    NtfsClearSfioReservation
0x1401c3d24  mov     rdx, [rsp+348h+var_2C0]
0x1401c3d2c  mov     rcx, rsi
0x1401c3d2f  call    NtfsSnapshotScb
0x1401c3d34  mov     rdx, [rsp+348h+var_2C0]
0x1401c3d3c  mov     eax, [rdx+100h]
0x1401c3d42  cmp     eax, 80h
0x1401c3d47  jz      loc_1401C4980
  ... truncated ...
```
