# ndisMTopReceiveNetBufferLists(void *,_NET_BUFFER_LIST *,ulong,ulong,ulong)

- ea: `0x14002afd0`
- end: `0x14002becf`
- name: `?ndisMTopReceiveNetBufferLists@@YAXPEAXPEAU_NET_BUFFER_LIST@@KKK@Z`
- size: `3839`
- prototype: `void(void *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1400110b0`
- `0x140011190`
- `0x1400231d0`
- `0x140023900`
- `0x140025d30`
- `0x1400260b0`
- `0x140029ce0`
- `0x14002a9a0`
- `0x14002aa30`
- `0x14002ab60`
- `0x14002ac10`
- `0x14002afd0`
- `0x14002bee0`
- `0x14002d620`
- `0x1400eb460`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x14002b887`
- `ntoskrnl!KeLowerIrql` at `0x14002b887`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002b2d4`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002b6a5`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002b7da`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002bc3b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002b2d4`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002b6a5`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002b7da`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002bc3b`
- `ntoskrnl!MmUnmapLockedPages` at `0x14002be39`
- `ntoskrnl!MmUnmapLockedPages` at `0x14002be39`
- `ntoskrnl!KfRaiseIrql` at `0x14002bbb6`
- `ntoskrnl!KfRaiseIrql` at `0x14002bbb6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002b4be`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002b4be`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14002bb19`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14002bb19`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b3d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002bc1c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b3d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002bc1c`
- `ntoskrnl!ExAllocatePool2` at `0x14002b2fd`
- `ntoskrnl!ExAllocatePool2` at `0x14002b2fd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002bb9c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002bb9c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002bb41`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002bb41`

## pseudocode

```c
void __fastcall ndisMTopReceiveNetBufferLists(
        char *a1,
        struct _NET_BUFFER_LIST *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5)
{
  struct _NET_BUFFER_LIST *v7; // r14
  char *v8; // r12
  unsigned int Number; // ebp
  struct _NDIS_RCV_TRACKER_ARRAY *v10; // r9
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 Pool2; // rsi
  _QWORD *v14; // r13
  struct _NET_BUFFER_LIST *v15; // rdx
  struct _NET_BUFFER_LIST *Alignment; // rcx
  struct _NDIS_OPEN_BLOCK *v17; // rbp
  __int64 v18; // r9
  struct _NET_BUFFER_LIST **v19; // rax
  struct _NDIS_OPEN_BLOCK *v20; // rdi
  unsigned int v21; // ebp
  unsigned int v22; // r14d
  struct _NDIS_OPEN_BLOCK *FilterNextOpen; // r15
  __int64 v24; // rbx
  __int64 v25; // rcx
  unsigned __int64 v26; // rdx
  struct _NDIS_OPEN_BLOCK *v27; // rbx
  unsigned int v28; // ebp
  unsigned int v29; // r15d
  unsigned int v30; // r13d
  int v31; // r14d
  struct _NDIS_OPEN_BLOCK *i; // rbx
  unsigned int j; // ebx
  __int64 v34; // rdx
  unsigned int v35; // ebx
  int v36; // edx
  __int64 v37; // rdi
  __int64 v38; // rax
  __int64 v39; // rcx
  unsigned __int64 v40; // rdx
  int v41; // r13d
  struct _NET_BUFFER_LIST *v42; // rcx
  struct _NET_BUFFER_LIST *v43; // r15
  _QWORD *p_Alignment; // r12
  struct _NET_BUFFER_LIST *v45; // rdi
  _NET_BUFFER *FirstNetBuffer; // rax
  struct _NPAGED_LOOKASIDE_LIST *v47; // rbx
  _MDL *CurrentMdl; // rbp
  __int64 v49; // rax
  unsigned int v50; // r12d
  unsigned __int64 v51; // rdx
  __int64 v52; // r10
  __int64 v53; // rbx
  unsigned __int64 v54; // rdi
  __int64 v55; // rbp
  unsigned __int64 v56; // r8
  unsigned __int64 v57; // rbx
  _SLIST_HEADER *v58; // r15
  unsigned __int64 Region; // rdi
  char *v60; // rcx
  char v61; // r9
  unsigned __int64 v62; // r10
  __int64 v63; // rcx
  unsigned __int64 v64; // rbp
  unsigned __int64 v65; // rdx
  __int64 v66; // rcx
  int v67; // r13d
  __int64 v68; // r15
  void (__fastcall *v69)(struct _NET_BUFFER_LIST *, struct _NET_BUFFER_LIST *, __int64); // rdi
  struct _NET_BUFFER_LIST *v70; // rbp
  __int64 v71; // r8
  unsigned __int64 v72; // rax
  struct _NET_BUFFER_LIST **p_Parameter; // rbx
  struct _NET_BUFFER_LIST *v74; // rdx
  __int64 v75; // r14
  __int64 v76; // r13
  struct _NET_BUFFER_LIST *v77; // rdx
  struct _VF_NDIS_DISPATCH_TABLE *v78; // rax
  __int64 v79; // r8
  struct _NET_BUFFER_LIST *v80; // rbx
  struct _VF_NDIS_DISPATCH_TABLE *v81; // rax
  __int64 ChildRefCount; // r8
  struct _NET_BUFFER_LIST *Scratch; // r14
  struct _NET_BUFFER_LIST *v84; // rdx
  struct _VF_NDIS_DISPATCH_TABLE *v85; // rax
  __int64 v86; // r8
  struct _NET_BUFFER_LIST *v87; // rbx
  unsigned int v88; // r15d
  struct _NDIS_OPEN_BLOCK *v89; // r14
  __int64 v90; // rdi
  __int64 v91; // rcx
  unsigned __int64 v92; // rdx
  int v93; // ecx
  KIRQL v94; // di
  struct _NET_BUFFER_LIST **p_Next; // rcx
  struct _NET_BUFFER_LIST *k; // rdx
  unsigned __int64 v97; // rdx
  unsigned __int64 v98; // rdi
  __int64 v99; // rdx
  PVOID Context; // [rsp+20h] [rbp-C8h]
  char v101; // [rsp+40h] [rbp-A8h]
  KIRQL v102; // [rsp+41h] [rbp-A7h]
  char v103; // [rsp+42h] [rbp-A6h]
  unsigned int v104; // [rsp+44h] [rbp-A4h]
  char v105; // [rsp+48h] [rbp-A0h]
  __int64 v106; // [rsp+50h] [rbp-98h]
  struct _NET_BUFFER_LIST **v107; // [rsp+58h] [rbp-90h]
  __int64 v108; // [rsp+58h] [rbp-90h]
  unsigned int v109; // [rsp+60h] [rbp-88h]
  unsigned __int64 v110; // [rsp+68h] [rbp-80h]
  __int64 v111; // [rsp+70h] [rbp-78h]
  unsigned __int64 v112; // [rsp+70h] [rbp-78h]
  struct _NET_BUFFER_LIST *Parameter; // [rsp+80h] [rbp-68h] BYREF
  struct _NET_BUFFER_LIST *v114; // [rsp+88h] [rbp-60h]
  void (__fastcall *v115)(struct _NET_BUFFER_LIST *, struct _NET_BUFFER_LIST *, __int64); // [rsp+90h] [rbp-58h]
  struct _NET_BUFFER_LIST *v116; // [rsp+98h] [rbp-50h]
  __int64 v117; // [rsp+A0h] [rbp-48h]
  int v118; // [rsp+A8h] [rbp-40h]
  int v119; // [rsp+ACh] [rbp-3Ch]
  unsigned int v121; // [rsp+F0h] [rbp+8h]
  char v122; // [rsp+F8h] [rbp+10h]
  int v123; // [rsp+F8h] [rbp+10h]

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
  v109 = 0;
  v104 = a5 & 1;
  if ( (a5 & 1) != 0 || KeGetCurrentIrql() == 2 )
  {
    if ( ndisPerProcRcvTrackers )
    {
      Number = KeGetPcr()->Prcb.Number;
      v10 = ndisPerProcRcvTrackers;
      v11 = 2096LL * Number;
      v109 = Number;
      v12 = *(unsigned int *)((char *)ndisPerProcRcvTrackers + v11);
      if ( (unsigned int)v12 < 3 )
      {
        v103 = 1;
        *(_DWORD *)((char *)ndisPerProcRcvTrackers + v11) = v12 + 1;
        Pool2 = (__int64)v10 + 696 * v12 + v11 + 8;
LABEL_7:
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
          ndisMIndicateNetBufferListsToOpen(v17, (unsigned __int64)v7, a3, a4, a5);
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
              v107 = v19;
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
                    v26 = *(_QWORD *)(Pool2 + 40 * v24 + 64);
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
                  v88 = v29 | 2;
                  do
                  {
                    v89 = v27->FilterNextOpen;
                    v90 = 0;
                    do
                    {
                      v91 = (unsigned int)v90;
                      v92 = *(_QWORD *)(Pool2 + 40 * v90 + 64);
                      v90 = (unsigned int)(v90 + 1);
                      if ( v92 )
                        ndisMIndicateNetBufferListsToOpen(
                          v27,
                          v92,
                          *(_DWORD *)(Pool2 + 40),
                          *(_DWORD *)(Pool2 + 40 * v91 + 80),
                          v88);
                    }
                    while ( (unsigned int)v90 <= v28 );
                    v27 = v89;
                  }
                  while ( v89 );
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
                          v40 = *(_QWORD *)(Pool2 + 40 * v37 + 64);
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
                      *(_QWORD *)(Pool2 + 40 * v34 + 64),
                      v30,
                      *(_DWORD *)(Pool2 + 40 * v34 + 80),
                      v29);
                  }
                }
              }
              v19 = v107;
            }
          }
        }
        if ( !*(_BYTE *)(Pool2 + 692) )
          goto LABEL_38;
        v7 = *v19;
        v35 = a5 & 2;
        goto LABEL_37;
      }
    }
  }
  v103 = 0;
  Pool2 = ExAllocatePool2(66, 696, 538985550);
  if ( Pool2 )
    goto LABEL_7;
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
LABEL_37:
  if ( !v7 )
    goto LABEL_38;
  if ( byte_140123720 && (*((_DWORD *)v8 + 1468) & 2) != 0 )
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
  if ( *((_DWORD *)v8 + 12) || (LOBYTE(v41) = 0, v108 = 0, v105 = 0, *((_DWORD *)v8 + 20)) )
  {
    v41 = *((_DWORD *)v8 + 20);
    v105 = v41;
    v108 = *((_QWORD *)v8 + 5);
    if ( !v108 )
      v108 = *((_QWORD *)v8 + 5);
  }
  v42 = v7;
  do
  {
    v42->Flags = v42->Flags & 0xFFFFFFF4 | 8;
    v42 = (struct _NET_BUFFER_LIST *)v42->Link.Alignment;
  }
  while ( v42 );
  if ( Microsoft_Windows_Networking_CorrelationEnabled
    || byte_140123720 != (_BYTE)Microsoft_Windows_Networking_CorrelationEnabled )
  {
    ndisMarkNetBufferListCorrelationIdsAsUsed(v7);
  }
  if ( *((_DWORD *)v8 + 806) )
  {
    v43 = 0;
    p_Alignment = 0;
    do
    {
      v45 = (struct _NET_BUFFER_LIST *)v7->Link.Alignment;
      v7->Link.Alignment = 0;
      if ( v7->NdisPoolHandle == PoolHandle )
      {
        _InterlockedDecrement((volatile signed __int32 *)a1 + 806);
        FirstNetBuffer = v7->FirstNetBuffer;
        v47 = (struct _NPAGED_LOOKASIDE_LIST *)v7->MiniportReserved[1];
        CurrentMdl = FirstNetBuffer->CurrentMdl;
        if ( (CurrentMdl->MdlFlags & 0x20) != 0 )
          MmUnmapLockedPages(CurrentMdl->MappedSystemVa, FirstNetBuffer->CurrentMdl);
        if ( v47 )
          ExFreeToNPagedLookasideList(v47, CurrentMdl);
        else
          ExFreePoolWithTag(CurrentMdl, 0);
        NdisFreeNetBufferList(v7);
      }
      else
      {
        if ( v43 )
          *p_Alignment = v7;
        else
          v43 = v7;
        p_Alignment = &v7->Link.Alignment;
      }
      v7 = v45;
    }
    while ( v45 );
    LOBYTE(v41) = v105;
    if ( !v43 )
      goto LABEL_38;
    v7 = v43;
  }
  v49 = *(unsigned int *)ndisNblTrackerMode;
  v50 = -1;
  v102 = 2;
  if ( !*(_DWORD *)ndisNblTrackerMode )
    goto LABEL_108;
  LODWORD(v51) = a5 & 1;
  v52 = 0;
  v53 = ndisNblTrackerEpoch;
  v111 = 0;
  v54 = *((_QWORD *)a1 + 317);
  v55 = 0;
  v106 = 0;
  v122 = a5 & 1;
  v101 = 0;
  if ( *(int *)ndisNblTrackerMode >= 3 )
  {
    ndisNblTrackerRecordEventInternal(v7, 0, 0x87u, (void *)v54, v104);
    v52 = 0;
  }
  v56 = v54 & 0xFFFFFFFFFFFFFFFDuLL;
  v110 = v54 & 0xFFFFFFFFFFFFFFFDuLL;
  if ( (v54 & 1) != 0 )
  {
    v49 = 2 * v53;
    v57 = (2 * v53) ^ (v54 ^ (2 * v53)) & 0xFFFFFFFFFFFFFFFDuLL;
    v56 = *(_QWORD *)((v54 & 0xFFFFFFFFFFFFFFF8uLL) + 24);
    v110 = v56;
  }
  else
  {
    v57 = v54 & 0xFFFFFFFFFFFFFFFDuLL;
  }
  v58 = (_SLIST_HEADER *)v7;
  do
  {
    Region = v58[22].Region;
    while ( v58[22].Region == Region )
    {
      if ( Region )
      {
        if ( (Region & 4) != 0 )
          goto LABEL_173;
      }
      else if ( !v58[7].Region )
      {
        v58[7].Region = 0;
      }
      v60 = (char *)v58[7].Region;
      if ( v60 )
      {
        LODWORD(v51) = (unsigned __int8)*v60;
        if ( (unsigned __int8)(v51 - 17) <= 1u || (_BYTE)v51 == 5 )
        {
          if ( v60 != (char *)v56 || v58[1].Region )
          {
            ++v55;
            v49 = v57;
          }
          else
          {
            ++v52;
            v49 = 24;
            v106 = v52;
            ++v55;
          }
          goto LABEL_89;
        }
        if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v51) = 3;
          WPP_RECORDER_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            v51,
            27,
            12,
            (struct _GUID *)&WPP_78a33c75b2d2335d1cf1dcc315edf7b8_Traceguids,
            (char)v58,
            *v60);
LABEL_198:
          v56 = v110;
          v52 = v106;
        }
      }
      else if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v51) = 3;
        WPP_RECORDER_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          v51,
          27,
          11,
          (struct _GUID *)&WPP_78a33c75b2d2335d1cf1dcc315edf7b8_Traceguids,
          (char)v58);
        goto LABEL_198;
      }
LABEL_173:
      v49 = v57 | 4;
LABEL_89:
      v58[22].Region = v49;
      v58 = (_SLIST_HEADER *)v58->Alignment;
      if ( !v58 )
        break;
    }
    v61 = v122;
    if ( (Region & 1) == 0 )
      goto LABEL_95;
    v62 = v111 - v55;
    v112 = v111 - v55;
    if ( !v112 )
      goto LABEL_95;
    if ( v122 || v101 )
    {
      v51 = (Region & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((Region >> 1) & 1) + 3);
      if ( !v122 )
        goto LABEL_165;
      goto LABEL_94;
    }
    v101 = 1;
    LOBYTE(v49) = KeGetCurrentIrql();
    v56 = v110;
    v97 = Region;
    v62 = v112;
    v98 = Region & 0xFFFFFFFFFFFFFFF8uLL;
    v99 = 16 * (((v97 >> 1) & 1) + 3);
    if ( (_BYTE)v49 == 2 )
    {
      v61 = 1;
      v51 = v98 + v99;
      v122 = 1;
LABEL_94:
      v63 = KeGetPcr()->Prcb.Number << 12;
      v49 = *(_QWORD *)v51;
      *(_QWORD *)(v63 + *(_QWORD *)v51) += v62;
      goto LABEL_95;
    }
    v61 = 0;
    v122 = 0;
    v51 = v98 + v99;
LABEL_165:
    _InterlockedAdd64((volatile signed __int64 *)(v51 + 8), v62);
LABEL_95:
    v52 = v106;
    v111 = v55;
  }
  while ( v58 );
  v50 = -1;
  LOBYTE(v41) = v105;
  if ( (v57 & 1) != 0 )
  {
    v64 = v55 - v106;
    if ( v64 )
    {
      if ( v61 || v101 )
      {
        v65 = (v57 & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((v57 >> 1) & 1) + 3);
        if ( v61 )
          goto LABEL_107;
LABEL_101:
        _InterlockedAdd64((volatile signed __int64 *)(v65 + 8), v64);
      }
      else
      {
        LOBYTE(v49) = KeGetCurrentIrql();
        v65 = (v57 & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((v57 >> 1) & 1) + 3);
        if ( (_BYTE)v49 != 2 )
          goto LABEL_101;
LABEL_107:
        v66 = KeGetPcr()->Prcb.Number << 12;
        v49 = *(_QWORD *)v65;
        *(_QWORD *)(v66 + *(_QWORD *)v65) += v64;
      }
    }
  }
LABEL_108:
  v67 = v41 & 0x20;
  v123 = v67;
  if ( v67 )
  {
    if ( (a5 & 1) == 0 )
      v102 = KfRaiseIrql(2u);
    v50 = KeGetPcr()->Prcb.Number;
    v49 = __rdtsc();
    *(_QWORD *)(ndisPcwOffsetToPerCpuData + ndisPcwPerCpuDataStride * v50 + v108 + 344) = v49;
  }
  v68 = *((_QWORD *)a1 + 318);
  v69 = (void (__fastcall *)(struct _NET_BUFFER_LIST *, struct _NET_BUFFER_LIST *, __int64))*((_QWORD *)a1 + 330);
  v70 = (struct _NET_BUFFER_LIST *)*((_QWORD *)a1 + 316);
  if ( *(_BYTE *)v68 == 17 )
    goto LABEL_115;
  if ( (a5 & 1) != 0 || KeGetCurrentIrql() == 2 )
  {
    LODWORD(v49) = KeGetPcr()->Prcb.Number;
    p_Parameter = &Parameter;
    v121 = v49;
    v115 = 0;
    Parameter = v7;
    v114 = v7;
    v7->Scratch = 0;
    v7->ChildRefCount = v104;
    while ( *(_BYTE *)v68 == 5 )
    {
      v74 = *p_Parameter;
      if ( !*p_Parameter )
        break;
      v75 = *(_QWORD *)(v68 + 424) + 96 * v49;
      if ( *(_BYTE *)(v75 + 88) )
      {
        *p_Parameter = 0;
        do
        {
          v81 = ndisVerifierNdisDispatch;
          ChildRefCount = (unsigned int)v74->ChildRefCount;
          Scratch = (struct _NET_BUFFER_LIST *)v74->Scratch;
          v74->ChildRefCount = 0;
          if ( v81 && *(_BYTE *)v68 == 5 && *(_QWORD *)(v68 + 776) )
            (*((void (__fastcall **)(struct _NET_BUFFER_LIST *, struct _NET_BUFFER_LIST *, __int64))v81 + 17))(
              v70,
              v74,
              ChildRefCount);
          else
            v69(v70, v74, ChildRefCount);
          v74 = Scratch;
        }
        while ( Scratch );
        break;
      }
      *(_BYTE *)(v75 + 88) = 1;
      v76 = v68;
      v77 = *p_Parameter;
      *p_Parameter = 0;
      if ( v77 )
      {
        do
        {
          v78 = ndisVerifierNdisDispatch;
          v79 = (unsigned int)v77->ChildRefCount;
          v80 = (struct _NET_BUFFER_LIST *)v77->Scratch;
          v77->ChildRefCount = 0;
          if ( v78 && *(_BYTE *)v68 == 5 && *(_QWORD *)(v68 + 776) )
            (*((void (__fastcall **)(struct _NET_BUFFER_LIST *, struct _NET_BUFFER_LIST *, __int64))v78 + 17))(
              v70,
              v77,
              v79);
          else
            v69(v70, v77, v79);
          v77 = v80;
        }
        while ( v80 );
      }
      v49 = v121;
      p_Parameter = (struct _NET_BUFFER_LIST **)(v75 + 72);
      *(_BYTE *)(v75 + 88) = 0;
      v68 = *(_QWORD *)(v68 + 552);
      v69 = *(void (__fastcall **)(struct _NET_BUFFER_LIST *, struct _NET_BUFFER_LIST *, __int64))(v76 + 528);
      v70 = *(struct _NET_BUFFER_LIST **)(v76 + 536);
    }
    v84 = *p_Parameter;
    if ( *p_Parameter )
    {
      *p_Parameter = 0;
      do
      {
        v85 = ndisVerifierNdisDispatch;
        v86 = (unsigned int)v84->ChildRefCount;
        v87 = (struct _NET_BUFFER_LIST *)v84->Scratch;
        v84->ChildRefCount = 0;
        if ( v85 && *(_BYTE *)v68 == 5 && *(_QWORD *)(v68 + 776) )
          (*((void (__fastcall **)(struct _NET_BUFFER_LIST *, struct _NET_BUFFER_LIST *, __int64))v85 + 17))(
            v70,
            v84,
            v86);
        else
          v69(v70, v84, v86);
        v84 = v87;
      }
      while ( v87 );
    }
    v67 = v123;
  }
  else
  {
    if ( *a1 != 5 )
      goto LABEL_115;
    if ( ndisIsLwfGuaranteedStackSpaceAvailable() )
    {
      if ( ndisVerifierNdisDispatch && *(_BYTE *)v68 == 5 && *(_QWORD *)(v68 + 776) )
      {
        (*((void (__fastcall **)(struct _NET_BUFFER_LIST *, struct _NET_BUFFER_LIST *, _QWORD))ndisVerifierNdisDispatch
         + 17))(
          v70,
          v7,
          0);
        goto LABEL_116;
      }
LABEL_115:
      v69(v70, v7, a5 & 1);
    }
    else
    {
      v93 = 24576;
      v118 = 0;
      v119 = 0;
      Parameter = (struct _NET_BUFFER_LIST *)v68;
      v114 = v70;
      v115 = v69;
      v116 = v7;
      v117 = 0;
      if ( (unsigned int)Size > 0x6000 )
        v93 = Size;
      if ( KeExpandKernelStackAndCalloutEx(
             ndisDataPathExpandStackCallback<3,void (void *,_NET_BUFFER_LIST *,unsigned long)>,
             &Parameter,
             v93,
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
        v94 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 18);
        *((_QWORD *)a1 + 19) = KeGetCurrentThread();
        p_Next = (struct _NET_BUFFER_LIST **)(a1 + 280);
        for ( k = (struct _NET_BUFFER_LIST *)*((_QWORD *)a1 + 35); k; k = (struct _NET_BUFFER_LIST *)k->Link.Alignment )
          p_Next = &k->Next;
        *p_Next = v7;
        ndisQueueStackExpansionFallbackWorkItem((struct _NDIS_FILTER_BLOCK *)a1);
        *((_QWORD *)a1 + 19) = 0;
        KeReleaseSpinLock((PKSPIN_LOCK)a1 + 18, v94);
      }
    }
  }
LABEL_116:
  if ( v67 )
  {
    if ( v50 == -1 )
      v50 = KeGetPcr()->Prcb.Number;
    v71 = v108 + ndisPcwPerCpuDataStride * v50 + ndisPcwOffsetToPerCpuData;
    v72 = __rdtsc();
    *(_QWORD *)(v71 + 144) += (((unsigned __int64)HIDWORD(v72) << 32) | (unsigned int)v72) - *(_QWORD *)(v71 + 344);
    *(_QWORD *)(v71 + 344) = 0;
    if ( v102 != 2 )
      KeLowerIrql(v102);
  }
LABEL_38:
  if ( v103 )
  {
    --*((_DWORD *)ndisPerProcRcvTrackers + 524 * v109);
  }
  else if ( Pool2 )
  {
    ExFreePoolWithTag((PVOID)Pool2, 0);
  }
}

```

## disassembly

```asm
0x14002afd0  mov     rax, rsp
0x14002afd3  mov     [rax+8], rcx
0x14002afd7  push    rdi
0x14002afd8  push    r12
0x14002afda  push    r14
0x14002afdc  push    r15
0x14002afde  sub     rsp, 0C8h
0x14002afe5  test    dword ptr [rdx+80h], 8000h
0x14002afef  mov     edi, r9d
0x14002aff2  mov     r15d, r8d
0x14002aff5  mov     r14, rdx
0x14002aff8  mov     r12, rcx
0x14002affb  jnz     loc_14002B241
0x14002b001  cmp     byte ptr [rcx+0A69h], 0
0x14002b008  jz      loc_14002B39D
0x14002b00e  mov     [rax+18h], rbx
0x14002b012  mov     ebx, [rsp+0E8h+arg_20]
0x14002b019  mov     [rax-28h], rbp
0x14002b01d  lea     rbp, WPP_RECORDER_INITIALIZED
0x14002b024  mov     [rax-30h], rsi
0x14002b028  mov     [rax-38h], r13
0x14002b02c  mov     eax, ebx
0x14002b02e  and     eax, 1
0x14002b031  mov     [rsp+0E8h+var_88], 0
0x14002b039  mov     [rsp+0E8h+var_A4], eax
0x14002b03d  jz      loc_14002B2D4
0x14002b043  cmp     cs:?ndisPerProcRcvTrackers@@3PEAU_NDIS_RCV_TRACKER_ARRAY@@EA, 0; _NDIS_RCV_TRACKER_ARRAY * ndisPerProcRcvTrackers
0x14002b04b  jz      loc_14002B2E8
0x14002b051  mov     ebp, gs:1A4h
0x14002b059  mov     r9, cs:?ndisPerProcRcvTrackers@@3PEAU_NDIS_RCV_TRACKER_ARRAY@@EA; _NDIS_RCV_TRACKER_ARRAY * ndisPerProcRcvTrackers
0x14002b060  mov     eax, ebp
0x14002b062  imul    r8, rax, 830h
0x14002b069  mov     [rsp+0E8h+var_88], ebp
0x14002b06d  mov     edx, [r8+r9]
0x14002b071  cmp     edx, 3
0x14002b074  jnb     loc_14002BBFE
0x14002b07a  imul    rsi, rdx, 2B8h
0x14002b081  lea     eax, [rdx+1]
0x14002b084  mov     [rsp+0E8h+var_A6], 1
0x14002b089  add     rsi, 8
0x14002b08d  mov     [r8+r9], eax
0x14002b091  add     rsi, r8
0x14002b094  add     rsi, r9
0x14002b097  mov     r13, [r12+190h]
0x14002b09f  xor     edx, edx
0x14002b0a1  mov     eax, ebx
0x14002b0a3  mov     [rsi+2B4h], dl
0x14002b0a9  and     eax, 2
0x14002b0ac  mov     rcx, r14
0x14002b0af  mov     [rsp+0E8h+arg_8], eax
0x14002b0b6  jz      loc_14002BE10
0x14002b0bc  mov     rbp, [r13+148h]
0x14002b0c3  test    rbp, rbp
0x14002b0c6  jnz     loc_14002B363
0x14002b0cc  mov     rcx, rsi; struct _NDIS_NBL_RCV_TRACKER *
0x14002b0cf  mov     [rsi+18h], r14
0x14002b0d3  mov     [rsi+8], r13
0x14002b0d7  mov     [rsi+10h], ebx
0x14002b0da  mov     [rsi], r12
0x14002b0dd  mov     [rsi+20h], rdx
0x14002b0e1  mov     [rsi+28h], r15d
0x14002b0e5  mov     [rsi+2Ch], edi
0x14002b0e8  call    ?ndisSortNetBufferLists@@YAXPEAU_NDIS_NBL_RCV_TRACKER@@@Z; ndisSortNetBufferLists(_NDIS_NBL_RCV_TRACKER *)
0x14002b0ed  cmp     qword ptr [rsi+40h], 0
0x14002b0f2  lea     rax, [rsi+40h]
0x14002b0f6  jnz     short loc_14002B105
0x14002b0f8  cmp     dword ptr [rsi+2B0h], 0
0x14002b0ff  jz      loc_14002B22C
0x14002b105  cmp     qword ptr [r13+0], 0
0x14002b10a  jnz     loc_14002B6DB
0x14002b110  mov     byte ptr [rsi+2B4h], 1
0x14002b117  test    rbp, rbp
0x14002b11a  jnz     loc_14002B22C
0x14002b120  mov     rdi, [r13+8]
0x14002b124  mov     [rsp+0E8h+var_90], rax
0x14002b129  test    rdi, rdi
0x14002b12c  jz      short loc_14002B181
0x14002b12e  mov     r14d, [rsi+10h]
0x14002b132  mov     ebp, [rsi+2B0h]
0x14002b138  or      r14d, 2
0x14002b13c  nop     dword ptr [rax+00h]
0x14002b140  mov     r15, [rdi+1A8h]
0x14002b147  xor     ebx, ebx
0x14002b149  lea     rax, [rbx+rbx*4]
0x14002b14d  mov     ecx, ebx
0x14002b14f  mov     rdx, [rsi+rax*8+40h]; struct _NET_BUFFER_LIST *
0x14002b154  inc     ebx
0x14002b156  test    rdx, rdx
0x14002b159  jz      short loc_14002B175
0x14002b15b  mov     r8d, [rsi+28h]; unsigned int
0x14002b15f  lea     r9, [rcx+rcx*4]
0x14002b163  mov     r9d, [rsi+r9*8+50h]; unsigned int
0x14002b168  mov     rcx, rdi; struct _NDIS_OPEN_BLOCK *
0x14002b16b  mov     dword ptr [rsp+0E8h+Context], r14d; unsigned int
0x14002b170  call    ?ndisMIndicateNetBufferListsToOpen@@YAXPEAU_NDIS_OPEN_BLOCK@@PEAU_NET_BUFFER_LIST@@KKK@Z; ndisMIndicateNetBufferListsToOpen(_NDIS_OPEN_BLOCK *,_NET_BUFFER_LIST *,ulong,ulong,ulong)
0x14002b175  cmp     ebx, ebp
0x14002b177  jbe     short loc_14002B149
0x14002b179  mov     rdi, r15
0x14002b17c  test    r15, r15
0x14002b17f  jnz     short loc_14002B140
0x14002b181  mov     rbx, [r13+10h]
0x14002b185  test    rbx, rbx
0x14002b188  jz      loc_14002B227
0x14002b18e  cmp     [rsp+0E8h+arg_8], 0
0x14002b196  mov     ebp, [rsi+2B0h]
0x14002b19c  mov     r15d, [rsi+10h]
0x14002b1a0  jnz     loc_14002BA51
0x14002b1a6  mov     rax, [rsi]
0x14002b1a9  mov     r13d, [rsi+28h]
0x14002b1ad  mov     r14d, [rax+8C4h]
0x14002b1b4  test    r14d, r14d
0x14002b1b7  jz      short loc_14002B1F2
0x14002b1b9  mov     rax, [rsi+8]
0x14002b1bd  mov     r12d, r15d
0x14002b1c0  or      r12d, 2
0x14002b1c4  mov     rbx, [rax+10h]
0x14002b1c8  test    rbx, rbx
0x14002b1cb  jz      short loc_14002B1EA
0x14002b1cd  nop     dword ptr [rax]
0x14002b1d0  mov     eax, [rbx+0E0h]
0x14002b1d6  test    al, 4
0x14002b1d8  jnz     loc_14002B31A
0x14002b1de  mov     rbx, [rbx+1A8h]
0x14002b1e5  test    rbx, rbx
0x14002b1e8  jnz     short loc_14002B1D0
0x14002b1ea  mov     r12, [rsp+0E8h+arg_0]
0x14002b1f2  mov     ebx, 1
0x14002b1f7  cmp     ebp, ebx
0x14002b1f9  jb      short loc_14002B227
0x14002b1fb  mov     edx, ebx
0x14002b1fd  mov     r8d, r13d; unsigned int
0x14002b200  inc     ebx
0x14002b202  mov     dword ptr [rsp+0E8h+Context], r15d; unsigned int
0x14002b207  lea     rax, [rdx+rdx*4]
0x14002b20b  mov     rcx, [rsi+rax*8+38h]; struct _NDIS_OPEN_BLOCK *
0x14002b210  lea     r9, [rdx+rdx*4]
0x14002b214  mov     r9d, [rsi+r9*8+50h]; unsigned int
0x14002b219  mov     rdx, [rsi+rax*8+40h]; struct _NET_BUFFER_LIST *
0x14002b21e  call    ?ndisMIndicateNetBufferListsToOpen@@YAXPEAU_NDIS_OPEN_BLOCK@@PEAU_NET_BUFFER_LIST@@KKK@Z; ndisMIndicateNetBufferListsToOpen(_NDIS_OPEN_BLOCK *,_NET_BUFFER_LIST *,ulong,ulong,ulong)
0x14002b223  cmp     ebx, ebp
0x14002b225  jbe     short loc_14002B1FB
0x14002b227  mov     rax, [rsp+0E8h+var_90]
0x14002b22c  cmp     byte ptr [rsi+2B4h], 0
0x14002b233  jz      short loc_14002B284
0x14002b235  mov     r14, [rax]
0x14002b238  mov     ebx, [rsp+0E8h+arg_8]
0x14002b23f  jmp     short loc_14002B27B
0x14002b241  mov     edx, [rsp+0E8h+arg_20]
0x14002b248  mov     rax, [rcx+860h]
0x14002b24f  mov     dword ptr [rsp+0E8h+Context], edx
0x14002b253  mov     rdx, r14
0x14002b256  call    _guard_dispatch_icall
0x14002b25b  add     rsp, 0C8h
0x14002b262  pop     r15
0x14002b264  pop     r14
0x14002b266  pop     r12
0x14002b268  pop     rdi
0x14002b269  retn
0x14002b26b  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14002b272  jnz     loc_14002B6F5
0x14002b278  and     ebx, 2
0x14002b27b  test    r14, r14
0x14002b27e  jnz     loc_14002B3E6
0x14002b284  cmp     [rsp+0E8h+var_A6], 0
0x14002b289  mov     r13, [rsp+0E8h+var_38]
0x14002b291  mov     rbp, [rsp+0E8h+var_28]
0x14002b299  mov     rbx, [rsp+0E8h+arg_10]
0x14002b2a1  jz      loc_14002B3C7
0x14002b2a7  mov     eax, [rsp+0E8h+var_88]
0x14002b2ab  imul    rcx, rax, 830h
0x14002b2b2  mov     rax, cs:?ndisPerProcRcvTrackers@@3PEAU_NDIS_RCV_TRACKER_ARRAY@@EA; _NDIS_RCV_TRACKER_ARRAY * ndisPerProcRcvTrackers
0x14002b2b9  dec     dword ptr [rcx+rax]
0x14002b2bc  mov     rsi, [rsp+0E8h+var_30]
0x14002b2c4  add     rsp, 0C8h
0x14002b2cb  pop     r15
0x14002b2cd  pop     r14
0x14002b2cf  pop     r12
0x14002b2d1  pop     rdi
0x14002b2d2  retn
0x14002b2d4  call    cs:__imp_KeGetCurrentIrql
0x14002b2db  nop     dword ptr [rax+rax+00h]
0x14002b2e0  cmp     al, 2
0x14002b2e2  jz      loc_14002B043
0x14002b2e8  mov     edx, 2B8h
0x14002b2ed  mov     [rsp+0E8h+var_A6], 0
0x14002b2f2  mov     ecx, 42h ; 'B'
0x14002b2f7  mov     r8d, 2020444Eh
0x14002b2fd  call    cs:__imp_ExAllocatePool2
0x14002b304  nop     dword ptr [rax+rax+00h]
0x14002b309  mov     rsi, rax
0x14002b30c  test    rax, rax
0x14002b30f  jnz     loc_14002B097
0x14002b315  jmp     loc_14002B26B
0x14002b31a  xor     edi, edi
0x14002b31c  lea     rax, [rdi+rdi*4]
0x14002b320  mov     ecx, edi
0x14002b322  mov     rdx, [rsi+rax*8+40h]; struct _NET_BUFFER_LIST *
0x14002b327  inc     edi
0x14002b329  test    rdx, rdx
0x14002b32c  jz      short loc_14002B335
0x14002b32e  cmp     [rsi+rax*8+38h], rbx
0x14002b333  jnz     short loc_14002B348
0x14002b335  cmp     edi, ebp
0x14002b337  jbe     short loc_14002B31C
0x14002b339  sub     r14d, 1
0x14002b33d  jz      loc_14002B1EA
0x14002b343  jmp     loc_14002B1DE
0x14002b348  lea     r9, [rcx+rcx*4]
0x14002b34c  mov     dword ptr [rsp+0E8h+Context], r12d; unsigned int
0x14002b351  mov     r9d, [rsi+r9*8+50h]; unsigned int
0x14002b356  mov     r8d, r13d; unsigned int
0x14002b359  mov     rcx, rbx; struct _NDIS_OPEN_BLOCK *
0x14002b35c  call    ?ndisMIndicateNetBufferListsToOpen@@YAXPEAU_NDIS_OPEN_BLOCK@@PEAU_NET_BUFFER_LIST@@KKK@Z; ndisMIndicateNetBufferListsToOpen(_NDIS_OPEN_BLOCK *,_NET_BUFFER_LIST *,ulong,ulong,ulong)
0x14002b361  jmp     short loc_14002B335
0x14002b363  mov     rax, [rbp+18h]
0x14002b367  cmp     byte ptr [rax+38h], 6
0x14002b36b  jb      loc_14002B0CC
0x14002b371  mov     r9d, edi; unsigned int
0x14002b374  mov     dword ptr [rsp+0E8h+Context], ebx; unsigned int
0x14002b378  mov     r8d, r15d; unsigned int
0x14002b37b  mov     rdx, r14; struct _NET_BUFFER_LIST *
0x14002b37e  mov     rcx, rbp; struct _NDIS_OPEN_BLOCK *
0x14002b381  call    ?ndisMIndicateNetBufferListsToOpen@@YAXPEAU_NDIS_OPEN_BLOCK@@PEAU_NET_BUFFER_LIST@@KKK@Z; ndisMIndicateNetBufferListsToOpen(_NDIS_OPEN_BLOCK *,_NET_BUFFER_LIST *,ulong,ulong,ulong)
0x14002b386  lea     rax, [rsi+40h]
0x14002b38a  mov     dword ptr [rsi+50h], 0
0x14002b391  mov     qword ptr [rax], 0
0x14002b398  jmp     loc_14002B22C
0x14002b39d  mov     rax, [rcx+858h]
0x14002b3a4  mov     ecx, [rsp+0E8h+arg_20]
0x14002b3ab  mov     dword ptr [rsp+0E8h+Context], ecx
0x14002b3af  mov     rcx, r12
0x14002b3b2  call    _guard_dispatch_icall
0x14002b3b7  add     rsp, 0C8h
0x14002b3be  pop     r15
0x14002b3c0  pop     r14
0x14002b3c2  pop     r12
0x14002b3c4  pop     rdi
0x14002b3c5  retn
0x14002b3c7  test    rsi, rsi
0x14002b3ca  jz      loc_14002B2BC
0x14002b3d0  xor     edx, edx; Tag
0x14002b3d2  mov     rcx, rsi; P
0x14002b3d5  call    cs:__imp_ExFreePoolWithTag
0x14002b3dc  nop     dword ptr [rax+rax+00h]
0x14002b3e1  jmp     loc_14002B2BC
0x14002b3e6  cmp     cs:byte_140123720, 0
0x14002b3ed  jnz     loc_14002B724
0x14002b3f3  test    ebx, ebx
0x14002b3f5  jnz     loc_14002B284
0x14002b3fb  cmp     [r12+30h], ebx
0x14002b400  jnz     loc_14002BA25
0x14002b406  xor     r13d, r13d
0x14002b409  mov     [rsp+0E8h+var_90], 0
0x14002b412  mov     dword ptr [rsp+0E8h+var_A0], r13d
0x14002b417  cmp     [r12+50h], r13d
0x14002b41c  jnz     loc_14002BA25
0x14002b422  mov     rcx, r14
0x14002b425  mov     eax, [rcx+88h]
0x14002b42b  and     eax, 0FFFFFFFCh
0x14002b42e  or      eax, 8
0x14002b431  mov     [rcx+88h], eax
0x14002b437  mov     rcx, [rcx]
0x14002b43a  test    rcx, rcx
0x14002b43d  jnz     short loc_14002B425
0x14002b43f  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14002b445  test    eax, eax
0x14002b447  jnz     loc_14002BC0A
0x14002b44d  cmp     cs:byte_140123720, al
0x14002b453  jnz     loc_14002BC0A
0x14002b459  cmp     dword ptr [r12+0C98h], 0
0x14002b462  jz      loc_14002B4EB
0x14002b468  mov     r13, [rsp+0E8h+arg_0]
0x14002b470  xor     r15d, r15d
0x14002b473  xor     r12d, r12d
0x14002b476  mov     rdi, [r14]
0x14002b479  mov     qword ptr [r14], 0
0x14002b480  mov     rax, cs:PoolHandle
0x14002b487  cmp     [r14+20h], rax
0x14002b48b  jnz     loc_14002BE4A
0x14002b491  lock dec dword ptr [r13+0C98h]
0x14002b499  mov     rax, [r14+8]
0x14002b49d  mov     rbx, [r14+68h]
0x14002b4a1  mov     rbp, [rax+8]
0x14002b4a5  test    byte ptr [rbp+0Ah], 20h
0x14002b4a9  jnz     loc_14002BE32
0x14002b4af  test    rbx, rbx
0x14002b4b2  jz      loc_14002BC17
0x14002b4b8  mov     rdx, rbp; Entry
0x14002b4bb  mov     rcx, rbx; Lookaside
0x14002b4be  call    cs:__imp_ExFreeToNPagedLookasideList
0x14002b4c5  nop     dword ptr [rax+rax+00h]
0x14002b4ca  mov     rcx, r14; NetBufferList
0x14002b4cd  call    NdisFreeNetBufferList
0x14002b4d2  mov     r14, rdi
0x14002b4d5  test    rdi, rdi
0x14002b4d8  jnz     short loc_14002B476
0x14002b4da  mov     r13d, dword ptr [rsp+0E8h+var_A0]
0x14002b4df  test    r15, r15
0x14002b4e2  jz      loc_14002B284
0x14002b4e8  mov     r14, r15
  ... truncated ...
```
