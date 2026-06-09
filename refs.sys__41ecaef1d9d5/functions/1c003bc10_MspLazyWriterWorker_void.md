# MspLazyWriterWorker(void *)

- ea: `0x1c003bc10`
- end: `0x1c003c2af`
- name: `?MspLazyWriterWorker@@YAXPEAX@Z`
- size: `1695`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1c0011660`
- `0x1c00133f0`
- `0x1c0014410`
- `0x1c0037038`
- `0x1c003bc10`
- `0x1c003c2b8`
- `0x1c006ac80`
- `0x1c00b1324`
- `0x1c00b4598`
- `0x1c00b46e8`
- `0x1c00caea4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1c003bd68`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c003bd68`
- `ntoskrnl!KeDelayExecutionThread` at `0x1c003c209`
- `ntoskrnl!KeDelayExecutionThread` at `0x1c003c209`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c003bef9`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c003bef9`
- `ntoskrnl!KeSetEvent` at `0x1c00811c6`
- `ntoskrnl!KeSetEvent` at `0x1c00811c6`
- `ntoskrnl!IoSetActivityIdThread` at `0x1c003bdf2`
- `ntoskrnl!IoSetActivityIdThread` at `0x1c003bdf2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c003bf40`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c003bf92`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c003c094`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c003c0fc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c003c15e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c003bf40`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c003bf92`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c003c094`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c003c0fc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c003c15e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c003c022`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c003c06e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c003c117`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c003c135`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c003c1b9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c003c022`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c003c06e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c003c117`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c003c135`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c003c1b9`
- `ntoskrnl!IoTransferActivityId` at `0x1c003be12`
- `ntoskrnl!IoTransferActivityId` at `0x1c003be12`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1c003bc64`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1c003bc64`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1c003bca2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1c003bca2`

## pseudocode

```c
void __fastcall MspLazyWriterWorker(void *a1)
{
  volatile signed __int32 *v1; // rdi
  unsigned int i; // ebx
  volatile signed __int32 *p_Blink; // r9
  struct _LIST_ENTRY near **v4; // rdx
  struct _LIST_ENTRY near *v5; // r8
  struct _LIST_ENTRY *Flink; // rax
  int Flink_high; // ecx
  struct _LIST_ENTRY near *v8; // rcx
  struct _LIST_ENTRY *Blink; // rax
  unsigned __int64 v10; // rsi
  unsigned __int64 v11; // r13
  __int64 v12; // rax
  struct CmsTransactionContext *v13; // r12
  int v14; // r8d
  int updated; // eax
  __int64 v16; // rbx
  KSPIN_LOCK *v17; // rsi
  KIRQL v18; // r10
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // r12
  __int64 v22; // rdx
  __int64 v23; // rbx
  __int64 v24; // rbx
  __int64 v25; // rax
  __int64 v26; // r12
  unsigned __int64 v27; // rsi
  unsigned int v28; // r12d
  unsigned __int64 v29; // rbx
  KSPIN_LOCK *v30; // rsi
  __int64 v31; // rcx
  __int64 v32; // rbx
  __int64 v33; // rbx
  KSPIN_LOCK *v34; // rsi
  KIRQL v35; // al
  KIRQL v36; // r9
  unsigned __int64 v37; // rdx
  unsigned __int64 v38; // rbx
  unsigned int v39; // r12d
  __int64 v40; // r11
  unsigned int v41; // ecx
  unsigned __int64 v42; // r10
  __int64 v43; // rdx
  volatile signed __int32 *v44; // [rsp+30h] [rbp-C8h]
  struct CmsTransactionContext *v45; // [rsp+40h] [rbp-B8h] BYREF
  volatile signed __int32 *v46; // [rsp+48h] [rbp-B0h]
  void *v47; // [rsp+50h] [rbp-A8h]
  volatile signed __int32 *v48; // [rsp+58h] [rbp-A0h]
  unsigned __int64 v49; // [rsp+60h] [rbp-98h]
  __int64 v50; // [rsp+70h] [rbp-88h]
  volatile signed __int32 *v51; // [rsp+78h] [rbp-80h]
  volatile signed __int32 *v52; // [rsp+80h] [rbp-78h]
  union _LARGE_INTEGER Interval; // [rsp+88h] [rbp-70h] BYREF
  __int64 v54; // [rsp+98h] [rbp-60h]
  __int64 v55; // [rsp+A0h] [rbp-58h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+A8h] [rbp-50h] BYREF
  int v58; // [rsp+108h] [rbp+10h]
  int v59; // [rsp+110h] [rbp+18h]
  __int64 v60; // [rsp+110h] [rbp+18h]
  CmsDurableLog *v61; // [rsp+118h] [rbp+20h]

  v47 = a1;
  v1 = 0;
  v46 = 0;
  v45 = 0;
LABEL_2:
  for ( i = 0; i < 3; ++i )
  {
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(0x1C0000000LL + 8LL * i + 1275856), &LockHandle);
    p_Blink = 0;
    v4 = &(&WorkerEntriesQueue)[2 * i];
    v5 = *v4;
    if ( *v4 != (struct _LIST_ENTRY near *)v4 )
    {
      while ( 1 )
      {
        p_Blink = (volatile signed __int32 *)&v5[-2].Blink;
        Flink = v5[3].Flink;
        if ( !Flink
          || (Flink_high = HIDWORD(Flink[160].Flink), Flink_high < LazyWriterMaxWorkersPerVolume)
          || !i && Flink_high < LazyWriterMaxLogWorkersPerVolume )
        {
          _m_prefetchw((const void *)(p_Blink + 4));
          if ( (_InterlockedOr(p_Blink + 4, 0x10u) & 0x10) == 0 )
            break;
        }
        v5 = v5->Flink;
        if ( v5 == (struct _LIST_ENTRY near *)v4 )
          goto LABEL_5;
      }
      v8 = v5->Flink;
      Blink = v5->Blink;
      if ( v5->Flink->Blink != v5 || Blink->Flink != v5 )
        __fastfail(3u);
      Blink->Flink = v8;
      v8->Blink = Blink;
      v5->Blink = v5;
      v5->Flink = v5;
      *((_DWORD *)p_Blink + 16) = 3;
      --*((_DWORD *)&WorkerEntriesQueueCount + i);
    }
LABEL_5:
    v1 = 0;
    if ( v5 != (struct _LIST_ENTRY near *)v4 )
      v1 = p_Blink;
    v46 = v1;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( v1 )
    {
LABEL_20:
      _InterlockedDecrement(&LazyWriterEntries);
      v10 = *((_QWORD *)v1 + 9);
      v49 = v10;
      v11 = v10;
      v51 = (volatile signed __int32 *)(v10 + 2564);
      _InterlockedIncrement((volatile signed __int32 *)(v10 + 2564));
      _InterlockedDecrement((volatile signed __int32 *)(v10 + 2568));
      v52 = v1 + 4;
      if ( (v1[4] & 8) != 0 )
      {
        MspLazyWriterDeliverSpaceNotification((PVOID)v1);
        _InterlockedDecrement((volatile signed __int32 *)(v10 + 2564));
      }
      else
      {
        v44 = (volatile signed __int32 *)*((_QWORD *)v1 - 73);
        v48 = v44;
        v59 = *((_DWORD *)v1 + 14);
        v12 = IoSetActivityIdThread(v10 + 2548);
        v50 = v12;
        if ( v12 )
          IoTransferActivityId(v10 + 2548, v12);
        v58 = MsCreateTransactionContext(&v45, v10);
        if ( v58 >= 0 )
        {
          v13 = v45;
          *((_QWORD *)v45 + 2) |= 0x10000uLL;
          if ( i == 2 )
          {
            CmsBPlusTable::DelayedReleaseCachedPinList((CmsBPlusTable *)v44, v13);
            updated = v58;
          }
          else
          {
            if ( (*(_DWORD *)(v10 + 3116) & 0x20000000) != 0 )
              v14 = 6;
            else
              v14 = 1;
            updated = MsUpdateTree((_DWORD)v13, (_DWORD)v44, v14, 0, 0);
          }
          if ( updated < 0 )
            MsAbortTransaction(v13);
          else
            MsCommitTransaction(v13);
          MsDeleteTransactionContext(v13);
        }
        IoClearActivityIdThread(v50);
        _InterlockedDecrement(v51);
        _InterlockedAnd(v52, 0xFFFFFFEF);
        _InterlockedExchangeAdd64(&PagesQueuedForWriting, -v59);
        v61 = (CmsDurableLog *)(v10 + 2608);
        LOBYTE(v10) = 0;
        *(_BYTE *)(v11 + 2672) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v11 + 2664));
        v16 = *(_QWORD *)(v11 + 2680);
        v60 = v16;
        if ( v16 && (*(_DWORD *)(v11 + 2904) & 4) != 0 && !*(_QWORD *)(v11 + 2888) )
        {
          v17 = (KSPIN_LOCK *)(v16 + 3776);
          v18 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v16 + 3776));
          v19 = *(_QWORD *)(v16 + 3704);
          v20 = *(unsigned int *)(v16 + 24);
          v21 = *(unsigned int *)(v16 + 3664);
          v22 = *(unsigned int *)(v16 + 32);
          if ( RefsLargeEof == v19 )
            v23 = (unsigned int)v22 - v20;
          else
            v23 = v22 + (unsigned int)v19 - v20;
          v24 = v21 * v23;
          v54 = v24;
          if ( RefsLargeEof == v19 )
            v25 = v20 + *(unsigned int *)(v60 + 3696) - v22;
          else
            v25 = v20 - v22;
          v26 = v25 * v21;
          v55 = v26;
          KeReleaseSpinLock(v17, v18);
          v27 = 100 * (v24 + *(unsigned int *)(v11 + 2896));
          if ( v26 + v24 == 0x20000000 )
            v10 = v27 >> 29;
          else
            v10 = v27 / (v26 + v24);
          *(_QWORD *)(v11 + 2616) = v24;
          *(_QWORD *)(v11 + 2624) = v26;
        }
        KeReleaseSpinLock((PKSPIN_LOCK)(v11 + 2664), *(_BYTE *)(v11 + 2672));
        v28 = (unsigned __int8)v10;
        v29 = RefsLargeEof;
        v30 = (KSPIN_LOCK *)(v11 + 2664);
        *(_BYTE *)(v11 + 2672) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v11 + 2664));
        v31 = *(_QWORD *)(v11 + 2632);
        if ( v31 != v11 + 2632 )
          v29 = *(_QWORD *)(v31 + 16);
        if ( RefsLargeEof == v29 )
        {
          v32 = *(_QWORD *)(v11 + 2888);
          if ( v32 )
          {
            v29 = *(_QWORD *)(v32 + 104);
          }
          else
          {
            v33 = *(_QWORD *)(v11 + 2680);
            if ( v33 && (*(_DWORD *)(v11 + 2904) & 4) != 0 )
            {
              v34 = (KSPIN_LOCK *)(v33 + 3776);
              v35 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v33 + 3776));
              v29 = *(_QWORD *)(v33 + 32);
              KeReleaseSpinLock(v34, v35);
              v30 = (KSPIN_LOCK *)(v11 + 2664);
            }
            else
            {
              v29 = ML_LSN_NULL;
            }
          }
        }
        KeReleaseSpinLock(v30, *(_BYTE *)(v11 + 2672));
        if ( RefsLargeEof == v29 || ML_LSN_NULL == v29 )
        {
          LODWORD(v38) = 0;
        }
        else
        {
          v36 = KeAcquireSpinLockRaiseToDpc(v30);
          *(_BYTE *)(v11 + 2672) = v36;
          if ( (*(_DWORD *)(v11 + 2904) & 4) != 0 )
          {
            v37 = *(_QWORD *)(v11 + 2736);
            if ( v29 < v37 )
            {
              v40 = *(_QWORD *)(v11 + 2680);
              v41 = HIDWORD(v37) - HIDWORD(v29);
              v42 = (unsigned int)v37 - (unsigned __int64)(unsigned int)v29;
              if ( HIDWORD(v37) != HIDWORD(v29) )
              {
                v43 = *(unsigned int *)(v40 + 3696);
                v42 += v43;
                if ( v41 > 1 )
                  v42 += (unsigned int)v43 * (v41 - 1);
              }
              v38 = 100
                  * (*(unsigned int *)(v11 + 2896) + v42 * *(unsigned int *)(v40 + 3664))
                  / (*(_QWORD *)(*(_QWORD *)(v11 + 2688) + 2952LL) << *(_DWORD *)(*(_QWORD *)(v11 + 2688) + 64LL));
            }
            else
            {
              LODWORD(v38) = 0;
            }
          }
          else
          {
            LODWORD(v38) = 0;
          }
          KeReleaseSpinLock(v30, v36);
        }
        if ( (unsigned int)v38 > v28 )
          v39 = 0;
        else
          v39 = v28 - v38;
        if ( v39 >= BYTE2(dword_1C0136C58)
          && CmsDurableLog::GetLogFullPercentage(v61) >= (unsigned int)(unsigned __int8)dword_1C0136C58 )
        {
          KeSetEvent(&LazyWriterScanEvent, 0, 0);
        }
        if ( _InterlockedExchangeAdd(v44 + 2, 0xFFFFFFFF) == 1 && v44 )
          (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v44)(v44, 1);
        Interval.QuadPart = 0;
        KeDelayExecutionThread(0, 0, &Interval);
      }
      goto LABEL_2;
    }
    if ( LazyWriterWorkersActive >= LazyWriterMaxWorkers )
    {
      i = 3;
      break;
    }
  }
  if ( v1 )
    goto LABEL_20;
  _InterlockedDecrement(&LazyWriterWorkersActive);
  if ( a1 )
    ExFreePoolWithTag(a1, 0);
}

```

## disassembly

```asm
0x1c003bc10  mov     [rsp+P], rcx
0x1c003bc15  push    rbx
0x1c003bc16  push    rsi
0x1c003bc17  push    rdi
0x1c003bc18  push    r12
0x1c003bc1a  push    r13
0x1c003bc1c  push    r14
0x1c003bc1e  push    r15
0x1c003bc20  sub     rsp, 0C0h
0x1c003bc27  mov     [rsp+0F8h+var_A8], rcx
0x1c003bc2c  xor     r14d, r14d
0x1c003bc2f  mov     edi, r14d
0x1c003bc32  mov     [rsp+0F8h+var_B0], r14
0x1c003bc37  mov     [rsp+0F8h+var_B8], r14
0x1c003bc3c  lea     r15, cs:1C0000000h
0x1c003bc43  mov     ebx, r14d
0x1c003bc46  cmp     ebx, 3
0x1c003bc49  jnb     loc_1C003BD4A
0x1c003bc4f  mov     edi, ebx
0x1c003bc51  lea     rcx, ds:1377D0h[rdi*8]
0x1c003bc59  add     rcx, r15; SpinLock
0x1c003bc5c  lea     rdx, [rsp+0F8h+LockHandle]; LockHandle
0x1c003bc64  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1c003bc6b  nop     dword ptr [rax+rax+00h]
0x1c003bc70  mov     r9, r14
0x1c003bc73  mov     eax, ebx
0x1c003bc75  shl     rax, 4
0x1c003bc79  lea     rdx, rva ?WorkerEntriesQueue@@3PAU_LIST_ENTRY@@A[r15]; _LIST_ENTRY near * WorkerEntriesQueue ...
0x1c003bc80  add     rdx, rax
0x1c003bc83  mov     r8, [rdx]
0x1c003bc86  cmp     r8, rdx
0x1c003bc89  jnz     short loc_1C003BCD0
0x1c003bc8b  mov     rdi, r14
0x1c003bc8e  cmp     r8, rdx
0x1c003bc91  cmovnz  rdi, r9
0x1c003bc95  mov     [rsp+0F8h+var_B0], rdi
0x1c003bc9a  lea     rcx, [rsp+0F8h+LockHandle]; LockHandle
0x1c003bca2  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1c003bca9  nop     dword ptr [rax+rax+00h]
0x1c003bcae  test    rdi, rdi
0x1c003bcb1  jnz     loc_1C003BD88
0x1c003bcb7  mov     eax, cs:?LazyWriterMaxWorkers@@3JA; long LazyWriterMaxWorkers
0x1c003bcbd  cmp     cs:?LazyWriterWorkersActive@@3JA, eax; long LazyWriterWorkersActive
0x1c003bcc3  jge     loc_1C0081106
0x1c003bcc9  inc     ebx
0x1c003bccb  jmp     loc_1C003BC46
0x1c003bcd0  lea     r9, [r8-18h]
0x1c003bcd4  mov     rax, [r9+48h]
0x1c003bcd8  test    rax, rax
0x1c003bcdb  jz      short loc_1C003BCEF
0x1c003bcdd  mov     ecx, [rax+0A04h]
0x1c003bce3  cmp     ecx, cs:?LazyWriterMaxWorkersPerVolume@@3JA; long LazyWriterMaxWorkersPerVolume
0x1c003bce9  jge     loc_1C00810DE
0x1c003bcef  prefetchw byte ptr [r9+10h]
0x1c003bcf4  mov     eax, [r9+10h]
0x1c003bcf8  mov     ecx, eax
0x1c003bcfa  or      ecx, 10h
0x1c003bcfd  lock cmpxchg [r9+10h], ecx
0x1c003bd03  jnz     short loc_1C003BCF8
0x1c003bd05  test    al, 10h
0x1c003bd07  jnz     loc_1C00810EE
0x1c003bd0d  mov     rcx, [r8]
0x1c003bd10  mov     rax, [r8+8]
0x1c003bd14  cmp     [rcx+8], r8
0x1c003bd18  jnz     loc_1C00810FF
0x1c003bd1e  cmp     [rax], r8
0x1c003bd21  jnz     loc_1C00810FF
0x1c003bd27  mov     [rax], rcx
0x1c003bd2a  mov     [rcx+8], rax
0x1c003bd2e  mov     [r8+8], r8
0x1c003bd32  mov     [r8], r8
0x1c003bd35  mov     dword ptr [r9+40h], 3
0x1c003bd3d  dec     rva ?WorkerEntriesQueueCount@@3PAJA[r15+rdi*4]; long near * WorkerEntriesQueueCount ...
0x1c003bd45  jmp     loc_1C003BC8B
0x1c003bd4a  test    rdi, rdi
0x1c003bd4d  jnz     short loc_1C003BD88
0x1c003bd4f  lock dec cs:?LazyWriterWorkersActive@@3JA; long LazyWriterWorkersActive
0x1c003bd56  mov     rax, [rsp+0F8h+P]
0x1c003bd5e  test    rax, rax
0x1c003bd61  jz      short loc_1C003BD74
0x1c003bd63  xor     edx, edx; Tag
0x1c003bd65  mov     rcx, rax; P
0x1c003bd68  call    cs:__imp_ExFreePoolWithTag
0x1c003bd6f  nop     dword ptr [rax+rax+00h]
0x1c003bd74  add     rsp, 0C0h
0x1c003bd7b  pop     r15
0x1c003bd7d  pop     r14
0x1c003bd7f  pop     r13
0x1c003bd81  pop     r12
0x1c003bd83  pop     rdi
0x1c003bd84  pop     rsi
0x1c003bd85  pop     rbx
0x1c003bd86  retn
0x1c003bd88  lock dec cs:?LazyWriterEntries@@3JA; long LazyWriterEntries
0x1c003bd8f  mov     rsi, [rdi+48h]
0x1c003bd93  mov     [rsp+0F8h+var_98], rsi
0x1c003bd98  mov     r13, rsi
0x1c003bd9b  lea     r12, [rsi+0A04h]
0x1c003bda2  mov     [rsp+0F8h+var_80], r12
0x1c003bda7  lock inc dword ptr [r12]
0x1c003bdac  lock dec dword ptr [rsi+0A08h]
0x1c003bdb3  lea     rax, [rdi+10h]
0x1c003bdb7  mov     [rsp+0F8h+var_78], rax
0x1c003bdbf  mov     eax, [rax]
0x1c003bdc1  test    al, 8
0x1c003bdc3  jnz     loc_1C0081110
0x1c003bdc9  mov     rax, [rdi-248h]
0x1c003bdd0  mov     [rsp+0F8h+var_C8], rax
0x1c003bdd5  mov     [rsp+0F8h+var_A0], rax
0x1c003bdda  mov     eax, [rdi+38h]
0x1c003bddd  mov     dword ptr [rsp+0F8h+arg_10], eax
0x1c003bde4  mov     dword ptr [rsp+0F8h+arg_18], eax
0x1c003bdeb  lea     rcx, [rsi+9F4h]
0x1c003bdf2  call    cs:__imp_IoSetActivityIdThread
0x1c003bdf9  nop     dword ptr [rax+rax+00h]
0x1c003bdfe  mov     [rsp+0F8h+var_88], rax
0x1c003be03  test    rax, rax
0x1c003be06  jz      short loc_1C003BE1F
0x1c003be08  mov     rdx, rax
0x1c003be0b  lea     rcx, [rsi+9F4h]
0x1c003be12  call    cs:__imp_IoTransferActivityId
0x1c003be19  nop     dword ptr [rax+rax+00h]
0x1c003be1e  nop
0x1c003be1f  mov     rdx, rsi
0x1c003be22  lea     rcx, [rsp+0F8h+var_B8]
0x1c003be27  call    MsCreateTransactionContext
0x1c003be2c  mov     [rsp+0F8h+arg_8], eax
0x1c003be33  test    eax, eax
0x1c003be35  js      short loc_1C003BEB6
0x1c003be37  mov     r12, [rsp+0F8h+var_B8]
0x1c003be3c  or      qword ptr [r12+10h], 10000h
0x1c003be45  cmp     ebx, 2
0x1c003be48  jz      short loc_1C003BE91
0x1c003be4a  mov     [rsp+0F8h+var_D8], r14
0x1c003be4f  xor     r9d, r9d
0x1c003be52  mov     rdx, [rsp+0F8h+var_C8]
0x1c003be57  mov     rcx, r12
0x1c003be5a  test    dword ptr [rsi+0C2Ch], 20000000h
0x1c003be64  jnz     short loc_1C003BEA7
0x1c003be66  lea     r8d, [r9+1]
0x1c003be6a  call    MsUpdateTree
0x1c003be6f  mov     [rsp+0F8h+arg_8], eax
0x1c003be76  mov     rcx, r12; this
0x1c003be79  test    eax, eax
0x1c003be7b  js      short loc_1C003BEAF
0x1c003be7d  xor     r8d, r8d
0x1c003be80  xor     edx, edx
0x1c003be82  call    MsCommitTransaction
0x1c003be87  mov     rcx, r12
0x1c003be8a  call    MsDeleteTransactionContext
0x1c003be8f  jmp     short loc_1C003BEB6
0x1c003be91  mov     rdx, r12; struct CmsTransactionContext *
0x1c003be94  mov     rcx, [rsp+0F8h+var_C8]; this
0x1c003be99  call    ?DelayedReleaseCachedPinList@CmsBPlusTable@@QEAAXPEAVCmsTransactionContext@@@Z; CmsBPlusTable::DelayedReleaseCachedPinList(CmsTransactionContext *)
0x1c003be9e  mov     eax, [rsp+0F8h+arg_8]
0x1c003bea5  jmp     short loc_1C003BE76
0x1c003bea7  mov     r8d, 6
0x1c003bead  jmp     short loc_1C003BE6A
0x1c003beaf  call    MsAbortTransaction
0x1c003beb4  jmp     short loc_1C003BE87
0x1c003beb6  mov     ebx, dword ptr [rsp+0F8h+arg_10]
0x1c003bebd  jmp     short loc_1C003BEF4
0x1c003bebf  xor     r14d, r14d
0x1c003bec2  lea     r15, cs:1C0000000h
0x1c003bec9  mov     rax, [rsp+0F8h+var_A8]
0x1c003bece  mov     [rsp+0F8h+P], rax
0x1c003bed6  mov     rdi, [rsp+0F8h+var_B0]
0x1c003bedb  mov     rax, [rsp+0F8h+var_A0]
0x1c003bee0  mov     [rsp+0F8h+var_C8], rax
0x1c003bee5  mov     rsi, [rsp+0F8h+var_98]
0x1c003beea  mov     ebx, dword ptr [rsp+0F8h+arg_18]
0x1c003bef1  mov     r13, rsi
0x1c003bef4  mov     rcx, [rsp+0F8h+var_88]
0x1c003bef9  call    cs:__imp_IoClearActivityIdThread
0x1c003bf00  nop     dword ptr [rax+rax+00h]
0x1c003bf05  mov     rax, [rsp+0F8h+var_80]
0x1c003bf0a  lock dec dword ptr [rax]
0x1c003bf0d  mov     rax, [rsp+0F8h+var_78]
0x1c003bf15  lock and dword ptr [rax], 0FFFFFFEFh
0x1c003bf19  neg     ebx
0x1c003bf1b  movsxd  rax, ebx
0x1c003bf1e  lock xadd cs:?PagesQueuedForWriting@@3_JA, rax; __int64 PagesQueuedForWriting
0x1c003bf27  lea     rax, [rsi+0A30h]
0x1c003bf2e  mov     [rsp+0F8h+arg_18], rax
0x1c003bf36  mov     rsi, r14
0x1c003bf39  lea     rcx, [r13+0A68h]; SpinLock
0x1c003bf40  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1c003bf47  nop     dword ptr [rax+rax+00h]
0x1c003bf4c  mov     [r13+0A70h], al
0x1c003bf53  mov     rbx, [r13+0A78h]
0x1c003bf5a  mov     [rsp+0F8h+arg_10], rbx
0x1c003bf62  test    rbx, rbx
0x1c003bf65  jz      loc_1C003C05F
0x1c003bf6b  mov     eax, [r13+0B58h]
0x1c003bf72  test    al, 4
0x1c003bf74  jz      loc_1C003C05F
0x1c003bf7a  cmp     qword ptr [r13+0B48h], 0
0x1c003bf82  jnz     loc_1C003C05F
0x1c003bf88  lea     rsi, [rbx+0EC0h]
0x1c003bf8f  mov     rcx, rsi; SpinLock
0x1c003bf92  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1c003bf99  nop     dword ptr [rax+rax+00h]
0x1c003bf9e  movzx   r10d, al
0x1c003bfa2  mov     r8, [rbx+0E78h]
0x1c003bfa9  mov     rcx, cs:RefsLargeEof
0x1c003bfb0  cmp     rcx, r8
0x1c003bfb3  jnz     loc_1C0081122
0x1c003bfb9  mov     edx, 1
0x1c003bfbe  mov     r9d, [rbx+18h]
0x1c003bfc2  mov     r12d, [rbx+0E50h]
0x1c003bfc9  test    edx, edx
0x1c003bfcb  mov     edx, [rbx+20h]
0x1c003bfce  jz      loc_1C008112A
0x1c003bfd4  mov     ebx, edx
0x1c003bfd6  sub     rbx, r9
0x1c003bfd9  imul    rbx, r12
0x1c003bfdd  mov     [rsp+0F8h+var_60], rbx
0x1c003bfe5  cmp     rcx, r8
0x1c003bfe8  jnz     loc_1C0081138
0x1c003bfee  mov     eax, 1
0x1c003bff3  test    eax, eax
0x1c003bff5  jz      loc_1C0081140
0x1c003bffb  mov     rax, [rsp+0F8h+arg_10]
0x1c003c003  mov     eax, [rax+0E70h]
0x1c003c009  sub     rax, rdx
0x1c003c00c  add     rax, r9
0x1c003c00f  imul    r12, rax
0x1c003c013  mov     [rsp+0F8h+var_58], r12
0x1c003c01b  movzx   edx, r10b; NewIrql
0x1c003c01f  mov     rcx, rsi; SpinLock
0x1c003c022  call    cs:__imp_KeReleaseSpinLock
0x1c003c029  nop     dword ptr [rax+rax+00h]
0x1c003c02e  lea     rcx, [r12+rbx]
0x1c003c032  mov     eax, [r13+0B50h]
0x1c003c039  add     rax, rbx
0x1c003c03c  imul    rsi, rax, 64h ; 'd'
0x1c003c040  cmp     rcx, 20000000h
0x1c003c047  jnz     loc_1C003C29F
0x1c003c04d  shr     rsi, 1Dh
0x1c003c051  mov     [r13+0A38h], rbx
0x1c003c058  mov     [r13+0A40h], r12
0x1c003c05f  movzx   edx, byte ptr [r13+0A70h]; NewIrql
0x1c003c067  lea     rcx, [r13+0A68h]; SpinLock
0x1c003c06e  call    cs:__imp_KeReleaseSpinLock
0x1c003c075  nop     dword ptr [rax+rax+00h]
0x1c003c07a  movzx   r12d, sil
0x1c003c07e  mov     rbx, cs:RefsLargeEof
0x1c003c085  mov     [rsp+0F8h+var_C0], rbx
0x1c003c08a  lea     rsi, [r13+0A68h]
0x1c003c091  mov     rcx, rsi; SpinLock
0x1c003c094  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1c003c09b  nop     dword ptr [rax+rax+00h]
0x1c003c0a0  mov     [r13+0A70h], al
0x1c003c0a7  lea     rax, [r13+0A48h]
0x1c003c0ae  mov     rcx, [rax]
0x1c003c0b1  cmp     rcx, rax
0x1c003c0b4  jnz     loc_1C003C21A
0x1c003c0ba  cmp     cs:RefsLargeEof, rbx
0x1c003c0c1  jnz     short loc_1C003C12A
0x1c003c0c3  mov     rbx, [r13+0B48h]
0x1c003c0ca  test    rbx, rbx
0x1c003c0cd  jnz     loc_1C008114B
0x1c003c0d3  mov     rbx, [r13+0A78h]
0x1c003c0da  test    rbx, rbx
0x1c003c0dd  jz      loc_1C0081151
0x1c003c0e3  mov     eax, [r13+0B58h]
0x1c003c0ea  test    al, 4
0x1c003c0ec  jz      loc_1C0081151
0x1c003c0f2  lea     rsi, [rbx+0EC0h]
0x1c003c0f9  mov     rcx, rsi; SpinLock
0x1c003c0fc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1c003c103  nop     dword ptr [rax+rax+00h]
0x1c003c108  mov     rbx, [rbx+20h]
0x1c003c10c  mov     [rsp+0F8h+var_C0], rbx
0x1c003c111  movzx   edx, al; NewIrql
0x1c003c114  mov     rcx, rsi; SpinLock
0x1c003c117  call    cs:__imp_KeReleaseSpinLock
0x1c003c11e  nop     dword ptr [rax+rax+00h]
0x1c003c123  lea     rsi, [r13+0A68h]
0x1c003c12a  movzx   edx, byte ptr [r13+0A70h]; NewIrql
0x1c003c132  mov     rcx, rsi; SpinLock
0x1c003c135  call    cs:__imp_KeReleaseSpinLock
0x1c003c13c  nop     dword ptr [rax+rax+00h]
0x1c003c141  cmp     cs:RefsLargeEof, rbx
0x1c003c148  jz      loc_1C008118B
0x1c003c14e  cmp     cs:ML_LSN_NULL, rbx
0x1c003c155  jz      loc_1C008118B
0x1c003c15b  mov     rcx, rsi; SpinLock
0x1c003c15e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1c003c165  nop     dword ptr [rax+rax+00h]
0x1c003c16a  movzx   r9d, al
0x1c003c16e  mov     [r13+0A70h], al
0x1c003c175  mov     ecx, [r13+0B58h]
0x1c003c17c  test    cl, 4
0x1c003c17f  jz      loc_1C0081162
0x1c003c185  mov     rdx, [r13+0AB0h]
0x1c003c18c  mov     rcx, rdx
0x1c003c18f  shr     rcx, 20h
0x1c003c193  mov     rax, rbx
0x1c003c196  shr     rax, 20h
  ... truncated ...
```
