# UlResumeParsing

- ea: `0x1c000cec0`
- end: `0x1c000d68b`
- name: `UlResumeParsing`
- size: `1995`
- prototype: ``
- caller_count: `9`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1c000fd50`
- `0x1c00c0360`
- `0x1c00c2a50`
- `0x1c00cd390`
- `0x1c00cd760`
- `0x1c00ce660`
- `0x1c00ceb70`
- `0x1c00d3bf0`
- `0x1c0117f70`

## callees

- `0x1c0001118`
- `0x1c0001ae0`
- `0x1c0006870`
- `0x1c000cec0`
- `0x1c000e3b0`
- `0x1c000fc68`
- `0x1c001683c`
- `0x1c001a4b0`
- `0x1c001b610`
- `0x1c002cad4`
- `0x1c002e5e4`
- `0x1c004ceac`
- `0x1c008f21c`
- `0x1c008f3ec`
- `0x1c008f680`
- `0x1c008f76c`
- `0x1c00aa2f8`
- `0x1c00c2ce0`
- `0x1c00d1380`

## import_xrefs

- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c000d2c5`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c000d65d`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c000d2c5`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c000d65d`
- `ntoskrnl!ExQueryDepthSList` at `0x1c000d2ac`
- `ntoskrnl!ExQueryDepthSList` at `0x1c000d62b`
- `ntoskrnl!ExQueryDepthSList` at `0x1c000d2ac`
- `ntoskrnl!ExQueryDepthSList` at `0x1c000d62b`
- `ntoskrnl!KeBugCheckEx` at `0x1c0022d9c`
- `ntoskrnl!KeBugCheckEx` at `0x1c0022d9c`
- `ntoskrnl!IofCompleteRequest` at `0x1c000d5c2`
- `ntoskrnl!IofCompleteRequest` at `0x1c0022eed`
- `ntoskrnl!IofCompleteRequest` at `0x1c00231ec`
- `ntoskrnl!IofCompleteRequest` at `0x1c000d5c2`
- `ntoskrnl!IofCompleteRequest` at `0x1c0022eed`
- `ntoskrnl!IofCompleteRequest` at `0x1c00231ec`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c0022ff6`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c00232e7`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c0022ff6`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c00232e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c000d539`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c000d67a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c000d539`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c000d67a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0023096`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0023096`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c0023066`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c0023066`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c000d12c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c000d12c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c000cf4f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c000cf4f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c000d138`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c000d138`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c000cf3a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c000cf3a`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c0022d0e`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c0022d0e`

## pseudocode

```c
__int64 __fastcall UlResumeParsing(__int64 a1, unsigned __int8 a2)
{
  _QWORD *v4; // rcx
  int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // rdi
  int v8; // eax
  __int64 v10; // rdi
  int v11; // eax
  _QWORD **v12; // rsi
  _QWORD *v13; // rax
  __int64 *v14; // rsi
  volatile signed __int32 *v15; // rdi
  __int64 *v16; // r14
  __int64 result; // rax
  __int64 v18; // r12
  __int64 v19; // rax
  __int64 **v20; // rcx
  unsigned int v21; // edx
  unsigned int v22; // eax
  __int64 v23; // r14
  __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rdi
  int v27; // eax
  _QWORD **v28; // rsi
  _QWORD *v29; // rax
  __int64 *v30; // rdi
  volatile signed __int32 *v31; // rsi
  __int64 *v32; // r14
  __int64 v33; // r12
  __int64 v34; // rax
  __int64 **v35; // rcx
  __int64 v36; // rax
  unsigned int v37; // edx
  unsigned int v38; // eax
  __int64 v39; // r14
  __int64 v40; // rcx
  __int64 v41; // r9
  __int64 v42; // r9
  __int64 v43; // rax
  __int64 v44; // r9
  __int64 v45; // r9
  _QWORD *v46; // rsi
  __int64 v47; // r14
  _QWORD *v48; // rcx
  IRP *v49; // r14
  PNAMED_PIPE_CREATE_PARAMETERS v50; // rcx
  __int64 v51; // r12
  unsigned int v52; // edx
  unsigned int v53; // eax
  KIRQL v54; // al
  __int64 v55; // r9
  KIRQL v56; // di
  __int64 v57; // r9
  __int64 v58; // r9
  _QWORD *v59; // rsi
  __int64 v60; // r14
  _QWORD *v61; // rcx
  IRP *v62; // r14
  PNAMED_PIPE_CREATE_PARAMETERS Parameters; // rcx
  __int64 v64; // r12
  unsigned int v65; // edx
  unsigned int v66; // eax
  __int64 v67; // [rsp+28h] [rbp-21h]
  _QWORD v68[2]; // [rsp+38h] [rbp-11h] BYREF
  struct _LIST_ENTRY *v69; // [rsp+48h] [rbp-1h] BYREF
  struct _LIST_ENTRY *Blink; // [rsp+50h] [rbp+7h] BYREF
  _QWORD v71[2]; // [rsp+58h] [rbp+Fh] BYREF
  _QWORD v72[2]; // [rsp+68h] [rbp+1Fh] BYREF

  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x2000) != 0 )
  {
    if ( a1 )
      v41 = *(_QWORD *)(a1 + 24);
    else
      v41 = 0;
    WPP_SF_qqD(39, WPP_95173837b5773721cd51a44381a2b960_Traceguids, a1, v41, a2);
  }
  v4 = v68;
  v68[1] = v68;
  v5 = *(_DWORD *)(a1 + 520);
  v68[0] = v68;
  if ( (v5 & 2) == 0 )
  {
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(a1 + 464, 0);
    if ( (*(_DWORD *)(a1 + 520) & 2) != 0 )
    {
LABEL_38:
      ExReleasePushLockExclusiveEx(a1 + 464, 0);
      KeLeaveCriticalRegion();
      v4 = (_QWORD *)v68[0];
      goto LABEL_39;
    }
    if ( !*(_BYTE *)(a1 + 412) )
      *(_BYTE *)(a1 + 412) = a2;
    if ( *(_QWORD *)(a1 + 688) != -1 && *(_QWORD *)(a1 + 696) != -1 && IoGetCurrentProcess() != UxSystemProcess )
    {
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 20));
      v43 = *(_QWORD *)(a1 + 952);
      if ( *(_QWORD *)(a1 + 176) || *(_QWORD *)(a1 + 192) || *(_QWORD *)(a1 + 208) )
        KeBugCheckEx(0xFAu, 1u, a1 + 176, (ULONG_PTR)"minio\\http\\sys\\httprcv.c", 0x6FFu);
      LODWORD(v67) = -1;
      LOBYTE(v42) = 1;
      UlThreadPoolEnqueueWorkItem(0, a1 + 176, UlpResumeParsingWorker, v42, v43, v67);
      goto LABEL_38;
    }
    v7 = *(_QWORD *)(a1 + 456);
    v8 = *(_DWORD *)(v7 + 2184);
    if ( !*(_QWORD *)(v7 + 2112) && (v8 & 0x40) == 0 )
    {
      *(_DWORD *)(v7 + 2184) = v8 | 0x4000;
      if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
        WPP_SF_qq(26, WPP_6cebc73ec5833d6d901146f2aa6dea31_Traceguids, a1, *(_QWORD *)(a1 + 24));
      v10 = *(_QWORD *)(a1 + 456);
      if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
      {
        if ( v10 )
          v57 = *(_QWORD *)(v10 + 64);
        else
          v57 = 0;
        WPP_SF_qq(57, WPP_6cebc73ec5833d6d901146f2aa6dea31_Traceguids, *(_QWORD *)(a1 + 456), v57);
      }
      if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
      {
        if ( v10 )
          v58 = *(_QWORD *)(v10 + 64);
        else
          v58 = 0;
        WPP_SF_qq(36, WPP_6cebc73ec5833d6d901146f2aa6dea31_Traceguids, v10, v58);
      }
      v11 = *(_DWORD *)(v10 + 2184) | 0x400;
      *(_DWORD *)(v10 + 2184) = v11;
      if ( (v11 & 0x4000) == 0 )
      {
        v59 = (_QWORD *)(v10 + 2496);
        v60 = 3;
        do
        {
          if ( *v59 )
          {
            LOBYTE(v6) = 1;
            UlHkeCancelCalloutContext(*v59, v6);
          }
          ++v59;
          --v60;
        }
        while ( v60 );
        v11 = *(_DWORD *)(v10 + 2184);
      }
      v12 = (_QWORD **)(v10 + 488);
      *(_DWORD *)(v10 + 2184) = v11 & 0xFFFFBFFF;
      while ( 1 )
      {
        v13 = *v12;
        if ( *v12 == v12 )
          break;
        if ( (_QWORD **)v13[1] != v12 )
          goto LABEL_76;
        v61 = (_QWORD *)*v13;
        if ( *(_QWORD **)(*v13 + 8LL) != v13 )
          goto LABEL_76;
        *v12 = v61;
        v62 = (IRP *)(v13 - 21);
        v61[1] = v12;
        *v13 = 0;
        v13[1] = 0;
        if ( _InterlockedExchange64(v13 - 8, 0) )
        {
          Parameters = v62->Tail.Overlay.CurrentStackLocation->Parameters.CreatePipe.Parameters;
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)&Parameters[1].CompletionMode, 0xFFFFFFFF) == 1 )
            UlpQueueFreeHttpRequest(Parameters);
          v62->Tail.Overlay.CurrentStackLocation->Parameters.CreatePipe.Parameters = 0;
          Blink = v62->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink;
          v62->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink = 0;
          UlFreeGrip(&Blink);
          v62->IoStatus.Status = -1073741536;
          v62->IoStatus.Information = 0;
          IofCompleteRequest(v62, 0);
        }
      }
      if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
        WPP_SF_(37, WPP_6cebc73ec5833d6d901146f2aa6dea31_Traceguids);
      if ( *(_QWORD *)(v10 + 64) )
      {
        if ( *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v10 + 24) + 960LL) + 79LL)
          && Microsoft_Windows_Networking_CorrelationEnabled )
        {
          UlEtwStopActivity(v10 + 72, 3);
        }
        UxFreeOpaqueIdEx(*(_QWORD *)(v10 + 64));
        *(_QWORD *)(v10 + 64) = 0;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v10 + 48), 0xFFFFFFFF) == 1 )
          UlpQueueFreeHttpRequest(v10);
      }
      UlUnlinkRequestFromRequestQueue(v10);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v10 + 48), 0xFFFFFFFF) == 1 )
        UlpQueueFreeHttpRequest(v10);
      if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
        WPP_SF_(58, WPP_6cebc73ec5833d6d901146f2aa6dea31_Traceguids);
      *(_DWORD *)(a1 + 520) &= ~4u;
      *(_QWORD *)(a1 + 456) = 0;
      if ( (WORD2(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x2000) != 0 )
        WPP_SF_q(27, WPP_6cebc73ec5833d6d901146f2aa6dea31_Traceguids, a1);
      if ( *(_QWORD *)(a1 + 488) )
      {
        v14 = *(__int64 **)(a1 + 472);
        if ( v14 != (__int64 *)(a1 + 472) )
        {
          while ( 1 )
          {
            v15 = (volatile signed __int32 *)(v14 - 4);
            v16 = v14;
            if ( v14 - 4 == *(__int64 **)(a1 + 488) )
              goto LABEL_35;
            v14 = (__int64 *)*v14;
            v18 = *(_QWORD *)(a1 + 960);
            if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
              WPP_SF_qq(50, WPP_6cebc73ec5833d6d901146f2aa6dea31_Traceguids, *(_QWORD *)(a1 + 960), v15);
            if ( SBYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) < 0 )
              WPP_SF_q(51, WPP_6cebc73ec5833d6d901146f2aa6dea31_Traceguids, *((_QWORD *)v15 + 16));
            v19 = *v16;
            if ( *v16 )
            {
              if ( *(__int64 **)(v19 + 8) != v16 )
                goto LABEL_76;
              v20 = (__int64 **)v16[1];
              if ( *v20 != v16 )
                goto LABEL_76;
              *v20 = (__int64 *)v19;
              *(_QWORD *)(v19 + 8) = v20;
              *v16 = 0;
              *((_QWORD *)v15 + 5) = 0;
            }
            if ( *(_BYTE *)(v18 + 79) && Microsoft_Windows_Networking_CorrelationEnabled )
            {
              v72[1] = *((_QWORD *)&UlEtwBasePtrActivityGuid + 1);
              v72[0] = v15;
              UlEtwStopActivity(v72, 2);
            }
            if ( _InterlockedExchangeAdd(v15 + 5, 0xFFFFFFFF) == 1 )
              break;
LABEL_71:
            if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
              WPP_SF_(52, WPP_6cebc73ec5833d6d901146f2aa6dea31_Traceguids);
            if ( v14 == (__int64 *)(a1 + 472) )
              goto LABEL_35;
          }
          if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
            WPP_SF_q(53, WPP_6cebc73ec5833d6d901146f2aa6dea31_Traceguids, v15);
          if ( (v15[31] & 1) == 0 )
          {
            *((_DWORD *)v15 + 4) = 1886538869;
            ExFreePoolWithTag((PVOID)v15, 0);
            goto LABEL_69;
          }
          *((_DWORD *)v15 + 4) = 1347570805;
          if ( UxCompactMode )
          {
            v64 = UlLookaside;
            v65 = KeGetCurrentNodeNumber() + 1;
            v66 = *(_DWORD *)v64 - 1;
            if ( v65 < *(_DWORD *)v64 )
              v66 = v65;
            v23 = *(_QWORD *)(*(_QWORD *)(v64 + 32) + 8LL * v66);
            if ( *(_BYTE *)(v23 + 112) )
              goto LABEL_67;
            v24 = v64;
          }
          else
          {
            v21 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
            v22 = *(_DWORD *)UlLookaside - 1;
            if ( v21 < *(_DWORD *)UlLookaside )
              v22 = v21;
            v23 = *(_QWORD *)(*(_QWORD *)(UlLookaside + 32) + 8LL * v22);
            if ( *(_BYTE *)(v23 + 112) )
              goto LABEL_67;
            v24 = UlLookaside;
          }
          PplpLazyInitializeLookasideList(v24, v23);
LABEL_67:
          ++*(_DWORD *)(v23 + 28);
          if ( ExQueryDepthSList((PSLIST_HEADER)v23) >= *(_WORD *)(v23 + 16) )
          {
            ++*(_DWORD *)(v23 + 32);
            (*(void (__fastcall **)(volatile signed __int32 *, __int64))(v23 + 56))(v15, v23);
          }
          else
          {
            ExpInterlockedPushEntrySList((PSLIST_HEADER)v23, (PSLIST_ENTRY)v15);
          }
LABEL_69:
          if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
            WPP_SF_(54, WPP_6cebc73ec5833d6d901146f2aa6dea31_Traceguids);
          goto LABEL_71;
        }
      }
LABEL_35:
      if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) >= 0 )
      {
LABEL_36:
        if ( !*(_BYTE *)(a1 + 412) && (int)UlpParseNextRequest(a1, 0, v68) < 0 && *(_QWORD *)(a1 + 456) )
          UlSendErrorResponse(a1);
        goto LABEL_38;
      }
LABEL_198:
      WPP_SF_(28, WPP_6cebc73ec5833d6d901146f2aa6dea31_Traceguids);
      goto LABEL_36;
    }
    *(_DWORD *)(v7 + 2184) = v8 | 0x100;
    UlProcessBufferQueue(v7, 0, 0);
    if ( *(_DWORD *)(v7 + 480) != 10 )
    {
      v54 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 528));
      LOBYTE(v55) = 1;
      v56 = v54;
      UlSetBundleTimerEx(a1 + 536, 4, 0, v55);
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 528), v56);
      goto LABEL_36;
    }
    *(_DWORD *)(v7 + 2184) |= 0x4000u;
    if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
      WPP_SF_qq(26, WPP_6cebc73ec5833d6d901146f2aa6dea31_Traceguids, a1, *(_QWORD *)(a1 + 24));
    v26 = *(_QWORD *)(a1 + 456);
    if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    {
      if ( v26 )
        v44 = *(_QWORD *)(v26 + 64);
      else
        v44 = 0;
      WPP_SF_qq(57, WPP_6cebc73ec5833d6d901146f2aa6dea31_Traceguids, *(_QWORD *)(a1 + 456), v44);
    }
    if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    {
      if ( v26 )
        v45 = *(_QWORD *)(v26 + 64);
      else
        v45 = 0;
      WPP_SF_qq(36, WPP_6cebc73ec5833d6d901146f2aa6dea31_Traceguids, v26, v45);
    }
    v27 = *(_DWORD *)(v26 + 2184) | 0x400;
    *(_DWORD *)(v26 + 2184) = v27;
    if ( (v27 & 0x4000) == 0 )
    {
      v46 = (_QWORD *)(v26 + 2496);
      v47 = 3;
      do
      {
        if ( *v46 )
        {
          LOBYTE(v25) = 1;
          UlHkeCancelCalloutContext(*v46, v25);
        }
        ++v46;
        --v47;
      }
      while ( v47 );
      v27 = *(_DWORD *)(v26 + 2184);
    }
    v28 = (_QWORD **)(v26 + 488);
    *(_DWORD *)(v26 + 2184) = v27 & 0xFFFFBFFF;
    while ( 1 )
    {
      v29 = *v28;
      if ( *v28 == v28 )
        break;
      if ( (_QWORD **)v29[1] != v28 || (v48 = (_QWORD *)*v29, *(_QWORD **)(*v29 + 8LL) != v29) )
LABEL_76:
        __fastfail(3u);
      *v28 = v48;
      v49 = (IRP *)(v29 - 21);
      v48[1] = v28;
      *v29 = 0;
      v29[1] = 0;
      if ( _InterlockedExchange64(v29 - 8, 0) )
      {
        v50 = v49->Tail.Overlay.CurrentStackLocation->Parameters.CreatePipe.Parameters;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v50[1].CompletionMode, 0xFFFFFFFF) == 1 )
          UlpQueueFreeHttpRequest(v50);
        v49->Tail.Overlay.CurrentStackLocation->Parameters.CreatePipe.Parameters = 0;
        v69 = v49->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink;
        v49->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink = 0;
        UlFreeGrip(&v69);
        v49->IoStatus.Status = -1073741536;
        v49->IoStatus.Information = 0;
        IofCompleteRequest(v49, 0);
      }
    }
    if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
      WPP_SF_(37, WPP_6cebc73ec5833d6d901146f2aa6dea31_Traceguids);
    if ( *(_QWORD *)(v26 + 64) )
    {
      if ( *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v26 + 24) + 960LL) + 79LL)
        && Microsoft_Windows_Networking_CorrelationEnabled )
      {
        UlEtwStopActivity(v26 + 72, 3);
      }
      UxFreeOpaqueIdEx(*(_QWORD *)(v26 + 64));
      *(_QWORD *)(v26 + 64) = 0;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v26 + 48), 0xFFFFFFFF) == 1 )
        UlpQueueFreeHttpRequest(v26);
    }
    UlUnlinkRequestFromRequestQueue(v26);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v26 + 48), 0xFFFFFFFF) == 1 )
      UlpQueueFreeHttpRequest(v26);
    if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
      WPP_SF_(58, WPP_6cebc73ec5833d6d901146f2aa6dea31_Traceguids);
    *(_DWORD *)(a1 + 520) &= ~4u;
    *(_QWORD *)(a1 + 456) = 0;
    if ( (WORD2(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x2000) != 0 )
      WPP_SF_q(27, WPP_6cebc73ec5833d6d901146f2aa6dea31_Traceguids, a1);
    if ( !*(_QWORD *)(a1 + 488) || (v30 = *(__int64 **)(a1 + 472), v30 == (__int64 *)(a1 + 472)) )
    {
LABEL_124:
      if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) >= 0 )
        goto LABEL_36;
      goto LABEL_198;
    }
    while ( 1 )
    {
      v31 = (volatile signed __int32 *)(v30 - 4);
      v32 = v30;
      if ( v30 - 4 == *(__int64 **)(a1 + 488) )
        goto LABEL_124;
      v30 = (__int64 *)*v30;
      v33 = *(_QWORD *)(a1 + 960);
      if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
        WPP_SF_qq(50, WPP_6cebc73ec5833d6d901146f2aa6dea31_Traceguids, *(_QWORD *)(a1 + 960), v31);
      if ( SBYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) < 0 )
        WPP_SF_q(51, WPP_6cebc73ec5833d6d901146f2aa6dea31_Traceguids, *((_QWORD *)v31 + 16));
      v34 = *v32;
      if ( *v32 )
      {
        if ( *(__int64 **)(v34 + 8) != v32 )
          goto LABEL_76;
        v35 = (__int64 **)v32[1];
        if ( *v35 != v32 )
          goto LABEL_76;
        *v35 = (__int64 *)v34;
        *(_QWORD *)(v34 + 8) = v35;
        *v32 = 0;
        *((_QWORD *)v31 + 5) = 0;
      }
      if ( *(_BYTE *)(v33 + 79) && Microsoft_Windows_Networking_CorrelationEnabled )
      {
        v71[1] = *((_QWORD *)&UlEtwBasePtrActivityGuid + 1);
        v71[0] = v31;
        UlEtwStopActivity(v71, 2);
      }
      if ( _InterlockedExchangeAdd(v31 + 5, 0xFFFFFFFF) == 1 )
        break;
LABEL_121:
      if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
        WPP_SF_(52, WPP_6cebc73ec5833d6d901146f2aa6dea31_Traceguids);
      if ( v30 == (__int64 *)(a1 + 472) )
        goto LABEL_124;
    }
    if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
      WPP_SF_q(53, WPP_6cebc73ec5833d6d901146f2aa6dea31_Traceguids, v31);
    if ( (v31[31] & 1) == 0 )
    {
      *((_DWORD *)v31 + 4) = 1886538869;
      ExFreePoolWithTag((PVOID)v31, 0);
      goto LABEL_119;
    }
    *((_DWORD *)v31 + 4) = 1347570805;
    if ( UxCompactMode )
    {
      v51 = UlLookaside;
      v52 = KeGetCurrentNodeNumber() + 1;
      v53 = *(_DWORD *)v51 - 1;
      if ( v52 < *(_DWORD *)v51 )
        v53 = v52;
      v39 = *(_QWORD *)(*(_QWORD *)(v51 + 32) + 8LL * v53);
      if ( *(_BYTE *)(v39 + 112) )
        goto LABEL_136;
      v40 = v51;
    }
    else
    {
      v37 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
      v38 = *(_DWORD *)UlLookaside - 1;
      if ( v37 < *(_DWORD *)UlLookaside )
        v38 = v37;
      v39 = *(_QWORD *)(*(_QWORD *)(UlLookaside + 32) + 8LL * v38);
      if ( *(_BYTE *)(v39 + 112) )
        goto LABEL_136;
      v40 = UlLookaside;
    }
    PplpLazyInitializeLookasideList(v40, v39);
LABEL_136:
    ++*(_DWORD *)(v39 + 28);
    if ( ExQueryDepthSList((PSLIST_HEADER)v39) < *(_WORD *)(v39 + 16) )
    {
      ExpInterlockedPushEntrySList((PSLIST_HEADER)v39, (PSLIST_ENTRY)v31);
    }
    else
    {
      ++*(_DWORD *)(v39 + 32);
      (*(void (__fastcall **)(volatile signed __int32 *, __int64))(v39 + 56))(v31, v39);
    }
LABEL_119:
    if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
      WPP_SF_(54, WPP_6cebc73ec5833d6d901146f2aa6dea31_Traceguids);
    goto LABEL_121;
  }
LABEL_39:
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
  {
    WPP_SF_q(265, WPP_95173837b5773721cd51a44381a2b960_Traceguids, v68);
    goto LABEL_129;
  }
  while ( v4 != v68 )
  {
    if ( (_QWORD *)v4[1] != v68 )
      goto LABEL_76;
    v36 = *v4;
    if ( *(_QWORD **)(*v4 + 8LL) != v4 )
      goto LABEL_76;
    v68[0] = *v4;
    *(_QWORD *)(v36 + 8) = v68;
    *v4 = 0;
    v4[1] = 0;
    IofCompleteRequest((PIRP)(v4 - 21), 0);
LABEL_129:
    v4 = (_QWORD *)v68[0];
  }
  result = LODWORD(WPP_MAIN_CB.Queue.ListEntry.Flink);
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    result = WPP_SF_(266, WPP_95173837b5773721cd51a44381a2b960_Traceguids);
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x2000) != 0 )
    return WPP_SF_(40, WPP_95173837b5773721cd51a44381a2b960_Traceguids);
  return result;
}

```

## disassembly

```asm
0x1c000cec0  push    rbp
0x1c000cec2  push    rbx
0x1c000cec3  push    rdi
0x1c000cec4  lea     rbp, [rsp-47h]
0x1c000cec9  sub     rsp, 90h
0x1c000ced0  mov     rax, cs:__security_cookie
0x1c000ced7  xor     rax, rsp
0x1c000ceda  mov     [rbp+57h+var_28], rax
0x1c000cede  movzx   edi, dl
0x1c000cee1  mov     rbx, rcx
0x1c000cee4  test    dword ptr cs:WPP_MAIN_CB.Queue, 2000h
0x1c000ceee  jnz     loc_1C0022CD4
0x1c000cef4  mov     [rsp+0A0h+arg_8], rsi
0x1c000cefc  lea     rax, [rbp+57h+var_68]
0x1c000cf00  mov     [rsp+0A0h+arg_10], r12
0x1c000cf08  lea     rcx, [rbp+57h+var_68]
0x1c000cf0c  mov     [rsp+0A0h+arg_18], r13
0x1c000cf14  mov     [rbp+57h+var_60], rax
0x1c000cf18  mov     eax, [rbx+208h]
0x1c000cf1e  mov     [rsp+0A0h+var_18], r14
0x1c000cf26  mov     [rsp+0A0h+var_20], r15
0x1c000cf2e  mov     [rbp+57h+var_68], rcx
0x1c000cf32  test    al, 2
0x1c000cf34  jnz     loc_1C000D148
0x1c000cf3a  call    cs:__imp_KeEnterCriticalRegion
0x1c000cf41  nop     dword ptr [rax+rax+00h]
0x1c000cf46  xor     edx, edx
0x1c000cf48  lea     rcx, [rbx+1D0h]
0x1c000cf4f  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1c000cf56  nop     dword ptr [rax+rax+00h]
0x1c000cf5b  mov     eax, [rbx+208h]
0x1c000cf61  test    al, 2
0x1c000cf63  jnz     loc_1C000D123
0x1c000cf69  cmp     byte ptr [rbx+19Ch], 0
0x1c000cf70  jnz     short loc_1C000CF79
0x1c000cf72  mov     [rbx+19Ch], dil
0x1c000cf79  cmp     qword ptr [rbx+2B0h], 0FFFFFFFFFFFFFFFFh
0x1c000cf81  jnz     loc_1C0022D00
0x1c000cf87  mov     rdi, [rbx+1C8h]
0x1c000cf8e  cmp     qword ptr [rdi+840h], 0
0x1c000cf96  mov     eax, [rdi+888h]
0x1c000cf9c  jnz     loc_1C000D57D
0x1c000cfa2  test    al, 40h
0x1c000cfa4  jnz     loc_1C000D57D
0x1c000cfaa  xor     cl, cl
0x1c000cfac  test    cl, cl
0x1c000cfae  jnz     loc_1C000D326
0x1c000cfb4  bts     eax, 0Eh
0x1c000cfb8  mov     [rdi+888h], eax
0x1c000cfbe  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c000cfc4  test    al, al
0x1c000cfc6  js      loc_1C00230A8
0x1c000cfcc  mov     rdi, [rbx+1C8h]
0x1c000cfd3  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c000cfd9  test    al, al
0x1c000cfdb  js      loc_1C00230C6
0x1c000cfe1  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c000cfe7  test    al, al
0x1c000cfe9  js      loc_1C00230EE
0x1c000cfef  mov     eax, [rdi+888h]
0x1c000cff5  bts     eax, 0Ah
0x1c000cff9  mov     [rdi+888h], eax
0x1c000cfff  bt      eax, 0Eh
0x1c000d003  jnb     loc_1C0023116
0x1c000d009  btr     eax, 0Eh
0x1c000d00d  lea     rsi, [rdi+1E8h]
0x1c000d014  mov     [rdi+888h], eax
0x1c000d01a  mov     rax, [rsi]
0x1c000d01d  cmp     rax, rsi
0x1c000d020  jnz     loc_1C0023147
0x1c000d026  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c000d02c  test    al, al
0x1c000d02e  js      loc_1C00231FE
0x1c000d034  cmp     qword ptr [rdi+40h], 0
0x1c000d039  jz      short loc_1C000D07E
0x1c000d03b  mov     rax, [rdi+18h]
0x1c000d03f  mov     rcx, [rax+3C0h]
0x1c000d046  cmp     byte ptr [rcx+4Fh], 0
0x1c000d04a  jz      short loc_1C000D05A
0x1c000d04c  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1c000d052  test    eax, eax
0x1c000d054  jnz     loc_1C0023215
0x1c000d05a  mov     rcx, [rdi+40h]
0x1c000d05e  call    UxFreeOpaqueIdEx
0x1c000d063  mov     eax, 0FFFFFFFFh
0x1c000d068  mov     qword ptr [rdi+40h], 0
0x1c000d070  lock xadd [rdi+30h], eax
0x1c000d075  cmp     eax, 1
0x1c000d078  jz      loc_1C0023229
0x1c000d07e  mov     rcx, rdi
0x1c000d081  call    UlUnlinkRequestFromRequestQueue
0x1c000d086  mov     eax, 0FFFFFFFFh
0x1c000d08b  lock xadd [rdi+30h], eax
0x1c000d090  cmp     eax, 1
0x1c000d093  jz      loc_1C000D584
0x1c000d099  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c000d09f  test    al, al
0x1c000d0a1  js      loc_1C0023237
0x1c000d0a7  and     dword ptr [rbx+208h], 0FFFFFFFBh
0x1c000d0ae  mov     qword ptr [rbx+1C8h], 0
0x1c000d0b9  test    dword ptr cs:WPP_MAIN_CB.Queue+4, 2000h
0x1c000d0c3  jnz     loc_1C002324E
0x1c000d0c9  cmp     qword ptr [rbx+1E8h], 0
0x1c000d0d1  jz      short loc_1C000D0F6
0x1c000d0d3  lea     r15, [rbx+1D8h]
0x1c000d0da  mov     rsi, [r15]
0x1c000d0dd  cmp     rsi, r15
0x1c000d0e0  jz      short loc_1C000D0F6
0x1c000d0e2  lea     rdi, [rsi-20h]
0x1c000d0e6  mov     r14, rsi
0x1c000d0e9  cmp     rdi, [rbx+1E8h]
0x1c000d0f0  jnz     loc_1C000D1C1
0x1c000d0f6  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c000d0fc  test    al, al
0x1c000d0fe  js      loc_1C0023350
0x1c000d104  cmp     byte ptr [rbx+19Ch], 0
0x1c000d10b  jnz     short loc_1C000D123
0x1c000d10d  lea     r8, [rbp+57h+var_68]
0x1c000d111  xor     edx, edx
0x1c000d113  mov     rcx, rbx
0x1c000d116  call    UlpParseNextRequest
0x1c000d11b  test    eax, eax
0x1c000d11d  js      loc_1C0023367
0x1c000d123  xor     edx, edx
0x1c000d125  lea     rcx, [rbx+1D0h]
0x1c000d12c  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c000d133  nop     dword ptr [rax+rax+00h]
0x1c000d138  call    cs:__imp_KeLeaveCriticalRegion
0x1c000d13f  nop     dword ptr [rax+rax+00h]
0x1c000d144  mov     rcx, [rbp+57h+var_68]
0x1c000d148  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c000d14e  test    al, al
0x1c000d150  js      loc_1C0023383
0x1c000d156  lea     rax, [rbp+57h+var_68]
0x1c000d15a  cmp     rcx, rax
0x1c000d15d  jnz     loc_1C000D2FB
0x1c000d163  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c000d169  test    al, al
0x1c000d16b  js      loc_1C002339E
0x1c000d171  test    dword ptr cs:WPP_MAIN_CB.Queue, 2000h
0x1c000d17b  jnz     loc_1C00233B5
0x1c000d181  mov     r15, [rsp+0A0h+var_20]
0x1c000d189  mov     r14, [rsp+0A0h+var_18]
0x1c000d191  mov     r13, [rsp+0A0h+arg_18]
0x1c000d199  mov     r12, [rsp+0A0h+arg_10]
0x1c000d1a1  mov     rsi, [rsp+0A0h+arg_8]
0x1c000d1a9  mov     rcx, [rbp+57h+var_28]
0x1c000d1ad  xor     rcx, rsp; StackCookie
0x1c000d1b0  call    __security_check_cookie
0x1c000d1b5  add     rsp, 90h
0x1c000d1bc  pop     rdi
0x1c000d1bd  pop     rbx
0x1c000d1be  pop     rbp
0x1c000d1bf  retn
0x1c000d1c1  mov     rsi, [rsi]
0x1c000d1c4  mov     r12, [rbx+3C0h]
0x1c000d1cb  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c000d1d1  test    al, al
0x1c000d1d3  js      loc_1C0023268
0x1c000d1d9  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+4
0x1c000d1df  test    al, al
0x1c000d1e1  js      loc_1C0023285
0x1c000d1e7  mov     rax, [r14]
0x1c000d1ea  test    rax, rax
0x1c000d1ed  jz      short loc_1C000D216
0x1c000d1ef  cmp     [rax+8], r14
0x1c000d1f3  jnz     loc_1C000D309
0x1c000d1f9  mov     rcx, [r14+8]
0x1c000d1fd  cmp     [rcx], r14
0x1c000d200  jnz     loc_1C000D309
0x1c000d206  mov     [rcx], rax
0x1c000d209  mov     [rax+8], rcx
0x1c000d20d  xor     eax, eax
0x1c000d20f  mov     [r14], rax
0x1c000d212  mov     [rdi+28h], rax
0x1c000d216  cmp     byte ptr [r12+4Fh], 0
0x1c000d21c  jz      short loc_1C000D22C
0x1c000d21e  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1c000d224  test    eax, eax
0x1c000d226  jnz     loc_1C00232A3
0x1c000d22c  mov     eax, 0FFFFFFFFh
0x1c000d231  lock xadd [rdi+14h], eax
0x1c000d236  cmp     eax, 1
0x1c000d239  jnz     loc_1C000D2DF
0x1c000d23f  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c000d245  test    al, al
0x1c000d247  js      loc_1C00232C6
0x1c000d24d  mov     eax, [rdi+7Ch]
0x1c000d250  test    al, 1
0x1c000d252  jz      loc_1C000D66E
0x1c000d258  mov     dword ptr [rdi+10h], 50524C75h
0x1c000d25f  cmp     cs:UxCompactMode, 0
0x1c000d266  jnz     loc_1C00232E0
0x1c000d26c  mov     eax, gs:1A4h
0x1c000d274  mov     r8, cs:UlLookaside
0x1c000d27b  lea     edx, [rax+1]
0x1c000d27e  mov     ecx, [r8]
0x1c000d281  cmp     edx, ecx
0x1c000d283  lea     eax, [rcx-1]
0x1c000d286  cmovb   eax, edx
0x1c000d289  mov     ecx, eax
0x1c000d28b  mov     rax, [r8+20h]
0x1c000d28f  mov     r14, [rax+rcx*8]
0x1c000d293  cmp     byte ptr [r14+70h], 0
0x1c000d298  jnz     short loc_1C000D2A5
0x1c000d29a  mov     rcx, r8
0x1c000d29d  mov     rdx, r14
0x1c000d2a0  call    PplpLazyInitializeLookasideList
0x1c000d2a5  inc     dword ptr [r14+1Ch]
0x1c000d2a9  mov     rcx, r14; SListHead
0x1c000d2ac  call    cs:__imp_ExQueryDepthSList
0x1c000d2b3  nop     dword ptr [rax+rax+00h]
0x1c000d2b8  cmp     ax, [r14+10h]
0x1c000d2bd  jnb     short loc_1C000D310
0x1c000d2bf  mov     rdx, rdi; ListEntry
0x1c000d2c2  mov     rcx, r14; ListHead
0x1c000d2c5  call    cs:__imp_ExpInterlockedPushEntrySList
0x1c000d2cc  nop     dword ptr [rax+rax+00h]
0x1c000d2d1  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c000d2d7  test    al, al
0x1c000d2d9  js      loc_1C0023322
0x1c000d2df  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c000d2e5  test    al, al
0x1c000d2e7  js      loc_1C0023339
0x1c000d2ed  cmp     rsi, r15
0x1c000d2f0  jnz     loc_1C000D0E2
0x1c000d2f6  jmp     loc_1C000D0F6
0x1c000d2fb  lea     rax, [rbp+57h+var_68]
0x1c000d2ff  cmp     [rcx+8], rax
0x1c000d303  jz      loc_1C000D591
0x1c000d309  mov     ecx, 3
0x1c000d30e  int     29h; Win8: RtlFailFast(ecx)
0x1c000d310  inc     dword ptr [r14+20h]
0x1c000d314  mov     rdx, r14
0x1c000d317  mov     rax, [r14+38h]
0x1c000d31b  mov     rcx, rdi
0x1c000d31e  call    cs:__guard_dispatch_icall_fptr
0x1c000d324  jmp     short loc_1C000D2D1
0x1c000d326  bts     eax, 8
0x1c000d32a  xor     r8d, r8d
0x1c000d32d  xor     edx, edx
0x1c000d32f  mov     [rdi+888h], eax
0x1c000d335  mov     rcx, rdi
0x1c000d338  call    UlProcessBufferQueue
0x1c000d33d  cmp     dword ptr [rdi+1E0h], 0Ah
0x1c000d344  jnz     loc_1C002305F
0x1c000d34a  or      dword ptr [rdi+888h], 4000h
0x1c000d354  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c000d35a  test    al, al
0x1c000d35c  js      loc_1C0022DA9
0x1c000d362  mov     rdi, [rbx+1C8h]
0x1c000d369  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c000d36f  test    al, al
0x1c000d371  js      loc_1C0022DC7
0x1c000d377  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c000d37d  test    al, al
0x1c000d37f  js      loc_1C0022DEF
0x1c000d385  mov     eax, [rdi+888h]
0x1c000d38b  bts     eax, 0Ah
0x1c000d38f  mov     [rdi+888h], eax
0x1c000d395  bt      eax, 0Eh
0x1c000d399  jnb     loc_1C0022E17
0x1c000d39f  btr     eax, 0Eh
0x1c000d3a3  lea     rsi, [rdi+1E8h]
0x1c000d3aa  mov     [rdi+888h], eax
0x1c000d3b0  mov     rax, [rsi]
0x1c000d3b3  cmp     rax, rsi
0x1c000d3b6  jnz     loc_1C0022E48
0x1c000d3bc  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c000d3c2  test    al, al
0x1c000d3c4  js      loc_1C0022EFF
0x1c000d3ca  cmp     qword ptr [rdi+40h], 0
0x1c000d3cf  jz      short loc_1C000D414
0x1c000d3d1  mov     rax, [rdi+18h]
0x1c000d3d5  mov     rcx, [rax+3C0h]
0x1c000d3dc  cmp     byte ptr [rcx+4Fh], 0
0x1c000d3e0  jz      short loc_1C000D3F0
0x1c000d3e2  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1c000d3e8  test    eax, eax
0x1c000d3ea  jnz     loc_1C0022F16
0x1c000d3f0  mov     rcx, [rdi+40h]
0x1c000d3f4  call    UxFreeOpaqueIdEx
0x1c000d3f9  mov     eax, 0FFFFFFFFh
0x1c000d3fe  mov     qword ptr [rdi+40h], 0
0x1c000d406  lock xadd [rdi+30h], eax
0x1c000d40b  cmp     eax, 1
0x1c000d40e  jz      loc_1C0022F2A
0x1c000d414  mov     rcx, rdi
0x1c000d417  call    UlUnlinkRequestFromRequestQueue
0x1c000d41c  mov     eax, 0FFFFFFFFh
0x1c000d421  lock xadd [rdi+30h], eax
0x1c000d426  cmp     eax, 1
0x1c000d429  jz      loc_1C0022F38
0x1c000d42f  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c000d435  test    al, al
0x1c000d437  js      loc_1C0022F46
0x1c000d43d  and     dword ptr [rbx+208h], 0FFFFFFFBh
0x1c000d444  mov     qword ptr [rbx+1C8h], 0
0x1c000d44f  test    dword ptr cs:WPP_MAIN_CB.Queue+4, 2000h
0x1c000d459  jnz     loc_1C0022F5D
  ... truncated ...
```
