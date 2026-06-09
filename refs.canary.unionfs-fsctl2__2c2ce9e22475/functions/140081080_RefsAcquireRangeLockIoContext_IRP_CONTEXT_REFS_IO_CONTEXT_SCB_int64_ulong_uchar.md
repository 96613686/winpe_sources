# RefsAcquireRangeLockIoContext(_IRP_CONTEXT *,REFS_IO_CONTEXT *,_SCB *,__int64,ulong,uchar)

- ea: `0x140081080`
- end: `0x1400815d6`
- name: `?RefsAcquireRangeLockIoContext@@YA_NPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@PEAU_SCB@@_JKE@Z`
- size: `1366`
- prototype: `bool __usercall@<al>(struct _IRP_CONTEXT *@<rcx>, struct REFS_IO_CONTEXT *@<rdx>, struct _SCB *@<r8>, __int64@<r9>, unsigned int, unsigned __int8)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x1400b97a0`

## callees

- `0x140081080`
- `0x140081670`
- `0x14008c030`
- `0x14008dbd0`
- `0x1400904c0`
- `0x1400a1730`
- `0x1400ca788`
- `0x1400cabd8`
- `0x1401e993c`
- `0x1401e9a0c`
- `0x1401e9ce0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140081230`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400813ad`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401f7b3a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140081230`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400813ad`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401f7b3a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400811b1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140081393`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400813fc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400814e5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1401f7b21`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1401f7bbd`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400811b1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140081393`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400813fc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400814e5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1401f7b21`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1401f7bbd`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140081283`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400813dc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400815bf`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401f7b53`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401f7b79`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401f7bef`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140081283`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400813dc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400815bf`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401f7b53`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401f7b79`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401f7bef`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x1400810d0`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140081322`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x1400810d0`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140081322`

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
    JUMPOUT(0x1401F7C52LL);
  }
  return 1;
}

```

## disassembly

```asm
0x140081080  push    rbp
0x140081082  push    rbx
0x140081083  push    rsi
0x140081084  push    r13
0x140081086  push    r15
0x140081088  lea     rbp, [rsp-27h]
0x14008108d  sub     rsp, 0A0h
0x140081094  mov     rax, cs:__security_cookie
0x14008109b  xor     rax, rsp
0x14008109e  mov     [rbp+47h+var_50], rax
0x1400810a2  mov     eax, [rcx+4]
0x1400810a5  mov     rbx, r8
0x1400810a8  mov     [rbp+47h+var_70], rbx
0x1400810ac  mov     rsi, r9
0x1400810af  mov     [rbp+47h+var_68], r9
0x1400810b3  mov     r15, rdx
0x1400810b6  mov     r13, rcx
0x1400810b9  test    al, 40h
0x1400810bb  jnz     loc_140081336
0x1400810c1  mov     rax, [r8+88h]
0x1400810c8  mov     rcx, [rax+58h]
0x1400810cc  add     rcx, 40h ; '@'
0x1400810d0  call    cs:__imp_ExIsFastResourceHeldExclusive
0x1400810d7  nop     dword ptr [rax+rax+00h]
0x1400810dc  test    al, al
0x1400810de  jnz     loc_140081317
0x1400810e4  mov     eax, [r13+4]
0x1400810e8  mov     [rsp+0C0h+var_28], rdi
0x1400810f0  mov     [rsp+0C0h+var_30], r12
0x1400810f8  mov     [rsp+0C0h+var_38], r14
0x140081100  test    al, 40h
0x140081102  jnz     loc_1400812A0
0x140081108  cmp     [rbp+47h+arg_28], 0
0x14008110c  lea     r12, [r15+20h]
0x140081110  mov     r8, [rbx+0F8h]
0x140081117  xorps   xmm0, xmm0
0x14008111a  mov     r9d, [rbp+47h+arg_20]
0x14008111e  mov     rdi, rsi
0x140081121  movups  xmmword ptr [rbp+47h+LockHandle.LockQueue.Next], xmm0
0x140081125  mov     rax, [r8+38h]
0x140081129  movups  [rbp+47h+var_60], xmm0
0x14008112d  jnz     loc_14008133A
0x140081133  mov     eax, [rax+228h]
0x140081139  mov     ecx, 0Eh
0x14008113e  cmp     eax, 0Ch
0x140081141  cmovz   cx, ax
0x140081145  dec     rsi
0x140081148  mov     eax, 1
0x14008114d  shl     eax, cl
0x14008114f  movsxd  rcx, eax
0x140081152  xor     eax, eax
0x140081154  mov     rdx, rcx
0x140081157  mov     qword ptr [rbp+47h+LockHandle.OldIrql], rax
0x14008115b  add     rcx, r9
0x14008115e  neg     rdx
0x140081161  add     rcx, rsi
0x140081164  and     rdi, rdx
0x140081167  and     rcx, rdx
0x14008116a  lea     rsi, [rcx-1]
0x14008116e  cmp     rsi, rdi
0x140081171  jb      loc_1400814B6
0x140081177  mov     r14, [r8+40h]
0x14008117b  lea     rbx, [r8+40h]
0x14008117f  test    r14, r14
0x140081182  jz      loc_1400814CA
0x140081188  xor     r12d, r12d
0x14008118b  mov     qword ptr [rbp+47h+var_60], rdi
0x14008118f  mov     qword ptr [rbp+47h+var_60+8], rsi
0x140081193  cmp     [r14+8], r12
0x140081197  jz      loc_1401F7B1A
0x14008119d  mov     rax, [r14+18h]
0x1400811a1  lea     rdx, [rbp+47h+LockHandle]; LockHandle
0x1400811a5  mov     rcx, r14; SpinLock
0x1400811a8  test    rax, rax
0x1400811ab  jnz     loc_1400814E5
0x1400811b1  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400811b8  nop     dword ptr [rax+rax+00h]
0x1400811bd  mov     r10, [r14+10h]
0x1400811c1  mov     r11, qword ptr [rbp+47h+var_60+8]
0x1400811c5  mov     r9, qword ptr [rbp+47h+var_60]
0x1400811c9  test    r10, r10
0x1400811cc  jz      loc_140081310
0x1400811d2  mov     rax, [r10+8]
0x1400811d6  bsf     rcx, rax
0x1400811da  jz      loc_140081308
0x1400811e0  mov     edx, ecx
0x1400811e2  add     rcx, rcx
0x1400811e5  mov     r8, [r10+rcx*8+10h]
0x1400811ea  cmp     r9, r8
0x1400811ed  jg      short loc_1400811F9
0x1400811ef  cmp     r8, r11
0x1400811f2  jle     short loc_140081206
0x1400811f4  cmp     r9, r8
0x1400811f7  jl      short loc_140081200
0x1400811f9  cmp     r9, [r10+rcx*8+18h]
0x1400811fe  jle     short loc_140081206
0x140081200  btr     rax, rdx
0x140081204  jmp     short loc_1400811D6
0x140081206  xor     al, al
0x140081208  test    al, al
0x14008120a  jz      loc_140081517
0x140081210  mov     rdx, [r14+8]
0x140081214  mov     rax, [rdx+8]
0x140081218  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14008121c  jnz     short loc_140081253
0x14008121e  mov     rbx, rdx
0x140081221  mov     rdx, [rdx]
0x140081224  test    rdx, rdx
0x140081227  jnz     short loc_140081214
0x140081229  lea     rcx, FsLibRangeLockIntLookasideList; Lookaside
0x140081230  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140081237  nop     dword ptr [rax+rax+00h]
0x14008123c  mov     [rbx], rax
0x14008123f  mov     rdx, rax
0x140081242  test    rax, rax
0x140081245  jnz     loc_1401F7BA2
0x14008124b  mov     r12d, 0C000009Ah
0x140081251  jmp     short loc_14008127F
0x140081253  not     rax
0x140081256  bsf     rax, rax
0x14008125a  mov     [r15+20h], rdx
0x14008125e  mov     r8d, 1
0x140081264  mov     ecx, eax
0x140081266  inc     rax
0x140081269  shl     r8, cl
0x14008126c  mov     [r15+28h], r8
0x140081270  or      [rdx+8], r8
0x140081274  movups  xmm0, [rbp+47h+var_60]
0x140081278  add     rax, rax
0x14008127b  movups  xmmword ptr [rdx+rax*8], xmm0
0x14008127f  lea     rcx, [rbp+47h+LockHandle]; LockHandle
0x140081283  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14008128a  nop     dword ptr [rax+rax+00h]
0x14008128f  test    r12d, r12d
0x140081292  js      loc_14008142F
0x140081298  mov     rsi, [rbp+47h+var_68]
0x14008129c  mov     rbx, [rbp+47h+var_70]
0x1400812a0  or      dword ptr [r13+4], 40h
0x1400812a5  mov     rax, [rbx+0F8h]
0x1400812ac  mov     r12, [rsp+0C0h+var_30]
0x1400812b4  mov     rdi, [rsp+0C0h+var_28]
0x1400812bc  mov     r14, [rsp+0C0h+var_38]
0x1400812c4  mov     [r15+330h], rax
0x1400812cb  mov     eax, [rbp+47h+arg_20]
0x1400812ce  mov     [r15+340h], eax
0x1400812d5  movzx   eax, [rbp+47h+arg_28]
0x1400812d9  test    al, al
0x1400812db  mov     [r15+344h], al
0x1400812e2  mov     [r15+338h], rsi
0x1400812e9  setnz   al
0x1400812ec  mov     rcx, [rbp+47h+var_50]
0x1400812f0  xor     rcx, rsp; StackCookie
0x1400812f3  call    __security_check_cookie
0x1400812f8  add     rsp, 0A0h
0x1400812ff  pop     r15
0x140081301  pop     r13
0x140081303  pop     rsi
0x140081304  pop     rbx
0x140081305  pop     rbp
0x140081306  retn
0x140081308  mov     r10, [r10]
0x14008130b  jmp     loc_1400811C9
0x140081310  mov     al, 1
0x140081312  jmp     loc_140081208
0x140081317  mov     rcx, [rbx+88h]
0x14008131e  mov     rcx, [rcx+60h]
0x140081322  call    cs:__imp_ExIsFastResourceHeldExclusive
0x140081329  nop     dword ptr [rax+rax+00h]
0x14008132e  test    al, al
0x140081330  jz      loc_1400810E4
0x140081336  mov     al, 1
0x140081338  jmp     short loc_1400812EC
0x14008133a  movsx   ecx, byte ptr [rax+228h]
0x140081341  mov     edx, [rax+220h]
0x140081347  xor     eax, eax
0x140081349  add     rdx, r9
0x14008134c  sar     rdi, cl
0x14008134f  add     rdx, rsi
0x140081352  shl     rdi, cl
0x140081355  sar     rdx, cl
0x140081358  shl     rdx, cl
0x14008135b  mov     qword ptr [rbp+47h+LockHandle.OldIrql], rax
0x14008135f  lea     r14, [rdx-1]
0x140081363  cmp     r14, rdi
0x140081366  jb      loc_14008158F
0x14008136c  mov     rbx, [r8+40h]
0x140081370  lea     rsi, [r8+40h]
0x140081374  test    rbx, rbx
0x140081377  jz      loc_1400815A3
0x14008137d  mov     qword ptr [rbp+47h+var_60], rdi
0x140081381  mov     qword ptr [rbp+47h+var_60+8], r14
0x140081385  cmp     qword ptr [rbx+10h], 0
0x14008138a  jnz     short loc_1400813E8
0x14008138c  lea     rdx, [rbp+47h+LockHandle]; LockHandle
0x140081390  mov     rcx, rbx; SpinLock
0x140081393  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14008139a  nop     dword ptr [rax+rax+00h]
0x14008139f  cmp     qword ptr [rbx+10h], 0
0x1400813a4  jnz     short loc_1400813D8
0x1400813a6  lea     rcx, FsLibRangeLockIntLookasideList; Lookaside
0x1400813ad  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400813b4  nop     dword ptr [rax+rax+00h]
0x1400813b9  mov     [rbx+10h], rax
0x1400813bd  test    rax, rax
0x1400813c0  jz      loc_1400815BB
0x1400813c6  xor     r12d, r12d
0x1400813c9  mov     [rax+8], r12
0x1400813cd  mov     rax, [rbx+10h]
0x1400813d1  mov     [rax], r12
0x1400813d4  lea     r12, [r15+20h]
0x1400813d8  lea     rcx, [rbp+47h+LockHandle]; LockHandle
0x1400813dc  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400813e3  nop     dword ptr [rax+rax+00h]
0x1400813e8  mov     rax, [rbx+18h]
0x1400813ec  lea     rdx, [rbp+47h+LockHandle]; LockHandle
0x1400813f0  mov     rcx, rbx; SpinLock
0x1400813f3  test    rax, rax
0x1400813f6  jz      loc_1401F7BBD
0x1400813fc  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140081403  nop     dword ptr [rax+rax+00h]
0x140081408  cmp     qword ptr [rbx+18h], 0
0x14008140d  lea     rdx, [rbp+47h+var_60]
0x140081411  jz      loc_1401F7BCD
0x140081417  xor     r8d, r8d
0x14008141a  mov     rcx, rbx
0x14008141d  call    FsLibPrivateCheckFirstWaitingRangeLockForAccess
0x140081422  test    al, al
0x140081424  jnz     loc_1401F7BC9
0x14008142a  jmp     loc_1401F7C01
0x14008142f  mov     rcx, cs:WPP_GLOBAL_Control
0x140081436  lea     rax, WPP_GLOBAL_Control
0x14008143d  cmp     rcx, rax
0x140081440  jnz     loc_14008153E
0x140081446  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14008144d  test    al, al
0x14008144f  jnz     loc_140081572
0x140081455  mov     edx, r12d; int
0x140081458  mov     rcx, r13; struct _IRP_CONTEXT *
0x14008145b  call    ?RefsRaiseStatusInternal@@YAXPEAU_IRP_CONTEXT@@JK@Z; RefsRaiseStatusInternal(_IRP_CONTEXT *,long,ulong)
0x140081460  int     3; Trap to Debugger
0x140081461  test    r12d, r12d
0x140081464  jns     loc_140081298
0x14008146a  mov     rcx, cs:WPP_GLOBAL_Control
0x140081471  lea     rax, WPP_GLOBAL_Control
0x140081478  cmp     rcx, rax
0x14008147b  jz      loc_1401F7C24
0x140081481  test    dword ptr [rcx+2Ch], 100h
0x140081488  jz      loc_1401F7C24
0x14008148e  cmp     byte ptr [rcx+29h], 4
0x140081492  jb      loc_1401F7C24
0x140081498  mov     rcx, [rcx+18h]
0x14008149c  lea     r8, WPP_31376ab3b8073048edfb14e725e449b5_Traceguids
0x1400814a3  mov     edx, 13h
0x1400814a8  mov     r9d, r12d
0x1400814ab  call    WPP_SF_d
0x1400814b0  nop
0x1400814b1  jmp     loc_1401F7C24
0x1400814b6  cmp     rcx, rdi
0x1400814b9  jz      loc_140081177
0x1400814bf  mov     r12d, 0C00001A1h
0x1400814c5  jmp     loc_14008142F
0x1400814ca  mov     rcx, rbx
0x1400814cd  call    FsLibPrivateInitializeRangeLock
0x1400814d2  mov     r12d, eax
0x1400814d5  test    eax, eax
0x1400814d7  js      loc_14008142F
0x1400814dd  mov     r14, [rbx]
0x1400814e0  jmp     loc_140081188
0x1400814e5  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400814ec  nop     dword ptr [rax+rax+00h]
0x1400814f1  lea     rdx, [rbp+47h+var_60]
0x1400814f5  cmp     [r14+18h], r12
0x1400814f9  jz      loc_1401F7B8B
0x1400814ff  xor     r8d, r8d
0x140081502  mov     rcx, r14
0x140081505  call    FsLibPrivateCheckFirstWaitingRangeLockForAccess
0x14008150a  test    al, al
0x14008150c  jz      short loc_140081517
0x14008150e  lea     rdx, [rbp+47h+var_60]
0x140081512  jmp     loc_1401F7B8B
0x140081517  lea     r9, [r15+20h]
0x14008151b  mov     r8d, 80000000h
0x140081521  mov     [rsp+0C0h+var_A0], r9
0x140081526  lea     rdx, [rbp+47h+var_60]
0x14008152a  lea     r9, [rbp+47h+LockHandle]
0x14008152e  mov     rcx, r14
0x140081531  call    FsLibInsertWaitingLock
0x140081536  mov     r12d, eax
0x140081539  jmp     loc_14008128F
0x14008153e  test    dword ptr [rcx+2Ch], 100h
0x140081545  jz      loc_140081446
0x14008154b  cmp     byte ptr [rcx+29h], 4
0x14008154f  jb      loc_140081446
0x140081555  mov     rcx, [rcx+18h]
0x140081559  lea     r8, WPP_31376ab3b8073048edfb14e725e449b5_Traceguids
0x140081560  mov     edx, 12h
0x140081565  mov     r9d, r12d
0x140081568  call    WPP_SF_d
0x14008156d  jmp     loc_140081446
0x140081572  mov     r9d, 0E54h; unsigned int
  ... truncated ...
```
