# VidSchiScheduleCommandToRun

- ea: `0x14000f040`
- end: `0x14000fdb3`
- name: `VidSchiScheduleCommandToRun`
- size: `3443`
- prototype: `__int64 __fastcall(struct _VIDSCH_GLOBAL *)`
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400e5a50`

## callees

- `0x14000a2ac`
- `0x14000a488`
- `0x14000da88`
- `0x14000df60`
- `0x14000e840`
- `0x14000f040`
- `0x140010200`
- `0x140011610`
- `0x140017930`
- `0x14001f794`
- `0x14002fee8`
- `0x140042c38`
- `0x1400e4e44`
- `0x1400e5280`
- `0x1400e6ca0`

## import_xrefs

- `ntoskrnl!KeReadStateEvent` at `0x14000f109`
- `ntoskrnl!KeReadStateEvent` at `0x14000f109`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000f0c2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000f128`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000f0c2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000f128`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000f0e5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000f682`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000f0e5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000f682`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000f492`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000f949`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000f9b6`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000f492`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000f949`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000f9b6`
- `ntoskrnl!RtlCopyBitMapEx` at `0x14000f38a`
- `ntoskrnl!RtlCopyBitMapEx` at `0x14000f3d1`
- `ntoskrnl!RtlCopyBitMapEx` at `0x14000f38a`
- `ntoskrnl!RtlCopyBitMapEx` at `0x14000f3d1`
- `ntoskrnl!RtlIntersectBitMapsEx` at `0x14000f3a0`
- `ntoskrnl!RtlIntersectBitMapsEx` at `0x14000f3a0`
- `ntoskrnl!RtlAreBitsClearEx` at `0x14000f3b4`
- `ntoskrnl!RtlAreBitsClearEx` at `0x14000f3b4`
- `ntoskrnl!RtlFindSetBitsEx` at `0x14000f3ef`
- `ntoskrnl!RtlFindSetBitsEx` at `0x14000f3ef`
- `ntoskrnl!KeSetEvent` at `0x14000fba8`
- `ntoskrnl!KeSetEvent` at `0x14000fcb7`
- `ntoskrnl!KeSetEvent` at `0x14000fba8`
- `ntoskrnl!KeSetEvent` at `0x14000fcb7`
- `watchdog!WdLogSingleEntry1` at `0x14000fd6c`
- `watchdog!WdLogSingleEntry1` at `0x14000fd92`
- `watchdog!WdLogSingleEntry1` at `0x14000fd6c`
- `watchdog!WdLogSingleEntry1` at `0x14000fd92`
- `dxgkrnl!DpSynchronizeExecution` at `0x14000f2c2`
- `dxgkrnl!DpSynchronizeExecution` at `0x14000f470`
- `dxgkrnl!DpSynchronizeExecution` at `0x14000f2c2`
- `dxgkrnl!DpSynchronizeExecution` at `0x14000f470`
- `HAL!KeQueryPerformanceCounter` at `0x14000f9e5`
- `HAL!KeQueryPerformanceCounter` at `0x14000fa63`
- `HAL!KeQueryPerformanceCounter` at `0x14000f9e5`
- `HAL!KeQueryPerformanceCounter` at `0x14000fa63`

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
      VidSchiProcessCrossAdapterSignaledSyncObjects((struct _VIDSCH_GLOBAL *)((char *)a1 + 280), (__int64)a1);
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
                VidSchiUpdateContextStatus(v14, 10, 25387);
            }
            else if ( (_QWORD *)v14[84] == v14 + 84 )
            {
              VidSchiUpdateContextStatus(v14, 0, 25404);
            }
            else if ( *((_DWORD *)v14 + 197) )
            {
              if ( (v14[24] & 0x20) != 0 )
              {
                VidSchiUpdateContextStatus(v14, 4, 23667);
              }
              else if ( (*((_DWORD *)v14 + 48) & 0x80u) != 0 )
              {
                VidSchiUpdateContextStatus(v14, 8, 23667);
              }
              else if ( (v14[24] & 0x10) != 0 )
              {
                VidSchiUpdateContextStatus(v14, 3, 23667);
              }
              else if ( (v14[24] & 0x40) != 0 )
              {
                VidSchiUpdateContextStatus(v14, 7, 23667);
              }
              else if ( (v14[24] & 8) != 0 )
              {
                VidSchiUpdateContextStatus(v14, 2, 23667);
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
                VidSchiUpdateContextStatus(v14, 5, 23667);
              }
            }
            else
            {
              VidSchiUpdateContextStatus(v14, 1, 25470);
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
                    WdLogGlobalForLineNumber = 18990;
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
                  WdLogGlobalForLineNumber = 18990;
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
          VidSchiUpdateContextStatus(v22, 1, 19261);
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
0x14000f040  mov     [rsp-8+arg_18], rbx
0x14000f045  mov     [rsp-8+arg_8], rdx
0x14000f04a  push    rbp
0x14000f04b  push    rsi
0x14000f04c  push    rdi
0x14000f04d  push    r12
0x14000f04f  push    r13
0x14000f051  push    r14
0x14000f053  push    r15
0x14000f055  lea     rbp, [rsp-27h]
0x14000f05a  sub     rsp, 90h
0x14000f061  xor     r14d, r14d
0x14000f064  xorps   xmm0, xmm0
0x14000f067  mov     r13d, r14d
0x14000f06a  xor     eax, eax
0x14000f06c  mov     [rdx], r13b
0x14000f06f  mov     rbx, rcx
0x14000f072  mov     [rbp+57h+arg_0], r13b
0x14000f076  mov     qword ptr [rbp+57h+var_80.OldIrql], rax
0x14000f07a  movups  xmmword ptr [rbp+57h+var_80.LockQueue.Next], xmm0
0x14000f07e  mov     rsi, 0FFFFF78000000320h
0x14000f088  mov     eax, [rbx+0D0Ch]
0x14000f08e  sub     eax, 2
0x14000f091  cmp     eax, 1
0x14000f094  jbe     short loc_14000F0AA
0x14000f096  lea     rdx, [rbp+57h+arg_0]
0x14000f09a  mov     rcx, rbx; struct _VIDSCH_GLOBAL *
0x14000f09d  call    VidSchiCheckHwProgress
0x14000f0a2  test    eax, eax
0x14000f0a4  jz      loc_14000F694
0x14000f0aa  xorps   xmm0, xmm0
0x14000f0ad  lea     rcx, [rbx+850h]; SpinLock
0x14000f0b4  xor     eax, eax
0x14000f0b6  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x14000f0ba  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x14000f0be  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x14000f0c2  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000f0c9  nop     dword ptr [rax+rax+00h]
0x14000f0ce  lea     rdi, [rbx+870h]
0x14000f0d5  mov     r9, [rdi]
0x14000f0d8  cmp     r9, rdi
0x14000f0db  jnz     loc_14000F710
0x14000f0e1  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x14000f0e5  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000f0ec  nop     dword ptr [rax+rax+00h]
0x14000f0f1  mov     rax, ds:0FFFFF78000000320h
0x14000f0fb  lea     rcx, [rbx+640h]; Event
0x14000f102  mov     [rbx+670h], rax
0x14000f109  call    cs:__imp_KeReadStateEvent
0x14000f110  nop     dword ptr [rax+rax+00h]
0x14000f115  test    eax, eax
0x14000f117  jg      loc_14000F6E6
0x14000f11d  lea     rcx, [rbx+830h]; SpinLock
0x14000f124  lea     rdx, [rbp+57h+var_80]; LockHandle
0x14000f128  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000f12f  nop     dword ptr [rax+rax+00h]
0x14000f134  lea     r15, [rbx+118h]
0x14000f13b  cmp     dword ptr [r15+1Ch], 1
0x14000f140  jnz     short loc_14000F15D
0x14000f142  mov     rcx, [r15]
0x14000f145  mov     eax, [rcx+138h]
0x14000f14b  cmp     eax, 1
0x14000f14e  jz      loc_14000FAFF
0x14000f154  cmp     eax, 2
0x14000f157  jz      loc_14000F75A
0x14000f15d  mov     rdi, [r15+8]
0x14000f161  lea     r12, [r15+8]
0x14000f165  cmp     rdi, r12
0x14000f168  jnz     loc_14000F850
0x14000f16e  mov     byte ptr [r15+18h], 1
0x14000f173  cmp     dword ptr [rbx+0DC0h], 0
0x14000f17a  jnz     loc_14000F909
0x14000f180  cmp     byte ptr [rbx+0DC4h], 0
0x14000f187  jnz     loc_14000F909
0x14000f18d  cmp     byte ptr [rbx+3Bh], 0
0x14000f191  jz      loc_14000F340
0x14000f197  lea     rsi, [rbx+0F08h]
0x14000f19e  mov     rax, [rsi]
0x14000f1a1  cmp     rax, rsi
0x14000f1a4  jz      loc_14000F2E6
0x14000f1aa  cmp     [rax+8], rsi
0x14000f1ae  jnz     loc_14000F336
0x14000f1b4  mov     rcx, [rax]
0x14000f1b7  cmp     [rcx+8], rax
0x14000f1bb  jnz     loc_14000F336
0x14000f1c1  mov     [rsi], rcx
0x14000f1c4  lea     rdi, [rax-28h]
0x14000f1c8  mov     [rcx+8], rsi
0x14000f1cc  mov     [rax], r14
0x14000f1cf  mov     [rax+8], r14
0x14000f1d3  mov     eax, [rdi+0C0h]
0x14000f1d9  test    al, 10h
0x14000f1db  jz      short loc_14000F19E
0x14000f1dd  mov     eax, [rdi+0C0h]
0x14000f1e3  and     eax, 0FFFFFFEFh
0x14000f1e6  mov     [rdi+0C0h], eax
0x14000f1ec  mov     eax, [rdi+0C0h]
0x14000f1f2  bt      eax, 8
0x14000f1f6  jb      short loc_14000F19E
0x14000f1f8  mov     eax, [rdi+0C0h]
0x14000f1fe  bt      eax, 9
0x14000f202  jb      loc_14000FD11
0x14000f208  lea     rax, [rdi+2A0h]
0x14000f20f  cmp     [rax], rax
0x14000f212  jz      loc_14000F81E
0x14000f218  cmp     dword ptr [rdi+314h], 0
0x14000f21f  jz      loc_14000F806
0x14000f225  mov     eax, [rdi+0C0h]
0x14000f22b  test    al, 20h
0x14000f22d  jnz     loc_14000F998
0x14000f233  mov     eax, [rdi+0C0h]
0x14000f239  test    al, al
0x14000f23b  js      loc_14000FD37
0x14000f241  mov     eax, [rdi+0C0h]
0x14000f247  test    al, 10h
0x14000f249  jnz     loc_14000FAB5
0x14000f24f  mov     eax, [rdi+0C0h]
0x14000f255  test    al, 40h
0x14000f257  jnz     loc_14000FD4F
0x14000f25d  mov     eax, [rdi+0C0h]
0x14000f263  test    al, 8
0x14000f265  jnz     loc_14000F978
0x14000f26b  mov     eax, [rdi+0C0h]
0x14000f271  test    al, 1
0x14000f273  jnz     loc_14000F19E
0x14000f279  mov     eax, [rdi+0C0h]
0x14000f27f  bt      eax, 8
0x14000f283  jb      loc_14000F19E
0x14000f289  mov     ecx, r14d
0x14000f28c  xor     eax, eax
0x14000f28e  lock cmpxchg [rdi+1BCh], ecx
0x14000f296  cmp     eax, 2
0x14000f299  jnz     short loc_14000F2CE
0x14000f29b  mov     rax, [rdi+60h]
0x14000f29f  lea     rdx, VidSchiResetContextQuantumAtISR
0x14000f2a6  mov     byte ptr [rbp+57h+PerformanceFrequency], 0
0x14000f2aa  mov     r8, rdi
0x14000f2ad  mov     rcx, [rax+18h]
0x14000f2b1  lea     rax, [rbp+57h+PerformanceFrequency]
0x14000f2b5  mov     [rsp+0C0h+var_A0], rax
0x14000f2ba  mov     r9d, [rcx+28h]
0x14000f2be  mov     rcx, [rcx+20h]
0x14000f2c2  call    cs:__imp_DpSynchronizeExecution
0x14000f2c9  nop     dword ptr [rax+rax+00h]
0x14000f2ce  mov     edx, 5
0x14000f2d3  mov     r8d, 5C73h
0x14000f2d9  mov     rcx, rdi
0x14000f2dc  call    VidSchiUpdateContextStatus
0x14000f2e1  jmp     loc_14000F19E
0x14000f2e6  lea     rcx, [rbx+0F18h]
0x14000f2ed  mov     rax, [rcx]
0x14000f2f0  cmp     rax, rcx
0x14000f2f3  jz      short loc_14000F340
0x14000f2f5  cmp     [rax+8], rcx
0x14000f2f9  jnz     short loc_14000F336
0x14000f2fb  mov     rdx, [rax]
0x14000f2fe  cmp     [rdx+8], rax
0x14000f302  jnz     short loc_14000F336
0x14000f304  mov     [rcx], rdx
0x14000f307  lea     r9, [rax+98h]
0x14000f30e  mov     [rdx+8], rcx
0x14000f312  cmp     qword ptr [r9], 0
0x14000f316  mov     [rax], r14
0x14000f319  mov     [rax+8], r14
0x14000f31d  jnz     short loc_14000F2ED
0x14000f31f  mov     r8, [rbx+128h]
0x14000f326  lea     rdx, [rbx+120h]
0x14000f32d  cmp     [r8], rdx
0x14000f330  jz      loc_14000F8EC
0x14000f336  mov     ecx, 3
0x14000f33b  int     29h; Win8: RtlFailFast(ecx)
0x14000f340  xor     eax, eax
0x14000f342  xorps   xmm0, xmm0
0x14000f345  mov     rsi, r14
0x14000f348  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x14000f34c  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x14000f350  cmp     [rbx+360h], eax
0x14000f356  jz      loc_14000F4E4
0x14000f35c  mov     rax, [rbx+110h]
0x14000f363  test    rax, rax
0x14000f366  jz      short loc_14000F376
0x14000f368  mov     eax, [rax+0C0h]
0x14000f36e  test    al, 1
0x14000f370  jnz     loc_14000F7FA
0x14000f376  lea     rdi, [rbx+2A8h]
0x14000f37d  xor     r8d, r8d
0x14000f380  mov     rdx, rdi
0x14000f383  lea     rcx, [rbx+248h]
0x14000f38a  call    cs:__imp_RtlCopyBitMapEx
0x14000f391  nop     dword ptr [rax+rax+00h]
0x14000f396  lea     rdx, [rbx+278h]
0x14000f39d  mov     rcx, rdi
0x14000f3a0  call    cs:__imp_RtlIntersectBitMapsEx
0x14000f3a7  nop     dword ptr [rax+rax+00h]
0x14000f3ac  mov     r8, [rdi]
0x14000f3af  xor     edx, edx
0x14000f3b1  mov     rcx, rdi
0x14000f3b4  call    cs:__imp_RtlAreBitsClearEx
0x14000f3bb  nop     dword ptr [rax+rax+00h]
0x14000f3c0  test    al, al
0x14000f3c2  jz      short loc_14000F3DD
0x14000f3c4  xor     r8d, r8d
0x14000f3c7  lea     rcx, [rbx+248h]
0x14000f3ce  mov     rdx, rdi
0x14000f3d1  call    cs:__imp_RtlCopyBitMapEx
0x14000f3d8  nop     dword ptr [rax+rax+00h]
0x14000f3dd  mov     r8d, [rbx+358h]
0x14000f3e4  mov     edx, 1
0x14000f3e9  inc     r8d
0x14000f3ec  mov     rcx, rdi
0x14000f3ef  call    cs:__imp_RtlFindSetBitsEx
0x14000f3f6  nop     dword ptr [rax+rax+00h]
0x14000f3fb  mov     rcx, rax
0x14000f3fe  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000f402  jz      loc_14000F990
0x14000f408  mov     rdi, [rbx+308h]
0x14000f40f  cmp     ecx, [rbx+350h]
0x14000f415  jnb     short loc_14000F41D
0x14000f417  mov     eax, ecx
0x14000f419  lea     rdi, [rdi+rax*8]
0x14000f41d  mov     rdi, [rdi]
0x14000f420  mov     [rbx+358h], ecx
0x14000f426  test    rdi, rdi
0x14000f429  jz      loc_14000F990
0x14000f42f  mov     eax, [rdi+76Ch]
0x14000f435  xor     r14d, r14d
0x14000f438  test    eax, eax
0x14000f43a  jz      short loc_14000F47C
0x14000f43c  mov     rcx, [rdi+18h]
0x14000f440  lea     rax, [rbp+57h+PerformanceFrequency]
0x14000f444  mov     byte ptr [rbp+57h+PerformanceFrequency], r14b
0x14000f448  lea     r8, [rbp+57h+var_50]
0x14000f44c  mov     [rbp+57h+var_38], r14
0x14000f450  lea     rdx, VidSchiUpdateNodeRunningTimeAtISR
0x14000f457  mov     qword ptr [rbp+57h+var_50], rdi
0x14000f45b  xorps   xmm0, xmm0
0x14000f45e  movdqu  xmmword ptr [rbp+57h+var_50+8], xmm0
0x14000f463  mov     r9d, [rcx+28h]
0x14000f467  mov     rcx, [rcx+20h]
0x14000f46b  mov     [rsp+0C0h+var_A0], rax
0x14000f470  call    cs:__imp_DpSynchronizeExecution
0x14000f477  nop     dword ptr [rax+rax+00h]
0x14000f47c  cmp     byte ptr [rdi+868h], 0
0x14000f483  mov     edx, [rdi+768h]
0x14000f489  jnz     loc_14000F919
0x14000f48f  mov     rcx, rdx; Set
0x14000f492  call    cs:__imp_RtlFindMostSignificantBit
0x14000f499  nop     dword ptr [rax+rax+00h]
0x14000f49e  movsx   edx, al; unsigned int
0x14000f4a1  xor     r8d, r8d; bool
0x14000f4a4  mov     rcx, rdi; struct _VIDSCH_NODE *
0x14000f4a7  call    ?VidSchiSelectContextFromThisPriority@@YAPEAU_VIDSCH_CONTEXT@@PEAU_VIDSCH_NODE@@K_N@Z; VidSchiSelectContextFromThisPriority(_VIDSCH_NODE *,ulong,bool)
0x14000f4ac  mov     rsi, rax
0x14000f4af  mov     eax, [rbx+0B58h]
0x14000f4b5  test    al, 8
0x14000f4b7  jnz     loc_14000FA40
0x14000f4bd  mov     [rsp+0C0h+var_88], r14
0x14000f4c2  mov     [rsp+0C0h+var_90], r14
0x14000f4c7  xor     r9d, r9d
0x14000f4ca  mov     [rsp+0C0h+var_98], r14
0x14000f4cf  mov     r8, rdi
0x14000f4d2  mov     rdx, rbx
0x14000f4d5  mov     [rsp+0C0h+var_A0], rsi
0x14000f4da  mov     ecx, 14h
0x14000f4df  call    VidSchiProfilePerformanceTick
0x14000f4e4  mov     [rsp+0C0h+var_88], r14
0x14000f4e9  xor     r9d, r9d
0x14000f4ec  mov     [rsp+0C0h+var_90], r14
0x14000f4f1  xor     r8d, r8d
0x14000f4f4  mov     [rsp+0C0h+var_98], r14
0x14000f4f9  mov     rdx, rbx
0x14000f4fc  mov     ecx, 2
0x14000f501  mov     [rsp+0C0h+var_A0], rsi
0x14000f506  call    VidSchiProfilePerformanceTick
0x14000f50b  test    rsi, rsi
0x14000f50e  jz      loc_14000F6FB
0x14000f514  mov     rcx, rsi
0x14000f517  call    VidSchiSwitchContextWithCheck
0x14000f51c  mov     r14d, eax
0x14000f51f  cmp     eax, 1
0x14000f522  jnz     loc_14000F7E9
0x14000f528  mov     rcx, [rsi+60h]
0x14000f52c  xor     eax, eax
0x14000f52e  mov     qword ptr [rbp+57h+var_50+10h], rax
0x14000f532  xor     r9d, r9d
0x14000f535  mov     eax, [rsi+0C0h]
0x14000f53b  xorps   xmm0, xmm0
0x14000f53e  mov     r13d, r9d
0x14000f541  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x14000f545  mov     rdi, [rcx+18h]
0x14000f549  test    r14b, al
0x14000f54c  jz      loc_14000F63A
0x14000f552  mov     r13, [rsi+290h]
0x14000f559  test    r13, r13
0x14000f55c  jz      loc_14000F63A
0x14000f562  mov     eax, 0FFFFFFFFh
0x14000f567  add     [rsi+314h], eax
0x14000f56d  add     [rcx+0BC8h], eax
0x14000f573  add     [rdi+360h], eax
0x14000f579  lea     rax, [rsi+2A0h]
  ... truncated ...
```
