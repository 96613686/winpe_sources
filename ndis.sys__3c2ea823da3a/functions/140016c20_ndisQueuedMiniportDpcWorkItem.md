# ndisQueuedMiniportDpcWorkItem

- ea: `0x140016c20`
- end: `0x140017775`
- name: `ndisQueuedMiniportDpcWorkItem`
- size: `2901`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x140016c20`
- `0x140017780`
- `0x140017930`
- `0x14001cf50`
- `0x14001d350`
- `0x140020ce0`
- `0x1400230c0`
- `0x140025c70`
- `0x140026220`
- `0x140079490`
- `0x140083a40`
- `0x1400c4c7c`
- `0x1400e6160`
- `0x1400e6240`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x140017695`
- `ntoskrnl!KfRaiseIrql` at `0x140017695`
- `ntoskrnl!KeLowerIrql` at `0x140017725`
- `ntoskrnl!KeLowerIrql` at `0x140017725`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x1400e7d64`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x1400e7d64`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x1400e7da2`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x1400e7da2`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x140017682`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x140017682`
- `ntoskrnl!ExQueueWorkItem` at `0x1400176c7`
- `ntoskrnl!ExQueueWorkItem` at `0x1400176c7`
- `ntoskrnl!WmiGetClock` at `0x1400173c4`
- `ntoskrnl!WmiGetClock` at `0x1400176ef`
- `ntoskrnl!WmiGetClock` at `0x1400173c4`
- `ntoskrnl!WmiGetClock` at `0x1400176ef`
- `ntoskrnl!KeSetTimer` at `0x140017485`
- `ntoskrnl!KeSetTimer` at `0x140017485`
- `ntoskrnl!KeReleaseSemaphore` at `0x140017418`
- `ntoskrnl!KeReleaseSemaphore` at `0x140017418`
- `ntoskrnl!KeSetEvent` at `0x140016e70`
- `ntoskrnl!KeSetEvent` at `0x14001709d`
- `ntoskrnl!KeSetEvent` at `0x1400172b7`
- `ntoskrnl!KeSetEvent` at `0x1400175fd`
- `ntoskrnl!KeSetEvent` at `0x140016e70`
- `ntoskrnl!KeSetEvent` at `0x14001709d`
- `ntoskrnl!KeSetEvent` at `0x1400172b7`
- `ntoskrnl!KeSetEvent` at `0x1400175fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017749`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017749`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016fd4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400171b0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017554`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016fd4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400171b0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017554`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016ebc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001716c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017320`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016ebc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001716c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017320`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140016cdc`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400173fd`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001749d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140016cdc`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400173fd`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001749d`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140016cc8`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400171ef`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001726f`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140016cc8`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400171ef`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001726f`

## pseudocode

```c
void __fastcall ndisQueuedMiniportDpcWorkItem(__int64 a1)
{
  unsigned int Number; // r12d
  __int64 v3; // rax
  __int64 v4; // rsi
  char v5; // bp
  char v6; // bp
  ULONG v7; // r15d
  unsigned __int64 v8; // rdx
  char *v9; // r8
  struct _NDIS_MINIPORT_BLOCK *v10; // r14
  KSPIN_LOCK *v11; // r11
  void (__fastcall *v12)(__int64, _QWORD, __int64, __int64 *, _QWORD); // r10
  wchar_t *Buffer; // r13
  int PcwDatapathCycleMask; // edi
  unsigned int v15; // ebx
  unsigned int v16; // ecx
  int v17; // edi
  __int64 v18; // rcx
  unsigned __int64 v19; // rax
  __int64 v20; // rbp
  KIRQL v21; // al
  int v22; // edx
  ULONG_PTR v23; // r8
  KIRQL v24; // si
  __int64 v25; // r9
  unsigned __int8 k; // cl
  _BYTE *v27; // r10
  char v28; // al
  int v29; // edi
  int v30; // edx
  struct _KEVENT *v31; // rcx
  ULONG_PTR v32; // rdi
  unsigned int v33; // r9d
  int v34; // ecx
  struct _NDIS_REFCOUNT_STACK_BLOCK *j; // r14
  __int64 v36; // rdi
  int v37; // eax
  __int64 v38; // rdx
  __int64 v39; // rax
  KIRQL v40; // al
  __int64 v41; // rdx
  __int64 v42; // rcx
  KIRQL v43; // r13
  int v44; // eax
  __int64 v45; // r13
  int v46; // edx
  char *v47; // rbx
  __int64 *v48; // rax
  KIRQL v49; // al
  __int64 v50; // rdx
  ULONG_PTR v51; // r8
  KIRQL v52; // r13
  __int64 v53; // r8
  __int64 Clock; // rax
  LARGE_INTEGER v55; // rdx
  struct _KDPC *v56; // r8
  __int64 v57; // rcx
  unsigned __int8 i; // cl
  _BYTE *v59; // r9
  char v60; // al
  int v61; // esi
  int v62; // edx
  struct _KEVENT *v63; // rcx
  ULONG_PTR v64; // rsi
  unsigned int v65; // edx
  int v66; // ecx
  __int64 v67; // rax
  char v68; // [rsp+40h] [rbp-98h]
  KIRQL v69; // [rsp+41h] [rbp-97h]
  char v70; // [rsp+42h] [rbp-96h]
  struct _PROCESSOR_NUMBER ProcNumber[2]; // [rsp+48h] [rbp-90h] BYREF
  __int64 v72; // [rsp+50h] [rbp-88h] BYREF
  __int64 v73; // [rsp+58h] [rbp-80h]
  __int64 v74; // [rsp+60h] [rbp-78h]
  PKSPIN_LOCK SpinLock; // [rsp+68h] [rbp-70h]
  __int64 v76; // [rsp+70h] [rbp-68h]
  char v77[8]; // [rsp+78h] [rbp-60h]
  __int64 v78; // [rsp+80h] [rbp-58h]
  struct _GROUP_AFFINITY Affinity; // [rsp+88h] [rbp-50h] BYREF
  struct _GROUP_AFFINITY PreviousAffinity; // [rsp+98h] [rbp-40h] BYREF

  v69 = 0;
  PreviousAffinity = 0;
  Affinity = 0;
  Number = KeGetPcr()->Prcb.Number;
  v3 = *(_QWORD *)(a1 + 32);
  v4 = *(_QWORD *)(a1 + 40);
  v5 = *(_BYTE *)(a1 + 68);
  ++ndisWorkitemDpcs;
  v6 = v5 & 2;
  v7 = *(_DWORD *)(a1 + 64);
  v78 = v3;
  *(_QWORD *)v77 = *(_QWORD *)(v4 + 96);
  v73 = *(_QWORD *)(a1 + 48);
  v74 = *(_QWORD *)(a1 + 56);
  if ( Number != v7 )
  {
    ProcNumber[0] = 0;
    KeGetProcessorNumberFromIndex(v7, ProcNumber);
    Affinity.Group = ProcNumber[0].Group;
    Affinity.Mask = 1LL << ProcNumber[0].Number;
    KeSetSystemGroupAffinityThread(&Affinity, &PreviousAffinity);
  }
  if ( !v6 )
    v69 = KfRaiseIrql(2u);
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(a1 + 72));
  *(_DWORD *)(a1 + 68) &= ~1u;
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a1 + 72));
  v10 = *(struct _NDIS_MINIPORT_BLOCK **)(v4 + 96);
  v11 = *(KSPIN_LOCK **)(v4 + 24);
  v12 = *(void (__fastcall **)(__int64, _QWORD, __int64, __int64 *, _QWORD))(v4 + 184);
  v72 = 0;
  SpinLock = v11;
  *(_QWORD *)&ProcNumber[0].Group = v12;
  if ( v10->PcwDatapathEventMask || (Buffer = 0, LOBYTE(PcwDatapathCycleMask) = 0, v10->PcwDatapathCycleMask) )
  {
    Buffer = v10->Reserved4.Buffer;
    PcwDatapathCycleMask = v10->PcwDatapathCycleMask;
    if ( !Buffer )
      Buffer = v10->Reserved4.Buffer;
  }
  if ( HIBYTE(dword_14011CF90) )
  {
    v68 = 1;
    ndisTraceDpcStart(v10, 1u);
    Clock = WmiGetClock(0, 0, v53);
    v12 = *(void (__fastcall **)(__int64, _QWORD, __int64, __int64 *, _QWORD))&ProcNumber[0].Group;
    v11 = SpinLock;
    v76 = Clock;
  }
  else
  {
    v76 = 0;
    v68 = 0;
  }
  if ( *(_BYTE *)(v4 + 4) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 104), 0xFFFFFFFF) == 1 )
LABEL_25:
      KeSetEvent((PRKEVENT)(v4 + 128), 0, 0);
  }
  else
  {
    v15 = -1;
    if ( byte_14011B401 )
    {
      if ( dword_14011B40C )
      {
        v16 = dword_14011B404;
      }
      else
      {
        v16 = *((_DWORD *)&ndisPeriodicReceivesNblCounts
              + *(unsigned int *)((char *)v10->PeriodicReceivesNblCountIndex + (KeGetPcr()->Prcb.Number << 12)));
        if ( dword_14011B404 < v16 )
          v16 = dword_14011B404;
      }
    }
    else
    {
      v16 = -1;
    }
    LODWORD(v72) = v16;
    v17 = PcwDatapathCycleMask & 1;
    if ( v17 )
    {
      v15 = KeGetPcr()->Prcb.Number;
      *(_QWORD *)((char *)Buffer + ndisPcwPerCpuDataStride * v15 + ndisPcwOffsetToPerCpuData + 304) = __rdtsc();
    }
    v18 = *(_QWORD *)(v4 + 8);
    if ( *(_BYTE *)(v4 + 193) == 1 )
      v12(v18, (unsigned int)v73, v74, &v72, 0);
    else
      ((void (__fastcall *)(__int64, __int64, __int64 *, _QWORD))v11)(v18, v74, &v72, 0);
    if ( v17 )
    {
      if ( v15 == -1 )
        v15 = KeGetPcr()->Prcb.Number;
      v9 = (char *)Buffer + ndisPcwPerCpuDataStride * v15 + ndisPcwOffsetToPerCpuData;
      v19 = __rdtsc();
      v8 = (unsigned __int64)HIDWORD(v19) << 32;
      *((_QWORD *)v9 + 13) += (v8 | (unsigned int)v19) - *((_QWORD *)v9 + 38);
      *((_QWORD *)v9 + 38) = 0;
    }
    if ( (v72 & 0x100000000LL) != 0 )
    {
      v36 = *(_QWORD *)(v4 + 96);
      v70 = byte_14011B401;
      ProcNumber[0] = (struct _PROCESSOR_NUMBER)KeGetPcr()->Prcb.Number;
      v37 = *(_DWORD *)(v36 + 48);
      if ( v37 || *(_DWORD *)(v36 + 80) )
      {
        v38 = *(_QWORD *)(v36 + 40);
        if ( !v38 )
          v38 = *(_QWORD *)(v36 + 40);
        if ( (v37 & 0x800000) != 0 )
        {
          v39 = v38 + ndisPcwPerCpuDataStride * KeGetPcr()->Prcb.Number;
          ++*(_QWORD *)(ndisPcwOffsetToPerCpuData + v39 + 288);
        }
      }
      v40 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v36 + 4432));
      v42 = *(_QWORD *)(v36 + 4896);
      v43 = v40;
      if ( v42 )
      {
        LOBYTE(v41) = 77;
        NdisReferenceWithTag(v42, v41);
      }
      ++*(_DWORD *)(v36 + 4440);
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v41) = 4;
        WPP_RECORDER_SF_qL(
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          v41,
          20,
          13,
          (struct _GUID *)&WPP_5c1c115ae3d7308ea4dc20929af9c88a_Traceguids,
          v36,
          *(_DWORD *)(v36 + 4440));
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(v36 + 4432), v43);
      v44 = 0;
      if ( *(_BYTE *)(v4 + 193) )
        v44 = v73;
      v45 = *(_QWORD *)(v4 + 216) + 80LL * (*(_DWORD *)ProcNumber + ndisMaxNumberOfProcessors * v44);
      SpinLock = (PKSPIN_LOCK)(v45 + 72);
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v45 + 72));
      if ( (*(_DWORD *)(v45 + 68) & 1) != 0 )
      {
        _InterlockedDecrement((volatile signed __int32 *)(v4 + 104));
        if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v46) = 4;
          WPP_RECORDER_SF_q(
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            v46,
            20,
            25,
            (struct _GUID *)&WPP_91e24223ea6635c7ede0c9cfb5715ff6_Traceguids,
            v36);
        }
        v49 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v36 + 4432));
        v51 = *(_QWORD *)(v36 + 4896);
        v52 = v49;
        if ( (v51 & 0xFFFFFFFFFFFFFFFCuLL) != 0 || v51 == 1 )
        {
          if ( v51 == 1 )
            ndisBugCheckEx(0x1Eu, 3u, 1u, 0);
          if ( *(_BYTE *)(v51 + 2) <= 0x4Du )
            ndisBugCheckEx(0x1Eu, 2u, v51, 0x4Du);
          if ( *(_BYTE *)(v51 + 1) )
          {
            if ( *(_BYTE *)(v51 + 1) == 1 )
            {
              v64 = v51 + 4936;
              v65 = *(_DWORD *)(v51 + 4992);
              v66 = (unsigned __int16)v65 >> 1;
              if ( v65 >> 17 < 0x3FFE && v66 == (v65 >> 17) + 1 )
              {
                ndisFreeRefCountStackChain((struct _NDIS_REFCOUNT_STACK_BLOCK *)(v51 + 4936));
                *(_DWORD *)(v64 + 56) &= 0x10001u;
              }
              else
              {
                if ( v66 == 0 && (v65 & 1) == 0 )
                  ndisReportRefcountImbalance(*(_QWORD *)(v36 + 4896), 0x4Du);
                ndisReferenceWithTagStackTrace((struct _NDIS_REFCOUNT_WITH_STACK *)(v51 + 4936), 0);
              }
            }
          }
          else
          {
            v50 = *(_QWORD *)(v51 + 8);
            if ( v50 )
            {
              for ( i = 0; i < *(_BYTE *)(v51 + 3); ++i )
              {
                v59 = (_BYTE *)(v50 + 2LL * i);
                if ( *v59 == 77 )
                {
                  v60 = v59[1];
                  if ( v60 )
                  {
                    v59[1] = v60 - 1;
                    goto LABEL_112;
                  }
                }
              }
            }
            if ( !_bittestandreset((signed __int32 *)(v51 + 24), 0xDu) )
              ndisReportRefcountImbalance(v51, 0x4Du);
          }
        }
LABEL_112:
        v61 = --*(_DWORD *)(v36 + 4440);
        if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v50) = 4;
          WPP_RECORDER_SF_qL(
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            v50,
            20,
            14,
            (struct _GUID *)&WPP_5c1c115ae3d7308ea4dc20929af9c88a_Traceguids,
            v36,
            *(_DWORD *)(v36 + 4440));
        }
        KeReleaseSpinLock((PKSPIN_LOCK)(v36 + 4432), v52);
        if ( !v61 )
        {
          v63 = *(struct _KEVENT **)(v36 + 1608);
          if ( v63 )
            KeSetEvent(v63, 0, 0);
        }
        if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v62) = 4;
          WPP_RECORDER_SF_q(
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            v62,
            20,
            26,
            (struct _GUID *)&WPP_91e24223ea6635c7ede0c9cfb5715ff6_Traceguids,
            v36);
        }
      }
      else
      {
        *(_QWORD *)(v45 + 32) = v78;
        *(_QWORD *)(v45 + 48) = v73;
        *(_QWORD *)(v45 + 56) = v74;
        *(struct _PROCESSOR_NUMBER *)(v45 + 64) = ProcNumber[0];
        *(_QWORD *)(v45 + 40) = v4;
        *(_DWORD *)(v45 + 68) = 1;
        if ( v70 )
        {
          if ( HIBYTE(word_14011CF94) )
            ndisTraceQueueWorkItem();
          *(_DWORD *)(v45 + 68) |= 2u;
          v47 = (char *)qword_14011B440 + 64 * (unsigned __int64)KeGetPcr()->Prcb.Number;
          KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)v47 + 2);
          v48 = (__int64 *)*((_QWORD *)v47 + 1);
          if ( (char *)*v48 != v47 )
            __fastfail(3u);
          *(_QWORD *)v45 = v47;
          *(_QWORD *)(v45 + 8) = v48;
          *v48 = v45;
          *((_QWORD *)v47 + 1) = v45;
          ++*((_DWORD *)v47 + 6);
          KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)v47 + 2);
          KeReleaseSemaphore((PRKSEMAPHORE)v47 + 1, 0, 1, 0);
          if ( !_InterlockedExchange((volatile __int32 *)qword_14011B438 + KeGetPcr()->Prcb.Number, 1) )
          {
            v55.QuadPart = -1;
            v56 = (struct _KDPC *)((char *)qword_14011B430 + 128 * (unsigned __int64)KeGetPcr()->Prcb.Number + 64);
            HIDWORD(v57) = DueTime.HighPart;
            if ( DueTime.QuadPart )
              v55 = DueTime;
            LODWORD(v57) = KeGetPcr()->Prcb.Number;
            KeSetTimer((PKTIMER)qword_14011B430 + 2 * v57, v55, v56);
          }
        }
        else
        {
          ExQueueWorkItem((PWORK_QUEUE_ITEM)v45, CustomPriorityWorkQueue|RealTimeWorkQueue|0x8);
        }
      }
      KeReleaseSpinLockFromDpcLevel(SpinLock);
    }
    else if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 104), 0xFFFFFFFF) == 1 && *(_BYTE *)(v4 + 4) )
    {
      goto LABEL_25;
    }
  }
  if ( v68 )
  {
    v67 = WmiGetClock(0, 0, v9);
    ndisTraceDpcEnd(v10, 1u, v67 - v76);
  }
  if ( !v6 && v69 != 2 )
    KeLowerIrql(v69);
  if ( Number != v7 )
    KeRevertToUserGroupAffinityThread(&PreviousAffinity);
  v20 = *(_QWORD *)v77;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v8) = 4;
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v8,
      20,
      25,
      (struct _GUID *)&WPP_91e24223ea6635c7ede0c9cfb5715ff6_Traceguids,
      v77[0]);
  }
  v21 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v20 + 4432));
  v23 = *(_QWORD *)(v20 + 4896);
  v24 = v21;
  if ( (v23 & 0xFFFFFFFFFFFFFFFCuLL) == 0 && v23 != 1 )
    goto LABEL_51;
  if ( v23 == 1 )
    ndisBugCheckEx(0x1Eu, 3u, 1u, 0);
  if ( *(_BYTE *)(v23 + 2) <= 0x4Du )
    ndisBugCheckEx(0x1Eu, 2u, v23, 0x4Du);
  if ( *(_BYTE *)(v23 + 1) )
  {
    if ( *(_BYTE *)(v23 + 1) != 1 )
      goto LABEL_51;
    v32 = v23 + 4936;
    v33 = *(_DWORD *)(v23 + 4992);
    v34 = (unsigned __int16)v33 >> 1;
    if ( v33 >> 17 < 0x3FFE && v34 == (v33 >> 17) + 1 )
    {
      for ( j = *(struct _NDIS_REFCOUNT_STACK_BLOCK **)v32; *(_QWORD *)v32; j = *(struct _NDIS_REFCOUNT_STACK_BLOCK **)v32 )
      {
        *(_QWORD *)v32 = j->Next;
        ndisFreeRefCountStacksInBlock(j);
        ExFreePoolWithTag(j, 0);
      }
      ndisFreeRefCountStacksInBlock((struct _NDIS_REFCOUNT_STACK_BLOCK *)v32);
      *(_DWORD *)(v32 + 56) &= 0x10001u;
      goto LABEL_51;
    }
    if ( v34 != 0 || (v33 & 1) != 0 )
    {
      ndisReferenceWithTagStackTrace((struct _NDIS_REFCOUNT_WITH_STACK *)(v23 + 4936), 0);
      goto LABEL_51;
    }
LABEL_44:
    ndisReportRefcountImbalance(v23, 0x4Du);
  }
  v25 = *(_QWORD *)(v23 + 8);
  if ( !v25 )
  {
LABEL_43:
    if ( _bittestandreset((signed __int32 *)(v23 + 24), 0xDu) )
      goto LABEL_51;
    goto LABEL_44;
  }
  v22 = *(unsigned __int8 *)(v23 + 3);
  for ( k = 0; ; ++k )
  {
    if ( k >= (unsigned __int8)v22 )
      goto LABEL_43;
    v27 = (_BYTE *)(v25 + 2LL * k);
    if ( *v27 == 77 )
    {
      v28 = v27[1];
      if ( v28 )
        break;
    }
  }
  v27[1] = v28 - 1;
LABEL_51:
  v29 = --*(_DWORD *)(v20 + 4440);
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v22) = 4;
    WPP_RECORDER_SF_qL(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v22,
      20,
      14,
      (struct _GUID *)&WPP_5c1c115ae3d7308ea4dc20929af9c88a_Traceguids,
      v20,
      *(_DWORD *)(v20 + 4440));
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(v20 + 4432), v24);
  if ( !v29 )
  {
    v31 = *(struct _KEVENT **)(v20 + 1608);
    if ( v31 )
      KeSetEvent(v31, 0, 0);
  }
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v30) = 4;
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v30,
      20,
      26,
      (struct _GUID *)&WPP_91e24223ea6635c7ede0c9cfb5715ff6_Traceguids,
      v20);
  }
}

```

## disassembly

```asm
0x140016c20  mov     r11, rsp
0x140016c23  mov     [r11+18h], rbx
0x140016c27  mov     [r11+20h], rbp
0x140016c2b  push    rsi
0x140016c2c  push    rdi
0x140016c2d  push    r12
0x140016c2f  push    r14
0x140016c31  push    r15
0x140016c33  sub     rsp, 0B0h
0x140016c3a  mov     rax, cs:__security_cookie
0x140016c41  xor     rax, rsp
0x140016c44  mov     [rsp+0D8h+var_30], rax
0x140016c4c  xorps   xmm0, xmm0
0x140016c4f  mov     [rsp+0D8h+var_97], 0
0x140016c54  movups  xmmword ptr [r11-40h], xmm0
0x140016c59  mov     rdi, rcx
0x140016c5c  xorps   xmm1, xmm1
0x140016c5f  movups  xmmword ptr [r11-50h], xmm1
0x140016c64  mov     r12d, gs:1A4h
0x140016c6d  mov     rax, [rcx+20h]
0x140016c71  mov     rsi, [rcx+28h]
0x140016c75  movzx   ebp, byte ptr [rcx+44h]
0x140016c79  inc     cs:?ndisWorkitemDpcs@@3KA; ulong ndisWorkitemDpcs
0x140016c7f  and     bpl, 2
0x140016c83  mov     r15d, [rcx+40h]
0x140016c87  mov     [rsp+0D8h+var_58], rax
0x140016c8f  mov     rax, [rsi+60h]
0x140016c93  mov     qword ptr [rsp+0D8h+var_60], rax
0x140016c98  mov     rax, [rcx+30h]
0x140016c9c  mov     [rsp+0D8h+var_80], rax
0x140016ca1  mov     rax, [rcx+38h]
0x140016ca5  mov     [rsp+0D8h+var_78], rax
0x140016caa  cmp     r12d, r15d
0x140016cad  jnz     loc_1400E7D54
0x140016cb3  test    bpl, bpl
0x140016cb6  jz      loc_140017693
0x140016cbc  lea     rcx, [rdi+48h]; SpinLock
0x140016cc0  mov     [rsp+0D8h+arg_8], r13
0x140016cc8  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140016ccf  nop     dword ptr [rax+rax+00h]
0x140016cd4  and     dword ptr [rdi+44h], 0FFFFFFFEh
0x140016cd8  lea     rcx, [rdi+48h]; SpinLock
0x140016cdc  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140016ce3  nop     dword ptr [rax+rax+00h]
0x140016ce8  mov     r14, [rsi+60h]
0x140016cec  xor     r9d, r9d
0x140016cef  mov     r11, [rsi+18h]
0x140016cf3  mov     r10, [rsi+0B8h]
0x140016cfa  mov     [rsp+0D8h+var_88], r9
0x140016cff  mov     [rsp+0D8h+SpinLock], r11
0x140016d04  mov     qword ptr [rsp+0D8h+ProcNumber.Group], r10
0x140016d09  cmp     [r14+30h], r9d
0x140016d0d  jnz     loc_140016F0D
0x140016d13  mov     r13d, r9d
0x140016d16  mov     edi, r9d
0x140016d19  cmp     [r14+50h], r9d
0x140016d1d  jnz     loc_140016F0D
0x140016d23  cmp     byte ptr cs:dword_14011CF90+3, r9b
0x140016d2a  jnz     loc_1400173AE
0x140016d30  mov     [rsp+0D8h+var_68], r9
0x140016d35  mov     [rsp+0D8h+var_98], r9b
0x140016d3a  movzx   eax, byte ptr [rsi+4]
0x140016d3e  lea     rbx, WPP_RECORDER_INITIALIZED
0x140016d45  test    al, al
0x140016d47  jnz     loc_140017296
0x140016d4d  cmp     cs:byte_14011B401, al
0x140016d53  mov     ebx, 0FFFFFFFFh
0x140016d58  jz      loc_14001728F
0x140016d5e  cmp     cs:dword_14011B40C, 0
0x140016d65  jnz     loc_1400176AA
0x140016d6b  mov     eax, gs:1A4h
0x140016d73  shl     eax, 0Ch
0x140016d76  mov     ecx, eax
0x140016d78  mov     rax, [r14+0CE0h]
0x140016d7f  mov     edx, [rcx+rax]
0x140016d82  lea     rcx, ?ndisPeriodicReceivesNblCounts@@3PAKA; ulong near * ndisPeriodicReceivesNblCounts
0x140016d89  mov     ecx, [rcx+rdx*4]
0x140016d8c  cmp     cs:dword_14011B404, ecx
0x140016d92  cmovb   ecx, cs:dword_14011B404
0x140016d99  mov     dword ptr [rsp+0D8h+var_88], ecx
0x140016d9d  and     edi, 1
0x140016da0  jz      short loc_140016DCE
0x140016da2  mov     ebx, gs:1A4h
0x140016daa  rdtsc
0x140016dac  mov     r8d, cs:?ndisPcwOffsetToPerCpuData@@3KA; ulong ndisPcwOffsetToPerCpuData
0x140016db3  mov     ecx, ebx
0x140016db5  imul    ecx, cs:?ndisPcwPerCpuDataStride@@3KA; ulong ndisPcwPerCpuDataStride
0x140016dbc  shl     rdx, 20h
0x140016dc0  or      rax, rdx
0x140016dc3  add     rcx, r13
0x140016dc6  mov     [r8+rcx+130h], rax
0x140016dce  cmp     byte ptr [rsi+0C1h], 1
0x140016dd5  mov     rcx, [rsi+8]
0x140016dd9  jnz     loc_1400172C8
0x140016ddf  mov     edx, dword ptr [rsp+0D8h+var_80]
0x140016de3  mov     rax, r10
0x140016de6  mov     r8, [rsp+0D8h+var_78]
0x140016deb  mov     [rsp+0D8h+var_B8], r9
0x140016df0  lea     r9, [rsp+0D8h+var_88]
0x140016df5  call    _guard_dispatch_icall
0x140016dfa  test    edi, edi
0x140016dfc  jz      short loc_140016E40
0x140016dfe  cmp     ebx, 0FFFFFFFFh
0x140016e01  jnz     short loc_140016E0B
0x140016e03  mov     ebx, gs:1A4h
0x140016e0b  imul    ebx, cs:?ndisPcwPerCpuDataStride@@3KA; ulong ndisPcwPerCpuDataStride
0x140016e12  mov     r8d, cs:?ndisPcwOffsetToPerCpuData@@3KA; ulong ndisPcwOffsetToPerCpuData
0x140016e19  mov     eax, ebx
0x140016e1b  add     rax, r13
0x140016e1e  add     r8, rax
0x140016e21  rdtsc
0x140016e23  shl     rdx, 20h
0x140016e27  or      rax, rdx
0x140016e2a  sub     rax, [r8+130h]
0x140016e31  add     [r8+68h], rax
0x140016e35  mov     qword ptr [r8+130h], 0
0x140016e40  test    byte ptr [rsp+0D8h+var_88+4], 1
0x140016e45  jnz     loc_140017108
0x140016e4b  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140016e52  lock xadd [rsi+68h], eax
0x140016e57  cmp     eax, 1
0x140016e5a  jnz     short loc_140016E7C
0x140016e5c  movzx   eax, byte ptr [rsi+4]
0x140016e60  test    al, al
0x140016e62  jz      short loc_140016E7C
0x140016e64  lea     rcx, [rsi+80h]; Event
0x140016e6b  xor     r8d, r8d; Wait
0x140016e6e  xor     edx, edx; Increment
0x140016e70  call    cs:__imp_KeSetEvent
0x140016e77  nop     dword ptr [rax+rax+00h]
0x140016e7c  lea     rbx, WPP_RECORDER_INITIALIZED
0x140016e83  cmp     [rsp+0D8h+var_98], 0
0x140016e88  jnz     loc_1400176EB
0x140016e8e  test    bpl, bpl
0x140016e91  jz      loc_140017715
0x140016e97  cmp     r12d, r15d
0x140016e9a  jnz     loc_14001767A
0x140016ea0  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140016ea7  lea     r15, WPP_91e24223ea6635c7ede0c9cfb5715ff6_Traceguids
0x140016eae  mov     rbp, qword ptr [rsp+0D8h+var_60]
0x140016eb3  jnz     short loc_140016F27
0x140016eb5  lea     rcx, [rbp+1150h]; SpinLock
0x140016ebc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140016ec3  nop     dword ptr [rax+rax+00h]
0x140016ec8  mov     r8, [rbp+1320h]; BugCheckParameter3
0x140016ecf  movzx   esi, al
0x140016ed2  test    r8, 0FFFFFFFFFFFFFFFCh
0x140016ed9  jz      short loc_140016F02
0x140016edb  cmp     r8, 1
0x140016edf  jz      loc_140017762
0x140016ee5  cmp     byte ptr [r8+2], 4Dh ; 'M'
0x140016eea  ja      short loc_140016F54
0x140016eec  mov     edx, 2; BugCheckParameter2
0x140016ef1  mov     ecx, 1Eh; BugCheckParameter1
0x140016ef6  mov     r9d, 4Dh ; 'M'; BugCheckParameter4
0x140016efc  call    ?ndisBugCheckEx@@YAX_K000@Z; ndisBugCheckEx(unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64)
0x140016f02  cmp     r8, 1
0x140016f06  jz      short loc_140016EDB
0x140016f08  jmp     loc_140016FA9
0x140016f0d  mov     r13, [r14+28h]
0x140016f11  mov     edi, [r14+50h]
0x140016f15  test    r13, r13
0x140016f18  jnz     loc_140016D23
0x140016f1e  mov     r13, [r14+28h]
0x140016f22  jmp     loc_140016D23
0x140016f27  mov     rcx, cs:WPP_GLOBAL_Control
0x140016f2e  mov     r9d, 19h; int
0x140016f34  mov     qword ptr [rsp+0D8h+var_B0], rbp; char
0x140016f39  mov     r8d, 14h; int
0x140016f3f  mov     dl, 4; int
0x140016f41  mov     [rsp+0D8h+var_B8], r15; struct _GUID *
0x140016f46  mov     rcx, [rcx+40h]; int
0x140016f4a  call    WPP_RECORDER_SF_q
0x140016f4f  jmp     loc_140016EB5
0x140016f54  movzx   ecx, byte ptr [r8+1]
0x140016f59  test    ecx, ecx
0x140016f5b  jnz     loc_1400170AE
0x140016f61  mov     r9, [r8+8]
0x140016f65  test    r9, r9
0x140016f68  jnz     short loc_140016F7D
0x140016f6a  btr     dword ptr [r8+18h], 0Dh
0x140016f70  jb      short loc_140016FA9
0x140016f72  mov     dl, 4Dh ; 'M'; unsigned __int8
0x140016f74  mov     rcx, r8; BugCheckParameter3
0x140016f77  call    ?ndisReportRefcountImbalance@@YAXPEAU_NDIS_REFCOUNT_BLOCK@@E@Z; ndisReportRefcountImbalance(_NDIS_REFCOUNT_BLOCK *,uchar)
0x140016f7d  movzx   edx, byte ptr [r8+3]
0x140016f82  xor     cl, cl
0x140016f84  cmp     cl, dl
0x140016f86  jnb     short loc_140016F6A
0x140016f88  movzx   eax, cl
0x140016f8b  cmp     byte ptr [r9+rax*2], 4Dh ; 'M'
0x140016f90  lea     r10, [r9+rax*2]
0x140016f94  jz      short loc_140016F9A
0x140016f96  inc     cl
0x140016f98  jmp     short loc_140016F84
0x140016f9a  movzx   eax, byte ptr [r10+1]
0x140016f9f  test    al, al
0x140016fa1  jz      short loc_140016F96
0x140016fa3  dec     al
0x140016fa5  mov     [r10+1], al
0x140016fa9  dec     dword ptr [rbp+1158h]
0x140016faf  mov     edi, [rbp+1158h]
0x140016fb5  lea     r14, WPP_RECORDER_INITIALIZED
0x140016fbc  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140016fc3  jnz     loc_140017050
0x140016fc9  movzx   edx, sil; NewIrql
0x140016fcd  lea     rcx, [rbp+1150h]; SpinLock
0x140016fd4  call    cs:__imp_KeReleaseSpinLock
0x140016fdb  nop     dword ptr [rax+rax+00h]
0x140016fe0  test    edi, edi
0x140016fe2  jz      loc_140017088
0x140016fe8  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140016fef  jnz     short loc_140017026
0x140016ff1  mov     r13, [rsp+0D8h+arg_8]
0x140016ff9  mov     rcx, [rsp+0D8h+var_30]
0x140017001  xor     rcx, rsp; StackCookie
0x140017004  call    __security_check_cookie
0x140017009  lea     r11, [rsp+0D8h+var_28]
0x140017011  mov     rbx, [r11+40h]
0x140017015  mov     rbp, [r11+48h]
0x140017019  mov     rsp, r11
0x14001701c  pop     r15
0x14001701e  pop     r14
0x140017020  pop     r12
0x140017022  pop     rdi
0x140017023  pop     rsi
0x140017024  retn
0x140017026  mov     rcx, cs:WPP_GLOBAL_Control
0x14001702d  mov     r9d, 1Ah; int
0x140017033  mov     qword ptr [rsp+0D8h+var_B0], rbp; char
0x140017038  mov     r8d, 14h; int
0x14001703e  mov     dl, 4; int
0x140017040  mov     [rsp+0D8h+var_B8], r15; struct _GUID *
0x140017045  mov     rcx, [rcx+40h]; int
0x140017049  call    WPP_RECORDER_SF_q
0x14001704e  jmp     short loc_140016FF1
0x140017050  mov     rcx, cs:WPP_GLOBAL_Control
0x140017057  lea     rax, WPP_5c1c115ae3d7308ea4dc20929af9c88a_Traceguids
0x14001705e  mov     dword ptr [rsp+0D8h+var_A8], edi; char
0x140017062  mov     r9d, 0Eh; int
0x140017068  mov     qword ptr [rsp+0D8h+var_B0], rbp; char
0x14001706d  mov     r8d, 14h; int
0x140017073  mov     dl, 4; int
0x140017075  mov     [rsp+0D8h+var_B8], rax; struct _GUID *
0x14001707a  mov     rcx, [rcx+40h]; int
0x14001707e  call    WPP_RECORDER_SF_qL
0x140017083  jmp     loc_140016FC9
0x140017088  mov     rcx, [rbp+648h]; Event
0x14001708f  test    rcx, rcx
0x140017092  jz      loc_140016FE8
0x140017098  xor     r8d, r8d; Wait
0x14001709b  xor     edx, edx; Increment
0x14001709d  call    cs:__imp_KeSetEvent
0x1400170a4  nop     dword ptr [rax+rax+00h]
0x1400170a9  jmp     loc_140016FE8
0x1400170ae  cmp     ecx, 1
0x1400170b1  jnz     loc_140016FA9
0x1400170b7  lea     rdi, [r8+1348h]
0x1400170be  mov     r9d, [rdi+38h]
0x1400170c2  mov     ecx, r9d
0x1400170c5  shr     ecx, 1
0x1400170c7  mov     eax, r9d
0x1400170ca  and     ecx, 7FFFh
0x1400170d0  shr     eax, 11h
0x1400170d3  cmp     eax, 3FFEh
0x1400170d8  jnb     loc_1400172E2
0x1400170de  inc     eax
0x1400170e0  cmp     ecx, eax
0x1400170e2  jnz     loc_1400172E2
0x1400170e8  mov     r14, [rdi]
0x1400170eb  test    r14, r14
0x1400170ee  jnz     loc_140017736
0x1400170f4  mov     rcx, rdi; struct _NDIS_REFCOUNT_STACK_BLOCK *
0x1400170f7  call    ?ndisFreeRefCountStacksInBlock@@YAXPEAU_NDIS_REFCOUNT_STACK_BLOCK@@@Z; ndisFreeRefCountStacksInBlock(_NDIS_REFCOUNT_STACK_BLOCK *)
0x1400170fc  and     dword ptr [rdi+38h], 10001h
0x140017103  jmp     loc_140016FA9
0x140017108  movzx   eax, cs:byte_14011B401
0x14001710f  mov     rdi, [rsi+60h]
0x140017113  mov     [rsp+0D8h+var_96], al
0x140017117  mov     eax, gs:1A4h
0x14001711f  mov     dword ptr [rsp+0D8h+ProcNumber.Group], eax
0x140017123  mov     eax, [rdi+30h]
0x140017126  test    eax, eax
0x140017128  jnz     short loc_14001712F
0x14001712a  cmp     [rdi+50h], eax
0x14001712d  jz      short loc_140017162
0x14001712f  mov     rdx, [rdi+28h]
0x140017133  test    rdx, rdx
0x140017136  jnz     short loc_14001713C
0x140017138  mov     rdx, [rdi+28h]
0x14001713c  bt      eax, 17h
0x140017140  jnb     short loc_140017162
0x140017142  mov     eax, gs:1A4h
0x14001714a  imul    eax, cs:?ndisPcwPerCpuDataStride@@3KA; ulong ndisPcwPerCpuDataStride
0x140017151  mov     ecx, cs:?ndisPcwOffsetToPerCpuData@@3KA; ulong ndisPcwOffsetToPerCpuData
0x140017157  add     rax, rdx
0x14001715a  inc     qword ptr [rcx+rax+120h]
0x140017162  lea     rbx, [rdi+1150h]
0x140017169  mov     rcx, rbx; SpinLock
0x14001716c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
  ... truncated ...
```
