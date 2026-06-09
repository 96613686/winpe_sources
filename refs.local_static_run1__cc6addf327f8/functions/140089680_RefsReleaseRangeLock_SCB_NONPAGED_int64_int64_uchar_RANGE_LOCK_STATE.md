# RefsReleaseRangeLock(_SCB_NONPAGED *,__int64,__int64,uchar,_RANGE_LOCK_STATE *)

- ea: `0x140089680`
- end: `0x140089a40`
- name: `?RefsReleaseRangeLock@@YAXPEAU_SCB_NONPAGED@@_J1EPEAU_RANGE_LOCK_STATE@@@Z`
- size: `960`
- prototype: `void __fastcall(struct _SCB_NONPAGED *, __int64, __int64, unsigned __int8, struct _RANGE_LOCK_STATE *)`
- caller_count: `15`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x1400867d0`
- `0x1400ba4d0`
- `0x1400ea220`
- `0x1400eaac8`
- `0x1400ebf08`
- `0x1400ec8a4`
- `0x1400ee708`
- `0x1400f0948`
- `0x1400f192c`
- `0x1400fbedc`
- `0x140291a00`
- `0x140295fb0`
- `0x14029ddd4`
- `0x1402a2e00`
- `0x1402b2c70`

## callees

- `0x1400845e0`
- `0x140089680`
- `0x140089b40`
- `0x140089bf0`
- `0x1400901a0`
- `0x14009c7a0`
- `0x1400cf214`
- `0x1401f3cdc`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140200fe7`
- `ntoskrnl!KeSetEvent` at `0x1402010cb`
- `ntoskrnl!KeSetEvent` at `0x140200fe7`
- `ntoskrnl!KeSetEvent` at `0x1402010cb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400899f1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140089a23`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140200f6a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14020104d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400899f1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140089a23`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140200f6a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14020104d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140089747`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14008983b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400898cb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140089954`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140089747`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14008983b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400898cb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140089954`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140089903`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14008998c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140089903`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14008998c`

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
0x140089680  mov     [rsp+arg_0], rbx
0x140089685  mov     [rsp+arg_8], rbp
0x14008968a  push    rsi
0x14008968b  push    rdi
0x14008968c  push    r12
0x14008968e  push    r14
0x140089690  push    r15
0x140089692  sub     rsp, 60h
0x140089696  mov     rax, [rcx+38h]
0x14008969a  xorps   xmm0, xmm0
0x14008969d  mov     r10, rdx
0x1400896a0  movups  [rsp+88h+var_68], xmm0
0x1400896a5  test    r9b, r9b
0x1400896a8  jnz     loc_1400897CF
0x1400896ae  mov     eax, [rax+228h]
0x1400896b4  mov     edx, 0Eh
0x1400896b9  mov     rbp, [rcx+40h]
0x1400896bd  cmp     eax, 0Ch
0x1400896c0  movups  xmmword ptr [rsp+88h+LockHandle.LockQueue.Next], xmm0
0x1400896c5  cmovz   dx, ax
0x1400896c9  xor     eax, eax
0x1400896cb  mov     qword ptr [rsp+88h+LockHandle.OldIrql], rax
0x1400896d0  cmp     [rbp+8], rax
0x1400896d4  jnz     short loc_1400896F0
0x1400896d6  lea     r11, [rsp+88h+var_28]
0x1400896db  mov     rbx, [r11+30h]
0x1400896df  mov     rbp, [r11+38h]
0x1400896e3  mov     rsp, r11
0x1400896e6  pop     r15
0x1400896e8  pop     r14
0x1400896ea  pop     r12
0x1400896ec  pop     rdi
0x1400896ed  pop     rsi
0x1400896ee  retn
0x1400896f0  mov     rbx, [rsp+88h+arg_20]
0x1400896f8  lea     rsi, [r10-1]
0x1400896fc  movzx   ecx, dl
0x1400896ff  mov     eax, 1
0x140089704  shl     eax, cl
0x140089706  movsxd  rcx, eax
0x140089709  add     rsi, rcx
0x14008970c  mov     rdx, rcx
0x14008970f  neg     rdx
0x140089712  add     rsi, r8
0x140089715  and     rsi, rdx
0x140089718  mov     r14, rdx
0x14008971b  and     r14, r10
0x14008971e  dec     rsi
0x140089721  mov     qword ptr [rsp+88h+var_68], r14
0x140089726  mov     qword ptr [rsp+88h+var_68+8], rsi
0x14008972b  test    rbx, rbx
0x14008972e  jz      loc_14008994C
0x140089734  cmp     qword ptr [rbx+8], 0
0x140089739  jz      loc_14008994C
0x14008973f  lea     rdx, [rsp+88h+LockHandle]; LockHandle
0x140089744  mov     rcx, rbp; SpinLock
0x140089747  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14008974e  nop     dword ptr [rax+rax+00h]
0x140089753  mov     rax, [rbx+8]
0x140089757  mov     rdx, [rbp+8]
0x14008975b  not     rax
0x14008975e  mov     rcx, [rbx]
0x140089761  and     [rcx+8], rax
0x140089765  mov     rax, [rbx]
0x140089768  cmp     rax, rdx
0x14008976b  jnz     loc_14008991D
0x140089771  xor     edi, edi
0x140089773  mov     r14, [rbp+18h]
0x140089777  test    r14, r14
0x14008977a  jz      loc_140089987
0x140089780  lea     r15, [rbp+18h]
0x140089784  mov     r12, [r14+28h]
0x140089788  lea     rcx, [rsp+88h+var_68]
0x14008978d  mov     rdx, r12
0x140089790  call    AreRangeLocksOverlapping
0x140089795  test    al, al
0x140089797  jz      loc_140200FF5
0x14008979d  movzx   r9d, byte ptr [r14+24h]
0x1400897a2  test    r9b, 2
0x1400897a6  jnz     loc_140200F8D
0x1400897ac  cmp     [rbp+18h], r14
0x1400897b0  jz      loc_140200F8D
0x1400897b6  movzx   r8d, r9b
0x1400897ba  mov     rcx, rbp
0x1400897bd  call    FsLibPrivateCheckFirstWaitingRangeLockForAccess
0x1400897c2  test    al, al
0x1400897c4  jnz     loc_140200F8D
0x1400897ca  jmp     loc_140200FF5
0x1400897cf  mov     rsi, [rcx+40h]
0x1400897d3  xor     edx, edx
0x1400897d5  movups  xmmword ptr [rsp+88h+var_40.LockQueue.Next], xmm0
0x1400897da  mov     qword ptr [rsp+88h+var_40.OldIrql], rdx
0x1400897df  cmp     [rsi+10h], rdx
0x1400897e3  jz      loc_1400896D6
0x1400897e9  movsx   ecx, byte ptr [rax+228h]
0x1400897f0  mov     r14, r10
0x1400897f3  mov     ebp, [rax+220h]
0x1400897f9  mov     rbx, [rsp+88h+arg_20]
0x140089801  add     rbp, r10
0x140089804  add     rbp, r8
0x140089807  sar     r14, cl
0x14008980a  sar     rbp, cl
0x14008980d  shl     rbp, cl
0x140089810  dec     rbp
0x140089813  shl     r14, cl
0x140089816  mov     qword ptr [rsp+88h+var_68], r14
0x14008981b  mov     qword ptr [rsp+88h+var_68+8], rbp
0x140089820  test    rbx, rbx
0x140089823  jz      loc_1400898C3
0x140089829  cmp     [rbx+8], rdx
0x14008982d  jz      loc_1400898C3
0x140089833  lea     rdx, [rsp+88h+var_40]; LockHandle
0x140089838  mov     rcx, rsi; SpinLock
0x14008983b  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140089842  nop     dword ptr [rax+rax+00h]
0x140089847  mov     rax, [rbx+8]
0x14008984b  mov     rdx, [rsi+10h]
0x14008984f  not     rax
0x140089852  mov     rcx, [rbx]
0x140089855  and     [rcx+8], rax
0x140089859  mov     rax, [rbx]
0x14008985c  cmp     rax, rdx
0x14008985f  jnz     loc_1400899AA
0x140089865  xor     edi, edi
0x140089867  mov     r15, [rsi+18h]
0x14008986b  test    r15, r15
0x14008986e  jz      loc_1400898FE
0x140089874  lea     rbp, [rsi+18h]
0x140089878  mov     r12, [r15+28h]
0x14008987c  lea     rcx, [rsp+88h+var_68]
0x140089881  mov     rdx, r12
0x140089884  call    AreRangeLocksOverlapping
0x140089889  test    al, al
0x14008988b  jz      loc_1402010D9
0x140089891  movzx   r9d, byte ptr [r15+24h]
0x140089896  test    r9b, 2
0x14008989a  jnz     loc_140201070
0x1400898a0  cmp     [rsi+18h], r15
0x1400898a4  jz      loc_140201070
0x1400898aa  movzx   r8d, r9b
0x1400898ae  mov     rcx, rsi
0x1400898b1  call    FsLibPrivateCheckFirstWaitingRangeLockForAccess
0x1400898b6  test    al, al
0x1400898b8  jnz     loc_140201070
0x1400898be  jmp     loc_1402010D9
0x1400898c3  lea     rdx, [rsp+88h+var_40]; LockHandle
0x1400898c8  mov     rcx, rsi; SpinLock
0x1400898cb  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400898d2  nop     dword ptr [rax+rax+00h]
0x1400898d7  mov     rdx, [rsi+10h]; Entry
0x1400898db  xor     edi, edi
0x1400898dd  mov     ecx, edi
0x1400898df  test    rdx, rdx
0x1400898e2  jnz     loc_140089A34
0x1400898e8  cmp     [rsi+18h], rdi
0x1400898ec  jz      short loc_1400898FE
0x1400898ee  lea     r8, [rsp+88h+var_68]
0x1400898f3  mov     rdx, rsi
0x1400898f6  mov     rcx, rsi
0x1400898f9  call    FsLibPrivateCheckWaitingRangeLocks
0x1400898fe  lea     rcx, [rsp+88h+var_40]; LockHandle
0x140089903  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14008990a  nop     dword ptr [rax+rax+00h]
0x14008990f  test    rbx, rbx
0x140089912  jnz     loc_1400899A1
0x140089918  jmp     loc_1400896D6
0x14008991d  cmp     qword ptr [rax+8], 0
0x140089922  jnz     loc_140089771
0x140089928  mov     r8, rdx
0x14008992b  mov     rcx, rdx
0x14008992e  xchg    ax, ax
0x140089930  test    rcx, rcx
0x140089933  jz      loc_140089771
0x140089939  cmp     qword ptr [rcx+8], 0
0x14008993e  jz      loc_1400899D8
0x140089944  mov     r8, rcx
0x140089947  mov     rcx, [rcx]
0x14008994a  jmp     short loc_140089930
0x14008994c  lea     rdx, [rsp+88h+LockHandle]; LockHandle
0x140089951  mov     rcx, rbp; SpinLock
0x140089954  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14008995b  nop     dword ptr [rax+rax+00h]
0x140089960  mov     rdx, [rbp+8]; Entry
0x140089964  xor     edi, edi
0x140089966  mov     ecx, edi
0x140089968  test    rdx, rdx
0x14008996b  jnz     loc_140089A02
0x140089971  cmp     [rbp+18h], rdi
0x140089975  jz      short loc_140089987
0x140089977  lea     r8, [rsp+88h+var_68]
0x14008997c  mov     rdx, rbp
0x14008997f  mov     rcx, rbp
0x140089982  call    FsLibPrivateCheckWaitingRangeLocks
0x140089987  lea     rcx, [rsp+88h+LockHandle]; LockHandle
0x14008998c  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140089993  nop     dword ptr [rax+rax+00h]
0x140089998  test    rbx, rbx
0x14008999b  jz      loc_1400896D6
0x1400899a1  mov     [rbx+8], rdi
0x1400899a5  jmp     loc_1400896D6
0x1400899aa  cmp     qword ptr [rax+8], 0
0x1400899af  jnz     loc_140089865
0x1400899b5  mov     r8, rdx
0x1400899b8  mov     rcx, rdx
0x1400899bb  nop     dword ptr [rax+rax+00h]
0x1400899c0  test    rcx, rcx
0x1400899c3  jz      loc_140089865
0x1400899c9  cmp     qword ptr [rcx+8], 0
0x1400899ce  jz      short loc_140089A0E
0x1400899d0  mov     r8, rcx
0x1400899d3  mov     rcx, [rcx]
0x1400899d6  jmp     short loc_1400899C0
0x1400899d8  cmp     rcx, rdx
0x1400899db  jz      loc_140089944
0x1400899e1  mov     rax, [rcx]
0x1400899e4  mov     rdx, rcx; Entry
0x1400899e7  lea     rcx, FsLibRangeLockIntLookasideList; Lookaside
0x1400899ee  mov     [r8], rax
0x1400899f1  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400899f8  nop     dword ptr [rax+rax+00h]
0x1400899fd  jmp     loc_140089771
0x140089a02  mov     r8, [rdx+8]
0x140089a06  mov     r9, r8
0x140089a09  jmp     loc_140200F26
0x140089a0e  cmp     rcx, rdx
0x140089a11  jz      short loc_1400899D0
0x140089a13  mov     rax, [rcx]
0x140089a16  mov     rdx, rcx; Entry
0x140089a19  lea     rcx, FsLibRangeLockIntLookasideList; Lookaside
0x140089a20  mov     [r8], rax
0x140089a23  call    cs:__imp_ExFreeToNPagedLookasideList
0x140089a2a  nop     dword ptr [rax+rax+00h]
0x140089a2f  jmp     loc_140089865
0x140089a34  mov     r8, [rdx+8]
0x140089a38  mov     r9, r8
0x140089a3b  jmp     loc_140201009
0x140200f26  bsf     rax, r9
0x140200f2a  jz      short loc_140200F82
0x140200f2c  mov     r10d, eax
0x140200f2f  add     rax, rax
0x140200f32  cmp     [rdx+rax*8+10h], r14
0x140200f37  jnz     short loc_140200F7C
0x140200f39  cmp     [rdx+rax*8+18h], rsi
0x140200f3e  jnz     short loc_140200F7C
0x140200f40  btr     r8, r10
0x140200f44  mov     [rdx+8], r8
0x140200f48  test    r8, r8
0x140200f4b  jnz     loc_140089773
0x140200f51  test    rcx, rcx
0x140200f54  jz      loc_140089773
0x140200f5a  mov     rax, [rdx]
0x140200f5d  mov     [rcx], rax
0x140200f60  lea     rcx, FsLibRangeLockIntLookasideList; Lookaside
0x140200f67  mov     [rdx], rdi
0x140200f6a  call    cs:__imp_ExFreeToNPagedLookasideList
0x140200f71  nop     dword ptr [rax+rax+00h]
0x140200f76  nop
0x140200f77  jmp     loc_140089773
0x140200f7c  btr     r9, r10
0x140200f80  jmp     short loc_140200F26
0x140200f82  mov     rcx, rdx
0x140200f85  mov     rdx, [rdx]
0x140200f88  jmp     loc_140089968
0x140200f8d  mov     rdx, r12
0x140200f90  test    r9b, 1
0x140200f94  jz      short loc_140200FA0
0x140200f96  mov     rcx, rbp
0x140200f99  call    FsLibPrivateCheckForExclusiveRangeLockAccess
0x140200f9e  jmp     short loc_140200FA9
0x140200fa0  mov     rcx, [rbp+10h]
0x140200fa4  call    FsLibPrivateSearchArrayForRange
0x140200fa9  test    al, al
0x140200fab  jz      short loc_140200FF5
0x140200fad  test    byte ptr [r14+24h], 1
0x140200fb2  mov     rdx, r12
0x140200fb5  mov     r8, [r14+30h]
0x140200fb9  mov     rcx, rbp
0x140200fbc  jz      short loc_140200FC5
0x140200fbe  call    FsLibPrivateInsertRangeLockExclusive
0x140200fc3  jmp     short loc_140200FCA
0x140200fc5  call    FsLibPrivateInsertRangeLockShared
0x140200fca  mov     [r14+20h], eax
0x140200fce  mov     rax, [r14]
0x140200fd1  mov     [r15], rax
0x140200fd4  cmp     r14, [rbp+20h]
0x140200fd8  jnz     short loc_140200FDE
0x140200fda  mov     [rbp+20h], r15
0x140200fde  lea     rcx, [r14+8]; Event
0x140200fe2  xor     r8d, r8d; Wait
0x140200fe5  xor     edx, edx; Increment
0x140200fe7  call    cs:__imp_KeSetEvent
0x140200fee  nop     dword ptr [rax+rax+00h]
0x140200ff3  jmp     short loc_140200FF8
0x140200ff5  mov     r15, r14
0x140200ff8  mov     r14, [r15]
0x140200ffb  test    r14, r14
0x140200ffe  jnz     loc_140089784
0x140201004  jmp     loc_140089987
0x140201009  bsf     rax, r9
0x14020100d  jz      short loc_140201065
  ... truncated ...
```
