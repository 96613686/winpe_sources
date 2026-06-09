# NtfsCommonCleanup

- ea: `0x1401c3750`
- end: `0x1401c9a85`
- name: `NtfsCommonCleanup`
- size: `25397`
- prototype: `__int64 __fastcall(int)`
- caller_count: `3`
- callee_count: `95`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140015d10`
- `0x1401c3130`
- `0x1401c3370`

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
- `0x1400592c0`
- `0x1400593e0`
- `0x140059740`
- `0x1400c6844`
- `0x1400f8f30`
- `0x140125100`
- `0x140126220`
- `0x14012a000`
- `0x14012bac0`
- `0x14012bb48`
- `0x14012d1a0`
- `0x14012f3ec`
- `0x14012f980`
- `0x1401305a0`
- `0x140132210`
- `0x140138c70`
- `0x14013c320`
- `0x1401403d0`
- `0x140141400`
- `0x140141a3c`
- `0x140141e90`

## import_xrefs

- `ntoskrnl!FsRtlCheckOplock` at `0x1401c4826`
- `ntoskrnl!FsRtlCheckOplock` at `0x1401c49f1`
- `ntoskrnl!FsRtlCheckOplock` at `0x1401c4826`
- `ntoskrnl!FsRtlCheckOplock` at `0x1401c49f1`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401c6914`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401c6914`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401c9718`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1402af94a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401c9718`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1402af94a`
- `ntoskrnl!CcUninitializeCacheMap` at `0x1401c4cc2`
- `ntoskrnl!CcUninitializeCacheMap` at `0x1401c4cc2`
- `ntoskrnl!KeBugCheckEx` at `0x1401c455d`
- `ntoskrnl!KeBugCheckEx` at `0x1401c455d`
- `ntoskrnl!CcPurgeCacheSection` at `0x1401c93f3`
- `ntoskrnl!CcPurgeCacheSection` at `0x1401c93f3`
- `ntoskrnl!FsRtlAddToTunnelCacheEx` at `0x1401c5054`
- `ntoskrnl!FsRtlAddToTunnelCacheEx` at `0x1401c62ec`
- `ntoskrnl!FsRtlAddToTunnelCacheEx` at `0x1401c7314`
- `ntoskrnl!FsRtlAddToTunnelCacheEx` at `0x1401c5054`
- `ntoskrnl!FsRtlAddToTunnelCacheEx` at `0x1401c62ec`
- `ntoskrnl!FsRtlAddToTunnelCacheEx` at `0x1401c7314`
- `ntoskrnl!MmFlushImageSection` at `0x1401c784e`
- `ntoskrnl!MmFlushImageSection` at `0x1401c7998`
- `ntoskrnl!MmFlushImageSection` at `0x1401c784e`
- `ntoskrnl!MmFlushImageSection` at `0x1401c7998`
- `ntoskrnl!FsRtlNotifyFilterChangeDirectoryLite` at `0x1401c793f`
- `ntoskrnl!FsRtlNotifyFilterChangeDirectoryLite` at `0x1401c793f`
- `ntoskrnl!FsRtlNotifyCleanup` at `0x1401c7ee5`
- `ntoskrnl!FsRtlNotifyCleanup` at `0x1401c7f39`
- `ntoskrnl!FsRtlNotifyCleanup` at `0x1401c7ee5`
- `ntoskrnl!FsRtlNotifyCleanup` at `0x1401c7f39`
- `ntoskrnl!FsRtlDeleteKeyFromTunnelCache` at `0x1401c5980`
- `ntoskrnl!FsRtlDeleteKeyFromTunnelCache` at `0x1401c5980`
- `ntoskrnl!FsRtlFastUnlockAll` at `0x1401c459e`
- `ntoskrnl!FsRtlFastUnlockAll` at `0x1401c459e`
- `ntoskrnl!IoGetRequestorProcess` at `0x1401c4586`
- `ntoskrnl!IoGetRequestorProcess` at `0x1401c4586`
- `ntoskrnl!FsRtlHeatLogIo` at `0x1401c6665`
- `ntoskrnl!FsRtlHeatLogIo` at `0x1401c6665`
- `ntoskrnl!MmForceSectionClosed` at `0x1401c60c8`
- `ntoskrnl!MmForceSectionClosed` at `0x1401c9421`
- `ntoskrnl!MmForceSectionClosed` at `0x1401c60c8`
- `ntoskrnl!MmForceSectionClosed` at `0x1401c9421`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1401c9a0f`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1402afaed`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1401c9a0f`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1402afaed`
- `ntoskrnl!IoRaiseInformationalHardError` at `0x1402cba99`
- `ntoskrnl!IoRaiseInformationalHardError` at `0x1402cba99`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x1401c470a`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x1401c470a`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1401c9747`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1402af977`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1401c9747`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1402af977`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401c551d`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401c551d`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401c9772`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401c997c`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402af99f`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402afa47`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401c9772`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401c997c`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402af99f`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402afa47`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401c9a22`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402afb0f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401c9a22`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402afb0f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c6bbf`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c6db9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c717c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c766a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c7ac8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c7ae5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c906e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c9133`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c9354`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c9473`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c6bbf`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c6db9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c717c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c766a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c7ac8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c7ae5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c906e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c9133`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c9354`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401c9473`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c6c9a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c6fe0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c71ae`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c7770`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c7b4e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c7b69`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c90be`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c9174`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c92bb`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c93bf`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c9445`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c94bc`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c995a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402af4ed`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402af511`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402afa24`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c6c9a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c6fe0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c71ae`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c7770`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c7b4e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c7b69`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c90be`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c9174`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c92bb`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c93bf`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c9445`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c94bc`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401c995a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402af4ed`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402af511`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402afa24`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1401c3d17`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1401c3ea9`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1401c4348`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1401c3d17`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1401c3ea9`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1401c4348`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402cba70`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402cba70`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402cbab2`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402cbab2`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1401c8ade`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1401c8e2a`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1401c8ade`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1401c8e2a`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401c927e`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401c927e`

## string_xrefs

- `0x1401c676f`: `NtfsCommonCleanup`

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
  __int64 v11; // r9
  __int64 v12; // r12
  __int64 v13; // rdi
  unsigned int v14; // ecx
  __int64 v15; // rdx
  __int64 v16; // rax
  int v17; // r9d
  char *v18; // rcx
  ULONG *p_Flags; // rdi
  __int64 v20; // r14
  __int64 v21; // rax
  __int64 v22; // rcx
  int v23; // ecx
  __int64 v24; // rax
  __int64 v25; // r8
  __int64 v26; // rdx
  int v27; // eax
  __int64 v28; // rdx
  int v29; // eax
  char v30; // al
  __int64 v31; // r8
  __int64 v32; // r8
  int v33; // r9d
  int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // rax
  __int64 v38; // rax
  char *v39; // rcx
  _BYTE *v40; // rcx
  __int64 v41; // rdx
  int v42; // eax
  __int64 v43; // r9
  __int64 v44; // rcx
  __int64 v45; // rdx
  int v46; // eax
  unsigned int v47; // eax
  int v48; // edi
  __int64 v49; // rdx
  __int64 v50; // rcx
  int v51; // eax
  int v52; // r10d
  __int64 v53; // rcx
  __int64 v54; // r8
  __int64 v55; // r9
  FILE_LOCK *v56; // rdi
  struct _KPROCESS *RequestorProcess; // rax
  int v58; // edx
  __int64 v59; // rcx
  int v60; // eax
  BOOLEAN IsFastIoPossible; // al
  __int64 v62; // rax
  __int64 v63; // rcx
  char v64; // dl
  __int64 v65; // rcx
  int v66; // eax
  __int64 v67; // rdi
  __int64 v68; // rcx
  char updated; // al
  char v70; // cl
  int v71; // ecx
  int v72; // r8d
  int v73; // eax
  int v74; // r8d
  __int64 v75; // rcx
  __int64 v76; // r8
  char v77; // al
  int v78; // eax
  __int64 v79; // rdi
  int v80; // ecx
  __int64 v81; // r8
  __int64 v82; // rdx
  char v83; // al
  __int64 v84; // r8
  __int64 v85; // rdx
  _QWORD *ActivityIdThread; // rax
  PIRP v87; // rax
  __int64 v88; // rax
  __int64 v89; // r13
  __int64 v90; // rdx
  int v91; // eax
  __int64 v92; // r8
  int v93; // r8d
  __int64 v94; // rdi
  int v95; // ecx
  __int64 v96; // r8
  __int64 v97; // rdx
  char v98; // al
  int v99; // eax
  char v100; // al
  __int64 v101; // r8
  __int64 v102; // rcx
  int v103; // eax
  __int64 v104; // rcx
  __int64 v105; // rcx
  int v106; // eax
  __int64 v107; // rax
  SECTION_OBJECT_POINTERS *v108; // rcx
  int v109; // edx
  __int64 v110; // rcx
  int v111; // eax
  __int64 v112; // r8
  __int64 v113; // rdi
  __int64 v114; // r8
  __int64 v115; // r9
  unsigned int v116; // ecx
  __int64 v117; // rdx
  __int64 v118; // rax
  int v119; // r8d
  int v120; // r9d
  __int64 v121; // rdx
  __int64 v122; // rdx
  int v123; // r12d
  __int64 v124; // r8
  int ActivityIdIrp; // eax
  char *v126; // rcx
  unsigned int v127; // r12d
  __int64 NextChildScb; // rax
  __int64 v129; // rcx
  int v130; // r8d
  __int64 v131; // rax
  __int64 v132; // r12
  int v133; // ecx
  __int64 v134; // r8
  __int64 Scb; // rdx
  char *v136; // rcx
  char *v137; // rcx
  char v138; // dl
  __int64 v139; // rax
  unsigned int v140; // ecx
  int v141; // r12d
  __int64 v142; // r10
  __int64 v143; // rcx
  __int64 *v144; // rax
  __int64 v145; // rdi
  int v146; // eax
  int v147; // eax
  int v148; // r8d
  __int64 v149; // rcx
  __int64 v150; // rax
  char v151; // di
  __int64 v152; // rdi
  __int64 v153; // rdx
  int v154; // eax
  __int64 MatchingLcbPair; // rax
  char *v156; // rcx
  __int64 v157; // rax
  __int64 v158; // rdi
  __int64 v159; // rcx
  char *v160; // rcx
  __int64 v161; // rdi
  __int64 v162; // rcx
  __int64 v163; // rax
  __int64 v164; // rax
  __int64 v165; // rax
  __int64 NextParentLcb; // rax
  _QWORD *i; // rcx
  __int64 v168; // rax
  __int16 v169; // di
  __int64 v170; // rdx
  char j; // al
  _DWORD *v172; // rax
  int v173; // r8d
  int v174; // r8d
  __int64 v175; // rcx
  int v176; // r8d
  __int64 v177; // rdx
  int v178; // r8d
  signed __int64 v179; // r10
  signed __int64 v180; // r9
  __int64 v181; // rcx
  int v182; // edx
  __int64 v183; // r8
  __int64 v184; // r8
  char v185; // di
  char v186; // al
  __int64 v187; // r8
  __int64 v188; // rax
  __int64 v189; // rcx
  int v190; // edx
  __int64 v191; // rax
  __int64 v192; // rcx
  __int64 v193; // rdx
  __int64 v194; // rdx
  __int64 v195; // rax
  __int64 v197; // rcx
  __int64 v198; // rax
  _QWORD *v199; // rax
  char v200; // di
  __int64 v201; // r14
  __int64 v202; // rdi
  __int64 v203; // r8
  __int64 v204; // r9
  __int64 v205; // r8
  int v206; // eax
  POPLOCK_WAIT_COMPLETE_ROUTINE CompletionRoutine; // [rsp+20h] [rbp-328h]
  POPLOCK_WAIT_COMPLETE_ROUTINE CompletionRoutinea; // [rsp+20h] [rbp-328h]
  int v209; // [rsp+30h] [rbp-318h]
  int v210; // [rsp+30h] [rbp-318h]
  size_t Size; // [rsp+38h] [rbp-310h]
  int v212; // [rsp+70h] [rbp-2D8h]
  char v213; // [rsp+70h] [rbp-2D8h]
  char v214; // [rsp+70h] [rbp-2D8h]
  char v215; // [rsp+70h] [rbp-2D8h]
  char v216; // [rsp+73h] [rbp-2D5h]
  int v217[2]; // [rsp+78h] [rbp-2D0h] BYREF
  char v218[8]; // [rsp+80h] [rbp-2C8h] BYREF
  __int64 v219; // [rsp+88h] [rbp-2C0h] BYREF
  unsigned int v220; // [rsp+90h] [rbp-2B8h]
  __int64 v221; // [rsp+98h] [rbp-2B0h] BYREF
  PVOID FsContext; // [rsp+A0h] [rbp-2A8h] BYREF
  __int64 v223; // [rsp+A8h] [rbp-2A0h]
  __int64 v224; // [rsp+B0h] [rbp-298h] BYREF
  char v225; // [rsp+B8h] [rbp-290h]
  __int64 v226; // [rsp+C0h] [rbp-288h]
  char v227; // [rsp+C8h] [rbp-280h]
  struct _FILE_OBJECT *v228; // [rsp+D0h] [rbp-278h]
  char v229; // [rsp+D8h] [rbp-270h]
  char v230; // [rsp+D9h] [rbp-26Fh]
  PIRP Irp; // [rsp+E0h] [rbp-268h]
  unsigned int v232; // [rsp+E8h] [rbp-260h]
  __int64 v233; // [rsp+F0h] [rbp-258h] BYREF
  __int64 v234; // [rsp+F8h] [rbp-250h]
  char v235; // [rsp+100h] [rbp-248h]
  char v236; // [rsp+101h] [rbp-247h]
  char v237; // [rsp+102h] [rbp-246h]
  char v238; // [rsp+103h] [rbp-245h]
  __int64 Fcb; // [rsp+108h] [rbp-240h]
  _QWORD *v240; // [rsp+110h] [rbp-238h]
  int v241; // [rsp+118h] [rbp-230h]
  int v242; // [rsp+11Ch] [rbp-22Ch]
  unsigned int v243; // [rsp+120h] [rbp-228h]
  __int64 Lcb; // [rsp+128h] [rbp-220h]
  __int64 v245; // [rsp+130h] [rbp-218h]
  PLARGE_INTEGER TruncateSize; // [rsp+138h] [rbp-210h]
  int v247; // [rsp+140h] [rbp-208h]
  int v248; // [rsp+144h] [rbp-204h]
  int v249; // [rsp+148h] [rbp-200h]
  unsigned int v250; // [rsp+14Ch] [rbp-1FCh]
  unsigned int v251; // [rsp+150h] [rbp-1F8h]
  __int64 v252; // [rsp+158h] [rbp-1F0h]
  __int64 v253; // [rsp+160h] [rbp-1E8h]
  __int128 v254; // [rsp+168h] [rbp-1E0h] BYREF
  int v255; // [rsp+178h] [rbp-1D0h]
  unsigned int v256; // [rsp+17Ch] [rbp-1CCh]
  __int64 v257; // [rsp+180h] [rbp-1C8h]
  __int128 v258; // [rsp+188h] [rbp-1C0h] BYREF
  __int64 v259[12]; // [rsp+1A0h] [rbp-1A8h] BYREF
  __int64 v260; // [rsp+200h] [rbp-148h] BYREF
  __int64 v261; // [rsp+208h] [rbp-140h] BYREF
  __int128 v262; // [rsp+210h] [rbp-138h] BYREF
  IRP *v263; // [rsp+220h] [rbp-128h]
  __int64 v264[24]; // [rsp+230h] [rbp-118h] BYREF
  __int128 v265; // [rsp+2F0h] [rbp-58h] BYREF
  __int64 v266; // [rsp+300h] [rbp-48h]
  __int128 v267; // [rsp+308h] [rbp-40h] BYREF

  v3 = a1;
  v223 = a1;
  Irp = a2;
  PostIrpRoutine = 0;
  v220 = 0;
  v242 = 0;
  v221 = 0;
  *(_QWORD *)v217 = 0;
  v219 = 0;
  FsContext = 0;
  v233 = 0;
  v224 = 0;
  memset(v259, 0, 0x58u);
  v261 = 0;
  v218[0] = 0;
  memset(v264, 0, sizeof(v264));
  v212 = 12;
  a2->IoStatus.Information = 2;
  v264[1] = (__int64)&v264[4];
  v264[3] = (__int64)&v264[7];
  LODWORD(v264[0]) = 1572864;
  LODWORD(v264[2]) = 3407872;
  FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  v228 = FileObject;
  v232 = NtfsDecodeFileObject(v3, (__int64)FileObject, &v221, v217, &v219, &FsContext, 0);
  if ( ((v232 - 1) & 0xFFFFFFFB) == 0 )
  {
    FileObject->Flags |= 0x4000u;
    NtfsCompleteCleanupRequest(v3, Irp, v220);
    return v220;
  }
  v263 = a2;
  Fcb = 0;
  v234 = 0;
  v7 = 0;
  v253 = 0;
  Lcb = 0;
  v245 = 0;
  v240 = 0;
  TruncateSize = 0;
  SectionObjectPointer = FileObject->SectionObjectPointer;
  if ( SectionObjectPointer != (PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v219 + 288) + 16LL)
    && *(_DWORD *)(v219 + 256) == 128
    && (SectionObjectPointer[1].ImageSectionObject
     || (v198 = *(_QWORD *)(v219 + 528)) != 0
     && (v199 = *(_QWORD **)(v198 + 112)) != 0
     && SectionObjectPointer == (PSECTION_OBJECT_POINTERS)(*v199 + 16LL)) )
  {
    BYTE2(v212) = 64;
  }
  BYTE1(v212) = 4 * (*((_BYTE *)FsContext + 4) & 8);
  *(_DWORD *)(v3 + 272) = *((_DWORD *)FsContext + 25);
  if ( *((_QWORD *)FsContext + 10) || (dword_1400956B8 & 0x10000000) != 0 )
  {
    LOBYTE(v212) = 8;
    if ( *((_QWORD *)FsContext + 10) )
      LOBYTE(v212) = 0;
  }
  v9 = v221;
  if ( v232 != 4 )
  {
    if ( (*(_DWORD *)(v3 + 12) & 0x100) != 0 )
    {
      LOBYTE(v6) = 1;
      NtfsAcquireExclusiveVcb(v3, v221, v6);
      goto LABEL_8;
    }
LABEL_7:
    LOBYTE(v6) = 1;
    NtfsAcquireSharedVcb(v3, v221, v6);
LABEL_8:
    LODWORD(v12) = 512;
    goto LABEL_9;
  }
  if ( (*(_DWORD *)(v221 + 4) & 2) == 0
    || (struct _FILE_OBJECT *)(*(_QWORD *)(v221 + 1472) & 0xFFFFFFFFFFFFFFFEuLL) != FileObject )
  {
    goto LABEL_7;
  }
  LODWORD(v12) = 512;
  if ( (*(_DWORD *)(v3 + 12) & 0x200) != 0 )
  {
    NtfsAcquireCheckpointSynchronization(v3, v221, 82);
    LOBYTE(v212) = v212 | 1;
    v9 = v221;
  }
  LOBYTE(v6) = 1;
  NtfsAcquireExclusiveVcb(v3, v9, v6);
LABEL_9:
  if ( (*(_DWORD *)(v221 + 4) & 0x8000823) == 1 && (*(_DWORD *)(*(_QWORD *)v217 + 4LL) & 0x80u) == 0 )
    BYTE2(v212) |= 8u;
  if ( (*(_DWORD *)(v221 + 4) & 0x2000020) != 0 || (*(_DWORD *)(*(_QWORD *)v217 + 4LL) & 0x8000000) != 0 )
    BYTE2(v212) |= 0x10u;
  if ( (*(_DWORD *)(v221 + 4) & 0x4000000) != 0 )
    BYTE1(v212) |= 8u;
  v13 = *(_QWORD *)v217;
  if ( *(_QWORD *)(*(_QWORD *)v217 + 112LL) )
  {
    LOBYTE(v10) = 1;
    if ( (unsigned __int8)NtfsAcquirePagingResourceExclusive(v3, *(_QWORD *)v217, v10, v11) )
    {
      v14 = 0;
      v251 = 0;
      while ( v14 < 2 )
      {
        v15 = v3 + 8LL * v14;
        v16 = *(_QWORD *)(v15 + 48);
        if ( !v16 || v16 == v13 )
        {
          *(_QWORD *)(v15 + 48) = v13;
          break;
        }
        v251 = ++v14;
      }
    }
LABEL_20:
    NtfsAcquireExclusiveFcb(v3, *(_QWORD *)(v219 + 184), v219, 8);
    goto LABEL_21;
  }
  NtfsAcquireExclusiveFcb(v3, *(_QWORD *)(v219 + 184), v219, 8);
  if ( *(_QWORD *)(*(_QWORD *)v217 + 112LL) )
  {
    NtfsReleaseFcbEx(v3, *(_QWORD *)(v219 + 184), 0);
    v113 = *(_QWORD *)v217;
    LOBYTE(v114) = 1;
    if ( (unsigned __int8)NtfsAcquirePagingResourceExclusive(v3, *(_QWORD *)v217, v114, v115) )
    {
      v116 = 0;
      v250 = 0;
      while ( v116 < 2 )
      {
        v117 = v3 + 8LL * v116;
        v118 = *(_QWORD *)(v117 + 48);
        if ( !v118 || v118 == v113 )
        {
          *(_QWORD *)(v117 + 48) = v113;
          goto LABEL_20;
        }
        v250 = ++v116;
      }
    }
    goto LABEL_20;
  }
LABEL_21:
  v18 = (char *)FsContext + 8;
  if ( (*((_DWORD *)FsContext + 2) & 0x100) == 0 )
    goto LABEL_22;
  while ( 1 )
  {
    ClearFlagInterlocked(v18, 256);
    --*(_DWORD *)(v219 + 448);
LABEL_22:
    if ( (*((_DWORD *)FsContext + 2) & 0x8000) != 0 )
    {
      --*(_DWORD *)(v219 + 544);
      ClearFlagInterlocked((char *)FsContext + 8, 0x8000);
    }
    p_Flags = &FileObject->Flags;
    *(_QWORD *)&v258 = &FileObject->Flags;
    if ( (FileObject->Flags & 0x800000) != 0 )
      NtfsBypassIoDisableCore(v3, FileObject);
    v20 = *((_QWORD *)FsContext + 9);
    v226 = v20;
    v252 = v20;
    v233 = v20;
    if ( v20 )
    {
      if ( (*(_DWORD *)(v20 + 4) & 2) != 0 )
      {
        v20 = PostIrpRoutine;
        v226 = PostIrpRoutine;
        v233 = PostIrpRoutine;
        ClearFlagInterlocked((char *)FsContext + 4, 0x40000);
      }
      else
      {
        v21 = *(_QWORD *)(v20 + 24);
        v224 = v21;
        if ( v21 )
          Fcb = *(_QWORD *)(v21 + 184);
      }
    }
    if ( (*((_DWORD *)FsContext + 1) & 0x100) != 0 && v232 == 2 )
      TxfUnmarkObjectAsClfsLog(v219);
    if ( ((unsigned int)v12 & *((_DWORD *)FsContext + 2)) != 0 )
    {
      v127 = PostIrpRoutine;
      v255 = PostIrpRoutine;
      v249 = PostIrpRoutine;
      v243 = PostIrpRoutine;
      v248 = PostIrpRoutine;
      *(_QWORD *)&v254 = PostIrpRoutine;
      *(_DWORD *)(*(_QWORD *)v217 + 4LL) &= ~0x40000000u;
      ClearFlagInterlocked((char *)FsContext + 8, 512);
      _InterlockedDecrement((volatile signed __int32 *)(v221 + 276));
      while ( 1 )
      {
        NextChildScb = NtfsGetNextChildScb(*(_QWORD *)v217, v254, 1);
        *(_QWORD *)&v254 = NextChildScb;
        if ( !NextChildScb )
          break;
        v119 = PostIrpRoutine;
        v249 = PostIrpRoutine;
        v120 = PostIrpRoutine;
        v248 = PostIrpRoutine;
        v121 = *(_QWORD *)(NextChildScb + 480);
        if ( v121 == NextChildScb + 480 )
          v122 = PostIrpRoutine;
        else
          v122 = v121 - 40;
        while ( v122 )
        {
          if ( (*(_DWORD *)(v122 + 8) & 4) == 0 )
            v249 = --v119;
          if ( (*(_DWORD *)(v122 + 4) & 0x80000) == 0 && !*(_WORD *)(*(_QWORD *)(v122 + 112) + 75LL) )
            v248 = ++v120;
          v129 = *(_QWORD *)(v122 + 40);
          v122 = PostIrpRoutine;
          if ( NextChildScb + 480 != v129 )
            v122 = v129 - 40;
        }
        v127 += v119;
        v255 = v127;
        v243 += v120;
      }
      _InterlockedAdd((volatile signed __int32 *)(v221 + 268), v127);
      _InterlockedAdd((volatile signed __int32 *)(v221 + 264), v243);
    }
    if ( (v212 & 0x80000) == 0 )
      goto LABEL_46;
    v22 = *((_QWORD *)FsContext + 10);
    if ( v22 && (*(_DWORD *)(v22 + 4) & 2) == 0 )
    {
      v130 = PostIrpRoutine;
      LOBYTE(v130) = *(_DWORD *)(v22 + 36) == (_DWORD)PostIrpRoutine;
      LOBYTE(v17) = 1;
      v220 = TxfSetupTransactionContextFromCcb(v3, (_DWORD)FileObject, v130, v17, PostIrpRoutine);
      if ( (v220 & 0x80000000) != 0 )
      {
        v233 = PostIrpRoutine;
        HIBYTE(v212) |= 0x20u;
        ClearFlagInterlocked((char *)FsContext + 4, 0x40000);
        if ( !*(_DWORD *)(*((_QWORD *)FsContext + 10) + 36LL) )
        {
          v152 = *(_QWORD *)(*(_QWORD *)v217 + 328LL);
          ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v152 + 136), 1u);
          v234 = v152;
          v153 = *(_QWORD *)(v152 + 24);
          if ( v153
            && *(_QWORD *)(v153 + 232) == *(_QWORD *)(*((_QWORD *)FsContext + 10) + 56LL)
            && (*(_DWORD *)(v152 + 4) & 0x2000000) == 0 )
          {
            HIBYTE(v212) |= 8u;
            if ( v20 )
            {
              v154 = *(_DWORD *)(v20 + 4);
              if ( (v154 & 2) == 0 )
              {
                if ( (v154 & 1) != 0
                  || (*(_BYTE *)(*(_QWORD *)(v20 + 192) + 65LL) & 3) != 0
                  && (*(_DWORD *)(*(_QWORD *)(v20 + 48) + 4LL) & 0x20) != 0 )
                {
                  MatchingLcbPair = NtfsFindMatchingLcbPair(v20, 0);
                  ++*(_WORD *)(*(_QWORD *)v217 + 188LL);
                  ++*(_DWORD *)(v152 + 20);
                  if ( MatchingLcbPair )
                    ClearFlagInterlocked(MatchingLcbPair + 4, 1);
                  ClearFlagInterlocked(v20 + 4, 1);
                  if ( (*(_BYTE *)(*(_QWORD *)(v20 + 192) + 65LL) & 3) != 0 )
                    *(_DWORD *)(*(_QWORD *)v217 + 4LL) &= ~0x20u;
                }
                if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)v217 + 328LL) + 4LL) & 0x800) == 0 )
                  HIBYTE(v212) |= 4u;
              }
            }
            v20 = PostIrpRoutine;
            v226 = PostIrpRoutine;
          }
          ExReleaseResourceLite(*(PERESOURCE *)(v152 + 136));
          v234 = PostIrpRoutine;
        }
        v220 = PostIrpRoutine;
        v234 = PostIrpRoutine;
      }
      else if ( !*(_DWORD *)(*((_QWORD *)FsContext + 10) + 36LL) )
      {
        HIBYTE(v212) |= 2u;
        ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v217 + 328LL) + 136LL), 1u);
        v131 = *(_QWORD *)(*(_QWORD *)v217 + 328LL);
        v234 = v131;
        if ( v252 )
        {
          if ( (*(_DWORD *)(v252 + 4) & 2) != 0 )
          {
            Lcb = v252;
            HIBYTE(v212) |= 1u;
          }
          else
          {
            Lcb = v20;
            v216 = HIBYTE(v212) | 1;
            if ( (*((_DWORD *)FsContext + 1) & 0x40002) == 0x40002 )
            {
              v235 = 0;
              v238 = 0;
              if ( (*(_DWORD *)(v20 + 4) & 1) != 0
                || (*(_BYTE *)(*(_QWORD *)(v20 + 192) + 65LL) & 3) != 0
                && (*(_DWORD *)(*(_QWORD *)(v20 + 48) + 4LL) & 0x20) != 0 )
              {
                v137 = (char *)FsContext + 8;
                if ( (*((_DWORD *)FsContext + 2) & 0x20000) != 0 )
                  SetFlagInterlocked(v137, 0x10000);
                else
                  ClearFlagInterlocked(v137, 0x10000);
              }
              else if ( (*(_DWORD *)(*(_QWORD *)v217 + 176LL) & 0x10000000) == 0
                     || (unsigned __int8)NtfsIsLinkDeleteable(v3, v217[0]) )
              {
                --*(_WORD *)(*(_QWORD *)v217 + 188LL);
                SetFlagInterlocked(v20 + 4, 1);
                v136 = (char *)FsContext + 8;
                if ( (*((_DWORD *)FsContext + 2) & 0x20000) != 0 )
                  SetFlagInterlocked(v136, 0x10000);
                else
                  ClearFlagInterlocked(v136, 0x10000);
                BYTE2(v212) |= 0x20u;
                --*(_DWORD *)(*(_QWORD *)(*(_QWORD *)v217 + 328LL) + 20LL);
                if ( (*(_BYTE *)(*(_QWORD *)(v20 + 192) + 65LL) & 3) != 0 )
                  *(_DWORD *)(*(_QWORD *)v217 + 4LL) |= 0x20u;
              }
            }
            v138 = v216 | 0x10;
            HIBYTE(v212) = v216 | 0x10;
            if ( (*(_DWORD *)(v20 + 4) & 1) == 0
              && ((*(_BYTE *)(*(_QWORD *)(v20 + 192) + 65LL) & 3) == 0
               || (*(_DWORD *)(*(_QWORD *)(v20 + 48) + 4LL) & 0x20) == 0) )
            {
              goto LABEL_597;
            }
            v139 = NtfsFindMatchingLcbPair(v20, 0);
            v140 = *(_DWORD *)(v20 + 32);
            v256 = v140;
            if ( v139 )
            {
              v140 += *(_DWORD *)(v139 + 32);
              v256 = v140;
            }
            v138 = HIBYTE(v212);
            if ( v140 > 1 )
            {
LABEL_597:
              v138 &= ~0x10u;
              HIBYTE(v212) = v138;
            }
            if ( (v138 & 0x10) != 0
              && *(_WORD *)(*(_QWORD *)v217 + 190LL) == 1
              && *(_WORD *)(*(_QWORD *)(*(_QWORD *)v217 + 328LL) + 144LL) > 1u )
            {
              HIBYTE(v212) = v138 & 0xEF;
              *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v217 + 328LL) + 4LL) |= 0x800u;
            }
          }
        }
        else if ( *(_WORD *)(v131 + 144) == 1 && (*(_DWORD *)(v131 + 4) & 0x800) != 0 )
        {
          v254 = 0;
          HIBYTE(v212) |= 0x10u;
          memset(v259, 0, 0x58u);
          LOBYTE(v212) = v212 | 0x10;
          LOBYTE(v209) = 0;
          if ( !(unsigned __int8)NtfsLookupInFileRecord(
                                   v3,
                                   *(_QWORD *)v217,
                                   *(_QWORD *)v217 + 8LL,
                                   48,
                                   PostIrpRoutine,
                                   PostIrpRoutine,
                                   v209,
                                   PostIrpRoutine,
                                   PostIrpRoutine,
                                   v259) )
          {
            NtfsAttachCorruption_BadOrOrphanFRS(v3, 2, 460131, 0, *(_QWORD *)v217 + 8LL, *(__int64 *)v217, 0);
            NtfsAttachRepairInfoPriv(v3, 256, 0, 0xFB00070563LL);
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(v3, 3221225730LL, 460131);
            NtfsRaiseStatusInternal(v3, -1073741566, v217[0] + 8, v217[0], 460131);
LABEL_517:
            v123 = -1072037844;
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(0, 3222929452LL, 460523);
            v220 = -1072037844;
LABEL_520:
            TxfRaiseAndAbortAtTopLevelPriv(
              v3,
              v257,
              0,
              0,
              0,
              v123,
              (__int64)"NtfsCommonCleanup",
              (__int64)"Cleanup.c",
              1786);
          }
          v132 = v259[0] + *(unsigned __int16 *)(v259[0] + 20);
          ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v217 + 328LL) + 136LL));
          v234 = PostIrpRoutine;
          v133 = *(_DWORD *)(*(_QWORD *)v217 + 8LL);
          if ( v133 == 5 || (v134 = *(_QWORD *)(*(_QWORD *)v217 + 320LL), *(_DWORD *)(v134 + 88) == v133) )
            v134 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v217 + 96LL) + 6248LL);
          Fcb = NtfsCreateFcb(v3, v221, v134, *(_QWORD *)v132, 66, PostIrpRoutine);
          Scb = NtfsCreateScb(v3, Fcb, 160, (unsigned int)&NtfsFileNameIndex, 0, PostIrpRoutine, PostIrpRoutine);
          v224 = Scb;
          if ( (*(_DWORD *)(Scb + 200) & 0x200) != 0 )
          {
            NtfsSnapshotScb(v3, Scb);
            LODWORD(Scb) = v224;
          }
          *((_QWORD *)&v254 + 1) = v132 + 66;
          LOWORD(v254) = 2 * *(unsigned __int8 *)(v132 + 64);
          WORD1(v254) = v254;
          Lcb = NtfsCreateLcb(v3, Scb, v217[0], (unsigned int)&v254, *(_BYTE *)(v132 + 65), PostIrpRoutine);
          v218[0] = 1;
          ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v217 + 328LL) + 136LL), 1u);
          v234 = *(_QWORD *)(*(_QWORD *)v217 + 328LL);
        }
        ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v217 + 328LL) + 136LL));
        v234 = PostIrpRoutine;
        if ( (v212 & 0x10000000) != 0 )
        {
          v247 = 18;
          v257 = PostIrpRoutine;
          v141 = 18;
          if ( v218[0] )
            v141 = 22;
          v247 = v141;
          if ( (*((_DWORD *)FsContext + 1) & 1) != 0 )
            v247 = v141 | 1;
          LOBYTE(v264[23]) = 0;
          v142 = *(_QWORD *)(v219 + 184);
          if ( *(_WORD *)(v142 + 190) == 1 )
          {
            NtfsPostUsnChangeWithOverrideOption(
              v3,
              v142,
              -2147483136,
              0,
              PostIrpRoutine,
              PostIrpRoutine,
              PostIrpRoutine);
          }
          else
          {
            v143 = PostIrpRoutine;
            if ( (*(_BYTE *)(*(_QWORD *)(Lcb + 192) + 65LL) & 3) != 2 )
              v143 = *(_QWORD *)(Lcb + 192);
            NtfsPostUsnChangeWithOverrideOption(v3, v142, -2147418112, 0, PostIrpRoutine, PostIrpRoutine, v143);
            NtfsUpdateFileTimestampsForChange(*(_QWORD *)(v219 + 184), FsContext, 0);
          }
          if ( *(int *)(v221 + 4) < 0 || (v144 = &v264[14], (*p_Flags & 0x20000) != 0) )
            v144 = (__int64 *)PostIrpRoutine;
          TxfDeleteFile(v3, *(_QWORD *)(v219 + 184), PostIrpRoutine, (__int64)v264, (__int64)v144);
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v217 + 328LL) + 4LL) &= ~0x800u;
          v123 = v220;
          if ( v220 )
          {
            if ( v220 != -1073741608 || (*(_DWORD *)(*(_QWORD *)(v257 + 208) + 136LL) & 0x1000) == 0 )
              goto LABEL_520;
            goto LABEL_517;
          }
          if ( v218[0] || *(_DWORD *)(v3 + 28) )
          {
            NtfsUpdateFcbTimestamps(Fcb, 2684354576LL);
          }
          else
          {
            NtfsAcquireExclusiveScbEx(v3, v224, 0);
            v218[0] = 1;
            NtfsUpdateFcbTimestamps(Fcb, 2684354576LL);
            NtfsReleaseFcbEx(v3, *(_QWORD *)(v224 + 184), 0);
            v218[0] = 0;
          }
          if ( !v220 )
          {
            if ( *(int *)(v221 + 4) >= 0 && (*p_Flags & 0x20000) == 0 )
            {
              v145 = Lcb;
              NtfsGetTunneledData(v3, *(_QWORD *)v217, *(unsigned __int8 *)(*(_QWORD *)(Lcb + 192) + 65LL), &v264[14]);
              if ( FsContext )
                v146 = *((_DWORD *)FsContext + 1);
              else
                v146 = PostIrpRoutine;
              if ( (v146 & 0x4000000) != 0 || (v147 = 1, (*(_DWORD *)(*(_QWORD *)(v224 + 184) + 16LL) & 0x400) == 0) )
                v147 = PostIrpRoutine;
              FsRtlAddToTunnelCacheEx(
                v221 + 4720,
                *(_QWORD *)(*(_QWORD *)(v224 + 184) + 8LL),
                v264,
                &v264[2],
                *(_BYTE *)(*(_QWORD *)(v145 + 192) + 65LL) & 2 | v147,
                80,
                &v264[14]);
            }
            if ( (v212 & 0x2000) == 0 && *(_WORD *)v219 != 1796 )
            {
              v148 = PostIrpRoutine;
              LOBYTE(v148) = *(_WORD *)v219 == 1795;
              NtfsReportDirNotify(
                v3,
                *((_QWORD *)FsContext + 9),
                v221,
                (_DWORD)FsContext + 16,
                *((unsigned __int16 *)FsContext + 16),
                PostIrpRoutine,
                v148 + 1,
                2,
                Fcb,
                PostIrpRoutine);
            }
          }
        }
        if ( (*((_DWORD *)FsContext + 1) & 2) != 0
          && ((*(_DWORD *)(*(_QWORD *)(*(_QWORD *)v217 + 328LL) + 4LL) & 0x800) != 0 || (v212 & 0x10000000) != 0) )
        {
          ClearFlagInterlocked((char *)FsContext + 4, 0x40000);
        }
        else if ( *(_DWORD *)(v219 + 256) == 128 )
        {
          if ( *(_WORD *)(v219 + 264) )
          {
            v149 = *(_QWORD *)(v219 + 528);
            if ( *(_DWORD *)(v149 + 36) == 1 )
            {
              LOBYTE(v124) = 1;
              v150 = TxfCurrentWritableVersion(v149, 0, v124);
              v7 = v150;
              v253 = v150;
              if ( v150 )
              {
                if ( (*(_DWORD *)(v150 + 8) & 4) == 0
                  && (*(_DWORD *)(*(_QWORD *)(v219 + 528) + 24LL) & 1) == 0
                  && ((*(_DWORD *)(v219 + 200) & 2) != 0 || (*((_DWORD *)FsContext + 1) & 0x40000) != 0) )
                {
                  v151 = v212;
                  if ( (v212 & 0x10) != 0 )
                  {
                    NtfsCleanupAttributeContext(v3, v259);
                    v151 = v212;
                  }
                  memset(v259, 0, 0x58u);
                  LOBYTE(v212) = v151 | 0x10;
                  LOBYTE(v209) = 0;
                  if ( !(unsigned __int8)NtfsLookupInFileRecord(
                                           v3,
                                           *(_QWORD *)(v219 + 184),
                                           *(_QWORD *)(v219 + 184) + 8LL,
                                           *(unsigned int *)(v219 + 256),
                                           v219 + 264,
                                           PostIrpRoutine,
                                           v209,
                                           PostIrpRoutine,
                                           PostIrpRoutine,
                                           v259)
                    && (*(_DWORD *)(v219 + 512) & 4) == 0 )
                  {
                    PostIrpRoutine = 0xA9000707AFLL;
                    NtfsAttachCorruption_BadOrOrphanFRS(
                      v3,
                      2,
                      460719,
                      0,
                      *(_QWORD *)(v219 + 184) + 8LL,
                      *(_QWORD *)(v219 + 184),
                      0);
                    NtfsAttachRepairInfoPriv(v3, 512, 0, 0xA9000707AFLL);
                    if ( NtfsStatusDebugFlags )
                      NtfsStatusTraceAndDebugInternal(v3, 3221225730LL, 460719);
                    NtfsRaiseStatusInternal(
                      v3,
                      -1073741566,
                      *(_QWORD *)(v219 + 184) + 8,
                      *(_QWORD *)(v219 + 184),
                      460719);
                  }
                  TxfOverwriteAttribute(v3);
                  BYTE2(v212) |= 0x80u;
                }
              }
            }
          }
        }
        if ( v7 )
          TxfDereferenceTxfVscb((PVOID)v7);
      }
    }
    if ( (v212 & 0x100000) != 0 || !(unsigned __int8)NtfsIsFileStillValid(*(_QWORD *)v217) )
    {
LABEL_46:
      v12 = 1797;
      goto LABEL_47;
    }
    v23 = *((_DWORD *)FsContext + 1);
    if ( (v23 & 0x40000) != 0 )
    {
      if ( (v23 & 2) == 0 )
      {
        v161 = v219;
        v245 = v219;
        _InterlockedIncrement((volatile signed __int32 *)(v219 + 212));
        v214 = v212 | 0x80;
        if ( !(unsigned __int8)TxfCantFlushDefaultReaderImageSection(v161, 0) )
        {
          v162 = *(_QWORD *)(v161 + 288);
          if ( !*(_QWORD *)(v162 + 32) || MmFlushImageSection((PSECTION_OBJECT_POINTERS)(v162 + 16), MmFlushForDelete) )
          {
            SetFlagInterlocked(v219 + 200, 2);
            BYTE2(v212) |= 0x20u;
          }
        }
        _InterlockedDecrement((volatile signed __int32 *)(v161 + 212));
        LOBYTE(v212) = v214 & 0x7F;
        goto LABEL_464;
      }
      v236 = 0;
      v237 = 0;
      if ( (*(_DWORD *)(v20 + 4) & 1) != 0
        || (*(_BYTE *)(*(_QWORD *)(v20 + 192) + 65LL) & 3) != 0
        && (*(_DWORD *)(*(_QWORD *)(v20 + 48) + 4LL) & 0x20) != 0 )
      {
        v156 = (char *)FsContext + 8;
        if ( (*((_DWORD *)FsContext + 2) & 0x20000) != 0 )
          SetFlagInterlocked(v156, 0x10000);
        else
          ClearFlagInterlocked(v156, 0x10000);
        goto LABEL_464;
      }
      v104 = *(_QWORD *)v217;
      if ( (*(_DWORD *)(*(_QWORD *)v217 + 176LL) & 0x10000000) != 0 )
      {
        if ( !(unsigned __int8)NtfsIsLinkDeleteable(v3, v217[0]) )
        {
LABEL_464:
          ClearFlagInterlocked((char *)FsContext + 4, 0x40000);
          goto LABEL_37;
        }
        v104 = *(_QWORD *)v217;
      }
      v245 = PostIrpRoutine;
      while ( 1 )
      {
        v157 = NtfsGetNextChildScb(v104, v245, 0);
        v158 = v157;
        v245 = v157;
        if ( !v157 )
          break;
        _InterlockedIncrement((volatile signed __int32 *)(v157 + 212));
        v213 = v212 | 0x80;
        if ( *(_DWORD *)(v157 + 256) == 128 && (*(_DWORD *)(v157 + 512) & 0x1000040) == 0 )
        {
          if ( (unsigned __int8)TxfCantFlushDefaultReaderImageSection(v157, 0)
            || (v159 = *(_QWORD *)(v158 + 288), *(_QWORD *)(v159 + 32))
            && !MmFlushImageSection((PSECTION_OBJECT_POINTERS)(v159 + 16), MmFlushForDelete) )
          {
            _InterlockedDecrement((volatile signed __int32 *)(v158 + 212));
            LOBYTE(v212) = v213 & 0x7F;
            break;
          }
        }
        _InterlockedDecrement((volatile signed __int32 *)(v158 + 212));
        LOBYTE(v212) = v213 & 0x7F;
        v104 = *(_QWORD *)v217;
      }
      if ( !v245 )
      {
        if ( (*(_BYTE *)(*(_QWORD *)(v20 + 192) + 65LL) & 3) != 0 )
          *(_DWORD *)(*(_QWORD *)v217 + 4LL) |= 0x20u;
        --*(_WORD *)(*(_QWORD *)v217 + 188LL);
        SetFlagInterlocked(v20 + 4, 1);
        v160 = (char *)FsContext + 8;
        if ( (*((_DWORD *)FsContext + 2) & 0x20000) != 0 )
          SetFlagInterlocked(v160, 0x10000);
        else
          ClearFlagInterlocked(v160, 0x10000);
        BYTE2(v212) |= 0x20u;
        if ( (*(_DWORD *)(*(_QWORD *)v217 + 176LL) & 0x10000000) != 0 )
          FsRtlNotifyFilterChangeDirectoryLite(
            v219 + 768,
            v219 + 752,
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
    v12 = 1797;
    if ( (v212 & 0x200000) != 0 )
    {
      if ( (v46 = *(_DWORD *)(v219 + 256), v46 == 128) && *(_WORD *)v219 == 1797
        || v46 == 160
        && *(_WORD *)(v219 + 264) == 8
        && **(_QWORD **)(v219 + 272) == 0x30003300490024LL
        && (unsigned __int16)(*(_WORD *)v219 - 1795) <= 1u )
      {
        v47 = FsRtlCheckOplockEx(
                (POPLOCK)(v219 + 88),
                Irp,
                0x20u,
                (PVOID)v3,
                NtfsOplockComplete,
                NtfsCleanupOplockPrePostIrp);
        v220 = v47;
        if ( v47 )
        {
          if ( v47 == 259 )
          {
            Irp = (PIRP)PostIrpRoutine;
            v3 = PostIrpRoutine;
            v223 = PostIrpRoutine;
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(0, 871, 461121);
            v45 = 871;
            v220 = 871;
            goto LABEL_958;
          }
          if ( NtfsStatusDebugFlags
            && (((v47 - 294) & 0xFFFFFFFA) != 0 || v47 == 295)
            && v47 < 0xFFFFFFED
            && v47 != -1073741802
            && v47 != -1073741807
            && v47 + 2147483643 > 1
            && v47 != -1073741608 )
          {
            NtfsStatusTraceAndDebugInternal(0, v47, 461130);
          }
        }
      }
    }
    if ( *(_WORD *)(*(_QWORD *)v217 + 188LL) || *(_DWORD *)(*(_QWORD *)v217 + 20LL) != 1 )
    {
      if ( (*(_DWORD *)(v219 + 200) & 2) != 0 )
      {
        v24 = *(_QWORD *)(*(_QWORD *)v217 + 328LL);
        if ( v24 && (*(_DWORD *)(v24 + 4) & 1) != 0 )
        {
          if ( (v212 & 0x10000000) == 0 && (v212 & 0x2000000) != 0 && *(_DWORD *)(*(_QWORD *)(v219 + 528) + 36LL) == 1 )
            BYTE1(v212) |= 4u;
        }
        else if ( *(_DWORD *)(v219 + 208) == 1 && (*(_DWORD *)(v219 + 512) & 0x200000) == 0 )
        {
          BYTE1(v212) |= 4u;
        }
      }
    }
    else
    {
      BYTE1(v212) |= 1u;
    }
LABEL_47:
    switch ( v232 )
    {
      case 2u:
        if ( (*(_DWORD *)(v219 + 200) & 0x20) == 0
          && (v212 & 0x80000) != 0
          && (v212 & 0x100000) == 0
          && (unsigned __int8)NtfsIsFileStillValid(*(_QWORD *)(v219 + 184)) )
        {
          NtfsUpdateScbFromAttribute(v3, v219, 0);
        }
        NtfsClearSfioReservation(v3, (_DWORD)Irp, (_DWORD)FileObject, v221, v219, (__int64)FsContext);
        NtfsSnapshotScb(v3, v219);
        v28 = v219;
        v29 = *(_DWORD *)(v219 + 256);
        if ( v29 == 128 && *(_WORD *)v219 == 1797
          || v29 == 160
          && *(_WORD *)(v219 + 264) == 8
          && **(_QWORD **)(v219 + 272) == 0x30003300490024LL
          && (unsigned __int16)(*(_WORD *)v219 - 1795) <= 1u )
        {
          FsRtlCheckOplock((POPLOCK)(v219 + 88), Irp, 0, 0, (POPLOCK_FS_PREPOST_IRP)PostIrpRoutine);
          v28 = v219;
        }
        if ( *(_WORD *)v28 == 1797 && *(_QWORD *)(v28 + 584) )
        {
          v56 = *(FILE_LOCK **)(v28 + 584);
          RequestorProcess = IoGetRequestorProcess(Irp);
          FsRtlFastUnlockAll(v56, FileObject, RequestorProcess, 0);
          v28 = v219;
        }
        if ( (*(_DWORD *)(*(_QWORD *)(v28 + 192) + 4LL) & 0x4000005) == 1
          && *(_WORD *)v28 == 1797
          && (IsFastIoPossible = FsRtlOplockIsFastIoPossible((POPLOCK)(v28 + 88)), v28 = v219, IsFastIoPossible) )
        {
          if ( *(_DWORD *)(v219 + 452)
            || (v62 = *(_QWORD *)(v219 + 584)) != 0 && *(_BYTE *)(v62 + 16)
            || (v63 = *(_QWORD *)(v219 + 192), (*(_DWORD *)(v63 + 4) & 0x2000000) != 0)
            || (*(_DWORD *)(v219 + 512) & 0x4000000) != 0
            || *(_QWORD *)(v219 + 528)
            || *(_QWORD *)(v63 + 40) )
          {
            v30 = 2;
          }
          else
          {
            v30 = 1;
          }
        }
        else
        {
          v30 = PostIrpRoutine;
        }
        *(_BYTE *)(v28 + 5) = v30;
        if ( (v212 & 0x80000) == 0 || (v212 & 0x100000) != 0 || !(unsigned __int8)NtfsIsFileStillValid(*(_QWORD *)v217) )
        {
          FileObject->Flags |= 0x4000u;
          if ( (v212 & 0x80000) == 0 || !(unsigned __int8)NtfsIsFileStillValid(*(_QWORD *)v217) )
          {
            v12 = (__int64)&NtfsLarge0;
            TruncateSize = &NtfsLarge0;
          }
          goto LABEL_90;
        }
        LOBYTE(v31) = 1;
        NtfsUpdateScbFromFileObject(FileObject, v219, v31);
        FileObject->Flags |= 0x4000u;
        if ( v220 )
          goto LABEL_90;
        if ( !v20
          || ((v33 = *(_DWORD *)(v20 + 4), (v33 & 1) != 0)
           || (*(_BYTE *)(*(_QWORD *)(v20 + 192) + 65LL) & 3) != 0
           && (*(_DWORD *)(*(_QWORD *)(v20 + 48) + 4LL) & 0x20) != 0)
          && *(_DWORD *)(v20 + 188) == 1 )
        {
          if ( (v212 & 0x100) != 0 && (*(_DWORD *)(*(_QWORD *)v217 + 4LL) & 0x8000) != 0 )
          {
            NtfsPostSpecial(v3, v221, (unsigned int)NtfsDeleteUsnSpecial, v221 + 2144, 13);
            BYTE1(v212) &= ~1u;
            ++*(_WORD *)(*(_QWORD *)v217 + 188LL);
            *(_DWORD *)(*(_QWORD *)v217 + 4LL) &= ~0x20u;
            if ( v20 )
            {
              ClearFlagInterlocked(v20 + 4, 1);
            }
            else
            {
              while ( 1 )
              {
                NextParentLcb = NtfsGetNextParentLcb(v3, *(_QWORD *)v217, v20);
                v20 = NextParentLcb;
                v226 = NextParentLcb;
                if ( !NextParentLcb )
                  break;
                ClearFlagInterlocked(NextParentLcb + 4, 1);
              }
            }
            goto LABEL_77;
          }
          if ( (v212 & 0x100) != 0 )
          {
            if ( v20 )
            {
              v240 = (_QWORD *)v20;
            }
            else
            {
              for ( i = *(_QWORD **)(*(_QWORD *)v217 + 48LL); i != (_QWORD *)(*(_QWORD *)v217 + 48LL); i = (_QWORD *)*i )
              {
                v240 = i - 7;
                if ( (*((_DWORD *)i - 13) & 2) == 0 )
                {
                  v76 = *(i - 4);
                  v224 = v76;
                  if ( v76 )
                    Fcb = *(_QWORD *)(v76 + 184);
                  goto LABEL_318;
                }
              }
            }
            v76 = v224;
LABEL_318:
            if ( v76 )
            {
              v77 = v212;
            }
            else
            {
              while ( 1 )
              {
                v262 = 0;
                memset(v259, 0, 0x58u);
                LOBYTE(v212) = v212 | 0x10;
                v240 = (_QWORD *)PostIrpRoutine;
                LOBYTE(v209) = 0;
                if ( (unsigned __int8)NtfsLookupInFileRecord(
                                        v3,
                                        *(_QWORD *)v217,
                                        *(_QWORD *)v217 + 8LL,
                                        48,
                                        PostIrpRoutine,
                                        PostIrpRoutine,
                                        v209,
                                        PostIrpRoutine,
                                        PostIrpRoutine,
                                        v259) )
                  break;
                PostIrpRoutine = 0xFD00070D48LL;
                NtfsAttachCorruption_BadOrOrphanFRS(v3, 2, 462152, 0, *(_QWORD *)v217 + 8LL, *(__int64 *)v217, 0);
                NtfsAttachRepairInfoPriv(v3, 256, 0, 0xFD00070D48LL);
                if ( NtfsStatusDebugFlags )
                  NtfsStatusTraceAndDebugInternal(v3, 3221225730LL, 462152);
                NtfsRaiseStatusInternal(v3, -1073741566, v217[0] + 8, v217[0], 462152);
              }
              v79 = v259[0] + *(unsigned __int16 *)(v259[0] + 20);
              v80 = *(_DWORD *)(*(_QWORD *)v217 + 8LL);
              if ( v80 == 5 || (v81 = *(_QWORD *)(*(_QWORD *)v217 + 320LL), *(_DWORD *)(v81 + 88) == v80) )
                v81 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v217 + 96LL) + 6248LL);
              Fcb = NtfsCreateFcb(v3, v221, v81, *(_QWORD *)v79, 66, PostIrpRoutine);
              v82 = NtfsCreateScb(v3, Fcb, 160, (unsigned int)&NtfsFileNameIndex, 0, PostIrpRoutine, PostIrpRoutine);
              v224 = v82;
              if ( (*(_DWORD *)(v82 + 200) & 0x200) != 0 )
              {
                NtfsSnapshotScb(v3, v82);
                LODWORD(v82) = v224;
              }
              *((_QWORD *)&v262 + 1) = v79 + 66;
              LOWORD(v262) = 2 * *(unsigned __int8 *)(v79 + 64);
              WORD1(v262) = v262;
              NtfsCreateLcb(v3, v82, v217[0], (unsigned int)&v262, *(_BYTE *)(v79 + 65), PostIrpRoutine);
              v218[0] = 1;
              NtfsCleanupAttributeContext(v3, v259);
              v77 = v212 & 0xEF;
              v76 = v224;
            }
            LOBYTE(v212) = v77 & 0xFB;
            LOBYTE(v264[23]) = 0;
            if ( (v212 & 0x2000) != 0
              || !v76
              || !*((_QWORD *)FsContext + 9)
              || *(int *)(v221 + 4) < 0
              || (FileObject->Flags & 0x20000) != 0 )
            {
              NtfsDeleteFile(v3, v217[0], (__int64)v264, PostIrpRoutine);
            }
            else
            {
              NtfsDeleteFile(v3, v217[0], (__int64)v264, (__int64)&v264[14]);
              NtfsGetTunneledData(
                v3,
                *(_QWORD *)v217,
                *(unsigned __int8 *)(*(_QWORD *)(*((_QWORD *)FsContext + 9) + 192LL) + 65LL),
                &v264[14]);
              if ( (*((_DWORD *)FsContext + 1) & 0x4000000) != 0
                || (*(_DWORD *)(*(_QWORD *)(v224 + 184) + 16LL) & 0x400) == 0 )
              {
                v78 = PostIrpRoutine;
              }
              else
              {
                v78 = 1;
              }
              FsRtlAddToTunnelCacheEx(
                v221 + 4720,
                *(_QWORD *)(*(_QWORD *)(v224 + 184) + 8LL),
                v264,
                &v264[2],
                (BYTE1(v264[23]) != 0 ? 2 : 0) | v78,
                80,
                &v264[14]);
            }
            --*(_WORD *)(*(_QWORD *)v217 + 190LL);
            LOBYTE(v212) = v212 | 0x20;
            v240 = (_QWORD *)PostIrpRoutine;
            if ( !v220 )
            {
              v83 = BYTE1(v212);
              if ( (v212 & 0x2000) == 0 )
              {
                NtfsReportDirNotify(
                  v3,
                  *((_QWORD *)FsContext + 9),
                  v221,
                  (_DWORD)FsContext + 16,
                  *((unsigned __int16 *)FsContext + 16),
                  PostIrpRoutine,
                  1,
                  2,
                  Fcb,
                  PostIrpRoutine);
                v83 = BYTE1(v212);
              }
              BYTE1(v212) = v83 | 2;
              ClearFlagInterlocked((char *)FsContext + 4, 112);
              TruncateSize = &NtfsLarge0;
            }
LABEL_77:
            if ( (v212 & 0x4000) != 0 || (v212 & 0x100) != 0 || v212 < 0 )
              FsRtlCheckOplockEx(
                (POPLOCK)(v224 + 88),
                Irp,
                0x50u,
                0,
                (POPLOCK_WAIT_COMPLETE_ROUTINE)PostIrpRoutine,
                (POPLOCK_FS_PREPOST_IRP)PostIrpRoutine);
            if ( *(_DWORD *)(v219 + 208) != 1 && (v212 & 0x800000) == 0 || !*(_WORD *)(*(_QWORD *)v217 + 188LL) || v220 )
            {
LABEL_86:
              v12 = 4294967288LL;
LABEL_87:
              if ( !v220 && *(_DWORD *)(v219 + 208) == 1 )
              {
                if ( *(_WORD *)(*(_QWORD *)v217 + 188LL) )
                {
                  if ( (v212 & 0x400) == 0
                    && FileObject->SectionObjectPointer == (PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v219 + 288) + 16LL) )
                  {
                    v66 = *(_DWORD *)(v219 + 256);
                    if ( v66 )
                    {
                      if ( (v66 != 32 || *(_QWORD *)(v219 + 184) != *(_QWORD *)(*(_QWORD *)(v221 + 48) + 184LL))
                        && (*(_DWORD *)(v219 + 200) & 1) != 0 )
                      {
                        BYTE2(v212) |= 1u;
                        if ( (v212 & 0x40000000) == 0
                          && (v212 & 0x4000) == 0
                          && (*(_DWORD *)(*(_QWORD *)v217 + 4LL) & 0x100) == 0 )
                        {
                          NtfsPrepareForUpdateDuplicate(v3, v217[0], (unsigned int)&v233, (unsigned int)&v224, 1, 0);
                        }
                        v89 = v219;
                        if ( (*(_DWORD *)(v219 + 200) & 8) != 0 )
                        {
                          if ( ((*(_DWORD *)(v219 + 32) + 7) & 0xFFFFFFF8) < *(_DWORD *)(v219 + 24) )
                          {
                            v185 = v212;
                            if ( (v212 & 0x10) != 0 )
                            {
                              NtfsCleanupAttributeContext(v3, v259);
                              v185 = v212;
                              v89 = v219;
                            }
                            memset(v259, 0, 0x58u);
                            LOBYTE(v212) = v185 | 0x10;
                            LOBYTE(v209) = 0;
                            v186 = NtfsLookupInFileRecord(
                                     v3,
                                     *(_QWORD *)(v89 + 184),
                                     *(_QWORD *)(v89 + 184) + 8LL,
                                     *(unsigned int *)(v89 + 256),
                                     v89 + 264,
                                     PostIrpRoutine,
                                     v209,
                                     PostIrpRoutine,
                                     PostIrpRoutine,
                                     v259);
                            v187 = v219;
                            if ( !v186 && (*(_DWORD *)(v219 + 512) & 4) == 0 )
                            {
                              PostIrpRoutine = 0xA90007115CLL;
                              NtfsAttachCorruption_BadOrOrphanFRS(
                                v3,
                                2,
                                463196,
                                0,
                                *(_QWORD *)(v219 + 184) + 8LL,
                                *(_QWORD *)(v219 + 184),
                                0);
                              NtfsAttachRepairInfoPriv(v3, 512, 0, 0xA90007115CLL);
                              if ( NtfsStatusDebugFlags )
                                NtfsStatusTraceAndDebugInternal(v3, 3221225730LL, 463196);
                              NtfsRaiseStatusInternal(
                                v3,
                                -1073741566,
                                *(_QWORD *)(v219 + 184) + 8,
                                *(_QWORD *)(v219 + 184),
                                463196);
                            }
                            LODWORD(CompletionRoutinea) = PostIrpRoutine;
                            NtfsChangeAttributeValue(
                              v3,
                              v217[0],
                              *(_DWORD *)(v187 + 32),
                              0,
                              (SIZE_T)CompletionRoutinea,
                              1,
                              1,
                              0,
                              0,
                              v259);
                            v32 = 512;
                            v188 = v219;
                            v189 = (*(_DWORD *)(v219 + 32) + 7) & 0xFFFFFFF8;
                            v190 = *(_DWORD *)(v219 + 200);
                            if ( (v190 & 0x20000) != 0
                              && *(_QWORD *)(v219 + 24) > v189
                              && *(_QWORD *)(v219 + 464) > v189 )
                            {
                              if ( (v190 & 0x200) != 0 )
                                v188 = v219;
                              *(_QWORD *)(v188 + 464) = v189;
                              v188 = v219;
                            }
                            *(_QWORD *)(v188 + 24) = v189;
                            *(_QWORD *)(v219 + 472) = v189;
                            v89 = v219;
                          }
                        }
                        else
                        {
                          v32 = *(_QWORD *)(v219 + 24);
                          if ( v32 )
                          {
                            v90 = *(unsigned int *)(v221 + 480);
                            v12 = (v90 + *(_QWORD *)(v219 + 32)) >> *(_BYTE *)(v221 + 488);
                            if ( (v90 + v32) >> *(_BYTE *)(v221 + 488) != v12 )
                            {
                              if ( (*(_DWORD *)(v219 + 200) & 0x20000) == 0
                                || MmCanFileBeTruncated(FileObject->SectionObjectPointer, (PLARGE_INTEGER)(v219 + 32)) )
                              {
                                NtfsDeleteAllocation(v3, 0x7FFFFFFFFFFFFFFFLL, 1, 1);
                              }
                              else if ( (v212 & 8) != 0 )
                              {
                                *(_DWORD *)(v219 + 200) &= ~1u;
                                BYTE2(v212) &= ~1u;
                              }
                              v89 = v219;
                            }
                            v261 = *(_QWORD *)(v89 + 32);
                            TruncateSize = (PLARGE_INTEGER)&v261;
                          }
                        }
                        LOBYTE(v32) = 1;
                        NtfsUpdateScbFromFileObject(FileObject, v89, v32);
                      }
                    }
                  }
                }
              }
              v34 = *(_DWORD *)(v219 + 204);
              if ( v34 )
              {
                if ( *(_DWORD *)(v219 + 208) == v34 + 1
                  && !*(_DWORD *)(v219 + 452)
                  && (*((_BYTE *)FsContext + 104) & 7) != 0 )
                {
                  v191 = *(_QWORD *)(v219 + 288);
                  if ( *(_QWORD *)(v191 + 16) )
                  {
                    if ( !*(_QWORD *)(v191 + 32)
                      && (FileObject->Flags & 8) == 0
                      && !v220
                      && MmCanFileBeTruncated((PSECTION_OBJECT_POINTERS)(v191 + 16), 0)
                      && (*(_DWORD *)(*(_QWORD *)(v219 + 184) + 4LL) & 0x100) == 0
                      && (v212 & 0x4000) == 0 )
                    {
                      NtfsCheckpointCurrentTransaction(v3);
                      if ( v218[0] )
                      {
                        NtfsReleaseFcbEx(v3, *(_QWORD *)(v224 + 184), 0);
                        v218[0] = 0;
                      }
                      NtfsReleaseSharedResources(v3);
                      NtfsFlushAndPurgeScb(v3, v219);
                      *(_DWORD *)(v3 + 24) = PostIrpRoutine;
                    }
                  }
                }
              }
              v28 = *(_QWORD *)v217;
              if ( *(_DWORD *)(*(_QWORD *)v217 + 24LL) == 1
                && (v212 & 4) != 0
                && *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v217 + 96LL) + 8428LL) <= (unsigned int)NtfsMaxDelayCloseCount
                && !v220
                && (*(_DWORD *)(*(_QWORD *)v217 + 4LL) & 4) == 0
                && (*(_DWORD *)(v219 + 200) & 0x1000000) == 0 )
              {
                SetFlagInterlocked(v219 + 200, 0x200000);
              }
              goto LABEL_90;
            }
            if ( (v212 & 0x400) == 0 && (v212 & 0x800000) == 0 )
            {
              if ( *(_DWORD *)(v219 + 256) && (*(_DWORD *)(v219 + 200) & 4) != 0 )
              {
                if ( (v212 & 0x40000000) == 0
                  && (v212 & 0x4000) == 0
                  && (*(_DWORD *)(*(_QWORD *)v217 + 4LL) & 0x100) == 0 )
                {
                  NtfsPrepareForUpdateDuplicate(v3, v217[0], (unsigned int)&v233, (unsigned int)&v224, 1, 0);
                }
                if ( (*(_DWORD *)(v219 + 200) & 8) != 0 )
                {
                  memset(v259, 0, 0x58u);
                  LOBYTE(v212) = v212 | 0x10;
                  LOBYTE(v209) = 0;
                  v100 = NtfsLookupInFileRecord(
                           v3,
                           *(_QWORD *)(v219 + 184),
                           *(_QWORD *)(v219 + 184) + 8LL,
                           *(unsigned int *)(v219 + 256),
                           v219 + 264,
                           PostIrpRoutine,
                           v209,
                           PostIrpRoutine,
                           PostIrpRoutine,
                           v259);
                  v101 = v219;
                  if ( !v100 && (*(_DWORD *)(v219 + 512) & 4) == 0 )
                  {
                    PostIrpRoutine = 0xA900071091LL;
                    NtfsAttachCorruption_BadOrOrphanFRS(
                      v3,
                      2,
                      462993,
                      0,
                      *(_QWORD *)(v219 + 184) + 8LL,
                      *(_QWORD *)(v219 + 184),
                      0);
                    NtfsAttachRepairInfoPriv(v3, 512, 0, 0xA900071091LL);
                    if ( NtfsStatusDebugFlags )
                      NtfsStatusTraceAndDebugInternal(v3, 3221225730LL, 462993);
                    NtfsRaiseStatusInternal(
                      v3,
                      -1073741566,
                      *(_QWORD *)(v219 + 184) + 8,
                      *(_QWORD *)(v219 + 184),
                      462993);
                  }
                  LODWORD(CompletionRoutine) = PostIrpRoutine;
                  NtfsChangeAttributeValue(
                    v3,
                    v217[0],
                    *(_DWORD *)(v101 + 32),
                    0,
                    (SIZE_T)CompletionRoutine,
                    1,
                    1,
                    0,
                    0,
                    v259);
                  v85 = v219;
                  v12 = 4294967288LL;
                  if ( ((*(_DWORD *)(v219 + 32) + 7) & 0xFFFFFFF8) != *(_DWORD *)(v219 + 24) )
                  {
                    v102 = (*(_DWORD *)(v219 + 32) + 7) & 0xFFFFFFF8;
                    v103 = *(_DWORD *)(v219 + 200);
                    if ( (v103 & 0x20000) != 0 && *(_QWORD *)(v219 + 24) > v102 && *(_QWORD *)(v219 + 464) > v102 )
                    {
                      if ( (v103 & 0x200) != 0 )
                        v85 = v219;
                      *(_QWORD *)(v85 + 464) = v102;
                      v85 = v219;
                    }
                    *(_QWORD *)(v85 + 24) = v102;
                    v85 = v219;
                  }
                }
                else
                {
                  NtfsWriteFileSizes(v3, v219, 0, 0, 1, 1);
                  v12 = 4294967288LL;
                  v85 = v219;
                }
                LOBYTE(v84) = 1;
                NtfsUpdateScbFromFileObject(FileObject, v85, v84);
                goto LABEL_87;
              }
              goto LABEL_86;
            }
            if ( (v212 & 0x40000000) != 0
              || !*(_QWORD *)(*(_QWORD *)v217 + 120LL)
              || (v212 & 0x4000) != 0
              || (*(_DWORD *)(*(_QWORD *)v217 + 4LL) & 0x100) != 0 )
            {
              v169 = 2;
            }
            else
            {
              NtfsPrepareForUpdateDuplicate(v3, v217[0], (unsigned int)&v233, (unsigned int)&v224, 1, 0);
              v169 = 2;
            }
            if ( *(_DWORD *)(v219 + 256) )
            {
              if ( (v212 & 0x10) != 0 )
                NtfsCleanupAttributeContext(v3, v259);
              if ( *(_DWORD *)(v219 + 256) == 128
                && ((*(_DWORD *)(v219 + 200) & 0x6000000) != 0 || *(_QWORD *)(v219 + 632) == -1)
                && xmmword_1400957B0 )
              {
                xmmword_1400957B0(v3, *(_QWORD *)v217);
              }
              memset(v259, 0, 0x58u);
              v215 = v212 | 0x10;
              LOBYTE(v209) = 0;
              if ( (unsigned __int8)NtfsLookupInFileRecord(
                                      v3,
                                      *(_QWORD *)(v219 + 184),
                                      *(_QWORD *)(v219 + 184) + 8LL,
                                      *(unsigned int *)(v219 + 256),
                                      v219 + 264,
                                      PostIrpRoutine,
                                      v209,
                                      PostIrpRoutine,
                                      PostIrpRoutine,
                                      v259)
                || (*(_DWORD *)(v219 + 512) & 4) != 0 )
              {
                v169 = *(_WORD *)(v259[0] + 12);
                goto LABEL_796;
              }
              PostIrpRoutine = 0xA900070F88LL;
              NtfsAttachCorruption_BadOrOrphanFRS(
                v3,
                2,
                462728,
                0,
                *(_QWORD *)(v219 + 184) + 8LL,
                *(_QWORD *)(v219 + 184),
                0);
              NtfsAttachRepairInfoPriv(v3, 512, 0, 0xA900070F88LL);
              if ( NtfsStatusDebugFlags )
                NtfsStatusTraceAndDebugInternal(v3, 3221225730LL, 462728);
              NtfsRaiseStatusInternal(v3, -1073741566, *(_QWORD *)(v219 + 184) + 8, *(_QWORD *)(v219 + 184), 462728);
LABEL_801:
              LODWORD(Size) = PostIrpRoutine;
              for ( j = NtfsLookupExternalAttribute(
                          v3,
                          *(_QWORD *)(v170 + 184),
                          *(_DWORD *)(v170 + 256),
                          (PCUNICODE_STRING)(v170 + 264),
                          PostIrpRoutine,
                          0,
                          (void *)PostIrpRoutine,
                          Size,
                          (__int64)v259);
                    j;
                    j = NtfsLookupInFileRecord(
                          v3,
                          *(_QWORD *)(v219 + 184),
                          0,
                          *(unsigned int *)(v219 + 256),
                          v219 + 264,
                          PostIrpRoutine,
                          v210,
                          PostIrpRoutine,
                          PostIrpRoutine,
                          v259) )
              {
LABEL_796:
                NtfsDeleteAttributeRecord(v3, *(_QWORD *)v217, 15, v259);
                v170 = v219;
                if ( v259[5] )
                  goto LABEL_801;
                LOBYTE(v210) = 0;
              }
              NtfsCleanupAttributeContext(v3, v259);
              LOBYTE(v212) = v215 & 0xEF;
              if ( v169 >= 0 && *(__int16 *)(v219 + 460) >= 0
                || (unsigned __int8)NtfsIsSparseStreamRemaining(v3, v217[0]) )
              {
                v174 = 0x200000;
              }
              else
              {
                v172 = (_DWORD *)NtfsAddStructToRollbackList(v3, 1827, *(_QWORD *)v217, 1);
                v173 = ~v172[11] & 0x200;
                v172[11] |= v173;
                v172[10] |= v173 & *(_DWORD *)(*(_QWORD *)v217 + 176LL);
                v172[1] |= 0x10u;
                *(_DWORD *)(*(_QWORD *)v217 + 176LL) &= ~0x200u;
                *(_DWORD *)(*(_QWORD *)v217 + 184LL) |= 4u;
                *(_DWORD *)(*(_QWORD *)v217 + 4LL) |= 0x10u;
                *(_QWORD *)(v3 + 16) |= 4uLL;
                v174 = 2129920;
              }
              NtfsPostUsnChangeWithOverrideOption(v3, v217[0], v174, 0, PostIrpRoutine, PostIrpRoutine, PostIrpRoutine);
            }
            if ( !v220 )
            {
              if ( (v212 & 0x800000) != 0 )
              {
                v260 = PostIrpRoutine;
                v260 = TxfWriteAttributeLogRecord(
                         v3,
                         v217[0],
                         *(_DWORD *)(v219 + 256),
                         (int)v219 + 264,
                         PostIrpRoutine,
                         PostIrpRoutine,
                         PostIrpRoutine,
                         PostIrpRoutine,
                         16);
                TxfUpdateTxfDataAttributeMembers(
                  v3,
                  v217[0],
                  PostIrpRoutine,
                  PostIrpRoutine,
                  (*(_DWORD *)(*(_QWORD *)v217 + 4LL) & 0x100000) == 0,
                  (__int64)&v260,
                  PostIrpRoutine,
                  PostIrpRoutine,
                  PostIrpRoutine,
                  PostIrpRoutine,
                  PostIrpRoutine);
              }
              NtfsCheckpointCurrentTransaction(v3);
              LOBYTE(v212) = v212 | 0x40;
            }
            if ( *(_BYTE *)(v219 + 460) || (*(_DWORD *)(v219 + 512) & 1) != 0 )
              *(_QWORD *)(v219 + 464) = PostIrpRoutine;
            if ( (*(_DWORD *)(v219 + 200) & 0x20000) != 0 && *(__int64 *)(v219 + 24) > 0 && *(__int64 *)(v219 + 464) > 0 )
              *(_QWORD *)(v219 + 464) = PostIrpRoutine;
            *(_QWORD *)(v219 + 24) = PostIrpRoutine;
            v175 = v219;
            v176 = *(_DWORD *)(v219 + 200);
            if ( (v176 & 0x20000) == 0 || *(__int64 *)(v219 + 32) >= 0 )
              goto LABEL_847;
            v177 = PostIrpRoutine;
            if ( *(__int64 *)(v219 + 464) <= 0 )
              v177 = *(_QWORD *)(v219 + 464);
            if ( v177 <= *(_QWORD *)(v219 + 40) )
            {
LABEL_847:
              *(_QWORD *)(v175 + 32) = PostIrpRoutine;
              v181 = v219;
              if ( (*(_DWORD *)(v219 + 200) & 0x200) != 0 )
                v181 = v219;
              v182 = *(_DWORD *)(v181 + 200);
              if ( (v182 & 0x20000) == 0 )
                goto LABEL_862;
              v183 = *(_QWORD *)(v181 + 464);
              if ( v183 >= 0 )
              {
                if ( *(__int64 *)(v181 + 40) <= 0 )
                  goto LABEL_862;
                if ( *(_QWORD *)(*(_QWORD *)(v181 + 288) + 16LL) )
                {
                  if ( v183 <= 0 )
                    goto LABEL_862;
                  if ( (v182 & 0x200) == 0 )
                  {
LABEL_861:
                    *(_QWORD *)(v181 + 464) = PostIrpRoutine;
                    v181 = v219;
LABEL_862:
                    *(_QWORD *)(v181 + 40) = PostIrpRoutine;
                    *(_DWORD *)(v219 + 256) = PostIrpRoutine;
                    if ( (v212 & 0x800000) == 0 || (*(_DWORD *)(*(_QWORD *)(v219 + 528) + 24LL) & 1) != 0 )
                    {
                      *(_DWORD *)(v219 + 512) |= 0x440u;
                      TruncateSize = &NtfsLarge0;
                    }
                    else
                    {
                      *(_DWORD *)(v219 + 512) |= 0x200000u;
                      *(_DWORD *)(*(_QWORD *)(v219 + 528) + 24LL) |= 2u;
                    }
                    *(_DWORD *)(v219 + 512) &= 0xFFFFE5FF;
                    NtfsUpdateFileTimestampsForChange(*(_QWORD *)v217, FsContext, 0x400000);
                    FileObject->Flags &= ~0x4000u;
                    LOBYTE(v184) = 1;
                    NtfsUpdateScbFromFileObject(FileObject, v219, v184);
                    FileObject->Flags |= 0x4000u;
                    v12 = 4294967288LL;
                    goto LABEL_87;
                  }
                }
                else if ( (v182 & 0x200) == 0 || !v183 )
                {
                  goto LABEL_861;
                }
              }
              else if ( (v182 & 0x200) == 0 )
              {
                goto LABEL_861;
              }
              v181 = v219;
              goto LABEL_861;
            }
            if ( (v176 & 0x200) != 0 )
              v175 = v219;
            v178 = *(_DWORD *)(v175 + 200);
            if ( (v178 & 0x20000) != 0 )
            {
              v179 = *(_QWORD *)(v175 + 464);
              if ( v179 < v177 )
              {
                if ( (v178 & 0x200) == 0 )
                  goto LABEL_845;
                goto LABEL_844;
              }
              if ( *(_QWORD *)(v175 + 40) > v177 )
              {
                if ( *(_QWORD *)(*(_QWORD *)(v175 + 288) + 16LL) )
                {
                  if ( v177 == 0x7FFFFFFFFFFFFFFFLL )
                  {
                    if ( (v178 & 0x200) != 0 && v179 != 0x7FFFFFFFFFFFFFFFLL )
                      v175 = v219;
                    *(_QWORD *)(v175 + 464) = 0x7FFFFFFFFFFFFFFFLL;
                    v175 = v219;
                  }
                  else
                  {
                    v180 = (v177 + 4095) & 0xFFFFFFFFFFFFF000uLL;
                    if ( v180 < v179 )
                    {
                      if ( (v178 & 0x200) != 0 )
                        v175 = v219;
                      *(_QWORD *)(v175 + 464) = v180;
                      v175 = v219;
                    }
                  }
                  goto LABEL_846;
                }
                if ( (v178 & 0x200) == 0 || v179 == v177 )
                  goto LABEL_845;
LABEL_844:
                v175 = v219;
LABEL_845:
                *(_QWORD *)(v175 + 464) = v177;
                v175 = v219;
              }
            }
LABEL_846:
            *(_QWORD *)(v175 + 40) = v177;
            v175 = v219;
            goto LABEL_847;
          }
          if ( !v20 )
            goto LABEL_77;
          BYTE1(v212) |= 0x40u;
          if ( (v212 & 0x10000000) != 0 )
          {
            v67 = (__int64)v240;
          }
          else
          {
            v168 = NtfsFindMatchingLcbPair(v20, 0);
            v67 = v168;
            v240 = (_QWORD *)v168;
            if ( v168 && *(_DWORD *)(v168 + 188) )
              BYTE1(v212) &= ~0x40u;
          }
          if ( (v212 & 0x4000) != 0 && *(_WORD *)(*(_QWORD *)v217 + 190LL) > 1u )
          {
            NtfsAcquireExclusiveScbEx(v3, v224, 0);
            v218[0] = 1;
            v109 = v217[0];
            if ( *(_QWORD *)(*(_QWORD *)v217 + 120LL) )
            {
              NtfsAcquireSharedFcb(v3, *(_QWORD *)(*(_QWORD *)(v221 + 160) + 184LL), *(_QWORD *)(v221 + 160), 0);
              LOBYTE(v212) = v212 | 2;
              NtfsAcquireQuotaControl(v3, *(_QWORD *)(*(_QWORD *)v217 + 120LL));
              v109 = v217[0];
            }
            LOBYTE(v212) = v212 & 0xFB;
            if ( (v212 & 0x10000000) != 0 )
            {
              NtfsCheckpointCurrentTransaction(v3);
              LOBYTE(v212) = v212 | 0x20;
            }
            else
            {
              v110 = PostIrpRoutine;
              if ( (*(_BYTE *)(*(_QWORD *)(v20 + 192) + 65LL) & 3) != 2 )
                v110 = *(_QWORD *)(v20 + 192);
              NtfsPostUsnChangeWithOverrideOption(v3, v109, -2147418112, 0, PostIrpRoutine, PostIrpRoutine, v110);
              LOBYTE(v264[23]) = 0;
              if ( (v212 & 0x2000) != 0 || *(int *)(v221 + 4) < 0 || (FileObject->Flags & 0x20000) != 0 )
              {
                NtfsRemoveLink(v3, v217[0], (__int64)v264, PostIrpRoutine);
              }
              else
              {
                NtfsRemoveLink(v3, v217[0], (__int64)v264, (__int64)&v264[14]);
                NtfsGetTunneledData(v3, *(_QWORD *)v217, *(unsigned __int8 *)(*(_QWORD *)(v20 + 192) + 65LL), &v264[14]);
                if ( (*((_DWORD *)FsContext + 1) & 0x4000000) != 0
                  || (v111 = 1, (*(_DWORD *)(*(_QWORD *)(v224 + 184) + 16LL) & 0x400) == 0) )
                {
                  v111 = PostIrpRoutine;
                }
                FsRtlAddToTunnelCacheEx(
                  v221 + 4720,
                  *(_QWORD *)(*(_QWORD *)(v224 + 184) + 8LL),
                  v264,
                  &v264[2],
                  v111 | *(_BYTE *)(*(_QWORD *)(v20 + 192) + 65LL) & 2,
                  80,
                  &v264[14]);
              }
              NtfsCheckpointCurrentTransaction(v3);
              LOBYTE(v212) = v212 | 0x20;
              --*(_WORD *)(*(_QWORD *)v217 + 190LL);
              NtfsRemovePrefix(v3, v20);
              if ( (*(_DWORD *)(v20 + 4) & 0x20) != 0 )
              {
                NtfsRemoveHashEntry(
                  v3,
                  *(_QWORD *)(*(_QWORD *)(v20 + 48) + 96LL) + 4968LL,
                  *(unsigned int *)(v20 + 184),
                  v20);
                *(_DWORD *)(v20 + 184) = PostIrpRoutine;
                ClearFlagInterlocked(v20 + 4, 32);
              }
              SetFlagInterlocked(v20 + 4, 2);
              *(_DWORD *)(v20 + 180) = PostIrpRoutine;
              *(_DWORD *)(v20 + 156) = PostIrpRoutine;
              if ( v67 )
              {
                NtfsRemovePrefix(v3, v67);
                if ( (*(_DWORD *)(v67 + 4) & 0x20) != 0 )
                {
                  NtfsRemoveHashEntry(
                    v3,
                    *(_QWORD *)(*(_QWORD *)(v67 + 48) + 96LL) + 4968LL,
                    *(unsigned int *)(v67 + 184),
                    v67);
                  *(_DWORD *)(v67 + 184) = PostIrpRoutine;
                  ClearFlagInterlocked(v67 + 4, 32);
                }
                SetFlagInterlocked(v67 + 4, 2);
                *(_DWORD *)(v67 + 180) = PostIrpRoutine;
                *(_DWORD *)(v67 + 156) = PostIrpRoutine;
              }
            }
            NtfsUpdateFcbTimestamps(Fcb, 2684354576LL);
            if ( (v212 & 0x2000) == 0 && (v220 & 0x80000000) == 0 && (v212 & 0x10000000) == 0 )
              NtfsReportDirNotify(
                v3,
                *((_QWORD *)FsContext + 9),
                v221,
                (_DWORD)FsContext + 16,
                *((unsigned __int16 *)FsContext + 16),
                PostIrpRoutine,
                1,
                2,
                Fcb,
                PostIrpRoutine);
            v233 = PostIrpRoutine;
            if ( (v220 & 0x80000000) == 0 )
              NtfsUpdateFileTimestampsForChange(*(_QWORD *)v217, FsContext, 0);
            FileObject->Flags &= ~0x4000u;
            LOBYTE(v112) = 1;
            NtfsUpdateScbFromFileObject(FileObject, v219, v112);
            FileObject->Flags |= 0x4000u;
            goto LABEL_77;
          }
          if ( (v212 & 0x4000) == 0 )
            goto LABEL_77;
          BYTE1(v212) &= ~0x40u;
          if ( (*(_DWORD *)(*(_QWORD *)v217 + 176LL) & 0x10000000) != 0
            || (*((_DWORD *)FsContext + 2) & 0x10000) == 0 && !*(_QWORD *)(*(_QWORD *)v217 + 352LL) )
          {
            goto LABEL_77;
          }
          if ( (*(_DWORD *)(v20 + 4) & 0x40) != 0 )
            goto LABEL_77;
          if ( *(_QWORD *)(v3 + 400) )
            goto LABEL_77;
          v68 = *(_QWORD *)(v221 + 200);
          if ( *(_QWORD *)(v20 + 24) == v68 || !v68 )
            goto LABEL_77;
        }
        else
        {
          if ( (*(_DWORD *)(v20 + 4) & 1) == 0
            && ((*(_BYTE *)(*(_QWORD *)(v20 + 192) + 65LL) & 3) == 0
             || (*(_DWORD *)(*(_QWORD *)(v20 + 48) + 4LL) & 0x20) == 0) )
          {
            goto LABEL_77;
          }
          v32 = (__int64)FsContext;
          if ( (*((_DWORD *)FsContext + 2) & 0x10000) == 0 || (v33 & 0x40) != 0 )
            goto LABEL_77;
          if ( *(_QWORD *)(v3 + 400) )
            goto LABEL_77;
          v75 = *(_QWORD *)(v221 + 200);
          if ( *(_QWORD *)(v20 + 24) == v75 || !v75 )
            goto LABEL_77;
        }
        NtfsRenameToPrivateDir(v3, (__int64)FsContext, v20, v224, (__int64)v218);
        HIBYTE(v212) |= 0x80u;
        goto LABEL_77;
      case 3u:
        goto LABEL_49;
      case 4u:
        FileObject->Flags |= 0x4000u;
        if ( *((_BYTE *)FsContext + 88) == 4 && (*((_DWORD *)FsContext + 1) & 0x400) != 0 )
        {
          v230 = 0;
          v229 = 0;
          ExAcquireResourceExclusiveLite((PERESOURCE)(v221 + 6800), 1u);
          v230 = 1;
          ExAcquireResourceExclusiveLite(&stru_1400953C0, 1u);
          v229 = 1;
          ClearFlagInterlocked((char *)FsContext + 4, 1024);
          *(_DWORD *)(v221 + 6904) &= ~2u;
          *(_QWORD *)(v221 + 6928) = PostIrpRoutine;
          if ( !--dword_140095450 )
            NtfsSendGlobalCorruptionActionEvent(v3);
          ExReleaseResourceLite(&stru_1400953C0);
          ExReleaseResourceLite((PERESOURCE)(v221 + 6800));
        }
        v28 = v221;
        if ( *(struct _FILE_OBJECT **)(v221 + 1480) == FileObject )
        {
          v163 = *(_QWORD *)(v221 + 72);
          if ( v163 )
          {
            NtfsAcquireExclusiveFcb(v3, *(_QWORD *)(v163 + 184), *(_QWORD *)(v221 + 72), 0);
            *(_QWORD *)(v221 + 5368) = 0x7FFFFFFFFFFFFFFFLL;
            *(_QWORD *)(v221 + 5376) = PostIrpRoutine;
            *(_QWORD *)(v221 + 1480) = PostIrpRoutine;
            NtfsReleaseFcbEx(v3, *(_QWORD *)(*(_QWORD *)(v221 + 72) + 184LL), 0);
            v28 = v221;
          }
        }
        if ( (*(_DWORD *)(v28 + 4) & 2) == 0
          || (struct _FILE_OBJECT *)(*(_QWORD *)(v28 + 1472) & 0xFFFFFFFFFFFFFFFEuLL) != FileObject )
        {
          goto LABEL_90;
        }
        v91 = *(_DWORD *)(v3 + 12);
        if ( (v91 & 0x200) == 0 )
        {
          *(_DWORD *)(v3 + 12) = v91 | 0x200;
          NtfsRaiseStatusInternal(v3, -1073741608, 0, 0, 461358);
          goto LABEL_407;
        }
        if ( *(struct _FILE_OBJECT **)(v28 + 1472) == (struct _FILE_OBJECT *)((char *)&FileObject->Type + 1) )
        {
          NtfsSendBeginDismountEvent(v3, v28, 0, 3);
          if ( (*(_DWORD *)(v221 + 24) & 0x40000) != 0 )
          {
            v164 = *(_QWORD *)(v221 + 64);
            if ( !v164 || (*(_DWORD *)(v164 + 200) & 0x20000) != 0 )
              NtfsPurgeLogFile(v221, v3);
          }
          NtfsPerformDismountOnVcb((PVOID)v3, 3, PostIrpRoutine);
          goto LABEL_733;
        }
        if ( (FileObject->Flags & 0x1000) != 0 )
        {
          if ( (v212 & 0x80000) != 0 && (v212 & 0x100000) == 0 )
          {
            if ( (unsigned __int8)NtfsIsFileStillValid(*(_QWORD *)v217) )
            {
              NtfsReleaseFcbEx(v3, *(_QWORD *)(v219 + 184), 0);
              NtfsFlushVolume(v3);
              NtfsAcquireExclusiveFcb(v3, *(_QWORD *)(v219 + 184), v219, 8);
            }
            v28 = v221;
          }
          if ( *(_DWORD *)(v28 + 256) == 1 )
          {
            v28 = v221;
            if ( *(_DWORD *)(v221 + 260) - *(_DWORD *)(v221 + 268) == 1 )
            {
              NtfsSendBeginDismountEvent(v3, v221, 0, 3);
              NtfsPerformDismountOnVcb((PVOID)v3, 3, PostIrpRoutine);
              v28 = v221;
            }
          }
          else
          {
LABEL_733:
            v28 = v221;
          }
        }
        ClearFlagInterlocked(v28 + 4, 32770);
        *(_QWORD *)(v221 + 1472) = PostIrpRoutine;
        BYTE2(v212) |= 2u;
        if ( (BYTE2(v212) & 0x18) == 8 && (unsigned __int8)NtfsIsFileStillValid(*(_QWORD *)v217) && !v220 )
        {
          if ( *(_DWORD *)(v221 + 2156) == -1073741202 )
          {
            *(_DWORD *)(v221 + 2156) = PostIrpRoutine;
            NtfsPostSpecial(v3, v221, (unsigned int)NtfsDeleteUsnSpecial, v221 + 2144, 13);
          }
          if ( !v220 )
          {
            v28 = v221;
            if ( (*(_DWORD *)(v221 + 4504) & 0xE00) != 0 && (*(_DWORD *)(v221 + 4504) & 0x40) != 0 )
              NtfsPostRepairQuotaIndex(v3);
          }
        }
        goto LABEL_90;
    }
    if ( v232 != 6 )
    {
      if ( (!v3 || (*(_DWORD *)(v3 + 16) & 0x100000LL) == 0)
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x800) != 0 )
      {
        McTemplateU0q_EtwWriteTransfer(&NtfsLog_Context, cleanup_c4599, v232);
      }
      KeBugCheckEx(0x24u, 0xAD000711FCuLL, (int)v232, 0, PostIrpRoutine);
    }
LABEL_49:
    NtfsSnapshotScb(v3, v219);
    v26 = v219;
    v27 = *(_DWORD *)(v219 + 256);
    if ( v27 == 128 && *(_WORD *)v219 == 1797
      || v27 == 160
      && *(_WORD *)(v219 + 264) == 8
      && **(_QWORD **)(v219 + 272) == 0x30003300490024LL
      && (unsigned __int16)(*(_WORD *)v219 - 1795) <= 1u )
    {
      FsRtlCheckOplock((POPLOCK)(v219 + 88), Irp, 0, 0, (POPLOCK_FS_PREPOST_IRP)PostIrpRoutine);
      v26 = v219;
    }
    LOBYTE(v25) = 1;
    NtfsUpdateScbFromFileObject(FileObject, v26, v25);
    FileObject->Flags |= 0x4000u;
    if ( (*((_DWORD *)FsContext + 1) & 0x800000) != 0 )
    {
      if ( v232 == 6 )
      {
        FsRtlNotifyCleanup(*(PNOTIFY_SYNC *)(v221 + 1464), (PLIST_ENTRY)(v221 + 1448), FsContext);
        ClearFlagInterlocked((char *)FsContext + 4, 0x800000);
        _InterlockedDecrement((volatile signed __int32 *)(v221 + 2440));
      }
      else
      {
        FsRtlNotifyCleanup(*(PNOTIFY_SYNC *)(v219 + 768), (PLIST_ENTRY)(v219 + 752), FsContext);
        ClearFlagInterlocked((char *)FsContext + 4, 0x800000);
        _InterlockedDecrement((volatile signed __int32 *)(v221 + 2436));
      }
    }
    if ( (v212 & 0x80000) != 0
      && (v212 & 0x100000) == 0
      && *(_WORD *)v219 == 1795
      && (unsigned __int8)NtfsIsFileStillValid(*(_QWORD *)v217) )
    {
      if ( (v212 & 0x100) == 0 )
      {
        if ( v20
          && ((v58 = *(_DWORD *)(v20 + 4), (v58 & 1) != 0)
           || (*(_BYTE *)(*(_QWORD *)(v20 + 192) + 65LL) & 3) != 0
           && (*(_DWORD *)(*(_QWORD *)(v20 + 48) + 4LL) & 0x20) != 0)
          && ((*((_DWORD *)FsContext + 2) & 0x10000) != 0 || *(_QWORD *)(*(_QWORD *)v217 + 352LL))
          && (v58 & 0x40) == 0
          && !*(_QWORD *)(v3 + 400)
          && (v59 = *(_QWORD *)(v221 + 200), *(_QWORD *)(v20 + 24) != v59)
          && v59 )
        {
          NtfsRenameToPrivateDir(v3, (__int64)FsContext, v20, v224, (__int64)v218);
          HIBYTE(v212) |= 0x80u;
        }
        else
        {
          v28 = *(_QWORD *)v217;
          if ( *(_DWORD *)(*(_QWORD *)v217 + 24LL) == 1
            && (v212 & 4) != 0
            && *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v217 + 96LL) + 8428LL) <= (unsigned int)NtfsMaxDelayCloseCount
            && (*(_DWORD *)(v219 + 200) & 0x1000000) == 0 )
          {
            SetFlagInterlocked(v219 + 200, 0x200000);
          }
        }
LABEL_59:
        if ( (v212 & 0x100) != 0 || v212 < 0 )
          FsRtlCheckOplockEx(
            (POPLOCK)(v224 + 88),
            Irp,
            0x50u,
            0,
            (POPLOCK_WAIT_COMPLETE_ROUTINE)PostIrpRoutine,
            (POPLOCK_FS_PREPOST_IRP)PostIrpRoutine);
        goto LABEL_90;
      }
LABEL_407:
      if ( v20 )
      {
        v240 = (_QWORD *)v20;
        if ( (*(_DWORD *)(v20 + 4) & 2) != 0 )
        {
          v240 = (_QWORD *)PostIrpRoutine;
          v20 = PostIrpRoutine;
          v226 = PostIrpRoutine;
          v92 = PostIrpRoutine;
          v224 = PostIrpRoutine;
          goto LABEL_410;
        }
      }
      else
      {
        v165 = NtfsGetNextParentLcb(v3, *(_QWORD *)v217, 0);
        v240 = (_QWORD *)v165;
        if ( v165 )
        {
          v92 = *(_QWORD *)(v165 + 24);
          v224 = v92;
          if ( v92 )
            Fcb = *(_QWORD *)(v92 + 184);
          goto LABEL_410;
        }
      }
      v92 = v224;
LABEL_410:
      if ( !v92 )
      {
        while ( 1 )
        {
          v258 = 0;
          memset(v259, 0, 0x58u);
          LOBYTE(v212) = v212 | 0x10;
          LOBYTE(v209) = 0;
          if ( (unsigned __int8)NtfsLookupInFileRecord(
                                  v3,
                                  *(_QWORD *)v217,
                                  *(_QWORD *)v217 + 8LL,
                                  48,
                                  PostIrpRoutine,
                                  PostIrpRoutine,
                                  v209,
                                  PostIrpRoutine,
                                  PostIrpRoutine,
                                  v259) )
            break;
          PostIrpRoutine = 0xFC00070B5DLL;
          NtfsAttachCorruption_BadOrOrphanFRS(v3, 2, 461661, 0, *(_QWORD *)v217 + 8LL, *(__int64 *)v217, 0);
          NtfsAttachRepairInfoPriv(v3, 256, 0, 0xFC00070B5DLL);
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(v3, 3221225730LL, 461661);
          NtfsRaiseStatusInternal(v3, -1073741566, v217[0] + 8, v217[0], 461661);
        }
        v94 = v259[0] + *(unsigned __int16 *)(v259[0] + 20);
        v95 = *(_DWORD *)(*(_QWORD *)v217 + 8LL);
        if ( v95 == 5 || (v96 = *(_QWORD *)(*(_QWORD *)v217 + 320LL), *(_DWORD *)(v96 + 88) == v95) )
          v96 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v217 + 96LL) + 6248LL);
        Fcb = NtfsCreateFcb(v3, v221, v96, *(_QWORD *)v94, 66, PostIrpRoutine);
        v97 = NtfsCreateScb(v3, Fcb, 160, (unsigned int)&NtfsFileNameIndex, 0, PostIrpRoutine, PostIrpRoutine);
        v224 = v97;
        if ( (*(_DWORD *)(v97 + 200) & 0x200) != 0 )
        {
          NtfsSnapshotScb(v3, v97);
          LODWORD(v97) = v224;
        }
        *((_QWORD *)&v258 + 1) = v94 + 66;
        LOWORD(v258) = 2 * *(unsigned __int8 *)(v94 + 64);
        WORD1(v258) = v258;
        NtfsCreateLcb(v3, v97, v217[0], (unsigned int)&v258, *(_BYTE *)(v94 + 65), PostIrpRoutine);
        v218[0] = 1;
        NtfsCleanupAttributeContext(v3, v259);
        LOBYTE(v212) = v212 & 0xEF;
      }
      NtfsDeleteFile(v3, v217[0], PostIrpRoutine, PostIrpRoutine);
      --*(_WORD *)(*(_QWORD *)v217 + 190LL);
      LOBYTE(v212) = v212 | 0x20;
      v93 = v221;
      if ( *(int *)(v221 + 4) >= 0 )
      {
        FsRtlDeleteKeyFromTunnelCache((TUNNEL *)(v221 + 4720), *(_QWORD *)(*(_QWORD *)v217 + 8LL));
        v93 = v221;
      }
      v240 = (_QWORD *)PostIrpRoutine;
      if ( !v220 )
      {
        v98 = BYTE1(v212);
        if ( (v212 & 0x2000) == 0 )
        {
          NtfsReportDirNotify(
            v3,
            *((_QWORD *)FsContext + 9),
            v93,
            (_DWORD)FsContext + 16,
            *((unsigned __int16 *)FsContext + 16),
            PostIrpRoutine,
            2,
            2,
            Fcb,
            PostIrpRoutine);
          v98 = BYTE1(v212);
        }
        BYTE1(v212) = v98 | 2;
        ClearFlagInterlocked((char *)FsContext + 4, 112);
      }
      goto LABEL_59;
    }
LABEL_90:
    if ( v232 == 4 )
    {
      v12 = 4;
      v7 = 8;
      goto LABEL_117;
    }
    v35 = *(_QWORD *)(*(_QWORD *)v217 + 192LL);
    if ( *(_QWORD *)(*(_QWORD *)v217 + 152LL) != v35 )
    {
      v60 = *(_DWORD *)(*(_QWORD *)v217 + 4LL);
      if ( (v60 & 0x10) != 0 )
      {
        *(_QWORD *)(*(_QWORD *)v217 + 152LL) = v35;
      }
      else
      {
        if ( (v60 & 1) != 0 || !(unsigned __int8)NtfsCheckLastAccess(v3, *(_QWORD *)v217) )
          goto LABEL_92;
        *(_DWORD *)(*(_QWORD *)v217 + 4LL) |= 0x10u;
      }
      *(_DWORD *)(*(_QWORD *)v217 + 184LL) |= 0x20u;
    }
LABEL_92:
    if ( (v212 & 0x80000) == 0 || (v212 & 0x100000) != 0 || !(unsigned __int8)NtfsIsFileStillValid(*(_QWORD *)v217) )
      goto LABEL_93;
    if ( (*(_DWORD *)(*(_QWORD *)v217 + 4LL) & 0x10) == 0 || v220 || (v212 & 0x20000000) != 0 )
    {
      v48 = 512;
      v12 = 8;
    }
    else
    {
      NtfsUpdateStandardInformation(v3, v217[0]);
      v48 = 512;
      v12 = 8;
    }
    v49 = v233;
    if ( ((*(_DWORD *)(*(_QWORD *)v217 + 184LL) & 0xD00000FC) != 0
       || v233 && (*(_DWORD *)(v233 + 180) & 0xD00000FC) != 0 && ((*(_DWORD *)(v233 + 4) & 0x40) == 0 || v212 >= 0))
      && !v220
      && (*(_DWORD *)(*(_QWORD *)v217 + 4LL) & 0x100) == 0 )
    {
      v64 = 0;
      v225 = 0;
      if ( (*(_DWORD *)(*(_QWORD *)v217 + 4LL) & 0x20000) != 0
        || v224 && ((v65 = *(_QWORD *)(v224 + 184), (*(_DWORD *)(v65 + 4) & 0x20000) != 0) || *(int *)(v65 + 176) < 0) )
      {
        v225 = 1;
      }
      else
      {
        if ( (v212 & 0x4000) == 0 )
        {
          updated = 0;
          v227 = 0;
          v70 = HIBYTE(v212);
          if ( (v212 & 0x40000000) != 0 )
          {
            v49 = v233;
          }
          else
          {
            updated = NtfsPrepareForUpdateDuplicate(v3, v217[0], (unsigned int)&v233, (unsigned int)&v224, 1, 1);
            v227 = updated;
            v49 = v233;
            if ( v233 && (*(_DWORD *)(v233 + 4) & 0x40) != 0 )
            {
              v70 = HIBYTE(v212);
              if ( v212 < 0 )
                updated = PostIrpRoutine;
              v227 = updated;
            }
            else
            {
              v70 = HIBYTE(v212);
            }
          }
          if ( !updated || (v70 & 0x40) != 0 )
          {
            v225 = 1;
            goto LABEL_168;
          }
          v64 = NtfsUpdateDuplicateInfo(v3, v217[0]);
          v225 = v64;
        }
        if ( !v64 )
          BYTE2(v212) |= 4u;
      }
      v49 = v233;
    }
LABEL_168:
    if ( (v212 & 0x2000) == 0 && !v220 )
    {
      v241 = PostIrpRoutine;
      if ( (v212 & 0x40000) != 0 && (v212 & 0x4000) == 0 || (*(_DWORD *)(*(_QWORD *)v217 + 184LL) & 0x100) != 0 )
      {
        v71 = v49 ? *(_DWORD *)(v49 + 180) : PostIrpRoutine;
        v72 = *(_DWORD *)(*(_QWORD *)v217 + 184LL);
        if ( ((v71 | v72) & 0x40000000) != 0 )
        {
          if ( v49 )
            v99 = *(_DWORD *)(v49 + 180);
          else
            LOWORD(v99) = PostIrpRoutine;
          v74 = ((unsigned __int16)v99 | (unsigned __int16)v72) & 0x1F4 | 8;
        }
        else
        {
          if ( v49 )
            v73 = *(_DWORD *)(v49 + 180);
          else
            LOWORD(v73) = PostIrpRoutine;
          v74 = ((unsigned __int16)v73 | (unsigned __int16)v72) & 0x1FC;
        }
        v241 = v74;
        if ( v74 )
          NtfsReportDirNotify(
            v3,
            *((_QWORD *)FsContext + 9),
            v221,
            (_DWORD)FsContext + 16,
            *((unsigned __int16 *)FsContext + 16),
            PostIrpRoutine,
            v74,
            3,
            Fcb,
            PostIrpRoutine);
      }
      *(_DWORD *)(*(_QWORD *)v217 + 184LL) &= ~0x100u;
      v50 = v219;
      if ( *(_WORD *)(v219 + 264) && *(_DWORD *)(v219 + 256) == 128 )
      {
        v51 = *(_DWORD *)(v219 + 512);
        if ( (v51 & 0x1C00) != 0 )
        {
          v241 = PostIrpRoutine;
          if ( (v51 & 0x400) != 0 )
          {
            v241 = 512;
            v52 = 7;
          }
          else
          {
            v48 = PostIrpRoutine;
            if ( (v51 & 0x800) != 0 )
              v48 = 1024;
            v241 = v48;
            if ( (v51 & 0x1000) != 0 )
            {
              v48 |= 0x800u;
              v241 = v48;
            }
            v52 = 8;
          }
          NtfsReportDirNotify(
            v3,
            *((_QWORD *)FsContext + 9),
            v221,
            (_DWORD)FsContext + 16,
            *((unsigned __int16 *)FsContext + 16),
            v219 + 264,
            v48,
            v52,
            Fcb,
            PostIrpRoutine);
          v50 = v219;
        }
        *(_DWORD *)(v219 + 512) = *(_DWORD *)(v50 + 512) & 0xFFFFE1FF;
      }
    }
LABEL_93:
    *(_DWORD *)(*(_QWORD *)v217 + 4LL) &= ~0x10u;
    if ( v218[0] && (v212 & 0x4000) == 0 )
    {
      NtfsReleaseFcbEx(v3, *(_QWORD *)(v224 + 184), 0);
      v218[0] = 0;
    }
    if ( FileObject->PrivateCacheMap || TruncateSize )
      CcUninitializeCacheMap(FileObject, TruncateSize, 0);
    if ( (v212 & 0x10) != 0 )
    {
      NtfsCleanupAttributeContext(v3, v259);
      LOBYTE(v212) = v212 & 0xEF;
    }
    v36 = *(_QWORD *)v217;
    v37 = *(_QWORD *)(*(_QWORD *)v217 + 328LL);
    if ( v37 )
      v28 = *(_QWORD *)(v37 + 24);
    else
      v28 = PostIrpRoutine;
    if ( v28 == *(_QWORD *)(v3 + 400)
      && (*(_DWORD *)(*(_QWORD *)v217 + 20LL) == 1 && (!v37 || !*(_QWORD *)(v37 + 24))
       || (v212 & 0x2000000) != 0 && *(_WORD *)(v37 + 144) == 1) )
    {
      v38 = *(_QWORD *)(*(_QWORD *)v217 + 296LL);
      if ( v38 )
      {
        if ( *(_DWORD *)(v38 + 248) || *(_QWORD *)(v3 + 240) == *(_QWORD *)v217 && *(_DWORD *)(v3 + 256) )
        {
          v28 = PostIrpRoutine;
          while ( 1 )
          {
            v88 = NtfsGetNextChildScb(v36, v28, 1);
            v28 = v88;
            if ( !v88 )
            {
              NtfsPostUsnChangeWithOverrideOption(
                v3,
                v217[0],
                0x80000000,
                0,
                PostIrpRoutine,
                PostIrpRoutine,
                PostIrpRoutine);
              v36 = *(_QWORD *)v217;
              v7 = 8;
              goto LABEL_107;
            }
            if ( (*(_BYTE *)(v88 + 4) & 0x20) != 0 && (*(_DWORD *)(v88 + 200) & 0x40000) != 0 )
              break;
            v36 = *(_QWORD *)v217;
          }
          v36 = *(_QWORD *)v217;
        }
      }
    }
    v7 = 8;
LABEL_107:
    if ( *(_QWORD *)(v3 + 240) && !v220 )
    {
      NtfsWriteUsnJournalChanges(v3);
      NtfsCheckpointCurrentTransaction(v3);
      v36 = *(_QWORD *)v217;
    }
    if ( v220 == -1073741608 || v220 == -1073741432 )
      break;
    if ( !v220 || (v212 & 8) != 0 )
    {
      if ( (*(_DWORD *)(v219 + 200) & 4) != 0 && *(_DWORD *)(v219 + 208) == 1 )
      {
        v12 = 4;
        ClearFlagInterlocked(v219 + 200, 4);
        v36 = *(_QWORD *)v217;
      }
      else
      {
        v12 = 4;
      }
      if ( (v212 & 0x10000) != 0 )
      {
        ClearFlagInterlocked(v219 + 200, 1);
        v36 = *(_QWORD *)v217;
      }
      if ( (v212 & 0x2000000) == 0 )
        goto LABEL_116;
    }
    else
    {
      *(_DWORD *)(v219 + 512) |= 0x20000000u;
      BYTE1(v212) |= 0x80u;
      if ( (*(_DWORD *)(v3 + 16) & 0x100000LL) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 1) != 0 )
      {
        McTemplateU0q_EtwWriteTransfer(&NtfsLog_Context, cleanup_c5039, v220);
      }
      NtfsRaiseStatusInternal(v3, 0, 0, 0, 463797);
    }
    ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(v36 + 328) + 136LL), 1u);
    v192 = *(_QWORD *)v217;
    v193 = *(_QWORD *)(*(_QWORD *)v217 + 328LL);
    v234 = v193;
    if ( *(_WORD *)(v193 + 144) == 1 && (*(_DWORD *)(v193 + 4) & 0x10000) == 0 )
    {
      if ( *(_WORD *)(*(_QWORD *)v217 + 188LL) > 1u )
      {
        ExReleaseResourceLite(*(PERESOURCE *)(v193 + 136));
        v234 = PostIrpRoutine;
        TxfLogFcbInfoRecord(v3, *(_QWORD *)(v3 + 400), v217[0], 0, 1, PostIrpRoutine);
        ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v217 + 328LL) + 136LL), 1u);
        v192 = *(_QWORD *)v217;
        v234 = *(_QWORD *)(*(_QWORD *)v217 + 328LL);
      }
      *(_DWORD *)(*(_QWORD *)(v192 + 328) + 4LL) |= 0x10000u;
      v192 = *(_QWORD *)v217;
    }
    ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(v192 + 328) + 136LL));
    v234 = PostIrpRoutine;
    v36 = *(_QWORD *)v217;
LABEL_116:
    if ( *(_DWORD *)(v36 + 20) == 1 )
    {
      v28 = *(unsigned int *)(v36 + 8);
      if ( (_DWORD)v28 == 5 || *(_DWORD *)(*(_QWORD *)(v36 + 320) + 88LL) == (_DWORD)v28 )
      {
        v53 = *(_QWORD *)(v36 + 320);
        if ( v53 != *(_QWORD *)(*(_QWORD *)(v53 + 16) + 6248LL) )
        {
          if ( (unsigned __int8)TxfMarkRmForShutdown(v53) )
          {
            _InterlockedOr((volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)v217 + 320LL) + 136LL), 4u);
            TxfQueueDelayedRmWorkItem(*(_QWORD *)(*(_QWORD *)v217 + 320LL), v28, v54, v55);
          }
        }
      }
    }
LABEL_117:
    if ( v220 != -1073741608 && v220 != -1073741432 )
    {
      if ( !v220 || (v212 & 8) != 0 )
      {
        v39 = (char *)FsContext + 128;
        if ( !*((_QWORD *)FsContext + 16) )
          goto LABEL_121;
      }
      else
      {
        *(_DWORD *)(v219 + 512) |= 0x20000000u;
        if ( (!v3 || (*(_DWORD *)(v3 + 16) & 0x100000LL) == 0)
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 1) != 0 )
        {
          McTemplateU0q_EtwWriteTransfer(&NtfsLog_Context, cleanup_c5206, v220);
        }
        NtfsRaiseStatusInternal(v3, 0, 0, 0, 463964);
      }
      if ( xmmword_140095790 )
        xmmword_140095790(v39, 0);
LABEL_121:
      if ( *(_DWORD *)(v219 + 208) == 1 && *(_QWORD *)(v219 + 536) && xmmword_140095790 )
      {
        LOBYTE(v28) = 1;
        xmmword_140095790(v219 + 536, v28);
      }
      if ( !*(_QWORD *)(v3 + 400)
        && *(_DWORD *)(v219 + 208) == 1
        && *(_QWORD *)(v219 + 504)
        && (*(_BYTE *)(v219 + 4) & 0x20) != 0
        && (dword_1400956B8 & 0x10000000) != 0 )
      {
        v267 = 0;
        NtfsCoherencyFlushAndPurgeCache(v3, v219, 0, 0, &v267, PostIrpRoutine);
      }
      if ( (*(_DWORD *)(v3 + 8) & 1) != 0 )
        NtfsPersistStorageReserveChanges(v3);
      *(_DWORD *)(v3 + 12) |= 0x8000000u;
      SetFlagInterlocked((char *)FsContext + 4, 0x8000);
      if ( (v212 & 0x4000) != 0 || (v212 & 0x10000000) != 0 )
        *(_DWORD *)(*(_QWORD *)v217 + 4LL) &= ~0x4000u;
      if ( (v212 & 0x100) != 0 && (*(_DWORD *)(v221 + 8204) & 4) != 0 && v232 - 2 <= 1 )
      {
        *(_QWORD *)&v267 = 0;
        v265 = 0;
        v266 = 0;
        *((_QWORD *)&v267 + 1) = PostIrpRoutine;
        *(_QWORD *)&v267 = *(_QWORD *)(*(_QWORD *)(v219 + 184) + 8LL);
        if ( Irp )
        {
          ActivityIdIrp = IoGetActivityIdIrp(Irp, (char *)&v265 + 8);
          v126 = (char *)&v265 + 8;
          if ( ActivityIdIrp < 0 )
            v126 = (char *)PostIrpRoutine;
          *(_QWORD *)&v265 = v126;
        }
        else
        {
          ActivityIdThread = (_QWORD *)IoGetActivityIdThread();
          if ( ActivityIdThread )
            goto LABEL_508;
          *(_QWORD *)&v265 = PostIrpRoutine;
        }
        goto LABEL_509;
      }
      goto LABEL_128;
    }
    if ( NtfsStatusDebugFlags && v220 - 298 > 1 && v220 != -1073741608 && v220 + 2147483643 > 1 )
      NtfsStatusTraceAndDebugInternal(v3, v220, 463950);
    NtfsRaiseStatusInternal(v3, v220, 0, 0, 463950);
  }
  if ( NtfsStatusDebugFlags && v220 - 298 > 1 && v220 != -1073741608 && v220 + 2147483643 > 1 )
    NtfsStatusTraceAndDebugInternal(v3, v220, 463782);
  ActivityIdThread = (_QWORD *)NtfsRaiseStatusInternal(v3, v220, 0, 0, 463782);
LABEL_508:
  *((_QWORD *)&v265 + 1) = *ActivityIdThread;
  v266 = ActivityIdThread[1];
  *(_QWORD *)&v265 = (char *)&v265 + 8;
LABEL_509:
  FsRtlHeatLogIo(v221 + 8200, Irp, &v267, 0, v265);
LABEL_128:
  if ( (v212 & 0x100) != 0 || (v212 & 0x4000) != 0 || (v212 & 0x10000000) != 0 )
  {
    if ( (v212 & 0x10000000) != 0 )
      v20 = Lcb;
    if ( (v212 & 0x100) != 0 || (*(_BYTE *)(*(_QWORD *)(v20 + 192) + 65LL) & 3) != 0 )
      *(_DWORD *)(*(_QWORD *)v217 + 4LL) &= ~0x20u;
  }
  if ( (v212 & 0x100) != 0 || (v212 & 0x4000) != 0 || (v212 & 0x400) != 0 || v212 < 0 || (v212 & 0x10000000) != 0 )
  {
    v87 = Irp;
    Irp->IoStatus.Information = PostIrpRoutine;
    if ( (v212 & 0x10000000) != 0 )
    {
      ExAcquireResourceSharedLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v217 + 328LL) + 136LL), 1u);
      v194 = *(_QWORD *)v217;
      if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)v217 + 328LL) + 4LL) & 0x200000) != 0 )
        v7 = v12;
      v263->IoStatus.Information = v7;
      ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(v194 + 328) + 136LL));
    }
    else if ( (v212 & 0x100) != 0 )
    {
      v87->IoStatus.Information = v12;
    }
    else if ( (v212 & 0x4000) != 0 )
    {
      Irp->IoStatus.Information = 8;
    }
    else if ( v212 < 0 )
    {
      Irp->IoStatus.Information = 36;
    }
    if ( (v212 & 0x400) != 0 )
      Irp->IoStatus.Information |= 0x10uLL;
  }
  v40 = FsContext;
  if ( *((_QWORD *)FsContext + 10) && ((v212 & 0x1000000) != 0 || (v212 & 0x4000000) != 0) )
  {
    --*(_DWORD *)(v252 + 32);
    v40 = FsContext;
  }
  if ( (v212 & 0x40000) != 0 && (v212 & 0x4000) == 0 && (*(_DWORD *)(v3 + 436) & 0x80008) == 0 )
  {
    NtfsUpdateLcbDuplicateInfo(*(_QWORD *)v217, v233);
    *(_DWORD *)(*(_QWORD *)v217 + 184LL) = PostIrpRoutine;
    v40 = FsContext;
  }
  if ( (*((_DWORD *)v40 + 1) & 8) != 0 )
  {
    v41 = 1;
  }
  else
  {
    v41 = (unsigned int)PostIrpRoutine;
    if ( v40[88] == 4 )
      v41 = 2;
  }
  NtfsRemoveShareAccess(FileObject, v41, v219, v252);
  if ( *((int *)FsContext + 1) >= 0 || (*((_DWORD *)FsContext + 2) & 2) != 0 )
    v42 = PostIrpRoutine;
  else
    v42 = 1;
  NtfsDecrementCleanupCounts(v3, v219, v252, FileObject->Flags & 8, v42);
  if ( (*((_DWORD *)FsContext + 2) & 0x80000) != 0 )
  {
    _InterlockedDecrement((volatile signed __int32 *)(v221 + 272));
    ClearFlagInterlocked((char *)FsContext + 8, 0x80000);
  }
  v240 = (_QWORD *)PostIrpRoutine;
  v226 = PostIrpRoutine;
  v44 = *((_QWORD *)FsContext + 10);
  if ( v44 )
  {
    if ( *(_DWORD *)(v44 + 36) )
    {
      ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v217 + 328LL) + 136LL), 1u);
      v234 = *(_QWORD *)(*(_QWORD *)v217 + 328LL);
      --*(_DWORD *)(*(_QWORD *)(*((_QWORD *)FsContext + 10) + 8LL) + 12LL);
      v195 = *(_QWORD *)(*((_QWORD *)FsContext + 10) + 8LL);
      if ( *(_DWORD *)(v195 + 12) || (*(_DWORD *)(v195 + 8) & 1) == 0 )
      {
        ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v217 + 328LL) + 136LL));
        v234 = PostIrpRoutine;
      }
      else
      {
        ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v217 + 328LL) + 136LL));
        v234 = PostIrpRoutine;
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
    if ( (v212 & 0x2000000) != 0 || (v212 & 0x8000000) != 0 )
    {
      ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v217 + 328LL) + 136LL), 1u);
      --*(_WORD *)(*(_QWORD *)(*(_QWORD *)v217 + 328LL) + 144LL);
      --*(_DWORD *)(*(_QWORD *)(v219 + 528) + 36LL);
      ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v217 + 328LL) + 136LL));
    }
    v105 = *((_QWORD *)FsContext + 10);
    v106 = *(_DWORD *)(v105 + 4);
    if ( (v106 & 2) == 0 )
    {
      *(_DWORD *)(v105 + 4) = v106 | 8;
      v107 = *(_QWORD *)(v3 + 400);
      if ( v107 )
        _InterlockedDecrement((volatile signed __int32 *)(v107 + 448));
    }
  }
  if ( (v212 & 0x200) != 0 )
  {
    v108 = (SECTION_OBJECT_POINTERS *)(*(_QWORD *)(v219 + 288) + 16LL);
    if ( v108->DataSectionObject )
    {
      if ( !MmForceSectionClosed(v108, 1u) )
        BYTE1(v212) &= ~2u;
    }
  }
  if ( (*((_DWORD *)FsContext + 1) & 0x8000000) != 0 )
  {
    ClearFlagInterlocked((char *)FsContext + 4, 0x8000000);
    *(_DWORD *)(v219 + 512) &= ~2u;
  }
  if ( (*((_DWORD *)FsContext + 2) & 0x1000) != 0 )
  {
    ClearFlagInterlocked((char *)FsContext + 8, 4096);
    *(_DWORD *)(*(_QWORD *)v217 + 16LL) &= ~2u;
  }
  if ( (*((_DWORD *)FsContext + 2) & 0x400) != 0 )
  {
    ClearFlagInterlocked((char *)FsContext + 8, 1024);
    --*(_DWORD *)(v219 + 220);
  }
  if ( v232 != 4 && *(_QWORD *)(*(_QWORD *)v217 + 120LL) && (*(_DWORD *)(*(_QWORD *)v217 + 4LL) & 1) != 0 )
    NtfsDereferenceQuotaControlBlock(v221, *(_QWORD *)v217 + 120LL, 0);
  v45 = v220;
  if ( v220 )
  {
    if ( (*(_DWORD *)(v3 + 16) & 0x100000LL) == 0
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 1) != 0 )
    {
      McTemplateU0q_EtwWriteTransfer(&NtfsLog_Context, cleanup_c5778, v220);
    }
    *(_DWORD *)(v3 + 24) = PostIrpRoutine;
    NtfsRaiseStatusInternal(v3, 0, 0, 0, 464543);
  }
LABEL_958:
  if ( (_DWORD)v45 != 871 )
  {
    if ( (v212 & 0x200) != 0 && (*(_DWORD *)(*(_QWORD *)v217 + 4LL) & 0x40) != 0 )
    {
      v200 = 0;
      ExAcquirePushLockExclusiveEx(v221 + 656, 0);
      v201 = *(_QWORD *)v217;
      if ( (*(_DWORD *)(*(_QWORD *)v217 + 4LL) & 0x40) != 0 )
      {
        v202 = *(_QWORD *)(*(_QWORD *)v217 + 96LL);
        RtlAvlRemoveNode(v202 + 1344, *(_QWORD *)(*(_QWORD *)v217 + 104LL) + 256LL);
        --*(_DWORD *)(v202 + 1352);
        *(_DWORD *)(v201 + 4) &= ~0x40u;
        v200 = 1;
      }
      ExReleasePushLockEx(v221 + 656, 0);
      if ( v200 )
      {
        LOBYTE(v203) = 1;
        NtfsDereferenceMftView(*(_QWORD *)(*(_QWORD *)v217 + 96LL), *(_QWORD *)v217 + 8LL, v203);
      }
    }
    v197 = *((_QWORD *)FsContext + 10);
    if ( v197 )
      *(_DWORD *)(v197 + 4) &= ~0x40u;
    if ( v234 )
      ExReleaseResourceLite(*(PERESOURCE *)(v234 + 136));
    if ( (v212 & 0x1000) != 0 )
    {
      ExReleasePushLockEx(v221 + 656, 0);
      BYTE1(v212) &= ~0x10u;
    }
    if ( (v212 & 2) != 0 )
      NtfsReleaseFcbEx(v3, *(_QWORD *)(*(_QWORD *)(v221 + 160) + 184LL), 0);
    NtfsReleaseVcb(v3, v221);
    if ( (v212 & 1) != 0 )
    {
      NtfsReleaseCheckpointSynchronization(v3, v221, 18);
      LOBYTE(v212) = v212 & 0xFE;
    }
    if ( (v212 & 0x10) != 0 )
      NtfsCleanupAttributeContext(v3, v259);
    if ( (v212 & 0x20000) != 0 )
    {
      NtfsReleaseFcbEx(v3, *(_QWORD *)(v219 + 184), 0);
      FsRtlNotifyVolumeEvent(FileObject, 5u);
    }
    v45 = v220;
  }
  if ( (__int64 *)v264[3] != &v264[7] )
  {
    ExFreePoolWithTag((PVOID)v264[3], 0);
    v45 = v220;
  }
  if ( (v212 & 0x80u) != 0 )
  {
    _InterlockedDecrement((volatile signed __int32 *)(v245 + 212));
    v45 = v220;
  }
  if ( (v212 & 0x800) != 0 && (int)v45 >= 0 )
  {
    if ( (_DWORD)v45 != 871 )
    {
      if ( v232 != 4
        && (v212 & 0x80000) != 0
        && (v212 & 0x100000) == 0
        && ((v212 & 0x100) != 0
         || (v212 & 0x400) != 0
         || (v212 & 0x4000) != 0
         || (*((_WORD *)FsContext + 52) & 0x912) != 0) )
      {
        if ( NtfsStatusDebugFlags
          && (_DWORD)v45
          && (_DWORD)v45 != 294
          && (unsigned int)(v45 - 298) > 1
          && (unsigned int)(v45 + 2147483643) > 1
          && (_DWORD)v45 != 259 )
        {
          NtfsStatusTraceAndDebugInternal(v3, v45, 464898);
        }
        LOBYTE(v43) = 1;
        NtfsExtendedCompleteRequestInternal(v3, 0, v220, v43, 1);
        LOBYTE(v204) = (*(_DWORD *)(v221 + 24) & 0x100) != 0 ? 3 : 0;
        LOBYTE(v205) = 9;
        v206 = NtfsIoCallSelf(0, FileObject, v205, v204);
        if ( v206 != -1073741533 )
          LODWORD(PostIrpRoutine) = v206;
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
          ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)v217 + 104LL) + 8LL));
          IoRaiseInformationalHardError(PostIrpRoutine, (PUNICODE_STRING)FsContext + 1, Irp->Tail.Overlay.Thread);
          ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)v217 + 104LL) + 8LL));
        }
        LODWORD(v45) = v220;
      }
      goto LABEL_964;
    }
  }
  else
  {
LABEL_964:
    if ( (_DWORD)v45 != 871 )
    {
      NtfsCompleteCleanupRequest(v3, Irp, (unsigned int)v45);
      LODWORD(v45) = v220;
    }
  }
  return (unsigned int)v45;
}

```

## disassembly

```asm
0x1401c3750  mov     r11, rsp
0x1401c3753  mov     [r11+18h], rbx
0x1401c3757  mov     [r11+20h], rsi
0x1401c375b  push    rdi
0x1401c375c  push    r12
0x1401c375e  push    r13
0x1401c3760  push    r14
0x1401c3762  push    r15
0x1401c3764  sub     rsp, 320h
0x1401c376b  mov     rax, cs:__security_cookie
0x1401c3772  xor     rax, rsp
0x1401c3775  mov     [rsp+348h+var_30], rax
0x1401c377d  mov     rdi, rdx
0x1401c3780  mov     rsi, rcx
0x1401c3783  mov     [r11-2A0h], rcx
0x1401c378a  mov     [r11-268h], rdx
0x1401c3791  xor     ebx, ebx
0x1401c3793  mov     [rsp+348h+var_2B8], ebx
0x1401c379a  mov     [rsp+348h+var_22C], ebx
0x1401c37a1  mov     [r11-2B0h], rbx
0x1401c37a8  mov     qword ptr [rsp+348h+var_2D0], rbx
0x1401c37ad  mov     [r11-2C0h], rbx
0x1401c37b4  mov     [r11-2A8h], rbx
0x1401c37bb  mov     [r11-258h], rbx
0x1401c37c2  mov     [r11-298h], rbx
0x1401c37c9  xor     edx, edx; Val
0x1401c37cb  mov     r8d, 58h ; 'X'; Size
0x1401c37d1  lea     rcx, [r11-1A8h]; void *
0x1401c37d8  call    memset
0x1401c37dd  mov     [rsp+348h+var_140], rbx
0x1401c37e5  mov     [rsp+348h+var_2C8], bl
0x1401c37ec  xor     edx, edx; Val
0x1401c37ee  mov     r8d, 0C0h; Size
0x1401c37f4  lea     rcx, [rsp+348h+var_118]; void *
0x1401c37fc  call    memset
0x1401c3801  mov     [rsp+348h+var_2D8], rbx
0x1401c3806  mov     byte ptr [rsp+348h+var_2D8], 0Ch
0x1401c380b  and     byte ptr [rsp+348h+var_2D8+3], 0BFh
0x1401c3810  mov     qword ptr [rdi+38h], 2
0x1401c3818  lea     rax, [rsp+348h+var_F8]
0x1401c3820  mov     [rsp+348h+var_110], rax
0x1401c3828  lea     rax, [rsp+348h+var_E0]
0x1401c3830  mov     [rsp+348h+P], rax
0x1401c3838  mov     dword ptr [rsp+348h+var_118], 180000h
0x1401c3843  mov     [rsp+348h+var_108], 340000h
0x1401c384e  mov     rax, [rdi+0B8h]
0x1401c3855  mov     r15, [rax+30h]
0x1401c3859  mov     [rsp+348h+var_278], r15
0x1401c3861  mov     byte ptr [rsp+348h+var_318], bl
0x1401c3865  lea     rax, [rsp+348h+FsContext]
0x1401c386d  mov     [rsp+348h+PostIrpRoutine], rax
0x1401c3872  lea     rax, [rsp+348h+var_2C0]
0x1401c387a  mov     [rsp+348h+CompletionRoutine], rax
0x1401c387f  lea     r9, [rsp+348h+var_2D0]
0x1401c3884  lea     r8, [rsp+348h+var_2B0]
0x1401c388c  mov     rdx, r15
0x1401c388f  mov     rcx, rsi
0x1401c3892  call    NtfsDecodeFileObject
0x1401c3897  mov     [rsp+348h+var_260], eax
0x1401c389e  dec     eax
0x1401c38a0  test    eax, 0FFFFFFFBh
0x1401c38a5  jz      loc_1401C9A55
0x1401c38ab  mov     [rsp+348h+var_128], rdi
0x1401c38b3  mov     [rsp+348h+var_240], rbx
0x1401c38bb  mov     [rsp+348h+var_250], rbx
0x1401c38c3  mov     r13d, ebx
0x1401c38c6  mov     [rsp+348h+var_1E8], rbx
0x1401c38ce  mov     [rsp+348h+var_220], rbx
0x1401c38d6  mov     [rsp+348h+var_218], rbx
0x1401c38de  mov     [rsp+348h+var_238], rbx
0x1401c38e6  mov     [rsp+348h+TruncateSize], rbx
0x1401c38ee  mov     rdx, [r15+28h]
0x1401c38f2  mov     rcx, [rsp+348h+var_2C0]
0x1401c38fa  mov     rax, [rcx+120h]
0x1401c3901  add     rax, 10h
0x1401c3905  cmp     rdx, rax
0x1401c3908  jnz     loc_1401C96A7
0x1401c390e  mov     rdx, [rsp+348h+FsContext]
0x1401c3916  movzx   ecx, byte ptr [rdx+4]
0x1401c391a  and     cl, 8
0x1401c391d  shl     cl, 2
0x1401c3920  movzx   eax, byte ptr [rsp+348h+var_2D8+1]
0x1401c3925  and     al, 0DFh
0x1401c3927  or      cl, al
0x1401c3929  mov     byte ptr [rsp+348h+var_2D8+1], cl
0x1401c392d  mov     eax, [rdx+64h]
0x1401c3930  mov     [rsi+110h], eax
0x1401c3936  mov     rcx, [rsp+348h+FsContext]
0x1401c393e  cmp     [rcx+50h], rbx
0x1401c3942  jnz     loc_1401C98B7
0x1401c3948  test    cs:dword_1400956B8, 10000000h
0x1401c3952  jnz     loc_1401C98B7
0x1401c3958  mov     rdx, [rsp+348h+var_2B0]
0x1401c3960  cmp     [rsp+348h+var_260], 4
0x1401c3968  jz      loc_1401C98D7
0x1401c396e  test    dword ptr [rsi+0Ch], 100h
0x1401c3975  jnz     loc_1401C9926
0x1401c397b  mov     r8b, 1
0x1401c397e  mov     rcx, rsi
0x1401c3981  call    NtfsAcquireSharedVcb
0x1401c3986  mov     r12d, 200h
0x1401c398c  mov     rax, [rsp+348h+var_2B0]
0x1401c3994  mov     ecx, [rax+4]
0x1401c3997  and     ecx, 8000823h
0x1401c399d  cmp     ecx, 1
0x1401c39a0  jz      loc_1401C968D
0x1401c39a6  mov     rax, [rsp+348h+var_2B0]
0x1401c39ae  test    dword ptr [rax+4], 2000020h
0x1401c39b5  jnz     loc_1401C9936
0x1401c39bb  mov     rax, qword ptr [rsp+348h+var_2D0]
0x1401c39c0  mov     ecx, [rax+4]
0x1401c39c3  bt      ecx, 1Bh
0x1401c39c7  jb      loc_1401C9936
0x1401c39cd  mov     rax, [rsp+348h+var_2B0]
0x1401c39d5  test    dword ptr [rax+4], 4000000h
0x1401c39dc  jnz     loc_1401C9940
0x1401c39e2  mov     rdi, qword ptr [rsp+348h+var_2D0]
0x1401c39e7  mov     rcx, rsi
0x1401c39ea  cmp     qword ptr [rdi+70h], 0
0x1401c39ef  jz      loc_1401C654C
0x1401c39f5  mov     r8b, 1
0x1401c39f8  mov     rdx, rdi
0x1401c39fb  call    NtfsAcquirePagingResourceExclusive
0x1401c3a00  test    al, al
0x1401c3a02  jz      short loc_1401C3A30
0x1401c3a04  mov     [rsp+348h+var_1F8], ebx
0x1401c3a0b  mov     ecx, ebx
0x1401c3a0d  mov     [rsp+348h+var_1F8], ebx
0x1401c3a14  cmp     ecx, 2
0x1401c3a17  jnb     short loc_1401C3A30
0x1401c3a19  mov     eax, ecx
0x1401c3a1b  lea     rdx, [rsi+rax*8]
0x1401c3a1f  mov     rax, [rdx+30h]
0x1401c3a23  test    rax, rax
0x1401c3a26  jnz     loc_1401C53A8
0x1401c3a2c  mov     [rdx+30h], rdi
0x1401c3a30  mov     r9d, 8
0x1401c3a36  mov     rdx, [rsp+348h+var_2C0]
0x1401c3a3e  mov     r8, rdx
0x1401c3a41  mov     rdx, [rdx+0B8h]
0x1401c3a48  mov     rcx, rsi
0x1401c3a4b  call    NtfsAcquireExclusiveFcb
0x1401c3a50  mov     rcx, [rsp+348h+FsContext]
0x1401c3a58  add     rcx, 8
0x1401c3a5c  test    dword ptr [rcx], 100h
0x1401c3a62  jnz     loc_1401C69C0
0x1401c3a68  mov     rax, [rsp+348h+FsContext]
0x1401c3a70  test    dword ptr [rax+8], 8000h
0x1401c3a77  jnz     loc_1401C69DD
0x1401c3a7d  lea     rdi, [r15+50h]
0x1401c3a81  mov     qword ptr [rsp+348h+var_1C0], rdi
0x1401c3a89  test    dword ptr [rdi], 800000h
0x1401c3a8f  jnz     loc_1401C6A06
0x1401c3a95  mov     rdx, [rsp+348h+FsContext]
0x1401c3a9d  mov     r14, [rdx+48h]
0x1401c3aa1  mov     [rsp+348h+var_288], r14
0x1401c3aa9  mov     [rsp+348h+var_1F0], r14
0x1401c3ab1  mov     [rsp+348h+var_258], r14
0x1401c3ab9  test    r14, r14
0x1401c3abc  jz      short loc_1401C3AEA
0x1401c3abe  mov     eax, [r14+4]
0x1401c3ac2  test    al, 2
0x1401c3ac4  jnz     loc_1401C6A16
0x1401c3aca  mov     rax, [r14+18h]
0x1401c3ace  mov     [rsp+348h+var_298], rax
0x1401c3ad6  test    rax, rax
0x1401c3ad9  jz      short loc_1401C3AEA
0x1401c3adb  mov     rax, [rax+0B8h]
0x1401c3ae2  mov     [rsp+348h+var_240], rax
0x1401c3aea  mov     rdx, [rsp+348h+FsContext]
0x1401c3af2  test    dword ptr [rdx+4], 100h
0x1401c3af9  jnz     loc_1401C5719
0x1401c3aff  mov     rax, [rsp+348h+FsContext]
0x1401c3b07  test    [rax+8], r12d
0x1401c3b0b  jnz     loc_1401C6A3C
0x1401c3b11  test    byte ptr [rsp+348h+var_2D8+2], 8
0x1401c3b16  jz      loc_1401C3BEC
0x1401c3b1c  mov     rax, [rsp+348h+FsContext]
0x1401c3b24  mov     rcx, [rax+50h]
0x1401c3b28  test    rcx, rcx
0x1401c3b2b  jnz     loc_1401C6B58
0x1401c3b31  mov     r12d, 2
0x1401c3b37  mov     r13d, 703h
0x1401c3b3d  test    byte ptr [rsp+348h+var_2D8+2], 10h
0x1401c3b42  jnz     loc_1401C3BF2
0x1401c3b48  mov     rcx, qword ptr [rsp+348h+var_2D0]
0x1401c3b4d  call    NtfsIsFileStillValid
0x1401c3b52  test    al, al
0x1401c3b54  jz      loc_1401C3BF2
0x1401c3b5a  mov     rax, [rsp+348h+FsContext]
0x1401c3b62  mov     ecx, [rax+4]
0x1401c3b65  bt      ecx, 12h
0x1401c3b69  jb      loc_1401C5F72
0x1401c3b6f  mov     r12d, 705h
0x1401c3b75  test    byte ptr [rsp+348h+var_2D8+2], 20h
0x1401c3b7a  jnz     loc_1401C42E5
0x1401c3b80  mov     rdi, 30003300490024h
0x1401c3b8a  mov     rcx, qword ptr [rsp+348h+var_2D0]
0x1401c3b8f  cmp     word ptr [rcx+0BCh], 0
0x1401c3b97  jz      loc_1401C5855
0x1401c3b9d  mov     r9, [rsp+348h+var_2C0]
0x1401c3ba5  mov     eax, [r9+0C8h]
0x1401c3bac  test    al, 2
0x1401c3bae  jz      short loc_1401C3C02
0x1401c3bb0  mov     rax, [rcx+148h]
0x1401c3bb7  test    rax, rax
0x1401c3bba  jz      loc_1401C7A39
0x1401c3bc0  mov     eax, [rax+4]
0x1401c3bc3  test    al, 1
0x1401c3bc5  jz      loc_1401C7A39
0x1401c3bcb  movzx   eax, byte ptr [rsp+348h+var_2D8+3]
0x1401c3bd0  test    al, 10h
0x1401c3bd2  jnz     short loc_1401C3C02
0x1401c3bd4  test    al, 2
0x1401c3bd6  jz      short loc_1401C3C02
0x1401c3bd8  mov     rax, [r9+210h]
0x1401c3bdf  cmp     dword ptr [rax+24h], 1
0x1401c3be3  jnz     short loc_1401C3C02
0x1401c3be5  or      byte ptr [rsp+348h+var_2D8+1], 4
0x1401c3bea  jmp     short loc_1401C3C02
0x1401c3bec  mov     r13d, 703h
0x1401c3bf2  mov     rdi, 30003300490024h
0x1401c3bfc  mov     r12d, 705h
0x1401c3c02  mov     r9d, 400h
0x1401c3c08  mov     ecx, [rsp+348h+var_260]
0x1401c3c0f  cmp     ecx, 2
0x1401c3c12  jz      loc_1401C3D28
0x1401c3c18  sub     ecx, 3
0x1401c3c1b  jnz     loc_1401C4515
0x1401c3c21  mov     rdx, [rsp+348h+var_2C0]
0x1401c3c29  mov     rcx, rsi
0x1401c3c2c  call    NtfsSnapshotScb
0x1401c3c31  mov     rdx, [rsp+348h+var_2C0]
0x1401c3c39  mov     eax, [rdx+100h]
0x1401c3c3f  cmp     eax, 80h
0x1401c3c44  jz      loc_1401C7EB6
0x1401c3c4a  cmp     eax, 0A0h
0x1401c3c4f  jz      loc_1401C47E0
0x1401c3c55  mov     r8b, 1
0x1401c3c58  mov     rcx, r15
0x1401c3c5b  call    NtfsUpdateScbFromFileObject
0x1401c3c60  mov     eax, [r15+50h]
0x1401c3c64  bts     eax, 0Eh
0x1401c3c68  mov     [r15+50h], eax
0x1401c3c6c  mov     r8, [rsp+348h+FsContext]; FsContext
0x1401c3c74  test    dword ptr [r8+4], 800000h
0x1401c3c7c  jnz     loc_1401C7EC5
0x1401c3c82  movzx   eax, byte ptr [rsp+348h+var_2D8+2]
0x1401c3c87  test    al, 8
0x1401c3c89  jz      loc_1401C3F61
0x1401c3c8f  test    al, 10h
0x1401c3c91  jnz     loc_1401C3F61
0x1401c3c97  mov     rax, [rsp+348h+var_2C0]
0x1401c3c9f  cmp     [rax], r13w
0x1401c3ca3  jnz     loc_1401C3F61
0x1401c3ca9  mov     rcx, qword ptr [rsp+348h+var_2D0]
0x1401c3cae  call    NtfsIsFileStillValid
0x1401c3cb3  test    al, al
0x1401c3cb5  jz      loc_1401C3F61
0x1401c3cbb  test    byte ptr [rsp+348h+var_2D8+1], 1
0x1401c3cc0  jnz     loc_1401C58FA
0x1401c3cc6  test    r14, r14
0x1401c3cc9  jnz     loc_1401C45C0
0x1401c3ccf  mov     rdx, qword ptr [rsp+348h+var_2D0]
0x1401c3cd4  cmp     dword ptr [rdx+18h], 1
0x1401c3cd8  jz      loc_1401C53BF
0x1401c3cde  test    byte ptr [rsp+348h+var_2D8+1], 1
0x1401c3ce3  jnz     short loc_1401C3CF0
0x1401c3ce5  test    byte ptr [rsp+348h+var_2D8+3], 80h
0x1401c3cea  jz      loc_1401C3F61
0x1401c3cf0  mov     rcx, [rsp+348h+var_298]
0x1401c3cf8  add     rcx, 58h ; 'X'; Oplock
0x1401c3cfc  mov     [rsp+348h+PostIrpRoutine], rbx; PostIrpRoutine
0x1401c3d01  mov     [rsp+348h+CompletionRoutine], rbx; CompletionRoutine
0x1401c3d06  xor     r9d, r9d; Context
0x1401c3d09  mov     r8d, 50h ; 'P'; Flags
0x1401c3d0f  mov     rdx, [rsp+348h+Irp]; Irp
0x1401c3d17  call    cs:__imp_FsRtlCheckOplockEx
0x1401c3d1e  nop     dword ptr [rax+rax+00h]
0x1401c3d23  jmp     loc_1401C3F61
0x1401c3d28  mov     r9, [rsp+348h+var_2C0]
0x1401c3d30  mov     eax, [r9+0C8h]
0x1401c3d37  test    al, 20h
0x1401c3d39  jz      loc_1401C803F
0x1401c3d3f  mov     rax, [rsp+348h+FsContext]
0x1401c3d47  mov     [rsp+348h+PostIrpRoutine], rax
0x1401c3d4c  mov     rax, [rsp+348h+var_2C0]
0x1401c3d54  mov     [rsp+348h+CompletionRoutine], rax
0x1401c3d59  mov     r9, [rsp+348h+var_2B0]
0x1401c3d61  mov     r8, r15
0x1401c3d64  mov     rdx, [rsp+348h+Irp]
0x1401c3d6c  mov     rcx, rsi
0x1401c3d6f  call    NtfsClearSfioReservation
0x1401c3d74  mov     rdx, [rsp+348h+var_2C0]
0x1401c3d7c  mov     rcx, rsi
0x1401c3d7f  call    NtfsSnapshotScb
0x1401c3d84  mov     rdx, [rsp+348h+var_2C0]
0x1401c3d8c  mov     eax, [rdx+100h]
0x1401c3d92  cmp     eax, 80h
0x1401c3d97  jz      loc_1401C49D0
  ... truncated ...
```
