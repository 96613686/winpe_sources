# NtfsFspDispatch

- ea: `0x140015d10`
- end: `0x140016848`
- name: `NtfsFspDispatch`
- size: `2872`
- prototype: `KSTART_ROUTINE`
- caller_count: `1`
- callee_count: `34`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x140297d20`

## callees

- `0x14000549c`
- `0x1400054e8`
- `0x140007ea0`
- `0x1400082b0`
- `0x140015d10`
- `0x140016ea0`
- `0x140017480`
- `0x1400177d0`
- `0x1400291f0`
- `0x140029d80`
- `0x14002c840`
- `0x140059250`
- `0x140059370`
- `0x1400596c0`
- `0x1400bc850`
- `0x1400e2e10`
- `0x140113a30`
- `0x14013ad80`
- `0x140179c20`
- `0x14017a590`
- `0x14017aac0`
- `0x14017ba20`
- `0x14017cdf0`
- `0x14017d1c0`
- `0x1401a0dd0`
- `0x1401a2cb0`
- `0x1401a7710`
- `0x1401aae60`
- `0x1401c3700`
- `0x1401f5650`
- `0x140202288`
- `0x14021c680`
- `0x140228b38`
- `0x14026f774`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140016650`
- `ntoskrnl!KeSetEvent` at `0x140016650`
- `ntoskrnl!ObfDereferenceObject` at `0x140016585`
- `ntoskrnl!ObfDereferenceObject` at `0x140016585`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140015e5a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140015e5a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001649b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001649b`
- `ntoskrnl!KeBugCheckEx` at `0x1400161e0`
- `ntoskrnl!KeBugCheckEx` at `0x1400161e0`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140015f43`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140015f43`
- `ntoskrnl!IoSetActivityIdThread` at `0x1400165e5`
- `ntoskrnl!IoSetActivityIdThread` at `0x1400165e5`
- `ntoskrnl!IoClearActivityIdThread` at `0x14001648f`
- `ntoskrnl!IoClearActivityIdThread` at `0x14001648f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400164cb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005e412`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400164cb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005e412`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016575`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001662f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005e3c8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005e403`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016575`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001662f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005e3c8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005e403`
- `ntoskrnl!IoGetIoPriorityHint` at `0x140015eed`
- `ntoskrnl!IoGetIoPriorityHint` at `0x140015eed`
- `ntoskrnl!ObfReferenceObject` at `0x140015e1b`
- `ntoskrnl!ObfReferenceObject` at `0x140015e1b`
- `ntoskrnl!IoRetrievePriorityInfo` at `0x140015ed1`
- `ntoskrnl!IoRetrievePriorityInfo` at `0x140015ed1`
- `ntoskrnl!IoSetIoPriorityHintIntoThread` at `0x140015efe`
- `ntoskrnl!IoSetIoPriorityHintIntoThread` at `0x140015efe`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x140015fb3`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x140016406`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x140015fb3`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x140016406`
- `ntoskrnl!CcErrorCallbackRoutine` at `0x140016195`
- `ntoskrnl!CcErrorCallbackRoutine` at `0x140016195`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x140016468`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x140016468`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400166ce`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14005e3a6`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400166ce`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14005e3a6`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400166f3`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140016827`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005e3f0`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400166f3`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140016827`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005e3f0`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400167c4`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400167c4`
- `ntoskrnl!KeInitializeEvent` at `0x140016208`
- `ntoskrnl!KeInitializeEvent` at `0x140016208`

## pseudocode

```c
void __fastcall NtfsFspDispatch(LARGE_INTEGER *StartContext)
{
  __int64 v2; // rcx
  void *v3; // rdi
  LARGE_INTEGER v4; // rbx
  LONG HighPart; // eax
  char v6; // r8
  __int64 v7; // r13
  struct _KTHREAD *CurrentThread; // rdi
  IO_PRIORITY_HINT IoPriorityHint; // eax
  LONG v10; // esi
  __int64 v11; // rdx
  int v12; // edx
  int LowPart; // edx
  unsigned int v14; // edx
  unsigned int v15; // esi
  __int64 v16; // rcx
  __int64 v17; // r9
  _BYTE *v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // r14
  __int64 v21; // rsi
  __int16 v22; // di
  __int64 v23; // r8
  char v24; // al
  bool v25; // zf
  KSPIN_LOCK *v26; // r14
  KSPIN_LOCK *v27; // rdi
  KIRQL v28; // si
  KSPIN_LOCK *v29; // r13
  KSPIN_LOCK *v30; // r8
  _DWORD *v31; // rdx
  int v32; // eax
  _QWORD *v33; // r14
  _DWORD *v34; // rcx
  _DWORD *v35; // r13
  _QWORD *QuadPart; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  _QWORD *v39; // rax
  unsigned int v40; // ecx
  unsigned int v41; // r10d
  void (__fastcall *v42)(_QWORD, LARGE_INTEGER); // r14
  KIRQL v43; // cl
  _BYTE v44[48]; // [rsp+10h] [rbp-60h] BYREF
  ULONG_PTR BugCheckParameter4; // [rsp+60h] [rbp-10h]
  int v46; // [rsp+68h] [rbp-8h]
  char v47; // [rsp+70h] [rbp+0h]
  KIRQL Irql; // [rsp+71h] [rbp+1h] BYREF
  char v49; // [rsp+72h] [rbp+2h]
  char v50; // [rsp+73h] [rbp+3h]
  char v51; // [rsp+74h] [rbp+4h]
  bool v52; // [rsp+75h] [rbp+5h]
  unsigned int v53; // [rsp+78h] [rbp+8h]
  unsigned int v54; // [rsp+7Ch] [rbp+Ch]
  unsigned int v55; // [rsp+80h] [rbp+10h]
  int v56; // [rsp+84h] [rbp+14h]
  int v57; // [rsp+88h] [rbp+18h]
  int v58; // [rsp+90h] [rbp+20h] BYREF
  unsigned int v59; // [rsp+94h] [rbp+24h]
  ULONG_PTR BugCheckParameter2; // [rsp+98h] [rbp+28h]
  __int64 v61; // [rsp+A0h] [rbp+30h]
  _BYTE *v62; // [rsp+A8h] [rbp+38h]
  _DWORD *v63; // [rsp+B0h] [rbp+40h]
  KSPIN_LOCK *v64; // [rsp+B8h] [rbp+48h]
  PVOID Object; // [rsp+C0h] [rbp+50h]
  _DWORD *v66; // [rsp+C8h] [rbp+58h]
  int v67; // [rsp+D0h] [rbp+60h]
  _BYTE *v68; // [rsp+D8h] [rbp+68h]
  LARGE_INTEGER v69; // [rsp+E8h] [rbp+78h]
  struct _KEVENT Event; // [rsp+F8h] [rbp+88h] BYREF
  _OWORD v71[2]; // [rsp+110h] [rbp+A0h] BYREF
  __int64 v72; // [rsp+130h] [rbp+C0h]
  __int128 v73; // [rsp+138h] [rbp+C8h] BYREF
  __int64 v74; // [rsp+148h] [rbp+D8h]
  _IO_PRIORITY_INFO PriorityInfo; // [rsp+150h] [rbp+E0h] BYREF

  memset(v71, 0, sizeof(v71));
  v72 = 0;
  v2 = 0;
  v56 = 0;
  v54 = 0;
  v55 = 0;
  v3 = 0;
  Object = 0;
  v52 = 0;
  v53 = 0;
  memset(&Event, 0, sizeof(Event));
  v51 = 0;
  PriorityInfo = 0;
  LOWORD(v59) = 0;
  v58 = 0;
  v62 = 0;
  v68 = 0;
  BugCheckParameter2 = (ULONG_PTR)StartContext;
  StartContext[22].QuadPart = (LONGLONG)&StartContext[21];
  StartContext[21].QuadPart = (LONGLONG)&StartContext[21];
  StartContext[20].QuadPart = (LONGLONG)&StartContext[19];
  StartContext[19].QuadPart = (LONGLONG)&StartContext[19];
  v4 = StartContext[14];
  v69 = v4;
  if ( v4.QuadPart )
    v2 = *(_QWORD *)(v4.QuadPart + 184);
  HighPart = StartContext->HighPart;
  v57 = HighPart & 0x4000000;
  v67 = HighPart & 0x4000000;
  v6 = HighPart & 1;
  v47 = HighPart & 1;
  StartContext->HighPart = HighPart & 0xFFFFFFFE;
  StartContext[1].HighPart |= 1u;
  if ( (HighPart & 0x4000000) == 0 )
  {
    if ( v4.QuadPart && *(_QWORD *)(v2 + 48) )
    {
      v3 = *(void **)(v2 + 40);
      Object = v3;
      ObfReferenceObject(v3);
      v6 = v47;
    }
    else
    {
      Object = 0;
    }
    v52 = (StartContext->HighPart & 0x400000) != 0;
  }
  v64 = (KSPIN_LOCK *)v3;
  v50 = v6;
  while ( 2 )
  {
    v73 = 0;
    v74 = 0;
    KeEnterCriticalRegion();
    if ( (StartContext[2].LowPart & 0x100LL) != 0 )
    {
      v61 = 0;
      Irql = 0;
    }
    else
    {
      Irql = 1;
      QuadPart = (_QWORD *)StartContext[15].QuadPart;
      if ( QuadPart )
      {
        *((_QWORD *)&v73 + 1) = *QuadPart;
        v74 = QuadPart[1];
        *(_QWORD *)&v73 = (char *)&v73 + 8;
      }
      else
      {
        *(_QWORD *)&v73 = 0;
      }
      v61 = IoSetActivityIdThread(v73);
      if ( (Microsoft_Windows_NtfsEnableBits & 0x8000000) != 0 )
      {
        LODWORD(BugCheckParameter4) = 0;
        McTemplateK0pq_EtwWriteTransfer(v37, WORKITEM_START, v73);
      }
    }
    v7 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))NtfsInitializeTopLevelIrp)(
           v71,
           3,
           (LARGE_INTEGER)StartContext[13].QuadPart);
    v66 = (_DWORD *)v7;
    if ( v4.QuadPart )
    {
      PriorityInfo.Size = 16;
      *(_QWORD *)&PriorityInfo.ThreadPriority = 0xFFFF;
      PriorityInfo.IoPriority = IoPriorityNormal;
      if ( IoRetrievePriorityInfo(0, 0, KeGetCurrentThread(), &PriorityInfo) >= 0 )
      {
        CurrentThread = KeGetCurrentThread();
        IoPriorityHint = IoGetIoPriorityHint((PIRP)v4.QuadPart);
        IoSetIoPriorityHintIntoThread(CurrentThread, (unsigned int)IoPriorityHint);
        v51 = 1;
      }
      v53 = 0;
    }
    ++NtfsPostRequests;
    do
    {
      v10 = StartContext[54].HighPart;
      v11 = *(_QWORD *)(v7 + 32);
      if ( v11 )
      {
        v12 = *(_DWORD *)(v11 + 436);
      }
      else
      {
        *(_DWORD *)(v7 + 4) = 1397118030;
        *(_QWORD *)(v7 + 32) = StartContext;
        StartContext[1].HighPart |= 0x100000u;
        IoSetTopLevelIrp((PIRP)v7);
        if ( !*(_BYTE *)(v7 + 1) )
        {
          LowPart = StartContext[54].LowPart;
          goto LABEL_20;
        }
        v12 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v7 + 24) + 32LL) + 436LL);
      }
      LowPart = StartContext[54].LowPart | v12;
LABEL_20:
      v14 = LowPart & 0xFFFFFBFF;
      StartContext[54].LowPart = v14;
      StartContext[54].HighPart |= v14;
      StartContext[18] = *(LARGE_INTEGER *)(v7 + 32);
      StartContext[54].HighPart = v10;
      v49 = 0;
      StartContext[3].LowPart = 0;
      StartContext[1].HighPart |= 0x40u;
      if ( StartContext[25].QuadPart )
      {
        NtfsCheckpointForLogFileFull(StartContext);
        if ( (unsigned int)++v56 >= 2 )
          StartContext->HighPart |= 0x10u;
      }
      v15 = v53;
      if ( (unsigned __int8)CcIsCacheManagerCallbackNeeded(v53) )
      {
        v58 = 8;
        v59 = v15;
        CcErrorCallbackRoutine(&v58);
      }
      NtfsPreRequestProcessingExtend((_DWORD)StartContext);
      if ( !v4.QuadPart )
      {
        LOBYTE(v17) = 1;
        NtfsExtendedCompleteRequestInternal(StartContext, 0, 0, v17, 1);
        StartContext = 0;
        BugCheckParameter2 = 0;
LABEL_62:
        v24 = v49;
        continue;
      }
      if ( LOBYTE(StartContext[4].LowPart) == 4 )
      {
        v18 = v62;
        if ( !v62 )
        {
          v18 = v44;
          v62 = v44;
          v68 = v44;
        }
        NtfsCommonWrite(StartContext, (PIRP)v4.QuadPart, (LARGE_INTEGER)v18);
        goto LABEL_62;
      }
      switch ( LOBYTE(StartContext[4].LowPart) )
      {
        case 0:
          StartContext[1].HighPart &= ~2u;
          if ( (StartContext[1].HighPart & 0x200) != 0 )
          {
            v53 = NtfsCommonVolumeOpen((_DWORD)StartContext);
          }
          else
          {
            v20 = StartContext[26].QuadPart;
            v21 = *(_QWORD *)(v20 + 184);
            v22 = *(_WORD *)(v20 + 70);
            memset((void *)v20, 0, 0xF0u);
            *(_QWORD *)(v20 + 184) = v21;
            *(_WORD *)(v20 + 70) = v22;
            *(_QWORD *)(v20 + 176) = *(_QWORD *)(v4.QuadPart + 184);
            v53 = NtfsCommonCreate((__int64)StartContext, (PIRP)v4.QuadPart, v20);
          }
          goto LABEL_62;
        case 2:
          if ( (StartContext[2].LowPart & 0x100000) == 0
            && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x800) != 0 )
          {
            McTemplateU0_EtwWriteTransfer(v16, fspdisp_c402);
          }
          KeBugCheckEx(0x24u, 0xB200130196uLL, 0, 0, 0);
        case 3:
          if ( !v62 )
          {
            v62 = v44;
            v68 = v44;
          }
          NtfsCommonRead((int)StartContext, v4.LowPart);
          goto LABEL_62;
        case 5:
          NtfsCommonQueryInformation((_DWORD)StartContext);
          goto LABEL_62;
        case 6:
          KeInitializeEvent(&Event, NotificationEvent, 0);
          StartContext[27].QuadPart = (LONGLONG)&Event;
          v53 = NtfsCommonSetInformation((int)StartContext, (PIRP)v4.QuadPart);
          if ( v53 != 871 )
            goto LABEL_62;
          v46 = 0;
          ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))NtfsWaitForOplockCompletionEvent)(
            v19,
            (LARGE_INTEGER)v4.QuadPart,
            v23,
            &Event);
          v24 = 1;
          v49 = 1;
          break;
        case 7:
          ((void (__fastcall *)(_QWORD, _QWORD))NtfsCommonQueryEa)(StartContext, (LARGE_INTEGER)v4.QuadPart);
          goto LABEL_62;
        case 8:
          NtfsCommonSetEa(StartContext);
          goto LABEL_62;
        case 9:
          NtfsCommonFlushBuffers((__int64)StartContext, (IRP *)v4.QuadPart);
          goto LABEL_62;
        case 0xA:
          ((void (__fastcall *)(_QWORD, _QWORD))NtfsCommonQueryVolumeInfo)(StartContext, (LARGE_INTEGER)v4.QuadPart);
          goto LABEL_62;
        case 0xB:
          ((void (__fastcall *)(_QWORD, _QWORD))NtfsCommonSetVolumeInfo)(StartContext, (LARGE_INTEGER)v4.QuadPart);
          goto LABEL_62;
        case 0xC:
          NtfsCommonDirectoryControl(StartContext, v4.LowPart);
          goto LABEL_62;
        case 0xD:
          NtfsCommonFileSystemControl((_DWORD)StartContext);
          goto LABEL_62;
        case 0xE:
          NtfsCommonDeviceControl((int)StartContext);
          goto LABEL_62;
        case 0x11:
          NtfsCommonLockControl(StartContext, (PIRP)v4.QuadPart);
          goto LABEL_62;
        case 0x12:
          NtfsCommonCleanup((__int64)StartContext, (IRP *)v4.QuadPart);
          goto LABEL_62;
        case 0x14:
          ((void (__fastcall *)(_QWORD, _QWORD))NtfsCommonQuerySecurityInfo)(StartContext, (LARGE_INTEGER)v4.QuadPart);
          goto LABEL_62;
        case 0x15:
          NtfsCommonSetSecurityInfo((_DWORD)StartContext);
          goto LABEL_62;
        case 0x19:
          NtfsCommonQueryQuota((_DWORD)StartContext);
          goto LABEL_62;
        case 0x1A:
          NtfsCommonSetQuota(StartContext);
          goto LABEL_62;
        default:
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(StartContext, 3221225488LL, 1245816);
          LOBYTE(v17) = 1;
          ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))NtfsExtendedCompleteRequestInternal)(
            StartContext,
            (LARGE_INTEGER)v4.QuadPart,
            3221225488LL,
            v17,
            0);
          goto LABEL_62;
      }
    }
    while ( v24 );
    if ( v51 )
    {
      IoApplyPriorityInfoThread(&PriorityInfo, 0, KeGetCurrentThread());
      v51 = 0;
    }
    if ( Irql )
    {
      if ( (Microsoft_Windows_NtfsEnableBits & 0x8000000) != 0 )
        McTemplateK0pq_EtwWriteTransfer(v19, WORKITEM_COMPLETE, v73);
      IoClearActivityIdThread(v61);
    }
    KeLeaveCriticalRegion();
    v25 = v57 == 0;
    if ( v57 )
      goto LABEL_97;
    if ( Object )
    {
      v26 = v64;
      v27 = v64 + 717;
      v28 = KeAcquireSpinLockRaiseToDpc(v64 + 717);
      if ( v47 )
        --*((_DWORD *)v26 + 1409);
      v29 = v26;
      v30 = v26;
      v31 = v26 + 711;
      v61 = (__int64)(v26 + 711);
      while ( 2 )
      {
        v32 = *((_DWORD *)v29 + 1410);
        if ( !v32 )
        {
          v33 = 0;
          if ( !*v31 )
          {
            v35 = 0;
            goto LABEL_85;
          }
          v26 = v29;
        }
        if ( !*v31 )
        {
LABEL_79:
          v54 = 0;
          v55 = 0;
          v47 = 0;
          v50 = 0;
          if ( v32 )
          {
            v66 = (_DWORD *)v30 + 1409;
            goto LABEL_81;
          }
          v35 = 0;
LABEL_84:
          v33 = 0;
          goto LABEL_85;
        }
        v66 = (_DWORD *)v26 + 1409;
        v40 = *((_DWORD *)v26 + 1409);
        if ( v40 >= 3 )
        {
          v30 = v29;
          goto LABEL_79;
        }
        v41 = v54 + 1;
        v54 = v41;
        if ( v41 <= 0x14 && v32 )
        {
          v55 = v41;
          v47 = 0;
          v50 = 0;
LABEL_81:
          v34 = v29 + 705;
          v63 = v29 + 705;
        }
        else
        {
          v54 = 0;
          v55 = 0;
          *((_DWORD *)v26 + 1409) = v40 + 1;
          v47 = 1;
          v50 = 1;
          v34 = v31;
          v63 = v31;
        }
        if ( !v34 )
        {
          v35 = v63;
          goto LABEL_84;
        }
        v33 = (_QWORD *)*((_QWORD *)v34 + 4);
        StartContext = (LARGE_INTEGER *)(v33 - 19);
        BugCheckParameter2 = (ULONG_PTR)(v33 - 19);
        v69 = (LARGE_INTEGER)*(v33 - 5);
        v4 = v69;
        Irql = 0;
        IoAcquireCancelSpinLock(&Irql);
        if ( *(_BYTE *)(v4.QuadPart + 68) )
        {
          IoReleaseCancelSpinLock(Irql);
          if ( v47 )
            --*v66;
          IoAcquireCancelSpinLock((PKIRQL)(v4.QuadPart + 69));
          v42 = (void (__fastcall *)(_QWORD, LARGE_INTEGER))_InterlockedExchange64(
                                                              (volatile __int64 *)(v4.QuadPart + 104),
                                                              0);
          v43 = *(_BYTE *)(v4.QuadPart + 69);
          if ( v42 )
          {
            KeReleaseSpinLock(v27, v43);
            *(_BYTE *)(v4.QuadPart + 69) = v28;
            ((void (__fastcall *)(_QWORD, _QWORD))v42)(
              *(_QWORD *)(*(_QWORD *)(v4.QuadPart + 184) + 40LL),
              (LARGE_INTEGER)v4.QuadPart);
          }
          else
          {
            IoReleaseCancelSpinLock(v43);
            KeReleaseSpinLock(v27, v28);
          }
          v28 = KeAcquireSpinLockRaiseToDpc(v27);
          v31 = (_DWORD *)v61;
          v26 = v29;
          v30 = v29;
          continue;
        }
        break;
      }
      *(_QWORD *)(v4.QuadPart + 56) = 0;
      _InterlockedExchange64((volatile __int64 *)(v4.QuadPart + 104), 0);
      IoReleaseCancelSpinLock(Irql);
      v35 = v63;
      --*v63;
      v38 = *v33;
      if ( *(_QWORD **)(*v33 + 8LL) != v33 || (v39 = (_QWORD *)v33[1], (_QWORD *)*v39 != v33) )
        __fastfail(3u);
      *v39 = v38;
      *(_QWORD *)(v38 + 8) = v39;
      StartContext[22].QuadPart = (LONGLONG)&StartContext[21];
      StartContext[21].QuadPart = (LONGLONG)&StartContext[21];
      StartContext[20].QuadPart = (LONGLONG)v33;
      *v33 = v33;
LABEL_85:
      if ( !v33 )
      {
        --*((_DWORD *)v64 + 1408);
        KeReleaseSpinLock(v27, v28);
        ObfDereferenceObject(Object);
        return;
      }
      KeReleaseSpinLock(v27, v28);
      if ( *v35 < (unsigned int)dword_140095AC0 )
        KeSetEvent((PRKEVENT)(v35 + 2), 0, 0);
      v56 = 0;
      StartContext[1].HighPart |= 1u;
      v25 = v57 == 0;
LABEL_97:
      if ( !v25 )
        return;
      continue;
    }
    break;
  }
  if ( v52 )
    KeReleaseSemaphore(&NtfsGlobalPostThrottle, 0, 1, 0);
}

```

## disassembly

```asm
0x140015d10  push    rbp
0x140015d12  push    rbx
0x140015d13  push    rsi
0x140015d14  push    rdi
0x140015d15  push    r12
0x140015d17  push    r13
0x140015d19  push    r14
0x140015d1b  push    r15
0x140015d1d  sub     rsp, 138h
0x140015d24  lea     rbp, [rsp+30h]
0x140015d29  mov     rax, cs:__security_cookie
0x140015d30  xor     rax, rbp
0x140015d33  mov     [rbp+140h+var_50], rax
0x140015d3a  mov     r15, rcx
0x140015d3d  xorps   xmm0, xmm0
0x140015d40  xor     eax, eax
0x140015d42  movups  [rbp+140h+var_A0], xmm0
0x140015d49  movups  [rbp+140h+var_90], xmm0
0x140015d50  mov     [rbp+140h+var_80], rax
0x140015d57  xor     r12d, r12d
0x140015d5a  mov     ecx, r12d
0x140015d5d  mov     [rbp+140h+var_12C], r12d
0x140015d61  mov     [rbp+140h+var_134], eax
0x140015d64  mov     [rbp+140h+var_130], eax
0x140015d67  mov     edi, r12d
0x140015d6a  mov     [rbp+140h+Object], r12
0x140015d6e  mov     [rbp+140h+var_13B], al
0x140015d71  mov     [rbp+140h+var_138], r12d
0x140015d75  movups  xmmword ptr [rbp+140h+Event.Header], xmm0
0x140015d7c  mov     [rbp+140h+Event.Header.WaitListHead.Blink], rax
0x140015d83  mov     [rbp+140h+var_13C], al
0x140015d86  movups  xmmword ptr [rbp+140h+PriorityInfo.Size], xmm0
0x140015d8d  mov     dword ptr [rbp+140h+var_120+2], eax
0x140015d90  mov     dword ptr [rbp+140h+var_120], eax
0x140015d93  mov     [rbp+140h+var_108], rax
0x140015d97  mov     [rbp+140h+var_D8], rax
0x140015d9b  mov     [rbp+140h+BugCheckParameter2], r15
0x140015d9f  lea     rax, [r15+0A8h]
0x140015da6  mov     [rax+8], rax
0x140015daa  mov     [rax], rax
0x140015dad  lea     rax, [r15+98h]
0x140015db4  mov     [rax+8], rax
0x140015db8  mov     [rax], rax
0x140015dbb  mov     rbx, [r15+70h]
0x140015dbf  mov     [rbp+140h+var_C8], rbx
0x140015dc3  test    rbx, rbx
0x140015dc6  jz      short loc_140015DCF
0x140015dc8  mov     rcx, [rbx+0B8h]
0x140015dcf  mov     eax, [r15+4]
0x140015dd3  mov     edx, eax
0x140015dd5  and     edx, 4000000h
0x140015ddb  mov     [rbp+140h+var_128], edx
0x140015dde  mov     [rbp+140h+var_E0], edx
0x140015de1  movzx   r8d, al
0x140015de5  and     r8b, 1
0x140015de9  mov     [rbp+140h+var_140], r8b
0x140015ded  and     eax, 0FFFFFFFEh
0x140015df0  mov     [r15+4], eax
0x140015df4  or      dword ptr [r15+0Ch], 1
0x140015df9  test    edx, edx
0x140015dfb  jnz     short loc_140015E38
0x140015dfd  test    rbx, rbx
0x140015e00  jz      loc_1400167E4
0x140015e06  cmp     [rcx+30h], r12
0x140015e0a  jz      loc_1400167E4
0x140015e10  mov     rdi, [rcx+28h]
0x140015e14  mov     [rbp+140h+Object], rdi
0x140015e18  mov     rcx, rdi; Object
0x140015e1b  call    cs:__imp_ObfReferenceObject
0x140015e22  nop     dword ptr [rax+rax+00h]
0x140015e27  movzx   r8d, [rbp+140h+var_140]
0x140015e2c  mov     eax, [r15+4]
0x140015e30  shr     eax, 16h
0x140015e33  and     al, 1
0x140015e35  mov     [rbp+140h+var_13B], al
0x140015e38  mov     [rbp+140h+var_F8], rdi
0x140015e3c  mov     [rbp+140h+var_13D], r8b
0x140015e40  lea     r14, cs:140000000h
0x140015e47  xorps   xmm0, xmm0
0x140015e4a  xor     eax, eax
0x140015e4c  movups  [rbp+140h+var_78], xmm0
0x140015e53  mov     [rbp+140h+var_68], rax
0x140015e5a  call    cs:__imp_KeEnterCriticalRegion
0x140015e61  nop     dword ptr [rax+rax+00h]
0x140015e66  mov     eax, [r15+10h]
0x140015e6a  bt      rax, 8
0x140015e6f  jnb     loc_1400165BF
0x140015e75  mov     [rbp+140h+var_110], r12
0x140015e79  mov     [rbp+140h+Irql], 0
0x140015e7d  mov     r8, [r15+68h]
0x140015e81  mov     edx, 3
0x140015e86  lea     rcx, [rbp+140h+var_A0]
0x140015e8d  call    NtfsInitializeTopLevelIrp
0x140015e92  mov     r13, rax
0x140015e95  mov     [rbp+140h+var_E8], rax
0x140015e99  test    rbx, rbx
0x140015e9c  jz      short loc_140015F12
0x140015e9e  mov     [rbp+140h+PriorityInfo.Size], 10h
0x140015ea8  mov     qword ptr [rbp+140h+PriorityInfo.ThreadPriority], 0FFFFh
0x140015eb3  mov     [rbp+140h+PriorityInfo.IoPriority], 2
0x140015ebd  mov     r8, gs:188h; Thread
0x140015ec6  lea     r9, [rbp+140h+PriorityInfo]; PriorityInfo
0x140015ecd  xor     edx, edx; FileObject
0x140015ecf  xor     ecx, ecx; Irp
0x140015ed1  call    cs:__imp_IoRetrievePriorityInfo
0x140015ed8  nop     dword ptr [rax+rax+00h]
0x140015edd  test    eax, eax
0x140015edf  js      short loc_140015F0E
0x140015ee1  mov     rdi, gs:188h
0x140015eea  mov     rcx, rbx; Irp
0x140015eed  call    cs:__imp_IoGetIoPriorityHint
0x140015ef4  nop     dword ptr [rax+rax+00h]
0x140015ef9  mov     edx, eax
0x140015efb  mov     rcx, rdi
0x140015efe  call    cs:__imp_IoSetIoPriorityHintIntoThread
0x140015f05  nop     dword ptr [rax+rax+00h]
0x140015f0a  mov     [rbp+140h+var_13C], 1
0x140015f0e  mov     [rbp+140h+var_138], r12d
0x140015f12  inc     cs:NtfsPostRequests
0x140015f18  mov     esi, [r15+1B4h]
0x140015f1f  mov     rdx, [r13+20h]
0x140015f23  test    rdx, rdx
0x140015f26  jnz     loc_1400166A4
0x140015f2c  mov     dword ptr [r13+4], 5346544Eh
0x140015f34  mov     [r13+20h], r15
0x140015f38  or      dword ptr [r15+0Ch], 100000h
0x140015f40  mov     rcx, r13; Irp
0x140015f43  call    cs:__imp_IoSetTopLevelIrp
0x140015f4a  nop     dword ptr [rax+rax+00h]
0x140015f4f  cmp     byte ptr [r13+1], 0
0x140015f54  jz      loc_14001679C
0x140015f5a  mov     rax, [r13+18h]
0x140015f5e  mov     rcx, [rax+20h]
0x140015f62  mov     edx, [rcx+1B4h]
0x140015f68  or      edx, [r15+1B0h]
0x140015f6f  btr     edx, 0Ah
0x140015f73  mov     [r15+1B0h], edx
0x140015f7a  or      [r15+1B4h], edx
0x140015f81  mov     rax, [r13+20h]
0x140015f85  mov     [r15+90h], rax
0x140015f8c  mov     [r15+1B4h], esi
0x140015f93  mov     [rbp+140h+var_13E], 0
0x140015f97  mov     [r15+18h], r12d
0x140015f9b  or      dword ptr [r15+0Ch], 40h
0x140015fa0  cmp     qword ptr [r15+0C8h], 0
0x140015fa8  jnz     loc_14001615E
0x140015fae  mov     esi, [rbp+140h+var_138]
0x140015fb1  mov     ecx, esi
0x140015fb3  call    cs:__imp_CcIsCacheManagerCallbackNeeded
0x140015fba  nop     dword ptr [rax+rax+00h]
0x140015fbf  test    al, al
0x140015fc1  jnz     loc_140016181
0x140015fc7  mov     edx, esi
0x140015fc9  mov     rcx, r15
0x140015fcc  call    NtfsPreRequestProcessingExtend
0x140015fd1  test    rbx, rbx
0x140015fd4  jz      short loc_140016012
0x140015fd6  movzx   eax, byte ptr [r15+20h]
0x140015fdb  cmp     eax, 4
0x140015fde  jnz     short loc_14001603D
0x140015fe0  mov     rcx, [rbp+140h+var_108]
0x140015fe4  test    rcx, rcx
0x140015fe7  jnz     short loc_140015FFF
0x140015fe9  mov     eax, [rsp+170h+var_170]
0x140015fec  sub     rsp, 60h
0x140015ff0  lea     rcx, [rsp+1D0h+var_1A0]
0x140015ff5  mov     [rbp+140h+var_108], rcx
0x140015ff9  mov     eax, [rcx]
0x140015ffb  mov     [rbp+140h+var_D8], rcx
0x140015fff  mov     r8, rcx
0x140016002  mov     rdx, rbx; Irp
0x140016005  mov     rcx, r15; Context
0x140016008  call    NtfsCommonWrite
0x14001600d  jmp     loc_1400162F9
0x140016012  movzx   eax, cs:NtfsStatusDebugFlags
0x140016019  mov     dword ptr [rsp+170h+BugCheckParameter4], 1
0x140016021  mov     r9b, 1
0x140016024  xor     r8d, r8d
0x140016027  xor     edx, edx
0x140016029  mov     rcx, r15
0x14001602c  call    NtfsExtendedCompleteRequestInternal
0x140016031  mov     r15, r12
0x140016034  mov     [rbp+140h+BugCheckParameter2], r12
0x140016038  jmp     loc_1400162F9
0x14001603d  cmp     eax, 1Ah; switch 27 cases
0x140016040  ja      def_140016051; jumptable 0000000140016051 default case, cases 1,4,15,16,19,22-24
0x140016046  mov     ecx, ds:(jpt_140016051 - 140000000h)[r14+rax*4]
0x14001604e  add     rcx, r14
0x140016051  jmp     rcx; switch jump
0x140016057  mov     rdx, rbx; jumptable 0000000140016051 case 13
0x14001605a  mov     rcx, r15
0x14001605d  call    NtfsCommonFileSystemControl
0x140016062  jmp     loc_1400162F9
0x140016067  and     dword ptr [r15+0Ch], 0FFFFFFFDh; jumptable 0000000140016051 case 0
0x14001606c  test    dword ptr [r15+0Ch], 200h
0x140016074  jnz     loc_14001610F
0x14001607a  mov     r14, [r15+0D0h]
0x140016081  mov     rsi, [r14+0B8h]
0x140016088  movzx   edi, word ptr [r14+46h]
0x14001608d  xor     edx, edx; Val
0x14001608f  mov     r8d, 0F0h; Size
0x140016095  mov     rcx, r14; void *
0x140016098  call    memset
0x14001609d  mov     [r14+0B8h], rsi
0x1400160a4  mov     [r14+46h], di
0x1400160a9  mov     rax, [rbx+0B8h]
0x1400160b0  mov     [r14+0B0h], rax
0x1400160b7  mov     r8, r14
0x1400160ba  mov     rdx, rbx; Irp
0x1400160bd  mov     rcx, r15; int
0x1400160c0  call    NtfsCommonCreate
0x1400160c5  mov     [rbp+140h+var_138], eax
0x1400160c8  jmp     loc_1400162F9
0x1400160cd  mov     rdx, rbx; jumptable 0000000140016051 case 12
0x1400160d0  mov     rcx, r15; StartContext
0x1400160d3  call    NtfsCommonDirectoryControl
0x1400160d8  jmp     loc_1400162F9
0x1400160dd  mov     rcx, [rbp+140h+var_108]; jumptable 0000000140016051 case 3
0x1400160e1  test    rcx, rcx
0x1400160e4  jnz     short loc_1400160FC
0x1400160e6  mov     eax, [rsp+170h+var_170]
0x1400160e9  sub     rsp, 60h
0x1400160ed  lea     rcx, [rsp+1D0h+var_1A0]
0x1400160f2  mov     [rbp+140h+var_108], rcx
0x1400160f6  mov     eax, [rcx]
0x1400160f8  mov     [rbp+140h+var_D8], rcx
0x1400160fc  mov     r8, rcx
0x1400160ff  mov     rdx, rbx; int
0x140016102  mov     rcx, r15; int
0x140016105  call    NtfsCommonRead
0x14001610a  jmp     loc_1400162F9
0x14001610f  mov     rdx, rbx
0x140016112  mov     rcx, r15
0x140016115  call    NtfsCommonVolumeOpen
0x14001611a  mov     [rbp+140h+var_138], eax
0x14001611d  jmp     loc_1400162F9
0x140016122  movzx   eax, cs:NtfsStatusDebugFlags; jumptable 0000000140016051 default case, cases 1,4,15,16,19,22-24
0x140016129  test    al, al
0x14001612b  jz      short loc_140016140
0x14001612d  mov     edx, 0C0000010h
0x140016132  mov     r8d, 130278h
0x140016138  mov     rcx, r15
0x14001613b  call    NtfsStatusTraceAndDebugInternal
0x140016140  mov     dword ptr [rsp+170h+BugCheckParameter4], r12d
0x140016145  mov     r9b, 1
0x140016148  mov     r8d, 0C0000010h
0x14001614e  mov     rdx, rbx
0x140016151  mov     rcx, r15
0x140016154  call    NtfsExtendedCompleteRequestInternal
0x140016159  jmp     loc_1400162F9
0x14001615e  mov     rcx, r15
0x140016161  call    NtfsCheckpointForLogFileFull
0x140016166  mov     eax, [rbp+140h+var_12C]
0x140016169  inc     eax
0x14001616b  mov     [rbp+140h+var_12C], eax
0x14001616e  cmp     eax, 2
0x140016171  jb      loc_140015FAE
0x140016177  or      dword ptr [r15+4], 10h
0x14001617c  jmp     loc_140015FAE
0x140016181  mov     [rbp+140h+var_120], r12
0x140016185  mov     eax, 8
0x14001618a  mov     word ptr [rbp+140h+var_120], ax
0x14001618e  mov     dword ptr [rbp+140h+var_120+4], esi
0x140016191  lea     rcx, [rbp+140h+var_120]
0x140016195  call    cs:__imp_CcErrorCallbackRoutine
0x14001619c  nop     dword ptr [rax+rax+00h]
0x1400161a1  jmp     loc_140015FC7
0x1400161a6  mov     eax, [r15+10h]; jumptable 0000000140016051 case 2
0x1400161aa  bt      rax, 14h
0x1400161af  jb      short loc_1400161C6
0x1400161b1  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+1, 8
0x1400161b8  jz      short loc_1400161C6
0x1400161ba  lea     rdx, fspdisp_c402
0x1400161c1  call    McTemplateU0_EtwWriteTransfer
0x1400161c6  mov     [rsp+170h+BugCheckParameter4], r12; BugCheckParameter4
0x1400161cb  xor     r9d, r9d; BugCheckParameter3
0x1400161ce  xor     r8d, r8d; BugCheckParameter2
0x1400161d1  mov     rdx, 0B200130196h; BugCheckParameter1
0x1400161db  mov     ecx, 24h ; '$'; BugCheckCode
0x1400161e0  call    cs:__imp_KeBugCheckEx
0x1400161ec  mov     rdx, rbx; jumptable 0000000140016051 case 5
0x1400161ef  mov     rcx, r15
0x1400161f2  call    NtfsCommonQueryInformation
0x1400161f7  jmp     loc_1400162F9
0x1400161fc  xor     r8d, r8d; jumptable 0000000140016051 case 6
0x1400161ff  xor     edx, edx; Type
0x140016201  lea     rcx, [rbp+140h+Event]; Event
0x140016208  call    cs:__imp_KeInitializeEvent
0x14001620f  nop     dword ptr [rax+rax+00h]
0x140016214  lea     rax, [rbp+140h+Event]
0x14001621b  mov     [r15+0D8h], rax
0x140016222  mov     rdx, rbx; Irp
0x140016225  mov     rcx, r15; int
0x140016228  call    NtfsCommonSetInformation
0x14001622d  mov     [rbp+140h+var_138], eax
0x140016230  cmp     eax, 367h
0x140016235  jnz     loc_1400162F9
0x14001623b  mov     [rsp+170h+var_148], r12d
0x140016240  lea     r9, [rbp+140h+Event]
0x140016247  mov     rdx, rbx
  ... truncated ...
```
