# RefsCommonWrite

- ea: `0x1c000a190`
- end: `0x1c000ceb8`
- name: `RefsCommonWrite`
- size: `11560`
- prototype: `__int64 __fastcall(PVOID Context1, PVOID Context2)`
- caller_count: `3`
- callee_count: `52`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1c0008060`
- `0x1c00098f0`
- `0x1c00aacb0`

## callees

- `0x1c0001268`
- `0x1c0003334`
- `0x1c0004300`
- `0x1c0004a30`
- `0x1c00057a8`
- `0x1c0005818`
- `0x1c000a190`
- `0x1c000f770`
- `0x1c0013f90`
- `0x1c003b27c`
- `0x1c004d164`
- `0x1c00583d0`
- `0x1c00595d0`
- `0x1c005c580`
- `0x1c005f020`
- `0x1c0062928`
- `0x1c0063db0`
- `0x1c0068168`
- `0x1c0068960`
- `0x1c009166c`
- `0x1c0091864`
- `0x1c00921c8`
- `0x1c00925e8`
- `0x1c009263c`
- `0x1c009294c`
- `0x1c0097cc8`
- `0x1c009871c`
- `0x1c009eeb0`
- `0x1c009eee8`
- `0x1c009f298`
- `0x1c00a0534`
- `0x1c00a29c4`
- `0x1c00a7df8`
- `0x1c00aa988`
- `0x1c00aab1c`
- `0x1c00aae9c`
- `0x1c00ab0cc`
- `0x1c00ab184`
- `0x1c00ab2d4`
- `0x1c00ab338`
- `0x1c00adb9c`
- `0x1c014fe2c`
- `0x1c015ac58`
- `0x1c01632d4`
- `0x1c0163360`
- `0x1c01634c8`
- `0x1c01635d0`
- `0x1c0163640`
- `0x1c01636b0`
- `0x1c01639a0`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x1c000bc6e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c000c496`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c000bc6e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c000c496`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x1c000be81`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x1c000be81`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c000b30b`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c000b905`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c006b978`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c007101b`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c000b30b`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c000b905`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c006b978`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c007101b`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c000b3b1`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c000b443`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c000b52d`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c000b9cd`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c000bada`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c000bb7d`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c006ba2a`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c00710e3`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c000b3b1`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c000b443`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c000b52d`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c000b9cd`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c000bada`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c000bb7d`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c006ba2a`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c00710e3`
- `ntoskrnl!CcFlushCache` at `0x1c000cbec`
- `ntoskrnl!CcFlushCache` at `0x1c000cbec`
- `ntoskrnl!CcPrepareMdlWrite` at `0x1c000cb8b`
- `ntoskrnl!CcPrepareMdlWrite` at `0x1c000cb8b`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x1c000c75f`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x1c000c75f`
- `ntoskrnl!FsRtlCheckOplock` at `0x1c000aa37`
- `ntoskrnl!FsRtlCheckOplock` at `0x1c000aa37`
- `ntoskrnl!FsRtlCheckLockForWriteAccess` at `0x1c000beef`
- `ntoskrnl!FsRtlCheckLockForWriteAccess` at `0x1c000beef`
- `ntoskrnl!CcUninitializeCacheMap` at `0x1c000b18c`
- `ntoskrnl!CcUninitializeCacheMap` at `0x1c000b18c`
- `ntoskrnl!CcSetParallelFlushFile` at `0x1c000c88e`
- `ntoskrnl!CcSetParallelFlushFile` at `0x1c000c88e`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c000a401`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c000b57a`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c000b5ca`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c000b88c`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c000bd0a`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c00709f9`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c000a401`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c000b57a`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c000b5ca`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c000b88c`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c000bd0a`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c00709f9`
- `ntoskrnl!ExRaiseStatus` at `0x1c000c76d`
- `ntoskrnl!ExRaiseStatus` at `0x1c000c76d`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1c000c47f`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1c000c47f`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1c000a9ec`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1c000a9ec`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1c000a9ba`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1c000c635`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1c000a9ba`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1c000c635`
- `ntoskrnl!CcCopyWrite` at `0x1c000ca5c`
- `ntoskrnl!CcCopyWrite` at `0x1c000ca5c`
- `ntoskrnl!CcCanIWrite` at `0x1c0070cbc`
- `ntoskrnl!CcCanIWrite` at `0x1c0070cbc`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1c000b59b`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1c000b614`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1c000b59b`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1c000b614`
- `ntoskrnl!CcSetReadAheadGranularity` at `0x1c000c87d`
- `ntoskrnl!CcSetReadAheadGranularity` at `0x1c000c87d`
- `ntoskrnl!CcDeferWrite` at `0x1c0070d33`
- `ntoskrnl!CcDeferWrite` at `0x1c0070d33`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x1c000ac69`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x1c000bde9`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x1c000ac69`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x1c000bde9`
- `ntoskrnl!ExIsFastResourceHeld` at `0x1c000ac81`
- `ntoskrnl!ExIsFastResourceHeld` at `0x1c000b5ba`
- `ntoskrnl!ExIsFastResourceHeld` at `0x1c000b5f4`
- `ntoskrnl!ExIsFastResourceHeld` at `0x1c000be01`
- `ntoskrnl!ExIsFastResourceHeld` at `0x1c000ac81`
- `ntoskrnl!ExIsFastResourceHeld` at `0x1c000b5ba`
- `ntoskrnl!ExIsFastResourceHeld` at `0x1c000b5f4`
- `ntoskrnl!ExIsFastResourceHeld` at `0x1c000be01`
- `HAL!KeQueryPerformanceCounter` at `0x1c000a52f`
- `HAL!KeQueryPerformanceCounter` at `0x1c0070cfb`
- `HAL!KeQueryPerformanceCounter` at `0x1c000a52f`
- `HAL!KeQueryPerformanceCounter` at `0x1c0070cfb`

## string_xrefs

- `0x1c000ade3`: `write.c`
- `0x1c000ae72`: `write.c`
- `0x1c000ae8c`: `write.c`
- `0x1c000afee`: `write.c`
- `0x1c000b1f3`: `write.c`
- `0x1c000b264`: `write.c`
- `0x1c000b2ea`: `write.c`
- `0x1c000b791`: `write.c`
- `0x1c000b828`: `write.c`
- `0x1c000bdbc`: `write.c`
- `0x1c000c155`: `write.c`
- `0x1c000c297`: `write.c`
- `0x1c000c74a`: `write.c`
- `0x1c000c84a`: `write.c`
- `0x1c000c930`: `write.c`
- `0x1c000c9fd`: `write.c`
- `0x1c000caba`: `write.c`
- `0x1c000cb2e`: `write.c`
- `0x1c000cc49`: `write.c`
- `0x1c000ccc3`: `write.c`
- `0x1c007065a`: `write.c`
- `0x1c00706e2`: `write.c`
- `0x1c0070760`: `write.c`
- `0x1c00707d3`: `write.c`
- `0x1c0070957`: `write.c`
- `0x1c00709d1`: `write.c`
- `0x1c0070da3`: `write.c`
- `0x1c00711c0`: `write.c`

## pseudocode

```c
__int64 __fastcall RefsCommonWrite(LARGE_INTEGER *Context1, IRP *Context2)
{
  PIRP v2; // r13
  LARGE_INTEGER *v3; // r15
  ULONG_PTR Information; // rbx
  __int64 v5; // rdi
  ULONG_PTR v6; // rdx
  PFILE_OBJECT v7; // r9
  __int64 FsContext; // rax
  union _LARGE_INTEGER *v9; // r14
  __int64 FsContext2; // rcx
  int v11; // eax
  int v12; // r8d
  int v13; // esi
  ULONG Flags; // ecx
  char v15; // dl
  char v16; // cl
  char v17; // si
  volatile signed __int32 *Flags_low; // r12
  char v19; // al
  unsigned __int8 v20; // si
  _DWORD *v21; // r11
  LARGE_INTEGER *v22; // rdx
  union _LARGE_INTEGER *v23; // r8
  union _LARGE_INTEGER v24; // rcx
  ULONG LowPart; // r10d
  __int64 v26; // r8
  char v27; // dl
  bool v28; // r9
  LARGE_INTEGER PerformanceCounter; // rax
  char v30; // al
  int v31; // edx
  __int64 v32; // r8
  bool v33; // di
  union _LARGE_INTEGER *v34; // rcx
  __int64 v35; // rcx
  int v36; // r9d
  int v37; // eax
  _QWORD *v38; // rdx
  DWORD v39; // eax
  NTSTATUS v40; // edi
  char v41; // al
  char v42; // di
  union _LARGE_INTEGER *v43; // rsi
  union _LARGE_INTEGER v44; // rdx
  LARGE_INTEGER v45; // rcx
  int v46; // eax
  union _LARGE_INTEGER *v47; // rdi
  __int64 v48; // rdx
  __int64 v49; // rcx
  __int64 v50; // rax
  LARGE_INTEGER **v51; // rax
  LARGE_INTEGER *v52; // rax
  NTSTATUS v53; // eax
  unsigned int Status; // edi
  FILE_LOCK *v55; // rcx
  __int64 v56; // r8
  __int64 v57; // r9
  int v58; // ecx
  int v59; // edi
  ULONG v60; // r8d
  union _LARGE_INTEGER v61; // rdx
  union _LARGE_INTEGER v62; // rcx
  PDEVICE_OBJECT v63; // rcx
  int v64; // ebx
  char v65; // si
  char v66; // al
  LARGE_INTEGER v67; // rcx
  __int64 v68; // rax
  __int64 v69; // rax
  int v70; // ecx
  union _LARGE_INTEGER v71; // rax
  DWORD v72; // r9d
  __int64 v73; // rcx
  union _LARGE_INTEGER v74; // rax
  LONGLONG v75; // rdi
  LARGE_INTEGER *v76; // rdx
  union _LARGE_INTEGER *v77; // rcx
  char v78; // al
  union _LARGE_INTEGER *v79; // r13
  LARGE_INTEGER v80; // rax
  union _LARGE_INTEGER *v81; // rsi
  DWORD v82; // eax
  NTSTATUS v83; // edi
  ULONG v84; // ecx
  int v85; // eax
  char v86; // r12
  __int64 v87; // r8
  int v88; // ecx
  union _LARGE_INTEGER *v89; // r15
  union _LARGE_INTEGER *v90; // rsi
  union _LARGE_INTEGER v91; // rdx
  LONGLONG v92; // rdi
  unsigned __int64 v93; // rcx
  union _LARGE_INTEGER v94; // rdi
  union _LARGE_INTEGER v95; // r10
  union _LARGE_INTEGER v96; // r8
  DWORD v97; // r9d
  union _LARGE_INTEGER v98; // rax
  __int64 v99; // rax
  int v100; // r9d
  __int64 v101; // r10
  __int64 v102; // r8
  char v103; // r12
  struct _ERESOURCE *v104; // rcx
  union _LARGE_INTEGER v105; // rax
  int v106; // edx
  char v107; // al
  _DWORD *v108; // r10
  __int64 v109; // r9
  __int64 v110; // r8
  LONGLONG v111; // rdx
  __int64 v112; // r8
  __int64 v113; // rdi
  int v114; // r9d
  int *v115; // rdi
  int v116; // edx
  int v117; // r8d
  union _LARGE_INTEGER v118; // rcx
  __int64 v119; // rcx
  char v120; // al
  PSECTION_OBJECT_POINTERS v121; // rax
  _QWORD *v122; // rax
  __int64 v123; // rax
  int v124; // eax
  ULONG_PTR v125; // rdi
  LONG v126; // eax
  LARGE_INTEGER *v127; // rdx
  int v128; // r8d
  char v129; // r12
  DWORD v130; // eax
  char v131; // r12
  DWORD v132; // eax
  ULONG v133; // eax
  NTSTATUS v134; // ebx
  NTSTATUS v135; // eax
  struct _FILE_OBJECT *v136; // rdi
  LARGE_INTEGER *v137; // rcx
  __int64 v138; // r9
  __int64 v139; // r9
  int v141; // eax
  int v142; // eax
  __int64 v143; // rcx
  unsigned int v144; // ebx
  const char *v145; // r11
  const char *v146; // r10
  const char *v147; // r9
  const char *v148; // r8
  const char *v149; // rdx
  const char *QuadPart; // rax
  ULONG v151; // eax
  int v152; // ebx
  __int64 v153; // rcx
  LARGE_INTEGER v154; // rcx
  __int64 v155; // rax
  LARGE_INTEGER v156; // rcx
  _DWORD *v157; // rcx
  int v158; // eax
  __int64 v159; // rcx
  char v160; // di
  union _LARGE_INTEGER *v161; // rsi
  int v162; // edx
  _DWORD *v163; // rbx
  __int64 HighestPendingFileSize; // rax
  PSECTION_OBJECT_POINTERS SectionObjectPointer; // rcx
  _QWORD *SharedCacheMap; // rcx
  int v167; // eax
  signed __int32 v168[8]; // [rsp+88h] [rbp-2C8h] BYREF
  BOOLEAN Retrying[8]; // [rsp+B0h] [rbp-2A0h]
  __int64 v170; // [rsp+B8h] [rbp-298h]
  __int64 v171; // [rsp+C0h] [rbp-290h]
  int v172; // [rsp+F8h] [rbp-258h] BYREF
  _BYTE v173[4]; // [rsp+FCh] [rbp-254h] BYREF
  NTSTATUS Exception; // [rsp+100h] [rbp-250h]
  unsigned __int8 v175; // [rsp+104h] [rbp-24Ch]
  PVOID Context; // [rsp+108h] [rbp-248h]
  char v177; // [rsp+110h] [rbp-240h]
  int v178[2]; // [rsp+118h] [rbp-238h]
  PIRP Irp; // [rsp+120h] [rbp-230h]
  char v180; // [rsp+128h] [rbp-228h]
  char v181; // [rsp+129h] [rbp-227h]
  char v182; // [rsp+12Ah] [rbp-226h]
  char v183[5]; // [rsp+12Bh] [rbp-225h] BYREF
  PFILE_OBJECT FileObject; // [rsp+130h] [rbp-220h]
  int v185; // [rsp+138h] [rbp-218h]
  LARGE_INTEGER *v186; // [rsp+140h] [rbp-210h]
  __int64 v187; // [rsp+148h] [rbp-208h]
  union _LARGE_INTEGER v188; // [rsp+150h] [rbp-200h]
  _QWORD v189[2]; // [rsp+158h] [rbp-1F8h] BYREF
  union _LARGE_INTEGER FileOffset[2]; // [rsp+168h] [rbp-1E8h] BYREF
  __int64 Length; // [rsp+178h] [rbp-1D8h]
  LONGLONG v192; // [rsp+180h] [rbp-1D0h]
  ULONG v193; // [rsp+188h] [rbp-1C8h]
  __int64 v194; // [rsp+190h] [rbp-1C0h]
  ULONG v195; // [rsp+198h] [rbp-1B8h]
  int HighPart; // [rsp+19Ch] [rbp-1B4h]
  unsigned int v197; // [rsp+1A0h] [rbp-1B0h]
  int v198; // [rsp+1A4h] [rbp-1ACh]
  _DWORD *v199; // [rsp+1A8h] [rbp-1A8h]
  ULONG_PTR v200; // [rsp+1B0h] [rbp-1A0h]
  struct _IO_STACK_LOCATION *CurrentStackLocation; // [rsp+1B8h] [rbp-198h]
  int v202; // [rsp+1C0h] [rbp-190h]
  __int64 v203; // [rsp+1C8h] [rbp-188h]
  PDEVICE_OBJECT v204; // [rsp+1D0h] [rbp-180h]
  __int64 v205; // [rsp+1D8h] [rbp-178h]
  __int64 v206; // [rsp+1E0h] [rbp-170h]
  union _LARGE_INTEGER v207; // [rsp+1E8h] [rbp-168h]
  union _LARGE_INTEGER *v208; // [rsp+1F0h] [rbp-160h]
  _DWORD *v209; // [rsp+1F8h] [rbp-158h]
  __int64 v210; // [rsp+200h] [rbp-150h]
  __int64 v211; // [rsp+208h] [rbp-148h]
  IRP *v212; // [rsp+210h] [rbp-140h]
  PFILE_OBJECT v213; // [rsp+218h] [rbp-138h]
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+220h] [rbp-130h] BYREF
  _OWORD v215[4]; // [rsp+238h] [rbp-118h] BYREF
  __int128 v216; // [rsp+278h] [rbp-D8h]
  __int64 v217; // [rsp+288h] [rbp-C8h]
  _QWORD v218[2]; // [rsp+298h] [rbp-B8h] BYREF
  ULONG_PTR v219[2]; // [rsp+2A8h] [rbp-A8h] BYREF
  _QWORD v220[2]; // [rsp+2B8h] [rbp-98h] BYREF
  __int128 v221; // [rsp+2C8h] [rbp-88h] BYREF
  __int64 v222; // [rsp+2D8h] [rbp-78h]
  __int64 v223; // [rsp+2E0h] [rbp-70h]
  struct _KTHREAD *CurrentThread; // [rsp+2E8h] [rbp-68h]
  PVOID v225; // [rsp+2F0h] [rbp-60h]
  __int64 v226; // [rsp+2F8h] [rbp-58h]
  LONGLONG v227; // [rsp+300h] [rbp-50h]
  __int128 v228; // [rsp+308h] [rbp-48h] BYREF
  union _LARGE_INTEGER v229; // [rsp+318h] [rbp-38h]

  v2 = Context2;
  v3 = Context1;
  Context = Context1;
  Irp = Context2;
  v212 = Context2;
  Information = 0;
  v5 = 0;
  v194 = 0;
  v6 = 0;
  v200 = 0;
  *(_OWORD *)&FileOffset[0].LowPart = 0;
  Length = 0;
  v195 = 0;
  v202 = 0;
  v197 = 0;
  v173[0] = 0;
  v177 = 0;
  memset(v215, 0, sizeof(v215));
  v216 = 0;
  v217 = 0;
  v172 = 0;
  v189[1] = v189;
  v189[0] = v189;
  CurrentStackLocation = v2->Tail.Overlay.CurrentStackLocation;
  v218[1] = CurrentStackLocation;
  v7 = CurrentStackLocation->FileObject;
  FileObject = v7;
  v213 = v7;
  FsContext = (__int64)v7->FsContext;
  v210 = FsContext;
  v9 = (union _LARGE_INTEGER *)FsContext;
  *(_QWORD *)v178 = FsContext;
  v205 = FsContext;
  v211 = FsContext;
  if ( FsContext )
  {
    v5 = *(_QWORD *)(FsContext + 128);
    v194 = v5;
    FsContext2 = (__int64)v7->FsContext2;
    v187 = FsContext2;
    v199 = (_DWORD *)FsContext2;
    v6 = *(_QWORD *)(FsContext + 120);
    v200 = v6;
    v11 = *(_DWORD *)(v5 + 4);
    if ( (v11 & 1) == 0 && (!FsContext2 || *(_BYTE *)(FsContext2 + 80) != 4 || (v11 & 2) == 0) )
    {
      RefsRaiseStatusInternal(v3, 3221226094LL);
      __debugbreak();
    }
    v198 = 1;
    if ( FsContext2 )
      v12 = *(unsigned __int8 *)(FsContext2 + 80);
    else
      v12 = 5;
  }
  else
  {
    v187 = 0;
    v199 = 0;
    v198 = 1;
    v12 = 1;
  }
  v185 = v12;
  v206 = v5;
  if ( ((v12 - 2) & 0xFFFFFFFC) != 0 || v12 == 3 || *(_QWORD *)(v6 + 16) == 1312 && *(_QWORD *)(v6 + 8) == 1024 )
  {
    RefsCompleteWriteRequest(v3, v2, 3221225488LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids, 3221225488LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741808);
    return 3221225488LL;
  }
  v192 = (LONGLONG)&v3[13];
  v13 = *(_DWORD *)(v3[13].QuadPart + 16);
  if ( v13 < 0 && (v9[17].LowPart & 0x2000) == 0 )
  {
    Exception = *(_DWORD *)(v3[13].QuadPart + 16);
    if ( v13 == -1073741608 || v13 == -1073741432 || v13 == -1073741400 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v13 = -1073741823;
      }
      else
      {
        v13 = -1073741823;
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids, 3221225473LL);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741823);
      Exception = -1073741823;
      v3 = (LARGE_INTEGER *)Context;
      v2 = Irp;
    }
    RefsCompleteWriteRequest(v3, v2, (unsigned int)v13);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        16,
        WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids,
        (unsigned int)v13);
    }
    v144 = Exception;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(Exception);
    return v144;
  }
  v209 = (_DWORD *)(v5 + 4);
  if ( (*(_DWORD *)(v5 + 4) & 0xA000021) == 1 )
    goto LABEL_10;
  v2->IoStatus.Information = 0;
  v141 = *(_DWORD *)(v5 + 4);
  if ( (v141 & 0x20) != 0 )
  {
    Status = -1073741431;
    RefsCompleteWriteRequest(v3, v2, 3221225865LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids, 3221225865LL);
    }
    if ( !RefsStatusDebugEnabled )
      return Status;
LABEL_618:
    RefsStatusDebug(Status);
    return Status;
  }
  if ( (v141 & 0x8000000) != 0 || (v141 & 1) == 0 && v12 != 4 )
  {
    Status = -1073741202;
    RefsCompleteWriteRequest(v3, v2, 3221226094LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids, 3221226094LL);
    }
    if ( !RefsStatusDebugEnabled )
      return Status;
    goto LABEL_618;
  }
  if ( (v141 & 0x2000000) != 0 )
  {
    RefsCompleteWriteRequest(v3, v2, 3221225634LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids, 3221225634LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741662);
    return 3221225634LL;
  }
LABEL_10:
  v208 = v9 + 38;
  if ( (v9[38].LowPart & 0x1000000) != 0 )
  {
    v2->IoStatus.Information = 0;
    Status = -1073741816;
    RefsCompleteWriteRequest(v3, v2, 3221225480LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids, 3221225480LL);
    }
    if ( !RefsStatusDebugEnabled )
      return Status;
    goto LABEL_618;
  }
  v186 = v3 + 1;
  Flags = v2->Flags;
  if ( (Flags & 2) != 0 )
    v15 = 32;
  else
    v15 = 0;
  if ( (Flags & 1) != 0 )
    v16 = 4;
  else
    v16 = 0;
  v17 = v16 | v15 & 0xFB | v172 & 0xDB;
  Flags_low = (volatile signed __int32 *)LOBYTE(v7->Flags);
  LOBYTE(Flags_low) = ((v3[1].LowPart & 1) << 6) | (4 * ((unsigned __int8)Flags_low & 2));
  BYTE1(v172) = (_BYTE)Flags_low;
  if ( v3 == (LARGE_INTEGER *)v3[13].QuadPart && LOBYTE(IoGetTopLevelIrp()->Type) )
    v19 = 8;
  else
    v19 = 0;
  v20 = v19 | v17 & 0xF7;
  LOBYTE(v172) = v20;
  v21 = (_DWORD *)v187;
  if ( v187 && (*(_DWORD *)(v187 + 4) & 0x2000) != 0 && (v20 & 0x20) == 0 )
  {
    Status = -1073741811;
    RefsCompleteWriteRequest(v3, v2, 3221225485LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids, 3221225485LL);
    }
    if ( !RefsStatusDebugEnabled )
      return Status;
    goto LABEL_618;
  }
  if ( !v9[40].LowPart )
  {
    if ( ((unsigned __int8)Flags_low & 0x40) == 0 && (v20 & 0x20) != 0 )
    {
      if ( *(LARGE_INTEGER **)v192 == v3 )
      {
        if ( IoGetTopLevelIrp()->AssociatedIrp.MasterIrp == (struct _IRP *)3 )
        {
          v22 = v186;
          if ( (v9[31].QuadPart & 0x800000000000LL) != 0 )
          {
            LOBYTE(Flags_low) = (unsigned __int8)Flags_low | 0x40;
            BYTE1(v172) = (_BYTE)Flags_low;
            v186->LowPart |= 1u;
          }
          v21 = (_DWORD *)v187;
LABEL_24:
          v23 = (union _LARGE_INTEGER *)CurrentStackLocation;
          if ( (v22->LowPart & 0x20000) != 0
            && v9[4].QuadPart < CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart
                              + CurrentStackLocation->Parameters.Read.Length )
          {
            v22->LowPart &= ~0x20000u;
            v23[3].QuadPart = -1;
          }
          v24 = v23[3];
          v188 = v24;
          FileOffset[0] = v24;
          LowPart = v23[1].LowPart;
          v193 = LowPart;
          LODWORD(Length) = LowPart;
          v204 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v145 = "EXT";
            if ( v24.QuadPart >= 0 )
              v145 = "NEXT";
            v146 = "TL";
            if ( (v20 & 8) == 0 )
              v146 = "NTL";
            v147 = "SYNC";
            if ( ((unsigned __int8)Flags_low & 8) == 0 )
              v147 = "ASYNC";
            v148 = "C";
            if ( (v20 & 4) == 0 )
              v148 = "NC";
            v149 = "P";
            if ( (v20 & 0x20) == 0 )
              v149 = "NP";
            v188.QuadPart = (LONGLONG)"NWAIT";
            QuadPart = "WAIT";
            if ( ((unsigned __int8)Flags_low & 0x40) == 0 )
              QuadPart = (const char *)v188.QuadPart;
            WPP_SF_qiDqssssss(
              v204->AttachedDevice,
              (_DWORD)v149,
              (_DWORD)v148,
              (_DWORD)v9,
              v24.QuadPart,
              v193,
              (char)v2,
              (__int64)QuadPart,
              (__int64)v149,
              (__int64)v148,
              (__int64)v147,
              (__int64)v146,
              (__int64)v145);
            LowPart = Length;
            v24 = FileOffset[0];
            v188 = FileOffset[0];
            v21 = (_DWORD *)v187;
          }
          if ( 0x7FFFFFFFFFFFFFFFLL - v24.QuadPart < LowPart && v24.QuadPart >= 0 )
          {
            Status = -1073741811;
            RefsCompleteWriteRequest(v3, v2, 3221225485LL);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_D(
                WPP_GLOBAL_Control->AttachedDevice,
                24,
                WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids,
                3221225485LL);
            }
            if ( !RefsStatusDebugEnabled )
              return Status;
            goto LABEL_618;
          }
          v26 = LowPart + v24.QuadPart;
          FileOffset[1].QuadPart = v26;
          if ( LowPart )
          {
            v27 = v20 >> 2;
            v180 = v20 >> 2;
            v28 = (v20 & 4) != 0;
            v175 = v28;
            if ( (v20 & 4) == 0 )
            {
              v151 = v186->LowPart;
              v193 = v151;
              if ( (v151 & 8) == 0 )
              {
                if ( !CcCanIWrite(FileObject, LowPart, (v151 & 0x41) == 1, (v3->HighPart & 8) != 0) )
                {
                  v152 = v3->HighPart & 8;
                  RefsPrePostIrp(v3, v2);
                  v3->HighPart |= 8u;
                  if ( !v152 && *(_QWORD *)(v5 + 3944) )
                    v3[31] = KeQueryPerformanceCounter(0);
                  CcDeferWrite(FileObject, RefsAddToWorkque, v3, v2, Length, v152 != 0);
                  if ( (v20 & 0x40) != 0 )
                    RefsReleasePagingFastResource(v153, v9, v215);
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                  {
                    WPP_SF_D(
                      WPP_GLOBAL_Control->AttachedDevice,
                      25,
                      WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids,
                      259);
                  }
                  if ( RefsStatusDebugEnabled )
                    RefsStatusDebug(259);
                  return 259;
                }
                LowPart = Length;
                v26 = FileOffset[1].QuadPart;
                v24 = FileOffset[0];
                v188 = FileOffset[0];
                v27 = v180;
                v21 = (_DWORD *)v187;
                v28 = v175;
              }
            }
            if ( *(_QWORD *)(v5 + 3944) )
            {
              if ( (v3->HighPart & 8) == 0 || (PerformanceCounter = v3[31], PerformanceCounter.QuadPart <= 20) )
              {
                PerformanceCounter = KeQueryPerformanceCounter(0);
                v27 = v180;
                v21 = (_DWORD *)v187;
                v28 = v175;
              }
              *(LARGE_INTEGER *)(v3[18].QuadPart + 288) = PerformanceCounter;
              v193 = 0;
              v30 = 0;
              if ( (v20 & 0x24) == 0 )
                v30 = 4;
              HIBYTE(v193) = v27 & 8 | (((unsigned __int8)Flags_low & 0x40) != 0) | v30 | (v186->LowPart >> 2) & 2;
              *(_DWORD *)v3[18].QuadPart |= v193;
              LowPart = Length;
              v26 = FileOffset[1].QuadPart;
              v24 = FileOffset[0];
              v188 = FileOffset[0];
            }
            v31 = v185;
            if ( v185 != 4 )
            {
              v32 = v20;
              LOBYTE(v32) = (v20 & 0x20) != 0;
              if ( (v20 & 0x20) != 0 )
              {
                v157 = (_DWORD *)(*(_QWORD *)(v194 + 680)
                                + ((unsigned __int64)(KeGetCurrentProcessorNumber() % (unsigned int)RefsNumberProcessors) << 6));
                v9 = *(union _LARGE_INTEGER **)v178;
                if ( (*(_DWORD *)(v200 + 4) & 0x100) == 0
                  && ((v158 = *(_DWORD *)(*(_QWORD *)v178 + 200LL), v158 == 128) || v158 == 176) )
                {
                  ++v157[5];
                  v157[6] += Length;
                }
                else
                {
                  ++v157[11];
                  v157[12] += Length;
                }
                v24 = FileOffset[0];
                v21 = v199;
                v31 = v185;
                v2 = Irp;
                v3 = (LARGE_INTEGER *)Context;
                v20 = v172;
                Flags_low = (volatile signed __int32 *)BYTE1(v172);
                v188 = FileOffset[0];
                LowPart = Length;
                v187 = (__int64)v199;
              }
              if ( (v20 & 0x24) != 4 )
              {
                v9[21].LowPart = 0;
                LowPart = Length;
                v24 = FileOffset[0];
                v188 = FileOffset[0];
              }
              Exception = 0;
              *((_QWORD *)&v216 + 1) = 0x100000000LL;
              v217 = 0;
              if ( !(_BYTE)v32 )
              {
                if ( v21 )
                {
                  v3[25].LowPart = v21[21];
                  LowPart = Length;
                  v24 = FileOffset[0];
                  v188 = FileOffset[0];
                }
                if ( (v20 & 0x40) != 0 )
                  goto LABEL_147;
                if ( (v186->LowPart & 0x100) != 0 )
                  goto LABEL_133;
                if ( v31 != 5 )
                {
                  if ( !v28 )
                    goto LABEL_132;
                  if ( FileObject->SectionObjectPointer->DataSectionObject )
                    goto LABEL_133;
                }
                if ( v28 )
                {
LABEL_49:
                  if ( v24.QuadPart >= 0 )
                  {
                    v33 = ((unsigned __int8)Flags_low & 0x40) != 0;
                    v34 = 0;
                    if ( LOWORD(v9->LowPart) == 2050 )
                    {
                      v34 = v9;
                    }
                    else if ( v9[2].QuadPart )
                    {
                      v34 = (union _LARGE_INTEGER *)v9[15].QuadPart;
                    }
                    v20 ^= (v20
                          ^ ((unsigned __int8)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))MsAcquireFastResourceShared)(
                                                (union _LARGE_INTEGER)v34[13].QuadPart,
                                                v215,
                                                v33) << 6))
                         & 0x40;
                    LOBYTE(v172) = v20;
                    v36 = v185;
                    if ( v185 == 5 || (v20 & 4) == 0 || !FileObject->SectionObjectPointer->DataSectionObject )
                    {
                      v35 = v20;
                      if ( (v20 & 4) != 0 || FileObject->SectionObjectPointer->SharedCacheMap )
                        goto LABEL_57;
                    }
                    v175 = v20;
                    if ( (v20 & 0x40) != 0 )
                    {
                      RefsReleasePagingFastResource(v35, v9, v215);
                      v175 = v20 & 0xBF;
                      LOBYTE(v172) = v20 & 0xBF;
                    }
                    v65 = v175
                        ^ (v175
                         ^ ((unsigned __int8)RefsAcquirePagingFastResourceExclusive(v35, v9, v215, v33) << 6))
                        & 0x40;
LABEL_134:
                    v20 = v65 | 0x10;
                    v36 = v185;
                    LOBYTE(v35) = v20;
                    LOBYTE(v172) = v20;
LABEL_57:
                    if ( (v35 & 0x40) != 0 )
                    {
                      LowPart = Length;
                      v24.LowPart = FileOffset[0].LowPart;
                      v188 = FileOffset[0];
                      v21 = (_DWORD *)v187;
                      goto LABEL_59;
                    }
                    LOBYTE(v172) = v35 & 0xEF;
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                    {
                      WPP_SF_D(
                        WPP_GLOBAL_Control->AttachedDevice,
                        26,
                        WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids,
                        3221225688LL);
                    }
                    if ( RefsStatusDebugEnabled )
                      RefsStatusDebug(-1073741608);
                    RefsRaiseStatusInternal(Context, 3221225688LL);
LABEL_147:
                    v36 = v185;
LABEL_59:
                    v37 = *(_DWORD *)(v200 + 4);
                    if ( (v37 & 0x20) != 0 )
                    {
                      v63 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
                        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
                      {
                        Status = -1073741431;
                      }
                      else
                      {
                        Status = -1073741431;
                        WPP_SF_D(
                          WPP_GLOBAL_Control->AttachedDevice,
                          27,
                          WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids,
                          3221225865LL);
                      }
                      if ( !RefsStatusDebugEnabled )
                        goto LABEL_155;
                      goto LABEL_154;
                    }
                    if ( (v37 & 0x1000000) == 0
                      && (*(_QWORD *)(v200 + 8) || (v68 = *(_QWORD *)(v200 + 248)) != 0 && *(_QWORD *)(v68 + 384))
                      && *(_QWORD *)(v200 + 240) )
                    {
                      if ( (v20 & 4) == 0 )
                        goto LABEL_67;
                      v38 = *(_QWORD **)v192;
                      if ( v3 == *(LARGE_INTEGER **)v192 )
                        goto LABEL_65;
                    }
                    else
                    {
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                      {
                        WPP_SF_D(
                          WPP_GLOBAL_Control->AttachedDevice,
                          28,
                          WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids,
                          3221225768LL);
                      }
                      if ( RefsStatusDebugEnabled )
                        RefsStatusDebug(-1073741528);
                      RefsRaiseStatusInternal(Context, 3221225768LL);
                    }
                    v32 = 0x4000;
                    if ( (v9[31].QuadPart & 0x400000000000LL) != 0 && *((_BYTE *)v38 + 40) == 13 )
                    {
                      v69 = v38[9];
                      if ( v69 )
                      {
                        v222 = *(_QWORD *)(v69 + 184);
                        v70 = v202;
                        LODWORD(v38) = 2;
                        if ( *(_DWORD *)(v222 + 24) == 590047 )
                          v70 = 2;
                        v202 = v70;
                        v24.LowPart = v188.LowPart;
                      }
                    }
LABEL_65:
                    if ( v36 == 5 || !FileObject->SectionObjectPointer->DataSectionObject )
                      goto LABEL_67;
                    if ( LOWORD(v9->LowPart) == 2053 && v9[45].QuadPart && HIWORD(v9[32].u.LowPart) )
                    {
                      v71 = v9[16];
                      LODWORD(v38) = -(1 << *(_DWORD *)(v71.QuadPart + 464));
                      v72 = v188.LowPart & (unsigned int)v38;
                      LowPart = ((unsigned int)v38
                               & ((1 << *(_DWORD *)(v71.QuadPart + 464)) + FileOffset[0].LowPart + LowPart - 1))
                              - (v188.LowPart & (unsigned int)v38);
                    }
                    else
                    {
                      v72 = v24.LowPart;
                    }
                    if ( v9[20].LowPart )
                    {
                      v63 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
                        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
                      {
                        Status = -1073740747;
                      }
                      else
                      {
                        Status = -1073740747;
                        WPP_SF_D(
                          WPP_GLOBAL_Control->AttachedDevice,
                          29,
                          WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids,
                          3221226549LL);
                      }
                      if ( !RefsStatusDebugEnabled )
                        goto LABEL_155;
                      goto LABEL_154;
                    }
                    Status = RefsCacheCoherencyFlush(
                               (_DWORD)v3,
                               (_DWORD)v38,
                               (_DWORD)v9,
                               v72,
                               LowPart,
                               1,
                               v9[20].HighPart == 0);
                    Exception = Status;
                    if ( (Status & 0x80000000) == 0 )
                    {
                      if ( FileObject->PrivateCacheMap )
                        CcUninitializeCacheMap(FileObject, 0, 0);
                      v21 = (_DWORD *)v187;
LABEL_67:
                      if ( v21 && (v21[1] & 0x8000) != 0 )
                      {
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                        {
                          WPP_SF_D(
                            WPP_GLOBAL_Control->AttachedDevice,
                            30,
                            WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids,
                            3221225768LL);
                        }
                        if ( RefsStatusDebugEnabled )
                          RefsStatusDebug(-1073741528);
                        RefsRaiseStatusInternal(Context, 3221225768LL);
                      }
                      else
                      {
                        v39 = v208->LowPart;
                        if ( (v208->LowPart & 0x40) == 0 )
                        {
                          if ( (v39 & 0x10000) == 0 )
                          {
                            if ( (v39 & 0x1000000) != 0 )
                              v40 = -1073741816;
                            else
                              v40 = 0;
                            goto LABEL_73;
                          }
LABEL_219:
                          v40 = -1073741202;
LABEL_73:
                          Exception = v40;
                          if ( v40 < 0 )
                          {
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                            {
                              WPP_SF_D(
                                WPP_GLOBAL_Control->AttachedDevice,
                                32,
                                WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids,
                                (unsigned int)v40);
                            }
                            Information = (unsigned int)Exception;
                            if ( RefsStatusDebugEnabled )
                              RefsStatusDebug(Exception);
                            RefsRaiseStatusInternal(Context, (unsigned int)Exception);
                            goto LABEL_228;
                          }
                          Flags_low = &v9[19].HighPart;
                          HighPart = v9[19].HighPart;
                          _InterlockedOr(v168, 0);
                          v9 = *(union _LARGE_INTEGER **)v178;
                          v41 = HighPart;
                          v2 = (PIRP)CurrentStackLocation;
LABEL_75:
                          v3 = (LARGE_INTEGER *)Context;
                          v42 = v177;
                          while ( 1 )
                          {
                            if ( (v41 & 1) != 0 || FileOffset[0].QuadPart < 0 )
                            {
LABEL_228:
                              ExAcquireFastMutex((PFAST_MUTEX)v9[6].QuadPart);
                              _InterlockedIncrement(Flags_low);
                              v42 = 1;
                              v177 = 1;
                              v9 = *(union _LARGE_INTEGER **)v178;
                              v3 = (LARGE_INTEGER *)Context;
                            }
                            v43 = v9 + 4;
                            v44 = v9[4];
                            v207 = v44;
                            if ( !v42 )
                            {
                              _InterlockedOr(v168, 0);
                              v9 = *(union _LARGE_INTEGER **)v178;
                              if ( HighPart != *(_DWORD *)(*(_QWORD *)v178 + 156LL) )
                              {
                                v41 = 1;
                                HighPart = 1;
                                goto LABEL_75;
                              }
                              v42 = v177;
                              v44 = v207;
                              v3 = (LARGE_INTEGER *)Context;
                            }
                            if ( FileOffset[0].QuadPart < 0 )
                            {
                              Exception = RefsGetIoAtEof((_DWORD)v3, (_DWORD)v9, -1, 0, (__int64)v173);
                              v3[1].LowPart |= 0x20000u;
                              v74.QuadPart = RefsGetHighestPendingFileSize(v73, v9);
                              v2->AssociatedIrp.MasterIrp = (struct _IRP *)v74.QuadPart;
                              FileOffset[0] = v74;
                              FileOffset[1].QuadPart = v74.QuadPart + (unsigned int)Length;
                              if ( __OFSUB__(FileOffset[1].QuadPart, v74.QuadPart) )
                              {
                                _InterlockedIncrement(Flags_low);
                                ExReleaseFastMutex(*(PFAST_MUTEX *)(*(_QWORD *)v178 + 48LL));
                                v63 = WPP_GLOBAL_Control;
                                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
                                  || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
                                {
                                  Status = -1073741811;
                                }
                                else
                                {
                                  Status = -1073741811;
                                  WPP_SF_D(
                                    WPP_GLOBAL_Control->AttachedDevice,
                                    33,
                                    WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids,
                                    3221225485LL);
                                }
                                if ( !RefsStatusDebugEnabled )
                                  goto LABEL_155;
                                goto LABEL_154;
                              }
                              v44 = *v43;
                              v207 = *v43;
                            }
                            if ( FileOffset[1].QuadPart > *(_QWORD *)(v9[16].QuadPart + 392) )
                              break;
                            if ( (v3[1].LowPart & 0x20000) != 0 )
                              goto LABEL_251;
                            if ( FileOffset[1].QuadPart <= v44.QuadPart )
                              goto LABEL_85;
                            if ( v42 )
                            {
                              Exception = RefsGetIoAtEof(
                                            (_DWORD)v3,
                                            (_DWORD)v9,
                                            FileOffset[0].LowPart,
                                            Length,
                                            (__int64)v173);
                              v44 = v9[4];
                              v207 = v44;
LABEL_251:
                              if ( FileOffset[1].QuadPart > v44.QuadPart )
                                v197 = 2;
LABEL_85:
                              if ( FileOffset[0].QuadPart < v44.QuadPart )
                                v197 |= 1u;
                              if ( v42 )
                              {
                                _InterlockedIncrement(&v9[19].HighPart);
                                v9 = *(union _LARGE_INTEGER **)v178;
                                ExReleaseFastMutex(*(PFAST_MUTEX *)(*(_QWORD *)v178 + 48LL));
                                v3 = (LARGE_INTEGER *)Context;
                              }
                              v45 = v3[13];
                              v46 = *(_DWORD *)(v45.QuadPart + 4);
                              if ( (v46 & 2) != 0 )
                              {
                                LOBYTE(Flags_low) = BYTE1(v172);
                              }
                              else
                              {
                                *(_DWORD *)(v45.QuadPart + 4) = v46 | 2;
                                LOBYTE(Flags_low) = BYTE1(v172) | 4;
                                BYTE1(v172) |= 4u;
                              }
                              v47 = (union _LARGE_INTEGER *)(v205 + 136);
                              v188.QuadPart = v205 + 136;
                              goto LABEL_92;
                            }
                            v41 = 1;
                            HighPart = 1;
                          }
                          if ( v42 )
                          {
                            _InterlockedIncrement(Flags_low);
                            ExReleaseFastMutex(*(PFAST_MUTEX *)(*(_QWORD *)v178 + 48LL));
                          }
                          v63 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
                            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
                          {
                            Status = -1073741811;
                          }
                          else
                          {
                            Status = -1073741811;
                            WPP_SF_D(
                              WPP_GLOBAL_Control->AttachedDevice,
                              34,
                              WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids,
                              3221225485LL);
                          }
                          if ( !RefsStatusDebugEnabled )
                            goto LABEL_155;
LABEL_154:
                          RefsStatusDebug(Status);
LABEL_155:
                          Exception = Status;
LABEL_158:
                          v9 = *(union _LARGE_INTEGER **)v178;
                          LOBYTE(Flags_low) = BYTE1(v172);
                          v20 = v172;
                          v3 = (LARGE_INTEGER *)Context;
                          v2 = Irp;
                          goto LABEL_159;
                        }
                      }
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                      {
                        WPP_SF_D(
                          WPP_GLOBAL_Control->AttachedDevice,
                          31,
                          WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids,
                          3221225763LL);
                      }
                      if ( RefsStatusDebugEnabled )
                        RefsStatusDebug(-1073741533);
                      RefsRaiseStatusInternal(Context, 3221225763LL);
                      goto LABEL_219;
                    }
LABEL_159:
                    if ( v2 )
                    {
                      if ( (Status & 0x80000000) == 0 && Status != 259 )
                        *(_BYTE *)(v3[18].QuadPart + 3) |= 1u;
                      v2->IoStatus.Status = Status;
                      if ( (Status & 0x80000000) == 0 && (v20 & 0x80u) != 0 )
                        v2->IoStatus.Information = v195;
                      RefsPostWriteProcessing(
                        (_DWORD)v3,
                        (_DWORD)v2,
                        (_DWORD)v9,
                        (unsigned int)v189,
                        (__int64)&v172,
                        (__int64)v173);
                      v66 = v173[0];
                      if ( (Status & 0x80000000) == 0 )
                        v66 = Information;
                      v173[0] = v66;
                      LOBYTE(Flags_low) = BYTE1(v172);
                      v20 = v172;
                      if ( (v172 & 0x800) != 0 && (v172 & 0x20) == 0 )
                      {
                        if ( (Status & 0xC0000000) != 0xC0000000 )
                          Information = v2->IoStatus.Information;
                        v67.QuadPart = Information + FileOffset[0].QuadPart;
                        v64 = (int)FileObject;
                        FileObject->CurrentByteOffset = v67;
                        goto LABEL_558;
                      }
LABEL_557:
                      v64 = (int)FileObject;
LABEL_558:
                      RefsCleanupTransaction(v3, Status, 0);
                      RefsCommitCurrentTransaction(v3, 0);
                      RefsFlushForWriteThrough(v3, v9);
                      goto LABEL_559;
                    }
LABEL_131:
                    v64 = (int)FileObject;
LABEL_559:
                    if ( (v173[0] || (v20 & 2) != 0) && Status != 259 )
                    {
                      ExAcquireFastMutex((PFAST_MUTEX)v9[6].QuadPart);
                      _InterlockedIncrement(&v9[19].HighPart);
                      v160 = v172;
                      v161 = *(union _LARGE_INTEGER **)v178;
                      if ( (v172 & 2) != 0 )
                      {
                        v162 = v64;
                        v163 = Context;
                        RefsCompleteFileSizeExtension(
                          (_DWORD)Context,
                          v162,
                          v178[0],
                          (unsigned int)v189,
                          0,
                          (__int64)v173);
                        LOBYTE(v172) = v160 & 0xFD;
                      }
                      else
                      {
                        v163 = Context;
                      }
                      if ( v173[0] )
                      {
                        HighestPendingFileSize = RefsGetHighestPendingFileSize(v159, v161);
                        v203 = HighestPendingFileSize;
                        SectionObjectPointer = FileObject->SectionObjectPointer;
                        if ( SectionObjectPointer )
                        {
                          SharedCacheMap = SectionObjectPointer->SharedCacheMap;
                          if ( SharedCacheMap )
                            SharedCacheMap[1] = HighestPendingFileSize;
                        }
                      }
                      v167 = v163[2];
                      if ( (v167 & 0x20000) != 0 )
                      {
                        v163[2] = v167 & 0xFFFDFFFF;
                        CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart = -1;
                      }
                      _InterlockedIncrement(&v9[19].HighPart);
                      ExReleaseFastMutex((PFAST_MUTEX)v9[6].QuadPart);
                      Status = Exception;
                      v9 = *(union _LARGE_INTEGER **)v178;
                      LOBYTE(Flags_low) = BYTE1(v172);
                      v20 = v172;
                      v3 = (LARGE_INTEGER *)Context;
                      v2 = Irp;
                    }
                    if ( v2 )
                    {
                      if ( ((unsigned __int8)Flags_low & 2) != 0 )
                        ((void (__fastcall *)(_QWORD, _QWORD))RefsReleaseFcb)(v3, (union _LARGE_INTEGER)v9[15].QuadPart);
                      if ( ((unsigned __int8)Flags_low & 4) != 0 )
                        *(_DWORD *)(v3[13].QuadPart + 4) &= ~2u;
                    }
                    if ( (v20 & 0x40) != 0 )
                      RefsReleasePagingFastResource(v63, v9, v215);
                    if ( DWORD2(v216) )
                      __fastfail(5u);
                    *((_QWORD *)&v216 + 1) &= 0xFFFFFFFE00000000uLL;
                    RefsCompleteWriteRequest(v3, v2, Status);
                    return Status;
                  }
LABEL_133:
                  v65 = (v20
                       ^ ((unsigned __int8)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))RefsAcquirePagingFastResourceExclusive)(
                                             (union _LARGE_INTEGER)v24.QuadPart,
                                             v9,
                                             v215,
                                             ((unsigned __int8)Flags_low & 0x40) != 0) << 6))
                      & 0x40
                      ^ v20;
                  goto LABEL_134;
                }
LABEL_132:
                if ( !FileObject->SectionObjectPointer->SharedCacheMap )
                  goto LABEL_133;
                goto LABEL_49;
              }
              if ( v21 && (v21[2] & 2) != 0 )
                v3[25].LowPart = v21[21];
              v75 = v192;
              if ( v3 == *(LARGE_INTEGER **)v192 && LOBYTE(IoGetTopLevelIrp()->Type) )
              {
                if ( ExIsResourceAcquiredSharedLite((PERESOURCE)(*(_QWORD *)(v9[15].QuadPart + 96) + 64LL))
                  || v9[2].QuadPart && (unsigned __int8)ExIsFastResourceHeld(*(_QWORD *)(v9[15].QuadPart + 104)) )
                {
                  LOBYTE(IoGetTopLevelIrp()->Type) = 0;
                }
              }
              else if ( (*(_DWORD *)(*(_QWORD *)v75 + 8LL) & 8) != 0 )
              {
                v76 = v186;
                v186->LowPart |= 8u;
                *(_BYTE *)(v3[18].QuadPart + 3) |= 2u;
LABEL_264:
                if ( v9[2].QuadPart )
                {
                  if ( !(unsigned __int8)ExIsFastResourceHeld(*(_QWORD *)(v9[15].QuadPart + 104))
                    && !ExIsResourceAcquiredSharedLite((PERESOURCE)(*(_QWORD *)(v9[15].QuadPart + 96) + 64LL)) )
                  {
                    v77 = 0;
                    if ( LOWORD(v9->LowPart) == 2050 )
                    {
                      v77 = v9;
                    }
                    else if ( v9[2].QuadPart )
                    {
                      v77 = (union _LARGE_INTEGER *)v9[15].QuadPart;
                    }
                    v78 = v20
                        ^ (v20
                         ^ ((unsigned __int8)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))MsAcquireFastResourceSharedStarveExclusive)(
                                               (union _LARGE_INTEGER)v77[13].QuadPart,
                                               v215,
                                               0) << 6))
                        & 0x40;
                    LOBYTE(v172) = v78;
                    if ( (v78 & 0x40) == 0 )
                    {
                      LOBYTE(v172) = v78 & 0xEF;
                      v63 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
                        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
                      {
                        Status = -1073741740;
                      }
                      else
                      {
                        Status = -1073741740;
                        WPP_SF_D(
                          WPP_GLOBAL_Control->AttachedDevice,
                          35,
                          WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids,
                          3221225556LL);
                      }
                      if ( !RefsStatusDebugEnabled )
                        goto LABEL_155;
                      goto LABEL_154;
                    }
                  }
                  v76 = v186;
                }
                v79 = v9 + 15;
                if ( (*(_DWORD *)(v9[15].QuadPart + 4) & 0x8000) != 0
                  || *(union _LARGE_INTEGER **)(v9[16].QuadPart + 40) == v9 )
                {
                  v3[1].HighPart |= 0x100u;
                  v80 = v3[3];
                  if ( v80.QuadPart )
                    *(_QWORD *)(v80.QuadPart + 16) |= 0x80000000uLL;
                }
                v81 = v208;
                v82 = v208->LowPart;
                if ( (v208->LowPart & 0x40) != 0 )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                  {
                    WPP_SF_D(
                      WPP_GLOBAL_Control->AttachedDevice,
                      36,
                      WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids,
                      3221225763LL);
                  }
                  if ( RefsStatusDebugEnabled )
                    RefsStatusDebug(-1073741533);
                  v82 = RefsRaiseStatusInternal(Context, 3221225763LL);
                }
                if ( (v82 & 0x10000) != 0 )
                  v83 = -1073741202;
                else
                  v83 = (v82 & 0x1000000) != 0 ? 0xC0000008 : 0;
                Exception = v83;
                if ( v83 < 0 )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                  {
                    WPP_SF_D(
                      WPP_GLOBAL_Control->AttachedDevice,
                      37,
                      WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids,
                      (unsigned int)v83);
                  }
                  Information = (unsigned int)Exception;
                  if ( RefsStatusDebugEnabled )
                    RefsStatusDebug(Exception);
                  RefsRaiseStatusInternal(Context, (unsigned int)Exception);
                }
                if ( ((unsigned __int8)Flags_low & 0x40) == 0
                  && v9[31].LowPart
                  && LOWORD(v9->LowPart) == 2053
                  && v9[45].QuadPart
                  && HIWORD(v9[32].u.LowPart) )
                {
                  LOBYTE(Flags_low) = (unsigned __int8)Flags_low | 0x40;
                  BYTE1(v172) = (_BYTE)Flags_low;
                  v76->LowPart |= 1u;
                  *(_BYTE *)(v3[18].QuadPart + 3) |= 1u;
                }
                if ( IoGetTopLevelIrp()->AssociatedIrp.MasterIrp == (struct _IRP *)2 )
                {
                  v186->LowPart &= ~8u;
                  *(_BYTE *)(v3[18].QuadPart + 3) &= ~2u;
                  v84 = FileObject->Flags;
                  if ( (v81->LowPart & 0x100) != 0 )
                    FileObject->Flags = v84 | 0x8000;
                  else
                    FileObject->Flags = v84 & 0xFFFF7FFF;
                }
                else
                {
                  v85 = *(_DWORD *)(*(_QWORD *)v192 + 4LL);
                  if ( (v85 & 2) != 0 )
                  {
                    v86 = (unsigned __int8)Flags_low | 1;
                  }
                  else
                  {
                    *(_DWORD *)(*(_QWORD *)v192 + 4LL) = v85 | 2;
                    v86 = (unsigned __int8)Flags_low | 4;
                  }
                  BYTE1(v172) = v86;
                }
                ExAcquireFastMutex((PFAST_MUTEX)v9[6].QuadPart);
                _InterlockedIncrement(&v9[19].HighPart);
                v88 = *(_DWORD *)(v194 + 288);
                v89 = *(union _LARGE_INTEGER **)v178;
                v90 = (union _LARGE_INTEGER *)(*(_QWORD *)v178 + 24LL);
                v91 = *(union _LARGE_INTEGER *)(*(_QWORD *)v178 + 24LL);
                v92 = v91.QuadPart + v88 - 1;
                v93 = (unsigned int)-v88;
                v94.QuadPart = (int)v93 & (unsigned __int64)v92;
                v95 = FileOffset[0];
                if ( FileOffset[0].QuadPart >= v91.QuadPart )
                {
                  *(_QWORD *)(*((_QWORD *)Context + 18) + 288LL) = 2;
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                  {
                    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_iiP)(
                      WPP_GLOBAL_Control->AttachedDevice,
                      38,
                      v87,
                      (union _LARGE_INTEGER)FileOffset[0].QuadPart,
                      v90->QuadPart,
                      v89);
                  }
                  Irp->IoStatus.Information = Information;
                  _InterlockedIncrement(&v9[19].HighPart);
                  ExReleaseFastMutex((PFAST_MUTEX)v9[6].QuadPart);
                  v63 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                  {
                    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids, 0);
                  }
                  if ( !RefsStatusDebugEnabled )
                    goto LABEL_157;
                  goto LABEL_156;
                }
                v96 = FileOffset[1];
                if ( FileOffset[1].QuadPart <= v94.QuadPart )
                {
                  v97 = FileOffset[0].LowPart;
                }
                else
                {
                  v93 = (unsigned __int64)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                  {
                    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_iiP)(
                      WPP_GLOBAL_Control->AttachedDevice,
                      40,
                      (union _LARGE_INTEGER)FileOffset[1].QuadPart,
                      (union _LARGE_INTEGER)FileOffset[1].QuadPart,
                      (union _LARGE_INTEGER)v94.QuadPart,
                      *(_QWORD *)v178);
                    v95 = FileOffset[0];
                  }
                  v96 = v94;
                  FileOffset[1] = v94;
                  v97 = FileOffset[0].LowPart;
                  LODWORD(Length) = v94.LowPart - FileOffset[0].LowPart;
                }
                v223 = *(_QWORD *)v178 + 24LL;
                v98 = *v90;
                if ( v96.QuadPart > v90->QuadPart )
                {
                  if ( v95.QuadPart >= v98.QuadPart )
                  {
                    Irp->IoStatus.Information = Information;
                    FileOffset[1] = *v90;
                    _InterlockedIncrement(&v9[19].HighPart);
                    ExReleaseFastMutex((PFAST_MUTEX)v9[6].QuadPart);
                    v63 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                    {
                      WPP_SF_D(
                        WPP_GLOBAL_Control->AttachedDevice,
                        41,
                        WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids,
                        0);
                    }
                    if ( !RefsStatusDebugEnabled )
                      goto LABEL_157;
LABEL_156:
                    RefsStatusDebug(0);
LABEL_157:
                    Status = Information;
                    Exception = Information;
                    goto LABEL_158;
                  }
                  LODWORD(Length) = v98.LowPart - v97;
                  FileOffset[1] = *v90;
                }
                v99 = RefsGetHighestPendingFileSize(v93, *(_QWORD *)v178);
                v203 = v99;
                if ( v102 > v99 )
                {
                  if ( v99 > v101 )
                    v195 = v99 - v100;
                  LOBYTE(v172) = v172 | 0x80;
                }
                _InterlockedIncrement(&v9[19].HighPart);
                ExReleaseFastMutex((PFAST_MUTEX)v9[6].QuadPart);
                v9 = *(union _LARGE_INTEGER **)v178;
                v47 = (union _LARGE_INTEGER *)(*(_QWORD *)v178 + 136LL);
                v188.QuadPart = *(_QWORD *)v178 + 136LL;
                v45.QuadPart = *(unsigned __int8 *)(*(_QWORD *)v178 + 4LL);
                LOBYTE(v45.LowPart) = ((*v209 & 0x80000) != 0)
                                    & ((*(_DWORD *)(*(_QWORD *)v178 + 136LL) & 0x40000) != 0)
                                    & (LOBYTE(v45.LowPart) >> 5);
                if ( (v45.LowPart & 1) == 0
                  || (v188.QuadPart = *(_QWORD *)v178 + 136LL, (*(_DWORD *)(v79->QuadPart + 4) & 0x100) != 0) )
                {
                  v3 = (LARGE_INTEGER *)Context;
                }
                else
                {
                  v3 = (LARGE_INTEGER *)Context;
                  RefsPostUsnChangeWithOverrideOption(Context, *(_QWORD *)v178, 1);
                  RefsCheckpointCurrentTransaction(Context);
                  v188.QuadPart = *(_QWORD *)v178 + 136LL;
                }
                LOBYTE(Flags_low) = BYTE1(v172);
LABEL_92:
                v48 = 0x80000000LL;
                if ( (v47->LowPart & 0x20) == 0 && v9[25].LowPart != 160 )
                {
                  LOBYTE(v32) = 1;
                  ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))RefsAcquireResourceShared)(
                    (LARGE_INTEGER)v45.QuadPart,
                    v9,
                    v32);
                  v103 = (unsigned __int8)Flags_low | 2;
                  BYTE1(v172) = v103;
                  RefsUpdateScbFromAttribute(v3, v9, 0);
                  if ( LOWORD(v9->LowPart) == 2050 )
                    v104 = (struct _ERESOURCE *)(v9[12].QuadPart + 64);
                  else
                    v104 = (struct _ERESOURCE *)v9[1].QuadPart;
                  ExReleaseResourceLite(v104);
                  LOBYTE(Flags_low) = v103 & 0xFD;
                  BYTE1(v172) = (_BYTE)Flags_low;
                  v48 = 0x80000000LL;
                }
                v20 = v172;
                if ( v173[0]
                  && (((unsigned __int8)Flags_low & 0x40) == 0 && (v172 & 4) != 0
                   || LOWORD(v9->LowPart) == 2053 && v9[45].QuadPart && HIWORD(v9[32].u.LowPart)) )
                {
                  LOBYTE(Flags_low) = (unsigned __int8)Flags_low | 0x40;
                  BYTE1(v172) = (_BYTE)Flags_low;
                  v3[1].LowPart |= 1u;
                  *(_BYTE *)(v3[18].QuadPart + 3) |= 1u;
                }
                v49 = v20;
                LOBYTE(v49) = (v20 & 0x20) != 0;
                v175 = v49;
                if ( (v20 & 0x20) != 0 || v185 != 2 )
                {
                  v2 = Irp;
                  goto LABEL_110;
                }
                v181 = 0;
                v182 = 0;
                v2 = Irp;
                if ( IoGetIoPriorityHint(Irp) < IoPriorityNormal )
                  v50 = 3136;
                else
                  v50 = 3088;
                if ( *(_DWORD *)(v50 + v206) >= 0x3E8u || IoIsOperationSynchronous(v2) )
                {
                  v51 = (LARGE_INTEGER **)v192;
                  if ( (v3[1].LowPart & 0x40) != 0 || v3 != *(LARGE_INTEGER **)v192 )
                    goto LABEL_101;
                  if ( LOBYTE(IoGetTopLevelIrp()->Type) )
                  {
                    *(_DWORD *)v3[18].QuadPart |= 8u;
                    v181 = 1;
                  }
                }
                v51 = (LARGE_INTEGER **)v192;
LABEL_101:
                if ( ((unsigned __int8)Flags_low & 4) != 0 )
                {
                  v52 = *v51;
                  if ( v52 != v3 )
                  {
                    v52->HighPart &= ~2u;
                    LOBYTE(Flags_low) = (unsigned __int8)Flags_low & 0xFB;
                    BYTE1(v172) = (_BYTE)Flags_low;
                    v182 = 1;
                  }
                }
                v53 = FsRtlCheckOplock((POPLOCK)&v9[11], v2, v3, RefsOplockComplete, RefsWriteOplockPrePostIrp);
                Status = v53;
                Exception = v53;
                if ( v53 )
                {
                  if ( v53 == 259 && v181 )
                  {
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
                      || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
                    {
                      Status = 871;
                    }
                    else
                    {
                      Status = 871;
                      WPP_SF_D(
                        WPP_GLOBAL_Control->AttachedDevice,
                        42,
                        WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids,
                        871);
                    }
                    if ( RefsStatusDebugEnabled )
                      RefsStatusDebug(871);
                    Exception = 871;
                    v9 = *(union _LARGE_INTEGER **)v178;
                    LOBYTE(Flags_low) = BYTE1(v172);
                    v20 = v172;
                  }
                  if ( !(unsigned __int8)ExIsFastResourceHeldExclusive(*(_QWORD *)(v9[15].QuadPart + 104)) )
                    ExIsFastResourceHeld(*(_QWORD *)(v9[15].QuadPart + 104));
                  LOBYTE(Flags_low) = (unsigned __int8)Flags_low & 0xFD;
                  BYTE1(v172) = (_BYTE)Flags_low;
                  v2 = (PIRP)Information;
                  Irp = (PIRP)Information;
                  v3 = (LARGE_INTEGER *)Information;
                  Context = (PVOID)Information;
                  v173[0] = Information;
                  goto LABEL_159;
                }
                if ( v182 )
                {
                  *(_DWORD *)(*(_QWORD *)v192 + 4LL) |= 2u;
                  LOBYTE(Flags_low) = (unsigned __int8)Flags_low | 4;
                  BYTE1(v172) = (_BYTE)Flags_low;
                }
                if ( !BYTE5(v9->QuadPart) )
                {
                  if ( (*(_DWORD *)(v9[16].QuadPart + 4) & 0x4000005) == 1
                    && LOWORD(v9->LowPart) == 2053
                    && (v9[38].LowPart & 0x40) == 0
                    && FsRtlOplockIsFastIoPossible((POPLOCK)&v9[11]) )
                  {
                    if ( v9[31].LowPart
                      || (v105 = v9[42], v105.QuadPart) && *(_BYTE *)(v105.QuadPart + 16)
                      || (v106 = *(_DWORD *)(v9[16].QuadPart + 4), (v106 & 0x2000000) != 0)
                      || (*(_BYTE *)(v9[15].QuadPart + 4) & 0x20) != 0
                      || (v106 & 0x80000) != 0 )
                    {
                      v107 = 2;
                    }
                    else
                    {
                      v107 = 1;
                    }
                  }
                  else
                  {
                    v107 = Information;
                  }
                  BYTE5(v9->QuadPart) = v107;
                }
                v55 = (FILE_LOCK *)v9[42].QuadPart;
                if ( v55 && !FsRtlCheckLockForWriteAccess(v55, v2) )
                {
                  v63 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
                    || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
                  {
                    Status = -1073741740;
                  }
                  else
                  {
                    Status = -1073741740;
                    WPP_SF_D(
                      WPP_GLOBAL_Control->AttachedDevice,
                      43,
                      WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids,
                      3221225556LL);
                  }
                  if ( !RefsStatusDebugEnabled )
                    goto LABEL_155;
                  goto LABEL_154;
                }
                v49 = v175;
                v47 = (union _LARGE_INTEGER *)v188.QuadPart;
                v48 = 0x80000000LL;
LABEL_110:
                v56 = v197;
                v57 = v194;
                if ( v197 && (*(_DWORD *)(v194 + 4) & 0x80000) != 0 )
                {
                  RefsPostUsnChangeWithOverrideOption(v3, v9, v197);
                  v57 = v194;
                  v49 = v175;
                  v48 = 0x80000000LL;
                }
                if ( v173[0] )
                {
                  v47 = (union _LARGE_INTEGER *)v188.QuadPart;
                  if ( !(_BYTE)v49 )
                  {
                    v206 = v9[4].QuadPart;
                    v205 = v206;
                    v204 = (PDEVICE_OBJECT)RefsGetHighestPendingFileSize(v49, v9);
                    v203 = (__int64)v204;
                    v110 = *(unsigned int *)(v109 + 456);
                    v111 = (v110 + FileOffset[1].QuadPart) >> *(_BYTE *)(v109 + 464);
                    v112 = ((__int64)v204 + v110) >> *(_BYTE *)(v109 + 464);
                    v187 = v112;
                    if ( v112 < v111 && (*v108 & 8) == 0 )
                    {
                      v221 = 0;
                      v226 = v112;
                      v192 = v111 - v112;
                      v227 = v111 - v112;
                      RefsBindMinstoreTransaction(v3);
                      v113 = v194;
                      RefsAcquireRangeLock(
                        (_DWORD)v3,
                        v9[30].QuadPart,
                        v187 << *(_BYTE *)(v194 + 464),
                        v192 << *(_BYTE *)(v194 + 464),
                        1,
                        (__int64)&v221);
                      v220[0] = v187;
                      v220[1] = v192;
                      Exception = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))MsSetRangeValidState)(
                                    (LARGE_INTEGER)v3[3].QuadPart,
                                    (union _LARGE_INTEGER)v9[45].QuadPart,
                                    v220,
                                    0);
                      LOBYTE(v114) = 1;
                      RefsReleaseRangeLock(
                        v9[30].QuadPart,
                        v187 << *(_BYTE *)(v113 + 464),
                        v192 << *(_BYTE *)(v113 + 464),
                        v114,
                        (__int64)&v221);
                      if ( Exception < 0 )
                      {
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                        {
                          WPP_SF_D(
                            WPP_GLOBAL_Control->AttachedDevice,
                            44,
                            WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids,
                            (unsigned int)Exception);
                        }
                        Information = (unsigned int)Exception;
                        if ( RefsStatusDebugEnabled )
                          RefsStatusDebug(Exception);
                        RefsRaiseStatusInternal(Context, (unsigned int)Information);
                      }
                      RefsCheckpointCurrentTransaction(v3);
                    }
                    RefsAcquireExclusiveScbWithFlags(v3, v9, 0);
                    v115 = (int *)v188.QuadPart;
                    v116 = *(_DWORD *)v188.QuadPart;
                    v117 = 15;
                    if ( (*(_DWORD *)v188.QuadPart & 8) == 0 && (v9[31].QuadPart & 0x800000000000LL) != 0 )
                    {
                      v118 = v9[16];
                      v117 = v206;
                      if ( ((unsigned int)v206 & *(_DWORD *)(v118.QuadPart + 456)) != 0 )
                      {
                        v219[0] = Information;
                        v218[0] = Information;
                        v183[0] = 0;
                        RefsLookupAllocationEx(
                          (_DWORD)v3,
                          (_DWORD)v9,
                          v206 >> *(_BYTE *)(v118.QuadPart + 464),
                          4,
                          (__int64)v219,
                          (__int64)v218,
                          v170,
                          v171,
                          Information,
                          Information,
                          Information,
                          (__int64)v183,
                          Information);
                        if ( v183[0] )
                        {
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                          {
                            WPP_SF_D(
                              WPP_GLOBAL_Control->AttachedDevice,
                              45,
                              WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids,
                              3221266439LL);
                          }
                          if ( RefsStatusDebugEnabled )
                            RefsStatusDebug(-1073700857);
                          RefsRaiseStatusInternal(Context, 3221266439LL);
                        }
                        if ( (v9[31].QuadPart & 0x200000000000LL) == 0
                          || (*(_DWORD *)(*(_QWORD *)(v9[16].QuadPart + 104) + 3116LL) & 0x800000) == 0 )
                        {
                          v198 = Information;
                        }
                        *(_DWORD *)(v3[18].QuadPart + 296) = v198;
                        v116 = *(_DWORD *)(v210 + 136);
                      }
                    }
                    v119 = FileOffset[1].QuadPart;
                    if ( FileOffset[1].QuadPart > v9[3].QuadPart )
                    {
                      if ( (v116 & 8) == 0
                        || (v120 = RefsAddAllocationForResidentWrite(
                                     (_DWORD)v3,
                                     v116,
                                     v117,
                                     (_DWORD)v9,
                                     (__int64)v199,
                                     FileOffset[0].QuadPart,
                                     Length),
                            v119 = FileOffset[1].QuadPart,
                            v120) )
                      {
                        if ( v119 > v9[3].QuadPart )
                        {
                          RefsAddAllocationForNonResidentWrite(
                            (_DWORD)v3,
                            (_DWORD)FileObject,
                            (_DWORD)v9,
                            (_DWORD)v199,
                            FileOffset[0].QuadPart,
                            v119);
                          v119 = FileOffset[1].QuadPart;
                        }
                      }
                    }
                    v205 = v9[4].QuadPart;
                    v121 = FileObject->SectionObjectPointer;
                    if ( v121 )
                    {
                      v122 = v121->SharedCacheMap;
                      if ( v122 )
                      {
                        if ( v119 > v122[1] )
                        {
                          v228 = 0;
                          v229.QuadPart = 0;
                          *(union _LARGE_INTEGER *)&v228 = v9[3];
                          v123 = (__int64)v204;
                          if ( v119 > (__int64)v204 )
                            v123 = v119;
                          *((_QWORD *)&v228 + 1) = v123;
                          v229 = v9[5];
                          RefsSetBothCacheSizes(v119, FileObject, &v228, v9);
                        }
                      }
                    }
                    v124 = *v115;
                    v125 = v200;
                    if ( (v124 & 0x10) != 0 )
                    {
                      *(_DWORD *)(v200 + 4) |= 0x10u;
                      v199[1] |= 0x10000u;
                    }
                    RefsCheckpointCurrentTransaction(v3);
                    v20 |= 2u;
                    LOBYTE(v172) = v20;
                    RefsInitiateFileSizeExtension(v9, v189, 0);
                    v126 = v3->HighPart;
                    if ( (v126 & 0x2000) != 0 )
                    {
                      v3->HighPart = v126 & 0xFFFFCFFF;
                      RtlCaptureStackBackTrace(0, 9u, (PVOID *)(*(_QWORD *)(v125 + 88) + 1352LL), 0);
                      ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(v125 + 88) + 1176LL));
                    }
                    while ( 1 )
                    {
                      v127 = (LARGE_INTEGER *)v3[14].QuadPart;
                      if ( v127 == &v3[14] )
                        break;
                      RefsReleaseFcb(v3, &v127[-9]);
                    }
                    if ( v3[6].QuadPart )
                      RefsReleaseSharedResources(v3);
                    v47 = v9 + 17;
                    if ( (v9[17].LowPart & 8) == 0 || (v20 & 4) == 0 )
                    {
                      RefsReleaseEofLock(v3, v9);
                      v173[0] = 0;
                    }
                    v48 = 0x80000000LL;
                    v57 = v194;
                  }
                }
                if ( (v9[38].LowPart & 0x4000) != 0 || (v47->LowPart & 8) != 0 )
                {
                  if ( (v20 & 4) == 0 )
                    goto LABEL_490;
                  RefsAcquireExclusiveScbWithFlags(v3, v9, 0);
                  v129 = (unsigned __int8)Flags_low | 2;
                  BYTE1(v172) = v129;
                  v130 = v47->LowPart;
                  if ( (v47->LowPart & 0x20) == 0 )
                  {
                    RefsUpdateScbFromAttribute(v3, v9, 0);
                    v130 = *(_DWORD *)(v210 + 136);
                  }
                  if ( (v130 & 8) != 0 )
                  {
                    v131 = v129 | 0x10;
                    BYTE1(v172) = v131;
                    *(_DWORD *)Retrying = Length;
                    Status = RefsResidentWrite(
                               (int)v3,
                               (int)v2,
                               v128,
                               (int)v9,
                               FileOffset[0].LowPart,
                               *(size_t *)Retrying);
                    Exception = Status;
                    RefsCheckpointCurrentTransaction(v3);
                    RefsReleaseFcb(v3, *(_QWORD *)(v211 + 120));
                    LOBYTE(Flags_low) = v131 & 0xFD;
                    BYTE1(v172) = (_BYTE)Flags_low;
                    goto LABEL_159;
                  }
                  RefsReleaseFcb(v3, *(_QWORD *)(v211 + 120));
                  LOBYTE(Flags_low) = v129 & 0xFD;
                  BYTE1(v172) = (_BYTE)Flags_low;
                  v57 = v194;
                  v48 = 0x80000000LL;
                }
                if ( (v20 & 4) != 0 )
                {
                  v58 = *(_DWORD *)(v57 + 276);
                  v59 = -v58 & (v58 + Length - 1);
                  if ( ((v58 - 1) & FileOffset[0].LowPart) != 0
                    || v59 != (_DWORD)Length && FileOffset[1].QuadPart < v9[4].QuadPart )
                  {
                    v63 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
                      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
                    {
                      Status = -1073741822;
                    }
                    else
                    {
                      Status = -1073741822;
                      WPP_SF_D(
                        WPP_GLOBAL_Control->AttachedDevice,
                        46,
                        WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids,
                        3221225474LL);
                    }
                    if ( !RefsStatusDebugEnabled )
                      goto LABEL_155;
                    goto LABEL_154;
                  }
                  if ( (*(_DWORD *)(v57 + 3824) & 2) != 0 && IoGetIoPriorityHint(v2) > IoPriorityLow )
                  {
                    if ( ((v132 = v9[25].LowPart, v132 == 128) || v132 == 176) && !LOWORD(v9[26].LowPart) || v132 == 160 )
                      RefsHeatLogIo(v2, v200);
                  }
                  if ( ((unsigned __int8)Flags_low & 0x40) == 0 )
                  {
                    if ( (v20 & 0x20) != 0 )
                    {
                      if ( (v20 & 0x80u) == 0 )
                        v133 = CurrentStackLocation->Parameters.Read.Length;
                      else
                        v133 = v195;
                      RefsSetIoContextAsync((_DWORD)v3, 0, 0, 0, Information, FileOffset[0].QuadPart, v133, 1, v133);
                    }
                    else
                    {
                      v60 = CurrentStackLocation->Parameters.Read.Length;
                      v61 = FileOffset[0];
                      v62 = v9[2];
                      *(_QWORD *)(v3[18].QuadPart + 48) = Information;
                      *(union _LARGE_INTEGER *)(v3[18].QuadPart + 64) = v62;
                      *(_QWORD *)(v3[18].QuadPart + 72) = v215;
                      CurrentThread = KeGetCurrentThread();
                      *(_QWORD *)(v3[18].QuadPart + 56) = CurrentThread;
                      *(_QWORD *)(v3[18].QuadPart + 168) = Information;
                      *(union _LARGE_INTEGER *)(v3[18].QuadPart + 176) = v61;
                      *(_DWORD *)(v3[18].QuadPart + 184) = v60;
                      *(_BYTE *)(v3[18].QuadPart + 188) = 1;
                      *(_DWORD *)(v3[18].QuadPart + 192) = v60;
                      *(_QWORD *)(v3[18].QuadPart + 200) = Information;
                      *(_DWORD *)v3[18].QuadPart |= 4u;
                      v9 = *(union _LARGE_INTEGER **)v178;
                      LOBYTE(Flags_low) = BYTE1(v172);
                      v20 = v172;
                      v3 = (LARGE_INTEGER *)Context;
                      v2 = Irp;
                    }
                  }
                  if ( (v3[1].LowPart & 1) == 0 )
                    RefsFlushForWriteThrough(v3, v9);
                  Status = RefsNonCachedIo((int)v3, v2, v59, v202);
                  Exception = Status;
                  if ( Status == 259 )
                  {
                    if ( v9[2].QuadPart
                      && !(unsigned __int8)ExIsFastResourceHeldExclusive(*(_QWORD *)(v9[15].QuadPart + 104)) )
                    {
                      ExIsFastResourceHeld(*(_QWORD *)(v9[15].QuadPart + 104));
                    }
                    if ( ((unsigned __int8)Flags_low & 4) != 0 )
                      *(_DWORD *)(v3[13].QuadPart + 4) &= ~2u;
                    v3[18].QuadPart = Information;
                    v3[1].LowPart &= ~0x8000u;
                    v20 &= ~0x40u;
                    LOBYTE(v172) = v20;
                    v2 = (PIRP)Information;
                    Irp = (PIRP)Information;
                    goto LABEL_131;
                  }
                  LOBYTE(Flags_low) = (unsigned __int8)Flags_low | 0x10;
                  BYTE1(v172) = (_BYTE)Flags_low;
                  Status = v2->IoStatus.Status;
                  Exception = Status;
                  if ( (Status & 0x80000000) != 0 )
                  {
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                    {
                      WPP_SF_DD(
                        WPP_GLOBAL_Control->AttachedDevice,
                        47,
                        WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids,
                        3221225705LL,
                        Status);
                    }
                    v3[2].LowPart = Status;
                    v134 = Exception;
                    if ( RefsStatusDebugEnabled )
                      RefsStatusDebug(Exception);
                    v135 = FsRtlNormalizeNtstatus(v134, -1073741591);
                    ExRaiseStatus(v135);
                  }
                  v63 = (PDEVICE_OBJECT)v212;
                  if ( v195 )
                    v212->IoStatus.Information = v195;
                  else
                    v212->IoStatus.Information = (unsigned int)Length;
                  goto LABEL_159;
                }
LABEL_490:
                v136 = FileObject;
                if ( !FileObject->PrivateCacheMap )
                {
                  v137 = v3;
                  if ( v9[4].QuadPart > v9[3].QuadPart )
                  {
                    Information = v200;
                    v136 = (struct _FILE_OBJECT *)(unsigned int)RefsQueueTriageForDeadFcb(v3, v200, v56, v57);
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                    {
                      WPP_SF_qd(
                        WPP_GLOBAL_Control->AttachedDevice,
                        48,
                        WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids,
                        Information,
                        (_DWORD)v136);
                    }
                    if ( RefsStatusDebugEnabled )
                      RefsStatusDebug((NTSTATUS)v136);
                    RefsRaiseStatusInternal(Context, (unsigned int)v136);
                  }
                  RefsInitializeCacheMap(v137, v136, 0, v9);
                  CcSetReadAheadGranularity(v136, 0x10000u);
                  CcSetParallelFlushFile(v136, 1u);
                  v48 = 0x80000000LL;
                }
                if ( ((v20 >> 4) & ((v3[1].LowPart & 0x20100) == 0)) != 0 )
                {
                  LOBYTE(v49) = (v20 >> 4) & ((v3[1].LowPart & 0x20100) == 0);
                  RefsConvertPagingFastResourceExclusiveToShared(v49, v9, v215, v57);
                  v20 &= ~0x10u;
                  LOBYTE(v172) = v20;
                  v48 = 0x80000000LL;
                }
                if ( (v20 & 1) != 0 )
                {
                  v63 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                  {
                    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids, 0);
                  }
                  if ( RefsStatusDebugEnabled )
                    RefsStatusDebug(0);
                  Status = Information;
                  Exception = Information;
                  v9 = *(union _LARGE_INTEGER **)v178;
                  LOBYTE(Flags_low) = BYTE1(v172);
                  v20 = v172;
                  v3 = (LARGE_INTEGER *)Context;
                  v2 = Irp;
                }
                else
                {
                  if ( v9[31].LowPart
                    && (v9[38].LowPart & 0x40000) == 0
                    && !(unsigned __int8)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))RefsReserveClusters)(
                                           v3,
                                           v9,
                                           (union _LARGE_INTEGER)FileOffset[0].QuadPart,
                                           (unsigned int)Length) )
                  {
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                    {
                      WPP_SF_D(
                        WPP_GLOBAL_Control->AttachedDevice,
                        50,
                        WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids,
                        3221225599LL);
                    }
                    if ( RefsStatusDebugEnabled )
                      RefsStatusDebug(-1073741697);
                    RefsRaiseStatusInternal(Context, 3221225599LL);
                  }
                  if ( (v3[5].LowPart & 0x200) != 0 )
                  {
                    CcPrepareMdlWrite(FileObject, FileOffset, Length, &v2->MdlAddress, &v2->IoStatus);
                    Status = v2->IoStatus.Status;
                    Exception = Status;
                  }
                  else
                  {
                    v225 = (PVOID)RefsMapUserBuffer(v2, v48, v56, v57);
                    if ( !CcCopyWrite(v136, FileOffset, Length, v3[1].LowPart & 1, v225) )
                    {
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                      {
                        WPP_SF_D(
                          WPP_GLOBAL_Control->AttachedDevice,
                          51,
                          WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids,
                          3221225688LL);
                      }
                      if ( RefsStatusDebugEnabled )
                        RefsStatusDebug(-1073741608);
                      RefsRaiseStatusInternal(Context, 3221225688LL);
                    }
                    v138 = v3[2].LowPart;
                    if ( (int)v138 < 0 )
                    {
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                      {
                        WPP_SF_D(
                          WPP_GLOBAL_Control->AttachedDevice,
                          52,
                          WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids,
                          v138);
                      }
                      if ( RefsStatusDebugEnabled )
                        RefsStatusDebug(v3[2].LowPart);
                      RefsRaiseStatusInternal(Context, v3[2].LowPart);
                    }
                    v2->IoStatus.Status = Information;
                    v2->IoStatus.Information = (unsigned int)Length;
                    Status = Information;
                    Exception = Information;
                  }
                  if ( (*(_DWORD *)(v9[16].QuadPart + 4) & 0x4000000) != 0 && (unsigned int)Length >= 0x10000 )
                  {
                    IoStatus = 0;
                    CcFlushCache((PSECTION_OBJECT_POINTERS)(v9[30].QuadPart + 8), FileOffset, Length, &IoStatus);
                    v139 = v3[2].LowPart;
                    if ( (int)v139 < 0 )
                    {
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                      {
                        WPP_SF_D(
                          WPP_GLOBAL_Control->AttachedDevice,
                          53,
                          WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids,
                          v139);
                      }
                      if ( RefsStatusDebugEnabled )
                        RefsStatusDebug(v3[2].LowPart);
                      RefsRaiseStatusInternal(Context, v3[2].LowPart);
                    }
                    if ( IoStatus.Status < 0 )
                    {
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                      {
                        WPP_SF_D(
                          WPP_GLOBAL_Control->AttachedDevice,
                          54,
                          WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids,
                          (unsigned int)IoStatus.Status);
                      }
                      if ( RefsStatusDebugEnabled )
                        RefsStatusDebug(IoStatus.Status);
                      RefsRaiseStatusInternal(Context, (unsigned int)IoStatus.Status);
                      goto LABEL_557;
                    }
                  }
                }
                goto LABEL_159;
              }
              v76 = v186;
              goto LABEL_264;
            }
            if ( (*v209 & 2) == 0
              && (CurrentStackLocation->Flags & 0x10) == 0
              && v24.QuadPart >= 0
              && v24.QuadPart < v9[4].QuadPart
              && v26 > (unsigned int)(16 * *(_DWORD *)(v5 + 276)) )
            {
              v154 = v3[18];
              if ( v154.QuadPart && (v186->LowPart & 0x8000) != 0 )
                *(_QWORD *)(v154.QuadPart + 288) = 3;
              if ( (v20 & 0x40) != 0 )
                ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))RefsReleasePagingFastResource)(
                  (LARGE_INTEGER)v154.QuadPart,
                  v9,
                  v215);
              RefsCompleteWriteRequest(v3, v2, 3221225506LL);
              return 3221225506LL;
            }
            if ( (v21[1] & 0x100) != 0 )
            {
LABEL_581:
              if ( ((unsigned __int8)Flags_low & 0x40) == 0 )
                RefsSetIoContextAsync((_DWORD)v3, 0, 0, 0, 0, v24.QuadPart, LowPart, 1, LowPart);
              FileObject->Flags |= 0x1000u;
              v142 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))RefsVolumeDasdIo)(
                       v3,
                       v2,
                       v9,
                       v21,
                       (union _LARGE_INTEGER)FileOffset[0].QuadPart,
                       Length);
              v144 = v142;
              if ( ((unsigned __int8)Flags_low & 8) != 0 && (v20 & 0x20) == 0 && v142 >= 0 )
                FileObject->CurrentByteOffset.QuadPart = FileOffset[0].QuadPart + v2->IoStatus.Information;
              if ( (v20 & 0x40) != 0 )
                RefsReleasePagingFastResource(v143, v9, v215);
              if ( ((unsigned __int8)Flags_low & 0x40) != 0 )
              {
                RefsCompleteWriteRequest(v3, v2, v144);
                return v144;
              }
              return v144;
            }
            if ( v24.QuadPart >= 0 )
            {
              v155 = v9[4].QuadPart;
              if ( v155 > v24.QuadPart )
              {
                if ( v155 < v26 )
                {
                  LowPart = v155 - FileOffset[0].LowPart;
                  LODWORD(Length) = v155 - FileOffset[0].LowPart;
                }
                goto LABEL_581;
              }
            }
            v156 = v3[18];
            if ( v156.QuadPart && (v186->LowPart & 0x8000) != 0 )
              *(_QWORD *)(v156.QuadPart + 288) = 3;
            if ( (v20 & 0x40) != 0 )
              ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))RefsReleasePagingFastResource)(
                (LARGE_INTEGER)v156.QuadPart,
                v9,
                v215);
          }
          else
          {
            *(_QWORD *)(v3[18].QuadPart + 288) = 8;
            v2->IoStatus.Information = 0;
          }
          RefsCompleteWriteRequest(v3, v2, 0);
          return 0;
        }
        v21 = (_DWORD *)v187;
      }
      if ( (v9[31].QuadPart & 0x800000000000LL) != 0 )
        goto LABEL_665;
      v5 = v194;
      v9 = *(union _LARGE_INTEGER **)v178;
      v21 = v199;
      Flags_low = (volatile signed __int32 *)BYTE1(v172);
      v20 = v172;
      v3 = (LARGE_INTEGER *)Context;
      v2 = Irp;
      v187 = (__int64)v199;
      if ( RefsDebugForceSynchronous )
      {
LABEL_665:
        LOBYTE(Flags_low) = (unsigned __int8)Flags_low | 0x40;
        BYTE1(v172) = (_BYTE)Flags_low;
        v22 = v186;
        v186->LowPart |= 1u;
        goto LABEL_24;
      }
    }
    v22 = v186;
    goto LABEL_24;
  }
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(-1073740659);
  RefsExtendedCompleteRequestInternal(Context, Irp, 3221226637LL);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_6aacebc266ac3269315b387f9bbedff0_Traceguids, 3221226637LL);
  }
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(-1073740659);
  return 3221226637LL;
}

```

## disassembly

```asm
0x1c000a190  mov     r11, rsp
0x1c000a193  mov     [r11+18h], rbx
0x1c000a197  mov     [r11+20h], rsi
0x1c000a19b  push    rdi
0x1c000a19c  push    r12
0x1c000a19e  push    r13
0x1c000a1a0  push    r14
0x1c000a1a2  push    r15
0x1c000a1a4  sub     rsp, 2A0h
0x1c000a1ab  mov     rax, cs:__security_cookie
0x1c000a1b2  xor     rax, rsp
0x1c000a1b5  mov     [rsp+2C8h+var_30], rax
0x1c000a1bd  mov     r13, rdx
0x1c000a1c0  mov     r15, rcx
0x1c000a1c3  mov     [r11-248h], rcx
0x1c000a1ca  mov     [r11-230h], rdx
0x1c000a1d1  mov     [rsp+2C8h+var_140], rdx
0x1c000a1d9  xor     ebx, ebx
0x1c000a1db  mov     edi, ebx
0x1c000a1dd  mov     [r11-1C0h], rbx
0x1c000a1e4  mov     edx, ebx
0x1c000a1e6  mov     [r11-1A0h], rbx
0x1c000a1ed  xorps   xmm0, xmm0
0x1c000a1f0  movdqu  xmmword ptr [rsp+2C8h+FileOffset], xmm0
0x1c000a1f9  mov     [r11-1D8h], rbx
0x1c000a200  mov     [rsp+2C8h+var_1B8], ebx
0x1c000a207  mov     [rsp+2C8h+var_190], ebx
0x1c000a20e  mov     [rsp+2C8h+var_1B0], ebx
0x1c000a215  mov     [rsp+2C8h+var_254], bl
0x1c000a219  mov     [rsp+2C8h+var_240], bl
0x1c000a220  xor     eax, eax
0x1c000a222  movups  [rsp+2C8h+var_118], xmm0
0x1c000a22a  movups  [rsp+2C8h+var_108], xmm0
0x1c000a232  movups  [rsp+2C8h+var_F8], xmm0
0x1c000a23a  movups  [rsp+2C8h+var_E8], xmm0
0x1c000a242  movups  [rsp+2C8h+var_D8], xmm0
0x1c000a24a  mov     [r11-0C8h], rax
0x1c000a251  mov     [rsp+2C8h+var_258], ebx
0x1c000a255  lea     rax, [r11-1F8h]
0x1c000a25c  mov     [r11-1F0h], rax
0x1c000a263  lea     rax, [r11-1F8h]
0x1c000a26a  mov     [r11-1F8h], rax
0x1c000a271  mov     rax, [r13+0B8h]
0x1c000a278  mov     [rsp+2C8h+var_198], rax
0x1c000a280  mov     [rsp+2C8h+var_B0], rax
0x1c000a288  mov     r9, [rax+30h]
0x1c000a28c  mov     [rsp+2C8h+FileObject], r9
0x1c000a294  mov     [rsp+2C8h+var_138], r9
0x1c000a29c  mov     rax, [r9+18h]
0x1c000a2a0  mov     [rsp+2C8h+var_150], rax
0x1c000a2a8  mov     r14, rax
0x1c000a2ab  mov     [r11-238h], rax
0x1c000a2b2  mov     [rsp+2C8h+var_178], rax
0x1c000a2ba  mov     [rsp+2C8h+var_148], rax
0x1c000a2c2  test    rax, rax
0x1c000a2c5  jz      loc_1C00705A9
0x1c000a2cb  mov     rdi, [rax+80h]
0x1c000a2d2  mov     [r11-1C0h], rdi
0x1c000a2d9  mov     rcx, [r9+20h]
0x1c000a2dd  mov     [r11-208h], rcx
0x1c000a2e4  mov     [r11-1A8h], rcx
0x1c000a2eb  mov     rdx, [rax+78h]
0x1c000a2ef  mov     [r11-1A0h], rdx
0x1c000a2f6  mov     eax, [rdi+4]
0x1c000a2f9  test    al, 1
0x1c000a2fb  jz      loc_1C000CD91
0x1c000a301  mov     [rsp+2C8h+var_1AC], 1
0x1c000a30c  test    rcx, rcx
0x1c000a30f  jz      loc_1C007059E
0x1c000a315  movzx   r8d, byte ptr [rcx+50h]
0x1c000a31a  mov     [rsp+2C8h+var_218], r8d
0x1c000a322  mov     [rsp+2C8h+var_170], rdi
0x1c000a32a  lea     eax, [r8-2]
0x1c000a32e  test    eax, 0FFFFFFFCh
0x1c000a333  jnz     loc_1C0071161
0x1c000a339  cmp     r8d, 3
0x1c000a33d  jz      loc_1C0071161
0x1c000a343  cmp     qword ptr [rdx+10h], 520h
0x1c000a34b  jz      loc_1C000CDB1
0x1c000a351  lea     r10, [r15+68h]
0x1c000a355  mov     [rsp+2C8h+var_1D0], r10
0x1c000a35d  mov     rax, [r10]
0x1c000a360  mov     esi, [rax+10h]
0x1c000a363  test    esi, esi
0x1c000a365  js      loc_1C00705CD
0x1c000a36b  lea     rcx, [rdi+4]
0x1c000a36f  mov     [rsp+2C8h+var_158], rcx
0x1c000a377  mov     eax, [rcx]
0x1c000a379  and     eax, 0A000021h
0x1c000a37e  cmp     eax, 1
0x1c000a381  jnz     loc_1C000CDC4
0x1c000a387  lea     rax, [r14+130h]
0x1c000a38e  mov     [rsp+2C8h+var_160], rax
0x1c000a396  mov     eax, [rax]
0x1c000a398  bt      eax, 18h
0x1c000a39c  jb      loc_1C0070855
0x1c000a3a2  lea     rax, [r15+8]
0x1c000a3a6  mov     [rsp+2C8h+var_210], rax
0x1c000a3ae  movzx   eax, byte ptr [rax]
0x1c000a3b1  and     al, 1
0x1c000a3b3  shl     al, 6
0x1c000a3b6  mov     ecx, [r13+10h]
0x1c000a3ba  test    cl, 2
0x1c000a3bd  jnz     loc_1C00708C0
0x1c000a3c3  xor     dl, dl
0x1c000a3c5  movzx   esi, byte ptr [rsp+2C8h+var_258]
0x1c000a3ca  and     sil, 0DFh
0x1c000a3ce  or      sil, dl
0x1c000a3d1  test    cl, 1
0x1c000a3d4  jz      loc_1C00708C7
0x1c000a3da  mov     cl, 4
0x1c000a3dc  and     sil, 0FBh
0x1c000a3e0  or      sil, cl
0x1c000a3e3  movzx   r12d, byte ptr [r9+50h]
0x1c000a3e8  and     r12b, 2
0x1c000a3ec  shl     r12b, 2
0x1c000a3f0  or      r12b, al
0x1c000a3f3  mov     byte ptr [rsp+2C8h+var_258+1], r12b
0x1c000a3f8  cmp     r15, [r10]
0x1c000a3fb  jnz     loc_1C00708CE
0x1c000a401  call    cs:__imp_IoGetTopLevelIrp
0x1c000a408  nop     dword ptr [rax+rax+00h]
0x1c000a40d  cmp     [rax], bl
0x1c000a40f  jz      loc_1C00708CE
0x1c000a415  mov     al, 8
0x1c000a417  and     sil, 0F7h
0x1c000a41b  or      sil, al
0x1c000a41e  mov     byte ptr [rsp+2C8h+var_258], sil
0x1c000a423  mov     r11, [rsp+2C8h+var_208]
0x1c000a42b  test    r11, r11
0x1c000a42e  jz      short loc_1C000A43E
0x1c000a430  test    dword ptr [r11+4], 2000h
0x1c000a438  jnz     loc_1C00708D5
0x1c000a43e  cmp     [r14+140h], ebx
0x1c000a445  jnz     loc_1C0070946
0x1c000a44b  test    r12b, 40h
0x1c000a44f  jnz     short loc_1C000A45B
0x1c000a451  test    sil, 20h
0x1c000a455  jnz     loc_1C00709EC
0x1c000a45b  mov     rdx, [rsp+2C8h+var_210]
0x1c000a463  mov     ecx, [rdx]
0x1c000a465  mov     r8, [rsp+2C8h+var_198]
0x1c000a46d  bt      ecx, 11h
0x1c000a471  jb      loc_1C0070AAE
0x1c000a477  mov     rcx, [r8+18h]
0x1c000a47b  mov     [rsp+2C8h+var_200], rcx
0x1c000a483  mov     qword ptr [rsp+2C8h+FileOffset], rcx
0x1c000a48b  mov     r10d, [r8+8]
0x1c000a48f  mov     [rsp+2C8h+var_1C8], r10d
0x1c000a497  mov     dword ptr [rsp+2C8h+Length], r10d
0x1c000a49f  lea     rax, WPP_GLOBAL_Control
0x1c000a4a6  mov     rdx, cs:WPP_GLOBAL_Control
0x1c000a4ad  mov     [rsp+2C8h+var_180], rdx
0x1c000a4b5  cmp     rdx, rax
0x1c000a4b8  jz      short loc_1C000A4C5
0x1c000a4ba  mov     eax, [rdx+2Ch]
0x1c000a4bd  test    al, 10h
0x1c000a4bf  jnz     loc_1C0070AD3
0x1c000a4c5  mov     edx, r10d
0x1c000a4c8  mov     rax, 7FFFFFFFFFFFFFFFh
0x1c000a4d2  sub     rax, rcx
0x1c000a4d5  cmp     rax, rdx
0x1c000a4d8  jl      loc_1C0070BD9
0x1c000a4de  lea     r8, [rdx+rcx]
0x1c000a4e2  mov     qword ptr [rsp+2C8h+FileOffset+8], r8
0x1c000a4ea  test    r10d, r10d
0x1c000a4ed  jz      loc_1C0070C43
0x1c000a4f3  movzx   edx, sil
0x1c000a4f7  shr     dl, 2
0x1c000a4fa  mov     [rsp+2C8h+var_228], dl
0x1c000a501  movzx   r9d, dl
0x1c000a505  and     r9b, 1
0x1c000a509  mov     [rsp+2C8h+var_24C], r9b
0x1c000a50e  jz      loc_1C0070C80
0x1c000a514  cmp     [rdi+0F68h], rbx
0x1c000a51b  jz      loc_1C000A5CF
0x1c000a521  mov     eax, [r15+4]
0x1c000a525  test    al, 8
0x1c000a527  jnz     loc_1C0070DF9
0x1c000a52d  xor     ecx, ecx; PerformanceFrequency
0x1c000a52f  call    cs:__imp_KeQueryPerformanceCounter
0x1c000a536  nop     dword ptr [rax+rax+00h]
0x1c000a53b  movzx   edx, [rsp+2C8h+var_228]
0x1c000a543  mov     r11, [rsp+2C8h+var_208]
0x1c000a54b  movzx   r9d, [rsp+2C8h+var_24C]
0x1c000a551  mov     rcx, [r15+90h]
0x1c000a558  mov     [rcx+120h], rax
0x1c000a55f  mov     [rsp+2C8h+var_1C8], ebx
0x1c000a566  mov     rax, [rsp+2C8h+var_210]
0x1c000a56e  mov     ecx, [rax]
0x1c000a570  shr     ecx, 2
0x1c000a573  and     cl, 2
0x1c000a576  test    sil, 24h
0x1c000a57a  mov     eax, ebx
0x1c000a57c  mov     r8d, 4
0x1c000a582  cmovz   eax, r8d
0x1c000a586  or      cl, al
0x1c000a588  movzx   eax, r12b
0x1c000a58c  shr     al, 6
0x1c000a58f  and     al, 1
0x1c000a591  or      cl, al
0x1c000a593  and     dl, 8
0x1c000a596  or      cl, dl
0x1c000a598  mov     byte ptr [rsp+2C8h+var_1C8+3], cl
0x1c000a59f  mov     rcx, [r15+90h]
0x1c000a5a6  mov     eax, [rsp+2C8h+var_1C8]
0x1c000a5ad  or      [rcx], eax
0x1c000a5af  mov     r10d, dword ptr [rsp+2C8h+Length]
0x1c000a5b7  mov     r8, qword ptr [rsp+2C8h+FileOffset+8]
0x1c000a5bf  mov     rcx, qword ptr [rsp+2C8h+FileOffset]
0x1c000a5c7  mov     [rsp+2C8h+var_200], rcx
0x1c000a5cf  mov     edx, [rsp+2C8h+var_218]
0x1c000a5d6  cmp     edx, 4
0x1c000a5d9  jz      loc_1C000CDF9
0x1c000a5df  movzx   r8d, sil
0x1c000a5e3  shr     r8b, 5
0x1c000a5e7  and     r8b, 1
0x1c000a5eb  jnz     loc_1C0070F4A
0x1c000a5f1  movzx   eax, sil
0x1c000a5f5  and     al, 24h
0x1c000a5f7  cmp     al, 4
0x1c000a5f9  jz      short loc_1C000A61A
0x1c000a5fb  mov     [r14+0A8h], ebx
0x1c000a602  mov     r10d, dword ptr [rsp+2C8h+Length]
0x1c000a60a  mov     rcx, qword ptr [rsp+2C8h+FileOffset]
0x1c000a612  mov     [rsp+2C8h+var_200], rcx
0x1c000a61a  mov     [rsp+2C8h+Exception], ebx
0x1c000a61e  mov     qword ptr [rsp+2C8h+var_D8+8], rbx
0x1c000a626  mov     [rsp+2C8h+var_C8], rbx
0x1c000a62e  mov     dword ptr [rsp+2C8h+var_D8+0Ch], 1
0x1c000a639  test    r8b, r8b
0x1c000a63c  jnz     loc_1C000B551
0x1c000a642  test    r11, r11
0x1c000a645  jz      short loc_1C000A66A
0x1c000a647  mov     eax, [r11+54h]
0x1c000a64b  mov     [r15+0C8h], eax
0x1c000a652  mov     r10d, dword ptr [rsp+2C8h+Length]
0x1c000a65a  mov     rcx, qword ptr [rsp+2C8h+FileOffset]
0x1c000a662  mov     [rsp+2C8h+var_200], rcx
0x1c000a66a  test    sil, 40h
0x1c000a66e  jnz     loc_1C000AE06
0x1c000a674  mov     rax, [rsp+2C8h+var_210]
0x1c000a67c  mov     eax, [rax]
0x1c000a67e  bt      eax, 8
0x1c000a682  jb      loc_1C000ACDA
0x1c000a688  cmp     edx, 5
0x1c000a68b  mov     rdx, [rsp+2C8h+FileObject]
0x1c000a693  jz      short loc_1C000A6AC
0x1c000a695  test    r9b, r9b
0x1c000a698  jz      loc_1C000ACCB
0x1c000a69e  mov     rax, [rdx+28h]
0x1c000a6a2  cmp     qword ptr [rax], 0
0x1c000a6a6  jnz     loc_1C000ACDA
0x1c000a6ac  test    r9b, r9b
0x1c000a6af  jz      loc_1C000ACCB
0x1c000a6b5  test    rcx, rcx
0x1c000a6b8  js      loc_1C000ACDA
0x1c000a6be  movzx   edi, r12b
0x1c000a6c2  shr     dil, 6
0x1c000a6c6  and     dil, 1
0x1c000a6ca  mov     rcx, rbx
0x1c000a6cd  mov     eax, 802h
0x1c000a6d2  cmp     ax, [r14]
0x1c000a6d6  jz      loc_1C000AD20
0x1c000a6dc  cmp     [r14+10h], rbx
0x1c000a6e0  jz      short loc_1C000A6E6
0x1c000a6e2  mov     rcx, [r14+78h]
0x1c000a6e6  movzx   r8d, dil
0x1c000a6ea  lea     rdx, [rsp+2C8h+var_118]
0x1c000a6f2  mov     rcx, [rcx+68h]
0x1c000a6f6  call    MsAcquireFastResourceShared
0x1c000a6fb  shl     al, 6
0x1c000a6fe  xor     al, sil
0x1c000a701  and     al, 40h
0x1c000a703  xor     sil, al
0x1c000a706  mov     byte ptr [rsp+2C8h+var_258], sil
0x1c000a70b  mov     r9d, [rsp+2C8h+var_218]
0x1c000a713  mov     rdx, [rsp+2C8h+FileObject]
0x1c000a71b  cmp     r9d, 5
0x1c000a71f  jz      short loc_1C000A735
0x1c000a721  test    sil, 4
0x1c000a725  jz      short loc_1C000A735
0x1c000a727  mov     rax, [rdx+28h]
0x1c000a72b  cmp     qword ptr [rax], 0
0x1c000a72f  jnz     loc_1C000AD37
0x1c000a735  movzx   ecx, sil
0x1c000a739  test    sil, 4
0x1c000a73d  jz      loc_1C000AD28
0x1c000a743  test    cl, 40h
0x1c000a746  jz      loc_1C000AD8E
0x1c000a74c  mov     r10d, dword ptr [rsp+2C8h+Length]
0x1c000a754  mov     rcx, qword ptr [rsp+2C8h+FileOffset]
0x1c000a75c  mov     [rsp+2C8h+var_200], rcx
0x1c000a764  mov     r11, [rsp+2C8h+var_208]
0x1c000a76c  mov     rdx, [rsp+2C8h+var_1A0]
0x1c000a774  mov     eax, [rdx+4]
0x1c000a777  test    al, 20h
0x1c000a779  jnz     loc_1C000AE13
0x1c000a77f  bt      eax, 18h
0x1c000a783  jb      loc_1C000AFA0
  ... truncated ...
```
