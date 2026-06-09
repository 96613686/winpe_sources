# ndisMIndicateNetBufferListsToOpen(_NDIS_OPEN_BLOCK *,_NET_BUFFER_LIST *,ulong,ulong,ulong)

- ea: `0x14000b750`
- end: `0x14000cab7`
- name: `?ndisMIndicateNetBufferListsToOpen@@YAXPEAU_NDIS_OPEN_BLOCK@@PEAU_NET_BUFFER_LIST@@KKK@Z`
- size: `4967`
- prototype: `void __usercall(struct _NDIS_OPEN_BLOCK *@<rcx>, struct _NET_BUFFER_LIST *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int)`
- caller_count: `7`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140004d70`
- `0x1400054e0`
- `0x140005a30`
- `0x14000a600`
- `0x14000a9b0`
- `0x14000aac0`
- `0x14000ab60`

## callees

- `0x140009e70`
- `0x14000a5a0`
- `0x14000b750`
- `0x14000de20`
- `0x140014250`
- `0x140014280`
- `0x14002ddf0`
- `0x140046270`
- `0x1400464e0`
- `0x14004bb70`
- `0x1400615a0`
- `0x14009fa38`
- `0x1400e6240`
- `0x1400e65c0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14000b8b3`
- `ntoskrnl!KfRaiseIrql` at `0x14000c1bc`
- `ntoskrnl!KfRaiseIrql` at `0x14000c7a7`
- `ntoskrnl!KfRaiseIrql` at `0x14000b8b3`
- `ntoskrnl!KfRaiseIrql` at `0x14000c1bc`
- `ntoskrnl!KfRaiseIrql` at `0x14000c7a7`
- `ntoskrnl!KeLowerIrql` at `0x14000b962`
- `ntoskrnl!KeLowerIrql` at `0x14000bba8`
- `ntoskrnl!KeLowerIrql` at `0x14000bebe`
- `ntoskrnl!KeLowerIrql` at `0x14000c676`
- `ntoskrnl!KeLowerIrql` at `0x14000b962`
- `ntoskrnl!KeLowerIrql` at `0x14000bba8`
- `ntoskrnl!KeLowerIrql` at `0x14000bebe`
- `ntoskrnl!KeLowerIrql` at `0x14000c676`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000baf8`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000c5d1`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000baf8`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000c5d1`
- `ntoskrnl!IoWMIWriteEvent` at `0x14000bdd8`
- `ntoskrnl!IoWMIWriteEvent` at `0x14000bdd8`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000c994`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000ca0b`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000c994`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000ca0b`
- `ntoskrnl!WmiGetClock` at `0x14000bd51`
- `ntoskrnl!WmiGetClock` at `0x14000c05b`
- `ntoskrnl!WmiGetClock` at `0x14000ca89`
- `ntoskrnl!WmiGetClock` at `0x14000bd51`
- `ntoskrnl!WmiGetClock` at `0x14000c05b`
- `ntoskrnl!WmiGetClock` at `0x14000ca89`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000ba51`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000c511`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000ba51`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000c511`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000c12d`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000c712`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000c12d`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000c712`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c216`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c808`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c216`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c808`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c1a5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c78f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c1a5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c78f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c155`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c73a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c155`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c73a`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14000bfce`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14000bfce`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14000c02d`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14000c02d`

## pseudocode

```c
void __fastcall ndisMIndicateNetBufferListsToOpen(
        struct _NDIS_OPEN_BLOCK *a1,
        struct _NET_BUFFER_LIST *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5)
{
  _NDIS_MINIPORT_BLOCK *MiniportHandle; // r14
  struct _NDIS_OPEN_BLOCK *v6; // rbx
  struct _NET_BUFFER_LIST *Alignment; // rsi
  int PcwDatapathCycleMask; // r12d
  struct _NDIS_OPEN_BLOCK *SourceHandle; // rcx
  _NET_BUFFER_LIST **Flags; // r8
  bool v11; // dl
  unsigned int v12; // r13d
  int v13; // r15d
  __int16 v14; // r9
  KIRQL v15; // al
  wchar_t *v16; // r15
  unsigned int Number; // r10d
  unsigned int v18; // r8d
  int v19; // r12d
  struct _NET_BUFFER_LIST *v20; // rcx
  struct _NET_BUFFER_LIST *v21; // rcx
  _QWORD *p_Alignment; // rdx
  struct _NET_BUFFER_LIST *v23; // r15
  _NET_BUFFER *FirstNetBuffer; // rax
  struct _NPAGED_LOOKASIDE_LIST *v25; // rcx
  _MDL *CurrentMdl; // r13
  unsigned int v27; // ebx
  unsigned int v28; // r15d
  KIRQL v29; // r12
  struct _NDIS_FILTER_BLOCK *v30; // r13
  __int64 v31; // rcx
  __int64 v32; // rdx
  char *v33; // r8
  unsigned __int64 v34; // rax
  __int64 v35; // r8
  volatile unsigned int v36; // eax
  volatile unsigned int v37; // eax
  unsigned __int16 v38; // ax
  __int64 v39; // rax
  __int64 v40; // rcx
  _SLIST_HEADER *v41; // r15
  unsigned int v42; // eax
  unsigned __int64 v43; // rax
  _PKTMON_COMPONENT_CONTEXT *CompContext; // rax
  bool v45; // zf
  _PKTMON_PACKET_TYPE PacketType; // r15d
  void *EdgeHandle; // rdx
  int v48; // ecx
  KIRQL v49; // al
  _QWORD *v50; // rdx
  KIRQL v51; // r13
  _QWORD *j; // r8
  unsigned int v53; // r9d
  _NDIS_OBJECT_HEADER *ReturnNetBufferListsObject; // r11
  unsigned __int64 v55; // rax
  void *v56; // r10
  void (__fastcall *v57)(void *, _NET_BUFFER_LIST *, unsigned int); // r9
  _NET_BUFFER_LIST *v58; // rdx
  __int64 v59; // rax
  _NDIS_OBJECT_HEADER *v60; // rcx
  _NET_BUFFER_LIST *v61; // rdx
  struct _VF_NDIS_DISPATCH_TABLE *v62; // rax
  __int64 v63; // r8
  _NET_BUFFER_LIST *v64; // r15
  struct _VF_NDIS_DISPATCH_TABLE *v65; // rax
  __int64 ChildRefCount; // r8
  _NET_BUFFER_LIST *Scratch; // r15
  _NET_BUFFER_LIST *v68; // rdx
  struct _VF_NDIS_DISPATCH_TABLE *v69; // rax
  __int64 v70; // r8
  _NET_BUFFER_LIST *v71; // r15
  PNET_BUFFER_LIST v72; // rcx
  struct _NET_BUFFER_LIST *v73; // rdx
  struct _NET_BUFFER_LIST *v74; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v75; // rcx
  __int64 v76; // r8
  PNET_BUFFER_LIST v77; // r15
  unsigned int v78; // eax
  unsigned __int64 v79; // rax
  int v80; // ecx
  KIRQL v81; // al
  _QWORD *p_TargetInfoAsUlong; // rcx
  _QWORD *v83; // rdx
  KIRQL v84; // al
  __int64 v85; // rcx
  unsigned int v86; // r9d
  _QWORD *v87; // rax
  PVOID Context; // [rsp+20h] [rbp-E0h]
  int v89; // [rsp+28h] [rbp-D8h]
  int v90; // [rsp+30h] [rbp-D0h]
  int v91; // [rsp+38h] [rbp-C8h]
  int v92; // [rsp+40h] [rbp-C0h]
  _NET_BUFFER_LIST **v93; // [rsp+40h] [rbp-C0h]
  _NDIS_OBJECT_HEADER *v94; // [rsp+40h] [rbp-C0h]
  _NDIS_OBJECT_HEADER *v95; // [rsp+48h] [rbp-B8h]
  __int64 v96; // [rsp+48h] [rbp-B8h]
  void (__fastcall *ReturnNetBufferListsHandler)(void *, _NET_BUFFER_LIST *, unsigned int); // [rsp+50h] [rbp-B0h]
  PNET_BUFFER_LIST v98; // [rsp+50h] [rbp-B0h]
  void *ReturnNetBufferListsContext; // [rsp+58h] [rbp-A8h]
  struct _NPAGED_LOOKASIDE_LIST *v100; // [rsp+58h] [rbp-A8h]
  wchar_t *Buffer; // [rsp+60h] [rbp-A0h]
  wchar_t *v102; // [rsp+60h] [rbp-A0h]
  unsigned int v103; // [rsp+68h] [rbp-98h]
  int v104; // [rsp+68h] [rbp-98h]
  _NDIS_MINIPORT_BLOCK *v105; // [rsp+70h] [rbp-90h]
  __int64 Clock; // [rsp+70h] [rbp-90h]
  struct _NPAGED_LOOKASIDE_LIST *v107; // [rsp+70h] [rbp-90h]
  int v108; // [rsp+70h] [rbp-90h]
  int PcwDatapathEventMask; // [rsp+78h] [rbp-88h]
  _BYTE WnodeEventItem[40]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v111; // [rsp+A8h] [rbp-58h]
  int v112; // [rsp+ACh] [rbp-54h]
  int v113; // [rsp+B0h] [rbp-50h]
  unsigned int v114; // [rsp+B4h] [rbp-4Ch]
  __int64 v115; // [rsp+B8h] [rbp-48h]
  unsigned int v116; // [rsp+C0h] [rbp-40h]
  int v117; // [rsp+C4h] [rbp-3Ch]
  struct _NET_BUFFER_LIST *v118; // [rsp+D0h] [rbp-30h]
  wchar_t *v119; // [rsp+D8h] [rbp-28h]
  PNET_BUFFER_LIST NetBufferList; // [rsp+E0h] [rbp-20h] BYREF
  PNET_BUFFER_LIST *p_NetBufferList; // [rsp+E8h] [rbp-18h]
  int v122; // [rsp+F0h] [rbp-10h]
  __int64 v123; // [rsp+F8h] [rbp-8h]
  _QWORD v124[49]; // [rsp+100h] [rbp+0h] BYREF
  KIRQL v126; // [rsp+2D0h] [rbp+1D0h]
  struct _NET_BUFFER_LIST *v127; // [rsp+2D0h] [rbp+1D0h]
  __int64 v128; // [rsp+2D0h] [rbp+1D0h]
  KIRQL i; // [rsp+2D0h] [rbp+1D0h]
  char v130; // [rsp+2D8h] [rbp+1D8h]
  struct _NET_BUFFER_LIST *v131; // [rsp+2D8h] [rbp+1D8h]
  void (__fastcall *v132)(__int64, struct _NET_BUFFER_LIST *, _QWORD); // [rsp+2D8h] [rbp+1D8h]
  PNET_BUFFER_LIST v133; // [rsp+2D8h] [rbp+1D8h]
  KIRQL v134; // [rsp+2D8h] [rbp+1D8h]

  MiniportHandle = a1->MiniportHandle;
  v6 = a1;
  v105 = MiniportHandle;
  Alignment = a2;
  if ( MiniportHandle->PcwDatapathEventMask
    || (LOBYTE(PcwDatapathCycleMask) = 0,
        Buffer = 0,
        LOWORD(PcwDatapathEventMask) = 0,
        MiniportHandle->PcwDatapathCycleMask) )
  {
    PcwDatapathCycleMask = MiniportHandle->PcwDatapathCycleMask;
    PcwDatapathEventMask = MiniportHandle->PcwDatapathEventMask;
    Buffer = MiniportHandle->Reserved4.Buffer;
    if ( !Buffer )
      Buffer = MiniportHandle->Reserved4.Buffer;
  }
  SourceHandle = (struct _NDIS_OPEN_BLOCK *)a2->SourceHandle;
  Flags = (_NET_BUFFER_LIST **)a2->Flags;
  v11 = SourceHandle == v6;
  if ( (Alignment->NblFlags & 0x8000) != 0 && Alignment->NetBufferListInfo[5] == v6 )
  {
    v11 = 1;
  }
  else if ( SourceHandle != v6 )
  {
    goto LABEL_5;
  }
  if ( ((unsigned __int16)Flags & 0x200) != 0 )
  {
LABEL_5:
    if ( MiniportHandle->CheckPacketFilters && !v6->PacketFilters
      || (v6->PacketFilters & 0x10000) != 0 && !v11 && (char)Flags < 0 )
    {
      goto LABEL_29;
    }
    v12 = a5;
    if ( !ndisNblContextVerifierMode || ndisNblContextVerifierMode == 3 )
    {
LABEL_9:
      v92 = -1;
      v126 = 2;
      if ( (_BYTE)dword_14011CF90 )
      {
        v130 = 1;
        Clock = WmiGetClock(0, 0, Flags);
      }
      else
      {
        Clock = 0;
        v130 = 0;
      }
      v13 = v12 & 1;
      if ( *(_DWORD *)ndisNblTrackerMode )
        ndisNblTrackerTransferOwnershipInternal(
          Alignment,
          (struct NDIS_NBL_TRACKER_HANDLE__ *)0x20,
          v6->NblTracker,
          (enum _NDIS_NBL_TRACKER_OWNERSHIP_EVENT)((v12 & 2 | 0x108) >> 1),
          v12 & 1);
      if ( byte_14011D730 )
      {
        CompContext = v6->PktMonEdge.CompContext;
        if ( CompContext )
        {
          if ( (*((_DWORD *)CompContext + 14) & 1) != 0 )
          {
            v45 = (Alignment->NblFlags & 0x8000) == 0;
            memset(WnodeEventItem, 0, 36);
            if ( v45 )
            {
              PacketType = v6->PktMonEdge.PacketType;
              if ( ExAcquireRundownProtectionCacheAware(RunRefCacheAware) )
              {
                EdgeHandle = v6->PktMonEdge.EdgeHandle;
                strcpy(WnodeEventItem, "(");
                *(_QWORD *)&WnodeEventItem[8] = Alignment;
                *(_DWORD *)&WnodeEventItem[16] = 1;
                *(_DWORD *)&WnodeEventItem[20] = PacketType;
                *(_DWORD *)&WnodeEventItem[24] = 1;
                *(_QWORD *)&WnodeEventItem[32] = 0;
                (*(void (__fastcall **)(_QWORD, void *, _BYTE *, _QWORD))(*((_QWORD *)&xmmword_14011D750 + 1) + 40LL))(
                  xmmword_14011D750,
                  EdgeHandle,
                  WnodeEventItem,
                  0);
                ExReleaseRundownProtectionCacheAware(RunRefCacheAware);
              }
            }
            v13 = v12 & 1;
          }
        }
      }
      v14 = PcwDatapathEventMask;
      if ( (PcwDatapathEventMask & 0x3014) == 0 && (PcwDatapathCycleMask & 8) == 0 )
      {
        v16 = Buffer;
      }
      else
      {
        if ( !v13 )
        {
          v15 = KfRaiseIrql(2u);
          v14 = PcwDatapathEventMask;
          v126 = v15;
        }
        v16 = Buffer;
        if ( (v14 & 4) != 0 )
        {
          Number = KeGetPcr()->Prcb.Number;
          v92 = Number;
          ++*(_QWORD *)((char *)Buffer + ndisPcwPerCpuDataStride * Number + ndisPcwOffsetToPerCpuData + 16);
        }
        else
        {
          Number = -1;
        }
        if ( (v14 & 0x10) != 0 )
        {
          v18 = a4;
          if ( Number == -1 )
          {
            Number = KeGetPcr()->Prcb.Number;
            v92 = Number;
          }
          *(_QWORD *)((char *)Buffer + ndisPcwPerCpuDataStride * Number + ndisPcwOffsetToPerCpuData + 32) += a4;
        }
        else
        {
          v18 = a4;
        }
        if ( (v12 & 2) != 0 )
        {
          if ( (v14 & 0x1000) != 0 )
          {
            if ( Number == -1 )
            {
              Number = KeGetPcr()->Prcb.Number;
              v92 = Number;
            }
            ++*(_QWORD *)((char *)Buffer + ndisPcwPerCpuDataStride * Number + ndisPcwOffsetToPerCpuData + 232);
          }
          if ( (v14 & 0x2000) != 0 )
          {
            if ( Number == -1 )
            {
              Number = KeGetPcr()->Prcb.Number;
              v92 = Number;
            }
            *(_QWORD *)((char *)Buffer + ndisPcwPerCpuDataStride * Number + ndisPcwOffsetToPerCpuData + 240) += v18;
          }
        }
        if ( (PcwDatapathCycleMask & 8) != 0 )
        {
          if ( Number == -1 )
          {
            Number = KeGetPcr()->Prcb.Number;
            v92 = Number;
          }
          *(_QWORD *)((char *)Buffer + ndisPcwPerCpuDataStride * Number + ndisPcwOffsetToPerCpuData + 328) = __rdtsc();
        }
        else if ( v126 != 2 )
        {
          KeLowerIrql(v126);
        }
      }
      LODWORD(Context) = v12;
      v6->ReceiveNetBufferLists(v6->ReceiveNetBufferListsContext, Alignment, a3, a4, (unsigned int)Context);
      if ( (PcwDatapathCycleMask & 8) != 0 )
      {
        v42 = v92;
        if ( v92 == -1 )
          v42 = KeGetPcr()->Prcb.Number;
        v35 = (__int64)v16 + ndisPcwPerCpuDataStride * v42 + ndisPcwOffsetToPerCpuData;
        v43 = __rdtsc();
        *(_QWORD *)(v35 + 128) += (((unsigned __int64)HIDWORD(v43) << 32) | (unsigned int)v43) - *(_QWORD *)(v35 + 328);
        *(_QWORD *)(v35 + 328) = 0;
        if ( v126 != 2 )
          KeLowerIrql(v126);
      }
      if ( (v12 & 2) == 0 )
        goto LABEL_68;
      if ( *(_DWORD *)ndisNblTrackerMode )
        ndisNblTrackerTransferOwnershipInternal(
          Alignment,
          v6->NblTracker,
          (struct NDIS_NBL_TRACKER_HANDLE__ *)0x20,
          NdisNblTrackerEvent_ProtocolReturnedResources,
          v12 & 1);
      if ( !ndisNblContextVerifierMode || ndisNblContextVerifierMode == 3 )
        goto LABEL_68;
      switch ( v6->Header.Type )
      {
        case 5u:
          v37 = LODWORD(v6->MiniportAdapterContext) >> 10;
          break;
        case 0x11u:
          v37 = LODWORD(v6[3].ReceivePacketHandler) >> 12;
          break;
        case 0x12u:
          v37 = v6->OpenFlags >> 31;
LABEL_115:
          if ( (_BYTE)v37 )
            ndisRemoveNblContextTerminator(Alignment, (struct _NDIS_OBJECT_HEADER *)v6);
          goto LABEL_68;
        default:
LABEL_68:
          if ( (_BYTE)dword_14011CF90 )
            WmiGetClock(0, 0, v35);
          if ( v130 )
          {
            v38 = v6->FrameTypeArray[0];
            if ( v38 == 0xDD86 || v38 == 1544 || v38 == 8 )
            {
              v39 = WmiGetClock(0, 0, v35);
              *(_DWORD *)WnodeEventItem = 0;
              v40 = v39 - Clock;
              LODWORD(v39) = (MiniportHandle->NetLuid.Value >> 24) & 0xFFFFFF;
              *(_DWORD *)&WnodeEventItem[5] = 0;
              v113 = v39;
              v114 = a4;
              *(_QWORD *)&WnodeEventItem[13] = 0;
              v117 = 0;
              v115 = v40;
              *(_WORD *)&WnodeEventItem[21] = 0;
              WnodeEventItem[23] = 0;
              v111 = 0;
              v112 = 0x20000;
              *(GUID *)&WnodeEventItem[24] = EtwGuidNdisReceive;
              WnodeEventItem[4] = 16;
              v116 = KeGetPcr()->Prcb.Number;
              strcpy(WnodeEventItem, "H");
              *(_QWORD *)&WnodeEventItem[8] = qword_14011CF88;
              IoWMIWriteEvent(WnodeEventItem);
            }
          }
          return;
      }
      LOBYTE(v37) = v37 & 1;
      goto LABEL_115;
    }
    switch ( v6->Header.Type )
    {
      case 5u:
        v36 = LODWORD(v6->MiniportAdapterContext) >> 10;
        break;
      case 0x11u:
        v36 = LODWORD(v6[3].ReceivePacketHandler) >> 12;
        break;
      case 0x12u:
        v36 = v6->OpenFlags >> 31;
LABEL_92:
        if ( !(_BYTE)v36 )
          goto LABEL_9;
        NetBufferList = 0;
        p_NetBufferList = &NetBufferList;
        memset(&v124[1], 0, 0x178u);
        v124[0] = Alignment;
        v41 = (_SLIST_HEADER *)v124;
        do
        {
          if ( NdisAllocateNetBufferListContext(Alignment, 8u, 0, 0x6376444Eu) )
          {
            TrackNblContextVerifierFailure(Alignment, v6);
            v41->Alignment = Alignment->Link.Alignment;
            Alignment->Link.Alignment = 0;
            *p_NetBufferList = Alignment;
            p_NetBufferList = &Alignment->Next;
            Alignment = (struct _NET_BUFFER_LIST *)v41->Alignment;
          }
          else
          {
            v41 = (_SLIST_HEADER *)Alignment;
            *(_QWORD *)&Alignment->Context->ContextData[Alignment->Context->Offset] = v6;
            Alignment = (struct _NET_BUFFER_LIST *)Alignment->Link.Alignment;
          }
        }
        while ( Alignment );
        Alignment = (struct _NET_BUFFER_LIST *)v124[0];
        v86 = 0;
        a4 = 0;
        v87 = (_QWORD *)v124[0];
        if ( v124[0] )
        {
          do
          {
            v87 = (_QWORD *)*v87;
            ++v86;
          }
          while ( v87 );
          a4 = v86;
        }
        v77 = NetBufferList;
        NetBufferList = 0;
        p_NetBufferList = &NetBufferList;
        if ( !v77 )
          goto LABEL_9;
        if ( byte_14011D730 && (*((_DWORD *)&MiniportHandle->PktMonComp + 14) & 2) != 0 )
        {
          v91 = -536866800;
          v90 = 3;
          v89 = 1;
          PktMonClientNblDrop((_DWORD)MiniportHandle + 5816, (_DWORD)v77, MiniportHandle->PktMonComp.PacketType, v86);
        }
        if ( (a5 & 2) != 0 )
          goto LABEL_199;
        if ( MiniportHandle->PcwDatapathEventMask
          || (v45 = MiniportHandle->PcwDatapathCycleMask == 0, v119 = 0, LOBYTE(v104) = 0, !v45) )
        {
          v104 = MiniportHandle->PcwDatapathCycleMask;
          v119 = MiniportHandle->Reserved4.Buffer;
          if ( !v119 )
            v119 = MiniportHandle->Reserved4.Buffer;
        }
        v72 = v77;
        do
        {
          v72->Flags = v72->Flags & 0xFFFFFFF4 | 8;
          v72 = (PNET_BUFFER_LIST)v72->Link.Alignment;
        }
        while ( v72 );
        if ( Microsoft_Windows_Networking_CorrelationEnabled
          || byte_14011D730 != (_BYTE)Microsoft_Windows_Networking_CorrelationEnabled )
        {
          ndisMarkNetBufferListCorrelationIdsAsUsed(v77);
        }
        if ( MiniportHandle->PeriodicReceiveQueue.NblsAllocated )
        {
          v73 = 0;
          v133 = 0;
          v98 = 0;
          Flags = 0;
          do
          {
            v74 = (struct _NET_BUFFER_LIST *)v77->Link.Alignment;
            v77->Link.Alignment = 0;
            v118 = v74;
            if ( v77->NdisPoolHandle == PoolHandle )
            {
              _InterlockedDecrement(&MiniportHandle->PeriodicReceiveQueue.NblsAllocated);
              v75 = (struct _NPAGED_LOOKASIDE_LIST *)v77->MiniportReserved[1];
              v100 = v75;
              v76 = *(_QWORD *)(v77->Link.Region + 8);
              v96 = v76;
              if ( (*(_BYTE *)(v76 + 10) & 0x20) != 0 )
              {
                MmUnmapLockedPages(*(PVOID *)(v76 + 24), (PMDL)v76);
                v75 = v100;
                v76 = v96;
              }
              if ( v75 )
                ExFreeToNPagedLookasideList(v75, (PVOID)v76);
              else
                ExFreePoolWithTag((PVOID)v76, 0);
              NdisFreeNetBufferList(v77);
              v74 = v118;
              v73 = v98;
              Flags = &v133->Next;
            }
            else
            {
              v133 = v77;
              if ( v73 )
              {
                *Flags = v77;
              }
              else
              {
                v73 = v77;
                v98 = v77;
              }
              Flags = &v77->Next;
            }
            v77 = v74;
          }
          while ( v74 );
          if ( !v73 )
          {
LABEL_199:
            if ( !Alignment )
              return;
            goto LABEL_9;
          }
          v77 = v73;
        }
        v134 = 2;
        v53 = a5 & 1;
        LODWORD(v118) = -1;
        if ( *(_DWORD *)ndisNblTrackerMode )
        {
          ndisNblTrackerTransferOwnershipInternal(
            v77,
            0,
            MiniportHandle->Next.ReturnNetBufferListsTracker,
            NdisNblTrackerEvent_ProtocolReturned,
            v53);
          v53 = a5 & 1;
        }
        v55 = v104 & 0x20;
        v122 = v104 & 0x20;
        if ( (v104 & 0x20) != 0 )
        {
          if ( !v53 )
          {
            v84 = KfRaiseIrql(2u);
            v53 = a5 & 1;
            v134 = v84;
          }
          LODWORD(v118) = KeGetPcr()->Prcb.Number;
          v55 = __rdtsc();
          *(_QWORD *)((char *)v119 + ndisPcwPerCpuDataStride * (unsigned int)v118 + ndisPcwOffsetToPerCpuData + 344) = v55;
        }
        ReturnNetBufferListsObject = MiniportHandle->Next.ReturnNetBufferListsObject;
        ReturnNetBufferListsHandler = MiniportHandle->Next.ReturnNetBufferListsHandler;
        ReturnNetBufferListsContext = MiniportHandle->Next.ReturnNetBufferListsContext;
        v95 = ReturnNetBufferListsObject;
        if ( ReturnNetBufferListsObject->Type == 17 )
          goto LABEL_193;
        if ( !v53 )
        {
          if ( KeGetCurrentIrql() != 2 )
          {
            if ( MiniportHandle->Header.Type == 5 )
            {
              if ( !ndisIsLwfGuaranteedStackSpaceAvailable() )
              {
                *(_QWORD *)WnodeEventItem = v95;
                *(_QWORD *)&WnodeEventItem[8] = ReturnNetBufferListsContext;
                v80 = 24576;
                v112 = 0;
                *(_QWORD *)&WnodeEventItem[16] = ReturnNetBufferListsHandler;
                *(_OWORD *)&WnodeEventItem[24] = (unsigned __int64)v77;
                v111 = a5 & 1;
                if ( (unsigned int)Size > 0x6000 )
                  v80 = Size;
                if ( KeExpandKernelStackAndCalloutEx(
                       ndisDataPathExpandStackCallback<3,void (void *,_NET_BUFFER_LIST *,unsigned long)>,
                       WnodeEventItem,
                       v80,
                       0,
                       0) < 0 )
                {
                  if ( *(_DWORD *)ndisNblTrackerMode )
                    ndisNblTrackerTransferOwnershipInternal(
                      v77,
                      (struct NDIS_NBL_TRACKER_HANDLE__ *)MiniportHandle->Reserved30,
                      (struct NDIS_NBL_TRACKER_HANDLE__ *)0xA0,
                      (enum _NDIS_NBL_TRACKER_OWNERSHIP_EVENT)1,
                      0);
                  v81 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&MiniportHandle->FirstPendingPacket);
                  MiniportHandle->ReturnPacketsQueue = (_NDIS_PACKET *)KeGetCurrentThread();
                  p_TargetInfoAsUlong = &MiniportHandle->WakeUpDpcTimer.Dpc.TargetInfoAsUlong;
                  v83 = *(_QWORD **)&MiniportHandle->WakeUpDpcTimer.Dpc.TargetInfoAsUlong;
                  for ( i = v81; v83; v83 = (_QWORD *)*v83 )
                    p_TargetInfoAsUlong = v83;
                  *p_TargetInfoAsUlong = v77;
                  ndisQueueStackExpansionFallbackWorkItem((struct _NDIS_FILTER_BLOCK *)MiniportHandle);
                  MiniportHandle->ReturnPacketsQueue = 0;
                  KeReleaseSpinLock((PKSPIN_LOCK)&MiniportHandle->FirstPendingPacket, i);
                }
                goto LABEL_194;
              }
              if ( ndisVerifierNdisDispatch && v95->Type == 5 && *(_QWORD *)&v95[194].Type )
              {
                HIDWORD(Context) = HIDWORD(ReturnNetBufferListsHandler);
                (*((void (__fastcall **)(void *, PNET_BUFFER_LIST, _QWORD))ndisVerifierNdisDispatch + 17))(
                  ReturnNetBufferListsContext,
                  v77,
                  a5 & 1);
LABEL_194:
                if ( v122 )
                {
                  v78 = (unsigned int)v118;
                  if ( (_DWORD)v118 == -1 )
                    v78 = KeGetPcr()->Prcb.Number;
                  Flags = (_NET_BUFFER_LIST **)((char *)v119 + ndisPcwPerCpuDataStride * v78 + ndisPcwOffsetToPerCpuData);
                  v79 = __rdtsc();
                  Flags[18] = (_NET_BUFFER_LIST *)((char *)Flags[18]
                                                 + (((unsigned __int64)HIDWORD(v79) << 32) | (unsigned int)v79)
                                                 - (_QWORD)Flags[43]);
                  Flags[43] = 0;
                  if ( v134 != 2 )
                    KeLowerIrql(v134);
                }
                goto LABEL_199;
              }
            }
LABEL_193:
            ReturnNetBufferListsHandler(ReturnNetBufferListsContext, v77, a5 & 1);
            goto LABEL_194;
          }
          v53 = a5 & 1;
          ReturnNetBufferListsObject = v95;
        }
        LODWORD(v55) = KeGetPcr()->Prcb.Number;
        Flags = (_NET_BUFFER_LIST **)WnodeEventItem;
        v56 = ReturnNetBufferListsContext;
        v77->ChildRefCount = v53;
        v57 = ReturnNetBufferListsHandler;
        v103 = v55;
        v93 = (_NET_BUFFER_LIST **)WnodeEventItem;
        *(_QWORD *)&WnodeEventItem[16] = 0;
        *(_QWORD *)WnodeEventItem = v77;
        *(_QWORD *)&WnodeEventItem[8] = v77;
        v77->Scratch = 0;
        while ( ReturnNetBufferListsObject->Type == 5 )
        {
          v58 = *Flags;
          if ( !*Flags )
            break;
          v59 = 96 * v55 + *(_QWORD *)&ReturnNetBufferListsObject[106].Type + 72LL;
          v123 = v59;
          if ( *(_BYTE *)(v59 + 16) )
          {
            *Flags = 0;
            do
            {
              v65 = ndisVerifierNdisDispatch;
              ChildRefCount = (unsigned int)v58->ChildRefCount;
              Scratch = (_NET_BUFFER_LIST *)v58->Scratch;
              v58->ChildRefCount = 0;
              if ( v65
                && ReturnNetBufferListsObject->Type == 5
                && (v85 = *(_QWORD *)&ReturnNetBufferListsObject[194].Type) != 0 )
              {
                (*((void (__fastcall **)(void *, _NET_BUFFER_LIST *, __int64, __int64, void (__fastcall *)(void *, _NET_BUFFER_LIST *, unsigned int), int, int, int))v65
                 + 17))(
                  v56,
                  v58,
                  ChildRefCount,
                  v85,
                  v57,
                  v89,
                  v90,
                  v91);
              }
              else
              {
                v57(v56, v58, ChildRefCount);
              }
              v57 = ReturnNetBufferListsHandler;
              v58 = Scratch;
              v56 = ReturnNetBufferListsContext;
              ReturnNetBufferListsObject = v95;
            }
            while ( Scratch );
            Flags = v93;
            break;
          }
          *(_BYTE *)(v59 + 16) = 1;
          v60 = ReturnNetBufferListsObject;
          v61 = *Flags;
          v94 = ReturnNetBufferListsObject;
          *Flags = 0;
          if ( v61 )
          {
            do
            {
              v62 = ndisVerifierNdisDispatch;
              v63 = (unsigned int)v61->ChildRefCount;
              v64 = (_NET_BUFFER_LIST *)v61->Scratch;
              v61->ChildRefCount = 0;
              if ( v62
                && v95->Type == 5
                && (v57 = *(void (__fastcall **)(void *, _NET_BUFFER_LIST *, unsigned int))&v95[194].Type) != 0 )
              {
                HIDWORD(Context) = HIDWORD(ReturnNetBufferListsHandler);
                (*((void (__fastcall **)(void *, _NET_BUFFER_LIST *, __int64))v62 + 17))(
                  ReturnNetBufferListsContext,
                  v61,
                  v63);
              }
              else
              {
                ((void (__fastcall *)(void *, _NET_BUFFER_LIST *, __int64, void (__fastcall *)(void *, _NET_BUFFER_LIST *, unsigned int)))ReturnNetBufferListsHandler)(
                  ReturnNetBufferListsContext,
                  v61,
                  v63,
                  v57);
              }
              v61 = v64;
            }
            while ( v64 );
            v6 = a1;
            MiniportHandle = v105;
            v12 = a5;
            v59 = v123;
            v60 = v94;
            ReturnNetBufferListsObject = v95;
          }
          *(_BYTE *)(v59 + 16) = 0;
          Flags = (_NET_BUFFER_LIST **)v59;
          ReturnNetBufferListsObject = *(_NDIS_OBJECT_HEADER **)&ReturnNetBufferListsObject[138].Type;
          v57 = *(void (__fastcall **)(void *, _NET_BUFFER_LIST *, unsigned int))&v60[132].Type;
          v56 = *(void **)&v60[134].Type;
          v93 = (_NET_BUFFER_LIST **)v59;
          v55 = v103;
          v95 = ReturnNetBufferListsObject;
          ReturnNetBufferListsHandler = v57;
          ReturnNetBufferListsContext = v56;
        }
        v68 = *Flags;
        if ( *Flags )
        {
          *Flags = 0;
          do
          {
            v69 = ndisVerifierNdisDispatch;
            v70 = (unsigned int)v68->ChildRefCount;
            v71 = (_NET_BUFFER_LIST *)v68->Scratch;
            v68->ChildRefCount = 0;
            if ( v69
              && ReturnNetBufferListsObject->Type == 5
              && (v57 = *(void (__fastcall **)(void *, _NET_BUFFER_LIST *, unsigned int))&ReturnNetBufferListsObject[194].Type) != 0 )
            {
              HIDWORD(Context) = HIDWORD(ReturnNetBufferListsHandler);
              (*((void (__fastcall **)(void *, _NET_BUFFER_LIST *, __int64))v69 + 17))(
                ReturnNetBufferListsContext,
                v68,
                v70);
            }
            else
            {
              ((void (__fastcall *)(void *, _NET_BUFFER_LIST *, __int64, void (__fastcall *)(void *, _NET_BUFFER_LIST *, unsigned int)))ReturnNetBufferListsHandler)(
                ReturnNetBufferListsContext,
                v68,
                v70,
                v57);
            }
            ReturnNetBufferListsObject = v95;
            v68 = v71;
          }
          while ( v71 );
          MiniportHandle = v105;
          v12 = a5;
        }
        goto LABEL_194;
      default:
        goto LABEL_9;
    }
    LOBYTE(v36) = v36 & 1;
    goto LABEL_92;
  }
LABEL_29:
  if ( (a5 & 2) == 0 )
  {
    if ( MiniportHandle->PcwDatapathEventMask || (LOBYTE(v19) = 0, v102 = 0, MiniportHandle->PcwDatapathCycleMask) )
    {
      v19 = MiniportHandle->PcwDatapathCycleMask;
      v102 = MiniportHandle->Reserved4.Buffer;
      if ( !v102 )
        v102 = MiniportHandle->Reserved4.Buffer;
    }
    v20 = Alignment;
    do
    {
      v20->Flags = v20->Flags & 0xFFFFFFF4 | 8;
      v20 = (struct _NET_BUFFER_LIST *)v20->Link.Alignment;
    }
    while ( v20 );
    if ( Microsoft_Windows_Networking_CorrelationEnabled
      || byte_14011D730 != (_BYTE)Microsoft_Windows_Networking_CorrelationEnabled )
    {
      ndisMarkNetBufferListCorrelationIdsAsUsed(Alignment);
    }
    if ( MiniportHandle->PeriodicReceiveQueue.NblsAllocated )
    {
      v21 = 0;
      p_Alignment = 0;
      v131 = 0;
      v127 = 0;
      do
      {
        v23 = (struct _NET_BUFFER_LIST *)Alignment->Link.Alignment;
        Alignment->Link.Alignment = 0;
        if ( Alignment->NdisPoolHandle == PoolHandle )
        {
          _InterlockedDecrement(&MiniportHandle->PeriodicReceiveQueue.NblsAllocated);
          FirstNetBuffer = Alignment->FirstNetBuffer;
          v25 = (struct _NPAGED_LOOKASIDE_LIST *)Alignment->MiniportReserved[1];
          v107 = v25;
          CurrentMdl = FirstNetBuffer->CurrentMdl;
          if ( (CurrentMdl->MdlFlags & 0x20) != 0 )
          {
            MmUnmapLockedPages(CurrentMdl->MappedSystemVa, FirstNetBuffer->CurrentMdl);
            v25 = v107;
          }
          if ( v25 )
            ExFreeToNPagedLookasideList(v25, CurrentMdl);
          else
            ExFreePoolWithTag(CurrentMdl, 0);
          NdisFreeNetBufferList(Alignment);
          v21 = v131;
          p_Alignment = &v127->Link.Alignment;
        }
        else
        {
          if ( v21 )
          {
            *p_Alignment = Alignment;
          }
          else
          {
            v21 = Alignment;
            v131 = Alignment;
          }
          p_Alignment = &Alignment->Link.Alignment;
          v127 = Alignment;
        }
        Alignment = v23;
      }
      while ( v23 );
      Alignment = v21;
    }
    if ( Alignment )
    {
      v27 = a5 & 1;
      v28 = -1;
      if ( *(_DWORD *)ndisNblTrackerMode )
        ndisNblTrackerTransferOwnershipInternal(
          Alignment,
          0,
          MiniportHandle->Next.ReturnNetBufferListsTracker,
          NdisNblTrackerEvent_ProtocolReturned,
          v27);
      v108 = v19 & 0x20;
      if ( (v19 & 0x20) != 0 )
      {
        if ( (a5 & 1) != 0 )
          v29 = 2;
        else
          v29 = KfRaiseIrql(2u);
        v28 = KeGetPcr()->Prcb.Number;
        LODWORD(Flags) = ndisPcwOffsetToPerCpuData;
        *(_QWORD *)((char *)v102 + ndisPcwPerCpuDataStride * v28 + ndisPcwOffsetToPerCpuData + 344) = __rdtsc();
      }
      else
      {
        v29 = 2;
      }
      v30 = (struct _NDIS_FILTER_BLOCK *)MiniportHandle->Next.ReturnNetBufferListsObject;
      v31 = (__int64)MiniportHandle->Next.ReturnNetBufferListsHandler;
      v32 = (__int64)MiniportHandle->Next.ReturnNetBufferListsContext;
      v132 = (void (__fastcall *)(__int64, struct _NET_BUFFER_LIST *, _QWORD))v31;
      v128 = v32;
      if ( v30->Header.Type == 17 )
      {
LABEL_57:
        v132(v128, Alignment, a5 & 1);
        goto LABEL_58;
      }
      if ( (a5 & 1) == 0 )
      {
        if ( KeGetCurrentIrql() != 2 )
        {
          if ( MiniportHandle->Header.Type != 5 )
            goto LABEL_57;
          if ( !ndisIsLwfGuaranteedStackSpaceAvailable() )
          {
            *(_QWORD *)&WnodeEventItem[8] = v128;
            v48 = 24576;
            v112 = 0;
            *(_QWORD *)WnodeEventItem = v30;
            *(_QWORD *)&WnodeEventItem[16] = v132;
            *(_OWORD *)&WnodeEventItem[24] = (unsigned __int64)Alignment;
            v111 = 0;
            if ( (unsigned int)Size > 0x6000 )
              v48 = Size;
            if ( KeExpandKernelStackAndCalloutEx(
                   ndisDataPathExpandStackCallback<3,void (void *,_NET_BUFFER_LIST *,unsigned long)>,
                   WnodeEventItem,
                   v48,
                   0,
                   0) < 0 )
            {
              if ( *(_DWORD *)ndisNblTrackerMode )
                ndisNblTrackerTransferOwnershipInternal(
                  Alignment,
                  (struct NDIS_NBL_TRACKER_HANDLE__ *)MiniportHandle->Reserved30,
                  (struct NDIS_NBL_TRACKER_HANDLE__ *)0xA0,
                  (enum _NDIS_NBL_TRACKER_OWNERSHIP_EVENT)1,
                  0);
              v49 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&MiniportHandle->FirstPendingPacket);
              v50 = &MiniportHandle->WakeUpDpcTimer.Dpc.TargetInfoAsUlong;
              MiniportHandle->ReturnPacketsQueue = (_NDIS_PACKET *)KeGetCurrentThread();
              v51 = v49;
              for ( j = *(_QWORD **)&MiniportHandle->WakeUpDpcTimer.Dpc.TargetInfoAsUlong; j; j = (_QWORD *)*j )
                v50 = j;
              *v50 = Alignment;
              ndisQueueStackExpansionFallbackWorkItem((struct _NDIS_FILTER_BLOCK *)MiniportHandle);
              MiniportHandle->ReturnPacketsQueue = 0;
              KeReleaseSpinLock((PKSPIN_LOCK)&MiniportHandle->FirstPendingPacket, v51);
            }
            goto LABEL_58;
          }
          if ( !ndisIsFilterVerified(v30) )
            goto LABEL_57;
          (*((void (__fastcall **)(__int64, struct _NET_BUFFER_LIST *, _QWORD, void *, void (__fastcall *)(__int64, struct _NET_BUFFER_LIST *, _QWORD)))ndisVerifierNdisDispatch
           + 17))(
            v128,
            Alignment,
            0,
            v30->VerifierContext,
            v132);
LABEL_58:
          if ( v108 )
          {
            if ( v28 == -1 )
              v28 = KeGetPcr()->Prcb.Number;
            v33 = (char *)v102 + ndisPcwPerCpuDataStride * v28 + ndisPcwOffsetToPerCpuData;
            v34 = __rdtsc();
            *((_QWORD *)v33 + 18) += (((unsigned __int64)HIDWORD(v34) << 32) | (unsigned int)v34)
                                   - *((_QWORD *)v33 + 43);
            *((_QWORD *)v33 + 43) = 0;
            if ( v29 != 2 )
              KeLowerIrql(v29);
          }
          return;
        }
        v32 = v128;
        v31 = (__int64)v132;
      }
      ndisInvokeIterativeDatapath<3,void (void *,_NET_BUFFER_LIST *,unsigned long)>(
        (_DWORD)Alignment,
        v32,
        (_DWORD)Flags,
        v27,
        (__int64)v30,
        v32,
        v31);
      goto LABEL_58;
    }
  }
}

```

## disassembly

```asm
0x14000b750  mov     [rsp-8+arg_18], r9d
0x14000b755  mov     [rsp-8+arg_10], r8d
0x14000b75a  mov     [rsp-8+arg_0], rcx
0x14000b75f  push    rbp
0x14000b760  push    rbx
0x14000b761  push    rsi
0x14000b762  push    rdi
0x14000b763  push    r12
0x14000b765  push    r14
0x14000b767  lea     rbp, [rsp-198h]
0x14000b76f  sub     rsp, 298h
0x14000b776  mov     r14, [rcx+10h]
0x14000b77a  mov     rbx, rcx
0x14000b77d  xor     edi, edi
0x14000b77f  mov     [rsp+2C0h+var_250], r14
0x14000b784  mov     rsi, rdx
0x14000b787  mov     ecx, [r14+30h]
0x14000b78b  test    ecx, ecx
0x14000b78d  jnz     loc_14000BC6B
0x14000b793  mov     r12d, edi
0x14000b796  mov     [rsp+2C0h+var_260], rdi
0x14000b79b  mov     [rsp+2C0h+var_248], edi
0x14000b79f  cmp     [r14+50h], edi
0x14000b7a3  jnz     loc_14000BC6B
0x14000b7a9  mov     rcx, [rdx+78h]
0x14000b7ad  mov     r8d, [rsi+88h]
0x14000b7b4  cmp     rcx, rbx
0x14000b7b7  mov     [rsp+2C0h+var_30], r13
0x14000b7bf  setz    dl
0x14000b7c2  mov     [rsp+2C0h+var_38], r15
0x14000b7ca  test    dword ptr [rsi+80h], 8000h
0x14000b7d4  jnz     loc_14000BF47
0x14000b7da  cmp     rcx, rbx
0x14000b7dd  jz      loc_14000BF56
0x14000b7e3  cmp     byte ptr [r14+7CEh], 0
0x14000b7eb  jz      short loc_14000B7FA
0x14000b7ed  cmp     dword ptr [rbx+1B0h], 0
0x14000b7f4  jz      loc_14000B984
0x14000b7fa  test    dword ptr [rbx+1B0h], 10000h
0x14000b804  jnz     loc_14000B973
0x14000b80a  mov     eax, cs:?ndisNblContextVerifierMode@@3W4NDIS_NBL_CONTEXT_VERIFIER_MODE@@A; NDIS_NBL_CONTEXT_VERIFIER_MODE ndisNblContextVerifierMode
0x14000b810  mov     r13d, [rbp+1C0h+arg_20]
0x14000b817  test    eax, eax
0x14000b819  jnz     loc_14000BC93
0x14000b81f  cmp     byte ptr cs:dword_14011CF90, 0
0x14000b826  mov     dword ptr [rsp+2C0h+var_280], 0FFFFFFFFh
0x14000b82e  mov     byte ptr [rbp+1C0h+arg_0], 2
0x14000b835  jnz     loc_14000C050
0x14000b83b  mov     [rsp+2C0h+var_250], rdi
0x14000b840  mov     byte ptr [rbp+1C0h+arg_8], 0
0x14000b847  mov     r15d, r13d
0x14000b84a  and     r15d, 1
0x14000b84e  cmp     cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A, 0; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x14000b855  jz      short loc_14000B881
0x14000b857  mov     r8, [rbx+248h]; struct NDIS_NBL_TRACKER_HANDLE__ *
0x14000b85e  mov     r9d, r13d
0x14000b861  and     r9d, 2
0x14000b865  mov     dword ptr [rsp+2C0h+Context], r15d; unsigned int
0x14000b86a  or      r9d, 108h
0x14000b871  mov     edx, 20h ; ' '; struct NDIS_NBL_TRACKER_HANDLE__ *
0x14000b876  shr     r9d, 1; enum _NDIS_NBL_TRACKER_OWNERSHIP_EVENT
0x14000b879  mov     rcx, rsi; struct _NET_BUFFER_LIST *
0x14000b87c  call    ?ndisNblTrackerTransferOwnershipInternal@@YAXPEAU_NET_BUFFER_LIST@@PEAUNDIS_NBL_TRACKER_HANDLE__@@1W4_NDIS_NBL_TRACKER_OWNERSHIP_EVENT@@K@Z; ndisNblTrackerTransferOwnershipInternal(_NET_BUFFER_LIST *,NDIS_NBL_TRACKER_HANDLE__ *,NDIS_NBL_TRACKER_HANDLE__ *,_NDIS_NBL_TRACKER_OWNERSHIP_EVENT,ulong)
0x14000b881  cmp     cs:byte_14011D730, 0
0x14000b888  jnz     loc_14000BF89
0x14000b88e  mov     r9d, [rsp+2C0h+var_248]
0x14000b893  test    r9d, 3014h
0x14000b89a  setz    cl
0x14000b89d  test    r12b, 8
0x14000b8a1  setz    al
0x14000b8a4  test    al, cl
0x14000b8a6  jnz     loc_14000BDE9
0x14000b8ac  test    r15d, r15d
0x14000b8af  jnz     short loc_14000B8CA
0x14000b8b1  mov     cl, 2; NewIrql
0x14000b8b3  call    cs:__imp_KfRaiseIrql
0x14000b8ba  nop     dword ptr [rax+rax+00h]
0x14000b8bf  mov     r9d, [rsp+2C0h+var_248]
0x14000b8c4  mov     byte ptr [rbp+1C0h+arg_0], al
0x14000b8ca  mov     r15, [rsp+2C0h+var_260]
0x14000b8cf  test    r9b, 4
0x14000b8d3  jz      loc_14000C0AA
0x14000b8d9  mov     r10d, gs:1A4h
0x14000b8e2  mov     ecx, r10d
0x14000b8e5  imul    ecx, cs:?ndisPcwPerCpuDataStride@@3KA; ulong ndisPcwPerCpuDataStride
0x14000b8ec  mov     r8d, cs:?ndisPcwOffsetToPerCpuData@@3KA; ulong ndisPcwOffsetToPerCpuData
0x14000b8f3  mov     dword ptr [rsp+2C0h+var_280], r10d
0x14000b8f8  add     rcx, r15
0x14000b8fb  inc     qword ptr [r8+rcx+10h]
0x14000b900  test    r9b, 10h
0x14000b904  jz      loc_14000C09E
0x14000b90a  mov     r8d, [rbp+1C0h+arg_18]
0x14000b911  cmp     r10d, 0FFFFFFFFh
0x14000b915  jnz     short loc_14000B925
0x14000b917  mov     r10d, gs:1A4h
0x14000b920  mov     dword ptr [rsp+2C0h+var_280], r10d
0x14000b925  mov     edx, cs:?ndisPcwOffsetToPerCpuData@@3KA; ulong ndisPcwOffsetToPerCpuData
0x14000b92b  mov     eax, r10d
0x14000b92e  imul    eax, cs:?ndisPcwPerCpuDataStride@@3KA; ulong ndisPcwPerCpuDataStride
0x14000b935  add     rax, r15
0x14000b938  add     [rdx+rax+20h], r8
0x14000b93d  test    r13b, 2
0x14000b941  jnz     loc_14000BECF
0x14000b947  bt      r12d, 3
0x14000b94c  jb      loc_14000BBB9
0x14000b952  movzx   ecx, byte ptr [rbp+1C0h+arg_0]; NewIrql
0x14000b959  cmp     cl, 2
0x14000b95c  jz      loc_14000BBF2
0x14000b962  call    cs:__imp_KeLowerIrql
0x14000b969  nop     dword ptr [rax+rax+00h]
0x14000b96e  jmp     loc_14000BBF2
0x14000b973  test    dl, dl
0x14000b975  jnz     loc_14000B80A
0x14000b97b  test    r8b, r8b
0x14000b97e  jns     loc_14000B80A
0x14000b984  mov     ebx, [rbp+1C0h+arg_20]
0x14000b98a  test    bl, 2
0x14000b98d  jnz     loc_14000BC4A
0x14000b993  cmp     dword ptr [r14+30h], 0
0x14000b998  jnz     loc_14000C0B4
0x14000b99e  cmp     dword ptr [r14+50h], 0
0x14000b9a3  mov     r12d, edi
0x14000b9a6  mov     [rsp+2C0h+var_260], rdi
0x14000b9ab  jnz     loc_14000C0B4
0x14000b9b1  mov     rcx, rsi
0x14000b9b4  mov     eax, [rcx+88h]
0x14000b9ba  and     eax, 0FFFFFFFCh
0x14000b9bd  or      eax, 8
0x14000b9c0  mov     [rcx+88h], eax
0x14000b9c6  mov     rcx, [rcx]
0x14000b9c9  test    rcx, rcx
0x14000b9cc  jnz     short loc_14000B9B4
0x14000b9ce  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14000b9d4  test    eax, eax
0x14000b9d6  jnz     loc_14000C204
0x14000b9dc  cmp     cs:byte_14011D730, al
0x14000b9e2  jnz     loc_14000C204
0x14000b9e8  cmp     dword ptr [r14+0C98h], 0
0x14000b9f0  jz      loc_14000BA7E
0x14000b9f6  mov     rcx, rdi
0x14000b9f9  mov     rdx, rdi
0x14000b9fc  mov     [rbp+1C0h+arg_8], rcx
0x14000ba03  mov     [rbp+1C0h+arg_0], rdx
0x14000ba0a  mov     r15, [rsi]
0x14000ba0d  mov     [rsi], rdi
0x14000ba10  mov     rax, cs:PoolHandle
0x14000ba17  cmp     [rsi+20h], rax
0x14000ba1b  jnz     loc_14000C9AA
0x14000ba21  lock dec dword ptr [r14+0C98h]
0x14000ba29  mov     rax, [rsi+8]
0x14000ba2d  mov     rcx, [rsi+68h]; Lookaside
0x14000ba31  mov     [rsp+2C0h+var_250], rcx
0x14000ba36  mov     r13, [rax+8]
0x14000ba3a  test    byte ptr [r13+0Ah], 20h
0x14000ba3f  jnz     loc_14000C98D
0x14000ba45  test    rcx, rcx
0x14000ba48  jz      loc_14000C211
0x14000ba4e  mov     rdx, r13; Entry
0x14000ba51  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000ba58  nop     dword ptr [rax+rax+00h]
0x14000ba5d  mov     rcx, rsi; NetBufferList
0x14000ba60  call    NdisFreeNetBufferList
0x14000ba65  mov     rcx, [rbp+1C0h+arg_8]
0x14000ba6c  mov     rdx, [rbp+1C0h+arg_0]
0x14000ba73  mov     rsi, r15
0x14000ba76  test    r15, r15
0x14000ba79  jnz     short loc_14000BA0A
0x14000ba7b  mov     rsi, rcx
0x14000ba7e  test    rsi, rsi
0x14000ba81  jz      loc_14000BC4A
0x14000ba87  and     ebx, 1
0x14000ba8a  mov     r15d, 0FFFFFFFFh
0x14000ba90  cmp     cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A, 0; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x14000ba97  jz      short loc_14000BAB4
0x14000ba99  mov     r8, [r14+9E8h]; struct NDIS_NBL_TRACKER_HANDLE__ *
0x14000baa0  mov     r9d, 87h; enum _NDIS_NBL_TRACKER_OWNERSHIP_EVENT
0x14000baa6  xor     edx, edx; struct NDIS_NBL_TRACKER_HANDLE__ *
0x14000baa8  mov     dword ptr [rsp+2C0h+Context], ebx; unsigned int
0x14000baac  mov     rcx, rsi; struct _NET_BUFFER_LIST *
0x14000baaf  call    ?ndisNblTrackerTransferOwnershipInternal@@YAXPEAU_NET_BUFFER_LIST@@PEAUNDIS_NBL_TRACKER_HANDLE__@@1W4_NDIS_NBL_TRACKER_OWNERSHIP_EVENT@@K@Z; ndisNblTrackerTransferOwnershipInternal(_NET_BUFFER_LIST *,NDIS_NBL_TRACKER_HANDLE__ *,NDIS_NBL_TRACKER_HANDLE__ *,_NDIS_NBL_TRACKER_OWNERSHIP_EVENT,ulong)
0x14000bab4  and     r12d, 20h
0x14000bab8  mov     dword ptr [rsp+2C0h+var_250], r12d
0x14000babd  jnz     loc_14000C1B6
0x14000bac3  mov     r12b, 2
0x14000bac6  mov     r13, [r14+9F0h]
0x14000bacd  mov     rcx, [r14+0A50h]
0x14000bad4  mov     rdx, [r14+9E0h]
0x14000badb  mov     [rbp+1C0h+arg_8], rcx
0x14000bae2  cmp     byte ptr [r13+0], 11h
0x14000bae7  mov     [rbp+1C0h+arg_0], rdx
0x14000baee  jz      short loc_14000BB2F
0x14000baf0  test    ebx, ebx
0x14000baf2  jnz     loc_14000C07F
0x14000baf8  call    cs:__imp_KeGetCurrentIrql
0x14000baff  nop     dword ptr [rax+rax+00h]
0x14000bb04  cmp     al, 2
0x14000bb06  jz      loc_14000C071
0x14000bb0c  cmp     byte ptr [r14], 5
0x14000bb10  jnz     short loc_14000BB2F
0x14000bb12  call    ?ndisIsLwfGuaranteedStackSpaceAvailable@@YA_NXZ; ndisIsLwfGuaranteedStackSpaceAvailable(void)
0x14000bb17  test    al, al
0x14000bb19  jz      loc_14000C0D8
0x14000bb1f  mov     rcx, r13; struct _NDIS_FILTER_BLOCK *
0x14000bb22  call    ?ndisIsFilterVerified@@YA_NPEAU_NDIS_FILTER_BLOCK@@@Z; ndisIsFilterVerified(_NDIS_FILTER_BLOCK *)
0x14000bb27  test    al, al
0x14000bb29  jnz     loc_14000C22C
0x14000bb2f  mov     rcx, [rbp+1C0h+arg_0]
0x14000bb36  mov     r8d, ebx
0x14000bb39  mov     rax, [rbp+1C0h+arg_8]
0x14000bb40  mov     rdx, rsi
0x14000bb43  call    _guard_dispatch_icall
0x14000bb48  cmp     dword ptr [rsp+2C0h+var_250], 0
0x14000bb4d  jz      loc_14000BC4A
0x14000bb53  cmp     r15d, 0FFFFFFFFh
0x14000bb57  jnz     short loc_14000BB62
0x14000bb59  mov     r15d, gs:1A4h
0x14000bb62  imul    r15d, cs:?ndisPcwPerCpuDataStride@@3KA; ulong ndisPcwPerCpuDataStride
0x14000bb6a  mov     r8d, cs:?ndisPcwOffsetToPerCpuData@@3KA; ulong ndisPcwOffsetToPerCpuData
0x14000bb71  mov     eax, r15d
0x14000bb74  add     rax, [rsp+2C0h+var_260]
0x14000bb79  add     r8, rax
0x14000bb7c  rdtsc
0x14000bb7e  shl     rdx, 20h
0x14000bb82  or      rax, rdx
0x14000bb85  sub     rax, [r8+158h]
0x14000bb8c  add     [r8+90h], rax
0x14000bb93  mov     [r8+158h], rdi
0x14000bb9a  cmp     r12b, 2
0x14000bb9e  jz      loc_14000BC4A
0x14000bba4  movzx   ecx, r12b; NewIrql
0x14000bba8  call    cs:__imp_KeLowerIrql
0x14000bbaf  nop     dword ptr [rax+rax+00h]
0x14000bbb4  jmp     loc_14000BC4A
0x14000bbb9  cmp     r10d, 0FFFFFFFFh
0x14000bbbd  jnz     short loc_14000BBCD
0x14000bbbf  mov     r10d, gs:1A4h
0x14000bbc8  mov     dword ptr [rsp+2C0h+var_280], r10d
0x14000bbcd  rdtsc
0x14000bbcf  mov     r8d, cs:?ndisPcwOffsetToPerCpuData@@3KA; ulong ndisPcwOffsetToPerCpuData
0x14000bbd6  mov     ecx, r10d
0x14000bbd9  imul    ecx, cs:?ndisPcwPerCpuDataStride@@3KA; ulong ndisPcwPerCpuDataStride
0x14000bbe0  shl     rdx, 20h
0x14000bbe4  or      rax, rdx
0x14000bbe7  add     rcx, r15
0x14000bbea  mov     [r8+rcx+148h], rax
0x14000bbf2  mov     rax, [rbx+220h]
0x14000bbf9  mov     rdx, rsi
0x14000bbfc  mov     r9d, [rbp+1C0h+arg_18]
0x14000bc03  mov     r8d, [rbp+1C0h+arg_10]
0x14000bc0a  mov     rcx, [rbx+228h]
0x14000bc11  mov     dword ptr [rsp+2C0h+Context], r13d
0x14000bc16  call    _guard_dispatch_icall
0x14000bc1b  bt      r12d, 3
0x14000bc20  jb      loc_14000BE69
0x14000bc26  test    r13b, 2
0x14000bc2a  jnz     loc_14000BCC8
0x14000bc30  cmp     byte ptr cs:dword_14011CF90, 0
0x14000bc37  jnz     loc_14000CA85
0x14000bc3d  cmp     byte ptr [rbp+1C0h+arg_8], 0
0x14000bc44  jnz     loc_14000BD38
0x14000bc4a  mov     r15, [rsp+2C0h+var_38]
0x14000bc52  mov     r13, [rsp+2C0h+var_30]
0x14000bc5a  add     rsp, 298h
0x14000bc61  pop     r14
0x14000bc63  pop     r12
0x14000bc65  pop     rdi
0x14000bc66  pop     rsi
0x14000bc67  pop     rbx
0x14000bc68  pop     rbp
0x14000bc69  retn
0x14000bc6b  mov     rax, [r14+28h]
0x14000bc6f  mov     r12d, [r14+50h]
0x14000bc73  mov     [rsp+2C0h+var_248], ecx
0x14000bc77  mov     [rsp+2C0h+var_260], rax
0x14000bc7c  test    rax, rax
0x14000bc7f  jnz     loc_14000B7A9
0x14000bc85  mov     rax, [r14+28h]
0x14000bc89  mov     [rsp+2C0h+var_260], rax
0x14000bc8e  jmp     loc_14000B7A9
0x14000bc93  cmp     eax, 3
0x14000bc96  jz      loc_14000B81F
0x14000bc9c  movzx   ecx, byte ptr [rbx]
0x14000bc9f  sub     ecx, 5
0x14000bca2  jz      loc_14000BE61
0x14000bca8  sub     ecx, 0Ch
0x14000bcab  jz      loc_14000BDF3
0x14000bcb1  cmp     ecx, 1
0x14000bcb4  jnz     loc_14000B81F
0x14000bcba  mov     eax, [rbx+0E0h]
0x14000bcc0  shr     eax, 1Fh
0x14000bcc3  jmp     loc_14000BDFE
0x14000bcc8  cmp     cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A, 0; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x14000bccf  jz      short loc_14000BCF5
0x14000bcd1  mov     rdx, [rbx+248h]; struct NDIS_NBL_TRACKER_HANDLE__ *
0x14000bcd8  and     r13d, 1
0x14000bcdc  mov     r9d, 88h; enum _NDIS_NBL_TRACKER_OWNERSHIP_EVENT
0x14000bce2  mov     dword ptr [rsp+2C0h+Context], r13d; unsigned int
0x14000bce7  mov     r8d, 20h ; ' '; struct NDIS_NBL_TRACKER_HANDLE__ *
0x14000bced  mov     rcx, rsi; struct _NET_BUFFER_LIST *
0x14000bcf0  call    ?ndisNblTrackerTransferOwnershipInternal@@YAXPEAU_NET_BUFFER_LIST@@PEAUNDIS_NBL_TRACKER_HANDLE__@@1W4_NDIS_NBL_TRACKER_OWNERSHIP_EVENT@@K@Z; ndisNblTrackerTransferOwnershipInternal(_NET_BUFFER_LIST *,NDIS_NBL_TRACKER_HANDLE__ *,NDIS_NBL_TRACKER_HANDLE__ *,_NDIS_NBL_TRACKER_OWNERSHIP_EVENT,ulong)
  ... truncated ...
```
