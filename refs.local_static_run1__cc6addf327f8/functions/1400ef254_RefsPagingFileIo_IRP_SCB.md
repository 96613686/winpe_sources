# RefsPagingFileIo(_IRP *,_SCB *)

- ea: `0x1400ef254`
- end: `0x1400efca4`
- name: `?RefsPagingFileIo@@YAXPEAU_IRP@@PEAU_SCB@@@Z`
- size: `2640`
- prototype: `void __fastcall(PIRP Irp, struct _SCB *)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1400bc5b0`
- `0x1400bd090`

## callees

- `0x14000e0e0`
- `0x140088c00`
- `0x1400a0338`
- `0x1400ae33c`
- `0x1400e6524`
- `0x1400e7edc`
- `0x1400ef254`
- `0x1400efcac`
- `0x1400f4cc4`
- `0x1400f4de4`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x1400efc35`
- `ntoskrnl!KeBugCheckEx` at `0x1400efc97`
- `ntoskrnl!KeBugCheckEx` at `0x1400efc35`
- `ntoskrnl!KeBugCheckEx` at `0x1400efc97`
- `ntoskrnl!IofCompleteRequest` at `0x1400ef6ca`
- `ntoskrnl!IofCompleteRequest` at `0x1400efa43`
- `ntoskrnl!IofCompleteRequest` at `0x1400ef6ca`
- `ntoskrnl!IofCompleteRequest` at `0x1400efa43`
- `ntoskrnl!IoFreeIrp` at `0x1400efb0f`
- `ntoskrnl!IoFreeIrp` at `0x1401f68a8`
- `ntoskrnl!IoFreeIrp` at `0x1400efb0f`
- `ntoskrnl!IoFreeIrp` at `0x1401f68a8`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400ef888`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400ef888`
- `ntoskrnl!IoAllocateMdl` at `0x1400ef51c`
- `ntoskrnl!IoAllocateMdl` at `0x1400ef83c`
- `ntoskrnl!IoAllocateMdl` at `0x1400ef862`
- `ntoskrnl!IoAllocateMdl` at `0x1400ef51c`
- `ntoskrnl!IoAllocateMdl` at `0x1400ef83c`
- `ntoskrnl!IoAllocateMdl` at `0x1400ef862`
- `ntoskrnl!IoFreeMdl` at `0x1400ef66e`
- `ntoskrnl!IoFreeMdl` at `0x1400efaf8`
- `ntoskrnl!IoFreeMdl` at `0x1401f6891`
- `ntoskrnl!IoFreeMdl` at `0x1400ef66e`
- `ntoskrnl!IoFreeMdl` at `0x1400efaf8`
- `ntoskrnl!IoFreeMdl` at `0x1401f6891`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400ef537`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400ef850`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400ef537`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400ef850`
- `ntoskrnl!IoMakeAssociatedIrpEx` at `0x1400ef7cc`
- `ntoskrnl!IoMakeAssociatedIrpEx` at `0x1400ef7cc`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400ef65a`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400efa15`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400ef65a`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400efa15`
- `ntoskrnl!KeInitializeEvent` at `0x1400ef49f`
- `ntoskrnl!KeInitializeEvent` at `0x1400ef49f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ef67f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ef697`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400efb32`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f68cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ef67f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ef697`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400efb32`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f68cb`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400ef441`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400ef441`

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
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_9c60aa4d8ddb36935dafcdfba0977da1_Traceguids);
    }
    KeBugCheckEx(0x149u, 0xC09AFu, v8, *((_QWORD *)a2 + 3), *((_QWORD *)a2 + 4));
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
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_9c60aa4d8ddb36935dafcdfba0977da1_Traceguids);
        }
        KeBugCheckEx(0x149u, 0xC0B60u, v40, *((_QWORD *)a2 + 3), *((_QWORD *)a2 + 4));
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
0x1400ef254  mov     rax, rsp
0x1400ef257  push    rbx
0x1400ef258  push    rsi
0x1400ef259  push    rdi
0x1400ef25a  push    r12
0x1400ef25c  push    r13
0x1400ef25e  push    r14
0x1400ef260  push    r15
0x1400ef262  sub     rsp, 0F0h
0x1400ef269  mov     rbx, rdx
0x1400ef26c  mov     rdi, rcx
0x1400ef26f  xor     esi, esi
0x1400ef271  mov     [rsp+128h+var_B0], rsi
0x1400ef276  mov     [rax-0A8h], rsi
0x1400ef27d  mov     r15, [rdx+90h]
0x1400ef284  mov     [rsp+128h+arg_10], r15
0x1400ef28c  xorps   xmm0, xmm0
0x1400ef28f  movups  [rsp+128h+var_E8], xmm0
0x1400ef294  mov     [rax-0A0h], rsi
0x1400ef29b  xorps   xmm1, xmm1
0x1400ef29e  movups  xmmword ptr [rax-78h], xmm1
0x1400ef2a2  movups  xmmword ptr [rax-68h], xmm1
0x1400ef2a6  mov     rax, [rcx+8]
0x1400ef2aa  mov     [rsp+128h+var_C8], rax
0x1400ef2af  mov     rax, [rcx+0B8h]
0x1400ef2b6  mov     al, [rax]
0x1400ef2b8  mov     [rsp+128h+arg_0], al
0x1400ef2bf  mov     rax, [r15+0D0h]
0x1400ef2c6  mov     rcx, [rax+10h]
0x1400ef2ca  mov     eax, [rcx+30h]
0x1400ef2cd  and     eax, 0FFFFFFFDh
0x1400ef2d0  mov     [rcx+30h], eax
0x1400ef2d3  mov     rax, [rdx+90h]
0x1400ef2da  mov     ecx, [rax+1Ch]
0x1400ef2dd  test    cl, 2
0x1400ef2e0  jz      short loc_1400EF304
0x1400ef2e2  mov     [rsp+128h+var_100], 72657355h; unsigned __int64
0x1400ef2eb  mov     [rsp+128h+Irp], rsi; union SmsBigIdentifier *
0x1400ef2f0  mov     r9, [rdx+88h]; struct _FCB *
0x1400ef2f7  xor     r8d, r8d; unsigned __int8
0x1400ef2fa  mov     rdx, rdi; struct _IRP *
0x1400ef2fd  xor     ecx, ecx; struct _IRP_CONTEXT *
0x1400ef2ff  call    ?RefsInsertDebugInfoIrpImplementation@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@EPEAU_FCB@@PEBTSmsBigIdentifier@@_K4@Z; RefsInsertDebugInfoIrpImplementation(_IRP_CONTEXT *,_IRP *,uchar,_FCB *,SmsBigIdentifier const *,unsigned __int64,unsigned __int64)
0x1400ef304  mov     rax, [rdi+0B8h]
0x1400ef30b  mov     [rsp+128h+BugCheckParameter2], rax
0x1400ef310  mov     r14d, [rax+8]
0x1400ef314  test    r14d, r14d
0x1400ef317  jnz     short loc_1400EF33E
0x1400ef319  or      byte ptr [rax+3], 1
0x1400ef31d  xor     r8d, r8d; Status
0x1400ef320  mov     rdx, rdi; Irp
0x1400ef323  xor     ecx, ecx; struct _IRP_CONTEXT *
0x1400ef325  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x1400ef32a  add     rsp, 0F0h
0x1400ef331  pop     r15
0x1400ef333  pop     r14
0x1400ef335  pop     r13
0x1400ef337  pop     r12
0x1400ef339  pop     rdi
0x1400ef33a  pop     rsi
0x1400ef33b  pop     rbx
0x1400ef33c  retn
0x1400ef33e  mov     r13, [rax+18h]
0x1400ef342  mov     eax, [r15+220h]
0x1400ef349  mov     qword ptr [rsp+128h+var_88], rax
0x1400ef351  movsx   ecx, byte ptr [r15+228h]
0x1400ef359  add     rax, r14
0x1400ef35c  add     rax, r13
0x1400ef35f  sar     rax, cl
0x1400ef362  mov     [rsp+128h+var_C0], rax
0x1400ef367  mov     rsi, r13
0x1400ef36a  sar     rsi, cl
0x1400ef36d  mov     [rsp+128h+var_D0], rsi
0x1400ef372  mov     [rsp+128h+var_98], rsi
0x1400ef37a  sub     rax, rsi
0x1400ef37d  mov     [rsp+128h+var_90], rax
0x1400ef385  lea     rax, [rsp+128h+var_A0]
0x1400ef38d  mov     [rsp+128h+var_100], rax; __int64
0x1400ef392  lea     rax, [rsp+128h+var_B0]
0x1400ef397  mov     [rsp+128h+Irp], rax; __int64
0x1400ef39c  mov     r9d, 4
0x1400ef3a2  lea     r8, [rsp+128h+var_98]
0x1400ef3aa  mov     rdx, [rbx+1B0h]; this
0x1400ef3b1  xor     ecx, ecx; struct CmsTransactionContext *
0x1400ef3b3  call    MsLookupAllocationCoalesce
0x1400ef3b8  xor     r10d, r10d
0x1400ef3bb  test    eax, eax
0x1400ef3bd  js      loc_1400EFC48
0x1400ef3c3  mov     r8, [rsp+128h+var_B0]
0x1400ef3c8  mov     [rsp+128h+arg_18], r8
0x1400ef3d0  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1400ef3d4  jz      loc_1400EFC48
0x1400ef3da  mov     esi, r10d
0x1400ef3dd  mov     [rsp+128h+var_98], r10
0x1400ef3e5  mov     al, [r15+228h]
0x1400ef3ec  mov     byte ptr [rsp+128h+arg_8], al
0x1400ef3f3  mov     [rdi+30h], r10d
0x1400ef3f7  mov     [rdi+38h], r14
0x1400ef3fb  mov     r11d, 4000h
0x1400ef401  test    [rbx+100h], r11w
0x1400ef409  jz      loc_1400EF4BC
0x1400ef40f  cmp     [rbx+120h], r10
0x1400ef416  jz      loc_1400EF4BC
0x1400ef41c  cmp     [rbx+98h], r10d
0x1400ef423  jl      loc_1400EF4BC
0x1400ef429  cmp     [rsp+128h+arg_0], 4
0x1400ef431  jnz     short loc_1400EF490
0x1400ef433  mov     r8d, 44466552h; Tag
0x1400ef439  mov     rdx, r14; NumberOfBytes
0x1400ef43c  mov     ecx, 200h; PoolType
0x1400ef441  call    cs:__imp_ExAllocatePoolWithTag
0x1400ef448  nop     dword ptr [rax+rax+00h]
0x1400ef44d  mov     rsi, rax
0x1400ef450  mov     [rsp+128h+var_98], rax
0x1400ef458  mov     r8, r13; __int64
0x1400ef45b  test    rax, rax
0x1400ef45e  jnz     short loc_1400EF473
0x1400ef460  mov     r9d, r14d; unsigned int
0x1400ef463  mov     rdx, rbx; struct _SCB *
0x1400ef466  mov     rcx, rdi; Irp
0x1400ef469  call    ?RefsPagingFileIoWithNoAllocation@@YAXPEAU_IRP@@PEAU_SCB@@_JK@Z; RefsPagingFileIoWithNoAllocation(_IRP *,_SCB *,__int64,ulong)
0x1400ef46e  jmp     loc_1400EF32A
0x1400ef473  mov     byte ptr [rsp+128h+var_F8], 0; unsigned __int8
0x1400ef478  mov     [rsp+128h+var_100], rax; void *
0x1400ef47d  mov     dword ptr [rsp+128h+Irp], r14d; unsigned int
0x1400ef482  xor     r9d, r9d; unsigned int
0x1400ef485  mov     rdx, rdi; struct _IRP *
0x1400ef488  mov     rcx, rbx; struct _SCB *
0x1400ef48b  call    ?RefsEncryptPagingFileBuffer@@YAXPEAU_SCB@@PEAU_IRP@@_JKKPEAXE@Z; RefsEncryptPagingFileBuffer(_SCB *,_IRP *,__int64,ulong,ulong,void *,uchar)
0x1400ef490  xor     r8d, r8d; State
0x1400ef493  lea     edx, [r8+1]; Type
0x1400ef497  lea     rcx, [rsp+128h+Event]; Event
0x1400ef49f  call    cs:__imp_KeInitializeEvent
0x1400ef4a6  nop     dword ptr [rax+rax+00h]
0x1400ef4ab  mov     r8, [rsp+128h+arg_18]
0x1400ef4b3  xor     r10d, r10d
0x1400ef4b6  mov     r11d, 4000h
0x1400ef4bc  mov     r15d, r10d
0x1400ef4bf  mov     r9d, r13d
0x1400ef4c2  and     r9d, dword ptr [rsp+128h+var_88]
0x1400ef4ca  mov     cl, byte ptr [rsp+128h+arg_8]
0x1400ef4d1  shl     r8, cl
0x1400ef4d4  mov     eax, r9d
0x1400ef4d7  add     r8, rax
0x1400ef4da  mov     [rsp+128h+arg_18], r8
0x1400ef4e2  mov     r12, [rsp+128h+var_A8]
0x1400ef4ea  mov     eax, r12d
0x1400ef4ed  mov     rcx, [rsp+128h+var_D0]
0x1400ef4f2  add     rax, rcx
0x1400ef4f5  mov     rdx, [rsp+128h+var_C0]
0x1400ef4fa  cmp     rax, rdx
0x1400ef4fd  jl      loc_1400EF6DB
0x1400ef503  mov     r15, r10
0x1400ef506  test    rsi, rsi
0x1400ef509  jz      short loc_1400EF552
0x1400ef50b  mov     [rsp+128h+Irp], r10; Irp
0x1400ef510  xor     r9d, r9d; ChargeQuota
0x1400ef513  xor     r8d, r8d; SecondaryBuffer
0x1400ef516  mov     edx, r14d; Length
0x1400ef519  mov     rcx, rsi; VirtualAddress
0x1400ef51c  call    cs:__imp_IoAllocateMdl
0x1400ef523  nop     dword ptr [rax+rax+00h]
0x1400ef528  mov     r15, rax
0x1400ef52b  test    rax, rax
0x1400ef52e  jz      loc_1400EF692
0x1400ef534  mov     rcx, rax; MemoryDescriptorList
0x1400ef537  call    cs:__imp_MmBuildMdlForNonPagedPool
0x1400ef53e  nop     dword ptr [rax+rax+00h]
0x1400ef543  mov     [rdi+8], r15
0x1400ef547  mov     r8, [rsp+128h+arg_18]
0x1400ef54f  xor     r10d, r10d
0x1400ef552  mov     rax, [rsp+128h+BugCheckParameter2]
0x1400ef557  mov     [rax+18h], r8
0x1400ef55b  mov     [rax+10h], r13d
0x1400ef55f  bt      word ptr [rbx+100h], 0Eh
0x1400ef568  jnb     short loc_1400EF57E
0x1400ef56a  cmp     [rbx+120h], r10
0x1400ef571  jz      short loc_1400EF57E
0x1400ef573  cmp     [rbx+98h], r10d
0x1400ef57a  mov     dl, 1
0x1400ef57c  jge     short loc_1400EF581
0x1400ef57e  mov     dl, r10b
0x1400ef581  mov     rcx, [rdi+0B8h]
0x1400ef588  lea     rax, ?RefsSyncPagingFileCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; RefsSyncPagingFileCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x1400ef58f  lea     r9, ?RefsPagingFileCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; RefsPagingFileCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x1400ef596  test    dl, dl
0x1400ef598  cmovz   rax, r9
0x1400ef59c  mov     [rcx-10h], rax
0x1400ef5a0  neg     dl
0x1400ef5a2  sbb     rax, rax
0x1400ef5a5  lea     rdx, [rsp+128h+Event]
0x1400ef5ad  and     rax, rdx
0x1400ef5b0  mov     [rcx-8], rax
0x1400ef5b4  mov     byte ptr [rcx-45h], 0E0h
0x1400ef5b8  mov     rdx, [rdi+0B8h]
0x1400ef5bf  or      byte ptr [rdx-46h], 2
0x1400ef5c3  mov     rax, [rdi+0B8h]
0x1400ef5ca  mov     cl, [rax]
0x1400ef5cc  mov     [rdx-48h], cl
0x1400ef5cf  mov     [rdx-40h], r14d
0x1400ef5d3  mov     [rdx-30h], r8
0x1400ef5d7  mov     dword ptr [rsp+128h+Irp], r10d
0x1400ef5dc  mov     r9, r13
0x1400ef5df  mov     r8, rbx
0x1400ef5e2  mov     dl, [rdx-48h]
0x1400ef5e5  mov     rcx, rdi
0x1400ef5e8  call    ?RefsPrepareIrpForEncryptionOffload@@YAXPEAU_IRP@@EPEAU_SCB@@_JW4RefsIoStreamFlags@@@Z; RefsPrepareIrpForEncryptionOffload(_IRP *,uchar,_SCB *,__int64,RefsIoStreamFlags)
0x1400ef5ed  mov     rax, [rdi+0B8h]
0x1400ef5f4  or      byte ptr [rax+3], 1
0x1400ef5f8  xor     r9d, r9d; int *
0x1400ef5fb  mov     r8, cs:?RefsReserveStackStorage@@3PEAXEA; Context
0x1400ef602  mov     rdx, rdi; Irp
0x1400ef605  mov     rax, [rsp+128h+arg_10]
0x1400ef60d  mov     rcx, [rax+0C0h]; DeviceObject
0x1400ef614  call    ?RefsCallStorageDriver@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAXPEAJ@Z; RefsCallStorageDriver(_DEVICE_OBJECT *,_IRP *,void *,long *)
0x1400ef619  bt      word ptr [rbx+100h], 0Eh
0x1400ef622  jnb     loc_1400EF32A
0x1400ef628  xor     r12d, r12d
0x1400ef62b  cmp     [rbx+120h], r12
0x1400ef632  jz      loc_1400EF32A
0x1400ef638  cmp     [rbx+98h], r12d
0x1400ef63f  jl      loc_1400EF32A
0x1400ef645  mov     [rsp+128h+Irp], r12; Timeout
0x1400ef64a  xor     r9d, r9d; Alertable
0x1400ef64d  xor     r8d, r8d; WaitMode
0x1400ef650  xor     edx, edx; WaitReason
0x1400ef652  lea     rcx, [rsp+128h+Event]; Object
0x1400ef65a  call    cs:__imp_KeWaitForSingleObject
0x1400ef661  nop     dword ptr [rax+rax+00h]
0x1400ef666  test    rsi, rsi
0x1400ef669  jz      short loc_1400EF6AB
0x1400ef66b  mov     rcx, r15; Mdl
0x1400ef66e  call    cs:__imp_IoFreeMdl
0x1400ef675  nop     dword ptr [rax+rax+00h]
0x1400ef67a  xor     edx, edx; Tag
0x1400ef67c  mov     rcx, rsi; P
0x1400ef67f  call    cs:__imp_ExFreePoolWithTag
0x1400ef686  nop     dword ptr [rax+rax+00h]
0x1400ef68b  mov     r14, [rsp+128h+var_C8]
0x1400ef690  jmp     short loc_1400EF6C1
0x1400ef692  xor     edx, edx; Tag
0x1400ef694  mov     rcx, rsi; P
0x1400ef697  call    cs:__imp_ExFreePoolWithTag
0x1400ef69e  nop     dword ptr [rax+rax+00h]
0x1400ef6a3  mov     r8, r13
0x1400ef6a6  jmp     loc_1400EF460
0x1400ef6ab  mov     r9d, r14d; unsigned int
0x1400ef6ae  mov     r8, r13; __int64
0x1400ef6b1  mov     r14, [rsp+128h+var_C8]
0x1400ef6b6  mov     rdx, r14; struct _MDL *
0x1400ef6b9  mov     rcx, rbx; struct _SCB *
0x1400ef6bc  call    ?RefsDecryptPagingFileBuffer@@YAXPEAU_SCB@@PEAU_MDL@@_JK@Z; RefsDecryptPagingFileBuffer(_SCB *,_MDL *,__int64,ulong)
0x1400ef6c1  mov     [rdi+8], r14
0x1400ef6c5  mov     dl, 1; PriorityBoost
0x1400ef6c7  mov     rcx, rdi; Irp
0x1400ef6ca  call    cs:__imp_IofCompleteRequest
0x1400ef6d1  nop     dword ptr [rax+rax+00h]
0x1400ef6d6  jmp     loc_1400EF32A
0x1400ef6db  lea     rax, [rsp+128h+var_E8]
0x1400ef6e0  mov     qword ptr [rsp+128h+var_E8+8], rax
0x1400ef6e5  lea     rax, [rsp+128h+var_E8]
0x1400ef6ea  mov     qword ptr [rsp+128h+var_E8], rax
0x1400ef6ef  mov     [rsp+128h+var_D4], r10d
0x1400ef6f4  test    [rbx+100h], r11w
0x1400ef6fc  jz      loc_1400EF784
0x1400ef702  cmp     [rbx+120h], r10
0x1400ef709  jz      short loc_1400EF784
0x1400ef70b  cmp     [rbx+98h], r10d
0x1400ef712  jl      short loc_1400EF784
0x1400ef714  mov     rax, [rdi+0B8h]
0x1400ef71b  or      byte ptr [rax+3], 1
0x1400ef71f  mov     rax, [rdi+0B8h]
0x1400ef726  movups  xmm0, xmmword ptr [rax]
0x1400ef729  movups  xmmword ptr [rax-48h], xmm0
0x1400ef72d  movups  xmm1, xmmword ptr [rax+10h]
0x1400ef731  movups  xmmword ptr [rax-38h], xmm1
0x1400ef735  movups  xmm0, xmmword ptr [rax+20h]
0x1400ef739  movups  xmmword ptr [rax-28h], xmm0
0x1400ef73d  movsd   xmm1, qword ptr [rax+30h]
0x1400ef742  movsd   qword ptr [rax-18h], xmm1
0x1400ef747  mov     [rax-45h], r10b
0x1400ef74b  mov     rax, [rdi+0B8h]
0x1400ef752  lea     r8, ?RefsVerifyReadCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; RefsVerifyReadCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x1400ef759  mov     [rax-10h], r8
0x1400ef75d  lea     r8, [rsp+128h+Event]
0x1400ef765  mov     [rax-8], r8
0x1400ef769  mov     [rax-45h], r10b
0x1400ef76d  mov     byte ptr [rax-45h], 40h ; '@'
0x1400ef771  mov     byte ptr [rax-45h], 0C0h
0x1400ef775  mov     byte ptr [rax-45h], 0E0h
0x1400ef779  dec     byte ptr [rdi+43h]
0x1400ef77c  add     qword ptr [rdi+0B8h], 0FFFFFFFFFFFFFFB8h
0x1400ef784  mov     eax, r12d
0x1400ef787  add     rax, rcx
0x1400ef78a  mov     [rsp+128h+BugCheckParameter2], rax
0x1400ef78f  cmp     rax, rdx
0x1400ef792  mov     rax, [rsp+128h+arg_10]
0x1400ef79a  jl      short loc_1400EF7A4
0x1400ef79c  mov     r12d, r14d
0x1400ef79f  sub     r12d, r15d
  ... truncated ...
```
