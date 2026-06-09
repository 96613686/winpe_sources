# RxDuplicateExtents

- ea: `0x140019aac`
- end: `0x14001a143`
- name: `RxDuplicateExtents`
- size: `1687`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext, PIRP Irp, struct _FCB *MrxFcb)`
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
- `0x140019aac`
- `0x14001b3ec`
- `0x140025c20`
- `0x140057660`
- `0x140067ad0`
- `0x140069970`

## import_xrefs

- `ntoskrnl!FsRtlCheckOplock` at `0x140019d85`
- `ntoskrnl!FsRtlCheckOplock` at `0x140019d85`
- `ntoskrnl!IoGetRequestorProcess` at `0x140019bc3`
- `ntoskrnl!IoGetRequestorProcess` at `0x140019d9e`
- `ntoskrnl!IoGetRequestorProcess` at `0x140019bc3`
- `ntoskrnl!IoGetRequestorProcess` at `0x140019d9e`
- `ntoskrnl!CcSetFileSizes` at `0x14001a045`
- `ntoskrnl!CcSetFileSizes` at `0x14001a045`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x140019ea8`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x140019ea8`
- `ntoskrnl!MmIsFileSectionActive` at `0x140019e48`
- `ntoskrnl!MmIsFileSectionActive` at `0x140019e48`
- `ntoskrnl!FsRtlFastCheckLockForWrite` at `0x140019dc6`
- `ntoskrnl!FsRtlFastCheckLockForWrite` at `0x140019dc6`
- `ntoskrnl!IoIs32bitProcess` at `0x140019ba8`
- `ntoskrnl!IoIs32bitProcess` at `0x140019ba8`
- `ntoskrnl!KeStackAttachProcess` at `0x140019bd6`
- `ntoskrnl!KeStackAttachProcess` at `0x140019bd6`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140019c06`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140019c06`
- `ntoskrnl!IoFileObjectType` at `0x140019be2`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140019c18`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140019c18`
- `ntoskrnl!ObfDereferenceObject` at `0x14001a0bd`
- `ntoskrnl!ObfDereferenceObject` at `0x14001a0bd`

## pseudocode

```c
__int64 __fastcall RxDuplicateExtents(PRX_CONTEXT RxContext, PIRP Irp, struct _FCB *MrxFcb)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  struct _FILE_OBJECT *FileObject; // r13
  PSECTION_OBJECT_POINTERS SectionObjectPointer; // rax
  _QWORD *v9; // r9
  NTSTATUS Status; // ebx
  LARGE_INTEGER *MasterIrp; // r14
  LARGE_INTEGER v12; // rax
  LARGE_INTEGER v13; // rdx
  LARGE_INTEGER v14; // rax
  LONGLONG LowPart; // rbx
  struct _KPROCESS *RequestorProcess; // rax
  __int16 v17; // ax
  unsigned __int8 v18; // r15
  __int64 v19; // rdx
  __int64 v20; // r8
  const CHAR *v21; // r9
  char v22; // r12
  PIRP v23; // r14
  __int64 v24; // r8
  const CHAR *QuadPart; // r9
  PEPROCESS v26; // rax
  char v27; // r15
  __int64 v28; // rcx
  struct _DRIVER_OBJECT **p_DriverObject; // rcx
  LARGE_INTEGER *p_StartingByte; // rdx
  __int64 v31; // rcx
  int RdbssDbgExtension; // eax
  NTSTATUS v33; // eax
  LARGE_INTEGER v34; // rcx
  PVOID *Object; // [rsp+20h] [rbp-79h]
  ULONG Objecta; // [rsp+20h] [rbp-79h]
  ULONG Objectb; // [rsp+20h] [rbp-79h]
  ULONG HandleInformation; // [rsp+28h] [rbp-71h]
  char v40; // [rsp+50h] [rbp-49h]
  LARGE_INTEGER Length; // [rsp+58h] [rbp-41h] BYREF
  LARGE_INTEGER StartingByte; // [rsp+60h] [rbp-39h] BYREF
  PVOID v43; // [rsp+68h] [rbp-31h] BYREF
  __int64 v44; // [rsp+70h] [rbp-29h] BYREF
  __int64 v45; // [rsp+78h] [rbp-21h] BYREF
  PIRP Irpa; // [rsp+80h] [rbp-19h]
  _KAPC_STATE ApcState; // [rsp+88h] [rbp-11h] BYREF

  Irpa = Irp;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  FileObject = CurrentStackLocation->FileObject;
  StartingByte.QuadPart = 0;
  Length.QuadPart = 0;
  SectionObjectPointer = FileObject->SectionObjectPointer;
  if ( !SectionObjectPointer || (v40 = 1, !SectionObjectPointer->SharedCacheMap) )
    v40 = 0;
  v43 = 0;
  memset(&ApcState, 0, sizeof(ApcState));
  v9 = 0;
  if ( CurrentStackLocation->Parameters.Create.Options < 0x20 )
    goto LABEL_88;
  if ( MrxFcb->Header.NodeTypeCode != -5086 )
  {
    Status = -1073741808;
    goto LABEL_89;
  }
  MasterIrp = (LARGE_INTEGER *)Irp->AssociatedIrp.MasterIrp;
  v12 = MasterIrp[1];
  v13 = MasterIrp[3];
  if ( v12.QuadPart + v13.QuadPart < (unsigned __int64)v12.QuadPart
    || v12.QuadPart + v13.QuadPart > 0x7FFFFFFFFFFFFFFFuLL )
  {
LABEL_88:
    Status = -1073741811;
LABEL_89:
    if ( !BYTE3(RxContext->RealDevice)
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 26, &WPP_0631a9abaf7433de250bb1791161ea05_Traceguids);
    }
    return (unsigned int)Status;
  }
  v14 = MasterIrp[2];
  if ( v14.QuadPart + v13.QuadPart < (unsigned __int64)v14.QuadPart
    || v14.QuadPart + v13.QuadPart > 0x7FFFFFFFFFFFFFFFuLL )
  {
    goto LABEL_83;
  }
  StartingByte = MasterIrp[2];
  Length = MasterIrp[3];
  if ( IoIs32bitProcess(Irp) )
    LowPart = (int)MasterIrp->LowPart;
  else
    LowPart = MasterIrp->QuadPart;
  RequestorProcess = IoGetRequestorProcess(Irp);
  KeStackAttachProcess(RequestorProcess, &ApcState);
  Status = ObReferenceObjectByHandle(
             (HANDLE)LowPart,
             0x81u,
             (POBJECT_TYPE)IoFileObjectType,
             Irp->RequestorMode,
             &v43,
             0);
  KeUnstackDetachProcess(&ApcState);
  if ( Status < 0 )
  {
LABEL_80:
    v9 = v43;
    goto LABEL_84;
  }
  v44 = 0;
  v45 = 0;
  v17 = RxDecodeFileObject2(v43, &v44, &v45);
  if ( (PDEVICE_OBJECT)v9[1] == FileObject->DeviceObject
    && v17 == -5086
    && *(_QWORD *)(v44 + 120) == *((_QWORD *)&MrxFcb->1 + 15) )
  {
    if ( (*(_DWORD *)(v45 + 72) & 0x400002) == 0 && (*(_DWORD *)(*(_QWORD *)(v45 + 32) + 72LL) & 0x400) == 0 )
    {
      if ( FileObject->SectionObjectPointer->DataSectionObject
        || (v18 = 0, Length.QuadPart + StartingByte.QuadPart > MrxFcb->Header.ValidDataLength.QuadPart) )
      {
        v18 = 1;
      }
      while ( 1 )
      {
        Status = _RxAcquireFcb(MrxFcb, RxContext, (v18 ^ 1) + 1, 0, (PCSTR)Object, HandleInformation);
        if ( Status < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 22, &WPP_0631a9abaf7433de250bb1791161ea05_Traceguids);
          }
          if ( Status == -1073741739 )
            BYTE3(RxContext->RealDevice) = 1;
          goto LABEL_80;
        }
        v22 = 1;
        if ( v18
          || !FileObject->SectionObjectPointer->DataSectionObject
          && StartingByte.QuadPart + Length.QuadPart <= MrxFcb->Header.ValidDataLength.QuadPart )
        {
          break;
        }
        _RxReleaseFcb(RxContext, (PMRX_FCB)&MrxFcb->Header, v20, v21, Objecta);
        v18 = 1;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_qqqiiiq)(
          WPP_GLOBAL_Control->AttachedDevice,
          v19,
          v20,
          RxContext,
          FileObject,
          MasterIrp->QuadPart,
          (LARGE_INTEGER)MasterIrp[1].QuadPart,
          (LARGE_INTEGER)MasterIrp[2].QuadPart,
          (LARGE_INTEGER)MasterIrp[3].QuadPart,
          MrxFcb);
      }
      v23 = Irpa;
      Status = FsRtlCheckOplock(
                 (POPLOCK)&MrxFcb->pNetRoot,
                 Irpa,
                 RxContext,
                 RxUpperOplockBreakCompleteAsync,
                 RxPrePostIrp);
      if ( Status )
        goto LABEL_63;
      v26 = IoGetRequestorProcess(v23);
      if ( !FsRtlFastCheckLockForWrite(
              (PFILE_LOCK)&MrxFcb->FileLock.LockRequestsInProgress,
              &StartingByte,
              &Length,
              0,
              FileObject,
              v26) )
      {
        Status = -1073741740;
LABEL_63:
        _RxReleaseFcb(RxContext, (PMRX_FCB)&MrxFcb->Header, v24, QuadPart, Objectb);
        v9 = v43;
        goto LABEL_84;
      }
      if ( FileObject->SectionObjectPointer->DataSectionObject )
      {
        LOBYTE(v24) = 1;
        v27 = 0;
        RxAcquirePagingIoResource(RxContext, MrxFcb, v24);
        if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
          McTemplateK0p_EtwWriteTransfer(v28, &CcPurgeRequest, &RxContext->LowIoContext.Flags + 1, MrxFcb);
        if ( ++MrxFcb->FcbReleases[3] > 0x10 )
        {
          p_DriverObject = &MrxFcb->RxDeviceObject->DeviceObject.DriverObject;
          LODWORD(v44) = 0;
          MmIsFileSectionActive(p_DriverObject, 7, &v44);
          if ( !(_DWORD)v44
            && (LODWORD(MrxFcb->NonPaged) == HIDWORD(MrxFcb->NonPaged)
             || (*((_DWORD *)&MrxFcb->1 + 41) & 2) == 0
             || (*((_DWORD *)&MrxFcb->1 + 40) & 0x8000000) == 0) )
          {
            v27 = 1;
            MrxFcb->FcbReleases[3] = 0;
          }
        }
        p_StartingByte = &StartingByte;
        if ( v27 )
          p_StartingByte = 0;
        CcCoherencyFlushAndPurgeCache(
          FileObject->SectionObjectPointer,
          p_StartingByte,
          Length.LowPart,
          &v23->IoStatus,
          0);
        if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
          McTemplateK0p_EtwWriteTransfer(v31, &CcPurgeCompletion, &RxContext->LowIoContext.Flags + 1, MrxFcb);
        RxReleasePagingIoResource(RxContext, MrxFcb);
        if ( v23->IoStatus.Status < 0 )
        {
          Status = v23->IoStatus.Status;
          goto LABEL_63;
        }
      }
      if ( StartingByte.QuadPart + Length.QuadPart <= MrxFcb->Header.ValidDataLength.QuadPart )
      {
        _RxReleaseFcb(RxContext, (PMRX_FCB)&MrxFcb->Header, v24, QuadPart, Objectb);
        v22 = 0;
      }
      else
      {
        RdbssDbgExtension = (int)RxContext->RdbssDbgExtension;
        if ( (RdbssDbgExtension & 2) == 0 )
        {
          BYTE3(RxContext->RealDevice) = 1;
          goto LABEL_63;
        }
        LODWORD(RxContext->RdbssDbgExtension) = RdbssDbgExtension & 0xFFFFEFFF;
      }
      RxInitializeLowIoContext(RxContext, 6u, (PLOWIO_CONTEXT)((char *)&RxContext->9 + 120));
      *((_QWORD *)&RxContext->9 + 18) = v43;
      v43 = 0;
      _InterlockedOr8((volatile signed __int8 *)&MrxFcb->FcbTableEntry.HashLinks.Blink, 1u);
      FileObject->Flags |= 0x1000u;
      v33 = RxLowIoSubmit(RxContext, v23, MrxFcb, RxLowIoFsCtlShellCompletion);
      Status = v33;
      if ( v33 == 259 )
      {
LABEL_62:
        if ( !v22 )
          goto LABEL_80;
        goto LABEL_63;
      }
      if ( v33 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          Objectb = v33;
          WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 24, &WPP_0631a9abaf7433de250bb1791161ea05_Traceguids);
        }
        goto LABEL_62;
      }
      if ( v22 )
      {
        if ( StartingByte.QuadPart + Length.QuadPart > MrxFcb->Header.ValidDataLength.QuadPart )
        {
          QuadPart = (const CHAR *)MrxFcb->Header.FileSize.QuadPart;
          v34.QuadPart = (LONGLONG)QuadPart;
          if ( (__int64)QuadPart >= StartingByte.QuadPart + Length.QuadPart )
            v34.QuadPart = StartingByte.QuadPart + Length.QuadPart;
          MrxFcb->Header.ValidDataLength = v34;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_qqq)(
              WPP_GLOBAL_Control->AttachedDevice,
              25,
              &WPP_0631a9abaf7433de250bb1791161ea05_Traceguids,
              QuadPart,
              (LARGE_INTEGER)v34.QuadPart,
              (LARGE_INTEGER)v34.QuadPart);
          }
          if ( v40 )
            CcSetFileSizes(FileObject, (PCC_FILE_SIZES)&MrxFcb->spacer.AllocationSize);
        }
        goto LABEL_63;
      }
      goto LABEL_80;
    }
    Status = -1073741528;
  }
  else
  {
LABEL_83:
    Status = -1073741811;
  }
LABEL_84:
  if ( v9 )
    ObfDereferenceObject(v9);
  if ( Status < 0 )
    goto LABEL_89;
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140019aac  mov     [rsp-8+arg_18], rbx
0x140019ab1  push    rbp
0x140019ab2  push    rsi
0x140019ab3  push    rdi
0x140019ab4  push    r12
0x140019ab6  push    r13
0x140019ab8  push    r14
0x140019aba  push    r15
0x140019abc  lea     rbp, [rsp-27h]
0x140019ac1  sub     rsp, 0C0h
0x140019ac8  mov     rax, cs:__security_cookie
0x140019acf  xor     rax, rsp
0x140019ad2  mov     [rbp+57h+var_38], rax
0x140019ad6  xor     r12d, r12d
0x140019ad9  mov     [rbp+57h+Irp], rdx
0x140019add  mov     rsi, rcx
0x140019ae0  mov     rdi, r8
0x140019ae3  mov     rcx, [rdx+0B8h]
0x140019aea  mov     r15, rdx
0x140019aed  mov     r13, [rcx+30h]
0x140019af1  mov     qword ptr [rbp+57h+StartingByte], r12
0x140019af5  mov     qword ptr [rbp+57h+Length], r12
0x140019af9  mov     rax, [r13+28h]
0x140019afd  test    rax, rax
0x140019b00  jz      short loc_140019B0C
0x140019b02  mov     [rbp+57h+var_A0], 1
0x140019b06  cmp     [rax+8], r12
0x140019b0a  jnz     short loc_140019B10
0x140019b0c  mov     [rbp+57h+var_A0], r12b
0x140019b10  xorps   xmm0, xmm0
0x140019b13  mov     [rbp+57h+var_88], r12
0x140019b17  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink], xmm0
0x140019b1b  mov     r9, r12
0x140019b1e  lea     rax, WPP_GLOBAL_Control
0x140019b25  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink+10h], xmm0
0x140019b29  movups  xmmword ptr [rbp+57h+ApcState.Process], xmm0
0x140019b2d  cmp     dword ptr [rcx+10h], 20h ; ' '
0x140019b31  jb      loc_14001A0D9
0x140019b37  mov     eax, 0EC22h
0x140019b3c  cmp     [r8], ax
0x140019b40  jz      short loc_140019B53
0x140019b42  mov     ebx, 0C0000010h
0x140019b47  lea     rax, WPP_GLOBAL_Control
0x140019b4e  jmp     loc_14001A0DE
0x140019b53  mov     r14, [rdx+18h]
0x140019b57  mov     rax, [r14+8]
0x140019b5b  mov     rdx, [r14+18h]
0x140019b5f  lea     rcx, [rax+rdx]
0x140019b63  cmp     rcx, rax
0x140019b66  jb      loc_14001A0D2
0x140019b6c  mov     r8, 7FFFFFFFFFFFFFFFh
0x140019b76  cmp     rcx, r8
0x140019b79  ja      loc_14001A0D2
0x140019b7f  mov     rax, [r14+10h]
0x140019b83  lea     rcx, [rax+rdx]
0x140019b87  cmp     rcx, rax
0x140019b8a  jb      loc_14001A0B0
0x140019b90  cmp     rcx, r8
0x140019b93  ja      loc_14001A0B0
0x140019b99  mov     qword ptr [rbp+57h+StartingByte], rax
0x140019b9d  mov     rcx, r15; Irp
0x140019ba0  mov     rax, [r14+18h]
0x140019ba4  mov     qword ptr [rbp+57h+Length], rax
0x140019ba8  call    cs:__imp_IoIs32bitProcess
0x140019baf  nop     dword ptr [rax+rax+00h]
0x140019bb4  test    al, al
0x140019bb6  jz      short loc_140019BBD
0x140019bb8  movsxd  rbx, dword ptr [r14]
0x140019bbb  jmp     short loc_140019BC0
0x140019bbd  mov     rbx, [r14]
0x140019bc0  mov     rcx, r15; Irp
0x140019bc3  call    cs:__imp_IoGetRequestorProcess
0x140019bca  nop     dword ptr [rax+rax+00h]
0x140019bcf  mov     rcx, rax; PROCESS
0x140019bd2  lea     rdx, [rbp+57h+ApcState]; ApcState
0x140019bd6  call    cs:__imp_KeStackAttachProcess
0x140019bdd  nop     dword ptr [rax+rax+00h]
0x140019be2  mov     r8, cs:__imp_IoFileObjectType
0x140019be9  lea     rax, [rbp+57h+var_88]
0x140019bed  mov     r9b, [r15+40h]; AccessMode
0x140019bf1  mov     edx, 81h; DesiredAccess
0x140019bf6  mov     [rsp+0F0h+HandleInformation], r12; SerialNumber
0x140019bfb  mov     rcx, rbx; Handle
0x140019bfe  mov     [rsp+0F0h+Object], rax; SerialNumber
0x140019c03  mov     r8, [r8]; ObjectType
0x140019c06  call    cs:__imp_ObReferenceObjectByHandle
0x140019c0d  nop     dword ptr [rax+rax+00h]
0x140019c12  lea     rcx, [rbp+57h+ApcState]; ApcState
0x140019c16  mov     ebx, eax
0x140019c18  call    cs:__imp_KeUnstackDetachProcess
0x140019c1f  nop     dword ptr [rax+rax+00h]
0x140019c24  test    ebx, ebx
0x140019c26  js      loc_14001A09E
0x140019c2c  mov     r9, [rbp+57h+var_88]
0x140019c30  lea     r8, [rbp+57h+var_78]
0x140019c34  mov     rcx, r9
0x140019c37  mov     [rbp+57h+var_80], r12
0x140019c3b  lea     rdx, [rbp+57h+var_80]
0x140019c3f  mov     [rbp+57h+var_78], r12
0x140019c43  call    RxDecodeFileObject2
0x140019c48  mov     rcx, [r13+8]
0x140019c4c  cmp     [r9+8], rcx
0x140019c50  jnz     loc_14001A0B0
0x140019c56  mov     ecx, 0EC22h
0x140019c5b  cmp     ax, cx
0x140019c5e  jnz     loc_14001A0B0
0x140019c64  mov     rax, [rbp+57h+var_80]
0x140019c68  mov     rcx, [rdi+78h]
0x140019c6c  cmp     [rax+78h], rcx
0x140019c70  jnz     loc_14001A0B0
0x140019c76  mov     rcx, [rbp+57h+var_78]
0x140019c7a  test    dword ptr [rcx+48h], 400002h
0x140019c81  jnz     loc_14001A0A4
0x140019c87  mov     rax, [rcx+20h]
0x140019c8b  test    dword ptr [rax+48h], 400h
0x140019c92  jnz     loc_14001A0A4
0x140019c98  mov     rax, [r13+28h]
0x140019c9c  cmp     [rax], r12
0x140019c9f  jnz     short loc_140019CB2
0x140019ca1  mov     rcx, qword ptr [rbp+57h+StartingByte]
0x140019ca5  mov     r15b, r12b
0x140019ca8  add     rcx, qword ptr [rbp+57h+Length]
0x140019cac  cmp     rcx, [rdi+28h]
0x140019cb0  jle     short loc_140019CB5
0x140019cb2  mov     r15b, 1
0x140019cb5  movzx   r8d, r15b
0x140019cb9  xor     r9d, r9d; LineNumber
0x140019cbc  xor     r8d, 1
0x140019cc0  mov     rdx, rsi; RxContext
0x140019cc3  inc     r8d; Mode
0x140019cc6  mov     rcx, rdi; Fcb
0x140019cc9  call    __RxAcquireFcb
0x140019cce  mov     ebx, eax
0x140019cd0  test    eax, eax
0x140019cd2  js      loc_14001A056
0x140019cd8  mov     r12b, 1
0x140019cdb  test    r15b, r15b
0x140019cde  jnz     short loc_140019D0B
0x140019ce0  mov     rax, [r13+28h]
0x140019ce4  cmp     qword ptr [rax], 0
0x140019ce8  jnz     short loc_140019CF8
0x140019cea  mov     rcx, qword ptr [rbp+57h+Length]
0x140019cee  add     rcx, qword ptr [rbp+57h+StartingByte]
0x140019cf2  cmp     rcx, [rdi+28h]
0x140019cf6  jle     short loc_140019D0B
0x140019cf8  mov     rdx, rdi; MrxFcb
0x140019cfb  mov     rcx, rsi; RxContext
0x140019cfe  call    __RxReleaseFcb
0x140019d03  mov     r15b, r12b
0x140019d06  xor     r12d, r12d
0x140019d09  jmp     short loc_140019CB5
0x140019d0b  mov     rcx, cs:WPP_GLOBAL_Control
0x140019d12  lea     r15, WPP_GLOBAL_Control
0x140019d19  cmp     rcx, r15
0x140019d1c  jz      short loc_140019D64
0x140019d1e  mov     eax, [rcx+2Ch]
0x140019d21  test    al, 10h
0x140019d23  jz      short loc_140019D64
0x140019d25  cmp     byte ptr [rcx+29h], 2
0x140019d29  jb      short loc_140019D64
0x140019d2b  mov     rax, [r14+18h]
0x140019d2f  mov     r9, rsi
0x140019d32  mov     rcx, [rcx+18h]
0x140019d36  mov     [rsp+0F0h+var_A8], rdi
0x140019d3b  mov     [rsp+0F0h+var_B0], rax
0x140019d40  mov     rax, [r14+10h]
0x140019d44  mov     [rsp+0F0h+var_B8], rax
0x140019d49  mov     rax, [r14+8]
0x140019d4d  mov     [rsp+0F0h+var_C0], rax
0x140019d52  mov     rax, [r14]
0x140019d55  mov     [rsp+0F0h+HandleInformation], rax
0x140019d5a  mov     [rsp+0F0h+Object], r13
0x140019d5f  call    WPP_SF_qqqiiiq
0x140019d64  mov     r14, [rbp+57h+Irp]
0x140019d68  lea     rax, RxPrePostIrp
0x140019d6f  mov     rdx, r14; Irp
0x140019d72  mov     [rsp+0F0h+Object], rax; PostIrpRoutine
0x140019d77  lea     rcx, [rdi+58h]; Oplock
0x140019d7b  mov     r8, rsi; Context
0x140019d7e  lea     r9, RxUpperOplockBreakCompleteAsync; CompletionRoutine
0x140019d85  call    cs:__imp_FsRtlCheckOplock
0x140019d8c  nop     dword ptr [rax+rax+00h]
0x140019d91  mov     ebx, eax
0x140019d93  test    eax, eax
0x140019d95  jnz     loc_140019FBE
0x140019d9b  mov     rcx, r14; Irp
0x140019d9e  call    cs:__imp_IoGetRequestorProcess
0x140019da5  nop     dword ptr [rax+rax+00h]
0x140019daa  mov     [rsp+0F0h+HandleInformation], rax; ProcessId
0x140019daf  lea     rcx, [rdi+218h]; FileLock
0x140019db6  xor     r9d, r9d; Key
0x140019db9  mov     [rsp+0F0h+Object], r13; FileObject
0x140019dbe  lea     r8, [rbp+57h+Length]; Length
0x140019dc2  lea     rdx, [rbp+57h+StartingByte]; StartingByte
0x140019dc6  call    cs:__imp_FsRtlFastCheckLockForWrite
0x140019dcd  nop     dword ptr [rax+rax+00h]
0x140019dd2  test    al, al
0x140019dd4  jnz     short loc_140019DE0
0x140019dd6  mov     ebx, 0C0000054h
0x140019ddb  jmp     loc_140019FBE
0x140019de0  mov     rax, [r13+28h]
0x140019de4  cmp     qword ptr [rax], 0
0x140019de8  jz      loc_140019EF4
0x140019dee  mov     r8b, r12b
0x140019df1  mov     rdx, rdi
0x140019df4  mov     rcx, rsi
0x140019df7  xor     r15b, r15b
0x140019dfa  call    RxAcquirePagingIoResource
0x140019dff  test    byte ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4, 8
0x140019e06  jz      short loc_140019E1E
0x140019e08  lea     r8, [rsi+19Ch]
0x140019e0f  mov     r9, rdi
0x140019e12  lea     rdx, CcPurgeRequest
0x140019e19  call    McTemplateK0p_EtwWriteTransfer
0x140019e1e  inc     dword ptr [rdi+27Ch]
0x140019e24  cmp     dword ptr [rdi+27Ch], 10h
0x140019e2b  jbe     short loc_140019E8B
0x140019e2d  mov     rcx, [rdi+130h]
0x140019e34  lea     r8, [rbp+57h+var_80]
0x140019e38  add     rcx, 8
0x140019e3c  mov     dword ptr [rbp+57h+var_80], 0
0x140019e43  mov     edx, 7
0x140019e48  call    cs:__imp_MmIsFileSectionActive
0x140019e4f  nop     dword ptr [rax+rax+00h]
0x140019e54  cmp     dword ptr [rbp+57h+var_80], 0
0x140019e58  jnz     short loc_140019E8B
0x140019e5a  mov     eax, [rdi+0BCh]
0x140019e60  cmp     [rdi+0B8h], eax
0x140019e66  jz      short loc_140019E7E
0x140019e68  mov     eax, [rdi+0A4h]
0x140019e6e  test    al, 2
0x140019e70  jz      short loc_140019E7E
0x140019e72  test    dword ptr [rdi+0A0h], 8000000h
0x140019e7c  jnz     short loc_140019E8B
0x140019e7e  mov     r15b, r12b
0x140019e81  mov     dword ptr [rdi+27Ch], 0
0x140019e8b  mov     r8d, dword ptr [rbp+57h+Length]; Length
0x140019e8f  lea     rdx, [rbp+57h+StartingByte]
0x140019e93  mov     rcx, [r13+28h]; SectionObjectPointer
0x140019e97  lea     r9, [r14+30h]; IoStatus
0x140019e9b  xor     eax, eax
0x140019e9d  test    r15b, r15b
0x140019ea0  mov     dword ptr [rsp+0F0h+Object], eax; SerialNumber
0x140019ea4  cmovnz  rdx, rax; FileOffset
0x140019ea8  call    cs:__imp_CcCoherencyFlushAndPurgeCache
0x140019eaf  nop     dword ptr [rax+rax+00h]
0x140019eb4  test    byte ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4, 8
0x140019ebb  jz      short loc_140019ED3
0x140019ebd  lea     r8, [rsi+19Ch]
0x140019ec4  mov     r9, rdi
0x140019ec7  lea     rdx, CcPurgeCompletion
0x140019ece  call    McTemplateK0p_EtwWriteTransfer
0x140019ed3  mov     rdx, rdi
0x140019ed6  mov     rcx, rsi
0x140019ed9  call    RxReleasePagingIoResource
0x140019ede  mov     eax, [r14+30h]
0x140019ee2  test    eax, eax
0x140019ee4  jns     short loc_140019EED
0x140019ee6  mov     ebx, eax
0x140019ee8  jmp     loc_140019FBE
0x140019eed  lea     r15, WPP_GLOBAL_Control
0x140019ef4  mov     rcx, qword ptr [rbp+57h+Length]
0x140019ef8  add     rcx, qword ptr [rbp+57h+StartingByte]
0x140019efc  cmp     rcx, [rdi+28h]
0x140019f00  jle     short loc_140019F1B
0x140019f02  mov     eax, [rsi+78h]
0x140019f05  test    al, 2
0x140019f07  jnz     short loc_140019F12
0x140019f09  mov     [rsi+23h], r12b
0x140019f0d  jmp     loc_140019FBE
0x140019f12  btr     eax, 0Ch
0x140019f16  mov     [rsi+78h], eax
0x140019f19  jmp     short loc_140019F29
0x140019f1b  mov     rdx, rdi; MrxFcb
0x140019f1e  mov     rcx, rsi; RxContext
0x140019f21  call    __RxReleaseFcb
0x140019f26  xor     r12b, r12b
0x140019f29  lea     r8, [rsi+208h]; LowIoContext
0x140019f30  mov     edx, 6; Operation
0x140019f35  mov     rcx, rsi; RxContext
0x140019f38  call    RxInitializeLowIoContext
0x140019f3d  mov     rax, [rbp+57h+var_88]
0x140019f41  mov     [rsi+220h], rax
0x140019f48  mov     [rbp+57h+var_88], 0
0x140019f50  lock or byte ptr [rdi+100h], 1
0x140019f58  bts     dword ptr [r13+50h], 0Ch
0x140019f5e  lea     r9, RxLowIoFsCtlShellCompletion; CompletionRoutine
0x140019f65  mov     r8, rdi; Fcb
0x140019f68  mov     rdx, r14; Irp
0x140019f6b  mov     rcx, rsi; RxContext
0x140019f6e  call    RxLowIoSubmit
0x140019f73  mov     ebx, eax
0x140019f75  cmp     eax, 103h
0x140019f7a  jz      short loc_140019FB5
0x140019f7c  test    eax, eax
0x140019f7e  jns     short loc_140019FD5
0x140019f80  mov     rcx, cs:WPP_GLOBAL_Control
0x140019f87  cmp     rcx, r15
0x140019f8a  jz      short loc_140019FB5
0x140019f8c  mov     eax, [rcx+2Ch]
  ... truncated ...
```
