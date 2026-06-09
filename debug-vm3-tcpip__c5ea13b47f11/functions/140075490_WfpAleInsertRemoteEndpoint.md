# WfpAleInsertRemoteEndpoint

- ea: `0x140075490`
- end: `0x140076250`
- name: `WfpAleInsertRemoteEndpoint`
- size: `3520`
- prototype: `__int64 __usercall@<rax>(PKSPIN_LOCK SpinLock@<rcx>, __int64, __int16, __int64, __int16, char, __int64, __int16, int, char, __int64, __int64, __int64, int, int, char, char, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `34`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140098370`
- `0x140139410`
- `0x14013ab20`

## callees

- `0x14001a630`
- `0x14001b1a0`
- `0x14002f4a0`
- `0x14002f4d0`
- `0x140050870`
- `0x1400509e0`
- `0x140052870`
- `0x140053bb0`
- `0x1400541c0`
- `0x1400551a0`
- `0x140055a20`
- `0x140073ca0`
- `0x140075090`
- `0x140075490`
- `0x140076258`
- `0x1400762b0`
- `0x140076360`
- `0x1400771e0`
- `0x140077580`
- `0x140077610`
- `0x140077790`
- `0x140077814`
- `0x140077974`
- `0x1400779d8`
- `0x140077ac0`
- `0x140077bc0`
- `0x1400bc8c0`
- `0x1400be690`
- `0x1400d2400`
- `0x14010cf28`
- `0x14014e364`
- `0x140196564`
- `0x1401bf4d0`
- `0x1401bfa80`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400761e3`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400761e3`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140075ce9`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140075ce9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140075a66`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140075a66`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140075c13`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140075c13`
- `ntoskrnl!KeReadStateEvent` at `0x140075558`
- `ntoskrnl!KeReadStateEvent` at `0x140075b97`
- `ntoskrnl!KeReadStateEvent` at `0x1401c62a6`
- `ntoskrnl!KeReadStateEvent` at `0x1401c62bb`
- `ntoskrnl!KeReadStateEvent` at `0x1401c62d0`
- `ntoskrnl!KeReadStateEvent` at `0x1401c62e5`
- `ntoskrnl!KeReadStateEvent` at `0x1401c6338`
- `ntoskrnl!KeReadStateEvent` at `0x1401c634d`
- `ntoskrnl!KeReadStateEvent` at `0x1401c6362`
- `ntoskrnl!KeReadStateEvent` at `0x1401c6377`
- `ntoskrnl!KeReadStateEvent` at `0x1401c63bd`
- `ntoskrnl!KeReadStateEvent` at `0x1401c63d2`
- `ntoskrnl!KeReadStateEvent` at `0x1401c63e7`
- `ntoskrnl!KeReadStateEvent` at `0x1401c63fc`
- `ntoskrnl!KeReadStateEvent` at `0x140075558`
- `ntoskrnl!KeReadStateEvent` at `0x140075b97`
- `ntoskrnl!KeReadStateEvent` at `0x1401c62a6`
- `ntoskrnl!KeReadStateEvent` at `0x1401c62bb`
- `ntoskrnl!KeReadStateEvent` at `0x1401c62d0`
- `ntoskrnl!KeReadStateEvent` at `0x1401c62e5`
- `ntoskrnl!KeReadStateEvent` at `0x1401c6338`
- `ntoskrnl!KeReadStateEvent` at `0x1401c634d`
- `ntoskrnl!KeReadStateEvent` at `0x1401c6362`
- `ntoskrnl!KeReadStateEvent` at `0x1401c6377`
- `ntoskrnl!KeReadStateEvent` at `0x1401c63bd`
- `ntoskrnl!KeReadStateEvent` at `0x1401c63d2`
- `ntoskrnl!KeReadStateEvent` at `0x1401c63e7`
- `ntoskrnl!KeReadStateEvent` at `0x1401c63fc`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400759a9`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400759a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075e77`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075e77`
- `NETIO!KfdAleInitializeFlowTable` at `0x14007596f`
- `NETIO!KfdAleInitializeFlowTable` at `0x140075d65`
- `NETIO!KfdAleInitializeFlowTable` at `0x14007596f`
- `NETIO!KfdAleInitializeFlowTable` at `0x140075d65`
- `NETIO!KfdAleRemoveFlowContextTable` at `0x14007595b`
- `NETIO!KfdAleRemoveFlowContextTable` at `0x14007595b`
- `NDIS!NdisReleaseRWLock` at `0x140075d1a`
- `NDIS!NdisReleaseRWLock` at `0x140075d1a`

## pseudocode

```c
__int64 __fastcall WfpAleInsertRemoteEndpoint(
        KSPIN_LOCK *SpinLock,
        unsigned __int16 a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int16 a6,
        _DWORD *a7,
        __int16 a8,
        char a9,
        __int64 a10,
        unsigned __int16 a11,
        int a12,
        char a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        unsigned int a17,
        int a18,
        char a19,
        char a20,
        __int64 a21,
        PKSPIN_LOCK *a22,
        _BYTE *a23)
{
  unsigned __int16 v24; // di
  __int64 v26; // rcx
  int v27; // ebx
  __int64 v28; // rsi
  __int64 v29; // r10
  _DWORD *v30; // r8
  _DWORD *v31; // r9
  int v32; // eax
  __int64 v33; // rax
  int v34; // ecx
  char v35; // cl
  unsigned int v36; // eax
  PKSPIN_LOCK v37; // rbx
  char v38; // r12
  char v39; // r13
  char v40; // di
  __int64 v41; // rax
  PKSPIN_LOCK v42; // rcx
  _QWORD *v43; // rax
  __int64 v44; // rdx
  __int128 v45; // xmm0
  KSPIN_LOCK v46; // r13
  __int64 v47; // rcx
  KSPIN_LOCK v48; // r13
  __int64 v49; // rdx
  __int64 v50; // r8
  KSPIN_LOCK v51; // rdi
  int v52; // edx
  int v53; // ecx
  __int64 v54; // r15
  bool v55; // zf
  KSPIN_LOCK v56; // rcx
  _QWORD *v57; // rdx
  int v58; // eax
  __int128 v59; // xmm1
  __int128 v60; // xmm0
  __int128 v61; // xmm1
  __int128 v62; // xmm0
  __int128 v63; // xmm1
  __int128 v64; // xmm0
  void *v65; // rdi
  int v67; // r15d
  int v68; // r9d
  __int64 v69; // rdi
  int ProfileIdFromInterface; // eax
  char v71; // r15
  unsigned __int64 v72; // rbx
  _DWORD *v73; // rdx
  UCHAR v75; // al
  char v76; // dl
  int v77; // ecx
  int v78; // r8d
  __int64 v79; // rax
  KSPIN_LOCK v80; // rdx
  PKSPIN_LOCK *v81; // rcx
  KSPIN_LOCK v82; // rdx
  PKSPIN_LOCK *v83; // rcx
  KSPIN_LOCK v84; // rax
  char v85; // si
  char v86; // di
  char v87; // bl
  LONG v88; // eax
  char StateEvent; // si
  char v90; // di
  char v91; // bl
  LONG v92; // eax
  char v93; // si
  char v94; // di
  char v95; // bl
  LONG v96; // eax
  PVOID v97; // rcx
  char v98; // [rsp+40h] [rbp-C0h]
  char v100; // [rsp+44h] [rbp-BCh]
  KSPIN_LOCK v101; // [rsp+48h] [rbp-B8h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v103; // [rsp+54h] [rbp-ACh]
  _DWORD *v104; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD *v105; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v106; // [rsp+68h] [rbp-98h]
  PKSPIN_LOCK SpinLocka; // [rsp+70h] [rbp-90h] BYREF
  __int64 v108; // [rsp+78h] [rbp-88h]
  __int64 v109; // [rsp+80h] [rbp-80h]
  __int64 v110; // [rsp+88h] [rbp-78h]
  _BYTE *v111; // [rsp+90h] [rbp-70h]
  PKSPIN_LOCK *v112; // [rsp+98h] [rbp-68h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v114[79]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v115[128]; // [rsp+330h] [rbp+230h] BYREF
  _BYTE v116[128]; // [rsp+3B0h] [rbp+2B0h] BYREF

  v24 = a2;
  v110 = a14;
  v106 = a5;
  v108 = a21;
  v111 = a23;
  v109 = a4;
  v112 = a22;
  memset(v114, 0, sizeof(v114));
  v104 = 0;
  v105 = 0;
  v101 = 0;
  *a22 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( KeReadStateEvent(*(PRKEVENT *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters)
    || KeReadStateEvent(LowNonPagedPoolEvent) )
  {
    if ( WfpSystemHasMemoryAvailable && (*((_BYTE *)&WPP_MAIN_CB.Reserved + 10) & 2) != 0 )
    {
      StateEvent = KeReadStateEvent(LowNonPagedPoolEvent);
      v90 = KeReadStateEvent(*(PRKEVENT *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters);
      v91 = KeReadStateEvent(*(PRKEVENT *)&WPP_MAIN_CB.DeviceType);
      v92 = KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Dpc.DeferredRoutine);
      McTemplateK0qqqq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)LOW_MEMORY,
        (unsigned int)MICROSOFT_TCPIP_PROVIDER,
        v92,
        v91,
        v90,
        StateEvent);
      v24 = a2;
    }
    WfpSystemHasMemoryAvailable = 0;
  }
  else
  {
    if ( !WfpSystemHasMemoryAvailable && (*((_BYTE *)&WPP_MAIN_CB.Reserved + 10) & 4) != 0 )
    {
      v85 = KeReadStateEvent(LowNonPagedPoolEvent);
      v86 = KeReadStateEvent(*(PRKEVENT *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters);
      v87 = KeReadStateEvent(*(PRKEVENT *)&WPP_MAIN_CB.DeviceType);
      v88 = KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Dpc.DeferredRoutine);
      McTemplateK0qqqq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)HIGH_MEMORY,
        (unsigned int)MICROSOFT_TCPIP_PROVIDER,
        v88,
        v87,
        v86,
        v85);
      v24 = a2;
    }
    WfpSystemHasMemoryAvailable = 1;
  }
  if ( !WfpSystemHasMemoryAvailable )
  {
    WfpLruCleanupDpc(0, 0);
    if ( (*((_BYTE *)&WPP_MAIN_CB.Reserved + 10) & 4) != 0 )
    {
      v93 = KeReadStateEvent(LowNonPagedPoolEvent);
      v94 = KeReadStateEvent(*(PRKEVENT *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters);
      v95 = KeReadStateEvent(*(PRKEVENT *)&WPP_MAIN_CB.DeviceType);
      v96 = KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Dpc.DeferredRoutine);
      McTemplateK0qqqq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)DPC_LOW_MEMORY,
        (unsigned int)MICROSOFT_TCPIP_PROVIDER,
        v96,
        v95,
        v94,
        v93);
      v24 = a2;
    }
  }
  memset(v114, 0, sizeof(v114));
  v27 = 16;
  if ( v24 == 2 )
  {
    v28 = WfpAllocateFromPerProcessorLookasideList(V4AddressLookasideList, &v104);
    if ( v28 )
      goto LABEL_138;
    v28 = WfpAllocateFromPerProcessorLookasideList(V4AddressLookasideList, &v105);
    if ( v28 )
      goto LABEL_138;
    v29 = v106;
    v30 = v104;
    v31 = v105;
    *v104 = ***(_DWORD ***)(v106 + 16);
    *v31 = *a7;
    LODWORD(v114[61]) = 4;
  }
  else
  {
    if ( v24 != 23 )
    {
      v28 = WfpReportSysErrorAsNtStatus(v26, "WfpAleInsertRemoteEndpoint", 3221225485LL);
LABEL_136:
      if ( v104 )
        PplFreeToLookasideList(V6AddressLookasideList);
      if ( !v105 )
        goto LABEL_86;
      v97 = V6AddressLookasideList;
      goto LABEL_153;
    }
    v28 = WfpAllocateFromPerProcessorLookasideList(V6AddressLookasideList, &v104);
    if ( v28 )
      goto LABEL_136;
    v28 = WfpAllocateFromPerProcessorLookasideList(V6AddressLookasideList, &v105);
    if ( v28 )
      goto LABEL_136;
    v29 = v106;
    v30 = v104;
    v31 = v105;
    *(_OWORD *)v104 = *(_OWORD *)**(_QWORD **)(v106 + 16);
    *(_OWORD *)v31 = *(_OWORD *)a7;
    LODWORD(v114[61]) = 16;
  }
  v32 = LODWORD(v114[6]) | 2;
  v100 = 0;
  BYTE2(v114[77]) = 0;
  LODWORD(v114[6]) |= 2u;
  if ( a13 )
    LODWORD(v114[6]) = v32 | 0x100000;
  if ( a9 )
    _InterlockedOr((volatile signed __int32 *)&v114[6], 0x1000000u);
  if ( (SpinLock[6] & 0x10) != 0 )
    _InterlockedOr((volatile signed __int32 *)&v114[6], 0x10u);
  BYTE5(v114[61]) = a20;
  v33 = *(_QWORD *)(v29 + 8);
  v114[62] = SpinLock;
  WORD2(v114[7]) = a2;
  LODWORD(v114[5]) = a3;
  v114[60] = v30;
  v114[4] = v31;
  BYTE4(v114[61]) = a19;
  LOBYTE(v114[77]) = a13;
  v114[59] = *(_QWORD *)(v33 + 16);
  if ( a2 == 2 )
    v27 = 4;
  LODWORD(v114[61]) = v27;
  if ( a16 )
  {
    v58 = *(_DWORD *)(a16 + 48);
    v59 = *(_OWORD *)(a16 + 184);
    *(_OWORD *)&v114[21] = *(_OWORD *)(a16 + 168);
    v60 = *(_OWORD *)(a16 + 200);
    *(_OWORD *)&v114[23] = v59;
    v61 = *(_OWORD *)(a16 + 216);
    *(_OWORD *)&v114[25] = v60;
    v62 = *(_OWORD *)(a16 + 232);
    *(_OWORD *)&v114[27] = v61;
    v63 = *(_OWORD *)(a16 + 248);
    *(_OWORD *)&v114[29] = v62;
    v64 = *(_OWORD *)(a16 + 264);
    *(_OWORD *)&v114[31] = v63;
    v114[35] = *(_QWORD *)(a16 + 280);
    *(_OWORD *)&v114[33] = v64;
    if ( (v58 & 0x8000) != 0 )
      _InterlockedOr((volatile signed __int32 *)&v114[6], 0x8000u);
    if ( (*(_DWORD *)(a16 + 48) & 0x10000) != 0 )
      _InterlockedOr((volatile signed __int32 *)&v114[6], 0x10000u);
    if ( (*(_DWORD *)(a16 + 48) & 0x2000000) != 0 )
      _InterlockedOr((volatile signed __int32 *)&v114[6], 0x2000000u);
    if ( (*(_DWORD *)(a16 + 48) & 0x4000000) != 0 )
      _InterlockedOr((volatile signed __int32 *)&v114[6], 0x4000000u);
    if ( (*(_DWORD *)(a16 + 48) & 0x8000000) != 0 )
      _InterlockedOr((volatile signed __int32 *)&v114[6], 0x8000000u);
  }
  v34 = v114[37];
  if ( a18 )
    v34 = a18;
  LODWORD(v114[37]) = v34;
  if ( a2 != 2 )
  {
    if ( a3 == 58 && a2 == 23 )
      goto LABEL_22;
LABEL_24:
    HIWORD(v114[7]) = a6;
    LOWORD(v114[8]) = a8;
    goto LABEL_25;
  }
  if ( a3 != 1 )
    goto LABEL_24;
LABEL_22:
  v35 = *(_BYTE *)(a10 + 4);
  LODWORD(v114[8]) = *(_DWORD *)a10;
  BYTE1(v114[71]) = *(_BYTE *)(a10 + 5);
  LOBYTE(v114[71]) = v35;
  BYTE2(v114[71]) = v35;
LABEL_25:
  WfpAlepHashRemoteEndpoint(v114, &v101);
  v36 = WfpAleGetAndWriteLockPartition(v101, &LockState);
  v103 = v36;
  if ( CurrentLifeTimeThresholdIndex < 3
    && (unsigned int)(*(_DWORD *)(pRemoteEndpointTable + 4) * *(_DWORD *)(pRemoteEndpointTable + 92)) > *((_DWORD *)nFlows + CurrentLifeTimeThresholdIndex) )
  {
    ++CurrentLifeTimeThresholdIndex;
  }
  SpinLocka = (PKSPIN_LOCK)WfpAlepFindRemoteEndpoint(v114, &v101, v36);
  v37 = SpinLocka;
  if ( SpinLocka )
  {
    if ( (v114[6] & 0x8000) != 0 )
    {
      if ( gAleDebugEnabled )
      {
        v84 = SpinLocka[19];
        if ( v84 != 0xBADBADFABADBADFAuLL )
        {
          _InterlockedIncrement((volatile signed __int32 *)(v84 + 16));
          _InterlockedIncrement((volatile signed __int32 *)(v37[19] + 48));
        }
      }
      if ( !(unsigned __int8)WfpAleIncrementWaitRefEx(v37 + 16, 2) )
        goto LABEL_29;
    }
    else if ( !(unsigned __int8)WfpAleReferenceEndpoint_0(SpinLocka, 4) )
    {
      goto LABEL_29;
    }
    v98 = 0;
    if ( (v37[6] & 0x8000) == 0 )
      WfpRefreshRemoteEndpointLruEntry(v37 + 63, 0, a17);
    if ( !v37[31] && v114[31] )
    {
      v37[31] = v114[31];
      *(_QWORD *)(a16 + 248) = 0;
    }
LABEL_80:
    v71 = v98;
    v38 = 0;
    v39 = v98;
    v40 = v98;
    *v112 = v37;
    goto LABEL_81;
  }
LABEL_29:
  v98 = 1;
  *(_QWORD *)(a16 + 248) = 0;
  *(_QWORD *)(a16 + 256) = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = WfpAllocateFromPerProcessorLookasideList(RemoteEndpointLookasideList, &SpinLocka);
  v37 = SpinLocka;
  v28 = v41;
  if ( !v41 )
  {
    memset(SpinLocka, 0, 0x278u);
    v42 = v37;
    v43 = v114;
    v44 = 4;
    do
    {
      v42 += 16;
      v45 = *(_OWORD *)v43;
      v43 += 16;
      *((_OWORD *)v42 - 8) = v45;
      *((_OWORD *)v42 - 7) = *((_OWORD *)v43 - 7);
      *((_OWORD *)v42 - 6) = *((_OWORD *)v43 - 6);
      *((_OWORD *)v42 - 5) = *((_OWORD *)v43 - 5);
      *((_OWORD *)v42 - 4) = *((_OWORD *)v43 - 4);
      *((_OWORD *)v42 - 3) = *((_OWORD *)v43 - 3);
      *((_OWORD *)v42 - 2) = *((_OWORD *)v43 - 2);
      *((_OWORD *)v42 - 1) = *((_OWORD *)v43 - 1);
      --v44;
    }
    while ( v44 );
    v46 = v103;
    *(_OWORD *)v42 = *(_OWORD *)v43;
    *((_OWORD *)v42 + 1) = *((_OWORD *)v43 + 1);
    *((_OWORD *)v42 + 2) = *((_OWORD *)v43 + 2);
    *((_OWORD *)v42 + 3) = *((_OWORD *)v43 + 3);
    *((_OWORD *)v42 + 4) = *((_OWORD *)v43 + 4);
    *((_OWORD *)v42 + 5) = *((_OWORD *)v43 + 5);
    *((_OWORD *)v42 + 6) = *((_OWORD *)v43 + 6);
    v42[14] = v43[14];
    v37[74] = v101;
    v101 = v46;
    v28 = WfpHashtableInsert((v46 << 7) + pRemoteEndpointTable + 72, v37 + 72);
    if ( !v28 )
    {
      v40 = 1;
      if ( !(unsigned __int8)WfpAleReferenceEndpoint_0(SpinLock, 2) )
      {
        v28 = WfpReportSysErrorAsNtStatus(v47, "WfpAleInsertRemoteEndpoint", 3221225473LL);
        v39 = 0;
        v71 = 1;
LABEL_81:
        if ( !v28 )
          goto LABEL_82;
        goto LABEL_131;
      }
      if ( (*((_BYTE *)&WPP_MAIN_CB.Reserved + 10) & 1) != 0
        && (memset(v116, 0, sizeof(v116)),
            memset(v115, 0, sizeof(v115)),
            ((void (__fastcall *)(_DWORD, _DWORD, _DWORD, _DWORD, __int16))INETADDR_SETSOCKADDR)(
              *((unsigned __int16 *)v37 + 30),
              (unsigned int)v116,
              v37[60],
              scopeid_unspecified.0,
              *((_WORD *)v37 + 31)),
            ((void (__fastcall *)(_DWORD, _DWORD, _DWORD, _DWORD, __int16))INETADDR_SETSOCKADDR)(
              *((unsigned __int16 *)v37 + 30),
              (unsigned int)v115,
              v37[4],
              scopeid_unspecified.0,
              *((_WORD *)v37 + 32)),
            (*((_BYTE *)&WPP_MAIN_CB.Reserved + 10) & 1) != 0) )
      {
        v75 = SOCKADDR_SIZE(*((_WORD *)v37 + 30));
        v48 = v101;
        McTemplateK0qbr0br0xx_EtwWriteTransfer(
          v77,
          (unsigned int)REMOTEENDPOINT_INSERT_V1,
          v78,
          v75,
          (__int64)v116,
          (__int64)v115,
          v101,
          v76);
      }
      else
      {
        v48 = v101;
      }
      v38 = 1;
      WfpAleInitializeEpochContext(
        a2,
        *((_DWORD *)SpinLock + 10),
        (*((_DWORD *)SpinLock + 12) >> 4) & 1,
        a11,
        a12,
        (__int64)(v37 + 45));
      _InterlockedOr((volatile signed __int32 *)v37 + 12, 0x1000u);
      WfpAleInitializeWaitRef(v37 + 16, v49, v50, v37);
      if ( *(_QWORD *)(a16 + 96) )
      {
        KfdAleRemoveFlowContextTable();
        v28 = KfdAleInitializeFlowTable(v37 + 9, *(_QWORD *)(a16 + 96));
        if ( !v28 )
        {
          v51 = 0;
          v37[14] = *(_QWORD *)(a16 + 112);
          *(_QWORD *)(a16 + 112) = 0;
          *(_QWORD *)(a16 + 96) = 0;
LABEL_39:
          WfpAleReferenceEndpointNoLock(v37, 1);
          KeInitializeSpinLock(v37);
          *((_DWORD *)v37 + 2) = 0;
          v28 = 0;
          v37[2] = 0;
          v37[3] = 0;
          if ( (SpinLock[25] & 4) != 0 )
            IPSecSetRequireSecurityOnEndpoint(v37);
          *((_DWORD *)v37 + 50) |= SpinLock[25] & 0x7000884;
          WfpAleCopySecureSocketInfoFromParent(SpinLock, v37);
          if ( v108 )
          {
            v28 = WfpAleProcessPostClassifySocketOptions(v37, v108);
            if ( v28 )
              goto LABEL_140;
          }
          if ( !a13 || a19 != 1 || (v53 = 1, (v37[6] & 0x4000) == 0) )
            v53 = 0;
          if ( (v37[6] & 0x8000) != 0 || v53 )
          {
            *((_DWORD *)v37 + 155) = a17;
          }
          else
          {
            v54 = 0;
            v101 = 0;
            if ( gAleDebugEnabled )
            {
              v79 = WfpPoolAllocNonPaged(27, 1281715265, &v101);
              v51 = v101;
              v54 = v79;
              if ( !v79 )
                WfpStringCchCopyA("WfpAleInsertRemoteEndpoint", 27, v101);
            }
            KeAcquireInStackQueuedSpinLock(SpinLock, &LockHandle);
            while ( *((_DWORD *)SpinLock + 2) )
              ;
            v55 = gAleDebugEnabled == 1;
            SpinLock[2] = (KSPIN_LOCK)KeGetCurrentThread();
            if ( v55 && !v54 )
              SpinLock[3] = v51;
            WfpAlepInsertEntryIntoLruList(v103, v37, a17);
            v56 = 16 * v48 + SpinLock[69];
            v57 = *(_QWORD **)(v56 + 8);
            if ( *v57 != v56 )
LABEL_54:
              __fastfail(3u);
            v100 = 1;
            v37[75] = v56;
            v37[76] = (KSPIN_LOCK)v57;
            *v57 = v37 + 75;
            *(_QWORD *)(v56 + 8) = v37 + 75;
            _InterlockedOr((volatile signed __int32 *)v37 + 12, 0x20000u);
            v55 = gAleDebugEnabled == 1;
            v65 = 0;
            SpinLock[2] = 0;
            if ( v55 )
            {
              v65 = (void *)SpinLock[3];
              SpinLock[3] = 0;
            }
            KeReleaseInStackQueuedSpinLock(&LockHandle);
            if ( gAleDebugEnabled == 1 && v65 )
              ExFreePoolWithTag(v65, 0);
          }
          if ( v109 )
          {
            if ( a13 )
            {
              v68 = v110;
              v67 = 0;
              a15 = 0;
            }
            else
            {
              v67 = 1;
              v68 = 0;
            }
            v69 = *(_QWORD *)(v109 + 16);
            ProfileIdFromInterface = WfpGetProfileIdFromInterface(v109, v52, v106, v68, a15);
            AleEdgeIFsInit((_DWORD)v37 + 304, (_DWORD)v37 + 360, v69, v67, ProfileIdFromInterface);
          }
          WfpAleReferenceEndpointNoLock(v37, 4);
          if ( (v37[6] & 0x8000) != 0 )
            WfpAleReferenceEndpointNoLock(v37, 12);
          if ( v111 )
            *v111 = 1;
          goto LABEL_80;
        }
      }
      else
      {
        v28 = KfdAleInitializeFlowTable(v37 + 9, 0);
        if ( !v28 )
        {
          v51 = 0;
          goto LABEL_39;
        }
      }
    }
    v39 = 0;
  }
LABEL_131:
  v71 = v98;
  if ( v37 && v98 )
  {
    if ( v40 )
      RtlRemoveEntryHashTable(
        (PRTL_DYNAMIC_HASH_TABLE)(pRemoteEndpointTable + 72 + ((unsigned __int64)v103 << 7)),
        (PRTL_DYNAMIC_HASH_TABLE_ENTRY)v37 + 24,
        0);
    if ( v100 )
    {
      v80 = v37[64];
      if ( *(PKSPIN_LOCK *)(v80 + 8) != v37 + 64 )
        goto LABEL_54;
      v81 = (PKSPIN_LOCK *)v37[65];
      if ( *v81 != v37 + 64 )
        goto LABEL_54;
      *v81 = (PKSPIN_LOCK)v80;
      *(_QWORD *)(v80 + 8) = v81;
      WfpAleDereferenceEndpoint(v37, 3);
    }
    if ( (v37[6] & 0x20000) != 0 )
    {
      AleAcquireEndpointLockEx(SpinLock, &LockHandle);
      v82 = v37[75];
      if ( *(PKSPIN_LOCK *)(v82 + 8) != v37 + 75 )
        goto LABEL_54;
      v83 = (PKSPIN_LOCK *)v37[76];
      if ( *v83 != v37 + 75 )
        goto LABEL_54;
      *v83 = (PKSPIN_LOCK)v82;
      *(_QWORD *)(v82 + 8) = v83;
      _InterlockedAnd((volatile signed __int32 *)v37 + 12, 0xFFFDFFFF);
      AleReleaseEndpointLock(SpinLock, &LockHandle);
    }
    if ( v39 )
    {
      WfpAleDisableWaitRef(v37 + 16);
      WfpAleDereferenceEndpoint(v37, 1);
    }
    if ( v38 )
      WfpAleDereferenceEndpoint(SpinLock, 2);
  }
LABEL_82:
  v72 = pRemoteEndpointTable + ((unsigned __int64)v103 << 7);
  if ( gWfpPerProContext )
  {
    v73 = *(_DWORD **)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    if ( *v73 == 4 )
      *v73 = 0;
  }
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v72 + 64), &LockState);
  if ( !v71 )
  {
    if ( a2 != 2 )
      goto LABEL_136;
LABEL_138:
    if ( v104 )
      PplFreeToLookasideList(V4AddressLookasideList);
    if ( !v105 )
      goto LABEL_86;
    v97 = V4AddressLookasideList;
LABEL_153:
    PplFreeToLookasideList(v97);
  }
LABEL_86:
  if ( v28 )
LABEL_140:
    WfpReportError(v28, "WfpAleInsertRemoteEndpoint");
  return v28;
}

```

## disassembly

```asm
0x140075490  push    rbp
0x140075492  push    rbx
0x140075493  push    rsi
0x140075494  push    rdi
0x140075495  push    r12
0x140075497  push    r13
0x140075499  push    r14
0x14007549b  push    r15
0x14007549d  lea     rbp, [rsp-348h]
0x1400754a5  sub     rsp, 448h
0x1400754ac  mov     rax, cs:__security_cookie
0x1400754b3  xor     rax, rsp
0x1400754b6  mov     [rbp+380h+var_50], rax
0x1400754bd  mov     rax, [rbp+380h+arg_68]
0x1400754c4  mov     r12d, r8d
0x1400754c7  mov     rbx, [rbp+380h+arg_A8]
0x1400754ce  movzx   edi, dx
0x1400754d1  mov     r13, [rbp+380h+arg_48]
0x1400754d8  mov     r14, rcx
0x1400754db  mov     r15, [rbp+380h+arg_78]
0x1400754e2  lea     rcx, [rbp+380h+var_3C8]; void *
0x1400754e6  mov     [rbp+380h+var_3F8], rax
0x1400754ea  mov     r8d, 278h; Size
0x1400754f0  mov     rax, [rbp+380h+arg_20]
0x1400754f7  mov     [rsp+480h+var_418], rax
0x1400754fc  mov     rax, [rbp+380h+arg_A0]
0x140075503  mov     [rsp+480h+var_408], rax
0x140075508  mov     rax, [rbp+380h+arg_B0]
0x14007550f  mov     [rsp+480h+var_43E], dx
0x140075514  xor     edx, edx; Val
0x140075516  mov     [rbp+380h+var_3F0], rax
0x14007551a  mov     [rbp+380h+var_400], r9
0x14007551e  mov     [rbp+380h+var_3E8], rbx
0x140075522  call    memset
0x140075527  xor     ecx, ecx
0x140075529  xor     eax, eax
0x14007552b  mov     [rsp+480h+var_428], rcx
0x140075530  xorps   xmm0, xmm0
0x140075533  mov     [rsp+480h+var_420], rcx
0x140075538  mov     [rsp+480h+var_438], rcx
0x14007553d  mov     [rbx], rcx
0x140075540  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+28h; Event
0x140075547  mov     word ptr [rsp+480h+LockState.OldIrql], ax
0x14007554c  mov     [rsp+480h+LockState.Flags], al
0x140075550  movups  xmmword ptr [rbp+380h+LockHandle.LockQueue.Next], xmm0
0x140075554  mov     qword ptr [rbp+380h+LockHandle.OldIrql], rax
0x140075558  call    cs:__imp_KeReadStateEvent
0x14007555f  nop     dword ptr [rax+rax+00h]
0x140075564  test    eax, eax
0x140075566  jz      loc_140075B90
0x14007556c  movzx   eax, cs:WfpSystemHasMemoryAvailable
0x140075573  test    al, al
0x140075575  jnz     loc_1401C6324
0x14007557b  mov     cs:WfpSystemHasMemoryAvailable, 0
0x140075582  movzx   eax, cs:WfpSystemHasMemoryAvailable
0x140075589  test    al, al
0x14007558b  jz      loc_140075E88
0x140075591  xor     edx, edx; Val
0x140075593  lea     rcx, [rbp+380h+var_3C8]; void *
0x140075597  mov     r8d, 278h; Size
0x14007559d  call    memset
0x1400755a2  mov     ebx, 10h
0x1400755a7  cmp     di, 2
0x1400755ab  jnz     loc_140075DA0
0x1400755b1  mov     rcx, cs:V4AddressLookasideList
0x1400755b8  lea     rdx, [rsp+480h+var_428]
0x1400755bd  call    WfpAllocateFromPerProcessorLookasideList
0x1400755c2  mov     rsi, rax
0x1400755c5  test    rax, rax
0x1400755c8  jnz     loc_14007621C
0x1400755ce  mov     rcx, cs:V4AddressLookasideList
0x1400755d5  lea     rdx, [rsp+480h+var_420]
0x1400755da  call    WfpAllocateFromPerProcessorLookasideList
0x1400755df  mov     rsi, rax
0x1400755e2  test    rax, rax
0x1400755e5  jnz     loc_14007621C
0x1400755eb  mov     r10, [rsp+480h+var_418]
0x1400755f0  mov     r11d, 4
0x1400755f6  mov     r8, [rsp+480h+var_428]
0x1400755fb  mov     r9, [rsp+480h+var_420]
0x140075600  mov     rax, [r10+10h]
0x140075604  mov     rcx, [rax]
0x140075607  mov     eax, [rcx]
0x140075609  mov     [r8], eax
0x14007560c  mov     rax, [rbp+380h+arg_30]
0x140075613  mov     ecx, [rax]
0x140075615  mov     [r9], ecx
0x140075618  mov     [rbp+380h+var_1E0], r11d
0x14007561f  mov     eax, [rbp+380h+var_398]
0x140075622  movzx   ecx, [rbp+380h+arg_60]
0x140075629  or      eax, 2
0x14007562c  mov     [rsp+480h+var_43C], 0
0x140075631  mov     [rbp+380h+var_15E], 0
0x140075638  mov     [rbp+380h+var_398], eax
0x14007563b  test    cl, cl
0x14007563d  jz      short loc_140075646
0x14007563f  bts     eax, 14h
0x140075643  mov     [rbp+380h+var_398], eax
0x140075646  cmp     [rbp+380h+arg_40], 0
0x14007564d  jz      short loc_140075657
0x14007564f  lock or [rbp+380h+var_398], 1000000h
0x140075657  mov     eax, [r14+30h]
0x14007565b  test    bl, al
0x14007565d  jnz     loc_140075E20
0x140075663  movzx   eax, [rbp+380h+arg_98]
0x14007566a  movzx   edx, [rsp+480h+var_43E]
0x14007566f  movzx   edi, [rbp+380h+arg_90]
0x140075676  mov     [rbp+380h+var_1DB], al
0x14007567c  mov     rax, [r10+8]
0x140075680  mov     [rbp+380h+var_1D8], r14
0x140075687  mov     [rbp+380h+var_38C], dx
0x14007568b  mov     [rbp+380h+var_3A0], r12d
0x14007568f  mov     [rbp+380h+var_1E8], r8
0x140075696  mov     [rbp+380h+var_3A8], r9
0x14007569a  mov     [rbp+380h+var_1DC], dil
0x1400756a1  mov     [rbp+380h+var_160], cl
0x1400756a7  mov     rcx, [rax+10h]
0x1400756ab  mov     eax, 2
0x1400756b0  cmp     ax, dx
0x1400756b3  mov     [rbp+380h+var_1F0], rcx
0x1400756ba  cmovz   ebx, r11d
0x1400756be  mov     [rbp+380h+var_1E0], ebx
0x1400756c4  test    r15, r15
0x1400756c7  jnz     loc_140075AC9
0x1400756cd  mov     eax, [rbp+380h+arg_88]
0x1400756d3  test    eax, eax
0x1400756d5  mov     ecx, [rbp+380h+var_2A0]
0x1400756db  cmovnz  ecx, eax
0x1400756de  mov     [rbp+380h+var_2A0], ecx
0x1400756e4  cmp     dx, 2
0x1400756e8  jnz     short loc_140075715
0x1400756ea  cmp     r12d, 1
0x1400756ee  jnz     short loc_14007571F
0x1400756f0  mov     eax, [r13+0]
0x1400756f4  movzx   ecx, byte ptr [r13+4]
0x1400756f9  mov     [rbp+380h+var_388], eax
0x1400756fc  movzx   eax, byte ptr [r13+5]
0x140075701  mov     [rbp+380h+var_18F], al
0x140075707  mov     [rbp+380h+var_190], cl
0x14007570d  mov     [rbp+380h+var_18E], cl
0x140075713  jmp     short loc_140075735
0x140075715  cmp     r12d, 3Ah ; ':'
0x140075719  jz      loc_140075FC4
0x14007571f  movzx   eax, [rbp+380h+arg_28]
0x140075726  mov     [rbp+380h+var_38A], ax
0x14007572a  movzx   eax, [rbp+380h+arg_38]
0x140075731  mov     word ptr [rbp+380h+var_388], ax
0x140075735  lea     rdx, [rsp+480h+var_438]
0x14007573a  lea     rcx, [rbp+380h+var_3C8]
0x14007573e  call    WfpAlepHashRemoteEndpoint
0x140075743  mov     rcx, [rsp+480h+var_438]
0x140075748  lea     rdx, [rsp+480h+LockState]
0x14007574d  call    WfpAleGetAndWriteLockPartition
0x140075752  movsxd  r8, cs:CurrentLifeTimeThresholdIndex
0x140075759  mov     [rsp+480h+var_42C], eax
0x14007575d  cmp     r8d, 3
0x140075761  jge     short loc_140075782
0x140075763  mov     rcx, cs:pRemoteEndpointTable
0x14007576a  lea     r9, nFlows
0x140075771  mov     edx, [rcx+5Ch]
0x140075774  imul    edx, [rcx+4]
0x140075778  cmp     edx, [r9+r8*4]
0x14007577c  ja      loc_140076183
0x140075782  mov     r8d, eax
0x140075785  lea     rdx, [rsp+480h+var_438]
0x14007578a  lea     rcx, [rbp+380h+var_3C8]
0x14007578e  call    WfpAlepFindRemoteEndpoint
0x140075793  mov     [rsp+480h+SpinLock], rax
0x140075798  mov     rbx, rax
0x14007579b  test    rax, rax
0x14007579e  jnz     loc_140075FD3
0x1400757a4  xor     eax, eax
0x1400757a6  mov     [rsp+480h+var_440], 1
0x1400757ab  mov     [r15+0F8h], rax
0x1400757b2  lea     rdx, [rsp+480h+SpinLock]
0x1400757b7  mov     [r15+100h], rax
0x1400757be  xor     r12b, r12b
0x1400757c1  mov     rcx, cs:RemoteEndpointLookasideList
0x1400757c8  xor     r13b, r13b
0x1400757cb  xor     dil, dil
0x1400757ce  call    WfpAllocateFromPerProcessorLookasideList
0x1400757d3  mov     rbx, [rsp+480h+SpinLock]
0x1400757d8  mov     rsi, rax
0x1400757db  test    rax, rax
0x1400757de  jnz     loc_1400761A2
0x1400757e4  xor     edx, edx; Val
0x1400757e6  mov     r8d, 278h; Size
0x1400757ec  mov     rcx, rbx; void *
0x1400757ef  call    memset
0x1400757f4  mov     rcx, rbx
0x1400757f7  lea     rax, [rbp+380h+var_3C8]
0x1400757fb  mov     edx, 4
0x140075800  lea     rcx, [rcx+80h]
0x140075807  movups  xmm0, xmmword ptr [rax]
0x14007580a  lea     rax, [rax+80h]
0x140075811  movups  xmmword ptr [rcx-80h], xmm0
0x140075815  movups  xmm1, xmmword ptr [rax-70h]
0x140075819  movups  xmmword ptr [rcx-70h], xmm1
0x14007581d  movups  xmm0, xmmword ptr [rax-60h]
0x140075821  movups  xmmword ptr [rcx-60h], xmm0
0x140075825  movups  xmm1, xmmword ptr [rax-50h]
0x140075829  movups  xmmword ptr [rcx-50h], xmm1
0x14007582d  movups  xmm0, xmmword ptr [rax-40h]
0x140075831  movups  xmmword ptr [rcx-40h], xmm0
0x140075835  movups  xmm1, xmmword ptr [rax-30h]
0x140075839  movups  xmmword ptr [rcx-30h], xmm1
0x14007583d  movups  xmm0, xmmword ptr [rax-20h]
0x140075841  movups  xmmword ptr [rcx-20h], xmm0
0x140075845  movups  xmm1, xmmword ptr [rax-10h]
0x140075849  movups  xmmword ptr [rcx-10h], xmm1
0x14007584d  sub     rdx, 1
0x140075851  jnz     short loc_140075800
0x140075853  movups  xmm0, xmmword ptr [rax]
0x140075856  mov     r13d, [rsp+480h+var_42C]
0x14007585b  lea     rdx, [rbx+240h]
0x140075862  movups  xmmword ptr [rcx], xmm0
0x140075865  movups  xmm1, xmmword ptr [rax+10h]
0x140075869  movups  xmmword ptr [rcx+10h], xmm1
0x14007586d  movups  xmm0, xmmword ptr [rax+20h]
0x140075871  movups  xmmword ptr [rcx+20h], xmm0
0x140075875  movups  xmm1, xmmword ptr [rax+30h]
0x140075879  movups  xmmword ptr [rcx+30h], xmm1
0x14007587d  movups  xmm0, xmmword ptr [rax+40h]
0x140075881  movups  xmmword ptr [rcx+40h], xmm0
0x140075885  movups  xmm1, xmmword ptr [rax+50h]
0x140075889  movups  xmmword ptr [rcx+50h], xmm1
0x14007588d  movups  xmm0, xmmword ptr [rax+60h]
0x140075891  movups  xmmword ptr [rcx+60h], xmm0
0x140075895  mov     rax, [rax+70h]
0x140075899  mov     [rcx+70h], rax
0x14007589d  mov     rax, [rsp+480h+var_438]
0x1400758a2  mov     [rbx+250h], rax
0x1400758a9  mov     rcx, cs:pRemoteEndpointTable
0x1400758b0  add     rcx, 48h ; 'H'
0x1400758b4  mov     [rsp+480h+var_438], r13
0x1400758b9  shl     r13, 7
0x1400758bd  add     rcx, r13
0x1400758c0  call    WfpHashtableInsert
0x1400758c5  mov     rsi, rax
0x1400758c8  test    rax, rax
0x1400758cb  jnz     loc_14007619F
0x1400758d1  mov     edx, 2
0x1400758d6  mov     rcx, r14
0x1400758d9  mov     dil, 1
0x1400758dc  call    WfpAleReferenceEndpoint_0
0x1400758e1  test    al, al
0x1400758e3  jz      loc_140075E48
0x1400758e9  test    byte ptr cs:WPP_MAIN_CB+14Ah, dil
0x1400758f0  jnz     loc_140075EA3
0x1400758f6  mov     r13, [rsp+480h+var_438]
0x1400758fb  mov     r8d, [r14+30h]
0x1400758ff  lea     rax, [rbx+168h]
0x140075906  movzx   r9d, [rbp+380h+arg_50]
0x14007590e  movzx   r12d, dil
0x140075912  mov     edx, [r14+28h]
0x140075916  movzx   ecx, [rsp+480h+var_43E]
0x14007591b  mov     [rsp+480h+var_458], rax
0x140075920  mov     eax, [rbp+380h+arg_58]
0x140075926  shr     r8d, 4
0x14007592a  and     r8d, 1
0x14007592e  mov     dword ptr [rsp+480h+var_460], eax
0x140075932  call    WfpAleInitializeEpochContext
0x140075937  lock or dword ptr [rbx+30h], 1000h
0x14007593f  lea     rcx, [rbx+80h]
0x140075946  mov     r9, rbx
0x140075949  call    WfpAleInitializeWaitRef
0x14007594e  mov     rcx, [r15+60h]
0x140075952  test    rcx, rcx
0x140075955  jz      loc_140075D5F
0x14007595b  call    cs:__imp_KfdAleRemoveFlowContextTable
0x140075962  nop     dword ptr [rax+rax+00h]
0x140075967  mov     rdx, [r15+60h]
0x14007596b  lea     rcx, [rbx+48h]
0x14007596f  call    cs:__imp_KfdAleInitializeFlowTable
0x140075976  nop     dword ptr [rax+rax+00h]
0x14007597b  mov     rsi, rax
0x14007597e  test    rax, rax
0x140075981  jnz     loc_14007619F
0x140075987  mov     rax, [r15+70h]
0x14007598b  xor     edi, edi
0x14007598d  mov     [rbx+70h], rax
0x140075991  mov     [r15+70h], rdi
0x140075995  mov     [r15+60h], rdi
0x140075999  mov     edx, 1
0x14007599e  mov     rcx, rbx
0x1400759a1  call    WfpAleReferenceEndpointNoLock
0x1400759a6  mov     rcx, rbx; SpinLock
0x1400759a9  call    cs:__imp_KeInitializeSpinLock
0x1400759b0  nop     dword ptr [rax+rax+00h]
0x1400759b5  mov     [rbx+8], edi
0x1400759b8  mov     rsi, rdi
0x1400759bb  mov     [rbx+10h], rdi
0x1400759bf  mov     [rbx+18h], rdi
0x1400759c3  mov     eax, [r14+0C8h]
0x1400759ca  test    al, 4
0x1400759cc  jnz     loc_140076192
0x1400759d2  mov     eax, [r14+0C8h]
0x1400759d9  mov     rdx, rbx
0x1400759dc  and     eax, 7000884h
0x1400759e1  mov     rcx, r14
  ... truncated ...
```
