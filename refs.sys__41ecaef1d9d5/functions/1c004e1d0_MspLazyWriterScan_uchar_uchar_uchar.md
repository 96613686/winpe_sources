# MspLazyWriterScan(uchar,uchar,uchar)

- ea: `0x1c004e1d0`
- end: `0x1c004e89e`
- name: `?MspLazyWriterScan@@YAXEEE@Z`
- size: `1742`
- prototype: `void __fastcall(unsigned __int8, unsigned __int8, unsigned __int8)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1c004d380`

## callees

- `0x1c002357c`
- `0x1c004d1f4`
- `0x1c004e1d0`
- `0x1c004e8c0`
- `0x1c00b4508`
- `0x1c00b477c`
- `0x1c00cc800`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c004e61f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c004e61f`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1c004e3dd`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1c004e3dd`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c004e502`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c004e7e2`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c0086a19`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c004e502`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c004e7e2`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c0086a19`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c004e63a`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c004e63a`
- `ntoskrnl!ExQueueWorkItem` at `0x1c004e68d`
- `ntoskrnl!ExQueueWorkItem` at `0x1c004e68d`
- `ntoskrnl!ExIsFastResourceHeld` at `0x1c004e4cf`
- `ntoskrnl!ExIsFastResourceHeld` at `0x1c004e4cf`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1c004e25b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1c004e565`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1c004e6a7`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1c0086aba`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1c004e25b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1c004e565`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1c004e6a7`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1c0086aba`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1c004e385`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1c004e5cf`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1c004e738`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1c0086acf`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1c0086b57`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1c004e385`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1c004e5cf`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1c004e738`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1c0086acf`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1c0086b57`

## pseudocode

```c
void __fastcall MspLazyWriterScan(char a1, char a2, char a3)
{
  char v3; // r12
  char v4; // r15
  struct _LIST_ENTRY **p_Blink; // rsi
  __int64 v6; // rbx
  __int64 v7; // r14
  struct _LIST_ENTRY *v8; // rdi
  int Flink; // eax
  int v10; // ecx
  CmsReferenced **v11; // rbx
  struct _LIST_ENTRY *v12; // r14
  struct _LIST_ENTRY *v13; // rax
  int *v14; // r12
  CmsBPlusTable *v15; // rbx
  __int64 v16; // r13
  int v17; // r8d
  int v18; // r11d
  char *v19; // r9
  int v20; // ecx
  int v21; // edx
  int v22; // ecx
  bool v23; // cc
  int v24; // r15d
  struct _LIST_ENTRY *v25; // rbx
  unsigned __int64 v26; // r12
  struct _LIST_ENTRY *v27; // rax
  int v28; // r13d
  unsigned int v29; // ebx
  char v30; // r15
  int v31; // eax
  __int64 *v32; // rcx
  __int64 i; // rdx
  __int64 **v34; // rax
  __int64 *v35; // r14
  char *PoolWithTag; // rbx
  _OWORD *ActivityIdThread; // rax
  struct _LIST_ENTRY *v38; // rax
  unsigned __int64 v39; // rbx
  int v40; // eax
  struct _LIST_ENTRY *v41; // rcx
  struct _LIST_ENTRY **v42; // rax
  struct _LIST_ENTRY *v43; // rdx
  struct _LIST_ENTRY *v44; // rax
  struct _LIST_ENTRY *v45; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 v46; // [rsp+28h] [rbp-D8h]
  unsigned __int64 v47; // [rsp+30h] [rbp-D0h]
  struct _LIST_ENTRY **v48; // [rsp+38h] [rbp-C8h]
  int Blink; // [rsp+40h] [rbp-C0h]
  unsigned __int64 v50; // [rsp+48h] [rbp-B8h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+50h] [rbp-B0h] BYREF
  struct _LIST_ENTRY *v52; // [rsp+70h] [rbp-90h] BYREF
  struct _LIST_ENTRY *v53; // [rsp+78h] [rbp-88h]
  int v54; // [rsp+80h] [rbp-80h]
  _QWORD v55[4]; // [rsp+88h] [rbp-78h] BYREF
  int v56; // [rsp+A8h] [rbp-58h]
  int v57; // [rsp+B0h] [rbp-50h]
  __int64 v58; // [rsp+C0h] [rbp-40h]
  int v59; // [rsp+C8h] [rbp-38h]
  __int64 v60; // [rsp+D0h] [rbp-30h]
  PERESOURCE Resource; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v62; // [rsp+E0h] [rbp-20h] BYREF
  struct _KLOCK_QUEUE_HANDLE v63; // [rsp+E8h] [rbp-18h] BYREF
  struct _KLOCK_QUEUE_HANDLE v64; // [rsp+100h] [rbp+0h] BYREF
  char v67; // [rsp+180h] [rbp+80h]
  char v68; // [rsp+188h] [rbp+88h]

  v67 = a3;
  v57 = 3;
  v53 = (struct _LIST_ENTRY *)&v52;
  v68 = 1;
  v52 = (struct _LIST_ENTRY *)&v52;
  v3 = a2;
  v4 = a3;
  v55[1] = v55;
  v55[0] = v55;
  v54 = 0;
  p_Blink = 0;
  v56 = 0;
  v6 = 0;
  v58 = 0;
  v7 = 0;
  v59 = 0;
  v47 = 0;
  v46 = 0;
  KeAcquireInStackQueuedSpinLock(&LazyWriterSpinLock, &LockHandle);
  if ( v3 )
  {
    v6 = 1;
    if ( TargetPagesToWrite > PagesQueuedForWriting )
      v6 = TargetPagesToWrite - PagesQueuedForWriting;
    v47 = v6;
    if ( NumberOfDirtyPages >= 12000 && v6 >= 90 * NumberOfDirtyPages / 100 )
      v68 = 0;
    if ( NumberOfDirtyTableListEntries > TargetAggresiveBindableTreshold )
    {
      v68 = 0;
      if ( NumberOfDirtyPages > v6 )
        v6 = NumberOfDirtyPages;
      v47 = v6;
    }
  }
  while ( 1 )
  {
    v8 = DirtyTableList;
    v45 = DirtyTableList;
    if ( DirtyTableList != (struct _LIST_ENTRY *)&DirtyTableList )
    {
      while ( 1 )
      {
        if ( v3 && v7 >= v6 && !v4 )
          goto LABEL_62;
        Flink = (int)v8[1].Flink;
        if ( (Flink & 2) == 0 )
        {
          v10 = (int)v8[4].Flink;
          if ( (Flink & 8) != 0 )
          {
            if ( v10 == 3 && (Flink & 0x10) == 0 && !v4 )
              MspQueueEntry(v8, 1);
            goto LABEL_60;
          }
          if ( (v10 == 3 || v4) && (Flink & 0x10) == 0 && v10 )
            break;
        }
LABEL_60:
        v8 = v8->Flink;
        v6 = v47;
        v45 = v8;
        if ( v8 == (struct _LIST_ENTRY *)&DirtyTableList )
          goto LABEL_61;
      }
      v11 = (CmsReferenced **)p_Blink;
      if ( (Flink & 1) != 0 )
        p_Blink = &v8[-37].Blink;
      else
        p_Blink = 0;
      _InterlockedIncrement((volatile signed __int32 *)&(*p_Blink)->Blink);
      v12 = v45;
      v54 = 2;
      v13 = v45->Flink;
      if ( v45->Flink->Blink != v45 )
        goto LABEL_125;
      v52 = v45->Flink;
      v53 = v45;
      v13->Blink = (struct _LIST_ENTRY *)&v52;
      v12->Flink = (struct _LIST_ENTRY *)&v52;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      if ( v11 )
        CmsReferenced::Release(*v11);
      v14 = (int *)&v12[3].Blink;
      v15 = (CmsBPlusTable *)*p_Blink;
      Blink = (int)v12[3].Blink;
      v50 = 0;
      v48 = &v12[3].Blink;
      v16 = *(_QWORD *)(*((_QWORD *)v15 + 12) + 24LL);
      v60 = v16;
      if ( a2 )
      {
        Resource = (PERESOURCE)(v16 + 3160);
        ExAcquireResourceSharedLite((PERESOURCE)(v16 + 3160), 1u);
        if ( p_Blink[16] == (struct _LIST_ENTRY *)p_Blink
          && (!v4 || BoundSetDelayingCheckpoint((struct _SmsBindable *)p_Blink, &v50)) )
        {
          v17 = 0;
          v18 = 0;
          v19 = (char *)(p_Blink + 14);
          do
          {
            v20 = *((_DWORD *)v19 + 63);
            v21 = v17;
            v19 = *(char **)v19;
            v22 = v17 + v20;
            v23 = v22 <= v17;
            v17 = v22;
            if ( v23 )
              v17 = v21;
            if ( v19 == (char *)(p_Blink + 14) )
              break;
            v40 = v18++;
          }
          while ( v40 < 100 );
          v24 = v17;
          if ( v18 >= 100 && v17 < 2147478647 )
            v24 = v17 + 5000;
          if ( v24 < 0 )
            v24 = 0;
          v25 = (struct _LIST_ENTRY *)MEMORY[0xFFFFF78000000014];
          v12 = v45;
          if ( *v14 != v24 && LODWORD(v8[4].Flink) == 3 && ((__int64)v8[1].Flink & 0x10) == 0 )
          {
            *v14 = v24;
            v12[3].Flink = v25;
          }
          if ( !v67 )
          {
            v26 = 0;
            v27 = (*p_Blink)[6].Flink[1].Blink;
            v28 = (int)v27[115].Flink;
            if ( v46 < v47 )
              v26 = v47 - v46;
            if ( !BYTE2(v27[194].Blink)
              || v68
              && (*((_DWORD *)p_Blink + 160)
               || (unsigned int)(v28 - 1) <= *((_DWORD *)p_Blink + 168)
               && (unsigned __int8)ExIsFastResourceHeld(p_Blink + 1))
              && (unsigned __int64)((char *)v25 - (char *)p_Blink[78]) < 0x11E1A300
              && (v39 = (char *)v25 - (char *)p_Blink[79], v39 <= 0x55D4A80)
              && (v39 <= 0x2FAF080 || *((int *)p_Blink + 160) > v26)
              && !BoundSetDelayingCheckpoint((struct _SmsBindable *)p_Blink, &v62)
              && (!dword_1C0136C84
               || *((_DWORD *)p_Blink + 59)
                + *((_DWORD *)p_Blink + 63)
                + *((_DWORD *)p_Blink + 77)
                + *((_DWORD *)p_Blink + 81) < (unsigned int)dword_1C0136C84) )
            {
              ExReleaseResourceLite(Resource);
              goto LABEL_71;
            }
            v14 = (int *)v48;
            *((_DWORD *)p_Blink + 168) = v28;
            v16 = v60;
          }
          v46 += v24;
          ExReleaseResourceLite((PERESOURCE)(v16 + 3160));
LABEL_40:
          v29 = (unsigned int)v8[4].Flink;
          v30 = 0;
          if ( v29 != 3 )
          {
            while ( 1 )
            {
              KeAcquireInStackQueuedSpinLock(&LazyWriterQueueSpinLock + v29, &v63);
              if ( v29 == LODWORD(v8[4].Flink) )
                break;
              KeReleaseInStackQueuedSpinLock(&v63);
              v29 = (unsigned int)v8[4].Flink;
              if ( v29 == 3 )
                goto LABEL_110;
            }
            v41 = v12[1].Blink;
            v42 = &v12[1].Blink;
            if ( v41 != (struct _LIST_ENTRY *)&v12[1].Blink )
            {
              if ( (struct _LIST_ENTRY **)v41->Blink != v42 )
                goto LABEL_125;
              v43 = v12[2].Flink;
              if ( (struct _LIST_ENTRY **)v43->Flink != v42 )
                goto LABEL_125;
              v43->Flink = v41;
              v41->Blink = v43;
              v12[2].Flink = (struct _LIST_ENTRY *)((char *)v12 + 24);
              *v42 = (struct _LIST_ENTRY *)v42;
              v44 = v12[4].Blink;
              if ( v44 )
                --LODWORD(v44[160].Blink);
              v30 = 1;
              --*((_DWORD *)&WorkerEntriesQueueCount + v29);
              _InterlockedDecrement(&LazyWriterEntries);
              v12 = v45;
              LODWORD(v8[4].Flink) = 3;
            }
            KeReleaseInStackQueuedSpinLock(&v63);
            if ( v30 )
            {
              CmsReferenced::Release((CmsReferenced *)*p_Blink);
              _InterlockedExchangeAdd64(&PagesQueuedForWriting, -Blink);
              v12 = v45;
              v14 = (int *)v48;
              goto LABEL_42;
            }
LABEL_110:
            v14 = (int *)v48;
          }
          if ( ((__int64)v8[1].Flink & 0x10) != 0 )
          {
LABEL_71:
            MspAcquireLazyWriterLockAtEntry(&LockHandle, &v45, (struct _SmsLazyWriterEntry *)&v52);
            v8 = v45;
            v4 = v67;
LABEL_59:
            v3 = a2;
            v7 = v46;
            goto LABEL_60;
          }
LABEL_42:
          HIDWORD(v12[3].Blink) = *((_DWORD *)p_Blink + 90);
          v12[5].Flink = (struct _LIST_ENTRY *)v50;
          v12[4].Blink = (struct _LIST_ENTRY *)v16;
          if ( a1 )
          {
            MspQueueEntry(v12, 2);
            v4 = v67;
          }
          else
          {
            v4 = v67;
            if ( v67 )
            {
              MspQueueEntry(v12, 0);
            }
            else
            {
              KeAcquireInStackQueuedSpinLock(&SpinLock, &v64);
              v31 = (int)v8[1].Flink;
              LODWORD(v8[4].Flink) = 1;
              v32 = &qword_1C0137800;
              if ( (v31 & 1) != 0 )
              {
                for ( i = qword_1C0137808; (__int64 *)i != &qword_1C0137800; i = *(_QWORD *)(i + 8) )
                {
                  if ( *(_QWORD *)(i + 48) == v16 )
                  {
                    if ( (*(_DWORD *)(i - 8) & 8) != 0 || *(_DWORD *)(i + 36) >= SHIDWORD(v12[3].Blink) )
                      break;
                    v32 = (__int64 *)i;
                  }
                }
              }
              v34 = (__int64 **)v32[1];
              v35 = (__int64 *)&v12[1].Blink;
              if ( *v34 != v32 )
LABEL_125:
                __fastfail(3u);
              ++dword_1C0136D6C;
              *v35 = (__int64)v32;
              v35[1] = (__int64)v34;
              *v34 = v35;
              v32[1] = (__int64)v35;
              _InterlockedExchangeAdd64(&PagesQueuedForWriting, *v14);
              KeReleaseInStackQueuedSpinLock(&v64);
              _InterlockedIncrement((volatile signed __int32 *)(v16 + 2568));
              _InterlockedIncrement(&LazyWriterEntries);
              if ( *(_DWORD *)(v16 + 2564) < LazyWriterMaxWorkersPerVolume
                && LazyWriterWorkersActive < LazyWriterMaxWorkers )
              {
                PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)512, 0x40u, 0x6950534Du);
                if ( PoolWithTag )
                {
                  _InterlockedIncrement(&LazyWriterWorkersActive);
                  ActivityIdThread = (_OWORD *)IoGetActivityIdThread();
                  if ( ActivityIdThread && KeGetCurrentIrql() < 2u )
                    *(_OWORD *)PoolWithTag = *ActivityIdThread;
                  else
                    *(_OWORD *)PoolWithTag = 0;
                  *((_QWORD *)PoolWithTag + 7) = PoolWithTag;
                  *((_QWORD *)PoolWithTag + 5) = PoolWithTag;
                  *((_QWORD *)PoolWithTag + 6) = MspLazyWriterWorker;
                  *((_QWORD *)PoolWithTag + 2) = 0;
                  *((_QWORD *)PoolWithTag + 4) = MspWorkerRoutine;
                  ExQueueWorkItem((PWORK_QUEUE_ITEM)(PoolWithTag + 16), CriticalWorkQueue);
                }
              }
            }
          }
          p_Blink = 0;
          KeAcquireInStackQueuedSpinLock(&LazyWriterSpinLock, &LockHandle);
          v38 = v52;
          v8 = v53;
          if ( (struct _LIST_ENTRY **)v52->Blink != &v52 || (struct _LIST_ENTRY **)v53->Flink != &v52 )
            goto LABEL_125;
          v53->Flink = v52;
          v38->Blink = v8;
          if ( (struct _LIST_ENTRY **)v8->Flink == &v52 )
            v8 = (struct _LIST_ENTRY *)&DirtyTableList;
          v53 = (struct _LIST_ENTRY *)&v52;
          v52 = (struct _LIST_ENTRY *)&v52;
          goto LABEL_59;
        }
        ExReleaseResourceLite((PERESOURCE)(v16 + 3160));
      }
      else if ( !a1
             || (int)CmsBPlusTable::GetBoundSetDirtyPageCount((struct _SmsBindable *)p_Blink) <= 0
             && CmsBPlusTable::HasCachedPins(v15) )
      {
        goto LABEL_40;
      }
      MspAcquireLazyWriterLockAtEntry(&LockHandle, &v45, (struct _SmsLazyWriterEntry *)&v52);
      v8 = v45;
      goto LABEL_59;
    }
LABEL_61:
    if ( !v4 )
      break;
    v6 = v47;
    v4 = 0;
    v67 = 0;
  }
LABEL_62:
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( p_Blink )
    CmsReferenced::Release((CmsReferenced *)*p_Blink);
}

```

## disassembly

```asm
0x1c004e1d0  mov     [rsp-8+arg_10], r8b
0x1c004e1d5  mov     [rsp-8+arg_8], dl
0x1c004e1d9  mov     [rsp-8+arg_0], cl
0x1c004e1dd  push    rbp
0x1c004e1de  push    rbx
0x1c004e1df  push    rsi
0x1c004e1e0  push    rdi
0x1c004e1e1  push    r12
0x1c004e1e3  push    r13
0x1c004e1e5  push    r14
0x1c004e1e7  push    r15
0x1c004e1e9  lea     rbp, [rsp-28h]
0x1c004e1ee  sub     rsp, 128h
0x1c004e1f5  lea     rax, [rsp+160h+var_F0]
0x1c004e1fa  mov     [rbp+60h+var_B0], 3
0x1c004e201  mov     [rsp+160h+var_E8], rax
0x1c004e206  lea     rcx, ?LazyWriterSpinLock@@3_KA; SpinLock
0x1c004e20d  lea     rax, [rsp+160h+var_F0]
0x1c004e212  mov     [rbp+60h+arg_18], 1
0x1c004e219  mov     [rsp+160h+var_F0], rax
0x1c004e21e  movzx   r12d, dl
0x1c004e222  lea     rax, [rbp+60h+var_D8]
0x1c004e226  movzx   r15d, r8b
0x1c004e22a  mov     [rbp+60h+var_D0], rax
0x1c004e22e  lea     rdx, [rsp+160h+LockHandle]; LockHandle
0x1c004e233  lea     rax, [rbp+60h+var_D8]
0x1c004e237  mov     [rbp+60h+var_D8], rax
0x1c004e23b  xor     eax, eax
0x1c004e23d  mov     [rbp+60h+var_E0], eax
0x1c004e240  mov     esi, eax
0x1c004e242  mov     [rbp+60h+var_B8], eax
0x1c004e245  mov     ebx, eax
0x1c004e247  mov     [rbp+60h+var_A0], rax
0x1c004e24b  mov     r14d, eax
0x1c004e24e  mov     [rbp+60h+var_98], eax
0x1c004e251  mov     [rsp+160h+var_130], rax
0x1c004e256  mov     [rsp+160h+var_138], rax
0x1c004e25b  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1c004e262  nop     dword ptr [rax+rax+00h]
0x1c004e267  test    r12b, r12b
0x1c004e26a  jz      short loc_1C004E2DA
0x1c004e26c  mov     rcx, cs:?TargetPagesToWrite@@3_JA; __int64 TargetPagesToWrite
0x1c004e273  mov     ebx, 1
0x1c004e278  mov     r8, cs:?NumberOfDirtyPages@@3_JA; __int64 NumberOfDirtyPages
0x1c004e27f  mov     rdx, rcx
0x1c004e282  sub     rdx, cs:?PagesQueuedForWriting@@3_JA; __int64 PagesQueuedForWriting
0x1c004e289  mov     rax, 0A3D70A3D70A3D70Bh
0x1c004e293  cmp     rcx, cs:?PagesQueuedForWriting@@3_JA; __int64 PagesQueuedForWriting
0x1c004e29a  cmovg   rbx, rdx
0x1c004e29e  imul    rcx, r8, 5Ah ; 'Z'
0x1c004e2a2  mov     [rsp+160h+var_130], rbx
0x1c004e2a7  imul    rcx
0x1c004e2aa  add     rdx, rcx
0x1c004e2ad  sar     rdx, 6
0x1c004e2b1  mov     rax, rdx
0x1c004e2b4  shr     rax, 3Fh
0x1c004e2b8  add     rdx, rax
0x1c004e2bb  cmp     r8, 2EE0h
0x1c004e2c2  jge     loc_1C004E851
0x1c004e2c8  mov     eax, cs:?TargetAggresiveBindableTreshold@@3KA; ulong TargetAggresiveBindableTreshold
0x1c004e2ce  cmp     cs:?NumberOfDirtyTableListEntries@@3KA, eax; ulong NumberOfDirtyTableListEntries
0x1c004e2d4  ja      loc_1C00869A2
0x1c004e2da  lea     rax, ?DirtyTableList@@3U_LIST_ENTRY@@A; _LIST_ENTRY DirtyTableList
0x1c004e2e1  mov     rdi, cs:?DirtyTableList@@3U_LIST_ENTRY@@A; _LIST_ENTRY DirtyTableList
0x1c004e2e8  mov     [rsp+160h+var_140], rdi
0x1c004e2ed  cmp     rdi, rax
0x1c004e2f0  jz      loc_1C004E72A
0x1c004e2f6  test    r12b, r12b
0x1c004e2f9  jz      short loc_1C004E304
0x1c004e2fb  cmp     r14, rbx
0x1c004e2fe  jge     loc_1C00869BA
0x1c004e304  mov     eax, [rdi+10h]
0x1c004e307  test    al, 2
0x1c004e309  jnz     loc_1C004E70D
0x1c004e30f  mov     ecx, [rdi+40h]
0x1c004e312  test    al, 8
0x1c004e314  jnz     loc_1C00869C8
0x1c004e31a  cmp     ecx, 3
0x1c004e31d  jnz     loc_1C00869F3
0x1c004e323  test    al, 10h
0x1c004e325  jnz     loc_1C004E70D
0x1c004e32b  test    ecx, ecx
0x1c004e32d  jz      loc_1C004E70D
0x1c004e333  mov     rbx, rsi
0x1c004e336  test    al, 1
0x1c004e338  jz      loc_1C0086A01
0x1c004e33e  lea     rsi, [rdi-248h]
0x1c004e345  mov     rax, [rsi]
0x1c004e348  lock inc dword ptr [rax+8]
0x1c004e34c  mov     r14, [rsp+160h+var_140]
0x1c004e351  mov     [rbp+60h+var_E0], 2
0x1c004e358  mov     rax, [r14]
0x1c004e35b  cmp     [rax+8], r14
0x1c004e35f  jnz     loc_1C0086BFB
0x1c004e365  mov     [rsp+160h+var_F0], rax
0x1c004e36a  lea     rcx, [rsp+160h+var_F0]
0x1c004e36f  mov     [rsp+160h+var_E8], r14
0x1c004e374  mov     [rax+8], rcx
0x1c004e378  lea     rax, [rsp+160h+var_F0]
0x1c004e37d  lea     rcx, [rsp+160h+LockHandle]; LockHandle
0x1c004e382  mov     [r14], rax
0x1c004e385  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1c004e38c  nop     dword ptr [rax+rax+00h]
0x1c004e391  test    rbx, rbx
0x1c004e394  jnz     loc_1C0086A08
0x1c004e39a  cmp     [rbp+60h+arg_8], 0
0x1c004e39e  lea     r12, [r14+38h]
0x1c004e3a2  mov     eax, [r12]
0x1c004e3a6  mov     rbx, [rsi]
0x1c004e3a9  mov     [rsp+160h+var_120], eax
0x1c004e3ad  mov     [rsp+160h+var_118], 0
0x1c004e3b6  mov     [rsp+160h+var_128], r12
0x1c004e3bb  mov     rax, [rbx+60h]
0x1c004e3bf  mov     r13, [rax+18h]
0x1c004e3c3  mov     [rbp+60h+var_90], r13
0x1c004e3c7  jz      loc_1C0086A7A
0x1c004e3cd  lea     rbx, [r13+0C58h]
0x1c004e3d4  mov     dl, 1; Wait
0x1c004e3d6  mov     rcx, rbx; Resource
0x1c004e3d9  mov     [rbp+60h+Resource], rbx
0x1c004e3dd  call    cs:__imp_ExAcquireResourceSharedLite
0x1c004e3e4  nop     dword ptr [rax+rax+00h]
0x1c004e3e9  mov     rax, [rsi+80h]
0x1c004e3f0  cmp     rax, rsi
0x1c004e3f3  jnz     loc_1C0086A16
0x1c004e3f9  test    r15b, r15b
0x1c004e3fc  jnz     loc_1C0086A43
0x1c004e402  xor     r8d, r8d
0x1c004e405  lea     r10, [rsi+70h]
0x1c004e409  xor     r11d, r11d
0x1c004e40c  mov     r9, r10
0x1c004e40f  mov     ecx, [r9+0FCh]
0x1c004e416  mov     edx, r8d
0x1c004e419  mov     r9, [r9]
0x1c004e41c  add     ecx, r8d
0x1c004e41f  cmp     ecx, edx
0x1c004e421  mov     r8d, ecx
0x1c004e424  cmovle  r8d, edx
0x1c004e428  cmp     r9, r10
0x1c004e42b  jnz     loc_1C004E88A
0x1c004e431  mov     r15d, r8d
0x1c004e434  cmp     r11d, 64h ; 'd'
0x1c004e438  jge     loc_1C0086A59
0x1c004e43e  test    r15d, r15d
0x1c004e441  js      loc_1C0086A72
0x1c004e447  mov     rax, 0FFFFF78000000014h
0x1c004e451  mov     rbx, [rax]
0x1c004e454  mov     r14, [rsp+160h+var_140]
0x1c004e459  cmp     [r12], r15d
0x1c004e45d  jnz     loc_1C004E821
0x1c004e463  cmp     [rbp+60h+arg_10], 0
0x1c004e46a  jnz     loc_1C004E4F3
0x1c004e470  mov     rax, [rsi]
0x1c004e473  xor     r12d, r12d
0x1c004e476  mov     rdx, [rsp+160h+var_130]
0x1c004e47b  mov     r8, [rsp+160h+var_138]
0x1c004e480  mov     rcx, [rax+60h]
0x1c004e484  mov     rax, [rcx+18h]
0x1c004e488  mov     ecx, [rsi+2A0h]
0x1c004e48e  mov     r13d, [rax+730h]
0x1c004e495  cmp     r8, rdx
0x1c004e498  jnb     short loc_1C004E4A0
0x1c004e49a  mov     r12, rdx
0x1c004e49d  sub     r12, r8
0x1c004e4a0  cmp     byte ptr [rax+0C2Ah], 0
0x1c004e4a7  jz      loc_1C004E7DE
0x1c004e4ad  cmp     [rbp+60h+arg_18], 0
0x1c004e4b4  jz      short loc_1C004E4E3
0x1c004e4b6  cmp     dword ptr [rsi+280h], 0
0x1c004e4bd  jnz     loc_1C004E762
0x1c004e4c3  lea     eax, [r13-1]
0x1c004e4c7  cmp     eax, ecx
0x1c004e4c9  ja      short loc_1C004E4E3
0x1c004e4cb  lea     rcx, [rsi+8]
0x1c004e4cf  call    cs:__imp_ExIsFastResourceHeld
0x1c004e4d6  nop     dword ptr [rax+rax+00h]
0x1c004e4db  test    al, al
0x1c004e4dd  jnz     loc_1C004E762
0x1c004e4e3  mov     r12, [rsp+160h+var_128]
0x1c004e4e8  mov     [rsi+2A0h], r13d
0x1c004e4ef  mov     r13, [rbp+60h+var_90]
0x1c004e4f3  movsxd  rax, r15d
0x1c004e4f6  lea     rcx, [r13+0C58h]; Resource
0x1c004e4fd  add     [rsp+160h+var_138], rax
0x1c004e502  call    cs:__imp_ExReleaseResourceLite
0x1c004e509  nop     dword ptr [rax+rax+00h]
0x1c004e50e  mov     ebx, [rdi+40h]
0x1c004e511  xor     r15b, r15b
0x1c004e514  cmp     ebx, 3
0x1c004e517  jnz     loc_1C0086AA1
0x1c004e51d  mov     eax, [rdi+10h]
0x1c004e520  test    al, 10h
0x1c004e522  jnz     loc_1C004E7EE
0x1c004e528  cmp     [rbp+60h+arg_0], 0
0x1c004e52c  mov     eax, [rsi+168h]
0x1c004e532  mov     [r14+3Ch], eax
0x1c004e536  mov     rax, [rsp+160h+var_118]
0x1c004e53b  mov     [r14+50h], rax
0x1c004e53f  mov     [r14+48h], r13
0x1c004e543  jnz     loc_1C0086B94
0x1c004e549  movzx   r15d, [rbp+60h+arg_10]
0x1c004e551  test    r15b, r15b
0x1c004e554  jnz     loc_1C0086BAE
0x1c004e55a  lea     rdx, [rbp+60h+var_60]; LockHandle
0x1c004e55e  lea     rcx, SpinLock; SpinLock
0x1c004e565  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1c004e56c  nop     dword ptr [rax+rax+00h]
0x1c004e571  mov     eax, [rdi+10h]
0x1c004e574  lea     r8, qword_1C0137800
0x1c004e57b  mov     dword ptr [rdi+40h], 1
0x1c004e582  mov     rcx, r8
0x1c004e585  test    al, 1
0x1c004e587  jz      short loc_1C004E599
0x1c004e589  mov     rdx, cs:qword_1C0137808
0x1c004e590  cmp     rdx, r8
0x1c004e593  jnz     loc_1C004E860
0x1c004e599  mov     rax, [rcx+8]
0x1c004e59d  add     r14, 18h
0x1c004e5a1  cmp     [rax], rcx
0x1c004e5a4  jnz     loc_1C0086BFB
0x1c004e5aa  inc     cs:dword_1C0136D6C
0x1c004e5b0  mov     [r14], rcx
0x1c004e5b3  mov     [r14+8], rax
0x1c004e5b7  mov     [rax], r14
0x1c004e5ba  mov     [rcx+8], r14
0x1c004e5be  movsxd  rax, dword ptr [r12]
0x1c004e5c2  lock xadd cs:?PagesQueuedForWriting@@3_JA, rax; __int64 PagesQueuedForWriting
0x1c004e5cb  lea     rcx, [rbp+60h+var_60]; LockHandle
0x1c004e5cf  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1c004e5d6  nop     dword ptr [rax+rax+00h]
0x1c004e5db  lock inc dword ptr [r13+0A08h]
0x1c004e5e3  lock inc cs:?LazyWriterEntries@@3JA; long LazyWriterEntries
0x1c004e5ea  mov     eax, cs:?LazyWriterMaxWorkersPerVolume@@3JA; long LazyWriterMaxWorkersPerVolume
0x1c004e5f0  cmp     [r13+0A04h], eax
0x1c004e5f7  jge     loc_1C004E699
0x1c004e5fd  mov     eax, cs:?LazyWriterMaxWorkers@@3JA; long LazyWriterMaxWorkers
0x1c004e603  cmp     cs:?LazyWriterWorkersActive@@3JA, eax; long LazyWriterWorkersActive
0x1c004e609  jge     loc_1C004E699
0x1c004e60f  mov     edx, 40h ; '@'; NumberOfBytes
0x1c004e614  mov     ecx, 200h; PoolType
0x1c004e619  mov     r8d, 6950534Dh; Tag
0x1c004e61f  call    cs:__imp_ExAllocatePoolWithTag
0x1c004e626  nop     dword ptr [rax+rax+00h]
0x1c004e62b  mov     rbx, rax
0x1c004e62e  test    rax, rax
0x1c004e631  jz      short loc_1C004E699
0x1c004e633  lock inc cs:?LazyWriterWorkersActive@@3JA; long LazyWriterWorkersActive
0x1c004e63a  call    cs:__imp_IoGetActivityIdThread
0x1c004e641  nop     dword ptr [rax+rax+00h]
0x1c004e646  test    rax, rax
0x1c004e649  jz      loc_1C0086BD0
0x1c004e64f  mov     rcx, cr8
0x1c004e653  cmp     cl, 2
0x1c004e656  jnb     loc_1C0086BD0
0x1c004e65c  movups  xmm0, xmmword ptr [rax]
0x1c004e65f  movups  xmmword ptr [rbx], xmm0
0x1c004e662  lea     rcx, [rbx+10h]; WorkItem
0x1c004e666  mov     [rbx+38h], rbx
0x1c004e66a  lea     rax, ?MspLazyWriterWorker@@YAXPEAX@Z; MspLazyWriterWorker(void *)
0x1c004e671  mov     [rcx+18h], rbx
0x1c004e675  mov     [rbx+30h], rax
0x1c004e679  xor     edx, edx; QueueType
0x1c004e67b  lea     rax, ?MspWorkerRoutine@@YAXPEAX@Z; MspWorkerRoutine(void *)
0x1c004e682  mov     qword ptr [rcx], 0
0x1c004e689  mov     [rcx+10h], rax
0x1c004e68d  call    cs:__imp_ExQueueWorkItem
0x1c004e694  nop     dword ptr [rax+rax+00h]
0x1c004e699  lea     rdx, [rsp+160h+LockHandle]; LockHandle
0x1c004e69e  xor     esi, esi
0x1c004e6a0  lea     rcx, ?LazyWriterSpinLock@@3_KA; SpinLock
0x1c004e6a7  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1c004e6ae  nop     dword ptr [rax+rax+00h]
0x1c004e6b3  mov     rax, [rsp+160h+var_F0]
0x1c004e6b8  lea     rcx, [rsp+160h+var_F0]
0x1c004e6bd  mov     rdi, [rsp+160h+var_E8]
0x1c004e6c2  cmp     [rax+8], rcx
0x1c004e6c6  jnz     loc_1C0086BFB
0x1c004e6cc  lea     rcx, [rsp+160h+var_F0]
0x1c004e6d1  cmp     [rdi], rcx
0x1c004e6d4  jnz     loc_1C0086BFB
0x1c004e6da  mov     [rdi], rax
0x1c004e6dd  mov     [rax+8], rdi
0x1c004e6e1  lea     rax, [rsp+160h+var_F0]
0x1c004e6e6  cmp     [rdi], rax
0x1c004e6e9  jz      loc_1C0086BDB
0x1c004e6ef  lea     rax, [rsp+160h+var_F0]
0x1c004e6f4  mov     [rsp+160h+var_E8], rax
0x1c004e6f9  lea     rax, [rsp+160h+var_F0]
0x1c004e6fe  mov     [rsp+160h+var_F0], rax
0x1c004e703  movzx   r12d, [rbp+60h+arg_8]
0x1c004e708  mov     r14, [rsp+160h+var_138]
0x1c004e70d  mov     rdi, [rdi]
0x1c004e710  lea     rax, ?DirtyTableList@@3U_LIST_ENTRY@@A; _LIST_ENTRY DirtyTableList
0x1c004e717  mov     rbx, [rsp+160h+var_130]
0x1c004e71c  mov     [rsp+160h+var_140], rdi
0x1c004e721  cmp     rdi, rax
0x1c004e724  jnz     loc_1C004E2F6
0x1c004e72a  test    r15b, r15b
0x1c004e72d  jnz     loc_1C0086BE7
0x1c004e733  lea     rcx, [rsp+160h+LockHandle]; LockHandle
  ... truncated ...
```
