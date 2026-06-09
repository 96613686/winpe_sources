# VidSchiProcessCompletedQueuePacketInternal(_VIDSCH_QUEUE_PACKET *)

- ea: `0x14001a260`
- end: `0x14001b34e`
- name: `?VidSchiProcessCompletedQueuePacketInternal@@YAPEAU_VIDSCH_QUEUE_PACKET@@PEAU1@@Z`
- size: `4334`
- prototype: `struct _VIDSCH_QUEUE_PACKET *__fastcall(struct _VIDSCH_QUEUE_PACKET *)`
- caller_count: `4`
- callee_count: `24`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14001978c`
- `0x1400197ac`
- `0x140019840`
- `0x140019db0`

## callees

- `0x14000cf08`
- `0x14000d2dc`
- `0x14000eda0`
- `0x140010760`
- `0x140018c20`
- `0x140018ff4`
- `0x14001a260`
- `0x14001b5f0`
- `0x14001ba84`
- `0x14001c360`
- `0x14001c44c`
- `0x14001ca80`
- `0x14001cc60`
- `0x14001f798`
- `0x14001f7fc`
- `0x140020288`
- `0x140026334`
- `0x1400265c0`
- `0x14003308c`
- `0x140034800`
- `0x14003c5ac`
- `0x140043aec`
- `0x140045000`
- `0x140058760`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14001abf9`
- `ntoskrnl!ObfDereferenceObject` at `0x14001abf9`
- `ntoskrnl!KfRaiseIrql` at `0x14001a2c1`
- `ntoskrnl!KfRaiseIrql` at `0x14001a7c0`
- `ntoskrnl!KfRaiseIrql` at `0x14001a886`
- `ntoskrnl!KfRaiseIrql` at `0x14001a937`
- `ntoskrnl!KfRaiseIrql` at `0x14001a2c1`
- `ntoskrnl!KfRaiseIrql` at `0x14001a7c0`
- `ntoskrnl!KfRaiseIrql` at `0x14001a886`
- `ntoskrnl!KfRaiseIrql` at `0x14001a937`
- `ntoskrnl!KeLowerIrql` at `0x14001a851`
- `ntoskrnl!KeLowerIrql` at `0x14001a915`
- `ntoskrnl!KeLowerIrql` at `0x14001a97e`
- `ntoskrnl!KeLowerIrql` at `0x14001aaec`
- `ntoskrnl!KeLowerIrql` at `0x14001a851`
- `ntoskrnl!KeLowerIrql` at `0x14001a915`
- `ntoskrnl!KeLowerIrql` at `0x14001a97e`
- `ntoskrnl!KeLowerIrql` at `0x14001aaec`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001a2db`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001a4dc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001a7da`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001a8a0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001a952`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001a2db`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001a4dc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001a7da`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001a8a0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001a952`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001a51c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001a841`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001a905`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001a96e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001aadc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001a51c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001a841`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001a905`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001a96e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001aadc`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14001ab32`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14001ab32`
- `ntoskrnl!RtlSetBitEx` at `0x14001a65d`
- `ntoskrnl!RtlSetBitEx` at `0x14001a65d`
- `ntoskrnl!KeSetEvent` at `0x14001a825`
- `ntoskrnl!KeSetEvent` at `0x14001a8ec`
- `ntoskrnl!KeSetEvent` at `0x14001a9aa`
- `ntoskrnl!KeSetEvent` at `0x14001a9cc`
- `ntoskrnl!KeSetEvent` at `0x14001ab81`
- `ntoskrnl!KeSetEvent` at `0x14001abe6`
- `ntoskrnl!KeSetEvent` at `0x14001af4e`
- `ntoskrnl!KeSetEvent` at `0x14001b14f`
- `ntoskrnl!KeSetEvent` at `0x14001b300`
- `ntoskrnl!KeSetEvent` at `0x14001a825`
- `ntoskrnl!KeSetEvent` at `0x14001a8ec`
- `ntoskrnl!KeSetEvent` at `0x14001a9aa`
- `ntoskrnl!KeSetEvent` at `0x14001a9cc`
- `ntoskrnl!KeSetEvent` at `0x14001ab81`
- `ntoskrnl!KeSetEvent` at `0x14001abe6`
- `ntoskrnl!KeSetEvent` at `0x14001af4e`
- `ntoskrnl!KeSetEvent` at `0x14001b14f`
- `ntoskrnl!KeSetEvent` at `0x14001b300`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001abc0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001abc0`
- `watchdog!WdLogSingleEntry5` at `0x14001b338`
- `watchdog!WdLogSingleEntry5` at `0x14001b338`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x14001b311`

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
  unsigned int v104[2]; // [rsp+20h] [rbp-99h]
  unsigned int v105[2]; // [rsp+28h] [rbp-91h]
  __int64 v106; // [rsp+60h] [rbp-59h] BYREF
  __int64 v107; // [rsp+68h] [rbp-51h] BYREF
  __int64 **v108; // [rsp+70h] [rbp-49h]
  char v109; // [rsp+78h] [rbp-41h]
  int v110; // [rsp+7Ch] [rbp-3Dh]
  struct _KLOCK_QUEUE_HANDLE v111; // [rsp+80h] [rbp-39h] BYREF
  __int64 v112; // [rsp+98h] [rbp-21h]
  __int64 v113; // [rsp+A0h] [rbp-19h]
  __int64 v114; // [rsp+A8h] [rbp-11h]
  __int64 v115; // [rsp+B0h] [rbp-9h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+B8h] [rbp-1h] BYREF
  int v117; // [rsp+120h] [rbp+67h]
  KIRQL v118; // [rsp+120h] [rbp+67h]
  KIRQL v119; // [rsp+120h] [rbp+67h]
  KIRQL v120; // [rsp+128h] [rbp+6Fh]
  int v121; // [rsp+130h] [rbp+77h]
  unsigned int v122; // [rsp+130h] [rbp+77h]
  unsigned int v123; // [rsp+138h] [rbp+7Fh]
  unsigned int *v124; // [rsp+138h] [rbp+7Fh]
  char v125; // [rsp+138h] [rbp+7Fh]

  v3 = *((_QWORD *)a1 + 11);
  v4 = *((_DWORD *)a1 + 16);
  v113 = v3;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v6 = *(_QWORD *)(v3 + 96);
  v7 = *(_QWORD *)(v3 + 104);
  v114 = v6;
  v8 = *(_QWORD *)(v6 + 24);
  if ( (v4 & 0x20) != 0 && (byte_140086201 & 1) != 0 )
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
  v120 = KfRaiseIrql(2u);
  KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v8 + 2096), &LockHandle);
  v11 = *((_DWORD *)a1 + 20);
  v106 = v8;
  v109 = 0;
  v110 = 2;
  v108 = (__int64 **)&v107;
  v107 = (__int64)&v107;
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
    *(_QWORD *)v105 = a1;
    *(_QWORD *)v104 = v3;
    WdLogSingleEntry5(0, 281, 512);
    WdLogGlobalForLineNumber = 921;
    JUMPOUT(0x14001B34ELL);
  }
  if ( (*((_DWORD *)a1 + 20) & 0x20) != 0 )
    VidSchiAdvanceContextSubmissionId((struct HwQueueStagingList *)&v106, a1);
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
  v117 = 0;
  v115 = 0;
  if ( v15 == v3 + 672 )
  {
    if ( (*(_DWORD *)(v3 + 192) & 0x200) != 0 )
    {
      v29 = 14037;
LABEL_217:
      v28 = 10;
      goto LABEL_43;
    }
    if ( (*(_DWORD *)(v3 + 192) & 0x10) == 0
      && (*(_DWORD *)(v3 + 192) & 0x40) == 0
      && (*(_DWORD *)(v3 + 192) & 0x100) == 0 )
    {
      v28 = 0;
      v29 = 14070;
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
      v115 = v16;
      *(_DWORD *)(v16 + 80) = v17 | 2;
    }
    if ( (*(_DWORD *)(v3 + 192) & 0x200) != 0
      && (((unsigned __int8)(*(_DWORD *)(v3 + 192) >> 9) | *(_BYTE *)(v3 + 192)) & 2) == 0 )
    {
      v29 = 14018;
      goto LABEL_217;
    }
  }
  v18 = *((_DWORD *)a1 + 12);
  if ( v18 == 5 )
  {
    if ( (*((_DWORD *)a1 + 20) & 4) == 0 )
    {
      if ( (byte_140086204 & 4) != 0 )
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
      VidSchiCompleteSignalCommmand((HwQueueStagingList *)&v106, (__int64)a1, 1);
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
    v121 = v21;
    v22 = (_DWORD *)((char *)a1 + 168);
    v23 = *((_DWORD *)a1 + 42);
    v123 = v23;
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
            v117 = 1;
            VidSchiUpdateLastCompletedPresentTimestamp(*((_QWORD *)a1 + 11), 1, 0);
            v23 = v123;
          }
          if ( (*((_DWORD *)a1 + 220) & 0x3FF) != 0 )
          {
            v94 = *(unsigned int *)(v3 + 88);
            v95 = *(_QWORD *)(v8 + 776);
            if ( (unsigned int)v94 < *(_DWORD *)(v8 + 848) )
              v95 += 8 * v94;
            VidSchiUnreferencePrimaryAllocations(
              (struct HwQueueStagingList *)&v106,
              (struct _VIDSCH_GLOBAL *)v8,
              v23,
              (struct _VIDSCH_QUEUE_PACKET *)((char *)a1 + 880),
              *((_DWORD *)a1 + 104),
              1 << *(_BYTE *)(*(_QWORD *)v95 + 6LL),
              0,
              0,
              (unsigned int *)a1 + 224);
          }
          v25 = v117;
          if ( !v117 )
          {
LABEL_62:
            v117 = v25;
            if ( (*((_DWORD *)a1 + 18) & 0x40080) != 0 && *((_QWORD *)a1 + 19) && *((_QWORD *)a1 + 20) && v121 )
              VidSchiSubmitPresentHistoryToken((struct HwQueueStagingList *)&v106, a1, 0, 0, 0);
            if ( v14 )
            {
              _InterlockedDecrement((volatile signed __int32 *)(v8 + 880));
              DecrementNumberOfQueuedFlipPerSource((struct _VIDSCH_GLOBAL *)v8, v123);
              _InterlockedDecrement((volatile signed __int32 *)(v7 + 1836));
              _InterlockedDecrement((volatile signed __int32 *)(v7 + 4LL * v103 + 1772));
            }
            VidSchiSignalRegisteredEvent(v8, v8 + 2040);
            v124 = (unsigned int *)((char *)a1 + 168);
            if ( v117 )
              goto LABEL_75;
            goto LABEL_73;
          }
LABEL_28:
          if ( v123 != -1 && (*((_DWORD *)a1 + 18) & 0x40000) == 0 )
          {
            v112 = v123;
            _InterlockedDecrement((volatile signed __int32 *)(v7 + 4LL * v123 + 1708));
            v26 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v7 + 48) + 32LL)
                                        + 8LL * *(unsigned int *)(*(_QWORD *)(v7 + 40) + 4LL))
                            + 8LL * v123
                            + 88);
            if ( (*((_DWORD *)a1 + 18) & 0x80u) == 0 )
            {
              _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(v8 + 8LL * v123 + 7584) + 8LL));
              ++**(_DWORD **)(v8 + 8LL * v123 + 7584);
            }
            _InterlockedDecrement((volatile signed __int32 *)(v26 + 8));
            ++*(_DWORD *)v26;
            if ( (*((_DWORD *)a1 + 18) & 0x20000) != 0 )
            {
              memset(&v111, 0, sizeof(v111));
              KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v8 + 2104), &v111);
              v27 = v112;
              *(_DWORD *)(v7 + 4 * v112 + 516) = *((_DWORD *)a1 + 98);
              *(_QWORD *)(v7 + 8 * v27 + 584) = *((_QWORD *)a1 + 17);
              *(_QWORD *)(v7 + 8 * v27 + 712) = *((_QWORD *)a1 + 18);
              KeReleaseInStackQueuedSpinLockFromDpcLevel(&v111);
            }
            v25 = v117;
          }
          goto LABEL_62;
        }
        v14 = v21;
      }
      v25 = v21;
    }
    v117 = v25;
    if ( !v25 )
      goto LABEL_62;
    LOBYTE(v19) = 1;
    VidSchiUpdateLastCompletedPresentTimestamp(*((_QWORD *)a1 + 11), v19, 0);
    v25 = v117;
    goto LABEL_28;
  }
  v22 = (_DWORD *)((char *)a1 + 168);
  v124 = (unsigned int *)((char *)a1 + 168);
LABEL_73:
  if ( !*((_DWORD *)a1 + 12) )
    VidSchiUpdateLastCompletedPresentTimestamp(v3, 0, 0);
LABEL_75:
  if ( *((_DWORD *)a1 + 12) != 3 || *v22 == -1 )
  {
    v35 = v124;
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
    v112 = v66;
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
    v35 = v124;
    v24 = !_BitScanForward((unsigned int *)&v70, v69);
    v71 = -1;
    if ( !v24 )
      v71 = v70;
    if ( v69 )
    {
      v72 = v112;
      do
      {
        v73 = v71;
        v74 = v71;
        v71 = -1;
        _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(v72 + 8LL * *v124 + 3528) + 304 * v74 + 192));
        v69 &= ~(1 << v73);
        v24 = !_BitScanForward((unsigned int *)&v74, v69);
        if ( !v24 )
          v71 = v74;
      }
      while ( v69 );
      v3 = v113;
      v68 = (_DWORD *)((char *)a1 + 880);
      v6 = v114;
    }
    if ( (*((_DWORD *)a1 + 18) & 0x800000) != 0 )
      v75 = ((unsigned __int16)*v68 | (unsigned __int16)(*v68 >> 10)) & 0x3FF;
    else
      v75 = (1 << *(_DWORD *)(v8 + 160)) - 1;
    v24 = !_BitScanForward((unsigned int *)&v76, v75);
    v77 = -1;
    v122 = v75;
    if ( !v24 )
      v77 = v76;
    while ( v75 )
    {
      v78 = *v35;
      v79 = v77;
      v80 = *(_QWORD *)(v8 + 8 * v78 + 3528);
      v125 = v77;
      v113 = v78;
      v81 = *(int *)(v80 + 304LL * (unsigned int)v77 + 188);
      if ( (int)v81 > -1
        && *(_DWORD *)(160 * v81 + *(_QWORD *)(v8 + 3656) + 112) == 1
        && VidSchiCheckPlaneIndependentFlipCondition((struct _VIDSCH_GLOBAL *)v8, v78, v77) )
      {
        VidSchiFlushPendingTokenList((struct HwQueueStagingList *)&v106, (struct _VIDSCH_GLOBAL *)v8);
        v75 = v122;
        v79 = v125;
      }
      v77 = -1;
      v75 &= ~(1 << v79);
      v24 = !_BitScanForward((unsigned int *)&v82, v75);
      v122 = v75;
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
  if ( !v117 )
    goto LABEL_91;
  v36 = (struct _KEVENT *)(v7 + 128);
  memset(&v111, 0, sizeof(v111));
  v118 = KfRaiseIrql(2u);
  KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v8 + 2112), &v111);
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
  v6 = v114;
LABEL_90:
  KeReleaseInStackQueuedSpinLockFromDpcLevel(&v111);
  KeLowerIrql(v118);
LABEL_91:
  if ( v14 )
  {
    VidSchiSignalRegisteredEvent(v8, v7 + 144);
    VidSchiSignalRegisteredEvent(v8, v8 + 2024);
    *(_QWORD *)(v8 + 1968) = MEMORY[0xFFFFF78000000320];
    KeSetEvent((PRKEVENT)(v8 + 1936), 0, 0);
  }
  v40 = (struct _KEVENT *)(v6 + 424);
  memset(&v111, 0, sizeof(v111));
  v119 = KfRaiseIrql(2u);
  KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v8 + 2112), &v111);
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
  KeReleaseInStackQueuedSpinLockFromDpcLevel(&v111);
  KeLowerIrql(v119);
  v44 = (struct _KEVENT *)(v8 + 2008);
  memset(&v111, 0, sizeof(v111));
  v45 = KfRaiseIrql(2u);
  KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v8 + 2112), &v111);
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
  KeReleaseInStackQueuedSpinLockFromDpcLevel(&v111);
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
  VidSchiFreeQueuePacket(v3);
  if ( v110 != 1 )
    goto LABEL_118;
  v55 = *(_DWORD *)(v106 + 312);
  if ( v55 == 1 )
  {
    if ( (__int64 *)v107 == &v107 )
      goto LABEL_118;
    v96 = (__int64 *)(v106 + 288);
    if ( *(__int64 **)(*v96 + 8) == v96 )
    {
      v97 = *(__int64 ***)(v106 + 296);
      if ( *v97 == v96 && *(__int64 **)(v107 + 8) == &v107 && *v108 == &v107 )
      {
        *v97 = &v107;
        v96[1] = (__int64)v108;
        *v108 = v96;
        v98 = v107;
        v108 = v97;
        if ( *(__int64 **)(v107 + 8) == &v107 && *v97 == &v107 )
        {
          *v97 = (__int64 *)v107;
          *(_QWORD *)(v98 + 8) = v97;
          v108 = (__int64 **)&v107;
          v107 = (__int64)&v107;
          goto LABEL_209;
        }
      }
    }
LABEL_182:
    __fastfail(3u);
  }
  if ( v55 == 2 )
  {
    v61 = (__int64 *)v107;
    v62 = 0;
    if ( (__int64 *)v107 != &v107 )
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
          v101 = v106 + 288;
          v102 = *(__int64 ***)(v106 + 296);
          if ( *v102 != (__int64 *)(v106 + 288) )
            goto LABEL_182;
          *v61 = v101;
          v61[1] = (__int64)v102;
          *v102 = v61;
          *(_QWORD *)(v101 + 8) = v61;
          v62 = 1;
        }
        v61 = v63;
      }
      while ( v63 != &v107 );
      if ( v62 )
      {
LABEL_209:
        *(_BYTE *)(v106 + 304) = 0;
        v99 = (struct _KEVENT *)(v106 + 1544);
        *(_QWORD *)(v106 + 1576) = MEMORY[0xFFFFF78000000320];
        KeSetEvent(v99, 0, 0);
      }
    }
  }
LABEL_118:
  for ( j = (_QWORD *)v107; (__int64 *)v107 != &v107; j = (_QWORD *)v107 )
  {
    HwQueueStagingList::ProcessHwQueue((HwQueueStagingList *)&v106, (struct VIDSCH_HW_QUEUE *)(j - 22), 0);
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
  v109 = 1;
  KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  KeLowerIrql(v120);
  HwQueueStagingList::~HwQueueStagingList((HwQueueStagingList *)&v106);
  return (struct _VIDSCH_QUEUE_PACKET *)v115;
}

```

## disassembly

```asm
0x14001a260  push    rbp
0x14001a262  push    rbx
0x14001a263  push    rsi
0x14001a264  push    rdi
0x14001a265  push    r13
0x14001a267  push    r14
0x14001a269  push    r15
0x14001a26b  lea     rbp, [rsp-27h]
0x14001a270  sub     rsp, 0E0h
0x14001a277  mov     r15, [rcx+58h]
0x14001a27b  xor     eax, eax
0x14001a27d  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x14001a281  xorps   xmm0, xmm0
0x14001a284  mov     eax, [rcx+40h]
0x14001a287  mov     rbx, rcx
0x14001a28a  mov     [rbp+57h+var_70], r15
0x14001a28e  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x14001a292  mov     rdi, [r15+60h]
0x14001a296  mov     r13, [r15+68h]
0x14001a29a  mov     [rbp+57h+var_68], rdi
0x14001a29e  mov     rsi, [rdi+18h]
0x14001a2a2  test    al, 20h
0x14001a2a4  jnz     loc_14001AF5F
0x14001a2aa  xor     r14d, r14d
0x14001a2ad  mov     [rsp+110h+var_38], r12
0x14001a2b5  cmp     [rbx+30h], r14d
0x14001a2b9  jz      loc_14001A5F4
0x14001a2bf  mov     cl, 2; NewIrql
0x14001a2c1  call    cs:__imp_KfRaiseIrql
0x14001a2c8  nop     dword ptr [rax+rax+00h]
0x14001a2cd  lea     rcx, [rsi+830h]; SpinLock
0x14001a2d4  mov     [rbp+57h+arg_8], al
0x14001a2d7  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x14001a2db  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14001a2e2  nop     dword ptr [rax+rax+00h]
0x14001a2e7  mov     ecx, [rbx+50h]
0x14001a2ea  lea     rax, [rbp+57h+var_A8]
0x14001a2ee  mov     [rbp+57h+var_B0], rsi
0x14001a2f2  xorps   xmm0, xmm0
0x14001a2f5  mov     [rbp+57h+var_98], 0
0x14001a2f9  mov     [rbp+57h+var_94], 2
0x14001a300  movups  [rbp+57h+var_A8], xmm0
0x14001a304  mov     qword ptr [rbp+57h+var_A8+8], rax
0x14001a308  lea     rax, [rbp+57h+var_A8]
0x14001a30c  mov     qword ptr [rbp+57h+var_A8], rax
0x14001a310  test    cl, 10h
0x14001a313  jnz     loc_14001A5B6
0x14001a319  mov     eax, [rbx+34h]
0x14001a31c  cmp     eax, 10h
0x14001a31f  jz      loc_14001B311
0x14001a325  mov     eax, [rbx+34h]
0x14001a328  test    eax, eax
0x14001a32a  jz      loc_14001B311
0x14001a330  mov     eax, [rbx+50h]
0x14001a333  test    al, 20h
0x14001a335  jnz     loc_14001B1AA
0x14001a33b  mov     rax, ds:0FFFFF78000000320h
0x14001a345  mov     [rbx+38h], rax
0x14001a349  lea     rax, [rbx+20h]
0x14001a34d  mov     dword ptr [rbx+34h], 10h
0x14001a354  mov     rdx, [rax]
0x14001a357  cmp     [rdx+8], rax
0x14001a35b  jnz     loc_14001AF18
0x14001a361  mov     rcx, [rax+8]
0x14001a365  cmp     [rcx], rax
0x14001a368  jnz     loc_14001AF18
0x14001a36e  mov     [rcx], rdx
0x14001a371  lea     rax, [r15+2A0h]
0x14001a378  mov     [rdx+8], rcx
0x14001a37c  mov     r12d, r14d
0x14001a37f  mov     rcx, [rax]
0x14001a382  mov     [rbp+57h+arg_0], r14d
0x14001a386  mov     [rbp+57h+var_60], r14
0x14001a38a  cmp     rcx, rax
0x14001a38d  jz      loc_14001A561
0x14001a393  lea     rdx, [rcx-20h]
0x14001a397  mov     ecx, [rcx+30h]
0x14001a39a  mov     eax, ecx
0x14001a39c  and     al, 3
0x14001a39e  cmp     al, 1
0x14001a3a0  jnz     short loc_14001A3AC
0x14001a3a2  or      ecx, 2
0x14001a3a5  mov     [rbp+57h+var_60], rdx
0x14001a3a9  mov     [rdx+50h], ecx
0x14001a3ac  mov     eax, [r15+0C0h]
0x14001a3b3  bt      eax, 9
0x14001a3b7  jb      loc_14001B1C3
0x14001a3bd  mov     eax, [rbx+30h]
0x14001a3c0  cmp     eax, 5
0x14001a3c3  jz      loc_14001A530
0x14001a3c9  cmp     eax, 3
0x14001a3cc  jz      loc_14001AE70
0x14001a3d2  mov     eax, [rbx+50h]
0x14001a3d5  test    al, 8
0x14001a3d7  jnz     loc_14001AFB9
0x14001a3dd  cmp     dword ptr [rbx+30h], 0
0x14001a3e1  jz      loc_14001A644
0x14001a3e7  mov     edx, [rbx+48h]
0x14001a3ea  mov     ecx, edx
0x14001a3ec  mov     eax, edx
0x14001a3ee  and     ecx, 4000h
0x14001a3f4  and     eax, 40020h
0x14001a3f9  cmp     eax, 40000h
0x14001a3fe  jnz     loc_14001A703
0x14001a404  bt      edx, 0Ah
0x14001a408  jb      loc_14001B237
0x14001a40e  mov     r8d, 1
0x14001a414  mov     [rbp+57h+arg_10], r8d
0x14001a418  lea     r14, [rbx+0A8h]
0x14001a41f  mov     r10d, [r14]
0x14001a422  mov     qword ptr [rbp+57h+arg_18], r10
0x14001a426  bt      edx, 12h
0x14001a42a  jnb     loc_14001A67E
0x14001a430  xor     eax, eax
0x14001a432  test    ecx, ecx
0x14001a434  mov     ecx, r8d
0x14001a437  cmovz   ecx, eax
0x14001a43a  mov     [rbp+57h+arg_0], ecx
0x14001a43d  test    ecx, ecx
0x14001a43f  jz      loc_14001A6A2
0x14001a445  mov     rcx, [rbx+58h]
0x14001a449  xor     r8d, r8d
0x14001a44c  mov     dl, 1
0x14001a44e  call    VidSchiUpdateLastCompletedPresentTimestamp
0x14001a453  mov     ecx, [rbp+57h+arg_0]
0x14001a456  mov     rdx, qword ptr [rbp+57h+arg_18]
0x14001a45a  cmp     edx, 0FFFFFFFFh
0x14001a45d  jz      loc_14001A6A2
0x14001a463  test    dword ptr [rbx+48h], 40000h
0x14001a46a  jnz     loc_14001A6A2
0x14001a470  mov     r8d, edx
0x14001a473  mov     [rbp+57h+var_78], r8
0x14001a477  lock dec dword ptr [r13+r8*4+6ACh]
0x14001a480  mov     rax, [r13+28h]
0x14001a484  mov     edx, [rax+4]
0x14001a487  mov     rax, [r13+30h]
0x14001a48b  mov     rcx, [rax+20h]
0x14001a48f  mov     rax, [rcx+rdx*8]
0x14001a493  mov     rcx, [rax+r8*8+58h]
0x14001a498  mov     eax, [rbx+48h]
0x14001a49b  test    al, al
0x14001a49d  js      short loc_14001A4B5
0x14001a49f  mov     rax, [rsi+r8*8+1DA0h]
0x14001a4a7  lock dec dword ptr [rax+8]
0x14001a4ab  mov     rax, [rsi+r8*8+1DA0h]
0x14001a4b3  inc     dword ptr [rax]
0x14001a4b5  lock dec dword ptr [rcx+8]
0x14001a4b9  inc     dword ptr [rcx]
0x14001a4bb  test    dword ptr [rbx+48h], 20000h
0x14001a4c2  jz      short loc_14001A528
0x14001a4c4  xorps   xmm0, xmm0
0x14001a4c7  lea     rcx, [rsi+838h]; SpinLock
0x14001a4ce  xor     eax, eax
0x14001a4d0  lea     rdx, [rbp+57h+var_90]; LockHandle
0x14001a4d4  movups  xmmword ptr [rbp+57h+var_90.LockQueue.Next], xmm0
0x14001a4d8  mov     qword ptr [rbp+57h+var_90.OldIrql], rax
0x14001a4dc  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14001a4e3  nop     dword ptr [rax+rax+00h]
0x14001a4e8  mov     eax, [rbx+188h]
0x14001a4ee  mov     rcx, [rbp+57h+var_78]
0x14001a4f2  mov     [r13+rcx*4+204h], eax
0x14001a4fa  mov     rax, [rbx+88h]
0x14001a501  mov     [r13+rcx*8+248h], rax
0x14001a509  mov     rax, [rbx+90h]
0x14001a510  mov     [r13+rcx*8+2C8h], rax
0x14001a518  lea     rcx, [rbp+57h+var_90]; LockHandle
0x14001a51c  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14001a523  nop     dword ptr [rax+rax+00h]
0x14001a528  mov     ecx, [rbp+57h+arg_0]
0x14001a52b  jmp     loc_14001A6A2
0x14001a530  mov     eax, [rbx+50h]
0x14001a533  test    al, 4
0x14001a535  jnz     loc_14001A3D2
0x14001a53b  movzx   eax, cs:byte_140086204
0x14001a542  and     al, 4
0x14001a544  mov     byte ptr [rbp+57h+arg_10], al
0x14001a547  jnz     loc_14001ADCD
0x14001a54d  mov     r8b, 1
0x14001a550  lea     rcx, [rbp+57h+var_B0]
0x14001a554  mov     rdx, rbx
0x14001a557  call    VidSchiCompleteSignalCommmand
0x14001a55c  jmp     loc_14001A3D2
0x14001a561  mov     eax, [r15+0C0h]
0x14001a568  bt      eax, 9
0x14001a56c  jb      loc_14001B1BB
0x14001a572  mov     eax, [r15+0C0h]
0x14001a579  test    al, 10h
0x14001a57b  jnz     loc_14001A3BD
0x14001a581  mov     eax, [r15+0C0h]
0x14001a588  test    al, 40h
0x14001a58a  jnz     loc_14001A3BD
0x14001a590  mov     eax, [r15+0C0h]
0x14001a597  bt      eax, 8
0x14001a59b  jb      loc_14001A3BD
0x14001a5a1  xor     edx, edx
0x14001a5a3  mov     r8d, 36F6h
0x14001a5a9  mov     rcx, r15
0x14001a5ac  call    VidSchiUpdateContextStatus
0x14001a5b1  jmp     loc_14001A3BD
0x14001a5b6  mov     rax, [rbx+58h]
0x14001a5ba  and     ecx, 0FFFFFFEFh
0x14001a5bd  mov     [rbx+50h], ecx
0x14001a5c0  mov     rcx, [rax+60h]
0x14001a5c4  mov     edx, [rcx+4088h]
0x14001a5ca  cmp     edx, 0FFFFFFFFh
0x14001a5cd  jz      loc_14001A319
0x14001a5d3  mov     rax, [rsi+0D58h]
0x14001a5da  test    rax, rax
0x14001a5dd  jz      loc_14001A319
0x14001a5e3  mov     rcx, [rsi+0D78h]
0x14001a5ea  call    _guard_dispatch_icall
0x14001a5ef  jmp     loc_14001A319
0x14001a5f4  mov     rcx, [rbx+128h]; Entry
0x14001a5fb  test    rcx, rcx
0x14001a5fe  jz      short loc_14001A60C
0x14001a600  call    ?RefCountedBufferRelease@CRefCountedBuffer@@QEAAXXZ; CRefCountedBuffer::RefCountedBufferRelease(void)
0x14001a605  mov     [rbx+128h], r14
0x14001a60c  call    Feature_PeriodicTrimImprovements__private_IsEnabledDeviceUsageNoInline
0x14001a611  test    eax, eax
0x14001a613  jz      loc_14001A2BF
0x14001a619  mov     r14, [r13+10h]
0x14001a61d  test    r14, r14
0x14001a620  jz      short loc_14001A63C
0x14001a622  mov     r12, [rsi+18h]
0x14001a626  call    Feature_PeriodicTrimImprovements__private_IsEnabledDeviceUsageNoInline
0x14001a62b  test    eax, eax
0x14001a62d  jz      short loc_14001A63C
0x14001a62f  mov     rdx, [r14+10h]; struct VIDMM_PROCESS_ADAPTER_INFO *
0x14001a633  mov     rcx, [r12]; struct VIDMM_WORKER_THREAD *
0x14001a637  call    ?VidMmIncrementPeriodicTrimUniqueness@@YAXPEAUVIDMM_WORKER_THREAD@@PEAUVIDMM_PROCESS_ADAPTER_INFO@@@Z; VidMmIncrementPeriodicTrimUniqueness(VIDMM_WORKER_THREAD *,VIDMM_PROCESS_ADAPTER_INFO *)
0x14001a63c  xor     r14d, r14d
0x14001a63f  jmp     loc_14001A2BF
0x14001a644  mov     eax, [rbx+40h]
0x14001a647  test    al, 4
0x14001a649  jz      short loc_14001A669
0x14001a64b  lock inc dword ptr [rdi+0BC0h]
0x14001a652  movzx   edx, word ptr [rdi+4]
0x14001a656  lea     rcx, [rsi+278h]
0x14001a65d  call    cs:__imp_RtlSetBitEx
0x14001a664  nop     dword ptr [rax+rax+00h]
0x14001a669  cmp     dword ptr [rbx+1E0h], 0
0x14001a670  ja      loc_14001AE16
0x14001a676  xor     r14d, r14d
0x14001a679  jmp     loc_14001A3E7
0x14001a67e  test    dl, 4
0x14001a681  jz      loc_14001B24C
0x14001a687  cmp     dword ptr [rbx+190h], 1
0x14001a68e  jz      loc_14001B249
0x14001a694  mov     eax, [rbx+40h]
0x14001a697  test    al, 2
0x14001a699  jz      loc_14001B254
0x14001a69f  mov     ecx, r12d
0x14001a6a2  test    dword ptr [rbx+48h], 40080h
0x14001a6a9  mov     [rbp+57h+arg_0], ecx
0x14001a6ac  jz      short loc_14001A6DF
0x14001a6ae  cmp     qword ptr [rbx+98h], 0
0x14001a6b6  jz      short loc_14001A6DF
0x14001a6b8  cmp     qword ptr [rbx+0A0h], 0
0x14001a6c0  jz      short loc_14001A6DF
0x14001a6c2  cmp     [rbp+57h+arg_10], 0
0x14001a6c6  jz      short loc_14001A6DF
0x14001a6c8  xor     r9d, r9d
0x14001a6cb  lea     rcx, [rbp+57h+var_B0]
0x14001a6cf  xor     r8d, r8d
0x14001a6d2  mov     qword ptr [rsp+110h+var_F0], r9
0x14001a6d7  mov     rdx, rbx
0x14001a6da  call    VidSchiSubmitPresentHistoryToken
0x14001a6df  test    r12d, r12d
0x14001a6e2  jnz     loc_14001B290
0x14001a6e8  lea     rdx, [rsi+7F8h]
0x14001a6ef  mov     rcx, rsi
0x14001a6f2  call    VidSchiSignalRegisteredEvent
0x14001a6f7  cmp     [rbp+57h+arg_0], 0
0x14001a6fb  mov     qword ptr [rbp+57h+arg_18], r14
0x14001a6ff  jnz     short loc_14001A729
0x14001a701  jmp     short loc_14001A716
0x14001a703  test    ecx, ecx
0x14001a705  jnz     loc_14001A404
0x14001a70b  lea     r14, [rbx+0A8h]
0x14001a712  mov     qword ptr [rbp+57h+arg_18], r14
0x14001a716  cmp     dword ptr [rbx+30h], 0
0x14001a71a  jnz     short loc_14001A729
0x14001a71c  xor     r8d, r8d
0x14001a71f  xor     edx, edx
0x14001a721  mov     rcx, r15
0x14001a724  call    VidSchiUpdateLastCompletedPresentTimestamp
0x14001a729  cmp     dword ptr [rbx+30h], 3
0x14001a72d  jz      loc_14001AC43
0x14001a733  mov     r14, qword ptr [rbp+57h+arg_18]
0x14001a737  xor     r8d, r8d
0x14001a73a  lock dec dword ptr [rsi+364h]
0x14001a741  lock dec dword ptr [rdi+0BCCh]
0x14001a748  lock dec dword ptr [r13+734h]
0x14001a750  mov     eax, [rbx+30h]
0x14001a753  sub     eax, 4
0x14001a756  cmp     eax, 1
0x14001a759  ja      loc_14001B2BF
0x14001a75f  cmp     dword ptr [rbx+30h], 0
0x14001a763  jz      loc_14001AB9C
0x14001a769  lock dec dword ptr [r15+318h]
  ... truncated ...
```
