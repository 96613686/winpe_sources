# RxCreateFromNetRoot

- ea: `0x140054ca0`
- end: `0x14005593f`
- name: `RxCreateFromNetRoot`
- size: `3231`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext, PIRP Irp, PIRP)`
- caller_count: `1`
- callee_count: `29`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140053400`

## callees

- `0x1400080b0`
- `0x140009b80`
- `0x14000d120`
- `0x14000d690`
- `0x14000de80`
- `0x14000df50`
- `0x14000f690`
- `0x140014e40`
- `0x140015230`
- `0x140016d40`
- `0x140016e70`
- `0x140017280`
- `0x140017310`
- `0x140017370`
- `0x140018838`
- `0x1400188e4`
- `0x140025c20`
- `0x140025d00`
- `0x140054c30`
- `0x140054ca0`
- `0x140055950`
- `0x140057660`
- `0x140058540`
- `0x14005a850`
- `0x14005c6c0`
- `0x14005cae0`
- `0x14005e810`
- `0x140065690`
- `0x14006e560`

## import_xrefs

- `ntoskrnl!IoRemoveShareAccess` at `0x14005548c`
- `ntoskrnl!IoRemoveShareAccess` at `0x14005548c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14007c9a4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14007c9a4`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005542e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005542e`
- `ntoskrnl!IoWithinStackLimits` at `0x140054f6d`
- `ntoskrnl!IoWithinStackLimits` at `0x140054f6d`
- `ntoskrnl!IoGetSymlinkSupportInformation` at `0x1400556b9`
- `ntoskrnl!IoGetSymlinkSupportInformation` at `0x1400556b9`
- `ntoskrnl!SePrivilegeCheck` at `0x1400550c8`
- `ntoskrnl!SePrivilegeCheck` at `0x14005514a`
- `ntoskrnl!SePrivilegeCheck` at `0x140055373`
- `ntoskrnl!SePrivilegeCheck` at `0x1400550c8`
- `ntoskrnl!SePrivilegeCheck` at `0x14005514a`
- `ntoskrnl!SePrivilegeCheck` at `0x140055373`
- `ntoskrnl!IoSetShareAccess` at `0x1400551ff`
- `ntoskrnl!IoSetShareAccess` at `0x1400551ff`
- `ntoskrnl!IoUpdateShareAccess` at `0x14005534b`
- `ntoskrnl!IoUpdateShareAccess` at `0x14005534b`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x14005544d`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x14005544d`
- `ntoskrnl!MmFlushImageSection` at `0x1400554f0`
- `ntoskrnl!MmFlushImageSection` at `0x1400554f0`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x140054e6e`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x140054e6e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007c97b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007c97b`

## string_xrefs

- `0x14007ac17`: `RxCreateFromNetRoot`

## pseudocode

```c
__int64 __fastcall RxCreateFromNetRoot(PRX_CONTEXT RxContext, PIRP Irp, PIRP a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r13
  PSZ FileName; // r15
  __int64 v8; // rsi
  PNON_PAGED_FCB NonPagedFcb; // rdx
  int Request; // edi
  int v11; // r9d
  PSZ v12; // rcx
  int v13; // eax
  PFCB v14; // rsi
  int SrvOpen; // eax
  struct _IO_STACK_LOCATION *v16; // rax
  PMRX_FCB pFcb; // r15
  PMRX_SRV_OPEN pRelevantSrvOpen; // r12
  PMRX_FOBX pFobx; // r13
  __int16 v20; // cx
  struct _IO_STACK_LOCATION *v21; // rdx
  ULONG_PTR v22; // r14
  LOGICAL v23; // eax
  struct _MRX_PIPE_HANDLE_INFORMATION *v24; // rdx
  PIO_SECURITY_CONTEXT SecurityContext; // rcx
  __int64 v26; // rax
  struct _SECURITY_SUBJECT_CONTEXT *v27; // rcx
  KPROCESSOR_MODE *v28; // r14
  __int16 v29; // r8
  __int16 v30; // dx
  struct _FILE_OBJECT *v31; // r13
  int v32; // eax
  int v33; // r14d
  PRDBSS_DEVICE_OBJECT RxDeviceObject; // rcx
  PFILE_OBJECT v36; // r14
  __int64 v37; // rdi
  struct _RX_CONTEXT *v38; // rsi
  PNON_PAGED_FCB v39; // rcx
  volatile LONG Lock; // eax
  UNICODE_STRING *v41; // r9
  struct _V_NET_ROOT *p_FileName; // r8
  struct _FCB *NetFcb; // rax
  struct _FCB *v44; // rsi
  __int64 v45; // rdx
  struct _MRX_SRV_OPEN_ *FcbObject; // r15
  struct _MRX_FOBX_ *v47; // rax
  ULONG v48; // r8d
  PCSTR v49; // r9
  const CHAR *CompletionRoutine; // [rsp+20h] [rbp-108h]
  ULONG CompletionRoutinea; // [rsp+20h] [rbp-108h]
  ULONG PostIrpRoutine; // [rsp+28h] [rbp-100h]
  int v53; // [rsp+50h] [rbp-D8h] BYREF
  __int16 v54; // [rsp+54h] [rbp-D4h]
  int v55; // [rsp+58h] [rbp-D0h]
  __int16 v56; // [rsp+5Ch] [rbp-CCh]
  int v57; // [rsp+60h] [rbp-C8h]
  int v58; // [rsp+64h] [rbp-C4h]
  PFCB ThisFcb; // [rsp+68h] [rbp-C0h]
  PFILE_OBJECT FileObject[2]; // [rsp+70h] [rbp-B8h] BYREF
  PSECURITY_SUBJECT_CONTEXT SubjectSecurityContext; // [rsp+80h] [rbp-A8h]
  __int64 v62; // [rsp+88h] [rbp-A0h]
  int v63; // [rsp+90h] [rbp-98h]
  ULONG DesiredShareAccess; // [rsp+94h] [rbp-94h]
  ACCESS_MASK DesiredAccess; // [rsp+98h] [rbp-90h]
  __int64 v66; // [rsp+A0h] [rbp-88h]
  __int64 v67; // [rsp+A8h] [rbp-80h]
  __int64 v68; // [rsp+B0h] [rbp-78h]
  __int64 v69; // [rsp+B8h] [rbp-70h]
  PRX_CONTEXT v70; // [rsp+C0h] [rbp-68h]
  struct _PRIVILEGE_SET RequiredPrivileges; // [rsp+C8h] [rbp-60h] BYREF

  v70 = RxContext;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  FileName = RxContext->TrackerHistory[0].FileName;
  v8 = *(_QWORD *)&RxContext->TrackerHistory[0].Flags;
  ThisFcb = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_Zqq(WPP_GLOBAL_Control->AttachedDevice, (_DWORD)Irp, (_DWORD)a3, (_DWORD)a3, (char)FileName, v8);
  }
  NonPagedFcb = RxContext->NonPagedFcb;
  if ( NonPagedFcb != *(PNON_PAGED_FCB *)(*((_QWORD *)RxContext->TrackerHistory[0].FileName + 4) + 48LL) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 43, &WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids);
    }
    Request = -1073741634;
    v33 = 2829;
    goto LABEL_101;
  }
  if ( (NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.LockNV & 0x800) == 0
    && LOBYTE(RxContext->TrackerHistory[6].AcquireRelease)
    && FileName[77] )
  {
    Request = -1073741311;
    v33 = 2840;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 44, &WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids);
    }
    goto LABEL_101;
  }
  Request = RxProcessDfsCreateRequest((__int64)RxContext);
  if ( Request < 0 )
  {
    v33 = 2853;
    goto LABEL_101;
  }
  if ( (*((_DWORD *)&RxContext->9 + 35) & 0x10000) != 0 )
  {
    Request = -1073741598;
    v33 = 2865;
    goto LABEL_101;
  }
  v12 = RxContext->TrackerHistory[1].FileName;
  if ( (*((_DWORD *)v12 + 3) & 1) != 0 )
  {
    WORD1(RxContext->TrackerHistory[4].FileName) |= 0x40u;
    LODWORD(RxContext->RdbssDbgExtension) |= 0x20000000u;
  }
  v13 = *(_DWORD *)(v8 + 184);
  if ( v13 > *((_DWORD *)v12 + 2) )
    *((_DWORD *)v12 + 2) = v13;
  if ( (*(_DWORD *)(v8 + 188) & 2) != 0 )
  {
    *((_DWORD *)&RxContext->9 + 35) |= 2u;
    CurrentStackLocation->FileObject->Flags |= 0x10u;
  }
  if ( ((FileName[77] - 1) & 0xFD) == 0 )
    RxContext->Create.PipeReadMode = 7;
  if ( (CurrentStackLocation->Flags & 4) != 0 )
  {
    v36 = Irp->Tail.Overlay.CurrentStackLocation->FileObject;
    v37 = *(_QWORD *)&RxContext->TrackerHistory[0].Flags;
    v38 = (struct _RX_CONTEXT *)RxContext->TrackerHistory[0].FileName;
    v53 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 39, &WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids, a3);
    }
    if ( (*((_DWORD *)&RxContext->9 + 28) & 0x10000) != 0 )
    {
      LOBYTE(v11) = 1;
      RxScavengeRelatedClosePendingFobxs(RxContext->NonPagedFcb, (_DWORD)v38, 1, v11, 0);
    }
    BYTE6(RxContext->TrackerHistory[4].FileName) |= 8u;
    IoGetSymlinkSupportInformation(&v53, 4);
    v39 = RxContext->NonPagedFcb;
    Lock = v39->AdvancedFcbHeaderMutex.Event.Header.Lock;
    if ( ((Lock & 0x400) != 0 && HIWORD(v53) || (Lock & 0x1000) != 0) && (*(_DWORD *)(v37 + 56) & 0x50) == 0 )
    {
      if ( v39->AdvancedFcbHeaderMutex.Event.Header.WaitListHead.Blink[18].Flink )
      {
        if ( ((__int64)RxContext->ScavengerEntry.List.Flink & 2) == 0 )
        {
          *(_OWORD *)&RxContext->MRxContext[2] = 0;
          *(_OWORD *)&RxContext->WriteOnlyOpenRetryContext = 0;
          RxContext->ResumeRoutine = 0;
          Request = ((__int64 (__fastcall *)(PRX_CONTEXT, PIRP))RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.WaitListHead.Blink[18].Flink)(
                      RxContext,
                      a3);
          if ( Request == -2147483603 )
          {
            v45 = *(_QWORD *)&RxContext->TrackerHistory[6].Flags;
            if ( v45
              && (*(_WORD *)(v45 + 6) > RxContext->CurrentIrp->Tail.Overlay.CurrentStackLocation->FileObject->FileName.Length
               || *(_DWORD *)v45 != -1610612724) )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) )
              {
                WPP_SF_q(
                  WPP_GLOBAL_Control->AttachedDevice,
                  40,
                  &WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids,
                  RxContext);
              }
              Request = -1073741629;
            }
            goto LABEL_119;
          }
        }
      }
    }
    v41 = *(UNICODE_STRING **)&RxContext->TrackerHistory[1].AcquireRelease;
    p_FileName = (struct _V_NET_ROOT *)&RxContext->TrackerHistory[7].FileName;
    if ( !v41 )
      p_FileName = 0;
    PostIrpRoutine = ((WORD1(RxContext->TrackerHistory[4].FileName) & 0x10) << 13) | 0x1000;
    LOWORD(CompletionRoutine) = RxContext->Create.Password.Length;
    NetFcb = RxCreateNetFcb(v38, a3, p_FileName, v41);
    v44 = NetFcb;
    Request = 0;
    if ( !NetFcb )
    {
LABEL_118:
      if ( v44 )
      {
LABEL_119:
        v33 = 2916;
        goto LABEL_101;
      }
LABEL_132:
      Request = -1073741670;
      goto LABEL_119;
    }
    *(_QWORD *)&RxContext->TrackerHistory[1].AcquireRelease = 0;
    Request = _RxAcquireFcb(NetFcb, RxContext, 1u, 0, CompletionRoutine, PostIrpRoutine);
    if ( Request < 0 )
    {
      ExAcquireResourceExclusiveLite(v44->Header.Resource, 1u);
      RxpDereferenceAndFinalizeNetFcb(v44, 0, 0, 0);
      goto LABEL_132;
    }
    FcbObject = (struct _MRX_SRV_OPEN_ *)RxAllocateFcbObject(
                                           *(PRDBSS_DEVICE_OBJECT *)(*(_QWORD *)&RxContext->TrackerHistory[0].AcquireRelease
                                                                   + 48LL),
                                           0xEB1Cu,
                                           (POOL_TYPE)256,
                                           0,
                                           0);
    if ( FcbObject )
    {
      v47 = (struct _MRX_FOBX_ *)RxAllocateFcbObject(
                                   *(PRDBSS_DEVICE_OBJECT *)(*(_QWORD *)&RxContext->TrackerHistory[0].AcquireRelease
                                                           + 48LL),
                                   0xEC30u,
                                   (POOL_TYPE)256,
                                   0,
                                   0);
      if ( v47 )
      {
        v47->Context2 = FcbObject;
        FcbObject->Context2 = v44;
        v44->Header.NodeTypeCode = -5084;
        BYTE5(RxContext->TrackerHistory[4].FileName) &= ~1u;
        v36->FsContext = v44;
        v36->FsContext2 = v47;
        RxContext->pFcb = (PMRX_FCB)&v44->Header;
        RxContext->pFobx = v47;
        RxContext->pRelevantSrvOpen = FcbObject;
        RxSetUpFobxForDfs((__int64)RxContext, (__int64)v47);
        _InterlockedIncrement((volatile signed __int32 *)&v44->ScavengerFinalizationList);
        _InterlockedIncrement((volatile signed __int32 *)&v44->NonPaged);
        _RxReleaseFcb(RxContext, (PMRX_FCB)&v44->Header, v48, v49, CompletionRoutinea);
        goto LABEL_118;
      }
      ExFreePoolWithTag(FcbObject, 0);
    }
    RxpDereferenceAndFinalizeNetFcb(v44, RxContext, 0, 0);
    goto LABEL_132;
  }
  v58 = 0;
  if ( ((__int64)RxContext->RdbssDbgExtension & 0x400) == 0 )
  {
    Request = RxFindOrCreateFcb(RxContext, 1);
    v55 = Request;
    if ( Request < 0 )
    {
      v33 = 2947;
      v57 = 2947;
      v14 = ThisFcb;
    }
    else
    {
      LOBYTE(RxContext->TrackerHistory[4].FileName) |= 2u;
      if ( byte_14003314D
        && (dword_140033144 & *((_DWORD *)&RxContext->9 + 28)) == dword_140033144
        && (dword_140033148 & RxContext->Create.PipeReadMode) == dword_140033148
        && (*(_OWORD *)FileObject = 0,
            RtlInitUnicodeString((PUNICODE_STRING)FileObject, &word_14003314E),
            FsRtlIsNameInExpression((PUNICODE_STRING)FileObject, &CurrentStackLocation->FileObject->FileName, 1u, 0)) )
      {
        v14 = ThisFcb;
        LOBYTE(ThisFcb->PrivateDispatchVector) = 1;
      }
      else
      {
        v14 = ThisFcb;
      }
      if ( (*((_DWORD *)&RxContext->9 + 28) & 6) != 0 )
      {
        RxDeviceObject = v14->RxDeviceObject;
        if ( RxDeviceObject->DeviceObject.AttachedDevice )
          MmFlushImageSection((PSECTION_OBJECT_POINTERS)&RxDeviceObject->DriverObject, MmFlushForWrite);
        if ( v14->RxDeviceObject->DeviceObject.AttachedDevice )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_qq(
              WPP_GLOBAL_Control->AttachedDevice,
              45,
              &WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids,
              CurrentStackLocation->FileObject,
              RxContext);
          }
          Request = -1073741757;
          v55 = -1073741757;
          v33 = 2995;
          v57 = 2995;
          goto LABEL_96;
        }
      }
      if ( SBYTE2(RxContext->TrackerHistory[4].FileName) < 0 )
        *((_DWORD *)&v14->1 + 39) |= 0x4000000u;
      Request = RxPreProcessOpen(RxContext, v14);
      v55 = Request;
      if ( Request >= 0 )
      {
        if ( RxContext->Create.PipeCompletionMode == 2
          && LODWORD(v14->ScavengerFinalizationList.Flink) + HIDWORD(v14->ScavengerFinalizationList.Flink) > 0
          && (BYTE6(RxContext->TrackerHistory[4].FileName) & 4) == 0 )
        {
          Request = -1073741771;
          v55 = -1073741771;
          v33 = 3033;
          goto LABEL_67;
        }
        FsRtlCheckOplockEx((POPLOCK)&v14->pNetRoot, Irp, 2u, 0, 0, 0);
        SrvOpen = RxCollapseOrCreateSrvOpen(RxContext);
        Request = SrvOpen;
        v55 = SrvOpen;
        if ( SrvOpen < 0 || SrvOpen == 871 || SrvOpen == 260 )
        {
          v33 = 3058;
LABEL_67:
          v57 = v33;
          goto LABEL_96;
        }
        v16 = Irp->Tail.Overlay.CurrentStackLocation;
        FileObject[0] = v16->FileObject;
        pFcb = RxContext->pFcb;
        pRelevantSrvOpen = RxContext->pRelevantSrvOpen;
        pFobx = RxContext->pFobx;
        DesiredAccess = *((_DWORD *)&RxContext->9 + 28);
        DesiredShareAccess = RxContext->Create.PipeReadMode;
        v63 = *((_DWORD *)&RxContext->9 + 35) & 0x1000;
        v20 = WORD1(RxContext->TrackerHistory[4].FileName);
        v56 = v20 & 0x2000;
        v54 = v20 & 0x20;
        v53 = (__int64)pRelevantSrvOpen->Key & 0x200;
        if ( (DesiredAccess & 0x2000000) != 0 )
          *(_DWORD *)(*(_QWORD *)(v16->Parameters.WMI.ProviderId + 8) + 20LL) = *(_DWORD *)&pRelevantSrvOpen[1].NodeTypeCode;
        v21 = Irp->Tail.Overlay.CurrentStackLocation;
        v62 = (__int64)v21;
        v22 = (ULONG_PTR)v21->FileObject;
        if ( pFcb && (HIDWORD(pFcb->SrvOpenList.Flink) & 0x20) != 0 && v22 )
          *(_DWORD *)(v22 + 80) |= 0x8000u;
        *(_QWORD *)(v22 + 24) = pFcb;
        if ( RxContext->pFobx )
        {
          v23 = IoWithinStackLimits(v22, *(__int16 *)(v22 + 2));
          v24 = (struct _MRX_PIPE_HANDLE_INFORMATION *)v22;
          if ( v23 )
            v24 = 0;
          RxContext->pFobx->PipeHandleInformation = v24;
          v21 = (struct _IO_STACK_LOCATION *)v62;
        }
        *(_QWORD *)(v22 + 32) = RxContext->pFobx;
        *(_QWORD *)(v22 + 40) = *(_QWORD *)&pFcb[1].OpenCount + 8LL;
        SecurityContext = v21->Parameters.Create.SecurityContext;
        if ( SecurityContext )
        {
          SecurityContext->AccessState->PreviouslyGrantedAccess |= SecurityContext->AccessState->RemainingDesiredAccess;
          *(_DWORD *)(*(_QWORD *)(v21->Parameters.WMI.ProviderId + 8) + 16LL) = 0;
        }
        RxSetUpFobxForDfs((__int64)RxContext, (__int64)RxContext->pFobx);
        v26 = *(_QWORD *)(*((_QWORD *)&RxContext->9 + 18) + 8LL);
        RequiredPrivileges.PrivilegeCount = 1;
        RequiredPrivileges.Control = 1;
        v67 = 18;
        RequiredPrivileges.Privilege[0].Luid = (LUID)18LL;
        RequiredPrivileges.Privilege[0].Attributes = 0;
        v27 = (struct _SECURITY_SUBJECT_CONTEXT *)(v26 + 32);
        SubjectSecurityContext = (PSECURITY_SUBJECT_CONTEXT)(v26 + 32);
        if ( (*(_DWORD *)(v26 + 20) & 0x10102) != 0 )
        {
          v28 = (char *)&RxContext->RealDevice + 4;
          if ( SePrivilegeCheck(
                 &RequiredPrivileges,
                 (PSECURITY_SUBJECT_CONTEXT)(v26 + 32),
                 BYTE4(RxContext->RealDevice)) )
          {
LABEL_41:
            *(_DWORD *)&RxContext->pFobx[1].NodeTypeCode |= 0x400u;
LABEL_42:
            RequiredPrivileges.PrivilegeCount = 1;
            RequiredPrivileges.Control = 1;
            v69 = 7;
            v62 = 7;
            RequiredPrivileges.Privilege[0].Luid = (LUID)7LL;
            RequiredPrivileges.Privilege[0].Attributes = 0;
            if ( SePrivilegeCheck(&RequiredPrivileges, SubjectSecurityContext, *v28) )
              *(_DWORD *)&RxContext->pFobx[1].NodeTypeCode |= 0x800u;
            if ( v63 )
              *(_DWORD *)&pFobx[1].NodeTypeCode |= 0x800000u;
            v29 = v56;
            if ( v56 )
              *(_DWORD *)&pFobx[1].NodeTypeCode |= 0x40000000u;
            v30 = v54;
            if ( v54 )
              *(_DWORD *)&pFobx[1].NodeTypeCode |= 0x80000000;
            if ( RxContext->TrackerHistory[0].FileName[77] == 1 )
            {
              FileObject[0]->Flags |= 0x80u;
            }
            else if ( RxContext->TrackerHistory[0].FileName[77] != 3 )
            {
              v31 = FileObject[0];
              if ( RxContext->TrackerHistory[0].FileName[77] == 5 )
                FileObject[0]->Flags |= 0x200u;
LABEL_54:
              if ( RxContext->TrackerHistory[0].FileName[77] == 1 )
              {
LABEL_63:
                if ( ((__int64)pRelevantSrvOpen->Key & 0x40000) == 0 )
                {
                  RxUpdateShareAccess(
                    (char *)pRelevantSrvOpen->Context2 + 452,
                    *(unsigned int *)&pRelevantSrvOpen[1].NodeTypeCode,
                    pRelevantSrvOpen[1].NodeReferenceCount);
                  LODWORD(pRelevantSrvOpen->Key) |= 0x40000u;
                }
                v33 = v58;
                goto LABEL_96;
              }
              if ( LODWORD(pFcb[1].Header.PagingIoResource) == 1 )
              {
                IoSetShareAccess(DesiredAccess, DesiredShareAccess, v31, (PSHARE_ACCESS)&pFcb[2].Header.PushLock);
                if ( v56 || v54 )
                  IoRemoveShareAccess(v31, (PSHARE_ACCESS)&pFcb[2].Header.PushLock);
                v32 = v53;
                if ( v53 )
                  goto LABEL_62;
                HIDWORD(pFcb->SrvOpenList.Flink) |= 0x40000u;
              }
              else
              {
                if ( !v29 && !v30 )
                  IoUpdateShareAccess(v31, (PSHARE_ACCESS)&pFcb[2].Header.PushLock);
                v32 = v53;
              }
              if ( !v32 )
                RxUpdateOplockStateOnCreate(
                  RxContext,
                  pFcb,
                  pRelevantSrvOpen,
                  RxContext->TrackerHistory[4].AcquireRelease);
LABEL_62:
              RxSetupFcbForCaching(RxContext, pFcb, v31);
              RxUpdateFcbLocalCachingState(pFcb);
              goto LABEL_63;
            }
            pFobx[1].pSrvOpen = (PMRX_SRV_OPEN)&pFobx[2].pSrvOpen;
            pFobx[2].Context = 0;
            LODWORD(pFobx[2].Context2) = *((_DWORD *)RxContext->TrackerHistory[0].FileName + 26);
            LODWORD(pFobx[2].pSrvOpen) = RxContext->TrackerHistory[3].FileName;
            HIDWORD(pFobx[2].pSrvOpen) = HIDWORD(RxContext->TrackerHistory[3].FileName);
            LODWORD(pFobx[2].AssociatedFileObject) = RxContext->TrackerHistory[3].Flags;
            pFobx[3].pSrvOpen = (PMRX_SRV_OPEN)&pFobx[3];
            pFobx[3].0 = (MRX_NORMAL_NODE_HEADER)&pFobx[3];
            pFobx[3].Context = &pFobx[3].AssociatedFileObject;
            pFobx[3].AssociatedFileObject = (PFILE_OBJECT)&pFobx[3].AssociatedFileObject;
            v30 = v54;
            v31 = FileObject[0];
            goto LABEL_54;
          }
          v27 = SubjectSecurityContext;
        }
        RequiredPrivileges.PrivilegeCount = 1;
        RequiredPrivileges.Control = 1;
        v68 = 35;
        v66 = 35;
        RequiredPrivileges.Privilege[0].Luid = (LUID)35LL;
        RequiredPrivileges.Privilege[0].Attributes = 0;
        v28 = (char *)&RxContext->RealDevice + 4;
        if ( !SePrivilegeCheck(&RequiredPrivileges, v27, BYTE4(RxContext->RealDevice)) )
          goto LABEL_42;
        goto LABEL_41;
      }
      v33 = 3012;
      v57 = 3012;
    }
LABEL_96:
    if ( v14 )
    {
      _InterlockedDecrement((volatile signed __int32 *)&v14->FileLock.LastReturnedLockInfo);
      LOBYTE(RxContext->TrackerHistory[4].FileName) &= ~2u;
      if ( Request >= 0 && Request != 871 && Request != 260 )
        goto LABEL_100;
      if ( LODWORD(v14->RxDeviceObject->DeviceLock.Header.WaitListHead.Blink) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 46, &WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids, v14);
        }
        RxProcessFcbChangeBufferingStateRequestInternal(v14);
      }
      WORD1(RxContext->TrackerHistory[4].FileName) |= 4u;
      if ( !LODWORD(v14->ScavengerFinalizationList.Flink) )
      {
        if ( RxpDereferenceAndFinalizeNetFcb(v14, RxContext, 0, 0) )
        {
          BYTE5(RxContext->TrackerHistory[4].FileName) &= ~1u;
          RxContext->pFcb = 0;
        }
      }
      else
      {
LABEL_100:
        _InterlockedDecrement((volatile signed __int32 *)&v14->1 + 38);
      }
    }
    goto LABEL_101;
  }
  FileObject[0] = 0;
  Request = RxFindOrCreateFcb(RxContext, 1);
  if ( Request >= 0 )
  {
    FileObject[0]->Type = -5082;
    _InterlockedIncrement((volatile signed __int32 *)0xC0);
    RxSetupNetFileObject(RxContext, Irp, 0);
    _InterlockedDecrement((volatile signed __int32 *)0x1E0);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qDZ(
      WPP_GLOBAL_Control->AttachedDevice,
      41,
      (unsigned int)&WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids,
      0,
      Request,
      (__int64)a3);
  }
  v33 = v58;
LABEL_101:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      47,
      &WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids,
      (unsigned int)Request,
      v33);
  }
  return (unsigned int)Request;
}

```

## disassembly

```asm
0x140054ca0  push    rbx
0x140054ca2  push    rsi
0x140054ca3  push    rdi
0x140054ca4  push    r12
0x140054ca6  push    r13
0x140054ca8  push    r14
0x140054caa  push    r15
0x140054cac  sub     rsp, 0F0h
0x140054cb3  mov     rax, cs:__security_cookie
0x140054cba  xor     rax, rsp
0x140054cbd  mov     [rsp+128h+var_48], rax
0x140054cc5  mov     r12, r8
0x140054cc8  mov     r14, rdx
0x140054ccb  mov     rbx, rcx
0x140054cce  mov     [rsp+128h+var_68], rcx
0x140054cd6  mov     r13, [rdx+0B8h]
0x140054cdd  mov     r15, [rcx+288h]
0x140054ce4  mov     rsi, [rcx+290h]
0x140054ceb  mov     [rsp+128h+ThisFcb], 0
0x140054cf4  lea     rdi, WPP_GLOBAL_Control
0x140054cfb  mov     rcx, cs:WPP_GLOBAL_Control
0x140054d02  cmp     rcx, rdi
0x140054d05  jz      short loc_140054D12
0x140054d07  mov     eax, [rcx+2Ch]
0x140054d0a  test    al, 8
0x140054d0c  jnz     loc_14005577F
0x140054d12  mov     rdx, [rbx+50h]
0x140054d16  mov     rax, [rbx+288h]
0x140054d1d  mov     rcx, [rax+20h]
0x140054d21  cmp     rdx, [rcx+30h]
0x140054d25  jnz     loc_140055640
0x140054d2b  test    dword ptr [rdx+150h], 800h
0x140054d35  jnz     short loc_140054D44
0x140054d37  cmp     byte ptr [rbx+310h], 0
0x140054d3e  jnz     loc_14007C758
0x140054d44  mov     rcx, rbx
0x140054d47  call    RxProcessDfsCreateRequest
0x140054d4c  mov     edi, eax
0x140054d4e  test    eax, eax
0x140054d50  js      loc_140055764
0x140054d56  test    dword ptr [rbx+21Ch], 10000h
0x140054d60  jnz     loc_14005576F
0x140054d66  mov     rcx, [rbx+2A0h]
0x140054d6d  mov     eax, [rcx+0Ch]
0x140054d70  test    al, 1
0x140054d72  jnz     loc_1400557D3
0x140054d78  mov     eax, [rsi+0B8h]
0x140054d7e  cmp     eax, [rcx+8]
0x140054d81  jg      loc_1400557E7
0x140054d87  mov     eax, [rsi+0BCh]
0x140054d8d  test    al, 2
0x140054d8f  jnz     loc_1400557EF
0x140054d95  movzx   eax, byte ptr [r15+4Dh]
0x140054d9a  dec     al
0x140054d9c  test    al, 0FDh
0x140054d9e  jz      loc_1400555E3
0x140054da4  test    byte ptr [r13+2], 4
0x140054da9  jnz     loc_140055660
0x140054daf  xor     r15d, r15d
0x140054db2  mov     [rsp+128h+var_C4], r15d
0x140054db7  test    dword ptr [rbx+78h], 400h
0x140054dbe  jnz     loc_140055877
0x140054dc4  mov     [rsp+128h+var_D0], 0C0000016h
0x140054dcc  mov     byte ptr [rsp+128h+CompletionRoutine], 1; char
0x140054dd1  lea     r9, [rsp+128h+ThisFcb]
0x140054dd6  mov     r8, r12
0x140054dd9  mov     rdx, r14
0x140054ddc  mov     rcx, rbx; RxContext
0x140054ddf  call    RxFindOrCreateFcb
0x140054de4  mov     edi, eax
0x140054de6  mov     [rsp+128h+var_D0], eax
0x140054dea  test    eax, eax
0x140054dec  js      loc_1400554D2
0x140054df2  or      byte ptr [rbx+2E8h], 2
0x140054df9  cmp     cs:byte_14003314D, r15b
0x140054e00  jnz     loc_1400553EA
0x140054e06  mov     rsi, [rsp+128h+ThisFcb]
0x140054e0b  mov     eax, [rbx+200h]
0x140054e11  test    al, 6
0x140054e13  jnz     loc_140055396
0x140054e19  movzx   eax, byte ptr [rbx+2EAh]
0x140054e20  test    al, al
0x140054e22  jns     short loc_140054E2E
0x140054e24  or      dword ptr [rsi+9Ch], 4000000h
0x140054e2e  mov     rdx, rsi
0x140054e31  mov     rcx, rbx
0x140054e34  call    RxPreProcessOpen
0x140054e39  mov     edi, eax
0x140054e3b  mov     [rsp+128h+var_D0], eax
0x140054e3f  test    eax, eax
0x140054e41  js      loc_140055472
0x140054e47  cmp     dword ptr [rbx+218h], 2
0x140054e4e  jz      loc_14005549D
0x140054e54  lea     rcx, [rsi+58h]; Oplock
0x140054e58  mov     [rsp+128h+PostIrpRoutine], r15; PostIrpRoutine
0x140054e5d  mov     [rsp+128h+CompletionRoutine], r15; CompletionRoutine
0x140054e62  xor     r9d, r9d; Context
0x140054e65  mov     r8d, 2; Flags
0x140054e6b  mov     rdx, r14; Irp
0x140054e6e  call    cs:__imp_FsRtlCheckOplockEx
0x140054e75  nop     dword ptr [rax+rax+00h]
0x140054e7a  mov     r8, rsi
0x140054e7d  mov     rdx, r14
0x140054e80  mov     rcx, rbx; Context
0x140054e83  call    RxCollapseOrCreateSrvOpen
0x140054e88  mov     edi, eax
0x140054e8a  mov     [rsp+128h+var_D0], eax
0x140054e8e  test    eax, eax
0x140054e90  js      loc_1400552A6
0x140054e96  cmp     eax, 367h
0x140054e9b  jz      loc_1400552A6
0x140054ea1  cmp     eax, 104h
0x140054ea6  jz      loc_1400552A6
0x140054eac  mov     rax, [r14+0B8h]
0x140054eb3  mov     rcx, [rax+30h]
0x140054eb7  mov     [rsp+128h+FileObject], rcx
0x140054ebc  mov     r15, [rbx+38h]
0x140054ec0  mov     r12, [rbx+48h]
0x140054ec4  mov     r13, [rbx+40h]
0x140054ec8  mov     r8d, [rbx+200h]
0x140054ecf  mov     [rsp+128h+DesiredAccess], r8d
0x140054ed7  mov     ecx, [rbx+214h]
0x140054edd  mov     [rsp+128h+DesiredShareAccess], ecx
0x140054ee4  mov     ecx, [rbx+21Ch]
0x140054eea  and     ecx, 1000h
0x140054ef0  mov     [rsp+128h+var_98], ecx
0x140054ef7  movzx   ecx, word ptr [rbx+2EAh]
0x140054efe  mov     r9d, 2000h
0x140054f04  movzx   edx, cx
0x140054f07  and     dx, r9w
0x140054f0b  mov     [rsp+128h+var_CC], dx
0x140054f10  and     cx, 20h
0x140054f14  mov     [rsp+128h+var_D4], cx
0x140054f19  mov     ecx, [r12+48h]
0x140054f1e  and     ecx, 200h
0x140054f24  mov     [rsp+128h+var_D8], ecx
0x140054f28  bt      r8d, 19h
0x140054f2d  jb      loc_140055539
0x140054f33  mov     rdx, [r14+0B8h]
0x140054f3a  mov     [rsp+128h+var_A0], rdx
0x140054f42  mov     r14, [rdx+30h]
0x140054f46  test    r15, r15
0x140054f49  jz      short loc_140054F5A
0x140054f4b  mov     eax, [r15+9Ch]
0x140054f52  test    al, 20h
0x140054f54  jnz     loc_14005554E
0x140054f5a  mov     [r14+18h], r15
0x140054f5e  cmp     qword ptr [rbx+40h], 0
0x140054f63  jz      short loc_140054F94
0x140054f65  movsx   rdx, word ptr [r14+2]; RegionSize
0x140054f6a  mov     rcx, r14; RegionStart
0x140054f6d  call    cs:__imp_IoWithinStackLimits
0x140054f74  nop     dword ptr [rax+rax+00h]
0x140054f79  mov     r8, [rbx+40h]
0x140054f7d  mov     rdx, r14
0x140054f80  xor     ecx, ecx
0x140054f82  test    eax, eax
0x140054f84  cmovnz  rdx, rcx
0x140054f88  mov     [r8+30h], rdx
0x140054f8c  mov     rdx, [rsp+128h+var_A0]
0x140054f94  mov     rax, [rbx+40h]
0x140054f98  mov     [r14+20h], rax
0x140054f9c  mov     rax, [r15+130h]
0x140054fa3  add     rax, 8
0x140054fa7  mov     [r14+28h], rax
0x140054fab  mov     rcx, [rdx+8]
0x140054faf  test    rcx, rcx
0x140054fb2  jz      short loc_140054FCD
0x140054fb4  mov     rcx, [rcx+8]
0x140054fb8  mov     eax, [rcx+10h]
0x140054fbb  or      [rcx+14h], eax
0x140054fbe  mov     rax, [rdx+8]
0x140054fc2  mov     rcx, [rax+8]
0x140054fc6  mov     dword ptr [rcx+10h], 0
0x140054fcd  mov     rdx, [rbx+40h]
0x140054fd1  mov     rcx, rbx
0x140054fd4  call    RxSetUpFobxForDfs
0x140054fd9  mov     rax, [rbx+220h]
0x140054fe0  mov     rax, [rax+8]
0x140054fe4  xorps   xmm0, xmm0
0x140054fe7  xor     ecx, ecx
0x140054fe9  movups  xmmword ptr [rsp+128h+RequiredPrivileges.PrivilegeCount], xmm0
0x140054ff1  mov     [rsp+128h+RequiredPrivileges.Privilege.Attributes], ecx
0x140054ff8  mov     [rsp+128h+RequiredPrivileges.PrivilegeCount], 1
0x140055003  mov     [rsp+128h+RequiredPrivileges.Control], 1
0x14005500e  xor     edx, edx
0x140055010  mov     [rsp+128h+SubjectSecurityContext], rdx
0x140055018  mov     [rsp+128h+var_80], rdx
0x140055020  mov     [rsp+128h+var_80], 12h
0x14005502c  mov     [rsp+128h+SubjectSecurityContext], 12h
0x140055038  mov     qword ptr [rsp+128h+RequiredPrivileges.Privilege.Luid.LowPart], 12h
0x140055044  mov     [rsp+128h+RequiredPrivileges.Privilege.Attributes], edx
0x14005504b  lea     rcx, [rax+20h]
0x14005504f  mov     [rsp+128h+SubjectSecurityContext], rcx
0x140055057  test    dword ptr [rax+14h], 10102h
0x14005505e  jnz     loc_140055360
0x140055064  mov     [rsp+128h+RequiredPrivileges.PrivilegeCount], 1
0x14005506f  mov     [rsp+128h+RequiredPrivileges.Control], 1
0x14005507a  mov     [rsp+128h+var_88], rdx
0x140055082  mov     [rsp+128h+var_78], rdx
0x14005508a  mov     [rsp+128h+var_78], 23h ; '#'
0x140055096  mov     [rsp+128h+var_88], 23h ; '#'
0x1400550a2  mov     qword ptr [rsp+128h+RequiredPrivileges.Privilege.Luid.LowPart], 23h ; '#'
0x1400550ae  mov     [rsp+128h+RequiredPrivileges.Privilege.Attributes], edx
0x1400550b5  lea     r14, [rbx+24h]
0x1400550b9  movzx   r8d, byte ptr [r14]; AccessMode
0x1400550bd  mov     rdx, rcx; SubjectSecurityContext
0x1400550c0  lea     rcx, [rsp+128h+RequiredPrivileges]; RequiredPrivileges
0x1400550c8  call    cs:__imp_SePrivilegeCheck
0x1400550cf  nop     dword ptr [rax+rax+00h]
0x1400550d4  test    al, al
0x1400550d6  jz      short loc_1400550E3
0x1400550d8  mov     rax, [rbx+40h]
0x1400550dc  or      dword ptr [rax+48h], 400h
0x1400550e3  mov     [rsp+128h+RequiredPrivileges.PrivilegeCount], 1
0x1400550ee  mov     [rsp+128h+RequiredPrivileges.Control], 1
0x1400550f9  xor     eax, eax
0x1400550fb  mov     [rsp+128h+var_A0], rax
0x140055103  mov     [rsp+128h+var_70], rax
0x14005510b  mov     [rsp+128h+var_70], 7
0x140055117  mov     [rsp+128h+var_A0], 7
0x140055123  mov     qword ptr [rsp+128h+RequiredPrivileges.Privilege.Luid.LowPart], 7
0x14005512f  mov     [rsp+128h+RequiredPrivileges.Privilege.Attributes], eax
0x140055136  movzx   r8d, byte ptr [r14]; AccessMode
0x14005513a  mov     rdx, [rsp+128h+SubjectSecurityContext]; SubjectSecurityContext
0x140055142  lea     rcx, [rsp+128h+RequiredPrivileges]; RequiredPrivileges
0x14005514a  call    cs:__imp_SePrivilegeCheck
0x140055151  nop     dword ptr [rax+rax+00h]
0x140055156  test    al, al
0x140055158  jz      short loc_140055165
0x14005515a  mov     rax, [rbx+40h]
0x14005515e  or      dword ptr [rax+48h], 800h
0x140055165  cmp     [rsp+128h+var_98], 0
0x14005516d  jz      short loc_140055177
0x14005516f  or      dword ptr [r13+48h], 800000h
0x140055177  movzx   r8d, [rsp+128h+var_CC]
0x14005517d  test    r8w, r8w
0x140055181  jz      short loc_14005518B
0x140055183  or      dword ptr [r13+48h], 40000000h
0x14005518b  movzx   edx, [rsp+128h+var_D4]
0x140055190  test    dx, dx
0x140055193  jz      short loc_14005519D
0x140055195  or      dword ptr [r13+48h], 80000000h
0x14005519d  mov     rax, [rbx+288h]
0x1400551a4  movzx   ecx, byte ptr [rax+4Dh]
0x1400551a8  sub     ecx, 1
0x1400551ab  jz      loc_1400552B6
0x1400551b1  sub     ecx, 2
0x1400551b4  jz      loc_1400552C2
0x1400551ba  mov     r13, [rsp+128h+FileObject]
0x1400551bf  cmp     ecx, 2
0x1400551c2  jz      loc_140055564
0x1400551c8  mov     rax, [rbx+288h]
0x1400551cf  cmp     byte ptr [rax+4Dh], 1
0x1400551d3  jz      loc_140055265
0x1400551d9  cmp     dword ptr [r15+0C0h], 1
0x1400551e1  jnz     loc_140055336
0x1400551e7  lea     r9, [r15+1A8h]; ShareAccess
0x1400551ee  mov     r8, r13; FileObject
0x1400551f1  mov     edx, [rsp+128h+DesiredShareAccess]; DesiredShareAccess
0x1400551f8  mov     ecx, [rsp+128h+DesiredAccess]; DesiredAccess
0x1400551ff  call    cs:__imp_IoSetShareAccess
0x140055206  nop     dword ptr [rax+rax+00h]
0x14005520b  cmp     [rsp+128h+var_CC], 0
0x140055211  jnz     loc_140055482
0x140055217  cmp     [rsp+128h+var_D4], 0
0x14005521d  jnz     loc_140055482
0x140055223  mov     eax, [rsp+128h+var_D8]
0x140055227  test    eax, eax
0x140055229  jnz     short loc_14005524F
0x14005522b  or      dword ptr [r15+9Ch], 40000h
0x140055236  test    eax, eax
0x140055238  jnz     short loc_14005524F
0x14005523a  mov     r9d, [rbx+2E0h]
0x140055241  mov     r8, r12
0x140055244  mov     rdx, r15
0x140055247  mov     rcx, rbx
0x14005524a  call    RxUpdateOplockStateOnCreate
0x14005524f  mov     r8, r13
0x140055252  mov     rdx, r15
0x140055255  mov     rcx, rbx
0x140055258  call    RxSetupFcbForCaching
0x14005525d  mov     rcx, r15
0x140055260  call    RxUpdateFcbLocalCachingState
0x140055265  test    dword ptr [r12+48h], 40000h
0x14005526e  jnz     short loc_140055299
0x140055270  mov     rcx, [r12+20h]
0x140055275  add     rcx, 1C4h
0x14005527c  mov     r8d, [r12+7Ch]
0x140055281  mov     edx, [r12+78h]
0x140055286  call    RxUpdateShareAccess
0x14005528b  mov     ecx, [r12+48h]
0x140055290  bts     ecx, 12h
0x140055294  mov     [r12+48h], ecx
0x140055299  mov     r14d, [rsp+128h+var_C4]
0x14005529e  xor     r15d, r15d
0x1400552a1  jmp     loc_140055571
0x1400552a6  mov     r14d, 0BF2h
0x1400552ac  mov     [rsp+128h+var_C8], r14d
0x1400552b1  jmp     loc_140055571
  ... truncated ...
```
