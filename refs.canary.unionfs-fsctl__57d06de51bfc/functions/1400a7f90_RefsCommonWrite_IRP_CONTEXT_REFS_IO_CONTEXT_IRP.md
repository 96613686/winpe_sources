# RefsCommonWrite(_IRP_CONTEXT *,REFS_IO_CONTEXT *,_IRP *)

- ea: `0x1400a7f90`
- end: `0x1400aba2c`
- name: `?RefsCommonWrite@@YAJPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@PEAU_IRP@@@Z`
- size: `15004`
- prototype: `__int64 __fastcall(struct _IRP_CONTEXT *, struct REFS_IO_CONTEXT *, PIRP Irp)`
- caller_count: `3`
- callee_count: `48`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400a4ff0`
- `0x1400bc440`
- `0x14032c860`

## callees

- `0x140008c10`
- `0x140008fd0`
- `0x140009af0`
- `0x140009c20`
- `0x14000a370`
- `0x14000bcc0`
- `0x14003d1d8`
- `0x140041a40`
- `0x140041b40`
- `0x14007c580`
- `0x140080834`
- `0x1400815e0`
- `0x140081670`
- `0x14008dbd0`
- `0x14008e360`
- `0x140096fd0`
- `0x1400994e0`
- `0x14009ca80`
- `0x14009ccb0`
- `0x1400a11b0`
- `0x1400a38b0`
- `0x1400a7f90`
- `0x1400abbc8`
- `0x1400ac4c8`
- `0x1400ae910`
- `0x1400af2cc`
- `0x1400b0470`
- `0x1400b87a0`
- `0x1400c8024`
- `0x1400ca788`
- `0x1400e1498`
- `0x1400ef56c`
- `0x1400fa85c`
- `0x140106810`
- `0x140106b88`
- `0x140106c88`
- `0x140106cf0`
- `0x14010d8f8`
- `0x1401e9ce0`
- `0x1402fec90`
- `0x1402fed30`
- `0x1403000b0`
- `0x1403021e0`
- `0x140320330`
- `0x140325110`
- `0x14032ae48`
- `0x1403390c4`
- `0x14033b8d0`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x1400a8988`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400a9ed4`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400a9ee9`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400aa10e`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400a8988`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400a9ed4`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400a9ee9`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400aa10e`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400aaaad`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400aaaad`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a830b`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a8325`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a850d`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a8527`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a86d6`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a86f0`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a8884`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a889e`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a8aff`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a8b19`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a8cce`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a8ce8`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a8e86`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a8ea0`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a91e3`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a91fd`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400ab34a`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400ab364`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a830b`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a8325`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a850d`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a8527`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a86d6`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a86f0`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a8884`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a889e`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a8aff`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a8b19`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a8cce`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a8ce8`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a8e86`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a8ea0`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a91e3`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a91fd`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400ab34a`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400ab364`
- `ntoskrnl!ExRaiseStatus` at `0x1400a8110`
- `ntoskrnl!ExRaiseStatus` at `0x1400aadb1`
- `ntoskrnl!ExRaiseStatus` at `0x1400a8110`
- `ntoskrnl!ExRaiseStatus` at `0x1400aadb1`
- `ntoskrnl!DbgPrintEx` at `0x1400a82a9`
- `ntoskrnl!DbgPrintEx` at `0x1400a84ab`
- `ntoskrnl!DbgPrintEx` at `0x1400a866f`
- `ntoskrnl!DbgPrintEx` at `0x1400a881d`
- `ntoskrnl!DbgPrintEx` at `0x1400a8a98`
- `ntoskrnl!DbgPrintEx` at `0x1400a8c67`
- `ntoskrnl!DbgPrintEx` at `0x1400a8e1f`
- `ntoskrnl!DbgPrintEx` at `0x1400a917c`
- `ntoskrnl!DbgPrintEx` at `0x1400ab2e3`
- `ntoskrnl!DbgPrintEx` at `0x1400a82a9`
- `ntoskrnl!DbgPrintEx` at `0x1400a84ab`
- `ntoskrnl!DbgPrintEx` at `0x1400a866f`
- `ntoskrnl!DbgPrintEx` at `0x1400a881d`
- `ntoskrnl!DbgPrintEx` at `0x1400a8a98`
- `ntoskrnl!DbgPrintEx` at `0x1400a8c67`
- `ntoskrnl!DbgPrintEx` at `0x1400a8e1f`
- `ntoskrnl!DbgPrintEx` at `0x1400a917c`
- `ntoskrnl!DbgPrintEx` at `0x1400ab2e3`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400a82d1`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400a84d3`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400a869c`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400a884a`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400a8ac5`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400a8c94`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400a8e4c`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400a91a9`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400ab310`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400a82d1`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400a84d3`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400a869c`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400a884a`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400a8ac5`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400a8c94`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400a8e4c`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400a91a9`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400ab310`
- `ntoskrnl!_strnicmp` at `0x1400a8350`
- `ntoskrnl!_strnicmp` at `0x1400a8552`
- `ntoskrnl!_strnicmp` at `0x1400a871b`
- `ntoskrnl!_strnicmp` at `0x1400a88c9`
- `ntoskrnl!_strnicmp` at `0x1400a8b44`
- `ntoskrnl!_strnicmp` at `0x1400a8d13`
- `ntoskrnl!_strnicmp` at `0x1400a8ecb`
- `ntoskrnl!_strnicmp` at `0x1400a9228`
- `ntoskrnl!_strnicmp` at `0x1400ab38f`
- `ntoskrnl!_strnicmp` at `0x1400a8350`
- `ntoskrnl!_strnicmp` at `0x1400a8552`
- `ntoskrnl!_strnicmp` at `0x1400a871b`
- `ntoskrnl!_strnicmp` at `0x1400a88c9`
- `ntoskrnl!_strnicmp` at `0x1400a8b44`
- `ntoskrnl!_strnicmp` at `0x1400a8d13`
- `ntoskrnl!_strnicmp` at `0x1400a8ecb`
- `ntoskrnl!_strnicmp` at `0x1400a9228`
- `ntoskrnl!_strnicmp` at `0x1400ab38f`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400a8334`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400a8536`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400a86ff`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400a88ad`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400a8b28`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400a8cf7`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400a8eaf`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400a920c`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400ab373`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400a8334`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400a8536`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400a86ff`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400a88ad`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400a8b28`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400a8cf7`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400a8eaf`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400a920c`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400ab373`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400aab0b`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400aab0b`
- `ntoskrnl!CcCopyWrite` at `0x1400aaf6a`
- `ntoskrnl!CcCopyWrite` at `0x1400aaf6a`
- `ntoskrnl!CcSetParallelFlushFile` at `0x1400aaead`
- `ntoskrnl!CcSetParallelFlushFile` at `0x1400aaead`
- `ntoskrnl!ExIsFastResourceHeld` at `0x1400a9f16`
- `ntoskrnl!ExIsFastResourceHeld` at `0x1400a9f39`
- `ntoskrnl!ExIsFastResourceHeld` at `0x1400a9f16`
- `ntoskrnl!ExIsFastResourceHeld` at `0x1400a9f39`
- `ntoskrnl!CcCanIWrite` at `0x1400a92f2`
- `ntoskrnl!CcCanIWrite` at `0x1400a92f2`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1400aa17f`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1400ab0b7`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1401eb7af`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1400aa17f`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1400ab0b7`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1401eb7af`
- `ntoskrnl!CcSetReadAheadGranularity` at `0x1400aae9c`
- `ntoskrnl!CcSetReadAheadGranularity` at `0x1400aae9c`
- `ntoskrnl!CcDeferWrite` at `0x1400a937b`
- `ntoskrnl!CcDeferWrite` at `0x1400a937b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400aa18e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400ab0c6`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401eb7be`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400aa18e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400ab0c6`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401eb7be`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x1400aa7b0`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x1400aa7b0`
- `ntoskrnl!FsRtlCheckLockForWriteAccess` at `0x1400aa814`
- `ntoskrnl!FsRtlCheckLockForWriteAccess` at `0x1400aa814`
- `ntoskrnl!FsRtlCheckOplock` at `0x1400aa61a`
- `ntoskrnl!FsRtlCheckOplock` at `0x1400aa61a`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x1400aada3`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x1400aada3`
- `ntoskrnl!CcFlushCache` at `0x1400ab02d`
- `ntoskrnl!CcFlushCache` at `0x1400ab02d`
- `ntoskrnl!CcPrepareMdlWrite` at `0x1400aafca`
- `ntoskrnl!CcPrepareMdlWrite` at `0x1400aafca`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400aa222`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400aa36c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400aa44e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400ab173`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401eb867`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400aa222`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400aa36c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400aa44e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400ab173`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401eb867`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400aa22e`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400aa378`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400aa45a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400ab17f`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1401eb873`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400aa22e`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400aa378`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400aa45a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400ab17f`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1401eb873`
- `ntoskrnl!ExReleaseFastResource` at `0x1400a93bf`
- `ntoskrnl!ExReleaseFastResource` at `0x1400a9533`
- `ntoskrnl!ExReleaseFastResource` at `0x1400a95f6`
- `ntoskrnl!ExReleaseFastResource` at `0x1400a96b2`
- `ntoskrnl!ExReleaseFastResource` at `0x1400ab215`
- `ntoskrnl!ExReleaseFastResource` at `0x1401eb922`
- `ntoskrnl!ExReleaseFastResource` at `0x1400a93bf`
- `ntoskrnl!ExReleaseFastResource` at `0x1400a9533`
- `ntoskrnl!ExReleaseFastResource` at `0x1400a95f6`
- `ntoskrnl!ExReleaseFastResource` at `0x1400a96b2`
- `ntoskrnl!ExReleaseFastResource` at `0x1400ab215`
- `ntoskrnl!ExReleaseFastResource` at `0x1401eb922`
- `HAL!KeQueryPerformanceCounter` at `0x1400a9343`
- `HAL!KeQueryPerformanceCounter` at `0x1400a9434`
- `HAL!KeQueryPerformanceCounter` at `0x1400a9343`
- `HAL!KeQueryPerformanceCounter` at `0x1400a9434`

## string_xrefs

- `0x1400a81c6`: `write.c`
- `0x1400a8274`: `write.c`
- `0x1400a8476`: `write.c`
- `0x1400a8639`: `write.c`
- `0x1400a87e7`: `write.c`
- `0x1400a8a62`: `write.c`
- `0x1400a8c31`: `write.c`
- `0x1400a8de9`: `write.c`
- `0x1400a9146`: `write.c`
- `0x1400a9ace`: `write.c`
- `0x1400aa27e`: `write.c`
- `0x1400aa3cc`: `write.c`
- `0x1400aa6b6`: `write.c`
- `0x1400aad89`: `write.c`
- `0x1400ab2ad`: `write.c`
- `0x1400ab464`: `write.c`
- `0x1400ab4cc`: `write.c`
- `0x1400ab534`: `write.c`
- `0x1400ab59c`: `write.c`
- `0x1400ab604`: `write.c`
- `0x1400ab669`: `write.c`
- `0x1400ab6cd`: `write.c`
- `0x1400ab735`: `write.c`
- `0x1400ab7a2`: `write.c`
- `0x1400ab81d`: `write.c`
- `0x1400ab87f`: `write.c`
- `0x1400ab8e7`: `write.c`
- `0x1400ab949`: `write.c`
- `0x1400ab9a7`: `write.c`
- `0x1400aba05`: `write.c`

## pseudocode

```c
__int64 __fastcall RefsCommonWrite(struct _IRP_CONTEXT *a1, struct REFS_IO_CONTEXT *a2, PIRP Irp)
{
  PIRP v3; // rbx
  struct _IRP_CONTEXT *v5; // rdi
  struct _FILE_OBJECT *v6; // r8
  __int64 FsContext; // rsi
  __int64 v8; // r9
  char *FsContext2; // r13
  int v10; // ecx
  __int64 v11; // r9
  char v12; // dl
  PMRX_NET_ROOT pNetRoot; // rax
  int v14; // r14d
  volatile unsigned int v15; // esi
  struct _KPROCESS *v16; // rsi
  PEPROCESS v17; // rax
  const char *v18; // rax
  __int64 v19; // rcx
  int v21; // eax
  volatile unsigned int v22; // edi
  struct _KPROCESS *v23; // rdi
  PEPROCESS v24; // rax
  const char *v25; // rax
  __int64 v26; // rcx
  volatile unsigned int v27; // edi
  struct _KPROCESS *v28; // rdi
  PEPROCESS v29; // rax
  const char *v30; // rax
  __int64 v31; // rcx
  volatile unsigned int v32; // edi
  struct _KPROCESS *v33; // rdi
  PEPROCESS v34; // rax
  const char *v35; // rax
  __int64 v36; // rdx
  char v37; // r15
  NTSTATUS Flags; // r14d
  char v39; // al
  char v40; // r15
  __int64 v41; // rax
  __int64 v42; // rax
  volatile unsigned int v43; // edi
  struct _KPROCESS *v44; // rdi
  PEPROCESS v45; // rax
  const char *v46; // rax
  __int64 v47; // rdx
  volatile unsigned int v48; // edi
  struct _KPROCESS *v49; // rdi
  PEPROCESS v50; // rax
  const char *v51; // rax
  __int64 v52; // rcx
  volatile unsigned int v53; // edi
  struct _KPROCESS *v54; // rdi
  PEPROCESS v55; // rax
  const char *v56; // rax
  __int64 v57; // rdx
  __int64 v58; // rcx
  struct _IO_STACK_LOCATION *v59; // rdx
  ULONG v60; // r10d
  __int64 QuadPart; // rcx
  union _LARGE_INTEGER v62; // rdx
  const char *v63; // r11
  const char *v64; // r10
  const char *v65; // r9
  const char *v66; // r8
  const char *v67; // rdx
  const char *v68; // rax
  volatile unsigned int v69; // edi
  struct _KPROCESS *v70; // rdi
  PEPROCESS v71; // rax
  const char *v72; // rax
  __int64 v73; // rdx
  __int64 v74; // rax
  int v75; // ebx
  PVOID v76; // r12
  __int64 v77; // rcx
  __int64 v78; // rcx
  LARGE_INTEGER PerformanceCounter; // rax
  __int64 v80; // r9
  char v81; // dl
  char v82; // r10
  __int64 v83; // rdx
  __int64 v84; // rcx
  union _LARGE_INTEGER v85; // rcx
  unsigned int v86; // ecx
  __int64 v87; // rcx
  unsigned __int8 v88; // r9
  int v89; // r12d
  __int64 v90; // rcx
  unsigned int v91; // r8d
  __int64 v92; // rcx
  _DWORD *v93; // rdx
  __int16 v94; // ax
  bool v95; // dl
  unsigned int v96; // r8d
  int v97; // eax
  char v98; // al
  __int64 v99; // rcx
  char v100; // al
  PFILE_OBJECT v101; // rcx
  char *v102; // r8
  unsigned __int8 v103; // r15
  char v104; // r15
  __int16 v105; // ax
  unsigned int v106; // r9d
  char v107; // r12
  unsigned __int8 v108; // bl
  struct REFS_IO_CONTEXT *v109; // rax
  __int64 v110; // rcx
  struct _IRP *v111; // r13
  PFILE_OBJECT v112; // rbx
  ULONG_PTR Information; // rax
  struct _CACHE_UNINITIALIZE_EVENT *v114; // r8
  char v115; // r10
  int v116; // r11d
  __int64 v117; // rdx
  __int64 v118; // rax
  int v119; // eax
  __int64 v120; // r9
  ULONG v121; // r8d
  int v122; // ecx
  __int64 v123; // rcx
  int v124; // eax
  struct REFS_IO_CONTEXT *v125; // rbx
  __int64 v126; // rcx
  __int64 v127; // rcx
  __int16 v128; // ax
  int v129; // ecx
  unsigned int v130; // r10d
  ULONG v131; // eax
  __int64 v132; // rcx
  int v133; // eax
  struct _FAST_MUTEX *v134; // rbx
  __int64 v135; // r8
  union _LARGE_INTEGER v136; // rcx
  union _LARGE_INTEGER v137; // r9
  union _LARGE_INTEGER v138; // rbx
  union _LARGE_INTEGER v139; // r8
  __int64 v140; // rax
  __int64 v141; // r9
  int v142; // r10d
  __int64 v143; // r8
  unsigned int v144; // edx
  struct REFS_IO_CONTEXT *v145; // rax
  struct _IRP_CONTEXT *v146; // rcx
  char v147; // al
  __int64 v148; // rax
  FILE_LOCK *v149; // rcx
  unsigned int v150; // r8d
  struct _CCB *v151; // r12
  int v152; // eax
  int v153; // eax
  __int64 v155; // rdx
  __int64 v156; // rcx
  int ActivityIdIrp; // eax
  char *v158; // rdx
  __int16 v159; // ax
  struct REFS_IO_CONTEXT *v160; // r12
  struct _MS_FAST_RESOURCE_OWNER_ENTRY *v161; // rax
  unsigned int v162; // ecx
  NTSTATUS v163; // eax
  struct _FILE_OBJECT *v164; // r14
  struct _IRP_CONTEXT *v165; // rcx
  unsigned int v166; // r8d
  void *v167; // rax
  unsigned int v168; // r8d
  __int64 v169; // r9
  struct _IO_STATUS_BLOCK *p_IoStatus; // rbx
  unsigned int v171; // r8d
  __int64 v172; // r9
  __int64 Status; // r9
  struct _FAST_MUTEX *v174; // rbx
  __int64 HighestPendingFileSize; // rax
  __int64 v176; // r8
  __int64 v177; // rax
  __int64 v178; // rcx
  volatile unsigned int v179; // edi
  struct _KPROCESS *v180; // rdi
  PEPROCESS CurrentProcess; // rax
  const char *ProcessImageFileName; // rax
  __int64 v183; // rdx
  struct _FCB *v184; // rbx
  NTSTATUS v185; // eax
  unsigned int v186; // r8d
  NTSTATUS v187; // esi
  unsigned __int8 v188; // [rsp+C8h] [rbp-248h]
  struct _CCB *v189; // [rsp+D8h] [rbp-238h]
  unsigned __int8 v190; // [rsp+E8h] [rbp-228h]
  int v191; // [rsp+ECh] [rbp-224h] BYREF
  bool v192; // [rsp+F0h] [rbp-220h] BYREF
  char v193; // [rsp+F1h] [rbp-21Fh]
  int v194; // [rsp+F4h] [rbp-21Ch]
  struct REFS_IO_CONTEXT *v195; // [rsp+F8h] [rbp-218h]
  __int64 v196; // [rsp+100h] [rbp-210h]
  char v197; // [rsp+108h] [rbp-208h]
  unsigned int v198[2]; // [rsp+110h] [rbp-200h]
  int v199[2]; // [rsp+118h] [rbp-1F8h]
  PFILE_OBJECT FileObject; // [rsp+120h] [rbp-1F0h]
  char v201; // [rsp+128h] [rbp-1E8h]
  __int64 *v202; // [rsp+130h] [rbp-1E0h]
  union _LARGE_INTEGER FileOffset[2]; // [rsp+138h] [rbp-1D8h] BYREF
  ULONG Length[4]; // [rsp+148h] [rbp-1C8h]
  __int64 v205; // [rsp+158h] [rbp-1B8h]
  PVOID Context2; // [rsp+160h] [rbp-1B0h]
  struct _FCB *v207; // [rsp+168h] [rbp-1A8h]
  struct _IO_STACK_LOCATION *CurrentStackLocation; // [rsp+170h] [rbp-1A0h]
  __int64 v209; // [rsp+178h] [rbp-198h]
  struct _CCB *v210; // [rsp+180h] [rbp-190h]
  unsigned int v211; // [rsp+188h] [rbp-188h]
  struct _IRP_CONTEXT *v212; // [rsp+190h] [rbp-180h]
  const char *v213; // [rsp+198h] [rbp-178h]
  _OWORD v214[4]; // [rsp+1A8h] [rbp-168h] BYREF
  __int128 v215; // [rsp+1E8h] [rbp-128h]
  __int64 v216; // [rsp+1F8h] [rbp-118h]
  unsigned int v217; // [rsp+208h] [rbp-108h]
  PIRP v218; // [rsp+210h] [rbp-100h]
  struct REFS_IO_CONTEXT *v219; // [rsp+218h] [rbp-F8h]
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+220h] [rbp-F0h] BYREF
  struct _IO_STACK_LOCATION *v221; // [rsp+230h] [rbp-E0h]
  __int64 v222; // [rsp+238h] [rbp-D8h]
  __int64 v223; // [rsp+240h] [rbp-D0h]
  _QWORD v224[3]; // [rsp+248h] [rbp-C8h] BYREF
  _BOOL8 v225; // [rsp+260h] [rbp-B0h]
  int v226; // [rsp+268h] [rbp-A8h]
  __int64 v227; // [rsp+270h] [rbp-A0h]
  __int64 v228; // [rsp+278h] [rbp-98h]
  __int64 v229; // [rsp+280h] [rbp-90h]
  __int64 v230; // [rsp+288h] [rbp-88h]
  __int64 v231; // [rsp+290h] [rbp-80h]
  __int64 v232; // [rsp+298h] [rbp-78h]
  __int64 v233; // [rsp+2A0h] [rbp-70h]
  __int64 v234; // [rsp+2A8h] [rbp-68h]
  __int64 v235; // [rsp+2B0h] [rbp-60h]
  __int128 v236; // [rsp+2B8h] [rbp-58h] BYREF
  __int64 v237; // [rsp+2C8h] [rbp-48h]

  v3 = Irp;
  Context2 = Irp;
  v195 = a2;
  v5 = a1;
  v212 = a1;
  v219 = a2;
  v218 = Irp;
  *(_OWORD *)&FileOffset[0].LowPart = 0;
  *(_OWORD *)Length = 0;
  v205 = 0;
  v191 = 0;
  memset(v214, 0, sizeof(v214));
  v215 = 0;
  v216 = 0;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v6 = CurrentStackLocation->FileObject;
  FileObject = v6;
  FsContext = (__int64)v6->FsContext;
  if ( !FsContext )
    goto LABEL_671;
  v8 = *(_QWORD *)(FsContext + 144);
  v209 = v8;
  FsContext2 = (char *)v6->FsContext2;
  v210 = (struct _CCB *)FsContext2;
  v10 = *(_DWORD *)(v8 + 24);
  if ( (v10 & 1) == 0 && (!FsContext2 || FsContext2[80] != 4 || (v10 & 2) == 0) )
  {
    *((_DWORD *)v5 + 1) |= 0x100u;
    v11 = *((unsigned int *)v5 + 4);
    if ( (int)v11 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_3a66e9b7f5c134dfe789af195554f06a_Traceguids, v11);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(*((_DWORD *)v5 + 4), 0, "NtfsData.c", 0x3C7u);
    }
    else
    {
      *((_DWORD *)v5 + 4) = -1073741202;
    }
    ExRaiseStatus(*((_DWORD *)v5 + 4));
  }
  if ( FsContext2 )
  {
    v193 = FsContext2[80];
    v12 = v193;
    if ( ((v193 - 2) & 0xFC) != 0 || v193 == 3 )
      goto LABEL_671;
  }
  else
  {
    v12 = 5;
    v193 = 5;
  }
  v202 = (__int64 *)(FsContext + 136);
  v207 = *(struct _FCB **)(FsContext + 136);
  pNetRoot = v207->pNetRoot;
  if ( pNetRoot[2].Context == (PVOID)1313 && pNetRoot[2].pSrvCall == (PMRX_SRV_CALL)1024 )
  {
LABEL_671:
    RefsCompleteReadWriteRequest(v5, a2, v3, -1073741808);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids, 3221225488LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
    {
      if ( RefsStatusDisplayStatus == -1073741808 )
        DbgPrintEx(0x95u, 0, "th%p %x %s:%i\n", KeGetCurrentThread(), -1073741808, "write.c", 1040);
      v179 = RefsStatusBreakOnWin32Error;
      if ( RefsStatusBreakOnStatus == -1073741808
        || RefsStatusBreakOnWin32Error && v179 == RtlNtStatusToDosErrorNoTeb(-1073741808) )
      {
        v180 = RefsStatusBreakForProcess;
        if ( !RefsStatusBreakForThread
          || RefsStatusBreakForThread == KeGetCurrentThread()
          && (!RefsStatusBreakForProcess || v180 == IoGetCurrentProcess())
          && (!RefsStatusBreakForImage
           || (CurrentProcess = IoGetCurrentProcess(),
               ProcessImageFileName = (const char *)PsGetProcessImageFileName(CurrentProcess),
               !_strnicmp(&RefsStatusBreakForImage, ProcessImageFileName, 0xFu))) )
        {
          __int2c();
        }
      }
      v183 = 32LL
           * (((unsigned __int16)_InterlockedExchangeAdd((volatile signed __int32 *)&RefsStatusNextQueueEntry, 1u) + 1)
            & 0xFFF);
      *(struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near **)((char *)&RefsStatusQueue + v183) = KeGetCurrentThread();
      *(_DWORD *)((char *)&RefsStatusQueue + v183 + 8) = -1073741808;
      *(struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near **)((char *)&RefsStatusQueue + v183 + 16) = (struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near *)"write.c";
      *(_DWORD *)((char *)&RefsStatusQueue + v183 + 24) = 1040;
    }
    return 3221225488LL;
  }
  v14 = *(_DWORD *)(*((_QWORD *)v5 + 13) + 16LL);
  if ( v14 < 0 && (*(_DWORD *)(FsContext + 152) & 0x2000) == 0 )
  {
    if ( v14 == -1073741608 || v14 == -1073741432 || v14 == -1073741400 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
      {
        v14 = -1073741823;
      }
      else
      {
        v14 = -1073741823;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            19,
            WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids,
            3221225473LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        if ( RefsStatusDisplayStatus == -1073741823 )
          DbgPrintEx(0x95u, 0, "th%p %x %s:%i\n", KeGetCurrentThread(), -1073741823, "write.c", 1062);
        v15 = RefsStatusBreakOnWin32Error;
        if ( RefsStatusBreakOnStatus == -1073741823
          || RefsStatusBreakOnWin32Error && v15 == RtlNtStatusToDosErrorNoTeb(-1073741823) )
        {
          v16 = RefsStatusBreakForProcess;
          if ( !RefsStatusBreakForThread
            || RefsStatusBreakForThread == KeGetCurrentThread()
            && (!RefsStatusBreakForProcess || v16 == IoGetCurrentProcess())
            && (!RefsStatusBreakForImage
             || (v17 = IoGetCurrentProcess(),
                 v18 = (const char *)PsGetProcessImageFileName(v17),
                 !_strnicmp(&RefsStatusBreakForImage, v18, 0xFu))) )
          {
            __int2c();
          }
        }
        v19 = 32LL
            * (((unsigned __int16)_InterlockedExchangeAdd((volatile signed __int32 *)&RefsStatusNextQueueEntry, 1u) + 1)
             & 0xFFF);
        *(struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near **)((char *)&RefsStatusQueue + v19) = KeGetCurrentThread();
        *(_DWORD *)((char *)&RefsStatusQueue + v19 + 8) = -1073741823;
        *(struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near **)((char *)&RefsStatusQueue + v19 + 16) = (struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near *)"write.c";
        *(_DWORD *)((char *)&RefsStatusQueue + v19 + 24) = 1062;
      }
    }
    RefsCompleteReadWriteRequest(v5, v195, (struct _IRP *)Context2, v14);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        20,
        WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids,
        (unsigned int)v14);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(v14, 0, "write.c", 0x42Au);
    return (unsigned int)v14;
  }
  if ( (v10 & 0xA000021) != 1 )
  {
    v3->IoStatus.Information = 0;
    v21 = *(_DWORD *)(v8 + 24);
    if ( (v21 & 0x20) != 0 )
    {
      RefsCompleteReadWriteRequest(v5, a2, v3, -1073741431);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids, 3221225865LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        if ( RefsStatusDisplayStatus == -1073741431 )
          DbgPrintEx(0x95u, 0, "th%p %x %s:%i\n", KeGetCurrentThread(), -1073741431, "write.c", 1087);
        v22 = RefsStatusBreakOnWin32Error;
        if ( RefsStatusBreakOnStatus == -1073741431
          || RefsStatusBreakOnWin32Error && v22 == RtlNtStatusToDosErrorNoTeb(-1073741431) )
        {
          v23 = RefsStatusBreakForProcess;
          if ( !RefsStatusBreakForThread
            || RefsStatusBreakForThread == KeGetCurrentThread()
            && (!RefsStatusBreakForProcess || v23 == IoGetCurrentProcess())
            && (!RefsStatusBreakForImage
             || (v24 = IoGetCurrentProcess(),
                 v25 = (const char *)PsGetProcessImageFileName(v24),
                 !_strnicmp(&RefsStatusBreakForImage, v25, 0xFu))) )
          {
            __int2c();
          }
        }
        v26 = 32LL
            * (((unsigned __int16)_InterlockedExchangeAdd((volatile signed __int32 *)&RefsStatusNextQueueEntry, 1u) + 1)
             & 0xFFF);
        *(struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near **)((char *)&RefsStatusQueue + v26) = KeGetCurrentThread();
        *(_DWORD *)((char *)&RefsStatusQueue + v26 + 8) = -1073741431;
        *(struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near **)((char *)&RefsStatusQueue + v26 + 16) = (struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near *)"write.c";
        *(_DWORD *)((char *)&RefsStatusQueue + v26 + 24) = 1087;
      }
      return 3221225865LL;
    }
    if ( (v21 & 0x8000000) != 0 || (v21 & 1) == 0 && v12 != 4 )
    {
      RefsCompleteReadWriteRequest(v5, a2, v3, -1073741202);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids, 3221226094LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        if ( RefsStatusDisplayStatus == -1073741202 )
          DbgPrintEx(0x95u, 0, "th%p %x %s:%i\n", KeGetCurrentThread(), -1073741202, "write.c", 1099);
        v32 = RefsStatusBreakOnWin32Error;
        if ( RefsStatusBreakOnStatus == -1073741202
          || RefsStatusBreakOnWin32Error && v32 == RtlNtStatusToDosErrorNoTeb(-1073741202) )
        {
          v33 = RefsStatusBreakForProcess;
          if ( !RefsStatusBreakForThread
            || RefsStatusBreakForThread == KeGetCurrentThread()
            && (!RefsStatusBreakForProcess || v33 == IoGetCurrentProcess())
            && (!RefsStatusBreakForImage
             || (v34 = IoGetCurrentProcess(),
                 v35 = (const char *)PsGetProcessImageFileName(v34),
                 !_strnicmp(&RefsStatusBreakForImage, v35, 0xFu))) )
          {
            __int2c();
          }
        }
        v36 = 32LL
            * (((unsigned __int16)_InterlockedExchangeAdd((volatile signed __int32 *)&RefsStatusNextQueueEntry, 1u) + 1)
             & 0xFFF);
        *(struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near **)((char *)&RefsStatusQueue + v36) = KeGetCurrentThread();
        *(_DWORD *)((char *)&RefsStatusQueue + v36 + 8) = -1073741202;
        *(struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near **)((char *)&RefsStatusQueue + v36 + 16) = (struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near *)"write.c";
        *(_DWORD *)((char *)&RefsStatusQueue + v36 + 24) = 1099;
      }
      return 3221226094LL;
    }
    if ( (v21 & 0x2000000) != 0 )
    {
      RefsCompleteReadWriteRequest(v5, a2, v3, -1073741662);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids, 3221225634LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        if ( RefsStatusDisplayStatus == -1073741662 )
          DbgPrintEx(0x95u, 0, "th%p %x %s:%i\n", KeGetCurrentThread(), -1073741662, "write.c", 1109);
        v27 = RefsStatusBreakOnWin32Error;
        if ( RefsStatusBreakOnStatus == -1073741662
          || RefsStatusBreakOnWin32Error && v27 == RtlNtStatusToDosErrorNoTeb(-1073741662) )
        {
          v28 = RefsStatusBreakForProcess;
          if ( !RefsStatusBreakForThread
            || RefsStatusBreakForThread == KeGetCurrentThread()
            && (!RefsStatusBreakForProcess || v28 == IoGetCurrentProcess())
            && (!RefsStatusBreakForImage
             || (v29 = IoGetCurrentProcess(),
                 v30 = (const char *)PsGetProcessImageFileName(v29),
                 !_strnicmp(&RefsStatusBreakForImage, v30, 0xFu))) )
          {
            __int2c();
          }
        }
        v31 = 32LL
            * (((unsigned __int16)_InterlockedExchangeAdd((volatile signed __int32 *)&RefsStatusNextQueueEntry, 1u) + 1)
             & 0xFFF);
        *(struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near **)((char *)&RefsStatusQueue + v31) = KeGetCurrentThread();
        *(_DWORD *)((char *)&RefsStatusQueue + v31 + 8) = -1073741662;
        *(struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near **)((char *)&RefsStatusQueue + v31 + 16) = (struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near *)"write.c";
        *(_DWORD *)((char *)&RefsStatusQueue + v31 + 24) = 1109;
      }
      return 3221225634LL;
    }
  }
  v190 = *((_BYTE *)v5 + 8) & 1;
  BYTE2(v191) = v190;
  v37 = v191 & 0xB7 | (8 * (v3->Flags & 1 | (4 * (v3->Flags & 2))));
  Flags = v6->Flags;
  LOBYTE(Flags) = BYTE1(v191) & 0xBF | (32 * (Flags & 2));
  LODWORD(v196) = Flags;
  BYTE1(v191) = Flags;
  if ( v5 == *((struct _IRP_CONTEXT **)v5 + 13) && LOBYTE(IoGetTopLevelIrp()->Type) )
    v39 = 16;
  else
    v39 = 0;
  v40 = v39 | v37 & 0xEF;
  LOBYTE(v191) = v40;
  v201 = (unsigned __int8)v40 >> 3;
  v192 = (v40 & 8) != 0;
  if ( (v40 & 8) != 0 && (*(_DWORD *)(FsContext + 152) & 0x1000000) != 0 )
  {
    v41 = *((_QWORD *)v5 + 13);
    if ( *(_BYTE *)(v41 + 40) != 13
      || (v42 = *(_QWORD *)(v41 + 72)) == 0
      || *(_DWORD *)(*(_QWORD *)(v42 + 184) + 24LL) != 590047 )
    {
      RefsCompleteReadWriteRequest(v5, a2, v3, -1073739760);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids, 3221227536LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        if ( RefsStatusDisplayStatus == -1073739760 )
          DbgPrintEx(0x95u, 0, "th%p %x %s:%i\n", KeGetCurrentThread(), -1073739760, "write.c", 1136);
        v43 = RefsStatusBreakOnWin32Error;
        if ( RefsStatusBreakOnStatus == -1073739760
          || RefsStatusBreakOnWin32Error && v43 == RtlNtStatusToDosErrorNoTeb(-1073739760) )
        {
          v44 = RefsStatusBreakForProcess;
          if ( !RefsStatusBreakForThread
            || RefsStatusBreakForThread == KeGetCurrentThread()
            && (!RefsStatusBreakForProcess || v44 == IoGetCurrentProcess())
            && (!RefsStatusBreakForImage
             || (v45 = IoGetCurrentProcess(),
                 v46 = (const char *)PsGetProcessImageFileName(v45),
                 !_strnicmp(&RefsStatusBreakForImage, v46, 0xFu))) )
          {
            __int2c();
          }
        }
        v47 = 32LL
            * (((unsigned __int16)_InterlockedExchangeAdd((volatile signed __int32 *)&RefsStatusNextQueueEntry, 1u) + 1)
             & 0xFFF);
        *(struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near **)((char *)&RefsStatusQueue + v47) = KeGetCurrentThread();
        *(_DWORD *)((char *)&RefsStatusQueue + v47 + 8) = -1073739760;
        *(struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near **)((char *)&RefsStatusQueue + v47 + 16) = (struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near *)"write.c";
        *(_DWORD *)((char *)&RefsStatusQueue + v47 + 24) = 1136;
      }
      return 3221227536LL;
    }
  }
  if ( FsContext2 && (*((_DWORD *)FsContext2 + 1) & 0x2000) != 0 && (v40 & 0x40) == 0 )
  {
    RefsCompleteReadWriteRequest(v5, a2, v3, -1073741811);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids, 3221225485LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
    {
      if ( RefsStatusDisplayStatus == -1073741811 )
        DbgPrintEx(0x95u, 0, "th%p %x %s:%i\n", KeGetCurrentThread(), -1073741811, "write.c", 1148);
      v48 = RefsStatusBreakOnWin32Error;
      if ( RefsStatusBreakOnStatus == -1073741811
        || RefsStatusBreakOnWin32Error && v48 == RtlNtStatusToDosErrorNoTeb(-1073741811) )
      {
        v49 = RefsStatusBreakForProcess;
        if ( !RefsStatusBreakForThread
          || RefsStatusBreakForThread == KeGetCurrentThread()
          && (!RefsStatusBreakForProcess || v49 == IoGetCurrentProcess())
          && (!RefsStatusBreakForImage
           || (v50 = IoGetCurrentProcess(),
               v51 = (const char *)PsGetProcessImageFileName(v50),
               !_strnicmp(&RefsStatusBreakForImage, v51, 0xFu))) )
        {
          __int2c();
        }
      }
      v52 = 32LL
          * (((unsigned __int16)_InterlockedExchangeAdd((volatile signed __int32 *)&RefsStatusNextQueueEntry, 1u) + 1)
           & 0xFFF);
      *(struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near **)((char *)&RefsStatusQueue + v52) = KeGetCurrentThread();
      *(_DWORD *)((char *)&RefsStatusQueue + v52 + 8) = -1073741811;
      *(struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near **)((char *)&RefsStatusQueue + v52 + 16) = (struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near *)"write.c";
      *(_DWORD *)((char *)&RefsStatusQueue + v52 + 24) = 1148;
      return 3221225485LL;
    }
    return 3221225485LL;
  }
  if ( *(_DWORD *)(FsContext + 344) )
  {
    RefsCompleteRequest(v5, v3, -1073740659);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids, 3221226637LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
    {
      if ( RefsStatusDisplayStatus == -1073740659 )
        DbgPrintEx(0x95u, 0, "th%p %x %s:%i\n", KeGetCurrentThread(), -1073740659, "write.c", 1168);
      v53 = RefsStatusBreakOnWin32Error;
      if ( RefsStatusBreakOnStatus == -1073740659
        || RefsStatusBreakOnWin32Error && v53 == RtlNtStatusToDosErrorNoTeb(-1073740659) )
      {
        v54 = RefsStatusBreakForProcess;
        if ( !RefsStatusBreakForThread
          || RefsStatusBreakForThread == KeGetCurrentThread()
          && (!RefsStatusBreakForProcess || v54 == IoGetCurrentProcess())
          && (!RefsStatusBreakForImage
           || (v55 = IoGetCurrentProcess(),
               v56 = (const char *)PsGetProcessImageFileName(v55),
               !_strnicmp(&RefsStatusBreakForImage, v56, 0xFu))) )
        {
          __int2c();
        }
      }
      v57 = 32LL
          * (((unsigned __int16)_InterlockedExchangeAdd((volatile signed __int32 *)&RefsStatusNextQueueEntry, 1u) + 1)
           & 0xFFF);
      *(struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near **)((char *)&RefsStatusQueue + v57) = KeGetCurrentThread();
      *(_DWORD *)((char *)&RefsStatusQueue + v57 + 8) = -1073740659;
      *(struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near **)((char *)&RefsStatusQueue + v57 + 16) = (struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near *)"write.c";
      *(_DWORD *)((char *)&RefsStatusQueue + v57 + 24) = 1168;
    }
    return 3221226637LL;
  }
  RefsUpdateFileTimestampsFromNonpagedFcb(v207, 0);
  v58 = *((_QWORD *)v5 + 1);
  v59 = CurrentStackLocation;
  if ( (v58 & 0x20000) != 0
    && *(_QWORD *)(FsContext + 32) < CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart
                                   + CurrentStackLocation->Parameters.Read.Length )
  {
    *((_QWORD *)v5 + 1) = v58 & 0xFFFFFFFFFFFDFFFFuLL;
    v59->Parameters.Read.ByteOffset.QuadPart = -1;
  }
  v199[0] = v59->Parameters.Read.Length;
  v60 = v199[0];
  QuadPart = v59->Parameters.Read.ByteOffset.QuadPart;
  FileOffset[0].QuadPart = QuadPart;
  v62.QuadPart = QuadPart + (unsigned int)v199[0];
  FileOffset[1] = v62;
  Length[0] = v199[0];
  *(_QWORD *)v198 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v63 = "EXT";
    if ( QuadPart >= 0 )
      v63 = "NEXT";
    v64 = "TL";
    if ( (v40 & 0x10) == 0 )
      v64 = "NTL";
    v65 = "SYNC";
    if ( (Flags & 0x40) == 0 )
      v65 = "ASYNC";
    v66 = "C";
    if ( !v192 )
      v66 = "NC";
    v67 = "P";
    if ( (v40 & 0x40) == 0 )
      v67 = "NP";
    v213 = "NWAIT";
    v68 = "WAIT";
    if ( !v190 )
      v68 = v213;
    WPP_SF_qiDqssssss(
      *(_QWORD *)(*(_QWORD *)v198 + 24LL),
      (_DWORD)v67,
      (_DWORD)v66,
      FsContext,
      QuadPart,
      v199[0],
      (char)v3,
      (__int64)v68,
      (__int64)v67,
      (__int64)v66,
      (__int64)v65,
      (__int64)v64,
      (__int64)v63);
    v60 = Length[0];
    v62 = FileOffset[1];
    QuadPart = FileOffset[0].QuadPart;
  }
  if ( QuadPart >= 0 && (QuadPart > v62.QuadPart || QuadPart + v60 != v62.QuadPart) )
  {
    RefsCompleteReadWriteRequest(v5, a2, v3, -1073741811);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids, 3221225485LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
    {
      if ( RefsStatusDisplayStatus == -1073741811 )
        DbgPrintEx(0x95u, 0, "th%p %x %s:%i\n", KeGetCurrentThread(), -1073741811, "write.c", 1217);
      v69 = RefsStatusBreakOnWin32Error;
      if ( RefsStatusBreakOnStatus == -1073741811
        || RefsStatusBreakOnWin32Error && v69 == RtlNtStatusToDosErrorNoTeb(-1073741811) )
      {
        v70 = RefsStatusBreakForProcess;
        if ( !RefsStatusBreakForThread
          || RefsStatusBreakForThread == KeGetCurrentThread()
          && (!RefsStatusBreakForProcess || v70 == IoGetCurrentProcess())
          && (!RefsStatusBreakForImage
           || (v71 = IoGetCurrentProcess(),
               v72 = (const char *)PsGetProcessImageFileName(v71),
               !_strnicmp(&RefsStatusBreakForImage, v72, 0xFu))) )
        {
          __int2c();
        }
      }
      v73 = 32LL
          * (((unsigned __int16)_InterlockedExchangeAdd((volatile signed __int32 *)&RefsStatusNextQueueEntry, 1u) + 1)
           & 0xFFF);
      *(struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near **)((char *)&RefsStatusQueue + v73) = KeGetCurrentThread();
      *(_DWORD *)((char *)&RefsStatusQueue + v73 + 8) = -1073741811;
      *(struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near **)((char *)&RefsStatusQueue + v73 + 16) = (struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near *)"write.c";
      *(_DWORD *)((char *)&RefsStatusQueue + v73 + 24) = 1217;
    }
    return 3221225485LL;
  }
  if ( !v60 )
  {
    *((_QWORD *)v5 + 86) = 8;
    v3->IoStatus.Information = 0;
LABEL_228:
    RefsCompleteReadWriteRequest(v5, a2, v3, 0);
    return 0;
  }
  if ( !v192 )
  {
    v74 = *((_QWORD *)v5 + 1);
    if ( (v74 & 8) == 0 && !CcCanIWrite(FileObject, v60, (v74 & 0x41) != 0, (*((_DWORD *)v5 + 1) & 8) != 0) )
    {
      v75 = *((_DWORD *)v5 + 1);
      v76 = Context2;
      RefsPrePostIrp(v5, (PIRP)Context2);
      *((_DWORD *)v5 + 1) |= 8u;
      if ( (v75 & 8) == 0 && *(_BYTE *)(v209 + 10496) )
        *((LARGE_INTEGER *)v5 + 86) = KeQueryPerformanceCounter(0);
      CcDeferWrite(FileObject, RefsAddToWorkque, v5, v76, Length[0], (v75 & 8) != 0);
      if ( v40 < 0 )
      {
        if ( *(_WORD *)FsContext != 2050 )
          FsContext = *v202;
        v77 = *(_QWORD *)(FsContext + 96);
        if ( !--DWORD2(v215) )
        {
          *((_QWORD *)&v215 + 1) &= 0xFFFFFFFD00000000uLL;
          ExReleaseFastResource(v77, v214);
        }
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids, 259);
      }
      return 259;
    }
  }
  v78 = v209;
  if ( *(_BYTE *)(v209 + 10496) )
  {
    PerformanceCounter = *(LARGE_INTEGER *)((char *)v5 + 688);
    if ( PerformanceCounter.QuadPart <= 23 )
      PerformanceCounter = KeQueryPerformanceCounter(0);
    *((LARGE_INTEGER *)v5 + 86) = PerformanceCounter;
    v80 = v190;
    if ( (v40 & 0x40) != 0 || v192 )
      v81 = 0;
    else
      v81 = 4;
    *((_BYTE *)a2 + 56) = v81 | v190 | (*((_BYTE *)v5 + 8) >> 2) & 2 | v201 & 8;
    v78 = v209;
  }
  else
  {
    v80 = v190;
  }
  v82 = v193;
  if ( v193 != 4 )
  {
    v221 = CurrentStackLocation;
    v213 = (const char *)FsContext;
    v198[0] = 0;
    LODWORD(v202) = 0;
    v91 = (unsigned __int8)v40;
    LOBYTE(v91) = v40 & 0x40;
    v92 = 128;
    if ( (v40 & 0x40) != 0 )
    {
      v93 = (_DWORD *)(*(_QWORD *)(v209 + 808)
                     + ((unsigned __int64)(KeGetCurrentProcessorNumber() % RefsNumberProcessors) << 6));
      if ( ((__int64)v207->spacer.Resource & 0x100LL) == 0
        && ((v94 = *(_WORD *)(FsContext + 216), v94 == 128) || v94 == 176) )
      {
        ++v93[5];
        v93[6] += Length[0];
      }
      else
      {
        ++v93[11];
        v93[12] += Length[0];
      }
    }
    v95 = v192;
    if ( (_BYTE)v91 || !v192 )
      *(_DWORD *)(FsContext + 184) = 0;
    v194 = 0;
    *((_QWORD *)&v215 + 1) = 0x100000000LL;
    v216 = 0;
    if ( (v40 & 0x40) == 0 )
    {
      v96 = (unsigned int)v210;
      if ( v210 )
        *((_DWORD *)v5 + 158) = *((_DWORD *)v210 + 21);
      if ( v40 < 0 )
        goto LABEL_342;
      if ( (*((_DWORD *)v5 + 2) & 0x100LL) != 0 )
        goto LABEL_339;
      if ( (*(_DWORD *)(FsContext + 152) & 0x10) != 0 )
      {
        v92 = *(_QWORD *)(*(_QWORD *)(FsContext + 136) + 8LL) & 0x40000100LL;
        if ( v92 == 0x40000000 )
          goto LABEL_339;
      }
      v92 = (__int64)FileObject;
      if ( v82 != 5 )
      {
        if ( !v95 )
          goto LABEL_316;
        if ( FileObject->SectionObjectPointer->DataSectionObject )
          goto LABEL_339;
      }
      if ( v95 )
      {
LABEL_317:
        if ( FileOffset[0].QuadPart >= 0 )
        {
          if ( !v95 || (_BYTE)v80 || (v97 = *(_DWORD *)(FsContext + 152), (v97 & 8) != 0) && (v97 & 0x40) == 0 )
          {
            v227 = FsContext;
            v100 = (unsigned __int8)RefsAcquirePagingFastResourceShared(FileObject, FsContext, v214) << 7;
            v99 = (unsigned __int8)v40;
            LOBYTE(v99) = v40 & 0x7F;
            v40 = v99 | v100;
            LOBYTE(v191) = v99 | v100;
          }
          else
          {
            *(_QWORD *)v199 = FsContext;
            v98 = (unsigned __int8)RefsAcquirePagingFastResourceShared(FileObject, FsContext, (char *)v195 + 720) << 7;
            v99 = (unsigned __int8)v40;
            LOBYTE(v99) = v40 & 0x7F;
            v40 = v99 | v98;
            LOBYTE(v191) = v99 | v98;
            if ( ((v99 | v98) & 0x80u) != 0LL )
            {
              v190 |= 2u;
              BYTE2(v191) = v190;
            }
          }
          Flags = (unsigned __int8)v40;
          if ( v40 >= 0 )
          {
            v103 = v190;
          }
          else
          {
            if ( (*(_DWORD *)(FsContext + 152) & 0x10) == 0 || !_FCB::HasPurgeableEAs(*(_FCB **)(FsContext + 136)) )
            {
              v101 = FileObject;
              if ( (v193 == 5 || (v40 & 8) == 0 || !FileObject->SectionObjectPointer->DataSectionObject)
                && ((v40 & 8) != 0 || FileObject->SectionObjectPointer->SharedCacheMap) )
              {
LABEL_341:
                if ( (Flags & 0x80u) == 0 )
                {
                  LOBYTE(Flags) = Flags & 0xDF;
                  LOBYTE(v191) = Flags;
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                  {
                    WPP_SF_d(
                      WPP_GLOBAL_Control->AttachedDevice,
                      30,
                      WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids,
                      3221225688LL);
                  }
                  if ( (_BYTE)RefsStatusDebugEnabled )
                    RefsStatusDebug(-1073741608, v5, "write.c", 0x696u);
                  RefsRaiseStatusInternal(v5, -1073741608, v96);
                  goto LABEL_697;
                }
LABEL_342:
                if ( *(_DWORD *)(FsContext + 296) != 3
                  || (v105 = *(_WORD *)(FsContext + 216), v105 != 128) && v105 != 176 )
                {
                  if ( ((__int64)v207->spacer.Resource & 0x20) != 0 )
                  {
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
                      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
                    {
                      Flags = -1073741431;
                    }
                    else
                    {
                      Flags = -1073741431;
                      WPP_SF_d(
                        WPP_GLOBAL_Control->AttachedDevice,
                        32,
                        WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids,
                        3221225865LL);
                    }
                    if ( !(_BYTE)RefsStatusDebugEnabled )
                      goto LABEL_354;
                    v106 = 1701;
                    goto LABEL_353;
                  }
                  if ( (*(_DWORD *)(FsContext + 152) & 0x80u) != 0 )
                  {
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
                      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
                    {
                      Flags = -1073740610;
                    }
                    else
                    {
                      Flags = -1073740610;
                      WPP_SF_d(
                        WPP_GLOBAL_Control->AttachedDevice,
                        33,
                        WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids,
                        3221226686LL);
                    }
                    if ( !(_BYTE)RefsStatusDebugEnabled )
                      goto LABEL_354;
                    v106 = 1710;
                    goto LABEL_353;
                  }
                  if ( (*(_DWORD *)(FsContext + 300) & 0x40) == 0 )
                  {
                    if ( RefsIsFileOpen(v207) )
                    {
                      if ( (v40 & 8) != 0 )
                      {
                        v117 = *((_QWORD *)v5 + 13);
                        if ( v5 != (struct _IRP_CONTEXT *)v117 )
                        {
                          if ( _bittest16((const signed __int16 *)(FsContext + 256), 0xEu) )
                          {
                            if ( *(_BYTE *)(v117 + 40) == 13 )
                            {
                              v118 = *(_QWORD *)(v117 + 72);
                              if ( v118 )
                              {
                                if ( *(_DWORD *)(*(_QWORD *)(v118 + 184) + 24LL) == 590047 )
                                  v116 = 2;
                                LODWORD(v202) = v116;
                                v217 = v116;
                              }
                            }
                          }
                        }
                        if ( v115 != 5 && FileObject->SectionObjectPointer->DataSectionObject )
                        {
                          if ( *(_WORD *)FsContext == 2053
                            && *(_QWORD *)(FsContext + 432)
                            && *(_WORD *)(FsContext + 260) )
                          {
                            v119 = 1 << *(_DWORD *)(*(_QWORD *)(FsContext + 144) + 552LL);
                            v117 = -(__int64)v119;
                            v120 = FileOffset[0].QuadPart & v117;
                            v121 = (v117 & (v119 + FileOffset[1].LowPart - 1)) - (FileOffset[0].LowPart & v117);
                          }
                          else
                          {
                            v120 = FileOffset[0].QuadPart;
                            v121 = Length[0];
                          }
                          if ( *(_DWORD *)(FsContext + 176) )
                          {
                            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
                              || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
                            {
                              Flags = -1073740747;
                            }
                            else
                            {
                              Flags = -1073740747;
                              WPP_SF_d(
                                WPP_GLOBAL_Control->AttachedDevice,
                                36,
                                WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids,
                                3221226549LL);
                            }
                            if ( !(_BYTE)RefsStatusDebugEnabled )
                              goto LABEL_354;
                            v106 = 1783;
                            goto LABEL_353;
                          }
                          Flags = RefsCacheCoherencyFlush(
                                    v5,
                                    (struct _IRP *)v117,
                                    (struct _SCB *)FsContext,
                                    v120,
                                    v121,
                                    1u,
                                    *(_DWORD *)(FsContext + 180) == 0);
                          v194 = Flags;
                          if ( Flags < 0 )
                            goto LABEL_355;
                          if ( FileObject->PrivateCacheMap )
                            RefsUninitializeCacheMap(FileObject, 0, v114);
                        }
                      }
                      if ( !v210 || (*((_DWORD *)v210 + 1) & 0x8000) == 0 )
                      {
                        v122 = *(_DWORD *)(FsContext + 300) & 0x4000;
                        Flags = v122 != 0 ? 0xC000026E : 0;
                        v194 = Flags;
                        if ( !v122 )
                        {
                          Flags = RefsSetWriteRangeFromEof(v5, FsContext, FileOffset, &v191);
                          v194 = Flags;
                          if ( Flags < 0 )
                          {
                            v108 = BYTE2(v191);
                            v190 = BYTE2(v191);
                            v107 = BYTE1(v191);
                            v40 = v191;
                            goto LABEL_357;
                          }
                          v123 = *((_QWORD *)v5 + 13);
                          v124 = *(_DWORD *)(v123 + 4);
                          if ( (v124 & 2) != 0 )
                          {
                            v190 = BYTE2(v191);
                            Flags = BYTE1(v191);
                            LODWORD(v196) = BYTE1(v191);
                          }
                          else
                          {
                            *(_DWORD *)(v123 + 4) = v124 | 2;
                            Flags = BYTE1(v191) | 0x20;
                            LODWORD(v196) = Flags;
                            BYTE1(v191) |= 0x20u;
                            v190 = BYTE2(v191);
                          }
                          v40 = v191;
LABEL_499:
                          if ( (*(_DWORD *)(FsContext + 152) & 0x20) == 0 && *(_WORD *)(FsContext + 216) != 160 )
                          {
                            v196 = FsContext;
                            RefsAcquireResourceShared(v5, FsContext, 1);
                            LOBYTE(Flags) = Flags | 0x10;
                            BYTE1(v191) = Flags;
                            RefsUpdateScbFromAttribute(v5, (struct _SCB *)FsContext, 0);
                            IoStatus.Pointer = (PVOID)FsContext;
                            RefsReleaseResource(v5, FsContext);
                            LOBYTE(Flags) = Flags & 0xEF;
                            LODWORD(v196) = Flags;
                            BYTE1(v191) = Flags;
                          }
                          v144 = v190;
                          if ( (Flags & 4) != 0 && (v190 & 1) == 0 && (v40 & 8) != 0 )
                          {
                            LOBYTE(v144) = v190 | 1;
                            v190 = v144;
                            BYTE2(v191) = v144;
                            *((_QWORD *)v5 + 1) |= 1uLL;
                            v145 = v195;
                            *((_BYTE *)v195 + 56) |= 1u;
                          }
                          else
                          {
                            v145 = v195;
                          }
                          if ( (v40 & 0x40) != 0 )
                          {
LABEL_555:
                            v151 = v210;
                            if ( (v40 & 2) != 0 )
                            {
                              RefsInitiateFileExtensionForWrite(v5, (__int64)&v191);
                              v190 = BYTE2(v191);
                              Flags = BYTE1(v191);
                              LODWORD(v196) = BYTE1(v191);
                              v40 = v191;
                            }
                            v152 = *(_DWORD *)(FsContext + 152);
                            if ( (v152 & 8) != 0 && (v152 & 0x40) == 0 )
                            {
                              if ( (v40 & 8) == 0 )
                              {
LABEL_622:
                                v164 = FileObject;
                                if ( FileObject->PrivateCacheMap > (PVOID)1 )
                                  goto LABEL_625;
                                v165 = v5;
                                if ( *(_QWORD *)(FsContext + 32) <= *(_QWORD *)(FsContext + 24) )
                                {
                                  RefsInitializeCacheMap(v5, FileObject, 0, (struct DataSCB *)FsContext);
                                  CcSetReadAheadGranularity(v164, 0x10000u);
                                  CcSetParallelFlushFile(v164, 1u);
LABEL_625:
                                  if ( (v40 & 0x20) != 0
                                    && (*((_DWORD *)v5 + 2) & 0x100LL) == 0
                                    && ((*(_DWORD *)(FsContext + 152) & 0x10) == 0
                                     || !_FCB::HasPurgeableEAs(*(_FCB **)(FsContext + 136)))
                                    && (*((_DWORD *)v5 + 2) & 0x20000LL) == 0 )
                                  {
                                    v207 = (struct _FCB *)FsContext;
                                    RefsConvertPagingFastResourceExclusiveToShared(v123, FsContext, v214);
                                    v40 &= ~0x20u;
                                    LOBYTE(v191) = v40;
                                  }
                                  if ( *(__int16 *)(FsContext + 256) >= 0
                                    || RefsReserveClusters(
                                         v5,
                                         (struct _SCB *)FsContext,
                                         FileOffset[0].QuadPart,
                                         Length[0]) )
                                  {
                                    if ( (*((_BYTE *)v5 + 41) & 2) != 0 )
                                    {
                                      p_IoStatus = &v3->IoStatus;
                                      CcPrepareMdlWrite(v164, FileOffset, Length[0], (PMDL *)Context2 + 1, p_IoStatus);
                                      Flags = p_IoStatus->Status;
                                      goto LABEL_638;
                                    }
                                    v167 = RefsMapUserBuffer(v3, v144);
                                    if ( CcCopyWrite(v164, FileOffset, Length[0], *((_BYTE *)v5 + 8) & 1, v167) )
                                    {
                                      v169 = *((unsigned int *)v5 + 4);
                                      if ( (int)v169 >= 0 )
                                      {
                                        v3->IoStatus.Status = 0;
                                        v3->IoStatus.Information = Length[0];
                                        Flags = 0;
LABEL_638:
                                        v194 = Flags;
                                        if ( (*(_DWORD *)(*(_QWORD *)(FsContext + 144) + 24LL) & 0x4000000) == 0
                                          || Length[0] < 0x10000 )
                                        {
                                          goto LABEL_355;
                                        }
                                        IoStatus = 0;
                                        CcFlushCache(
                                          (PSECTION_OBJECT_POINTERS)(*(_QWORD *)(FsContext + 248) + 8LL),
                                          FileOffset,
                                          Length[0],
                                          &IoStatus);
                                        v172 = *((unsigned int *)v5 + 4);
                                        if ( (int)v172 >= 0 )
                                        {
                                          Status = (unsigned int)IoStatus.Status;
                                          if ( IoStatus.Status >= 0 )
                                            goto LABEL_355;
LABEL_788:
                                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                                            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                                          {
                                            WPP_SF_d(
                                              WPP_GLOBAL_Control->AttachedDevice,
                                              56,
                                              WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids,
                                              Status);
                                          }
                                          if ( (_BYTE)RefsStatusDebugEnabled )
                                            RefsStatusDebug(IoStatus.Status, v5, "write.c", 0xBD7u);
                                          RefsRaiseStatusInternal(v5, IoStatus.Status, v171);
                                          __debugbreak();
                                          JUMPOUT(0x1400ABA2CLL);
                                        }
LABEL_781:
                                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                                          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                                        {
                                          WPP_SF_d(
                                            WPP_GLOBAL_Control->AttachedDevice,
                                            55,
                                            WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids,
                                            v172);
                                        }
                                        if ( (_BYTE)RefsStatusDebugEnabled )
                                          RefsStatusDebug(*((_DWORD *)v5 + 4), v5, "write.c", 0xBD4u);
                                        RefsRaiseStatusInternal(v5, *((_DWORD *)v5 + 4), v171);
                                        goto LABEL_788;
                                      }
LABEL_774:
                                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                                        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                                      {
                                        WPP_SF_d(
                                          WPP_GLOBAL_Control->AttachedDevice,
                                          54,
                                          WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids,
                                          v169);
                                      }
                                      if ( (_BYTE)RefsStatusDebugEnabled )
                                        RefsStatusDebug(*((_DWORD *)v5 + 4), v5, "write.c", 0xB88u);
                                      RefsRaiseStatusInternal(v5, *((_DWORD *)v5 + 4), v168);
                                      goto LABEL_781;
                                    }
LABEL_767:
                                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                                    {
                                      WPP_SF_d(
                                        WPP_GLOBAL_Control->AttachedDevice,
                                        53,
                                        WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids,
                                        3221225688LL);
                                    }
                                    if ( (_BYTE)RefsStatusDebugEnabled )
                                      RefsStatusDebug(-1073741608, v5, "write.c", 0xB84u);
                                    RefsRaiseStatusInternal(v5, -1073741608, v168);
                                    goto LABEL_774;
                                  }
LABEL_760:
                                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                                  {
                                    WPP_SF_d(
                                      WPP_GLOBAL_Control->AttachedDevice,
                                      52,
                                      WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids,
                                      3221225599LL);
                                  }
                                  if ( (_BYTE)RefsStatusDebugEnabled )
                                    RefsStatusDebug(-1073741697, v5, "write.c", 0xB6Bu);
                                  RefsRaiseStatusInternal(v5, -1073741697, v166);
                                  goto LABEL_767;
                                }
LABEL_753:
                                v184 = v207;
                                v185 = RefsQueueTriageForDeadFcb(v165, v207);
                                v187 = v185;
                                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                                {
                                  WPP_SF_qd(
                                    WPP_GLOBAL_Control->AttachedDevice,
                                    51,
                                    WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids,
                                    v184,
                                    v185);
                                }
                                if ( (_BYTE)RefsStatusDebugEnabled )
                                  RefsStatusDebug(v187, v5, "write.c", 0xB34u);
                                RefsRaiseStatusInternal(v5, v187, v186);
                                goto LABEL_760;
                              }
                              RefsAcquireExclusiveScb(v5, FsContext, 0);
                              LOBYTE(Flags) = Flags | 0x10;
                              LODWORD(v196) = Flags;
                              BYTE1(v191) = Flags;
                              if ( (*(_DWORD *)(FsContext + 152) & 0x20) == 0 )
                                RefsUpdateScbFromAttribute(v5, (struct _SCB *)FsContext, 0);
                              v153 = *(_DWORD *)(FsContext + 152);
                              if ( (v153 & 8) != 0 && (v153 & 0x40) == 0 )
                              {
                                Flags = RefsResidentWrite(
                                          v5,
                                          v3,
                                          (struct _SCB *)FsContext,
                                          FileOffset[0].LowPart,
                                          Length[0]);
                                v194 = Flags;
                                RefsCheckpointCurrentTransaction(v5);
                                RefsReleaseFcb(v5, *(struct _FCB **)(FsContext + 136));
                                v107 = v196 & 0xEF;
                                BYTE1(v191) = v196 & 0xEF;
                                goto LABEL_356;
                              }
                              RefsReleaseFcb(v5, *(struct _FCB **)(FsContext + 136));
                              LOBYTE(Flags) = Flags & 0xEF;
                              LODWORD(v196) = Flags;
                              BYTE1(v191) = Flags;
                            }
                            if ( (v40 & 8) != 0 )
                            {
                              v155 = *(int *)(v209 + 276);
                              if ( (((_DWORD)v155 - 1) & FileOffset[0].LowPart) == 0 )
                              {
                                v156 = Length[0];
                                *(_QWORD *)v199 = -v155 & (v155 + Length[0] - 1LL);
                                if ( v199[0] == Length[0] || FileOffset[1].QuadPart >= *(_QWORD *)(FsContext + 32) )
                                {
                                  if ( *(_WORD *)(FsContext + 216) == 128 )
                                  {
                                    v156 = *(unsigned int *)(*(_QWORD *)(FsContext + 144) + 28LL);
                                    if ( (v156 & 0x80u) != 0LL && (v156 & 0x400) != 0 )
                                    {
                                      v156 = *(_QWORD *)(FsContext + 136);
                                      if ( (*(_DWORD *)(v156 + 8) & 0x8905LL) == 0 && (*(_DWORD *)(v156 + 152) & 4) == 0 )
                                      {
                                        v236 = 0;
                                        v237 = 0;
                                        ActivityIdIrp = IoGetActivityIdIrp(v3, (char *)&v236 + 8);
                                        v158 = (char *)&v236 + 8;
                                        if ( ActivityIdIrp < 0 )
                                          v158 = 0;
                                        *(_QWORD *)&v236 = v158;
                                        RefsChangeLogWrite(
                                          v207,
                                          (struct _REFS_ACTIVITY_ID *)&v236,
                                          FileOffset[0].QuadPart,
                                          Length[0]);
                                      }
                                    }
                                  }
                                  if ( (*(_DWORD *)(v209 + 6568) & 2) != 0 && IoGetIoPriorityHint(v3) > IoPriorityLow )
                                  {
                                    if ( ((v159 = *(_WORD *)(FsContext + 216), v159 == 128) || v159 == 176)
                                      && !*(_WORD *)(FsContext + 224)
                                      || (v156 = 160, v159 == 160) )
                                    {
                                      RefsHeatLogIo(v3, v207);
                                    }
                                  }
                                  if ( (v190 & 1) != 0 )
                                  {
                                    v160 = v195;
                                  }
                                  else if ( (v40 & 0x40) != 0 )
                                  {
                                    v189 = v151;
                                    v160 = v195;
                                    if ( (Flags & 1) != 0 )
                                      RefsSetIoContextAsync(
                                        (struct _IRP_CONTEXT *)v156,
                                        v195,
                                        0,
                                        0,
                                        0,
                                        0,
                                        FileOffset[0].QuadPart,
                                        v198[0],
                                        1,
                                        v198[0],
                                        v188,
                                        (struct _SCB *)FsContext,
                                        v189);
                                    else
                                      RefsSetIoContextAsync(
                                        (struct _IRP_CONTEXT *)v156,
                                        v195,
                                        0,
                                        0,
                                        0,
                                        0,
                                        FileOffset[0].QuadPart,
                                        CurrentStackLocation->Parameters.Read.Length,
                                        1,
                                        CurrentStackLocation->Parameters.Read.Length,
                                        v188,
                                        (struct _SCB *)FsContext,
                                        v189);
                                  }
                                  else
                                  {
                                    v160 = v195;
                                    v161 = (struct REFS_IO_CONTEXT *)((char *)v195 + 720);
                                    if ( (v190 & 2) == 0 )
                                      v161 = (struct _MS_FAST_RESOURCE_OWNER_ENTRY *)v214;
                                    RefsSetIoContextAsync(
                                      (struct _IRP_CONTEXT *)CurrentStackLocation->Parameters.Read.Length,
                                      v195,
                                      0,
                                      *(struct _MS_FAST_RESOURCE **)(FsContext + 16),
                                      v161,
                                      0,
                                      FileOffset[0].QuadPart,
                                      CurrentStackLocation->Parameters.Read.Length,
                                      1,
                                      CurrentStackLocation->Parameters.Read.Length,
                                      v188,
                                      (struct _SCB *)FsContext,
                                      v210);
                                  }
                                  if ( (*((_BYTE *)v5 + 8) & 1) == 0 )
                                    RefsFlushForWriteThrough(v5, FsContext, 0);
                                  v162 = (unsigned int)v202;
                                  if ( (Flags & 0x20) != 0 )
                                  {
                                    v162 = (unsigned int)v202 | 0x40;
                                    v217 = (unsigned int)v202 | 0x40;
                                  }
                                  Flags = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))RefsNonCachedIo)(
                                            v5,
                                            v160,
                                            v3,
                                            FsContext,
                                            (union _LARGE_INTEGER)FileOffset[0].QuadPart,
                                            v199[0],
                                            v162);
                                  v194 = Flags;
                                  if ( Flags != 259 )
                                  {
                                    Flags = v3->IoStatus.Status;
                                    v194 = Flags;
                                    if ( Flags < 0 )
                                    {
                                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                                        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                                      {
                                        WPP_SF_dd(
                                          WPP_GLOBAL_Control->AttachedDevice,
                                          50,
                                          WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids,
                                          3221225705LL,
                                          Flags);
                                      }
                                      *((_DWORD *)v5 + 4) = Flags;
                                      if ( (_BYTE)RefsStatusDebugEnabled )
                                        RefsStatusDebug(Flags, v5, "write.c", 0xB00u);
                                      v163 = FsRtlNormalizeNtstatus(Flags, -1073741591);
                                      ExRaiseStatus(v163);
                                    }
                                    v110 = v198[0];
                                    if ( v198[0] )
                                      v3->IoStatus.Information = v198[0];
                                    else
                                      v3->IoStatus.Information = Length[0];
                                    v107 = v196;
                                    v109 = v195;
                                    v108 = v190;
                                    goto LABEL_359;
                                  }
                                  v40 &= ~0x80u;
                                  LOBYTE(v191) = v40;
                                  v5 = 0;
                                  Context2 = 0;
                                  v218 = 0;
                                  v212 = 0;
                                  v109 = 0;
                                  v195 = 0;
                                  v219 = 0;
                                  v107 = v196;
                                  v108 = v190;
LABEL_358:
                                  v110 = v198[0];
LABEL_359:
                                  v111 = (struct _IRP *)Context2;
                                  if ( Context2 )
                                  {
                                    if ( Flags >= 0 && Flags != 259 )
                                      *((_BYTE *)v109 + 56) |= 1u;
                                    v111->IoStatus.Status = Flags;
                                    if ( Flags >= 0 && (v107 & 1) != 0 )
                                      v111->IoStatus.Information = (unsigned int)v110;
                                    v112 = FileObject;
                                    RefsPostWriteProcessing(v5, FileObject, (__int64)FileOffset, (__int64)&v191);
                                    v107 = BYTE1(v191);
                                    if ( Flags >= 0 )
                                    {
                                      v107 = BYTE1(v191) & 0xFB;
                                      BYTE1(v191) &= ~4u;
                                    }
                                    v40 = v191;
                                    if ( (v107 & 0x40) != 0 && (v191 & 0x40) == 0 && FileOffset[0].QuadPart >= 0 )
                                    {
                                      if ( (Flags & 0xC0000000) == 0xC0000000 )
                                        Information = 0;
                                      else
                                        Information = v111->IoStatus.Information;
                                      v112->CurrentByteOffset.QuadPart = FileOffset[0].QuadPart + Information;
                                    }
                                    RefsCleanupTransaction(v5, Flags, 0);
                                    RefsCommitCurrentTransaction(v5, 0);
                                    RefsFlushForWriteThrough(v5, FsContext, 0);
                                    v108 = BYTE2(v191);
                                    v190 = BYTE2(v191);
                                  }
                                  if ( ((v107 & 4) != 0 || (v40 & 4) != 0) && Flags != 259 )
                                  {
                                    v174 = *(struct _FAST_MUTEX **)(FsContext + 48);
                                    KeEnterGuardedRegion();
                                    ExAcquireFastMutexUnsafe(v174);
                                    _InterlockedIncrement((volatile signed __int32 *)(FsContext + 172));
                                    if ( (v40 & 4) != 0 )
                                    {
                                      RefsCompleteFileSizeExtension(v5, (struct DataSCB *)FsContext, (__int64)&v191);
                                      v40 = v191 & 0xFB;
                                      v108 = BYTE2(v191);
                                      v107 = BYTE1(v191);
                                    }
                                    else
                                    {
                                      v108 = v190;
                                    }
                                    if ( (v107 & 4) != 0 && *(_QWORD *)(*(_QWORD *)(FsContext + 248) + 16LL) )
                                    {
                                      HighestPendingFileSize = RefsGetHighestPendingFileSize((const struct DataSCB *)FsContext);
                                      *(_QWORD *)(v176 + 8) = HighestPendingFileSize;
                                    }
                                    v177 = *((_QWORD *)v5 + 1);
                                    if ( (v177 & 0x20000) != 0 )
                                    {
                                      *((_QWORD *)v5 + 1) = v177 & 0xFFFFFFFFFFFDFFFFuLL;
                                      CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart = -1;
                                    }
                                    ++*(_DWORD *)(FsContext + 172);
                                    ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(FsContext + 48));
                                    KeLeaveGuardedRegion();
                                  }
                                  if ( v111 )
                                  {
                                    if ( (v107 & 0x10) != 0 )
                                      RefsReleaseFcb(v5, *(struct _FCB **)(FsContext + 136));
                                    if ( (v107 & 0x20) != 0 )
                                      *(_DWORD *)(*((_QWORD *)v5 + 13) + 4LL) &= ~2u;
                                  }
                                  if ( v40 < 0 )
                                  {
                                    if ( (v108 & 2) != 0 )
                                    {
                                      v222 = FsContext;
                                      RefsReleasePagingFastResource(v110, FsContext, (char *)v195 + 720);
                                    }
                                    else
                                    {
                                      v223 = FsContext;
                                      if ( *(_WORD *)FsContext != 2050 )
                                        FsContext = *(_QWORD *)(FsContext + 136);
                                      v178 = *(_QWORD *)(FsContext + 96);
                                      if ( !--DWORD2(v215) )
                                      {
                                        *((_QWORD *)&v215 + 1) &= 0xFFFFFFFD00000000uLL;
                                        ExReleaseFastResource(v178, v214);
                                      }
                                    }
                                  }
                                  HIDWORD(v215) &= ~1u;
                                  RefsCompleteReadWriteRequest(v5, v195, v111, Flags);
                                  return (unsigned int)Flags;
                                }
                              }
                              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
                                || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
                              {
                                Flags = -1073741822;
                              }
                              else
                              {
                                Flags = -1073741822;
                                WPP_SF_d(
                                  WPP_GLOBAL_Control->AttachedDevice,
                                  49,
                                  WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids,
                                  3221225474LL);
                              }
                              if ( !(_BYTE)RefsStatusDebugEnabled )
                                goto LABEL_354;
                              v106 = 2567;
LABEL_353:
                              RefsStatusDebug(Flags, 0, "write.c", v106);
LABEL_354:
                              v194 = Flags;
LABEL_355:
                              v107 = v196;
LABEL_356:
                              v108 = v190;
LABEL_357:
                              v109 = v195;
                              goto LABEL_358;
                            }
                            goto LABEL_622;
                          }
                          if ( v193 != 2 )
                          {
LABEL_552:
                            v150 = (v40 & 1) != 0;
                            v211 = v150;
                            if ( (v40 & 2) != 0 )
                            {
                              v150 |= 2u;
                              v211 = v150;
                            }
                            RefsPostUsnChange(v5, (struct _FCB *)FsContext, v150, 0);
                            goto LABEL_555;
                          }
                          v192 = 0;
                          v197 = 0;
                          *((_QWORD *)v145 + 6) = &v192;
                          if ( (Flags & 0x20) != 0 )
                          {
                            v146 = (struct _IRP_CONTEXT *)*((_QWORD *)v5 + 13);
                            if ( v146 != v5 )
                            {
                              *((_DWORD *)v146 + 1) &= ~2u;
                              LOBYTE(Flags) = Flags & 0xDF;
                              LODWORD(v196) = Flags;
                              BYTE1(v191) = Flags;
                              v197 = 1;
                            }
                          }
                          v224[0] = v145;
                          v224[1] = FsContext;
                          v224[2] = v214;
                          v225 = (v144 & 2) != 0;
                          *((_QWORD *)v5 + 18) = v224;
                          Flags = FsRtlCheckOplock(
                                    (POPLOCK)(FsContext + 88),
                                    v3,
                                    v5,
                                    RefsOplockComplete,
                                    RefsCommonWrite_::_415_::_lambda_1_::_lambda_invoker_cdecl_);
                          v194 = Flags;
                          v190 = v190 & 0xFD | (2 * v225);
                          BYTE2(v191) = v190;
                          if ( Flags )
                          {
                            if ( Flags == 259 && v192 )
                            {
                              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
                                || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
                              {
                                Flags = 871;
                              }
                              else
                              {
                                Flags = 871;
                                WPP_SF_d(
                                  WPP_GLOBAL_Control->AttachedDevice,
                                  47,
                                  WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids,
                                  871);
                              }
                              if ( (_BYTE)RefsStatusDebugEnabled )
                                RefsStatusDebug(871, 0, "write.c", 0x956u);
                              v194 = 871;
                            }
                            v107 = v196 & 0xEB;
                            BYTE1(v191) = v196 & 0xEB;
                            v5 = 0;
                            Context2 = 0;
                            v218 = 0;
                            v212 = 0;
                            v109 = 0;
                            v195 = 0;
                            v219 = 0;
                            v108 = v190;
                            goto LABEL_358;
                          }
                          if ( v197 )
                          {
                            *(_DWORD *)(*((_QWORD *)v5 + 13) + 4LL) |= 2u;
                            Flags = v196;
                            LOBYTE(Flags) = v196 | 0x20;
                            LODWORD(v196) = Flags;
                            BYTE1(v191) = Flags;
                          }
                          else
                          {
                            Flags = v196;
                          }
                          if ( *(_BYTE *)(FsContext + 5) )
                          {
LABEL_543:
                            v149 = *(FILE_LOCK **)(FsContext + 384);
                            if ( v149 && !FsRtlCheckLockForWriteAccess(v149, v3) )
                            {
                              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
                                || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
                              {
                                Flags = -1073741740;
                              }
                              else
                              {
                                Flags = -1073741740;
                                WPP_SF_d(
                                  WPP_GLOBAL_Control->AttachedDevice,
                                  48,
                                  WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids,
                                  3221225556LL);
                              }
                              if ( !(_BYTE)RefsStatusDebugEnabled )
                                goto LABEL_354;
                              v106 = 2448;
                              goto LABEL_353;
                            }
                            goto LABEL_552;
                          }
                          *(_QWORD *)v199 = *(_QWORD *)(FsContext + 144);
                          if ( (*(_DWORD *)(*(_QWORD *)v199 + 24LL) & 0x4000005) == 1
                            && *(_WORD *)FsContext == 2053
                            && (*(_DWORD *)(FsContext + 300) & 0x40) == 0
                            && *(char *)(*(_QWORD *)(FsContext + 136) + 8LL) >= 0 )
                          {
                            if ( (*(_DWORD *)(FsContext + 152) & 0x20) == 0 )
                              goto LABEL_533;
                            if ( FsRtlOplockIsFastIoPossible((POPLOCK)(FsContext + 88)) )
                            {
                              if ( *(__int16 *)(FsContext + 256) >= 0 )
                              {
                                v148 = *(_QWORD *)(FsContext + 384);
                                if ( (!v148 || !*(_BYTE *)(v148 + 16))
                                  && (*(_DWORD *)(*(_QWORD *)v199 + 24LL) & 0x2000000) == 0
                                  && (*(_BYTE *)(*(_QWORD *)(FsContext + 136) + 8LL) & 0x20) == 0 )
                                {
                                  v147 = 1;
                                  goto LABEL_542;
                                }
                              }
LABEL_533:
                              v147 = 2;
LABEL_542:
                              *(_BYTE *)(FsContext + 5) = v147;
                              goto LABEL_543;
                            }
                          }
                          v147 = 0;
                          goto LABEL_542;
                        }
                        goto LABEL_725;
                      }
LABEL_718:
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                      {
                        WPP_SF_d(
                          WPP_GLOBAL_Control->AttachedDevice,
                          37,
                          WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids,
                          3221225768LL);
                      }
                      if ( (_BYTE)RefsStatusDebugEnabled )
                        RefsStatusDebug(-1073741528, v5, "write.c", 0x726u);
                      RefsRaiseStatusInternal(v5, -1073741528, (unsigned int)v114);
LABEL_725:
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                      {
                        WPP_SF_d(
                          WPP_GLOBAL_Control->AttachedDevice,
                          38,
                          WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids,
                          (unsigned int)Flags);
                      }
                      if ( (_BYTE)RefsStatusDebugEnabled )
                        RefsStatusDebug(Flags, v5, "write.c", 0x72Cu);
                      RefsRaiseStatusInternal(v5, Flags, (unsigned int)v114);
                      goto LABEL_732;
                    }
LABEL_711:
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                    {
                      WPP_SF_d(
                        WPP_GLOBAL_Control->AttachedDevice,
                        35,
                        WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids,
                        3221225768LL);
                    }
                    if ( (_BYTE)RefsStatusDebugEnabled )
                      RefsStatusDebug(-1073741528, v5, "write.c", 0x6BBu);
                    RefsRaiseStatusInternal(v5, -1073741528, (unsigned int)v114);
                    goto LABEL_718;
                  }
LABEL_704:
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                  {
                    WPP_SF_d(
                      WPP_GLOBAL_Control->AttachedDevice,
                      34,
                      WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids,
                      3221225763LL);
                  }
                  if ( (_BYTE)RefsStatusDebugEnabled )
                    RefsStatusDebug(-1073741533, v5, "write.c", 0x6B6u);
                  RefsRaiseStatusInternal(v5, -1073741533, v96);
                  goto LABEL_711;
                }
LABEL_697:
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    31,
                    WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids,
                    3221226659LL);
                }
                if ( (_BYTE)RefsStatusDebugEnabled )
                  RefsStatusDebug(-1073740637, v5, "write.c", 0x6A0u);
                RefsRaiseStatusInternal(v5, -1073740637, v96);
                goto LABEL_704;
              }
            }
            if ( (v190 & 2) != 0 )
            {
              v228 = FsContext;
              v102 = (char *)v195 + 720;
            }
            else
            {
              v229 = FsContext;
              v102 = (char *)v214;
            }
            RefsReleasePagingFastResource(v101, FsContext, v102);
            LOBYTE(Flags) = v40 & 0x7F;
            LOBYTE(v191) = v40 & 0x7F;
            v103 = v190 & 0xFD;
            v190 = v103;
            BYTE2(v191) = v103;
          }
          v234 = FsContext;
          v104 = Flags & 0x7F
               | ((unsigned __int8)RefsAcquirePagingFastResourceExclusive(v99, FsContext, v214, v103 & 1) << 7);
LABEL_340:
          v40 = v104 | 0x20;
          Flags = (unsigned __int8)v40;
          LOBYTE(v191) = v40;
          goto LABEL_341;
        }
LABEL_339:
        v230 = FsContext;
        v104 = v40 & 0x7F | ((unsigned __int8)RefsAcquirePagingFastResourceExclusive(v92, FsContext, v214, v80) << 7);
        goto LABEL_340;
      }
LABEL_316:
      if ( !FileObject->SectionObjectPointer->SharedCacheMap )
        goto LABEL_339;
      goto LABEL_317;
    }
    if ( v210 && (*((_DWORD *)v210 + 2) & 2) != 0 )
      *((_DWORD *)v5 + 158) = *((_DWORD *)v210 + 21);
    if ( v5 == *((struct _IRP_CONTEXT **)v5 + 13) && LOBYTE(IoGetTopLevelIrp()->Type) )
    {
      LOBYTE(IoGetTopLevelIrp()->Type) = 0;
    }
    else if ( (*(_BYTE *)(*((_QWORD *)v5 + 13) + 8LL) & 8) != 0 )
    {
      *((_QWORD *)v5 + 1) |= 8uLL;
      v125 = v195;
      *((_BYTE *)v195 + 56) |= 2u;
      goto LABEL_425;
    }
    v125 = v195;
LABEL_425:
    if ( !*(_QWORD *)(FsContext + 16)
      || (unsigned __int8)ExIsFastResourceHeld(*(_QWORD *)(*(_QWORD *)(FsContext + 136) + 96LL))
      || (unsigned __int8)ExIsFastResourceHeld(*(_QWORD *)(*(_QWORD *)(FsContext + 136) + 88LL) + 64LL) )
    {
      goto LABEL_446;
    }
    if ( (*(_DWORD *)(FsContext + 152) & 0x10) != 0
      && (v126 = *(_QWORD *)(*(_QWORD *)(FsContext + 136) + 8LL) & 0x40000100LL, v126 == 0x40000000) )
    {
      v231 = FsContext;
    }
    else
    {
      v232 = FsContext;
      v40 = v40 & 0x7F
          | ((unsigned __int8)RefsAcquirePagingFastResourceSharedStarveExclusive(v126, FsContext, v214) << 7);
      LOBYTE(v191) = v40;
      if ( v40 >= 0 || (*(_DWORD *)(FsContext + 152) & 0x10) == 0 || !_FCB::HasPurgeableEAs(*(_FCB **)(FsContext + 136)) )
      {
LABEL_438:
        if ( v40 >= 0 )
        {
          v40 &= ~0x20u;
          LOBYTE(v191) = v40;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            Flags = -1073741740;
          }
          else
          {
            Flags = -1073741740;
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              39,
              WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids,
              3221225556LL);
          }
          if ( !(_BYTE)RefsStatusDebugEnabled )
            goto LABEL_354;
          v106 = 1952;
          goto LABEL_353;
        }
LABEL_446:
        if ( *(_DWORD *)(FsContext + 296) == 3 )
        {
          v128 = *(_WORD *)(FsContext + 216);
          if ( v128 == 128 || v128 == 176 )
          {
LABEL_732:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                40,
                WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids,
                3221226659LL);
            }
            if ( (_BYTE)RefsStatusDebugEnabled )
              RefsStatusDebug(-1073740637, v5, "write.c", 0x7AAu);
            RefsRaiseStatusInternal(v5, -1073740637, v91);
            goto LABEL_739;
          }
        }
        if ( (*(_DWORD *)(FsContext + 300) & 0x40) != 0 )
        {
LABEL_739:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              41,
              WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids,
              3221225763LL);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(-1073741533, v5, "write.c", 0x7B3u);
          RefsRaiseStatusInternal(v5, -1073741533, v91);
          goto LABEL_746;
        }
        v129 = *(_DWORD *)(FsContext + 300) & 0x4000;
        v130 = v129 != 0 ? 0xC000026E : 0;
        v199[0] = v130;
        v194 = v130;
        if ( v129 )
        {
LABEL_746:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids, v130);
            v130 = v199[0];
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(v130, v5, "write.c", 0x7BAu);
          RefsRaiseStatusInternal(v5, v199[0], v91);
          goto LABEL_753;
        }
        if ( IoGetTopLevelIrp()->MdlAddress == (PMDL)2 )
        {
          *((_QWORD *)v5 + 1) &= ~8uLL;
          *((_BYTE *)v125 + 56) &= ~2u;
          v131 = FileObject->Flags;
          if ( (*(_DWORD *)(FsContext + 300) & 0x100) != 0 )
            FileObject->Flags = v131 | 0x8000;
          else
            FileObject->Flags = v131 & 0xFFFF7FFF;
        }
        else
        {
          v132 = *((_QWORD *)v5 + 13);
          v133 = *(_DWORD *)(v132 + 4);
          if ( (v133 & 2) != 0 )
          {
            LOBYTE(Flags) = Flags | 8;
          }
          else
          {
            *(_DWORD *)(v132 + 4) = v133 | 2;
            LOBYTE(Flags) = Flags | 0x20;
          }
          BYTE1(v191) = Flags;
          LODWORD(v196) = Flags;
        }
        v134 = *(struct _FAST_MUTEX **)(FsContext + 48);
        KeEnterGuardedRegion();
        ExAcquireFastMutexUnsafe(v134);
        _InterlockedIncrement((volatile signed __int32 *)(FsContext + 172));
        v136 = *(union _LARGE_INTEGER *)(FsContext + 24);
        v137 = FileOffset[0];
        if ( FileOffset[0].QuadPart >= v136.QuadPart )
        {
          *((_QWORD *)v5 + 86) = 2;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_iiP)(
              WPP_GLOBAL_Control->AttachedDevice,
              43,
              v135,
              (union _LARGE_INTEGER)FileOffset[0].QuadPart,
              *(_QWORD *)(FsContext + 24),
              FsContext);
          }
          *((_QWORD *)Context2 + 7) = 0;
          ++*(_DWORD *)(FsContext + 172);
          ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(FsContext + 48));
          KeLeaveGuardedRegion();
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids, 0);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(0, 0, "write.c", 0x828u);
LABEL_470:
          Flags = 0;
          goto LABEL_354;
        }
        v138.QuadPart = -(__int64)*(int *)(v209 + 288) & (v136.QuadPart + *(int *)(v209 + 288) - 1LL);
        if ( FileOffset[1].QuadPart <= v138.QuadPart )
        {
          v138 = FileOffset[1];
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_iiP)(
              WPP_GLOBAL_Control->AttachedDevice,
              45,
              (union _LARGE_INTEGER)FileOffset[1].QuadPart,
              (union _LARGE_INTEGER)FileOffset[1].QuadPart,
              (union _LARGE_INTEGER)v138.QuadPart,
              FsContext);
            v137 = FileOffset[0];
          }
          FileOffset[1] = v138;
          Length[0] = v138.LowPart - v137.LowPart;
        }
        v139 = *(union _LARGE_INTEGER *)(FsContext + 24);
        if ( v138.QuadPart > v139.QuadPart )
        {
          if ( v137.QuadPart >= v139.QuadPart )
          {
            *((_QWORD *)Context2 + 7) = 0;
            *(__m128i *)&FileOffset[0].LowPart = _mm_load_si128((const __m128i *)&_xmm);
            Length[0] = -1159767027;
            ++*(_DWORD *)(FsContext + 172);
            ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(FsContext + 48));
            KeLeaveGuardedRegion();
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids, 0);
            }
            if ( (_BYTE)RefsStatusDebugEnabled )
            {
              RefsStatusDebug(0, 0, "write.c", 0x858u);
              Flags = 0;
              goto LABEL_354;
            }
            goto LABEL_470;
          }
          FileOffset[1] = *(union _LARGE_INTEGER *)(FsContext + 24);
          Length[0] = v139.LowPart - v137.LowPart;
        }
        v140 = RefsGetHighestPendingFileSize((const struct DataSCB *)FsContext);
        if ( v143 > v140 )
        {
          if ( v140 <= v141 )
          {
            LOBYTE(Flags) = Flags | 2;
            BYTE1(v191) = Flags;
          }
          else
          {
            v198[0] = v140 - v142;
            v226 = v140 - v142;
          }
          LOBYTE(Flags) = Flags | 1;
          LODWORD(v196) = Flags;
          BYTE1(v191) = Flags;
        }
        ++*(_DWORD *)(FsContext + 172);
        ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(FsContext + 48));
        KeLeaveGuardedRegion();
        if ( (*(_BYTE *)(FsContext + 4) & 0x20) != 0 && (*(_DWORD *)(FsContext + 152) & 0x40000) != 0 )
        {
          v123 = *(unsigned int *)(*(_QWORD *)(FsContext + 136) + 8LL);
          if ( (v123 & 0x100) == 0 )
          {
            if ( (Flags & 2) == 0 )
              RefsPostUsnChange(v5, (struct _FCB *)FsContext, 1u, 0);
            RefsCheckpointCurrentTransaction(v5);
          }
        }
        v3 = (PIRP)Context2;
        goto LABEL_499;
      }
      v233 = FsContext;
      RefsReleasePagingFastResource(v127, FsContext, v214);
      v235 = FsContext;
    }
    v40 = v40 & 0x7F | ((unsigned __int8)RefsAcquirePagingFastResourceExclusive(v126, FsContext, v214, 0) << 7) | 0x20;
    LOBYTE(v191) = v40;
    goto LABEL_438;
  }
  if ( (*(_DWORD *)(v78 + 24) & 2) != 0 || (CurrentStackLocation->Flags & 0x10) != 0 )
  {
    v83 = FileOffset[0].QuadPart;
  }
  else
  {
    v83 = FileOffset[0].QuadPart;
    if ( FileOffset[0].QuadPart >= 0
      && FileOffset[0].QuadPart < *(_QWORD *)(FsContext + 32)
      && FileOffset[1].QuadPart > (unsigned int)(16 * *(_DWORD *)(v78 + 276)) )
    {
      if ( a2 )
        *((_QWORD *)v5 + 86) = 3;
      if ( v40 < 0 )
      {
        if ( *(_WORD *)FsContext != 2050 )
          FsContext = *v202;
        v84 = *(_QWORD *)(FsContext + 96);
        if ( !--DWORD2(v215) )
        {
          *((_QWORD *)&v215 + 1) &= 0xFFFFFFFD00000000uLL;
          ExReleaseFastResource(v84, v214);
        }
      }
      RefsCompleteReadWriteRequest(v5, a2, v3, -1073741790);
      return 3221225506LL;
    }
  }
  if ( (*((_DWORD *)v210 + 1) & 0x100) != 0 )
    goto LABEL_281;
  if ( v83 < 0 || (v85 = *(union _LARGE_INTEGER *)(FsContext + 32), v85.QuadPart <= v83) )
  {
    if ( a2 )
      *((_QWORD *)v5 + 86) = 3;
    if ( v40 < 0 )
    {
      if ( *(_WORD *)FsContext != 2050 )
        FsContext = *v202;
      v87 = *(_QWORD *)(FsContext + 96);
      if ( !--DWORD2(v215) )
      {
        *((_QWORD *)&v215 + 1) &= 0xFFFFFFFD00000000uLL;
        ExReleaseFastResource(v87, v214);
      }
    }
    goto LABEL_228;
  }
  if ( v85.QuadPart >= FileOffset[1].QuadPart )
  {
LABEL_281:
    v86 = Length[0];
  }
  else
  {
    FileOffset[1] = *(union _LARGE_INTEGER *)(FsContext + 32);
    v86 = v85.LowPart - v83;
    Length[0] = v86;
  }
  v89 = RefsVolumeDasdIo(v5, a2, v3, (struct _SCB *)FsContext, v210, v83, v86);
  if ( v89 >= 0 )
    RefsUpdateFileTimestampsForModification(FileObject, v207, v210, v88);
  if ( (Flags & 0x40) != 0 && (v40 & 0x40) == 0 && v89 >= 0 )
    FileObject->CurrentByteOffset.QuadPart = FileOffset[0].QuadPart + v3->IoStatus.Information;
  if ( v40 < 0 )
  {
    if ( *(_WORD *)FsContext != 2050 )
      FsContext = *v202;
    v90 = *(_QWORD *)(FsContext + 96);
    if ( !--DWORD2(v215) )
    {
      *((_QWORD *)&v215 + 1) &= 0xFFFFFFFD00000000uLL;
      ExReleaseFastResource(v90, v214);
    }
  }
  if ( v190 )
    RefsCompleteReadWriteRequest(v5, v195, v3, v89);
  return (unsigned int)v89;
}

```

## disassembly

```asm
0x1400a7f90  mov     r11, rsp
0x1400a7f93  push    rbx
0x1400a7f94  push    rsi
0x1400a7f95  push    rdi
0x1400a7f96  push    r12
0x1400a7f98  push    r13
0x1400a7f9a  push    r14
0x1400a7f9c  push    r15
0x1400a7f9e  sub     rsp, 260h
0x1400a7fa5  mov     rax, cs:__security_cookie
0x1400a7fac  xor     rax, rsp
0x1400a7faf  mov     [rsp+298h+var_40], rax
0x1400a7fb7  mov     rbx, r8
0x1400a7fba  mov     [r11-1B0h], rbx
0x1400a7fc1  mov     r12, rdx
0x1400a7fc4  mov     [r11-218h], rdx
0x1400a7fcb  mov     rdi, rcx
0x1400a7fce  mov     [r11-180h], rcx
0x1400a7fd5  mov     [r11-0F8h], rdx
0x1400a7fdc  mov     [r11-100h], rbx
0x1400a7fe3  xorps   xmm0, xmm0
0x1400a7fe6  xor     eax, eax
0x1400a7fe8  movups  xmmword ptr [rsp+298h+FileOffset], xmm0
0x1400a7ff0  movups  xmmword ptr [rsp+298h+Length], xmm0
0x1400a7ff8  mov     [r11-1B8h], rax
0x1400a7fff  xor     r15d, r15d
0x1400a8002  mov     dword ptr [rsp+298h+var_224], r15d
0x1400a8007  movups  [rsp+298h+var_168], xmm0
0x1400a800f  movups  [rsp+298h+var_158], xmm0
0x1400a8017  movups  [rsp+298h+var_148], xmm0
0x1400a801f  movups  [rsp+298h+var_138], xmm0
0x1400a8027  movups  [rsp+298h+var_128], xmm0
0x1400a802f  mov     [r11-118h], rax
0x1400a8036  mov     rax, [r8+0B8h]
0x1400a803d  mov     [rsp+298h+var_1A0], rax
0x1400a8045  mov     r8, [rax+30h]
0x1400a8049  mov     [rsp+298h+FileObject], r8
0x1400a8051  mov     rsi, [r8+18h]
0x1400a8055  test    rsi, rsi
0x1400a8058  jz      loc_1400AB247
0x1400a805e  mov     r9, [rsi+90h]
0x1400a8065  mov     [rsp+298h+var_198], r9
0x1400a806d  mov     r13, [r8+20h]
0x1400a8071  mov     [rsp+298h+var_190], r13
0x1400a8079  mov     ecx, [r9+18h]
0x1400a807d  test    cl, 1
0x1400a8080  jnz     loc_1400A811D
0x1400a8086  test    r13, r13
0x1400a8089  jz      short loc_1400A809B
0x1400a808b  cmp     byte ptr [r13+50h], 4
0x1400a8090  jnz     short loc_1400A809B
0x1400a8092  test    cl, 2
0x1400a8095  jnz     loc_1400A811D
0x1400a809b  or      dword ptr [rdi+4], 100h
0x1400a80a2  mov     r9d, [rdi+10h]
0x1400a80a6  test    r9d, r9d
0x1400a80a9  js      short loc_1400A80B4
0x1400a80ab  mov     dword ptr [rdi+10h], 0C000026Eh
0x1400a80b2  jmp     short loc_1400A810D
0x1400a80b4  lea     r13, WPP_GLOBAL_Control
0x1400a80bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a80c2  cmp     rcx, r13
0x1400a80c5  jz      short loc_1400A80EB
0x1400a80c7  test    dword ptr [rcx+2Ch], 100h
0x1400a80ce  jz      short loc_1400A80EB
0x1400a80d0  cmp     byte ptr [rcx+29h], 4
0x1400a80d4  jb      short loc_1400A80EB
0x1400a80d6  mov     edx, 0Bh
0x1400a80db  lea     r8, WPP_3a66e9b7f5c134dfe789af195554f06a_Traceguids
0x1400a80e2  mov     rcx, [rcx+18h]
0x1400a80e6  call    WPP_SF_d
0x1400a80eb  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1400a80f2  test    al, al
0x1400a80f4  jz      short loc_1400A810D
0x1400a80f6  mov     r9d, 3C7h; unsigned int
0x1400a80fc  lea     r8, aNtfsdataC; "NtfsData.c"
0x1400a8103  xor     edx, edx; struct _IRP_CONTEXT *
0x1400a8105  mov     ecx, [rdi+10h]; Status
0x1400a8108  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1400a810d  mov     ecx, [rdi+10h]; Status
0x1400a8110  call    cs:__imp_ExRaiseStatus
0x1400a811d  test    r13, r13
0x1400a8120  jnz     short loc_1400A812A
0x1400a8122  mov     dl, 5
0x1400a8124  mov     byte ptr [rsp+298h+var_224+5], dl
0x1400a8128  jmp     short loc_1400A8147
0x1400a812a  movzx   edx, byte ptr [r13+50h]
0x1400a812f  mov     byte ptr [rsp+298h+var_224+5], dl
0x1400a8133  lea     eax, [rdx-2]
0x1400a8136  test    al, 0FCh
0x1400a8138  jnz     loc_1400AB247
0x1400a813e  cmp     dl, 3
0x1400a8141  jz      loc_1400AB247
0x1400a8147  lea     rax, [rsi+88h]
0x1400a814e  mov     [rsp+298h+var_1E0], rax
0x1400a8156  mov     rax, [rax]
0x1400a8159  mov     [rsp+298h+var_1A8], rax
0x1400a8161  mov     rax, [rax+58h]
0x1400a8165  cmp     qword ptr [rax+100h], 521h
0x1400a8170  jnz     short loc_1400A8183
0x1400a8172  cmp     qword ptr [rax+0F8h], 400h
0x1400a817d  jz      loc_1400AB247
0x1400a8183  mov     rax, [rdi+68h]
0x1400a8187  mov     r14d, [rax+10h]
0x1400a818b  test    r14d, r14d
0x1400a818e  jns     loc_1400A83F1
0x1400a8194  test    dword ptr [rsi+98h], 2000h
0x1400a819e  jnz     loc_1400A83F1
0x1400a81a4  cmp     r14d, 0C00000D8h
0x1400a81ab  jz      short loc_1400A8217
0x1400a81ad  cmp     r14d, 0C0000188h
0x1400a81b4  jz      short loc_1400A8217
0x1400a81b6  cmp     r14d, 0C00001A8h
0x1400a81bd  jz      short loc_1400A8217
0x1400a81bf  lea     r13, WPP_GLOBAL_Control
0x1400a81c6  lea     rbx, aWriteC; "write.c"
0x1400a81cd  mov     r9d, r14d; int
0x1400a81d0  mov     r8, [rsp+298h+Context2]; struct _IRP *
0x1400a81d8  mov     rdx, [rsp+298h+var_218]; struct REFS_IO_CONTEXT *
0x1400a81e0  mov     rcx, rdi; struct _IRP_CONTEXT *
0x1400a81e3  call    ?RefsCompleteReadWriteRequest@@YAXPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteReadWriteRequest(_IRP_CONTEXT *,REFS_IO_CONTEXT *,_IRP *,long)
0x1400a81e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a81ef  cmp     rcx, r13
0x1400a81f2  jz      loc_1400A83CB
0x1400a81f8  test    dword ptr [rcx+2Ch], 100h
0x1400a81ff  jz      loc_1400A83CB
0x1400a8205  test    r14d, r14d
0x1400a8208  js      loc_1400A83AD
0x1400a820e  cmp     byte ptr [rcx+29h], 5
0x1400a8212  jmp     loc_1400A83B1
0x1400a8217  lea     r13, WPP_GLOBAL_Control
0x1400a821e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a8225  cmp     rcx, r13
0x1400a8228  jz      short loc_1400A8259
0x1400a822a  test    dword ptr [rcx+2Ch], 100h
0x1400a8231  jz      short loc_1400A8259
0x1400a8233  mov     r14d, 0C0000001h
0x1400a8239  cmp     byte ptr [rcx+29h], 4
0x1400a823d  jb      short loc_1400A825F
0x1400a823f  mov     edx, 13h
0x1400a8244  mov     r9d, r14d
0x1400a8247  lea     r8, WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids
0x1400a824e  mov     rcx, [rcx+18h]
0x1400a8252  call    WPP_SF_d
0x1400a8257  jmp     short loc_1400A825F
0x1400a8259  mov     r14d, 0C0000001h
0x1400a825f  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1400a8266  test    al, al
0x1400a8268  jz      loc_1400A81C6
0x1400a826e  mov     eax, cs:?RefsStatusDisplayStatus@@3JC; long volatile RefsStatusDisplayStatus
0x1400a8274  lea     rbx, aWriteC; "write.c"
0x1400a827b  cmp     eax, r14d
0x1400a827e  jnz     short loc_1400A82B5
0x1400a8280  mov     r9, gs:188h
0x1400a8289  mov     dword ptr [rsp+298h+var_268], 426h
0x1400a8291  mov     qword ptr [rsp+298h+Retrying], rbx
0x1400a8296  mov     [rsp+298h+BytesToWrite], r14d
0x1400a829b  lea     r8, Format; "th%p %x %s:%i\n"
0x1400a82a2  xor     edx, edx; Level
0x1400a82a4  mov     ecx, 95h; ComponentId
0x1400a82a9  call    cs:__imp_DbgPrintEx
0x1400a82b0  nop     dword ptr [rax+rax+00h]
0x1400a82b5  mov     ecx, cs:?RefsStatusBreakOnStatus@@3JC; long volatile RefsStatusBreakOnStatus
0x1400a82bb  mov     esi, cs:?RefsStatusBreakOnWin32Error@@3KC; ulong volatile RefsStatusBreakOnWin32Error
0x1400a82c1  cmp     ecx, r14d
0x1400a82c4  jz      short loc_1400A82E5
0x1400a82c6  test    esi, esi
0x1400a82c8  jz      loc_1400A8368
0x1400a82ce  mov     ecx, r14d; Status
0x1400a82d1  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1400a82d8  nop     dword ptr [rax+rax+00h]
0x1400a82dd  cmp     esi, eax
0x1400a82df  jnz     loc_1400A8368
0x1400a82e5  mov     rcx, cs:?RefsStatusBreakForThread@@3REAU_KTHREAD@@EA; _KTHREAD * RefsStatusBreakForThread
0x1400a82ec  mov     rsi, cs:?RefsStatusBreakForProcess@@3REAU_KPROCESS@@EA; _KPROCESS * RefsStatusBreakForProcess
0x1400a82f3  test    rcx, rcx
0x1400a82f6  jz      short loc_1400A8366
0x1400a82f8  mov     rax, gs:188h
0x1400a8301  cmp     rcx, rax
0x1400a8304  jnz     short loc_1400A8368
0x1400a8306  test    rsi, rsi
0x1400a8309  jz      short loc_1400A831C
0x1400a830b  call    cs:__imp_IoGetCurrentProcess
0x1400a8312  nop     dword ptr [rax+rax+00h]
0x1400a8317  cmp     rsi, rax
0x1400a831a  jnz     short loc_1400A8368
0x1400a831c  cmp     cs:?RefsStatusBreakForImage@@3PADA, r15b; char near * RefsStatusBreakForImage
0x1400a8323  jz      short loc_1400A8360
0x1400a8325  call    cs:__imp_IoGetCurrentProcess
0x1400a832c  nop     dword ptr [rax+rax+00h]
0x1400a8331  mov     rcx, rax
0x1400a8334  call    cs:__imp_PsGetProcessImageFileName
0x1400a833b  nop     dword ptr [rax+rax+00h]
0x1400a8340  mov     rdx, rax; Str2
0x1400a8343  mov     r8d, 0Fh; MaxCount
0x1400a8349  lea     rcx, ?RefsStatusBreakForImage@@3PADA; Str1
0x1400a8350  call    cs:__imp__strnicmp
0x1400a8357  nop     dword ptr [rax+rax+00h]
0x1400a835c  test    eax, eax
0x1400a835e  jnz     short loc_1400A8368
0x1400a8360  mov     eax, cs:?RefsStatusBreakForFsCtl@@3KC; ulong volatile RefsStatusBreakForFsCtl
0x1400a8366  int     2Ch; Windows NT - assertion failure
0x1400a8368  mov     ecx, 1
0x1400a836d  lock xadd cs:?RefsStatusNextQueueEntry@@3KA, ecx; ulong RefsStatusNextQueueEntry
0x1400a8375  inc     ecx
0x1400a8377  and     ecx, 0FFFh
0x1400a837d  shl     rcx, 5
0x1400a8381  mov     rax, gs:188h
0x1400a838a  lea     r8, ?RefsStatusQueue@@3PAU_REFS_STATUS_DEBUG_QUEUE_ENTRY@@A; _REFS_STATUS_DEBUG_QUEUE_ENTRY near * RefsStatusQueue
0x1400a8391  mov     [rcx+r8], rax
0x1400a8395  mov     [rcx+r8+8], r14d
0x1400a839a  mov     [rcx+r8+10h], rbx
0x1400a839f  mov     dword ptr [rcx+r8+18h], 426h
0x1400a83a8  jmp     loc_1400A81CD
0x1400a83ad  cmp     byte ptr [rcx+29h], 4
0x1400a83b1  jb      short loc_1400A83CB
0x1400a83b3  mov     edx, 14h
0x1400a83b8  mov     r9d, r14d
0x1400a83bb  lea     r8, WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids
0x1400a83c2  mov     rcx, [rcx+18h]
0x1400a83c6  call    WPP_SF_d
0x1400a83cb  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1400a83d2  test    al, al
0x1400a83d4  jz      short loc_1400A83E9
0x1400a83d6  mov     r9d, 42Ah; unsigned int
0x1400a83dc  mov     r8, rbx; char *
0x1400a83df  xor     edx, edx; struct _IRP_CONTEXT *
0x1400a83e1  mov     ecx, r14d; Status
0x1400a83e4  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1400a83e9  mov     eax, r14d
0x1400a83ec  jmp     loc_1400AB3F0
0x1400a83f1  and     ecx, 0A000021h
0x1400a83f7  cmp     ecx, 1
0x1400a83fa  jz      loc_1400A892F
0x1400a8400  mov     [rbx+38h], r15
0x1400a8404  mov     eax, [r9+18h]
0x1400a8408  test    al, 20h
0x1400a840a  jz      loc_1400A85B2
0x1400a8410  mov     r14d, 0C0000189h
0x1400a8416  mov     r9d, r14d; int
0x1400a8419  mov     r8, rbx; struct _IRP *
0x1400a841c  mov     rdx, r12; struct REFS_IO_CONTEXT *
0x1400a841f  mov     rcx, rdi; struct _IRP_CONTEXT *
0x1400a8422  call    ?RefsCompleteReadWriteRequest@@YAXPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteReadWriteRequest(_IRP_CONTEXT *,REFS_IO_CONTEXT *,_IRP *,long)
0x1400a8427  lea     r13, WPP_GLOBAL_Control
0x1400a842e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a8435  cmp     rcx, r13
0x1400a8438  jz      short loc_1400A8461
0x1400a843a  test    dword ptr [rcx+2Ch], 100h
0x1400a8441  jz      short loc_1400A8461
0x1400a8443  cmp     byte ptr [rcx+29h], 4
0x1400a8447  jb      short loc_1400A8461
0x1400a8449  mov     edx, 15h
0x1400a844e  mov     r9d, r14d
0x1400a8451  lea     r8, WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids
0x1400a8458  mov     rcx, [rcx+18h]
0x1400a845c  call    WPP_SF_d
0x1400a8461  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1400a8468  test    al, al
0x1400a846a  jz      loc_1400A85AA
0x1400a8470  mov     eax, cs:?RefsStatusDisplayStatus@@3JC; long volatile RefsStatusDisplayStatus
0x1400a8476  lea     rbx, aWriteC; "write.c"
0x1400a847d  cmp     eax, r14d
0x1400a8480  jnz     short loc_1400A84B7
0x1400a8482  mov     r9, gs:188h
0x1400a848b  mov     dword ptr [rsp+298h+var_268], 43Fh
0x1400a8493  mov     qword ptr [rsp+298h+Retrying], rbx
0x1400a8498  mov     [rsp+298h+BytesToWrite], r14d
0x1400a849d  lea     r8, Format; "th%p %x %s:%i\n"
0x1400a84a4  xor     edx, edx; Level
0x1400a84a6  mov     ecx, 95h; ComponentId
0x1400a84ab  call    cs:__imp_DbgPrintEx
0x1400a84b2  nop     dword ptr [rax+rax+00h]
0x1400a84b7  mov     ecx, cs:?RefsStatusBreakOnStatus@@3JC; long volatile RefsStatusBreakOnStatus
0x1400a84bd  mov     edi, cs:?RefsStatusBreakOnWin32Error@@3KC; ulong volatile RefsStatusBreakOnWin32Error
0x1400a84c3  cmp     ecx, r14d
0x1400a84c6  jz      short loc_1400A84E7
0x1400a84c8  test    edi, edi
0x1400a84ca  jz      loc_1400A856A
0x1400a84d0  mov     ecx, r14d; Status
0x1400a84d3  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1400a84da  nop     dword ptr [rax+rax+00h]
0x1400a84df  cmp     edi, eax
0x1400a84e1  jnz     loc_1400A856A
0x1400a84e7  mov     rcx, cs:?RefsStatusBreakForThread@@3REAU_KTHREAD@@EA; _KTHREAD * RefsStatusBreakForThread
0x1400a84ee  mov     rdi, cs:?RefsStatusBreakForProcess@@3REAU_KPROCESS@@EA; _KPROCESS * RefsStatusBreakForProcess
0x1400a84f5  test    rcx, rcx
0x1400a84f8  jz      short loc_1400A8568
0x1400a84fa  mov     rax, gs:188h
0x1400a8503  cmp     rcx, rax
0x1400a8506  jnz     short loc_1400A856A
0x1400a8508  test    rdi, rdi
0x1400a850b  jz      short loc_1400A851E
0x1400a850d  call    cs:__imp_IoGetCurrentProcess
0x1400a8514  nop     dword ptr [rax+rax+00h]
0x1400a8519  cmp     rdi, rax
0x1400a851c  jnz     short loc_1400A856A
0x1400a851e  cmp     cs:?RefsStatusBreakForImage@@3PADA, r15b; char near * RefsStatusBreakForImage
0x1400a8525  jz      short loc_1400A8562
0x1400a8527  call    cs:__imp_IoGetCurrentProcess
  ... truncated ...
```
