# PxIODispatch

- ea: `0x140004ad0`
- end: `0x14000547a`
- name: `PxIODispatch`
- size: `2474`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140001b54`
- `0x140001b84`
- `0x140001bc8`
- `0x140001c0c`
- `0x140004ad0`
- `0x140005718`
- `0x14000576c`
- `0x1400057c4`
- `0x140005820`
- `0x140008000`
- `0x140010ecc`
- `0x1400112d8`
- `0x140011474`
- `0x14001152c`
- `0x1400115f0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004bee`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004d5d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004efa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400050f1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000527c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400052b2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000534e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005388`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004bee`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004d5d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004efa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400050f1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000527c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400052b2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000534e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005388`
- `ntoskrnl!IofCompleteRequest` at `0x14000540c`
- `ntoskrnl!IofCompleteRequest` at `0x14000545a`
- `ntoskrnl!IofCompleteRequest` at `0x14000540c`
- `ntoskrnl!IofCompleteRequest` at `0x14000545a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004c17`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004dd5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004fe8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000513e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005184`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400052da`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400052f7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400053b0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004c17`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004dd5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004fe8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000513e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005184`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400052da`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400052f7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400053b0`
- `NDIS!NdisReleaseRWLock` at `0x140004e4b`
- `NDIS!NdisReleaseRWLock` at `0x140004e4b`
- `NDIS!NdisAcquireRWLockRead` at `0x140004e04`
- `NDIS!NdisAcquireRWLockRead` at `0x140004e04`

## pseudocode

```c
__int64 __fastcall PxIODispatch(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rcx
  unsigned int v6; // ebp
  unsigned __int64 v7; // r12
  int v8; // ecx
  unsigned int v9; // ebx
  volatile LONG *v10; // rdi
  unsigned int v11; // r15d
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  PDEVICE_OBJECT v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rbp
  volatile unsigned int v17; // edi
  unsigned int i; // edx
  struct _SINGLE_LIST_ENTRY *Next; // r8
  unsigned int LineEvents; // eax
  unsigned __int64 v21; // rax
  int v22; // eax
  unsigned int v23; // r9d
  __int64 v24; // r13
  PDEVICE_OBJECT v25; // rcx
  __int64 v26; // rdx
  LONG v27; // eax
  unsigned int v28; // eax
  unsigned __int64 v30; // rcx
  KIRQL v31; // al
  ULONG *v32; // rdi
  ULONG *v33; // rdi
  __int64 v34; // rax
  __int64 LockState; // [rsp+98h] [rbp+10h] BYREF

  v5 = *(_QWORD *)(a2 + 184);
  if ( *(_BYTE *)v5 != 14 || a1 != *((_QWORD *)WPP_MAIN_CB.Dpc.DeferredRoutine + 2) )
  {
    *(_DWORD *)(a2 + 48) = -1073741637;
    *(_QWORD *)(a2 + 56) = 0;
    IofCompleteRequest((PIRP)a2, 0);
    return 3221225659LL;
  }
  v6 = *(_DWORD *)(v5 + 16);
  v7 = *(unsigned int *)(v5 + 8);
  v8 = *(_DWORD *)(v5 + 24);
  v9 = 0;
  v10 = *(volatile LONG **)(a2 + 24);
  v11 = 0;
  if ( v8 == -1879104576 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_713d02be0a463cb5141fa39da77025f3_Traceguids, a2);
    if ( v6 >= 8 && (unsigned int)v7 >= 4 )
    {
      LOBYTE(WPP_MAIN_CB.SectorSize) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink);
      *v10 = WPP_MAIN_CB.DeviceLock.Header.Lock;
      v33 = *(ULONG **)&WPP_MAIN_CB.ActiveThreadCount;
      LODWORD(WPP_MAIN_CB.Dpc.DpcData) = 0;
      while ( v33 != &WPP_MAIN_CB.ActiveThreadCount )
      {
        *((_BYTE *)v33 + 144) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v33 + 17);
        if ( !v33[4] )
          MarkProviderConnected(v33);
        KeReleaseSpinLock((PKSPIN_LOCK)v33 + 17, *((_BYTE *)v33 + 144));
        v33 = *(ULONG **)v33;
      }
      goto LABEL_20;
    }
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      v15 = 16;
      goto LABEL_143;
    }
    goto LABEL_144;
  }
  if ( v8 == -1879104572 )
  {
    v31 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink);
    v32 = *(ULONG **)&WPP_MAIN_CB.ActiveThreadCount;
    LOBYTE(WPP_MAIN_CB.SectorSize) = v31;
    LODWORD(WPP_MAIN_CB.Dpc.DpcData) = 3;
    while ( v32 != &WPP_MAIN_CB.ActiveThreadCount )
    {
      *((_BYTE *)v32 + 144) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v32 + 17);
      if ( !v32[4] )
        MarkProviderDisconnected(v32);
      KeReleaseSpinLock((PKSPIN_LOCK)v32 + 17, *((_BYTE *)v32 + 144));
      v32 = *(ULONG **)v32;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink, WPP_MAIN_CB.SectorSize);
    v11 = 0;
    goto LABEL_145;
  }
  if ( ((v8 + 1879104568) & 0xFFFFFFFB) != 0 )
  {
    switch ( v8 )
    {
      case -1879104560:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_713d02be0a463cb5141fa39da77025f3_Traceguids);
        if ( v6 >= 0xC )
        {
          if ( v7 - 11 >= *(unsigned int *)v10 )
          {
            LOBYTE(WPP_MAIN_CB.Queue.Wcb.DeviceRoutine) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels);
            if ( LODWORD(WPP_MAIN_CB.Queue.ListEntry.Flink) )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                WPP_SF_DD(
                  WPP_GLOBAL_Control->AttachedDevice,
                  27,
                  WPP_713d02be0a463cb5141fa39da77025f3_Traceguids,
                  LODWORD(WPP_MAIN_CB.Queue.ListEntry.Flink),
                  *v10);
              LineEvents = GetLineEvents(v10 + 2, *(unsigned int *)v10);
              *((_DWORD *)v10 + 1) = LineEvents;
              v11 = v7;
              v21 = LineEvents + 11LL;
              if ( v7 >= v21 )
                v11 = v21;
            }
            else
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_713d02be0a463cb5141fa39da77025f3_Traceguids);
              if ( WPP_MAIN_CB.Queue.ListEntry.Blink )
              {
                v9 = -1073741823;
                v11 = 4;
              }
              else
              {
                _InterlockedExchange64((volatile __int64 *)(a2 + 104), (__int64)PxCancelGetEvents);
                *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
                *(_QWORD *)(a2 + 56) = 0;
                v9 = 259;
                *(_DWORD *)(a2 + 48) = 259;
                WPP_MAIN_CB.Queue.ListEntry.Blink = (struct _LIST_ENTRY *)a2;
              }
            }
            KeReleaseSpinLock(
              (PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels,
              (KIRQL)WPP_MAIN_CB.Queue.Wcb.DeviceRoutine);
            if ( v9 == 259 )
              goto LABEL_146;
            goto LABEL_145;
          }
          v9 = -1073741789;
          v11 = 4;
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
          {
LABEL_145:
            *(_QWORD *)(a2 + 56) = v11;
            v34 = *(_QWORD *)(a2 + 184);
            *(_DWORD *)(a2 + 48) = v9;
            *(_BYTE *)(v34 + 3) &= ~1u;
            IofCompleteRequest((PIRP)a2, 0);
LABEL_146:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_713d02be0a463cb5141fa39da77025f3_Traceguids, a2, v9);
            return v9;
          }
          v13 = 26;
        }
        else
        {
          v9 = -1073741789;
          v11 = 4;
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
            goto LABEL_145;
          v13 = 25;
        }
LABEL_13:
        WPP_SF_(v12->AttachedDevice, v13, WPP_713d02be0a463cb5141fa39da77025f3_Traceguids);
        goto LABEL_145;
      case -1879104556:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_713d02be0a463cb5141fa39da77025f3_Traceguids, a2, v6);
        if ( v6 >= 4 )
        {
          LOBYTE(WPP_MAIN_CB.SectorSize) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink);
          if ( !LODWORD(WPP_MAIN_CB.Dpc.DpcData) )
          {
            v17 = *v10;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_713d02be0a463cb5141fa39da77025f3_Traceguids, v17);
            KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink, WPP_MAIN_CB.SectorSize);
            LOWORD(LockState) = 0;
            BYTE2(LockState) = 0;
            NdisAcquireRWLockRead((PNDIS_RW_LOCK_EX)WPP_MAIN_CB.Dpc.ProcessorHistory, (PLOCK_STATE_EX)&LockState, 0);
            for ( i = 0; i < *((_DWORD *)&WPP_MAIN_CB.DeviceQueue.1 + 1); ++i )
            {
              Next = WPP_MAIN_CB.Dpc.DpcListEntry.Next[i].Next;
              if ( Next )
                LODWORD(Next[4].Next) = v17++;
            }
            NdisReleaseRWLock((PNDIS_RW_LOCK_EX)WPP_MAIN_CB.Dpc.ProcessorHistory, (PLOCK_STATE_EX)&LockState);
            goto LABEL_145;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_713d02be0a463cb5141fa39da77025f3_Traceguids);
          v9 = -1073741823;
          goto LABEL_21;
        }
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          v15 = 30;
          goto LABEL_143;
        }
        break;
      case -1879104552:
        LockState = 0;
        if ( v6 >= 8 )
        {
          if ( (unsigned __int8)IsTapiLineValid(*(unsigned int *)v10, &LockState) )
          {
            v16 = LockState;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              WPP_SF_qD(
                WPP_GLOBAL_Control->AttachedDevice,
                35,
                WPP_713d02be0a463cb5141fa39da77025f3_Traceguids,
                LockState,
                *((_DWORD *)v10 + 1));
            *(_DWORD *)(v16 + 32) = *((_DWORD *)v10 + 1);
          }
          else
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                34,
                WPP_713d02be0a463cb5141fa39da77025f3_Traceguids,
                *(unsigned int *)v10);
            v9 = -1073741811;
          }
          goto LABEL_145;
        }
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
          break;
        v15 = 33;
        goto LABEL_143;
      case -1879104548:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_713d02be0a463cb5141fa39da77025f3_Traceguids, a2);
        if ( v6 >= 8 && (unsigned int)v7 >= 4 )
        {
          LOBYTE(WPP_MAIN_CB.SectorSize) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink);
          *v10 = WPP_MAIN_CB.DeviceLock.Header.Lock;
LABEL_20:
          v11 = 4;
LABEL_21:
          KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink, WPP_MAIN_CB.SectorSize);
          goto LABEL_145;
        }
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          v15 = 37;
LABEL_143:
          WPP_SF_(v14->AttachedDevice, v15, WPP_713d02be0a463cb5141fa39da77025f3_Traceguids);
        }
        break;
      default:
        v9 = -1073741811;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
          goto LABEL_145;
        v13 = 38;
        goto LABEL_13;
    }
LABEL_144:
    v9 = -1073741789;
    goto LABEL_145;
  }
  if ( v6 < 0x38 || (unsigned int)v7 < 0x38 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_DD(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_713d02be0a463cb5141fa39da77025f3_Traceguids, v6, 56);
    v9 = -1073741820;
    goto LABEL_145;
  }
  v11 = 56;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_qDdD(
      WPP_GLOBAL_Control->AttachedDevice,
      a1,
      a3,
      a2,
      *((_DWORD *)v10 + 8),
      *((_DWORD *)v10 + 9),
      *((_DWORD *)v10 + 12));
  v22 = *((_DWORD *)v10 + 8) - 117637377;
  if ( (unsigned int)v22 >= 0x24 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice);
    *((_DWORD *)v10 + 7) = -1073668067;
    goto LABEL_145;
  }
  v23 = *((_DWORD *)v10 + 10);
  v24 = 2LL * v22;
  if ( v23 < HIDWORD(TapiOids[2 * v22]) )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
      goto LABEL_95;
    v26 = 20;
LABEL_94:
    WPP_SF_dd(v25->AttachedDevice, v26);
LABEL_95:
    *((_DWORD *)v10 + 7) = -1073668071;
    goto LABEL_145;
  }
  if ( v23 > v6 - 48 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
      goto LABEL_95;
    v26 = 21;
    goto LABEL_94;
  }
  LOBYTE(WPP_MAIN_CB.SectorSize) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink);
  if ( LODWORD(WPP_MAIN_CB.Dpc.DpcData) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_713d02be0a463cb5141fa39da77025f3_Traceguids);
    KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink, WPP_MAIN_CB.SectorSize);
    *((_DWORD *)v10 + 7) = 4097;
    goto LABEL_145;
  }
  v27 = WPP_MAIN_CB.DeviceLock.Header.SignalState + 1;
  WPP_MAIN_CB.DeviceLock.Header.SignalState = v27;
  if ( v27 == -1 )
  {
    v27 = -2147483647;
    WPP_MAIN_CB.DeviceLock.Header.SignalState = -2147483647;
  }
  *((_DWORD *)v10 + 6) = v27;
  *((_QWORD *)v10 + 2) = a2;
  KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink, WPP_MAIN_CB.SectorSize);
  *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
  v28 = ((__int64 (__fastcall *)(volatile LONG *))*(&funcs_1400051AA + v24))(v10);
  if ( v28 != 259 )
  {
    v30 = *((unsigned int *)v10 + 10) + 56LL;
    *((_DWORD *)v10 + 7) = v28;
    v11 = v7;
    _InterlockedExchange64((volatile __int64 *)(a2 + 104), 0);
    if ( v7 >= v30 )
      v11 = v30;
    goto LABEL_145;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_713d02be0a463cb5141fa39da77025f3_Traceguids);
  return 259;
}

```

## disassembly

```asm
0x140004ad0  push    rbx
0x140004ad2  push    rbp
0x140004ad3  push    rsi
0x140004ad4  push    rdi
0x140004ad5  push    r12
0x140004ad7  push    r13
0x140004ad9  push    r14
0x140004adb  push    r15
0x140004add  sub     rsp, 48h
0x140004ae1  mov     r14, rdx
0x140004ae4  mov     rdx, rcx
0x140004ae7  mov     rcx, [r14+0B8h]
0x140004aee  cmp     byte ptr [rcx], 0Eh
0x140004af1  jnz     loc_140005446
0x140004af7  mov     rax, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x140004afe  cmp     rdx, [rax+10h]
0x140004b02  jnz     loc_140005446
0x140004b08  mov     ebp, [rcx+10h]
0x140004b0b  lea     rsi, WPP_713d02be0a463cb5141fa39da77025f3_Traceguids
0x140004b12  mov     r12d, [rcx+8]
0x140004b16  lea     r13, WPP_GLOBAL_Control
0x140004b1d  mov     ecx, [rcx+18h]
0x140004b20  xor     ebx, ebx
0x140004b22  mov     rdi, [r14+18h]
0x140004b26  mov     r15d, ebx
0x140004b29  cmp     ecx, 8FFF23C0h
0x140004b2f  jz      loc_14000530B
0x140004b35  cmp     ecx, 8FFF23C4h
0x140004b3b  jz      loc_140005272
0x140004b41  lea     eax, [rcx+7000DC38h]
0x140004b47  test    eax, 0FFFFFFFBh
0x140004b4c  jz      loc_140005001
0x140004b52  cmp     ecx, 8FFF23D0h
0x140004b58  jz      loc_140004E5C
0x140004b5e  cmp     ecx, 8FFF23D4h
0x140004b64  jz      loc_140004D00
0x140004b6a  cmp     ecx, 8FFF23D8h
0x140004b70  jz      loc_140004C4C
0x140004b76  cmp     ecx, 8FFF23DCh
0x140004b7c  jz      short loc_140004BB3
0x140004b7e  mov     ebx, 0C000000Dh
0x140004b83  mov     rcx, cs:WPP_GLOBAL_Control
0x140004b8a  cmp     rcx, r13
0x140004b8d  jz      loc_1400053F1
0x140004b93  cmp     byte ptr [rcx+29h], 3
0x140004b97  jb      loc_1400053F1
0x140004b9d  mov     edx, 26h ; '&'
0x140004ba2  mov     rcx, [rcx+18h]
0x140004ba6  mov     r8, rsi
0x140004ba9  call    WPP_SF_
0x140004bae  jmp     loc_1400053F1
0x140004bb3  mov     rcx, cs:WPP_GLOBAL_Control
0x140004bba  cmp     rcx, r13
0x140004bbd  jz      short loc_140004BD9
0x140004bbf  cmp     byte ptr [rcx+29h], 4
0x140004bc3  jb      short loc_140004BD9
0x140004bc5  mov     rcx, [rcx+18h]
0x140004bc9  mov     edx, 24h ; '$'
0x140004bce  mov     r9, r14
0x140004bd1  mov     r8, rsi
0x140004bd4  call    WPP_SF_q
0x140004bd9  cmp     ebp, 8
0x140004bdc  jb      short loc_140004C28
0x140004bde  cmp     r12d, 4
0x140004be2  jb      short loc_140004C28
0x140004be4  lea     rbp, WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink
0x140004beb  mov     rcx, rbp; SpinLock
0x140004bee  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004bf5  nop     dword ptr [rax+rax+00h]
0x140004bfa  mov     byte ptr cs:WPP_MAIN_CB.SectorSize, al
0x140004c00  mov     eax, dword ptr cs:WPP_MAIN_CB.DeviceLock.Header
0x140004c06  mov     [rdi], eax
0x140004c08  mov     r15d, 4
0x140004c0e  mov     dl, byte ptr cs:WPP_MAIN_CB.SectorSize; NewIrql
0x140004c14  mov     rcx, rbp; SpinLock
0x140004c17  call    cs:__imp_KeReleaseSpinLock
0x140004c1e  nop     dword ptr [rax+rax+00h]
0x140004c23  jmp     loc_1400053F1
0x140004c28  mov     rcx, cs:WPP_GLOBAL_Control
0x140004c2f  cmp     rcx, r13
0x140004c32  jz      loc_1400053EC
0x140004c38  cmp     byte ptr [rcx+29h], 3
0x140004c3c  jb      loc_1400053EC
0x140004c42  mov     edx, 25h ; '%'
0x140004c47  jmp     loc_1400053E0
0x140004c4c  mov     [rsp+88h+LockState], rbx
0x140004c54  cmp     ebp, 8
0x140004c57  jnb     short loc_140004C7D
0x140004c59  mov     rcx, cs:WPP_GLOBAL_Control
0x140004c60  cmp     rcx, r13
0x140004c63  jz      loc_1400053EC
0x140004c69  cmp     byte ptr [rcx+29h], 3
0x140004c6d  jb      loc_1400053EC
0x140004c73  mov     edx, 21h ; '!'
0x140004c78  jmp     loc_1400053E0
0x140004c7d  mov     ecx, [rdi]
0x140004c7f  lea     rdx, [rsp+88h+LockState]
0x140004c87  call    IsTapiLineValid
0x140004c8c  test    al, al
0x140004c8e  jnz     short loc_140004CC0
0x140004c90  mov     rcx, cs:WPP_GLOBAL_Control
0x140004c97  cmp     rcx, r13
0x140004c9a  jz      short loc_140004CB6
0x140004c9c  cmp     byte ptr [rcx+29h], 3
0x140004ca0  jb      short loc_140004CB6
0x140004ca2  mov     r9d, [rdi]
0x140004ca5  mov     edx, 22h ; '"'
0x140004caa  mov     rcx, [rcx+18h]
0x140004cae  mov     r8, rsi
0x140004cb1  call    WPP_SF_d
0x140004cb6  mov     ebx, 0C000000Dh
0x140004cbb  jmp     loc_1400053F1
0x140004cc0  mov     rcx, cs:WPP_GLOBAL_Control
0x140004cc7  mov     rbp, [rsp+88h+LockState]
0x140004ccf  cmp     rcx, r13
0x140004cd2  jz      short loc_140004CF5
0x140004cd4  cmp     byte ptr [rcx+29h], 5
0x140004cd8  jb      short loc_140004CF5
0x140004cda  mov     eax, [rdi+4]
0x140004cdd  mov     edx, 23h ; '#'
0x140004ce2  mov     rcx, [rcx+18h]
0x140004ce6  mov     r9, rbp
0x140004ce9  mov     r8, rsi
0x140004cec  mov     [rsp+88h+var_68], eax
0x140004cf0  call    WPP_SF_qD
0x140004cf5  mov     eax, [rdi+4]
0x140004cf8  mov     [rbp+20h], eax
0x140004cfb  jmp     loc_1400053F1
0x140004d00  mov     rcx, cs:WPP_GLOBAL_Control
0x140004d07  cmp     rcx, r13
0x140004d0a  jz      short loc_140004D2A
0x140004d0c  cmp     byte ptr [rcx+29h], 4
0x140004d10  jb      short loc_140004D2A
0x140004d12  mov     rcx, [rcx+18h]
0x140004d16  mov     edx, 1Dh
0x140004d1b  mov     r9, r14
0x140004d1e  mov     [rsp+88h+var_68], ebp
0x140004d22  mov     r8, rsi
0x140004d25  call    WPP_SF_qD
0x140004d2a  cmp     ebp, 4
0x140004d2d  jnb     short loc_140004D53
0x140004d2f  mov     rcx, cs:WPP_GLOBAL_Control
0x140004d36  cmp     rcx, r13
0x140004d39  jz      loc_1400053EC
0x140004d3f  cmp     byte ptr [rcx+29h], 3
0x140004d43  jb      loc_1400053EC
0x140004d49  mov     edx, 1Eh
0x140004d4e  jmp     loc_1400053E0
0x140004d53  lea     rbp, WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink
0x140004d5a  mov     rcx, rbp; SpinLock
0x140004d5d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004d64  nop     dword ptr [rax+rax+00h]
0x140004d69  cmp     dword ptr cs:WPP_MAIN_CB.Dpc.DpcData, ebx
0x140004d6f  mov     byte ptr cs:WPP_MAIN_CB.SectorSize, al
0x140004d75  jz      short loc_140004DA4
0x140004d77  mov     rcx, cs:WPP_GLOBAL_Control
0x140004d7e  cmp     rcx, r13
0x140004d81  jz      short loc_140004D9A
0x140004d83  cmp     byte ptr [rcx+29h], 3
0x140004d87  jb      short loc_140004D9A
0x140004d89  mov     rcx, [rcx+18h]
0x140004d8d  mov     edx, 1Fh
0x140004d92  mov     r8, rsi
0x140004d95  call    WPP_SF_
0x140004d9a  mov     ebx, 0C0000001h
0x140004d9f  jmp     loc_140004C0E
0x140004da4  mov     edi, [rdi]
0x140004da6  mov     rcx, cs:WPP_GLOBAL_Control
0x140004dad  cmp     rcx, r13
0x140004db0  jz      short loc_140004DCC
0x140004db2  cmp     byte ptr [rcx+29h], 5
0x140004db6  jb      short loc_140004DCC
0x140004db8  mov     rcx, [rcx+18h]
0x140004dbc  mov     edx, 20h ; ' '
0x140004dc1  mov     r9d, edi
0x140004dc4  mov     r8, rsi
0x140004dc7  call    WPP_SF_d
0x140004dcc  mov     dl, byte ptr cs:WPP_MAIN_CB.SectorSize; NewIrql
0x140004dd2  mov     rcx, rbp; SpinLock
0x140004dd5  call    cs:__imp_KeReleaseSpinLock
0x140004ddc  nop     dword ptr [rax+rax+00h]
0x140004de1  mov     rcx, cs:WPP_MAIN_CB.Dpc.ProcessorHistory; Lock
0x140004de8  lea     rdx, [rsp+88h+LockState]; LockState
0x140004df0  xor     eax, eax
0x140004df2  xor     r8d, r8d; Flags
0x140004df5  mov     word ptr [rsp+88h+LockState], ax
0x140004dfd  mov     byte ptr [rsp+88h+LockState+2], al
0x140004e04  call    cs:__imp_NdisAcquireRWLockRead
0x140004e0b  nop     dword ptr [rax+rax+00h]
0x140004e10  cmp     dword ptr cs:WPP_MAIN_CB.DeviceQueue.20h+4, ebx
0x140004e16  mov     edx, ebx
0x140004e18  jz      short loc_140004E3C
0x140004e1a  mov     rax, cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next
0x140004e21  mov     ecx, edx
0x140004e23  mov     r8, [rax+rcx*8]
0x140004e27  test    r8, r8
0x140004e2a  jz      short loc_140004E32
0x140004e2c  mov     [r8+20h], edi
0x140004e30  inc     edi
0x140004e32  inc     edx
0x140004e34  cmp     edx, dword ptr cs:WPP_MAIN_CB.DeviceQueue.20h+4
0x140004e3a  jb      short loc_140004E1A
0x140004e3c  mov     rcx, cs:WPP_MAIN_CB.Dpc.ProcessorHistory; Lock
0x140004e43  lea     rdx, [rsp+88h+LockState]; LockState
0x140004e4b  call    cs:__imp_NdisReleaseRWLock
0x140004e52  nop     dword ptr [rax+rax+00h]
0x140004e57  jmp     loc_1400053F1
0x140004e5c  mov     rcx, cs:WPP_GLOBAL_Control
0x140004e63  cmp     rcx, r13
0x140004e66  jz      short loc_140004E7F
0x140004e68  cmp     byte ptr [rcx+29h], 5
0x140004e6c  jb      short loc_140004E7F
0x140004e6e  mov     rcx, [rcx+18h]
0x140004e72  mov     edx, 18h
0x140004e77  mov     r8, rsi
0x140004e7a  call    WPP_SF_
0x140004e7f  cmp     ebp, 0Ch
0x140004e82  jnb     short loc_140004EB2
0x140004e84  mov     ebx, 0C0000023h
0x140004e89  mov     r15d, 4
0x140004e8f  mov     rcx, cs:WPP_GLOBAL_Control
0x140004e96  cmp     rcx, r13
0x140004e99  jz      loc_1400053F1
0x140004e9f  cmp     byte ptr [rcx+29h], 3
0x140004ea3  jb      loc_1400053F1
0x140004ea9  lea     edx, [r15+15h]
0x140004ead  jmp     loc_140004BA2
0x140004eb2  mov     eax, [rdi]
0x140004eb4  lea     rcx, [r12-0Bh]
0x140004eb9  cmp     rcx, rax
0x140004ebc  jnb     short loc_140004EF3
0x140004ebe  mov     ebx, 0C0000023h
0x140004ec3  mov     r15d, 4
0x140004ec9  mov     rcx, cs:WPP_GLOBAL_Control
0x140004ed0  lea     r13, WPP_GLOBAL_Control
0x140004ed7  cmp     rcx, r13
0x140004eda  jz      loc_1400053F1
0x140004ee0  cmp     byte ptr [rcx+29h], 3
0x140004ee4  jb      loc_1400053F1
0x140004eea  lea     edx, [r15+16h]
0x140004eee  jmp     loc_140004BA2
0x140004ef3  lea     rcx, WPP_MAIN_CB.Queue+10h; SpinLock
0x140004efa  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004f01  nop     dword ptr [rax+rax+00h]
0x140004f06  mov     r9d, dword ptr cs:WPP_MAIN_CB.Queue
0x140004f0d  mov     ebp, 103h
0x140004f12  mov     byte ptr cs:WPP_MAIN_CB.Queue+18h, al
0x140004f18  test    r9d, r9d
0x140004f1b  jz      short loc_140004F74
0x140004f1d  mov     rcx, cs:WPP_GLOBAL_Control
0x140004f24  lea     rax, WPP_GLOBAL_Control
0x140004f2b  cmp     rcx, rax
0x140004f2e  jz      short loc_140004F4D
0x140004f30  cmp     byte ptr [rcx+29h], 5
0x140004f34  jb      short loc_140004F4D
0x140004f36  mov     eax, [rdi]
0x140004f38  mov     edx, 1Bh
0x140004f3d  mov     rcx, [rcx+18h]
0x140004f41  mov     r8, rsi
0x140004f44  mov     [rsp+88h+var_68], eax
0x140004f48  call    WPP_SF_DD
0x140004f4d  mov     edx, [rdi]
0x140004f4f  lea     rcx, [rdi+8]
0x140004f53  call    GetLineEvents
0x140004f58  mov     eax, eax
0x140004f5a  lea     r13, WPP_GLOBAL_Control
0x140004f61  mov     [rdi+4], eax
0x140004f64  mov     r15d, r12d
0x140004f67  add     rax, 0Bh
0x140004f6b  cmp     r12, rax
0x140004f6e  cmovnb  r15d, eax
0x140004f72  jmp     short loc_140004FDB
0x140004f74  mov     rcx, cs:WPP_GLOBAL_Control
0x140004f7b  lea     r13, WPP_GLOBAL_Control
0x140004f82  cmp     rcx, r13
0x140004f85  jz      short loc_140004F9E
0x140004f87  cmp     byte ptr [rcx+29h], 5
0x140004f8b  jb      short loc_140004F9E
0x140004f8d  mov     rcx, [rcx+18h]
0x140004f91  mov     edx, 1Ch
0x140004f96  mov     r8, rsi
0x140004f99  call    WPP_SF_
0x140004f9e  cmp     qword ptr cs:WPP_MAIN_CB.Queue+8, rbx
0x140004fa5  jnz     short loc_140004FD0
0x140004fa7  lea     rax, PxCancelGetEvents
0x140004fae  xchg    rax, [r14+68h]
0x140004fb2  mov     rcx, [r14+0B8h]
0x140004fb9  or      byte ptr [rcx+3], 1
0x140004fbd  mov     [r14+38h], rbx
0x140004fc1  mov     ebx, ebp
0x140004fc3  mov     [r14+30h], ebp
0x140004fc7  mov     qword ptr cs:WPP_MAIN_CB.Queue+8, r14
0x140004fce  jmp     short loc_140004FDB
0x140004fd0  mov     ebx, 0C0000001h
0x140004fd5  mov     r15d, 4
0x140004fdb  mov     dl, byte ptr cs:WPP_MAIN_CB.Queue+18h; NewIrql
0x140004fe1  lea     rcx, WPP_MAIN_CB.Queue+10h; SpinLock
0x140004fe8  call    cs:__imp_KeReleaseSpinLock
0x140004fef  nop     dword ptr [rax+rax+00h]
0x140004ff4  cmp     ebx, ebp
  ... truncated ...
```
