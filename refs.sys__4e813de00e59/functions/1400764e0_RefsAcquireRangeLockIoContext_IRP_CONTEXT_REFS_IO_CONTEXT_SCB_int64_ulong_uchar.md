# RefsAcquireRangeLockIoContext(_IRP_CONTEXT *,REFS_IO_CONTEXT *,_SCB *,__int64,ulong,uchar)

- ea: `0x1400764e0`
- end: `0x140076a36`
- name: `?RefsAcquireRangeLockIoContext@@YA_NPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@PEAU_SCB@@_JKE@Z`
- size: `1366`
- prototype: `bool __usercall@<al>(struct _IRP_CONTEXT *@<rcx>, struct REFS_IO_CONTEXT *@<rdx>, struct _SCB *@<r8>, __int64@<r9>, unsigned int, unsigned __int8)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x1400b6ba0`

## callees

- `0x1400764e0`
- `0x140076ad0`
- `0x1400845e0`
- `0x1400862c0`
- `0x140089b40`
- `0x14009c7a0`
- `0x1400d0fd8`
- `0x1400d13a8`
- `0x1401f3c1c`
- `0x1401f3cec`
- `0x1401f3fc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140076690`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007680d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401feeae`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140076690`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007680d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401feeae`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140076611`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400767f3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14007685c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140076945`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1401fee95`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1401fef31`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140076611`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400767f3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14007685c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140076945`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1401fee95`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1401fef31`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400766e3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14007683c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140076a1f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401feec7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401feeed`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401fef63`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400766e3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14007683c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140076a1f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401feec7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401feeed`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401fef63`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140076530`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140076782`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140076530`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140076782`

## pseudocode

```c
bool __fastcall RefsAcquireRangeLockIoContext(
        struct _IRP_CONTEXT *a1,
        struct REFS_IO_CONTEXT *a2,
        struct _SCB *a3,
        __int64 a4,
        unsigned int a5,
        unsigned __int8 a6)
{
  int v6; // eax
  struct _SCB *v7; // rbx
  __int64 v8; // rsi
  char *v11; // r12
  __int64 v12; // r8
  __int64 v13; // rax
  char v14; // cl
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int128 v19; // rdi
  KSPIN_LOCK *v20; // r14
  KSPIN_LOCK **v21; // rbx
  NTSTATUS inserted; // r12d
  _QWORD *i; // r10
  unsigned __int64 j; // rax
  __int64 v26; // rcx
  char v27; // dl
  __int64 v28; // rcx
  __int64 v29; // r8
  char v30; // al
  _QWORD *v31; // rdx
  __int64 v32; // rax
  _QWORD *v33; // rbx
  _QWORD *v34; // rax
  unsigned __int64 v35; // rax
  char v37; // cl
  unsigned __int64 v38; // rdi
  __int64 v39; // rdx
  __int64 v40; // r14
  KSPIN_LOCK *v41; // rbx
  KSPIN_LOCK **v42; // rsi
  _QWORD *v43; // rax
  NTSTATUS v44; // r12d
  int v45; // eax
  _QWORD *v46; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+38h] [rbp-41h] BYREF
  struct _SCB *v48; // [rsp+50h] [rbp-29h]
  __int64 v49; // [rsp+58h] [rbp-21h]
  __int128 v50; // [rsp+60h] [rbp-19h] BYREF

  v6 = *((_DWORD *)a1 + 1);
  v7 = a3;
  v48 = a3;
  v8 = a4;
  v49 = a4;
  if ( (v6 & 0x40) == 0
    && (!(unsigned __int8)ExIsFastResourceHeldExclusive(*(_QWORD *)(*((_QWORD *)a3 + 17) + 88LL) + 64LL)
     || !(unsigned __int8)ExIsFastResourceHeldExclusive(*(_QWORD *)(*((_QWORD *)v7 + 17) + 96LL))) )
  {
    if ( (*((_DWORD *)a1 + 1) & 0x40) != 0 )
    {
LABEL_32:
      *((_DWORD *)a1 + 1) |= 0x40u;
      *((_QWORD *)a2 + 102) = *((_QWORD *)v7 + 31);
      *((_DWORD *)a2 + 208) = a5;
      *((_BYTE *)a2 + 836) = a6;
      *((_QWORD *)a2 + 103) = v8;
      return a6 != 0;
    }
    v11 = (char *)a2 + 32;
    v12 = *((_QWORD *)v7 + 31);
    LockHandle.LockQueue = 0;
    v13 = *(_QWORD *)(v12 + 56);
    v50 = 0;
    if ( !a6 )
    {
      v14 = 14;
      if ( *(_DWORD *)(v13 + 552) == 12 )
        v14 = 12;
      v15 = 1 << v14;
      *(_QWORD *)&LockHandle.OldIrql = 0;
      v16 = a5 + v15;
      v17 = -v15;
      *(_QWORD *)&v19 = v17 & v8;
      v18 = v17 & (v8 - 1 + v16);
      *((_QWORD *)&v19 + 1) = v18 - 1;
      if ( v18 - 1 < (unsigned __int64)v19 && v18 != (_QWORD)v19 )
      {
        inserted = -1073741407;
        goto LABEL_48;
      }
      v20 = *(KSPIN_LOCK **)(v12 + 64);
      v21 = (KSPIN_LOCK **)(v12 + 64);
      if ( !v20 )
      {
        inserted = FsLibPrivateInitializeRangeLock(v12 + 64);
        if ( inserted < 0 )
          goto LABEL_48;
        v20 = *v21;
      }
      inserted = 0;
      v50 = v19;
      if ( !v20[1] )
      {
        KeAcquireInStackQueuedSpinLock(v20, &LockHandle);
        if ( !v20[1] )
        {
          v46 = ExAllocateFromNPagedLookasideList(&FsLibRangeLockIntLookasideList);
          v20[1] = (KSPIN_LOCK)v46;
          if ( !v46 )
          {
            KeReleaseInStackQueuedSpinLock(&LockHandle);
            inserted = -1073741670;
            goto LABEL_48;
          }
          v46[1] = 0;
          *(_QWORD *)v20[1] = 0;
        }
        KeReleaseInStackQueuedSpinLock(&LockHandle);
      }
      if ( v20[3] )
      {
        KeAcquireInStackQueuedSpinLock(v20, &LockHandle);
        if ( v20[3] && !(unsigned __int8)FsLibPrivateCheckFirstWaitingRangeLockForAccess(v20, &v50, 0) )
          goto LABEL_63;
        v30 = FsLibPrivateSearchArrayForRange(v20[2], &v50);
      }
      else
      {
        KeAcquireInStackQueuedSpinLock(v20, &LockHandle);
        for ( i = (_QWORD *)v20[2]; i; i = (_QWORD *)*i )
        {
          for ( j = i[1]; _BitScanForward64((unsigned __int64 *)&v26, j); j &= ~(1LL << v27) )
          {
            v27 = v26;
            v28 = 2 * v26;
            v29 = i[v28 + 2];
            if ( (__int64)v50 > v29 )
              goto LABEL_18;
            if ( v29 <= *((__int64 *)&v50 + 1) )
              goto LABEL_20;
            if ( (__int64)v50 >= v29 )
            {
LABEL_18:
              if ( (__int64)v50 <= i[v28 + 3] )
              {
LABEL_20:
                v30 = 0;
                goto LABEL_21;
              }
            }
          }
        }
        v30 = 1;
      }
LABEL_21:
      if ( v30 )
      {
        v31 = (_QWORD *)v20[1];
        do
        {
          v32 = v31[1];
          if ( v32 != -1 )
          {
            v35 = ~v32;
            goto LABEL_28;
          }
          v33 = v31;
          v31 = (_QWORD *)*v31;
        }
        while ( v31 );
        v34 = ExAllocateFromNPagedLookasideList(&FsLibRangeLockIntLookasideList);
        *v33 = v34;
        v31 = v34;
        if ( !v34 )
        {
          inserted = -1073741670;
          goto LABEL_29;
        }
        v34[1] = 0;
        *v34 = 0;
        v35 = -1;
LABEL_28:
        _BitScanForward64(&v35, v35);
        *((_QWORD *)a2 + 4) = v31;
        *((_QWORD *)a2 + 5) = 1LL << v35;
        v31[1] |= 1LL << v35;
        *(_OWORD *)&v31[2 * v35 + 2] = v50;
LABEL_29:
        KeReleaseInStackQueuedSpinLock(&LockHandle);
LABEL_30:
        if ( inserted < 0 )
        {
LABEL_48:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              18,
              WPP_31376ab3b8073048edfb14e725e449b5_Traceguids,
              (unsigned int)inserted);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(inserted, a1, "ResrcSup.c", 0xE54u);
          RefsRaiseStatusInternal(a1, inserted, v12);
          __debugbreak();
        }
        goto LABEL_31;
      }
LABEL_63:
      inserted = FsLibInsertWaitingLock(v20, &v50, 0x80000000LL, &LockHandle, (char *)a2 + 32);
      goto LABEL_30;
    }
    v37 = *(_BYTE *)(v13 + 552);
    v38 = v8 >> v37 << v37;
    v39 = (__int64)(v8 + a5 + (unsigned __int64)*(unsigned int *)(v13 + 544)) >> v37 << v37;
    *(_QWORD *)&LockHandle.OldIrql = 0;
    v40 = v39 - 1;
    if ( v39 - 1 < v38 && v39 != v38 )
    {
      v44 = -1073741407;
      goto LABEL_53;
    }
    v41 = *(KSPIN_LOCK **)(v12 + 64);
    v42 = (KSPIN_LOCK **)(v12 + 64);
    if ( !v41 )
    {
      v45 = FsLibPrivateInitializeRangeLock(v12 + 64);
      if ( v45 < 0 )
      {
        v44 = v45;
        goto LABEL_53;
      }
      v41 = *v42;
    }
    *(_QWORD *)&v50 = v38;
    *((_QWORD *)&v50 + 1) = v40;
    if ( !v41[2] )
    {
      KeAcquireInStackQueuedSpinLock(v41, &LockHandle);
      if ( !v41[2] )
      {
        v43 = ExAllocateFromNPagedLookasideList(&FsLibRangeLockIntLookasideList);
        v41[2] = (KSPIN_LOCK)v43;
        if ( !v43 )
        {
          KeReleaseInStackQueuedSpinLock(&LockHandle);
          v44 = -1073741670;
          goto LABEL_53;
        }
        v43[1] = 0;
        *(_QWORD *)v41[2] = 0;
        v11 = (char *)a2 + 32;
      }
      KeReleaseInStackQueuedSpinLock(&LockHandle);
    }
    if ( v41[3] )
    {
      KeAcquireInStackQueuedSpinLock(v41, &LockHandle);
      if ( v41[3] && !(unsigned __int8)FsLibPrivateCheckFirstWaitingRangeLockForAccess(v41, &v50, 0) )
        goto LABEL_83;
    }
    else
    {
      KeAcquireInStackQueuedSpinLock(v41, &LockHandle);
    }
    if ( (unsigned __int8)FsLibPrivateCheckForExclusiveRangeLockAccess(v41, &v50) )
    {
      v44 = FsLibPrivateInsertRangeLockExclusive(v41, &v50, v11);
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      goto LABEL_52;
    }
LABEL_83:
    v44 = FsLibInsertWaitingLock(v41, &v50, 2147483649LL, &LockHandle, v11);
LABEL_52:
    if ( v44 >= 0 )
    {
LABEL_31:
      v8 = v49;
      v7 = v48;
      goto LABEL_32;
    }
LABEL_53:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        19,
        WPP_31376ab3b8073048edfb14e725e449b5_Traceguids,
        (unsigned int)v44);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(v44, a1, "ResrcSup.c", 0xE63u);
    RefsRaiseStatusInternal(a1, v44, v12);
    JUMPOUT(0x1401FEFC6LL);
  }
  return 1;
}

```

## disassembly

```asm
0x1400764e0  push    rbp
0x1400764e2  push    rbx
0x1400764e3  push    rsi
0x1400764e4  push    r13
0x1400764e6  push    r15
0x1400764e8  lea     rbp, [rsp-27h]
0x1400764ed  sub     rsp, 0A0h
0x1400764f4  mov     rax, cs:__security_cookie
0x1400764fb  xor     rax, rsp
0x1400764fe  mov     [rbp+47h+var_50], rax
0x140076502  mov     eax, [rcx+4]
0x140076505  mov     rbx, r8
0x140076508  mov     [rbp+47h+var_70], rbx
0x14007650c  mov     rsi, r9
0x14007650f  mov     [rbp+47h+var_68], r9
0x140076513  mov     r15, rdx
0x140076516  mov     r13, rcx
0x140076519  test    al, 40h
0x14007651b  jnz     loc_140076796
0x140076521  mov     rax, [r8+88h]
0x140076528  mov     rcx, [rax+58h]
0x14007652c  add     rcx, 40h ; '@'
0x140076530  call    cs:__imp_ExIsFastResourceHeldExclusive
0x140076537  nop     dword ptr [rax+rax+00h]
0x14007653c  test    al, al
0x14007653e  jnz     loc_140076777
0x140076544  mov     eax, [r13+4]
0x140076548  mov     [rsp+0C0h+var_28], rdi
0x140076550  mov     [rsp+0C0h+var_30], r12
0x140076558  mov     [rsp+0C0h+var_38], r14
0x140076560  test    al, 40h
0x140076562  jnz     loc_140076700
0x140076568  cmp     [rbp+47h+arg_28], 0
0x14007656c  lea     r12, [r15+20h]
0x140076570  mov     r8, [rbx+0F8h]
0x140076577  xorps   xmm0, xmm0
0x14007657a  mov     r9d, [rbp+47h+arg_20]
0x14007657e  mov     rdi, rsi
0x140076581  movups  xmmword ptr [rbp+47h+LockHandle.LockQueue.Next], xmm0
0x140076585  mov     rax, [r8+38h]
0x140076589  movups  [rbp+47h+var_60], xmm0
0x14007658d  jnz     loc_14007679A
0x140076593  mov     eax, [rax+228h]
0x140076599  mov     ecx, 0Eh
0x14007659e  cmp     eax, 0Ch
0x1400765a1  cmovz   cx, ax
0x1400765a5  dec     rsi
0x1400765a8  mov     eax, 1
0x1400765ad  shl     eax, cl
0x1400765af  movsxd  rcx, eax
0x1400765b2  xor     eax, eax
0x1400765b4  mov     rdx, rcx
0x1400765b7  mov     qword ptr [rbp+47h+LockHandle.OldIrql], rax
0x1400765bb  add     rcx, r9
0x1400765be  neg     rdx
0x1400765c1  add     rcx, rsi
0x1400765c4  and     rdi, rdx
0x1400765c7  and     rcx, rdx
0x1400765ca  lea     rsi, [rcx-1]
0x1400765ce  cmp     rsi, rdi
0x1400765d1  jb      loc_140076916
0x1400765d7  mov     r14, [r8+40h]
0x1400765db  lea     rbx, [r8+40h]
0x1400765df  test    r14, r14
0x1400765e2  jz      loc_14007692A
0x1400765e8  xor     r12d, r12d
0x1400765eb  mov     qword ptr [rbp+47h+var_60], rdi
0x1400765ef  mov     qword ptr [rbp+47h+var_60+8], rsi
0x1400765f3  cmp     [r14+8], r12
0x1400765f7  jz      loc_1401FEE8E
0x1400765fd  mov     rax, [r14+18h]
0x140076601  lea     rdx, [rbp+47h+LockHandle]; LockHandle
0x140076605  mov     rcx, r14; SpinLock
0x140076608  test    rax, rax
0x14007660b  jnz     loc_140076945
0x140076611  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140076618  nop     dword ptr [rax+rax+00h]
0x14007661d  mov     r10, [r14+10h]
0x140076621  mov     r11, qword ptr [rbp+47h+var_60+8]
0x140076625  mov     r9, qword ptr [rbp+47h+var_60]
0x140076629  test    r10, r10
0x14007662c  jz      loc_140076770
0x140076632  mov     rax, [r10+8]
0x140076636  bsf     rcx, rax
0x14007663a  jz      loc_140076768
0x140076640  mov     edx, ecx
0x140076642  add     rcx, rcx
0x140076645  mov     r8, [r10+rcx*8+10h]
0x14007664a  cmp     r9, r8
0x14007664d  jg      short loc_140076659
0x14007664f  cmp     r8, r11
0x140076652  jle     short loc_140076666
0x140076654  cmp     r9, r8
0x140076657  jl      short loc_140076660
0x140076659  cmp     r9, [r10+rcx*8+18h]
0x14007665e  jle     short loc_140076666
0x140076660  btr     rax, rdx
0x140076664  jmp     short loc_140076636
0x140076666  xor     al, al
0x140076668  test    al, al
0x14007666a  jz      loc_140076977
0x140076670  mov     rdx, [r14+8]
0x140076674  mov     rax, [rdx+8]
0x140076678  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14007667c  jnz     short loc_1400766B3
0x14007667e  mov     rbx, rdx
0x140076681  mov     rdx, [rdx]
0x140076684  test    rdx, rdx
0x140076687  jnz     short loc_140076674
0x140076689  lea     rcx, FsLibRangeLockIntLookasideList; Lookaside
0x140076690  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140076697  nop     dword ptr [rax+rax+00h]
0x14007669c  mov     [rbx], rax
0x14007669f  mov     rdx, rax
0x1400766a2  test    rax, rax
0x1400766a5  jnz     loc_1401FEF16
0x1400766ab  mov     r12d, 0C000009Ah
0x1400766b1  jmp     short loc_1400766DF
0x1400766b3  not     rax
0x1400766b6  bsf     rax, rax
0x1400766ba  mov     [r15+20h], rdx
0x1400766be  mov     r8d, 1
0x1400766c4  mov     ecx, eax
0x1400766c6  inc     rax
0x1400766c9  shl     r8, cl
0x1400766cc  mov     [r15+28h], r8
0x1400766d0  or      [rdx+8], r8
0x1400766d4  movups  xmm0, [rbp+47h+var_60]
0x1400766d8  add     rax, rax
0x1400766db  movups  xmmword ptr [rdx+rax*8], xmm0
0x1400766df  lea     rcx, [rbp+47h+LockHandle]; LockHandle
0x1400766e3  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400766ea  nop     dword ptr [rax+rax+00h]
0x1400766ef  test    r12d, r12d
0x1400766f2  js      loc_14007688F
0x1400766f8  mov     rsi, [rbp+47h+var_68]
0x1400766fc  mov     rbx, [rbp+47h+var_70]
0x140076700  or      dword ptr [r13+4], 40h
0x140076705  mov     rax, [rbx+0F8h]
0x14007670c  mov     r12, [rsp+0C0h+var_30]
0x140076714  mov     rdi, [rsp+0C0h+var_28]
0x14007671c  mov     r14, [rsp+0C0h+var_38]
0x140076724  mov     [r15+330h], rax
0x14007672b  mov     eax, [rbp+47h+arg_20]
0x14007672e  mov     [r15+340h], eax
0x140076735  movzx   eax, [rbp+47h+arg_28]
0x140076739  test    al, al
0x14007673b  mov     [r15+344h], al
0x140076742  mov     [r15+338h], rsi
0x140076749  setnz   al
0x14007674c  mov     rcx, [rbp+47h+var_50]
0x140076750  xor     rcx, rsp; StackCookie
0x140076753  call    __security_check_cookie
0x140076758  add     rsp, 0A0h
0x14007675f  pop     r15
0x140076761  pop     r13
0x140076763  pop     rsi
0x140076764  pop     rbx
0x140076765  pop     rbp
0x140076766  retn
0x140076768  mov     r10, [r10]
0x14007676b  jmp     loc_140076629
0x140076770  mov     al, 1
0x140076772  jmp     loc_140076668
0x140076777  mov     rcx, [rbx+88h]
0x14007677e  mov     rcx, [rcx+60h]
0x140076782  call    cs:__imp_ExIsFastResourceHeldExclusive
0x140076789  nop     dword ptr [rax+rax+00h]
0x14007678e  test    al, al
0x140076790  jz      loc_140076544
0x140076796  mov     al, 1
0x140076798  jmp     short loc_14007674C
0x14007679a  movsx   ecx, byte ptr [rax+228h]
0x1400767a1  mov     edx, [rax+220h]
0x1400767a7  xor     eax, eax
0x1400767a9  add     rdx, r9
0x1400767ac  sar     rdi, cl
0x1400767af  add     rdx, rsi
0x1400767b2  shl     rdi, cl
0x1400767b5  sar     rdx, cl
0x1400767b8  shl     rdx, cl
0x1400767bb  mov     qword ptr [rbp+47h+LockHandle.OldIrql], rax
0x1400767bf  lea     r14, [rdx-1]
0x1400767c3  cmp     r14, rdi
0x1400767c6  jb      loc_1400769EF
0x1400767cc  mov     rbx, [r8+40h]
0x1400767d0  lea     rsi, [r8+40h]
0x1400767d4  test    rbx, rbx
0x1400767d7  jz      loc_140076A03
0x1400767dd  mov     qword ptr [rbp+47h+var_60], rdi
0x1400767e1  mov     qword ptr [rbp+47h+var_60+8], r14
0x1400767e5  cmp     qword ptr [rbx+10h], 0
0x1400767ea  jnz     short loc_140076848
0x1400767ec  lea     rdx, [rbp+47h+LockHandle]; LockHandle
0x1400767f0  mov     rcx, rbx; SpinLock
0x1400767f3  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400767fa  nop     dword ptr [rax+rax+00h]
0x1400767ff  cmp     qword ptr [rbx+10h], 0
0x140076804  jnz     short loc_140076838
0x140076806  lea     rcx, FsLibRangeLockIntLookasideList; Lookaside
0x14007680d  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140076814  nop     dword ptr [rax+rax+00h]
0x140076819  mov     [rbx+10h], rax
0x14007681d  test    rax, rax
0x140076820  jz      loc_140076A1B
0x140076826  xor     r12d, r12d
0x140076829  mov     [rax+8], r12
0x14007682d  mov     rax, [rbx+10h]
0x140076831  mov     [rax], r12
0x140076834  lea     r12, [r15+20h]
0x140076838  lea     rcx, [rbp+47h+LockHandle]; LockHandle
0x14007683c  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140076843  nop     dword ptr [rax+rax+00h]
0x140076848  mov     rax, [rbx+18h]
0x14007684c  lea     rdx, [rbp+47h+LockHandle]; LockHandle
0x140076850  mov     rcx, rbx; SpinLock
0x140076853  test    rax, rax
0x140076856  jz      loc_1401FEF31
0x14007685c  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140076863  nop     dword ptr [rax+rax+00h]
0x140076868  cmp     qword ptr [rbx+18h], 0
0x14007686d  lea     rdx, [rbp+47h+var_60]
0x140076871  jz      loc_1401FEF41
0x140076877  xor     r8d, r8d
0x14007687a  mov     rcx, rbx
0x14007687d  call    FsLibPrivateCheckFirstWaitingRangeLockForAccess
0x140076882  test    al, al
0x140076884  jnz     loc_1401FEF3D
0x14007688a  jmp     loc_1401FEF75
0x14007688f  mov     rcx, cs:WPP_GLOBAL_Control
0x140076896  lea     rax, WPP_GLOBAL_Control
0x14007689d  cmp     rcx, rax
0x1400768a0  jnz     loc_14007699E
0x1400768a6  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1400768ad  test    al, al
0x1400768af  jnz     loc_1400769D2
0x1400768b5  mov     edx, r12d; int
0x1400768b8  mov     rcx, r13; struct _IRP_CONTEXT *
0x1400768bb  call    ?RefsRaiseStatusInternal@@YAXPEAU_IRP_CONTEXT@@JK@Z; RefsRaiseStatusInternal(_IRP_CONTEXT *,long,ulong)
0x1400768c0  int     3; Trap to Debugger
0x1400768c1  test    r12d, r12d
0x1400768c4  jns     loc_1400766F8
0x1400768ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400768d1  lea     rax, WPP_GLOBAL_Control
0x1400768d8  cmp     rcx, rax
0x1400768db  jz      loc_1401FEF98
0x1400768e1  test    dword ptr [rcx+2Ch], 100h
0x1400768e8  jz      loc_1401FEF98
0x1400768ee  cmp     byte ptr [rcx+29h], 4
0x1400768f2  jb      loc_1401FEF98
0x1400768f8  mov     rcx, [rcx+18h]
0x1400768fc  lea     r8, WPP_31376ab3b8073048edfb14e725e449b5_Traceguids
0x140076903  mov     edx, 13h
0x140076908  mov     r9d, r12d
0x14007690b  call    WPP_SF_d
0x140076910  nop
0x140076911  jmp     loc_1401FEF98
0x140076916  cmp     rcx, rdi
0x140076919  jz      loc_1400765D7
0x14007691f  mov     r12d, 0C00001A1h
0x140076925  jmp     loc_14007688F
0x14007692a  mov     rcx, rbx
0x14007692d  call    FsLibPrivateInitializeRangeLock
0x140076932  mov     r12d, eax
0x140076935  test    eax, eax
0x140076937  js      loc_14007688F
0x14007693d  mov     r14, [rbx]
0x140076940  jmp     loc_1400765E8
0x140076945  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14007694c  nop     dword ptr [rax+rax+00h]
0x140076951  lea     rdx, [rbp+47h+var_60]
0x140076955  cmp     [r14+18h], r12
0x140076959  jz      loc_1401FEEFF
0x14007695f  xor     r8d, r8d
0x140076962  mov     rcx, r14
0x140076965  call    FsLibPrivateCheckFirstWaitingRangeLockForAccess
0x14007696a  test    al, al
0x14007696c  jz      short loc_140076977
0x14007696e  lea     rdx, [rbp+47h+var_60]
0x140076972  jmp     loc_1401FEEFF
0x140076977  lea     r9, [r15+20h]
0x14007697b  mov     r8d, 80000000h
0x140076981  mov     [rsp+0C0h+var_A0], r9
0x140076986  lea     rdx, [rbp+47h+var_60]
0x14007698a  lea     r9, [rbp+47h+LockHandle]
0x14007698e  mov     rcx, r14
0x140076991  call    FsLibInsertWaitingLock
0x140076996  mov     r12d, eax
0x140076999  jmp     loc_1400766EF
0x14007699e  test    dword ptr [rcx+2Ch], 100h
0x1400769a5  jz      loc_1400768A6
0x1400769ab  cmp     byte ptr [rcx+29h], 4
0x1400769af  jb      loc_1400768A6
0x1400769b5  mov     rcx, [rcx+18h]
0x1400769b9  lea     r8, WPP_31376ab3b8073048edfb14e725e449b5_Traceguids
0x1400769c0  mov     edx, 12h
0x1400769c5  mov     r9d, r12d
0x1400769c8  call    WPP_SF_d
0x1400769cd  jmp     loc_1400768A6
0x1400769d2  mov     r9d, 0E54h; unsigned int
  ... truncated ...
```
