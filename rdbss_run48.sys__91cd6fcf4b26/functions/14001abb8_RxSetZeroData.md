# RxSetZeroData

- ea: `0x14001abb8`
- end: `0x14001af3a`
- name: `RxSetZeroData`
- size: `898`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext, PIRP Irp, PMRX_FCB MrxFcb)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140045410`

## callees

- `0x140008030`
- `0x140008190`
- `0x140009b80`
- `0x140017220`
- `0x140017280`
- `0x140017370`
- `0x14001abb8`
- `0x14001b230`
- `0x140057660`

## import_xrefs

- `ntoskrnl!FsRtlCheckOplock` at `0x14001add8`
- `ntoskrnl!FsRtlCheckOplock` at `0x14001add8`
- `ntoskrnl!IoGetRequestorProcess` at `0x14001adf1`
- `ntoskrnl!IoGetRequestorProcess` at `0x14001adf1`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x14001ae90`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x14001ae90`
- `ntoskrnl!MmIsFileSectionActive` at `0x14001ad9e`
- `ntoskrnl!MmIsFileSectionActive` at `0x14001ad9e`
- `ntoskrnl!FsRtlFastCheckLockForWrite` at `0x14001ae1c`
- `ntoskrnl!FsRtlFastCheckLockForWrite` at `0x14001ae1c`

## pseudocode

```c
__int64 __fastcall RxSetZeroData(PRX_CONTEXT RxContext, PIRP Irp, struct _FCB *MrxFcb)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  PSECTION_OBJECT_POINTERS *FileObject; // rbp
  NTSTATUS Status; // ebx
  LARGE_INTEGER *MasterIrp; // r14
  __int64 QuadPart; // rcx
  __int64 v11; // rax
  PVOID DataSectionObject; // r15
  NTSTATUS v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  const CHAR *v16; // r9
  NTSTATUS v17; // eax
  __int64 p_DriverObject; // rcx
  __int64 v19; // r8
  const CHAR *v20; // r9
  PEPROCESS RequestorProcess; // rax
  __int64 v22; // rcx
  __int64 v23; // rcx
  const CHAR *PostIrpRoutine; // [rsp+20h] [rbp-48h]
  ULONG PostIrpRoutinea; // [rsp+20h] [rbp-48h]
  PCSTR PostIrpRoutineb; // [rsp+20h] [rbp-48h]
  ULONG ProcessId; // [rsp+28h] [rbp-40h]
  ULONG ProcessIda; // [rsp+28h] [rbp-40h]
  int v30; // [rsp+78h] [rbp+10h] BYREF
  LARGE_INTEGER Length; // [rsp+88h] [rbp+20h] BYREF

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  FileObject = (PSECTION_OBJECT_POINTERS *)CurrentStackLocation->FileObject;
  Length.QuadPart = 0;
  if ( CurrentStackLocation->Parameters.Create.Options < 0x10
    || (MasterIrp = (LARGE_INTEGER *)Irp->AssociatedIrp.MasterIrp,
        QuadPart = MasterIrp->QuadPart,
        MasterIrp->QuadPart < 0)
    || (v11 = MasterIrp[1].QuadPart, v11 < 0)
    || QuadPart > v11
    || !QuadPart && !v11 )
  {
    Status = -1073741811;
LABEL_43:
    if ( !BYTE3(RxContext->RealDevice)
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 13, &WPP_0631a9abaf7433de250bb1791161ea05_Traceguids);
    }
    return (unsigned int)Status;
  }
  Length.QuadPart = v11 - QuadPart;
  if ( MrxFcb->Header.NodeTypeCode != -5086 )
  {
    Status = -1073741808;
    goto LABEL_43;
  }
  DataSectionObject = FileObject[5]->DataSectionObject;
  v13 = _RxAcquireFcb(MrxFcb, RxContext, 2 - (DataSectionObject != 0), 0, PostIrpRoutine, ProcessId);
  Status = v13;
  if ( v13 < 0 )
  {
    if ( v13 == -1073741739 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, &WPP_0631a9abaf7433de250bb1791161ea05_Traceguids);
      }
      BYTE3(RxContext->RealDevice) = 1;
    }
    goto LABEL_43;
  }
  if ( !DataSectionObject )
  {
    if ( FileObject[5]->DataSectionObject )
    {
      _RxReleaseFcb(RxContext, (PMRX_FCB)&MrxFcb->Header, v15, v16, PostIrpRoutinea);
      v17 = _RxAcquireFcb(MrxFcb, RxContext, 1u, 0, PostIrpRoutineb, ProcessIda);
      Status = v17;
      if ( v17 < 0 )
      {
        if ( v17 == -1073741739 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, &WPP_0631a9abaf7433de250bb1791161ea05_Traceguids);
          }
          BYTE3(RxContext->RealDevice) = 1;
        }
        goto LABEL_43;
      }
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    PostIrpRoutinea = (unsigned int)MrxFcb;
    WPP_SF_qqqLL(WPP_GLOBAL_Control->AttachedDevice, v14, v15, RxContext);
  }
  p_DriverObject = (__int64)&MrxFcb->RxDeviceObject->DeviceObject.DriverObject;
  v30 = 0;
  MmIsFileSectionActive(p_DriverObject, 7, &v30);
  if ( v30 )
  {
    Status = -1073741245;
  }
  else
  {
    Status = FsRtlCheckOplock((POPLOCK)&MrxFcb->pNetRoot, Irp, RxContext, RxUpperOplockBreakCompleteAsync, RxPrePostIrp);
    if ( !Status )
    {
      RequestorProcess = IoGetRequestorProcess(Irp);
      if ( FsRtlFastCheckLockForWrite(
             (PFILE_LOCK)&MrxFcb->FileLock.LockRequestsInProgress,
             MasterIrp,
             &Length,
             0,
             FileObject,
             RequestorProcess) )
      {
        if ( FileObject[5]->DataSectionObject )
        {
          LOBYTE(v19) = 1;
          RxAcquirePagingIoResource(RxContext, MrxFcb, v19);
          if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
            McTemplateK0p_EtwWriteTransfer(v22, &CcFlushRequest, &RxContext->LowIoContext.Flags + 1, MrxFcb);
          CcCoherencyFlushAndPurgeCache(FileObject[5], MasterIrp, Length.LowPart, &Irp->IoStatus, 0);
          if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
            McTemplateK0p_EtwWriteTransfer(v23, &CcFlushCompletion, &RxContext->LowIoContext.Flags + 1, MrxFcb);
          RxReleasePagingIoResource(RxContext, MrxFcb);
          if ( Irp->IoStatus.Status < 0 )
            Status = Irp->IoStatus.Status;
        }
      }
      else
      {
        Status = -1073741740;
      }
    }
  }
  _RxReleaseFcb(RxContext, (PMRX_FCB)&MrxFcb->Header, v19, v20, PostIrpRoutinea);
  if ( Status < 0 )
    goto LABEL_43;
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14001abb8  mov     r11, rsp
0x14001abbb  mov     [r11+8], rbx
0x14001abbf  mov     [r11+18h], rbp
0x14001abc3  push    rsi
0x14001abc4  push    rdi
0x14001abc5  push    r12
0x14001abc7  push    r14
0x14001abc9  push    r15
0x14001abcb  sub     rsp, 40h
0x14001abcf  mov     rax, [rdx+0B8h]
0x14001abd6  mov     r12, rdx
0x14001abd9  mov     rsi, r8
0x14001abdc  lea     rdx, WPP_GLOBAL_Control
0x14001abe3  mov     rdi, rcx
0x14001abe6  mov     rbp, [rax+30h]
0x14001abea  mov     qword ptr [r11+20h], 0
0x14001abf2  cmp     dword ptr [rax+10h], 10h
0x14001abf6  jnb     short loc_14001AC02
0x14001abf8  mov     ebx, 0C000000Dh
0x14001abfd  jmp     loc_14001AEE3
0x14001ac02  mov     r14, [r12+18h]
0x14001ac07  mov     rcx, [r14]
0x14001ac0a  test    rcx, rcx
0x14001ac0d  js      short loc_14001ABF8
0x14001ac0f  mov     rax, [r14+8]
0x14001ac13  test    rax, rax
0x14001ac16  js      short loc_14001ABF8
0x14001ac18  cmp     rcx, rax
0x14001ac1b  jg      short loc_14001ABF8
0x14001ac1d  test    rcx, rcx
0x14001ac20  jnz     short loc_14001AC27
0x14001ac22  test    rax, rax
0x14001ac25  jz      short loc_14001ABF8
0x14001ac27  sub     rax, rcx
0x14001ac2a  mov     qword ptr [rsp+68h+Length], rax
0x14001ac32  mov     eax, 0EC22h
0x14001ac37  cmp     [r8], ax
0x14001ac3b  jz      short loc_14001AC47
0x14001ac3d  mov     ebx, 0C0000010h
0x14001ac42  jmp     loc_14001AEE3
0x14001ac47  mov     rax, [rbp+28h]
0x14001ac4b  mov     rdx, rdi; RxContext
0x14001ac4e  mov     rcx, rsi; Fcb
0x14001ac51  mov     r15, [rax]
0x14001ac54  mov     rax, r15
0x14001ac57  neg     rax
0x14001ac5a  sbb     r8d, r8d
0x14001ac5d  xor     r9d, r9d; LineNumber
0x14001ac60  add     r8d, 2; Mode
0x14001ac64  call    __RxAcquireFcb
0x14001ac69  mov     ebx, eax
0x14001ac6b  test    eax, eax
0x14001ac6d  jns     short loc_14001ACB8
0x14001ac6f  cmp     eax, 0C0000055h
0x14001ac74  jnz     loc_14001AEDC
0x14001ac7a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ac81  lea     rax, WPP_GLOBAL_Control
0x14001ac88  cmp     rcx, rax
0x14001ac8b  jz      short loc_14001ACAF
0x14001ac8d  mov     eax, [rcx+2Ch]
0x14001ac90  test    al, 10h
0x14001ac92  jz      short loc_14001ACAF
0x14001ac94  cmp     byte ptr [rcx+29h], 4
0x14001ac98  jb      short loc_14001ACAF
0x14001ac9a  mov     rcx, [rcx+18h]
0x14001ac9e  lea     r8, WPP_0631a9abaf7433de250bb1791161ea05_Traceguids
0x14001aca5  mov     edx, 0Ah
0x14001acaa  call    WPP_SF_
0x14001acaf  mov     byte ptr [rdi+23h], 1
0x14001acb3  jmp     loc_14001AEDC
0x14001acb8  test    r15, r15
0x14001acbb  jnz     short loc_14001AD39
0x14001acbd  mov     rax, [rbp+28h]
0x14001acc1  cmp     [rax], r15
0x14001acc4  jz      short loc_14001AD39
0x14001acc6  mov     rdx, rsi; MrxFcb
0x14001acc9  mov     rcx, rdi; RxContext
0x14001accc  call    __RxReleaseFcb
0x14001acd1  xor     r9d, r9d; LineNumber
0x14001acd4  lea     r8d, [r15+1]; Mode
0x14001acd8  mov     rdx, rdi; RxContext
0x14001acdb  mov     rcx, rsi; Fcb
0x14001acde  call    __RxAcquireFcb
0x14001ace3  mov     ebx, eax
0x14001ace5  test    eax, eax
0x14001ace7  jns     short loc_14001AD39
0x14001ace9  cmp     eax, 0C0000055h
0x14001acee  jnz     loc_14001AEDC
0x14001acf4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001acfb  lea     rdx, WPP_GLOBAL_Control
0x14001ad02  cmp     rcx, rdx
0x14001ad05  jz      short loc_14001AD30
0x14001ad07  mov     edx, [rcx+2Ch]
0x14001ad0a  test    dl, 10h
0x14001ad0d  jz      short loc_14001AD29
0x14001ad0f  cmp     byte ptr [rcx+29h], 4
0x14001ad13  jb      short loc_14001AD29
0x14001ad15  mov     rcx, [rcx+18h]
0x14001ad19  lea     edx, [r15+0Bh]
0x14001ad1d  lea     r8, WPP_0631a9abaf7433de250bb1791161ea05_Traceguids
0x14001ad24  call    WPP_SF_
0x14001ad29  lea     rdx, WPP_GLOBAL_Control
0x14001ad30  mov     byte ptr [rdi+23h], 1
0x14001ad34  jmp     loc_14001AEE3
0x14001ad39  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ad40  lea     rax, WPP_GLOBAL_Control
0x14001ad47  cmp     rcx, rax
0x14001ad4a  jz      short loc_14001AD81
0x14001ad4c  mov     eax, [rcx+2Ch]
0x14001ad4f  test    al, 10h
0x14001ad51  jz      short loc_14001AD81
0x14001ad53  cmp     byte ptr [rcx+29h], 2
0x14001ad57  jb      short loc_14001AD81
0x14001ad59  mov     eax, [r14]
0x14001ad5c  mov     r9, rdi
0x14001ad5f  mov     rcx, [rcx+18h]
0x14001ad63  mov     [rsp+68h+var_30], eax
0x14001ad67  mov     eax, dword ptr [rsp+68h+Length]
0x14001ad6e  mov     [rsp+68h+var_38], eax
0x14001ad72  mov     [rsp+68h+ProcessId], rbp
0x14001ad77  mov     [rsp+68h+PostIrpRoutine], rsi
0x14001ad7c  call    WPP_SF_qqqLL
0x14001ad81  mov     rcx, [rsi+130h]
0x14001ad88  lea     r8, [rsp+68h+arg_8]
0x14001ad8d  add     rcx, 8
0x14001ad91  mov     [rsp+68h+arg_8], 0
0x14001ad99  mov     edx, 7
0x14001ad9e  call    cs:__imp_MmIsFileSectionActive
0x14001ada5  nop     dword ptr [rax+rax+00h]
0x14001adaa  cmp     [rsp+68h+arg_8], 0
0x14001adaf  jz      short loc_14001ADBB
0x14001adb1  mov     ebx, 0C0000243h
0x14001adb6  jmp     loc_14001AECD
0x14001adbb  lea     rax, RxPrePostIrp
0x14001adc2  mov     r8, rdi; Context
0x14001adc5  lea     rcx, [rsi+58h]; Oplock
0x14001adc9  mov     [rsp+68h+PostIrpRoutine], rax; PostIrpRoutine
0x14001adce  lea     r9, RxUpperOplockBreakCompleteAsync; CompletionRoutine
0x14001add5  mov     rdx, r12; Irp
0x14001add8  call    cs:__imp_FsRtlCheckOplock
0x14001addf  nop     dword ptr [rax+rax+00h]
0x14001ade4  mov     ebx, eax
0x14001ade6  test    eax, eax
0x14001ade8  jnz     loc_14001AECD
0x14001adee  mov     rcx, r12; Irp
0x14001adf1  call    cs:__imp_IoGetRequestorProcess
0x14001adf8  nop     dword ptr [rax+rax+00h]
0x14001adfd  mov     [rsp+68h+ProcessId], rax; ProcessId
0x14001ae02  lea     rcx, [rsi+218h]; FileLock
0x14001ae09  xor     r9d, r9d; Key
0x14001ae0c  mov     [rsp+68h+PostIrpRoutine], rbp; FileObject
0x14001ae11  lea     r8, [rsp+68h+Length]; Length
0x14001ae19  mov     rdx, r14; StartingByte
0x14001ae1c  call    cs:__imp_FsRtlFastCheckLockForWrite
0x14001ae23  nop     dword ptr [rax+rax+00h]
0x14001ae28  test    al, al
0x14001ae2a  jnz     short loc_14001AE36
0x14001ae2c  mov     ebx, 0C0000054h
0x14001ae31  jmp     loc_14001AECD
0x14001ae36  mov     rax, [rbp+28h]
0x14001ae3a  cmp     qword ptr [rax], 0
0x14001ae3e  jz      loc_14001AECD
0x14001ae44  mov     r8b, 1
0x14001ae47  mov     rdx, rsi
0x14001ae4a  mov     rcx, rdi
0x14001ae4d  call    RxAcquirePagingIoResource
0x14001ae52  test    byte ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4, 8
0x14001ae59  lea     r15, [rdi+19Ch]
0x14001ae60  jz      short loc_14001AE74
0x14001ae62  mov     r9, rsi
0x14001ae65  lea     rdx, CcFlushRequest
0x14001ae6c  mov     r8, r15
0x14001ae6f  call    McTemplateK0p_EtwWriteTransfer
0x14001ae74  mov     r8d, dword ptr [rsp+68h+Length]; Length
0x14001ae7c  lea     r9, [r12+30h]; IoStatus
0x14001ae81  mov     rcx, [rbp+28h]; SectionObjectPointer
0x14001ae85  mov     rdx, r14; FileOffset
0x14001ae88  mov     dword ptr [rsp+68h+PostIrpRoutine], 0; SerialNumber
0x14001ae90  call    cs:__imp_CcCoherencyFlushAndPurgeCache
0x14001ae97  nop     dword ptr [rax+rax+00h]
0x14001ae9c  test    byte ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4, 8
0x14001aea3  jz      short loc_14001AEB7
0x14001aea5  mov     r9, rsi
0x14001aea8  lea     rdx, CcFlushCompletion
0x14001aeaf  mov     r8, r15
0x14001aeb2  call    McTemplateK0p_EtwWriteTransfer
0x14001aeb7  mov     rdx, rsi
0x14001aeba  mov     rcx, rdi
0x14001aebd  call    RxReleasePagingIoResource
0x14001aec2  mov     eax, [r12+30h]
0x14001aec7  test    eax, eax
0x14001aec9  jns     short loc_14001AECD
0x14001aecb  mov     ebx, eax
0x14001aecd  mov     rdx, rsi; MrxFcb
0x14001aed0  mov     rcx, rdi; RxContext
0x14001aed3  call    __RxReleaseFcb
0x14001aed8  test    ebx, ebx
0x14001aeda  jns     short loc_14001AF1E
0x14001aedc  lea     rdx, WPP_GLOBAL_Control
0x14001aee3  cmp     byte ptr [rdi+23h], 0
0x14001aee7  jnz     short loc_14001AF1E
0x14001aee9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001aef0  cmp     rcx, rdx
0x14001aef3  jz      short loc_14001AF1E
0x14001aef5  mov     eax, [rcx+2Ch]
0x14001aef8  test    al, 1
0x14001aefa  jz      short loc_14001AF1E
0x14001aefc  cmp     byte ptr [rcx+29h], 1
0x14001af00  jb      short loc_14001AF1E
0x14001af02  mov     rcx, [rcx+18h]
0x14001af06  lea     r8, WPP_0631a9abaf7433de250bb1791161ea05_Traceguids
0x14001af0d  mov     edx, 0Dh
0x14001af12  mov     dword ptr [rsp+68h+PostIrpRoutine], ebx
0x14001af16  mov     r9, rdi
0x14001af19  call    WPP_SF_qD
0x14001af1e  lea     r11, [rsp+68h+var_28]
0x14001af23  mov     eax, ebx
0x14001af25  mov     rbx, [r11+30h]
0x14001af29  mov     rbp, [r11+40h]
0x14001af2d  mov     rsp, r11
0x14001af30  pop     r15
0x14001af32  pop     r14
0x14001af34  pop     r12
0x14001af36  pop     rdi
0x14001af37  pop     rsi
0x14001af38  retn
```
