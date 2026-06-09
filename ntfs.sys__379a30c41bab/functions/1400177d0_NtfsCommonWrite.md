# NtfsCommonWrite

- ea: `0x1400177d0`
- end: `0x14001c2cb`
- name: `NtfsCommonWrite`
- size: `19195`
- prototype: `__int64 __fastcall(PVOID Context, PIRP Irp)`
- caller_count: `3`
- callee_count: `59`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140015d10`
- `0x140016850`
- `0x140055830`

## callees

- `0x1400055f0`
- `0x140007ea0`
- `0x1400082b0`
- `0x1400085e0`
- `0x140009710`
- `0x140009af0`
- `0x14000a600`
- `0x14000c1d0`
- `0x14000c290`
- `0x14000c5b0`
- `0x14000cb00`
- `0x14000d1e0`
- `0x14000eaa0`
- `0x140012e70`
- `0x1400177d0`
- `0x14001c910`
- `0x140024338`
- `0x140024914`
- `0x140025210`
- `0x140025830`
- `0x140025d00`
- `0x140028890`
- `0x14002bfb0`
- `0x140034560`
- `0x14003731c`
- `0x140039038`
- `0x14003ac2c`
- `0x14003c210`
- `0x14003f634`
- `0x14004062c`
- `0x1400410a8`
- `0x1400592c0`
- `0x1400593e0`
- `0x140059c60`
- `0x14012d1a0`
- `0x1401403d0`
- `0x1401597b8`
- `0x14015eaf0`
- `0x140162110`
- `0x140163fc8`
- `0x140164c20`
- `0x140175ad0`
- `0x14017db70`
- `0x140181bb0`
- `0x14018a8a0`
- `0x1401abd40`
- `0x1401bb5f4`
- `0x1401be3e8`
- `0x1401c0130`
- `0x1401c0ba0`

## import_xrefs

- `ntoskrnl!FsRtlCheckOplock` at `0x14001a782`
- `ntoskrnl!FsRtlCheckOplock` at `0x14001a782`
- `ntoskrnl!FsRtlCheckLockForWriteAccess` at `0x14001a92b`
- `ntoskrnl!FsRtlCheckLockForWriteAccess` at `0x14001a92b`
- `ntoskrnl!CcSetParallelFlushFile` at `0x14001b246`
- `ntoskrnl!CcSetParallelFlushFile` at `0x14001b246`
- `ntoskrnl!CcUninitializeCacheMap` at `0x140019639`
- `ntoskrnl!CcUninitializeCacheMap` at `0x140019639`
- `ntoskrnl!CcPrepareMdlWrite` at `0x14001b712`
- `ntoskrnl!CcPrepareMdlWrite` at `0x14001b712`
- `ntoskrnl!IoIsOperationSynchronous` at `0x14001a6f3`
- `ntoskrnl!IoIsOperationSynchronous` at `0x14001a6f3`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400191b6`
- `ntoskrnl!IoGetIoPriorityHint` at `0x140019319`
- `ntoskrnl!IoGetIoPriorityHint` at `0x14001a6bf`
- `ntoskrnl!IoGetIoPriorityHint` at `0x14001aa19`
- `ntoskrnl!IoGetIoPriorityHint` at `0x14001ace5`
- `ntoskrnl!IoGetIoPriorityHint` at `0x14001ae34`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400191b6`
- `ntoskrnl!IoGetIoPriorityHint` at `0x140019319`
- `ntoskrnl!IoGetIoPriorityHint` at `0x14001a6bf`
- `ntoskrnl!IoGetIoPriorityHint` at `0x14001aa19`
- `ntoskrnl!IoGetIoPriorityHint` at `0x14001ace5`
- `ntoskrnl!IoGetIoPriorityHint` at `0x14001ae34`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14001b919`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14001bc30`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14005a5ad`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14005a94c`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14001b919`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14001bc30`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14005a5ad`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14005a94c`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x1400183fa`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x1400198ff`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x140019ebd`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x14001b31e`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x1400183fa`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x1400198ff`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x140019ebd`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x14001b31e`
- `ntoskrnl!IoIrpHasFsTrackOffsetExtensionType` at `0x14001785e`
- `ntoskrnl!IoIrpHasFsTrackOffsetExtensionType` at `0x14001785e`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x140017871`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x140017871`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14001a8a6`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14001a8a6`
- `ntoskrnl!FsRtlReleaseEofLock` at `0x140019747`
- `ntoskrnl!FsRtlReleaseEofLock` at `0x14001b221`
- `ntoskrnl!FsRtlReleaseEofLock` at `0x140019747`
- `ntoskrnl!FsRtlReleaseEofLock` at `0x14001b221`
- `ntoskrnl!CcSetReadAheadGranularity` at `0x14001b235`
- `ntoskrnl!CcSetReadAheadGranularity` at `0x14001b235`
- `ntoskrnl!ExAcquireSharedStarveExclusive` at `0x14001b8a8`
- `ntoskrnl!ExAcquireSharedStarveExclusive` at `0x14001bbbf`
- `ntoskrnl!ExAcquireSharedStarveExclusive` at `0x14005a532`
- `ntoskrnl!ExAcquireSharedStarveExclusive` at `0x14005a8d8`
- `ntoskrnl!ExAcquireSharedStarveExclusive` at `0x14001b8a8`
- `ntoskrnl!ExAcquireSharedStarveExclusive` at `0x14001bbbf`
- `ntoskrnl!ExAcquireSharedStarveExclusive` at `0x14005a532`
- `ntoskrnl!ExAcquireSharedStarveExclusive` at `0x14005a8d8`
- `ntoskrnl!CcDeferWrite` at `0x140018734`
- `ntoskrnl!CcDeferWrite` at `0x140018734`
- `ntoskrnl!MmMdlPagesAreZero` at `0x14001a519`
- `ntoskrnl!MmMdlPagesAreZero` at `0x14001a519`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1400199dd`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x140019a35`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x140019b40`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14001a0f0`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14001a19f`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14001a2e1`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14001a3f3`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14001a49a`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14001bb7d`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14005a883`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1400199dd`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x140019a35`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x140019b40`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14001a0f0`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14001a19f`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14001a2e1`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14001a3f3`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14001a49a`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14001bb7d`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14005a883`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x140019938`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x140019aae`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14001a04f`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14001ba3a`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14005a6fa`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x140019938`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x140019aae`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14001a04f`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14001ba3a`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14005a6fa`
- `ntoskrnl!CcCanIWrite` at `0x140018689`
- `ntoskrnl!CcCanIWrite` at `0x140018689`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14001817c`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1400181a4`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140019bbb`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140019be2`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140019c5d`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140019c85`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14001817c`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1400181a4`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140019bbb`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140019be2`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140019c5d`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140019c85`
- `ntoskrnl!ExReleaseResourceLite` at `0x140018032`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400182b6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001833b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001858b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140018761`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400187d9`
- `ntoskrnl!ExReleaseResourceLite` at `0x140018a20`
- `ntoskrnl!ExReleaseResourceLite` at `0x140018c26`
- `ntoskrnl!ExReleaseResourceLite` at `0x140018d1c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140019dc6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001a5ca`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001a67c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140018032`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400182b6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001833b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001858b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140018761`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400187d9`
- `ntoskrnl!ExReleaseResourceLite` at `0x140018a20`
- `ntoskrnl!ExReleaseResourceLite` at `0x140018c26`
- `ntoskrnl!ExReleaseResourceLite` at `0x140018d1c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140019dc6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001a5ca`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001a67c`
- `ntoskrnl!FsRtlAcquireEofLock` at `0x1400196ec`
- `ntoskrnl!FsRtlAcquireEofLock` at `0x14001b1ae`
- `ntoskrnl!FsRtlAcquireEofLock` at `0x1400196ec`
- `ntoskrnl!FsRtlAcquireEofLock` at `0x14001b1ae`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001aff3`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001aff3`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001b025`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001b025`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140017c07`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140017e50`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140019b96`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140019bf2`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140019fa1`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14001a713`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140017c07`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140017e50`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140019b96`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140019bf2`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140019fa1`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14001a713`
- `ntoskrnl!CcCopyWriteEx` at `0x14001b6b5`
- `ntoskrnl!CcCopyWriteEx` at `0x14001b6b5`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14001b9a0`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14005a660`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14001b9a0`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14005a660`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14001a590`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14001a642`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14001a590`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14001a642`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x14001b127`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x14001b127`
- `ntoskrnl!ExRaiseStatus` at `0x14001b135`
- `ntoskrnl!ExRaiseStatus` at `0x14001b135`
- `ntoskrnl!CcFlushCache` at `0x14001b770`
- `ntoskrnl!CcFlushCache` at `0x14001b770`
- `HAL!KeQueryPerformanceCounter` at `0x1400186dd`
- `HAL!KeQueryPerformanceCounter` at `0x1400188d0`
- `HAL!KeQueryPerformanceCounter` at `0x1400186dd`
- `HAL!KeQueryPerformanceCounter` at `0x1400188d0`

## pseudocode

```c
__int64 __fastcall NtfsCommonWrite(LARGE_INTEGER *Context, PIRP Irp, LARGE_INTEGER a3)
{
  LARGE_INTEGER v3; // r14
  PIRP v4; // r15
  LARGE_INTEGER *v5; // rdi
  unsigned int v6; // ebx
  struct _FILE_OBJECT *v7; // r12
  unsigned int v8; // eax
  __int64 v9; // r9
  __int64 v10; // r8
  _DWORD *QuadPart; // rdx
  PFILE_OBJECT v12; // rsi
  _DWORD *v13; // rcx
  __int64 v14; // r8
  BOOL v15; // eax
  __int64 v17; // rdx
  int v18; // eax
  __int64 v19; // r8
  ULONG Flags; // edx
  char v21; // cl
  _DWORD *v22; // rdx
  LARGE_INTEGER v23; // rax
  __int64 v24; // rax
  __int64 v25; // r8
  LONG HighPart; // edx
  union _LARGE_INTEGER *v27; // r8
  union _LARGE_INTEGER v28; // r13
  signed __int64 LowPart; // r12
  __int64 v30; // rax
  LARGE_INTEGER v31; // rcx
  PERESOURCE *v32; // rcx
  __int64 v33; // r9
  char v34; // r12
  PVOID v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // rax
  PVOID v38; // rcx
  int v39; // edx
  __int64 v40; // rax
  PERESOURCE *v41; // rcx
  int v42; // edx
  __int64 v43; // rax
  LARGE_INTEGER *i; // r14
  LARGE_INTEGER v45; // rcx
  PERESOURCE *v46; // rcx
  struct _FILE_OBJECT *v47; // r10
  LONG v48; // eax
  int v49; // r8d
  LONG v50; // ebx
  PERESOURCE *v51; // rcx
  LARGE_INTEGER v52; // rcx
  PERESOURCE *v53; // rcx
  LARGE_INTEGER v54; // rdx
  LARGE_INTEGER PerformanceCounter; // rax
  char v56; // dl
  unsigned int v57; // r10d
  __int64 v58; // r10
  __int64 v59; // rdx
  PERESOURCE *v60; // rcx
  __int64 v61; // rbx
  __int64 v62; // r8
  unsigned __int16 v63; // dx
  __int64 v64; // rax
  int v65; // ebx
  __int64 v66; // r9
  PFILE_OBJECT v67; // r14
  PERESOURCE *v68; // rcx
  LARGE_INTEGER v69; // rdx
  int v70; // r11d
  unsigned __int8 v71; // r12
  __int64 v72; // r8
  size_t v73; // rdx
  LARGE_INTEGER *v74; // rax
  char v75; // cl
  LARGE_INTEGER *v76; // rax
  char v77; // cl
  LARGE_INTEGER *v78; // rax
  char v79; // cl
  LARGE_INTEGER *v80; // rax
  char v81; // cl
  __int64 v82; // r8
  IO_PRIORITY_HINT v83; // eax
  char v84; // al
  char v85; // cl
  bool v86; // r8
  __int64 v87; // rcx
  __int64 v88; // rax
  __int64 v89; // r8
  char v90; // dl
  IO_PRIORITY_HINT v91; // eax
  int *v92; // r9
  PVOID v93; // r8
  char v94; // cl
  char v95; // dl
  int v96; // edx
  __int64 v97; // rax
  __int64 v98; // r8
  __int64 v99; // r12
  LARGE_INTEGER v100; // rdx
  __int64 v101; // rax
  int v102; // ecx
  PVOID v103; // r14
  char *v104; // rcx
  PFILE_OBJECT v105; // rcx
  int v106; // edx
  __int64 v107; // rax
  signed __int64 v108; // rcx
  __int64 v109; // r8
  union _LARGE_INTEGER v110; // r14
  int v111; // eax
  LARGE_INTEGER v112; // rcx
  int v113; // eax
  __int64 v114; // r9
  PVOID v115; // rdx
  PVOID v116; // rdx
  __int64 v117; // rcx
  __int64 v118; // rax
  char v119; // dl
  PVOID v120; // rcx
  int v121; // edx
  __int64 v122; // rax
  __int64 v123; // r9
  int v124; // edx
  __int64 v125; // rax
  int v126; // ecx
  __int64 v127; // r8
  int v128; // eax
  LARGE_INTEGER v129; // rcx
  int v130; // eax
  char v131; // r9
  _QWORD *v132; // r10
  union _LARGE_INTEGER v133; // rdx
  char v134; // al
  __int64 v135; // r8
  __int64 v136; // r8
  __int64 v137; // r8
  DWORD v138; // edx
  ULONG_PTR Information; // rcx
  LARGE_INTEGER v140; // rdx
  __int64 v141; // r14
  size_t v142; // r14
  __int64 *v143; // rcx
  __int64 v144; // rax
  __int64 *v145; // rcx
  LARGE_INTEGER v146; // r8
  union _LARGE_INTEGER v147; // rax
  __int64 v148; // rcx
  _QWORD *v149; // r8
  struct _ERESOURCE *v150; // rcx
  _QWORD *v151; // r8
  struct _ERESOURCE *v152; // rcx
  char v153; // r12
  char v154; // r14
  _DWORD *v155; // rax
  LARGE_INTEGER *v156; // rax
  _BYTE *v157; // rdx
  BOOLEAN IsFastIoPossible; // al
  __int64 v159; // rax
  __int64 v160; // rcx
  char v161; // al
  FILE_LOCK *v162; // rcx
  LONGLONG v163; // r8
  ULONG v164; // r14d
  LARGE_INTEGER *v165; // rdx
  char v166; // cl
  LARGE_INTEGER *v167; // rdx
  __int64 v168; // rax
  union _LARGE_INTEGER v169; // rdx
  LARGE_INTEGER v170; // rax
  union _LARGE_INTEGER *v171; // rdx
  IO_PRIORITY_HINT IoPriorityHint; // eax
  char v173; // cl
  _DWORD *v174; // rcx
  char v175; // al
  int v176; // ecx
  ULONG v177; // esi
  IO_PRIORITY_HINT v178; // eax
  int v179; // eax
  union _LARGE_INTEGER *v180; // r8
  union _LARGE_INTEGER *p_FileOffset; // rcx
  union _LARGE_INTEGER v182; // rax
  __int64 v183; // rcx
  __int64 v184; // rcx
  __int64 v185; // rbx
  __int64 v186; // r8
  int v187; // eax
  NTSTATUS v188; // eax
  PVOID v189; // rsi
  int v190; // r9d
  char *v191; // rcx
  char v192; // dl
  __int64 v193; // rax
  int v194; // r8d
  __int64 v195; // rax
  PIRP v196; // rcx
  PVOID v197; // r9
  _DWORD *v198; // r10
  char *v199; // rsi
  union _LARGE_INTEGER v200; // rdx
  union _LARGE_INTEGER v201; // rcx
  const void *v202; // rax
  int v203; // eax
  int v204; // eax
  int v205; // eax
  __int64 v206; // rax
  char v207; // bl
  __int64 v208; // rdx
  __int64 v209; // rdx
  __int64 Status; // rdx
  signed __int64 v211; // rdx
  _DWORD *v212; // rdx
  __int64 v213; // rcx
  LARGE_INTEGER v214; // rdx
  __int64 v215; // rcx
  LARGE_INTEGER v216; // rdx
  _QWORD *v217; // rdx
  __int64 v218; // rcx
  LONG v219; // edx
  _QWORD *v220; // rcx
  union _LARGE_INTEGER *v221; // r8
  int v222; // r8d
  signed __int64 v223; // rdx
  signed __int64 v224; // r9
  bool v225; // zf
  unsigned __int64 v226; // rax
  _QWORD *SharedCacheMap; // rdx
  _DWORD *v228; // rdx
  __int64 v229; // rcx
  LARGE_INTEGER v230; // rdx
  __int64 v231; // rcx
  LARGE_INTEGER v232; // rdx
  bool v233; // sf
  ULONG BytesToWrite[2]; // [rsp+20h] [rbp-1B8h]
  __int64 BytesToWritea; // [rsp+20h] [rbp-1B8h]
  BOOLEAN Retrying[8]; // [rsp+28h] [rbp-1B0h]
  int v237; // [rsp+40h] [rbp-198h]
  int v238; // [rsp+48h] [rbp-190h]
  __int64 v239; // [rsp+50h] [rbp-188h] BYREF
  PVOID P; // [rsp+58h] [rbp-180h] BYREF
  int v241; // [rsp+60h] [rbp-178h] BYREF
  int v242; // [rsp+64h] [rbp-174h]
  int v243; // [rsp+68h] [rbp-170h]
  DWORD v244; // [rsp+6Ch] [rbp-16Ch]
  union _LARGE_INTEGER FileOffset; // [rsp+70h] [rbp-168h] BYREF
  int v246; // [rsp+78h] [rbp-160h] BYREF
  PFILE_OBJECT FileObject; // [rsp+80h] [rbp-158h]
  __int64 v248; // [rsp+88h] [rbp-150h] BYREF
  int v249[2]; // [rsp+90h] [rbp-148h]
  int v250[2]; // [rsp+98h] [rbp-140h]
  size_t Size; // [rsp+A0h] [rbp-138h]
  __int64 v252; // [rsp+A8h] [rbp-130h] BYREF
  __int64 v253; // [rsp+B0h] [rbp-128h] BYREF
  int v254; // [rsp+B8h] [rbp-120h]
  unsigned int v255; // [rsp+BCh] [rbp-11Ch]
  int v256; // [rsp+C0h] [rbp-118h]
  int v257[2]; // [rsp+C8h] [rbp-110h]
  int v258; // [rsp+D0h] [rbp-108h]
  PVOID Entry; // [rsp+D8h] [rbp-100h]
  int v260[2]; // [rsp+E0h] [rbp-F8h]
  LARGE_INTEGER *v261; // [rsp+E8h] [rbp-F0h]
  int v262; // [rsp+F0h] [rbp-E8h]
  __int64 v263; // [rsp+F8h] [rbp-E0h]
  LARGE_INTEGER v264; // [rsp+100h] [rbp-D8h]
  PIRP v265; // [rsp+108h] [rbp-D0h]
  LARGE_INTEGER v266; // [rsp+110h] [rbp-C8h]
  int v267; // [rsp+118h] [rbp-C0h]
  int v268; // [rsp+11Ch] [rbp-BCh]
  BOOL v269; // [rsp+120h] [rbp-B8h]
  PFILE_OBJECT v270; // [rsp+128h] [rbp-B0h]
  union _LARGE_INTEGER v271; // [rsp+130h] [rbp-A8h]
  union _LARGE_INTEGER *v272; // [rsp+138h] [rbp-A0h]
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+140h] [rbp-98h] BYREF
  int v274; // [rsp+150h] [rbp-88h]
  LONGLONG v275; // [rsp+158h] [rbp-80h]
  __int128 v276; // [rsp+160h] [rbp-78h] BYREF
  __int64 v277; // [rsp+170h] [rbp-68h]
  __int128 v278; // [rsp+178h] [rbp-60h] BYREF
  __int64 v279; // [rsp+188h] [rbp-50h]

  v3 = a3;
  v266 = a3;
  v4 = Irp;
  v5 = Context;
  v261 = Context;
  v265 = Irp;
  v253 = 0;
  v248 = 0;
  P = 0;
  v252 = 0;
  FileOffset.QuadPart = 0;
  v276 = 0;
  v277 = 0;
  LOBYTE(v241) = 0;
  v278 = 0;
  v279 = 0;
  LODWORD(v239) = 0;
  v6 = 0;
  if ( (unsigned __int8)IoIrpHasFsTrackOffsetExtensionType(Irp) )
    IoClearFsTrackOffsetState(v4);
  *(_QWORD *)v257 = v4->Tail.Overlay.CurrentStackLocation;
  v7 = *(struct _FILE_OBJECT **)(*(_QWORD *)v257 + 48LL);
  FileObject = v7;
  v8 = NtfsDecodeFileObject((int)v5, (__int64)v7, &v253, &v248, &P, &v252, 1);
  v10 = v8;
  v255 = v8;
  if ( ((v8 - 2) & 0xFFFFFFFC) != 0 || v8 == 3 )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v5, 3221225488LL, 2491559);
    LOBYTE(v9) = v4 != 0;
    NtfsExtendedCompleteRequestInternal(v5, v4, 3221225488LL, v9, 0);
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3221225488LL, 2491560);
    return 3221225488LL;
  }
  QuadPart = (_DWORD *)v5[18].QuadPart;
  LODWORD(v12) = QuadPart[6];
  v13 = P;
  if ( (int)v12 < 0 && (*((_DWORD *)P + 50) & 0x2000) == 0 && P != *(PVOID *)(v253 + 64) && (QuadPart[109] & 0x80u) == 0 )
  {
    if ( (QuadPart[1] & 0x1000000) != 0 )
    {
      if ( !NtfsStatusDebugFlags
        || (unsigned int)v12 >= 0xFFFFFFED
        || (_DWORD)v12 == -1073741802
        || (unsigned int)((_DWORD)v12 + 2147483643) <= 1
        || (_DWORD)v12 == -1073741807
        || (_DWORD)v12 == -1073741608 )
      {
        goto LABEL_18;
      }
      v14 = 2491582;
LABEL_17:
      NtfsStatusTraceAndDebugInternal(v5, (unsigned int)v12, v14);
LABEL_18:
      v15 = (int)v12 >= 0;
LABEL_19:
      LOBYTE(v9) = v4 != 0;
LABEL_20:
      NtfsExtendedCompleteRequestInternal(v5, v4, (unsigned int)v12, v9, v15);
      return (unsigned int)v12;
    }
    if ( NtfsStatusDebugFlags
      && (unsigned int)v12 < 0xFFFFFFED
      && (_DWORD)v12 != -1073741802
      && (unsigned int)((_DWORD)v12 + 2147483643) > 1
      && (_DWORD)v12 != -1073741807 )
    {
      if ( (_DWORD)v12 == -1073741608 )
        goto LABEL_32;
      NtfsStatusTraceAndDebugInternal(0, (unsigned int)v12, 2491591);
    }
    if ( (_DWORD)v12 != -1073741608 && (_DWORD)v12 != -1073741432 && (_DWORD)v12 != -1073741400 )
    {
LABEL_34:
      if ( NtfsStatusDebugFlags
        && (unsigned int)v12 < 0xFFFFFFED
        && (_DWORD)v12 != -1073741802
        && (unsigned int)((_DWORD)v12 + 2147483643) > 1
        && (_DWORD)v12 != -1073741807 )
      {
        NtfsStatusTraceAndDebugInternal(v5, (unsigned int)v12, 2491600);
      }
LABEL_40:
      LOBYTE(v9) = v4 != 0;
      NtfsExtendedCompleteRequestInternal(v5, v4, (unsigned int)v12, v9, (int)v12 >= 0);
      return (unsigned int)v12;
    }
LABEL_32:
    LODWORD(v12) = -1073741823;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3221225473LL, 2491597);
    goto LABEL_34;
  }
  v17 = v253;
  if ( (*(_DWORD *)(v253 + 4) & 0xA000021) != 1 )
  {
    v4->IoStatus.Information = 0;
    v18 = *(_DWORD *)(v17 + 4);
    if ( (v18 & 0x20) != 0 )
    {
      LODWORD(v12) = -1073741431;
      if ( !NtfsStatusDebugFlags )
      {
LABEL_185:
        LOBYTE(v9) = v4 != 0;
        NtfsExtendedCompleteRequestInternal(v5, v4, (unsigned int)v12, v9, 0);
        return (unsigned int)v12;
      }
      v19 = 2491637;
LABEL_45:
      NtfsStatusTraceAndDebugInternal(v5, (unsigned int)v12, v19);
      goto LABEL_185;
    }
    if ( (v18 & 0x8000000) != 0 || (v18 & 1) == 0 && (_DWORD)v10 != 4 )
    {
      LODWORD(v12) = -1073741202;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_185;
      v19 = 2491649;
      goto LABEL_45;
    }
    if ( (v18 & 0x2000000) != 0 )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(v5, 3221225634LL, 2491659);
      LOBYTE(v9) = v4 != 0;
      NtfsExtendedCompleteRequestInternal(v5, v4, 3221225634LL, v9, 0);
      return 3221225634LL;
    }
    v13 = P;
  }
  if ( (v13[128] & 0x1000000) != 0 )
  {
    v4->IoStatus.Information = 0;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v5, 3221225480LL, 2491675);
    LOBYTE(v9) = v4 != 0;
    NtfsExtendedCompleteRequestInternal(v5, v4, 3221225480LL, v9, 0);
    return 3221225480LL;
  }
  BYTE2(v239) = BYTE2(v239) & 0xFE | BYTE4(v5[1].QuadPart) & 1;
  Flags = v4->Flags;
  LOBYTE(v239) = v239 & 0xFD | (2 * (Flags & 1));
  BYTE1(v239) = BYTE1(v239) & 0xDE | ((Flags & 2) != 0) | (16 * (v7->Flags & 2));
  if ( v5 == (LARGE_INTEGER *)v5[18].QuadPart && LOBYTE(IoGetTopLevelIrp()->Type) )
    v21 = 8;
  else
    v21 = 0;
  LOBYTE(v239) = v21 | v239 & 0xF7;
  v22 = P;
  if ( (v239 & 2) != 0 && (*((_DWORD *)P + 50) & 0x1000000) != 0 )
  {
    v23 = v5[18];
    if ( *(_BYTE *)(v23.QuadPart + 32) != 13
      || (v24 = *(_QWORD *)(v23.QuadPart + 112)) == 0
      || *(_DWORD *)(*(_QWORD *)(v24 + 184) + 24LL) != 590047 )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(v5, 3221227536LL, 2491717);
      LOBYTE(v9) = v4 != 0;
      NtfsExtendedCompleteRequestInternal(v5, v4, 3221227536LL, v9, 0);
      return 3221227536LL;
    }
  }
  if ( v252 && (*(_DWORD *)(v252 + 4) & 0x2000) != 0 && (v239 & 0x100) == 0 )
  {
    if ( NtfsStatusDebugFlags )
    {
      LODWORD(v12) = -1073741811;
      NtfsStatusTraceAndDebugInternal(v5, 3221225485LL, 2491729);
      LOBYTE(v9) = v4 != 0;
      v15 = 0;
      goto LABEL_20;
    }
LABEL_117:
    LODWORD(v12) = -1073741811;
    LOBYTE(v9) = v4 != 0;
    v15 = 0;
    goto LABEL_20;
  }
  if ( (*(_DWORD *)(*((_QWORD *)P + 24) + 24LL) & 0x40000) != 0
    && (*(_DWORD *)(*((_QWORD *)P + 23) + 4LL) & 0x100) == 0
    && (*((_DWORD *)P + 128) & 0x20) == 0 )
  {
    if ( (*((_WORD *)P + 230) & 0xC0FF) != 0 || (v22 = P, (*((_DWORD *)P + 50) & 8) != 0) )
    {
      if ( v22[64] == 128 && !v22[112] )
      {
        if ( NtfsStatusDebugFlags )
        {
          v25 = 2491763;
LABEL_284:
          NtfsStatusTraceAndDebugInternal(v5, 3221226650LL, v25);
          goto LABEL_285;
        }
        goto LABEL_285;
      }
    }
  }
  if ( (v22[50] & 0x20000) != 0 )
  {
    if ( (v239 & 0x100) != 0 )
    {
      if ( (v5[2].LowPart & 0x100000LL) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 8) != 0 )
      {
        McTemplateU0p_EtwWriteTransfer(&NtfsLog_Context, write_c1420, P);
      }
      if ( !NtfsStatusDebugFlags )
        goto LABEL_285;
      v25 = 2491794;
      goto LABEL_284;
    }
    if ( (v239 & 2) != 0 )
      LOBYTE(v239) = v239 & 0xFD;
  }
  if ( *((_DWORD *)P + 136) )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v5, 3221226637LL, 2491821);
    LOBYTE(v9) = v4 != 0;
    NtfsExtendedCompleteRequestInternal(v5, v4, 3221226637LL, v9, 0);
    return 3221226637LL;
  }
  LOBYTE(v10) = 1;
  InternalNtfsUpdateFileTimestampsFromNonpagedFcb(v248, 0, v10);
  if ( (v239 & 0x10000) == 0 && (v239 & 0x100) != 0 )
  {
    if ( (LARGE_INTEGER *)v5[18].QuadPart == v5 && IoGetTopLevelIrp()->AssociatedIrp.MasterIrp == (struct _IRP *)3 )
    {
      if ( *((__int16 *)P + 230) < 0 )
      {
LABEL_109:
        BYTE2(v239) |= 1u;
        v5[1].HighPart |= 1u;
      }
    }
    else if ( (*((_DWORD *)P + 128) & 8) != 0 || *((__int16 *)P + 230) < 0 || NtfsDebugForceSynchronous )
    {
      goto LABEL_109;
    }
  }
  HighPart = v5[1].HighPart;
  v27 = *(union _LARGE_INTEGER **)v257;
  if ( (HighPart & 0x20000) != 0
    && *((_QWORD *)P + 4) < (signed __int64)(*(_QWORD *)(*(_QWORD *)v257 + 24LL)
                                           + *(unsigned int *)(*(_QWORD *)v257 + 8LL)) )
  {
    v5[1].HighPart = HighPart & 0xFFFDFFFF;
    v27[3].QuadPart = -1;
  }
  v28 = v27[3];
  FileOffset = v28;
  LowPart = v27[1].LowPart;
  Size = LowPart;
  if ( 0x7FFFFFFFFFFFFFFFLL - v28.QuadPart < LowPart && v28.QuadPart >= 0 )
  {
    if ( NtfsStatusDebugFlags )
    {
      LODWORD(v12) = -1073741811;
      NtfsStatusTraceAndDebugInternal(v5, 3221225485LL, 2491902);
      LOBYTE(v9) = v4 != 0;
      v15 = 0;
      goto LABEL_20;
    }
    goto LABEL_117;
  }
  if ( !(_DWORD)LowPart )
  {
    v5[62].QuadPart = 17;
    v4->IoStatus.Information = 0;
LABEL_120:
    LOBYTE(v9) = v4 != 0;
    NtfsExtendedCompleteRequestInternal(v5, v4, 0, v9, 1);
    return 0;
  }
  Entry = 0;
  if ( !*((_QWORD *)P + 66) )
    goto LABEL_230;
  LODWORD(v12) = 0;
  if ( (*((_DWORD *)P + 128) & 0x200040) != 0 )
  {
    if ( (v239 & 0x100) == 0 )
    {
      if ( v252 )
      {
        v30 = *(_QWORD *)(v252 + 80);
        if ( v30 )
        {
          if ( (*(_DWORD *)(v30 + 4) & 2) == 0 )
          {
            LODWORD(v12) = TxfSetupTransactionContextFromCcb((_DWORD)v5, (_DWORD)FileObject, 1, 0, 0);
            if ( (int)v12 >= 0 )
              LODWORD(v12) = 0;
          }
        }
      }
    }
    v31 = v5[26];
    if ( v31.QuadPart && (v5[1].HighPart & 0x80000010) != 0 )
      *(_QWORD *)(v31.QuadPart + 80) = 3;
    if ( (v239 & 0x10) != 0 )
    {
      v32 = (PERESOURCE *)P;
      if ( *(_WORD *)P != 1794 )
        v32 = (PERESOURCE *)*((_QWORD *)P + 23);
      ExReleaseResourceLite(v32[14]);
    }
    if ( NtfsStatusDebugFlags
      && (_DWORD)v12
      && (unsigned int)((_DWORD)v12 - 298) > 1
      && (unsigned int)v12 < 0xFFFFFFED
      && (_DWORD)v12 != -1073741802
      && (unsigned int)((_DWORD)v12 + 2147483643) > 1
      && (_DWORD)v12 != -1073741807
      && (_DWORD)v12 != -1073741608 )
    {
      NtfsStatusTraceAndDebugInternal(v5, (unsigned int)v12, 2492028);
      LOBYTE(v33) = v4 != 0;
      NtfsExtendedCompleteRequestInternal(v5, v4, (unsigned int)v12, v33, (int)v12 >= 0);
      return (unsigned int)v12;
    }
    goto LABEL_40;
  }
  if ( *((_DWORD *)P + 64) != 128 )
    goto LABEL_230;
  v34 = 0;
  if ( (v239 & 0x100) == 0 )
  {
    NtfsAcquireExclusiveScbEx(v5, P, 0);
    BYTE1(v239) |= 8u;
    v6 = 2;
    if ( v252 )
    {
      if ( *(_QWORD *)(v252 + 80) )
      {
        LODWORD(v12) = TxfSetupTransactionContextFromCcb((_DWORD)v5, (_DWORD)FileObject, 1, 0, 0);
        if ( (int)v12 >= 0 )
          v6 = 0;
      }
    }
    goto LABEL_200;
  }
  if ( *((_QWORD *)P + 2)
    && !ExIsResourceAcquiredSharedLite(*(PERESOURCE *)(*((_QWORD *)P + 23) + 112LL))
    && !ExIsResourceAcquiredSharedLite((PERESOURCE)(*(_QWORD *)(*((_QWORD *)P + 23) + 104LL) + 64LL)) )
  {
    v35 = P;
    if ( !*((_BYTE *)P + 460) || *((_QWORD *)P + 35) )
    {
      if ( (*((_DWORD *)P + 50) & 0x10) == 0
        || (v36 = *((_QWORD *)P + 23), (v37 = *(_QWORD *)(v36 + 328)) != 0) && *(_QWORD *)(v37 + 24)
        || (*(_DWORD *)(v36 + 4) & 0x20020100) != 0x20000000 )
      {
        LOBYTE(v239) = v239 & 0xEF | (16 * (NtfsAcquirePagingResourceSharedStarveExclusive(v5, P, 0) & 1));
        if ( (v239 & 0x10) == 0 )
        {
LABEL_176:
          if ( (v239 & 0x10) == 0 )
          {
            LOBYTE(v239) = v239 & 0xBF;
            v4->IoStatus.Information = 0;
            LODWORD(v12) = -1073741740;
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(0, 3221225556LL, 2492147);
            if ( (v239 & 0x10) != 0 )
            {
              v41 = (PERESOURCE *)P;
              if ( *(_WORD *)P != 1794 )
                v41 = (PERESOURCE *)*((_QWORD *)P + 23);
              ExReleaseResourceLite(v41[14]);
            }
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(v5, 3221225556LL, 2492150);
            goto LABEL_185;
          }
          v5[2].QuadPart |= 0x400000uLL;
          if ( (v239 & 0x40) != 0 && (!*((_BYTE *)P + 460) || *((_QWORD *)P + 35)) )
          {
            if ( (v42 = *(_DWORD *)(*((_QWORD *)P + 23) + 4LL), (*((_DWORD *)P + 50) & 0x10) == 0)
              || (v43 = *(_QWORD *)(*((_QWORD *)P + 23) + 328LL)) != 0 && *(_QWORD *)(v43 + 24)
              || (v42 & 0x20100) != 0
              || (v42 & 0x20000000) == 0 && ((v42 & 0x10000000) != 0 || !(unsigned __int8)NtfsGetPurgeKernelEAState()) )
            {
              ExConvertExclusiveToSharedLite(*(PERESOURCE *)(*((_QWORD *)P + 23) + 112LL));
              LOBYTE(v239) = v239 & 0x3F | 0x80;
            }
          }
          goto LABEL_197;
        }
        v38 = P;
        if ( !*((_BYTE *)P + 460) || *((_QWORD *)P + 35) )
        {
          v39 = *(_DWORD *)(*((_QWORD *)P + 23) + 4LL);
          if ( (*((_DWORD *)P + 50) & 0x10) == 0 )
            goto LABEL_176;
          v40 = *(_QWORD *)(*((_QWORD *)P + 23) + 328LL);
          if ( v40 )
          {
            if ( *(_QWORD *)(v40 + 24) )
              goto LABEL_176;
          }
          if ( (v39 & 0x20100) != 0
            || (v39 & 0x20000000) == 0 && ((v39 & 0x10000000) != 0 || !(unsigned __int8)NtfsGetPurgeKernelEAState()) )
          {
            goto LABEL_176;
          }
          v38 = P;
        }
        if ( *(_WORD *)v38 != 1794 )
          v38 = (PVOID)*((_QWORD *)v38 + 23);
        ExReleaseResourceLite(*((PERESOURCE *)v38 + 14));
      }
      v35 = P;
    }
    LOBYTE(v239) = v239 & 0xEF | (16 * (NtfsAcquirePagingResourceExclusive(v5, v35, 0, v9) & 1 | 4));
    goto LABEL_176;
  }
LABEL_197:
  if ( FileObject->SectionObjectPointer == (PSECTION_OBJECT_POINTERS)(*((_QWORD *)P + 36) + 16LL) )
    v6 = TxfSetupTransactionContextFromFcb(v5, v248, P, &v5[50]);
  else
    v34 = 1;
LABEL_200:
  if ( v5[3].HighPart )
    NtfsCheckpointCurrentTransaction(v5);
  if ( (v239 & 0x100) == 0
    && !v34
    && (v5[54].HighPart & 0x80008) == 0
    && !(unsigned __int8)TxfIsFileObjectWritable(FileObject, P, v252) )
  {
    v4->IoStatus.Information = 0;
    LODWORD(v12) = -1072103423;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3222863873LL, 2492221);
    v34 = 1;
  }
  if ( (v239 & 0x800) != 0 )
  {
    v5->HighPart &= ~0x2000u;
    for ( i = v5 + 19; (LARGE_INTEGER *)i->QuadPart != i; NtfsReleaseFcbEx(v5, i->QuadPart - 80, 0) )
      ;
    BYTE1(v239) &= ~8u;
    v3 = v266;
  }
  if ( (int)v12 < 0 || v34 )
  {
    v52 = v5[26];
    if ( v52.QuadPart && (v5[1].HighPart & 0x80000010) != 0 )
      *(_QWORD *)(v52.QuadPart + 80) = 3;
    if ( (v239 & 0x10) != 0 )
    {
      v53 = (PERESOURCE *)P;
      if ( *(_WORD *)P != 1794 )
        v53 = (PERESOURCE *)*((_QWORD *)P + 23);
      ExReleaseResourceLite(v53[14]);
    }
    if ( !NtfsStatusDebugFlags
      || !(_DWORD)v12
      || (_DWORD)v12 == 294
      || (unsigned int)((_DWORD)v12 - 298) <= 1
      || (unsigned int)v12 >= 0xFFFFFFED
      || (_DWORD)v12 == -1073741802
      || (unsigned int)((_DWORD)v12 + 2147483643) <= 1
      || (_DWORD)v12 == -1073741807
      || (_DWORD)v12 == 259
      || (_DWORD)v12 == -1073741608 )
    {
      goto LABEL_18;
    }
    v14 = 2492256;
    goto LABEL_17;
  }
  if ( v6 && ((v6 & 4) == 0 || (v6 & 8) != 0) )
  {
    if ( (v6 & 1) != 0 )
    {
      v45 = v5[26];
      if ( v45.QuadPart && (v5[1].HighPart & 0x80000010) != 0 )
        *(_QWORD *)(v45.QuadPart + 80) = 3;
      LOBYTE(v9) = v4 != 0;
      NtfsExtendedCompleteRequestInternal(v5, v4, 0, v9, 1);
      if ( (v239 & 0x10) != 0 )
      {
        v46 = (PERESOURCE *)P;
        if ( *(_WORD *)P != 1794 )
          v46 = (PERESOURCE *)*((_QWORD *)P + 23);
        ExReleaseResourceLite(v46[14]);
      }
      return 0;
    }
  }
  else
  {
    LOBYTE(v27) = 1;
    Entry = (PVOID)TxfCurrentWritableVersion(*((_QWORD *)P + 66), 0, v27);
    BYTE1(v239) |= 0x40u;
  }
  LowPart = Size;
LABEL_230:
  LODWORD(v12) = 1794;
  v47 = FileObject;
  v270 = FileObject;
  if ( *((_BYTE *)P + 460) || (v239 & 0x4000) != 0 )
  {
    BYTE2(v239) |= 1u;
    v5[1].HighPart |= 1u;
  }
  if ( (*((_DWORD *)P + 128) & 0x10000000) != 0 )
  {
    v5[1].HighPart |= 0x10000000u;
    NtfsLockUserBuffer(v5, v4, 0, (unsigned int)LowPart);
    v47 = FileObject;
  }
  if ( (v239 & 0x4000) != 0 && (v5->HighPart & 8) != 0 )
    _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)P + 23) + 328LL) + 24LL)
                                                    + 312LL));
  if ( (v239 & 2) == 0 )
  {
    v48 = v5[1].HighPart;
    if ( (v48 & 8) == 0 && !CcCanIWrite(v47, LowPart, (v48 & 0x41) == 1, (v5->HighPart & 8) != 0) )
    {
      v50 = v5->HighPart;
      LOBYTE(v49) = 1;
      NtfsPrePostIrpInternal((_DWORD)v5, (_DWORD)v4, v49, 0, 1);
      v5->HighPart |= 8u;
      if ( (v50 & 8) == 0 && *(_BYTE *)(v253 + 10496) )
        v5[62] = KeQueryPerformanceCounter(0);
      if ( (v239 & 0x4000) != 0 )
        _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)P + 23) + 328LL) + 24LL)
                                                        + 312LL));
      CcDeferWrite(FileObject, NtfsAddToWorkque, v5, v4, LowPart, (v50 & 8) != 0);
      if ( (v239 & 0x10) != 0 )
      {
        v51 = (PERESOURCE *)P;
        if ( *(_WORD *)P != 1794 )
          v51 = (PERESOURCE *)*((_QWORD *)P + 23);
        ExReleaseResourceLite(v51[14]);
      }
      if ( Entry )
        TxfDereferenceTxfVscb(Entry);
      return 259;
    }
  }
  v272 = *(union _LARGE_INTEGER **)v257;
  *(_QWORD *)v249 = LowPart + v28.QuadPart;
  ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))NtfsInitializeIoContext)(
    v5,
    (LARGE_INTEGER)v3.QuadPart,
    BYTE1(v239) & 1);
  v54 = v5[26];
  v264 = v54;
  if ( *(_BYTE *)(v253 + 10496) )
  {
    PerformanceCounter = v5[62];
    if ( PerformanceCounter.QuadPart <= 23 )
      PerformanceCounter = KeQueryPerformanceCounter(0);
    *(LARGE_INTEGER *)(v5[26].QuadPart + 80) = PerformanceCounter;
    v256 = 0;
    if ( (v239 & 0x100) != 0 || (v239 & 2) != 0 )
      v56 = 0;
    else
      v56 = 4;
    HIBYTE(v256) = v56 | BYTE2(v239) & 1 | ((unsigned int)v5[1].HighPart >> 2) & 2 | (8 * (BYTE1(v239) & 1));
    *(_DWORD *)v5[26].QuadPart |= v256;
    v54 = v264;
  }
  v57 = v255;
  if ( v255 != 4 )
  {
    *(_QWORD *)v250 = FileObject;
    IoStatus.Pointer = FileObject;
    *(_QWORD *)v260 = *(_QWORD *)v249;
    v244 = 0;
    v262 = 0;
    v70 = 0;
    v256 = 0;
    v258 = 0;
    v71 = 0;
    LOBYTE(v243) = 0;
    v266 = v54;
    if ( (v239 & 0x100) != 0 )
    {
      if ( (*((_DWORD *)P + 128) & 1) != 0 )
      {
        FileOffset.QuadPart += *(_QWORD *)(v253 + 1952);
        *(_QWORD *)v249 = FileOffset.QuadPart + *(unsigned int *)(*(_QWORD *)v257 + 8LL);
        *(_QWORD *)v260 = *(_QWORD *)v249;
      }
      v9 = v253;
      v72 = *(_QWORD *)(v253 + 808) + 704LL * (HIDWORD(KeGetPcr()[1].LockArray) % NtfsNumberProcessors);
      if ( (*(_DWORD *)(v248 + 4) & 0x100) != 0 )
      {
        v73 = Size;
        if ( P == *(PVOID *)(v253 + 64) )
        {
          ++*(_QWORD *)(v72 + 432);
          *(_QWORD *)(v72 + 440) += v73;
        }
        else
        {
          ++*(_QWORD *)(v72 + 80);
          *(_QWORD *)(v72 + 88) += v73;
        }
        if ( P == *(PVOID *)(v253 + 48) )
        {
          ++*(_QWORD *)(v72 + 128);
          *(_QWORD *)(v72 + 136) += v73;
          v74 = (LARGE_INTEGER *)v5[18].QuadPart;
          if ( v5 == v74 )
          {
            ++*(_DWORD *)(v72 + 164);
          }
          else if ( v74[25].QuadPart )
          {
            ++*(_DWORD *)(v72 + 160);
          }
          else
          {
            ++*(_DWORD *)(v72 + 168);
            v75 = *(_BYTE *)(v5[18].QuadPart + 32);
            if ( v75 == 4 )
            {
              ++*(_DWORD *)(v72 + 144);
            }
            else if ( v75 )
            {
              if ( v75 == 6 )
              {
                ++*(_DWORD *)(v72 + 152);
              }
              else if ( v75 == 9 )
              {
                ++*(_DWORD *)(v72 + 156);
              }
            }
            else
            {
              ++*(_DWORD *)(v72 + 148);
            }
          }
        }
        else if ( P == *(PVOID *)(v253 + 56) )
        {
          ++*(_QWORD *)(v72 + 176);
          *(_QWORD *)(v72 + 184) += v73;
          v76 = (LARGE_INTEGER *)v5[18].QuadPart;
          if ( v5 == v76 )
          {
            ++*(_DWORD *)(v72 + 212);
          }
          else if ( v76[25].QuadPart )
          {
            ++*(_DWORD *)(v72 + 208);
          }
          else
          {
            ++*(_DWORD *)(v72 + 216);
            v77 = *(_BYTE *)(v5[18].QuadPart + 32);
            if ( v77 )
            {
              switch ( v77 )
              {
                case 4:
                  ++*(_DWORD *)(v72 + 192);
                  break;
                case 6:
                  ++*(_DWORD *)(v72 + 200);
                  break;
                case 9:
                  ++*(_DWORD *)(v72 + 204);
                  break;
              }
            }
            else
            {
              ++*(_DWORD *)(v72 + 196);
            }
          }
        }
        else if ( P == *(PVOID *)(v253 + 32) )
        {
          ++*(_QWORD *)(v72 + 240);
          *(_QWORD *)(v72 + 248) += v73;
        }
        else if ( P == *(PVOID *)(v253 + 72) )
        {
          ++*(_QWORD *)(v72 + 272);
          *(_QWORD *)(v72 + 280) += v73;
          v78 = (LARGE_INTEGER *)v5[18].QuadPart;
          if ( v5 == v78 )
          {
            ++*(_DWORD *)(v72 + 292);
          }
          else if ( v78[25].QuadPart )
          {
            ++*(_DWORD *)(v72 + 288);
          }
          else
          {
            ++*(_DWORD *)(v72 + 296);
            v79 = *(_BYTE *)(v5[18].QuadPart + 32);
            if ( v79 )
            {
              switch ( v79 )
              {
                case 4:
                  ++*(_DWORD *)(v72 + 300);
                  break;
                case 6:
                  ++*(_DWORD *)(v72 + 308);
                  break;
                case 9:
                  ++*(_DWORD *)(v72 + 312);
                  break;
              }
            }
            else
            {
              ++*(_DWORD *)(v72 + 304);
            }
          }
        }
        else if ( P == *(PVOID *)(v253 + 208) )
        {
          ++*(_QWORD *)(v72 + 336);
          *(_QWORD *)(v72 + 344) += v73;
          v80 = (LARGE_INTEGER *)v5[18].QuadPart;
          if ( v5 == v80 )
          {
            ++*(_DWORD *)(v72 + 356);
          }
          else if ( v80[25].QuadPart )
          {
            ++*(_DWORD *)(v72 + 352);
          }
          else
          {
            ++*(_DWORD *)(v72 + 360);
            v81 = *(_BYTE *)(v5[18].QuadPart + 32);
            if ( v81 )
            {
              switch ( v81 )
              {
                case 4:
                  ++*(_DWORD *)(v72 + 364);
                  break;
                case 6:
                  ++*(_DWORD *)(v72 + 372);
                  break;
                case 9:
                  ++*(_DWORD *)(v72 + 376);
                  break;
              }
            }
            else
            {
              ++*(_DWORD *)(v72 + 368);
            }
          }
        }
      }
      else if ( *((_DWORD *)P + 64) == 128 )
      {
        ++*(_QWORD *)(v72 + 32);
        *(_QWORD *)(v72 + 40) += Size;
      }
      else
      {
        ++*(_QWORD *)(v72 + 400);
        *(_QWORD *)(v72 + 408) += Size;
      }
      if ( (v239 & 0x100) != 0 )
        goto LABEL_415;
    }
    v82 = (unsigned __int8)v239;
    if ( (v239 & 2) == 0 )
    {
LABEL_415:
      *((_DWORD *)P + 56) = 0;
      v82 = (unsigned __int8)v239;
    }
    v242 = 0;
    if ( (v239 & 0x100) == 0 )
    {
      if ( v252 )
      {
        v5[34].LowPart = *(_DWORD *)(v252 + 100);
        v82 = (unsigned __int8)v239;
      }
      if ( (v82 & 0x10) != 0 )
      {
LABEL_477:
        if ( *((_DWORD *)P + 129) != 3 || *((_DWORD *)P + 64) != 128 )
        {
          if ( *((_DWORD *)P + 64) != 128 || (unsigned __int8)*((_WORD *)P + 230) < 2u )
          {
            if ( (*((_DWORD *)P + 128) & 0x4000000) != 0 )
            {
              LODWORD(v12) = -1073741431;
              if ( !NtfsStatusDebugFlags )
              {
LABEL_485:
                v242 = (int)v12;
LABEL_486:
                v99 = *(_QWORD *)v249;
LABEL_673:
                v137 = *(_QWORD *)v250;
                v138 = v244;
                goto LABEL_674;
              }
              v98 = 2492936;
LABEL_484:
              NtfsStatusTraceAndDebugInternal(0, (unsigned int)v12, v98);
              goto LABEL_485;
            }
            if ( (v82 & 2) != 0 && (v239 & 0x4000) == 0 )
            {
              v100 = v5[18];
              if ( v5 != (LARGE_INTEGER *)v100.QuadPart )
              {
                if ( _bittest16((const signed __int16 *)P + 230, 0xEu) )
                {
                  if ( *(_BYTE *)(v100.QuadPart + 32) == 13 )
                  {
                    v101 = *(_QWORD *)(v100.QuadPart + 112);
                    if ( v101 )
                    {
                      if ( *(_DWORD *)(*(_QWORD *)(v101 + 184) + 24LL) == 590047 )
                        v70 = 2;
                      v256 = v70;
                      v274 = v70;
                    }
                  }
                }
              }
              if ( v57 != 5 && FileObject->SectionObjectPointer->DataSectionObject && !*((_BYTE *)P + 460) )
              {
                if ( *((_DWORD *)P + 54) )
                {
                  LODWORD(v12) = -1073740747;
                  if ( !NtfsStatusDebugFlags )
                    goto LABEL_485;
                  v98 = 2493011;
                  goto LABEL_484;
                }
                LODWORD(v12) = NtfsCacheCoherencyFlush(
                                 (_DWORD)v5,
                                 (_DWORD)v4,
                                 (_DWORD)P,
                                 FileOffset.LowPart,
                                 Size,
                                 1,
                                 *((_DWORD *)P + 55) == 0);
                v242 = (int)v12;
                if ( (int)v12 < 0 )
                  goto LABEL_486;
                if ( FileObject->PrivateCacheMap )
                  CcUninitializeCacheMap(FileObject, 0, 0);
                v82 = (unsigned __int8)v239;
              }
            }
            if ( !v252 || (*(_DWORD *)(v252 + 4) & 0x8000) == 0 )
            {
              v102 = *((_DWORD *)P + 128);
              if ( (v102 & 0x40) == 0 )
              {
                if ( (v102 & 0x10000) != 0 )
                  LODWORD(v12) = -1073741202;
                else
                  LODWORD(v12) = (v102 & 0x1000000) != 0 ? 0xC0000008 : 0;
                v242 = (int)v12;
                if ( (int)v12 >= 0 )
                {
                  if ( (v5[1].HighPart & 0x400000) == 0
                    && (*((_BYTE *)P + 460) || (v239 & 0x4000) != 0 && (v82 & 2) != 0) )
                  {
                    v103 = P;
                    if ( !*((_QWORD *)P + 35) )
                    {
                      FsRtlAcquireEofLock((char *)P + 120, (char *)P + 160, v82);
                      v5[8].QuadPart = (LONGLONG)v103;
                      NtfsCreateInternalAttributeStream(
                        (_DWORD)v5,
                        (_DWORD)P,
                        0,
                        0,
                        (__int64)&asc_140062170[8 * (((unsigned __int64)BYTE1(v239) >> 6) & 1)],
                        0);
                      v104 = (char *)P;
                      v5[8].QuadPart = 0;
                      FsRtlReleaseEofLock(v104 + 120, v104 + 160);
                      v82 = (unsigned __int8)v239;
                    }
                  }
                  if ( (*((_BYTE *)P + 460) || (v239 & 0x4000) != 0) && (v82 & 2) != 0 )
                  {
                    LOBYTE(v239) = v82 & 0xFD;
                    *(_BYTE *)(v5[26].QuadPart + 3) |= 4u;
                    if ( (v239 & 0x4000) != 0 )
                    {
                      v105 = FileObject;
                      FileObject->Flags &= ~0x10u;
                      v5[1].HighPart &= ~8u;
                      *(_BYTE *)(v5[26].QuadPart + 3) &= ~2u;
                    }
                    else
                    {
                      v105 = (PFILE_OBJECT)*((_QWORD *)P + 35);
                      FileObject = v105;
                      v270 = v105;
                      v105->Flags |= 0x10u;
                      v5[1].HighPart |= 8u;
                      *(_BYTE *)(v5[26].QuadPart + 3) |= 2u;
                    }
                    v82 = (unsigned __int8)v239;
                  }
                  else
                  {
                    v105 = FileObject;
                  }
                  if ( (v82 & 0x40) != 0
                    && (v5[1].HighPart & 0x100) == 0
                    && (!*((_BYTE *)P + 460) || *((_QWORD *)P + 35))
                    && (v255 == 5
                     || (v82 & 2) == 0
                     || (v239 & 0x4000) != 0
                     || !v105->SectionObjectPointer->DataSectionObject) )
                  {
                    if ( (LOBYTE(v82) = (v82 & 2) != 0, (_BYTE)v82) && (v239 & 0x4000) == 0
                      || v105->SectionObjectPointer->SharedCacheMap )
                    {
                      if ( !(_BYTE)v82 || (v239 & 0x4000) == 0 || *((_QWORD *)P + 35) )
                      {
                        if ( (v106 = *(_DWORD *)(*((_QWORD *)P + 23) + 4LL), (*((_DWORD *)P + 50) & 0x10) == 0)
                          || (v107 = *(_QWORD *)(*((_QWORD *)P + 23) + 328LL)) != 0 && *(_QWORD *)(v107 + 24)
                          || (v106 & 0x20100) != 0
                          || (v106 & 0x20000000) == 0
                          && ((v106 & 0x10000000) != 0 || !(unsigned __int8)NtfsGetPurgeKernelEAState()) )
                        {
                          ExConvertExclusiveToSharedLite(*(PERESOURCE *)(*((_QWORD *)P + 23) + 112LL));
                          LOBYTE(v239) = v239 & 0x3F | 0x80;
                        }
                      }
                    }
                  }
                  if ( FileOffset.QuadPart >= 0 )
                  {
                    v108 = *(_QWORD *)v249;
                  }
                  else
                  {
                    FsRtlAcquireHeaderMutex((char *)P + 120, (char *)P + 160, v82);
                    v71 = 1;
                    do
                    {
                      LODWORD(v12) = NtfsGetIoAtEof((_DWORD)v5, (_DWORD)P, *((_QWORD *)P + 4), Size, 1, (__int64)&v241);
                      v242 = (int)v12;
                    }
                    while ( !(_BYTE)v241 );
                    v5[1].HighPart |= 0x20000u;
                    *(_QWORD *)(*(_QWORD *)v257 + 24LL) = *((_QWORD *)P + 4);
                    FileOffset = *(union _LARGE_INTEGER *)((char *)P + 32);
                    v108 = FileOffset.QuadPart + Size;
                    *(_QWORD *)v249 = FileOffset.QuadPart + Size;
                    *(_QWORD *)v260 = FileOffset.QuadPart + Size;
                    if ( (__int64)(FileOffset.QuadPart + Size) < FileOffset.QuadPart )
                    {
                      FsRtlReleaseHeaderMutex((char *)P + 120, (char *)P + 160);
                      LODWORD(v12) = -1073741811;
                      if ( !NtfsStatusDebugFlags )
                        goto LABEL_485;
                      v98 = 2493253;
                      goto LABEL_484;
                    }
                  }
                  if ( v108 > *(_QWORD *)(*((_QWORD *)P + 24) + 7776LL) )
                  {
                    if ( v71 )
                      FsRtlReleaseHeaderMutex((char *)P + 120, (char *)P + 160);
                    LODWORD(v12) = -1073741811;
                    if ( !NtfsStatusDebugFlags )
                      goto LABEL_485;
                    v98 = 2493269;
                    goto LABEL_484;
                  }
                  while ( 1 )
                  {
                    NtfsGetScbFileSizes(P, &v278, v71);
                    v110 = *(union _LARGE_INTEGER *)((char *)&v278 + 8);
                    if ( (v5[1].HighPart & 0x20000) != 0 || *(__int64 *)v249 <= v279 )
                      break;
                    if ( v71 )
                    {
                      LODWORD(v12) = NtfsGetIoAtEof((_DWORD)v5, (_DWORD)P, FileOffset.LowPart, Size, 1, (__int64)&v241);
                      v242 = (int)v12;
                      break;
                    }
                    FsRtlAcquireHeaderMutex((char *)P + 120, (char *)P + 160, v109);
                    v71 = 1;
                  }
                  v111 = v258;
                  if ( *(__int64 *)v249 > v110.QuadPart )
                    v111 = 2;
                  v258 = v111;
                  v267 = v111;
                  if ( FileOffset.QuadPart < v110.QuadPart )
                  {
                    v258 = v111 | 1;
                    v267 = v111 | 1;
                  }
                  if ( v71 )
                    FsRtlReleaseHeaderMutex((char *)P + 120, (char *)P + 160);
                  v112 = v5[18];
                  v113 = *(_DWORD *)(v112.QuadPart + 4);
                  if ( (v113 & 2) == 0 )
                  {
                    *(_DWORD *)(v112.QuadPart + 4) = v113 | 2;
                    BYTE1(v239) |= 0x10u;
                  }
LABEL_721:
                  v149 = P;
                  if ( (*((_DWORD *)P + 50) & 0x20) == 0 && *((_DWORD *)P + 64) != 160 )
                  {
                    if ( *(_WORD *)P != 1794 )
                      v149 = (_QWORD *)*((_QWORD *)P + 23);
                    ExAcquireResourceSharedLite((PERESOURCE)(v149[13] + 64LL), 1u);
                    BYTE1(v239) |= 8u;
                    NtfsUpdateScbFromAttribute(v5, P, 0);
                    if ( *(_WORD *)P == 1794 )
                      v150 = (struct _ERESOURCE *)(*((_QWORD *)P + 13) + 64LL);
                    else
                      v150 = (struct _ERESOURCE *)*((_QWORD *)P + 1);
                    ExReleaseResourceLite(v150);
                    BYTE1(v239) &= ~8u;
                  }
                  if ( (_BYTE)v241 )
                  {
                    if ( (v239 & 0x10000) == 0 && (v239 & 2) != 0 || *((_BYTE *)P + 460) )
                    {
                      BYTE2(v239) |= 1u;
                      v5[1].HighPart |= 1u;
                      *(_BYTE *)(v5[26].QuadPart + 3) |= 1u;
                    }
                    v151 = P;
                    if ( (*((_DWORD *)P + 50) & 0x20) == 0 )
                    {
                      if ( *(_WORD *)P != 1794 )
                        v151 = (_QWORD *)*((_QWORD *)P + 23);
                      ExAcquireResourceSharedLite((PERESOURCE)(v151[13] + 64LL), 1u);
                      BYTE1(v239) |= 8u;
                      NtfsUpdateScbFromAttribute(v5, P, 0);
                      if ( *(_WORD *)P == 1794 )
                        v152 = (struct _ERESOURCE *)(*((_QWORD *)P + 13) + 64LL);
                      else
                        v152 = (struct _ERESOURCE *)*((_QWORD *)P + 1);
                      ExReleaseResourceLite(v152);
                      BYTE1(v239) &= ~8u;
                    }
                  }
                  if ( (v239 & 0x100) == 0 && v255 == 2 )
                  {
                    v153 = 0;
                    LOWORD(v254) = 0;
                    v154 = 0;
                    if ( IoGetIoPriorityHint(v4) >= IoPriorityNormal )
                      v155 = (_DWORD *)(v253 + 5256);
                    else
                      v155 = (_DWORD *)(v253 + 5304);
                    if ( (*v155 >= (unsigned int)dword_140095AC0 || IoIsOperationSynchronous(v4))
                      && (v5[1].HighPart & 0x40) == 0
                      && v5 == (LARGE_INTEGER *)v5[18].QuadPart
                      && LOBYTE(IoGetTopLevelIrp()->Type) )
                    {
                      *(_DWORD *)v5[26].QuadPart |= 8u;
                      v153 = 1;
                      LOBYTE(v254) = 1;
                    }
                    if ( (v239 & 0x1000) != 0 )
                    {
                      v156 = (LARGE_INTEGER *)v5[18].QuadPart;
                      if ( v156 != v5 )
                      {
                        v156->HighPart &= ~2u;
                        BYTE1(v239) &= ~0x10u;
                        v154 = 1;
                        BYTE1(v254) = 1;
                      }
                    }
                    LODWORD(v12) = FsRtlCheckOplock(
                                     (POPLOCK)P + 11,
                                     v4,
                                     v5,
                                     NtfsOplockComplete,
                                     NtfsWriteOplockPrePostIrp);
                    v242 = (int)v12;
                    if ( (_DWORD)v12 )
                    {
                      if ( NtfsStatusDebugFlags
                        && ((((_DWORD)v12 - 294) & 0xFFFFFFFA) != 0 || (_DWORD)v12 == 295)
                        && (unsigned int)v12 < 0xFFFFFFED
                        && (_DWORD)v12 != -1073741802
                        && (unsigned int)((_DWORD)v12 + 2147483643) > 1
                        && (_DWORD)v12 != -1073741807 )
                      {
                        if ( (_DWORD)v12 == 259 )
                          goto LABEL_767;
                        if ( (_DWORD)v12 != -1073741608 )
                          NtfsStatusTraceAndDebugInternal(0, (unsigned int)v12, 2494140);
                      }
                      if ( (_DWORD)v12 != 259 )
                      {
LABEL_771:
                        BYTE1(v239) &= ~8u;
                        v4 = 0;
                        v265 = 0;
                        v5 = 0;
                        v261 = 0;
                        LOBYTE(v241) = 0;
                        v99 = *(_QWORD *)v249;
                        goto LABEL_673;
                      }
LABEL_767:
                      if ( v153 )
                      {
                        LODWORD(v12) = 871;
                        if ( NtfsStatusDebugFlags )
                          NtfsStatusTraceAndDebugInternal(0, 871, 2494144);
                        v242 = 871;
                      }
                      goto LABEL_771;
                    }
                    if ( v154 )
                    {
                      *(_DWORD *)(v5[18].QuadPart + 4) |= 2u;
                      BYTE1(v239) |= 0x10u;
                    }
                    if ( !*((_BYTE *)P + 5) )
                    {
                      v157 = P;
                      if ( (*(_DWORD *)(*((_QWORD *)P + 24) + 4LL) & 0x4000005) == 1
                        && *(_WORD *)P == 1797
                        && (IsFastIoPossible = FsRtlOplockIsFastIoPossible((POPLOCK)P + 11), v157 = P, IsFastIoPossible) )
                      {
                        if ( *((_DWORD *)P + 113)
                          || (v159 = *((_QWORD *)P + 73)) != 0 && *(_BYTE *)(v159 + 16)
                          || (v160 = *((_QWORD *)P + 24), (*(_DWORD *)(v160 + 4) & 0x2000000) != 0)
                          || (*((_DWORD *)P + 128) & 0x4000000) != 0
                          || *((_QWORD *)P + 66)
                          || *(_QWORD *)(v160 + 40) )
                        {
                          v161 = 2;
                        }
                        else
                        {
                          v161 = 1;
                        }
                      }
                      else
                      {
                        v161 = 0;
                      }
                      v157[5] = v161;
                    }
                    v162 = (FILE_LOCK *)*((_QWORD *)P + 73);
                    if ( v162 && !FsRtlCheckLockForWriteAccess(v162, v4) )
                    {
                      LODWORD(v12) = -1073741740;
                      if ( !NtfsStatusDebugFlags )
                        goto LABEL_485;
                      v98 = 2494186;
                      goto LABEL_484;
                    }
                  }
                  v163 = (unsigned int)v258;
                  v164 = Size;
                  if ( v258 )
                  {
                    NtfsPostUsnChangeWithOverrideOption(
                      (_DWORD)v5,
                      (_DWORD)P,
                      v258,
                      0,
                      FileOffset.QuadPart,
                      (unsigned int)Size,
                      0);
                    v5->HighPart &= ~0x2000u;
                    while ( 1 )
                    {
                      v165 = (LARGE_INTEGER *)v5[19].QuadPart;
                      if ( v165 == &v5[19] )
                        break;
                      NtfsReleaseFcbEx(v5, &v165[-10], 0);
                    }
                  }
                  v99 = *(_QWORD *)v249;
                  if ( (_BYTE)v241 && (v5[1].HighPart & 0x800) == 0 )
                  {
                    if ( *(__int64 *)v249 > *((_QWORD *)P + 3)
                      || (*((_DWORD *)P + 50) & 8) != 0 && *(__int64 *)v249 > *((_QWORD *)P + 4) )
                    {
                      if ( (v239 & 0x10000) != 0
                        || (v239 & 0x2000) == 0 && (v239 & 2) != 0 && IoGetIoPriorityHint(v4) < IoPriorityNormal )
                      {
                        v166 = 2;
                      }
                      else
                      {
                        v166 = 0;
                      }
                      BYTE2(v239) = v166 | BYTE2(v239) & 0xFD;
                      NtfsAcquireExclusiveScbEx(v5, P, 2 * (BYTE2(v239) & 2u));
                      BYTE1(v239) |= 8u;
                    }
                    v163 = (LONGLONG)P;
                    if ( v99 > *((_QWORD *)P + 3)
                      || (v239 & 0x100) == 0 && (*((_DWORD *)P + 50) & 8) != 0 && v99 > *((_QWORD *)P + 4) )
                    {
                      if ( (*((_DWORD *)P + 50) & 8) == 0
                        || (*(_DWORD *)Retrying = v164,
                            (unsigned __int8)NtfsAddAllocationForResidentWrite(
                                               (int)v5,
                                               (int)v4,
                                               (int)FileObject,
                                               (int)P,
                                               FileOffset.QuadPart,
                                               *(SIZE_T *)Retrying,
                                               (v239 & 2) != 0,
                                               (v239 & 0x4000) != 0,
                                               v237,
                                               v238,
                                               v239,
                                               P,
                                               v241,
                                               v243,
                                               FileOffset.LowPart,
                                               v246,
                                               (int)FileObject,
                                               v248,
                                               v249[0],
                                               v250[0],
                                               Size,
                                               v252,
                                               v253,
                                               v254,
                                               v256,
                                               v257[0],
                                               v258,
                                               (int)Entry,
                                               v260[0],
                                               (int)v261,
                                               v262,
                                               v263)) )
                      {
                        if ( v99 > *((_QWORD *)P + 3) )
                          NtfsAddAllocationForNonResidentWrite(
                            (_DWORD)v5,
                            (_DWORD)FileObject,
                            (_DWORD)P,
                            v252,
                            FileOffset.QuadPart,
                            v99);
                      }
                      NtfsCheckpointCurrentTransaction(v5);
                      v5->HighPart &= ~0x2000u;
                      while ( 1 )
                      {
                        v167 = (LARGE_INTEGER *)v5[19].QuadPart;
                        if ( v167 == &v5[19] )
                          break;
                        NtfsReleaseFcbEx(v5, &v167[-10], 0);
                      }
                      NtfsReleaseSharedResources(v5);
                      BYTE1(v239) &= ~8u;
                    }
                  }
                  if ( (v239 & 0x4000) == 0 || (v239 & 2) == 0 )
                  {
                    v12 = FileObject;
                    goto LABEL_841;
                  }
                  v163 = (LONGLONG)P;
                  if ( (*((_BYTE *)P + 4) & 0x20) != 0 )
                  {
                    v168 = *((_QWORD *)P + 66);
                    if ( v168 )
                    {
                      if ( (*(_DWORD *)(v168 + 24) & 0x800) != 0 && (v6 & 4) == 0 )
                      {
                        BYTE2(v254) = 0;
                        v169.QuadPart = 0;
                        v271.QuadPart = 0;
                        v163 = v164;
                        v275 = v164;
                        if ( (v239 & 0x400) != 0 )
                        {
                          v170 = v5[18];
                          if ( *(_BYTE *)(v170.QuadPart + 32) == 4 )
                          {
                            v169.QuadPart = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v170.QuadPart + 112) + 184LL) + 24LL)
                                          + *(unsigned int *)(*(_QWORD *)(*(_QWORD *)(v170.QuadPart + 112) + 184LL) + 8LL);
                            v271 = v169;
                          }
                        }
                        if ( v169.QuadPart < *((_QWORD *)P + 4) )
                          v169 = *(union _LARGE_INTEGER *)((char *)P + 32);
                        v271 = v169;
                        if ( v164 + FileOffset.QuadPart > v169.QuadPart )
                        {
                          if ( FileOffset.QuadPart >= v169.QuadPart )
                          {
                            BYTE2(v254) = 1;
                            goto LABEL_837;
                          }
                          v163 = v169.QuadPart - FileOffset.QuadPart;
                          v275 = v169.QuadPart - FileOffset.QuadPart;
                        }
                        LODWORD(v12) = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))TxfLogPriorToWrite)(
                                         v5,
                                         FileObject,
                                         Entry,
                                         (union _LARGE_INTEGER)FileOffset.QuadPart,
                                         v163,
                                         v4,
                                         1,
                                         0);
                        v242 = (int)v12;
                      }
                    }
                  }
LABEL_837:
                  if ( (int)v12 < 0 )
                    goto LABEL_673;
                  v12 = FileObject;
                  if ( (v6 & 8) == 0 )
                    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))TxfFlushUndoPriorToDiskWrite)(
                      v5,
                      FileObject,
                      (union _LARGE_INTEGER)FileOffset.QuadPart,
                      v164);
LABEL_841:
                  v171 = (union _LARGE_INTEGER *)P;
                  if ( (*((_DWORD *)P + 50) & 8) != 0 || (*((_DWORD *)P + 128) & 0x4000) != 0 )
                  {
                    if ( (v239 & 2) == 0 )
                      goto LABEL_916;
                    if ( (v239 & 0x10000) != 0
                      || (v239 & 0x2000) == 0
                      && (IoPriorityHint = IoGetIoPriorityHint(v4),
                          v171 = (union _LARGE_INTEGER *)P,
                          IoPriorityHint < IoPriorityNormal) )
                    {
                      v173 = 2;
                    }
                    else
                    {
                      v173 = 0;
                    }
                    BYTE2(v239) = v173 | BYTE2(v239) & 0xFD;
                    NtfsAcquireExclusiveScbEx(v5, v171, 2 * (BYTE2(v239) & 2u));
                    BYTE1(v239) |= 8u;
                    v174 = P;
                    if ( (*((_DWORD *)P + 50) & 0x20) == 0 )
                    {
                      NtfsUpdateScbFromAttribute(v5, P, 0);
                      v174 = P;
                    }
                    if ( (v174[50] & 8) != 0 )
                    {
                      v175 = (v5[1].HighPart & 8) != 0 || (v239 & 0x4000) != 0;
                      BytesToWrite[0] = v164;
                      LODWORD(v12) = NtfsResidentWrite(
                                       (int)v5,
                                       (int)v4,
                                       (int)P,
                                       FileOffset.LowPart,
                                       *(SIZE_T *)BytesToWrite,
                                       (__int64)&v239,
                                       v241,
                                       v175);
                      v242 = (int)v12;
                      goto LABEL_673;
                    }
                    NtfsReleaseFcbEx(v5, *((_QWORD *)P + 23), 0);
                    BYTE1(v239) &= ~8u;
                    v171 = (union _LARGE_INTEGER *)P;
                  }
                  if ( (v239 & 2) != 0 )
                  {
                    v176 = *(_DWORD *)(v253 + 364);
                    v177 = -v176 & (v164 + v176 - 1);
                    if ( (v5[1].HighPart & 0x800) == 0
                      && (((v176 - 1) & FileOffset.LowPart) != 0 || v177 != v164 && v99 < v171[5].QuadPart) )
                    {
                      LODWORD(v12) = -1073741822;
                      if ( !NtfsStatusDebugFlags )
                        goto LABEL_672;
                      v136 = 2494624;
                      goto LABEL_671;
                    }
                    if ( (*(_DWORD *)(v253 + 8204) & 2) != 0 )
                    {
                      v178 = IoGetIoPriorityHint(v4);
                      v171 = (union _LARGE_INTEGER *)P;
                      if ( v178 > IoPriorityLow )
                      {
                        if ( (v179 = *((_DWORD *)P + 64), v179 == 128) && !*((_WORD *)P + 132) || v179 == 160 )
                        {
                          if ( ((*(_DWORD *)(v248 + 8) - 2) & 0xFFFFFFFB) != 0 )
                          {
                            NtfsHeatLogIo(v4, v248);
                            v171 = (union _LARGE_INTEGER *)P;
                          }
                        }
                      }
                    }
                    if ( !(_BYTE)v241 || (v5[1].HighPart & 0x800) != 0 )
                      goto LABEL_882;
                    v180 = v171 + 58;
                    if ( v171[5].QuadPart > v171[58].QuadPart )
                      v180 = v171 + 5;
                    v263 = (__int64)v180;
                    if ( (v239 & 0x100) == 0
                      || (p_FileOffset = v171 + 4, v182 = v171[4], FileOffset.QuadPart <= v182.QuadPart) )
                    {
                      p_FileOffset = &FileOffset;
                      v182 = FileOffset;
                    }
                    if ( v182.QuadPart <= v180->QuadPart )
                    {
LABEL_882:
                      if ( (v171[64].LowPart & 8) != 0 )
                      {
                        NtfsNonCachedUsaWrite((int)v5, (int)v4, (int)v171, FileOffset.LowPart, v177);
                      }
                      else
                      {
                        if ( (v239 & 0x10000) == 0 )
                        {
                          if ( (v239 & 0x100) != 0 )
                          {
                            if ( (v239 & 0x200) != 0 )
                            {
                              if ( (v239 & 0x10) != 0 )
                                v183 = v171[2].QuadPart;
                              else
                                v183 = 0;
                              NtfsSetIoContextAsync((_DWORD)v5, (_DWORD)v171, v244, v252, v183, (v239 & 0x20) != 0);
                            }
                            else
                            {
                              if ( (v239 & 0x10) != 0 )
                                v184 = v171[2].QuadPart;
                              else
                                v184 = 0;
                              NtfsSetIoContextAsync(
                                (_DWORD)v5,
                                (_DWORD)v171,
                                *(_DWORD *)(*(_QWORD *)v257 + 8LL),
                                v252,
                                v184,
                                (v239 & 0x20) != 0);
                            }
                          }
                          else
                          {
                            NtfsSetIoContextAsync(
                              (_DWORD)v5,
                              (_DWORD)v171,
                              *(_DWORD *)(*(_QWORD *)v257 + 8LL),
                              v252,
                              v171[2].QuadPart,
                              (v239 & 0x20) != 0);
                          }
                        }
                        if ( *(_QWORD *)(v248 + 224) )
                        {
                          ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(v248 + 104) + 8LL));
                          v185 = *(_QWORD *)(v248 + 224);
                          *(_QWORD *)(v248 + 224) = 0;
                          ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(v248 + 104) + 8LL));
                          LOBYTE(v186) = 1;
                          LfsFlushToLsnWithoutDiskCacheFlush(*(_QWORD *)(v253 + 232), v185, v186, 0);
                        }
                        v187 = NtfsNonCachedIo((_DWORD)v5, v4, v177, v256);
                        LODWORD(v12) = v187;
                        v242 = v187;
                        if ( v187 == 259 )
                        {
                          if ( (v239 & 0x1000) != 0 )
                            *(_DWORD *)(v5[18].QuadPart + 4) &= ~2u;
                          v5[26].QuadPart = 0;
                          LOBYTE(v239) = v239 & 0xEF;
                          v4 = 0;
                          v265 = 0;
LABEL_998:
                          if ( Entry )
                            TxfDereferenceTxfVscb(Entry);
                          if ( !(_BYTE)v241 || (_DWORD)v12 == 259 )
                            goto LABEL_1055;
                          if ( (v239 & 0x10) != 0 )
                          {
                            if ( (v239 & 0x20) != 0 )
                            {
                              ExAcquireSharedStarveExclusive(*(PERESOURCE *)(v248 + 112), 0);
                              if ( (v5[1].HighPart & 0x80000010) != 0 )
                                v212 = (_DWORD *)v5[26].QuadPart;
                              else
                                v212 = 0;
                              v213 = *(_QWORD *)(v248 + 104);
                              if ( v212 )
                                *v212 &= ~0x10000u;
                              if ( _InterlockedDecrement((volatile signed __int32 *)(v213 + 384)) == 0x80000000
                                && _InterlockedCompareExchange((volatile signed __int32 *)(v213 + 384), 0, 0x80000000) == 0x80000000 )
                              {
                                ExReleaseResourceForThreadLite((PERESOURCE)(v213 + 280), (v213 + 280) | 3);
                              }
                              LOBYTE(v239) = v239 & 0xDF;
                            }
                            v214 = v5[6];
                            v215 = 0;
                            if ( !v214.QuadPart
                              || v214.QuadPart == v248
                              || (v216 = v5[7], v215 = 1, !v216.QuadPart)
                              || v216.QuadPart == v248 )
                            {
                              v5[v215 + 6].QuadPart = v248;
                            }
                            LOBYTE(v239) = v239 & 0xEF;
                          }
                          if ( (v239 & 0x100) != 0 )
                          {
LABEL_1055:
                            if ( (v239 & 0x10) != 0 )
                            {
                              if ( v5 && v5[3].HighPart )
                              {
                                if ( (v239 & 0x20) != 0 )
                                {
                                  ExAcquireSharedStarveExclusive(*(PERESOURCE *)(v248 + 112), 0);
                                  if ( (v5[1].HighPart & 0x80000010) != 0 )
                                    v228 = (_DWORD *)v5[26].QuadPart;
                                  else
                                    v228 = 0;
                                  v229 = *(_QWORD *)(v248 + 104);
                                  if ( v228 )
                                    *v228 &= ~0x10000u;
                                  if ( _InterlockedDecrement((volatile signed __int32 *)(v229 + 384)) == 0x80000000
                                    && _InterlockedCompareExchange(
                                         (volatile signed __int32 *)(v229 + 384),
                                         0,
                                         0x80000000) == 0x80000000 )
                                  {
                                    ExReleaseResourceForThreadLite((PERESOURCE)(v229 + 280), (v229 + 280) | 3);
                                  }
                                  LOBYTE(v239) = v239 & 0xDF;
                                }
                                v230 = v5[6];
                                v231 = 0;
                                if ( !v230.QuadPart
                                  || v230.QuadPart == v248
                                  || (v232 = v5[7], v231 = 1, !v232.QuadPart)
                                  || v232.QuadPart == v248 )
                                {
                                  v5[v231 + 6].QuadPart = v248;
                                }
                              }
                              else
                              {
                                ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))NtfsReleasePaging)(
                                  v5,
                                  (LARGE_INTEGER)v264.QuadPart,
                                  P,
                                  (v239 & 0x20) != 0);
                                LOBYTE(v239) = v239 & 0xDF;
                              }
                            }
                            if ( (_BYTE)v243 )
                              v5[2].QuadPart &= ~0x800000uLL;
                            if ( v4 )
                            {
                              if ( (v239 & 0x800) != 0 )
                                NtfsReleaseFcbEx(v5, *((_QWORD *)P + 23), 0);
                              if ( (v239 & 0x1000) != 0 )
                              {
                                *(_QWORD *)(v5[18].QuadPart + 224) = 0;
                                *(_DWORD *)(v5[18].QuadPart + 4) &= ~2u;
                              }
                            }
                            if ( NtfsStatusDebugFlags )
                            {
                              v233 = (int)v12 < 0;
                              if ( !(_DWORD)v12 )
                              {
LABEL_1093:
                                v15 = !v233;
                                goto LABEL_19;
                              }
                              if ( (_DWORD)v12 != 294
                                && (unsigned int)((_DWORD)v12 - 298) > 1
                                && (unsigned int)v12 < 0xFFFFFFED
                                && (_DWORD)v12 != -1073741802
                                && (unsigned int)((_DWORD)v12 + 2147483643) > 1
                                && (_DWORD)v12 != -1073741807
                                && (_DWORD)v12 != 259
                                && (_DWORD)v12 != -1073741608 )
                              {
                                NtfsStatusTraceAndDebugInternal(v5, (unsigned int)v12, 2495878);
                              }
                            }
                            v233 = (int)v12 < 0;
                            goto LABEL_1093;
                          }
                          if ( *((_QWORD *)P + 58) > *((_QWORD *)P + 4) )
                          {
                            if ( (v239 & 0x800) != 0
                              && !ExIsResourceAcquiredExclusiveLite((PERESOURCE)(*(_QWORD *)(*((_QWORD *)P + 23) + 104LL)
                                                                               + 64LL)) )
                            {
                              NtfsReleaseFcbEx(v5, *((_QWORD *)P + 23), 0);
                              BYTE1(v239) &= ~8u;
                            }
                            NtfsAcquireExclusiveFcb(v5, v248, P, 4);
                            v217 = P;
                            v218 = *((_QWORD *)P + 4);
                            if ( *((_QWORD *)P + 58) > v218 && (*((_BYTE *)P + 460) || (*((_DWORD *)P + 128) & 1) != 0) )
                            {
                              *((_QWORD *)P + 58) = v218;
                              v217 = P;
                            }
                            NtfsReleaseFcbEx(v5, v217[23], 0);
                          }
                          FsRtlAcquireHeaderMutex((char *)P + 120, (char *)P + 160, P);
                          v219 = v5[1].HighPart;
                          v220 = P;
                          if ( (v219 & 0x20000) != 0 )
                          {
                            v221 = *(union _LARGE_INTEGER **)v257;
                            if ( *((_QWORD *)P + 4) == *(_QWORD *)(*(_QWORD *)v257 + 24LL) )
                            {
                              v5[1].HighPart = v219 & 0xFFFDFFFF;
                              v221[3].QuadPart = -1;
                              v220 = P;
                            }
                          }
                          if ( v220[5] <= v220[4] )
                          {
LABEL_1052:
                            SharedCacheMap = FileObject->SectionObjectPointer->SharedCacheMap;
                            if ( SharedCacheMap )
                            {
                              SharedCacheMap[1] = v220[4];
                              v220 = P;
                            }
                            FsRtlReleaseHeaderMutex(v220 + 15, v220 + 20);
                            goto LABEL_1055;
                          }
                          if ( (v220[25] & 0x200) != 0 )
                            v220 = P;
                          v222 = *((_DWORD *)v220 + 50);
                          if ( (v222 & 0x20000) != 0 )
                          {
                            v223 = v220[4];
                            v224 = v220[58];
                            if ( v224 < v223 )
                            {
                              v225 = (v220[25] & 0x200) == 0;
                              goto LABEL_1047;
                            }
                            if ( v220[5] > v223 )
                            {
                              if ( !*(_QWORD *)(v220[36] + 16LL) || v223 == 0x7FFFFFFFFFFFFFFFLL )
                              {
                                if ( (v222 & 0x200) == 0 )
                                {
LABEL_1049:
                                  v226 = v220[4];
LABEL_1050:
                                  v220[58] = v226;
                                  v220 = P;
                                  goto LABEL_1051;
                                }
                                v225 = v224 == v223;
LABEL_1047:
                                if ( !v225 )
                                  v220 = P;
                                goto LABEL_1049;
                              }
                              if ( (__int64)((v223 + 4095) & 0xFFFFFFFFFFFFF000uLL) < v224 )
                              {
                                if ( (v222 & 0x200) != 0 )
                                  v220 = P;
                                v226 = (v220[4] + 4095LL) & 0xFFFFFFFFFFFFF000uLL;
                                goto LABEL_1050;
                              }
                            }
                          }
LABEL_1051:
                          v220[5] = v220[4];
                          v220 = P;
                          goto LABEL_1052;
                        }
                        if ( v187 >= 0 )
                          *(_BYTE *)(v5[26].QuadPart + 3) |= 1u;
                      }
                      BYTE1(v239) |= 0x80u;
                      LODWORD(v12) = v4->IoStatus.Status;
                      v242 = (int)v12;
                      if ( (int)v12 < 0 )
                      {
                        v5[3].LowPart = (unsigned int)v12;
                        if ( NtfsStatusDebugFlags
                          && (unsigned int)v12 < 0xFFFFFFED
                          && (_DWORD)v12 != -1073741802
                          && (unsigned int)((_DWORD)v12 + 2147483643) > 1
                          && (_DWORD)v12 != -1073741807
                          && (_DWORD)v12 != -1073741608 )
                        {
                          NtfsStatusTraceAndDebugInternal(v5, (unsigned int)v12, 2494967);
                        }
                        v188 = FsRtlNormalizeNtstatus((NTSTATUS)v12, -1073741591);
                        ExRaiseStatus(v188);
                      }
                      v138 = v244;
                      v137 = *(_QWORD *)v250;
                      if ( v244 )
                        v4->IoStatus.Information = v244;
                      else
                        v4->IoStatus.Information = v164;
LABEL_674:
                      if ( v4 )
                      {
                        if ( (v239 & 0x2000) != 0 && (v239 & 0x100) == 0 )
                        {
                          Information = 0;
                          if ( ((unsigned int)v12 & 0xC0000000) != 0xC0000000 )
                            Information = v4->IoStatus.Information;
                          *(_QWORD *)(v137 + 104) = FileOffset.QuadPart + Information;
                        }
                        v4->IoStatus.Status = (int)v12;
                        if ( (int)v12 >= 0 && (v239 & 0x200) != 0 )
                          v4->IoStatus.Information = v138;
                        v140 = v5[26];
                        if ( (v239 & 1) != 0 )
                          NtfsPostWriteProcessing(
                            (_DWORD)v5,
                            v140.LowPart,
                            (_DWORD)v4,
                            (_DWORD)P,
                            *((_QWORD *)P + 5),
                            v99,
                            (__int64)&v239,
                            v241);
                        else
                          NtfsPostWriteProcessing(
                            (_DWORD)v5,
                            v140.LowPart,
                            (_DWORD)v4,
                            (_DWORD)P,
                            v99,
                            v99,
                            (__int64)&v239,
                            v241);
                        if ( (int)v12 >= 0 )
                        {
                          LOBYTE(v241) = 0;
                          if ( v252 )
                          {
                            if ( (*(_DWORD *)(v252 + 8) & 0x4000) == 0 )
                            {
                              _InterlockedOr((volatile signed __int32 *)(v252 + 8), 0x4000u);
                              v211 = *(_QWORD *)(v252 + 128);
                              if ( v211 )
                              {
                                if ( !_InterlockedCompareExchange64((volatile signed __int64 *)P + 67, v211, 0) )
                                {
                                  *(_QWORD *)(v252 + 128) = 0;
                                  if ( *((_QWORD *)&xmmword_140095780 + 1) )
                                  {
                                    (*((void (__fastcall **)(_QWORD))&xmmword_140095780 + 1))(*((_QWORD *)P + 67));
                                    _InterlockedIncrement64((volatile signed __int64 *)(v253 + 8776));
                                  }
                                }
                              }
                            }
                          }
                        }
                        if ( P != *(PVOID *)(*((_QWORD *)P + 24) + 64LL) )
                          NtfsCleanupTransaction(v5, (unsigned int)v12, 0);
                      }
                      goto LABEL_998;
                    }
                    if ( (unsigned __int8)NtfsZeroData(
                                            (_DWORD)v5,
                                            (_DWORD)v171,
                                            FileObject,
                                            p_FileOffset->QuadPart - v180->QuadPart,
                                            0,
                                            0) )
                    {
                      v171 = (union _LARGE_INTEGER *)P;
                      goto LABEL_882;
                    }
                    goto LABEL_1127;
                  }
LABEL_916:
                  if ( (v171[25].LowPart & 8) == 0 )
                    BYTE1(v239) = BYTE1(v239) & 0x7F | (16 * (BYTE4(v5[1].QuadPart) & 0xF8));
                  if ( !v12->PrivateCacheMap )
                  {
                    if ( !(_BYTE)v241 )
                    {
                      v189 = P;
                      FsRtlAcquireEofLock((char *)P + 120, (char *)P + 160, v163);
                      if ( v5 )
                        v5[8].QuadPart = (LONGLONG)v189;
                      v12 = FileObject;
                    }
                    v190 = 0;
                    if ( *((_QWORD *)P + 4) > *((_QWORD *)P + 3) )
                      goto LABEL_1128;
                    NtfsInitializeCacheMap((_DWORD)v5, (_DWORD)v12, (_DWORD)P + 24, 0, (__int64)P);
                    NtfsUpdateBackingFileObject(v12, ChangeSharedCacheMap);
                    if ( !(_BYTE)v241 )
                    {
                      v191 = (char *)P;
                      if ( v5 )
                        v5[8].QuadPart = 0;
                      FsRtlReleaseEofLock(v191 + 120, v191 + 160);
                    }
                    CcSetReadAheadGranularity(v12, 0x10000u);
                    CcSetParallelFlushFile(v12, 1u);
                  }
                  if ( (v239 & 0x4000) != 0 && (v6 & 4) == 0 )
                  {
                    v192 = *((_BYTE *)P + 4) & 0x20;
                    if ( !v192 || (v193 = *((_QWORD *)P + 66)) == 0 || (v194 = 1, (*(_DWORD *)(v193 + 24) & 0x800) == 0) )
                      v194 = 0;
                    if ( (v5[4].LowPart & 0x200) != 0
                      || v192 && (v195 = *((_QWORD *)P + 66)) != 0 && (*(_DWORD *)(v195 + 24) & 0x800) != 0 )
                    {
                      v196 = 0;
                    }
                    else
                    {
                      v196 = v4;
                    }
                    LODWORD(v12) = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))TxfLogPriorToWrite)(
                                     v5,
                                     v12,
                                     Entry,
                                     (union _LARGE_INTEGER)FileOffset.QuadPart,
                                     v164,
                                     v196,
                                     v194,
                                     0);
                    v242 = (int)v12;
                    if ( (int)v12 < 0 )
                      goto LABEL_673;
                    v12 = FileObject;
                  }
                  if ( (v239 & 0x40) != 0 && (v5[1].HighPart & 0x100) == 0 )
                  {
                    ExConvertExclusiveToSharedLite(*(PERESOURCE *)(*((_QWORD *)P + 23) + 112LL));
                    LOBYTE(v239) = v239 & 0x3F | 0x80;
                  }
                  if ( (_BYTE)v241 )
                  {
                    v197 = P;
                    v276 = *(_OWORD *)((char *)P + 24);
                    v277 = *((_QWORD *)P + 5);
                    if ( v99 > *((_QWORD *)P + 4) )
                    {
                      *((_QWORD *)&v276 + 1) = v99;
                      *(_DWORD *)(*(_QWORD *)v250 + 80LL) |= 0x2000u;
                      v197 = P;
                    }
                    NtfsSetBothCacheSizes(v5, v12, &v276, v197);
                    if ( (v239 & 0x1000) != 0 )
                      *(_QWORD *)(v5[18].QuadPart + 224) = (char *)&v276 + 8;
                    v198 = P;
                    if ( (*((_DWORD *)P + 50) & 0x20000) != 0 )
                      goto LABEL_964;
                    v199 = (char *)P + 464;
                    v200 = *(union _LARGE_INTEGER *)((char *)P + 464);
                    v201 = *(union _LARGE_INTEGER *)((char *)P + 40);
                    if ( v201.QuadPart > v200.QuadPart )
                      v199 = (char *)P + 40;
                    v263 = (__int64)v199;
                    if ( v201.QuadPart <= v200.QuadPart )
                      v201 = v200;
                    if ( FileOffset.QuadPart <= v201.QuadPart )
                    {
LABEL_964:
                      v12 = FileObject;
LABEL_967:
                      if ( v198[113] )
                      {
                        v204 = v198[128];
                        if ( (v204 & 0x40000) == 0 )
                        {
                          if ( (v204 & 0x2000) == 0 )
                          {
                            NtfsAcquireExclusiveScbEx(v5, v198, 0);
                            BYTE1(v239) |= 8u;
                            v205 = NtfsEnforceReservation((_DWORD)v5);
                            v6 = v205;
                            v242 = v205;
                            if ( v205 < 0 )
                              goto LABEL_1132;
                            NtfsReleaseFcbEx(v5, *((_QWORD *)P + 23), 0);
                            BYTE1(v239) &= ~8u;
                          }
                          if ( !(unsigned __int8)NtfsReserveClusters((int)v5, 0) )
                          {
LABEL_1140:
                            if ( NtfsStatusDebugFlags )
                              NtfsStatusTraceAndDebugInternal(v5, 3221225599LL, 2495396);
                            NtfsRaiseStatusInternal((_DWORD)v5, -1073741697, 0, 0, 2495396);
                            goto LABEL_1143;
                          }
                        }
                      }
                      if ( (v5[4].LowPart & 0x200) != 0 )
                      {
                        CcPrepareMdlWrite(v12, &FileOffset, v164, &v4->MdlAddress, &v4->IoStatus);
                        LODWORD(v12) = v4->IoStatus.Status;
                        v242 = (int)v12;
                      }
                      else
                      {
                        v206 = NtfsMapUserBuffer(v4, 16);
                        if ( (v12->Flags & 0x10) != 0 )
                        {
                          v5[2].QuadPart |= 0x800000uLL;
                          v207 = 1;
                          LOBYTE(v243) = 1;
                        }
                        else
                        {
                          v207 = v243;
                        }
                        if ( !(unsigned __int8)CcCopyWriteEx(
                                                 v12,
                                                 &FileOffset,
                                                 v164,
                                                 BYTE4(v5[1].QuadPart) & 1,
                                                 v206,
                                                 v4->Tail.Overlay.Thread) )
                        {
LABEL_1143:
                          NtfsRaiseStatusInternal((_DWORD)v5, -1073741608, 0, 0, 2495433);
LABEL_1144:
                          if ( NtfsStatusDebugFlags
                            && (unsigned int)v208 < 0xFFFFFFED
                            && (_DWORD)v208 != -1073741802
                            && (unsigned int)(v208 + 2147483643) > 1
                            && (_DWORD)v208 != -1073741807
                            && (_DWORD)v208 != -1073741608 )
                          {
                            NtfsStatusTraceAndDebugInternal(v5, v208, 2495437);
                          }
                          NtfsRaiseStatusInternal((_DWORD)v5, v5[3].LowPart, 0, 0, 2495437);
                          goto LABEL_1152;
                        }
                        v208 = v5[3].LowPart;
                        if ( (int)v208 < 0 )
                          goto LABEL_1144;
                        if ( v207 )
                        {
                          v5[2].QuadPart &= ~0x800000uLL;
                          LOBYTE(v243) = 0;
                        }
                        v4->IoStatus.Status = 0;
                        v4->IoStatus.Information = v164;
                        LODWORD(v12) = 0;
                        v242 = 0;
                      }
                      if ( (*(_DWORD *)(*((_QWORD *)P + 24) + 4LL) & 0x4000000) == 0 || v164 < 0x10000 )
                        goto LABEL_673;
                      IoStatus = 0;
                      CcFlushCache((PSECTION_OBJECT_POINTERS)(*((_QWORD *)P + 36) + 16LL), &FileOffset, v164, &IoStatus);
                      v209 = v5[3].LowPart;
                      if ( (int)v209 >= 0 )
                      {
                        Status = (unsigned int)IoStatus.Status;
                        if ( IoStatus.Status >= 0 )
                          goto LABEL_673;
LABEL_1160:
                        if ( NtfsStatusDebugFlags
                          && (_DWORD)Status
                          && (_DWORD)Status != 294
                          && (unsigned int)(Status - 298) > 1
                          && (unsigned int)Status < 0xFFFFFFED
                          && (_DWORD)Status != -1073741802
                          && (unsigned int)(Status + 2147483643) > 1
                          && (_DWORD)Status != -1073741807
                          && (_DWORD)Status != 259
                          && (_DWORD)Status != -1073741608 )
                        {
                          NtfsStatusTraceAndDebugInternal(v5, Status, 2495528);
                        }
                        NtfsRaiseStatusInternal((_DWORD)v5, IoStatus.Status, 0, 0, 2495528);
                        __debugbreak();
                        JUMPOUT(0x14001C2CBLL);
                      }
LABEL_1152:
                      if ( NtfsStatusDebugFlags
                        && (unsigned int)v209 < 0xFFFFFFED
                        && (_DWORD)v209 != -1073741802
                        && (unsigned int)(v209 + 2147483643) > 1
                        && (_DWORD)v209 != -1073741807
                        && (_DWORD)v209 != -1073741608 )
                      {
                        NtfsStatusTraceAndDebugInternal(v5, v209, 2495524);
                      }
                      NtfsRaiseStatusInternal((_DWORD)v5, v5[3].LowPart, 0, 0, 2495524);
                      goto LABEL_1160;
                    }
                    if ( FileOffset.QuadPart - *(_QWORD *)v199 > 0x400000 && v164 <= 8 )
                    {
                      v269 = 0;
                      v202 = (const void *)NtfsMapUserBuffer(v4, 16);
                      v203 = memcmp(v202, &NtfsLarge0, v164);
                      v269 = v203 == 0;
                      if ( !v203 )
                      {
                        *(_QWORD *)(v5[26].QuadPart + 80) = 4;
                        LOBYTE(v239) = v239 | 1;
                        v4->IoStatus.Information = v164;
                        LODWORD(v12) = 0;
                        v242 = 0;
                        goto LABEL_673;
                      }
                      LODWORD(v198) = (_DWORD)P;
                    }
                    BytesToWritea = FileOffset.QuadPart - *(_QWORD *)v199;
                    v12 = FileObject;
                    if ( !(unsigned __int8)NtfsZeroData((_DWORD)v5, (_DWORD)v198, FileObject, BytesToWritea, 0, 0) )
                      goto LABEL_1131;
                  }
                  else
                  {
                    v12 = FileObject;
                  }
                  v198 = P;
                  goto LABEL_967;
                }
                goto LABEL_1112;
              }
LABEL_1109:
              if ( NtfsStatusDebugFlags )
                NtfsStatusTraceAndDebugInternal(v5, 3221225763LL, 2493084);
              NtfsRaiseStatusInternal((_DWORD)v5, -1073741533, 0, 0, 2493084);
LABEL_1112:
              if ( NtfsStatusDebugFlags )
                NtfsStatusTraceAndDebugInternal(v5, (unsigned int)v12, 2493091);
              NtfsRaiseStatusInternal((_DWORD)v5, (_DWORD)v12, 0, 0, 2493091);
              goto LABEL_1115;
            }
LABEL_1106:
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(v5, 3221225768LL, 2493075);
            NtfsRaiseStatusInternal((_DWORD)v5, -1073741528, 0, 0, 2493075);
            goto LABEL_1109;
          }
LABEL_1103:
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(v5, 3221225659LL, 2492918);
          NtfsRaiseStatusInternal((_DWORD)v5, -1073741637, 0, 0, 2492918);
          goto LABEL_1106;
        }
LABEL_1100:
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(v5, 3221226659LL, 2492912);
        NtfsRaiseStatusInternal((_DWORD)v5, -1073740637, 0, 0, 2492912);
        goto LABEL_1103;
      }
      LOBYTE(v246) = 0;
      if ( (v239 & 0x10000) != 0
        || (v239 & 0x2000) == 0
        && (v82 & 2) != 0
        && (v83 = IoGetIoPriorityHint(v4), LOBYTE(v82) = v239, v57 = v255, v83 < IoPriorityNormal) )
      {
        v84 = 2;
      }
      else
      {
        v84 = 0;
      }
      v85 = v84 | BYTE2(v239) & 0xFD;
      BYTE2(v239) = v85;
      if ( (v5[1].HighPart & 0x100) != 0 || *((_BYTE *)P + 460) && !*((_QWORD *)P + 35) )
        goto LABEL_444;
      v12 = FileObject;
      if ( v57 != 5 && (v82 & 2) != 0 && (v239 & 0x4000) == 0 && FileObject->SectionObjectPointer->DataSectionObject )
        goto LABEL_444;
      v86 = (v82 & 2) != 0;
      if ( (!v86 || (v239 & 0x4000) != 0) && !FileObject->SectionObjectPointer->SharedCacheMap )
        goto LABEL_444;
      if ( v86 && (v239 & 0x4000) != 0 && !*((_QWORD *)P + 35) )
        goto LABEL_444;
      if ( (*((_DWORD *)P + 50) & 0x10) != 0 )
      {
        v87 = *((_QWORD *)P + 23);
        v88 = *(_QWORD *)(v87 + 328);
        if ( (!v88 || !*(_QWORD *)(v88 + 24)) && (*(_DWORD *)(v87 + 4) & 0x20020100) == 0x20000000 )
        {
          v85 = BYTE2(v239);
LABEL_444:
          v89 = (v85 & 2) != 0;
LABEL_445:
          v90 = v239 & 0xEF | (16 * (NtfsAcquirePagingResourceExclusive(v5, P, v89, v9) & 1)) | 0x40;
          LOBYTE(v239) = v90;
          goto LABEL_446;
        }
      }
      if ( (v239 & 2) == 0
        || (v239 & 0x4000) != 0
        || (*((_WORD *)P + 230) & 0x40FF) != 0
        || (v91 = IoGetIoPriorityHint(v4), v92 = &v246, v91 < IoPriorityNormal) )
      {
        v92 = 0;
      }
      v90 = v239 & 0xEF | (16 * (NtfsAcquirePagingShared(v5, P, (v239 & 0x20000) != 0, v92) & 1));
      LOBYTE(v239) = v90;
      if ( (v90 & 0x10) == 0 )
        goto LABEL_1099;
      v93 = P;
      if ( !*((_BYTE *)P + 460) || *((_QWORD *)P + 35) )
      {
        if ( v255 == 5 || (v90 & 2) == 0 )
        {
          v94 = BYTE1(v239);
        }
        else
        {
          v94 = BYTE1(v239);
          if ( (v239 & 0x4000) == 0 && v12->SectionObjectPointer->DataSectionObject )
            goto LABEL_460;
        }
        v95 = v90 & 2;
        if ( (v95 && (v94 & 0x40) == 0 || v12->SectionObjectPointer->SharedCacheMap)
          && (!v95 || (v94 & 0x40) == 0 || *((_QWORD *)P + 35)) )
        {
          v96 = *(_DWORD *)(*((_QWORD *)P + 23) + 4LL);
          if ( (*((_DWORD *)P + 50) & 0x10) == 0
            || (v97 = *(_QWORD *)(*((_QWORD *)P + 23) + 328LL)) != 0 && *(_QWORD *)(v97 + 24)
            || (v96 & 0x20100) != 0
            || (v96 & 0x20000000) == 0 && ((v96 & 0x10000000) != 0 || !(unsigned __int8)NtfsGetPurgeKernelEAState()) )
          {
            v90 = v239;
LABEL_446:
            if ( (v90 & 0x10) != 0 )
            {
              v82 = (unsigned __int8)v246;
              LOBYTE(v82) = v90 & 0xDF | (32 * (v246 & 1));
              LOBYTE(v239) = v82;
              v57 = v255;
              v70 = v256;
              goto LABEL_477;
            }
LABEL_1099:
            LOBYTE(v239) = v90 & 0xBF;
            NtfsRaiseStatusInternal((_DWORD)v5, -1073741608, 0, 0, 2492900);
            goto LABEL_1100;
          }
          v93 = P;
        }
      }
LABEL_460:
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))NtfsReleasePaging)(
        v5,
        (LARGE_INTEGER)v264.QuadPart,
        v93,
        (unsigned __int8)v246);
      LOBYTE(v246) = 0;
      v89 = BYTE2(v239);
      LOBYTE(v89) = (v239 & 0x20000) != 0;
      goto LABEL_445;
    }
    if ( v252 && (*(_DWORD *)(v252 + 8) & 0x2000) != 0 )
      v5[34].LowPart = *(_DWORD *)(v252 + 100);
    if ( v5 == (LARGE_INTEGER *)v5[18].QuadPart && LOBYTE(IoGetTopLevelIrp()->Type) )
    {
      if ( ExIsResourceAcquiredSharedLite((PERESOURCE)(*(_QWORD *)(*((_QWORD *)P + 23) + 104LL) + 64LL))
        || *((_QWORD *)P + 2) && ExIsResourceAcquiredSharedLite(*(PERESOURCE *)(*((_QWORD *)P + 23) + 112LL)) )
      {
        LOBYTE(IoGetTopLevelIrp()->Type) = 0;
      }
    }
    else if ( (*(_DWORD *)(v5[18].QuadPart + 12) & 8) != 0
           && ((*((_DWORD *)P + 128) & 0x20) == 0 || (dword_1400956B8 & 0x200000) != 0) )
    {
      v5[1].HighPart |= 8u;
      *(_BYTE *)(v5[26].QuadPart + 3) |= 2u;
    }
    if ( !*((_QWORD *)P + 2)
      || ExIsResourceAcquiredSharedLite(*(PERESOURCE *)(*((_QWORD *)P + 23) + 112LL))
      || ExIsResourceAcquiredSharedLite((PERESOURCE)(*(_QWORD *)(*((_QWORD *)P + 23) + 104LL) + 64LL)) )
    {
      goto LABEL_628;
    }
    v115 = P;
    if ( *((_BYTE *)P + 460) && !*((_QWORD *)P + 35) )
      goto LABEL_597;
    if ( (*((_DWORD *)P + 50) & 0x10) != 0 )
    {
      v116 = P;
      v117 = *((_QWORD *)P + 23);
      v118 = *(_QWORD *)(v117 + 328);
      if ( v118 && *(_QWORD *)(v118 + 24) )
      {
LABEL_599:
        v119 = v239 & 0xEF | (16 * (NtfsAcquirePagingResourceSharedStarveExclusive(v5, v116, 0) & 1));
        LOBYTE(v239) = v119;
        if ( (v119 & 0x10) == 0 )
        {
LABEL_615:
          LOBYTE(v239) = v119 & 0xBF;
          LODWORD(v12) = -1073741740;
          if ( !NtfsStatusDebugFlags )
            goto LABEL_485;
          v98 = 2493465;
          goto LABEL_484;
        }
        v120 = P;
        if ( !*((_BYTE *)P + 460) || *((_QWORD *)P + 35) )
        {
          v121 = *(_DWORD *)(*((_QWORD *)P + 23) + 4LL);
          if ( (*((_DWORD *)P + 50) & 0x10) == 0
            || (v122 = *(_QWORD *)(*((_QWORD *)P + 23) + 328LL)) != 0 && *(_QWORD *)(v122 + 24)
            || (v121 & 0x20100) != 0
            || (v121 & 0x20000000) == 0 && ((v121 & 0x10000000) != 0 || !(unsigned __int8)NtfsGetPurgeKernelEAState()) )
          {
            v119 = v239;
            goto LABEL_614;
          }
          v120 = P;
        }
        if ( *(_WORD *)v120 != 1794 )
          v120 = (PVOID)*((_QWORD *)v120 + 23);
        ExReleaseResourceLite(*((PERESOURCE *)v120 + 14));
        v119 = v239 & 0xEF | (16 * (NtfsAcquirePagingResourceExclusive(v5, P, 0, v123) & 1)) | 0x40;
        LOBYTE(v239) = v119;
        goto LABEL_614;
      }
      if ( (*(_DWORD *)(v117 + 4) & 0x20020100) == 0x20000000 )
      {
        v115 = P;
LABEL_597:
        v119 = v239 & 0xEF | (16 * (NtfsAcquirePagingResourceExclusive(v5, v115, 0, v114) & 1)) | 0x40;
        LOBYTE(v239) = v119;
LABEL_614:
        if ( (v119 & 0x10) == 0 )
          goto LABEL_615;
        v5[2].QuadPart |= 0x400000uLL;
        if ( (v239 & 0x40) != 0 && (!*((_BYTE *)P + 460) || *((_QWORD *)P + 35)) )
        {
          if ( (v124 = *(_DWORD *)(*((_QWORD *)P + 23) + 4LL), (*((_DWORD *)P + 50) & 0x10) == 0)
            || (v125 = *(_QWORD *)(*((_QWORD *)P + 23) + 328LL)) != 0 && *(_QWORD *)(v125 + 24)
            || (v124 & 0x20100) != 0
            || (v124 & 0x20000000) == 0 && ((v124 & 0x10000000) != 0 || !(unsigned __int8)NtfsGetPurgeKernelEAState()) )
          {
            ExConvertExclusiveToSharedLite(*(PERESOURCE *)(*((_QWORD *)P + 23) + 112LL));
            LOBYTE(v239) = v239 & 0x3F | 0x80;
          }
        }
LABEL_628:
        if ( *((_DWORD *)P + 129) == 3 && *((_DWORD *)P + 64) == 128 )
        {
LABEL_1115:
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(v5, 3221226659LL, 2493497);
          NtfsRaiseStatusInternal((_DWORD)v5, -1073740637, 0, 0, 2493497);
          goto LABEL_1118;
        }
        v126 = *((_DWORD *)P + 128);
        if ( (v126 & 0x40) != 0 )
        {
LABEL_1118:
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(v5, 3221225763LL, 2493506);
          NtfsRaiseStatusInternal((_DWORD)v5, -1073741533, 0, 0, 2493506);
          goto LABEL_1121;
        }
        if ( (v126 & 0x10000) != 0 )
          LODWORD(v12) = -1073741202;
        else
          LODWORD(v12) = (v126 & 0x1000000) != 0 ? 0xC0000008 : 0;
        v242 = (int)v12;
        if ( (int)v12 < 0 )
        {
LABEL_1121:
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(v5, (unsigned int)v12, 2493513);
          NtfsRaiseStatusInternal((_DWORD)v5, (_DWORD)v12, 0, 0, 2493513);
          goto LABEL_1124;
        }
        if ( *((_DWORD *)P + 64) == 128 && (unsigned __int8)*((_WORD *)P + 230) >= 2u )
        {
LABEL_1124:
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(v5, 3221225659LL, 2493519);
          NtfsRaiseStatusInternal((_DWORD)v5, -1073741637, 0, 0, 2493519);
LABEL_1127:
          NtfsRaiseStatusInternal((_DWORD)v5, -1073741608, 0, 0, 2494741);
LABEL_1128:
          v6 = 2495050;
          NtfsAttachCorruption_BadOrOrphanFRS((_DWORD)v5, 2, 2495050, v190, v248 + 8, v248, v190);
          NtfsAttachRepairInfoPriv(v5, 256, 0, 0xA70026124ALL);
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(v5, 3221225730LL, 2495050);
          NtfsRaiseStatusInternal((_DWORD)v5, -1073741566, v248 + 8, v248, 2495050);
LABEL_1131:
          v205 = NtfsRaiseStatusInternal((_DWORD)v5, -1073741608, 0, 0, 2495352);
LABEL_1132:
          if ( NtfsStatusDebugFlags
            && (unsigned int)v205 < 0xFFFFFFED
            && v205 != -1073741802
            && (unsigned int)(v205 + 2147483643) > 1
            && v6 != -1073741807
            && v6 != -1073741608 )
          {
            NtfsStatusTraceAndDebugInternal(v5, v6, 2495387);
          }
          NtfsRaiseStatusInternal((_DWORD)v5, v6, 0, 0, 2495387);
          goto LABEL_1140;
        }
        if ( (v239 & 0x10000) == 0 && *((_DWORD *)P + 113) && *((_BYTE *)P + 460) )
        {
          BYTE2(v239) |= 1u;
          v5[1].HighPart |= 1u;
          *(_BYTE *)(v5[26].QuadPart + 3) |= 1u;
        }
        if ( IoGetTopLevelIrp()->AssociatedIrp.MasterIrp == (struct _IRP *)2 )
        {
          v128 = v5[1].HighPart | 0x800;
          v5[1].HighPart = v128;
          v5[1].HighPart = v128 & 0xFFFFFFF7;
          *(_BYTE *)(v5[26].QuadPart + 3) &= ~2u;
          if ( (*((_DWORD *)P + 128) & 0x100) != 0 )
            FileObject->Flags |= 0x8000u;
          else
            FileObject->Flags &= ~0x8000u;
        }
        else
        {
          v129 = v5[18];
          v130 = *(_DWORD *)(v129.QuadPart + 4);
          if ( (v130 & 2) != 0 )
          {
            BYTE1(v239) |= 4u;
          }
          else
          {
            *(_DWORD *)(v129.QuadPart + 4) = v130 | 2;
            BYTE1(v239) |= 0x10u;
          }
          if ( (*(_DWORD *)(v5[18].QuadPart + 4) & 0x1000000) != 0 )
            LOBYTE(v239) = v239 | 4;
        }
        FsRtlAcquireHeaderMutex((char *)P + 120, (char *)P + 160, v127);
        v131 = BYTE1(v239);
        v132 = P;
        v133 = FileOffset;
        if ( (v239 & 0x400) != 0 )
          goto LABEL_695;
        if ( (*((_DWORD *)P + 128) & 0x20) == 0 && FileOffset.QuadPart + (unsigned int)Size > *((_QWORD *)P + 5) )
        {
          v134 = (v239 & 8) != 0 || (v239 & 4) == 0 && v5 != (LARGE_INTEGER *)v5[18].QuadPart;
          LODWORD(v12) = NtfsGetIoAtEof((_DWORD)v5, (_DWORD)P, FileOffset.LowPart, Size, v134, (__int64)&v241);
          v242 = (int)v12;
          if ( (int)v12 < 0 )
          {
            FsRtlReleaseHeaderMutex((char *)P + 120, (char *)P + 160);
            if ( (v239 & 4) == 0 )
              goto LABEL_486;
            LODWORD(v12) = -1073741245;
            if ( !NtfsStatusDebugFlags )
              goto LABEL_485;
            v98 = 2493691;
            goto LABEL_484;
          }
          v132 = P;
          v133 = FileOffset;
          v131 = BYTE1(v239);
        }
        if ( (v5[1].HighPart & 0x800) == 0 )
        {
LABEL_695:
          v99 = *(_QWORD *)v249;
        }
        else
        {
          v135 = v132[5];
          if ( (*((_BYTE *)v132 + 4) & 0x20) != 0 && (v132[25] & 0x40000) != 0 )
          {
            v99 = *(_QWORD *)v249;
            if ( *(__int64 *)v249 > v135
              && v133.QuadPart < v132[4]
              && *(__int64 *)v249 > (__int64)((v135 + 4095) & 0xFFFFFFFFFFFFF000uLL) )
            {
              FsRtlReleaseHeaderMutex(v132 + 15, v132 + 20);
              LODWORD(v12) = -1073741740;
              if ( !NtfsStatusDebugFlags )
              {
LABEL_672:
                v242 = (int)v12;
                goto LABEL_673;
              }
              v136 = 2493753;
LABEL_671:
              NtfsStatusTraceAndDebugInternal(0, (unsigned int)v12, v136);
              goto LABEL_672;
            }
          }
          else
          {
            if ( v133.QuadPart >= v135 )
            {
              *(_QWORD *)(v5[26].QuadPart + 80) = 2;
              if ( (v5[2].LowPart & 0x100000) == 0
                && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x2000000000LL) != 0 )
              {
                McTemplateU0ppp_EtwWriteTransfer(
                  (unsigned int)&NtfsLog_Context,
                  (unsigned int)write_c3397,
                  FileOffset.LowPart,
                  *((_QWORD *)P + 5),
                  (char)P);
              }
              LOBYTE(v241) = 0;
              v4->IoStatus.Information = 0;
              FsRtlReleaseHeaderMutex((char *)P + 120, (char *)P + 160);
              LODWORD(v12) = 0;
              v242 = 0;
              v99 = *(_QWORD *)v249;
              goto LABEL_673;
            }
            v141 = -*(_DWORD *)(v253 + 376) & (unsigned __int64)(v135 + *(_DWORD *)(v253 + 376) - 1);
            v99 = *(_QWORD *)v249;
            if ( *(__int64 *)v249 > v141 )
            {
              if ( (v5[2].LowPart & 0x100000) == 0
                && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x2000000000LL) != 0 )
              {
                McTemplateU0ppp_EtwWriteTransfer(
                  (unsigned int)&NtfsLog_Context,
                  (unsigned int)write_c3419,
                  v249[0],
                  v141,
                  (char)v132);
                v132 = P;
                v133 = FileOffset;
                v131 = BYTE1(v239);
              }
              v99 = v141;
              *(_QWORD *)v249 = v141;
              *(_QWORD *)v260 = v141;
              v142 = (unsigned int)(v141 - v133.LowPart);
              Size = v142;
              v268 = v142;
              goto LABEL_697;
            }
          }
        }
        LODWORD(v142) = Size;
LABEL_697:
        v143 = v132 + 3;
        v263 = (__int64)(v132 + 3);
        v144 = v132[3];
        if ( v99 > v144 )
        {
          if ( v133.QuadPart >= v144 )
          {
            v4->IoStatus.Information = 0;
            *(_QWORD *)(v5[26].QuadPart + 80) = 2;
            v99 = *v143;
            *(_QWORD *)v260 = *v143;
            LOBYTE(v241) = 0;
            FsRtlReleaseHeaderMutex((char *)P + 120, (char *)P + 160);
            LODWORD(v12) = 0;
            v242 = 0;
            goto LABEL_673;
          }
          v99 = v132[3];
          *(_QWORD *)v249 = v99;
          LODWORD(v142) = v144 - v133.LowPart;
          Size = (unsigned int)(v144 - v133.LowPart);
          v268 = v144 - v133.LowPart;
          *(_QWORD *)v260 = v144;
        }
        v145 = v132 + 4;
        v263 = (__int64)(v132 + 4);
        if ( (v131 & 4) != 0 )
        {
          v146 = v5[18];
          if ( (*(_DWORD *)(v146.QuadPart + 4) & 2) != 0 )
          {
            if ( *(_QWORD *)(v146.QuadPart + 224) )
              v145 = *(__int64 **)(v146.QuadPart + 224);
            v263 = (__int64)v145;
          }
        }
        v147.QuadPart = *v145;
        if ( v99 > *v145 )
        {
          if ( v147.QuadPart > v133.QuadPart )
          {
            v244 = v147.LowPart - v133.LowPart;
            v262 = v147.LowPart - v133.LowPart;
          }
          BYTE1(v239) = v131 | 2;
        }
        FsRtlReleaseHeaderMutex(v132 + 15, v132 + 20);
        if ( (*((_BYTE *)P + 4) & 0x20) != 0
          && (*((_DWORD *)P + 50) & 0x40000) != 0
          && (*(_DWORD *)(*((_QWORD *)P + 23) + 4LL) & 0x20100) == 0
          && (*((_QWORD *)P + 66) && (v6 & 2) == 0 || (v148 = *(_QWORD *)(v248 + 328)) == 0 || !*(_QWORD *)(v148 + 24))
          && ((*(_DWORD *)(v5[18].QuadPart + 4) & 4) == 0 || !v4->MdlAddress || !(unsigned int)MmMdlPagesAreZero()) )
        {
          NtfsPostUsnChangeWithOverrideOption((_DWORD)v5, (_DWORD)P, 1, 0, FileOffset.QuadPart, (unsigned int)v142, 0);
        }
        goto LABEL_721;
      }
    }
    v116 = P;
    goto LABEL_599;
  }
  v58 = v253;
  if ( (*(_DWORD *)(v253 + 4) & 2) == 0 && (*(_DWORD *)(v253 + 24) & 0x40000) != 0 )
  {
    if ( NtfsStatusDebugFlags )
    {
      v25 = 2492564;
      goto LABEL_284;
    }
LABEL_285:
    LOBYTE(v9) = v4 != 0;
    NtfsExtendedCompleteRequestInternal(v5, v4, 3221226650LL, v9, 0);
    return 3221226650LL;
  }
  if ( (*(_DWORD *)(v253 + 4) & 2) != 0 || (*(_BYTE *)(*(_QWORD *)v257 + 2LL) & 0x10) != 0 )
  {
    v60 = (PERESOURCE *)P;
    v59 = FileOffset.QuadPart;
    v61 = *(_QWORD *)v249;
  }
  else
  {
    v59 = FileOffset.QuadPart;
    v60 = (PERESOURCE *)P;
    v61 = *(_QWORD *)v249;
    if ( FileOffset.QuadPart >= 0
      && FileOffset.QuadPart < *((_QWORD *)P + 4)
      && *(__int64 *)v249 > (unsigned int)(16 * *(_DWORD *)(v253 + 364)) )
    {
      if ( (v239 & 0x10) != 0 )
      {
        if ( *(_WORD *)P != 1794 )
          v60 = (PERESOURCE *)*((_QWORD *)P + 23);
        ExReleaseResourceLite(v60[14]);
        v58 = v253;
      }
      if ( Entry )
      {
        TxfDereferenceTxfVscb(Entry);
        v58 = v253;
      }
      if ( (v5[2].LowPart & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
      {
        v62 = *(_QWORD *)(v58 + 248);
        v63 = *(_WORD *)(v62 + 6);
        if ( v63 > 0x40u || (v63 & 1) != 0 )
          v63 = 0;
        McTemplateU0ppwwii_EtwWriteTransfer(
          (unsigned int)&NtfsLog_Context,
          (unsigned int)write_c2216,
          (unsigned int)KeGetCurrentThread(),
          v253,
          *(_WORD *)(v58 + 7872) >> 1,
          *(_QWORD *)(v58 + 7880),
          v63 >> 1,
          v62 + 32,
          v61,
          16 * *(_BYTE *)(v58 + 364));
      }
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(v5, 3221225506LL, 2492596);
      LOBYTE(v9) = v4 != 0;
      NtfsExtendedCompleteRequestInternal(v5, v4, 3221225506LL, v9, 0);
      return 3221225506LL;
    }
  }
  v9 = v252;
  if ( (*(_DWORD *)(v252 + 4) & 0x100) == 0 )
  {
    if ( v59 < 0 || (v64 = (__int64)v60[4], v64 <= v59) )
    {
      v69 = v5[26];
      if ( v69.QuadPart && (v5[1].HighPart & 0x80000010) != 0 )
      {
        *(_QWORD *)(v69.QuadPart + 80) = 3;
        v60 = (PERESOURCE *)P;
      }
      if ( (v239 & 0x10) != 0 )
      {
        if ( *(_WORD *)v60 != 1794 )
          v60 = (PERESOURCE *)v60[23];
        ExReleaseResourceLite(v60[14]);
      }
      if ( Entry )
        TxfDereferenceTxfVscb(Entry);
      goto LABEL_120;
    }
    if ( v64 < v61 )
      LODWORD(LowPart) = v64 - v59;
  }
  if ( (v239 & 0x10000) == 0 )
  {
    NtfsSetIoContextAsync((_DWORD)v5, (_DWORD)v60, LowPart, v252, 0, 0);
    v59 = FileOffset.QuadPart;
  }
  v65 = NtfsVolumeDasdIo((_DWORD)v5, v59, LowPart);
  v67 = FileObject;
  if ( v65 >= 0 )
    NtfsUpdateFileTimestampsForModification(FileObject, v248, v252);
  if ( (v239 & 0x2000) != 0 && (v239 & 0x100) == 0 && v65 >= 0 )
    v67->CurrentByteOffset.QuadPart = FileOffset.QuadPart + v4->IoStatus.Information;
  if ( (v239 & 0x10) != 0 )
  {
    v68 = (PERESOURCE *)P;
    if ( *(_WORD *)P != 1794 )
      v68 = (PERESOURCE *)*((_QWORD *)P + 23);
    ExReleaseResourceLite(v68[14]);
  }
  if ( Entry )
    TxfDereferenceTxfVscb(Entry);
  if ( (v239 & 0x10000) != 0 )
  {
    if ( NtfsStatusDebugFlags
      && v65
      && v65 != 294
      && (unsigned int)(v65 - 298) > 1
      && (unsigned int)v65 < 0xFFFFFFED
      && v65 != -1073741802
      && (unsigned int)(v65 + 2147483643) > 1
      && v65 != -1073741807
      && v65 != 259
      && v65 != -1073741608 )
    {
      NtfsStatusTraceAndDebugInternal(v5, (unsigned int)v65, 2492696);
    }
    LOBYTE(v66) = v4 != 0;
    NtfsExtendedCompleteRequestInternal(v5, v4, (unsigned int)v65, v66, v65 >= 0);
  }
  return (unsigned int)v65;
}

```

## disassembly

```asm
0x1400177d0  mov     r11, rsp
0x1400177d3  push    rbx
0x1400177d4  push    rsi
0x1400177d5  push    rdi
0x1400177d6  push    r12
0x1400177d8  push    r13
0x1400177da  push    r14
0x1400177dc  push    r15
0x1400177de  sub     rsp, 1A0h
0x1400177e5  mov     rax, cs:__security_cookie
0x1400177ec  xor     rax, rsp
0x1400177ef  mov     [rsp+1D8h+var_48], rax
0x1400177f7  mov     r14, r8
0x1400177fa  mov     [rsp+1D8h+var_C8], r8
0x140017802  mov     r15, rdx
0x140017805  mov     rdi, rcx
0x140017808  mov     [r11-0F0h], rcx
0x14001780f  mov     [r11-0D0h], rdx
0x140017816  xor     r13d, r13d
0x140017819  mov     [r11-128h], r13
0x140017820  mov     [r11-150h], r13
0x140017827  mov     [rsp+1D8h+P], r13; P
0x14001782c  mov     [r11-130h], r13
0x140017833  mov     qword ptr [rsp+1D8h+FileOffset], r13
0x140017838  xorps   xmm0, xmm0
0x14001783b  xor     eax, eax
0x14001783d  movups  xmmword ptr [r11-78h], xmm0
0x140017842  mov     [r11-68h], rax
0x140017846  mov     byte ptr [rsp+1D8h+var_178], al; int
0x14001784a  movups  xmmword ptr [r11-60h], xmm0
0x14001784f  mov     [r11-50h], rax
0x140017853  mov     dword ptr [rsp+1D8h+var_188], r13d
0x140017858  mov     ebx, r13d
0x14001785b  mov     rcx, rdx
0x14001785e  call    cs:__imp_IoIrpHasFsTrackOffsetExtensionType
0x140017865  nop     dword ptr [rax+rax+00h]
0x14001786a  test    al, al
0x14001786c  jz      short loc_14001787D
0x14001786e  mov     rcx, r15
0x140017871  call    cs:__imp_IoClearFsTrackOffsetState
0x140017878  nop     dword ptr [rax+rax+00h]
0x14001787d  mov     rax, [r15+0B8h]
0x140017884  mov     qword ptr [rsp+1D8h+var_110], rax; int
0x14001788c  mov     r12, [rax+30h]
0x140017890  mov     [rsp+1D8h+FileObject], r12; int
0x140017898  mov     [rsp+1D8h+var_1A8], 1
0x14001789d  lea     rax, [rsp+1D8h+var_130]
0x1400178a5  mov     qword ptr [rsp+1D8h+Retrying], rax
0x1400178aa  lea     rax, [rsp+1D8h+P]
0x1400178af  mov     qword ptr [rsp+1D8h+BytesToWrite], rax
0x1400178b4  lea     r9, [rsp+1D8h+var_150]
0x1400178bc  lea     r8, [rsp+1D8h+var_128]
0x1400178c4  mov     rdx, r12
0x1400178c7  mov     rcx, rdi
0x1400178ca  call    NtfsDecodeFileObject
0x1400178cf  mov     r8d, eax
0x1400178d2  mov     [rsp+1D8h+var_11C], eax
0x1400178d9  lea     ecx, [rax-2]
0x1400178dc  test    ecx, 0FFFFFFFCh
0x1400178e2  jnz     loc_14001BD67
0x1400178e8  cmp     eax, 3
0x1400178eb  jz      loc_14001BD67
0x1400178f1  mov     rdx, [rdi+90h]
0x1400178f8  mov     esi, [rdx+18h]
0x1400178fb  mov     rcx, [rsp+1D8h+P]
0x140017900  test    esi, esi
0x140017902  jns     loc_140017A77
0x140017908  test    dword ptr [rcx+0C8h], 2000h
0x140017912  jnz     loc_140017A77
0x140017918  mov     rax, [rsp+1D8h+var_128]
0x140017920  cmp     rcx, [rax+40h]
0x140017924  jz      loc_140017A77
0x14001792a  mov     eax, [rdx+1B4h]
0x140017930  test    al, al
0x140017932  js      loc_140017A77
0x140017938  test    dword ptr [rdx+4], 1000000h
0x14001793f  movzx   eax, cs:NtfsStatusDebugFlags
0x140017946  jz      short loc_1400179AB
0x140017948  test    al, al
0x14001794a  jz      short loc_140017984
0x14001794c  cmp     esi, 0FFFFFFEDh
0x14001794f  jnb     short loc_140017984
0x140017951  cmp     esi, 0C0000016h
0x140017957  jz      short loc_140017984
0x140017959  lea     eax, [rsi+7FFFFFFBh]
0x14001795f  cmp     eax, 1
0x140017962  jbe     short loc_140017984
0x140017964  cmp     esi, 0C0000011h
0x14001796a  jz      short loc_140017984
0x14001796c  cmp     esi, 0C00000D8h
0x140017972  jz      short loc_140017984
0x140017974  mov     r8d, 2604BEh
0x14001797a  mov     edx, esi
0x14001797c  mov     rcx, rdi
0x14001797f  call    NtfsStatusTraceAndDebugInternal
0x140017984  mov     eax, esi
0x140017986  not     eax
0x140017988  shr     eax, 1Fh
0x14001798b  test    r15, r15
0x14001798e  setnz   r9b
0x140017992  mov     [rsp+1D8h+BytesToWrite], eax
0x140017996  mov     r8d, esi
0x140017999  mov     rdx, r15
0x14001799c  mov     rcx, rdi
0x14001799f  call    NtfsExtendedCompleteRequestInternal
0x1400179a4  mov     eax, esi
0x1400179a6  jmp     loc_14001BDC4
0x1400179ab  test    al, al
0x1400179ad  jz      short loc_1400179E6
0x1400179af  cmp     esi, 0FFFFFFEDh
0x1400179b2  jnb     short loc_1400179E6
0x1400179b4  cmp     esi, 0C0000016h
0x1400179ba  jz      short loc_1400179E6
0x1400179bc  lea     eax, [rsi+7FFFFFFBh]
0x1400179c2  cmp     eax, 1
0x1400179c5  jbe     short loc_1400179E6
0x1400179c7  cmp     esi, 0C0000011h
0x1400179cd  jz      short loc_1400179E6
0x1400179cf  cmp     esi, 0C00000D8h
0x1400179d5  jz      short loc_1400179FE
0x1400179d7  mov     r8d, 2604C7h
0x1400179dd  mov     edx, esi
0x1400179df  xor     ecx, ecx
0x1400179e1  call    NtfsStatusTraceAndDebugInternal
0x1400179e6  cmp     esi, 0C00000D8h
0x1400179ec  jz      short loc_1400179FE
0x1400179ee  cmp     esi, 0C0000188h
0x1400179f4  jz      short loc_1400179FE
0x1400179f6  cmp     esi, 0C00001A8h
0x1400179fc  jnz     short loc_140017A1D
0x1400179fe  movzx   eax, cs:NtfsStatusDebugFlags
0x140017a05  mov     esi, 0C0000001h
0x140017a0a  test    al, al
0x140017a0c  jz      short loc_140017A1D
0x140017a0e  mov     r8d, 2604CDh
0x140017a14  mov     edx, esi
0x140017a16  xor     ecx, ecx
0x140017a18  call    NtfsStatusTraceAndDebugInternal
0x140017a1d  movzx   eax, cs:NtfsStatusDebugFlags
0x140017a24  test    al, al
0x140017a26  jz      short loc_140017A60
0x140017a28  cmp     esi, 0FFFFFFEDh
0x140017a2b  jnb     short loc_140017A60
0x140017a2d  cmp     esi, 0C0000016h
0x140017a33  jz      short loc_140017A60
0x140017a35  lea     eax, [rsi+7FFFFFFBh]
0x140017a3b  cmp     eax, 1
0x140017a3e  jbe     short loc_140017A60
0x140017a40  cmp     esi, 0C0000011h
0x140017a46  jz      short loc_140017A60
0x140017a48  cmp     esi, 0C00000D8h
0x140017a4e  jz      short loc_140017A60
0x140017a50  mov     r8d, 2604D0h
0x140017a56  mov     edx, esi
0x140017a58  mov     rcx, rdi
0x140017a5b  call    NtfsStatusTraceAndDebugInternal
0x140017a60  mov     ecx, esi
0x140017a62  not     ecx
0x140017a64  shr     ecx, 1Fh
0x140017a67  test    r15, r15
0x140017a6a  setnz   r9b
0x140017a6e  mov     [rsp+1D8h+BytesToWrite], ecx
0x140017a72  jmp     loc_140017996
0x140017a77  mov     rdx, [rsp+1D8h+var_128]
0x140017a7f  mov     eax, [rdx+4]
0x140017a82  and     eax, 0A000021h
0x140017a87  cmp     eax, 1
0x140017a8a  jz      loc_140017B34
0x140017a90  mov     [r15+38h], r13
0x140017a94  mov     eax, [rdx+4]
0x140017a97  test    al, 20h
0x140017a99  jz      short loc_140017ACC
0x140017a9b  movzx   eax, cs:NtfsStatusDebugFlags
0x140017aa2  mov     esi, 0C0000189h
0x140017aa7  test    al, al
0x140017aa9  jz      short loc_140017ABB
0x140017aab  mov     r8d, 2604F5h
0x140017ab1  mov     edx, esi
0x140017ab3  mov     rcx, rdi
0x140017ab6  call    NtfsStatusTraceAndDebugInternal
0x140017abb  test    r15, r15
0x140017abe  setnz   r9b
0x140017ac2  mov     [rsp+1D8h+BytesToWrite], r13d
0x140017ac7  jmp     loc_140017996
0x140017acc  bt      eax, 1Bh
0x140017ad0  jb      loc_140017B89
0x140017ad6  test    al, 1
0x140017ad8  jnz     short loc_140017AE4
0x140017ada  cmp     r8d, 4
0x140017ade  jnz     loc_140017B89
0x140017ae4  bt      eax, 19h
0x140017ae8  jnb     short loc_140017B2F
0x140017aea  movzx   eax, cs:NtfsStatusDebugFlags
0x140017af1  test    al, al
0x140017af3  jz      short loc_140017B08
0x140017af5  mov     edx, 0C00000A2h
0x140017afa  mov     r8d, 26050Bh
0x140017b00  mov     rcx, rdi
0x140017b03  call    NtfsStatusTraceAndDebugInternal
0x140017b08  test    r15, r15
0x140017b0b  setnz   r9b
0x140017b0f  mov     [rsp+1D8h+BytesToWrite], r13d
0x140017b14  mov     r8d, 0C00000A2h
0x140017b1a  mov     rdx, r15
0x140017b1d  mov     rcx, rdi
0x140017b20  call    NtfsExtendedCompleteRequestInternal
0x140017b25  mov     eax, 0C00000A2h
0x140017b2a  jmp     loc_14001BDC4
0x140017b2f  mov     rcx, [rsp+1D8h+P]
0x140017b34  test    dword ptr [rcx+200h], 1000000h
0x140017b3e  jz      short loc_140017BA8
0x140017b40  mov     [r15+38h], r13
0x140017b44  movzx   eax, cs:NtfsStatusDebugFlags
0x140017b4b  test    al, al
0x140017b4d  jz      short loc_140017B62
0x140017b4f  mov     edx, 0C0000008h
0x140017b54  mov     r8d, 26051Bh
0x140017b5a  mov     rcx, rdi
0x140017b5d  call    NtfsStatusTraceAndDebugInternal
0x140017b62  test    r15, r15
0x140017b65  setnz   r9b
0x140017b69  mov     [rsp+1D8h+BytesToWrite], r13d
0x140017b6e  mov     r8d, 0C0000008h
0x140017b74  mov     rdx, r15
0x140017b77  mov     rcx, rdi
0x140017b7a  call    NtfsExtendedCompleteRequestInternal
0x140017b7f  mov     eax, 0C0000008h
0x140017b84  jmp     loc_14001BDC4
0x140017b89  movzx   eax, cs:NtfsStatusDebugFlags
0x140017b90  mov     esi, 0C000026Eh
0x140017b95  test    al, al
0x140017b97  jz      loc_140017ABB
0x140017b9d  mov     r8d, 260501h
0x140017ba3  jmp     loc_140017AB1
0x140017ba8  movzx   ecx, byte ptr [rdi+0Ch]
0x140017bac  and     cl, 1
0x140017baf  movzx   eax, byte ptr [rsp+1D8h+var_188+2]
0x140017bb4  and     al, 0FEh
0x140017bb6  or      cl, al
0x140017bb8  mov     byte ptr [rsp+1D8h+var_188+2], cl
0x140017bbc  mov     edx, [r15+10h]
0x140017bc0  mov     ecx, edx
0x140017bc2  shr     ecx, 1
0x140017bc4  and     cl, 1
0x140017bc7  movzx   eax, byte ptr [rsp+1D8h+var_188+1]
0x140017bcc  and     al, 0FEh
0x140017bce  or      cl, al
0x140017bd0  mov     byte ptr [rsp+1D8h+var_188+1], cl
0x140017bd4  and     dl, 1
0x140017bd7  add     dl, dl
0x140017bd9  movzx   eax, byte ptr [rsp+1D8h+var_188]
0x140017bde  and     al, 0FDh
0x140017be0  or      dl, al
0x140017be2  mov     byte ptr [rsp+1D8h+var_188], dl
0x140017be6  mov     ecx, [r12+50h]
0x140017beb  and     cl, 2
0x140017bee  shl     cl, 4
0x140017bf1  movzx   eax, byte ptr [rsp+1D8h+var_188+1]
0x140017bf6  and     al, 0DFh
0x140017bf8  or      cl, al
0x140017bfa  mov     byte ptr [rsp+1D8h+var_188+1], cl
0x140017bfe  cmp     rdi, [rdi+90h]
0x140017c05  jnz     short loc_140017C1B
0x140017c07  call    cs:__imp_IoGetTopLevelIrp
0x140017c0e  nop     dword ptr [rax+rax+00h]
0x140017c13  cmp     [rax], bl
0x140017c15  jz      short loc_140017C1B
0x140017c17  mov     cl, 8
0x140017c19  jmp     short loc_140017C1D
0x140017c1b  xor     cl, cl
0x140017c1d  movzx   eax, byte ptr [rsp+1D8h+var_188]
0x140017c22  and     al, 0F7h
0x140017c24  or      al, cl
0x140017c26  mov     byte ptr [rsp+1D8h+var_188], al
0x140017c2a  mov     rdx, [rsp+1D8h+P]
0x140017c2f  test    al, 2
0x140017c31  jz      short loc_140017CAA
0x140017c33  test    dword ptr [rdx+0C8h], 1000000h
0x140017c3d  jz      short loc_140017CAA
0x140017c3f  mov     rax, [rdi+90h]
0x140017c46  cmp     byte ptr [rax+20h], 0Dh
0x140017c4a  jnz     short loc_140017C65
0x140017c4c  mov     rax, [rax+70h]
0x140017c50  test    rax, rax
0x140017c53  jz      short loc_140017C65
0x140017c55  mov     rax, [rax+0B8h]
0x140017c5c  cmp     dword ptr [rax+18h], 900DFh
0x140017c63  jz      short loc_140017CAA
0x140017c65  movzx   eax, cs:NtfsStatusDebugFlags
0x140017c6c  test    al, al
0x140017c6e  jz      short loc_140017C83
0x140017c70  mov     edx, 0C0000810h
0x140017c75  mov     r8d, 260545h
0x140017c7b  mov     rcx, rdi
0x140017c7e  call    NtfsStatusTraceAndDebugInternal
0x140017c83  test    r15, r15
0x140017c86  setnz   r9b
0x140017c8a  mov     [rsp+1D8h+BytesToWrite], r13d
0x140017c8f  mov     r8d, 0C0000810h
0x140017c95  mov     rdx, r15
  ... truncated ...
```
