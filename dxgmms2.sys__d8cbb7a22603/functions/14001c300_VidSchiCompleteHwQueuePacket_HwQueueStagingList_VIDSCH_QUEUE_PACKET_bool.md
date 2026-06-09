# VidSchiCompleteHwQueuePacket(HwQueueStagingList *,_VIDSCH_QUEUE_PACKET *,bool)

- ea: `0x14001c300`
- end: `0x14001d3f4`
- name: `?VidSchiCompleteHwQueuePacket@@YAXPEAVHwQueueStagingList@@PEAU_VIDSCH_QUEUE_PACKET@@_N@Z`
- size: `4340`
- prototype: `void __fastcall(struct HwQueueStagingList *, struct _VIDSCH_QUEUE_PACKET *, bool)`
- caller_count: `6`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140007890`
- `0x140017e70`
- `0x140018014`
- `0x14001c1a0`
- `0x14003fdb8`
- `0x1400442b4`

## callees

- `0x14000d02c`
- `0x14001b910`
- `0x14001bc80`
- `0x14001c300`
- `0x14001d400`
- `0x14001d46c`
- `0x14001dc38`
- `0x14001dc9c`
- `0x14001e42c`
- `0x14001e5d8`
- `0x14001e670`
- `0x14001e728`
- `0x140043c5c`
- `0x140058f50`
- `0x140059030`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14001c589`
- `ntoskrnl!KfRaiseIrql` at `0x14001c7a4`
- `ntoskrnl!KfRaiseIrql` at `0x14001cf2e`
- `ntoskrnl!KfRaiseIrql` at `0x14001cfea`
- `ntoskrnl!KfRaiseIrql` at `0x14001d0a2`
- `ntoskrnl!KfRaiseIrql` at `0x14001c589`
- `ntoskrnl!KfRaiseIrql` at `0x14001c7a4`
- `ntoskrnl!KfRaiseIrql` at `0x14001cf2e`
- `ntoskrnl!KfRaiseIrql` at `0x14001cfea`
- `ntoskrnl!KfRaiseIrql` at `0x14001d0a2`
- `ntoskrnl!KeLowerIrql` at `0x14001c614`
- `ntoskrnl!KeLowerIrql` at `0x14001c7eb`
- `ntoskrnl!KeLowerIrql` at `0x14001cfc4`
- `ntoskrnl!KeLowerIrql` at `0x14001d080`
- `ntoskrnl!KeLowerIrql` at `0x14001d12d`
- `ntoskrnl!KeLowerIrql` at `0x14001c614`
- `ntoskrnl!KeLowerIrql` at `0x14001c7eb`
- `ntoskrnl!KeLowerIrql` at `0x14001cfc4`
- `ntoskrnl!KeLowerIrql` at `0x14001d080`
- `ntoskrnl!KeLowerIrql` at `0x14001d12d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001c5a4`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001c7bf`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001ce7a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001cf49`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001d005`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001d0bd`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001c5a4`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001c7bf`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001ce7a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001cf49`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001d005`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001d0bd`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001c604`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001c7db`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001ceba`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001cfb4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001d070`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001d11d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001c604`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001c7db`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001ceba`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001cfb4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001d070`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001d11d`
- `ntoskrnl!ExQueueWorkItem` at `0x14001c696`
- `ntoskrnl!ExQueueWorkItem` at `0x14001c696`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14001c8ef`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14001c970`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14001c8ef`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14001c970`
- `ntoskrnl!KeSetEvent` at `0x14001c5ec`
- `ntoskrnl!KeSetEvent` at `0x14001c947`
- `ntoskrnl!KeSetEvent` at `0x14001cf9b`
- `ntoskrnl!KeSetEvent` at `0x14001d057`
- `ntoskrnl!KeSetEvent` at `0x14001d105`
- `ntoskrnl!KeSetEvent` at `0x14001d15d`
- `ntoskrnl!KeSetEvent` at `0x14001d183`
- `ntoskrnl!KeSetEvent` at `0x14001d1a5`
- `ntoskrnl!KeSetEvent` at `0x14001d3e3`
- `ntoskrnl!KeSetEvent` at `0x14001c5ec`
- `ntoskrnl!KeSetEvent` at `0x14001c947`
- `ntoskrnl!KeSetEvent` at `0x14001cf9b`
- `ntoskrnl!KeSetEvent` at `0x14001d057`
- `ntoskrnl!KeSetEvent` at `0x14001d105`
- `ntoskrnl!KeSetEvent` at `0x14001d15d`
- `ntoskrnl!KeSetEvent` at `0x14001d183`
- `ntoskrnl!KeSetEvent` at `0x14001d1a5`
- `ntoskrnl!KeSetEvent` at `0x14001d3e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c902`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001cb39`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c902`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001cb39`
- `dxgkrnl!DxgCoreInterface` at `0x14001c654`
- `dxgkrnl!DxgCoreInterface` at `0x14001cc77`
- `dxgkrnl!DxgCoreInterface` at `0x14001cdc7`
- `HAL!KeQueryPerformanceCounter` at `0x14001cbc7`
- `HAL!KeQueryPerformanceCounter` at `0x14001cbc7`

## pseudocode

```c
void __fastcall VidSchiCompleteHwQueuePacket(
        struct HwQueueStagingList ***a1,
        struct _VIDSCH_QUEUE_PACKET *a2,
        unsigned __int64 a3)
{
  __int64 v3; // r12
  char v4; // di
  struct _VIDSCH_QUEUE_PACKET *v5; // r15
  __int64 v6; // r13
  __int64 v7; // rcx
  __int64 v8; // rbx
  __int64 v9; // rsi
  int v10; // eax
  unsigned int v11; // r8d
  bool v12; // zf
  unsigned int v13; // r8d
  int v14; // eax
  char v15; // cl
  int v16; // r9d
  unsigned int v17; // r12d
  unsigned int v18; // eax
  unsigned int v19; // r13d
  __int64 v20; // rdi
  void *v21; // rcx
  void *v22; // rcx
  __int64 v23; // r12
  int v24; // edx
  BOOL v25; // edi
  __int64 v26; // rbx
  __int64 v27; // rcx
  __int64 v28; // rax
  struct _KEVENT *v29; // rbx
  KIRQL v30; // r12
  struct _KEVENT *v31; // rdi
  int Flink; // ecx
  BOOL v33; // eax
  __int64 v34; // rbx
  __int64 v35; // rbx
  struct _KEVENT *v36; // rbx
  KIRQL v37; // r12
  struct _KEVENT *v38; // rdi
  unsigned int v39; // eax
  int v40; // ecx
  unsigned int j; // ebx
  __int64 v42; // rax
  char *v43; // rdi
  __int64 v44; // rax
  int v45; // ecx
  BOOL v46; // eax
  struct HwQueueStagingList *v47; // rax
  struct HwQueueStagingList **v48; // r8
  __int64 v49; // rax
  __int64 v50; // rcx
  __int64 v51; // r11
  _DWORD *v52; // rcx
  unsigned int v53; // r9d
  int v54; // eax
  char v55; // r10
  char v56; // cl
  __int64 v57; // rax
  unsigned int v58; // ebx
  int v59; // eax
  char v60; // cl
  __int64 v61; // r8
  char v62; // di
  __int64 v63; // rcx
  __int64 v64; // r9
  __int64 v65; // rax
  __int64 v66; // rdx
  int v67; // eax
  char *v68; // rdi
  volatile signed __int32 *v69; // rcx
  int v70; // edx
  BOOL v71; // r12d
  int v72; // r12d
  LARGE_INTEGER PerformanceCounter; // r9
  unsigned __int64 v74; // rax
  unsigned __int64 v75; // r8
  __int64 v76; // r10
  unsigned __int64 v77; // r9
  unsigned __int64 v78; // rax
  __int64 v79; // rdx
  char v80; // al
  __int64 v81; // rcx
  int v82; // eax
  __int64 v83; // rcx
  __int64 v84; // r9
  __int64 v85; // rdx
  __int64 v86; // rcx
  __int64 v87; // rcx
  struct _KEVENT **v88; // rdi
  KIRQL v89; // r13
  struct _KEVENT *i; // r12
  int v91; // ecx
  BOOL v92; // eax
  struct _KEVENT *v93; // rdi
  KIRQL v94; // r13
  struct _KEVENT *v95; // r12
  int v96; // ecx
  BOOL v97; // eax
  struct _KEVENT *v98; // rdi
  KIRQL v99; // r12
  struct _KEVENT *v100; // rbx
  int v101; // ecx
  BOOL v102; // eax
  __int64 v103; // r9
  __int64 v104; // rcx
  __int64 v105; // rax
  char v106; // [rsp+50h] [rbp-59h]
  int v107; // [rsp+54h] [rbp-55h]
  __int64 v108; // [rsp+60h] [rbp-49h]
  int v109; // [rsp+68h] [rbp-41h]
  __int64 v110; // [rsp+70h] [rbp-39h]
  __int64 v112; // [rsp+80h] [rbp-29h]
  __int64 v113; // [rsp+88h] [rbp-21h]
  __int64 v114; // [rsp+90h] [rbp-19h]
  _BYTE LockHandle[28]; // [rsp+98h] [rbp-11h] BYREF
  unsigned int v116; // [rsp+B4h] [rbp+Bh]
  unsigned int v117; // [rsp+B8h] [rbp+Fh]

  v3 = *((_QWORD *)a2 + 12);
  v4 = a3;
  v106 = a3;
  v5 = a2;
  v114 = v3;
  v6 = *(_QWORD *)(v3 + 40);
  v113 = v6;
  v109 = 0;
  v107 = 0;
  v7 = *(_QWORD *)(v6 + 16);
  v110 = *(_QWORD *)(v6 + 8);
  v108 = v7;
  v8 = *(_QWORD *)(v110 + 48);
  v9 = *(_QWORD *)(v110 + 40);
  v112 = v8;
  if ( (*((_DWORD *)a2 + 16) & 0x20) != 0 && (byte_140087201 & 1) != 0 )
  {
    v85 = *((_QWORD *)a2 + 11);
    if ( v85 )
    {
      v86 = *(_QWORD *)(v85 + 56);
      if ( !v86 || (*(_DWORD *)(v85 + 112) & 0x40) != 0 )
        v86 = v85;
    }
    else
    {
      v86 = *(_QWORD *)(v3 + 48);
      if ( !v86 )
        v86 = v3;
    }
    McTemplateK0pp_EtwWriteTransfer(v86, AbortQueuePacket, a3, v5, v86);
    v7 = v108;
  }
  v10 = *((_DWORD *)v5 + 12);
  if ( !v10 )
  {
    if ( (byte_140087201 & 1) != 0 )
    {
      v84 = *(_QWORD *)(*((_QWORD *)v5 + 12) + 48LL);
      if ( !v84 )
        v84 = *((_QWORD *)v5 + 12);
      McTemplateK0pp_EtwWriteTransfer(*((_QWORD *)v5 + 97), EventDmaCompleteByGpu, a3, v84, *((_QWORD *)v5 + 97));
      v7 = v108;
    }
    --*(_DWORD *)(v3 + 152);
    _InterlockedIncrement64((volatile signed __int64 *)(v7 + 1752));
    v7 = *((_QWORD *)v5 + 36);
    if ( v7 )
    {
      VidMmUnreferenceDmaBuffer(v7, 0);
      if ( (*((_DWORD *)v5 + 18) & 0x100) != 0 )
        VidMmReleaseDmaBuffer(*((struct VIDMM_DMA_BUFFER **)v5 + 36), 0);
    }
    v34 = 0;
    if ( *((_DWORD *)v5 + 120) )
    {
      do
      {
        if ( (unsigned int)v34 >= 0x10 )
          break;
        v68 = (char *)v5 + 8 * v34;
        v7 = *((_QWORD *)v68 + 61);
        if ( v7 )
        {
          v69 = (volatile signed __int32 *)(v7 + 104);
          v70 = _InterlockedDecrement(v69);
          if ( v5 != (struct _VIDSCH_QUEUE_PACKET *)-616LL )
            --*((_DWORD *)v5 + 154);
          InterlockedCounterWithHistoryRelease::AddHistoryEntry((InterlockedCounterWithHistoryRelease *)v69, v70, a3);
        }
        v34 = (unsigned int)(v34 + 1);
        *((_QWORD *)v68 + 61) = 0;
      }
      while ( (unsigned int)v34 < *((_DWORD *)v5 + 120) );
      v4 = v106;
    }
    if ( (*((_DWORD *)v5 + 20) & 0x80u) != 0 )
    {
      _InterlockedDecrement((volatile signed __int32 *)(v9 + 956));
      v35 = *(_QWORD *)(v9 + 8LL * *((unsigned int *)v5 + 42) + 3528);
      if ( _InterlockedExchange((volatile __int32 *)(v35 + 44420), 0) )
      {
        PerformanceCounter = KeQueryPerformanceCounter(0);
        v74 = _InterlockedCompareExchange64((volatile signed __int64 *)(v35 + 44432), 0, 0);
        v75 = v74;
        if ( v74 )
        {
          v76 = *(_QWORD *)(v35 + 44304);
          v77 = PerformanceCounter.QuadPart - v76;
          if ( v77 > v74 )
          {
            v78 = v77 / v74;
            if ( (unsigned int)(v77 / v75) )
            {
              ++*(_DWORD *)(v35 + 44416);
              *(_QWORD *)(v35 + 44312) += (unsigned int)v78;
              v79 = v76 + v75 * v78;
              if ( *(_DWORD *)(v35 + 44416) < *(_DWORD *)(v35 + 83092) )
              {
                v80 = 1;
              }
              else
              {
                *(_DWORD *)(v35 + 44328) += v78;
                v80 = 0;
                *(_DWORD *)(v35 + 44416) = 0;
                *(_QWORD *)(v35 + 44320) = v79;
              }
              *(_BYTE *)(v35 + 44344) = v80;
              v12 = *(_BYTE *)(v35 + 8) == 0;
              *(_QWORD *)(v35 + 44304) = v79;
              if ( !v12 && !*(_BYTE *)(v9 + 164) )
              {
                v81 = *(_QWORD *)(v9 + 8);
                memset(LockHandle, 0, sizeof(LockHandle));
                v82 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _BYTE *))DxgCoreInterface[64])(
                        v81,
                        0,
                        0,
                        LockHandle);
                v83 = 0;
                if ( v82 >= 0 )
                  v83 = *(_QWORD *)&LockHandle[8];
                *(_QWORD *)(v35 + 44336) = v83;
              }
            }
          }
        }
      }
      a2 = (struct _VIDSCH_QUEUE_PACKET *)(v9 + 8LL * *((unsigned int *)v5 + 42));
      *((_QWORD *)v5 + 18) = *(_QWORD *)(*((_QWORD *)a2 + 441) + 44304LL);
      v7 = *(_QWORD *)(*((_QWORD *)a2 + 441) + 44312LL);
      *((_QWORD *)v5 + 17) = v7;
    }
    goto LABEL_19;
  }
  if ( v10 != 8 )
  {
    if ( v10 != 3 )
    {
LABEL_20:
      v23 = v108;
      goto LABEL_21;
    }
    *(_QWORD *)LockHandle = v9;
    v11 = *((_DWORD *)v5 + 220);
    a2 = (struct _VIDSCH_QUEUE_PACKET *)(v11 & 0x3FF);
    *(_QWORD *)&LockHandle[8] = (char *)v5 + 880;
    v12 = *(_BYTE *)(v9 + 164) == 0;
    *(_DWORD *)&LockHandle[16] = v11 & 0x3FF;
    if ( v12 )
    {
      v13 = 0;
      *(_DWORD *)&LockHandle[20] = 0;
    }
    else
    {
      v13 = (v11 >> 10) & 0x3FF;
      *(_DWORD *)&LockHandle[20] = v13;
    }
    v12 = !_BitScanForward((unsigned int *)&v14, (unsigned int)a2);
    v15 = -1;
    v16 = 0;
    *(_DWORD *)&LockHandle[24] = 0;
    if ( !v12 )
      v15 = v14;
    v17 = v15;
    v7 = 0xFFFFFFFFLL;
    v12 = !_BitScanForward(&v18, v13);
    v116 = v17;
    if ( !v12 )
      v7 = v18;
    v19 = (char)v7;
    v117 = (char)v7;
    while ( (_DWORD)a2 || v13 )
    {
      v20 = (__int64)v5 + (unsigned int)(8 * v16 * (*((_DWORD *)v5 + 222) + 28)) + 880;
      v21 = *(void **)(v20 + 216);
      if ( v21 )
      {
        VidSchiReleaseSyncObjectReference(v21);
        *(_QWORD *)(v20 + 216) = 0;
      }
      v22 = *(void **)(v20 + 232);
      if ( v22 )
      {
        if ( v17 < v19 )
        {
          VidSchiReleaseSyncObjectReference(v22);
          *(_QWORD *)(v20 + 232) = 0;
        }
      }
      VIDSCH_FLIP_MULTIPLANE_OVERLAY_ITERATOR::operator++(LockHandle);
      v13 = *(_DWORD *)&LockHandle[20];
      a2 = (struct _VIDSCH_QUEUE_PACKET *)*(unsigned int *)&LockHandle[16];
      v19 = v117;
      v17 = v116;
      v16 = *(_DWORD *)&LockHandle[24];
    }
    v6 = v113;
    v4 = v106;
LABEL_19:
    v8 = v112;
    goto LABEL_20;
  }
  if ( (byte_140087201 & 1) != 0 )
  {
    v103 = *(_QWORD *)(*((_QWORD *)v5 + 12) + 48LL);
    if ( !v103 )
      v103 = *((_QWORD *)v5 + 12);
    McTemplateK0pp_EtwWriteTransfer(*((_QWORD *)v5 + 37), EventDmaCompleteByGpu, a3, v103, *((_QWORD *)v5 + 37));
  }
  --*(_DWORD *)(v3 + 152);
  v23 = v108;
  _InterlockedIncrement64((volatile signed __int64 *)(v108 + 1752));
  if ( (*((_DWORD *)v5 + 70) & 0x100) != 0 )
    VidMmReleaseDmaBuffer(*((struct VIDMM_DMA_BUFFER **)v5 + 36), 1);
LABEL_21:
  if ( v4 )
  {
    if ( (*((_DWORD *)v5 + 12) & 0xFFFFFFF7) == 0 )
    {
      ++*(_QWORD *)(v8 + 2848);
      if ( bTracingEnabled )
      {
        if ( (byte_140087204 & 0x40) != 0
          && *(_BYTE *)(DxgCoreInterface[3](v7, (__int64)a2, (__int64 *)1) + 305736)
          && !_InterlockedCompareExchange((volatile signed __int32 *)(v23 + 3080), 1, 0) )
        {
          ExQueueWorkItem((PWORK_QUEUE_ITEM)(v23 + 3048), NormalWorkQueue);
        }
      }
    }
  }
  v24 = *((_DWORD *)v5 + 18);
  *((_QWORD *)v5 + 7) = MEMORY[0xFFFFF78000000320];
  *((_DWORD *)v5 + 13) = 16;
  if ( (v24 & 0x40020) == 0x40000 || (v24 & 0x4000) != 0 )
  {
    v25 = (v24 & 0x400) == 0 || (v24 & 0x800) != 0;
    v26 = *((unsigned int *)v5 + 42);
    if ( (v24 & 0x40000) != 0 )
    {
      v71 = v25;
      if ( (v24 & 0x4000) == 0 )
        v71 = 0;
      v107 = v71;
    }
    else
    {
      if ( (v24 & 4) != 0 )
      {
        if ( *((_DWORD *)v5 + 100) != 1 )
        {
          if ( (*((_DWORD *)v5 + 16) & 2) != 0 )
            goto LABEL_29;
          if ( !v25 )
          {
LABEL_210:
            if ( (*((_DWORD *)v5 + 220) & 0x3FF) != 0 )
            {
              v104 = *(_QWORD *)(v9 + 776);
              v105 = *(unsigned __int16 *)(v108 + 4);
              if ( (unsigned int)v105 < *(_DWORD *)(v9 + 848) )
                v104 += 8 * v105;
              VidSchiUnreferencePrimaryAllocations(
                (struct HwQueueStagingList *)a1,
                (struct _VIDSCH_GLOBAL *)v9,
                v26,
                (struct _VIDSCH_QUEUE_PACKET *)((char *)v5 + 880),
                *((_DWORD *)v5 + 104),
                1 << *(_BYTE *)(*(_QWORD *)v104 + 6LL),
                0,
                0,
                (unsigned int *)v5 + 224);
            }
LABEL_165:
            if ( (_DWORD)v26 != -1 && v107 && (*((_DWORD *)v5 + 18) & 0x40000) == 0 )
            {
              _InterlockedDecrement((volatile signed __int32 *)(v110 + 4 * v26 + 1708));
              v87 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v110 + 48) + 32LL)
                                          + 8LL * *(unsigned int *)(*(_QWORD *)(v110 + 40) + 4LL))
                              + 8 * v26
                              + 88);
              if ( (*((_DWORD *)v5 + 18) & 0x80u) == 0 )
              {
                _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(v9 + 8 * v26 + 7584) + 8LL));
                ++**(_DWORD **)(v9 + 8 * v26 + 7584);
              }
              _InterlockedDecrement((volatile signed __int32 *)(v87 + 8));
              ++*(_DWORD *)v87;
              if ( (*((_DWORD *)v5 + 18) & 0x20000) != 0 )
              {
                memset(LockHandle, 0, 24);
                KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v9 + 2104), (PKLOCK_QUEUE_HANDLE)LockHandle);
                *(_DWORD *)(v110 + 4 * v26 + 516) = *((_DWORD *)v5 + 98);
                *(_QWORD *)(v110 + 8 * v26 + 584) = *((_QWORD *)v5 + 17);
                *(_QWORD *)(v110 + 8 * v26 + 712) = *((_QWORD *)v5 + 18);
                KeReleaseInStackQueuedSpinLockFromDpcLevel((PKLOCK_QUEUE_HANDLE)LockHandle);
              }
            }
LABEL_29:
            if ( (*((_DWORD *)v5 + 18) & 0x40080) != 0 && *((_QWORD *)v5 + 19) && *((_QWORD *)v5 + 20) && v25 )
              VidSchiSubmitPresentHistoryToken((struct HwQueueStagingList *)a1, v5, 0, 0, 0);
            if ( v109 )
            {
              _InterlockedDecrement((volatile signed __int32 *)(v9 + 880));
              v27 = 4 * v26;
              if ( *(_BYTE *)(v9 + 2580) )
                v28 = v9 + v27;
              else
                v28 = v9;
              _InterlockedDecrement((volatile signed __int32 *)(v28 + 884));
              _InterlockedDecrement((volatile signed __int32 *)(v110 + 1836));
              _InterlockedDecrement((volatile signed __int32 *)(v110 + v27 + 1772));
            }
            v29 = (struct _KEVENT *)(v9 + 2040);
            memset(LockHandle, 0, 24);
            v30 = KfRaiseIrql(2u);
            KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v9 + 2112), (PKLOCK_QUEUE_HANDLE)LockHandle);
            v31 = *(struct _KEVENT **)(v9 + 2040);
            if ( *(struct _KEVENT **)&v29->Header.Lock == v29 )
            {
LABEL_45:
              KeReleaseInStackQueuedSpinLockFromDpcLevel((PKLOCK_QUEUE_HANDLE)LockHandle);
              KeLowerIrql(v30);
              goto LABEL_60;
            }
            while ( 1 )
            {
              if ( LODWORD(v31->Header.WaitListHead.Blink) == 4 )
              {
                v33 = *(_DWORD *)(*(_QWORD *)&v31[1].Header.Lock + 4LL * LODWORD(v31[1].Header.WaitListHead.Blink) + 1708) < *(_DWORD *)(*(_QWORD *)&v31[1].Header.Lock + 252LL);
              }
              else
              {
                if ( ((__int64)v31[1].Header.WaitListHead.Flink & 0x10) == 0 )
                  goto LABEL_43;
                Flink = (int)v31[1].Header.WaitListHead.Blink->Flink;
                HIDWORD(v31[5].Header.WaitListHead.Blink) = Flink;
                v33 = Flink == 0;
              }
              if ( v33 )
              {
LABEL_43:
                ++v31[5].Header.LockNV;
                KeSetEvent(v31 + 4, 0, 0);
              }
              v31 = *(struct _KEVENT **)&v31->Header.Lock;
              if ( v31 == v29 )
                goto LABEL_45;
            }
          }
          v109 = 1;
          v72 = 1;
          v107 = 1;
LABEL_162:
          if ( VidSchiIsFocusHwContext((struct VIDSCH_HW_CONTEXT *)v6) )
            ((void (__fastcall *)(_QWORD))DxgCoreInterface[26])(*(_QWORD *)(*(_QWORD *)(v110 + 40) + 8LL));
          if ( !v72 )
            goto LABEL_165;
          goto LABEL_210;
        }
        v109 = v25;
      }
      v107 = v25;
    }
    v72 = 0;
    if ( !v107 )
      goto LABEL_29;
    goto LABEL_162;
  }
LABEL_60:
  if ( *((_DWORD *)v5 + 12) == 3 && *((_DWORD *)v5 + 42) != -1 )
  {
    v49 = *((_QWORD *)v5 + 11);
    if ( v49 )
      v50 = *(_QWORD *)(v49 + 104);
    else
      v50 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v5 + 12) + 40LL) + 8LL);
    v51 = *(_QWORD *)(v50 + 40);
    v52 = (_DWORD *)((char *)v5 + 880);
    if ( (*((_DWORD *)v5 + 18) & 0x800000) != 0 )
      v53 = ((unsigned __int16)*((_DWORD *)v5 + 220) | (unsigned __int16)(*((_DWORD *)v5 + 220) >> 10)) & 0x3FF;
    else
      v53 = (1 << *(_DWORD *)(v51 + 160)) - 1;
    v12 = !_BitScanForward((unsigned int *)&v54, v53);
    v55 = -1;
    if ( !v12 )
      v55 = v54;
    if ( v53 )
    {
      do
      {
        v56 = v55;
        v57 = v55;
        v55 = -1;
        _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(v51 + 8LL * *((unsigned int *)v5 + 42) + 3528)
                                                        + 304 * v57
                                                        + 192));
        v53 &= ~(1 << v56);
        v12 = !_BitScanForward((unsigned int *)&v57, v53);
        if ( !v12 )
          v55 = v57;
      }
      while ( v53 );
      v52 = (_DWORD *)((char *)v5 + 880);
    }
    if ( (*((_DWORD *)v5 + 18) & 0x800000) != 0 )
      v58 = ((unsigned __int16)*v52 | (unsigned __int16)(*v52 >> 10)) & 0x3FF;
    else
      v58 = (1 << *(_DWORD *)(v9 + 160)) - 1;
    v12 = !_BitScanForward((unsigned int *)&v59, v58);
    v60 = -1;
    if ( !v12 )
      v60 = v59;
    while ( v58 )
    {
      v61 = *((unsigned int *)v5 + 42);
      v62 = v60;
      v63 = 304LL * (unsigned int)v60;
      v64 = *(_QWORD *)(v9 + 8 * v61 + 3528);
      v65 = *(int *)(v64 + v63 + 188);
      if ( (int)v65 > -1 )
      {
        v66 = *(_QWORD *)(v9 + 3656) + 160 * v65;
        if ( *(_DWORD *)(v66 + 112) == 1
          && (_DWORD)v61 != -1
          && (!v66
           || *(_BYTE *)(v66 + 98)
           && !*(_DWORD *)(v64 + v63 + 192)
           && *(_BYTE *)(v66 + 96)
           && !*(_DWORD *)(v64 + v63 + 196)) )
        {
          VidSchiFlushPendingTokenList((struct HwQueueStagingList *)a1, (struct _VIDSCH_GLOBAL *)v9);
        }
      }
      v60 = -1;
      v58 &= ~(1 << v62);
      v12 = !_BitScanForward((unsigned int *)&v67, v58);
      if ( !v12 )
        v60 = v67;
    }
    v6 = v113;
  }
  if ( (unsigned int)(*((_DWORD *)v5 + 12) - 4) > 1 )
    _InterlockedDecrement((volatile signed __int32 *)(v110 + 1848));
  if ( v107 )
  {
    v36 = (struct _KEVENT *)(v110 + 128);
    memset(LockHandle, 0, 24);
    v37 = KfRaiseIrql(2u);
    KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v9 + 2112), (PKLOCK_QUEUE_HANDLE)LockHandle);
    v38 = *(struct _KEVENT **)(v110 + 128);
    if ( *(struct _KEVENT **)&v36->Header.Lock == v36 )
    {
LABEL_65:
      KeReleaseInStackQueuedSpinLockFromDpcLevel((PKLOCK_QUEUE_HANDLE)LockHandle);
      KeLowerIrql(v37);
      goto LABEL_66;
    }
    while ( 1 )
    {
      if ( LODWORD(v38->Header.WaitListHead.Blink) == 4 )
      {
        v46 = *(_DWORD *)(*(_QWORD *)&v38[1].Header.Lock + 4LL * LODWORD(v38[1].Header.WaitListHead.Blink) + 1708) < *(_DWORD *)(*(_QWORD *)&v38[1].Header.Lock + 252LL);
      }
      else
      {
        if ( ((__int64)v38[1].Header.WaitListHead.Flink & 0x10) == 0 )
          goto LABEL_88;
        v45 = (int)v38[1].Header.WaitListHead.Blink->Flink;
        HIDWORD(v38[5].Header.WaitListHead.Blink) = v45;
        v46 = v45 == 0;
      }
      if ( v46 )
      {
LABEL_88:
        ++v38[5].Header.LockNV;
        KeSetEvent(v38 + 4, 0, 0);
      }
      v38 = *(struct _KEVENT **)&v38->Header.Lock;
      if ( v38 == v36 )
        goto LABEL_65;
    }
  }
LABEL_66:
  if ( v109 )
  {
    VidSchiSignalRegisteredEvent(v9, v110 + 144);
    VidSchiSignalRegisteredEvent(v9, v9 + 2024);
    *(_QWORD *)(v9 + 1968) = MEMORY[0xFFFFF78000000320];
    KeSetEvent((PRKEVENT)(v9 + 1936), 0, 0);
  }
  if ( (*((_DWORD *)v5 + 12) & 0xFFFFFFF7) == 0 )
  {
    v47 = (struct HwQueueStagingList *)(v114 + 176);
    if ( !*(_QWORD *)(v114 + 176) )
    {
      v48 = a1[2];
      if ( *v48 != (struct HwQueueStagingList *)(a1 + 1) )
        __fastfail(3u);
      *(_QWORD *)v47 = a1 + 1;
      *(_QWORD *)(v114 + 184) = v48;
      *v48 = v47;
      a1[2] = (struct HwQueueStagingList **)v47;
      *((_BYTE *)a1 + 24) = 0;
    }
    v88 = (struct _KEVENT **)(v6 + 408);
    memset(LockHandle, 0, 24);
    v89 = KfRaiseIrql(2u);
    KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v9 + 2112), (PKLOCK_QUEUE_HANDLE)LockHandle);
    for ( i = *v88; i != (struct _KEVENT *)v88; i = *(struct _KEVENT **)&i->Header.Lock )
    {
      if ( LODWORD(i->Header.WaitListHead.Blink) == 4 )
      {
        v92 = *(_DWORD *)(*(_QWORD *)&i[1].Header.Lock + 4LL * LODWORD(i[1].Header.WaitListHead.Blink) + 1708) < *(_DWORD *)(*(_QWORD *)&i[1].Header.Lock + 252LL);
      }
      else
      {
        if ( ((__int64)i[1].Header.WaitListHead.Flink & 0x10) == 0 )
          goto LABEL_182;
        v91 = (int)i[1].Header.WaitListHead.Blink->Flink;
        HIDWORD(i[5].Header.WaitListHead.Blink) = v91;
        v92 = v91 == 0;
      }
      if ( v92 )
      {
LABEL_182:
        ++i[5].Header.LockNV;
        KeSetEvent(i + 4, 0, 0);
      }
    }
    KeReleaseInStackQueuedSpinLockFromDpcLevel((PKLOCK_QUEUE_HANDLE)LockHandle);
    KeLowerIrql(v89);
    memset(LockHandle, 0, 24);
    v93 = (struct _KEVENT *)(v108 + 408);
    v94 = KfRaiseIrql(2u);
    KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v9 + 2112), (PKLOCK_QUEUE_HANDLE)LockHandle);
    v95 = *(struct _KEVENT **)(v108 + 408);
    if ( *(struct _KEVENT **)&v93->Header.Lock != v93 )
    {
      do
      {
        if ( LODWORD(v95->Header.WaitListHead.Blink) == 4 )
        {
          v97 = *(_DWORD *)(*(_QWORD *)&v95[1].Header.Lock + 4LL * LODWORD(v95[1].Header.WaitListHead.Blink) + 1708) < *(_DWORD *)(*(_QWORD *)&v95[1].Header.Lock + 252LL);
        }
        else
        {
          if ( ((__int64)v95[1].Header.WaitListHead.Flink & 0x10) == 0 )
            goto LABEL_189;
          v96 = (int)v95[1].Header.WaitListHead.Blink->Flink;
          HIDWORD(v95[5].Header.WaitListHead.Blink) = v96;
          v97 = v96 == 0;
        }
        if ( v97 )
        {
LABEL_189:
          ++v95[5].Header.LockNV;
          KeSetEvent(v95 + 4, 0, 0);
        }
        v95 = *(struct _KEVENT **)&v95->Header.Lock;
      }
      while ( v95 != v93 );
    }
    KeReleaseInStackQueuedSpinLockFromDpcLevel((PKLOCK_QUEUE_HANDLE)LockHandle);
    KeLowerIrql(v94);
    v98 = (struct _KEVENT *)(v9 + 1992);
    memset(LockHandle, 0, 24);
    v99 = KfRaiseIrql(2u);
    KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v9 + 2112), (PKLOCK_QUEUE_HANDLE)LockHandle);
    v100 = *(struct _KEVENT **)(v9 + 1992);
    if ( *(struct _KEVENT **)&v98->Header.Lock == v98 )
    {
LABEL_198:
      KeReleaseInStackQueuedSpinLockFromDpcLevel((PKLOCK_QUEUE_HANDLE)LockHandle);
      KeLowerIrql(v99);
      v6 = v113;
      *(_QWORD *)(v113 + 384) = MEMORY[0xFFFFF78000000320];
      KeSetEvent((PRKEVENT)(v113 + 352), 0, 0);
      *(_QWORD *)(v108 + 272) = MEMORY[0xFFFFF78000000320];
      KeSetEvent((PRKEVENT)(v108 + 240), 0, 0);
      *(_QWORD *)(v9 + 1800) = MEMORY[0xFFFFF78000000320];
      KeSetEvent((PRKEVENT)(v9 + 1768), 0, 0);
      goto LABEL_69;
    }
    while ( 1 )
    {
      if ( LODWORD(v100->Header.WaitListHead.Blink) == 4 )
      {
        v102 = *(_DWORD *)(*(_QWORD *)&v100[1].Header.Lock + 4LL * LODWORD(v100[1].Header.WaitListHead.Blink) + 1708) < *(_DWORD *)(*(_QWORD *)&v100[1].Header.Lock + 252LL);
      }
      else
      {
        if ( ((__int64)v100[1].Header.WaitListHead.Flink & 0x10) == 0 )
          goto LABEL_196;
        v101 = (int)v100[1].Header.WaitListHead.Blink->Flink;
        HIDWORD(v100[5].Header.WaitListHead.Blink) = v101;
        v102 = v101 == 0;
      }
      if ( v102 )
      {
LABEL_196:
        ++v100[5].Header.LockNV;
        KeSetEvent(v100 + 4, 0, 0);
      }
      v100 = *(struct _KEVENT **)&v100->Header.Lock;
      if ( v100 == v98 )
        goto LABEL_198;
    }
  }
LABEL_69:
  v39 = *((_DWORD *)v5 + 12);
  if ( v39 <= 7 )
  {
    v40 = 137;
    if ( _bittest(&v40, v39) )
    {
      if ( !*(_BYTE *)(v6 + 149) )
      {
        for ( j = 0; j < *(_DWORD *)(v9 + 160); ++j )
        {
          v42 = *((_QWORD *)v5 + j * (*((_DWORD *)v5 + 222) + 28) + 136);
          if ( v42 )
          {
            v43 = (char *)v5 + 8 * j * (*((_DWORD *)v5 + 222) + 28);
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v42 + 12), 0xFFFFFFFF) == 1 )
            {
              if ( *(_QWORD *)v42 )
                ExFreeToLookasideListEx(*(PLOOKASIDE_LIST_EX *)v42, (PVOID)v42);
              else
                ExFreePoolWithTag((PVOID)v42, 0);
            }
            *((_QWORD *)v43 + 136) = 0;
          }
        }
      }
      v44 = *((_QWORD *)v5 + 39);
      if ( v44 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v44 + 12), 0xFFFFFFFF) == 1 )
        {
          if ( *(_QWORD *)v44 )
            ExFreeToLookasideListEx(*(PLOOKASIDE_LIST_EX *)v44, (PVOID)v44);
          else
            ExFreePoolWithTag((PVOID)v44, 0);
        }
        *((_QWORD *)v5 + 39) = 0;
      }
    }
  }
  VidSchiFreeCompletedHwQueuePacket(v5);
}

```

## disassembly

```asm
0x14001c300  mov     [rsp-8+arg_10], rbx
0x14001c305  push    rbp
0x14001c306  push    rsi
0x14001c307  push    rdi
0x14001c308  push    r12
0x14001c30a  push    r13
0x14001c30c  push    r14
0x14001c30e  push    r15
0x14001c310  lea     rbp, [rsp-27h]
0x14001c315  sub     rsp, 0D0h
0x14001c31c  mov     rax, cs:__security_cookie
0x14001c323  xor     rax, rsp
0x14001c326  mov     [rbp+57h+var_40], rax
0x14001c32a  mov     r12, [rdx+60h]
0x14001c32e  xor     r10d, r10d
0x14001c331  mov     [rbp+57h+var_88], rcx
0x14001c335  movzx   edi, r8b
0x14001c339  mov     [rbp+57h+var_B0], r8b
0x14001c33d  mov     r15, rdx
0x14001c340  mov     [rbp+57h+var_70], r12
0x14001c344  mov     r13, [r12+28h]
0x14001c349  mov     [rbp+57h+var_78], r13
0x14001c34d  mov     [rbp+57h+var_98], r10d
0x14001c351  mov     [rbp+57h+var_AC], r10d
0x14001c355  mov     rax, [r13+8]
0x14001c359  mov     rcx, [r13+10h]
0x14001c35d  mov     [rbp+57h+var_90], rax
0x14001c361  mov     [rbp+57h+var_A0], rcx
0x14001c365  mov     rbx, [rax+30h]
0x14001c369  mov     rsi, [rax+28h]
0x14001c36d  mov     eax, [rdx+40h]
0x14001c370  mov     [rbp+57h+var_80], rbx
0x14001c374  test    al, 20h
0x14001c376  jnz     loc_14001CD2B
0x14001c37c  mov     eax, [r15+30h]
0x14001c380  mov     r14d, 0FFFFFFFFh
0x14001c386  test    eax, eax
0x14001c388  jz      loc_14001C6AD
0x14001c38e  cmp     eax, 8
0x14001c391  jz      loc_14001D1DB
0x14001c397  cmp     eax, 3
0x14001c39a  jnz     loc_14001C473
0x14001c3a0  lea     rbx, [r15+370h]
0x14001c3a7  mov     [rbp+57h+LockHandle.LockQueue.Next], rsi
0x14001c3ab  mov     r8d, [rbx]
0x14001c3ae  mov     edx, r8d
0x14001c3b1  and     edx, 3FFh
0x14001c3b7  mov     [rbp+57h+LockHandle.LockQueue.Lock], rbx
0x14001c3bb  cmp     byte ptr [rsi+0A4h], 0
0x14001c3c2  mov     dword ptr [rbp+57h+LockHandle.OldIrql], edx
0x14001c3c5  jz      loc_14001C755
0x14001c3cb  shr     r8d, 0Ah
0x14001c3cf  and     r8d, 3FFh
0x14001c3d6  mov     dword ptr [rbp+57h+LockHandle+14h], r8d
0x14001c3da  bsf     eax, edx
0x14001c3dd  mov     ecx, 0FFFFFFFFh
0x14001c3e2  mov     [rbp+57h+var_A8], r10d
0x14001c3e6  mov     r9d, r10d
0x14001c3e9  mov     [rbp+57h+var_50], r10d
0x14001c3ed  cmovnz  ecx, eax
0x14001c3f0  mov     [rbp+57h+var_A8], r10d
0x14001c3f4  movsx   r12d, cl
0x14001c3f8  mov     ecx, 0FFFFFFFFh
0x14001c3fd  bsf     eax, r8d
0x14001c401  mov     [rbp+57h+var_4C], r12d
0x14001c405  cmovnz  ecx, eax
0x14001c408  movsx   r13d, cl
0x14001c40c  mov     [rbp+57h+var_48], r13d
0x14001c410  test    edx, edx
0x14001c412  jnz     short loc_14001C419
0x14001c414  test    r8d, r8d
0x14001c417  jz      short loc_14001C467
0x14001c419  mov     edi, [rbx+8]
0x14001c41c  add     edi, 1Ch
0x14001c41f  imul    edi, r9d
0x14001c423  shl     edi, 3
0x14001c426  add     rdi, rbx
0x14001c429  mov     rcx, [rdi+0D8h]; P
0x14001c430  test    rcx, rcx
0x14001c433  jnz     loc_14001D370
0x14001c439  mov     rcx, [rdi+0E8h]; P
0x14001c440  test    rcx, rcx
0x14001c443  jnz     loc_14001D352
0x14001c449  lea     rcx, [rbp+57h+LockHandle]
0x14001c44d  call    ??EVIDSCH_FLIP_MULTIPLANE_OVERLAY_ITERATOR@@QEAAXXZ; VIDSCH_FLIP_MULTIPLANE_OVERLAY_ITERATOR::operator++(void)
0x14001c452  mov     r8d, dword ptr [rbp+57h+LockHandle+14h]
0x14001c456  mov     edx, dword ptr [rbp+57h+LockHandle.OldIrql]
0x14001c459  mov     r13d, [rbp+57h+var_48]
0x14001c45d  mov     r12d, [rbp+57h+var_4C]
0x14001c461  mov     r9d, [rbp+57h+var_50]
0x14001c465  jmp     short loc_14001C410
0x14001c467  mov     r13, [rbp+57h+var_78]
0x14001c46b  movzx   edi, [rbp+57h+var_B0]
0x14001c46f  mov     rbx, [rbp+57h+var_80]
0x14001c473  mov     r12, [rbp+57h+var_A0]
0x14001c477  mov     r8d, 1
0x14001c47d  test    dil, dil
0x14001c480  jnz     loc_14001C625
0x14001c486  mov     rax, ds:0FFFFF78000000320h
0x14001c490  mov     edx, [r15+48h]
0x14001c494  mov     ecx, edx
0x14001c496  mov     [r15+38h], rax
0x14001c49a  and     ecx, 4000h
0x14001c4a0  mov     eax, edx
0x14001c4a2  mov     dword ptr [r15+34h], 10h
0x14001c4aa  and     eax, 40020h
0x14001c4af  cmp     eax, 40000h
0x14001c4b4  jnz     loc_14001C761
0x14001c4ba  bt      edx, 0Ah
0x14001c4be  jb      loc_14001D385
0x14001c4c4  mov     edi, r8d
0x14001c4c7  mov     ebx, [r15+0A8h]
0x14001c4ce  bt      edx, 12h
0x14001c4d2  jb      loc_14001CBA4
0x14001c4d8  test    dl, 4
0x14001c4db  jz      loc_14001CD74
0x14001c4e1  cmp     dword ptr [r15+190h], 1
0x14001c4e9  jz      loc_14001CD71
0x14001c4ef  mov     eax, [r15+40h]
0x14001c4f3  test    al, 2
0x14001c4f5  jz      loc_14001CDA4
0x14001c4fb  test    dword ptr [r15+48h], 40080h
0x14001c503  jz      short loc_14001C534
0x14001c505  cmp     qword ptr [r15+98h], 0
0x14001c50d  jz      short loc_14001C534
0x14001c50f  cmp     qword ptr [r15+0A0h], 0
0x14001c517  jz      short loc_14001C534
0x14001c519  test    edi, edi
0x14001c51b  jz      short loc_14001C534
0x14001c51d  mov     rcx, [rbp+57h+var_88]
0x14001c521  xor     r9d, r9d
0x14001c524  xor     r8d, r8d
0x14001c527  mov     qword ptr [rsp+100h+var_E0], r9
0x14001c52c  mov     rdx, r15
0x14001c52f  call    VidSchiSubmitPresentHistoryToken
0x14001c534  cmp     [rbp+57h+var_98], 0
0x14001c538  jz      short loc_14001C573
0x14001c53a  lock dec dword ptr [rsi+370h]
0x14001c541  lea     rcx, ds:0[rbx*4]
0x14001c549  cmp     byte ptr [rsi+0A14h], 0
0x14001c550  jnz     loc_14001D396
0x14001c556  mov     rax, rsi
0x14001c559  lock dec dword ptr [rax+374h]
0x14001c560  mov     rax, [rbp+57h+var_90]
0x14001c564  lock dec dword ptr [rax+72Ch]
0x14001c56b  lock dec dword ptr [rax+rcx+6ECh]
0x14001c573  xorps   xmm0, xmm0
0x14001c576  lea     rbx, [rsi+7F8h]
0x14001c57d  xor     eax, eax
0x14001c57f  mov     cl, 2; NewIrql
0x14001c581  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x14001c585  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x14001c589  call    cs:__imp_KfRaiseIrql
0x14001c590  nop     dword ptr [rax+rax+00h]
0x14001c595  lea     rcx, [rsi+840h]; SpinLock
0x14001c59c  movzx   r12d, al
0x14001c5a0  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x14001c5a4  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14001c5ab  nop     dword ptr [rax+rax+00h]
0x14001c5b0  mov     rdi, [rbx]
0x14001c5b3  cmp     rdi, rbx
0x14001c5b6  jz      short loc_14001C600
0x14001c5b8  cmp     dword ptr [rdi+10h], 4
0x14001c5bc  jz      loc_14001D2D4
0x14001c5c2  mov     eax, [rdi+20h]
0x14001c5c5  test    al, 10h
0x14001c5c7  jz      short loc_14001C5E0
0x14001c5c9  mov     rax, [rdi+28h]
0x14001c5cd  mov     ecx, [rax]
0x14001c5cf  xor     eax, eax
0x14001c5d1  test    ecx, ecx
0x14001c5d3  mov     [rdi+8Ch], ecx
0x14001c5d9  setz    al
0x14001c5dc  test    eax, eax
0x14001c5de  jz      short loc_14001C5F8
0x14001c5e0  inc     dword ptr [rdi+78h]
0x14001c5e3  lea     rcx, [rdi+60h]; Event
0x14001c5e7  xor     r8d, r8d; Wait
0x14001c5ea  xor     edx, edx; Increment
0x14001c5ec  call    cs:__imp_KeSetEvent
0x14001c5f3  nop     dword ptr [rax+rax+00h]
0x14001c5f8  mov     rdi, [rdi]
0x14001c5fb  cmp     rdi, rbx
0x14001c5fe  jnz     short loc_14001C5B8
0x14001c600  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x14001c604  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14001c60b  nop     dword ptr [rax+rax+00h]
0x14001c610  movzx   ecx, r12b; NewIrql
0x14001c614  call    cs:__imp_KeLowerIrql
0x14001c61b  nop     dword ptr [rax+rax+00h]
0x14001c620  jmp     loc_14001C769
0x14001c625  test    dword ptr [r15+30h], 0FFFFFFF7h
0x14001c62d  jnz     loc_14001C486
0x14001c633  inc     qword ptr [rbx+0B20h]
0x14001c63a  cmp     cs:bTracingEnabled, 0
0x14001c641  jz      loc_14001C486
0x14001c647  test    cs:byte_140087204, 40h
0x14001c64e  jz      loc_14001C486
0x14001c654  mov     rax, cs:DxgCoreInterface
0x14001c65b  mov     rax, [rax+18h]
0x14001c65f  call    _guard_dispatch_icall
0x14001c664  mov     r8d, 1
0x14001c66a  cmp     byte ptr [rax+4AA48h], 0
0x14001c671  jz      loc_14001C486
0x14001c677  xor     eax, eax
0x14001c679  lock cmpxchg [r12+0C08h], r8d
0x14001c683  jnz     loc_14001C486
0x14001c689  lea     rcx, [r12+0BE8h]; WorkItem
0x14001c691  mov     edx, 3; QueueType
0x14001c696  call    cs:__imp_ExQueueWorkItem
0x14001c69d  nop     dword ptr [rax+rax+00h]
0x14001c6a2  mov     r8d, 1
0x14001c6a8  jmp     loc_14001C486
0x14001c6ad  test    cs:byte_140087201, 1
0x14001c6b4  jnz     loc_14001CCFB
0x14001c6ba  dec     dword ptr [r12+98h]
0x14001c6c2  lock inc qword ptr [rcx+6D8h]
0x14001c6ca  mov     rcx, [r15+120h]
0x14001c6d1  test    rcx, rcx
0x14001c6d4  jnz     loc_14001CD7C
0x14001c6da  xor     ebx, ebx
0x14001c6dc  cmp     [r15+1E0h], ebx
0x14001c6e3  ja      loc_14001CB50
0x14001c6e9  mov     eax, [r15+50h]
0x14001c6ed  test    al, al
0x14001c6ef  jns     loc_14001C46F
0x14001c6f5  lock dec dword ptr [rsi+3BCh]
0x14001c6fc  mov     eax, [r15+0A8h]
0x14001c703  mov     rbx, [rsi+rax*8+0DC8h]
0x14001c70b  xor     eax, eax
0x14001c70d  xchg    eax, [rbx+0AD84h]
0x14001c713  test    eax, eax
0x14001c715  jnz     loc_14001CBC5
0x14001c71b  mov     eax, [r15+0A8h]
0x14001c722  lea     rdx, [rsi+rax*8]
0x14001c726  mov     rax, [rdx+0DC8h]
0x14001c72d  mov     rcx, [rax+0AD10h]
0x14001c734  mov     [r15+90h], rcx
0x14001c73b  mov     rax, [rdx+0DC8h]
0x14001c742  mov     rcx, [rax+0AD18h]
0x14001c749  mov     [r15+88h], rcx
0x14001c750  jmp     loc_14001C46F
0x14001c755  mov     r8d, r10d
0x14001c758  mov     dword ptr [rbp+57h+LockHandle+14h], r10d
0x14001c75c  jmp     loc_14001C3DA
0x14001c761  test    ecx, ecx
0x14001c763  jnz     loc_14001C4BA
0x14001c769  cmp     dword ptr [r15+30h], 3
0x14001c76e  jz      loc_14001C9B1
0x14001c774  mov     eax, [r15+30h]
0x14001c778  sub     eax, 4
0x14001c77b  cmp     eax, 1
0x14001c77e  mov     rax, [rbp+57h+var_90]
0x14001c782  ja      loc_14001D39F
0x14001c788  cmp     [rbp+57h+var_AC], 0
0x14001c78c  jz      short loc_14001C7F7
0x14001c78e  lea     rbx, [rax+80h]
0x14001c795  xorps   xmm0, xmm0
0x14001c798  xor     eax, eax
0x14001c79a  mov     cl, 2; NewIrql
0x14001c79c  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x14001c7a0  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x14001c7a4  call    cs:__imp_KfRaiseIrql
0x14001c7ab  nop     dword ptr [rax+rax+00h]
0x14001c7b0  lea     rcx, [rsi+840h]; SpinLock
0x14001c7b7  movzx   r12d, al
0x14001c7bb  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x14001c7bf  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14001c7c6  nop     dword ptr [rax+rax+00h]
0x14001c7cb  mov     rdi, [rbx]
0x14001c7ce  cmp     rdi, rbx
0x14001c7d1  jnz     loc_14001C913
0x14001c7d7  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x14001c7db  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14001c7e2  nop     dword ptr [rax+rax+00h]
0x14001c7e7  movzx   ecx, r12b; NewIrql
0x14001c7eb  call    cs:__imp_KeLowerIrql
0x14001c7f2  nop     dword ptr [rax+rax+00h]
0x14001c7f7  cmp     [rbp+57h+var_98], 0
0x14001c7fb  mov     rbx, 0FFFFF78000000320h
0x14001c805  jnz     loc_14001D3AB
0x14001c80b  test    dword ptr [r15+30h], 0FFFFFFF7h
0x14001c813  jz      loc_14001C981
0x14001c819  mov     eax, [r15+30h]
0x14001c81d  cmp     eax, 7
0x14001c820  ja      loc_14001C8B4
0x14001c826  mov     ecx, 89h
0x14001c82b  bt      ecx, eax
0x14001c82e  jnb     loc_14001C8B4
0x14001c834  xor     r12d, r12d
0x14001c837  cmp     [r13+95h], r12b
0x14001c83e  jnz     short loc_14001C891
0x14001c840  mov     ebx, r12d
0x14001c843  cmp     [rsi+0A0h], ebx
0x14001c849  jbe     short loc_14001C891
0x14001c84b  nop     dword ptr [rax+rax+00h]
0x14001c850  mov     eax, [r15+378h]
0x14001c857  add     eax, 1Ch
0x14001c85a  imul    eax, ebx
0x14001c85d  shl     eax, 3
  ... truncated ...
```
