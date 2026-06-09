# VidSchiScheduleCommandToRun

- ea: `0x14000f5a0`
- end: `0x140010313`
- name: `VidSchiScheduleCommandToRun`
- size: `3443`
- prototype: `__int64 __fastcall(struct _VIDSCH_GLOBAL *)`
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400dd5f0`

## callees

- `0x14000a61c`
- `0x14000a7f8`
- `0x14000dfe8`
- `0x14000e4c0`
- `0x14000eda0`
- `0x14000f5a0`
- `0x140010760`
- `0x140011b70`
- `0x14001cc60`
- `0x140021de4`
- `0x140032128`
- `0x140042ac8`
- `0x1400dc9e4`
- `0x1400dce20`
- `0x1400de840`

## import_xrefs

- `ntoskrnl!KeReadStateEvent` at `0x14000f669`
- `ntoskrnl!KeReadStateEvent` at `0x14000f669`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000f622`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000f688`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000f622`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000f688`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000f645`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000fbe2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000f645`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000fbe2`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000f9f2`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000fea9`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000ff16`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000f9f2`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000fea9`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000ff16`
- `ntoskrnl!RtlCopyBitMapEx` at `0x14000f8ea`
- `ntoskrnl!RtlCopyBitMapEx` at `0x14000f931`
- `ntoskrnl!RtlCopyBitMapEx` at `0x14000f8ea`
- `ntoskrnl!RtlCopyBitMapEx` at `0x14000f931`
- `ntoskrnl!RtlIntersectBitMapsEx` at `0x14000f900`
- `ntoskrnl!RtlIntersectBitMapsEx` at `0x14000f900`
- `ntoskrnl!RtlAreBitsClearEx` at `0x14000f914`
- `ntoskrnl!RtlAreBitsClearEx` at `0x14000f914`
- `ntoskrnl!RtlFindSetBitsEx` at `0x14000f94f`
- `ntoskrnl!RtlFindSetBitsEx` at `0x14000f94f`
- `ntoskrnl!KeSetEvent` at `0x140010108`
- `ntoskrnl!KeSetEvent` at `0x140010217`
- `ntoskrnl!KeSetEvent` at `0x140010108`
- `ntoskrnl!KeSetEvent` at `0x140010217`
- `watchdog!WdLogSingleEntry1` at `0x1400102cc`
- `watchdog!WdLogSingleEntry1` at `0x1400102f2`
- `watchdog!WdLogSingleEntry1` at `0x1400102cc`
- `watchdog!WdLogSingleEntry1` at `0x1400102f2`
- `dxgkrnl!DpSynchronizeExecution` at `0x14000f822`
- `dxgkrnl!DpSynchronizeExecution` at `0x14000f9d0`
- `dxgkrnl!DpSynchronizeExecution` at `0x14000f822`
- `dxgkrnl!DpSynchronizeExecution` at `0x14000f9d0`
- `HAL!KeQueryPerformanceCounter` at `0x14000ff45`
- `HAL!KeQueryPerformanceCounter` at `0x14000ffc3`
- `HAL!KeQueryPerformanceCounter` at `0x14000ff45`
- `HAL!KeQueryPerformanceCounter` at `0x14000ffc3`

## pseudocode

```c
__int64 __fastcall VidSchiScheduleCommandToRun(struct _VIDSCH_GLOBAL *a1, _BYTE *a2)
{
  int v2; // r14d
  __int64 v3; // r13
  struct _VIDSCH_GLOBAL *v5; // r9
  char *v6; // r15
  __int64 v7; // rcx
  int v8; // eax
  struct _VIDSCH_GLOBAL *v9; // rdi
  struct _VIDSCH_GLOBAL **v10; // r12
  _QWORD **v11; // rsi
  _QWORD *v12; // rax
  _QWORD *v13; // rcx
  _QWORD *v14; // rdi
  __int64 v15; // rax
  _QWORD **v16; // rcx
  _QWORD *v17; // rax
  _QWORD *v18; // rdx
  struct _VIDSCH_GLOBAL *v19; // r9
  bool v20; // zf
  struct _VIDSCH_GLOBAL **v21; // r8
  struct _VIDSCH_CONTEXT *v22; // rsi
  __int64 v23; // rax
  __int64 SetBits; // rax
  __int64 *v25; // rdi
  __int64 v26; // rdi
  __int64 v27; // rcx
  __int64 v28; // rdx
  CCHAR v29; // al
  int v30; // eax
  __int64 v31; // rcx
  int v32; // eax
  __int64 v33; // rdi
  __int64 v34; // r8
  int v35; // ecx
  unsigned int v36; // eax
  unsigned int v37; // ecx
  int v38; // eax
  unsigned int v39; // eax
  int v40; // ecx
  unsigned int v41; // ecx
  __int64 v42; // rcx
  int v43; // eax
  struct _VIDSCH_GLOBAL *i; // rdi
  struct _VIDSCH_GLOBAL *v46; // rsi
  _QWORD *v47; // r9
  __int64 *v48; // rdx
  char v49; // al
  __int64 *v50; // r8
  __int64 *v51; // rcx
  char v52; // al
  __int64 v53; // rdx
  struct _VIDSCH_GLOBAL *v54; // rcx
  struct _VIDSCH_GLOBAL **v55; // rax
  struct _VIDSCH_GLOBAL *v56; // rcx
  struct _VIDSCH_GLOBAL **v57; // rax
  __int64 v58; // rax
  CCHAR MostSignificantBit; // al
  CCHAR v60; // al
  LARGE_INTEGER v61; // r14
  unsigned int v62; // edx
  __int64 v63; // rcx
  LARGE_INTEGER v64; // r14
  unsigned int v65; // edx
  __int64 v66; // rcx
  __int64 v67; // rcx
  _QWORD *v68; // rax
  _QWORD *v69; // r10
  char *v70; // rdx
  char *v71; // r9
  char **v72; // r8
  __int64 v73; // rax
  __int64 v74; // rcx
  __int64 **v75; // rax
  __int64 v76; // rax
  __int64 **v77; // r9
  struct _VIDSCH_GLOBAL **v78; // r9
  __int64 v79; // r8
  struct _VIDSCH_GLOBAL ***v80; // rdx
  char *v81; // rcx
  __int64 v82; // rax
  __int64 v83; // rcx
  __int64 **v84; // rax
  __int64 v85; // rax
  __int64 **v86; // r8
  struct _KLOCK_QUEUE_HANDLE v87; // [rsp+40h] [rbp-29h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+58h] [rbp-11h] BYREF
  _QWORD v89[10]; // [rsp+70h] [rbp+7h] BYREF
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+E0h] [rbp+77h] BYREF

  v2 = 0;
  v3 = 0;
  *a2 = 0;
  memset(&v87, 0, sizeof(v87));
  while ( (unsigned int)(*((_DWORD *)a1 + 835) - 2) <= 1 || (unsigned int)VidSchiCheckHwProgress(a1) )
  {
    memset(&LockHandle, 0, sizeof(LockHandle));
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)a1 + 266, &LockHandle);
    v5 = (struct _VIDSCH_GLOBAL *)*((_QWORD *)a1 + 270);
    if ( v5 != (struct _VIDSCH_GLOBAL *)((char *)a1 + 2160) )
    {
      do
      {
        v46 = *(struct _VIDSCH_GLOBAL **)v5;
        if ( (unsigned int)VidMmCheckAllocConditionDeviceCommand((struct _VIDSCH_GLOBAL *)((char *)v5 - 736)) )
        {
          v67 = *v47;
          if ( *(_QWORD **)(*v47 + 8LL) != v47 )
            goto LABEL_38;
          v68 = (_QWORD *)v47[1];
          if ( (_QWORD *)*v68 != v47 )
            goto LABEL_38;
          *v68 = v67;
          *(_QWORD *)(v67 + 8) = v68;
          VidMmAddPendingTermination((struct VIDMM_ALLOC *)(v47 - 92));
        }
        v5 = v46;
      }
      while ( v46 != (struct _VIDSCH_GLOBAL *)((char *)a1 + 2160) );
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    *((_QWORD *)a1 + 206) = MEMORY[0xFFFFF78000000320];
    if ( KeReadStateEvent((PRKEVENT)((char *)a1 + 1600)) > 0 )
      goto LABEL_79;
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)a1 + 262, &v87);
    v6 = (char *)a1 + 280;
    if ( *((_DWORD *)a1 + 77) == 1 )
    {
      v7 = *(_QWORD *)v6;
      v8 = *(_DWORD *)(*(_QWORD *)v6 + 312LL);
      if ( v8 == 1 )
      {
        v69 = (_QWORD *)*((_QWORD *)a1 + 36);
        v70 = (char *)a1 + 288;
        if ( v69 == (_QWORD *)((char *)a1 + 288) )
          goto LABEL_9;
        v71 = (char *)(v7 + 288);
        if ( *(_QWORD *)(*(_QWORD *)(v7 + 288) + 8LL) != v7 + 288 )
          goto LABEL_38;
        v72 = *(char ***)(v7 + 296);
        if ( *v72 != v71 )
          goto LABEL_38;
        if ( (char *)v69[1] != v70 )
          goto LABEL_38;
        if ( **((char ***)a1 + 37) != v70 )
          goto LABEL_38;
        *v72 = v70;
        *(_QWORD *)(v7 + 296) = *((_QWORD *)a1 + 37);
        **((_QWORD **)a1 + 37) = v71;
        *((_QWORD *)a1 + 37) = v72;
        v73 = *(_QWORD *)v70;
        if ( *(char **)(*(_QWORD *)v70 + 8LL) != v70 || *v72 != v70 )
          goto LABEL_38;
        *v72 = (char *)v73;
        *(_QWORD *)(v73 + 8) = v72;
        *((_QWORD *)a1 + 37) = v70;
        *(_QWORD *)v70 = v70;
LABEL_146:
        *(_BYTE *)(*(_QWORD *)v6 + 304LL) = 0;
        v74 = *(_QWORD *)v6;
        *(_QWORD *)(v74 + 1576) = MEMORY[0xFFFFF78000000320];
        KeSetEvent((PRKEVENT)(v74 + 1544), 0, 0);
        goto LABEL_9;
      }
      if ( v8 == 2 )
      {
        v48 = (__int64 *)*((_QWORD *)a1 + 36);
        v49 = 0;
        if ( v48 != (__int64 *)((char *)a1 + 288) )
        {
          do
          {
            v50 = (__int64 *)*v48;
            if ( *((_BYTE *)v48 - 29) )
            {
              if ( (__int64 *)v50[1] != v48 )
                goto LABEL_38;
              v75 = (__int64 **)v48[1];
              if ( *v75 != v48 )
                goto LABEL_38;
              *v75 = v50;
              v50[1] = (__int64)v75;
              v76 = *(_QWORD *)v6 + 288LL;
              v77 = *(__int64 ***)(*(_QWORD *)v6 + 296LL);
              if ( *v77 != (__int64 *)v76 )
                goto LABEL_38;
              *v48 = v76;
              v48[1] = (__int64)v77;
              *v77 = v48;
              *(_QWORD *)(v76 + 8) = v48;
              v49 = 1;
            }
            v48 = v50;
          }
          while ( v50 != (__int64 *)((char *)a1 + 288) );
          if ( v49 )
            goto LABEL_146;
        }
      }
    }
LABEL_9:
    v9 = (struct _VIDSCH_GLOBAL *)*((_QWORD *)a1 + 36);
    v10 = (struct _VIDSCH_GLOBAL **)((char *)a1 + 288);
    if ( v9 != (struct _VIDSCH_GLOBAL *)((char *)a1 + 288) )
    {
      while ( 1 )
      {
        HwQueueStagingList::ProcessHwQueue(
          (struct _VIDSCH_GLOBAL *)((char *)a1 + 280),
          (struct _VIDSCH_GLOBAL *)((char *)v9 - 176),
          &v87);
        v54 = *(struct _VIDSCH_GLOBAL **)v9;
        if ( *(struct _VIDSCH_GLOBAL **)(*(_QWORD *)v9 + 8LL) != v9 )
          break;
        v55 = (struct _VIDSCH_GLOBAL **)*((_QWORD *)v9 + 1);
        if ( *v55 != v9 )
          break;
        *v55 = v54;
        *((_QWORD *)v54 + 1) = v55;
        *(_QWORD *)v9 = 0;
        *((_QWORD *)v9 + 1) = 0;
        v9 = *v10;
        if ( *v10 == (struct _VIDSCH_GLOBAL *)v10 )
          goto LABEL_10;
      }
LABEL_38:
      __fastfail(3u);
    }
LABEL_10:
    *((_BYTE *)a1 + 304) = 1;
    if ( *((_DWORD *)a1 + 880) || *((_BYTE *)a1 + 3524) )
      VidSchiProcessCrossAdapterSignaledSyncObjects((struct _VIDSCH_GLOBAL *)((char *)a1 + 280));
    if ( *((_BYTE *)a1 + 59) )
    {
      v11 = (_QWORD **)((char *)a1 + 3848);
      while ( 1 )
      {
        v12 = *v11;
        if ( *v11 == v11 )
          break;
        if ( (_QWORD **)v12[1] != v11 )
          goto LABEL_38;
        v13 = (_QWORD *)*v12;
        if ( *(_QWORD **)(*v12 + 8LL) != v12 )
          goto LABEL_38;
        *v11 = v13;
        v14 = v12 - 5;
        v13[1] = v11;
        *v12 = 0;
        v12[1] = 0;
        if ( (v12[19] & 0x10) != 0 )
        {
          *((_DWORD *)v14 + 48) &= ~0x10u;
          if ( (v14[24] & 0x100) == 0 )
          {
            if ( (v14[24] & 0x200) != 0 )
            {
              if ( (v14[24] & 2) == 0 )
                VidSchiUpdateContextStatus(v14, 10, 25377);
            }
            else if ( (_QWORD *)v14[84] == v14 + 84 )
            {
              VidSchiUpdateContextStatus(v14, 0, 25394);
            }
            else if ( *((_DWORD *)v14 + 197) )
            {
              if ( (v14[24] & 0x20) != 0 )
              {
                VidSchiUpdateContextStatus(v14, 4, 23657);
              }
              else if ( (*((_DWORD *)v14 + 48) & 0x80u) != 0 )
              {
                VidSchiUpdateContextStatus(v14, 8, 23657);
              }
              else if ( (v14[24] & 0x10) != 0 )
              {
                VidSchiUpdateContextStatus(v14, 3, 23657);
              }
              else if ( (v14[24] & 0x40) != 0 )
              {
                VidSchiUpdateContextStatus(v14, 7, 23657);
              }
              else if ( (v14[24] & 8) != 0 )
              {
                VidSchiUpdateContextStatus(v14, 2, 23657);
              }
              else if ( (v14[24] & 1) == 0 && (v14[24] & 0x100) == 0 )
              {
                if ( _InterlockedCompareExchange((volatile signed __int32 *)v14 + 111, 0, 0) == 2 )
                {
                  v15 = v14[12];
                  LOBYTE(PerformanceFrequency.LowPart) = 0;
                  DpSynchronizeExecution(
                    *(_QWORD *)(*(_QWORD *)(v15 + 24) + 32LL),
                    VidSchiResetContextQuantumAtISR,
                    v14,
                    *(unsigned int *)(*(_QWORD *)(v15 + 24) + 40LL),
                    &PerformanceFrequency);
                }
                VidSchiUpdateContextStatus(v14, 5, 23657);
              }
            }
            else
            {
              VidSchiUpdateContextStatus(v14, 1, 25460);
            }
          }
        }
      }
      v16 = (_QWORD **)((char *)a1 + 3864);
      while ( 1 )
      {
        v17 = *v16;
        if ( *v16 == v16 )
          goto LABEL_39;
        if ( (_QWORD **)v17[1] != v16 )
          goto LABEL_38;
        v18 = (_QWORD *)*v17;
        if ( *(_QWORD **)(*v17 + 8LL) != v17 )
          goto LABEL_38;
        *v16 = v18;
        v19 = (struct _VIDSCH_GLOBAL *)(v17 + 19);
        v18[1] = v16;
        v20 = v17[19] == 0;
        *v17 = 0;
        v17[1] = 0;
        if ( v20 )
        {
          v21 = (struct _VIDSCH_GLOBAL **)*((_QWORD *)a1 + 37);
          if ( *v21 != (struct _VIDSCH_GLOBAL *)((char *)a1 + 288) )
            goto LABEL_38;
          *(_QWORD *)v19 = (char *)a1 + 288;
          v17[20] = v21;
          *v21 = v19;
          *((_QWORD *)a1 + 37) = v19;
          *((_BYTE *)a1 + 304) = 0;
        }
      }
    }
    while ( 1 )
    {
LABEL_39:
      v22 = 0;
      memset(&LockHandle, 0, sizeof(LockHandle));
      if ( *((_DWORD *)a1 + 216) )
      {
        v23 = *((_QWORD *)a1 + 34);
        if ( v23 && (*(_DWORD *)(v23 + 192) & 1) != 0 )
        {
          v22 = (struct _VIDSCH_CONTEXT *)*((_QWORD *)a1 + 34);
        }
        else
        {
          RtlCopyBitMapEx((char *)a1 + 584, (char *)a1 + 680, 0);
          RtlIntersectBitMapsEx((char *)a1 + 680, (char *)a1 + 632);
          if ( (unsigned __int8)RtlAreBitsClearEx((char *)a1 + 680, 0, *((_QWORD *)a1 + 85)) )
            RtlCopyBitMapEx((char *)a1 + 584, (char *)a1 + 680, 0);
          SetBits = RtlFindSetBitsEx((char *)a1 + 680, 1, (unsigned int)(*((_DWORD *)a1 + 214) + 1));
          if ( SetBits == -1 )
            goto LABEL_118;
          v25 = (__int64 *)*((_QWORD *)a1 + 97);
          if ( (unsigned int)SetBits < *((_DWORD *)a1 + 212) )
            v25 += (unsigned int)SetBits;
          v26 = *v25;
          *((_DWORD *)a1 + 214) = SetBits;
          if ( !v26 )
          {
LABEL_118:
            v2 = 0;
          }
          else
          {
            v2 = 0;
            if ( *(_DWORD *)(v26 + 1900) )
            {
              v27 = *(_QWORD *)(v26 + 24);
              LOBYTE(PerformanceFrequency.LowPart) = 0;
              v89[0] = v26;
              memset(&v89[1], 0, 24);
              DpSynchronizeExecution(
                *(_QWORD *)(v27 + 32),
                VidSchiUpdateNodeRunningTimeAtISR,
                v89,
                *(unsigned int *)(v27 + 40),
                &PerformanceFrequency);
            }
            v28 = *(unsigned int *)(v26 + 1896);
            if ( *(_BYTE *)(v26 + 2152)
              && (v28 & 0xC0000000) == 0
              && (v58 = *(_QWORD *)(v26 + 24), (v28 & (0xFFFFFFFFuLL >> (31 - *(_BYTE *)(v58 + 224)))) != 0) )
            {
              MostSignificantBit = RtlFindMostSignificantBit(v28 & (0xFFFFFFFFuLL >> (31 - *(_BYTE *)(v58 + 224))));
              v22 = VidSchiSelectContextFromThisPriority((struct _VIDSCH_NODE *)v26, MostSignificantBit, 1);
              if ( v22 )
              {
                VidSchiUpdateNodeYieldStatus((struct _VIDSCH_NODE *)v26);
              }
              else
              {
                v60 = RtlFindMostSignificantBit(*(unsigned int *)(v26 + 1896));
                v22 = VidSchiSelectContextFromThisPriority((struct _VIDSCH_NODE *)v26, v60, 0);
                if ( !*(_QWORD *)(v26 + 2128) )
                {
                  PerformanceFrequency.QuadPart = 0;
                  v61 = KeQueryPerformanceCounter(&PerformanceFrequency);
                  v62 = *(_DWORD *)(*((_QWORD *)v22 + 13) + 512LL);
                  v63 = 0;
                  if ( v62 <= *((_DWORD *)a1 + 12) )
                    v63 = v62;
                  if ( !*(_DWORD *)(*((_QWORD *)a1 + v63 + 441) + 83104LL) )
                  {
                    WdLogSingleEntry1(3, (unsigned int)v63);
                    WdLogGlobalForLineNumber = 18980;
                  }
                  ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))VidSchiStartNodeYield)(
                    v26,
                    (LARGE_INTEGER)v61.QuadPart,
                    (union _LARGE_INTEGER)PerformanceFrequency.QuadPart);
                  v2 = 0;
                }
                VidSchiProfilePerformanceTick(20, (_DWORD)a1, v26, 0, (__int64)v22, 0, 0, 1);
              }
            }
            else
            {
              v29 = RtlFindMostSignificantBit(*(unsigned int *)(v26 + 1896));
              v22 = VidSchiSelectContextFromThisPriority((struct _VIDSCH_NODE *)v26, v29, 0);
              if ( (*((_DWORD *)a1 + 726) & 8) != 0 && *(_BYTE *)(v26 + 2152) && !*(_QWORD *)(v26 + 2128) )
              {
                PerformanceFrequency.QuadPart = 0;
                v64 = KeQueryPerformanceCounter(&PerformanceFrequency);
                v65 = *(_DWORD *)(*((_QWORD *)v22 + 13) + 512LL);
                v66 = 0;
                if ( v65 <= *((_DWORD *)a1 + 12) )
                  v66 = v65;
                if ( !*(_DWORD *)(*((_QWORD *)a1 + v66 + 441) + 83104LL) )
                {
                  WdLogSingleEntry1(3, (unsigned int)v66);
                  WdLogGlobalForLineNumber = 18980;
                }
                ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))VidSchiStartNodeYield)(
                  v26,
                  (LARGE_INTEGER)v64.QuadPart,
                  (union _LARGE_INTEGER)PerformanceFrequency.QuadPart);
                v2 = 0;
              }
              VidSchiProfilePerformanceTick(20, (_DWORD)a1, v26, 0, (__int64)v22, 0, 0, 0);
            }
          }
        }
      }
      VidSchiProfilePerformanceTick(2, (_DWORD)a1, 0, 0, (__int64)v22, 0, 0, 0);
      if ( !v22 )
      {
        VidSchiLogAggregatedTelemetry(a1);
        goto LABEL_69;
      }
      v30 = VidSchiSwitchContextWithCheck(v22);
      v2 = v30;
      if ( v30 == 1 )
        break;
      if ( v30 != 3 )
        goto LABEL_69;
      v2 = 0;
    }
    v31 = *((_QWORD *)v22 + 12);
    v32 = *((_DWORD *)v22 + 48);
    v3 = 0;
    memset(v89, 0, 24);
    v33 = *(_QWORD *)(v31 + 24);
    if ( (v32 & 1) != 0 )
    {
      v3 = *((_QWORD *)v22 + 82);
      if ( v3 )
      {
        --*((_DWORD *)v22 + 197);
        --*(_DWORD *)(v31 + 3016);
        --*(_DWORD *)(v33 + 864);
        v34 = *(_QWORD *)(v3 + 32);
        if ( (struct _VIDSCH_CONTEXT *)v34 == (struct _VIDSCH_CONTEXT *)((char *)v22 + 672) )
        {
          *((_QWORD *)v22 + 82) = 0;
          *((_DWORD *)v22 + 163) &= 0xFFFFFFF0;
          VidSchiUpdateContextStatus(v22, 1, 19251);
        }
        else
        {
          *((_QWORD *)v22 + 82) = v34 - 32;
          if ( v34 == 32 )
          {
            *((_DWORD *)v22 + 163) &= 0xFFFFFFF8;
            v41 = *((_DWORD *)v22 + 163) & 0xFFFFFFF7;
          }
          else
          {
            v35 = 0;
            v36 = ((unsigned int)(*(_DWORD *)(v34 + 16) - 4) <= 1) | *((_DWORD *)v22 + 163) & 0xFFFFFFFE;
            *((_DWORD *)v22 + 163) = v36;
            if ( *(_DWORD *)(v34 + 16) == 3 )
              v35 = 2;
            v37 = v36 & 0xFFFFFFFD | v35;
            *((_DWORD *)v22 + 163) = v37;
            v38 = 0;
            if ( *(_DWORD *)(v34 + 16) == 7 )
              v38 = 4;
            v39 = v37 & 0xFFFFFFFB | v38;
            *((_DWORD *)v22 + 163) = v39;
            v40 = 0;
            if ( *(_DWORD *)(v34 + 16) == 6 )
              v40 = 8;
            v41 = v39 & 0xFFFFFFF7 | v40;
          }
          *((_DWORD *)v22 + 163) = v41;
        }
        VidSchiProfilePerformanceTick(5, v33, 0, 0, 0, v3, 0, 0);
      }
    }
    *((_DWORD *)v22 + 48) |= 0x400u;
LABEL_69:
    if ( *((_DWORD *)a1 + 77) != 1 )
      goto LABEL_72;
    v42 = *(_QWORD *)v6;
    v43 = *(_DWORD *)(*(_QWORD *)v6 + 312LL);
    if ( v43 != 1 )
    {
      if ( v43 != 2 )
        goto LABEL_72;
      v51 = (__int64 *)*((_QWORD *)a1 + 36);
      v52 = 0;
      if ( v51 == (__int64 *)v10 )
        goto LABEL_72;
      do
      {
        v53 = *v51;
        if ( *((_BYTE *)v51 - 29) )
        {
          if ( *(__int64 **)(v53 + 8) != v51 )
            goto LABEL_38;
          v84 = (__int64 **)v51[1];
          if ( *v84 != v51 )
            goto LABEL_38;
          *v84 = (__int64 *)v53;
          *(_QWORD *)(v53 + 8) = v84;
          v85 = *(_QWORD *)v6 + 288LL;
          v86 = *(__int64 ***)(*(_QWORD *)v6 + 296LL);
          if ( *v86 != (__int64 *)v85 )
            goto LABEL_38;
          *v51 = v85;
          v51[1] = (__int64)v86;
          *v86 = v51;
          *(_QWORD *)(v85 + 8) = v51;
          v52 = 1;
        }
        v51 = (__int64 *)v53;
      }
      while ( (struct _VIDSCH_GLOBAL **)v53 != v10 );
      if ( !v52 )
        goto LABEL_72;
      goto LABEL_159;
    }
    v78 = (struct _VIDSCH_GLOBAL **)*((_QWORD *)a1 + 36);
    if ( v78 != v10 )
    {
      v79 = v42 + 288;
      if ( *(_QWORD *)(*(_QWORD *)(v42 + 288) + 8LL) != v42 + 288 )
        goto LABEL_38;
      v80 = *(struct _VIDSCH_GLOBAL ****)(v42 + 296);
      if ( *v80 != (struct _VIDSCH_GLOBAL **)v79 )
        goto LABEL_38;
      v81 = (char *)a1 + 288;
      if ( v78[1] != (struct _VIDSCH_GLOBAL *)((char *)a1 + 288) )
        goto LABEL_38;
      if ( **((char ***)a1 + 37) != v81 )
        goto LABEL_38;
      *v80 = (struct _VIDSCH_GLOBAL **)v81;
      *(_QWORD *)(v79 + 8) = *((_QWORD *)a1 + 37);
      **((_QWORD **)a1 + 37) = v79;
      *((_QWORD *)a1 + 37) = v80;
      v82 = *((_QWORD *)a1 + 36);
      if ( *(struct _VIDSCH_GLOBAL ***)(v82 + 8) != v10 || *v80 != v10 )
        goto LABEL_38;
      *v80 = (struct _VIDSCH_GLOBAL **)v82;
      *(_QWORD *)(v82 + 8) = v80;
      *((_QWORD *)a1 + 37) = v10;
      *((_QWORD *)a1 + 36) = v10;
LABEL_159:
      *(_BYTE *)(*(_QWORD *)v6 + 304LL) = 0;
      v83 = *(_QWORD *)v6;
      *(_QWORD *)(v83 + 1576) = MEMORY[0xFFFFF78000000320];
      KeSetEvent((PRKEVENT)(v83 + 1544), 0, 0);
    }
LABEL_72:
    for ( i = *v10; *v10 != (struct _VIDSCH_GLOBAL *)v10; i = *v10 )
    {
      HwQueueStagingList::ProcessHwQueue(
        (struct _VIDSCH_GLOBAL *)((char *)a1 + 280),
        (struct _VIDSCH_GLOBAL *)((char *)i - 176),
        &v87);
      v56 = *(struct _VIDSCH_GLOBAL **)i;
      if ( *(struct _VIDSCH_GLOBAL **)(*(_QWORD *)i + 8LL) != i )
        goto LABEL_38;
      v57 = (struct _VIDSCH_GLOBAL **)*((_QWORD *)i + 1);
      if ( *v57 != i )
        goto LABEL_38;
      *v57 = v56;
      *((_QWORD *)v56 + 1) = v57;
      *(_QWORD *)i = 0;
      *((_QWORD *)i + 1) = 0;
    }
    *((_BYTE *)a1 + 304) = 1;
    KeReleaseInStackQueuedSpinLock(&v87);
    if ( v2 == 1 )
      break;
    if ( v2 == 4 )
    {
      v2 = 0;
      *(_QWORD *)(*((_QWORD *)v22 + 12) + 232LL) = 0;
      VidSchiSubmitPreemptionCommand(*((_QWORD *)v22 + 12));
    }
    else
    {
      v20 = (v2 & 0xFFFFFFFD) == 0;
      v2 = 0;
      if ( v20 )
      {
LABEL_79:
        if ( (unsigned int)VidSchiWaitForSchedulerEvents(a1) == 258 )
          break;
      }
    }
  }
  if ( *((_DWORD *)a1 + 835) )
    *a2 = 1;
  return v3;
}

```

## disassembly

```asm
0x14000f5a0  mov     [rsp-8+arg_18], rbx
0x14000f5a5  mov     [rsp-8+arg_8], rdx
0x14000f5aa  push    rbp
0x14000f5ab  push    rsi
0x14000f5ac  push    rdi
0x14000f5ad  push    r12
0x14000f5af  push    r13
0x14000f5b1  push    r14
0x14000f5b3  push    r15
0x14000f5b5  lea     rbp, [rsp-27h]
0x14000f5ba  sub     rsp, 90h
0x14000f5c1  xor     r14d, r14d
0x14000f5c4  xorps   xmm0, xmm0
0x14000f5c7  mov     r13d, r14d
0x14000f5ca  xor     eax, eax
0x14000f5cc  mov     [rdx], r13b
0x14000f5cf  mov     rbx, rcx
0x14000f5d2  mov     [rbp+57h+arg_0], r13b
0x14000f5d6  mov     qword ptr [rbp+57h+var_80.OldIrql], rax
0x14000f5da  movups  xmmword ptr [rbp+57h+var_80.LockQueue.Next], xmm0
0x14000f5de  mov     rsi, 0FFFFF78000000320h
0x14000f5e8  mov     eax, [rbx+0D0Ch]
0x14000f5ee  sub     eax, 2
0x14000f5f1  cmp     eax, 1
0x14000f5f4  jbe     short loc_14000F60A
0x14000f5f6  lea     rdx, [rbp+57h+arg_0]
0x14000f5fa  mov     rcx, rbx; struct _VIDSCH_GLOBAL *
0x14000f5fd  call    VidSchiCheckHwProgress
0x14000f602  test    eax, eax
0x14000f604  jz      loc_14000FBF4
0x14000f60a  xorps   xmm0, xmm0
0x14000f60d  lea     rcx, [rbx+850h]; SpinLock
0x14000f614  xor     eax, eax
0x14000f616  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x14000f61a  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x14000f61e  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x14000f622  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000f629  nop     dword ptr [rax+rax+00h]
0x14000f62e  lea     rdi, [rbx+870h]
0x14000f635  mov     r9, [rdi]
0x14000f638  cmp     r9, rdi
0x14000f63b  jnz     loc_14000FC70
0x14000f641  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x14000f645  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000f64c  nop     dword ptr [rax+rax+00h]
0x14000f651  mov     rax, ds:0FFFFF78000000320h
0x14000f65b  lea     rcx, [rbx+640h]; Event
0x14000f662  mov     [rbx+670h], rax
0x14000f669  call    cs:__imp_KeReadStateEvent
0x14000f670  nop     dword ptr [rax+rax+00h]
0x14000f675  test    eax, eax
0x14000f677  jg      loc_14000FC46
0x14000f67d  lea     rcx, [rbx+830h]; SpinLock
0x14000f684  lea     rdx, [rbp+57h+var_80]; LockHandle
0x14000f688  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000f68f  nop     dword ptr [rax+rax+00h]
0x14000f694  lea     r15, [rbx+118h]
0x14000f69b  cmp     dword ptr [r15+1Ch], 1
0x14000f6a0  jnz     short loc_14000F6BD
0x14000f6a2  mov     rcx, [r15]
0x14000f6a5  mov     eax, [rcx+138h]
0x14000f6ab  cmp     eax, 1
0x14000f6ae  jz      loc_14001005F
0x14000f6b4  cmp     eax, 2
0x14000f6b7  jz      loc_14000FCBA
0x14000f6bd  mov     rdi, [r15+8]
0x14000f6c1  lea     r12, [r15+8]
0x14000f6c5  cmp     rdi, r12
0x14000f6c8  jnz     loc_14000FDB0
0x14000f6ce  mov     byte ptr [r15+18h], 1
0x14000f6d3  cmp     dword ptr [rbx+0DC0h], 0
0x14000f6da  jnz     loc_14000FE69
0x14000f6e0  cmp     byte ptr [rbx+0DC4h], 0
0x14000f6e7  jnz     loc_14000FE69
0x14000f6ed  cmp     byte ptr [rbx+3Bh], 0
0x14000f6f1  jz      loc_14000F8A0
0x14000f6f7  lea     rsi, [rbx+0F08h]
0x14000f6fe  mov     rax, [rsi]
0x14000f701  cmp     rax, rsi
0x14000f704  jz      loc_14000F846
0x14000f70a  cmp     [rax+8], rsi
0x14000f70e  jnz     loc_14000F896
0x14000f714  mov     rcx, [rax]
0x14000f717  cmp     [rcx+8], rax
0x14000f71b  jnz     loc_14000F896
0x14000f721  mov     [rsi], rcx
0x14000f724  lea     rdi, [rax-28h]
0x14000f728  mov     [rcx+8], rsi
0x14000f72c  mov     [rax], r14
0x14000f72f  mov     [rax+8], r14
0x14000f733  mov     eax, [rdi+0C0h]
0x14000f739  test    al, 10h
0x14000f73b  jz      short loc_14000F6FE
0x14000f73d  mov     eax, [rdi+0C0h]
0x14000f743  and     eax, 0FFFFFFEFh
0x14000f746  mov     [rdi+0C0h], eax
0x14000f74c  mov     eax, [rdi+0C0h]
0x14000f752  bt      eax, 8
0x14000f756  jb      short loc_14000F6FE
0x14000f758  mov     eax, [rdi+0C0h]
0x14000f75e  bt      eax, 9
0x14000f762  jb      loc_140010271
0x14000f768  lea     rax, [rdi+2A0h]
0x14000f76f  cmp     [rax], rax
0x14000f772  jz      loc_14000FD7E
0x14000f778  cmp     dword ptr [rdi+314h], 0
0x14000f77f  jz      loc_14000FD66
0x14000f785  mov     eax, [rdi+0C0h]
0x14000f78b  test    al, 20h
0x14000f78d  jnz     loc_14000FEF8
0x14000f793  mov     eax, [rdi+0C0h]
0x14000f799  test    al, al
0x14000f79b  js      loc_140010297
0x14000f7a1  mov     eax, [rdi+0C0h]
0x14000f7a7  test    al, 10h
0x14000f7a9  jnz     loc_140010015
0x14000f7af  mov     eax, [rdi+0C0h]
0x14000f7b5  test    al, 40h
0x14000f7b7  jnz     loc_1400102AF
0x14000f7bd  mov     eax, [rdi+0C0h]
0x14000f7c3  test    al, 8
0x14000f7c5  jnz     loc_14000FED8
0x14000f7cb  mov     eax, [rdi+0C0h]
0x14000f7d1  test    al, 1
0x14000f7d3  jnz     loc_14000F6FE
0x14000f7d9  mov     eax, [rdi+0C0h]
0x14000f7df  bt      eax, 8
0x14000f7e3  jb      loc_14000F6FE
0x14000f7e9  mov     ecx, r14d
0x14000f7ec  xor     eax, eax
0x14000f7ee  lock cmpxchg [rdi+1BCh], ecx
0x14000f7f6  cmp     eax, 2
0x14000f7f9  jnz     short loc_14000F82E
0x14000f7fb  mov     rax, [rdi+60h]
0x14000f7ff  lea     rdx, VidSchiResetContextQuantumAtISR
0x14000f806  mov     byte ptr [rbp+57h+PerformanceFrequency], 0
0x14000f80a  mov     r8, rdi
0x14000f80d  mov     rcx, [rax+18h]
0x14000f811  lea     rax, [rbp+57h+PerformanceFrequency]
0x14000f815  mov     [rsp+0C0h+var_A0], rax
0x14000f81a  mov     r9d, [rcx+28h]
0x14000f81e  mov     rcx, [rcx+20h]
0x14000f822  call    cs:__imp_DpSynchronizeExecution
0x14000f829  nop     dword ptr [rax+rax+00h]
0x14000f82e  mov     edx, 5
0x14000f833  mov     r8d, 5C69h
0x14000f839  mov     rcx, rdi
0x14000f83c  call    VidSchiUpdateContextStatus
0x14000f841  jmp     loc_14000F6FE
0x14000f846  lea     rcx, [rbx+0F18h]
0x14000f84d  mov     rax, [rcx]
0x14000f850  cmp     rax, rcx
0x14000f853  jz      short loc_14000F8A0
0x14000f855  cmp     [rax+8], rcx
0x14000f859  jnz     short loc_14000F896
0x14000f85b  mov     rdx, [rax]
0x14000f85e  cmp     [rdx+8], rax
0x14000f862  jnz     short loc_14000F896
0x14000f864  mov     [rcx], rdx
0x14000f867  lea     r9, [rax+98h]
0x14000f86e  mov     [rdx+8], rcx
0x14000f872  cmp     qword ptr [r9], 0
0x14000f876  mov     [rax], r14
0x14000f879  mov     [rax+8], r14
0x14000f87d  jnz     short loc_14000F84D
0x14000f87f  mov     r8, [rbx+128h]
0x14000f886  lea     rdx, [rbx+120h]
0x14000f88d  cmp     [r8], rdx
0x14000f890  jz      loc_14000FE4C
0x14000f896  mov     ecx, 3
0x14000f89b  int     29h; Win8: RtlFailFast(ecx)
0x14000f8a0  xor     eax, eax
0x14000f8a2  xorps   xmm0, xmm0
0x14000f8a5  mov     rsi, r14
0x14000f8a8  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x14000f8ac  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x14000f8b0  cmp     [rbx+360h], eax
0x14000f8b6  jz      loc_14000FA44
0x14000f8bc  mov     rax, [rbx+110h]
0x14000f8c3  test    rax, rax
0x14000f8c6  jz      short loc_14000F8D6
0x14000f8c8  mov     eax, [rax+0C0h]
0x14000f8ce  test    al, 1
0x14000f8d0  jnz     loc_14000FD5A
0x14000f8d6  lea     rdi, [rbx+2A8h]
0x14000f8dd  xor     r8d, r8d
0x14000f8e0  mov     rdx, rdi
0x14000f8e3  lea     rcx, [rbx+248h]
0x14000f8ea  call    cs:__imp_RtlCopyBitMapEx
0x14000f8f1  nop     dword ptr [rax+rax+00h]
0x14000f8f6  lea     rdx, [rbx+278h]
0x14000f8fd  mov     rcx, rdi
0x14000f900  call    cs:__imp_RtlIntersectBitMapsEx
0x14000f907  nop     dword ptr [rax+rax+00h]
0x14000f90c  mov     r8, [rdi]
0x14000f90f  xor     edx, edx
0x14000f911  mov     rcx, rdi
0x14000f914  call    cs:__imp_RtlAreBitsClearEx
0x14000f91b  nop     dword ptr [rax+rax+00h]
0x14000f920  test    al, al
0x14000f922  jz      short loc_14000F93D
0x14000f924  xor     r8d, r8d
0x14000f927  lea     rcx, [rbx+248h]
0x14000f92e  mov     rdx, rdi
0x14000f931  call    cs:__imp_RtlCopyBitMapEx
0x14000f938  nop     dword ptr [rax+rax+00h]
0x14000f93d  mov     r8d, [rbx+358h]
0x14000f944  mov     edx, 1
0x14000f949  inc     r8d
0x14000f94c  mov     rcx, rdi
0x14000f94f  call    cs:__imp_RtlFindSetBitsEx
0x14000f956  nop     dword ptr [rax+rax+00h]
0x14000f95b  mov     rcx, rax
0x14000f95e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000f962  jz      loc_14000FEF0
0x14000f968  mov     rdi, [rbx+308h]
0x14000f96f  cmp     ecx, [rbx+350h]
0x14000f975  jnb     short loc_14000F97D
0x14000f977  mov     eax, ecx
0x14000f979  lea     rdi, [rdi+rax*8]
0x14000f97d  mov     rdi, [rdi]
0x14000f980  mov     [rbx+358h], ecx
0x14000f986  test    rdi, rdi
0x14000f989  jz      loc_14000FEF0
0x14000f98f  mov     eax, [rdi+76Ch]
0x14000f995  xor     r14d, r14d
0x14000f998  test    eax, eax
0x14000f99a  jz      short loc_14000F9DC
0x14000f99c  mov     rcx, [rdi+18h]
0x14000f9a0  lea     rax, [rbp+57h+PerformanceFrequency]
0x14000f9a4  mov     byte ptr [rbp+57h+PerformanceFrequency], r14b
0x14000f9a8  lea     r8, [rbp+57h+var_50]
0x14000f9ac  mov     [rbp+57h+var_38], r14
0x14000f9b0  lea     rdx, VidSchiUpdateNodeRunningTimeAtISR
0x14000f9b7  mov     qword ptr [rbp+57h+var_50], rdi
0x14000f9bb  xorps   xmm0, xmm0
0x14000f9be  movdqu  xmmword ptr [rbp+57h+var_50+8], xmm0
0x14000f9c3  mov     r9d, [rcx+28h]
0x14000f9c7  mov     rcx, [rcx+20h]
0x14000f9cb  mov     [rsp+0C0h+var_A0], rax
0x14000f9d0  call    cs:__imp_DpSynchronizeExecution
0x14000f9d7  nop     dword ptr [rax+rax+00h]
0x14000f9dc  cmp     byte ptr [rdi+868h], 0
0x14000f9e3  mov     edx, [rdi+768h]
0x14000f9e9  jnz     loc_14000FE79
0x14000f9ef  mov     rcx, rdx; Set
0x14000f9f2  call    cs:__imp_RtlFindMostSignificantBit
0x14000f9f9  nop     dword ptr [rax+rax+00h]
0x14000f9fe  movsx   edx, al; unsigned int
0x14000fa01  xor     r8d, r8d; bool
0x14000fa04  mov     rcx, rdi; struct _VIDSCH_NODE *
0x14000fa07  call    ?VidSchiSelectContextFromThisPriority@@YAPEAU_VIDSCH_CONTEXT@@PEAU_VIDSCH_NODE@@K_N@Z; VidSchiSelectContextFromThisPriority(_VIDSCH_NODE *,ulong,bool)
0x14000fa0c  mov     rsi, rax
0x14000fa0f  mov     eax, [rbx+0B58h]
0x14000fa15  test    al, 8
0x14000fa17  jnz     loc_14000FFA0
0x14000fa1d  mov     [rsp+0C0h+var_88], r14
0x14000fa22  mov     [rsp+0C0h+var_90], r14
0x14000fa27  xor     r9d, r9d
0x14000fa2a  mov     [rsp+0C0h+var_98], r14
0x14000fa2f  mov     r8, rdi
0x14000fa32  mov     rdx, rbx
0x14000fa35  mov     [rsp+0C0h+var_A0], rsi
0x14000fa3a  mov     ecx, 14h
0x14000fa3f  call    VidSchiProfilePerformanceTick
0x14000fa44  mov     [rsp+0C0h+var_88], r14
0x14000fa49  xor     r9d, r9d
0x14000fa4c  mov     [rsp+0C0h+var_90], r14
0x14000fa51  xor     r8d, r8d
0x14000fa54  mov     [rsp+0C0h+var_98], r14
0x14000fa59  mov     rdx, rbx
0x14000fa5c  mov     ecx, 2
0x14000fa61  mov     [rsp+0C0h+var_A0], rsi
0x14000fa66  call    VidSchiProfilePerformanceTick
0x14000fa6b  test    rsi, rsi
0x14000fa6e  jz      loc_14000FC5B
0x14000fa74  mov     rcx, rsi
0x14000fa77  call    VidSchiSwitchContextWithCheck
0x14000fa7c  mov     r14d, eax
0x14000fa7f  cmp     eax, 1
0x14000fa82  jnz     loc_14000FD49
0x14000fa88  mov     rcx, [rsi+60h]
0x14000fa8c  xor     eax, eax
0x14000fa8e  mov     qword ptr [rbp+57h+var_50+10h], rax
0x14000fa92  xor     r9d, r9d
0x14000fa95  mov     eax, [rsi+0C0h]
0x14000fa9b  xorps   xmm0, xmm0
0x14000fa9e  mov     r13d, r9d
0x14000faa1  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x14000faa5  mov     rdi, [rcx+18h]
0x14000faa9  test    r14b, al
0x14000faac  jz      loc_14000FB9A
0x14000fab2  mov     r13, [rsi+290h]
0x14000fab9  test    r13, r13
0x14000fabc  jz      loc_14000FB9A
0x14000fac2  mov     eax, 0FFFFFFFFh
0x14000fac7  add     [rsi+314h], eax
0x14000facd  add     [rcx+0BC8h], eax
0x14000fad3  add     [rdi+360h], eax
0x14000fad9  lea     rax, [rsi+2A0h]
  ... truncated ...
```
