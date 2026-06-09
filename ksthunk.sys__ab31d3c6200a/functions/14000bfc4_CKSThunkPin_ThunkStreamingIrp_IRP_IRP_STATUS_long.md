# CKSThunkPin::ThunkStreamingIrp(_IRP *,_IRP_STATUS,long *)

- ea: `0x14000bfc4`
- end: `0x14000c9b4`
- name: `?ThunkStreamingIrp@CKSThunkPin@@AEAA?AW4_IRP_DISPOSITION@@PEAU_IRP@@W4_IRP_STATUS@@PEAJ@Z`
- size: `2544`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140002c80`

## callees

- `0x1400010f4`
- `0x140002d30`
- `0x140002d74`
- `0x140002d90`
- `0x140002f5c`
- `0x140004140`
- `0x1400041f0`
- `0x140004240`
- `0x140004540`
- `0x14000bfc4`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c06a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c573`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c06a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c573`
- `ntoskrnl!IofCallDriver` at `0x14000c882`
- `ntoskrnl!IofCallDriver` at `0x14000c882`
- `ntoskrnl!ProbeForRead` at `0x14000c125`
- `ntoskrnl!ProbeForRead` at `0x14000c125`
- `ntoskrnl!MmUnlockPages` at `0x14000c951`
- `ntoskrnl!MmUnlockPages` at `0x14000c951`
- `ntoskrnl!MmProbeAndLockPages` at `0x14000c48c`
- `ntoskrnl!MmProbeAndLockPages` at `0x14000c48c`
- `ntoskrnl!IoFreeIrp` at `0x14000c0a9`
- `ntoskrnl!IoFreeIrp` at `0x14000c97f`
- `ntoskrnl!IoFreeIrp` at `0x14000c0a9`
- `ntoskrnl!IoFreeIrp` at `0x14000c97f`
- `ntoskrnl!IoAllocateMdl` at `0x14000c289`
- `ntoskrnl!IoAllocateMdl` at `0x14000c315`
- `ntoskrnl!IoAllocateMdl` at `0x14000c289`
- `ntoskrnl!IoAllocateMdl` at `0x14000c315`
- `ntoskrnl!ProbeForWrite` at `0x14000c0e0`
- `ntoskrnl!ProbeForWrite` at `0x14000c133`
- `ntoskrnl!ProbeForWrite` at `0x14000c233`
- `ntoskrnl!ProbeForWrite` at `0x14000c2d4`
- `ntoskrnl!ProbeForWrite` at `0x14000c0e0`
- `ntoskrnl!ProbeForWrite` at `0x14000c133`
- `ntoskrnl!ProbeForWrite` at `0x14000c233`
- `ntoskrnl!ProbeForWrite` at `0x14000c2d4`
- `ntoskrnl!IoFreeMdl` at `0x14000c967`
- `ntoskrnl!IoFreeMdl` at `0x14000c967`
- `ntoskrnl!IoAllocateIrp` at `0x14000c02f`
- `ntoskrnl!IoAllocateIrp` at `0x14000c02f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000c4cb`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000c6d8`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000c78c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000c4cb`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000c6d8`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000c78c`
- `ntoskrnl!ExRaiseStatus` at `0x14000c24c`
- `ntoskrnl!ExRaiseStatus` at `0x14000c29f`
- `ntoskrnl!ExRaiseStatus` at `0x14000c2ec`
- `ntoskrnl!ExRaiseStatus` at `0x14000c32b`
- `ntoskrnl!ExRaiseStatus` at `0x14000c33c`
- `ntoskrnl!ExRaiseStatus` at `0x14000c384`
- `ntoskrnl!ExRaiseStatus` at `0x14000c3b5`
- `ntoskrnl!ExRaiseStatus` at `0x14000c416`
- `ntoskrnl!ExRaiseStatus` at `0x14000c42f`
- `ntoskrnl!ExRaiseStatus` at `0x14000c448`
- `ntoskrnl!ExRaiseStatus` at `0x14000c459`
- `ntoskrnl!ExRaiseStatus` at `0x14000c46a`
- `ntoskrnl!ExRaiseStatus` at `0x14000c4e1`
- `ntoskrnl!ExRaiseStatus` at `0x14000c24c`
- `ntoskrnl!ExRaiseStatus` at `0x14000c29f`
- `ntoskrnl!ExRaiseStatus` at `0x14000c2ec`
- `ntoskrnl!ExRaiseStatus` at `0x14000c32b`
- `ntoskrnl!ExRaiseStatus` at `0x14000c33c`
- `ntoskrnl!ExRaiseStatus` at `0x14000c384`
- `ntoskrnl!ExRaiseStatus` at `0x14000c3b5`
- `ntoskrnl!ExRaiseStatus` at `0x14000c416`
- `ntoskrnl!ExRaiseStatus` at `0x14000c42f`
- `ntoskrnl!ExRaiseStatus` at `0x14000c448`
- `ntoskrnl!ExRaiseStatus` at `0x14000c459`
- `ntoskrnl!ExRaiseStatus` at `0x14000c46a`
- `ntoskrnl!ExRaiseStatus` at `0x14000c4e1`
- `ntoskrnl!ExFreePool` at `0x14000c993`
- `ntoskrnl!ExFreePool` at `0x14000c993`

## pseudocode

```c
__int64 __fastcall CKSThunkPin::ThunkStreamingIrp(__int64 a1, __int64 a2, __int64 a3, int *a4)
{
  __int64 v6; // rdi
  SIZE_T v7; // r12
  PIRP Irp; // r15
  unsigned int *PoolWithTag; // rax
  unsigned int *v10; // rdi
  int IsEnabledDeviceUsageNoInline; // eax
  int v12; // ecx
  void *v13; // rdx
  bool v14; // zf
  volatile void *v15; // rcx
  int v16; // edx
  unsigned int v17; // ecx
  char v18; // si
  unsigned int v19; // ecx
  unsigned int v20; // eax
  ULONG v21; // edx
  struct KSSTREAM_METADATA_INFO32 *MetadataBuffer32; // rax
  ULONG *v23; // rsi
  volatile void *v24; // rcx
  unsigned int v25; // eax
  int ExtendedHeaderSize; // ecx
  __int64 v27; // rsi
  CKSThunkPin *v28; // rax
  __int64 v29; // rcx
  unsigned int v30; // eax
  __int64 v31; // rax
  struct _MDL *i; // rdi
  PVOID MappedSystemVa; // rax
  char *v34; // rsi
  char *v35; // r10
  int v36; // eax
  __int64 v37; // rdi
  char *v38; // rax
  struct _LIST_ENTRY *v39; // r8
  unsigned int v40; // r9d
  __int64 v41; // r11
  struct KSSTREAM_HEADER *v42; // rsi
  PMDL MdlAddress; // rdi
  struct _KSSTREAM_HEADER32 *v44; // r8
  int v45; // ecx
  ULONG *v46; // r12
  ULONG v47; // ecx
  ULONG v48; // eax
  int v49; // eax
  struct KSSTREAM_METADATA_INFO *MetadataBuffer64; // rax
  struct _KSSTREAM_HEADER32 *v51; // r8
  PVOID v52; // rax
  struct KSSTREAM_METADATA_INFO *v53; // rax
  ULONG *v54; // rdx
  struct KSSTREAM_METADATA_INFO *v55; // r12
  PVOID v56; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  struct _IO_STACK_LOCATION *v58; // rax
  int v60; // r12d
  unsigned int v61; // eax
  const void *v62; // rdx
  __int64 v63; // rcx
  int v64; // ecx
  PMDL v65; // rdi
  unsigned int v66; // [rsp+30h] [rbp-98h]
  struct _KSSTREAM_HEADER32 *v67; // [rsp+38h] [rbp-90h]
  __int64 v68; // [rsp+48h] [rbp-80h]
  int v69; // [rsp+50h] [rbp-78h]
  unsigned int v70; // [rsp+58h] [rbp-70h]
  char *v71; // [rsp+58h] [rbp-70h]
  __int64 v72; // [rsp+80h] [rbp-48h]
  char *v74; // [rsp+D8h] [rbp+10h]
  char v75; // [rsp+E0h] [rbp+18h]
  int v76; // [rsp+E0h] [rbp+18h]

  v6 = *(_QWORD *)(a2 + 184);
  v68 = v6;
  v7 = *(unsigned int *)(v6 + 8);
  v70 = v7;
  if ( (unsigned int)v7 < 0x30 )
  {
    *a4 = -1073741306;
    return 0;
  }
  Irp = IoAllocateIrp(*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 40LL) + 76LL), 0);
  if ( !Irp )
  {
LABEL_4:
    *a4 = -1073741670;
    return 0;
  }
  v72 = v6;
  PoolWithTag = (unsigned int *)ExAllocatePoolWithTag((POOL_TYPE)1536, v7, 0x6274534Bu);
  v10 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported && PoolWithTag )
    memset(PoolWithTag, 0, v7);
  v67 = (struct _KSSTREAM_HEADER32 *)v10;
  if ( !v10 )
  {
    IoFreeIrp(Irp);
    goto LABEL_4;
  }
  IsEnabledDeviceUsageNoInline = Feature_Servicing_KSTHUNK_UMA__private_IsEnabledDeviceUsageNoInline();
  v12 = *(_DWORD *)(v72 + 24);
  if ( IsEnabledDeviceUsageNoInline )
  {
    if ( v12 != 3112979 )
      ProbeForWrite(*(volatile void **)(a2 + 112), v7, 1u);
    v13 = *(void **)(a2 + 112);
    if ( *(_BYTE *)(a2 + 64) )
      RtlCopyFromUser(v10, v13, v7);
    else
      RtlCopyVolatileMemory(v10, v13, v7);
  }
  else
  {
    v14 = v12 == 3112979;
    v15 = *(volatile void **)(a2 + 112);
    if ( v14 )
      ProbeForRead(v15, v7, 1u);
    else
      ProbeForWrite(v15, v7, 1u);
    memmove(v10, *(const void **)(a2 + 112), v7);
  }
  *(_QWORD *)(a2 + 24) = v10;
  *(_DWORD *)(a2 + 16) |= 0x30u;
  if ( *(_DWORD *)(v68 + 24) == 3096599 )
    *(_DWORD *)(a2 + 16) |= 0x40u;
  v16 = 0;
  v69 = 0;
  v17 = 0;
  v66 = 0;
  v18 = *(_BYTE *)(a1 + 116);
  v75 = v18;
  if ( *a4 >= 0 )
  {
    while ( (_DWORD)v7 )
    {
      v19 = *v10;
      if ( (unsigned int)v7 < *v10 )
        break;
      if ( v19 < 0x30 || (v10[11] & 0x1000) != 0 && v19 < 0x88 )
        ExRaiseStatus(-1073741811);
      v69 = v16 + 1;
      v20 = v10[10];
      if ( !v20 )
        ExRaiseStatus(-1073741811);
      ProbeForWrite((volatile void *)v20, v10[8], 1u);
      v21 = v10[8];
      if ( v10[9] > v21 )
        ExRaiseStatus(-1073741306);
      if ( !v18 || v70 > *v10 )
        v10[11] &= 0xFFFE7FFF;
      if ( (v10[11] & 0x18000) == 0 && !IoAllocateMdl((PVOID)v10[10], v21, Irp->MdlAddress != 0, 1u, Irp) )
        ExRaiseStatus(-1073741670);
      MetadataBuffer32 = GetMetadataBuffer32((struct _KSSTREAM_HEADER32 *)v10);
      v23 = (ULONG *)MetadataBuffer32;
      if ( MetadataBuffer32 )
      {
        v24 = (volatile void *)*((unsigned int *)MetadataBuffer32 + 2);
        if ( !(_DWORD)v24 || (v25 = *(_DWORD *)MetadataBuffer32) == 0 )
          ExRaiseStatus(-1073741811);
        ProbeForWrite(v24, v25, 1u);
        if ( v23[1] > *v23 )
          ExRaiseStatus(-1073741306);
        if ( (v10[11] & 0x18000) == 0 && !IoAllocateMdl((PVOID)v23[2], *v23, Irp->MdlAddress != 0, 1u, Irp) )
          ExRaiseStatus(-1073741670);
      }
      ExtendedHeaderSize = 0;
      v27 = *v10;
      if ( (unsigned int)v27 > 0x30 )
      {
        v28 = (CKSThunkPin *)a1;
        v29 = *(_QWORD *)(a1 + 104);
        if ( v29 )
        {
          if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v29 + 32LL))(v29, v10[11], 0) != v27 - 48 )
            ExRaiseStatus(-1073741811);
          v28 = (CKSThunkPin *)a1;
        }
        ExtendedHeaderSize = CKSThunkPin::GetExtendedHeaderSize(v28, v10[11], *v10 - 48);
        if ( !ExtendedHeaderSize )
          ExRaiseStatus(-1073741811);
      }
      v30 = v66 + 56;
      if ( v66 + 56 < v66 )
        ExRaiseStatus(-1073741811);
      v66 = v30 + ExtendedHeaderSize;
      if ( v30 + ExtendedHeaderSize < v30 )
        ExRaiseStatus(-1073741811);
      v31 = *v10;
      if ( (unsigned int)v7 < (unsigned int)v31 )
        ExRaiseStatus(-1073741811);
      LODWORD(v7) = v7 - v31;
      v10 = (unsigned int *)((char *)v10 + v31);
      v18 = v75;
      v16 = v69;
    }
    for ( i = Irp->MdlAddress; i; i = i->Next )
    {
      MmProbeAndLockPages(i, *(_BYTE *)(a2 + 64), IoWriteAccess);
      i->MdlFlags |= 0x2000u;
      if ( (i->MdlFlags & 5) != 0 )
        MappedSystemVa = i->MappedSystemVa;
      else
        MappedSystemVa = MmMapLockedPagesSpecifyCache(i, 0, MmCached, 0, 0, 0x40000000u);
      if ( !MappedSystemVa )
        ExRaiseStatus(-1073741670);
    }
    v17 = v66;
  }
  v34 = 0;
  v35 = 0;
  v36 = *a4;
  if ( *a4 < 0 )
    goto LABEL_107;
  if ( (_DWORD)v7 )
  {
    *a4 = -1073741811;
    v36 = -1073741811;
  }
  if ( v36 < 0 )
    goto LABEL_107;
  v37 = v17;
  v38 = (char *)ExAllocatePoolWithTag((POOL_TYPE)1536, v17 + 16LL, 0x6373534Bu);
  v34 = v38;
  v74 = v38;
  if ( !ExPoolZeroingNativelySupported && v38 )
    memset(v38, 0, v37 + 16);
  v35 = v34 + 16;
  v71 = v34 + 16;
  v39 = (struct _LIST_ENTRY *)a1;
  v40 = v66;
  v41 = v68;
  if ( !v34 )
  {
    *a4 = -1073741670;
    goto LABEL_108;
  }
  *(_DWORD *)v34 = *(_DWORD *)(v68 + 24);
  *((_DWORD *)v34 + 1) = v66;
  *((_QWORD *)v34 + 1) = a1;
  v42 = (struct KSSTREAM_HEADER *)(v34 + 16);
  MdlAddress = Irp->MdlAddress;
  if ( !v69 )
  {
    v34 = v74;
    goto LABEL_108;
  }
  v44 = v67;
  while ( 1 )
  {
    v45 = 0;
    v76 = 0;
    v46 = (ULONG *)((char *)v44 + 44);
    if ( *(_DWORD *)v44 > 0x30u )
    {
      v45 = CKSThunkPin::GetExtendedHeaderSize((CKSThunkPin *)a1, *v46, (unsigned int)(*(_DWORD *)v44 - 48));
      v76 = v45;
      v44 = v67;
    }
    v42->Size = v45 + 56;
    v42->TypeSpecificFlags = *((_DWORD *)v44 + 1);
    v42->PresentationTime.Time = *((_QWORD *)v44 + 1);
    v42->PresentationTime.Numerator = *((_DWORD *)v44 + 4);
    v42->PresentationTime.Denominator = *((_DWORD *)v44 + 5);
    v42->Duration = *((_QWORD *)v44 + 3);
    v47 = *((_DWORD *)v44 + 8);
    v42->FrameExtent = v47;
    v42->DataUsed = *((_DWORD *)v44 + 9);
    v48 = *v46;
    v42->OptionsFlags = *v46;
    v49 = v48 & 0x8000;
    if ( !MdlAddress && !v49 )
    {
      MetadataBuffer64 = GetMetadataBuffer64(v42);
      v42->Data = 0;
      if ( MetadataBuffer64 )
        MetadataBuffer64->Data = 0;
      goto LABEL_111;
    }
    if ( !v47 )
      break;
    if ( v49 )
    {
      v42->Data = (PVOID)*((unsigned int *)v44 + 10);
    }
    else
    {
      if ( (MdlAddress->MdlFlags & 5) != 0 )
      {
        v52 = MdlAddress->MappedSystemVa;
      }
      else
      {
        v52 = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u);
        v44 = v67;
      }
      v42->Data = v52;
      if ( !v52 )
      {
LABEL_105:
        *a4 = -1073741670;
        goto LABEL_106;
      }
    }
    if ( GetMetadataBuffer32(v44) )
    {
      if ( MdlAddress && (MdlAddress = MdlAddress->Next) != 0 || (v42->OptionsFlags & 0x8000) != 0 )
      {
        v53 = GetMetadataBuffer64(v42);
        v55 = v53;
        if ( v53 )
        {
          v53->BufferSize = *v54;
          v53->Flags = v54[4];
          v53->Reserved = v54[5];
          v53->UsedSize = v54[1];
          v53->SystemVa = 0;
          if ( (*((_DWORD *)v51 + 11) & 0x18000) != 0 )
          {
            v53->Data = (PVOID)v54[2];
          }
          else
          {
            if ( (MdlAddress->MdlFlags & 5) != 0 )
            {
              v56 = MdlAddress->MappedSystemVa;
            }
            else
            {
              v56 = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u);
              v51 = v67;
            }
            v55->Data = v56;
            if ( !v56 )
              goto LABEL_105;
          }
        }
      }
    }
LABEL_111:
    v60 = 0;
    v61 = *(_DWORD *)v51 - 48;
    if ( *(_DWORD *)v51 == 48 )
      goto LABEL_118;
    v62 = (char *)v51 + 48;
    v63 = *(_QWORD *)(a1 + 104);
    if ( v63 )
    {
      (*(void (__fastcall **)(__int64, const void *, struct KSSTREAM_HEADER *))(*(_QWORD *)v63 + 40LL))(
        v63,
        v62,
        v42 + 1);
    }
    else
    {
      if ( v61 != v76 )
      {
        v60 = -1073741811;
        goto LABEL_118;
      }
      memmove(&v42[1], v62, v61);
    }
    v51 = v67;
LABEL_118:
    *a4 = v60;
    if ( v60 >= 0 )
    {
      v64 = --v69;
      v42 = (struct KSSTREAM_HEADER *)((char *)v42 + v42->Size);
      v44 = (struct _KSSTREAM_HEADER32 *)((char *)v51 + *(unsigned int *)v51);
      v67 = v44;
      if ( MdlAddress )
        MdlAddress = MdlAddress->Next;
      if ( v64 )
        continue;
    }
    goto LABEL_106;
  }
  *a4 = -1073741811;
LABEL_106:
  v35 = v71;
  v34 = v74;
LABEL_107:
  v41 = v68;
  v40 = v66;
  v39 = (struct _LIST_ENTRY *)a1;
LABEL_108:
  if ( *a4 >= 0 )
  {
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].DeviceObject = (PDEVICE_OBJECT)v39[2].Flink[3].Blink;
    CurrentStackLocation[-1].FileObject = *(PFILE_OBJECT *)(v72 + 48);
    CurrentStackLocation[-1].MajorFunction = 14;
    CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = *(_DWORD *)(v41 + 24);
    CurrentStackLocation[-1].Parameters.Create.Options = 0;
    CurrentStackLocation[-1].Parameters.Read.Length = v40;
    Irp->UserBuffer = v35;
    Irp->RequestorMode = 0;
    Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = (struct _LIST_ENTRY *)KeGetCurrentThread();
    Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink = v39;
    *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
    *(_QWORD *)(a2 + 120) = Irp;
    *(_QWORD *)(a2 + 128) = v39;
    *(_QWORD *)(a2 + 136) = 0;
    v58 = Irp->Tail.Overlay.CurrentStackLocation;
    v58[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)CKSThunkPin::ThunkStreamingIrpCompletion;
    v58[-1].Context = (PVOID)a2;
    v58[-1].Control = -32;
    _InterlockedExchange64((volatile __int64 *)(a2 + 104), (__int64)CKSThunkPin::CancelStreamingIrp);
    IofCallDriver((PDEVICE_OBJECT)v39[2].Flink[3].Blink, Irp);
    return 2;
  }
  while ( 1 )
  {
    v65 = Irp->MdlAddress;
    if ( !v65 )
      break;
    if ( (v65->MdlFlags & 2) != 0 )
      MmUnlockPages(Irp->MdlAddress);
    Irp->MdlAddress = v65->Next;
    IoFreeMdl(v65);
  }
  IoFreeIrp(Irp);
  if ( v34 )
    ExFreePool(v34);
  return 0;
}

```

## disassembly

```asm
0x14000bfc4  mov     rax, rsp
0x14000bfc7  mov     [rax+20h], r9
0x14000bfcb  mov     [rax+18h], r8d
0x14000bfcf  mov     [rax+10h], rdx
0x14000bfd3  mov     [rax+8], rcx
0x14000bfd7  push    rsi
0x14000bfd8  push    rdi
0x14000bfd9  push    r12
0x14000bfdb  push    r13
0x14000bfdd  push    r14
0x14000bfdf  push    r15
0x14000bfe1  sub     rsp, 98h
0x14000bfe8  mov     r14, r9
0x14000bfeb  mov     r13, rdx
0x14000bfee  mov     rdi, [rdx+0B8h]
0x14000bff5  mov     [rsp+0C8h+var_80], rdi
0x14000bffa  mov     [rsp+0C8h+var_50], rdi
0x14000bfff  mov     r12d, [rdi+8]
0x14000c003  mov     dword ptr [rsp+0C8h+var_70], r12d
0x14000c008  mov     [rsp+0C8h+arg_10], r12d
0x14000c010  cmp     r12d, 30h ; '0'
0x14000c014  jnb     short loc_14000C022
0x14000c016  mov     dword ptr [r9], 0C0000206h
0x14000c01d  jmp     loc_14000C99F
0x14000c022  mov     rax, [rcx+20h]
0x14000c026  mov     rcx, [rax+28h]
0x14000c02a  xor     edx, edx; ChargeQuota
0x14000c02c  mov     cl, [rcx+4Ch]; StackSize
0x14000c02f  call    cs:__imp_IoAllocateIrp
0x14000c036  nop     dword ptr [rax+rax+00h]
0x14000c03b  mov     r15, rax
0x14000c03e  mov     [rsp+0C8h+var_60], rax
0x14000c043  test    rax, rax
0x14000c046  jnz     short loc_14000C054
0x14000c048  mov     dword ptr [r14], 0C000009Ah
0x14000c04f  jmp     loc_14000C99F
0x14000c054  mov     [rsp+0C8h+var_48], rdi
0x14000c05c  mov     r8d, 6274534Bh; Tag
0x14000c062  mov     rdx, r12; NumberOfBytes
0x14000c065  mov     ecx, 600h; PoolType
0x14000c06a  call    cs:__imp_ExAllocatePoolWithTag
0x14000c071  nop     dword ptr [rax+rax+00h]
0x14000c076  mov     rdi, rax
0x14000c079  cmp     cs:ExPoolZeroingNativelySupported, 0
0x14000c080  jnz     short loc_14000C094
0x14000c082  test    rax, rax
0x14000c085  jz      short loc_14000C094
0x14000c087  mov     r8, r12; Size
0x14000c08a  xor     edx, edx; Val
0x14000c08c  mov     rcx, rax; void *
0x14000c08f  call    memset
0x14000c094  mov     rax, rdi
0x14000c097  mov     [rsp+0C8h+var_90], rax
0x14000c09c  mov     [rsp+0C8h+var_58], rax
0x14000c0a1  test    rdi, rdi
0x14000c0a4  jnz     short loc_14000C0B7
0x14000c0a6  mov     rcx, r15; Irp
0x14000c0a9  call    cs:__imp_IoFreeIrp
0x14000c0b0  nop     dword ptr [rax+rax+00h]
0x14000c0b5  jmp     short loc_14000C048
0x14000c0b7  call    Feature_Servicing_KSTHUNK_UMA__private_IsEnabledDeviceUsageNoInline
0x14000c0bc  mov     rcx, [rsp+0C8h+var_48]
0x14000c0c4  mov     ecx, [rcx+18h]
0x14000c0c7  test    eax, eax
0x14000c0c9  jz      short loc_14000C10D
0x14000c0cb  cmp     ecx, 2F8013h
0x14000c0d1  jz      short loc_14000C0EC
0x14000c0d3  mov     r8d, 1; Alignment
0x14000c0d9  mov     rdx, r12; Length
0x14000c0dc  mov     rcx, [r13+70h]; Address
0x14000c0e0  call    cs:__imp_ProbeForWrite
0x14000c0e7  nop     dword ptr [rax+rax+00h]
0x14000c0ec  mov     rdx, [r13+70h]; Src
0x14000c0f0  mov     r8, r12; Size
0x14000c0f3  mov     rcx, [rsp+0C8h+var_90]; void *
0x14000c0f8  cmp     byte ptr [r13+40h], 0
0x14000c0fd  jz      short loc_14000C106
0x14000c0ff  call    RtlCopyFromUser
0x14000c104  jmp     short loc_14000C150
0x14000c106  call    RtlCopyVolatileMemory
0x14000c10b  jmp     short loc_14000C150
0x14000c10d  mov     rax, [r13+70h]
0x14000c111  mov     r8d, 1; Alignment
0x14000c117  mov     rdx, r12; Length
0x14000c11a  cmp     ecx, 2F8013h
0x14000c120  mov     rcx, rax; Address
0x14000c123  jnz     short loc_14000C133
0x14000c125  call    cs:__imp_ProbeForRead
0x14000c12c  nop     dword ptr [rax+rax+00h]
0x14000c131  jmp     short loc_14000C13F
0x14000c133  call    cs:__imp_ProbeForWrite
0x14000c13a  nop     dword ptr [rax+rax+00h]
0x14000c13f  mov     r8, r12; Size
0x14000c142  mov     rdx, [r13+70h]; Src
0x14000c146  mov     rcx, [rsp+0C8h+var_90]; void *
0x14000c14b  call    memmove
0x14000c150  mov     r8, [rsp+0C8h+var_80]
0x14000c155  jmp     short loc_14000C193
0x14000c157  mov     r14, [rsp+0C8h+arg_18]
0x14000c15f  mov     [r14], eax
0x14000c162  mov     r13, [rsp+0C8h+arg_8]
0x14000c16a  mov     r12d, [rsp+0C8h+arg_10]
0x14000c172  mov     dword ptr [rsp+0C8h+var_70], r12d
0x14000c177  mov     r15, [rsp+0C8h+var_60]
0x14000c17c  mov     rcx, [rsp+0C8h+var_58]
0x14000c181  mov     [rsp+0C8h+var_90], rcx
0x14000c186  mov     rdi, rcx
0x14000c189  mov     r8, [rsp+0C8h+var_50]
0x14000c18e  mov     [rsp+0C8h+var_80], r8
0x14000c193  mov     [r13+18h], rdi
0x14000c197  or      dword ptr [r13+10h], 30h
0x14000c19c  cmp     dword ptr [r8+18h], 2F4017h
0x14000c1a4  jnz     short loc_14000C1AB
0x14000c1a6  or      dword ptr [r13+10h], 40h
0x14000c1ab  mov     [rsp+0C8h+var_68], r12d
0x14000c1b0  xor     edx, edx
0x14000c1b2  mov     [rsp+0C8h+var_78], edx
0x14000c1b6  mov     [rsp+0C8h+var_64], edx
0x14000c1ba  xor     ecx, ecx
0x14000c1bc  mov     [rsp+0C8h+var_98], ecx
0x14000c1c0  mov     [rsp+0C8h+var_88], ecx
0x14000c1c4  mov     rax, [rsp+0C8h+arg_0]
0x14000c1cc  mov     sil, [rax+74h]
0x14000c1d0  mov     byte ptr [rsp+0C8h+arg_10], sil
0x14000c1d8  cmp     [r14], ecx
0x14000c1db  jl      loc_14000C539
0x14000c1e1  test    r12d, r12d
0x14000c1e4  jz      loc_14000C476
0x14000c1ea  mov     ecx, [rdi]
0x14000c1ec  cmp     r12d, ecx
0x14000c1ef  jb      loc_14000C476
0x14000c1f5  cmp     ecx, 30h ; '0'
0x14000c1f8  jb      loc_14000C465
0x14000c1fe  test    dword ptr [rdi+2Ch], 1000h
0x14000c205  jz      short loc_14000C213
0x14000c207  cmp     ecx, 88h
0x14000c20d  jb      loc_14000C465
0x14000c213  inc     edx
0x14000c215  mov     [rsp+0C8h+var_78], edx
0x14000c219  mov     [rsp+0C8h+var_64], edx
0x14000c21d  mov     eax, [rdi+28h]
0x14000c220  test    eax, eax
0x14000c222  jz      loc_14000C454
0x14000c228  mov     edx, [rdi+20h]; Length
0x14000c22b  mov     ecx, eax; Address
0x14000c22d  mov     r8d, 1; Alignment
0x14000c233  call    cs:__imp_ProbeForWrite
0x14000c23a  nop     dword ptr [rax+rax+00h]
0x14000c23f  mov     edx, [rdi+20h]; Length
0x14000c242  cmp     [rdi+24h], edx
0x14000c245  jbe     short loc_14000C258
0x14000c247  mov     ecx, 0C0000206h; Status
0x14000c24c  call    cs:__imp_ExRaiseStatus
0x14000c258  test    sil, sil
0x14000c25b  jz      short loc_14000C265
0x14000c25d  mov     eax, dword ptr [rsp+0C8h+var_70]
0x14000c261  cmp     eax, [rdi]
0x14000c263  jbe     short loc_14000C26C
0x14000c265  and     dword ptr [rdi+2Ch], 0FFFE7FFFh
0x14000c26c  test    dword ptr [rdi+2Ch], 18000h
0x14000c273  jnz     short loc_14000C2AB
0x14000c275  cmp     qword ptr [r15+8], 0
0x14000c27a  setnz   r8b; SecondaryBuffer
0x14000c27e  mov     ecx, [rdi+28h]; VirtualAddress
0x14000c281  mov     [rsp+0C8h+Irp], r15; Irp
0x14000c286  mov     r9b, 1; ChargeQuota
0x14000c289  call    cs:__imp_IoAllocateMdl
0x14000c290  nop     dword ptr [rax+rax+00h]
0x14000c295  test    rax, rax
0x14000c298  jnz     short loc_14000C2AB
0x14000c29a  mov     ecx, 0C000009Ah; Status
0x14000c29f  call    cs:__imp_ExRaiseStatus
0x14000c2ab  mov     rcx, rdi; struct _KSSTREAM_HEADER32 *
0x14000c2ae  call    ?GetMetadataBuffer32@@YAPEAUKSSTREAM_METADATA_INFO32@@PEAU_KSSTREAM_HEADER32@@@Z; GetMetadataBuffer32(_KSSTREAM_HEADER32 *)
0x14000c2b3  mov     rsi, rax
0x14000c2b6  test    rax, rax
0x14000c2b9  jz      loc_14000C348
0x14000c2bf  mov     ecx, [rax+8]; Address
0x14000c2c2  test    ecx, ecx
0x14000c2c4  jz      short loc_14000C337
0x14000c2c6  mov     eax, [rax]
0x14000c2c8  test    eax, eax
0x14000c2ca  jz      short loc_14000C337
0x14000c2cc  mov     edx, eax; Length
0x14000c2ce  mov     r8d, 1; Alignment
0x14000c2d4  call    cs:__imp_ProbeForWrite
0x14000c2db  nop     dword ptr [rax+rax+00h]
0x14000c2e0  mov     edx, [rsi]; Length
0x14000c2e2  cmp     [rsi+4], edx
0x14000c2e5  jbe     short loc_14000C2F8
0x14000c2e7  mov     ecx, 0C0000206h; Status
0x14000c2ec  call    cs:__imp_ExRaiseStatus
0x14000c2f8  test    dword ptr [rdi+2Ch], 18000h
0x14000c2ff  jnz     short loc_14000C348
0x14000c301  cmp     qword ptr [r15+8], 0
0x14000c306  setnz   r8b; SecondaryBuffer
0x14000c30a  mov     ecx, [rsi+8]; VirtualAddress
0x14000c30d  mov     [rsp+0C8h+Irp], r15; Irp
0x14000c312  mov     r9b, 1; ChargeQuota
0x14000c315  call    cs:__imp_IoAllocateMdl
0x14000c31c  nop     dword ptr [rax+rax+00h]
0x14000c321  test    rax, rax
0x14000c324  jnz     short loc_14000C348
0x14000c326  mov     ecx, 0C000009Ah; Status
0x14000c32b  call    cs:__imp_ExRaiseStatus
0x14000c337  mov     ecx, 0C000000Dh; Status
0x14000c33c  call    cs:__imp_ExRaiseStatus
0x14000c348  xor     ecx, ecx
0x14000c34a  mov     esi, [rdi]
0x14000c34c  cmp     esi, 30h ; '0'
0x14000c34f  jbe     short loc_14000C3C1
0x14000c351  mov     rax, [rsp+0C8h+arg_0]
0x14000c359  mov     rcx, [rax+68h]
0x14000c35d  test    rcx, rcx
0x14000c360  jz      short loc_14000C398
0x14000c362  mov     rax, [rcx]
0x14000c365  mov     rax, [rax+20h]
0x14000c369  xor     r8d, r8d
0x14000c36c  mov     edx, [rdi+2Ch]
0x14000c36f  call    _guard_dispatch_icall
0x14000c374  mov     ecx, eax
0x14000c376  lea     rax, [rsi-30h]
0x14000c37a  cmp     rcx, rax
0x14000c37d  jz      short loc_14000C390
0x14000c37f  mov     ecx, 0C000000Dh; Status
0x14000c384  call    cs:__imp_ExRaiseStatus
0x14000c390  mov     rax, [rsp+0C8h+arg_0]
0x14000c398  mov     r8d, [rdi]
0x14000c39b  sub     r8d, 30h ; '0'; unsigned int
0x14000c39f  mov     edx, [rdi+2Ch]; unsigned int
0x14000c3a2  mov     rcx, rax; this
0x14000c3a5  call    ?GetExtendedHeaderSize@CKSThunkPin@@AEAAKKK@Z; CKSThunkPin::GetExtendedHeaderSize(ulong,ulong)
0x14000c3aa  mov     ecx, eax
0x14000c3ac  test    eax, eax
0x14000c3ae  jnz     short loc_14000C3C1
0x14000c3b0  mov     ecx, 0C000000Dh; Status
0x14000c3b5  call    cs:__imp_ExRaiseStatus
0x14000c3c1  mov     edx, [rsp+0C8h+var_98]
0x14000c3c5  lea     eax, [rdx+38h]
0x14000c3c8  cmp     eax, edx
0x14000c3ca  jb      short loc_14000C43B
0x14000c3cc  mov     [rsp+0C8h+var_88], eax
0x14000c3d0  add     ecx, eax
0x14000c3d2  mov     [rsp+0C8h+var_98], ecx
0x14000c3d6  cmp     ecx, eax
0x14000c3d8  jb      short loc_14000C422
0x14000c3da  mov     [rsp+0C8h+var_88], ecx
0x14000c3de  mov     eax, [rdi]
0x14000c3e0  cmp     r12d, eax
0x14000c3e3  jb      short loc_14000C409
0x14000c3e5  sub     r12d, eax
0x14000c3e8  mov     [rsp+0C8h+var_68], r12d
0x14000c3ed  add     rdi, rax
0x14000c3f0  mov     [rsp+0C8h+var_40], rdi
0x14000c3f8  mov     sil, byte ptr [rsp+0C8h+arg_10]
0x14000c400  mov     edx, [rsp+0C8h+var_78]
0x14000c404  jmp     loc_14000C1E1
0x14000c409  mov     [rsp+0C8h+var_68], 0FFFFFFFFh
0x14000c411  mov     ecx, 0C000000Dh; Status
0x14000c416  call    cs:__imp_ExRaiseStatus
0x14000c422  mov     [rsp+0C8h+var_88], 0FFFFFFFFh
0x14000c42a  mov     ecx, 0C000000Dh; Status
0x14000c42f  call    cs:__imp_ExRaiseStatus
0x14000c43b  mov     [rsp+0C8h+var_88], 0FFFFFFFFh
0x14000c443  mov     ecx, 0C000000Dh; Status
0x14000c448  call    cs:__imp_ExRaiseStatus
0x14000c454  mov     ecx, 0C000000Dh; Status
0x14000c459  call    cs:__imp_ExRaiseStatus
0x14000c465  mov     ecx, 0C000000Dh; Status
0x14000c46a  call    cs:__imp_ExRaiseStatus
0x14000c476  mov     rdi, [r15+8]
0x14000c47a  test    rdi, rdi
0x14000c47d  jz      short loc_14000C4F2
0x14000c47f  mov     r8d, 1; Operation
0x14000c485  mov     dl, [r13+40h]; AccessMode
0x14000c489  mov     rcx, rdi; MemoryDescriptorList
0x14000c48c  call    cs:__imp_MmProbeAndLockPages
0x14000c493  nop     dword ptr [rax+rax+00h]
0x14000c498  mov     eax, 2000h
0x14000c49d  or      [rdi+0Ah], ax
0x14000c4a1  movzx   eax, word ptr [rdi+0Ah]
0x14000c4a5  test    al, 5
0x14000c4a7  jz      short loc_14000C4AF
0x14000c4a9  mov     rax, [rdi+18h]
0x14000c4ad  jmp     short loc_14000C4D7
0x14000c4af  mov     [rsp+0C8h+Priority], 40000000h; Priority
0x14000c4b7  mov     dword ptr [rsp+0C8h+Irp], 0; BugCheckOnFailure
0x14000c4bf  xor     r9d, r9d; RequestedAddress
0x14000c4c2  xor     edx, edx; AccessMode
0x14000c4c4  lea     r8d, [r9+1]; CacheType
0x14000c4c8  mov     rcx, rdi; MemoryDescriptorList
0x14000c4cb  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000c4d2  nop     dword ptr [rax+rax+00h]
0x14000c4d7  test    rax, rax
0x14000c4da  jnz     short loc_14000C4ED
0x14000c4dc  mov     ecx, 0C000009Ah; Status
0x14000c4e1  call    cs:__imp_ExRaiseStatus
0x14000c4ed  mov     rdi, [rdi]
0x14000c4f0  jmp     short loc_14000C47A
0x14000c4f2  mov     ecx, [rsp+0C8h+var_98]
  ... truncated ...
```
