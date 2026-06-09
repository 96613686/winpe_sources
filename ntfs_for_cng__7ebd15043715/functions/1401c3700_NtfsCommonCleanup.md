# NtfsCommonCleanup

- ea: `0x1401c3700`
- end: `0x1401c9a35`
- name: `NtfsCommonCleanup`
- size: `25397`
- prototype: `__int64 __fastcall(CLFS_LSN *, IRP *)`
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
__int64 __fastcall NtfsCommonCleanup(CLFS_LSN *a1, IRP *a2)
{
  CLFS_LSN *v3; // rsi
  NTSTATUS v4; // ebx
  struct _FILE_OBJECT *FileObject; // r15
  __int64 v6; // r8
  volatile signed __int32 *v7; // r13
  PSECTION_OBJECT_POINTERS SectionObjectPointer; // rdx
  __int64 v9; // rdx
  CLFS_LSN v10; // rdi
  unsigned int v11; // ecx
  CLFS_LSN *v12; // rdx
  CLFS_LSN v13; // rax
  ULONG *p_Flags; // rdi
  _QWORD *v15; // r14
  __int64 v16; // rax
  __int64 v17; // rcx
  int v18; // ecx
  __int64 v19; // rax
  __int64 v20; // rdx
  int v21; // eax
  __int64 v22; // rdx
  int v23; // eax
  char v24; // al
  int v25; // r9d
  int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // r13
  _BYTE *v32; // rcx
  __int64 v33; // rdx
  BOOL v34; // eax
  __int64 v35; // rcx
  unsigned int v36; // edx
  int v37; // eax
  unsigned int v38; // eax
  int v39; // edi
  __int64 v40; // rdx
  __int64 v41; // rcx
  int v42; // eax
  int v43; // r10d
  __int64 v44; // rcx
  FILE_LOCK *v45; // rdi
  struct _KPROCESS *RequestorProcess; // rax
  int v47; // edx
  __int64 v48; // rcx
  int v49; // eax
  BOOLEAN IsFastIoPossible; // al
  __int64 v51; // rax
  __int64 v52; // rcx
  char v53; // dl
  __int64 v54; // r9
  __int64 v55; // rcx
  int v56; // eax
  __int64 v57; // rdi
  __int64 v58; // rcx
  char updated; // al
  char v60; // cl
  int v61; // ecx
  int v62; // r8d
  int v63; // eax
  int v64; // r8d
  __int64 v65; // rcx
  __int64 v66; // r8
  char v67; // al
  BOOL v68; // eax
  __int64 v69; // rdi
  int v70; // ecx
  __int64 v71; // r8
  __int16 *v72; // rdx
  char v73; // al
  __int64 v74; // rdx
  __int64 v75; // rcx
  _QWORD *ActivityIdThread; // rax
  PIRP v77; // rax
  _QWORD *v78; // rax
  __int64 v79; // r13
  __int64 v80; // r8
  __int64 v81; // rdx
  __int64 v82; // r12
  CLFS_CONTAINER_ID cidContainer; // eax
  __int64 v84; // r8
  __int64 v85; // r8
  __int64 v86; // rdi
  int v87; // ecx
  __int64 v88; // r8
  __int16 *v89; // rdx
  char v90; // al
  int v91; // eax
  __int64 v92; // rcx
  int v93; // eax
  __int64 v94; // rcx
  __int64 v95; // rcx
  int v96; // eax
  CLFS_LSN v97; // rax
  SECTION_OBJECT_POINTERS *v98; // rcx
  __int64 v99; // rdx
  __int64 v100; // rcx
  int v101; // eax
  __int64 v102; // rdi
  unsigned int v103; // ecx
  CLFS_LSN *v104; // rdx
  CLFS_LSN v105; // rax
  int v106; // r8d
  int v107; // r9d
  _QWORD *v108; // rdx
  _QWORD *v109; // rdx
  int v110; // r12d
  __int64 v111; // r8
  int ActivityIdIrp; // eax
  char *v113; // rcx
  unsigned int v114; // r12d
  _QWORD *NextChildScb; // rax
  _QWORD *v116; // rcx
  __int64 v117; // rax
  __int64 v118; // r12
  int v119; // ecx
  __int64 v120; // r8
  __int16 *Scb; // rdx
  unsigned int *v122; // rcx
  unsigned int *v123; // rcx
  _QWORD *v124; // rax
  unsigned int v125; // ecx
  char v126; // dl
  int v127; // r12d
  __int64 v128; // r10
  __int64 v129; // rcx
  __int64 *v130; // rax
  _QWORD *v131; // rdi
  int v132; // eax
  int v133; // eax
  __int64 v134; // rcx
  __int64 v135; // rax
  char v136; // di
  __int64 v137; // rdi
  __int64 v138; // rdx
  int v139; // eax
  unsigned int *MatchingLcbPair; // rax
  unsigned int *v141; // rcx
  volatile signed __int32 *v142; // rax
  volatile signed __int32 *v143; // rdi
  __int64 v144; // rcx
  unsigned int *v145; // rcx
  __int64 v146; // rdi
  __int64 v147; // rcx
  __int64 v148; // rax
  __int64 v149; // rcx
  __int64 v150; // rax
  _QWORD *NextParentLcb; // rax
  _QWORD *v152; // rax
  _QWORD *i; // rcx
  _QWORD *v154; // rax
  __int16 v155; // di
  char v156; // al
  _DWORD *v157; // rax
  int v158; // r8d
  int v159; // r8d
  __int64 v160; // rcx
  int v161; // r8d
  signed __int64 v162; // rdx
  int v163; // r8d
  signed __int64 v164; // r10
  signed __int64 v165; // r9
  __int64 v166; // rcx
  int v167; // edx
  __int64 v168; // r8
  char v169; // di
  __int64 v170; // rax
  __int64 v171; // rcx
  int v172; // edx
  __int64 v173; // rax
  __int64 v174; // rcx
  __int64 v175; // rdx
  __int64 v176; // rdx
  __int64 v177; // rax
  __int64 v179; // rcx
  __int64 v180; // rax
  _QWORD *v181; // rax
  char v182; // di
  __int64 v183; // r14
  __int64 v184; // rdi
  __int64 v185; // r8
  __int64 v186; // r8
  NTSTATUS v187; // eax
  POPLOCK_WAIT_COMPLETE_ROUTINE CompletionRoutine; // [rsp+20h] [rbp-328h]
  POPLOCK_WAIT_COMPLETE_ROUTINE CompletionRoutinea; // [rsp+20h] [rbp-328h]
  POPLOCK_WAIT_COMPLETE_ROUTINE CompletionRoutineb; // [rsp+20h] [rbp-328h]
  POPLOCK_WAIT_COMPLETE_ROUTINE CompletionRoutinec; // [rsp+20h] [rbp-328h]
  POPLOCK_WAIT_COMPLETE_ROUTINE CompletionRoutined; // [rsp+20h] [rbp-328h]
  size_t Size; // [rsp+38h] [rbp-310h]
  int v194; // [rsp+70h] [rbp-2D8h]
  char v195; // [rsp+70h] [rbp-2D8h]
  char v196; // [rsp+70h] [rbp-2D8h]
  char v197; // [rsp+70h] [rbp-2D8h]
  char v198; // [rsp+70h] [rbp-2D8h]
  char v199; // [rsp+70h] [rbp-2D8h]
  int v200[2]; // [rsp+78h] [rbp-2D0h] BYREF
  char v201[8]; // [rsp+80h] [rbp-2C8h] BYREF
  _QWORD *v202; // [rsp+88h] [rbp-2C0h] BYREF
  unsigned int v203; // [rsp+90h] [rbp-2B8h]
  __int64 v204; // [rsp+98h] [rbp-2B0h] BYREF
  PVOID FsContext; // [rsp+A0h] [rbp-2A8h] BYREF
  CLFS_LSN *v206; // [rsp+A8h] [rbp-2A0h]
  __int64 v207; // [rsp+B0h] [rbp-298h] BYREF
  char v208; // [rsp+B8h] [rbp-290h]
  _QWORD *v209; // [rsp+C0h] [rbp-288h]
  char v210; // [rsp+C8h] [rbp-280h]
  struct _FILE_OBJECT *v211; // [rsp+D0h] [rbp-278h]
  char v212; // [rsp+D8h] [rbp-270h]
  char v213; // [rsp+D9h] [rbp-26Fh]
  PIRP Irp; // [rsp+E0h] [rbp-268h]
  int v215; // [rsp+E8h] [rbp-260h]
  _QWORD *v216; // [rsp+F0h] [rbp-258h] BYREF
  __int64 v217; // [rsp+F8h] [rbp-250h]
  char v218; // [rsp+100h] [rbp-248h]
  char v219; // [rsp+101h] [rbp-247h]
  char v220; // [rsp+102h] [rbp-246h]
  char v221; // [rsp+103h] [rbp-245h]
  __int64 Fcb; // [rsp+108h] [rbp-240h]
  _QWORD *v223; // [rsp+110h] [rbp-238h]
  int v224; // [rsp+118h] [rbp-230h]
  int v225; // [rsp+11Ch] [rbp-22Ch]
  unsigned int v226; // [rsp+120h] [rbp-228h]
  _QWORD *Lcb; // [rsp+128h] [rbp-220h]
  volatile signed __int32 *v228; // [rsp+130h] [rbp-218h]
  PLARGE_INTEGER TruncateSize; // [rsp+138h] [rbp-210h]
  int v230; // [rsp+140h] [rbp-208h]
  int v231; // [rsp+144h] [rbp-204h]
  int v232; // [rsp+148h] [rbp-200h]
  unsigned int v233; // [rsp+14Ch] [rbp-1FCh]
  unsigned int v234; // [rsp+150h] [rbp-1F8h]
  _QWORD *v235; // [rsp+158h] [rbp-1F0h]
  __int64 v236; // [rsp+160h] [rbp-1E8h]
  __int128 v237; // [rsp+168h] [rbp-1E0h] BYREF
  unsigned int v238; // [rsp+178h] [rbp-1D0h]
  unsigned int v239; // [rsp+17Ch] [rbp-1CCh]
  __int64 v240; // [rsp+180h] [rbp-1C8h]
  __int128 v241; // [rsp+188h] [rbp-1C0h] BYREF
  __int64 v242[12]; // [rsp+1A0h] [rbp-1A8h] BYREF
  __int64 v243; // [rsp+200h] [rbp-148h] BYREF
  __int64 v244; // [rsp+208h] [rbp-140h] BYREF
  __int128 v245; // [rsp+210h] [rbp-138h] BYREF
  IRP *v246; // [rsp+220h] [rbp-128h]
  __int64 v247[24]; // [rsp+230h] [rbp-118h] BYREF
  __int128 v248; // [rsp+2F0h] [rbp-58h] BYREF
  __int64 v249; // [rsp+300h] [rbp-48h]
  __int128 v250; // [rsp+308h] [rbp-40h] BYREF

  v3 = a1;
  v206 = a1;
  Irp = a2;
  v4 = 0;
  v203 = 0;
  v225 = 0;
  v204 = 0;
  *(_QWORD *)v200 = 0;
  v202 = 0;
  FsContext = 0;
  v216 = 0;
  v207 = 0;
  memset(v242, 0, 0x58u);
  v244 = 0;
  v201[0] = 0;
  memset(v247, 0, sizeof(v247));
  v194 = 12;
  a2->IoStatus.Information = 2;
  v247[1] = (__int64)&v247[4];
  v247[3] = (__int64)&v247[7];
  LODWORD(v247[0]) = 1572864;
  LODWORD(v247[2]) = 3407872;
  FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  v211 = FileObject;
  v215 = NtfsDecodeFileObject((__int64)v3, (__int64)FileObject, &v204, v200, &v202, &FsContext, 0);
  if ( ((v215 - 1) & 0xFFFFFFFB) != 0 )
  {
    v246 = a2;
    Fcb = 0;
    v217 = 0;
    v7 = 0;
    v236 = 0;
    Lcb = 0;
    v228 = 0;
    v223 = 0;
    TruncateSize = 0;
    SectionObjectPointer = FileObject->SectionObjectPointer;
    if ( SectionObjectPointer != (PSECTION_OBJECT_POINTERS)(v202[36] + 16LL)
      && *((_DWORD *)v202 + 64) == 128
      && (SectionObjectPointer[1].ImageSectionObject
       || (v180 = v202[66]) != 0
       && (v181 = *(_QWORD **)(v180 + 112)) != 0
       && SectionObjectPointer == (PSECTION_OBJECT_POINTERS)(*v181 + 16LL)) )
    {
      BYTE2(v194) = 64;
    }
    BYTE1(v194) = 4 * (*((_BYTE *)FsContext + 4) & 8);
    v3[34].offset.idxRecord = *((_DWORD *)FsContext + 25);
    if ( *((_QWORD *)FsContext + 10) || (dword_1400956B8 & 0x10000000) != 0 )
    {
      LOBYTE(v194) = 8;
      if ( *((_QWORD *)FsContext + 10) )
        LOBYTE(v194) = 0;
    }
    v9 = v204;
    if ( v215 == 4 )
    {
      if ( (*(_DWORD *)(v204 + 4) & 2) != 0
        && (struct _FILE_OBJECT *)(*(_QWORD *)(v204 + 1472) & 0xFFFFFFFFFFFFFFFEuLL) == FileObject )
      {
        if ( (v3[1].offset.cidContainer & 0x200) != 0 )
        {
          NtfsAcquireCheckpointSynchronization((__int64)v3, v204, 82);
          LOBYTE(v194) = v194 | 1;
          v9 = v204;
        }
        LOBYTE(v6) = 1;
        NtfsAcquireExclusiveVcb(v3, v9, v6);
LABEL_8:
        if ( (*(_DWORD *)(v204 + 4) & 0x8000823) == 1 && (*(_DWORD *)(*(_QWORD *)v200 + 4LL) & 0x80u) == 0 )
          BYTE2(v194) |= 8u;
        if ( (*(_DWORD *)(v204 + 4) & 0x2000020) != 0 || (*(_DWORD *)(*(_QWORD *)v200 + 4LL) & 0x8000000) != 0 )
          BYTE2(v194) |= 0x10u;
        if ( (*(_DWORD *)(v204 + 4) & 0x4000000) != 0 )
          BYTE1(v194) |= 8u;
        v10 = *(CLFS_LSN *)v200;
        if ( *(_QWORD *)(*(_QWORD *)v200 + 112LL) )
        {
          if ( NtfsAcquirePagingResourceExclusive((__int64)v3, *(__int64 *)v200, 1u) )
          {
            v11 = 0;
            v234 = 0;
            while ( v11 < 2 )
            {
              v12 = &v3[v11];
              v13 = v12[6];
              if ( !v13.ullOffset || v13.ullOffset == v10.ullOffset )
              {
                v12[6] = v10;
                break;
              }
              v234 = ++v11;
            }
          }
        }
        else
        {
          NtfsAcquireExclusiveFcb((__int64)v3, v202[23], (__int64)v202, 8);
          if ( !*(_QWORD *)(*(_QWORD *)v200 + 112LL) )
          {
LABEL_20:
            if ( (*((_DWORD *)FsContext + 2) & 0x100) != 0 )
            {
              ClearFlagInterlocked((unsigned int *)FsContext + 2, 256);
              --*((_DWORD *)v202 + 112);
            }
            if ( (*((_DWORD *)FsContext + 2) & 0x8000) != 0 )
            {
              --*((_DWORD *)v202 + 136);
              ClearFlagInterlocked((unsigned int *)FsContext + 2, 0x8000);
            }
            p_Flags = &FileObject->Flags;
            *(_QWORD *)&v241 = &FileObject->Flags;
            if ( (FileObject->Flags & 0x800000) != 0 )
              NtfsBypassIoDisableCore(v3, FileObject);
            v15 = (_QWORD *)*((_QWORD *)FsContext + 9);
            v209 = v15;
            v235 = v15;
            v216 = v15;
            if ( v15 )
            {
              if ( (*((_DWORD *)v15 + 1) & 2) != 0 )
              {
                v15 = 0;
                v209 = 0;
                v216 = 0;
                ClearFlagInterlocked((unsigned int *)FsContext + 1, 0x40000);
              }
              else
              {
                v16 = v15[3];
                v207 = v16;
                if ( v16 )
                  Fcb = *(_QWORD *)(v16 + 184);
              }
            }
            if ( (*((_DWORD *)FsContext + 1) & 0x100) != 0 && v215 == 2 )
              TxfUnmarkObjectAsClfsLog(v202);
            if ( (*((_DWORD *)FsContext + 2) & 0x200) != 0 )
            {
              v114 = 0;
              v238 = 0;
              v232 = 0;
              v226 = 0;
              v231 = 0;
              *(_QWORD *)&v237 = 0;
              *(_DWORD *)(*(_QWORD *)v200 + 4LL) &= ~0x40000000u;
              ClearFlagInterlocked((unsigned int *)FsContext + 2, 512);
              _InterlockedDecrement((volatile signed __int32 *)(v204 + 276));
              while ( 1 )
              {
                NextChildScb = NtfsGetNextChildScb(*(__int64 *)v200, v237, 1);
                *(_QWORD *)&v237 = NextChildScb;
                if ( !NextChildScb )
                  break;
                v106 = 0;
                v232 = 0;
                v107 = 0;
                v231 = 0;
                v108 = (_QWORD *)NextChildScb[60];
                if ( v108 == NextChildScb + 60 )
                  v109 = 0;
                else
                  v109 = v108 - 5;
                while ( v109 )
                {
                  if ( (v109[1] & 4) == 0 )
                    v232 = --v106;
                  if ( (*((_DWORD *)v109 + 1) & 0x80000) == 0 && !*(_WORD *)(v109[14] + 75LL) )
                    v231 = ++v107;
                  v116 = (_QWORD *)v109[5];
                  v109 = 0;
                  if ( NextChildScb + 60 != v116 )
                    v109 = v116 - 5;
                }
                v114 += v106;
                v238 = v114;
                v226 += v107;
              }
              _InterlockedAdd((volatile signed __int32 *)(v204 + 268), v114);
              _InterlockedAdd((volatile signed __int32 *)(v204 + 264), v226);
            }
            if ( (v194 & 0x80000) == 0 )
              goto LABEL_46;
            v17 = *((_QWORD *)FsContext + 10);
            if ( v17 && (*(_DWORD *)(v17 + 4) & 2) == 0 )
            {
              v203 = TxfSetupTransactionContextFromCcb(
                       (__int64)v3,
                       (__int64)FileObject,
                       *(_DWORD *)(v17 + 36) == 0,
                       1,
                       0);
              if ( (v203 & 0x80000000) != 0 )
              {
                v216 = 0;
                HIBYTE(v194) = 32;
                ClearFlagInterlocked((unsigned int *)FsContext + 1, 0x40000);
                if ( !*(_DWORD *)(*((_QWORD *)FsContext + 10) + 36LL) )
                {
                  v137 = *(_QWORD *)(*(_QWORD *)v200 + 328LL);
                  ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v137 + 136), 1u);
                  v217 = v137;
                  v138 = *(_QWORD *)(v137 + 24);
                  if ( v138
                    && *(_QWORD *)(v138 + 232) == *(_QWORD *)(*((_QWORD *)FsContext + 10) + 56LL)
                    && (*(_DWORD *)(v137 + 4) & 0x2000000) == 0 )
                  {
                    HIBYTE(v194) = 40;
                    if ( v15 )
                    {
                      v139 = *((_DWORD *)v15 + 1);
                      if ( (v139 & 2) == 0 )
                      {
                        if ( (v139 & 1) != 0
                          || (*(_BYTE *)(v15[24] + 65LL) & 3) != 0 && (*(_DWORD *)(v15[6] + 4LL) & 0x20) != 0 )
                        {
                          MatchingLcbPair = (unsigned int *)NtfsFindMatchingLcbPair(v15);
                          ++*(_WORD *)(*(_QWORD *)v200 + 188LL);
                          ++*(_DWORD *)(v137 + 20);
                          if ( MatchingLcbPair )
                            ClearFlagInterlocked(MatchingLcbPair + 1, 1);
                          ClearFlagInterlocked((unsigned int *)v15 + 1, 1);
                          if ( (*(_BYTE *)(v15[24] + 65LL) & 3) != 0 )
                            *(_DWORD *)(*(_QWORD *)v200 + 4LL) &= ~0x20u;
                        }
                        if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)v200 + 328LL) + 4LL) & 0x800) == 0 )
                          HIBYTE(v194) = 44;
                      }
                    }
                    v15 = 0;
                    v209 = 0;
                  }
                  ExReleaseResourceLite(*(PERESOURCE *)(v137 + 136));
                  v217 = 0;
                }
                v203 = 0;
                v217 = 0;
              }
              else if ( !*(_DWORD *)(*((_QWORD *)FsContext + 10) + 36LL) )
              {
                HIBYTE(v194) = 2;
                ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v200 + 328LL) + 136LL), 1u);
                v117 = *(_QWORD *)(*(_QWORD *)v200 + 328LL);
                v217 = v117;
                if ( v235 )
                {
                  if ( (*((_DWORD *)v235 + 1) & 2) != 0 )
                  {
                    Lcb = v235;
                    HIBYTE(v194) = 3;
                  }
                  else
                  {
                    Lcb = v15;
                    if ( (*((_DWORD *)FsContext + 1) & 0x40002) == 0x40002 )
                    {
                      v218 = 0;
                      v221 = 0;
                      if ( (*((_DWORD *)v15 + 1) & 1) != 0
                        || (*(_BYTE *)(v15[24] + 65LL) & 3) != 0 && (*(_DWORD *)(v15[6] + 4LL) & 0x20) != 0 )
                      {
                        v123 = (unsigned int *)((char *)FsContext + 8);
                        if ( (*((_DWORD *)FsContext + 2) & 0x20000) != 0 )
                          SetFlagInterlocked(v123, 0x10000u);
                        else
                          ClearFlagInterlocked(v123, 0x10000);
                      }
                      else if ( (*(_DWORD *)(*(_QWORD *)v200 + 176LL) & 0x10000000) == 0
                             || (unsigned __int8)NtfsIsLinkDeleteable((_DWORD)v3, v200[0]) )
                      {
                        --*(_WORD *)(*(_QWORD *)v200 + 188LL);
                        SetFlagInterlocked((unsigned int *)v15 + 1, 1u);
                        v122 = (unsigned int *)((char *)FsContext + 8);
                        if ( (*((_DWORD *)FsContext + 2) & 0x20000) != 0 )
                          SetFlagInterlocked(v122, 0x10000u);
                        else
                          ClearFlagInterlocked(v122, 0x10000);
                        BYTE2(v194) |= 0x20u;
                        --*(_DWORD *)(*(_QWORD *)(*(_QWORD *)v200 + 328LL) + 20LL);
                        if ( (*(_BYTE *)(v15[24] + 65LL) & 3) != 0 )
                          *(_DWORD *)(*(_QWORD *)v200 + 4LL) |= 0x20u;
                      }
                    }
                    HIBYTE(v194) = 19;
                    if ( (*((_DWORD *)v15 + 1) & 1) == 0
                      && ((*(_BYTE *)(v15[24] + 65LL) & 3) == 0 || (*(_DWORD *)(v15[6] + 4LL) & 0x20) == 0) )
                    {
                      goto LABEL_594;
                    }
                    v124 = NtfsFindMatchingLcbPair(v15);
                    v125 = *((_DWORD *)v15 + 8);
                    v239 = v125;
                    if ( v124 )
                    {
                      v125 += *((_DWORD *)v124 + 8);
                      v239 = v125;
                    }
                    v126 = 19;
                    if ( v125 > 1 )
                    {
LABEL_594:
                      v126 = 3;
                      HIBYTE(v194) = 3;
                    }
                    if ( (v126 & 0x10) != 0
                      && *(_WORD *)(*(_QWORD *)v200 + 190LL) == 1
                      && *(_WORD *)(*(_QWORD *)(*(_QWORD *)v200 + 328LL) + 144LL) > 1u )
                    {
                      HIBYTE(v194) = v126 & 0xEF;
                      *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v200 + 328LL) + 4LL) |= 0x800u;
                    }
                  }
                }
                else if ( *(_WORD *)(v117 + 144) == 1 && (*(_DWORD *)(v117 + 4) & 0x800) != 0 )
                {
                  v237 = 0;
                  HIBYTE(v194) = 18;
                  memset(v242, 0, 0x58u);
                  LOBYTE(v194) = v194 | 0x10;
                  if ( !NtfsLookupInFileRecord(
                          (__int64)v3,
                          *(__int64 *)v200,
                          (_DWORD *)(*(_QWORD *)v200 + 8LL),
                          48,
                          0,
                          0,
                          0,
                          0,
                          0,
                          (__int64)v242) )
                  {
                    NtfsAttachCorruption_BadOrOrphanFRS(
                      (__int64)v3,
                      2,
                      460131,
                      0,
                      (_DWORD *)(*(_QWORD *)v200 + 8LL),
                      *(__int64 *)v200,
                      0);
                    NtfsAttachRepairInfoPriv((__int64)v3, 256, 0, (struct _LIST_ENTRY *)0xFB00070563LL);
                    if ( NtfsStatusDebugFlags )
                      NtfsStatusTraceAndDebugInternal((__int64)v3, 0xC0000102, 0x70563u);
                    NtfsRaiseStatusInternal((__int64)v3, -1073741566, v200[0] + 8, v200[0], 460131);
                  }
                  v118 = v242[0] + *(unsigned __int16 *)(v242[0] + 20);
                  ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v200 + 328LL) + 136LL));
                  v217 = 0;
                  v119 = *(_DWORD *)(*(_QWORD *)v200 + 8LL);
                  if ( v119 == 5 || (v120 = *(_QWORD *)(*(_QWORD *)v200 + 320LL), *(_DWORD *)(v120 + 88) == v119) )
                    v120 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v200 + 96LL) + 6248LL);
                  LODWORD(CompletionRoutinec) = 66;
                  Fcb = NtfsCreateFcb((__int64)v3, v204, v120, *(_QWORD *)v118, CompletionRoutinec, 0);
                  Scb = NtfsCreateScb((__int64)v3, Fcb, 160, &NtfsFileNameIndex, 0, 0, 0);
                  v207 = (__int64)Scb;
                  if ( (*((_DWORD *)Scb + 50) & 0x200) != 0 )
                  {
                    NtfsSnapshotScb((__int64)v3, (__int64)Scb);
                    Scb = (__int16 *)v207;
                  }
                  *((_QWORD *)&v237 + 1) = v118 + 66;
                  LOWORD(v237) = 2 * *(unsigned __int8 *)(v118 + 64);
                  WORD1(v237) = v237;
                  Lcb = NtfsCreateLcb(
                          (__int64)v3,
                          (__int64)Scb,
                          *(__int64 *)v200,
                          (const void **)&v237,
                          *(_BYTE *)(v118 + 65),
                          0);
                  v201[0] = 1;
                  ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v200 + 328LL) + 136LL), 1u);
                  v217 = *(_QWORD *)(*(_QWORD *)v200 + 328LL);
                }
                ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v200 + 328LL) + 136LL));
                v217 = 0;
                if ( (v194 & 0x10000000) != 0 )
                {
                  v230 = 18;
                  v240 = 0;
                  v127 = 18;
                  if ( v201[0] )
                    v127 = 22;
                  v230 = v127;
                  if ( (*((_DWORD *)FsContext + 1) & 1) != 0 )
                  {
                    v127 |= 1u;
                    v230 = v127;
                  }
                  LOBYTE(v247[23]) = 0;
                  v128 = v202[23];
                  if ( *(_WORD *)(v128 + 190) == 1 )
                  {
                    NtfsPostUsnChangeWithOverrideOption((__int64)v3, v128, -2147483136, 0, 0, 0, 0);
                  }
                  else
                  {
                    v129 = 0;
                    if ( (*(_BYTE *)(Lcb[24] + 65LL) & 3) != 2 )
                      v129 = Lcb[24];
                    NtfsPostUsnChangeWithOverrideOption((__int64)v3, v128, -2147418112, 0, 0, 0, v129);
                    NtfsUpdateFileTimestampsForChange(v202[23], FsContext, 0);
                  }
                  if ( *(int *)(v204 + 4) < 0 || (v130 = &v247[14], (*p_Flags & 0x20000) != 0) )
                    v130 = 0;
                  TxfDeleteFile(v3, v202[23], (__int64)Lcb, v127, 0, v247, (__int64)v130);
                  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v200 + 328LL) + 4LL) &= ~0x800u;
                  v110 = v203;
                  if ( v203 )
                  {
                    if ( v203 == -1073741608 && (*(_DWORD *)(*(_QWORD *)(v240 + 208) + 136LL) & 0x1000) != 0 )
                    {
                      v110 = -1072037844;
                      if ( NtfsStatusDebugFlags )
                        NtfsStatusTraceAndDebugInternal(0, 0xC01A002C, 0x706EBu);
                      v203 = -1072037844;
                    }
                    TxfRaiseAndAbortAtTopLevelPriv(
                      (__int64)v3,
                      v240,
                      0,
                      0,
                      0,
                      v110,
                      (__int64)"NtfsCommonCleanup",
                      (__int64)"Cleanup.c",
                      250);
                  }
                  if ( v201[0] || v3[3].offset.cidContainer )
                  {
                    NtfsUpdateFcbTimestamps(Fcb, -1610612720);
                  }
                  else
                  {
                    NtfsAcquireExclusiveScbEx((__int64)v3, v207, 0);
                    v201[0] = 1;
                    NtfsUpdateFcbTimestamps(Fcb, -1610612720);
                    NtfsReleaseFcbEx((__int64)v3, *(_QWORD *)(v207 + 184), 0);
                    v201[0] = 0;
                  }
                  if ( !v203 )
                  {
                    if ( *(int *)(v204 + 4) >= 0 && (*p_Flags & 0x20000) == 0 )
                    {
                      v131 = Lcb;
                      NtfsGetTunneledData(v3, *(_QWORD *)v200, *(unsigned __int8 *)(Lcb[24] + 65LL), &v247[14]);
                      if ( FsContext )
                        v132 = *((_DWORD *)FsContext + 1);
                      else
                        v132 = 0;
                      if ( (v132 & 0x4000000) != 0
                        || (v133 = 1, (*(_DWORD *)(*(_QWORD *)(v207 + 184) + 16LL) & 0x400) == 0) )
                      {
                        v133 = 0;
                      }
                      FsRtlAddToTunnelCacheEx(
                        v204 + 4720,
                        *(_QWORD *)(*(_QWORD *)(v207 + 184) + 8LL),
                        v247,
                        &v247[2],
                        *(_BYTE *)(v131[24] + 65LL) & 2 | v133,
                        80,
                        &v247[14]);
                    }
                    if ( (v194 & 0x2000) == 0 && *(_WORD *)v202 != 1796 )
                      NtfsReportDirNotify(
                        (__int64)v3,
                        *((_QWORD *)FsContext + 9),
                        v204,
                        (unsigned __int16 *)FsContext + 8,
                        *((unsigned __int16 *)FsContext + 16),
                        0,
                        (*(_WORD *)v202 == 1795) + 1,
                        2,
                        Fcb,
                        0);
                  }
                }
                if ( (*((_DWORD *)FsContext + 1) & 2) != 0
                  && ((*(_DWORD *)(*(_QWORD *)(*(_QWORD *)v200 + 328LL) + 4LL) & 0x800) != 0 || (v194 & 0x10000000) != 0) )
                {
                  ClearFlagInterlocked((unsigned int *)FsContext + 1, 0x40000);
                }
                else if ( *((_DWORD *)v202 + 64) == 128 )
                {
                  if ( *((_WORD *)v202 + 132) )
                  {
                    v134 = v202[66];
                    if ( *(_DWORD *)(v134 + 36) == 1 )
                    {
                      v135 = TxfCurrentWritableVersion(v134, 0, 1);
                      v7 = (volatile signed __int32 *)v135;
                      v236 = v135;
                      if ( v135 )
                      {
                        if ( (*(_DWORD *)(v135 + 8) & 4) == 0
                          && (*(_DWORD *)(v202[66] + 24LL) & 1) == 0
                          && ((v202[25] & 2) != 0 || (*((_DWORD *)FsContext + 1) & 0x40000) != 0) )
                        {
                          v136 = v194;
                          if ( (v194 & 0x10) != 0 )
                          {
                            NtfsCleanupAttributeContext(v3, v242);
                            v136 = v194;
                          }
                          memset(v242, 0, 0x58u);
                          LOBYTE(v194) = v136 | 0x10;
                          if ( !NtfsLookupInFileRecord(
                                  (__int64)v3,
                                  v202[23],
                                  (_DWORD *)(v202[23] + 8LL),
                                  *((_DWORD *)v202 + 64),
                                  (const UNICODE_STRING *)(v202 + 33),
                                  0,
                                  0,
                                  0,
                                  0,
                                  (__int64)v242)
                            && (v202[64] & 4) == 0 )
                          {
                            NtfsAttachCorruption_BadOrOrphanFRS(
                              (__int64)v3,
                              2,
                              460719,
                              0,
                              (_DWORD *)(v202[23] + 8LL),
                              v202[23],
                              0);
                            NtfsAttachRepairInfoPriv((__int64)v3, 512, 0, (struct _LIST_ENTRY *)0xA9000707AFLL);
                            if ( NtfsStatusDebugFlags )
                              NtfsStatusTraceAndDebugInternal((__int64)v3, 0xC0000102, 0x707AFu);
                            NtfsRaiseStatusInternal((__int64)v3, -1073741566, v202[23] + 8, v202[23], 460719);
                          }
                          TxfOverwriteAttribute((__int64)v3, (__int64)v202, v242, 1);
                          BYTE2(v194) |= 0x80u;
                        }
                      }
                    }
                  }
                }
                if ( v7 )
                {
                  LOBYTE(v111) = 6;
                  TxfDereferenceTxfVscb(v7, 0, v111, 0);
                }
              }
            }
            if ( (v194 & 0x100000) != 0 || !NtfsIsFileStillValid(*(__int64 *)v200) )
              goto LABEL_46;
            v18 = *((_DWORD *)FsContext + 1);
            if ( (v18 & 0x40000) == 0 )
            {
LABEL_37:
              if ( (v194 & 0x200000) != 0 )
              {
                if ( (v37 = *((_DWORD *)v202 + 64), v37 == 128) && *(_WORD *)v202 == 1797
                  || v37 == 160
                  && *((_WORD *)v202 + 132) == 8
                  && *(_QWORD *)v202[34] == 0x30003300490024LL
                  && (unsigned __int16)(*(_WORD *)v202 - 1795) <= 1u )
                {
                  v38 = FsRtlCheckOplockEx(
                          (POPLOCK)v202 + 11,
                          Irp,
                          0x20u,
                          v3,
                          NtfsOplockComplete,
                          (POPLOCK_FS_PREPOST_IRP)NtfsCleanupOplockPrePostIrp);
                  v203 = v38;
                  if ( v38 )
                  {
                    if ( v38 == 259 )
                    {
                      Irp = 0;
                      v3 = 0;
                      v206 = 0;
                      if ( NtfsStatusDebugFlags )
                        NtfsStatusTraceAndDebugInternal(0, 0x367u, 0x70941u);
                      v36 = 871;
                      v203 = 871;
                      goto LABEL_955;
                    }
                    if ( NtfsStatusDebugFlags
                      && (((v38 - 294) & 0xFFFFFFFA) != 0 || v38 == 295)
                      && v38 < 0xFFFFFFED
                      && v38 != -1073741802
                      && v38 != -1073741807
                      && v38 + 2147483643 > 1
                      && v38 != -1073741608 )
                    {
                      NtfsStatusTraceAndDebugInternal(0, v38, 0x7094Au);
                    }
                  }
                }
              }
              if ( *(_WORD *)(*(_QWORD *)v200 + 188LL) || *(_DWORD *)(*(_QWORD *)v200 + 20LL) != 1 )
              {
                if ( (v202[25] & 2) != 0 )
                {
                  v19 = *(_QWORD *)(*(_QWORD *)v200 + 328LL);
                  if ( v19 && (*(_DWORD *)(v19 + 4) & 1) != 0 )
                  {
                    if ( (v194 & 0x10000000) == 0 && (v194 & 0x2000000) != 0 && *(_DWORD *)(v202[66] + 36LL) == 1 )
                      BYTE1(v194) |= 4u;
                  }
                  else if ( *((_DWORD *)v202 + 52) == 1 && (v202[64] & 0x200000) == 0 )
                  {
                    BYTE1(v194) |= 4u;
                  }
                }
              }
              else
              {
                BYTE1(v194) |= 1u;
              }
LABEL_46:
              if ( v215 != 2 )
              {
                if ( v215 == 3 )
                  goto LABEL_48;
                if ( v215 != 4 )
                {
                  if ( v215 != 6 )
                  {
                    if ( (!v3 || (v3[2].offset.idxRecord & 0x100000) == 0)
                      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x800) != 0 )
                    {
                      McTemplateU0q_EtwWriteTransfer(
                        (__int64)&NtfsLog_Context,
                        (const EVENT_DESCRIPTOR *)cleanup_c4599,
                        v215);
                    }
                    KeBugCheckEx(0x24u, 0xAD000711FCuLL, v215, 0, 0);
                  }
LABEL_48:
                  NtfsSnapshotScb((__int64)v3, (__int64)v202);
                  v20 = (__int64)v202;
                  v21 = *((_DWORD *)v202 + 64);
                  if ( v21 == 128 && *(_WORD *)v202 == 1797
                    || v21 == 160
                    && *((_WORD *)v202 + 132) == 8
                    && *(_QWORD *)v202[34] == 0x30003300490024LL
                    && (unsigned __int16)(*(_WORD *)v202 - 1795) <= 1u )
                  {
                    FsRtlCheckOplock((POPLOCK)v202 + 11, Irp, 0, 0, 0);
                    v20 = (__int64)v202;
                  }
                  NtfsUpdateScbFromFileObject((__int64)FileObject, v20, 1);
                  FileObject->Flags |= 0x4000u;
                  if ( (*((_DWORD *)FsContext + 1) & 0x800000) != 0 )
                  {
                    if ( v215 == 6 )
                    {
                      FsRtlNotifyCleanup(*(PNOTIFY_SYNC *)(v204 + 1464), (PLIST_ENTRY)(v204 + 1448), FsContext);
                      ClearFlagInterlocked((unsigned int *)FsContext + 1, 0x800000);
                      _InterlockedDecrement((volatile signed __int32 *)(v204 + 2440));
                    }
                    else
                    {
                      FsRtlNotifyCleanup((PNOTIFY_SYNC)v202[96], (PLIST_ENTRY)v202 + 47, FsContext);
                      ClearFlagInterlocked((unsigned int *)FsContext + 1, 0x800000);
                      _InterlockedDecrement((volatile signed __int32 *)(v204 + 2436));
                    }
                  }
                  if ( (v194 & 0x80000) != 0
                    && (v194 & 0x100000) == 0
                    && *(_WORD *)v202 == 1795
                    && NtfsIsFileStillValid(*(__int64 *)v200) )
                  {
                    if ( (v194 & 0x100) == 0 )
                    {
                      if ( v15
                        && ((v47 = *((_DWORD *)v15 + 1), (v47 & 1) != 0)
                         || (*(_BYTE *)(v15[24] + 65LL) & 3) != 0 && (*(_DWORD *)(v15[6] + 4LL) & 0x20) != 0)
                        && ((*((_DWORD *)FsContext + 2) & 0x10000) != 0 || *(_QWORD *)(*(_QWORD *)v200 + 352LL))
                        && (v47 & 0x40) == 0
                        && !v3[50].ullOffset
                        && (v48 = *(_QWORD *)(v204 + 200), v15[3] != v48)
                        && v48 )
                      {
                        NtfsRenameToPrivateDir(
                          (__int64)v3,
                          (__int64)Irp,
                          *(__int64 *)v200,
                          (__int64)v202,
                          (__int64)FsContext,
                          (__int64)v15,
                          v207,
                          v201);
                        HIBYTE(v194) |= 0x80u;
                      }
                      else
                      {
                        v22 = *(_QWORD *)v200;
                        if ( *(_DWORD *)(*(_QWORD *)v200 + 24LL) == 1
                          && (v194 & 4) != 0
                          && *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v200 + 96LL) + 8428LL) <= (unsigned int)NtfsMaxDelayCloseCount
                          && (v202[25] & 0x1000000) == 0 )
                        {
                          SetFlagInterlocked((unsigned int *)v202 + 50, 0x200000u);
                        }
                      }
LABEL_58:
                      if ( (v194 & 0x100) != 0 || v194 < 0 )
                        FsRtlCheckOplockEx((POPLOCK)(v207 + 88), Irp, 0x50u, 0, 0, 0);
                      goto LABEL_88;
                    }
                    if ( v15 )
                    {
                      v223 = v15;
                      if ( (*((_DWORD *)v15 + 1) & 2) != 0 )
                      {
                        v223 = 0;
                        v15 = 0;
                        v209 = 0;
                        v84 = 0;
                        v207 = 0;
                        goto LABEL_408;
                      }
                    }
                    else
                    {
                      NextParentLcb = NtfsGetNextParentLcb((__int64)v3, *(__int64 *)v200, 0);
                      v223 = NextParentLcb;
                      if ( NextParentLcb )
                      {
                        v84 = NextParentLcb[3];
                        v207 = v84;
                        if ( v84 )
                          Fcb = *(_QWORD *)(v84 + 184);
                        goto LABEL_408;
                      }
                    }
                    v84 = v207;
LABEL_408:
                    if ( !v84 )
                    {
                      v241 = 0;
                      memset(v242, 0, 0x58u);
                      v196 = v194 | 0x10;
                      if ( !NtfsLookupInFileRecord(
                              (__int64)v3,
                              *(__int64 *)v200,
                              (_DWORD *)(*(_QWORD *)v200 + 8LL),
                              48,
                              0,
                              0,
                              0,
                              0,
                              0,
                              (__int64)v242) )
                      {
                        NtfsAttachCorruption_BadOrOrphanFRS(
                          (__int64)v3,
                          2,
                          461661,
                          0,
                          (_DWORD *)(*(_QWORD *)v200 + 8LL),
                          *(__int64 *)v200,
                          0);
                        NtfsAttachRepairInfoPriv((__int64)v3, 256, 0, (struct _LIST_ENTRY *)0xFC00070B5DLL);
                        if ( NtfsStatusDebugFlags )
                          NtfsStatusTraceAndDebugInternal((__int64)v3, 0xC0000102, 0x70B5Du);
                        NtfsRaiseStatusInternal((__int64)v3, -1073741566, v200[0] + 8, v200[0], 461661);
                      }
                      v86 = v242[0] + *(unsigned __int16 *)(v242[0] + 20);
                      v87 = *(_DWORD *)(*(_QWORD *)v200 + 8LL);
                      if ( v87 == 5 || (v88 = *(_QWORD *)(*(_QWORD *)v200 + 320LL), *(_DWORD *)(v88 + 88) == v87) )
                        v88 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v200 + 96LL) + 6248LL);
                      LODWORD(CompletionRoutinea) = 66;
                      Fcb = NtfsCreateFcb((__int64)v3, v204, v88, *(_QWORD *)v86, CompletionRoutinea, 0);
                      v89 = NtfsCreateScb((__int64)v3, Fcb, 160, &NtfsFileNameIndex, 0, 0, 0);
                      v207 = (__int64)v89;
                      if ( (*((_DWORD *)v89 + 50) & 0x200) != 0 )
                      {
                        NtfsSnapshotScb((__int64)v3, (__int64)v89);
                        v89 = (__int16 *)v207;
                      }
                      *((_QWORD *)&v241 + 1) = v86 + 66;
                      LOWORD(v241) = 2 * *(unsigned __int8 *)(v86 + 64);
                      WORD1(v241) = v241;
                      NtfsCreateLcb(
                        (__int64)v3,
                        (__int64)v89,
                        *(__int64 *)v200,
                        (const void **)&v241,
                        *(_BYTE *)(v86 + 65),
                        0);
                      v201[0] = 1;
                      NtfsCleanupAttributeContext(v3, v242);
                      LOBYTE(v194) = v196 & 0xEF;
                    }
                    NtfsDeleteFile((int)v3, v200[0], 0, 0);
                    --*(_WORD *)(*(_QWORD *)v200 + 190LL);
                    LOBYTE(v194) = v194 | 0x20;
                    v85 = v204;
                    if ( *(int *)(v204 + 4) >= 0 )
                    {
                      FsRtlDeleteKeyFromTunnelCache((TUNNEL *)(v204 + 4720), *(_QWORD *)(*(_QWORD *)v200 + 8LL));
                      v85 = v204;
                    }
                    v223 = 0;
                    if ( !v203 )
                    {
                      v90 = BYTE1(v194);
                      if ( (v194 & 0x2000) == 0 )
                      {
                        NtfsReportDirNotify(
                          (__int64)v3,
                          *((_QWORD *)FsContext + 9),
                          v85,
                          (unsigned __int16 *)FsContext + 8,
                          *((unsigned __int16 *)FsContext + 16),
                          0,
                          2,
                          2,
                          Fcb,
                          0);
                        v90 = BYTE1(v194);
                      }
                      BYTE1(v194) = v90 | 2;
                      ClearFlagInterlocked((unsigned int *)FsContext + 1, 112);
                    }
                    goto LABEL_58;
                  }
LABEL_88:
                  if ( v215 == 4 )
                  {
                    v31 = 8;
LABEL_114:
                    if ( v203 == -1073741608 || v203 == -1073741432 )
                    {
                      if ( NtfsStatusDebugFlags && v203 - 298 > 1 && v203 != -1073741608 && v203 + 2147483643 > 1 )
                        NtfsStatusTraceAndDebugInternal((__int64)v3, v203, 0x7144Eu);
                      NtfsRaiseStatusInternal((__int64)v3, v203, 0, 0, 463950);
                    }
                    if ( v203 && (v194 & 8) == 0 )
                    {
                      *((_DWORD *)v202 + 128) |= 0x20000000u;
                      if ( (!v3 || (v3[2].offset.idxRecord & 0x100000) == 0)
                        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 1) != 0 )
                      {
                        McTemplateU0q_EtwWriteTransfer(
                          (__int64)&NtfsLog_Context,
                          (const EVENT_DESCRIPTOR *)cleanup_c5206,
                          v203);
                      }
                      NtfsRaiseStatusInternal((__int64)v3, 0, 0, 0, 463964);
                    }
                    if ( *((_QWORD *)FsContext + 16) && xmmword_140095790 )
                      xmmword_140095790((char *)FsContext + 128, 0);
                    if ( *((_DWORD *)v202 + 52) == 1 && v202[67] && xmmword_140095790 )
                    {
                      LOBYTE(v22) = 1;
                      xmmword_140095790(v202 + 67, v22);
                    }
                    if ( !v3[50].ullOffset
                      && *((_DWORD *)v202 + 52) == 1
                      && v202[63]
                      && (*((_BYTE *)v202 + 4) & 0x20) != 0
                      && (dword_1400956B8 & 0x10000000) != 0 )
                    {
                      v250 = 0;
                      NtfsCoherencyFlushAndPurgeCache(v3, v202, 0, 0, &v250, 0);
                    }
                    if ( (v3[1].offset.idxRecord & 1) != 0 )
                      NtfsPersistStorageReserveChanges((__int64)v3);
                    v3[1].offset.cidContainer |= 0x8000000u;
                    SetFlagInterlocked((unsigned int *)FsContext + 1, 0x8000u);
                    if ( (v194 & 0x4000) != 0 || (v194 & 0x10000000) != 0 )
                      *(_DWORD *)(*(_QWORD *)v200 + 4LL) &= ~0x4000u;
                    if ( (v194 & 0x100) != 0 && (*(_DWORD *)(v204 + 8204) & 4) != 0 && (unsigned int)(v215 - 2) <= 1 )
                    {
                      v250 = 0u;
                      v248 = 0;
                      v249 = 0;
                      v75 = v202[23];
                      *(_QWORD *)&v250 = *(_QWORD *)(v75 + 8);
                      if ( Irp )
                      {
                        ActivityIdIrp = IoGetActivityIdIrp(Irp, (char *)&v248 + 8);
                        v113 = (char *)&v248 + 8;
                        if ( ActivityIdIrp < 0 )
                          v113 = 0;
                        *(_QWORD *)&v248 = v113;
                      }
                      else
                      {
                        ActivityIdThread = (_QWORD *)IoGetActivityIdThread(v75);
                        if ( ActivityIdThread )
                        {
                          *((_QWORD *)&v248 + 1) = *ActivityIdThread;
                          v249 = ActivityIdThread[1];
                          *(_QWORD *)&v248 = (char *)&v248 + 8;
                        }
                        else
                        {
                          *(_QWORD *)&v248 = 0;
                        }
                      }
                      FsRtlHeatLogIo(v204 + 8200, Irp, &v250, 0, v248);
                    }
                    if ( (v194 & 0x100) != 0 || (v194 & 0x4000) != 0 || (v194 & 0x10000000) != 0 )
                    {
                      if ( (v194 & 0x10000000) != 0 )
                        v15 = Lcb;
                      if ( (v194 & 0x100) != 0 || (*(_BYTE *)(v15[24] + 65LL) & 3) != 0 )
                        *(_DWORD *)(*(_QWORD *)v200 + 4LL) &= ~0x20u;
                    }
                    if ( (v194 & 0x100) != 0
                      || (v194 & 0x4000) != 0
                      || (v194 & 0x400) != 0
                      || v194 < 0
                      || (v194 & 0x10000000) != 0 )
                    {
                      v77 = Irp;
                      Irp->IoStatus.Information = 0;
                      if ( (v194 & 0x10000000) != 0 )
                      {
                        ExAcquireResourceSharedLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v200 + 328LL) + 136LL), 1u);
                        v176 = *(_QWORD *)v200;
                        if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)v200 + 328LL) + 4LL) & 0x200000) != 0 )
                          v31 = 4;
                        v246->IoStatus.Information = v31;
                        ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(v176 + 328) + 136LL));
                      }
                      else if ( (v194 & 0x100) != 0 )
                      {
                        v77->IoStatus.Information = 4;
                      }
                      else if ( (v194 & 0x4000) != 0 )
                      {
                        Irp->IoStatus.Information = 8;
                      }
                      else if ( v194 < 0 )
                      {
                        Irp->IoStatus.Information = 36;
                      }
                      if ( (v194 & 0x400) != 0 )
                        Irp->IoStatus.Information |= 0x10uLL;
                    }
                    v32 = FsContext;
                    if ( *((_QWORD *)FsContext + 10) && ((v194 & 0x1000000) != 0 || (v194 & 0x4000000) != 0) )
                    {
                      --*((_DWORD *)v235 + 8);
                      v32 = FsContext;
                    }
                    if ( (v194 & 0x40000) != 0 && (v194 & 0x4000) == 0 && (v3[54].offset.cidContainer & 0x80008) == 0 )
                    {
                      NtfsUpdateLcbDuplicateInfo(*(_QWORD *)v200, v216);
                      *(_DWORD *)(*(_QWORD *)v200 + 184LL) = 0;
                      v32 = FsContext;
                    }
                    if ( (*((_DWORD *)v32 + 1) & 8) != 0 )
                    {
                      v33 = 1;
                    }
                    else
                    {
                      v33 = 0;
                      if ( v32[88] == 4 )
                        v33 = 2;
                    }
                    NtfsRemoveShareAccess(FileObject, v33, v202, v235);
                    v34 = *((int *)FsContext + 1) < 0 && (*((_DWORD *)FsContext + 2) & 2) == 0;
                    NtfsDecrementCleanupCounts((__int64)v3, (__int64)v202, (__int64)v235, FileObject->Flags & 8, v34);
                    if ( (*((_DWORD *)FsContext + 2) & 0x80000) != 0 )
                    {
                      _InterlockedDecrement((volatile signed __int32 *)(v204 + 272));
                      ClearFlagInterlocked((unsigned int *)FsContext + 2, 0x80000);
                    }
                    v223 = 0;
                    v209 = 0;
                    v35 = *((_QWORD *)FsContext + 10);
                    if ( v35 )
                    {
                      if ( *(_DWORD *)(v35 + 36) )
                      {
                        ExAcquireResourceExclusiveLite(
                          *(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v200 + 328LL) + 136LL),
                          1u);
                        v217 = *(_QWORD *)(*(_QWORD *)v200 + 328LL);
                        --*(_DWORD *)(*(_QWORD *)(*((_QWORD *)FsContext + 10) + 8LL) + 12LL);
                        v177 = *(_QWORD *)(*((_QWORD *)FsContext + 10) + 8LL);
                        if ( *(_DWORD *)(v177 + 12) || (*(_DWORD *)(v177 + 8) & 1) == 0 )
                        {
                          ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v200 + 328LL) + 136LL));
                          v217 = 0;
                        }
                        else
                        {
                          ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v200 + 328LL) + 136LL));
                          v217 = 0;
                          if ( !CcPurgeCacheSection(
                                  (PSECTION_OBJECT_POINTERS)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)FsContext + 10) + 8LL)
                                                                       + 24LL)
                                                           + 16LL),
                                  0,
                                  0,
                                  0) )
                            MmForceSectionClosed(
                              (PSECTION_OBJECT_POINTERS)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)FsContext + 10) + 8LL)
                                                                   + 24LL)
                                                       + 16LL),
                              1u);
                        }
                      }
                      if ( (v194 & 0x2000000) != 0 || (v194 & 0x8000000) != 0 )
                      {
                        ExAcquireResourceExclusiveLite(
                          *(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v200 + 328LL) + 136LL),
                          1u);
                        --*(_WORD *)(*(_QWORD *)(*(_QWORD *)v200 + 328LL) + 144LL);
                        --*(_DWORD *)(v202[66] + 36LL);
                        ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v200 + 328LL) + 136LL));
                      }
                      v95 = *((_QWORD *)FsContext + 10);
                      v96 = *(_DWORD *)(v95 + 4);
                      if ( (v96 & 2) == 0 )
                      {
                        *(_DWORD *)(v95 + 4) = v96 | 8;
                        v97 = v3[50];
                        if ( v97.ullOffset )
                          _InterlockedDecrement((volatile signed __int32 *)(v97.ullOffset + 448));
                      }
                    }
                    if ( (v194 & 0x200) != 0 )
                    {
                      v98 = (SECTION_OBJECT_POINTERS *)(v202[36] + 16LL);
                      if ( v98->DataSectionObject )
                      {
                        if ( !MmForceSectionClosed(v98, 1u) )
                          BYTE1(v194) &= ~2u;
                      }
                    }
                    if ( (*((_DWORD *)FsContext + 1) & 0x8000000) != 0 )
                    {
                      ClearFlagInterlocked((unsigned int *)FsContext + 1, 0x8000000);
                      *((_DWORD *)v202 + 128) &= ~2u;
                    }
                    if ( (*((_DWORD *)FsContext + 2) & 0x1000) != 0 )
                    {
                      ClearFlagInterlocked((unsigned int *)FsContext + 2, 4096);
                      *(_DWORD *)(*(_QWORD *)v200 + 16LL) &= ~2u;
                    }
                    if ( (*((_DWORD *)FsContext + 2) & 0x400) != 0 )
                    {
                      ClearFlagInterlocked((unsigned int *)FsContext + 2, 1024);
                      --*((_DWORD *)v202 + 55);
                    }
                    if ( v215 != 4
                      && *(_QWORD *)(*(_QWORD *)v200 + 120LL)
                      && (*(_DWORD *)(*(_QWORD *)v200 + 4LL) & 1) != 0 )
                    {
                      NtfsDereferenceQuotaControlBlock(v204, (PVOID **)(*(_QWORD *)v200 + 120LL), 0);
                    }
                    v36 = v203;
                    if ( v203 )
                    {
                      if ( (v3[2].offset.idxRecord & 0x100000) == 0
                        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 1) != 0 )
                      {
                        McTemplateU0q_EtwWriteTransfer(
                          (__int64)&NtfsLog_Context,
                          (const EVENT_DESCRIPTOR *)cleanup_c5778,
                          v203);
                      }
                      v3[3].offset.idxRecord = 0;
                      NtfsRaiseStatusInternal((__int64)v3, 0, 0, 0, 464543);
                    }
LABEL_955:
                    if ( v36 != 871 )
                    {
                      if ( (v194 & 0x200) != 0 && (*(_DWORD *)(*(_QWORD *)v200 + 4LL) & 0x40) != 0 )
                      {
                        v182 = 0;
                        ExAcquirePushLockExclusiveEx(v204 + 656, 0);
                        v183 = *(_QWORD *)v200;
                        if ( (*(_DWORD *)(*(_QWORD *)v200 + 4LL) & 0x40) != 0 )
                        {
                          v184 = *(_QWORD *)(*(_QWORD *)v200 + 96LL);
                          RtlAvlRemoveNode(v184 + 1344, *(_QWORD *)(*(_QWORD *)v200 + 104LL) + 256LL);
                          --*(_DWORD *)(v184 + 1352);
                          *(_DWORD *)(v183 + 4) &= ~0x40u;
                          v182 = 1;
                        }
                        ExReleasePushLockEx(v204 + 656, 0);
                        if ( v182 )
                        {
                          LOBYTE(v185) = 1;
                          NtfsDereferenceMftView(*(_QWORD *)(*(_QWORD *)v200 + 96LL), *(_QWORD *)v200 + 8LL, v185);
                        }
                      }
                      v179 = *((_QWORD *)FsContext + 10);
                      if ( v179 )
                        *(_DWORD *)(v179 + 4) &= ~0x40u;
                      if ( v217 )
                        ExReleaseResourceLite(*(PERESOURCE *)(v217 + 136));
                      if ( (v194 & 0x1000) != 0 )
                      {
                        ExReleasePushLockEx(v204 + 656, 0);
                        BYTE1(v194) &= ~0x10u;
                      }
                      if ( (v194 & 2) != 0 )
                        NtfsReleaseFcbEx((__int64)v3, *(_QWORD *)(*(_QWORD *)(v204 + 160) + 184LL), 0);
                      NtfsReleaseVcb((__int64)v3, v204);
                      if ( (v194 & 1) != 0 )
                      {
                        NtfsReleaseCheckpointSynchronization((__int64)v3, v204, 18);
                        LOBYTE(v194) = v194 & 0xFE;
                      }
                      if ( (v194 & 0x10) != 0 )
                        NtfsCleanupAttributeContext(v3, v242);
                      if ( (v194 & 0x20000) != 0 )
                      {
                        NtfsReleaseFcbEx((__int64)v3, v202[23], 0);
                        FsRtlNotifyVolumeEvent(FileObject, 5u);
                      }
                      v36 = v203;
                    }
                    if ( (__int64 *)v247[3] != &v247[7] )
                    {
                      ExFreePoolWithTag((PVOID)v247[3], 0);
                      v36 = v203;
                    }
                    if ( (v194 & 0x80u) != 0 )
                    {
                      _InterlockedDecrement(v228 + 53);
                      v36 = v203;
                    }
                    if ( (v194 & 0x800) != 0 && (v36 & 0x80000000) == 0 )
                    {
                      if ( v36 == 871 )
                        return v36;
                      if ( v215 != 4
                        && (v194 & 0x80000) != 0
                        && (v194 & 0x100000) == 0
                        && ((v194 & 0x100) != 0
                         || (v194 & 0x400) != 0
                         || (v194 & 0x4000) != 0
                         || (*((_WORD *)FsContext + 52) & 0x912) != 0) )
                      {
                        if ( NtfsStatusDebugFlags
                          && v36
                          && v36 != 294
                          && v36 - 298 > 1
                          && v36 + 2147483643 > 1
                          && v36 != 259 )
                        {
                          NtfsStatusTraceAndDebugInternal((__int64)v3, v36, 0x71802u);
                        }
                        NtfsExtendedCompleteRequestInternal((__int64)v3, 0, v203, 1u, 1);
                        LOBYTE(v186) = 9;
                        v187 = NtfsIoCallSelf(0, FileObject, v186, (*(_DWORD *)(v204 + 24) & 0x100) != 0 ? 3 : 0);
                        if ( v187 != -1073741533 )
                          v4 = v187;
                        if ( v4 < 0 )
                        {
                          if ( (unsigned int)(v4 + 1073741662) > 1
                            && (unsigned int)(v4 + 1073741806) > 2
                            && v4 != -2147483626
                            && v4 != -1073741643 )
                          {
                            v4 = -1073700734;
                            if ( NtfsStatusDebugFlags )
                              NtfsStatusTraceAndDebugInternal(0, 0xC000A082, 0x71827u);
                          }
                          ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)v200 + 104LL) + 8LL));
                          IoRaiseInformationalHardError(v4, (PUNICODE_STRING)FsContext + 1, Irp->Tail.Overlay.Thread);
                          ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)v200 + 104LL) + 8LL));
                        }
                        v36 = v203;
                      }
                    }
                    if ( v36 != 871 )
                    {
                      NtfsCompleteCleanupRequest(v3, Irp, v36);
                      return v203;
                    }
                    return v36;
                  }
                  v27 = *(_QWORD *)(*(_QWORD *)v200 + 192LL);
                  if ( *(_QWORD *)(*(_QWORD *)v200 + 152LL) == v27 )
                  {
LABEL_90:
                    if ( (v194 & 0x80000) == 0 || (v194 & 0x100000) != 0 || !NtfsIsFileStillValid(*(__int64 *)v200) )
                    {
LABEL_91:
                      *(_DWORD *)(*(_QWORD *)v200 + 4LL) &= ~0x10u;
                      if ( v201[0] && (v194 & 0x4000) == 0 )
                      {
                        NtfsReleaseFcbEx((__int64)v3, *(_QWORD *)(v207 + 184), 0);
                        v201[0] = 0;
                      }
                      if ( FileObject->PrivateCacheMap || TruncateSize )
                        CcUninitializeCacheMap(FileObject, TruncateSize, 0);
                      if ( (v194 & 0x10) != 0 )
                      {
                        NtfsCleanupAttributeContext(v3, v242);
                        LOBYTE(v194) = v194 & 0xEF;
                      }
                      v28 = *(_QWORD *)v200;
                      v29 = *(_QWORD *)(*(_QWORD *)v200 + 328LL);
                      if ( v29 )
                        v22 = *(_QWORD *)(v29 + 24);
                      else
                        v22 = 0;
                      if ( v22 == v3[50].ullOffset
                        && (*(_DWORD *)(*(_QWORD *)v200 + 20LL) == 1 && (!v29 || !*(_QWORD *)(v29 + 24))
                         || (v194 & 0x2000000) != 0 && *(_WORD *)(v29 + 144) == 1) )
                      {
                        v30 = *(_QWORD *)(*(_QWORD *)v200 + 296LL);
                        if ( v30 )
                        {
                          if ( *(_DWORD *)(v30 + 248) || v3[30].ullOffset == *(_QWORD *)v200 && v3[32].offset.idxRecord )
                          {
                            v22 = 0;
                            while ( 1 )
                            {
                              v78 = NtfsGetNextChildScb(v28, v22, 1);
                              v22 = (__int64)v78;
                              if ( !v78 )
                              {
                                NtfsPostUsnChangeWithOverrideOption(
                                  (__int64)v3,
                                  *(__int64 *)v200,
                                  0x80000000,
                                  0,
                                  0,
                                  0,
                                  0);
                                v28 = *(_QWORD *)v200;
                                v31 = 8;
                                goto LABEL_105;
                              }
                              if ( (*((_BYTE *)v78 + 4) & 0x20) != 0 && (v78[25] & 0x40000) != 0 )
                                break;
                              v28 = *(_QWORD *)v200;
                            }
                            v28 = *(_QWORD *)v200;
                          }
                        }
                      }
                      v31 = 8;
LABEL_105:
                      if ( v3[30].ullOffset && !v203 )
                      {
                        NtfsWriteUsnJournalChanges((__int64)v3);
                        NtfsCheckpointCurrentTransaction((__int64)v3);
                        v28 = *(_QWORD *)v200;
                      }
                      if ( v203 == -1073741608 || v203 == -1073741432 )
                      {
                        if ( NtfsStatusDebugFlags && v203 - 298 > 1 && v203 != -1073741608 && v203 + 2147483643 > 1 )
                          NtfsStatusTraceAndDebugInternal((__int64)v3, v203, 0x713A6u);
                        NtfsRaiseStatusInternal((__int64)v3, v203, 0, 0, 463782);
                      }
                      if ( v203 && (v194 & 8) == 0 )
                      {
                        *((_DWORD *)v202 + 128) |= 0x20000000u;
                        if ( (v3[2].offset.idxRecord & 0x100000) == 0
                          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 1) != 0 )
                        {
                          McTemplateU0q_EtwWriteTransfer(
                            (__int64)&NtfsLog_Context,
                            (const EVENT_DESCRIPTOR *)cleanup_c5039,
                            v203);
                        }
                        NtfsRaiseStatusInternal((__int64)v3, 0, 0, 0, 463797);
                      }
                      if ( (v202[25] & 4) != 0 && *((_DWORD *)v202 + 52) == 1 )
                      {
                        ClearFlagInterlocked((unsigned int *)v202 + 50, 4);
                        v28 = *(_QWORD *)v200;
                      }
                      if ( (v194 & 0x10000) != 0 )
                      {
                        ClearFlagInterlocked((unsigned int *)v202 + 50, 1);
                        v28 = *(_QWORD *)v200;
                      }
                      if ( (v194 & 0x2000000) != 0 )
                      {
                        ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(v28 + 328) + 136LL), 1u);
                        v174 = *(_QWORD *)v200;
                        v175 = *(_QWORD *)(*(_QWORD *)v200 + 328LL);
                        v217 = v175;
                        if ( *(_WORD *)(v175 + 144) == 1 && (*(_DWORD *)(v175 + 4) & 0x10000) == 0 )
                        {
                          if ( *(_WORD *)(*(_QWORD *)v200 + 188LL) > 1u )
                          {
                            ExReleaseResourceLite(*(PERESOURCE *)(v175 + 136));
                            v217 = 0;
                            TxfLogFcbInfoRecord((__int64)v3, v3[50].ullOffset, *(__int64 *)v200, 0, 1, 0);
                            ExAcquireResourceExclusiveLite(
                              *(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v200 + 328LL) + 136LL),
                              1u);
                            v174 = *(_QWORD *)v200;
                            v217 = *(_QWORD *)(*(_QWORD *)v200 + 328LL);
                          }
                          *(_DWORD *)(*(_QWORD *)(v174 + 328) + 4LL) |= 0x10000u;
                          v174 = *(_QWORD *)v200;
                        }
                        ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(v174 + 328) + 136LL));
                        v217 = 0;
                        v28 = *(_QWORD *)v200;
                      }
                      if ( *(_DWORD *)(v28 + 20) == 1 )
                      {
                        v22 = *(unsigned int *)(v28 + 8);
                        if ( (_DWORD)v22 == 5 || *(_DWORD *)(*(_QWORD *)(v28 + 320) + 88LL) == (_DWORD)v22 )
                        {
                          v44 = *(_QWORD *)(v28 + 320);
                          if ( v44 != *(_QWORD *)(*(_QWORD *)(v44 + 16) + 6248LL) )
                          {
                            if ( TxfMarkRmForShutdown(v44) )
                            {
                              _InterlockedOr(
                                (volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)v200 + 320LL) + 136LL),
                                4u);
                              TxfQueueDelayedRmWorkItem(*(_QWORD *)(*(_QWORD *)v200 + 320LL));
                            }
                          }
                        }
                      }
                      goto LABEL_114;
                    }
                    if ( (*(_DWORD *)(*(_QWORD *)v200 + 4LL) & 0x10) == 0 || v203 || (v194 & 0x20000000) != 0 )
                    {
                      v39 = 512;
                    }
                    else
                    {
                      NtfsUpdateStandardInformation((__int64)v3, *(__int64 *)v200, 0);
                      v39 = 512;
                    }
                    v40 = (__int64)v216;
                    if ( ((*(_DWORD *)(*(_QWORD *)v200 + 184LL) & 0xD00000FC) != 0
                       || v216
                       && (*((_DWORD *)v216 + 45) & 0xD00000FC) != 0
                       && ((*((_DWORD *)v216 + 1) & 0x40) == 0 || v194 >= 0))
                      && !v203
                      && (*(_DWORD *)(*(_QWORD *)v200 + 4LL) & 0x100) == 0 )
                    {
                      v53 = 0;
                      v208 = 0;
                      if ( (*(_DWORD *)(*(_QWORD *)v200 + 4LL) & 0x20000) != 0
                        || (v54 = v207) != 0
                        && ((v55 = *(_QWORD *)(v207 + 184), (*(_DWORD *)(v55 + 4) & 0x20000) != 0)
                         || *(int *)(v55 + 176) < 0) )
                      {
                        v208 = 1;
                      }
                      else
                      {
                        if ( (v194 & 0x4000) == 0 )
                        {
                          updated = 0;
                          v210 = 0;
                          v60 = HIBYTE(v194);
                          if ( (v194 & 0x40000000) != 0 )
                          {
                            v40 = (__int64)v216;
                          }
                          else
                          {
                            updated = NtfsPrepareForUpdateDuplicate(
                                        (__int64)v3,
                                        *(__int64 *)v200,
                                        (__int64 *)&v216,
                                        &v207,
                                        1,
                                        1);
                            v210 = updated;
                            v40 = (__int64)v216;
                            if ( v216 && (*((_DWORD *)v216 + 1) & 0x40) != 0 )
                            {
                              v60 = HIBYTE(v194);
                              if ( v194 < 0 )
                                updated = 0;
                              v210 = updated;
                            }
                            else
                            {
                              v60 = HIBYTE(v194);
                            }
                            v54 = v207;
                          }
                          if ( !updated || (v60 & 0x40) != 0 )
                          {
                            v208 = 1;
                            goto LABEL_165;
                          }
                          v53 = NtfsUpdateDuplicateInfo((__int64)v3, *(__int64 *)v200, v40, v54);
                          v208 = v53;
                        }
                        if ( !v53 )
                          BYTE2(v194) |= 4u;
                      }
                      v40 = (__int64)v216;
                    }
LABEL_165:
                    if ( (v194 & 0x2000) == 0 && !v203 )
                    {
                      v224 = 0;
                      if ( (v194 & 0x40000) != 0 && (v194 & 0x4000) == 0
                        || (*(_DWORD *)(*(_QWORD *)v200 + 184LL) & 0x100) != 0 )
                      {
                        v61 = v40 ? *(_DWORD *)(v40 + 180) : 0;
                        v62 = *(_DWORD *)(*(_QWORD *)v200 + 184LL);
                        if ( ((v61 | v62) & 0x40000000) != 0 )
                        {
                          if ( v40 )
                            v91 = *(_DWORD *)(v40 + 180);
                          else
                            LOWORD(v91) = 0;
                          v64 = ((unsigned __int16)v91 | (unsigned __int16)v62) & 0x1F4 | 8;
                        }
                        else
                        {
                          if ( v40 )
                            v63 = *(_DWORD *)(v40 + 180);
                          else
                            LOWORD(v63) = 0;
                          v64 = ((unsigned __int16)v63 | (unsigned __int16)v62) & 0x1FC;
                        }
                        v224 = v64;
                        if ( v64 )
                          NtfsReportDirNotify(
                            (__int64)v3,
                            *((_QWORD *)FsContext + 9),
                            v204,
                            (unsigned __int16 *)FsContext + 8,
                            *((unsigned __int16 *)FsContext + 16),
                            0,
                            v64,
                            3,
                            Fcb,
                            0);
                      }
                      *(_DWORD *)(*(_QWORD *)v200 + 184LL) &= ~0x100u;
                      v41 = (__int64)v202;
                      if ( *((_WORD *)v202 + 132) && *((_DWORD *)v202 + 64) == 128 )
                      {
                        v42 = *((_DWORD *)v202 + 128);
                        if ( (v42 & 0x1C00) != 0 )
                        {
                          v224 = 0;
                          if ( (v42 & 0x400) != 0 )
                          {
                            v224 = 512;
                            v43 = 7;
                          }
                          else
                          {
                            v39 = 0;
                            if ( (v42 & 0x800) != 0 )
                              v39 = 1024;
                            v224 = v39;
                            if ( (v42 & 0x1000) != 0 )
                            {
                              v39 |= 0x800u;
                              v224 = v39;
                            }
                            v43 = 8;
                          }
                          NtfsReportDirNotify(
                            (__int64)v3,
                            *((_QWORD *)FsContext + 9),
                            v204,
                            (unsigned __int16 *)FsContext + 8,
                            *((unsigned __int16 *)FsContext + 16),
                            (__int64)(v202 + 33),
                            v39,
                            v43,
                            Fcb,
                            0);
                          v41 = (__int64)v202;
                        }
                        *((_DWORD *)v202 + 128) = *(_DWORD *)(v41 + 512) & 0xFFFFE1FF;
                      }
                    }
                    goto LABEL_91;
                  }
                  v49 = *(_DWORD *)(*(_QWORD *)v200 + 4LL);
                  if ( (v49 & 0x10) != 0 )
                  {
                    *(_QWORD *)(*(_QWORD *)v200 + 152LL) = v27;
                  }
                  else
                  {
                    if ( (v49 & 1) != 0 || !NtfsCheckLastAccess((__int64)v3, *(__int64 *)v200) )
                      goto LABEL_90;
                    *(_DWORD *)(*(_QWORD *)v200 + 4LL) |= 0x10u;
                  }
                  *(_DWORD *)(*(_QWORD *)v200 + 184LL) |= 0x20u;
                  goto LABEL_90;
                }
                FileObject->Flags |= 0x4000u;
                if ( *((_BYTE *)FsContext + 88) == 4 && (*((_DWORD *)FsContext + 1) & 0x400) != 0 )
                {
                  v213 = 0;
                  v212 = 0;
                  ExAcquireResourceExclusiveLite((PERESOURCE)(v204 + 6800), 1u);
                  v213 = 1;
                  ExAcquireResourceExclusiveLite(&stru_1400953C0, 1u);
                  v212 = 1;
                  ClearFlagInterlocked((unsigned int *)FsContext + 1, 1024);
                  *(_DWORD *)(v204 + 6904) &= ~2u;
                  *(_QWORD *)(v204 + 6928) = 0;
                  if ( !--dword_140095450 )
                    NtfsSendGlobalCorruptionActionEvent(v3);
                  ExReleaseResourceLite(&stru_1400953C0);
                  ExReleaseResourceLite((PERESOURCE)(v204 + 6800));
                }
                v22 = v204;
                if ( *(struct _FILE_OBJECT **)(v204 + 1480) == FileObject )
                {
                  v148 = *(_QWORD *)(v204 + 72);
                  if ( v148 )
                  {
                    NtfsAcquireExclusiveFcb((__int64)v3, *(_QWORD *)(v148 + 184), *(_QWORD *)(v204 + 72), 0);
                    *(_QWORD *)(v204 + 5368) = 0x7FFFFFFFFFFFFFFFLL;
                    *(_QWORD *)(v204 + 5376) = 0;
                    *(_QWORD *)(v204 + 1480) = 0;
                    NtfsReleaseFcbEx((__int64)v3, *(_QWORD *)(*(_QWORD *)(v204 + 72) + 184LL), 0);
                    v22 = v204;
                  }
                }
                if ( (*(_DWORD *)(v22 + 4) & 2) == 0
                  || (struct _FILE_OBJECT *)(*(_QWORD *)(v22 + 1472) & 0xFFFFFFFFFFFFFFFEuLL) != FileObject )
                {
                  goto LABEL_88;
                }
                cidContainer = v3[1].offset.cidContainer;
                if ( (cidContainer & 0x200) == 0 )
                {
                  v3[1].offset.cidContainer = cidContainer | 0x200;
                  NtfsRaiseStatusInternal((__int64)v3, -1073741608, 0, 0, 461358);
                }
                if ( *(struct _FILE_OBJECT **)(v22 + 1472) == (struct _FILE_OBJECT *)((char *)&FileObject->Type + 1) )
                {
                  NtfsSendBeginDismountEvent(v3, v22, 0, 3);
                  v149 = v204;
                  if ( (*(_DWORD *)(v204 + 24) & 0x40000) != 0 )
                  {
                    v150 = *(_QWORD *)(v204 + 64);
                    if ( !v150 || (*(_DWORD *)(v150 + 200) & 0x20000) != 0 )
                    {
                      NtfsPurgeLogFile(v204, v3);
                      v149 = v204;
                    }
                  }
                  NtfsPerformDismountOnVcb((char *)v3, v149, 1, 0, 3, 0);
                }
                else
                {
                  if ( (FileObject->Flags & 0x1000) == 0 )
                  {
LABEL_731:
                    ClearFlagInterlocked((unsigned int *)(v22 + 4), 32770);
                    *(_QWORD *)(v204 + 1472) = 0;
                    BYTE2(v194) |= 2u;
                    if ( (BYTE2(v194) & 0x18) == 8 && NtfsIsFileStillValid(*(__int64 *)v200) && !v203 )
                    {
                      if ( *(_DWORD *)(v204 + 2156) == -1073741202 )
                      {
                        *(_DWORD *)(v204 + 2156) = 0;
                        NtfsPostSpecial((_DWORD)v3, v204, (unsigned int)NtfsDeleteUsnSpecial, v204 + 2144, 13);
                      }
                      if ( !v203 )
                      {
                        v22 = v204;
                        if ( (*(_DWORD *)(v204 + 4504) & 0xE00) != 0 && (*(_DWORD *)(v204 + 4504) & 0x40) != 0 )
                          NtfsPostRepairQuotaIndex(v3, v204);
                      }
                    }
                    goto LABEL_88;
                  }
                  if ( (v194 & 0x80000) != 0 && (v194 & 0x100000) == 0 )
                  {
                    if ( NtfsIsFileStillValid(*(__int64 *)v200) )
                    {
                      NtfsReleaseFcbEx((__int64)v3, v202[23], 0);
                      NtfsFlushVolume((int)v3);
                      NtfsAcquireExclusiveFcb((__int64)v3, v202[23], (__int64)v202, 8);
                    }
                    v22 = v204;
                  }
                  if ( *(_DWORD *)(v22 + 256) == 1 )
                  {
                    v22 = v204;
                    if ( *(_DWORD *)(v204 + 260) - *(_DWORD *)(v204 + 268) == 1 )
                    {
                      NtfsSendBeginDismountEvent(v3, v204, 0, 3);
                      NtfsPerformDismountOnVcb((char *)v3, v204, 1, 0, 3, 0);
                      v22 = v204;
                    }
                    goto LABEL_731;
                  }
                }
                v22 = v204;
                goto LABEL_731;
              }
              if ( (v202[25] & 0x20) == 0
                && (v194 & 0x80000) != 0
                && (v194 & 0x100000) == 0
                && NtfsIsFileStillValid(v202[23]) )
              {
                NtfsUpdateScbFromAttribute((__int64)v3, (__int64)v202, 0);
              }
              NtfsClearSfioReservation(
                (_DWORD)v3,
                (_DWORD)Irp,
                (_DWORD)FileObject,
                v204,
                (__int64)v202,
                (__int64)FsContext);
              NtfsSnapshotScb((__int64)v3, (__int64)v202);
              v22 = (__int64)v202;
              v23 = *((_DWORD *)v202 + 64);
              if ( v23 == 128 && *(_WORD *)v202 == 1797
                || v23 == 160
                && *((_WORD *)v202 + 132) == 8
                && *(_QWORD *)v202[34] == 0x30003300490024LL
                && (unsigned __int16)(*(_WORD *)v202 - 1795) <= 1u )
              {
                FsRtlCheckOplock((POPLOCK)v202 + 11, Irp, 0, 0, 0);
                v22 = (__int64)v202;
              }
              if ( *(_WORD *)v22 == 1797 && *(_QWORD *)(v22 + 584) )
              {
                v45 = *(FILE_LOCK **)(v22 + 584);
                RequestorProcess = IoGetRequestorProcess(Irp);
                FsRtlFastUnlockAll(v45, FileObject, RequestorProcess, 0);
                v22 = (__int64)v202;
              }
              if ( (*(_DWORD *)(*(_QWORD *)(v22 + 192) + 4LL) & 0x4000005) == 1
                && *(_WORD *)v22 == 1797
                && (IsFastIoPossible = FsRtlOplockIsFastIoPossible((POPLOCK)(v22 + 88)),
                    v22 = (__int64)v202,
                    IsFastIoPossible) )
              {
                if ( *((_DWORD *)v202 + 113)
                  || (v51 = v202[73]) != 0 && *(_BYTE *)(v51 + 16)
                  || (v52 = v202[24], (*(_DWORD *)(v52 + 4) & 0x2000000) != 0)
                  || (v202[64] & 0x4000000) != 0
                  || v202[66]
                  || *(_QWORD *)(v52 + 40) )
                {
                  v24 = 2;
                }
                else
                {
                  v24 = 1;
                }
              }
              else
              {
                v24 = 0;
              }
              *(_BYTE *)(v22 + 5) = v24;
              if ( (v194 & 0x80000) == 0 || (v194 & 0x100000) != 0 || !NtfsIsFileStillValid(*(__int64 *)v200) )
              {
                FileObject->Flags |= 0x4000u;
                if ( (v194 & 0x80000) == 0 || !NtfsIsFileStillValid(*(__int64 *)v200) )
                  TruncateSize = &NtfsLarge0;
                goto LABEL_88;
              }
              NtfsUpdateScbFromFileObject((__int64)FileObject, (__int64)v202, 1);
              FileObject->Flags |= 0x4000u;
              if ( v203 )
                goto LABEL_88;
              if ( !v15
                || ((v25 = *((_DWORD *)v15 + 1), (v25 & 1) != 0)
                 || (*(_BYTE *)(v15[24] + 65LL) & 3) != 0 && (*(_DWORD *)(v15[6] + 4LL) & 0x20) != 0)
                && *((_DWORD *)v15 + 47) == 1 )
              {
                if ( (v194 & 0x100) != 0 && (*(_DWORD *)(*(_QWORD *)v200 + 4LL) & 0x8000) != 0 )
                {
                  NtfsPostSpecial((_DWORD)v3, v204, (unsigned int)NtfsDeleteUsnSpecial, v204 + 2144, 13);
                  BYTE1(v194) &= ~1u;
                  ++*(_WORD *)(*(_QWORD *)v200 + 188LL);
                  *(_DWORD *)(*(_QWORD *)v200 + 4LL) &= ~0x20u;
                  if ( v15 )
                  {
                    ClearFlagInterlocked((unsigned int *)v15 + 1, 1);
                  }
                  else
                  {
                    while ( 1 )
                    {
                      v152 = NtfsGetNextParentLcb((__int64)v3, *(__int64 *)v200, v15);
                      v15 = v152;
                      v209 = v152;
                      if ( !v152 )
                        break;
                      ClearFlagInterlocked((unsigned int *)v152 + 1, 1);
                    }
                  }
                  goto LABEL_76;
                }
                if ( (v194 & 0x100) != 0 )
                {
                  if ( v15 )
                  {
                    v223 = v15;
                  }
                  else
                  {
                    for ( i = *(_QWORD **)(*(_QWORD *)v200 + 48LL);
                          i != (_QWORD *)(*(_QWORD *)v200 + 48LL);
                          i = (_QWORD *)*i )
                    {
                      v223 = i - 7;
                      if ( (*((_DWORD *)i - 13) & 2) == 0 )
                      {
                        v66 = *(i - 4);
                        v207 = v66;
                        if ( v66 )
                          Fcb = *(_QWORD *)(v66 + 184);
                        goto LABEL_316;
                      }
                    }
                  }
                  v66 = v207;
LABEL_316:
                  if ( v66 )
                  {
                    v67 = v194;
                  }
                  else
                  {
                    v245 = 0;
                    memset(v242, 0, 0x58u);
                    v195 = v194 | 0x10;
                    v223 = 0;
                    if ( !NtfsLookupInFileRecord(
                            (__int64)v3,
                            *(__int64 *)v200,
                            (_DWORD *)(*(_QWORD *)v200 + 8LL),
                            48,
                            0,
                            0,
                            0,
                            0,
                            0,
                            (__int64)v242) )
                    {
                      NtfsAttachCorruption_BadOrOrphanFRS(
                        (__int64)v3,
                        2,
                        462152,
                        0,
                        (_DWORD *)(*(_QWORD *)v200 + 8LL),
                        *(__int64 *)v200,
                        0);
                      NtfsAttachRepairInfoPriv((__int64)v3, 256, 0, (struct _LIST_ENTRY *)0xFD00070D48LL);
                      if ( NtfsStatusDebugFlags )
                        NtfsStatusTraceAndDebugInternal((__int64)v3, 0xC0000102, 0x70D48u);
                      NtfsRaiseStatusInternal((__int64)v3, -1073741566, v200[0] + 8, v200[0], 462152);
                    }
                    v69 = v242[0] + *(unsigned __int16 *)(v242[0] + 20);
                    v70 = *(_DWORD *)(*(_QWORD *)v200 + 8LL);
                    if ( v70 == 5 || (v71 = *(_QWORD *)(*(_QWORD *)v200 + 320LL), *(_DWORD *)(v71 + 88) == v70) )
                      v71 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v200 + 96LL) + 6248LL);
                    LODWORD(CompletionRoutine) = 66;
                    Fcb = NtfsCreateFcb((__int64)v3, v204, v71, *(_QWORD *)v69, CompletionRoutine, 0);
                    v72 = NtfsCreateScb((__int64)v3, Fcb, 160, &NtfsFileNameIndex, 0, 0, 0);
                    v207 = (__int64)v72;
                    if ( (*((_DWORD *)v72 + 50) & 0x200) != 0 )
                    {
                      NtfsSnapshotScb((__int64)v3, (__int64)v72);
                      v72 = (__int16 *)v207;
                    }
                    *((_QWORD *)&v245 + 1) = v69 + 66;
                    LOWORD(v245) = 2 * *(unsigned __int8 *)(v69 + 64);
                    WORD1(v245) = v245;
                    NtfsCreateLcb(
                      (__int64)v3,
                      (__int64)v72,
                      *(__int64 *)v200,
                      (const void **)&v245,
                      *(_BYTE *)(v69 + 65),
                      0);
                    v201[0] = 1;
                    NtfsCleanupAttributeContext(v3, v242);
                    v67 = v195 & 0xEF;
                    v66 = v207;
                  }
                  LOBYTE(v194) = v67 & 0xFB;
                  LOBYTE(v247[23]) = 0;
                  if ( (v194 & 0x2000) != 0
                    || !v66
                    || !*((_QWORD *)FsContext + 9)
                    || *(int *)(v204 + 4) < 0
                    || (FileObject->Flags & 0x20000) != 0 )
                  {
                    NtfsDeleteFile((int)v3, v200[0], (__int64)v247, 0);
                  }
                  else
                  {
                    NtfsDeleteFile((int)v3, v200[0], (__int64)v247, (__int64)&v247[14]);
                    NtfsGetTunneledData(
                      v3,
                      *(_QWORD *)v200,
                      *(unsigned __int8 *)(*(_QWORD *)(*((_QWORD *)FsContext + 9) + 192LL) + 65LL),
                      &v247[14]);
                    v68 = (*((_DWORD *)FsContext + 1) & 0x4000000) == 0
                       && (*(_DWORD *)(*(_QWORD *)(v207 + 184) + 16LL) & 0x400) != 0;
                    FsRtlAddToTunnelCacheEx(
                      v204 + 4720,
                      *(_QWORD *)(*(_QWORD *)(v207 + 184) + 8LL),
                      v247,
                      &v247[2],
                      (BYTE1(v247[23]) != 0 ? 2 : 0) | v68,
                      80,
                      &v247[14]);
                  }
                  --*(_WORD *)(*(_QWORD *)v200 + 190LL);
                  LOBYTE(v194) = v194 | 0x20;
                  v223 = 0;
                  if ( !v203 )
                  {
                    v73 = BYTE1(v194);
                    if ( (v194 & 0x2000) == 0 )
                    {
                      NtfsReportDirNotify(
                        (__int64)v3,
                        *((_QWORD *)FsContext + 9),
                        v204,
                        (unsigned __int16 *)FsContext + 8,
                        *((unsigned __int16 *)FsContext + 16),
                        0,
                        1,
                        2,
                        Fcb,
                        0);
                      v73 = BYTE1(v194);
                    }
                    BYTE1(v194) = v73 | 2;
                    ClearFlagInterlocked((unsigned int *)FsContext + 1, 112);
                    TruncateSize = &NtfsLarge0;
                  }
LABEL_76:
                  if ( (v194 & 0x4000) != 0 || (v194 & 0x100) != 0 || v194 < 0 )
                    FsRtlCheckOplockEx((POPLOCK)(v207 + 88), Irp, 0x50u, 0, 0, 0);
                  if ( *((_DWORD *)v202 + 52) != 1 && (v194 & 0x800000) == 0
                    || !*(_WORD *)(*(_QWORD *)v200 + 188LL)
                    || v203 )
                  {
LABEL_85:
                    if ( v203 )
                      goto LABEL_86;
                    if ( *((_DWORD *)v202 + 52) != 1 )
                      goto LABEL_86;
                    if ( !*(_WORD *)(*(_QWORD *)v200 + 188LL) )
                      goto LABEL_86;
                    if ( (v194 & 0x400) != 0 )
                      goto LABEL_86;
                    if ( FileObject->SectionObjectPointer != (PSECTION_OBJECT_POINTERS)(v202[36] + 16LL) )
                      goto LABEL_86;
                    v56 = *((_DWORD *)v202 + 64);
                    if ( !v56 || v56 == 32 && v202[23] == *(_QWORD *)(*(_QWORD *)(v204 + 48) + 184LL) )
                      goto LABEL_86;
                    if ( (v202[25] & 1) == 0 )
                      goto LABEL_86;
                    BYTE2(v194) |= 1u;
                    if ( (v194 & 0x40000000) == 0
                      && (v194 & 0x4000) == 0
                      && (*(_DWORD *)(*(_QWORD *)v200 + 4LL) & 0x100) == 0 )
                    {
                      NtfsPrepareForUpdateDuplicate((__int64)v3, *(__int64 *)v200, (__int64 *)&v216, &v207, 1, 0);
                    }
                    v79 = (__int64)v202;
                    if ( (v202[25] & 8) != 0 )
                    {
                      if ( ((*((_DWORD *)v202 + 8) + 7) & 0xFFFFFFF8) < *((_DWORD *)v202 + 6) )
                      {
                        v169 = v194;
                        if ( (v194 & 0x10) != 0 )
                        {
                          NtfsCleanupAttributeContext(v3, v242);
                          v169 = v194;
                          v79 = (__int64)v202;
                        }
                        memset(v242, 0, 0x58u);
                        LOBYTE(v194) = v169 | 0x10;
                        if ( !NtfsLookupInFileRecord(
                                (__int64)v3,
                                *(_QWORD *)(v79 + 184),
                                (_DWORD *)(*(_QWORD *)(v79 + 184) + 8LL),
                                *(_DWORD *)(v79 + 256),
                                (const UNICODE_STRING *)(v79 + 264),
                                0,
                                0,
                                0,
                                0,
                                (__int64)v242)
                          && (v202[64] & 4) == 0 )
                        {
                          NtfsAttachCorruption_BadOrOrphanFRS(
                            (__int64)v3,
                            2,
                            463196,
                            0,
                            (_DWORD *)(v202[23] + 8LL),
                            v202[23],
                            0);
                          NtfsAttachRepairInfoPriv((__int64)v3, 512, 0, (struct _LIST_ENTRY *)0xA90007115CLL);
                          if ( NtfsStatusDebugFlags )
                            NtfsStatusTraceAndDebugInternal((__int64)v3, 0xC0000102, 0x7115Cu);
                          NtfsRaiseStatusInternal((__int64)v3, -1073741566, v202[23] + 8, v202[23], 463196);
                        }
                        LODWORD(CompletionRoutined) = 0;
                        NtfsChangeAttributeValue(
                          (__int64)v3,
                          *(__int64 *)v200,
                          *((_DWORD *)v202 + 8),
                          0,
                          (SIZE_T)CompletionRoutined,
                          1,
                          1,
                          0,
                          0,
                          v242);
                        v170 = (__int64)v202;
                        v171 = (*((_DWORD *)v202 + 8) + 7) & 0xFFFFFFF8;
                        v172 = *((_DWORD *)v202 + 50);
                        if ( (v172 & 0x20000) != 0 && v202[3] > v171 && v202[58] > v171 )
                        {
                          if ( (v172 & 0x200) != 0 )
                            v170 = (__int64)v202;
                          *(_QWORD *)(v170 + 464) = v171;
                          v170 = (__int64)v202;
                        }
                        *(_QWORD *)(v170 + 24) = v171;
                        v202[59] = v171;
                        v79 = (__int64)v202;
                      }
                      goto LABEL_385;
                    }
                    v80 = v202[3];
                    if ( !v80 )
                    {
LABEL_385:
                      NtfsUpdateScbFromFileObject((__int64)FileObject, v79, 1);
LABEL_86:
                      v26 = *((_DWORD *)v202 + 51);
                      if ( v26 )
                      {
                        if ( *((_DWORD *)v202 + 52) == v26 + 1
                          && !*((_DWORD *)v202 + 113)
                          && (*((_BYTE *)FsContext + 104) & 7) != 0 )
                        {
                          v173 = v202[36];
                          if ( *(_QWORD *)(v173 + 16) )
                          {
                            if ( !*(_QWORD *)(v173 + 32)
                              && (FileObject->Flags & 8) == 0
                              && !v203
                              && MmCanFileBeTruncated((PSECTION_OBJECT_POINTERS)(v173 + 16), 0)
                              && (*(_DWORD *)(v202[23] + 4LL) & 0x100) == 0
                              && (v194 & 0x4000) == 0 )
                            {
                              NtfsCheckpointCurrentTransaction((__int64)v3);
                              if ( v201[0] )
                              {
                                NtfsReleaseFcbEx((__int64)v3, *(_QWORD *)(v207 + 184), 0);
                                v201[0] = 0;
                              }
                              NtfsReleaseSharedResources((__int64)v3);
                              NtfsFlushAndPurgeScb(v3, v202);
                              v3[3].offset.idxRecord = 0;
                            }
                          }
                        }
                      }
                      v22 = *(_QWORD *)v200;
                      if ( *(_DWORD *)(*(_QWORD *)v200 + 24LL) == 1
                        && (v194 & 4) != 0
                        && *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v200 + 96LL) + 8428LL) <= (unsigned int)NtfsMaxDelayCloseCount
                        && !v203
                        && (*(_DWORD *)(*(_QWORD *)v200 + 4LL) & 4) == 0
                        && (v202[25] & 0x1000000) == 0 )
                      {
                        SetFlagInterlocked((unsigned int *)v202 + 50, 0x200000u);
                      }
                      goto LABEL_88;
                    }
                    v81 = *(unsigned int *)(v204 + 480);
                    v82 = (v81 + v202[4]) >> *(_BYTE *)(v204 + 488);
                    if ( (v81 + v80) >> *(_BYTE *)(v204 + 488) == v82 )
                    {
LABEL_384:
                      v244 = *(_QWORD *)(v79 + 32);
                      TruncateSize = (PLARGE_INTEGER)&v244;
                      goto LABEL_385;
                    }
                    if ( (v202[25] & 0x20000) != 0 )
                    {
                      if ( !MmCanFileBeTruncated(FileObject->SectionObjectPointer, (PLARGE_INTEGER)v202 + 4) )
                      {
                        if ( (v194 & 8) != 0 )
                        {
                          *((_DWORD *)v202 + 50) &= ~1u;
                          BYTE2(v194) &= ~1u;
                        }
                        goto LABEL_871;
                      }
                      v79 = (__int64)v202;
                    }
                    NtfsDeleteAllocation((__int64)v3, FileObject, v79, v82, 0x7FFFFFFFFFFFFFFFLL, 1u, 1);
LABEL_871:
                    v79 = (__int64)v202;
                    goto LABEL_384;
                  }
                  if ( (v194 & 0x400) == 0 && (v194 & 0x800000) == 0 )
                  {
                    if ( *((_DWORD *)v202 + 64) && (v202[25] & 4) != 0 )
                    {
                      if ( (v194 & 0x40000000) == 0
                        && (v194 & 0x4000) == 0
                        && (*(_DWORD *)(*(_QWORD *)v200 + 4LL) & 0x100) == 0 )
                      {
                        NtfsPrepareForUpdateDuplicate((__int64)v3, *(__int64 *)v200, (__int64 *)&v216, &v207, 1, 0);
                      }
                      if ( (v202[25] & 8) != 0 )
                      {
                        memset(v242, 0, 0x58u);
                        LOBYTE(v194) = v194 | 0x10;
                        if ( !NtfsLookupInFileRecord(
                                (__int64)v3,
                                v202[23],
                                (_DWORD *)(v202[23] + 8LL),
                                *((_DWORD *)v202 + 64),
                                (const UNICODE_STRING *)(v202 + 33),
                                0,
                                0,
                                0,
                                0,
                                (__int64)v242)
                          && (v202[64] & 4) == 0 )
                        {
                          NtfsAttachCorruption_BadOrOrphanFRS(
                            (__int64)v3,
                            2,
                            462993,
                            0,
                            (_DWORD *)(v202[23] + 8LL),
                            v202[23],
                            0);
                          NtfsAttachRepairInfoPriv((__int64)v3, 512, 0, (struct _LIST_ENTRY *)0xA900071091LL);
                          if ( NtfsStatusDebugFlags )
                            NtfsStatusTraceAndDebugInternal((__int64)v3, 0xC0000102, 0x71091u);
                          NtfsRaiseStatusInternal((__int64)v3, -1073741566, v202[23] + 8, v202[23], 462993);
                        }
                        LODWORD(CompletionRoutineb) = 0;
                        NtfsChangeAttributeValue(
                          (__int64)v3,
                          *(__int64 *)v200,
                          *((_DWORD *)v202 + 8),
                          0,
                          (SIZE_T)CompletionRoutineb,
                          1,
                          1,
                          0,
                          0,
                          v242);
                        v74 = (__int64)v202;
                        if ( ((*((_DWORD *)v202 + 8) + 7) & 0xFFFFFFF8) != *((_DWORD *)v202 + 6) )
                        {
                          v92 = (*((_DWORD *)v202 + 8) + 7) & 0xFFFFFFF8;
                          v93 = *((_DWORD *)v202 + 50);
                          if ( (v93 & 0x20000) != 0 && v202[3] > v92 && v202[58] > v92 )
                          {
                            if ( (v93 & 0x200) != 0 )
                              v74 = (__int64)v202;
                            *(_QWORD *)(v74 + 464) = v92;
                            v74 = (__int64)v202;
                          }
                          *(_QWORD *)(v74 + 24) = v92;
                          v74 = (__int64)v202;
                        }
                      }
                      else
                      {
                        NtfsWriteFileSizes((__int64)v3, (__int64)v202, 0, 0, 1, 1);
                        v74 = (__int64)v202;
                      }
                      NtfsUpdateScbFromFileObject((__int64)FileObject, v74, 1);
                    }
                    goto LABEL_85;
                  }
                  if ( (v194 & 0x40000000) == 0
                    && *(_QWORD *)(*(_QWORD *)v200 + 120LL)
                    && (v194 & 0x4000) == 0
                    && (*(_DWORD *)(*(_QWORD *)v200 + 4LL) & 0x100) == 0 )
                  {
                    NtfsPrepareForUpdateDuplicate((__int64)v3, *(__int64 *)v200, (__int64 *)&v216, &v207, 1, 0);
                  }
                  if ( *((_DWORD *)v202 + 64) )
                  {
                    if ( (v194 & 0x10) != 0 )
                      NtfsCleanupAttributeContext(v3, v242);
                    if ( *((_DWORD *)v202 + 64) == 128
                      && ((v202[25] & 0x6000000) != 0 || v202[79] == -1)
                      && xmmword_1400957B0 )
                    {
                      xmmword_1400957B0(v3, *(_QWORD *)v200);
                    }
                    memset(v242, 0, 0x58u);
                    v199 = v194 | 0x10;
                    if ( !NtfsLookupInFileRecord(
                            (__int64)v3,
                            v202[23],
                            (_DWORD *)(v202[23] + 8LL),
                            *((_DWORD *)v202 + 64),
                            (const UNICODE_STRING *)(v202 + 33),
                            0,
                            0,
                            0,
                            0,
                            (__int64)v242)
                      && (v202[64] & 4) == 0 )
                    {
                      NtfsAttachCorruption_BadOrOrphanFRS(
                        (__int64)v3,
                        2,
                        462728,
                        0,
                        (_DWORD *)(v202[23] + 8LL),
                        v202[23],
                        0);
                      NtfsAttachRepairInfoPriv((__int64)v3, 512, 0, (struct _LIST_ENTRY *)0xA900070F88LL);
                      if ( NtfsStatusDebugFlags )
                        NtfsStatusTraceAndDebugInternal((__int64)v3, 0xC0000102, 0x70F88u);
                      NtfsRaiseStatusInternal((__int64)v3, -1073741566, v202[23] + 8, v202[23], 462728);
                    }
                    v155 = *(_WORD *)(v242[0] + 12);
                    do
                    {
                      NtfsDeleteAttributeRecord((__int64)v3, *(__int64 *)v200, 15, (int **)v242);
                      if ( v242[5] )
                      {
                        LODWORD(Size) = 0;
                        v156 = NtfsLookupExternalAttribute(
                                 (__int64)v3,
                                 v202[23],
                                 *((_DWORD *)v202 + 64),
                                 (PCUNICODE_STRING)(v202 + 33),
                                 0,
                                 0,
                                 0,
                                 Size,
                                 (unsigned __int64)v242);
                      }
                      else
                      {
                        v156 = NtfsLookupInFileRecord(
                                 (__int64)v3,
                                 v202[23],
                                 0,
                                 *((_DWORD *)v202 + 64),
                                 (const UNICODE_STRING *)(v202 + 33),
                                 0,
                                 0,
                                 0,
                                 0,
                                 (__int64)v242);
                      }
                    }
                    while ( v156 );
                    NtfsCleanupAttributeContext(v3, v242);
                    LOBYTE(v194) = v199 & 0xEF;
                    if ( v155 >= 0 && *((__int16 *)v202 + 230) >= 0
                      || (unsigned __int8)NtfsIsSparseStreamRemaining((int)v3, v200[0]) )
                    {
                      v159 = 0x200000;
                    }
                    else
                    {
                      v157 = NtfsAddStructToRollbackList((__int64)v3, 1827, *(__int64 *)v200, 1);
                      v158 = ~v157[11] & 0x200;
                      v157[11] |= v158;
                      v157[10] |= v158 & *(_DWORD *)(*(_QWORD *)v200 + 176LL);
                      v157[1] |= 0x10u;
                      *(_DWORD *)(*(_QWORD *)v200 + 176LL) &= ~0x200u;
                      *(_DWORD *)(*(_QWORD *)v200 + 184LL) |= 4u;
                      *(_DWORD *)(*(_QWORD *)v200 + 4LL) |= 0x10u;
                      v3[2].ullOffset |= 4uLL;
                      v159 = 2129920;
                    }
                    NtfsPostUsnChangeWithOverrideOption((__int64)v3, *(__int64 *)v200, v159, 0, 0, 0, 0);
                  }
                  if ( !v203 )
                  {
                    if ( (v194 & 0x800000) != 0 )
                    {
                      v243 = 0;
                      v243 = TxfWriteAttributeLogRecord(
                               (_DWORD)v3,
                               v200[0],
                               *((_DWORD *)v202 + 64),
                               (int)v202 + 264,
                               0,
                               0,
                               0,
                               0,
                               16);
                      TxfUpdateTxfDataAttributeMembers(
                        (__int64)v3,
                        *(__int64 *)v200,
                        0,
                        0,
                        0,
                        0,
                        (*(_DWORD *)(*(_QWORD *)v200 + 4LL) & 0x100000) == 0,
                        &v243,
                        0,
                        0,
                        0,
                        0,
                        0);
                    }
                    NtfsCheckpointCurrentTransaction((__int64)v3);
                    LOBYTE(v194) = v194 | 0x40;
                  }
                  if ( *((_BYTE *)v202 + 460) || (v202[64] & 1) != 0 )
                    v202[58] = 0;
                  if ( (v202[25] & 0x20000) != 0 && (__int64)v202[3] > 0 && (__int64)v202[58] > 0 )
                    v202[58] = 0;
                  v202[3] = 0;
                  v160 = (__int64)v202;
                  v161 = *((_DWORD *)v202 + 50);
                  if ( (v161 & 0x20000) == 0 || (__int64)v202[4] >= 0 )
                    goto LABEL_843;
                  v162 = 0;
                  if ( (__int64)v202[58] <= 0 )
                    v162 = v202[58];
                  if ( v162 <= v202[5] )
                  {
LABEL_843:
                    *(_QWORD *)(v160 + 32) = 0;
                    v166 = (__int64)v202;
                    if ( (v202[25] & 0x200) != 0 )
                      v166 = (__int64)v202;
                    v167 = *(_DWORD *)(v166 + 200);
                    if ( (v167 & 0x20000) == 0 )
                      goto LABEL_858;
                    v168 = *(_QWORD *)(v166 + 464);
                    if ( v168 >= 0 )
                    {
                      if ( *(__int64 *)(v166 + 40) <= 0 )
                        goto LABEL_858;
                      if ( *(_QWORD *)(*(_QWORD *)(v166 + 288) + 16LL) )
                      {
                        if ( v168 <= 0 )
                          goto LABEL_858;
                        if ( (v167 & 0x200) == 0 )
                        {
LABEL_857:
                          *(_QWORD *)(v166 + 464) = 0;
                          v166 = (__int64)v202;
LABEL_858:
                          *(_QWORD *)(v166 + 40) = 0;
                          *((_DWORD *)v202 + 64) = 0;
                          if ( (v194 & 0x800000) == 0 || (*(_DWORD *)(v202[66] + 24LL) & 1) != 0 )
                          {
                            *((_DWORD *)v202 + 128) |= 0x440u;
                            TruncateSize = &NtfsLarge0;
                          }
                          else
                          {
                            *((_DWORD *)v202 + 128) |= 0x200000u;
                            *(_DWORD *)(v202[66] + 24LL) |= 2u;
                          }
                          *((_DWORD *)v202 + 128) &= 0xFFFFE5FF;
                          NtfsUpdateFileTimestampsForChange(*(_QWORD *)v200, FsContext, 0x400000);
                          FileObject->Flags &= ~0x4000u;
                          NtfsUpdateScbFromFileObject((__int64)FileObject, (__int64)v202, 1);
                          FileObject->Flags |= 0x4000u;
                          goto LABEL_85;
                        }
                      }
                      else if ( (v167 & 0x200) == 0 || !v168 )
                      {
                        goto LABEL_857;
                      }
                    }
                    else if ( (v167 & 0x200) == 0 )
                    {
                      goto LABEL_857;
                    }
                    v166 = (__int64)v202;
                    goto LABEL_857;
                  }
                  if ( (v161 & 0x200) != 0 )
                    v160 = (__int64)v202;
                  v163 = *(_DWORD *)(v160 + 200);
                  if ( (v163 & 0x20000) != 0 )
                  {
                    v164 = *(_QWORD *)(v160 + 464);
                    if ( v164 < v162 )
                    {
                      if ( (v163 & 0x200) == 0 )
                        goto LABEL_841;
                      goto LABEL_840;
                    }
                    if ( *(_QWORD *)(v160 + 40) > v162 )
                    {
                      if ( *(_QWORD *)(*(_QWORD *)(v160 + 288) + 16LL) )
                      {
                        if ( v162 == 0x7FFFFFFFFFFFFFFFLL )
                        {
                          if ( (v163 & 0x200) != 0 && v164 != 0x7FFFFFFFFFFFFFFFLL )
                            v160 = (__int64)v202;
                          *(_QWORD *)(v160 + 464) = 0x7FFFFFFFFFFFFFFFLL;
                          v160 = (__int64)v202;
                        }
                        else
                        {
                          v165 = (v162 + 4095) & 0xFFFFFFFFFFFFF000uLL;
                          if ( v165 < v164 )
                          {
                            if ( (v163 & 0x200) != 0 )
                              v160 = (__int64)v202;
                            *(_QWORD *)(v160 + 464) = v165;
                            v160 = (__int64)v202;
                          }
                        }
                        goto LABEL_842;
                      }
                      if ( (v163 & 0x200) == 0 || v164 == v162 )
                        goto LABEL_841;
LABEL_840:
                      v160 = (__int64)v202;
LABEL_841:
                      *(_QWORD *)(v160 + 464) = v162;
                      v160 = (__int64)v202;
                    }
                  }
LABEL_842:
                  *(_QWORD *)(v160 + 40) = v162;
                  v160 = (__int64)v202;
                  goto LABEL_843;
                }
                if ( !v15 )
                  goto LABEL_76;
                BYTE1(v194) |= 0x40u;
                if ( (v194 & 0x10000000) != 0 )
                {
                  v57 = (__int64)v223;
                }
                else
                {
                  v154 = NtfsFindMatchingLcbPair(v15);
                  v57 = (__int64)v154;
                  v223 = v154;
                  if ( v154 && *((_DWORD *)v154 + 47) )
                    BYTE1(v194) &= ~0x40u;
                }
                if ( (v194 & 0x4000) != 0 && *(_WORD *)(*(_QWORD *)v200 + 190LL) > 1u )
                {
                  NtfsAcquireExclusiveScbEx((__int64)v3, v207, 0);
                  v201[0] = 1;
                  v99 = *(_QWORD *)v200;
                  if ( *(_QWORD *)(*(_QWORD *)v200 + 120LL) )
                  {
                    NtfsAcquireSharedFcb(
                      (__int64)v3,
                      *(_QWORD *)(*(_QWORD *)(v204 + 160) + 184LL),
                      *(_QWORD *)(v204 + 160),
                      0);
                    LOBYTE(v194) = v194 | 2;
                    NtfsAcquireQuotaControl(v3);
                    v99 = *(_QWORD *)v200;
                  }
                  LOBYTE(v194) = v194 & 0xFB;
                  if ( (v194 & 0x10000000) != 0 )
                  {
                    NtfsCheckpointCurrentTransaction((__int64)v3);
                    LOBYTE(v194) = v194 | 0x20;
                  }
                  else
                  {
                    v100 = 0;
                    if ( (*(_BYTE *)(v15[24] + 65LL) & 3) != 2 )
                      v100 = v15[24];
                    NtfsPostUsnChangeWithOverrideOption((__int64)v3, v99, -2147418112, 0, 0, 0, v100);
                    LOBYTE(v247[23]) = 0;
                    if ( (v194 & 0x2000) != 0 || *(int *)(v204 + 4) < 0 || (FileObject->Flags & 0x20000) != 0 )
                    {
                      NtfsRemoveLink((__int64)v3, *(__int64 *)v200, v207, (const void **)v15 + 9, (__int64)v247, 0);
                    }
                    else
                    {
                      NtfsRemoveLink(
                        (__int64)v3,
                        *(__int64 *)v200,
                        v207,
                        (const void **)v15 + 9,
                        (__int64)v247,
                        (__int64)&v247[14]);
                      NtfsGetTunneledData(v3, *(_QWORD *)v200, *(unsigned __int8 *)(v15[24] + 65LL), &v247[14]);
                      if ( (*((_DWORD *)FsContext + 1) & 0x4000000) != 0
                        || (v101 = 1, (*(_DWORD *)(*(_QWORD *)(v207 + 184) + 16LL) & 0x400) == 0) )
                      {
                        v101 = 0;
                      }
                      FsRtlAddToTunnelCacheEx(
                        v204 + 4720,
                        *(_QWORD *)(*(_QWORD *)(v207 + 184) + 8LL),
                        v247,
                        &v247[2],
                        v101 | *(_BYTE *)(v15[24] + 65LL) & 2,
                        80,
                        &v247[14]);
                    }
                    NtfsCheckpointCurrentTransaction((__int64)v3);
                    LOBYTE(v194) = v194 | 0x20;
                    --*(_WORD *)(*(_QWORD *)v200 + 190LL);
                    NtfsRemovePrefix((__int64)v3, (__int64)v15);
                    if ( (*((_DWORD *)v15 + 1) & 0x20) != 0 )
                    {
                      NtfsRemoveHashEntry(v3, *(_QWORD *)(v15[6] + 96LL) + 4968LL, *((unsigned int *)v15 + 46), v15);
                      *((_DWORD *)v15 + 46) = 0;
                      ClearFlagInterlocked((unsigned int *)v15 + 1, 32);
                    }
                    SetFlagInterlocked((unsigned int *)v15 + 1, 2u);
                    *((_DWORD *)v15 + 45) = 0;
                    *((_DWORD *)v15 + 39) = 0;
                    if ( v57 )
                    {
                      NtfsRemovePrefix((__int64)v3, v57);
                      if ( (*(_DWORD *)(v57 + 4) & 0x20) != 0 )
                      {
                        NtfsRemoveHashEntry(
                          v3,
                          *(_QWORD *)(*(_QWORD *)(v57 + 48) + 96LL) + 4968LL,
                          *(unsigned int *)(v57 + 184),
                          v57);
                        *(_DWORD *)(v57 + 184) = 0;
                        ClearFlagInterlocked((unsigned int *)(v57 + 4), 32);
                      }
                      SetFlagInterlocked((unsigned int *)(v57 + 4), 2u);
                      *(_DWORD *)(v57 + 180) = 0;
                      *(_DWORD *)(v57 + 156) = 0;
                    }
                  }
                  NtfsUpdateFcbTimestamps(Fcb, -1610612720);
                  if ( (v194 & 0x2000) == 0 && (v203 & 0x80000000) == 0 && (v194 & 0x10000000) == 0 )
                    NtfsReportDirNotify(
                      (__int64)v3,
                      *((_QWORD *)FsContext + 9),
                      v204,
                      (unsigned __int16 *)FsContext + 8,
                      *((unsigned __int16 *)FsContext + 16),
                      0,
                      1,
                      2,
                      Fcb,
                      0);
                  v216 = 0;
                  if ( (v203 & 0x80000000) == 0 )
                    NtfsUpdateFileTimestampsForChange(*(_QWORD *)v200, FsContext, 0);
                  FileObject->Flags &= ~0x4000u;
                  NtfsUpdateScbFromFileObject((__int64)FileObject, (__int64)v202, 1);
                  FileObject->Flags |= 0x4000u;
                  goto LABEL_76;
                }
                if ( (v194 & 0x4000) == 0 )
                  goto LABEL_76;
                BYTE1(v194) &= ~0x40u;
                if ( (*(_DWORD *)(*(_QWORD *)v200 + 176LL) & 0x10000000) != 0
                  || (*((_DWORD *)FsContext + 2) & 0x10000) == 0 && !*(_QWORD *)(*(_QWORD *)v200 + 352LL) )
                {
                  goto LABEL_76;
                }
                if ( (*((_DWORD *)v15 + 1) & 0x40) != 0 )
                  goto LABEL_76;
                if ( v3[50].ullOffset )
                  goto LABEL_76;
                v58 = *(_QWORD *)(v204 + 200);
                if ( v15[3] == v58 || !v58 )
                  goto LABEL_76;
              }
              else
              {
                if ( (*((_DWORD *)v15 + 1) & 1) == 0
                  && ((*(_BYTE *)(v15[24] + 65LL) & 3) == 0 || (*(_DWORD *)(v15[6] + 4LL) & 0x20) == 0) )
                {
                  goto LABEL_76;
                }
                if ( (*((_DWORD *)FsContext + 2) & 0x10000) == 0 || (v25 & 0x40) != 0 )
                  goto LABEL_76;
                if ( v3[50].ullOffset )
                  goto LABEL_76;
                v65 = *(_QWORD *)(v204 + 200);
                if ( v15[3] == v65 || !v65 )
                  goto LABEL_76;
              }
              NtfsRenameToPrivateDir(
                (__int64)v3,
                (__int64)Irp,
                *(__int64 *)v200,
                (__int64)v202,
                (__int64)FsContext,
                (__int64)v15,
                v207,
                v201);
              HIBYTE(v194) |= 0x80u;
              goto LABEL_76;
            }
            if ( (v18 & 2) == 0 )
            {
              v146 = (__int64)v202;
              v228 = (volatile signed __int32 *)v202;
              _InterlockedIncrement((volatile signed __int32 *)v202 + 53);
              v198 = v194 | 0x80;
              if ( !TxfCantFlushDefaultReaderImageSection(v146, MmFlushForDelete) )
              {
                v147 = *(_QWORD *)(v146 + 288);
                if ( !*(_QWORD *)(v147 + 32)
                  || MmFlushImageSection((PSECTION_OBJECT_POINTERS)(v147 + 16), MmFlushForDelete) )
                {
                  SetFlagInterlocked((unsigned int *)v202 + 50, 2u);
                  BYTE2(v194) |= 0x20u;
                }
              }
              _InterlockedDecrement((volatile signed __int32 *)(v146 + 212));
              LOBYTE(v194) = v198 & 0x7F;
              goto LABEL_462;
            }
            v219 = 0;
            v220 = 0;
            if ( (*((_DWORD *)v15 + 1) & 1) != 0
              || (*(_BYTE *)(v15[24] + 65LL) & 3) != 0 && (*(_DWORD *)(v15[6] + 4LL) & 0x20) != 0 )
            {
              v141 = (unsigned int *)((char *)FsContext + 8);
              if ( (*((_DWORD *)FsContext + 2) & 0x20000) != 0 )
                SetFlagInterlocked(v141, 0x10000u);
              else
                ClearFlagInterlocked(v141, 0x10000);
              goto LABEL_462;
            }
            v94 = *(_QWORD *)v200;
            if ( (*(_DWORD *)(*(_QWORD *)v200 + 176LL) & 0x10000000) != 0 )
            {
              if ( !(unsigned __int8)NtfsIsLinkDeleteable((_DWORD)v3, v200[0]) )
              {
LABEL_462:
                ClearFlagInterlocked((unsigned int *)FsContext + 1, 0x40000);
                goto LABEL_37;
              }
              v94 = *(_QWORD *)v200;
            }
            v228 = 0;
            while ( 1 )
            {
              v142 = (volatile signed __int32 *)NtfsGetNextChildScb(v94, (__int64)v228, 0);
              v143 = v142;
              v228 = v142;
              if ( !v142 )
                break;
              _InterlockedIncrement(v142 + 53);
              v197 = v194 | 0x80;
              if ( *((_DWORD *)v142 + 64) == 128 && (v142[128] & 0x1000040) == 0 )
              {
                if ( TxfCantFlushDefaultReaderImageSection((__int64)v142, MmFlushForDelete)
                  || (v144 = *((_QWORD *)v143 + 36), *(_QWORD *)(v144 + 32))
                  && !MmFlushImageSection((PSECTION_OBJECT_POINTERS)(v144 + 16), MmFlushForDelete) )
                {
                  _InterlockedDecrement(v143 + 53);
                  LOBYTE(v194) = v197 & 0x7F;
                  break;
                }
              }
              _InterlockedDecrement(v143 + 53);
              LOBYTE(v194) = v197 & 0x7F;
              v94 = *(_QWORD *)v200;
            }
            if ( !v228 )
            {
              if ( (*(_BYTE *)(v15[24] + 65LL) & 3) != 0 )
                *(_DWORD *)(*(_QWORD *)v200 + 4LL) |= 0x20u;
              --*(_WORD *)(*(_QWORD *)v200 + 188LL);
              SetFlagInterlocked((unsigned int *)v15 + 1, 1u);
              v145 = (unsigned int *)((char *)FsContext + 8);
              if ( (*((_DWORD *)FsContext + 2) & 0x20000) != 0 )
                SetFlagInterlocked(v145, 0x10000u);
              else
                ClearFlagInterlocked(v145, 0x10000);
              BYTE2(v194) |= 0x20u;
              if ( (*(_DWORD *)(*(_QWORD *)v200 + 176LL) & 0x10000000) != 0 )
                FsRtlNotifyFilterChangeDirectoryLite(v202 + 96, v202 + 94, 0, 0, 0, 0, 0, 0, 0);
            }
            goto LABEL_462;
          }
          NtfsReleaseFcbEx((__int64)v3, v202[23], 0);
          v102 = *(_QWORD *)v200;
          if ( NtfsAcquirePagingResourceExclusive((__int64)v3, *(__int64 *)v200, 1u) )
          {
            v103 = 0;
            v233 = 0;
            while ( v103 < 2 )
            {
              v104 = &v3[v103];
              v105 = v104[6];
              if ( !v105.ullOffset || v105.ullOffset == v102 )
              {
                v104[6].ullOffset = v102;
                break;
              }
              v233 = ++v103;
            }
          }
        }
        NtfsAcquireExclusiveFcb((__int64)v3, v202[23], (__int64)v202, 8);
        goto LABEL_20;
      }
    }
    else if ( (v3[1].offset.cidContainer & 0x100) != 0 )
    {
      LOBYTE(v6) = 1;
      NtfsAcquireExclusiveVcb(v3, v204, v6);
      goto LABEL_8;
    }
    NtfsAcquireSharedVcb((__int64)v3, v204, 1);
    goto LABEL_8;
  }
  FileObject->Flags |= 0x4000u;
  NtfsCompleteCleanupRequest(v3, Irp, v203);
  return v203;
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
