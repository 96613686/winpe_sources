# UxDuoAllocateStream

- ea: `0x140068890`
- end: `0x1400690c3`
- name: `UxDuoAllocateStream`
- size: `2099`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400680c0`
- `0x1400dcac0`

## callees

- `0x14000a350`
- `0x140049d08`
- `0x1400513f0`
- `0x140058520`
- `0x140064118`
- `0x140068890`
- `0x1400690d0`
- `0x1400a9b00`
- `0x1400dc1d8`
- `0x1401678f0`
- `0x140167c40`
- `0x1401d9f54`
- `0x1401da4fc`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400688f8`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400689a1`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140068ced`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400688f8`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400689a1`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140068ced`
- `ntoskrnl!KeSetCoalescableTimer` at `0x140068f7c`
- `ntoskrnl!KeSetCoalescableTimer` at `0x140068f7c`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140068fba`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140068feb`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14006901c`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140068fba`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140068feb`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14006901c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140068a57`
- `ntoskrnl!KeReleaseSpinLock` at `0x140068c66`
- `ntoskrnl!KeReleaseSpinLock` at `0x140068a57`
- `ntoskrnl!KeReleaseSpinLock` at `0x140068c66`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140068a11`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140068c36`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140068a11`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140068c36`
- `HAL!KeQueryPerformanceCounter` at `0x140068a71`
- `HAL!KeQueryPerformanceCounter` at `0x140068a71`
- `NETIO!RtlInitializeTimerWheelEntry` at `0x140068c81`
- `NETIO!RtlInitializeTimerWheelEntry` at `0x140068c81`

## pseudocode

```c
__int64 __fastcall UxDuoAllocateStream(__int64 a1, int a2, _QWORD *a3)
{
  _QWORD *v3; // r13
  int LockArray_high; // edi
  unsigned __int64 v6; // rbx
  _DWORD *v7; // rax
  _DWORD *v8; // r14
  int v9; // edi
  unsigned __int64 v10; // rbx
  char *v11; // rax
  char *v12; // rbx
  int v13; // eax
  _QWORD *v14; // rdi
  KIRQL v15; // r13
  _QWORD *v16; // rcx
  __int64 v17; // rcx
  _QWORD *v18; // rdx
  int v19; // eax
  __int64 v20; // r14
  __int64 v21; // r12
  unsigned __int16 v22; // r8
  char i; // cl
  __int64 v24; // rdx
  KIRQL v25; // di
  int v26; // r14d
  unsigned __int64 v27; // rdi
  _DWORD *v28; // rax
  _DWORD *v29; // rdi
  int v30; // ebp
  unsigned __int64 v31; // rcx
  unsigned int *v32; // rdx
  unsigned __int64 v33; // r8
  unsigned int v34; // edi
  unsigned __int64 v36; // rcx
  unsigned __int64 v37; // r8
  unsigned __int64 v38; // rcx
  unsigned __int64 v39; // r8
  unsigned __int64 v40; // rcx
  unsigned __int64 v41; // rdx
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // rbx
  USHORT CurrentNodeNumber; // ax
  __int64 v46; // rbx
  USHORT v47; // ax
  __int64 v48; // rdi
  USHORT v49; // ax
  int v50; // [rsp+40h] [rbp-48h]

  *a3 = 0;
  v3 = a3;
  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  v50 = a2;
  if ( UxDebugDisableLookaside )
  {
    v7 = (_DWORD *)((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A07B0)(
                     (unsigned int)dword_1401A0798,
                     qword_1401A07A0,
                     (unsigned int)dword_1401A07A8,
                     0);
  }
  else if ( UxCompactMode )
  {
    v44 = qword_1401A0790;
    CurrentNodeNumber = KeGetCurrentNodeNumber();
    v7 = (_DWORD *)PplAllocateFromLookasideListProcessor(v44, CurrentNodeNumber);
  }
  else
  {
    v6 = qword_1401A0790 + ((unsigned __int64)(unsigned int)(LockArray_high + 1) << 7);
    if ( !*(_BYTE *)(v6 + 176) )
      PplpLazyInitializeLookasideList(qword_1401A0790, v6 + 64);
    v7 = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v6 + 64));
  }
  v8 = v7;
  if ( !v7 )
    return (unsigned int)-1073741670;
  memset(v7, 0, 0x90u);
  *v8 = LockArray_high;
  v8[4] = 1230600277;
  *((_QWORD *)v8 + 4) = v8 + 6;
  *((_QWORD *)v8 + 3) = v8 + 6;
  *((_QWORD *)v8 + 5) = UxDuoExecuteStreamCleanup;
  v8[16] = 0;
  v9 = HIDWORD(KeGetPcr()[1].LockArray);
  if ( UxDebugDisableLookaside )
  {
    v11 = (char *)((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A0780)(
                    (unsigned int)dword_1401A0768,
                    qword_1401A0770,
                    (unsigned int)dword_1401A0778,
                    0);
  }
  else if ( UxCompactMode )
  {
    v46 = qword_1401A0760;
    v47 = KeGetCurrentNodeNumber();
    v11 = (char *)PplAllocateFromLookasideListProcessor(v46, v47);
  }
  else
  {
    v10 = qword_1401A0760 + ((unsigned __int64)(unsigned int)(v9 + 1) << 7);
    if ( !*(_BYTE *)(v10 + 176) )
      PplpLazyInitializeLookasideList(qword_1401A0760, v10 + 64);
    v11 = (char *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v10 + 64));
  }
  v12 = v11;
  if ( !v11 )
  {
    v34 = -1073741670;
    UxDuoFreeTask(v8);
    return v34;
  }
  memset(v11, 0, 0x1E0u);
  *(_DWORD *)v12 = v9;
  *((_DWORD *)v12 + 4) = 1213823061;
  v13 = _InterlockedIncrement((volatile signed __int32 *)(a1 + 4));
  if ( UxDebugCheckRefcount && v13 <= -1 )
    UlBugCheckEx(3u, a1 + 4, 6u, v13);
  v14 = (_QWORD *)(a1 + 32);
  *((_QWORD *)v12 + 6) = a1;
  if ( (_QWORD *)*v14 == v14 )
  {
    if ( (BYTE11(xmmword_1401A2CA0) & 8) != 0 )
      WPP_SF_d(1307, 22, WPP_03a57f2472ee35d9a08fe2d0d8024514_Traceguids, *(unsigned int *)(a1 + 17232));
    v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 16936));
    if ( *(_BYTE *)(a1 + 16908) && (*(_DWORD *)(a1 + 16904) & 1) != 0 )
    {
      if ( (BYTE2(xmmword_1401A2CA0) & 8) != 0 )
        WPP_SF_qLd(1043, 16, WPP_94ca9e589e4f3da486b24c2e49372186_Traceguids, a1 + 16808, *(_DWORD *)(a1 + 16808), 14);
      *(_DWORD *)(a1 + 16852) = 0;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 16936), v15);
    v3 = a3;
  }
  *((_DWORD *)v12 + 22) = v50;
  *((LARGE_INTEGER *)v12 + 52) = KeQueryPerformanceCounter(0);
  v16 = *(_QWORD **)(a1 + 40);
  if ( (_QWORD *)*v16 != v14
    || (*((_QWORD *)v12 + 8) = v16,
        *((_QWORD *)v12 + 7) = v14,
        *v16 = v12 + 56,
        *(_QWORD *)(a1 + 40) = v12 + 56,
        v17 = a1 + 16 * ((((unsigned int)(413293 * *((_DWORD *)v12 + 22) + 12345) >> 16) & 0xF) + 3LL),
        v18 = *(_QWORD **)(v17 + 8),
        *v18 != v17) )
  {
    __fastfail(3u);
  }
  *((_QWORD *)v12 + 9) = v17;
  *((_QWORD *)v12 + 10) = v18;
  *v18 = v12 + 72;
  *(_QWORD *)(v17 + 8) = v12 + 72;
  *((_DWORD *)v12 + 23) = (*(_DWORD *)(a1 + 316))++;
  *((_DWORD *)v12 + 5) = 1;
  *((_QWORD *)v12 + 46) = v12 + 360;
  *((_QWORD *)v12 + 45) = v12 + 360;
  *((_QWORD *)v12 + 32) = v8;
  v19 = _InterlockedIncrement((volatile signed __int32 *)v12 + 5);
  if ( UxDebugCheckRefcount && v19 <= -1 )
    UlBugCheckEx(3u, (ULONG_PTR)(v12 + 20), 0x2Cu, v19);
  *(_QWORD *)(*((_QWORD *)v12 + 32) + 48LL) = v12;
  *((_DWORD *)v12 + 82) = *(_DWORD *)(a1 + 17028);
  *((_DWORD *)v12 + 80) = *(_DWORD *)(a1 + 17028);
  *((_QWORD *)v12 + 36) = v12 + 280;
  *((_QWORD *)v12 + 35) = v12 + 280;
  *((_DWORD *)v12 + 74) = *(_DWORD *)(a1 + 17004);
  v20 = *(_QWORD *)(a1 + 17280);
  v21 = *(_QWORD *)(a1 + 16952) + 16LL;
  if ( (BYTE2(xmmword_1401A2CA0) & 8) != 0 )
    WPP_SF_qD(1043, 12, WPP_94ca9e589e4f3da486b24c2e49372186_Traceguids, v12 + 104, 3);
  memset(v12 + 104, 0, 0x80u);
  *((__m128i *)v12 + 13) = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  *((_QWORD *)v12 + 15) = a1 + 16936;
  v22 = 0;
  *((_QWORD *)v12 + 14) = v21;
  v12[204] = 1;
  *((_DWORD *)v12 + 26) = 3;
  for ( i = BYTE6(UlTimersPerBundle); v22 < WORD3(UlTimersPerBundle); i = BYTE6(UlTimersPerBundle) )
  {
    v24 = v22++;
    *(_DWORD *)&v12[4 * v24 + 176] = *(_DWORD *)(v20 + 4LL * *((int *)qword_1401A3DE8 + v24) + 4272);
  }
  *((_DWORD *)v12 + 50) = (1 << i) - 1;
  if ( _InterlockedIncrement((volatile signed __int32 *)(v21 + 64)) == 1 )
  {
    v25 = KeAcquireSpinLockRaiseToDpc(&UlHotAddCommitLock);
    if ( ++UlMetronomeCount != 1 )
    {
LABEL_35:
      KeReleaseSpinLock(&UlHotAddCommitLock, v25);
      goto LABEL_36;
    }
    if ( UlMetronomeState )
    {
      if ( UlMetronomeState != 1 )
        goto LABEL_35;
    }
    else
    {
      UlpResumeTimerWheels();
      KeSetCoalescableTimer(&UlMetronomeTimer, (LARGE_INTEGER)-50000000LL, 0, 0x1F4u, &UlMetronomeDpc);
    }
    UlMetronomeState = 2;
    goto LABEL_35;
  }
LABEL_36:
  RtlInitializeTimerWheelEntry(0, v12 + 128, 0, 0);
  *(_OWORD *)(v12 + 24) = 0;
  *((_QWORD *)v12 + 5) = 0;
  *((_DWORD *)v12 + 10) = 1;
  *((_QWORD *)v12 + 33) = 0;
  v26 = HIDWORD(KeGetPcr()[1].LockArray);
  if ( UxDebugDisableLookaside )
  {
    v28 = (_DWORD *)((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A07B0)(
                      (unsigned int)dword_1401A0798,
                      qword_1401A07A0,
                      (unsigned int)dword_1401A07A8,
                      0);
  }
  else if ( UxCompactMode )
  {
    v48 = qword_1401A0790;
    v49 = KeGetCurrentNodeNumber();
    v28 = (_DWORD *)PplAllocateFromLookasideListProcessor(v48, v49);
  }
  else
  {
    v27 = qword_1401A0790 + ((unsigned __int64)(unsigned int)(v26 + 1) << 7);
    if ( !*(_BYTE *)(v27 + 176) )
      PplpLazyInitializeLookasideList(qword_1401A0790, v27 + 64);
    v28 = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v27 + 64));
  }
  v29 = v28;
  if ( !v28 )
  {
    v34 = -1073741670;
    goto LABEL_45;
  }
  memset(v28, 0, 0x90u);
  *v29 = v26;
  v29[4] = 1230600277;
  *((_QWORD *)v29 + 4) = v29 + 6;
  *((_QWORD *)v29 + 3) = v29 + 6;
  *((_QWORD *)v29 + 5) = UxDuoExecuteKillStream;
  v29[16] = 6;
  v30 = _InterlockedIncrement((volatile signed __int32 *)v12 + 5);
  if ( UxDebugCheckRefcount && v30 <= -1 )
    UlBugCheckEx(3u, (ULONG_PTR)(v12 + 20), 0x2Cu, v30);
  *((_QWORD *)v29 + 6) = v12;
  *((_QWORD *)v12 + 33) = v29;
  v31 = *(_QWORD *)(a1 + 17360);
  v32 = *(unsigned int **)(a1 + 17280);
  v33 = v31 + v32[1790];
  if ( v33 < v31 )
  {
    *(_QWORD *)(a1 + 17360) = -1;
    v34 = -1073741675;
LABEL_45:
    UxDuoCleanupStream(v12);
    return v34;
  }
  *(_QWORD *)(a1 + 17360) = v33;
  v36 = *(_QWORD *)(a1 + 17376);
  v37 = v36 + v32[1791];
  if ( v37 < v36 )
  {
    *(_QWORD *)(a1 + 17376) = -1;
    v34 = -1073741675;
    goto LABEL_45;
  }
  *(_QWORD *)(a1 + 17376) = v37;
  v38 = *(_QWORD *)(a1 + 17392);
  v39 = v38 + v32[1792];
  if ( v39 < v38 )
  {
    *(_QWORD *)(a1 + 17392) = -1;
    v34 = -1073741675;
    goto LABEL_45;
  }
  *(_QWORD *)(a1 + 17392) = v39;
  v40 = *(_QWORD *)(a1 + 17328);
  v41 = v40 + v32[1802];
  if ( v41 < v40 )
  {
    *(_QWORD *)(a1 + 17328) = -1;
    v34 = -1073741675;
    goto LABEL_45;
  }
  *(_QWORD *)(a1 + 17328) = v41;
  v34 = 0;
  v42 = *((_QWORD *)v12 + 6);
  v43 = *(_QWORD *)(v42 + 17280);
  if ( (*(_BYTE *)(v43 + 1765) & 0x20) != 0
    && (!*(_QWORD *)(v43 + 1776)
     || (unsigned __int8)UlEtwEvaluateFilter(
                           v43,
                           v42 + 17472,
                           v42 + 17500,
                           0,
                           *((_QWORD *)v12 + 43),
                           *((unsigned __int16 *)v12 + 168),
                           0,
                           0,
                           v50)) )
  {
    McTemplateK0pxq_EtwWriteTransfer(
      *(_QWORD *)(*((_QWORD *)v12 + 6) + 17280LL) + 1688,
      *(_DWORD *)(a1 + 17232),
      v39,
      a1,
      *(_DWORD *)(a1 + 17232),
      v50);
  }
  *v3 = v12;
  return v34;
}

```

## disassembly

```asm
0x140068890  push    rbx
0x140068892  push    rsi
0x140068893  push    rdi
0x140068894  push    r13
0x140068896  push    r14
0x140068898  sub     rsp, 60h
0x14006889c  mov     qword ptr [r8], 0
0x1400688a3  mov     r13, r8
0x1400688a6  mov     edi, gs:1A4h
0x1400688ae  mov     rsi, rcx
0x1400688b1  cmp     cs:UxDebugDisableLookaside, 0
0x1400688b8  mov     [rsp+88h+var_40], r8
0x1400688bd  mov     [rsp+88h+var_48], edx
0x1400688c1  jnz     loc_140068EDC
0x1400688c7  cmp     cs:UxCompactMode, 0
0x1400688ce  jnz     loc_140068FB3
0x1400688d4  mov     rcx, cs:qword_1401A0790
0x1400688db  lea     ebx, [rdi+1]
0x1400688de  shl     rbx, 7
0x1400688e2  add     rbx, rcx
0x1400688e5  movzx   eax, byte ptr [rbx+0B0h]
0x1400688ec  test    al, al
0x1400688ee  jz      loc_140068FD6
0x1400688f4  lea     rcx, [rbx+40h]; Lookaside
0x1400688f8  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400688ff  nop     dword ptr [rax+rax+00h]
0x140068904  mov     [rsp+88h+arg_8], rbp
0x14006890c  mov     r14, rax
0x14006890f  mov     [rsp+88h+var_30], r12
0x140068914  mov     [rsp+88h+var_38], r15
0x140068919  test    rax, rax
0x14006891c  jz      loc_140068F97
0x140068922  xor     edx, edx; Val
0x140068924  mov     r8d, 90h; Size
0x14006892a  mov     rcx, rax; void *
0x14006892d  call    memset
0x140068932  mov     [r14], edi
0x140068935  lea     rax, [r14+18h]
0x140068939  mov     dword ptr [r14+10h], 49597855h
0x140068941  mov     [rax+8], rax
0x140068945  mov     [rax], rax
0x140068948  lea     rax, UxDuoExecuteStreamCleanup
0x14006894f  mov     [r14+28h], rax
0x140068953  mov     dword ptr [r14+40h], 0
0x14006895b  mov     edi, gs:1A4h
0x140068963  cmp     cs:UxDebugDisableLookaside, 0
0x14006896a  jnz     loc_140068F04
0x140068970  cmp     cs:UxCompactMode, 0
0x140068977  jnz     loc_140068FE4
0x14006897d  mov     rcx, cs:qword_1401A0760
0x140068984  lea     ebx, [rdi+1]
0x140068987  shl     rbx, 7
0x14006898b  add     rbx, rcx
0x14006898e  movzx   eax, byte ptr [rbx+0B0h]
0x140068995  test    al, al
0x140068997  jz      loc_140069007
0x14006899d  lea     rcx, [rbx+40h]; Lookaside
0x1400689a1  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400689a8  nop     dword ptr [rax+rax+00h]
0x1400689ad  mov     rbx, rax
0x1400689b0  test    rax, rax
0x1400689b3  jz      loc_140068FA1
0x1400689b9  xor     edx, edx; Val
0x1400689bb  mov     r8d, 1E0h; Size
0x1400689c1  mov     rcx, rax; void *
0x1400689c4  call    memset
0x1400689c9  mov     ebp, 1
0x1400689ce  mov     [rbx], edi
0x1400689d0  mov     eax, ebp
0x1400689d2  mov     dword ptr [rbx+10h], 48597855h
0x1400689d9  lea     rdx, [rsi+4]; BugCheckParameter2
0x1400689dd  lock xadd [rdx], eax
0x1400689e1  inc     eax
0x1400689e3  cmp     cs:UxDebugCheckRefcount, 0
0x1400689ea  jnz     loc_140068A94
0x1400689f0  lea     rdi, [rsi+20h]
0x1400689f4  mov     [rbx+30h], rsi
0x1400689f8  cmp     [rdi], rdi
0x1400689fb  jnz     short loc_140068A68
0x1400689fd  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 8
0x140068a04  jnz     loc_140069046
0x140068a0a  lea     rcx, [rsi+4228h]; SpinLock
0x140068a11  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140068a18  nop     dword ptr [rax+rax+00h]
0x140068a1d  cmp     byte ptr [rsi+420Ch], 0
0x140068a24  movzx   r13d, al
0x140068a28  jz      short loc_140068A4C
0x140068a2a  mov     ecx, [rsi+4208h]
0x140068a30  test    bpl, cl
0x140068a33  jz      short loc_140068A4C
0x140068a35  test    byte ptr cs:xmmword_1401A2CA0+2, 8
0x140068a3c  jnz     loc_140069068
0x140068a42  mov     dword ptr [rsi+41D4h], 0
0x140068a4c  movzx   edx, r13b; NewIrql
0x140068a50  lea     rcx, [rsi+4228h]; SpinLock
0x140068a57  call    cs:__imp_KeReleaseSpinLock
0x140068a5e  nop     dword ptr [rax+rax+00h]
0x140068a63  mov     r13, [rsp+88h+var_40]
0x140068a68  mov     eax, [rsp+88h+var_48]
0x140068a6c  xor     ecx, ecx; PerformanceFrequency
0x140068a6e  mov     [rbx+58h], eax
0x140068a71  call    cs:__imp_KeQueryPerformanceCounter
0x140068a78  nop     dword ptr [rax+rax+00h]
0x140068a7d  mov     [rbx+1A0h], rax
0x140068a84  mov     rcx, [rdi+8]
0x140068a88  cmp     [rcx], rdi
0x140068a8b  jz      short loc_140068AB1
0x140068a8d  mov     ecx, 3
0x140068a92  int     29h; Win8: RtlFailFast(ecx)
0x140068a94  cmp     eax, 0FFFFFFFFh
0x140068a97  jg      loc_1400689F0
0x140068a9d  movsxd  r9, eax; BugCheckParameter4
0x140068aa0  mov     ecx, 3; BugCheckParameter1
0x140068aa5  mov     r8d, 6; BugCheckParameter3
0x140068aab  call    UlBugCheckEx
0x140068ab1  mov     [rbx+40h], rcx
0x140068ab5  lea     rax, [rbx+38h]
0x140068ab9  mov     [rax], rdi
0x140068abc  mov     [rcx], rax
0x140068abf  mov     [rdi+8], rax
0x140068ac3  imul    ecx, [rbx+58h], 64E6Dh
0x140068aca  add     ecx, 3039h
0x140068ad0  shr     rcx, 10h
0x140068ad4  and     ecx, 0Fh
0x140068ad7  add     rcx, 3
0x140068adb  shl     rcx, 4
0x140068adf  add     rcx, rsi
0x140068ae2  mov     rdx, [rcx+8]
0x140068ae6  cmp     [rdx], rcx
0x140068ae9  jnz     short loc_140068A8D
0x140068aeb  mov     [rbx+48h], rcx
0x140068aef  lea     rax, [rbx+48h]
0x140068af3  mov     [rax+8], rdx
0x140068af7  mov     [rdx], rax
0x140068afa  mov     [rcx+8], rax
0x140068afe  mov     eax, [rsi+13Ch]
0x140068b04  mov     [rbx+5Ch], eax
0x140068b07  lea     rax, [rbx+168h]
0x140068b0e  inc     dword ptr [rsi+13Ch]
0x140068b14  mov     [rbx+14h], ebp
0x140068b17  mov     [rax+8], rax
0x140068b1b  mov     [rax], rax
0x140068b1e  mov     eax, ebp
0x140068b20  mov     [rbx+100h], r14
0x140068b27  lock xadd [rbx+14h], eax
0x140068b2c  inc     eax
0x140068b2e  cmp     cs:UxDebugCheckRefcount, 0
0x140068b35  jnz     loc_140068E9A
0x140068b3b  mov     rax, [rbx+100h]
0x140068b42  mov     [rax+30h], rbx
0x140068b46  mov     eax, [rsi+4284h]
0x140068b4c  mov     [rbx+148h], eax
0x140068b52  mov     eax, [rsi+4284h]
0x140068b58  mov     [rbx+140h], eax
0x140068b5e  lea     rax, [rbx+118h]
0x140068b65  mov     [rax+8], rax
0x140068b69  mov     [rax], rax
0x140068b6c  mov     eax, [rsi+426Ch]
0x140068b72  mov     [rbx+128h], eax
0x140068b78  mov     r12, [rsi+4238h]
0x140068b7f  mov     r14, [rsi+4380h]
0x140068b86  add     r12, 10h
0x140068b8a  test    byte ptr cs:xmmword_1401A2CA0+2, 8
0x140068b91  jnz     loc_14006909C
0x140068b97  xor     edx, edx; Val
0x140068b99  lea     rcx, [rbx+68h]; void *
0x140068b9d  mov     r8d, 80h; Size
0x140068ba3  call    memset
0x140068ba8  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140068bb0  lea     rax, [rsi+4228h]
0x140068bb7  movups  xmmword ptr [rbx+0D0h], xmm0
0x140068bbe  mov     [rbx+78h], rax
0x140068bc2  xor     r8d, r8d
0x140068bc5  mov     [rbx+70h], r12
0x140068bc9  xor     eax, eax
0x140068bcb  mov     [rbx+0CCh], bpl
0x140068bd2  mov     dword ptr [rbx+68h], 3
0x140068bd9  movzx   ecx, word ptr cs:UlTimersPerBundle+6
0x140068be0  cmp     ax, cx
0x140068be3  jnb     short loc_140068C14
0x140068be5  lea     r9, qword_1401A3DE8
0x140068bec  movzx   edx, r8w
0x140068bf0  inc     r8w
0x140068bf4  movsxd  rax, dword ptr [r9+rdx*4]
0x140068bf8  mov     ecx, [r14+rax*4+10B0h]
0x140068c00  mov     [rbx+rdx*4+0B0h], ecx
0x140068c07  movzx   ecx, word ptr cs:UlTimersPerBundle+6
0x140068c0e  cmp     r8w, cx
0x140068c12  jb      short loc_140068BEC
0x140068c14  mov     eax, ebp
0x140068c16  shl     eax, cl
0x140068c18  dec     eax
0x140068c1a  mov     [rbx+0C8h], eax
0x140068c20  mov     eax, ebp
0x140068c22  lock xadd [r12+40h], eax
0x140068c29  inc     eax
0x140068c2b  cmp     eax, ebp
0x140068c2d  jnz     short loc_140068C72
0x140068c2f  lea     rcx, UlHotAddCommitLock; SpinLock
0x140068c36  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140068c3d  nop     dword ptr [rax+rax+00h]
0x140068c42  mov     ecx, cs:UlMetronomeCount
0x140068c48  movzx   edi, al
0x140068c4b  inc     ecx
0x140068c4d  mov     cs:UlMetronomeCount, ecx
0x140068c53  cmp     ecx, ebp
0x140068c55  jz      loc_140068E75
0x140068c5b  movzx   edx, dil; NewIrql
0x140068c5f  lea     rcx, UlHotAddCommitLock; SpinLock
0x140068c66  call    cs:__imp_KeReleaseSpinLock
0x140068c6d  nop     dword ptr [rax+rax+00h]
0x140068c72  lea     rdx, [rbx+80h]
0x140068c79  xor     r9d, r9d
0x140068c7c  xor     r8d, r8d
0x140068c7f  xor     ecx, ecx
0x140068c81  call    cs:__imp_RtlInitializeTimerWheelEntry
0x140068c88  nop     dword ptr [rax+rax+00h]
0x140068c8d  xor     eax, eax
0x140068c8f  xor     r12d, r12d
0x140068c92  xorps   xmm0, xmm0
0x140068c95  movups  xmmword ptr [rbx+18h], xmm0
0x140068c99  mov     [rbx+28h], rax
0x140068c9d  mov     [rbx+28h], ebp
0x140068ca0  mov     [rbx+108h], r12
0x140068ca7  mov     r14d, gs:1A4h
0x140068cb0  cmp     cs:UxDebugDisableLookaside, al
0x140068cb6  jnz     loc_140068F2C
0x140068cbc  cmp     cs:UxCompactMode, al
0x140068cc2  jnz     loc_140069015
0x140068cc8  mov     rcx, cs:qword_1401A0790
0x140068ccf  lea     edi, [r14+1]
0x140068cd3  shl     rdi, 7
0x140068cd7  add     rdi, rcx
0x140068cda  movzx   eax, byte ptr [rdi+0B0h]
0x140068ce1  test    al, al
0x140068ce3  jz      loc_140069038
0x140068ce9  lea     rcx, [rdi+40h]; Lookaside
0x140068ced  call    cs:__imp_ExAllocateFromLookasideListEx
0x140068cf4  nop     dword ptr [rax+rax+00h]
0x140068cf9  mov     rdi, rax
0x140068cfc  test    rax, rax
0x140068cff  jz      loc_140068F8D
0x140068d05  xor     edx, edx; Val
0x140068d07  mov     r8d, 90h; Size
0x140068d0d  mov     rcx, rax; void *
0x140068d10  call    memset
0x140068d15  mov     [rdi], r14d
0x140068d18  lea     rax, [rdi+18h]
0x140068d1c  mov     dword ptr [rdi+10h], 49597855h
0x140068d23  mov     [rax+8], rax
0x140068d27  mov     [rax], rax
0x140068d2a  lea     rax, UxDuoExecuteKillStream
0x140068d31  mov     [rdi+28h], rax
0x140068d35  mov     dword ptr [rdi+40h], 6
0x140068d3c  lock xadd [rbx+14h], ebp
0x140068d41  inc     ebp
0x140068d43  cmp     cs:UxDebugCheckRefcount, r12b
0x140068d4a  jnz     loc_140068EBB
0x140068d50  mov     [rdi+30h], rbx
0x140068d54  mov     [rbx+108h], rdi
0x140068d5b  mov     rcx, [rsi+43D0h]
0x140068d62  mov     rdx, [rsi+4380h]
0x140068d69  mov     r8d, [rdx+1BF8h]
0x140068d70  add     r8, rcx
0x140068d73  cmp     r8, rcx
0x140068d76  jnb     short loc_140068DB1
0x140068d78  mov     qword ptr [rsi+43D0h], 0FFFFFFFFFFFFFFFFh
0x140068d83  mov     edi, 0C0000095h
0x140068d88  mov     rcx, rbx
0x140068d8b  call    UxDuoCleanupStream
0x140068d90  mov     r15, [rsp+88h+var_38]
0x140068d95  mov     eax, edi
0x140068d97  mov     r12, [rsp+88h+var_30]
0x140068d9c  mov     rbp, [rsp+88h+arg_8]
0x140068da4  add     rsp, 60h
0x140068da8  pop     r14
0x140068daa  pop     r13
0x140068dac  pop     rdi
0x140068dad  pop     rsi
0x140068dae  pop     rbx
0x140068daf  retn
0x140068db1  mov     [rsi+43D0h], r8
0x140068db8  mov     rcx, [rsi+43E0h]
0x140068dbf  mov     r8d, [rdx+1BFCh]
0x140068dc6  add     r8, rcx
0x140068dc9  cmp     r8, rcx
0x140068dcc  jb      loc_140068E60
0x140068dd2  mov     [rsi+43E0h], r8
0x140068dd9  mov     rcx, [rsi+43F0h]
0x140068de0  mov     r8d, [rdx+1C00h]
0x140068de7  add     r8, rcx
0x140068dea  cmp     r8, rcx
0x140068ded  jb      short loc_140068E4B
0x140068def  mov     [rsi+43F0h], r8
0x140068df6  mov     rcx, [rsi+43B0h]
0x140068dfd  mov     edx, [rdx+1C28h]
0x140068e03  add     rdx, rcx
0x140068e06  cmp     rdx, rcx
0x140068e09  jb      short loc_140068E36
0x140068e0b  mov     [rsi+43B0h], rdx
  ... truncated ...
```
