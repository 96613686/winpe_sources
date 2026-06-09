# RxRefsStreamSnapshotManagement

- ea: `0x14001a834`
- end: `0x14001aa4b`
- name: `RxRefsStreamSnapshotManagement`
- size: `535`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext, PIRP Irp, struct _FCB *MrxFcb)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140045410`

## callees

- `0x140008030`
- `0x140008190`
- `0x140009b80`
- `0x140017220`
- `0x140017370`
- `0x140017a8c`
- `0x14001a834`
- `0x140057660`

## import_xrefs

- `ntoskrnl!FsRtlCheckOplock` at `0x14001a954`
- `ntoskrnl!FsRtlCheckOplock` at `0x14001a954`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x14001a9b4`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x14001a9b4`

## pseudocode

```c
__int64 __fastcall RxRefsStreamSnapshotManagement(PRX_CONTEXT RxContext, PIRP Irp, struct _FCB *MrxFcb)
{
  NTSTATUS Status; // ebx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  PFILE_OBJECT FileObject; // r15
  unsigned __int8 v9; // r14
  struct _IRP *MasterIrp; // rbx
  __int64 v11; // r8
  const CHAR *v12; // r9
  __int64 v13; // rcx
  __int64 v14; // rcx
  const CHAR *FileName; // [rsp+20h] [rbp-48h]
  ULONG FileNamea; // [rsp+20h] [rbp-48h]
  ULONG SerialNumber; // [rsp+28h] [rbp-40h]

  if ( MrxFcb->Header.NodeTypeCode != -5086 )
  {
    Status = -1073741808;
LABEL_27:
    if ( !BYTE3(RxContext->RealDevice)
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 34, &WPP_0631a9abaf7433de250bb1791161ea05_Traceguids);
    }
    return (unsigned int)Status;
  }
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  if ( CurrentStackLocation->Parameters.Create.Options < 0x18 )
  {
    Status = -1073741811;
    goto LABEL_27;
  }
  FileObject = CurrentStackLocation->FileObject;
  v9 = 0;
  MasterIrp = Irp->AssociatedIrp.MasterIrp;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    SerialNumber = *(_DWORD *)&MasterIrp->Type;
    FileName = (const CHAR *)CurrentStackLocation->FileObject;
    WPP_SF_qqD(WPP_GLOBAL_Control->AttachedDevice, 32, &WPP_0631a9abaf7433de250bb1791161ea05_Traceguids, RxContext);
  }
  if ( *(_DWORD *)&MasterIrp->Type == 1 )
    v9 = 1;
  Status = _RxAcquireFcb(MrxFcb, RxContext, (v9 ^ 1) + 1, 0, FileName, SerialNumber);
  if ( Status < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 33, &WPP_0631a9abaf7433de250bb1791161ea05_Traceguids);
    }
    if ( Status == -1073741739 )
      BYTE3(RxContext->RealDevice) = 1;
    goto LABEL_27;
  }
  Status = FsRtlCheckOplock((POPLOCK)&MrxFcb->pNetRoot, Irp, RxContext, RxUpperOplockBreakCompleteAsync, RxPrePostIrp);
  if ( !Status && v9 )
  {
    LOBYTE(v11) = 1;
    RxAcquirePagingIoResource(RxContext, MrxFcb, v11);
    if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
      McTemplateK0p_EtwWriteTransfer(v13, &CcFlushRequest, &RxContext->LowIoContext.Flags + 1, MrxFcb);
    CcCoherencyFlushAndPurgeCache(FileObject->SectionObjectPointer, 0, 0, &Irp->IoStatus, 3u);
    if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
      McTemplateK0p_EtwWriteTransfer(v14, &CcFlushCompletion, &RxContext->LowIoContext.Flags + 1, MrxFcb);
    RxReleasePagingIoResource(RxContext, MrxFcb);
    if ( Irp->IoStatus.Status < 0 )
      Status = Irp->IoStatus.Status;
  }
  _RxReleaseFcb(RxContext, (PMRX_FCB)&MrxFcb->Header, v11, v12, FileNamea);
  if ( Status < 0 )
    goto LABEL_27;
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14001a834  push    rbx
0x14001a836  push    rbp
0x14001a837  push    rsi
0x14001a838  push    rdi
0x14001a839  push    r12
0x14001a83b  push    r14
0x14001a83d  push    r15
0x14001a83f  sub     rsp, 30h
0x14001a843  mov     eax, 0EC22h
0x14001a848  lea     r12, WPP_GLOBAL_Control
0x14001a84f  mov     rsi, r8
0x14001a852  mov     rbp, rdx
0x14001a855  mov     rdi, rcx
0x14001a858  cmp     [r8], ax
0x14001a85c  jz      short loc_14001A868
0x14001a85e  mov     ebx, 0C0000010h
0x14001a863  jmp     loc_14001A9FD
0x14001a868  mov     rax, [rdx+0B8h]
0x14001a86f  cmp     dword ptr [rax+10h], 18h
0x14001a873  jnb     short loc_14001A87F
0x14001a875  mov     ebx, 0C000000Dh
0x14001a87a  jmp     loc_14001A9FD
0x14001a87f  mov     r15, [rax+30h]
0x14001a883  xor     r14b, r14b
0x14001a886  mov     rbx, [rdx+18h]
0x14001a88a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a891  cmp     rcx, r12
0x14001a894  jz      short loc_14001A8C6
0x14001a896  mov     eax, [rcx+2Ch]
0x14001a899  test    al, 10h
0x14001a89b  jz      short loc_14001A8C6
0x14001a89d  cmp     byte ptr [rcx+29h], 2
0x14001a8a1  jb      short loc_14001A8C6
0x14001a8a3  mov     eax, [rbx]
0x14001a8a5  lea     r8, WPP_0631a9abaf7433de250bb1791161ea05_Traceguids
0x14001a8ac  mov     rcx, [rcx+18h]
0x14001a8b0  mov     edx, 20h ; ' '
0x14001a8b5  mov     [rsp+68h+SerialNumber], eax; SerialNumber
0x14001a8b9  mov     r9, rdi
0x14001a8bc  mov     [rsp+68h+FileName], r15; FileName
0x14001a8c1  call    WPP_SF_qqD
0x14001a8c6  cmp     dword ptr [rbx], 1
0x14001a8c9  jnz     short loc_14001A8CE
0x14001a8cb  mov     r14b, 1
0x14001a8ce  movzx   r8d, r14b
0x14001a8d2  xor     r9d, r9d; LineNumber
0x14001a8d5  xor     r8d, 1
0x14001a8d9  mov     rdx, rdi; RxContext
0x14001a8dc  inc     r8d; Mode
0x14001a8df  mov     rcx, rsi; Fcb
0x14001a8e2  call    __RxAcquireFcb
0x14001a8e7  mov     ebx, eax
0x14001a8e9  test    eax, eax
0x14001a8eb  jns     short loc_14001A937
0x14001a8ed  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a8f4  cmp     rcx, r12
0x14001a8f7  jz      short loc_14001A922
0x14001a8f9  mov     eax, [rcx+2Ch]
0x14001a8fc  test    al, 10h
0x14001a8fe  jz      short loc_14001A922
0x14001a900  cmp     byte ptr [rcx+29h], 4
0x14001a904  jb      short loc_14001A922
0x14001a906  mov     rcx, [rcx+18h]
0x14001a90a  lea     r8, WPP_0631a9abaf7433de250bb1791161ea05_Traceguids
0x14001a911  mov     edx, 21h ; '!'
0x14001a916  mov     dword ptr [rsp+68h+FileName], ebx
0x14001a91a  mov     r9, rsi
0x14001a91d  call    WPP_SF_qD
0x14001a922  cmp     ebx, 0C0000055h
0x14001a928  jnz     loc_14001A9FD
0x14001a92e  mov     byte ptr [rdi+23h], 1
0x14001a932  jmp     loc_14001A9FD
0x14001a937  lea     rax, RxPrePostIrp
0x14001a93e  mov     r8, rdi; Context
0x14001a941  lea     rcx, [rsi+58h]; Oplock
0x14001a945  mov     [rsp+68h+FileName], rax; PostIrpRoutine
0x14001a94a  lea     r9, RxUpperOplockBreakCompleteAsync; CompletionRoutine
0x14001a951  mov     rdx, rbp; Irp
0x14001a954  call    cs:__imp_FsRtlCheckOplock
0x14001a95b  nop     dword ptr [rax+rax+00h]
0x14001a960  mov     ebx, eax
0x14001a962  test    eax, eax
0x14001a964  jnz     loc_14001A9EE
0x14001a96a  test    r14b, r14b
0x14001a96d  jz      short loc_14001A9EE
0x14001a96f  mov     r8b, 1
0x14001a972  mov     rdx, rsi
0x14001a975  mov     rcx, rdi
0x14001a978  call    RxAcquirePagingIoResource
0x14001a97d  test    byte ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4, 8
0x14001a984  lea     r14, [rdi+19Ch]
0x14001a98b  jz      short loc_14001A99F
0x14001a98d  mov     r9, rsi
0x14001a990  lea     rdx, CcFlushRequest
0x14001a997  mov     r8, r14
0x14001a99a  call    McTemplateK0p_EtwWriteTransfer
0x14001a99f  mov     rcx, [r15+28h]; SectionObjectPointer
0x14001a9a3  lea     r9, [rbp+30h]; IoStatus
0x14001a9a7  xor     r8d, r8d; Length
0x14001a9aa  mov     dword ptr [rsp+68h+FileName], 3; SerialNumber
0x14001a9b2  xor     edx, edx; FileOffset
0x14001a9b4  call    cs:__imp_CcCoherencyFlushAndPurgeCache
0x14001a9bb  nop     dword ptr [rax+rax+00h]
0x14001a9c0  test    byte ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4, 8
0x14001a9c7  jz      short loc_14001A9DB
0x14001a9c9  mov     r9, rsi
0x14001a9cc  lea     rdx, CcFlushCompletion
0x14001a9d3  mov     r8, r14
0x14001a9d6  call    McTemplateK0p_EtwWriteTransfer
0x14001a9db  mov     rdx, rsi
0x14001a9de  mov     rcx, rdi
0x14001a9e1  call    RxReleasePagingIoResource
0x14001a9e6  mov     eax, [rbp+30h]
0x14001a9e9  test    eax, eax
0x14001a9eb  cmovs   ebx, eax
0x14001a9ee  mov     rdx, rsi; MrxFcb
0x14001a9f1  mov     rcx, rdi; RxContext
0x14001a9f4  call    __RxReleaseFcb
0x14001a9f9  test    ebx, ebx
0x14001a9fb  jns     short loc_14001AA39
0x14001a9fd  cmp     byte ptr [rdi+23h], 0
0x14001aa01  jnz     short loc_14001AA39
0x14001aa03  mov     rcx, cs:WPP_GLOBAL_Control
0x14001aa0a  cmp     rcx, r12
0x14001aa0d  jz      short loc_14001AA39
0x14001aa0f  mov     edx, [rcx+2Ch]
0x14001aa12  test    dl, 1
0x14001aa15  jz      short loc_14001AA39
0x14001aa17  cmp     byte ptr [rcx+29h], 1
0x14001aa1b  jb      short loc_14001AA39
0x14001aa1d  mov     rcx, [rcx+18h]
0x14001aa21  lea     r8, WPP_0631a9abaf7433de250bb1791161ea05_Traceguids
0x14001aa28  mov     edx, 22h ; '"'
0x14001aa2d  mov     dword ptr [rsp+68h+FileName], ebx
0x14001aa31  mov     r9, rdi
0x14001aa34  call    WPP_SF_qD
0x14001aa39  mov     eax, ebx
0x14001aa3b  add     rsp, 30h
0x14001aa3f  pop     r15
0x14001aa41  pop     r14
0x14001aa43  pop     r12
0x14001aa45  pop     rdi
0x14001aa46  pop     rsi
0x14001aa47  pop     rbp
0x14001aa48  pop     rbx
0x14001aa49  retn
```
