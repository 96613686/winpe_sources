# NdisFIndicateReceiveNetBufferLists

- ea: `0x14000f060`
- end: `0x14000ff5f`
- name: `NdisFIndicateReceiveNetBufferLists`
- size: `3839`
- prototype: `void __stdcall(NDIS_HANDLE NdisFilterHandle, PNET_BUFFER_LIST NetBufferLists, NDIS_PORT_NUMBER PortNumber, ULONG NumberOfNetBufferLists, ULONG ReceiveFlags)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14009f890`

## callees

- `0x140004890`
- `0x14000a110`
- `0x14000de20`
- `0x14000f060`
- `0x140010050`
- `0x140014280`
- `0x14002c970`
- `0x14002c9d0`
- `0x14002ddf0`
- `0x14002de40`
- `0x140030450`
- `0x140046270`
- `0x140083a20`
- `0x14009f8e4`
- `0x14009fa38`
- `0x1400e6240`
- `0x1400e65c0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14000f32e`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000f35b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000f32e`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000f35b`
- `ntoskrnl!MmBadPointer` at `0x1400e768c`
- `ntoskrnl!IoGetStackLimits` at `0x14000f3ce`
- `ntoskrnl!IoGetStackLimits` at `0x14000f3ce`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000f45b`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000f45b`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14000f88e`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14000fae5`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14000fbc2`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14000f88e`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14000fae5`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14000fbc2`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14000f8f0`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14000fb4d`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14000fc34`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14000f8f0`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14000fb4d`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14000fc34`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
void __stdcall NdisFIndicateReceiveNetBufferLists(
        NDIS_HANDLE NdisFilterHandle,
        PNET_BUFFER_LIST NetBufferLists,
        NDIS_PORT_NUMBER PortNumber,
        ULONG NumberOfNetBufferLists,
        ULONG ReceiveFlags)
{
  unsigned __int8 *v6; // rcx
  int v10; // eax
  PNET_BUFFER_LIST Alignment; // rdi
  __int64 v12; // r13
  unsigned __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r13
  PNET_BUFFER_LIST v16; // rdx
  unsigned __int32 v17; // ecx
  void *v18; // rax
  __int64 v19; // rcx
  ULONG v20; // r14d
  __int64 v21; // rax
  NDIS_PORT_NUMBER v22; // ecx
  unsigned __int64 v23; // rcx
  _QWORD *v24; // rcx
  __int64 v25; // rax
  unsigned int v26; // edx
  __int64 v27; // rcx
  unsigned __int64 v28; // r8
  int v29; // ecx
  int v30; // r8d
  unsigned int v31; // ecx
  PNET_BUFFER_LIST k; // rax
  unsigned __int8 *v33; // rcx
  int v34; // eax
  int v35; // eax
  int v36; // eax
  __int64 *v37; // rdi
  unsigned __int64 v38; // rcx
  void (__fastcall *v39)(__int64, __int64, _QWORD, _QWORD, int); // rsi
  __int64 j; // r14
  __int64 v41; // rbx
  __int64 v42; // r15
  __int64 v43; // r12
  __int64 v44; // rbx
  void (__fastcall *v45)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD); // rdi
  __int64 v46; // r14
  int v47; // ecx
  unsigned int v48; // edx
  __int64 v49; // rsi
  __int64 v50; // rbx
  unsigned int v51; // ecx
  __int64 v52; // rdi
  int v53; // r12d
  unsigned int v54; // r15d
  __int64 v55; // rdx
  unsigned __int64 v56; // rax
  PNET_BUFFER_LIST *v57; // rcx
  __int64 v58; // rax
  bool v59; // zf
  unsigned int v60; // edi
  __int64 v61; // rdx
  __int64 v62; // rdi
  PNET_BUFFER_LIST m; // rbx
  struct _NET_BUFFER_LIST *v64; // rdi
  int v65; // r9d
  PNET_BUFFER_LIST i; // rax
  int v67; // ecx
  unsigned int v68; // edx
  __int64 v69; // r15
  unsigned int v70; // r12d
  __int64 v71; // rax
  __int64 v72; // rdx
  __int64 v73; // rax
  __int64 v74; // rdx
  __int64 v75; // rax
  __int64 v76; // rax
  __int64 v77; // r8
  __int64 v78; // rdx
  __int64 v79; // rdx
  __int64 v80; // r8
  ULONG v81; // edx
  __int64 v82; // r12
  PNET_BUFFER_LIST v83; // rdi
  __int64 v84; // r8
  char v85; // dl
  unsigned int Flags; // eax
  unsigned int v87; // eax
  _NET_BUFFER_LIST_CONTEXT *Context; // r13
  int v89; // [rsp+28h] [rbp-D8h]
  int v90; // [rsp+30h] [rbp-D0h]
  int v91; // [rsp+38h] [rbp-C8h]
  __int64 v92; // [rsp+40h] [rbp-C0h]
  unsigned int v93; // [rsp+40h] [rbp-C0h]
  unsigned int v94; // [rsp+40h] [rbp-C0h]
  void (__fastcall *v95)(__int64, __int64, _QWORD, _QWORD, int); // [rsp+48h] [rbp-B8h]
  int v96; // [rsp+50h] [rbp-B0h]
  unsigned int v97; // [rsp+54h] [rbp-ACh]
  unsigned int v98; // [rsp+58h] [rbp-A8h]
  __int128 Parameter; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v100; // [rsp+70h] [rbp-90h]
  unsigned __int64 v101; // [rsp+80h] [rbp-80h]
  ULONG v102; // [rsp+88h] [rbp-78h]
  int v103; // [rsp+8Ch] [rbp-74h]
  unsigned __int64 LowLimit; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 HighLimit; // [rsp+98h] [rbp-68h] BYREF
  struct _NET_BUFFER_LIST *v106; // [rsp+A0h] [rbp-60h] BYREF
  PNET_BUFFER_LIST v107; // [rsp+A8h] [rbp-58h]
  __int128 v108; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v109; // [rsp+C0h] [rbp-40h]
  __int64 v110; // [rsp+D0h] [rbp-30h]
  _QWORD v111[3]; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v112[54]; // [rsp+F0h] [rbp-10h] BYREF
  _UNKNOWN *retaddr; // [rsp+2A8h] [rbp+1A8h] BYREF
  __int64 v114; // [rsp+2B0h] [rbp+1B0h]
  unsigned int v115; // [rsp+2B0h] [rbp+1B0h]
  unsigned int v116; // [rsp+2B0h] [rbp+1B0h]
  unsigned int v117; // [rsp+2B0h] [rbp+1B0h]
  int v118; // [rsp+2B0h] [rbp+1B0h]
  unsigned int v119; // [rsp+2B0h] [rbp+1B0h]
  char v120; // [rsp+2B0h] [rbp+1B0h]

  v6 = (unsigned __int8 *)*((_QWORD *)NdisFilterHandle + 65);
  v10 = *v6;
  if ( (_BYTE)v10 != 17 && ndisNblContextVerifierMode && ndisNblContextVerifierMode != 3 && v6 )
  {
    if ( v10 == 5 )
    {
      LOBYTE(v36) = (*((_DWORD *)v6 + 14) & 0x400) != 0;
    }
    else
    {
      if ( v10 != 18 )
        goto LABEL_2;
      v36 = *((_DWORD *)v6 + 56) >> 31;
    }
    if ( (_BYTE)v36 )
    {
      v64 = 0;
      v106 = 0;
      v107 = (PNET_BUFFER_LIST)&v106;
      memset(&v112[1], 0, 0x178u);
      v112[0] = NetBufferLists;
      if ( NetBufferLists )
      {
        v82 = *((_QWORD *)NdisFilterHandle + 65);
        v83 = (PNET_BUFFER_LIST)v112;
        do
        {
          if ( NdisAllocateNetBufferListContext(NetBufferLists, 8u, 0, 0x6376444Eu) )
          {
            TrackNblContextVerifierFailure(NetBufferLists, v82);
            v83->Link.Alignment = NetBufferLists->Link.Alignment;
            NetBufferLists->Link.Alignment = 0;
            v107->Link.Alignment = (unsigned __int64)NetBufferLists;
            v107 = NetBufferLists;
            NetBufferLists = (PNET_BUFFER_LIST)v83->Link.Alignment;
          }
          else
          {
            v83 = NetBufferLists;
            *(_QWORD *)&NetBufferLists->Context->ContextData[NetBufferLists->Context->Offset] = v82;
            NetBufferLists = (PNET_BUFFER_LIST)NetBufferLists->Link.Alignment;
          }
        }
        while ( NetBufferLists );
        v64 = v106;
        NetBufferLists = (PNET_BUFFER_LIST)v112[0];
      }
      NumberOfNetBufferLists = 0;
      for ( i = NetBufferLists; i; ++NumberOfNetBufferLists )
        i = (PNET_BUFFER_LIST)i->Link.Alignment;
      v106 = 0;
      v107 = (PNET_BUFFER_LIST)&v106;
      if ( v64 )
      {
        if ( byte_14011D730 && (*((_DWORD *)NdisFilterHandle + 210) & 2) != 0 )
        {
          v91 = -536866800;
          v90 = 3;
          v89 = 1;
          PktMonClientNblDrop((_DWORD)NdisFilterHandle + 784, (_DWORD)v64, *((_DWORD *)NdisFilterHandle + 209), v65);
        }
        if ( (ReceiveFlags & 2) == 0 )
        {
          if ( *(_BYTE *)NdisFilterHandle == 5 )
          {
            v84 = *((_QWORD *)NdisFilterHandle + 65);
          }
          else
          {
            if ( *(_BYTE *)NdisFilterHandle != 17 )
              goto LABEL_129;
            v84 = *((_QWORD *)NdisFilterHandle + 314);
          }
          v81 = ReceiveFlags & 1;
          if ( !v84 )
            goto LABEL_129;
          if ( *(_BYTE *)v84 != 5 )
          {
            if ( *(_BYTE *)v84 == 17 )
            {
              ndisInvokeNextReceiveCompleteHandler(
                v64,
                v81,
                (struct _NDIS_OBJECT_HEADER *)v84,
                *(struct _NDIS_OBJECT_HEADER **)(v84 + 2544),
                *(void **)(v84 + 2528),
                *(void (**)(void *, struct _NET_BUFFER_LIST *, unsigned int))(v84 + 2640));
              goto LABEL_177;
            }
LABEL_129:
            NblContextVerifierBugcheckInternalError((ULONG_PTR)NdisFilterHandle, (ULONG_PTR)v64);
          }
          ndisInvokeNextReceiveCompleteHandler(
            v64,
            v81,
            (struct _NDIS_OBJECT_HEADER *)v84,
            *(struct _NDIS_OBJECT_HEADER **)(v84 + 552),
            *(void **)(v84 + 536),
            *(void (**)(void *, struct _NET_BUFFER_LIST *, unsigned int))(v84 + 528));
        }
LABEL_177:
        if ( !NetBufferLists )
          return;
      }
    }
  }
LABEL_2:
  if ( (*((_DWORD *)NdisFilterHandle + 14) & 0x200) != 0 )
  {
    ndisNblVerifyRxIndication(
      NetBufferLists,
      PortNumber,
      NumberOfNetBufferLists,
      ReceiveFlags,
      (const struct _NDIS_OBJECT_HEADER *)NdisFilterHandle,
      *((enum _NDIS_MEDIUM *)NdisFilterHandle + 84));
    Alignment = NetBufferLists;
    if ( NetBufferLists )
    {
      v85 = byte_14011CDF0;
      do
      {
        Flags = Alignment->Flags;
        Alignment->Scratch = MmBadPointer;
        Alignment->ChildRefCount = -892679478;
        if ( v85 )
        {
          v85 = 0;
          v87 = Flags & 0xFFF0FFFF;
        }
        else
        {
          v85 = 1;
          v87 = Flags | 0xF0000;
        }
        byte_14011CDF0 = v85;
        Alignment->Flags = v87;
        Context = Alignment->Context;
        v120 = v85;
        if ( Context )
        {
          do
          {
            memset(Context->ContextData, 202, Context->Offset);
            Context = Context->Next;
          }
          while ( Context );
          v85 = v120;
        }
        Alignment = (PNET_BUFFER_LIST)Alignment->Link.Alignment;
      }
      while ( Alignment );
    }
  }
  if ( Microsoft_Windows_Networking_CorrelationEnabled )
  {
    if ( (__int64)NetBufferLists->NetBufferListInfo[13] > 0 )
    {
      v24 = (_QWORD *)NetBufferLists->Link.Alignment;
      if ( NetBufferLists->Link.Alignment )
      {
        do
        {
          v25 = v24[31];
          if ( !v25 || v25 < 0 )
          {
            v26 = _InterlockedExchangeAdd(&dword_14011AE28, 1u);
            if ( v26 + 1 < v26 )
              v26 = _InterlockedExchangeAdd(&dword_14011AE28, 1u);
            v24[31] = v26;
          }
          v24 = (_QWORD *)*v24;
        }
        while ( v24 );
      }
    }
    else
    {
      v16 = NetBufferLists;
      v17 = _InterlockedExchangeAdd(&dword_14011AE28, NumberOfNetBufferLists);
      if ( v17 + NumberOfNetBufferLists < v17 )
        v17 = _InterlockedExchangeAdd(&dword_14011AE28, NumberOfNetBufferLists);
      do
      {
        if ( (__int64)v16->NetBufferListInfo[13] <= 0 )
        {
          v18 = (void *)v17++;
          v16->NetBufferListInfo[13] = v18;
        }
        v16 = (PNET_BUFFER_LIST)v16->Link.Alignment;
      }
      while ( v16 );
    }
  }
  HIDWORD(v12) = 0;
  if ( byte_14011D730 )
  {
    v58 = *((_QWORD *)NdisFilterHandle + 114);
    if ( v58 )
    {
      if ( (*(_DWORD *)(v58 + 56) & 1) != 0 )
      {
        v59 = (NetBufferLists->NblFlags & 0x8000) == 0;
        v108 = 0;
        LODWORD(v110) = 0;
        v109 = 0;
        if ( v59 )
        {
          v60 = *((_DWORD *)NdisFilterHandle + 230);
          if ( ExAcquireRundownProtectionCacheAware(RunRefCacheAware) )
          {
            v61 = *((_QWORD *)NdisFilterHandle + 113);
            LOWORD(v108) = 40;
            *((_QWORD *)&v108 + 1) = NetBufferLists;
            LODWORD(v109) = 1;
            *(_QWORD *)((char *)&v109 + 4) = v60 | 0x100000000LL;
            v110 = 0;
            (*(void (__fastcall **)(_QWORD, __int64, __int128 *, _QWORD))(*((_QWORD *)&xmmword_14011D750 + 1) + 40LL))(
              xmmword_14011D750,
              v61,
              &v108,
              0);
            ExReleaseRundownProtectionCacheAware(RunRefCacheAware);
          }
        }
      }
    }
  }
  v13 = *((_QWORD *)NdisFilterHandle + 79);
  if ( (void (*)(void *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int, unsigned int))v13 != ndisFilterIndicateReceiveNetBufferLists )
  {
    ((void (__fastcall *)(NDIS_HANDLE, PNET_BUFFER_LIST, _QWORD, _QWORD, ULONG, int, int, int))v13)(
      NdisFilterHandle,
      NetBufferLists,
      PortNumber,
      NumberOfNetBufferLists,
      ReceiveFlags,
      v89,
      v90,
      v91);
    goto LABEL_15;
  }
  LODWORD(v12) = KeGetPcr()->Prcb.Number;
  v14 = *((_QWORD *)NdisFilterHandle + 53);
  v114 = v14;
  if ( *(_DWORD *)ndisNblTrackerMode )
  {
    ndisNblTrackerTransferOwnershipInternal(
      NetBufferLists,
      *((struct NDIS_NBL_TRACKER_HANDLE__ **)NdisFilterHandle + 81),
      *((struct NDIS_NBL_TRACKER_HANDLE__ **)NdisFilterHandle + 64),
      (enum _NDIS_NBL_TRACKER_OWNERSHIP_EVENT)(((ReceiveFlags & 2) != 0) + 130),
      ReceiveFlags & 1);
    v14 = v114;
  }
  if ( (ReceiveFlags & 2) == 0 )
  {
    if ( (ReceiveFlags & 1) == 0 )
    {
      if ( KeGetCurrentIrql() != 2 )
        goto LABEL_10;
      v14 = v114;
    }
    v19 = 96 * v12;
    if ( !*(_BYTE *)(96 * v12 + v14 + 64) )
      goto LABEL_10;
    v20 = ReceiveFlags | 1;
    v21 = v19 + v14;
    if ( *(_QWORD *)(v19 + v14 + 48) )
    {
      v55 = *(_QWORD *)(v21 + 56);
      v22 = PortNumber;
      if ( PortNumber == *(_DWORD *)(v55 + 140) && v20 == *(_DWORD *)(v55 + 132) && (ReceiveFlags & 0xCB00) == 0 )
      {
        v56 = *(_QWORD *)v55;
        if ( *(_QWORD *)v55 )
        {
          NumberOfNetBufferLists += *(_DWORD *)(v56 + 112);
          do
          {
            v57 = (PNET_BUFFER_LIST *)v56;
            v56 = *(_QWORD *)v56;
          }
          while ( v56 );
          *v57 = NetBufferLists;
          v23 = *(_QWORD *)v55;
        }
        else
        {
          *(_QWORD *)v55 = NetBufferLists;
          v23 = *(_QWORD *)v55;
          ++NumberOfNetBufferLists;
        }
LABEL_29:
        if ( v23 )
          *(_QWORD *)(v23 + 112) = NumberOfNetBufferLists;
        return;
      }
      *(_QWORD *)(v55 + 112) = NetBufferLists;
    }
    else
    {
      *(_QWORD *)(v19 + v14 + 48) = NetBufferLists;
      v22 = PortNumber;
    }
    *(_QWORD *)(v21 + 56) = NetBufferLists;
    NetBufferLists->Status = v22;
    v23 = NetBufferLists->Link.Alignment;
    NetBufferLists->Scratch = 0;
    NetBufferLists->ChildRefCount = v20;
    goto LABEL_29;
  }
LABEL_10:
  v15 = *((_QWORD *)NdisFilterHandle + 65);
  v95 = (void (__fastcall *)(__int64, __int64, _QWORD, _QWORD, int))*((_QWORD *)NdisFilterHandle + 62);
  v92 = *((_QWORD *)NdisFilterHandle + 63);
  if ( *(_BYTE *)v15 == 17 )
  {
    (*((void (__fastcall **)(_QWORD, PNET_BUFFER_LIST, _QWORD, _QWORD, ULONG, int, int, int))NdisFilterHandle + 62))(
      *((_QWORD *)NdisFilterHandle + 63),
      NetBufferLists,
      PortNumber,
      NumberOfNetBufferLists,
      ReceiveFlags,
      v89,
      v90,
      v91);
    goto LABEL_12;
  }
  if ( (ReceiveFlags & 2) == 0 && ((ReceiveFlags & 1) != 0 || KeGetCurrentIrql() == 2) )
  {
    LODWORD(v13) = KeGetPcr()->Prcb.Number;
    v37 = v111;
    NetBufferLists->Status = PortNumber;
    v38 = NetBufferLists->Link.Alignment;
    v98 = v13;
    v111[2] = 0;
    v111[0] = NetBufferLists;
    v111[1] = NetBufferLists;
    NetBufferLists->Scratch = 0;
    NetBufferLists->ChildRefCount = ReceiveFlags;
    if ( v38 )
    {
      *(_QWORD *)(v38 + 112) = NumberOfNetBufferLists;
      v13 = (unsigned int)v13;
    }
    v39 = v95;
    for ( j = v92; *(_BYTE *)v15 == 5; v92 = j )
    {
      v41 = *v37;
      if ( !*v37 )
        break;
      v42 = *(_QWORD *)(v15 + 424) + 96 * v13;
      if ( *(_BYTE *)(v42 + 64) )
      {
        *v37 = 0;
        do
        {
          v67 = *(_DWORD *)(v41 + 132);
          v68 = *(_DWORD *)(v41 + 140);
          v69 = *(_QWORD *)(v41 + 112);
          v118 = v67;
          v93 = v68;
          if ( *(_QWORD *)v41 )
            v70 = *(_DWORD *)(*(_QWORD *)v41 + 112LL);
          else
            v70 = 1;
          *(_DWORD *)(v41 + 132) = 0;
          if ( byte_14011D730 )
          {
            if ( *(_BYTE *)v15 == 5 )
            {
              v76 = *(_QWORD *)(v15 + 872);
              if ( v76 )
              {
                if ( (*(_DWORD *)(v76 + 56) & 1) != 0 )
                {
                  PktMonClientNblLogNdis(v15 + 848, v41, *(_QWORD *)&PortNumber, 1);
                  v67 = v118;
                  v68 = v93;
                }
              }
            }
          }
          if ( ndisVerifierNdisDispatch && *(_BYTE *)v15 == 5 && (v80 = *(_QWORD *)(v15 + 776)) != 0 )
            (*((void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, int, __int64, void (__fastcall *)(__int64, __int64, _QWORD, _QWORD, int), int))ndisVerifierNdisDispatch
             + 14))(
              j,
              v41,
              v68,
              v70,
              v67,
              v80,
              v39,
              v91);
          else
            v39(j, v41, v68, v70, v67);
          v41 = v69;
        }
        while ( v69 );
        break;
      }
      *(_BYTE *)(v42 + 64) = 1;
      v43 = v15;
      v44 = *v37;
      *v37 = 0;
      if ( v44 )
      {
        v45 = v95;
        v46 = v92;
        do
        {
          v47 = *(_DWORD *)(v44 + 132);
          v48 = *(_DWORD *)(v44 + 140);
          v49 = *(_QWORD *)(v44 + 112);
          v96 = v47;
          v97 = v48;
          if ( *(_QWORD *)v44 )
            v116 = *(_DWORD *)(*(_QWORD *)v44 + 112LL);
          else
            v116 = 1;
          *(_DWORD *)(v44 + 132) = 0;
          if ( byte_14011D730 )
          {
            if ( *(_BYTE *)v15 == 5 )
            {
              v71 = *(_QWORD *)(v15 + 872);
              if ( v71 )
              {
                if ( (*(_DWORD *)(v71 + 56) & 1) != 0 )
                {
                  v59 = (*(_DWORD *)(v44 + 128) & 0x8000) == 0;
                  Parameter = 0;
                  LODWORD(v101) = 0;
                  v100 = 0;
                  if ( v59 )
                  {
                    v94 = *(_DWORD *)(v15 + 880);
                    if ( ExAcquireRundownProtectionCacheAware(RunRefCacheAware) )
                    {
                      v72 = *(_QWORD *)(v15 + 864);
                      *(_QWORD *)((char *)&v100 + 4) = v94 | 0x100000000LL;
                      LOWORD(Parameter) = 40;
                      *((_QWORD *)&Parameter + 1) = v44;
                      LODWORD(v100) = 1;
                      v101 = 0;
                      (*(void (__fastcall **)(_QWORD, __int64, __int128 *, _QWORD))(*((_QWORD *)&xmmword_14011D750 + 1)
                                                                                  + 40LL))(
                        xmmword_14011D750,
                        v72,
                        &Parameter,
                        0);
                      ExReleaseRundownProtectionCacheAware(RunRefCacheAware);
                    }
                    v48 = v97;
                    v47 = v96;
                  }
                }
              }
            }
          }
          if ( ndisVerifierNdisDispatch && *(_BYTE *)v15 == 5 && (v77 = *(_QWORD *)(v15 + 776)) != 0 )
          {
            (*((void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, int, __int64, void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD), int))ndisVerifierNdisDispatch
             + 14))(
              v46,
              v44,
              v48,
              v116,
              v47,
              v77,
              v45,
              v91);
          }
          else
          {
            ((void (__fastcall *)(__int64, __int64, _QWORD, _QWORD, int, int, int))v95)(
              v46,
              v44,
              v48,
              v116,
              v47,
              v89,
              v90);
            v45 = v95;
          }
          v44 = v49;
        }
        while ( v49 );
        v43 = v15;
      }
      v13 = v98;
      v37 = (__int64 *)(v42 + 48);
      *(_BYTE *)(v42 + 64) = 0;
      v39 = *(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, int))(v43 + 496);
      j = *(_QWORD *)(v43 + 504);
      v15 = *(_QWORD *)(v15 + 520);
      v95 = v39;
    }
    v50 = *v37;
    if ( *v37 )
    {
      *v37 = 0;
      do
      {
        v51 = *(_DWORD *)(v50 + 140);
        v52 = *(_QWORD *)(v50 + 112);
        v53 = *(_DWORD *)(v50 + 132);
        v117 = v51;
        if ( *(_QWORD *)v50 )
          v54 = *(_DWORD *)(*(_QWORD *)v50 + 112LL);
        else
          v54 = 1;
        *(_DWORD *)(v50 + 132) = 0;
        if ( byte_14011D730 )
        {
          if ( *(_BYTE *)v15 == 5 )
          {
            v75 = *(_QWORD *)(v15 + 872);
            if ( v75 )
            {
              if ( (*(_DWORD *)(v75 + 56) & 1) != 0 )
              {
                PktMonClientNblLogNdis(v15 + 848, v50, *(_QWORD *)&PortNumber, 1);
                v51 = v117;
              }
            }
          }
        }
        if ( ndisVerifierNdisDispatch && *(_BYTE *)v15 == 5 && (v79 = *(_QWORD *)(v15 + 776)) != 0 )
          (*((void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, int, __int64, void (__fastcall *)(__int64, __int64, _QWORD, _QWORD, int)))ndisVerifierNdisDispatch
           + 14))(
            j,
            v50,
            v51,
            v54,
            v53,
            v79,
            v39);
        else
          v39(j, v50, v51, v54, v53);
        v50 = v52;
      }
      while ( v52 );
    }
    return;
  }
  v115 = Size;
  LowLimit = 0;
  HighLimit = 0;
  v27 = KeGetPcr()->Prcb.Number << 12;
  v28 = *(_QWORD *)(v27 + qword_14011CF78);
  LowLimit = v28;
  HighLimit = *(_QWORD *)(v27 + qword_14011CF70);
  if ( (unsigned __int64)&retaddr >= HighLimit || v28 > (unsigned __int64)&retaddr )
  {
    IoGetStackLimits(&LowLimit, &HighLimit);
    v28 = LowLimit;
  }
  if ( (unsigned __int64)&retaddr - v28 >= v115 )
  {
    if ( byte_14011D730 )
    {
      if ( *(_BYTE *)v15 == 5 )
      {
        v73 = *(_QWORD *)(v15 + 872);
        if ( v73 )
        {
          if ( (*(_DWORD *)(v73 + 56) & 1) != 0 )
          {
            v59 = (NetBufferLists->NblFlags & 0x8000) == 0;
            Parameter = 0;
            LODWORD(v101) = 0;
            v100 = 0;
            if ( v59 )
            {
              v119 = *(_DWORD *)(v15 + 880);
              if ( ExAcquireRundownProtectionCacheAware(RunRefCacheAware) )
              {
                v74 = *(_QWORD *)(v15 + 864);
                LOWORD(Parameter) = 40;
                *(_QWORD *)((char *)&v100 + 4) = v119 | 0x100000000LL;
                *((_QWORD *)&Parameter + 1) = NetBufferLists;
                LODWORD(v100) = 1;
                v101 = 0;
                (*(void (__fastcall **)(_QWORD, __int64, __int128 *, _QWORD))(*((_QWORD *)&xmmword_14011D750 + 1) + 40LL))(
                  xmmword_14011D750,
                  v74,
                  &Parameter,
                  0);
                ExReleaseRundownProtectionCacheAware(RunRefCacheAware);
              }
            }
          }
        }
      }
    }
    if ( ndisVerifierNdisDispatch && *(_BYTE *)v15 == 5 && (v78 = *(_QWORD *)(v15 + 776)) != 0 )
      (*((void (__fastcall **)(__int64, PNET_BUFFER_LIST, _QWORD, _QWORD, ULONG, __int64, void (__fastcall *)(__int64, __int64, _QWORD, _QWORD, int), int))ndisVerifierNdisDispatch
       + 14))(
        v92,
        NetBufferLists,
        PortNumber,
        NumberOfNetBufferLists,
        ReceiveFlags,
        v78,
        v95,
        v91);
    else
      ((void (__fastcall *)(__int64, PNET_BUFFER_LIST, _QWORD, _QWORD, ULONG, int, int, int))v95)(
        v92,
        NetBufferLists,
        PortNumber,
        NumberOfNetBufferLists,
        ReceiveFlags,
        v89,
        v90,
        v91);
LABEL_12:
    if ( (ReceiveFlags & 2) == 0 )
      return;
    goto LABEL_13;
  }
  *((_QWORD *)&Parameter + 1) = v92;
  v101 = __PAIR64__(NumberOfNetBufferLists, PortNumber);
  v29 = 24576;
  *(_QWORD *)&v100 = v95;
  v103 = 0;
  *(_QWORD *)&Parameter = v15;
  *((_QWORD *)&v100 + 1) = NetBufferLists;
  v102 = ReceiveFlags;
  if ( (unsigned int)Size > 0x6000 )
    v29 = Size;
  if ( KeExpandKernelStackAndCalloutEx(
         ndisDataPathExpandStackCallback<2,void (void *,_NET_BUFFER_LIST *,unsigned long,unsigned long,unsigned long)>,
         &Parameter,
         v29,
         0,
         0) >= 0 )
    goto LABEL_12;
  if ( byte_14011D730 && (*(_DWORD *)(v15 + 840) & 2) != 0 )
    PktMonClientNblDropNdis(v15 + 784, (_DWORD)NetBufferLists, v30, 1, -1073741670, -536866813);
  NdisSetStatusInNblChain(NetBufferLists, -1073741670);
  v31 = 0;
  for ( k = NetBufferLists; k; ++v31 )
    k = (PNET_BUFFER_LIST)k->Link.Alignment;
  _InterlockedAdd((volatile signed __int32 *)(v15 + 292), v31);
  if ( (ReceiveFlags & 2) == 0 )
  {
    ndisQueueStackExpansionFallbackNbls((struct _NDIS_FILTER_BLOCK *)v15, NetBufferLists, 0);
    return;
  }
LABEL_13:
  if ( *(_DWORD *)ndisNblTrackerMode )
    ndisNblTrackerTransferOwnershipInternal(
      NetBufferLists,
      *((struct NDIS_NBL_TRACKER_HANDLE__ **)NdisFilterHandle + 64),
      *((struct NDIS_NBL_TRACKER_HANDLE__ **)NdisFilterHandle + 81),
      NdisNblTrackerEvent_ReturnedToFilterResources,
      ReceiveFlags & 1);
LABEL_15:
  if ( (ReceiveFlags & 2) != 0 )
  {
    if ( Microsoft_Windows_Networking_CorrelationEnabled || byte_14011D730 )
      ndisMarkNetBufferListCorrelationIdsAsUsed(NetBufferLists);
    v33 = (unsigned __int8 *)*((_QWORD *)NdisFilterHandle + 65);
    v34 = *v33;
    if ( (_BYTE)v34 != 17 && ndisNblContextVerifierMode && ndisNblContextVerifierMode != 3 && v33 )
    {
      if ( v34 == 5 )
      {
        LOBYTE(v35) = (*((_DWORD *)v33 + 14) & 0x400) != 0;
      }
      else
      {
        if ( v34 != 18 )
          return;
        v35 = *((_DWORD *)v33 + 56) >> 31;
      }
      if ( (_BYTE)v35 )
      {
        v62 = *((_QWORD *)NdisFilterHandle + 65);
        for ( m = NetBufferLists; m; m = (PNET_BUFFER_LIST)m->Link.Alignment )
        {
          if ( *(_QWORD *)&m->Context->ContextData[m->Context->Offset] != v62 )
            NblContextVerifierBugcheckContextCorruption(m, NetBufferLists, v62);
          NdisFreeNetBufferListContext(m, 8u);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x14000f060  mov     [rsp-8+arg_10], r8d
0x14000f065  push    rbp
0x14000f066  push    rbx
0x14000f067  push    rsi
0x14000f068  push    rdi
0x14000f069  push    r12
0x14000f06b  push    r14
0x14000f06d  push    r15
0x14000f06f  lea     rbp, [rsp-170h]
0x14000f077  sub     rsp, 270h
0x14000f07e  mov     r14d, [rbp+1A0h+ReceiveFlags]
0x14000f085  mov     rbx, rcx
0x14000f088  mov     rcx, [rcx+208h]
0x14000f08f  mov     r12d, r9d
0x14000f092  mov     r15d, r8d
0x14000f095  mov     rsi, rdx
0x14000f098  movzx   eax, byte ptr [rcx]
0x14000f09b  cmp     al, 11h
0x14000f09d  jnz     loc_14000F537
0x14000f0a3  mov     eax, [rbx+38h]
0x14000f0a6  mov     [rsp+2A0h+arg_8], r13
0x14000f0ae  bt      eax, 9
0x14000f0b2  jnb     short loc_14000F0E0
0x14000f0b4  mov     eax, [rbx+150h]
0x14000f0ba  mov     r9d, r14d; unsigned int
0x14000f0bd  mov     [rsp+2A0h+var_278], eax; enum _NDIS_MEDIUM
0x14000f0c1  mov     r8d, r12d; unsigned int
0x14000f0c4  mov     edx, r15d; unsigned int
0x14000f0c7  mov     [rsp+2A0h+Context], rbx; struct _NDIS_OBJECT_HEADER *
0x14000f0cc  mov     rcx, rsi; struct _NET_BUFFER_LIST *
0x14000f0cf  call    ?ndisNblVerifyRxIndication@@YAXPEBU_NET_BUFFER_LIST@@KKKPEBU_NDIS_OBJECT_HEADER@@W4_NDIS_MEDIUM@@@Z; ndisNblVerifyRxIndication(_NET_BUFFER_LIST const *,ulong,ulong,ulong,_NDIS_OBJECT_HEADER const *,_NDIS_MEDIUM)
0x14000f0d4  mov     rdi, rsi
0x14000f0d7  test    rsi, rsi
0x14000f0da  jnz     loc_14000FED6
0x14000f0e0  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14000f0e6  test    eax, eax
0x14000f0e8  jnz     loc_14000F217
0x14000f0ee  cmp     cs:byte_14011D730, 0
0x14000f0f5  mov     r13d, 28h ; '('
0x14000f0fb  jnz     loc_14000F846
0x14000f101  mov     rax, [rbx+278h]
0x14000f108  lea     rcx, ?ndisFilterIndicateReceiveNetBufferLists@@YAXPEAXPEAU_NET_BUFFER_LIST@@KKK@Z; ndisFilterIndicateReceiveNetBufferLists(void *,_NET_BUFFER_LIST *,ulong,ulong,ulong)
0x14000f10f  mov     edi, r14d
0x14000f112  and     edi, 2
0x14000f115  cmp     rax, rcx
0x14000f118  jnz     loc_14000FF44
0x14000f11e  mov     r13d, gs:1A4h
0x14000f127  mov     r15d, r14d
0x14000f12a  mov     rdx, [rbx+1A8h]
0x14000f131  and     r15d, 1
0x14000f135  cmp     cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A, 0; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x14000f13c  mov     [rbp+1A0h+arg_0], rdx
0x14000f143  jz      short loc_14000F177
0x14000f145  mov     r8, [rbx+200h]; struct NDIS_NBL_TRACKER_HANDLE__ *
0x14000f14c  xor     r9d, r9d
0x14000f14f  mov     rdx, [rbx+288h]; struct NDIS_NBL_TRACKER_HANDLE__ *
0x14000f156  test    edi, edi
0x14000f158  mov     rcx, rsi; struct _NET_BUFFER_LIST *
0x14000f15b  mov     dword ptr [rsp+2A0h+Context], r15d; unsigned int
0x14000f160  setnz   r9b
0x14000f164  add     r9d, 82h; enum _NDIS_NBL_TRACKER_OWNERSHIP_EVENT
0x14000f16b  call    ?ndisNblTrackerTransferOwnershipInternal@@YAXPEAU_NET_BUFFER_LIST@@PEAUNDIS_NBL_TRACKER_HANDLE__@@1W4_NDIS_NBL_TRACKER_OWNERSHIP_EVENT@@K@Z; ndisNblTrackerTransferOwnershipInternal(_NET_BUFFER_LIST *,NDIS_NBL_TRACKER_HANDLE__ *,NDIS_NBL_TRACKER_HANDLE__ *,_NDIS_NBL_TRACKER_OWNERSHIP_EVENT,ulong)
0x14000f170  mov     rdx, [rbp+1A0h+arg_0]
0x14000f177  test    edi, edi
0x14000f179  jz      loc_14000F26A
0x14000f17f  mov     r13, [rbx+208h]
0x14000f186  mov     r10, [rbx+1F0h]
0x14000f18d  mov     r11, [rbx+1F8h]
0x14000f194  mov     [rsp+2A0h+var_258], r10
0x14000f199  cmp     byte ptr [r13+0], 11h
0x14000f19e  mov     [rsp+2A0h+var_260], r11
0x14000f1a3  jnz     loc_14000F34E
0x14000f1a9  mov     r8d, [rbp+1A0h+arg_10]
0x14000f1b0  mov     r9d, r12d
0x14000f1b3  mov     dword ptr [rsp+2A0h+Context], r14d
0x14000f1b8  mov     rdx, rsi
0x14000f1bb  mov     rcx, r11
0x14000f1be  mov     rax, r10
0x14000f1c1  call    _guard_dispatch_icall
0x14000f1c6  test    edi, edi
0x14000f1c8  jz      short loc_14000F1FC
0x14000f1ca  cmp     cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A, 0; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x14000f1d1  jz      short loc_14000F1F4
0x14000f1d3  mov     r8, [rbx+288h]; struct NDIS_NBL_TRACKER_HANDLE__ *
0x14000f1da  mov     r9d, 8Ch; enum _NDIS_NBL_TRACKER_OWNERSHIP_EVENT
0x14000f1e0  mov     rdx, [rbx+200h]; struct NDIS_NBL_TRACKER_HANDLE__ *
0x14000f1e7  mov     rcx, rsi; struct _NET_BUFFER_LIST *
0x14000f1ea  mov     dword ptr [rsp+2A0h+Context], r15d; unsigned int
0x14000f1ef  call    ?ndisNblTrackerTransferOwnershipInternal@@YAXPEAU_NET_BUFFER_LIST@@PEAUNDIS_NBL_TRACKER_HANDLE__@@1W4_NDIS_NBL_TRACKER_OWNERSHIP_EVENT@@K@Z; ndisNblTrackerTransferOwnershipInternal(_NET_BUFFER_LIST *,NDIS_NBL_TRACKER_HANDLE__ *,NDIS_NBL_TRACKER_HANDLE__ *,_NDIS_NBL_TRACKER_OWNERSHIP_EVENT,ulong)
0x14000f1f4  test    edi, edi
0x14000f1f6  jnz     loc_14000F4C0
0x14000f1fc  mov     r13, [rsp+2A0h+arg_8]
0x14000f204  add     rsp, 270h
0x14000f20b  pop     r15
0x14000f20d  pop     r14
0x14000f20f  pop     r12
0x14000f211  pop     rdi
0x14000f212  pop     rsi
0x14000f213  pop     rbx
0x14000f214  pop     rbp
0x14000f215  retn
0x14000f217  mov     rax, [rsi+0F8h]
0x14000f21e  test    rax, rax
0x14000f221  jnz     loc_14000F2DD
0x14000f227  mov     rdx, rsi
0x14000f22a  mov     ecx, r12d
0x14000f22d  lock xadd cs:dword_14011AE28, ecx
0x14000f235  lea     eax, [rcx+r12]
0x14000f239  cmp     eax, ecx
0x14000f23b  jb      loc_14000FEF4
0x14000f241  mov     rax, [rdx+0F8h]
0x14000f248  test    rax, rax
0x14000f24b  jnz     loc_14000F582
0x14000f251  mov     eax, ecx
0x14000f253  inc     ecx
0x14000f255  mov     [rdx+0F8h], rax
0x14000f25c  mov     rdx, [rdx]
0x14000f25f  test    rdx, rdx
0x14000f262  jz      loc_14000F0EE
0x14000f268  jmp     short loc_14000F241
0x14000f26a  test    r15d, r15d
0x14000f26d  jz      loc_14000F32E
0x14000f273  lea     rcx, ds:0[r13*2]
0x14000f27b  add     rcx, r13
0x14000f27e  shl     rcx, 5
0x14000f282  cmp     byte ptr [rcx+rdx+40h], 0
0x14000f287  jz      loc_14000F17F
0x14000f28d  or      r14d, 1
0x14000f291  lea     rax, [rcx+rdx]
0x14000f295  cmp     qword ptr [rcx+rdx+30h], 0
0x14000f29b  jnz     loc_14000F7D9
0x14000f2a1  mov     [rcx+rdx+30h], rsi
0x14000f2a6  mov     ecx, [rbp+1A0h+arg_10]
0x14000f2ac  mov     [rax+38h], rsi
0x14000f2b0  mov     [rsi+8Ch], ecx
0x14000f2b6  mov     rcx, [rsi]
0x14000f2b9  mov     qword ptr [rsi+70h], 0
0x14000f2c1  mov     [rsi+84h], r14d
0x14000f2c8  test    rcx, rcx
0x14000f2cb  jz      loc_14000F1FC
0x14000f2d1  mov     eax, r12d
0x14000f2d4  mov     [rcx+70h], rax
0x14000f2d8  jmp     loc_14000F1FC
0x14000f2dd  js      loc_14000F227
0x14000f2e3  mov     rcx, [rsi]
0x14000f2e6  test    rcx, rcx
0x14000f2e9  jz      loc_14000F0EE
0x14000f2ef  mov     rax, [rcx+0F8h]
0x14000f2f6  test    rax, rax
0x14000f2f9  jnz     loc_14000F735
0x14000f2ff  mov     edx, 1
0x14000f304  lock xadd cs:dword_14011AE28, edx
0x14000f30c  lea     eax, [rdx+1]
0x14000f30f  cmp     eax, edx
0x14000f311  jb      loc_14000FEE2
0x14000f317  mov     eax, edx
0x14000f319  mov     [rcx+0F8h], rax
0x14000f320  mov     rcx, [rcx]
0x14000f323  test    rcx, rcx
0x14000f326  jz      loc_14000F0EE
0x14000f32c  jmp     short loc_14000F2EF
0x14000f32e  call    cs:__imp_KeGetCurrentIrql
0x14000f335  nop     dword ptr [rax+rax+00h]
0x14000f33a  cmp     al, 2
0x14000f33c  jnz     loc_14000F17F
0x14000f342  mov     rdx, [rbp+1A0h+arg_0]
0x14000f349  jmp     loc_14000F273
0x14000f34e  test    edi, edi
0x14000f350  jnz     short loc_14000F36F
0x14000f352  test    r15d, r15d
0x14000f355  jnz     loc_14000F5CB
0x14000f35b  call    cs:__imp_KeGetCurrentIrql
0x14000f362  nop     dword ptr [rax+rax+00h]
0x14000f367  cmp     al, 2
0x14000f369  jz      loc_14000F5CB
0x14000f36f  mov     eax, cs:Size
0x14000f375  lea     rdx, [rbp+1A8h]
0x14000f37c  mov     dword ptr [rbp+1A0h+arg_0], eax
0x14000f382  mov     [rbp+1A0h+LowLimit], 0
0x14000f38a  mov     [rbp+1A0h+HighLimit], 0
0x14000f392  mov     eax, gs:1A4h
0x14000f39a  shl     eax, 0Ch
0x14000f39d  mov     ecx, eax
0x14000f39f  mov     rax, cs:qword_14011CF78
0x14000f3a6  mov     r8, [rcx+rax]
0x14000f3aa  mov     rax, cs:qword_14011CF70
0x14000f3b1  mov     [rbp+1A0h+LowLimit], r8
0x14000f3b5  mov     r9, [rcx+rax]
0x14000f3b9  mov     [rbp+1A0h+HighLimit], r9
0x14000f3bd  cmp     rdx, r9
0x14000f3c0  jb      loc_14000F9FE
0x14000f3c6  lea     rdx, [rbp+1A0h+HighLimit]; HighLimit
0x14000f3ca  lea     rcx, [rbp+1A0h+LowLimit]; LowLimit
0x14000f3ce  call    cs:__imp_IoGetStackLimits
0x14000f3d5  nop     dword ptr [rax+rax+00h]
0x14000f3da  mov     r8, [rbp+1A0h+LowLimit]
0x14000f3de  lea     rdx, [rbp+1A8h]
0x14000f3e5  mov     eax, dword ptr [rbp+1A0h+arg_0]
0x14000f3eb  sub     rdx, r8
0x14000f3ee  cmp     rdx, rax
0x14000f3f1  jnb     loc_14000F58D
0x14000f3f7  mov     rax, [rsp+2A0h+var_260]
0x14000f3fc  mov     ecx, [rbp+1A0h+arg_10]
0x14000f402  mov     qword ptr [rsp+2A0h+Parameter+8], rax
0x14000f407  mov     rax, [rsp+2A0h+var_258]
0x14000f40c  mov     dword ptr [rbp+1A0h+var_220], ecx
0x14000f40f  mov     ecx, 6000h
0x14000f414  mov     qword ptr [rsp+2A0h+var_230], rax
0x14000f419  mov     eax, cs:Size
0x14000f41f  mov     [rbp+1A0h+var_214], 0
0x14000f426  mov     qword ptr [rsp+2A0h+Parameter], r13
0x14000f42b  mov     qword ptr [rsp+2A0h+var_230+8], rsi
0x14000f430  mov     dword ptr [rbp+1A0h+var_220+4], r12d
0x14000f434  mov     [rbp+1A0h+var_218], r14d
0x14000f438  cmp     eax, ecx
0x14000f43a  ja      loc_14000FF04
0x14000f440  movsxd  r8, ecx; Size
0x14000f443  lea     rdx, [rsp+2A0h+Parameter]; Parameter
0x14000f448  lea     rcx, ??$ndisDataPathExpandStackCallback@$01$$A6AXPEAXPEAU_NET_BUFFER_LIST@@KKK@Z@@YAXPEAX@Z; Callout
0x14000f44f  mov     [rsp+2A0h+Context], 0; Context
0x14000f458  xor     r9d, r9d; Wait
0x14000f45b  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x14000f462  nop     dword ptr [rax+rax+00h]
0x14000f467  test    eax, eax
0x14000f469  jns     loc_14000F1C6
0x14000f46f  cmp     cs:byte_14011D730, 0
0x14000f476  jnz     loc_14000FF0F
0x14000f47c  mov     edx, 0C000009Ah; int
0x14000f481  mov     rcx, rsi; struct _NET_BUFFER_LIST *
0x14000f484  call    ?NdisSetStatusInNblChain@@YAXPEAU_NET_BUFFER_LIST@@H@Z; NdisSetStatusInNblChain(_NET_BUFFER_LIST *,int)
0x14000f489  xor     ecx, ecx
0x14000f48b  mov     rax, rsi
0x14000f48e  test    rsi, rsi
0x14000f491  jz      short loc_14000F49D
0x14000f493  mov     rax, [rax]
0x14000f496  inc     ecx
0x14000f498  test    rax, rax
0x14000f49b  jnz     short loc_14000F493
0x14000f49d  lock add [r13+124h], ecx
0x14000f4a5  test    edi, edi
0x14000f4a7  jnz     loc_14000F1CA
0x14000f4ad  xor     r8d, r8d; unsigned __int8
0x14000f4b0  mov     rdx, rsi; struct _NET_BUFFER_LIST *
0x14000f4b3  mov     rcx, r13; struct _NDIS_FILTER_BLOCK *
0x14000f4b6  call    ?ndisQueueStackExpansionFallbackNbls@@YAXPEAU_NDIS_FILTER_BLOCK@@PEAU_NET_BUFFER_LIST@@E@Z; ndisQueueStackExpansionFallbackNbls(_NDIS_FILTER_BLOCK *,_NET_BUFFER_LIST *,uchar)
0x14000f4bb  jmp     loc_14000F1FC
0x14000f4c0  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14000f4c6  test    eax, eax
0x14000f4c8  jnz     loc_14000FCE7
0x14000f4ce  cmp     cs:byte_14011D730, al
0x14000f4d4  jnz     loc_14000FCE7
0x14000f4da  mov     rcx, [rbx+208h]
0x14000f4e1  movzx   eax, byte ptr [rcx]
0x14000f4e4  cmp     al, 11h
0x14000f4e6  jz      loc_14000F1FC
0x14000f4ec  mov     edx, cs:?ndisNblContextVerifierMode@@3W4NDIS_NBL_CONTEXT_VERIFIER_MODE@@A; NDIS_NBL_CONTEXT_VERIFIER_MODE ndisNblContextVerifierMode
0x14000f4f2  test    edx, edx
0x14000f4f4  jz      loc_14000F1FC
0x14000f4fa  cmp     edx, 3
0x14000f4fd  jz      loc_14000F1FC
0x14000f503  test    rcx, rcx
0x14000f506  jz      loc_14000F1FC
0x14000f50c  mov     edx, eax
0x14000f50e  sub     edx, 5
0x14000f511  jz      loc_14000F94C
0x14000f517  sub     edx, 0Ch
0x14000f51a  jz      loc_14000F901
0x14000f520  cmp     edx, 1
0x14000f523  jnz     loc_14000F1FC
0x14000f529  mov     eax, [rcx+0E0h]
0x14000f52f  shr     eax, 1Fh
0x14000f532  jmp     loc_14000F90C
0x14000f537  mov     edx, cs:?ndisNblContextVerifierMode@@3W4NDIS_NBL_CONTEXT_VERIFIER_MODE@@A; NDIS_NBL_CONTEXT_VERIFIER_MODE ndisNblContextVerifierMode
0x14000f53d  test    edx, edx
0x14000f53f  jz      loc_14000F0A3
0x14000f545  cmp     edx, 3
0x14000f548  jz      loc_14000F0A3
0x14000f54e  test    rcx, rcx
0x14000f551  jz      loc_14000F0A3
0x14000f557  mov     edx, eax
0x14000f559  sub     edx, 5
0x14000f55c  jz      loc_14000F9F3
0x14000f562  sub     edx, 0Ch
0x14000f565  jz      loc_14000F954
0x14000f56b  cmp     edx, 1
0x14000f56e  jnz     loc_14000F0A3
0x14000f574  mov     eax, [rcx+0E0h]
0x14000f57a  shr     eax, 1Fh
0x14000f57d  jmp     loc_14000F95F
0x14000f582  js      loc_14000F251
0x14000f588  jmp     loc_14000F25C
0x14000f58d  cmp     cs:byte_14011D730, 0
0x14000f594  jnz     loc_14000FB66
0x14000f59a  mov     rax, cs:?ndisVerifierNdisDispatch@@3PEAU_VF_NDIS_DISPATCH_TABLE@@EA; _VF_NDIS_DISPATCH_TABLE * ndisVerifierNdisDispatch
0x14000f5a1  test    rax, rax
0x14000f5a4  jnz     loc_14000FD3B
0x14000f5aa  mov     r8d, [rbp+1A0h+arg_10]
0x14000f5b1  mov     r9d, r12d
0x14000f5b4  mov     rcx, [rsp+2A0h+var_260]
0x14000f5b9  mov     rdx, rsi
  ... truncated ...
```
