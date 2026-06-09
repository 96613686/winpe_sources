# RxOffloadRead

- ea: `0x1400466c0`
- end: `0x140046983`
- name: `RxOffloadRead`
- size: `707`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext, PIRP Irp, struct _FCB *MrxFcb)`
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
- `0x14001b2b8`
- `0x1400466c0`
- `0x140057660`

## import_xrefs

- `ntoskrnl!FsRtlCheckOplock` at `0x14004680a`
- `ntoskrnl!FsRtlCheckOplock` at `0x14004680a`
- `ntoskrnl!IoGetRequestorProcess` at `0x140046838`
- `ntoskrnl!IoGetRequestorProcess` at `0x140046838`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x1400468da`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x1400468da`
- `ntoskrnl!FsRtlFastCheckLockForRead` at `0x140046865`
- `ntoskrnl!FsRtlFastCheckLockForRead` at `0x140046865`

## pseudocode

```c
__int64 __fastcall RxOffloadRead(PRX_CONTEXT RxContext, PIRP Irp, struct _FCB *MrxFcb)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _FILE_OBJECT *FileObject; // r15
  NTSTATUS Status; // ebx
  LARGE_INTEGER *MasterIrp; // rbp
  unsigned __int64 QuadPart; // rcx
  unsigned __int64 v11; // rdx
  NTSTATUS v12; // eax
  __int64 v13; // r8
  __int64 v14; // r8
  const CHAR *v15; // r9
  PEPROCESS RequestorProcess; // rax
  __int64 v17; // rcx
  __int64 v18; // rcx
  const CHAR *PostIrpRoutine; // [rsp+20h] [rbp-48h]
  ULONG PostIrpRoutinea; // [rsp+20h] [rbp-48h]
  ULONG ProcessId; // [rsp+28h] [rbp-40h]
  LARGE_INTEGER Length; // [rsp+78h] [rbp+10h] BYREF
  LARGE_INTEGER StartingByte; // [rsp+88h] [rbp+20h] BYREF

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  FileObject = CurrentStackLocation->FileObject;
  StartingByte.QuadPart = 0;
  Length.QuadPart = 0;
  if ( CurrentStackLocation->Parameters.Create.Options < 0x20 )
    goto LABEL_29;
  if ( MrxFcb->Header.NodeTypeCode != -5086 )
  {
    Status = -1073741808;
LABEL_30:
    if ( !BYTE3(RxContext->RealDevice)
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 16, &WPP_0631a9abaf7433de250bb1791161ea05_Traceguids);
    }
    return (unsigned int)Status;
  }
  MasterIrp = (LARGE_INTEGER *)Irp->AssociatedIrp.MasterIrp;
  QuadPart = MasterIrp[2].QuadPart;
  v11 = QuadPart + MasterIrp[3].QuadPart;
  if ( v11 < QuadPart || v11 > 0x7FFFFFFFFFFFFFFFLL )
  {
LABEL_29:
    Status = -1073741811;
    goto LABEL_30;
  }
  v12 = _RxAcquireFcb(MrxFcb, RxContext, 1u, 0, PostIrpRoutine, ProcessId);
  Status = v12;
  if ( v12 < 0 )
  {
    if ( v12 == -1073741739 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, &WPP_0631a9abaf7433de250bb1791161ea05_Traceguids);
      }
      BYTE3(RxContext->RealDevice) = 1;
    }
    goto LABEL_30;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_qqqii)(
      WPP_GLOBAL_Control->AttachedDevice,
      15,
      v13,
      RxContext,
      MrxFcb,
      FileObject,
      (LARGE_INTEGER)MasterIrp[3].QuadPart,
      (LARGE_INTEGER)MasterIrp[2].QuadPart);
  }
  Status = FsRtlCheckOplock((POPLOCK)&MrxFcb->pNetRoot, Irp, RxContext, RxUpperOplockBreakCompleteAsync, RxPrePostIrp);
  if ( !Status )
  {
    StartingByte = MasterIrp[2];
    Length = MasterIrp[3];
    RequestorProcess = IoGetRequestorProcess(Irp);
    if ( FsRtlFastCheckLockForRead(
           (PFILE_LOCK)&MrxFcb->FileLock.LockRequestsInProgress,
           &StartingByte,
           &Length,
           0,
           FileObject,
           RequestorProcess) )
    {
      if ( FileObject->SectionObjectPointer->DataSectionObject )
      {
        LOBYTE(v14) = 1;
        RxAcquirePagingIoResource(RxContext, MrxFcb, v14);
        if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
          McTemplateK0p_EtwWriteTransfer(v17, &CcFlushRequest, &RxContext->LowIoContext.Flags + 1, MrxFcb);
        CcCoherencyFlushAndPurgeCache(
          FileObject->SectionObjectPointer,
          &StartingByte,
          Length.LowPart,
          &Irp->IoStatus,
          3u);
        if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
          McTemplateK0p_EtwWriteTransfer(v18, &CcFlushCompletion, &RxContext->LowIoContext.Flags + 1, MrxFcb);
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
  _RxReleaseFcb(RxContext, (PMRX_FCB)&MrxFcb->Header, v14, v15, PostIrpRoutinea);
  if ( Status < 0 )
    goto LABEL_30;
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400466c0  mov     r11, rsp
0x1400466c3  mov     [r11+8], rbx
0x1400466c7  mov     [r11+18h], rbp
0x1400466cb  push    rsi
0x1400466cc  push    rdi
0x1400466cd  push    r13
0x1400466cf  push    r14
0x1400466d1  push    r15
0x1400466d3  sub     rsp, 40h
0x1400466d7  mov     rax, [rdx+0B8h]
0x1400466de  lea     r13, WPP_GLOBAL_Control
0x1400466e5  mov     rsi, r8
0x1400466e8  mov     r14, rdx
0x1400466eb  mov     rdi, rcx
0x1400466ee  mov     r15, [rax+30h]
0x1400466f2  mov     qword ptr [r11+20h], 0
0x1400466fa  mov     qword ptr [r11+10h], 0
0x140046702  cmp     dword ptr [rax+10h], 20h ; ' '
0x140046706  jb      loc_140046927
0x14004670c  mov     eax, 0EC22h
0x140046711  cmp     [r8], ax
0x140046715  jz      short loc_140046721
0x140046717  mov     ebx, 0C0000010h
0x14004671c  jmp     loc_14004692C
0x140046721  mov     rbp, [rdx+18h]
0x140046725  mov     rcx, [rbp+10h]
0x140046729  mov     rdx, [rbp+18h]
0x14004672d  add     rdx, rcx
0x140046730  cmp     rdx, rcx
0x140046733  jb      loc_140046927
0x140046739  mov     rax, 7FFFFFFFFFFFFFFFh
0x140046743  cmp     rdx, rax
0x140046746  ja      loc_140046927
0x14004674c  xor     r9d, r9d; LineNumber
0x14004674f  mov     rdx, rdi; RxContext
0x140046752  mov     rcx, rsi; Fcb
0x140046755  lea     r8d, [r9+1]; Mode
0x140046759  call    __RxAcquireFcb
0x14004675e  mov     ebx, eax
0x140046760  test    eax, eax
0x140046762  jns     short loc_1400467A7
0x140046764  cmp     eax, 0C0000055h
0x140046769  jnz     loc_14004692C
0x14004676f  mov     rcx, cs:WPP_GLOBAL_Control
0x140046776  cmp     rcx, r13
0x140046779  jz      short loc_14004679E
0x14004677b  mov     edx, [rcx+2Ch]
0x14004677e  test    dl, 10h
0x140046781  jz      short loc_14004679E
0x140046783  cmp     byte ptr [rcx+29h], 4
0x140046787  jb      short loc_14004679E
0x140046789  mov     rcx, [rcx+18h]
0x14004678d  lea     r8, WPP_0631a9abaf7433de250bb1791161ea05_Traceguids
0x140046794  mov     edx, 0Eh
0x140046799  call    WPP_SF_
0x14004679e  mov     byte ptr [rdi+23h], 1
0x1400467a2  jmp     loc_14004692C
0x1400467a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400467ae  cmp     rcx, r13
0x1400467b1  jz      short loc_1400467ED
0x1400467b3  mov     eax, [rcx+2Ch]
0x1400467b6  test    al, 10h
0x1400467b8  jz      short loc_1400467ED
0x1400467ba  cmp     byte ptr [rcx+29h], 2
0x1400467be  jb      short loc_1400467ED
0x1400467c0  mov     rax, [rbp+10h]
0x1400467c4  mov     edx, 0Fh
0x1400467c9  mov     rcx, [rcx+18h]
0x1400467cd  mov     r9, rdi
0x1400467d0  mov     [rsp+68h+var_30], rax
0x1400467d5  mov     rax, [rbp+18h]
0x1400467d9  mov     [rsp+68h+var_38], rax
0x1400467de  mov     [rsp+68h+ProcessId], r15
0x1400467e3  mov     [rsp+68h+PostIrpRoutine], rsi
0x1400467e8  call    WPP_SF_qqqii
0x1400467ed  lea     rax, RxPrePostIrp
0x1400467f4  mov     r8, rdi; Context
0x1400467f7  lea     rcx, [rsi+58h]; Oplock
0x1400467fb  mov     [rsp+68h+PostIrpRoutine], rax; PostIrpRoutine
0x140046800  lea     r9, RxUpperOplockBreakCompleteAsync; CompletionRoutine
0x140046807  mov     rdx, r14; Irp
0x14004680a  call    cs:__imp_FsRtlCheckOplock
0x140046811  nop     dword ptr [rax+rax+00h]
0x140046816  mov     ebx, eax
0x140046818  test    eax, eax
0x14004681a  jnz     loc_140046916
0x140046820  mov     rax, [rbp+10h]
0x140046824  mov     rcx, r14; Irp
0x140046827  mov     qword ptr [rsp+68h+StartingByte], rax
0x14004682f  mov     rax, [rbp+18h]
0x140046833  mov     qword ptr [rsp+68h+Length], rax
0x140046838  call    cs:__imp_IoGetRequestorProcess
0x14004683f  nop     dword ptr [rax+rax+00h]
0x140046844  mov     [rsp+68h+ProcessId], rax; ProcessId
0x140046849  lea     rcx, [rsi+218h]; FileLock
0x140046850  xor     r9d, r9d; Key
0x140046853  mov     [rsp+68h+PostIrpRoutine], r15; FileObject
0x140046858  lea     r8, [rsp+68h+Length]; Length
0x14004685d  lea     rdx, [rsp+68h+StartingByte]; StartingByte
0x140046865  call    cs:__imp_FsRtlFastCheckLockForRead
0x14004686c  nop     dword ptr [rax+rax+00h]
0x140046871  test    al, al
0x140046873  jnz     short loc_14004687F
0x140046875  mov     ebx, 0C0000054h
0x14004687a  jmp     loc_140046916
0x14004687f  mov     rax, [r15+28h]
0x140046883  cmp     qword ptr [rax], 0
0x140046887  jz      loc_140046916
0x14004688d  mov     r8b, 1
0x140046890  mov     rdx, rsi
0x140046893  mov     rcx, rdi
0x140046896  call    RxAcquirePagingIoResource
0x14004689b  test    byte ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4, 8
0x1400468a2  lea     rbp, [rdi+19Ch]
0x1400468a9  jz      short loc_1400468BD
0x1400468ab  mov     r9, rsi
0x1400468ae  lea     rdx, CcFlushRequest
0x1400468b5  mov     r8, rbp
0x1400468b8  call    McTemplateK0p_EtwWriteTransfer
0x1400468bd  mov     r8d, dword ptr [rsp+68h+Length]; Length
0x1400468c2  lea     r9, [r14+30h]; IoStatus
0x1400468c6  mov     rcx, [r15+28h]; SectionObjectPointer
0x1400468ca  lea     rdx, [rsp+68h+StartingByte]; FileOffset
0x1400468d2  mov     dword ptr [rsp+68h+PostIrpRoutine], 3; SerialNumber
0x1400468da  call    cs:__imp_CcCoherencyFlushAndPurgeCache
0x1400468e1  nop     dword ptr [rax+rax+00h]
0x1400468e6  test    byte ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4, 8
0x1400468ed  jz      short loc_140046901
0x1400468ef  mov     r9, rsi
0x1400468f2  lea     rdx, CcFlushCompletion
0x1400468f9  mov     r8, rbp
0x1400468fc  call    McTemplateK0p_EtwWriteTransfer
0x140046901  mov     rdx, rsi
0x140046904  mov     rcx, rdi
0x140046907  call    RxReleasePagingIoResource
0x14004690c  mov     eax, [r14+30h]
0x140046910  test    eax, eax
0x140046912  jns     short loc_140046916
0x140046914  mov     ebx, eax
0x140046916  mov     rdx, rsi; MrxFcb
0x140046919  mov     rcx, rdi; RxContext
0x14004691c  call    __RxReleaseFcb
0x140046921  test    ebx, ebx
0x140046923  jns     short loc_140046967
0x140046925  jmp     short loc_14004692C
0x140046927  mov     ebx, 0C000000Dh
0x14004692c  cmp     byte ptr [rdi+23h], 0
0x140046930  jnz     short loc_140046967
0x140046932  mov     rcx, cs:WPP_GLOBAL_Control
0x140046939  cmp     rcx, r13
0x14004693c  jz      short loc_140046967
0x14004693e  mov     eax, [rcx+2Ch]
0x140046941  test    al, 1
0x140046943  jz      short loc_140046967
0x140046945  cmp     byte ptr [rcx+29h], 1
0x140046949  jb      short loc_140046967
0x14004694b  mov     rcx, [rcx+18h]
0x14004694f  lea     r8, WPP_0631a9abaf7433de250bb1791161ea05_Traceguids
0x140046956  mov     edx, 10h
0x14004695b  mov     dword ptr [rsp+68h+PostIrpRoutine], ebx
0x14004695f  mov     r9, rdi
0x140046962  call    WPP_SF_qD
0x140046967  lea     r11, [rsp+68h+var_28]
0x14004696c  mov     eax, ebx
0x14004696e  mov     rbx, [r11+30h]
0x140046972  mov     rbp, [r11+40h]
0x140046976  mov     rsp, r11
0x140046979  pop     r15
0x14004697b  pop     r14
0x14004697d  pop     r13
0x14004697f  pop     rdi
0x140046980  pop     rsi
0x140046981  retn
```
