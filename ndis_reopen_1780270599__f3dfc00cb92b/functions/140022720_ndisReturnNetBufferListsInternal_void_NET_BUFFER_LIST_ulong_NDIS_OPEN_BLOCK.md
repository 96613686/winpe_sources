# ndisReturnNetBufferListsInternal(void *,_NET_BUFFER_LIST *,ulong,_NDIS_OPEN_BLOCK *)

- ea: `0x140022720`
- end: `0x1400231c8`
- name: `?ndisReturnNetBufferListsInternal@@YAXPEAXPEAU_NET_BUFFER_LIST@@KPEAU_NDIS_OPEN_BLOCK@@@Z`
- size: `2728`
- prototype: `void __fastcall(struct _NDIS_FILTER_BLOCK *, struct _NET_BUFFER_LIST *, unsigned int, struct _NDIS_OPEN_BLOCK *)`
- caller_count: `10`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140029d30`
- `0x14002bee0`
- `0x14002e4f0`
- `0x14002e8a0`
- `0x14002ed80`
- `0x14002f560`
- `0x14002fab0`
- `0x140037ca0`
- `0x140077c50`
- `0x14008c3e0`

## callees

- `0x1400110b0`
- `0x140011190`
- `0x140022720`
- `0x1400231d0`
- `0x140023900`
- `0x140025d30`
- `0x1400260b0`
- `0x1400eb460`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x140022bcc`
- `ntoskrnl!KeLowerIrql` at `0x140022bcc`
- `ntoskrnl!KeGetCurrentIrql` at `0x140022a0b`
- `ntoskrnl!KeGetCurrentIrql` at `0x140022aaf`
- `ntoskrnl!KeGetCurrentIrql` at `0x140022c15`
- `ntoskrnl!KeGetCurrentIrql` at `0x140022a0b`
- `ntoskrnl!KeGetCurrentIrql` at `0x140022aaf`
- `ntoskrnl!KeGetCurrentIrql` at `0x140022c15`
- `ntoskrnl!MmUnmapLockedPages` at `0x140023136`
- `ntoskrnl!MmUnmapLockedPages` at `0x140023136`
- `ntoskrnl!KfRaiseIrql` at `0x140022f49`
- `ntoskrnl!KfRaiseIrql` at `0x140022f49`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140022821`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140022821`
- `ntoskrnl!IoGetStackLimits` at `0x140022b2c`
- `ntoskrnl!IoGetStackLimits` at `0x140022b2c`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140022d8f`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140022d8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002301b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002301b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140022e06`
- `ntoskrnl!KeReleaseSpinLock` at `0x140022e06`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140022db7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140022db7`

## pseudocode

```c
void __fastcall ndisReturnNetBufferListsInternal(
        struct _NDIS_FILTER_BLOCK *a1,
        struct _NET_BUFFER_LIST *a2,
        unsigned int a3,
        struct _NDIS_OPEN_BLOCK *a4)
{
  struct _NDIS_OPEN_BLOCK *v4; // r13
  struct _NET_BUFFER_LIST *v5; // rsi
  struct _NDIS_FILTER_BLOCK *v6; // r14
  struct _NET_BUFFER_LIST *i; // rcx
  struct _NET_BUFFER_LIST *v8; // r12
  _QWORD *p_Alignment; // r13
  struct _NET_BUFFER_LIST *v10; // rbx
  _NET_BUFFER *FirstNetBuffer; // rax
  struct _NPAGED_LOOKASIDE_LIST *v12; // rdi
  _MDL *CurrentMdl; // r15
  unsigned __int64 v14; // rbx
  unsigned int v15; // r15d
  struct NDIS_NBL_TRACKER_HANDLE__ *NblTracker; // rdx
  __int64 v17; // rdi
  __int64 v18; // r12
  __int64 v19; // r8
  unsigned __int64 v20; // r13
  unsigned __int64 v21; // rbx
  unsigned __int64 v22; // rbp
  _SLIST_HEADER *v23; // r14
  unsigned __int64 Region; // rdi
  char *v25; // rcx
  __int64 v26; // rax
  unsigned __int64 v27; // r8
  __int64 v28; // rcx
  unsigned __int64 v29; // r12
  KIRQL v30; // al
  unsigned __int64 v31; // rdx
  __int64 v32; // rcx
  unsigned __int64 v33; // rax
  unsigned __int64 v34; // r13
  void (__fastcall *v35)(unsigned __int64, unsigned __int64, __int64); // rdi
  unsigned __int64 v36; // r15
  __int64 v37; // rcx
  unsigned __int64 v38; // rdx
  unsigned int v39; // eax
  char *v40; // r8
  unsigned __int64 v41; // rax
  KIRQL CurrentIrql; // al
  unsigned __int64 v43; // rdx
  unsigned __int64 v44; // rdi
  __int64 v45; // rdx
  unsigned __int64 *p_LowLimit; // rbx
  unsigned __int64 v47; // rdx
  __int64 v48; // rsi
  unsigned __int64 v49; // r14
  unsigned __int64 v50; // rdx
  struct _VF_NDIS_DISPATCH_TABLE *v51; // rax
  __int64 v52; // r8
  unsigned __int64 v53; // rbx
  int v54; // ecx
  KIRQL v55; // di
  _NET_BUFFER_LIST **p_ReceivedNblsToComplete; // rcx
  _SLIST_HEADER *j; // rdx
  struct _VF_NDIS_DISPATCH_TABLE *v58; // rax
  __int64 v59; // r8
  unsigned __int64 v60; // rsi
  unsigned __int64 v61; // rdx
  struct _VF_NDIS_DISPATCH_TABLE *v62; // rax
  __int64 v63; // r8
  unsigned __int64 v64; // rbx
  unsigned __int64 v65; // rax
  struct _NET_BUFFER_LIST *Alignment; // rax
  char v67; // [rsp+40h] [rbp-A8h]
  KIRQL v68; // [rsp+41h] [rbp-A7h]
  __int64 v69; // [rsp+48h] [rbp-A0h]
  int v70; // [rsp+50h] [rbp-98h]
  unsigned int Number; // [rsp+54h] [rbp-94h]
  __int64 v72; // [rsp+58h] [rbp-90h]
  unsigned __int64 v73; // [rsp+58h] [rbp-90h]
  Rtl::KString *value; // [rsp+60h] [rbp-88h]
  unsigned __int64 LowLimit; // [rsp+68h] [rbp-80h] BYREF
  unsigned __int64 HighLimit; // [rsp+70h] [rbp-78h] BYREF
  void (__fastcall *v77)(unsigned __int64, unsigned __int64, __int64); // [rsp+78h] [rbp-70h]
  struct _NET_BUFFER_LIST *v78; // [rsp+80h] [rbp-68h]
  __int64 v79; // [rsp+88h] [rbp-60h]
  unsigned int v80; // [rsp+90h] [rbp-58h]
  int v81; // [rsp+94h] [rbp-54h]
  _UNKNOWN *retaddr; // [rsp+E8h] [rbp+0h] BYREF
  struct _NET_BUFFER_LIST *v84; // [rsp+F8h] [rbp+10h]
  unsigned int v85; // [rsp+F8h] [rbp+10h]
  unsigned int v86; // [rsp+F8h] [rbp+10h]
  unsigned int v87; // [rsp+100h] [rbp+18h]

  v87 = a3;
  v84 = a2;
  v4 = a4;
  v5 = a2;
  v6 = a1;
  if ( LODWORD(a1->FilterFriendlyName) || (value = 0, LOBYTE(v70) = 0, *(_DWORD *)&a1->Ref.ReferenceCount) )
  {
    v70 = *(_DWORD *)&a1->Ref.ReferenceCount;
    value = a1->FilterInstanceName.__ptr_.__value_;
    if ( !value )
      value = a1->FilterInstanceName.__ptr_.__value_;
  }
  for ( i = a2; i; i = (struct _NET_BUFFER_LIST *)i->Link.Alignment )
    i->Flags = i->Flags & 0xFFFFFFF4 | 8;
  if ( (Microsoft_Windows_Networking_CorrelationEnabled || byte_140123720) && a2 )
  {
    Alignment = a2;
    if ( byte_140123720 )
    {
      do
      {
        Alignment->NetBufferListInfo[13] = 0;
        Alignment = (struct _NET_BUFFER_LIST *)Alignment->Link.Alignment;
      }
      while ( Alignment );
    }
    else
    {
      do
      {
        Alignment->NetBufferListInfo[13] = (void *)((unsigned __int64)Alignment->NetBufferListInfo[13]
                                                  | 0x8000000000000000uLL);
        Alignment = (struct _NET_BUFFER_LIST *)Alignment->Link.Alignment;
      }
      while ( Alignment );
    }
  }
  if ( *(_DWORD *)&v6[2].XState )
  {
    v8 = 0;
    if ( a2 )
    {
      p_Alignment = 0;
      do
      {
        v10 = (struct _NET_BUFFER_LIST *)v5->Link.Alignment;
        v5->Link.Alignment = 0;
        if ( v5->NdisPoolHandle == PoolHandle )
        {
          _InterlockedDecrement((volatile signed __int32 *)&v6[2].XState);
          FirstNetBuffer = v5->FirstNetBuffer;
          v12 = (struct _NPAGED_LOOKASIDE_LIST *)v5->MiniportReserved[1];
          CurrentMdl = FirstNetBuffer->CurrentMdl;
          if ( (CurrentMdl->MdlFlags & 0x20) != 0 )
            MmUnmapLockedPages(CurrentMdl->MappedSystemVa, FirstNetBuffer->CurrentMdl);
          if ( v12 )
            ExFreeToNPagedLookasideList(v12, CurrentMdl);
          else
            ExFreePoolWithTag(CurrentMdl, 0);
          NdisFreeNetBufferList(v5);
        }
        else
        {
          if ( v8 )
            *p_Alignment = v5;
          else
            v8 = v5;
          p_Alignment = &v5->Link.Alignment;
        }
        v5 = v10;
      }
      while ( v10 );
      v4 = a4;
      LOBYTE(a3) = v87;
    }
    v5 = v8;
    v84 = v8;
  }
  if ( !v5 )
    return;
  Number = -1;
  v68 = 2;
  if ( !*(_DWORD *)ndisNblTrackerMode )
    goto LABEL_51;
  v14 = *(_QWORD *)&v6[1].NicSwitchHwCapabilities.MaxNumQueuePairsForDefaultVPort;
  v15 = a3 & 1;
  if ( v4 )
    NblTracker = v4->NblTracker;
  else
    NblTracker = 0;
  v17 = ndisNblTrackerEpoch;
  LowLimit = (unsigned __int64)NblTracker;
  v18 = 0;
  v72 = 0;
  v19 = 0;
  v69 = 0;
  v67 = 0;
  if ( *(int *)ndisNblTrackerMode >= 3 )
  {
    ndisNblTrackerRecordEventInternal(v5, NblTracker, 0x87u, (void *)v14, v15);
    v19 = 0;
  }
  v20 = v14 & 0xFFFFFFFFFFFFFFFDuLL;
  if ( (v14 & 1) != 0 )
  {
    v21 = (2 * v17) ^ ((2 * v17) ^ v14) & 0xFFFFFFFFFFFFFFFDuLL;
    v20 = *(_QWORD *)((v20 & 0xFFFFFFFFFFFFFFF8uLL) + 24);
  }
  else
  {
    v21 = v14 & 0xFFFFFFFFFFFFFFFDuLL;
  }
  v22 = LowLimit;
  v23 = (_SLIST_HEADER *)v5;
  do
  {
    Region = v23[22].Region;
    while ( v23[22].Region == Region )
    {
      if ( Region )
      {
        if ( (Region & 4) != 0 )
          goto LABEL_108;
      }
      else if ( !v23[7].Region )
      {
        v65 = v22 & 0xFFFFFFFFFFFFFFFDuLL;
        if ( (v22 & 1) != 0 )
          v65 = *(_QWORD *)((v22 & 0xFFFFFFFFFFFFFFF8uLL) + 24);
        v23[7].Region = v65;
      }
      v25 = (char *)v23[7].Region;
      if ( v25 )
      {
        LODWORD(NblTracker) = (unsigned __int8)*v25;
        if ( (unsigned __int8)((_BYTE)NblTracker - 17) <= 1u || (_BYTE)NblTracker == 5 )
        {
          if ( v25 != (char *)v20 || v23[1].Region )
          {
            ++v18;
            v26 = v21;
          }
          else
          {
            ++v19;
            v26 = 24;
            v69 = v19;
            ++v18;
          }
          goto LABEL_36;
        }
        if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(NblTracker) = 3;
          WPP_RECORDER_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            (int)NblTracker,
            27,
            12,
            (struct _GUID *)&WPP_78a33c75b2d2335d1cf1dcc315edf7b8_Traceguids,
            (char)v23,
            *v25);
LABEL_144:
          v19 = v69;
        }
      }
      else if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(NblTracker) = 3;
        WPP_RECORDER_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          (int)NblTracker,
          27,
          11,
          (struct _GUID *)&WPP_78a33c75b2d2335d1cf1dcc315edf7b8_Traceguids,
          (char)v23);
        goto LABEL_144;
      }
LABEL_108:
      v26 = v21 | 4;
LABEL_36:
      v23[22].Region = v26;
      v23 = (_SLIST_HEADER *)v23->Alignment;
      if ( !v23 )
        break;
    }
    if ( (Region & 1) == 0 )
      goto LABEL_42;
    v27 = v72 - v18;
    v73 = v72 - v18;
    if ( !v73 )
      goto LABEL_42;
    if ( (_BYTE)v15 || v67 )
    {
      NblTracker = (struct NDIS_NBL_TRACKER_HANDLE__ *)((Region & 0xFFFFFFFFFFFFFFF8uLL) + 16
                                                                                         * (((Region >> 1) & 1) + 3));
      if ( !(_BYTE)v15 )
        goto LABEL_70;
      goto LABEL_41;
    }
    v67 = 1;
    CurrentIrql = KeGetCurrentIrql();
    v27 = v73;
    v43 = Region;
    v44 = Region & 0xFFFFFFFFFFFFFFF8uLL;
    v45 = 16 * (((v43 >> 1) & 1) + 3);
    if ( CurrentIrql == 2 )
    {
      LOBYTE(v15) = 1;
      NblTracker = (struct NDIS_NBL_TRACKER_HANDLE__ *)(v44 + v45);
LABEL_41:
      v28 = KeGetPcr()->Prcb.Number << 12;
      *(_QWORD *)(v28 + *(_QWORD *)NblTracker) += v27;
      goto LABEL_42;
    }
    LOBYTE(v15) = 0;
    NblTracker = (struct NDIS_NBL_TRACKER_HANDLE__ *)(v44 + v45);
LABEL_70:
    _InterlockedAdd64((volatile signed __int64 *)NblTracker + 1, v27);
LABEL_42:
    v19 = v69;
    v72 = v18;
  }
  while ( v23 );
  v5 = v84;
  v6 = a1;
  if ( (v21 & 1) != 0 )
  {
    v29 = v18 - v69;
    if ( v29 )
    {
      if ( (_BYTE)v15 || v67 )
      {
        v31 = (v21 & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((v21 >> 1) & 1) + 3);
        if ( (_BYTE)v15 )
          goto LABEL_50;
LABEL_48:
        _InterlockedAdd64((volatile signed __int64 *)(v31 + 8), v29);
      }
      else
      {
        v30 = KeGetCurrentIrql();
        v31 = (v21 & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((v21 >> 1) & 1) + 3);
        if ( v30 != 2 )
          goto LABEL_48;
LABEL_50:
        v32 = KeGetPcr()->Prcb.Number << 12;
        *(_QWORD *)(v32 + *(_QWORD *)v31) += v29;
      }
    }
  }
LABEL_51:
  v33 = v70 & 0x20;
  if ( (v70 & 0x20) != 0 )
  {
    if ( (v87 & 1) == 0 )
      v68 = KfRaiseIrql(2u);
    Number = KeGetPcr()->Prcb.Number;
    v33 = __rdtsc();
    *(wchar_t **)((char *)&value[21].Buffer + ndisPcwPerCpuDataStride * Number + ndisPcwOffsetToPerCpuData) = (wchar_t *)v33;
  }
  v34 = *(_QWORD *)&v6[1].NicSwitchCurrentCapabilities.Flags;
  v35 = *(void (__fastcall **)(unsigned __int64, unsigned __int64, __int64))&v6[1].NicSwitchCurrentCapabilities.NdisReserved14;
  v36 = *(_QWORD *)&v6[1].NicSwitchHwCapabilities.NumberOfIndirectionTableEntriesForDefaultVPort;
  if ( *(_BYTE *)v34 == 17 )
    goto LABEL_60;
  if ( (v87 & 1) != 0 || KeGetCurrentIrql() == 2 )
  {
    LODWORD(v33) = KeGetPcr()->Prcb.Number;
    p_LowLimit = &LowLimit;
    v86 = v33;
    v77 = 0;
    LowLimit = (unsigned __int64)v5;
    HighLimit = (unsigned __int64)v5;
    v5->Scratch = 0;
    v5->ChildRefCount = v87;
    while ( *(_BYTE *)v34 == 5 )
    {
      v47 = *p_LowLimit;
      if ( !*p_LowLimit )
        break;
      v48 = *(_QWORD *)(v34 + 424) + 96 * v33;
      if ( *(_BYTE *)(v48 + 88) )
      {
        *p_LowLimit = 0;
        do
        {
          v58 = ndisVerifierNdisDispatch;
          v59 = *(unsigned int *)(v47 + 132);
          v60 = *(_QWORD *)(v47 + 112);
          *(_DWORD *)(v47 + 132) = 0;
          if ( v58 && *(_BYTE *)v34 == 5 && *(_QWORD *)(v34 + 776) )
            (*((void (__fastcall **)(unsigned __int64, unsigned __int64, __int64))v58 + 17))(v36, v47, v59);
          else
            v35(v36, v47, v59);
          v47 = v60;
        }
        while ( v60 );
        break;
      }
      *(_BYTE *)(v48 + 88) = 1;
      v49 = v34;
      v50 = *p_LowLimit;
      *p_LowLimit = 0;
      if ( v50 )
      {
        do
        {
          v51 = ndisVerifierNdisDispatch;
          v52 = *(unsigned int *)(v50 + 132);
          v53 = *(_QWORD *)(v50 + 112);
          *(_DWORD *)(v50 + 132) = 0;
          if ( v51 && *(_BYTE *)v34 == 5 && *(_QWORD *)(v34 + 776) )
            (*((void (__fastcall **)(unsigned __int64, unsigned __int64, __int64))v51 + 17))(v36, v50, v52);
          else
            v35(v36, v50, v52);
          v50 = v53;
        }
        while ( v53 );
      }
      v33 = v86;
      p_LowLimit = (unsigned __int64 *)(v48 + 72);
      *(_BYTE *)(v48 + 88) = 0;
      v34 = *(_QWORD *)(v34 + 552);
      v35 = *(void (__fastcall **)(unsigned __int64, unsigned __int64, __int64))(v49 + 528);
      v36 = *(_QWORD *)(v49 + 536);
    }
    v61 = *p_LowLimit;
    if ( *p_LowLimit )
    {
      *p_LowLimit = 0;
      do
      {
        v62 = ndisVerifierNdisDispatch;
        v63 = *(unsigned int *)(v61 + 132);
        v64 = *(_QWORD *)(v61 + 112);
        *(_DWORD *)(v61 + 132) = 0;
        if ( v62 && *(_BYTE *)v34 == 5 && *(_QWORD *)(v34 + 776) )
          (*((void (__fastcall **)(unsigned __int64, unsigned __int64, __int64))v62 + 17))(v36, v61, v63);
        else
          v35(v36, v61, v63);
        v61 = v64;
      }
      while ( v64 );
    }
  }
  else
  {
    if ( v6->Header.Type != 5 )
      goto LABEL_60;
    v85 = Size;
    LowLimit = 0;
    HighLimit = 0;
    v37 = KeGetPcr()->Prcb.Number << 12;
    v38 = *(_QWORD *)(v37 + qword_140122F78);
    LowLimit = v38;
    HighLimit = *(_QWORD *)(v37 + qword_140122F70);
    if ( (unsigned __int64)&retaddr >= HighLimit || v38 > (unsigned __int64)&retaddr )
    {
      IoGetStackLimits(&LowLimit, &HighLimit);
      v38 = LowLimit;
    }
    if ( (unsigned __int64)&retaddr - v38 < v85 )
    {
      v54 = 24576;
      v80 = v87;
      v81 = 0;
      LowLimit = v34;
      HighLimit = v36;
      v77 = v35;
      v78 = v5;
      v79 = 0;
      if ( (unsigned int)Size > 0x6000 )
        v54 = Size;
      if ( KeExpandKernelStackAndCalloutEx(
             ndisDataPathExpandStackCallback<3,void (void *,_NET_BUFFER_LIST *,unsigned long)>,
             &LowLimit,
             v54,
             0,
             0) < 0 )
      {
        if ( *(_DWORD *)ndisNblTrackerMode )
          ndisNblTrackerTransferOwnershipInternal(
            v5,
            v6->NblTracker,
            (struct NDIS_NBL_TRACKER_HANDLE__ *)0xA0,
            (enum _NDIS_NBL_TRACKER_OWNERSHIP_EVENT)1,
            0);
        v55 = KeAcquireSpinLockRaiseToDpc(&v6->Lock);
        v6->LockThread = KeGetCurrentThread();
        p_ReceivedNblsToComplete = &v6->StackExpansionFallback.PendingWork.ReceivedNblsToComplete;
        for ( j = (_SLIST_HEADER *)v6->StackExpansionFallback.PendingWork.ReceivedNblsToComplete;
              j;
              j = (_SLIST_HEADER *)j->Alignment )
        {
          p_ReceivedNblsToComplete = (_NET_BUFFER_LIST **)j;
        }
        *p_ReceivedNblsToComplete = v5;
        ndisQueueStackExpansionFallbackWorkItem(v6);
        v6->LockThread = 0;
        KeReleaseSpinLock(&v6->Lock, v55);
      }
    }
    else
    {
      if ( ndisVerifierNdisDispatch && *(_BYTE *)v34 == 5 && *(_QWORD *)(v34 + 776) )
      {
        (*((void (__fastcall **)(unsigned __int64, struct _NET_BUFFER_LIST *, _QWORD))ndisVerifierNdisDispatch + 17))(
          v36,
          v5,
          v87);
        goto LABEL_61;
      }
LABEL_60:
      v35(v36, (unsigned __int64)v5, v87);
    }
  }
LABEL_61:
  if ( (v70 & 0x20) != 0 )
  {
    v39 = Number;
    if ( Number == -1 )
      v39 = KeGetPcr()->Prcb.Number;
    v40 = (char *)value + ndisPcwPerCpuDataStride * v39 + ndisPcwOffsetToPerCpuData;
    v41 = __rdtsc();
    *((_QWORD *)v40 + 18) += (((unsigned __int64)HIDWORD(v41) << 32) | (unsigned int)v41) - *((_QWORD *)v40 + 43);
    *((_QWORD *)v40 + 43) = 0;
    if ( v68 != 2 )
      KeLowerIrql(v68);
  }
}

```

## disassembly

```asm
0x140022720  mov     [rsp+arg_18], r9
0x140022725  mov     [rsp+arg_10], r8d
0x14002272a  mov     [rsp+arg_8], rdx
0x14002272f  mov     [rsp+arg_0], rcx
0x140022734  push    rbp
0x140022735  push    rsi
0x140022736  push    r13
0x140022738  push    r14
0x14002273a  sub     rsp, 0C8h
0x140022741  xor     ebp, ebp
0x140022743  mov     r13, r9
0x140022746  mov     rsi, rdx
0x140022749  mov     r14, rcx
0x14002274c  cmp     [rcx+30h], ebp
0x14002274f  jnz     loc_140022EB4
0x140022755  mov     [rsp+0E8h+var_88], rbp
0x14002275a  mov     [rsp+0E8h+var_98], ebp
0x14002275e  cmp     [rcx+50h], ebp
0x140022761  jnz     loc_140022EB4
0x140022767  mov     rcx, rdx
0x14002276a  test    rdx, rdx
0x14002276d  jz      short loc_140022789
0x14002276f  mov     eax, [rcx+88h]
0x140022775  and     eax, 0FFFFFFFCh
0x140022778  or      eax, 8
0x14002277b  mov     [rcx+88h], eax
0x140022781  mov     rcx, [rcx]
0x140022784  test    rcx, rcx
0x140022787  jnz     short loc_14002276F
0x140022789  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14002278f  test    eax, eax
0x140022791  jnz     loc_140022FD7
0x140022797  cmp     cs:byte_140123720, al
0x14002279d  jnz     loc_140022FD7
0x1400227a3  cmp     dword ptr [r14+0C98h], 0
0x1400227ab  mov     [rsp+0E8h+var_28], rbx
0x1400227b3  mov     [rsp+0E8h+var_30], rdi
0x1400227bb  mov     [rsp+0E8h+var_38], r12
0x1400227c3  mov     [rsp+0E8h+var_40], r15
0x1400227cb  jz      loc_140022858
0x1400227d1  mov     r12, rbp
0x1400227d4  test    rdx, rdx
0x1400227d7  jz      short loc_14002284D
0x1400227d9  mov     r13, rbp
0x1400227dc  mov     rbx, [rsi]
0x1400227df  mov     [rsi], rbp
0x1400227e2  mov     rax, cs:PoolHandle
0x1400227e9  cmp     [rsi+20h], rax
0x1400227ed  jnz     loc_140023147
0x1400227f3  lock dec dword ptr [r14+0C98h]
0x1400227fb  mov     rax, [rsi+8]
0x1400227ff  mov     rdi, [rsi+68h]
0x140022803  mov     r15, [rax+8]
0x140022807  test    byte ptr [r15+0Ah], 20h
0x14002280c  jnz     loc_14002312F
0x140022812  test    rdi, rdi
0x140022815  jz      loc_140023016
0x14002281b  mov     rdx, r15; Entry
0x14002281e  mov     rcx, rdi; Lookaside
0x140022821  call    cs:__imp_ExFreeToNPagedLookasideList
0x140022828  nop     dword ptr [rax+rax+00h]
0x14002282d  mov     rcx, rsi; NetBufferList
0x140022830  call    NdisFreeNetBufferList
0x140022835  mov     rsi, rbx
0x140022838  test    rbx, rbx
0x14002283b  jnz     short loc_1400227DC
0x14002283d  mov     r13, [rsp+0E8h+arg_18]
0x140022845  mov     r8d, [rsp+0E8h+arg_10]
0x14002284d  mov     rsi, r12
0x140022850  mov     [rsp+0E8h+arg_8], r12
0x140022858  test    rsi, rsi
0x14002285b  jz      loc_140022BD8
0x140022861  mov     eax, cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x140022867  mov     ecx, 0FFFFFFFFh
0x14002286c  mov     [rsp+0E8h+var_94], ecx
0x140022870  mov     [rsp+0E8h+var_A7], 2
0x140022875  test    eax, eax
0x140022877  jz      loc_140022A6B
0x14002287d  mov     rbx, [r14+9E8h]
0x140022884  mov     r15d, r8d
0x140022887  and     r15d, 1
0x14002288b  test    r13, r13
0x14002288e  jz      loc_14002300E
0x140022894  mov     rdx, [r13+248h]; struct NDIS_NBL_TRACKER_HANDLE__ *
0x14002289b  mov     edi, cs:?ndisNblTrackerEpoch@@3KA; ulong ndisNblTrackerEpoch
0x1400228a1  xor     cl, cl
0x1400228a3  mov     [rsp+0E8h+LowLimit], rdx
0x1400228a8  mov     r12, rbp
0x1400228ab  mov     [rsp+0E8h+var_90], rbp
0x1400228b0  mov     r8, rbp
0x1400228b3  mov     [rsp+0E8h+var_A0], rbp
0x1400228b8  mov     [rsp+0E8h+var_A8], cl
0x1400228bc  cmp     eax, 3
0x1400228bf  jl      short loc_1400228DA
0x1400228c1  mov     r9, rbx; void *
0x1400228c4  mov     dword ptr [rsp+0E8h+Context], r15d; unsigned int
0x1400228c9  mov     r8d, 87h; unsigned int
0x1400228cf  mov     rcx, rsi; struct _NET_BUFFER_LIST *
0x1400228d2  call    ?ndisNblTrackerRecordEventInternal@@YAXPEAU_NET_BUFFER_LIST@@PEAUNDIS_NBL_TRACKER_HANDLE__@@KPEAXK@Z; ndisNblTrackerRecordEventInternal(_NET_BUFFER_LIST *,NDIS_NBL_TRACKER_HANDLE__ *,ulong,void *,ulong)
0x1400228d7  mov     r8, rbp
0x1400228da  mov     r13, rbx
0x1400228dd  and     r13, 0FFFFFFFFFFFFFFFDh
0x1400228e1  test    r13b, 1
0x1400228e5  jz      loc_140022EFB
0x1400228eb  mov     rax, rdi
0x1400228ee  add     rax, rax
0x1400228f1  xor     rbx, rax
0x1400228f4  and     rbx, 0FFFFFFFFFFFFFFFDh
0x1400228f8  xor     rbx, rax
0x1400228fb  and     r13, 0FFFFFFFFFFFFFFF8h
0x1400228ff  mov     r13, [r13+18h]
0x140022903  mov     rbp, [rsp+0E8h+LowLimit]
0x140022908  lea     r9, WPP_RECORDER_INITIALIZED
0x14002290f  mov     r14, rsi
0x140022912  mov     rdi, [r14+168h]
0x140022919  lea     rsi, WPP_78a33c75b2d2335d1cf1dcc315edf7b8_Traceguids
0x140022920  cmp     [r14+168h], rdi
0x140022927  jnz     short loc_140022975
0x140022929  test    rdi, rdi
0x14002292c  jz      loc_140022F03
0x140022932  test    dil, 4
0x140022936  jnz     loc_140022F37
0x14002293c  mov     rcx, [r14+78h]
0x140022940  test    rcx, rcx
0x140022943  jz      loc_140022F2A
0x140022949  movzx   edx, byte ptr [rcx]
0x14002294c  lea     eax, [rdx-11h]
0x14002294f  cmp     al, 1
0x140022951  ja      loc_140022F93
0x140022957  cmp     rcx, r13
0x14002295a  jz      loc_140022EDB
0x140022960  inc     r12
0x140022963  mov     rax, rbx
0x140022966  mov     [r14+168h], rax
0x14002296d  mov     r14, [r14]
0x140022970  test    r14, r14
0x140022973  jnz     short loc_140022920
0x140022975  movzx   esi, [rsp+0E8h+var_A8]
0x14002297a  test    dil, 1
0x14002297e  jz      short loc_1400229CD
0x140022980  mov     r8, [rsp+0E8h+var_90]
0x140022985  sub     r8, r12
0x140022988  mov     [rsp+0E8h+var_90], r8
0x14002298d  jz      short loc_1400229CD
0x14002298f  test    r15b, r15b
0x140022992  jz      loc_140022C07
0x140022998  mov     rdx, rdi
0x14002299b  and     rdi, 0FFFFFFFFFFFFFFF8h
0x14002299f  shr     rdx, 1
0x1400229a2  and     edx, 1
0x1400229a5  add     rdx, 3
0x1400229a9  shl     rdx, 4
0x1400229ad  add     rdx, rdi
0x1400229b0  test    r15b, r15b
0x1400229b3  jz      loc_140022C50
0x1400229b9  mov     eax, gs:1A4h
0x1400229c1  shl     eax, 0Ch
0x1400229c4  mov     ecx, eax
0x1400229c6  mov     rax, [rdx]
0x1400229c9  add     [rcx+rax], r8
0x1400229cd  mov     r8, [rsp+0E8h+var_A0]
0x1400229d2  mov     [rsp+0E8h+var_90], r12
0x1400229d7  test    r14, r14
0x1400229da  jnz     loc_140022912
0x1400229e0  mov     rsi, [rsp+0E8h+arg_8]
0x1400229e8  mov     ebp, 0
0x1400229ed  mov     r14, [rsp+0E8h+arg_0]
0x1400229f5  test    bl, 1
0x1400229f8  jz      short loc_140022A6B
0x1400229fa  sub     r12, r8
0x1400229fd  jz      short loc_140022A6B
0x1400229ff  test    r15b, r15b
0x140022a02  jnz     short loc_140022A3A
0x140022a04  cmp     [rsp+0E8h+var_A8], bpl
0x140022a09  jnz     short loc_140022A3A
0x140022a0b  call    cs:__imp_KeGetCurrentIrql
0x140022a12  nop     dword ptr [rax+rax+00h]
0x140022a17  mov     rdx, rbx
0x140022a1a  and     rbx, 0FFFFFFFFFFFFFFF8h
0x140022a1e  shr     rdx, 1
0x140022a21  and     edx, 1
0x140022a24  add     rdx, 3
0x140022a28  shl     rdx, 4
0x140022a2c  add     rdx, rbx
0x140022a2f  cmp     al, 2
0x140022a31  jz      short loc_140022A57
0x140022a33  lock add [rdx+8], r12
0x140022a38  jmp     short loc_140022A6B
0x140022a3a  mov     rdx, rbx
0x140022a3d  and     rbx, 0FFFFFFFFFFFFFFF8h
0x140022a41  shr     rdx, 1
0x140022a44  and     edx, 1
0x140022a47  add     rdx, 3
0x140022a4b  shl     rdx, 4
0x140022a4f  add     rdx, rbx
0x140022a52  test    r15b, r15b
0x140022a55  jz      short loc_140022A33
0x140022a57  mov     eax, gs:1A4h
0x140022a5f  shl     eax, 0Ch
0x140022a62  mov     ecx, eax
0x140022a64  mov     rax, [rdx]
0x140022a67  add     [rcx+rax], r12
0x140022a6b  mov     eax, [rsp+0E8h+var_98]
0x140022a6f  mov     ebx, [rsp+0E8h+arg_10]
0x140022a76  and     eax, 20h
0x140022a79  and     ebx, 1
0x140022a7c  mov     r12d, eax
0x140022a7f  test    eax, eax
0x140022a81  jnz     loc_140022F43
0x140022a87  mov     r13, [r14+9F0h]
0x140022a8e  mov     rdi, [r14+0A50h]
0x140022a95  mov     r15, [r14+9E0h]
0x140022a9c  cmp     byte ptr [r13+0], 11h
0x140022aa1  jz      loc_140022B60
0x140022aa7  test    ebx, ebx
0x140022aa9  jnz     loc_140022C5A
0x140022aaf  call    cs:__imp_KeGetCurrentIrql
0x140022ab6  nop     dword ptr [rax+rax+00h]
0x140022abb  cmp     al, 2
0x140022abd  jz      loc_140022C5A
0x140022ac3  cmp     byte ptr [r14], 5
0x140022ac7  jnz     loc_140022B60
0x140022acd  mov     eax, cs:Size
0x140022ad3  lea     rbx, [rsp+0E8h]
0x140022adb  mov     dword ptr [rsp+0E8h+arg_8], eax
0x140022ae2  mov     [rsp+0E8h+LowLimit], rbp
0x140022ae7  mov     [rsp+0E8h+HighLimit], rbp
0x140022aec  mov     eax, gs:1A4h
0x140022af4  shl     eax, 0Ch
0x140022af7  mov     ecx, eax
0x140022af9  mov     rax, cs:qword_140122F78
0x140022b00  mov     rdx, [rcx+rax]
0x140022b04  mov     rax, cs:qword_140122F70
0x140022b0b  mov     [rsp+0E8h+LowLimit], rdx
0x140022b10  mov     r8, [rcx+rax]
0x140022b14  mov     [rsp+0E8h+HighLimit], r8
0x140022b19  cmp     rbx, r8
0x140022b1c  jb      loc_140023000
0x140022b22  lea     rdx, [rsp+0E8h+HighLimit]; HighLimit
0x140022b27  lea     rcx, [rsp+0E8h+LowLimit]; LowLimit
0x140022b2c  call    cs:__imp_IoGetStackLimits
0x140022b33  nop     dword ptr [rax+rax+00h]
0x140022b38  mov     rdx, [rsp+0E8h+LowLimit]
0x140022b3d  mov     eax, dword ptr [rsp+0E8h+arg_8]
0x140022b44  sub     rbx, rdx
0x140022b47  cmp     rbx, rax
0x140022b4a  jb      loc_140022D2D
0x140022b50  mov     rax, cs:?ndisVerifierNdisDispatch@@3PEAU_VF_NDIS_DISPATCH_TABLE@@EA; _VF_NDIS_DISPATCH_TABLE * ndisVerifierNdisDispatch
0x140022b57  test    rax, rax
0x140022b5a  jnz     loc_1400230F0
0x140022b60  mov     r8d, [rsp+0E8h+arg_10]
0x140022b68  mov     rdx, rsi
0x140022b6b  mov     rcx, r15
0x140022b6e  mov     rax, rdi
0x140022b71  call    _guard_dispatch_icall
0x140022b76  test    r12d, r12d
0x140022b79  jz      short loc_140022BD8
0x140022b7b  mov     eax, [rsp+0E8h+var_94]
0x140022b7f  cmp     eax, 0FFFFFFFFh
0x140022b82  jnz     short loc_140022B8C
0x140022b84  mov     eax, gs:1A4h
0x140022b8c  imul    eax, cs:?ndisPcwPerCpuDataStride@@3KA; ulong ndisPcwPerCpuDataStride
0x140022b93  mov     r8d, cs:?ndisPcwOffsetToPerCpuData@@3KA; ulong ndisPcwOffsetToPerCpuData
0x140022b9a  add     rax, [rsp+0E8h+var_88]
0x140022b9f  add     r8, rax
0x140022ba2  rdtsc
0x140022ba4  shl     rdx, 20h
0x140022ba8  or      rax, rdx
0x140022bab  sub     rax, [r8+158h]
0x140022bb2  add     [r8+90h], rax
0x140022bb9  movzx   eax, [rsp+0E8h+var_A7]
0x140022bbe  mov     [r8+158h], rbp
0x140022bc5  cmp     al, 2
0x140022bc7  jz      short loc_140022BD8
0x140022bc9  movzx   ecx, al; NewIrql
0x140022bcc  call    cs:__imp_KeLowerIrql
0x140022bd3  nop     dword ptr [rax+rax+00h]
0x140022bd8  mov     r15, [rsp+0E8h+var_40]
0x140022be0  mov     r12, [rsp+0E8h+var_38]
0x140022be8  mov     rdi, [rsp+0E8h+var_30]
0x140022bf0  mov     rbx, [rsp+0E8h+var_28]
0x140022bf8  add     rsp, 0C8h
0x140022bff  pop     r14
0x140022c01  pop     r13
0x140022c03  pop     rsi
0x140022c04  pop     rbp
0x140022c05  retn
0x140022c07  test    sil, sil
0x140022c0a  jnz     loc_140022998
0x140022c10  mov     [rsp+0E8h+var_A8], 1
0x140022c15  call    cs:__imp_KeGetCurrentIrql
0x140022c1c  nop     dword ptr [rax+rax+00h]
0x140022c21  mov     r8, [rsp+0E8h+var_90]
0x140022c26  lea     r9, WPP_RECORDER_INITIALIZED
0x140022c2d  mov     rdx, rdi
0x140022c30  and     rdi, 0FFFFFFFFFFFFFFF8h
0x140022c34  shr     rdx, 1
0x140022c37  and     edx, 1
0x140022c3a  add     rdx, 3
0x140022c3e  shl     rdx, 4
  ... truncated ...
```
