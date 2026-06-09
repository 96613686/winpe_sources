# ndisQueuedMiniportDpcWorkItem

- ea: `0x14000acc0`
- end: `0x14000b815`
- name: `ndisQueuedMiniportDpcWorkItem`
- size: `2901`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x14000acc0`
- `0x14000b820`
- `0x14000b9d0`
- `0x1400110b0`
- `0x1400114b0`
- `0x140014e40`
- `0x140017220`
- `0x140019dd0`
- `0x14001a380`
- `0x14007eb60`
- `0x140088cc0`
- `0x1400c9e2c`
- `0x1400eb380`
- `0x1400eb460`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x14000b7c5`
- `ntoskrnl!KeLowerIrql` at `0x14000b7c5`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x1400ecbd8`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x1400ecbd8`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x1400ecc16`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x1400ecc16`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x14000b722`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x14000b722`
- `ntoskrnl!ExQueueWorkItem` at `0x14000b767`
- `ntoskrnl!ExQueueWorkItem` at `0x14000b767`
- `ntoskrnl!KfRaiseIrql` at `0x14000b735`
- `ntoskrnl!KfRaiseIrql` at `0x14000b735`
- `ntoskrnl!KeSetTimer` at `0x14000b525`
- `ntoskrnl!KeSetTimer` at `0x14000b525`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000b4b8`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000b4b8`
- `ntoskrnl!KeSetEvent` at `0x14000af10`
- `ntoskrnl!KeSetEvent` at `0x14000b13d`
- `ntoskrnl!KeSetEvent` at `0x14000b357`
- `ntoskrnl!KeSetEvent` at `0x14000b69d`
- `ntoskrnl!KeSetEvent` at `0x14000af10`
- `ntoskrnl!KeSetEvent` at `0x14000b13d`
- `ntoskrnl!KeSetEvent` at `0x14000b357`
- `ntoskrnl!KeSetEvent` at `0x14000b69d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b7e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b7e9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b074`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b250`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b5f4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b074`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b250`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b5f4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000af5c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b20c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b3c0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000af5c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b20c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b3c0`
- `ntoskrnl!WmiGetClock` at `0x14000b464`
- `ntoskrnl!WmiGetClock` at `0x14000b78f`
- `ntoskrnl!WmiGetClock` at `0x14000b464`
- `ntoskrnl!WmiGetClock` at `0x14000b78f`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000ad68`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000b28f`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000b30f`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000ad68`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000b28f`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000b30f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000ad7c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000b49d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000b53d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000ad7c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000b49d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000b53d`

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
  if ( HIBYTE(dword_140122F90) )
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
    if ( byte_140121401 )
    {
      if ( dword_14012140C )
      {
        v16 = dword_140121404;
      }
      else
      {
        v16 = *((_DWORD *)&ndisPeriodicReceivesNblCounts
              + *(unsigned int *)((char *)v10->PeriodicReceivesNblCountIndex + (KeGetPcr()->Prcb.Number << 12)));
        if ( dword_140121404 < v16 )
          v16 = dword_140121404;
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
      v70 = byte_140121401;
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
          if ( HIBYTE(word_140122F94) )
            ndisTraceQueueWorkItem();
          *(_DWORD *)(v45 + 68) |= 2u;
          v47 = (char *)qword_140121440 + 64 * (unsigned __int64)KeGetPcr()->Prcb.Number;
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
          if ( !_InterlockedExchange((volatile __int32 *)qword_140121438 + KeGetPcr()->Prcb.Number, 1) )
          {
            v55.QuadPart = -1;
            v56 = (struct _KDPC *)((char *)qword_140121430 + 128 * (unsigned __int64)KeGetPcr()->Prcb.Number + 64);
            HIDWORD(v57) = DueTime.HighPart;
            if ( DueTime.QuadPart )
              v55 = DueTime;
            LODWORD(v57) = KeGetPcr()->Prcb.Number;
            KeSetTimer((PKTIMER)qword_140121430 + 2 * v57, v55, v56);
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
0x14000acc0  mov     r11, rsp
0x14000acc3  mov     [r11+18h], rbx
0x14000acc7  mov     [r11+20h], rbp
0x14000accb  push    rsi
0x14000accc  push    rdi
0x14000accd  push    r12
0x14000accf  push    r14
0x14000acd1  push    r15
0x14000acd3  sub     rsp, 0B0h
0x14000acda  mov     rax, cs:__security_cookie
0x14000ace1  xor     rax, rsp
0x14000ace4  mov     [rsp+0D8h+var_30], rax
0x14000acec  xorps   xmm0, xmm0
0x14000acef  mov     [rsp+0D8h+var_97], 0
0x14000acf4  movups  xmmword ptr [r11-40h], xmm0
0x14000acf9  mov     rdi, rcx
0x14000acfc  xorps   xmm1, xmm1
0x14000acff  movups  xmmword ptr [r11-50h], xmm1
0x14000ad04  mov     r12d, gs:1A4h
0x14000ad0d  mov     rax, [rcx+20h]
0x14000ad11  mov     rsi, [rcx+28h]
0x14000ad15  movzx   ebp, byte ptr [rcx+44h]
0x14000ad19  inc     cs:?ndisWorkitemDpcs@@3KA; ulong ndisWorkitemDpcs
0x14000ad1f  and     bpl, 2
0x14000ad23  mov     r15d, [rcx+40h]
0x14000ad27  mov     [rsp+0D8h+var_58], rax
0x14000ad2f  mov     rax, [rsi+60h]
0x14000ad33  mov     qword ptr [rsp+0D8h+var_60], rax
0x14000ad38  mov     rax, [rcx+30h]
0x14000ad3c  mov     [rsp+0D8h+var_80], rax
0x14000ad41  mov     rax, [rcx+38h]
0x14000ad45  mov     [rsp+0D8h+var_78], rax
0x14000ad4a  cmp     r12d, r15d
0x14000ad4d  jnz     loc_1400ECBC8
0x14000ad53  test    bpl, bpl
0x14000ad56  jz      loc_14000B733
0x14000ad5c  lea     rcx, [rdi+48h]; SpinLock
0x14000ad60  mov     [rsp+0D8h+arg_8], r13
0x14000ad68  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000ad6f  nop     dword ptr [rax+rax+00h]
0x14000ad74  and     dword ptr [rdi+44h], 0FFFFFFFEh
0x14000ad78  lea     rcx, [rdi+48h]; SpinLock
0x14000ad7c  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000ad83  nop     dword ptr [rax+rax+00h]
0x14000ad88  mov     r14, [rsi+60h]
0x14000ad8c  xor     r9d, r9d
0x14000ad8f  mov     r11, [rsi+18h]
0x14000ad93  mov     r10, [rsi+0B8h]
0x14000ad9a  mov     [rsp+0D8h+var_88], r9
0x14000ad9f  mov     [rsp+0D8h+SpinLock], r11
0x14000ada4  mov     qword ptr [rsp+0D8h+ProcNumber.Group], r10
0x14000ada9  cmp     [r14+30h], r9d
0x14000adad  jnz     loc_14000AFAD
0x14000adb3  mov     r13d, r9d
0x14000adb6  mov     edi, r9d
0x14000adb9  cmp     [r14+50h], r9d
0x14000adbd  jnz     loc_14000AFAD
0x14000adc3  cmp     byte ptr cs:dword_140122F90+3, r9b
0x14000adca  jnz     loc_14000B44E
0x14000add0  mov     [rsp+0D8h+var_68], r9
0x14000add5  mov     [rsp+0D8h+var_98], r9b
0x14000adda  movzx   eax, byte ptr [rsi+4]
0x14000adde  lea     rbx, WPP_RECORDER_INITIALIZED
0x14000ade5  test    al, al
0x14000ade7  jnz     loc_14000B336
0x14000aded  cmp     cs:byte_140121401, al
0x14000adf3  mov     ebx, 0FFFFFFFFh
0x14000adf8  jz      loc_14000B32F
0x14000adfe  cmp     cs:dword_14012140C, 0
0x14000ae05  jnz     loc_14000B74A
0x14000ae0b  mov     eax, gs:1A4h
0x14000ae13  shl     eax, 0Ch
0x14000ae16  mov     ecx, eax
0x14000ae18  mov     rax, [r14+0CE0h]
0x14000ae1f  mov     edx, [rcx+rax]
0x14000ae22  lea     rcx, ?ndisPeriodicReceivesNblCounts@@3PAKA; ulong near * ndisPeriodicReceivesNblCounts
0x14000ae29  mov     ecx, [rcx+rdx*4]
0x14000ae2c  cmp     cs:dword_140121404, ecx
0x14000ae32  cmovb   ecx, cs:dword_140121404
0x14000ae39  mov     dword ptr [rsp+0D8h+var_88], ecx
0x14000ae3d  and     edi, 1
0x14000ae40  jz      short loc_14000AE6E
0x14000ae42  mov     ebx, gs:1A4h
0x14000ae4a  rdtsc
0x14000ae4c  mov     r8d, cs:?ndisPcwOffsetToPerCpuData@@3KA; ulong ndisPcwOffsetToPerCpuData
0x14000ae53  mov     ecx, ebx
0x14000ae55  imul    ecx, cs:?ndisPcwPerCpuDataStride@@3KA; ulong ndisPcwPerCpuDataStride
0x14000ae5c  shl     rdx, 20h
0x14000ae60  or      rax, rdx
0x14000ae63  add     rcx, r13
0x14000ae66  mov     [r8+rcx+130h], rax
0x14000ae6e  cmp     byte ptr [rsi+0C1h], 1
0x14000ae75  mov     rcx, [rsi+8]
0x14000ae79  jnz     loc_14000B368
0x14000ae7f  mov     edx, dword ptr [rsp+0D8h+var_80]
0x14000ae83  mov     rax, r10
0x14000ae86  mov     r8, [rsp+0D8h+var_78]
0x14000ae8b  mov     [rsp+0D8h+var_B8], r9
0x14000ae90  lea     r9, [rsp+0D8h+var_88]
0x14000ae95  call    _guard_dispatch_icall
0x14000ae9a  test    edi, edi
0x14000ae9c  jz      short loc_14000AEE0
0x14000ae9e  cmp     ebx, 0FFFFFFFFh
0x14000aea1  jnz     short loc_14000AEAB
0x14000aea3  mov     ebx, gs:1A4h
0x14000aeab  imul    ebx, cs:?ndisPcwPerCpuDataStride@@3KA; ulong ndisPcwPerCpuDataStride
0x14000aeb2  mov     r8d, cs:?ndisPcwOffsetToPerCpuData@@3KA; ulong ndisPcwOffsetToPerCpuData
0x14000aeb9  mov     eax, ebx
0x14000aebb  add     rax, r13
0x14000aebe  add     r8, rax
0x14000aec1  rdtsc
0x14000aec3  shl     rdx, 20h
0x14000aec7  or      rax, rdx
0x14000aeca  sub     rax, [r8+130h]
0x14000aed1  add     [r8+68h], rax
0x14000aed5  mov     qword ptr [r8+130h], 0
0x14000aee0  test    byte ptr [rsp+0D8h+var_88+4], 1
0x14000aee5  jnz     loc_14000B1A8
0x14000aeeb  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14000aef2  lock xadd [rsi+68h], eax
0x14000aef7  cmp     eax, 1
0x14000aefa  jnz     short loc_14000AF1C
0x14000aefc  movzx   eax, byte ptr [rsi+4]
0x14000af00  test    al, al
0x14000af02  jz      short loc_14000AF1C
0x14000af04  lea     rcx, [rsi+80h]; Event
0x14000af0b  xor     r8d, r8d; Wait
0x14000af0e  xor     edx, edx; Increment
0x14000af10  call    cs:__imp_KeSetEvent
0x14000af17  nop     dword ptr [rax+rax+00h]
0x14000af1c  lea     rbx, WPP_RECORDER_INITIALIZED
0x14000af23  cmp     [rsp+0D8h+var_98], 0
0x14000af28  jnz     loc_14000B78B
0x14000af2e  test    bpl, bpl
0x14000af31  jz      loc_14000B7B5
0x14000af37  cmp     r12d, r15d
0x14000af3a  jnz     loc_14000B71A
0x14000af40  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14000af47  lea     r15, WPP_91e24223ea6635c7ede0c9cfb5715ff6_Traceguids
0x14000af4e  mov     rbp, qword ptr [rsp+0D8h+var_60]
0x14000af53  jnz     short loc_14000AFC7
0x14000af55  lea     rcx, [rbp+1150h]; SpinLock
0x14000af5c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000af63  nop     dword ptr [rax+rax+00h]
0x14000af68  mov     r8, [rbp+1320h]; BugCheckParameter3
0x14000af6f  movzx   esi, al
0x14000af72  test    r8, 0FFFFFFFFFFFFFFFCh
0x14000af79  jz      short loc_14000AFA2
0x14000af7b  cmp     r8, 1
0x14000af7f  jz      loc_14000B802
0x14000af85  cmp     byte ptr [r8+2], 4Dh ; 'M'
0x14000af8a  ja      short loc_14000AFF4
0x14000af8c  mov     edx, 2; BugCheckParameter2
0x14000af91  mov     ecx, 1Eh; BugCheckParameter1
0x14000af96  mov     r9d, 4Dh ; 'M'; BugCheckParameter4
0x14000af9c  call    ?ndisBugCheckEx@@YAX_K000@Z; ndisBugCheckEx(unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64)
0x14000afa2  cmp     r8, 1
0x14000afa6  jz      short loc_14000AF7B
0x14000afa8  jmp     loc_14000B049
0x14000afad  mov     r13, [r14+28h]
0x14000afb1  mov     edi, [r14+50h]
0x14000afb5  test    r13, r13
0x14000afb8  jnz     loc_14000ADC3
0x14000afbe  mov     r13, [r14+28h]
0x14000afc2  jmp     loc_14000ADC3
0x14000afc7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000afce  mov     r9d, 19h; int
0x14000afd4  mov     qword ptr [rsp+0D8h+var_B0], rbp; char
0x14000afd9  mov     r8d, 14h; int
0x14000afdf  mov     dl, 4; int
0x14000afe1  mov     [rsp+0D8h+var_B8], r15; struct _GUID *
0x14000afe6  mov     rcx, [rcx+40h]; int
0x14000afea  call    WPP_RECORDER_SF_q
0x14000afef  jmp     loc_14000AF55
0x14000aff4  movzx   ecx, byte ptr [r8+1]
0x14000aff9  test    ecx, ecx
0x14000affb  jnz     loc_14000B14E
0x14000b001  mov     r9, [r8+8]
0x14000b005  test    r9, r9
0x14000b008  jnz     short loc_14000B01D
0x14000b00a  btr     dword ptr [r8+18h], 0Dh
0x14000b010  jb      short loc_14000B049
0x14000b012  mov     dl, 4Dh ; 'M'; unsigned __int8
0x14000b014  mov     rcx, r8; BugCheckParameter3
0x14000b017  call    ?ndisReportRefcountImbalance@@YAXPEAU_NDIS_REFCOUNT_BLOCK@@E@Z; ndisReportRefcountImbalance(_NDIS_REFCOUNT_BLOCK *,uchar)
0x14000b01d  movzx   edx, byte ptr [r8+3]
0x14000b022  xor     cl, cl
0x14000b024  cmp     cl, dl
0x14000b026  jnb     short loc_14000B00A
0x14000b028  movzx   eax, cl
0x14000b02b  cmp     byte ptr [r9+rax*2], 4Dh ; 'M'
0x14000b030  lea     r10, [r9+rax*2]
0x14000b034  jz      short loc_14000B03A
0x14000b036  inc     cl
0x14000b038  jmp     short loc_14000B024
0x14000b03a  movzx   eax, byte ptr [r10+1]
0x14000b03f  test    al, al
0x14000b041  jz      short loc_14000B036
0x14000b043  dec     al
0x14000b045  mov     [r10+1], al
0x14000b049  dec     dword ptr [rbp+1158h]
0x14000b04f  mov     edi, [rbp+1158h]
0x14000b055  lea     r14, WPP_RECORDER_INITIALIZED
0x14000b05c  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000b063  jnz     loc_14000B0F0
0x14000b069  movzx   edx, sil; NewIrql
0x14000b06d  lea     rcx, [rbp+1150h]; SpinLock
0x14000b074  call    cs:__imp_KeReleaseSpinLock
0x14000b07b  nop     dword ptr [rax+rax+00h]
0x14000b080  test    edi, edi
0x14000b082  jz      loc_14000B128
0x14000b088  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000b08f  jnz     short loc_14000B0C6
0x14000b091  mov     r13, [rsp+0D8h+arg_8]
0x14000b099  mov     rcx, [rsp+0D8h+var_30]
0x14000b0a1  xor     rcx, rsp; StackCookie
0x14000b0a4  call    __security_check_cookie
0x14000b0a9  lea     r11, [rsp+0D8h+var_28]
0x14000b0b1  mov     rbx, [r11+40h]
0x14000b0b5  mov     rbp, [r11+48h]
0x14000b0b9  mov     rsp, r11
0x14000b0bc  pop     r15
0x14000b0be  pop     r14
0x14000b0c0  pop     r12
0x14000b0c2  pop     rdi
0x14000b0c3  pop     rsi
0x14000b0c4  retn
0x14000b0c6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b0cd  mov     r9d, 1Ah; int
0x14000b0d3  mov     qword ptr [rsp+0D8h+var_B0], rbp; char
0x14000b0d8  mov     r8d, 14h; int
0x14000b0de  mov     dl, 4; int
0x14000b0e0  mov     [rsp+0D8h+var_B8], r15; struct _GUID *
0x14000b0e5  mov     rcx, [rcx+40h]; int
0x14000b0e9  call    WPP_RECORDER_SF_q
0x14000b0ee  jmp     short loc_14000B091
0x14000b0f0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b0f7  lea     rax, WPP_5c1c115ae3d7308ea4dc20929af9c88a_Traceguids
0x14000b0fe  mov     dword ptr [rsp+0D8h+var_A8], edi; char
0x14000b102  mov     r9d, 0Eh; int
0x14000b108  mov     qword ptr [rsp+0D8h+var_B0], rbp; char
0x14000b10d  mov     r8d, 14h; int
0x14000b113  mov     dl, 4; int
0x14000b115  mov     [rsp+0D8h+var_B8], rax; struct _GUID *
0x14000b11a  mov     rcx, [rcx+40h]; int
0x14000b11e  call    WPP_RECORDER_SF_qL
0x14000b123  jmp     loc_14000B069
0x14000b128  mov     rcx, [rbp+648h]; Event
0x14000b12f  test    rcx, rcx
0x14000b132  jz      loc_14000B088
0x14000b138  xor     r8d, r8d; Wait
0x14000b13b  xor     edx, edx; Increment
0x14000b13d  call    cs:__imp_KeSetEvent
0x14000b144  nop     dword ptr [rax+rax+00h]
0x14000b149  jmp     loc_14000B088
0x14000b14e  cmp     ecx, 1
0x14000b151  jnz     loc_14000B049
0x14000b157  lea     rdi, [r8+1348h]
0x14000b15e  mov     r9d, [rdi+38h]
0x14000b162  mov     ecx, r9d
0x14000b165  shr     ecx, 1
0x14000b167  mov     eax, r9d
0x14000b16a  and     ecx, 7FFFh
0x14000b170  shr     eax, 11h
0x14000b173  cmp     eax, 3FFEh
0x14000b178  jnb     loc_14000B382
0x14000b17e  inc     eax
0x14000b180  cmp     ecx, eax
0x14000b182  jnz     loc_14000B382
0x14000b188  mov     r14, [rdi]
0x14000b18b  test    r14, r14
0x14000b18e  jnz     loc_14000B7D6
0x14000b194  mov     rcx, rdi; struct _NDIS_REFCOUNT_STACK_BLOCK *
0x14000b197  call    ?ndisFreeRefCountStacksInBlock@@YAXPEAU_NDIS_REFCOUNT_STACK_BLOCK@@@Z; ndisFreeRefCountStacksInBlock(_NDIS_REFCOUNT_STACK_BLOCK *)
0x14000b19c  and     dword ptr [rdi+38h], 10001h
0x14000b1a3  jmp     loc_14000B049
0x14000b1a8  movzx   eax, cs:byte_140121401
0x14000b1af  mov     rdi, [rsi+60h]
0x14000b1b3  mov     [rsp+0D8h+var_96], al
0x14000b1b7  mov     eax, gs:1A4h
0x14000b1bf  mov     dword ptr [rsp+0D8h+ProcNumber.Group], eax
0x14000b1c3  mov     eax, [rdi+30h]
0x14000b1c6  test    eax, eax
0x14000b1c8  jnz     short loc_14000B1CF
0x14000b1ca  cmp     [rdi+50h], eax
0x14000b1cd  jz      short loc_14000B202
0x14000b1cf  mov     rdx, [rdi+28h]
0x14000b1d3  test    rdx, rdx
0x14000b1d6  jnz     short loc_14000B1DC
0x14000b1d8  mov     rdx, [rdi+28h]
0x14000b1dc  bt      eax, 17h
0x14000b1e0  jnb     short loc_14000B202
0x14000b1e2  mov     eax, gs:1A4h
0x14000b1ea  imul    eax, cs:?ndisPcwPerCpuDataStride@@3KA; ulong ndisPcwPerCpuDataStride
0x14000b1f1  mov     ecx, cs:?ndisPcwOffsetToPerCpuData@@3KA; ulong ndisPcwOffsetToPerCpuData
0x14000b1f7  add     rax, rdx
0x14000b1fa  inc     qword ptr [rcx+rax+120h]
0x14000b202  lea     rbx, [rdi+1150h]
0x14000b209  mov     rcx, rbx; SpinLock
0x14000b20c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
  ... truncated ...
```
