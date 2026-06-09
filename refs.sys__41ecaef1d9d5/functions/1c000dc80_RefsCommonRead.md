# RefsCommonRead

- ea: `0x1c000dc80`
- end: `0x1c000f3df`
- name: `RefsCommonRead`
- size: `5983`
- prototype: ``
- caller_count: `2`
- callee_count: `26`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1c0008060`
- `0x1c000d400`

## callees

- `0x1c0003334`
- `0x1c00057a8`
- `0x1c000dc80`
- `0x1c000f770`
- `0x1c0013f90`
- `0x1c004d164`
- `0x1c00583d0`
- `0x1c00592b0`
- `0x1c005f020`
- `0x1c005f338`
- `0x1c0062928`
- `0x1c0063db0`
- `0x1c0068168`
- `0x1c009263c`
- `0x1c0097cc8`
- `0x1c009871c`
- `0x1c009ed34`
- `0x1c009eee8`
- `0x1c009efbc`
- `0x1c009f298`
- `0x1c00a7df8`
- `0x1c015ac58`
- `0x1c01636b0`
- `0x1c01639a0`
- `0x1c0178f14`
- `0x1c0199678`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x1c000ebf2`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c000eea6`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c000f378`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c006bbc3`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c000ebf2`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c000eea6`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c000f378`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c006bbc3`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x1c000ecb1`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x1c000ecb1`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c000e3e1`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c000e3e1`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c000e44a`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c000e44a`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x1c000f0d9`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x1c000f0d9`
- `ntoskrnl!FsRtlCheckOplock` at `0x1c000e173`
- `ntoskrnl!FsRtlCheckOplock` at `0x1c000e173`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c000dfb1`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c000e40e`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c000dfb1`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c000e40e`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c0071a07`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c0071a2c`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c0071a07`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c0071a2c`
- `ntoskrnl!ExRaiseStatus` at `0x1c000f0e7`
- `ntoskrnl!ExRaiseStatus` at `0x1c000f0e7`
- `ntoskrnl!DbgPrintEx` at `0x1c007199e`
- `ntoskrnl!DbgPrintEx` at `0x1c007199e`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1c00719c5`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1c00719c5`
- `ntoskrnl!_strnicmp` at `0x1c0071a57`
- `ntoskrnl!_strnicmp` at `0x1c0071a57`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1c0071a3b`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1c0071a3b`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1c000eedb`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1c000eedb`
- `ntoskrnl!FsRtlCheckLockForReadAccess` at `0x1c000ed1e`
- `ntoskrnl!FsRtlCheckLockForReadAccess` at `0x1c000ed1e`
- `ntoskrnl!ExIsFastResourceHeld` at `0x1c000e31b`
- `ntoskrnl!ExIsFastResourceHeld` at `0x1c000e31b`
- `HAL!KeQueryPerformanceCounter` at `0x1c000deaf`
- `HAL!KeQueryPerformanceCounter` at `0x1c000deaf`

## string_xrefs

- `0x1c000e2e6`: `Read.c`
- `0x1c000e5f7`: `Read.c`
- `0x1c000e637`: `Read.c`
- `0x1c000e762`: `Read.c`
- `0x1c000e7dc`: `Read.c`
- `0x1c000e847`: `Read.c`
- `0x1c000e8d2`: `Read.c`
- `0x1c000e9e3`: `Read.c`
- `0x1c000ea56`: `Read.c`
- `0x1c000eb13`: `Read.c`
- `0x1c000eb34`: `Read.c`
- `0x1c000ec78`: `Read.c`
- `0x1c000ed92`: `Read.c`
- `0x1c000ee23`: `Read.c`
- `0x1c000efbe`: `Read.c`
- `0x1c000f0c4`: `Read.c`
- `0x1c000f138`: `Read.c`
- `0x1c0071473`: `Read.c`
- `0x1c007151b`: `Read.c`
- `0x1c00715cc`: `Read.c`
- `0x1c0071686`: `Read.c`
- `0x1c0071735`: `Read.c`
- `0x1c00717b9`: `Read.c`
- `0x1c0071903`: `Read.c`

## pseudocode

```c
__int64 __fastcall RefsCommonRead(__int64 a1, IRP *a2)
{
  ULONG_PTR Information; // r12
  __int64 v4; // r8
  __int64 v5; // r14
  unsigned int v6; // ecx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  PFILE_OBJECT FileObject; // r11
  char *FsContext; // rax
  char *v10; // rsi
  unsigned __int8 *FsContext2; // rbx
  int v12; // eax
  int v13; // r10d
  ULONG Flags; // eax
  int v15; // r10d
  bool v16; // r13
  __int64 QuadPart; // rdx
  __int64 Length; // r11
  PDEVICE_OBJECT *v19; // rdi
  char v20; // cl
  char v21; // al
  int v22; // r8d
  _DWORD **v23; // rcx
  unsigned int v24; // r13d
  PIRP TopLevelIrp; // rax
  unsigned __int64 MasterIrp; // rcx
  __int64 v27; // r8
  _BOOL8 v28; // rcx
  char v29; // r15
  _QWORD *v30; // rcx
  unsigned __int8 v31; // al
  int v32; // edx
  void *v33; // r13
  const char *v34; // r15
  int v35; // eax
  NTSTATUS v36; // ebx
  int Status; // r9d
  int v38; // r15d
  char v39; // di
  volatile signed __int32 *v40; // r13
  __int64 v41; // rdx
  int v42; // edi
  __int64 HighestPendingFileSize; // rbx
  __int64 v44; // r11
  unsigned int v45; // ebx
  int v46; // edx
  _DWORD **v47; // r14
  IRP *v48; // r13
  ULONG_PTR v49; // rbx
  __int64 v50; // r8
  __int64 v51; // rcx
  int v52; // r15d
  __int64 v53; // rcx
  NTSTATUS v54; // eax
  unsigned __int8 v55; // al
  __int64 v56; // rax
  int v57; // ecx
  int v58; // r9d
  NTSTATUS v59; // eax
  struct _ERESOURCE *v60; // rcx
  __int64 v61; // rax
  int v62; // edx
  char v63; // al
  struct _ERESOURCE *v64; // rcx
  int v65; // eax
  __int64 v66; // rdx
  NTSTATUS v67; // ebx
  NTSTATUS v68; // eax
  struct _IO_STACK_LOCATION *v69; // r8
  struct _KTHREAD *v70; // rdi
  unsigned int v71; // ebx
  unsigned __int32 v72; // eax
  __int64 v73; // rax
  __int64 v74; // rax
  _DWORD *v76; // rcx
  int v77; // eax
  struct _ERESOURCE *v78; // rcx
  __int64 v79; // rax
  NTSTATUS v80; // eax
  PEPROCESS CurrentProcess; // rax
  const char *ProcessImageFileName; // rax
  signed __int32 v83[8]; // [rsp+48h] [rbp-1A8h] BYREF
  POPLOCK_FS_PREPOST_IRP PostIrpRoutine; // [rsp+68h] [rbp-188h]
  int v85[2]; // [rsp+70h] [rbp-180h]
  unsigned int v86; // [rsp+78h] [rbp-178h]
  __int64 v87; // [rsp+80h] [rbp-170h]
  unsigned int v88; // [rsp+88h] [rbp-168h]
  int v89; // [rsp+98h] [rbp-158h] BYREF
  NTSTATUS Exception; // [rsp+9Ch] [rbp-154h]
  int v91[2]; // [rsp+A0h] [rbp-150h]
  int v92; // [rsp+A8h] [rbp-148h]
  int v93; // [rsp+ACh] [rbp-144h]
  int v94; // [rsp+B0h] [rbp-140h]
  int v95[2]; // [rsp+B8h] [rbp-138h]
  unsigned int Size; // [rsp+C0h] [rbp-130h]
  unsigned int Size_4; // [rsp+C4h] [rbp-12Ch]
  int v98; // [rsp+C8h] [rbp-128h]
  int v99; // [rsp+CCh] [rbp-124h]
  int v100; // [rsp+D0h] [rbp-120h]
  int *v101; // [rsp+D8h] [rbp-118h]
  PIRP v102; // [rsp+E0h] [rbp-110h]
  unsigned __int8 *v103; // [rsp+E8h] [rbp-108h]
  __int64 v104; // [rsp+F0h] [rbp-100h]
  __int64 v105; // [rsp+F8h] [rbp-F8h]
  struct _IO_STACK_LOCATION *v106; // [rsp+100h] [rbp-F0h]
  __int64 v107; // [rsp+108h] [rbp-E8h]
  PFILE_OBJECT v108; // [rsp+110h] [rbp-E0h]
  ULONG_PTR v109; // [rsp+118h] [rbp-D8h]
  _DWORD *v110; // [rsp+120h] [rbp-D0h]
  volatile signed __int32 *v111; // [rsp+128h] [rbp-C8h]
  __int64 v112; // [rsp+130h] [rbp-C0h]
  __int64 v113; // [rsp+140h] [rbp-B0h]
  _OWORD v114[4]; // [rsp+148h] [rbp-A8h] BYREF
  __int128 v115; // [rsp+188h] [rbp-68h]
  __int64 v116; // [rsp+198h] [rbp-58h]
  __int64 v117; // [rsp+1A8h] [rbp-48h]
  struct _KTHREAD *CurrentThread; // [rsp+1B0h] [rbp-40h]
  _DWORD **Context; // [rsp+1F8h] [rbp+8h]
  PIRP Irp; // [rsp+200h] [rbp+10h]
  bool v121; // [rsp+208h] [rbp+18h]
  int v122; // [rsp+208h] [rbp+18h]
  int v123; // [rsp+208h] [rbp+18h]
  bool v124; // [rsp+210h] [rbp+20h]

  Irp = a2;
  Context = (_DWORD **)a1;
  Information = 0;
  v4 = 0;
  v104 = 0;
  v5 = 0;
  v105 = 0;
  Size_4 = 0;
  v100 = 0;
  memset(v114, 0, sizeof(v114));
  v115 = 0;
  v116 = 0;
  v89 = 0;
  v6 = *(_DWORD *)(a1 + 8) & 0xFFFFFFF7;
  *(_DWORD *)(a1 + 8) = v6;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v106 = CurrentStackLocation;
  FileObject = CurrentStackLocation->FileObject;
  v108 = FileObject;
  FsContext = (char *)FileObject->FsContext;
  v10 = FsContext;
  *(_QWORD *)v95 = FsContext;
  v111 = (volatile signed __int32 *)FsContext;
  if ( FsContext )
  {
    v4 = *((_QWORD *)FsContext + 16);
    v104 = v4;
    FsContext2 = (unsigned __int8 *)FileObject->FsContext2;
    v103 = FsContext2;
    v5 = *((_QWORD *)FsContext + 15);
    v105 = v5;
    v12 = *(_DWORD *)(v4 + 4);
    if ( (v12 & 1) == 0 && (!FsContext2 || FsContext2[80] != 4 || (v12 & 2) == 0) )
    {
      RefsRaiseStatusInternal(a1, 3221226094LL);
      __debugbreak();
    }
    if ( FsContext2 )
      v13 = FsContext2[80];
    else
      v13 = 5;
  }
  else
  {
    FsContext2 = 0;
    v103 = 0;
    v13 = 1;
  }
  v98 = v13;
  v101 = (int *)(v10 + 304);
  if ( (*((_DWORD *)v10 + 76) & 0x1000000) != 0 )
  {
    v71 = -1073741816;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741816);
    RefsExtendedCompleteRequestInternal(Context, Irp, 3221225480LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_f4fe8069457b33cee1a723bb8f3f2247_Traceguids, 3221225480LL);
    }
    if ( !RefsStatusDebugEnabled )
      return v71;
LABEL_330:
    RefsStatusDebug(v71);
    return v71;
  }
  if ( (*(_DWORD *)(v4 + 4) & 1) == 0 && v13 != 4 )
  {
    v71 = -1073741202;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741202);
    RefsExtendedCompleteRequestInternal(Context, Irp, 3221226094LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_f4fe8069457b33cee1a723bb8f3f2247_Traceguids, 3221226094LL);
    }
    if ( !RefsStatusDebugEnabled )
      return v71;
    goto LABEL_330;
  }
  v92 = v6 & 1;
  Flags = a2->Flags;
  v15 = Flags & 2;
  v93 = v15;
  v16 = (Flags & 1) != 0;
  v121 = v16;
  v124 = (FileObject->Flags & 2) != 0;
  if ( FsContext2 )
  {
    if ( (*((_DWORD *)FsContext2 + 1) & 0x2000) != 0 && (Flags & 2) == 0 )
    {
      v71 = -1073741811;
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741811);
      RefsExtendedCompleteRequestInternal(Context, Irp, 3221225485LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_f4fe8069457b33cee1a723bb8f3f2247_Traceguids, 3221225485LL);
      }
      if ( !RefsStatusDebugEnabled )
        return v71;
      goto LABEL_330;
    }
    if ( (FsContext2[88] & 8) != 0 )
      v100 = 16;
  }
  QuadPart = CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart;
  *(_QWORD *)v91 = QuadPart;
  v113 = QuadPart;
  Length = CurrentStackLocation->Parameters.Read.Length;
  LODWORD(v102) = Length;
  Size = Length;
  if ( (Flags & 1) != 0
    && ((*(_DWORD *)(*(_QWORD *)(v5 + 88) + 276LL) - 1) & ((unsigned int)Length | (unsigned int)QuadPart)) != 0 )
  {
    LOBYTE(v19) = 32;
    LOBYTE(v89) = 32;
  }
  else
  {
    LOBYTE(v19) = v89;
  }
  if ( FsContext2 && FsContext2[90] )
    *(_DWORD *)(a1 + 12) |= 0x80u;
  v109 = Length;
  if ( 0x7FFFFFFFFFFFFFFFLL - QuadPart < Length )
  {
    v71 = -1073741811;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811);
    RefsExtendedCompleteRequestInternal(Context, Irp, 3221225485LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_f4fe8069457b33cee1a723bb8f3f2247_Traceguids, 3221225485LL);
    }
    if ( !RefsStatusDebugEnabled )
      return v71;
    goto LABEL_330;
  }
  v107 = Length + QuadPart;
  v117 = Length + QuadPart;
  if ( (_DWORD)Length )
  {
    if ( *(_QWORD *)(v4 + 3944) )
    {
      *(LARGE_INTEGER *)(*(_QWORD *)(a1 + 144) + 288LL) = KeQueryPerformanceCounter(0);
      v94 = 0;
      v15 = v93;
      if ( v93 || v16 )
        v20 = 0;
      else
        v20 = 2;
      v21 = 16;
      if ( v93 )
        v21 = 20;
      v22 = v92;
      HIBYTE(v94) = v92 | v20 | v21;
      **(_DWORD **)(a1 + 144) |= v94;
      LODWORD(Length) = (_DWORD)v102;
      QuadPart = *(_QWORD *)v91;
    }
    else
    {
      v22 = v92;
    }
    if ( (v108->Flags & 0x20000000) == 0 )
    {
      v110 = v10 + 136;
      if ( (*((_DWORD *)v10 + 34) & 0x20) == 0 )
      {
        LOBYTE(v22) = 1;
        v92 = v22;
        *(_DWORD *)(a1 + 8) |= 1u;
        *(_BYTE *)(*(_QWORD *)(a1 + 144) + 3LL) |= 1u;
      }
      v23 = Context;
      if ( (*(_DWORD *)(a1 + 12) & 0x80u) != 0 )
        *Context[18] |= 0x80u;
      if ( v98 != 4 )
      {
        if ( v15 )
        {
          v76 = (_DWORD *)(*(_QWORD *)(v104 + 680)
                         + ((unsigned __int64)(KeGetCurrentProcessorNumber() % (unsigned int)RefsNumberProcessors) << 6));
          v5 = v105;
          v10 = *(char **)v95;
          if ( (*(_DWORD *)(v105 + 4) & 0x100) == 0
            && ((v77 = *(_DWORD *)(*(_QWORD *)v95 + 200LL), v77 == 128) || v77 == 176) )
          {
            ++v76[2];
            v24 = Size;
            v76[3] += Size;
            FsContext2 = v103;
            LOBYTE(v19) = v89;
          }
          else
          {
            ++v76[8];
            v24 = Size;
            v76[9] += Size;
            FsContext2 = v103;
            LOBYTE(v19) = v89;
          }
        }
        else
        {
          v24 = (unsigned int)v102;
        }
        if ( v15 || !v121 )
          *((_DWORD *)v10 + 42) = 0;
        *((_QWORD *)&v115 + 1) = 0x100000000LL;
        v116 = 0;
        TopLevelIrp = IoGetTopLevelIrp();
        v102 = TopLevelIrp;
        if ( HIBYTE(TopLevelIrp->Type) )
        {
          MasterIrp = (unsigned __int64)TopLevelIrp->AssociatedIrp.MasterIrp;
          if ( (*(_DWORD *)(*(_QWORD *)(MasterIrp + 32) + 4LL) & 0x200) == 0 )
            LOBYTE(TopLevelIrp->Type) = 0;
        }
        if ( v93 )
        {
          if ( !*((_QWORD *)v10 + 2)
            || (unsigned __int8)ExIsFastResourceHeld(*(_QWORD *)(*((_QWORD *)v10 + 15) + 104LL)) )
          {
            goto LABEL_57;
          }
          Size_4 = v24;
          v33 = Context;
          v49 = v109;
          RefsAcquireRangeLock((_DWORD)Context, *((_QWORD *)v10 + 30), v91[0], v109, 0, (__int64)(Context[18] + 8));
          *((_DWORD *)Context + 1) |= 0x40u;
          LOBYTE(v50) = 1;
          RefsAcquireResourceShared(v51, v10, v50);
          LOBYTE(v19) = (unsigned __int8)v19 | 0x14;
          LOBYTE(v89) = (_BYTE)v19;
          if ( (*v101 & 4) != 0 )
          {
LABEL_174:
            Irp->IoStatus.Information = v49;
            MasterIrp = (unsigned __int64)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_D(
                WPP_GLOBAL_Control->AttachedDevice,
                26,
                WPP_f4fe8069457b33cee1a723bb8f3f2247_Traceguids,
                3221225489LL);
            }
            Status = -1073741807;
            if ( RefsStatusDebugEnabled )
            {
              RefsStatusDebug(-1073741807);
              Status = -1073741807;
            }
            goto LABEL_180;
          }
          if ( *(_WORD *)v10 == 2053 && *((_QWORD *)v10 + 45) && *((_WORD *)v10 + 129) )
            *(_DWORD *)(a1 + 12) |= 0x100u;
LABEL_58:
          LOWORD(v34) = 2050;
          v35 = *v101;
          if ( (*v101 & 0x10000) != 0 )
          {
            v36 = -1073741202;
          }
          else if ( (v35 & 0x1000000) != 0 )
          {
            v36 = -1073741816;
          }
          else
          {
            v36 = 0;
          }
          Exception = v36;
          if ( (v35 & 0x40) != 0 )
          {
            v19 = &WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
            {
              v36 = -1073741533;
            }
            else
            {
              v36 = -1073741533;
              WPP_SF_D(
                WPP_GLOBAL_Control->AttachedDevice,
                27,
                WPP_f4fe8069457b33cee1a723bb8f3f2247_Traceguids,
                3221225763LL);
            }
            v34 = "Read.c";
            if ( RefsStatusDebugEnabled )
              RefsStatusDebug(-1073741533);
            Exception = -1073741533;
          }
          else
          {
            if ( v36 >= 0 )
            {
              if ( (*v110 & 0x20) != 0 )
                goto LABEL_64;
              goto LABEL_199;
            }
            v34 = "Read.c";
            v19 = &WPP_GLOBAL_Control;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_D(
              WPP_GLOBAL_Control->AttachedDevice,
              28,
              WPP_f4fe8069457b33cee1a723bb8f3f2247_Traceguids,
              (unsigned int)v36);
          }
          if ( RefsStatusDebugEnabled )
            RefsStatusDebug(Exception);
          RefsRaiseStatusInternal(Context, (unsigned int)Exception);
LABEL_199:
          if ( ((unsigned __int8)v19 & 0x10) == 0 )
          {
            LOBYTE(v27) = 1;
            RefsAcquireResourceShared(MasterIrp, v10, v27);
            LOBYTE(v19) = (unsigned __int8)v19 | 0x18;
            LOBYTE(v89) = (_BYTE)v19;
          }
          RefsUpdateScbFromAttribute(v33, v10, 0);
          if ( ((unsigned __int8)v19 & 8) != 0 )
          {
            if ( (_WORD)v34 == *(_WORD *)v10 )
              v60 = (struct _ERESOURCE *)(*((_QWORD *)v10 + 12) + 64LL);
            else
              v60 = (struct _ERESOURCE *)*((_QWORD *)v10 + 1);
            ExReleaseResourceLite(v60);
            LOBYTE(v19) = (unsigned __int8)v19 & 0xE7;
            LOBYTE(v89) = (_BYTE)v19;
          }
LABEL_64:
          if ( v98 == 2 )
          {
            Status = FsRtlCheckOplock((POPLOCK)v10 + 11, Irp, v33, RefsOplockComplete, RefsPrePostIrp);
            Exception = Status;
            if ( Status )
            {
LABEL_207:
              v48 = 0;
              Irp = 0;
              v47 = 0;
              Context = 0;
              goto LABEL_283;
            }
            if ( !v10[5] )
            {
              if ( (*(_DWORD *)(*((_QWORD *)v10 + 16) + 4LL) & 0x4000005) == 1
                && *(_WORD *)v10 == 2053
                && (*v101 & 0x40) == 0
                && FsRtlOplockIsFastIoPossible((POPLOCK)v10 + 11) )
              {
                if ( *((_DWORD *)v10 + 62)
                  || (v61 = *((_QWORD *)v10 + 42)) != 0 && *(_BYTE *)(v61 + 16)
                  || (v62 = *(_DWORD *)(*((_QWORD *)v10 + 16) + 4LL), (v62 & 0x2000000) != 0)
                  || (LOBYTE(MasterIrp) = (*(_BYTE *)(*((_QWORD *)v10 + 15) + 4LL) & 0x20) == 0,
                      ((unsigned __int8)MasterIrp & ((v62 & 0x80000) == 0)) == 0) )
                {
                  v63 = 2;
                }
                else
                {
                  v63 = 1;
                }
              }
              else
              {
                v63 = 0;
              }
              v10[5] = v63;
            }
            v38 = v93;
            if ( !v93 )
            {
              MasterIrp = *((_QWORD *)v10 + 42);
              if ( MasterIrp )
              {
                if ( !FsRtlCheckLockForReadAccess((PFILE_LOCK)MasterIrp, Irp) )
                {
                  MasterIrp = (unsigned __int64)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
                    || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
                  {
                    Status = -1073741740;
                  }
                  else
                  {
                    WPP_SF_D(
                      WPP_GLOBAL_Control->AttachedDevice,
                      29,
                      WPP_f4fe8069457b33cee1a723bb8f3f2247_Traceguids,
                      3221225556LL);
                    Status = -1073741740;
                  }
                  if ( RefsStatusDebugEnabled )
                  {
                    RefsStatusDebug(-1073741740);
                    Status = -1073741740;
                  }
LABEL_180:
                  Exception = Status;
                  v48 = Irp;
                  v47 = Context;
                  v10 = *(char **)v95;
LABEL_282:
                  LOBYTE(v19) = v89;
                  goto LABEL_283;
                }
              }
            }
          }
          else
          {
            v38 = v93;
          }
          v94 = *((_DWORD *)v10 + 39);
          _InterlockedOr(v83, 0);
          v39 = v94;
          v40 = v111;
          while ( 2 )
          {
            v41 = *(_QWORD *)v95;
            while ( 1 )
            {
              v42 = v39 & 1;
              if ( v42 )
              {
                ExAcquireFastMutex(*(PFAST_MUTEX *)(v41 + 48));
                _InterlockedIncrement((volatile signed __int32 *)v10 + 39);
                v41 = *(_QWORD *)v95;
              }
              HighestPendingFileSize = *(_QWORD *)(v41 + 32);
              v112 = HighestPendingFileSize;
              if ( !v38 )
                break;
              if ( v42 )
              {
                HighestPendingFileSize = RefsGetHighestPendingFileSize(MasterIrp, v41);
                v112 = HighestPendingFileSize;
                if ( IoGetTopLevelIrp()->AssociatedIrp.MasterIrp == (struct _IRP *)2 )
                  *((_DWORD *)Context + 2) |= 0x800u;
                break;
              }
              v39 = 1;
              v94 = 1;
            }
            if ( v42 )
            {
              _InterlockedIncrement(v40 + 39);
              v10 = *(char **)v95;
              ExReleaseFastMutex(*(PFAST_MUTEX *)(*(_QWORD *)v95 + 48LL));
            }
            else
            {
              _InterlockedOr(v83, 0);
              if ( v94 != *((_DWORD *)v40 + 39) )
              {
                v39 = 1;
                v94 = 1;
                continue;
              }
              v10 = *(char **)v95;
            }
            break;
          }
          v44 = *(_QWORD *)v91;
          if ( *(__int64 *)v91 >= HighestPendingFileSize )
          {
            MasterIrp = (unsigned __int64)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
            {
              Status = -1073741807;
              v123 = -1073741807;
            }
            else
            {
              v123 = -1073741807;
              WPP_SF_D(
                WPP_GLOBAL_Control->AttachedDevice,
                30,
                WPP_f4fe8069457b33cee1a723bb8f3f2247_Traceguids,
                3221225489LL);
              Status = -1073741807;
              v44 = *(_QWORD *)v91;
            }
            if ( !RefsStatusDebugEnabled )
              goto LABEL_238;
LABEL_237:
            RefsStatusDebug(Status);
            Status = v123;
            v44 = *(_QWORD *)v91;
LABEL_238:
            Exception = Status;
            v48 = Irp;
            v47 = Context;
            v10 = *(char **)v95;
            LOBYTE(v19) = v89;
            goto LABEL_114;
          }
          if ( v107 > HighestPendingFileSize )
          {
            v45 = HighestPendingFileSize - v91[0];
            Size = v45;
          }
          else
          {
            v45 = Size;
          }
          v46 = *((_DWORD *)v10 + 34);
          LOBYTE(MasterIrp) = (*((_DWORD *)v10 + 76) & 0x4000) == 0;
          if ( ((unsigned __int8)MasterIrp & ((v46 & 8) == 0)) != 0 || !v121 )
          {
            LOBYTE(v19) = v89;
          }
          else
          {
            LOBYTE(v19) = v89;
            if ( (v89 & 0x10) == 0 )
            {
              LOBYTE(v27) = 1;
              RefsAcquireResourceShared(MasterIrp, v10, v27);
              LOBYTE(v19) = (unsigned __int8)v19 | 0x18;
              LOBYTE(v89) = (_BYTE)v19;
              v46 = *((_DWORD *)v40 + 34);
              v44 = *(_QWORD *)v91;
            }
            if ( (v46 & 8) != 0 )
            {
              v47 = Context;
              *((_QWORD *)Context[18] + 36) = 16;
              LODWORD(PostIrpRoutine) = v45;
              v48 = Irp;
              RefsNonCachedResidentRead((int)Context, (int)Irp, (int)v10, v44, (size_t)PostIrpRoutine);
              Irp->IoStatus.Information = v45;
              Status = 0;
              Exception = 0;
LABEL_283:
              v44 = *(_QWORD *)v91;
LABEL_114:
              if ( v48 )
              {
                if ( !v93 )
                {
                  if ( v124 )
                  {
                    if ( (Status & 0xC0000000) != 0xC0000000 )
                      Information = v48->IoStatus.Information;
                    v69 = v106;
                    v106->FileObject->CurrentByteOffset.QuadPart = Information + v44;
                  }
                  else
                  {
                    v69 = v106;
                  }
                  if ( Status >= 0 )
                    v69->FileObject->Flags |= 0x80000u;
                }
                RefsCleanupTransaction(v47, (unsigned int)Status, 0);
              }
              goto LABEL_291;
            }
            if ( ((unsigned __int8)v19 & 8) != 0 )
            {
              if ( *(_WORD *)v10 == 2050 )
                v64 = (struct _ERESOURCE *)(*((_QWORD *)v10 + 12) + 64LL);
              else
                v64 = (struct _ERESOURCE *)*((_QWORD *)v10 + 1);
              ExReleaseResourceLite(v64);
              LOBYTE(v19) = (unsigned __int8)v19 & 0xE7;
              LOBYTE(v89) = (_BYTE)v19;
              v44 = *(_QWORD *)v91;
            }
          }
          v48 = Irp;
          if ( !v121 )
          {
            v47 = Context;
            Status = RefsCachedRead(Context, v108, Irp, v10, v114, v44, v45, &v89);
            Exception = Status;
            if ( Status == 259 )
            {
              v48 = 0;
              Irp = 0;
              v47 = 0;
              Context = 0;
            }
            goto LABEL_282;
          }
          v52 = v45;
          if ( v45 )
          {
            if ( (*(_DWORD *)(v104 + 3824) & 1) != 0 )
            {
              if ( IoGetIoPriorityHint(Irp) > IoPriorityLow )
              {
                if ( ((v65 = *((_DWORD *)v10 + 50), v65 == 128) || v65 == 176) && !*((_WORD *)v10 + 104) || v65 == 160 )
                  RefsHeatLogIo(Irp, v105);
              }
              v44 = *(_QWORD *)v91;
            }
            if ( ((unsigned __int8)v19 & 0x20) == 0
              || *(_WORD *)v10 == 2053 && *((_QWORD *)v10 + 45) && *((_WORD *)v10 + 129) )
            {
              v47 = Context;
              if ( ((unsigned __int8)v19 & 0x20) == 0 )
                v52 = -Context[8][69] & (v45 + Context[8][69] - 1);
              if ( !(_BYTE)v92 )
              {
                if ( v93 )
                {
                  v88 = v45;
                  LOBYTE(v87) = 0;
                  if ( ((unsigned __int8)v19 & 0x10) != 0 )
                  {
                    v86 = Size_4;
                    *(_QWORD *)v85 = v44;
                    PostIrpRoutine = (POPLOCK_FS_PREPOST_IRP)*((_QWORD *)v10 + 30);
                    v66 = *((_QWORD *)v10 + 1);
                  }
                  else
                  {
                    v86 = 0;
                    *(_QWORD *)v85 = v44;
                    PostIrpRoutine = 0;
                    LODWORD(v66) = 0;
                  }
                  RefsSetIoContextAsync(
                    (_DWORD)Context,
                    v66,
                    0,
                    0,
                    (__int64)PostIrpRoutine,
                    *(__int64 *)v85,
                    v86,
                    v87,
                    v88);
                }
                else
                {
                  v53 = *((_QWORD *)v10 + 2);
                  *((_QWORD *)Context[18] + 6) = 0;
                  *((_QWORD *)Context[18] + 8) = v53;
                  *((_QWORD *)Context[18] + 9) = v114;
                  CurrentThread = KeGetCurrentThread();
                  *((_QWORD *)Context[18] + 7) = CurrentThread;
                  *((_QWORD *)Context[18] + 21) = 0;
                  *((_QWORD *)Context[18] + 22) = v44;
                  Context[18][46] = 0;
                  *((_BYTE *)Context[18] + 188) = 0;
                  v45 = Size;
                  Context[18][48] = Size;
                  *((_QWORD *)Context[18] + 25) = 0;
                  *Context[18] |= 4u;
                  v48 = Irp;
                  v47 = Context;
                  v10 = *(char **)v95;
                  LOBYTE(v19) = v89;
                }
              }
              v54 = RefsNonCachedIo((int)v47, v48, v52, v100);
              Exception = v54;
              if ( v54 == 259 )
              {
                LOBYTE(v19) = (unsigned __int8)v19 & 0xEA;
                LOBYTE(v89) = (_BYTE)v19;
                v47[18] = 0;
                *((_DWORD *)v47 + 2) &= 0xFFFF7FEF;
                Irp = 0;
LABEL_291:
                if ( ((unsigned __int8)v19 & 4) != 0 )
                {
                  *((_DWORD *)v47 + 1) &= ~0x40u;
                  RefsReleaseRangeLock(*((_QWORD *)v10 + 30), v91[0], Size_4, 0, (__int64)(v47[18] + 8));
                }
                if ( ((unsigned __int8)v19 & 1) != 0 )
                  RefsReleasePagingFastResource(MasterIrp, v10, v114);
                if ( ((unsigned __int8)v19 & 0x10) != 0 )
                {
                  if ( *(_WORD *)v10 == 2050 )
                    v78 = (struct _ERESOURCE *)(*((_QWORD *)v10 + 12) + 64LL);
                  else
                    v78 = (struct _ERESOURCE *)*((_QWORD *)v10 + 1);
                  ExReleaseResourceLite(v78);
                }
                if ( DWORD2(v115) )
                  __fastfail(5u);
                *((_QWORD *)&v115 + 1) &= 0xFFFFFFFE00000000uLL;
                if ( RefsStatusDebugEnabled )
                {
                  v70 = KeGetCurrentThread();
                  if ( RefsStatusDisplayStatus && RefsStatusDisplayStatus == Exception )
                    DbgPrintEx(0x95u, 0, "th%p %x %s:%i\n", v70, Exception, "Read.c", 1850);
                  if ( (RefsStatusBreakOnStatus && RefsStatusBreakOnStatus == Exception
                     || RefsStatusBreakOnWin32Error
                     && RefsStatusBreakOnWin32Error == RtlNtStatusToDosErrorNoTeb(Exception))
                    && (!RefsStatusBreakForThread || (struct _KTHREAD *)RefsStatusBreakForThread == v70)
                    && (!RefsStatusBreakForProcess || (PEPROCESS)RefsStatusBreakForProcess == IoGetCurrentProcess()) )
                  {
                    if ( !RefsStatusBreakForImage
                      || (CurrentProcess = IoGetCurrentProcess(),
                          ProcessImageFileName = (const char *)PsGetProcessImageFileName(CurrentProcess),
                          !_strnicmp(&RefsStatusBreakForImage, ProcessImageFileName, 0xFu)) )
                    {
                      __int2c();
                    }
                  }
                  v71 = Exception;
                  if ( Exception )
                  {
                    v72 = _InterlockedIncrement(&RefsStatusNextQueueEntry);
                    if ( RefsStatusDebugQueueMax == 1024 )
                      v73 = v72 & 0x3FF;
                    else
                      v73 = v72 % RefsStatusDebugQueueMax;
                    v74 = 4 * v73;
                    RefsStatusQueue[v74] = (__int64)v70;
                    v71 = Exception;
                    LODWORD(RefsStatusQueue[v74 + 1]) = Exception;
                    RefsStatusQueue[v74 + 2] = (__int64)"Read.c";
                    LODWORD(RefsStatusQueue[v74 + 3]) = 1850;
                  }
                }
                else
                {
                  v71 = Exception;
                }
LABEL_305:
                RefsExtendedCompleteRequestInternal(Context, Irp, v71);
                return v71;
              }
              if ( v54 >= 0 )
                *((_BYTE *)v47[18] + 3) |= 1u;
            }
            else
            {
              v47 = Context;
              if ( (*((_DWORD *)Context + 3) & 0x80u) != 0 )
              {
                MasterIrp = (unsigned __int64)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
                {
                  Status = -1073741811;
                  v123 = -1073741811;
                }
                else
                {
                  v123 = -1073741811;
                  WPP_SF_D(
                    WPP_GLOBAL_Control->AttachedDevice,
                    31,
                    WPP_f4fe8069457b33cee1a723bb8f3f2247_Traceguids,
                    3221225485LL);
                  Status = -1073741811;
                  v44 = *(_QWORD *)v91;
                }
                if ( !RefsStatusDebugEnabled )
                  goto LABEL_238;
                goto LABEL_237;
              }
              if ( !(_BYTE)v92 )
              {
                if ( ((unsigned __int8)v19 & 4) != 0 )
                {
                  *((_DWORD *)Context + 1) &= ~0x40u;
                  LOBYTE(v19) = (unsigned __int8)v19 & 0xFB;
                  LOBYTE(v89) = (_BYTE)v19;
                  RefsReleaseRangeLock(*((_QWORD *)v10 + 30), v44, Size_4, 0, (__int64)(Context[18] + 8));
                }
                Status = RefsPostRequest(Context);
                Exception = Status;
                goto LABEL_207;
              }
              RefsNonCachedNonAlignedIo((int)Context, Irp, v45);
            }
            v44 = *(_QWORD *)v91;
          }
          else
          {
            v47 = Context;
          }
          Status = v48->IoStatus.Status;
          v122 = Status;
          Exception = Status;
          if ( Status < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_DD(
                WPP_GLOBAL_Control->AttachedDevice,
                32,
                WPP_f4fe8069457b33cee1a723bb8f3f2247_Traceguids,
                3221225705LL,
                Status);
              Status = v122;
            }
            *((_DWORD *)v47 + 4) = Status;
            v67 = Exception;
            if ( RefsStatusDebugEnabled )
              RefsStatusDebug(Exception);
            v68 = FsRtlNormalizeNtstatus(v67, -1073741591);
            ExRaiseStatus(v68);
          }
          v48->IoStatus.Information = v45;
          goto LABEL_114;
        }
        v99 = 0;
        v28 = v121;
        if ( v121 )
        {
          v29 = 0;
        }
        else
        {
          v29 = 1;
          if ( !*(_QWORD *)(*((_QWORD *)v10 + 30) + 16LL) )
            goto LABEL_128;
        }
        if ( !v121 || !*(_QWORD *)(*((_QWORD *)v10 + 30) + 8LL) || *((_DWORD *)v10 + 80) )
        {
          v30 = 0;
          if ( *(_WORD *)v10 == 2050 )
          {
            v30 = v10;
          }
          else if ( *((_QWORD *)v10 + 2) )
          {
            v30 = (_QWORD *)*((_QWORD *)v10 + 15);
          }
          v31 = MsAcquireFastResourceShared(v30[13], v114, (unsigned __int8)v92);
          MasterIrp = v31;
          v99 = v31;
          if ( !v31 )
            goto LABEL_129;
          if ( !v29 || *(_QWORD *)(*((_QWORD *)v10 + 30) + 16LL) )
          {
            v32 = v121;
            if ( !v121 || !*(_QWORD *)(*((_QWORD *)v10 + 30) + 8LL) || *((_DWORD *)v10 + 80) )
            {
LABEL_49:
              if ( (_DWORD)MasterIrp )
              {
                LOBYTE(v19) = (unsigned __int8)v19 | 1;
                LOBYTE(v89) = (_BYTE)v19;
                if ( (*v101 & 0x1000000) == 0 )
                {
                  if ( (*((_DWORD *)FsContext2 + 1) & 0x8000) == 0 )
                  {
                    if ( (*(_DWORD *)(v5 + 4) & 0x1000000) != 0 )
                      goto LABEL_153;
                    if ( *(_QWORD *)(v5 + 8) )
                    {
LABEL_54:
                      if ( *(_QWORD *)(v5 + 240) )
                      {
                        if ( !(_BYTE)v32 || !*(_QWORD *)(*((_QWORD *)v10 + 30) + 8LL) )
                          goto LABEL_57;
LABEL_160:
                        if ( *((_DWORD *)v10 + 80) )
                        {
LABEL_57:
                          v33 = Context;
                          goto LABEL_58;
                        }
                        if ( *(_WORD *)v10 == 2053 && *((_QWORD *)v10 + 45) && *((_WORD *)v10 + 129) )
                        {
                          v57 = -(1 << *(_DWORD *)(*((_QWORD *)v10 + 16) + 464LL));
                          v32 = v91[0];
                          v58 = v91[0] & v57;
                          v24 = (v57 & (v91[0] + (1 << *(_DWORD *)(*((_QWORD *)v10 + 16) + 464LL)) + v24 - 1))
                              - (v91[0] & v57);
                        }
                        else
                        {
                          v58 = v91[0];
                        }
                        LOBYTE(v86) = *((_DWORD *)v10 + 41) == 0;
                        PostIrpRoutine = (POPLOCK_FS_PREPOST_IRP)v24;
                        v33 = Context;
                        v59 = RefsCacheCoherencyFlush(
                                (_DWORD)Context,
                                v32,
                                (_DWORD)v10,
                                v58,
                                (__int64)PostIrpRoutine,
                                0,
                                v86);
                        Exception = v59;
                        if ( v59 < 0 )
                        {
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                          {
                            WPP_SF_D(
                              WPP_GLOBAL_Control->AttachedDevice,
                              25,
                              WPP_f4fe8069457b33cee1a723bb8f3f2247_Traceguids,
                              (unsigned int)v59);
                          }
                          v49 = (unsigned int)Exception;
                          if ( RefsStatusDebugEnabled )
                            RefsStatusDebug(Exception);
                          RefsRaiseStatusInternal(Context, (unsigned int)Exception);
                          goto LABEL_174;
                        }
                        goto LABEL_58;
                      }
LABEL_153:
                      v19 = &WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                      {
                        WPP_SF_D(
                          WPP_GLOBAL_Control->AttachedDevice,
                          24,
                          WPP_f4fe8069457b33cee1a723bb8f3f2247_Traceguids,
                          3221225768LL);
                      }
                      if ( RefsStatusDebugEnabled )
                        RefsStatusDebug(-1073741528);
                      RefsRaiseStatusInternal(Context, 3221225768LL);
                      goto LABEL_160;
                    }
LABEL_151:
                    v56 = *(_QWORD *)(v5 + 248);
                    if ( !v56 || !*(_QWORD *)(v56 + 384) )
                      goto LABEL_153;
                    goto LABEL_54;
                  }
LABEL_144:
                  v19 = &WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                  {
                    WPP_SF_D(
                      WPP_GLOBAL_Control->AttachedDevice,
                      23,
                      WPP_f4fe8069457b33cee1a723bb8f3f2247_Traceguids,
                      3221225768LL);
                  }
                  if ( RefsStatusDebugEnabled )
                    RefsStatusDebug(-1073741528);
                  RefsRaiseStatusInternal(Context, 3221225768LL);
                  goto LABEL_151;
                }
              }
              else
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_D(
                    WPP_GLOBAL_Control->AttachedDevice,
                    21,
                    WPP_f4fe8069457b33cee1a723bb8f3f2247_Traceguids,
                    3221225688LL);
                }
                if ( RefsStatusDebugEnabled )
                  RefsStatusDebug(-1073741608);
                RefsRaiseStatusInternal(Context, 3221225688LL);
              }
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_D(
                  WPP_GLOBAL_Control->AttachedDevice,
                  22,
                  WPP_f4fe8069457b33cee1a723bb8f3f2247_Traceguids,
                  3221225480LL);
              }
              if ( RefsStatusDebugEnabled )
                RefsStatusDebug(-1073741816);
              RefsRaiseStatusInternal(Context, 3221225480LL);
              goto LABEL_144;
            }
          }
          RefsReleasePagingFastResource(v31, v10, v114);
        }
LABEL_128:
        v55 = RefsAcquirePagingFastResourceExclusive(v28, v10, v114, (unsigned __int8)v92);
        LOBYTE(v19) = (unsigned __int8)v19 | 2;
        MasterIrp = v55;
        LOBYTE(v89) = (_BYTE)v19;
        v99 = v55;
LABEL_129:
        v32 = v121;
        goto LABEL_49;
      }
      if ( (*((_DWORD *)FsContext2 + 1) & 0x100) == 0 )
      {
        v79 = *((_QWORD *)v10 + 4);
        if ( v79 <= QuadPart )
        {
          v71 = -1073741807;
          if ( RefsStatusDebugEnabled )
            RefsStatusDebug(-1073741807);
          RefsExtendedCompleteRequestInternal(Context, Irp, 3221225489LL);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_D(
              WPP_GLOBAL_Control->AttachedDevice,
              20,
              WPP_f4fe8069457b33cee1a723bb8f3f2247_Traceguids,
              3221225489LL);
          }
          if ( !RefsStatusDebugEnabled )
            return v71;
          goto LABEL_330;
        }
        if ( v79 < v107 )
          LODWORD(Length) = v79 - QuadPart;
      }
      if ( !(_BYTE)v22 )
      {
        RefsSetIoContextAsync((_DWORD)Context, 0, 0, 0, 0, QuadPart, Length, 0, Length);
        QuadPart = *(_QWORD *)v91;
        v23 = Context;
      }
      v80 = RefsVolumeDasdIo(v23, Irp, v10, FsContext2, QuadPart, Length);
      v71 = v80;
      Exception = v80;
      if ( v124 && !v93 && v80 >= 0 )
        v106->FileObject->CurrentByteOffset.QuadPart = Irp->IoStatus.Information + *(_QWORD *)v91;
      if ( !(_BYTE)v92 )
        return v71;
      v71 = Exception;
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(Exception);
      goto LABEL_305;
    }
    *(_BYTE *)(*(_QWORD *)(a1 + 144) + 3LL) |= 1u;
    return RefsMinstoreRead(a1, (_DWORD)Irp, (_DWORD)v10, QuadPart, Length);
  }
  else
  {
    *(_QWORD *)(*(_QWORD *)(a1 + 144) + 288LL) = 8;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(0);
    RefsExtendedCompleteRequestInternal(Context, Irp, 0);
    return 0;
  }
}

```

## disassembly

```asm
0x1c000dc80  mov     r11, rsp
0x1c000dc83  mov     [r11+10h], rdx
0x1c000dc87  mov     [r11+8], rcx
0x1c000dc8b  push    rbx
0x1c000dc8c  push    rsi
0x1c000dc8d  push    rdi
0x1c000dc8e  push    r12
0x1c000dc90  push    r13
0x1c000dc92  push    r14
0x1c000dc94  push    r15
0x1c000dc96  sub     rsp, 170h
0x1c000dc9d  mov     r15, rcx
0x1c000dca0  xor     r12d, r12d
0x1c000dca3  mov     r8d, r12d
0x1c000dca6  mov     [r11-100h], r12
0x1c000dcad  mov     r14d, r12d
0x1c000dcb0  mov     [r11-0F8h], r12
0x1c000dcb7  mov     dword ptr [rsp+1A8h+Size+4], r12d
0x1c000dcbc  mov     [rsp+1A8h+var_120], r12d
0x1c000dcc4  xorps   xmm0, xmm0
0x1c000dcc7  xor     eax, eax
0x1c000dcc9  movups  [rsp+1A8h+var_A8], xmm0
0x1c000dcd1  movups  [rsp+1A8h+var_98], xmm0
0x1c000dcd9  movups  [rsp+1A8h+var_88], xmm0
0x1c000dce1  movups  xmmword ptr [r11-78h], xmm0
0x1c000dce6  movups  xmmword ptr [r11-68h], xmm0
0x1c000dceb  mov     [r11-58h], rax
0x1c000dcef  mov     [rsp+1A8h+var_158], r12d
0x1c000dcf4  mov     ecx, [rcx+8]
0x1c000dcf7  and     ecx, 0FFFFFFF7h
0x1c000dcfa  mov     [r15+8], ecx
0x1c000dcfe  mov     rdi, [rdx+0B8h]
0x1c000dd05  mov     [rsp+1A8h+var_F0], rdi
0x1c000dd0d  mov     r11, [rdi+30h]
0x1c000dd11  mov     [rsp+1A8h+var_E0], r11
0x1c000dd19  mov     rax, [r11+18h]
0x1c000dd1d  mov     rsi, rax
0x1c000dd20  mov     qword ptr [rsp+1A8h+var_138], rax
0x1c000dd25  mov     [rsp+1A8h+var_C8], rax
0x1c000dd2d  test    rax, rax
0x1c000dd30  jz      loc_1C0071453
0x1c000dd36  mov     r8, [rax+80h]
0x1c000dd3d  mov     [rsp+1A8h+var_100], r8
0x1c000dd45  mov     rbx, [r11+20h]
0x1c000dd49  mov     [rsp+1A8h+var_108], rbx
0x1c000dd51  mov     r14, [rax+78h]
0x1c000dd55  mov     [rsp+1A8h+var_F8], r14
0x1c000dd5d  mov     eax, [r8+4]
0x1c000dd61  test    al, 1
0x1c000dd63  jz      loc_1C0071432
0x1c000dd69  mov     r9d, 1
0x1c000dd6f  test    rbx, rbx
0x1c000dd72  jz      loc_1C000F389
0x1c000dd78  movzx   r10d, byte ptr [rbx+50h]
0x1c000dd7d  mov     [rsp+1A8h+var_128], r10d
0x1c000dd85  lea     rax, [rsi+130h]
0x1c000dd8c  mov     [rsp+1A8h+var_118], rax
0x1c000dd94  mov     eax, [rax]
0x1c000dd96  bt      eax, 18h
0x1c000dd9a  jb      loc_1C007146C
0x1c000dda0  mov     eax, [r8+4]
0x1c000dda4  test    al, 1
0x1c000dda6  jz      loc_1C007150A
0x1c000ddac  and     ecx, 1
0x1c000ddaf  mov     [rsp+1A8h+var_148], ecx
0x1c000ddb3  mov     eax, [rdx+10h]
0x1c000ddb6  mov     r10d, eax
0x1c000ddb9  and     r10d, 2
0x1c000ddbd  mov     [rsp+1A8h+var_144], r10d
0x1c000ddc2  test    al, 1
0x1c000ddc4  jz      loc_1C00715A7
0x1c000ddca  mov     r13b, 1
0x1c000ddcd  mov     byte ptr [rsp+1A8h+arg_10], r13b
0x1c000ddd5  mov     eax, [r11+50h]
0x1c000ddd9  test    al, 2
0x1c000dddb  jnz     loc_1C00715AF
0x1c000dde1  mov     [rsp+1A8h+arg_18], r12b
0x1c000dde9  test    rbx, rbx
0x1c000ddec  jz      short loc_1C000DE0A
0x1c000ddee  test    dword ptr [rbx+4], 2000h
0x1c000ddf5  jnz     loc_1C00715BC
0x1c000ddfb  test    rbx, rbx
0x1c000ddfe  jz      short loc_1C000DE0A
0x1c000de00  test    byte ptr [rbx+58h], 8
0x1c000de04  jnz     loc_1C0071658
0x1c000de0a  mov     rdx, [rdi+18h]
0x1c000de0e  mov     qword ptr [rsp+1A8h+var_150], rdx
0x1c000de13  mov     [rsp+1A8h+var_B0], rdx
0x1c000de1b  mov     r11d, [rdi+8]
0x1c000de1f  mov     dword ptr [rsp+1A8h+var_110], r11d
0x1c000de27  mov     dword ptr [rsp+1A8h+Size], r11d
0x1c000de2c  test    r13b, r13b
0x1c000de2f  jz      loc_1C0071668
0x1c000de35  mov     rax, [r14+58h]
0x1c000de39  mov     ecx, [rax+114h]
0x1c000de3f  dec     ecx
0x1c000de41  mov     eax, edx
0x1c000de43  or      eax, r11d
0x1c000de46  test    eax, ecx
0x1c000de48  jz      loc_1C0071668
0x1c000de4e  mov     dil, 20h ; ' '
0x1c000de51  mov     byte ptr [rsp+1A8h+var_158], dil
0x1c000de56  test    rbx, rbx
0x1c000de59  jz      short loc_1C000DE65
0x1c000de5b  cmp     [rbx+5Ah], r12b
0x1c000de5f  ja      loc_1C0071672
0x1c000de65  mov     [rsp+1A8h+var_D8], r11
0x1c000de6d  mov     rax, 7FFFFFFFFFFFFFFFh
0x1c000de77  sub     rax, rdx
0x1c000de7a  cmp     rax, r11
0x1c000de7d  jl      loc_1C007167F
0x1c000de83  lea     rax, [r11+rdx]
0x1c000de87  mov     [rsp+1A8h+var_E8], rax
0x1c000de8f  mov     [rsp+1A8h+var_48], rax
0x1c000de97  test    r11d, r11d
0x1c000de9a  jz      loc_1C0071712
0x1c000dea0  cmp     [r8+0F68h], r12
0x1c000dea7  jz      loc_1C000F3BF
0x1c000dead  xor     ecx, ecx; PerformanceFrequency
0x1c000deaf  call    cs:__imp_KeQueryPerformanceCounter
0x1c000deb6  nop     dword ptr [rax+rax+00h]
0x1c000debb  mov     rcx, [r15+90h]
0x1c000dec2  mov     [rcx+120h], rax
0x1c000dec9  mov     [rsp+1A8h+var_140], r12d
0x1c000dece  mov     r10d, [rsp+1A8h+var_144]
0x1c000ded3  test    r10d, r10d
0x1c000ded6  jnz     short loc_1C000DEE1
0x1c000ded8  test    r13b, r13b
0x1c000dedb  jz      loc_1C0071762
0x1c000dee1  xor     cl, cl
0x1c000dee3  mov     eax, 10h
0x1c000dee8  mov     r13d, 14h
0x1c000deee  test    r10d, r10d
0x1c000def1  cmovnz  eax, r13d
0x1c000def5  or      al, cl
0x1c000def7  mov     r8d, [rsp+1A8h+var_148]
0x1c000defc  or      al, r8b
0x1c000deff  mov     byte ptr [rsp+1A8h+var_140+3], al
0x1c000df03  mov     rcx, [r15+90h]
0x1c000df0a  mov     eax, [rsp+1A8h+var_140]
0x1c000df0e  or      [rcx], eax
0x1c000df10  lea     r9d, [r13-13h]
0x1c000df14  mov     r11d, dword ptr [rsp+1A8h+var_110]
0x1c000df1c  mov     rdx, qword ptr [rsp+1A8h+var_150]
0x1c000df21  mov     rax, [rsp+1A8h+var_E0]
0x1c000df29  mov     eax, [rax+50h]
0x1c000df2c  bt      eax, 1Dh
0x1c000df30  jb      loc_1C000F394
0x1c000df36  lea     rax, [rsi+88h]
0x1c000df3d  mov     [rsp+1A8h+var_D0], rax
0x1c000df45  mov     eax, [rax]
0x1c000df47  test    al, 20h
0x1c000df49  jz      loc_1C0071769
0x1c000df4f  mov     eax, [r15+0Ch]
0x1c000df53  mov     rcx, [rsp+1A8h+Context]
0x1c000df5b  test    al, al
0x1c000df5d  js      loc_1C0071786
0x1c000df63  cmp     [rsp+1A8h+var_128], 4
0x1c000df6b  jz      loc_1C0071798
0x1c000df71  test    r10d, r10d
0x1c000df74  jnz     loc_1C000F2B5
0x1c000df7a  mov     r13d, dword ptr [rsp+1A8h+var_110]
0x1c000df82  test    r10d, r10d
0x1c000df85  jnz     loc_1C000F327
0x1c000df8b  cmp     byte ptr [rsp+1A8h+arg_10], r12b
0x1c000df93  jz      loc_1C000F327
0x1c000df99  mov     [rsp+1A8h+var_60], r12
0x1c000dfa1  mov     [rsp+1A8h+var_58], r12
0x1c000dfa9  mov     dword ptr [rsp+1A8h+var_60+4], r9d
0x1c000dfb1  call    cs:__imp_IoGetTopLevelIrp
0x1c000dfb8  nop     dword ptr [rax+rax+00h]
0x1c000dfbd  mov     [rsp+1A8h+var_110], rax
0x1c000dfc5  cmp     byte ptr [rax+1], 0
0x1c000dfc9  jnz     loc_1C000E665
0x1c000dfcf  cmp     [rsp+1A8h+var_144], 0
0x1c000dfd4  jnz     loc_1C000E308
0x1c000dfda  mov     [rsp+1A8h+var_124], r12d
0x1c000dfe2  movzx   ecx, byte ptr [rsp+1A8h+arg_10]
0x1c000dfea  test    cl, cl
0x1c000dfec  jz      loc_1C000E682
0x1c000dff2  xor     r15b, r15b
0x1c000dff5  test    cl, cl
0x1c000dff7  jz      short loc_1C000E00B
0x1c000dff9  mov     rax, [rsi+0F0h]
0x1c000e000  cmp     qword ptr [rax+8], 0
0x1c000e005  jnz     loc_1C000E698
0x1c000e00b  mov     rcx, r12
0x1c000e00e  mov     eax, 802h
0x1c000e013  cmp     ax, [rsi]
0x1c000e016  jz      loc_1C000E6A6
0x1c000e01c  cmp     [rsi+10h], rcx
0x1c000e020  jz      short loc_1C000E026
0x1c000e022  mov     rcx, [rsi+78h]
0x1c000e026  movzx   r8d, byte ptr [rsp+1A8h+var_148]
0x1c000e02c  lea     rdx, [rsp+1A8h+var_A8]
0x1c000e034  mov     rcx, [rcx+68h]
0x1c000e038  call    MsAcquireFastResourceShared
0x1c000e03d  movzx   ecx, al
0x1c000e040  mov     [rsp+1A8h+var_124], ecx
0x1c000e047  test    al, al
0x1c000e049  jz      loc_1C000E707
0x1c000e04f  test    r15b, r15b
0x1c000e052  jnz     loc_1C000E6AE
0x1c000e058  movzx   edx, byte ptr [rsp+1A8h+arg_10]
0x1c000e060  test    dl, dl
0x1c000e062  jz      short loc_1C000E076
0x1c000e064  mov     rax, [rsi+0F0h]
0x1c000e06b  cmp     qword ptr [rax+8], 0
0x1c000e070  jnz     loc_1C000E6C1
0x1c000e076  test    ecx, ecx
0x1c000e078  jz      loc_1C000E714
0x1c000e07e  or      dil, 1
0x1c000e082  mov     byte ptr [rsp+1A8h+var_158], dil
0x1c000e087  mov     rax, [rsp+1A8h+var_118]
0x1c000e08f  mov     eax, [rax]
0x1c000e091  bt      eax, 18h
0x1c000e095  jb      loc_1C000E785
0x1c000e09b  mov     eax, [rbx+4]
0x1c000e09e  bt      eax, 0Fh
0x1c000e0a2  jb      loc_1C000E7F9
0x1c000e0a8  mov     eax, [r14+4]
0x1c000e0ac  bt      eax, 18h
0x1c000e0b0  jb      loc_1C000E884
0x1c000e0b6  cmp     qword ptr [r14+8], 0
0x1c000e0bb  jz      loc_1C000E86A
0x1c000e0c1  cmp     qword ptr [r14+0F0h], 0
0x1c000e0c9  jz      loc_1C000E884
0x1c000e0cf  test    dl, dl
0x1c000e0d1  jz      short loc_1C000E0E5
0x1c000e0d3  mov     rax, [rsi+0F0h]
0x1c000e0da  cmp     qword ptr [rax+8], 0
0x1c000e0df  jnz     loc_1C000E8F5
0x1c000e0e5  mov     r13, [rsp+1A8h+Context]
0x1c000e0ed  mov     r14d, 805h
0x1c000e0f3  mov     r15d, 802h
0x1c000e0f9  mov     rax, [rsp+1A8h+var_118]
0x1c000e101  mov     eax, [rax]
0x1c000e103  bt      eax, 10h
0x1c000e107  jb      loc_1C000EAB2
0x1c000e10d  bt      eax, 18h
0x1c000e111  jb      loc_1C000EABC
0x1c000e117  mov     ebx, r12d
0x1c000e11a  mov     [rsp+1A8h+Exception], ebx
0x1c000e11e  test    al, 40h
0x1c000e120  jnz     loc_1C000EAC6
0x1c000e126  test    ebx, ebx
0x1c000e128  js      loc_1C000EB34
0x1c000e12e  mov     rax, [rsp+1A8h+var_D0]
0x1c000e136  mov     eax, [rax]
0x1c000e138  test    al, 20h
0x1c000e13a  jz      loc_1C000EBA3
0x1c000e140  cmp     [rsp+1A8h+var_128], 2
0x1c000e148  jnz     loc_1C000EDA6
0x1c000e14e  lea     rax, RefsPrePostIrp
0x1c000e155  mov     [rsp+1A8h+PostIrpRoutine], rax; PostIrpRoutine
0x1c000e15a  lea     r9, RefsOplockComplete; CompletionRoutine
0x1c000e161  mov     r8, r13; Context
0x1c000e164  mov     r13, [rsp+1A8h+Irp]
0x1c000e16c  mov     rdx, r13; Irp
0x1c000e16f  lea     rcx, [rsi+58h]; Oplock
0x1c000e173  call    cs:__imp_FsRtlCheckOplock
0x1c000e17a  nop     dword ptr [rax+rax+00h]
0x1c000e17f  mov     r9d, eax
0x1c000e182  mov     [rsp+1A8h+Exception], eax
0x1c000e186  test    eax, eax
0x1c000e188  jnz     loc_1C000EC62
0x1c000e18e  cmp     [rsi+5], al
0x1c000e191  jz      loc_1C000EC84
0x1c000e197  mov     r15d, [rsp+1A8h+var_144]
0x1c000e19c  test    r15d, r15d
0x1c000e19f  jnz     short loc_1C000E1B1
0x1c000e1a1  mov     rcx, [rsi+150h]; FileLock
0x1c000e1a8  test    rcx, rcx
0x1c000e1ab  jnz     loc_1C000ED1B
0x1c000e1b1  mov     eax, [rsi+9Ch]
0x1c000e1b7  mov     [rsp+1A8h+var_140], eax
0x1c000e1bb  lock or [rsp+1A8h+var_1A8], 0
0x1c000e1c0  mov     edi, [rsp+1A8h+var_140]
0x1c000e1c4  mov     r13, [rsp+1A8h+var_C8]
0x1c000e1cc  mov     rdx, qword ptr [rsp+1A8h+var_138]
0x1c000e1d1  and     edi, 1
0x1c000e1d4  jnz     loc_1C000E3DD
0x1c000e1da  mov     rbx, [rdx+20h]
0x1c000e1de  mov     [rsp+1A8h+var_C0], rbx
0x1c000e1e6  test    r15d, r15d
0x1c000e1e9  jnz     loc_1C000E2F2
0x1c000e1ef  test    edi, edi
0x1c000e1f1  jnz     loc_1C000E439
0x1c000e1f7  lock or [rsp+1A8h+var_1A8], edi
0x1c000e1fb  mov     eax, [r13+9Ch]
0x1c000e202  cmp     [rsp+1A8h+var_140], eax
0x1c000e206  jnz     loc_1C000EDB0
0x1c000e20c  mov     rsi, qword ptr [rsp+1A8h+var_138]
0x1c000e211  mov     r11, qword ptr [rsp+1A8h+var_150]
0x1c000e216  cmp     r11, rbx
0x1c000e219  jge     loc_1C000EDBE
0x1c000e21f  cmp     [rsp+1A8h+var_E8], rbx
0x1c000e227  jg      loc_1C000EE78
0x1c000e22d  mov     ebx, dword ptr [rsp+1A8h+Size]
0x1c000e231  mov     edx, [rsi+88h]
  ... truncated ...
```
