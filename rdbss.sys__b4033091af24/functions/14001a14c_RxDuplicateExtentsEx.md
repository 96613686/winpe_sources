# RxDuplicateExtentsEx

- ea: `0x14001a14c`
- end: `0x14001a82d`
- name: `RxDuplicateExtentsEx`
- size: `1761`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext, PIRP Irp, PMRX_FCB MrxFcb)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x140045410`

## callees

- `0x140008030`
- `0x140008190`
- `0x140009b80`
- `0x14000f130`
- `0x140017220`
- `0x140017370`
- `0x14001810c`
- `0x14001a14c`
- `0x14001b33c`
- `0x140025c20`
- `0x140057660`
- `0x140067ad0`
- `0x140069970`

## import_xrefs

- `ntoskrnl!FsRtlCheckOplock` at `0x14001a468`
- `ntoskrnl!FsRtlCheckOplock` at `0x14001a468`
- `ntoskrnl!IoGetRequestorProcess` at `0x14001a2a2`
- `ntoskrnl!IoGetRequestorProcess` at `0x14001a481`
- `ntoskrnl!IoGetRequestorProcess` at `0x14001a2a2`
- `ntoskrnl!IoGetRequestorProcess` at `0x14001a481`
- `ntoskrnl!CcSetFileSizes` at `0x14001a731`
- `ntoskrnl!CcSetFileSizes` at `0x14001a731`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x14001a58c`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x14001a58c`
- `ntoskrnl!MmIsFileSectionActive` at `0x14001a527`
- `ntoskrnl!MmIsFileSectionActive` at `0x14001a527`
- `ntoskrnl!FsRtlFastCheckLockForWrite` at `0x14001a4a9`
- `ntoskrnl!FsRtlFastCheckLockForWrite` at `0x14001a4a9`
- `ntoskrnl!IoIs32bitProcess` at `0x14001a1ce`
- `ntoskrnl!IoIs32bitProcess` at `0x14001a1ce`
- `ntoskrnl!KeStackAttachProcess` at `0x14001a2b5`
- `ntoskrnl!KeStackAttachProcess` at `0x14001a2b5`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001a2e7`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001a2e7`
- `ntoskrnl!IoFileObjectType` at `0x14001a2c1`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14001a2f9`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14001a2f9`
- `ntoskrnl!ObfDereferenceObject` at `0x14001a7b8`
- `ntoskrnl!ObfDereferenceObject` at `0x14001a7b8`

## pseudocode

```c
__int64 __fastcall RxDuplicateExtentsEx(PRX_CONTEXT RxContext, PIRP Irp, struct _FCB *MrxFcb)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  unsigned __int8 v4; // r15
  struct _FILE_OBJECT *FileObject; // r13
  PSECTION_OBJECT_POINTERS SectionObjectPointer; // rax
  BOOLEAN v10; // al
  unsigned int Options; // ecx
  struct _IRP *MasterIrp; // rcx
  struct _IRP *v13; // r14
  NTSTATUS Status; // ebx
  unsigned __int64 v15; // rax
  struct _LIST_ENTRY *Flink; // rdx
  struct _IRP *v17; // rax
  struct _KPROCESS *RequestorProcess; // rax
  __int16 v19; // ax
  __int64 v20; // r9
  __int64 v21; // rdx
  __int64 v22; // r8
  const CHAR *v23; // r9
  char v24; // r15
  __int64 v25; // r8
  const CHAR *QuadPart; // r9
  PEPROCESS v27; // rax
  __int64 v28; // rcx
  __int64 p_DriverObject; // rcx
  LARGE_INTEGER *p_StartingByte; // rdx
  __int64 v31; // rcx
  int RdbssDbgExtension; // eax
  char v33; // r14
  NTSTATUS v34; // eax
  LARGE_INTEGER v35; // rcx
  PVOID *Object; // [rsp+20h] [rbp-B9h]
  ULONG Objecta; // [rsp+20h] [rbp-B9h]
  ULONG Objectb; // [rsp+20h] [rbp-B9h]
  ULONG HandleInformation; // [rsp+28h] [rbp-B1h]
  char v41; // [rsp+60h] [rbp-79h]
  LARGE_INTEGER Length; // [rsp+68h] [rbp-71h] BYREF
  LARGE_INTEGER StartingByte; // [rsp+70h] [rbp-69h] BYREF
  __int64 v44; // [rsp+78h] [rbp-61h] BYREF
  PVOID v45; // [rsp+80h] [rbp-59h] BYREF
  __int64 v46; // [rsp+88h] [rbp-51h] BYREF
  __int128 v47; // [rsp+90h] [rbp-49h] BYREF
  __int128 v48; // [rsp+A0h] [rbp-39h]
  __int128 v49; // [rsp+B0h] [rbp-29h]
  struct _KAPC_STATE ApcState; // [rsp+C0h] [rbp-19h] BYREF

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v4 = 0;
  v47 = 0;
  FileObject = CurrentStackLocation->FileObject;
  StartingByte.QuadPart = 0;
  Length.QuadPart = 0;
  v48 = 0;
  SectionObjectPointer = FileObject->SectionObjectPointer;
  v49 = 0;
  if ( !SectionObjectPointer || (v41 = 1, !SectionObjectPointer->SharedCacheMap) )
    v41 = 0;
  v45 = 0;
  memset(&ApcState, 0, sizeof(ApcState));
  v10 = IoIs32bitProcess(Irp);
  Options = CurrentStackLocation->Parameters.Create.Options;
  if ( v10 )
  {
    if ( Options < 0x28 )
      goto LABEL_84;
    MasterIrp = Irp->AssociatedIrp.MasterIrp;
    v13 = (struct _IRP *)&v47;
    *(_QWORD *)&v47 = *(unsigned int *)&MasterIrp->Type;
    *((_QWORD *)&v47 + 1) = *(int *)(&MasterIrp->Size + 1);
    v48 = *(_OWORD *)&MasterIrp->MdlAddress;
    *(_QWORD *)&v49 = MasterIrp->AssociatedIrp.MasterIrp;
    DWORD2(v49) = MasterIrp->ThreadListEntry.Flink;
  }
  else
  {
    if ( Options < 0x30 )
      goto LABEL_84;
    v13 = Irp->AssociatedIrp.MasterIrp;
  }
  if ( MrxFcb->Header.NodeTypeCode != -5086 )
  {
    Status = -1073741808;
    goto LABEL_85;
  }
  v15 = *(_QWORD *)&v13->Flags;
  Flink = v13->ThreadListEntry.Flink;
  if ( (unsigned __int64)Flink + v15 < v15 || (unsigned __int64)Flink + v15 > 0x7FFFFFFFFFFFFFFFLL )
  {
LABEL_84:
    Status = -1073741811;
    goto LABEL_85;
  }
  v17 = v13->AssociatedIrp.MasterIrp;
  if ( (char *)Flink + (unsigned __int64)v17 < (char *)v17
    || (struct _LIST_ENTRY *)((char *)Flink + (_QWORD)v17) > (struct _LIST_ENTRY *)0x7FFFFFFFFFFFFFFFLL )
  {
    Status = -1073741811;
    goto LABEL_85;
  }
  StartingByte = (LARGE_INTEGER)v13->AssociatedIrp.MasterIrp;
  Length = (LARGE_INTEGER)v13->ThreadListEntry.Flink;
  RequestorProcess = IoGetRequestorProcess(Irp);
  KeStackAttachProcess(RequestorProcess, &ApcState);
  Status = ObReferenceObjectByHandle(
             v13->MdlAddress,
             0x81u,
             (POBJECT_TYPE)IoFileObjectType,
             Irp->RequestorMode,
             &v45,
             0);
  KeUnstackDetachProcess(&ApcState);
  if ( Status >= 0 )
  {
    v44 = 0;
    v46 = 0;
    v19 = RxDecodeFileObject2(v45, &v44, &v46);
    if ( *(PDEVICE_OBJECT *)(v20 + 8) == FileObject->DeviceObject
      && v19 == -5086
      && *(_QWORD *)(v44 + 120) == *((_QWORD *)&MrxFcb->1 + 15) )
    {
      if ( (*(_DWORD *)(v46 + 72) & 0x400002) != 0 || (*(_DWORD *)(*(_QWORD *)(v46 + 32) + 72LL) & 0x400) != 0 )
      {
        Status = -1073741528;
      }
      else
      {
        if ( !FileObject->SectionObjectPointer->DataSectionObject
          && Length.QuadPart + StartingByte.QuadPart <= MrxFcb->Header.ValidDataLength.QuadPart )
        {
          goto LABEL_25;
        }
        while ( 1 )
        {
          v4 = 1;
LABEL_25:
          Status = _RxAcquireFcb(MrxFcb, RxContext, (v4 ^ 1) + 1, 0, (PCSTR)Object, HandleInformation);
          if ( Status < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_qD(
                WPP_GLOBAL_Control->AttachedDevice,
                27,
                WPP_0631a9abaf7433de250bb1791161ea05_Traceguids,
                MrxFcb,
                Status);
            }
            if ( Status == -1073741739 )
              BYTE3(RxContext->RealDevice) = 1;
            goto LABEL_85;
          }
          if ( v4 )
            break;
          v24 = 0;
          if ( !FileObject->SectionObjectPointer->DataSectionObject
            && StartingByte.QuadPart + Length.QuadPart <= MrxFcb->Header.ValidDataLength.QuadPart )
          {
            goto LABEL_31;
          }
          _RxReleaseFcb(RxContext, (PMRX_FCB)&MrxFcb->Header, v22, v23, Objecta);
        }
        v24 = 0;
LABEL_31:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qqqiiiDq(
            WPP_GLOBAL_Control->AttachedDevice,
            v21,
            v22,
            RxContext,
            FileObject,
            v13->MdlAddress,
            *(_QWORD *)&v13->Flags,
            v13->AssociatedIrp.MasterIrp,
            v13->ThreadListEntry.Flink,
            v13->ThreadListEntry.Blink,
            MrxFcb);
        }
        Status = FsRtlCheckOplock(
                   (POPLOCK)&MrxFcb->pNetRoot,
                   Irp,
                   RxContext,
                   RxUpperOplockBreakCompleteAsync,
                   RxPrePostIrp);
        if ( Status )
        {
LABEL_65:
          _RxReleaseFcb(RxContext, (PMRX_FCB)&MrxFcb->Header, v25, QuadPart, Objectb);
          goto LABEL_85;
        }
        v27 = IoGetRequestorProcess(Irp);
        if ( !FsRtlFastCheckLockForWrite(
                (PFILE_LOCK)&MrxFcb->FileLock.LockRequestsInProgress,
                &StartingByte,
                &Length,
                0,
                FileObject,
                v27) )
        {
          Status = -1073741740;
          goto LABEL_65;
        }
        if ( FileObject->SectionObjectPointer->DataSectionObject )
        {
          LOBYTE(v25) = 1;
          RxAcquirePagingIoResource(RxContext, MrxFcb, v25);
          if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
            McTemplateK0p_EtwWriteTransfer(v28, CcPurgeRequest, &RxContext->LowIoContext.Flags + 1, MrxFcb);
          if ( ++MrxFcb->FcbReleases[3] > 0x10 )
          {
            p_DriverObject = (__int64)&MrxFcb->RxDeviceObject->DeviceObject.DriverObject;
            LODWORD(v44) = 0;
            MmIsFileSectionActive(p_DriverObject, 7, &v44);
            if ( !(_DWORD)v44
              && (LODWORD(MrxFcb->NonPaged) == HIDWORD(MrxFcb->NonPaged)
               || (*((_DWORD *)&MrxFcb->1 + 41) & 2) == 0
               || (*((_DWORD *)&MrxFcb->1 + 40) & 0x8000000) == 0) )
            {
              v24 = 1;
              MrxFcb->FcbReleases[3] = 0;
            }
          }
          p_StartingByte = &StartingByte;
          if ( v24 )
            p_StartingByte = 0;
          CcCoherencyFlushAndPurgeCache(
            FileObject->SectionObjectPointer,
            p_StartingByte,
            Length.LowPart,
            &Irp->IoStatus,
            0);
          if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
            McTemplateK0p_EtwWriteTransfer(v31, CcPurgeCompletion, &RxContext->LowIoContext.Flags + 1, MrxFcb);
          RxReleasePagingIoResource(RxContext, MrxFcb);
          if ( Irp->IoStatus.Status < 0 )
          {
            Status = Irp->IoStatus.Status;
            goto LABEL_65;
          }
        }
        if ( StartingByte.QuadPart + Length.QuadPart <= MrxFcb->Header.ValidDataLength.QuadPart )
        {
          _RxReleaseFcb(RxContext, (PMRX_FCB)&MrxFcb->Header, v25, QuadPart, Objectb);
          v33 = 0;
        }
        else
        {
          RdbssDbgExtension = (int)RxContext->RdbssDbgExtension;
          if ( (RdbssDbgExtension & 2) == 0 )
          {
            BYTE3(RxContext->RealDevice) = 1;
            goto LABEL_65;
          }
          v33 = 1;
          LODWORD(RxContext->RdbssDbgExtension) = RdbssDbgExtension & 0xFFFFEFFF;
        }
        RxInitializeLowIoContext(RxContext, 6u, (PLOWIO_CONTEXT)((char *)&RxContext->9 + 120));
        *((_QWORD *)&RxContext->9 + 18) = v45;
        v45 = 0;
        _InterlockedOr8((volatile signed __int8 *)&MrxFcb->FcbTableEntry.HashLinks.Blink, 1u);
        FileObject->Flags |= 0x1000u;
        v34 = RxLowIoSubmit(RxContext, Irp, MrxFcb, RxLowIoFsCtlShellCompletion);
        Status = v34;
        if ( v34 == 259 )
        {
LABEL_64:
          if ( !v33 )
            goto LABEL_85;
          goto LABEL_65;
        }
        if ( v34 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              29,
              WPP_0631a9abaf7433de250bb1791161ea05_Traceguids,
              RxContext,
              v34);
          }
          goto LABEL_64;
        }
        if ( v33 )
        {
          if ( StartingByte.QuadPart + Length.QuadPart > MrxFcb->Header.ValidDataLength.QuadPart )
          {
            QuadPart = (const CHAR *)MrxFcb->Header.FileSize.QuadPart;
            v35.QuadPart = (LONGLONG)QuadPart;
            if ( (__int64)QuadPart >= StartingByte.QuadPart + Length.QuadPart )
              v35.QuadPart = StartingByte.QuadPart + Length.QuadPart;
            MrxFcb->Header.ValidDataLength = v35;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_qqq)(
                WPP_GLOBAL_Control->AttachedDevice,
                30,
                WPP_0631a9abaf7433de250bb1791161ea05_Traceguids,
                QuadPart,
                (LARGE_INTEGER)v35.QuadPart,
                (LARGE_INTEGER)v35.QuadPart);
            }
            if ( v41 )
              CcSetFileSizes(FileObject, (PCC_FILE_SIZES)&MrxFcb->spacer.AllocationSize);
          }
          goto LABEL_65;
        }
      }
      goto LABEL_85;
    }
    goto LABEL_84;
  }
LABEL_85:
  if ( v45 )
    ObfDereferenceObject(v45);
  if ( Status < 0
    && !BYTE3(RxContext->RealDevice)
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      31,
      WPP_0631a9abaf7433de250bb1791161ea05_Traceguids,
      RxContext,
      Status);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14001a14c  mov     [rsp-8+arg_18], rbx
0x14001a151  push    rbp
0x14001a152  push    rsi
0x14001a153  push    rdi
0x14001a154  push    r12
0x14001a156  push    r13
0x14001a158  push    r14
0x14001a15a  push    r15
0x14001a15c  lea     rbp, [rsp-27h]
0x14001a161  sub     rsp, 100h
0x14001a168  mov     rax, cs:__security_cookie
0x14001a16f  xor     rax, rsp
0x14001a172  mov     [rbp+57h+var_40], rax
0x14001a176  mov     rbx, [rdx+0B8h]
0x14001a17d  xor     r15d, r15d
0x14001a180  xorps   xmm0, xmm0
0x14001a183  mov     rdi, r8
0x14001a186  mov     r12, rdx
0x14001a189  mov     rsi, rcx
0x14001a18c  movups  [rbp+57h+var_A0], xmm0
0x14001a190  mov     r13, [rbx+30h]
0x14001a194  mov     qword ptr [rbp+57h+StartingByte], r15
0x14001a198  mov     qword ptr [rbp+57h+Length], r15
0x14001a19c  movups  [rbp+57h+var_90], xmm0
0x14001a1a0  mov     rax, [r13+28h]
0x14001a1a4  movups  [rbp+57h+var_80], xmm0
0x14001a1a8  test    rax, rax
0x14001a1ab  jz      short loc_14001A1B7
0x14001a1ad  mov     [rbp+57h+var_D0], 1
0x14001a1b1  cmp     [rax+8], r15
0x14001a1b5  jnz     short loc_14001A1BB
0x14001a1b7  mov     [rbp+57h+var_D0], r15b
0x14001a1bb  mov     rcx, r12; Irp
0x14001a1be  mov     [rbp+57h+var_B0], r15
0x14001a1c2  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink], xmm0
0x14001a1c6  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink+10h], xmm0
0x14001a1ca  movups  xmmword ptr [rbp+57h+ApcState.Process], xmm0
0x14001a1ce  call    cs:__imp_IoIs32bitProcess
0x14001a1d5  nop     dword ptr [rax+rax+00h]
0x14001a1da  mov     ecx, [rbx+10h]
0x14001a1dd  lea     r14, WPP_GLOBAL_Control
0x14001a1e4  test    al, al
0x14001a1e6  jz      short loc_14001A228
0x14001a1e8  cmp     ecx, 28h ; '('
0x14001a1eb  jb      loc_14001A7A7
0x14001a1f1  mov     rcx, [r12+18h]
0x14001a1f6  lea     r14, [rbp+57h+var_A0]
0x14001a1fa  mov     eax, [rcx]
0x14001a1fc  mov     qword ptr [rbp+57h+var_A0], rax
0x14001a200  movsxd  rax, dword ptr [rcx+4]
0x14001a204  mov     qword ptr [rbp+57h+var_A0+8], rax
0x14001a208  mov     rax, [rcx+8]
0x14001a20c  mov     qword ptr [rbp+57h+var_90], rax
0x14001a210  mov     rax, [rcx+10h]
0x14001a214  mov     qword ptr [rbp+57h+var_90+8], rax
0x14001a218  mov     rax, [rcx+18h]
0x14001a21c  mov     qword ptr [rbp+57h+var_80], rax
0x14001a220  mov     eax, [rcx+20h]
0x14001a223  mov     dword ptr [rbp+57h+var_80+8], eax
0x14001a226  jmp     short loc_14001A236
0x14001a228  cmp     ecx, 30h ; '0'
0x14001a22b  jb      loc_14001A7A7
0x14001a231  mov     r14, [r12+18h]
0x14001a236  mov     eax, 0EC22h
0x14001a23b  cmp     [rdi], ax
0x14001a23e  jz      short loc_14001A251
0x14001a240  mov     ebx, 0C0000010h
0x14001a245  lea     r14, WPP_GLOBAL_Control
0x14001a24c  jmp     loc_14001A7AC
0x14001a251  mov     rax, [r14+10h]
0x14001a255  mov     rdx, [r14+20h]
0x14001a259  lea     rcx, [rax+rdx]
0x14001a25d  cmp     rcx, rax
0x14001a260  jb      loc_14001A7A0
0x14001a266  mov     r8, 7FFFFFFFFFFFFFFFh
0x14001a270  cmp     rcx, r8
0x14001a273  ja      loc_14001A7A0
0x14001a279  mov     rax, [r14+18h]
0x14001a27d  lea     rcx, [rax+rdx]
0x14001a281  cmp     rcx, rax
0x14001a284  jb      loc_14001A796
0x14001a28a  cmp     rcx, r8
0x14001a28d  ja      loc_14001A796
0x14001a293  mov     qword ptr [rbp+57h+StartingByte], rax
0x14001a297  mov     rcx, r12; Irp
0x14001a29a  mov     rax, [r14+20h]
0x14001a29e  mov     qword ptr [rbp+57h+Length], rax
0x14001a2a2  call    cs:__imp_IoGetRequestorProcess
0x14001a2a9  nop     dword ptr [rax+rax+00h]
0x14001a2ae  mov     rcx, rax; PROCESS
0x14001a2b1  lea     rdx, [rbp+57h+ApcState]; ApcState
0x14001a2b5  call    cs:__imp_KeStackAttachProcess
0x14001a2bc  nop     dword ptr [rax+rax+00h]
0x14001a2c1  mov     r8, cs:__imp_IoFileObjectType
0x14001a2c8  lea     rax, [rbp+57h+var_B0]
0x14001a2cc  mov     r9b, [r12+40h]; AccessMode
0x14001a2d1  mov     edx, 81h; DesiredAccess
0x14001a2d6  mov     rcx, [r14+8]; Handle
0x14001a2da  mov     [rsp+130h+HandleInformation], r15; SerialNumber
0x14001a2df  mov     r8, [r8]; ObjectType
0x14001a2e2  mov     [rsp+130h+Object], rax; SerialNumber
0x14001a2e7  call    cs:__imp_ObReferenceObjectByHandle
0x14001a2ee  nop     dword ptr [rax+rax+00h]
0x14001a2f3  lea     rcx, [rbp+57h+ApcState]; ApcState
0x14001a2f7  mov     ebx, eax
0x14001a2f9  call    cs:__imp_KeUnstackDetachProcess
0x14001a300  nop     dword ptr [rax+rax+00h]
0x14001a305  test    ebx, ebx
0x14001a307  js      loc_14001A245
0x14001a30d  mov     r9, [rbp+57h+var_B0]
0x14001a311  lea     r8, [rbp+57h+var_A8]
0x14001a315  mov     rcx, r9
0x14001a318  mov     [rbp+57h+var_B8], r15
0x14001a31c  lea     rdx, [rbp+57h+var_B8]
0x14001a320  mov     [rbp+57h+var_A8], r15
0x14001a324  call    RxDecodeFileObject2
0x14001a329  mov     rcx, [r13+8]
0x14001a32d  cmp     [r9+8], rcx
0x14001a331  jnz     loc_14001A7A0
0x14001a337  mov     ecx, 0EC22h
0x14001a33c  cmp     ax, cx
0x14001a33f  jnz     loc_14001A7A0
0x14001a345  mov     rax, [rbp+57h+var_B8]
0x14001a349  mov     rcx, [rdi+78h]
0x14001a34d  cmp     [rax+78h], rcx
0x14001a351  jnz     loc_14001A7A0
0x14001a357  mov     rcx, [rbp+57h+var_A8]
0x14001a35b  test    dword ptr [rcx+48h], 400002h
0x14001a362  jnz     loc_14001A78C
0x14001a368  mov     rax, [rcx+20h]
0x14001a36c  test    dword ptr [rax+48h], 400h
0x14001a373  jnz     loc_14001A78C
0x14001a379  mov     rax, [r13+28h]
0x14001a37d  cmp     [rax], r15
0x14001a380  jnz     short loc_14001A390
0x14001a382  mov     rcx, qword ptr [rbp+57h+StartingByte]
0x14001a386  add     rcx, qword ptr [rbp+57h+Length]
0x14001a38a  cmp     rcx, [rdi+28h]
0x14001a38e  jle     short loc_14001A393
0x14001a390  mov     r15b, 1
0x14001a393  movzx   r8d, r15b
0x14001a397  xor     r9d, r9d; LineNumber
0x14001a39a  xor     r8d, 1
0x14001a39e  mov     rdx, rsi; RxContext
0x14001a3a1  inc     r8d; Mode
0x14001a3a4  mov     rcx, rdi; Fcb
0x14001a3a7  call    __RxAcquireFcb
0x14001a3ac  mov     ebx, eax
0x14001a3ae  test    eax, eax
0x14001a3b0  js      loc_14001A742
0x14001a3b6  mov     [rbp+57h+var_CF], 1
0x14001a3ba  test    r15b, r15b
0x14001a3bd  jnz     short loc_14001A3E6
0x14001a3bf  mov     rax, [r13+28h]
0x14001a3c3  xor     r15d, r15d
0x14001a3c6  cmp     [rax], r15
0x14001a3c9  jnz     short loc_14001A3D9
0x14001a3cb  mov     rcx, qword ptr [rbp+57h+Length]
0x14001a3cf  add     rcx, qword ptr [rbp+57h+StartingByte]
0x14001a3d3  cmp     rcx, [rdi+28h]
0x14001a3d7  jle     short loc_14001A3E9
0x14001a3d9  mov     rdx, rdi; MrxFcb
0x14001a3dc  mov     rcx, rsi; RxContext
0x14001a3df  call    __RxReleaseFcb
0x14001a3e4  jmp     short loc_14001A390
0x14001a3e6  xor     r15d, r15d
0x14001a3e9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a3f0  lea     rax, WPP_GLOBAL_Control
0x14001a3f7  cmp     rcx, rax
0x14001a3fa  jz      short loc_14001A44B
0x14001a3fc  mov     eax, [rcx+2Ch]
0x14001a3ff  test    al, 10h
0x14001a401  jz      short loc_14001A44B
0x14001a403  cmp     byte ptr [rcx+29h], 2
0x14001a407  jb      short loc_14001A44B
0x14001a409  mov     eax, [r14+28h]
0x14001a40d  mov     r9, rsi
0x14001a410  mov     rcx, [rcx+18h]
0x14001a414  mov     [rsp+130h+var_E0], rdi
0x14001a419  mov     [rsp+130h+var_E8], eax
0x14001a41d  mov     rax, [r14+20h]
0x14001a421  mov     [rsp+130h+var_F0], rax
0x14001a426  mov     rax, [r14+18h]
0x14001a42a  mov     [rsp+130h+var_F8], rax
0x14001a42f  mov     rax, [r14+10h]
0x14001a433  mov     [rsp+130h+var_100], rax
0x14001a438  mov     rax, [r14+8]
0x14001a43c  mov     [rsp+130h+HandleInformation], rax
0x14001a441  mov     [rsp+130h+Object], r13
0x14001a446  call    WPP_SF_qqqiiiDq
0x14001a44b  lea     rax, RxPrePostIrp
0x14001a452  mov     r8, rsi; Context
0x14001a455  lea     rcx, [rdi+58h]; Oplock
0x14001a459  mov     [rsp+130h+Object], rax; PostIrpRoutine
0x14001a45e  lea     r9, RxUpperOplockBreakCompleteAsync; CompletionRoutine
0x14001a465  mov     rdx, r12; Irp
0x14001a468  call    cs:__imp_FsRtlCheckOplock
0x14001a46f  nop     dword ptr [rax+rax+00h]
0x14001a474  mov     ebx, eax
0x14001a476  test    eax, eax
0x14001a478  jnz     loc_14001A6A3
0x14001a47e  mov     rcx, r12; Irp
0x14001a481  call    cs:__imp_IoGetRequestorProcess
0x14001a488  nop     dword ptr [rax+rax+00h]
0x14001a48d  mov     [rsp+130h+HandleInformation], rax; ProcessId
0x14001a492  lea     rcx, [rdi+218h]; FileLock
0x14001a499  xor     r9d, r9d; Key
0x14001a49c  mov     [rsp+130h+Object], r13; SerialNumber
0x14001a4a1  lea     r8, [rbp+57h+Length]; Length
0x14001a4a5  lea     rdx, [rbp+57h+StartingByte]; StartingByte
0x14001a4a9  call    cs:__imp_FsRtlFastCheckLockForWrite
0x14001a4b0  nop     dword ptr [rax+rax+00h]
0x14001a4b5  test    al, al
0x14001a4b7  jnz     short loc_14001A4C3
0x14001a4b9  mov     ebx, 0C0000054h
0x14001a4be  jmp     loc_14001A6A3
0x14001a4c3  mov     rax, [r13+28h]
0x14001a4c7  cmp     [rax], r15
0x14001a4ca  jz      loc_14001A5D2
0x14001a4d0  mov     r8b, 1
0x14001a4d3  mov     rdx, rdi
0x14001a4d6  mov     rcx, rsi
0x14001a4d9  call    RxAcquirePagingIoResource
0x14001a4de  test    byte ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4, 8
0x14001a4e5  jz      short loc_14001A4FD
0x14001a4e7  lea     r8, [rsi+19Ch]
0x14001a4ee  mov     r9, rdi
0x14001a4f1  lea     rdx, CcPurgeRequest
0x14001a4f8  call    McTemplateK0p_EtwWriteTransfer
0x14001a4fd  inc     dword ptr [rdi+27Ch]
0x14001a503  cmp     dword ptr [rdi+27Ch], 10h
0x14001a50a  jbe     short loc_14001A56A
0x14001a50c  mov     rcx, [rdi+130h]
0x14001a513  lea     r8, [rbp+57h+var_B8]
0x14001a517  add     rcx, 8
0x14001a51b  mov     dword ptr [rbp+57h+var_B8], 0
0x14001a522  mov     edx, 7
0x14001a527  call    cs:__imp_MmIsFileSectionActive
0x14001a52e  nop     dword ptr [rax+rax+00h]
0x14001a533  cmp     dword ptr [rbp+57h+var_B8], 0
0x14001a537  jnz     short loc_14001A56A
0x14001a539  mov     eax, [rdi+0BCh]
0x14001a53f  cmp     [rdi+0B8h], eax
0x14001a545  jz      short loc_14001A55D
0x14001a547  mov     eax, [rdi+0A4h]
0x14001a54d  test    al, 2
0x14001a54f  jz      short loc_14001A55D
0x14001a551  test    dword ptr [rdi+0A0h], 8000000h
0x14001a55b  jnz     short loc_14001A56A
0x14001a55d  mov     r15b, 1
0x14001a560  mov     dword ptr [rdi+27Ch], 0
0x14001a56a  mov     r8d, dword ptr [rbp+57h+Length]; Length
0x14001a56e  lea     rdx, [rbp+57h+StartingByte]
0x14001a572  mov     rcx, [r13+28h]; SectionObjectPointer
0x14001a576  lea     r9, [r12+30h]; IoStatus
0x14001a57b  xor     eax, eax
0x14001a57d  test    r15b, r15b
0x14001a580  cmovnz  rdx, rax; FileOffset
0x14001a584  xor     r15d, r15d
0x14001a587  mov     dword ptr [rsp+130h+Object], r15d; Flags
0x14001a58c  call    cs:__imp_CcCoherencyFlushAndPurgeCache
0x14001a593  nop     dword ptr [rax+rax+00h]
0x14001a598  test    byte ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4, 8
0x14001a59f  jz      short loc_14001A5B7
0x14001a5a1  lea     r8, [rsi+19Ch]
0x14001a5a8  mov     r9, rdi
0x14001a5ab  lea     rdx, CcPurgeCompletion
0x14001a5b2  call    McTemplateK0p_EtwWriteTransfer
0x14001a5b7  mov     rdx, rdi
0x14001a5ba  mov     rcx, rsi
0x14001a5bd  call    RxReleasePagingIoResource
0x14001a5c2  mov     eax, [r12+30h]
0x14001a5c7  test    eax, eax
0x14001a5c9  jns     short loc_14001A5D2
0x14001a5cb  mov     ebx, eax
0x14001a5cd  jmp     loc_14001A6A3
0x14001a5d2  mov     rcx, qword ptr [rbp+57h+Length]
0x14001a5d6  add     rcx, qword ptr [rbp+57h+StartingByte]
0x14001a5da  cmp     rcx, [rdi+28h]
0x14001a5de  jle     short loc_14001A5FD
0x14001a5e0  mov     eax, [rsi+78h]
0x14001a5e3  test    al, 2
0x14001a5e5  jnz     short loc_14001A5F0
0x14001a5e7  mov     byte ptr [rsi+23h], 1
0x14001a5eb  jmp     loc_14001A6A3
0x14001a5f0  mov     r14b, [rbp+57h+var_CF]
0x14001a5f4  btr     eax, 0Ch
0x14001a5f8  mov     [rsi+78h], eax
0x14001a5fb  jmp     short loc_14001A60B
0x14001a5fd  mov     rdx, rdi; MrxFcb
0x14001a600  mov     rcx, rsi; RxContext
0x14001a603  call    __RxReleaseFcb
0x14001a608  mov     r14b, r15b
0x14001a60b  lea     r8, [rsi+208h]; LowIoContext
0x14001a612  mov     edx, 6; Operation
0x14001a617  mov     rcx, rsi; RxContext
0x14001a61a  call    RxInitializeLowIoContext
0x14001a61f  mov     rax, [rbp+57h+var_B0]
0x14001a623  mov     [rsi+220h], rax
0x14001a62a  mov     [rbp+57h+var_B0], r15
  ... truncated ...
```
