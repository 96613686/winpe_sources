# BwcTimeoutHandler

- ea: `0x140013080`
- end: `0x1400134d0`
- name: `BwcTimeoutHandler`
- size: `1104`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140009368`
- `0x140011da8`
- `0x1400123bc`
- `0x1400123e4`
- `0x140012b0c`
- `0x140012ddc`
- `0x140012e70`
- `0x140013080`
- `0x140013a04`
- `0x140013f48`
- `0x140013fb8`
- `0x140014010`
- `0x140014050`
- `0x140014384`
- `0x1400143d0`
- `0x140014fb4`
- `0x140016230`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x14001347d`
- `ntoskrnl!KeCancelTimer` at `0x14001347d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400131a3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001330a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400134a7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400131a3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001330a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400134a7`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400130bd`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400130bd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001333b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001333b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400131c7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400131c7`
- `NDIS!NdisReleaseRWLock` at `0x140013248`
- `NDIS!NdisReleaseRWLock` at `0x1400133aa`
- `NDIS!NdisReleaseRWLock` at `0x140013248`
- `NDIS!NdisReleaseRWLock` at `0x1400133aa`
- `NDIS!NdisAcquireRWLockWrite` at `0x14001320b`
- `NDIS!NdisAcquireRWLockWrite` at `0x14001338c`
- `NDIS!NdisAcquireRWLockWrite` at `0x14001320b`
- `NDIS!NdisAcquireRWLockWrite` at `0x14001338c`
- `NETIO!RtlGetNextExpirationTimerWheelTick` at `0x140013439`
- `NETIO!RtlGetNextExpirationTimerWheelTick` at `0x140013439`
- `NETIO!RtlUpdateCurrentTimerWheelTick` at `0x14001317d`
- `NETIO!RtlUpdateCurrentTimerWheelTick` at `0x14001317d`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x140013190`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x1400132f7`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x140013190`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x1400132f7`
- `NETIO!RtlIsTimerWheelSuspended` at `0x14001315f`
- `NETIO!RtlIsTimerWheelSuspended` at `0x140013450`
- `NETIO!RtlIsTimerWheelSuspended` at `0x14001315f`
- `NETIO!RtlIsTimerWheelSuspended` at `0x140013450`
- `NETIO!RtlReturnTimerWheelEntry` at `0x1400132dd`
- `NETIO!RtlReturnTimerWheelEntry` at `0x1400132dd`
- `NETIO!RtlSuspendTimerWheel` at `0x140013467`
- `NETIO!RtlSuspendTimerWheel` at `0x140013467`

## pseudocode

```c
void __fastcall BwcTimeoutHandler(
        struct _KDPC *Dpc,
        char *DeferredContext,
        PVOID SystemArgument1,
        PVOID SystemArgument2)
{
  __int64 CurrentProcessorNumber; // r15
  __int64 v6; // r8
  __int64 v7; // rdx
  unsigned __int64 CurrentTime; // rdi
  int v9; // r13d
  unsigned __int64 v10; // r12
  unsigned int v11; // eax
  int v12; // ecx
  __int64 NextExpiredTimerWheelEntry; // r14
  __int64 v14; // rdi
  KIRQL v15; // al
  unsigned __int64 v16; // rdx
  PNDIS_RW_LOCK_EX *v17; // rsi
  __int64 v18; // rdx
  unsigned __int64 v19; // r8
  int v20; // ecx
  __int64 v21; // rcx
  int v22; // edx
  int v23; // r9d
  int NextExpirationTimerWheelTick; // eax
  int v25; // [rsp+30h] [rbp-79h] BYREF
  __int64 v26; // [rsp+38h] [rbp-71h] BYREF
  unsigned __int64 v27; // [rsp+40h] [rbp-69h]
  __int64 v28; // [rsp+48h] [rbp-61h] BYREF
  __int64 v29; // [rsp+50h] [rbp-59h] BYREF
  __int64 v30; // [rsp+58h] [rbp-51h] BYREF
  __int64 v31; // [rsp+60h] [rbp-49h] BYREF
  unsigned __int64 v32; // [rsp+68h] [rbp-41h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+70h] [rbp-39h] BYREF
  __int64 v34; // [rsp+88h] [rbp-21h]
  __int64 v35; // [rsp+90h] [rbp-19h]
  _OWORD v36[2]; // [rsp+98h] [rbp-11h] BYREF
  int v37; // [rsp+B8h] [rbp+Fh]
  struct _LOCK_STATE_EX LockState; // [rsp+118h] [rbp+6Fh] BYREF

  v37 = 0;
  memset(v36, 0, sizeof(v36));
  *(_WORD *)&LockState.OldIrql = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  LockState.Flags = 0;
  CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
  LOBYTE(v6) = 1;
  LOBYTE(v7) = 1;
  CurrentTime = QosTimerGetCurrentTime(CurrentProcessorNumber, v7, v6);
  v32 = CurrentTime;
  v9 = 0;
  v29 = 0;
  v10 = CurrentTime / 0xFA;
  v27 = CurrentTime / 0xFA;
  v26 = 0;
  ++*((_DWORD *)BwcDelayQueue + 16 * (unsigned __int64)(unsigned int)CurrentProcessorNumber + 4);
  v30 = 0;
  v28 = 0;
  v25 = 0;
  RtlAcquireWriteLockAtDpcLevel(DeferredContext, &LockHandle);
  v11 = *((_DWORD *)DeferredContext + 43) & 0xFFFFFFFE;
  v12 = ~(*((_DWORD *)DeferredContext + 43) >> 1);
  *((_QWORD *)DeferredContext + 2) = CurrentTime;
  *((_DWORD *)DeferredContext + 43) = v11 | v12 & 1;
  if ( !(unsigned __int8)RtlIsTimerWheelSuspended(*((_QWORD *)DeferredContext + 20)) )
  {
    RtlUpdateCurrentTimerWheelTick(*((_QWORD *)DeferredContext + 20), (unsigned int)v10);
    NextExpiredTimerWheelEntry = RtlGetNextExpiredTimerWheelEntry(*((_QWORD *)DeferredContext + 20));
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
    if ( NextExpiredTimerWheelEntry )
    {
      do
      {
        v14 = NextExpiredTimerWheelEntry - 8;
        v34 = NextExpiredTimerWheelEntry;
        v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(NextExpiredTimerWheelEntry - 8 + 472));
        v16 = v32;
        *(_BYTE *)(NextExpiredTimerWheelEntry - 8 + 480) = v15;
        v17 = (PNDIS_RW_LOCK_EX *)BwcVirtualLine;
        *(_DWORD *)(NextExpiredTimerWheelEntry + 20) = v9;
        if ( (unsigned __int8)QosFlowNeedQueueFeedback(NextExpiredTimerWheelEntry - 8 + 40, v16, v36) && v17 )
        {
          NdisAcquireRWLockWrite(*v17, &LockState, 1u);
          if ( (unsigned __int8)QosLineNeedSignal(v17 + 1, (unsigned int)CurrentProcessorNumber) )
            QosLineSignalExternalEvent(v17 + 1, (unsigned int)CurrentProcessorNumber);
          QosLineQueryQueueFeedback(v17 + 1, v18, v36);
          NdisReleaseRWLock(*v17, &LockState);
          QosTbcAdjustSendWindow(v14 + 40, v36);
          LODWORD(v10) = v27;
        }
        if ( (unsigned __int8)QosFlowProcessQueuedNetBufferLists(
                                (int)v14 + 40,
                                CurrentProcessorNumber,
                                (unsigned int)&v29,
                                (unsigned int)&v25,
                                (__int64)&v26) )
        {
          v19 = *(_QWORD *)(*(_QWORD *)(v14 + 136) + 24LL) / 0xFAuLL;
          v20 = v19 + 1;
          if ( (int)v19 - (int)v10 > 0 )
            v20 = *(_QWORD *)(*(_QWORD *)(v14 + 136) + 24LL) / 0xFAuLL;
          if ( !v20 )
            v20 = 1;
          *(_DWORD *)(NextExpiredTimerWheelEntry + 20) = v20;
        }
        RtlAcquireWriteLockAtDpcLevel(DeferredContext, &LockHandle);
        RtlReturnTimerWheelEntry(*((_QWORD *)DeferredContext + 20), NextExpiredTimerWheelEntry);
        v21 = *((_QWORD *)DeferredContext + 20);
        v35 = *(_QWORD *)NextExpiredTimerWheelEntry;
        NextExpiredTimerWheelEntry = RtlGetNextExpiredTimerWheelEntry(v21);
        KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
        if ( v26 )
          BwcDropNbls(v14, v17, v26, &v28);
        KeReleaseSpinLock((PKSPIN_LOCK)(v14 + 472), *(_BYTE *)(v14 + 480));
        if ( v28 )
          ((void (__fastcall *)(__int64, __int64))DropQueuedNonConformantNbls)(v14, v28);
        v9 = v29;
        if ( v29 )
        {
          if ( (unsigned __int8)QosLineNeedSignal(v17 + 1, (unsigned int)CurrentProcessorNumber) )
          {
            NdisAcquireRWLockWrite(*v17, &LockState, 1u);
            QosLineSignalExternalEvent(v17 + 1, (unsigned int)CurrentProcessorNumber);
            NdisReleaseRWLock(*v17, &LockState);
          }
          QosLineSendNetBufferLists((_DWORD)v17 + 8, v22, v9, v23, (__int64)&v30, (__int64)&v26);
          v9 = 0;
          v31 = 0;
          BwcCompleteNbls(v14, v17, v30, &v31);
          if ( v31 )
            BwcSendProcessedNbls(v14, v31);
        }
        if ( v35 == v34 )
          BwcDereferenceFlow(v14);
        LODWORD(v10) = v27;
      }
      while ( NextExpiredTimerWheelEntry );
      CurrentTime = v32;
    }
    RtlAcquireWriteLockAtDpcLevel(DeferredContext, &LockHandle);
  }
  NextExpirationTimerWheelTick = RtlGetNextExpirationTimerWheelTick(*((_QWORD *)DeferredContext + 20));
  if ( NextExpirationTimerWheelTick )
  {
    BwcSetTimer(DeferredContext, CurrentTime, CurrentTime + 250LL * (unsigned int)(NextExpirationTimerWheelTick - v10));
  }
  else
  {
    if ( !(unsigned __int8)RtlIsTimerWheelSuspended(*((_QWORD *)DeferredContext + 20)) )
      RtlSuspendTimerWheel(*((_QWORD *)DeferredContext + 20));
    *((_DWORD *)DeferredContext + 43) |= 1u;
    KeCancelTimer((PKTIMER)(DeferredContext + 96));
  }
  KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  BwcIndicateDelayQueueConsumerEnd((unsigned int)CurrentProcessorNumber);
}

```

## disassembly

```asm
0x140013080  push    rbp
0x140013082  push    rbx
0x140013083  push    rsi
0x140013084  push    rdi
0x140013085  push    r12
0x140013087  push    r13
0x140013089  push    r14
0x14001308b  push    r15
0x14001308d  lea     rbp, [rsp-1Fh]
0x140013092  sub     rsp, 0C8h
0x140013099  xor     eax, eax
0x14001309b  xorps   xmm0, xmm0
0x14001309e  xor     ecx, ecx; ProcNumber
0x1400130a0  mov     [rbp+57h+var_48], eax
0x1400130a3  movups  [rbp+57h+var_68], xmm0
0x1400130a7  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x1400130ab  mov     rbx, rdx
0x1400130ae  movups  [rbp+57h+var_58], xmm0
0x1400130b2  mov     word ptr [rbp+57h+LockState.OldIrql], ax
0x1400130b6  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x1400130ba  mov     [rbp+57h+LockState.Flags], al
0x1400130bd  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400130c4  nop     dword ptr [rax+rax+00h]
0x1400130c9  mov     esi, 1
0x1400130ce  mov     r15d, eax
0x1400130d1  mov     r8b, sil
0x1400130d4  mov     dl, sil
0x1400130d7  mov     ecx, eax
0x1400130d9  call    QosTimerGetCurrentTime
0x1400130de  mov     rdi, rax
0x1400130e1  mov     [rbp+57h+var_98], rax
0x1400130e5  xor     r13d, r13d
0x1400130e8  mov     rax, 624DD2F1A9FBE77h
0x1400130f2  mul     rdi
0x1400130f5  mov     rax, cs:BwcDelayQueue
0x1400130fc  mov     r12, rdi
0x1400130ff  sub     r12, rdx
0x140013102  mov     [rbp+57h+var_B0], r13
0x140013106  shr     r12, 1
0x140013109  mov     ecx, r15d
0x14001310c  shl     rcx, 6
0x140013110  add     r12, rdx
0x140013113  shr     r12, 7
0x140013117  lea     rdx, [rbp+57h+LockHandle]
0x14001311b  mov     [rbp+57h+var_C0], r12
0x14001311f  mov     [rbp+57h+var_C8], r13
0x140013123  add     [rcx+rax+10h], esi
0x140013127  mov     rcx, rbx
0x14001312a  mov     [rbp+57h+var_A8], r13
0x14001312e  mov     [rbp+57h+var_B8], r13
0x140013132  mov     [rbp+57h+var_D0], r13d
0x140013136  call    RtlAcquireWriteLockAtDpcLevel
0x14001313b  mov     eax, [rbx+0ACh]
0x140013141  mov     ecx, eax
0x140013143  shr     ecx, 1
0x140013145  and     eax, 0FFFFFFFEh
0x140013148  not     ecx
0x14001314a  mov     [rbx+10h], rdi
0x14001314e  and     ecx, esi
0x140013150  or      ecx, eax
0x140013152  mov     [rbx+0ACh], ecx
0x140013158  mov     rcx, [rbx+0A0h]
0x14001315f  call    cs:__imp_RtlIsTimerWheelSuspended
0x140013166  nop     dword ptr [rax+rax+00h]
0x14001316b  test    al, al
0x14001316d  jnz     loc_140013432
0x140013173  mov     rcx, [rbx+0A0h]
0x14001317a  mov     edx, r12d
0x14001317d  call    cs:__imp_RtlUpdateCurrentTimerWheelTick
0x140013184  nop     dword ptr [rax+rax+00h]
0x140013189  mov     rcx, [rbx+0A0h]
0x140013190  call    cs:__imp_RtlGetNextExpiredTimerWheelEntry
0x140013197  nop     dword ptr [rax+rax+00h]
0x14001319c  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x1400131a0  mov     r14, rax
0x1400131a3  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x1400131aa  nop     dword ptr [rax+rax+00h]
0x1400131af  test    r14, r14
0x1400131b2  jz      loc_140013426
0x1400131b8  lea     rdi, [r14-8]
0x1400131bc  mov     [rbp+57h+var_78], r14
0x1400131c0  lea     rcx, [rdi+1D8h]; SpinLock
0x1400131c7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400131ce  nop     dword ptr [rax+rax+00h]
0x1400131d3  mov     rdx, [rbp+57h+var_98]
0x1400131d7  lea     r8, [rbp+57h+var_68]
0x1400131db  mov     [rdi+1E0h], al
0x1400131e1  mov     rsi, cs:BwcVirtualLine
0x1400131e8  mov     [r14+14h], r13d
0x1400131ec  lea     r13, [rdi+28h]
0x1400131f0  mov     rcx, r13
0x1400131f3  call    QosFlowNeedQueueFeedback
0x1400131f8  test    al, al
0x1400131fa  jz      short loc_140013264
0x1400131fc  test    rsi, rsi
0x1400131ff  jz      short loc_140013264
0x140013201  mov     rcx, [rsi]; Lock
0x140013204  lea     rdx, [rbp+57h+LockState]; LockState
0x140013208  mov     r8b, 1; Flags
0x14001320b  call    cs:__imp_NdisAcquireRWLockWrite
0x140013212  nop     dword ptr [rax+rax+00h]
0x140013217  lea     r12, [rsi+8]
0x14001321b  mov     edx, r15d
0x14001321e  mov     rcx, r12
0x140013221  call    QosLineNeedSignal
0x140013226  test    al, al
0x140013228  jz      short loc_140013235
0x14001322a  mov     edx, r15d
0x14001322d  mov     rcx, r12
0x140013230  call    QosLineSignalExternalEvent
0x140013235  lea     r8, [rbp+57h+var_68]
0x140013239  mov     rcx, r12
0x14001323c  call    QosLineQueryQueueFeedback
0x140013241  mov     rcx, [rsi]; Lock
0x140013244  lea     rdx, [rbp+57h+LockState]; LockState
0x140013248  call    cs:__imp_NdisReleaseRWLock
0x14001324f  nop     dword ptr [rax+rax+00h]
0x140013254  lea     rdx, [rbp+57h+var_68]
0x140013258  mov     rcx, r13
0x14001325b  call    QosTbcAdjustSendWindow
0x140013260  mov     r12, [rbp+57h+var_C0]
0x140013264  lea     rax, [rbp+57h+var_C8]
0x140013268  mov     edx, r15d
0x14001326b  lea     r9, [rbp+57h+var_D0]
0x14001326f  mov     [rsp+100h+var_E0], rax
0x140013274  lea     r8, [rbp+57h+var_B0]
0x140013278  mov     rcx, r13
0x14001327b  call    QosFlowProcessQueuedNetBufferLists
0x140013280  test    al, al
0x140013282  jz      short loc_1400132C7
0x140013284  mov     rax, [rdi+88h]
0x14001328b  mov     r8, [rax+18h]
0x14001328f  mov     rax, 624DD2F1A9FBE77h
0x140013299  mul     r8
0x14001329c  sub     r8, rdx
0x14001329f  shr     r8, 1
0x1400132a2  add     r8, rdx
0x1400132a5  shr     r8, 7
0x1400132a9  mov     eax, r8d
0x1400132ac  sub     eax, r12d
0x1400132af  test    eax, eax
0x1400132b1  mov     eax, 1
0x1400132b6  lea     ecx, [r8+1]
0x1400132ba  cmovg   ecx, r8d
0x1400132be  test    ecx, ecx
0x1400132c0  cmovz   ecx, eax
0x1400132c3  mov     [r14+14h], ecx
0x1400132c7  lea     rdx, [rbp+57h+LockHandle]
0x1400132cb  mov     rcx, rbx
0x1400132ce  call    RtlAcquireWriteLockAtDpcLevel
0x1400132d3  mov     rcx, [rbx+0A0h]
0x1400132da  mov     rdx, r14
0x1400132dd  call    cs:__imp_RtlReturnTimerWheelEntry
0x1400132e4  nop     dword ptr [rax+rax+00h]
0x1400132e9  mov     rax, [r14]
0x1400132ec  mov     rcx, [rbx+0A0h]
0x1400132f3  mov     [rbp+57h+var_70], rax
0x1400132f7  call    cs:__imp_RtlGetNextExpiredTimerWheelEntry
0x1400132fe  nop     dword ptr [rax+rax+00h]
0x140013303  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x140013307  mov     r14, rax
0x14001330a  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140013311  nop     dword ptr [rax+rax+00h]
0x140013316  mov     r8, [rbp+57h+var_C8]
0x14001331a  test    r8, r8
0x14001331d  jz      short loc_14001332E
0x14001331f  lea     r9, [rbp+57h+var_B8]
0x140013323  mov     rdx, rsi
0x140013326  mov     rcx, rdi
0x140013329  call    BwcDropNbls
0x14001332e  mov     dl, [rdi+1E0h]; NewIrql
0x140013334  lea     rcx, [rdi+1D8h]; SpinLock
0x14001333b  call    cs:__imp_KeReleaseSpinLock
0x140013342  nop     dword ptr [rax+rax+00h]
0x140013347  mov     rcx, [rbp+57h+var_B8]
0x14001334b  test    rcx, rcx
0x14001334e  jz      short loc_140013362
0x140013350  mov     rax, cs:DropQueuedNonConformantNbls
0x140013357  mov     rdx, rcx
0x14001335a  mov     rcx, rdi
0x14001335d  call    _guard_dispatch_icall
0x140013362  mov     r13, [rbp+57h+var_B0]
0x140013366  test    r13, r13
0x140013369  jz      loc_1400133FE
0x14001336f  lea     r12, [rsi+8]
0x140013373  mov     edx, r15d
0x140013376  mov     rcx, r12
0x140013379  call    QosLineNeedSignal
0x14001337e  test    al, al
0x140013380  jz      short loc_1400133B6
0x140013382  mov     rcx, [rsi]; Lock
0x140013385  lea     rdx, [rbp+57h+LockState]; LockState
0x140013389  mov     r8b, 1; Flags
0x14001338c  call    cs:__imp_NdisAcquireRWLockWrite
0x140013393  nop     dword ptr [rax+rax+00h]
0x140013398  mov     edx, r15d
0x14001339b  mov     rcx, r12
0x14001339e  call    QosLineSignalExternalEvent
0x1400133a3  mov     rcx, [rsi]; Lock
0x1400133a6  lea     rdx, [rbp+57h+LockState]; LockState
0x1400133aa  call    cs:__imp_NdisReleaseRWLock
0x1400133b1  nop     dword ptr [rax+rax+00h]
0x1400133b6  lea     rax, [rbp+57h+var_C8]
0x1400133ba  mov     r8, r13
0x1400133bd  mov     [rsp+100h+var_D8], rax
0x1400133c2  mov     rcx, r12
0x1400133c5  lea     rax, [rbp+57h+var_A8]
0x1400133c9  mov     [rsp+100h+var_E0], rax
0x1400133ce  call    QosLineSendNetBufferLists
0x1400133d3  mov     r8, [rbp+57h+var_A8]
0x1400133d7  lea     r9, [rbp+57h+var_A0]
0x1400133db  xor     r13d, r13d
0x1400133de  mov     rdx, rsi
0x1400133e1  mov     rcx, rdi
0x1400133e4  mov     [rbp+57h+var_A0], r13
0x1400133e8  call    BwcCompleteNbls
0x1400133ed  mov     rdx, [rbp+57h+var_A0]
0x1400133f1  test    rdx, rdx
0x1400133f4  jz      short loc_1400133FE
0x1400133f6  mov     rcx, rdi
0x1400133f9  call    BwcSendProcessedNbls
0x1400133fe  mov     rax, [rbp+57h+var_78]
0x140013402  cmp     [rbp+57h+var_70], rax
0x140013406  jnz     short loc_140013410
0x140013408  mov     rcx, rdi
0x14001340b  call    BwcDereferenceFlow
0x140013410  mov     r12, [rbp+57h+var_C0]
0x140013414  test    r14, r14
0x140013417  jnz     loc_1400131B8
0x14001341d  mov     rdi, [rbp+57h+var_98]
0x140013421  mov     esi, 1
0x140013426  lea     rdx, [rbp+57h+LockHandle]
0x14001342a  mov     rcx, rbx
0x14001342d  call    RtlAcquireWriteLockAtDpcLevel
0x140013432  mov     rcx, [rbx+0A0h]
0x140013439  call    cs:__imp_RtlGetNextExpirationTimerWheelTick
0x140013440  nop     dword ptr [rax+rax+00h]
0x140013445  test    eax, eax
0x140013447  jnz     short loc_14001348B
0x140013449  mov     rcx, [rbx+0A0h]
0x140013450  call    cs:__imp_RtlIsTimerWheelSuspended
0x140013457  nop     dword ptr [rax+rax+00h]
0x14001345c  test    al, al
0x14001345e  jnz     short loc_140013473
0x140013460  mov     rcx, [rbx+0A0h]
0x140013467  call    cs:__imp_RtlSuspendTimerWheel
0x14001346e  nop     dword ptr [rax+rax+00h]
0x140013473  or      [rbx+0ACh], esi
0x140013479  lea     rcx, [rbx+60h]; PKTIMER
0x14001347d  call    cs:__imp_KeCancelTimer
0x140013484  nop     dword ptr [rax+rax+00h]
0x140013489  jmp     short loc_1400134A3
0x14001348b  sub     eax, r12d
0x14001348e  mov     rdx, rdi
0x140013491  imul    r8, rax, 0FAh
0x140013498  mov     rcx, rbx
0x14001349b  add     r8, rdi
0x14001349e  call    BwcSetTimer
0x1400134a3  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x1400134a7  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x1400134ae  nop     dword ptr [rax+rax+00h]
0x1400134b3  mov     ecx, r15d
0x1400134b6  call    BwcIndicateDelayQueueConsumerEnd
0x1400134bb  add     rsp, 0C8h
0x1400134c2  pop     r15
0x1400134c4  pop     r14
0x1400134c6  pop     r13
0x1400134c8  pop     r12
0x1400134ca  pop     rdi
0x1400134cb  pop     rsi
0x1400134cc  pop     rbx
0x1400134cd  pop     rbp
0x1400134ce  retn
```
