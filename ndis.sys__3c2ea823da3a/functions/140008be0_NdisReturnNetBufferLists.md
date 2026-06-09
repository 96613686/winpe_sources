# NdisReturnNetBufferLists

- ea: `0x140008be0`
- end: `0x1400096b0`
- name: `NdisReturnNetBufferLists`
- size: `2768`
- prototype: `void __stdcall(NDIS_HANDLE NdisBindingHandle, PNET_BUFFER_LIST NetBufferLists, ULONG ReturnFlags)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x140008be0`
- `0x140009e70`
- `0x14000a5a0`
- `0x14000dd50`
- `0x14000de20`
- `0x140030450`
- `0x14009f8e4`
- `0x1400e6240`
- `0x1400e65c0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x140008c8b`
- `ntoskrnl!KfRaiseIrql` at `0x140009355`
- `ntoskrnl!KfRaiseIrql` at `0x140008c8b`
- `ntoskrnl!KfRaiseIrql` at `0x140009355`
- `ntoskrnl!KeLowerIrql` at `0x140008d4f`
- `ntoskrnl!KeLowerIrql` at `0x14000903f`
- `ntoskrnl!KeLowerIrql` at `0x14000942c`
- `ntoskrnl!KeLowerIrql` at `0x140008d4f`
- `ntoskrnl!KeLowerIrql` at `0x14000903f`
- `ntoskrnl!KeLowerIrql` at `0x14000942c`
- `ntoskrnl!KeGetCurrentIrql` at `0x140008f22`
- `ntoskrnl!KeGetCurrentIrql` at `0x140008f22`
- `ntoskrnl!MmUnmapLockedPages` at `0x140009647`
- `ntoskrnl!MmUnmapLockedPages` at `0x140009647`
- `ntoskrnl!MmBadPointer` at `0x1400e7352`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140008e76`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140008e76`
- `ntoskrnl!IoGetStackLimits` at `0x140008f9b`
- `ntoskrnl!IoGetStackLimits` at `0x140008f9b`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1400091af`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1400091af`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000947d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000947d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009227`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009227`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400091d7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400091d7`

## pseudocode

```c
void __stdcall NdisReturnNetBufferLists(
        NDIS_HANDLE NdisBindingHandle,
        PNET_BUFFER_LIST NetBufferLists,
        ULONG ReturnFlags)
{
  __int64 v3; // rsi
  PNET_BUFFER_LIST v4; // rbx
  __int64 v5; // r9
  NDIS_HANDLE v6; // r14
  __int64 v7; // r13
  int v8; // ebp
  int v9; // r12d
  unsigned int Number; // r10d
  KIRQL v11; // r11
  KIRQL v12; // al
  _SLIST_HEADER *v13; // rax
  unsigned int v14; // r8d
  PNET_BUFFER_LIST Alignment; // r15
  int v16; // r12d
  PNET_BUFFER_LIST k; // rcx
  struct _NET_BUFFER_LIST *v18; // rcx
  _QWORD *p_Alignment; // r14
  struct _NET_BUFFER_LIST *v20; // r15
  _NET_BUFFER *FirstNetBuffer; // rax
  struct _NPAGED_LOOKASIDE_LIST *v22; // rbp
  _MDL *CurrentMdl; // r13
  unsigned int v24; // r13d
  __int64 v25; // r14
  void (__fastcall *v26)(struct _NET_BUFFER_LIST *, PNET_BUFFER_LIST, __int64, __int64); // r15
  struct _NET_BUFFER_LIST *v27; // r12
  __int64 v28; // rcx
  unsigned __int64 v29; // rdx
  __int64 v30; // r8
  unsigned __int64 v31; // rax
  unsigned int v32; // ecx
  PNET_BUFFER_LIST *p_Parameter; // rsi
  PNET_BUFFER_LIST v34; // rdx
  __int64 v35; // rbp
  __int64 v36; // rax
  PNET_BUFFER_LIST v37; // rdx
  struct _VF_NDIS_DISPATCH_TABLE *v38; // rax
  __int64 v39; // r8
  struct _NET_BUFFER_LIST *v40; // rbx
  int v41; // ecx
  KIRQL v42; // r14
  PNET_BUFFER_LIST *v43; // rcx
  _QWORD *m; // rdx
  struct _VF_NDIS_DISPATCH_TABLE *v45; // rax
  __int64 ChildRefCount; // r8
  struct _NET_BUFFER_LIST *Scratch; // rbx
  PNET_BUFFER_LIST v48; // rdx
  struct _VF_NDIS_DISPATCH_TABLE *v49; // rax
  __int64 v50; // r8
  struct _NET_BUFFER_LIST *v51; // rbx
  int v52; // eax
  struct _NET_BUFFER_LIST *j; // r15
  unsigned int v54; // eax
  __int64 v55; // r8
  unsigned __int64 v56; // rax
  _SLIST_HEADER *v57; // rax
  char v58; // r13
  unsigned int Flags; // eax
  unsigned int v60; // eax
  _NET_BUFFER_LIST_CONTEXT *i; // r12
  int v62; // [rsp+30h] [rbp-A8h]
  char v63; // [rsp+34h] [rbp-A4h]
  PNET_BUFFER_LIST v64; // [rsp+38h] [rbp-A0h]
  unsigned int v65; // [rsp+38h] [rbp-A0h]
  unsigned int v66; // [rsp+38h] [rbp-A0h]
  __int64 v67; // [rsp+40h] [rbp-98h]
  __int64 v68; // [rsp+48h] [rbp-90h]
  unsigned __int64 LowLimit; // [rsp+50h] [rbp-88h] BYREF
  unsigned __int64 HighLimit; // [rsp+58h] [rbp-80h] BYREF
  int v71; // [rsp+60h] [rbp-78h]
  PNET_BUFFER_LIST Parameter; // [rsp+68h] [rbp-70h] BYREF
  PNET_BUFFER_LIST v73; // [rsp+70h] [rbp-68h]
  void (__fastcall *v74)(struct _NET_BUFFER_LIST *, PNET_BUFFER_LIST, __int64, __int64); // [rsp+78h] [rbp-60h]
  PNET_BUFFER_LIST v75; // [rsp+80h] [rbp-58h]
  __int64 v76; // [rsp+88h] [rbp-50h]
  ULONG v77; // [rsp+90h] [rbp-48h]
  int v78; // [rsp+94h] [rbp-44h]
  _UNKNOWN *retaddr; // [rsp+D8h] [rbp+0h] BYREF
  KIRQL v81; // [rsp+E0h] [rbp+8h]
  KIRQL v83; // [rsp+F8h] [rbp+20h]

  v3 = *((_QWORD *)NdisBindingHandle + 2);
  v4 = NetBufferLists;
  v5 = ReturnFlags;
  v6 = NdisBindingHandle;
  if ( *(_DWORD *)(v3 + 48) || (v7 = 0, v68 = 0, v8 = 0, LOBYTE(v9) = 0, v63 = 0, *(_DWORD *)(v3 + 80)) )
  {
    v7 = *(_QWORD *)(v3 + 40);
    v8 = *(_DWORD *)(v3 + 48);
    v9 = *(_DWORD *)(v3 + 80);
    v63 = v9;
    v68 = v7;
    if ( !v7 )
    {
      v7 = *(_QWORD *)(v3 + 40);
      v68 = v7;
    }
  }
  if ( (*((_DWORD *)NdisBindingHandle + 56) & 1) != 0 )
  {
    ndisNblVerifyRxCompletion(NetBufferLists, ReturnFlags, (const struct _NDIS_OBJECT_HEADER *)NdisBindingHandle);
    Alignment = v4;
    if ( v4 )
    {
      v58 = byte_14011CDF0;
      do
      {
        Flags = Alignment->Flags;
        Alignment->Scratch = MmBadPointer;
        Alignment->ChildRefCount = -892679478;
        if ( v58 )
        {
          v58 = 0;
          v60 = Flags & 0xFFF0FFFF;
        }
        else
        {
          v58 = 1;
          v60 = Flags | 0xF0000;
        }
        byte_14011CDF0 = v58;
        Alignment->Flags = v60;
        for ( i = Alignment->Context; i; i = i->Next )
          memset(i->ContextData, 202, i->Offset);
        Alignment = (PNET_BUFFER_LIST)Alignment->Link.Alignment;
      }
      while ( Alignment );
      LOBYTE(v9) = v63;
      v7 = v68;
    }
    v5 = ReturnFlags;
  }
  if ( ndisNblContextVerifierMode && ndisNblContextVerifierMode != 3 )
  {
    switch ( *(_BYTE *)v6 )
    {
      case 5:
        v52 = *((_DWORD *)v6 + 14) >> 10;
        break;
      case 0x11:
        v52 = *((_DWORD *)v6 + 922) >> 12;
        break;
      case 0x12:
        v52 = *((_DWORD *)v6 + 56) >> 31;
        goto LABEL_106;
      default:
        goto LABEL_5;
    }
    LOBYTE(v52) = v52 & 1;
LABEL_106:
    if ( (_BYTE)v52 )
    {
      for ( j = v4; j; j = (struct _NET_BUFFER_LIST *)j->Link.Alignment )
      {
        if ( *(NDIS_HANDLE *)&j->Context->ContextData[j->Context->Offset] != v6 )
          NblContextVerifierBugcheckContextCorruption(j, v4, v6);
        NdisFreeNetBufferListContext(j, 8u);
      }
      v5 = ReturnFlags;
    }
  }
LABEL_5:
  Number = -1;
  v11 = 2;
  v62 = -1;
  v83 = 2;
  if ( (v8 & 0x180028) != 0 || (v9 & 0x10) != 0 )
  {
    if ( (v5 & 1) == 0 )
    {
      v12 = KfRaiseIrql(2u);
      Number = -1;
      v11 = v12;
      v83 = v12;
    }
    if ( (v8 & 8) != 0 )
    {
      Number = KeGetPcr()->Prcb.Number;
      v62 = Number;
      ++*(_QWORD *)(ndisPcwOffsetToPerCpuData + v7 + ndisPcwPerCpuDataStride * Number + 24);
    }
    if ( !v11 && (v8 & 0x80000) != 0 )
    {
      if ( Number == -1 )
      {
        Number = KeGetPcr()->Prcb.Number;
        v62 = Number;
      }
      ++*(_QWORD *)(ndisPcwOffsetToPerCpuData + v7 + ndisPcwPerCpuDataStride * Number + 216);
    }
    if ( (v8 & 0x100020) != 0 )
    {
      v13 = (_SLIST_HEADER *)v4;
      v14 = 0;
      if ( v4 )
      {
        do
        {
          v13 = (_SLIST_HEADER *)v13->Alignment;
          ++v14;
        }
        while ( v13 );
      }
      if ( (v8 & 0x20) != 0 )
      {
        if ( Number == -1 )
        {
          Number = KeGetPcr()->Prcb.Number;
          v62 = Number;
        }
        *(_QWORD *)(v7 + ndisPcwPerCpuDataStride * Number + ndisPcwOffsetToPerCpuData + 40) += v14;
      }
      if ( !v11 && (v8 & 0x100000) != 0 )
      {
        if ( Number == -1 )
        {
          Number = KeGetPcr()->Prcb.Number;
          v62 = Number;
        }
        *(_QWORD *)(v7 + ndisPcwPerCpuDataStride * Number + ndisPcwOffsetToPerCpuData + 224) += v14;
      }
    }
    v71 = v9 & 0x10;
    if ( (v9 & 0x10) != 0 )
    {
      if ( Number == -1 )
      {
        Number = KeGetPcr()->Prcb.Number;
        v62 = Number;
      }
      *(_QWORD *)(ndisPcwOffsetToPerCpuData + v7 + ndisPcwPerCpuDataStride * Number + 336) = __rdtsc();
    }
    else if ( v11 != 2 )
    {
      KeLowerIrql(v11);
    }
  }
  if ( *(_DWORD *)(v3 + 48) || (LOBYTE(v16) = 0, v67 = 0, *(_DWORD *)(v3 + 80)) )
  {
    v16 = *(_DWORD *)(v3 + 80);
    v67 = *(_QWORD *)(v3 + 40);
    if ( !v67 )
      v67 = *(_QWORD *)(v3 + 40);
  }
  for ( k = v4; k; k = (PNET_BUFFER_LIST)k->Link.Alignment )
    k->Flags = k->Flags & 0xFFFFFFF4 | 8;
  if ( (Microsoft_Windows_Networking_CorrelationEnabled || byte_14011D730) && v4 )
  {
    v57 = (_SLIST_HEADER *)v4;
    if ( byte_14011D730 )
    {
      do
      {
        v57[15].Region = 0;
        v57 = (_SLIST_HEADER *)v57->Alignment;
      }
      while ( v57 );
    }
    else
    {
      do
      {
        v57[15].Region |= 0x8000000000000000uLL;
        v57 = (_SLIST_HEADER *)v57->Alignment;
      }
      while ( v57 );
    }
  }
  if ( *(_DWORD *)(v3 + 3224) )
  {
    v18 = 0;
    v64 = 0;
    if ( v4 )
    {
      p_Alignment = 0;
      do
      {
        v20 = (struct _NET_BUFFER_LIST *)v4->Link.Alignment;
        v4->Link.Alignment = 0;
        if ( v4->NdisPoolHandle == PoolHandle )
        {
          _InterlockedDecrement((volatile signed __int32 *)(v3 + 3224));
          FirstNetBuffer = v4->FirstNetBuffer;
          v22 = (struct _NPAGED_LOOKASIDE_LIST *)v4->MiniportReserved[1];
          CurrentMdl = FirstNetBuffer->CurrentMdl;
          if ( (CurrentMdl->MdlFlags & 0x20) != 0 )
            MmUnmapLockedPages(CurrentMdl->MappedSystemVa, FirstNetBuffer->CurrentMdl);
          if ( v22 )
            ExFreeToNPagedLookasideList(v22, CurrentMdl);
          else
            ExFreePoolWithTag(CurrentMdl, 0);
          NdisFreeNetBufferList(v4);
          v18 = v64;
        }
        else
        {
          if ( v18 )
          {
            *p_Alignment = v4;
          }
          else
          {
            v18 = v4;
            v64 = v4;
          }
          p_Alignment = &v4->Link.Alignment;
        }
        v4 = v20;
      }
      while ( v20 );
      v6 = NdisBindingHandle;
    }
    v4 = v18;
  }
  if ( v4 )
  {
    v24 = -1;
    v81 = 2;
    if ( *(_DWORD *)ndisNblTrackerMode )
      ndisNblTrackerTransferOwnershipInternal(
        v4,
        *((struct NDIS_NBL_TRACKER_HANDLE__ **)v6 + 73),
        *(struct NDIS_NBL_TRACKER_HANDLE__ **)(v3 + 2536),
        NdisNblTrackerEvent_ProtocolReturned,
        ReturnFlags & 1);
    v71 = v16 & 0x20;
    if ( (v16 & 0x20) != 0 )
    {
      if ( (ReturnFlags & 1) == 0 )
        v81 = KfRaiseIrql(2u);
      v24 = KeGetPcr()->Prcb.Number;
      *(_QWORD *)(ndisPcwOffsetToPerCpuData + ndisPcwPerCpuDataStride * v24 + v67 + 344) = __rdtsc();
    }
    v25 = *(_QWORD *)(v3 + 2544);
    v26 = *(void (__fastcall **)(struct _NET_BUFFER_LIST *, PNET_BUFFER_LIST, __int64, __int64))(v3 + 2640);
    v27 = *(struct _NET_BUFFER_LIST **)(v3 + 2528);
    if ( *(_BYTE *)v25 == 17 )
      goto LABEL_57;
    if ( (ReturnFlags & 1) != 0 || KeGetCurrentIrql() == 2 )
    {
      v32 = KeGetPcr()->Prcb.Number;
      p_Parameter = &Parameter;
      v66 = v32;
      v74 = 0;
      Parameter = v4;
      v73 = v4;
      v4->Scratch = 0;
      v4->ChildRefCount = ReturnFlags;
      while ( *(_BYTE *)v25 == 5 )
      {
        v34 = *p_Parameter;
        if ( !*p_Parameter )
          break;
        v35 = *(_QWORD *)(v25 + 424) + 96LL * v32;
        if ( *(_BYTE *)(v35 + 88) )
        {
          *p_Parameter = 0;
          do
          {
            v45 = ndisVerifierNdisDispatch;
            ChildRefCount = (unsigned int)v34->ChildRefCount;
            Scratch = (struct _NET_BUFFER_LIST *)v34->Scratch;
            v34->ChildRefCount = 0;
            if ( v45 && *(_BYTE *)v25 == 5 && (v5 = *(_QWORD *)(v25 + 776)) != 0 )
              (*((void (__fastcall **)(struct _NET_BUFFER_LIST *, PNET_BUFFER_LIST, __int64))v45 + 17))(
                v27,
                v34,
                ChildRefCount);
            else
              v26(v27, v34, ChildRefCount, v5);
            v34 = Scratch;
          }
          while ( Scratch );
          break;
        }
        *(_BYTE *)(v35 + 88) = 1;
        v36 = v25;
        v37 = *p_Parameter;
        *p_Parameter = 0;
        if ( v37 )
        {
          do
          {
            v38 = ndisVerifierNdisDispatch;
            v39 = (unsigned int)v37->ChildRefCount;
            v40 = (struct _NET_BUFFER_LIST *)v37->Scratch;
            v37->ChildRefCount = 0;
            if ( v38 && *(_BYTE *)v25 == 5 && (v5 = *(_QWORD *)(v25 + 776)) != 0 )
              (*((void (__fastcall **)(struct _NET_BUFFER_LIST *, PNET_BUFFER_LIST, __int64))v38 + 17))(v27, v37, v39);
            else
              v26(v27, v37, v39, v5);
            v37 = v40;
          }
          while ( v40 );
          v36 = v25;
        }
        v32 = v66;
        p_Parameter = (PNET_BUFFER_LIST *)(v35 + 72);
        *(_BYTE *)(v35 + 88) = 0;
        v25 = *(_QWORD *)(v25 + 552);
        v26 = *(void (__fastcall **)(struct _NET_BUFFER_LIST *, PNET_BUFFER_LIST, __int64, __int64))(v36 + 528);
        v27 = *(struct _NET_BUFFER_LIST **)(v36 + 536);
      }
      v48 = *p_Parameter;
      if ( *p_Parameter )
      {
        *p_Parameter = 0;
        do
        {
          v49 = ndisVerifierNdisDispatch;
          v50 = (unsigned int)v48->ChildRefCount;
          v51 = (struct _NET_BUFFER_LIST *)v48->Scratch;
          v48->ChildRefCount = 0;
          if ( v49 && *(_BYTE *)v25 == 5 && (v5 = *(_QWORD *)(v25 + 776)) != 0 )
            (*((void (__fastcall **)(struct _NET_BUFFER_LIST *, PNET_BUFFER_LIST, __int64))v49 + 17))(v27, v48, v50);
          else
            v26(v27, v48, v50, v5);
          v48 = v51;
        }
        while ( v51 );
      }
      goto LABEL_58;
    }
    if ( *(_BYTE *)v3 != 5 )
      goto LABEL_57;
    v65 = Size;
    LowLimit = 0;
    HighLimit = 0;
    v28 = KeGetPcr()->Prcb.Number << 12;
    v29 = *(_QWORD *)(v28 + qword_14011CF78);
    LowLimit = v29;
    HighLimit = *(_QWORD *)(v28 + qword_14011CF70);
    if ( (unsigned __int64)&retaddr >= HighLimit || v29 > (unsigned __int64)&retaddr )
    {
      IoGetStackLimits(&LowLimit, &HighLimit);
      v29 = LowLimit;
    }
    if ( (unsigned __int64)&retaddr - v29 < v65 )
    {
      v41 = 24576;
      v77 = ReturnFlags;
      v78 = 0;
      Parameter = (PNET_BUFFER_LIST)v25;
      v73 = v27;
      v74 = v26;
      v75 = v4;
      v76 = 0;
      if ( (unsigned int)Size > 0x6000 )
        v41 = Size;
      if ( KeExpandKernelStackAndCalloutEx(
             ndisDataPathExpandStackCallback<3,void (void *,_NET_BUFFER_LIST *,unsigned long)>,
             &Parameter,
             v41,
             0,
             0) < 0 )
      {
        if ( *(_DWORD *)ndisNblTrackerMode )
          ndisNblTrackerTransferOwnershipInternal(
            v4,
            *(struct NDIS_NBL_TRACKER_HANDLE__ **)(v3 + 648),
            (struct NDIS_NBL_TRACKER_HANDLE__ *)0xA0,
            (enum _NDIS_NBL_TRACKER_OWNERSHIP_EVENT)1,
            0);
        v42 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 144));
        *(_QWORD *)(v3 + 152) = KeGetCurrentThread();
        v43 = (PNET_BUFFER_LIST *)(v3 + 280);
        for ( m = *(_QWORD **)(v3 + 280); m; m = (_QWORD *)*m )
          v43 = (PNET_BUFFER_LIST *)m;
        *v43 = v4;
        ndisQueueStackExpansionFallbackWorkItem((struct _NDIS_FILTER_BLOCK *)v3);
        *(_QWORD *)(v3 + 152) = 0;
        KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 144), v42);
      }
      goto LABEL_58;
    }
    if ( ndisVerifierNdisDispatch && *(_BYTE *)v25 == 5 && (v5 = *(_QWORD *)(v25 + 776)) != 0 )
      (*((void (__fastcall **)(struct _NET_BUFFER_LIST *, PNET_BUFFER_LIST, _QWORD))ndisVerifierNdisDispatch + 17))(
        v27,
        v4,
        ReturnFlags);
    else
LABEL_57:
      v26(v27, v4, ReturnFlags, v5);
LABEL_58:
    if ( v71 )
    {
      if ( v24 == -1 )
        v24 = KeGetPcr()->Prcb.Number;
      v30 = v67 + ndisPcwPerCpuDataStride * v24 + ndisPcwOffsetToPerCpuData;
      v31 = __rdtsc();
      *(_QWORD *)(v30 + 144) += (((unsigned __int64)HIDWORD(v31) << 32) | (unsigned int)v31) - *(_QWORD *)(v30 + 344);
      *(_QWORD *)(v30 + 344) = 0;
      if ( v81 != 2 )
        KeLowerIrql(v81);
    }
  }
  if ( (v63 & 0x10) != 0 )
  {
    v54 = v62;
    if ( v62 == -1 )
      v54 = KeGetPcr()->Prcb.Number;
    v55 = v68 + ndisPcwPerCpuDataStride * v54 + ndisPcwOffsetToPerCpuData;
    v56 = __rdtsc();
    *(_QWORD *)(v55 + 136) += (((unsigned __int64)HIDWORD(v56) << 32) | (unsigned int)v56) - *(_QWORD *)(v55 + 336);
    *(_QWORD *)(v55 + 336) = 0;
    if ( v83 != 2 )
      KeLowerIrql(v83);
  }
}

```

## disassembly

```asm
0x140008be0  mov     [rsp+arg_10], r8d
0x140008be5  mov     [rsp+arg_0], rcx
0x140008bea  push    rbx
0x140008beb  push    rbp
0x140008bec  push    rsi
0x140008bed  push    rdi
0x140008bee  push    r12
0x140008bf0  push    r13
0x140008bf2  push    r14
0x140008bf4  sub     rsp, 0A0h
0x140008bfb  mov     rsi, [rcx+10h]
0x140008bff  mov     rbx, rdx
0x140008c02  xor     edi, edi
0x140008c04  mov     r9d, r8d
0x140008c07  mov     r14, rcx
0x140008c0a  mov     edx, [rsi+30h]
0x140008c0d  test    edx, edx
0x140008c0f  jnz     loc_140009300
0x140008c15  mov     r13d, edi
0x140008c18  mov     [rsp+0D8h+var_90], rdi
0x140008c1d  mov     ebp, edi
0x140008c1f  mov     r12d, edi
0x140008c22  mov     [rsp+0D8h+var_A4], edi
0x140008c26  cmp     [rsi+50h], edi
0x140008c29  jnz     loc_140009300
0x140008c2f  mov     eax, [rcx+0E0h]
0x140008c35  mov     [rsp+0D8h+arg_8], r15
0x140008c3d  test    al, 1
0x140008c3f  jnz     loc_140008D5D
0x140008c45  mov     eax, cs:?ndisNblContextVerifierMode@@3W4NDIS_NBL_CONTEXT_VERIFIER_MODE@@A; NDIS_NBL_CONTEXT_VERIFIER_MODE ndisNblContextVerifierMode
0x140008c4b  test    eax, eax
0x140008c4d  jnz     loc_1400092C9
0x140008c53  test    ebp, 180028h
0x140008c59  mov     r10d, 0FFFFFFFFh
0x140008c5f  mov     r11b, 2
0x140008c62  mov     [rsp+0D8h+var_A8], r10d
0x140008c67  setz    cl
0x140008c6a  mov     [rsp+0D8h+arg_18], r11b
0x140008c72  test    r12b, 10h
0x140008c76  setz    al
0x140008c79  test    al, cl
0x140008c7b  jnz     loc_140008DBD
0x140008c81  test    r9b, 1
0x140008c85  jnz     short loc_140008CA7
0x140008c87  movzx   ecx, r11b; NewIrql
0x140008c8b  call    cs:__imp_KfRaiseIrql
0x140008c92  nop     dword ptr [rax+rax+00h]
0x140008c97  mov     r10d, [rsp+0D8h+var_A8]
0x140008c9c  movzx   r11d, al
0x140008ca0  mov     [rsp+0D8h+arg_18], al
0x140008ca7  test    bpl, 8
0x140008cab  jz      short loc_140008CD4
0x140008cad  mov     r10d, gs:1A4h
0x140008cb6  mov     ecx, r10d
0x140008cb9  imul    ecx, cs:?ndisPcwPerCpuDataStride@@3KA; ulong ndisPcwPerCpuDataStride
0x140008cc0  mov     r8d, cs:?ndisPcwOffsetToPerCpuData@@3KA; ulong ndisPcwOffsetToPerCpuData
0x140008cc7  mov     [rsp+0D8h+var_A8], r10d
0x140008ccc  add     rcx, r13
0x140008ccf  inc     qword ptr [r8+rcx+18h]
0x140008cd4  test    r11b, r11b
0x140008cd7  jz      loc_14000948E
0x140008cdd  test    ebp, 100020h
0x140008ce3  jz      short loc_140008D39
0x140008ce5  mov     rax, rbx
0x140008ce8  mov     r8d, edi
0x140008ceb  test    rbx, rbx
0x140008cee  jz      short loc_140008CFB
0x140008cf0  mov     rax, [rax]
0x140008cf3  inc     r8d
0x140008cf6  test    rax, rax
0x140008cf9  jnz     short loc_140008CF0
0x140008cfb  test    bpl, 20h
0x140008cff  jz      short loc_140008D30
0x140008d01  cmp     r10d, 0FFFFFFFFh
0x140008d05  jnz     short loc_140008D15
0x140008d07  mov     r10d, gs:1A4h
0x140008d10  mov     [rsp+0D8h+var_A8], r10d
0x140008d15  mov     edx, cs:?ndisPcwOffsetToPerCpuData@@3KA; ulong ndisPcwOffsetToPerCpuData
0x140008d1b  mov     ecx, r10d
0x140008d1e  imul    ecx, cs:?ndisPcwPerCpuDataStride@@3KA; ulong ndisPcwPerCpuDataStride
0x140008d25  mov     eax, r8d
0x140008d28  add     rcx, r13
0x140008d2b  add     [rcx+rdx+28h], rax
0x140008d30  test    r11b, r11b
0x140008d33  jz      loc_1400094CC
0x140008d39  mov     eax, r12d
0x140008d3c  and     eax, 10h
0x140008d3f  mov     [rsp+0D8h+var_78], eax
0x140008d43  jnz     short loc_140008D84
0x140008d45  cmp     r11b, 2
0x140008d49  jz      short loc_140008DBD
0x140008d4b  movzx   ecx, r11b; NewIrql
0x140008d4f  call    cs:__imp_KeLowerIrql
0x140008d56  nop     dword ptr [rax+rax+00h]
0x140008d5b  jmp     short loc_140008DBD
0x140008d5d  mov     r8, r14; struct _NDIS_OBJECT_HEADER *
0x140008d60  mov     edx, r9d; unsigned int
0x140008d63  mov     rcx, rbx; struct _NET_BUFFER_LIST *
0x140008d66  call    ?ndisNblVerifyRxCompletion@@YAXPEBU_NET_BUFFER_LIST@@KPEBU_NDIS_OBJECT_HEADER@@@Z; ndisNblVerifyRxCompletion(_NET_BUFFER_LIST const *,ulong,_NDIS_OBJECT_HEADER const *)
0x140008d6b  mov     r15, rbx
0x140008d6e  test    rbx, rbx
0x140008d71  jnz     loc_14000960B
0x140008d77  mov     r9d, [rsp+0D8h+arg_10]
0x140008d7f  jmp     loc_140008C45
0x140008d84  cmp     r10d, 0FFFFFFFFh
0x140008d88  jnz     short loc_140008D98
0x140008d8a  mov     r10d, gs:1A4h
0x140008d93  mov     [rsp+0D8h+var_A8], r10d
0x140008d98  rdtsc
0x140008d9a  mov     r8d, cs:?ndisPcwOffsetToPerCpuData@@3KA; ulong ndisPcwOffsetToPerCpuData
0x140008da1  mov     ecx, r10d
0x140008da4  imul    ecx, cs:?ndisPcwPerCpuDataStride@@3KA; ulong ndisPcwPerCpuDataStride
0x140008dab  shl     rdx, 20h
0x140008daf  or      rax, rdx
0x140008db2  add     rcx, r13
0x140008db5  mov     [r8+rcx+150h], rax
0x140008dbd  cmp     dword ptr [rsi+30h], 0
0x140008dc1  jnz     loc_14000932B
0x140008dc7  cmp     dword ptr [rsi+50h], 0
0x140008dcb  mov     r12d, edi
0x140008dce  mov     [rsp+0D8h+var_98], rdi
0x140008dd3  jnz     loc_14000932B
0x140008dd9  mov     rcx, rbx
0x140008ddc  test    rbx, rbx
0x140008ddf  jz      short loc_140008DFB
0x140008de1  mov     eax, [rcx+88h]
0x140008de7  and     eax, 0FFFFFFFCh
0x140008dea  or      eax, 8
0x140008ded  mov     [rcx+88h], eax
0x140008df3  mov     rcx, [rcx]
0x140008df6  test    rcx, rcx
0x140008df9  jnz     short loc_140008DE1
0x140008dfb  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x140008e01  test    eax, eax
0x140008e03  jnz     loc_14000943D
0x140008e09  cmp     cs:byte_14011D730, al
0x140008e0f  jnz     loc_14000943D
0x140008e15  cmp     dword ptr [rsi+0C98h], 0
0x140008e1c  jz      loc_140008EA2
0x140008e22  mov     rcx, rdi
0x140008e25  mov     [rsp+0D8h+var_A0], rcx
0x140008e2a  test    rbx, rbx
0x140008e2d  jz      short loc_140008E9F
0x140008e2f  mov     r14, rdi
0x140008e32  mov     r15, [rbx]
0x140008e35  mov     [rbx], rdi
0x140008e38  mov     rax, cs:PoolHandle
0x140008e3f  cmp     [rbx+20h], rax
0x140008e43  jnz     loc_140009658
0x140008e49  lock dec dword ptr [rsi+0C98h]
0x140008e50  mov     rax, [rbx+8]
0x140008e54  mov     rbp, [rbx+68h]
0x140008e58  mov     r13, [rax+8]
0x140008e5c  test    byte ptr [r13+0Ah], 20h
0x140008e61  jnz     loc_140009640
0x140008e67  test    rbp, rbp
0x140008e6a  jz      loc_140009478
0x140008e70  mov     rdx, r13; Entry
0x140008e73  mov     rcx, rbp; Lookaside
0x140008e76  call    cs:__imp_ExFreeToNPagedLookasideList
0x140008e7d  nop     dword ptr [rax+rax+00h]
0x140008e82  mov     rcx, rbx; NetBufferList
0x140008e85  call    NdisFreeNetBufferList
0x140008e8a  mov     rcx, [rsp+0D8h+var_A0]
0x140008e8f  mov     rbx, r15
0x140008e92  test    r15, r15
0x140008e95  jnz     short loc_140008E32
0x140008e97  mov     r14, [rsp+0D8h+arg_0]
0x140008e9f  mov     rbx, rcx
0x140008ea2  test    rbx, rbx
0x140008ea5  jz      loc_14000904B
0x140008eab  mov     ebp, [rsp+0D8h+arg_10]
0x140008eb2  mov     r13d, 0FFFFFFFFh
0x140008eb8  and     ebp, 1
0x140008ebb  mov     byte ptr [rsp+0D8h+arg_0], 2
0x140008ec3  cmp     cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A, 0; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x140008eca  jz      short loc_140008EEC
0x140008ecc  mov     r8, [rsi+9E8h]; struct NDIS_NBL_TRACKER_HANDLE__ *
0x140008ed3  mov     r9d, 87h; enum _NDIS_NBL_TRACKER_OWNERSHIP_EVENT
0x140008ed9  mov     rdx, [r14+248h]; struct NDIS_NBL_TRACKER_HANDLE__ *
0x140008ee0  mov     rcx, rbx; struct _NET_BUFFER_LIST *
0x140008ee3  mov     dword ptr [rsp+0D8h+Context], ebp; unsigned int
0x140008ee7  call    ?ndisNblTrackerTransferOwnershipInternal@@YAXPEAU_NET_BUFFER_LIST@@PEAUNDIS_NBL_TRACKER_HANDLE__@@1W4_NDIS_NBL_TRACKER_OWNERSHIP_EVENT@@K@Z; ndisNblTrackerTransferOwnershipInternal(_NET_BUFFER_LIST *,NDIS_NBL_TRACKER_HANDLE__ *,NDIS_NBL_TRACKER_HANDLE__ *,_NDIS_NBL_TRACKER_OWNERSHIP_EVENT,ulong)
0x140008eec  and     r12d, 20h
0x140008ef0  mov     [rsp+0D8h+var_78], r12d
0x140008ef5  jnz     loc_14000934F
0x140008efb  mov     r14, [rsi+9F0h]
0x140008f02  mov     r15, [rsi+0A50h]
0x140008f09  mov     r12, [rsi+9E0h]
0x140008f10  cmp     byte ptr [r14], 11h
0x140008f14  jz      loc_140008FCC
0x140008f1a  test    ebp, ebp
0x140008f1c  jnz     loc_140009074
0x140008f22  call    cs:__imp_KeGetCurrentIrql
0x140008f29  nop     dword ptr [rax+rax+00h]
0x140008f2e  cmp     al, 2
0x140008f30  jz      loc_140009074
0x140008f36  cmp     byte ptr [rsi], 5
0x140008f39  jnz     loc_140008FCC
0x140008f3f  mov     eax, cs:Size
0x140008f45  lea     rbp, [rsp+0D8h]
0x140008f4d  mov     dword ptr [rsp+0D8h+var_A0], eax
0x140008f51  mov     [rsp+0D8h+LowLimit], rdi
0x140008f56  mov     [rsp+0D8h+HighLimit], rdi
0x140008f5b  mov     eax, gs:1A4h
0x140008f63  shl     eax, 0Ch
0x140008f66  mov     ecx, eax
0x140008f68  mov     rax, cs:qword_14011CF78
0x140008f6f  mov     rdx, [rcx+rax]
0x140008f73  mov     rax, cs:qword_14011CF70
0x140008f7a  mov     [rsp+0D8h+LowLimit], rdx
0x140008f7f  mov     r8, [rcx+rax]
0x140008f83  mov     [rsp+0D8h+HighLimit], r8
0x140008f88  cmp     rbp, r8
0x140008f8b  jb      loc_14000946A
0x140008f91  lea     rdx, [rsp+0D8h+HighLimit]; HighLimit
0x140008f96  lea     rcx, [rsp+0D8h+LowLimit]; LowLimit
0x140008f9b  call    cs:__imp_IoGetStackLimits
0x140008fa2  nop     dword ptr [rax+rax+00h]
0x140008fa7  mov     rdx, [rsp+0D8h+LowLimit]
0x140008fac  mov     eax, dword ptr [rsp+0D8h+var_A0]
0x140008fb0  sub     rbp, rdx
0x140008fb3  cmp     rbp, rax
0x140008fb6  jb      loc_14000914D
0x140008fbc  mov     rax, cs:?ndisVerifierNdisDispatch@@3PEAU_VF_NDIS_DISPATCH_TABLE@@EA; _VF_NDIS_DISPATCH_TABLE * ndisVerifierNdisDispatch
0x140008fc3  test    rax, rax
0x140008fc6  jnz     loc_1400095CD
0x140008fcc  mov     r8d, [rsp+0D8h+arg_10]
0x140008fd4  mov     rdx, rbx
0x140008fd7  mov     rcx, r12
0x140008fda  mov     rax, r15
0x140008fdd  call    _guard_dispatch_icall
0x140008fe2  cmp     [rsp+0D8h+var_78], 0
0x140008fe7  jz      short loc_14000904B
0x140008fe9  cmp     r13d, 0FFFFFFFFh
0x140008fed  jnz     short loc_140008FF8
0x140008fef  mov     r13d, gs:1A4h
0x140008ff8  imul    r13d, cs:?ndisPcwPerCpuDataStride@@3KA; ulong ndisPcwPerCpuDataStride
0x140009000  mov     r8d, cs:?ndisPcwOffsetToPerCpuData@@3KA; ulong ndisPcwOffsetToPerCpuData
0x140009007  mov     eax, r13d
0x14000900a  add     rax, [rsp+0D8h+var_98]
0x14000900f  add     r8, rax
0x140009012  rdtsc
0x140009014  shl     rdx, 20h
0x140009018  or      rax, rdx
0x14000901b  sub     rax, [r8+158h]
0x140009022  add     [r8+90h], rax
0x140009029  movzx   eax, byte ptr [rsp+0D8h+arg_0]
0x140009031  mov     [r8+158h], rdi
0x140009038  cmp     al, 2
0x14000903a  jz      short loc_14000904B
0x14000903c  movzx   ecx, al; NewIrql
0x14000903f  call    cs:__imp_KeLowerIrql
0x140009046  nop     dword ptr [rax+rax+00h]
0x14000904b  test    [rsp+0D8h+var_A4], 10h
0x140009053  jnz     loc_1400093D6
0x140009059  mov     r15, [rsp+0D8h+arg_8]
0x140009061  add     rsp, 0A0h
0x140009068  pop     r14
0x14000906a  pop     r13
0x14000906c  pop     r12
0x14000906e  pop     rdi
0x14000906f  pop     rsi
0x140009070  pop     rbp
0x140009071  pop     rbx
0x140009072  retn
0x140009074  mov     ecx, gs:1A4h
0x14000907c  lea     rsi, [rsp+0D8h+Parameter]
0x140009081  mov     eax, [rsp+0D8h+arg_10]
0x140009088  mov     dword ptr [rsp+0D8h+var_A0], ecx
0x14000908c  mov     [rsp+0D8h+var_60], rdi
0x140009091  mov     [rsp+0D8h+Parameter], rbx
0x140009096  mov     [rsp+0D8h+var_68], rbx
0x14000909b  mov     [rbx+70h], rdi
0x14000909f  mov     [rbx+84h], eax
0x1400090a5  cmp     byte ptr [r14], 5
0x1400090a9  jnz     loc_140009274
0x1400090af  mov     rdx, [rsi]
0x1400090b2  test    rdx, rdx
0x1400090b5  jz      loc_140009274
0x1400090bb  mov     eax, ecx
0x1400090bd  lea     rbp, [rax+rax*2]
0x1400090c1  shl     rbp, 5
0x1400090c5  add     rbp, [r14+1A8h]
0x1400090cc  cmp     byte ptr [rbp+58h], 0
0x1400090d0  jnz     loc_140009238
0x1400090d6  mov     byte ptr [rbp+58h], 1
0x1400090da  mov     rax, r14
0x1400090dd  mov     rdx, [rsi]
0x1400090e0  mov     [rsi], rdi
0x1400090e3  test    rdx, rdx
0x1400090e6  jz      short loc_140009127
0x1400090e8  nop     dword ptr [rax+rax+00000000h]
0x1400090f0  mov     rax, cs:?ndisVerifierNdisDispatch@@3PEAU_VF_NDIS_DISPATCH_TABLE@@EA; _VF_NDIS_DISPATCH_TABLE * ndisVerifierNdisDispatch
0x1400090f7  mov     r8d, [rdx+84h]
0x1400090fe  mov     rbx, [rdx+70h]
0x140009102  mov     [rdx+84h], edi
0x140009108  test    rax, rax
0x14000910b  jnz     loc_140009534
0x140009111  mov     rcx, r12
  ... truncated ...
```
