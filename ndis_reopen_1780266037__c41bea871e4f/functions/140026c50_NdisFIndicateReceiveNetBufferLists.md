# NdisFIndicateReceiveNetBufferLists

- ea: `0x140026c50`
- end: `0x14002823d`
- name: `NdisFIndicateReceiveNetBufferLists`
- size: `5613`
- prototype: `void __stdcall(NDIS_HANDLE NdisFilterHandle, PNET_BUFFER_LIST NetBufferLists, NDIS_PORT_NUMBER PortNumber, ULONG NumberOfNetBufferLists, ULONG ReceiveFlags)`
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400a4cd0`

## callees

- `0x1400110b0`
- `0x140011190`
- `0x140023470`
- `0x1400260b0`
- `0x140026c50`
- `0x140028330`
- `0x140029ce0`
- `0x14002aa30`
- `0x140032cb0`
- `0x1400334f0`
- `0x140037bd0`
- `0x140038090`
- `0x14003a0e0`
- `0x14004ad70`
- `0x140088ca0`
- `0x1400a4d24`
- `0x1400a4e78`
- `0x1400eb460`
- `0x1400eb7c0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140027018`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400270d4`
- `ntoskrnl!KeGetCurrentIrql` at `0x140027166`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002718d`
- `ntoskrnl!KeGetCurrentIrql` at `0x140027b32`
- `ntoskrnl!KeGetCurrentIrql` at `0x140027b88`
- `ntoskrnl!KeGetCurrentIrql` at `0x140027018`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400270d4`
- `ntoskrnl!KeGetCurrentIrql` at `0x140027166`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002718d`
- `ntoskrnl!KeGetCurrentIrql` at `0x140027b32`
- `ntoskrnl!KeGetCurrentIrql` at `0x140027b88`
- `ntoskrnl!MmBadPointer` at `0x1400ee8c8`
- `ntoskrnl!IoGetStackLimits` at `0x140027201`
- `ntoskrnl!IoGetStackLimits` at `0x140027201`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140027285`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140027285`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x1400277a0`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140027cc8`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140027d96`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x1400277a0`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140027cc8`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140027d96`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140027801`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140027d2a`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140027dfd`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140027801`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140027d2a`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140027dfd`

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
  NDIS_HANDLE v5; // r14
  ULONG v6; // edi
  unsigned __int8 *v7; // rcx
  NDIS_PORT_NUMBER v8; // r13d
  int v10; // eax
  PNET_BUFFER_LIST v11; // rbx
  void (*v12)(void *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int, unsigned int); // rax
  unsigned int Number; // ebx
  __int64 v14; // rdi
  __int64 v15; // rax
  unsigned __int64 v16; // rdx
  struct NDIS_NBL_TRACKER_HANDLE__ *v17; // r10
  __int64 v18; // r9
  unsigned __int64 v19; // rdi
  __int64 v20; // rbx
  char v21; // r13
  __int64 v22; // r12
  unsigned __int64 v23; // rbx
  PNET_BUFFER_LIST v24; // rsi
  unsigned __int64 v25; // rdi
  char *SourceHandle; // rcx
  unsigned __int64 v27; // r9
  __int64 v28; // rcx
  unsigned __int64 v29; // r12
  unsigned __int64 v30; // rdx
  __int64 v31; // rcx
  ULONG v32; // r12d
  ULONG v33; // esi
  __int64 v34; // rdi
  __int64 v35; // rbx
  void (__fastcall *v36)(__int64, PNET_BUFFER_LIST, _QWORD, _QWORD, ULONG, int, int, int); // r13
  PNET_BUFFER_LIST v37; // rdx
  unsigned int v38; // ecx
  void *v39; // rax
  unsigned __int64 v40; // rdx
  unsigned __int64 v41; // rdi
  __int64 v42; // rdx
  __int64 v43; // rcx
  ULONG v44; // r12d
  __int64 v45; // rax
  unsigned __int64 v46; // rcx
  _QWORD *v47; // rcx
  __int64 v48; // rax
  unsigned int v49; // edx
  __int64 v50; // rcx
  unsigned __int64 v51; // rdx
  int v52; // ecx
  int v53; // r8d
  unsigned int v54; // ecx
  PNET_BUFFER_LIST j; // rax
  unsigned __int8 *v56; // rcx
  int v57; // eax
  int v58; // eax
  int v59; // eax
  unsigned __int64 v60; // rax
  unsigned __int64 *v61; // r12
  unsigned __int64 v62; // rcx
  unsigned __int64 v63; // rdx
  __int64 v64; // rax
  __int64 v65; // rcx
  unsigned __int64 v66; // rbx
  __int64 v67; // r12
  int v68; // ecx
  unsigned int v69; // edx
  unsigned __int64 v70; // rbx
  int v71; // ecx
  unsigned int v72; // edx
  __int64 v73; // rdx
  PNET_BUFFER_LIST v74; // rax
  PNET_BUFFER_LIST *p_Next; // rcx
  ULONG v76; // r8d
  __int64 v77; // rax
  bool v78; // zf
  unsigned int v79; // ebx
  __int64 v80; // rdx
  struct NDIS_NBL_TRACKER_HANDLE__ *v81; // r10
  unsigned __int64 v82; // rdi
  unsigned int v83; // r12d
  __int64 v84; // rbx
  __int64 v85; // r9
  __int64 v86; // r13
  unsigned __int64 v87; // rdx
  unsigned __int64 v88; // rbx
  PNET_BUFFER_LIST v89; // r12
  unsigned __int64 v90; // rdi
  char *v91; // rcx
  char v92; // r8
  __int64 v93; // rax
  ULONG v94; // r14d
  unsigned __int64 v95; // r8
  unsigned __int64 v96; // r9
  __int64 v97; // rcx
  unsigned __int64 v98; // r13
  unsigned __int64 v99; // rdx
  __int64 v100; // rcx
  __int64 v101; // rdi
  PNET_BUFFER_LIST k; // rbx
  struct _NET_BUFFER_LIST *v103; // rbx
  int v104; // r9d
  PNET_BUFFER_LIST Alignment; // rax
  KIRQL CurrentIrql; // al
  unsigned __int64 v107; // r9
  unsigned __int64 v108; // rdi
  __int64 v109; // r9
  KIRQL v110; // al
  int v111; // ecx
  __int64 v112; // r8
  __int64 v113; // rax
  __int64 v114; // rdx
  __int64 v115; // rax
  unsigned int v116; // r12d
  __int64 v117; // rdx
  __int64 v118; // rax
  unsigned __int64 v119; // rax
  __int64 v120; // rax
  __int64 v121; // r8
  __int64 v122; // rcx
  __int64 v123; // r8
  __int64 v124; // r9
  ULONG v125; // edx
  __int64 v126; // rdi
  PNET_BUFFER_LIST v127; // rbx
  __int64 v128; // r8
  char v129; // si
  unsigned int Flags; // eax
  unsigned int v131; // eax
  _NET_BUFFER_LIST_CONTEXT *i; // rdi
  int v133; // [rsp+28h] [rbp-D8h]
  int v134; // [rsp+30h] [rbp-D0h]
  int v135; // [rsp+38h] [rbp-C8h]
  char v136; // [rsp+40h] [rbp-C0h]
  char v137; // [rsp+40h] [rbp-C0h]
  __int64 v138; // [rsp+48h] [rbp-B8h]
  unsigned int v139; // [rsp+48h] [rbp-B8h]
  int v140; // [rsp+48h] [rbp-B8h]
  __int64 v141; // [rsp+48h] [rbp-B8h]
  int v142; // [rsp+48h] [rbp-B8h]
  unsigned int v143; // [rsp+48h] [rbp-B8h]
  unsigned int v144; // [rsp+50h] [rbp-B0h]
  unsigned int v145; // [rsp+50h] [rbp-B0h]
  __int64 v146; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v147; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v148; // [rsp+58h] [rbp-A8h]
  unsigned int v149; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v150; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v151; // [rsp+60h] [rbp-A0h]
  unsigned int v152; // [rsp+60h] [rbp-A0h]
  unsigned int v153; // [rsp+60h] [rbp-A0h]
  unsigned int v154; // [rsp+60h] [rbp-A0h]
  __int64 v155; // [rsp+68h] [rbp-98h]
  __int64 v156; // [rsp+68h] [rbp-98h]
  unsigned __int64 v157; // [rsp+68h] [rbp-98h]
  struct NDIS_NBL_TRACKER_HANDLE__ *v158; // [rsp+68h] [rbp-98h]
  struct NDIS_NBL_TRACKER_HANDLE__ *v159; // [rsp+70h] [rbp-90h]
  int v160; // [rsp+70h] [rbp-90h]
  __int64 v161; // [rsp+70h] [rbp-90h]
  unsigned __int64 v162; // [rsp+70h] [rbp-90h]
  unsigned __int64 LowLimit; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 HighLimit; // [rsp+80h] [rbp-80h] BYREF
  __int128 Parameter; // [rsp+88h] [rbp-78h] BYREF
  __int128 v166; // [rsp+98h] [rbp-68h]
  unsigned __int64 v167; // [rsp+A8h] [rbp-58h]
  ULONG v168; // [rsp+B0h] [rbp-50h]
  int v169; // [rsp+B4h] [rbp-4Ch]
  struct _NET_BUFFER_LIST *v170; // [rsp+B8h] [rbp-48h] BYREF
  PNET_BUFFER_LIST v171; // [rsp+C0h] [rbp-40h]
  __int128 v172; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v173; // [rsp+D8h] [rbp-28h]
  __int64 v174; // [rsp+E8h] [rbp-18h]
  __int64 v175; // [rsp+F0h] [rbp-10h]
  _QWORD v176[3]; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD v177[48]; // [rsp+110h] [rbp+10h] BYREF
  _UNKNOWN *retaddr; // [rsp+2C8h] [rbp+1C8h] BYREF
  unsigned int v180; // [rsp+2D0h] [rbp+1D0h]
  unsigned int v181; // [rsp+2D0h] [rbp+1D0h]
  NDIS_PORT_NUMBER v182; // [rsp+2E0h] [rbp+1E0h]
  ULONG v183; // [rsp+2E8h] [rbp+1E8h]
  ULONG ReceiveFlagsa; // [rsp+2F0h] [rbp+1F0h]

  v183 = NumberOfNetBufferLists;
  v182 = PortNumber;
  v5 = NdisFilterHandle;
  v6 = NumberOfNetBufferLists;
  v7 = (unsigned __int8 *)*((_QWORD *)NdisFilterHandle + 65);
  v8 = PortNumber;
  v10 = *v7;
  if ( (_BYTE)v10 != 17 && ndisNblContextVerifierMode && ndisNblContextVerifierMode != 3 && v7 )
  {
    if ( v10 == 5 )
    {
      LOBYTE(v59) = (*((_DWORD *)v7 + 14) & 0x400) != 0;
    }
    else
    {
      if ( v10 != 18 )
        goto LABEL_2;
      v59 = *((_DWORD *)v7 + 56) >> 31;
    }
    if ( (_BYTE)v59 )
    {
      v103 = 0;
      v170 = 0;
      v171 = (PNET_BUFFER_LIST)&v170;
      memset(&v177[1], 0, 0x178u);
      v177[0] = NetBufferLists;
      if ( NetBufferLists )
      {
        v126 = *((_QWORD *)v5 + 65);
        v127 = (PNET_BUFFER_LIST)v177;
        do
        {
          if ( NdisAllocateNetBufferListContext(NetBufferLists, 8u, 0, 0x6376444Eu) )
          {
            TrackNblContextVerifierFailure(NetBufferLists, v126);
            v127->Link.Alignment = NetBufferLists->Link.Alignment;
            NetBufferLists->Link.Alignment = 0;
            v171->Link.Alignment = (unsigned __int64)NetBufferLists;
            v171 = NetBufferLists;
            NetBufferLists = (PNET_BUFFER_LIST)v127->Link.Alignment;
          }
          else
          {
            v127 = NetBufferLists;
            *(_QWORD *)&NetBufferLists->Context->ContextData[NetBufferLists->Context->Offset] = v126;
            NetBufferLists = (PNET_BUFFER_LIST)NetBufferLists->Link.Alignment;
          }
        }
        while ( NetBufferLists );
        v103 = v170;
        NetBufferLists = (PNET_BUFFER_LIST)v177[0];
      }
      v6 = 0;
      Alignment = NetBufferLists;
      v183 = 0;
      if ( NetBufferLists )
      {
        do
        {
          Alignment = (PNET_BUFFER_LIST)Alignment->Link.Alignment;
          ++v6;
        }
        while ( Alignment );
        v183 = v6;
      }
      v170 = 0;
      v171 = (PNET_BUFFER_LIST)&v170;
      if ( v103 )
      {
        if ( byte_140123720 && (*((_DWORD *)v5 + 210) & 2) != 0 )
        {
          v135 = -536866800;
          v134 = 3;
          v133 = 1;
          PktMonClientNblDrop((_DWORD)v5 + 784, (_DWORD)v103, *((_DWORD *)v5 + 209), v104);
        }
        if ( (ReceiveFlags & 2) == 0 )
        {
          if ( *(_BYTE *)v5 == 5 )
          {
            v128 = *((_QWORD *)v5 + 65);
          }
          else
          {
            if ( *(_BYTE *)v5 != 17 )
              goto LABEL_202;
            v128 = *((_QWORD *)v5 + 314);
          }
          v125 = ReceiveFlags & 1;
          if ( !v128 )
            goto LABEL_202;
          if ( *(_BYTE *)v128 != 5 )
          {
            if ( *(_BYTE *)v128 == 17 )
            {
              ndisInvokeNextReceiveCompleteHandler(
                v103,
                v125,
                (struct _NDIS_OBJECT_HEADER *)v128,
                *(struct _NDIS_OBJECT_HEADER **)(v128 + 2544),
                *(void **)(v128 + 2528),
                *(void (**)(void *, struct _NET_BUFFER_LIST *, unsigned int))(v128 + 2640));
              goto LABEL_270;
            }
LABEL_202:
            NblContextVerifierBugcheckInternalError((ULONG_PTR)v5, (ULONG_PTR)v103);
          }
          ndisInvokeNextReceiveCompleteHandler(
            v103,
            v125,
            (struct _NDIS_OBJECT_HEADER *)v128,
            *(struct _NDIS_OBJECT_HEADER **)(v128 + 552),
            *(void **)(v128 + 536),
            *(void (**)(void *, struct _NET_BUFFER_LIST *, unsigned int))(v128 + 528));
        }
LABEL_270:
        if ( !NetBufferLists )
          return;
      }
    }
  }
LABEL_2:
  if ( (*((_DWORD *)v5 + 14) & 0x200) != 0 )
  {
    ndisNblVerifyRxIndication(
      NetBufferLists,
      v8,
      v6,
      ReceiveFlags,
      (const struct _NDIS_OBJECT_HEADER *)v5,
      *((enum _NDIS_MEDIUM *)v5 + 84));
    v11 = NetBufferLists;
    if ( NetBufferLists )
    {
      v129 = byte_140122DF0;
      do
      {
        Flags = v11->Flags;
        v11->Scratch = MmBadPointer;
        v11->ChildRefCount = -892679478;
        if ( v129 )
        {
          v129 = 0;
          v131 = Flags & 0xFFF0FFFF;
        }
        else
        {
          v129 = 1;
          v131 = Flags | 0xF0000;
        }
        byte_140122DF0 = v129;
        v11->Flags = v131;
        for ( i = v11->Context; i; i = i->Next )
          memset(i->ContextData, 202, i->Offset);
        v11 = (PNET_BUFFER_LIST)v11->Link.Alignment;
      }
      while ( v11 );
      v6 = v183;
    }
  }
  if ( Microsoft_Windows_Networking_CorrelationEnabled )
  {
    if ( (__int64)NetBufferLists->NetBufferListInfo[13] > 0 )
    {
      v47 = (_QWORD *)NetBufferLists->Link.Alignment;
      if ( NetBufferLists->Link.Alignment )
      {
        do
        {
          v48 = v47[31];
          if ( !v48 || v48 < 0 )
          {
            v49 = _InterlockedExchangeAdd(&dword_140120E28, 1u);
            if ( v49 + 1 < v49 )
              v49 = _InterlockedExchangeAdd(&dword_140120E28, 1u);
            v47[31] = v49;
          }
          v47 = (_QWORD *)*v47;
        }
        while ( v47 );
      }
    }
    else
    {
      v37 = NetBufferLists;
      v38 = _InterlockedExchangeAdd(&dword_140120E28, v6);
      if ( v38 + v6 < v38 )
        v38 = _InterlockedExchangeAdd(&dword_140120E28, v6);
      do
      {
        if ( (__int64)v37->NetBufferListInfo[13] <= 0 )
        {
          v39 = (void *)v38++;
          v37->NetBufferListInfo[13] = v39;
        }
        v37 = (PNET_BUFFER_LIST)v37->Link.Alignment;
      }
      while ( v37 );
    }
  }
  if ( byte_140123720 )
  {
    v77 = *((_QWORD *)v5 + 114);
    if ( v77 )
    {
      if ( (*(_DWORD *)(v77 + 56) & 1) != 0 )
      {
        v78 = (NetBufferLists->NblFlags & 0x8000) == 0;
        v172 = 0;
        LODWORD(v174) = 0;
        v173 = 0;
        if ( v78 )
        {
          v79 = *((_DWORD *)v5 + 230);
          if ( ExAcquireRundownProtectionCacheAware(RunRefCacheAware) )
          {
            v80 = *((_QWORD *)v5 + 113);
            LOWORD(v172) = 40;
            *((_QWORD *)&v172 + 1) = NetBufferLists;
            LODWORD(v173) = 1;
            *(_QWORD *)((char *)&v173 + 4) = v79 | 0x100000000LL;
            v174 = 0;
            (*(void (__fastcall **)(_QWORD, __int64, __int128 *, _QWORD))(*((_QWORD *)&xmmword_140123740 + 1) + 40LL))(
              xmmword_140123740,
              v80,
              &v172,
              0);
            ExReleaseRundownProtectionCacheAware(RunRefCacheAware);
          }
        }
      }
    }
  }
  v12 = (void (*)(void *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int, unsigned int))*((_QWORD *)v5 + 79);
  if ( v12 != ndisFilterIndicateReceiveNetBufferLists )
  {
    ((void (__fastcall *)(NDIS_HANDLE, PNET_BUFFER_LIST, _QWORD, _QWORD, ULONG, int, int, int))v12)(
      v5,
      NetBufferLists,
      v8,
      v6,
      ReceiveFlags,
      v133,
      v134,
      v135);
    v33 = ReceiveFlags & 2;
    goto LABEL_39;
  }
  Number = KeGetPcr()->Prcb.Number;
  v14 = *((_QWORD *)v5 + 53);
  v15 = *(unsigned int *)ndisNblTrackerMode;
  v155 = v14;
  v144 = Number;
  if ( *(_DWORD *)ndisNblTrackerMode )
  {
    LODWORD(v16) = 0;
    v17 = (struct NDIS_NBL_TRACKER_HANDLE__ *)*((_QWORD *)v5 + 81);
    v18 = 0;
    v19 = *((_QWORD *)v5 + 64);
    v20 = ndisNblTrackerEpoch;
    v21 = ReceiveFlags & 1;
    v22 = 0;
    v159 = v17;
    v146 = 0;
    v138 = 0;
    v136 = 0;
    if ( *(int *)ndisNblTrackerMode >= 3 )
    {
      ndisNblTrackerRecordEventInternal(
        NetBufferLists,
        v17,
        ((ReceiveFlags & 2) != 0) + 130,
        (void *)v19,
        ReceiveFlags & 1);
      v17 = v159;
      v18 = 0;
    }
    *(_QWORD *)&PortNumber = v19 & 0xFFFFFFFFFFFFFFFDuLL;
    v151 = v19 & 0xFFFFFFFFFFFFFFFDuLL;
    if ( (v19 & 1) != 0 )
    {
      v15 = 2 * v20;
      v23 = (2 * v20) ^ (v19 ^ (2 * v20)) & 0xFFFFFFFFFFFFFFFDuLL;
      *(_QWORD *)&PortNumber = *(_QWORD *)((v19 & 0xFFFFFFFFFFFFFFF8uLL) + 24);
      v151 = *(_QWORD *)&PortNumber;
    }
    else
    {
      v23 = v19 & 0xFFFFFFFFFFFFFFFDuLL;
    }
    v24 = NetBufferLists;
    if ( NetBufferLists )
    {
      while ( 1 )
      {
        v25 = (unsigned __int64)v24->NetBufferListInfo[27];
        while ( v24->NetBufferListInfo[27] == (void *)v25 )
        {
          if ( v25 )
          {
            if ( (v25 & 4) != 0 )
              goto LABEL_109;
          }
          else if ( !v24->SourceHandle )
          {
            v60 = (unsigned __int64)v17 & 0xFFFFFFFFFFFFFFFDuLL;
            if ( ((unsigned __int8)v17 & 1) != 0 )
              v60 = *(_QWORD *)(((unsigned __int64)v17 & 0xFFFFFFFFFFFFFFF8uLL) + 24);
            v24->SourceHandle = (void *)v60;
          }
          SourceHandle = (char *)v24->SourceHandle;
          if ( SourceHandle )
          {
            LODWORD(v16) = (unsigned __int8)*SourceHandle;
            if ( (unsigned __int8)(v16 - 17) <= 1u || (_BYTE)v16 == 5 )
            {
              if ( SourceHandle != *(char **)&PortNumber || v24->ParentNetBufferList )
              {
                ++v22;
                v15 = v23;
              }
              else
              {
                ++v18;
                v15 = 24;
                v138 = v18;
                ++v22;
              }
              goto LABEL_21;
            }
            if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v16) = 3;
              WPP_RECORDER_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                v16,
                27,
                12,
                (struct _GUID *)&WPP_78a33c75b2d2335d1cf1dcc315edf7b8_Traceguids,
                (char)v24,
                *SourceHandle);
LABEL_143:
              *(_QWORD *)&PortNumber = v151;
              v18 = v138;
              v17 = v159;
            }
          }
          else if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v16) = 3;
            WPP_RECORDER_SF_q(
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              v16,
              27,
              11,
              (struct _GUID *)&WPP_78a33c75b2d2335d1cf1dcc315edf7b8_Traceguids,
              (char)v24);
            goto LABEL_143;
          }
LABEL_109:
          v15 = v23 | 4;
LABEL_21:
          v24->NetBufferListInfo[27] = (void *)v15;
          v24 = (PNET_BUFFER_LIST)v24->Link.Alignment;
          if ( !v24 )
            break;
        }
        if ( (v25 & 1) == 0 )
          goto LABEL_27;
        v27 = v146 - v22;
        v147 = v146 - v22;
        if ( !v147 )
          goto LABEL_27;
        if ( v21 || v136 )
        {
          v16 = (v25 & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((v25 >> 1) & 1) + 3);
          if ( !v21 )
            goto LABEL_51;
          goto LABEL_26;
        }
        v136 = 1;
        LOBYTE(v15) = KeGetCurrentIrql();
        *(_QWORD *)&PortNumber = v151;
        v40 = v25;
        v27 = v147;
        v41 = v25 & 0xFFFFFFFFFFFFFFF8uLL;
        v42 = 16 * (((v40 >> 1) & 1) + 3);
        if ( (_BYTE)v15 == 2 )
        {
          v21 = 1;
          v16 = v41 + v42;
LABEL_26:
          v28 = KeGetPcr()->Prcb.Number << 12;
          v15 = *(_QWORD *)v16;
          *(_QWORD *)(v28 + *(_QWORD *)v16) += v27;
          goto LABEL_27;
        }
        v21 = 0;
        v16 = v41 + v42;
LABEL_51:
        _InterlockedAdd64((volatile signed __int64 *)(v16 + 8), v27);
LABEL_27:
        v18 = v138;
        v17 = v159;
        v146 = v22;
        if ( !v24 )
        {
          v5 = NdisFilterHandle;
          break;
        }
      }
    }
    if ( (v23 & 1) == 0 )
      goto LABEL_34;
    v29 = v22 - v138;
    if ( !v29 )
      goto LABEL_34;
    if ( v21 || v136 )
    {
      v30 = (v23 & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((v23 >> 1) & 1) + 3);
      if ( !v21 )
      {
LABEL_60:
        _InterlockedAdd64((volatile signed __int64 *)(v30 + 8), v29);
        goto LABEL_34;
      }
    }
    else
    {
      LOBYTE(v15) = KeGetCurrentIrql();
      v30 = (v23 & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((v23 >> 1) & 1) + 3);
      if ( (_BYTE)v15 != 2 )
        goto LABEL_60;
    }
    v31 = KeGetPcr()->Prcb.Number << 12;
    v15 = *(_QWORD *)v30;
    *(_QWORD *)(v31 + *(_QWORD *)v30) += v29;
LABEL_34:
    v14 = v155;
    Number = v144;
    v8 = v182;
  }
  v32 = ReceiveFlags;
  v33 = ReceiveFlags & 2;
  if ( (ReceiveFlags & 2) != 0
    || (ReceiveFlags & 1) == 0 && KeGetCurrentIrql() != 2
    || (v15 = Number, v43 = 96LL * Number, !*(_BYTE *)(v43 + v14 + 64)) )
  {
    v34 = *((_QWORD *)v5 + 65);
    v35 = *((_QWORD *)v5 + 63);
    v36 = (void (__fastcall *)(__int64, PNET_BUFFER_LIST, _QWORD, _QWORD, ULONG, int, int, int))*((_QWORD *)v5 + 62);
    v156 = v35;
    if ( *(_BYTE *)v34 == 17 )
    {
LABEL_37:
      v36(v35, NetBufferLists, v182, v183, v32, v133, v134, v135);
      goto LABEL_38;
    }
    if ( (ReceiveFlags & 2) == 0 && ((ReceiveFlags & 1) != 0 || KeGetCurrentIrql() == 2) )
    {
      LODWORD(v15) = KeGetPcr()->Prcb.Number;
      v61 = v176;
      NetBufferLists->ChildRefCount = ReceiveFlags;
      NetBufferLists->Status = v182;
      v62 = NetBufferLists->Link.Alignment;
      v152 = v15;
      v176[2] = 0;
      v176[0] = NetBufferLists;
      v176[1] = NetBufferLists;
      NetBufferLists->Scratch = 0;
      if ( v62 )
      {
        *(_QWORD *)&PortNumber = v183;
        *(_QWORD *)(v62 + 112) = v183;
      }
      while ( *(_BYTE *)v34 == 5 )
      {
        v63 = *v61;
        v148 = *v61;
        if ( !*v61 )
          break;
        v64 = 96 * v15 + *(_QWORD *)(v34 + 424) + 48LL;
        v175 = v64;
        if ( *(_BYTE *)(v64 + 16) )
        {
          *v61 = 0;
          do
          {
            v111 = *(_DWORD *)(v63 + 132);
            v112 = *(unsigned int *)(v63 + 140);
            LowLimit = *(_QWORD *)(v63 + 112);
            v142 = v111;
            v154 = v112;
            if ( *(_QWORD *)v63 )
              v181 = *(_DWORD *)(*(_QWORD *)v63 + 112LL);
            else
              v181 = 1;
            *(_DWORD *)(v63 + 132) = 0;
            if ( byte_140123720 )
            {
              if ( *(_BYTE *)v34 == 5 )
              {
                v120 = *(_QWORD *)(v34 + 872);
                if ( v120 )
                {
                  if ( (*(_DWORD *)(v120 + 56) & 1) != 0 )
                  {
                    PktMonClientNblLogNdis(v34 + 848, v63, v112, 1);
                    v63 = v148;
                    v111 = v142;
                    v112 = v154;
                  }
                }
              }
            }
            if ( ndisVerifierNdisDispatch && *(_BYTE *)v34 == 5 && (v124 = *(_QWORD *)(v34 + 776)) != 0 )
              (*((void (__fastcall **)(__int64, unsigned __int64, __int64, _QWORD, int, __int64, void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD), int))ndisVerifierNdisDispatch
               + 14))(
                v35,
                v63,
                v112,
                v181,
                v111,
                v124,
                (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))v36,
                v135);
            else
              ((void (__fastcall *)(__int64, unsigned __int64, __int64, _QWORD, int))v36)(v35, v63, v112, v181, v111);
            v148 = LowLimit;
            v63 = LowLimit;
          }
          while ( LowLimit );
          break;
        }
        *(_BYTE *)(v64 + 16) = 1;
        v65 = v34;
        v66 = *v61;
        *v61 = 0;
        if ( v66 )
        {
          v67 = v156;
          do
          {
            v68 = *(_DWORD *)(v66 + 132);
            v69 = *(_DWORD *)(v66 + 140);
            v157 = *(_QWORD *)(v66 + 112);
            v160 = v68;
            v149 = v69;
            if ( *(_QWORD *)v66 )
              v145 = *(_DWORD *)(*(_QWORD *)v66 + 112LL);
            else
              v145 = 1;
            *(_DWORD *)(v66 + 132) = 0;
            if ( byte_140123720 )
            {
              if ( *(_BYTE *)v34 == 5 )
              {
                v113 = *(_QWORD *)(v34 + 872);
                if ( v113 )
                {
                  if ( (*(_DWORD *)(v113 + 56) & 1) != 0 )
                  {
                    v78 = (*(_DWORD *)(v66 + 128) & 0x8000) == 0;
                    Parameter = 0;
                    LODWORD(v167) = 0;
                    v166 = 0;
                    if ( v78 )
                    {
                      v143 = *(_DWORD *)(v34 + 880);
                      if ( ExAcquireRundownProtectionCacheAware(RunRefCacheAware) )
                      {
                        v114 = *(_QWORD *)(v34 + 864);
                        *(_QWORD *)((char *)&v166 + 4) = v143 | 0x100000000LL;
                        LOWORD(Parameter) = 40;
                        *((_QWORD *)&Parameter + 1) = v66;
                        LODWORD(v166) = 1;
                        v167 = 0;
                        (*(void (__fastcall **)(_QWORD, __int64, __int128 *, _QWORD))(*((_QWORD *)&xmmword_140123740 + 1)
                                                                                    + 40LL))(
                          xmmword_140123740,
                          v114,
                          &Parameter,
                          0);
                        ExReleaseRundownProtectionCacheAware(RunRefCacheAware);
                      }
                      v69 = v149;
                      v68 = v160;
                    }
                  }
                }
              }
            }
            if ( ndisVerifierNdisDispatch && *(_BYTE *)v34 == 5 && (v121 = *(_QWORD *)(v34 + 776)) != 0 )
              (*((void (__fastcall **)(__int64, unsigned __int64, _QWORD, _QWORD, int, __int64, void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD), int))ndisVerifierNdisDispatch
               + 14))(
                v67,
                v66,
                v69,
                v145,
                v68,
                v121,
                (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))v36,
                v135);
            else
              ((void (__fastcall *)(__int64, unsigned __int64, _QWORD, _QWORD, int, int, int))v36)(
                v67,
                v66,
                v69,
                v145,
                v68,
                v133,
                v134);
            v66 = v157;
          }
          while ( v157 );
          v5 = NdisFilterHandle;
          v65 = v34;
          v64 = v175;
        }
        *(_BYTE *)(v64 + 16) = 0;
        v61 = (unsigned __int64 *)v64;
        v35 = *(_QWORD *)(v65 + 504);
        v34 = *(_QWORD *)(v34 + 520);
        v36 = *(void (__fastcall **)(__int64, PNET_BUFFER_LIST, _QWORD, _QWORD, ULONG, int, int, int))(v65 + 496);
        v15 = v152;
        v156 = v35;
      }
      v70 = *v61;
      if ( *v61 )
      {
        *v61 = 0;
        do
        {
          v71 = *(_DWORD *)(v70 + 132);
          v72 = *(_DWORD *)(v70 + 140);
          LowLimit = *(_QWORD *)(v70 + 112);
          v140 = v71;
          v153 = v72;
          if ( *(_QWORD *)v70 )
            v180 = *(_DWORD *)(*(_QWORD *)v70 + 112LL);
          else
            v180 = 1;
          *(_DWORD *)(v70 + 132) = 0;
          if ( byte_140123720 )
          {
            if ( *(_BYTE *)v34 == 5 )
            {
              v118 = *(_QWORD *)(v34 + 872);
              if ( v118 )
              {
                if ( (*(_DWORD *)(v118 + 56) & 1) != 0 )
                {
                  PktMonClientNblLogNdis(v34 + 848, v70, *(_QWORD *)&PortNumber, 1);
                  v71 = v140;
                  v72 = v153;
                }
              }
            }
          }
          if ( ndisVerifierNdisDispatch && *(_BYTE *)v34 == 5 && (v123 = *(_QWORD *)(v34 + 776)) != 0 )
            (*((void (__fastcall **)(__int64, unsigned __int64, _QWORD, _QWORD, int, __int64, void (__fastcall *)(__int64, PNET_BUFFER_LIST, _QWORD, _QWORD, ULONG, int, int, int)))ndisVerifierNdisDispatch
             + 14))(
              v156,
              v70,
              v72,
              v180,
              v71,
              v123,
              v36);
          else
            ((void (__fastcall *)(__int64, unsigned __int64, _QWORD, _QWORD, int))v36)(v156, v70, v72, v180, v71);
          v70 = LowLimit;
        }
        while ( LowLimit );
      }
      goto LABEL_39;
    }
    v139 = Size;
    LowLimit = 0;
    HighLimit = 0;
    v50 = KeGetPcr()->Prcb.Number << 12;
    v51 = *(_QWORD *)(v50 + qword_140122F78);
    LowLimit = v51;
    HighLimit = *(_QWORD *)(v50 + qword_140122F70);
    if ( (unsigned __int64)&retaddr >= HighLimit || v51 > (unsigned __int64)&retaddr )
    {
      IoGetStackLimits(&LowLimit, &HighLimit);
      v51 = LowLimit;
    }
    if ( (unsigned __int64)&retaddr - v51 >= v139 )
    {
      if ( byte_140123720 )
      {
        if ( *(_BYTE *)v34 == 5 )
        {
          v115 = *(_QWORD *)(v34 + 872);
          if ( v115 )
          {
            if ( (*(_DWORD *)(v115 + 56) & 1) != 0 )
            {
              v78 = (NetBufferLists->NblFlags & 0x8000) == 0;
              Parameter = 0;
              LODWORD(v167) = 0;
              v166 = 0;
              if ( v78 )
              {
                v116 = *(_DWORD *)(v34 + 880);
                if ( ExAcquireRundownProtectionCacheAware(RunRefCacheAware) )
                {
                  v117 = *(_QWORD *)(v34 + 864);
                  LOWORD(Parameter) = 40;
                  *((_QWORD *)&Parameter + 1) = NetBufferLists;
                  LODWORD(v166) = 1;
                  *(_QWORD *)((char *)&v166 + 4) = v116 | 0x100000000LL;
                  v167 = 0;
                  (*(void (__fastcall **)(_QWORD, __int64, __int128 *, _QWORD))(*((_QWORD *)&xmmword_140123740 + 1)
                                                                              + 40LL))(
                    xmmword_140123740,
                    v117,
                    &Parameter,
                    0);
                  ExReleaseRundownProtectionCacheAware(RunRefCacheAware);
                }
              }
            }
          }
        }
      }
      if ( !ndisVerifierNdisDispatch || *(_BYTE *)v34 != 5 || (v122 = *(_QWORD *)(v34 + 776)) == 0 )
      {
        v32 = ReceiveFlags;
        goto LABEL_37;
      }
      LOBYTE(v32) = ReceiveFlags;
      (*((void (__fastcall **)(__int64, PNET_BUFFER_LIST, _QWORD, _QWORD, ULONG, __int64, void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD), int))ndisVerifierNdisDispatch
       + 14))(
        v35,
        NetBufferLists,
        v182,
        v183,
        ReceiveFlags,
        v122,
        (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))v36,
        v135);
    }
    else
    {
      LOBYTE(v32) = ReceiveFlags;
      v167 = __PAIR64__(v183, v182);
      v52 = 24576;
      v169 = 0;
      *(_QWORD *)&Parameter = v34;
      *((_QWORD *)&Parameter + 1) = v35;
      *(_QWORD *)&v166 = v36;
      *((_QWORD *)&v166 + 1) = NetBufferLists;
      v168 = ReceiveFlags;
      if ( (unsigned int)Size > 0x6000 )
        v52 = Size;
      if ( KeExpandKernelStackAndCalloutEx(
             ndisDataPathExpandStackCallback<2,void (void *,_NET_BUFFER_LIST *,unsigned long,unsigned long,unsigned long)>,
             &Parameter,
             v52,
             0,
             0) < 0 )
      {
        if ( byte_140123720 && (*(_DWORD *)(v34 + 840) & 2) != 0 )
          PktMonClientNblDropNdis(v34 + 784, (_DWORD)NetBufferLists, v53, 1, -1073741670, -536866813);
        NdisSetStatusInNblChain(NetBufferLists, -1073741670);
        v54 = 0;
        for ( j = NetBufferLists; j; ++v54 )
          j = (PNET_BUFFER_LIST)j->Link.Alignment;
        _InterlockedAdd((volatile signed __int32 *)(v34 + 292), v54);
        if ( (ReceiveFlags & 2) == 0 )
        {
          ndisQueueStackExpansionFallbackNbls((struct _NDIS_FILTER_BLOCK *)v34, NetBufferLists, 0);
          goto LABEL_39;
        }
        goto LABEL_159;
      }
    }
LABEL_38:
    if ( (ReceiveFlags & 2) == 0 )
      goto LABEL_39;
LABEL_159:
    if ( !*(_DWORD *)ndisNblTrackerMode )
      goto LABEL_39;
    v81 = (struct NDIS_NBL_TRACKER_HANDLE__ *)*((_QWORD *)v5 + 64);
    v82 = *((_QWORD *)v5 + 81);
    v83 = v32 & 1;
    v84 = ndisNblTrackerEpoch;
    v85 = 0;
    v86 = 0;
    ReceiveFlagsa = v83;
    v158 = v81;
    v161 = 0;
    v141 = 0;
    v137 = 0;
    if ( *(int *)ndisNblTrackerMode >= 3 )
    {
      ndisNblTrackerRecordEventInternal(NetBufferLists, v81, 0x8Cu, (void *)v82, v83);
      v81 = v158;
      v85 = 0;
    }
    v87 = v82 & 0xFFFFFFFFFFFFFFFDuLL;
    v150 = v82 & 0xFFFFFFFFFFFFFFFDuLL;
    if ( (v82 & 1) != 0 )
    {
      v88 = (2 * v84) ^ (v82 ^ (2 * v84)) & 0xFFFFFFFFFFFFFFFDuLL;
      v87 = *(_QWORD *)((v82 & 0xFFFFFFFFFFFFFFF8uLL) + 24);
      v150 = v87;
    }
    else
    {
      v88 = v82 & 0xFFFFFFFFFFFFFFFDuLL;
    }
    v89 = NetBufferLists;
    if ( NetBufferLists )
    {
LABEL_165:
      v90 = (unsigned __int64)v89->NetBufferListInfo[27];
      while ( 1 )
      {
        if ( v89->NetBufferListInfo[27] != (void *)v90 )
        {
LABEL_174:
          v94 = ReceiveFlagsa;
          if ( (v90 & 1) == 0 )
            goto LABEL_179;
          v95 = v161 - v86;
          v162 = v161 - v86;
          if ( !v162 )
            goto LABEL_179;
          if ( (_BYTE)ReceiveFlagsa || v137 )
          {
            v96 = (v90 & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((v90 >> 1) & 1) + 3);
            if ( !(_BYTE)ReceiveFlagsa )
              goto LABEL_207;
            goto LABEL_178;
          }
          v137 = 1;
          CurrentIrql = KeGetCurrentIrql();
          v87 = v150;
          v107 = v90;
          v95 = v162;
          v108 = v90 & 0xFFFFFFFFFFFFFFF8uLL;
          v109 = 16 * (((v107 >> 1) & 1) + 3);
          if ( CurrentIrql == 2 )
          {
            LOBYTE(v94) = 1;
            v96 = v108 + v109;
            ReceiveFlagsa = v94;
LABEL_178:
            v97 = KeGetPcr()->Prcb.Number << 12;
            *(_QWORD *)(v97 + *(_QWORD *)v96) += v95;
            goto LABEL_179;
          }
          LOBYTE(v94) = 0;
          ReceiveFlagsa = v94;
          v96 = v108 + v109;
LABEL_207:
          _InterlockedAdd64((volatile signed __int64 *)(v96 + 8), v95);
LABEL_179:
          v85 = v141;
          v81 = v158;
          v161 = v86;
          if ( !v89 )
          {
            v5 = NdisFilterHandle;
            break;
          }
          goto LABEL_165;
        }
        if ( v90 )
        {
          if ( (v90 & 4) != 0 )
            goto LABEL_249;
        }
        else if ( !v89->SourceHandle )
        {
          v119 = (unsigned __int64)v81 & 0xFFFFFFFFFFFFFFFDuLL;
          if ( ((unsigned __int8)v81 & 1) != 0 )
            v119 = *(_QWORD *)(((unsigned __int64)v81 & 0xFFFFFFFFFFFFFFF8uLL) + 24);
          v89->SourceHandle = (void *)v119;
        }
        v91 = (char *)v89->SourceHandle;
        if ( v91 )
        {
          v92 = *v91;
          if ( (unsigned __int8)(*v91 - 17) <= 1u || v92 == 5 )
          {
            if ( v91 != (char *)v87 || v89->ParentNetBufferList )
            {
              ++v86;
              v93 = v88;
            }
            else
            {
              ++v85;
              v93 = 24;
              v141 = v85;
              ++v86;
            }
            goto LABEL_173;
          }
          if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v87) = 3;
            WPP_RECORDER_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              v87,
              27,
              12,
              (struct _GUID *)&WPP_78a33c75b2d2335d1cf1dcc315edf7b8_Traceguids,
              (char)v89,
              v92);
LABEL_301:
            v87 = v150;
            v85 = v141;
            v81 = v158;
          }
        }
        else if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v87) = 3;
          WPP_RECORDER_SF_q(
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            v87,
            27,
            11,
            (struct _GUID *)&WPP_78a33c75b2d2335d1cf1dcc315edf7b8_Traceguids,
            (char)v89);
          goto LABEL_301;
        }
LABEL_249:
        v93 = v88 | 4;
LABEL_173:
        v89->NetBufferListInfo[27] = (void *)v93;
        v89 = (PNET_BUFFER_LIST)v89->Link.Alignment;
        if ( !v89 )
          goto LABEL_174;
      }
    }
    if ( (v88 & 1) == 0 )
      goto LABEL_39;
    v98 = v86 - v141;
    if ( !v98 )
      goto LABEL_39;
    if ( (_BYTE)ReceiveFlagsa || v137 )
    {
      v99 = (v88 & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((v88 >> 1) & 1) + 3);
      if ( !(_BYTE)ReceiveFlagsa )
      {
LABEL_210:
        _InterlockedAdd64((volatile signed __int64 *)(v99 + 8), v98);
        goto LABEL_39;
      }
    }
    else
    {
      v110 = KeGetCurrentIrql();
      v99 = (v88 & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((v88 >> 1) & 1) + 3);
      if ( v110 != 2 )
        goto LABEL_210;
    }
    v100 = KeGetPcr()->Prcb.Number << 12;
    *(_QWORD *)(v100 + *(_QWORD *)v99) += v98;
    goto LABEL_39;
  }
  v44 = ReceiveFlags | 1;
  v45 = v43 + v14;
  if ( !*(_QWORD *)(v43 + v14 + 48) )
  {
    *(_QWORD *)(v43 + v14 + 48) = NetBufferLists;
    goto LABEL_56;
  }
  v73 = *(_QWORD *)(v45 + 56);
  if ( v8 != *(_DWORD *)(v73 + 140) || v44 != *(_DWORD *)(v73 + 132) || (ReceiveFlags & 0xCB00) != 0 )
  {
    *(_QWORD *)(v73 + 112) = NetBufferLists;
LABEL_56:
    *(_QWORD *)(v45 + 56) = NetBufferLists;
    v46 = NetBufferLists->Link.Alignment;
    NetBufferLists->Scratch = 0;
    NetBufferLists->ChildRefCount = v44;
    NetBufferLists->Status = v8;
    if ( v46 )
      *(_QWORD *)(v46 + 112) = v183;
    goto LABEL_39;
  }
  v74 = *(PNET_BUFFER_LIST *)v73;
  if ( *(_QWORD *)v73 )
  {
    v76 = LODWORD(v74->Scratch) + v183;
    do
    {
      p_Next = &v74->Next;
      v74 = (PNET_BUFFER_LIST)v74->Link.Alignment;
    }
    while ( v74 );
  }
  else
  {
    p_Next = (PNET_BUFFER_LIST *)v73;
    v76 = v183 + 1;
  }
  *p_Next = NetBufferLists;
  if ( *(_QWORD *)v73 )
    *(_QWORD *)(*(_QWORD *)v73 + 112LL) = v76;
LABEL_39:
  if ( v33 )
  {
    if ( Microsoft_Windows_Networking_CorrelationEnabled || byte_140123720 )
      ndisMarkNetBufferListCorrelationIdsAsUsed(NetBufferLists);
    v56 = (unsigned __int8 *)*((_QWORD *)v5 + 65);
    v57 = *v56;
    if ( (_BYTE)v57 != 17 && ndisNblContextVerifierMode && ndisNblContextVerifierMode != 3 && v56 )
    {
      if ( v57 == 5 )
      {
        LOBYTE(v58) = (*((_DWORD *)v56 + 14) & 0x400) != 0;
      }
      else
      {
        if ( v57 != 18 )
          return;
        v58 = *((_DWORD *)v56 + 56) >> 31;
      }
      if ( (_BYTE)v58 )
      {
        v101 = *((_QWORD *)v5 + 65);
        for ( k = NetBufferLists; k; k = (PNET_BUFFER_LIST)k->Link.Alignment )
        {
          if ( *(_QWORD *)&k->Context->ContextData[k->Context->Offset] != v101 )
            NblContextVerifierBugcheckContextCorruption(k, NetBufferLists, v101);
          NdisFreeNetBufferListContext(k, 8u);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x140026c50  mov     [rsp-8+arg_18], r9d
0x140026c55  mov     [rsp-8+arg_10], r8d
0x140026c5a  mov     [rsp-8+arg_0], rcx
0x140026c5f  push    rbp
0x140026c60  push    rbx
0x140026c61  push    rdi
0x140026c62  push    r13
0x140026c64  push    r14
0x140026c66  push    r15
0x140026c68  lea     rbp, [rsp-198h]
0x140026c70  sub     rsp, 298h
0x140026c77  mov     r14, rcx
0x140026c7a  mov     edi, r9d
0x140026c7d  mov     rcx, [rcx+208h]
0x140026c84  mov     r13d, r8d
0x140026c87  mov     r15, rdx
0x140026c8a  movzx   eax, byte ptr [rcx]
0x140026c8d  cmp     al, 11h
0x140026c8f  jnz     loc_140027388
0x140026c95  mov     eax, [r14+38h]
0x140026c99  mov     [rsp+2C0h+arg_8], rsi
0x140026ca1  bt      eax, 9
0x140026ca5  jnb     short loc_140026CD8
0x140026ca7  mov     eax, [r14+150h]
0x140026cae  mov     r8d, edi; unsigned int
0x140026cb1  mov     r9d, [rbp+1C0h+ReceiveFlags]; unsigned int
0x140026cb8  mov     edx, r13d; unsigned int
0x140026cbb  mov     [rsp+2C0h+var_298], eax; enum _NDIS_MEDIUM
0x140026cbf  mov     rcx, r15; struct _NET_BUFFER_LIST *
0x140026cc2  mov     [rsp+2C0h+Context], r14; struct _NDIS_OBJECT_HEADER *
0x140026cc7  call    ?ndisNblVerifyRxIndication@@YAXPEBU_NET_BUFFER_LIST@@KKKPEBU_NDIS_OBJECT_HEADER@@W4_NDIS_MEDIUM@@@Z; ndisNblVerifyRxIndication(_NET_BUFFER_LIST const *,ulong,ulong,ulong,_NDIS_OBJECT_HEADER const *,_NDIS_MEDIUM)
0x140026ccc  mov     rbx, r15
0x140026ccf  test    r15, r15
0x140026cd2  jnz     loc_14002813F
0x140026cd8  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x140026cde  test    eax, eax
0x140026ce0  jnz     loc_140026FB9
0x140026ce6  cmp     cs:byte_140123720, 0
0x140026ced  mov     esi, 28h ; '('
0x140026cf2  jnz     loc_140027756
0x140026cf8  mov     rax, [r14+278h]
0x140026cff  lea     rcx, ?ndisFilterIndicateReceiveNetBufferLists@@YAXPEAXPEAU_NET_BUFFER_LIST@@KKK@Z; ndisFilterIndicateReceiveNetBufferLists(void *,_NET_BUFFER_LIST *,ulong,ulong,ulong)
0x140026d06  cmp     rax, rcx
0x140026d09  jnz     loc_140028207
0x140026d0f  mov     ebx, gs:1A4h
0x140026d17  lea     r11, WPP_RECORDER_INITIALIZED
0x140026d1e  mov     rdi, [r14+1A8h]
0x140026d25  mov     eax, cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x140026d2b  mov     [rsp+2C0h+var_258], rdi
0x140026d30  mov     [rsp+2C0h+var_30], r12
0x140026d38  mov     [rsp+2C0h+var_270], ebx
0x140026d3c  test    eax, eax
0x140026d3e  jz      loc_140026F38
0x140026d44  mov     ecx, [rbp+1C0h+ReceiveFlags]
0x140026d4a  xor     edx, edx
0x140026d4c  mov     r10, [r14+288h]
0x140026d53  xor     r9d, r9d
0x140026d56  mov     rdi, [r14+200h]
0x140026d5d  mov     r13d, ecx
0x140026d60  mov     ebx, cs:?ndisNblTrackerEpoch@@3KA; ulong ndisNblTrackerEpoch
0x140026d66  and     r13d, 1
0x140026d6a  xor     r12d, r12d
0x140026d6d  mov     [rsp+2C0h+var_250], r10
0x140026d72  mov     [rsp+2C0h+var_268], rdx
0x140026d77  mov     [rsp+2C0h+var_278], r9
0x140026d7c  mov     [rsp+2C0h+var_280], dl
0x140026d80  cmp     eax, 3
0x140026d83  jl      short loc_140026DBA
0x140026d85  mov     r8d, edx
0x140026d88  mov     dword ptr [rsp+2C0h+Context], r13d; unsigned int
0x140026d8d  mov     eax, ecx
0x140026d8f  mov     r9, rdi; void *
0x140026d92  and     eax, 2
0x140026d95  mov     rdx, r10; struct NDIS_NBL_TRACKER_HANDLE__ *
0x140026d98  mov     rcx, r15; struct _NET_BUFFER_LIST *
0x140026d9b  setnz   r8b
0x140026d9f  add     r8d, 82h; unsigned int
0x140026da6  call    ?ndisNblTrackerRecordEventInternal@@YAXPEAU_NET_BUFFER_LIST@@PEAUNDIS_NBL_TRACKER_HANDLE__@@KPEAXK@Z; ndisNblTrackerRecordEventInternal(_NET_BUFFER_LIST *,NDIS_NBL_TRACKER_HANDLE__ *,ulong,void *,ulong)
0x140026dab  mov     r10, [rsp+2C0h+var_250]
0x140026db0  lea     r11, WPP_RECORDER_INITIALIZED
0x140026db7  mov     r9d, r12d
0x140026dba  mov     r8, rdi
0x140026dbd  and     r8, 0FFFFFFFFFFFFFFFDh
0x140026dc1  mov     [rsp+2C0h+var_260], r8
0x140026dc6  test    r8b, 1
0x140026dca  jz      loc_140027380
0x140026dd0  mov     rax, rbx
0x140026dd3  add     rax, rax
0x140026dd6  mov     rbx, rax
0x140026dd9  xor     rbx, rdi
0x140026ddc  and     rbx, 0FFFFFFFFFFFFFFFDh
0x140026de0  xor     rbx, rax
0x140026de3  and     r8, 0FFFFFFFFFFFFFFF8h
0x140026de7  mov     r8, [r8+18h]
0x140026deb  mov     [rsp+2C0h+var_260], r8
0x140026df0  mov     rsi, r15
0x140026df3  test    r15, r15
0x140026df6  jz      loc_140026EDE
0x140026dfc  mov     rdi, [rsi+168h]
0x140026e03  lea     r14, WPP_78a33c75b2d2335d1cf1dcc315edf7b8_Traceguids
0x140026e0a  cmp     [rsi+168h], rdi
0x140026e11  jnz     short loc_140026E5F
0x140026e13  test    rdi, rdi
0x140026e16  jz      loc_1400273DE
0x140026e1c  test    dil, 4
0x140026e20  jnz     loc_140027412
0x140026e26  mov     rcx, [rsi+78h]
0x140026e2a  test    rcx, rcx
0x140026e2d  jz      loc_140027405
0x140026e33  movzx   edx, byte ptr [rcx]
0x140026e36  lea     eax, [rdx-11h]
0x140026e39  cmp     al, 1
0x140026e3b  ja      loc_140027676
0x140026e41  cmp     rcx, r8
0x140026e44  jz      loc_140027360
0x140026e4a  inc     r12
0x140026e4d  mov     rax, rbx
0x140026e50  mov     [rsi+168h], rax
0x140026e57  mov     rsi, [rsi]
0x140026e5a  test    rsi, rsi
0x140026e5d  jnz     short loc_140026E0A
0x140026e5f  movzx   r14d, [rsp+2C0h+var_280]
0x140026e65  test    dil, 1
0x140026e69  jz      short loc_140026EB8
0x140026e6b  mov     r9, [rsp+2C0h+var_268]
0x140026e70  sub     r9, r12
0x140026e73  mov     [rsp+2C0h+var_268], r9
0x140026e78  jz      short loc_140026EB8
0x140026e7a  test    r13b, r13b
0x140026e7d  jz      loc_14002700A
0x140026e83  mov     rdx, rdi
0x140026e86  and     rdi, 0FFFFFFFFFFFFFFF8h
0x140026e8a  shr     rdx, 1
0x140026e8d  and     edx, 1
0x140026e90  add     rdx, 3
0x140026e94  shl     rdx, 4
0x140026e98  add     rdx, rdi
0x140026e9b  test    r13b, r13b
0x140026e9e  jz      loc_140027051
0x140026ea4  mov     eax, gs:1A4h
0x140026eac  shl     eax, 0Ch
0x140026eaf  mov     ecx, eax
0x140026eb1  mov     rax, [rdx]
0x140026eb4  add     [rcx+rax], r9
0x140026eb8  mov     r9, [rsp+2C0h+var_278]
0x140026ebd  lea     r11, WPP_RECORDER_INITIALIZED
0x140026ec4  mov     r10, [rsp+2C0h+var_250]
0x140026ec9  mov     [rsp+2C0h+var_268], r12
0x140026ece  test    rsi, rsi
0x140026ed1  jnz     loc_140026DFC
0x140026ed7  mov     r14, [rbp+1C0h+arg_0]
0x140026ede  test    bl, 1
0x140026ee1  jz      short loc_140026F28
0x140026ee3  sub     r12, [rsp+2C0h+var_278]
0x140026ee8  jz      short loc_140026F28
0x140026eea  test    r13b, r13b
0x140026eed  jz      loc_1400270C9
0x140026ef3  mov     rdx, rbx
0x140026ef6  and     rbx, 0FFFFFFFFFFFFFFF8h
0x140026efa  shr     rdx, 1
0x140026efd  and     edx, 1
0x140026f00  add     rdx, 3
0x140026f04  shl     rdx, 4
0x140026f08  add     rdx, rbx
0x140026f0b  test    r13b, r13b
0x140026f0e  jz      loc_140027100
0x140026f14  mov     eax, gs:1A4h
0x140026f1c  shl     eax, 0Ch
0x140026f1f  mov     ecx, eax
0x140026f21  mov     rax, [rdx]
0x140026f24  add     [rcx+rax], r12
0x140026f28  mov     rdi, [rsp+2C0h+var_258]
0x140026f2d  mov     ebx, [rsp+2C0h+var_270]
0x140026f31  mov     r13d, [rbp+1C0h+arg_10]
0x140026f38  mov     r12d, [rbp+1C0h+ReceiveFlags]
0x140026f3f  mov     esi, r12d
0x140026f42  and     esi, 2
0x140026f45  mov     dword ptr [rsp+2C0h+var_260], esi
0x140026f49  jz      loc_14002705B
0x140026f4f  mov     rdi, [r14+208h]
0x140026f56  mov     rbx, [r14+1F8h]
0x140026f5d  mov     r13, [r14+1F0h]
0x140026f64  mov     [rsp+2C0h+var_258], rbx
0x140026f69  cmp     byte ptr [rdi], 11h
0x140026f6c  jnz     loc_14002717F
0x140026f72  mov     r9d, [rbp+1C0h+arg_18]
0x140026f79  mov     rdx, r15
0x140026f7c  mov     r8d, [rbp+1C0h+arg_10]
0x140026f83  mov     rcx, rbx
0x140026f86  mov     rax, r13
0x140026f89  mov     dword ptr [rsp+2C0h+Context], r12d
0x140026f8e  call    _guard_dispatch_icall
0x140026f93  test    esi, esi
0x140026f95  jnz     loc_140027812
0x140026f9b  mov     r12, [rsp+2C0h+var_30]
0x140026fa3  test    esi, esi
0x140026fa5  mov     rsi, [rsp+2C0h+arg_8]
0x140026fad  jnz     loc_1400272E9
0x140026fb3  jmp     loc_14002822C
0x140026fb9  mov     rax, [r15+0F8h]
0x140026fc0  test    rax, rax
0x140026fc3  jnz     loc_140027115
0x140026fc9  mov     rdx, r15
0x140026fcc  mov     ecx, edi
0x140026fce  lock xadd cs:dword_140120E28, ecx
0x140026fd6  lea     eax, [rcx+rdi]
0x140026fd9  cmp     eax, ecx
0x140026fdb  jb      loc_14002815D
0x140026fe1  mov     rax, [rdx+0F8h]
0x140026fe8  test    rax, rax
0x140026feb  jnz     loc_1400273D3
0x140026ff1  mov     eax, ecx
0x140026ff3  inc     ecx
0x140026ff5  mov     [rdx+0F8h], rax
0x140026ffc  mov     rdx, [rdx]
0x140026fff  test    rdx, rdx
0x140027002  jz      loc_140026CE6
0x140027008  jmp     short loc_140026FE1
0x14002700a  test    r14b, r14b
0x14002700d  jnz     loc_140026E83
0x140027013  mov     [rsp+2C0h+var_280], 1
0x140027018  call    cs:__imp_KeGetCurrentIrql
0x14002701f  nop     dword ptr [rax+rax+00h]
0x140027024  mov     r8, [rsp+2C0h+var_260]
0x140027029  mov     rdx, rdi
0x14002702c  mov     r9, [rsp+2C0h+var_268]
0x140027031  and     rdi, 0FFFFFFFFFFFFFFF8h
0x140027035  shr     rdx, 1
0x140027038  and     edx, 1
0x14002703b  add     rdx, 3
0x14002703f  shl     rdx, 4
0x140027043  cmp     al, 2
0x140027045  jz      loc_14002710A
0x14002704b  xor     r13b, r13b
0x14002704e  add     rdx, rdi
0x140027051  lock add [rdx+8], r9
0x140027056  jmp     loc_140026EB8
0x14002705b  test    r12b, 1
0x14002705f  jz      loc_140027166
0x140027065  mov     eax, ebx
0x140027067  lea     rcx, [rax+rax*2]
0x14002706b  shl     rcx, 5
0x14002706f  cmp     byte ptr [rcx+rdi+40h], 0
0x140027074  jz      loc_140026F4F
0x14002707a  or      r12d, 1
0x14002707e  lea     rax, [rcx+rdi]
0x140027082  cmp     qword ptr [rcx+rdi+30h], 0
0x140027088  jnz     loc_1400276E1
0x14002708e  mov     [rcx+rdi+30h], r15
0x140027093  mov     [rax+38h], r15
0x140027097  mov     rcx, [r15]
0x14002709a  mov     qword ptr [r15+70h], 0
0x1400270a2  mov     [r15+84h], r12d
0x1400270a9  mov     [r15+8Ch], r13d
0x1400270b0  test    rcx, rcx
0x1400270b3  jz      loc_140026F9B
0x1400270b9  mov     r8d, [rbp+1C0h+arg_18]
0x1400270c0  mov     [rcx+70h], r8
0x1400270c4  jmp     loc_140026F9B
0x1400270c9  cmp     [rsp+2C0h+var_280], 0
0x1400270ce  jnz     loc_140026EF3
0x1400270d4  call    cs:__imp_KeGetCurrentIrql
0x1400270db  nop     dword ptr [rax+rax+00h]
0x1400270e0  mov     rdx, rbx
0x1400270e3  and     rbx, 0FFFFFFFFFFFFFFF8h
0x1400270e7  shr     rdx, 1
0x1400270ea  and     edx, 1
0x1400270ed  add     rdx, 3
0x1400270f1  shl     rdx, 4
0x1400270f5  add     rdx, rbx
0x1400270f8  cmp     al, 2
0x1400270fa  jz      loc_140026F14
0x140027100  lock add [rdx+8], r12
0x140027105  jmp     loc_140026F28
0x14002710a  mov     r13b, 1
0x14002710d  add     rdx, rdi
0x140027110  jmp     loc_140026EA4
0x140027115  js      loc_140026FC9
0x14002711b  mov     rcx, [r15]
0x14002711e  test    rcx, rcx
0x140027121  jz      loc_140026CE6
0x140027127  mov     rax, [rcx+0F8h]
0x14002712e  test    rax, rax
0x140027131  jnz     loc_1400275B9
0x140027137  mov     edx, 1
0x14002713c  lock xadd cs:dword_140120E28, edx
0x140027144  lea     eax, [rdx+1]
0x140027147  cmp     eax, edx
0x140027149  jb      loc_14002814B
0x14002714f  mov     eax, edx
0x140027151  mov     [rcx+0F8h], rax
0x140027158  mov     rcx, [rcx]
0x14002715b  test    rcx, rcx
0x14002715e  jz      loc_140026CE6
0x140027164  jmp     short loc_140027127
0x140027166  call    cs:__imp_KeGetCurrentIrql
0x14002716d  nop     dword ptr [rax+rax+00h]
0x140027172  cmp     al, 2
0x140027174  jnz     loc_140026F4F
0x14002717a  jmp     loc_140027065
  ... truncated ...
```
