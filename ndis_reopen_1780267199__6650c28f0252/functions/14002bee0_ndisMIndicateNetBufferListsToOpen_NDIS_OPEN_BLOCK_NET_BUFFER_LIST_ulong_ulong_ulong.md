# ndisMIndicateNetBufferListsToOpen(_NDIS_OPEN_BLOCK *,_NET_BUFFER_LIST *,ulong,ulong,ulong)

- ea: `0x14002bee0`
- end: `0x14002d61a`
- name: `?ndisMIndicateNetBufferListsToOpen@@YAXPEAU_NDIS_OPEN_BLOCK@@PEAU_NET_BUFFER_LIST@@KKK@Z`
- size: `5946`
- prototype: `void __usercall(struct _NDIS_OPEN_BLOCK *@<rcx>, struct _NET_BUFFER_LIST *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int)`
- caller_count: `7`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14002ae20`
- `0x14002af30`
- `0x14002afd0`
- `0x14002e4f0`
- `0x14002e8a0`
- `0x14002f560`
- `0x14002fab0`

## callees

- `0x140010ff0`
- `0x1400110b0`
- `0x140011190`
- `0x140022720`
- `0x1400231d0`
- `0x140023900`
- `0x140025d30`
- `0x1400260b0`
- `0x140029ce0`
- `0x14002a9a0`
- `0x14002aa30`
- `0x14002bee0`
- `0x140037bb0`
- `0x14004ad70`
- `0x140066620`
- `0x1400a4e78`
- `0x1400eb460`
- `0x1400eb7c0`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x14002c301`
- `ntoskrnl!KeLowerIrql` at `0x14002c878`
- `ntoskrnl!KeLowerIrql` at `0x14002ce42`
- `ntoskrnl!KeLowerIrql` at `0x14002c301`
- `ntoskrnl!KeLowerIrql` at `0x14002c878`
- `ntoskrnl!KeLowerIrql` at `0x14002ce42`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002c1b0`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002c31e`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002c743`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002d1c4`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002d26f`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002d36b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002c1b0`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002c31e`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002c743`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002d1c4`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002d26f`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002d36b`
- `ntoskrnl!IoWMIWriteEvent` at `0x14002c70c`
- `ntoskrnl!IoWMIWriteEvent` at `0x14002c70c`
- `ntoskrnl!MmUnmapLockedPages` at `0x14002d502`
- `ntoskrnl!MmUnmapLockedPages` at `0x14002d502`
- `ntoskrnl!KfRaiseIrql` at `0x14002c251`
- `ntoskrnl!KfRaiseIrql` at `0x14002d2f7`
- `ntoskrnl!KfRaiseIrql` at `0x14002c251`
- `ntoskrnl!KfRaiseIrql` at `0x14002d2f7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002cfbe`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002cfbe`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14002cd6c`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14002cd6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d34e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d34e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002cde1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002cde1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002cd90`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002cd90`
- `ntoskrnl!WmiGetClock` at `0x14002c686`
- `ntoskrnl!WmiGetClock` at `0x14002cb05`
- `ntoskrnl!WmiGetClock` at `0x14002d5da`
- `ntoskrnl!WmiGetClock` at `0x14002c686`
- `ntoskrnl!WmiGetClock` at `0x14002cb05`
- `ntoskrnl!WmiGetClock` at `0x14002d5da`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002ca0e`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002ca0e`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002ca70`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002ca70`

## pseudocode

```c
void __fastcall ndisMIndicateNetBufferListsToOpen(
        struct _NDIS_OPEN_BLOCK *a1,
        unsigned __int64 a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5)
{
  _NDIS_MINIPORT_BLOCK *MiniportHandle; // r13
  struct _NDIS_OPEN_BLOCK *v6; // r14
  struct _NET_BUFFER_LIST *Alignment; // r15
  int PcwDatapathCycleMask; // r12d
  struct _NDIS_OPEN_BLOCK *v9; // rcx
  unsigned __int64 v10; // r8
  bool v11; // dl
  char v12; // di
  NDIS_NBL_TRACKER_HANDLE__ *v13; // rsi
  char v14; // r10
  __int64 v15; // rdi
  unsigned int v16; // r10d
  struct _NET_BUFFER_LIST *v17; // r8
  __int64 v18; // r11
  unsigned __int64 v19; // r9
  unsigned __int64 v20; // rdi
  _SLIST_HEADER *v21; // r12
  char v22; // r13
  unsigned __int64 v23; // rsi
  char *v24; // rcx
  __int64 v25; // rax
  unsigned __int64 v26; // r11
  __int64 v27; // rcx
  unsigned __int64 v28; // r8
  KIRQL v29; // al
  unsigned __int64 v30; // rdx
  __int64 v31; // rcx
  KIRQL v32; // r11
  wchar_t *v33; // rsi
  unsigned int v34; // r10d
  unsigned int v35; // r9d
  KIRQL v36; // al
  unsigned __int64 v37; // rdx
  unsigned __int64 v38; // rsi
  __int64 v39; // rdx
  unsigned __int64 v40; // r8
  volatile unsigned int v41; // eax
  unsigned __int64 NblTracker; // rdx
  __int64 v43; // r12
  _SLIST_HEADER *v44; // rsi
  char v45; // r15
  char v46; // r14
  unsigned __int64 Region; // rdi
  char *v48; // rcx
  __int64 v49; // rax
  __int64 v50; // rcx
  volatile unsigned int v51; // eax
  unsigned __int16 v52; // ax
  __int64 v53; // rax
  __int64 v54; // rcx
  KIRQL v55; // al
  unsigned __int64 v56; // r8
  unsigned __int64 v57; // rdi
  __int64 v58; // r8
  _SLIST_HEADER *v59; // rdi
  unsigned int v60; // eax
  unsigned __int64 v61; // rax
  unsigned __int64 v62; // rax
  _PKTMON_COMPONENT_CONTEXT *CompContext; // rax
  bool v64; // zf
  _PKTMON_PACKET_TYPE PacketType; // edi
  void *EdgeHandle; // rdx
  void *ReturnNetBufferListsContext; // r10
  _NDIS_OBJECT_HEADER *ReturnNetBufferListsObject; // r11
  unsigned int v69; // ecx
  struct _NET_BUFFER_LIST **v70; // rsi
  void (__fastcall *v71)(void *, _NET_BUFFER_LIST *, unsigned int); // r9
  struct _NET_BUFFER_LIST *v72; // rdx
  __int64 v73; // rax
  _NDIS_OBJECT_HEADER *v74; // rcx
  struct _NET_BUFFER_LIST *v75; // rdx
  struct _VF_NDIS_DISPATCH_TABLE *v76; // rax
  __int64 v77; // r8
  struct _NET_BUFFER_LIST *v78; // rdi
  struct _VF_NDIS_DISPATCH_TABLE *v79; // rax
  __int64 ChildRefCount; // r8
  struct _NET_BUFFER_LIST *Scratch; // rdi
  struct _VF_NDIS_DISPATCH_TABLE *v82; // rax
  __int64 v83; // r8
  struct _NET_BUFFER_LIST *v84; // rdi
  int v85; // ecx
  KIRQL v86; // al
  _QWORD *p_TargetInfoAsUlong; // rcx
  _QWORD *v88; // rdx
  unsigned int v89; // eax
  unsigned __int64 v90; // rax
  __int64 v91; // rcx
  PNET_BUFFER_LIST v92; // rcx
  struct _NET_BUFFER_LIST *v93; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v94; // rdi
  struct _NET_BUFFER_LIST *v95; // rcx
  PNET_BUFFER_LIST v96; // rsi
  unsigned int v97; // edi
  NDIS_NBL_TRACKER_HANDLE__ *ReturnNetBufferListsTracker; // rcx
  unsigned int v99; // edx
  unsigned __int64 v100; // rdi
  struct _NET_BUFFER_LIST *v101; // r12
  char v102; // r13
  char v103; // r15
  unsigned __int64 v104; // rsi
  __int64 v105; // rax
  unsigned __int64 v106; // rdx
  __int64 v107; // rcx
  KIRQL v108; // al
  unsigned __int64 v109; // rdx
  __int64 v110; // rcx
  void (__fastcall *ReturnNetBufferListsHandler)(void *, _NET_BUFFER_LIST *, unsigned int); // rsi
  void *v112; // rcx
  KIRQL CurrentIrql; // al
  unsigned __int64 v114; // rdx
  unsigned __int64 v115; // rsi
  __int64 v116; // rdx
  unsigned int v117; // r9d
  _QWORD *v118; // rax
  PVOID Context; // [rsp+20h] [rbp-E0h]
  int v120; // [rsp+28h] [rbp-D8h]
  int v121; // [rsp+30h] [rbp-D0h]
  int v122; // [rsp+38h] [rbp-C8h]
  char v123; // [rsp+40h] [rbp-C0h]
  char v124; // [rsp+40h] [rbp-C0h]
  KIRQL v125; // [rsp+41h] [rbp-BFh]
  KIRQL i; // [rsp+41h] [rbp-BFh]
  char v127; // [rsp+41h] [rbp-BFh]
  char v128; // [rsp+42h] [rbp-BEh]
  KIRQL v129; // [rsp+42h] [rbp-BEh]
  struct _NET_BUFFER_LIST *v130; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v131; // [rsp+48h] [rbp-B8h]
  _NDIS_OBJECT_HEADER *v132; // [rsp+48h] [rbp-B8h]
  struct _NET_BUFFER_LIST *v133; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v134; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v135; // [rsp+48h] [rbp-B8h]
  int v136; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v137; // [rsp+58h] [rbp-A8h]
  void (__fastcall *v138)(void *, _NET_BUFFER_LIST *, unsigned int); // [rsp+58h] [rbp-A8h]
  PNET_BUFFER_LIST v139; // [rsp+58h] [rbp-A8h]
  __int64 v140; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v141; // [rsp+58h] [rbp-A8h]
  char v142; // [rsp+60h] [rbp-A0h]
  void *v143; // [rsp+60h] [rbp-A0h]
  int v144; // [rsp+60h] [rbp-A0h]
  char v145; // [rsp+68h] [rbp-98h]
  __int64 v146; // [rsp+70h] [rbp-90h]
  unsigned int v147; // [rsp+70h] [rbp-90h]
  unsigned int v148; // [rsp+70h] [rbp-90h]
  unsigned __int64 v149; // [rsp+70h] [rbp-90h]
  struct _NET_BUFFER_LIST *v150; // [rsp+78h] [rbp-88h]
  struct _NET_BUFFER_LIST *v151; // [rsp+78h] [rbp-88h]
  struct _NET_BUFFER_LIST *v152; // [rsp+78h] [rbp-88h]
  struct _NET_BUFFER_LIST *v153; // [rsp+78h] [rbp-88h]
  wchar_t *Buffer; // [rsp+80h] [rbp-80h]
  __int64 v155; // [rsp+80h] [rbp-80h]
  unsigned __int64 v156; // [rsp+80h] [rbp-80h]
  __int64 Clock; // [rsp+88h] [rbp-78h]
  _NDIS_OBJECT_HEADER *v158; // [rsp+88h] [rbp-78h]
  struct _NET_BUFFER_LIST *v159; // [rsp+88h] [rbp-78h]
  __int64 v160; // [rsp+88h] [rbp-78h]
  unsigned int Number; // [rsp+90h] [rbp-70h]
  int PcwDatapathEventMask; // [rsp+94h] [rbp-6Ch]
  _NDIS_MINIPORT_BLOCK *v163; // [rsp+98h] [rbp-68h]
  unsigned __int64 v164; // [rsp+A0h] [rbp-60h]
  int v165; // [rsp+A0h] [rbp-60h]
  wchar_t *v166; // [rsp+A8h] [rbp-58h]
  _BYTE WnodeEventItem[40]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v168; // [rsp+D8h] [rbp-28h]
  int v169; // [rsp+DCh] [rbp-24h]
  int v170; // [rsp+E0h] [rbp-20h]
  unsigned int v171; // [rsp+E4h] [rbp-1Ch]
  __int64 v172; // [rsp+E8h] [rbp-18h]
  unsigned int v173; // [rsp+F0h] [rbp-10h]
  int v174; // [rsp+F4h] [rbp-Ch]
  PNET_BUFFER_LIST NetBufferList; // [rsp+100h] [rbp+0h] BYREF
  PNET_BUFFER_LIST *p_NetBufferList; // [rsp+108h] [rbp+8h]
  NDIS_NBL_TRACKER_HANDLE__ *v177; // [rsp+110h] [rbp+10h]
  _QWORD v178[49]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int64 v180; // [rsp+2F8h] [rbp+1F8h]

  v180 = a2;
  MiniportHandle = a1->MiniportHandle;
  v6 = a1;
  v163 = MiniportHandle;
  Alignment = (struct _NET_BUFFER_LIST *)a2;
  if ( MiniportHandle->PcwDatapathEventMask
    || (LOBYTE(PcwDatapathCycleMask) = 0,
        Buffer = 0,
        LOWORD(PcwDatapathEventMask) = 0,
        v145 = 0,
        MiniportHandle->PcwDatapathCycleMask) )
  {
    PcwDatapathCycleMask = MiniportHandle->PcwDatapathCycleMask;
    PcwDatapathEventMask = MiniportHandle->PcwDatapathEventMask;
    v145 = PcwDatapathCycleMask;
    Buffer = MiniportHandle->Reserved4.Buffer;
    if ( !Buffer )
      Buffer = MiniportHandle->Reserved4.Buffer;
  }
  v9 = *(struct _NDIS_OPEN_BLOCK **)(a2 + 120);
  v10 = *(unsigned int *)(a2 + 136);
  v11 = v9 == v6;
  if ( (Alignment->NblFlags & 0x8000) != 0 && Alignment->NetBufferListInfo[5] == v6 )
  {
    v11 = 1;
  }
  else if ( v9 != v6 )
  {
    goto LABEL_5;
  }
  if ( (v10 & 0x200) == 0 )
  {
LABEL_63:
    if ( (a5 & 2) == 0 )
      ndisReturnNetBufferListsInternal((struct _NDIS_FILTER_BLOCK *)MiniportHandle, Alignment, a5 & 1, 0);
    return;
  }
LABEL_5:
  if ( MiniportHandle->CheckPacketFilters && !v6->PacketFilters
    || (v6->PacketFilters & 0x10000) != 0 && !v11 && (v10 & 0x80u) != 0LL )
  {
    goto LABEL_63;
  }
  v12 = a5;
  if ( !ndisNblContextVerifierMode || ndisNblContextVerifierMode == 3 )
    goto LABEL_9;
  switch ( v6->Header.Type )
  {
    case 5u:
      v41 = LODWORD(v6->MiniportAdapterContext) >> 10;
      break;
    case 0x11u:
      v41 = LODWORD(v6[3].ReceivePacketHandler) >> 12;
      break;
    case 0x12u:
      v41 = v6->OpenFlags >> 31;
      goto LABEL_125;
    default:
      goto LABEL_9;
  }
  LOBYTE(v41) = v41 & 1;
LABEL_125:
  if ( !(_BYTE)v41 )
    goto LABEL_9;
  NetBufferList = 0;
  p_NetBufferList = &NetBufferList;
  memset(&v178[1], 0, 0x178u);
  v178[0] = Alignment;
  v59 = (_SLIST_HEADER *)v178;
  do
  {
    if ( NdisAllocateNetBufferListContext(Alignment, 8u, 0, 0x6376444Eu) )
    {
      TrackNblContextVerifierFailure(Alignment, v6);
      v59->Alignment = Alignment->Link.Alignment;
      Alignment->Link.Alignment = 0;
      *p_NetBufferList = Alignment;
      p_NetBufferList = &Alignment->Next;
      Alignment = (struct _NET_BUFFER_LIST *)v59->Alignment;
    }
    else
    {
      v59 = (_SLIST_HEADER *)Alignment;
      *(_QWORD *)&Alignment->Context->ContextData[Alignment->Context->Offset] = v6;
      Alignment = (struct _NET_BUFFER_LIST *)Alignment->Link.Alignment;
    }
  }
  while ( Alignment );
  Alignment = (struct _NET_BUFFER_LIST *)v178[0];
  v117 = 0;
  v180 = v178[0];
  v118 = (_QWORD *)v178[0];
  a4 = 0;
  if ( v178[0] )
  {
    do
    {
      v118 = (_QWORD *)*v118;
      ++v117;
    }
    while ( v118 );
    a4 = v117;
  }
  v96 = NetBufferList;
  v153 = NetBufferList;
  NetBufferList = 0;
  p_NetBufferList = &NetBufferList;
  if ( !v153 )
    goto LABEL_210;
  if ( byte_140123720 && (*((_DWORD *)&MiniportHandle->PktMonComp + 14) & 2) != 0 )
  {
    v122 = -536866800;
    v121 = 3;
    v120 = 1;
    PktMonClientNblDrop((_DWORD)MiniportHandle + 5816, (_DWORD)v96, MiniportHandle->PktMonComp.PacketType, v117);
  }
  if ( (a5 & 2) != 0 )
    goto LABEL_209;
  if ( MiniportHandle->PcwDatapathEventMask || (v166 = 0, LOBYTE(v144) = 0, MiniportHandle->PcwDatapathCycleMask) )
  {
    v144 = MiniportHandle->PcwDatapathCycleMask;
    v166 = MiniportHandle->Reserved4.Buffer;
    if ( !v166 )
      v166 = MiniportHandle->Reserved4.Buffer;
  }
  v92 = v96;
  do
  {
    v92->Flags = v92->Flags & 0xFFFFFFF4 | 8;
    v92 = (PNET_BUFFER_LIST)v92->Link.Alignment;
  }
  while ( v92 );
  if ( Microsoft_Windows_Networking_CorrelationEnabled
    || byte_140123720 != (_BYTE)Microsoft_Windows_Networking_CorrelationEnabled )
  {
    ndisMarkNetBufferListCorrelationIdsAsUsed(v96);
  }
  if ( MiniportHandle->PeriodicReceiveQueue.NblsAllocated )
  {
    a2 = 0;
    v159 = 0;
    v10 = 0;
    v139 = 0;
    do
    {
      v93 = (struct _NET_BUFFER_LIST *)v96->Link.Alignment;
      v96->Link.Alignment = 0;
      v133 = v93;
      if ( v96->NdisPoolHandle == PoolHandle )
      {
        _InterlockedDecrement(&MiniportHandle->PeriodicReceiveQueue.NblsAllocated);
        v94 = (struct _NPAGED_LOOKASIDE_LIST *)v96->MiniportReserved[1];
        v95 = *(struct _NET_BUFFER_LIST **)(v96->Link.Region + 8);
        v152 = v95;
        if ( (*((_BYTE *)&v95->NetBufferListHeader.Link.HeaderX64 + 10) & 0x20) != 0 )
        {
          MmUnmapLockedPages(v95->ParentNetBufferList, (PMDL)v95);
          v95 = v152;
        }
        if ( v94 )
          ExFreeToNPagedLookasideList(v94, v95);
        else
          ExFreePoolWithTag(v95, 0);
        NdisFreeNetBufferList(v96);
        v93 = v133;
        a2 = (unsigned __int64)v159;
        v10 = (unsigned __int64)v139;
      }
      else
      {
        v139 = v96;
        if ( a2 )
        {
          *(_QWORD *)v10 = v96;
        }
        else
        {
          a2 = (unsigned __int64)v96;
          v159 = v96;
        }
        v10 = (unsigned __int64)v96;
      }
      v96 = v93;
    }
    while ( v93 );
    if ( !a2 )
      goto LABEL_209;
    v96 = (PNET_BUFFER_LIST)a2;
    v153 = (struct _NET_BUFFER_LIST *)a2;
  }
  v97 = a5 & 1;
  Number = -1;
  v129 = 2;
  if ( !*(_DWORD *)ndisNblTrackerMode )
    goto LABEL_266;
  ReturnNetBufferListsTracker = MiniportHandle->Next.ReturnNetBufferListsTracker;
  v10 = 0;
  v99 = ndisNblTrackerEpoch;
  v177 = ReturnNetBufferListsTracker;
  v148 = ndisNblTrackerEpoch;
  v134 = 0;
  v140 = 0;
  v160 = 0;
  if ( *(int *)ndisNblTrackerMode >= 3 )
  {
    ndisNblTrackerRecordEventInternal(v96, 0, 0x87u, ReturnNetBufferListsTracker, a5 & 1);
    ReturnNetBufferListsTracker = v177;
    v10 = 0;
    v99 = v148;
  }
  v149 = (unsigned __int64)ReturnNetBufferListsTracker & 0xFFFFFFFFFFFFFFFDuLL;
  if ( ((unsigned __int8)ReturnNetBufferListsTracker & 1) != 0 )
  {
    v100 = (2LL * v99) ^ ((unsigned __int64)ReturnNetBufferListsTracker ^ (2LL * v99)) & 0xFFFFFFFFFFFFFFFDuLL;
    v149 = *(_QWORD *)(((unsigned __int64)ReturnNetBufferListsTracker & 0xFFFFFFFFFFFFFFF8uLL) + 24);
  }
  else
  {
    v100 = (unsigned __int64)ReturnNetBufferListsTracker & 0xFFFFFFFFFFFFFFFDuLL;
  }
  v101 = v96;
  v102 = a5 & 1;
  v103 = 0;
  do
  {
    v104 = (unsigned __int64)v101->NetBufferListInfo[27];
    while ( v101->NetBufferListInfo[27] == (void *)v104 )
    {
      if ( v104 )
      {
        if ( (v104 & 4) != 0 )
          goto LABEL_294;
      }
      else if ( !v101->SourceHandle )
      {
        v101->SourceHandle = (void *)ndisSourceHandleFromOwner(0);
      }
      if ( ndisNblTrackerCanNblBeTracked(v101) )
      {
        if ( v101->SourceHandle != (void *)v149 || v101->ParentNetBufferList )
        {
          v105 = v100;
          v10 = ++v134;
        }
        else
        {
          v105 = 24;
          ++v160;
          v10 = ++v134;
        }
        goto LABEL_250;
      }
LABEL_294:
      v10 = v134;
      v105 = v100 | 4;
LABEL_250:
      v101->NetBufferListInfo[27] = (void *)v105;
      v101 = (struct _NET_BUFFER_LIST *)v101->Link.Alignment;
      if ( !v101 )
        break;
    }
    if ( (v104 & 1) == 0 )
      goto LABEL_256;
    v141 = v140 - v10;
    if ( !v141 )
      goto LABEL_256;
    if ( v102 || v103 )
    {
      v106 = (v104 & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((v104 >> 1) & 1) + 3);
      if ( !v102 )
        goto LABEL_287;
      goto LABEL_255;
    }
    v103 = 1;
    CurrentIrql = KeGetCurrentIrql();
    v10 = v134;
    v114 = v104 >> 1;
    v115 = v104 & 0xFFFFFFFFFFFFFFF8uLL;
    v116 = 16 * ((v114 & 1) + 3);
    if ( CurrentIrql == 2 )
    {
      v102 = 1;
      v106 = v115 + v116;
LABEL_255:
      v107 = KeGetPcr()->Prcb.Number << 12;
      *(_QWORD *)(v107 + *(_QWORD *)v106) += v141;
      goto LABEL_256;
    }
    v102 = 0;
    v106 = v115 + v116;
LABEL_287:
    _InterlockedAdd64((volatile signed __int64 *)(v106 + 8), v141);
LABEL_256:
    v140 = v10;
  }
  while ( v101 );
  v6 = a1;
  LOBYTE(PcwDatapathCycleMask) = v145;
  v127 = v103;
  Alignment = (struct _NET_BUFFER_LIST *)v180;
  v124 = v102;
  MiniportHandle = v163;
  if ( (v100 & 1) != 0 )
  {
    v10 -= v160;
    v135 = v10;
    if ( v10 )
    {
      if ( v124 || v127 )
      {
        v109 = (v100 & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((v100 >> 1) & 1) + 3);
        if ( v124 )
          goto LABEL_264;
LABEL_262:
        _InterlockedAdd64((volatile signed __int64 *)(v109 + 8), v10);
      }
      else
      {
        v108 = KeGetCurrentIrql();
        v10 = v135;
        v109 = (v100 & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((v100 >> 1) & 1) + 3);
        if ( v108 != 2 )
          goto LABEL_262;
LABEL_264:
        v110 = KeGetPcr()->Prcb.Number << 12;
        *(_QWORD *)(v110 + *(_QWORD *)v109) += v10;
      }
    }
  }
  v97 = a5 & 1;
LABEL_266:
  v165 = v144 & 0x20;
  if ( (v144 & 0x20) != 0 )
  {
    if ( !v97 )
      v129 = KfRaiseIrql(2u);
    Number = KeGetPcr()->Prcb.Number;
    v10 = ndisPcwOffsetToPerCpuData;
    *(_QWORD *)((char *)v166 + ndisPcwPerCpuDataStride * Number + ndisPcwOffsetToPerCpuData + 344) = __rdtsc();
  }
  ReturnNetBufferListsObject = MiniportHandle->Next.ReturnNetBufferListsObject;
  ReturnNetBufferListsHandler = MiniportHandle->Next.ReturnNetBufferListsHandler;
  ReturnNetBufferListsContext = MiniportHandle->Next.ReturnNetBufferListsContext;
  v138 = ReturnNetBufferListsHandler;
  v143 = ReturnNetBufferListsContext;
  v132 = ReturnNetBufferListsObject;
  if ( ReturnNetBufferListsObject->Type == 17 )
  {
LABEL_276:
    v112 = ReturnNetBufferListsContext;
    goto LABEL_274;
  }
  if ( v97 )
  {
LABEL_177:
    v69 = KeGetPcr()->Prcb.Number;
    v70 = (struct _NET_BUFFER_LIST **)WnodeEventItem;
    v71 = v138;
    v147 = v69;
    v153->Scratch = 0;
    v153->ChildRefCount = a5 & 1;
    *(_QWORD *)&WnodeEventItem[16] = 0;
    *(_QWORD *)WnodeEventItem = v153;
    *(_QWORD *)&WnodeEventItem[8] = v153;
    while ( ReturnNetBufferListsObject->Type == 5 )
    {
      v72 = *v70;
      if ( !*v70 )
        break;
      v73 = 96LL * v69 + *(_QWORD *)&ReturnNetBufferListsObject[106].Type + 72LL;
      v177 = (NDIS_NBL_TRACKER_HANDLE__ *)v73;
      if ( *(_BYTE *)(v73 + 16) )
      {
        *v70 = 0;
        do
        {
          v79 = ndisVerifierNdisDispatch;
          ChildRefCount = (unsigned int)v72->ChildRefCount;
          Scratch = (struct _NET_BUFFER_LIST *)v72->Scratch;
          v72->ChildRefCount = 0;
          if ( v79
            && ReturnNetBufferListsObject->Type == 5
            && (v91 = *(_QWORD *)&ReturnNetBufferListsObject[194].Type) != 0 )
          {
            (*((void (__fastcall **)(void *, struct _NET_BUFFER_LIST *, __int64, __int64, void (__fastcall *)(void *, _NET_BUFFER_LIST *, unsigned int), int, int, int))v79
             + 17))(
              ReturnNetBufferListsContext,
              v72,
              ChildRefCount,
              v91,
              v71,
              v120,
              v121,
              v122);
          }
          else
          {
            v71(ReturnNetBufferListsContext, v72, ChildRefCount);
          }
          v71 = v138;
          v72 = Scratch;
          ReturnNetBufferListsContext = v143;
          ReturnNetBufferListsObject = v132;
        }
        while ( Scratch );
        break;
      }
      *(_BYTE *)(v73 + 16) = 1;
      v74 = ReturnNetBufferListsObject;
      v75 = *v70;
      v158 = ReturnNetBufferListsObject;
      *v70 = 0;
      if ( v75 )
      {
        do
        {
          v76 = ndisVerifierNdisDispatch;
          v77 = (unsigned int)v75->ChildRefCount;
          v78 = (struct _NET_BUFFER_LIST *)v75->Scratch;
          v75->ChildRefCount = 0;
          if ( v76
            && v132->Type == 5
            && (v71 = *(void (__fastcall **)(void *, _NET_BUFFER_LIST *, unsigned int))&v132[194].Type) != 0 )
          {
            HIDWORD(Context) = HIDWORD(v138);
            (*((void (__fastcall **)(void *, struct _NET_BUFFER_LIST *, __int64))v76 + 17))(v143, v75, v77);
          }
          else
          {
            ((void (__fastcall *)(void *, struct _NET_BUFFER_LIST *, __int64, void (__fastcall *)(void *, _NET_BUFFER_LIST *, unsigned int)))v138)(
              v143,
              v75,
              v77,
              v71);
          }
          v75 = v78;
        }
        while ( v78 );
        v6 = a1;
        MiniportHandle = v163;
        LOBYTE(PcwDatapathCycleMask) = v145;
        v73 = (__int64)v177;
        ReturnNetBufferListsObject = v132;
        v74 = v158;
      }
      *(_BYTE *)(v73 + 16) = 0;
      v70 = (struct _NET_BUFFER_LIST **)v73;
      v71 = *(void (__fastcall **)(void *, _NET_BUFFER_LIST *, unsigned int))&v74[132].Type;
      ReturnNetBufferListsContext = *(void **)&v74[134].Type;
      ReturnNetBufferListsObject = *(_NDIS_OBJECT_HEADER **)&ReturnNetBufferListsObject[138].Type;
      v69 = v147;
      v132 = ReturnNetBufferListsObject;
      v138 = v71;
      v143 = ReturnNetBufferListsContext;
    }
    a2 = (unsigned __int64)*v70;
    if ( *v70 )
    {
      *v70 = 0;
      do
      {
        v82 = ndisVerifierNdisDispatch;
        v83 = *(unsigned int *)(a2 + 132);
        v84 = *(struct _NET_BUFFER_LIST **)(a2 + 112);
        *(_DWORD *)(a2 + 132) = 0;
        if ( v82
          && ReturnNetBufferListsObject->Type == 5
          && (v71 = *(void (__fastcall **)(void *, _NET_BUFFER_LIST *, unsigned int))&ReturnNetBufferListsObject[194].Type) != 0 )
        {
          HIDWORD(Context) = HIDWORD(v138);
          (*((void (__fastcall **)(void *, unsigned __int64, __int64))v82 + 17))(v143, a2, v83);
        }
        else
        {
          ((void (__fastcall *)(void *, unsigned __int64, __int64, void (__fastcall *)(void *, _NET_BUFFER_LIST *, unsigned int)))v138)(
            v143,
            a2,
            v83,
            v71);
        }
        ReturnNetBufferListsObject = v132;
        a2 = (unsigned __int64)v84;
      }
      while ( v84 );
      MiniportHandle = v163;
    }
    goto LABEL_204;
  }
  if ( KeGetCurrentIrql() == 2 )
  {
    ReturnNetBufferListsContext = v143;
    ReturnNetBufferListsObject = v132;
    goto LABEL_177;
  }
  if ( MiniportHandle->Header.Type != 5 )
  {
    ReturnNetBufferListsContext = v143;
    goto LABEL_276;
  }
  if ( ndisIsLwfGuaranteedStackSpaceAvailable() )
  {
    if ( ndisVerifierNdisDispatch && v132->Type == 5 && *(_QWORD *)&v132[194].Type )
    {
      HIDWORD(Context) = HIDWORD(ReturnNetBufferListsHandler);
      (*((void (__fastcall **)(void *, struct _NET_BUFFER_LIST *, _QWORD))ndisVerifierNdisDispatch + 17))(v143, v153, 0);
      goto LABEL_204;
    }
    v112 = v143;
LABEL_274:
    ReturnNetBufferListsHandler(v112, v153, v97);
  }
  else
  {
    *(_QWORD *)WnodeEventItem = v132;
    *(_QWORD *)&WnodeEventItem[8] = v143;
    v85 = 24576;
    v168 = a5 & 1;
    v169 = 0;
    *(_QWORD *)&WnodeEventItem[16] = ReturnNetBufferListsHandler;
    *(_OWORD *)&WnodeEventItem[24] = (unsigned __int64)v153;
    if ( (unsigned int)Size > 0x6000 )
      v85 = Size;
    if ( KeExpandKernelStackAndCalloutEx(
           ndisDataPathExpandStackCallback<3,void (void *,_NET_BUFFER_LIST *,unsigned long)>,
           WnodeEventItem,
           v85,
           0,
           0) < 0 )
    {
      if ( *(_DWORD *)ndisNblTrackerMode )
        ndisNblTrackerTransferOwnershipInternal(
          v153,
          (struct NDIS_NBL_TRACKER_HANDLE__ *)MiniportHandle->Reserved30,
          (struct NDIS_NBL_TRACKER_HANDLE__ *)0xA0,
          (enum _NDIS_NBL_TRACKER_OWNERSHIP_EVENT)1,
          0);
      v86 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&MiniportHandle->FirstPendingPacket);
      MiniportHandle->ReturnPacketsQueue = (_NDIS_PACKET *)KeGetCurrentThread();
      p_TargetInfoAsUlong = &MiniportHandle->WakeUpDpcTimer.Dpc.TargetInfoAsUlong;
      v88 = *(_QWORD **)&MiniportHandle->WakeUpDpcTimer.Dpc.TargetInfoAsUlong;
      for ( i = v86; v88; v88 = (_QWORD *)*v88 )
        p_TargetInfoAsUlong = v88;
      *p_TargetInfoAsUlong = v153;
      ndisQueueStackExpansionFallbackWorkItem((struct _NDIS_FILTER_BLOCK *)MiniportHandle);
      MiniportHandle->ReturnPacketsQueue = 0;
      KeReleaseSpinLock((PKSPIN_LOCK)&MiniportHandle->FirstPendingPacket, i);
    }
  }
LABEL_204:
  if ( v165 )
  {
    v89 = Number;
    if ( Number == -1 )
      v89 = KeGetPcr()->Prcb.Number;
    v10 = (unsigned __int64)v166 + ndisPcwPerCpuDataStride * v89 + ndisPcwOffsetToPerCpuData;
    v90 = __rdtsc();
    a2 = (unsigned __int64)HIDWORD(v90) << 32;
    *(_QWORD *)(v10 + 144) += (a2 | (unsigned int)v90) - *(_QWORD *)(v10 + 344);
    *(_QWORD *)(v10 + 344) = 0;
    if ( v129 != 2 )
      KeLowerIrql(v129);
  }
LABEL_209:
  if ( Alignment )
  {
LABEL_210:
    v12 = a5;
LABEL_9:
    v136 = -1;
    v125 = 2;
    if ( (_BYTE)dword_140122F90 )
    {
      v123 = 1;
      Clock = WmiGetClock(0, 0, v10);
    }
    else
    {
      Clock = 0;
      v123 = 0;
    }
    if ( !*(_DWORD *)ndisNblTrackerMode )
    {
LABEL_43:
      if ( byte_140123720 )
      {
        CompContext = v6->PktMonEdge.CompContext;
        if ( CompContext )
        {
          if ( (*((_DWORD *)CompContext + 14) & 1) != 0 )
          {
            v64 = (Alignment->NblFlags & 0x8000) == 0;
            memset(WnodeEventItem, 0, 36);
            if ( v64 )
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
                (*(void (__fastcall **)(_QWORD, void *, _BYTE *, _QWORD))(*((_QWORD *)&xmmword_140123740 + 1) + 40LL))(
                  xmmword_140123740,
                  EdgeHandle,
                  WnodeEventItem,
                  0);
                ExReleaseRundownProtectionCacheAware(RunRefCacheAware);
              }
            }
          }
        }
      }
      if ( (PcwDatapathEventMask & 0x3014) == 0 && (PcwDatapathCycleMask & 8) == 0 )
      {
        v33 = Buffer;
      }
      else
      {
        if ( (a5 & 1) != 0 )
        {
          v32 = 2;
        }
        else
        {
          v32 = KfRaiseIrql(2u);
          v125 = v32;
        }
        v33 = Buffer;
        if ( (PcwDatapathEventMask & 4) != 0 )
        {
          v34 = KeGetPcr()->Prcb.Number;
          v136 = v34;
          ++*(_QWORD *)((char *)Buffer + ndisPcwPerCpuDataStride * v34 + ndisPcwOffsetToPerCpuData + 16);
        }
        else
        {
          v34 = -1;
        }
        if ( (PcwDatapathEventMask & 0x10) != 0 )
        {
          v35 = a4;
          if ( v34 == -1 )
          {
            v34 = KeGetPcr()->Prcb.Number;
            v136 = v34;
          }
          *(_QWORD *)((char *)Buffer + ndisPcwPerCpuDataStride * v34 + ndisPcwOffsetToPerCpuData + 32) += a4;
        }
        else
        {
          v35 = a4;
        }
        if ( (a5 & 2) != 0 )
        {
          if ( (PcwDatapathEventMask & 0x1000) != 0 )
          {
            if ( v34 == -1 )
            {
              v34 = KeGetPcr()->Prcb.Number;
              v136 = v34;
            }
            ++*(_QWORD *)((char *)Buffer + ndisPcwPerCpuDataStride * v34 + ndisPcwOffsetToPerCpuData + 232);
          }
          if ( (PcwDatapathEventMask & 0x2000) != 0 )
          {
            if ( v34 == -1 )
            {
              v34 = KeGetPcr()->Prcb.Number;
              v136 = v34;
            }
            *(_QWORD *)((char *)Buffer + ndisPcwPerCpuDataStride * v34 + ndisPcwOffsetToPerCpuData + 240) += v35;
          }
        }
        if ( (PcwDatapathCycleMask & 8) != 0 )
        {
          if ( v34 == -1 )
          {
            v34 = KeGetPcr()->Prcb.Number;
            v136 = v34;
          }
          *(_QWORD *)((char *)Buffer + ndisPcwPerCpuDataStride * v34 + ndisPcwOffsetToPerCpuData + 328) = __rdtsc();
        }
        else if ( v32 != 2 )
        {
          KeLowerIrql(v32);
        }
      }
      LODWORD(Context) = a5;
      v6->ReceiveNetBufferLists(v6->ReceiveNetBufferListsContext, Alignment, a3, a4, (unsigned int)Context);
      if ( (PcwDatapathCycleMask & 8) != 0 )
      {
        v60 = v136;
        if ( v136 == -1 )
          v60 = KeGetPcr()->Prcb.Number;
        v40 = (unsigned __int64)v33 + ndisPcwPerCpuDataStride * v60 + ndisPcwOffsetToPerCpuData;
        v61 = __rdtsc();
        *(_QWORD *)(v40 + 128) += (((unsigned __int64)HIDWORD(v61) << 32) | (unsigned int)v61) - *(_QWORD *)(v40 + 328);
        *(_QWORD *)(v40 + 328) = 0;
        if ( v125 != 2 )
          KeLowerIrql(v125);
      }
      if ( (a5 & 2) == 0 )
        goto LABEL_70;
      if ( *(_DWORD *)ndisNblTrackerMode )
      {
        NblTracker = (unsigned __int64)v6->NblTracker;
        v43 = 0;
        v164 = NblTracker;
        v155 = 0;
        if ( *(int *)ndisNblTrackerMode >= 3 )
          ndisNblTrackerRecordEventInternal(
            Alignment,
            (struct NDIS_NBL_TRACKER_HANDLE__ *)NblTracker,
            0x88u,
            (void *)0x20,
            a5 & 1);
        v44 = (_SLIST_HEADER *)Alignment;
        if ( Alignment )
        {
          v45 = a5 & 1;
          v46 = 0;
          while ( 1 )
          {
            Region = v44[22].Region;
            while ( v44[22].Region == Region )
            {
              if ( Region )
              {
                if ( (Region & 4) != 0 )
                  goto LABEL_158;
              }
              else if ( !v44[7].Region )
              {
                v62 = v164 & 0xFFFFFFFFFFFFFFFDuLL;
                if ( (v164 & 1) != 0 )
                  v62 = *(_QWORD *)((v164 & 0xFFFFFFFFFFFFFFF8uLL) + 24);
                v44[7].Region = v62;
              }
              v48 = (char *)v44[7].Region;
              if ( v48 )
              {
                LODWORD(NblTracker) = (unsigned __int8)*v48;
                if ( (unsigned __int8)(NblTracker - 17) <= 1u || (_BYTE)NblTracker == 5 )
                {
                  if ( v48 != (char *)32 || v44[1].Region )
                  {
                    ++v43;
                    v49 = 32;
                  }
                  else
                  {
                    ++v43;
                    v49 = 24;
                  }
                  goto LABEL_95;
                }
                if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                {
                  LOBYTE(NblTracker) = 3;
                  WPP_RECORDER_SF_qD(
                    *((_QWORD *)WPP_GLOBAL_Control + 8),
                    NblTracker,
                    27,
                    12,
                    (struct _GUID *)&WPP_78a33c75b2d2335d1cf1dcc315edf7b8_Traceguids,
                    (char)v44,
                    *v48);
                }
              }
              else if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(NblTracker) = 3;
                WPP_RECORDER_SF_q(
                  *((_QWORD *)WPP_GLOBAL_Control + 8),
                  NblTracker,
                  27,
                  11,
                  (struct _GUID *)&WPP_78a33c75b2d2335d1cf1dcc315edf7b8_Traceguids,
                  (char)v44);
              }
LABEL_158:
              v49 = 36;
LABEL_95:
              v44[22].Region = v49;
              v44 = (_SLIST_HEADER *)v44->Alignment;
              if ( !v44 )
                break;
            }
            if ( (Region & 1) == 0 )
              goto LABEL_101;
            NblTracker = v155 - v43;
            v156 = v155 - v43;
            if ( !v156 )
              goto LABEL_101;
            if ( v45 || v46 )
            {
              v40 = (Region & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((Region >> 1) & 1) + 3);
              if ( !v45 )
                goto LABEL_119;
              goto LABEL_100;
            }
            v46 = 1;
            v55 = KeGetCurrentIrql();
            NblTracker = v156;
            v56 = Region >> 1;
            v57 = Region & 0xFFFFFFFFFFFFFFF8uLL;
            v58 = 16 * ((v56 & 1) + 3);
            if ( v55 == 2 )
            {
              v45 = 1;
              v40 = v57 + v58;
LABEL_100:
              v50 = KeGetPcr()->Prcb.Number << 12;
              *(_QWORD *)(v50 + *(_QWORD *)v40) += NblTracker;
              goto LABEL_101;
            }
            v45 = 0;
            v40 = v57 + v58;
LABEL_119:
            _InterlockedAdd64((volatile signed __int64 *)(v40 + 8), NblTracker);
LABEL_101:
            v155 = v43;
            if ( !v44 )
            {
              v6 = a1;
              Alignment = (struct _NET_BUFFER_LIST *)v180;
              MiniportHandle = v163;
              break;
            }
          }
        }
      }
      if ( !ndisNblContextVerifierMode || ndisNblContextVerifierMode == 3 )
        goto LABEL_70;
      switch ( v6->Header.Type )
      {
        case 5u:
          v51 = LODWORD(v6->MiniportAdapterContext) >> 10;
          break;
        case 0x11u:
          v51 = LODWORD(v6[3].ReceivePacketHandler) >> 12;
          break;
        case 0x12u:
          v51 = v6->OpenFlags >> 31;
          goto LABEL_167;
        default:
LABEL_70:
          if ( (_BYTE)dword_140122F90 )
            WmiGetClock(0, 0, v40);
          if ( v123 )
          {
            v52 = v6->FrameTypeArray[0];
            if ( v52 == 0xDD86 || v52 == 1544 || v52 == 8 )
            {
              v53 = WmiGetClock(0, 0, v40);
              *(_DWORD *)WnodeEventItem = 0;
              v54 = v53 - Clock;
              LODWORD(v53) = (MiniportHandle->NetLuid.Value >> 24) & 0xFFFFFF;
              *(_DWORD *)&WnodeEventItem[5] = 0;
              v170 = v53;
              v171 = a4;
              *(_QWORD *)&WnodeEventItem[13] = 0;
              v174 = 0;
              v172 = v54;
              *(_WORD *)&WnodeEventItem[21] = 0;
              WnodeEventItem[23] = 0;
              v168 = 0;
              v169 = 0x20000;
              *(GUID *)&WnodeEventItem[24] = EtwGuidNdisReceive;
              WnodeEventItem[4] = 16;
              v173 = KeGetPcr()->Prcb.Number;
              strcpy(WnodeEventItem, "H");
              *(_QWORD *)&WnodeEventItem[8] = qword_140122F88;
              IoWMIWriteEvent(WnodeEventItem);
            }
          }
          return;
      }
      LOBYTE(v51) = v51 & 1;
LABEL_167:
      if ( (_BYTE)v51 )
        ndisRemoveNblContextTerminator(Alignment, (struct _NDIS_OBJECT_HEADER *)v6);
      goto LABEL_70;
    }
    v13 = v6->NblTracker;
    v14 = v12;
    v15 = ndisNblTrackerEpoch;
    v16 = v14 & 1;
    v142 = v16;
    v17 = 0;
    v130 = 0;
    v18 = 0;
    v150 = 0;
    v146 = 0;
    v128 = 0;
    if ( *(int *)ndisNblTrackerMode >= 3 )
    {
      ndisNblTrackerRecordEventInternal(
        Alignment,
        (struct NDIS_NBL_TRACKER_HANDLE__ *)0x20,
        (a5 & 2 | 0x108) >> 1,
        v13,
        v16);
      LOBYTE(v16) = v142;
      v17 = 0;
      v18 = 0;
    }
    v19 = (unsigned __int64)v13 & 0xFFFFFFFFFFFFFFFDuLL;
    v137 = (unsigned __int64)v13 & 0xFFFFFFFFFFFFFFFDuLL;
    if ( ((unsigned __int8)v13 & 1) != 0 )
    {
      v20 = (2 * v15) ^ ((unsigned __int64)v13 ^ (2 * v15)) & 0xFFFFFFFFFFFFFFFDuLL;
      v19 = *(_QWORD *)(((unsigned __int64)v13 & 0xFFFFFFFFFFFFFFF8uLL) + 24);
      v137 = v19;
    }
    else
    {
      v20 = (unsigned __int64)v13 & 0xFFFFFFFFFFFFFFFDuLL;
    }
    v21 = (_SLIST_HEADER *)Alignment;
    if ( Alignment )
    {
      v22 = 0;
      while ( 1 )
      {
        v23 = v21[22].Region;
        while ( v21[22].Region == v23 )
        {
          if ( v23 )
          {
            if ( (v23 & 4) != 0 )
              goto LABEL_121;
          }
          else if ( !v21[7].Region )
          {
            v21[7].Region = 32;
          }
          v24 = (char *)v21[7].Region;
          if ( v24 )
          {
            LODWORD(a2) = (unsigned __int8)*v24;
            if ( (unsigned __int8)(a2 - 17) <= 1u || (_BYTE)a2 == 5 )
            {
              if ( v24 != (char *)v19 || v21[1].Region )
              {
                v17 = (struct _NET_BUFFER_LIST *)((char *)v17 + 1);
                v25 = v20;
                v130 = v17;
              }
              else
              {
                ++v18;
                v25 = 24;
                v17 = (struct _NET_BUFFER_LIST *)((char *)v17 + 1);
                v146 = v18;
                v130 = v17;
              }
              goto LABEL_26;
            }
            if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(a2) = 3;
              WPP_RECORDER_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                a2,
                27,
                12,
                (struct _GUID *)&WPP_78a33c75b2d2335d1cf1dcc315edf7b8_Traceguids,
                (char)v21,
                *v24);
LABEL_320:
              v17 = v130;
              v19 = v137;
              v18 = v146;
            }
          }
          else if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(a2) = 3;
            WPP_RECORDER_SF_q(
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              a2,
              27,
              11,
              (struct _GUID *)&WPP_78a33c75b2d2335d1cf1dcc315edf7b8_Traceguids,
              (char)v21);
            goto LABEL_320;
          }
LABEL_121:
          v25 = v20 | 4;
LABEL_26:
          v21[22].Region = v25;
          v21 = (_SLIST_HEADER *)v21->Alignment;
          if ( !v21 )
            break;
        }
        LOBYTE(v16) = v142;
        if ( (v23 & 1) == 0 )
          goto LABEL_32;
        v26 = (char *)v150 - (char *)v17;
        v151 = (struct _NET_BUFFER_LIST *)((char *)v150 - (char *)v17);
        if ( !v151 )
          goto LABEL_32;
        if ( v142 || v22 )
        {
          a2 = (v23 & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((v23 >> 1) & 1) + 3);
          if ( !v142 )
            goto LABEL_60;
          goto LABEL_31;
        }
        v22 = 1;
        v36 = KeGetCurrentIrql();
        v17 = v130;
        v37 = v23;
        v19 = v137;
        v38 = v23 & 0xFFFFFFFFFFFFFFF8uLL;
        v26 = (unsigned __int64)v151;
        v39 = 16 * (((v37 >> 1) & 1) + 3);
        if ( v36 == 2 )
        {
          LOBYTE(v16) = 1;
          a2 = v38 + v39;
          v142 = 1;
LABEL_31:
          v27 = KeGetPcr()->Prcb.Number << 12;
          *(_QWORD *)(v27 + *(_QWORD *)a2) += v26;
          goto LABEL_32;
        }
        LOBYTE(v16) = 0;
        v142 = 0;
        a2 = v38 + v39;
LABEL_60:
        _InterlockedAdd64((volatile signed __int64 *)(a2 + 8), v26);
LABEL_32:
        v18 = v146;
        v150 = v17;
        if ( !v21 )
        {
          v6 = a1;
          Alignment = (struct _NET_BUFFER_LIST *)v180;
          v128 = v22;
          MiniportHandle = v163;
          break;
        }
      }
    }
    if ( (v20 & 1) == 0 || (v28 = (unsigned __int64)v17 - v146, (v131 = v28) == 0) )
    {
LABEL_42:
      LOBYTE(PcwDatapathCycleMask) = v145;
      goto LABEL_43;
    }
    if ( (_BYTE)v16 || v128 )
    {
      v30 = (v20 & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((v20 >> 1) & 1) + 3);
      if ( !(_BYTE)v16 )
        goto LABEL_39;
    }
    else
    {
      v29 = KeGetCurrentIrql();
      v28 = v131;
      v30 = (v20 & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((v20 >> 1) & 1) + 3);
      if ( v29 != 2 )
      {
LABEL_39:
        _InterlockedAdd64((volatile signed __int64 *)(v30 + 8), v28);
        goto LABEL_42;
      }
    }
    v31 = KeGetPcr()->Prcb.Number << 12;
    *(_QWORD *)(v31 + *(_QWORD *)v30) += v28;
    goto LABEL_42;
  }
}

```

## disassembly

```asm
0x14002bee0  mov     [rsp-8+arg_18], r9d
0x14002bee5  mov     [rsp-8+arg_10], r8d
0x14002beea  mov     [rsp-8+arg_8], rdx
0x14002beef  mov     [rsp-8+arg_0], rcx
0x14002bef4  push    rbp
0x14002bef5  push    rbx
0x14002bef6  push    r12
0x14002bef8  push    r13
0x14002befa  push    r14
0x14002befc  push    r15
0x14002befe  lea     rbp, [rsp-1B8h]
0x14002bf06  sub     rsp, 2B8h
0x14002bf0d  mov     r13, [rcx+10h]
0x14002bf11  mov     r14, rcx
0x14002bf14  xor     ebx, ebx
0x14002bf16  mov     [rbp+1E0h+var_248], r13
0x14002bf1a  mov     r15, rdx
0x14002bf1d  mov     ecx, [r13+30h]
0x14002bf21  test    ecx, ecx
0x14002bf23  jnz     loc_14002C452
0x14002bf29  mov     r12d, ebx
0x14002bf2c  mov     [rbp+1E0h+var_260], rbx
0x14002bf30  mov     [rbp+1E0h+var_24C], ebx
0x14002bf33  mov     dword ptr [rsp+2E0h+var_278], ebx
0x14002bf37  cmp     [r13+50h], ebx
0x14002bf3b  jnz     loc_14002C452
0x14002bf41  mov     rcx, [rdx+78h]
0x14002bf45  mov     r8d, [r15+88h]
0x14002bf4c  cmp     rcx, r14
0x14002bf4f  setz    dl
0x14002bf52  test    dword ptr [r15+80h], 8000h
0x14002bf5d  jnz     loc_14002C95F
0x14002bf63  cmp     rcx, r14
0x14002bf66  jz      loc_14002C96E
0x14002bf6c  cmp     byte ptr [r13+7CEh], 0
0x14002bf74  jz      short loc_14002BF84
0x14002bf76  cmp     dword ptr [r14+1B0h], 0
0x14002bf7e  jz      loc_14002C37C
0x14002bf84  test    dword ptr [r14+1B0h], 10000h
0x14002bf8f  jnz     loc_14002C36B
0x14002bf95  mov     eax, cs:?ndisNblContextVerifierMode@@3W4NDIS_NBL_CONTEXT_VERIFIER_MODE@@A; NDIS_NBL_CONTEXT_VERIFIER_MODE ndisNblContextVerifierMode
0x14002bf9b  mov     [rsp+2E0h+var_30], rsi
0x14002bfa3  mov     [rsp+2E0h+var_38], rdi
0x14002bfab  mov     edi, [rbp+1E0h+arg_20]
0x14002bfb1  test    eax, eax
0x14002bfb3  jnz     loc_14002C48D
0x14002bfb9  cmp     byte ptr cs:dword_140122F90, 0
0x14002bfc0  mov     [rsp+2E0h+var_290], 0FFFFFFFFh
0x14002bfc8  mov     [rsp+2E0h+var_29F], 2
0x14002bfcd  jnz     loc_14002CAFC
0x14002bfd3  mov     [rbp+1E0h+var_258], rbx
0x14002bfd7  mov     [rsp+2E0h+var_2A0], 0
0x14002bfdc  mov     eax, cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x14002bfe2  test    eax, eax
0x14002bfe4  jz      loc_14002C21A
0x14002bfea  mov     rsi, [r14+248h]
0x14002bff1  mov     r10d, edi
0x14002bff4  mov     edi, cs:?ndisNblTrackerEpoch@@3KA; ulong ndisNblTrackerEpoch
0x14002bffa  and     r10d, 1
0x14002bffe  mov     dword ptr [rsp+2E0h+var_280], r10d
0x14002c003  mov     r8, rbx
0x14002c006  mov     [rsp+2E0h+var_298], rbx
0x14002c00b  mov     r11, rbx
0x14002c00e  mov     [rsp+2E0h+var_268], rbx
0x14002c013  mov     [rsp+2E0h+var_270], rbx
0x14002c018  mov     [rsp+2E0h+var_29E], 0
0x14002c01d  cmp     eax, 3
0x14002c020  jl      short loc_14002C057
0x14002c022  mov     r8d, [rbp+1E0h+arg_20]
0x14002c029  mov     r9, rsi; void *
0x14002c02c  and     r8d, 2
0x14002c030  mov     dword ptr [rsp+2E0h+Context], r10d; unsigned int
0x14002c035  or      r8d, 108h
0x14002c03c  mov     edx, 20h ; ' '; struct NDIS_NBL_TRACKER_HANDLE__ *
0x14002c041  shr     r8d, 1; unsigned int
0x14002c044  mov     rcx, r15; struct _NET_BUFFER_LIST *
0x14002c047  call    ?ndisNblTrackerRecordEventInternal@@YAXPEAU_NET_BUFFER_LIST@@PEAUNDIS_NBL_TRACKER_HANDLE__@@KPEAXK@Z; ndisNblTrackerRecordEventInternal(_NET_BUFFER_LIST *,NDIS_NBL_TRACKER_HANDLE__ *,ulong,void *,ulong)
0x14002c04c  mov     r10d, dword ptr [rsp+2E0h+var_280]
0x14002c051  mov     r8, rbx
0x14002c054  mov     r11, rbx
0x14002c057  mov     r9, rsi
0x14002c05a  and     r9, 0FFFFFFFFFFFFFFFDh
0x14002c05e  mov     [rsp+2E0h+var_288], r9
0x14002c063  test    r9b, 1
0x14002c067  jz      loc_14002C664
0x14002c06d  mov     rax, rdi
0x14002c070  add     rax, rax
0x14002c073  mov     rdi, rax
0x14002c076  xor     rdi, rsi
0x14002c079  and     rdi, 0FFFFFFFFFFFFFFFDh
0x14002c07d  xor     rdi, rax
0x14002c080  and     r9, 0FFFFFFFFFFFFFFF8h
0x14002c084  mov     r9, [r9+18h]
0x14002c088  mov     [rsp+2E0h+var_288], r9
0x14002c08d  mov     r12, r15
0x14002c090  test    r15, r15
0x14002c093  jz      loc_14002C192
0x14002c099  xor     r13b, r13b
0x14002c09c  lea     r14, WPP_RECORDER_INITIALIZED
0x14002c0a3  lea     r15, WPP_78a33c75b2d2335d1cf1dcc315edf7b8_Traceguids
0x14002c0aa  mov     rsi, [r12+168h]
0x14002c0b2  cmp     [r12+168h], rsi
0x14002c0ba  jnz     short loc_14002C110
0x14002c0bc  test    rsi, rsi
0x14002c0bf  jz      loc_14002C71D
0x14002c0c5  test    sil, 4
0x14002c0c9  jnz     loc_14002C78E
0x14002c0cf  mov     rcx, [r12+78h]
0x14002c0d4  test    rcx, rcx
0x14002c0d7  jz      loc_14002C781
0x14002c0dd  movzx   edx, byte ptr [rcx]
0x14002c0e0  lea     eax, [rdx-11h]
0x14002c0e3  cmp     al, 1
0x14002c0e5  ja      loc_14002C889
0x14002c0eb  cmp     rcx, r9
0x14002c0ee  jz      loc_14002C63E
0x14002c0f4  inc     r8
0x14002c0f7  mov     rax, rdi
0x14002c0fa  mov     [rsp+2E0h+var_298], r8
0x14002c0ff  mov     [r12+168h], rax
0x14002c107  mov     r12, [r12]
0x14002c10b  test    r12, r12
0x14002c10e  jnz     short loc_14002C0B2
0x14002c110  mov     r10d, dword ptr [rsp+2E0h+var_280]
0x14002c115  test    sil, 1
0x14002c119  jz      short loc_14002C168
0x14002c11b  mov     r11, [rsp+2E0h+var_268]
0x14002c120  sub     r11, r8
0x14002c123  mov     [rsp+2E0h+var_268], r11
0x14002c128  jz      short loc_14002C168
0x14002c12a  test    r10b, r10b
0x14002c12d  jz      loc_14002C312
0x14002c133  mov     rdx, rsi
0x14002c136  and     rsi, 0FFFFFFFFFFFFFFF8h
0x14002c13a  shr     rdx, 1
0x14002c13d  and     edx, 1
0x14002c140  add     rdx, 3
0x14002c144  shl     rdx, 4
0x14002c148  add     rdx, rsi
0x14002c14b  test    r10b, r10b
0x14002c14e  jz      loc_14002C361
0x14002c154  mov     eax, gs:1A4h
0x14002c15c  shl     eax, 0Ch
0x14002c15f  mov     ecx, eax
0x14002c161  mov     rax, [rdx]
0x14002c164  add     [rcx+rax], r11
0x14002c168  mov     r11, [rsp+2E0h+var_270]
0x14002c16d  mov     [rsp+2E0h+var_268], r8
0x14002c172  test    r12, r12
0x14002c175  jnz     loc_14002C0AA
0x14002c17b  mov     r14, [rbp+1E0h+arg_0]
0x14002c182  mov     r15, [rbp+1E0h+arg_8]
0x14002c189  mov     [rsp+2E0h+var_29E], r13b
0x14002c18e  mov     r13, [rbp+1E0h+var_248]
0x14002c192  test    dil, 1
0x14002c196  jz      short loc_14002C215
0x14002c198  sub     r8, [rsp+2E0h+var_270]
0x14002c19d  mov     [rsp+2E0h+var_298], r8
0x14002c1a2  jz      short loc_14002C215
0x14002c1a4  test    r10b, r10b
0x14002c1a7  jnz     short loc_14002C1E4
0x14002c1a9  cmp     [rsp+2E0h+var_29E], r10b
0x14002c1ae  jnz     short loc_14002C1E4
0x14002c1b0  call    cs:__imp_KeGetCurrentIrql
0x14002c1b7  nop     dword ptr [rax+rax+00h]
0x14002c1bc  mov     r8, [rsp+2E0h+var_298]
0x14002c1c1  mov     rdx, rdi
0x14002c1c4  shr     rdx, 1
0x14002c1c7  and     rdi, 0FFFFFFFFFFFFFFF8h
0x14002c1cb  and     edx, 1
0x14002c1ce  add     rdx, 3
0x14002c1d2  shl     rdx, 4
0x14002c1d6  add     rdx, rdi
0x14002c1d9  cmp     al, 2
0x14002c1db  jz      short loc_14002C201
0x14002c1dd  lock add [rdx+8], r8
0x14002c1e2  jmp     short loc_14002C215
0x14002c1e4  mov     rdx, rdi
0x14002c1e7  and     rdi, 0FFFFFFFFFFFFFFF8h
0x14002c1eb  shr     rdx, 1
0x14002c1ee  and     edx, 1
0x14002c1f1  add     rdx, 3
0x14002c1f5  shl     rdx, 4
0x14002c1f9  add     rdx, rdi
0x14002c1fc  test    r10b, r10b
0x14002c1ff  jz      short loc_14002C1DD
0x14002c201  mov     eax, gs:1A4h
0x14002c209  shl     eax, 0Ch
0x14002c20c  mov     ecx, eax
0x14002c20e  mov     rax, [rdx]
0x14002c211  add     [rcx+rax], r8
0x14002c215  mov     r12d, dword ptr [rsp+2E0h+var_278]
0x14002c21a  cmp     cs:byte_140123720, 0
0x14002c221  jnz     loc_14002C9C4
0x14002c227  mov     edi, [rbp+1E0h+var_24C]
0x14002c22a  test    edi, 3014h
0x14002c230  setz    cl
0x14002c233  test    r12b, 8
0x14002c237  setz    al
0x14002c23a  test    al, cl
0x14002c23c  jnz     loc_14002C79A
0x14002c242  test    byte ptr [rbp+1E0h+arg_20], 1
0x14002c249  jnz     loc_14002C9BC
0x14002c24f  mov     cl, 2; NewIrql
0x14002c251  call    cs:__imp_KfRaiseIrql
0x14002c258  nop     dword ptr [rax+rax+00h]
0x14002c25d  movzx   r11d, al
0x14002c261  mov     [rsp+2E0h+var_29F], al
0x14002c265  mov     rsi, [rbp+1E0h+var_260]
0x14002c269  test    dil, 4
0x14002c26d  jz      loc_14002CB26
0x14002c273  mov     r10d, gs:1A4h
0x14002c27c  mov     ecx, r10d
0x14002c27f  imul    ecx, cs:?ndisPcwPerCpuDataStride@@3KA; ulong ndisPcwPerCpuDataStride
0x14002c286  mov     r8d, cs:?ndisPcwOffsetToPerCpuData@@3KA; ulong ndisPcwOffsetToPerCpuData
0x14002c28d  mov     [rsp+2E0h+var_290], r10d
0x14002c292  add     rcx, rsi
0x14002c295  inc     qword ptr [r8+rcx+10h]
0x14002c29a  test    dil, 10h
0x14002c29e  jz      loc_14002CB1A
0x14002c2a4  mov     r9d, [rbp+1E0h+arg_18]
0x14002c2ab  cmp     r10d, 0FFFFFFFFh
0x14002c2af  jnz     short loc_14002C2BF
0x14002c2b1  mov     r10d, gs:1A4h
0x14002c2ba  mov     [rsp+2E0h+var_290], r10d
0x14002c2bf  mov     edx, cs:?ndisPcwOffsetToPerCpuData@@3KA; ulong ndisPcwOffsetToPerCpuData
0x14002c2c5  mov     eax, r10d
0x14002c2c8  imul    eax, cs:?ndisPcwPerCpuDataStride@@3KA; ulong ndisPcwPerCpuDataStride
0x14002c2cf  add     rax, rsi
0x14002c2d2  add     [rdx+rax+20h], r9
0x14002c2d7  test    byte ptr [rbp+1E0h+arg_20], 2
0x14002c2de  jnz     loc_14002C8E9
0x14002c2e4  mov     eax, r12d
0x14002c2e7  and     eax, 8
0x14002c2ea  mov     dword ptr [rbp+1E0h+var_240], eax
0x14002c2ed  jnz     loc_14002C3A5
0x14002c2f3  cmp     r11b, 2
0x14002c2f7  jz      loc_14002C3DE
0x14002c2fd  movzx   ecx, r11b; NewIrql
0x14002c301  call    cs:__imp_KeLowerIrql
0x14002c308  nop     dword ptr [rax+rax+00h]
0x14002c30d  jmp     loc_14002C3DE
0x14002c312  test    r13b, r13b
0x14002c315  jnz     loc_14002C133
0x14002c31b  mov     r13b, 1
0x14002c31e  call    cs:__imp_KeGetCurrentIrql
0x14002c325  nop     dword ptr [rax+rax+00h]
0x14002c32a  mov     r8, [rsp+2E0h+var_298]
0x14002c32f  mov     rdx, rsi
0x14002c332  mov     r9, [rsp+2E0h+var_288]
0x14002c337  and     rsi, 0FFFFFFFFFFFFFFF8h
0x14002c33b  mov     r11, [rsp+2E0h+var_268]
0x14002c340  shr     rdx, 1
0x14002c343  and     edx, 1
0x14002c346  add     rdx, 3
0x14002c34a  shl     rdx, 4
0x14002c34e  cmp     al, 2
0x14002c350  jz      loc_14002C47C
0x14002c356  xor     r10b, r10b
0x14002c359  mov     dword ptr [rsp+2E0h+var_280], r10d
0x14002c35e  add     rdx, rsi
0x14002c361  lock add [rdx+8], r11
0x14002c366  jmp     loc_14002C168
0x14002c36b  test    dl, dl
0x14002c36d  jnz     loc_14002BF95
0x14002c373  test    r8b, r8b
0x14002c376  jns     loc_14002BF95
0x14002c37c  mov     r8d, [rbp+1E0h+arg_20]
0x14002c383  test    r8b, 2
0x14002c387  jnz     loc_14002C44C
0x14002c38d  and     r8d, 1; unsigned int
0x14002c391  xor     r9d, r9d; struct _NDIS_OPEN_BLOCK *
0x14002c394  mov     rdx, r15; struct _NET_BUFFER_LIST *
0x14002c397  mov     rcx, r13; struct _NDIS_FILTER_BLOCK *
0x14002c39a  call    ?ndisReturnNetBufferListsInternal@@YAXPEAXPEAU_NET_BUFFER_LIST@@KPEAU_NDIS_OPEN_BLOCK@@@Z; ndisReturnNetBufferListsInternal(void *,_NET_BUFFER_LIST *,ulong,_NDIS_OPEN_BLOCK *)
0x14002c39f  jmp     loc_14002D608
0x14002c3a5  cmp     r10d, 0FFFFFFFFh
0x14002c3a9  jnz     short loc_14002C3B9
0x14002c3ab  mov     r10d, gs:1A4h
0x14002c3b4  mov     [rsp+2E0h+var_290], r10d
0x14002c3b9  rdtsc
0x14002c3bb  mov     r8d, cs:?ndisPcwOffsetToPerCpuData@@3KA; ulong ndisPcwOffsetToPerCpuData
0x14002c3c2  mov     ecx, r10d
0x14002c3c5  imul    ecx, cs:?ndisPcwPerCpuDataStride@@3KA; ulong ndisPcwPerCpuDataStride
0x14002c3cc  shl     rdx, 20h
0x14002c3d0  or      rax, rdx
0x14002c3d3  add     rcx, rsi
0x14002c3d6  mov     [r8+rcx+148h], rax
0x14002c3de  mov     rax, [r14+220h]
0x14002c3e5  mov     rdx, r15
0x14002c3e8  mov     edi, [rbp+1E0h+arg_20]
0x14002c3ee  mov     r9d, [rbp+1E0h+arg_18]
0x14002c3f5  mov     r8d, [rbp+1E0h+arg_10]
0x14002c3fc  mov     rcx, [r14+228h]
0x14002c403  mov     dword ptr [rsp+2E0h+Context], edi
0x14002c407  call    _guard_dispatch_icall
0x14002c40c  and     r12d, 8
0x14002c410  mov     dword ptr [rbp+1E0h+var_240], r12d
0x14002c414  jnz     loc_14002C827
0x14002c41a  test    dil, 2
  ... truncated ...
```
