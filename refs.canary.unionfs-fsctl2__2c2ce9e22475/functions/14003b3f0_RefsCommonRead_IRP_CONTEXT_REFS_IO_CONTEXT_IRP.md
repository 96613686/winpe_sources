# RefsCommonRead(_IRP_CONTEXT *,REFS_IO_CONTEXT *,_IRP *)

- ea: `0x14003b3f0`
- end: `0x14003d175`
- name: `?RefsCommonRead@@YAJPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@PEAU_IRP@@@Z`
- size: `7557`
- prototype: `__int64 __fastcall(struct _IRP_CONTEXT *, struct REFS_IO_CONTEXT *, struct _IRP *)`
- caller_count: `3`
- callee_count: `32`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14003a850`
- `0x1400bc440`
- `0x14032c860`

## callees

- `0x14000a370`
- `0x14003b3f0`
- `0x14003d1d8`
- `0x14003d410`
- `0x14003d8f0`
- `0x14003fbe0`
- `0x140041280`
- `0x140041a40`
- `0x140041b40`
- `0x140042af0`
- `0x14007c580`
- `0x140080834`
- `0x140080c00`
- `0x1400815e0`
- `0x140081670`
- `0x14008dbd0`
- `0x140090040`
- `0x14009ca80`
- `0x1400a11b0`
- `0x1400abbc8`
- `0x1400ac4c8`
- `0x1400ca788`
- `0x1400ef56c`
- `0x1400fa85c`
- `0x1400fa94c`
- `0x1401ea140`
- `0x140298ed4`
- `0x1403148b0`
- `0x140320330`
- `0x140325110`
- `0x14032ae48`
- `0x14033b8d0`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x14003ba88`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14003c90b`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14003ba88`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14003c90b`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003c804`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003c81e`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003c804`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003c81e`
- `ntoskrnl!ExRaiseStatus` at `0x14003ce68`
- `ntoskrnl!ExRaiseStatus` at `0x14003ce68`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14003bcc9`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14003bcc9`
- `ntoskrnl!DbgPrintEx` at `0x14003c7a1`
- `ntoskrnl!DbgPrintEx` at `0x14003c7a1`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x14003c7c9`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x14003c7c9`
- `ntoskrnl!_strnicmp` at `0x14003c849`
- `ntoskrnl!_strnicmp` at `0x14003c849`
- `ntoskrnl!PsGetProcessImageFileName` at `0x14003c82d`
- `ntoskrnl!PsGetProcessImageFileName` at `0x14003c82d`
- `ntoskrnl!IoGetIoPriorityHint` at `0x14003ca75`
- `ntoskrnl!IoGetIoPriorityHint` at `0x14003ca75`
- `ntoskrnl!ExIsFastResourceHeld` at `0x14003c0a1`
- `ntoskrnl!ExIsFastResourceHeld` at `0x14003c0a1`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14003c685`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14003c685`
- `ntoskrnl!FsRtlCheckLockForReadAccess` at `0x14003c58e`
- `ntoskrnl!FsRtlCheckLockForReadAccess` at `0x14003c58e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003c694`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003c694`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14003c525`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14003c525`
- `ntoskrnl!FsRtlCheckOplock` at `0x14003c478`
- `ntoskrnl!FsRtlCheckOplock` at `0x14003c478`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x14003ce5a`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x14003ce5a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003c6d0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003c6d0`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14003c6dc`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14003c6dc`
- `HAL!KeQueryPerformanceCounter` at `0x14003b7de`
- `HAL!KeQueryPerformanceCounter` at `0x14003b7de`

## string_xrefs

- `0x14003b55c`: `Read.c`
- `0x14003b60c`: `Read.c`
- `0x14003bd4f`: `Read.c`
- `0x14003be00`: `Read.c`
- `0x14003be79`: `Read.c`
- `0x14003c001`: `Read.c`
- `0x14003c06a`: `Read.c`
- `0x14003c189`: `Read.c`
- `0x14003c261`: `Read.c`
- `0x14003c2fb`: `Read.c`
- `0x14003c32c`: `Read.c`
- `0x14003c5f5`: `Read.c`
- `0x14003c783`: `Read.c`
- `0x14003c892`: `Read.c`
- `0x14003c8ad`: `Read.c`
- `0x14003c8d5`: `Read.c`
- `0x14003c91e`: `Read.c`
- `0x14003c992`: `Read.c`
- `0x14003ca31`: `Read.c`
- `0x14003cace`: `Read.c`
- `0x14003cb73`: `Read.c`
- `0x14003cdc2`: `Read.c`
- `0x14003ce2e`: `Read.c`
- `0x14003d14f`: `Read.c`

## pseudocode

```c
__int64 __fastcall RefsCommonRead(struct _IRP_CONTEXT *a1, struct REFS_IO_CONTEXT *a2, struct _IRP *a3)
{
  PDEVICE_OBJECT *v4; // r15
  unsigned int v6; // r8d
  struct _FILE_OBJECT *v7; // rcx
  char *FsContext; // r14
  __int64 v9; // r10
  _BYTE *FsContext2; // r13
  int v11; // eax
  struct _FCB *v12; // r8
  char v13; // dl
  ULONG Flags; // r12d
  char v16; // di
  int v17; // r12d
  int Status; // edi
  unsigned int v19; // r9d
  int v20; // ecx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rcx
  __int64 v24; // r10
  const char *v25; // rbx
  __int64 v26; // r11
  LARGE_INTEGER PerformanceCounter; // rax
  char v28; // cl
  char v29; // al
  __int64 v30; // rax
  struct _IRP *v31; // rbx
  unsigned __int8 v32; // r9
  _DWORD *v33; // rdx
  __int16 v34; // ax
  PIRP TopLevelIrp; // rax
  __int64 Process; // rdx
  PMDL MdlAddress; // rcx
  struct REFS_IO_CONTEXT *v38; // r8
  char v39; // r15
  int v40; // eax
  unsigned __int8 v41; // al
  __int64 v42; // rcx
  unsigned __int8 v43; // al
  _QWORD *v44; // r8
  __int64 v45; // rcx
  unsigned __int8 v46; // al
  char *v47; // rax
  int v48; // ecx
  __int64 v49; // rdi
  __int16 v50; // ax
  PMRX_NET_ROOT pNetRoot; // rax
  PSRV_OPEN InternalSrvOpen; // rax
  __int64 v53; // r9
  unsigned __int64 v54; // rcx
  int v55; // eax
  int v56; // eax
  NTSTATUS v57; // edi
  __int64 v58; // r8
  __int16 v59; // ax
  __int16 v60; // ax
  __int64 v61; // rcx
  NTSTATUS v62; // edi
  IRP *v63; // r15
  struct REFS_IO_CONTEXT *v64; // r15
  __int64 v65; // rdi
  char v66; // al
  __int64 v67; // rax
  __int64 HighestPendingFileSize; // rdi
  int v69; // edx
  __int64 v70; // r15
  __int64 v71; // rax
  struct _FAST_MUTEX *v72; // rdi
  union _LARGE_INTEGER v73; // r11
  volatile unsigned int v74; // r15d
  struct _KPROCESS *v75; // r15
  PEPROCESS CurrentProcess; // rax
  const char *ProcessImageFileName; // rax
  const char *v78; // r8
  unsigned int v79; // r15d
  PIRP v80; // rax
  int v81; // eax
  int v82; // eax
  __int64 v83; // rcx
  unsigned int v84; // r9d
  PIRP v85; // r15
  __int16 v86; // ax
  int v87; // ecx
  unsigned int v88; // r10d
  int v89; // r10d
  struct REFS_IO_CONTEXT *v90; // rdx
  struct _MS_FAST_RESOURCE_OWNER_ENTRY *v91; // rax
  NTSTATUS v92; // eax
  bool v93; // zf
  PIRP v94; // r12
  ULONG v95; // edx
  ULONG_PTR v96; // rax
  __int64 v97; // r9
  _QWORD *v98; // r8
  __int64 v99; // rax
  unsigned int v100; // eax
  int v101; // ecx
  __int64 v102; // rax
  unsigned __int8 v103; // [rsp+50h] [rbp-1D8h]
  int v104; // [rsp+70h] [rbp-1B8h] BYREF
  __int64 v105; // [rsp+78h] [rbp-1B0h]
  int v106; // [rsp+80h] [rbp-1A8h]
  PIRP Irp; // [rsp+88h] [rbp-1A0h]
  char v108; // [rsp+90h] [rbp-198h]
  __int64 v109; // [rsp+98h] [rbp-190h]
  __int64 v110; // [rsp+A0h] [rbp-188h]
  unsigned int v111[2]; // [rsp+A8h] [rbp-180h]
  int v112; // [rsp+B0h] [rbp-178h]
  ULONG v113; // [rsp+B4h] [rbp-174h]
  int v114; // [rsp+B8h] [rbp-170h]
  __int64 v115; // [rsp+C0h] [rbp-168h]
  struct _FCB *v116; // [rsp+C8h] [rbp-160h]
  unsigned __int64 LowLimit; // [rsp+D0h] [rbp-158h] BYREF
  __int64 v118; // [rsp+D8h] [rbp-150h]
  unsigned int v119; // [rsp+E0h] [rbp-148h]
  unsigned __int8 v120[8]; // [rsp+E8h] [rbp-140h]
  struct _FILE_OBJECT *v121; // [rsp+F0h] [rbp-138h]
  __int64 v122; // [rsp+F8h] [rbp-130h]
  char *v123; // [rsp+100h] [rbp-128h]
  char *v124; // [rsp+108h] [rbp-120h]
  char *v125; // [rsp+110h] [rbp-118h]
  char *v126; // [rsp+118h] [rbp-110h]
  char *v127; // [rsp+120h] [rbp-108h]
  _QWORD v128[3]; // [rsp+128h] [rbp-100h] BYREF
  __int64 v129; // [rsp+140h] [rbp-E8h]
  _QWORD v130[27]; // [rsp+150h] [rbp-D8h] BYREF
  char v132; // [rsp+240h] [rbp+18h]
  char v133; // [rsp+248h] [rbp+20h]

  Irp = a3;
  v4 = (PDEVICE_OBJECT *)a2;
  memset(v130, 0, 0x58u);
  v104 = 0;
  *((_QWORD *)a1 + 1) &= ~8uLL;
  v109 = *((_QWORD *)a1 + 1);
  *(_QWORD *)v120 = a3->Tail.Overlay.CurrentStackLocation;
  v7 = *(struct _FILE_OBJECT **)(*(_QWORD *)v120 + 48LL);
  v121 = v7;
  FsContext = (char *)v7->FsContext;
  if ( FsContext )
  {
    v9 = *((_QWORD *)FsContext + 18);
    v115 = v9;
    FsContext2 = v7->FsContext2;
    v11 = *(_DWORD *)(v9 + 24);
    if ( (v11 & 1) == 0 && (!FsContext2 || FsContext2[80] != 4 || (v11 & 2) == 0) )
    {
      RefsRaiseStatusInternal(a1, -1073741202, v6);
      __debugbreak();
    }
    v12 = (struct _FCB *)*((_QWORD *)FsContext + 17);
    v116 = v12;
    if ( FsContext2 )
      v13 = FsContext2[80];
    else
      v13 = 5;
  }
  else
  {
    v9 = 0;
    v115 = 0;
    v12 = 0;
    v116 = 0;
    FsContext2 = 0;
    v13 = 1;
  }
  v133 = v13;
  if ( (*(_DWORD *)(v9 + 24) & 1) == 0 && v13 != 4 )
  {
    RefsCompleteReadWriteRequest(a1, (struct REFS_IO_CONTEXT *)v4, a3, -1073741202);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_4825f846088e3f1b9f5b83e186ef8a59_Traceguids, 3221226094LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741202, 0, "Read.c", 0x326u);
    return 3221226094LL;
  }
  Flags = a3->Flags;
  v16 = Flags & 1;
  v132 = Flags & 1;
  v113 = v7->Flags;
  if ( (Flags & 1) == 0 || (*((_DWORD *)FsContext + 38) & 0x1000000) == 0 )
  {
    v17 = Flags & 2;
    if ( FsContext2 && (*((_DWORD *)FsContext2 + 1) & 0x2000) != 0 && !v17 )
    {
      Status = -1073741811;
      RefsCompleteReadWriteRequest(a1, (struct REFS_IO_CONTEXT *)v4, a3, -1073741811);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_4825f846088e3f1b9f5b83e186ef8a59_Traceguids, 3221225485LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        return (unsigned int)Status;
      v19 = 842;
      goto LABEL_428;
    }
    v20 = 0;
    v114 = 0;
    if ( FsContext2 )
    {
      if ( (FsContext2[88] & 8) != 0 )
        v20 = 16;
      v114 = v20;
    }
    RefsUpdateFileTimestampsFromNonpagedFcb(v12, 0);
    v21 = *(unsigned int *)(*(_QWORD *)v120 + 8LL);
    *(_QWORD *)v111 = v21;
    v22 = *(_QWORD *)(*(_QWORD *)v120 + 24LL);
    v105 = v22;
    LowLimit = v22;
    v23 = v21 + v22;
    v118 = v21 + v22;
    v119 = v21;
    v24 = v115;
    if ( v16 )
    {
      LOBYTE(v25) = v104;
      if ( ((*(_DWORD *)(v115 + 276) - 1) & (unsigned int)v22) != 0
        || ((*(_DWORD *)(v115 + 276) - 1) & (unsigned int)v21) != 0 )
      {
        LOBYTE(v25) = 32;
      }
      LOBYTE(v104) = (_BYTE)v25;
      v23 = v118;
    }
    else
    {
      LOBYTE(v25) = v104;
    }
    if ( FsContext2 && FsContext2[81] )
      *((_QWORD *)a1 + 1) |= 0x8000000000uLL;
    if ( v22 < 0 || v22 > v23 )
    {
      Status = -1073741811;
      RefsCompleteReadWriteRequest(a1, (struct REFS_IO_CONTEXT *)v4, Irp, -1073741811);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_4825f846088e3f1b9f5b83e186ef8a59_Traceguids, 3221225485LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        return (unsigned int)Status;
      v19 = 896;
LABEL_428:
      RefsStatusDebug(Status, 0, "Read.c", v19);
      return (unsigned int)Status;
    }
    if ( !(_DWORD)v21 )
    {
      *((_QWORD *)a1 + 86) = 8;
      RefsCompleteReadWriteRequest(a1, (struct REFS_IO_CONTEXT *)v4, Irp, 0);
      return 0;
    }
    v26 = v109;
    LOBYTE(v26) = v109 & 1;
    v109 = v26;
    if ( *(_BYTE *)(v24 + 10496) )
    {
      PerformanceCounter = *(LARGE_INTEGER *)((char *)a1 + 688);
      if ( PerformanceCounter.QuadPart <= 23 )
      {
        PerformanceCounter = KeQueryPerformanceCounter(0);
        LODWORD(v21) = v111[0];
        v22 = v105;
        v24 = v115;
        LOBYTE(v26) = v109;
      }
      *((LARGE_INTEGER *)a1 + 86) = PerformanceCounter;
      if ( v17 || v16 )
        v28 = 0;
      else
        v28 = 2;
      v29 = 16;
      if ( v17 )
        v29 = 20;
      *((_BYTE *)v4 + 56) = v26 | v28 | v29;
      v23 = v118;
    }
    if ( (v121->Flags & 0x20000000) != 0 )
    {
      *((_BYTE *)v4 + 56) |= 1u;
      return RefsMinstoreRead(a1, (struct REFS_IO_CONTEXT *)v4, Irp, (unsigned __int64)&LowLimit);
    }
    v113 &= 2u;
    if ( (*((_DWORD *)FsContext + 38) & 0x20) == 0 )
    {
      LOBYTE(v109) = 1;
      *((_QWORD *)a1 + 1) |= 1uLL;
      *((_BYTE *)v4 + 56) |= 1u;
    }
    if ( _bittest64((const signed __int64 *)a1 + 1, 0x27u) )
      *(_DWORD *)v4 |= 0x80u;
    if ( v133 == 4 )
    {
      if ( (*((_DWORD *)FsContext2 + 1) & 0x100) == 0 )
      {
        v30 = *((_QWORD *)FsContext + 4);
        if ( v30 <= v22 )
        {
          Status = -1073741807;
          RefsCompleteReadWriteRequest(a1, (struct REFS_IO_CONTEXT *)v4, Irp, -1073741807);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              22,
              WPP_4825f846088e3f1b9f5b83e186ef8a59_Traceguids,
              3221225489LL);
          }
          if ( !(_BYTE)RefsStatusDebugEnabled )
            return (unsigned int)Status;
          v19 = 1010;
          goto LABEL_428;
        }
        if ( v30 < v23 )
          LODWORD(v21) = v30 - v22;
      }
      v31 = Irp;
      Status = RefsVolumeDasdIo(
                 a1,
                 (struct REFS_IO_CONTEXT *)v4,
                 Irp,
                 (struct _SCB *)FsContext,
                 (struct _CCB *)FsContext2,
                 v22,
                 v21);
      if ( Status >= 0 )
        RefsUpdateFileTimestampsForAccess(v121, v116, (struct _CCB *)FsContext2, v32);
      if ( v113 && !v17 && Status >= 0 )
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v120 + 48LL) + 104LL) = Irp->IoStatus.Information + v105;
      if ( (_BYTE)v109 )
        RefsCompleteReadWriteRequest(a1, (struct REFS_IO_CONTEXT *)v4, v31, Status);
      return (unsigned int)Status;
    }
    v123 = FsContext;
    LODWORD(v110) = 0;
    if ( v17 )
    {
      v33 = (_DWORD *)(*(_QWORD *)(v24 + 808)
                     + ((unsigned __int64)(KeGetCurrentProcessorNumber() % RefsNumberProcessors) << 6));
      if ( ((__int64)v116->spacer.Resource & 0x100LL) == 0
        && ((v34 = *((_WORD *)FsContext + 108), v34 == 128) || v34 == 176) )
      {
        ++v33[2];
        v33[3] += v21;
      }
      else
      {
        ++v33[8];
        v33[9] += v21;
      }
    }
    else if ( v16 )
    {
LABEL_97:
      v130[9] = 0x100000000LL;
      v130[10] = 0;
      TopLevelIrp = IoGetTopLevelIrp();
      if ( HIBYTE(TopLevelIrp->Type) )
      {
        MdlAddress = TopLevelIrp->MdlAddress;
        Process = (__int64)MdlAddress->Process;
        if ( (*(_DWORD *)(Process + 4) & 0x200) == 0 )
          LOBYTE(TopLevelIrp->Type) = 0;
      }
      if ( v17 )
        goto LABEL_195;
      v112 = 0;
      if ( v16 )
      {
        v39 = 0;
      }
      else
      {
        if ( !*(_QWORD *)(*((_QWORD *)FsContext + 31) + 16LL) )
          goto LABEL_127;
        v39 = 1;
      }
      if ( !v16 )
        goto LABEL_115;
      if ( !*(_QWORD *)(*((_QWORD *)FsContext + 31) + 8LL) || *((_DWORD *)FsContext + 86) )
      {
        if ( !(_BYTE)v109 )
        {
          v40 = *((_DWORD *)FsContext + 38);
          if ( ((v40 & 8) == 0 || (v40 & 0x40) != 0) && ((unsigned __int8)v25 & 0x20) == 0 )
          {
            v130[12] = FsContext;
            v124 = (char *)a2 + 720;
            v41 = RefsAcquirePagingFastResourceShared(MdlAddress, FsContext, (char *)a2 + 720);
            v42 = v41;
            v112 = v41;
            if ( v41 )
            {
              LOBYTE(v25) = (unsigned __int8)v25 | 0x80;
              LOBYTE(v104) = (_BYTE)v25;
            }
            Process = (__int64)v124;
            v38 = a2;
LABEL_116:
            if ( !(_DWORD)v42 )
              goto LABEL_141;
            if ( !v39 || *(_QWORD *)(*((_QWORD *)FsContext + 31) + 16LL) )
            {
              if ( !v16 || !*(_QWORD *)(*((_QWORD *)FsContext + 31) + 8LL) || *((_DWORD *)FsContext + 86) )
                goto LABEL_140;
              Process = (__int64)v38 + 720;
            }
            if ( (char)v25 >= 0 )
            {
              v130[14] = FsContext;
              v44 = v130;
            }
            else
            {
              v130[13] = FsContext;
              v44 = (_QWORD *)Process;
            }
            RefsReleasePagingFastResource(v42, FsContext, v44);
            v130[15] = FsContext;
            v46 = RefsAcquirePagingFastResourceExclusive(v45, FsContext, v130, (unsigned __int8)v109);
            LOBYTE(v104) = (unsigned __int8)v25 | 2;
            for ( LOBYTE(v25) = (unsigned __int8)v25 & 0x7D | 2; ; LOBYTE(v25) = (unsigned __int8)v25 | 2 )
            {
              LODWORD(v42) = v46;
              LOBYTE(v104) = (_BYTE)v25;
              v112 = v46;
LABEL_140:
              if ( (_DWORD)v42 )
                break;
LABEL_141:
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  23,
                  WPP_4825f846088e3f1b9f5b83e186ef8a59_Traceguids,
                  3221225688LL);
              }
              if ( (_BYTE)RefsStatusDebugEnabled )
                RefsStatusDebug(-1073741608, a1, "Read.c", 0x4A4u);
              RefsRaiseStatusInternal(a1, -1073741608, (unsigned int)v38);
LABEL_148:
              LODWORD(v130[9]) = v48 + 1;
              v46 = 1;
LABEL_138:
              ;
            }
            LOBYTE(v25) = (unsigned __int8)v25 | 1;
            LOBYTE(v104) = (_BYTE)v25;
            if ( *((_DWORD *)FsContext + 74) == 3 )
            {
              v50 = *((_WORD *)FsContext + 108);
              if ( v50 == 128 || v50 == 176 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    24,
                    WPP_4825f846088e3f1b9f5b83e186ef8a59_Traceguids,
                    3221226659LL);
                }
                if ( (_BYTE)RefsStatusDebugEnabled )
                  RefsStatusDebug(-1073740637, a1, "Read.c", 0x4AFu);
                RefsRaiseStatusInternal(a1, -1073740637, (unsigned int)v38);
              }
            }
            if ( (*((_DWORD *)FsContext2 + 1) & 0x8000) != 0 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  25,
                  WPP_4825f846088e3f1b9f5b83e186ef8a59_Traceguids,
                  3221225768LL);
              }
              if ( (_BYTE)RefsStatusDebugEnabled )
                RefsStatusDebug(-1073741528, a1, "Read.c", 0x4B7u);
              RefsRaiseStatusInternal(a1, -1073741528, (unsigned int)v38);
            }
            if ( ((__int64)v116->Header.Resource & 0x1000000) == 0 )
            {
              pNetRoot = v116->pNetRoot;
              if ( pNetRoot[2].pSrvCall
                || !pNetRoot[2].Context
                || (InternalSrvOpen = v116->InternalSrvOpen) != 0 && InternalSrvOpen[1].SrvOpenKeyList.Blink )
              {
                if ( *(_QWORD *)&v116->FcbTableEntry.Lookups )
                {
                  if ( !v16 || !*(_QWORD *)(*((_QWORD *)FsContext + 31) + 8LL) || *((_DWORD *)FsContext + 86) )
                    goto LABEL_221;
                  v53 = v105;
                  v54 = v111[0];
                  if ( *(_WORD *)FsContext == 2053 && *((_QWORD *)FsContext + 54) && *((_WORD *)FsContext + 130) )
                  {
                    v55 = 1 << *(_DWORD *)(*((_QWORD *)FsContext + 18) + 552LL);
                    Process = -(__int64)v55;
                    v53 = v105 & Process;
                    v54 = ((unsigned int)Process & ((_DWORD)v105 + v111[0] + v55 - 1))
                        - ((unsigned int)v105 & (unsigned int)Process);
                  }
                  v56 = RefsCacheCoherencyFlush(
                          a1,
                          (struct _IRP *)Process,
                          (struct _SCB *)FsContext,
                          v53,
                          v54,
                          0,
                          *((_DWORD *)FsContext + 45) == 0);
                  v57 = v56;
                  v106 = v56;
                  if ( v56 >= 0 )
                    goto LABEL_221;
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                  {
                    WPP_SF_d(
                      WPP_GLOBAL_Control->AttachedDevice,
                      27,
                      WPP_4825f846088e3f1b9f5b83e186ef8a59_Traceguids,
                      (unsigned int)v56);
                  }
                  if ( (_BYTE)RefsStatusDebugEnabled )
                    RefsStatusDebug(v57, a1, "Read.c", 0x4EEu);
                  RefsRaiseStatusInternal(a1, v57, (unsigned int)v38);
                }
              }
            }
            v4 = &WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                26,
                WPP_4825f846088e3f1b9f5b83e186ef8a59_Traceguids,
                3221225768LL);
            }
            if ( (_BYTE)RefsStatusDebugEnabled )
              RefsStatusDebug(-1073741528, a1, "Read.c", 0x4BBu);
            RefsRaiseStatusInternal(a1, -1073741528, (unsigned int)v38);
LABEL_195:
            if ( *((_QWORD *)FsContext + 2)
              && !(unsigned __int8)ExIsFastResourceHeld(*(_QWORD *)(*((_QWORD *)FsContext + 17) + 96LL)) )
            {
              LODWORD(v110) = v111[0];
              RefsAcquireRangeLock(
                a1,
                *((struct _SCB_NONPAGED **)FsContext + 31),
                v105,
                v111[0],
                0,
                (struct _RANGE_LOCK_STATE *)(v4 + 4));
              *((_DWORD *)a1 + 1) |= 0x40u;
              v130[17] = FsContext;
              LOBYTE(v58) = 1;
              RefsAcquireResourceShared(a1, FsContext, v58);
              LOBYTE(v25) = (unsigned __int8)v25 | 0x14;
              LOBYTE(v104) = (_BYTE)v25;
              if ( *((_DWORD *)FsContext + 74) == 3 )
              {
                v59 = *((_WORD *)FsContext + 108);
                if ( v59 == 128 || v59 == 176 )
                {
                  v4 = &WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                  {
                    WPP_SF_d(
                      WPP_GLOBAL_Control->AttachedDevice,
                      28,
                      WPP_4825f846088e3f1b9f5b83e186ef8a59_Traceguids,
                      3221226659LL);
                  }
                  if ( (_BYTE)RefsStatusDebugEnabled )
                    RefsStatusDebug(-1073740637, a1, "Read.c", 0x539u);
                  RefsRaiseStatusInternal(a1, -1073740637, (unsigned int)v38);
                }
              }
              if ( *(_WORD *)FsContext == 2053 && *((_QWORD *)FsContext + 54) && *((_WORD *)FsContext + 130) )
                *((_QWORD *)a1 + 1) |= 0x10000000000uLL;
LABEL_222:
              v61 = *((unsigned int *)FsContext + 75);
              v62 = (*((_DWORD *)FsContext + 75) & 0x4000) != 0 ? 0xC000026E : 0;
              v106 = v62;
              if ( (v61 & 0x40) != 0 )
              {
                v4 = &WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
                {
                  v62 = -1073741533;
                }
                else
                {
                  v62 = -1073741533;
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    30,
                    WPP_4825f846088e3f1b9f5b83e186ef8a59_Traceguids,
                    3221225763LL);
                }
                v25 = "Read.c";
                if ( (_BYTE)RefsStatusDebugEnabled )
                  RefsStatusDebug(-1073741533, 0, "Read.c", 0x566u);
                v106 = -1073741533;
              }
              else
              {
                if ( v62 >= 0 )
                  goto LABEL_240;
                v4 = &WPP_GLOBAL_Control;
                v25 = "Read.c";
              }
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  31,
                  WPP_4825f846088e3f1b9f5b83e186ef8a59_Traceguids,
                  (unsigned int)v62);
              }
              if ( (_BYTE)RefsStatusDebugEnabled )
                RefsStatusDebug(v62, a1, "Read.c", 0x56Eu);
              RefsRaiseStatusInternal(a1, v62, (unsigned int)v38);
LABEL_240:
              if ( (*((_DWORD *)FsContext + 38) & 0x20) == 0 )
              {
                if ( ((unsigned __int8)v25 & 0x10) == 0 )
                {
                  v130[18] = FsContext;
                  LOBYTE(v38) = 1;
                  RefsAcquireResourceShared(a1, FsContext, v38);
                  LOBYTE(v25) = (unsigned __int8)v25 | 0x18;
                  LOBYTE(v104) = (_BYTE)v25;
                }
                RefsUpdateScbFromAttribute(a1, (struct _SCB *)FsContext, 0);
                if ( ((unsigned __int8)v25 & 8) != 0 )
                {
                  v130[19] = FsContext;
                  RefsReleaseResource(a1, FsContext);
                  LOBYTE(v25) = (unsigned __int8)v25 & 0xE7;
                  LOBYTE(v104) = (_BYTE)v25;
                }
              }
              if ( v133 != 2 )
                goto LABEL_275;
              v128[0] = v4;
              v128[1] = FsContext;
              v128[2] = v130;
              v129 = (unsigned __int8)v25 >> 7;
              *((_QWORD *)a1 + 18) = v128;
              v63 = Irp;
              Status = FsRtlCheckOplock(
                         (POPLOCK)FsContext + 11,
                         Irp,
                         a1,
                         RefsOplockComplete,
                         RefsCommonRead_::_213_::_lambda_1_::_lambda_invoker_cdecl_);
              v106 = Status;
              v61 = (unsigned __int8)v129;
              LOBYTE(v25) = (unsigned __int8)v25 & 0x7F | ((_BYTE)v129 << 7);
              LOBYTE(v104) = (_BYTE)v25;
              if ( Status )
              {
LABEL_247:
                Irp = 0;
                a1 = 0;
                v64 = 0;
LABEL_382:
                v83 = v105;
LABEL_383:
                if ( Irp )
                {
                  v93 = v17 == 0;
                  v94 = Irp;
                  if ( v93 )
                  {
                    v95 = v113;
                    if ( v113 )
                    {
                      v96 = (Status & 0xC0000000) == 0xC0000000 ? 0LL : Irp->IoStatus.Information;
                      v97 = *(_QWORD *)v120;
                      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v120 + 48LL) + 104LL) = v96 + v83;
                    }
                    else
                    {
                      v97 = *(_QWORD *)v120;
                    }
                    if ( Status >= 0 && v95 )
                      RefsUpdateFileTimestampsForAccess(
                        *(struct _FILE_OBJECT **)(v97 + 48),
                        *((struct _FCB **)FsContext + 17),
                        (struct _CCB *)FsContext2,
                        v97);
                  }
                  RefsCleanupTransaction(a1, Status, 0);
                  v83 = v105;
                }
                else
                {
                  v94 = 0;
                }
                if ( ((unsigned __int8)v25 & 4) != 0 )
                {
                  *((_DWORD *)a1 + 1) &= ~0x40u;
                  RefsReleaseRangeLock(
                    *((struct _SCB_NONPAGED **)FsContext + 31),
                    v83,
                    (unsigned int)v110,
                    0,
                    (struct REFS_IO_CONTEXT *)((char *)v64 + 32));
                }
                if ( ((unsigned __int8)v25 & 1) != 0 )
                {
                  if ( (char)v25 >= 0 )
                  {
                    v126 = FsContext;
                    v98 = v130;
                  }
                  else
                  {
                    v125 = FsContext;
                    v98 = (_QWORD *)((char *)v64 + 720);
                  }
                  RefsReleasePagingFastResource(v83, FsContext, v98);
                }
                if ( ((unsigned __int8)v25 & 0x10) != 0 )
                {
                  v127 = FsContext;
                  RefsReleaseResource(a1, FsContext);
                }
                HIDWORD(v130[9]) &= ~1u;
                if ( a1 )
                {
                  v99 = *((_QWORD *)a1 + 1);
                  if ( (v99 & 0x100000000LL) != 0 )
                  {
                    *((_QWORD *)a1 + 1) = v99 | 0x200000000LL;
                    return (unsigned int)Status;
                  }
                  if ( Status >= 0 && *(_BYTE *)(*((_QWORD *)a1 + 8) + 10496LL) && *((__int64 *)a1 + 86) > 23 )
                    RefsIoPerfCollectReadWriteData(*((struct _VCB **)a1 + 8), v94, a1, v64);
                  *((_QWORD *)a1 + 1) |= 0x8000uLL;
                  if ( Status < 0 )
                  {
                    v100 = *((unsigned __int8 *)a1 + 40);
                    if ( (unsigned __int8)v100 <= 0x12u )
                    {
                      v101 = 262685;
                      if ( _bittest(&v101, v100) )
                      {
                        v102 = *((_QWORD *)a1 + 8);
                        if ( v102 )
                        {
                          if ( *(_BYTE *)(v102 + 10496)
                            && (*((_DWORD *)a1 + 1) & 0x400) == 0
                            && (*((_DWORD *)a1 + 2) & 0x10000) == 0 )
                          {
                            *((_QWORD *)a1 + 86) = 7;
                          }
                        }
                      }
                    }
                  }
                  *((_DWORD *)v64 + 199) &= ~1u;
                }
                RefsCompleteRequest(a1, v94, Status);
                return (unsigned int)Status;
              }
              if ( FsContext[5] )
              {
LABEL_264:
                if ( !v17 )
                {
                  v61 = *((_QWORD *)FsContext + 48);
                  if ( v61 )
                  {
                    if ( !FsRtlCheckLockForReadAccess((PFILE_LOCK)v61, v63) )
                    {
                      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
                        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
                      {
                        Status = -1073741740;
                      }
                      else
                      {
                        Status = -1073741740;
                        WPP_SF_d(
                          WPP_GLOBAL_Control->AttachedDevice,
                          32,
                          WPP_4825f846088e3f1b9f5b83e186ef8a59_Traceguids,
                          3221225556LL);
                      }
                      if ( (_BYTE)RefsStatusDebugEnabled )
                        RefsStatusDebug(-1073741740, 0, "Read.c", 0x5D1u);
LABEL_274:
                      v106 = Status;
                      v64 = a2;
                      goto LABEL_382;
                    }
                  }
                }
LABEL_275:
                HighestPendingFileSize = 0;
                v122 = 0;
                v69 = *((_DWORD *)FsContext + 43);
                LOBYTE(v61) = 1;
                v108 = 1;
                v70 = 0;
                v71 = v118;
                if ( (v69 & 1) == 0 )
                {
                  HighestPendingFileSize = *((_QWORD *)FsContext + 4);
                  v122 = HighestPendingFileSize;
                  if ( v118 >= HighestPendingFileSize && v17 )
                  {
                    v70 = HighestPendingFileSize;
                  }
                  else
                  {
                    v70 = HighestPendingFileSize;
                    v71 = v118;
                    if ( v69 == *((_DWORD *)FsContext + 43) )
                    {
                      LOBYTE(v61) = 0;
                      v108 = 0;
                    }
                  }
                }
                if ( (_BYTE)v61 )
                {
                  v72 = (struct _FAST_MUTEX *)*((_QWORD *)FsContext + 6);
                  KeEnterGuardedRegion();
                  ExAcquireFastMutexUnsafe(v72);
                  if ( v17 )
                    HighestPendingFileSize = RefsGetHighestPendingFileSize((const struct DataSCB *)FsContext);
                  else
                    HighestPendingFileSize = *((_QWORD *)FsContext + 4);
                  v122 = HighestPendingFileSize;
                  v70 = HighestPendingFileSize;
                  ExReleaseFastMutexUnsafe(*((PFAST_MUTEX *)FsContext + 6));
                  KeLeaveGuardedRegion();
                  v71 = v118;
                }
                v73.QuadPart = v105;
                if ( v71 > v70 )
                {
                  if ( v105 >= v70 )
                  {
                    v61 = (__int64)WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
                      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
                    {
                      Status = -1073741807;
                    }
                    else
                    {
                      Status = -1073741807;
                      WPP_SF_d(
                        WPP_GLOBAL_Control->AttachedDevice,
                        17,
                        WPP_4825f846088e3f1b9f5b83e186ef8a59_Traceguids,
                        3221225489LL);
                      v73.QuadPart = v105;
                    }
                    if ( (_BYTE)RefsStatusDebugEnabled )
                    {
                      if ( RefsStatusDisplayStatus == -1073741807 )
                        DbgPrintEx(0x95u, 0, "th%p %x %s:%i\n", KeGetCurrentThread(), -1073741807, "Read.c", 701);
                      v74 = RefsStatusBreakOnWin32Error;
                      if ( RefsStatusBreakOnStatus == -1073741807
                        || RefsStatusBreakOnWin32Error && v74 == RtlNtStatusToDosErrorNoTeb(-1073741807) )
                      {
                        v75 = RefsStatusBreakForProcess;
                        if ( !RefsStatusBreakForThread
                          || RefsStatusBreakForThread == KeGetCurrentThread()
                          && (!RefsStatusBreakForProcess || v75 == IoGetCurrentProcess())
                          && (!RefsStatusBreakForImage
                           || (CurrentProcess = IoGetCurrentProcess(),
                               ProcessImageFileName = (const char *)PsGetProcessImageFileName(CurrentProcess),
                               !_strnicmp(&RefsStatusBreakForImage, ProcessImageFileName, 0xFu))) )
                        {
                          __int2c();
                        }
                      }
                      v61 = 32LL
                          * (((unsigned __int16)_InterlockedExchangeAdd(
                                                  (volatile signed __int32 *)&RefsStatusNextQueueEntry,
                                                  1u)
                            + 1)
                           & 0xFFF);
                      *(struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near **)((char *)&RefsStatusQueue + v61) = KeGetCurrentThread();
                      *(_DWORD *)((char *)&RefsStatusQueue + v61 + 8) = -1073741807;
                      v78 = "Read.c";
                      *(struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near **)((char *)&RefsStatusQueue + v61 + 16) = (struct _REFS_STATUS_DEBUG_QUEUE_ENTRY near *)"Read.c";
                      *(_DWORD *)((char *)&RefsStatusQueue + v61 + 24) = 701;
                      v73.QuadPart = v105;
                    }
                    else
                    {
                      v78 = "Read.c";
                    }
LABEL_310:
                    v106 = Status;
                    if ( Status < 0 )
                    {
                      *((_QWORD *)a1 + 86) = 18;
                      v64 = a2;
                      goto LABEL_382;
                    }
                    if ( v17 )
                    {
                      v80 = IoGetTopLevelIrp();
                      v78 = "Read.c";
                      v73.QuadPart = v105;
                      if ( v80->MdlAddress == (PMDL)2 )
                        *((_QWORD *)a1 + 1) |= 0x800uLL;
                    }
                    v81 = *((_DWORD *)FsContext + 38);
                    if ( (v81 & 8) != 0 && (v81 & 0x40) == 0 )
                    {
                      if ( !v132 )
                        goto LABEL_379;
                      if ( ((unsigned __int8)v25 & 0x10) == 0 )
                      {
                        LOBYTE(v78) = 1;
                        RefsAcquireResourceShared(a1, FsContext, v78);
                        LOBYTE(v25) = (unsigned __int8)v25 | 0x18;
                        LOBYTE(v104) = (_BYTE)v25;
                        v73.QuadPart = v105;
                      }
                      v82 = *((_DWORD *)FsContext + 38);
                      if ( (v82 & 8) != 0 && (v82 & 0x40) == 0 )
                      {
                        *((_QWORD *)a1 + 86) = 16;
                        RefsNonCachedResidentRead(a1, Irp, (struct _SCB *)FsContext);
                        Irp->IoStatus.Information = v119;
                        Status = 0;
                        v106 = 0;
                        v83 = LowLimit;
                        v105 = LowLimit;
                        v64 = a2;
                        goto LABEL_383;
                      }
                      if ( ((unsigned __int8)v25 & 8) != 0 )
                      {
                        RefsReleaseResource(a1, FsContext);
                        LOBYTE(v25) = (unsigned __int8)v25 & 0xE7;
                        LOBYTE(v104) = (_BYTE)v25;
                        v73.QuadPart = v105;
                      }
                    }
                    if ( v132 )
                    {
                      v84 = v111[0];
                      v85 = Irp;
                      if ( v111[0] )
                      {
                        if ( (*(_DWORD *)(v115 + 6568) & 1) != 0 )
                        {
                          if ( IoGetIoPriorityHint(Irp) > IoPriorityLow )
                          {
                            if ( ((v86 = *((_WORD *)FsContext + 108), v86 == 128) || v86 == 176)
                              && !*((_WORD *)FsContext + 112)
                              || (v61 = 160, v86 == 160) )
                            {
                              RefsHeatLogIo(Irp, v116);
                            }
                          }
                          v84 = v111[0];
                          v73.QuadPart = v105;
                        }
                        if ( ((unsigned __int8)v25 & 0x20) == 0
                          || (v61 = 2053, *(_WORD *)FsContext == 2053)
                          && *((_QWORD *)FsContext + 54)
                          && *((_WORD *)FsContext + 130) )
                        {
                          if ( ((unsigned __int8)v25 & 0x20) != 0 )
                          {
                            v89 = v84;
                          }
                          else
                          {
                            v87 = *(_DWORD *)(*((_QWORD *)a1 + 8) + 276LL);
                            v88 = v84 + v87 - 1;
                            v61 = (unsigned int)-v87;
                            v89 = v61 & v88;
                          }
                          v90 = a2;
                          if ( !(_BYTE)v109 )
                          {
                            if ( v17 )
                            {
                              if ( ((unsigned __int8)v25 & 0x10) != 0 )
                                RefsSetIoContextAsync(
                                  (struct _IRP_CONTEXT *)v61,
                                  a2,
                                  *((struct _FAST_ERESOURCE **)FsContext + 1),
                                  0,
                                  0,
                                  *((struct _SCB_NONPAGED **)FsContext + 31),
                                  v73.QuadPart,
                                  v110,
                                  0,
                                  v84,
                                  v103,
                                  (struct _SCB *)FsContext,
                                  (struct _CCB *)FsContext2);
                              else
                                RefsSetIoContextAsync(
                                  (struct _IRP_CONTEXT *)v61,
                                  a2,
                                  0,
                                  0,
                                  0,
                                  0,
                                  v73.QuadPart,
                                  0,
                                  0,
                                  v84,
                                  v103,
                                  (struct _SCB *)FsContext,
                                  (struct _CCB *)FsContext2);
                            }
                            else
                            {
                              v91 = (struct REFS_IO_CONTEXT *)((char *)a2 + 720);
                              if ( (char)v25 >= 0 )
                                v91 = (struct _MS_FAST_RESOURCE_OWNER_ENTRY *)v130;
                              RefsSetIoContextAsync(
                                (struct _IRP_CONTEXT *)v61,
                                a2,
                                0,
                                *((struct _MS_FAST_RESOURCE **)FsContext + 2),
                                v91,
                                0,
                                v73.QuadPart,
                                0,
                                0,
                                v84,
                                v103,
                                (struct _SCB *)FsContext,
                                (struct _CCB *)FsContext2);
                            }
                          }
                          LOBYTE(v25) = (unsigned __int8)v25 & 0xBF | (*((_QWORD *)a1 + 1) >> 26) & 0x40;
                          LOBYTE(v104) = (_BYTE)v25;
                          Status = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))RefsNonCachedIo)(
                                     a1,
                                     v90,
                                     Irp,
                                     FsContext,
                                     (union _LARGE_INTEGER)v73.QuadPart,
                                     v89,
                                     v114);
                          v106 = Status;
                        }
                        else
                        {
                          if ( (*((_QWORD *)a1 + 1) & 0x8000000000LL) != 0 )
                          {
                            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
                              || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
                            {
                              Status = -1073741811;
                            }
                            else
                            {
                              Status = -1073741811;
                              WPP_SF_d(
                                WPP_GLOBAL_Control->AttachedDevice,
                                33,
                                WPP_4825f846088e3f1b9f5b83e186ef8a59_Traceguids,
                                3221225485LL);
                            }
                            if ( (_BYTE)RefsStatusDebugEnabled )
                            {
                              RefsStatusDebug(-1073741811, 0, "Read.c", 0x653u);
                              v106 = -1073741811;
                              v64 = a2;
                              goto LABEL_382;
                            }
                            goto LABEL_274;
                          }
                          if ( !(_BYTE)v109 )
                          {
                            if ( ((unsigned __int8)v25 & 4) != 0 )
                            {
                              *((_DWORD *)a1 + 1) &= ~0x40u;
                              LOBYTE(v25) = (unsigned __int8)v25 & 0xFB;
                              LOBYTE(v104) = (_BYTE)v25;
                              RefsReleaseRangeLock(
                                *((struct _SCB_NONPAGED **)FsContext + 31),
                                v73.QuadPart,
                                (unsigned int)v110,
                                0,
                                (struct REFS_IO_CONTEXT *)((char *)a2 + 32));
                            }
                            if ( ((unsigned __int8)v25 & 0x10) != 0 )
                            {
                              v121 = (struct _FILE_OBJECT *)FsContext;
                              RefsReleaseResource(a1, FsContext);
                              LOBYTE(v25) = (unsigned __int8)v25 & 0xE7;
                              LOBYTE(v104) = (_BYTE)v25;
                            }
                            Status = RefsPostRequest(a1, v85, 0, 0);
                            v106 = Status;
                            goto LABEL_247;
                          }
                          RefsNonCachedNonAlignedIo(a1, a2, Irp, (struct _SCB *)FsContext, v73.QuadPart, v84);
                        }
                        if ( Status == 259 )
                        {
                          Irp = 0;
                          a1 = 0;
                          v64 = 0;
                          LOBYTE(v25) = (unsigned __int8)v25 & 0xEA;
                          LOBYTE(v104) = (_BYTE)v25;
                          goto LABEL_382;
                        }
                        v84 = v111[0];
                        if ( Status >= 0 )
                          *((_BYTE *)a2 + 56) |= 1u;
                      }
                      Status = v85->IoStatus.Status;
                      v106 = Status;
                      if ( Status < 0 )
                      {
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                        {
                          WPP_SF_dd(
                            WPP_GLOBAL_Control->AttachedDevice,
                            34,
                            WPP_4825f846088e3f1b9f5b83e186ef8a59_Traceguids,
                            3221225705LL,
                            Status);
                        }
                        *((_DWORD *)a1 + 4) = Status;
                        if ( (_BYTE)RefsStatusDebugEnabled )
                          RefsStatusDebug(Status, a1, "Read.c", 0x716u);
                        v92 = FsRtlNormalizeNtstatus(Status, -1073741591);
                        ExRaiseStatus(v92);
                      }
                      v85->IoStatus.Information = v84;
                      v64 = a2;
                      goto LABEL_382;
                    }
LABEL_379:
                    v64 = a2;
                    Status = RefsCachedRead(
                               a1,
                               a2,
                               v121,
                               Irp,
                               (struct DataSCB *)FsContext,
                               (struct _MS_FAST_RESOURCE_OWNER_ENTRY *)v130,
                               v73,
                               v111[0],
                               (union _REFS_READ_FLAGS *)&v104);
                    v106 = Status;
                    if ( Status == 259 )
                    {
                      Irp = 0;
                      a1 = 0;
                      v64 = 0;
                    }
                    LOBYTE(v25) = v104;
                    goto LABEL_382;
                  }
                  v118 = HighestPendingFileSize;
                  v79 = v70 - v105;
                  *(_QWORD *)v111 = v79;
                  v119 = v79;
                }
                Status = 0;
                v78 = "Read.c";
                goto LABEL_310;
              }
              v65 = *((_QWORD *)FsContext + 18);
              if ( (*(_DWORD *)(v65 + 24) & 0x4000005) == 1
                && *(_WORD *)FsContext == 2053
                && (*((_DWORD *)FsContext + 75) & 0x40) == 0 )
              {
                v61 = *(unsigned __int8 *)(*((_QWORD *)FsContext + 17) + 8LL);
                if ( (v61 & 0x80u) == 0LL )
                {
                  if ( (*((_DWORD *)FsContext + 38) & 0x20) == 0 )
                    goto LABEL_254;
                  if ( FsRtlOplockIsFastIoPossible((POPLOCK)FsContext + 11) )
                  {
                    if ( *((__int16 *)FsContext + 128) >= 0 )
                    {
                      v67 = *((_QWORD *)FsContext + 48);
                      if ( (!v67 || !*(_BYTE *)(v67 + 16))
                        && (*(_DWORD *)(v65 + 24) & 0x2000000) == 0
                        && (*(_BYTE *)(*((_QWORD *)FsContext + 17) + 8LL) & 0x20) == 0 )
                      {
                        v66 = 1;
                        goto LABEL_263;
                      }
                    }
LABEL_254:
                    v66 = 2;
LABEL_263:
                    FsContext[5] = v66;
                    goto LABEL_264;
                  }
                }
              }
              v66 = 0;
              goto LABEL_263;
            }
            if ( *((_DWORD *)FsContext + 74) != 3 )
              goto LABEL_222;
            v60 = *((_WORD *)FsContext + 108);
            if ( v60 != 128 && v60 != 176 )
              goto LABEL_222;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                29,
                WPP_4825f846088e3f1b9f5b83e186ef8a59_Traceguids,
                3221226659LL);
            }
            if ( (_BYTE)RefsStatusDebugEnabled )
              RefsStatusDebug(-1073740637, a1, "Read.c", 0x54Fu);
            RefsRaiseStatusInternal(a1, -1073740637, (unsigned int)v38);
LABEL_221:
            v4 = (PDEVICE_OBJECT *)a2;
            goto LABEL_222;
          }
        }
LABEL_115:
        v124 = FsContext;
        v43 = RefsAcquirePagingFastResourceShared(MdlAddress, FsContext, v130);
        v42 = v43;
        v112 = v43;
        v38 = a2;
        Process = (__int64)a2 + 720;
        goto LABEL_116;
      }
LABEL_127:
      v130[16] = FsContext;
      if ( *(_WORD *)FsContext == 2050 )
        v47 = FsContext;
      else
        v47 = (char *)*((_QWORD *)FsContext + 17);
      if ( (v130[9] & 0x200000000LL) != 0 )
      {
        if ( (_BYTE)v109 )
          __fastfail(5u);
        v46 = 0;
      }
      else
      {
        v48 = v130[9];
        if ( LODWORD(v130[9]) )
          goto LABEL_148;
        v49 = *((_QWORD *)v47 + 12);
        MsReInitializeFastOwnerEntry((struct _MS_FAST_RESOURCE_OWNER_ENTRY *)v130);
        v46 = ExAcquireFastResourceExclusive(v49, v130, (unsigned __int8)v109);
        if ( v46 )
          ++LODWORD(v130[9]);
        v16 = v132;
      }
      goto LABEL_138;
    }
    *((_DWORD *)FsContext + 46) = 0;
    goto LABEL_97;
  }
  RefsCompleteReadWriteRequest(a1, (struct REFS_IO_CONTEXT *)v4, a3, -1073739760);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_4825f846088e3f1b9f5b83e186ef8a59_Traceguids, 3221227536LL);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
    RefsStatusDebug(-1073739760, 0, "Read.c", 0x33Eu);
  return 3221227536LL;
}

```

## disassembly

```asm
0x14003b3f0  mov     [rsp+arg_8], rdx
0x14003b3f5  mov     [rsp+arg_0], rcx
0x14003b3fa  push    rbx
0x14003b3fb  push    rsi
0x14003b3fc  push    rdi
0x14003b3fd  push    r12
0x14003b3ff  push    r13
0x14003b401  push    r14
0x14003b403  push    r15
0x14003b405  sub     rsp, 1F0h
0x14003b40c  mov     rbx, r8
0x14003b40f  mov     [rsp+228h+Irp], rbx
0x14003b417  mov     r15, rdx
0x14003b41a  mov     rsi, rcx
0x14003b41d  xor     edx, edx; Val
0x14003b41f  mov     r8d, 58h ; 'X'; Size
0x14003b425  lea     rcx, [rsp+228h+var_D8]; void *
0x14003b42d  call    memset
0x14003b432  mov     [rsp+228h+var_1B8], 0
0x14003b43a  and     qword ptr [rsi+8], 0FFFFFFFFFFFFFFF7h
0x14003b43f  mov     rax, [rsi+8]
0x14003b443  mov     [rsp+228h+var_190], rax
0x14003b44b  mov     rax, [rbx+0B8h]
0x14003b452  mov     qword ptr [rsp+228h+var_140], rax
0x14003b45a  mov     rcx, [rax+30h]
0x14003b45e  mov     [rsp+228h+var_138], rcx
0x14003b466  mov     r14, [rcx+18h]
0x14003b46a  test    r14, r14
0x14003b46d  jz      short loc_14003B4C7
0x14003b46f  mov     r10, [r14+90h]
0x14003b476  mov     [rsp+228h+var_168], r10
0x14003b47e  mov     r13, [rcx+20h]
0x14003b482  mov     eax, [r10+18h]
0x14003b486  test    al, 1
0x14003b488  jnz     short loc_14003B4A8
0x14003b48a  test    r13, r13
0x14003b48d  jz      short loc_14003B49A
0x14003b48f  cmp     byte ptr [r13+50h], 4
0x14003b494  jnz     short loc_14003B49A
0x14003b496  test    al, 2
0x14003b498  jnz     short loc_14003B4A8
0x14003b49a  mov     edx, 0C000026Eh; int
0x14003b49f  mov     rcx, rsi; struct _IRP_CONTEXT *
0x14003b4a2  call    ?RefsRaiseStatusInternal@@YAXPEAU_IRP_CONTEXT@@JK@Z; RefsRaiseStatusInternal(_IRP_CONTEXT *,long,ulong)
0x14003b4a7  int     3; Trap to Debugger
0x14003b4a8  mov     r8, [r14+88h]
0x14003b4af  mov     [rsp+228h+var_160], r8
0x14003b4b7  test    r13, r13
0x14003b4ba  jnz     short loc_14003B4C0
0x14003b4bc  mov     dl, 5
0x14003b4be  jmp     short loc_14003B4E2
0x14003b4c0  movzx   edx, byte ptr [r13+50h]
0x14003b4c5  jmp     short loc_14003B4E2
0x14003b4c7  xor     r10d, r10d
0x14003b4ca  mov     [rsp+228h+var_168], r10
0x14003b4d2  xor     r8d, r8d
0x14003b4d5  mov     [rsp+228h+var_160], r8
0x14003b4dd  xor     r13d, r13d
0x14003b4e0  mov     dl, 1
0x14003b4e2  mov     byte ptr [rsp+228h+arg_18], dl
0x14003b4e9  mov     eax, [r10+18h]
0x14003b4ed  test    al, 1
0x14003b4ef  jnz     loc_14003B579
0x14003b4f5  cmp     dl, 4
0x14003b4f8  jz      short loc_14003B579
0x14003b4fa  mov     r9d, 0C000026Eh; int
0x14003b500  mov     r8, rbx; struct _IRP *
0x14003b503  mov     rdx, r15; struct REFS_IO_CONTEXT *
0x14003b506  mov     rcx, rsi; struct _IRP_CONTEXT *
0x14003b509  call    ?RefsCompleteReadWriteRequest@@YAXPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteReadWriteRequest(_IRP_CONTEXT *,REFS_IO_CONTEXT *,_IRP *,long)
0x14003b50e  lea     r15, WPP_GLOBAL_Control
0x14003b515  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b51c  cmp     rcx, r15
0x14003b51f  jz      short loc_14003B54B
0x14003b521  test    dword ptr [rcx+2Ch], 100h
0x14003b528  jz      short loc_14003B54B
0x14003b52a  cmp     byte ptr [rcx+29h], 4
0x14003b52e  jb      short loc_14003B54B
0x14003b530  mov     edx, 12h
0x14003b535  mov     r9d, 0C000026Eh
0x14003b53b  lea     r8, WPP_4825f846088e3f1b9f5b83e186ef8a59_Traceguids
0x14003b542  mov     rcx, [rcx+18h]
0x14003b546  call    WPP_SF_d
0x14003b54b  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14003b552  test    al, al
0x14003b554  jz      short loc_14003B56F
0x14003b556  mov     r9d, 326h; unsigned int
0x14003b55c  lea     r8, aReadC; "Read.c"
0x14003b563  xor     edx, edx; struct _IRP_CONTEXT *
0x14003b565  mov     ecx, 0C000026Eh; Status
0x14003b56a  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x14003b56f  mov     eax, 0C000026Eh
0x14003b574  jmp     loc_14003D161
0x14003b579  mov     r12d, [rbx+10h]
0x14003b57d  movzx   edi, r12b
0x14003b581  and     dil, 1
0x14003b585  mov     byte ptr [rsp+228h+arg_10], dil
0x14003b58d  mov     edx, [rcx+50h]
0x14003b590  mov     [rsp+228h+var_174], edx
0x14003b597  jz      loc_14003B629
0x14003b59d  test    dword ptr [r14+98h], 1000000h
0x14003b5a8  jz      short loc_14003B629
0x14003b5aa  mov     r9d, 0C0000810h; int
0x14003b5b0  mov     r8, rbx; struct _IRP *
0x14003b5b3  mov     rdx, r15; struct REFS_IO_CONTEXT *
0x14003b5b6  mov     rcx, rsi; struct _IRP_CONTEXT *
0x14003b5b9  call    ?RefsCompleteReadWriteRequest@@YAXPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteReadWriteRequest(_IRP_CONTEXT *,REFS_IO_CONTEXT *,_IRP *,long)
0x14003b5be  lea     r15, WPP_GLOBAL_Control
0x14003b5c5  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b5cc  cmp     rcx, r15
0x14003b5cf  jz      short loc_14003B5FB
0x14003b5d1  test    dword ptr [rcx+2Ch], 100h
0x14003b5d8  jz      short loc_14003B5FB
0x14003b5da  cmp     byte ptr [rcx+29h], 4
0x14003b5de  jb      short loc_14003B5FB
0x14003b5e0  mov     edx, 13h
0x14003b5e5  mov     r9d, 0C0000810h
0x14003b5eb  lea     r8, WPP_4825f846088e3f1b9f5b83e186ef8a59_Traceguids
0x14003b5f2  mov     rcx, [rcx+18h]
0x14003b5f6  call    WPP_SF_d
0x14003b5fb  movzx   ecx, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14003b602  test    cl, cl
0x14003b604  jz      short loc_14003B61F
0x14003b606  mov     r9d, 33Eh; unsigned int
0x14003b60c  lea     r8, aReadC; "Read.c"
0x14003b613  xor     edx, edx; struct _IRP_CONTEXT *
0x14003b615  mov     ecx, 0C0000810h; Status
0x14003b61a  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x14003b61f  mov     eax, 0C0000810h
0x14003b624  jmp     loc_14003D161
0x14003b629  and     r12d, 2
0x14003b62d  test    r13, r13
0x14003b630  jz      short loc_14003B6AB
0x14003b632  test    dword ptr [r13+4], 2000h
0x14003b63a  jz      short loc_14003B6AB
0x14003b63c  test    r12d, r12d
0x14003b63f  jnz     short loc_14003B6AB
0x14003b641  mov     edi, 0C000000Dh
0x14003b646  mov     r9d, edi; int
0x14003b649  mov     r8, rbx; struct _IRP *
0x14003b64c  mov     rdx, r15; struct REFS_IO_CONTEXT *
0x14003b64f  mov     rcx, rsi; struct _IRP_CONTEXT *
0x14003b652  call    ?RefsCompleteReadWriteRequest@@YAXPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteReadWriteRequest(_IRP_CONTEXT *,REFS_IO_CONTEXT *,_IRP *,long)
0x14003b657  lea     r15, WPP_GLOBAL_Control
0x14003b65e  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b665  cmp     rcx, r15
0x14003b668  jz      short loc_14003B691
0x14003b66a  test    dword ptr [rcx+2Ch], 100h
0x14003b671  jz      short loc_14003B691
0x14003b673  cmp     byte ptr [rcx+29h], 4
0x14003b677  jb      short loc_14003B691
0x14003b679  mov     edx, 14h
0x14003b67e  mov     r9d, edi
0x14003b681  lea     r8, WPP_4825f846088e3f1b9f5b83e186ef8a59_Traceguids
0x14003b688  mov     rcx, [rcx+18h]
0x14003b68c  call    WPP_SF_d
0x14003b691  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14003b698  test    al, al
0x14003b69a  jz      loc_14003D15F
0x14003b6a0  mov     r9d, 34Ah
0x14003b6a6  jmp     loc_14003D14F
0x14003b6ab  xor     ecx, ecx
0x14003b6ad  mov     [rsp+228h+var_170], ecx
0x14003b6b4  test    r13, r13
0x14003b6b7  jz      short loc_14003B6CD
0x14003b6b9  test    byte ptr [r13+58h], 8
0x14003b6be  mov     ebx, 10h
0x14003b6c3  cmovnz  ecx, ebx
0x14003b6c6  mov     [rsp+228h+var_170], ecx
0x14003b6cd  xor     edx, edx; __int64 *
0x14003b6cf  mov     rcx, r8; struct _FCB *
0x14003b6d2  call    ?RefsUpdateFileTimestampsFromNonpagedFcb@@YAEPEAU_FCB@@PEA_J@Z; RefsUpdateFileTimestampsFromNonpagedFcb(_FCB *,__int64 *)
0x14003b6d7  mov     rax, qword ptr [rsp+228h+var_140]
0x14003b6df  mov     r8d, [rax+8]
0x14003b6e3  mov     qword ptr [rsp+228h+var_180], r8
0x14003b6eb  mov     r9, [rax+18h]
0x14003b6ef  mov     [rsp+228h+var_1B0], r9
0x14003b6f4  mov     [rsp+228h+LowLimit], r9
0x14003b6fc  lea     rcx, [r8+r9]
0x14003b700  mov     [rsp+228h+var_150], rcx
0x14003b708  mov     [rsp+228h+var_148], r8d
0x14003b710  mov     r10, [rsp+228h+var_168]
0x14003b718  test    dil, dil
0x14003b71b  jz      short loc_14003B751
0x14003b71d  mov     edx, [r10+114h]
0x14003b724  dec     edx
0x14003b726  mov     eax, edx
0x14003b728  test    r9, rax
0x14003b72b  setz    cl
0x14003b72e  test    r8d, edx
0x14003b731  setz    al
0x14003b734  test    al, cl
0x14003b736  movzx   ebx, byte ptr [rsp+228h+var_1B8]
0x14003b73b  mov     eax, 20h ; ' '
0x14003b740  cmovz   ebx, eax
0x14003b743  mov     byte ptr [rsp+228h+var_1B8], bl
0x14003b747  mov     rcx, [rsp+228h+var_150]
0x14003b74f  jmp     short loc_14003B756
0x14003b751  movzx   ebx, byte ptr [rsp+228h+var_1B8]
0x14003b756  test    r13, r13
0x14003b759  jz      short loc_14003B770
0x14003b75b  cmp     byte ptr [r13+51h], 0
0x14003b760  jbe     short loc_14003B770
0x14003b762  mov     rax, 8000000000h
0x14003b76c  or      [rsi+8], rax
0x14003b770  test    r9, r9
0x14003b773  js      loc_14003D0E9
0x14003b779  cmp     r9, rcx
0x14003b77c  jg      loc_14003D0E9
0x14003b782  test    r8d, r8d
0x14003b785  jnz     short loc_14003B7AF
0x14003b787  mov     qword ptr [rsi+2B0h], 8
0x14003b792  xor     r9d, r9d; int
0x14003b795  mov     r8, [rsp+228h+Irp]; struct _IRP *
0x14003b79d  mov     rdx, r15; struct REFS_IO_CONTEXT *
0x14003b7a0  mov     rcx, rsi; struct _IRP_CONTEXT *
0x14003b7a3  call    ?RefsCompleteReadWriteRequest@@YAXPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteReadWriteRequest(_IRP_CONTEXT *,REFS_IO_CONTEXT *,_IRP *,long)
0x14003b7a8  xor     eax, eax
0x14003b7aa  jmp     loc_14003D161
0x14003b7af  mov     r11, [rsp+228h+var_190]
0x14003b7b7  and     r11b, 1
0x14003b7bb  mov     [rsp+228h+var_190], r11
0x14003b7c3  movzx   eax, byte ptr [r10+2900h]
0x14003b7cb  test    al, al
0x14003b7cd  jz      short loc_14003B83F
0x14003b7cf  mov     rax, [rsi+2B0h]
0x14003b7d6  cmp     rax, 17h
0x14003b7da  jg      short loc_14003B807
0x14003b7dc  xor     ecx, ecx; PerformanceFrequency
0x14003b7de  call    cs:__imp_KeQueryPerformanceCounter
0x14003b7e5  nop     dword ptr [rax+rax+00h]
0x14003b7ea  mov     r8, qword ptr [rsp+228h+var_180]
0x14003b7f2  mov     r9, [rsp+228h+var_1B0]
0x14003b7f7  mov     r10, [rsp+228h+var_168]
0x14003b7ff  mov     r11, [rsp+228h+var_190]
0x14003b807  mov     [rsi+2B0h], rax
0x14003b80e  test    r12d, r12d
0x14003b811  jnz     short loc_14003B81C
0x14003b813  test    dil, dil
0x14003b816  jnz     short loc_14003B81C
0x14003b818  mov     cl, 2
0x14003b81a  jmp     short loc_14003B81E
0x14003b81c  xor     cl, cl
0x14003b81e  mov     eax, 10h
0x14003b823  mov     edx, 14h
0x14003b828  test    r12d, r12d
0x14003b82b  cmovnz  eax, edx
0x14003b82e  or      al, cl
0x14003b830  or      al, r11b
0x14003b833  mov     [r15+38h], al
0x14003b837  mov     rcx, [rsp+228h+var_150]
0x14003b83f  mov     rdx, [rsp+228h+var_138]
0x14003b847  mov     eax, [rdx+50h]
0x14003b84a  bt      eax, 1Dh
0x14003b84e  jnb     short loc_14003B87D
0x14003b850  or      byte ptr [r15+38h], 1
0x14003b855  lea     rax, [rsp+228h+LowLimit]
0x14003b85d  mov     [rsp+228h+PostIrpRoutine], rax; LowLimit
0x14003b862  mov     r9, rdx
0x14003b865  mov     r8, [rsp+228h+Irp]; struct _IRP *
0x14003b86d  mov     rdx, r15; struct REFS_IO_CONTEXT *
0x14003b870  mov     rcx, rsi; struct _IRP_CONTEXT *
0x14003b873  call    RefsMinstoreRead
0x14003b878  jmp     loc_14003D161
0x14003b87d  and     [rsp+228h+var_174], 2
0x14003b885  mov     eax, [r14+98h]
0x14003b88c  test    al, 20h
0x14003b88e  jnz     short loc_14003B8A2
0x14003b890  mov     byte ptr [rsp+228h+var_190], 1
0x14003b898  or      qword ptr [rsi+8], 1
0x14003b89d  or      byte ptr [r15+38h], 1
0x14003b8a2  mov     r11d, 80h
0x14003b8a8  bt      qword ptr [rsi+8], 27h ; '''
0x14003b8ae  jnb     short loc_14003B8B3
0x14003b8b0  or      [r15], r11d
0x14003b8b3  cmp     byte ptr [rsp+228h+arg_18], 4
0x14003b8bb  jnz     loc_14003B9E8
0x14003b8c1  test    dword ptr [r13+4], 100h
0x14003b8c9  jnz     loc_14003B952
0x14003b8cf  mov     rax, [r14+20h]
0x14003b8d3  cmp     rax, r9
0x14003b8d6  jg      short loc_14003B947
0x14003b8d8  mov     edi, 0C0000011h
0x14003b8dd  mov     r9d, edi; int
0x14003b8e0  mov     r8, [rsp+228h+Irp]; struct _IRP *
0x14003b8e8  mov     rdx, r15; struct REFS_IO_CONTEXT *
0x14003b8eb  mov     rcx, rsi; struct _IRP_CONTEXT *
0x14003b8ee  call    ?RefsCompleteReadWriteRequest@@YAXPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteReadWriteRequest(_IRP_CONTEXT *,REFS_IO_CONTEXT *,_IRP *,long)
0x14003b8f3  lea     r15, WPP_GLOBAL_Control
0x14003b8fa  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b901  cmp     rcx, r15
0x14003b904  jz      short loc_14003B92D
0x14003b906  test    dword ptr [rcx+2Ch], 100h
0x14003b90d  jz      short loc_14003B92D
0x14003b90f  cmp     byte ptr [rcx+29h], 4
0x14003b913  jb      short loc_14003B92D
0x14003b915  mov     edx, 16h
0x14003b91a  mov     r9d, edi
0x14003b91d  lea     r8, WPP_4825f846088e3f1b9f5b83e186ef8a59_Traceguids
0x14003b924  mov     rcx, [rcx+18h]
  ... truncated ...
```
