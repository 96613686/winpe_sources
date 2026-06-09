# PcFilterSendNetBufferListsComplete

- ea: `0x1400085c0`
- end: `0x140009001`
- name: `PcFilterSendNetBufferListsComplete`
- size: `2625`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000298c`
- `0x140003770`
- `0x140007e10`
- `0x140008290`
- `0x1400085c0`
- `0x140009010`
- `0x140009100`
- `0x140009140`
- `0x140009b80`
- `0x14000a380`
- `0x14000a8c4`
- `0x14000bcb4`
- `0x14000cce0`
- `0x140011154`
- `0x140011904`
- `0x140011a34`
- `0x140011ae8`
- `0x140012410`

## import_xrefs

- `ntoskrnl!IoGetStackLimits` at `0x140008729`
- `ntoskrnl!IoGetStackLimits` at `0x140008729`
- `ntoskrnl!KfRaiseIrql` at `0x14000860e`
- `ntoskrnl!KfRaiseIrql` at `0x14000860e`
- `ntoskrnl!KeLowerIrql` at `0x1400089e2`
- `ntoskrnl!KeLowerIrql` at `0x1400089e2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140008b84`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140008b84`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000861f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000861f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140008947`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140008a84`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140008e76`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140008faf`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140008947`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140008a84`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140008e76`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140008faf`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140008921`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140008a35`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140008921`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140008a35`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140008b3b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140008b3b`
- `NDIS!NdisFreeNetBufferListContext` at `0x140008e00`
- `NDIS!NdisFreeNetBufferListContext` at `0x140008e00`
- `NDIS!NdisFSendNetBufferListsComplete` at `0x1400087fa`
- `NDIS!NdisFSendNetBufferListsComplete` at `0x140008bd1`
- `NDIS!NdisFSendNetBufferListsComplete` at `0x1400087fa`
- `NDIS!NdisFSendNetBufferListsComplete` at `0x140008bd1`
- `NDIS!NdisReleaseRWLock` at `0x140008d92`
- `NDIS!NdisReleaseRWLock` at `0x140008f61`
- `NDIS!NdisReleaseRWLock` at `0x140008d92`
- `NDIS!NdisReleaseRWLock` at `0x140008f61`
- `NDIS!NdisAcquireRWLockWrite` at `0x140008d66`
- `NDIS!NdisAcquireRWLockWrite` at `0x140008f40`
- `NDIS!NdisAcquireRWLockWrite` at `0x140008d66`
- `NDIS!NdisAcquireRWLockWrite` at `0x140008f40`
- `HAL!KeQueryPerformanceCounter` at `0x140008669`
- `HAL!KeQueryPerformanceCounter` at `0x140008849`
- `HAL!KeQueryPerformanceCounter` at `0x140008c67`
- `HAL!KeQueryPerformanceCounter` at `0x140008669`
- `HAL!KeQueryPerformanceCounter` at `0x140008849`
- `HAL!KeQueryPerformanceCounter` at `0x140008c67`

## pseudocode

```c
void __fastcall PcFilterSendNetBufferListsComplete(union _LARGE_INTEGER a1, struct _NET_BUFFER_LIST *a2, ULONG a3)
{
  KIRQL v3; // al
  unsigned __int8 v6; // r12
  ULONG CurrentProcessorNumber; // eax
  __int64 v8; // r14
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // r15
  __int64 v11; // rbx
  LARGE_INTEGER v12; // rax
  union _LARGE_INTEGER v13; // rcx
  LARGE_INTEGER v14; // r8
  __int64 v15; // rdx
  unsigned __int64 v16; // rdi
  unsigned __int8 v17; // al
  unsigned __int8 v18; // al
  union _LARGE_INTEGER v19; // r9
  struct _NET_BUFFER_LIST *Next; // rbx
  __int64 v21; // r8
  volatile PKSPIN_LOCK Lock; // rcx
  union _LARGE_INTEGER v23; // r14
  struct _NET_BUFFER_LIST *Alignment; // r15
  union _LARGE_INTEGER v25; // rdx
  ULONGLONG v26; // rax
  struct _NET_BUFFER_LIST *v27; // r15
  __int64 v28; // rbx
  char *v29; // rsi
  LARGE_INTEGER v30; // rax
  union _LARGE_INTEGER v31; // rcx
  LARGE_INTEGER v32; // r8
  __int64 v33; // rdx
  unsigned __int64 v34; // rdi
  unsigned __int8 v35; // al
  unsigned __int8 v36; // al
  char *v37; // rbx
  int v38; // eax
  char *v39; // rcx
  __int64 *v41; // rsi
  unsigned __int64 v42; // rbx
  unsigned __int64 *v43; // rdi
  unsigned __int64 v44; // rbx
  __int64 v45; // rax
  __int64 v46; // rdx
  struct _NET_BUFFER_LIST *v47; // rax
  __int64 v48; // rdx
  unsigned int NblChainDataLength; // eax
  __int64 v50; // r9
  char *v51; // rax
  __int64 v52; // rcx
  PVOID v53; // rcx
  PNET_BUFFER_LIST_CONTEXT Context; // rcx
  __int64 Offset; // r10
  LARGE_INTEGER v56; // rax
  union _LARGE_INTEGER v57; // r8
  LARGE_INTEGER v58; // r9
  __int64 v59; // rdx
  unsigned __int64 v60; // rcx
  unsigned __int8 v61; // al
  unsigned __int8 v62; // dl
  ULONG v63; // r12d
  __int64 *v64; // r15
  struct _NET_BUFFER_LIST *v65; // rdi
  int v66; // eax
  struct _NET_BUFFER_LIST *v67; // r14
  __int64 v68; // rax
  PNDIS_RW_LOCK_EX *v69; // rdi
  __int64 v70; // rdx
  char *P; // [rsp+30h] [rbp-D0h]
  struct _NET_BUFFER_LIST *v72; // [rsp+38h] [rbp-C8h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+40h] [rbp-C0h] BYREF
  ULONG v74; // [rsp+44h] [rbp-BCh]
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v76; // [rsp+50h] [rbp-B0h]
  struct _NET_BUFFER_LIST *v77; // [rsp+58h] [rbp-A8h] BYREF
  union _LARGE_INTEGER v78; // [rsp+60h] [rbp-A0h]
  volatile PKSPIN_LOCK v79; // [rsp+68h] [rbp-98h]
  struct _KLOCK_QUEUE_HANDLE NetBufferList; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 HighLimit; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 LowLimit; // [rsp+90h] [rbp-70h] BYREF
  __int64 v83; // [rsp+98h] [rbp-68h]
  _OWORD v84[2]; // [rsp+A0h] [rbp-60h] BYREF
  int v85; // [rsp+C0h] [rbp-40h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+C8h] [rbp-38h] BYREF
  struct _KLOCK_QUEUE_HANDLE v87; // [rsp+E0h] [rbp-20h] BYREF
  struct _KLOCK_QUEUE_HANDLE v88; // [rsp+F8h] [rbp-8h] BYREF
  union _LARGE_INTEGER v89; // [rsp+160h] [rbp+60h] BYREF
  char v90; // [rsp+168h] [rbp+68h]
  struct _LOCK_STATE_EX v91; // [rsp+170h] [rbp+70h] BYREF
  KIRQL v92; // [rsp+178h] [rbp+78h]

  v89 = a1;
  v3 = 0;
  v91.OldIrql = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  memset(&NetBufferList, 0, sizeof(NetBufferList));
  v6 = a3 & 1;
  if ( (a3 & 1) != 0 )
  {
    v90 = 1;
  }
  else
  {
    v90 = 0;
    v3 = KfRaiseIrql(2u);
  }
  v92 = v3;
  CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
  v8 = CurrentProcessorNumber;
  v74 = CurrentProcessorNumber;
  v9 = (unsigned __int64)CurrentProcessorNumber << 7;
  v10 = v9 + *(_QWORD *)QosgTimerTable;
  v77 = (struct _NET_BUFFER_LIST *)v9;
  v83 = v8;
  v11 = MEMORY[0xFFFFF78000000008];
  PerformanceFrequency.QuadPart = 0;
  v12 = KeQueryPerformanceCounter(&PerformanceFrequency);
  v13 = PerformanceFrequency;
  v14 = v12;
  v15 = *(unsigned __int8 *)(v10 + 112);
  v16 = ((1000000 * HIDWORD(v12.QuadPart) / (unsigned __int64)PerformanceFrequency.QuadPart) << 32)
      + (1000000LL * v12.LowPart
       + ((1000000 * HIDWORD(v12.QuadPart) % (unsigned __int64)PerformanceFrequency.QuadPart) << 32))
      / PerformanceFrequency.QuadPart;
  if ( (_BYTE)v15 )
    v17 = v15 - 1;
  else
    v17 = 2;
  if ( (__int64)(*(_QWORD *)(v10 + 8LL * v17 + 64) - v16) > 0 )
  {
    *(_QWORD *)(v10 + 8 * v15 + 16) = *(_QWORD *)(v10 + 8LL * v17 + 16);
    *(_QWORD *)(v10 + 8 * v15 + 40) = *(_QWORD *)(v10 + 8LL * v17 + 40);
    *(_QWORD *)(v10 + 8 * v15 + 64) = *(_QWORD *)(v10 + 8LL * v17 + 64);
    v16 = *(_QWORD *)(v10 + 8LL * v17 + 64);
  }
  else
  {
    *(LARGE_INTEGER *)(v10 + 8 * v15 + 16) = v14;
    *(union _LARGE_INTEGER *)(v10 + 8 * v15 + 40) = v13;
    *(_QWORD *)(v10 + 8 * v15 + 64) = v16;
  }
  *(_QWORD *)(v10 + 8 * v15 + 88) = v11;
  v18 = *(_BYTE *)(v10 + 112) + 1;
  *(_QWORD *)(v10 + 8) = v11;
  *(_QWORD *)v10 = v16;
  HighLimit = 0;
  LowLimit = 0;
  *(_BYTE *)(v10 + 112) = v18 % 3u;
  IoGetStackLimits(&LowLimit, &HighLimit);
  if ( (unsigned __int64)&HighLimit - LowLimit > 0x2000 )
  {
    v91.OldIrql = 1;
    ++*((_DWORD *)PcgDelayQueue + 16 * v8 + 4);
    ++*((_DWORD *)PcgTimerUnits + 48 * v8 + 10);
  }
  PerformanceFrequency.QuadPart = 0;
  v19.QuadPart = 0;
  Next = (struct _NET_BUFFER_LIST *)NetBufferList.LockQueue.Next;
  v21 = 1;
  if ( a2 )
  {
    Lock = NetBufferList.LockQueue.Lock;
    v23 = v89;
    v79 = NetBufferList.LockQueue.Lock;
    do
    {
      Alignment = (struct _NET_BUFFER_LIST *)a2->Link.Alignment;
      a2->Link.Alignment = 0;
      v25 = (union _LARGE_INTEGER)a2->NetBufferListInfo[3];
      v78 = v25;
      if ( v25.QuadPart )
      {
        if ( *(_DWORD *)(v23.QuadPart + 16) == 3 && *(_WORD *)(v23.QuadPart + 212) == 2048 )
        {
          Context = a2->Context;
          Offset = Context->Offset;
          if ( a2->SourceHandle == *(NDIS_HANDLE *)(v23.QuadPart + 40) )
            v45 = *(_QWORD *)&Context->ContextData[Offset + 32] - 24LL;
          else
            v45 = *(_QWORD *)&Context->ContextData[Offset];
        }
        else
        {
          v45 = *(_QWORD *)(v23.QuadPart + 160);
        }
        P = (char *)v45;
        if ( v25.QuadPart != v19.QuadPart )
        {
          PerformanceFrequency = v25;
          v72 = (struct _NET_BUFFER_LIST *)(v25.QuadPart + 96);
          KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v25.QuadPart + 96), &LockHandle);
          while ( *((_DWORD *)&v72->NetBufferListHeader.Link.HeaderX64 + 2) )
            ;
          if ( *(_DWORD *)(v78.QuadPart + 84) != v74 )
          {
            v46 = *(_QWORD *)(v78.QuadPart + 232);
            if ( v46 != v78.QuadPart + 232 && (__int64)(*(_QWORD *)(v46 + 24) - v16) <= 0 )
              ((void (__fastcall *)(_QWORD, _QWORD))PcpFlowDelay)((union _LARGE_INTEGER)v78.QuadPart, v74);
          }
          KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
          v21 = 1;
        }
        *(_WORD *)&LockState.OldIrql = 0;
        LockState.Flags = 0;
        v47 = (struct _NET_BUFFER_LIST *)((char *)v77 + *(_QWORD *)QosgTimerTable);
        v72 = v47;
        v48 = MEMORY[0xFFFFF78000000008];
        if ( MEMORY[0xFFFFF78000000008] != v47->Link.Region )
        {
          QosTimerConvertPerformanceCounterToMicroseconds(v47, MEMORY[0xFFFFF78000000008], 1);
          v47 = v72;
          v21 = 1;
        }
        if ( ((__int64)(*((_QWORD *)P + 24) - v47->Link.Alignment) <= 0
           || (__int64)(*((_QWORD *)P + 23) - v47->Link.Alignment) <= 0)
          && !_InterlockedExchangeAdd((volatile signed __int32 *)P + 38, 1u) )
        {
          NdisAcquireRWLockWrite(*((PNDIS_RW_LOCK_EX *)P + 2), &LockState, 0);
          QosLineSignalExternalEvent(P + 24, v74);
          NdisReleaseRWLock(*((PNDIS_RW_LOCK_EX *)P + 2), &LockState);
        }
        NblChainDataLength = QosGetNblChainDataLength(a2, v48, v21);
        _InterlockedAdd((volatile signed __int32 *)(v50 + 160), NblChainDataLength);
        v72 = (struct _NET_BUFFER_LIST *)(v78.QuadPart + 96);
        memset(&v87, 0, sizeof(v87));
        KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v78.QuadPart + 96), &v87);
        while ( *((_DWORD *)&v72->NetBufferListHeader.Link.HeaderX64 + 2) )
          ;
        v76 = 0;
        v72 = a2;
        if ( a2->SourceHandle == (NDIS_HANDLE)*((_QWORD *)P + 7)
          && !*(_DWORD *)&a2->Context->ContextData[a2->Context->Offset + 40] )
        {
          QosNblCadComplete(a2, &v72, v6);
          a2 = v72;
          v76 = 1;
        }
        if ( a2 )
          _InterlockedIncrement((volatile signed __int32 *)(v78.QuadPart + 172));
        KeReleaseInStackQueuedSpinLock(&v87);
        if ( a2 )
        {
          v51 = P;
          v52 = *((_QWORD *)P + 32);
          if ( *(_DWORD *)(v52 + 16) == 3 && *(_WORD *)(v52 + 212) == 2048 )
          {
            PcpLineDereference(P);
            NdisFreeNetBufferListContext(a2, 8u);
            v51 = P;
          }
          v53 = a2->NetBufferListInfo[3];
          if ( v53 && v53 == *(PVOID *)&WPP_MAIN_CB.DeviceLock.Header.Lock )
          {
            PcpDereferenceFlow(v53);
            v51 = P;
            a2->NetBufferListInfo[3] = 0;
          }
          NdisFSendNetBufferListsComplete(*(NDIS_HANDLE *)(*((_QWORD *)v51 + 32) + 40LL), a2, a3);
        }
        if ( v76 )
          PcpFilterDecrementPauseCount(*((_QWORD *)P + 32), v76);
        v19 = PerformanceFrequency;
        Lock = v79;
        v21 = 1;
      }
      else
      {
        if ( Lock )
        {
          v26 = *Lock;
          *Lock = (KSPIN_LOCK)a2;
        }
        else
        {
          v26 = (ULONGLONG)Next;
          Next = a2;
        }
        a2->Link.Alignment = v26;
        if ( !v26 )
        {
          Lock = (volatile PKSPIN_LOCK)a2;
          v79 = (volatile PKSPIN_LOCK)a2;
        }
      }
      a2 = Alignment;
    }
    while ( Alignment );
    v8 = v83;
  }
  if ( Next )
    NdisFSendNetBufferListsComplete(*(NDIS_HANDLE *)(v89.QuadPart + 40), Next, a3);
  if ( v91.OldIrql )
  {
    v27 = v77;
    memset(&NetBufferList, 0, sizeof(NetBufferList));
    v28 = MEMORY[0xFFFFF78000000008];
    v29 = (char *)v77 + *(_QWORD *)QosgTimerTable;
    v89.QuadPart = 0;
    v30 = KeQueryPerformanceCounter(&v89);
    v31 = v89;
    v32 = v30;
    v33 = (unsigned __int8)v29[112];
    v34 = ((1000000 * HIDWORD(v30.QuadPart) / (unsigned __int64)v89.QuadPart) << 32)
        + (1000000LL * v30.LowPart + ((1000000 * HIDWORD(v30.QuadPart) % (unsigned __int64)v89.QuadPart) << 32))
        / v89.QuadPart;
    if ( (_BYTE)v33 )
      v35 = v33 - 1;
    else
      v35 = 2;
    if ( (__int64)(*(_QWORD *)&v29[8 * v35 + 64] - v34) > 0 )
    {
      *(_QWORD *)&v29[8 * v33 + 16] = *(_QWORD *)&v29[8 * v35 + 16];
      *(_QWORD *)&v29[8 * v33 + 40] = *(_QWORD *)&v29[8 * v35 + 40];
      *(_QWORD *)&v29[8 * v33 + 64] = *(_QWORD *)&v29[8 * v35 + 64];
      v34 = *(_QWORD *)&v29[8 * v35 + 64];
    }
    else
    {
      *(LARGE_INTEGER *)&v29[8 * v33 + 16] = v32;
      *(union _LARGE_INTEGER *)&v29[8 * v33 + 40] = v31;
      *(_QWORD *)&v29[8 * v33 + 64] = v34;
    }
    *(_QWORD *)&v29[8 * v33 + 88] = v28;
    v36 = v29[112] + 1;
    *((_QWORD *)v29 + 1) = v28;
    *(_QWORD *)v29 = v34;
    v29[112] = v36 % 3u;
    v37 = (char *)PcgTimerUnits + 192 * v8;
    if ( PcgDisableRecursionFix )
    {
      --*((_DWORD *)v37 + 10);
      v38 = 0;
    }
    else
    {
      v38 = 1;
    }
    if ( *((_DWORD *)v37 + 10) == v38 )
    {
      KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)v37, &NetBufferList);
      while ( *((_DWORD *)v37 + 2) )
        ;
      if ( (*((_DWORD *)v37 + 11) & 1) != 0 || (__int64)(*((_QWORD *)v37 + 3) - v34) > 0 )
      {
        KeReleaseInStackQueuedSpinLockFromDpcLevel(&NetBufferList);
      }
      else
      {
        KeReleaseInStackQueuedSpinLockFromDpcLevel(&NetBufferList);
        *((_DWORD *)v37 + 11) |= 2u;
        PcpTimeoutHandler(0, v37, 0, 0);
        *((_DWORD *)v37 + 11) &= ~2u;
      }
    }
    if ( !PcgDisableRecursionFix )
      --*((_DWORD *)v37 + 10);
    v39 = (char *)PcgDelayQueue + 64 * v8;
    if ( (*((_DWORD *)v39 + 4))-- == 1 )
    {
      v41 = *(__int64 **)v39;
      *(_WORD *)&v91.OldIrql = 0;
      v91.Flags = 0;
      memset(&v88, 0, sizeof(v88));
      *(_QWORD *)v39 = 0;
      *((_QWORD *)v39 + 1) = 0;
      v42 = MEMORY[0xFFFFF78000000008];
      v85 = 0;
      memset(v84, 0, sizeof(v84));
      v43 = (unsigned __int64 *)((char *)v27 + *(_QWORD *)QosgTimerTable);
      if ( MEMORY[0xFFFFF78000000008] != v43[1] )
      {
        v89.QuadPart = 0;
        v56 = KeQueryPerformanceCounter(&v89);
        v57 = v89;
        v58 = v56;
        v59 = *((unsigned __int8 *)v43 + 112);
        v60 = ((1000000 * HIDWORD(v56.QuadPart) / (unsigned __int64)v89.QuadPart) << 32)
            + (1000000LL * v56.LowPart + ((1000000 * HIDWORD(v56.QuadPart) % (unsigned __int64)v89.QuadPart) << 32))
            / v89.QuadPart;
        if ( (_BYTE)v59 )
          v61 = v59 - 1;
        else
          v61 = 2;
        if ( (__int64)(v43[v61 + 8] - v60) > 0 )
        {
          v43[v59 + 2] = v43[v61 + 2];
          v43[v59 + 5] = v43[v61 + 5];
          v43[v59 + 8] = v43[v61 + 8];
          v60 = v43[v61 + 8];
        }
        else
        {
          v43[v59 + 2] = v58.QuadPart;
          v43[v59 + 5] = v57.QuadPart;
          v43[v59 + 8] = v60;
        }
        v43[v59 + 11] = v42;
        v62 = *((_BYTE *)v43 + 112) + 1;
        *v43 = v60;
        v43[1] = v42;
        *((_BYTE *)v43 + 112) = v62 % 3u;
      }
      v44 = *v43;
      if ( v41 )
      {
        v63 = v74;
        do
        {
          v64 = (__int64 *)*v41;
          RtlAcquireWriteLockAtDpcLevel(v41 + 7, &v88);
          *((_DWORD *)v41 + 144) &= ~4u;
          v65 = 0;
          v66 = *((_DWORD *)v41 + 144);
          v67 = 0;
          v77 = 0;
          v72 = 0;
          v89.LowPart = 0;
          if ( (v66 & 8) == 0 )
          {
            if ( (unsigned __int8)QosFlowNeedQueueFeedback(v41 + 12, v44, v84) )
            {
              v68 = PcpLineFindByLuid(v41[6]);
              v69 = (PNDIS_RW_LOCK_EX *)v68;
              if ( v68 )
              {
                PcpLineSignalExternalEvent(v68, v63);
                NdisAcquireRWLockWrite(v69[2], &v91, 0);
                QosLineQueryQueueFeedback(v69 + 3, v70, v84);
                NdisReleaseRWLock(v69[2], &v91);
                PcpLineDereference(v69);
                QosTbcAdjustSendWindow(v41 + 12, v84);
              }
            }
            QosFlowProcessQueuedNetBufferLists(
              (_DWORD)v41 + 96,
              v63,
              (unsigned int)&v77,
              (unsigned int)&v89,
              (__int64)&v72);
            v65 = v77;
            v67 = v72;
          }
          KeReleaseInStackQueuedSpinLockFromDpcLevel(&v88);
          if ( v65 )
            PcpSchedulerBatchAndSendOrDropNblChain(v65);
          if ( v67 )
            PcpSchedulerBatchAndSendOrDropNblChain(v67);
          PcpDereferenceFlow(v41 - 5);
          v41 = v64;
        }
        while ( v64 );
      }
    }
  }
  if ( !v90 )
    KeLowerIrql(v92);
}

```

## disassembly

```asm
0x1400085c0  mov     qword ptr [rsp-8+arg_0], rcx
0x1400085c5  push    rbp
0x1400085c6  push    rbx
0x1400085c7  push    rsi
0x1400085c8  push    rdi
0x1400085c9  push    r12
0x1400085cb  push    r13
0x1400085cd  push    r14
0x1400085cf  push    r15
0x1400085d1  lea     rbp, [rsp-18h]
0x1400085d6  sub     rsp, 118h
0x1400085dd  xor     eax, eax
0x1400085df  xorps   xmm0, xmm0
0x1400085e2  mov     r12d, r8d
0x1400085e5  mov     qword ptr [rbp+50h+LockHandle.OldIrql], rax
0x1400085e9  mov     [rbp+50h+arg_10.OldIrql], al
0x1400085ec  mov     r13d, r8d
0x1400085ef  mov     [rbp+50h+var_D0], rax
0x1400085f3  mov     rsi, rdx
0x1400085f6  movups  xmmword ptr [rbp+50h+LockHandle.LockQueue.Next], xmm0
0x1400085fa  movups  xmmword ptr [rsp+150h+NetBufferList], xmm0
0x1400085ff  and     r12d, 1
0x140008603  jnz     loc_1400089F0
0x140008609  mov     cl, 2; NewIrql
0x14000860b  mov     [rbp+50h+arg_8], al
0x14000860e  call    cs:__imp_KfRaiseIrql
0x140008615  nop     dword ptr [rax+rax+00h]
0x14000861a  xor     ecx, ecx; ProcNumber
0x14000861c  mov     [rbp+50h+arg_18], al
0x14000861f  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140008626  nop     dword ptr [rax+rax+00h]
0x14000862b  mov     rcx, cs:QosgTimerTable
0x140008632  mov     r14d, eax
0x140008635  mov     [rsp+150h+var_10C], eax
0x140008639  mov     eax, eax
0x14000863b  mov     r15, [rcx]
0x14000863e  lea     rcx, [rsp+150h+PerformanceFrequency]; PerformanceFrequency
0x140008643  shl     rax, 7
0x140008647  add     r15, rax
0x14000864a  mov     [rsp+150h+var_F8], rax
0x14000864f  mov     rax, 0FFFFF78000000008h
0x140008659  mov     [rbp+50h+var_B8], r14
0x14000865d  mov     rbx, [rax]
0x140008660  mov     qword ptr [rsp+150h+PerformanceFrequency], 0
0x140008669  call    cs:__imp_KeQueryPerformanceCounter
0x140008670  nop     dword ptr [rax+rax+00h]
0x140008675  mov     rcx, qword ptr [rsp+150h+PerformanceFrequency]
0x14000867a  xor     edx, edx
0x14000867c  mov     r8, rax
0x14000867f  shr     rax, 20h
0x140008683  imul    r10, rax, 0F4240h
0x14000868a  mov     rax, r10
0x14000868d  div     rcx
0x140008690  mov     rax, rdx
0x140008693  mov     edx, r8d
0x140008696  imul    r9, rdx, 0F4240h
0x14000869d  shl     rax, 20h
0x1400086a1  xor     edx, edx
0x1400086a3  add     rax, r9
0x1400086a6  div     rcx
0x1400086a9  xor     edx, edx
0x1400086ab  mov     rdi, rax
0x1400086ae  mov     rax, r10
0x1400086b1  div     rcx
0x1400086b4  movzx   edx, byte ptr [r15+70h]
0x1400086b9  shl     rax, 20h
0x1400086bd  add     rdi, rax
0x1400086c0  test    dl, dl
0x1400086c2  jz      loc_140008C01
0x1400086c8  lea     eax, [rdx-1]
0x1400086cb  movzx   r9d, al
0x1400086cf  mov     rax, [r15+r9*8+40h]
0x1400086d4  sub     rax, rdi
0x1400086d7  test    rax, rax
0x1400086da  jg      loc_140008D1A
0x1400086e0  mov     [r15+rdx*8+10h], r8
0x1400086e5  mov     [r15+rdx*8+28h], rcx
0x1400086ea  mov     [r15+rdx*8+40h], rdi
0x1400086ef  mov     [r15+rdx*8+58h], rbx
0x1400086f4  movzx   eax, byte ptr [r15+70h]
0x1400086f9  inc     al
0x1400086fb  mov     [r15+8], rbx
0x1400086ff  movzx   ecx, al
0x140008702  xor     ebx, ebx
0x140008704  mov     eax, 0AAAAAAABh
0x140008709  mov     [r15], rdi
0x14000870c  mul     ecx
0x14000870e  mov     [rbp+50h+HighLimit], rbx
0x140008712  shr     edx, 1
0x140008714  mov     [rbp+50h+LowLimit], rbx
0x140008718  lea     eax, [rdx+rdx*2]
0x14000871b  sub     ecx, eax
0x14000871d  lea     rdx, [rbp+50h+HighLimit]; HighLimit
0x140008721  mov     [r15+70h], cl
0x140008725  lea     rcx, [rbp+50h+LowLimit]; LowLimit
0x140008729  call    cs:__imp_IoGetStackLimits
0x140008730  nop     dword ptr [rax+rax+00h]
0x140008735  lea     rax, [rbp+50h+HighLimit]
0x140008739  sub     rax, [rbp+50h+LowLimit]
0x14000873d  cmp     rax, 2000h
0x140008743  jbe     short loc_14000876E
0x140008745  mov     rax, cs:PcgDelayQueue
0x14000874c  mov     rcx, r14
0x14000874f  shl     rcx, 6
0x140008753  mov     [rbp+50h+arg_10.OldIrql], 1
0x140008757  inc     dword ptr [rcx+rax+10h]
0x14000875b  lea     rcx, [r14+r14*2]
0x14000875f  mov     rax, cs:PcgTimerUnits
0x140008766  shl     rcx, 6
0x14000876a  inc     dword ptr [rcx+rax+28h]
0x14000876e  mov     qword ptr [rsp+150h+PerformanceFrequency], rbx
0x140008773  mov     r9, rbx
0x140008776  mov     rbx, [rsp+150h+NetBufferList]
0x14000877b  mov     r8d, 1
0x140008781  test    rsi, rsi
0x140008784  jz      short loc_1400087E7
0x140008786  mov     rcx, [rsp+150h+NetBufferList+8]
0x14000878b  mov     eax, 800h
0x140008790  mov     r14, qword ptr [rbp+50h+arg_0]
0x140008794  xor     r10d, r10d
0x140008797  mov     [rsp+150h+var_E8], rcx
0x14000879c  mov     r15, [rsi]
0x14000879f  mov     [rsi], r10
0x1400087a2  mov     rdx, [rsi+0A8h]
0x1400087a9  mov     [rsp+150h+var_F0], rdx
0x1400087ae  test    rdx, rdx
0x1400087b1  jnz     loc_140008A04
0x1400087b7  test    rcx, rcx
0x1400087ba  jnz     loc_1400089F9
0x1400087c0  mov     rax, rbx
0x1400087c3  mov     rbx, rsi
0x1400087c6  mov     [rsi], rax
0x1400087c9  test    rax, rax
0x1400087cc  jnz     short loc_1400087D6
0x1400087ce  mov     rcx, rsi
0x1400087d1  mov     [rsp+150h+var_E8], rcx
0x1400087d6  mov     rsi, r15
0x1400087d9  mov     eax, 800h
0x1400087de  test    r15, r15
0x1400087e1  jnz     short loc_14000879C
0x1400087e3  mov     r14, [rbp+50h+var_B8]
0x1400087e7  test    rbx, rbx
0x1400087ea  jz      short loc_140008806
0x1400087ec  mov     rcx, qword ptr [rbp+50h+arg_0]
0x1400087f0  mov     r8d, r13d; SendCompleteFlags
0x1400087f3  mov     rdx, rbx; NetBufferList
0x1400087f6  mov     rcx, [rcx+28h]; NdisFilterHandle
0x1400087fa  call    cs:__imp_NdisFSendNetBufferListsComplete
0x140008801  nop     dword ptr [rax+rax+00h]
0x140008806  cmp     [rbp+50h+arg_10.OldIrql], 0
0x14000880a  jz      loc_1400089C3
0x140008810  mov     r15, [rsp+150h+var_F8]
0x140008815  lea     rcx, [rbp+50h+arg_0]; PerformanceFrequency
0x140008819  xor     eax, eax
0x14000881b  xorps   xmm0, xmm0
0x14000881e  mov     [rbp+50h+var_D0], rax
0x140008822  mov     r12, 0FFFFF78000000008h
0x14000882c  mov     rax, cs:QosgTimerTable
0x140008833  xor     r13d, r13d
0x140008836  movups  xmmword ptr [rsp+150h+NetBufferList], xmm0
0x14000883b  mov     rbx, [r12]
0x14000883f  mov     rsi, [rax]
0x140008842  add     rsi, r15
0x140008845  mov     qword ptr [rbp+50h+arg_0], r13
0x140008849  call    cs:__imp_KeQueryPerformanceCounter
0x140008850  nop     dword ptr [rax+rax+00h]
0x140008855  mov     rcx, qword ptr [rbp+50h+arg_0]
0x140008859  xor     edx, edx
0x14000885b  mov     r8, rax
0x14000885e  shr     rax, 20h
0x140008862  imul    r10, rax, 0F4240h
0x140008869  mov     rax, r10
0x14000886c  div     rcx
0x14000886f  mov     rax, rdx
0x140008872  mov     edx, r8d
0x140008875  imul    r9, rdx, 0F4240h
0x14000887c  shl     rax, 20h
0x140008880  xor     edx, edx
0x140008882  add     rax, r9
0x140008885  div     rcx
0x140008888  xor     edx, edx
0x14000888a  mov     rdi, rax
0x14000888d  mov     rax, r10
0x140008890  div     rcx
0x140008893  movzx   edx, byte ptr [rsi+70h]
0x140008897  shl     rax, 20h
0x14000889b  add     rdi, rax
0x14000889e  test    dl, dl
0x1400088a0  jz      loc_140008C08
0x1400088a6  lea     eax, [rdx-1]
0x1400088a9  movzx   r9d, al
0x1400088ad  mov     rax, [rsi+r9*8+40h]
0x1400088b2  sub     rax, rdi
0x1400088b5  test    rax, rax
0x1400088b8  jg      loc_140008E2E
0x1400088be  mov     [rsi+rdx*8+10h], r8
0x1400088c3  mov     [rsi+rdx*8+28h], rcx
0x1400088c8  mov     [rsi+rdx*8+40h], rdi
0x1400088cd  mov     [rsi+rdx*8+58h], rbx
0x1400088d2  movzx   eax, byte ptr [rsi+70h]
0x1400088d6  inc     al
0x1400088d8  mov     [rsi+8], rbx
0x1400088dc  movzx   ecx, al
0x1400088df  lea     rbx, [r14+r14*2]
0x1400088e3  shl     rbx, 6
0x1400088e7  mov     eax, 0AAAAAAABh
0x1400088ec  mul     ecx
0x1400088ee  mov     [rsi], rdi
0x1400088f1  shr     edx, 1
0x1400088f3  lea     eax, [rdx+rdx*2]
0x1400088f6  sub     ecx, eax
0x1400088f8  mov     [rsi+70h], cl
0x1400088fb  add     rbx, cs:PcgTimerUnits
0x140008902  cmp     cs:PcgDisableRecursionFix, r13d
0x140008909  jnz     loc_140008E56
0x14000890f  mov     eax, 1
0x140008914  cmp     [rbx+28h], eax
0x140008917  jnz     short loc_140008953
0x140008919  lea     rdx, [rsp+150h+NetBufferList]; LockHandle
0x14000891e  mov     rcx, rbx; SpinLock
0x140008921  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140008928  nop     dword ptr [rax+rax+00h]
0x14000892d  nop     dword ptr [rax]
0x140008930  mov     eax, [rbx+8]
0x140008933  test    eax, eax
0x140008935  jnz     short loc_140008930
0x140008937  mov     eax, [rbx+2Ch]
0x14000893a  test    al, 1
0x14000893c  jz      loc_140008E61
0x140008942  lea     rcx, [rsp+150h+NetBufferList]; LockHandle
0x140008947  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14000894e  nop     dword ptr [rax+rax+00h]
0x140008953  cmp     cs:PcgDisableRecursionFix, r13d
0x14000895a  jnz     short loc_14000895F
0x14000895c  dec     dword ptr [rbx+28h]
0x14000895f  mov     rcx, cs:PcgDelayQueue
0x140008966  shl     r14, 6
0x14000896a  add     rcx, r14
0x14000896d  add     dword ptr [rcx+10h], 0FFFFFFFFh
0x140008971  jnz     short loc_1400089C3
0x140008973  mov     rsi, [rcx]
0x140008976  xor     eax, eax
0x140008978  mov     qword ptr [rbp+50h+var_58.OldIrql], rax
0x14000897c  xorps   xmm0, xmm0
0x14000897f  mov     word ptr [rbp+50h+arg_10.OldIrql], ax
0x140008983  mov     [rbp+50h+arg_10.Flags], al
0x140008986  movups  xmmword ptr [rbp+50h+var_58.LockQueue.Next], xmm0
0x14000898a  mov     [rcx], r13
0x14000898d  mov     [rcx+8], r13
0x140008991  mov     rbx, [r12]
0x140008995  mov     [rbp+50h+var_90], eax
0x140008998  mov     rax, cs:QosgTimerTable
0x14000899f  movups  [rbp+50h+var_B0], xmm0
0x1400089a3  movups  [rbp+50h+var_A0], xmm0
0x1400089a7  mov     rdi, [rax]
0x1400089aa  add     rdi, r15
0x1400089ad  cmp     rbx, [rdi+8]
0x1400089b1  jnz     loc_140008C5F
0x1400089b7  mov     rbx, [rdi]
0x1400089ba  test    rsi, rsi
0x1400089bd  jnz     loc_140008EC7
0x1400089c3  cmp     [rbp+50h+arg_8], 0
0x1400089c7  jz      short loc_1400089DE
0x1400089c9  add     rsp, 118h
0x1400089d0  pop     r15
0x1400089d2  pop     r14
0x1400089d4  pop     r13
0x1400089d6  pop     r12
0x1400089d8  pop     rdi
0x1400089d9  pop     rsi
0x1400089da  pop     rbx
0x1400089db  pop     rbp
0x1400089dc  retn
0x1400089de  movzx   ecx, [rbp+50h+arg_18]; NewIrql
0x1400089e2  call    cs:__imp_KeLowerIrql
0x1400089e9  nop     dword ptr [rax+rax+00h]
0x1400089ee  jmp     short loc_1400089C9
0x1400089f0  mov     [rbp+50h+arg_8], 1
0x1400089f4  jmp     loc_14000861A
0x1400089f9  mov     rax, [rcx]
0x1400089fc  mov     [rcx], rsi
0x1400089ff  jmp     loc_1400087C6
0x140008a04  cmp     dword ptr [r14+10h], 3
0x140008a09  jz      loc_140008C26
0x140008a0f  mov     rax, [r14+0A0h]
0x140008a16  mov     [rsp+150h+P], rax
0x140008a1b  cmp     rdx, r9
0x140008a1e  jz      short loc_140008A96
0x140008a20  lea     rax, [rdx+60h]
0x140008a24  mov     qword ptr [rsp+150h+PerformanceFrequency], rdx
0x140008a29  mov     rcx, rax; SpinLock
0x140008a2c  mov     [rsp+150h+var_118], rax
0x140008a31  lea     rdx, [rbp+50h+LockHandle]; LockHandle
0x140008a35  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140008a3c  nop     dword ptr [rax+rax+00h]
0x140008a41  mov     rcx, [rsp+150h+var_118]
0x140008a46  mov     eax, [rcx+8]
0x140008a49  test    eax, eax
0x140008a4b  jnz     short loc_140008A46
0x140008a4d  mov     rcx, [rsp+150h+var_F0]
  ... truncated ...
```
