# RxProcessBatchedWrite

- ea: `0x14004b370`
- end: `0x14004b9a7`
- name: `RxProcessBatchedWrite`
- size: `1591`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext, PIRP, struct _FCB *MrxFcb)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140045410`

## callees

- `0x140008030`
- `0x140008190`
- `0x140009b80`
- `0x140017220`
- `0x140017280`
- `0x140017370`
- `0x14001810c`
- `0x14004adc0`
- `0x14004b370`
- `0x14004b9b0`
- `0x14004ba48`
- `0x14004baf4`
- `0x14004bca0`
- `0x140057660`
- `0x140067ad0`
- `0x140069970`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14004b906`
- `ntoskrnl!ExAllocatePool2` at `0x14004b906`
- `ntoskrnl!FsRtlCheckOplock` at `0x14004b61d`
- `ntoskrnl!FsRtlCheckOplock` at `0x14004b61d`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x14004b73f`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x14004b7cc`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x14004b73f`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x14004b7cc`
- `ntoskrnl!MmIsFileSectionActive` at `0x14004b5db`
- `ntoskrnl!MmIsFileSectionActive` at `0x14004b6e2`
- `ntoskrnl!MmIsFileSectionActive` at `0x14004b5db`
- `ntoskrnl!MmIsFileSectionActive` at `0x14004b6e2`
- `ntoskrnl!FsRtlFastCheckLockForWrite` at `0x14004b633`

## pseudocode

```c
__int64 __fastcall RxProcessBatchedWrite(PRX_CONTEXT RxContext, PIRP a2, struct _FCB *MrxFcb)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r14
  struct _IRP *Parameters; // r13
  char v8; // cl
  int Status; // ebx
  unsigned int Options; // r8d
  unsigned __int64 v12; // rax
  ULONG v13; // ecx
  ULONG Length; // eax
  PFILE_OBJECT v15; // r15
  PSECTION_OBJECT_POINTERS SectionObjectPointer; // rax
  NTSTATUS v17; // eax
  PRDBSS_DEVICE_OBJECT RxDeviceObject; // rcx
  __int64 v19; // r8
  const CHAR *v20; // r9
  __int64 v21; // rcx
  unsigned int *v22; // r13
  ULONG *v23; // rcx
  ULONG v24; // edx
  __int64 v25; // rax
  struct _DRIVER_OBJECT **p_DriverObject; // rcx
  ULONG *v27; // r14
  unsigned int i; // r15d
  __int64 v29; // rax
  bool v30; // al
  int RdbssDbgExtension; // eax
  char v32; // r14
  __int64 Pool2; // rax
  NTSTATUS v34; // eax
  const CHAR *PostIrpRoutine; // [rsp+20h] [rbp-30h]
  ULONG PostIrpRoutinea; // [rsp+20h] [rbp-30h]
  ULONG v37; // [rsp+28h] [rbp-28h]
  PFILE_OBJECT FileObject; // [rsp+30h] [rbp-20h]
  ULONG *p_Flags; // [rsp+38h] [rbp-18h]
  LARGE_INTEGER FileOffset; // [rsp+40h] [rbp-10h] BYREF
  __int64 v41; // [rsp+48h] [rbp-8h] BYREF
  char v42; // [rsp+90h] [rbp+40h]
  int v43; // [rsp+98h] [rbp+48h] BYREF
  ULONG v44; // [rsp+A8h] [rbp+58h]

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 1344075 )
  {
    Parameters = (struct _IRP *)CurrentStackLocation->Parameters.CreatePipe.Parameters;
    v8 = 1;
  }
  else
  {
    Parameters = a2->AssociatedIrp.MasterIrp;
    v8 = 0;
  }
  FileObject = CurrentStackLocation->FileObject;
  v42 = v8;
  v41 = 0;
  FileOffset.QuadPart = 0;
  if ( !v8 || !a2->RequestorMode )
  {
    Options = CurrentStackLocation->Parameters.Create.Options;
    RxContext->Create.EaLength = 0;
    *((_DWORD *)&RxContext->9 + 28) = 0;
    if ( Options < 0x38 )
    {
      Status = -1073741811;
      goto LABEL_9;
    }
    if ( *(_DWORD *)&Parameters->Type != 1 )
    {
      Status = -1073741736;
      goto LABEL_9;
    }
    p_Flags = &Parameters->Flags;
    Status = RxpValidateBatchedRequest(
               &RxContext->Create.EaLength,
               (_DWORD *)&RxContext->9 + 28,
               Options,
               (int *)&Parameters->Flags);
    if ( Status >= 0 )
    {
      if ( (int)RxpComputeNewVdlForBatchedWrite(
                  (unsigned __int64 *)&v41,
                  &Parameters->Flags,
                  RxContext->Create.EaLength) < 0 )
      {
        Status = -1073741811;
        goto LABEL_10;
      }
      v12 = 16LL * *((unsigned int *)&RxContext->9 + 28);
      if ( v12 > 0xFFFFFFFF )
      {
        Status = -1073740685;
        goto LABEL_10;
      }
      v13 = v12 + 8;
      Length = CurrentStackLocation->Parameters.Read.Length;
      v44 = v13;
      if ( Length && Length < v13 )
      {
        Status = -1073741789;
        goto LABEL_10;
      }
      if ( MrxFcb->Header.NodeTypeCode != -5086 )
      {
        Status = -1073741808;
        goto LABEL_10;
      }
      v15 = FileObject;
      SectionObjectPointer = FileObject->SectionObjectPointer;
      if ( SectionObjectPointer && SectionObjectPointer->SharedCacheMap )
      {
        Status = -1073741637;
        goto LABEL_10;
      }
      v17 = _RxAcquireFcb(MrxFcb, RxContext, 1u, 0, PostIrpRoutine, v37);
      Status = v17;
      if ( v17 < 0 )
      {
        if ( v17 == -1073741739 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, &WPP_08739a57919f3523a69f175bfdb02181_Traceguids);
          }
          BYTE3(RxContext->RealDevice) = 1;
        }
        goto LABEL_10;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqq(
          WPP_GLOBAL_Control->AttachedDevice,
          11,
          &WPP_08739a57919f3523a69f175bfdb02181_Traceguids,
          RxContext,
          MrxFcb,
          FileObject);
      }
      RxDeviceObject = MrxFcb->RxDeviceObject;
      v43 = 0;
      MmIsFileSectionActive(&RxDeviceObject->DriverObject, 7, &v43);
      if ( v43 )
      {
        Status = -1073741245;
LABEL_100:
        _RxReleaseFcb(RxContext, (PMRX_FCB)&MrxFcb->Header, v19, v20, PostIrpRoutinea);
        goto LABEL_9;
      }
      if ( (*(_DWORD *)(&Parameters->Size + 1) & 8) == 0 )
      {
        Status = FsRtlCheckOplock(
                   (POPLOCK)&MrxFcb->pNetRoot,
                   a2,
                   RxContext,
                   RxUpperOplockBreakCompleteAsync,
                   RxPrePostIrp);
        if ( Status )
          goto LABEL_100;
        Status = RxCheckByteRangeLocks(a2, (__int64)FsRtlFastCheckLockForWrite);
        if ( Status )
          goto LABEL_100;
      }
      if ( FileObject->SectionObjectPointer->DataSectionObject )
      {
        LOBYTE(v19) = 1;
        RxAcquirePagingIoResource(RxContext, MrxFcb, v19);
        if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
          McTemplateK0p_EtwWriteTransfer(v21, &CcPurgeRequest, &RxContext->LowIoContext.Flags + 1, MrxFcb);
        v22 = &Parameters->Flags;
        v23 = p_Flags;
        if ( p_Flags )
        {
          v24 = MrxFcb->FcbReleases[3];
          do
          {
            v24 += v23[2];
            MrxFcb->FcbReleases[3] = v24;
            v25 = *v23;
            if ( !(_DWORD)v25 )
              break;
            v23 = (ULONG *)((char *)v23 + v25);
          }
          while ( v23 );
        }
        if ( MrxFcb->FcbReleases[3] <= 0x10
          || (p_DriverObject = &MrxFcb->RxDeviceObject->DeviceObject.DriverObject,
              v43 = 0,
              MmIsFileSectionActive(p_DriverObject, 7, &v43),
              v43)
          || LODWORD(MrxFcb->NonPaged) != HIDWORD(MrxFcb->NonPaged)
          && (*((_DWORD *)&MrxFcb->1 + 41) & 2) != 0
          && (*((_DWORD *)&MrxFcb->1 + 40) & 0x8000000) != 0 )
        {
          v27 = p_Flags;
LABEL_63:
          if ( v27 )
          {
            for ( i = 0; ; ++i )
            {
              if ( i >= v27[2] )
              {
                v29 = *v27;
                if ( (_DWORD)v29 )
                  v27 = (ULONG *)((char *)v27 + v29);
                else
                  v27 = 0;
                goto LABEL_63;
              }
              FileOffset = *(LARGE_INTEGER *)&v27[4 * i + 6];
              CcCoherencyFlushAndPurgeCache(
                FileObject->SectionObjectPointer,
                &FileOffset,
                v27[4 * i + 9],
                &a2->IoStatus,
                0);
              if ( a2->IoStatus.Status < 0 )
                break;
            }
            if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
              McTemplateK0p_EtwWriteTransfer(v23, &CcPurgeCompletion, &RxContext->LowIoContext.Flags + 1, MrxFcb);
            RxReleasePagingIoResource(RxContext, MrxFcb);
            Status = a2->IoStatus.Status;
            goto LABEL_100;
          }
          v15 = FileObject;
          v22 = p_Flags;
        }
        else
        {
          MrxFcb->FcbReleases[3] = 0;
          CcCoherencyFlushAndPurgeCache(FileObject->SectionObjectPointer, 0, 0, &a2->IoStatus, 0);
          if ( a2->IoStatus.Status < 0 )
          {
            if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
              McTemplateK0p_EtwWriteTransfer(v23, &CcPurgeCompletion, &RxContext->LowIoContext.Flags + 1, MrxFcb);
            RxReleasePagingIoResource(RxContext, MrxFcb);
            Status = a2->IoStatus.Status;
            goto LABEL_100;
          }
        }
        if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
          McTemplateK0p_EtwWriteTransfer(v23, &CcPurgeCompletion, &RxContext->LowIoContext.Flags + 1, MrxFcb);
        RxReleasePagingIoResource(RxContext, MrxFcb);
      }
      else
      {
        v22 = &Parameters->Flags;
      }
      if ( ((__int64)RxContext->RdbssDbgExtension & 0x200) != 0 || v42 )
      {
        RxpAssertBatchedBuffersLocked((__int64)a2, v22, RxContext->Create.EaLength, v42);
      }
      else
      {
        Status = RxpProbeAndLockBatchedBuffers(a2, v22, RxContext->Create.EaLength, IoReadAccess);
        if ( Status < 0 )
          goto LABEL_100;
      }
      v30 = v41 > MrxFcb->Header.ValidDataLength.QuadPart;
      *((_BYTE *)&RxContext->9 + 116) = v30;
      if ( v30 )
      {
        RdbssDbgExtension = (int)RxContext->RdbssDbgExtension;
        if ( (RdbssDbgExtension & 2) == 0 )
        {
          BYTE3(RxContext->RealDevice) = 1;
          goto LABEL_100;
        }
        v32 = 1;
        LODWORD(RxContext->RdbssDbgExtension) = RdbssDbgExtension & 0xFFFFEFFF;
      }
      else
      {
        _RxReleaseFcb(RxContext, (PMRX_FCB)&MrxFcb->Header, v19, v20, PostIrpRoutinea);
        v32 = 0;
      }
      RxInitializeLowIoContext(RxContext, 6u, (PLOWIO_CONTEXT)((char *)&RxContext->9 + 120));
      Pool2 = ExAllocatePool2(64, v44, 2000844882);
      *((_QWORD *)&RxContext->9 + 18) = Pool2;
      if ( Pool2 )
      {
        if ( !RxContext->LockManagerContext && (a2->Flags & 2) == 0 && !*((_BYTE *)&RxContext->9 + 116) )
          *((_WORD *)&RxContext->9 + 61) |= 8u;
        v34 = RxLowIoSubmit(RxContext, a2, MrxFcb, RxLowIoFsCtlShellCompletion);
        Status = v34;
        if ( v34 >= 0 && v34 != 259 && RxContext->InformationToReturn >= 0x18 )
        {
          _InterlockedOr8((volatile signed __int8 *)&MrxFcb->FcbTableEntry.HashLinks.Blink, 1u);
          v15->Flags |= 0x1000u;
        }
      }
      else
      {
        Status = -1073741670;
      }
      if ( v32 )
        goto LABEL_100;
    }
LABEL_9:
    if ( Status >= 0 )
      return (unsigned int)Status;
    goto LABEL_10;
  }
  Status = -1073741790;
LABEL_10:
  if ( !BYTE3(RxContext->RealDevice)
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 12, &WPP_08739a57919f3523a69f175bfdb02181_Traceguids);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14004b370  mov     [rsp-38h+arg_10], rbx
0x14004b375  push    rbp
0x14004b376  push    rsi
0x14004b377  push    rdi
0x14004b378  push    r12
0x14004b37a  push    r13
0x14004b37c  push    r14
0x14004b37e  push    r15
0x14004b380  mov     rbp, rsp
0x14004b383  sub     rsp, 50h
0x14004b387  mov     r14, [rdx+0B8h]
0x14004b38e  mov     r12, rdx
0x14004b391  xor     edx, edx
0x14004b393  mov     rsi, r8
0x14004b396  mov     rdi, rcx
0x14004b399  cmp     dword ptr [r14+18h], 14824Bh
0x14004b3a1  jnz     short loc_14004B3AB
0x14004b3a3  mov     r13, [r14+20h]
0x14004b3a7  mov     cl, 1
0x14004b3a9  jmp     short loc_14004B3B2
0x14004b3ab  mov     r13, [r12+18h]
0x14004b3b0  mov     cl, dl
0x14004b3b2  mov     rax, [r14+30h]
0x14004b3b6  mov     [rbp+var_20], rax
0x14004b3ba  lea     rax, WPP_GLOBAL_Control
0x14004b3c1  mov     [rbp+arg_0], cl
0x14004b3c4  mov     [rbp+var_8], rdx
0x14004b3c8  mov     qword ptr [rbp+FileOffset], rdx
0x14004b3cc  test    cl, cl
0x14004b3ce  jz      short loc_14004B3DE
0x14004b3d0  cmp     [r12+40h], dl
0x14004b3d5  jz      short loc_14004B3DE
0x14004b3d7  mov     ebx, 0C0000022h
0x14004b3dc  jmp     short loc_14004B40B
0x14004b3de  mov     r8d, [r14+10h]
0x14004b3e2  lea     rcx, [rdi+208h]
0x14004b3e9  mov     [rcx], edx
0x14004b3eb  lea     r15, [rdi+200h]
0x14004b3f2  mov     [r15], edx
0x14004b3f5  cmp     r8d, 38h ; '8'
0x14004b3f9  jnb     short loc_14004B461
0x14004b3fb  mov     ebx, 0C000000Dh
0x14004b400  test    ebx, ebx
0x14004b402  jns     short loc_14004B446
0x14004b404  lea     rax, WPP_GLOBAL_Control
0x14004b40b  cmp     byte ptr [rdi+23h], 0
0x14004b40f  jnz     short loc_14004B446
0x14004b411  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b418  cmp     rcx, rax
0x14004b41b  jz      short loc_14004B446
0x14004b41d  mov     eax, [rcx+2Ch]
0x14004b420  test    al, 1
0x14004b422  jz      short loc_14004B446
0x14004b424  cmp     byte ptr [rcx+29h], 1
0x14004b428  jb      short loc_14004B446
0x14004b42a  mov     rcx, [rcx+18h]
0x14004b42e  lea     r8, WPP_08739a57919f3523a69f175bfdb02181_Traceguids
0x14004b435  mov     edx, 0Ch
0x14004b43a  mov     dword ptr [rsp+50h+PostIrpRoutine], ebx
0x14004b43e  mov     r9, rdi
0x14004b441  call    WPP_SF_qD
0x14004b446  mov     eax, ebx
0x14004b448  mov     rbx, [rsp+50h+arg_10]
0x14004b450  add     rsp, 50h
0x14004b454  pop     r15
0x14004b456  pop     r14
0x14004b458  pop     r13
0x14004b45a  pop     r12
0x14004b45c  pop     rdi
0x14004b45d  pop     rsi
0x14004b45e  pop     rbp
0x14004b45f  retn
0x14004b461  cmp     dword ptr [r13+0], 1
0x14004b466  jz      short loc_14004B46F
0x14004b468  mov     ebx, 0C0000058h
0x14004b46d  jmp     short loc_14004B400
0x14004b46f  lea     rax, [r13+10h]
0x14004b473  mov     rdx, r15
0x14004b476  mov     r9, rax
0x14004b479  mov     [rbp+var_18], rax
0x14004b47d  call    RxpValidateBatchedRequest
0x14004b482  mov     ebx, eax
0x14004b484  test    eax, eax
0x14004b486  js      loc_14004B400
0x14004b48c  mov     r8d, [rdi+208h]
0x14004b493  lea     rdx, [r13+10h]
0x14004b497  lea     rcx, [rbp+var_8]
0x14004b49b  call    RxpComputeNewVdlForBatchedWrite
0x14004b4a0  test    eax, eax
0x14004b4a2  jns     short loc_14004B4AE
0x14004b4a4  mov     ebx, 0C000000Dh
0x14004b4a9  jmp     loc_14004B404
0x14004b4ae  mov     eax, [r15]
0x14004b4b1  mov     ecx, 0FFFFFFFFh
0x14004b4b6  shl     rax, 4
0x14004b4ba  cmp     rax, rcx
0x14004b4bd  ja      loc_14004B99D
0x14004b4c3  lea     ecx, [rax+8]
0x14004b4c6  mov     eax, [r14+8]
0x14004b4ca  mov     [rbp+arg_18], ecx
0x14004b4cd  test    eax, eax
0x14004b4cf  jz      short loc_14004B4DF
0x14004b4d1  cmp     eax, ecx
0x14004b4d3  jnb     short loc_14004B4DF
0x14004b4d5  mov     ebx, 0C0000023h
0x14004b4da  jmp     loc_14004B404
0x14004b4df  mov     eax, 0EC22h
0x14004b4e4  cmp     [rsi], ax
0x14004b4e7  jz      short loc_14004B4F3
0x14004b4e9  mov     ebx, 0C0000010h
0x14004b4ee  jmp     loc_14004B404
0x14004b4f3  mov     r15, [rbp+var_20]
0x14004b4f7  mov     rax, [r15+28h]
0x14004b4fb  test    rax, rax
0x14004b4fe  jz      short loc_14004B511
0x14004b500  cmp     qword ptr [rax+8], 0
0x14004b505  jz      short loc_14004B511
0x14004b507  mov     ebx, 0C00000BBh
0x14004b50c  jmp     loc_14004B404
0x14004b511  xor     r9d, r9d; LineNumber
0x14004b514  mov     rdx, rdi; RxContext
0x14004b517  mov     rcx, rsi; Fcb
0x14004b51a  lea     r8d, [r9+1]; Mode
0x14004b51e  call    __RxAcquireFcb
0x14004b523  mov     ebx, eax
0x14004b525  test    eax, eax
0x14004b527  jns     short loc_14004B57A
0x14004b529  cmp     eax, 0C0000055h
0x14004b52e  jnz     loc_14004B404
0x14004b534  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b53b  lea     rax, WPP_GLOBAL_Control
0x14004b542  cmp     rcx, rax
0x14004b545  jz      short loc_14004B571
0x14004b547  mov     edx, [rcx+2Ch]
0x14004b54a  test    dl, 10h
0x14004b54d  jz      short loc_14004B571
0x14004b54f  cmp     byte ptr [rcx+29h], 4
0x14004b553  jb      short loc_14004B571
0x14004b555  mov     rcx, [rcx+18h]
0x14004b559  lea     r8, WPP_08739a57919f3523a69f175bfdb02181_Traceguids
0x14004b560  mov     edx, 0Ah
0x14004b565  call    WPP_SF_
0x14004b56a  lea     rax, WPP_GLOBAL_Control
0x14004b571  mov     byte ptr [rdi+23h], 1
0x14004b575  jmp     loc_14004B40B
0x14004b57a  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b581  lea     rax, WPP_GLOBAL_Control
0x14004b588  cmp     rcx, rax
0x14004b58b  jz      short loc_14004B5BC
0x14004b58d  mov     eax, [rcx+2Ch]
0x14004b590  test    al, 10h
0x14004b592  jz      short loc_14004B5BC
0x14004b594  cmp     byte ptr [rcx+29h], 2
0x14004b598  jb      short loc_14004B5BC
0x14004b59a  mov     rcx, [rcx+18h]
0x14004b59e  lea     r8, WPP_08739a57919f3523a69f175bfdb02181_Traceguids
0x14004b5a5  mov     edx, 0Bh
0x14004b5aa  mov     [rsp+50h+var_28], r15
0x14004b5af  mov     r9, rdi
0x14004b5b2  mov     [rsp+50h+PostIrpRoutine], rsi
0x14004b5b7  call    WPP_SF_qqq
0x14004b5bc  mov     rcx, [rsi+130h]
0x14004b5c3  lea     r8, [rbp+arg_8]
0x14004b5c7  mov     r14d, 8
0x14004b5cd  mov     [rbp+arg_8], 0
0x14004b5d4  add     rcx, r14
0x14004b5d7  lea     edx, [r14-1]
0x14004b5db  call    cs:__imp_MmIsFileSectionActive
0x14004b5e2  nop     dword ptr [rax+rax+00h]
0x14004b5e7  cmp     [rbp+arg_8], 0
0x14004b5eb  jz      short loc_14004B5F7
0x14004b5ed  mov     ebx, 0C0000243h
0x14004b5f2  jmp     loc_14004B98D
0x14004b5f7  mov     eax, [r13+4]
0x14004b5fb  test    r14b, al
0x14004b5fe  jnz     short loc_14004B65A
0x14004b600  lea     rax, RxPrePostIrp
0x14004b607  mov     r8, rdi; Context
0x14004b60a  lea     rcx, [rsi+58h]; Oplock
0x14004b60e  mov     [rsp+50h+PostIrpRoutine], rax; PostIrpRoutine
0x14004b613  lea     r9, RxUpperOplockBreakCompleteAsync; CompletionRoutine
0x14004b61a  mov     rdx, r12; Irp
0x14004b61d  call    cs:__imp_FsRtlCheckOplock
0x14004b624  nop     dword ptr [rax+rax+00h]
0x14004b629  mov     ebx, eax
0x14004b62b  test    eax, eax
0x14004b62d  jnz     loc_14004B98D
0x14004b633  mov     rax, cs:__imp_FsRtlFastCheckLockForWrite
0x14004b63a  mov     r9, r13
0x14004b63d  xor     r8d, r8d
0x14004b640  mov     [rsp+50h+PostIrpRoutine], rax; __int64
0x14004b645  mov     rdx, rsi
0x14004b648  mov     rcx, r12; Irp
0x14004b64b  call    RxCheckByteRangeLocks
0x14004b650  mov     ebx, eax
0x14004b652  test    eax, eax
0x14004b654  jnz     loc_14004B98D
0x14004b65a  mov     rax, [r15+28h]
0x14004b65e  cmp     qword ptr [rax], 0
0x14004b662  jz      loc_14004B85C
0x14004b668  mov     r8b, 1
0x14004b66b  mov     rdx, rsi
0x14004b66e  mov     rcx, rdi
0x14004b671  call    RxAcquirePagingIoResource
0x14004b676  test    byte ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4, r14b
0x14004b67d  jz      short loc_14004B695
0x14004b67f  lea     r8, [rdi+19Ch]
0x14004b686  mov     r9, rsi
0x14004b689  lea     rdx, CcPurgeRequest
0x14004b690  call    McTemplateK0p_EtwWriteTransfer
0x14004b695  mov     r13, [rbp+var_18]
0x14004b699  mov     rcx, r13
0x14004b69c  test    r13, r13
0x14004b69f  jz      short loc_14004B6BB
0x14004b6a1  mov     edx, [rsi+27Ch]
0x14004b6a7  add     edx, [rcx+8]
0x14004b6aa  mov     [rsi+27Ch], edx
0x14004b6b0  mov     eax, [rcx]
0x14004b6b2  test    eax, eax
0x14004b6b4  jz      short loc_14004B6BB
0x14004b6b6  add     rcx, rax
0x14004b6b9  jnz     short loc_14004B6A7
0x14004b6bb  cmp     dword ptr [rsi+27Ch], 10h
0x14004b6c2  jbe     loc_14004B787
0x14004b6c8  mov     rcx, [rsi+130h]
0x14004b6cf  lea     r8, [rbp+arg_8]
0x14004b6d3  add     rcx, r14
0x14004b6d6  mov     [rbp+arg_8], 0
0x14004b6dd  mov     edx, 7
0x14004b6e2  call    cs:__imp_MmIsFileSectionActive
0x14004b6e9  nop     dword ptr [rax+rax+00h]
0x14004b6ee  cmp     [rbp+arg_8], 0
0x14004b6f2  jnz     loc_14004B787
0x14004b6f8  mov     eax, [rsi+0BCh]
0x14004b6fe  cmp     [rsi+0B8h], eax
0x14004b704  jz      short loc_14004B71C
0x14004b706  mov     eax, [rsi+0A4h]
0x14004b70c  test    al, 2
0x14004b70e  jz      short loc_14004B71C
0x14004b710  test    dword ptr [rsi+0A0h], 8000000h
0x14004b71a  jnz     short loc_14004B787
0x14004b71c  mov     dword ptr [rsi+27Ch], 0
0x14004b726  lea     r14, [r12+30h]
0x14004b72b  mov     rcx, [r15+28h]; SectionObjectPointer
0x14004b72f  mov     r9, r14; IoStatus
0x14004b732  xor     r8d, r8d; Length
0x14004b735  mov     dword ptr [rsp+50h+PostIrpRoutine], 0; Flags
0x14004b73d  xor     edx, edx; FileOffset
0x14004b73f  call    cs:__imp_CcCoherencyFlushAndPurgeCache
0x14004b746  nop     dword ptr [rax+rax+00h]
0x14004b74b  cmp     dword ptr [r14], 0
0x14004b74f  jge     loc_14004B830
0x14004b755  test    byte ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4, 8
0x14004b75c  jz      short loc_14004B774
0x14004b75e  lea     r8, [rdi+19Ch]
0x14004b765  mov     r9, rsi
0x14004b768  lea     rdx, CcPurgeCompletion
0x14004b76f  call    McTemplateK0p_EtwWriteTransfer
0x14004b774  mov     rdx, rsi
0x14004b777  mov     rcx, rdi
0x14004b77a  call    RxReleasePagingIoResource
0x14004b77f  mov     ebx, [r14]
0x14004b782  jmp     loc_14004B98D
0x14004b787  mov     r14, r13
0x14004b78a  test    r14, r14
0x14004b78d  jz      loc_14004B828
0x14004b793  xor     r15d, r15d
0x14004b796  cmp     r15d, [r14+8]
0x14004b79a  jnb     short loc_14004B7E4
0x14004b79c  mov     r8d, r15d
0x14004b79f  lea     r13, [r12+30h]
0x14004b7a4  add     r8, r8
0x14004b7a7  mov     dword ptr [rsp+50h+PostIrpRoutine], 0; Flags
0x14004b7af  mov     r9, r13; IoStatus
0x14004b7b2  lea     rdx, [rbp+FileOffset]; FileOffset
0x14004b7b6  mov     rax, [r14+r8*8+18h]
0x14004b7bb  mov     qword ptr [rbp+FileOffset], rax
0x14004b7bf  mov     rax, [rbp+var_20]
0x14004b7c3  mov     r8d, [r14+r8*8+24h]; Length
0x14004b7c8  mov     rcx, [rax+28h]; SectionObjectPointer
0x14004b7cc  call    cs:__imp_CcCoherencyFlushAndPurgeCache
0x14004b7d3  nop     dword ptr [rax+rax+00h]
0x14004b7d8  cmp     dword ptr [r13+0], 0
0x14004b7dd  jl      short loc_14004B7F5
0x14004b7df  inc     r15d
0x14004b7e2  jmp     short loc_14004B796
0x14004b7e4  mov     eax, [r14]
0x14004b7e7  test    eax, eax
0x14004b7e9  jz      short loc_14004B7F0
0x14004b7eb  add     r14, rax
0x14004b7ee  jmp     short loc_14004B78A
0x14004b7f0  xor     r14d, r14d
0x14004b7f3  jmp     short loc_14004B78A
0x14004b7f5  test    byte ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4, 8
0x14004b7fc  jz      short loc_14004B814
0x14004b7fe  lea     r8, [rdi+19Ch]
0x14004b805  mov     r9, rsi
0x14004b808  lea     rdx, CcPurgeCompletion
0x14004b80f  call    McTemplateK0p_EtwWriteTransfer
0x14004b814  mov     rdx, rsi
  ... truncated ...
```
