# ndisSortNetBufferLists(_NDIS_NBL_RCV_TRACKER *)

- ea: `0x14002d620`
- end: `0x14002e4e8`
- name: `?ndisSortNetBufferLists@@YAXPEAU_NDIS_NBL_RCV_TRACKER@@@Z`
- size: `3784`
- prototype: `void __fastcall(struct _NDIS_NBL_RCV_TRACKER *)`
- caller_count: `5`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14002afd0`
- `0x14002e4f0`
- `0x14002e8a0`
- `0x14002f560`
- `0x14002fab0`

## callees

- `0x1400110b0`
- `0x140011190`
- `0x1400231d0`
- `0x140023900`
- `0x140025d30`
- `0x1400260b0`
- `0x14002d620`
- `0x14003a0e0`
- `0x1400eb460`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x14002ddc4`
- `ntoskrnl!KeLowerIrql` at `0x14002ddc4`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002dbed`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002dc9f`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002e173`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002dbed`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002dc9f`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002e173`
- `ntoskrnl!MmMapLockedPages` at `0x14002e3f1`
- `ntoskrnl!MmMapLockedPages` at `0x14002e3f1`
- `ntoskrnl!MmUnmapLockedPages` at `0x14002e452`
- `ntoskrnl!MmUnmapLockedPages` at `0x14002e452`
- `ntoskrnl!KfRaiseIrql` at `0x14002e0a0`
- `ntoskrnl!KfRaiseIrql` at `0x14002e0a0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002da13`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002da13`
- `ntoskrnl!IoGetStackLimits` at `0x14002dd1d`
- `ntoskrnl!IoGetStackLimits` at `0x14002dd1d`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14002df1f`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14002df1f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e151`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e151`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002df9f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002df9f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002df4c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002df4c`

## pseudocode

```c
void __fastcall ndisSortNetBufferLists(struct _NDIS_NBL_RCV_TRACKER *a1)
{
  __int64 v1; // rax
  unsigned __int64 v3; // rdi
  _QWORD *v4; // r9
  struct _NDIS_FILTER_BLOCK *v5; // r13
  char *v6; // r8
  unsigned __int64 v7; // r12
  struct _NET_BUFFER_LIST *v8; // r14
  char v9; // r11
  unsigned __int16 v10; // r15
  unsigned __int64 v11; // r13
  unsigned __int64 v12; // r10
  __int64 v13; // rax
  __int64 v14; // rcx
  unsigned int v15; // esi
  __int64 v16; // rbp
  _BYTE *v17; // rax
  char *v18; // rdx
  unsigned __int16 v19; // ax
  char v20; // cl
  __int64 v21; // r9
  unsigned int v22; // edx
  unsigned int i; // r8d
  char *v24; // rcx
  __int64 v25; // rcx
  bool v26; // zf
  _DWORD *v27; // rcx
  int v28; // ebp
  int v29; // esi
  struct _NET_BUFFER_LIST *Alignment; // rcx
  struct _NET_BUFFER_LIST *v31; // rbx
  struct _NET_BUFFER_LIST *v32; // rdi
  _NET_BUFFER *FirstNetBuffer; // rax
  struct _NPAGED_LOOKASIDE_LIST *v34; // r14
  _MDL *CurrentMdl; // r15
  unsigned int v36; // ebp
  unsigned int Number; // r15d
  KIRQL v38; // r13
  __int64 v39; // rdi
  __int64 v40; // r9
  unsigned __int64 v41; // rbx
  unsigned __int64 v42; // r13
  unsigned __int64 v43; // rbx
  unsigned __int64 v44; // rdi
  char *SourceHandle; // rcx
  int v46; // edx
  __int64 v47; // rax
  char v48; // r8
  unsigned __int64 v49; // r9
  unsigned __int64 v50; // rdx
  __int64 v51; // rcx
  KIRQL v52; // al
  unsigned __int64 v53; // rdx
  __int64 v54; // rcx
  unsigned __int64 v55; // r14
  void (__fastcall *v56)(unsigned __int64, unsigned __int64, __int64); // rdi
  unsigned __int64 v57; // rsi
  unsigned __int64 v58; // r12
  __int64 v59; // rcx
  unsigned __int64 v60; // rdx
  __int64 v61; // r8
  unsigned __int64 v62; // rax
  unsigned __int64 *p_LowLimit; // rbx
  unsigned __int64 v64; // rdx
  __int64 v65; // rbp
  unsigned __int64 v66; // r13
  unsigned __int64 v67; // rdx
  struct _VF_NDIS_DISPATCH_TABLE *v68; // rax
  __int64 v69; // r8
  unsigned __int64 v70; // rbx
  int v71; // ecx
  KIRQL v72; // di
  _NET_BUFFER_LIST **p_ReceivedNblsToComplete; // rcx
  _SLIST_HEADER *j; // rdx
  struct _VF_NDIS_DISPATCH_TABLE *v75; // rax
  __int64 v76; // r8
  unsigned __int64 v77; // rbp
  unsigned __int64 v78; // rdx
  struct _VF_NDIS_DISPATCH_TABLE *v79; // rax
  __int64 v80; // r8
  unsigned __int64 v81; // rbx
  _SLIST_HEADER *v82; // rax
  KIRQL CurrentIrql; // al
  unsigned __int64 v84; // rdx
  unsigned __int64 v85; // rdi
  __int64 v86; // rdx
  PNET_BUFFER_LIST NetBufferList; // [rsp+40h] [rbp-98h]
  int v88; // [rsp+48h] [rbp-90h]
  __int64 v89; // [rsp+48h] [rbp-90h]
  unsigned __int64 v90; // [rsp+48h] [rbp-90h]
  Rtl::KString *value; // [rsp+50h] [rbp-88h]
  struct _NDIS_FILTER_BLOCK *v92; // [rsp+58h] [rbp-80h]
  unsigned __int64 LowLimit; // [rsp+60h] [rbp-78h] BYREF
  unsigned __int64 HighLimit; // [rsp+68h] [rbp-70h] BYREF
  void (__fastcall *v95)(unsigned __int64, unsigned __int64, __int64); // [rsp+70h] [rbp-68h]
  PNET_BUFFER_LIST v96; // [rsp+78h] [rbp-60h]
  __int64 v97; // [rsp+80h] [rbp-58h]
  int v98; // [rsp+88h] [rbp-50h]
  int v99; // [rsp+8Ch] [rbp-4Ch]
  _UNKNOWN *retaddr; // [rsp+D8h] [rbp+0h] BYREF
  char v101; // [rsp+E0h] [rbp+8h]
  char v102; // [rsp+E0h] [rbp+8h]
  KIRQL v103; // [rsp+E0h] [rbp+8h]
  unsigned __int16 v104; // [rsp+E8h] [rbp+10h]
  char v105; // [rsp+E8h] [rbp+10h]
  int v106; // [rsp+E8h] [rbp+10h]
  unsigned __int16 v107; // [rsp+F0h] [rbp+18h]
  unsigned int v108; // [rsp+F8h] [rbp+20h]
  __int64 v109; // [rsp+F8h] [rbp+20h]

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
  v4 = 0;
  v5 = *(struct _NDIS_FILTER_BLOCK **)a1;
  LODWORD(v6) = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v101 = 0;
  v10 = 0;
  v92 = *(struct _NDIS_FILTER_BLOCK **)a1;
  LowLimit = 0;
  NetBufferList = 0;
  v88 = 0;
  v108 = 0;
  *((_QWORD *)a1 + 7) = 0;
  *((_QWORD *)a1 + 8) = 0;
  *((_QWORD *)a1 + 9) = 0;
  *((_WORD *)a1 + 24) = 0;
  *((_DWORD *)a1 + 20) = 0;
  while ( v3 )
  {
    v11 = *(_QWORD *)v3;
    *(_QWORD *)v3 = 0;
    v12 = v3;
    if ( *(_DWORD *)(*(_QWORD *)a1 + 464LL) )
    {
      v19 = *(_WORD *)(v3 + 200);
      goto LABEL_15;
    }
    v13 = *(_QWORD *)(v3 + 8);
    v14 = *(_QWORD *)(v13 + 8);
    if ( v14
      && (v15 = *(_DWORD *)(v14 + 40), v15 >= 0xE)
      && (v16 = *(unsigned int *)(v13 + 16), v15 > (unsigned int)v16) )
    {
      if ( v15 - (unsigned int)v16 < 0xE )
        goto LABEL_187;
      if ( (*(_BYTE *)(v14 + 10) & 5) != 0 )
      {
        v17 = *(_BYTE **)(v14 + 24);
      }
      else
      {
        v17 = MmMapLockedPages((PMDL)v14, 0);
        v9 = v101;
        v12 = v3;
        LODWORD(v6) = v108;
        v4 = (_QWORD *)LowLimit;
      }
      v18 = &v17[v16];
      HIBYTE(v107) = v17[v16 + 12];
      LOBYTE(v107) = v17[v16 + 13];
      v104 = *(_WORD *)&v17[v16 + 12];
      if ( v107 > 0x600u )
      {
        if ( v107 != 0x8100 )
          goto LABEL_14;
        if ( v15 >= 0x12 && v15 - (unsigned int)v16 >= 0x12 )
        {
          v104 = *((_WORD *)v18 + 8);
LABEL_14:
          v19 = v104;
LABEL_15:
          v20 = 1;
          v10 = v19;
          goto LABEL_16;
        }
LABEL_187:
        v8 = NetBufferList;
        goto LABEL_179;
      }
      v20 = 0;
      if ( v18[14] == -86 && v18[15] == -86 && v18[16] == 3 )
      {
        v19 = *((_WORD *)v18 + 10);
        goto LABEL_15;
      }
LABEL_16:
      if ( !v20 )
        goto LABEL_118;
      v21 = *((_QWORD *)a1 + 1);
      if ( v88 != v10 )
      {
        v22 = 0;
        v88 = v10;
        while ( v22 < *(_DWORD *)(v21 + 24) )
        {
          if ( v10 == *(_WORD *)(v21 + 16LL * v22 + 32) )
          {
            v9 = 1;
            v108 = v22;
            v101 = 1;
            goto LABEL_23;
          }
          ++v22;
        }
        v9 = 0;
        v101 = 0;
        v108 = 0;
LABEL_118:
        i = 0;
        goto LABEL_27;
      }
      v22 = (unsigned int)v6;
      if ( v9 != 1 )
        goto LABEL_118;
LABEL_23:
      if ( *((_WORD *)a1 + 20 * (unsigned int)v7 + 24) == v10 )
      {
        i = v7;
      }
      else
      {
        for ( i = 1; ; ++i )
        {
          if ( i > *((_DWORD *)a1 + 172) )
          {
            ++*((_DWORD *)a1 + 172);
            v12 = v3;
            v7 = *((unsigned int *)a1 + 172);
            i = *((_DWORD *)a1 + 172);
            v24 = (char *)a1 + 40 * v7;
            *((_WORD *)v24 + 24) = v10;
            *((_QWORD *)v24 + 7) = *(_QWORD *)(v21 + 16 * (v22 + 1LL) + 24);
            *((_QWORD *)v24 + 8) = 0;
            goto LABEL_27;
          }
          if ( *((_WORD *)a1 + 20 * i + 24) == v10 )
            break;
        }
        v7 = i;
        v12 = v3;
      }
LABEL_27:
      v25 = i + 2LL;
      v26 = *((_QWORD *)a1 + 5 * i + 8) == 0;
      v6 = (char *)a1 + 40 * i;
      v27 = (_DWORD *)((char *)a1 + 40 * v25);
      if ( v26 )
      {
        *((_QWORD *)v6 + 8) = v3;
        if ( (*((_DWORD *)a1 + 4) & 0x100) != 0 )
        {
          v8 = NetBufferList;
          *((_QWORD *)v6 + 9) = 0;
          *(_QWORD *)v3 = v11;
          v5 = v92;
          *v27 = *((_DWORD *)a1 + 11);
          break;
        }
        *v27 = 1;
      }
      else
      {
        **((_QWORD **)v6 + 9) = v3;
        ++*v27;
      }
      v8 = NetBufferList;
      v3 = v11;
      v5 = v92;
      *((_QWORD *)v6 + 9) = v12;
      LODWORD(v6) = v108;
      v4 = (_QWORD *)LowLimit;
    }
    else
    {
LABEL_179:
      if ( v4 )
      {
        *v4 = v3;
      }
      else
      {
        v8 = (struct _NET_BUFFER_LIST *)v3;
        NetBufferList = (PNET_BUFFER_LIST)v3;
      }
      v3 = v11;
      LowLimit = v12;
      v5 = v92;
      v4 = (_QWORD *)v12;
      ++v92[2].Characteristics.CancelSendNetBufferListsHandler;
    }
  }
  if ( !v8 )
    return;
  if ( byte_140123720 && ((__int64)v5[4].PendingOidRequest & 2) != 0 )
    PktMonClientNblDropNdis((_DWORD)v5 + 5816, (_DWORD)v8, (_DWORD)v6, 1, -1073676273, -536866810);
  v28 = *((_DWORD *)a1 + 4);
  if ( (v28 & 2) != 0 )
    return;
  if ( LODWORD(v5->FilterFriendlyName) || (LOBYTE(v29) = 0, value = 0, *(_DWORD *)&v5->Ref.ReferenceCount) )
  {
    v29 = *(_DWORD *)&v5->Ref.ReferenceCount;
    value = v5->FilterInstanceName.__ptr_.__value_;
    if ( !value )
      value = v5->FilterInstanceName.__ptr_.__value_;
  }
  Alignment = v8;
  do
  {
    Alignment->Flags = Alignment->Flags & 0xFFFFFFF4 | 8;
    Alignment = (struct _NET_BUFFER_LIST *)Alignment->Link.Alignment;
  }
  while ( Alignment );
  if ( Microsoft_Windows_Networking_CorrelationEnabled
    || byte_140123720 != (_BYTE)Microsoft_Windows_Networking_CorrelationEnabled )
  {
    v82 = (_SLIST_HEADER *)v8;
    if ( byte_140123720 )
    {
      do
      {
        v82[15].Region = 0;
        v82 = (_SLIST_HEADER *)v82->Alignment;
      }
      while ( v82 );
    }
    else
    {
      do
      {
        v82[15].Region |= 0x8000000000000000uLL;
        v82 = (_SLIST_HEADER *)v82->Alignment;
      }
      while ( v82 );
    }
  }
  if ( *(_DWORD *)&v5[2].XState )
  {
    v31 = 0;
    v7 = 0;
    do
    {
      v32 = (struct _NET_BUFFER_LIST *)v8->Link.Alignment;
      v8->Link.Alignment = 0;
      if ( v8->NdisPoolHandle == PoolHandle )
      {
        _InterlockedDecrement((volatile signed __int32 *)&v5[2].XState);
        FirstNetBuffer = v8->FirstNetBuffer;
        v34 = (struct _NPAGED_LOOKASIDE_LIST *)v8->MiniportReserved[1];
        CurrentMdl = FirstNetBuffer->CurrentMdl;
        if ( (CurrentMdl->MdlFlags & 0x20) != 0 )
          MmUnmapLockedPages(CurrentMdl->MappedSystemVa, FirstNetBuffer->CurrentMdl);
        if ( v34 )
          ExFreeToNPagedLookasideList(v34, CurrentMdl);
        else
          ExFreePoolWithTag(CurrentMdl, 0);
        NdisFreeNetBufferList(NetBufferList);
      }
      else
      {
        if ( v31 )
          *(_QWORD *)v7 = v8;
        else
          v31 = v8;
        v7 = (unsigned __int64)v8;
      }
      NetBufferList = v32;
      v8 = v32;
    }
    while ( v32 );
    if ( !v31 )
      return;
    v8 = v31;
    NetBufferList = v31;
  }
  v36 = v28 & 1;
  Number = -1;
  v38 = 2;
  if ( !*(_DWORD *)ndisNblTrackerMode )
    goto LABEL_85;
  v39 = ndisNblTrackerEpoch;
  v40 = 0;
  v7 = 0;
  v89 = 0;
  v109 = 0;
  v41 = *(_QWORD *)&v92[1].NicSwitchHwCapabilities.MaxNumQueuePairsForDefaultVPort;
  v102 = v36;
  v105 = 0;
  if ( *(int *)ndisNblTrackerMode >= 3 )
  {
    ndisNblTrackerRecordEventInternal(v8, 0, 0x87u, (void *)v41, v36);
    v40 = 0;
  }
  v42 = v41 & 0xFFFFFFFFFFFFFFFDuLL;
  if ( (v41 & 1) != 0 )
  {
    v43 = (2 * v39) ^ ((2 * v39) ^ v41) & 0xFFFFFFFFFFFFFFFDuLL;
    v42 = *(_QWORD *)((v42 & 0xFFFFFFFFFFFFFFF8uLL) + 24);
  }
  else
  {
    v43 = v41 & 0xFFFFFFFFFFFFFFFDuLL;
  }
  do
  {
    v44 = (unsigned __int64)v8->NetBufferListInfo[27];
    while ( v8->NetBufferListInfo[27] == (void *)v44 )
    {
      if ( v44 )
      {
        if ( (v44 & 4) != 0 )
          goto LABEL_155;
      }
      else if ( !v8->SourceHandle )
      {
        v8->SourceHandle = 0;
      }
      SourceHandle = (char *)v8->SourceHandle;
      if ( SourceHandle )
      {
        v46 = (unsigned __int8)*SourceHandle;
        if ( (unsigned __int8)(v46 - 17) <= 1u || (_BYTE)v46 == 5 )
        {
          if ( SourceHandle != (char *)v42 || v8->ParentNetBufferList )
          {
            ++v7;
            v47 = v43;
          }
          else
          {
            ++v40;
            v47 = 24;
            v109 = v40;
            ++v7;
          }
          goto LABEL_68;
        }
        if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v46) = 3;
          WPP_RECORDER_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            v46,
            27,
            12,
            (struct _GUID *)&WPP_78a33c75b2d2335d1cf1dcc315edf7b8_Traceguids,
            (char)v8,
            *SourceHandle);
LABEL_195:
          v40 = v109;
        }
      }
      else if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        WPP_RECORDER_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          3,
          27,
          11,
          (struct _GUID *)&WPP_78a33c75b2d2335d1cf1dcc315edf7b8_Traceguids,
          (char)v8);
        goto LABEL_195;
      }
LABEL_155:
      v47 = v43 | 4;
LABEL_68:
      v8->NetBufferListInfo[27] = (void *)v47;
      v8 = (struct _NET_BUFFER_LIST *)v8->Link.Alignment;
      if ( !v8 )
        break;
    }
    v48 = v102;
    if ( (v44 & 1) == 0 )
      goto LABEL_74;
    v49 = v89 - v7;
    v90 = v89 - v7;
    if ( !v90 )
      goto LABEL_74;
    if ( v102 || v105 )
    {
      v50 = (v44 & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((v44 >> 1) & 1) + 3);
      if ( !v102 )
        goto LABEL_147;
      goto LABEL_73;
    }
    v105 = 1;
    CurrentIrql = KeGetCurrentIrql();
    v49 = v90;
    v84 = v44 >> 1;
    v85 = v44 & 0xFFFFFFFFFFFFFFF8uLL;
    v86 = 16 * ((v84 & 1) + 3);
    if ( CurrentIrql == 2 )
    {
      v48 = 1;
      v50 = v85 + v86;
      v102 = 1;
LABEL_73:
      v51 = KeGetPcr()->Prcb.Number << 12;
      *(_QWORD *)(v51 + *(_QWORD *)v50) += v49;
      goto LABEL_74;
    }
    v48 = 0;
    v102 = 0;
    v50 = v85 + v86;
LABEL_147:
    _InterlockedAdd64((volatile signed __int64 *)(v50 + 8), v49);
LABEL_74:
    v40 = v109;
    v89 = v7;
  }
  while ( v8 );
  Number = -1;
  if ( (v43 & 1) != 0 )
  {
    v7 -= v109;
    if ( v7 )
    {
      if ( v48 || v105 )
      {
        v53 = (v43 & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((v43 >> 1) & 1) + 3);
        if ( v48 )
          goto LABEL_83;
LABEL_80:
        _InterlockedAdd64((volatile signed __int64 *)(v53 + 8), v7);
      }
      else
      {
        v52 = KeGetCurrentIrql();
        v53 = (v43 & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((v43 >> 1) & 1) + 3);
        if ( v52 != 2 )
          goto LABEL_80;
LABEL_83:
        v54 = KeGetPcr()->Prcb.Number << 12;
        *(_QWORD *)(v54 + *(_QWORD *)v53) += v7;
      }
    }
  }
  v38 = 2;
LABEL_85:
  v106 = v29 & 0x20;
  if ( (v29 & 0x20) != 0 )
  {
    if ( !v36 )
      v38 = KfRaiseIrql(2u);
    Number = KeGetPcr()->Prcb.Number;
    *(wchar_t **)((char *)&value[21].Buffer + ndisPcwPerCpuDataStride * Number + ndisPcwOffsetToPerCpuData) = (wchar_t *)__rdtsc();
  }
  v103 = v38;
  v55 = *(_QWORD *)&v92[1].NicSwitchCurrentCapabilities.Flags;
  v56 = *(void (__fastcall **)(unsigned __int64, unsigned __int64, __int64))&v92[1].NicSwitchCurrentCapabilities.NdisReserved14;
  v57 = *(_QWORD *)&v92[1].NicSwitchHwCapabilities.NumberOfIndirectionTableEntriesForDefaultVPort;
  if ( *(_BYTE *)v55 == 17 )
    goto LABEL_94;
  if ( v36 || KeGetCurrentIrql() == 2 )
  {
    LODWORD(v7) = KeGetPcr()->Prcb.Number;
    p_LowLimit = &LowLimit;
    v95 = 0;
    LowLimit = (unsigned __int64)NetBufferList;
    HighLimit = (unsigned __int64)NetBufferList;
    NetBufferList->Scratch = 0;
    NetBufferList->ChildRefCount = v36;
    while ( *(_BYTE *)v55 == 5 )
    {
      v64 = *p_LowLimit;
      if ( !*p_LowLimit )
        break;
      v65 = *(_QWORD *)(v55 + 424) + 96 * v7;
      if ( *(_BYTE *)(v65 + 88) )
      {
        *p_LowLimit = 0;
        do
        {
          v75 = ndisVerifierNdisDispatch;
          v76 = *(unsigned int *)(v64 + 132);
          v77 = *(_QWORD *)(v64 + 112);
          *(_DWORD *)(v64 + 132) = 0;
          if ( v75 && *(_BYTE *)v55 == 5 && *(_QWORD *)(v55 + 776) )
            (*((void (__fastcall **)(unsigned __int64, unsigned __int64, __int64))v75 + 17))(v57, v64, v76);
          else
            v56(v57, v64, v76);
          v64 = v77;
        }
        while ( v77 );
        break;
      }
      *(_BYTE *)(v65 + 88) = 1;
      v66 = v55;
      v67 = *p_LowLimit;
      *p_LowLimit = 0;
      if ( v67 )
      {
        do
        {
          v68 = ndisVerifierNdisDispatch;
          v69 = *(unsigned int *)(v67 + 132);
          v70 = *(_QWORD *)(v67 + 112);
          *(_DWORD *)(v67 + 132) = 0;
          if ( v68 && *(_BYTE *)v55 == 5 && *(_QWORD *)(v55 + 776) )
            (*((void (__fastcall **)(unsigned __int64, unsigned __int64, __int64))v68 + 17))(v57, v67, v69);
          else
            v56(v57, v67, v69);
          v67 = v70;
        }
        while ( v70 );
      }
      *(_BYTE *)(v65 + 88) = 0;
      p_LowLimit = (unsigned __int64 *)(v65 + 72);
      v55 = *(_QWORD *)(v55 + 552);
      v56 = *(void (__fastcall **)(unsigned __int64, unsigned __int64, __int64))(v66 + 528);
      v57 = *(_QWORD *)(v66 + 536);
    }
    v78 = *p_LowLimit;
    if ( *p_LowLimit )
    {
      *p_LowLimit = 0;
      do
      {
        v79 = ndisVerifierNdisDispatch;
        v80 = *(unsigned int *)(v78 + 132);
        v81 = *(_QWORD *)(v78 + 112);
        *(_DWORD *)(v78 + 132) = 0;
        if ( v79 && *(_BYTE *)v55 == 5 && *(_QWORD *)(v55 + 776) )
          (*((void (__fastcall **)(unsigned __int64, unsigned __int64, __int64))v79 + 17))(v57, v78, v80);
        else
          v56(v57, v78, v80);
        v78 = v81;
      }
      while ( v81 );
    }
    v38 = v103;
  }
  else
  {
    if ( v92->Header.Type != 5 )
      goto LABEL_94;
    v58 = (unsigned int)Size;
    LowLimit = 0;
    HighLimit = 0;
    v59 = KeGetPcr()->Prcb.Number << 12;
    v60 = *(_QWORD *)(v59 + qword_140122F78);
    LowLimit = v60;
    HighLimit = *(_QWORD *)(v59 + qword_140122F70);
    if ( (unsigned __int64)&retaddr >= HighLimit || v60 > (unsigned __int64)&retaddr )
    {
      IoGetStackLimits(&LowLimit, &HighLimit);
      v60 = LowLimit;
    }
    if ( (unsigned __int64)&retaddr - v60 < v58 )
    {
      v71 = 24576;
      HighLimit = v57;
      v96 = NetBufferList;
      v99 = 0;
      LowLimit = v55;
      v95 = v56;
      v97 = 0;
      v98 = 0;
      if ( (unsigned int)Size > 0x6000 )
        v71 = Size;
      if ( KeExpandKernelStackAndCalloutEx(
             ndisDataPathExpandStackCallback<3,void (void *,_NET_BUFFER_LIST *,unsigned long)>,
             &LowLimit,
             v71,
             0,
             0) < 0 )
      {
        if ( *(_DWORD *)ndisNblTrackerMode )
          ndisNblTrackerTransferOwnershipInternal(
            NetBufferList,
            v92->NblTracker,
            (struct NDIS_NBL_TRACKER_HANDLE__ *)0xA0,
            (enum _NDIS_NBL_TRACKER_OWNERSHIP_EVENT)1,
            0);
        v72 = KeAcquireSpinLockRaiseToDpc(&v92->Lock);
        v92->LockThread = KeGetCurrentThread();
        p_ReceivedNblsToComplete = &v92->StackExpansionFallback.PendingWork.ReceivedNblsToComplete;
        for ( j = (_SLIST_HEADER *)v92->StackExpansionFallback.PendingWork.ReceivedNblsToComplete;
              j;
              j = (_SLIST_HEADER *)j->Alignment )
        {
          p_ReceivedNblsToComplete = (_NET_BUFFER_LIST **)j;
        }
        *p_ReceivedNblsToComplete = NetBufferList;
        ndisQueueStackExpansionFallbackWorkItem(v92);
        v92->LockThread = 0;
        KeReleaseSpinLock(&v92->Lock, v72);
      }
    }
    else
    {
      if ( ndisVerifierNdisDispatch && *(_BYTE *)v55 == 5 && *(_QWORD *)(v55 + 776) )
      {
        (*((void (__fastcall **)(unsigned __int64, PNET_BUFFER_LIST, _QWORD))ndisVerifierNdisDispatch + 17))(
          v57,
          NetBufferList,
          0);
        goto LABEL_95;
      }
LABEL_94:
      v56(v57, (unsigned __int64)NetBufferList, v36);
    }
  }
LABEL_95:
  if ( v106 )
  {
    if ( Number == -1 )
      Number = KeGetPcr()->Prcb.Number;
    v61 = (__int64)value + ndisPcwPerCpuDataStride * Number + ndisPcwOffsetToPerCpuData;
    v62 = __rdtsc();
    *(_QWORD *)(v61 + 144) += (((unsigned __int64)HIDWORD(v62) << 32) | (unsigned int)v62) - *(_QWORD *)(v61 + 344);
    *(_QWORD *)(v61 + 344) = 0;
    if ( v38 != 2 )
      KeLowerIrql(v38);
  }
}

```

## disassembly

```asm
0x14002d620  mov     r11, rsp
0x14002d623  push    rbx
0x14002d624  push    rdi
0x14002d625  sub     rsp, 0C8h
0x14002d62c  mov     rax, [rcx+8]
0x14002d630  mov     rbx, rcx
0x14002d633  mov     rdi, [rcx+18h]
0x14002d637  mov     dword ptr [rcx+2B0h], 0
0x14002d641  cmp     qword ptr [rax+148h], 0
0x14002d649  jnz     loc_14002D921
0x14002d64f  mov     eax, [rcx+10h]
0x14002d652  test    al, 2
0x14002d654  jnz     loc_14002D921
0x14002d65a  mov     [r11-28h], r12
0x14002d65e  xor     eax, eax
0x14002d660  mov     [r11-30h], r13
0x14002d664  xor     r9d, r9d
0x14002d667  mov     r13, [rcx]
0x14002d66a  xor     r8d, r8d
0x14002d66d  mov     [r11-38h], r14
0x14002d671  xor     r12d, r12d
0x14002d674  mov     [r11-40h], r15
0x14002d678  xor     r14d, r14d
0x14002d67b  xor     r11b, r11b
0x14002d67e  mov     [rsp+0D8h+var_18], rbp
0x14002d686  mov     [rsp+0D8h+arg_0], r11b
0x14002d68e  xor     r15d, r15d
0x14002d691  mov     [rsp+0D8h+var_80], r13
0x14002d696  mov     [rsp+0D8h+LowLimit], r9
0x14002d69b  mov     [rsp+0D8h+NetBufferList], r14
0x14002d6a0  mov     dword ptr [rsp+0D8h+var_90], eax
0x14002d6a4  mov     dword ptr [rsp+0D8h+arg_18], r8d
0x14002d6ac  mov     [rcx+38h], rax
0x14002d6b0  mov     [rcx+40h], rax
0x14002d6b4  mov     [rcx+48h], rax
0x14002d6b8  mov     [rcx+30h], ax
0x14002d6bc  mov     [rcx+50h], eax
0x14002d6bf  mov     [rsp+0D8h+var_20], rsi
0x14002d6c7  test    rdi, rdi
0x14002d6ca  jz      loc_14002D8A9
0x14002d6d0  mov     r13, [rdi]
0x14002d6d3  xor     eax, eax
0x14002d6d5  mov     qword ptr [rdi], 0
0x14002d6dc  mov     r10, rdi
0x14002d6df  mov     word ptr [rsp+0D8h+arg_8], ax
0x14002d6e7  mov     rax, [rbx]
0x14002d6ea  cmp     dword ptr [rax+1D0h], 0
0x14002d6f1  jnz     loc_14002E127
0x14002d6f7  xor     eax, eax
0x14002d6f9  mov     word ptr [rsp+0D8h+arg_10], ax
0x14002d701  mov     rax, [rdi+8]
0x14002d705  mov     rcx, [rax+8]; MemoryDescriptorList
0x14002d709  test    rcx, rcx
0x14002d70c  jz      loc_14002E3C1
0x14002d712  mov     esi, [rcx+28h]
0x14002d715  cmp     esi, 0Eh
0x14002d718  jb      loc_14002E3C1
0x14002d71e  mov     ebp, [rax+10h]
0x14002d721  cmp     esi, ebp
0x14002d723  jbe     loc_14002E3C1
0x14002d729  mov     r14d, esi
0x14002d72c  sub     r14d, ebp
0x14002d72f  cmp     r14d, 0Eh
0x14002d733  jb      loc_14002E441
0x14002d739  test    byte ptr [rcx+0Ah], 5
0x14002d73d  jz      loc_14002E3EF
0x14002d743  mov     rax, [rcx+18h]
0x14002d747  movzx   ecx, byte ptr [rax+rbp+0Ch]
0x14002d74c  lea     rdx, [rax+rbp]
0x14002d750  movzx   eax, byte ptr [rax+rbp+0Dh]
0x14002d755  mov     byte ptr [rsp+0D8h+arg_10+1], cl
0x14002d75c  mov     byte ptr [rsp+0D8h+arg_10], al
0x14002d763  mov     byte ptr [rsp+0D8h+arg_8], cl
0x14002d76a  mov     ecx, 600h
0x14002d76f  mov     byte ptr [rsp+0D8h+arg_8+1], al
0x14002d776  movzx   eax, word ptr [rsp+0D8h+arg_10]
0x14002d77e  cmp     ax, cx
0x14002d781  jbe     loc_14002E398
0x14002d787  mov     ecx, 8100h
0x14002d78c  cmp     ax, cx
0x14002d78f  jz      loc_14002E41B
0x14002d795  movzx   eax, word ptr [rsp+0D8h+arg_8]
0x14002d79d  mov     cl, 1
0x14002d79f  movzx   r15d, ax
0x14002d7a3  test    cl, cl
0x14002d7a5  jz      loc_14002DFC4
0x14002d7ab  mov     r9, [rbx+8]
0x14002d7af  movzx   eax, r15w
0x14002d7b3  cmp     dword ptr [rsp+0D8h+var_90], eax
0x14002d7b7  jz      short loc_14002D7F0
0x14002d7b9  mov     ecx, [r9+18h]
0x14002d7bd  xor     edx, edx
0x14002d7bf  mov     dword ptr [rsp+0D8h+var_90], eax
0x14002d7c3  cmp     edx, ecx
0x14002d7c5  jnb     loc_14002DFB0
0x14002d7cb  mov     eax, edx
0x14002d7cd  add     rax, rax
0x14002d7d0  cmp     r15w, [r9+rax*8+20h]
0x14002d7d6  jnz     loc_14002DDD5
0x14002d7dc  mov     r11b, 1
0x14002d7df  mov     dword ptr [rsp+0D8h+arg_18], edx
0x14002d7e6  mov     [rsp+0D8h+arg_0], r11b
0x14002d7ee  jmp     short loc_14002D7FD
0x14002d7f0  mov     edx, r8d
0x14002d7f3  cmp     r11b, 1
0x14002d7f7  jnz     loc_14002DFC4
0x14002d7fd  mov     eax, r12d
0x14002d800  lea     rcx, [rax+rax*4]
0x14002d804  cmp     [rbx+rcx*8+30h], r15w
0x14002d80a  jz      loc_14002D919
0x14002d810  mov     r10d, [rbx+2B0h]
0x14002d817  mov     r8d, 1
0x14002d81d  cmp     r8d, r10d
0x14002d820  jbe     loc_14002E110
0x14002d826  inc     dword ptr [rbx+2B0h]
0x14002d82c  mov     r10, rdi
0x14002d82f  mov     r12d, [rbx+2B0h]
0x14002d836  mov     r8d, r12d
0x14002d839  lea     rax, [r12+r12*4]
0x14002d83d  lea     rcx, [rbx+rax*8]
0x14002d841  mov     eax, edx
0x14002d843  inc     rax
0x14002d846  mov     [rcx+30h], r15w
0x14002d84b  add     rax, rax
0x14002d84e  mov     rax, [r9+rax*8+18h]
0x14002d853  mov     [rcx+38h], rax
0x14002d857  mov     qword ptr [rcx+40h], 0
0x14002d85f  mov     ecx, r8d
0x14002d862  lea     rax, [rcx+rcx*4]
0x14002d866  add     rcx, 2
0x14002d86a  cmp     qword ptr [rbx+rax*8+40h], 0
0x14002d870  lea     r8, [rbx+rax*8]
0x14002d874  lea     rax, [rcx+rcx*4]
0x14002d878  lea     rcx, [rbx+rax*8]
0x14002d87c  jnz     short loc_14002D8ED
0x14002d87e  mov     [r8+40h], rdi
0x14002d882  test    dword ptr [rbx+10h], 100h
0x14002d889  jz      loc_14002DC1C
0x14002d88f  mov     r14, [rsp+0D8h+NetBufferList]
0x14002d894  mov     qword ptr [r8+48h], 0
0x14002d89c  mov     [rdi], r13
0x14002d89f  mov     eax, [rbx+2Ch]
0x14002d8a2  mov     r13, [rsp+0D8h+var_80]
0x14002d8a7  mov     [rcx], eax
0x14002d8a9  test    r14, r14
0x14002d8ac  jnz     loc_14002D946
0x14002d8b2  mov     rsi, [rsp+0D8h+var_20]
0x14002d8ba  mov     rbp, [rsp+0D8h+var_18]
0x14002d8c2  mov     r12, [rsp+0D8h+var_28]
0x14002d8ca  mov     r13, [rsp+0D8h+var_30]
0x14002d8d2  mov     r14, [rsp+0D8h+var_38]
0x14002d8da  mov     r15, [rsp+0D8h+var_40]
0x14002d8e2  add     rsp, 0C8h
0x14002d8e9  pop     rdi
0x14002d8ea  pop     rbx
0x14002d8eb  retn
0x14002d8ed  mov     rax, [r8+48h]
0x14002d8f1  mov     [rax], rdi
0x14002d8f4  inc     dword ptr [rcx]
0x14002d8f6  mov     r14, [rsp+0D8h+NetBufferList]
0x14002d8fb  mov     rdi, r13
0x14002d8fe  mov     r13, [rsp+0D8h+var_80]
0x14002d903  mov     [r8+48h], r10
0x14002d907  mov     r8d, dword ptr [rsp+0D8h+arg_18]
0x14002d90f  mov     r9, [rsp+0D8h+LowLimit]
0x14002d914  jmp     loc_14002D6C7
0x14002d919  mov     r8d, r12d
0x14002d91c  jmp     loc_14002D85F
0x14002d921  mov     [rcx+40h], rdi
0x14002d925  mov     rax, [rcx+20h]
0x14002d929  mov     [rcx+48h], rax
0x14002d92d  mov     qword ptr [rcx+38h], 0
0x14002d935  mov     eax, [rcx+2Ch]
0x14002d938  mov     [rcx+50h], eax
0x14002d93b  add     rsp, 0C8h
0x14002d942  pop     rdi
0x14002d943  pop     rbx
0x14002d944  retn
0x14002d946  cmp     cs:byte_140123720, 0
0x14002d94d  jnz     loc_14002E268
0x14002d953  mov     ebp, [rbx+10h]
0x14002d956  test    bpl, 2
0x14002d95a  jnz     loc_14002D8B2
0x14002d960  cmp     dword ptr [r13+30h], 0
0x14002d965  jnz     loc_14002E076
0x14002d96b  xor     esi, esi
0x14002d96d  mov     [rsp+0D8h+var_88], 0
0x14002d976  cmp     [r13+50h], esi
0x14002d97a  jnz     loc_14002E076
0x14002d980  mov     rcx, r14
0x14002d983  mov     eax, [rcx+88h]
0x14002d989  and     eax, 0FFFFFFFCh
0x14002d98c  or      eax, 8
0x14002d98f  mov     [rcx+88h], eax
0x14002d995  mov     rcx, [rcx]
0x14002d998  test    rcx, rcx
0x14002d99b  jnz     short loc_14002D983
0x14002d99d  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14002d9a3  test    eax, eax
0x14002d9a5  jnz     loc_14002E0E8
0x14002d9ab  cmp     cs:byte_140123720, al
0x14002d9b1  jnz     loc_14002E0E8
0x14002d9b7  cmp     dword ptr [r13+0C98h], 0
0x14002d9bf  jz      loc_14002DA47
0x14002d9c5  xor     ebx, ebx
0x14002d9c7  xor     r12d, r12d
0x14002d9ca  mov     rdi, [r14]
0x14002d9cd  mov     qword ptr [r14], 0
0x14002d9d4  mov     rax, cs:PoolHandle
0x14002d9db  cmp     [r14+20h], rax
0x14002d9df  jnz     loc_14002E463
0x14002d9e5  lock dec dword ptr [r13+0C98h]
0x14002d9ed  mov     rax, [r14+8]
0x14002d9f1  mov     r14, [r14+68h]
0x14002d9f5  mov     r15, [rax+8]
0x14002d9f9  test    byte ptr [r15+0Ah], 20h
0x14002d9fe  jnz     loc_14002E44B
0x14002da04  test    r14, r14
0x14002da07  jz      loc_14002E14C
0x14002da0d  mov     rdx, r15; Entry
0x14002da10  mov     rcx, r14; Lookaside
0x14002da13  call    cs:__imp_ExFreeToNPagedLookasideList
0x14002da1a  nop     dword ptr [rax+rax+00h]
0x14002da1f  mov     rcx, [rsp+0D8h+NetBufferList]; NetBufferList
0x14002da24  call    NdisFreeNetBufferList
0x14002da29  mov     [rsp+0D8h+NetBufferList], rdi
0x14002da2e  mov     r14, rdi
0x14002da31  test    rdi, rdi
0x14002da34  jnz     short loc_14002D9CA
0x14002da36  test    rbx, rbx
0x14002da39  jz      loc_14002D8B2
0x14002da3f  mov     r14, rbx
0x14002da42  mov     [rsp+0D8h+NetBufferList], rbx
0x14002da47  mov     eax, cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x14002da4d  and     ebp, 1
0x14002da50  mov     r15d, 0FFFFFFFFh
0x14002da56  mov     r13b, 2
0x14002da59  mov     [rsp+0D8h+arg_10], r15d
0x14002da61  test    eax, eax
0x14002da63  jz      loc_14002DC5B
0x14002da69  mov     rbx, [rsp+0D8h+var_80]
0x14002da6e  xor     ecx, ecx
0x14002da70  mov     edi, cs:?ndisNblTrackerEpoch@@3KA; ulong ndisNblTrackerEpoch
0x14002da76  xor     r9d, r9d
0x14002da79  xor     r12d, r12d
0x14002da7c  mov     [rsp+0D8h+var_90], rcx
0x14002da81  mov     [rsp+0D8h+arg_18], r9
0x14002da89  mov     rbx, [rbx+9E8h]
0x14002da90  mov     [rsp+0D8h+arg_0], bpl
0x14002da98  mov     byte ptr [rsp+0D8h+arg_8], cl
0x14002da9f  cmp     eax, 3
0x14002daa2  jl      short loc_14002DABE
0x14002daa4  mov     r9, rbx; void *
0x14002daa7  mov     dword ptr [rsp+0D8h+Context], ebp; unsigned int
0x14002daab  xor     edx, edx; struct NDIS_NBL_TRACKER_HANDLE__ *
0x14002daad  mov     r8d, 87h; unsigned int
0x14002dab3  mov     rcx, r14; struct _NET_BUFFER_LIST *
0x14002dab6  call    ?ndisNblTrackerRecordEventInternal@@YAXPEAU_NET_BUFFER_LIST@@PEAUNDIS_NBL_TRACKER_HANDLE__@@KPEAXK@Z; ndisNblTrackerRecordEventInternal(_NET_BUFFER_LIST *,NDIS_NBL_TRACKER_HANDLE__ *,ulong,void *,ulong)
0x14002dabb  mov     r9d, r12d
0x14002dabe  mov     r13, rbx
0x14002dac1  and     r13, 0FFFFFFFFFFFFFFFDh
0x14002dac5  test    r13b, 1
0x14002dac9  jz      loc_14002E1EB
0x14002dacf  mov     rax, rdi
0x14002dad2  add     rax, rax
0x14002dad5  xor     rbx, rax
0x14002dad8  and     rbx, 0FFFFFFFFFFFFFFFDh
0x14002dadc  xor     rbx, rax
0x14002dadf  and     r13, 0FFFFFFFFFFFFFFF8h
0x14002dae3  mov     r13, [r13+18h]
0x14002dae7  mov     rdi, [r14+168h]
0x14002daee  lea     r8, WPP_RECORDER_INITIALIZED
0x14002daf5  lea     r15, WPP_78a33c75b2d2335d1cf1dcc315edf7b8_Traceguids
0x14002dafc  cmp     [r14+168h], rdi
0x14002db03  jnz     short loc_14002DB51
0x14002db05  test    rdi, rdi
0x14002db08  jz      loc_14002E1F3
0x14002db0e  test    dil, 4
0x14002db12  jnz     loc_14002E218
0x14002db18  mov     rcx, [r14+78h]
0x14002db1c  test    rcx, rcx
0x14002db1f  jz      loc_14002E20B
0x14002db25  movzx   edx, byte ptr [rcx]
0x14002db28  lea     eax, [rdx-11h]
0x14002db2b  cmp     al, 1
0x14002db2d  ja      loc_14002E224
0x14002db33  cmp     rcx, r13
0x14002db36  jz      loc_14002E1C8
0x14002db3c  inc     r12
0x14002db3f  mov     rax, rbx
0x14002db42  mov     [r14+168h], rax
0x14002db49  mov     r14, [r14]
0x14002db4c  test    r14, r14
0x14002db4f  jnz     short loc_14002DAFC
0x14002db51  movzx   r15d, byte ptr [rsp+0D8h+arg_8]
0x14002db5a  movzx   r8d, [rsp+0D8h+arg_0]
0x14002db63  test    dil, 1
0x14002db67  jz      short loc_14002DBB6
0x14002db69  mov     r9, [rsp+0D8h+var_90]
0x14002db6e  sub     r9, r12
  ... truncated ...
```
