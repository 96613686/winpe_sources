# PcFilterSendNetBufferLists

- ea: `0x140005c10`
- end: `0x14000724d`
- name: `PcFilterSendNetBufferLists`
- size: `5693`
- prototype: ``
- caller_count: `0`
- callee_count: `30`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140003770`
- `0x1400039a0`
- `0x140005578`
- `0x1400057b0`
- `0x140005b00`
- `0x140005c10`
- `0x140007260`
- `0x140007e10`
- `0x140008290`
- `0x140009100`
- `0x140009b80`
- `0x140009fe0`
- `0x14000a380`
- `0x14000a790`
- `0x14000a8c4`
- `0x14000adf8`
- `0x14000bcb4`
- `0x14000bdf4`
- `0x14000c380`
- `0x14000ca40`
- `0x14000cab0`
- `0x14000cce0`
- `0x1400110d8`
- `0x140011154`
- `0x140011500`
- `0x140011904`
- `0x140011a34`
- `0x14001233c`
- `0x140012410`
- `0x140013110`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x140005cac`
- `ntoskrnl!KfRaiseIrql` at `0x140005cac`
- `ntoskrnl!KeLowerIrql` at `0x1400060a2`
- `ntoskrnl!KeLowerIrql` at `0x1400060a2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400063e3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400063e3`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140005cbe`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140005cbe`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140005fec`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400061f1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000677b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400070a8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400071de`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140005fec`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400061f1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000677b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400070a8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400071de`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140005fca`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400061aa`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140005fca`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400061aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006124`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006124`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000626d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000626d`
- `NDIS!NdisGetDataBuffer` at `0x1400065a5`
- `NDIS!NdisGetDataBuffer` at `0x1400065a5`
- `NDIS!NdisFreeMemoryWithTag` at `0x1400060ea`
- `NDIS!NdisFreeMemoryWithTag` at `0x1400060ea`
- `NDIS!NdisFreeRWLock` at `0x140006110`
- `NDIS!NdisFreeRWLock` at `0x140006110`
- `NDIS!NdisFSendNetBufferListsComplete` at `0x14000665b`
- `NDIS!NdisFSendNetBufferListsComplete` at `0x140006b1e`
- `NDIS!NdisFSendNetBufferListsComplete` at `0x140006b72`
- `NDIS!NdisFSendNetBufferListsComplete` at `0x14000665b`
- `NDIS!NdisFSendNetBufferListsComplete` at `0x140006b1e`
- `NDIS!NdisFSendNetBufferListsComplete` at `0x140006b72`
- `NDIS!NdisFSendNetBufferLists` at `0x140005eb3`
- `NDIS!NdisFSendNetBufferLists` at `0x140006530`
- `NDIS!NdisFSendNetBufferLists` at `0x140006bb0`
- `NDIS!NdisFSendNetBufferLists` at `0x140005eb3`
- `NDIS!NdisFSendNetBufferLists` at `0x140006530`
- `NDIS!NdisFSendNetBufferLists` at `0x140006bb0`
- `NDIS!NdisAllocateNetBufferListContext` at `0x140006161`
- `NDIS!NdisAllocateNetBufferListContext` at `0x140006161`
- `NDIS!NdisReleaseRWLock` at `0x140006e06`
- `NDIS!NdisReleaseRWLock` at `0x140007027`
- `NDIS!NdisReleaseRWLock` at `0x140007192`
- `NDIS!NdisReleaseRWLock` at `0x140006e06`
- `NDIS!NdisReleaseRWLock` at `0x140007027`
- `NDIS!NdisReleaseRWLock` at `0x140007192`
- `NDIS!NdisAcquireRWLockWrite` at `0x140006ddf`
- `NDIS!NdisAcquireRWLockWrite` at `0x140007002`
- `NDIS!NdisAcquireRWLockWrite` at `0x140007170`
- `NDIS!NdisAcquireRWLockWrite` at `0x140006ddf`
- `NDIS!NdisAcquireRWLockWrite` at `0x140007002`
- `NDIS!NdisAcquireRWLockWrite` at `0x140007170`
- `NETIO!RtlCopyBufferToMdl` at `0x14000668e`
- `NETIO!RtlCopyBufferToMdl` at `0x14000668e`
- `HAL!KeQueryPerformanceCounter` at `0x140005cfd`
- `HAL!KeQueryPerformanceCounter` at `0x140005ef7`
- `HAL!KeQueryPerformanceCounter` at `0x1400067bd`
- `HAL!KeQueryPerformanceCounter` at `0x14000687c`
- `HAL!KeQueryPerformanceCounter` at `0x140006942`
- `HAL!KeQueryPerformanceCounter` at `0x140006a08`
- `HAL!KeQueryPerformanceCounter` at `0x140005cfd`
- `HAL!KeQueryPerformanceCounter` at `0x140005ef7`
- `HAL!KeQueryPerformanceCounter` at `0x1400067bd`
- `HAL!KeQueryPerformanceCounter` at `0x14000687c`
- `HAL!KeQueryPerformanceCounter` at `0x140006942`
- `HAL!KeQueryPerformanceCounter` at `0x140006a08`

## pseudocode

```c
void __fastcall PcFilterSendNetBufferLists(__int64 a1, struct _NET_BUFFER_LIST *a2, NDIS_PORT_NUMBER a3, ULONG a4)
{
  KIRQL v4; // al
  bool v5; // zf
  unsigned __int64 v8; // rsi
  __int64 v9; // rbx
  LARGE_INTEGER v10; // rax
  union _LARGE_INTEGER v11; // rcx
  LARGE_INTEGER v12; // r8
  __int64 v13; // rdx
  unsigned __int64 v14; // rdi
  unsigned __int8 v15; // al
  unsigned __int8 v16; // al
  PNET_BUFFER_LIST Alignment; // rbx
  unsigned __int64 v18; // r13
  __int64 v19; // r12
  char v20; // cl
  char *v21; // rax
  struct _NET_BUFFER_LIST *Next; // rsi
  volatile PKSPIN_LOCK Lock; // r12
  __int64 v24; // r8
  SLIST_HEADER *v25; // rax
  struct _NET_BUFFER_LIST *v26; // r13
  KSPIN_LOCK *v27; // rcx
  unsigned __int64 v28; // rdx
  ULONGLONG v29; // rax
  unsigned __int64 v30; // r14
  unsigned __int64 v31; // rsi
  __int64 v32; // rbx
  LARGE_INTEGER v33; // rax
  union _LARGE_INTEGER v34; // rcx
  LARGE_INTEGER v35; // r8
  __int64 v36; // rdx
  unsigned __int64 v37; // rdi
  unsigned __int8 v38; // al
  unsigned __int8 v39; // al
  char *v40; // rbx
  int v41; // eax
  __int64 **v42; // rcx
  __int64 *v43; // rsi
  unsigned __int64 v44; // rdi
  __int64 v45; // rbx
  __int64 v46; // rbx
  _QWORD *v47; // r13
  void *v48; // rcx
  __int64 v49; // rcx
  struct _NDIS_RW_LOCK_EX *v50; // rcx
  PVOID v51; // rdx
  char *v52; // rbx
  KSPIN_LOCK *v53; // rdx
  KSPIN_LOCK *v54; // rdx
  char *v55; // rbx
  union _LARGE_INTEGER v56; // r10
  __int64 v57; // rbx
  _DWORD *v58; // rbx
  unsigned __int64 v59; // rcx
  int v60; // eax
  union _LARGE_INTEGER v61; // r10
  __int64 v62; // rbx
  __int64 v63; // rdx
  void *v64; // r9
  PNET_BUFFER_LIST *QuadPart; // r10
  char *v66; // rbx
  _QWORD *v67; // rcx
  int v68; // ecx
  PNET_BUFFER v69; // rax
  unsigned int i; // edx
  int v71; // r8d
  PNET_BUFFER_LIST v72; // r13
  struct _NET_BUFFER_LIST *v73; // rbx
  PNET_BUFFER_LIST v74; // rax
  volatile signed __int32 *v75; // r9
  union _LARGE_INTEGER v76; // r11
  unsigned __int64 v77; // r10
  __int64 v78; // rbx
  SLIST_HEADER *v79; // rcx
  ULONGLONG Region; // rax
  int j; // edx
  signed int v82; // r8d
  __int64 v83; // r11
  SLIST_HEADER *v84; // rdx
  signed int v85; // ecx
  struct _NET_BUFFER_LIST *DataBuffer; // rax
  __int64 v87; // rax
  struct _NET_BUFFER_LIST *v88; // rcx
  PVOID v89; // rax
  struct _NET_BUFFER_LIST *k; // rax
  _QWORD *v91; // rdi
  struct _NET_BUFFER_LIST *v92; // rbx
  __int64 v93; // rcx
  _DWORD *v94; // r13
  __int64 v95; // rbx
  struct _NET_BUFFER_LIST *v96; // rcx
  LARGE_INTEGER v97; // rax
  union _LARGE_INTEGER v98; // rcx
  LARGE_INTEGER v99; // r9
  __int64 v100; // rdx
  unsigned __int64 v101; // r8
  unsigned __int8 v102; // al
  unsigned __int8 v103; // cl
  LARGE_INTEGER v104; // rax
  union _LARGE_INTEGER v105; // r8
  LARGE_INTEGER v106; // r9
  __int64 v107; // rdx
  unsigned __int64 v108; // rcx
  unsigned __int8 v109; // al
  unsigned __int8 v110; // al
  LARGE_INTEGER v111; // rax
  union _LARGE_INTEGER v112; // r8
  LARGE_INTEGER v113; // r9
  __int64 v114; // rdx
  unsigned __int64 v115; // rcx
  unsigned __int8 v116; // al
  unsigned __int8 v117; // al
  LARGE_INTEGER v118; // rax
  union _LARGE_INTEGER v119; // r8
  LARGE_INTEGER v120; // r9
  __int64 v121; // rdx
  unsigned __int64 v122; // rcx
  unsigned __int8 v123; // al
  unsigned __int8 v124; // al
  PVOID v125; // rcx
  PVOID v126; // rcx
  signed int v127; // ecx
  SLIST_HEADER *v128; // rax
  __int64 v129; // r8
  _QWORD *v130; // rax
  signed int v131; // ecx
  union _LARGE_INTEGER v132; // rax
  PNET_BUFFER_LIST *v133; // rcx
  __int64 v134; // rbx
  __int64 v135; // rdx
  PVOID v136; // rax
  __int64 v137; // rdx
  __int64 v138; // r9
  __int64 v139; // r9
  __int64 v140; // rcx
  int v141; // edx
  int v142; // r9d
  struct _NET_BUFFER_LIST *v143; // rdx
  __int64 v144; // r8
  PNDIS_RW_LOCK_EX *v145; // rbx
  __int64 *v146; // r15
  struct _NET_BUFFER_LIST *v147; // rdi
  int v148; // eax
  struct _NET_BUFFER_LIST *v149; // r14
  __int64 v150; // rax
  PNDIS_RW_LOCK_EX *v151; // rdi
  __int64 v152; // rdx
  char v153; // [rsp+58h] [rbp-B0h]
  char v154; // [rsp+59h] [rbp-AFh]
  KIRQL v155; // [rsp+5Ah] [rbp-AEh]
  ULONG CurrentProcessorNumber; // [rsp+5Ch] [rbp-ACh]
  union _LARGE_INTEGER v157; // [rsp+60h] [rbp-A8h] BYREF
  PVOID FirstNetBuffer; // [rsp+68h] [rbp-A0h] BYREF
  KSPIN_LOCK *v159; // [rsp+70h] [rbp-98h] BYREF
  struct _NET_BUFFER_LIST *v160; // [rsp+78h] [rbp-90h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+80h] [rbp-88h] BYREF
  struct _LOCK_STATE_EX v162; // [rsp+84h] [rbp-84h] BYREF
  NDIS_PORT_NUMBER PortNumber; // [rsp+88h] [rbp-80h] BYREF
  PVOID P; // [rsp+90h] [rbp-78h]
  _DWORD *v165; // [rsp+98h] [rbp-70h]
  union _LARGE_INTEGER v166; // [rsp+A0h] [rbp-68h] BYREF
  unsigned __int64 v167; // [rsp+A8h] [rbp-60h]
  PNET_BUFFER_LIST v168; // [rsp+B0h] [rbp-58h]
  PNET_BUFFER_LIST *v169; // [rsp+B8h] [rbp-50h]
  unsigned __int64 v170; // [rsp+C0h] [rbp-48h]
  unsigned __int64 v171; // [rsp+C8h] [rbp-40h]
  PNET_BUFFER_LIST v172; // [rsp+D0h] [rbp-38h] BYREF
  PNET_BUFFER_LIST v173; // [rsp+D8h] [rbp-30h] BYREF
  struct _KLOCK_QUEUE_HANDLE NetBufferList; // [rsp+E0h] [rbp-28h] BYREF
  void *v175; // [rsp+F8h] [rbp-10h] BYREF
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+100h] [rbp-8h] BYREF
  PVOID v177; // [rsp+108h] [rbp+0h] BYREF
  KSPIN_LOCK *v178; // [rsp+110h] [rbp+8h]
  __int64 v179; // [rsp+118h] [rbp+10h]
  union _LARGE_INTEGER v180; // [rsp+120h] [rbp+18h] BYREF
  union _LARGE_INTEGER v181; // [rsp+128h] [rbp+20h] BYREF
  struct _KLOCK_QUEUE_HANDLE v182; // [rsp+130h] [rbp+28h] BYREF
  __int64 v183; // [rsp+148h] [rbp+40h]
  __int64 v184; // [rsp+150h] [rbp+48h]
  __int64 v185; // [rsp+158h] [rbp+50h]
  unsigned __int64 v186; // [rsp+160h] [rbp+58h]
  __int64 v187; // [rsp+168h] [rbp+60h] BYREF
  _OWORD v188[2]; // [rsp+170h] [rbp+68h] BYREF
  int v189; // [rsp+190h] [rbp+88h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+198h] [rbp+90h] BYREF
  struct _KLOCK_QUEUE_HANDLE v191; // [rsp+1B0h] [rbp+A8h] BYREF
  struct _KLOCK_QUEUE_HANDLE v192; // [rsp+1C8h] [rbp+C0h] BYREF
  __int64 Storage; // [rsp+1E0h] [rbp+D8h] BYREF
  int v194; // [rsp+1E8h] [rbp+E0h]
  __int16 v195; // [rsp+1ECh] [rbp+E4h]
  __int128 v196; // [rsp+1F8h] [rbp+F0h] BYREF
  __int128 v197; // [rsp+208h] [rbp+100h]
  __int128 v198; // [rsp+218h] [rbp+110h]
  __int128 v199; // [rsp+228h] [rbp+120h]
  __int128 v200; // [rsp+238h] [rbp+130h]

  PortNumber = a3;
  v4 = 0;
  v168 = a2;
  v5 = *(_DWORD *)(a1 + 24) == 2;
  v177 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v196 = 0;
  v197 = 0;
  v198 = 0;
  v199 = 0;
  v200 = 0;
  if ( v5 )
  {
    if ( (a4 & 1) != 0 )
    {
      v154 = 1;
    }
    else
    {
      v154 = 0;
      v4 = KfRaiseIrql(2u);
    }
    v155 = v4;
    CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
    v8 = ((unsigned __int64)CurrentProcessorNumber << 7) + *(_QWORD *)QosgTimerTable;
    v171 = (unsigned __int64)CurrentProcessorNumber << 7;
    v9 = MEMORY[0xFFFFF78000000008];
    PerformanceFrequency.QuadPart = 0;
    v10 = KeQueryPerformanceCounter(&PerformanceFrequency);
    v11 = PerformanceFrequency;
    v12 = v10;
    v13 = *(unsigned __int8 *)(v8 + 112);
    v14 = ((1000000 * HIDWORD(v10.QuadPart) / (unsigned __int64)PerformanceFrequency.QuadPart) << 32)
        + (1000000LL * v10.LowPart
         + ((1000000 * HIDWORD(v10.QuadPart) % (unsigned __int64)PerformanceFrequency.QuadPart) << 32))
        / PerformanceFrequency.QuadPart;
    v170 = v14;
    if ( (_BYTE)v13 )
      v15 = v13 - 1;
    else
      v15 = 2;
    if ( (__int64)(*(_QWORD *)(v8 + 8LL * v15 + 64) - v14) > 0 )
    {
      *(_QWORD *)(v8 + 8 * v13 + 16) = *(_QWORD *)(v8 + 8LL * v15 + 16);
      *(_QWORD *)(v8 + 8 * v13 + 40) = *(_QWORD *)(v8 + 8LL * v15 + 40);
      *(_QWORD *)(v8 + 8 * v13 + 64) = *(_QWORD *)(v8 + 8LL * v15 + 64);
      v14 = *(_QWORD *)(v8 + 8LL * v15 + 64);
      v170 = v14;
    }
    else
    {
      *(LARGE_INTEGER *)(v8 + 8 * v13 + 16) = v12;
      *(union _LARGE_INTEGER *)(v8 + 8 * v13 + 40) = v11;
      *(_QWORD *)(v8 + 8 * v13 + 64) = v14;
    }
    *(_QWORD *)(v8 + 8 * v13 + 88) = v9;
    v16 = *(_BYTE *)(v8 + 112) + 1;
    *(_QWORD *)(v8 + 8) = v9;
    Alignment = v168;
    NetBufferList.LockQueue = 0;
    *(_QWORD *)v8 = v14;
    v18 = (unsigned __int64)CurrentProcessorNumber << 6;
    v19 = 192LL * CurrentProcessorNumber;
    v186 = v18;
    v185 = v19;
    v20 = v16 % 3u;
    v21 = (char *)PcgDelayQueue;
    *(_BYTE *)(v8 + 112) = v20;
    Next = (struct _NET_BUFFER_LIST *)NetBufferList.LockQueue.Next;
    v178 = 0;
    ++*(_DWORD *)&v21[v18 + 16];
    ++*(_DWORD *)((char *)PcgTimerUnits + v19 + 40);
    *(_QWORD *)&NetBufferList.OldIrql = 0;
    if ( Alignment )
    {
      Lock = NetBufferList.LockQueue.Lock;
      v24 = 0x7FFFFFFFFFFFFFFFLL;
      while ( 1 )
      {
        v25 = (SLIST_HEADER *)Alignment;
        v26 = Alignment;
        Alignment = (PNET_BUFFER_LIST)Alignment->Link.Alignment;
        v168 = Alignment;
        v25->Alignment = 0;
        v5 = *(_BYTE *)(a1 + 211) == 1;
        v27 = (KSPIN_LOCK *)v26->NetBufferListInfo[3];
        v159 = v27;
        if ( v5 && !v27 )
        {
          v93 = *(_QWORD *)&WPP_MAIN_CB.DeviceLock.Header.Lock;
          if ( !*(_QWORD *)&WPP_MAIN_CB.DeviceLock.Header.Lock )
          {
            v198 = 0;
            v199 = 0;
            v200 = 0;
            *(_QWORD *)&v196 = -1;
            *((_QWORD *)&v196 + 1) = -1;
            *(_QWORD *)&v197 = 0x1FFFFFFFFLL;
            *((_QWORD *)&v197 + 1) = -1;
            PcpCreateFlow(&v177, 0, 0, 0, 0x50u, 0, &v196, 1, 0);
            if ( _InterlockedCompareExchange64(
                   (volatile signed __int64 *)&WPP_MAIN_CB.DeviceLock.Header.Lock,
                   (signed __int64)v177,
                   0)
              && v177 )
            {
              PcpDeleteFlow((char *)v177, v135);
            }
            v93 = *(_QWORD *)&WPP_MAIN_CB.DeviceLock.Header.Lock;
            if ( !*(_QWORD *)&WPP_MAIN_CB.DeviceLock.Header.Lock )
              goto LABEL_146;
          }
          if ( PcpReferenceFlow(v93) != 1 )
            goto LABEL_146;
          v27 = *(KSPIN_LOCK **)&WPP_MAIN_CB.DeviceLock.Header.Lock;
          v159 = *(KSPIN_LOCK **)&WPP_MAIN_CB.DeviceLock.Header.Lock;
          v26->NetBufferListInfo[3] = *(PVOID *)&WPP_MAIN_CB.DeviceLock.Header.Lock;
          if ( v27 )
          {
            if ( Microsoft_Windows_Networking_CorrelationEnabled
              && PcgEventTraceEnabled
              && (v24 & (__int64)v26->NetBufferListInfo[13]) != 0 )
            {
              break;
            }
          }
        }
LABEL_11:
        v5 = *(_DWORD *)(a1 + 16) == 3;
        v28 = *(_QWORD *)(a1 + 160);
        P = (PVOID)v28;
        v153 = 0;
        if ( v5 && *(_WORD *)(a1 + 212) == 2048 )
        {
          Storage = 0;
          v194 = 0;
          v195 = 0;
          v187 = 0;
          FirstNetBuffer = v26->FirstNetBuffer;
          DataBuffer = (struct _NET_BUFFER_LIST *)NdisGetDataBuffer((PNET_BUFFER)FirstNetBuffer, 0xEu, &Storage, 2u, 0);
          v160 = DataBuffer;
          if ( !DataBuffer )
            goto LABEL_151;
          v87 = PcpLineLookupById(LOWORD(DataBuffer->Next));
          P = (PVOID)v87;
          v28 = v87;
          if ( !v87 )
            goto LABEL_151;
          if ( *(_DWORD *)(v87 + 244) != 2 )
          {
            PcpLineDereference((PVOID)v87);
LABEL_151:
            v126 = v26->NetBufferListInfo[3];
            if ( v126 && v126 == *(PVOID *)&WPP_MAIN_CB.DeviceLock.Header.Lock )
            {
              PcpDereferenceFlow(v126);
              v26->NetBufferListInfo[3] = 0;
            }
            v26->Status = -1073741823;
            NdisFSendNetBufferListsComplete(*(NDIS_HANDLE *)(a1 + 40), v26, a4);
            goto LABEL_18;
          }
          v88 = v160;
          LODWORD(v160->Next) = *(_DWORD *)(v87 + 328);
          *((_WORD *)&v88->NetBufferListHeader.Link.HeaderX64 + 2) = *(_WORD *)(v87 + 332);
          *((_WORD *)&v88->NetBufferListHeader.Link.HeaderX64 + 3) = *(_WORD *)(v87 + 240);
          v89 = FirstNetBuffer;
          if ( v88 != (struct _NET_BUFFER_LIST *)&Storage )
          {
            v89 = *(PVOID *)FirstNetBuffer;
            FirstNetBuffer = *(PVOID *)FirstNetBuffer;
          }
          if ( v89 )
          {
            v91 = FirstNetBuffer;
            v92 = v88;
            do
            {
              RtlCopyBufferToMdl(v92, v91[1], *((unsigned int *)v91 + 4), 12, &v187);
              v91 = (_QWORD *)*v91;
            }
            while ( v91 );
            v14 = v170;
            Alignment = v168;
          }
          v153 = 1;
          if ( !v159 )
          {
LABEL_13:
            if ( Lock )
            {
              v29 = *Lock;
              *Lock = (KSPIN_LOCK)v26;
            }
            else
            {
              v29 = (ULONGLONG)Next;
              Next = v26;
            }
            v26->Link.Alignment = v29;
            if ( !v29 )
              Lock = (volatile PKSPIN_LOCK)v26;
            goto LABEL_17;
          }
          if ( NdisAllocateNetBufferListContext(v26, 8u, 0, 0x63776350u) )
          {
            v125 = v26->NetBufferListInfo[3];
            if ( v125 && v125 == *(PVOID *)&WPP_MAIN_CB.DeviceLock.Header.Lock )
            {
              PcpDereferenceFlow(v125);
              v26->NetBufferListInfo[3] = 0;
            }
            v26->Status = -1073741823;
            NdisFSendNetBufferListsComplete(*(NDIS_HANDLE *)(a1 + 40), v26, a4);
            PcpLineDereference(P);
            goto LABEL_18;
          }
          v51 = P;
          _InterlockedIncrement((volatile signed __int32 *)P + 62);
          *(_QWORD *)&v26->Context->ContextData[v26->Context->Offset] = v51;
          v27 = v159;
        }
        else if ( !v27 )
        {
          goto LABEL_13;
        }
        if ( v27 != v178 )
        {
          v52 = (char *)(v27 + 12);
          v178 = v27;
          KeAcquireInStackQueuedSpinLockAtDpcLevel(v27 + 12, &LockHandle);
          while ( *((_DWORD *)v52 + 2) )
            ;
          if ( *((_DWORD *)v159 + 21) != CurrentProcessorNumber )
          {
            v53 = (KSPIN_LOCK *)v159[29];
            if ( v53 != v159 + 29 && (__int64)(v53[3] - v14) <= 0 )
              PcpFlowDelay(v159, CurrentProcessorNumber);
          }
          KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
        }
        v54 = (KSPIN_LOCK *)v26->NetBufferListInfo[3];
        *(_WORD *)&LockState.OldIrql = 0;
        LockState.Flags = 0;
        v55 = (char *)(v54 + 12);
        v172 = 0;
        v173 = 0;
        memset(&v192, 0, sizeof(v192));
        v165 = v54;
        memset(&v191, 0, sizeof(v191));
        v160 = (struct _NET_BUFFER_LIST *)((char *)PcgTimerUnits + 192 * *((unsigned int *)v54 + 21));
        KeAcquireInStackQueuedSpinLock(v54 + 12, &v192);
        while ( *((_DWORD *)v55 + 2) )
          ;
        v56.QuadPart = *(_QWORD *)QosgTimerTable + v171;
        v57 = MEMORY[0xFFFFF78000000008];
        v157 = v56;
        if ( MEMORY[0xFFFFF78000000008] != *(_QWORD *)(v56.QuadPart + 8) )
        {
          v180.QuadPart = 0;
          v104 = KeQueryPerformanceCounter(&v180);
          v105 = v180;
          v106 = v104;
          v56 = v157;
          v107 = *(unsigned __int8 *)(v157.QuadPart + 112);
          v108 = ((1000000 * HIDWORD(v104.QuadPart) / (unsigned __int64)v180.QuadPart) << 32)
               + (1000000LL * v104.LowPart + ((1000000 * HIDWORD(v104.QuadPart) % (unsigned __int64)v180.QuadPart) << 32))
               / v180.QuadPart;
          if ( (_BYTE)v107 )
            v109 = v107 - 1;
          else
            v109 = 2;
          if ( (__int64)(*(_QWORD *)(v157.QuadPart + 8LL * v109 + 64) - v108) > 0 )
          {
            *(_QWORD *)(v157.QuadPart + 8 * v107 + 16) = *(_QWORD *)(v157.QuadPart + 8LL * v109 + 16);
            *(_QWORD *)(v56.QuadPart + 8 * v107 + 40) = *(_QWORD *)(v56.QuadPart + 8LL * v109 + 40);
            *(_QWORD *)(v56.QuadPart + 8 * v107 + 64) = *(_QWORD *)(v56.QuadPart + 8LL * v109 + 64);
            v108 = *(_QWORD *)(v56.QuadPart + 8LL * v109 + 64);
          }
          else
          {
            *(LARGE_INTEGER *)(v157.QuadPart + 8 * v107 + 16) = v106;
            *(union _LARGE_INTEGER *)(v56.QuadPart + 8 * v107 + 40) = v105;
            *(_QWORD *)(v56.QuadPart + 8 * v107 + 64) = v108;
          }
          *(_QWORD *)(v56.QuadPart + 8 * v107 + 88) = v57;
          v110 = *(_BYTE *)(v56.QuadPart + 112) + 1;
          *(_QWORD *)v56.QuadPart = v108;
          *(_QWORD *)(v56.QuadPart + 8) = v57;
          *(_BYTE *)(v56.QuadPart + 112) = v110 % 3u;
        }
        v58 = v165;
        v59 = *(_QWORD *)v56.QuadPart;
        v183 = 0x7FFFFFFFFFFFFFFFLL;
        v167 = v59;
        v60 = v165[114];
        v184 = 0;
        LODWORD(v182.LockQueue.Next) = v60;
        memset((char *)&v182.LockQueue.Next + 4, 0, 20);
        if ( v60 && (unsigned __int8)QosTbcAdjustBytesSent(v165 + 34, v59) )
        {
          if ( *((_QWORD *)v58 + 11) == *((_QWORD *)P + 37) )
            v136 = P;
          else
            v136 = (PVOID)PcpLineFindByLuid(*((_QWORD *)v58 + 11));
          FirstNetBuffer = v136;
          if ( v136 )
          {
            PcpLineSignalExternalEvent(v136, CurrentProcessorNumber);
            NdisAcquireRWLockWrite(*((PNDIS_RW_LOCK_EX *)FirstNetBuffer + 2), &LockState, 0);
            QosLineQueryQueueFeedback((char *)FirstNetBuffer + 24, v137, &v182);
            NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v138 + 16), &LockState);
            if ( FirstNetBuffer != P )
              PcpLineDereference(FirstNetBuffer);
          }
          QosTbcAdjustSendWindow(v58 + 34, &v182);
        }
        LODWORD(v159) = 0;
        v61.QuadPart = *(_QWORD *)QosgTimerTable + v171;
        v157 = v61;
        v62 = MEMORY[0xFFFFF78000000008];
        if ( MEMORY[0xFFFFF78000000008] != *(_QWORD *)(v61.QuadPart + 8) )
        {
          v181.QuadPart = 0;
          v111 = KeQueryPerformanceCounter(&v181);
          v112 = v181;
          v113 = v111;
          v61 = v157;
          v114 = *(unsigned __int8 *)(v157.QuadPart + 112);
          v115 = ((1000000 * HIDWORD(v111.QuadPart) / (unsigned __int64)v181.QuadPart) << 32)
               + (1000000LL * v111.LowPart + ((1000000 * HIDWORD(v111.QuadPart) % (unsigned __int64)v181.QuadPart) << 32))
               / v181.QuadPart;
          if ( (_BYTE)v114 )
            v116 = v114 - 1;
          else
            v116 = 2;
          if ( (__int64)(*(_QWORD *)(v157.QuadPart + 8LL * v116 + 64) - v115) > 0 )
          {
            *(_QWORD *)(v157.QuadPart + 8 * v114 + 16) = *(_QWORD *)(v157.QuadPart + 8LL * v116 + 16);
            *(_QWORD *)(v61.QuadPart + 8 * v114 + 40) = *(_QWORD *)(v61.QuadPart + 8LL * v116 + 40);
            *(_QWORD *)(v61.QuadPart + 8 * v114 + 64) = *(_QWORD *)(v61.QuadPart + 8LL * v116 + 64);
            v115 = *(_QWORD *)(v61.QuadPart + 8LL * v116 + 64);
          }
          else
          {
            *(LARGE_INTEGER *)(v157.QuadPart + 8 * v114 + 16) = v113;
            *(union _LARGE_INTEGER *)(v61.QuadPart + 8 * v114 + 40) = v112;
            *(_QWORD *)(v61.QuadPart + 8 * v114 + 64) = v115;
          }
          *(_QWORD *)(v61.QuadPart + 8 * v114 + 88) = v62;
          v117 = *(_BYTE *)(v61.QuadPart + 112) + 1;
          *(_QWORD *)v61.QuadPart = v115;
          *(_QWORD *)(v61.QuadPart + 8) = v62;
          *(_BYTE *)(v61.QuadPart + 112) = v117 % 3u;
        }
        v63 = *(_QWORD *)v61.QuadPart;
        v64 = &v172;
        QuadPart = &v173;
        v66 = (char *)(v165 + 34);
        v179 = v63;
        v67 = (_QWORD *)*((_QWORD *)v165 + 29);
        FirstNetBuffer = &v172;
        v175 = 0;
        v169 = &v173;
        v157.QuadPart = 0;
        if ( v67 == (_QWORD *)(v165 + 58) )
        {
          if ( **(_DWORD **)QosgEtwDispatchTable == 1 )
          {
            v139 = v63 - *((_QWORD *)v165 + 50);
            if ( v139 > 0 )
            {
              QosTraceFlowSendQueue((_DWORD)v165 + 136, 0, v63, v139, 0, 0, 0);
              QuadPart = v169;
            }
            v64 = FirstNetBuffer;
          }
        }
        else if ( v67[3] - v63 <= 0 )
        {
          QosTbcProcessQueuedNetBufferLists(
            (_DWORD)v165 + 136,
            CurrentProcessorNumber,
            (unsigned int)&v172,
            (unsigned int)&v175,
            (__int64)&v159,
            (__int64)&v173,
            (__int64)&v157);
          v64 = FirstNetBuffer;
          QuadPart = v169;
          if ( v175 )
            v64 = v175;
          if ( v157.QuadPart )
            QuadPart = (PNET_BUFFER_LIST *)v157.QuadPart;
        }
        ++*((_DWORD *)v66 + 8);
        v68 = 0;
        v69 = v26->FirstNetBuffer;
        for ( i = 0; v69; v69 = (PNET_BUFFER)v69->Link.Alignment )
        {
          i += v69->DataLength;
          ++v68;
        }
        *((_DWORD *)v66 + 2) += v68;
        v71 = (_DWORD)P + 24;
        *((_QWORD *)v66 + 2) += i;
        if ( (unsigned __int8)QosTbcSendNetBufferList(
                                (_DWORD)v66,
                                CurrentProcessorNumber,
                                v71,
                                (_DWORD)v26,
                                v68,
                                i,
                                a4,
                                (__int64)v64,
                                (__int64)QuadPart) )
        {
          v94 = v165;
          v95 = *(_QWORD *)(*((_QWORD *)v165 + 29) + 24LL);
          RtlAcquireWriteLockAtDpcLevel(v160, &v191);
          PcpSetTimer(v160, v167, v95);
          PcpSetFlowTimer(v160, v94, v95);
          KeReleaseInStackQueuedSpinLockFromDpcLevel(&v191);
        }
        else
        {
          *((_QWORD *)v66 + 33) = v179;
        }
        KeReleaseInStackQueuedSpinLock(&v192);
        v72 = v172;
        if ( v172 )
        {
          v73 = (struct _NET_BUFFER_LIST *)v172->Link.Alignment;
          v74 = v172;
          v75 = (volatile signed __int32 *)v172->MiniportReserved[0];
          v165 = v75;
          if ( v73 )
          {
            do
            {
              v96 = v73;
              if ( v73->MiniportReserved[0] != v75 )
              {
                v74->Link.Alignment = 0;
                PcpLineSendNetBufferLists(v75 - 6, CurrentProcessorNumber, v72);
                v75 = (volatile signed __int32 *)v73->MiniportReserved[0];
                v96 = v73;
                v72 = v73;
              }
              v73 = (struct _NET_BUFFER_LIST *)v73->Link.Alignment;
              v74 = v96;
            }
            while ( v73 );
            v14 = v170;
            v165 = v75;
          }
          v76.QuadPart = (LONGLONG)(v75 - 6);
          v160 = 0;
          v157.QuadPart = (LONGLONG)(v75 - 6);
          FirstNetBuffer = 0;
          if ( v75 == (volatile signed __int32 *)24 )
          {
            v28 = (unsigned __int64)v72;
            v134 = *(_QWORD *)&v72->Context->ContextData[v72->Context->Offset + 32] - 24LL;
            do
            {
              v132 = *(union _LARGE_INTEGER *)v28;
              v157 = v132;
              if ( v132.QuadPart )
              {
                v140 = *(_QWORD *)(*(unsigned __int16 *)(*(_QWORD *)(v132.QuadPart + 16) + 10LL)
                                 + *(_QWORD *)(v132.QuadPart + 16)
                                 + 48LL);
                v132 = v157;
                v133 = (PNET_BUFFER_LIST *)(v140 - 24);
              }
              else
              {
                v133 = 0;
              }
              v169 = v133;
              if ( (PNET_BUFFER_LIST *)v134 != v133 )
              {
                *(_QWORD *)v28 = 0;
                PcpLineSignalExternalEvent(v134, CurrentProcessorNumber);
                QosLineSendNetBufferLists(v134 + 24, v141, (_DWORD)v72, v142, (__int64)&v160, (__int64)&FirstNetBuffer);
                v143 = v160;
                if ( v160 )
                {
                  v144 = *(_QWORD *)(v134 + 256);
                  v128 = (SLIST_HEADER *)v160;
                  v127 = 0;
                  do
                  {
                    if ( v128[7].Region == *(_QWORD *)(v144 + 40) )
                      ++v127;
                    v128 = (SLIST_HEADER *)v128->Alignment;
                  }
                  while ( v128 );
                  if ( v127 > 0 )
                    _InterlockedAdd((volatile signed __int32 *)(v144 + 128), v127);
                  NdisFSendNetBufferLists(*(NDIS_HANDLE *)(*(_QWORD *)(v134 + 256) + 40LL), v143, 0, 0);
                  v160 = 0;
                }
                if ( FirstNetBuffer )
                {
                  v129 = *(_QWORD *)(v134 + 256);
                  v130 = FirstNetBuffer;
                  v131 = 0;
                  do
                  {
                    if ( v130[15] == *(_QWORD *)(v129 + 40) )
                      ++v131;
                    v130 = (_QWORD *)*v130;
                  }
                  while ( v130 );
                  if ( v131 > 0 )
                    _InterlockedAdd((volatile signed __int32 *)(v129 + 128), v131);
                  PcpLineDropNblChain(v134);
                  FirstNetBuffer = 0;
                }
                v132 = v157;
                v133 = v169;
                LODWORD(v72) = v157.LowPart;
              }
              v134 = (__int64)v133;
              v28 = v132.QuadPart;
            }
            while ( v132.QuadPart );
            v14 = v170;
          }
          else
          {
            *(_WORD *)&v162.OldIrql = 0;
            v162.Flags = 0;
            v77 = *(_QWORD *)QosgTimerTable + v171;
            v167 = v77;
            v78 = MEMORY[0xFFFFF78000000008];
            if ( MEMORY[0xFFFFF78000000008] != *(_QWORD *)(v77 + 8) )
            {
              v166.QuadPart = 0;
              v118 = KeQueryPerformanceCounter(&v166);
              v119 = v166;
              v120 = v118;
              v77 = v167;
              v121 = *(unsigned __int8 *)(v167 + 112);
              v122 = ((1000000 * HIDWORD(v118.QuadPart) / (unsigned __int64)v166.QuadPart) << 32)
                   + (1000000LL * v118.LowPart
                    + ((1000000 * HIDWORD(v118.QuadPart) % (unsigned __int64)v166.QuadPart) << 32))
                   / v166.QuadPart;
              if ( (_BYTE)v121 )
                v123 = v121 - 1;
              else
                v123 = 2;
              if ( (__int64)(*(_QWORD *)(v167 + 8LL * v123 + 64) - v122) > 0 )
              {
                *(_QWORD *)(v167 + 8 * v121 + 16) = *(_QWORD *)(v167 + 8LL * v123 + 16);
                *(_QWORD *)(v77 + 8 * v121 + 40) = *(_QWORD *)(v77 + 8LL * v123 + 40);
                *(_QWORD *)(v77 + 8 * v121 + 64) = *(_QWORD *)(v77 + 8LL * v123 + 64);
                v122 = *(_QWORD *)(v77 + 8LL * v123 + 64);
              }
              else
              {
                *(LARGE_INTEGER *)(v167 + 8 * v121 + 16) = v120;
                *(union _LARGE_INTEGER *)(v77 + 8 * v121 + 40) = v119;
                *(_QWORD *)(v77 + 8 * v121 + 64) = v122;
              }
              v75 = v165;
              v76 = v157;
              *(_QWORD *)(v77 + 8 * v121 + 88) = v78;
              v124 = *(_BYTE *)(v77 + 112) + 1;
              *(_QWORD *)v77 = v122;
              *(_QWORD *)(v77 + 8) = v78;
              v28 = v124 / 3u;
              *(_BYTE *)(v77 + 112) = v124 % 3u;
            }
            if ( ((__int64)(*((_QWORD *)v75 + 21) - *(_QWORD *)v77) <= 0
               || (__int64)(*((_QWORD *)v75 + 20) - *(_QWORD *)v77) <= 0)
              && !_InterlockedExchangeAdd(v75 + 32, 1u) )
            {
              NdisAcquireRWLockWrite(*((PNDIS_RW_LOCK_EX *)v75 - 1), &v162, 0);
              v145 = (PNDIS_RW_LOCK_EX *)v165;
              QosLineSignalExternalEvent(v165, CurrentProcessorNumber);
              NdisReleaseRWLock(*(v145 - 1), &v162);
              v76 = v157;
              v75 = (volatile signed __int32 *)v145;
            }
            v24 = 0;
            v79 = (SLIST_HEADER *)v72;
            if ( v72 )
            {
              do
              {
                Region = v79->Region;
                for ( j = 0; Region; Region = *(_QWORD *)Region )
                  j += *(_DWORD *)(Region + 24);
                v79 = (SLIST_HEADER *)v79->Alignment;
                LODWORD(v24) = j + v24;
              }
              while ( v79 );
              _InterlockedAdd((volatile signed __int32 *)(v76.QuadPart + 156), v24);
              v82 = 0;
              v83 = *((_QWORD *)v75 + 29);
              v84 = (SLIST_HEADER *)v72;
              do
              {
                v5 = v84[7].Region == *(_QWORD *)(v83 + 40);
                v85 = v82 + 1;
                v84 = (SLIST_HEADER *)v84->Alignment;
                if ( !v5 )
                  v85 = v82;
                v82 = v85;
              }
              while ( v84 );
              if ( v85 > 0 )
                _InterlockedAdd((volatile signed __int32 *)(v83 + 128), v85);
              NdisFSendNetBufferLists(*(NDIS_HANDLE *)(*((_QWORD *)v75 + 29) + 40LL), v72, 0, 0);
            }
            else
            {
              _InterlockedAdd(v75 + 33, 0);
            }
          }
        }
        if ( v173 )
          PcpSchedulerBatchAndSendOrDropNblChain(v173);
        Alignment = v168;
LABEL_17:
        if ( v153 )
        {
          v47 = P;
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)P + 62, 0xFFFFFFFF) == 1 )
          {
            v48 = (void *)v47[40];
            if ( v48 )
              NdisFreeMemoryWithTag(v48, 0x616E6350u);
            v49 = v47[32];
            if ( v49 )
              PcpFilterDecrementDetachCount(v49, v28, v24);
            v50 = (struct _NDIS_RW_LOCK_EX *)v47[2];
            if ( v50 )
              NdisFreeRWLock(v50);
            ExFreePoolWithTag(v47, 0x656C6350u);
          }
        }
LABEL_18:
        v24 = 0x7FFFFFFFFFFFFFFFLL;
        if ( !Alignment )
        {
          v19 = v185;
          v18 = v186;
          goto LABEL_20;
        }
      }
      PcpEtwTransferFlowActivity(v24 & (__int64)v26->NetBufferListInfo[13], v27, 2);
LABEL_146:
      v27 = v159;
      goto LABEL_11;
    }
LABEL_20:
    if ( Next )
      NdisFSendNetBufferLists(*(NDIS_HANDLE *)(a1 + 40), Next, PortNumber, a4);
    v30 = v171;
    memset(&NetBufferList, 0, sizeof(NetBufferList));
    v31 = v171 + *(_QWORD *)QosgTimerTable;
    v32 = MEMORY[0xFFFFF78000000008];
    v157.QuadPart = 0;
    v33 = KeQueryPerformanceCounter(&v157);
    v34 = v157;
    v35 = v33;
    v36 = *(unsigned __int8 *)(v31 + 112);
    v37 = ((1000000 * HIDWORD(v33.QuadPart) / (unsigned __int64)v157.QuadPart) << 32)
        + (1000000LL * v33.LowPart + ((1000000 * HIDWORD(v33.QuadPart) % (unsigned __int64)v157.QuadPart) << 32))
        / v157.QuadPart;
    if ( (_BYTE)v36 )
      v38 = v36 - 1;
    else
      v38 = 2;
    if ( (__int64)(*(_QWORD *)(v31 + 8LL * v38 + 64) - v37) > 0 )
    {
      *(_QWORD *)(v31 + 8 * v36 + 16) = *(_QWORD *)(v31 + 8LL * v38 + 16);
      *(_QWORD *)(v31 + 8 * v36 + 40) = *(_QWORD *)(v31 + 8LL * v38 + 40);
      *(_QWORD *)(v31 + 8 * v36 + 64) = *(_QWORD *)(v31 + 8LL * v38 + 64);
      v37 = *(_QWORD *)(v31 + 8LL * v38 + 64);
    }
    else
    {
      *(LARGE_INTEGER *)(v31 + 8 * v36 + 16) = v35;
      *(union _LARGE_INTEGER *)(v31 + 8 * v36 + 40) = v34;
      *(_QWORD *)(v31 + 8 * v36 + 64) = v37;
    }
    *(_QWORD *)(v31 + 8 * v36 + 88) = v32;
    v39 = *(_BYTE *)(v31 + 112) + 1;
    *(_QWORD *)(v31 + 8) = v32;
    *(_QWORD *)v31 = v37;
    *(_BYTE *)(v31 + 112) = v39 % 3u;
    v40 = (char *)PcgTimerUnits + v19;
    if ( PcgDisableRecursionFix )
    {
      --*((_DWORD *)v40 + 10);
      v41 = 0;
    }
    else
    {
      v41 = 1;
    }
    if ( *((_DWORD *)v40 + 10) == v41 )
    {
      KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)v40, &NetBufferList);
      while ( *((_DWORD *)v40 + 2) )
        ;
      if ( (*((_DWORD *)v40 + 11) & 1) != 0 || (__int64)(*((_QWORD *)v40 + 3) - v37) > 0 )
      {
        KeReleaseInStackQueuedSpinLockFromDpcLevel(&NetBufferList);
      }
      else
      {
        KeReleaseInStackQueuedSpinLockFromDpcLevel(&NetBufferList);
        *((_DWORD *)v40 + 11) |= 2u;
        PcpTimeoutHandler(0, v40, 0, 0);
        *((_DWORD *)v40 + 11) &= ~2u;
      }
    }
    if ( !PcgDisableRecursionFix )
      --*((_DWORD *)v40 + 10);
    v42 = (__int64 **)((char *)PcgDelayQueue + v18);
    v5 = (*(_DWORD *)((char *)PcgDelayQueue + v18 + 16))-- == 1;
    if ( v5 )
    {
      v43 = *v42;
      LOWORD(v159) = 0;
      BYTE2(v159) = 0;
      memset(&v182, 0, sizeof(v182));
      *v42 = 0;
      v42[1] = 0;
      v189 = 0;
      memset(v188, 0, sizeof(v188));
      v44 = v30 + *(_QWORD *)QosgTimerTable;
      v45 = MEMORY[0xFFFFF78000000008];
      if ( MEMORY[0xFFFFF78000000008] != *(_QWORD *)(v44 + 8) )
      {
        v166.QuadPart = 0;
        v97 = KeQueryPerformanceCounter(&v166);
        v98 = v166;
        v99 = v97;
        v100 = *(unsigned __int8 *)(v44 + 112);
        v101 = ((1000000 * HIDWORD(v97.QuadPart) / (unsigned __int64)v166.QuadPart) << 32)
             + (1000000LL * v97.LowPart + ((1000000 * HIDWORD(v97.QuadPart) % (unsigned __int64)v166.QuadPart) << 32))
             / v166.QuadPart;
        if ( (_BYTE)v100 )
          v102 = v100 - 1;
        else
          v102 = 2;
        if ( (__int64)(*(_QWORD *)(v44 + 8LL * v102 + 64) - v101) > 0 )
        {
          *(_QWORD *)(v44 + 8 * v100 + 16) = *(_QWORD *)(v44 + 8LL * v102 + 16);
          *(_QWORD *)(v44 + 8 * v100 + 40) = *(_QWORD *)(v44 + 8LL * v102 + 40);
          *(_QWORD *)(v44 + 8 * v100 + 64) = *(_QWORD *)(v44 + 8LL * v102 + 64);
          v101 = *(_QWORD *)(v44 + 8LL * v102 + 64);
        }
        else
        {
          *(LARGE_INTEGER *)(v44 + 8 * v100 + 16) = v99;
          *(union _LARGE_INTEGER *)(v44 + 8 * v100 + 40) = v98;
          *(_QWORD *)(v44 + 8 * v100 + 64) = v101;
        }
        *(_QWORD *)(v44 + 8 * v100 + 88) = v45;
        v103 = *(_BYTE *)(v44 + 112) + 1;
        *(_QWORD *)v44 = v101;
        *(_QWORD *)(v44 + 8) = v45;
        *(_BYTE *)(v44 + 112) = v103 % 3u;
      }
      v46 = *(_QWORD *)v44;
      if ( v43 )
      {
        do
        {
          v146 = (__int64 *)*v43;
          RtlAcquireWriteLockAtDpcLevel(v43 + 7, &v182);
          *((_DWORD *)v43 + 144) &= ~4u;
          v147 = 0;
          v148 = *((_DWORD *)v43 + 144);
          v149 = 0;
          v166.QuadPart = 0;
          v157.QuadPart = 0;
          PortNumber = 0;
          if ( (v148 & 8) == 0 )
          {
            if ( (unsigned __int8)QosFlowNeedQueueFeedback(v43 + 12, v46, v188) )
            {
              v150 = PcpLineFindByLuid(v43[6]);
              v151 = (PNDIS_RW_LOCK_EX *)v150;
              if ( v150 )
              {
                PcpLineSignalExternalEvent(v150, CurrentProcessorNumber);
                NdisAcquireRWLockWrite(v151[2], (PLOCK_STATE_EX)&v159, 0);
                QosLineQueryQueueFeedback(v151 + 3, v152, v188);
                NdisReleaseRWLock(v151[2], (PLOCK_STATE_EX)&v159);
                PcpLineDereference(v151);
                QosTbcAdjustSendWindow(v43 + 12, v188);
              }
            }
            QosFlowProcessQueuedNetBufferLists(
              (_DWORD)v43 + 96,
              CurrentProcessorNumber,
              (unsigned int)&v166,
              (unsigned int)&PortNumber,
              (__int64)&v157);
            v147 = (struct _NET_BUFFER_LIST *)v166.QuadPart;
            v149 = (struct _NET_BUFFER_LIST *)v157.QuadPart;
          }
          KeReleaseInStackQueuedSpinLockFromDpcLevel(&v182);
          if ( v147 )
            PcpSchedulerBatchAndSendOrDropNblChain(v147);
          if ( v149 )
            PcpSchedulerBatchAndSendOrDropNblChain(v149);
          PcpDereferenceFlow(v43 - 5);
          v43 = v146;
        }
        while ( v146 );
      }
    }
    if ( !v154 )
      KeLowerIrql(v155);
  }
  else
  {
    for ( k = a2; k; k = (struct _NET_BUFFER_LIST *)k->Link.Alignment )
      k->Status = -1071448022;
    NdisFSendNetBufferListsComplete(*(NDIS_HANDLE *)(a1 + 40), a2, a4);
  }
}

```

## disassembly

```asm
0x140005c10  mov     r11, rsp
0x140005c13  push    rbp
0x140005c14  push    rdi
0x140005c15  push    r14
0x140005c17  push    r15
0x140005c19  lea     rbp, [r11-198h]
0x140005c20  sub     rsp, 278h
0x140005c27  mov     rax, cs:__security_cookie
0x140005c2e  xor     rax, rsp
0x140005c31  mov     [rbp+190h+var_50], rax
0x140005c38  xorps   xmm0, xmm0
0x140005c3b  mov     [rbp+190h+PortNumber], r8d
0x140005c3f  xor     eax, eax
0x140005c41  mov     [rbp+190h+var_1E8], rdx
0x140005c45  xor     edi, edi
0x140005c47  mov     qword ptr [rbp+190h+LockHandle.OldIrql], rax
0x140005c4e  cmp     dword ptr [rcx+18h], 2
0x140005c52  mov     r15d, r9d
0x140005c55  mov     r14, rcx
0x140005c58  mov     [rbp+190h+var_190], rdi
0x140005c5c  movups  xmmword ptr [rbp+190h+LockHandle.LockQueue.Next], xmm0
0x140005c63  movups  [rbp+190h+var_A0], xmm0
0x140005c6a  movups  [rbp+190h+var_90], xmm0
0x140005c71  movups  [rbp+190h+var_80], xmm0
0x140005c78  movups  [rbp+190h+var_70], xmm0
0x140005c7f  movups  [rbp+190h+var_60], xmm0
0x140005c86  jnz     loc_140006648
0x140005c8c  mov     [r11-28h], rbx
0x140005c90  mov     [r11-30h], rsi
0x140005c94  mov     [r11-38h], r12
0x140005c98  mov     [r11-40h], r13
0x140005c9c  test    r15b, 1
0x140005ca0  jnz     loc_1400060B4
0x140005ca6  mov     cl, 2; NewIrql
0x140005ca8  mov     byte ptr [rsp+290h+var_240+1], al
0x140005cac  call    cs:__imp_KfRaiseIrql
0x140005cb3  nop     dword ptr [rax+rax+00h]
0x140005cb8  xor     ecx, ecx; ProcNumber
0x140005cba  mov     byte ptr [rsp+290h+var_240+2], al
0x140005cbe  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140005cc5  nop     dword ptr [rax+rax+00h]
0x140005cca  mov     rcx, cs:QosgTimerTable
0x140005cd1  mov     dword ptr [rsp+290h+var_240+4], eax
0x140005cd5  mov     r12d, eax
0x140005cd8  mov     eax, eax
0x140005cda  mov     rsi, [rcx]
0x140005cdd  lea     rcx, [rbp+190h+PerformanceFrequency]; PerformanceFrequency
0x140005ce1  shl     rax, 7
0x140005ce5  add     rsi, rax
0x140005ce8  mov     [rbp+190h+var_1D0], rax
0x140005cec  mov     rax, 0FFFFF78000000008h
0x140005cf6  mov     rbx, [rax]
0x140005cf9  mov     qword ptr [rbp+190h+PerformanceFrequency], rdi
0x140005cfd  call    cs:__imp_KeQueryPerformanceCounter
0x140005d04  nop     dword ptr [rax+rax+00h]
0x140005d09  mov     rcx, qword ptr [rbp+190h+PerformanceFrequency]
0x140005d0d  xor     edx, edx
0x140005d0f  mov     r8, rax
0x140005d12  shr     rax, 20h
0x140005d16  imul    r10, rax, 0F4240h
0x140005d1d  mov     rax, r10
0x140005d20  div     rcx
0x140005d23  mov     rax, rdx
0x140005d26  mov     edx, r8d
0x140005d29  imul    r9, rdx, 0F4240h
0x140005d30  shl     rax, 20h
0x140005d34  xor     edx, edx
0x140005d36  add     rax, r9
0x140005d39  div     rcx
0x140005d3c  xor     edx, edx
0x140005d3e  mov     rdi, rax
0x140005d41  mov     rax, r10
0x140005d44  div     rcx
0x140005d47  movzx   edx, byte ptr [rsi+70h]
0x140005d4b  shl     rax, 20h
0x140005d4f  add     rdi, rax
0x140005d52  mov     [rbp+190h+var_1D8], rdi
0x140005d56  test    dl, dl
0x140005d58  jz      loc_140006142
0x140005d5e  lea     eax, [rdx-1]
0x140005d61  movzx   r9d, al
0x140005d65  mov     rax, [rsi+r9*8+40h]
0x140005d6a  sub     rax, rdi
0x140005d6d  test    rax, rax
0x140005d70  jg      loc_140006C47
0x140005d76  mov     [rsi+rdx*8+10h], r8
0x140005d7b  mov     [rsi+rdx*8+28h], rcx
0x140005d80  mov     [rsi+rdx*8+40h], rdi
0x140005d85  mov     [rsi+rdx*8+58h], rbx
0x140005d8a  mov     r13, r12
0x140005d8d  movzx   eax, byte ptr [rsi+70h]
0x140005d91  lea     r12, [r12+r12*2]
0x140005d95  inc     al
0x140005d97  mov     [rsi+8], rbx
0x140005d9b  mov     rbx, [rbp+190h+var_1E8]
0x140005d9f  xorps   xmm0, xmm0
0x140005da2  movzx   ecx, al
0x140005da5  mov     eax, 0AAAAAAABh
0x140005daa  mul     ecx
0x140005dac  movups  xmmword ptr [rbp+190h+NetBufferList], xmm0
0x140005db0  mov     [rsi], rdi
0x140005db3  shr     edx, 1
0x140005db5  shl     r13, 6
0x140005db9  shl     r12, 6
0x140005dbd  mov     [rbp+190h+var_138], r13
0x140005dc1  lea     eax, [rdx+rdx*2]
0x140005dc4  mov     [rbp+190h+var_140], r12
0x140005dc8  sub     ecx, eax
0x140005dca  xor     edx, edx
0x140005dcc  mov     rax, cs:PcgDelayQueue
0x140005dd3  mov     [rsi+70h], cl
0x140005dd6  mov     rsi, [rbp+190h+NetBufferList]
0x140005dda  mov     [rbp+190h+var_188], rdx
0x140005dde  inc     dword ptr [rax+r13+10h]
0x140005de3  mov     rax, cs:PcgTimerUnits
0x140005dea  inc     dword ptr [r12+rax+28h]
0x140005def  xor     eax, eax
0x140005df1  mov     [rbp+190h+var_1A8], rax
0x140005df5  test    rbx, rbx
0x140005df8  jz      loc_140005EA0
0x140005dfe  mov     r12, [rbp+190h+NetBufferList+8]
0x140005e02  mov     r8, 7FFFFFFFFFFFFFFFh
0x140005e0c  mov     rax, rbx
0x140005e0f  mov     r13, rbx
0x140005e12  mov     rbx, [rbx]
0x140005e15  mov     [rbp+190h+var_1E8], rbx
0x140005e19  mov     [rax], rdx
0x140005e1c  cmp     byte ptr [r14+0D3h], 1
0x140005e24  mov     rcx, [r13+0A8h]
0x140005e2b  mov     [rsp+290h+var_228], rcx
0x140005e30  jz      loc_1400066AF
0x140005e36  cmp     dword ptr [r14+10h], 3
0x140005e3b  mov     rdx, [r14+0A0h]
0x140005e42  mov     [rbp+190h+P], rdx
0x140005e46  mov     byte ptr [rsp+290h+var_240], 0
0x140005e4b  jz      loc_140006552
0x140005e51  test    rcx, rcx
0x140005e54  jnz     loc_140006192
0x140005e5a  test    r12, r12
0x140005e5d  jnz     loc_140006135
0x140005e63  mov     rax, rsi
0x140005e66  mov     rsi, r13
0x140005e69  mov     [r13+0], rax
0x140005e6d  test    rax, rax
0x140005e70  jnz     short loc_140005E75
0x140005e72  mov     r12, r13
0x140005e75  cmp     byte ptr [rsp+290h+var_240], 0
0x140005e7a  jnz     loc_1400060BE
0x140005e80  mov     edx, 0
0x140005e85  mov     r8, 7FFFFFFFFFFFFFFFh
0x140005e8f  test    rbx, rbx
0x140005e92  jnz     loc_140005E0C
0x140005e98  mov     r12, [rbp+190h+var_140]
0x140005e9c  mov     r13, [rbp+190h+var_138]
0x140005ea0  test    rsi, rsi
0x140005ea3  jz      short loc_140005EBF
0x140005ea5  mov     r8d, [rbp+190h+PortNumber]; PortNumber
0x140005ea9  mov     r9d, r15d; SendFlags
0x140005eac  mov     rcx, [r14+28h]; NdisFilterHandle
0x140005eb0  mov     rdx, rsi; NetBufferList
0x140005eb3  call    cs:__imp_NdisFSendNetBufferLists
0x140005eba  nop     dword ptr [rax+rax+00h]
0x140005ebf  mov     r14, [rbp+190h+var_1D0]
0x140005ec3  lea     rcx, [rsp+290h+var_238]; PerformanceFrequency
0x140005ec8  xor     eax, eax
0x140005eca  xorps   xmm0, xmm0
0x140005ecd  mov     [rbp+190h+var_1A8], rax
0x140005ed1  xor     r15d, r15d
0x140005ed4  mov     rax, cs:QosgTimerTable
0x140005edb  movups  xmmword ptr [rbp+190h+NetBufferList], xmm0
0x140005edf  mov     rsi, [rax]
0x140005ee2  mov     rax, 0FFFFF78000000008h
0x140005eec  add     rsi, r14
0x140005eef  mov     rbx, [rax]
0x140005ef2  mov     qword ptr [rsp+290h+var_238], r15
0x140005ef7  call    cs:__imp_KeQueryPerformanceCounter
0x140005efe  nop     dword ptr [rax+rax+00h]
0x140005f03  mov     rcx, qword ptr [rsp+290h+var_238]
0x140005f08  xor     edx, edx
0x140005f0a  mov     r8, rax
0x140005f0d  shr     rax, 20h
0x140005f11  imul    r10, rax, 0F4240h
0x140005f18  mov     rax, r10
0x140005f1b  div     rcx
0x140005f1e  mov     rax, rdx
0x140005f21  mov     edx, r8d
0x140005f24  imul    r9, rdx, 0F4240h
0x140005f2b  shl     rax, 20h
0x140005f2f  xor     edx, edx
0x140005f31  add     rax, r9
0x140005f34  div     rcx
0x140005f37  xor     edx, edx
0x140005f39  mov     rdi, rax
0x140005f3c  mov     rax, r10
0x140005f3f  div     rcx
0x140005f42  movzx   edx, byte ptr [rsi+70h]
0x140005f46  shl     rax, 20h
0x140005f4a  add     rdi, rax
0x140005f4d  test    dl, dl
0x140005f4f  jz      loc_140006149
0x140005f55  lea     eax, [rdx-1]
0x140005f58  movzx   r9d, al
0x140005f5c  mov     rax, [rsi+r9*8+40h]
0x140005f61  sub     rax, rdi
0x140005f64  test    rax, rax
0x140005f67  jg      loc_140007061
0x140005f6d  mov     [rsi+rdx*8+10h], r8
0x140005f72  mov     [rsi+rdx*8+28h], rcx
0x140005f77  mov     [rsi+rdx*8+40h], rdi
0x140005f7c  mov     [rsi+rdx*8+58h], rbx
0x140005f81  movzx   eax, byte ptr [rsi+70h]
0x140005f85  inc     al
0x140005f87  mov     [rsi+8], rbx
0x140005f8b  movzx   ecx, al
0x140005f8e  mov     eax, 0AAAAAAABh
0x140005f93  mul     ecx
0x140005f95  mov     [rsi], rdi
0x140005f98  shr     edx, 1
0x140005f9a  lea     eax, [rdx+rdx*2]
0x140005f9d  sub     ecx, eax
0x140005f9f  mov     [rsi+70h], cl
0x140005fa2  mov     rbx, cs:PcgTimerUnits
0x140005fa9  add     rbx, r12
0x140005fac  cmp     cs:PcgDisableRecursionFix, r15d
0x140005fb3  jnz     loc_140007089
0x140005fb9  mov     eax, 1
0x140005fbe  cmp     [rbx+28h], eax
0x140005fc1  jnz     short loc_140005FF8
0x140005fc3  lea     rdx, [rbp+190h+NetBufferList]; LockHandle
0x140005fc7  mov     rcx, rbx; SpinLock
0x140005fca  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140005fd1  nop     dword ptr [rax+rax+00h]
0x140005fd6  mov     eax, [rbx+8]
0x140005fd9  test    eax, eax
0x140005fdb  jnz     short loc_140005FD6
0x140005fdd  mov     eax, [rbx+2Ch]
0x140005fe0  test    al, 1
0x140005fe2  jz      loc_140007094
0x140005fe8  lea     rcx, [rbp+190h+NetBufferList]; LockHandle
0x140005fec  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140005ff3  nop     dword ptr [rax+rax+00h]
0x140005ff8  cmp     cs:PcgDisableRecursionFix, r15d
0x140005fff  jnz     short loc_140006004
0x140006001  dec     dword ptr [rbx+28h]
0x140006004  mov     rcx, cs:PcgDelayQueue
0x14000600b  add     rcx, r13
0x14000600e  mov     r13, [rsp+290h+var_38]
0x140006016  add     dword ptr [rcx+10h], 0FFFFFFFFh
0x14000601a  jnz     short loc_14000607A
0x14000601c  mov     rsi, [rcx]
0x14000601f  xor     eax, eax
0x140006021  mov     qword ptr [rbp+190h+var_168.OldIrql], rax
0x140006025  xorps   xmm0, xmm0
0x140006028  mov     word ptr [rsp+290h+var_228], ax
0x14000602d  mov     byte ptr [rsp+290h+var_228+2], al
0x140006031  movups  xmmword ptr [rbp+190h+var_168.LockQueue.Next], xmm0
0x140006035  mov     [rcx], r15
0x140006038  mov     [rcx+8], r15
0x14000603c  mov     [rbp+190h+var_108], eax
0x140006042  mov     rax, cs:QosgTimerTable
0x140006049  movups  [rbp+190h+var_128], xmm0
0x14000604d  movups  [rbp+190h+var_118], xmm0
0x140006051  mov     rdi, [rax]
0x140006054  mov     rax, 0FFFFF78000000008h
0x14000605e  add     rdi, r14
0x140006061  mov     rbx, [rax]
0x140006064  cmp     rbx, [rdi+8]
0x140006068  jnz     loc_1400067B5
0x14000606e  mov     rbx, [rdi]
0x140006071  test    rsi, rsi
0x140006074  jnz     loc_1400070F9
0x14000607a  cmp     byte ptr [rsp+290h+var_240+1], 0
0x14000607f  mov     r12, [rsp+290h+var_30]
0x140006087  mov     rsi, [rsp+290h+var_28]
0x14000608f  mov     rbx, [rsp+270h]
0x140006097  jnz     loc_140007230
0x14000609d  movzx   ecx, byte ptr [rsp+290h+var_240+2]; NewIrql
0x1400060a2  call    cs:__imp_KeLowerIrql
0x1400060a9  nop     dword ptr [rax+rax+00h]
0x1400060ae  jmp     loc_140007230
0x1400060b4  mov     byte ptr [rsp+290h+var_240+1], 1
0x1400060b9  jmp     loc_140005CB8
0x1400060be  mov     r13, [rbp+190h+P]
0x1400060c2  mov     eax, 0FFFFFFFFh
0x1400060c7  lock xadd [r13+0F8h], eax
0x1400060d0  cmp     eax, 1
0x1400060d3  jnz     loc_140005E80
0x1400060d9  mov     rcx, [r13+140h]; VirtualAddress
0x1400060e0  test    rcx, rcx
0x1400060e3  jz      short loc_1400060F6
0x1400060e5  mov     edx, 616E6350h; Tag
0x1400060ea  call    cs:__imp_NdisFreeMemoryWithTag
0x1400060f1  nop     dword ptr [rax+rax+00h]
0x1400060f6  mov     rcx, [r13+100h]
0x1400060fd  test    rcx, rcx
0x140006100  jz      short loc_140006107
0x140006102  call    PcpFilterDecrementDetachCount
0x140006107  mov     rcx, [r13+10h]; Lock
0x14000610b  test    rcx, rcx
0x14000610e  jz      short loc_14000611C
  ... truncated ...
```
