# FatCommonWrite

- ea: `0x14004af08`
- end: `0x14004cd88`
- name: `FatCommonWrite`
- size: `7808`
- prototype: `__int64 __fastcall(int, int)`
- caller_count: `3`
- callee_count: `34`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callers

- `0x140007530`
- `0x14003816c`
- `0x1400438e0`

## callees

- `0x140001858`
- `0x140001d4c`
- `0x140003128`
- `0x140005c80`
- `0x140007408`
- `0x140007440`
- `0x14000c680`
- `0x140020458`
- `0x1400226b8`
- `0x14002486c`
- `0x140024b3c`
- `0x14002d4a8`
- `0x14002d5a8`
- `0x14002d610`
- `0x14002d918`
- `0x14002e6ac`
- `0x14002e95c`
- `0x140033270`
- `0x140038eb4`
- `0x14003958c`
- `0x14003d880`
- `0x14003dae0`
- `0x14003e4b4`
- `0x1400426ec`
- `0x140044bac`
- `0x1400465f4`
- `0x1400466c8`
- `0x1400468c4`
- `0x140046998`
- `0x1400483bc`
- `0x140048740`
- `0x140049fa8`
- `0x14004a1d4`
- `0x14004af08`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14004b24f`
- `ntoskrnl!KeInitializeEvent` at `0x14004c079`
- `ntoskrnl!KeInitializeEvent` at `0x14004c0ec`
- `ntoskrnl!KeInitializeEvent` at `0x14004b24f`
- `ntoskrnl!KeInitializeEvent` at `0x14004c079`
- `ntoskrnl!KeInitializeEvent` at `0x14004c0ec`
- `ntoskrnl!KeClearEvent` at `0x14004c0b1`
- `ntoskrnl!KeClearEvent` at `0x14004c0b1`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004bb5d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004bd60`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004bb5d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004bd60`
- `ntoskrnl!CcPurgeCacheSection` at `0x14004b8d6`
- `ntoskrnl!CcPurgeCacheSection` at `0x14004b8d6`
- `ntoskrnl!KeSetTimer` at `0x14004c9d6`
- `ntoskrnl!KeSetTimer` at `0x14004c9d6`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x14004b65c`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x14004ba5f`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x14004bc1b`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x14004c816`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x14004b65c`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x14004ba5f`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x14004bc1b`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x14004c816`
- `ntoskrnl!FsRtlNotifyFullReportChange` at `0x14004cc10`
- `ntoskrnl!FsRtlNotifyFullReportChange` at `0x14004cc10`
- `ntoskrnl!FsRtlCheckOplock` at `0x14004c252`
- `ntoskrnl!FsRtlCheckOplock` at `0x14004c252`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14004c2a8`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14004c2a8`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x14004bcd8`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x14004bcd8`
- `ntoskrnl!PsUpdateDiskCounters` at `0x14004b5f3`
- `ntoskrnl!PsUpdateDiskCounters` at `0x14004ba21`
- `ntoskrnl!PsUpdateDiskCounters` at `0x14004b5f3`
- `ntoskrnl!PsUpdateDiskCounters` at `0x14004ba21`
- `ntoskrnl!PsGetThreadProcess` at `0x14004b5d0`
- `ntoskrnl!PsGetThreadProcess` at `0x14004ba01`
- `ntoskrnl!PsGetThreadProcess` at `0x14004b5d0`
- `ntoskrnl!PsGetThreadProcess` at `0x14004ba01`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14004b32c`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14004bb69`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14004beb1`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14004b32c`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14004bb69`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14004beb1`
- `ntoskrnl!ExInterlockedAddUlong` at `0x14004c099`
- `ntoskrnl!ExInterlockedAddUlong` at `0x14004cd21`
- `ntoskrnl!ExInterlockedAddUlong` at `0x14006008d`
- `ntoskrnl!ExInterlockedAddUlong` at `0x14004c099`
- `ntoskrnl!ExInterlockedAddUlong` at `0x14004cd21`
- `ntoskrnl!ExInterlockedAddUlong` at `0x14006008d`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x14004c698`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x14004c698`
- `ntoskrnl!ObfReferenceObject` at `0x14004c9b0`
- `ntoskrnl!ObfReferenceObject` at `0x14004c9b0`
- `ntoskrnl!CcCanIWrite` at `0x14004b018`
- `ntoskrnl!CcCanIWrite` at `0x14004b018`
- `ntoskrnl!CcSetReadAheadGranularity` at `0x14004c8dd`
- `ntoskrnl!CcSetReadAheadGranularity` at `0x14004c8dd`
- `ntoskrnl!KeInitializeTimer` at `0x14004c986`
- `ntoskrnl!KeInitializeTimer` at `0x14004c986`
- `ntoskrnl!KeInitializeDpc` at `0x14004c99f`
- `ntoskrnl!KeInitializeDpc` at `0x14004c99f`
- `ntoskrnl!CcDeferWrite` at `0x14004b05c`
- `ntoskrnl!CcDeferWrite` at `0x14004b05c`
- `ntoskrnl!FsRtlCheckLockForWriteAccess` at `0x14004c308`
- `ntoskrnl!FsRtlCheckLockForWriteAccess` at `0x14004c308`
- `ntoskrnl!CcCopyWriteEx` at `0x14004caa0`
- `ntoskrnl!CcCopyWriteEx` at `0x14004caa0`
- `ntoskrnl!CcPrepareMdlWrite` at `0x14004cafc`
- `ntoskrnl!CcPrepareMdlWrite` at `0x14004cafc`
- `ntoskrnl!ExAcquireSharedStarveExclusive` at `0x14004bb0d`
- `ntoskrnl!ExAcquireSharedStarveExclusive` at `0x14004bb0d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004bc9c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004ccb5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004bc9c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004ccb5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004b8fd`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004b931`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004bfa4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004bfc5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004ccea`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004cd3d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004cd59`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ff9d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ffc7`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400600ae`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400600cf`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004b8fd`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004b931`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004bfa4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004bfc5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004ccea`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004cd3d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004cd59`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ff9d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ffc7`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400600ae`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400600cf`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14004bd21`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14004bd21`
- `ntoskrnl!KeBugCheckEx` at `0x14004b68b`
- `ntoskrnl!KeBugCheckEx` at `0x14004baee`
- `ntoskrnl!KeBugCheckEx` at `0x14004b68b`
- `ntoskrnl!KeBugCheckEx` at `0x14004baee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b5b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ff72`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b5b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ff72`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004b1fe`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004b4be`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004c03b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004c955`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004b1fe`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004b4be`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004c03b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004c955`
- `ntoskrnl!CcSetFileSizes` at `0x14004c660`
- `ntoskrnl!CcSetFileSizes` at `0x14004cc83`
- `ntoskrnl!CcSetFileSizes` at `0x14004c660`
- `ntoskrnl!CcSetFileSizes` at `0x14004cc83`
- `ntoskrnl!ExRaiseStatus` at `0x14004b66a`
- `ntoskrnl!ExRaiseStatus` at `0x14004ba6d`
- `ntoskrnl!ExRaiseStatus` at `0x14004bc29`
- `ntoskrnl!ExRaiseStatus` at `0x14004c824`
- `ntoskrnl!ExRaiseStatus` at `0x14004c8ad`
- `ntoskrnl!ExRaiseStatus` at `0x14004b66a`
- `ntoskrnl!ExRaiseStatus` at `0x14004ba6d`
- `ntoskrnl!ExRaiseStatus` at `0x14004bc29`
- `ntoskrnl!ExRaiseStatus` at `0x14004c824`
- `ntoskrnl!ExRaiseStatus` at `0x14004c8ad`

## pseudocode

```c
__int64 __fastcall FatCommonWrite(__int64 a1, IRP *a2)
{
  IRP *v2; // r13
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  struct _FILE_OBJECT *v5; // r10
  _DWORD *v6; // r12
  bool v7; // zf
  int v8; // ecx
  ULONG Flags; // edx
  __int64 v10; // rdi
  BOOLEAN v12; // r8
  BOOLEAN Retrying; // bl
  union _LARGE_INTEGER ByteOffset; // rbx
  unsigned __int64 v15; // rcx
  __int64 v16; // r9
  DWORD v17; // r11d
  int v18; // eax
  __int64 v19; // r8
  __int64 v20; // r12
  __int64 v21; // rdx
  unsigned int *v22; // r10
  int v23; // eax
  unsigned int v24; // eax
  ULONG_PTR v25; // r15
  __int64 v26; // r9
  int v27; // r12d
  _BYTE *PoolWithTag; // rax
  DWORD v29; // edx
  unsigned int v30; // r10d
  struct _FILE_OBJECT *v31; // rcx
  int v32; // eax
  NTSTATUS Status; // ebx
  __int64 v34; // r15
  __int64 v35; // r8
  int v36; // r15d
  __int64 v37; // r8
  int v38; // eax
  unsigned int v39; // r9d
  unsigned int v40; // r15d
  int v41; // eax
  int v42; // ecx
  int v43; // ecx
  __int64 v44; // rax
  _BYTE *v45; // rax
  _BYTE *v46; // rdi
  unsigned int v47; // r8d
  unsigned int v48; // r11d
  int v49; // edx
  __int64 v50; // rcx
  unsigned __int64 v51; // r8
  PEPROCESS v52; // rax
  NTSTATUS v53; // eax
  int *v54; // rdx
  unsigned int v55; // edi
  __int64 v56; // rbx
  int v57; // ecx
  union _LARGE_INTEGER v58; // r8
  signed __int64 QuadPart; // r12
  union _LARGE_INTEGER v60; // rcx
  ULONG *v61; // rcx
  ULONG v62; // eax
  int v63; // eax
  __int64 v64; // rcx
  __int64 NextFcbBottomUp; // rax
  __int64 v66; // rcx
  __int64 v67; // r8
  __int64 v68; // r9
  __int64 v69; // rdi
  __int64 v70; // rcx
  __int64 i; // rdx
  __int64 v72; // rax
  ULONG *v73; // rax
  PEPROCESS ThreadProcess; // rax
  NTSTATUS v75; // eax
  void *v76; // rcx
  unsigned __int8 TopLevelIrp; // al
  _DWORD *v78; // rcx
  NTSTATUS v79; // eax
  char v80; // dl
  union _LARGE_INTEGER *p_FileOffset; // rdx
  void *v82; // rcx
  PIRP v83; // rax
  struct _IO_STACK_LOCATION *v84; // rdx
  char v85; // al
  bool v86; // al
  __int64 v87; // r8
  __int64 v88; // r9
  _QWORD *v89; // rcx
  _QWORD *v90; // rax
  __int64 v91; // rcx
  DWORD v92; // r10d
  union _LARGE_INTEGER v93; // rdx
  __int64 v94; // r9
  char v95; // al
  char v96; // al
  int v97; // ecx
  __int64 v98; // rdx
  struct _CC_FILE_SIZES *v99; // r8
  unsigned int v100; // r9d
  char v101; // r11
  unsigned int v102; // r10d
  int v103; // eax
  __int64 v104; // r9
  unsigned __int64 v105; // rcx
  unsigned __int64 v106; // r9
  PSECTION_OBJECT_POINTERS v107; // rax
  ULONG *v108; // rcx
  ULONG v109; // eax
  signed __int64 v110; // r8
  int v111; // r12d
  _DWORD *v112; // rax
  int v113; // eax
  NTSTATUS v114; // eax
  unsigned int v115; // eax
  PFILE_OBJECT v116; // r10
  unsigned int *v117; // rax
  struct _KTIMER *v118; // rax
  struct _KTIMER *v119; // rdi
  __int64 v120; // rdi
  char v121; // al
  __int64 v122; // rax
  __int64 v123; // r9
  ULONG_PTR v124; // rdi
  char v125; // al
  __int64 Information_low; // rdx
  int v127; // ecx
  DWORD v128; // eax
  char v129; // al
  unsigned int v130; // eax
  PSECTION_OBJECT_POINTERS SectionObjectPointer; // rax
  _QWORD *SharedCacheMap; // rcx
  ULONG BytesToWrite[2]; // [rsp+20h] [rbp-228h]
  char v134; // [rsp+50h] [rbp-1F8h]
  bool Wait; // [rsp+51h] [rbp-1F7h]
  char v136; // [rsp+52h] [rbp-1F6h]
  char v137; // [rsp+54h] [rbp-1F4h]
  unsigned int v138; // [rsp+54h] [rbp-1F4h]
  char v139; // [rsp+58h] [rbp-1F0h]
  char v140; // [rsp+59h] [rbp-1EFh]
  char v141; // [rsp+5Bh] [rbp-1EDh]
  PFILE_OBJECT FileObject; // [rsp+60h] [rbp-1E8h]
  __int64 v143; // [rsp+68h] [rbp-1E0h] BYREF
  int v144; // [rsp+70h] [rbp-1D8h]
  char v145; // [rsp+74h] [rbp-1D4h]
  char v146; // [rsp+75h] [rbp-1D3h]
  char v147; // [rsp+76h] [rbp-1D2h]
  char v148; // [rsp+77h] [rbp-1D1h]
  char v149; // [rsp+78h] [rbp-1D0h]
  char v150; // [rsp+79h] [rbp-1CFh]
  char v151; // [rsp+7Ah] [rbp-1CEh]
  unsigned int v152; // [rsp+7Ch] [rbp-1CCh]
  DWORD v153; // [rsp+80h] [rbp-1C8h]
  char v154; // [rsp+84h] [rbp-1C4h]
  char v155; // [rsp+85h] [rbp-1C3h]
  unsigned int v156; // [rsp+88h] [rbp-1C0h]
  DWORD v157; // [rsp+8Ch] [rbp-1BCh]
  ULONG Length; // [rsp+90h] [rbp-1B8h]
  int v159; // [rsp+94h] [rbp-1B4h]
  unsigned int v160; // [rsp+98h] [rbp-1B0h]
  char v161; // [rsp+9Ch] [rbp-1ACh]
  int v162; // [rsp+A0h] [rbp-1A8h]
  char v163; // [rsp+A4h] [rbp-1A4h]
  unsigned int v164; // [rsp+A8h] [rbp-1A0h]
  ULONG v165; // [rsp+ACh] [rbp-19Ch]
  union _LARGE_INTEGER FileOffset; // [rsp+B0h] [rbp-198h] BYREF
  int v167; // [rsp+B8h] [rbp-190h]
  int v168; // [rsp+BCh] [rbp-18Ch]
  int v169; // [rsp+C0h] [rbp-188h]
  unsigned int v170; // [rsp+C4h] [rbp-184h]
  ULONG_PTR BugCheckParameter3; // [rsp+C8h] [rbp-180h] BYREF
  ULONG *v172; // [rsp+D0h] [rbp-178h] BYREF
  _DWORD *v173; // [rsp+D8h] [rbp-170h]
  ULONG_PTR v174; // [rsp+E0h] [rbp-168h]
  struct _FILE_OBJECT *v175; // [rsp+E8h] [rbp-160h] BYREF
  int v176; // [rsp+F0h] [rbp-158h]
  DWORD LowPart; // [rsp+F4h] [rbp-154h]
  int v178; // [rsp+F8h] [rbp-150h]
  ULONG *p_Flags; // [rsp+100h] [rbp-148h]
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+108h] [rbp-140h] BYREF
  unsigned int v181; // [rsp+118h] [rbp-130h]
  unsigned int v182; // [rsp+11Ch] [rbp-12Ch]
  unsigned int v183; // [rsp+120h] [rbp-128h]
  ULONG v184; // [rsp+124h] [rbp-124h]
  unsigned int v185; // [rsp+128h] [rbp-120h]
  union _LARGE_INTEGER *v186; // [rsp+130h] [rbp-118h]
  unsigned __int64 v187; // [rsp+138h] [rbp-110h]
  __int128 v188; // [rsp+140h] [rbp-108h]
  ULONG *v189; // [rsp+150h] [rbp-F8h]
  _BYTE v190[64]; // [rsp+160h] [rbp-E8h] BYREF
  _BYTE v191[168]; // [rsp+1A0h] [rbp-A8h] BYREF
  __int64 v192; // [rsp+250h] [rbp+8h] BYREF
  IRP *v193; // [rsp+258h] [rbp+10h]
  unsigned int v194; // [rsp+260h] [rbp+18h]
  size_t Size; // [rsp+268h] [rbp+20h] BYREF

  v193 = a2;
  v192 = a1;
  v2 = a2;
  v143 = 0;
  BugCheckParameter3 = 0;
  v172 = 0;
  memset(v191, 0, 0x70u);
  FileOffset.QuadPart = 0;
  CurrentStackLocation = v2->Tail.Overlay.CurrentStackLocation;
  v174 = (ULONG_PTR)CurrentStackLocation;
  v5 = CurrentStackLocation->FileObject;
  FileObject = v5;
  v6 = (_DWORD *)(a1 + 68);
  v173 = (_DWORD *)(a1 + 68);
  v7 = (*(_DWORD *)(a1 + 68) & 2) == 0;
  v8 = *(_DWORD *)(a1 + 68) & 2;
  v153 = v8;
  Wait = !v7;
  Flags = v2->Flags;
  v137 = Flags;
  p_Flags = &v5->Flags;
  v165 = v5->Flags;
  v10 = CurrentStackLocation->Parameters.Read.Length;
  Length = v10;
  v164 = v10;
  if ( !(_DWORD)v10 )
  {
    v2->IoStatus.Information = 0;
LABEL_3:
    FatCompleteRequest_Real((PVOID)a1, v2);
    return 0;
  }
  LOBYTE(v194) = Flags & 1;
  if ( (Flags & 1) == 0 )
  {
    if ( !v8 || (v12 = 1, (*v6 & 0x200) != 0) )
      v12 = 0;
    if ( !CcCanIWrite(v5, v10, v12, (*v6 & 0x40) != 0) )
    {
      Retrying = (*v6 & 0x40) != 0;
      FatPrePostIrp((PVOID)a1, v2);
      *v6 |= 0x40u;
      CcDeferWrite(FileObject, FatAddToWorkque, (PVOID)a1, v2, v10, Retrying);
      return 259;
    }
    v5 = FileObject;
    LOBYTE(Flags) = v137;
  }
  v138 = Flags & 2;
  ByteOffset = CurrentStackLocation->Parameters.Read.ByteOffset;
  FileOffset = ByteOffset;
  LowPart = ByteOffset.LowPart;
  if ( ByteOffset.LowPart != -1 || (v139 = 1, ByteOffset.HighPart != -1) )
    v139 = 0;
  v17 = FatDecodeFileObject(v5, &v143, &BugCheckParameter3, &v172);
  v157 = v17;
  v18 = (unsigned __int8)v194;
  if ( v17 == 4 )
    v18 = 1;
  v159 = v18;
  v163 = v18;
  v19 = v138;
  v20 = v143;
  if ( v138 )
  {
    v15 = (unsigned __int64)(KeGetCurrentProcessorNumber() % (unsigned int)dword_140017D48) << 7;
    v21 = *(_QWORD *)(v143 + 1024);
    if ( v17 == 2 )
    {
      ++*(_DWORD *)(v15 + v21 + 20);
      *(_DWORD *)(v15 + v21 + 24) += v10;
    }
    else if ( v17 - 5 <= 1 )
    {
      ++*(_DWORD *)(v15 + v21 + 44);
      *(_DWORD *)(v15 + v21 + 48) += v10;
    }
    v22 = (unsigned int *)(a1 + 68);
    v23 = *(_DWORD *)(a1 + 68);
    if ( v17 == 2 )
      v24 = v23 | 0x400;
    else
      v24 = v23 & 0xFFFFFBFF;
    *v22 = v24;
  }
  else
  {
    v22 = (unsigned int *)(a1 + 68);
  }
  if ( v138 || v139 || v17 == 4 )
  {
    v25 = BugCheckParameter3;
  }
  else
  {
    v25 = BugCheckParameter3;
    if ( v17 == 2 )
      v26 = *(unsigned int *)(BugCheckParameter3 + 132);
    else
      v26 = 0;
    if ( !(unsigned __int8)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))FatIsIoRangeValid)(
                             v15,
                             (union _LARGE_INTEGER)FileOffset.QuadPart,
                             (unsigned int)v10,
                             v26) )
    {
      v2->IoStatus.Information = 0;
      v27 = -1073741697;
LABEL_35:
      FatCompleteRequest_Real((PVOID)a1, v2);
      return (unsigned int)v27;
    }
  }
  if ( !(_BYTE)v159 )
    goto LABEL_45;
  PoolWithTag = *(_BYTE **)(a1 + 80);
  if ( !PoolWithTag )
  {
    if ( v153 )
    {
      *(_QWORD *)(a1 + 80) = v191;
      *v22 |= 0x100u;
      PoolWithTag = v191;
    }
    else
    {
      PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)528, 0x70u, 0x58746146u);
      *(_QWORD *)(a1 + 80) = PoolWithTag;
    }
  }
  memset(PoolWithTag, 0, 0x70u);
  v29 = v153;
  if ( v153 )
  {
    KeInitializeEvent((PRKEVENT)(*(_QWORD *)(a1 + 80) + 24LL), NotificationEvent, 0);
    v17 = v157;
LABEL_45:
    v30 = v138;
    v31 = FileObject;
    v29 = v153;
    goto LABEL_46;
  }
  v30 = v138;
  if ( v138 )
    *(_QWORD *)(*(_QWORD *)(a1 + 80) + 40LL) = KeGetCurrentThread();
  else
    *(_QWORD *)(*(_QWORD *)(a1 + 80) + 40LL) = *(_QWORD *)(a1 + 80) | 3LL;
  *(_DWORD *)(*(_QWORD *)(a1 + 80) + 48LL) = v10;
  v31 = FileObject;
  *(_QWORD *)(*(_QWORD *)(a1 + 80) + 56LL) = FileObject;
  v17 = v157;
LABEL_46:
  v32 = *(_DWORD *)(v20 + 200);
  if ( (v32 & 0x40) != 0 )
  {
    v2->IoStatus.Information = 0;
    Status = -1073741431;
LABEL_48:
    FatCompleteRequest_Real((PVOID)a1, v2);
    return (unsigned int)Status;
  }
  if ( v17 != 5 )
  {
    v175 = v31;
    v54 = (int *)(a1 + 68);
    *(_QWORD *)&v188 = a1 + 68;
    v165 &= 2u;
    v152 = 0;
    v167 = 0;
    v178 = 0;
    LOBYTE(v19) = 0;
    v134 = 0;
    LOBYTE(v32) = 0;
    LOBYTE(Size) = 0;
    v161 = 0;
    v162 = v32;
    v150 = 0;
    v140 = 0;
    v146 = 0;
    v145 = 0;
    v151 = 0;
    v154 = 0;
    v148 = 0;
    LOBYTE(v16) = 0;
    LOBYTE(v194) = 0;
    v149 = 0;
    v136 = 0;
    v147 = 0;
    v141 = 0;
    v27 = 0;
    v144 = 0;
    v183 = v30;
    v189 = &v31->Flags;
    v184 = v165;
    v55 = Length;
    if ( v17 == 4 )
    {
      v56 = v143;
      v57 = *(unsigned __int16 *)(v143 + 298);
      if ( !*(_WORD *)(v143 + 298) )
        v57 = *(_DWORD *)(v143 + 312);
      v58.QuadPart = v57 * (unsigned __int64)*(unsigned __int16 *)(v143 + 288);
      Size = v58.QuadPart;
      QuadPart = FileOffset.QuadPart;
      if ( *(_DWORD *)(*(_QWORD *)(v143 + 136) + 72LL) != 7
        || (*(_DWORD *)(v143 + 200) & 1) != 0
        || (*(_BYTE *)(v174 + 2) & 0x10) != 0
        || (v172[1] & 0x10000) != 0
        || v139
        || FileOffset.QuadPart >= v58.QuadPart
        || (v60.QuadPart = *(unsigned __int16 *)(v143 + 288) * (unsigned __int64)*(unsigned __int16 *)(v143 + 292),
            FileOffset.QuadPart < v60.QuadPart)
        && Length <= v60.QuadPart - FileOffset.QuadPart )
      {
        v61 = v172;
        if ( (v172[1] & 0x50000) == 0 )
        {
          ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))FatQuickVerifyVcb)(
            a1,
            v143,
            (union _LARGE_INTEGER)v58.QuadPart,
            v16);
          v54 = (int *)(a1 + 68);
          v61 = v172;
        }
        if ( (v61[1] & 0x40000) != 0 )
          *v54 |= 0x1000u;
        v62 = v61[1];
        if ( (v62 & 0x200) == 0 )
        {
          v63 = *v54;
          LOBYTE(v194) = (*v54 & 2) != 0;
          *v54 = v63 | 2;
          FatAcquireExclusiveVcb_Real(a1, v56, 0, v16);
          NextFcbBottomUp = FatGetNextFcbBottomUp(v64, 0, *(_QWORD *)(v56 + 208));
          if ( NextFcbBottomUp )
          {
            v69 = NextFcbBottomUp;
            do
            {
              FatAcquireExclusiveFcb(a1, v69, v67, v68);
              v69 = FatGetNextFcbBottomUp(v70, v69, *(_QWORD *)(v56 + 208));
            }
            while ( v69 );
            v55 = Length;
          }
          if ( (*(_DWORD *)(v56 + 200) & 1) == 0 )
          {
            FatFlushFat(a1, v56);
            CcPurgeCacheSection((PSECTION_OBJECT_POINTERS)(v56 + 736), 0, 0, 0);
            FatPurgeReferencedFileObjects(a1, *(_QWORD *)(v56 + 208), 1);
          }
          for ( i = 0; ; i = v192 )
          {
            v72 = FatGetNextFcbBottomUp(v66, i, *(_QWORD *)(v56 + 208));
            v192 = v72;
            if ( !v72 )
              break;
            ExReleaseResourceLite(*(PERESOURCE *)(v72 + 8));
          }
          ExReleaseResourceLite((PERESOURCE)(v56 + 520));
          if ( !(_BYTE)v194 )
            *(_DWORD *)(a1 + 68) &= ~2u;
          v73 = v172;
          v172[1] |= 0x300u;
          v62 = v73[1];
        }
        if ( (v62 & 0x2000) != 0 )
        {
          if ( v139 )
            QuadPart = Size;
        }
        else
        {
          if ( v139 || QuadPart >= (__int64)Size )
            goto LABEL_3;
          if ( v55 > (__int64)(Size - QuadPart) )
          {
            v55 = Size - QuadPart;
            if ( !v153 )
              *(_DWORD *)(*(_QWORD *)(a1 + 80) + 48LL) = v55;
          }
        }
        FatLockUserBuffer(a1, v2, 0, v55);
        *p_Flags = FileObject->Flags | 0x1000;
        FatSingleAsync(a1, v56, QuadPart, v55, (__int64)v2);
        if ( FatDiskAccountingEnabled )
        {
          ThreadProcess = PsGetThreadProcess(KeGetCurrentThread());
          PsUpdateDiskCounters(ThreadProcess, 0, v55, 0, 1, 0);
        }
        if ( !v153 )
        {
          *(_QWORD *)(a1 + 80) = 0;
          FatDeleteIrpContext_Real((PVOID)a1);
          return 259;
        }
        FatWaitSync(a1);
        Status = v2->IoStatus.Status;
        if ( Status < 0 )
        {
          *(_DWORD *)(a1 + 72) = Status;
          v75 = FsRtlNormalizeNtstatus(Status, -1073741591);
          ExRaiseStatus(v75);
        }
        if ( v165 && !v138 )
          FileObject->CurrentByteOffset.QuadPart = QuadPart + v2->IoStatus.Information;
      }
      else
      {
        Status = -1073741790;
      }
      goto LABEL_48;
    }
    if ( v17 != 2 && v17 != 9 )
    {
      if ( v17 - 6 > 2 )
      {
        if ( v17 != 3 )
          KeBugCheckEx(0x23u, 0x210B59u, (int)v17, v25, 0);
        v27 = -1073741811;
        v144 = -1073741811;
        goto LABEL_364;
      }
      FatVerifyFcb(a1, v25);
      if ( !ExAcquireSharedStarveExclusive(*(PERESOURCE *)(v25 + 16), Wait) )
        goto LABEL_145;
      v141 = 1;
      if ( !v153 )
        *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL) = *(_QWORD *)(v25 + 16);
      v76 = *(void **)(v25 + 624);
      if ( v76 )
        KeWaitForSingleObject(v76, Executive, 0, 0, 0);
      TopLevelIrp = (unsigned __int8)IoGetTopLevelIrp();
      v78 = (_DWORD *)(a1 + 68);
      if ( (TopLevelIrp & 2) == 0 )
        *v78 |= 4u;
      if ( v157 == 8 )
        v54 = (int *)*(unsigned int *)(v25 + 440);
      else
        v54 = (int *)*(unsigned int *)(v25 + 32);
      if ( ByteOffset.LowPart >= (unsigned int)v54 )
      {
        v2->IoStatus.Information = 0;
        v27 = 0;
        v144 = 0;
LABEL_360:
        LOBYTE(v19) = 0;
        goto LABEL_361;
      }
      if ( v55 + ByteOffset.LowPart > (unsigned int)v54 )
      {
        v55 = (_DWORD)v54 - ByteOffset.LowPart;
        v164 = (_DWORD)v54 - ByteOffset.LowPart;
      }
      *v78 |= 0x4000u;
      BytesToWrite[0] = v55;
      v27 = 259;
      if ( (unsigned int)FatNonCachedIo(a1, (int)v2, v25, ByteOffset.LowPart, *(SIZE_T *)BytesToWrite, v55, 0) != 259 )
      {
        v27 = v2->IoStatus.Status;
        v144 = v27;
        if ( v27 < 0 )
        {
          *(_DWORD *)(a1 + 72) = v27;
          v79 = FsRtlNormalizeNtstatus(v27, -1073741591);
          ExRaiseStatus(v79);
        }
        goto LABEL_360;
      }
LABEL_160:
      *(_QWORD *)(a1 + 80) = 0;
      v2 = 0;
      v193 = 0;
LABEL_359:
      v144 = v27;
      goto LABEL_360;
    }
    v168 = 0;
    v169 = 0;
    v80 = v159;
    if ( (_BYTE)v159 )
    {
      if ( v30 )
        goto LABEL_175;
      if ( v31->SectionObjectPointer->DataSectionObject )
      {
        IoStatus = 0;
        if ( !(unsigned __int8)FatAcquireExclusiveFcb(a1, v25, v19, v16) )
          goto LABEL_145;
        v140 = 1;
        v154 = 1;
        ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v25 + 16), 1u);
        v141 = 1;
        p_FileOffset = (union _LARGE_INTEGER *)(v25 + 32);
        if ( !v139 )
          p_FileOffset = &FileOffset;
        CcCoherencyFlushAndPurgeCache(FileObject->SectionObjectPointer, p_FileOffset, v55, &IoStatus, 0);
        if ( IoStatus.Status < 0 && *(_DWORD *)(v25 + 240) )
        {
          v27 = -1073740747;
          goto LABEL_359;
        }
        v148 = 1;
        v30 = v138;
        v80 = v159;
      }
      LOBYTE(v32) = v140;
    }
    if ( !v30 )
    {
      if ( v153 || !v80 )
      {
        if ( !(_BYTE)v32 && !(unsigned __int8)FatAcquireSharedFcb(a1, v25, v19, v16) )
          goto LABEL_145;
      }
      else
      {
        if ( !(_BYTE)v32 && !(unsigned __int8)FatAcquireSharedFcbWaitForEx(a1, v25, v19, v16) )
          goto LABEL_145;
        *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL) = *(_QWORD *)(v25 + 8);
        if ( v148 )
          *(_QWORD *)(*(_QWORD *)(a1 + 80) + 32LL) = *(_QWORD *)(v25 + 16);
      }
      v140 = 1;
LABEL_188:
      IoStatus.Pointer = (PVOID)(v25 + 280);
      v19 = *(unsigned int *)(v25 + 280);
      v160 = v19;
      v169 = v19;
      v54 = (int *)*(unsigned int *)(v25 + 40);
      v156 = (unsigned int)v54;
      v168 = (int)v54;
      v186 = (union _LARGE_INTEGER *)(v25 + 32);
      v16 = *(unsigned int *)(v25 + 32);
      v152 = v16;
      v170 = v16;
      v30 = v138;
      if ( v138 )
      {
        if ( ByteOffset.LowPart >= (unsigned int)v16 )
        {
LABEL_190:
          v2->IoStatus.Information = 0;
          v27 = 0;
          v144 = 0;
LABEL_191:
          LOBYTE(v19) = 0;
LABEL_362:
          v31 = FileObject;
LABEL_363:
          LOBYTE(v16) = v194;
LABEL_364:
          v95 = Size;
          goto LABEL_365;
        }
        if ( v55 > (int)v16 - ByteOffset.LowPart )
          v55 = v16 - ByteOffset.LowPart;
        Length = v55;
        v164 = v55;
      }
      if ( *(struct _KTHREAD **)(v25 + 416) == KeGetCurrentThread() )
      {
        v145 = 1;
        if ( (*(_BYTE *)(v25 + 4) & 0x20) != 0
          && v55 + ByteOffset.LowPart > (unsigned int)v54
          && ByteOffset.LowPart < (unsigned int)v16
          && v55 + ByteOffset.LowPart > (((_DWORD)v54 + 4095) & 0xFFFFF000) )
        {
          v27 = -1073741740;
          v144 = -1073741740;
          goto LABEL_191;
        }
      }
      if ( (v2->Flags & 0x40) != 0 && (*(_DWORD *)(a1 + 68) & 0x10) != 0 )
      {
        v83 = IoGetTopLevelIrp();
        if ( (unsigned __int64)v83 <= 0xFFFF || v83->Type != 6 )
          goto LABEL_209;
        v84 = v83->Tail.Overlay.CurrentStackLocation;
        if ( v84->MajorFunction != 4 )
        {
          LODWORD(v54) = v156;
          v30 = v138;
          v85 = 0;
          goto LABEL_218;
        }
        if ( v84->FileObject->FsContext == FileObject->FsContext )
        {
          LODWORD(v54) = v156;
          v30 = v138;
          if ( (v83->Flags & 1) == 0 )
          {
            v85 = 1;
            v136 = 1;
            *(_DWORD *)(a1 + 68) |= 4u;
LABEL_218:
            LODWORD(v16) = v152;
LABEL_211:
            if ( v145 || v85 )
            {
              v86 = Wait;
              goto LABEL_247;
            }
            if ( !v139 && v55 + ByteOffset.LowPart <= (unsigned int)v54 )
            {
              v86 = Wait;
              goto LABEL_247;
            }
            if ( !v153 )
            {
              Wait = 1;
              *(_DWORD *)(a1 + 68) |= 2u;
              if ( (_BYTE)v159 )
                v146 = 1;
            }
            if ( v30 )
            {
              ExReleaseResourceLite(*(PERESOURCE *)(v25 + 16));
              v141 = 0;
LABEL_227:
              v30 = v138;
              goto LABEL_228;
            }
            if ( v154 )
            {
LABEL_228:
              if ( v146 )
              {
                v89 = *(_QWORD **)(v25 + 120);
                if ( *v89 || v55 + ByteOffset.LowPart > *(_DWORD *)(v25 + 40) || FatNoAsync )
                {
                  memset(*(void **)(a1 + 80), 0, 0x70u);
                  KeInitializeEvent((PRKEVENT)(*(_QWORD *)(a1 + 80) + 24LL), NotificationEvent, 0);
                  v146 = 0;
                }
                else
                {
                  if ( !v89[4] )
                  {
                    v90 = ExAllocatePoolWithTag((POOL_TYPE)1552, 0x18u, 0x74746146u);
                    if ( !ExPoolZeroingNativelySupported && v90 )
                    {
                      *(_OWORD *)v90 = 0;
                      v90[2] = 0;
                    }
                    *(_QWORD *)(*(_QWORD *)(v25 + 120) + 32LL) = v90;
                    KeInitializeEvent(*(PRKEVENT *)(*(_QWORD *)(v25 + 120) + 32LL), NotificationEvent, 0);
                  }
                  if ( !ExInterlockedAddUlong((PULONG)(*(_QWORD *)(v25 + 120) + 24LL), 1u, &SpinLock) )
                    KeClearEvent(*(PRKEVENT *)(*(_QWORD *)(v25 + 120) + 32LL));
                  v147 = 1;
                  *(_QWORD *)(*(_QWORD *)(a1 + 80) + 64LL) = *(_QWORD *)(v25 + 120);
                }
                v30 = v138;
              }
              v160 = *(_DWORD *)IoStatus.Pointer;
              v169 = v160;
              v54 = (int *)*(unsigned int *)(v25 + 40);
              v156 = (unsigned int)v54;
              v168 = (int)v54;
              v16 = v186->LowPart;
              v152 = v16;
              v170 = v16;
              if ( v30 )
              {
                if ( ByteOffset.LowPart >= (unsigned int)v16 )
                  goto LABEL_190;
                v55 = *(_DWORD *)(v174 + 8);
                Length = v55;
                v164 = v55;
                if ( v55 > (int)v16 - ByteOffset.LowPart )
                {
                  v55 = v16 - ByteOffset.LowPart;
                  Length = v16 - ByteOffset.LowPart;
                  v164 = v16 - ByteOffset.LowPart;
                }
              }
              v86 = Wait;
LABEL_247:
              if ( (_BYTE)v159 && !v86 )
                *(_DWORD *)(*(_QWORD *)(a1 + 80) + 48LL) = v55;
              v167 = v16;
              v178 = (int)v54;
              FatVerifyFcb(a1, v25);
              v92 = v157;
              if ( v139 )
              {
                ByteOffset.LowPart = v152;
                LowPart = v152;
                v93 = *v186;
                FileOffset = *v186;
                v94 = v157 == 2 ? *(unsigned int *)(v25 + 132) : 0LL;
                if ( !(unsigned __int8)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))FatIsIoRangeValid)(
                                         v91,
                                         (union _LARGE_INTEGER)v93.QuadPart,
                                         v55,
                                         v94) )
                {
                  v2->IoStatus.Information = 0;
                  v27 = -1073741697;
                  goto LABEL_359;
                }
              }
              if ( v138 )
              {
                LOBYTE(v97) = v162;
              }
              else
              {
                if ( v92 == 2 )
                {
                  v27 = FsRtlCheckOplock((POPLOCK)(v25 + 88), v2, (PVOID)a1, FatOplockComplete, FatPrePostIrp);
                  v144 = v27;
                  if ( v27 )
                  {
                    v95 = 1;
                    LOBYTE(v19) = 1;
                    v134 = 1;
                    v31 = FileObject;
                    v30 = 0;
                    LOBYTE(v16) = v194;
LABEL_365:
                    v120 = v143;
LABEL_366:
                    if ( v2 )
                    {
                      if ( (_BYTE)v19 )
                      {
                        if ( !v95 )
                        {
                          FatUnpinRepinnedBcbs(a1, v54, v19, v16);
                          if ( (_BYTE)v162 )
                          {
                            ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v25 + 16), 1u);
                            *(_DWORD *)(v25 + 32) = v167;
                            SharedCacheMap = FileObject->SectionObjectPointer->SharedCacheMap;
                            if ( SharedCacheMap )
                              SharedCacheMap[1] = *(_QWORD *)(v25 + 32);
                            ExReleaseResourceLite(*(PERESOURCE *)(v25 + 16));
                          }
                          v27 = FatFsdPostRequest((PVOID)a1, v2);
                          v144 = v27;
                        }
                      }
                      else
                      {
                        Information_low = LODWORD(v2->IoStatus.Information);
                        LODWORD(Size) = v2->IoStatus.Information;
                        if ( v165 && !v30 )
                        {
                          v19 = 3221225472LL;
                          v127 = Information_low;
                          if ( (v27 & 0xC0000000) == 0xC0000000 )
                            v127 = 0;
                          v128 = v127 + ByteOffset.LowPart;
                          v31 = FileObject;
                          FileObject->CurrentByteOffset.LowPart = v128;
                        }
                        if ( v27 >= 0 )
                        {
                          if ( !v30 )
                          {
                            v19 = (__int64)p_Flags;
                            *p_Flags = v31->Flags | 0x1000;
                          }
                          v129 = v162;
                          if ( (_BYTE)v162 )
                          {
                            if ( (_BYTE)v16 )
                            {
                              FatSetFileSizeInDirent(a1, v25);
                              if ( !*(_QWORD *)(v25 + 536) )
                                FatSetFullFileNameInFcb(a1);
                              FsRtlNotifyFullReportChange(
                                *(PNOTIFY_SYNC *)(v120 + 816),
                                (PLIST_ENTRY)(v120 + 800),
                                (PSTRING)(v25 + 528),
                                *(_WORD *)(v25 + 528) - *(_WORD *)(v25 + 544),
                                0,
                                0,
                                8u,
                                3u,
                                0);
                              Information_low = (unsigned int)Size;
                              v31 = FileObject;
                              v129 = v162;
                            }
                            if ( v129 && !(_BYTE)v194 )
                            {
                              v19 = (__int64)p_Flags;
                              *p_Flags = v31->Flags | 0x2000;
                            }
                          }
                          if ( v151 )
                          {
                            v130 = Information_low + ByteOffset.LowPart;
                            if ( v152 < (int)Information_low + ByteOffset.LowPart )
                              v130 = v152;
                            *(_DWORD *)(v25 + 40) = v130;
                            if ( (_BYTE)v159 )
                            {
                              SectionObjectPointer = v31->SectionObjectPointer;
                              if ( SectionObjectPointer )
                              {
                                if ( SectionObjectPointer->SharedCacheMap )
                                  CcSetFileSizes(v31, (PCC_FILE_SIZES)(v25 + 24));
                              }
                            }
                          }
                        }
                        FatUnpinRepinnedBcbs(a1, Information_low, v19, v16);
                      }
                    }
                    if ( v147 )
                      ExInterlockedAddUlong((PULONG)(*(_QWORD *)(v25 + 120) + 24LL), 0xFFFFFFFF, &SpinLock);
                    if ( v140 && v2 )
                      ExReleaseResourceLite(*(PERESOURCE *)(v25 + 8));
                    if ( v141 && v2 )
                      ExReleaseResourceLite(*(PERESOURCE *)(v25 + 16));
                    if ( v134 )
                      return (unsigned int)v27;
                    goto LABEL_35;
                  }
                  if ( !*(_BYTE *)(v25 + 5) )
                  {
                    if ( *(_DWORD *)(v25 + 196) == 1
                      && *(_WORD *)v25 == 1282
                      && FsRtlOplockIsFastIoPossible((POPLOCK)(v25 + 88)) )
                    {
                      if ( *(_BYTE *)(v25 + 336)
                        || *(_DWORD *)(*(_QWORD *)(v25 + 120) + 24LL)
                        || (*(_DWORD *)(*(_QWORD *)(v25 + 184) + 200LL) & 0x4000) != 0
                        || (*(_DWORD *)(v25 + 192) & 0x8000) != 0 )
                      {
                        v96 = 2;
                      }
                      else
                      {
                        v96 = 1;
                      }
                    }
                    else
                    {
                      v96 = 0;
                    }
                    *(_BYTE *)(v25 + 5) = v96;
                  }
                  if ( !FsRtlCheckLockForWriteAccess((PFILE_LOCK)(v25 + 320), v2) )
                  {
                    v27 = -1073741740;
                    goto LABEL_359;
                  }
                }
                v97 = (unsigned __int8)v162;
                if ( v55 + ByteOffset.LowPart > v152 )
                  v97 = 1;
                v162 = v97;
                v150 = v97;
              }
              if ( (_BYTE)v97 )
              {
                v176 = 0;
                v98 = v143;
                if ( (*(_DWORD *)(v143 + 200) & 0x1000) != 0 )
                  *(_DWORD *)(a1 + 68) |= 8u;
                v153 = v55 + ByteOffset.LowPart;
                v152 = v55 + ByteOffset.LowPart;
                v170 = v55 + ByteOffset.LowPart;
                if ( (*(_DWORD *)(v98 + 200) & 0x400000) != 0 && (*(_DWORD *)(v25 + 192) & 0x8000) != 0 )
                  v176 = *(_DWORD *)(v25 + 132);
                v99 = (struct _CC_FILE_SIZES *)(v25 + 24);
                v174 = v25 + 24;
                if ( *(_QWORD *)(v25 + 24) == -1 )
                {
                  FatLookupFileAllocationSize(a1, v25);
                  v98 = v143;
                  v99 = (struct _CC_FILE_SIZES *)v174;
                }
                v100 = v99->AllocationSize.LowPart;
                v185 = v100;
                v157 = v176 + v153;
                if ( v176 + v153 > v100 )
                {
                  v101 = 1;
                  v155 = 1;
                  if ( v100 )
                  {
                    v187 = 0;
                    v102 = 1 << *(_BYTE *)(v98 + 378);
                    v181 = -v102;
                    v103 = -v102 & (v153 - 1 + v102 + v176);
                    v55 = Length;
                    if ( v103 )
                    {
                      v104 = v103 - v100;
                      v182 = *(_DWORD *)(v98 + 368);
                      v105 = v182 * (v102 >> 5) / (unsigned int)v104 + 1;
                      if ( v105 > 0x20 )
                        v105 = 32;
                      v106 = v105 * v104;
                      v187 = v185 + v106;
                      if ( v187 > v181 )
                      {
                        v187 = v181;
                        v106 = v181 - (unsigned __int64)v185;
                      }
                      if ( v106 / v102 <= v182 )
                      {
                        FatAddFileAllocation(a1);
                        v101 = 0;
                        v155 = 0;
                        *(_DWORD *)(v25 + 192) |= 2u;
                      }
                    }
                  }
                  if ( v101 )
                    FatAddFileAllocation(a1);
                  v99 = (struct _CC_FILE_SIZES *)v174;
                }
                v186->LowPart = v153;
                v107 = FileObject->SectionObjectPointer;
                if ( v107 && v107->SharedCacheMap )
                  CcSetFileSizes(FileObject, v99);
              }
              if ( v145 || v136 || v55 + ByteOffset.LowPart <= v156 )
              {
                if ( v148 )
                  ExConvertExclusiveToSharedLite(*(PERESOURCE *)(v25 + 8));
              }
              else
              {
                v151 = 1;
              }
              v16 = v156;
              v54 = (int *)v156;
              if ( v160 > v156 )
                v54 = (int *)v160;
              v160 = (unsigned int)v54;
              v108 = v172;
              if ( v172 )
              {
                v109 = v172[1];
                if ( (v109 & 0x100000) == 0 )
                {
                  v172[1] = v109 | 0x100000;
                  v110 = *((_QWORD *)v108 + 2);
                  if ( v110 )
                  {
                    if ( !_InterlockedCompareExchange64((volatile signed __int64 *)(v25 + 152), v110, 0) )
                    {
                      *((_QWORD *)v108 + 2) = 0;
                      EfsFirstWriteEncryptOnCloseFileCallback(*(_QWORD *)(v25 + 152));
                      v54 = (int *)v160;
                      v16 = v156;
                    }
                  }
                }
              }
              if ( !(_BYTE)v159 )
              {
                v116 = FileObject;
                if ( !FileObject->PrivateCacheMap )
                {
                  v117 = (unsigned int *)(v25 + 24);
                  if ( *(_QWORD *)(v25 + 24) == -1 )
                  {
                    FatLookupFileAllocationSize(a1, v25);
                    v117 = (unsigned int *)(v25 + 24);
                    LODWORD(v116) = (_DWORD)FileObject;
                  }
                  if ( v152 > *v117 )
                  {
                    FatPopUpFileCorrupt(a1, v25);
                    *(_DWORD *)(a1 + 72) = -1073741566;
                    ExRaiseStatus(-1073741566);
                  }
                  FatInitializeCacheMap((int)v116, (int)v117, 0, (int)&qword_140017D90, (PVOID)v25);
                  CcSetReadAheadGranularity(FileObject, 0x10000u);
                  v116 = FileObject;
                  if ( (FileObject->Flags & 0x10) == 0 )
                  {
                    v108 = (ULONG *)v143;
                    if ( (*(_DWORD *)(v143 + 200) & 0x1000) != 0 )
                    {
                      if ( (FileOffset.LowPart & 0xFFF) != 0 || v55 < 0x1000 )
                      {
                        v118 = (struct _KTIMER *)ExAllocatePoolWithTag((POOL_TYPE)1552, 0xA8u, 0x66746146u);
                        v119 = v118;
                        if ( !ExPoolZeroingNativelySupported && v118 )
                          memset(v118, 0, 0xA8u);
                        KeInitializeTimer(v119 + 1);
                        KeInitializeDpc((PRKDPC)v119, FatDeferredFlushDpc, v119);
                        ObfReferenceObject(FileObject);
                        v119[2].TimerListEntry.Flink = (struct _LIST_ENTRY *)FileObject;
                        KeSetTimer(v119 + 1, (LARGE_INTEGER)-10000000LL, (PKDPC)v119);
                        v116 = FileObject;
                      }
                      else
                      {
                        v108 = p_Flags;
                        *p_Flags = FileObject->Flags | 0x10;
                        *v173 |= 4u;
                      }
                    }
                  }
                }
                v120 = v143;
                if ( ByteOffset.LowPart > v160 && !(unsigned __int8)FatZeroData(a1, v143, v116) )
                {
                  LOBYTE(v19) = 1;
                  v134 = 1;
                  v31 = FileObject;
                  v30 = v138;
                  LOBYTE(v16) = v194;
                  v95 = Size;
                  goto LABEL_366;
                }
                if ( (*v173 & 4) != 0 || (v121 = 0, (*(_DWORD *)(v120 + 200) & 0x1000) != 0) )
                  v121 = 1;
                LOBYTE(v194) = v121;
                v149 = v121;
                if ( (*(_BYTE *)(a1 + 65) & 2) == 0 )
                {
                  v122 = FatMapUserBuffer(v108, v2);
                  LOBYTE(v123) = Wait;
                  v124 = Length;
                  v125 = CcCopyWriteEx(FileObject, &FileOffset, Length, v123, v122, v2->Tail.Overlay.Thread);
                  v31 = FileObject;
                  v30 = v138;
                  if ( v125 )
                  {
                    v2->IoStatus.Status = 0;
                    v2->IoStatus.Information = v124;
                    v27 = 0;
                    v144 = 0;
                    LOBYTE(v19) = 0;
                  }
                  else
                  {
                    LOBYTE(v19) = 1;
                    v134 = 1;
                  }
                  goto LABEL_363;
                }
                CcPrepareMdlWrite(FileObject, &FileOffset, Length, &v2->MdlAddress, &v2->IoStatus);
                v27 = v2->IoStatus.Status;
                goto LABEL_359;
              }
              v19 = *(unsigned __int16 *)(v143 + 288);
              if ( (((_DWORD)v19 - 1) & ByteOffset.LowPart) != 0
                || (v111 = ~(v19 - 1) & (v55 + v19 - 1), v111 != v55) && v55 + ByteOffset.LowPart < (unsigned int)v16 )
              {
                v27 = -1073741822;
                goto LABEL_359;
              }
              if ( !v145 && !v136 && ByteOffset.LowPart > (unsigned int)v54 )
                FatZeroData(a1, v143, FileObject);
              LOBYTE(v194) = 1;
              v149 = 1;
              v112 = v173;
              if ( v146 )
                *v173 &= ~2u;
              BytesToWrite[0] = v111;
              v113 = FatNonCachedIo(
                       a1,
                       (int)v2,
                       v25,
                       ByteOffset.LowPart,
                       *(SIZE_T *)BytesToWrite,
                       v111,
                       *((_BYTE *)v112 + 2) & 2);
              v27 = 259;
              if ( v113 != 259 )
              {
                v27 = v2->IoStatus.Status;
                v144 = v27;
                if ( v27 < 0 )
                {
                  *(_DWORD *)(a1 + 72) = v27;
                  v114 = FsRtlNormalizeNtstatus(v27, -1073741591);
                  ExRaiseStatus(v114);
                }
                v2->IoStatus.Information = v55;
                v115 = v55 + ByteOffset.LowPart;
                if ( v55 + ByteOffset.LowPart > v152 )
                  v115 = v152;
                if ( *(_DWORD *)IoStatus.Pointer < v115 )
                  *(_DWORD *)IoStatus.Pointer = v115;
                goto LABEL_360;
              }
              v147 = 0;
              *v173 |= 2u;
              goto LABEL_160;
            }
            ExReleaseResourceLite(*(PERESOURCE *)(v25 + 8));
            v140 = 0;
            if ( (unsigned __int8)FatAcquireExclusiveFcb(a1, v25, v87, v88) )
            {
              v140 = 1;
              goto LABEL_227;
            }
LABEL_145:
            LOBYTE(v19) = 1;
            v134 = 1;
LABEL_361:
            v30 = v138;
            goto LABEL_362;
          }
          LODWORD(v16) = v152;
        }
        else
        {
LABEL_209:
          LODWORD(v54) = v156;
          LODWORD(v16) = v152;
          v30 = v138;
        }
      }
      v85 = 0;
      goto LABEL_211;
    }
LABEL_175:
    ExAcquireResourceSharedLite(*(PERESOURCE *)(v25 + 16), 1u);
    v141 = 1;
    if ( !v153 )
      *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL) = *(_QWORD *)(v25 + 16);
    v82 = *(void **)(v25 + 624);
    if ( v82 )
      KeWaitForSingleObject(v82, Executive, 0, 0, 0);
    goto LABEL_188;
  }
  v143 = 0;
  v175 = 0;
  LODWORD(v192) = 0;
  LODWORD(Size) = 0;
  v188 = 0;
  if ( v29 )
  {
    if ( ((unsigned __int8)IoGetTopLevelIrp() & 2) == 0 )
      *(_DWORD *)(a1 + 68) |= 4u;
    v34 = v20 + 384;
    if ( !(unsigned __int8)FatLookupMcbEntry(v20, v20 + 384, ByteOffset.LowPart, &v143, &v192, 0) )
      goto LABEL_3;
    v35 = v143;
    if ( !v143 && (unsigned int)v192 >= (unsigned int)v10 )
      goto LABEL_3;
    if ( !(_DWORD)v143 )
      v35 = (unsigned int)(ByteOffset.LowPart + v192);
    v194 = v35;
    while ( 1 )
    {
      if ( !(unsigned __int8)FatLookupMcbEntry(v20, v34, v35, &v143, &v192, 0) )
        KeBugCheckEx(0x23u, 0x210295u, 0, 0, 0);
      v160 = v10 + ByteOffset.LowPart;
      v36 = v192;
      v37 = (unsigned int)(v192 + v143);
      if ( (unsigned int)v37 >= (int)v10 + ByteOffset.LowPart )
        break;
      v7 = (unsigned __int8)FatLookupMcbEntry(v20, v20 + 384, v37, &v175, &Size, 0) == 0;
      v38 = v143;
      if ( v7 )
        goto LABEL_70;
      v35 = (unsigned int)(v143 + v36 + Size);
      if ( (unsigned int)v35 >= v160 )
        goto LABEL_70;
      v34 = v20 + 384;
    }
    v36 = ByteOffset.LowPart + v10 - v143;
    v38 = v143;
LABEL_70:
    v39 = v194;
    v40 = v38 + v36 - v194;
    *((_QWORD *)&v188 + 1) = v10;
    v41 = *(unsigned __int16 *)(v20 + 302);
    v42 = *(unsigned __int16 *)(v20 + 288);
    if ( (_WORD)v41 )
      v43 = v41 * v42;
    else
      v43 = *(_DWORD *)(v20 + 316) * v42;
    LODWORD(v192) = v43;
    v44 = *(unsigned __int8 *)(v20 + 294);
    if ( (unsigned __int8)v44 <= 2u )
    {
      v46 = v190;
    }
    else
    {
      Size = 32 * v44;
      v45 = ExAllocatePoolWithTag((POOL_TYPE)1041, 32 * v44, 0x69746146u);
      v46 = v45;
      if ( !ExPoolZeroingNativelySupported && v45 )
        memset(v45, 0, Size);
      v39 = v194;
    }
    Size = (size_t)v46;
    v47 = 0;
    LOBYTE(v48) = *(_BYTE *)(v20 + 294);
    if ( (_BYTE)v48 )
    {
      v49 = v192;
      do
      {
        v50 = 32LL * v47;
        *(_DWORD *)&v46[v50 + 8] = v39;
        *(_QWORD *)&v46[v50] = v39 + v47 * v49;
        *(_DWORD *)&v46[v50 + 12] = v39 - ByteOffset.LowPart;
        *(_DWORD *)&v46[v50 + 16] = v40;
        ++v47;
        v48 = *(unsigned __int8 *)(v20 + 294);
      }
      while ( v47 < v48 );
    }
    v51 = (unsigned __int64)(KeGetCurrentProcessorNumber() % (unsigned int)dword_140017D48) << 7;
    *(_DWORD *)(v51 + *(_QWORD *)(v20 + 1024) + 52) += (unsigned __int8)v48;
    FatMultipleAsync(a1, v20, v2, *(unsigned __int8 *)(v20 + 294), v46);
    if ( v46 != v190 )
      ExFreePoolWithTag(v46, 0);
    if ( FatDiskAccountingEnabled )
    {
      v52 = PsGetThreadProcess(KeGetCurrentThread());
      PsUpdateDiskCounters(v52, 0, v40, 0, 1, 0);
    }
    FatWaitSync(a1);
    if ( v2->IoStatus.Status < 0 )
      v188 = *(_OWORD *)&v2->IoStatus.Status;
    *(_OWORD *)&v2->IoStatus.Status = v188;
    Status = v2->IoStatus.Status;
    if ( Status < 0 )
    {
      *(_DWORD *)(a1 + 72) = Status;
      v53 = FsRtlNormalizeNtstatus(Status, -1073741591);
      ExRaiseStatus(v53);
    }
    FatRemoveMcbEntry(v20, v20 + 384, v194, v40);
    goto LABEL_48;
  }
  return FatFsdPostRequest((PVOID)a1, v2);
}

```

## disassembly

```asm
0x14004af08  mov     rax, rsp
0x14004af0b  mov     [rax+10h], rdx
0x14004af0f  mov     [rax+8], rcx
0x14004af13  push    rbx
0x14004af14  push    rsi
0x14004af15  push    rdi
0x14004af16  push    r12
0x14004af18  push    r13
0x14004af1a  push    r14
0x14004af1c  push    r15
0x14004af1e  sub     rsp, 210h
0x14004af25  mov     r13, rdx
0x14004af28  mov     r14, rcx
0x14004af2b  xor     esi, esi
0x14004af2d  mov     [rsp+248h+var_1E0], rsi
0x14004af32  mov     [rax-180h], rsi
0x14004af39  mov     [rax-178h], rsi
0x14004af40  xor     edx, edx; Val
0x14004af42  lea     r8d, [rsi+70h]; Size
0x14004af46  lea     rcx, [rax-0A8h]; void *
0x14004af4d  call    memset
0x14004af52  mov     qword ptr [rsp+248h+FileOffset], rsi
0x14004af5a  mov     rbx, [r13+0B8h]
0x14004af61  mov     [rsp+248h+var_168], rbx
0x14004af69  mov     r10, [rbx+30h]
0x14004af6d  mov     [rsp+248h+FileObject], r10
0x14004af72  lea     r12, [r14+44h]
0x14004af76  mov     [rsp+248h+var_170], r12
0x14004af7e  mov     ecx, [r12]
0x14004af82  and     ecx, 2
0x14004af85  mov     [rsp+248h+var_1C8], ecx
0x14004af8c  setnz   [rsp+248h+Wait]
0x14004af91  mov     edx, [r13+10h]
0x14004af95  mov     [rsp+248h+var_1F4], edx
0x14004af99  lea     rax, [r10+50h]
0x14004af9d  mov     [rsp+248h+var_148], rax
0x14004afa5  mov     eax, [rax]
0x14004afa7  mov     [rsp+248h+var_19C], eax
0x14004afae  mov     edi, [rbx+8]
0x14004afb1  mov     [rsp+248h+Length], edi
0x14004afb8  mov     [rsp+248h+var_1A0], edi
0x14004afbf  test    edi, edi
0x14004afc1  jnz     short loc_14004AFDD
0x14004afc3  mov     [r13+38h], rsi
0x14004afc7  xor     r8d, r8d
0x14004afca  mov     rdx, r13; Irp
0x14004afcd  mov     rcx, r14; Entry
0x14004afd0  call    FatCompleteRequest_Real
0x14004afd5  xor     eax, eax
0x14004afd7  jmp     loc_14004CD75
0x14004afdd  mov     al, dl
0x14004afdf  mov     r15d, 1
0x14004afe5  and     al, r15b
0x14004afe8  mov     byte ptr [rsp+248h+arg_10], al
0x14004afef  jnz     loc_14004B07B
0x14004aff5  mov     eax, [r12]
0x14004aff9  mov     r9d, eax
0x14004affc  shr     r9d, 6
0x14004b000  and     r9b, r15b; Retrying
0x14004b003  test    ecx, ecx
0x14004b005  jz      short loc_14004B010
0x14004b007  bt      eax, 9
0x14004b00b  mov     r8b, r15b
0x14004b00e  jnb     short loc_14004B013
0x14004b010  mov     r8b, sil; Wait
0x14004b013  mov     edx, edi; BytesToWrite
0x14004b015  mov     rcx, r10; FileObject
0x14004b018  call    cs:__imp_CcCanIWrite
0x14004b01f  nop     dword ptr [rax+rax+00h]
0x14004b024  test    al, al
0x14004b026  jnz     short loc_14004B072
0x14004b028  mov     ebx, [r12]
0x14004b02c  shr     ebx, 6
0x14004b02f  and     bl, r15b
0x14004b032  mov     rdx, r13; Irp
0x14004b035  mov     rcx, r14; Context
0x14004b038  call    FatPrePostIrp
0x14004b03d  or      dword ptr [r12], 40h
0x14004b042  mov     [rsp+248h+Retrying], bl; Retrying
0x14004b046  mov     [rsp+248h+BytesToWrite], edi; BytesToWrite
0x14004b04a  mov     r9, r13; Context2
0x14004b04d  mov     r8, r14; Context1
0x14004b050  lea     rdx, FatAddToWorkque; PostRoutine
0x14004b057  mov     rcx, [rsp+248h+FileObject]; FileObject
0x14004b05c  call    cs:__imp_CcDeferWrite
0x14004b063  nop     dword ptr [rax+rax+00h]
0x14004b068  mov     eax, 103h
0x14004b06d  jmp     loc_14004CD75
0x14004b072  mov     r10, [rsp+248h+FileObject]
0x14004b077  mov     edx, [rsp+248h+var_1F4]
0x14004b07b  and     edx, 2
0x14004b07e  mov     [rsp+248h+var_1F4], edx
0x14004b082  mov     rbx, [rbx+18h]
0x14004b086  mov     qword ptr [rsp+248h+FileOffset], rbx
0x14004b08e  mov     [rsp+248h+var_154], ebx
0x14004b095  cmp     ebx, 0FFFFFFFFh
0x14004b098  jnz     short loc_14004B0AB
0x14004b09a  mov     rax, rbx
0x14004b09d  shr     rax, 20h
0x14004b0a1  cmp     eax, 0FFFFFFFFh
0x14004b0a4  mov     [rsp+248h+var_1F0], r15b
0x14004b0a9  jz      short loc_14004B0B0
0x14004b0ab  mov     [rsp+248h+var_1F0], sil
0x14004b0b0  lea     r9, [rsp+248h+var_178]
0x14004b0b8  lea     r8, [rsp+248h+BugCheckParameter3]
0x14004b0c0  lea     rdx, [rsp+248h+var_1E0]
0x14004b0c5  mov     rcx, r10
0x14004b0c8  call    FatDecodeFileObject
0x14004b0cd  mov     r11d, eax
0x14004b0d0  mov     [rsp+248h+var_1BC], eax
0x14004b0d7  movzx   eax, byte ptr [rsp+248h+arg_10]
0x14004b0df  cmp     r11d, 4
0x14004b0e3  cmovz   eax, r15d
0x14004b0e7  mov     [rsp+248h+var_1B4], eax
0x14004b0ee  mov     [rsp+248h+var_1A4], al
0x14004b0f5  mov     r8d, [rsp+248h+var_1F4]
0x14004b0fa  mov     r12, [rsp+248h+var_1E0]
0x14004b0ff  test    r8d, r8d
0x14004b102  jz      short loc_14004B164
0x14004b104  mov     cl, gs:184h
0x14004b10c  movzx   eax, cl
0x14004b10f  xor     edx, edx
0x14004b111  div     cs:dword_140017D48
0x14004b117  mov     ecx, edx
0x14004b119  shl     rcx, 7
0x14004b11d  mov     rdx, [r12+400h]
0x14004b125  cmp     r11d, 2
0x14004b129  jnz     short loc_14004B136
0x14004b12b  add     [rcx+rdx+14h], r15d
0x14004b130  add     [rcx+rdx+18h], edi
0x14004b134  jmp     short loc_14004B148
0x14004b136  lea     eax, [r11-5]
0x14004b13a  cmp     eax, r15d
0x14004b13d  ja      short loc_14004B148
0x14004b13f  add     [rcx+rdx+2Ch], r15d
0x14004b144  add     [rcx+rdx+30h], edi
0x14004b148  lea     r10, [r14+44h]
0x14004b14c  mov     eax, [r10]
0x14004b14f  cmp     r11d, 2
0x14004b153  jnz     short loc_14004B15E
0x14004b155  bts     eax, 0Ah
0x14004b159  mov     [r10], eax
0x14004b15c  jmp     short loc_14004B168
0x14004b15e  btr     eax, 0Ah
0x14004b162  jmp     short loc_14004B159
0x14004b164  lea     r10, [r14+44h]
0x14004b168  test    r8d, r8d
0x14004b16b  jnz     short loc_14004B1C8
0x14004b16d  cmp     [rsp+248h+var_1F0], sil
0x14004b172  jnz     short loc_14004B1C8
0x14004b174  cmp     r11d, 4
0x14004b178  jz      short loc_14004B1C8
0x14004b17a  mov     r15, [rsp+248h+BugCheckParameter3]
0x14004b182  cmp     r11d, 2
0x14004b186  jnz     short loc_14004B191
0x14004b188  mov     r9d, [r15+84h]
0x14004b18f  jmp     short loc_14004B194
0x14004b191  mov     r9d, esi
0x14004b194  mov     r8d, edi
0x14004b197  mov     rdx, qword ptr [rsp+248h+FileOffset]
0x14004b19f  call    FatIsIoRangeValid
0x14004b1a4  test    al, al
0x14004b1a6  jnz     short loc_14004B1D0
0x14004b1a8  mov     [r13+38h], rsi
0x14004b1ac  mov     r12d, 0C000007Fh
0x14004b1b2  mov     r8d, r12d
0x14004b1b5  mov     rdx, r13; Irp
0x14004b1b8  mov     rcx, r14; Entry
0x14004b1bb  call    FatCompleteRequest_Real
0x14004b1c0  mov     eax, r12d
0x14004b1c3  jmp     loc_14004CD75
0x14004b1c8  mov     r15, [rsp+248h+BugCheckParameter3]
0x14004b1d0  cmp     byte ptr [rsp+248h+var_1B4], sil
0x14004b1d8  jz      loc_14004B263
0x14004b1de  mov     rax, [r14+50h]
0x14004b1e2  test    rax, rax
0x14004b1e5  jnz     short loc_14004B229
0x14004b1e7  cmp     [rsp+248h+var_1C8], esi
0x14004b1ee  jnz     short loc_14004B210
0x14004b1f0  lea     edx, [rax+70h]; NumberOfBytes
0x14004b1f3  mov     ecx, 210h; PoolType
0x14004b1f8  mov     r8d, 58746146h; Tag
0x14004b1fe  call    cs:__imp_ExAllocatePoolWithTag
0x14004b205  nop     dword ptr [rax+rax+00h]
0x14004b20a  mov     [r14+50h], rax
0x14004b20e  jmp     short loc_14004B229
0x14004b210  lea     rax, [rsp+248h+var_A8]
0x14004b218  mov     [r14+50h], rax
0x14004b21c  bts     dword ptr [r10], 8
0x14004b221  lea     rax, [rsp+248h+var_A8]
0x14004b229  xor     edx, edx; Val
0x14004b22b  lea     r8d, [rdx+70h]; Size
0x14004b22f  mov     rcx, rax; void *
0x14004b232  call    memset
0x14004b237  mov     edx, [rsp+248h+var_1C8]
0x14004b23e  test    edx, edx
0x14004b240  jz      short loc_14004B29E
0x14004b242  mov     rcx, [r14+50h]
0x14004b246  add     rcx, 18h; Event
0x14004b24a  xor     r8d, r8d; State
0x14004b24d  xor     edx, edx; Type
0x14004b24f  call    cs:__imp_KeInitializeEvent
0x14004b256  nop     dword ptr [rax+rax+00h]
0x14004b25b  mov     r11d, [rsp+248h+var_1BC]
0x14004b263  mov     r10d, [rsp+248h+var_1F4]
0x14004b268  mov     rcx, [rsp+248h+FileObject]
0x14004b26d  mov     edx, [rsp+248h+var_1C8]
0x14004b274  mov     eax, [r12+0C8h]
0x14004b27c  test    al, 40h
0x14004b27e  jz      short loc_14004B2E8
0x14004b280  mov     [r13+38h], rsi
0x14004b284  mov     ebx, 0C0000189h
0x14004b289  mov     r8d, ebx
0x14004b28c  mov     rdx, r13; Irp
0x14004b28f  mov     rcx, r14; Entry
0x14004b292  call    FatCompleteRequest_Real
0x14004b297  mov     eax, ebx
0x14004b299  jmp     loc_14004CD75
0x14004b29e  mov     r10d, [rsp+248h+var_1F4]
0x14004b2a3  test    r10d, r10d
0x14004b2a6  jz      short loc_14004B2BB
0x14004b2a8  mov     rcx, gs:188h
0x14004b2b1  mov     rax, [r14+50h]
0x14004b2b5  mov     [rax+28h], rcx
0x14004b2b9  jmp     short loc_14004B2CA
0x14004b2bb  mov     rcx, [r14+50h]
0x14004b2bf  mov     rax, rcx
0x14004b2c2  or      rax, 3
0x14004b2c6  mov     [rcx+28h], rax
0x14004b2ca  mov     rax, [r14+50h]
0x14004b2ce  mov     [rax+30h], edi
0x14004b2d1  mov     rax, [r14+50h]
0x14004b2d5  mov     rcx, [rsp+248h+FileObject]
0x14004b2da  mov     [rax+38h], rcx
0x14004b2de  mov     r11d, [rsp+248h+var_1BC]
0x14004b2e6  jmp     short loc_14004B274
0x14004b2e8  cmp     r11d, 5
0x14004b2ec  jnz     loc_14004B698
0x14004b2f2  mov     [rsp+248h+var_1E0], rsi
0x14004b2f7  mov     [rsp+248h+var_160], rsi
0x14004b2ff  mov     dword ptr [rsp+248h+arg_0], esi
0x14004b306  mov     dword ptr [rsp+248h+Size], esi
0x14004b30d  xorps   xmm0, xmm0
0x14004b310  movups  [rsp+248h+var_108], xmm0
0x14004b318  test    edx, edx
0x14004b31a  jnz     short loc_14004B32C
0x14004b31c  mov     rdx, r13; Context2
0x14004b31f  mov     rcx, r14; Context1
0x14004b322  call    FatFsdPostRequest
0x14004b327  jmp     loc_14004CD75
0x14004b32c  call    cs:__imp_IoGetTopLevelIrp
0x14004b333  nop     dword ptr [rax+rax+00h]
0x14004b338  test    al, 2
0x14004b33a  jnz     short loc_14004B341
0x14004b33c  or      dword ptr [r14+44h], 4
0x14004b341  lea     r15, [r12+180h]
0x14004b349  mov     qword ptr [rsp+248h+Retrying], rsi
0x14004b34e  lea     rax, [rsp+248h+arg_0]
0x14004b356  mov     qword ptr [rsp+248h+BytesToWrite], rax
0x14004b35b  lea     r9, [rsp+248h+var_1E0]
0x14004b360  mov     r8d, ebx
0x14004b363  mov     rdx, r15
0x14004b366  mov     rcx, r12
0x14004b369  call    FatLookupMcbEntry
0x14004b36e  test    al, al
0x14004b370  jz      loc_14004AFC7
0x14004b376  mov     r8, [rsp+248h+var_1E0]
0x14004b37b  test    r8, r8
0x14004b37e  jnz     short loc_14004B38D
0x14004b380  cmp     dword ptr [rsp+248h+arg_0], edi
0x14004b387  jnb     loc_14004AFC7
0x14004b38d  test    r8d, r8d
0x14004b390  jnz     short loc_14004B39D
0x14004b392  mov     r8d, dword ptr [rsp+248h+arg_0]
0x14004b39a  add     r8d, ebx
0x14004b39d  mov     [rsp+248h+arg_10], r8d
0x14004b3a5  mov     qword ptr [rsp+248h+Retrying], rsi
0x14004b3aa  lea     rax, [rsp+248h+arg_0]
0x14004b3b2  mov     qword ptr [rsp+248h+BytesToWrite], rax
0x14004b3b7  lea     r9, [rsp+248h+var_1E0]
0x14004b3bc  mov     rdx, r15
0x14004b3bf  mov     rcx, r12
0x14004b3c2  call    FatLookupMcbEntry
0x14004b3c7  test    al, al
0x14004b3c9  jz      loc_14004B677
0x14004b3cf  lea     eax, [rdi+rbx]
0x14004b3d2  mov     [rsp+248h+var_1B0], eax
0x14004b3d9  mov     r15d, dword ptr [rsp+248h+arg_0]
0x14004b3e1  mov     r9, [rsp+248h+var_1E0]
0x14004b3e6  lea     r8d, [r15+r9]
0x14004b3ea  cmp     r8d, eax
0x14004b3ed  jnb     short loc_14004B447
0x14004b3ef  mov     qword ptr [rsp+248h+Retrying], rsi
0x14004b3f4  lea     rax, [rsp+248h+Size]
0x14004b3fc  mov     qword ptr [rsp+248h+BytesToWrite], rax
0x14004b401  lea     r9, [rsp+248h+var_160]
0x14004b409  lea     rdx, [r12+180h]
0x14004b411  mov     rcx, r12
0x14004b414  call    FatLookupMcbEntry
0x14004b419  test    al, al
  ... truncated ...
```
