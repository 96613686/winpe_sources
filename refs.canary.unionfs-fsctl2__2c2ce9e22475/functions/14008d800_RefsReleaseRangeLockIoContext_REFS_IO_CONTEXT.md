# RefsReleaseRangeLockIoContext(REFS_IO_CONTEXT *)

- ea: `0x14008d800`
- end: `0x14008dbc1`
- name: `?RefsReleaseRangeLockIoContext@@YAXPEAUREFS_IO_CONTEXT@@@Z`
- size: `961`
- prototype: `void __fastcall(struct REFS_IO_CONTEXT *)`
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x1400b9250`
- `0x1400b97a0`
- `0x1400e4df8`
- `0x14033b8d0`

## callees

- `0x14008c030`
- `0x14008d800`
- `0x1400904c0`
- `0x140090570`
- `0x140096570`
- `0x1400a1730`
- `0x1400c8a6c`
- `0x1401e9a0c`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1401f90c7`
- `ntoskrnl!KeSetEvent` at `0x1401f91ac`
- `ntoskrnl!KeSetEvent` at `0x1401f90c7`
- `ntoskrnl!KeSetEvent` at `0x1401f91ac`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008db72`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008dba4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1401f904a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1401f912e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008db72`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008dba4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1401f904a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1401f912e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14008d8d5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14008d9c3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14008da53`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14008dada`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14008d8d5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14008d9c3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14008da53`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14008dada`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14008da8b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14008db12`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14008da8b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14008db12`

## pseudocode

```c
void __fastcall RefsReleaseRangeLockIoContext(struct REFS_IO_CONTEXT *a1)
{
  bool v1; // zf
  _QWORD *v2; // rdi
  __int64 v3; // rdx
  __int64 v4; // r9
  __int64 v6; // r8
  __int64 v7; // rax
  int v8; // eax
  char v9; // cl
  KSPIN_LOCK *v10; // r14
  __int64 v11; // rcx
  __int64 v12; // r15
  __int64 v13; // rbp
  _QWORD *v14; // rdx
  KSPIN_LOCK v15; // rbp
  KSPIN_LOCK *v16; // r12
  __int64 v17; // r13
  __int64 v18; // rdx
  unsigned __int8 v19; // r9
  KSPIN_LOCK *v20; // rbp
  __int64 v21; // r15
  __int64 v22; // r14
  _QWORD *v23; // rdx
  KSPIN_LOCK v24; // r15
  KSPIN_LOCK *v25; // r12
  __int64 v26; // r13
  __int64 v27; // rdx
  unsigned __int8 v28; // r9
  _QWORD *v29; // rdx
  _QWORD *v30; // rcx
  _QWORD *v31; // r8
  _QWORD *k; // rcx
  _QWORD *v33; // rdx
  _QWORD *v34; // rcx
  _QWORD *v35; // r8
  _QWORD *j; // rcx
  unsigned __int64 m; // r9
  unsigned __int64 i; // r9
  __int64 v39; // rax
  char v40; // r10
  __int64 v41; // rax
  __int64 v42; // r8
  char v43; // al
  __int64 v44; // r8
  int v45; // eax
  __int64 v46; // rax
  char v47; // r10
  __int64 v48; // rax
  __int64 v49; // r8
  char v50; // al
  __int64 v51; // r8
  int inserted; // eax
  __int128 v53; // [rsp+20h] [rbp-88h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-78h] BYREF
  struct _KLOCK_QUEUE_HANDLE v55; // [rsp+48h] [rbp-60h] BYREF

  v1 = *((_BYTE *)a1 + 836) == 0;
  v2 = (_QWORD *)((char *)a1 + 32);
  v3 = *((_QWORD *)a1 + 102);
  v4 = *((unsigned int *)a1 + 208);
  v6 = *((_QWORD *)a1 + 103);
  v53 = 0;
  v7 = *(_QWORD *)(v3 + 56);
  if ( !v1 )
  {
    v20 = *(KSPIN_LOCK **)(v3 + 64);
    memset(&v55, 0, sizeof(v55));
    if ( !v20[2] )
      goto LABEL_5;
    v21 = v6 >> *(_BYTE *)(v7 + 552) << *(_BYTE *)(v7 + 552);
    v22 = ((v4 + v6 + *(unsigned int *)(v7 + 544)) >> *(_BYTE *)(v7 + 552) << *(_BYTE *)(v7 + 552)) - 1;
    *(_QWORD *)&v53 = v21;
    *((_QWORD *)&v53 + 1) = v22;
    if ( a1 == (struct REFS_IO_CONTEXT *)-32LL || !*((_QWORD *)a1 + 5) )
    {
      KeAcquireInStackQueuedSpinLock(v20, &v55);
      v29 = (_QWORD *)v20[2];
      v30 = 0;
LABEL_28:
      if ( !v29 )
      {
        if ( v20[3] )
          FsLibPrivateCheckWaitingRangeLocks(v20, v20, &v53);
LABEL_31:
        KeReleaseInStackQueuedSpinLock(&v55);
        if ( !v2 )
          goto LABEL_5;
        goto LABEL_43;
      }
      for ( i = v29[1]; ; i &= ~(1LL << v47) )
      {
        v1 = !_BitScanForward64((unsigned __int64 *)&v46, i);
        if ( v1 )
        {
          v30 = v29;
          v29 = (_QWORD *)*v29;
          goto LABEL_28;
        }
        v47 = v46;
        v48 = 2 * v46;
        if ( v29[v48 + 2] == v21 && v29[v48 + 3] == v22 )
          break;
      }
      v49 = v29[1] & ~(1LL << v47);
      v29[1] = v49;
      if ( !v49 && v30 )
      {
        *v30 = *v29;
        *v29 = 0;
        ExFreeToNPagedLookasideList(&FsLibRangeLockIntLookasideList, v29);
      }
    }
    else
    {
      KeAcquireInStackQueuedSpinLock(v20, &v55);
      v23 = (_QWORD *)v20[2];
      *(_QWORD *)(*v2 + 8LL) &= ~v2[1];
      if ( (_QWORD *)*v2 != v23 && !*(_QWORD *)(*v2 + 8LL) )
      {
        v35 = v23;
        for ( j = v23; j; j = (_QWORD *)*j )
        {
          if ( !j[1] && j != v23 )
          {
            *v35 = *j;
            ExFreeToNPagedLookasideList(&FsLibRangeLockIntLookasideList, j);
            break;
          }
          v35 = j;
        }
      }
    }
    v24 = v20[3];
    if ( v24 )
    {
      v25 = v20 + 3;
      do
      {
        v26 = *(_QWORD *)(v24 + 40);
        if ( (unsigned __int8)AreRangeLocksOverlapping(&v53, v26)
          && ((v28 = *(_BYTE *)(v24 + 36), (v28 & 2) != 0)
           || v20[3] == v24
           || (unsigned __int8)FsLibPrivateCheckFirstWaitingRangeLockForAccess(v20, v27, v28))
          && ((v28 & 1) == 0
            ? (v50 = FsLibPrivateSearchArrayForRange(v20[2], v26))
            : (v50 = FsLibPrivateCheckForExclusiveRangeLockAccess(v20, v26)),
              v50) )
        {
          v51 = *(_QWORD *)(v24 + 48);
          if ( (*(_BYTE *)(v24 + 36) & 1) != 0 )
            inserted = FsLibPrivateInsertRangeLockExclusive(v20, v26, v51);
          else
            inserted = FsLibPrivateInsertRangeLockShared(v20, v26, v51);
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
  v8 = *(_DWORD *)(v7 + 552);
  v9 = 14;
  v10 = *(KSPIN_LOCK **)(v3 + 64);
  LockHandle.LockQueue = 0;
  if ( v8 == 12 )
    v9 = 12;
  *(_QWORD *)&LockHandle.OldIrql = 0;
  if ( v10[1] )
  {
    v11 = 1 << v9;
    v12 = v6 & -v11;
    v13 = (-v11 & (v4 + v11 + v6 - 1)) - 1;
    *(_QWORD *)&v53 = v12;
    *((_QWORD *)&v53 + 1) = v13;
    if ( v2 && v2[1] )
    {
      KeAcquireInStackQueuedSpinLock(v10, &LockHandle);
      v14 = (_QWORD *)v10[1];
      *(_QWORD *)(*v2 + 8LL) &= ~v2[1];
      if ( (_QWORD *)*v2 != v14 && !*(_QWORD *)(*v2 + 8LL) )
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
      KeAcquireInStackQueuedSpinLock(v10, &LockHandle);
      v33 = (_QWORD *)v10[1];
      v34 = 0;
LABEL_39:
      if ( !v33 )
      {
        if ( v10[3] )
          FsLibPrivateCheckWaitingRangeLocks(v10, v10, &v53);
LABEL_42:
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        if ( !v2 )
          goto LABEL_5;
LABEL_43:
        v2[1] = 0;
        goto LABEL_5;
      }
      for ( m = v33[1]; ; m &= ~(1LL << v40) )
      {
        v1 = !_BitScanForward64((unsigned __int64 *)&v39, m);
        if ( v1 )
        {
          v34 = v33;
          v33 = (_QWORD *)*v33;
          goto LABEL_39;
        }
        v40 = v39;
        v41 = 2 * v39;
        if ( v33[v41 + 2] == v12 && v33[v41 + 3] == v13 )
          break;
      }
      v42 = v33[1] & ~(1LL << v40);
      v33[1] = v42;
      if ( !v42 && v34 )
      {
        *v34 = *v33;
        *v33 = 0;
        ExFreeToNPagedLookasideList(&FsLibRangeLockIntLookasideList, v33);
      }
    }
    v15 = v10[3];
    if ( v15 )
    {
      v16 = v10 + 3;
      do
      {
        v17 = *(_QWORD *)(v15 + 40);
        if ( (unsigned __int8)AreRangeLocksOverlapping(&v53, v17)
          && ((v19 = *(_BYTE *)(v15 + 36), (v19 & 2) != 0)
           || v10[3] == v15
           || (unsigned __int8)FsLibPrivateCheckFirstWaitingRangeLockForAccess(v10, v18, v19))
          && ((v19 & 1) == 0
            ? (v43 = FsLibPrivateSearchArrayForRange(v10[2], v17))
            : (v43 = FsLibPrivateCheckForExclusiveRangeLockAccess(v10, v17)),
              v43) )
        {
          v44 = *(_QWORD *)(v15 + 48);
          if ( (*(_BYTE *)(v15 + 36) & 1) != 0 )
            v45 = FsLibPrivateInsertRangeLockExclusive(v10, v17, v44);
          else
            v45 = FsLibPrivateInsertRangeLockShared(v10, v17, v44);
          *(_DWORD *)(v15 + 32) = v45;
          *v16 = *(_QWORD *)v15;
          if ( v15 == v10[4] )
            v10[4] = (KSPIN_LOCK)v16;
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
LABEL_5:
  *((_QWORD *)a1 + 102) = 0;
}

```

## disassembly

```asm
0x14008d800  push    rbx
0x14008d802  push    rbp
0x14008d803  push    rsi
0x14008d804  push    rdi
0x14008d805  push    r12
0x14008d807  push    r13
0x14008d809  push    r14
0x14008d80b  push    r15
0x14008d80d  sub     rsp, 68h
0x14008d811  cmp     byte ptr [rcx+344h], 0
0x14008d818  lea     rdi, [rcx+20h]
0x14008d81c  mov     rdx, [rcx+330h]
0x14008d823  xorps   xmm0, xmm0
0x14008d826  mov     r9d, [rcx+340h]
0x14008d82d  mov     rbx, rcx
0x14008d830  mov     r8, [rcx+338h]
0x14008d837  movups  [rsp+0A8h+var_88], xmm0
0x14008d83c  mov     rax, [rdx+38h]
0x14008d840  jnz     loc_14008D95D
0x14008d846  mov     eax, [rax+228h]
0x14008d84c  mov     ecx, 0Eh
0x14008d851  mov     r14, [rdx+40h]
0x14008d855  cmp     eax, 0Ch
0x14008d858  movups  xmmword ptr [rsp+0A8h+LockHandle.LockQueue.Next], xmm0
0x14008d85d  cmovz   cx, ax
0x14008d861  xor     eax, eax
0x14008d863  mov     qword ptr [rsp+0A8h+LockHandle.OldIrql], rax
0x14008d868  cmp     [r14+8], rax
0x14008d86c  jnz     short loc_14008D889
0x14008d86e  xor     esi, esi
0x14008d870  mov     [rbx+330h], rsi
0x14008d877  add     rsp, 68h
0x14008d87b  pop     r15
0x14008d87d  pop     r14
0x14008d87f  pop     r13
0x14008d881  pop     r12
0x14008d883  pop     rdi
0x14008d884  pop     rsi
0x14008d885  pop     rbp
0x14008d886  pop     rbx
0x14008d887  retn
0x14008d889  mov     eax, 1
0x14008d88e  lea     rbp, [r8-1]
0x14008d892  shl     eax, cl
0x14008d894  movsxd  rcx, eax
0x14008d897  add     rbp, rcx
0x14008d89a  mov     rdx, rcx
0x14008d89d  neg     rdx
0x14008d8a0  add     rbp, r9
0x14008d8a3  and     rbp, rdx
0x14008d8a6  mov     r15, rdx
0x14008d8a9  and     r15, r8
0x14008d8ac  dec     rbp
0x14008d8af  mov     qword ptr [rsp+0A8h+var_88], r15
0x14008d8b4  mov     qword ptr [rsp+0A8h+var_88+8], rbp
0x14008d8b9  test    rdi, rdi
0x14008d8bc  jz      loc_14008DAD2
0x14008d8c2  cmp     qword ptr [rdi+8], 0
0x14008d8c7  jz      loc_14008DAD2
0x14008d8cd  lea     rdx, [rsp+0A8h+LockHandle]; LockHandle
0x14008d8d2  mov     rcx, r14; SpinLock
0x14008d8d5  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14008d8dc  nop     dword ptr [rax+rax+00h]
0x14008d8e1  mov     rax, [rdi+8]
0x14008d8e5  mov     rdx, [r14+8]
0x14008d8e9  not     rax
0x14008d8ec  mov     rcx, [rdi]
0x14008d8ef  and     [rcx+8], rax
0x14008d8f3  mov     rax, [rdi]
0x14008d8f6  cmp     rax, rdx
0x14008d8f9  jnz     loc_14008DAA5
0x14008d8ff  xor     esi, esi
0x14008d901  mov     rbp, [r14+18h]
0x14008d905  test    rbp, rbp
0x14008d908  jz      loc_14008DB0D
0x14008d90e  lea     r12, [r14+18h]
0x14008d912  mov     r13, [rbp+28h]
0x14008d916  lea     rcx, [rsp+0A8h+var_88]
0x14008d91b  mov     rdx, r13
0x14008d91e  call    AreRangeLocksOverlapping
0x14008d923  test    al, al
0x14008d925  jz      loc_1401F90D5
0x14008d92b  movzx   r9d, byte ptr [rbp+24h]
0x14008d930  test    r9b, 2
0x14008d934  jnz     loc_1401F906D
0x14008d93a  cmp     [r14+18h], rbp
0x14008d93e  jz      loc_1401F906D
0x14008d944  movzx   r8d, r9b
0x14008d948  mov     rcx, r14
0x14008d94b  call    FsLibPrivateCheckFirstWaitingRangeLockForAccess
0x14008d950  test    al, al
0x14008d952  jnz     loc_1401F906D
0x14008d958  jmp     loc_1401F90D5
0x14008d95d  mov     rbp, [rdx+40h]
0x14008d961  xor     ecx, ecx
0x14008d963  movups  xmmword ptr [rsp+0A8h+var_60.LockQueue.Next], xmm0
0x14008d968  mov     qword ptr [rsp+0A8h+var_60.OldIrql], rcx
0x14008d96d  cmp     [rbp+10h], rcx
0x14008d971  jz      loc_14008D86E
0x14008d977  movsx   ecx, byte ptr [rax+228h]
0x14008d97e  mov     r15, r8
0x14008d981  mov     r14d, [rax+220h]
0x14008d988  add     r14, r8
0x14008d98b  sar     r15, cl
0x14008d98e  add     r14, r9
0x14008d991  shl     r15, cl
0x14008d994  sar     r14, cl
0x14008d997  shl     r14, cl
0x14008d99a  dec     r14
0x14008d99d  mov     qword ptr [rsp+0A8h+var_88], r15
0x14008d9a2  mov     qword ptr [rsp+0A8h+var_88+8], r14
0x14008d9a7  test    rdi, rdi
0x14008d9aa  jz      loc_14008DA4B
0x14008d9b0  cmp     qword ptr [rdi+8], 0
0x14008d9b5  jz      loc_14008DA4B
0x14008d9bb  lea     rdx, [rsp+0A8h+var_60]; LockHandle
0x14008d9c0  mov     rcx, rbp; SpinLock
0x14008d9c3  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14008d9ca  nop     dword ptr [rax+rax+00h]
0x14008d9cf  mov     rax, [rdi+8]
0x14008d9d3  mov     rdx, [rbp+10h]
0x14008d9d7  not     rax
0x14008d9da  mov     rcx, [rdi]
0x14008d9dd  and     [rcx+8], rax
0x14008d9e1  mov     rax, [rdi]
0x14008d9e4  cmp     rax, rdx
0x14008d9e7  jnz     loc_14008DB30
0x14008d9ed  xor     esi, esi
0x14008d9ef  mov     r15, [rbp+18h]
0x14008d9f3  test    r15, r15
0x14008d9f6  jz      loc_14008DA86
0x14008d9fc  lea     r12, [rbp+18h]
0x14008da00  mov     r13, [r15+28h]
0x14008da04  lea     rcx, [rsp+0A8h+var_88]
0x14008da09  mov     rdx, r13
0x14008da0c  call    AreRangeLocksOverlapping
0x14008da11  test    al, al
0x14008da13  jz      loc_1401F91BA
0x14008da19  movzx   r9d, byte ptr [r15+24h]
0x14008da1e  test    r9b, 2
0x14008da22  jnz     loc_1401F9151
0x14008da28  cmp     [rbp+18h], r15
0x14008da2c  jz      loc_1401F9151
0x14008da32  movzx   r8d, r9b
0x14008da36  mov     rcx, rbp
0x14008da39  call    FsLibPrivateCheckFirstWaitingRangeLockForAccess
0x14008da3e  test    al, al
0x14008da40  jnz     loc_1401F9151
0x14008da46  jmp     loc_1401F91BA
0x14008da4b  lea     rdx, [rsp+0A8h+var_60]; LockHandle
0x14008da50  mov     rcx, rbp; SpinLock
0x14008da53  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14008da5a  nop     dword ptr [rax+rax+00h]
0x14008da5f  mov     rdx, [rbp+10h]; Entry
0x14008da63  xor     esi, esi
0x14008da65  mov     ecx, esi
0x14008da67  test    rdx, rdx
0x14008da6a  jnz     loc_14008DBB5
0x14008da70  cmp     [rbp+18h], rsi
0x14008da74  jz      short loc_14008DA86
0x14008da76  lea     r8, [rsp+0A8h+var_88]
0x14008da7b  mov     rdx, rbp
0x14008da7e  mov     rcx, rbp
0x14008da81  call    FsLibPrivateCheckWaitingRangeLocks
0x14008da86  lea     rcx, [rsp+0A8h+var_60]; LockHandle
0x14008da8b  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14008da92  nop     dword ptr [rax+rax+00h]
0x14008da97  test    rdi, rdi
0x14008da9a  jnz     loc_14008DB27
0x14008daa0  jmp     loc_14008D870
0x14008daa5  cmp     qword ptr [rax+8], 0
0x14008daaa  jnz     loc_14008D8FF
0x14008dab0  mov     r8, rdx
0x14008dab3  mov     rcx, rdx
0x14008dab6  test    rcx, rcx
0x14008dab9  jz      loc_14008D8FF
0x14008dabf  cmp     qword ptr [rcx+8], 0
0x14008dac4  jz      loc_14008DB59
0x14008daca  mov     r8, rcx
0x14008dacd  mov     rcx, [rcx]
0x14008dad0  jmp     short loc_14008DAB6
0x14008dad2  lea     rdx, [rsp+0A8h+LockHandle]; LockHandle
0x14008dad7  mov     rcx, r14; SpinLock
0x14008dada  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14008dae1  nop     dword ptr [rax+rax+00h]
0x14008dae6  mov     rdx, [r14+8]; Entry
0x14008daea  xor     esi, esi
0x14008daec  mov     ecx, esi
0x14008daee  test    rdx, rdx
0x14008daf1  jnz     loc_14008DB83
0x14008daf7  cmp     [r14+18h], rsi
0x14008dafb  jz      short loc_14008DB0D
0x14008dafd  lea     r8, [rsp+0A8h+var_88]
0x14008db02  mov     rdx, r14
0x14008db05  mov     rcx, r14
0x14008db08  call    FsLibPrivateCheckWaitingRangeLocks
0x14008db0d  lea     rcx, [rsp+0A8h+LockHandle]; LockHandle
0x14008db12  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14008db19  nop     dword ptr [rax+rax+00h]
0x14008db1e  test    rdi, rdi
0x14008db21  jz      loc_14008D870
0x14008db27  mov     [rdi+8], rsi
0x14008db2b  jmp     loc_14008D870
0x14008db30  cmp     qword ptr [rax+8], 0
0x14008db35  jnz     loc_14008D9ED
0x14008db3b  mov     r8, rdx
0x14008db3e  mov     rcx, rdx
0x14008db41  test    rcx, rcx
0x14008db44  jz      loc_14008D9ED
0x14008db4a  cmp     qword ptr [rcx+8], 0
0x14008db4f  jz      short loc_14008DB8F
0x14008db51  mov     r8, rcx
0x14008db54  mov     rcx, [rcx]
0x14008db57  jmp     short loc_14008DB41
0x14008db59  cmp     rcx, rdx
0x14008db5c  jz      loc_14008DACA
0x14008db62  mov     rax, [rcx]
0x14008db65  mov     rdx, rcx; Entry
0x14008db68  lea     rcx, FsLibRangeLockIntLookasideList; Lookaside
0x14008db6f  mov     [r8], rax
0x14008db72  call    cs:__imp_ExFreeToNPagedLookasideList
0x14008db79  nop     dword ptr [rax+rax+00h]
0x14008db7e  jmp     loc_14008D8FF
0x14008db83  mov     r8, [rdx+8]
0x14008db87  mov     r9, r8
0x14008db8a  jmp     loc_1401F9006
0x14008db8f  cmp     rcx, rdx
0x14008db92  jz      short loc_14008DB51
0x14008db94  mov     rax, [rcx]
0x14008db97  mov     rdx, rcx; Entry
0x14008db9a  lea     rcx, FsLibRangeLockIntLookasideList; Lookaside
0x14008dba1  mov     [r8], rax
0x14008dba4  call    cs:__imp_ExFreeToNPagedLookasideList
0x14008dbab  nop     dword ptr [rax+rax+00h]
0x14008dbb0  jmp     loc_14008D9ED
0x14008dbb5  mov     r8, [rdx+8]
0x14008dbb9  mov     r9, r8
0x14008dbbc  jmp     loc_1401F90EA
0x1401f9006  bsf     rax, r9
0x1401f900a  jz      short loc_1401F9062
0x1401f900c  mov     r10d, eax
0x1401f900f  add     rax, rax
0x1401f9012  cmp     [rdx+rax*8+10h], r15
0x1401f9017  jnz     short loc_1401F905C
0x1401f9019  cmp     [rdx+rax*8+18h], rbp
0x1401f901e  jnz     short loc_1401F905C
0x1401f9020  btr     r8, r10
0x1401f9024  mov     [rdx+8], r8
0x1401f9028  test    r8, r8
0x1401f902b  jnz     loc_14008D901
0x1401f9031  test    rcx, rcx
0x1401f9034  jz      loc_14008D901
0x1401f903a  mov     rax, [rdx]
0x1401f903d  mov     [rcx], rax
0x1401f9040  lea     rcx, FsLibRangeLockIntLookasideList; Lookaside
0x1401f9047  mov     [rdx], rsi
0x1401f904a  call    cs:__imp_ExFreeToNPagedLookasideList
0x1401f9051  nop     dword ptr [rax+rax+00h]
0x1401f9056  nop
0x1401f9057  jmp     loc_14008D901
0x1401f905c  btr     r9, r10
0x1401f9060  jmp     short loc_1401F9006
0x1401f9062  mov     rcx, rdx
0x1401f9065  mov     rdx, [rdx]
0x1401f9068  jmp     loc_14008DAEE
0x1401f906d  mov     rdx, r13
0x1401f9070  test    r9b, 1
0x1401f9074  jz      short loc_1401F9080
0x1401f9076  mov     rcx, r14
0x1401f9079  call    FsLibPrivateCheckForExclusiveRangeLockAccess
0x1401f907e  jmp     short loc_1401F9089
0x1401f9080  mov     rcx, [r14+10h]
0x1401f9084  call    FsLibPrivateSearchArrayForRange
0x1401f9089  test    al, al
0x1401f908b  jz      short loc_1401F90D5
0x1401f908d  test    byte ptr [rbp+24h], 1
0x1401f9091  mov     rdx, r13
0x1401f9094  mov     r8, [rbp+30h]
0x1401f9098  mov     rcx, r14
0x1401f909b  jz      short loc_1401F90A4
0x1401f909d  call    FsLibPrivateInsertRangeLockExclusive
0x1401f90a2  jmp     short loc_1401F90A9
0x1401f90a4  call    FsLibPrivateInsertRangeLockShared
0x1401f90a9  mov     [rbp+20h], eax
0x1401f90ac  mov     rax, [rbp+0]
0x1401f90b0  mov     [r12], rax
0x1401f90b4  cmp     rbp, [r14+20h]
0x1401f90b8  jnz     short loc_1401F90BE
0x1401f90ba  mov     [r14+20h], r12
0x1401f90be  lea     rcx, [rbp+8]; Event
0x1401f90c2  xor     r8d, r8d; Wait
0x1401f90c5  xor     edx, edx; Increment
0x1401f90c7  call    cs:__imp_KeSetEvent
0x1401f90ce  nop     dword ptr [rax+rax+00h]
0x1401f90d3  jmp     short loc_1401F90D8
0x1401f90d5  mov     r12, rbp
0x1401f90d8  mov     rbp, [r12]
0x1401f90dc  test    rbp, rbp
0x1401f90df  jnz     loc_14008D912
0x1401f90e5  jmp     loc_14008DB0D
  ... truncated ...
```
