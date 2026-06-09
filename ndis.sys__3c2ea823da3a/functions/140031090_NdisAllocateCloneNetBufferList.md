# NdisAllocateCloneNetBufferList

- ea: `0x140031090`
- end: `0x1400319cb`
- name: `NdisAllocateCloneNetBufferList`
- size: `2363`
- prototype: `PNET_BUFFER_LIST __stdcall(PNET_BUFFER_LIST OriginalNetBufferList, NDIS_HANDLE NetBufferListPoolHandle, NDIS_HANDLE NetBufferPoolHandle, ULONG AllocateCloneFlags)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140030570`
- `0x140031090`
- `0x140032120`
- `0x140032aa0`
- `0x140032ee0`
- `0x140033240`
- `0x140033510`
- `0x1400e6160`
- `0x1400e65c0`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x14003196e`
- `ntoskrnl!DbgPrint` at `0x14003198c`
- `ntoskrnl!DbgPrint` at `0x14003196e`
- `ntoskrnl!DbgPrint` at `0x14003198c`
- `ntoskrnl!ExAllocatePool2` at `0x1400317f0`
- `ntoskrnl!ExAllocatePool2` at `0x1400317f0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400311cf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140031778`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003185c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400311cf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140031778`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003185c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031158`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031746`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003181d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031158`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031746`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003181d`
- `ntoskrnl!EtwWriteTransfer` at `0x14003172b`
- `ntoskrnl!EtwWriteTransfer` at `0x14003172b`
- `ntoskrnl!IoAllocateMdl` at `0x140031393`
- `ntoskrnl!IoAllocateMdl` at `0x1400318ba`
- `ntoskrnl!IoAllocateMdl` at `0x140031393`
- `ntoskrnl!IoAllocateMdl` at `0x1400318ba`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400311b1`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400311b1`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400313b4`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400318e0`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400313b4`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400318e0`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400311e6`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14003178b`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400317b9`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400311e6`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14003178b`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400317b9`
- `ntoskrnl!ExQueryDepthSList` at `0x14003190f`
- `ntoskrnl!ExQueryDepthSList` at `0x14003190f`
- `NETIO!WfpNblInfoClone` at `0x140031482`
- `NETIO!WfpNblInfoClone` at `0x140031482`

## pseudocode

```c
PNET_BUFFER_LIST __stdcall NdisAllocateCloneNetBufferList(
        PNET_BUFFER_LIST OriginalNetBufferList,
        NDIS_HANDLE NetBufferListPoolHandle,
        NDIS_HANDLE NetBufferPoolHandle,
        ULONG AllocateCloneFlags)
{
  unsigned __int64 v4; // rbp
  char *v5; // rsi
  _DWORD *v6; // r13
  ULONG v7; // edi
  PNET_BUFFER_LIST v8; // r12
  int v9; // eax
  unsigned int Number; // edi
  unsigned int v11; // r13d
  bool v12; // zf
  unsigned __int64 v13; // rbx
  char *v14; // rdi
  KIRQL v15; // r12
  struct _NET_BUFFER_LIST *NetBufferList; // rbx
  __int16 v17; // di
  _SLIST_HEADER *v18; // rdx
  unsigned int v19; // ecx
  unsigned __int64 v20; // rax
  int v21; // eax
  _SLIST_HEADER *v22; // rax
  struct _NET_BUFFER *FirstNetBuffer; // r14
  char v24; // al
  _NET_BUFFER *v25; // rdi
  int v26; // eax
  ULONG DataOffset; // edx
  struct _MDL *MdlChain; // r15
  ULONG ByteCount; // eax
  ULONG DataLength; // r12d
  ULONG v31; // eax
  ULONG v32; // r13d
  struct _MDL *v33; // rsi
  char *v34; // rcx
  struct _MDL *Mdl; // rax
  ULONG v36; // r12d
  PNET_BUFFER NetBuffer; // rax
  _QWORD *v38; // r12
  _QWORD *Alignment; // rcx
  __int64 v41; // rax
  unsigned int v42; // edx
  struct _NET_BUFFER *NetBufferInternal; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  const GUID *v46; // r9
  REGHANDLE v47; // rcx
  const EVENT_DESCRIPTOR *v48; // rdx
  int v49; // eax
  KIRQL v50; // al
  __int64 v51; // r8
  unsigned __int64 v52; // rax
  char **Pool2; // rax
  KIRQL v54; // al
  char **v55; // rdx
  _QWORD *v56; // rcx
  KIRQL v57; // r8
  void **v58; // rax
  ULONG v59; // eax
  ULONG v60; // ecx
  char *v61; // r10
  struct _MDL *v62; // rax
  struct _MDL *v63; // r13
  int Flags; // [rsp+20h] [rbp-60h]
  int v65; // [rsp+80h] [rbp+0h] BYREF

  v4 = (unsigned __int64)&v65 & 0xFFFFFFFFFFFFFFC0uLL;
  *(_DWORD *)(v4 + 8) = AllocateCloneFlags;
  v5 = (char *)NetBufferListPoolHandle;
  *(_QWORD *)(v4 + 128) = OriginalNetBufferList;
  if ( !NetBufferListPoolHandle )
    v5 = (char *)ndisNetBufferListPool;
  v6 = NetBufferPoolHandle;
  v7 = AllocateCloneFlags;
  v8 = OriginalNetBufferList;
  if ( !NetBufferPoolHandle )
    v6 = ndisNetBufferPool;
  v9 = *((_DWORD *)v5 + 11);
  *(_QWORD *)(((unsigned __int64)&v65 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40) = v6;
  if ( (v9 & 1) == 0 )
  {
    NetBufferList = NdisAllocateNetBufferList(v5, 0, 0);
    if ( !NetBufferList )
      return NetBufferList;
    *(_DWORD *)(((unsigned __int64)&v65 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10) = 0;
    if ( v6 )
    {
      if ( (v6[20] & 1) != 0 )
      {
        DbgPrint("NdisAllocateNetBuffer: Pool %p wrong pool type.\n", v6);
      }
      else
      {
        NetBufferInternal = ndisAllocateNetBufferInternal(v6, (unsigned int *)(v4 + 16));
        FirstNetBuffer = NetBufferInternal;
        if ( NetBufferInternal )
        {
          NetBufferInternal->NdisPoolHandle = v6;
          NetBufferInternal->NdisReserved[1] = 0;
          NetBufferInternal->NdisReserved[0] = 0;
          NetBufferInternal->MiniportReserved[1] = 0;
          NetBufferInternal->MiniportReserved[0] = 0;
          NetBufferInternal->MdlChain = 0;
          NetBufferInternal->DataOffset = 0;
          NetBufferInternal->DataLength = 0;
          NetBufferInternal->Link.Region = 0;
          NetBufferInternal->CurrentMdlOffset = 0;
          NetBufferInternal->Link.Alignment = 0;
          *(_DWORD *)&NetBufferInternal->ChecksumBias = 0;
          NetBufferInternal->SharedMemoryInfo = 0;
          NetBufferList->Link.Region = (unsigned __int64)NetBufferInternal;
          goto LABEL_33;
        }
      }
    }
LABEL_48:
    NdisFreeCloneNetBufferList(NetBufferList, v7);
    return 0;
  }
  if ( (v9 & 4) != 0 )
  {
    DbgPrint("NdisAllocateNetBufferAndNetBufferList: Pool %p wrong pool type.\n", v5);
    return 0;
  }
  if ( (*((_DWORD *)v5 + 1) & 1) != 0 )
  {
    v11 = 0;
    NetBufferList = (struct _NET_BUFFER_LIST *)ndisPplAllocateFromSpecialPool((const struct _NDIS_POOL_HEADER *)v5);
    goto LABEL_15;
  }
  Number = KeGetPcr()->Prcb.Number;
  v11 = 1;
  v12 = ndisMaxNumberOfProcessors == 1;
  *(_DWORD *)(((unsigned __int64)&v65 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10) = Number;
  if ( !v12 )
  {
    v13 = (unsigned __int64)Number << 8;
    v14 = &v5[v13 + 384];
    if ( !v14[216] )
    {
      v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v14 + 26);
      if ( !v14[216] )
      {
        ExInitializeLookasideListEx(
          (PLOOKASIDE_LIST_EX)&v5[v13 + 384],
          ndisAllocateFromNPagedPool,
          *((PFREE_FUNCTION_EX *)v5 + 23),
          NonPagedPoolNx,
          0,
          *((unsigned int *)v5 + 43),
          *((_DWORD *)v5 + 42),
          0x400u);
        v14[216] = 1;
      }
      KeReleaseSpinLock((PKSPIN_LOCK)v14 + 26, v15);
    }
    _InterlockedIncrement((volatile signed __int32 *)v14 + 5);
    NetBufferList = (struct _NET_BUFFER_LIST *)ExpInterlockedPopEntrySList(*((PSLIST_HEADER *)v14 + 24));
    if ( NetBufferList )
      goto LABEL_14;
    if ( ExQueryDepthSList(*((PSLIST_HEADER *)v14 + 25)) >= 0xAu )
    {
      v50 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v14 + 26);
      v51 = *((_QWORD *)v14 + 24);
      *((_QWORD *)v14 + 24) = *((_QWORD *)v14 + 25);
      *((_QWORD *)v14 + 25) = v51;
      KeReleaseSpinLock((PKSPIN_LOCK)v14 + 26, v50);
      NetBufferList = (struct _NET_BUFFER_LIST *)ExpInterlockedPopEntrySList(*((PSLIST_HEADER *)v14 + 24));
      if ( NetBufferList )
        goto LABEL_14;
    }
    _InterlockedIncrement((volatile signed __int32 *)v14 + 6);
    Number = *(_DWORD *)(((unsigned __int64)&v65 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10);
  }
  _InterlockedIncrement((volatile signed __int32 *)v5 + 37);
  NetBufferList = (struct _NET_BUFFER_LIST *)ExpInterlockedPopEntrySList((PSLIST_HEADER)v5 + 8);
  if ( NetBufferList )
    goto LABEL_89;
  _InterlockedIncrement((volatile signed __int32 *)v5 + 38);
  v52 = *((unsigned int *)v5 + 43);
  if ( v52 + 32 < v52 || (Pool2 = (char **)ExAllocatePool2(66, v52 + 32, *((unsigned int *)v5 + 42))) == 0 )
  {
    NetBufferList = 0;
    goto LABEL_100;
  }
  NetBufferList = (struct _NET_BUFFER_LIST *)(Pool2 + 4);
  *Pool2 = 0;
  if ( Pool2 == (char **)-32LL )
  {
LABEL_100:
    v11 = 0;
    goto LABEL_14;
  }
  *Pool2 = v5;
  v54 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v5 + 1);
  v55 = (char **)*((_QWORD *)v5 + 2);
  v56 = v5 + 16;
  v57 = v54;
  if ( v55[1] != v5 + 16 )
    __fastfail(3u);
  v58 = &NetBufferList[-1].NetBufferListInfo[27];
  *v58 = v55;
  v58[1] = v56;
  v55[1] = (char *)&NetBufferList[-1].NetBufferListInfo[27];
  *v56 = (char *)NetBufferList - 24;
  KeReleaseSpinLock((PKSPIN_LOCK)v5 + 1, v57);
  v11 = 0;
LABEL_89:
  LODWORD(NetBufferList[-1].NetBufferListInfo[29]) = Number;
LABEL_14:
  v8 = *(PNET_BUFFER_LIST *)(((unsigned __int64)&v65 & 0xFFFFFFFFFFFFFFC0uLL) + 0x80);
LABEL_15:
  if ( NetBufferList )
  {
    v17 = WORD1(NetBufferList->NdisReserved[1]);
    memset(NetBufferList, 0, 8 * (v11 ^ 1LL) + 368);
    NetBufferList->NdisPoolHandle = v5;
    NetBufferList->Flags = 256;
    if ( v11 )
      WORD1(NetBufferList->NdisReserved[1]) = v17;
    if ( Microsoft_Windows_Networking_CorrelationEnabled )
    {
      if ( (__int64)NetBufferList->NetBufferListInfo[13] > 0 )
      {
        Alignment = (_QWORD *)NetBufferList->Link.Alignment;
        if ( NetBufferList->Link.Alignment )
        {
          do
          {
            v41 = Alignment[31];
            if ( !v41 || v41 < 0 )
            {
              v42 = _InterlockedExchangeAdd(&dword_14011AE28, 1u);
              if ( v42 + 1 < v42 )
                v42 = _InterlockedExchangeAdd(&dword_14011AE28, 1u);
              Alignment[31] = v42;
            }
            Alignment = (_QWORD *)*Alignment;
          }
          while ( Alignment );
        }
      }
      else
      {
        v18 = (_SLIST_HEADER *)NetBufferList;
        v19 = _InterlockedExchangeAdd(&dword_14011AE28, 1u);
        if ( v19 + 1 < v19 )
          v19 = _InterlockedExchangeAdd(&dword_14011AE28, 1u);
        do
        {
          if ( (__int64)v18[15].Region <= 0 )
          {
            v20 = v19++;
            v18[15].Region = v20;
          }
          v18 = (_SLIST_HEADER *)v18->Alignment;
        }
        while ( v18 );
      }
    }
    LOBYTE(NetBufferList->NetBufferListInfo[7]) = v5[40];
    v21 = *((_DWORD *)v5 + 11);
    if ( (v21 & 2) != 0 )
    {
      v12 = (v21 & 1) == 0;
      v22 = (_SLIST_HEADER *)&NetBufferList[1].NetBufferListInfo[4];
      if ( v12 )
        v22 = (_SLIST_HEADER *)&NetBufferList[1];
      NetBufferList->Context = (_NET_BUFFER_LIST_CONTEXT *)v22;
      v22->Alignment = 0;
      NetBufferList->Context->Size = *((_WORD *)v5 + 21);
      NetBufferList->Context->Offset = *((_WORD *)v5 + 21);
    }
    memset(&NetBufferList[1], 0, 0xB0u);
    NetBufferList[1].NdisReserved[1] = v5;
    NetBufferList->Link.Region = (unsigned __int64)&NetBufferList[1];
    if ( *(int *)ndisNblTrackerMode >= 3 )
      ndisNblTrackerRecordEventInternal(NetBufferList, 0, 3u, 0, 0);
  }
  else
  {
    NetBufferList = 0;
  }
  if ( !NetBufferList )
    return NetBufferList;
  FirstNetBuffer = NetBufferList->FirstNetBuffer;
  v6 = *(_DWORD **)(((unsigned __int64)&v65 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40);
  v7 = *(_DWORD *)(((unsigned __int64)&v65 & 0xFFFFFFFFFFFFFFC0uLL) + 8);
LABEL_33:
  v24 = v7;
  v25 = v8->FirstNetBuffer;
  v26 = v24 & 2;
  for ( *(_DWORD *)v4 = v26; v25; v26 = *(_DWORD *)v4 )
  {
    DataOffset = v25->DataOffset;
    MdlChain = v25->MdlChain;
    if ( v26 )
    {
      FirstNetBuffer->MdlChain = MdlChain;
      FirstNetBuffer->Link.Region = v25->Link.Region;
      FirstNetBuffer->DataLength = v25->DataLength;
      FirstNetBuffer->DataOffset = DataOffset;
      FirstNetBuffer->CurrentMdlOffset = v25->CurrentMdlOffset;
    }
    else if ( MdlChain )
    {
      while ( 1 )
      {
        ByteCount = MdlChain->ByteCount;
        if ( DataOffset < ByteCount )
          break;
        MdlChain = MdlChain->Next;
        DataOffset -= ByteCount;
        if ( !MdlChain )
          goto LABEL_45;
      }
      DataLength = v25->DataLength;
      v31 = ByteCount - DataOffset;
      v32 = DataLength;
      v33 = 0;
      if ( v31 < DataLength )
        v32 = v31;
      if ( v32 )
      {
        v34 = (char *)MdlChain->StartVa + MdlChain->ByteOffset + DataOffset;
        *(_QWORD *)(((unsigned __int64)&v65 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10) = v34;
        Mdl = IoAllocateMdl(v34, v32, 0, 0, 0);
        v33 = Mdl;
        if ( !Mdl )
          goto LABEL_47;
        IoBuildPartialMdl(MdlChain, Mdl, *(PVOID *)(((unsigned __int64)&v65 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10), v32);
        v33->Next = 0;
      }
      FirstNetBuffer->Link.Region = (unsigned __int64)v33;
      FirstNetBuffer->MdlChain = v33;
      FirstNetBuffer->DataLength = v25->DataLength;
      FirstNetBuffer->CurrentMdlOffset = 0;
      FirstNetBuffer->DataOffset = 0;
      v36 = DataLength - v32;
      if ( v36 )
      {
        while ( 1 )
        {
          MdlChain = MdlChain->Next;
          if ( !MdlChain )
            break;
          v59 = MdlChain->ByteCount;
          v60 = v36;
          v61 = (char *)MdlChain->StartVa + MdlChain->ByteOffset;
          *(_QWORD *)(((unsigned __int64)&v65 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20) = v61;
          if ( v59 <= v36 )
            v60 = v59;
          *(_DWORD *)(((unsigned __int64)&v65 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10) = v60;
          v62 = IoAllocateMdl(v61, v60, 0, 0, 0);
          v63 = v62;
          if ( !v62 )
            goto LABEL_47;
          IoBuildPartialMdl(
            MdlChain,
            v62,
            *(PVOID *)(((unsigned __int64)&v65 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20),
            *(_DWORD *)(((unsigned __int64)&v65 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10));
          v33->Next = v63;
          v63->Next = 0;
          v36 -= *(_DWORD *)(((unsigned __int64)&v65 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10);
          if ( !v36 )
            break;
          v33 = v63;
        }
      }
      v6 = *(_DWORD **)(((unsigned __int64)&v65 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40);
    }
LABEL_45:
    v25 = (_NET_BUFFER *)v25->Link.Alignment;
    if ( !v25 )
      break;
    NetBuffer = NdisAllocateNetBuffer(v6, 0, 0, 0);
    if ( !NetBuffer )
    {
LABEL_47:
      v7 = *(_DWORD *)(((unsigned __int64)&v65 & 0xFFFFFFFFFFFFFFC0uLL) + 8);
      goto LABEL_48;
    }
    FirstNetBuffer->Link.Alignment = (unsigned __int64)NetBuffer;
    FirstNetBuffer = NetBuffer;
  }
  v38 = *(_QWORD **)(((unsigned __int64)&v65 & 0xFFFFFFFFFFFFFFC0uLL) + 0x80);
  NetBufferList->SourceHandle = (void *)v38[15];
  NetBufferList->NetBufferListInfo[16] = (void *)v38[34];
  if ( (v38[28] & 0xFFFFFFFFFFFFFFFCuLL) != 0 && (v38[28] & 1) == 0 )
  {
    LOBYTE(Flags) = 1;
    WfpNblInfoClone(v38, NetBufferList, 0, 0, Flags);
  }
  if ( byte_14011D730 )
  {
    NetBufferList->NetBufferListInfo[13] = (void *)v38[31];
  }
  else if ( Microsoft_Windows_Networking_CorrelationEnabled )
  {
    v44 = v38[31] & 0x7FFFFFFFFFFFFFFFLL;
    *(_QWORD *)(((unsigned __int64)&v65 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28) = 0;
    *(_QWORD *)(((unsigned __int64)&v65 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20) = v44;
    v45 = (__int64)NetBufferList->NetBufferListInfo[13] & 0x7FFFFFFFFFFFFFFFLL;
    *(_OWORD *)(((unsigned __int64)&v65 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40) = *(_OWORD *)(((unsigned __int64)&v65
                                                                                      & 0xFFFFFFFFFFFFFFC0uLL)
                                                                                     + 0x20);
    *(_QWORD *)(((unsigned __int64)&v65 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20) = v45;
    LODWORD(v45) = Microsoft_Windows_Networking_CorrelationEnabled;
    *(_QWORD *)(((unsigned __int64)&v65 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28) = 0;
    *(_OWORD *)(((unsigned __int64)&v65 & 0xFFFFFFFFFFFFFFC0uLL) + 0x80) = *(_OWORD *)(((unsigned __int64)&v65
                                                                                      & 0xFFFFFFFFFFFFFFC0uLL)
                                                                                     + 0x20);
    if ( (_DWORD)v45 )
    {
      v46 = (const GUID *)(v4 + 128);
      v47 = Microsoft_Windows_Networking_CorrelationHandle;
      v48 = (const EVENT_DESCRIPTOR *)(v4 + 32);
      *(_QWORD *)(((unsigned __int64)&v65 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20) = ActivityTransfer;
      *(_QWORD *)(((unsigned __int64)&v65 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28) = 0x8000000000000001uLL;
      v49 = Microsoft_Windows_Networking_CorrelationTraceActivityPayload;
      *(_DWORD *)(((unsigned __int64)&v65 & 0xFFFFFFFFFFFFFFC0uLL) + 8) = 1;
      if ( v49 )
      {
        *(_QWORD *)(((unsigned __int64)&v65 & 0xFFFFFFFFFFFFFFC0uLL) + 0x98) = 16;
        *(_QWORD *)(((unsigned __int64)&v65 & 0xFFFFFFFFFFFFFFC0uLL) + 0x90) = &Microsoft_Windows_Networking_ProviderId;
        *(_QWORD *)(((unsigned __int64)&v65 & 0xFFFFFFFFFFFFFFC0uLL) + 0xA0) = ((unsigned __int64)&v65
                                                                              & 0xFFFFFFFFFFFFFFC0uLL)
                                                                             + 8;
        *(_QWORD *)(((unsigned __int64)&v65 & 0xFFFFFFFFFFFFFFC0uLL) + 0xA8) = 4;
        EtwWriteTransfer(v47, v48, (LPCGUID)(v4 + 64), v46, 2u, (PEVENT_DATA_DESCRIPTOR)(v4 + 144));
      }
      else
      {
        EtwWriteTransfer(v47, v48, (LPCGUID)(v4 + 64), v46, 0, 0);
      }
    }
  }
  if ( *(int *)ndisNblTrackerMode >= 3 )
    ndisNblTrackerRecordEventInternal(NetBufferList, 0, 5u, v38, 0);
  return NetBufferList;
}

```

## disassembly

```asm
0x140031090  mov     [rsp-8+arg_18], rbx
0x140031095  push    rbp
0x140031096  push    rsi
0x140031097  push    rdi
0x140031098  push    r12
0x14003109a  push    r13
0x14003109c  push    r14
0x14003109e  push    r15
0x1400310a0  sub     rsp, 140h
0x1400310a7  lea     rbp, [rsp+80h]
0x1400310af  and     rbp, 0FFFFFFFFFFFFFFC0h
0x1400310b3  mov     rax, cs:__security_cookie
0x1400310ba  xor     rax, rsp
0x1400310bd  mov     [rbp+0F0h+var_40], rax
0x1400310c4  test    rdx, rdx
0x1400310c7  mov     [rbp+0F0h+FreeCloneFlags], r9d
0x1400310cb  mov     rsi, rdx
0x1400310ce  mov     qword ptr [rbp+0F0h+RelatedActivityId.Data1], rcx
0x1400310d5  cmovz   rsi, cs:?ndisNetBufferListPool@@3PEAXEA; void * ndisNetBufferListPool
0x1400310dd  mov     r13, r8
0x1400310e0  test    r8, r8
0x1400310e3  mov     edi, r9d
0x1400310e6  mov     r12, rcx
0x1400310e9  cmovz   r13, cs:?ndisNetBufferPool@@3PEAXEA; void * ndisNetBufferPool
0x1400310f1  mov     eax, [rsi+2Ch]
0x1400310f4  mov     [rbp+0F0h+PoolHandle], r13
0x1400310f8  test    al, 1
0x1400310fa  jz      loc_1400315AA
0x140031100  test    al, 4
0x140031102  jnz     loc_140031964
0x140031108  mov     eax, [rsi+4]
0x14003110b  xor     r15d, r15d
0x14003110e  test    al, 1
0x140031110  jnz     loc_140031597
0x140031116  mov     edi, gs:1A4h
0x14003111e  mov     r13d, 1
0x140031124  cmp     cs:?ndisMaxNumberOfProcessors@@3KA, r13d; ulong ndisMaxNumberOfProcessors
0x14003112b  mov     dword ptr [rbp+0F0h+VirtualAddress], edi
0x14003112e  jz      loc_1400317AA
0x140031134  mov     ebx, edi
0x140031136  shl     rbx, 8
0x14003113a  lea     rdi, [rbx+180h]
0x140031141  add     rdi, rsi
0x140031144  cmp     [rdi+0D8h], r15b
0x14003114b  jnz     loc_1400311DB
0x140031151  lea     rcx, [rdi+0D0h]; SpinLock
0x140031158  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003115f  nop     dword ptr [rax+rax+00h]
0x140031164  movzx   r12d, al
0x140031168  cmp     [rdi+0D8h], r15b
0x14003116f  jnz     short loc_1400311C4
0x140031171  mov     [rsp+170h+Depth], 400h; Depth
0x140031178  mov     r8, rdi
0x14003117b  sub     r8, rbx
0x14003117e  mov     r9d, 200h; PoolType
0x140031184  mov     edx, [r8-0D4h]
0x14003118b  mov     ecx, [r8-0D8h]
0x140031192  mov     r8, [r8-0C8h]; Free
0x140031199  mov     [rsp+170h+Tag], ecx; Tag
0x14003119d  mov     rcx, rdi; Lookaside
0x1400311a0  mov     [rsp+170h+Size], rdx; Size
0x1400311a5  lea     rdx, ndisAllocateFromNPagedPool; Allocate
0x1400311ac  mov     [rsp+170h+Flags], r15d; Flags
0x1400311b1  call    cs:__imp_ExInitializeLookasideListEx
0x1400311b8  nop     dword ptr [rax+rax+00h]
0x1400311bd  mov     [rdi+0D8h], r13b
0x1400311c4  movzx   edx, r12b; NewIrql
0x1400311c8  lea     rcx, [rdi+0D0h]; SpinLock
0x1400311cf  call    cs:__imp_KeReleaseSpinLock
0x1400311d6  nop     dword ptr [rax+rax+00h]
0x1400311db  lock inc dword ptr [rdi+14h]
0x1400311df  mov     rcx, [rdi+0C0h]; ListHead
0x1400311e6  call    cs:__imp_ExpInterlockedPopEntrySList
0x1400311ed  nop     dword ptr [rax+rax+00h]
0x1400311f2  mov     rbx, rax
0x1400311f5  test    rax, rax
0x1400311f8  jz      loc_140031908
0x1400311fe  mov     r12, qword ptr [rbp+0F0h+RelatedActivityId.Data1]
0x140031205  test    rbx, rbx
0x140031208  jz      loc_140031935
0x14003120e  movzx   edi, word ptr [rbx+3Ah]
0x140031212  xor     edx, edx; Val
0x140031214  mov     r8d, r13d
0x140031217  mov     rcx, rbx; void *
0x14003121a  xor     r8, 1
0x14003121e  lea     r8, ds:170h[r8*8]; Size
0x140031226  call    memset
0x14003122b  mov     [rbx+20h], rsi
0x14003122f  mov     dword ptr [rbx+88h], 100h
0x140031239  test    r13d, r13d
0x14003123c  jz      short loc_140031242
0x14003123e  mov     [rbx+3Ah], di
0x140031242  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x140031248  test    eax, eax
0x14003124a  jz      short loc_14003129A
0x14003124c  mov     rax, [rbx+0F8h]
0x140031253  test    rax, rax
0x140031256  jnz     loc_1400314E7
0x14003125c  mov     rdx, rbx
0x14003125f  mov     ecx, 1
0x140031264  lock xadd cs:dword_14011AE28, ecx
0x14003126c  lea     eax, [rcx+1]
0x14003126f  cmp     eax, ecx
0x140031271  jb      loc_140031952
0x140031277  mov     rax, [rdx+0F8h]
0x14003127e  test    rax, rax
0x140031281  jnz     loc_140031534
0x140031287  mov     eax, ecx
0x140031289  inc     ecx
0x14003128b  mov     [rdx+0F8h], rax
0x140031292  mov     rdx, [rdx]
0x140031295  test    rdx, rdx
0x140031298  jnz     short loc_140031277
0x14003129a  movzx   eax, byte ptr [rsi+28h]
0x14003129e  mov     [rbx+0C8h], al
0x1400312a4  mov     eax, [rsi+2Ch]
0x1400312a7  test    al, 2
0x1400312a9  jz      short loc_1400312DC
0x1400312ab  test    al, 1
0x1400312ad  lea     rax, [rbx+230h]
0x1400312b4  jnz     short loc_1400312BD
0x1400312b6  lea     rax, [rbx+180h]
0x1400312bd  mov     [rbx+10h], rax
0x1400312c1  mov     [rax], r15
0x1400312c4  mov     rcx, [rbx+10h]
0x1400312c8  movzx   eax, word ptr [rsi+2Ah]
0x1400312cc  mov     [rcx+8], ax
0x1400312d0  mov     rcx, [rbx+10h]
0x1400312d4  movzx   eax, word ptr [rsi+2Ah]
0x1400312d8  mov     [rcx+0Ah], ax
0x1400312dc  lea     rdi, [rbx+180h]
0x1400312e3  xor     edx, edx; Val
0x1400312e5  mov     rcx, rdi; void *
0x1400312e8  mov     r8d, 0B0h; Size
0x1400312ee  call    memset
0x1400312f3  mov     [rdi+38h], rsi
0x1400312f7  mov     [rbx+8], rdi
0x1400312fb  cmp     cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A, 3; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x140031302  jge     loc_14003157A
0x140031308  xor     r8d, r8d
0x14003130b  test    rbx, rbx
0x14003130e  jz      loc_1400314B9
0x140031314  mov     r14, [rbx+8]
0x140031318  mov     r13, [rbp+0F0h+PoolHandle]
0x14003131c  mov     edi, [rbp+0F0h+FreeCloneFlags]
0x14003131f  mov     eax, edi
0x140031321  mov     rdi, [r12+8]
0x140031326  and     eax, 2
0x140031329  mov     [rbp+0F0h+var_F0], eax
0x14003132c  test    rdi, rdi
0x14003132f  jz      loc_14003142F
0x140031335  mov     edx, [rdi+28h]
0x140031338  mov     r15, [rdi+20h]
0x14003133c  test    eax, eax
0x14003133e  jnz     loc_14003153F
0x140031344  test    r15, r15
0x140031347  jz      loc_1400313ED
0x14003134d  mov     eax, [r15+28h]
0x140031351  cmp     edx, eax
0x140031353  jnb     loc_14003163F
0x140031359  mov     r12d, [rdi+18h]
0x14003135d  sub     eax, edx
0x14003135f  cmp     eax, r12d
0x140031362  mov     r13d, r12d
0x140031365  mov     rsi, r8
0x140031368  cmovb   r13d, eax
0x14003136c  test    r13d, r13d
0x14003136f  jz      short loc_1400313C6
0x140031371  mov     ecx, [r15+2Ch]
0x140031375  xor     r9d, r9d; ChargeQuota
0x140031378  add     rcx, [r15+20h]
0x14003137c  mov     eax, edx
0x14003137e  mov     edx, r13d; Length
0x140031381  add     rax, rcx
0x140031384  mov     qword ptr [rsp+170h+Flags], r8; Irp
0x140031389  mov     rcx, rax; VirtualAddress
0x14003138c  mov     [rbp+0F0h+VirtualAddress], rax
0x140031390  xor     r8d, r8d; SecondaryBuffer
0x140031393  call    cs:__imp_IoAllocateMdl
0x14003139a  nop     dword ptr [rax+rax+00h]
0x14003139f  mov     rsi, rax
0x1400313a2  test    rax, rax
0x1400313a5  jz      short loc_14003140E
0x1400313a7  mov     r8, [rbp+0F0h+VirtualAddress]; VirtualAddress
0x1400313ab  mov     r9d, r13d; Length
0x1400313ae  mov     rdx, rax; TargetMdl
0x1400313b1  mov     rcx, r15; SourceMdl
0x1400313b4  call    cs:__imp_IoBuildPartialMdl
0x1400313bb  nop     dword ptr [rax+rax+00h]
0x1400313c0  xor     r8d, r8d
0x1400313c3  mov     [rsi], r8
0x1400313c6  mov     [r14+8], rsi
0x1400313ca  mov     [r14+20h], rsi
0x1400313ce  mov     eax, [rdi+18h]
0x1400313d1  mov     [r14+18h], eax
0x1400313d5  mov     [r14+10h], r8d
0x1400313d9  mov     [r14+28h], r8d
0x1400313dd  sub     r12d, r13d
0x1400313e0  jnz     loc_140031882
0x1400313e6  mov     r13, [rbp+0F0h+PoolHandle]
0x1400313ea  mov     eax, [rbp+0F0h+var_F0]
0x1400313ed  mov     rdi, [rdi]
0x1400313f0  test    rdi, rdi
0x1400313f3  jz      short loc_14003142F
0x1400313f5  xor     r9d, r9d; DataLength
0x1400313f8  xor     r8d, r8d; DataOffset
0x1400313fb  xor     edx, edx; MdlChain
0x1400313fd  mov     rcx, r13; PoolHandle
0x140031400  call    NdisAllocateNetBuffer
0x140031405  test    rax, rax
0x140031408  jnz     loc_14003199D
0x14003140e  test    rbx, rbx
0x140031411  jz      loc_1400314B9
0x140031417  mov     edi, [rbp+0F0h+FreeCloneFlags]
0x14003141a  xor     r15d, r15d
0x14003141d  mov     edx, edi; FreeCloneFlags
0x14003141f  mov     rcx, rbx; CloneNetBufferList
0x140031422  call    NdisFreeCloneNetBufferList
0x140031427  mov     rbx, r15
0x14003142a  jmp     loc_1400314B9
0x14003142f  test    rbx, rbx
0x140031432  jz      loc_1400314B9
0x140031438  mov     r12, qword ptr [rbp+0F0h+RelatedActivityId.Data1]
0x14003143f  mov     rax, [r12+78h]
0x140031444  mov     [rbx+78h], rax
0x140031448  mov     rax, [r12+110h]
0x140031450  mov     [rbx+110h], rax
0x140031457  mov     rax, [r12+0E0h]
0x14003145f  test    rax, 0FFFFFFFFFFFFFFFCh
0x140031465  setnz   cl
0x140031468  test    al, 1
0x14003146a  setz    al
0x14003146d  test    al, cl
0x14003146f  jz      short loc_140031491
0x140031471  xor     r9d, r9d
0x140031474  mov     byte ptr [rsp+170h+Flags], 1
0x140031479  xor     r8d, r8d
0x14003147c  mov     rdx, rbx
0x14003147f  mov     rcx, r12
0x140031482  call    cs:__imp_WfpNblInfoClone
0x140031489  nop     dword ptr [rax+rax+00h]
0x14003148e  xor     r8d, r8d
0x140031491  cmp     cs:byte_14011D730, 0
0x140031498  jnz     loc_140031566
0x14003149e  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1400314a4  test    eax, eax
0x1400314a6  jnz     loc_140031652
0x1400314ac  cmp     cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A, 3; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x1400314b3  jge     loc_1400319AE
0x1400314b9  mov     rax, rbx
0x1400314bc  mov     rcx, [rbp+0F0h+var_40]
0x1400314c3  xor     rcx, rsp; StackCookie
0x1400314c6  call    __security_check_cookie
0x1400314cb  mov     rbx, [rsp+170h+arg_18]
0x1400314d3  add     rsp, 140h
0x1400314da  pop     r15
0x1400314dc  pop     r14
0x1400314de  pop     r13
0x1400314e0  pop     r12
0x1400314e2  pop     rdi
0x1400314e3  pop     rsi
0x1400314e4  pop     rbp
0x1400314e5  retn
0x1400314e7  js      loc_14003125C
0x1400314ed  mov     rcx, [rbx]
0x1400314f0  test    rcx, rcx
0x1400314f3  jz      loc_14003129A
0x1400314f9  mov     rax, [rcx+0F8h]
0x140031500  test    rax, rax
0x140031503  jnz     short loc_140031562
0x140031505  mov     edx, 1
0x14003150a  lock xadd cs:dword_14011AE28, edx
0x140031512  lea     eax, [rdx+1]
0x140031515  cmp     eax, edx
0x140031517  jb      loc_140031940
0x14003151d  mov     eax, edx
0x14003151f  mov     [rcx+0F8h], rax
0x140031526  mov     rcx, [rcx]
0x140031529  test    rcx, rcx
0x14003152c  jz      loc_14003129A
0x140031532  jmp     short loc_1400314F9
0x140031534  js      loc_140031287
0x14003153a  jmp     loc_140031292
0x14003153f  mov     [r14+20h], r15
0x140031543  mov     rax, [rdi+8]
0x140031547  mov     [r14+8], rax
0x14003154b  mov     eax, [rdi+18h]
0x14003154e  mov     [r14+18h], eax
0x140031552  mov     [r14+28h], edx
0x140031556  mov     eax, [rdi+10h]
0x140031559  mov     [r14+10h], eax
0x14003155d  jmp     loc_1400313EA
0x140031562  jns     short loc_140031526
0x140031564  jmp     short loc_140031505
0x140031566  mov     rax, [r12+0F8h]
0x14003156e  mov     [rbx+0F8h], rax
0x140031575  jmp     loc_1400314AC
0x14003157a  xor     r9d, r9d; void *
0x14003157d  mov     [rsp+170h+Flags], r15d; unsigned int
0x140031582  xor     edx, edx; struct NDIS_NBL_TRACKER_HANDLE__ *
  ... truncated ...
```
