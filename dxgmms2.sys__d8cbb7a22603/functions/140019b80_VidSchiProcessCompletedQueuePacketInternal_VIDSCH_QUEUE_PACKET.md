# VidSchiProcessCompletedQueuePacketInternal(_VIDSCH_QUEUE_PACKET *)

- ea: `0x140019b80`
- end: `0x14001ac6e`
- name: `?VidSchiProcessCompletedQueuePacketInternal@@YAPEAU_VIDSCH_QUEUE_PACKET@@PEAU1@@Z`
- size: `4334`
- prototype: `struct _VIDSCH_QUEUE_PACKET *__fastcall(struct _VIDSCH_QUEUE_PACKET *)`
- caller_count: `4`
- callee_count: `24`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400190ac`
- `0x1400190cc`
- `0x140019160`
- `0x1400196d0`

## callees

- `0x14000cc58`
- `0x14000d02c`
- `0x14000e840`
- `0x140010200`
- `0x140017750`
- `0x140017930`
- `0x140018914`
- `0x140019b80`
- `0x14001af10`
- `0x14001b3a4`
- `0x14001bc80`
- `0x14001bd6c`
- `0x14001dc38`
- `0x14001dc9c`
- `0x14001e728`
- `0x140021d74`
- `0x1400246d0`
- `0x140024964`
- `0x140030efc`
- `0x1400330f0`
- `0x14003b2bc`
- `0x140043c5c`
- `0x140045200`
- `0x140059030`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14001a519`
- `ntoskrnl!ObfDereferenceObject` at `0x14001a519`
- `ntoskrnl!KfRaiseIrql` at `0x140019be1`
- `ntoskrnl!KfRaiseIrql` at `0x14001a0e0`
- `ntoskrnl!KfRaiseIrql` at `0x14001a1a6`
- `ntoskrnl!KfRaiseIrql` at `0x14001a257`
- `ntoskrnl!KfRaiseIrql` at `0x140019be1`
- `ntoskrnl!KfRaiseIrql` at `0x14001a0e0`
- `ntoskrnl!KfRaiseIrql` at `0x14001a1a6`
- `ntoskrnl!KfRaiseIrql` at `0x14001a257`
- `ntoskrnl!KeLowerIrql` at `0x14001a171`
- `ntoskrnl!KeLowerIrql` at `0x14001a235`
- `ntoskrnl!KeLowerIrql` at `0x14001a29e`
- `ntoskrnl!KeLowerIrql` at `0x14001a40c`
- `ntoskrnl!KeLowerIrql` at `0x14001a171`
- `ntoskrnl!KeLowerIrql` at `0x14001a235`
- `ntoskrnl!KeLowerIrql` at `0x14001a29e`
- `ntoskrnl!KeLowerIrql` at `0x14001a40c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140019bfb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140019dfc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001a0fa`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001a1c0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001a272`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140019bfb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140019dfc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001a0fa`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001a1c0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001a272`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140019e3c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001a161`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001a225`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001a28e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001a3fc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140019e3c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001a161`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001a225`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001a28e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001a3fc`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14001a452`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14001a452`
- `ntoskrnl!RtlSetBitEx` at `0x140019f7d`
- `ntoskrnl!RtlSetBitEx` at `0x140019f7d`
- `ntoskrnl!KeSetEvent` at `0x14001a145`
- `ntoskrnl!KeSetEvent` at `0x14001a20c`
- `ntoskrnl!KeSetEvent` at `0x14001a2ca`
- `ntoskrnl!KeSetEvent` at `0x14001a2ec`
- `ntoskrnl!KeSetEvent` at `0x14001a4a1`
- `ntoskrnl!KeSetEvent` at `0x14001a506`
- `ntoskrnl!KeSetEvent` at `0x14001a86e`
- `ntoskrnl!KeSetEvent` at `0x14001aa6f`
- `ntoskrnl!KeSetEvent` at `0x14001ac20`
- `ntoskrnl!KeSetEvent` at `0x14001a145`
- `ntoskrnl!KeSetEvent` at `0x14001a20c`
- `ntoskrnl!KeSetEvent` at `0x14001a2ca`
- `ntoskrnl!KeSetEvent` at `0x14001a2ec`
- `ntoskrnl!KeSetEvent` at `0x14001a4a1`
- `ntoskrnl!KeSetEvent` at `0x14001a506`
- `ntoskrnl!KeSetEvent` at `0x14001a86e`
- `ntoskrnl!KeSetEvent` at `0x14001aa6f`
- `ntoskrnl!KeSetEvent` at `0x14001ac20`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a4e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a4e0`
- `watchdog!WdLogSingleEntry5` at `0x14001ac58`
- `watchdog!WdLogSingleEntry5` at `0x14001ac58`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x14001ac31`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
struct _VIDSCH_QUEUE_PACKET *__fastcall VidSchiProcessCompletedQueuePacketInternal(
        struct _VIDSCH_QUEUE_PACKET *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // r15
  int v4; // eax
  __int64 v6; // rdi
  __int64 v7; // r13
  __int64 v8; // rsi
  unsigned int v9; // r14d
  unsigned __int64 v10; // r8
  int v11; // ecx
  struct _VIDSCH_QUEUE_PACKET **v12; // rdx
  struct _VIDSCH_QUEUE_PACKET **v13; // rcx
  int v14; // r12d
  __int64 v15; // rcx
  __int64 v16; // rdx
  int v17; // ecx
  int v18; // eax
  __int64 v19; // rdx
  int v20; // ecx
  int v21; // r8d
  _DWORD *v22; // r14
  unsigned int v23; // r10d
  bool v24; // zf
  int v25; // ecx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rax
  void (__fastcall *v31)(_QWORD); // rax
  void *v32; // rcx
  __int64 v33; // r14
  struct VIDMM_WORKER_THREAD **v34; // r12
  unsigned int *v35; // r14
  struct _KEVENT *v36; // r14
  struct _KEVENT *v37; // rdi
  int Flink; // ecx
  BOOL v39; // eax
  struct _KEVENT *v40; // r14
  struct _KEVENT *v41; // r13
  int v42; // ecx
  BOOL v43; // eax
  struct _KEVENT *v44; // r14
  KIRQL v45; // r13
  struct _KEVENT *v46; // r12
  int v47; // eax
  unsigned int v48; // eax
  int v49; // ecx
  unsigned int i; // edi
  __int64 v51; // rax
  __int64 v52; // rcx
  char *v53; // r14
  void *v54; // rcx
  int v55; // eax
  _QWORD *j; // rbx
  int v58; // ecx
  BOOL v59; // eax
  struct _KEVENT *v60; // rcx
  __int64 *v61; // rcx
  char v62; // al
  __int64 *v63; // rdx
  __int64 v64; // rax
  __int64 v65; // rcx
  __int64 v66; // rcx
  int v67; // eax
  _DWORD *v68; // rcx
  unsigned int v69; // r9d
  int v70; // eax
  char v71; // r10
  __int64 v72; // r15
  char v73; // cl
  __int64 v74; // rax
  unsigned int v75; // r10d
  int v76; // eax
  char v77; // cl
  __int64 v78; // r9
  char v79; // r11
  __int64 v80; // rax
  __int64 v81; // rdx
  int v82; // eax
  int v83; // ecx
  __int64 v84; // r8
  __int64 v85; // rdx
  __int64 v86; // rcx
  volatile signed __int32 *v87; // rcx
  int v88; // edx
  int v89; // r9d
  __int64 v90; // rcx
  _QWORD *v91; // rax
  struct _KEVENT *v92; // rcx
  __int64 v93; // rcx
  __int64 v94; // rax
  __int64 v95; // rcx
  __int64 *v96; // rcx
  __int64 **v97; // rdx
  __int64 v98; // rax
  struct _KEVENT *v99; // rcx
  __int64 **v100; // rax
  __int64 v101; // rax
  __int64 **v102; // r8
  unsigned int v103; // r8d
  __int64 v104; // [rsp+60h] [rbp-59h] BYREF
  __int64 v105; // [rsp+68h] [rbp-51h] BYREF
  __int64 **v106; // [rsp+70h] [rbp-49h]
  char v107; // [rsp+78h] [rbp-41h]
  int v108; // [rsp+7Ch] [rbp-3Dh]
  struct _KLOCK_QUEUE_HANDLE v109; // [rsp+80h] [rbp-39h] BYREF
  __int64 v110; // [rsp+98h] [rbp-21h]
  __int64 v111; // [rsp+A0h] [rbp-19h]
  __int64 v112; // [rsp+A8h] [rbp-11h]
  __int64 v113; // [rsp+B0h] [rbp-9h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+B8h] [rbp-1h] BYREF
  int v115; // [rsp+120h] [rbp+67h]
  KIRQL v116; // [rsp+120h] [rbp+67h]
  KIRQL v117; // [rsp+120h] [rbp+67h]
  KIRQL v118; // [rsp+128h] [rbp+6Fh]
  int v119; // [rsp+130h] [rbp+77h]
  unsigned int v120; // [rsp+130h] [rbp+77h]
  unsigned int v121; // [rsp+138h] [rbp+7Fh]
  unsigned int *v122; // [rsp+138h] [rbp+7Fh]
  char v123; // [rsp+138h] [rbp+7Fh]

  v3 = *((_QWORD *)a1 + 11);
  v4 = *((_DWORD *)a1 + 16);
  v111 = v3;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v6 = *(_QWORD *)(v3 + 96);
  v7 = *(_QWORD *)(v3 + 104);
  v112 = v6;
  v8 = *(_QWORD *)(v6 + 24);
  if ( (v4 & 0x20) != 0 && (byte_140087201 & 1) != 0 )
  {
    v93 = *(_QWORD *)(v3 + 56);
    if ( !v93 || (*(_DWORD *)(v3 + 112) & 0x40) != 0 )
      v93 = v3;
    McTemplateK0pp_EtwWriteTransfer(v93, AbortQueuePacket, a3, a1, v93);
  }
  v9 = 0;
  if ( !*((_DWORD *)a1 + 12) )
  {
    v32 = (void *)*((_QWORD *)a1 + 37);
    if ( v32 )
    {
      CRefCountedBuffer::RefCountedBufferRelease(v32);
      *((_QWORD *)a1 + 37) = 0;
    }
    if ( (unsigned int)Feature_PeriodicTrimImprovements__private_IsEnabledDeviceUsageNoInline() )
    {
      v33 = *(_QWORD *)(v7 + 16);
      if ( v33 )
      {
        v34 = *(struct VIDMM_WORKER_THREAD ***)(v8 + 24);
        if ( (unsigned int)Feature_PeriodicTrimImprovements__private_IsEnabledDeviceUsageNoInline() )
          VidMmIncrementPeriodicTrimUniqueness(*v34, *(struct VIDMM_PROCESS_ADAPTER_INFO **)(v33 + 16));
      }
      v9 = 0;
    }
  }
  v118 = KfRaiseIrql(2u);
  KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v8 + 2096), &LockHandle);
  v11 = *((_DWORD *)a1 + 20);
  v104 = v8;
  v107 = 0;
  v108 = 2;
  v106 = (__int64 **)&v105;
  v105 = (__int64)&v105;
  if ( (v11 & 0x10) != 0 )
  {
    v30 = *((_QWORD *)a1 + 11);
    *((_DWORD *)a1 + 20) = v11 & 0xFFFFFFEF;
    if ( *(_DWORD *)(*(_QWORD *)(v30 + 96) + 16520LL) != -1 )
    {
      v31 = *(void (__fastcall **)(_QWORD))(v8 + 3416);
      if ( v31 )
        v31(*(_QWORD *)(v8 + 3448));
    }
  }
  if ( *((_DWORD *)a1 + 13) == 16 || !*((_DWORD *)a1 + 13) )
  {
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 281, 512, v8, v3, a1);
    WdLogGlobalForLineNumber = 926;
    JUMPOUT(0x14001AC6ELL);
  }
  if ( (*((_DWORD *)a1 + 20) & 0x20) != 0 )
    VidSchiAdvanceContextSubmissionId((struct HwQueueStagingList *)&v104, a1);
  *((_QWORD *)a1 + 7) = MEMORY[0xFFFFF78000000320];
  *((_DWORD *)a1 + 13) = 16;
  v12 = (struct _VIDSCH_QUEUE_PACKET **)*((_QWORD *)a1 + 4);
  if ( v12[1] != (struct _VIDSCH_QUEUE_PACKET *)((char *)a1 + 32) )
    goto LABEL_182;
  v13 = (struct _VIDSCH_QUEUE_PACKET **)*((_QWORD *)a1 + 5);
  if ( *v13 != (struct _VIDSCH_QUEUE_PACKET *)((char *)a1 + 32) )
    goto LABEL_182;
  *v13 = (struct _VIDSCH_QUEUE_PACKET *)v12;
  v12[1] = (struct _VIDSCH_QUEUE_PACKET *)v13;
  v14 = 0;
  v15 = *(_QWORD *)(v3 + 672);
  v115 = 0;
  v113 = 0;
  if ( v15 == v3 + 672 )
  {
    if ( (*(_DWORD *)(v3 + 192) & 0x200) != 0 )
    {
      v29 = 14047;
LABEL_217:
      v28 = 10;
      goto LABEL_43;
    }
    if ( (*(_DWORD *)(v3 + 192) & 0x10) == 0
      && (*(_DWORD *)(v3 + 192) & 0x40) == 0
      && (*(_DWORD *)(v3 + 192) & 0x100) == 0 )
    {
      v28 = 0;
      v29 = 14080;
LABEL_43:
      VidSchiUpdateContextStatus(v3, v28, v29);
    }
  }
  else
  {
    v16 = v15 - 32;
    v17 = *(_DWORD *)(v15 + 48);
    if ( (v17 & 3) == 1 )
    {
      v113 = v16;
      *(_DWORD *)(v16 + 80) = v17 | 2;
    }
    if ( (*(_DWORD *)(v3 + 192) & 0x200) != 0
      && (((unsigned __int8)(*(_DWORD *)(v3 + 192) >> 9) | *(_BYTE *)(v3 + 192)) & 2) == 0 )
    {
      v29 = 14028;
      goto LABEL_217;
    }
  }
  v18 = *((_DWORD *)a1 + 12);
  if ( v18 == 5 )
  {
    if ( (*((_DWORD *)a1 + 20) & 4) == 0 )
    {
      if ( (byte_140087204 & 4) != 0 )
      {
        v83 = *((_DWORD *)a1 + 70);
        if ( (v83 & 0x10) != 0 )
        {
          v84 = *((_QWORD *)a1 + 11);
          if ( v84 )
          {
            v85 = *(_QWORD *)(v84 + 56);
            if ( !v85 || (*(_DWORD *)(v84 + 112) & 0x40) != 0 )
              v85 = *((_QWORD *)a1 + 11);
          }
          else
          {
            v85 = *(_QWORD *)(*((_QWORD *)a1 + 12) + 48LL);
            if ( !v85 )
              v85 = *((_QWORD *)a1 + 12);
          }
          McTemplateK0qpqdqPR4XR4p_EtwWriteTransfer(
            v83,
            v85,
            v84,
            1,
            v85,
            *((_DWORD *)a1 + 28),
            v83,
            *((_DWORD *)a1 + 71),
            (__int64)a1 + 288,
            (__int64)a1 + 544,
            (char)a1);
          v9 = 0;
        }
      }
      VidSchiCompleteSignalCommmand((HwQueueStagingList *)&v104, (__int64)a1, 1);
    }
  }
  else if ( v18 == 3 )
  {
    VidSchiReleaseFlipFencesReference((struct _VIDSCH_GLOBAL *)v8, (struct _VIDSCH_QUEUE_PACKET *)((char *)a1 + 880));
  }
  if ( (*((_DWORD *)a1 + 20) & 8) != 0 )
    _InterlockedDecrement((volatile signed __int32 *)(v8 + 1124));
  if ( !*((_DWORD *)a1 + 12) )
  {
    if ( (*((_DWORD *)a1 + 16) & 4) != 0 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v6 + 3008));
      RtlSetBitEx(v8 + 632, *(unsigned __int16 *)(v6 + 4));
    }
    if ( *((_DWORD *)a1 + 120) )
    {
      do
      {
        if ( v9 >= 0x10 )
          break;
        v86 = *((_QWORD *)a1 + v9 + 61);
        *((_QWORD *)a1 + v9 + 61) = 0;
        if ( v86 )
        {
          v87 = (volatile signed __int32 *)(v86 + 104);
          v88 = _InterlockedDecrement(v87);
          if ( a1 != (struct _VIDSCH_QUEUE_PACKET *)-616LL )
            --*((_DWORD *)a1 + 154);
          InterlockedCounterWithHistoryRelease::AddHistoryEntry((InterlockedCounterWithHistoryRelease *)v87, v88, v10);
        }
        ++v9;
      }
      while ( v9 < *((_DWORD *)a1 + 120) );
    }
  }
  v19 = *((unsigned int *)a1 + 18);
  v20 = *((_DWORD *)a1 + 18) & 0x4000;
  if ( (*((_DWORD *)a1 + 18) & 0x40020) == 0x40000 || v20 )
  {
    if ( (v19 & 0x400) == 0 || (v21 = 0, (v19 & 0x800) != 0) )
      v21 = 1;
    v119 = v21;
    v22 = (_DWORD *)((char *)a1 + 168);
    v23 = *((_DWORD *)a1 + 42);
    v121 = v23;
    if ( (v19 & 0x40000) != 0 )
    {
      v24 = v20 == 0;
      v25 = v21;
      if ( v24 )
        v25 = 0;
    }
    else
    {
      if ( (v19 & 4) != 0 )
      {
        if ( *((_DWORD *)a1 + 100) != 1 )
        {
          if ( (*((_DWORD *)a1 + 16) & 2) != 0 )
          {
            v25 = 0;
            goto LABEL_62;
          }
          if ( v21 )
          {
            v14 = 1;
            v115 = 1;
            VidSchiUpdateLastCompletedPresentTimestamp(*((_QWORD *)a1 + 11), 1, 0);
            v23 = v121;
          }
          if ( (*((_DWORD *)a1 + 220) & 0x3FF) != 0 )
          {
            v94 = *(unsigned int *)(v3 + 88);
            v95 = *(_QWORD *)(v8 + 776);
            if ( (unsigned int)v94 < *(_DWORD *)(v8 + 848) )
              v95 += 8 * v94;
            VidSchiUnreferencePrimaryAllocations(
              (struct HwQueueStagingList *)&v104,
              (struct _VIDSCH_GLOBAL *)v8,
              v23,
              (struct _VIDSCH_QUEUE_PACKET *)((char *)a1 + 880),
              *((_DWORD *)a1 + 104),
              1 << *(_BYTE *)(*(_QWORD *)v95 + 6LL),
              0,
              0,
              (unsigned int *)a1 + 224);
          }
          v25 = v115;
          if ( !v115 )
          {
LABEL_62:
            v115 = v25;
            if ( (*((_DWORD *)a1 + 18) & 0x40080) != 0 && *((_QWORD *)a1 + 19) && *((_QWORD *)a1 + 20) && v119 )
              VidSchiSubmitPresentHistoryToken((struct HwQueueStagingList *)&v104, a1, 0, 0, 0);
            if ( v14 )
            {
              _InterlockedDecrement((volatile signed __int32 *)(v8 + 880));
              DecrementNumberOfQueuedFlipPerSource((struct _VIDSCH_GLOBAL *)v8, v121);
              _InterlockedDecrement((volatile signed __int32 *)(v7 + 1836));
              _InterlockedDecrement((volatile signed __int32 *)(v7 + 4LL * v103 + 1772));
            }
            VidSchiSignalRegisteredEvent(v8, v8 + 2040);
            v122 = (unsigned int *)((char *)a1 + 168);
            if ( v115 )
              goto LABEL_75;
            goto LABEL_73;
          }
LABEL_28:
          if ( v121 != -1 && (*((_DWORD *)a1 + 18) & 0x40000) == 0 )
          {
            v110 = v121;
            _InterlockedDecrement((volatile signed __int32 *)(v7 + 4LL * v121 + 1708));
            v26 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v7 + 48) + 32LL)
                                        + 8LL * *(unsigned int *)(*(_QWORD *)(v7 + 40) + 4LL))
                            + 8LL * v121
                            + 88);
            if ( (*((_DWORD *)a1 + 18) & 0x80u) == 0 )
            {
              _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(v8 + 8LL * v121 + 7584) + 8LL));
              ++**(_DWORD **)(v8 + 8LL * v121 + 7584);
            }
            _InterlockedDecrement((volatile signed __int32 *)(v26 + 8));
            ++*(_DWORD *)v26;
            if ( (*((_DWORD *)a1 + 18) & 0x20000) != 0 )
            {
              memset(&v109, 0, sizeof(v109));
              KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v8 + 2104), &v109);
              v27 = v110;
              *(_DWORD *)(v7 + 4 * v110 + 516) = *((_DWORD *)a1 + 98);
              *(_QWORD *)(v7 + 8 * v27 + 584) = *((_QWORD *)a1 + 17);
              *(_QWORD *)(v7 + 8 * v27 + 712) = *((_QWORD *)a1 + 18);
              KeReleaseInStackQueuedSpinLockFromDpcLevel(&v109);
            }
            v25 = v115;
          }
          goto LABEL_62;
        }
        v14 = v21;
      }
      v25 = v21;
    }
    v115 = v25;
    if ( !v25 )
      goto LABEL_62;
    LOBYTE(v19) = 1;
    VidSchiUpdateLastCompletedPresentTimestamp(*((_QWORD *)a1 + 11), v19, 0);
    v25 = v115;
    goto LABEL_28;
  }
  v22 = (_DWORD *)((char *)a1 + 168);
  v122 = (unsigned int *)((char *)a1 + 168);
LABEL_73:
  if ( !*((_DWORD *)a1 + 12) )
    VidSchiUpdateLastCompletedPresentTimestamp(v3, 0, 0);
LABEL_75:
  if ( *((_DWORD *)a1 + 12) != 3 || *v22 == -1 )
  {
    v35 = v122;
  }
  else
  {
    v64 = *((_QWORD *)a1 + 11);
    if ( v64 )
      v65 = *(_QWORD *)(v64 + 104);
    else
      v65 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 12) + 40LL) + 8LL);
    v66 = *(_QWORD *)(v65 + 40);
    v67 = *((_DWORD *)a1 + 18) >> 23;
    v110 = v66;
    if ( (v67 & 1) != 0 )
    {
      v68 = (_DWORD *)((char *)a1 + 880);
      v69 = ((unsigned __int16)*((_DWORD *)a1 + 220) | (unsigned __int16)(*((_DWORD *)a1 + 220) >> 10)) & 0x3FF;
    }
    else
    {
      v89 = 1 << *(_DWORD *)(v66 + 160);
      v68 = (_DWORD *)((char *)a1 + 880);
      v69 = v89 - 1;
    }
    v35 = v122;
    v24 = !_BitScanForward((unsigned int *)&v70, v69);
    v71 = -1;
    if ( !v24 )
      v71 = v70;
    if ( v69 )
    {
      v72 = v110;
      do
      {
        v73 = v71;
        v74 = v71;
        v71 = -1;
        _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(v72 + 8LL * *v122 + 3528) + 304 * v74 + 192));
        v69 &= ~(1 << v73);
        v24 = !_BitScanForward((unsigned int *)&v74, v69);
        if ( !v24 )
          v71 = v74;
      }
      while ( v69 );
      v3 = v111;
      v68 = (_DWORD *)((char *)a1 + 880);
      v6 = v112;
    }
    if ( (*((_DWORD *)a1 + 18) & 0x800000) != 0 )
      v75 = ((unsigned __int16)*v68 | (unsigned __int16)(*v68 >> 10)) & 0x3FF;
    else
      v75 = (1 << *(_DWORD *)(v8 + 160)) - 1;
    v24 = !_BitScanForward((unsigned int *)&v76, v75);
    v77 = -1;
    v120 = v75;
    if ( !v24 )
      v77 = v76;
    while ( v75 )
    {
      v78 = *v35;
      v79 = v77;
      v80 = *(_QWORD *)(v8 + 8 * v78 + 3528);
      v123 = v77;
      v111 = v78;
      v81 = *(int *)(v80 + 304LL * (unsigned int)v77 + 188);
      if ( (int)v81 > -1
        && *(_DWORD *)(160 * v81 + *(_QWORD *)(v8 + 3656) + 112) == 1
        && VidSchiCheckPlaneIndependentFlipCondition((struct _VIDSCH_GLOBAL *)v8, v78, v77) )
      {
        VidSchiFlushPendingTokenList((struct HwQueueStagingList *)&v104, (struct _VIDSCH_GLOBAL *)v8);
        v75 = v120;
        v79 = v123;
      }
      v77 = -1;
      v75 &= ~(1 << v79);
      v24 = !_BitScanForward((unsigned int *)&v82, v75);
      v120 = v75;
      if ( !v24 )
        v77 = v82;
    }
  }
  _InterlockedDecrement((volatile signed __int32 *)(v8 + 868));
  _InterlockedDecrement((volatile signed __int32 *)(v6 + 3020));
  _InterlockedDecrement((volatile signed __int32 *)(v7 + 1844));
  if ( (unsigned int)(*((_DWORD *)a1 + 12) - 4) > 1 )
    _InterlockedDecrement((volatile signed __int32 *)(v7 + 1848));
  if ( !*((_DWORD *)a1 + 12) && (*((_DWORD *)a1 + 18) & 4) != 0 )
    _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(v8 + 8LL * *v35 + 3528) + 3244LL));
  _InterlockedDecrement((volatile signed __int32 *)(v3 + 792));
  VidSchiProfilePerformanceTick(9, v8, v6, 0, 0, (__int64)a1, 0, 0);
  VidSchiCheckPendingDeviceCommand(v7);
  if ( !v115 )
    goto LABEL_91;
  v36 = (struct _KEVENT *)(v7 + 128);
  memset(&v109, 0, sizeof(v109));
  v116 = KfRaiseIrql(2u);
  KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v8 + 2112), &v109);
  if ( *(struct _KEVENT **)&v36->Header.Lock == v36 )
    goto LABEL_90;
  v37 = *(struct _KEVENT **)&v36->Header.Lock;
  do
  {
    if ( LODWORD(v37->Header.WaitListHead.Blink) == 4 )
    {
      v39 = *(_DWORD *)(*(_QWORD *)&v37[1].Header.Lock + 4LL * LODWORD(v37[1].Header.WaitListHead.Blink) + 1708) < *(_DWORD *)(*(_QWORD *)&v37[1].Header.Lock + 252LL);
LABEL_86:
      if ( !v39 )
        goto LABEL_88;
      goto LABEL_87;
    }
    if ( ((__int64)v37[1].Header.WaitListHead.Flink & 0x10) != 0 )
    {
      Flink = (int)v37[1].Header.WaitListHead.Blink->Flink;
      HIDWORD(v37[5].Header.WaitListHead.Blink) = Flink;
      v39 = Flink == 0;
      goto LABEL_86;
    }
LABEL_87:
    ++v37[5].Header.LockNV;
    KeSetEvent(v37 + 4, 0, 0);
LABEL_88:
    v37 = *(struct _KEVENT **)&v37->Header.Lock;
  }
  while ( v37 != v36 );
  v6 = v112;
LABEL_90:
  KeReleaseInStackQueuedSpinLockFromDpcLevel(&v109);
  KeLowerIrql(v116);
LABEL_91:
  if ( v14 )
  {
    VidSchiSignalRegisteredEvent(v8, v7 + 144);
    VidSchiSignalRegisteredEvent(v8, v8 + 2024);
    *(_QWORD *)(v8 + 1968) = MEMORY[0xFFFFF78000000320];
    KeSetEvent((PRKEVENT)(v8 + 1936), 0, 0);
  }
  v40 = (struct _KEVENT *)(v6 + 424);
  memset(&v109, 0, sizeof(v109));
  v117 = KfRaiseIrql(2u);
  KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v8 + 2112), &v109);
  v41 = *(struct _KEVENT **)(v6 + 424);
  if ( *(struct _KEVENT **)&v40->Header.Lock != v40 )
  {
    while ( 2 )
    {
      if ( LODWORD(v41->Header.WaitListHead.Blink) != 4 )
      {
        if ( ((__int64)v41[1].Header.WaitListHead.Flink & 0x10) != 0 )
        {
          v42 = (int)v41[1].Header.WaitListHead.Blink->Flink;
          HIDWORD(v41[5].Header.WaitListHead.Blink) = v42;
          v43 = v42 == 0;
          goto LABEL_97;
        }
        goto LABEL_98;
      }
      v43 = *(_DWORD *)(*(_QWORD *)&v41[1].Header.Lock + 4LL * LODWORD(v41[1].Header.WaitListHead.Blink) + 1708) < *(_DWORD *)(*(_QWORD *)&v41[1].Header.Lock + 252LL);
LABEL_97:
      if ( v43 )
      {
LABEL_98:
        ++v41[5].Header.LockNV;
        KeSetEvent(v41 + 4, 0, 0);
      }
      v41 = *(struct _KEVENT **)&v41->Header.Lock;
      if ( v41 == v40 )
        break;
      continue;
    }
  }
  KeReleaseInStackQueuedSpinLockFromDpcLevel(&v109);
  KeLowerIrql(v117);
  v44 = (struct _KEVENT *)(v8 + 2008);
  memset(&v109, 0, sizeof(v109));
  v45 = KfRaiseIrql(2u);
  KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v8 + 2112), &v109);
  v46 = *(struct _KEVENT **)(v8 + 2008);
  if ( *(struct _KEVENT **)&v44->Header.Lock != v44 )
  {
    do
    {
      if ( LODWORD(v46->Header.WaitListHead.Blink) == 4 )
      {
        v59 = *(_DWORD *)(*(_QWORD *)&v46[1].Header.Lock + 4LL * LODWORD(v46[1].Header.WaitListHead.Blink) + 1708) < *(_DWORD *)(*(_QWORD *)&v46[1].Header.Lock + 252LL);
      }
      else
      {
        if ( ((__int64)v46[1].Header.WaitListHead.Flink & 0x10) == 0 )
          goto LABEL_126;
        v58 = (int)v46[1].Header.WaitListHead.Blink->Flink;
        HIDWORD(v46[5].Header.WaitListHead.Blink) = v58;
        v59 = v58 == 0;
      }
      if ( v59 )
      {
LABEL_126:
        ++v46[5].Header.LockNV;
        KeSetEvent(v46 + 4, 0, 0);
      }
      v46 = *(struct _KEVENT **)&v46->Header.Lock;
    }
    while ( v46 != v44 );
  }
  KeReleaseInStackQueuedSpinLockFromDpcLevel(&v109);
  KeLowerIrql(v45);
  *(_QWORD *)(v6 + 328) = MEMORY[0xFFFFF78000000320];
  KeSetEvent((PRKEVENT)(v6 + 296), 0, 0);
  *(_QWORD *)(v8 + 1856) = MEMORY[0xFFFFF78000000320];
  KeSetEvent((PRKEVENT)(v8 + 1824), 0, 0);
  if ( (*((_DWORD *)a1 + 16) & 1) == 0 )
  {
    v47 = *((_DWORD *)a1 + 12);
    if ( !v47 || v47 == 7 )
    {
      v60 = (struct _KEVENT *)*((_QWORD *)a1 + 46);
      if ( v60 )
      {
        KeSetEvent(v60, 0, 0);
        ObfDereferenceObject(*((PVOID *)a1 + 46));
      }
    }
    else if ( v47 == 6 )
    {
      v92 = (struct _KEVENT *)*((_QWORD *)a1 + 39);
      if ( v92 )
        KeSetEvent(v92, 0, 0);
    }
  }
  v48 = *((_DWORD *)a1 + 12);
  if ( v48 <= 7 )
  {
    v49 = 137;
    if ( _bittest(&v49, v48) )
    {
      if ( !*(_BYTE *)(v3 + 917) )
      {
        for ( i = 0; i < *(_DWORD *)(v8 + 160); ++i )
        {
          v51 = 8 * i * (*((_DWORD *)a1 + 222) + 28);
          v52 = *(_QWORD *)((char *)a1 + v51 + 1088);
          if ( v52 )
          {
            v53 = (char *)a1 + v51;
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v52 + 12), 0xFFFFFFFF) == 1 )
            {
              if ( *(_QWORD *)v52 )
                ExFreeToLookasideListEx(*(PLOOKASIDE_LIST_EX *)v52, (PVOID)v52);
              else
                ExFreePoolWithTag((PVOID)v52, 0);
            }
            *((_QWORD *)v53 + 136) = 0;
          }
        }
      }
      v54 = (void *)*((_QWORD *)a1 + 39);
      if ( v54 )
      {
        CRefCountedBuffer::RefCountedBufferRelease(v54);
        *((_QWORD *)a1 + 39) = 0;
      }
    }
  }
  VidSchiFreeQueuePacket(v3, a1);
  if ( v108 != 1 )
    goto LABEL_118;
  v55 = *(_DWORD *)(v104 + 312);
  if ( v55 == 1 )
  {
    if ( (__int64 *)v105 == &v105 )
      goto LABEL_118;
    v96 = (__int64 *)(v104 + 288);
    if ( *(__int64 **)(*v96 + 8) == v96 )
    {
      v97 = *(__int64 ***)(v104 + 296);
      if ( *v97 == v96 && *(__int64 **)(v105 + 8) == &v105 && *v106 == &v105 )
      {
        *v97 = &v105;
        v96[1] = (__int64)v106;
        *v106 = v96;
        v98 = v105;
        v106 = v97;
        if ( *(__int64 **)(v105 + 8) == &v105 && *v97 == &v105 )
        {
          *v97 = (__int64 *)v105;
          *(_QWORD *)(v98 + 8) = v97;
          v106 = (__int64 **)&v105;
          v105 = (__int64)&v105;
          goto LABEL_209;
        }
      }
    }
LABEL_182:
    __fastfail(3u);
  }
  if ( v55 == 2 )
  {
    v61 = (__int64 *)v105;
    v62 = 0;
    if ( (__int64 *)v105 != &v105 )
    {
      do
      {
        v63 = (__int64 *)*v61;
        if ( *((_BYTE *)v61 - 29) )
        {
          if ( (__int64 *)v63[1] != v61 )
            goto LABEL_182;
          v100 = (__int64 **)v61[1];
          if ( *v100 != v61 )
            goto LABEL_182;
          *v100 = v63;
          v63[1] = (__int64)v100;
          v101 = v104 + 288;
          v102 = *(__int64 ***)(v104 + 296);
          if ( *v102 != (__int64 *)(v104 + 288) )
            goto LABEL_182;
          *v61 = v101;
          v61[1] = (__int64)v102;
          *v102 = v61;
          *(_QWORD *)(v101 + 8) = v61;
          v62 = 1;
        }
        v61 = v63;
      }
      while ( v63 != &v105 );
      if ( v62 )
      {
LABEL_209:
        *(_BYTE *)(v104 + 304) = 0;
        v99 = (struct _KEVENT *)(v104 + 1544);
        *(_QWORD *)(v104 + 1576) = MEMORY[0xFFFFF78000000320];
        KeSetEvent(v99, 0, 0);
      }
    }
  }
LABEL_118:
  for ( j = (_QWORD *)v105; (__int64 *)v105 != &v105; j = (_QWORD *)v105 )
  {
    HwQueueStagingList::ProcessHwQueue((HwQueueStagingList *)&v104, (struct VIDSCH_HW_QUEUE *)(j - 22), 0);
    v90 = *j;
    if ( *(_QWORD **)(*j + 8LL) != j )
      goto LABEL_182;
    v91 = (_QWORD *)j[1];
    if ( (_QWORD *)*v91 != j )
      goto LABEL_182;
    *v91 = v90;
    *(_QWORD *)(v90 + 8) = v91;
    *j = 0;
    j[1] = 0;
  }
  v107 = 1;
  KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  KeLowerIrql(v118);
  HwQueueStagingList::~HwQueueStagingList((HwQueueStagingList *)&v104);
  return (struct _VIDSCH_QUEUE_PACKET *)v113;
}

```

## disassembly

```asm
0x140019b80  push    rbp
0x140019b82  push    rbx
0x140019b83  push    rsi
0x140019b84  push    rdi
0x140019b85  push    r13
0x140019b87  push    r14
0x140019b89  push    r15
0x140019b8b  lea     rbp, [rsp-27h]
0x140019b90  sub     rsp, 0E0h
0x140019b97  mov     r15, [rcx+58h]
0x140019b9b  xor     eax, eax
0x140019b9d  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x140019ba1  xorps   xmm0, xmm0
0x140019ba4  mov     eax, [rcx+40h]
0x140019ba7  mov     rbx, rcx
0x140019baa  mov     [rbp+57h+var_70], r15
0x140019bae  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x140019bb2  mov     rdi, [r15+60h]
0x140019bb6  mov     r13, [r15+68h]
0x140019bba  mov     [rbp+57h+var_68], rdi
0x140019bbe  mov     rsi, [rdi+18h]
0x140019bc2  test    al, 20h
0x140019bc4  jnz     loc_14001A87F
0x140019bca  xor     r14d, r14d
0x140019bcd  mov     [rsp+110h+var_38], r12
0x140019bd5  cmp     [rbx+30h], r14d
0x140019bd9  jz      loc_140019F14
0x140019bdf  mov     cl, 2; NewIrql
0x140019be1  call    cs:__imp_KfRaiseIrql
0x140019be8  nop     dword ptr [rax+rax+00h]
0x140019bed  lea     rcx, [rsi+830h]; SpinLock
0x140019bf4  mov     [rbp+57h+arg_8], al
0x140019bf7  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x140019bfb  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140019c02  nop     dword ptr [rax+rax+00h]
0x140019c07  mov     ecx, [rbx+50h]
0x140019c0a  lea     rax, [rbp+57h+var_A8]
0x140019c0e  mov     [rbp+57h+var_B0], rsi
0x140019c12  xorps   xmm0, xmm0
0x140019c15  mov     [rbp+57h+var_98], 0
0x140019c19  mov     [rbp+57h+var_94], 2
0x140019c20  movups  [rbp+57h+var_A8], xmm0
0x140019c24  mov     qword ptr [rbp+57h+var_A8+8], rax
0x140019c28  lea     rax, [rbp+57h+var_A8]
0x140019c2c  mov     qword ptr [rbp+57h+var_A8], rax
0x140019c30  test    cl, 10h
0x140019c33  jnz     loc_140019ED6
0x140019c39  mov     eax, [rbx+34h]
0x140019c3c  cmp     eax, 10h
0x140019c3f  jz      loc_14001AC31
0x140019c45  mov     eax, [rbx+34h]
0x140019c48  test    eax, eax
0x140019c4a  jz      loc_14001AC31
0x140019c50  mov     eax, [rbx+50h]
0x140019c53  test    al, 20h
0x140019c55  jnz     loc_14001AACA
0x140019c5b  mov     rax, ds:0FFFFF78000000320h
0x140019c65  mov     [rbx+38h], rax
0x140019c69  lea     rax, [rbx+20h]
0x140019c6d  mov     dword ptr [rbx+34h], 10h
0x140019c74  mov     rdx, [rax]
0x140019c77  cmp     [rdx+8], rax
0x140019c7b  jnz     loc_14001A838
0x140019c81  mov     rcx, [rax+8]
0x140019c85  cmp     [rcx], rax
0x140019c88  jnz     loc_14001A838
0x140019c8e  mov     [rcx], rdx
0x140019c91  lea     rax, [r15+2A0h]
0x140019c98  mov     [rdx+8], rcx
0x140019c9c  mov     r12d, r14d
0x140019c9f  mov     rcx, [rax]
0x140019ca2  mov     [rbp+57h+arg_0], r14d
0x140019ca6  mov     [rbp+57h+var_60], r14
0x140019caa  cmp     rcx, rax
0x140019cad  jz      loc_140019E81
0x140019cb3  lea     rdx, [rcx-20h]
0x140019cb7  mov     ecx, [rcx+30h]
0x140019cba  mov     eax, ecx
0x140019cbc  and     al, 3
0x140019cbe  cmp     al, 1
0x140019cc0  jnz     short loc_140019CCC
0x140019cc2  or      ecx, 2
0x140019cc5  mov     [rbp+57h+var_60], rdx
0x140019cc9  mov     [rdx+50h], ecx
0x140019ccc  mov     eax, [r15+0C0h]
0x140019cd3  bt      eax, 9
0x140019cd7  jb      loc_14001AAE3
0x140019cdd  mov     eax, [rbx+30h]
0x140019ce0  cmp     eax, 5
0x140019ce3  jz      loc_140019E50
0x140019ce9  cmp     eax, 3
0x140019cec  jz      loc_14001A790
0x140019cf2  mov     eax, [rbx+50h]
0x140019cf5  test    al, 8
0x140019cf7  jnz     loc_14001A8D9
0x140019cfd  cmp     dword ptr [rbx+30h], 0
0x140019d01  jz      loc_140019F64
0x140019d07  mov     edx, [rbx+48h]
0x140019d0a  mov     ecx, edx
0x140019d0c  mov     eax, edx
0x140019d0e  and     ecx, 4000h
0x140019d14  and     eax, 40020h
0x140019d19  cmp     eax, 40000h
0x140019d1e  jnz     loc_14001A023
0x140019d24  bt      edx, 0Ah
0x140019d28  jb      loc_14001AB57
0x140019d2e  mov     r8d, 1
0x140019d34  mov     [rbp+57h+arg_10], r8d
0x140019d38  lea     r14, [rbx+0A8h]
0x140019d3f  mov     r10d, [r14]
0x140019d42  mov     qword ptr [rbp+57h+arg_18], r10
0x140019d46  bt      edx, 12h
0x140019d4a  jnb     loc_140019F9E
0x140019d50  xor     eax, eax
0x140019d52  test    ecx, ecx
0x140019d54  mov     ecx, r8d
0x140019d57  cmovz   ecx, eax
0x140019d5a  mov     [rbp+57h+arg_0], ecx
0x140019d5d  test    ecx, ecx
0x140019d5f  jz      loc_140019FC2
0x140019d65  mov     rcx, [rbx+58h]
0x140019d69  xor     r8d, r8d
0x140019d6c  mov     dl, 1
0x140019d6e  call    VidSchiUpdateLastCompletedPresentTimestamp
0x140019d73  mov     ecx, [rbp+57h+arg_0]
0x140019d76  mov     rdx, qword ptr [rbp+57h+arg_18]
0x140019d7a  cmp     edx, 0FFFFFFFFh
0x140019d7d  jz      loc_140019FC2
0x140019d83  test    dword ptr [rbx+48h], 40000h
0x140019d8a  jnz     loc_140019FC2
0x140019d90  mov     r8d, edx
0x140019d93  mov     [rbp+57h+var_78], r8
0x140019d97  lock dec dword ptr [r13+r8*4+6ACh]
0x140019da0  mov     rax, [r13+28h]
0x140019da4  mov     edx, [rax+4]
0x140019da7  mov     rax, [r13+30h]
0x140019dab  mov     rcx, [rax+20h]
0x140019daf  mov     rax, [rcx+rdx*8]
0x140019db3  mov     rcx, [rax+r8*8+58h]
0x140019db8  mov     eax, [rbx+48h]
0x140019dbb  test    al, al
0x140019dbd  js      short loc_140019DD5
0x140019dbf  mov     rax, [rsi+r8*8+1DA0h]
0x140019dc7  lock dec dword ptr [rax+8]
0x140019dcb  mov     rax, [rsi+r8*8+1DA0h]
0x140019dd3  inc     dword ptr [rax]
0x140019dd5  lock dec dword ptr [rcx+8]
0x140019dd9  inc     dword ptr [rcx]
0x140019ddb  test    dword ptr [rbx+48h], 20000h
0x140019de2  jz      short loc_140019E48
0x140019de4  xorps   xmm0, xmm0
0x140019de7  lea     rcx, [rsi+838h]; SpinLock
0x140019dee  xor     eax, eax
0x140019df0  lea     rdx, [rbp+57h+var_90]; LockHandle
0x140019df4  movups  xmmword ptr [rbp+57h+var_90.LockQueue.Next], xmm0
0x140019df8  mov     qword ptr [rbp+57h+var_90.OldIrql], rax
0x140019dfc  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140019e03  nop     dword ptr [rax+rax+00h]
0x140019e08  mov     eax, [rbx+188h]
0x140019e0e  mov     rcx, [rbp+57h+var_78]
0x140019e12  mov     [r13+rcx*4+204h], eax
0x140019e1a  mov     rax, [rbx+88h]
0x140019e21  mov     [r13+rcx*8+248h], rax
0x140019e29  mov     rax, [rbx+90h]
0x140019e30  mov     [r13+rcx*8+2C8h], rax
0x140019e38  lea     rcx, [rbp+57h+var_90]; LockHandle
0x140019e3c  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140019e43  nop     dword ptr [rax+rax+00h]
0x140019e48  mov     ecx, [rbp+57h+arg_0]
0x140019e4b  jmp     loc_140019FC2
0x140019e50  mov     eax, [rbx+50h]
0x140019e53  test    al, 4
0x140019e55  jnz     loc_140019CF2
0x140019e5b  movzx   eax, cs:byte_140087204
0x140019e62  and     al, 4
0x140019e64  mov     byte ptr [rbp+57h+arg_10], al
0x140019e67  jnz     loc_14001A6ED
0x140019e6d  mov     r8b, 1
0x140019e70  lea     rcx, [rbp+57h+var_B0]
0x140019e74  mov     rdx, rbx
0x140019e77  call    VidSchiCompleteSignalCommmand
0x140019e7c  jmp     loc_140019CF2
0x140019e81  mov     eax, [r15+0C0h]
0x140019e88  bt      eax, 9
0x140019e8c  jb      loc_14001AADB
0x140019e92  mov     eax, [r15+0C0h]
0x140019e99  test    al, 10h
0x140019e9b  jnz     loc_140019CDD
0x140019ea1  mov     eax, [r15+0C0h]
0x140019ea8  test    al, 40h
0x140019eaa  jnz     loc_140019CDD
0x140019eb0  mov     eax, [r15+0C0h]
0x140019eb7  bt      eax, 8
0x140019ebb  jb      loc_140019CDD
0x140019ec1  xor     edx, edx
0x140019ec3  mov     r8d, 3700h
0x140019ec9  mov     rcx, r15
0x140019ecc  call    VidSchiUpdateContextStatus
0x140019ed1  jmp     loc_140019CDD
0x140019ed6  mov     rax, [rbx+58h]
0x140019eda  and     ecx, 0FFFFFFEFh
0x140019edd  mov     [rbx+50h], ecx
0x140019ee0  mov     rcx, [rax+60h]
0x140019ee4  mov     edx, [rcx+4088h]
0x140019eea  cmp     edx, 0FFFFFFFFh
0x140019eed  jz      loc_140019C39
0x140019ef3  mov     rax, [rsi+0D58h]
0x140019efa  test    rax, rax
0x140019efd  jz      loc_140019C39
0x140019f03  mov     rcx, [rsi+0D78h]
0x140019f0a  call    _guard_dispatch_icall
0x140019f0f  jmp     loc_140019C39
0x140019f14  mov     rcx, [rbx+128h]; Entry
0x140019f1b  test    rcx, rcx
0x140019f1e  jz      short loc_140019F2C
0x140019f20  call    ?RefCountedBufferRelease@CRefCountedBuffer@@QEAAXXZ; CRefCountedBuffer::RefCountedBufferRelease(void)
0x140019f25  mov     [rbx+128h], r14
0x140019f2c  call    Feature_PeriodicTrimImprovements__private_IsEnabledDeviceUsageNoInline
0x140019f31  test    eax, eax
0x140019f33  jz      loc_140019BDF
0x140019f39  mov     r14, [r13+10h]
0x140019f3d  test    r14, r14
0x140019f40  jz      short loc_140019F5C
0x140019f42  mov     r12, [rsi+18h]
0x140019f46  call    Feature_PeriodicTrimImprovements__private_IsEnabledDeviceUsageNoInline
0x140019f4b  test    eax, eax
0x140019f4d  jz      short loc_140019F5C
0x140019f4f  mov     rdx, [r14+10h]; struct VIDMM_PROCESS_ADAPTER_INFO *
0x140019f53  mov     rcx, [r12]; struct VIDMM_WORKER_THREAD *
0x140019f57  call    ?VidMmIncrementPeriodicTrimUniqueness@@YAXPEAUVIDMM_WORKER_THREAD@@PEAUVIDMM_PROCESS_ADAPTER_INFO@@@Z; VidMmIncrementPeriodicTrimUniqueness(VIDMM_WORKER_THREAD *,VIDMM_PROCESS_ADAPTER_INFO *)
0x140019f5c  xor     r14d, r14d
0x140019f5f  jmp     loc_140019BDF
0x140019f64  mov     eax, [rbx+40h]
0x140019f67  test    al, 4
0x140019f69  jz      short loc_140019F89
0x140019f6b  lock inc dword ptr [rdi+0BC0h]
0x140019f72  movzx   edx, word ptr [rdi+4]
0x140019f76  lea     rcx, [rsi+278h]
0x140019f7d  call    cs:__imp_RtlSetBitEx
0x140019f84  nop     dword ptr [rax+rax+00h]
0x140019f89  cmp     dword ptr [rbx+1E0h], 0
0x140019f90  ja      loc_14001A736
0x140019f96  xor     r14d, r14d
0x140019f99  jmp     loc_140019D07
0x140019f9e  test    dl, 4
0x140019fa1  jz      loc_14001AB6C
0x140019fa7  cmp     dword ptr [rbx+190h], 1
0x140019fae  jz      loc_14001AB69
0x140019fb4  mov     eax, [rbx+40h]
0x140019fb7  test    al, 2
0x140019fb9  jz      loc_14001AB74
0x140019fbf  mov     ecx, r12d
0x140019fc2  test    dword ptr [rbx+48h], 40080h
0x140019fc9  mov     [rbp+57h+arg_0], ecx
0x140019fcc  jz      short loc_140019FFF
0x140019fce  cmp     qword ptr [rbx+98h], 0
0x140019fd6  jz      short loc_140019FFF
0x140019fd8  cmp     qword ptr [rbx+0A0h], 0
0x140019fe0  jz      short loc_140019FFF
0x140019fe2  cmp     [rbp+57h+arg_10], 0
0x140019fe6  jz      short loc_140019FFF
0x140019fe8  xor     r9d, r9d
0x140019feb  lea     rcx, [rbp+57h+var_B0]
0x140019fef  xor     r8d, r8d
0x140019ff2  mov     qword ptr [rsp+110h+var_F0], r9
0x140019ff7  mov     rdx, rbx
0x140019ffa  call    VidSchiSubmitPresentHistoryToken
0x140019fff  test    r12d, r12d
0x14001a002  jnz     loc_14001ABB0
0x14001a008  lea     rdx, [rsi+7F8h]
0x14001a00f  mov     rcx, rsi
0x14001a012  call    VidSchiSignalRegisteredEvent
0x14001a017  cmp     [rbp+57h+arg_0], 0
0x14001a01b  mov     qword ptr [rbp+57h+arg_18], r14
0x14001a01f  jnz     short loc_14001A049
0x14001a021  jmp     short loc_14001A036
0x14001a023  test    ecx, ecx
0x14001a025  jnz     loc_140019D24
0x14001a02b  lea     r14, [rbx+0A8h]
0x14001a032  mov     qword ptr [rbp+57h+arg_18], r14
0x14001a036  cmp     dword ptr [rbx+30h], 0
0x14001a03a  jnz     short loc_14001A049
0x14001a03c  xor     r8d, r8d
0x14001a03f  xor     edx, edx
0x14001a041  mov     rcx, r15
0x14001a044  call    VidSchiUpdateLastCompletedPresentTimestamp
0x14001a049  cmp     dword ptr [rbx+30h], 3
0x14001a04d  jz      loc_14001A563
0x14001a053  mov     r14, qword ptr [rbp+57h+arg_18]
0x14001a057  xor     r8d, r8d
0x14001a05a  lock dec dword ptr [rsi+364h]
0x14001a061  lock dec dword ptr [rdi+0BCCh]
0x14001a068  lock dec dword ptr [r13+734h]
0x14001a070  mov     eax, [rbx+30h]
0x14001a073  sub     eax, 4
0x14001a076  cmp     eax, 1
0x14001a079  ja      loc_14001ABDF
0x14001a07f  cmp     dword ptr [rbx+30h], 0
0x14001a083  jz      loc_14001A4BC
0x14001a089  lock dec dword ptr [r15+318h]
  ... truncated ...
```
