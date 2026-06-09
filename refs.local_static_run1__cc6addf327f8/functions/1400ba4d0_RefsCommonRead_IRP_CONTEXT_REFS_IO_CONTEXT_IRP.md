# RefsCommonRead(_IRP_CONTEXT *,REFS_IO_CONTEXT *,_IRP *)

- ea: `0x1400ba4d0`
- end: `0x1400bc59e`
- name: `?RefsCommonRead@@YAJPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@PEAU_IRP@@@Z`
- size: `8398`
- prototype: `__int64 __fastcall(struct _IRP_CONTEXT *, struct REFS_IO_CONTEXT *, PIRP Irp)`
- caller_count: `3`
- callee_count: `31`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400b9530`
- `0x1400bc5b0`
- `0x14032da60`

## callees

- `0x140009d5c`
- `0x14000a2f0`
- `0x14000c180`
- `0x14000d820`
- `0x14000dfe0`
- `0x14000e0e0`
- `0x14000f090`
- `0x140036670`
- `0x1400733d0`
- `0x140075c94`
- `0x140076060`
- `0x140076a40`
- `0x140076ad0`
- `0x1400862c0`
- `0x140088990`
- `0x140089680`
- `0x14008d920`
- `0x140097c50`
- `0x14009c260`
- `0x1400a79f8`
- `0x1400ba4d0`
- `0x1400d0fd8`
- `0x1400f4880`
- `0x1400ff71c`
- `0x1400ff80c`
- `0x14029fc3c`
- `0x140318ae0`
- `0x140323450`
- `0x14033046c`
- `0x14033afa0`
- `0x14033e290`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x1400bb186`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400bb8f7`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400bb186`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400bb8f7`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400ba783`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400ba79d`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400ba9ed`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400baa07`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400babae`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400babc8`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400baf9c`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400bafb6`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400bc172`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400bc18c`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400ba783`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400ba79d`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400ba9ed`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400baa07`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400babae`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400babc8`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400baf9c`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400bafb6`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400bc172`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400bc18c`
- `ntoskrnl!ExRaiseStatus` at `0x1400bbe07`
- `ntoskrnl!ExRaiseStatus` at `0x1400bbe07`
- `ntoskrnl!DbgPrintEx` at `0x1400ba71c`
- `ntoskrnl!DbgPrintEx` at `0x1400ba986`
- `ntoskrnl!DbgPrintEx` at `0x1400bab4e`
- `ntoskrnl!DbgPrintEx` at `0x1400baf35`
- `ntoskrnl!DbgPrintEx` at `0x1400bc112`
- `ntoskrnl!DbgPrintEx` at `0x1400ba71c`
- `ntoskrnl!DbgPrintEx` at `0x1400ba986`
- `ntoskrnl!DbgPrintEx` at `0x1400bab4e`
- `ntoskrnl!DbgPrintEx` at `0x1400baf35`
- `ntoskrnl!DbgPrintEx` at `0x1400bc112`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400ba749`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400ba9b3`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400bab74`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400baf62`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400bc138`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400ba749`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400ba9b3`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400bab74`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400baf62`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400bc138`
- `ntoskrnl!_strnicmp` at `0x1400ba7c8`
- `ntoskrnl!_strnicmp` at `0x1400baa32`
- `ntoskrnl!_strnicmp` at `0x1400babf3`
- `ntoskrnl!_strnicmp` at `0x1400bafe1`
- `ntoskrnl!_strnicmp` at `0x1400bc1b7`
- `ntoskrnl!_strnicmp` at `0x1400ba7c8`
- `ntoskrnl!_strnicmp` at `0x1400baa32`
- `ntoskrnl!_strnicmp` at `0x1400babf3`
- `ntoskrnl!_strnicmp` at `0x1400bafe1`
- `ntoskrnl!_strnicmp` at `0x1400bc1b7`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400ba7ac`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400baa16`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400babd7`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400bafc5`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400bc19b`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400ba7ac`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400baa16`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400babd7`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400bafc5`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400bc19b`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400bba02`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400bba02`
- `ntoskrnl!ExIsFastResourceHeld` at `0x1400bb4a7`
- `ntoskrnl!ExIsFastResourceHeld` at `0x1400bb4a7`
- `ntoskrnl!FsRtlCheckLockForReadAccess` at `0x1400bb837`
- `ntoskrnl!FsRtlCheckLockForReadAccess` at `0x1400bb837`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x1400bb7c8`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x1400bb7c8`
- `ntoskrnl!FsRtlCheckOplock` at `0x1400bb728`
- `ntoskrnl!FsRtlCheckOplock` at `0x1400bb728`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x1400bbdf9`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x1400bbdf9`
- `ntoskrnl!ExReleaseFastResource` at `0x1400bbfb9`
- `ntoskrnl!ExReleaseFastResource` at `0x1401f7186`
- `ntoskrnl!ExReleaseFastResource` at `0x1400bbfb9`
- `ntoskrnl!ExReleaseFastResource` at `0x1401f7186`
- `HAL!KeQueryPerformanceCounter` at `0x1400bad96`
- `HAL!KeQueryPerformanceCounter` at `0x1400bad96`

## string_xrefs

- `0x1400ba6e6`: `Read.c`
- `0x1400ba950`: `Read.c`
- `0x1400bab1b`: `Read.c`
- `0x1400baeff`: `Read.c`
- `0x1400bb60e`: `Read.c`
- `0x1400bb89e`: `Read.c`
- `0x1400bbae9`: `Read.c`
- `0x1400bbde1`: `Read.c`
- `0x1400bc0df`: `Read.c`
- `0x1400bc281`: `Read.c`
- `0x1400bc2f0`: `Read.c`
- `0x1400bc35f`: `Read.c`
- `0x1400bc3ce`: `Read.c`
- `0x1400bc43a`: `Read.c`
- `0x1400bc4a3`: `Read.c`
- `0x1400bc512`: `Read.c`
- `0x1400bc53a`: `Read.c`

## pseudocode

```c
__int64 __fastcall RefsCommonRead(struct _IRP_CONTEXT *a1, struct REFS_IO_CONTEXT *a2, PIRP Irp)
{
  struct _IRP_CONTEXT *v5; // rbx
  __int64 v6; // rcx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  struct _FILE_OBJECT *FileObject; // r9
  unsigned __int64 FsContext; // rdi
  __int64 v10; // r10
  char *FsContext2; // rdx
  int v12; // eax
  struct _FCB *v13; // r11
  char v14; // r8
  unsigned int v15; // eax
  int v16; // ecx
  __int64 v17; // rax
  volatile unsigned int v18; // ebx
  struct _KPROCESS *v19; // rbx
  PEPROCESS CurrentProcess; // rax
  const char *ProcessImageFileName; // rax
  __int64 v22; // rcx
  int v24; // ecx
  ULONG Flags; // r15d
  __int64 v26; // rcx
  unsigned int v27; // eax
  int v28; // ecx
  __int64 v29; // rax
  volatile unsigned int v30; // ebx
  struct _KPROCESS *v31; // rbx
  PEPROCESS v32; // rax
  const char *v33; // rax
  __int64 v34; // rdx
  NTSTATUS RangeFromEof; // esi
  volatile unsigned int v36; // ebx
  struct _KPROCESS *v37; // rbx
  PEPROCESS v38; // rax
  const char *v39; // rax
  __int64 v40; // rcx
  struct _KTHREAD *CurrentThread; // rax
  unsigned __int64 Length; // r8
  __int64 QuadPart; // r12
  __int64 v44; // rsi
  __int64 v45; // r11
  char v46; // r15
  struct _CCB *v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rdx
  LARGE_INTEGER PerformanceCounter; // rax
  int v51; // r10d
  char v52; // cl
  __int64 v53; // rax
  volatile unsigned int v54; // ebx
  struct _KPROCESS *v55; // rbx
  PEPROCESS v56; // rax
  const char *v57; // rax
  __int64 v58; // rdx
  int v59; // edi
  unsigned __int8 v60; // r9
  _DWORD *v61; // rdx
  __int16 v62; // ax
  PIRP TopLevelIrp; // rax
  __int64 v64; // r8
  int v65; // eax
  unsigned __int8 v66; // al
  unsigned int v67; // r8d
  __int64 v68; // rcx
  unsigned __int8 v69; // al
  char *v70; // r8
  __int64 v71; // rcx
  unsigned __int8 v72; // al
  __int16 v73; // ax
  __int64 v74; // rdx
  __int64 v75; // r9
  unsigned int v76; // r10d
  int v77; // r12d
  int v78; // eax
  __int16 v79; // ax
  __int16 v80; // ax
  int v81; // ecx
  __int64 v82; // rcx
  struct _IRP *v83; // r14
  __int64 v84; // rsi
  char v85; // al
  __int64 v86; // rax
  int v87; // r12d
  FILE_LOCK *v88; // rcx
  __int64 v89; // r8
  ULONG_PTR v90; // r12
  int v91; // eax
  int v92; // eax
  __int16 v93; // ax
  unsigned int v94; // r12d
  int v95; // ecx
  int v96; // r10d
  int v97; // r10d
  struct _MS_FAST_RESOURCE_OWNER_ENTRY *v98; // rax
  char v99; // al
  NTSTATUS v100; // eax
  ULONG v101; // eax
  ULONG_PTR v102; // rcx
  __int64 v103; // r9
  unsigned __int64 v104; // rax
  __int64 v105; // rcx
  __int64 v106; // rcx
  unsigned int v107; // eax
  int v108; // ecx
  __int64 v109; // rax
  volatile unsigned int v110; // ebx
  struct _KPROCESS *v111; // rbx
  PEPROCESS v112; // rax
  const char *v113; // rax
  unsigned __int8 v114; // [rsp+C8h] [rbp-1B8h]
  int v115; // [rsp+E8h] [rbp-198h] BYREF
  unsigned int v116; // [rsp+ECh] [rbp-194h]
  int v117; // [rsp+F0h] [rbp-190h]
  ULONG v118; // [rsp+F4h] [rbp-18Ch]
  int v119; // [rsp+F8h] [rbp-188h]
  ULONG v120; // [rsp+FCh] [rbp-184h]
  __int64 v121; // [rsp+100h] [rbp-180h]
  int v122; // [rsp+108h] [rbp-178h]
  struct _CCB *v123; // [rsp+110h] [rbp-170h]
  unsigned __int64 v124; // [rsp+118h] [rbp-168h]
  PIRP v125; // [rsp+120h] [rbp-160h]
  __int64 v126; // [rsp+128h] [rbp-158h]
  struct _FCB *v127; // [rsp+130h] [rbp-150h]
  unsigned __int64 LowLimit[2]; // [rsp+138h] [rbp-148h] BYREF
  unsigned int v129; // [rsp+148h] [rbp-138h]
  struct _FILE_OBJECT *v130; // [rsp+150h] [rbp-130h]
  unsigned __int8 v131[8]; // [rsp+158h] [rbp-128h]
  __int64 v132; // [rsp+160h] [rbp-120h]
  unsigned __int64 v133; // [rsp+168h] [rbp-118h]
  _OWORD v134[4]; // [rsp+178h] [rbp-108h] BYREF
  __int128 v135; // [rsp+1B8h] [rbp-C8h]
  __int64 v136; // [rsp+1C8h] [rbp-B8h]
  unsigned __int64 v137; // [rsp+1D8h] [rbp-A8h]
  unsigned __int64 v138; // [rsp+1E0h] [rbp-A0h]
  unsigned __int64 v139; // [rsp+1E8h] [rbp-98h]
  _QWORD v140[3]; // [rsp+1F0h] [rbp-90h] BYREF
  __int64 v141; // [rsp+208h] [rbp-78h]
  unsigned __int64 v142; // [rsp+210h] [rbp-70h]
  unsigned __int64 v143; // [rsp+218h] [rbp-68h]
  unsigned __int64 v144; // [rsp+220h] [rbp-60h]
  unsigned __int64 v145; // [rsp+228h] [rbp-58h]
  unsigned __int64 v146; // [rsp+230h] [rbp-50h]
  unsigned __int64 v147; // [rsp+238h] [rbp-48h]
  unsigned __int64 v148; // [rsp+240h] [rbp-40h]
  char v149; // [rsp+298h] [rbp+18h]
  bool v150; // [rsp+2A0h] [rbp+20h]

  v125 = Irp;
  v5 = a1;
  memset(v134, 0, sizeof(v134));
  v135 = 0;
  v136 = 0;
  v115 = 0;
  *((_QWORD *)a1 + 1) &= ~8uLL;
  v6 = *((_QWORD *)a1 + 1);
  v121 = v6;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  *(_QWORD *)v131 = CurrentStackLocation;
  FileObject = CurrentStackLocation->FileObject;
  v130 = FileObject;
  FsContext = (unsigned __int64)FileObject->FsContext;
  if ( FsContext )
  {
    v10 = *(_QWORD *)(FsContext + 144);
    v126 = v10;
    FsContext2 = (char *)FileObject->FsContext2;
    v123 = (struct _CCB *)FsContext2;
    v12 = *(_DWORD *)(v10 + 24);
    if ( (v12 & 1) == 0 && (!FsContext2 || FsContext2[80] != 4 || (v12 & 2) == 0) )
    {
      RefsRaiseStatusInternal(v5, -1073741202, (unsigned int)Irp);
      goto LABEL_405;
    }
    v13 = *(struct _FCB **)(FsContext + 136);
    v127 = v13;
    if ( FsContext2 )
      v14 = FsContext2[80];
    else
      v14 = 5;
  }
  else
  {
    v10 = 0;
    v126 = 0;
    v13 = 0;
    v127 = 0;
    FsContext2 = 0;
    v123 = 0;
    v14 = 1;
  }
  v149 = v14;
  if ( (*(_DWORD *)(v10 + 24) & 1) == 0 && v14 != 4 )
  {
    if ( v5 )
    {
      if ( (v6 & 0x100000000LL) != 0 )
      {
        *((_QWORD *)v5 + 1) = v6 | 0x200000000LL;
        goto LABEL_24;
      }
      *((_QWORD *)v5 + 1) = v6 | 0x8000;
      v15 = *((unsigned __int8 *)v5 + 40);
      if ( (unsigned __int8)v15 <= 0x12u )
      {
        v16 = 262685;
        if ( _bittest(&v16, v15) )
        {
          v17 = *((_QWORD *)v5 + 8);
          if ( v17 )
          {
            if ( *(_BYTE *)(v17 + 10304) && (*((_DWORD *)v5 + 1) & 0x400) == 0 && (*((_DWORD *)v5 + 2) & 0x10000) == 0 )
              *((_QWORD *)v5 + 86) = 7;
          }
        }
      }
      *((_DWORD *)a2 + 199) &= ~1u;
    }
    RefsCompleteRequest(v5, Irp, -1073741202);
LABEL_24:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_78e3b6b3f5653fb4a422c7659bfeaffe_Traceguids, 3221226094LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
    {
      if ( RefsStatusDisplayStatus == -1073741202 )
        DbgPrintEx(0x95u, 0, "th%p %x %s:%i\n", KeGetCurrentThread(), -1073741202, "Read.c", 788);
      v18 = RefsStatusBreakOnWin32Error;
      if ( RefsStatusBreakOnStatus == -1073741202
        || RefsStatusBreakOnWin32Error && v18 == RtlNtStatusToDosErrorNoTeb(-1073741202) )
      {
        v19 = RefsStatusBreakForProcess;
        if ( !RefsStatusBreakForThread
          || RefsStatusBreakForThread == KeGetCurrentThread()
          && (!RefsStatusBreakForProcess || v19 == IoGetCurrentProcess())
          && (!RefsStatusBreakForImage
           || (CurrentProcess = IoGetCurrentProcess(),
               ProcessImageFileName = (const char *)PsGetProcessImageFileName(CurrentProcess),
               !_strnicmp(&RefsStatusBreakForImage, ProcessImageFileName, 0xFu))) )
        {
          __int2c();
        }
      }
      v22 = 32LL
          * (((unsigned __int16)_InterlockedExchangeAdd((volatile signed __int32 *)&RefsStatusNextQueueEntry, 1u) + 1)
           & 0xFFF);
      *(_QWORD *)((char *)&RefsStatusQueue + v22) = KeGetCurrentThread();
      *(unsigned int *)((char *)&RefsStatusQueue + v22 + 8) = -1073741202;
      *(_QWORD *)((char *)&RefsStatusQueue + v22 + 16) = "Read.c";
      *(unsigned int *)((char *)&RefsStatusQueue + v22 + 24) = 788;
    }
    return 3221226094LL;
  }
  Flags = Irp->Flags;
  v24 = Flags & 2;
  v119 = v24;
  v150 = v24 != 0;
  LOBYTE(Flags) = Flags & 1;
  v118 = Flags;
  v120 = FileObject->Flags;
  if ( (_BYTE)Flags && (*(_DWORD *)(FsContext + 152) & 0x1000000) != 0 )
  {
    if ( v5 )
    {
      v26 = *((_QWORD *)v5 + 1);
      if ( (v26 & 0x100000000LL) != 0 )
      {
        *((_QWORD *)v5 + 1) = v26 | 0x200000000LL;
        goto LABEL_57;
      }
      *((_QWORD *)v5 + 1) |= 0x8000uLL;
      v27 = *((unsigned __int8 *)v5 + 40);
      if ( (unsigned __int8)v27 <= 0x12u )
      {
        v28 = 262685;
        if ( _bittest(&v28, v27) )
        {
          v29 = *((_QWORD *)v5 + 8);
          if ( v29 )
          {
            if ( *(_BYTE *)(v29 + 10304) && (*((_DWORD *)v5 + 1) & 0x400) == 0 && (*((_DWORD *)v5 + 2) & 0x10000) == 0 )
              *((_QWORD *)v5 + 86) = 7;
          }
        }
      }
      *((_DWORD *)a2 + 199) &= ~1u;
    }
    RefsCompleteRequest(v5, Irp, -1073739760);
LABEL_57:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_78e3b6b3f5653fb4a422c7659bfeaffe_Traceguids, 3221227536LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
    {
      if ( RefsStatusDisplayStatus == -1073739760 )
        DbgPrintEx(0x95u, 0, "th%p %x %s:%i\n", KeGetCurrentThread(), -1073739760, "Read.c", 812);
      v30 = RefsStatusBreakOnWin32Error;
      if ( RefsStatusBreakOnStatus == -1073739760
        || RefsStatusBreakOnWin32Error && v30 == RtlNtStatusToDosErrorNoTeb(-1073739760) )
      {
        v31 = RefsStatusBreakForProcess;
        if ( !RefsStatusBreakForThread
          || RefsStatusBreakForThread == KeGetCurrentThread()
          && (!RefsStatusBreakForProcess || v31 == IoGetCurrentProcess())
          && (!RefsStatusBreakForImage
           || (v32 = IoGetCurrentProcess(),
               v33 = (const char *)PsGetProcessImageFileName(v32),
               !_strnicmp(&RefsStatusBreakForImage, v33, 0xFu))) )
        {
          __int2c();
        }
      }
      v34 = 32LL
          * (((unsigned __int16)_InterlockedExchangeAdd((volatile signed __int32 *)&RefsStatusNextQueueEntry, 1u) + 1)
           & 0xFFF);
      *(_QWORD *)((char *)&RefsStatusQueue + v34) = KeGetCurrentThread();
      *(unsigned int *)((char *)&RefsStatusQueue + v34 + 8) = -1073739760;
      *(_QWORD *)((char *)&RefsStatusQueue + v34 + 16) = "Read.c";
      *(unsigned int *)((char *)&RefsStatusQueue + v34 + 24) = 812;
    }
    return 3221227536LL;
  }
  if ( FsContext2 && (*((_DWORD *)FsContext2 + 1) & 0x2000) != 0 && !v24 )
  {
    RangeFromEof = -1073741811;
    RefsCompleteReadWriteRequest(v5, a2, Irp, -1073741811);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_78e3b6b3f5653fb4a422c7659bfeaffe_Traceguids, 3221225485LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      return (unsigned int)RangeFromEof;
    if ( RefsStatusDisplayStatus == -1073741811 )
      DbgPrintEx(0x95u, 0, "th%p %x %s:%i\n", KeGetCurrentThread(), -1073741811, "Read.c", 824);
    v36 = RefsStatusBreakOnWin32Error;
    if ( RefsStatusBreakOnStatus == -1073741811
      || RefsStatusBreakOnWin32Error && v36 == RtlNtStatusToDosErrorNoTeb(-1073741811) )
    {
      v37 = RefsStatusBreakForProcess;
      if ( !RefsStatusBreakForThread
        || RefsStatusBreakForThread == KeGetCurrentThread()
        && (!RefsStatusBreakForProcess || v37 == IoGetCurrentProcess())
        && (!RefsStatusBreakForImage
         || (v38 = IoGetCurrentProcess(),
             v39 = (const char *)PsGetProcessImageFileName(v38),
             !_strnicmp(&RefsStatusBreakForImage, v39, 0xFu))) )
      {
        __int2c();
      }
    }
    v40 = 32LL
        * (((unsigned __int16)_InterlockedExchangeAdd((volatile signed __int32 *)&RefsStatusNextQueueEntry, 1u) + 1)
         & 0xFFF);
    CurrentThread = KeGetCurrentThread();
    *(unsigned int *)((char *)&RefsStatusQueue + v40 + 24) = 824;
LABEL_402:
    *(_QWORD *)((char *)&RefsStatusQueue + v40 + 16) = "Read.c";
    *(unsigned int *)((char *)&RefsStatusQueue + v40 + 8) = -1073741811;
    *(_QWORD *)((char *)&RefsStatusQueue + v40) = CurrentThread;
    return (unsigned int)RangeFromEof;
  }
  RefsUpdateFileTimestampsFromNonpagedFcb(v13, 0);
  Length = CurrentStackLocation->Parameters.Read.Length;
  v124 = Length;
  QuadPart = CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart;
  v132 = QuadPart;
  LowLimit[0] = QuadPart;
  v44 = Length + QuadPart;
  LowLimit[1] = Length + QuadPart;
  v129 = Length;
  v45 = v126;
  if ( (_BYTE)Flags
    && (((*(_DWORD *)(v126 + 276) - 1) & (unsigned int)QuadPart) != 0
     || ((*(_DWORD *)(v126 + 276) - 1) & (unsigned int)Length) != 0) )
  {
    v46 = 32;
    LOBYTE(v115) = 32;
  }
  else
  {
    v46 = v115;
  }
  v47 = v123;
  if ( v123 && *((_BYTE *)v123 + 81) )
    *((_QWORD *)v5 + 1) |= 0x8000000000uLL;
  if ( QuadPart < 0 || QuadPart > v44 )
  {
    if ( v5 )
    {
      v106 = *((_QWORD *)v5 + 1);
      if ( (v106 & 0x100000000LL) != 0 )
      {
        *((_QWORD *)v5 + 1) = v106 | 0x200000000LL;
        RangeFromEof = -1073741811;
        goto LABEL_384;
      }
      *((_QWORD *)v5 + 1) |= 0x8000uLL;
      v107 = *((unsigned __int8 *)v5 + 40);
      if ( (unsigned __int8)v107 <= 0x12u )
      {
        v108 = 262685;
        if ( _bittest(&v108, v107) )
        {
          v109 = *((_QWORD *)v5 + 8);
          if ( v109 )
          {
            if ( *(_BYTE *)(v109 + 10304) && (*((_DWORD *)v5 + 1) & 0x400) == 0 && (*((_DWORD *)v5 + 2) & 0x10000) == 0 )
              *((_QWORD *)v5 + 86) = 7;
          }
        }
      }
      *((_DWORD *)a2 + 199) &= ~1u;
    }
    RangeFromEof = -1073741811;
    RefsCompleteRequest(v5, Irp, -1073741811);
LABEL_384:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_78e3b6b3f5653fb4a422c7659bfeaffe_Traceguids, 3221225485LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      return (unsigned int)RangeFromEof;
    if ( RefsStatusDisplayStatus == -1073741811 )
      DbgPrintEx(0x95u, 0, "th%p %x %s:%i\n", KeGetCurrentThread(), -1073741811, "Read.c", 873);
    v110 = RefsStatusBreakOnWin32Error;
    if ( RefsStatusBreakOnStatus == -1073741811
      || RefsStatusBreakOnWin32Error && v110 == RtlNtStatusToDosErrorNoTeb(-1073741811) )
    {
      v111 = RefsStatusBreakForProcess;
      if ( !RefsStatusBreakForThread
        || RefsStatusBreakForThread == KeGetCurrentThread()
        && (!RefsStatusBreakForProcess || v111 == IoGetCurrentProcess())
        && (!RefsStatusBreakForImage
         || (v112 = IoGetCurrentProcess(),
             v113 = (const char *)PsGetProcessImageFileName(v112),
             !_strnicmp(&RefsStatusBreakForImage, v113, 0xFu))) )
      {
        __int2c();
      }
    }
    v40 = 32LL
        * (((unsigned __int16)_InterlockedExchangeAdd((volatile signed __int32 *)&RefsStatusNextQueueEntry, 1u) + 1)
         & 0xFFF);
    CurrentThread = KeGetCurrentThread();
    *(unsigned int *)((char *)&RefsStatusQueue + v40 + 24) = 873;
    goto LABEL_402;
  }
  if ( !(_DWORD)Length )
  {
    *((_QWORD *)v5 + 86) = 8;
    v48 = *((_QWORD *)v5 + 1);
    if ( (v48 & 0x100000000LL) != 0 )
    {
      *((_QWORD *)v5 + 1) = v48 | 0x200000000LL;
      return 0;
    }
    else
    {
      if ( *(_BYTE *)(*((_QWORD *)v5 + 8) + 10304LL) && *((__int64 *)v5 + 86) > 23 )
        RefsIoPerfCollectReadWriteData(*((struct _VCB **)v5 + 8), Irp, v5, a2);
      *((_QWORD *)v5 + 1) |= 0x8000uLL;
      *((_DWORD *)a2 + 199) &= ~1u;
      RefsCompleteRequest(v5, Irp, 0);
      return 0;
    }
  }
  v49 = v121;
  LOBYTE(v49) = v121 & 1;
  v121 = v49;
  if ( *(_BYTE *)(v45 + 10304) )
  {
    PerformanceCounter = *(LARGE_INTEGER *)((char *)v5 + 688);
    if ( PerformanceCounter.QuadPart <= 23 )
    {
      PerformanceCounter = KeQueryPerformanceCounter(0);
      LOBYTE(v49) = v121;
      LODWORD(Length) = v124;
      v45 = v126;
    }
    *((LARGE_INTEGER *)v5 + 86) = PerformanceCounter;
    v51 = v119;
    if ( v119 || (_BYTE)v118 )
      v52 = 0;
    else
      v52 = 2;
    *((_BYTE *)a2 + 56) = v49 | v52 | (4 * (v150 | 4));
    v47 = v123;
  }
  else
  {
    v51 = v119;
  }
  if ( (v130->Flags & 0x20000000) != 0 )
  {
    *((_BYTE *)a2 + 56) |= 1u;
    return RefsMinstoreRead(v5, a2, Irp, (unsigned __int64)LowLimit);
  }
  v120 &= 2u;
  if ( (*(_DWORD *)(FsContext + 152) & 0x20) == 0 )
  {
    LOBYTE(v121) = 1;
    *((_QWORD *)v5 + 1) |= 1uLL;
    *((_BYTE *)a2 + 56) |= 1u;
  }
  if ( _bittest64((const signed __int64 *)v5 + 1, 0x27u) )
    *(_DWORD *)a2 |= 0x80u;
  if ( v149 != 4 )
  {
    v133 = FsContext;
    v116 = 0;
    LODWORD(CurrentStackLocation) = 176;
    if ( v51 )
    {
      v61 = (_DWORD *)(*(_QWORD *)(v45 + 808)
                     + ((unsigned __int64)(KeGetCurrentProcessorNumber() % RefsNumberProcessors) << 6));
      if ( ((__int64)v127->spacer.Resource & 0x100LL) == 0
        && ((v62 = *(_WORD *)(FsContext + 216), v62 == 128) || v62 == 176) )
      {
        ++v61[2];
        v61[3] += Length;
      }
      else
      {
        ++v61[8];
        v61[9] += Length;
      }
    }
    else if ( (_BYTE)v118 )
    {
LABEL_170:
      *((_QWORD *)&v135 + 1) = 0x100000000LL;
      v136 = 0;
      TopLevelIrp = IoGetTopLevelIrp();
      if ( HIBYTE(TopLevelIrp->Type) && (*((_DWORD *)TopLevelIrp->MdlAddress->Process + 1) & 0x200) == 0 )
        LOBYTE(TopLevelIrp->Type) = 0;
      if ( v119 )
      {
        if ( !*(_QWORD *)(FsContext + 16)
          || (unsigned __int8)ExIsFastResourceHeld(*(_QWORD *)(*(_QWORD *)(FsContext + 136) + 96LL)) )
        {
          if ( *(_DWORD *)(FsContext + 296) != 3 )
            goto LABEL_228;
          v80 = *(_WORD *)(FsContext + 216);
          if ( v80 != 128 && v80 != 176 )
            goto LABEL_228;
LABEL_447:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              29,
              WPP_78e3b6b3f5653fb4a422c7659bfeaffe_Traceguids,
              3221226659LL);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(-1073740637, v5, "Read.c", 0x52Eu);
          RefsRaiseStatusInternal(v5, -1073740637, v64);
LABEL_454:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              31,
              WPP_78e3b6b3f5653fb4a422c7659bfeaffe_Traceguids,
              (unsigned int)CurrentStackLocation);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug((NTSTATUS)CurrentStackLocation, v5, "Read.c", 0x54Du);
          RefsRaiseStatusInternal(v5, (int)CurrentStackLocation, v64);
          __debugbreak();
          JUMPOUT(0x1400BC59ELL);
        }
        v116 = v124;
        RefsAcquireRangeLock(
          v5,
          *(struct _SCB_NONPAGED **)(FsContext + 248),
          v132,
          (unsigned int)v124,
          0,
          (struct REFS_IO_CONTEXT *)((char *)a2 + 32));
        *((_DWORD *)v5 + 1) |= 0x40u;
        v132 = FsContext;
        RefsAcquireResourceShared(v5, FsContext, 1);
        v46 |= 0x14u;
        LOBYTE(v115) = v46;
        if ( *(_DWORD *)(FsContext + 296) != 3 || (v79 = *(_WORD *)(FsContext + 216), v79 != 128) && v79 != 176 )
        {
          if ( *(_WORD *)FsContext == 2053 && *(_QWORD *)(FsContext + 432) && *(_WORD *)(FsContext + 260) )
            *((_QWORD *)v5 + 1) |= 0x10000000000uLL;
LABEL_228:
          v81 = *(_DWORD *)(FsContext + 300);
          LODWORD(CurrentStackLocation) = (v81 & 0x4000) != 0 ? 0xC000026E : 0;
          v117 = (int)CurrentStackLocation;
          if ( (v81 & 0x40) != 0 )
          {
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
            {
              LODWORD(CurrentStackLocation) = -1073741533;
            }
            else
            {
              LODWORD(CurrentStackLocation) = -1073741533;
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                30,
                WPP_78e3b6b3f5653fb4a422c7659bfeaffe_Traceguids,
                3221225763LL);
            }
            if ( (_BYTE)RefsStatusDebugEnabled )
              RefsStatusDebug(-1073741533, 0, "Read.c", 0x545u);
            v117 = -1073741533;
            goto LABEL_454;
          }
          if ( (v81 & 0x4000) != 0 )
            goto LABEL_454;
          if ( (*(_DWORD *)(FsContext + 152) & 0x20) == 0 )
          {
            if ( (v46 & 0x10) == 0 )
            {
              v124 = FsContext;
              LOBYTE(v64) = 1;
              RefsAcquireResourceShared(v5, FsContext, v64);
              v46 |= 0x18u;
              LOBYTE(v115) = v46;
            }
            RefsUpdateScbFromAttribute(v5, (struct _SCB *)FsContext, 0);
            if ( (v46 & 8) != 0 )
            {
              v148 = FsContext;
              RefsReleaseResource(v5, FsContext);
              v46 &= 0xE7u;
              LOBYTE(v115) = v46;
            }
          }
          if ( v149 != 2 )
          {
            v87 = v119;
            goto LABEL_274;
          }
          v140[0] = a2;
          v140[1] = FsContext;
          v140[2] = v134;
          v141 = (unsigned __int8)v46 >> 7;
          *((_QWORD *)v5 + 18) = v140;
          RangeFromEof = FsRtlCheckOplock(
                           (POPLOCK)(FsContext + 88),
                           Irp,
                           v5,
                           RefsOplockComplete,
                           RefsCommonRead_::_210_::_lambda_1_::_lambda_invoker_cdecl_);
          v117 = RangeFromEof;
          v82 = (unsigned __int8)v46;
          LOBYTE(v82) = v46 & 0x7F;
          v46 = v46 & 0x7F | ((_BYTE)v141 << 7);
          LOBYTE(v115) = v46;
          if ( RangeFromEof )
          {
            v83 = 0;
            v5 = 0;
            a2 = 0;
LABEL_347:
            v94 = v116;
LABEL_348:
            if ( v83 )
            {
              if ( !v119 )
              {
                v101 = v120;
                if ( v120 )
                {
                  v102 = (RangeFromEof & 0xC0000000) == 0xC0000000 ? 0LL : v83->IoStatus.Information;
                  v103 = *(_QWORD *)v131;
                  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v131 + 48LL) + 104LL) = v102 + LowLimit[0];
                  v101 = v120;
                }
                else
                {
                  v103 = *(_QWORD *)v131;
                }
                if ( RangeFromEof >= 0 && v101 )
                  RefsUpdateFileTimestampsForAccess(
                    *(struct _FILE_OBJECT **)(v103 + 48),
                    *(struct _FCB **)(FsContext + 136),
                    v123,
                    v103);
              }
              RefsCleanupTransaction(v5, RangeFromEof, 0);
            }
            if ( (v46 & 4) != 0 )
            {
              *((_DWORD *)v5 + 1) &= ~0x40u;
              RefsReleaseRangeLock(
                *(struct _SCB_NONPAGED **)(FsContext + 248),
                LowLimit[0],
                v94,
                0,
                (struct REFS_IO_CONTEXT *)((char *)a2 + 32));
            }
            if ( (v46 & 1) != 0 )
            {
              if ( v46 >= 0 )
              {
                v138 = FsContext;
                v104 = FsContext;
                if ( *(_WORD *)FsContext != 2050 )
                  v104 = *(_QWORD *)(FsContext + 136);
                v105 = *(_QWORD *)(v104 + 96);
                if ( !--DWORD2(v135) )
                {
                  *((_QWORD *)&v135 + 1) &= 0xFFFFFFFD00000000uLL;
                  ExReleaseFastResource(v105, v134);
                }
              }
              else
              {
                v137 = FsContext;
                RefsReleasePagingFastResource(v82, FsContext, (char *)a2 + 720);
              }
            }
            if ( (v46 & 0x10) != 0 )
            {
              v139 = FsContext;
              RefsReleaseResource(v5, FsContext);
            }
            HIDWORD(v135) &= ~1u;
            RefsCompleteReadWriteRequest(v5, a2, v83, RangeFromEof);
            return (unsigned int)RangeFromEof;
          }
          if ( *(_BYTE *)(FsContext + 5) )
          {
LABEL_262:
            v87 = v119;
            if ( !v119 )
            {
              v88 = *(FILE_LOCK **)(FsContext + 384);
              if ( v88 )
              {
                if ( !FsRtlCheckLockForReadAccess(v88, Irp) )
                {
                  v82 = (__int64)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
                    || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
                  {
                    RangeFromEof = -1073741740;
                  }
                  else
                  {
                    RangeFromEof = -1073741740;
                    WPP_SF_d(
                      WPP_GLOBAL_Control->AttachedDevice,
                      32,
                      WPP_78e3b6b3f5653fb4a422c7659bfeaffe_Traceguids,
                      3221225556LL);
                  }
                  if ( (_BYTE)RefsStatusDebugEnabled )
                    RefsStatusDebug(-1073741740, 0, "Read.c", 0x5B0u);
LABEL_272:
                  v117 = RangeFromEof;
                  goto LABEL_346;
                }
              }
            }
LABEL_274:
            RangeFromEof = RefsSetReadRangeFromEof(FsContext, LowLimit, v150);
            v117 = RangeFromEof;
            if ( RangeFromEof < 0 )
            {
              *((_QWORD *)v5 + 86) = 18;
              goto LABEL_346;
            }
            if ( v87 && IoGetTopLevelIrp()->MdlAddress == (PMDL)2 )
              *((_QWORD *)v5 + 1) |= 0x800uLL;
            v90 = v129;
            v91 = *(_DWORD *)(FsContext + 152);
            if ( (v91 & 8) != 0 && (v91 & 0x40) == 0 )
            {
              if ( !(_BYTE)v118 )
                goto LABEL_343;
              if ( (v46 & 0x10) == 0 )
              {
                LOBYTE(v89) = 1;
                RefsAcquireResourceShared(v5, FsContext, v89);
                v46 |= 0x18u;
                LOBYTE(v115) = v46;
              }
              v92 = *(_DWORD *)(FsContext + 152);
              if ( (v92 & 8) != 0 && (v92 & 0x40) == 0 )
              {
                *((_QWORD *)v5 + 86) = 16;
                RefsNonCachedResidentRead(v5, Irp, (struct _SCB *)FsContext);
                Irp->IoStatus.Information = v129;
                RangeFromEof = 0;
                v117 = 0;
                goto LABEL_346;
              }
              if ( (v46 & 8) != 0 )
              {
                RefsReleaseResource(v5, FsContext);
                v46 &= 0xE7u;
                LOBYTE(v115) = v46;
              }
            }
            if ( (_BYTE)v118 )
            {
              if ( (_DWORD)v90 )
              {
                if ( (*(_DWORD *)(v126 + 6568) & 1) != 0 && IoGetIoPriorityHint(Irp) > IoPriorityLow )
                {
                  if ( ((v93 = *(_WORD *)(FsContext + 216), v93 == 128) || v93 == 176) && !*(_WORD *)(FsContext + 224)
                    || (v82 = 160, v93 == 160) )
                  {
                    RefsHeatLogIo(Irp, v127);
                  }
                }
                if ( (v46 & 0x20) == 0
                  || (v82 = 2053, *(_WORD *)FsContext == 2053)
                  && *(_QWORD *)(FsContext + 432)
                  && *(_WORD *)(FsContext + 260) )
                {
                  if ( (v46 & 0x20) != 0 )
                  {
                    v97 = v90;
                  }
                  else
                  {
                    v95 = *(_DWORD *)(*((_QWORD *)v5 + 8) + 276LL);
                    v96 = v95 + v90 - 1;
                    v82 = (unsigned int)-v95;
                    v97 = v82 & v96;
                  }
                  if ( !(_BYTE)v121 )
                  {
                    if ( v119 )
                    {
                      if ( (v46 & 0x10) != 0 )
                        RefsSetIoContextAsync(
                          (struct _IRP_CONTEXT *)v82,
                          a2,
                          *(struct _FAST_ERESOURCE **)(FsContext + 8),
                          0,
                          0,
                          *(struct _SCB_NONPAGED **)(FsContext + 248),
                          LowLimit[0],
                          v116,
                          0,
                          v90,
                          v114,
                          (struct _SCB *)FsContext,
                          v123);
                      else
                        RefsSetIoContextAsync(
                          0,
                          a2,
                          0,
                          0,
                          0,
                          0,
                          LowLimit[0],
                          0,
                          0,
                          v90,
                          v114,
                          (struct _SCB *)FsContext,
                          v123);
                    }
                    else
                    {
                      v98 = (struct REFS_IO_CONTEXT *)((char *)a2 + 720);
                      if ( v46 >= 0 )
                        v98 = (struct _MS_FAST_RESOURCE_OWNER_ENTRY *)v134;
                      RefsSetIoContextAsync(
                        (struct _IRP_CONTEXT *)LowLimit[0],
                        a2,
                        0,
                        *(struct _MS_FAST_RESOURCE **)(FsContext + 16),
                        v98,
                        0,
                        LowLimit[0],
                        0,
                        0,
                        v90,
                        v114,
                        (struct _SCB *)FsContext,
                        v123);
                    }
                  }
                  v99 = v46 & 0xBF;
                  v46 = v46 & 0xBF | (*((_QWORD *)v5 + 1) >> 26) & 0x40;
                  LOBYTE(v115) = v99 | (*((_QWORD *)v5 + 1) >> 26) & 0x40;
                  RangeFromEof = RefsNonCachedIo(v5, a2, Irp, FsContext, LowLimit[0], v97, 0);
                  v117 = RangeFromEof;
                }
                else
                {
                  if ( (*((_QWORD *)v5 + 1) & 0x8000000000LL) != 0 )
                  {
                    v82 = (__int64)WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
                      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
                    {
                      RangeFromEof = -1073741811;
                    }
                    else
                    {
                      RangeFromEof = -1073741811;
                      WPP_SF_d(
                        WPP_GLOBAL_Control->AttachedDevice,
                        33,
                        WPP_78e3b6b3f5653fb4a422c7659bfeaffe_Traceguids,
                        3221225485LL);
                    }
                    if ( (_BYTE)RefsStatusDebugEnabled )
                    {
                      RefsStatusDebug(-1073741811, 0, "Read.c", 0x632u);
                      v117 = -1073741811;
                      goto LABEL_346;
                    }
                    goto LABEL_272;
                  }
                  if ( !(_BYTE)v121 )
                  {
                    if ( (v46 & 4) != 0 )
                    {
                      *((_DWORD *)v5 + 1) &= ~0x40u;
                      v46 &= ~4u;
                      LOBYTE(v115) = v46;
                      v94 = v116;
                      RefsReleaseRangeLock(
                        *(struct _SCB_NONPAGED **)(FsContext + 248),
                        LowLimit[0],
                        v116,
                        0,
                        (struct REFS_IO_CONTEXT *)((char *)a2 + 32));
                    }
                    else
                    {
                      v94 = v116;
                    }
                    if ( (v46 & 0x10) != 0 )
                    {
                      v130 = (struct _FILE_OBJECT *)FsContext;
                      RefsReleaseResource(v5, FsContext);
                      v46 &= 0xE7u;
                      LOBYTE(v115) = v46;
                    }
                    RangeFromEof = RefsPostRequest(v5, Irp, 0, 0);
                    v117 = RangeFromEof;
                    v83 = 0;
                    v5 = 0;
                    a2 = 0;
                    goto LABEL_348;
                  }
                  RefsNonCachedNonAlignedIo(v5, a2, Irp, (struct _SCB *)FsContext, LowLimit[0], v90);
                }
                if ( RangeFromEof == 259 )
                {
                  v83 = 0;
                  v5 = 0;
                  a2 = 0;
                  v46 &= 0xEAu;
                  LOBYTE(v115) = v46;
                  goto LABEL_347;
                }
                if ( RangeFromEof >= 0 )
                  *((_BYTE *)a2 + 56) |= 1u;
              }
              RangeFromEof = Irp->IoStatus.Status;
              v117 = RangeFromEof;
              if ( RangeFromEof < 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_dd(
                    WPP_GLOBAL_Control->AttachedDevice,
                    34,
                    WPP_78e3b6b3f5653fb4a422c7659bfeaffe_Traceguids,
                    3221225705LL,
                    RangeFromEof);
                }
                *((_DWORD *)v5 + 4) = RangeFromEof;
                if ( (_BYTE)RefsStatusDebugEnabled )
                  RefsStatusDebug(RangeFromEof, v5, "Read.c", 0x6F0u);
                v100 = FsRtlNormalizeNtstatus(RangeFromEof, -1073741591);
                ExRaiseStatus(v100);
              }
              Irp->IoStatus.Information = v90;
              goto LABEL_346;
            }
LABEL_343:
            RangeFromEof = RefsCachedRead(
                             v5,
                             a2,
                             v130,
                             Irp,
                             (struct DataSCB *)FsContext,
                             (struct _MS_FAST_RESOURCE_OWNER_ENTRY *)v134,
                             (union _LARGE_INTEGER)LowLimit[0],
                             v90,
                             (union _REFS_READ_FLAGS *)&v115);
            v117 = RangeFromEof;
            if ( RangeFromEof == 259 )
            {
              v83 = 0;
              v5 = 0;
              a2 = 0;
              v46 = v115;
              goto LABEL_347;
            }
            v46 = v115;
LABEL_346:
            v83 = v125;
            goto LABEL_347;
          }
          v84 = *(_QWORD *)(FsContext + 144);
          if ( (*(_DWORD *)(v84 + 24) & 0x4000005) == 1
            && *(_WORD *)FsContext == 2053
            && (*(_DWORD *)(FsContext + 300) & 0x40) == 0
            && *(char *)(*(_QWORD *)(FsContext + 136) + 8LL) >= 0 )
          {
            if ( (*(_DWORD *)(FsContext + 152) & 0x20) == 0 )
              goto LABEL_252;
            if ( FsRtlOplockIsFastIoPossible((POPLOCK)(FsContext + 88)) )
            {
              if ( *(__int16 *)(FsContext + 256) >= 0 )
              {
                v86 = *(_QWORD *)(FsContext + 384);
                if ( (!v86 || !*(_BYTE *)(v86 + 16))
                  && (*(_DWORD *)(v84 + 24) & 0x2000000) == 0
                  && (*(_BYTE *)(*(_QWORD *)(FsContext + 136) + 8LL) & 0x20) == 0 )
                {
                  v85 = 1;
                  goto LABEL_261;
                }
              }
LABEL_252:
              v85 = 2;
LABEL_261:
              *(_BYTE *)(FsContext + 5) = v85;
              goto LABEL_262;
            }
          }
          v85 = 0;
          goto LABEL_261;
        }
LABEL_440:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            28,
            WPP_78e3b6b3f5653fb4a422c7659bfeaffe_Traceguids,
            3221226659LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073740637, v5, "Read.c", 0x518u);
        RefsRaiseStatusInternal(v5, -1073740637, v64);
        goto LABEL_447;
      }
      v122 = 0;
      if ( (_BYTE)v118 )
      {
        LOBYTE(CurrentStackLocation) = 0;
      }
      else
      {
        if ( !*(_QWORD *)(*(_QWORD *)(FsContext + 248) + 16LL) )
          goto LABEL_198;
        LODWORD(CurrentStackLocation) = 1;
      }
      if ( !(_BYTE)v118 )
        goto LABEL_187;
      if ( !*(_QWORD *)(*(_QWORD *)(FsContext + 248) + 8LL) || *(_DWORD *)(FsContext + 344) )
      {
        if ( !(_BYTE)v121 )
        {
          v65 = *(_DWORD *)(FsContext + 152);
          if ( ((v65 & 8) == 0 || (v65 & 0x40) != 0) && (v46 & 0x20) == 0 )
          {
            v142 = FsContext;
            v66 = RefsAcquirePagingFastResourceShared(v118, FsContext, (char *)a2 + 720);
            v68 = v66;
            v122 = v66;
            if ( v66 )
            {
              v46 |= 0x80u;
              LOBYTE(v115) = v46;
            }
            goto LABEL_188;
          }
        }
LABEL_187:
        v143 = FsContext;
        v69 = RefsAcquirePagingFastResourceShared(v118, FsContext, v134);
        v68 = v69;
        v122 = v69;
LABEL_188:
        if ( !(_DWORD)v68
          || (!(_BYTE)CurrentStackLocation || *(_QWORD *)(*(_QWORD *)(FsContext + 248) + 16LL))
          && (!(_BYTE)v118 || !*(_QWORD *)(*(_QWORD *)(FsContext + 248) + 8LL) || *(_DWORD *)(FsContext + 344)) )
        {
LABEL_200:
          if ( (_DWORD)v68 )
          {
            v46 |= 1u;
            LOBYTE(v115) = v46;
            if ( *(_DWORD *)(FsContext + 296) != 3 || (v73 = *(_WORD *)(FsContext + 216), v73 != 128) && v73 != 176 )
            {
              if ( (*((_DWORD *)v123 + 1) & 0x8000) == 0 )
              {
                if ( RefsIsFileOpen(v127) )
                {
                  if ( !(_BYTE)v74 || !*(_QWORD *)(*(_QWORD *)(FsContext + 248) + 8LL) || *(_DWORD *)(FsContext + 344) )
                    goto LABEL_228;
                  v75 = v132;
                  if ( *(_WORD *)FsContext == 2053 && *(_QWORD *)(FsContext + 432) )
                  {
                    v76 = v124;
                    if ( *(_WORD *)(FsContext + 260) )
                    {
                      v77 = 1 << *(_DWORD *)(*(_QWORD *)(FsContext + 144) + 552LL);
                      v74 = -(__int64)v77;
                      v75 = v74 & v132;
                      v76 = (v74 & (v77 + v132 + v124 - 1)) - (v74 & v132);
                    }
                  }
                  else
                  {
                    v76 = v124;
                  }
                  v78 = RefsCacheCoherencyFlush(
                          v5,
                          (struct _IRP *)v74,
                          (struct _SCB *)FsContext,
                          v75,
                          v76,
                          0,
                          *(_DWORD *)(FsContext + 180) == 0);
                  LODWORD(CurrentStackLocation) = v78;
                  v117 = v78;
                  if ( v78 >= 0 )
                    goto LABEL_228;
                  goto LABEL_433;
                }
LABEL_426:
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    26,
                    WPP_78e3b6b3f5653fb4a422c7659bfeaffe_Traceguids,
                    3221225768LL);
                }
                if ( (_BYTE)RefsStatusDebugEnabled )
                  RefsStatusDebug(-1073741528, v5, "Read.c", 0x49Au);
                RefsRaiseStatusInternal(v5, -1073741528, v64);
LABEL_433:
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    27,
                    WPP_78e3b6b3f5653fb4a422c7659bfeaffe_Traceguids,
                    (unsigned int)v78);
                }
                if ( (_BYTE)RefsStatusDebugEnabled )
                  RefsStatusDebug((NTSTATUS)CurrentStackLocation, v5, "Read.c", 0x4CDu);
                RefsRaiseStatusInternal(v5, (int)CurrentStackLocation, v64);
                goto LABEL_440;
              }
LABEL_419:
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  25,
                  WPP_78e3b6b3f5653fb4a422c7659bfeaffe_Traceguids,
                  3221225768LL);
              }
              if ( (_BYTE)RefsStatusDebugEnabled )
                RefsStatusDebug(-1073741528, v5, "Read.c", 0x496u);
              RefsRaiseStatusInternal(v5, -1073741528, v67);
              goto LABEL_426;
            }
LABEL_412:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                24,
                WPP_78e3b6b3f5653fb4a422c7659bfeaffe_Traceguids,
                3221226659LL);
            }
            if ( (_BYTE)RefsStatusDebugEnabled )
              RefsStatusDebug(-1073740637, v5, "Read.c", 0x48Eu);
            RefsRaiseStatusInternal(v5, -1073740637, v67);
            goto LABEL_419;
          }
LABEL_405:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              23,
              WPP_78e3b6b3f5653fb4a422c7659bfeaffe_Traceguids,
              3221225688LL);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(-1073741608, v5, "Read.c", 0x483u);
          RefsRaiseStatusInternal(v5, -1073741608, v67);
          goto LABEL_412;
        }
        if ( v46 >= 0 )
        {
          v145 = FsContext;
          v70 = (char *)v134;
        }
        else
        {
          v144 = FsContext;
          v70 = (char *)a2 + 720;
        }
        RefsReleasePagingFastResource(v68, FsContext, v70);
        v146 = FsContext;
        v72 = RefsAcquirePagingFastResourceExclusive(v71, FsContext, v134, (unsigned __int8)v121);
        LOBYTE(v115) = v46 | 2;
        v46 = v46 & 0x7D | 2;
LABEL_199:
        LODWORD(v68) = v72;
        LOBYTE(v115) = v46;
        v122 = v72;
        goto LABEL_200;
      }
LABEL_198:
      v147 = FsContext;
      v72 = RefsAcquirePagingFastResourceExclusive(v118, FsContext, v134, (unsigned __int8)v121);
      v46 |= 2u;
      goto LABEL_199;
    }
    *(_DWORD *)(FsContext + 184) = 0;
    goto LABEL_170;
  }
  if ( (*((_DWORD *)v47 + 1) & 0x100) == 0 )
  {
    v53 = *(_QWORD *)(FsContext + 32);
    if ( v53 <= QuadPart )
    {
      RefsCompleteReadWriteRequest(v5, a2, Irp, -1073741807);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_78e3b6b3f5653fb4a422c7659bfeaffe_Traceguids, 3221225489LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        if ( RefsStatusDisplayStatus == -1073741807 )
          DbgPrintEx(0x95u, 0, "th%p %x %s:%i\n", KeGetCurrentThread(), -1073741807, "Read.c", 977);
        v54 = RefsStatusBreakOnWin32Error;
        if ( RefsStatusBreakOnStatus == -1073741807
          || RefsStatusBreakOnWin32Error && v54 == RtlNtStatusToDosErrorNoTeb(-1073741807) )
        {
          v55 = RefsStatusBreakForProcess;
          if ( !RefsStatusBreakForThread
            || RefsStatusBreakForThread == KeGetCurrentThread()
            && (!RefsStatusBreakForProcess || v55 == IoGetCurrentProcess())
            && (!RefsStatusBreakForImage
             || (v56 = IoGetCurrentProcess(),
                 v57 = (const char *)PsGetProcessImageFileName(v56),
                 !_strnicmp(&RefsStatusBreakForImage, v57, 0xFu))) )
          {
            __int2c();
          }
        }
        v58 = 32LL
            * (((unsigned __int16)_InterlockedExchangeAdd((volatile signed __int32 *)&RefsStatusNextQueueEntry, 1u) + 1)
             & 0xFFF);
        *(_QWORD *)((char *)&RefsStatusQueue + v58) = KeGetCurrentThread();
        *(unsigned int *)((char *)&RefsStatusQueue + v58 + 8) = -1073741807;
        *(_QWORD *)((char *)&RefsStatusQueue + v58 + 16) = "Read.c";
        *(unsigned int *)((char *)&RefsStatusQueue + v58 + 24) = 977;
      }
      return 3221225489LL;
    }
    if ( v53 < v44 )
      LODWORD(Length) = v53 - QuadPart;
  }
  v59 = RefsVolumeDasdIo(v5, a2, Irp, (struct _SCB *)FsContext, v47, QuadPart, Length);
  if ( v59 >= 0 )
    RefsUpdateFileTimestampsForAccess(v130, v127, v123, v60);
  if ( v120 && !v119 && v59 >= 0 )
    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v131 + 48LL) + 104LL) = QuadPart + Irp->IoStatus.Information;
  if ( (_BYTE)v121 )
    RefsCompleteReadWriteRequest(v5, a2, Irp, v59);
  return (unsigned int)v59;
}

```

## disassembly

```asm
0x1400ba4d0  mov     [rsp+arg_8], rdx
0x1400ba4d5  mov     [rsp+arg_0], rcx
0x1400ba4da  push    rbx
0x1400ba4db  push    rsi
0x1400ba4dc  push    rdi
0x1400ba4dd  push    r12
0x1400ba4df  push    r13
0x1400ba4e1  push    r14
0x1400ba4e3  push    r15
0x1400ba4e5  sub     rsp, 1D0h
0x1400ba4ec  mov     r14, r8
0x1400ba4ef  mov     [rsp+208h+var_160], r8
0x1400ba4f7  mov     r13, rdx
0x1400ba4fa  mov     rbx, rcx
0x1400ba4fd  xorps   xmm0, xmm0
0x1400ba500  xor     eax, eax
0x1400ba502  movups  [rsp+208h+var_108], xmm0
0x1400ba50a  movups  [rsp+208h+var_F8], xmm0
0x1400ba512  movups  [rsp+208h+var_E8], xmm0
0x1400ba51a  movups  [rsp+208h+var_D8], xmm0
0x1400ba522  movups  [rsp+208h+var_C8], xmm0
0x1400ba52a  mov     [rsp+208h+var_B8], rax
0x1400ba532  mov     [rsp+208h+var_198], eax
0x1400ba536  and     qword ptr [rcx+8], 0FFFFFFFFFFFFFFF7h
0x1400ba53b  mov     rcx, [rcx+8]
0x1400ba53f  mov     [rsp+208h+var_180], rcx
0x1400ba547  mov     rsi, [r8+0B8h]
0x1400ba54e  mov     qword ptr [rsp+208h+var_128], rsi
0x1400ba556  mov     r9, [rsi+30h]
0x1400ba55a  mov     [rsp+208h+var_130], r9
0x1400ba562  mov     rdi, [r9+18h]
0x1400ba566  test    rdi, rdi
0x1400ba569  jz      short loc_1400BA5C9
0x1400ba56b  mov     r10, [rdi+90h]
0x1400ba572  mov     [rsp+208h+var_158], r10
0x1400ba57a  mov     rdx, [r9+20h]
0x1400ba57e  mov     [rsp+208h+var_170], rdx
0x1400ba586  mov     eax, [r10+18h]
0x1400ba58a  test    al, 1
0x1400ba58c  jnz     short loc_1400BA5A9
0x1400ba58e  test    rdx, rdx
0x1400ba591  jz      loc_1400BC225
0x1400ba597  cmp     byte ptr [rdx+50h], 4
0x1400ba59b  jnz     loc_1400BC225
0x1400ba5a1  test    al, 2
0x1400ba5a3  jz      loc_1400BC225
0x1400ba5a9  mov     r11, [rdi+88h]
0x1400ba5b0  mov     [rsp+208h+var_150], r11
0x1400ba5b8  test    rdx, rdx
0x1400ba5bb  jnz     short loc_1400BA5C2
0x1400ba5bd  mov     r8b, 5
0x1400ba5c0  jmp     short loc_1400BA5EC
0x1400ba5c2  movzx   r8d, byte ptr [rdx+50h]
0x1400ba5c7  jmp     short loc_1400BA5EC
0x1400ba5c9  xor     r10d, r10d
0x1400ba5cc  mov     [rsp+208h+var_158], r10
0x1400ba5d4  xor     r11d, r11d
0x1400ba5d7  mov     [rsp+208h+var_150], r11
0x1400ba5df  xor     edx, edx
0x1400ba5e1  mov     [rsp+208h+var_170], rdx
0x1400ba5e9  mov     r8b, 1
0x1400ba5ec  mov     byte ptr [rsp+208h+arg_10], r8b
0x1400ba5f4  mov     eax, [r10+18h]
0x1400ba5f8  test    al, 1
0x1400ba5fa  jnz     loc_1400BA82E
0x1400ba600  cmp     r8b, 4
0x1400ba604  jz      loc_1400BA82E
0x1400ba60a  test    rbx, rbx
0x1400ba60d  jz      short loc_1400BA683
0x1400ba60f  bt      rcx, 20h ; ' '
0x1400ba614  jnb     short loc_1400BA629
0x1400ba616  mov     rax, 200000000h
0x1400ba620  or      rcx, rax
0x1400ba623  mov     [rbx+8], rcx
0x1400ba627  jmp     short loc_1400BA694
0x1400ba629  test    rbx, rbx
0x1400ba62c  jz      short loc_1400BA683
0x1400ba62e  bts     rcx, 0Fh
0x1400ba633  mov     [rbx+8], rcx
0x1400ba637  movzx   eax, byte ptr [rbx+28h]
0x1400ba63b  cmp     al, 12h
0x1400ba63d  ja      short loc_1400BA67B
0x1400ba63f  mov     ecx, 4021Dh
0x1400ba644  bt      ecx, eax
0x1400ba647  jnb     short loc_1400BA67B
0x1400ba649  mov     rax, [rbx+40h]
0x1400ba64d  test    rax, rax
0x1400ba650  jz      short loc_1400BA67B
0x1400ba652  movzx   eax, byte ptr [rax+2840h]
0x1400ba659  test    al, al
0x1400ba65b  jz      short loc_1400BA67B
0x1400ba65d  test    dword ptr [rbx+4], 400h
0x1400ba664  jnz     short loc_1400BA67B
0x1400ba666  mov     eax, [rbx+8]
0x1400ba669  bt      rax, 10h
0x1400ba66e  jb      short loc_1400BA67B
0x1400ba670  mov     qword ptr [rbx+2B0h], 7
0x1400ba67b  and     dword ptr [r13+31Ch], 0FFFFFFFEh
0x1400ba683  mov     r8d, 0C000026Eh; Status
0x1400ba689  mov     rdx, r14; Irp
0x1400ba68c  mov     rcx, rbx; struct _IRP_CONTEXT *
0x1400ba68f  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x1400ba694  lea     r12, WPP_GLOBAL_Control
0x1400ba69b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ba6a2  cmp     rcx, r12
0x1400ba6a5  jz      short loc_1400BA6D1
0x1400ba6a7  test    dword ptr [rcx+2Ch], 100h
0x1400ba6ae  jz      short loc_1400BA6D1
0x1400ba6b0  cmp     byte ptr [rcx+29h], 4
0x1400ba6b4  jb      short loc_1400BA6D1
0x1400ba6b6  mov     edx, 12h
0x1400ba6bb  mov     r9d, 0C000026Eh
0x1400ba6c1  lea     r8, WPP_78e3b6b3f5653fb4a422c7659bfeaffe_Traceguids
0x1400ba6c8  mov     rcx, [rcx+18h]
0x1400ba6cc  call    WPP_SF_d
0x1400ba6d1  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1400ba6d8  test    al, al
0x1400ba6da  jz      loc_1400BA824
0x1400ba6e0  mov     eax, cs:?RefsStatusDisplayStatus@@3JC; long volatile RefsStatusDisplayStatus
0x1400ba6e6  lea     r14, aReadC; "Read.c"
0x1400ba6ed  cmp     eax, 0C000026Eh
0x1400ba6f2  jnz     short loc_1400BA728
0x1400ba6f4  mov     r9, gs:188h
0x1400ba6fd  mov     dword ptr [rsp+208h+var_1D8], 314h
0x1400ba705  mov     [rsp+208h+var_1E0], r14
0x1400ba70a  mov     dword ptr [rsp+208h+PostIrpRoutine], eax
0x1400ba70e  lea     r8, aThPXSI; "th%p %x %s:%i\n"
0x1400ba715  xor     edx, edx; Level
0x1400ba717  mov     ecx, 95h; ComponentId
0x1400ba71c  call    cs:__imp_DbgPrintEx
0x1400ba723  nop     dword ptr [rax+rax+00h]
0x1400ba728  mov     ecx, cs:?RefsStatusBreakOnStatus@@3JC; long volatile RefsStatusBreakOnStatus
0x1400ba72e  mov     ebx, cs:?RefsStatusBreakOnWin32Error@@3KC; ulong volatile RefsStatusBreakOnWin32Error
0x1400ba734  cmp     ecx, 0C000026Eh
0x1400ba73a  jz      short loc_1400BA75D
0x1400ba73c  test    ebx, ebx
0x1400ba73e  jz      loc_1400BA7E0
0x1400ba744  mov     ecx, 0C000026Eh; Status
0x1400ba749  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1400ba750  nop     dword ptr [rax+rax+00h]
0x1400ba755  cmp     ebx, eax
0x1400ba757  jnz     loc_1400BA7E0
0x1400ba75d  mov     rcx, cs:?RefsStatusBreakForThread@@3REAU_KTHREAD@@EA; _KTHREAD * RefsStatusBreakForThread
0x1400ba764  mov     rbx, cs:?RefsStatusBreakForProcess@@3REAU_KPROCESS@@EA; _KPROCESS * RefsStatusBreakForProcess
0x1400ba76b  test    rcx, rcx
0x1400ba76e  jz      short loc_1400BA7DE
0x1400ba770  mov     rax, gs:188h
0x1400ba779  cmp     rcx, rax
0x1400ba77c  jnz     short loc_1400BA7E0
0x1400ba77e  test    rbx, rbx
0x1400ba781  jz      short loc_1400BA794
0x1400ba783  call    cs:__imp_IoGetCurrentProcess
0x1400ba78a  nop     dword ptr [rax+rax+00h]
0x1400ba78f  cmp     rbx, rax
0x1400ba792  jnz     short loc_1400BA7E0
0x1400ba794  cmp     cs:?RefsStatusBreakForImage@@3PADA, 0; char near * RefsStatusBreakForImage
0x1400ba79b  jz      short loc_1400BA7D8
0x1400ba79d  call    cs:__imp_IoGetCurrentProcess
0x1400ba7a4  nop     dword ptr [rax+rax+00h]
0x1400ba7a9  mov     rcx, rax
0x1400ba7ac  call    cs:__imp_PsGetProcessImageFileName
0x1400ba7b3  nop     dword ptr [rax+rax+00h]
0x1400ba7b8  mov     rdx, rax; Str2
0x1400ba7bb  mov     r8d, 0Fh; MaxCount
0x1400ba7c1  lea     rcx, ?RefsStatusBreakForImage@@3PADA; Str1
0x1400ba7c8  call    cs:__imp__strnicmp
0x1400ba7cf  nop     dword ptr [rax+rax+00h]
0x1400ba7d4  test    eax, eax
0x1400ba7d6  jnz     short loc_1400BA7E0
0x1400ba7d8  mov     eax, cs:?RefsStatusBreakForFsCtl@@3KC; ulong volatile RefsStatusBreakForFsCtl
0x1400ba7de  int     2Ch; Windows NT - assertion failure
0x1400ba7e0  mov     ecx, 1
0x1400ba7e5  lock xadd cs:?RefsStatusNextQueueEntry@@3KA, ecx; ulong RefsStatusNextQueueEntry
0x1400ba7ed  inc     ecx
0x1400ba7ef  and     ecx, 0FFFh
0x1400ba7f5  shl     rcx, 5
0x1400ba7f9  mov     rax, gs:188h
0x1400ba802  lea     r8, ?RefsStatusQueue@@3PAU_REFS_STATUS_DEBUG_QUEUE_ENTRY@@A; _REFS_STATUS_DEBUG_QUEUE_ENTRY near * RefsStatusQueue
0x1400ba809  mov     [rcx+r8], rax
0x1400ba80d  mov     dword ptr [rcx+r8+8], 0C000026Eh
0x1400ba816  mov     [rcx+r8+10h], r14
0x1400ba81b  mov     dword ptr [rcx+r8+18h], 314h
0x1400ba824  mov     eax, 0C000026Eh
0x1400ba829  jmp     loc_1400BC211
0x1400ba82e  mov     r15d, [r14+10h]
0x1400ba832  mov     ecx, r15d
0x1400ba835  and     ecx, 2
0x1400ba838  mov     [rsp+208h+var_188], ecx
0x1400ba83f  setnz   byte ptr [rsp+208h+arg_18]
0x1400ba847  and     r15b, 1
0x1400ba84b  mov     [rsp+208h+var_18C], r15d
0x1400ba850  mov     eax, [r9+50h]
0x1400ba854  mov     [rsp+208h+var_184], eax
0x1400ba85b  jz      loc_1400BAA98
0x1400ba861  test    dword ptr [rdi+98h], 1000000h
0x1400ba86b  jz      loc_1400BAA98
0x1400ba871  test    rbx, rbx
0x1400ba874  jz      short loc_1400BA8ED
0x1400ba876  mov     rcx, [rbx+8]
0x1400ba87a  bt      rcx, 20h ; ' '
0x1400ba87f  jnb     short loc_1400BA894
0x1400ba881  mov     rax, 200000000h
0x1400ba88b  or      rcx, rax
0x1400ba88e  mov     [rbx+8], rcx
0x1400ba892  jmp     short loc_1400BA8FE
0x1400ba894  test    rbx, rbx
0x1400ba897  jz      short loc_1400BA8ED
0x1400ba899  or      qword ptr [rbx+8], 8000h
0x1400ba8a1  movzx   eax, byte ptr [rbx+28h]
0x1400ba8a5  cmp     al, 12h
0x1400ba8a7  ja      short loc_1400BA8E5
0x1400ba8a9  mov     ecx, 4021Dh
0x1400ba8ae  bt      ecx, eax
0x1400ba8b1  jnb     short loc_1400BA8E5
0x1400ba8b3  mov     rax, [rbx+40h]
0x1400ba8b7  test    rax, rax
0x1400ba8ba  jz      short loc_1400BA8E5
0x1400ba8bc  movzx   eax, byte ptr [rax+2840h]
0x1400ba8c3  test    al, al
0x1400ba8c5  jz      short loc_1400BA8E5
0x1400ba8c7  test    dword ptr [rbx+4], 400h
0x1400ba8ce  jnz     short loc_1400BA8E5
0x1400ba8d0  mov     eax, [rbx+8]
0x1400ba8d3  bt      rax, 10h
0x1400ba8d8  jb      short loc_1400BA8E5
0x1400ba8da  mov     qword ptr [rbx+2B0h], 7
0x1400ba8e5  and     dword ptr [r13+31Ch], 0FFFFFFFEh
0x1400ba8ed  mov     r8d, 0C0000810h; Status
0x1400ba8f3  mov     rdx, r14; Irp
0x1400ba8f6  mov     rcx, rbx; struct _IRP_CONTEXT *
0x1400ba8f9  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x1400ba8fe  lea     r12, WPP_GLOBAL_Control
0x1400ba905  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ba90c  cmp     rcx, r12
0x1400ba90f  jz      short loc_1400BA93B
0x1400ba911  test    dword ptr [rcx+2Ch], 100h
0x1400ba918  jz      short loc_1400BA93B
0x1400ba91a  cmp     byte ptr [rcx+29h], 4
0x1400ba91e  jb      short loc_1400BA93B
0x1400ba920  mov     edx, 13h
0x1400ba925  mov     r9d, 0C0000810h
0x1400ba92b  lea     r8, WPP_78e3b6b3f5653fb4a422c7659bfeaffe_Traceguids
0x1400ba932  mov     rcx, [rcx+18h]
0x1400ba936  call    WPP_SF_d
0x1400ba93b  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1400ba942  test    al, al
0x1400ba944  jz      loc_1400BAA8E
0x1400ba94a  mov     eax, cs:?RefsStatusDisplayStatus@@3JC; long volatile RefsStatusDisplayStatus
0x1400ba950  lea     r14, aReadC; "Read.c"
0x1400ba957  cmp     eax, 0C0000810h
0x1400ba95c  jnz     short loc_1400BA992
0x1400ba95e  mov     r9, gs:188h
0x1400ba967  mov     dword ptr [rsp+208h+var_1D8], 32Ch
0x1400ba96f  mov     [rsp+208h+var_1E0], r14
0x1400ba974  mov     dword ptr [rsp+208h+PostIrpRoutine], eax
0x1400ba978  lea     r8, aThPXSI; "th%p %x %s:%i\n"
0x1400ba97f  xor     edx, edx; Level
0x1400ba981  mov     ecx, 95h; ComponentId
0x1400ba986  call    cs:__imp_DbgPrintEx
0x1400ba98d  nop     dword ptr [rax+rax+00h]
0x1400ba992  mov     ecx, cs:?RefsStatusBreakOnStatus@@3JC; long volatile RefsStatusBreakOnStatus
0x1400ba998  mov     ebx, cs:?RefsStatusBreakOnWin32Error@@3KC; ulong volatile RefsStatusBreakOnWin32Error
0x1400ba99e  cmp     ecx, 0C0000810h
0x1400ba9a4  jz      short loc_1400BA9C7
0x1400ba9a6  test    ebx, ebx
0x1400ba9a8  jz      loc_1400BAA4A
0x1400ba9ae  mov     ecx, 0C0000810h; Status
0x1400ba9b3  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1400ba9ba  nop     dword ptr [rax+rax+00h]
0x1400ba9bf  cmp     ebx, eax
0x1400ba9c1  jnz     loc_1400BAA4A
0x1400ba9c7  mov     rcx, cs:?RefsStatusBreakForThread@@3REAU_KTHREAD@@EA; _KTHREAD * RefsStatusBreakForThread
0x1400ba9ce  mov     rbx, cs:?RefsStatusBreakForProcess@@3REAU_KPROCESS@@EA; _KPROCESS * RefsStatusBreakForProcess
0x1400ba9d5  test    rcx, rcx
0x1400ba9d8  jz      short loc_1400BAA48
0x1400ba9da  mov     rax, gs:188h
0x1400ba9e3  cmp     rcx, rax
0x1400ba9e6  jnz     short loc_1400BAA4A
0x1400ba9e8  test    rbx, rbx
0x1400ba9eb  jz      short loc_1400BA9FE
0x1400ba9ed  call    cs:__imp_IoGetCurrentProcess
0x1400ba9f4  nop     dword ptr [rax+rax+00h]
0x1400ba9f9  cmp     rbx, rax
0x1400ba9fc  jnz     short loc_1400BAA4A
0x1400ba9fe  cmp     cs:?RefsStatusBreakForImage@@3PADA, 0; char near * RefsStatusBreakForImage
0x1400baa05  jz      short loc_1400BAA42
0x1400baa07  call    cs:__imp_IoGetCurrentProcess
0x1400baa0e  nop     dword ptr [rax+rax+00h]
0x1400baa13  mov     rcx, rax
0x1400baa16  call    cs:__imp_PsGetProcessImageFileName
0x1400baa1d  nop     dword ptr [rax+rax+00h]
0x1400baa22  mov     rdx, rax; Str2
0x1400baa25  mov     r8d, 0Fh; MaxCount
0x1400baa2b  lea     rcx, ?RefsStatusBreakForImage@@3PADA; Str1
0x1400baa32  call    cs:__imp__strnicmp
0x1400baa39  nop     dword ptr [rax+rax+00h]
0x1400baa3e  test    eax, eax
0x1400baa40  jnz     short loc_1400BAA4A
0x1400baa42  mov     eax, cs:?RefsStatusBreakForFsCtl@@3KC; ulong volatile RefsStatusBreakForFsCtl
0x1400baa48  int     2Ch; Windows NT - assertion failure
  ... truncated ...
```
