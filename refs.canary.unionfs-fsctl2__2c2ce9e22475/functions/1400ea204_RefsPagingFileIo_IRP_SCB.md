# RefsPagingFileIo(_IRP *,_SCB *)

- ea: `0x1400ea204`
- end: `0x1400eac54`
- name: `?RefsPagingFileIo@@YAXPEAU_IRP@@PEAU_SCB@@@Z`
- size: `2640`
- prototype: `void __fastcall(PIRP Irp, struct _SCB *)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14003a850`
- `0x1400a4ff0`

## callees

- `0x140041b40`
- `0x14008e5d0`
- `0x1400a6128`
- `0x1400b2794`
- `0x1400e1534`
- `0x1400e2e8c`
- `0x1400ea204`
- `0x1400eac5c`
- `0x1400ef9b0`
- `0x1400efad0`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x1400eabe5`
- `ntoskrnl!KeBugCheckEx` at `0x1400eac47`
- `ntoskrnl!KeBugCheckEx` at `0x1400eabe5`
- `ntoskrnl!KeBugCheckEx` at `0x1400eac47`
- `ntoskrnl!IofCompleteRequest` at `0x1400ea67a`
- `ntoskrnl!IofCompleteRequest` at `0x1400ea9f3`
- `ntoskrnl!IofCompleteRequest` at `0x1400ea67a`
- `ntoskrnl!IofCompleteRequest` at `0x1400ea9f3`
- `ntoskrnl!IoFreeIrp` at `0x1400eaabf`
- `ntoskrnl!IoFreeIrp` at `0x1401ec778`
- `ntoskrnl!IoFreeIrp` at `0x1400eaabf`
- `ntoskrnl!IoFreeIrp` at `0x1401ec778`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400ea838`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400ea838`
- `ntoskrnl!IoAllocateMdl` at `0x1400ea4cc`
- `ntoskrnl!IoAllocateMdl` at `0x1400ea7ec`
- `ntoskrnl!IoAllocateMdl` at `0x1400ea812`
- `ntoskrnl!IoAllocateMdl` at `0x1400ea4cc`
- `ntoskrnl!IoAllocateMdl` at `0x1400ea7ec`
- `ntoskrnl!IoAllocateMdl` at `0x1400ea812`
- `ntoskrnl!IoFreeMdl` at `0x1400ea61e`
- `ntoskrnl!IoFreeMdl` at `0x1400eaaa8`
- `ntoskrnl!IoFreeMdl` at `0x1401ec761`
- `ntoskrnl!IoFreeMdl` at `0x1400ea61e`
- `ntoskrnl!IoFreeMdl` at `0x1400eaaa8`
- `ntoskrnl!IoFreeMdl` at `0x1401ec761`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400ea4e7`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400ea800`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400ea4e7`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400ea800`
- `ntoskrnl!IoMakeAssociatedIrpEx` at `0x1400ea77c`
- `ntoskrnl!IoMakeAssociatedIrpEx` at `0x1400ea77c`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400ea60a`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400ea9c5`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400ea60a`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400ea9c5`
- `ntoskrnl!KeInitializeEvent` at `0x1400ea44f`
- `ntoskrnl!KeInitializeEvent` at `0x1400ea44f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ea62f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ea647`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400eaae2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ec79b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ea62f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ea647`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400eaae2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ec79b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400ea3f1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400ea3f1`

## pseudocode

```c
void __fastcall RefsPagingFileIo(PIRP Irp, struct _SCB *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  ULONG_PTR Length; // r14
  __int64 QuadPart; // r13
  char v7; // cl
  ULONG_PTR v8; // rsi
  __int64 v9; // r8
  char *v10; // rsi
  char *PoolWithTag; // rax
  __int64 v12; // r8
  unsigned int v13; // r15d
  int v14; // r9d
  __int64 v15; // r8
  unsigned int v16; // r12d
  ULONG_PTR v17; // rcx
  signed __int64 v18; // rdx
  struct _MDL *v19; // r15
  struct _MDL *v20; // rax
  ULONG_PTR v21; // rax
  char v22; // dl
  struct _IO_STACK_LOCATION *v23; // rcx
  int (*v24)(struct _DEVICE_OBJECT *, struct _IRP *, void *); // rax
  struct _IO_STACK_LOCATION *v25; // rdx
  struct _MDL *v26; // r14
  unsigned int v27; // r9d
  struct _IO_STACK_LOCATION *v28; // rax
  struct _IO_STACK_LOCATION *v29; // rax
  ULONG v30; // r12d
  IRP *AssociatedIrp; // rdx
  struct _LIST_ENTRY *v32; // rcx
  struct _MDL *Mdl; // rax
  struct _MDL *v34; // rdx
  ULONG_PTR v35; // r8
  ULONG_PTR v36; // r9
  struct _IO_STACK_LOCATION *v37; // rdx
  struct _IO_STACK_LOCATION *v38; // rax
  struct _IO_STACK_LOCATION *v39; // rdx
  ULONG_PTR v40; // r12
  __int64 v41; // rdx
  __int64 v42; // rax
  __int64 v43; // rdx
  IRP *v44; // rbx
  struct _MDL *v45; // rcx
  CmsStream *v46; // rdx
  PIRP Irpa; // [rsp+20h] [rbp-108h]
  unsigned __int64 v48; // [rsp+30h] [rbp-F8h]
  __int128 v49; // [rsp+40h] [rbp-E8h] BYREF
  unsigned int v50; // [rsp+50h] [rbp-D8h]
  LONG v51; // [rsp+54h] [rbp-D4h]
  ULONG_PTR v52; // [rsp+58h] [rbp-D0h]
  struct _MDL *MdlAddress; // [rsp+60h] [rbp-C8h]
  __int64 v54; // [rsp+68h] [rbp-C0h]
  ULONG_PTR BugCheckParameter2; // [rsp+70h] [rbp-B8h]
  __int64 v56; // [rsp+78h] [rbp-B0h] BYREF
  __int64 v57; // [rsp+80h] [rbp-A8h]
  __int64 v58; // [rsp+88h] [rbp-A0h] BYREF
  __int64 v59; // [rsp+90h] [rbp-98h]
  __int64 v60; // [rsp+98h] [rbp-90h]
  __int128 v61; // [rsp+A0h] [rbp-88h]
  _BYTE Event[32]; // [rsp+B0h] [rbp-78h] BYREF
  ULONG_PTR v63; // [rsp+D0h] [rbp-58h]
  __int128 v64; // [rsp+E0h] [rbp-48h]
  UCHAR MajorFunction; // [rsp+130h] [rbp+8h]
  char v66; // [rsp+138h] [rbp+10h]
  IRP *v67; // [rsp+138h] [rbp+10h]
  __int64 v68; // [rsp+140h] [rbp+18h]
  __int64 v69; // [rsp+148h] [rbp+20h]
  __int64 v70; // [rsp+148h] [rbp+20h]

  v56 = 0;
  v57 = 0;
  v68 = *((_QWORD *)a2 + 18);
  v49 = 0;
  v58 = 0;
  memset(Event, 0, sizeof(Event));
  MdlAddress = Irp->MdlAddress;
  MajorFunction = Irp->Tail.Overlay.CurrentStackLocation->MajorFunction;
  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v68 + 208) + 16LL) + 48LL) &= ~2u;
  if ( (*(_DWORD *)(*((_QWORD *)a2 + 18) + 28LL) & 2) != 0 )
    RefsInsertDebugInfoIrpImplementation(0, Irp, 0, *((struct _FCB **)a2 + 17), 0, 0x72657355u, v48);
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  BugCheckParameter2 = (ULONG_PTR)CurrentStackLocation;
  Length = CurrentStackLocation->Parameters.Read.Length;
  if ( !(_DWORD)Length )
  {
    CurrentStackLocation->Control |= 1u;
    RefsCompleteRequest(0, Irp, 0);
    return;
  }
  QuadPart = CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart;
  *(_QWORD *)&v61 = *(unsigned int *)(v68 + 544);
  v7 = *(_BYTE *)(v68 + 552);
  v54 = (__int64)(QuadPart + Length + v61) >> v7;
  v8 = QuadPart >> v7;
  v52 = QuadPart >> v7;
  v59 = QuadPart >> v7;
  v60 = v54 - (QuadPart >> v7);
  if ( (int)MsLookupAllocationCoalesce(0, *((CmsStream **)a2 + 54), (__int64)&v56, (__int64)&v58) < 0
    || (v9 = v56, v69 = v56, v56 == -1) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_99ddc213b05f39bbd3789163ea155869_Traceguids);
    }
    KeBugCheckEx(0x149u, 0xC09C4u, v8, *((_QWORD *)a2 + 3), *((_QWORD *)a2 + 4));
  }
  v10 = 0;
  v59 = 0;
  v66 = *(_BYTE *)(v68 + 552);
  Irp->IoStatus.Status = 0;
  Irp->IoStatus.Information = Length;
  if ( (*((_WORD *)a2 + 128) & 0x4000) != 0 && *((_QWORD *)a2 + 36) && *((int *)a2 + 38) >= 0 )
  {
    if ( MajorFunction == 4 )
    {
      PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)512, Length, 0x44466552u);
      v10 = PoolWithTag;
      v59 = (__int64)PoolWithTag;
      v12 = QuadPart;
      if ( !PoolWithTag )
      {
LABEL_13:
        RefsPagingFileIoWithNoAllocation(Irp, a2, v12, Length);
        return;
      }
      RefsEncryptPagingFileBuffer(a2, Irp, QuadPart, 0, Length, PoolWithTag, 0);
    }
    KeInitializeEvent((PRKEVENT)Event, SynchronizationEvent, 0);
    v9 = v69;
  }
  v13 = 0;
  v14 = v61 & QuadPart;
  v15 = ((unsigned int)v61 & (unsigned int)QuadPart) + (v9 << v66);
  v70 = v15;
  v16 = v57;
  v17 = v52;
  v18 = v54;
  if ( (__int64)(v52 + (unsigned int)v57) < v54 )
  {
    *((_QWORD *)&v49 + 1) = &v49;
    *(_QWORD *)&v49 = &v49;
    v51 = 0;
    if ( (*((_WORD *)a2 + 128) & 0x4000) != 0 && *((_QWORD *)a2 + 36) && *((int *)a2 + 38) >= 0 )
    {
      Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
      v28 = Irp->Tail.Overlay.CurrentStackLocation;
      *(_OWORD *)&v28[-1].MajorFunction = *(_OWORD *)&v28->MajorFunction;
      *(_OWORD *)&v28[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v28->Parameters.NotifyDirectoryEx.CompletionFilter;
      *(_OWORD *)(&v28[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v28->Parameters.SetQuota + 6);
      v28[-1].FileObject = v28->FileObject;
      v28[-1].Control = 0;
      v29 = Irp->Tail.Overlay.CurrentStackLocation;
      v29[-1].CompletionRoutine = RefsVerifyReadCompletionRoutine;
      v15 = (__int64)Event;
      v29[-1].Context = Event;
      v29[-1].Control = 0;
      v29[-1].Control = 64;
      v29[-1].Control = -64;
      v29[-1].Control = -32;
      --Irp->CurrentLocation;
      --Irp->Tail.Overlay.CurrentStackLocation;
    }
    while ( 1 )
    {
      BugCheckParameter2 = v17 + v16;
      v30 = (__int64)BugCheckParameter2 < v18 ? (v16 << *(_DWORD *)(v68 + 552)) - v14 : Length - v13;
      LOBYTE(v15) = *(_BYTE *)(*(_QWORD *)(v68 + 192) + 76LL) + 1;
      AssociatedIrp = (IRP *)IoMakeAssociatedIrpEx(Irp, Irp->Tail.Overlay.CurrentStackLocation->DeviceObject, v15);
      v67 = AssociatedIrp;
      if ( !AssociatedIrp )
        break;
      v32 = (struct _LIST_ENTRY *)*((_QWORD *)&v49 + 1);
      if ( **((__int128 ***)&v49 + 1) != &v49 )
LABEL_80:
        __fastfail(3u);
      AssociatedIrp->Tail.Overlay.ListEntry.Flink = (struct _LIST_ENTRY *)&v49;
      AssociatedIrp->Tail.Overlay.ListEntry.Blink = v32;
      v32->Flink = &AssociatedIrp->Tail.Overlay.ListEntry;
      *((_QWORD *)&v49 + 1) = &AssociatedIrp->Tail.Overlay.ListEntry;
      Irpa = AssociatedIrp;
      if ( v10 )
      {
        Mdl = IoAllocateMdl(&v10[v13], v30, 0, 0, Irpa);
        if ( !Mdl )
          break;
        MmBuildMdlForNonPagedPool(Mdl);
      }
      else
      {
        v34 = IoAllocateMdl((char *)Irp->UserBuffer + v13, v30, 0, 0, Irpa);
        if ( !v34 )
          break;
        IoBuildPartialMdl(Irp->MdlAddress, v34, (char *)Irp->UserBuffer + v13, v30);
      }
      ++v51;
      v35 = v52;
      v36 = v52 << *(_BYTE *)(v68 + 552);
      --v67->CurrentLocation;
      v37 = --v67->Tail.Overlay.CurrentStackLocation;
      v37->MajorFunction = Irp->Tail.Overlay.CurrentStackLocation->MajorFunction;
      v37->FileObject = Irp->Tail.Overlay.CurrentStackLocation->FileObject;
      v37->DeviceObject = Irp->Tail.Overlay.CurrentStackLocation->DeviceObject;
      v37->Parameters.Read.Length = v30;
      v37->Parameters.Read.ByteOffset.QuadPart = v70;
      v37->Parameters.Create.Options = v35 << *(_BYTE *)(v68 + 552);
      v38 = v67->Tail.Overlay.CurrentStackLocation;
      v38[-1].CompletionRoutine = RefsPagingFileCompletionRoutine;
      v38[-1].Context = (PVOID)1;
      v38[-1].Control = 0;
      v38[-1].Control = 64;
      v38[-1].Control = -64;
      v38[-1].Control = -32;
      v39 = v67->Tail.Overlay.CurrentStackLocation;
      v39[-1].MajorFunction = Irp->Tail.Overlay.CurrentStackLocation->MajorFunction;
      v39[-1].Parameters.Read.Length = v30;
      v39[-1].Parameters.Read.ByteOffset.QuadPart = v70;
      v39[-1].Flags |= 2u;
      LODWORD(Irpa) = 0;
      LOBYTE(v39) = v39[-1].MajorFunction;
      RefsPrepareIrpForEncryptionOffload(v67, v39, a2, v36, 0);
      v13 += v30;
      v50 = v13;
      v40 = BugCheckParameter2;
      v52 = BugCheckParameter2;
      v63 = BugCheckParameter2;
      if ( v13 == (_DWORD)Length )
        goto LABEL_50;
      *(_QWORD *)&v61 = BugCheckParameter2;
      *((_QWORD *)&v61 + 1) = v54 - BugCheckParameter2;
      v46 = (CmsStream *)*((_QWORD *)a2 + 54);
      v64 = v61;
      if ( (int)MsLookupAllocationCoalesce(0, v46, (__int64)&v56, (__int64)&v58) < 0 || v56 == -1 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_99ddc213b05f39bbd3789163ea155869_Traceguids);
        }
        KeBugCheckEx(0x149u, 0xC0B77u, v40, *((_QWORD *)a2 + 3), *((_QWORD *)a2 + 4));
      }
      v15 = v56 << *(_BYTE *)(v68 + 552);
      v70 = v15;
      v16 = v57;
      v17 = v52;
      v18 = v54;
      v14 = 0;
    }
    v13 = 0;
    v50 = 0;
LABEL_50:
    if ( v13 == (_DWORD)Length )
    {
      Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
      Irp->AssociatedIrp.IrpCount = v51;
      while ( 1 )
      {
        v41 = v49;
        if ( (__int128 *)v49 == &v49 )
          break;
        if ( *(__int128 **)(v49 + 8) != &v49 )
          goto LABEL_80;
        v42 = *(_QWORD *)v49;
        if ( *(_QWORD *)(*(_QWORD *)v49 + 8LL) != (_QWORD)v49 )
          goto LABEL_80;
        *(_QWORD *)&v49 = *(_QWORD *)v49;
        *(_QWORD *)(v42 + 8) = &v49;
        RefsCallStorageDriver(*(PDEVICE_OBJECT *)(v68 + 192), (PIRP)(v41 - 168), RefsReserveStackStorage, 0);
      }
      if ( _bittest16((const signed __int16 *)a2 + 128, 0xEu) && *((_QWORD *)a2 + 36) && *((int *)a2 + 38) >= 0 )
      {
        KeWaitForSingleObject(Event, Executive, 0, 0, 0);
        if ( MajorFunction != 4 )
          RefsDecryptPagingFileBuffer(a2, MdlAddress, QuadPart, Length);
        IofCompleteRequest(Irp, 1);
      }
    }
    else
    {
      RefsPagingFileIoWithNoAllocation(Irp, a2, QuadPart, Length);
    }
    while ( (__int128 *)v49 != &v49 )
    {
      if ( *(__int128 **)(v49 + 8) != &v49 || (v43 = *(_QWORD *)v49, *(_QWORD *)(*(_QWORD *)v49 + 8LL) != (_QWORD)v49) )
        __fastfail(3u);
      v44 = (IRP *)(v49 - 168);
      *(_QWORD *)&v49 = *(_QWORD *)v49;
      *(_QWORD *)(v43 + 8) = &v49;
      v45 = v44->MdlAddress;
      if ( v45 )
      {
        IoFreeMdl(v45);
        v44->MdlAddress = 0;
      }
      IoFreeIrp(v44);
    }
    if ( v10 )
      ExFreePoolWithTag(v10, 0);
  }
  else
  {
    v19 = 0;
    if ( v10 )
    {
      v20 = IoAllocateMdl(v10, Length, 0, 0, 0);
      v19 = v20;
      if ( !v20 )
      {
        ExFreePoolWithTag(v10, 0);
        v12 = QuadPart;
        goto LABEL_13;
      }
      MmBuildMdlForNonPagedPool(v20);
      Irp->MdlAddress = v19;
      v15 = v70;
    }
    v21 = BugCheckParameter2;
    *(_QWORD *)(BugCheckParameter2 + 24) = v15;
    *(_DWORD *)(v21 + 16) = QuadPart;
    if ( !_bittest16((const signed __int16 *)a2 + 128, 0xEu)
      || !*((_QWORD *)a2 + 36)
      || (v22 = 1, *((int *)a2 + 38) < 0) )
    {
      v22 = 0;
    }
    v23 = Irp->Tail.Overlay.CurrentStackLocation;
    v24 = RefsSyncPagingFileCompletionRoutine;
    if ( !v22 )
      v24 = RefsPagingFileCompletionRoutine;
    v23[-1].CompletionRoutine = v24;
    v23[-1].Context = (PVOID)((unsigned __int64)Event & -(__int64)(v22 != 0));
    v23[-1].Control = -32;
    v25 = Irp->Tail.Overlay.CurrentStackLocation;
    v25[-1].Flags |= 2u;
    v25[-1].MajorFunction = Irp->Tail.Overlay.CurrentStackLocation->MajorFunction;
    v25[-1].Parameters.Read.Length = Length;
    v25[-1].Parameters.Read.ByteOffset.QuadPart = v15;
    LODWORD(Irpa) = 0;
    LOBYTE(v25) = v25[-1].MajorFunction;
    RefsPrepareIrpForEncryptionOffload(Irp, v25, a2, QuadPart, 0);
    Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
    RefsCallStorageDriver(*(PDEVICE_OBJECT *)(v68 + 192), Irp, RefsReserveStackStorage, 0);
    if ( _bittest16((const signed __int16 *)a2 + 128, 0xEu) && *((_QWORD *)a2 + 36) && *((int *)a2 + 38) >= 0 )
    {
      KeWaitForSingleObject(Event, Executive, 0, 0, 0);
      if ( v10 )
      {
        IoFreeMdl(v19);
        ExFreePoolWithTag(v10, 0);
        v26 = MdlAddress;
      }
      else
      {
        v27 = Length;
        v26 = MdlAddress;
        RefsDecryptPagingFileBuffer(a2, MdlAddress, QuadPart, v27);
      }
      Irp->MdlAddress = v26;
      IofCompleteRequest(Irp, 1);
    }
  }
}

```

## disassembly

```asm
0x1400ea204  mov     rax, rsp
0x1400ea207  push    rbx
0x1400ea208  push    rsi
0x1400ea209  push    rdi
0x1400ea20a  push    r12
0x1400ea20c  push    r13
0x1400ea20e  push    r14
0x1400ea210  push    r15
0x1400ea212  sub     rsp, 0F0h
0x1400ea219  mov     rbx, rdx
0x1400ea21c  mov     rdi, rcx
0x1400ea21f  xor     esi, esi
0x1400ea221  mov     [rsp+128h+var_B0], rsi
0x1400ea226  mov     [rax-0A8h], rsi
0x1400ea22d  mov     r15, [rdx+90h]
0x1400ea234  mov     [rsp+128h+arg_10], r15
0x1400ea23c  xorps   xmm0, xmm0
0x1400ea23f  movups  [rsp+128h+var_E8], xmm0
0x1400ea244  mov     [rax-0A0h], rsi
0x1400ea24b  xorps   xmm1, xmm1
0x1400ea24e  movups  xmmword ptr [rax-78h], xmm1
0x1400ea252  movups  xmmword ptr [rax-68h], xmm1
0x1400ea256  mov     rax, [rcx+8]
0x1400ea25a  mov     [rsp+128h+var_C8], rax
0x1400ea25f  mov     rax, [rcx+0B8h]
0x1400ea266  mov     al, [rax]
0x1400ea268  mov     [rsp+128h+arg_0], al
0x1400ea26f  mov     rax, [r15+0D0h]
0x1400ea276  mov     rcx, [rax+10h]
0x1400ea27a  mov     eax, [rcx+30h]
0x1400ea27d  and     eax, 0FFFFFFFDh
0x1400ea280  mov     [rcx+30h], eax
0x1400ea283  mov     rax, [rdx+90h]
0x1400ea28a  mov     ecx, [rax+1Ch]
0x1400ea28d  test    cl, 2
0x1400ea290  jz      short loc_1400EA2B4
0x1400ea292  mov     [rsp+128h+var_100], 72657355h; unsigned __int64
0x1400ea29b  mov     [rsp+128h+Irp], rsi; union SmsBigIdentifier *
0x1400ea2a0  mov     r9, [rdx+88h]; struct _FCB *
0x1400ea2a7  xor     r8d, r8d; unsigned __int8
0x1400ea2aa  mov     rdx, rdi; struct _IRP *
0x1400ea2ad  xor     ecx, ecx; struct _IRP_CONTEXT *
0x1400ea2af  call    ?RefsInsertDebugInfoIrpImplementation@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@EPEAU_FCB@@PEBTSmsBigIdentifier@@_K4@Z; RefsInsertDebugInfoIrpImplementation(_IRP_CONTEXT *,_IRP *,uchar,_FCB *,SmsBigIdentifier const *,unsigned __int64,unsigned __int64)
0x1400ea2b4  mov     rax, [rdi+0B8h]
0x1400ea2bb  mov     [rsp+128h+BugCheckParameter2], rax
0x1400ea2c0  mov     r14d, [rax+8]
0x1400ea2c4  test    r14d, r14d
0x1400ea2c7  jnz     short loc_1400EA2EE
0x1400ea2c9  or      byte ptr [rax+3], 1
0x1400ea2cd  xor     r8d, r8d; Status
0x1400ea2d0  mov     rdx, rdi; Irp
0x1400ea2d3  xor     ecx, ecx; struct _IRP_CONTEXT *
0x1400ea2d5  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x1400ea2da  add     rsp, 0F0h
0x1400ea2e1  pop     r15
0x1400ea2e3  pop     r14
0x1400ea2e5  pop     r13
0x1400ea2e7  pop     r12
0x1400ea2e9  pop     rdi
0x1400ea2ea  pop     rsi
0x1400ea2eb  pop     rbx
0x1400ea2ec  retn
0x1400ea2ee  mov     r13, [rax+18h]
0x1400ea2f2  mov     eax, [r15+220h]
0x1400ea2f9  mov     qword ptr [rsp+128h+var_88], rax
0x1400ea301  movsx   ecx, byte ptr [r15+228h]
0x1400ea309  add     rax, r14
0x1400ea30c  add     rax, r13
0x1400ea30f  sar     rax, cl
0x1400ea312  mov     [rsp+128h+var_C0], rax
0x1400ea317  mov     rsi, r13
0x1400ea31a  sar     rsi, cl
0x1400ea31d  mov     [rsp+128h+var_D0], rsi
0x1400ea322  mov     [rsp+128h+var_98], rsi
0x1400ea32a  sub     rax, rsi
0x1400ea32d  mov     [rsp+128h+var_90], rax
0x1400ea335  lea     rax, [rsp+128h+var_A0]
0x1400ea33d  mov     [rsp+128h+var_100], rax; __int64
0x1400ea342  lea     rax, [rsp+128h+var_B0]
0x1400ea347  mov     [rsp+128h+Irp], rax; __int64
0x1400ea34c  mov     r9d, 4
0x1400ea352  lea     r8, [rsp+128h+var_98]
0x1400ea35a  mov     rdx, [rbx+1B0h]; this
0x1400ea361  xor     ecx, ecx; struct CmsTransactionContext *
0x1400ea363  call    MsLookupAllocationCoalesce
0x1400ea368  xor     r10d, r10d
0x1400ea36b  test    eax, eax
0x1400ea36d  js      loc_1400EABF8
0x1400ea373  mov     r8, [rsp+128h+var_B0]
0x1400ea378  mov     [rsp+128h+arg_18], r8
0x1400ea380  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1400ea384  jz      loc_1400EABF8
0x1400ea38a  mov     esi, r10d
0x1400ea38d  mov     [rsp+128h+var_98], r10
0x1400ea395  mov     al, [r15+228h]
0x1400ea39c  mov     byte ptr [rsp+128h+arg_8], al
0x1400ea3a3  mov     [rdi+30h], r10d
0x1400ea3a7  mov     [rdi+38h], r14
0x1400ea3ab  mov     r11d, 4000h
0x1400ea3b1  test    [rbx+100h], r11w
0x1400ea3b9  jz      loc_1400EA46C
0x1400ea3bf  cmp     [rbx+120h], r10
0x1400ea3c6  jz      loc_1400EA46C
0x1400ea3cc  cmp     [rbx+98h], r10d
0x1400ea3d3  jl      loc_1400EA46C
0x1400ea3d9  cmp     [rsp+128h+arg_0], 4
0x1400ea3e1  jnz     short loc_1400EA440
0x1400ea3e3  mov     r8d, 44466552h; Tag
0x1400ea3e9  mov     rdx, r14; NumberOfBytes
0x1400ea3ec  mov     ecx, 200h; PoolType
0x1400ea3f1  call    cs:__imp_ExAllocatePoolWithTag
0x1400ea3f8  nop     dword ptr [rax+rax+00h]
0x1400ea3fd  mov     rsi, rax
0x1400ea400  mov     [rsp+128h+var_98], rax
0x1400ea408  mov     r8, r13; __int64
0x1400ea40b  test    rax, rax
0x1400ea40e  jnz     short loc_1400EA423
0x1400ea410  mov     r9d, r14d; unsigned int
0x1400ea413  mov     rdx, rbx; struct _SCB *
0x1400ea416  mov     rcx, rdi; Irp
0x1400ea419  call    ?RefsPagingFileIoWithNoAllocation@@YAXPEAU_IRP@@PEAU_SCB@@_JK@Z; RefsPagingFileIoWithNoAllocation(_IRP *,_SCB *,__int64,ulong)
0x1400ea41e  jmp     loc_1400EA2DA
0x1400ea423  mov     byte ptr [rsp+128h+var_F8], 0; unsigned __int8
0x1400ea428  mov     [rsp+128h+var_100], rax; void *
0x1400ea42d  mov     dword ptr [rsp+128h+Irp], r14d; unsigned int
0x1400ea432  xor     r9d, r9d; unsigned int
0x1400ea435  mov     rdx, rdi; struct _IRP *
0x1400ea438  mov     rcx, rbx; struct _SCB *
0x1400ea43b  call    ?RefsEncryptPagingFileBuffer@@YAXPEAU_SCB@@PEAU_IRP@@_JKKPEAXE@Z; RefsEncryptPagingFileBuffer(_SCB *,_IRP *,__int64,ulong,ulong,void *,uchar)
0x1400ea440  xor     r8d, r8d; State
0x1400ea443  lea     edx, [r8+1]; Type
0x1400ea447  lea     rcx, [rsp+128h+Event]; Event
0x1400ea44f  call    cs:__imp_KeInitializeEvent
0x1400ea456  nop     dword ptr [rax+rax+00h]
0x1400ea45b  mov     r8, [rsp+128h+arg_18]
0x1400ea463  xor     r10d, r10d
0x1400ea466  mov     r11d, 4000h
0x1400ea46c  mov     r15d, r10d
0x1400ea46f  mov     r9d, r13d
0x1400ea472  and     r9d, dword ptr [rsp+128h+var_88]
0x1400ea47a  mov     cl, byte ptr [rsp+128h+arg_8]
0x1400ea481  shl     r8, cl
0x1400ea484  mov     eax, r9d
0x1400ea487  add     r8, rax
0x1400ea48a  mov     [rsp+128h+arg_18], r8
0x1400ea492  mov     r12, [rsp+128h+var_A8]
0x1400ea49a  mov     eax, r12d
0x1400ea49d  mov     rcx, [rsp+128h+var_D0]
0x1400ea4a2  add     rax, rcx
0x1400ea4a5  mov     rdx, [rsp+128h+var_C0]
0x1400ea4aa  cmp     rax, rdx
0x1400ea4ad  jl      loc_1400EA68B
0x1400ea4b3  mov     r15, r10
0x1400ea4b6  test    rsi, rsi
0x1400ea4b9  jz      short loc_1400EA502
0x1400ea4bb  mov     [rsp+128h+Irp], r10; Irp
0x1400ea4c0  xor     r9d, r9d; ChargeQuota
0x1400ea4c3  xor     r8d, r8d; SecondaryBuffer
0x1400ea4c6  mov     edx, r14d; Length
0x1400ea4c9  mov     rcx, rsi; VirtualAddress
0x1400ea4cc  call    cs:__imp_IoAllocateMdl
0x1400ea4d3  nop     dword ptr [rax+rax+00h]
0x1400ea4d8  mov     r15, rax
0x1400ea4db  test    rax, rax
0x1400ea4de  jz      loc_1400EA642
0x1400ea4e4  mov     rcx, rax; MemoryDescriptorList
0x1400ea4e7  call    cs:__imp_MmBuildMdlForNonPagedPool
0x1400ea4ee  nop     dword ptr [rax+rax+00h]
0x1400ea4f3  mov     [rdi+8], r15
0x1400ea4f7  mov     r8, [rsp+128h+arg_18]
0x1400ea4ff  xor     r10d, r10d
0x1400ea502  mov     rax, [rsp+128h+BugCheckParameter2]
0x1400ea507  mov     [rax+18h], r8
0x1400ea50b  mov     [rax+10h], r13d
0x1400ea50f  bt      word ptr [rbx+100h], 0Eh
0x1400ea518  jnb     short loc_1400EA52E
0x1400ea51a  cmp     [rbx+120h], r10
0x1400ea521  jz      short loc_1400EA52E
0x1400ea523  cmp     [rbx+98h], r10d
0x1400ea52a  mov     dl, 1
0x1400ea52c  jge     short loc_1400EA531
0x1400ea52e  mov     dl, r10b
0x1400ea531  mov     rcx, [rdi+0B8h]
0x1400ea538  lea     rax, ?RefsSyncPagingFileCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; RefsSyncPagingFileCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x1400ea53f  lea     r9, ?RefsPagingFileCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; RefsPagingFileCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x1400ea546  test    dl, dl
0x1400ea548  cmovz   rax, r9
0x1400ea54c  mov     [rcx-10h], rax
0x1400ea550  neg     dl
0x1400ea552  sbb     rax, rax
0x1400ea555  lea     rdx, [rsp+128h+Event]
0x1400ea55d  and     rax, rdx
0x1400ea560  mov     [rcx-8], rax
0x1400ea564  mov     byte ptr [rcx-45h], 0E0h
0x1400ea568  mov     rdx, [rdi+0B8h]
0x1400ea56f  or      byte ptr [rdx-46h], 2
0x1400ea573  mov     rax, [rdi+0B8h]
0x1400ea57a  mov     cl, [rax]
0x1400ea57c  mov     [rdx-48h], cl
0x1400ea57f  mov     [rdx-40h], r14d
0x1400ea583  mov     [rdx-30h], r8
0x1400ea587  mov     dword ptr [rsp+128h+Irp], r10d
0x1400ea58c  mov     r9, r13
0x1400ea58f  mov     r8, rbx
0x1400ea592  mov     dl, [rdx-48h]
0x1400ea595  mov     rcx, rdi
0x1400ea598  call    ?RefsPrepareIrpForEncryptionOffload@@YAXPEAU_IRP@@EPEAU_SCB@@_JW4RefsIoStreamFlags@@@Z; RefsPrepareIrpForEncryptionOffload(_IRP *,uchar,_SCB *,__int64,RefsIoStreamFlags)
0x1400ea59d  mov     rax, [rdi+0B8h]
0x1400ea5a4  or      byte ptr [rax+3], 1
0x1400ea5a8  xor     r9d, r9d; int *
0x1400ea5ab  mov     r8, cs:?RefsReserveStackStorage@@3PEAXEA; Context
0x1400ea5b2  mov     rdx, rdi; Irp
0x1400ea5b5  mov     rax, [rsp+128h+arg_10]
0x1400ea5bd  mov     rcx, [rax+0C0h]; DeviceObject
0x1400ea5c4  call    ?RefsCallStorageDriver@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAXPEAJ@Z; RefsCallStorageDriver(_DEVICE_OBJECT *,_IRP *,void *,long *)
0x1400ea5c9  bt      word ptr [rbx+100h], 0Eh
0x1400ea5d2  jnb     loc_1400EA2DA
0x1400ea5d8  xor     r12d, r12d
0x1400ea5db  cmp     [rbx+120h], r12
0x1400ea5e2  jz      loc_1400EA2DA
0x1400ea5e8  cmp     [rbx+98h], r12d
0x1400ea5ef  jl      loc_1400EA2DA
0x1400ea5f5  mov     [rsp+128h+Irp], r12; Timeout
0x1400ea5fa  xor     r9d, r9d; Alertable
0x1400ea5fd  xor     r8d, r8d; WaitMode
0x1400ea600  xor     edx, edx; WaitReason
0x1400ea602  lea     rcx, [rsp+128h+Event]; Object
0x1400ea60a  call    cs:__imp_KeWaitForSingleObject
0x1400ea611  nop     dword ptr [rax+rax+00h]
0x1400ea616  test    rsi, rsi
0x1400ea619  jz      short loc_1400EA65B
0x1400ea61b  mov     rcx, r15; Mdl
0x1400ea61e  call    cs:__imp_IoFreeMdl
0x1400ea625  nop     dword ptr [rax+rax+00h]
0x1400ea62a  xor     edx, edx; Tag
0x1400ea62c  mov     rcx, rsi; P
0x1400ea62f  call    cs:__imp_ExFreePoolWithTag
0x1400ea636  nop     dword ptr [rax+rax+00h]
0x1400ea63b  mov     r14, [rsp+128h+var_C8]
0x1400ea640  jmp     short loc_1400EA671
0x1400ea642  xor     edx, edx; Tag
0x1400ea644  mov     rcx, rsi; P
0x1400ea647  call    cs:__imp_ExFreePoolWithTag
0x1400ea64e  nop     dword ptr [rax+rax+00h]
0x1400ea653  mov     r8, r13
0x1400ea656  jmp     loc_1400EA410
0x1400ea65b  mov     r9d, r14d; unsigned int
0x1400ea65e  mov     r8, r13; __int64
0x1400ea661  mov     r14, [rsp+128h+var_C8]
0x1400ea666  mov     rdx, r14; struct _MDL *
0x1400ea669  mov     rcx, rbx; struct _SCB *
0x1400ea66c  call    ?RefsDecryptPagingFileBuffer@@YAXPEAU_SCB@@PEAU_MDL@@_JK@Z; RefsDecryptPagingFileBuffer(_SCB *,_MDL *,__int64,ulong)
0x1400ea671  mov     [rdi+8], r14
0x1400ea675  mov     dl, 1; PriorityBoost
0x1400ea677  mov     rcx, rdi; Irp
0x1400ea67a  call    cs:__imp_IofCompleteRequest
0x1400ea681  nop     dword ptr [rax+rax+00h]
0x1400ea686  jmp     loc_1400EA2DA
0x1400ea68b  lea     rax, [rsp+128h+var_E8]
0x1400ea690  mov     qword ptr [rsp+128h+var_E8+8], rax
0x1400ea695  lea     rax, [rsp+128h+var_E8]
0x1400ea69a  mov     qword ptr [rsp+128h+var_E8], rax
0x1400ea69f  mov     [rsp+128h+var_D4], r10d
0x1400ea6a4  test    [rbx+100h], r11w
0x1400ea6ac  jz      loc_1400EA734
0x1400ea6b2  cmp     [rbx+120h], r10
0x1400ea6b9  jz      short loc_1400EA734
0x1400ea6bb  cmp     [rbx+98h], r10d
0x1400ea6c2  jl      short loc_1400EA734
0x1400ea6c4  mov     rax, [rdi+0B8h]
0x1400ea6cb  or      byte ptr [rax+3], 1
0x1400ea6cf  mov     rax, [rdi+0B8h]
0x1400ea6d6  movups  xmm0, xmmword ptr [rax]
0x1400ea6d9  movups  xmmword ptr [rax-48h], xmm0
0x1400ea6dd  movups  xmm1, xmmword ptr [rax+10h]
0x1400ea6e1  movups  xmmword ptr [rax-38h], xmm1
0x1400ea6e5  movups  xmm0, xmmword ptr [rax+20h]
0x1400ea6e9  movups  xmmword ptr [rax-28h], xmm0
0x1400ea6ed  movsd   xmm1, qword ptr [rax+30h]
0x1400ea6f2  movsd   qword ptr [rax-18h], xmm1
0x1400ea6f7  mov     [rax-45h], r10b
0x1400ea6fb  mov     rax, [rdi+0B8h]
0x1400ea702  lea     r8, ?RefsVerifyReadCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; RefsVerifyReadCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x1400ea709  mov     [rax-10h], r8
0x1400ea70d  lea     r8, [rsp+128h+Event]
0x1400ea715  mov     [rax-8], r8
0x1400ea719  mov     [rax-45h], r10b
0x1400ea71d  mov     byte ptr [rax-45h], 40h ; '@'
0x1400ea721  mov     byte ptr [rax-45h], 0C0h
0x1400ea725  mov     byte ptr [rax-45h], 0E0h
0x1400ea729  dec     byte ptr [rdi+43h]
0x1400ea72c  add     qword ptr [rdi+0B8h], 0FFFFFFFFFFFFFFB8h
0x1400ea734  mov     eax, r12d
0x1400ea737  add     rax, rcx
0x1400ea73a  mov     [rsp+128h+BugCheckParameter2], rax
0x1400ea73f  cmp     rax, rdx
0x1400ea742  mov     rax, [rsp+128h+arg_10]
0x1400ea74a  jl      short loc_1400EA754
0x1400ea74c  mov     r12d, r14d
0x1400ea74f  sub     r12d, r15d
  ... truncated ...
```
