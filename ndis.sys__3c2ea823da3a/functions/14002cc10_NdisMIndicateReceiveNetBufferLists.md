# NdisMIndicateReceiveNetBufferLists

- ea: `0x14002cc10`
- end: `0x14002dd34`
- name: `NdisMIndicateReceiveNetBufferLists`
- size: `4388`
- prototype: `void __stdcall(NDIS_HANDLE MiniportAdapterHandle, PNET_BUFFER_LIST NetBufferList, NDIS_PORT_NUMBER PortNumber, ULONG NumberOfNetBufferLists, ULONG ReceiveFlags)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14002c820`

## callees

- `0x140004890`
- `0x14000de20`
- `0x140010050`
- `0x14002c720`
- `0x14002c8d0`
- `0x14002c970`
- `0x14002c9d0`
- `0x14002caa0`
- `0x14002cb90`
- `0x14002cc10`
- `0x14002dd40`
- `0x14002ddf0`
- `0x14002de40`
- `0x1400615a0`
- `0x1400e6160`
- `0x1400e6240`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14002d598`
- `ntoskrnl!KfRaiseIrql` at `0x14002d598`
- `ntoskrnl!KeLowerIrql` at `0x14002d670`
- `ntoskrnl!KeLowerIrql` at `0x14002d670`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002cf28`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002d0d5`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002cf28`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002d0d5`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14002cded`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14002cded`
- `ntoskrnl!IoGetStackLimits` at `0x14002cf98`
- `ntoskrnl!IoGetStackLimits` at `0x14002cf98`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14002d01d`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14002d01d`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002d701`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002d8d8`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002d9a8`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002daca`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002d701`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002d8d8`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002d9a8`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002daca`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002d763`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002d939`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002da11`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002db30`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002d763`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002d939`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002da11`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002db30`
- `HAL!KeQueryPerformanceCounter` at `0x14002d786`
- `HAL!KeQueryPerformanceCounter` at `0x14002d786`

## pseudocode

```c
void __stdcall NdisMIndicateReceiveNetBufferLists(
        NDIS_HANDLE MiniportAdapterHandle,
        PNET_BUFFER_LIST NetBufferList,
        NDIS_PORT_NUMBER PortNumber,
        ULONG NumberOfNetBufferLists,
        ULONG ReceiveFlags)
{
  bool v5; // zf
  ULONG v6; // r13d
  NDIS_PORT_NUMBER v7; // r10d
  PNET_BUFFER_LIST v8; // r12
  NDIS_HANDLE v9; // rdi
  __int64 v10; // r14
  int v11; // ebx
  ULONG v12; // esi
  ULONG v13; // r14d
  __int64 v14; // rax
  __int64 v15; // rbx
  void (__fastcall *v16)(__int64, PNET_BUFFER_LIST, _QWORD, _QWORD, ULONG); // r10
  __int64 v17; // rcx
  __int64 v18; // rbx
  __int64 v19; // r15
  unsigned int v20; // eax
  unsigned int v21; // r10d
  char v22; // dl
  unsigned int v23; // ecx
  __int64 v24; // rcx
  unsigned __int64 v25; // r8
  int v26; // ecx
  int v27; // r8d
  unsigned int v28; // ecx
  _SLIST_HEADER *v29; // rax
  _SLIST_HEADER *v30; // rdx
  unsigned int v31; // ecx
  unsigned __int64 v32; // rax
  __int64 v33; // rax
  unsigned int v34; // ecx
  __int64 v35; // rdx
  int v36; // eax
  _QWORD *Alignment; // rcx
  __int64 v38; // rax
  unsigned int v39; // edx
  unsigned __int64 *v40; // rdx
  unsigned __int64 v41; // rcx
  __int64 v42; // r8
  void (__fastcall *v43)(__int64, unsigned __int64, __int64, _QWORD, int); // r15
  unsigned __int64 v44; // r10
  __int64 v45; // rcx
  __int64 v46; // rax
  unsigned __int64 *v47; // r15
  void (__fastcall *v48)(__int64, unsigned __int64, __int64, _QWORD, int); // rdi
  __int64 v49; // r13
  int v50; // ecx
  unsigned int v51; // edx
  unsigned __int64 v52; // rax
  unsigned __int64 v53; // rcx
  __int64 v54; // rdi
  int v55; // edx
  __int64 v56; // r8
  __int64 v57; // rax
  struct _NET_BUFFER_LIST *v58; // rax
  struct _NET_BUFFER_LIST *v59; // rsi
  __int64 v60; // rdx
  int v61; // eax
  unsigned int v62; // eax
  __int64 v63; // r8
  unsigned __int64 v64; // rax
  KIRQL v65; // al
  __int64 v66; // rax
  unsigned int v67; // ebx
  __int64 v68; // rdx
  LARGE_INTEGER *v69; // rbx
  LARGE_INTEGER PerformanceCounter; // rax
  __int64 v71; // rdi
  int v72; // ecx
  unsigned int v73; // edx
  __int64 v74; // rax
  __int64 v75; // rax
  __int64 v76; // rdx
  __int64 v77; // rax
  __int64 v78; // rdx
  __int64 v79; // rax
  __int64 v80; // rdx
  __int64 v81; // rax
  __int64 v82; // r8
  __int64 v83; // rcx
  __int64 v84; // r9
  __int64 v85; // r8
  unsigned int v86[2]; // [rsp+60h] [rbp-A0h] BYREF
  KIRQL v87; // [rsp+68h] [rbp-98h]
  unsigned int v88; // [rsp+6Ch] [rbp-94h]
  unsigned __int64 v89; // [rsp+70h] [rbp-90h]
  __int64 v90; // [rsp+78h] [rbp-88h]
  struct _NET_BUFFER_LIST *v91; // [rsp+80h] [rbp-80h] BYREF
  ULONG v92; // [rsp+88h] [rbp-78h]
  unsigned __int64 LowLimit; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 HighLimit; // [rsp+98h] [rbp-68h] BYREF
  __int128 Parameter; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v96; // [rsp+B0h] [rbp-50h]
  unsigned __int64 v97; // [rsp+C0h] [rbp-40h]
  ULONG v98; // [rsp+C8h] [rbp-38h]
  int v99; // [rsp+CCh] [rbp-34h]
  unsigned int Number; // [rsp+D0h] [rbp-30h]
  unsigned __int64 *v101; // [rsp+D8h] [rbp-28h]
  PNET_BUFFER_LIST v102; // [rsp+E0h] [rbp-20h]
  NDIS_HANDLE v103; // [rsp+E8h] [rbp-18h]
  __int64 v104; // [rsp+F0h] [rbp-10h]
  unsigned int *v105; // [rsp+F8h] [rbp-8h]
  __int64 v106; // [rsp+100h] [rbp+0h]
  int v107; // [rsp+108h] [rbp+8h]
  _QWORD v108[3]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE WatchdogInformation[32]; // [rsp+128h] [rbp+28h] BYREF
  __int64 v110; // [rsp+148h] [rbp+48h]
  _UNKNOWN *retaddr; // [rsp+1A8h] [rbp+A8h] BYREF

  v5 = *((_DWORD *)MiniportAdapterHandle + 12) == 0;
  v6 = NumberOfNetBufferLists;
  v92 = NumberOfNetBufferLists;
  v7 = PortNumber;
  LODWORD(v89) = PortNumber;
  v8 = NetBufferList;
  v102 = NetBufferList;
  v9 = MiniportAdapterHandle;
  v103 = MiniportAdapterHandle;
  v91 = NetBufferList;
  v86[0] = NumberOfNetBufferLists;
  if ( !v5 || (v10 = 0, LOBYTE(v11) = 0, v104 = 0, *((_DWORD *)MiniportAdapterHandle + 20)) )
  {
    v10 = *((_QWORD *)MiniportAdapterHandle + 5);
    v11 = *((_DWORD *)MiniportAdapterHandle + 20);
    v104 = v10;
    if ( !v10 )
    {
      v10 = *((_QWORD *)MiniportAdapterHandle + 5);
      v104 = v10;
    }
  }
  if ( !ndisNblContextVerifierMode )
    goto LABEL_4;
  if ( ndisNblContextVerifierMode == 3 )
    goto LABEL_4;
  v35 = *((_QWORD *)MiniportAdapterHandle + 314);
  if ( !v35 )
    goto LABEL_4;
  switch ( *(_BYTE *)v35 )
  {
    case 5:
      v36 = *(_DWORD *)(v35 + 56) >> 10;
      break;
    case 0x11:
      v36 = *(_DWORD *)(v35 + 3688) >> 12;
      break;
    case 0x12:
      v36 = *(_DWORD *)(v35 + 224) >> 31;
      goto LABEL_108;
    default:
      goto LABEL_4;
  }
  LOBYTE(v36) = v36 & 1;
LABEL_108:
  if ( (_BYTE)v36 )
  {
    v58 = ndisAddNblContextTerminator(&v91, v86, *((struct _NDIS_OBJECT_HEADER **)MiniportAdapterHandle + 314));
    v59 = v58;
    if ( v58 )
    {
      if ( byte_14011D730 && (*((_DWORD *)v9 + 1468) & 2) != 0 )
        PktMonClientNblDropNdis((_DWORD)v9 + 5816, (_DWORD)v58, PortNumber, 1, -1073741670, -536866800);
      if ( (ReceiveFlags & 2) == 0 )
        ndisCallPreviousReturnHandler((struct _NDIS_OBJECT_HEADER *)v9, v59, ReceiveFlags);
      v8 = v91;
      v102 = v91;
      if ( !v91 )
        return;
    }
    else
    {
      v8 = v91;
      v102 = v91;
    }
    v6 = v86[0];
    v7 = v89;
    v92 = v86[0];
  }
LABEL_4:
  v5 = (*((_DWORD *)v9 + 922) & 0x800) == 0;
  Number = -1;
  v87 = 2;
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
  v107 = v11 & 4;
  if ( (v11 & 4) != 0 )
  {
    if ( (ReceiveFlags & 1) == 0 )
      v87 = KfRaiseIrql(2u);
    Number = KeGetPcr()->Prcb.Number;
    PortNumber = ndisPcwOffsetToPerCpuData;
    *(_QWORD *)(ndisPcwOffsetToPerCpuData + v10 + ndisPcwPerCpuDataStride * Number + 320) = __rdtsc();
  }
  if ( (*((_DWORD *)v9 + 670) & 1) != 0 )
  {
    v69 = (LARGE_INTEGER *)v8;
    PerformanceCounter = KeQueryPerformanceCounter(0);
    if ( v8 )
    {
      do
      {
        v69[44] = PerformanceCounter;
        v69 = (LARGE_INTEGER *)v69->QuadPart;
      }
      while ( v69 );
    }
  }
  if ( *((_BYTE *)v9 + 2664) )
  {
    if ( Microsoft_Windows_Networking_CorrelationEnabled )
    {
      if ( (__int64)v8->NetBufferListInfo[13] > 0 )
      {
        Alignment = (_QWORD *)v8->Link.Alignment;
        if ( v8->Link.Alignment )
        {
          do
          {
            v38 = Alignment[31];
            if ( !v38 || v38 < 0 )
            {
              v39 = _InterlockedExchangeAdd(&dword_14011AE28, 1u);
              if ( v39 + 1 < v39 )
                v39 = _InterlockedExchangeAdd(&dword_14011AE28, 1u);
              Alignment[31] = v39;
            }
            Alignment = (_QWORD *)*Alignment;
          }
          while ( Alignment );
        }
      }
      else
      {
        v30 = (_SLIST_HEADER *)v8;
        v31 = _InterlockedExchangeAdd(&dword_14011AE28, v6);
        if ( v31 + v6 < v31 )
          v31 = _InterlockedExchangeAdd(&dword_14011AE28, v6);
        do
        {
          if ( (__int64)v30[15].Region <= 0 )
          {
            v32 = v31++;
            v30[15].Region = v32;
          }
          v30 = (_SLIST_HEADER *)v30->Alignment;
        }
        while ( v30 );
      }
    }
    if ( *(_DWORD *)ndisNblTrackerMode )
    {
      v13 = ReceiveFlags & 1;
      v12 = ReceiveFlags & 2;
      ndisNblTrackerTransferOwnershipInternal(
        v8,
        *((struct NDIS_NBL_TRACKER_HANDLE__ **)v9 + 510),
        *((struct NDIS_NBL_TRACKER_HANDLE__ **)v9 + 313),
        (enum _NDIS_NBL_TRACKER_OWNERSHIP_EVENT)((v12 != 0) + 128),
        v13);
    }
    else
    {
      v12 = ReceiveFlags & 2;
      v13 = ReceiveFlags & 1;
    }
    if ( byte_14011D730 )
    {
      v66 = *((_QWORD *)v9 + 738);
      if ( v66 )
      {
        if ( (*(_DWORD *)(v66 + 56) & 1) != 0 )
        {
          v5 = (v8->NblFlags & 0x8000) == 0;
          memset(WatchdogInformation, 0, sizeof(WatchdogInformation));
          LODWORD(v110) = 0;
          if ( v5 )
          {
            v67 = *((_DWORD *)v9 + 1478);
            if ( ExAcquireRundownProtectionCacheAware(RunRefCacheAware) )
            {
              v68 = *((_QWORD *)v9 + 737);
              strcpy(WatchdogInformation, "(");
              *(_QWORD *)&WatchdogInformation[8] = v8;
              *(_DWORD *)&WatchdogInformation[16] = 1;
              *(_QWORD *)&WatchdogInformation[20] = v67 | 0x100000000LL;
              v110 = 0;
              (*(void (__fastcall **)(_QWORD, __int64, _BYTE *, _QWORD))(*((_QWORD *)&xmmword_14011D750 + 1) + 40LL))(
                xmmword_14011D750,
                v68,
                WatchdogInformation,
                0);
              ExReleaseRundownProtectionCacheAware(RunRefCacheAware);
            }
          }
          v12 = ReceiveFlags & 2;
          v13 = ReceiveFlags & 1;
        }
      }
    }
    HIDWORD(v14) = MEMORY[0xFFFFF78000000324];
    v15 = *((_QWORD *)v9 + 314);
    v16 = (void (__fastcall *)(__int64, PNET_BUFFER_LIST, _QWORD, _QWORD, ULONG))*((_QWORD *)v9 + 328);
    v17 = *((_QWORD *)v9 + 312);
    v105 = (unsigned int *)MEMORY[0xFFFFF78000000320];
    v5 = *(_BYTE *)v15 == 17;
    *(_QWORD *)v86 = v16;
    v90 = v17;
    if ( v5 )
    {
      v16(v17, v8, (unsigned int)v89, v6, ReceiveFlags);
    }
    else if ( !v12 && (v13 || KeGetCurrentIrql() == 2) )
    {
      LODWORD(v14) = KeGetPcr()->Prcb.Number;
      v40 = v108;
      v41 = v8->Link.Alignment;
      v42 = (unsigned int)v89;
      v88 = v14;
      v108[2] = 0;
      v101 = v108;
      v108[0] = v8;
      v108[1] = v8;
      v8->Scratch = 0;
      v8->ChildRefCount = ReceiveFlags;
      v8->Status = v42;
      if ( v41 )
      {
        *(_QWORD *)(v41 + 112) = v6;
        v14 = v88;
      }
      v43 = *(void (__fastcall **)(__int64, unsigned __int64, __int64, _QWORD, int))v86;
      while ( *(_BYTE *)v15 == 5 )
      {
        v44 = *v40;
        v89 = v44;
        if ( !v44 )
          break;
        v45 = *(_QWORD *)(v15 + 424) + 96 * v14 + 48;
        v106 = v45;
        if ( *(_BYTE *)(v45 + 16) )
        {
          v71 = v90;
          *v40 = 0;
          do
          {
            v72 = *(_DWORD *)(v44 + 132);
            v73 = *(_DWORD *)(v44 + 140);
            LowLimit = *(_QWORD *)(v44 + 112);
            v74 = *(_QWORD *)v44;
            LODWORD(v91) = v72;
            v88 = v73;
            if ( v74 )
              v86[0] = *(_DWORD *)(v74 + 112);
            else
              v86[0] = 1;
            *(_DWORD *)(v44 + 132) = 0;
            if ( byte_14011D730 )
            {
              if ( *(_BYTE *)v15 == 5 )
              {
                v81 = *(_QWORD *)(v15 + 872);
                if ( v81 )
                {
                  if ( (*(_DWORD *)(v81 + 56) & 1) != 0 )
                  {
                    PktMonClientNblLogNdis(v15 + 848, v44, v42, 1);
                    v44 = v89;
                    v72 = (int)v91;
                    v73 = v88;
                  }
                }
              }
            }
            if ( ndisVerifierNdisDispatch && *(_BYTE *)v15 == 5 && (v85 = *(_QWORD *)(v15 + 776)) != 0 )
              (*((void (__fastcall **)(__int64, unsigned __int64, _QWORD, _QWORD, int, __int64, void (__fastcall *)(__int64, unsigned __int64, __int64, _QWORD, int)))ndisVerifierNdisDispatch
               + 14))(
                v71,
                v44,
                v73,
                v86[0],
                v72,
                v85,
                v43);
            else
              v43(v71, v44, v73, v86[0], v72);
            v89 = LowLimit;
            v44 = LowLimit;
          }
          while ( LowLimit );
          v9 = v103;
          v40 = v101;
          break;
        }
        *(_BYTE *)(v45 + 16) = 1;
        v46 = v15;
        v47 = (unsigned __int64 *)*v40;
        *v40 = 0;
        if ( v47 )
        {
          v48 = *(void (__fastcall **)(__int64, unsigned __int64, __int64, _QWORD, int))v86;
          v49 = v90;
          do
          {
            v50 = *((_DWORD *)v47 + 33);
            v51 = *((_DWORD *)v47 + 35);
            v101 = (unsigned __int64 *)v47[14];
            v52 = *v47;
            LODWORD(v89) = v50;
            LODWORD(v90) = v51;
            if ( v52 )
              v86[0] = *(_DWORD *)(v52 + 112);
            else
              v86[0] = 1;
            *((_DWORD *)v47 + 33) = 0;
            if ( byte_14011D730 )
            {
              if ( *(_BYTE *)v15 == 5 )
              {
                v75 = *(_QWORD *)(v15 + 872);
                if ( v75 )
                {
                  if ( (*(_DWORD *)(v75 + 56) & 1) != 0 )
                  {
                    v5 = (v47[16] & 0x8000) == 0;
                    Parameter = 0;
                    LODWORD(v97) = 0;
                    v96 = 0;
                    if ( v5 )
                    {
                      LODWORD(v91) = *(_DWORD *)(v15 + 880);
                      if ( ExAcquireRundownProtectionCacheAware(RunRefCacheAware) )
                      {
                        v76 = *(_QWORD *)(v15 + 864);
                        *(_QWORD *)((char *)&v96 + 4) = (unsigned int)v91 | 0x100000000LL;
                        LOWORD(Parameter) = 40;
                        *((_QWORD *)&Parameter + 1) = v47;
                        LODWORD(v96) = 1;
                        v97 = 0;
                        (*(void (__fastcall **)(_QWORD, __int64, __int128 *, _QWORD))(*((_QWORD *)&xmmword_14011D750 + 1)
                                                                                    + 40LL))(
                          xmmword_14011D750,
                          v76,
                          &Parameter,
                          0);
                        ExReleaseRundownProtectionCacheAware(RunRefCacheAware);
                      }
                      v51 = v90;
                      v50 = v89;
                    }
                  }
                }
              }
            }
            if ( ndisVerifierNdisDispatch && *(_BYTE *)v15 == 5 && (v82 = *(_QWORD *)(v15 + 776)) != 0 )
              (*((void (__fastcall **)(__int64, unsigned __int64 *, _QWORD, _QWORD, int, __int64, void (__fastcall *)(__int64, unsigned __int64, __int64, _QWORD, int)))ndisVerifierNdisDispatch
               + 14))(
                v49,
                v47,
                v51,
                v86[0],
                v50,
                v82,
                v48);
            else
              v48(v49, (unsigned __int64)v47, v51, v86[0], v50);
            v47 = v101;
          }
          while ( v101 );
          v9 = v103;
          v46 = v15;
          v8 = v102;
          v6 = v92;
          v45 = v106;
        }
        *(_BYTE *)(v45 + 16) = 0;
        v40 = (unsigned __int64 *)v45;
        v43 = *(void (__fastcall **)(__int64, unsigned __int64, __int64, _QWORD, int))(v46 + 496);
        v15 = *(_QWORD *)(v15 + 520);
        v90 = *(_QWORD *)(v46 + 504);
        v14 = v88;
        *(_QWORD *)v86 = v43;
        v101 = (unsigned __int64 *)v45;
      }
      v53 = *v40;
      v89 = v53;
      if ( v53 )
      {
        v54 = v90;
        *v40 = 0;
        do
        {
          v55 = *(_DWORD *)(v53 + 132);
          v56 = *(unsigned int *)(v53 + 140);
          LowLimit = *(_QWORD *)(v53 + 112);
          v57 = *(_QWORD *)v53;
          v88 = v55;
          LODWORD(v90) = v56;
          if ( v57 )
            v86[0] = *(_DWORD *)(v57 + 112);
          else
            v86[0] = 1;
          *(_DWORD *)(v53 + 132) = 0;
          if ( byte_14011D730 )
          {
            if ( *(_BYTE *)v15 == 5 )
            {
              v79 = *(_QWORD *)(v15 + 872);
              if ( v79 )
              {
                if ( (*(_DWORD *)(v79 + 56) & 1) != 0 )
                {
                  v5 = (*(_DWORD *)(v53 + 128) & 0x8000) == 0;
                  Parameter = 0;
                  LODWORD(v97) = 0;
                  v96 = 0;
                  if ( v5 )
                  {
                    LODWORD(v91) = *(_DWORD *)(v15 + 880);
                    if ( ExAcquireRundownProtectionCacheAware(RunRefCacheAware) )
                    {
                      v80 = *(_QWORD *)(v15 + 864);
                      *((_QWORD *)&Parameter + 1) = v89;
                      *(_QWORD *)((char *)&v96 + 4) = (unsigned int)v91 | 0x100000000LL;
                      LOWORD(Parameter) = 40;
                      LODWORD(v96) = 1;
                      v97 = 0;
                      (*(void (__fastcall **)(_QWORD, __int64, __int128 *, _QWORD))(*((_QWORD *)&xmmword_14011D750 + 1)
                                                                                  + 40LL))(
                        xmmword_14011D750,
                        v80,
                        &Parameter,
                        0);
                      ExReleaseRundownProtectionCacheAware(RunRefCacheAware);
                    }
                    v56 = (unsigned int)v90;
                    v55 = v88;
                    v53 = v89;
                  }
                }
              }
            }
          }
          if ( ndisVerifierNdisDispatch && *(_BYTE *)v15 == 5 && (v84 = *(_QWORD *)(v15 + 776)) != 0 )
            (*((void (__fastcall **)(__int64, unsigned __int64, __int64, _QWORD, int, __int64, void (__fastcall *)(__int64, unsigned __int64, __int64, _QWORD, int)))ndisVerifierNdisDispatch
             + 14))(
              v54,
              v53,
              v56,
              v86[0],
              v55,
              v84,
              v43);
          else
            v43(v54, v53, v56, v86[0], v55);
          v89 = LowLimit;
          v53 = LowLimit;
        }
        while ( LowLimit );
        v9 = v103;
        v6 = v92;
      }
    }
    else
    {
      LODWORD(v91) = Size;
      LowLimit = 0;
      HighLimit = 0;
      v24 = KeGetPcr()->Prcb.Number << 12;
      v25 = *(_QWORD *)(v24 + qword_14011CF78);
      LowLimit = v25;
      HighLimit = *(_QWORD *)(v24 + qword_14011CF70);
      if ( (unsigned __int64)&retaddr >= HighLimit || v25 > (unsigned __int64)&retaddr )
      {
        IoGetStackLimits(&LowLimit, &HighLimit);
        v25 = LowLimit;
      }
      if ( (unsigned __int64)&retaddr - v25 >= (unsigned int)v91 )
      {
        if ( byte_14011D730 )
        {
          if ( *(_BYTE *)v15 == 5 )
          {
            v77 = *(_QWORD *)(v15 + 872);
            if ( v77 )
            {
              if ( (*(_DWORD *)(v77 + 56) & 1) != 0 )
              {
                v5 = (v8->NblFlags & 0x8000) == 0;
                Parameter = 0;
                LODWORD(v97) = 0;
                v96 = 0;
                if ( v5 )
                {
                  LODWORD(v91) = *(_DWORD *)(v15 + 880);
                  if ( ExAcquireRundownProtectionCacheAware(RunRefCacheAware) )
                  {
                    v78 = *(_QWORD *)(v15 + 864);
                    LOWORD(Parameter) = 40;
                    *(_QWORD *)((char *)&v96 + 4) = (unsigned int)v91 | 0x100000000LL;
                    *((_QWORD *)&Parameter + 1) = v8;
                    LODWORD(v96) = 1;
                    v97 = 0;
                    (*(void (__fastcall **)(_QWORD, __int64, __int128 *, _QWORD))(*((_QWORD *)&xmmword_14011D750 + 1)
                                                                                + 40LL))(
                      xmmword_14011D750,
                      v78,
                      &Parameter,
                      0);
                    ExReleaseRundownProtectionCacheAware(RunRefCacheAware);
                  }
                }
              }
            }
          }
        }
        if ( ndisVerifierNdisDispatch && *(_BYTE *)v15 == 5 && (v83 = *(_QWORD *)(v15 + 776)) != 0 )
          (*((void (__fastcall **)(__int64, PNET_BUFFER_LIST, _QWORD, _QWORD, ULONG, __int64, _QWORD))ndisVerifierNdisDispatch
           + 14))(
            v90,
            v8,
            (unsigned int)v89,
            v6,
            ReceiveFlags,
            v83,
            *(_QWORD *)v86);
        else
          (*(void (__fastcall **)(__int64, PNET_BUFFER_LIST, _QWORD, _QWORD, ULONG))v86)(
            v90,
            v8,
            (unsigned int)v89,
            v6,
            ReceiveFlags);
      }
      else
      {
        v26 = 24576;
        *((_QWORD *)&Parameter + 1) = v90;
        *(_QWORD *)&v96 = *(_QWORD *)v86;
        v99 = 0;
        *(_QWORD *)&Parameter = v15;
        *((_QWORD *)&v96 + 1) = v8;
        v97 = __PAIR64__(v6, v89);
        v98 = ReceiveFlags;
        if ( (unsigned int)Size > 0x6000 )
          v26 = Size;
        if ( KeExpandKernelStackAndCalloutEx(
               ndisDataPathExpandStackCallback<2,void (void *,_NET_BUFFER_LIST *,unsigned long,unsigned long,unsigned long)>,
               &Parameter,
               v26,
               0,
               0) < 0 )
        {
          if ( byte_14011D730 && (*(_DWORD *)(v15 + 840) & 2) != 0 )
            PktMonClientNblDropNdis(v15 + 784, (_DWORD)v8, v27, 1, -1073741670, -536866813);
          NdisSetStatusInNblChain(v8, -1073741670);
          v28 = 0;
          v29 = (_SLIST_HEADER *)v8;
          if ( v8 )
          {
            do
            {
              v29 = (_SLIST_HEADER *)v29->Alignment;
              ++v28;
            }
            while ( v29 );
          }
          _InterlockedAdd((volatile signed __int32 *)(v15 + 292), v28);
          if ( !v12 )
            ndisQueueStackExpansionFallbackNbls((struct _NDIS_FILTER_BLOCK *)v15, v8, 0);
        }
      }
    }
    v18 = (MEMORY[0xFFFFF78000000320] - (_QWORD)v105) * ndisTimeIncrement / 10000LL;
    if ( v13 || KeGetCurrentIrql() == 2 )
    {
      v86[0] = 512;
      LODWORD(v90) = 512;
      memset(WatchdogInformation, 0, 20);
      v105 = (unsigned int *)((KeGetPcr()->Prcb.Number << 12) + *((_QWORD *)v9 + 412));
      v19 = *v105;
      LowLimit = (unsigned __int64)&ndisPeriodicReceivesNblCounts + 4 * v19;
      v88 = *(_DWORD *)LowLimit;
      if ( KeQueryDpcWatchdogInformation((PKDPC_WATCHDOG_INFORMATION)WatchdogInformation) < 0 )
        goto LABEL_57;
      if ( *(_DWORD *)WatchdogInformation )
        v86[0] = v88 * (1024 - (*(_DWORD *)&WatchdogInformation[4] << 10) / *(_DWORD *)WatchdogInformation) / v6;
      if ( *(_DWORD *)&WatchdogInformation[8] )
      {
        v20 = (*(_DWORD *)&WatchdogInformation[12] << 10) / *(_DWORD *)&WatchdogInformation[8];
        if ( v20 > 0x200 )
          v20 = 1024;
        v21 = v88 * (1024 - v20) / v6;
      }
      else
      {
LABEL_57:
        LOBYTE(v21) = v90;
      }
      v22 = v86[0];
      v23 = v19 + 1;
      if ( (unsigned int)(v19 + 1) < 0xB && v86[0] < 0x200
        || (_DWORD)v19 && v86[0] > 0x300 && (v23 = v19 - 1, (_DWORD)v19 != 12) )
      {
        *v105 = v23;
        if ( (byte_14011B005 & 2) != 0 )
        {
          v33 = v23;
          v34 = KeGetPcr()->Prcb.Number;
          McTemplateK0qqqqqqqq_EtwWriteTransfer(
            v34,
            (unsigned int)&ndisPeriodicReceivesNblCounts,
            (_DWORD)v9 + 4008,
            (*((_QWORD *)v9 + 503) >> 24) & 0xFFFFFF,
            v34,
            v6,
            v18,
            *(_DWORD *)LowLimit,
            *((_DWORD *)&ndisPeriodicReceivesNblCounts + v33),
            v22,
            v21);
        }
      }
    }
    if ( v12 && *(_DWORD *)ndisNblTrackerMode )
      ndisNblTrackerTransferOwnershipInternal(
        v8,
        *((struct NDIS_NBL_TRACKER_HANDLE__ **)v9 + 313),
        *((struct NDIS_NBL_TRACKER_HANDLE__ **)v9 + 510),
        NdisNblTrackerEvent_ReturnedToMiniportResources,
        v13);
    if ( (Microsoft_Windows_Networking_CorrelationEnabled || byte_14011D730) && v12 )
      ndisMarkNetBufferListCorrelationIdsAsUsed(v8);
  }
  else
  {
    ndisMDummyReceiveNetBufferLists(v9, v8, PortNumber, NumberOfNetBufferLists, ReceiveFlags);
    v12 = ReceiveFlags & 2;
  }
  if ( v107 )
  {
    v62 = Number;
    if ( Number == -1 )
      v62 = KeGetPcr()->Prcb.Number;
    v63 = v104 + ndisPcwPerCpuDataStride * v62 + ndisPcwOffsetToPerCpuData;
    v64 = __rdtsc();
    *(_QWORD *)(v63 + 120) += (((unsigned __int64)HIDWORD(v64) << 32) | (unsigned int)v64) - *(_QWORD *)(v63 + 320);
    v65 = v87;
    *(_QWORD *)(v63 + 320) = 0;
    if ( v65 != 2 )
      KeLowerIrql(v65);
  }
  if ( v12 )
  {
    if ( ndisNblContextVerifierMode )
    {
      if ( ndisNblContextVerifierMode != 3 )
      {
        v60 = *((_QWORD *)v9 + 314);
        if ( v60 )
        {
          switch ( *(_BYTE *)v60 )
          {
            case 5:
              v61 = *(_DWORD *)(v60 + 56) >> 10;
              break;
            case 0x11:
              v61 = *(_DWORD *)(v60 + 3688) >> 12;
              break;
            case 0x12:
              v61 = *(_DWORD *)(v60 + 224) >> 31;
              goto LABEL_138;
            default:
              return;
          }
          LOBYTE(v61) = v61 & 1;
LABEL_138:
          if ( (_BYTE)v61 )
            ndisRemoveNblContextTerminator(v8, *((struct _NDIS_OBJECT_HEADER **)v9 + 314));
        }
      }
    }
  }
}

```

## disassembly

```asm
0x14002cc10  push    rbp
0x14002cc12  push    rbx
0x14002cc13  push    rdi
0x14002cc14  push    r12
0x14002cc16  push    r13
0x14002cc18  push    r14
0x14002cc1a  push    r15
0x14002cc1c  lea     rbp, [rsp-70h]
0x14002cc21  sub     rsp, 170h
0x14002cc28  mov     rax, cs:__security_cookie
0x14002cc2f  xor     rax, rsp
0x14002cc32  mov     [rbp+0A0h+var_50], rax
0x14002cc36  cmp     dword ptr [rcx+30h], 0
0x14002cc3a  mov     r13d, r9d
0x14002cc3d  mov     [rbp+0A0h+var_118], r9d
0x14002cc41  mov     r10d, r8d
0x14002cc44  mov     dword ptr [rsp+1A0h+var_130], r8d
0x14002cc49  mov     r12, rdx
0x14002cc4c  mov     [rbp+0A0h+var_C0], rdx
0x14002cc50  mov     rdi, rcx
0x14002cc53  mov     [rbp+0A0h+var_B8], rcx
0x14002cc57  mov     [rbp+0A0h+var_120], rdx
0x14002cc5b  mov     [rsp+1A0h+var_140], r9d
0x14002cc60  jnz     loc_14002D1B7
0x14002cc66  xor     r14d, r14d
0x14002cc69  xor     ebx, ebx
0x14002cc6b  mov     [rbp+0A0h+var_B0], r14
0x14002cc6f  cmp     [rcx+50h], ebx
0x14002cc72  jnz     loc_14002D1B7
0x14002cc78  mov     eax, cs:?ndisNblContextVerifierMode@@3W4NDIS_NBL_CONTEXT_VERIFIER_MODE@@A; NDIS_NBL_CONTEXT_VERIFIER_MODE ndisNblContextVerifierMode
0x14002cc7e  mov     r15d, [rbp+0A0h+ReceiveFlags]
0x14002cc85  mov     [rsp+1A0h+var_38], rsi
0x14002cc8d  test    eax, eax
0x14002cc8f  jnz     loc_14002D172
0x14002cc95  test    dword ptr [rdi+0E68h], 800h
0x14002cc9f  mov     [rbp+0A0h+var_D0], 0FFFFFFFFh
0x14002cca6  mov     [rsp+1A0h+var_138], 2
0x14002ccab  jnz     loc_14002D7AF
0x14002ccb1  and     ebx, 4
0x14002ccb4  mov     [rbp+0A0h+var_98], ebx
0x14002ccb7  jnz     loc_14002D590
0x14002ccbd  mov     eax, [rdi+0A78h]
0x14002ccc3  test    al, 1
0x14002ccc5  jnz     loc_14002D781
0x14002cccb  cmp     byte ptr [rdi+0A68h], 0
0x14002ccd2  jz      loc_14002DB99
0x14002ccd8  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14002ccde  test    eax, eax
0x14002cce0  jnz     loc_14002D081
0x14002cce6  cmp     cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A, 0; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x14002cced  mov     esi, r15d
0x14002ccf0  mov     r14d, r15d
0x14002ccf3  jnz     loc_14002CEE9
0x14002ccf9  and     esi, 2
0x14002ccfc  and     r14d, 1
0x14002cd00  cmp     cs:byte_14011D730, 0
0x14002cd07  jnz     loc_14002D6BB
0x14002cd0d  mov     rax, 0FFFFF78000000320h
0x14002cd17  mov     rax, [rax]
0x14002cd1a  mov     rbx, [rdi+9D0h]
0x14002cd21  mov     r10, [rdi+0A40h]
0x14002cd28  mov     rcx, [rdi+9C0h]
0x14002cd2f  mov     [rbp+0A0h+var_A8], rax
0x14002cd33  cmp     byte ptr [rbx], 11h
0x14002cd36  mov     qword ptr [rsp+1A0h+var_140], r10
0x14002cd3b  mov     [rsp+1A0h+var_128], rcx
0x14002cd40  jnz     loc_14002CF1B
0x14002cd46  mov     r8d, dword ptr [rsp+1A0h+var_130]
0x14002cd4b  mov     r9d, r13d
0x14002cd4e  mov     rdx, r12
0x14002cd51  mov     dword ptr [rsp+1A0h+Context], r15d
0x14002cd56  mov     rax, r10
0x14002cd59  call    _guard_dispatch_icall
0x14002cd5e  mov     rax, ds:0FFFFF78000000320h
0x14002cd68  sub     rax, [rbp+0A0h+var_A8]
0x14002cd6c  mov     ecx, cs:?ndisTimeIncrement@@3KA; ulong ndisTimeIncrement
0x14002cd72  imul    rcx, rax
0x14002cd76  mov     rax, 346DC5D63886594Bh
0x14002cd80  imul    rcx
0x14002cd83  mov     rbx, rdx
0x14002cd86  sar     rbx, 0Bh
0x14002cd8a  mov     rax, rbx
0x14002cd8d  shr     rax, 3Fh
0x14002cd91  add     rbx, rax
0x14002cd94  test    r14d, r14d
0x14002cd97  jz      loc_14002D0D5
0x14002cd9d  xor     eax, eax
0x14002cd9f  xorps   xmm0, xmm0
0x14002cda2  mov     dword ptr [rbp+0A0h+WatchdogInformation+10h], eax
0x14002cda5  mov     eax, 200h
0x14002cdaa  mov     [rsp+1A0h+var_140], eax
0x14002cdae  mov     dword ptr [rsp+1A0h+var_128], eax
0x14002cdb2  movups  xmmword ptr [rbp+0A0h+WatchdogInformation], xmm0
0x14002cdb6  mov     eax, gs:1A4h
0x14002cdbe  shl     eax, 0Ch
0x14002cdc1  mov     ecx, eax
0x14002cdc3  mov     rax, [rdi+0CE0h]
0x14002cdca  add     rax, rcx
0x14002cdcd  lea     rcx, [rbp+0A0h+WatchdogInformation]; WatchdogInformation
0x14002cdd1  mov     [rbp+0A0h+var_A8], rax
0x14002cdd5  mov     r15d, [rax]
0x14002cdd8  lea     rax, ?ndisPeriodicReceivesNblCounts@@3PAKA; ulong near * ndisPeriodicReceivesNblCounts
0x14002cddf  lea     rax, [rax+r15*4]
0x14002cde3  mov     [rbp+0A0h+LowLimit], rax
0x14002cde7  mov     eax, [rax]
0x14002cde9  mov     [rsp+1A0h+var_134], eax
0x14002cded  call    cs:__imp_KeQueryDpcWatchdogInformation
0x14002cdf4  nop     dword ptr [rax+rax+00h]
0x14002cdf9  test    eax, eax
0x14002cdfb  js      loc_14002D0EE
0x14002ce01  mov     ecx, dword ptr [rbp+0A0h+WatchdogInformation]
0x14002ce04  mov     r8d, 400h
0x14002ce0a  mov     r9d, [rsp+1A0h+var_134]
0x14002ce0f  test    ecx, ecx
0x14002ce11  jz      short loc_14002CE31
0x14002ce13  mov     eax, dword ptr [rbp+0A0h+WatchdogInformation+4]
0x14002ce16  xor     edx, edx
0x14002ce18  shl     eax, 0Ah
0x14002ce1b  div     ecx
0x14002ce1d  mov     ecx, r8d
0x14002ce20  xor     edx, edx
0x14002ce22  sub     ecx, eax
0x14002ce24  imul    ecx, r9d
0x14002ce28  mov     eax, ecx
0x14002ce2a  div     r13d
0x14002ce2d  mov     [rsp+1A0h+var_140], eax
0x14002ce31  mov     ecx, dword ptr [rbp+0A0h+WatchdogInformation+8]
0x14002ce34  test    ecx, ecx
0x14002ce36  jz      loc_14002D0EE
0x14002ce3c  mov     eax, dword ptr [rbp+0A0h+WatchdogInformation+0Ch]
0x14002ce3f  xor     edx, edx
0x14002ce41  shl     eax, 0Ah
0x14002ce44  div     ecx
0x14002ce46  cmp     eax, 200h
0x14002ce4b  cmova   eax, r8d
0x14002ce4f  xor     edx, edx
0x14002ce51  sub     r8d, eax
0x14002ce54  imul    r8d, r9d
0x14002ce58  mov     eax, r8d
0x14002ce5b  div     r13d
0x14002ce5e  mov     r10d, eax
0x14002ce61  mov     edx, [rsp+1A0h+var_140]
0x14002ce65  lea     ecx, [r15+1]
0x14002ce69  cmp     ecx, 0Bh
0x14002ce6c  jb      loc_14002D0F8
0x14002ce72  test    r15d, r15d
0x14002ce75  jz      short loc_14002CE83
0x14002ce77  cmp     edx, 300h
0x14002ce7d  ja      loc_14002D572
0x14002ce83  test    esi, esi
0x14002ce85  jnz     loc_14002DA22
0x14002ce8b  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14002ce91  test    eax, eax
0x14002ce93  jnz     loc_14002DA55
0x14002ce99  cmp     cs:byte_14011D730, al
0x14002ce9f  jnz     loc_14002DA55
0x14002cea5  cmp     [rbp+0A0h+var_98], 0
0x14002cea9  jnz     loc_14002D61C
0x14002ceaf  test    esi, esi
0x14002ceb1  jz      short loc_14002CEC1
0x14002ceb3  mov     eax, cs:?ndisNblContextVerifierMode@@3W4NDIS_NBL_CONTEXT_VERIFIER_MODE@@A; NDIS_NBL_CONTEXT_VERIFIER_MODE ndisNblContextVerifierMode
0x14002ceb9  test    eax, eax
0x14002cebb  jnz     loc_14002D5DA
0x14002cec1  mov     rsi, [rsp+1A0h+var_38]
0x14002cec9  mov     rcx, [rbp+0A0h+var_50]
0x14002cecd  xor     rcx, rsp; StackCookie
0x14002ced0  call    __security_check_cookie
0x14002ced5  add     rsp, 170h
0x14002cedc  pop     r15
0x14002cede  pop     r14
0x14002cee0  pop     r13
0x14002cee2  pop     r12
0x14002cee4  pop     rdi
0x14002cee5  pop     rbx
0x14002cee6  pop     rbp
0x14002cee7  retn
0x14002cee9  mov     r8, [rdi+9C8h]; struct NDIS_NBL_TRACKER_HANDLE__ *
0x14002cef0  xor     r9d, r9d
0x14002cef3  mov     rdx, [rdi+0FF0h]; struct NDIS_NBL_TRACKER_HANDLE__ *
0x14002cefa  and     r14d, 1
0x14002cefe  and     esi, 2
0x14002cf01  mov     dword ptr [rsp+1A0h+Context], r14d; unsigned int
0x14002cf06  mov     rcx, r12; struct _NET_BUFFER_LIST *
0x14002cf09  setnz   r9b
0x14002cf0d  sub     r9d, 0FFFFFF80h; enum _NDIS_NBL_TRACKER_OWNERSHIP_EVENT
0x14002cf11  call    ?ndisNblTrackerTransferOwnershipInternal@@YAXPEAU_NET_BUFFER_LIST@@PEAUNDIS_NBL_TRACKER_HANDLE__@@1W4_NDIS_NBL_TRACKER_OWNERSHIP_EVENT@@K@Z; ndisNblTrackerTransferOwnershipInternal(_NET_BUFFER_LIST *,NDIS_NBL_TRACKER_HANDLE__ *,NDIS_NBL_TRACKER_HANDLE__ *,_NDIS_NBL_TRACKER_OWNERSHIP_EVENT,ulong)
0x14002cf16  jmp     loc_14002CD00
0x14002cf1b  test    esi, esi
0x14002cf1d  jnz     short loc_14002CF3C
0x14002cf1f  test    r14d, r14d
0x14002cf22  jnz     loc_14002D26B
0x14002cf28  call    cs:__imp_KeGetCurrentIrql
0x14002cf2f  nop     dword ptr [rax+rax+00h]
0x14002cf34  cmp     al, 2
0x14002cf36  jz      loc_14002D26B
0x14002cf3c  mov     eax, cs:Size
0x14002cf42  lea     rdx, [rbp+0A8h]
0x14002cf49  mov     dword ptr [rbp+0A0h+var_120], eax
0x14002cf4c  mov     [rbp+0A0h+LowLimit], 0
0x14002cf54  mov     [rbp+0A0h+HighLimit], 0
0x14002cf5c  mov     eax, gs:1A4h
0x14002cf64  shl     eax, 0Ch
0x14002cf67  mov     ecx, eax
0x14002cf69  mov     rax, cs:qword_14011CF78
0x14002cf70  mov     r8, [rcx+rax]
0x14002cf74  mov     rax, cs:qword_14011CF70
0x14002cf7b  mov     [rbp+0A0h+LowLimit], r8
0x14002cf7f  mov     r9, [rcx+rax]
0x14002cf83  mov     [rbp+0A0h+HighLimit], r9
0x14002cf87  cmp     rdx, r9
0x14002cf8a  jb      loc_14002D7DC
0x14002cf90  lea     rdx, [rbp+0A0h+HighLimit]; HighLimit
0x14002cf94  lea     rcx, [rbp+0A0h+LowLimit]; LowLimit
0x14002cf98  call    cs:__imp_IoGetStackLimits
0x14002cf9f  nop     dword ptr [rax+rax+00h]
0x14002cfa4  mov     r8, [rbp+0A0h+LowLimit]
0x14002cfa8  lea     rdx, [rbp+0A8h]
0x14002cfaf  mov     eax, dword ptr [rbp+0A0h+var_120]
0x14002cfb2  sub     rdx, r8
0x14002cfb5  cmp     rdx, rax
0x14002cfb8  jnb     loc_14002D1D8
0x14002cfbe  mov     rax, [rsp+1A0h+var_128]
0x14002cfc3  mov     ecx, 6000h
0x14002cfc8  mov     r8d, dword ptr [rsp+1A0h+var_130]
0x14002cfcd  mov     qword ptr [rbp+0A0h+Parameter+8], rax
0x14002cfd1  mov     rax, qword ptr [rsp+1A0h+var_140]
0x14002cfd6  mov     qword ptr [rbp+0A0h+var_F0], rax
0x14002cfda  mov     eax, cs:Size
0x14002cfe0  mov     [rbp+0A0h+var_D4], 0
0x14002cfe7  mov     qword ptr [rbp+0A0h+Parameter], rbx
0x14002cfeb  mov     qword ptr [rbp+0A0h+var_F0+8], r12
0x14002cfef  mov     dword ptr [rbp+0A0h+var_E0+4], r13d
0x14002cff3  mov     dword ptr [rbp+0A0h+var_E0], r8d
0x14002cff7  mov     [rbp+0A0h+var_D8], r15d
0x14002cffb  cmp     eax, ecx
0x14002cffd  ja      loc_14002DCF4
0x14002d003  movsxd  r8, ecx; Size
0x14002d006  lea     rdx, [rbp+0A0h+Parameter]; Parameter
0x14002d00a  lea     rcx, ??$ndisDataPathExpandStackCallback@$01$$A6AXPEAXPEAU_NET_BUFFER_LIST@@KKK@Z@@YAXPEAX@Z; Callout
0x14002d011  mov     [rsp+1A0h+Context], 0; Context
0x14002d01a  xor     r9d, r9d; Wait
0x14002d01d  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x14002d024  nop     dword ptr [rax+rax+00h]
0x14002d029  test    eax, eax
0x14002d02b  jns     loc_14002CD5E
0x14002d031  cmp     cs:byte_14011D730, 0
0x14002d038  jnz     loc_14002DCFF
0x14002d03e  mov     edx, 0C000009Ah; int
0x14002d043  mov     rcx, r12; struct _NET_BUFFER_LIST *
0x14002d046  call    ?NdisSetStatusInNblChain@@YAXPEAU_NET_BUFFER_LIST@@H@Z; NdisSetStatusInNblChain(_NET_BUFFER_LIST *,int)
0x14002d04b  xor     ecx, ecx
0x14002d04d  mov     rax, r12
0x14002d050  test    r12, r12
0x14002d053  jz      short loc_14002D05F
0x14002d055  mov     rax, [rax]
0x14002d058  inc     ecx
0x14002d05a  test    rax, rax
0x14002d05d  jnz     short loc_14002D055
0x14002d05f  lock add [rbx+124h], ecx
0x14002d066  test    esi, esi
0x14002d068  jnz     loc_14002CD5E
0x14002d06e  xor     r8d, r8d; unsigned __int8
0x14002d071  mov     rdx, r12; struct _NET_BUFFER_LIST *
0x14002d074  mov     rcx, rbx; struct _NDIS_FILTER_BLOCK *
0x14002d077  call    ?ndisQueueStackExpansionFallbackNbls@@YAXPEAU_NDIS_FILTER_BLOCK@@PEAU_NET_BUFFER_LIST@@E@Z; ndisQueueStackExpansionFallbackNbls(_NDIS_FILTER_BLOCK *,_NET_BUFFER_LIST *,uchar)
0x14002d07c  jmp     loc_14002CD5E
0x14002d081  mov     rax, [r12+0F8h]
0x14002d089  test    rax, rax
0x14002d08c  jnz     loc_14002D219
0x14002d092  mov     rdx, r12
0x14002d095  mov     ecx, r13d
0x14002d098  lock xadd cs:dword_14011AE28, ecx
0x14002d0a0  lea     eax, [rcx+r13]
0x14002d0a4  cmp     eax, ecx
0x14002d0a6  jb      loc_14002DCE4
0x14002d0ac  mov     rax, [rdx+0F8h]
0x14002d0b3  test    rax, rax
0x14002d0b6  jnz     loc_14002D4BA
0x14002d0bc  mov     eax, ecx
0x14002d0be  inc     ecx
0x14002d0c0  mov     [rdx+0F8h], rax
0x14002d0c7  mov     rdx, [rdx]
0x14002d0ca  test    rdx, rdx
0x14002d0cd  jz      loc_14002CCE6
0x14002d0d3  jmp     short loc_14002D0AC
0x14002d0d5  call    cs:__imp_KeGetCurrentIrql
0x14002d0dc  nop     dword ptr [rax+rax+00h]
0x14002d0e1  cmp     al, 2
0x14002d0e3  jnz     loc_14002CE83
0x14002d0e9  jmp     loc_14002CD9D
0x14002d0ee  mov     r10d, dword ptr [rsp+1A0h+var_128]
0x14002d0f3  jmp     loc_14002CE61
0x14002d0f8  cmp     edx, 200h
0x14002d0fe  jnb     loc_14002CE72
0x14002d104  mov     rax, [rbp+0A0h+var_A8]
0x14002d108  mov     [rax], ecx
0x14002d10a  test    cs:byte_14011B005, 2
0x14002d111  jz      loc_14002CE83
0x14002d117  mov     [rsp+1A0h+var_150], r10d
0x14002d11c  lea     r8, [rdi+0FA8h]
  ... truncated ...
```
