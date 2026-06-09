# MspLazyWriterWorker(void *)

- ea: `0x1400531e0`
- end: `0x140053900`
- name: `?MspLazyWriterWorker@@YAXPEAX@Z`
- size: `1824`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x140012b18`
- `0x1400531a0`
- `0x1400531e0`
- `0x140054950`
- `0x140054b90`
- `0x140060a4c`
- `0x1400a1d00`
- `0x1400c6084`
- `0x1400c92a8`
- `0x140117d68`
- `0x1401e9dc0`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x140053798`
- `ntoskrnl!KeDelayExecutionThread` at `0x140053798`
- `ntoskrnl!IoClearActivityIdThread` at `0x1400534e1`
- `ntoskrnl!IoClearActivityIdThread` at `0x1400534e1`
- `ntoskrnl!KeSetEvent` at `0x140053847`
- `ntoskrnl!KeSetEvent` at `0x140053847`
- `ntoskrnl!IoSetActivityIdThread` at `0x1400533e6`
- `ntoskrnl!IoSetActivityIdThread` at `0x1400533e6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140053521`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005356b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140053638`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140053695`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400536e9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140053521`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005356b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140053638`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140053695`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400536e9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400535e7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140053621`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400536ab`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400536bf`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005372c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400535e7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140053621`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400536ab`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400536bf`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005372c`
- `ntoskrnl!IoTransferActivityId` at `0x140053406`
- `ntoskrnl!IoTransferActivityId` at `0x140053406`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140053246`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140053246`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140053347`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140053347`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400537cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400537cb`

## pseudocode

```c
void __fastcall MspLazyWriterWorker(void *a1)
{
  volatile signed __int32 *v1; // rdi
  unsigned int i; // ebx
  volatile signed __int32 *v3; // r8
  _QWORD **v4; // r9
  _QWORD *j; // rdx
  __int64 v6; // rax
  __int64 v7; // rax
  unsigned __int8 v8; // cl
  int v9; // eax
  _QWORD *v10; // rax
  _QWORD *v11; // rcx
  __int64 v12; // rsi
  volatile signed __int32 *v13; // r13
  volatile signed __int32 *v14; // r12
  __int64 v15; // rax
  int TransactionContext; // r15d
  struct CmsTransactionContext *v17; // rbx
  __int64 v18; // r9
  __int64 v19; // rdx
  int v20; // ebx
  __int64 v21; // rsi
  __int64 v22; // rbx
  KIRQL v23; // r11
  __int64 v24; // r9
  __int64 v25; // rdx
  __int64 v26; // r8
  unsigned int v27; // r10d
  unsigned __int64 v28; // r15
  unsigned __int64 v29; // rbx
  unsigned __int64 v30; // rbx
  unsigned __int64 v31; // r15
  __int64 v32; // rax
  __int64 v33; // r15
  __int64 v34; // r15
  KSPIN_LOCK *v35; // rbx
  KIRQL v36; // al
  unsigned __int64 v37; // rbx
  unsigned int v38; // ecx
  __int64 Length; // rax
  __int64 v40; // r9
  signed __int32 v41; // [rsp+40h] [rbp-98h]
  int v42; // [rsp+44h] [rbp-94h] BYREF
  struct CmsTransactionContext *v43; // [rsp+48h] [rbp-90h] BYREF
  volatile signed __int32 *v44; // [rsp+50h] [rbp-88h]
  __int64 v45; // [rsp+58h] [rbp-80h]
  __int64 v46; // [rsp+60h] [rbp-78h]
  volatile signed __int32 *v47; // [rsp+68h] [rbp-70h]
  __int64 v48; // [rsp+70h] [rbp-68h]
  volatile signed __int32 *v49; // [rsp+78h] [rbp-60h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+80h] [rbp-58h] BYREF
  PKSPIN_LOCK SpinLock; // [rsp+E8h] [rbp+10h] BYREF
  unsigned __int64 v53; // [rsp+F0h] [rbp+18h] BYREF
  int v54; // [rsp+F8h] [rbp+20h]

  v1 = 0;
  v44 = 0;
  v43 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  while ( 1 )
  {
    for ( i = 0; ; ++i )
    {
      LODWORD(SpinLock) = i;
      if ( i >= 3 )
        break;
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(0x140000000LL + 8LL * i + 2499168), &LockHandle);
      v3 = 0;
      v4 = (_QWORD **)(0x140000000LL + 16LL * i + 2499120);
      for ( j = *v4; j != v4; j = (_QWORD *)*j )
      {
        v3 = (volatile signed __int32 *)(j - 3);
        v6 = j[8];
        if ( (!v6
           || *(_DWORD *)(v6 + 2836) < LazyWriterMaxWorkersPerVolume
           || !i && *(_DWORD *)(*((_QWORD *)v3 + 11) + 2836LL) < LazyWriterMaxLogWorkersPerVolume)
          && (v3[4] & 0x10) == 0 )
        {
          _m_prefetchw((const void *)(v3 + 4));
          v41 = _InterlockedOr(v3 + 4, 0x10u) & 0x10;
          v42 = 0;
          v7 = 0;
          while ( 1 )
          {
            v8 = *((_BYTE *)&v41 + v7++);
            if ( v8 != *((_BYTE *)&v42 + v7 - 1) )
              break;
            if ( v7 == 4 )
            {
              v9 = 0;
              goto LABEL_13;
            }
          }
          v9 = v8 < *((_BYTE *)&v42 + v7 - 1) ? -1 : 1;
LABEL_13:
          if ( !v9 )
          {
            *((_DWORD *)v3 + 20) = 3;
            v10 = (_QWORD *)*j;
            if ( *(_QWORD **)(*j + 8LL) != j || (v11 = (_QWORD *)j[1], (_QWORD *)*v11 != j) )
              __fastfail(3u);
            *v11 = v10;
            v10[1] = v11;
            j[1] = j;
            *j = j;
            --*((_DWORD *)&WorkerEntriesQueueCount + i);
            break;
          }
        }
      }
      v1 = 0;
      if ( j != v4 )
        v1 = v3;
      v44 = v1;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      if ( v1 )
        break;
      if ( LazyWriterWorkersActive >= LazyWriterMaxWorkers )
      {
        LODWORD(SpinLock) = 3;
        break;
      }
    }
    if ( !v1 )
      break;
    _InterlockedDecrement(&LazyWriterEntries);
    v12 = *((_QWORD *)v1 + 11);
    v45 = v12;
    v13 = (volatile signed __int32 *)(v12 + 2836);
    v46 = v12 + 2836;
    _InterlockedIncrement((volatile signed __int32 *)(v12 + 2836));
    _InterlockedDecrement((volatile signed __int32 *)(v12 + 2840));
    v49 = v1 + 4;
    if ( (v1[4] & 8) != 0 )
    {
      MspLazyWriterDeliverSpaceNotification((struct _SmsLazyWriterEntry *)v1);
      _InterlockedDecrement(v13);
    }
    else
    {
      v14 = (volatile signed __int32 *)*((_QWORD *)v1 - 74);
      v47 = v14;
      LODWORD(v53) = *((_DWORD *)v1 + 14);
      v54 = v53;
      v15 = IoSetActivityIdThread(v12 + 2820);
      v48 = v15;
      if ( v15 )
        IoTransferActivityId(v12 + 2820, v15);
      TransactionContext = MsCreateTransactionContext((PSLIST_ENTRY *)&v43, v12);
      if ( TransactionContext >= 0 )
      {
        v17 = v43;
        *(_QWORD *)v43 |= 0x10000uLL;
        if ( (_DWORD)SpinLock == 2 )
        {
          CmsBPlusTable::DelayedReleaseCachedPinList((CmsBPlusTable *)v14, v17);
        }
        else
        {
          if ( (*(_DWORD *)(v12 + 3460) & 0x20000000) != 0 || !*(_BYTE *)(v12 + 3457) )
            v18 = 2;
          else
            v18 = 1;
          TransactionContext = (*(__int64 (__fastcall **)(volatile signed __int32 *, struct CmsTransactionContext *, _QWORD, __int64, _QWORD, _QWORD))(*(_QWORD *)v14 + 64LL))(
                                 v14,
                                 v17,
                                 0,
                                 v18,
                                 0,
                                 0);
        }
        if ( TransactionContext < 0 )
          MsAbortTransaction(v17);
        else
          MsCommitTransaction(v17, v19, 0);
        MsDeleteTransactionContext(v17);
      }
      v20 = v53;
      IoClearActivityIdThread(v48);
      _InterlockedDecrement(v13);
      _InterlockedAnd(v49, 0xFFFFFFEF);
      _InterlockedAdd64(&PagesQueuedForWriting, -v20);
      v21 = v12 + 2880;
      SpinLock = 0;
      *(_BYTE *)(v21 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v21 + 56));
      v22 = *(_QWORD *)(v21 + 72);
      if ( v22 && (*(_DWORD *)(v21 + 296) & 4) != 0 && !*(_QWORD *)(v21 + 280) )
      {
        SpinLock = (PKSPIN_LOCK)(v22 + 3776);
        v23 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v22 + 3776));
        v24 = *(_QWORD *)(v22 + 3704);
        v25 = *(unsigned int *)(v22 + 32);
        if ( ML_LSN_INVALID == v24 )
        {
          v26 = *(unsigned int *)(v22 + 24);
          v27 = *(_DWORD *)(v22 + 3664);
          v28 = v27 * ((unsigned int)v25 - v26);
        }
        else
        {
          v28 = *(unsigned int *)(v22 + 3664)
              * (v25 + (unsigned int)v24 - (unsigned __int64)*(unsigned int *)(v22 + 24));
          v27 = *(_DWORD *)(v22 + 3664);
          LODWORD(v26) = *(_DWORD *)(v22 + 24);
        }
        if ( ML_LSN_INVALID == v24 )
          v29 = (unsigned int)v26 + *(unsigned int *)(v22 + 3696) - (unsigned __int64)(unsigned int)v25;
        else
          v29 = (unsigned int)v26 - (unsigned __int64)(unsigned int)v25;
        v30 = v27 * v29;
        KeReleaseSpinLock(SpinLock, v23);
        SpinLock = (PKSPIN_LOCK)(100 * (v28 + *(unsigned int *)(v21 + 288)) / (v30 + v28));
        *(_QWORD *)(v21 + 8) = v28;
        *(_QWORD *)(v21 + 16) = v30;
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(v21 + 56), *(_BYTE *)(v21 + 64));
      v31 = ML_LSN_INVALID;
      *(_BYTE *)(v21 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v21 + 56));
      v32 = *(_QWORD *)(v21 + 24);
      if ( v32 != v21 + 24 )
        v31 = *(_QWORD *)(v32 + 16);
      if ( ML_LSN_INVALID == v31 )
      {
        v33 = *(_QWORD *)(v21 + 280);
        if ( v33 )
        {
          v31 = *(_QWORD *)(v33 + 104);
        }
        else
        {
          v34 = *(_QWORD *)(v21 + 72);
          if ( v34 && (*(_DWORD *)(v21 + 296) & 4) != 0 )
          {
            v35 = (KSPIN_LOCK *)(v34 + 3776);
            v36 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v34 + 3776));
            v31 = *(_QWORD *)(v34 + 32);
            KeReleaseSpinLock(v35, v36);
          }
          else
          {
            v31 = ML_LSN_NULL;
          }
        }
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(v21 + 56), *(_BYTE *)(v21 + 64));
      if ( ML_LSN_NULL == v31 || ML_LSN_INVALID == v31 )
      {
        LODWORD(v37) = 0;
      }
      else
      {
        *(_BYTE *)(v21 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v21 + 56));
        v53 = v31;
        if ( (*(_DWORD *)(v21 + 296) & 4) != 0 )
        {
          if ( v31 < *(_QWORD *)(v21 + 128) )
          {
            Length = MlLogGetLength(*(_QWORD *)(v21 + 72), &v53, v21 + 128, *(_QWORD *)(v21 + 80));
            v37 = 100
                * ((unsigned __int64)*(unsigned int *)(v21 + 288) + Length)
                / (*(_QWORD *)(v40 + 3216) << *(_DWORD *)(v40 + 64));
          }
          else
          {
            LODWORD(v37) = 0;
          }
        }
        else
        {
          LODWORD(v37) = 0;
        }
        KeReleaseSpinLock((PKSPIN_LOCK)(v21 + 56), *(_BYTE *)(v21 + 64));
      }
      if ( (unsigned int)v37 <= (unsigned __int8)SpinLock )
        v38 = (unsigned __int8)SpinLock - (_DWORD)v37;
      else
        v38 = 0;
      if ( v38 >= (unsigned __int8)byte_14026207C
        && CmsDurableLog::GetLogFullPercentage((CmsDurableLog *)v21) >= (unsigned int)(unsigned __int8)byte_14026207A )
      {
        KeSetEvent(&LazyWriterScanEvent, 0, 0);
      }
      if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
      {
        if ( v14 )
          (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v14)(v14, 1);
      }
      SpinLock = 0;
      KeDelayExecutionThread(0, 0, (PLARGE_INTEGER)&SpinLock);
    }
  }
  _InterlockedDecrement(&LazyWriterWorkersActive);
  if ( a1 )
    ExFreePoolWithTag(a1, 0);
}

```

## disassembly

```asm
0x1400531e0  mov     r11, rsp
0x1400531e3  mov     [r11+8], rcx
0x1400531e7  push    rbx
0x1400531e8  push    rsi
0x1400531e9  push    rdi
0x1400531ea  push    r12
0x1400531ec  push    r13
0x1400531ee  push    r14
0x1400531f0  push    r15
0x1400531f2  sub     rsp, 0A0h
0x1400531f9  xor     r14d, r14d
0x1400531fc  mov     edi, r14d
0x1400531ff  mov     [rsp+0D8h+var_88], r14
0x140053204  mov     [rsp+0D8h+var_90], r14
0x140053209  xorps   xmm0, xmm0
0x14005320c  xor     eax, eax
0x14005320e  movups  xmmword ptr [r11-58h], xmm0
0x140053213  mov     [r11-48h], rax
0x140053217  lea     rsi, cs:140000000h
0x14005321e  mov     ebx, r14d
0x140053221  mov     dword ptr [rsp+0D8h+SpinLock], ebx
0x140053228  cmp     ebx, 3
0x14005322b  jnb     loc_140053378
0x140053231  mov     edi, ebx
0x140053233  lea     rcx, ds:262260h[rdi*8]
0x14005323b  add     rcx, rsi; SpinLock
0x14005323e  lea     rdx, [rsp+0D8h+LockHandle]; LockHandle
0x140053246  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14005324d  nop     dword ptr [rax+rax+00h]
0x140053252  mov     r8, r14
0x140053255  mov     eax, ebx
0x140053257  shl     rax, 4
0x14005325b  lea     r9, [rax+262230h]
0x140053262  add     r9, rsi
0x140053265  mov     rdx, [r9]
0x140053268  cmp     rdx, r9
0x14005326b  jz      loc_140053330
0x140053271  lea     r8, [rdx-18h]
0x140053275  mov     rax, [r8+58h]
0x140053279  test    rax, rax
0x14005327c  jz      short loc_140053290
0x14005327e  mov     eax, [rax+0B14h]
0x140053284  cmp     eax, cs:?LazyWriterMaxWorkersPerVolume@@3JA; long LazyWriterMaxWorkersPerVolume
0x14005328a  jge     loc_14005387A
0x140053290  mov     eax, [r8+10h]
0x140053294  test    al, 10h
0x140053296  jnz     loc_1400537A9
0x14005329c  nop
0x14005329d  prefetchw byte ptr [r8+10h]
0x1400532a2  mov     eax, [r8+10h]
0x1400532a6  mov     ecx, eax
0x1400532a8  or      ecx, 10h
0x1400532ab  lock cmpxchg [r8+10h], ecx
0x1400532b1  jnz     short loc_1400532A6
0x1400532b3  nop
0x1400532b4  and     eax, 10h
0x1400532b7  mov     [rsp+0D8h+var_98], eax
0x1400532bb  mov     [rsp+0D8h+var_94], r14d
0x1400532c0  mov     rax, r14
0x1400532c3  lea     r10, [rsp+0D8h+var_98]
0x1400532c8  lea     r11, [rsp+0D8h+var_94]
0x1400532cd  nop     dword ptr [rax]
0x1400532d0  movzx   ecx, byte ptr [r10+rax]
0x1400532d5  inc     rax
0x1400532d8  cmp     cl, [r11+rax-1]
0x1400532dd  jnz     loc_1400537F3
0x1400532e3  cmp     rax, 4
0x1400532e7  jnz     short loc_1400532D0
0x1400532e9  mov     eax, r14d
0x1400532ec  test    eax, eax
0x1400532ee  setz    al
0x1400532f1  test    al, al
0x1400532f3  jz      loc_1400537A9
0x1400532f9  mov     dword ptr [r8+50h], 3
0x140053301  mov     rax, [rdx]
0x140053304  cmp     [rax+8], rdx
0x140053308  jnz     loc_1400537FD
0x14005330e  mov     rcx, [rdx+8]
0x140053312  cmp     [rcx], rdx
0x140053315  jnz     loc_1400537FD
0x14005331b  mov     [rcx], rax
0x14005331e  mov     [rax+8], rcx
0x140053322  mov     [rdx+8], rdx
0x140053326  mov     [rdx], rdx
0x140053329  dec     rva ?WorkerEntriesQueueCount@@3PAJA[rsi+rdi*4]; long near * WorkerEntriesQueueCount ...
0x140053330  mov     rdi, r14
0x140053333  cmp     rdx, r9
0x140053336  cmovnz  rdi, r8
0x14005333a  mov     [rsp+0D8h+var_88], rdi
0x14005333f  lea     rcx, [rsp+0D8h+LockHandle]; LockHandle
0x140053347  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005334e  nop     dword ptr [rax+rax+00h]
0x140053353  test    rdi, rdi
0x140053356  jnz     short loc_140053378
0x140053358  mov     eax, cs:?LazyWriterMaxWorkers@@3JA; long LazyWriterMaxWorkers
0x14005335e  cmp     cs:?LazyWriterWorkersActive@@3JA, eax; long LazyWriterWorkersActive
0x140053364  jge     short loc_14005336D
0x140053366  inc     ebx
0x140053368  jmp     loc_140053221
0x14005336d  mov     dword ptr [rsp+0D8h+SpinLock], 3
0x140053378  nop
0x140053379  test    rdi, rdi
0x14005337c  jz      loc_1400537B1
0x140053382  lock dec cs:?LazyWriterEntries@@3JA; long LazyWriterEntries
0x140053389  nop
0x14005338a  mov     rsi, [rdi+58h]
0x14005338e  mov     [rsp+0D8h+var_80], rsi
0x140053393  nop
0x140053394  lea     r13, [rsi+0B14h]
0x14005339b  mov     [rsp+0D8h+var_78], r13
0x1400533a0  lock inc dword ptr [r13+0]
0x1400533a5  nop
0x1400533a6  nop
0x1400533a7  lock dec dword ptr [rsi+0B18h]
0x1400533ae  nop
0x1400533af  lea     rax, [rdi+10h]
0x1400533b3  mov     [rsp+0D8h+var_60], rax
0x1400533b8  mov     eax, [rax]
0x1400533ba  test    al, 8
0x1400533bc  jnz     loc_140053804
0x1400533c2  mov     r12, [rdi-250h]
0x1400533c9  mov     [rsp+0D8h+var_70], r12
0x1400533ce  mov     eax, [rdi+38h]
0x1400533d1  mov     dword ptr [rsp+0D8h+arg_10], eax
0x1400533d8  mov     [rsp+0D8h+arg_18], eax
0x1400533df  lea     rcx, [rsi+0B04h]
0x1400533e6  call    cs:__imp_IoSetActivityIdThread
0x1400533ed  nop     dword ptr [rax+rax+00h]
0x1400533f2  mov     [rsp+0D8h+var_68], rax
0x1400533f7  test    rax, rax
0x1400533fa  jz      short loc_140053413
0x1400533fc  mov     rdx, rax
0x1400533ff  lea     rcx, [rsi+0B04h]
0x140053406  call    cs:__imp_IoTransferActivityId
0x14005340d  nop     dword ptr [rax+rax+00h]
0x140053412  nop
0x140053413  mov     rdx, rsi
0x140053416  lea     rcx, [rsp+0D8h+var_90]
0x14005341b  call    MsCreateTransactionContext
0x140053420  mov     r15d, eax
0x140053423  test    eax, eax
0x140053425  js      loc_1400534B5
0x14005342b  mov     rbx, [rsp+0D8h+var_90]
0x140053430  or      qword ptr [rbx], 10000h
0x140053437  cmp     dword ptr [rsp+0D8h+SpinLock], 2
0x14005343f  jz      short loc_1400534A1
0x140053441  test    dword ptr [rsi+0D84h], 20000000h
0x14005344b  jnz     short loc_140053499
0x14005344d  cmp     byte ptr [rsi+0D81h], 0
0x140053454  jz      short loc_140053499
0x140053456  mov     r9d, 1
0x14005345c  mov     rax, [r12]
0x140053460  mov     rax, [rax+40h]
0x140053464  mov     [rsp+0D8h+var_B0], r14
0x140053469  mov     [rsp+0D8h+var_B8], r14
0x14005346e  xor     r8d, r8d
0x140053471  mov     rdx, rbx
0x140053474  mov     rcx, r12
0x140053477  call    _guard_dispatch_icall
0x14005347c  mov     r15d, eax
0x14005347f  mov     rcx, rbx
0x140053482  test    r15d, r15d
0x140053485  js      short loc_1400534AE
0x140053487  xor     r8d, r8d
0x14005348a  call    MsCommitTransaction
0x14005348f  mov     rcx, rbx
0x140053492  call    MsDeleteTransactionContext
0x140053497  jmp     short loc_1400534B5
0x140053499  mov     r9d, 2
0x14005349f  jmp     short loc_14005345C
0x1400534a1  mov     rdx, rbx; struct CmsTransactionContext *
0x1400534a4  mov     rcx, r12; this
0x1400534a7  call    ?DelayedReleaseCachedPinList@CmsBPlusTable@@QEAAXPEAVCmsTransactionContext@@@Z; CmsBPlusTable::DelayedReleaseCachedPinList(CmsTransactionContext *)
0x1400534ac  jmp     short loc_14005347F
0x1400534ae  call    MsAbortTransaction
0x1400534b3  jmp     short loc_14005348F
0x1400534b5  mov     ebx, dword ptr [rsp+0D8h+arg_10]
0x1400534bc  jmp     short loc_1400534DC
0x1400534be  xor     r14d, r14d
0x1400534c1  mov     rdi, [rsp+0D8h+var_88]
0x1400534c6  mov     rsi, [rsp+0D8h+var_80]
0x1400534cb  mov     r13, [rsp+0D8h+var_78]
0x1400534d0  mov     r12, [rsp+0D8h+var_70]
0x1400534d5  mov     ebx, [rsp+0D8h+arg_18]
0x1400534dc  mov     rcx, [rsp+0D8h+var_68]
0x1400534e1  call    cs:__imp_IoClearActivityIdThread
0x1400534e8  nop     dword ptr [rax+rax+00h]
0x1400534ed  nop
0x1400534ee  lock dec dword ptr [r13+0]
0x1400534f3  nop
0x1400534f4  nop
0x1400534f5  mov     rax, [rsp+0D8h+var_60]
0x1400534fa  lock and dword ptr [rax], 0FFFFFFEFh
0x1400534fe  nop
0x1400534ff  neg     ebx
0x140053501  movsxd  rax, ebx
0x140053504  nop
0x140053505  lock add cs:?PagesQueuedForWriting@@3_JA, rax; __int64 PagesQueuedForWriting
0x14005350d  nop
0x14005350e  add     rsi, 0B40h
0x140053515  mov     [rsp+0D8h+SpinLock], r14
0x14005351d  lea     rcx, [rsi+38h]; SpinLock
0x140053521  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140053528  nop     dword ptr [rax+rax+00h]
0x14005352d  mov     [rsi+40h], al
0x140053530  mov     eax, [rsi+128h]
0x140053536  mov     rbx, [rsi+48h]
0x14005353a  test    rbx, rbx
0x14005353d  jz      loc_140053619
0x140053543  test    al, 4
0x140053545  jz      loc_140053619
0x14005354b  cmp     qword ptr [rsi+118h], 0
0x140053553  jnz     loc_140053619
0x140053559  lea     rax, [rbx+0EC0h]
0x140053560  mov     [rsp+0D8h+SpinLock], rax
0x140053568  mov     rcx, rax; SpinLock
0x14005356b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140053572  nop     dword ptr [rax+rax+00h]
0x140053577  movzx   r11d, al
0x14005357b  mov     r9, [rbx+0E78h]
0x140053582  mov     edx, r14d
0x140053585  mov     rcx, cs:ML_LSN_INVALID
0x14005358c  cmp     rcx, r9
0x14005358f  setz    dl
0x140053592  test    edx, edx
0x140053594  mov     edx, [rbx+20h]
0x140053597  jz      loc_140053858
0x14005359d  mov     r8d, [rbx+18h]
0x1400535a1  mov     r10d, [rbx+0E50h]
0x1400535a8  mov     r15d, edx
0x1400535ab  sub     r15, r8
0x1400535ae  imul    r15, r10
0x1400535b2  mov     eax, r14d
0x1400535b5  cmp     rcx, r9
0x1400535b8  setz    al
0x1400535bb  test    eax, eax
0x1400535bd  mov     eax, edx
0x1400535bf  jz      loc_14005389D
0x1400535c5  mov     ebx, [rbx+0E70h]
0x1400535cb  sub     rbx, rax
0x1400535ce  mov     eax, r8d
0x1400535d1  add     rbx, rax
0x1400535d4  mov     eax, r10d
0x1400535d7  imul    rbx, rax
0x1400535db  movzx   edx, r11b; NewIrql
0x1400535df  mov     rcx, [rsp+0D8h+SpinLock]; SpinLock
0x1400535e7  call    cs:__imp_KeReleaseSpinLock
0x1400535ee  nop     dword ptr [rax+rax+00h]
0x1400535f3  mov     ecx, [rsi+120h]
0x1400535f9  add     rcx, r15
0x1400535fc  imul    rax, rcx, 64h ; 'd'
0x140053600  lea     rcx, [rbx+r15]
0x140053604  xor     edx, edx
0x140053606  div     rcx
0x140053609  mov     [rsp+0D8h+SpinLock], rax
0x140053611  mov     [rsi+8], r15
0x140053615  mov     [rsi+10h], rbx
0x140053619  movzx   edx, byte ptr [rsi+40h]; NewIrql
0x14005361d  lea     rcx, [rsi+38h]; SpinLock
0x140053621  call    cs:__imp_KeReleaseSpinLock
0x140053628  nop     dword ptr [rax+rax+00h]
0x14005362d  mov     r15, cs:ML_LSN_INVALID
0x140053634  lea     rcx, [rsi+38h]; SpinLock
0x140053638  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14005363f  nop     dword ptr [rax+rax+00h]
0x140053644  mov     [rsi+40h], al
0x140053647  lea     rcx, [rsi+18h]
0x14005364b  mov     rax, [rcx]
0x14005364e  cmp     rax, rcx
0x140053651  jz      short loc_140053657
0x140053653  mov     r15, [rax+10h]
0x140053657  cmp     cs:ML_LSN_INVALID, r15
0x14005365e  jnz     short loc_1400536B7
0x140053660  mov     r15, [rsi+118h]
0x140053667  test    r15, r15
0x14005366a  jnz     loc_140053818
0x140053670  mov     r15, [rsi+48h]
0x140053674  test    r15, r15
0x140053677  jz      loc_1400538A8
0x14005367d  mov     eax, [rsi+128h]
0x140053683  test    al, 4
0x140053685  jz      loc_1400538A8
0x14005368b  lea     rbx, [r15+0EC0h]
0x140053692  mov     rcx, rbx; SpinLock
0x140053695  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14005369c  nop     dword ptr [rax+rax+00h]
0x1400536a1  mov     r15, [r15+20h]
0x1400536a5  movzx   edx, al; NewIrql
0x1400536a8  mov     rcx, rbx; SpinLock
0x1400536ab  call    cs:__imp_KeReleaseSpinLock
0x1400536b2  nop     dword ptr [rax+rax+00h]
0x1400536b7  movzx   edx, byte ptr [rsi+40h]; NewIrql
0x1400536bb  lea     rcx, [rsi+38h]; SpinLock
0x1400536bf  call    cs:__imp_KeReleaseSpinLock
0x1400536c6  nop     dword ptr [rax+rax+00h]
0x1400536cb  cmp     cs:ML_LSN_NULL, r15
0x1400536d2  jz      loc_1400537EB
0x1400536d8  cmp     cs:ML_LSN_INVALID, r15
0x1400536df  jz      loc_1400537EB
0x1400536e5  lea     rcx, [rsi+38h]; SpinLock
  ... truncated ...
```
