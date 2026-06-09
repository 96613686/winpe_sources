# NdisMIndicateReceiveNetBufferLists

- ea: `0x1400285e0`
- end: `0x140029c25`
- name: `NdisMIndicateReceiveNetBufferLists`
- size: `5701`
- prototype: `void __stdcall(NDIS_HANDLE MiniportAdapterHandle, PNET_BUFFER_LIST NetBufferList, NDIS_PORT_NUMBER PortNumber, ULONG NumberOfNetBufferLists, ULONG ReceiveFlags)`
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140063190`

## callees

- `0x140010ff0`
- `0x1400110b0`
- `0x140011190`
- `0x1400260b0`
- `0x140028330`
- `0x1400285e0`
- `0x140029c30`
- `0x140029ce0`
- `0x1400334f0`
- `0x140037bb0`
- `0x140037bd0`
- `0x140038090`
- `0x14003a0e0`
- `0x14004b140`
- `0x140066620`
- `0x14007c2c0`
- `0x140080fb0`
- `0x1400843a0`
- `0x1400eb380`
- `0x1400eb460`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x1400292b5`
- `ntoskrnl!KeLowerIrql` at `0x1400292b5`
- `ntoskrnl!KeGetCurrentIrql` at `0x140028a8f`
- `ntoskrnl!KeGetCurrentIrql` at `0x140028c34`
- `ntoskrnl!KeGetCurrentIrql` at `0x140028ce1`
- `ntoskrnl!KeGetCurrentIrql` at `0x140028d2f`
- `ntoskrnl!KeGetCurrentIrql` at `0x140029957`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400299a2`
- `ntoskrnl!KeGetCurrentIrql` at `0x140028a8f`
- `ntoskrnl!KeGetCurrentIrql` at `0x140028c34`
- `ntoskrnl!KeGetCurrentIrql` at `0x140028ce1`
- `ntoskrnl!KeGetCurrentIrql` at `0x140028d2f`
- `ntoskrnl!KeGetCurrentIrql` at `0x140029957`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400299a2`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x1400287b0`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x1400287b0`
- `ntoskrnl!KfRaiseIrql` at `0x1400291da`
- `ntoskrnl!KfRaiseIrql` at `0x1400291da`
- `ntoskrnl!IoGetStackLimits` at `0x140028b00`
- `ntoskrnl!IoGetStackLimits` at `0x140028b00`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140028b7b`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140028b7b`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140029390`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140029549`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002961b`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x1400298cf`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140029390`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140029549`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002961b`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x1400298cf`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400293f2`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400295ab`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140029685`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140029930`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400293f2`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400295ab`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140029685`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140029930`
- `HAL!KeQueryPerformanceCounter` at `0x140029408`
- `HAL!KeQueryPerformanceCounter` at `0x140029408`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
void __stdcall NdisMIndicateReceiveNetBufferLists(
        NDIS_HANDLE MiniportAdapterHandle,
        PNET_BUFFER_LIST NetBufferList,
        NDIS_PORT_NUMBER PortNumber,
        ULONG NumberOfNetBufferLists,
        ULONG ReceiveFlags)
{
  bool v5; // zf
  ULONG v6; // r15d
  NDIS_PORT_NUMBER v7; // r10d
  PNET_BUFFER_LIST v8; // rdi
  NDIS_HANDLE v9; // rsi
  __int64 v10; // r12
  int v11; // ebx
  ULONG v12; // r14d
  __int64 v13; // r13
  __int64 v14; // rbx
  void (__fastcall *v15)(__int64, unsigned __int64, _QWORD, _QWORD, int); // r15
  __int64 v16; // r12
  __int64 v17; // rbx
  unsigned int v18; // r15d
  unsigned int v19; // r12d
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rdi
  int v23; // r13d
  unsigned int v24; // eax
  unsigned int v25; // edx
  unsigned int v26; // ecx
  ULONG v27; // r14d
  struct NDIS_NBL_TRACKER_HANDLE__ *v28; // rdx
  unsigned __int64 v29; // rbx
  __int64 v30; // r15
  ULONG v31; // r9d
  struct _NET_BUFFER_LIST *v32; // r12
  unsigned __int64 v33; // r13
  unsigned __int64 v34; // rbx
  _SLIST_HEADER *v35; // r15
  unsigned __int64 *v36; // r14
  unsigned __int64 Region; // rdi
  char *v38; // rcx
  __int64 v39; // rax
  unsigned __int64 v40; // r8
  __int64 v41; // rcx
  unsigned __int64 v42; // r12
  unsigned __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // rax
  __int64 v46; // rcx
  unsigned __int64 v47; // rdx
  struct _NET_BUFFER_LIST *v48; // rdi
  int v49; // ecx
  int v50; // r8d
  unsigned int v51; // ecx
  _SLIST_HEADER *v52; // rax
  _SLIST_HEADER *v53; // rdx
  unsigned int v54; // ecx
  unsigned __int64 v55; // rax
  __int64 v56; // rax
  unsigned int v57; // ecx
  KIRQL CurrentIrql; // al
  unsigned __int64 v59; // rdx
  unsigned __int64 v60; // rdi
  __int64 v61; // rdx
  KIRQL v62; // al
  __int64 v63; // rdx
  int v64; // eax
  __int64 v65; // rcx
  _QWORD *Alignment; // rcx
  __int64 v67; // rax
  unsigned int v68; // edx
  unsigned __int64 *v69; // rdx
  unsigned __int64 v70; // rcx
  unsigned __int64 v71; // rdi
  __int64 v72; // rax
  __int64 v73; // rcx
  unsigned __int64 v74; // rdi
  NDIS_PORT_NUMBER v75; // ecx
  unsigned int v76; // edx
  __int64 v77; // rax
  unsigned __int64 v78; // rdi
  int v79; // ecx
  unsigned int v80; // edx
  __int64 v81; // rax
  struct _NET_BUFFER_LIST *v82; // rax
  struct _NET_BUFFER_LIST *v83; // rdi
  unsigned __int64 v84; // rax
  __int64 v85; // rdx
  int v86; // eax
  unsigned int v87; // eax
  __int64 v88; // r8
  unsigned __int64 v89; // rax
  KIRQL v90; // al
  __int64 v91; // rax
  unsigned int v92; // ebx
  __int64 v93; // rdx
  LARGE_INTEGER *v94; // rbx
  LARGE_INTEGER PerformanceCounter; // rax
  int v96; // ecx
  unsigned int v97; // edx
  __int64 v98; // rax
  __int64 v99; // rax
  __int64 v100; // rdx
  __int64 v101; // rax
  __int64 v102; // rdx
  struct NDIS_NBL_TRACKER_HANDLE__ *v103; // rdx
  struct _NET_BUFFER_LIST *v104; // r13
  unsigned __int64 v105; // rbx
  __int64 v106; // r12
  PNET_BUFFER_LIST v107; // rdi
  unsigned __int64 v108; // rcx
  unsigned __int64 v109; // rbx
  struct _NET_BUFFER_LIST *v110; // r12
  void *v111; // rsi
  unsigned __int64 *v112; // r14
  unsigned __int64 v113; // rdi
  unsigned __int64 v114; // r15
  __int64 v115; // rax
  unsigned __int64 v116; // r8
  __int64 v117; // rcx
  unsigned __int64 v118; // r13
  unsigned __int64 v119; // rdx
  __int64 v120; // rcx
  __int64 v121; // rax
  __int64 v122; // rdx
  KIRQL v123; // al
  unsigned __int64 v124; // r8
  unsigned __int64 v125; // rdi
  __int64 v126; // r8
  KIRQL v127; // al
  __int64 v128; // rax
  __int64 v129; // r8
  __int64 v130; // r8
  __int64 v131; // r8
  char v132; // [rsp+60h] [rbp-A0h]
  char v133; // [rsp+60h] [rbp-A0h]
  unsigned int v134; // [rsp+68h] [rbp-98h] BYREF
  struct _NET_BUFFER_LIST *v135; // [rsp+70h] [rbp-90h] BYREF
  KIRQL v136; // [rsp+78h] [rbp-88h]
  ULONG v137; // [rsp+7Ch] [rbp-84h]
  NDIS_PORT_NUMBER v138; // [rsp+80h] [rbp-80h]
  unsigned __int64 v139; // [rsp+88h] [rbp-78h]
  PNET_BUFFER_LIST NetBufferLista; // [rsp+90h] [rbp-70h]
  unsigned __int64 *v141; // [rsp+98h] [rbp-68h]
  unsigned __int64 LowLimit; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int64 HighLimit; // [rsp+A8h] [rbp-58h] BYREF
  __int128 Parameter; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v145; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v146; // [rsp+D0h] [rbp-30h]
  ULONG v147; // [rsp+D8h] [rbp-28h]
  int v148; // [rsp+DCh] [rbp-24h]
  unsigned int Number; // [rsp+E0h] [rbp-20h]
  NDIS_HANDLE v150; // [rsp+E8h] [rbp-18h]
  __int64 v151; // [rsp+F0h] [rbp-10h]
  _DWORD *v152; // [rsp+F8h] [rbp-8h]
  unsigned __int64 v153; // [rsp+100h] [rbp+0h]
  int v154; // [rsp+108h] [rbp+8h]
  _QWORD v155[3]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE WatchdogInformation[32]; // [rsp+128h] [rbp+28h] BYREF
  __int64 v157; // [rsp+148h] [rbp+48h]
  _UNKNOWN *retaddr; // [rsp+1A8h] [rbp+A8h] BYREF
  ULONG ReceiveFlagsa; // [rsp+1D0h] [rbp+D0h]

  v5 = *((_DWORD *)MiniportAdapterHandle + 12) == 0;
  v6 = NumberOfNetBufferLists;
  v137 = NumberOfNetBufferLists;
  v7 = PortNumber;
  v138 = PortNumber;
  v8 = NetBufferList;
  NetBufferLista = NetBufferList;
  v9 = MiniportAdapterHandle;
  v150 = MiniportAdapterHandle;
  v135 = NetBufferList;
  v134 = NumberOfNetBufferLists;
  if ( !v5 || (v10 = 0, LOBYTE(v11) = 0, v151 = 0, *((_DWORD *)MiniportAdapterHandle + 20)) )
  {
    v10 = *((_QWORD *)MiniportAdapterHandle + 5);
    v11 = *((_DWORD *)MiniportAdapterHandle + 20);
    v151 = v10;
    if ( !v10 )
    {
      v10 = *((_QWORD *)MiniportAdapterHandle + 5);
      v151 = v10;
    }
  }
  v12 = ReceiveFlags;
  if ( !ndisNblContextVerifierMode )
    goto LABEL_4;
  if ( ndisNblContextVerifierMode == 3 )
    goto LABEL_4;
  v63 = *((_QWORD *)MiniportAdapterHandle + 314);
  if ( !v63 )
    goto LABEL_4;
  switch ( *(_BYTE *)v63 )
  {
    case 5:
      v64 = *(_DWORD *)(v63 + 56) >> 10;
      break;
    case 0x11:
      v64 = *(_DWORD *)(v63 + 3688) >> 12;
      break;
    case 0x12:
      v64 = *(_DWORD *)(v63 + 224) >> 31;
      goto LABEL_146;
    default:
      goto LABEL_4;
  }
  LOBYTE(v64) = v64 & 1;
LABEL_146:
  if ( (_BYTE)v64 )
  {
    v82 = ndisAddNblContextTerminator(&v135, &v134, *((struct _NDIS_OBJECT_HEADER **)MiniportAdapterHandle + 314));
    v83 = v82;
    if ( v82 )
    {
      if ( byte_140123720 && (*((_DWORD *)v9 + 1468) & 2) != 0 )
        PktMonClientNblDropNdis((_DWORD)v9 + 5816, (_DWORD)v82, PortNumber, 1, -1073741670, -536866800);
      if ( (ReceiveFlags & 2) == 0 )
        ndisCallPreviousReturnHandler((struct _NDIS_OBJECT_HEADER *)v9, v83, ReceiveFlags);
      v8 = v135;
      NetBufferLista = v135;
      if ( !v135 )
        return;
    }
    else
    {
      v8 = v135;
      NetBufferLista = v135;
    }
    v6 = v134;
    v7 = v138;
    v137 = v134;
  }
LABEL_4:
  v5 = (*((_DWORD *)v9 + 922) & 0x800) == 0;
  Number = -1;
  v136 = 2;
  if ( !v5 )
  {
    ndisNblVerifyRxIndication(
      v8,
      v7,
      v6,
      ReceiveFlags,
      (const struct _NDIS_OBJECT_HEADER *)v9,
      *((enum _NDIS_MEDIUM *)v9 + 459));
    ndisNblPoisonScratchFields(v8);
  }
  v154 = v11 & 4;
  if ( (v11 & 4) != 0 )
  {
    if ( (ReceiveFlags & 1) == 0 )
      v136 = KfRaiseIrql(2u);
    Number = KeGetPcr()->Prcb.Number;
    *(_QWORD *)&PortNumber = ndisPcwOffsetToPerCpuData;
    *(_QWORD *)(ndisPcwOffsetToPerCpuData + v10 + ndisPcwPerCpuDataStride * Number + 320) = __rdtsc();
  }
  if ( (*((_DWORD *)v9 + 670) & 1) != 0 )
  {
    v94 = (LARGE_INTEGER *)v8;
    PerformanceCounter = KeQueryPerformanceCounter(0);
    if ( v8 )
    {
      do
      {
        v94[44] = PerformanceCounter;
        v94 = (LARGE_INTEGER *)v94->QuadPart;
      }
      while ( v94 );
    }
  }
  if ( !*((_BYTE *)v9 + 2664) )
  {
    ndisMDummyReceiveNetBufferLists(v9, v8, PortNumber, NumberOfNetBufferLists, ReceiveFlags);
    v27 = ReceiveFlags & 2;
    goto LABEL_29;
  }
  if ( Microsoft_Windows_Networking_CorrelationEnabled )
  {
    if ( (__int64)v8->NetBufferListInfo[13] > 0 )
    {
      Alignment = (_QWORD *)v8->Link.Alignment;
      if ( v8->Link.Alignment )
      {
        do
        {
          v67 = Alignment[31];
          if ( !v67 || v67 < 0 )
          {
            v68 = _InterlockedExchangeAdd(&dword_140120E28, 1u);
            if ( v68 + 1 < v68 )
              v68 = _InterlockedExchangeAdd(&dword_140120E28, 1u);
            Alignment[31] = v68;
          }
          Alignment = (_QWORD *)*Alignment;
        }
        while ( Alignment );
      }
    }
    else
    {
      v53 = (_SLIST_HEADER *)v8;
      v54 = _InterlockedExchangeAdd(&dword_140120E28, v6);
      if ( v54 + v6 < v54 )
        v54 = _InterlockedExchangeAdd(&dword_140120E28, v6);
      do
      {
        if ( (__int64)v53[15].Region <= 0 )
        {
          v55 = v54++;
          v53[15].Region = v55;
        }
        v53 = (_SLIST_HEADER *)v53->Alignment;
      }
      while ( v53 );
    }
  }
  if ( !*(_DWORD *)ndisNblTrackerMode )
    goto LABEL_11;
  v28 = (struct NDIS_NBL_TRACKER_HANDLE__ *)*((_QWORD *)v9 + 510);
  v29 = *((_QWORD *)v9 + 313);
  *(_QWORD *)&PortNumber = 0;
  v30 = ndisNblTrackerEpoch;
  v31 = ReceiveFlags & 1;
  v141 = (unsigned __int64 *)v28;
  v32 = 0;
  v134 = v31;
  v135 = 0;
  v139 = 0;
  v132 = 0;
  if ( *(int *)ndisNblTrackerMode >= 3 )
  {
    ndisNblTrackerRecordEventInternal(v8, v28, (ReceiveFlags & 2 | 0x100) >> 1, (void *)v29, v31);
    LOBYTE(v31) = v134;
    *(_QWORD *)&PortNumber = 0;
  }
  v33 = v29 & 0xFFFFFFFFFFFFFFFDuLL;
  if ( (v29 & 1) != 0 )
  {
    v34 = (2 * v30) ^ ((2 * v30) ^ v29) & 0xFFFFFFFFFFFFFFFDuLL;
    v33 = *(_QWORD *)((v33 & 0xFFFFFFFFFFFFFFF8uLL) + 24);
  }
  else
  {
    v34 = v29 & 0xFFFFFFFFFFFFFFFDuLL;
  }
  v35 = (_SLIST_HEADER *)v8;
  if ( v8 )
  {
    v36 = v141;
    while ( 1 )
    {
      Region = v35[22].Region;
      while ( v35[22].Region == Region )
      {
        if ( Region )
        {
          if ( (Region & 4) != 0 )
            goto LABEL_164;
        }
        else if ( !v35[7].Region )
        {
          v84 = (unsigned __int64)v36 & 0xFFFFFFFFFFFFFFFDuLL;
          if ( ((unsigned __int8)v36 & 1) != 0 )
            v84 = *(_QWORD *)(((unsigned __int64)v36 & 0xFFFFFFFFFFFFFFF8uLL) + 24);
          v35[7].Region = v84;
        }
        v38 = (char *)v35[7].Region;
        if ( v38 )
        {
          LODWORD(v28) = (unsigned __int8)*v38;
          if ( (unsigned __int8)((_BYTE)v28 - 17) <= 1u || (_BYTE)v28 == 5 )
          {
            if ( v38 != (char *)v33 || v35[1].Region )
            {
              v32 = (struct _NET_BUFFER_LIST *)((char *)v32 + 1);
              v39 = v34;
            }
            else
            {
              ++*(_QWORD *)&PortNumber;
              v39 = 24;
              v139 = *(_QWORD *)&PortNumber;
              v32 = (struct _NET_BUFFER_LIST *)((char *)v32 + 1);
            }
            goto LABEL_47;
          }
          if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v28) = 3;
            WPP_RECORDER_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              (int)v28,
              27,
              12,
              (struct _GUID *)&WPP_78a33c75b2d2335d1cf1dcc315edf7b8_Traceguids,
              (char)v35,
              *v38);
LABEL_290:
            *(_QWORD *)&PortNumber = v139;
          }
        }
        else if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v28) = 3;
          WPP_RECORDER_SF_q(
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            (int)v28,
            27,
            11,
            (struct _GUID *)&WPP_78a33c75b2d2335d1cf1dcc315edf7b8_Traceguids,
            (char)v35);
          goto LABEL_290;
        }
LABEL_164:
        v39 = v34 | 4;
LABEL_47:
        v35[22].Region = v39;
        v35 = (_SLIST_HEADER *)v35->Alignment;
        if ( !v35 )
          break;
      }
      LOBYTE(v31) = v134;
      if ( (Region & 1) == 0 )
        goto LABEL_53;
      v40 = (char *)v135 - (char *)v32;
      v135 = (struct _NET_BUFFER_LIST *)((char *)v135 - (__int64)v32);
      if ( !v135 )
        goto LABEL_53;
      if ( (_BYTE)v134 || v132 )
      {
        v28 = (struct NDIS_NBL_TRACKER_HANDLE__ *)((Region & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((Region >> 1) & 1) + 3));
        if ( !(_BYTE)v134 )
          goto LABEL_90;
        goto LABEL_52;
      }
      v132 = 1;
      CurrentIrql = KeGetCurrentIrql();
      v40 = (unsigned __int64)v135;
      v59 = Region >> 1;
      v60 = Region & 0xFFFFFFFFFFFFFFF8uLL;
      v61 = 16 * ((v59 & 1) + 3);
      if ( CurrentIrql == 2 )
      {
        LOBYTE(v31) = 1;
        v28 = (struct NDIS_NBL_TRACKER_HANDLE__ *)(v60 + v61);
        v134 = v31;
LABEL_52:
        v41 = KeGetPcr()->Prcb.Number << 12;
        *(_QWORD *)(v41 + *(_QWORD *)v28) += v40;
        goto LABEL_53;
      }
      LOBYTE(v31) = 0;
      v134 = v31;
      v28 = (struct NDIS_NBL_TRACKER_HANDLE__ *)(v60 + v61);
LABEL_90:
      _InterlockedAdd64((volatile signed __int64 *)v28 + 1, v40);
LABEL_53:
      *(_QWORD *)&PortNumber = v139;
      v135 = v32;
      if ( !v35 )
      {
        v9 = v150;
        v12 = ReceiveFlags;
        v8 = NetBufferLista;
        break;
      }
    }
  }
  if ( (v34 & 1) != 0 )
  {
    v42 = (unsigned __int64)v32 - v139;
    if ( v42 )
    {
      if ( (_BYTE)v31 || v132 )
      {
        v43 = (v34 & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((v34 >> 1) & 1) + 3);
        if ( !(_BYTE)v31 )
        {
LABEL_93:
          _InterlockedAdd64((volatile signed __int64 *)(v43 + 8), v42);
          goto LABEL_11;
        }
      }
      else
      {
        v62 = KeGetCurrentIrql();
        v43 = (v34 & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((v34 >> 1) & 1) + 3);
        if ( v62 != 2 )
          goto LABEL_93;
      }
      v44 = KeGetPcr()->Prcb.Number << 12;
      *(_QWORD *)(v44 + *(_QWORD *)v43) += v42;
    }
  }
LABEL_11:
  if ( byte_140123720 )
  {
    v91 = *((_QWORD *)v9 + 738);
    if ( v91 )
    {
      if ( (*(_DWORD *)(v91 + 56) & 1) != 0 )
      {
        v5 = (v8->NblFlags & 0x8000) == 0;
        memset(WatchdogInformation, 0, sizeof(WatchdogInformation));
        LODWORD(v157) = 0;
        if ( v5 )
        {
          v92 = *((_DWORD *)v9 + 1478);
          if ( ExAcquireRundownProtectionCacheAware(RunRefCacheAware) )
          {
            v93 = *((_QWORD *)v9 + 737);
            strcpy(WatchdogInformation, "(");
            *(_QWORD *)&WatchdogInformation[8] = v8;
            *(_DWORD *)&WatchdogInformation[16] = 1;
            *(_QWORD *)&WatchdogInformation[20] = v92 | 0x100000000LL;
            v157 = 0;
            (*(void (__fastcall **)(_QWORD, __int64, _BYTE *, _QWORD))(*((_QWORD *)&xmmword_140123740 + 1) + 40LL))(
              xmmword_140123740,
              v93,
              WatchdogInformation,
              0);
            ExReleaseRundownProtectionCacheAware(RunRefCacheAware);
          }
        }
      }
    }
  }
  v13 = MEMORY[0xFFFFF78000000320];
  v14 = *((_QWORD *)v9 + 314);
  v15 = (void (__fastcall *)(__int64, unsigned __int64, _QWORD, _QWORD, int))*((_QWORD *)v9 + 328);
  v16 = *((_QWORD *)v9 + 312);
  if ( *(_BYTE *)v14 == 17 )
    goto LABEL_13;
  v45 = v12 & 2;
  LODWORD(v139) = v12 & 2;
  if ( (v12 & 2) == 0 && ((v12 & 1) != 0 || KeGetCurrentIrql() == 2) )
  {
    LODWORD(v45) = KeGetPcr()->Prcb.Number;
    v69 = v155;
    v8->Status = v138;
    v70 = v8->Link.Alignment;
    LODWORD(v139) = v45;
    v155[2] = 0;
    v141 = v155;
    v155[0] = v8;
    v155[1] = v8;
    v8->Scratch = 0;
    v8->ChildRefCount = v12;
    if ( v70 )
      *(_QWORD *)(v70 + 112) = v137;
    while ( *(_BYTE *)v14 == 5 )
    {
      v71 = *v69;
      if ( !*v69 )
        break;
      v72 = 96 * v45 + *(_QWORD *)(v14 + 424) + 48LL;
      v152 = (_DWORD *)v72;
      if ( *(_BYTE *)(v72 + 16) )
      {
        *v69 = 0;
        do
        {
          v96 = *(_DWORD *)(v71 + 132);
          v97 = *(_DWORD *)(v71 + 140);
          LowLimit = *(_QWORD *)(v71 + 112);
          v98 = *(_QWORD *)v71;
          LODWORD(v135) = v96;
          LODWORD(v139) = v97;
          if ( v98 )
            v134 = *(_DWORD *)(v98 + 112);
          else
            v134 = 1;
          *(_DWORD *)(v71 + 132) = 0;
          if ( byte_140123720 )
          {
            if ( *(_BYTE *)v14 == 5 )
            {
              v128 = *(_QWORD *)(v14 + 872);
              if ( v128 )
              {
                if ( (*(_DWORD *)(v128 + 56) & 1) != 0 )
                {
                  PktMonClientNblLogNdis(v14 + 848, v71, *(_QWORD *)&PortNumber, 1);
                  v96 = (int)v135;
                  v97 = v139;
                }
              }
            }
          }
          if ( ndisVerifierNdisDispatch && *(_BYTE *)v14 == 5 && (v131 = *(_QWORD *)(v14 + 776)) != 0 )
            (*((void (__fastcall **)(__int64, unsigned __int64, _QWORD, _QWORD, int, __int64, void (__fastcall *)(__int64, unsigned __int64, _QWORD, _QWORD, int)))ndisVerifierNdisDispatch
             + 14))(
              v16,
              v71,
              v97,
              v134,
              v96,
              v131,
              v15);
          else
            v15(v16, v71, v97, v134, v96);
          v71 = LowLimit;
        }
        while ( LowLimit );
        v69 = v141;
        break;
      }
      *(_BYTE *)(v72 + 16) = 1;
      v73 = v14;
      v74 = *v69;
      *v69 = 0;
      if ( v74 )
      {
        do
        {
          v75 = *(_DWORD *)(v74 + 132);
          v76 = *(_DWORD *)(v74 + 140);
          v153 = *(_QWORD *)(v74 + 112);
          v77 = *(_QWORD *)v74;
          v138 = v75;
          LODWORD(v141) = v76;
          if ( v77 )
            v134 = *(_DWORD *)(v77 + 112);
          else
            v134 = 1;
          *(_DWORD *)(v74 + 132) = 0;
          if ( byte_140123720 )
          {
            if ( *(_BYTE *)v14 == 5 )
            {
              v99 = *(_QWORD *)(v14 + 872);
              if ( v99 )
              {
                if ( (*(_DWORD *)(v99 + 56) & 1) != 0 )
                {
                  v5 = (*(_DWORD *)(v74 + 128) & 0x8000) == 0;
                  Parameter = 0;
                  LODWORD(v146) = 0;
                  v145 = 0;
                  if ( v5 )
                  {
                    LODWORD(v135) = *(_DWORD *)(v14 + 880);
                    if ( ExAcquireRundownProtectionCacheAware(RunRefCacheAware) )
                    {
                      v100 = *(_QWORD *)(v14 + 864);
                      *(_QWORD *)((char *)&v145 + 4) = (unsigned int)v135 | 0x100000000LL;
                      LOWORD(Parameter) = 40;
                      *((_QWORD *)&Parameter + 1) = v74;
                      LODWORD(v145) = 1;
                      v146 = 0;
                      (*(void (__fastcall **)(_QWORD, __int64, __int128 *, _QWORD))(*((_QWORD *)&xmmword_140123740 + 1)
                                                                                  + 40LL))(
                        xmmword_140123740,
                        v100,
                        &Parameter,
                        0);
                      ExReleaseRundownProtectionCacheAware(RunRefCacheAware);
                    }
                    v76 = (unsigned int)v141;
                    v75 = v138;
                  }
                }
              }
            }
          }
          if ( ndisVerifierNdisDispatch && *(_BYTE *)v14 == 5 && (v129 = *(_QWORD *)(v14 + 776)) != 0 )
            (*((void (__fastcall **)(__int64, unsigned __int64, _QWORD, _QWORD, NDIS_PORT_NUMBER, __int64, void (__fastcall *)(__int64, unsigned __int64, _QWORD, _QWORD, int)))ndisVerifierNdisDispatch
             + 14))(
              v16,
              v74,
              v76,
              v134,
              v75,
              v129,
              v15);
          else
            v15(v16, v74, v76, v134, v75);
          v74 = v153;
        }
        while ( v153 );
        LOBYTE(v12) = ReceiveFlags;
        v73 = v14;
        v72 = (__int64)v152;
      }
      *(_BYTE *)(v72 + 16) = 0;
      v69 = (unsigned __int64 *)v72;
      v14 = *(_QWORD *)(v14 + 520);
      v15 = *(void (__fastcall **)(__int64, unsigned __int64, _QWORD, _QWORD, int))(v73 + 496);
      v16 = *(_QWORD *)(v73 + 504);
      v141 = (unsigned __int64 *)v72;
      v45 = (unsigned int)v139;
    }
    v78 = *v69;
    if ( *v69 )
    {
      *v69 = 0;
      do
      {
        v79 = *(_DWORD *)(v78 + 132);
        v80 = *(_DWORD *)(v78 + 140);
        LowLimit = *(_QWORD *)(v78 + 112);
        v81 = *(_QWORD *)v78;
        LODWORD(v139) = v79;
        LODWORD(v141) = v80;
        if ( v81 )
          v134 = *(_DWORD *)(v81 + 112);
        else
          v134 = 1;
        *(_DWORD *)(v78 + 132) = 0;
        if ( byte_140123720 )
        {
          if ( *(_BYTE *)v14 == 5 )
          {
            v121 = *(_QWORD *)(v14 + 872);
            if ( v121 )
            {
              if ( (*(_DWORD *)(v121 + 56) & 1) != 0 )
              {
                v5 = (*(_DWORD *)(v78 + 128) & 0x8000) == 0;
                Parameter = 0;
                LODWORD(v146) = 0;
                v145 = 0;
                if ( v5 )
                {
                  LODWORD(v135) = *(_DWORD *)(v14 + 880);
                  if ( ExAcquireRundownProtectionCacheAware(RunRefCacheAware) )
                  {
                    v122 = *(_QWORD *)(v14 + 864);
                    *(_QWORD *)((char *)&v145 + 4) = (unsigned int)v135 | 0x100000000LL;
                    LOWORD(Parameter) = 40;
                    *((_QWORD *)&Parameter + 1) = v78;
                    LODWORD(v145) = 1;
                    v146 = 0;
                    (*(void (__fastcall **)(_QWORD, __int64, __int128 *, _QWORD))(*((_QWORD *)&xmmword_140123740 + 1)
                                                                                + 40LL))(
                      xmmword_140123740,
                      v122,
                      &Parameter,
                      0);
                    ExReleaseRundownProtectionCacheAware(RunRefCacheAware);
                  }
                  v80 = (unsigned int)v141;
                  v79 = v139;
                }
              }
            }
          }
        }
        if ( ndisVerifierNdisDispatch && *(_BYTE *)v14 == 5 && (v130 = *(_QWORD *)(v14 + 776)) != 0 )
          (*((void (__fastcall **)(__int64, unsigned __int64, _QWORD, _QWORD, int, __int64, void (__fastcall *)(__int64, unsigned __int64, _QWORD, _QWORD, int)))ndisVerifierNdisDispatch
           + 14))(
            v16,
            v78,
            v80,
            v134,
            v79,
            v130,
            v15);
        else
          v15(v16, v78, v80, v134, v79);
        v78 = LowLimit;
      }
      while ( LowLimit );
      v9 = v150;
    }
    goto LABEL_14;
  }
  LODWORD(v135) = Size;
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
  if ( (unsigned __int64)&retaddr - v47 < (unsigned int)v135 )
  {
    v48 = NetBufferLista;
    v146 = __PAIR64__(v137, v138);
    v49 = 24576;
    v148 = 0;
    *(_QWORD *)&Parameter = v14;
    *((_QWORD *)&Parameter + 1) = v16;
    *(_QWORD *)&v145 = v15;
    *((_QWORD *)&v145 + 1) = NetBufferLista;
    v147 = v12;
    if ( (unsigned int)Size > 0x6000 )
      v49 = Size;
    if ( KeExpandKernelStackAndCalloutEx(
           ndisDataPathExpandStackCallback<2,void (void *,_NET_BUFFER_LIST *,unsigned long,unsigned long,unsigned long)>,
           &Parameter,
           v49,
           0,
           0) < 0 )
    {
      if ( byte_140123720 && (*(_DWORD *)(v14 + 840) & 2) != 0 )
        PktMonClientNblDropNdis(v14 + 784, (_DWORD)v48, v50, 1, -1073741670, -536866813);
      NdisSetStatusInNblChain(v48, -1073741670);
      v51 = 0;
      v52 = (_SLIST_HEADER *)v48;
      if ( v48 )
      {
        do
        {
          v52 = (_SLIST_HEADER *)v52->Alignment;
          ++v51;
        }
        while ( v52 );
      }
      _InterlockedAdd((volatile signed __int32 *)(v14 + 292), v51);
      if ( !(_DWORD)v139 )
        ndisQueueStackExpansionFallbackNbls((struct _NDIS_FILTER_BLOCK *)v14, v48, 0);
    }
    goto LABEL_14;
  }
  if ( byte_140123720 && *(_BYTE *)v14 == 5 && (v101 = *(_QWORD *)(v14 + 872)) != 0 )
  {
    v8 = NetBufferLista;
    if ( (*(_DWORD *)(v101 + 56) & 1) != 0 )
    {
      v5 = (NetBufferLista->NblFlags & 0x8000) == 0;
      Parameter = 0;
      LODWORD(v146) = 0;
      v145 = 0;
      if ( v5 )
      {
        LODWORD(v135) = *(_DWORD *)(v14 + 880);
        if ( ExAcquireRundownProtectionCacheAware(RunRefCacheAware) )
        {
          v102 = *(_QWORD *)(v14 + 864);
          LOWORD(Parameter) = 40;
          *(_QWORD *)((char *)&v145 + 4) = (unsigned int)v135 | 0x100000000LL;
          *((_QWORD *)&Parameter + 1) = v8;
          LODWORD(v145) = 1;
          v146 = 0;
          (*(void (__fastcall **)(_QWORD, __int64, __int128 *, _QWORD))(*((_QWORD *)&xmmword_140123740 + 1) + 40LL))(
            xmmword_140123740,
            v102,
            &Parameter,
            0);
          ExReleaseRundownProtectionCacheAware(RunRefCacheAware);
        }
      }
    }
  }
  else
  {
    v8 = NetBufferLista;
  }
  if ( ndisVerifierNdisDispatch && *(_BYTE *)v14 == 5 && (v65 = *(_QWORD *)(v14 + 776)) != 0 )
    (*((void (__fastcall **)(__int64, PNET_BUFFER_LIST, _QWORD, _QWORD, ULONG, __int64, void (__fastcall *)(__int64, unsigned __int64, _QWORD, _QWORD, int)))ndisVerifierNdisDispatch
     + 14))(
      v16,
      v8,
      v138,
      v137,
      v12,
      v65,
      v15);
  else
LABEL_13:
    v15(v16, (unsigned __int64)v8, v138, v137, v12);
LABEL_14:
  v17 = (MEMORY[0xFFFFF78000000320] - v13) * ndisTimeIncrement / 10000;
  v18 = v12 & 1;
  v134 = v18;
  if ( (v12 & 1) != 0 || KeGetCurrentIrql() == 2 )
  {
    v19 = 512;
    memset(WatchdogInformation, 0, 20);
    v20 = KeGetPcr()->Prcb.Number << 12;
    v21 = *((_QWORD *)v9 + 412);
    LODWORD(v139) = 512;
    LowLimit = v20 + v21;
    v22 = *(unsigned int *)(v20 + v21);
    v23 = *((_DWORD *)&ndisPeriodicReceivesNblCounts + v22);
    v152 = (_DWORD *)&ndisPeriodicReceivesNblCounts + v22;
    if ( KeQueryDpcWatchdogInformation((PKDPC_WATCHDOG_INFORMATION)WatchdogInformation) < 0 )
    {
      LOBYTE(v25) = 0;
    }
    else
    {
      if ( *(_DWORD *)WatchdogInformation )
        v19 = v23 * (1024 - (*(_DWORD *)&WatchdogInformation[4] << 10) / *(_DWORD *)WatchdogInformation) / v137;
      if ( *(_DWORD *)&WatchdogInformation[8] )
      {
        v24 = (*(_DWORD *)&WatchdogInformation[12] << 10) / *(_DWORD *)&WatchdogInformation[8];
        if ( v24 > 0x200 )
          v24 = 1024;
        v25 = v23 * (1024 - v24) / v137;
      }
      else
      {
        LOBYTE(v25) = v139;
      }
    }
    v26 = v22 + 1;
    if ( (unsigned int)(v22 + 1) < 0xB && v19 < 0x200
      || (_DWORD)v22 && v19 > 0x300 && (v26 = v22 - 1, (_DWORD)v22 != 12) )
    {
      *(_DWORD *)LowLimit = v26;
      if ( (byte_140121005 & 2) != 0 )
      {
        v56 = v26;
        v57 = KeGetPcr()->Prcb.Number;
        McTemplateK0qqqqqqqq_EtwWriteTransfer(
          v57,
          (unsigned int)&ndisPeriodicReceivesNblCounts,
          (_DWORD)v9 + 4008,
          (*((_QWORD *)v9 + 503) >> 24) & 0xFFFFFF,
          v57,
          v137,
          v17,
          *v152,
          *((_DWORD *)&ndisPeriodicReceivesNblCounts + v56),
          v19,
          v25);
      }
    }
  }
  v27 = v12 & 2;
  ReceiveFlagsa = v27;
  if ( !v27 || !*(_DWORD *)ndisNblTrackerMode )
    goto LABEL_26;
  v103 = (struct NDIS_NBL_TRACKER_HANDLE__ *)*((_QWORD *)v9 + 313);
  v104 = 0;
  v105 = *((_QWORD *)v9 + 510);
  v106 = ndisNblTrackerEpoch;
  v107 = NetBufferLista;
  LowLimit = (unsigned __int64)v103;
  v135 = 0;
  v141 = 0;
  v133 = 0;
  if ( *(int *)ndisNblTrackerMode >= 3 )
    ndisNblTrackerRecordEventInternal(NetBufferLista, v103, 0x8Eu, (void *)v105, v18);
  v108 = v105 & 0xFFFFFFFFFFFFFFFDuLL;
  v139 = v105 & 0xFFFFFFFFFFFFFFFDuLL;
  if ( (v105 & 1) != 0 )
  {
    v109 = (2 * v106) ^ ((2 * v106) ^ v105) & 0xFFFFFFFFFFFFFFFDuLL;
    v139 = *(_QWORD *)((v108 & 0xFFFFFFFFFFFFFFF8uLL) + 24);
  }
  else
  {
    v109 = v105 & 0xFFFFFFFFFFFFFFFDuLL;
  }
  v110 = v107;
  if ( v107 )
  {
    v111 = (void *)v139;
    v112 = 0;
    while ( 1 )
    {
      v113 = (unsigned __int64)v110->NetBufferListInfo[27];
      v114 = LowLimit;
      while ( v110->NetBufferListInfo[27] == (void *)v113 )
      {
        if ( v113 )
        {
          if ( (v113 & 4) != 0 )
            goto LABEL_270;
        }
        else if ( !v110->SourceHandle )
        {
          v110->SourceHandle = (void *)ndisSourceHandleFromOwner(v114 & 0xFFFFFFFFFFFFFFFDuLL);
        }
        if ( ndisNblTrackerCanNblBeTracked(v110) )
        {
          if ( v110->SourceHandle != v111 || v110->ParentNetBufferList )
          {
            v104 = (struct _NET_BUFFER_LIST *)((char *)v104 + 1);
            v115 = v109;
          }
          else
          {
            v112 = (unsigned __int64 *)((char *)v112 + 1);
            v115 = 24;
            v104 = (struct _NET_BUFFER_LIST *)((char *)v104 + 1);
          }
          goto LABEL_233;
        }
LABEL_270:
        v115 = v109 | 4;
LABEL_233:
        v110->NetBufferListInfo[27] = (void *)v115;
        v110 = (struct _NET_BUFFER_LIST *)v110->Link.Alignment;
        if ( !v110 )
          break;
      }
      v18 = v134;
      v141 = v112;
      if ( (v113 & 1) == 0 )
        goto LABEL_239;
      v135 = (struct _NET_BUFFER_LIST *)((char *)v135 - (__int64)v104);
      if ( !v135 )
        goto LABEL_239;
      if ( (_BYTE)v134 || v133 )
      {
        v116 = (v113 & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((v113 >> 1) & 1) + 3);
        if ( !(_BYTE)v134 )
          goto LABEL_259;
        goto LABEL_238;
      }
      v133 = 1;
      v123 = KeGetCurrentIrql();
      v124 = v113;
      v125 = v113 & 0xFFFFFFFFFFFFFFF8uLL;
      v126 = 16 * (((v124 >> 1) & 1) + 3);
      if ( v123 == 2 )
      {
        LOBYTE(v18) = 1;
        v116 = v125 + v126;
        v134 = v18;
LABEL_238:
        v117 = KeGetPcr()->Prcb.Number << 12;
        *(_QWORD *)(v117 + *(_QWORD *)v116) += v135;
        goto LABEL_239;
      }
      LOBYTE(v18) = 0;
      v134 = v18;
      v116 = v125 + v126;
LABEL_259:
      _InterlockedAdd64((volatile signed __int64 *)(v116 + 8), (unsigned __int64)v135);
LABEL_239:
      v135 = v104;
      if ( !v110 )
      {
        v9 = v150;
        v27 = ReceiveFlagsa;
        break;
      }
    }
  }
  if ( (v109 & 1) == 0 )
    goto LABEL_26;
  v118 = (char *)v104 - (char *)v141;
  if ( !v118 )
    goto LABEL_26;
  if ( (_BYTE)v18 || v133 )
  {
    v119 = (v109 & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((v109 >> 1) & 1) + 3);
    if ( !(_BYTE)v18 )
    {
LABEL_262:
      _InterlockedAdd64((volatile signed __int64 *)(v119 + 8), v118);
      goto LABEL_26;
    }
  }
  else
  {
    v127 = KeGetCurrentIrql();
    v119 = (v109 & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((v109 >> 1) & 1) + 3);
    if ( v127 != 2 )
      goto LABEL_262;
  }
  v120 = KeGetPcr()->Prcb.Number << 12;
  *(_QWORD *)(v120 + *(_QWORD *)v119) += v118;
LABEL_26:
  if ( Microsoft_Windows_Networking_CorrelationEnabled || byte_140123720 )
  {
    v8 = NetBufferLista;
    if ( v27 )
      ndisMarkNetBufferListCorrelationIdsAsUsed(NetBufferLista);
  }
  else
  {
    v8 = NetBufferLista;
  }
LABEL_29:
  if ( v154 )
  {
    v87 = Number;
    if ( Number == -1 )
      v87 = KeGetPcr()->Prcb.Number;
    v88 = v151 + ndisPcwPerCpuDataStride * v87 + ndisPcwOffsetToPerCpuData;
    v89 = __rdtsc();
    *(_QWORD *)(v88 + 120) += (((unsigned __int64)HIDWORD(v89) << 32) | (unsigned int)v89) - *(_QWORD *)(v88 + 320);
    v90 = v136;
    *(_QWORD *)(v88 + 320) = 0;
    if ( v90 != 2 )
      KeLowerIrql(v90);
  }
  if ( v27 )
  {
    if ( ndisNblContextVerifierMode )
    {
      if ( ndisNblContextVerifierMode != 3 )
      {
        v85 = *((_QWORD *)v9 + 314);
        if ( v85 )
        {
          switch ( *(_BYTE *)v85 )
          {
            case 5:
              v86 = *(_DWORD *)(v85 + 56) >> 10;
              break;
            case 0x11:
              v86 = *(_DWORD *)(v85 + 3688) >> 12;
              break;
            case 0x12:
              v86 = *(_DWORD *)(v85 + 224) >> 31;
              goto LABEL_185;
            default:
              return;
          }
          LOBYTE(v86) = v86 & 1;
LABEL_185:
          if ( (_BYTE)v86 )
            ndisRemoveNblContextTerminator(v8, *((struct _NDIS_OBJECT_HEADER **)v9 + 314));
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1400285e0  push    rbp
0x1400285e2  push    rbx
0x1400285e3  push    rsi
0x1400285e4  push    rdi
0x1400285e5  push    r12
0x1400285e7  push    r14
0x1400285e9  push    r15
0x1400285eb  lea     rbp, [rsp-70h]
0x1400285f0  sub     rsp, 170h
0x1400285f7  mov     rax, cs:__security_cookie
0x1400285fe  xor     rax, rsp
0x140028601  mov     [rbp+0A0h+var_50], rax
0x140028605  cmp     dword ptr [rcx+30h], 0
0x140028609  mov     r15d, r9d
0x14002860c  mov     [rsp+1A0h+var_124], r9d
0x140028611  mov     r10d, r8d
0x140028614  mov     [rbp+0A0h+var_120], r8d
0x140028618  mov     rdi, rdx
0x14002861b  mov     [rbp+0A0h+NetBufferList], rdx
0x14002861f  mov     rsi, rcx
0x140028622  mov     [rbp+0A0h+var_B8], rcx
0x140028626  mov     [rsp+1A0h+var_130], rdx
0x14002862b  mov     [rsp+1A0h+var_138], r9d
0x140028630  jnz     loc_140028DAA
0x140028636  xor     r12d, r12d
0x140028639  xor     ebx, ebx
0x14002863b  mov     [rbp+0A0h+var_B0], r12
0x14002863f  cmp     [rcx+50h], ebx
0x140028642  jnz     loc_140028DAA
0x140028648  mov     eax, cs:?ndisNblContextVerifierMode@@3W4NDIS_NBL_CONTEXT_VERIFIER_MODE@@A; NDIS_NBL_CONTEXT_VERIFIER_MODE ndisNblContextVerifierMode
0x14002864e  mov     r14d, [rbp+0A0h+ReceiveFlags]
0x140028655  test    eax, eax
0x140028657  jnz     loc_140028D65
0x14002865d  test    dword ptr [rsi+0E68h], 800h
0x140028667  mov     [rbp+0A0h+var_C0], 0FFFFFFFFh
0x14002866e  mov     [rsp+1A0h+var_128], 2
0x140028673  jnz     loc_140029431
0x140028679  and     ebx, 4
0x14002867c  mov     [rbp+0A0h+var_98], ebx
0x14002867f  jnz     loc_1400291D2
0x140028685  mov     eax, [rsi+0A78h]
0x14002868b  test    al, 1
0x14002868d  jnz     loc_140029403
0x140028693  cmp     byte ptr [rsi+0A68h], 0
0x14002869a  jz      loc_140029A87
0x1400286a0  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1400286a6  mov     [rsp+1A0h+var_38], r13
0x1400286ae  test    eax, eax
0x1400286b0  jnz     loc_140028BE1
0x1400286b6  mov     eax, cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x1400286bc  test    eax, eax
0x1400286be  jnz     loc_14002889D
0x1400286c4  cmp     cs:byte_140123720, 0
0x1400286cb  mov     r15d, 28h ; '('
0x1400286d1  jnz     loc_140029348
0x1400286d7  mov     r13, 0FFFFF78000000320h
0x1400286e1  mov     r13, [r13+0]
0x1400286e5  mov     rbx, [rsi+9D0h]
0x1400286ec  mov     r15, [rsi+0A40h]
0x1400286f3  mov     r12, [rsi+9C0h]
0x1400286fa  cmp     byte ptr [rbx], 11h
0x1400286fd  jnz     loc_140028A7A
0x140028703  mov     r9d, [rsp+1A0h+var_124]
0x140028708  mov     rdx, rdi
0x14002870b  mov     r8d, [rbp+0A0h+var_120]
0x14002870f  mov     rcx, r12
0x140028712  mov     rax, r15
0x140028715  mov     dword ptr [rsp+1A0h+Context], r14d
0x14002871a  call    _guard_dispatch_icall
0x14002871f  mov     rax, ds:0FFFFF78000000320h
0x140028729  mov     r15d, r14d
0x14002872c  mov     ecx, cs:?ndisTimeIncrement@@3KA; ulong ndisTimeIncrement
0x140028732  sub     rax, r13
0x140028735  imul    rcx, rax
0x140028739  mov     rax, 346DC5D63886594Bh
0x140028743  imul    rcx
0x140028746  mov     rbx, rdx
0x140028749  sar     rbx, 0Bh
0x14002874d  mov     rax, rbx
0x140028750  shr     rax, 3Fh
0x140028754  add     rbx, rax
0x140028757  and     r15d, 1
0x14002875b  mov     [rsp+1A0h+var_138], r15d
0x140028760  jz      loc_140028C34
0x140028766  xor     eax, eax
0x140028768  xorps   xmm0, xmm0
0x14002876b  mov     dword ptr [rbp+0A0h+WatchdogInformation+10h], eax
0x14002876e  mov     r12d, 200h
0x140028774  movups  xmmword ptr [rbp+0A0h+WatchdogInformation], xmm0
0x140028778  mov     eax, gs:1A4h
0x140028780  shl     eax, 0Ch
0x140028783  mov     ecx, eax
0x140028785  mov     rax, [rsi+0CE0h]
0x14002878c  add     rax, rcx
0x14002878f  mov     dword ptr [rbp+0A0h+var_118], r12d
0x140028793  mov     [rbp+0A0h+LowLimit], rax
0x140028797  lea     rcx, [rbp+0A0h+WatchdogInformation]; WatchdogInformation
0x14002879b  mov     edi, [rax]
0x14002879d  lea     rax, ?ndisPeriodicReceivesNblCounts@@3PAKA; ulong near * ndisPeriodicReceivesNblCounts
0x1400287a4  mov     r13d, [rax+rdi*4]
0x1400287a8  lea     rax, [rax+rdi*4]
0x1400287ac  mov     [rbp+0A0h+var_A8], rax
0x1400287b0  call    cs:__imp_KeQueryDpcWatchdogInformation
0x1400287b7  nop     dword ptr [rax+rax+00h]
0x1400287bc  test    eax, eax
0x1400287be  js      loc_140028C4D
0x1400287c4  mov     ecx, dword ptr [rbp+0A0h+WatchdogInformation]
0x1400287c7  mov     r8d, 400h
0x1400287cd  mov     r9d, [rsp+1A0h+var_124]
0x1400287d2  test    ecx, ecx
0x1400287d4  jz      short loc_1400287F3
0x1400287d6  mov     eax, dword ptr [rbp+0A0h+WatchdogInformation+4]
0x1400287d9  xor     edx, edx
0x1400287db  shl     eax, 0Ah
0x1400287de  div     ecx
0x1400287e0  mov     ecx, r8d
0x1400287e3  xor     edx, edx
0x1400287e5  sub     ecx, eax
0x1400287e7  imul    ecx, r13d
0x1400287eb  mov     eax, ecx
0x1400287ed  div     r9d
0x1400287f0  mov     r12d, eax
0x1400287f3  mov     ecx, dword ptr [rbp+0A0h+WatchdogInformation+8]
0x1400287f6  test    ecx, ecx
0x1400287f8  jz      loc_140029A2E
0x1400287fe  mov     eax, dword ptr [rbp+0A0h+WatchdogInformation+0Ch]
0x140028801  xor     edx, edx
0x140028803  shl     eax, 0Ah
0x140028806  div     ecx
0x140028808  cmp     eax, 200h
0x14002880d  cmova   eax, r8d
0x140028811  xor     edx, edx
0x140028813  sub     r8d, eax
0x140028816  imul    r8d, r13d
0x14002881a  mov     eax, r8d
0x14002881d  div     r9d
0x140028820  mov     edx, eax
0x140028822  lea     ecx, [rdi+1]
0x140028825  cmp     ecx, 0Bh
0x140028828  jb      loc_140028C55
0x14002882e  test    edi, edi
0x140028830  jz      short loc_14002883F
0x140028832  cmp     r12d, 300h
0x140028839  ja      loc_140029175
0x14002883f  and     r14d, 2
0x140028843  mov     [rbp+0A0h+ReceiveFlags], r14d
0x14002884a  jnz     loc_140029696
0x140028850  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x140028856  mov     r13, [rsp+1A0h+var_38]
0x14002885e  test    eax, eax
0x140028860  jnz     loc_140029854
0x140028866  cmp     cs:byte_140123720, al
0x14002886c  jnz     loc_140029854
0x140028872  mov     rdi, [rbp+0A0h+NetBufferList]
0x140028876  cmp     [rbp+0A0h+var_98], 0
0x14002887a  jnz     loc_140029261
0x140028880  test    r14d, r14d
0x140028883  jz      loc_140029C07
0x140028889  mov     eax, cs:?ndisNblContextVerifierMode@@3W4NDIS_NBL_CONTEXT_VERIFIER_MODE@@A; NDIS_NBL_CONTEXT_VERIFIER_MODE ndisNblContextVerifierMode
0x14002888f  test    eax, eax
0x140028891  jnz     loc_14002921C
0x140028897  jmp     loc_140029C07
0x14002889d  mov     rdx, [rsi+0FF0h]; struct NDIS_NBL_TRACKER_HANDLE__ *
0x1400288a4  xor     ecx, ecx
0x1400288a6  mov     rbx, [rsi+9C8h]
0x1400288ad  xor     r8d, r8d
0x1400288b0  mov     r15d, cs:?ndisNblTrackerEpoch@@3KA; ulong ndisNblTrackerEpoch
0x1400288b7  mov     r9d, r14d
0x1400288ba  and     r9d, 1
0x1400288be  mov     [rbp+0A0h+var_108], rdx
0x1400288c2  xor     r12d, r12d
0x1400288c5  mov     [rsp+1A0h+var_138], r9d
0x1400288ca  mov     [rsp+1A0h+var_130], rcx
0x1400288cf  mov     [rbp+0A0h+var_118], r8
0x1400288d3  mov     [rsp+1A0h+var_140], cl
0x1400288d7  cmp     eax, 3
0x1400288da  jl      short loc_140028903
0x1400288dc  mov     r8d, r14d
0x1400288df  mov     dword ptr [rsp+1A0h+Context], r9d; unsigned int
0x1400288e4  and     r8d, 2
0x1400288e8  mov     r9, rbx; void *
0x1400288eb  bts     r8d, 8
0x1400288f0  mov     rcx, rdi; struct _NET_BUFFER_LIST *
0x1400288f3  shr     r8d, 1; unsigned int
0x1400288f6  call    ?ndisNblTrackerRecordEventInternal@@YAXPEAU_NET_BUFFER_LIST@@PEAUNDIS_NBL_TRACKER_HANDLE__@@KPEAXK@Z; ndisNblTrackerRecordEventInternal(_NET_BUFFER_LIST *,NDIS_NBL_TRACKER_HANDLE__ *,ulong,void *,ulong)
0x1400288fb  mov     r9d, [rsp+1A0h+var_138]
0x140028900  xor     r8d, r8d
0x140028903  mov     r13, rbx
0x140028906  and     r13, 0FFFFFFFFFFFFFFFDh
0x14002890a  test    r13b, 1
0x14002890e  jz      loc_1400290BE
0x140028914  mov     rax, r15
0x140028917  add     rax, rax
0x14002891a  xor     rbx, rax
0x14002891d  and     rbx, 0FFFFFFFFFFFFFFFDh
0x140028921  xor     rbx, rax
0x140028924  and     r13, 0FFFFFFFFFFFFFFF8h
0x140028928  mov     r13, [r13+18h]
0x14002892c  mov     r15, rdi
0x14002892f  test    rdi, rdi
0x140028932  jz      loc_140028A24
0x140028938  mov     r14, [rbp+0A0h+var_108]
0x14002893c  mov     rdi, [r15+168h]
0x140028943  lea     r9, WPP_RECORDER_INITIALIZED
0x14002894a  lea     rsi, WPP_78a33c75b2d2335d1cf1dcc315edf7b8_Traceguids
0x140028951  cmp     [r15+168h], rdi
0x140028958  jnz     short loc_1400289A6
0x14002895a  test    rdi, rdi
0x14002895d  jz      loc_140029192
0x140028963  test    dil, 4
0x140028967  jnz     loc_1400291C6
0x14002896d  mov     rcx, [r15+78h]
0x140028971  test    rcx, rcx
0x140028974  jz      loc_1400291B9
0x14002897a  movzx   edx, byte ptr [rcx]
0x14002897d  lea     eax, [rdx-11h]
0x140028980  cmp     al, 1
0x140028982  ja      loc_1400292D1
0x140028988  cmp     rcx, r13
0x14002898b  jz      loc_140029094
0x140028991  inc     r12
0x140028994  mov     rax, rbx
0x140028997  mov     [r15+168h], rax
0x14002899e  mov     r15, [r15]
0x1400289a1  test    r15, r15
0x1400289a4  jnz     short loc_140028951
0x1400289a6  movzx   esi, [rsp+1A0h+var_140]
0x1400289ab  mov     r9d, [rsp+1A0h+var_138]
0x1400289b0  test    dil, 1
0x1400289b4  jz      short loc_140028A03
0x1400289b6  mov     r8, [rsp+1A0h+var_130]
0x1400289bb  sub     r8, r12
0x1400289be  mov     [rsp+1A0h+var_130], r8
0x1400289c3  jz      short loc_140028A03
0x1400289c5  test    r9b, r9b
0x1400289c8  jz      loc_140028CD3
0x1400289ce  mov     rdx, rdi
0x1400289d1  and     rdi, 0FFFFFFFFFFFFFFF8h
0x1400289d5  shr     rdx, 1
0x1400289d8  and     edx, 1
0x1400289db  add     rdx, 3
0x1400289df  shl     rdx, 4
0x1400289e3  add     rdx, rdi
0x1400289e6  test    r9b, r9b
0x1400289e9  jz      loc_140028D1A
0x1400289ef  mov     eax, gs:1A4h
0x1400289f7  shl     eax, 0Ch
0x1400289fa  mov     ecx, eax
0x1400289fc  mov     rax, [rdx]
0x1400289ff  add     [rcx+rax], r8
0x140028a03  mov     r8, [rbp+0A0h+var_118]
0x140028a07  mov     [rsp+1A0h+var_130], r12
0x140028a0c  test    r15, r15
0x140028a0f  jnz     loc_14002893C
0x140028a15  mov     rsi, [rbp+0A0h+var_B8]
0x140028a19  mov     r14d, [rbp+0A0h+ReceiveFlags]
0x140028a20  mov     rdi, [rbp+0A0h+NetBufferList]
0x140028a24  test    bl, 1
0x140028a27  jz      loc_1400286C4
0x140028a2d  sub     r12, [rbp+0A0h+var_118]
0x140028a31  jz      loc_1400286C4
0x140028a37  test    r9b, r9b
0x140028a3a  jz      loc_140028D24
0x140028a40  mov     rdx, rbx
0x140028a43  and     rbx, 0FFFFFFFFFFFFFFF8h
0x140028a47  shr     rdx, 1
0x140028a4a  and     edx, 1
0x140028a4d  add     rdx, 3
0x140028a51  shl     rdx, 4
0x140028a55  add     rdx, rbx
0x140028a58  test    r9b, r9b
0x140028a5b  jz      loc_140028D5B
0x140028a61  mov     eax, gs:1A4h
0x140028a69  shl     eax, 0Ch
0x140028a6c  mov     ecx, eax
0x140028a6e  mov     rax, [rdx]
0x140028a71  add     [rcx+rax], r12
0x140028a75  jmp     loc_1400286C4
0x140028a7a  mov     eax, r14d
0x140028a7d  and     eax, 2
0x140028a80  mov     dword ptr [rbp+0A0h+var_118], eax
0x140028a83  jnz     short loc_140028AA3
0x140028a85  test    r14b, 1
0x140028a89  jnz     loc_140028E82
0x140028a8f  call    cs:__imp_KeGetCurrentIrql
0x140028a96  nop     dword ptr [rax+rax+00h]
0x140028a9b  cmp     al, 2
0x140028a9d  jz      loc_140028E82
0x140028aa3  mov     eax, cs:Size
0x140028aa9  lea     rdi, [rbp+0A8h]
0x140028ab0  mov     dword ptr [rsp+1A0h+var_130], eax
0x140028ab4  mov     [rbp+0A0h+LowLimit], 0
0x140028abc  mov     [rbp+0A0h+HighLimit], 0
0x140028ac4  mov     eax, gs:1A4h
0x140028acc  shl     eax, 0Ch
0x140028acf  mov     ecx, eax
0x140028ad1  mov     rax, cs:qword_140122F78
0x140028ad8  mov     rdx, [rcx+rax]
0x140028adc  mov     rax, cs:qword_140122F70
0x140028ae3  mov     [rbp+0A0h+LowLimit], rdx
  ... truncated ...
```
