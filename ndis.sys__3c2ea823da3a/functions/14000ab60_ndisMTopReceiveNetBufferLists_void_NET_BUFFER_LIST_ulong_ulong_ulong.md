# ndisMTopReceiveNetBufferLists(void *,_NET_BUFFER_LIST *,ulong,ulong,ulong)

- ea: `0x14000ab60`
- end: `0x14000b742`
- name: `?ndisMTopReceiveNetBufferLists@@YAXPEAXPEAU_NET_BUFFER_LIST@@KKK@Z`
- size: `3042`
- prototype: `void(void *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1400076e0`
- `0x140009e70`
- `0x14000a5a0`
- `0x14000ab60`
- `0x14000b750`
- `0x14000cac0`
- `0x14000de20`
- `0x140014280`
- `0x140029620`
- `0x14002ddf0`
- `0x14004bb70`
- `0x1400e6240`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14000b56d`
- `ntoskrnl!KfRaiseIrql` at `0x14000b56d`
- `ntoskrnl!KeLowerIrql` at `0x14000b1c4`
- `ntoskrnl!KeLowerIrql` at `0x14000b1c4`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000ae69`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000b116`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000ae69`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000b116`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000b6d9`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000b6d9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b05b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b05b`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000b4d6`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000b4d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000af69`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b5c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000af69`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b5c5`
- `ntoskrnl!ExAllocatePool2` at `0x14000ae92`
- `ntoskrnl!ExAllocatePool2` at `0x14000ae92`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b556`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b556`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b4ff`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b4ff`

## pseudocode

```c
void __fastcall ndisMTopReceiveNetBufferLists(
        char *a1,
        struct _NET_BUFFER_LIST *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5)
{
  struct _NET_BUFFER_LIST *v7; // rbx
  char *v8; // r12
  unsigned int Number; // r14d
  struct _NDIS_RCV_TRACKER_ARRAY *v10; // r9
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 Pool2; // rdi
  _QWORD *v14; // r13
  struct _NET_BUFFER_LIST *v15; // rdx
  struct _NET_BUFFER_LIST *Alignment; // rcx
  struct _NDIS_OPEN_BLOCK *v17; // r14
  __int64 v18; // r9
  struct _NET_BUFFER_LIST **v19; // rax
  struct _NDIS_OPEN_BLOCK *v20; // rsi
  unsigned int v21; // ebp
  unsigned int v22; // r15d
  struct _NDIS_OPEN_BLOCK *FilterNextOpen; // r14
  __int64 v24; // rbx
  __int64 v25; // rcx
  struct _NET_BUFFER_LIST *v26; // rdx
  struct _NDIS_OPEN_BLOCK *v27; // rbx
  unsigned int v28; // ebp
  unsigned int v29; // r15d
  unsigned int v30; // r13d
  int v31; // r14d
  struct _NDIS_OPEN_BLOCK *i; // rbx
  unsigned int j; // ebx
  __int64 v34; // rdx
  unsigned int v35; // esi
  int v36; // edx
  __int64 v37; // rsi
  __int64 v38; // rax
  __int64 v39; // rcx
  struct _NET_BUFFER_LIST *v40; // rdx
  char *v41; // r8
  __int64 v42; // rsi
  int v43; // r12d
  struct _NET_BUFFER_LIST *v44; // rcx
  unsigned __int64 v45; // rax
  struct _NET_BUFFER_LIST *v46; // r15
  _QWORD *p_Alignment; // r13
  struct _NET_BUFFER_LIST *v48; // rsi
  _NET_BUFFER *FirstNetBuffer; // rax
  struct _NPAGED_LOOKASIDE_LIST *v50; // rbp
  _MDL *CurrentMdl; // r14
  int v52; // r15d
  __int64 v53; // r13
  void (__fastcall *v54)(struct _NET_BUFFER_LIST *, struct _NET_BUFFER_LIST *, __int64); // rbp
  struct _NET_BUFFER_LIST *v55; // r14
  unsigned int v56; // eax
  __int64 v57; // r8
  unsigned __int64 v58; // rax
  struct _NET_BUFFER_LIST **p_Parameter; // rsi
  struct _NET_BUFFER_LIST *v60; // rdx
  __int64 v61; // r15
  __int64 v62; // r12
  struct _NET_BUFFER_LIST *v63; // rdx
  struct _VF_NDIS_DISPATCH_TABLE *v64; // rax
  __int64 v65; // r8
  struct _NET_BUFFER_LIST *v66; // rbx
  struct _VF_NDIS_DISPATCH_TABLE *v67; // rax
  __int64 ChildRefCount; // r8
  struct _NET_BUFFER_LIST *Scratch; // rbx
  struct _NET_BUFFER_LIST *v70; // rdx
  struct _VF_NDIS_DISPATCH_TABLE *v71; // rax
  __int64 v72; // r8
  struct _NET_BUFFER_LIST *v73; // rbx
  unsigned int v74; // r15d
  struct _NDIS_OPEN_BLOCK *v75; // r14
  __int64 v76; // rsi
  __int64 v77; // rcx
  struct _NET_BUFFER_LIST *v78; // rdx
  int v79; // ecx
  KIRQL v80; // bp
  struct _NET_BUFFER_LIST **p_Next; // rcx
  struct _NET_BUFFER_LIST *k; // rdx
  PVOID Context; // [rsp+20h] [rbp-A8h]
  char v84; // [rsp+40h] [rbp-88h]
  unsigned int v85; // [rsp+44h] [rbp-84h]
  unsigned int v86; // [rsp+48h] [rbp-80h]
  unsigned int v87; // [rsp+4Ch] [rbp-7Ch]
  __int64 v88; // [rsp+50h] [rbp-78h]
  struct _NET_BUFFER_LIST **v89; // [rsp+58h] [rbp-70h]
  int v90; // [rsp+58h] [rbp-70h]
  struct _NET_BUFFER_LIST *Parameter; // [rsp+60h] [rbp-68h] BYREF
  struct _NET_BUFFER_LIST *v92; // [rsp+68h] [rbp-60h]
  void (__fastcall *v93)(struct _NET_BUFFER_LIST *, struct _NET_BUFFER_LIST *, __int64); // [rsp+70h] [rbp-58h]
  struct _NET_BUFFER_LIST *v94; // [rsp+78h] [rbp-50h]
  __int64 v95; // [rsp+80h] [rbp-48h]
  int v96; // [rsp+88h] [rbp-40h]
  int v97; // [rsp+8Ch] [rbp-3Ch]
  unsigned int v99; // [rsp+D0h] [rbp+8h]
  char v100; // [rsp+D8h] [rbp+10h]
  KIRQL v101; // [rsp+D8h] [rbp+10h]

  v7 = a2;
  v8 = a1;
  if ( (a2->NblFlags & 0x8000) != 0 )
  {
    (*((void (__fastcall **)(char *, struct _NET_BUFFER_LIST *))a1 + 268))(a1, a2);
    return;
  }
  if ( !a1[2665] )
  {
    (*((void (__fastcall **)(char *))a1 + 267))(a1);
    return;
  }
  v87 = 0;
  v85 = a5 & 1;
  if ( ((a5 & 1) != 0 || KeGetCurrentIrql() == 2)
    && ndisPerProcRcvTrackers
    && (Number = KeGetPcr()->Prcb.Number,
        v10 = ndisPerProcRcvTrackers,
        v11 = 2096LL * Number,
        v87 = Number,
        v12 = *(unsigned int *)((char *)ndisPerProcRcvTrackers + v11),
        (unsigned int)v12 < 3) )
  {
    v84 = 1;
    *(_DWORD *)((char *)ndisPerProcRcvTrackers + v11) = v12 + 1;
    Pool2 = (__int64)v10 + 696 * v12 + v11 + 8;
  }
  else
  {
    v84 = 0;
    Pool2 = ExAllocatePool2(66, 696, 538985550);
    if ( !Pool2 )
    {
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v36) = 2;
        WPP_RECORDER_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          v36,
          4,
          11,
          (struct _GUID *)&WPP_ab2fd775e6d238d6e5be27dfc6df6673_Traceguids);
      }
      v35 = a5 & 2;
      goto LABEL_37;
    }
  }
  v14 = (_QWORD *)*((_QWORD *)v8 + 50);
  v15 = 0;
  *(_BYTE *)(Pool2 + 692) = 0;
  Alignment = v7;
  if ( (a5 & 2) == 0 )
  {
    do
    {
      v15 = Alignment;
      Alignment->Flags = Alignment->Flags & 0xFFFFFFF0 | 4;
      Alignment = (struct _NET_BUFFER_LIST *)Alignment->Link.Alignment;
    }
    while ( Alignment );
  }
  v17 = (struct _NDIS_OPEN_BLOCK *)v14[41];
  if ( v17 && v17->ProtocolHandle->MajorNdisVersion >= 6u )
  {
    ndisMIndicateNetBufferListsToOpen(v17, v7, a3, a4, a5);
    v19 = (struct _NET_BUFFER_LIST **)(Pool2 + 64);
    *(_DWORD *)(Pool2 + 80) = 0;
    *(_QWORD *)(Pool2 + 64) = 0;
  }
  else
  {
    *(_QWORD *)(Pool2 + 24) = v7;
    *(_QWORD *)(Pool2 + 8) = v14;
    *(_DWORD *)(Pool2 + 16) = a5;
    *(_QWORD *)Pool2 = v8;
    *(_QWORD *)(Pool2 + 32) = v15;
    *(_DWORD *)(Pool2 + 40) = a3;
    *(_DWORD *)(Pool2 + 44) = a4;
    ndisSortNetBufferLists((struct _NDIS_NBL_RCV_TRACKER *)Pool2);
    v19 = (struct _NET_BUFFER_LIST **)(Pool2 + 64);
    if ( *(_QWORD *)(Pool2 + 64) || *(_DWORD *)(Pool2 + 688) )
    {
      if ( !*v14 || a3 )
      {
        *(_BYTE *)(Pool2 + 692) = 1;
      }
      else
      {
        ndisIndicateXlatedPacketsToNdis5Protocols((struct _NDIS_NBL_RCV_TRACKER *)Pool2);
        v19 = (struct _NET_BUFFER_LIST **)(Pool2 + 64);
      }
      if ( !v17 )
      {
        v20 = (struct _NDIS_OPEN_BLOCK *)v14[1];
        v89 = v19;
        if ( v20 )
        {
          v21 = *(_DWORD *)(Pool2 + 688);
          v22 = *(_DWORD *)(Pool2 + 16) | 2;
          do
          {
            FilterNextOpen = v20->FilterNextOpen;
            v24 = 0;
            do
            {
              v25 = (unsigned int)v24;
              v26 = *(struct _NET_BUFFER_LIST **)(Pool2 + 40 * v24 + 64);
              v24 = (unsigned int)(v24 + 1);
              if ( v26 )
                ndisMIndicateNetBufferListsToOpen(
                  v20,
                  v26,
                  *(_DWORD *)(Pool2 + 40),
                  *(_DWORD *)(Pool2 + 40 * v25 + 80),
                  v22);
            }
            while ( (unsigned int)v24 <= v21 );
            v20 = FilterNextOpen;
          }
          while ( FilterNextOpen );
        }
        v27 = (struct _NDIS_OPEN_BLOCK *)v14[2];
        if ( v27 )
        {
          v28 = *(_DWORD *)(Pool2 + 688);
          v29 = *(_DWORD *)(Pool2 + 16);
          if ( (a5 & 2) != 0 )
          {
            v74 = v29 | 2;
            do
            {
              v75 = v27->FilterNextOpen;
              v76 = 0;
              do
              {
                v77 = (unsigned int)v76;
                v78 = *(struct _NET_BUFFER_LIST **)(Pool2 + 40 * v76 + 64);
                v76 = (unsigned int)(v76 + 1);
                if ( v78 )
                  ndisMIndicateNetBufferListsToOpen(
                    v27,
                    v78,
                    *(_DWORD *)(Pool2 + 40),
                    *(_DWORD *)(Pool2 + 40 * v77 + 80),
                    v74);
              }
              while ( (unsigned int)v76 <= v28 );
              v27 = v75;
            }
            while ( v75 );
          }
          else
          {
            v30 = *(_DWORD *)(Pool2 + 40);
            v31 = *(_DWORD *)(*(_QWORD *)Pool2 + 2244LL);
            if ( v31 )
            {
              for ( i = *(struct _NDIS_OPEN_BLOCK **)(*(_QWORD *)(Pool2 + 8) + 16LL); i; i = i->FilterNextOpen )
              {
                if ( (i->OpenFlags & 4) != 0 )
                {
                  v37 = 0;
                  do
                  {
                    v38 = 5 * v37;
                    v39 = (unsigned int)v37;
                    v40 = *(struct _NET_BUFFER_LIST **)(Pool2 + 40 * v37 + 64);
                    v37 = (unsigned int)(v37 + 1);
                    if ( v40 && *(struct _NDIS_OPEN_BLOCK **)(Pool2 + 8 * v38 + 56) != i )
                      ndisMIndicateNetBufferListsToOpen(i, v40, v30, *(_DWORD *)(Pool2 + 40 * v39 + 80), v29 | 2);
                  }
                  while ( (unsigned int)v37 <= v28 );
                  if ( !--v31 )
                    break;
                }
              }
              v8 = a1;
            }
            for ( j = 1; j <= v28; ++j )
            {
              v34 = j;
              ndisMIndicateNetBufferListsToOpen(
                *(struct _NDIS_OPEN_BLOCK **)(Pool2 + 40 * v34 + 56),
                *(struct _NET_BUFFER_LIST **)(Pool2 + 40 * v34 + 64),
                v30,
                *(_DWORD *)(Pool2 + 40 * v34 + 80),
                v29);
            }
          }
        }
        v19 = v89;
      }
    }
  }
  if ( !*(_BYTE *)(Pool2 + 692) )
    goto LABEL_38;
  v7 = *v19;
  v35 = a5 & 2;
LABEL_37:
  if ( !v7 )
    goto LABEL_38;
  if ( byte_14011D730 && (*((_DWORD *)v8 + 1468) & 2) != 0 )
    PktMonClientNblDrop(
      (__int64)(v8 + 5816),
      (__int64)v7,
      *((_DWORD *)v8 + 1467),
      v18,
      (__int64)Context,
      1u,
      204,
      -536866809);
  if ( v35 )
    goto LABEL_38;
  if ( !*((_DWORD *)v8 + 12) )
  {
    v41 = a1;
    v42 = 0;
    LOBYTE(v43) = 0;
    v88 = 0;
    v100 = 0;
    if ( !*((_DWORD *)a1 + 20) )
      goto LABEL_60;
    v8 = a1;
  }
  v41 = a1;
  v43 = *((_DWORD *)v8 + 20);
  v100 = v43;
  v42 = *((_QWORD *)a1 + 5);
  v88 = v42;
  if ( !v42 )
  {
    v42 = *((_QWORD *)a1 + 5);
    v88 = v42;
  }
LABEL_60:
  v44 = v7;
  do
  {
    v44->Flags = v44->Flags & 0xFFFFFFF4 | 8;
    v44 = (struct _NET_BUFFER_LIST *)v44->Link.Alignment;
  }
  while ( v44 );
  v45 = (unsigned int)Microsoft_Windows_Networking_CorrelationEnabled;
  if ( Microsoft_Windows_Networking_CorrelationEnabled
    || byte_14011D730 != (_BYTE)Microsoft_Windows_Networking_CorrelationEnabled )
  {
    ndisMarkNetBufferListCorrelationIdsAsUsed(v7);
  }
  if ( *((_DWORD *)v41 + 806) )
  {
    v46 = 0;
    p_Alignment = 0;
    do
    {
      v48 = (struct _NET_BUFFER_LIST *)v7->Link.Alignment;
      v7->Link.Alignment = 0;
      HIDWORD(v45) = HIDWORD(PoolHandle);
      if ( v7->NdisPoolHandle == PoolHandle )
      {
        _InterlockedDecrement((volatile signed __int32 *)a1 + 806);
        FirstNetBuffer = v7->FirstNetBuffer;
        v50 = (struct _NPAGED_LOOKASIDE_LIST *)v7->MiniportReserved[1];
        CurrentMdl = FirstNetBuffer->CurrentMdl;
        if ( (CurrentMdl->MdlFlags & 0x20) != 0 )
          MmUnmapLockedPages(CurrentMdl->MappedSystemVa, FirstNetBuffer->CurrentMdl);
        if ( v50 )
          ExFreeToNPagedLookasideList(v50, CurrentMdl);
        else
          ExFreePoolWithTag(CurrentMdl, 0);
        NdisFreeNetBufferList(v7);
      }
      else
      {
        if ( v46 )
          *p_Alignment = v7;
        else
          v46 = v7;
        p_Alignment = &v7->Link.Alignment;
      }
      v7 = v48;
    }
    while ( v48 );
    LOBYTE(v43) = v100;
    if ( !v46 )
      goto LABEL_38;
    v42 = v88;
    v7 = v46;
    v41 = a1;
  }
  v86 = -1;
  v101 = 2;
  if ( *(_DWORD *)ndisNblTrackerMode )
    ndisNblTrackerTransferOwnershipInternal(
      v7,
      0,
      *((struct NDIS_NBL_TRACKER_HANDLE__ **)v41 + 317),
      NdisNblTrackerEvent_ProtocolReturned,
      v85);
  v52 = v43 & 0x20;
  v90 = v52;
  if ( (v43 & 0x20) != 0 )
  {
    if ( (a5 & 1) == 0 )
      v101 = KfRaiseIrql(2u);
    v86 = KeGetPcr()->Prcb.Number;
    v45 = __rdtsc();
    *(_QWORD *)(ndisPcwOffsetToPerCpuData + v42 + ndisPcwPerCpuDataStride * v86 + 344) = v45;
  }
  v53 = *((_QWORD *)a1 + 318);
  v54 = (void (__fastcall *)(struct _NET_BUFFER_LIST *, struct _NET_BUFFER_LIST *, __int64))*((_QWORD *)a1 + 330);
  v55 = (struct _NET_BUFFER_LIST *)*((_QWORD *)a1 + 316);
  if ( *(_BYTE *)v53 == 17 )
    goto LABEL_84;
  if ( (a5 & 1) != 0 || KeGetCurrentIrql() == 2 )
  {
    LODWORD(v45) = KeGetPcr()->Prcb.Number;
    p_Parameter = &Parameter;
    v99 = v45;
    v93 = 0;
    Parameter = v7;
    v92 = v7;
    v7->Scratch = 0;
    v7->ChildRefCount = v85;
    while ( *(_BYTE *)v53 == 5 )
    {
      v60 = *p_Parameter;
      if ( !*p_Parameter )
        break;
      v61 = *(_QWORD *)(v53 + 424) + 96 * v45;
      if ( *(_BYTE *)(v61 + 88) )
      {
        *p_Parameter = 0;
        do
        {
          v67 = ndisVerifierNdisDispatch;
          ChildRefCount = (unsigned int)v60->ChildRefCount;
          Scratch = (struct _NET_BUFFER_LIST *)v60->Scratch;
          v60->ChildRefCount = 0;
          if ( v67 && *(_BYTE *)v53 == 5 && *(_QWORD *)(v53 + 776) )
            (*((void (__fastcall **)(struct _NET_BUFFER_LIST *, struct _NET_BUFFER_LIST *, __int64))v67 + 17))(
              v55,
              v60,
              ChildRefCount);
          else
            v54(v55, v60, ChildRefCount);
          v60 = Scratch;
        }
        while ( Scratch );
        break;
      }
      *(_BYTE *)(v61 + 88) = 1;
      v62 = v53;
      v63 = *p_Parameter;
      *p_Parameter = 0;
      if ( v63 )
      {
        do
        {
          v64 = ndisVerifierNdisDispatch;
          v65 = (unsigned int)v63->ChildRefCount;
          v66 = (struct _NET_BUFFER_LIST *)v63->Scratch;
          v63->ChildRefCount = 0;
          if ( v64 && *(_BYTE *)v53 == 5 && *(_QWORD *)(v53 + 776) )
            (*((void (__fastcall **)(struct _NET_BUFFER_LIST *, struct _NET_BUFFER_LIST *, __int64))v64 + 17))(
              v55,
              v63,
              v65);
          else
            v54(v55, v63, v65);
          v63 = v66;
        }
        while ( v66 );
      }
      v45 = v99;
      p_Parameter = (struct _NET_BUFFER_LIST **)(v61 + 72);
      *(_BYTE *)(v61 + 88) = 0;
      v53 = *(_QWORD *)(v53 + 552);
      v54 = *(void (__fastcall **)(struct _NET_BUFFER_LIST *, struct _NET_BUFFER_LIST *, __int64))(v62 + 528);
      v55 = *(struct _NET_BUFFER_LIST **)(v62 + 536);
    }
    v70 = *p_Parameter;
    if ( *p_Parameter )
    {
      *p_Parameter = 0;
      do
      {
        v71 = ndisVerifierNdisDispatch;
        v72 = (unsigned int)v70->ChildRefCount;
        v73 = (struct _NET_BUFFER_LIST *)v70->Scratch;
        v70->ChildRefCount = 0;
        if ( v71 && *(_BYTE *)v53 == 5 && *(_QWORD *)(v53 + 776) )
          (*((void (__fastcall **)(struct _NET_BUFFER_LIST *, struct _NET_BUFFER_LIST *, __int64))v71 + 17))(
            v55,
            v70,
            v72);
        else
          v54(v55, v70, v72);
        v70 = v73;
      }
      while ( v73 );
    }
    v52 = v90;
    goto LABEL_85;
  }
  if ( *a1 != 5 )
    goto LABEL_84;
  if ( !ndisIsLwfGuaranteedStackSpaceAvailable() )
  {
    v79 = 24576;
    v97 = 0;
    Parameter = (struct _NET_BUFFER_LIST *)v53;
    v92 = v55;
    v93 = v54;
    v94 = v7;
    v95 = 0;
    v96 = 0;
    if ( (unsigned int)Size > 0x6000 )
      v79 = Size;
    if ( KeExpandKernelStackAndCalloutEx(
           ndisDataPathExpandStackCallback<3,void (void *,_NET_BUFFER_LIST *,unsigned long)>,
           &Parameter,
           v79,
           0,
           0) < 0 )
    {
      if ( *(_DWORD *)ndisNblTrackerMode )
        ndisNblTrackerTransferOwnershipInternal(
          v7,
          *((struct NDIS_NBL_TRACKER_HANDLE__ **)a1 + 81),
          (struct NDIS_NBL_TRACKER_HANDLE__ *)0xA0,
          (enum _NDIS_NBL_TRACKER_OWNERSHIP_EVENT)1,
          0);
      v80 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 18);
      *((_QWORD *)a1 + 19) = KeGetCurrentThread();
      p_Next = (struct _NET_BUFFER_LIST **)(a1 + 280);
      for ( k = (struct _NET_BUFFER_LIST *)*((_QWORD *)a1 + 35); k; k = (struct _NET_BUFFER_LIST *)k->Link.Alignment )
        p_Next = &k->Next;
      *p_Next = v7;
      ndisQueueStackExpansionFallbackWorkItem((struct _NDIS_FILTER_BLOCK *)a1);
      *((_QWORD *)a1 + 19) = 0;
      KeReleaseSpinLock((PKSPIN_LOCK)a1 + 18, v80);
    }
    goto LABEL_85;
  }
  if ( ndisVerifierNdisDispatch && *(_BYTE *)v53 == 5 && *(_QWORD *)(v53 + 776) )
    (*((void (__fastcall **)(struct _NET_BUFFER_LIST *, struct _NET_BUFFER_LIST *, _QWORD))ndisVerifierNdisDispatch + 17))(
      v55,
      v7,
      0);
  else
LABEL_84:
    v54(v55, v7, a5 & 1);
LABEL_85:
  if ( v52 )
  {
    v56 = v86;
    if ( v86 == -1 )
      v56 = KeGetPcr()->Prcb.Number;
    v57 = v88 + ndisPcwPerCpuDataStride * v56 + ndisPcwOffsetToPerCpuData;
    v58 = __rdtsc();
    *(_QWORD *)(v57 + 144) += (((unsigned __int64)HIDWORD(v58) << 32) | (unsigned int)v58) - *(_QWORD *)(v57 + 344);
    *(_QWORD *)(v57 + 344) = 0;
    if ( v101 != 2 )
      KeLowerIrql(v101);
  }
LABEL_38:
  if ( v84 )
  {
    --*((_DWORD *)ndisPerProcRcvTrackers + 524 * v87);
  }
  else if ( Pool2 )
  {
    ExFreePoolWithTag((PVOID)Pool2, 0);
  }
}

```

## disassembly

```asm
0x14000ab60  mov     rax, rsp
0x14000ab63  mov     [rax+8], rcx
0x14000ab67  push    rbx
0x14000ab68  push    rbp
0x14000ab69  push    r12
0x14000ab6b  push    r15
0x14000ab6d  sub     rsp, 0A8h
0x14000ab74  test    dword ptr [rdx+80h], 8000h
0x14000ab7e  mov     ebp, r9d
0x14000ab81  mov     r15d, r8d
0x14000ab84  mov     rbx, rdx
0x14000ab87  mov     r12, rcx
0x14000ab8a  jnz     loc_14000ADD1
0x14000ab90  cmp     byte ptr [rcx+0A69h], 0
0x14000ab97  jz      loc_14000AF32
0x14000ab9d  mov     [rax+18h], rsi
0x14000aba1  mov     esi, [rsp+0C8h+arg_20]
0x14000aba8  mov     [rax-28h], rdi
0x14000abac  mov     [rax-30h], r13
0x14000abb0  mov     [rax-38h], r14
0x14000abb4  mov     eax, esi
0x14000abb6  and     eax, 1
0x14000abb9  mov     [rsp+0C8h+var_7C], 0
0x14000abc1  mov     [rsp+0C8h+var_84], eax
0x14000abc5  jz      loc_14000AE69
0x14000abcb  cmp     cs:?ndisPerProcRcvTrackers@@3PEAU_NDIS_RCV_TRACKER_ARRAY@@EA, 0; _NDIS_RCV_TRACKER_ARRAY * ndisPerProcRcvTrackers
0x14000abd3  jz      loc_14000AE7D
0x14000abd9  mov     r14d, gs:1A4h
0x14000abe2  mov     r9, cs:?ndisPerProcRcvTrackers@@3PEAU_NDIS_RCV_TRACKER_ARRAY@@EA; _NDIS_RCV_TRACKER_ARRAY * ndisPerProcRcvTrackers
0x14000abe9  mov     eax, r14d
0x14000abec  imul    r8, rax, 830h
0x14000abf3  mov     [rsp+0C8h+var_7C], r14d
0x14000abf8  mov     edx, [r8+r9]
0x14000abfc  cmp     edx, 3
0x14000abff  jnb     loc_14000AE7D
0x14000ac05  imul    rdi, rdx, 2B8h
0x14000ac0c  lea     eax, [rdx+1]
0x14000ac0f  mov     [rsp+0C8h+var_88], 1
0x14000ac14  add     rdi, 8
0x14000ac18  mov     [r8+r9], eax
0x14000ac1c  add     rdi, r8
0x14000ac1f  add     rdi, r9
0x14000ac22  mov     r13, [r12+190h]
0x14000ac2a  xor     edx, edx
0x14000ac2c  mov     eax, esi
0x14000ac2e  mov     [rdi+2B4h], dl
0x14000ac34  and     eax, 2
0x14000ac37  mov     rcx, rbx
0x14000ac3a  mov     [rsp+0C8h+arg_8], eax
0x14000ac41  jz      loc_14000B6B0
0x14000ac47  mov     r14, [r13+148h]
0x14000ac4e  test    r14, r14
0x14000ac51  jnz     loc_14000AEF8
0x14000ac57  mov     rcx, rdi; struct _NDIS_NBL_RCV_TRACKER *
0x14000ac5a  mov     [rdi+18h], rbx
0x14000ac5e  mov     [rdi+8], r13
0x14000ac62  mov     [rdi+10h], esi
0x14000ac65  mov     [rdi], r12
0x14000ac68  mov     [rdi+20h], rdx
0x14000ac6c  mov     [rdi+28h], r15d
0x14000ac70  mov     [rdi+2Ch], ebp
0x14000ac73  call    ?ndisSortNetBufferLists@@YAXPEAU_NDIS_NBL_RCV_TRACKER@@@Z; ndisSortNetBufferLists(_NDIS_NBL_RCV_TRACKER *)
0x14000ac78  cmp     qword ptr [rdi+40h], 0
0x14000ac7d  lea     rax, [rdi+40h]
0x14000ac81  jnz     short loc_14000AC90
0x14000ac83  cmp     dword ptr [rdi+2B0h], 0
0x14000ac8a  jz      loc_14000ADBC
0x14000ac90  cmp     qword ptr [r13+0], 0
0x14000ac95  jnz     loc_14000B1D5
0x14000ac9b  mov     byte ptr [rdi+2B4h], 1
0x14000aca2  test    r14, r14
0x14000aca5  jnz     loc_14000ADBC
0x14000acab  mov     rsi, [r13+8]
0x14000acaf  mov     [rsp+0C8h+var_70], rax
0x14000acb4  test    rsi, rsi
0x14000acb7  jz      short loc_14000AD11
0x14000acb9  mov     r15d, [rdi+10h]
0x14000acbd  mov     ebp, [rdi+2B0h]
0x14000acc3  or      r15d, 2
0x14000acc7  nop     word ptr [rax+rax+00000000h]
0x14000acd0  mov     r14, [rsi+1A8h]
0x14000acd7  xor     ebx, ebx
0x14000acd9  lea     rax, [rbx+rbx*4]
0x14000acdd  mov     ecx, ebx
0x14000acdf  mov     rdx, [rdi+rax*8+40h]; struct _NET_BUFFER_LIST *
0x14000ace4  inc     ebx
0x14000ace6  test    rdx, rdx
0x14000ace9  jz      short loc_14000AD05
0x14000aceb  mov     r8d, [rdi+28h]; unsigned int
0x14000acef  lea     r9, [rcx+rcx*4]
0x14000acf3  mov     r9d, [rdi+r9*8+50h]; unsigned int
0x14000acf8  mov     rcx, rsi; struct _NDIS_OPEN_BLOCK *
0x14000acfb  mov     dword ptr [rsp+0C8h+Context], r15d; unsigned int
0x14000ad00  call    ?ndisMIndicateNetBufferListsToOpen@@YAXPEAU_NDIS_OPEN_BLOCK@@PEAU_NET_BUFFER_LIST@@KKK@Z; ndisMIndicateNetBufferListsToOpen(_NDIS_OPEN_BLOCK *,_NET_BUFFER_LIST *,ulong,ulong,ulong)
0x14000ad05  cmp     ebx, ebp
0x14000ad07  jbe     short loc_14000ACD9
0x14000ad09  mov     rsi, r14
0x14000ad0c  test    r14, r14
0x14000ad0f  jnz     short loc_14000ACD0
0x14000ad11  mov     rbx, [r13+10h]
0x14000ad15  test    rbx, rbx
0x14000ad18  jz      loc_14000ADB7
0x14000ad1e  cmp     [rsp+0C8h+arg_8], 0
0x14000ad26  mov     ebp, [rdi+2B0h]
0x14000ad2c  mov     r15d, [rdi+10h]
0x14000ad30  jnz     loc_14000B41F
0x14000ad36  mov     rax, [rdi]
0x14000ad39  mov     r13d, [rdi+28h]
0x14000ad3d  mov     r14d, [rax+8C4h]
0x14000ad44  test    r14d, r14d
0x14000ad47  jz      short loc_14000AD82
0x14000ad49  mov     rax, [rdi+8]
0x14000ad4d  mov     r12d, r15d
0x14000ad50  or      r12d, 2
0x14000ad54  mov     rbx, [rax+10h]
0x14000ad58  test    rbx, rbx
0x14000ad5b  jz      short loc_14000AD7A
0x14000ad5d  nop     dword ptr [rax]
0x14000ad60  mov     eax, [rbx+0E0h]
0x14000ad66  test    al, 4
0x14000ad68  jnz     loc_14000AEAF
0x14000ad6e  mov     rbx, [rbx+1A8h]
0x14000ad75  test    rbx, rbx
0x14000ad78  jnz     short loc_14000AD60
0x14000ad7a  mov     r12, [rsp+0C8h+arg_0]
0x14000ad82  mov     ebx, 1
0x14000ad87  cmp     ebp, ebx
0x14000ad89  jb      short loc_14000ADB7
0x14000ad8b  mov     edx, ebx
0x14000ad8d  mov     r8d, r13d; unsigned int
0x14000ad90  inc     ebx
0x14000ad92  mov     dword ptr [rsp+0C8h+Context], r15d; unsigned int
0x14000ad97  lea     rax, [rdx+rdx*4]
0x14000ad9b  mov     rcx, [rdi+rax*8+38h]; struct _NDIS_OPEN_BLOCK *
0x14000ada0  lea     r9, [rdx+rdx*4]
0x14000ada4  mov     r9d, [rdi+r9*8+50h]; unsigned int
0x14000ada9  mov     rdx, [rdi+rax*8+40h]; struct _NET_BUFFER_LIST *
0x14000adae  call    ?ndisMIndicateNetBufferListsToOpen@@YAXPEAU_NDIS_OPEN_BLOCK@@PEAU_NET_BUFFER_LIST@@KKK@Z; ndisMIndicateNetBufferListsToOpen(_NDIS_OPEN_BLOCK *,_NET_BUFFER_LIST *,ulong,ulong,ulong)
0x14000adb3  cmp     ebx, ebp
0x14000adb5  jbe     short loc_14000AD8B
0x14000adb7  mov     rax, [rsp+0C8h+var_70]
0x14000adbc  cmp     byte ptr [rdi+2B4h], 0
0x14000adc3  jz      short loc_14000AE1A
0x14000adc5  mov     rbx, [rax]
0x14000adc8  mov     esi, [rsp+0C8h+arg_8]
0x14000adcf  jmp     short loc_14000AE11
0x14000add1  mov     edx, [rsp+0C8h+arg_20]
0x14000add8  mov     rax, [rcx+860h]
0x14000addf  mov     dword ptr [rsp+0C8h+Context], edx
0x14000ade3  mov     rdx, rbx
0x14000ade6  call    _guard_dispatch_icall
0x14000adeb  add     rsp, 0A8h
0x14000adf2  pop     r15
0x14000adf4  pop     r12
0x14000adf6  pop     rbp
0x14000adf7  pop     rbx
0x14000adf8  retn
0x14000adfa  lea     rax, WPP_RECORDER_INITIALIZED
0x14000ae01  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000ae08  jnz     loc_14000B1EF
0x14000ae0e  and     esi, 2
0x14000ae11  test    rbx, rbx
0x14000ae14  jnz     loc_14000AF7A
0x14000ae1a  cmp     [rsp+0C8h+var_88], 0
0x14000ae1f  mov     r14, [rsp+0C8h+var_38]
0x14000ae27  mov     r13, [rsp+0C8h+var_30]
0x14000ae2f  mov     rsi, [rsp+0C8h+arg_10]
0x14000ae37  jz      loc_14000AF5B
0x14000ae3d  mov     eax, [rsp+0C8h+var_7C]
0x14000ae41  imul    rcx, rax, 830h
0x14000ae48  mov     rax, cs:?ndisPerProcRcvTrackers@@3PEAU_NDIS_RCV_TRACKER_ARRAY@@EA; _NDIS_RCV_TRACKER_ARRAY * ndisPerProcRcvTrackers
0x14000ae4f  dec     dword ptr [rcx+rax]
0x14000ae52  mov     rdi, [rsp+0C8h+var_28]
0x14000ae5a  add     rsp, 0A8h
0x14000ae61  pop     r15
0x14000ae63  pop     r12
0x14000ae65  pop     rbp
0x14000ae66  pop     rbx
0x14000ae67  retn
0x14000ae69  call    cs:__imp_KeGetCurrentIrql
0x14000ae70  nop     dword ptr [rax+rax+00h]
0x14000ae75  cmp     al, 2
0x14000ae77  jz      loc_14000ABCB
0x14000ae7d  mov     edx, 2B8h
0x14000ae82  mov     [rsp+0C8h+var_88], 0
0x14000ae87  mov     ecx, 42h ; 'B'
0x14000ae8c  mov     r8d, 2020444Eh
0x14000ae92  call    cs:__imp_ExAllocatePool2
0x14000ae99  nop     dword ptr [rax+rax+00h]
0x14000ae9e  mov     rdi, rax
0x14000aea1  test    rax, rax
0x14000aea4  jnz     loc_14000AC22
0x14000aeaa  jmp     loc_14000ADFA
0x14000aeaf  xor     esi, esi
0x14000aeb1  lea     rax, [rsi+rsi*4]
0x14000aeb5  mov     ecx, esi
0x14000aeb7  mov     rdx, [rdi+rax*8+40h]; struct _NET_BUFFER_LIST *
0x14000aebc  inc     esi
0x14000aebe  test    rdx, rdx
0x14000aec1  jz      short loc_14000AECA
0x14000aec3  cmp     [rdi+rax*8+38h], rbx
0x14000aec8  jnz     short loc_14000AEDD
0x14000aeca  cmp     esi, ebp
0x14000aecc  jbe     short loc_14000AEB1
0x14000aece  sub     r14d, 1
0x14000aed2  jz      loc_14000AD7A
0x14000aed8  jmp     loc_14000AD6E
0x14000aedd  lea     r9, [rcx+rcx*4]
0x14000aee1  mov     dword ptr [rsp+0C8h+Context], r12d; unsigned int
0x14000aee6  mov     r9d, [rdi+r9*8+50h]; unsigned int
0x14000aeeb  mov     r8d, r13d; unsigned int
0x14000aeee  mov     rcx, rbx; struct _NDIS_OPEN_BLOCK *
0x14000aef1  call    ?ndisMIndicateNetBufferListsToOpen@@YAXPEAU_NDIS_OPEN_BLOCK@@PEAU_NET_BUFFER_LIST@@KKK@Z; ndisMIndicateNetBufferListsToOpen(_NDIS_OPEN_BLOCK *,_NET_BUFFER_LIST *,ulong,ulong,ulong)
0x14000aef6  jmp     short loc_14000AECA
0x14000aef8  mov     rax, [r14+18h]
0x14000aefc  cmp     byte ptr [rax+38h], 6
0x14000af00  jb      loc_14000AC57
0x14000af06  mov     r9d, ebp; unsigned int
0x14000af09  mov     dword ptr [rsp+0C8h+Context], esi; unsigned int
0x14000af0d  mov     r8d, r15d; unsigned int
0x14000af10  mov     rdx, rbx; struct _NET_BUFFER_LIST *
0x14000af13  mov     rcx, r14; struct _NDIS_OPEN_BLOCK *
0x14000af16  call    ?ndisMIndicateNetBufferListsToOpen@@YAXPEAU_NDIS_OPEN_BLOCK@@PEAU_NET_BUFFER_LIST@@KKK@Z; ndisMIndicateNetBufferListsToOpen(_NDIS_OPEN_BLOCK *,_NET_BUFFER_LIST *,ulong,ulong,ulong)
0x14000af1b  lea     rax, [rdi+40h]
0x14000af1f  mov     dword ptr [rdi+50h], 0
0x14000af26  mov     qword ptr [rax], 0
0x14000af2d  jmp     loc_14000ADBC
0x14000af32  mov     rax, [rcx+858h]
0x14000af39  mov     ecx, [rsp+0C8h+arg_20]
0x14000af40  mov     dword ptr [rsp+0C8h+Context], ecx
0x14000af44  mov     rcx, r12
0x14000af47  call    _guard_dispatch_icall
0x14000af4c  add     rsp, 0A8h
0x14000af53  pop     r15
0x14000af55  pop     r12
0x14000af57  pop     rbp
0x14000af58  pop     rbx
0x14000af59  retn
0x14000af5b  test    rdi, rdi
0x14000af5e  jz      loc_14000AE52
0x14000af64  xor     edx, edx; Tag
0x14000af66  mov     rcx, rdi; P
0x14000af69  call    cs:__imp_ExFreePoolWithTag
0x14000af70  nop     dword ptr [rax+rax+00h]
0x14000af75  jmp     loc_14000AE52
0x14000af7a  cmp     cs:byte_14011D730, 0
0x14000af81  jnz     loc_14000B21E
0x14000af87  test    esi, esi
0x14000af89  jnz     loc_14000AE1A
0x14000af8f  cmp     [r12+30h], esi
0x14000af94  jnz     loc_14000B3EA
0x14000af9a  mov     r8, [rsp+0C8h+arg_0]
0x14000afa2  xor     esi, esi
0x14000afa4  xor     r12d, r12d
0x14000afa7  mov     [rsp+0C8h+var_78], rsi
0x14000afac  mov     [rsp+0C8h+arg_8], r12d
0x14000afb4  cmp     [r8+50h], esi
0x14000afb8  jnz     loc_14000B3E2
0x14000afbe  mov     rcx, rbx
0x14000afc1  mov     eax, [rcx+88h]
0x14000afc7  and     eax, 0FFFFFFFCh
0x14000afca  or      eax, 8
0x14000afcd  mov     [rcx+88h], eax
0x14000afd3  mov     rcx, [rcx]
0x14000afd6  test    rcx, rcx
0x14000afd9  jnz     short loc_14000AFC1
0x14000afdb  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14000afe1  test    eax, eax
0x14000afe3  jnz     loc_14000B5B3
0x14000afe9  cmp     cs:byte_14011D730, al
0x14000afef  jnz     loc_14000B5B3
0x14000aff5  cmp     dword ptr [r8+0C98h], 0
0x14000affd  jz      loc_14000B098
0x14000b003  mov     r12, [rsp+0C8h+arg_0]
0x14000b00b  xor     r15d, r15d
0x14000b00e  xor     r13d, r13d
0x14000b011  mov     rsi, [rbx]
0x14000b014  mov     qword ptr [rbx], 0
0x14000b01b  mov     rax, cs:PoolHandle
0x14000b022  cmp     [rbx+20h], rax
0x14000b026  jnz     loc_14000B6EA
0x14000b02c  lock dec dword ptr [r12+0C98h]
0x14000b035  mov     rax, [rbx+8]
0x14000b039  mov     rbp, [rbx+68h]
0x14000b03d  mov     r14, [rax+8]
0x14000b041  test    byte ptr [r14+0Ah], 20h
0x14000b046  jnz     loc_14000B6D2
0x14000b04c  test    rbp, rbp
0x14000b04f  jz      loc_14000B5C0
0x14000b055  mov     rdx, r14; Entry
0x14000b058  mov     rcx, rbp; Lookaside
0x14000b05b  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000b062  nop     dword ptr [rax+rax+00h]
0x14000b067  mov     rcx, rbx; NetBufferList
0x14000b06a  call    NdisFreeNetBufferList
0x14000b06f  mov     rbx, rsi
0x14000b072  test    rsi, rsi
0x14000b075  jnz     short loc_14000B011
0x14000b077  mov     r12d, [rsp+0C8h+arg_8]
0x14000b07f  test    r15, r15
  ... truncated ...
```
