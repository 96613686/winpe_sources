# UxDuoAllocateStream

- ea: `0x1400688b0`
- end: `0x1400690e3`
- name: `UxDuoAllocateStream`
- size: `2099`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400680e0`
- `0x1400dcb70`

## callees

- `0x14000a350`
- `0x140049d28`
- `0x140051410`
- `0x140058540`
- `0x140064138`
- `0x1400688b0`
- `0x1400690f0`
- `0x1400a9b20`
- `0x1400dc288`
- `0x1401677e0`
- `0x140167b40`
- `0x1401d9f54`
- `0x1401da4fc`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140068918`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400689c1`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140068d0d`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140068918`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400689c1`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140068d0d`
- `ntoskrnl!KeSetCoalescableTimer` at `0x140068f9c`
- `ntoskrnl!KeSetCoalescableTimer` at `0x140068f9c`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140068fda`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14006900b`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14006903c`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140068fda`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14006900b`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14006903c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140068a77`
- `ntoskrnl!KeReleaseSpinLock` at `0x140068c86`
- `ntoskrnl!KeReleaseSpinLock` at `0x140068a77`
- `ntoskrnl!KeReleaseSpinLock` at `0x140068c86`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140068a31`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140068c56`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140068a31`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140068c56`
- `HAL!KeQueryPerformanceCounter` at `0x140068a91`
- `HAL!KeQueryPerformanceCounter` at `0x140068a91`
- `NETIO!RtlInitializeTimerWheelEntry` at `0x140068ca1`
- `NETIO!RtlInitializeTimerWheelEntry` at `0x140068ca1`

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
    *(_DWORD *)&v12[4 * v24 + 176] = *(_DWORD *)(v20 + 4LL * *((int *)qword_1401A3E28 + v24) + 4272);
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
0x1400688b0  push    rbx
0x1400688b2  push    rsi
0x1400688b3  push    rdi
0x1400688b4  push    r13
0x1400688b6  push    r14
0x1400688b8  sub     rsp, 60h
0x1400688bc  mov     qword ptr [r8], 0
0x1400688c3  mov     r13, r8
0x1400688c6  mov     edi, gs:1A4h
0x1400688ce  mov     rsi, rcx
0x1400688d1  cmp     cs:UxDebugDisableLookaside, 0
0x1400688d8  mov     [rsp+88h+var_40], r8
0x1400688dd  mov     [rsp+88h+var_48], edx
0x1400688e1  jnz     loc_140068EFC
0x1400688e7  cmp     cs:UxCompactMode, 0
0x1400688ee  jnz     loc_140068FD3
0x1400688f4  mov     rcx, cs:qword_1401A0790
0x1400688fb  lea     ebx, [rdi+1]
0x1400688fe  shl     rbx, 7
0x140068902  add     rbx, rcx
0x140068905  movzx   eax, byte ptr [rbx+0B0h]
0x14006890c  test    al, al
0x14006890e  jz      loc_140068FF6
0x140068914  lea     rcx, [rbx+40h]; Lookaside
0x140068918  call    cs:__imp_ExAllocateFromLookasideListEx
0x14006891f  nop     dword ptr [rax+rax+00h]
0x140068924  mov     [rsp+88h+arg_8], rbp
0x14006892c  mov     r14, rax
0x14006892f  mov     [rsp+88h+var_30], r12
0x140068934  mov     [rsp+88h+var_38], r15
0x140068939  test    rax, rax
0x14006893c  jz      loc_140068FB7
0x140068942  xor     edx, edx; Val
0x140068944  mov     r8d, 90h; Size
0x14006894a  mov     rcx, rax; void *
0x14006894d  call    memset
0x140068952  mov     [r14], edi
0x140068955  lea     rax, [r14+18h]
0x140068959  mov     dword ptr [r14+10h], 49597855h
0x140068961  mov     [rax+8], rax
0x140068965  mov     [rax], rax
0x140068968  lea     rax, UxDuoExecuteStreamCleanup
0x14006896f  mov     [r14+28h], rax
0x140068973  mov     dword ptr [r14+40h], 0
0x14006897b  mov     edi, gs:1A4h
0x140068983  cmp     cs:UxDebugDisableLookaside, 0
0x14006898a  jnz     loc_140068F24
0x140068990  cmp     cs:UxCompactMode, 0
0x140068997  jnz     loc_140069004
0x14006899d  mov     rcx, cs:qword_1401A0760
0x1400689a4  lea     ebx, [rdi+1]
0x1400689a7  shl     rbx, 7
0x1400689ab  add     rbx, rcx
0x1400689ae  movzx   eax, byte ptr [rbx+0B0h]
0x1400689b5  test    al, al
0x1400689b7  jz      loc_140069027
0x1400689bd  lea     rcx, [rbx+40h]; Lookaside
0x1400689c1  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400689c8  nop     dword ptr [rax+rax+00h]
0x1400689cd  mov     rbx, rax
0x1400689d0  test    rax, rax
0x1400689d3  jz      loc_140068FC1
0x1400689d9  xor     edx, edx; Val
0x1400689db  mov     r8d, 1E0h; Size
0x1400689e1  mov     rcx, rax; void *
0x1400689e4  call    memset
0x1400689e9  mov     ebp, 1
0x1400689ee  mov     [rbx], edi
0x1400689f0  mov     eax, ebp
0x1400689f2  mov     dword ptr [rbx+10h], 48597855h
0x1400689f9  lea     rdx, [rsi+4]; BugCheckParameter2
0x1400689fd  lock xadd [rdx], eax
0x140068a01  inc     eax
0x140068a03  cmp     cs:UxDebugCheckRefcount, 0
0x140068a0a  jnz     loc_140068AB4
0x140068a10  lea     rdi, [rsi+20h]
0x140068a14  mov     [rbx+30h], rsi
0x140068a18  cmp     [rdi], rdi
0x140068a1b  jnz     short loc_140068A88
0x140068a1d  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 8
0x140068a24  jnz     loc_140069066
0x140068a2a  lea     rcx, [rsi+4228h]; SpinLock
0x140068a31  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140068a38  nop     dword ptr [rax+rax+00h]
0x140068a3d  cmp     byte ptr [rsi+420Ch], 0
0x140068a44  movzx   r13d, al
0x140068a48  jz      short loc_140068A6C
0x140068a4a  mov     ecx, [rsi+4208h]
0x140068a50  test    bpl, cl
0x140068a53  jz      short loc_140068A6C
0x140068a55  test    byte ptr cs:xmmword_1401A2CA0+2, 8
0x140068a5c  jnz     loc_140069088
0x140068a62  mov     dword ptr [rsi+41D4h], 0
0x140068a6c  movzx   edx, r13b; NewIrql
0x140068a70  lea     rcx, [rsi+4228h]; SpinLock
0x140068a77  call    cs:__imp_KeReleaseSpinLock
0x140068a7e  nop     dword ptr [rax+rax+00h]
0x140068a83  mov     r13, [rsp+88h+var_40]
0x140068a88  mov     eax, [rsp+88h+var_48]
0x140068a8c  xor     ecx, ecx; PerformanceFrequency
0x140068a8e  mov     [rbx+58h], eax
0x140068a91  call    cs:__imp_KeQueryPerformanceCounter
0x140068a98  nop     dword ptr [rax+rax+00h]
0x140068a9d  mov     [rbx+1A0h], rax
0x140068aa4  mov     rcx, [rdi+8]
0x140068aa8  cmp     [rcx], rdi
0x140068aab  jz      short loc_140068AD1
0x140068aad  mov     ecx, 3
0x140068ab2  int     29h; Win8: RtlFailFast(ecx)
0x140068ab4  cmp     eax, 0FFFFFFFFh
0x140068ab7  jg      loc_140068A10
0x140068abd  movsxd  r9, eax; BugCheckParameter4
0x140068ac0  mov     ecx, 3; BugCheckParameter1
0x140068ac5  mov     r8d, 6; BugCheckParameter3
0x140068acb  call    UlBugCheckEx
0x140068ad1  mov     [rbx+40h], rcx
0x140068ad5  lea     rax, [rbx+38h]
0x140068ad9  mov     [rax], rdi
0x140068adc  mov     [rcx], rax
0x140068adf  mov     [rdi+8], rax
0x140068ae3  imul    ecx, [rbx+58h], 64E6Dh
0x140068aea  add     ecx, 3039h
0x140068af0  shr     rcx, 10h
0x140068af4  and     ecx, 0Fh
0x140068af7  add     rcx, 3
0x140068afb  shl     rcx, 4
0x140068aff  add     rcx, rsi
0x140068b02  mov     rdx, [rcx+8]
0x140068b06  cmp     [rdx], rcx
0x140068b09  jnz     short loc_140068AAD
0x140068b0b  mov     [rbx+48h], rcx
0x140068b0f  lea     rax, [rbx+48h]
0x140068b13  mov     [rax+8], rdx
0x140068b17  mov     [rdx], rax
0x140068b1a  mov     [rcx+8], rax
0x140068b1e  mov     eax, [rsi+13Ch]
0x140068b24  mov     [rbx+5Ch], eax
0x140068b27  lea     rax, [rbx+168h]
0x140068b2e  inc     dword ptr [rsi+13Ch]
0x140068b34  mov     [rbx+14h], ebp
0x140068b37  mov     [rax+8], rax
0x140068b3b  mov     [rax], rax
0x140068b3e  mov     eax, ebp
0x140068b40  mov     [rbx+100h], r14
0x140068b47  lock xadd [rbx+14h], eax
0x140068b4c  inc     eax
0x140068b4e  cmp     cs:UxDebugCheckRefcount, 0
0x140068b55  jnz     loc_140068EBA
0x140068b5b  mov     rax, [rbx+100h]
0x140068b62  mov     [rax+30h], rbx
0x140068b66  mov     eax, [rsi+4284h]
0x140068b6c  mov     [rbx+148h], eax
0x140068b72  mov     eax, [rsi+4284h]
0x140068b78  mov     [rbx+140h], eax
0x140068b7e  lea     rax, [rbx+118h]
0x140068b85  mov     [rax+8], rax
0x140068b89  mov     [rax], rax
0x140068b8c  mov     eax, [rsi+426Ch]
0x140068b92  mov     [rbx+128h], eax
0x140068b98  mov     r12, [rsi+4238h]
0x140068b9f  mov     r14, [rsi+4380h]
0x140068ba6  add     r12, 10h
0x140068baa  test    byte ptr cs:xmmword_1401A2CA0+2, 8
0x140068bb1  jnz     loc_1400690BC
0x140068bb7  xor     edx, edx; Val
0x140068bb9  lea     rcx, [rbx+68h]; void *
0x140068bbd  mov     r8d, 80h; Size
0x140068bc3  call    memset
0x140068bc8  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140068bd0  lea     rax, [rsi+4228h]
0x140068bd7  movups  xmmword ptr [rbx+0D0h], xmm0
0x140068bde  mov     [rbx+78h], rax
0x140068be2  xor     r8d, r8d
0x140068be5  mov     [rbx+70h], r12
0x140068be9  xor     eax, eax
0x140068beb  mov     [rbx+0CCh], bpl
0x140068bf2  mov     dword ptr [rbx+68h], 3
0x140068bf9  movzx   ecx, word ptr cs:UlTimersPerBundle+6
0x140068c00  cmp     ax, cx
0x140068c03  jnb     short loc_140068C34
0x140068c05  lea     r9, qword_1401A3E28
0x140068c0c  movzx   edx, r8w
0x140068c10  inc     r8w
0x140068c14  movsxd  rax, dword ptr [r9+rdx*4]
0x140068c18  mov     ecx, [r14+rax*4+10B0h]
0x140068c20  mov     [rbx+rdx*4+0B0h], ecx
0x140068c27  movzx   ecx, word ptr cs:UlTimersPerBundle+6
0x140068c2e  cmp     r8w, cx
0x140068c32  jb      short loc_140068C0C
0x140068c34  mov     eax, ebp
0x140068c36  shl     eax, cl
0x140068c38  dec     eax
0x140068c3a  mov     [rbx+0C8h], eax
0x140068c40  mov     eax, ebp
0x140068c42  lock xadd [r12+40h], eax
0x140068c49  inc     eax
0x140068c4b  cmp     eax, ebp
0x140068c4d  jnz     short loc_140068C92
0x140068c4f  lea     rcx, UlHotAddCommitLock; SpinLock
0x140068c56  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140068c5d  nop     dword ptr [rax+rax+00h]
0x140068c62  mov     ecx, cs:UlMetronomeCount
0x140068c68  movzx   edi, al
0x140068c6b  inc     ecx
0x140068c6d  mov     cs:UlMetronomeCount, ecx
0x140068c73  cmp     ecx, ebp
0x140068c75  jz      loc_140068E95
0x140068c7b  movzx   edx, dil; NewIrql
0x140068c7f  lea     rcx, UlHotAddCommitLock; SpinLock
0x140068c86  call    cs:__imp_KeReleaseSpinLock
0x140068c8d  nop     dword ptr [rax+rax+00h]
0x140068c92  lea     rdx, [rbx+80h]
0x140068c99  xor     r9d, r9d
0x140068c9c  xor     r8d, r8d
0x140068c9f  xor     ecx, ecx
0x140068ca1  call    cs:__imp_RtlInitializeTimerWheelEntry
0x140068ca8  nop     dword ptr [rax+rax+00h]
0x140068cad  xor     eax, eax
0x140068caf  xor     r12d, r12d
0x140068cb2  xorps   xmm0, xmm0
0x140068cb5  movups  xmmword ptr [rbx+18h], xmm0
0x140068cb9  mov     [rbx+28h], rax
0x140068cbd  mov     [rbx+28h], ebp
0x140068cc0  mov     [rbx+108h], r12
0x140068cc7  mov     r14d, gs:1A4h
0x140068cd0  cmp     cs:UxDebugDisableLookaside, al
0x140068cd6  jnz     loc_140068F4C
0x140068cdc  cmp     cs:UxCompactMode, al
0x140068ce2  jnz     loc_140069035
0x140068ce8  mov     rcx, cs:qword_1401A0790
0x140068cef  lea     edi, [r14+1]
0x140068cf3  shl     rdi, 7
0x140068cf7  add     rdi, rcx
0x140068cfa  movzx   eax, byte ptr [rdi+0B0h]
0x140068d01  test    al, al
0x140068d03  jz      loc_140069058
0x140068d09  lea     rcx, [rdi+40h]; Lookaside
0x140068d0d  call    cs:__imp_ExAllocateFromLookasideListEx
0x140068d14  nop     dword ptr [rax+rax+00h]
0x140068d19  mov     rdi, rax
0x140068d1c  test    rax, rax
0x140068d1f  jz      loc_140068FAD
0x140068d25  xor     edx, edx; Val
0x140068d27  mov     r8d, 90h; Size
0x140068d2d  mov     rcx, rax; void *
0x140068d30  call    memset
0x140068d35  mov     [rdi], r14d
0x140068d38  lea     rax, [rdi+18h]
0x140068d3c  mov     dword ptr [rdi+10h], 49597855h
0x140068d43  mov     [rax+8], rax
0x140068d47  mov     [rax], rax
0x140068d4a  lea     rax, UxDuoExecuteKillStream
0x140068d51  mov     [rdi+28h], rax
0x140068d55  mov     dword ptr [rdi+40h], 6
0x140068d5c  lock xadd [rbx+14h], ebp
0x140068d61  inc     ebp
0x140068d63  cmp     cs:UxDebugCheckRefcount, r12b
0x140068d6a  jnz     loc_140068EDB
0x140068d70  mov     [rdi+30h], rbx
0x140068d74  mov     [rbx+108h], rdi
0x140068d7b  mov     rcx, [rsi+43D0h]
0x140068d82  mov     rdx, [rsi+4380h]
0x140068d89  mov     r8d, [rdx+1BF8h]
0x140068d90  add     r8, rcx
0x140068d93  cmp     r8, rcx
0x140068d96  jnb     short loc_140068DD1
0x140068d98  mov     qword ptr [rsi+43D0h], 0FFFFFFFFFFFFFFFFh
0x140068da3  mov     edi, 0C0000095h
0x140068da8  mov     rcx, rbx
0x140068dab  call    UxDuoCleanupStream
0x140068db0  mov     r15, [rsp+88h+var_38]
0x140068db5  mov     eax, edi
0x140068db7  mov     r12, [rsp+88h+var_30]
0x140068dbc  mov     rbp, [rsp+88h+arg_8]
0x140068dc4  add     rsp, 60h
0x140068dc8  pop     r14
0x140068dca  pop     r13
0x140068dcc  pop     rdi
0x140068dcd  pop     rsi
0x140068dce  pop     rbx
0x140068dcf  retn
0x140068dd1  mov     [rsi+43D0h], r8
0x140068dd8  mov     rcx, [rsi+43E0h]
0x140068ddf  mov     r8d, [rdx+1BFCh]
0x140068de6  add     r8, rcx
0x140068de9  cmp     r8, rcx
0x140068dec  jb      loc_140068E80
0x140068df2  mov     [rsi+43E0h], r8
0x140068df9  mov     rcx, [rsi+43F0h]
0x140068e00  mov     r8d, [rdx+1C00h]
0x140068e07  add     r8, rcx
0x140068e0a  cmp     r8, rcx
0x140068e0d  jb      short loc_140068E6B
0x140068e0f  mov     [rsi+43F0h], r8
0x140068e16  mov     rcx, [rsi+43B0h]
0x140068e1d  mov     edx, [rdx+1C28h]
0x140068e23  add     rdx, rcx
0x140068e26  cmp     rdx, rcx
0x140068e29  jb      short loc_140068E56
0x140068e2b  mov     [rsi+43B0h], rdx
  ... truncated ...
```
