# RxCommonCleanup

- ea: `0x14006c5c0`
- end: `0x14006d1d3`
- name: `RxCommonCleanup`
- size: `3091`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext, PIRP Irp)`
- caller_count: `0`
- callee_count: `31`
- tags: `broker_com_uri`

## callees

- `0x140004180`
- `0x140008030`
- `0x140008190`
- `0x140009b80`
- `0x140009ea0`
- `0x14000d1e0`
- `0x14000dd90`
- `0x14000e9f0`
- `0x14000ec40`
- `0x140015230`
- `0x140016d40`
- `0x140016e20`
- `0x140017280`
- `0x140017370`
- `0x140017420`
- `0x140017f54`
- `0x14001810c`
- `0x14001816c`
- `0x140025d00`
- `0x140057660`
- `0x14005b620`
- `0x140065ee0`
- `0x140069970`
- `0x14006ba40`
- `0x14006c5c0`
- `0x14006d1e0`
- `0x14006d370`
- `0x14006d6e0`
- `0x14006f470`
- `0x140071990`
- `0x140071c90`

## import_xrefs

- `ntoskrnl!FsRtlCheckOplock` at `0x14006c8cc`
- `ntoskrnl!FsRtlCheckOplock` at `0x14007ef06`
- `ntoskrnl!FsRtlCheckOplock` at `0x14006c8cc`
- `ntoskrnl!FsRtlCheckOplock` at `0x14007ef06`
- `ntoskrnl!FsRtlFastUnlockAll` at `0x14006cb28`
- `ntoskrnl!FsRtlFastUnlockAll` at `0x14006cb28`
- `ntoskrnl!IoGetRequestorProcess` at `0x14006cb0c`
- `ntoskrnl!IoGetRequestorProcess` at `0x14006cb0c`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14007b30e`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14007b30e`
- `ntoskrnl!DbgPrint` at `0x14006ccac`
- `ntoskrnl!DbgPrint` at `0x14006ccac`
- `ntoskrnl!IoRemoveShareAccess` at `0x14006caa3`
- `ntoskrnl!IoRemoveShareAccess` at `0x14006caa3`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14006c994`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14006c994`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14006c9a5`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14006c9d2`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14006c9a5`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14006c9d2`
- `ntoskrnl!MmForceSectionClosedEx` at `0x14006c9c3`
- `ntoskrnl!MmForceSectionClosedEx` at `0x14006c9c3`
- `ntoskrnl!KeBugCheckEx` at `0x14007ee9e`
- `ntoskrnl!KeBugCheckEx` at `0x14007ee9e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006c920`
- `ntoskrnl!KeWaitForSingleObject` at `0x14007ef54`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006c920`
- `ntoskrnl!KeWaitForSingleObject` at `0x14007ef54`

## string_xrefs

- `0x14007b33f`: `RxCommonCleanup`

## pseudocode

```c
unsigned int __fastcall RxCommonCleanup(PRX_CONTEXT RxContext, PIRP Irp, __int64 a3)
{
  PFILE_OBJECT FileObject; // rdi
  ULONG_PTR FsContext; // rbx
  struct _FOBX *FsContext2; // r15
  unsigned __int16 v8; // r13
  unsigned int result; // eax
  PBOOLEAN v10; // rdx
  ULONG *p_Flags; // rdx
  int v12; // ecx
  char *v13; // r8
  char v14; // r10
  __int64 v15; // rdx
  int *v16; // r13
  ULONG v17; // r8d
  const CHAR *v18; // r9
  __int64 v19; // rax
  int v20; // r14d
  IRP *TopLevelIrp; // rdi
  int v22; // eax
  __int64 v23; // r8
  int v24; // eax
  NTSTATUS v25; // r8d
  NTSTATUS v26; // r9d
  unsigned int v27; // r13d
  struct _KPROCESS *RequestorProcess; // rax
  __int64 v29; // r8
  struct _LOWIO_CONTEXT *v30; // rdx
  __int64 v31; // r8
  char v32; // dl
  __int64 v33; // rax
  int v34; // eax
  int v35; // eax
  PERESOURCE Resource; // r13
  _DWORD *v37; // rcx
  char v38; // al
  char v39; // cl
  PVOID Context2; // rdx
  ULONG v41; // r8d
  PCSTR v42; // r9
  const CHAR *PostIrpRoutine; // [rsp+20h] [rbp-108h]
  POPLOCK_FS_PREPOST_IRP PostIrpRoutinea; // [rsp+20h] [rbp-108h]
  ULONG PostIrpRoutineb; // [rsp+20h] [rbp-108h]
  ULONG PostIrpRoutinec; // [rsp+20h] [rbp-108h]
  ULONG v47; // [rsp+28h] [rbp-100h]
  POWNER_ENTRY OwnerTable; // [rsp+28h] [rbp-100h]
  char v49; // [rsp+50h] [rbp-D8h]
  char v50; // [rsp+53h] [rbp-D5h]
  char v51; // [rsp+54h] [rbp-D4h]
  char v52; // [rsp+58h] [rbp-D0h]
  bool v53; // [rsp+60h] [rbp-C8h]
  NTSTATUS v54; // [rsp+64h] [rbp-C4h]
  ULONG *v55; // [rsp+70h] [rbp-B8h]
  ULONG *p_FobxSerialNumber; // [rsp+78h] [rbp-B0h]
  __int64 v57; // [rsp+88h] [rbp-A0h] BYREF
  struct _FOBX *v58; // [rsp+90h] [rbp-98h]
  __int64 *v59; // [rsp+98h] [rbp-90h]
  PFILE_OBJECT v60; // [rsp+A0h] [rbp-88h]
  ULONG *v61; // [rsp+A8h] [rbp-80h]
  volatile signed __int32 *v62; // [rsp+B0h] [rbp-78h]
  _DWORD *v63; // [rsp+B8h] [rbp-70h]
  PSHARE_ACCESS ShareAccess; // [rsp+C0h] [rbp-68h]
  _BYTE v65[96]; // [rsp+C8h] [rbp-60h] BYREF
  unsigned int v66; // [rsp+140h] [rbp+18h]
  char v67; // [rsp+140h] [rbp+18h]
  char v68; // [rsp+148h] [rbp+20h]

  FileObject = Irp->Tail.Overlay.CurrentStackLocation->FileObject;
  memset(v65, 0, 32);
  v57 = 0;
  if ( FileObject )
  {
    FsContext = (ULONG_PTR)FileObject->FsContext;
    FsContext2 = (struct _FOBX *)FileObject->FsContext2;
    v58 = FsContext2;
    if ( *(_WORD *)FsContext == 0xEC23 && FsContext2 )
      v8 = -5080;
    else
      v8 = *(_WORD *)FsContext;
  }
  else
  {
    FsContext = 0;
    FsContext2 = 0;
    v58 = 0;
    v8 = -5088;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    if ( FsContext2 )
      Context2 = FsContext2->Context2;
    else
      Context2 = 0;
    v47 = (unsigned int)FsContext2;
    PostIrpRoutine = (const CHAR *)FileObject;
    WPP_SF_qqqqqDD(WPP_GLOBAL_Control->AttachedDevice, Context2, a3, RxContext);
  }
  if ( (*(_DWORD *)(FsContext + 156) & 0x1000) != 0 || !FsContext2 )
  {
    if ( *(int *)(FsContext + 184) > 0 )
      _InterlockedDecrement((volatile signed __int32 *)(FsContext + 184));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, &WPP_62be9881804536e6c54be111b50a5a79_Traceguids);
    }
    return 0;
  }
  if ( (unsigned __int16)(v8 + 5088) > 2u && v8 != 0xEC27 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, 12, &WPP_62be9881804536e6c54be111b50a5a79_Traceguids);
    }
    KeBugCheckEx(0x27u, 0xC1EE00CF, v8, 0, 0);
  }
  result = _RxAcquireFcb((PFCB)FsContext, RxContext, 1u, 0, PostIrpRoutine, v47);
  v66 = result;
  if ( !result )
  {
    v53 = 0;
    if ( *(_QWORD *)(FsContext + 712) && (*(_DWORD *)(FsContext + 736) & 2) != 0 )
      v53 = *(_QWORD *)(*(_QWORD *)(FsContext + 304) + 8LL) != 0;
    RxCloseFileObjectForTurboIo(FileObject, FsContext);
    RxMarkFobxOnCleanup(FsContext2, v10);
    p_Flags = &FileObject->Flags;
    v55 = &FileObject->Flags;
    if ( (FileObject->Flags & 0x1000) != 0 )
      *((_DWORD *)FsContext2->Context2 + 18) |= 0x800u;
    v12 = *(_DWORD *)(FsContext + 156);
    if ( (v12 & 0x80u) != 0 )
    {
      _InterlockedDecrement((volatile signed __int32 *)(FsContext + 184));
      if ( (*p_Flags & 8) != 0 )
        --*(_DWORD *)(FsContext + 188);
      if ( (FsContext2->FobxSerialNumber & 0x200) == 0 )
        __int2c();
      --*((_DWORD *)FsContext2->Context2 + 22);
      if ( (FsContext2->FobxSerialNumber & 0x40000000) != 0 )
        --*((_DWORD *)FsContext2->Context2 + 24);
      *p_Flags |= 0x4000u;
      FsContext2->FobxSerialNumber |= 0x400000u;
      RxSelectAndSwitchPagingFileObject(FsContext, 0, 0, 2u);
      FsRtlCheckOplock((POPLOCK)(FsContext + 88), Irp, RxContext, 0, 0);
      RxUninitializeCacheMap(RxContext, FileObject, 0, v65);
      _RxReleaseFcb(RxContext, (PMRX_FCB)FsContext, v41, v42, PostIrpRoutinec);
      RxReleaseLViewRundown(RxContext);
      KeWaitForSingleObject(&v65[8], Executive, 0, 0, 0);
    }
    else
    {
      v61 = &FileObject->Flags;
      v54 = 0;
      v60 = FileObject;
      v59 = 0;
      v13 = (char *)&RxContext->9 + 120;
      v51 = 0;
      v49 = 0;
      v52 = 0;
      LOBYTE(p_Flags) = 0;
      v67 = 0;
      v14 = *(_BYTE *)(*(_QWORD *)(FsContext + 120) + 77LL);
      v68 = v14;
      p_FobxSerialNumber = &FsContext2->FobxSerialNumber;
      if ( (FsContext2->FobxSerialNumber & 0x800000) != 0 )
      {
        v12 |= 1u;
        *(_DWORD *)(FsContext + 156) = v12;
      }
      if ( (v12 & 1) != 0 )
      {
        RxPurgeConflictingSrvOpensEx(FsContext);
        LOBYTE(p_Flags) = 0;
        v13 = (char *)&RxContext->9 + 120;
        v14 = v68;
      }
      if ( (unsigned __int16)(v8 + 5088) <= 1u )
      {
        RxCancelNotifyChangeDirectoryRequestsForFobxOnCleanup(FsContext2, p_Flags, v13);
        LOBYTE(p_Flags) = 0;
        v13 = (char *)&RxContext->9 + 120;
        v14 = v68;
      }
      ShareAccess = (PSHARE_ACCESS)(FsContext + 424);
      v63 = (_DWORD *)(FsContext + 184);
      v62 = (volatile signed __int32 *)(FsContext + 184);
      if ( *(_DWORD *)(FsContext + 184) == 1 )
      {
        v49 = 1;
        LOBYTE(p_Flags) = *(_BYTE *)(FsContext + 156) & 1;
        v67 = (char)p_Flags;
      }
      v50 = (char)p_Flags;
      if ( v14 == 4 || !v14 )
      {
        if ( v8 == 0xEC22 )
        {
          *((_WORD *)v13 + 1) |= 2u;
          RequestorProcess = IoGetRequestorProcess(Irp);
          FsRtlFastUnlockAll((PFILE_LOCK)(FsContext + 536), FileObject, RequestorProcess, RxContext);
          v30 = (struct _LOWIO_CONTEXT *)((char *)&RxContext->9 + 120);
          if ( *((_QWORD *)&RxContext->9 + 17)
            && ((*(_DWORD *)(FsContext + 164) & 4) == 0 || *(_BYTE *)(FsContext + 640)) )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_qq(
                WPP_GLOBAL_Control->AttachedDevice,
                14,
                &WPP_62be9881804536e6c54be111b50a5a79_Traceguids,
                FileObject,
                FsContext);
              v30 = (struct _LOWIO_CONTEXT *)((char *)&RxContext->9 + 120);
            }
            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
            {
              Resource = v30->Resource;
              if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                while ( Resource )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                  {
                    OwnerTable = Resource->OwnerTable;
                    PostIrpRoutinea = *(POPLOCK_FS_PREPOST_IRP *)&Resource->ActiveCount;
                    WPP_SF_diiD(
                      WPP_GLOBAL_Control->AttachedDevice,
                      v30,
                      v29,
                      LODWORD(Resource->SystemResourcesList.Blink));
                  }
                  Resource = (PERESOURCE)Resource->SystemResourcesList.Flink;
                }
                v30 = (struct _LOWIO_CONTEXT *)((char *)&RxContext->9 + 120);
              }
            }
            RxInitializeLowIoContext(RxContext, 5u, v30);
            *((_DWORD *)&RxContext->9 + 36) = 0;
            RxLowIoLockControlShell(RxContext, Irp, (PFCB)FsContext);
          }
          RxAdjustFileTimesAndSize(RxContext, FileObject, FsContext, FsContext2);
          if ( v49 )
          {
            v32 = v67;
            if ( v67 )
            {
              LOBYTE(v31) = 1;
              RxAcquirePagingIoResource(RxContext, FsContext, v31);
              *(_QWORD *)(FsContext + 32) = 0;
              *(_QWORD *)(FsContext + 40) = 0;
              RxReleasePagingIoResource(RxContext, FsContext);
              v32 = v67;
            }
            else if ( (*(_DWORD *)(FsContext + 156) & 4) == 0 )
            {
              v33 = *(_QWORD *)(FsContext + 32);
              if ( *(_QWORD *)(FsContext + 40) < v33 )
                *(_QWORD *)(FsContext + 40) = v33;
            }
            if ( (*(_DWORD *)(FsContext + 156) & 2) != 0 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, &WPP_62be9881804536e6c54be111b50a5a79_Traceguids);
                v32 = v67;
              }
              if ( *(_QWORD *)(RxContext->pFcb[2].Header.ValidDataLength.QuadPart + 96)
                && ((__int64)RxContext->ScavengerEntry.List.Flink & 2) == 0 )
              {
                *(_OWORD *)&RxContext->MRxContext[2] = 0;
                *(_OWORD *)&RxContext->WriteOnlyOpenRetryContext = 0;
                RxContext->ResumeRoutine = 0;
                (*(void (__fastcall **)(PRX_CONTEXT))(RxContext->pFcb[2].Header.ValidDataLength.QuadPart + 96))(RxContext);
                v32 = v67;
              }
              v57 = *(_QWORD *)(FsContext + 32);
              v59 = &v57;
              *(_DWORD *)(FsContext + 156) &= ~2u;
            }
          }
          else
          {
            v32 = v67;
          }
          if ( v49 )
          {
            if ( v32
              || (v34 = *(_DWORD *)(FsContext + 164), (v34 & 0x10) == 0) && (v34 & 0x20) == 0
              || (*(_DWORD *)(FsContext + 160) & 0x800) == 0
              || (*((_DWORD *)FsContext2->Context2 + 18) & 0x1000) != 0
              && *(struct _FOBX **)(FsContext + 488) == FsContext2 )
            {
              v52 = 1;
            }
          }
          v35 = *(_DWORD *)(FsContext + 164);
          if ( (v35 & 1) != 0 && (v35 & 0x10) == 0 && (v35 & 0x20) == 0 && (v35 & 2) == 0 )
          {
            v37 = FsContext2->Context2;
            if ( v37[22] == 1 )
            {
              v38 = RxDoesOplockStateChangeOnSrvOpenClose(v37, 0);
              v39 = v52;
              if ( v38 )
                v39 = 1;
              v52 = v39;
            }
          }
          v51 = 1;
        }
      }
      else if ( v14 == 1 || v14 == 3 )
      {
        RxCleanupPipeQueues(RxContext, FsContext, FsContext2);
      }
      _InterlockedDecrement(v62);
      if ( (*v55 & 8) != 0 )
        --*(_DWORD *)(FsContext + 188);
      _InterlockedAnd((volatile signed __int32 *)&RxContext->ScavengerEntry, 0xFFFFFFFD);
      RxCleanupFobxForMiniRdr(RxContext);
      --*((_DWORD *)FsContext2->Context2 + 22);
      v16 = (int *)&FsContext2->FobxSerialNumber;
      if ( (*p_FobxSerialNumber & 0x40000000) != 0 )
        --*((_DWORD *)FsContext2->Context2 + 24);
      *p_FobxSerialNumber |= 0x400000u;
      if ( *(_QWORD *)(*(_QWORD *)(FsContext + 304) + 8LL) || !v67 && v52 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, &WPP_62be9881804536e6c54be111b50a5a79_Traceguids);
        }
        LOBYTE(v15) = 1;
        v24 = RxFlushFcbInSystemCacheEx(FsContext, v15, 0);
        v27 = v24;
        if ( v24 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            LOBYTE(PostIrpRoutinea) = v24;
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              18,
              &WPP_62be9881804536e6c54be111b50a5a79_Traceguids,
              FsContext);
          }
          RxCcLogError((PDEVICE_OBJECT)FsContext, (PUNICODE_STRING)v27, v25, v26, (UCHAR)PostIrpRoutinea, OwnerTable);
        }
        v16 = (int *)&FsContext2->FobxSerialNumber;
      }
      RxSelectAndSwitchPagingFileObject(FsContext, 0, 0, 2u);
      if ( (*v55 & 8) == 0
        && (v22 = *(_DWORD *)(FsContext + 188)) != 0
        && v22 == *v63
        && *(_QWORD *)(*(_QWORD *)(FsContext + 304) + 8LL)
        || v67
        || v52 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, &WPP_62be9881804536e6c54be111b50a5a79_Traceguids);
        }
        v54 = RxPurgeFcbInSystemCache((PFCB)FsContext, 0, 0, 0, v50 ^ 1);
        if ( v67 )
        {
          LOBYTE(v23) = 1;
          RxFcbScavengeRelatedFobxs(FsContext, 0, v23);
        }
      }
      if ( ShareAccess && !v68 && *v16 >= 0 && (*v16 & 0x40000002) == 0 )
        IoRemoveShareAccess(FileObject, ShareAccess);
      *v55 |= 0x4000u;
      FsRtlCheckOplock((POPLOCK)(FsContext + 88), Irp, RxContext, 0, 0);
      if ( v51 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, &WPP_62be9881804536e6c54be111b50a5a79_Traceguids);
        }
        RxUninitializeCacheMap(RxContext, FileObject, v59, v65);
      }
      _RxReleaseFcb(RxContext, (PMRX_FCB)FsContext, v17, v18, PostIrpRoutineb);
      RxReleaseLViewRundown(RxContext);
      if ( v51 )
        KeWaitForSingleObject(&v65[8], Executive, 0, 0, 0);
      if ( v53 || v52 && (v54 < 0 || *(_QWORD *)(*(_QWORD *)(FsContext + 304) + 24LL)) )
      {
        v19 = *(_QWORD *)(FsContext + 304);
        v20 = *(_QWORD *)(v19 + 8) != 0;
        if ( *(_QWORD *)(v19 + 24) )
          v20 |= 2u;
        if ( v20 )
        {
          TopLevelIrp = IoGetTopLevelIrp();
          IoSetTopLevelIrp(0);
          MmForceSectionClosedEx(*(_QWORD *)(FsContext + 304) + 8LL, v20 | 4u);
          IoSetTopLevelIrp(TopLevelIrp);
        }
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 21, &WPP_62be9881804536e6c54be111b50a5a79_Traceguids, 0);
    }
    return 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, &WPP_62be9881804536e6c54be111b50a5a79_Traceguids, result);
    return v66;
  }
  return result;
}

```

## disassembly

```asm
0x14006c5c0  mov     r11, rsp
0x14006c5c3  mov     [r11+10h], rdx
0x14006c5c7  mov     [r11+8], rcx
0x14006c5cb  push    rbx
0x14006c5cc  push    rsi
0x14006c5cd  push    rdi
0x14006c5ce  push    r12
0x14006c5d0  push    r13
0x14006c5d2  push    r14
0x14006c5d4  push    r15
0x14006c5d6  sub     rsp, 0F0h
0x14006c5dd  mov     r14, rdx
0x14006c5e0  mov     rsi, rcx
0x14006c5e3  mov     rax, [rdx+0B8h]
0x14006c5ea  mov     rdi, [rax+30h]
0x14006c5ee  xorps   xmm0, xmm0
0x14006c5f1  movups  xmmword ptr [r11-60h], xmm0
0x14006c5f6  movups  xmmword ptr [r11-50h], xmm0
0x14006c5fb  mov     qword ptr [r11-0A0h], 0
0x14006c606  test    rdi, rdi
0x14006c609  jz      loc_14006D0EC
0x14006c60f  mov     rbx, [rdi+18h]
0x14006c613  mov     [rsp+128h+var_A8], rbx
0x14006c61b  mov     r15, [rdi+20h]
0x14006c61f  mov     [rsp+128h+var_98], r15
0x14006c627  movzx   eax, word ptr [rbx]
0x14006c62a  mov     ecx, 0EC23h
0x14006c62f  cmp     ax, cx
0x14006c632  jz      loc_14006D06F
0x14006c638  movzx   r13d, ax
0x14006c63c  lea     r12, WPP_GLOBAL_Control
0x14006c643  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c64a  cmp     rcx, r12
0x14006c64d  jnz     loc_14006CFF0
0x14006c653  test    dword ptr [rbx+9Ch], 1000h
0x14006c65d  jnz     loc_14006D017
0x14006c663  test    r15, r15
0x14006c666  jz      loc_14006D017
0x14006c66c  mov     eax, 13E0h
0x14006c671  add     eax, r13d
0x14006c674  cmp     ax, 2
0x14006c678  ja      loc_14007EE3A
0x14006c67e  xor     r9d, r9d; LineNumber
0x14006c681  mov     r8d, 1; Mode
0x14006c687  mov     rdx, rsi; RxContext
0x14006c68a  mov     rcx, rbx; Fcb
0x14006c68d  call    __RxAcquireFcb
0x14006c692  mov     [rsp+128h+arg_10], eax
0x14006c699  test    eax, eax
0x14006c69b  jnz     loc_14006D083
0x14006c6a1  xor     cl, cl
0x14006c6a3  mov     [rsp+128h+var_C8], ecx
0x14006c6a7  mov     [rsp+128h+var_D6], cl
0x14006c6ab  cmp     qword ptr [rbx+2C8h], 0
0x14006c6b3  jnz     loc_14006D10C
0x14006c6b9  mov     rdx, rbx
0x14006c6bc  mov     rcx, rdi
0x14006c6bf  call    RxCloseFileObjectForTurboIo
0x14006c6c4  mov     rcx, r15; pFobx
0x14006c6c7  call    RxMarkFobxOnCleanup
0x14006c6cc  lea     rdx, [rdi+50h]
0x14006c6d0  mov     [rsp+128h+var_B8], rdx
0x14006c6d5  test    dword ptr [rdx], 1000h
0x14006c6db  jnz     loc_14006D13E
0x14006c6e1  mov     ecx, [rbx+9Ch]
0x14006c6e7  test    cl, cl
0x14006c6e9  js      loc_14006D14E
0x14006c6ef  mov     [rsp+128h+var_80], rdx
0x14006c6f7  mov     [rsp+128h+var_C4], 0
0x14006c6ff  mov     [rsp+128h+var_88], rdi
0x14006c707  mov     [rsp+128h+var_90], 0
0x14006c713  lea     r8, [rsi+208h]
0x14006c71a  mov     [rsp+128h+var_D4], 0
0x14006c71f  mov     [rsp+128h+var_D8], 0
0x14006c724  xor     r9b, r9b
0x14006c727  mov     [rsp+128h+var_D0], r9d
0x14006c72c  mov     [rsp+128h+var_D7], r9b
0x14006c731  xor     dl, dl
0x14006c733  mov     byte ptr [rsp+128h+arg_10], dl
0x14006c73a  mov     [rsp+128h+var_D3], 1
0x14006c73f  mov     rax, [rbx+78h]
0x14006c743  movzx   r10d, byte ptr [rax+4Dh]
0x14006c748  mov     [rsp+128h+arg_18], r10b
0x14006c750  mov     [rsp+128h+var_D2], r10b
0x14006c755  lea     rax, [r15+48h]
0x14006c759  mov     [rsp+128h+var_B0], rax
0x14006c75e  test    dword ptr [rax], 800000h
0x14006c764  jnz     loc_14006D16A
0x14006c76a  test    cl, 1
0x14006c76d  jnz     loc_14006D178
0x14006c773  mov     eax, 13E0h
0x14006c778  add     eax, r13d
0x14006c77b  cmp     ax, 1
0x14006c77f  jbe     loc_14006D0CD
0x14006c785  lea     rax, [rbx+1A8h]
0x14006c78c  mov     [rsp+128h+ShareAccess], rax
0x14006c794  lea     rax, [rbx+0B8h]
0x14006c79b  mov     [rsp+128h+var_70], rax
0x14006c7a3  mov     [rsp+128h+var_78], rax
0x14006c7ab  cmp     dword ptr [rax], 1
0x14006c7ae  jz      loc_14006D054
0x14006c7b4  mov     [rsp+128h+var_D5], dl
0x14006c7b8  mov     [rsp+128h+var_D1], dl
0x14006c7bc  movzx   ecx, r10b
0x14006c7c0  cmp     ecx, 4
0x14006c7c3  jz      loc_14006CAF4
0x14006c7c9  test    r10b, r10b
0x14006c7cc  jz      loc_14006CAF4
0x14006c7d2  sub     ecx, 1
0x14006c7d5  jz      loc_14006CD8E
0x14006c7db  cmp     ecx, 2
0x14006c7de  jz      loc_14006CD8E
0x14006c7e4  mov     rax, [rsp+128h+var_78]
0x14006c7ec  lock dec dword ptr [rax]
0x14006c7ef  mov     rax, [rsp+128h+var_B8]
0x14006c7f4  mov     eax, [rax]
0x14006c7f6  test    al, 8
0x14006c7f8  jz      short loc_14006C800
0x14006c7fa  dec     dword ptr [rbx+0BCh]
0x14006c800  lock and dword ptr [rsi+80h], 0FFFFFFFDh
0x14006c808  mov     r9, r15
0x14006c80b  mov     r8, [r15+20h]
0x14006c80f  mov     rdx, rbx
0x14006c812  mov     rcx, rsi; RxContext
0x14006c815  call    RxCleanupFobxForMiniRdr
0x14006c81a  mov     [rsp+128h+var_CC], eax
0x14006c81e  mov     rax, [r15+20h]
0x14006c822  dec     dword ptr [rax+58h]
0x14006c825  mov     r13, [rsp+128h+var_B0]
0x14006c82a  test    dword ptr [r13+0], 40000000h
0x14006c832  jnz     loc_14006CEEB
0x14006c838  or      dword ptr [r13+0], 400000h
0x14006c840  mov     rax, [rbx+130h]
0x14006c847  movzx   r15d, byte ptr [rsp+128h+arg_10]
0x14006c850  cmp     qword ptr [rax+8], 0
0x14006c855  jnz     loc_14006CABF
0x14006c85b  test    r15b, r15b
0x14006c85e  jz      loc_14006CAB4
0x14006c864  mov     r9d, 2
0x14006c86a  xor     r8d, r8d
0x14006c86d  xor     edx, edx
0x14006c86f  mov     rcx, rbx; BugCheckParameter3
0x14006c872  call    RxSelectAndSwitchPagingFileObject
0x14006c877  mov     rcx, [rsp+128h+var_B8]
0x14006c87c  mov     eax, [rcx]
0x14006c87e  test    al, 8
0x14006c880  jz      loc_14006C9E3
0x14006c886  test    r15b, r15b
0x14006c889  jnz     loc_14006CA13
0x14006c88f  cmp     byte ptr [rsp+128h+var_D0], r15b
0x14006c894  jnz     loc_14006CA13
0x14006c89a  mov     rdx, [rsp+128h+ShareAccess]; ShareAccess
0x14006c8a2  test    rdx, rdx
0x14006c8a5  jnz     loc_14006CA7B
0x14006c8ab  mov     rax, [rsp+128h+var_B8]
0x14006c8b0  or      dword ptr [rax], 4000h
0x14006c8b6  lea     rcx, [rbx+58h]; Oplock
0x14006c8ba  mov     [rsp+128h+PostIrpRoutine], 0; SerialNumber
0x14006c8c3  xor     r9d, r9d; CompletionRoutine
0x14006c8c6  mov     r8, rsi; Context
0x14006c8c9  mov     rdx, r14; Irp
0x14006c8cc  call    cs:__imp_FsRtlCheckOplock
0x14006c8d3  nop     dword ptr [rax+rax+00h]
0x14006c8d8  movzx   r14d, [rsp+128h+var_D4]
0x14006c8de  test    r14b, r14b
0x14006c8e1  jnz     loc_14006CF6D
0x14006c8e7  xor     r15b, r15b
0x14006c8ea  mov     [rsp+128h+var_D3], r15b
0x14006c8ef  mov     rdx, rbx; MrxFcb
0x14006c8f2  mov     rcx, rsi; RxContext
0x14006c8f5  call    __RxReleaseFcb
0x14006c8fa  mov     rcx, rsi
0x14006c8fd  call    RxReleaseLViewRundown
0x14006c902  test    r14b, r14b
0x14006c905  jz      short loc_14006C92C
0x14006c907  mov     [rsp+128h+PostIrpRoutine], 0; Timeout
0x14006c910  xor     r9d, r9d; Alertable
0x14006c913  xor     r8d, r8d; WaitMode
0x14006c916  xor     edx, edx; WaitReason
0x14006c918  lea     rcx, [rsp+128h+Object]; Object
0x14006c920  call    cs:__imp_KeWaitForSingleObject
0x14006c927  nop     dword ptr [rax+rax+00h]
0x14006c92c  cmp     byte ptr [rsp+128h+var_C8], r15b
0x14006c931  jnz     short loc_14006C957
0x14006c933  cmp     byte ptr [rsp+128h+var_D0], r15b
0x14006c938  jz      loc_14006CFBB
0x14006c93e  cmp     [rsp+128h+var_C4], 0
0x14006c943  jl      short loc_14006C957
0x14006c945  mov     rax, [rbx+130h]
0x14006c94c  cmp     qword ptr [rax+18h], 0
0x14006c951  jz      loc_14006CFBB
0x14006c957  mov     [rsp+128h+var_C0], 0
0x14006c95f  mov     rax, [rbx+130h]
0x14006c966  xor     r14d, r14d
0x14006c969  cmp     [rax+8], r14
0x14006c96d  mov     ecx, 1
0x14006c972  cmovnz  r14d, ecx
0x14006c976  mov     [rsp+128h+var_C0], r14d
0x14006c97b  cmp     qword ptr [rax+18h], 0
0x14006c980  jz      short loc_14006C98B
0x14006c982  or      r14d, 2
0x14006c986  mov     [rsp+128h+var_C0], r14d
0x14006c98b  test    r14d, r14d
0x14006c98e  jz      loc_14006CFBB
0x14006c994  call    cs:__imp_IoGetTopLevelIrp
0x14006c99b  nop     dword ptr [rax+rax+00h]
0x14006c9a0  mov     rdi, rax
0x14006c9a3  xor     ecx, ecx; Irp
0x14006c9a5  call    cs:__imp_IoSetTopLevelIrp
0x14006c9ac  nop     dword ptr [rax+rax+00h]
0x14006c9b1  or      r14d, 4
0x14006c9b5  mov     rcx, [rbx+130h]
0x14006c9bc  add     rcx, 8
0x14006c9c0  mov     edx, r14d
0x14006c9c3  call    cs:__imp_MmForceSectionClosedEx
0x14006c9ca  nop     dword ptr [rax+rax+00h]
0x14006c9cf  mov     rcx, rdi; Irp
0x14006c9d2  call    cs:__imp_IoSetTopLevelIrp
0x14006c9d9  nop     dword ptr [rax+rax+00h]
0x14006c9de  jmp     loc_14006CFBB
0x14006c9e3  mov     eax, [rbx+0BCh]
0x14006c9e9  test    eax, eax
0x14006c9eb  jz      loc_14006C886
0x14006c9f1  mov     rcx, [rsp+128h+var_70]
0x14006c9f9  cmp     eax, [rcx]
0x14006c9fb  jnz     loc_14006C886
0x14006ca01  mov     rax, [rbx+130h]
0x14006ca08  cmp     qword ptr [rax+8], 0
0x14006ca0d  jz      loc_14006C886
0x14006ca13  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ca1a  cmp     rcx, r12
0x14006ca1d  jz      short loc_14006CA41
0x14006ca1f  mov     eax, [rcx+2Ch]
0x14006ca22  test    al, 8
0x14006ca24  jz      short loc_14006CA41
0x14006ca26  cmp     byte ptr [rcx+29h], 4
0x14006ca2a  jb      short loc_14006CA41
0x14006ca2c  mov     edx, 13h
0x14006ca31  lea     r8, WPP_62be9881804536e6c54be111b50a5a79_Traceguids
0x14006ca38  mov     rcx, [rcx+18h]
0x14006ca3c  call    WPP_SF_
0x14006ca41  movzx   eax, [rsp+128h+var_D5]
0x14006ca46  xor     al, 1
0x14006ca48  mov     byte ptr [rsp+128h+PostIrpRoutine], al; FlushFile
0x14006ca4c  xor     r9d, r9d; UninitializeCacheMaps
0x14006ca4f  xor     r8d, r8d; Length
0x14006ca52  xor     edx, edx; FileOffset
0x14006ca54  mov     rcx, rbx; Fcb
0x14006ca57  call    RxPurgeFcbInSystemCache
0x14006ca5c  mov     [rsp+128h+var_C4], eax
0x14006ca60  test    r15b, r15b
0x14006ca63  jz      loc_14006C89A
0x14006ca69  mov     r8b, 1
0x14006ca6c  xor     edx, edx
0x14006ca6e  mov     rcx, rbx
0x14006ca71  call    RxFcbScavengeRelatedFobxs
0x14006ca76  jmp     loc_14006C89A
0x14006ca7b  cmp     [rsp+128h+arg_18], 0
0x14006ca83  jnz     loc_14006C8AB
0x14006ca89  mov     eax, [r13+0]
0x14006ca8d  test    eax, eax
0x14006ca8f  js      loc_14006C8AB
0x14006ca95  test    eax, 40000002h
0x14006ca9a  jnz     loc_14006C8AB
0x14006caa0  mov     rcx, rdi; FileObject
0x14006caa3  call    cs:__imp_IoRemoveShareAccess
0x14006caaa  nop     dword ptr [rax+rax+00h]
0x14006caaf  jmp     loc_14006C8AB
0x14006cab4  cmp     byte ptr [rsp+128h+var_D0], 0
0x14006cab9  jz      loc_14006C864
0x14006cabf  mov     rcx, cs:WPP_GLOBAL_Control
0x14006cac6  cmp     rcx, r12
0x14006cac9  jnz     loc_14006CEF7
0x14006cacf  xor     r9d, r9d
0x14006cad2  xor     r8d, r8d
0x14006cad5  mov     dl, 1
0x14006cad7  mov     rcx, rbx
0x14006cada  call    RxFlushFcbInSystemCacheEx
0x14006cadf  mov     r13d, eax
0x14006cae2  test    eax, eax
0x14006cae4  js      loc_14006CF26
0x14006caea  mov     r13, [rsp+128h+var_B0]
0x14006caef  jmp     loc_14006C864
0x14006caf4  mov     eax, 0EC22h
0x14006caf9  cmp     r13w, ax
0x14006cafd  jnz     loc_14006C7E4
0x14006cb03  or      word ptr [r8+2], 2
0x14006cb09  mov     rcx, r14; Irp
0x14006cb0c  call    cs:__imp_IoGetRequestorProcess
0x14006cb13  nop     dword ptr [rax+rax+00h]
0x14006cb18  mov     r8, rax; ProcessId
0x14006cb1b  lea     rcx, [rbx+218h]; FileLock
0x14006cb22  mov     r9, rsi; Context
0x14006cb25  mov     rdx, rdi; FileObject
0x14006cb28  call    cs:__imp_FsRtlFastUnlockAll
0x14006cb2f  nop     dword ptr [rax+rax+00h]
0x14006cb34  lea     rdx, [rsi+208h]
0x14006cb3b  cmp     qword ptr [rdx+10h], 0
0x14006cb40  jnz     loc_14006CDA1
0x14006cb46  mov     r9, r15
  ... truncated ...
```
