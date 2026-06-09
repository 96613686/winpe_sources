# PresentWorkerThread(CDDPDEV *)

- ea: `0x140011510`
- end: `0x1400129c3`
- name: `?PresentWorkerThread@@YAXPEAUCDDPDEV@@@Z`
- size: `5299`
- prototype: `void __fastcall(unsigned int *StartContext)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, installer_update`

## callees

- `0x14000e420`
- `0x140010850`
- `0x140011510`
- `0x140012b60`
- `0x14001b6e8`
- `0x140020960`
- `0x140021d5c`
- `0x1400224a0`
- `0x140022c28`
- `0x140027b1c`
- `0x14002a758`
- `0x14002ad30`
- `0x14002bf58`
- `0x14002d088`
- `0x14002d228`
- `0x1400371f0`
- `0x1400372d0`
- `0x140037640`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x140011aed`
- `ntoskrnl!KeCancelTimer` at `0x140011aed`
- `ntoskrnl!KeClearEvent` at `0x140011e2c`
- `ntoskrnl!KeClearEvent` at `0x140011e50`
- `ntoskrnl!KeClearEvent` at `0x140011e6a`
- `ntoskrnl!KeClearEvent` at `0x140012035`
- `ntoskrnl!KeClearEvent` at `0x140012045`
- `ntoskrnl!KeClearEvent` at `0x140011e2c`
- `ntoskrnl!KeClearEvent` at `0x140011e50`
- `ntoskrnl!KeClearEvent` at `0x140011e6a`
- `ntoskrnl!KeClearEvent` at `0x140012035`
- `ntoskrnl!KeClearEvent` at `0x140012045`
- `ntoskrnl!KeReadStateEvent` at `0x140011819`
- `ntoskrnl!KeReadStateEvent` at `0x14001183b`
- `ntoskrnl!KeReadStateEvent` at `0x140011862`
- `ntoskrnl!KeReadStateEvent` at `0x140011819`
- `ntoskrnl!KeReadStateEvent` at `0x14001183b`
- `ntoskrnl!KeReadStateEvent` at `0x140011862`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400117d9`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140011d5f`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400117d9`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140011d5f`
- `ntoskrnl!KeSetTimer` at `0x140011d18`
- `ntoskrnl!KeSetTimer` at `0x140011d18`
- `ntoskrnl!KeInitializeTimer` at `0x1400116d1`
- `ntoskrnl!KeInitializeTimer` at `0x1400116d1`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x140011628`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x140011628`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1400115cc`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1400115cc`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400124aa`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400124aa`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14001244a`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14001244a`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x1400125c2`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x1400125c2`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140012648`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140012648`
- `ntoskrnl!KeGetCurrentIrql` at `0x140011546`
- `ntoskrnl!KeGetCurrentIrql` at `0x140011546`
- `ntoskrnl!KeSetEvent` at `0x14001164a`
- `ntoskrnl!KeSetEvent` at `0x140011a32`
- `ntoskrnl!KeSetEvent` at `0x14001164a`
- `ntoskrnl!KeSetEvent` at `0x140011a32`
- `watchdog!WdLogSingleEntry5` at `0x140011c1e`
- `watchdog!WdLogSingleEntry5` at `0x1400122d4`
- `watchdog!WdLogSingleEntry5` at `0x1400127be`
- `watchdog!WdLogSingleEntry5` at `0x140011c1e`
- `watchdog!WdLogSingleEntry5` at `0x1400122d4`
- `watchdog!WdLogSingleEntry5` at `0x1400127be`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x140011c34`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x140011cac`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x140011c34`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x140011cac`
- `watchdog!WdLogSingleEntry1` at `0x140011c96`
- `watchdog!WdLogSingleEntry1` at `0x140011f17`
- `watchdog!WdLogSingleEntry1` at `0x140011c96`
- `watchdog!WdLogSingleEntry1` at `0x140011f17`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140011b75`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140011bc1`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140011d8e`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140011de1`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x1400120c7`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14001212f`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140012244`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140012380`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140012679`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14001274e`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140012867`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x1400128fb`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14001297d`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140011b75`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140011bc1`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140011d8e`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140011de1`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x1400120c7`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14001212f`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140012244`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140012380`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140012679`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14001274e`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140012867`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x1400128fb`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14001297d`
- `watchdog!WdLogSingleEntry0` at `0x140011b5e`
- `watchdog!WdLogSingleEntry0` at `0x140011baa`
- `watchdog!WdLogSingleEntry0` at `0x140011d78`
- `watchdog!WdLogSingleEntry0` at `0x140011dcb`
- `watchdog!WdLogSingleEntry0` at `0x1400120ae`
- `watchdog!WdLogSingleEntry0` at `0x140012116`
- `watchdog!WdLogSingleEntry0` at `0x14001222b`
- `watchdog!WdLogSingleEntry0` at `0x140012367`
- `watchdog!WdLogSingleEntry0` at `0x140012663`
- `watchdog!WdLogSingleEntry0` at `0x140012738`
- `watchdog!WdLogSingleEntry0` at `0x140012851`
- `watchdog!WdLogSingleEntry0` at `0x1400128e4`
- `watchdog!WdLogSingleEntry0` at `0x140012966`
- `watchdog!WdLogSingleEntry0` at `0x140011b5e`
- `watchdog!WdLogSingleEntry0` at `0x140011baa`
- `watchdog!WdLogSingleEntry0` at `0x140011d78`
- `watchdog!WdLogSingleEntry0` at `0x140011dcb`
- `watchdog!WdLogSingleEntry0` at `0x1400120ae`
- `watchdog!WdLogSingleEntry0` at `0x140012116`
- `watchdog!WdLogSingleEntry0` at `0x14001222b`
- `watchdog!WdLogSingleEntry0` at `0x140012367`
- `watchdog!WdLogSingleEntry0` at `0x140012663`
- `watchdog!WdLogSingleEntry0` at `0x140012738`
- `watchdog!WdLogSingleEntry0` at `0x140012851`
- `watchdog!WdLogSingleEntry0` at `0x1400128e4`
- `watchdog!WdLogSingleEntry0` at `0x140012966`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140011f30`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x1400122ed`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x1400127d7`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140011f30`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x1400122ed`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x1400127d7`
- `WIN32K!EngIsSemaphoreOwned` at `0x14001218d`
- `WIN32K!EngIsSemaphoreOwned` at `0x14001228e`
- `WIN32K!EngIsSemaphoreOwned` at `0x14001218d`
- `WIN32K!EngIsSemaphoreOwned` at `0x14001228e`
- `WIN32K!CddEngSetRectRgn` at `0x140012627`
- `WIN32K!CddEngSetRectRgn` at `0x140012627`
- `WIN32K!EngFreeMem` at `0x1400126dd`
- `WIN32K!EngFreeMem` at `0x1400126dd`

## string_xrefs

- `0x140011ad6`: `PresentWorkerThread: KeWait* returned STATUS_WAIT_0 but pClientThread is NULL\n`
- `0x14001219d`: `PresentWorkerThread: CDDDEVLOCK is not held\n`
- `0x14001229e`: `PresentWorkerThread: CDDDEVLOCK is not held\n`

## pseudocode

```c
void __fastcall PresentWorkerThread(unsigned int *StartContext)
{
  __int64 v2; // r12
  int v3; // r13d
  unsigned __int64 v4; // rbx
  unsigned __int64 v5; // r14
  int v6; // r15d
  unsigned int v7; // eax
  __int64 v8; // r10
  int v9; // eax
  int v10; // edx
  char v11; // al
  unsigned int v12; // r14d
  unsigned int v13; // r14d
  _QWORD *v14; // rax
  _QWORD *v15; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // rax
  _QWORD *v18; // rax
  _QWORD *v19; // rax
  int v20; // eax
  _QWORD *v21; // rax
  int v22; // eax
  struct _KEVENT *v23; // rcx
  __int64 v24; // rcx
  int v25; // eax
  unsigned __int64 v26; // rcx
  __int64 v27; // rdx
  _QWORD *v28; // rax
  _QWORD *v29; // rax
  __int64 (__fastcall *v30)(__int64, __int64, _BYTE *); // rax
  __int64 v31; // rdx
  __int64 v32; // rcx
  int v33; // eax
  char v34; // al
  __int64 v35; // r9
  _QWORD *v36; // rax
  _QWORD *v37; // rax
  __int64 v38; // rcx
  int v39; // eax
  unsigned __int64 v40; // rcx
  __int64 v41; // rdx
  _QWORD *v42; // rax
  unsigned int *v43; // rcx
  _DWORD *v44; // rax
  void *v45; // r14
  unsigned int v46; // eax
  struct _LOOKASIDE_LIST_EX *v47; // rcx
  CDDSYNCOBJECT *v48; // rcx
  __int64 v49; // rax
  __int64 v50; // rcx
  _QWORD *v51; // rax
  void *v52; // rcx
  bool v53; // zf
  _QWORD *v54; // rax
  _QWORD *v55; // rax
  unsigned __int64 v56; // rax
  __int64 v57; // rcx
  _QWORD *v58; // rax
  _QWORD *v59; // rax
  _QWORD *v60; // rax
  int WaitMode; // [rsp+20h] [rbp-E0h]
  BOOLEAN Alertable[8]; // [rsp+28h] [rbp-D8h]
  int Timeout; // [rsp+30h] [rbp-D0h]
  int v64; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v65[4]; // [rsp+54h] [rbp-ACh] BYREF
  unsigned __int64 v66; // [rsp+58h] [rbp-A8h]
  _KTIMER Timer; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v68[4]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v69[24]; // [rsp+C0h] [rbp-40h]
  _DWORD SystemInformation[16]; // [rsp+E0h] [rbp-20h] BYREF
  PVOID Object; // [rsp+120h] [rbp+20h] BYREF
  PRKEVENT Event; // [rsp+128h] [rbp+28h]
  PRKEVENT v73; // [rsp+130h] [rbp+30h]
  _KTIMER *p_Timer; // [rsp+138h] [rbp+38h]
  struct _KWAIT_BLOCK WaitBlockArray; // [rsp+140h] [rbp+40h] BYREF

  v2 = 0;
  if ( KeGetCurrentIrql() )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 3868;
    v14 = (_QWORD *)WdLogNewEntry5_WdAssertion();
    v14[3] = gCddImageInfo;
    v14[4] = (unsigned int)dword_14003E570;
    v14[5] = 215857758;
    WdLogGlobalForLineNumber = 3868;
  }
  if ( StartContext[630] )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 3871;
    v15 = (_QWORD *)WdLogNewEntry5_WdAssertion();
    v15[3] = gCddImageInfo;
    v15[4] = (unsigned int)dword_14003E570;
    v15[5] = 215857758;
    WdLogGlobalForLineNumber = 3871;
  }
  *((_QWORD *)StartContext + 321) = KeGetCurrentThread();
  v3 = *((_BYTE *)StartContext + 1120) == 0 ? 8 : 0;
  StartContext[686] = v3 | StartContext[686] & 0xFFFFFFF7;
  memset(SystemInformation, 0, sizeof(SystemInformation));
  InitDisplayMode((struct CDDPDEV *)StartContext);
  v4 = 156250;
  if ( ZwQuerySystemInformation(SystemBasicInformation, SystemInformation, 0x40u, 0) < 0 )
  {
    WdLogSingleEntry5(3, StartContext, StartContext[196], StartContext[199], StartContext[200], (int)StartContext[258]);
    WdLogGlobalForLineNumber = 3888;
    v16 = (_QWORD *)WdLogNewEntry5_WdWarning();
    v16[3] = gCddImageInfo;
    v16[4] = (unsigned int)dword_14003E570;
    v16[5] = 215857758;
    WdLogGlobalForLineNumber = 3888;
    SystemInformation[1] = 156250;
  }
  if ( *((_QWORD *)StartContext + 128) != 0xFFFFFFFEFFFFFFFEuLL )
    v4 = 10000000 * (unsigned __int64)StartContext[257] / StartContext[256];
  *((_QWORD *)StartContext + 334) = -(__int64)v4;
  KeSetActualBasePriorityThread(KeGetCurrentThread(), 14);
  StartContext[1370] = 1;
  KeSetEvent(*((PRKEVENT *)StartContext + 329), 0, 0);
  *(_QWORD *)&v69[16] = 0;
  v68[1] = CddAddD3DDirtyRgn;
  v68[0] = StartContext;
  v68[2] = CddNotifyExclusiveGDIOwner;
  p_Timer = 0;
  v68[3] = CddUpdatePresentRects;
  Object = (PVOID)*((_QWORD *)StartContext + 327);
  Event = (PRKEVENT)*((_QWORD *)StartContext + 326);
  v73 = (PRKEVENT)*((_QWORD *)StartContext + 328);
  *((_QWORD *)StartContext + 908) = &v64;
  *(_OWORD *)v69 = 0;
  v64 = 0;
  memset(&Timer, 0, sizeof(Timer));
  KeInitializeTimer(&Timer);
  v5 = v4 + MEMORY[0xFFFFF78000000008];
  v66 = v4 + MEMORY[0xFFFFF78000000008];
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        *((_BYTE *)StartContext + 2749) = 0;
        v6 = 0;
        if ( (unsigned __int8)(BYTE2(v64) | HIBYTE(v64) | BYTE1(v64)) | (unsigned __int8)v64 )
          goto LABEL_36;
        if ( *((_BYTE *)StartContext + 2716) && *((_BYTE *)StartContext + 2715)
          || *((_BYTE *)StartContext + 2752)
          || (v7 = StartContext[686], (v7 & 0x10) != 0)
          || *((_BYTE *)StartContext + 2719) )
        {
          p_Timer = (_KTIMER *)*((_QWORD *)StartContext + 330);
          v6 = KeWaitForMultipleObjects(4u, &Object, WaitAny, Executive, 0, 0, 0, &WaitBlockArray);
          if ( v6 == 3 )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 4056;
            v18 = (_QWORD *)WdLogNewEntry5_WdAssertion();
            v18[3] = gCddImageInfo;
            v18[4] = (unsigned int)dword_14003E570;
            v18[5] = 215857758;
            WdLogGlobalForLineNumber = 4056;
          }
          *((_BYTE *)StartContext + 2749) = 1;
          goto LABEL_24;
        }
        if ( (v7 & 8) != 0 )
        {
          v8 = *((_QWORD *)StartContext + 311);
          if ( v8 )
          {
            if ( StartContext[630] )
            {
              v9 = (*((__int64 (__fastcall **)(__int64, _QWORD, __int64, PVOID *, _QWORD))StartContext + 24))(
                     v8,
                     StartContext[196],
                     3,
                     &Object,
                     *((_QWORD *)StartContext + 452));
              v6 = v9;
              if ( v9 < 0 )
              {
                WdLogSingleEntry1(3, v9);
                WdLogGlobalForLineNumber = 4002;
                v17 = (_QWORD *)WdLogNewEntry5_WdWarning();
                v17[3] = gCddImageInfo;
                v17[4] = (unsigned int)dword_14003E570;
                v17[5] = 215857758;
                WdLogGlobalForLineNumber = 4002;
                if ( v6 == -1073740759 )
                  goto LABEL_90;
              }
              else if ( (unsigned int)v9 <= 3 )
              {
                goto LABEL_26;
              }
              if ( v6 == 258 )
LABEL_90:
                StartContext[686] &= ~8u;
            }
          }
        }
        KeSetTimer(&Timer, (LARGE_INTEGER)((MEMORY[0xFFFFF78000000008] - v5) % v4 - v4), 0);
        if ( p_Timer != &Timer )
          p_Timer = &Timer;
        v6 = KeWaitForMultipleObjects(4u, &Object, WaitAny, Executive, 0, 0, 0, &WaitBlockArray);
LABEL_24:
        if ( (unsigned int)v6 >= 4 )
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 4060;
          v19 = (_QWORD *)WdLogNewEntry5_WdAssertion();
          v19[3] = gCddImageInfo;
          v19[4] = (unsigned int)dword_14003E570;
          v19[5] = 215857758;
          WdLogGlobalForLineNumber = 4060;
        }
LABEL_26:
        if ( v6 == 1 )
        {
          BYTE2(v64) = 1;
        }
        else
        {
          if ( KeReadStateEvent(Event) )
          {
            BYTE2(v64) = 1;
            KeClearEvent(Event);
          }
          if ( v6 == 2 )
          {
            LOBYTE(v64) = 1;
            goto LABEL_63;
          }
        }
        if ( KeReadStateEvent(v73) )
        {
          LOBYTE(v64) = 1;
          KeClearEvent(v73);
        }
        if ( v6 == 3 )
        {
          HIBYTE(v64) = 1;
          goto LABEL_34;
        }
LABEL_63:
        if ( !*((_BYTE *)StartContext + 2716) )
          StartContext[686] ^= ((unsigned __int8)v3 ^ (unsigned __int8)StartContext[686]) & 8;
        if ( !v6 )
        {
          BYTE1(v64) = 1;
          goto LABEL_36;
        }
LABEL_34:
        if ( KeReadStateEvent((PRKEVENT)Object) )
        {
          BYTE1(v64) = 1;
          KeClearEvent((PRKEVENT)Object);
        }
LABEL_36:
        *((_BYTE *)StartContext + 2754) = 0;
        if ( !HIBYTE(v64) )
          break;
        v10 = ++StartContext[670] % StartContext[667];
        HIBYTE(v64) = 0;
        if ( !v10 )
        {
          if ( *((_BYTE *)StartContext + 2712) && *((_BYTE *)StartContext + 2716) || *((_BYTE *)StartContext + 2753) )
          {
            StartContext[671] &= ~StartContext[672];
            v11 = *((_BYTE *)StartContext + 2753);
            if ( v11 )
              BYTE1(v64) = 0;
            v12 = v11 != 0 ? 0x10 : 0;
            if ( *((_BYTE *)StartContext + 2712) )
              LOBYTE(v64) = 1;
            goto LABEL_47;
          }
          if ( (++StartContext[671] & StartContext[672]) == 0 )
            *((_BYTE *)StartContext + 2752) = 1;
        }
      }
      if ( !BYTE1(v64) )
        break;
      BYTE1(v64) = 0;
      if ( !*((_BYTE *)StartContext + 2749) || !*((_BYTE *)StartContext + 2753) )
      {
        v12 = 16;
        goto LABEL_47;
      }
      *((_BYTE *)StartContext + 2749) = 0;
      *((_BYTE *)StartContext + 2752) = 0;
    }
    if ( (_BYTE)v64 )
    {
      (*((void (**)(void))StartContext + 63))();
      LOBYTE(v64) = 0;
      v12 = 0;
    }
    else
    {
      v12 = 0;
      if ( BYTE2(v64) )
      {
        v12 = StartContext[900];
        StartContext[902] = 0;
        BYTE2(v64) = 0;
        if ( !*((_QWORD *)StartContext + 322) && (v12 & 0xFFFFFFEF) != 0 )
        {
          DbgLog("PresentWorkerThread: KeWait* returned STATUS_WAIT_0 but pClientThread is NULL\n");
          __debugbreak();
        }
      }
    }
LABEL_47:
    if ( StartContext[1370] != 1 )
      break;
    switch ( v12 )
    {
      case 0xBu:
        if ( (StartContext[686] & 0x100) != 0 )
        {
          v20 = (*((__int64 (__fastcall **)(char *, _QWORD, _QWORD))StartContext + 19))(
                  (char *)StartContext + 3968,
                  StartContext[196],
                  *((_QWORD *)StartContext + 452));
          StartContext[902] = v20;
          if ( v20 < 0 )
          {
            WdLogSingleEntry1(4, v20);
            WdLogGlobalForLineNumber = 4234;
            v21 = (_QWORD *)WdLogNewEntry5_WdEvent();
            v21[3] = gCddImageInfo;
            v21[4] = (unsigned int)dword_14003E570;
            v21[5] = 215857758;
            WdLogGlobalForLineNumber = 4234;
            CDDPDEV::CheckDeviceRemoved((CDDPDEV *)StartContext, StartContext[902]);
          }
        }
LABEL_69:
        v5 = v66;
        if ( !*((_BYTE *)StartContext + 2754) )
        {
          StartContext[900] = 0;
          KeSetEvent(*((PRKEVENT *)StartContext + 329), 0, 0);
        }
        break;
      case 0x11u:
        if ( (StartContext[686] & 0x100) != 0 )
          StartContext[926] = CDDPDEV::OpenResource(
                                (CDDPDEV *)StartContext,
                                StartContext[912],
                                *((void **)StartContext + 457),
                                StartContext[916],
                                *((struct _EPROCESS **)StartContext + 459),
                                *((unsigned int **)StartContext + 460),
                                *((void ***)StartContext + 461),
                                *((unsigned __int64 **)StartContext + 462),
                                *((void ***)StartContext + 464));
        goto LABEL_69;
      case 0xFu:
        if ( (StartContext[686] & 0x100) != 0 )
        {
          CDDPDEV::FlushGdiOutput((CDDPDEV *)StartContext, 0);
          v22 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))StartContext + 36))(
                  StartContext[631],
                  *((_QWORD *)StartContext + 456),
                  *((_QWORD *)StartContext + 452));
        }
        else
        {
          v22 = -1073741823;
        }
        goto LABEL_108;
      case 0xDu:
        v13 = StartContext[912];
        CDDPDEV::FlushGdiOutput((CDDPDEV *)StartContext, v13);
        if ( (v13 & 1) != 0 )
        {
          v23 = (struct _KEVENT *)Object;
          *((_BYTE *)StartContext + 2752) = 1;
          BYTE1(v64) = 0;
          KeClearEvent(v23);
          KeClearEvent(v73);
          if ( (StartContext[686] & 0x400) != 0 )
          {
            v24 = StartContext[630];
            if ( (_DWORD)v24 )
            {
              if ( *((_BYTE *)StartContext + 2716) )
              {
                v25 = (*((__int64 (__fastcall **)(__int64, _QWORD, _QWORD))StartContext + 15))(
                        v24,
                        0,
                        StartContext[196]);
                v26 = (unsigned int)(v25 + 1071774976);
                if ( (unsigned int)v26 > 0x39 || (v27 = 0x220000000000001LL, !_bittest64(&v27, v26)) )
                {
                  if ( v25 < 0 )
                  {
                    WdLogSingleEntry0(1);
                    WdLogGlobalForLineNumber = 4307;
                    v28 = (_QWORD *)WdLogNewEntry5_WdAssertion();
                    v28[3] = gCddImageInfo;
                    v28[4] = (unsigned int)dword_14003E570;
                    v28[5] = 215857758;
                    WdLogGlobalForLineNumber = 4307;
                  }
                }
              }
              CDDPDEV::DestroyDevice(StartContext, 13);
              if ( StartContext[630] )
              {
                WdLogSingleEntry0(1);
                WdLogGlobalForLineNumber = 4311;
                v29 = (_QWORD *)WdLogNewEntry5_WdAssertion();
                v29[3] = gCddImageInfo;
                v29[4] = (unsigned int)dword_14003E570;
                v29[5] = 215857758;
                WdLogGlobalForLineNumber = 4311;
              }
            }
          }
        }
        if ( (v13 & 2) == 0 )
          goto LABEL_69;
LABEL_119:
        v5 = v66;
        break;
      case 0x10u:
        *((_BYTE *)StartContext + 2750) = 1;
        CDDPDEV::FlushGdiOutput((CDDPDEV *)StartContext, 0);
        *((_BYTE *)StartContext + 2750) = 0;
        goto LABEL_119;
      case 7u:
        if ( !EngIsSemaphoreOwned(*((HSEMAPHORE *)StartContext + 365)) )
        {
          DbgLog("PresentWorkerThread: CDDDEVLOCK is not held\n");
          __debugbreak();
        }
        v30 = (__int64 (__fastcall *)(__int64, __int64, _BYTE *))*((_QWORD *)StartContext + 70);
        v31 = StartContext[196];
        v32 = *((_QWORD *)StartContext + 311);
        *(_OWORD *)&v69[8] = *((_OWORD *)StartContext + 162);
        v65[0] = 0;
        v33 = v30(v32, v31, v65);
        if ( v33 == -1073741130 )
        {
          v65[0] = 0;
          goto LABEL_124;
        }
        if ( v33 < 0 )
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 4355;
          v36 = (_QWORD *)WdLogNewEntry5_WdAssertion();
          v36[3] = gCddImageInfo;
          v36[4] = (unsigned int)dword_14003E570;
          v36[5] = 215857758;
          WdLogGlobalForLineNumber = 4355;
        }
        if ( v65[0] )
          v34 = 0;
        else
LABEL_124:
          v34 = 1;
        StartContext[686] &= ~8u;
        v35 = StartContext[912];
        *((_BYTE *)StartContext + 2716) = v34;
        *((_BYTE *)StartContext + 2715) = 0;
        v22 = CreateAndEnableDevice(StartContext, StartContext + 262, v68, v35, 7);
LABEL_108:
        StartContext[902] = v22;
        goto LABEL_69;
      case 6u:
        if ( !EngIsSemaphoreOwned(*((HSEMAPHORE *)StartContext + 365)) )
        {
          DbgLog("PresentWorkerThread: CDDDEVLOCK is not held\n");
          __debugbreak();
        }
        WdLogSingleEntry5(
          4,
          StartContext,
          StartContext[196],
          *((_QWORD *)StartContext + 1),
          StartContext[199],
          StartContext[200]);
        WdLogGlobalForLineNumber = 4372;
        v37 = (_QWORD *)WdLogNewEntry5_WdEvent();
        v37[3] = gCddImageInfo;
        v37[4] = (unsigned int)dword_14003E570;
        v37[5] = 215857758;
        WdLogGlobalForLineNumber = 4372;
        v38 = StartContext[630];
        if ( (_DWORD)v38 )
        {
          v39 = (*((__int64 (__fastcall **)(__int64, _QWORD, _QWORD))StartContext + 15))(
                  v38,
                  StartContext[677],
                  StartContext[196]);
          v40 = (unsigned int)(v39 + 1071774976);
          if ( (unsigned int)v40 > 0x39 || (v41 = 0x220000000000001LL, !_bittest64(&v41, v40)) )
          {
            if ( v39 < 0 )
            {
              WdLogSingleEntry0(1);
              WdLogGlobalForLineNumber = 4386;
              v42 = (_QWORD *)WdLogNewEntry5_WdAssertion();
              v42[3] = gCddImageInfo;
              v42[4] = (unsigned int)dword_14003E570;
              v42[5] = 215857758;
              WdLogGlobalForLineNumber = 4386;
            }
          }
          if ( (StartContext[686] & 0x400) != 0 )
          {
            CDDPDEV::FlushGdiOutput((CDDPDEV *)StartContext, 0);
            v43 = StartContext;
            goto LABEL_139;
          }
          if ( !StartContext[677] )
          {
            v43 = StartContext;
            if ( StartContext[1807] )
              CDDPDEV::FlushGdiOutput((CDDPDEV *)StartContext, 0);
            else
LABEL_139:
              CDDPDEV::DestroyDevice(v43, 6);
          }
        }
        *(_WORD *)((char *)StartContext + 2715) = 0;
        goto LABEL_69;
      case 0x13u:
        LOBYTE(Timeout) = 1;
        *(_DWORD *)Alertable = 16;
        v22 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD *, _QWORD, char *, BOOLEAN *, int))StartContext + 14))(
                StartContext[630],
                StartContext[677],
                v68,
                StartContext[196],
                (char *)StartContext + 1048,
                *(BOOLEAN **)Alertable,
                Timeout);
        goto LABEL_108;
      case 0x14u:
        CDDPDEV::FlushGdiOutput((CDDPDEV *)StartContext, 0);
        v44 = ExAllocateFromLookasideListEx(*((PLOOKASIDE_LIST_EX *)StartContext + 97));
        v45 = v44;
        if ( v44 )
        {
          *v44 = 8;
          *((_QWORD *)v44 + 2) = *((_QWORD *)StartContext + 456);
          v46 = (*((__int64 (__fastcall **)(_QWORD, _DWORD *, _QWORD))StartContext + 36))(
                  StartContext[631],
                  v44,
                  *((_QWORD *)StartContext + 452));
          v47 = (struct _LOOKASIDE_LIST_EX *)*((_QWORD *)StartContext + 97);
          StartContext[902] = v46;
          ExFreeToLookasideListEx(v47, v45);
        }
        else
        {
          StartContext[902] = -1073741801;
        }
        goto LABEL_69;
      case 4u:
        v22 = SetPalette((struct CDDPDEV *)StartContext);
        goto LABEL_108;
      case 8u:
        (*((void (__fastcall **)(_QWORD, _QWORD, char *))StartContext + 23))(
          *((_QWORD *)StartContext + 311),
          StartContext[196],
          (char *)StartContext + 788);
        goto LABEL_69;
      case 0x12u:
        v48 = (CDDSYNCOBJECT *)*((_QWORD *)StartContext + 457);
        if ( StartContext[912] )
          v22 = CDDSYNCOBJECT::IssueSignalForGdi(v48);
        else
          v22 = CDDSYNCOBJECT::IssueWaitForGdi(v48);
        goto LABEL_108;
      case 0xCu:
        TryCreateDevice(StartContext, StartContext + 262, v68, 1, 12);
        goto LABEL_69;
      case 0x15u:
        (*((void (__fastcall **)(_QWORD, _QWORD))StartContext + 65))(0, StartContext[630]);
        goto LABEL_69;
      default:
        if ( !*((_BYTE *)StartContext + 2716) || *((_BYTE *)StartContext + 2715) || *((_BYTE *)StartContext + 2720) )
        {
LABEL_83:
          v53 = v12 == 0;
          v5 = v66;
          if ( !v53 )
            goto LABEL_69;
        }
        else
        {
          if ( v12 > 3 && v12 != 9 )
            goto LABEL_69;
          if ( (StartContext[686] & 0x400) != 0 || !StartContext[630] )
          {
            TryCreateDevice(StartContext, StartContext + 262, v68, 0, v12);
            if ( !StartContext[630] )
              goto LABEL_83;
          }
          if ( v12 == 3 )
          {
            v6 = CddPresentColorFill((struct CDDPDEV *)StartContext);
          }
          else
          {
            ExEnterCriticalRegionAndAcquireFastMutexUnsafe(*((_QWORD *)StartContext + 360));
            if ( v12 == 1 )
            {
              v2 = *((_QWORD *)StartContext + 352);
              *((_QWORD *)StartContext + 352) = *((_QWORD *)StartContext + 351);
              *((_QWORD *)StartContext + 351) = v2;
            }
            else if ( *((_BYTE *)StartContext + 2712) )
            {
              v49 = *((_QWORD *)StartContext + 358);
              v50 = *((_QWORD *)StartContext + 355);
              *((_QWORD *)StartContext + 358) = v50;
              *((_QWORD *)StartContext + 355) = v49;
              CddEngSetRectRgn(v50, 0, 0, 0, 0);
              v2 = *((_QWORD *)StartContext + 355);
              *((_BYTE *)StartContext + 2712) = 0;
            }
            ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(*((_QWORD *)StartContext + 360));
            if ( *((_QWORD *)StartContext + 341) )
            {
              WdLogSingleEntry0(1);
              WdLogGlobalForLineNumber = 4535;
              v51 = (_QWORD *)WdLogNewEntry5_WdAssertion();
              v51[3] = gCddImageInfo;
              v51[4] = (unsigned int)dword_14003E570;
              v51[5] = 215857758;
              WdLogGlobalForLineNumber = 4535;
            }
            if ( (*((unsigned int (**)(void))StartContext + 63))() != 3 )
              v6 = CddPresentBlt((__int64)StartContext, v2, v12);
            v52 = (void *)*((_QWORD *)StartContext + 341);
            v2 = 0;
            if ( v52 )
            {
              EngFreeMem(v52);
              *((_QWORD *)StartContext + 341) = 0;
            }
          }
          if ( v6 == -1073741130 )
            goto LABEL_179;
          v53 = v6 == -1071775482;
          if ( v6 == -1071775482 )
            goto LABEL_180;
          if ( v6 == -1071775232 )
          {
LABEL_179:
            v53 = v6 == -1071775482;
LABEL_180:
            *((_BYTE *)StartContext + 2715) = v53;
            WdLogSingleEntry5(4, v6, StartContext, StartContext[196], StartContext[199], StartContext[200]);
            WdLogGlobalForLineNumber = 4567;
            v55 = (_QWORD *)WdLogNewEntry5_WdEvent();
            v55[3] = gCddImageInfo;
            v55[4] = (unsigned int)dword_14003E570;
            v55[5] = 215857758;
            WdLogGlobalForLineNumber = 4567;
            v6 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))StartContext + 15))(
                   StartContext[630],
                   *((_BYTE *)StartContext + 2715) != 0 ? 3 : 0,
                   StartContext[196]);
            v56 = (unsigned int)(v6 + 1071774976);
            if ( (unsigned int)v56 > 0x39 || (v57 = 0x220000000000001LL, !_bittest64(&v57, v56)) )
            {
              if ( v6 < 0 )
              {
                WdLogSingleEntry0(1);
                WdLogGlobalForLineNumber = 4579;
                v58 = (_QWORD *)WdLogNewEntry5_WdAssertion();
                v58[3] = gCddImageInfo;
                v58[4] = (unsigned int)dword_14003E570;
                v58[5] = 215857758;
                WdLogGlobalForLineNumber = 4579;
              }
            }
            if ( !*((_BYTE *)StartContext + 2715) )
            {
              CDDPDEV::CheckDeviceRemoved((CDDPDEV *)StartContext, v6);
              CDDPDEV::DestroyDevice(StartContext, v12);
            }
            goto LABEL_186;
          }
          if ( (int)(v6 + 0x80000000) >= 0 && v6 != -1073741801 )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 4591;
            v54 = (_QWORD *)WdLogNewEntry5_WdAssertion();
            v54[3] = gCddImageInfo;
            v54[4] = (unsigned int)dword_14003E570;
            v54[5] = 215857758;
            WdLogGlobalForLineNumber = 4591;
          }
LABEL_186:
          v53 = v12 == 0;
          v5 = v66;
          if ( !v53 )
          {
            StartContext[902] = v6;
            goto LABEL_69;
          }
        }
        break;
    }
  }
  KeCancelTimer(&Timer);
  if ( StartContext[630] )
  {
    if ( (int)CDDPDEV::DestroyResidencyState((CDDPDEV *)StartContext) < 0 )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 4627;
      v59 = (_QWORD *)WdLogNewEntry5_WdAssertion();
      v59[3] = gCddImageInfo;
      v59[4] = (unsigned int)dword_14003E570;
      v59[5] = 215857758;
      WdLogGlobalForLineNumber = 4627;
    }
    LOBYTE(WaitMode) = (StartContext[686] & 0x400) != 0;
    if ( (*((int (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, int))StartContext + 12))(
           StartContext[630],
           StartContext[631],
           StartContext[632],
           *((_QWORD *)StartContext + 311),
           WaitMode) < 0 )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 4632;
      v60 = (_QWORD *)WdLogNewEntry5_WdAssertion();
      v60[3] = gCddImageInfo;
      v60[4] = (unsigned int)dword_14003E570;
      v60[5] = 215857758;
      WdLogGlobalForLineNumber = 4632;
    }
    *((_QWORD *)StartContext + 315) = 0;
    StartContext[632] = 0;
  }
  (*((void (__fastcall **)(_QWORD))StartContext + 25))(*((_QWORD *)StartContext + 329));
}

```

## disassembly

```asm
0x140011510  mov     [rsp-8+arg_8], rbx
0x140011515  mov     [rsp-8+arg_10], rsi
0x14001151a  push    rbp
0x14001151b  push    r12
0x14001151d  push    r13
0x14001151f  push    r14
0x140011521  push    r15
0x140011523  lea     rbp, [rsp-110h]
0x14001152b  sub     rsp, 210h
0x140011532  mov     rax, cs:__security_cookie
0x140011539  xor     rax, rsp
0x14001153c  mov     [rbp+130h+var_30], rax
0x140011543  mov     rsi, rcx
0x140011546  call    cs:__imp_KeGetCurrentIrql
0x14001154d  nop     dword ptr [rax+rax+00h]
0x140011552  xor     r12d, r12d
0x140011555  mov     r15d, 0CDDBA5Eh
0x14001155b  test    al, al
0x14001155d  jnz     loc_140011B59
0x140011563  cmp     [rsi+9D8h], r12d
0x14001156a  jnz     loc_140011BA5
0x140011570  mov     rax, gs:188h
0x140011579  lea     rcx, [rbp+130h+SystemInformation]; void *
0x14001157d  mov     [rsi+0A08h], rax
0x140011584  mov     r14d, 40h ; '@'
0x14001158a  mov     al, [rsi+460h]
0x140011590  mov     r8d, r14d; Size
0x140011593  neg     al
0x140011595  mov     eax, [rsi+0AB8h]
0x14001159b  sbb     r13d, r13d
0x14001159e  and     eax, 0FFFFFFF7h
0x1400115a1  not     r13d
0x1400115a4  xor     edx, edx; Val
0x1400115a6  and     r13d, 8
0x1400115aa  or      eax, r13d
0x1400115ad  mov     [rsi+0AB8h], eax
0x1400115b3  call    memset
0x1400115b8  mov     rcx, rsi; struct CDDPDEV *
0x1400115bb  call    ?InitDisplayMode@@YAXPEAUCDDPDEV@@@Z; InitDisplayMode(CDDPDEV *)
0x1400115c0  xor     r9d, r9d; ReturnLength
0x1400115c3  lea     rdx, [rbp+130h+SystemInformation]; SystemInformation
0x1400115c7  mov     r8d, r14d; SystemInformationLength
0x1400115ca  xor     ecx, ecx; SystemInformationClass
0x1400115cc  call    cs:__imp_ZwQuerySystemInformation
0x1400115d3  nop     dword ptr [rax+rax+00h]
0x1400115d8  mov     ebx, 2625Ah
0x1400115dd  test    eax, eax
0x1400115df  js      loc_140011BF1
0x1400115e5  mov     ecx, [rsi+400h]
0x1400115eb  mov     eax, 0FFFFFFFEh
0x1400115f0  cmp     ecx, eax
0x1400115f2  jz      loc_140011C6B
0x1400115f8  mov     eax, [rsi+404h]
0x1400115fe  xor     edx, edx
0x140011600  imul    rax, 989680h
0x140011607  div     rcx
0x14001160a  mov     rbx, rax
0x14001160d  mov     rax, rbx
0x140011610  mov     edx, 0Eh
0x140011615  neg     rax
0x140011618  mov     [rsi+0A70h], rax
0x14001161f  mov     rcx, gs:188h
0x140011628  call    cs:__imp_KeSetActualBasePriorityThread
0x14001162f  nop     dword ptr [rax+rax+00h]
0x140011634  mov     dword ptr [rsi+1568h], 1
0x14001163e  xor     r8d, r8d; Wait
0x140011641  mov     rcx, [rsi+0A48h]; Event
0x140011648  xor     edx, edx; Increment
0x14001164a  call    cs:__imp_KeSetEvent
0x140011651  nop     dword ptr [rax+rax+00h]
0x140011656  lea     rax, ?CddAddD3DDirtyRgn@@YAXQEAXQEBUtagRECT@@@Z; CddAddD3DDirtyRgn(void * const,tagRECT const * const)
0x14001165d  mov     [rbp+130h+var_160], r12
0x140011661  mov     [rbp+130h+var_188], rax
0x140011665  lea     rcx, [rsp+230h+Timer]; void *
0x14001166a  lea     rax, ?CddNotifyExclusiveGDIOwner@@YAXQEAX@Z; CddNotifyExclusiveGDIOwner(void * const)
0x140011671  mov     [rbp+130h+var_190], rsi
0x140011675  mov     [rbp+130h+var_180], rax
0x140011679  xorps   xmm0, xmm0
0x14001167c  lea     rax, ?CddUpdatePresentRects@@YAXQEAXPEAPEBUtagRECT@@PEAI@Z; CddUpdatePresentRects(void * const,tagRECT const * *,uint *)
0x140011683  mov     [rbp+130h+var_F8], r12
0x140011687  mov     [rbp+130h+var_178], rax
0x14001168b  mov     r8, r14; Size
0x14001168e  mov     rax, [rsi+0A38h]
0x140011695  xor     edx, edx; Val
0x140011697  mov     [rbp+130h+Object], rax
0x14001169b  mov     rax, [rsi+0A30h]
0x1400116a2  mov     [rbp+130h+Event], rax
0x1400116a6  mov     rax, [rsi+0A40h]
0x1400116ad  mov     [rbp+130h+var_100], rax
0x1400116b1  lea     rax, [rsp+230h+var_1E0]
0x1400116b6  mov     [rsi+1C60h], rax
0x1400116bd  movdqu  [rbp+130h+var_170], xmm0
0x1400116c2  mov     [rsp+230h+var_1E0], r12d
0x1400116c7  call    memset
0x1400116cc  lea     rcx, [rsp+230h+Timer]; Timer
0x1400116d1  call    cs:__imp_KeInitializeTimer
0x1400116d8  nop     dword ptr [rax+rax+00h]
0x1400116dd  mov     rax, ds:0FFFFF78000000008h
0x1400116e7  lea     r14, [rbx+rax]
0x1400116eb  mov     [rsp+230h+var_1D8], r14
0x1400116f0  mov     [rsi+0ABDh], r12b
0x1400116f7  mov     r15d, r12d
0x1400116fa  mov     dl, byte ptr [rsp+230h+var_1E0+3]
0x1400116fe  mov     al, byte ptr [rsp+230h+var_1E0+2]
0x140011702  mov     cl, byte ptr [rsp+230h+var_1E0+1]
0x140011706  or      dl, al
0x140011708  mov     al, byte ptr [rsp+230h+var_1E0]
0x14001170c  or      cl, dl
0x14001170e  or      al, cl
0x140011710  jnz     loc_140011876
0x140011716  cmp     [rsi+0A9Ch], r12b
0x14001171d  jnz     loc_140011C7C
0x140011723  mov     al, [rsi+0AC0h]
0x140011729  test    al, al
0x14001172b  jnz     short loc_1400117A7
0x14001172d  mov     eax, [rsi+0AB8h]
0x140011733  test    al, 10h
0x140011735  jnz     short loc_1400117A7
0x140011737  cmp     [rsi+0A9Fh], r12b
0x14001173e  jnz     short loc_1400117A7
0x140011740  test    al, 8
0x140011742  jz      loc_140011CF8
0x140011748  mov     r10, [rsi+9B8h]
0x14001174f  test    r10, r10
0x140011752  jz      loc_140011CF8
0x140011758  cmp     [rsi+9D8h], r12d
0x14001175f  jz      loc_140011CF8
0x140011765  mov     rcx, [rsi+0E20h]
0x14001176c  lea     r9, [rbp+130h+Object]
0x140011770  mov     rax, [rsi+0C0h]
0x140011777  mov     r8d, 3
0x14001177d  mov     edx, [rsi+310h]
0x140011783  mov     qword ptr [rsp+230h+WaitMode], rcx
0x140011788  mov     rcx, r10
0x14001178b  call    _guard_dispatch_icall
0x140011790  movsxd  r15, eax
0x140011793  test    eax, eax
0x140011795  js      loc_140011C8E
0x14001179b  cmp     r15d, 3
0x14001179f  ja      loc_140011CE8
0x1400117a5  jmp     short loc_14001180B
0x1400117a7  mov     rax, [rsi+0A50h]
0x1400117ae  lea     rdx, [rbp+130h+Object]; Object
0x1400117b2  xor     r9d, r9d; WaitReason
0x1400117b5  mov     [rbp+130h+var_F8], rax
0x1400117b9  lea     rax, [rbp+130h+var_F0]
0x1400117bd  mov     [rsp+230h+WaitBlockArray], rax; WaitBlockArray
0x1400117c2  mov     [rsp+230h+Timeout], r12; Timeout
0x1400117c7  mov     [rsp+230h+Alertable], r12b; Alertable
0x1400117cc  lea     r8d, [r9+1]; WaitType
0x1400117d0  lea     ecx, [r9+4]; Count
0x1400117d4  mov     [rsp+230h+WaitMode], r12b; WaitMode
0x1400117d9  call    cs:__imp_KeWaitForMultipleObjects
0x1400117e0  nop     dword ptr [rax+rax+00h]
0x1400117e5  mov     r15d, eax
0x1400117e8  cmp     eax, 3
0x1400117eb  jz      loc_140011D73
0x1400117f1  mov     byte ptr [rsi+0ABDh], 1
0x1400117f8  test    r15d, r15d
0x1400117fb  js      loc_140011DC6
0x140011801  cmp     r15d, 3
0x140011805  ja      loc_140011DC6
0x14001180b  cmp     r15d, 1
0x14001180f  jz      loc_140011E19
0x140011815  mov     rcx, [rbp+130h+Event]; Event
0x140011819  call    cs:__imp_KeReadStateEvent
0x140011820  nop     dword ptr [rax+rax+00h]
0x140011825  test    eax, eax
0x140011827  jnz     loc_140011E23
0x14001182d  cmp     r15d, 2
0x140011831  jz      loc_140011E3D
0x140011837  mov     rcx, [rbp+130h+var_100]; Event
0x14001183b  call    cs:__imp_KeReadStateEvent
0x140011842  nop     dword ptr [rax+rax+00h]
0x140011847  test    eax, eax
0x140011849  jnz     loc_140011E47
0x14001184f  cmp     r15d, 3
0x140011853  jnz     loc_1400119CA
0x140011859  mov     byte ptr [rsp+230h+var_1E0+3], 1
0x14001185e  mov     rcx, [rbp+130h+Object]; Event
0x140011862  call    cs:__imp_KeReadStateEvent
0x140011869  nop     dword ptr [rax+rax+00h]
0x14001186e  test    eax, eax
0x140011870  jnz     loc_140011E61
0x140011876  mov     [rsi+0AC2h], r12b
0x14001187d  mov     al, byte ptr [rsp+230h+var_1E0+3]
0x140011881  test    al, al
0x140011883  jz      short loc_1400118F6
0x140011885  inc     dword ptr [rsi+0A78h]
0x14001188b  xor     edx, edx
0x14001188d  mov     eax, [rsi+0A78h]
0x140011893  div     dword ptr [rsi+0A6Ch]
0x140011899  mov     byte ptr [rsp+230h+var_1E0+3], r12b
0x14001189e  test    edx, edx
0x1400118a0  jnz     loc_1400116F0
0x1400118a6  cmp     [rsi+0A98h], r12b
0x1400118ad  jnz     loc_140011E7B
0x1400118b3  mov     al, [rsi+0AC1h]
0x1400118b9  test    al, al
0x1400118bb  jz      loc_140011A6A
0x1400118c1  mov     eax, [rsi+0A80h]
0x1400118c7  not     eax
0x1400118c9  and     [rsi+0A7Ch], eax
0x1400118cf  mov     al, [rsi+0AC1h]
0x1400118d5  test    al, al
0x1400118d7  jnz     loc_140011E8D
0x1400118dd  neg     al
0x1400118df  sbb     r14d, r14d
0x1400118e2  and     r14d, 10h
0x1400118e6  cmp     [rsi+0A98h], r12b
0x1400118ed  jz      short loc_14001191B
0x1400118ef  mov     byte ptr [rsp+230h+var_1E0], 1
0x1400118f4  jmp     short loc_14001191B
0x1400118f6  mov     al, byte ptr [rsp+230h+var_1E0+1]
0x1400118fa  test    al, al
0x1400118fc  jz      loc_140011A8E
0x140011902  mov     byte ptr [rsp+230h+var_1E0+1], r12b
0x140011907  mov     al, [rsi+0ABDh]
0x14001190d  test    al, al
0x14001190f  jnz     loc_140011E97
0x140011915  mov     r14d, 10h
0x14001191b  cmp     dword ptr [rsi+1568h], 1
0x140011922  jnz     loc_140011AE8
0x140011928  cmp     r14d, 0Bh
0x14001192c  jz      loc_140011ED1
0x140011932  cmp     r14d, 11h
0x140011936  jz      loc_1400119FC
0x14001193c  cmp     r14d, 0Fh
0x140011940  jz      loc_140011FD6
0x140011946  cmp     r14d, 0Dh
0x14001194a  jz      loc_140011A43
0x140011950  cmp     r14d, 10h
0x140011954  jz      loc_140012164
0x14001195a  cmp     r14d, 7
0x14001195e  jz      loc_140012186
0x140011964  cmp     r14d, 6
0x140011968  jz      loc_140012287
0x14001196e  cmp     r14d, 13h
0x140011972  jz      loc_1400123FB
0x140011978  cmp     r14d, 14h
0x14001197c  jz      loc_140012439
0x140011982  cmp     r14d, 4
0x140011986  jz      loc_1400124BB
0x14001198c  cmp     r14d, 8
0x140011990  jz      loc_1400124C8
0x140011996  cmp     r14d, 12h
0x14001199a  jz      loc_1400124ED
0x1400119a0  cmp     r14d, 0Ch
0x1400119a4  jz      loc_14001250B
0x1400119aa  cmp     r14d, 15h
0x1400119ae  jnz     loc_140012531
0x1400119b4  mov     rax, [rsi+208h]
0x1400119bb  xor     ecx, ecx
0x1400119bd  mov     edx, [rsi+9D8h]
0x1400119c3  call    _guard_dispatch_icall
0x1400119c8  jmp     short loc_140011A0C
0x1400119ca  cmp     [rsi+0A9Ch], r12b
0x1400119d1  jnz     short loc_1400119E9
0x1400119d3  mov     eax, [rsi+0AB8h]
0x1400119d9  mov     ecx, eax
0x1400119db  xor     ecx, r13d
0x1400119de  and     ecx, 8
0x1400119e1  xor     ecx, eax
0x1400119e3  mov     [rsi+0AB8h], ecx
0x1400119e9  test    r15d, r15d
0x1400119ec  jnz     loc_14001185E
0x1400119f2  mov     byte ptr [rsp+230h+var_1E0+1], 1
0x1400119f7  jmp     loc_140011876
0x1400119fc  test    dword ptr [rsi+0AB8h], 100h
0x140011a06  jnz     loc_140011F73
0x140011a0c  mov     al, [rsi+0AC2h]
0x140011a12  mov     r14, [rsp+230h+var_1D8]
0x140011a17  test    al, al
0x140011a19  jnz     loc_1400116F0
0x140011a1f  mov     [rsi+0E10h], r12d
0x140011a26  xor     r8d, r8d; Wait
0x140011a29  mov     rcx, [rsi+0A48h]; Event
0x140011a30  xor     edx, edx; Increment
0x140011a32  call    cs:__imp_KeSetEvent
0x140011a39  nop     dword ptr [rax+rax+00h]
0x140011a3e  jmp     loc_1400116F0
0x140011a43  mov     r14d, [rsi+0E40h]
0x140011a4a  mov     rcx, rsi; this
0x140011a4d  mov     edx, r14d; unsigned int
0x140011a50  call    ?FlushGdiOutput@CDDPDEV@@QEAAXI@Z; CDDPDEV::FlushGdiOutput(uint)
0x140011a55  test    r14b, 1
0x140011a59  jnz     loc_140012025
0x140011a5f  test    r14b, 2
0x140011a63  jz      short loc_140011A0C
0x140011a65  jmp     loc_14001217C
0x140011a6a  inc     dword ptr [rsi+0A7Ch]
0x140011a70  mov     ecx, [rsi+0A7Ch]
0x140011a76  test    [rsi+0A80h], ecx
0x140011a7c  jnz     loc_1400116F0
0x140011a82  mov     byte ptr [rsi+0AC0h], 1
0x140011a89  jmp     loc_1400116F0
0x140011a8e  mov     al, byte ptr [rsp+230h+var_1E0]
0x140011a92  test    al, al
0x140011a94  jnz     loc_140011EB8
0x140011a9a  mov     al, byte ptr [rsp+230h+var_1E0+2]
  ... truncated ...
```
