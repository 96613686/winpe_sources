# RxProcessOffloadWrite

- ea: `0x140046c48`
- end: `0x1400470ce`
- name: `RxProcessOffloadWrite`
- size: `1158`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext, PIRP Irp, PMRX_FCB MrxFcb)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

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
- `0x14001afa8`
- `0x14001b2b8`
- `0x140046c48`
- `0x140057660`
- `0x140067ad0`
- `0x140069970`

## import_xrefs

- `ntoskrnl!FsRtlCheckOplock` at `0x140046e06`
- `ntoskrnl!FsRtlCheckOplock` at `0x140046e06`
- `ntoskrnl!IoGetRequestorProcess` at `0x140046e1f`
- `ntoskrnl!IoGetRequestorProcess` at `0x140046e1f`
- `ntoskrnl!CcSetFileSizes` at `0x140047006`
- `ntoskrnl!CcSetFileSizes` at `0x140047006`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x140046eb3`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x140046eb3`
- `ntoskrnl!MmIsFileSectionActive` at `0x140046dcd`
- `ntoskrnl!MmIsFileSectionActive` at `0x140046dcd`
- `ntoskrnl!FsRtlFastCheckLockForWrite` at `0x140046e47`
- `ntoskrnl!FsRtlFastCheckLockForWrite` at `0x140046e47`

## pseudocode

```c
__int64 __fastcall RxProcessOffloadWrite(PRX_CONTEXT RxContext, PIRP Irp, struct _FCB *MrxFcb)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  struct _FILE_OBJECT *FileObject; // r15
  PSECTION_OBJECT_POINTERS SectionObjectPointer; // rax
  unsigned int Status; // ebx
  LARGE_INTEGER *MasterIrp; // r14
  unsigned __int64 QuadPart; // rcx
  unsigned __int64 v12; // rdx
  NTSTATUS v13; // eax
  __int64 v14; // r8
  PRDBSS_DEVICE_OBJECT RxDeviceObject; // rcx
  LONGLONG v16; // r8
  const CHAR *v17; // r9
  PEPROCESS RequestorProcess; // rax
  __int64 v19; // rcx
  __int64 v20; // rcx
  int RdbssDbgExtension; // eax
  char v22; // r14
  NTSTATUS v23; // eax
  __int64 v24; // rdx
  wchar_t *Buffer; // rax
  LARGE_INTEGER v26; // rdx
  const CHAR *PostIrpRoutine; // [rsp+20h] [rbp-30h]
  NTSTATUS PostIrpRoutinea; // [rsp+20h] [rbp-30h]
  ULONG ProcessId; // [rsp+28h] [rbp-28h]
  LARGE_INTEGER Length; // [rsp+40h] [rbp-10h] BYREF
  char v32; // [rsp+90h] [rbp+40h]
  int v33; // [rsp+98h] [rbp+48h] BYREF
  LARGE_INTEGER StartingByte; // [rsp+A8h] [rbp+58h] BYREF

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  FileObject = CurrentStackLocation->FileObject;
  StartingByte.QuadPart = 0;
  Length.QuadPart = 0;
  SectionObjectPointer = FileObject->SectionObjectPointer;
  if ( !SectionObjectPointer || (v32 = 1, !SectionObjectPointer->SharedCacheMap) )
    v32 = 0;
  if ( CurrentStackLocation->Parameters.Create.Options >= 0x220 )
  {
    if ( MrxFcb->Header.NodeTypeCode != -5086 )
    {
      Status = -1073741808;
      goto LABEL_60;
    }
    MasterIrp = (LARGE_INTEGER *)Irp->AssociatedIrp.MasterIrp;
    QuadPart = MasterIrp[1].QuadPart;
    v12 = QuadPart + MasterIrp[2].QuadPart;
    if ( v12 < QuadPart || v12 > 0x7FFFFFFFFFFFFFFFLL )
    {
      Status = -1073741811;
      goto LABEL_60;
    }
    v13 = _RxAcquireFcb(MrxFcb, RxContext, 1u, 0, PostIrpRoutine, ProcessId);
    Status = v13;
    if ( v13 < 0 )
    {
      if ( v13 == -1073741739 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_0631a9abaf7433de250bb1791161ea05_Traceguids);
        }
        BYTE3(RxContext->RealDevice) = 1;
      }
      goto LABEL_60;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      PostIrpRoutinea = (int)MrxFcb;
      WPP_SF_qqqii(WPP_GLOBAL_Control->AttachedDevice, 18, v14, RxContext);
    }
    RxDeviceObject = MrxFcb->RxDeviceObject;
    StartingByte = MasterIrp[1];
    Length = MasterIrp[2];
    v33 = 0;
    MmIsFileSectionActive(&RxDeviceObject->DriverObject, 7, &v33);
    if ( v33 )
    {
      Status = -1073741245;
    }
    else
    {
      Status = FsRtlCheckOplock(
                 (POPLOCK)&MrxFcb->pNetRoot,
                 Irp,
                 RxContext,
                 RxUpperOplockBreakCompleteAsync,
                 RxPrePostIrp);
      if ( !Status )
      {
        RequestorProcess = IoGetRequestorProcess(Irp);
        if ( FsRtlFastCheckLockForWrite(
               (PFILE_LOCK)&MrxFcb->FileLock.LockRequestsInProgress,
               &StartingByte,
               &Length,
               0,
               FileObject,
               RequestorProcess) )
        {
          if ( !FileObject->SectionObjectPointer->DataSectionObject )
            goto LABEL_33;
          LOBYTE(v16) = 1;
          RxAcquirePagingIoResource(RxContext, MrxFcb, v16);
          if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
            McTemplateK0p_EtwWriteTransfer(v19, CcPurgeRequest, &RxContext->LowIoContext.Flags + 1, MrxFcb);
          CcCoherencyFlushAndPurgeCache(
            FileObject->SectionObjectPointer,
            &StartingByte,
            Length.LowPart,
            &Irp->IoStatus,
            0);
          if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
            McTemplateK0p_EtwWriteTransfer(v20, CcPurgeCompletion, &RxContext->LowIoContext.Flags + 1, MrxFcb);
          RxReleasePagingIoResource(RxContext, MrxFcb);
          if ( Irp->IoStatus.Status >= 0 )
          {
LABEL_33:
            if ( StartingByte.QuadPart + Length.QuadPart <= MrxFcb->Header.ValidDataLength.QuadPart )
            {
              _RxReleaseFcb(RxContext, (PMRX_FCB)&MrxFcb->Header, v16, v17, PostIrpRoutinea);
              v22 = 0;
            }
            else
            {
              RdbssDbgExtension = (int)RxContext->RdbssDbgExtension;
              if ( (RdbssDbgExtension & 2) == 0 )
              {
                BYTE3(RxContext->RealDevice) = 1;
                goto LABEL_56;
              }
              v22 = 1;
              LODWORD(RxContext->RdbssDbgExtension) = RdbssDbgExtension & 0xFFFFEFFF;
            }
            RxInitializeLowIoContext(RxContext, 6u, (PLOWIO_CONTEXT)((char *)&RxContext->9 + 120));
            v23 = RxLowIoSubmit(RxContext, Irp, MrxFcb, RxLowIoFsCtlShellCompletion);
            Status = v23;
            if ( v23 != 259 )
            {
              if ( v23 >= 0 && RxContext->InformationToReturn >= 0x10 )
              {
                _InterlockedOr8((volatile signed __int8 *)&MrxFcb->FcbTableEntry.HashLinks.Blink, 1u);
                FileObject->Flags |= 0x1000u;
                if ( !v22 )
                  return Status;
                Buffer = RxContext->Create.TransportName.Buffer;
                v26.QuadPart = StartingByte.QuadPart + *((_QWORD *)Buffer + 1);
                if ( v26.QuadPart > MrxFcb->Header.ValidDataLength.QuadPart )
                {
                  v17 = (const CHAR *)MrxFcb->Header.FileSize.QuadPart;
                  v16 = (LONGLONG)v17;
                  if ( (__int64)v17 >= v26.QuadPart )
                    v16 = StartingByte.QuadPart + *((_QWORD *)Buffer + 1);
                  MrxFcb->Header.ValidDataLength.QuadPart = v16;
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                  {
                    PostIrpRoutinea = v16;
                    WPP_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_0631a9abaf7433de250bb1791161ea05_Traceguids);
                  }
                  if ( v32 )
                    CcSetFileSizes(FileObject, (PCC_FILE_SIZES)&MrxFcb->spacer.AllocationSize);
                }
                goto LABEL_56;
              }
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                PostIrpRoutinea = RxContext->StoredStatus;
                WPP_SF_qDP(WPP_GLOBAL_Control->AttachedDevice, v24, v16, RxContext);
              }
            }
            if ( !v22 )
              goto LABEL_57;
            goto LABEL_56;
          }
          Status = Irp->IoStatus.Status;
        }
        else
        {
          Status = -1073741740;
        }
      }
    }
LABEL_56:
    _RxReleaseFcb(RxContext, (PMRX_FCB)&MrxFcb->Header, v16, v17, PostIrpRoutinea);
LABEL_57:
    if ( (Status & 0x80000000) == 0 )
      return Status;
    goto LABEL_60;
  }
  Status = -1073741811;
LABEL_60:
  if ( !BYTE3(RxContext->RealDevice)
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_0631a9abaf7433de250bb1791161ea05_Traceguids, RxContext);
  }
  return Status;
}

```

## disassembly

```asm
0x140046c48  mov     [rsp-38h+arg_10], rbx
0x140046c4d  push    rbp
0x140046c4e  push    rsi
0x140046c4f  push    rdi
0x140046c50  push    r12
0x140046c52  push    r13
0x140046c54  push    r14
0x140046c56  push    r15
0x140046c58  mov     rbp, rsp
0x140046c5b  sub     rsp, 50h
0x140046c5f  xor     r12d, r12d
0x140046c62  mov     rdi, rcx
0x140046c65  mov     rcx, [rdx+0B8h]
0x140046c6c  mov     rsi, r8
0x140046c6f  mov     r13, rdx
0x140046c72  mov     r15, [rcx+30h]
0x140046c76  mov     qword ptr [rbp+StartingByte], r12
0x140046c7a  mov     qword ptr [rbp+Length], r12
0x140046c7e  mov     rax, [r15+28h]
0x140046c82  test    rax, rax
0x140046c85  jz      short loc_140046C91
0x140046c87  mov     [rbp+arg_0], 1
0x140046c8b  cmp     [rax+8], r12
0x140046c8f  jnz     short loc_140046C95
0x140046c91  mov     [rbp+arg_0], r12b
0x140046c95  cmp     dword ptr [rcx+10h], 220h
0x140046c9c  lea     rax, WPP_GLOBAL_Control
0x140046ca3  jnb     short loc_140046CAF
0x140046ca5  mov     ebx, 0C000000Dh
0x140046caa  jmp     loc_140047078
0x140046caf  mov     eax, 0EC22h
0x140046cb4  cmp     [r8], ax
0x140046cb8  jz      short loc_140046CC4
0x140046cba  mov     ebx, 0C0000010h
0x140046cbf  jmp     loc_140047071
0x140046cc4  mov     r14, [rdx+18h]
0x140046cc8  mov     rcx, [r14+8]
0x140046ccc  mov     rdx, [r14+10h]
0x140046cd0  add     rdx, rcx
0x140046cd3  cmp     rdx, rcx
0x140046cd6  jb      loc_14004706C
0x140046cdc  mov     rax, 7FFFFFFFFFFFFFFFh
0x140046ce6  cmp     rdx, rax
0x140046ce9  ja      loc_14004706C
0x140046cef  xor     r9d, r9d; LineNumber
0x140046cf2  mov     rdx, rdi; RxContext
0x140046cf5  mov     rcx, rsi; Fcb
0x140046cf8  lea     r8d, [r9+1]; Mode
0x140046cfc  call    __RxAcquireFcb
0x140046d01  mov     ebx, eax
0x140046d03  test    eax, eax
0x140046d05  jns     short loc_140046D58
0x140046d07  cmp     eax, 0C0000055h
0x140046d0c  jnz     loc_140047071
0x140046d12  mov     rcx, cs:WPP_GLOBAL_Control
0x140046d19  lea     rax, WPP_GLOBAL_Control
0x140046d20  cmp     rcx, rax
0x140046d23  jz      short loc_140046D4F
0x140046d25  mov     edx, [rcx+2Ch]
0x140046d28  test    dl, 10h
0x140046d2b  jz      short loc_140046D4F
0x140046d2d  cmp     byte ptr [rcx+29h], 4
0x140046d31  jb      short loc_140046D4F
0x140046d33  mov     rcx, [rcx+18h]
0x140046d37  lea     r8, WPP_0631a9abaf7433de250bb1791161ea05_Traceguids
0x140046d3e  mov     edx, 11h
0x140046d43  call    WPP_SF_
0x140046d48  lea     rax, WPP_GLOBAL_Control
0x140046d4f  mov     byte ptr [rdi+23h], 1
0x140046d53  jmp     loc_140047078
0x140046d58  mov     rcx, cs:WPP_GLOBAL_Control
0x140046d5f  lea     rax, WPP_GLOBAL_Control
0x140046d66  cmp     rcx, rax
0x140046d69  jz      short loc_140046DA5
0x140046d6b  mov     eax, [rcx+2Ch]
0x140046d6e  test    al, 10h
0x140046d70  jz      short loc_140046DA5
0x140046d72  cmp     byte ptr [rcx+29h], 2
0x140046d76  jb      short loc_140046DA5
0x140046d78  mov     rax, [r14+8]
0x140046d7c  mov     edx, 12h
0x140046d81  mov     rcx, [rcx+18h]
0x140046d85  mov     r9, rdi
0x140046d88  mov     [rsp+50h+var_18], rax
0x140046d8d  mov     rax, [r14+10h]
0x140046d91  mov     [rsp+50h+var_20], rax
0x140046d96  mov     [rsp+50h+ProcessId], r15
0x140046d9b  mov     [rsp+50h+PostIrpRoutine], rsi
0x140046da0  call    WPP_SF_qqqii
0x140046da5  mov     rax, [r14+8]
0x140046da9  lea     r8, [rbp+arg_8]
0x140046dad  mov     rcx, [rsi+130h]
0x140046db4  mov     edx, 7
0x140046db9  mov     qword ptr [rbp+StartingByte], rax
0x140046dbd  add     rcx, 8
0x140046dc1  mov     rax, [r14+10h]
0x140046dc5  mov     qword ptr [rbp+Length], rax
0x140046dc9  mov     [rbp+arg_8], r12d
0x140046dcd  call    cs:__imp_MmIsFileSectionActive
0x140046dd4  nop     dword ptr [rax+rax+00h]
0x140046dd9  cmp     [rbp+arg_8], r12d
0x140046ddd  jz      short loc_140046DE9
0x140046ddf  mov     ebx, 0C0000243h
0x140046de4  jmp     loc_14004705B
0x140046de9  lea     rax, RxPrePostIrp
0x140046df0  mov     r8, rdi; Context
0x140046df3  lea     rcx, [rsi+58h]; Oplock
0x140046df7  mov     [rsp+50h+PostIrpRoutine], rax; PostIrpRoutine
0x140046dfc  lea     r9, RxUpperOplockBreakCompleteAsync; CompletionRoutine
0x140046e03  mov     rdx, r13; Irp
0x140046e06  call    cs:__imp_FsRtlCheckOplock
0x140046e0d  nop     dword ptr [rax+rax+00h]
0x140046e12  mov     ebx, eax
0x140046e14  test    eax, eax
0x140046e16  jnz     loc_14004705B
0x140046e1c  mov     rcx, r13; Irp
0x140046e1f  call    cs:__imp_IoGetRequestorProcess
0x140046e26  nop     dword ptr [rax+rax+00h]
0x140046e2b  mov     [rsp+50h+ProcessId], rax; ProcessId
0x140046e30  lea     rcx, [rsi+218h]; FileLock
0x140046e37  xor     r9d, r9d; Key
0x140046e3a  mov     [rsp+50h+PostIrpRoutine], r15; SerialNumber
0x140046e3f  lea     r8, [rbp+Length]; Length
0x140046e43  lea     rdx, [rbp+StartingByte]; StartingByte
0x140046e47  call    cs:__imp_FsRtlFastCheckLockForWrite
0x140046e4e  nop     dword ptr [rax+rax+00h]
0x140046e53  test    al, al
0x140046e55  jnz     short loc_140046E61
0x140046e57  mov     ebx, 0C0000054h
0x140046e5c  jmp     loc_14004705B
0x140046e61  mov     rax, [r15+28h]
0x140046e65  cmp     [rax], r12
0x140046e68  jz      loc_140046EF4
0x140046e6e  mov     r8b, 1
0x140046e71  mov     rdx, rsi
0x140046e74  mov     rcx, rdi
0x140046e77  call    RxAcquirePagingIoResource
0x140046e7c  test    byte ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4, 8
0x140046e83  lea     r14, [rdi+19Ch]
0x140046e8a  jz      short loc_140046E9E
0x140046e8c  mov     r9, rsi
0x140046e8f  lea     rdx, CcPurgeRequest
0x140046e96  mov     r8, r14
0x140046e99  call    McTemplateK0p_EtwWriteTransfer
0x140046e9e  mov     r8d, dword ptr [rbp+Length]; Length
0x140046ea2  lea     r9, [r13+30h]; IoStatus
0x140046ea6  mov     rcx, [r15+28h]; SectionObjectPointer
0x140046eaa  lea     rdx, [rbp+StartingByte]; FileOffset
0x140046eae  mov     dword ptr [rsp+50h+PostIrpRoutine], r12d; Flags
0x140046eb3  call    cs:__imp_CcCoherencyFlushAndPurgeCache
0x140046eba  nop     dword ptr [rax+rax+00h]
0x140046ebf  test    byte ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4, 8
0x140046ec6  jz      short loc_140046EDA
0x140046ec8  mov     r9, rsi
0x140046ecb  lea     rdx, CcPurgeCompletion
0x140046ed2  mov     r8, r14
0x140046ed5  call    McTemplateK0p_EtwWriteTransfer
0x140046eda  mov     rdx, rsi
0x140046edd  mov     rcx, rdi
0x140046ee0  call    RxReleasePagingIoResource
0x140046ee5  mov     eax, [r13+30h]
0x140046ee9  test    eax, eax
0x140046eeb  jns     short loc_140046EF4
0x140046eed  mov     ebx, eax
0x140046eef  jmp     loc_14004705B
0x140046ef4  mov     rcx, qword ptr [rbp+Length]
0x140046ef8  add     rcx, qword ptr [rbp+StartingByte]
0x140046efc  cmp     rcx, [rsi+28h]
0x140046f00  jle     short loc_140046F1E
0x140046f02  mov     eax, [rdi+78h]
0x140046f05  test    al, 2
0x140046f07  jnz     short loc_140046F12
0x140046f09  mov     byte ptr [rdi+23h], 1
0x140046f0d  jmp     loc_14004705B
0x140046f12  btr     eax, 0Ch
0x140046f16  mov     r14b, 1
0x140046f19  mov     [rdi+78h], eax
0x140046f1c  jmp     short loc_140046F2C
0x140046f1e  mov     rdx, rsi; MrxFcb
0x140046f21  mov     rcx, rdi; RxContext
0x140046f24  call    __RxReleaseFcb
0x140046f29  mov     r14b, r12b
0x140046f2c  lea     r8, [rdi+208h]; LowIoContext
0x140046f33  mov     edx, 6; Operation
0x140046f38  mov     rcx, rdi; RxContext
0x140046f3b  call    RxInitializeLowIoContext
0x140046f40  lea     r9, RxLowIoFsCtlShellCompletion; CompletionRoutine
0x140046f47  mov     r8, rsi; Fcb
0x140046f4a  mov     rdx, r13; Irp
0x140046f4d  mov     rcx, rdi; RxContext
0x140046f50  call    RxLowIoSubmit
0x140046f55  mov     ebx, eax
0x140046f57  cmp     eax, 103h
0x140046f5c  jz      loc_140047056
0x140046f62  test    eax, eax
0x140046f64  js      loc_140047014
0x140046f6a  cmp     qword ptr [rdi+0B8h], 10h
0x140046f72  jb      loc_140047014
0x140046f78  lock or byte ptr [rsi+100h], 1
0x140046f80  bts     dword ptr [r15+50h], 0Ch
0x140046f86  test    r14b, r14b
0x140046f89  jz      loc_1400470B3
0x140046f8f  mov     rax, [rdi+230h]
0x140046f96  mov     rdx, [rax+8]
0x140046f9a  add     rdx, qword ptr [rbp+StartingByte]
0x140046f9e  cmp     rdx, [rsi+28h]
0x140046fa2  jle     loc_14004705B
0x140046fa8  mov     r9, [rsi+20h]
0x140046fac  cmp     r9, rdx
0x140046faf  mov     r8, r9
0x140046fb2  cmovge  r8, rdx
0x140046fb6  mov     [rsi+28h], r8
0x140046fba  mov     rcx, cs:WPP_GLOBAL_Control
0x140046fc1  lea     rax, WPP_GLOBAL_Control
0x140046fc8  cmp     rcx, rax
0x140046fcb  jz      short loc_140046FF9
0x140046fcd  mov     eax, [rcx+2Ch]
0x140046fd0  test    al, 10h
0x140046fd2  jz      short loc_140046FF9
0x140046fd4  cmp     byte ptr [rcx+29h], 2
0x140046fd8  jb      short loc_140046FF9
0x140046fda  mov     rcx, [rcx+18h]
0x140046fde  mov     edx, 14h
0x140046fe3  mov     [rsp+50h+ProcessId], r8
0x140046fe8  mov     [rsp+50h+PostIrpRoutine], r8
0x140046fed  lea     r8, WPP_0631a9abaf7433de250bb1791161ea05_Traceguids
0x140046ff4  call    WPP_SF_qqq
0x140046ff9  cmp     [rbp+arg_0], r12b
0x140046ffd  jz      short loc_14004705B
0x140046fff  lea     rdx, [rsi+18h]; FileSizes
0x140047003  mov     rcx, r15; FileObject
0x140047006  call    cs:__imp_CcSetFileSizes
0x14004700d  nop     dword ptr [rax+rax+00h]
0x140047012  jmp     short loc_14004705B
0x140047014  mov     rcx, cs:WPP_GLOBAL_Control
0x14004701b  lea     rax, WPP_GLOBAL_Control
0x140047022  cmp     rcx, rax
0x140047025  jz      short loc_140047056
0x140047027  mov     eax, [rcx+2Ch]
0x14004702a  test    al, 10h
0x14004702c  jz      short loc_140047056
0x14004702e  cmp     byte ptr [rcx+29h], 4
0x140047032  jb      short loc_140047056
0x140047034  mov     rax, [rdi+0B8h]
0x14004703b  mov     r9, rdi
0x14004703e  mov     rcx, [rcx+18h]
0x140047042  mov     [rsp+50h+ProcessId], rax
0x140047047  mov     eax, [rdi+0B0h]
0x14004704d  mov     dword ptr [rsp+50h+PostIrpRoutine], eax; SerialNumber
0x140047051  call    WPP_SF_qDP
0x140047056  test    r14b, r14b
0x140047059  jz      short loc_140047066
0x14004705b  mov     rdx, rsi; MrxFcb
0x14004705e  mov     rcx, rdi; RxContext
0x140047061  call    __RxReleaseFcb
0x140047066  test    ebx, ebx
0x140047068  jns     short loc_1400470B3
0x14004706a  jmp     short loc_140047071
0x14004706c  mov     ebx, 0C000000Dh
0x140047071  lea     rax, WPP_GLOBAL_Control
0x140047078  cmp     [rdi+23h], r12b
0x14004707c  jnz     short loc_1400470B3
0x14004707e  mov     rcx, cs:WPP_GLOBAL_Control
0x140047085  cmp     rcx, rax
0x140047088  jz      short loc_1400470B3
0x14004708a  mov     eax, [rcx+2Ch]
0x14004708d  test    al, 1
0x14004708f  jz      short loc_1400470B3
0x140047091  cmp     byte ptr [rcx+29h], 1
0x140047095  jb      short loc_1400470B3
0x140047097  mov     rcx, [rcx+18h]
0x14004709b  lea     r8, WPP_0631a9abaf7433de250bb1791161ea05_Traceguids
0x1400470a2  mov     edx, 15h
0x1400470a7  mov     dword ptr [rsp+50h+PostIrpRoutine], ebx
0x1400470ab  mov     r9, rdi
0x1400470ae  call    WPP_SF_qD
0x1400470b3  mov     eax, ebx
0x1400470b5  mov     rbx, [rsp+50h+arg_10]
0x1400470bd  add     rsp, 50h
0x1400470c1  pop     r15
0x1400470c3  pop     r14
0x1400470c5  pop     r13
0x1400470c7  pop     r12
0x1400470c9  pop     rdi
0x1400470ca  pop     rsi
0x1400470cb  pop     rbp
0x1400470cc  retn
```
