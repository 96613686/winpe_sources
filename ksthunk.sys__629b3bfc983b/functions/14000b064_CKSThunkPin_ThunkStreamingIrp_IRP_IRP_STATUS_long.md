# CKSThunkPin::ThunkStreamingIrp(_IRP *,_IRP_STATUS,long *)

- ea: `0x14000b064`
- end: `0x14000ba2a`
- name: `?ThunkStreamingIrp@CKSThunkPin@@AEAA?AW4_IRP_DISPOSITION@@PEAU_IRP@@W4_IRP_STATUS@@PEAJ@Z`
- size: `2502`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140002380`

## callees

- `0x1400010f4`
- `0x140002430`
- `0x140002474`
- `0x140002490`
- `0x1400036c0`
- `0x140003770`
- `0x1400037c0`
- `0x140003ac0`
- `0x14000b064`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000b106`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000b5c4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000b106`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000b5c4`
- `ntoskrnl!IofCallDriver` at `0x14000b8e5`
- `ntoskrnl!IofCallDriver` at `0x14000b8e5`
- `ntoskrnl!MmUnlockPages` at `0x14000b9c7`
- `ntoskrnl!MmUnlockPages` at `0x14000b9c7`
- `ntoskrnl!MmProbeAndLockPages` at `0x14000b4df`
- `ntoskrnl!MmProbeAndLockPages` at `0x14000b4df`
- `ntoskrnl!IoFreeIrp` at `0x14000b145`
- `ntoskrnl!IoFreeIrp` at `0x14000b9f5`
- `ntoskrnl!IoFreeIrp` at `0x14000b145`
- `ntoskrnl!IoFreeIrp` at `0x14000b9f5`
- `ntoskrnl!IoAllocateMdl` at `0x14000b2d3`
- `ntoskrnl!IoAllocateMdl` at `0x14000b365`
- `ntoskrnl!IoAllocateMdl` at `0x14000b2d3`
- `ntoskrnl!IoAllocateMdl` at `0x14000b365`
- `ntoskrnl!ProbeForWrite` at `0x14000b16e`
- `ntoskrnl!ProbeForWrite` at `0x14000b27d`
- `ntoskrnl!ProbeForWrite` at `0x14000b31e`
- `ntoskrnl!ProbeForWrite` at `0x14000b16e`
- `ntoskrnl!ProbeForWrite` at `0x14000b27d`
- `ntoskrnl!ProbeForWrite` at `0x14000b31e`
- `ntoskrnl!IoFreeMdl` at `0x14000b9dd`
- `ntoskrnl!IoFreeMdl` at `0x14000b9dd`
- `ntoskrnl!IoAllocateIrp` at `0x14000b0cf`
- `ntoskrnl!IoAllocateIrp` at `0x14000b0cf`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000b51e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000b73e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000b7f5`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000b51e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000b73e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000b7f5`
- `ntoskrnl!ExRaiseStatus` at `0x14000b296`
- `ntoskrnl!ExRaiseStatus` at `0x14000b2e9`
- `ntoskrnl!ExRaiseStatus` at `0x14000b33a`
- `ntoskrnl!ExRaiseStatus` at `0x14000b37b`
- `ntoskrnl!ExRaiseStatus` at `0x14000b38c`
- `ntoskrnl!ExRaiseStatus` at `0x14000b3d7`
- `ntoskrnl!ExRaiseStatus` at `0x14000b408`
- `ntoskrnl!ExRaiseStatus` at `0x14000b469`
- `ntoskrnl!ExRaiseStatus` at `0x14000b482`
- `ntoskrnl!ExRaiseStatus` at `0x14000b49b`
- `ntoskrnl!ExRaiseStatus` at `0x14000b4ac`
- `ntoskrnl!ExRaiseStatus` at `0x14000b4bd`
- `ntoskrnl!ExRaiseStatus` at `0x14000b534`
- `ntoskrnl!ExRaiseStatus` at `0x14000b296`
- `ntoskrnl!ExRaiseStatus` at `0x14000b2e9`
- `ntoskrnl!ExRaiseStatus` at `0x14000b33a`
- `ntoskrnl!ExRaiseStatus` at `0x14000b37b`
- `ntoskrnl!ExRaiseStatus` at `0x14000b38c`
- `ntoskrnl!ExRaiseStatus` at `0x14000b3d7`
- `ntoskrnl!ExRaiseStatus` at `0x14000b408`
- `ntoskrnl!ExRaiseStatus` at `0x14000b469`
- `ntoskrnl!ExRaiseStatus` at `0x14000b482`
- `ntoskrnl!ExRaiseStatus` at `0x14000b49b`
- `ntoskrnl!ExRaiseStatus` at `0x14000b4ac`
- `ntoskrnl!ExRaiseStatus` at `0x14000b4bd`
- `ntoskrnl!ExRaiseStatus` at `0x14000b534`
- `ntoskrnl!ExFreePool` at `0x14000ba09`
- `ntoskrnl!ExFreePool` at `0x14000ba09`

## pseudocode

```c
__int64 __fastcall CKSThunkPin::ThunkStreamingIrp(__int64 a1, __int64 a2, __int64 a3, int *a4)
{
  __int64 v6; // rdi
  SIZE_T v7; // r13
  PIRP Irp; // r14
  unsigned int *PoolWithTag; // rax
  unsigned int *v10; // rdi
  void *v11; // rax
  void *v12; // rdx
  int v13; // edx
  unsigned int v14; // ecx
  char v15; // r12
  unsigned int v16; // ecx
  unsigned int v17; // eax
  ULONG v18; // edx
  struct KSSTREAM_METADATA_INFO32 *MetadataBuffer32; // rax
  ULONG *v20; // r12
  volatile void *v21; // rcx
  unsigned int v22; // eax
  unsigned int ExtendedHeaderSize; // ecx
  __int64 v24; // r12
  CKSThunkPin *v25; // rax
  __int64 v26; // rcx
  unsigned int v27; // eax
  __int64 v28; // rax
  struct _MDL *i; // rdi
  PVOID MappedSystemVa; // rax
  char *v31; // r12
  char *v32; // r10
  int v33; // eax
  __int64 v34; // rdi
  char *v35; // rax
  struct _LIST_ENTRY *v36; // r8
  unsigned int v37; // r9d
  __int64 v38; // r11
  struct KSSTREAM_HEADER *v39; // r12
  PMDL MdlAddress; // rdi
  struct _KSSTREAM_HEADER32 *v41; // r9
  unsigned int v42; // eax
  unsigned int *v43; // r13
  ULONG v44; // ecx
  unsigned int v45; // eax
  int v46; // eax
  struct KSSTREAM_METADATA_INFO *MetadataBuffer64; // rax
  struct _KSSTREAM_HEADER32 *v48; // r9
  PVOID v49; // rax
  struct KSSTREAM_METADATA_INFO *v50; // rax
  ULONG *v51; // rdx
  struct KSSTREAM_METADATA_INFO *v52; // r13
  PVOID v53; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  struct _IO_STACK_LOCATION *v55; // rax
  int v57; // r13d
  unsigned int v58; // eax
  const void *v59; // rdx
  __int64 v60; // rcx
  int v61; // ecx
  PMDL v62; // rdi
  unsigned int v63; // [rsp+30h] [rbp-98h]
  __int64 v64; // [rsp+38h] [rbp-90h]
  struct _KSSTREAM_HEADER32 *v65; // [rsp+40h] [rbp-88h]
  int v66; // [rsp+48h] [rbp-80h]
  unsigned int v67; // [rsp+50h] [rbp-78h]
  char *v68; // [rsp+50h] [rbp-78h]
  __int64 v69; // [rsp+78h] [rbp-50h]
  char *v71; // [rsp+D8h] [rbp+10h]
  char v72; // [rsp+E0h] [rbp+18h]
  unsigned int v73; // [rsp+E0h] [rbp+18h]

  v6 = *(_QWORD *)(a2 + 184);
  v64 = v6;
  v7 = *(unsigned int *)(v6 + 8);
  v67 = v7;
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
  v69 = v6;
  PoolWithTag = (unsigned int *)ExAllocatePoolWithTag((POOL_TYPE)1536, v7, 0x6274534Bu);
  v10 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported && PoolWithTag )
    memset(PoolWithTag, 0, v7);
  v11 = v10;
  v65 = (struct _KSSTREAM_HEADER32 *)v10;
  if ( !v10 )
  {
    IoFreeIrp(Irp);
    goto LABEL_4;
  }
  if ( *(_DWORD *)(v69 + 24) != 3112979 )
  {
    ProbeForWrite(*(volatile void **)(a2 + 112), v7, 1u);
    v11 = v10;
  }
  v12 = *(void **)(a2 + 112);
  if ( *(_BYTE *)(a2 + 64) )
    RtlCopyFromUser(v11, v12, v7);
  else
    RtlCopyVolatileMemory(v11, v12, v7);
  *(_QWORD *)(a2 + 24) = v10;
  *(_DWORD *)(a2 + 16) |= 0x30u;
  if ( *(_DWORD *)(v64 + 24) == 3096599 )
    *(_DWORD *)(a2 + 16) |= 0x40u;
  v13 = 0;
  v66 = 0;
  v14 = 0;
  v63 = 0;
  v15 = *(_BYTE *)(a1 + 116);
  v72 = v15;
  if ( *a4 >= 0 )
  {
    while ( (_DWORD)v7 )
    {
      v16 = *v10;
      if ( (unsigned int)v7 < *v10 )
        break;
      if ( v16 < 0x30 || (v10[11] & 0x1000) != 0 && v16 < 0x88 )
        ExRaiseStatus(-1073741811);
      v66 = v13 + 1;
      v17 = v10[10];
      if ( !v17 )
        ExRaiseStatus(-1073741811);
      ProbeForWrite((volatile void *)v17, v10[8], 1u);
      v18 = v10[8];
      if ( v10[9] > v18 )
        ExRaiseStatus(-1073741306);
      if ( !v15 || v67 > *v10 )
        v10[11] &= 0xFFFE7FFF;
      if ( (v10[11] & 0x18000) == 0 && !IoAllocateMdl((PVOID)v10[10], v18, Irp->MdlAddress != 0, 1u, Irp) )
        ExRaiseStatus(-1073741670);
      MetadataBuffer32 = GetMetadataBuffer32((struct _KSSTREAM_HEADER32 *)v10);
      v20 = (ULONG *)MetadataBuffer32;
      if ( MetadataBuffer32 )
      {
        v21 = (volatile void *)*((unsigned int *)MetadataBuffer32 + 2);
        if ( !(_DWORD)v21 || (v22 = *(_DWORD *)MetadataBuffer32) == 0 )
          ExRaiseStatus(-1073741811);
        ProbeForWrite(v21, v22, 1u);
        if ( v20[1] > *v20 )
          ExRaiseStatus(-1073741306);
        if ( (v10[11] & 0x18000) == 0 && !IoAllocateMdl((PVOID)v20[2], *v20, Irp->MdlAddress != 0, 1u, Irp) )
          ExRaiseStatus(-1073741670);
      }
      ExtendedHeaderSize = 0;
      v24 = *v10;
      if ( (unsigned int)v24 > 0x30 )
      {
        v25 = (CKSThunkPin *)a1;
        v26 = *(_QWORD *)(a1 + 104);
        if ( v26 )
        {
          if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v26 + 32LL))(v26, v10[11], 0) != v24 - 48 )
            ExRaiseStatus(-1073741811);
          v25 = (CKSThunkPin *)a1;
        }
        ExtendedHeaderSize = CKSThunkPin::GetExtendedHeaderSize(v25, v10[11], *v10 - 48);
        if ( !ExtendedHeaderSize )
          ExRaiseStatus(-1073741811);
      }
      v27 = v63 + 56;
      if ( v63 + 56 < v63 )
        ExRaiseStatus(-1073741811);
      v63 = v27 + ExtendedHeaderSize;
      if ( v27 + ExtendedHeaderSize < v27 )
        ExRaiseStatus(-1073741811);
      v28 = *v10;
      if ( (unsigned int)v7 < (unsigned int)v28 )
        ExRaiseStatus(-1073741811);
      LODWORD(v7) = v7 - v28;
      v10 = (unsigned int *)((char *)v10 + v28);
      v15 = v72;
      v13 = v66;
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
    v14 = v63;
  }
  v31 = 0;
  v32 = 0;
  v33 = *a4;
  if ( *a4 < 0 )
    goto LABEL_102;
  if ( (_DWORD)v7 )
  {
    *a4 = -1073741811;
    v33 = -1073741811;
  }
  if ( v33 < 0 )
  {
LABEL_102:
    v36 = (struct _LIST_ENTRY *)a1;
    goto LABEL_103;
  }
  v34 = v14;
  v35 = (char *)ExAllocatePoolWithTag((POOL_TYPE)1536, v14 + 16LL, 0x6373534Bu);
  v31 = v35;
  v71 = v35;
  if ( !ExPoolZeroingNativelySupported && v35 )
    memset(v35, 0, v34 + 16);
  v32 = v31 + 16;
  v68 = v31 + 16;
  v36 = (struct _LIST_ENTRY *)a1;
  v37 = v63;
  v38 = v64;
  if ( !v31 )
  {
    *a4 = -1073741670;
    goto LABEL_104;
  }
  *(_DWORD *)v31 = *(_DWORD *)(v64 + 24);
  *((_DWORD *)v31 + 1) = v63;
  *((_QWORD *)v31 + 1) = a1;
  v39 = (struct KSSTREAM_HEADER *)(v31 + 16);
  MdlAddress = Irp->MdlAddress;
  if ( !v66 )
  {
    v31 = v71;
    goto LABEL_104;
  }
  v41 = v65;
  do
  {
    v42 = 0;
    v73 = 0;
    v43 = (unsigned int *)((char *)v41 + 44);
    if ( *(_DWORD *)v41 > 0x30u )
    {
      v42 = CKSThunkPin::GetExtendedHeaderSize((CKSThunkPin *)a1, *v43, *(_DWORD *)v41 - 48);
      v73 = v42;
      v41 = v65;
    }
    v39->Size = v42 + 56;
    v39->TypeSpecificFlags = *((_DWORD *)v41 + 1);
    v39->PresentationTime.Time = *((_QWORD *)v41 + 1);
    v39->PresentationTime.Numerator = *((_DWORD *)v41 + 4);
    v39->PresentationTime.Denominator = *((_DWORD *)v41 + 5);
    v39->Duration = *((_QWORD *)v41 + 3);
    v44 = *((_DWORD *)v41 + 8);
    v39->FrameExtent = v44;
    v39->DataUsed = *((_DWORD *)v41 + 9);
    v45 = *v43;
    v39->OptionsFlags = *v43;
    v46 = v45 & 0x8000;
    if ( !MdlAddress && !v46 )
    {
      MetadataBuffer64 = GetMetadataBuffer64(v39);
      v39->Data = 0;
      if ( MetadataBuffer64 )
        MetadataBuffer64->Data = 0;
      goto LABEL_107;
    }
    if ( !v44 )
    {
      *a4 = -1073741811;
      goto LABEL_101;
    }
    if ( !v46 )
    {
      if ( (MdlAddress->MdlFlags & 5) != 0 )
      {
        v49 = MdlAddress->MappedSystemVa;
      }
      else
      {
        v49 = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u);
        v41 = v65;
      }
      v39->Data = v49;
      if ( v49 )
        goto LABEL_90;
LABEL_100:
      *a4 = -1073741670;
LABEL_101:
      v31 = v71;
      v32 = v68;
      goto LABEL_102;
    }
    v39->Data = (PVOID)*((unsigned int *)v41 + 10);
LABEL_90:
    if ( GetMetadataBuffer32(v41) )
    {
      if ( MdlAddress && (MdlAddress = MdlAddress->Next) != 0 || (v39->OptionsFlags & 0x8000) != 0 )
      {
        v50 = GetMetadataBuffer64(v39);
        v52 = v50;
        if ( v50 )
        {
          v50->BufferSize = *v51;
          v50->Flags = v51[4];
          v50->Reserved = v51[5];
          v50->UsedSize = v51[1];
          v50->SystemVa = 0;
          if ( (*((_DWORD *)v48 + 11) & 0x18000) != 0 )
          {
            v50->Data = (PVOID)v51[2];
          }
          else
          {
            if ( (MdlAddress->MdlFlags & 5) != 0 )
            {
              v53 = MdlAddress->MappedSystemVa;
            }
            else
            {
              v53 = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u);
              v48 = v65;
            }
            v52->Data = v53;
            if ( !v53 )
              goto LABEL_100;
          }
        }
      }
    }
LABEL_107:
    v57 = 0;
    v58 = *(_DWORD *)v48 - 48;
    v36 = (struct _LIST_ENTRY *)a1;
    if ( *(_DWORD *)v48 != 48 )
    {
      v59 = (char *)v48 + 48;
      v60 = *(_QWORD *)(a1 + 104);
      if ( v60 )
      {
        (*(void (__fastcall **)(__int64, const void *, struct KSSTREAM_HEADER *))(*(_QWORD *)v60 + 40LL))(
          v60,
          v59,
          v39 + 1);
        goto LABEL_113;
      }
      if ( v58 == v73 )
      {
        memmove(&v39[1], v59, v58);
LABEL_113:
        v36 = (struct _LIST_ENTRY *)a1;
        v48 = v65;
        goto LABEL_114;
      }
      v57 = -1073741811;
    }
LABEL_114:
    *a4 = v57;
    if ( v57 < 0 )
      break;
    v61 = --v66;
    v39 = (struct KSSTREAM_HEADER *)((char *)v39 + v39->Size);
    v41 = (struct _KSSTREAM_HEADER32 *)((char *)v48 + *(unsigned int *)v48);
    v65 = v41;
    if ( MdlAddress )
      MdlAddress = MdlAddress->Next;
  }
  while ( v61 );
  v31 = v71;
  v32 = v68;
LABEL_103:
  v38 = v64;
  v37 = v63;
LABEL_104:
  if ( *a4 >= 0 )
  {
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].DeviceObject = (PDEVICE_OBJECT)v36[2].Flink[3].Blink;
    CurrentStackLocation[-1].FileObject = *(PFILE_OBJECT *)(v69 + 48);
    CurrentStackLocation[-1].MajorFunction = 14;
    CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = *(_DWORD *)(v38 + 24);
    CurrentStackLocation[-1].Parameters.Create.Options = 0;
    CurrentStackLocation[-1].Parameters.Read.Length = v37;
    Irp->UserBuffer = v32;
    Irp->RequestorMode = 0;
    Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = (struct _LIST_ENTRY *)KeGetCurrentThread();
    Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink = v36;
    *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
    *(_QWORD *)(a2 + 120) = Irp;
    *(_QWORD *)(a2 + 128) = v36;
    *(_QWORD *)(a2 + 136) = 0;
    v55 = Irp->Tail.Overlay.CurrentStackLocation;
    v55[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)CKSThunkPin::ThunkStreamingIrpCompletion;
    v55[-1].Context = (PVOID)a2;
    v55[-1].Control = -32;
    _InterlockedExchange64((volatile __int64 *)(a2 + 104), (__int64)CKSThunkPin::CancelStreamingIrp);
    IofCallDriver((PDEVICE_OBJECT)v36[2].Flink[3].Blink, Irp);
    return 2;
  }
  while ( 1 )
  {
    v62 = Irp->MdlAddress;
    if ( !v62 )
      break;
    if ( (v62->MdlFlags & 2) != 0 )
      MmUnlockPages(Irp->MdlAddress);
    Irp->MdlAddress = v62->Next;
    IoFreeMdl(v62);
  }
  IoFreeIrp(Irp);
  if ( v31 )
    ExFreePool(v31);
  return 0;
}

```

## disassembly

```asm
0x14000b064  mov     rax, rsp
0x14000b067  mov     [rax+20h], r9
0x14000b06b  mov     [rax+18h], r8d
0x14000b06f  mov     [rax+10h], rdx
0x14000b073  mov     [rax+8], rcx
0x14000b077  push    rsi
0x14000b078  push    rdi
0x14000b079  push    r12
0x14000b07b  push    r13
0x14000b07d  push    r14
0x14000b07f  push    r15
0x14000b081  sub     rsp, 98h
0x14000b088  mov     rsi, r9
0x14000b08b  mov     r15, rdx
0x14000b08e  mov     rdi, [rdx+0B8h]
0x14000b095  mov     [rsp+0C8h+var_90], rdi
0x14000b09a  mov     [rsp+0C8h+var_58], rdi
0x14000b09f  mov     r13d, [rdi+8]
0x14000b0a3  mov     dword ptr [rsp+0C8h+var_78], r13d
0x14000b0a8  mov     [rsp+0C8h+arg_10], r13d
0x14000b0b0  cmp     r13d, 30h ; '0'
0x14000b0b4  jnb     short loc_14000B0C2
0x14000b0b6  mov     dword ptr [r9], 0C0000206h
0x14000b0bd  jmp     loc_14000BA15
0x14000b0c2  mov     rax, [rcx+20h]
0x14000b0c6  mov     rcx, [rax+28h]
0x14000b0ca  xor     edx, edx; ChargeQuota
0x14000b0cc  mov     cl, [rcx+4Ch]; StackSize
0x14000b0cf  call    cs:__imp_IoAllocateIrp
0x14000b0d6  nop     dword ptr [rax+rax+00h]
0x14000b0db  mov     r14, rax
0x14000b0de  mov     [rsp+0C8h+var_68], rax
0x14000b0e3  test    rax, rax
0x14000b0e6  jnz     short loc_14000B0F3
0x14000b0e8  mov     dword ptr [rsi], 0C000009Ah
0x14000b0ee  jmp     loc_14000BA15
0x14000b0f3  mov     [rsp+0C8h+var_50], rdi
0x14000b0f8  mov     r8d, 6274534Bh; Tag
0x14000b0fe  mov     rdx, r13; NumberOfBytes
0x14000b101  mov     ecx, 600h; PoolType
0x14000b106  call    cs:__imp_ExAllocatePoolWithTag
0x14000b10d  nop     dword ptr [rax+rax+00h]
0x14000b112  mov     rdi, rax
0x14000b115  cmp     cs:ExPoolZeroingNativelySupported, 0
0x14000b11c  jnz     short loc_14000B130
0x14000b11e  test    rax, rax
0x14000b121  jz      short loc_14000B130
0x14000b123  mov     r8, r13; Size
0x14000b126  xor     edx, edx; Val
0x14000b128  mov     rcx, rax; void *
0x14000b12b  call    memset
0x14000b130  mov     rax, rdi
0x14000b133  mov     [rsp+0C8h+var_88], rax
0x14000b138  mov     [rsp+0C8h+var_60], rax
0x14000b13d  test    rdi, rdi
0x14000b140  jnz     short loc_14000B153
0x14000b142  mov     rcx, r14; Irp
0x14000b145  call    cs:__imp_IoFreeIrp
0x14000b14c  nop     dword ptr [rax+rax+00h]
0x14000b151  jmp     short loc_14000B0E8
0x14000b153  mov     rcx, [rsp+0C8h+var_50]
0x14000b158  cmp     dword ptr [rcx+18h], 2F8013h
0x14000b15f  jz      short loc_14000B17F
0x14000b161  mov     r8d, 1; Alignment
0x14000b167  mov     rdx, r13; Length
0x14000b16a  mov     rcx, [r15+70h]; Address
0x14000b16e  call    cs:__imp_ProbeForWrite
0x14000b175  nop     dword ptr [rax+rax+00h]
0x14000b17a  mov     rax, [rsp+0C8h+var_88]
0x14000b17f  mov     rdx, [r15+70h]; Src
0x14000b183  mov     r8, r13; Size
0x14000b186  mov     rcx, rax; void *
0x14000b189  cmp     byte ptr [r15+40h], 0
0x14000b18e  jz      short loc_14000B197
0x14000b190  call    RtlCopyFromUser
0x14000b195  jmp     short loc_14000B19C
0x14000b197  call    RtlCopyVolatileMemory
0x14000b19c  mov     r8, [rsp+0C8h+var_90]
0x14000b1a1  jmp     short loc_14000B1DE
0x14000b1a3  mov     rsi, [rsp+0C8h+arg_18]
0x14000b1ab  mov     [rsi], eax
0x14000b1ad  mov     r15, [rsp+0C8h+arg_8]
0x14000b1b5  mov     r13d, [rsp+0C8h+arg_10]
0x14000b1bd  mov     dword ptr [rsp+0C8h+var_78], r13d
0x14000b1c2  mov     r14, [rsp+0C8h+var_68]
0x14000b1c7  mov     rax, [rsp+0C8h+var_60]
0x14000b1cc  mov     [rsp+0C8h+var_88], rax
0x14000b1d1  mov     rdi, rax
0x14000b1d4  mov     r8, [rsp+0C8h+var_58]
0x14000b1d9  mov     [rsp+0C8h+var_90], r8
0x14000b1de  mov     [r15+18h], rdi
0x14000b1e2  or      dword ptr [r15+10h], 30h
0x14000b1e7  cmp     dword ptr [r8+18h], 2F4017h
0x14000b1ef  jnz     short loc_14000B1F6
0x14000b1f1  or      dword ptr [r15+10h], 40h
0x14000b1f6  mov     [rsp+0C8h+var_70], r13d
0x14000b1fb  xor     edx, edx
0x14000b1fd  mov     [rsp+0C8h+var_80], edx
0x14000b201  mov     [rsp+0C8h+var_6C], edx
0x14000b205  xor     ecx, ecx
0x14000b207  mov     [rsp+0C8h+var_98], ecx
0x14000b20b  mov     [rsp+0C8h+var_94], ecx
0x14000b20f  mov     rax, [rsp+0C8h+arg_0]
0x14000b217  mov     r12b, [rax+74h]
0x14000b21b  mov     byte ptr [rsp+0C8h+arg_10], r12b
0x14000b223  cmp     [rsi], ecx
0x14000b225  jl      loc_14000B58B
0x14000b22b  test    r13d, r13d
0x14000b22e  jz      loc_14000B4C9
0x14000b234  mov     ecx, [rdi]
0x14000b236  cmp     r13d, ecx
0x14000b239  jb      loc_14000B4C9
0x14000b23f  cmp     ecx, 30h ; '0'
0x14000b242  jb      loc_14000B4B8
0x14000b248  test    dword ptr [rdi+2Ch], 1000h
0x14000b24f  jz      short loc_14000B25D
0x14000b251  cmp     ecx, 88h
0x14000b257  jb      loc_14000B4B8
0x14000b25d  inc     edx
0x14000b25f  mov     [rsp+0C8h+var_80], edx
0x14000b263  mov     [rsp+0C8h+var_6C], edx
0x14000b267  mov     eax, [rdi+28h]
0x14000b26a  test    eax, eax
0x14000b26c  jz      loc_14000B4A7
0x14000b272  mov     edx, [rdi+20h]; Length
0x14000b275  mov     ecx, eax; Address
0x14000b277  mov     r8d, 1; Alignment
0x14000b27d  call    cs:__imp_ProbeForWrite
0x14000b284  nop     dword ptr [rax+rax+00h]
0x14000b289  mov     edx, [rdi+20h]; Length
0x14000b28c  cmp     [rdi+24h], edx
0x14000b28f  jbe     short loc_14000B2A2
0x14000b291  mov     ecx, 0C0000206h; Status
0x14000b296  call    cs:__imp_ExRaiseStatus
0x14000b2a2  test    r12b, r12b
0x14000b2a5  jz      short loc_14000B2AF
0x14000b2a7  mov     eax, dword ptr [rsp+0C8h+var_78]
0x14000b2ab  cmp     eax, [rdi]
0x14000b2ad  jbe     short loc_14000B2B6
0x14000b2af  and     dword ptr [rdi+2Ch], 0FFFE7FFFh
0x14000b2b6  test    dword ptr [rdi+2Ch], 18000h
0x14000b2bd  jnz     short loc_14000B2F5
0x14000b2bf  cmp     qword ptr [r14+8], 0
0x14000b2c4  setnz   r8b; SecondaryBuffer
0x14000b2c8  mov     ecx, [rdi+28h]; VirtualAddress
0x14000b2cb  mov     [rsp+0C8h+Irp], r14; Irp
0x14000b2d0  mov     r9b, 1; ChargeQuota
0x14000b2d3  call    cs:__imp_IoAllocateMdl
0x14000b2da  nop     dword ptr [rax+rax+00h]
0x14000b2df  test    rax, rax
0x14000b2e2  jnz     short loc_14000B2F5
0x14000b2e4  mov     ecx, 0C000009Ah; Status
0x14000b2e9  call    cs:__imp_ExRaiseStatus
0x14000b2f5  mov     rcx, rdi; struct _KSSTREAM_HEADER32 *
0x14000b2f8  call    ?GetMetadataBuffer32@@YAPEAUKSSTREAM_METADATA_INFO32@@PEAU_KSSTREAM_HEADER32@@@Z; GetMetadataBuffer32(_KSSTREAM_HEADER32 *)
0x14000b2fd  mov     r12, rax
0x14000b300  test    rax, rax
0x14000b303  jz      loc_14000B398
0x14000b309  mov     ecx, [rax+8]; Address
0x14000b30c  test    ecx, ecx
0x14000b30e  jz      short loc_14000B387
0x14000b310  mov     eax, [rax]
0x14000b312  test    eax, eax
0x14000b314  jz      short loc_14000B387
0x14000b316  mov     edx, eax; Length
0x14000b318  mov     r8d, 1; Alignment
0x14000b31e  call    cs:__imp_ProbeForWrite
0x14000b325  nop     dword ptr [rax+rax+00h]
0x14000b32a  mov     edx, [r12]; Length
0x14000b32e  cmp     [r12+4], edx
0x14000b333  jbe     short loc_14000B346
0x14000b335  mov     ecx, 0C0000206h; Status
0x14000b33a  call    cs:__imp_ExRaiseStatus
0x14000b346  test    dword ptr [rdi+2Ch], 18000h
0x14000b34d  jnz     short loc_14000B398
0x14000b34f  cmp     qword ptr [r14+8], 0
0x14000b354  setnz   r8b; SecondaryBuffer
0x14000b358  mov     ecx, [r12+8]; VirtualAddress
0x14000b35d  mov     [rsp+0C8h+Irp], r14; Irp
0x14000b362  mov     r9b, 1; ChargeQuota
0x14000b365  call    cs:__imp_IoAllocateMdl
0x14000b36c  nop     dword ptr [rax+rax+00h]
0x14000b371  test    rax, rax
0x14000b374  jnz     short loc_14000B398
0x14000b376  mov     ecx, 0C000009Ah; Status
0x14000b37b  call    cs:__imp_ExRaiseStatus
0x14000b387  mov     ecx, 0C000000Dh; Status
0x14000b38c  call    cs:__imp_ExRaiseStatus
0x14000b398  xor     ecx, ecx
0x14000b39a  mov     r12d, [rdi]
0x14000b39d  cmp     r12d, 30h ; '0'
0x14000b3a1  jbe     short loc_14000B414
0x14000b3a3  mov     rax, [rsp+0C8h+arg_0]
0x14000b3ab  mov     rcx, [rax+68h]
0x14000b3af  test    rcx, rcx
0x14000b3b2  jz      short loc_14000B3EB
0x14000b3b4  mov     rax, [rcx]
0x14000b3b7  mov     rax, [rax+20h]
0x14000b3bb  xor     r8d, r8d
0x14000b3be  mov     edx, [rdi+2Ch]
0x14000b3c1  call    _guard_dispatch_icall
0x14000b3c6  mov     ecx, eax
0x14000b3c8  lea     rax, [r12-30h]
0x14000b3cd  cmp     rcx, rax
0x14000b3d0  jz      short loc_14000B3E3
0x14000b3d2  mov     ecx, 0C000000Dh; Status
0x14000b3d7  call    cs:__imp_ExRaiseStatus
0x14000b3e3  mov     rax, [rsp+0C8h+arg_0]
0x14000b3eb  mov     r8d, [rdi]
0x14000b3ee  sub     r8d, 30h ; '0'; unsigned int
0x14000b3f2  mov     edx, [rdi+2Ch]; unsigned int
0x14000b3f5  mov     rcx, rax; this
0x14000b3f8  call    ?GetExtendedHeaderSize@CKSThunkPin@@AEAAKKK@Z; CKSThunkPin::GetExtendedHeaderSize(ulong,ulong)
0x14000b3fd  mov     ecx, eax
0x14000b3ff  test    eax, eax
0x14000b401  jnz     short loc_14000B414
0x14000b403  mov     ecx, 0C000000Dh; Status
0x14000b408  call    cs:__imp_ExRaiseStatus
0x14000b414  mov     edx, [rsp+0C8h+var_98]
0x14000b418  lea     eax, [rdx+38h]
0x14000b41b  cmp     eax, edx
0x14000b41d  jb      short loc_14000B48E
0x14000b41f  mov     [rsp+0C8h+var_94], eax
0x14000b423  add     ecx, eax
0x14000b425  mov     [rsp+0C8h+var_98], ecx
0x14000b429  cmp     ecx, eax
0x14000b42b  jb      short loc_14000B475
0x14000b42d  mov     [rsp+0C8h+var_94], ecx
0x14000b431  mov     eax, [rdi]
0x14000b433  cmp     r13d, eax
0x14000b436  jb      short loc_14000B45C
0x14000b438  sub     r13d, eax
0x14000b43b  mov     [rsp+0C8h+var_70], r13d
0x14000b440  add     rdi, rax
0x14000b443  mov     [rsp+0C8h+var_48], rdi
0x14000b44b  mov     r12b, byte ptr [rsp+0C8h+arg_10]
0x14000b453  mov     edx, [rsp+0C8h+var_80]
0x14000b457  jmp     loc_14000B22B
0x14000b45c  mov     [rsp+0C8h+var_70], 0FFFFFFFFh
0x14000b464  mov     ecx, 0C000000Dh; Status
0x14000b469  call    cs:__imp_ExRaiseStatus
0x14000b475  mov     [rsp+0C8h+var_94], 0FFFFFFFFh
0x14000b47d  mov     ecx, 0C000000Dh; Status
0x14000b482  call    cs:__imp_ExRaiseStatus
0x14000b48e  mov     [rsp+0C8h+var_94], 0FFFFFFFFh
0x14000b496  mov     ecx, 0C000000Dh; Status
0x14000b49b  call    cs:__imp_ExRaiseStatus
0x14000b4a7  mov     ecx, 0C000000Dh; Status
0x14000b4ac  call    cs:__imp_ExRaiseStatus
0x14000b4b8  mov     ecx, 0C000000Dh; Status
0x14000b4bd  call    cs:__imp_ExRaiseStatus
0x14000b4c9  mov     rdi, [r14+8]
0x14000b4cd  test    rdi, rdi
0x14000b4d0  jz      short loc_14000B545
0x14000b4d2  mov     r8d, 1; Operation
0x14000b4d8  mov     dl, [r15+40h]; AccessMode
0x14000b4dc  mov     rcx, rdi; MemoryDescriptorList
0x14000b4df  call    cs:__imp_MmProbeAndLockPages
0x14000b4e6  nop     dword ptr [rax+rax+00h]
0x14000b4eb  mov     eax, 2000h
0x14000b4f0  or      [rdi+0Ah], ax
0x14000b4f4  movzx   eax, word ptr [rdi+0Ah]
0x14000b4f8  test    al, 5
0x14000b4fa  jz      short loc_14000B502
0x14000b4fc  mov     rax, [rdi+18h]
0x14000b500  jmp     short loc_14000B52A
0x14000b502  mov     [rsp+0C8h+Priority], 40000000h; Priority
0x14000b50a  mov     dword ptr [rsp+0C8h+Irp], 0; BugCheckOnFailure
0x14000b512  xor     r9d, r9d; RequestedAddress
0x14000b515  xor     edx, edx; AccessMode
0x14000b517  lea     r8d, [r9+1]; CacheType
0x14000b51b  mov     rcx, rdi; MemoryDescriptorList
0x14000b51e  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000b525  nop     dword ptr [rax+rax+00h]
0x14000b52a  test    rax, rax
0x14000b52d  jnz     short loc_14000B540
0x14000b52f  mov     ecx, 0C000009Ah; Status
0x14000b534  call    cs:__imp_ExRaiseStatus
0x14000b540  mov     rdi, [rdi]
0x14000b543  jmp     short loc_14000B4CD
0x14000b545  mov     ecx, [rsp+0C8h+var_98]
0x14000b549  jmp     short loc_14000B58B
0x14000b54b  mov     rsi, [rsp+0C8h+arg_18]
0x14000b553  mov     [rsi], eax
0x14000b555  mov     r15, [rsp+0C8h+arg_8]
0x14000b55d  mov     r14, [rsp+0C8h+var_68]
0x14000b562  mov     rax, [rsp+0C8h+var_60]
0x14000b567  mov     [rsp+0C8h+var_88], rax
0x14000b56c  mov     r13d, [rsp+0C8h+var_70]
0x14000b571  mov     eax, [rsp+0C8h+var_6C]
0x14000b575  mov     [rsp+0C8h+var_80], eax
0x14000b579  mov     ecx, [rsp+0C8h+var_94]
0x14000b57d  mov     [rsp+0C8h+var_98], ecx
0x14000b581  mov     rax, [rsp+0C8h+var_58]
0x14000b586  mov     [rsp+0C8h+var_90], rax
0x14000b58b  xor     r12d, r12d
0x14000b58e  xor     r10d, r10d
0x14000b591  mov     eax, [rsi]
0x14000b593  test    eax, eax
0x14000b595  js      loc_14000B826
  ... truncated ...
```
