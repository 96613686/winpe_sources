# NdisReturnNetBufferLists

- ea: `0x1400218a0`
- end: `0x140022717`
- name: `NdisReturnNetBufferLists`
- size: `3703`
- prototype: `void __stdcall(NDIS_HANDLE NdisBindingHandle, PNET_BUFFER_LIST NetBufferLists, ULONG ReturnFlags)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1400110b0`
- `0x140011190`
- `0x1400218a0`
- `0x1400231d0`
- `0x140023900`
- `0x1400252e0`
- `0x140025d30`
- `0x1400260b0`
- `0x140032cb0`
- `0x1400a4d24`
- `0x1400eb460`
- `0x1400eb7c0`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x140021a16`
- `ntoskrnl!KeLowerIrql` at `0x140021fad`
- `ntoskrnl!KeLowerIrql` at `0x140022439`
- `ntoskrnl!KeLowerIrql` at `0x140021a16`
- `ntoskrnl!KeLowerIrql` at `0x140021fad`
- `ntoskrnl!KeLowerIrql` at `0x140022439`
- `ntoskrnl!KeGetCurrentIrql` at `0x140021db2`
- `ntoskrnl!KeGetCurrentIrql` at `0x140021ff3`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002204c`
- `ntoskrnl!KeGetCurrentIrql` at `0x140021db2`
- `ntoskrnl!KeGetCurrentIrql` at `0x140021ff3`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002204c`
- `ntoskrnl!MmUnmapLockedPages` at `0x140022686`
- `ntoskrnl!MmUnmapLockedPages` at `0x140022686`
- `ntoskrnl!MmBadPointer` at `0x1400ee572`
- `ntoskrnl!KfRaiseIrql` at `0x14002194d`
- `ntoskrnl!KfRaiseIrql` at `0x140022347`
- `ntoskrnl!KfRaiseIrql` at `0x14002194d`
- `ntoskrnl!KfRaiseIrql` at `0x140022347`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140021b38`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140021b38`
- `ntoskrnl!IoGetStackLimits` at `0x140021e3b`
- `ntoskrnl!IoGetStackLimits` at `0x140021e3b`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140021ec9`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140021ec9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400224e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400224e9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140021f3c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140021f3c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140021eed`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140021eed`

## pseudocode

```c
void __stdcall NdisReturnNetBufferLists(
        NDIS_HANDLE NdisBindingHandle,
        PNET_BUFFER_LIST NetBufferLists,
        ULONG ReturnFlags)
{
  unsigned __int64 v3; // rbp
  _DWORD *v4; // rbx
  char v5; // r13
  PNET_BUFFER_LIST v6; // r14
  int v7; // edi
  int v8; // r12d
  unsigned int Number; // r9d
  KIRQL v10; // r11
  KIRQL v11; // al
  _SLIST_HEADER *v12; // rax
  unsigned int v13; // r8d
  PNET_BUFFER_LIST Alignment; // r15
  char v15; // r13
  PNET_BUFFER_LIST k; // rcx
  struct _NET_BUFFER_LIST *v17; // r12
  _QWORD *p_Alignment; // rbx
  struct _NET_BUFFER_LIST *v19; // r15
  _NET_BUFFER *FirstNetBuffer; // rax
  struct _NPAGED_LOOKASIDE_LIST *v21; // rdi
  _MDL *CurrentMdl; // r13
  __int64 v23; // r12
  struct NDIS_NBL_TRACKER_HANDLE__ *v24; // r10
  unsigned __int64 v25; // rdi
  unsigned int v26; // r13d
  __int64 v27; // rbx
  __int64 v28; // rdx
  __int64 v29; // r9
  unsigned __int64 v30; // r15
  unsigned __int64 v31; // rbx
  _SLIST_HEADER *v32; // r12
  unsigned __int64 Region; // rdi
  char *v34; // rcx
  char v35; // r8
  __int64 v36; // rax
  unsigned __int64 v37; // r9
  unsigned __int64 v38; // r8
  __int64 v39; // rcx
  unsigned __int64 v40; // rdx
  __int64 v41; // rcx
  unsigned __int64 v42; // r13
  void (__fastcall *v43)(unsigned __int64, unsigned __int64, __int64); // rdi
  unsigned __int64 v44; // r15
  unsigned __int64 v45; // r12
  __int64 v46; // rcx
  unsigned __int64 v47; // rdx
  int v48; // ecx
  KIRQL v49; // di
  PNET_BUFFER_LIST *v50; // rcx
  _QWORD *m; // rdx
  __int64 v52; // r8
  unsigned __int64 v53; // rax
  KIRQL CurrentIrql; // al
  unsigned __int64 v55; // r8
  unsigned __int64 v56; // rdi
  __int64 v57; // r8
  KIRQL v58; // al
  unsigned __int64 *p_LowLimit; // rbx
  unsigned __int64 v60; // rdx
  __int64 v61; // rbp
  unsigned __int64 v62; // r14
  unsigned __int64 v63; // rdx
  struct _VF_NDIS_DISPATCH_TABLE *v64; // rax
  __int64 v65; // r8
  unsigned __int64 v66; // rbx
  struct _VF_NDIS_DISPATCH_TABLE *v67; // rax
  __int64 v68; // r8
  unsigned __int64 v69; // rbp
  unsigned __int64 v70; // rdx
  struct _VF_NDIS_DISPATCH_TABLE *v71; // rax
  __int64 v72; // r8
  unsigned __int64 v73; // rbx
  int v74; // eax
  unsigned __int64 v75; // rax
  struct _NET_BUFFER_LIST *j; // r15
  unsigned int v77; // eax
  __int64 v78; // r8
  unsigned __int64 v79; // rax
  _SLIST_HEADER *v80; // rax
  unsigned int Flags; // eax
  unsigned int v82; // eax
  _NET_BUFFER_LIST_CONTEXT *i; // r12
  KIRQL v84; // [rsp+40h] [rbp-B8h]
  int v85; // [rsp+44h] [rbp-B4h]
  int v86; // [rsp+48h] [rbp-B0h]
  int v87; // [rsp+4Ch] [rbp-ACh]
  int v88; // [rsp+4Ch] [rbp-ACh]
  __int64 v89; // [rsp+50h] [rbp-A8h]
  unsigned __int64 v90; // [rsp+50h] [rbp-A8h]
  char v91; // [rsp+58h] [rbp-A0h]
  __int64 v92; // [rsp+60h] [rbp-98h]
  unsigned __int64 v93; // [rsp+60h] [rbp-98h]
  __int64 v94; // [rsp+68h] [rbp-90h]
  __int64 v95; // [rsp+70h] [rbp-88h]
  struct NDIS_NBL_TRACKER_HANDLE__ *v96; // [rsp+78h] [rbp-80h]
  __int64 v97; // [rsp+80h] [rbp-78h]
  unsigned __int64 LowLimit; // [rsp+88h] [rbp-70h] BYREF
  unsigned __int64 HighLimit; // [rsp+90h] [rbp-68h] BYREF
  void (__fastcall *v100)(unsigned __int64, unsigned __int64, __int64); // [rsp+98h] [rbp-60h]
  PNET_BUFFER_LIST v101; // [rsp+A0h] [rbp-58h]
  __int64 v102; // [rsp+A8h] [rbp-50h]
  ULONG v103; // [rsp+B0h] [rbp-48h]
  int v104; // [rsp+B4h] [rbp-44h]
  _UNKNOWN *retaddr; // [rsp+F8h] [rbp+0h] BYREF
  char v107; // [rsp+100h] [rbp+8h]
  KIRQL v109; // [rsp+118h] [rbp+20h]

  v3 = *((_QWORD *)NdisBindingHandle + 2);
  v4 = NdisBindingHandle;
  LowLimit = v3;
  v5 = ReturnFlags;
  v6 = NetBufferLists;
  if ( *(_DWORD *)(v3 + 48) || (v7 = 0, v95 = 0, LOBYTE(v8) = 0, v91 = 0, *(_DWORD *)(v3 + 80)) )
  {
    v7 = *(_DWORD *)(v3 + 48);
    v8 = *(_DWORD *)(v3 + 80);
    v91 = v8;
    v95 = *(_QWORD *)(v3 + 40);
    if ( !v95 )
      v95 = *(_QWORD *)(v3 + 40);
  }
  if ( (*((_DWORD *)NdisBindingHandle + 56) & 1) != 0 )
  {
    ndisNblVerifyRxCompletion(NetBufferLists, ReturnFlags, (const struct _NDIS_OBJECT_HEADER *)NdisBindingHandle);
    Alignment = v6;
    if ( v6 )
    {
      v15 = byte_140122DF0;
      do
      {
        Flags = Alignment->Flags;
        Alignment->Scratch = MmBadPointer;
        Alignment->ChildRefCount = -892679478;
        if ( v15 )
        {
          v15 = 0;
          v82 = Flags & 0xFFF0FFFF;
        }
        else
        {
          v15 = 1;
          v82 = Flags | 0xF0000;
        }
        byte_140122DF0 = v15;
        Alignment->Flags = v82;
        for ( i = Alignment->Context; i; i = i->Next )
          memset(i->ContextData, 202, i->Offset);
        Alignment = (PNET_BUFFER_LIST)Alignment->Link.Alignment;
      }
      while ( Alignment );
      v5 = ReturnFlags;
      LOBYTE(v8) = v91;
    }
  }
  if ( !ndisNblContextVerifierMode || ndisNblContextVerifierMode == 3 )
    goto LABEL_5;
  switch ( *(_BYTE *)v4 )
  {
    case 5:
      v74 = v4[14] >> 10;
      goto LABEL_148;
    case 0x11:
      v74 = v4[922] >> 12;
LABEL_148:
      LOBYTE(v74) = v74 & 1;
LABEL_149:
      if ( (_BYTE)v74 )
      {
        for ( j = v6; j; j = (struct _NET_BUFFER_LIST *)j->Link.Alignment )
        {
          if ( *(_DWORD **)&j->Context->ContextData[j->Context->Offset] != v4 )
            NblContextVerifierBugcheckContextCorruption(j, v6, v4);
          NdisFreeNetBufferListContext(j, 8u);
        }
      }
      break;
    case 0x12:
      v74 = v4[56] >> 31;
      goto LABEL_149;
  }
LABEL_5:
  Number = -1;
  v10 = 2;
  v86 = -1;
  v84 = 2;
  if ( (v7 & 0x180028) != 0 || (v8 & 0x10) != 0 )
  {
    if ( (v5 & 1) == 0 )
    {
      v11 = KfRaiseIrql(2u);
      Number = -1;
      v10 = v11;
      v84 = v11;
    }
    if ( (v7 & 8) != 0 )
    {
      Number = KeGetPcr()->Prcb.Number;
      v86 = Number;
      ++*(_QWORD *)(ndisPcwOffsetToPerCpuData + v95 + ndisPcwPerCpuDataStride * Number + 24);
    }
    if ( !v10 && (v7 & 0x80000) != 0 )
    {
      if ( Number == -1 )
      {
        Number = KeGetPcr()->Prcb.Number;
        v86 = Number;
      }
      ++*(_QWORD *)(ndisPcwOffsetToPerCpuData + v95 + ndisPcwPerCpuDataStride * Number + 216);
    }
    if ( (v7 & 0x100020) != 0 )
    {
      v12 = (_SLIST_HEADER *)v6;
      v13 = 0;
      if ( v6 )
      {
        do
        {
          v12 = (_SLIST_HEADER *)v12->Alignment;
          ++v13;
        }
        while ( v12 );
      }
      if ( (v7 & 0x20) != 0 )
      {
        if ( Number == -1 )
        {
          Number = KeGetPcr()->Prcb.Number;
          v86 = Number;
        }
        *(_QWORD *)(v95 + ndisPcwPerCpuDataStride * Number + ndisPcwOffsetToPerCpuData + 40) += v13;
      }
      if ( !v10 && (v7 & 0x100000) != 0 )
      {
        if ( Number == -1 )
        {
          Number = KeGetPcr()->Prcb.Number;
          v86 = Number;
        }
        *(_QWORD *)(v95 + ndisPcwPerCpuDataStride * Number + ndisPcwOffsetToPerCpuData + 224) += v13;
      }
    }
    if ( (v8 & 0x10) != 0 )
    {
      if ( Number == -1 )
      {
        Number = KeGetPcr()->Prcb.Number;
        v86 = Number;
      }
      *(_QWORD *)(ndisPcwOffsetToPerCpuData + v95 + ndisPcwPerCpuDataStride * Number + 336) = __rdtsc();
    }
    else if ( v10 != 2 )
    {
      KeLowerIrql(v10);
    }
  }
  if ( *(_DWORD *)(v3 + 48) || (v97 = 0, LOBYTE(v87) = 0, *(_DWORD *)(v3 + 80)) )
  {
    v87 = *(_DWORD *)(v3 + 80);
    v97 = *(_QWORD *)(v3 + 40);
    if ( !v97 )
      v97 = *(_QWORD *)(v3 + 40);
  }
  for ( k = v6; k; k = (PNET_BUFFER_LIST)k->Link.Alignment )
    k->Flags = k->Flags & 0xFFFFFFF4 | 8;
  if ( (Microsoft_Windows_Networking_CorrelationEnabled || byte_140123720) && v6 )
  {
    v80 = (_SLIST_HEADER *)v6;
    if ( byte_140123720 )
    {
      do
      {
        v80[15].Region = 0;
        v80 = (_SLIST_HEADER *)v80->Alignment;
      }
      while ( v80 );
    }
    else
    {
      do
      {
        v80[15].Region |= 0x8000000000000000uLL;
        v80 = (_SLIST_HEADER *)v80->Alignment;
      }
      while ( v80 );
    }
  }
  if ( *(_DWORD *)(v3 + 3224) )
  {
    v17 = 0;
    if ( v6 )
    {
      p_Alignment = 0;
      do
      {
        v19 = (struct _NET_BUFFER_LIST *)v6->Link.Alignment;
        v6->Link.Alignment = 0;
        if ( v6->NdisPoolHandle == PoolHandle )
        {
          _InterlockedDecrement((volatile signed __int32 *)(v3 + 3224));
          FirstNetBuffer = v6->FirstNetBuffer;
          v21 = (struct _NPAGED_LOOKASIDE_LIST *)v6->MiniportReserved[1];
          CurrentMdl = FirstNetBuffer->CurrentMdl;
          if ( (CurrentMdl->MdlFlags & 0x20) != 0 )
            MmUnmapLockedPages(CurrentMdl->MappedSystemVa, FirstNetBuffer->CurrentMdl);
          if ( v21 )
            ExFreeToNPagedLookasideList(v21, CurrentMdl);
          else
            ExFreePoolWithTag(CurrentMdl, 0);
          NdisFreeNetBufferList(v6);
        }
        else
        {
          if ( v17 )
            *p_Alignment = v6;
          else
            v17 = v6;
          p_Alignment = &v6->Link.Alignment;
        }
        v6 = v19;
      }
      while ( v19 );
      v4 = NdisBindingHandle;
      v5 = ReturnFlags;
    }
    v6 = v17;
  }
  if ( !v6 )
    goto LABEL_94;
  v23 = 0xFFFFFFFFLL;
  v85 = -1;
  v109 = 2;
  if ( !*(_DWORD *)ndisNblTrackerMode )
    goto LABEL_73;
  v24 = (struct NDIS_NBL_TRACKER_HANDLE__ *)*((_QWORD *)v4 + 73);
  v25 = *(_QWORD *)(v3 + 2536);
  v26 = v5 & 1;
  v27 = ndisNblTrackerEpoch;
  v28 = 0;
  v96 = v24;
  v29 = 0;
  v89 = 0;
  v92 = 0;
  v94 = 0;
  v107 = 0;
  if ( *(int *)ndisNblTrackerMode >= 3 )
  {
    ndisNblTrackerRecordEventInternal(v6, v24, 0x87u, (void *)v25, v26);
    v24 = v96;
    v28 = 0;
    v29 = 0;
  }
  v30 = v25 & 0xFFFFFFFFFFFFFFFDuLL;
  if ( (v25 & 1) != 0 )
  {
    v31 = (2 * v27) ^ (v25 ^ (2 * v27)) & 0xFFFFFFFFFFFFFFFDuLL;
    v30 = *(_QWORD *)((v25 & 0xFFFFFFFFFFFFFFF8uLL) + 24);
  }
  else
  {
    v31 = v25 & 0xFFFFFFFFFFFFFFFDuLL;
  }
  v32 = (_SLIST_HEADER *)v6;
  do
  {
    Region = v32[22].Region;
    while ( v32[22].Region == Region )
    {
      if ( Region )
      {
        if ( (Region & 4) != 0 )
          goto LABEL_143;
      }
      else if ( !v32[7].Region )
      {
        v75 = (unsigned __int64)v24 & 0xFFFFFFFFFFFFFFFDuLL;
        if ( ((unsigned __int8)v24 & 1) != 0 )
          v75 = *(_QWORD *)(((unsigned __int64)v24 & 0xFFFFFFFFFFFFFFF8uLL) + 24);
        v32[7].Region = v75;
      }
      v34 = (char *)v32[7].Region;
      if ( v34 )
      {
        v35 = *v34;
        if ( (unsigned __int8)(*v34 - 17) <= 1u || v35 == 5 )
        {
          if ( v34 != (char *)v30 || v32[1].Region )
          {
            ++v28;
            v36 = v31;
            v89 = v28;
          }
          else
          {
            ++v29;
            v36 = 24;
            ++v28;
            v94 = v29;
            v89 = v28;
          }
          goto LABEL_60;
        }
        if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v28) = 3;
          WPP_RECORDER_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            v28,
            27,
            12,
            (struct _GUID *)&WPP_78a33c75b2d2335d1cf1dcc315edf7b8_Traceguids,
            (char)v32,
            v35);
LABEL_162:
          v28 = v89;
          v29 = v94;
          v24 = v96;
        }
      }
      else if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v28) = 3;
        WPP_RECORDER_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          v28,
          27,
          11,
          (struct _GUID *)&WPP_78a33c75b2d2335d1cf1dcc315edf7b8_Traceguids,
          (char)v32);
        goto LABEL_162;
      }
LABEL_143:
      v36 = v31 | 4;
LABEL_60:
      v32[22].Region = v36;
      v32 = (_SLIST_HEADER *)v32->Alignment;
      if ( !v32 )
        break;
    }
    if ( (Region & 1) == 0 )
      goto LABEL_66;
    v37 = v92 - v28;
    v93 = v92 - v28;
    if ( !v93 )
      goto LABEL_66;
    if ( (_BYTE)v26 || v107 )
    {
      v38 = (Region & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((Region >> 1) & 1) + 3);
      if ( !(_BYTE)v26 )
        goto LABEL_99;
      goto LABEL_65;
    }
    v107 = 1;
    CurrentIrql = KeGetCurrentIrql();
    v28 = v89;
    v37 = v93;
    v55 = Region >> 1;
    v56 = Region & 0xFFFFFFFFFFFFFFF8uLL;
    v57 = 16 * ((v55 & 1) + 3);
    if ( CurrentIrql == 2 )
    {
      LOBYTE(v26) = 1;
      v38 = v56 + v57;
LABEL_65:
      v39 = KeGetPcr()->Prcb.Number << 12;
      *(_QWORD *)(v39 + *(_QWORD *)v38) += v37;
      goto LABEL_66;
    }
    LOBYTE(v26) = 0;
    v38 = v56 + v57;
LABEL_99:
    _InterlockedAdd64((volatile signed __int64 *)(v38 + 8), v37);
LABEL_66:
    v29 = v94;
    v24 = v96;
    v92 = v28;
  }
  while ( v32 );
  v3 = LowLimit;
  if ( (v31 & 1) != 0 )
  {
    v90 = v28 - v94;
    if ( v28 != v94 )
    {
      if ( (_BYTE)v26 || v107 )
      {
        v40 = (v31 & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((v31 >> 1) & 1) + 3);
        if ( !(_BYTE)v26 )
          goto LABEL_102;
      }
      else
      {
        v58 = KeGetCurrentIrql();
        v40 = (v31 & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((v31 >> 1) & 1) + 3);
        if ( v58 != 2 )
        {
LABEL_102:
          _InterlockedAdd64((volatile signed __int64 *)(v40 + 8), v90);
          goto LABEL_72;
        }
      }
      v41 = KeGetPcr()->Prcb.Number << 12;
      *(_QWORD *)(v41 + *(_QWORD *)v40) += v90;
    }
  }
LABEL_72:
  v23 = 0xFFFFFFFFLL;
LABEL_73:
  v88 = v87 & 0x20;
  if ( v88 )
  {
    if ( (ReturnFlags & 1) == 0 )
      v109 = KfRaiseIrql(2u);
    LODWORD(v23) = KeGetPcr()->Prcb.Number;
    v85 = v23;
    *(_QWORD *)(ndisPcwOffsetToPerCpuData + ndisPcwPerCpuDataStride * (unsigned int)v23 + v97 + 344) = __rdtsc();
  }
  v42 = *(_QWORD *)(v3 + 2544);
  v43 = *(void (__fastcall **)(unsigned __int64, unsigned __int64, __int64))(v3 + 2640);
  v44 = *(_QWORD *)(v3 + 2528);
  if ( *(_BYTE *)v42 == 17 )
    goto LABEL_112;
  if ( (ReturnFlags & 1) != 0 || KeGetCurrentIrql() == 2 )
  {
    LODWORD(v23) = KeGetPcr()->Prcb.Number;
    p_LowLimit = &LowLimit;
    v100 = 0;
    LowLimit = (unsigned __int64)v6;
    HighLimit = (unsigned __int64)v6;
    v6->Scratch = 0;
    v6->ChildRefCount = ReturnFlags;
    while ( *(_BYTE *)v42 == 5 )
    {
      v60 = *p_LowLimit;
      if ( !*p_LowLimit )
        break;
      v61 = *(_QWORD *)(v42 + 424) + 96 * v23;
      if ( *(_BYTE *)(v61 + 88) )
      {
        *p_LowLimit = 0;
        do
        {
          v67 = ndisVerifierNdisDispatch;
          v68 = *(unsigned int *)(v60 + 132);
          v69 = *(_QWORD *)(v60 + 112);
          *(_DWORD *)(v60 + 132) = 0;
          if ( v67 && *(_BYTE *)v42 == 5 && *(_QWORD *)(v42 + 776) )
            (*((void (__fastcall **)(unsigned __int64, unsigned __int64, __int64))v67 + 17))(v44, v60, v68);
          else
            v43(v44, v60, v68);
          v60 = v69;
        }
        while ( v69 );
        break;
      }
      *(_BYTE *)(v61 + 88) = 1;
      v62 = v42;
      v63 = *p_LowLimit;
      *p_LowLimit = 0;
      if ( v63 )
      {
        do
        {
          v64 = ndisVerifierNdisDispatch;
          v65 = *(unsigned int *)(v63 + 132);
          v66 = *(_QWORD *)(v63 + 112);
          *(_DWORD *)(v63 + 132) = 0;
          if ( v64 && *(_BYTE *)v42 == 5 && *(_QWORD *)(v42 + 776) )
            (*((void (__fastcall **)(unsigned __int64, unsigned __int64, __int64))v64 + 17))(v44, v63, v65);
          else
            v43(v44, v63, v65);
          v63 = v66;
        }
        while ( v66 );
      }
      *(_BYTE *)(v61 + 88) = 0;
      p_LowLimit = (unsigned __int64 *)(v61 + 72);
      v42 = *(_QWORD *)(v42 + 552);
      v43 = *(void (__fastcall **)(unsigned __int64, unsigned __int64, __int64))(v62 + 528);
      v44 = *(_QWORD *)(v62 + 536);
    }
    v70 = *p_LowLimit;
    if ( *p_LowLimit )
    {
      *p_LowLimit = 0;
      do
      {
        v71 = ndisVerifierNdisDispatch;
        v72 = *(unsigned int *)(v70 + 132);
        v73 = *(_QWORD *)(v70 + 112);
        *(_DWORD *)(v70 + 132) = 0;
        if ( v71 && *(_BYTE *)v42 == 5 && *(_QWORD *)(v42 + 776) )
          (*((void (__fastcall **)(unsigned __int64, unsigned __int64, __int64))v71 + 17))(v44, v70, v72);
        else
          v43(v44, v70, v72);
        v70 = v73;
      }
      while ( v73 );
    }
LABEL_88:
    LODWORD(v23) = v85;
  }
  else
  {
    if ( *(_BYTE *)v3 == 5 )
    {
      v45 = (unsigned int)Size;
      LowLimit = 0;
      HighLimit = 0;
      v46 = KeGetPcr()->Prcb.Number << 12;
      v47 = *(_QWORD *)(v46 + qword_140122F78);
      LowLimit = v47;
      HighLimit = *(_QWORD *)(v46 + qword_140122F70);
      if ( (unsigned __int64)&retaddr >= HighLimit || v47 > (unsigned __int64)&retaddr )
      {
        IoGetStackLimits(&LowLimit, &HighLimit);
        v47 = LowLimit;
      }
      if ( (unsigned __int64)&retaddr - v47 >= v45 )
      {
        if ( ndisVerifierNdisDispatch && *(_BYTE *)v42 == 5 && *(_QWORD *)(v42 + 776) )
          (*((void (__fastcall **)(unsigned __int64, PNET_BUFFER_LIST, _QWORD))ndisVerifierNdisDispatch + 17))(
            v44,
            v6,
            ReturnFlags);
        else
          v43(v44, (unsigned __int64)v6, ReturnFlags);
      }
      else
      {
        v48 = 24576;
        v103 = ReturnFlags;
        v104 = 0;
        LowLimit = v42;
        HighLimit = v44;
        v100 = v43;
        v101 = v6;
        v102 = 0;
        if ( (unsigned int)Size > 0x6000 )
          v48 = Size;
        if ( KeExpandKernelStackAndCalloutEx(
               ndisDataPathExpandStackCallback<3,void (void *,_NET_BUFFER_LIST *,unsigned long)>,
               &LowLimit,
               v48,
               0,
               0) < 0 )
        {
          if ( *(_DWORD *)ndisNblTrackerMode )
            ndisNblTrackerTransferOwnershipInternal(
              v6,
              *(struct NDIS_NBL_TRACKER_HANDLE__ **)(v3 + 648),
              (struct NDIS_NBL_TRACKER_HANDLE__ *)0xA0,
              (enum _NDIS_NBL_TRACKER_OWNERSHIP_EVENT)1,
              0);
          v49 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 144));
          *(_QWORD *)(v3 + 152) = KeGetCurrentThread();
          v50 = (PNET_BUFFER_LIST *)(v3 + 280);
          for ( m = *(_QWORD **)(v3 + 280); m; m = (_QWORD *)*m )
            v50 = (PNET_BUFFER_LIST *)m;
          *v50 = v6;
          ndisQueueStackExpansionFallbackWorkItem((struct _NDIS_FILTER_BLOCK *)v3);
          *(_QWORD *)(v3 + 152) = 0;
          KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 144), v49);
        }
      }
      goto LABEL_88;
    }
LABEL_112:
    v43(v44, (unsigned __int64)v6, ReturnFlags);
  }
  if ( v88 )
  {
    if ( (_DWORD)v23 == -1 )
      LODWORD(v23) = KeGetPcr()->Prcb.Number;
    v52 = v97 + ndisPcwPerCpuDataStride * (unsigned int)v23 + ndisPcwOffsetToPerCpuData;
    v53 = __rdtsc();
    *(_QWORD *)(v52 + 144) += (((unsigned __int64)HIDWORD(v53) << 32) | (unsigned int)v53) - *(_QWORD *)(v52 + 344);
    *(_QWORD *)(v52 + 344) = 0;
    if ( v109 != 2 )
      KeLowerIrql(v109);
  }
LABEL_94:
  if ( (v91 & 0x10) != 0 )
  {
    v77 = v86;
    if ( v86 == -1 )
      v77 = KeGetPcr()->Prcb.Number;
    v78 = v95 + ndisPcwPerCpuDataStride * v77 + ndisPcwOffsetToPerCpuData;
    v79 = __rdtsc();
    *(_QWORD *)(v78 + 136) += (((unsigned __int64)HIDWORD(v79) << 32) | (unsigned int)v79) - *(_QWORD *)(v78 + 336);
    *(_QWORD *)(v78 + 336) = 0;
    if ( v84 != 2 )
      KeLowerIrql(v84);
  }
}

```

## disassembly

```asm
0x1400218a0  mov     [rsp+arg_10], r8d
0x1400218a5  mov     [rsp+arg_0], rcx
0x1400218aa  push    rbx
0x1400218ab  push    rbp
0x1400218ac  push    rsi
0x1400218ad  push    rdi
0x1400218ae  push    r12
0x1400218b0  push    r13
0x1400218b2  push    r14
0x1400218b4  sub     rsp, 0C0h
0x1400218bb  mov     rbp, [rcx+10h]
0x1400218bf  mov     rbx, rcx
0x1400218c2  xor     esi, esi
0x1400218c4  mov     [rsp+0F8h+LowLimit], rbp
0x1400218cc  mov     r13d, r8d
0x1400218cf  mov     r14, rdx
0x1400218d2  mov     ecx, [rbp+30h]
0x1400218d5  test    ecx, ecx
0x1400218d7  jnz     loc_140022279
0x1400218dd  mov     edi, esi
0x1400218df  mov     [rsp+0F8h+var_88], rsi
0x1400218e4  mov     r12d, esi
0x1400218e7  mov     dword ptr [rsp+0F8h+var_A0], esi
0x1400218eb  cmp     [rbp+50h], esi
0x1400218ee  jnz     loc_140022279
0x1400218f4  mov     eax, [rbx+0E0h]
0x1400218fa  mov     [rsp+0F8h+arg_8], r15
0x140021902  test    al, 1
0x140021904  jnz     loc_140021A24
0x14002190a  mov     eax, cs:?ndisNblContextVerifierMode@@3W4NDIS_NBL_CONTEXT_VERIFIER_MODE@@A; NDIS_NBL_CONTEXT_VERIFIER_MODE ndisNblContextVerifierMode
0x140021910  test    eax, eax
0x140021912  jnz     loc_140022244
0x140021918  test    edi, 180028h
0x14002191e  mov     r9d, 0FFFFFFFFh
0x140021924  mov     r11b, 2
0x140021927  mov     [rsp+0F8h+var_B0], r9d
0x14002192c  setz    cl
0x14002192f  mov     [rsp+0F8h+var_B8], r11b
0x140021934  test    r12b, 10h
0x140021938  setz    al
0x14002193b  test    al, cl
0x14002193d  jnz     loc_140021A84
0x140021943  test    r13b, 1
0x140021947  jnz     short loc_140021966
0x140021949  movzx   ecx, r11b; NewIrql
0x14002194d  call    cs:__imp_KfRaiseIrql
0x140021954  nop     dword ptr [rax+rax+00h]
0x140021959  mov     r9d, [rsp+0F8h+var_B0]
0x14002195e  movzx   r11d, al
0x140021962  mov     [rsp+0F8h+var_B8], al
0x140021966  mov     r10, [rsp+0F8h+var_88]
0x14002196b  test    dil, 8
0x14002196f  jz      short loc_140021998
0x140021971  mov     r9d, gs:1A4h
0x14002197a  mov     ecx, r9d
0x14002197d  imul    ecx, cs:?ndisPcwPerCpuDataStride@@3KA; ulong ndisPcwPerCpuDataStride
0x140021984  mov     r8d, cs:?ndisPcwOffsetToPerCpuData@@3KA; ulong ndisPcwOffsetToPerCpuData
0x14002198b  mov     [rsp+0F8h+var_B0], r9d
0x140021990  add     rcx, r10
0x140021993  inc     qword ptr [r8+rcx+18h]
0x140021998  test    r11b, r11b
0x14002199b  jz      loc_1400224FA
0x1400219a1  test    edi, 100020h
0x1400219a7  jz      short loc_1400219FD
0x1400219a9  mov     rax, r14
0x1400219ac  mov     r8d, esi
0x1400219af  test    r14, r14
0x1400219b2  jz      short loc_1400219BF
0x1400219b4  mov     rax, [rax]
0x1400219b7  inc     r8d
0x1400219ba  test    rax, rax
0x1400219bd  jnz     short loc_1400219B4
0x1400219bf  test    dil, 20h
0x1400219c3  jz      short loc_1400219F4
0x1400219c5  cmp     r9d, 0FFFFFFFFh
0x1400219c9  jnz     short loc_1400219D9
0x1400219cb  mov     r9d, gs:1A4h
0x1400219d4  mov     [rsp+0F8h+var_B0], r9d
0x1400219d9  mov     edx, cs:?ndisPcwOffsetToPerCpuData@@3KA; ulong ndisPcwOffsetToPerCpuData
0x1400219df  mov     ecx, r9d
0x1400219e2  imul    ecx, cs:?ndisPcwPerCpuDataStride@@3KA; ulong ndisPcwPerCpuDataStride
0x1400219e9  mov     eax, r8d
0x1400219ec  add     rcx, r10
0x1400219ef  add     [rcx+rdx+28h], rax
0x1400219f4  test    r11b, r11b
0x1400219f7  jz      loc_140022538
0x1400219fd  mov     eax, r12d
0x140021a00  and     eax, 10h
0x140021a03  mov     [rsp+0F8h+arg_18], eax
0x140021a0a  jnz     short loc_140021A4B
0x140021a0c  cmp     r11b, 2
0x140021a10  jz      short loc_140021A84
0x140021a12  movzx   ecx, r11b; NewIrql
0x140021a16  call    cs:__imp_KeLowerIrql
0x140021a1d  nop     dword ptr [rax+rax+00h]
0x140021a22  jmp     short loc_140021A84
0x140021a24  mov     r8, rbx; struct _NDIS_OBJECT_HEADER *
0x140021a27  mov     edx, r13d; unsigned int
0x140021a2a  mov     rcx, r14; struct _NET_BUFFER_LIST *
0x140021a2d  call    ?ndisNblVerifyRxCompletion@@YAXPEBU_NET_BUFFER_LIST@@KPEBU_NDIS_OBJECT_HEADER@@@Z; ndisNblVerifyRxCompletion(_NET_BUFFER_LIST const *,ulong,_NDIS_OBJECT_HEADER const *)
0x140021a32  mov     r15, r14
0x140021a35  test    r14, r14
0x140021a38  jz      loc_14002190A
0x140021a3e  movzx   r13d, cs:byte_140122DF0
0x140021a46  jmp     loc_1400EE572
0x140021a4b  cmp     r9d, 0FFFFFFFFh
0x140021a4f  jnz     short loc_140021A5F
0x140021a51  mov     r9d, gs:1A4h
0x140021a5a  mov     [rsp+0F8h+var_B0], r9d
0x140021a5f  rdtsc
0x140021a61  mov     r8d, cs:?ndisPcwOffsetToPerCpuData@@3KA; ulong ndisPcwOffsetToPerCpuData
0x140021a68  mov     ecx, r9d
0x140021a6b  imul    ecx, cs:?ndisPcwPerCpuDataStride@@3KA; ulong ndisPcwPerCpuDataStride
0x140021a72  shl     rdx, 20h
0x140021a76  or      rax, rdx
0x140021a79  add     rcx, r10
0x140021a7c  mov     [r8+rcx+150h], rax
0x140021a84  cmp     dword ptr [rbp+30h], 0
0x140021a88  jnz     loc_1400222A4
0x140021a8e  cmp     dword ptr [rbp+50h], 0
0x140021a92  mov     [rsp+0F8h+var_78], rsi
0x140021a9a  mov     [rsp+0F8h+var_AC], esi
0x140021a9e  jnz     loc_1400222A4
0x140021aa4  mov     rcx, r14
0x140021aa7  test    r14, r14
0x140021aaa  jz      short loc_140021AC6
0x140021aac  mov     eax, [rcx+88h]
0x140021ab2  and     eax, 0FFFFFFFCh
0x140021ab5  or      eax, 8
0x140021ab8  mov     [rcx+88h], eax
0x140021abe  mov     rcx, [rcx]
0x140021ac1  test    rcx, rcx
0x140021ac4  jnz     short loc_140021AAC
0x140021ac6  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x140021acc  test    eax, eax
0x140021ace  jnz     loc_1400224A9
0x140021ad4  cmp     cs:byte_140123720, al
0x140021ada  jnz     loc_1400224A9
0x140021ae0  cmp     dword ptr [rbp+0C98h], 0
0x140021ae7  jz      short loc_140021B67
0x140021ae9  mov     r12, rsi
0x140021aec  test    r14, r14
0x140021aef  jz      short loc_140021B64
0x140021af1  mov     rbx, rsi
0x140021af4  mov     r15, [r14]
0x140021af7  mov     [r14], rsi
0x140021afa  mov     rax, cs:PoolHandle
0x140021b01  cmp     [r14+20h], rax
0x140021b05  jnz     loc_140022697
0x140021b0b  lock dec dword ptr [rbp+0C98h]
0x140021b12  mov     rax, [r14+8]
0x140021b16  mov     rdi, [r14+68h]
0x140021b1a  mov     r13, [rax+8]
0x140021b1e  test    byte ptr [r13+0Ah], 20h
0x140021b23  jnz     loc_14002267F
0x140021b29  test    rdi, rdi
0x140021b2c  jz      loc_1400224E4
0x140021b32  mov     rdx, r13; Entry
0x140021b35  mov     rcx, rdi; Lookaside
0x140021b38  call    cs:__imp_ExFreeToNPagedLookasideList
0x140021b3f  nop     dword ptr [rax+rax+00h]
0x140021b44  mov     rcx, r14; NetBufferList
0x140021b47  call    NdisFreeNetBufferList
0x140021b4c  mov     r14, r15
0x140021b4f  test    r15, r15
0x140021b52  jnz     short loc_140021AF4
0x140021b54  mov     rbx, [rsp+0F8h+arg_0]
0x140021b5c  mov     r13d, [rsp+0F8h+arg_10]
0x140021b64  mov     r14, r12
0x140021b67  test    r14, r14
0x140021b6a  jz      loc_140021FB9
0x140021b70  mov     eax, cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x140021b76  mov     r12d, 0FFFFFFFFh
0x140021b7c  mov     [rsp+0F8h+var_B4], r12d
0x140021b81  mov     byte ptr [rsp+0F8h+arg_18], 2
0x140021b89  test    eax, eax
0x140021b8b  jz      loc_140021D6D
0x140021b91  mov     r10, [rbx+248h]
0x140021b98  xor     cl, cl
0x140021b9a  mov     rdi, [rbp+9E8h]
0x140021ba1  and     r13d, 1
0x140021ba5  mov     ebx, cs:?ndisNblTrackerEpoch@@3KA; ulong ndisNblTrackerEpoch
0x140021bab  mov     rdx, rsi
0x140021bae  mov     [rsp+0F8h+var_80], r10
0x140021bb3  mov     r9, rsi
0x140021bb6  mov     [rsp+0F8h+var_A8], rdx
0x140021bbb  mov     [rsp+0F8h+var_98], rsi
0x140021bc0  mov     [rsp+0F8h+var_90], rsi
0x140021bc5  mov     byte ptr [rsp+0F8h+arg_0], cl
0x140021bcc  cmp     eax, 3
0x140021bcf  jl      short loc_140021BF5
0x140021bd1  mov     r9, rdi; void *
0x140021bd4  mov     dword ptr [rsp+0F8h+Context], r13d; unsigned int
0x140021bd9  mov     r8d, 87h; unsigned int
0x140021bdf  mov     rdx, r10; struct NDIS_NBL_TRACKER_HANDLE__ *
0x140021be2  mov     rcx, r14; struct _NET_BUFFER_LIST *
0x140021be5  call    ?ndisNblTrackerRecordEventInternal@@YAXPEAU_NET_BUFFER_LIST@@PEAUNDIS_NBL_TRACKER_HANDLE__@@KPEAXK@Z; ndisNblTrackerRecordEventInternal(_NET_BUFFER_LIST *,NDIS_NBL_TRACKER_HANDLE__ *,ulong,void *,ulong)
0x140021bea  mov     r10, [rsp+0F8h+var_80]
0x140021bef  mov     rdx, rsi
0x140021bf2  mov     r9, rsi
0x140021bf5  mov     r15, rdi
0x140021bf8  and     r15, 0FFFFFFFFFFFFFFFDh
0x140021bfc  test    r15b, 1
0x140021c00  jz      loc_1400222F7
0x140021c06  mov     rax, rbx
0x140021c09  add     rax, rax
0x140021c0c  mov     rbx, rax
0x140021c0f  xor     rbx, rdi
0x140021c12  and     rbx, 0FFFFFFFFFFFFFFFDh
0x140021c16  xor     rbx, rax
0x140021c19  and     r15, 0FFFFFFFFFFFFFFF8h
0x140021c1d  mov     r15, [r15+18h]
0x140021c21  mov     r12, r14
0x140021c24  lea     r11, WPP_RECORDER_INITIALIZED
0x140021c2b  mov     rdi, [r12+168h]
0x140021c33  lea     rbp, WPP_78a33c75b2d2335d1cf1dcc315edf7b8_Traceguids
0x140021c3a  cmp     [r12+168h], rdi
0x140021c42  jnz     short loc_140021C9A
0x140021c44  test    rdi, rdi
0x140021c47  jz      loc_1400222FF
0x140021c4d  test    dil, 4
0x140021c51  jnz     loc_140022335
0x140021c57  mov     rcx, [r12+78h]
0x140021c5c  test    rcx, rcx
0x140021c5f  jz      loc_140022328
0x140021c65  movzx   r8d, byte ptr [rcx]
0x140021c69  lea     eax, [r8-11h]
0x140021c6d  cmp     al, 1
0x140021c6f  ja      loc_14002244A
0x140021c75  cmp     rcx, r15
0x140021c78  jz      loc_1400222D1
0x140021c7e  inc     rdx
0x140021c81  mov     rax, rbx
0x140021c84  mov     [rsp+0F8h+var_A8], rdx
0x140021c89  mov     [r12+168h], rax
0x140021c91  mov     r12, [r12]
0x140021c95  test    r12, r12
0x140021c98  jnz     short loc_140021C3A
0x140021c9a  movzx   ebp, byte ptr [rsp+0F8h+arg_0]
0x140021ca2  test    dil, 1
0x140021ca6  jz      short loc_140021CF6
0x140021ca8  mov     r9, [rsp+0F8h+var_98]
0x140021cad  sub     r9, rdx
0x140021cb0  mov     [rsp+0F8h+var_98], r9
0x140021cb5  jz      short loc_140021CF6
0x140021cb7  test    r13b, r13b
0x140021cba  jz      loc_140021FE2
0x140021cc0  mov     r8, rdi
0x140021cc3  and     rdi, 0FFFFFFFFFFFFFFF8h
0x140021cc7  shr     r8, 1
0x140021cca  and     r8d, 1
0x140021cce  add     r8, 3
0x140021cd2  shl     r8, 4
0x140021cd6  add     r8, rdi
0x140021cd9  test    r13b, r13b
0x140021cdc  jz      loc_140022034
0x140021ce2  mov     eax, gs:1A4h
0x140021cea  shl     eax, 0Ch
0x140021ced  mov     ecx, eax
0x140021cef  mov     rax, [r8]
0x140021cf2  add     [rcx+rax], r9
0x140021cf6  mov     r9, [rsp+0F8h+var_90]
0x140021cfb  mov     r10, [rsp+0F8h+var_80]
0x140021d00  mov     [rsp+0F8h+var_98], rdx
0x140021d05  test    r12, r12
0x140021d08  jnz     loc_140021C2B
0x140021d0e  mov     rbp, [rsp+0F8h+LowLimit]
0x140021d16  test    bl, 1
0x140021d19  jz      short loc_140021D68
0x140021d1b  sub     rdx, r9
0x140021d1e  mov     [rsp+0F8h+var_A8], rdx
0x140021d23  jz      short loc_140021D68
0x140021d25  test    r13b, r13b
0x140021d28  jz      loc_14002203E
0x140021d2e  mov     rdx, rbx
0x140021d31  and     rbx, 0FFFFFFFFFFFFFFF8h
0x140021d35  shr     rdx, 1
0x140021d38  and     edx, 1
0x140021d3b  add     rdx, 3
0x140021d3f  shl     rdx, 4
0x140021d43  add     rdx, rbx
0x140021d46  test    r13b, r13b
0x140021d49  jz      loc_140022078
0x140021d4f  mov     eax, gs:1A4h
0x140021d57  mov     r8, [rsp+0F8h+var_A8]
0x140021d5c  shl     eax, 0Ch
0x140021d5f  mov     ecx, eax
0x140021d61  mov     rax, [rdx]
0x140021d64  add     [rcx+rax], r8
0x140021d68  mov     r12d, [rsp+0F8h+var_B4]
0x140021d6d  mov     eax, [rsp+0F8h+var_AC]
0x140021d71  mov     ebx, [rsp+0F8h+arg_10]
0x140021d78  and     eax, 20h
0x140021d7b  and     ebx, 1
0x140021d7e  mov     [rsp+0F8h+var_AC], eax
0x140021d82  test    eax, eax
0x140021d84  jnz     loc_140022341
0x140021d8a  mov     r13, [rbp+9F0h]
0x140021d91  mov     rdi, [rbp+0A50h]
0x140021d98  mov     r15, [rbp+9E0h]
  ... truncated ...
```
