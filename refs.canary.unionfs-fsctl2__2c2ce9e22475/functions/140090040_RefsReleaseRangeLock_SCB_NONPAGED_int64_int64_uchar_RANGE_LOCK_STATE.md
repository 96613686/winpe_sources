# RefsReleaseRangeLock(_SCB_NONPAGED *,__int64,__int64,uchar,_RANGE_LOCK_STATE *)

- ea: `0x140090040`
- end: `0x140090400`
- name: `?RefsReleaseRangeLock@@YAXPEAU_SCB_NONPAGED@@_J1EPEAU_RANGE_LOCK_STATE@@@Z`
- size: `960`
- prototype: `void __fastcall(struct _SCB_NONPAGED *, __int64, __int64, unsigned __int8, struct _RANGE_LOCK_STATE *)`
- caller_count: `15`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x140008fd0`
- `0x14003b3f0`
- `0x1400e51d8`
- `0x1400e5a80`
- `0x1400e6ec0`
- `0x1400e785c`
- `0x1400e96c0`
- `0x1400eb8f8`
- `0x1400ec8dc`
- `0x1400f7004`
- `0x14028aa64`
- `0x14028f01c`
- `0x140296eb0`
- `0x14029c098`
- `0x1402ac510`

## callees

- `0x14008c030`
- `0x140090040`
- `0x1400904c0`
- `0x140090570`
- `0x140096570`
- `0x1400a1730`
- `0x1400c8a6c`
- `0x1401e9a0c`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1401f9409`
- `ntoskrnl!KeSetEvent` at `0x1401f94ed`
- `ntoskrnl!KeSetEvent` at `0x1401f9409`
- `ntoskrnl!KeSetEvent` at `0x1401f94ed`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400903b1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400903e3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1401f938c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1401f946f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400903b1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400903e3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1401f938c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1401f946f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140090107`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400901fb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14009028b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140090314`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140090107`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400901fb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14009028b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140090314`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400902c3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14009034c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400902c3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14009034c`

## pseudocode

```c
void __fastcall RefsReleaseRangeLock(
        struct _SCB_NONPAGED *a1,
        __int64 a2,
        __int64 a3,
        char a4,
        struct _RANGE_LOCK_STATE *a5)
{
  __int64 v5; // rax
  int v7; // eax
  char v8; // dl
  KSPIN_LOCK *v9; // rbp
  struct _RANGE_LOCK_STATE *v10; // rbx
  __int64 v11; // rcx
  __int64 v12; // r14
  __int64 v13; // rsi
  _QWORD *v14; // rdx
  KSPIN_LOCK v15; // r14
  KSPIN_LOCK *v16; // r15
  __int64 v17; // r12
  __int64 v18; // rdx
  unsigned __int8 v19; // r9
  KSPIN_LOCK *v20; // rsi
  __int64 v21; // rbp
  __int64 v22; // r14
  _QWORD *v23; // rdx
  KSPIN_LOCK v24; // r15
  KSPIN_LOCK *v25; // rbp
  __int64 v26; // r12
  __int64 v27; // rdx
  unsigned __int8 v28; // r9
  _QWORD *v29; // rdx
  _QWORD *v30; // rcx
  _QWORD *v31; // r8
  _QWORD *k; // rcx
  _QWORD *v33; // rdx
  _QWORD *v34; // rcx
  _QWORD *v35; // r8
  _QWORD *i; // rcx
  unsigned __int64 m; // r9
  unsigned __int64 j; // r9
  bool v39; // zf
  __int64 v40; // rax
  char v41; // r10
  __int64 v42; // rax
  __int64 v43; // r8
  char v44; // al
  __int64 v45; // r8
  int v46; // eax
  __int64 v47; // rax
  char v48; // r10
  __int64 v49; // rax
  __int64 v50; // r8
  char v51; // al
  __int64 v52; // r8
  int inserted; // eax
  __int128 v54; // [rsp+20h] [rbp-68h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-58h] BYREF
  struct _KLOCK_QUEUE_HANDLE v56; // [rsp+48h] [rbp-40h] BYREF

  v5 = *((_QWORD *)a1 + 7);
  v54 = 0;
  if ( a4 )
  {
    v20 = (KSPIN_LOCK *)*((_QWORD *)a1 + 8);
    memset(&v56, 0, sizeof(v56));
    if ( !v20[2] )
      return;
    v10 = a5;
    v21 = ((a3 + a2 + *(unsigned int *)(v5 + 544)) >> *(_BYTE *)(v5 + 552) << *(_BYTE *)(v5 + 552)) - 1;
    v22 = a2 >> *(_BYTE *)(v5 + 552) << *(_BYTE *)(v5 + 552);
    *(_QWORD *)&v54 = v22;
    *((_QWORD *)&v54 + 1) = v21;
    if ( a5 && *((_QWORD *)a5 + 1) )
    {
      KeAcquireInStackQueuedSpinLock(v20, &v56);
      v23 = (_QWORD *)v20[2];
      *(_QWORD *)(*(_QWORD *)a5 + 8LL) &= ~*((_QWORD *)a5 + 1);
      if ( *(_QWORD **)a5 != v23 && !*(_QWORD *)(*(_QWORD *)a5 + 8LL) )
      {
        v35 = v23;
        for ( i = v23; i; i = (_QWORD *)*i )
        {
          if ( !i[1] && i != v23 )
          {
            *v35 = *i;
            ExFreeToNPagedLookasideList(&FsLibRangeLockIntLookasideList, i);
            break;
          }
          v35 = i;
        }
      }
    }
    else
    {
      KeAcquireInStackQueuedSpinLock(v20, &v56);
      v29 = (_QWORD *)v20[2];
      v30 = 0;
LABEL_28:
      if ( !v29 )
      {
        if ( v20[3] )
          FsLibPrivateCheckWaitingRangeLocks(v20, v20, &v54);
LABEL_31:
        KeReleaseInStackQueuedSpinLock(&v56);
        if ( !a5 )
          return;
LABEL_43:
        *((_QWORD *)v10 + 1) = 0;
        return;
      }
      for ( j = v29[1]; ; j &= ~(1LL << v48) )
      {
        v39 = !_BitScanForward64((unsigned __int64 *)&v47, j);
        if ( v39 )
        {
          v30 = v29;
          v29 = (_QWORD *)*v29;
          goto LABEL_28;
        }
        v48 = v47;
        v49 = 2 * v47;
        if ( v29[v49 + 2] == v22 && v29[v49 + 3] == v21 )
          break;
      }
      v50 = v29[1] & ~(1LL << v48);
      v29[1] = v50;
      if ( !v50 && v30 )
      {
        *v30 = *v29;
        *v29 = 0;
        ExFreeToNPagedLookasideList(&FsLibRangeLockIntLookasideList, v29);
      }
    }
    v24 = v20[3];
    if ( v24 )
    {
      v25 = v20 + 3;
      do
      {
        v26 = *(_QWORD *)(v24 + 40);
        if ( (unsigned __int8)AreRangeLocksOverlapping(&v54, v26)
          && ((v28 = *(_BYTE *)(v24 + 36), (v28 & 2) != 0)
           || v20[3] == v24
           || (unsigned __int8)FsLibPrivateCheckFirstWaitingRangeLockForAccess(v20, v27, v28))
          && ((v28 & 1) == 0
            ? (v51 = FsLibPrivateSearchArrayForRange(v20[2], v26))
            : (v51 = FsLibPrivateCheckForExclusiveRangeLockAccess(v20, v26)),
              v51) )
        {
          v52 = *(_QWORD *)(v24 + 48);
          if ( (*(_BYTE *)(v24 + 36) & 1) != 0 )
            inserted = FsLibPrivateInsertRangeLockExclusive(v20, v26, v52);
          else
            inserted = FsLibPrivateInsertRangeLockShared(v20, v26, v52);
          *(_DWORD *)(v24 + 32) = inserted;
          *v25 = *(_QWORD *)v24;
          if ( v24 == v20[4] )
            v20[4] = (KSPIN_LOCK)v25;
          KeSetEvent((PRKEVENT)(v24 + 8), 0, 0);
        }
        else
        {
          v25 = (KSPIN_LOCK *)v24;
        }
        v24 = *v25;
      }
      while ( *v25 );
    }
    goto LABEL_31;
  }
  v7 = *(_DWORD *)(v5 + 552);
  v8 = 14;
  v9 = (KSPIN_LOCK *)*((_QWORD *)a1 + 8);
  LockHandle.LockQueue = 0;
  if ( v7 == 12 )
    v8 = 12;
  *(_QWORD *)&LockHandle.OldIrql = 0;
  if ( v9[1] )
  {
    v10 = a5;
    v11 = 1 << v8;
    v12 = a2 & -v11;
    v13 = (-v11 & (a3 + v11 + a2 - 1)) - 1;
    *(_QWORD *)&v54 = v12;
    *((_QWORD *)&v54 + 1) = v13;
    if ( a5 && *((_QWORD *)a5 + 1) )
    {
      KeAcquireInStackQueuedSpinLock(v9, &LockHandle);
      v14 = (_QWORD *)v9[1];
      *(_QWORD *)(*(_QWORD *)a5 + 8LL) &= ~*((_QWORD *)a5 + 1);
      if ( *(_QWORD **)a5 != v14 && !*(_QWORD *)(*(_QWORD *)a5 + 8LL) )
      {
        v31 = v14;
        for ( k = v14; k; k = (_QWORD *)*k )
        {
          if ( !k[1] && k != v14 )
          {
            *v31 = *k;
            ExFreeToNPagedLookasideList(&FsLibRangeLockIntLookasideList, k);
            break;
          }
          v31 = k;
        }
      }
    }
    else
    {
      KeAcquireInStackQueuedSpinLock(v9, &LockHandle);
      v33 = (_QWORD *)v9[1];
      v34 = 0;
LABEL_39:
      if ( !v33 )
      {
        if ( v9[3] )
          FsLibPrivateCheckWaitingRangeLocks(v9, v9, &v54);
LABEL_42:
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        if ( !a5 )
          return;
        goto LABEL_43;
      }
      for ( m = v33[1]; ; m &= ~(1LL << v41) )
      {
        v39 = !_BitScanForward64((unsigned __int64 *)&v40, m);
        if ( v39 )
        {
          v34 = v33;
          v33 = (_QWORD *)*v33;
          goto LABEL_39;
        }
        v41 = v40;
        v42 = 2 * v40;
        if ( v33[v42 + 2] == v12 && v33[v42 + 3] == v13 )
          break;
      }
      v43 = v33[1] & ~(1LL << v41);
      v33[1] = v43;
      if ( !v43 && v34 )
      {
        *v34 = *v33;
        *v33 = 0;
        ExFreeToNPagedLookasideList(&FsLibRangeLockIntLookasideList, v33);
      }
    }
    v15 = v9[3];
    if ( v15 )
    {
      v16 = v9 + 3;
      do
      {
        v17 = *(_QWORD *)(v15 + 40);
        if ( (unsigned __int8)AreRangeLocksOverlapping(&v54, v17)
          && ((v19 = *(_BYTE *)(v15 + 36), (v19 & 2) != 0)
           || v9[3] == v15
           || (unsigned __int8)FsLibPrivateCheckFirstWaitingRangeLockForAccess(v9, v18, v19))
          && ((v19 & 1) == 0
            ? (v44 = FsLibPrivateSearchArrayForRange(v9[2], v17))
            : (v44 = FsLibPrivateCheckForExclusiveRangeLockAccess(v9, v17)),
              v44) )
        {
          v45 = *(_QWORD *)(v15 + 48);
          if ( (*(_BYTE *)(v15 + 36) & 1) != 0 )
            v46 = FsLibPrivateInsertRangeLockExclusive(v9, v17, v45);
          else
            v46 = FsLibPrivateInsertRangeLockShared(v9, v17, v45);
          *(_DWORD *)(v15 + 32) = v46;
          *v16 = *(_QWORD *)v15;
          if ( v15 == v9[4] )
            v9[4] = (KSPIN_LOCK)v16;
          KeSetEvent((PRKEVENT)(v15 + 8), 0, 0);
        }
        else
        {
          v16 = (KSPIN_LOCK *)v15;
        }
        v15 = *v16;
      }
      while ( *v16 );
    }
    goto LABEL_42;
  }
}

```

## disassembly

```asm
0x140090040  mov     [rsp+arg_0], rbx
0x140090045  mov     [rsp+arg_8], rbp
0x14009004a  push    rsi
0x14009004b  push    rdi
0x14009004c  push    r12
0x14009004e  push    r14
0x140090050  push    r15
0x140090052  sub     rsp, 60h
0x140090056  mov     rax, [rcx+38h]
0x14009005a  xorps   xmm0, xmm0
0x14009005d  mov     r10, rdx
0x140090060  movups  [rsp+88h+var_68], xmm0
0x140090065  test    r9b, r9b
0x140090068  jnz     loc_14009018F
0x14009006e  mov     eax, [rax+228h]
0x140090074  mov     edx, 0Eh
0x140090079  mov     rbp, [rcx+40h]
0x14009007d  cmp     eax, 0Ch
0x140090080  movups  xmmword ptr [rsp+88h+LockHandle.LockQueue.Next], xmm0
0x140090085  cmovz   dx, ax
0x140090089  xor     eax, eax
0x14009008b  mov     qword ptr [rsp+88h+LockHandle.OldIrql], rax
0x140090090  cmp     [rbp+8], rax
0x140090094  jnz     short loc_1400900B0
0x140090096  lea     r11, [rsp+88h+var_28]
0x14009009b  mov     rbx, [r11+30h]
0x14009009f  mov     rbp, [r11+38h]
0x1400900a3  mov     rsp, r11
0x1400900a6  pop     r15
0x1400900a8  pop     r14
0x1400900aa  pop     r12
0x1400900ac  pop     rdi
0x1400900ad  pop     rsi
0x1400900ae  retn
0x1400900b0  mov     rbx, [rsp+88h+arg_20]
0x1400900b8  lea     rsi, [r10-1]
0x1400900bc  movzx   ecx, dl
0x1400900bf  mov     eax, 1
0x1400900c4  shl     eax, cl
0x1400900c6  movsxd  rcx, eax
0x1400900c9  add     rsi, rcx
0x1400900cc  mov     rdx, rcx
0x1400900cf  neg     rdx
0x1400900d2  add     rsi, r8
0x1400900d5  and     rsi, rdx
0x1400900d8  mov     r14, rdx
0x1400900db  and     r14, r10
0x1400900de  dec     rsi
0x1400900e1  mov     qword ptr [rsp+88h+var_68], r14
0x1400900e6  mov     qword ptr [rsp+88h+var_68+8], rsi
0x1400900eb  test    rbx, rbx
0x1400900ee  jz      loc_14009030C
0x1400900f4  cmp     qword ptr [rbx+8], 0
0x1400900f9  jz      loc_14009030C
0x1400900ff  lea     rdx, [rsp+88h+LockHandle]; LockHandle
0x140090104  mov     rcx, rbp; SpinLock
0x140090107  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14009010e  nop     dword ptr [rax+rax+00h]
0x140090113  mov     rax, [rbx+8]
0x140090117  mov     rdx, [rbp+8]
0x14009011b  not     rax
0x14009011e  mov     rcx, [rbx]
0x140090121  and     [rcx+8], rax
0x140090125  mov     rax, [rbx]
0x140090128  cmp     rax, rdx
0x14009012b  jnz     loc_1400902DD
0x140090131  xor     edi, edi
0x140090133  mov     r14, [rbp+18h]
0x140090137  test    r14, r14
0x14009013a  jz      loc_140090347
0x140090140  lea     r15, [rbp+18h]
0x140090144  mov     r12, [r14+28h]
0x140090148  lea     rcx, [rsp+88h+var_68]
0x14009014d  mov     rdx, r12
0x140090150  call    AreRangeLocksOverlapping
0x140090155  test    al, al
0x140090157  jz      loc_1401F9417
0x14009015d  movzx   r9d, byte ptr [r14+24h]
0x140090162  test    r9b, 2
0x140090166  jnz     loc_1401F93AF
0x14009016c  cmp     [rbp+18h], r14
0x140090170  jz      loc_1401F93AF
0x140090176  movzx   r8d, r9b
0x14009017a  mov     rcx, rbp
0x14009017d  call    FsLibPrivateCheckFirstWaitingRangeLockForAccess
0x140090182  test    al, al
0x140090184  jnz     loc_1401F93AF
0x14009018a  jmp     loc_1401F9417
0x14009018f  mov     rsi, [rcx+40h]
0x140090193  xor     edx, edx
0x140090195  movups  xmmword ptr [rsp+88h+var_40.LockQueue.Next], xmm0
0x14009019a  mov     qword ptr [rsp+88h+var_40.OldIrql], rdx
0x14009019f  cmp     [rsi+10h], rdx
0x1400901a3  jz      loc_140090096
0x1400901a9  movsx   ecx, byte ptr [rax+228h]
0x1400901b0  mov     r14, r10
0x1400901b3  mov     ebp, [rax+220h]
0x1400901b9  mov     rbx, [rsp+88h+arg_20]
0x1400901c1  add     rbp, r10
0x1400901c4  add     rbp, r8
0x1400901c7  sar     r14, cl
0x1400901ca  sar     rbp, cl
0x1400901cd  shl     rbp, cl
0x1400901d0  dec     rbp
0x1400901d3  shl     r14, cl
0x1400901d6  mov     qword ptr [rsp+88h+var_68], r14
0x1400901db  mov     qword ptr [rsp+88h+var_68+8], rbp
0x1400901e0  test    rbx, rbx
0x1400901e3  jz      loc_140090283
0x1400901e9  cmp     [rbx+8], rdx
0x1400901ed  jz      loc_140090283
0x1400901f3  lea     rdx, [rsp+88h+var_40]; LockHandle
0x1400901f8  mov     rcx, rsi; SpinLock
0x1400901fb  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140090202  nop     dword ptr [rax+rax+00h]
0x140090207  mov     rax, [rbx+8]
0x14009020b  mov     rdx, [rsi+10h]
0x14009020f  not     rax
0x140090212  mov     rcx, [rbx]
0x140090215  and     [rcx+8], rax
0x140090219  mov     rax, [rbx]
0x14009021c  cmp     rax, rdx
0x14009021f  jnz     loc_14009036A
0x140090225  xor     edi, edi
0x140090227  mov     r15, [rsi+18h]
0x14009022b  test    r15, r15
0x14009022e  jz      loc_1400902BE
0x140090234  lea     rbp, [rsi+18h]
0x140090238  mov     r12, [r15+28h]
0x14009023c  lea     rcx, [rsp+88h+var_68]
0x140090241  mov     rdx, r12
0x140090244  call    AreRangeLocksOverlapping
0x140090249  test    al, al
0x14009024b  jz      loc_1401F94FB
0x140090251  movzx   r9d, byte ptr [r15+24h]
0x140090256  test    r9b, 2
0x14009025a  jnz     loc_1401F9492
0x140090260  cmp     [rsi+18h], r15
0x140090264  jz      loc_1401F9492
0x14009026a  movzx   r8d, r9b
0x14009026e  mov     rcx, rsi
0x140090271  call    FsLibPrivateCheckFirstWaitingRangeLockForAccess
0x140090276  test    al, al
0x140090278  jnz     loc_1401F9492
0x14009027e  jmp     loc_1401F94FB
0x140090283  lea     rdx, [rsp+88h+var_40]; LockHandle
0x140090288  mov     rcx, rsi; SpinLock
0x14009028b  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140090292  nop     dword ptr [rax+rax+00h]
0x140090297  mov     rdx, [rsi+10h]; Entry
0x14009029b  xor     edi, edi
0x14009029d  mov     ecx, edi
0x14009029f  test    rdx, rdx
0x1400902a2  jnz     loc_1400903F4
0x1400902a8  cmp     [rsi+18h], rdi
0x1400902ac  jz      short loc_1400902BE
0x1400902ae  lea     r8, [rsp+88h+var_68]
0x1400902b3  mov     rdx, rsi
0x1400902b6  mov     rcx, rsi
0x1400902b9  call    FsLibPrivateCheckWaitingRangeLocks
0x1400902be  lea     rcx, [rsp+88h+var_40]; LockHandle
0x1400902c3  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400902ca  nop     dword ptr [rax+rax+00h]
0x1400902cf  test    rbx, rbx
0x1400902d2  jnz     loc_140090361
0x1400902d8  jmp     loc_140090096
0x1400902dd  cmp     qword ptr [rax+8], 0
0x1400902e2  jnz     loc_140090131
0x1400902e8  mov     r8, rdx
0x1400902eb  mov     rcx, rdx
0x1400902ee  xchg    ax, ax
0x1400902f0  test    rcx, rcx
0x1400902f3  jz      loc_140090131
0x1400902f9  cmp     qword ptr [rcx+8], 0
0x1400902fe  jz      loc_140090398
0x140090304  mov     r8, rcx
0x140090307  mov     rcx, [rcx]
0x14009030a  jmp     short loc_1400902F0
0x14009030c  lea     rdx, [rsp+88h+LockHandle]; LockHandle
0x140090311  mov     rcx, rbp; SpinLock
0x140090314  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14009031b  nop     dword ptr [rax+rax+00h]
0x140090320  mov     rdx, [rbp+8]; Entry
0x140090324  xor     edi, edi
0x140090326  mov     ecx, edi
0x140090328  test    rdx, rdx
0x14009032b  jnz     loc_1400903C2
0x140090331  cmp     [rbp+18h], rdi
0x140090335  jz      short loc_140090347
0x140090337  lea     r8, [rsp+88h+var_68]
0x14009033c  mov     rdx, rbp
0x14009033f  mov     rcx, rbp
0x140090342  call    FsLibPrivateCheckWaitingRangeLocks
0x140090347  lea     rcx, [rsp+88h+LockHandle]; LockHandle
0x14009034c  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140090353  nop     dword ptr [rax+rax+00h]
0x140090358  test    rbx, rbx
0x14009035b  jz      loc_140090096
0x140090361  mov     [rbx+8], rdi
0x140090365  jmp     loc_140090096
0x14009036a  cmp     qword ptr [rax+8], 0
0x14009036f  jnz     loc_140090225
0x140090375  mov     r8, rdx
0x140090378  mov     rcx, rdx
0x14009037b  nop     dword ptr [rax+rax+00h]
0x140090380  test    rcx, rcx
0x140090383  jz      loc_140090225
0x140090389  cmp     qword ptr [rcx+8], 0
0x14009038e  jz      short loc_1400903CE
0x140090390  mov     r8, rcx
0x140090393  mov     rcx, [rcx]
0x140090396  jmp     short loc_140090380
0x140090398  cmp     rcx, rdx
0x14009039b  jz      loc_140090304
0x1400903a1  mov     rax, [rcx]
0x1400903a4  mov     rdx, rcx; Entry
0x1400903a7  lea     rcx, FsLibRangeLockIntLookasideList; Lookaside
0x1400903ae  mov     [r8], rax
0x1400903b1  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400903b8  nop     dword ptr [rax+rax+00h]
0x1400903bd  jmp     loc_140090131
0x1400903c2  mov     r8, [rdx+8]
0x1400903c6  mov     r9, r8
0x1400903c9  jmp     loc_1401F9348
0x1400903ce  cmp     rcx, rdx
0x1400903d1  jz      short loc_140090390
0x1400903d3  mov     rax, [rcx]
0x1400903d6  mov     rdx, rcx; Entry
0x1400903d9  lea     rcx, FsLibRangeLockIntLookasideList; Lookaside
0x1400903e0  mov     [r8], rax
0x1400903e3  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400903ea  nop     dword ptr [rax+rax+00h]
0x1400903ef  jmp     loc_140090225
0x1400903f4  mov     r8, [rdx+8]
0x1400903f8  mov     r9, r8
0x1400903fb  jmp     loc_1401F942B
0x1401f9348  bsf     rax, r9
0x1401f934c  jz      short loc_1401F93A4
0x1401f934e  mov     r10d, eax
0x1401f9351  add     rax, rax
0x1401f9354  cmp     [rdx+rax*8+10h], r14
0x1401f9359  jnz     short loc_1401F939E
0x1401f935b  cmp     [rdx+rax*8+18h], rsi
0x1401f9360  jnz     short loc_1401F939E
0x1401f9362  btr     r8, r10
0x1401f9366  mov     [rdx+8], r8
0x1401f936a  test    r8, r8
0x1401f936d  jnz     loc_140090133
0x1401f9373  test    rcx, rcx
0x1401f9376  jz      loc_140090133
0x1401f937c  mov     rax, [rdx]
0x1401f937f  mov     [rcx], rax
0x1401f9382  lea     rcx, FsLibRangeLockIntLookasideList; Lookaside
0x1401f9389  mov     [rdx], rdi
0x1401f938c  call    cs:__imp_ExFreeToNPagedLookasideList
0x1401f9393  nop     dword ptr [rax+rax+00h]
0x1401f9398  nop
0x1401f9399  jmp     loc_140090133
0x1401f939e  btr     r9, r10
0x1401f93a2  jmp     short loc_1401F9348
0x1401f93a4  mov     rcx, rdx
0x1401f93a7  mov     rdx, [rdx]
0x1401f93aa  jmp     loc_140090328
0x1401f93af  mov     rdx, r12
0x1401f93b2  test    r9b, 1
0x1401f93b6  jz      short loc_1401F93C2
0x1401f93b8  mov     rcx, rbp
0x1401f93bb  call    FsLibPrivateCheckForExclusiveRangeLockAccess
0x1401f93c0  jmp     short loc_1401F93CB
0x1401f93c2  mov     rcx, [rbp+10h]
0x1401f93c6  call    FsLibPrivateSearchArrayForRange
0x1401f93cb  test    al, al
0x1401f93cd  jz      short loc_1401F9417
0x1401f93cf  test    byte ptr [r14+24h], 1
0x1401f93d4  mov     rdx, r12
0x1401f93d7  mov     r8, [r14+30h]
0x1401f93db  mov     rcx, rbp
0x1401f93de  jz      short loc_1401F93E7
0x1401f93e0  call    FsLibPrivateInsertRangeLockExclusive
0x1401f93e5  jmp     short loc_1401F93EC
0x1401f93e7  call    FsLibPrivateInsertRangeLockShared
0x1401f93ec  mov     [r14+20h], eax
0x1401f93f0  mov     rax, [r14]
0x1401f93f3  mov     [r15], rax
0x1401f93f6  cmp     r14, [rbp+20h]
0x1401f93fa  jnz     short loc_1401F9400
0x1401f93fc  mov     [rbp+20h], r15
0x1401f9400  lea     rcx, [r14+8]; Event
0x1401f9404  xor     r8d, r8d; Wait
0x1401f9407  xor     edx, edx; Increment
0x1401f9409  call    cs:__imp_KeSetEvent
0x1401f9410  nop     dword ptr [rax+rax+00h]
0x1401f9415  jmp     short loc_1401F941A
0x1401f9417  mov     r15, r14
0x1401f941a  mov     r14, [r15]
0x1401f941d  test    r14, r14
0x1401f9420  jnz     loc_140090144
0x1401f9426  jmp     loc_140090347
0x1401f942b  bsf     rax, r9
0x1401f942f  jz      short loc_1401F9487
  ... truncated ...
```
