# PcpTimeoutHandler

- ea: `0x14000cce0`
- end: `0x14000d16b`
- name: `PcpTimeoutHandler`
- size: `1163`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `2`
- callee_count: `15`
- tags: `loader_planting, installer_update`

## callers

- `0x140005c10`
- `0x1400085c0`

## callees

- `0x140003770`
- `0x140004fe0`
- `0x140007e10`
- `0x140007f90`
- `0x140008290`
- `0x140009100`
- `0x140009b80`
- `0x14000a8c4`
- `0x14000cab0`
- `0x14000cce0`
- `0x14000d174`
- `0x140011154`
- `0x140011904`
- `0x140011a34`
- `0x140012410`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000cd25`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000cd25`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000ce02`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000cf73`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000cf83`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000d142`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000ce02`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000cf73`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000cf83`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000d142`
- `ntoskrnl!KeCancelTimer` at `0x14000d0fe`
- `ntoskrnl!KeCancelTimer` at `0x14000d0fe`
- `NDIS!NdisReleaseRWLock` at `0x14000ce9d`
- `NDIS!NdisReleaseRWLock` at `0x14000ce9d`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000ce7c`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000ce7c`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x14000cdef`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x14000cf56`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x14000cdef`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x14000cf56`
- `NETIO!RtlUpdateCurrentTimerWheelTick` at `0x14000cddf`
- `NETIO!RtlUpdateCurrentTimerWheelTick` at `0x14000cddf`
- `NETIO!RtlGetNextExpirationTimerWheelTick` at `0x14000d064`
- `NETIO!RtlGetNextExpirationTimerWheelTick` at `0x14000d064`
- `NETIO!RtlSuspendTimerWheel` at `0x14000d0ea`
- `NETIO!RtlSuspendTimerWheel` at `0x14000d0ea`
- `NETIO!RtlReturnTimerWheelEntry` at `0x14000cf40`
- `NETIO!RtlReturnTimerWheelEntry` at `0x14000cf40`
- `NETIO!RtlIsTimerWheelSuspended` at `0x14000cdb5`
- `NETIO!RtlIsTimerWheelSuspended` at `0x14000d0d6`
- `NETIO!RtlIsTimerWheelSuspended` at `0x14000cdb5`
- `NETIO!RtlIsTimerWheelSuspended` at `0x14000d0d6`

## pseudocode

```c
void __fastcall PcpTimeoutHandler(
        struct _KDPC *Dpc,
        char *DeferredContext,
        PVOID SystemArgument1,
        PVOID SystemArgument2)
{
  __int64 CurrentProcessorNumber; // r12
  __int64 v6; // r8
  __int64 v7; // rdx
  unsigned __int64 CurrentTime; // rsi
  int v9; // r15d
  unsigned __int64 v10; // r14
  unsigned int v11; // eax
  int v12; // ecx
  __int64 v13; // rcx
  unsigned int v14; // r13d
  __int64 NextExpiredTimerWheelEntry; // rdi
  __int64 v16; // r15
  PVOID *v17; // rax
  PNDIS_RW_LOCK_EX *v18; // r14
  __int64 v19; // rdx
  unsigned __int64 v20; // r8
  int v21; // ecx
  char v22; // al
  __int64 v23; // r13
  __int64 v24; // rax
  PNET_BUFFER_LIST Alignment; // r14
  int v26; // ecx
  unsigned int NextExpirationTimerWheelTick; // eax
  __int64 v28; // rdx
  __int64 v29; // r8
  unsigned int v30; // edi
  __int64 v31; // r8
  unsigned __int64 v32; // r8
  __int64 LockState; // [rsp+30h] [rbp-79h] BYREF
  int v34; // [rsp+38h] [rbp-71h]
  int v35; // [rsp+3Ch] [rbp-6Dh]
  int v36; // [rsp+40h] [rbp-69h] BYREF
  unsigned __int64 v37; // [rsp+48h] [rbp-61h]
  PNET_BUFFER_LIST NetBufferList; // [rsp+50h] [rbp-59h] BYREF
  PNET_BUFFER_LIST v39; // [rsp+58h] [rbp-51h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+60h] [rbp-49h] BYREF
  __int64 v41; // [rsp+78h] [rbp-31h]
  _OWORD v42[2]; // [rsp+80h] [rbp-29h] BYREF
  int v43; // [rsp+A0h] [rbp-9h]
  struct _KLOCK_QUEUE_HANDLE v44; // [rsp+A8h] [rbp-1h] BYREF
  char v45; // [rsp+118h] [rbp+6Fh]

  v43 = 0;
  memset(v42, 0, sizeof(v42));
  LOWORD(LockState) = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  BYTE2(LockState) = 0;
  memset(&v44, 0, sizeof(v44));
  CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
  LOBYTE(v6) = 1;
  LOBYTE(v7) = 1;
  CurrentTime = QosTimerGetCurrentTime(CurrentProcessorNumber, v7, v6);
  v9 = 0;
  NetBufferList = 0;
  v39 = 0;
  v10 = CurrentTime / 0xFA;
  v37 = CurrentTime / 0xFA;
  v36 = 0;
  ++*((_DWORD *)PcgDelayQueue + 16 * (unsigned __int64)(unsigned int)CurrentProcessorNumber + 4);
  RtlAcquireWriteLockAtDpcLevel(DeferredContext, &LockHandle);
  v11 = *((_DWORD *)DeferredContext + 11) & 0xFFFFFFFE;
  v12 = ~(*((_DWORD *)DeferredContext + 11) >> 1);
  *((_QWORD *)DeferredContext + 2) = CurrentTime;
  *((_DWORD *)DeferredContext + 11) = v11 | v12 & 1;
  if ( !(unsigned __int8)RtlIsTimerWheelSuspended(*((_QWORD *)DeferredContext + 4)) )
  {
    v13 = *((_QWORD *)DeferredContext + 4);
    v14 = 0;
    v35 = 0;
    v34 = 0;
    HIDWORD(LockState) = 0;
    RtlUpdateCurrentTimerWheelTick(v13, (unsigned int)v10);
    NextExpiredTimerWheelEntry = RtlGetNextExpiredTimerWheelEntry(*((_QWORD *)DeferredContext + 4));
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
    if ( NextExpiredTimerWheelEntry )
    {
      _InterlockedAdd((volatile signed __int32 *)(NextExpiredTimerWheelEntry - 80), 1u);
      do
      {
        v16 = NextExpiredTimerWheelEntry - 112;
        v41 = NextExpiredTimerWheelEntry;
        RtlAcquireWriteLockAtDpcLevel(NextExpiredTimerWheelEntry - 112 + 96, &v44);
        *(_DWORD *)(NextExpiredTimerWheelEntry + 20) = 0;
        if ( (unsigned __int8)QosFlowNeedQueueFeedback(NextExpiredTimerWheelEntry - 112 + 136, CurrentTime, v42) )
        {
          v17 = PcpLineFindByLuid(*(PVOID *)(v16 + 88));
          v18 = (PNDIS_RW_LOCK_EX *)v17;
          if ( v17 )
          {
            PcpLineSignalExternalEvent(v17, (unsigned int)CurrentProcessorNumber);
            NdisAcquireRWLockWrite(v18[2], (PLOCK_STATE_EX)&LockState, 0);
            QosLineQueryQueueFeedback(v18 + 3, v19, v42);
            NdisReleaseRWLock(v18[2], (PLOCK_STATE_EX)&LockState);
            PcpLineDereference(v18);
            QosTbcAdjustSendWindow(v16 + 136, v42);
          }
          LODWORD(v10) = v37;
        }
        if ( (unsigned __int8)QosFlowProcessQueuedNetBufferLists(
                                (int)v16 + 136,
                                CurrentProcessorNumber,
                                (unsigned int)&NetBufferList,
                                (unsigned int)&v36,
                                (__int64)&v39) )
        {
          v20 = *(_QWORD *)(*(_QWORD *)(v16 + 232) + 24LL) / 0xFAuLL;
          v21 = v20 + 1;
          if ( (int)v20 - (int)v10 > 0 )
            v21 = *(_QWORD *)(*(_QWORD *)(v16 + 232) + 24LL) / 0xFAuLL;
          if ( !v21 )
            v21 = 1;
          *(_DWORD *)(NextExpiredTimerWheelEntry + 20) = v21;
        }
        RtlAcquireWriteLockAtDpcLevel(DeferredContext, &LockHandle);
        v22 = RtlReturnTimerWheelEntry(*((_QWORD *)DeferredContext + 4), NextExpiredTimerWheelEntry);
        v23 = *(_QWORD *)NextExpiredTimerWheelEntry;
        v45 = v22;
        v24 = RtlGetNextExpiredTimerWheelEntry(*((_QWORD *)DeferredContext + 4));
        NextExpiredTimerWheelEntry = v24;
        if ( v24 )
          _InterlockedAdd((volatile signed __int32 *)(v24 - 80), 1u);
        KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
        KeReleaseInStackQueuedSpinLockFromDpcLevel(&v44);
        if ( NetBufferList )
          PcpSchedulerBatchAndSendOrDropNblChain(NetBufferList);
        Alignment = v39;
        if ( v39 )
          PcpSchedulerBatchAndSendOrDropNblChain(v39);
        if ( v23 == v41 && v45 )
          PcpDereferenceFlow(v16);
        PcpDereferenceFlow(v16);
        v26 = v36 + v34;
        v14 = v35 + 1;
        v9 = HIDWORD(LockState);
        ++v35;
        v34 += v36;
        if ( Alignment )
        {
          do
          {
            Alignment = (PNET_BUFFER_LIST)Alignment->Link.Alignment;
            ++v9;
          }
          while ( Alignment );
          HIDWORD(LockState) = v9;
        }
        LODWORD(v10) = v37;
      }
      while ( NextExpiredTimerWheelEntry );
    }
    else
    {
      v26 = 0;
    }
    if ( PcgEventTraceEnabled )
      PcpTraceTimer(DeferredContext, CurrentTime, 1, v14, v26, v9, LockState);
    RtlAcquireWriteLockAtDpcLevel(DeferredContext, &LockHandle);
  }
  NextExpirationTimerWheelTick = RtlGetNextExpirationTimerWheelTick(*((_QWORD *)DeferredContext + 4));
  v30 = NextExpirationTimerWheelTick;
  if ( PcgDisableRecursionFix )
  {
    v31 = 250LL * (NextExpirationTimerWheelTick - (unsigned int)v10);
  }
  else
  {
    LOBYTE(v29) = 1;
    LOBYTE(v28) = 1;
    CurrentTime = QosTimerGetCurrentTime((unsigned int)CurrentProcessorNumber, v28, v29);
    if ( (unsigned int)(CurrentTime / 0xFA) > v30 )
    {
      v32 = CurrentTime;
      goto LABEL_38;
    }
    v31 = 250LL * (v30 - (unsigned int)(CurrentTime / 0xFA));
  }
  v32 = CurrentTime + v31;
LABEL_38:
  if ( v30 )
  {
    PcpSetTimer(DeferredContext, CurrentTime, v32);
  }
  else
  {
    if ( !(unsigned __int8)RtlIsTimerWheelSuspended(*((_QWORD *)DeferredContext + 4)) )
      RtlSuspendTimerWheel(*((_QWORD *)DeferredContext + 4));
    *((_DWORD *)DeferredContext + 11) |= 1u;
    KeCancelTimer((PKTIMER)(DeferredContext + 112));
    if ( PcgEventTraceEnabled )
      PcpTraceTimer(DeferredContext, *((_QWORD *)DeferredContext + 2), 2, 0, 0, 0, LockState);
  }
  KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  PcpIndicateDelayQueueConsumerEnd((unsigned int)CurrentProcessorNumber);
}

```

## disassembly

```asm
0x14000cce0  push    rbp
0x14000cce2  push    rbx
0x14000cce3  push    rsi
0x14000cce4  push    rdi
0x14000cce5  push    r12
0x14000cce7  push    r13
0x14000cce9  push    r14
0x14000cceb  push    r15
0x14000cced  lea     rbp, [rsp-1Fh]
0x14000ccf2  sub     rsp, 0C8h
0x14000ccf9  xor     eax, eax
0x14000ccfb  xorps   xmm0, xmm0
0x14000ccfe  xor     ecx, ecx; ProcNumber
0x14000cd00  mov     [rbp+57h+var_60], eax
0x14000cd03  movups  [rbp+57h+var_80], xmm0
0x14000cd07  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x14000cd0b  mov     rbx, rdx
0x14000cd0e  movups  [rbp+57h+var_70], xmm0
0x14000cd12  mov     word ptr [rbp+57h+LockState.OldIrql], ax
0x14000cd16  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x14000cd1a  mov     [rbp+57h+LockState.Flags], al
0x14000cd1d  movups  xmmword ptr [rbp+57h+var_58.LockQueue.Next], xmm0
0x14000cd21  mov     qword ptr [rbp+57h+var_58.OldIrql], rax
0x14000cd25  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000cd2c  nop     dword ptr [rax+rax+00h]
0x14000cd31  mov     r13d, 1
0x14000cd37  mov     r12d, eax
0x14000cd3a  mov     r8b, r13b
0x14000cd3d  mov     dl, r13b
0x14000cd40  mov     ecx, eax
0x14000cd42  call    QosTimerGetCurrentTime
0x14000cd47  mov     rsi, rax
0x14000cd4a  xor     r15d, r15d
0x14000cd4d  mov     rax, 624DD2F1A9FBE77h
0x14000cd57  mov     [rbp+57h+NetBufferList], r15
0x14000cd5b  mul     rsi
0x14000cd5e  mov     rax, cs:PcgDelayQueue
0x14000cd65  mov     r14, rsi
0x14000cd68  sub     r14, rdx
0x14000cd6b  mov     [rbp+57h+var_A8], r15
0x14000cd6f  shr     r14, 1
0x14000cd72  mov     ecx, r12d
0x14000cd75  shl     rcx, 6
0x14000cd79  add     r14, rdx
0x14000cd7c  shr     r14, 7
0x14000cd80  lea     rdx, [rbp+57h+LockHandle]
0x14000cd84  mov     [rbp+57h+var_B8], r14
0x14000cd88  mov     [rbp+57h+var_C0], r15d
0x14000cd8c  add     [rcx+rax+10h], r13d
0x14000cd91  mov     rcx, rbx
0x14000cd94  call    RtlAcquireWriteLockAtDpcLevel
0x14000cd99  mov     eax, [rbx+2Ch]
0x14000cd9c  mov     ecx, eax
0x14000cd9e  shr     ecx, 1
0x14000cda0  and     eax, 0FFFFFFFEh
0x14000cda3  not     ecx
0x14000cda5  mov     [rbx+10h], rsi
0x14000cda9  and     ecx, r13d
0x14000cdac  or      ecx, eax
0x14000cdae  mov     [rbx+2Ch], ecx
0x14000cdb1  mov     rcx, [rbx+20h]
0x14000cdb5  call    cs:__imp_RtlIsTimerWheelSuspended
0x14000cdbc  nop     dword ptr [rax+rax+00h]
0x14000cdc1  test    al, al
0x14000cdc3  jnz     loc_14000D060
0x14000cdc9  mov     rcx, [rbx+20h]
0x14000cdcd  mov     edx, r14d
0x14000cdd0  mov     r13d, r15d
0x14000cdd3  mov     [rbp+57h+var_C4], r15d
0x14000cdd7  mov     [rbp+57h+var_C8], r15d
0x14000cddb  mov     [rbp+57h+var_CC], r15d
0x14000cddf  call    cs:__imp_RtlUpdateCurrentTimerWheelTick
0x14000cde6  nop     dword ptr [rax+rax+00h]
0x14000cdeb  mov     rcx, [rbx+20h]
0x14000cdef  call    cs:__imp_RtlGetNextExpiredTimerWheelEntry
0x14000cdf6  nop     dword ptr [rax+rax+00h]
0x14000cdfb  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x14000cdff  mov     rdi, rax
0x14000ce02  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14000ce09  nop     dword ptr [rax+rax+00h]
0x14000ce0e  test    rdi, rdi
0x14000ce11  jz      loc_14000D01C
0x14000ce17  lea     eax, [r15+1]
0x14000ce1b  lock add [rdi-50h], eax
0x14000ce1f  lea     r15, [rdi-70h]
0x14000ce23  mov     [rbp+57h+var_88], rdi
0x14000ce27  lea     rcx, [r15+60h]
0x14000ce2b  lea     rdx, [rbp+57h+var_58]
0x14000ce2f  call    RtlAcquireWriteLockAtDpcLevel
0x14000ce34  lea     r13, [r15+88h]
0x14000ce3b  mov     dword ptr [rdi+14h], 0
0x14000ce42  mov     rcx, r13
0x14000ce45  lea     r8, [rbp+57h+var_80]
0x14000ce49  mov     rdx, rsi
0x14000ce4c  call    QosFlowNeedQueueFeedback
0x14000ce51  test    al, al
0x14000ce53  jz      short loc_14000CEC1
0x14000ce55  mov     rcx, [r15+58h]
0x14000ce59  call    PcpLineFindByLuid
0x14000ce5e  mov     r14, rax
0x14000ce61  test    rax, rax
0x14000ce64  jz      short loc_14000CEBD
0x14000ce66  mov     edx, r12d
0x14000ce69  mov     rcx, rax
0x14000ce6c  call    PcpLineSignalExternalEvent
0x14000ce71  mov     rcx, [r14+10h]; Lock
0x14000ce75  lea     rdx, [rbp+57h+LockState]; LockState
0x14000ce79  xor     r8d, r8d; Flags
0x14000ce7c  call    cs:__imp_NdisAcquireRWLockWrite
0x14000ce83  nop     dword ptr [rax+rax+00h]
0x14000ce88  lea     rcx, [r14+18h]
0x14000ce8c  lea     r8, [rbp+57h+var_80]
0x14000ce90  call    QosLineQueryQueueFeedback
0x14000ce95  mov     rcx, [r14+10h]; Lock
0x14000ce99  lea     rdx, [rbp+57h+LockState]; LockState
0x14000ce9d  call    cs:__imp_NdisReleaseRWLock
0x14000cea4  nop     dword ptr [rax+rax+00h]
0x14000cea9  mov     rcx, r14; P
0x14000ceac  call    PcpLineDereference
0x14000ceb1  lea     rdx, [rbp+57h+var_80]
0x14000ceb5  mov     rcx, r13
0x14000ceb8  call    QosTbcAdjustSendWindow
0x14000cebd  mov     r14, [rbp+57h+var_B8]
0x14000cec1  lea     rax, [rbp+57h+var_A8]
0x14000cec5  mov     edx, r12d
0x14000cec8  lea     r9, [rbp+57h+var_C0]
0x14000cecc  mov     [rsp+100h+var_E0], rax
0x14000ced1  lea     r8, [rbp+57h+NetBufferList]
0x14000ced5  mov     rcx, r13
0x14000ced8  call    QosFlowProcessQueuedNetBufferLists
0x14000cedd  test    al, al
0x14000cedf  jz      short loc_14000CF27
0x14000cee1  mov     rax, [r15+0E8h]
0x14000cee8  mov     r8, [rax+18h]
0x14000ceec  mov     rax, 624DD2F1A9FBE77h
0x14000cef6  mul     r8
0x14000cef9  sub     r8, rdx
0x14000cefc  shr     r8, 1
0x14000ceff  add     r8, rdx
0x14000cf02  shr     r8, 7
0x14000cf06  mov     eax, r8d
0x14000cf09  sub     eax, r14d
0x14000cf0c  mov     r14d, 1
0x14000cf12  test    eax, eax
0x14000cf14  lea     ecx, [r8+1]
0x14000cf18  cmovg   ecx, r8d
0x14000cf1c  test    ecx, ecx
0x14000cf1e  cmovz   ecx, r14d
0x14000cf22  mov     [rdi+14h], ecx
0x14000cf25  jmp     short loc_14000CF2D
0x14000cf27  mov     r14d, 1
0x14000cf2d  lea     rdx, [rbp+57h+LockHandle]
0x14000cf31  mov     rcx, rbx
0x14000cf34  call    RtlAcquireWriteLockAtDpcLevel
0x14000cf39  mov     rcx, [rbx+20h]
0x14000cf3d  mov     rdx, rdi
0x14000cf40  call    cs:__imp_RtlReturnTimerWheelEntry
0x14000cf47  nop     dword ptr [rax+rax+00h]
0x14000cf4c  mov     rcx, [rbx+20h]
0x14000cf50  mov     r13, [rdi]
0x14000cf53  mov     [rbp+57h+arg_8], al
0x14000cf56  call    cs:__imp_RtlGetNextExpiredTimerWheelEntry
0x14000cf5d  nop     dword ptr [rax+rax+00h]
0x14000cf62  mov     rdi, rax
0x14000cf65  test    rax, rax
0x14000cf68  jz      short loc_14000CF6F
0x14000cf6a  lock add [rax-50h], r14d
0x14000cf6f  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x14000cf73  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14000cf7a  nop     dword ptr [rax+rax+00h]
0x14000cf7f  lea     rcx, [rbp+57h+var_58]; LockHandle
0x14000cf83  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14000cf8a  nop     dword ptr [rax+rax+00h]
0x14000cf8f  mov     rcx, [rbp+57h+NetBufferList]; NetBufferList
0x14000cf93  test    rcx, rcx
0x14000cf96  jz      short loc_14000CFA6
0x14000cf98  mov     r9b, r14b
0x14000cf9b  xor     r8d, r8d
0x14000cf9e  mov     edx, r12d
0x14000cfa1  call    PcpSchedulerBatchAndSendOrDropNblChain
0x14000cfa6  mov     r14, [rbp+57h+var_A8]
0x14000cfaa  test    r14, r14
0x14000cfad  jz      short loc_14000CFC0
0x14000cfaf  xor     r9d, r9d
0x14000cfb2  xor     r8d, r8d
0x14000cfb5  mov     edx, r12d
0x14000cfb8  mov     rcx, r14; NetBufferList
0x14000cfbb  call    PcpSchedulerBatchAndSendOrDropNblChain
0x14000cfc0  cmp     r13, [rbp+57h+var_88]
0x14000cfc4  jnz     short loc_14000CFD4
0x14000cfc6  cmp     [rbp+57h+arg_8], 0
0x14000cfca  jz      short loc_14000CFD4
0x14000cfcc  mov     rcx, r15
0x14000cfcf  call    PcpDereferenceFlow
0x14000cfd4  mov     rcx, r15
0x14000cfd7  call    PcpDereferenceFlow
0x14000cfdc  mov     ecx, [rbp+57h+var_C8]
0x14000cfdf  mov     eax, 1
0x14000cfe4  mov     r13d, [rbp+57h+var_C4]
0x14000cfe8  add     ecx, [rbp+57h+var_C0]
0x14000cfeb  add     r13d, eax
0x14000cfee  mov     r15d, [rbp+57h+var_CC]
0x14000cff2  mov     [rbp+57h+var_C4], r13d
0x14000cff6  mov     [rbp+57h+var_C8], ecx
0x14000cff9  test    r14, r14
0x14000cffc  jz      short loc_14000D00D
0x14000cffe  mov     r14, [r14]
0x14000d001  add     r15d, eax
0x14000d004  test    r14, r14
0x14000d007  jnz     short loc_14000CFFE
0x14000d009  mov     [rbp+57h+var_CC], r15d
0x14000d00d  mov     r14, [rbp+57h+var_B8]
0x14000d011  test    rdi, rdi
0x14000d014  jnz     loc_14000CE1F
0x14000d01a  jmp     short loc_14000D01F
0x14000d01c  mov     ecx, r13d
0x14000d01f  mov     eax, cs:PcgEventTraceEnabled
0x14000d025  test    eax, eax
0x14000d027  jz      short loc_14000D04B
0x14000d029  mov     r9d, r13d
0x14000d02c  mov     [rsp+100h+var_D8], r15d
0x14000d031  mov     dword ptr [rsp+100h+var_E0], ecx
0x14000d035  mov     r13d, 1
0x14000d03b  mov     r8d, r13d
0x14000d03e  mov     rdx, rsi
0x14000d041  mov     rcx, rbx
0x14000d044  call    PcpTraceTimer
0x14000d049  jmp     short loc_14000D051
0x14000d04b  mov     r13d, 1
0x14000d051  lea     rdx, [rbp+57h+LockHandle]
0x14000d055  mov     rcx, rbx
0x14000d058  call    RtlAcquireWriteLockAtDpcLevel
0x14000d05d  xor     r15d, r15d
0x14000d060  mov     rcx, [rbx+20h]
0x14000d064  call    cs:__imp_RtlGetNextExpirationTimerWheelTick
0x14000d06b  nop     dword ptr [rax+rax+00h]
0x14000d070  cmp     cs:PcgDisableRecursionFix, r15d
0x14000d077  mov     edi, eax
0x14000d079  jz      short loc_14000D089
0x14000d07b  mov     ecx, eax
0x14000d07d  sub     ecx, r14d
0x14000d080  imul    r8, rcx, 0FAh
0x14000d087  jmp     short loc_14000D0CB
0x14000d089  mov     r8b, r13b
0x14000d08c  mov     dl, r13b
0x14000d08f  mov     ecx, r12d
0x14000d092  call    QosTimerGetCurrentTime
0x14000d097  mov     rsi, rax
0x14000d09a  mov     rax, 624DD2F1A9FBE77h
0x14000d0a4  mul     rsi
0x14000d0a7  mov     rcx, rsi
0x14000d0aa  sub     rcx, rdx
0x14000d0ad  shr     rcx, 1
0x14000d0b0  add     rcx, rdx
0x14000d0b3  shr     rcx, 7
0x14000d0b7  cmp     ecx, edi
0x14000d0b9  jbe     short loc_14000D0C0
0x14000d0bb  mov     r8, rsi
0x14000d0be  jmp     short loc_14000D0CE
0x14000d0c0  mov     eax, edi
0x14000d0c2  sub     eax, ecx
0x14000d0c4  imul    r8, rax, 0FAh
0x14000d0cb  add     r8, rsi
0x14000d0ce  test    edi, edi
0x14000d0d0  jnz     short loc_14000D133
0x14000d0d2  mov     rcx, [rbx+20h]
0x14000d0d6  call    cs:__imp_RtlIsTimerWheelSuspended
0x14000d0dd  nop     dword ptr [rax+rax+00h]
0x14000d0e2  test    al, al
0x14000d0e4  jnz     short loc_14000D0F6
0x14000d0e6  mov     rcx, [rbx+20h]
0x14000d0ea  call    cs:__imp_RtlSuspendTimerWheel
0x14000d0f1  nop     dword ptr [rax+rax+00h]
0x14000d0f6  or      [rbx+2Ch], r13d
0x14000d0fa  lea     rcx, [rbx+70h]; PKTIMER
0x14000d0fe  call    cs:__imp_KeCancelTimer
0x14000d105  nop     dword ptr [rax+rax+00h]
0x14000d10a  mov     eax, cs:PcgEventTraceEnabled
0x14000d110  test    eax, eax
0x14000d112  jz      short loc_14000D13E
0x14000d114  mov     rdx, [rbx+10h]
0x14000d118  xor     r9d, r9d
0x14000d11b  mov     [rsp+100h+var_D8], r15d
0x14000d120  mov     rcx, rbx
0x14000d123  mov     dword ptr [rsp+100h+var_E0], r15d
0x14000d128  lea     r8d, [r9+2]
0x14000d12c  call    PcpTraceTimer
0x14000d131  jmp     short loc_14000D13E
0x14000d133  mov     rdx, rsi
0x14000d136  mov     rcx, rbx
0x14000d139  call    PcpSetTimer
0x14000d13e  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x14000d142  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14000d149  nop     dword ptr [rax+rax+00h]
0x14000d14e  mov     ecx, r12d
0x14000d151  call    PcpIndicateDelayQueueConsumerEnd
0x14000d156  add     rsp, 0C8h
0x14000d15d  pop     r15
0x14000d15f  pop     r14
0x14000d161  pop     r13
  ... truncated ...
```
