# VidSchiCompleteHwQueuePacket(HwQueueStagingList *,_VIDSCH_QUEUE_PACKET *,bool)

- ea: `0x14001de60`
- end: `0x14001ef54`
- name: `?VidSchiCompleteHwQueuePacket@@YAXPEAVHwQueueStagingList@@PEAU_VIDSCH_QUEUE_PACKET@@_N@Z`
- size: `4340`
- prototype: `void __fastcall(struct HwQueueStagingList *, struct _VIDSCH_QUEUE_PACKET *, bool)`
- caller_count: `6`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140007c10`
- `0x14001d1a0`
- `0x14001d344`
- `0x14001dcf4`
- `0x140041438`
- `0x1400440b0`

## callees

- `0x14000d2dc`
- `0x14001bff0`
- `0x14001c360`
- `0x14001de60`
- `0x14001ef60`
- `0x14001efcc`
- `0x14001f798`
- `0x14001f7fc`
- `0x14001ff8c`
- `0x140020138`
- `0x1400201d0`
- `0x140020288`
- `0x140043aec`
- `0x140058680`
- `0x140058760`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14001e0e9`
- `ntoskrnl!KfRaiseIrql` at `0x14001e304`
- `ntoskrnl!KfRaiseIrql` at `0x14001ea8e`
- `ntoskrnl!KfRaiseIrql` at `0x14001eb4a`
- `ntoskrnl!KfRaiseIrql` at `0x14001ec02`
- `ntoskrnl!KfRaiseIrql` at `0x14001e0e9`
- `ntoskrnl!KfRaiseIrql` at `0x14001e304`
- `ntoskrnl!KfRaiseIrql` at `0x14001ea8e`
- `ntoskrnl!KfRaiseIrql` at `0x14001eb4a`
- `ntoskrnl!KfRaiseIrql` at `0x14001ec02`
- `ntoskrnl!KeLowerIrql` at `0x14001e174`
- `ntoskrnl!KeLowerIrql` at `0x14001e34b`
- `ntoskrnl!KeLowerIrql` at `0x14001eb24`
- `ntoskrnl!KeLowerIrql` at `0x14001ebe0`
- `ntoskrnl!KeLowerIrql` at `0x14001ec8d`
- `ntoskrnl!KeLowerIrql` at `0x14001e174`
- `ntoskrnl!KeLowerIrql` at `0x14001e34b`
- `ntoskrnl!KeLowerIrql` at `0x14001eb24`
- `ntoskrnl!KeLowerIrql` at `0x14001ebe0`
- `ntoskrnl!KeLowerIrql` at `0x14001ec8d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001e104`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001e31f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001e9da`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001eaa9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001eb65`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001ec1d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001e104`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001e31f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001e9da`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001eaa9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001eb65`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001ec1d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001e164`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001e33b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001ea1a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001eb14`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001ebd0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001ec7d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001e164`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001e33b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001ea1a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001eb14`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001ebd0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001ec7d`
- `ntoskrnl!ExQueueWorkItem` at `0x14001e1f6`
- `ntoskrnl!ExQueueWorkItem` at `0x14001e1f6`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14001e44f`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14001e4d0`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14001e44f`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14001e4d0`
- `ntoskrnl!KeSetEvent` at `0x14001e14c`
- `ntoskrnl!KeSetEvent` at `0x14001e4a7`
- `ntoskrnl!KeSetEvent` at `0x14001eafb`
- `ntoskrnl!KeSetEvent` at `0x14001ebb7`
- `ntoskrnl!KeSetEvent` at `0x14001ec65`
- `ntoskrnl!KeSetEvent` at `0x14001ecbd`
- `ntoskrnl!KeSetEvent` at `0x14001ece3`
- `ntoskrnl!KeSetEvent` at `0x14001ed05`
- `ntoskrnl!KeSetEvent` at `0x14001ef43`
- `ntoskrnl!KeSetEvent` at `0x14001e14c`
- `ntoskrnl!KeSetEvent` at `0x14001e4a7`
- `ntoskrnl!KeSetEvent` at `0x14001eafb`
- `ntoskrnl!KeSetEvent` at `0x14001ebb7`
- `ntoskrnl!KeSetEvent` at `0x14001ec65`
- `ntoskrnl!KeSetEvent` at `0x14001ecbd`
- `ntoskrnl!KeSetEvent` at `0x14001ece3`
- `ntoskrnl!KeSetEvent` at `0x14001ed05`
- `ntoskrnl!KeSetEvent` at `0x14001ef43`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e462`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e699`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e462`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e699`
- `dxgkrnl!DxgCoreInterface` at `0x14001e1b4`
- `dxgkrnl!DxgCoreInterface` at `0x14001e7d7`
- `dxgkrnl!DxgCoreInterface` at `0x14001e927`
- `HAL!KeQueryPerformanceCounter` at `0x14001e727`
- `HAL!KeQueryPerformanceCounter` at `0x14001e727`

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
  if ( (*((_DWORD *)a2 + 16) & 0x20) != 0 && (byte_140086201 & 1) != 0 )
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
    if ( (byte_140086201 & 1) != 0 )
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
      VIDSCH_FLIP_MULTIPLANE_OVERLAY_ITERATOR::operator++((unsigned int *)LockHandle);
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
  if ( (byte_140086201 & 1) != 0 )
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
        if ( (byte_140086204 & 0x40) != 0
          && *(_BYTE *)(((__int64 (__fastcall *)(__int64, struct _VIDSCH_QUEUE_PACKET *, __int64))DxgCoreInterface[3])(
                          v7,
                          a2,
                          1)
                      + 305736)
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
0x14001de60  mov     [rsp-8+arg_10], rbx
0x14001de65  push    rbp
0x14001de66  push    rsi
0x14001de67  push    rdi
0x14001de68  push    r12
0x14001de6a  push    r13
0x14001de6c  push    r14
0x14001de6e  push    r15
0x14001de70  lea     rbp, [rsp-27h]
0x14001de75  sub     rsp, 0D0h
0x14001de7c  mov     rax, cs:__security_cookie
0x14001de83  xor     rax, rsp
0x14001de86  mov     [rbp+57h+var_40], rax
0x14001de8a  mov     r12, [rdx+60h]
0x14001de8e  xor     r10d, r10d
0x14001de91  mov     [rbp+57h+var_88], rcx
0x14001de95  movzx   edi, r8b
0x14001de99  mov     [rbp+57h+var_B0], r8b
0x14001de9d  mov     r15, rdx
0x14001dea0  mov     [rbp+57h+var_70], r12
0x14001dea4  mov     r13, [r12+28h]
0x14001dea9  mov     [rbp+57h+var_78], r13
0x14001dead  mov     [rbp+57h+var_98], r10d
0x14001deb1  mov     [rbp+57h+var_AC], r10d
0x14001deb5  mov     rax, [r13+8]
0x14001deb9  mov     rcx, [r13+10h]
0x14001debd  mov     [rbp+57h+var_90], rax
0x14001dec1  mov     [rbp+57h+var_A0], rcx
0x14001dec5  mov     rbx, [rax+30h]
0x14001dec9  mov     rsi, [rax+28h]
0x14001decd  mov     eax, [rdx+40h]
0x14001ded0  mov     [rbp+57h+var_80], rbx
0x14001ded4  test    al, 20h
0x14001ded6  jnz     loc_14001E88B
0x14001dedc  mov     eax, [r15+30h]
0x14001dee0  mov     r14d, 0FFFFFFFFh
0x14001dee6  test    eax, eax
0x14001dee8  jz      loc_14001E20D
0x14001deee  cmp     eax, 8
0x14001def1  jz      loc_14001ED3B
0x14001def7  cmp     eax, 3
0x14001defa  jnz     loc_14001DFD3
0x14001df00  lea     rbx, [r15+370h]
0x14001df07  mov     [rbp+57h+LockHandle.LockQueue.Next], rsi
0x14001df0b  mov     r8d, [rbx]
0x14001df0e  mov     edx, r8d
0x14001df11  and     edx, 3FFh
0x14001df17  mov     [rbp+57h+LockHandle.LockQueue.Lock], rbx
0x14001df1b  cmp     byte ptr [rsi+0A4h], 0
0x14001df22  mov     dword ptr [rbp+57h+LockHandle.OldIrql], edx
0x14001df25  jz      loc_14001E2B5
0x14001df2b  shr     r8d, 0Ah
0x14001df2f  and     r8d, 3FFh
0x14001df36  mov     dword ptr [rbp+57h+LockHandle+14h], r8d
0x14001df3a  bsf     eax, edx
0x14001df3d  mov     ecx, 0FFFFFFFFh
0x14001df42  mov     [rbp+57h+var_A8], r10d
0x14001df46  mov     r9d, r10d
0x14001df49  mov     [rbp+57h+var_50], r10d
0x14001df4d  cmovnz  ecx, eax
0x14001df50  mov     [rbp+57h+var_A8], r10d
0x14001df54  movsx   r12d, cl
0x14001df58  mov     ecx, 0FFFFFFFFh
0x14001df5d  bsf     eax, r8d
0x14001df61  mov     [rbp+57h+var_4C], r12d
0x14001df65  cmovnz  ecx, eax
0x14001df68  movsx   r13d, cl
0x14001df6c  mov     [rbp+57h+var_48], r13d
0x14001df70  test    edx, edx
0x14001df72  jnz     short loc_14001DF79
0x14001df74  test    r8d, r8d
0x14001df77  jz      short loc_14001DFC7
0x14001df79  mov     edi, [rbx+8]
0x14001df7c  add     edi, 1Ch
0x14001df7f  imul    edi, r9d
0x14001df83  shl     edi, 3
0x14001df86  add     rdi, rbx
0x14001df89  mov     rcx, [rdi+0D8h]; P
0x14001df90  test    rcx, rcx
0x14001df93  jnz     loc_14001EED0
0x14001df99  mov     rcx, [rdi+0E8h]; P
0x14001dfa0  test    rcx, rcx
0x14001dfa3  jnz     loc_14001EEB2
0x14001dfa9  lea     rcx, [rbp+57h+LockHandle]
0x14001dfad  call    ??EVIDSCH_FLIP_MULTIPLANE_OVERLAY_ITERATOR@@QEAAXXZ; VIDSCH_FLIP_MULTIPLANE_OVERLAY_ITERATOR::operator++(void)
0x14001dfb2  mov     r8d, dword ptr [rbp+57h+LockHandle+14h]
0x14001dfb6  mov     edx, dword ptr [rbp+57h+LockHandle.OldIrql]
0x14001dfb9  mov     r13d, [rbp+57h+var_48]
0x14001dfbd  mov     r12d, [rbp+57h+var_4C]
0x14001dfc1  mov     r9d, [rbp+57h+var_50]
0x14001dfc5  jmp     short loc_14001DF70
0x14001dfc7  mov     r13, [rbp+57h+var_78]
0x14001dfcb  movzx   edi, [rbp+57h+var_B0]
0x14001dfcf  mov     rbx, [rbp+57h+var_80]
0x14001dfd3  mov     r12, [rbp+57h+var_A0]
0x14001dfd7  mov     r8d, 1
0x14001dfdd  test    dil, dil
0x14001dfe0  jnz     loc_14001E185
0x14001dfe6  mov     rax, ds:0FFFFF78000000320h
0x14001dff0  mov     edx, [r15+48h]
0x14001dff4  mov     ecx, edx
0x14001dff6  mov     [r15+38h], rax
0x14001dffa  and     ecx, 4000h
0x14001e000  mov     eax, edx
0x14001e002  mov     dword ptr [r15+34h], 10h
0x14001e00a  and     eax, 40020h
0x14001e00f  cmp     eax, 40000h
0x14001e014  jnz     loc_14001E2C1
0x14001e01a  bt      edx, 0Ah
0x14001e01e  jb      loc_14001EEE5
0x14001e024  mov     edi, r8d
0x14001e027  mov     ebx, [r15+0A8h]
0x14001e02e  bt      edx, 12h
0x14001e032  jb      loc_14001E704
0x14001e038  test    dl, 4
0x14001e03b  jz      loc_14001E8D4
0x14001e041  cmp     dword ptr [r15+190h], 1
0x14001e049  jz      loc_14001E8D1
0x14001e04f  mov     eax, [r15+40h]
0x14001e053  test    al, 2
0x14001e055  jz      loc_14001E904
0x14001e05b  test    dword ptr [r15+48h], 40080h
0x14001e063  jz      short loc_14001E094
0x14001e065  cmp     qword ptr [r15+98h], 0
0x14001e06d  jz      short loc_14001E094
0x14001e06f  cmp     qword ptr [r15+0A0h], 0
0x14001e077  jz      short loc_14001E094
0x14001e079  test    edi, edi
0x14001e07b  jz      short loc_14001E094
0x14001e07d  mov     rcx, [rbp+57h+var_88]
0x14001e081  xor     r9d, r9d
0x14001e084  xor     r8d, r8d
0x14001e087  mov     qword ptr [rsp+100h+var_E0], r9
0x14001e08c  mov     rdx, r15
0x14001e08f  call    VidSchiSubmitPresentHistoryToken
0x14001e094  cmp     [rbp+57h+var_98], 0
0x14001e098  jz      short loc_14001E0D3
0x14001e09a  lock dec dword ptr [rsi+370h]
0x14001e0a1  lea     rcx, ds:0[rbx*4]
0x14001e0a9  cmp     byte ptr [rsi+0A14h], 0
0x14001e0b0  jnz     loc_14001EEF6
0x14001e0b6  mov     rax, rsi
0x14001e0b9  lock dec dword ptr [rax+374h]
0x14001e0c0  mov     rax, [rbp+57h+var_90]
0x14001e0c4  lock dec dword ptr [rax+72Ch]
0x14001e0cb  lock dec dword ptr [rax+rcx+6ECh]
0x14001e0d3  xorps   xmm0, xmm0
0x14001e0d6  lea     rbx, [rsi+7F8h]
0x14001e0dd  xor     eax, eax
0x14001e0df  mov     cl, 2; NewIrql
0x14001e0e1  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x14001e0e5  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x14001e0e9  call    cs:__imp_KfRaiseIrql
0x14001e0f0  nop     dword ptr [rax+rax+00h]
0x14001e0f5  lea     rcx, [rsi+840h]; SpinLock
0x14001e0fc  movzx   r12d, al
0x14001e100  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x14001e104  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14001e10b  nop     dword ptr [rax+rax+00h]
0x14001e110  mov     rdi, [rbx]
0x14001e113  cmp     rdi, rbx
0x14001e116  jz      short loc_14001E160
0x14001e118  cmp     dword ptr [rdi+10h], 4
0x14001e11c  jz      loc_14001EE34
0x14001e122  mov     eax, [rdi+20h]
0x14001e125  test    al, 10h
0x14001e127  jz      short loc_14001E140
0x14001e129  mov     rax, [rdi+28h]
0x14001e12d  mov     ecx, [rax]
0x14001e12f  xor     eax, eax
0x14001e131  test    ecx, ecx
0x14001e133  mov     [rdi+8Ch], ecx
0x14001e139  setz    al
0x14001e13c  test    eax, eax
0x14001e13e  jz      short loc_14001E158
0x14001e140  inc     dword ptr [rdi+78h]
0x14001e143  lea     rcx, [rdi+60h]; Event
0x14001e147  xor     r8d, r8d; Wait
0x14001e14a  xor     edx, edx; Increment
0x14001e14c  call    cs:__imp_KeSetEvent
0x14001e153  nop     dword ptr [rax+rax+00h]
0x14001e158  mov     rdi, [rdi]
0x14001e15b  cmp     rdi, rbx
0x14001e15e  jnz     short loc_14001E118
0x14001e160  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x14001e164  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14001e16b  nop     dword ptr [rax+rax+00h]
0x14001e170  movzx   ecx, r12b; NewIrql
0x14001e174  call    cs:__imp_KeLowerIrql
0x14001e17b  nop     dword ptr [rax+rax+00h]
0x14001e180  jmp     loc_14001E2C9
0x14001e185  test    dword ptr [r15+30h], 0FFFFFFF7h
0x14001e18d  jnz     loc_14001DFE6
0x14001e193  inc     qword ptr [rbx+0B20h]
0x14001e19a  cmp     cs:bTracingEnabled, 0
0x14001e1a1  jz      loc_14001DFE6
0x14001e1a7  test    cs:byte_140086204, 40h
0x14001e1ae  jz      loc_14001DFE6
0x14001e1b4  mov     rax, cs:DxgCoreInterface
0x14001e1bb  mov     rax, [rax+18h]
0x14001e1bf  call    _guard_dispatch_icall
0x14001e1c4  mov     r8d, 1
0x14001e1ca  cmp     byte ptr [rax+4AA48h], 0
0x14001e1d1  jz      loc_14001DFE6
0x14001e1d7  xor     eax, eax
0x14001e1d9  lock cmpxchg [r12+0C08h], r8d
0x14001e1e3  jnz     loc_14001DFE6
0x14001e1e9  lea     rcx, [r12+0BE8h]; WorkItem
0x14001e1f1  mov     edx, 3; QueueType
0x14001e1f6  call    cs:__imp_ExQueueWorkItem
0x14001e1fd  nop     dword ptr [rax+rax+00h]
0x14001e202  mov     r8d, 1
0x14001e208  jmp     loc_14001DFE6
0x14001e20d  test    cs:byte_140086201, 1
0x14001e214  jnz     loc_14001E85B
0x14001e21a  dec     dword ptr [r12+98h]
0x14001e222  lock inc qword ptr [rcx+6D8h]
0x14001e22a  mov     rcx, [r15+120h]
0x14001e231  test    rcx, rcx
0x14001e234  jnz     loc_14001E8DC
0x14001e23a  xor     ebx, ebx
0x14001e23c  cmp     [r15+1E0h], ebx
0x14001e243  ja      loc_14001E6B0
0x14001e249  mov     eax, [r15+50h]
0x14001e24d  test    al, al
0x14001e24f  jns     loc_14001DFCF
0x14001e255  lock dec dword ptr [rsi+3BCh]
0x14001e25c  mov     eax, [r15+0A8h]
0x14001e263  mov     rbx, [rsi+rax*8+0DC8h]
0x14001e26b  xor     eax, eax
0x14001e26d  xchg    eax, [rbx+0AD84h]
0x14001e273  test    eax, eax
0x14001e275  jnz     loc_14001E725
0x14001e27b  mov     eax, [r15+0A8h]
0x14001e282  lea     rdx, [rsi+rax*8]
0x14001e286  mov     rax, [rdx+0DC8h]
0x14001e28d  mov     rcx, [rax+0AD10h]
0x14001e294  mov     [r15+90h], rcx
0x14001e29b  mov     rax, [rdx+0DC8h]
0x14001e2a2  mov     rcx, [rax+0AD18h]
0x14001e2a9  mov     [r15+88h], rcx
0x14001e2b0  jmp     loc_14001DFCF
0x14001e2b5  mov     r8d, r10d
0x14001e2b8  mov     dword ptr [rbp+57h+LockHandle+14h], r10d
0x14001e2bc  jmp     loc_14001DF3A
0x14001e2c1  test    ecx, ecx
0x14001e2c3  jnz     loc_14001E01A
0x14001e2c9  cmp     dword ptr [r15+30h], 3
0x14001e2ce  jz      loc_14001E511
0x14001e2d4  mov     eax, [r15+30h]
0x14001e2d8  sub     eax, 4
0x14001e2db  cmp     eax, 1
0x14001e2de  mov     rax, [rbp+57h+var_90]
0x14001e2e2  ja      loc_14001EEFF
0x14001e2e8  cmp     [rbp+57h+var_AC], 0
0x14001e2ec  jz      short loc_14001E357
0x14001e2ee  lea     rbx, [rax+80h]
0x14001e2f5  xorps   xmm0, xmm0
0x14001e2f8  xor     eax, eax
0x14001e2fa  mov     cl, 2; NewIrql
0x14001e2fc  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x14001e300  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x14001e304  call    cs:__imp_KfRaiseIrql
0x14001e30b  nop     dword ptr [rax+rax+00h]
0x14001e310  lea     rcx, [rsi+840h]; SpinLock
0x14001e317  movzx   r12d, al
0x14001e31b  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x14001e31f  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14001e326  nop     dword ptr [rax+rax+00h]
0x14001e32b  mov     rdi, [rbx]
0x14001e32e  cmp     rdi, rbx
0x14001e331  jnz     loc_14001E473
0x14001e337  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x14001e33b  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14001e342  nop     dword ptr [rax+rax+00h]
0x14001e347  movzx   ecx, r12b; NewIrql
0x14001e34b  call    cs:__imp_KeLowerIrql
0x14001e352  nop     dword ptr [rax+rax+00h]
0x14001e357  cmp     [rbp+57h+var_98], 0
0x14001e35b  mov     rbx, 0FFFFF78000000320h
0x14001e365  jnz     loc_14001EF0B
0x14001e36b  test    dword ptr [r15+30h], 0FFFFFFF7h
0x14001e373  jz      loc_14001E4E1
0x14001e379  mov     eax, [r15+30h]
0x14001e37d  cmp     eax, 7
0x14001e380  ja      loc_14001E414
0x14001e386  mov     ecx, 89h
0x14001e38b  bt      ecx, eax
0x14001e38e  jnb     loc_14001E414
0x14001e394  xor     r12d, r12d
0x14001e397  cmp     [r13+95h], r12b
0x14001e39e  jnz     short loc_14001E3F1
0x14001e3a0  mov     ebx, r12d
0x14001e3a3  cmp     [rsi+0A0h], ebx
0x14001e3a9  jbe     short loc_14001E3F1
0x14001e3ab  nop     dword ptr [rax+rax+00h]
0x14001e3b0  mov     eax, [r15+378h]
0x14001e3b7  add     eax, 1Ch
0x14001e3ba  imul    eax, ebx
0x14001e3bd  shl     eax, 3
  ... truncated ...
```
