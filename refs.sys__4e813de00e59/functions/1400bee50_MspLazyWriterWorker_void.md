# MspLazyWriterWorker(void *)

- ea: `0x1400bee50`
- end: `0x1400bf33a`
- name: `?MspLazyWriterWorker@@YAXPEAX@Z`
- size: `1258`
- prototype: `void __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x140008c40`
- `0x140022ba8`
- `0x14002b3e0`
- `0x140047580`
- `0x14005c048`
- `0x140089a80`
- `0x14008ac80`
- `0x1400bee50`
- `0x1400cfad4`
- `0x14011d3a8`
- `0x1401f40a0`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x1400bf321`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400bf321`
- `ntoskrnl!IoClearActivityIdThread` at `0x1400bf274`
- `ntoskrnl!IoClearActivityIdThread` at `0x1400bf274`
- `ntoskrnl!KeSetEvent` at `0x1400bf0fd`
- `ntoskrnl!KeSetEvent` at `0x1400bf2da`
- `ntoskrnl!KeSetEvent` at `0x1400bf0fd`
- `ntoskrnl!KeSetEvent` at `0x1400bf2da`
- `ntoskrnl!IoSetActivityIdThread` at `0x1400bf166`
- `ntoskrnl!IoSetActivityIdThread` at `0x1400bf166`
- `ntoskrnl!IoTransferActivityId` at `0x1400bf189`
- `ntoskrnl!IoTransferActivityId` at `0x1400bf189`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400beea8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400bf08d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400beea8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400bf08d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400befc8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400beff1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400bf0e4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400befc8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400beff1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400bf0e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bf00c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bf114`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bf00c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bf114`

## pseudocode

```c
void __fastcall MspLazyWriterWorker(PVOID P)
{
  PVOID v1; // r14
  unsigned int v2; // ebx
  volatile signed __int32 *v3; // rdx
  _QWORD **v4; // r9
  _QWORD *v5; // r8
  __int64 v6; // rax
  __int64 v7; // rax
  unsigned __int8 v8; // cl
  int v9; // eax
  _QWORD *v10; // rcx
  _QWORD *v11; // rax
  volatile signed __int32 *v12; // rdi
  __int64 v13; // rsi
  volatile signed __int32 *v14; // r14
  volatile signed __int32 *v15; // r12
  __int64 v16; // rcx
  volatile signed __int32 **v17; // rax
  volatile signed __int32 v18; // ebx
  volatile signed __int32 *v19; // rbx
  struct CmsTransactionContext *v20; // rax
  struct CmsTransactionContext *v21; // r13
  int TransactionContext; // r15d
  struct CmsTransactionContext *v23; // rdi
  __int64 v24; // rdx
  __int64 v25; // r9
  int v26; // edi
  signed __int32 v27; // [rsp+50h] [rbp-A8h]
  int v28; // [rsp+54h] [rbp-A4h] BYREF
  struct CmsTransactionContext *v29[6]; // [rsp+58h] [rbp-A0h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+88h] [rbp-70h] BYREF
  struct _KLOCK_QUEUE_HANDLE v31; // [rsp+A0h] [rbp-58h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+108h] [rbp+10h] BYREF
  int v34; // [rsp+110h] [rbp+18h]
  int v35; // [rsp+118h] [rbp+20h]

  v1 = P;
  v29[0] = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  while ( 1 )
  {
    v2 = 0;
    Interval.LowPart = 0;
    while ( 1 )
    {
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(0x140000000LL + 8LL * v2 + 2527848), &LockHandle);
      v3 = 0;
      v4 = (_QWORD **)(0x140000000LL + 16LL * v2 + 2527800);
      v5 = *v4;
      if ( *v4 != v4 )
      {
        while ( 1 )
        {
          v3 = (volatile signed __int32 *)(v5 - 3);
          v6 = v5[8];
          if ( (!v6
             || *(_DWORD *)(v6 + 2772) < LazyWriterMaxWorkersPerVolume
             || !v2 && *(_DWORD *)(*((_QWORD *)v3 + 11) + 2772LL) < LazyWriterMaxLogWorkersPerVolume)
            && (v3[4] & 0x10) == 0 )
          {
            _m_prefetchw((const void *)(v3 + 4));
            v27 = _InterlockedOr(v3 + 4, 0x10u) & 0x10;
            v28 = 0;
            v7 = 0;
            while ( 1 )
            {
              v8 = *((_BYTE *)&v27 + v7++);
              if ( v8 != *((_BYTE *)&v28 + v7 - 1) )
                break;
              if ( v7 == 4 )
              {
                v9 = 0;
                goto LABEL_14;
              }
            }
            v9 = v8 < *((_BYTE *)&v28 + v7 - 1) ? -1 : 1;
LABEL_14:
            if ( !v9 )
              break;
          }
          v5 = (_QWORD *)*v5;
          if ( v5 == v4 )
            goto LABEL_20;
        }
        *((_DWORD *)v3 + 20) = 3;
        v10 = (_QWORD *)*v5;
        if ( *(_QWORD **)(*v5 + 8LL) != v5 )
          goto LABEL_38;
        v11 = (_QWORD *)v5[1];
        if ( (_QWORD *)*v11 != v5 )
          goto LABEL_38;
        *v11 = v10;
        v10[1] = v11;
        v5[1] = v5;
        *v5 = v5;
        --*((_DWORD *)&WorkerEntriesQueueCount + v2);
      }
LABEL_20:
      v12 = 0;
      if ( v5 != v4 )
        v12 = v3;
      if ( v12 )
        goto LABEL_27;
      if ( v2 == 2 )
        break;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      Interval.LowPart = ++v2;
      if ( v2 >= 3 )
        goto LABEL_28;
    }
    _InterlockedDecrement(&LazyWriterWorkersActive);
LABEL_27:
    KeReleaseInStackQueuedSpinLock(&LockHandle);
LABEL_28:
    if ( !v12 )
      break;
    _InterlockedDecrement(&LazyWriterEntries);
    v13 = *((_QWORD *)v12 + 11);
    v14 = (volatile signed __int32 *)(v13 + 2772);
    v29[3] = (struct CmsTransactionContext *)(v13 + 2772);
    _InterlockedIncrement((volatile signed __int32 *)(v13 + 2772));
    _InterlockedDecrement((volatile signed __int32 *)(v13 + 2776));
    v15 = v12 + 4;
    v29[4] = (struct CmsTransactionContext *)(v12 + 4);
    if ( (v12[4] & 8) != 0 )
    {
      memset(&v31, 0, sizeof(v31));
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink, &v31);
      v16 = *(_QWORD *)v12;
      if ( *(volatile signed __int32 **)(*(_QWORD *)v12 + 8LL) != v12
        || (v17 = (volatile signed __int32 **)*((_QWORD *)v12 + 1), *v17 != v12) )
      {
LABEL_38:
        __fastfail(3u);
      }
      *v17 = (volatile signed __int32 *)v16;
      *(_QWORD *)(v16 + 8) = v17;
      *((_QWORD *)v12 + 1) = v12;
      *(_QWORD *)v12 = v12;
      _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)v12 + 11) + 2800LL));
      --NumberOfDirtyTableListEntries;
      MspUnqueueEntry((struct _SmsLazyWriterEntry *)v12);
      KeReleaseInStackQueuedSpinLock(&v31);
      v18 = *v15;
      KeSetEvent(*((PRKEVENT *)v12 + 13), 0, 0);
      if ( (v18 & 0x20) == 0 )
        ExFreePoolWithTag((PVOID)v12, 0);
      _InterlockedDecrement(v14);
      v1 = P;
    }
    else
    {
      v29[1] = (struct CmsTransactionContext *)v13;
      v19 = (volatile signed __int32 *)*((_QWORD *)v12 - 74);
      v29[5] = (struct CmsTransactionContext *)v19;
      v34 = *((_DWORD *)v12 + 14);
      v35 = v34;
      v20 = (struct CmsTransactionContext *)IoSetActivityIdThread(v13 + 2756);
      v21 = v20;
      v29[2] = v20;
      if ( v20 )
        IoTransferActivityId(v13 + 2756, v20);
      TransactionContext = MsCreateTransactionContext((PSLIST_ENTRY *)v29, v13);
      if ( TransactionContext >= 0 )
      {
        v23 = v29[0];
        *(_QWORD *)v29[0] |= 0x10000uLL;
        if ( Interval.LowPart == 2 )
        {
          CmsBPlusTable::DelayedReleaseCachedPinList((CmsBPlusTable *)v19, v23);
        }
        else
        {
          if ( (*(_DWORD *)(v13 + 3396) & 0x20000000) != 0 || (v25 = 1, !*(_BYTE *)(v13 + 3393)) )
            v25 = 2;
          TransactionContext = (*(__int64 (__fastcall **)(volatile signed __int32 *, struct CmsTransactionContext *, _QWORD, __int64, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v19 + 64LL))(
                                 v19,
                                 v23,
                                 0,
                                 v25,
                                 0,
                                 0,
                                 0,
                                 0);
        }
        if ( TransactionContext < 0 )
          MsAbortTransaction(v23);
        else
          MsCommitTransaction(v23, v24, 0);
        MsDeleteTransactionContext(v23);
      }
      v26 = v34;
      IoClearActivityIdThread(v21);
      _InterlockedDecrement(v14);
      _InterlockedAnd(v15, 0xFFFFFFEF);
      _InterlockedAdd64(&PagesQueuedForWriting, -v26);
      if ( CmsDurableLog::GetPercentageLogFreedIfAdvanced((CmsDurableLog *)(v13 + 2816)) >= (unsigned __int8)byte_14026907C
        && CmsDurableLog::GetLogFullPercentage((CmsDurableLog *)(v13 + 2816)) >= (unsigned int)(unsigned __int8)byte_14026907A )
      {
        KeSetEvent(&LazyWriterScanEvent, 0, 0);
      }
      if ( _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 && v19 )
        (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v19)(v19, 1);
      Interval.QuadPart = 0;
      KeDelayExecutionThread(0, 0, &Interval);
      v1 = P;
    }
  }
  if ( v1 )
    ExFreePoolWithTag(v1, 0);
}

```

## disassembly

```asm
0x1400bee50  mov     r11, rsp
0x1400bee53  mov     [r11+8], rcx
0x1400bee57  push    rbx
0x1400bee58  push    rsi
0x1400bee59  push    rdi
0x1400bee5a  push    r12
0x1400bee5c  push    r13
0x1400bee5e  push    r14
0x1400bee60  push    r15
0x1400bee62  sub     rsp, 0C0h
0x1400bee69  mov     r14, rcx
0x1400bee6c  xor     r15d, r15d
0x1400bee6f  mov     [rsp+0F8h+var_A0], r15
0x1400bee74  xorps   xmm0, xmm0
0x1400bee77  xor     eax, eax
0x1400bee79  movups  xmmword ptr [r11-70h], xmm0
0x1400bee7e  mov     [r11-60h], rax
0x1400bee82  lea     rsi, cs:140000000h
0x1400bee89  mov     ebx, r15d
0x1400bee8c  mov     dword ptr [rsp+0F8h+Interval], ebx
0x1400bee93  mov     edi, ebx
0x1400bee95  lea     rcx, ds:269268h[rdi*8]
0x1400bee9d  add     rcx, rsi; SpinLock
0x1400beea0  lea     rdx, [rsp+0F8h+LockHandle]; LockHandle
0x1400beea8  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400beeaf  nop     dword ptr [rax+rax+00h]
0x1400beeb4  mov     rdx, r15
0x1400beeb7  mov     eax, ebx
0x1400beeb9  shl     rax, 4
0x1400beebd  lea     r9, [rax+269238h]
0x1400beec4  add     r9, rsi
0x1400beec7  mov     r8, [r9]
0x1400beeca  cmp     r8, r9
0x1400beecd  jz      loc_1400BEFAC
0x1400beed3  lea     rdx, [r8-18h]
0x1400beed7  mov     rax, [rdx+58h]
0x1400beedb  test    rax, rax
0x1400beede  jz      short loc_1400BEF04
0x1400beee0  mov     eax, [rax+0AD4h]
0x1400beee6  cmp     eax, cs:?LazyWriterMaxWorkersPerVolume@@3JA; long LazyWriterMaxWorkersPerVolume
0x1400beeec  jl      short loc_1400BEF04
0x1400beeee  test    ebx, ebx
0x1400beef0  jnz     short loc_1400BEF68
0x1400beef2  mov     rcx, [rdx+58h]
0x1400beef6  mov     eax, cs:?LazyWriterMaxLogWorkersPerVolume@@3JA; long LazyWriterMaxLogWorkersPerVolume
0x1400beefc  cmp     [rcx+0AD4h], eax
0x1400bef02  jge     short loc_1400BEF68
0x1400bef04  mov     eax, [rdx+10h]
0x1400bef07  test    al, 10h
0x1400bef09  jnz     short loc_1400BEF68
0x1400bef0b  nop
0x1400bef0c  prefetchw byte ptr [rdx+10h]
0x1400bef10  mov     eax, [rdx+10h]
0x1400bef13  mov     ecx, eax
0x1400bef15  or      ecx, 10h
0x1400bef18  lock cmpxchg [rdx+10h], ecx
0x1400bef1d  jnz     short loc_1400BEF13
0x1400bef1f  nop
0x1400bef20  and     eax, 10h
0x1400bef23  mov     [rsp+0F8h+var_A8], eax
0x1400bef27  mov     [rsp+0F8h+var_A4], r15d
0x1400bef2c  mov     rax, r15
0x1400bef2f  lea     r10, [rsp+0F8h+var_A8]
0x1400bef34  lea     r11, [rsp+0F8h+var_A4]
0x1400bef39  nop     dword ptr [rax+00000000h]
0x1400bef40  movzx   ecx, byte ptr [r10+rax]
0x1400bef45  inc     rax
0x1400bef48  cmp     cl, [r11+rax-1]
0x1400bef4d  jnz     short loc_1400BEF5A
0x1400bef4f  cmp     rax, 4
0x1400bef53  jnz     short loc_1400BEF40
0x1400bef55  mov     eax, r15d
0x1400bef58  jmp     short loc_1400BEF5F
0x1400bef5a  sbb     eax, eax
0x1400bef5c  or      eax, 1
0x1400bef5f  test    eax, eax
0x1400bef61  setz    al
0x1400bef64  test    al, al
0x1400bef66  jnz     short loc_1400BEF76
0x1400bef68  mov     r8, [r8]
0x1400bef6b  cmp     r8, r9
0x1400bef6e  jnz     loc_1400BEED3
0x1400bef74  jmp     short loc_1400BEFAC
0x1400bef76  mov     dword ptr [rdx+50h], 3
0x1400bef7d  mov     rcx, [r8]
0x1400bef80  cmp     [rcx+8], r8
0x1400bef84  jnz     loc_1400BF133
0x1400bef8a  mov     rax, [r8+8]
0x1400bef8e  cmp     [rax], r8
0x1400bef91  jnz     loc_1400BF133
0x1400bef97  mov     [rax], rcx
0x1400bef9a  mov     [rcx+8], rax
0x1400bef9e  mov     [r8+8], r8
0x1400befa2  mov     [r8], r8
0x1400befa5  dec     rva ?WorkerEntriesQueueCount@@3PAJA[rsi+rdi*4]; long near * WorkerEntriesQueueCount ...
0x1400befac  mov     rdi, r15
0x1400befaf  cmp     r8, r9
0x1400befb2  cmovnz  rdi, rdx
0x1400befb6  lea     rcx, [rsp+0F8h+LockHandle]; LockHandle
0x1400befbe  test    rdi, rdi
0x1400befc1  jnz     short loc_1400BEFF1
0x1400befc3  cmp     ebx, 2
0x1400befc6  jz      short loc_1400BEFE8
0x1400befc8  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400befcf  nop     dword ptr [rax+rax+00h]
0x1400befd4  inc     ebx
0x1400befd6  mov     dword ptr [rsp+0F8h+Interval], ebx
0x1400befdd  cmp     ebx, 3
0x1400befe0  jb      loc_1400BEE93
0x1400befe6  jmp     short loc_1400BEFFD
0x1400befe8  nop
0x1400befe9  lock dec cs:?LazyWriterWorkersActive@@3JA; long LazyWriterWorkersActive
0x1400beff0  nop
0x1400beff1  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400beff8  nop     dword ptr [rax+rax+00h]
0x1400beffd  test    rdi, rdi
0x1400bf000  jnz     short loc_1400BF02C
0x1400bf002  test    r14, r14
0x1400bf005  jz      short loc_1400BF018
0x1400bf007  xor     edx, edx; Tag
0x1400bf009  mov     rcx, r14; P
0x1400bf00c  call    cs:__imp_ExFreePoolWithTag
0x1400bf013  nop     dword ptr [rax+rax+00h]
0x1400bf018  add     rsp, 0C0h
0x1400bf01f  pop     r15
0x1400bf021  pop     r14
0x1400bf023  pop     r13
0x1400bf025  pop     r12
0x1400bf027  pop     rdi
0x1400bf028  pop     rsi
0x1400bf029  pop     rbx
0x1400bf02a  retn
0x1400bf02c  nop
0x1400bf02d  lock dec cs:?LazyWriterEntries@@3JA; long LazyWriterEntries
0x1400bf034  nop
0x1400bf035  mov     rsi, [rdi+58h]
0x1400bf039  nop
0x1400bf03a  lea     r14, [rsi+0AD4h]
0x1400bf041  mov     [rsp+0F8h+var_88], r14
0x1400bf046  lock inc dword ptr [r14]
0x1400bf04a  nop
0x1400bf04b  nop
0x1400bf04c  lock dec dword ptr [rsi+0AD8h]
0x1400bf053  nop
0x1400bf054  lea     r12, [rdi+10h]
0x1400bf058  mov     [rsp+0F8h+var_80], r12
0x1400bf05d  mov     eax, [r12]
0x1400bf061  test    al, 8
0x1400bf063  jz      loc_1400BF13A
0x1400bf069  xorps   xmm0, xmm0
0x1400bf06c  xor     eax, eax
0x1400bf06e  movups  xmmword ptr [rsp+0F8h+var_58.LockQueue.Next], xmm0
0x1400bf076  mov     qword ptr [rsp+0F8h+var_58.OldIrql], rax
0x1400bf07e  lea     rdx, [rsp+0F8h+var_58]; LockHandle
0x1400bf086  lea     rcx, WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink; SpinLock
0x1400bf08d  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400bf094  nop     dword ptr [rax+rax+00h]
0x1400bf099  mov     rcx, [rdi]
0x1400bf09c  cmp     [rcx+8], rdi
0x1400bf0a0  jnz     loc_1400BF133
0x1400bf0a6  mov     rax, [rdi+8]
0x1400bf0aa  cmp     [rax], rdi
0x1400bf0ad  jnz     loc_1400BF133
0x1400bf0b3  mov     [rax], rcx
0x1400bf0b6  mov     [rcx+8], rax
0x1400bf0ba  mov     [rdi+8], rdi
0x1400bf0be  mov     [rdi], rdi
0x1400bf0c1  mov     rax, [rdi+58h]
0x1400bf0c5  nop
0x1400bf0c6  lock dec dword ptr [rax+0AF0h]
0x1400bf0cd  nop
0x1400bf0ce  dec     cs:?NumberOfDirtyTableListEntries@@3KA; ulong NumberOfDirtyTableListEntries
0x1400bf0d4  mov     rcx, rdi; struct _SmsLazyWriterEntry *
0x1400bf0d7  call    ?MspUnqueueEntry@@YAEPEAU_SmsLazyWriterEntry@@@Z; MspUnqueueEntry(_SmsLazyWriterEntry *)
0x1400bf0dc  lea     rcx, [rsp+0F8h+var_58]; LockHandle
0x1400bf0e4  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400bf0eb  nop     dword ptr [rax+rax+00h]
0x1400bf0f0  mov     ebx, [r12]
0x1400bf0f4  xor     r8d, r8d; Wait
0x1400bf0f7  xor     edx, edx; Increment
0x1400bf0f9  mov     rcx, [rdi+68h]; Event
0x1400bf0fd  call    cs:__imp_KeSetEvent
0x1400bf104  nop     dword ptr [rax+rax+00h]
0x1400bf109  bt      ebx, 5
0x1400bf10d  jb      short loc_1400BF120
0x1400bf10f  xor     edx, edx; Tag
0x1400bf111  mov     rcx, rdi; P
0x1400bf114  call    cs:__imp_ExFreePoolWithTag
0x1400bf11b  nop     dword ptr [rax+rax+00h]
0x1400bf120  nop
0x1400bf121  lock dec dword ptr [r14]
0x1400bf125  nop
0x1400bf126  mov     r14, [rsp+0F8h+arg_0]
0x1400bf12e  jmp     loc_1400BEE82
0x1400bf133  mov     ecx, 3
0x1400bf138  int     29h; Win8: RtlFailFast(ecx)
0x1400bf13a  mov     [rsp+0F8h+var_98], rsi
0x1400bf13f  mov     rbx, [rdi-250h]
0x1400bf146  mov     [rsp+0F8h+var_78], rbx
0x1400bf14e  mov     eax, [rdi+38h]
0x1400bf151  mov     [rsp+0F8h+arg_10], eax
0x1400bf158  mov     [rsp+0F8h+arg_18], eax
0x1400bf15f  lea     rcx, [rsi+0AC4h]
0x1400bf166  call    cs:__imp_IoSetActivityIdThread
0x1400bf16d  nop     dword ptr [rax+rax+00h]
0x1400bf172  mov     r13, rax
0x1400bf175  mov     [rsp+0F8h+var_90], rax
0x1400bf17a  test    rax, rax
0x1400bf17d  jz      short loc_1400BF196
0x1400bf17f  mov     rdx, rax
0x1400bf182  lea     rcx, [rsi+0AC4h]
0x1400bf189  call    cs:__imp_IoTransferActivityId
0x1400bf190  nop     dword ptr [rax+rax+00h]
0x1400bf195  nop
0x1400bf196  mov     rdx, rsi
0x1400bf199  lea     rcx, [rsp+0F8h+var_A0]
0x1400bf19e  call    MsCreateTransactionContext
0x1400bf1a3  mov     r15d, eax
0x1400bf1a6  test    eax, eax
0x1400bf1a8  js      loc_1400BF23F
0x1400bf1ae  mov     rdi, [rsp+0F8h+var_A0]
0x1400bf1b3  or      qword ptr [rdi], 10000h
0x1400bf1ba  cmp     dword ptr [rsp+0F8h+Interval], 2
0x1400bf1c2  jnz     short loc_1400BF1D1
0x1400bf1c4  mov     rdx, rdi; struct CmsTransactionContext *
0x1400bf1c7  mov     rcx, rbx; this
0x1400bf1ca  call    ?DelayedReleaseCachedPinList@CmsBPlusTable@@QEAAXPEAVCmsTransactionContext@@@Z; CmsBPlusTable::DelayedReleaseCachedPinList(CmsTransactionContext *)
0x1400bf1cf  jmp     short loc_1400BF220
0x1400bf1d1  test    dword ptr [rsi+0D44h], 20000000h
0x1400bf1db  jnz     short loc_1400BF1EC
0x1400bf1dd  cmp     byte ptr [rsi+0D41h], 0
0x1400bf1e4  mov     r9d, 1
0x1400bf1ea  jnz     short loc_1400BF1F2
0x1400bf1ec  mov     r9d, 2
0x1400bf1f2  mov     rax, [rbx]
0x1400bf1f5  mov     rax, [rax+40h]
0x1400bf1f9  xor     ecx, ecx
0x1400bf1fb  mov     [rsp+0F8h+var_C0], rcx
0x1400bf200  mov     [rsp+0F8h+var_C8], rcx
0x1400bf205  mov     [rsp+0F8h+var_D0], rcx
0x1400bf20a  mov     [rsp+0F8h+var_D8], rcx
0x1400bf20f  xor     r8d, r8d
0x1400bf212  mov     rdx, rdi
0x1400bf215  mov     rcx, rbx
0x1400bf218  call    _guard_dispatch_icall
0x1400bf21d  mov     r15d, eax
0x1400bf220  mov     rcx, rdi
0x1400bf223  test    r15d, r15d
0x1400bf226  js      short loc_1400BF232
0x1400bf228  xor     r8d, r8d
0x1400bf22b  call    MsCommitTransaction
0x1400bf230  jmp     short loc_1400BF237
0x1400bf232  call    MsAbortTransaction
0x1400bf237  mov     rcx, rdi
0x1400bf23a  call    MsDeleteTransactionContext
0x1400bf23f  mov     edi, [rsp+0F8h+arg_10]
0x1400bf246  xor     r15d, r15d
0x1400bf249  jmp     short loc_1400BF271
0x1400bf24b  xor     r15d, r15d
0x1400bf24e  mov     rsi, [rsp+0F8h+var_98]
0x1400bf253  mov     r13, [rsp+0F8h+var_90]
0x1400bf258  mov     r14, [rsp+0F8h+var_88]
0x1400bf25d  mov     r12, [rsp+0F8h+var_80]
0x1400bf262  mov     rbx, [rsp+0F8h+var_78]
0x1400bf26a  mov     edi, [rsp+0F8h+arg_18]
0x1400bf271  mov     rcx, r13
0x1400bf274  call    cs:__imp_IoClearActivityIdThread
0x1400bf27b  nop     dword ptr [rax+rax+00h]
0x1400bf280  nop
0x1400bf281  lock dec dword ptr [r14]
0x1400bf285  nop
0x1400bf286  nop
0x1400bf287  lock and dword ptr [r12], 0FFFFFFEFh
0x1400bf28d  nop
0x1400bf28e  nop
0x1400bf28f  neg     edi
0x1400bf291  movsxd  rax, edi
0x1400bf294  lock add cs:?PagesQueuedForWriting@@3_JA, rax; __int64 PagesQueuedForWriting
0x1400bf29c  nop
0x1400bf29d  lea     rcx, [rsi+0B00h]; this
0x1400bf2a4  call    ?GetPercentageLogFreedIfAdvanced@CmsDurableLog@@QEAAKXZ; CmsDurableLog::GetPercentageLogFreedIfAdvanced(void)
0x1400bf2a9  movzx   edx, cs:byte_14026907C
0x1400bf2b0  cmp     eax, edx
0x1400bf2b2  jb      short loc_1400BF2E6
0x1400bf2b4  lea     rcx, [rsi+0B00h]; this
0x1400bf2bb  call    ?GetLogFullPercentage@CmsDurableLog@@QEAAEXZ; CmsDurableLog::GetLogFullPercentage(void)
0x1400bf2c0  movzx   ecx, al
0x1400bf2c3  movzx   eax, cs:byte_14026907A
0x1400bf2ca  cmp     ecx, eax
0x1400bf2cc  jb      short loc_1400BF2E6
0x1400bf2ce  xor     r8d, r8d; Wait
0x1400bf2d1  xor     edx, edx; Increment
0x1400bf2d3  lea     rcx, ?LazyWriterScanEvent@@3U_KEVENT@@A; Event
0x1400bf2da  call    cs:__imp_KeSetEvent
0x1400bf2e1  nop     dword ptr [rax+rax+00h]
0x1400bf2e6  mov     eax, 0FFFFFFFFh
0x1400bf2eb  lock xadd [rbx+8], eax
0x1400bf2f0  cmp     eax, 1
0x1400bf2f3  jnz     short loc_1400BF30D
0x1400bf2f5  test    rbx, rbx
  ... truncated ...
```
