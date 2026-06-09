# ndisSortNetBufferLists(_NDIS_NBL_RCV_TRACKER *)

- ea: `0x14000cac0`
- end: `0x14000d694`
- name: `?ndisSortNetBufferLists@@YAXPEAU_NDIS_NBL_RCV_TRACKER@@@Z`
- size: `3028`
- prototype: `void __fastcall(struct _NDIS_NBL_RCV_TRACKER *)`
- caller_count: `5`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140004d70`
- `0x1400054e0`
- `0x140005a30`
- `0x14000a600`
- `0x14000ab60`

## callees

- `0x140009e70`
- `0x14000a5a0`
- `0x14000cac0`
- `0x14000de20`
- `0x14002c970`
- `0x1400e6240`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14000d378`
- `ntoskrnl!KfRaiseIrql` at `0x14000d378`
- `ntoskrnl!KeLowerIrql` at `0x14000d184`
- `ntoskrnl!KeLowerIrql` at `0x14000d184`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000cf66`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000cf66`
- `ntoskrnl!MmMapLockedPages` at `0x14000d5cc`
- `ntoskrnl!MmMapLockedPages` at `0x14000d5cc`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000d62c`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000d62c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000ceb6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000ceb6`
- `ntoskrnl!IoGetStackLimits` at `0x14000cfe5`
- `ntoskrnl!IoGetStackLimits` at `0x14000cfe5`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000d05e`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000d05e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d42d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d42d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d0de`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d0de`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d08b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d08b`

## pseudocode

```c
void __fastcall ndisSortNetBufferLists(struct _NDIS_NBL_RCV_TRACKER *a1)
{
  __int64 v1; // rax
  unsigned __int64 v3; // rdi
  struct _NDIS_FILTER_BLOCK *v4; // r14
  _QWORD *v5; // r10
  char *v6; // r8
  struct _NET_BUFFER_LIST *v7; // r11
  __int64 v8; // r9
  unsigned __int16 v9; // r15
  unsigned __int64 v10; // r12
  unsigned __int64 v11; // r13
  __int64 v12; // rax
  __int64 v13; // rcx
  unsigned int v14; // esi
  __int64 v15; // rbp
  _BYTE *v16; // rax
  char *v17; // rdx
  unsigned __int16 v18; // ax
  char v19; // cl
  __int64 v20; // r10
  unsigned int v21; // edx
  unsigned int i; // r8d
  char *v23; // rcx
  __int64 v24; // rcx
  bool v25; // zf
  _DWORD *v26; // rcx
  int v27; // ebx
  Rtl::KString *value; // rsi
  int v29; // edi
  struct _NET_BUFFER_LIST *Alignment; // rcx
  unsigned __int64 v31; // rax
  struct _NET_BUFFER_LIST *v32; // rsi
  _QWORD *p_Alignment; // r12
  struct _NET_BUFFER_LIST *v34; // rbp
  _NET_BUFFER *FirstNetBuffer; // rax
  struct _NPAGED_LOOKASIDE_LIST *v36; // r14
  _MDL *CurrentMdl; // r15
  unsigned int v38; // ebx
  KIRQL v39; // r13
  unsigned int Number; // r12d
  unsigned __int64 v41; // rbp
  void (__fastcall *v42)(unsigned __int64, unsigned __int64, __int64); // rdi
  unsigned __int64 v43; // rsi
  unsigned __int64 v44; // r15
  __int64 v45; // rcx
  unsigned __int64 v46; // rdx
  int v47; // ecx
  KIRQL v48; // di
  _NET_BUFFER_LIST **p_ReceivedNblsToComplete; // rcx
  _SLIST_HEADER *j; // rdx
  __int64 v51; // r8
  unsigned __int64 v52; // rax
  unsigned __int64 *p_LowLimit; // r14
  unsigned __int64 v54; // rdx
  __int64 v55; // r15
  unsigned __int64 v56; // r13
  unsigned __int64 v57; // rdx
  struct _VF_NDIS_DISPATCH_TABLE *v58; // rax
  __int64 v59; // r8
  unsigned __int64 v60; // rbx
  struct _VF_NDIS_DISPATCH_TABLE *v61; // rax
  __int64 v62; // r8
  unsigned __int64 v63; // rbx
  unsigned __int64 v64; // rdx
  struct _VF_NDIS_DISPATCH_TABLE *v65; // rax
  __int64 v66; // r8
  unsigned __int64 v67; // rbx
  int v68; // [rsp+30h] [rbp-98h]
  PNET_BUFFER_LIST NetBufferList; // [rsp+38h] [rbp-90h]
  struct _NDIS_FILTER_BLOCK *v70; // [rsp+40h] [rbp-88h]
  unsigned int v71; // [rsp+48h] [rbp-80h]
  unsigned __int64 LowLimit; // [rsp+50h] [rbp-78h] BYREF
  unsigned __int64 HighLimit; // [rsp+58h] [rbp-70h] BYREF
  void (__fastcall *v74)(unsigned __int64, unsigned __int64, __int64); // [rsp+60h] [rbp-68h]
  PNET_BUFFER_LIST v75; // [rsp+68h] [rbp-60h]
  __int64 v76; // [rsp+70h] [rbp-58h]
  int v77; // [rsp+78h] [rbp-50h]
  int v78; // [rsp+7Ch] [rbp-4Ch]
  _UNKNOWN *retaddr; // [rsp+C8h] [rbp+0h] BYREF
  char v80; // [rsp+D0h] [rbp+8h]
  char v81; // [rsp+D0h] [rbp+8h]
  unsigned __int16 v82; // [rsp+D8h] [rbp+10h]
  unsigned int v83; // [rsp+D8h] [rbp+10h]
  unsigned __int16 v84; // [rsp+E0h] [rbp+18h]
  Rtl::KString *v85; // [rsp+E0h] [rbp+18h]
  unsigned int v86; // [rsp+E8h] [rbp+20h]
  int v87; // [rsp+E8h] [rbp+20h]

  v1 = *((_QWORD *)a1 + 1);
  v3 = *((_QWORD *)a1 + 3);
  *((_DWORD *)a1 + 172) = 0;
  if ( *(_QWORD *)(v1 + 328) || (*((_DWORD *)a1 + 4) & 2) != 0 )
  {
    *((_QWORD *)a1 + 8) = v3;
    *((_QWORD *)a1 + 9) = *((_QWORD *)a1 + 4);
    *((_QWORD *)a1 + 7) = 0;
    *((_DWORD *)a1 + 20) = *((_DWORD *)a1 + 11);
    return;
  }
  v4 = *(struct _NDIS_FILTER_BLOCK **)a1;
  v5 = 0;
  LOBYTE(v6) = 0;
  v7 = 0;
  LODWORD(v8) = 0;
  v9 = 0;
  v70 = *(struct _NDIS_FILTER_BLOCK **)a1;
  LowLimit = 0;
  NetBufferList = 0;
  v68 = 0;
  v80 = 0;
  v86 = 0;
  v71 = 0;
  *((_QWORD *)a1 + 7) = 0;
  *((_QWORD *)a1 + 8) = 0;
  *((_QWORD *)a1 + 9) = 0;
  *((_WORD *)a1 + 24) = 0;
  *((_DWORD *)a1 + 20) = 0;
  while ( v3 )
  {
    v10 = *(_QWORD *)v3;
    *(_QWORD *)v3 = 0;
    v11 = v3;
    if ( *(_DWORD *)(*(_QWORD *)a1 + 464LL) )
    {
      v18 = *(_WORD *)(v3 + 200);
      goto LABEL_15;
    }
    v12 = *(_QWORD *)(v3 + 8);
    v13 = *(_QWORD *)(v12 + 8);
    if ( v13
      && (v14 = *(_DWORD *)(v13 + 40), v14 >= 0xE)
      && (v15 = *(unsigned int *)(v12 + 16), v14 > (unsigned int)v15) )
    {
      if ( v14 - (unsigned int)v15 < 0xE )
        goto LABEL_145;
      if ( (*(_BYTE *)(v13 + 10) & 5) != 0 )
      {
        v16 = *(_BYTE **)(v13 + 24);
      }
      else
      {
        v16 = MmMapLockedPages((PMDL)v13, 0);
        LODWORD(v8) = v71;
        v7 = NetBufferList;
        LOBYTE(v6) = v80;
        v5 = (_QWORD *)LowLimit;
      }
      v17 = &v16[v15];
      HIBYTE(v84) = v16[v15 + 12];
      LOBYTE(v84) = v16[v15 + 13];
      v82 = *(_WORD *)&v16[v15 + 12];
      if ( v84 > 0x600u )
      {
        if ( v84 != 0x8100 )
          goto LABEL_14;
        if ( v14 >= 0x12 && v14 - (unsigned int)v15 >= 0x12 )
        {
          v82 = *((_WORD *)v17 + 8);
LABEL_14:
          v18 = v82;
LABEL_15:
          v19 = 1;
          v9 = v18;
          goto LABEL_16;
        }
LABEL_145:
        v4 = v70;
        goto LABEL_137;
      }
      v19 = 0;
      if ( v17[14] == -86 && v17[15] == -86 && v17[16] == 3 )
      {
        v18 = *((_WORD *)v17 + 10);
        goto LABEL_15;
      }
LABEL_16:
      if ( !v19 )
        goto LABEL_91;
      v20 = *((_QWORD *)a1 + 1);
      if ( v68 != v9 )
      {
        v21 = 0;
        v68 = v9;
        while ( v21 < *(_DWORD *)(v20 + 24) )
        {
          if ( v9 == *(_WORD *)(v20 + 16LL * v21 + 32) )
          {
            v86 = v21;
            v80 = 1;
            goto LABEL_23;
          }
          ++v21;
        }
        v80 = 0;
        v86 = 0;
LABEL_91:
        i = 0;
        goto LABEL_27;
      }
      v21 = v86;
      if ( (_BYTE)v6 != 1 )
        goto LABEL_91;
LABEL_23:
      if ( *((_WORD *)a1 + 20 * (unsigned int)v8 + 24) == v9 )
      {
        i = v8;
      }
      else
      {
        for ( i = 1; ; ++i )
        {
          if ( i > *((_DWORD *)a1 + 172) )
          {
            v8 = (unsigned int)++*((_DWORD *)a1 + 172);
            v71 = *((_DWORD *)a1 + 172);
            i = v71;
            v23 = (char *)a1 + 40 * v8;
            *((_WORD *)v23 + 24) = v9;
            *((_QWORD *)v23 + 7) = *(_QWORD *)(v20 + 16 * (v21 + 1LL) + 24);
            *((_QWORD *)v23 + 8) = 0;
            goto LABEL_27;
          }
          if ( *((_WORD *)a1 + 20 * i + 24) == v9 )
            break;
        }
        LODWORD(v8) = i;
        v71 = i;
      }
LABEL_27:
      v24 = i + 2LL;
      v25 = *((_QWORD *)a1 + 5 * i + 8) == 0;
      v6 = (char *)a1 + 40 * i;
      v26 = (_DWORD *)((char *)a1 + 40 * v24);
      if ( v25 )
      {
        *((_QWORD *)v6 + 8) = v3;
        if ( (*((_DWORD *)a1 + 4) & 0x100) != 0 )
        {
          v4 = v70;
          *((_QWORD *)v6 + 9) = 0;
          *(_QWORD *)v3 = v10;
          *v26 = *((_DWORD *)a1 + 11);
          break;
        }
        *v26 = 1;
      }
      else
      {
        **((_QWORD **)v6 + 9) = v3;
        ++*v26;
      }
      v4 = v70;
      v3 = v10;
      *((_QWORD *)v6 + 9) = v11;
      LOBYTE(v6) = v80;
      v5 = (_QWORD *)LowLimit;
    }
    else
    {
LABEL_137:
      if ( v5 )
      {
        *v5 = v3;
      }
      else
      {
        v7 = (struct _NET_BUFFER_LIST *)v3;
        NetBufferList = (PNET_BUFFER_LIST)v3;
      }
      ++v4[2].Characteristics.CancelSendNetBufferListsHandler;
      v3 = v10;
      v5 = (_QWORD *)v11;
      LowLimit = v11;
    }
  }
  if ( !v7 )
    return;
  if ( byte_14011D730 && ((__int64)v4[4].PendingOidRequest & 2) != 0 )
  {
    PktMonClientNblDropNdis((_DWORD)v4 + 5816, (_DWORD)v7, (_BYTE)v6, 1, -1073676273, -536866810);
    v7 = NetBufferList;
  }
  v27 = *((_DWORD *)a1 + 4);
  if ( (v27 & 2) != 0 )
    return;
  if ( LODWORD(v4->FilterFriendlyName) || (value = 0, LOBYTE(v29) = 0, v85 = 0, *(_DWORD *)&v4->Ref.ReferenceCount) )
  {
    value = v4->FilterInstanceName.__ptr_.__value_;
    v29 = *(_DWORD *)&v4->Ref.ReferenceCount;
    v85 = value;
    if ( !value )
    {
      value = v4->FilterInstanceName.__ptr_.__value_;
      v85 = value;
    }
  }
  Alignment = v7;
  do
  {
    Alignment->Flags = Alignment->Flags & 0xFFFFFFF4 | 8;
    Alignment = (struct _NET_BUFFER_LIST *)Alignment->Link.Alignment;
  }
  while ( Alignment );
  v31 = (unsigned int)Microsoft_Windows_Networking_CorrelationEnabled;
  if ( Microsoft_Windows_Networking_CorrelationEnabled
    || byte_14011D730 != (_BYTE)Microsoft_Windows_Networking_CorrelationEnabled )
  {
    v31 = (unsigned __int64)v7;
    if ( byte_14011D730 )
    {
      do
      {
        *(_QWORD *)(v31 + 248) = 0;
        v31 = *(_QWORD *)v31;
      }
      while ( v31 );
    }
    else
    {
      do
      {
        *(_QWORD *)(v31 + 248) |= 0x8000000000000000uLL;
        v31 = *(_QWORD *)v31;
      }
      while ( v31 );
    }
  }
  if ( !*(_DWORD *)&v4[2].XState )
  {
LABEL_55:
    v38 = v27 & 1;
    v39 = 2;
    Number = -1;
    v81 = 2;
    if ( *(_DWORD *)ndisNblTrackerMode )
      ndisNblTrackerTransferOwnershipInternal(
        v7,
        0,
        *(struct NDIS_NBL_TRACKER_HANDLE__ **)&v4[1].NicSwitchHwCapabilities.MaxNumQueuePairsForDefaultVPort,
        NdisNblTrackerEvent_ProtocolReturned,
        v38);
    v87 = v29 & 0x20;
    if ( (v29 & 0x20) != 0 )
    {
      if ( !v38 )
      {
        v39 = KfRaiseIrql(2u);
        v81 = v39;
      }
      Number = KeGetPcr()->Prcb.Number;
      v31 = __rdtsc();
      *(wchar_t **)((char *)&value[21].Buffer + ndisPcwPerCpuDataStride * Number + ndisPcwOffsetToPerCpuData) = (wchar_t *)v31;
    }
    v41 = *(_QWORD *)&v4[1].NicSwitchCurrentCapabilities.Flags;
    v42 = *(void (__fastcall **)(unsigned __int64, unsigned __int64, __int64))&v4[1].NicSwitchCurrentCapabilities.NdisReserved14;
    v43 = *(_QWORD *)&v4[1].NicSwitchHwCapabilities.NumberOfIndirectionTableEntriesForDefaultVPort;
    if ( *(_BYTE *)v41 == 17 )
      goto LABEL_74;
    if ( v38 || KeGetCurrentIrql() == 2 )
    {
      LODWORD(v31) = KeGetPcr()->Prcb.Number;
      p_LowLimit = &LowLimit;
      v83 = v31;
      v74 = 0;
      LowLimit = (unsigned __int64)NetBufferList;
      NetBufferList->Scratch = 0;
      NetBufferList->ChildRefCount = v38;
      HighLimit = (unsigned __int64)NetBufferList;
      while ( *(_BYTE *)v41 == 5 )
      {
        v54 = *p_LowLimit;
        if ( !*p_LowLimit )
          break;
        v55 = *(_QWORD *)(v41 + 424) + 96 * v31;
        if ( *(_BYTE *)(v55 + 88) )
        {
          *p_LowLimit = 0;
          do
          {
            v61 = ndisVerifierNdisDispatch;
            v62 = *(unsigned int *)(v54 + 132);
            v63 = *(_QWORD *)(v54 + 112);
            *(_DWORD *)(v54 + 132) = 0;
            if ( v61 && *(_BYTE *)v41 == 5 && *(_QWORD *)(v41 + 776) )
              (*((void (__fastcall **)(unsigned __int64, unsigned __int64, __int64))v61 + 17))(v43, v54, v62);
            else
              v42(v43, v54, v62);
            v54 = v63;
          }
          while ( v63 );
          break;
        }
        *(_BYTE *)(v55 + 88) = 1;
        v56 = v41;
        v57 = *p_LowLimit;
        *p_LowLimit = 0;
        if ( v57 )
        {
          do
          {
            v58 = ndisVerifierNdisDispatch;
            v59 = *(unsigned int *)(v57 + 132);
            v60 = *(_QWORD *)(v57 + 112);
            *(_DWORD *)(v57 + 132) = 0;
            if ( v58 && *(_BYTE *)v41 == 5 && *(_QWORD *)(v41 + 776) )
              (*((void (__fastcall **)(unsigned __int64, unsigned __int64, __int64))v58 + 17))(v43, v57, v59);
            else
              v42(v43, v57, v59);
            v57 = v60;
          }
          while ( v60 );
        }
        v31 = v83;
        p_LowLimit = (unsigned __int64 *)(v55 + 72);
        *(_BYTE *)(v55 + 88) = 0;
        v41 = *(_QWORD *)(v41 + 552);
        v42 = *(void (__fastcall **)(unsigned __int64, unsigned __int64, __int64))(v56 + 528);
        v43 = *(_QWORD *)(v56 + 536);
      }
      v64 = *p_LowLimit;
      if ( *p_LowLimit )
      {
        *p_LowLimit = 0;
        do
        {
          v65 = ndisVerifierNdisDispatch;
          v66 = *(unsigned int *)(v64 + 132);
          v67 = *(_QWORD *)(v64 + 112);
          *(_DWORD *)(v64 + 132) = 0;
          if ( v65 && *(_BYTE *)v41 == 5 && *(_QWORD *)(v41 + 776) )
            (*((void (__fastcall **)(unsigned __int64, unsigned __int64, __int64))v65 + 17))(v43, v64, v66);
          else
            v42(v43, v64, v66);
          v64 = v67;
        }
        while ( v67 );
      }
      v39 = v81;
      goto LABEL_75;
    }
    if ( v4->Header.Type != 5 )
      goto LABEL_74;
    v44 = (unsigned int)Size;
    LowLimit = 0;
    HighLimit = 0;
    v45 = KeGetPcr()->Prcb.Number << 12;
    v46 = *(_QWORD *)(v45 + qword_14011CF78);
    LowLimit = v46;
    HighLimit = *(_QWORD *)(v45 + qword_14011CF70);
    if ( (unsigned __int64)&retaddr >= HighLimit || v46 > (unsigned __int64)&retaddr )
    {
      IoGetStackLimits(&LowLimit, &HighLimit);
      v46 = LowLimit;
    }
    if ( (unsigned __int64)&retaddr - v46 < v44 )
    {
      v47 = 24576;
      v78 = 0;
      LowLimit = v41;
      HighLimit = v43;
      v74 = v42;
      v75 = NetBufferList;
      v76 = 0;
      v77 = 0;
      if ( (unsigned int)Size > 0x6000 )
        v47 = Size;
      if ( KeExpandKernelStackAndCalloutEx(
             ndisDataPathExpandStackCallback<3,void (void *,_NET_BUFFER_LIST *,unsigned long)>,
             &LowLimit,
             v47,
             0,
             0) < 0 )
      {
        if ( *(_DWORD *)ndisNblTrackerMode )
          ndisNblTrackerTransferOwnershipInternal(
            NetBufferList,
            v70->NblTracker,
            (struct NDIS_NBL_TRACKER_HANDLE__ *)0xA0,
            (enum _NDIS_NBL_TRACKER_OWNERSHIP_EVENT)1,
            0);
        v48 = KeAcquireSpinLockRaiseToDpc(&v70->Lock);
        v70->LockThread = KeGetCurrentThread();
        p_ReceivedNblsToComplete = &v70->StackExpansionFallback.PendingWork.ReceivedNblsToComplete;
        for ( j = (_SLIST_HEADER *)v70->StackExpansionFallback.PendingWork.ReceivedNblsToComplete;
              j;
              j = (_SLIST_HEADER *)j->Alignment )
        {
          p_ReceivedNblsToComplete = (_NET_BUFFER_LIST **)j;
        }
        *p_ReceivedNblsToComplete = NetBufferList;
        ndisQueueStackExpansionFallbackWorkItem(v70);
        v70->LockThread = 0;
        KeReleaseSpinLock(&v70->Lock, v48);
      }
      goto LABEL_75;
    }
    if ( ndisVerifierNdisDispatch && *(_BYTE *)v41 == 5 && *(_QWORD *)(v41 + 776) )
      (*((void (__fastcall **)(unsigned __int64, PNET_BUFFER_LIST, _QWORD))ndisVerifierNdisDispatch + 17))(
        v43,
        NetBufferList,
        0);
    else
LABEL_74:
      v42(v43, (unsigned __int64)NetBufferList, v38);
LABEL_75:
    if ( v87 )
    {
      if ( Number == -1 )
        Number = KeGetPcr()->Prcb.Number;
      v51 = (__int64)v85 + ndisPcwPerCpuDataStride * Number + ndisPcwOffsetToPerCpuData;
      v52 = __rdtsc();
      *(_QWORD *)(v51 + 144) += (((unsigned __int64)HIDWORD(v52) << 32) | (unsigned int)v52) - *(_QWORD *)(v51 + 344);
      *(_QWORD *)(v51 + 344) = 0;
      if ( v39 != 2 )
        KeLowerIrql(v39);
    }
    return;
  }
  v32 = 0;
  p_Alignment = 0;
  do
  {
    v34 = (struct _NET_BUFFER_LIST *)v7->Link.Alignment;
    v7->Link.Alignment = 0;
    HIDWORD(v31) = HIDWORD(PoolHandle);
    if ( v7->NdisPoolHandle == PoolHandle )
    {
      _InterlockedDecrement((volatile signed __int32 *)&v4[2].XState);
      FirstNetBuffer = v7->FirstNetBuffer;
      v36 = (struct _NPAGED_LOOKASIDE_LIST *)v7->MiniportReserved[1];
      CurrentMdl = FirstNetBuffer->CurrentMdl;
      if ( (CurrentMdl->MdlFlags & 0x20) != 0 )
        MmUnmapLockedPages(CurrentMdl->MappedSystemVa, FirstNetBuffer->CurrentMdl);
      if ( v36 )
        ExFreeToNPagedLookasideList(v36, CurrentMdl);
      else
        ExFreePoolWithTag(CurrentMdl, 0);
      NdisFreeNetBufferList(NetBufferList);
      v4 = v70;
    }
    else
    {
      if ( v32 )
        *p_Alignment = v7;
      else
        v32 = v7;
      p_Alignment = &v7->Link.Alignment;
    }
    NetBufferList = v34;
    v7 = v34;
  }
  while ( v34 );
  if ( v32 )
  {
    v7 = v32;
    NetBufferList = v32;
    value = v85;
    goto LABEL_55;
  }
}

```

## disassembly

```asm
0x14000cac0  mov     r11, rsp
0x14000cac3  push    rbx
0x14000cac4  push    rdi
0x14000cac5  sub     rsp, 0B8h
0x14000cacc  mov     rax, [rcx+8]
0x14000cad0  mov     rbx, rcx
0x14000cad3  mov     rdi, [rcx+18h]
0x14000cad7  mov     dword ptr [rcx+2B0h], 0
0x14000cae1  cmp     qword ptr [rax+148h], 0
0x14000cae9  jnz     loc_14000CDC4
0x14000caef  mov     eax, [rcx+10h]
0x14000caf2  test    al, 2
0x14000caf4  jnz     loc_14000CDC4
0x14000cafa  xor     eax, eax
0x14000cafc  mov     [r11-38h], r14
0x14000cb00  mov     r14, [rcx]
0x14000cb03  xor     r10d, r10d
0x14000cb06  mov     [r11-40h], r15
0x14000cb0a  xor     r8b, r8b
0x14000cb0d  mov     [rsp+0C8h+var_18], rbp
0x14000cb15  xor     r11d, r11d
0x14000cb18  mov     [rsp+0C8h+var_20], rsi
0x14000cb20  xor     r9d, r9d
0x14000cb23  mov     [rsp+0C8h+var_28], r12
0x14000cb2b  xor     r15d, r15d
0x14000cb2e  mov     [rsp+0C8h+var_30], r13
0x14000cb36  mov     [rsp+0C8h+var_88], r14
0x14000cb3b  mov     [rsp+0C8h+LowLimit], r10
0x14000cb40  mov     [rsp+0C8h+NetBufferList], r11
0x14000cb45  mov     [rsp+0C8h+var_98], eax
0x14000cb49  mov     [rsp+0C8h+arg_0], r8b
0x14000cb51  mov     [rsp+0C8h+arg_18], eax
0x14000cb58  mov     [rsp+0C8h+var_80], r9
0x14000cb5d  mov     [rcx+38h], rax
0x14000cb61  mov     [rcx+40h], rax
0x14000cb65  mov     [rcx+48h], rax
0x14000cb69  mov     [rcx+30h], ax
0x14000cb6d  mov     [rcx+50h], eax
0x14000cb70  test    rdi, rdi
0x14000cb73  jz      loc_14000CD50
0x14000cb79  mov     r12, [rdi]
0x14000cb7c  xor     eax, eax
0x14000cb7e  mov     qword ptr [rdi], 0
0x14000cb85  mov     r13, rdi
0x14000cb88  mov     word ptr [rsp+0C8h+arg_8], ax
0x14000cb90  mov     rax, [rbx]
0x14000cb93  cmp     dword ptr [rax+1D0h], 0
0x14000cb9a  jnz     loc_14000D401
0x14000cba0  xor     eax, eax
0x14000cba2  mov     word ptr [rsp+0C8h+arg_10], ax
0x14000cbaa  mov     rax, [rdi+8]
0x14000cbae  mov     rcx, [rax+8]; MemoryDescriptorList
0x14000cbb2  test    rcx, rcx
0x14000cbb5  jz      loc_14000D5A1
0x14000cbbb  mov     esi, [rcx+28h]
0x14000cbbe  cmp     esi, 0Eh
0x14000cbc1  jb      loc_14000D5A1
0x14000cbc7  mov     ebp, [rax+10h]
0x14000cbca  cmp     esi, ebp
0x14000cbcc  jbe     loc_14000D5A1
0x14000cbd2  mov     r14d, esi
0x14000cbd5  sub     r14d, ebp
0x14000cbd8  cmp     r14d, 0Eh
0x14000cbdc  jb      loc_14000D61B
0x14000cbe2  test    byte ptr [rcx+0Ah], 5
0x14000cbe6  jz      loc_14000D5CA
0x14000cbec  mov     rax, [rcx+18h]
0x14000cbf0  movzx   ecx, byte ptr [rax+rbp+0Ch]
0x14000cbf5  lea     rdx, [rax+rbp]
0x14000cbf9  movzx   eax, byte ptr [rax+rbp+0Dh]
0x14000cbfe  mov     byte ptr [rsp+0C8h+arg_10+1], cl
0x14000cc05  mov     byte ptr [rsp+0C8h+arg_10], al
0x14000cc0c  mov     byte ptr [rsp+0C8h+arg_8], cl
0x14000cc13  mov     ecx, 600h
0x14000cc18  mov     byte ptr [rsp+0C8h+arg_8+1], al
0x14000cc1f  movzx   eax, word ptr [rsp+0C8h+arg_10]
0x14000cc27  cmp     ax, cx
0x14000cc2a  jbe     loc_14000D578
0x14000cc30  mov     ecx, 8100h
0x14000cc35  cmp     ax, cx
0x14000cc38  jz      loc_14000D5F5
0x14000cc3e  movzx   eax, word ptr [rsp+0C8h+arg_8]
0x14000cc46  mov     cl, 1
0x14000cc48  movzx   r15d, ax
0x14000cc4c  test    cl, cl
0x14000cc4e  jz      loc_14000D294
0x14000cc54  mov     r10, [rbx+8]
0x14000cc58  movzx   eax, r15w
0x14000cc5c  cmp     [rsp+0C8h+var_98], eax
0x14000cc60  jz      short loc_14000CC96
0x14000cc62  mov     ecx, [r10+18h]
0x14000cc66  xor     edx, edx
0x14000cc68  mov     [rsp+0C8h+var_98], eax
0x14000cc6c  cmp     edx, ecx
0x14000cc6e  jnb     loc_14000D282
0x14000cc74  mov     eax, edx
0x14000cc76  add     rax, rax
0x14000cc79  cmp     r15w, [r10+rax*8+20h]
0x14000cc7f  jnz     loc_14000D195
0x14000cc85  mov     [rsp+0C8h+arg_18], edx
0x14000cc8c  mov     [rsp+0C8h+arg_0], 1
0x14000cc94  jmp     short loc_14000CCA7
0x14000cc96  mov     edx, [rsp+0C8h+arg_18]
0x14000cc9d  cmp     r8b, 1
0x14000cca1  jnz     loc_14000D294
0x14000cca7  mov     eax, r9d
0x14000ccaa  lea     rcx, [rax+rax*4]
0x14000ccae  cmp     [rbx+rcx*8+30h], r15w
0x14000ccb4  jz      loc_14000CDBC
0x14000ccba  mov     r9d, [rbx+2B0h]
0x14000ccc1  mov     r8d, 1
0x14000ccc7  cmp     r8d, r9d
0x14000ccca  jbe     loc_14000D3EA
0x14000ccd0  inc     dword ptr [rbx+2B0h]
0x14000ccd6  mov     r9d, [rbx+2B0h]
0x14000ccdd  mov     [rsp+0C8h+var_80], r9
0x14000cce2  mov     r8d, r9d
0x14000cce5  lea     rax, [r9+r9*4]
0x14000cce9  lea     rcx, [rbx+rax*8]
0x14000cced  mov     eax, edx
0x14000ccef  inc     rax
0x14000ccf2  mov     [rcx+30h], r15w
0x14000ccf7  add     rax, rax
0x14000ccfa  mov     rax, [r10+rax*8+18h]
0x14000ccff  mov     [rcx+38h], rax
0x14000cd03  mov     qword ptr [rcx+40h], 0
0x14000cd0b  mov     ecx, r8d
0x14000cd0e  lea     rax, [rcx+rcx*4]
0x14000cd12  add     rcx, 2
0x14000cd16  cmp     qword ptr [rbx+rax*8+40h], 0
0x14000cd1c  lea     r8, [rbx+rax*8]
0x14000cd20  lea     rax, [rcx+rcx*4]
0x14000cd24  lea     rcx, [rbx+rax*8]
0x14000cd28  jnz     short loc_14000CD94
0x14000cd2a  mov     [r8+40h], rdi
0x14000cd2e  test    dword ptr [rbx+10h], 100h
0x14000cd35  jz      loc_14000D0EC
0x14000cd3b  mov     r14, [rsp+0C8h+var_88]
0x14000cd40  mov     qword ptr [r8+48h], 0
0x14000cd48  mov     [rdi], r12
0x14000cd4b  mov     eax, [rbx+2Ch]
0x14000cd4e  mov     [rcx], eax
0x14000cd50  test    r11, r11
0x14000cd53  jnz     loc_14000CDE9
0x14000cd59  mov     rsi, [rsp+0C8h+var_20]
0x14000cd61  mov     r13, [rsp+0C8h+var_30]
0x14000cd69  mov     r12, [rsp+0C8h+var_28]
0x14000cd71  mov     rbp, [rsp+0C8h+var_18]
0x14000cd79  mov     r14, [rsp+0C8h+var_38]
0x14000cd81  mov     r15, [rsp+0C8h+var_40]
0x14000cd89  add     rsp, 0B8h
0x14000cd90  pop     rdi
0x14000cd91  pop     rbx
0x14000cd92  retn
0x14000cd94  mov     rax, [r8+48h]
0x14000cd98  mov     [rax], rdi
0x14000cd9b  inc     dword ptr [rcx]
0x14000cd9d  mov     r14, [rsp+0C8h+var_88]
0x14000cda2  mov     rdi, r12
0x14000cda5  mov     [r8+48h], r13
0x14000cda9  movzx   r8d, [rsp+0C8h+arg_0]
0x14000cdb2  mov     r10, [rsp+0C8h+LowLimit]
0x14000cdb7  jmp     loc_14000CB70
0x14000cdbc  mov     r8d, r9d
0x14000cdbf  jmp     loc_14000CD0B
0x14000cdc4  mov     [rcx+40h], rdi
0x14000cdc8  mov     rax, [rcx+20h]
0x14000cdcc  mov     [rcx+48h], rax
0x14000cdd0  mov     qword ptr [rcx+38h], 0
0x14000cdd8  mov     eax, [rcx+2Ch]
0x14000cddb  mov     [rcx+50h], eax
0x14000cdde  add     rsp, 0B8h
0x14000cde5  pop     rdi
0x14000cde6  pop     rbx
0x14000cde7  retn
0x14000cde9  cmp     cs:byte_14011D730, 0
0x14000cdf0  jnz     loc_14000D43E
0x14000cdf6  mov     ebx, [rbx+10h]
0x14000cdf9  test    bl, 2
0x14000cdfc  jnz     loc_14000CD59
0x14000ce02  cmp     dword ptr [r14+30h], 0
0x14000ce07  jnz     loc_14000D346
0x14000ce0d  xor     esi, esi
0x14000ce0f  xor     edi, edi
0x14000ce11  mov     [rsp+0C8h+arg_10], rsi
0x14000ce19  cmp     [r14+50h], esi
0x14000ce1d  jnz     loc_14000D346
0x14000ce23  mov     rcx, r11
0x14000ce26  mov     eax, [rcx+88h]
0x14000ce2c  and     eax, 0FFFFFFFCh
0x14000ce2f  or      eax, 8
0x14000ce32  mov     [rcx+88h], eax
0x14000ce38  mov     rcx, [rcx]
0x14000ce3b  test    rcx, rcx
0x14000ce3e  jnz     short loc_14000CE26
0x14000ce40  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14000ce46  test    eax, eax
0x14000ce48  jnz     loc_14000D3C2
0x14000ce4e  cmp     cs:byte_14011D730, al
0x14000ce54  jnz     loc_14000D3C2
0x14000ce5a  cmp     dword ptr [r14+0C98h], 0
0x14000ce62  jz      loc_14000CEF7
0x14000ce68  xor     esi, esi
0x14000ce6a  xor     r12d, r12d
0x14000ce6d  mov     rbp, [r11]
0x14000ce70  mov     qword ptr [r11], 0
0x14000ce77  mov     rax, cs:PoolHandle
0x14000ce7e  cmp     [r11+20h], rax
0x14000ce82  jnz     loc_14000D63D
0x14000ce88  lock dec dword ptr [r14+0C98h]
0x14000ce90  mov     rax, [r11+8]
0x14000ce94  mov     r14, [r11+68h]
0x14000ce98  mov     r15, [rax+8]
0x14000ce9c  test    byte ptr [r15+0Ah], 20h
0x14000cea1  jnz     loc_14000D625
0x14000cea7  test    r14, r14
0x14000ceaa  jz      loc_14000D428
0x14000ceb0  mov     rdx, r15; Entry
0x14000ceb3  mov     rcx, r14; Lookaside
0x14000ceb6  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000cebd  nop     dword ptr [rax+rax+00h]
0x14000cec2  mov     rcx, [rsp+0C8h+NetBufferList]; NetBufferList
0x14000cec7  call    NdisFreeNetBufferList
0x14000cecc  mov     r14, [rsp+0C8h+var_88]
0x14000ced1  mov     [rsp+0C8h+NetBufferList], rbp
0x14000ced6  mov     r11, rbp
0x14000ced9  test    rbp, rbp
0x14000cedc  jnz     short loc_14000CE6D
0x14000cede  test    rsi, rsi
0x14000cee1  jz      loc_14000CD59
0x14000cee7  mov     r11, rsi
0x14000ceea  mov     [rsp+0C8h+NetBufferList], rsi
0x14000ceef  mov     rsi, [rsp+0C8h+arg_10]
0x14000cef7  and     ebx, 1
0x14000cefa  mov     r13b, 2
0x14000cefd  cmp     cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A, 0; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x14000cf04  mov     r12d, 0FFFFFFFFh
0x14000cf0a  mov     [rsp+0C8h+arg_0], r13b
0x14000cf12  jz      short loc_14000CF2F
0x14000cf14  mov     r8, [r14+9E8h]; struct NDIS_NBL_TRACKER_HANDLE__ *
0x14000cf1b  mov     r9d, 87h; enum _NDIS_NBL_TRACKER_OWNERSHIP_EVENT
0x14000cf21  xor     edx, edx; struct NDIS_NBL_TRACKER_HANDLE__ *
0x14000cf23  mov     dword ptr [rsp+0C8h+Context], ebx; unsigned int
0x14000cf27  mov     rcx, r11; struct _NET_BUFFER_LIST *
0x14000cf2a  call    ?ndisNblTrackerTransferOwnershipInternal@@YAXPEAU_NET_BUFFER_LIST@@PEAUNDIS_NBL_TRACKER_HANDLE__@@1W4_NDIS_NBL_TRACKER_OWNERSHIP_EVENT@@K@Z; ndisNblTrackerTransferOwnershipInternal(_NET_BUFFER_LIST *,NDIS_NBL_TRACKER_HANDLE__ *,NDIS_NBL_TRACKER_HANDLE__ *,_NDIS_NBL_TRACKER_OWNERSHIP_EVENT,ulong)
0x14000cf2f  and     edi, 20h
0x14000cf32  mov     [rsp+0C8h+arg_18], edi
0x14000cf39  jnz     loc_14000D370
0x14000cf3f  mov     rbp, [r14+9F0h]
0x14000cf46  mov     rdi, [r14+0A50h]
0x14000cf4d  mov     rsi, [r14+9E0h]
0x14000cf54  cmp     byte ptr [rbp+0], 11h
0x14000cf58  jz      loc_14000D107
0x14000cf5e  test    ebx, ebx
0x14000cf60  jnz     loc_14000D19C
0x14000cf66  call    cs:__imp_KeGetCurrentIrql
0x14000cf6d  nop     dword ptr [rax+rax+00h]
0x14000cf72  cmp     al, 2
0x14000cf74  jz      loc_14000D19C
0x14000cf7a  cmp     byte ptr [r14], 5
0x14000cf7e  jnz     loc_14000D107
0x14000cf84  mov     r15d, cs:Size
0x14000cf8b  lea     r14, [rsp+0C8h]
0x14000cf93  mov     [rsp+0C8h+LowLimit], 0
0x14000cf9c  mov     [rsp+0C8h+HighLimit], 0
0x14000cfa5  mov     eax, gs:1A4h
0x14000cfad  shl     eax, 0Ch
0x14000cfb0  mov     ecx, eax
0x14000cfb2  mov     rax, cs:qword_14011CF78
0x14000cfb9  mov     rdx, [rcx+rax]
0x14000cfbd  mov     rax, cs:qword_14011CF70
0x14000cfc4  mov     [rsp+0C8h+LowLimit], rdx
0x14000cfc9  mov     r8, [rcx+rax]
0x14000cfcd  mov     [rsp+0C8h+HighLimit], r8
0x14000cfd2  cmp     r14, r8
0x14000cfd5  jb      loc_14000D40D
0x14000cfdb  lea     rdx, [rsp+0C8h+HighLimit]; HighLimit
0x14000cfe0  lea     rcx, [rsp+0C8h+LowLimit]; LowLimit
0x14000cfe5  call    cs:__imp_IoGetStackLimits
0x14000cfec  nop     dword ptr [rax+rax+00h]
0x14000cff1  mov     rdx, [rsp+0C8h+LowLimit]
0x14000cff6  sub     r14, rdx
0x14000cff9  cmp     r14, r15
0x14000cffc  jnb     loc_14000D0F7
0x14000d002  mov     r15, [rsp+0C8h+NetBufferList]
0x14000d007  mov     ecx, 6000h
0x14000d00c  mov     eax, cs:Size
0x14000d012  mov     [rsp+0C8h+var_4C], 0
0x14000d01a  mov     [rsp+0C8h+LowLimit], rbp
0x14000d01f  mov     [rsp+0C8h+HighLimit], rsi
0x14000d024  mov     [rsp+0C8h+var_68], rdi
0x14000d029  mov     [rsp+0C8h+var_60], r15
0x14000d02e  mov     [rsp+0C8h+var_58], 0
0x14000d037  mov     [rsp+0C8h+var_50], ebx
0x14000d03b  cmp     eax, ecx
0x14000d03d  ja      loc_14000D64E
0x14000d043  movsxd  r8, ecx; Size
0x14000d046  lea     rdx, [rsp+0C8h+LowLimit]; Parameter
0x14000d04b  lea     rcx, ??$ndisDataPathExpandStackCallback@$02$$A6AXPEAXPEAU_NET_BUFFER_LIST@@K@Z@@YAXPEAX@Z; Callout
0x14000d052  mov     [rsp+0C8h+Context], 0; Context
  ... truncated ...
```
