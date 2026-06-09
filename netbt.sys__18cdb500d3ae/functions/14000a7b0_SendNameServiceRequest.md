# SendNameServiceRequest

- ea: `0x14000a7b0`
- end: `0x14000b2e6`
- name: `SendNameServiceRequest`
- size: `2870`
- prototype: ``
- caller_count: `10`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x140006e2c`
- `0x140009844`
- `0x140009ee0`
- `0x14000c570`
- `0x14000cca0`
- `0x14000d310`
- `0x14000e408`
- `0x140019870`
- `0x140019a10`
- `0x140028580`

## callees

- `0x140005fb0`
- `0x140006900`
- `0x14000a7b0`
- `0x14000b464`
- `0x14000b540`
- `0x14000b810`
- `0x14000bdfc`
- `0x14000be64`
- `0x140030f80`
- `0x140031140`
- `0x140031440`
- `0x1400400a4`
- `0x140040294`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x14000b0e6`
- `ntoskrnl!KeCancelTimer` at `0x14000b0e6`
- `ntoskrnl!KeInitializeDpc` at `0x14000ae23`
- `ntoskrnl!KeInitializeDpc` at `0x14000ae23`
- `ntoskrnl!KeSetCoalescableTimer` at `0x14000ae6c`
- `ntoskrnl!KeSetCoalescableTimer` at `0x14000ae6c`
- `ntoskrnl!KeSetTimer` at `0x14000b07e`
- `ntoskrnl!KeSetTimer` at `0x14000b07e`
- `ntoskrnl!KeInitializeTimer` at `0x14000adff`
- `ntoskrnl!KeInitializeTimer` at `0x14000adff`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a7f4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ac6d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b140`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a7f4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ac6d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b140`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a8b0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000acee`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000aefd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b040`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b11b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b25b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a8b0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000acee`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000aefd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b040`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b11b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b25b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b26c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b26c`
- `ntoskrnl!ExAllocatePool2` at `0x14000a904`
- `ntoskrnl!ExAllocatePool2` at `0x14000a904`

## pseudocode

```c
__int64 __fastcall SendNameServiceRequest(
        __int64 a1,
        _BYTE *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int16 a7,
        int a8,
        unsigned int a9,
        int a10,
        _DWORD *a11)
{
  int v12; // r12d
  KIRQL v15; // al
  PVOID v16; // rcx
  KIRQL v17; // bl
  _QWORD *v18; // rax
  __int64 inited; // rax
  __int64 v20; // rsi
  _QWORD *v21; // rax
  __int64 v22; // rax
  bool v23; // zf
  int v24; // ebx
  unsigned int v25; // ebx
  char *Pool2; // rax
  char *v27; // r14
  __int16 v28; // ax
  _BYTE *v29; // r12
  char *v30; // r12
  unsigned __int32 *v31; // r12
  PVOID v32; // rdi
  KIRQL v33; // al
  KIRQL v34; // dl
  PVOID v35; // rax
  __int16 v36; // r15
  int v37; // ebx
  int v38; // ebx
  __int64 v40; // rbx
  _QWORD *v41; // rbx
  _QWORD *v42; // rax
  int v43; // eax
  unsigned __int32 v44; // eax
  char v45; // al
  void (__fastcall *v46)(__int64, __int64, _QWORD); // rax
  __int64 v47; // rdx
  __int64 v48; // rcx
  void *v49; // rcx
  unsigned int v50; // [rsp+30h] [rbp-48h]
  __int64 v51; // [rsp+30h] [rbp-48h]
  PVOID DeferredContext[8]; // [rsp+38h] [rbp-40h] BYREF
  unsigned int Size; // [rsp+80h] [rbp+8h]
  KIRQL Sizea; // [rsp+80h] [rbp+8h]
  int v55; // [rsp+90h] [rbp+18h]

  v12 = *(_DWORD *)(a1 + 72);
  DeferredContext[0] = *(PVOID *)(a3 + 32);
  *a11 = 0;
  v15 = KeAcquireSpinLockRaiseToDpc(&Lock);
  v16 = qword_140039470;
  v17 = v15;
  if ( qword_140039470 == &qword_140039470 )
  {
    v16 = 0;
    if ( (unsigned __int16)word_14003950A >= (unsigned __int16)word_14003950E )
    {
      KeReleaseSpinLock(&Lock, v15);
      if ( (byte_140038419 & 2) != 0 )
        WPP_SF_(777, 11, WPP_87eb87a187c337230802581752a3dec7_Traceguids);
      return 3221225626LL;
    }
  }
  else
  {
    if ( *((PVOID **)qword_140039470 + 1) != &qword_140039470 )
      goto LABEL_69;
    v18 = *(_QWORD **)qword_140039470;
    if ( *(PVOID *)(*(_QWORD *)qword_140039470 + 8LL) != qword_140039470 )
      goto LABEL_69;
    --NumFreeTrackers;
    qword_140039470 = v18;
    v18[1] = &qword_140039470;
  }
  inited = NbtAllocInitTracker(v16);
  v20 = inited;
  if ( !inited )
  {
    KeReleaseSpinLock(&Lock, v17);
    return 3221225626LL;
  }
  *(_DWORD *)(inited + 432) = 13;
  v21 = (_QWORD *)qword_140039428;
  if ( *(__int64 **)qword_140039428 != &UsedTrackers )
    goto LABEL_69;
  *(_QWORD *)(v20 + 424) = qword_140039428;
  *(_QWORD *)(v20 + 416) = &UsedTrackers;
  *v21 = v20 + 416;
  qword_140039428 = v20 + 416;
  if ( ++dword_1400392F4 > (unsigned int)dword_140039354 )
    dword_140039354 = dword_1400392F4;
  KeReleaseSpinLock(&Lock, v17);
  v22 = -1;
  do
    v23 = a2[++v22] == 0;
  while ( !v23 );
  Size = v22 + 1;
  v24 = 49;
  if ( a9 )
    v24 = 67;
  v25 = v22 + 1 + v24;
  Pool2 = (char *)ExAllocatePool2(64, (unsigned __int16)v25, 1484022350);
  v27 = Pool2;
  if ( !Pool2 )
    goto LABEL_52;
  v55 = v12 & 0xC;
  memset(Pool2, 0, v25);
  v28 = *(_WORD *)(a3 + 128);
  if ( !v28 )
    v28 = __ROR2__(GetTransactId(), 8);
  *(_WORD *)v27 = v28;
  v27[5] = 1;
  v27[7] = 0;
  v27[9] = 0;
  v27[12] = 32;
  v27[13] = (*(_BYTE *)(a1 + 164) >> 4) + 65;
  v27[14] = (*(_BYTE *)(a1 + 164) & 0xF) + 65;
  v27[15] = (*(_BYTE *)(a1 + 165) >> 4) + 65;
  v27[16] = (*(_BYTE *)(a1 + 165) & 0xF) + 65;
  v27[17] = (*(_BYTE *)(a1 + 166) >> 4) + 65;
  v27[18] = (*(_BYTE *)(a1 + 166) & 0xF) + 65;
  v27[19] = (*(_BYTE *)(a1 + 167) >> 4) + 65;
  v27[20] = (*(_BYTE *)(a1 + 167) & 0xF) + 65;
  v27[21] = (*(_BYTE *)(a1 + 168) >> 4) + 65;
  v27[22] = (*(_BYTE *)(a1 + 168) & 0xF) + 65;
  v27[23] = (*(_BYTE *)(a1 + 169) >> 4) + 65;
  v27[24] = (*(_BYTE *)(a1 + 169) & 0xF) + 65;
  v27[25] = (*(_BYTE *)(a1 + 170) >> 4) + 65;
  v27[26] = (*(_BYTE *)(a1 + 170) & 0xF) + 65;
  v27[27] = (*(_BYTE *)(a1 + 171) >> 4) + 65;
  v27[28] = (*(_BYTE *)(a1 + 171) & 0xF) + 65;
  v27[29] = (*(_BYTE *)(a1 + 172) >> 4) + 65;
  v27[30] = (*(_BYTE *)(a1 + 172) & 0xF) + 65;
  v27[31] = (*(_BYTE *)(a1 + 173) >> 4) + 65;
  v29 = v27 + 45;
  v27[32] = (*(_BYTE *)(a1 + 173) & 0xF) + 65;
  v27[33] = (*(_BYTE *)(a1 + 174) >> 4) + 65;
  v27[34] = (*(_BYTE *)(a1 + 174) & 0xF) + 65;
  v27[35] = (*(_BYTE *)(a1 + 175) >> 4) + 65;
  v27[36] = (*(_BYTE *)(a1 + 175) & 0xF) + 65;
  v27[37] = (*(_BYTE *)(a1 + 176) >> 4) + 65;
  v27[38] = (*(_BYTE *)(a1 + 176) & 0xF) + 65;
  v27[39] = (*(_BYTE *)(a1 + 177) >> 4) + 65;
  v27[40] = (*(_BYTE *)(a1 + 177) & 0xF) + 65;
  v27[41] = (*(_BYTE *)(a1 + 178) >> 4) + 65;
  v27[42] = (*(_BYTE *)(a1 + 178) & 0xF) + 65;
  v27[43] = (*(_BYTE *)(a1 + 179) >> 4) + 65;
  v27[44] = (*(_BYTE *)(a1 + 179) & 0xF) + 65;
  if ( Size > 1 )
  {
    memmove(v27 + 45, a2, Size);
    v30 = &v29[Size];
  }
  else
  {
    *v29 = 0;
    v30 = v27 + 46;
  }
  *(_DWORD *)v30 = 16785408;
  if ( !a9 )
  {
    *((_WORD *)v27 + 1) = ((NodeType & 1) << 12) + 1;
    v31 = 0;
    v32 = DeferredContext[0];
    v27[11] = 0;
    goto LABEL_28;
  }
  if ( a9 != 4 && a9 != 5 )
  {
    if ( a9 == 7 )
      goto LABEL_21;
    if ( a9 != 8 )
      goto LABEL_25;
  }
  *((_WORD *)v27 + 1) = (a9 != 5) + 40;
  *(_DWORD *)(v30 + 10) = -527236096;
LABEL_21:
  if ( a9 == 7 )
  {
    *((_WORD *)v27 + 1) = 48;
    *(_DWORD *)(v30 + 10) = 0;
  }
  v23 = pWinsInfo == 0;
  v27[11] = 1;
  if ( !v23 && (*(_DWORD *)(a3 + 240) & 2) != 0 )
    v27[7] = -1;
  *((_WORD *)v30 + 2) = 3264;
  *(_DWORD *)(v30 + 6) = 16785408;
  *((_WORD *)v30 + 7) = 1536;
  *((_WORD *)v30 + 8) = __ROR2__(word_140039626 | (v55 != 0 ? 0x8000 : 0), 8);
  *(_DWORD *)(v30 + 18) = 0;
LABEL_25:
  v31 = (unsigned __int32 *)(v30 + 18);
  if ( v31 )
  {
    v32 = DeferredContext[0];
    if ( a9 == 8 )
      *((_WORD *)v27 + 1) = word_140039688;
LABEL_28:
    v33 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
    *(_QWORD *)(a3 + 48) = a1;
    v34 = v33;
    *(_WORD *)(a3 + 128) = *(_WORD *)v27;
    Sizea = v33;
    v35 = DeferredContext[0];
    *(_QWORD *)(v20 + 64) = v27;
    *(_DWORD *)(v20 + 56) = v25;
    *(_QWORD *)(v20 + 80) = 0;
    *(_DWORD *)(v20 + 72) = 0;
    *(_QWORD *)(v20 + 48) = a1;
    *(_QWORD *)(v20 + 32) = v35;
    if ( !a8 )
      goto LABEL_29;
    v40 = *(_QWORD *)(a1 + 112);
    if ( !v40 )
    {
LABEL_36:
      DeferredContext[0] = 0;
      if ( !byte_140039752 )
      {
        if ( v32 )
        {
          if ( *((_DWORD *)v32 + 90) != 1131832644 )
            goto LABEL_101;
          _InterlockedIncrement((volatile signed __int32 *)v32 + 91);
          ++*((_DWORD *)v32 + 273);
        }
        if ( (int)GetTimerEntry(DeferredContext) >= 0 )
        {
          v41 = DeferredContext[0];
          *((_DWORD *)DeferredContext[0] + 6) = a8;
          *((_BYTE *)v41 + 23) = 1;
          v41[6] = a3;
          v41[7] = 0;
          v41[5] = a4;
          *((_WORD *)v41 + 128) = 0;
          v41[8] = a5;
          v41[9] = a6;
          *((_WORD *)v41 + 10) = a7;
          v41[4] = v32;
          KeInitializeTimer((PKTIMER)v41 + 3);
          v50 = *((_DWORD *)v41 + 6);
          KeInitializeDpc((PRKDPC)v41 + 2, TimerExpiry, v41);
          if ( v50 >= 0x2710 )
            KeSetTimer((PKTIMER)v41 + 3, (LARGE_INTEGER)(-10000LL * v50), (PKDPC)v41 + 2);
          else
            KeSetCoalescableTimer((PKTIMER)v41 + 3, (LARGE_INTEGER)(-10000LL * v50), 0, v50 / 0xA, (PKDPC)v41 + 2);
          v42 = TimerQ;
          if ( *((PVOID **)TimerQ + 1) == &TimerQ )
          {
            v34 = Sizea;
            *v41 = TimerQ;
            v41[1] = &TimerQ;
            v42[1] = v41;
            TimerQ = v41;
            v41[10] = a1;
            *(_QWORD *)(a1 + 112) = v41;
            *a11 = 1;
LABEL_29:
            if ( (*(_DWORD *)(a3 + 240) & 1) != 0 || NodeType == 1 && v27[7] != -1 )
            {
              v36 = 137;
              *(_BYTE *)(*(_QWORD *)(v20 + 64) + 3LL) |= 0x10u;
              v37 = *((_DWORD *)v32 + 124);
            }
            else
            {
              *(_BYTE *)(*(_QWORD *)(v20 + 64) + 3LL) &= ~0x10u;
              if ( (_BYTE)word_140039670 && a9 == 4 && !v55 )
                *(_BYTE *)(*(_QWORD *)(v20 + 64) + 2LL) |= 0x78u;
              v43 = *(_DWORD *)(a3 + 240);
              v36 = word_14003962A;
              if ( (v43 & 2) != 0 )
              {
                v37 = *((_DWORD *)v32 + 126);
              }
              else if ( (v43 & 8) != 0 )
              {
                if ( *(_WORD *)(a3 + 206) )
                  v37 = *(_DWORD *)(*(_QWORD *)(a3 + 32) + 4LL * *(unsigned __int16 *)(a3 + 204) + 512);
                else
                  v37 = 2130706432;
              }
              else
              {
                v37 = *((_DWORD *)v32 + 127);
              }
              if ( v27[7] == -1 && (!*((_DWORD *)v32 + 215) || *((_DWORD *)v32 + 126) == 2130706432) )
                v37 = *((_DWORD *)v32 + 122);
            }
            if ( v31 )
            {
              if ( (*(_DWORD *)(a3 + 240) & 0x20000) != 0 )
                v44 = _byteswap_ulong(*(_DWORD *)(a3 + 208));
              else
                v44 = _byteswap_ulong(*((_DWORD *)v32 + 122));
              *v31 = v44;
            }
            KeReleaseSpinLock(&SpinLock, v34);
            v38 = UdpSendDatagram(v20, v37, (unsigned int)SessionRespDone, v20, v36, a10 != 0 ? 0x10 : 0);
            if ( v38 < 0 )
              FreeTracker(v20, 5);
            return (unsigned int)v38;
          }
LABEL_69:
          __fastfail(3u);
        }
        if ( v32 )
          NBT_DEREFERENCE_DEVICE(v32, 2);
        v34 = Sizea;
      }
LABEL_101:
      KeReleaseSpinLock(&SpinLock, v34);
      ExFreePoolWithTag(v27, 0);
      FreeTracker(v20, 4);
      return 3221225716LL;
    }
    while ( 1 )
    {
      *(_QWORD *)(a1 + 112) = 0;
      v45 = *(_BYTE *)(v40 + 23);
      if ( v45 == 1 )
        break;
      if ( v45 == 2 )
      {
        v51 = 0;
        v49 = *(void **)(v40 + 72);
        DeferredContext[0] = 0;
        if ( v49 )
        {
          v51 = *(_QWORD *)(v40 + 64);
          *(_QWORD *)(v40 + 72) = 0;
          DeferredContext[0] = v49;
        }
        *(_BYTE *)(v40 + 23) = 3;
        goto LABEL_80;
      }
LABEL_86:
      v40 = *(_QWORD *)(a1 + 112);
      if ( !v40 )
        goto LABEL_36;
    }
    v23 = (*(_BYTE *)(v40 + 256) & 8) == 0;
    DeferredContext[0] = *(PVOID *)(v40 + 72);
    v51 = *(_QWORD *)(v40 + 64);
    *(_QWORD *)(v40 + 72) = 0;
    if ( v23 && !KeCancelTimer((PKTIMER)(v40 + 192)) )
    {
      v46 = *(void (__fastcall **)(__int64, __int64, _QWORD))(v40 + 40);
      if ( v46 )
      {
        v47 = *(_QWORD *)(v40 + 56);
        v48 = *(_QWORD *)(v40 + 48);
        *(_QWORD *)(v40 + 40) = 0;
        v46(v48, v47, 0);
      }
      v34 = Sizea;
      *(_BYTE *)(v40 + 23) = 2;
    }
    else
    {
      CleanupCTETimer((_QWORD *)v40);
      v34 = Sizea;
    }
LABEL_80:
    if ( DeferredContext[0] )
    {
      KeReleaseSpinLock(&SpinLock, v34);
      ((void (__fastcall *)(__int64, __int64))DeferredContext[0])(v51, 258);
      v34 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
      Sizea = v34;
    }
    goto LABEL_86;
  }
LABEL_52:
  if ( (BYTE3(xmmword_140038420) & 2) != 0 )
    WPP_SF_d(1049, 10, WPP_dc02a1f82c2934b6fc0cb4f28219eafa_Traceguids, a9);
  FreeTracker(v20, 4);
  return 3221225626LL;
}

```

## disassembly

```asm
0x14000a7b0  mov     [rsp+arg_8], rbx
0x14000a7b5  mov     [rsp+arg_18], r9
0x14000a7ba  push    rbp
0x14000a7bb  push    rsi
0x14000a7bc  push    rdi
0x14000a7bd  push    r12
0x14000a7bf  push    r13
0x14000a7c1  push    r14
0x14000a7c3  push    r15
0x14000a7c5  sub     rsp, 40h
0x14000a7c9  mov     rax, [r8+20h]
0x14000a7cd  mov     r15, rcx
0x14000a7d0  mov     r12d, [rcx+48h]
0x14000a7d4  mov     rbp, r8
0x14000a7d7  mov     [rsp+78h+DeferredContext], rax
0x14000a7dc  lea     rcx, Lock; SpinLock
0x14000a7e3  mov     rax, [rsp+78h+arg_50]
0x14000a7eb  mov     rdi, rdx
0x14000a7ee  mov     dword ptr [rax], 0
0x14000a7f4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000a7fb  nop     dword ptr [rax+rax+00h]
0x14000a800  mov     rcx, cs:qword_140039470; void *
0x14000a807  lea     rdx, qword_140039470
0x14000a80e  movzx   ebx, al
0x14000a811  cmp     rcx, rdx
0x14000a814  jz      loc_14000B020
0x14000a81a  cmp     [rcx+8], rdx
0x14000a81e  jnz     loc_14000B019
0x14000a824  mov     rax, [rcx]
0x14000a827  cmp     [rax+8], rcx
0x14000a82b  jnz     loc_14000B019
0x14000a831  dec     cs:NumFreeTrackers
0x14000a837  mov     cs:qword_140039470, rax
0x14000a83e  mov     [rax+8], rdx
0x14000a842  call    NbtAllocInitTracker
0x14000a847  mov     rsi, rax
0x14000a84a  test    rax, rax
0x14000a84d  jz      loc_14000AEF3
0x14000a853  mov     dword ptr [rax+1B0h], 0Dh
0x14000a85d  lea     rdx, UsedTrackers
0x14000a864  mov     rax, cs:qword_140039428
0x14000a86b  cmp     [rax], rdx
0x14000a86e  jnz     loc_14000B019
0x14000a874  lea     rcx, [rsi+1A0h]
0x14000a87b  mov     [rcx+8], rax
0x14000a87f  mov     [rcx], rdx
0x14000a882  mov     [rax], rcx
0x14000a885  mov     eax, cs:dword_1400392F4
0x14000a88b  inc     eax
0x14000a88d  mov     cs:qword_140039428, rcx
0x14000a894  cmp     eax, cs:dword_140039354
0x14000a89a  mov     cs:dword_1400392F4, eax
0x14000a8a0  ja      loc_14000AFD4
0x14000a8a6  movzx   edx, bl; NewIrql
0x14000a8a9  lea     rcx, Lock; SpinLock
0x14000a8b0  call    cs:__imp_KeReleaseSpinLock
0x14000a8b7  nop     dword ptr [rax+rax+00h]
0x14000a8bc  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14000a8c3  cmp     byte ptr [rdi+rax+1], 0
0x14000a8c8  lea     rax, [rax+1]
0x14000a8cc  jnz     short loc_14000A8C3
0x14000a8ce  mov     r13d, [rsp+78h+arg_40]
0x14000a8d6  lea     ecx, [rax+1]
0x14000a8d9  mov     edx, 43h ; 'C'
0x14000a8de  mov     dword ptr [rsp+78h+Size], ecx
0x14000a8e5  test    r13d, r13d
0x14000a8e8  mov     ebx, 31h ; '1'
0x14000a8ed  mov     r8d, 5874624Eh
0x14000a8f3  cmovnz  ebx, edx
0x14000a8f6  add     ebx, ecx
0x14000a8f8  mov     ecx, 40h ; '@'
0x14000a8fd  movzx   edx, bx
0x14000a900  mov     dword ptr [rsp+78h+var_48], ebx
0x14000a904  call    cs:__imp_ExAllocatePool2
0x14000a90b  nop     dword ptr [rax+rax+00h]
0x14000a910  mov     r14, rax
0x14000a913  test    rax, rax
0x14000a916  jz      loc_14000AF13
0x14000a91c  and     r12d, 0Ch
0x14000a920  mov     r8d, ebx; Size
0x14000a923  xor     edx, edx; Val
0x14000a925  mov     [rsp+78h+arg_10], r12d
0x14000a92d  mov     rcx, rax; void *
0x14000a930  call    memset
0x14000a935  movzx   eax, word ptr [rbp+80h]
0x14000a93c  test    ax, ax
0x14000a93f  jz      loc_14000AF37
0x14000a945  mov     [r14], ax
0x14000a949  mov     byte ptr [r14+5], 1
0x14000a94e  mov     byte ptr [r14+7], 0
0x14000a953  mov     byte ptr [r14+9], 0
0x14000a958  mov     byte ptr [r14+0Ch], 20h ; ' '
0x14000a95d  movzx   eax, byte ptr [r15+0A4h]
0x14000a965  shr     al, 4
0x14000a968  add     al, 41h ; 'A'
0x14000a96a  mov     [r14+0Dh], al
0x14000a96e  movzx   eax, byte ptr [r15+0A4h]
0x14000a976  and     al, 0Fh
0x14000a978  add     al, 41h ; 'A'
0x14000a97a  mov     [r14+0Eh], al
0x14000a97e  movzx   eax, byte ptr [r15+0A5h]
0x14000a986  shr     al, 4
0x14000a989  add     al, 41h ; 'A'
0x14000a98b  mov     [r14+0Fh], al
0x14000a98f  movzx   eax, byte ptr [r15+0A5h]
0x14000a997  and     al, 0Fh
0x14000a999  add     al, 41h ; 'A'
0x14000a99b  mov     [r14+10h], al
0x14000a99f  movzx   eax, byte ptr [r15+0A6h]
0x14000a9a7  shr     al, 4
0x14000a9aa  add     al, 41h ; 'A'
0x14000a9ac  mov     [r14+11h], al
0x14000a9b0  movzx   eax, byte ptr [r15+0A6h]
0x14000a9b8  and     al, 0Fh
0x14000a9ba  add     al, 41h ; 'A'
0x14000a9bc  mov     [r14+12h], al
0x14000a9c0  movzx   eax, byte ptr [r15+0A7h]
0x14000a9c8  shr     al, 4
0x14000a9cb  add     al, 41h ; 'A'
0x14000a9cd  mov     [r14+13h], al
0x14000a9d1  movzx   eax, byte ptr [r15+0A7h]
0x14000a9d9  and     al, 0Fh
0x14000a9db  add     al, 41h ; 'A'
0x14000a9dd  mov     [r14+14h], al
0x14000a9e1  movzx   eax, byte ptr [r15+0A8h]
0x14000a9e9  shr     al, 4
0x14000a9ec  add     al, 41h ; 'A'
0x14000a9ee  mov     [r14+15h], al
0x14000a9f2  movzx   eax, byte ptr [r15+0A8h]
0x14000a9fa  and     al, 0Fh
0x14000a9fc  add     al, 41h ; 'A'
0x14000a9fe  mov     [r14+16h], al
0x14000aa02  movzx   eax, byte ptr [r15+0A9h]
0x14000aa0a  shr     al, 4
0x14000aa0d  add     al, 41h ; 'A'
0x14000aa0f  mov     [r14+17h], al
0x14000aa13  movzx   eax, byte ptr [r15+0A9h]
0x14000aa1b  and     al, 0Fh
0x14000aa1d  add     al, 41h ; 'A'
0x14000aa1f  mov     [r14+18h], al
0x14000aa23  movzx   eax, byte ptr [r15+0AAh]
0x14000aa2b  shr     al, 4
0x14000aa2e  add     al, 41h ; 'A'
0x14000aa30  mov     [r14+19h], al
0x14000aa34  movzx   eax, byte ptr [r15+0AAh]
0x14000aa3c  and     al, 0Fh
0x14000aa3e  add     al, 41h ; 'A'
0x14000aa40  mov     [r14+1Ah], al
0x14000aa44  movzx   eax, byte ptr [r15+0ABh]
0x14000aa4c  shr     al, 4
0x14000aa4f  add     al, 41h ; 'A'
0x14000aa51  mov     [r14+1Bh], al
0x14000aa55  movzx   eax, byte ptr [r15+0ABh]
0x14000aa5d  and     al, 0Fh
0x14000aa5f  add     al, 41h ; 'A'
0x14000aa61  mov     [r14+1Ch], al
0x14000aa65  movzx   eax, byte ptr [r15+0ACh]
0x14000aa6d  shr     al, 4
0x14000aa70  add     al, 41h ; 'A'
0x14000aa72  mov     [r14+1Dh], al
0x14000aa76  movzx   eax, byte ptr [r15+0ACh]
0x14000aa7e  and     al, 0Fh
0x14000aa80  add     al, 41h ; 'A'
0x14000aa82  mov     [r14+1Eh], al
0x14000aa86  movzx   eax, byte ptr [r15+0ADh]
0x14000aa8e  shr     al, 4
0x14000aa91  add     al, 41h ; 'A'
0x14000aa93  mov     [r14+1Fh], al
0x14000aa97  movzx   eax, byte ptr [r15+0ADh]
0x14000aa9f  lea     r12, [r14+2Dh]
0x14000aaa3  and     al, 0Fh
0x14000aaa5  add     al, 41h ; 'A'
0x14000aaa7  mov     [r14+20h], al
0x14000aaab  movzx   eax, byte ptr [r15+0AEh]
0x14000aab3  shr     al, 4
0x14000aab6  add     al, 41h ; 'A'
0x14000aab8  mov     [r14+21h], al
0x14000aabc  movzx   eax, byte ptr [r15+0AEh]
0x14000aac4  and     al, 0Fh
0x14000aac6  add     al, 41h ; 'A'
0x14000aac8  mov     [r14+22h], al
0x14000aacc  movzx   eax, byte ptr [r15+0AFh]
0x14000aad4  shr     al, 4
0x14000aad7  add     al, 41h ; 'A'
0x14000aad9  mov     [r14+23h], al
0x14000aadd  movzx   eax, byte ptr [r15+0AFh]
0x14000aae5  and     al, 0Fh
0x14000aae7  add     al, 41h ; 'A'
0x14000aae9  mov     [r14+24h], al
0x14000aaed  movzx   eax, byte ptr [r15+0B0h]
0x14000aaf5  shr     al, 4
0x14000aaf8  add     al, 41h ; 'A'
0x14000aafa  mov     [r14+25h], al
0x14000aafe  movzx   eax, byte ptr [r15+0B0h]
0x14000ab06  and     al, 0Fh
0x14000ab08  add     al, 41h ; 'A'
0x14000ab0a  mov     [r14+26h], al
0x14000ab0e  movzx   eax, byte ptr [r15+0B1h]
0x14000ab16  shr     al, 4
0x14000ab19  add     al, 41h ; 'A'
0x14000ab1b  mov     [r14+27h], al
0x14000ab1f  movzx   eax, byte ptr [r15+0B1h]
0x14000ab27  and     al, 0Fh
0x14000ab29  add     al, 41h ; 'A'
0x14000ab2b  mov     [r14+28h], al
0x14000ab2f  movzx   eax, byte ptr [r15+0B2h]
0x14000ab37  shr     al, 4
0x14000ab3a  add     al, 41h ; 'A'
0x14000ab3c  mov     [r14+29h], al
0x14000ab40  movzx   eax, byte ptr [r15+0B2h]
0x14000ab48  and     al, 0Fh
0x14000ab4a  add     al, 41h ; 'A'
0x14000ab4c  mov     [r14+2Ah], al
0x14000ab50  movzx   eax, byte ptr [r15+0B3h]
0x14000ab58  shr     al, 4
0x14000ab5b  add     al, 41h ; 'A'
0x14000ab5d  mov     [r14+2Bh], al
0x14000ab61  movzx   eax, byte ptr [r15+0B3h]
0x14000ab69  and     al, 0Fh
0x14000ab6b  add     al, 41h ; 'A'
0x14000ab6d  mov     [r14+2Ch], al
0x14000ab71  mov     eax, dword ptr [rsp+78h+Size]
0x14000ab78  cmp     eax, 1
0x14000ab7b  ja      loc_14000B18B
0x14000ab81  mov     byte ptr [r12], 0
0x14000ab86  inc     r12
0x14000ab89  mov     dword ptr [r12], 1002000h
0x14000ab91  test    r13d, r13d
0x14000ab94  jnz     loc_14000AEC7
0x14000ab9a  movzx   ecx, cs:NodeType
0x14000aba1  mov     eax, 1000h
0x14000aba6  and     cx, 1
0x14000abaa  movzx   edx, cx
0x14000abad  imul    edx, eax
0x14000abb0  inc     dx
0x14000abb3  mov     [r14+2], dx
0x14000abb8  xor     r12d, r12d
0x14000abbb  mov     rdi, [rsp+78h+DeferredContext]
0x14000abc0  mov     [r14+0Bh], r13b
0x14000abc4  jmp     loc_14000AC66
0x14000abc9  xor     eax, eax
0x14000abcb  cmp     r13d, 5
0x14000abcf  setnz   al
0x14000abd2  add     ax, 28h ; '('
0x14000abd6  mov     [r14+2], ax
0x14000abdb  mov     dword ptr [r12+0Ah], 0E0930400h
0x14000abe4  cmp     r13d, 7
0x14000abe8  jz      loc_14000AFDF
0x14000abee  cmp     cs:pWinsInfo, 0
0x14000abf6  mov     byte ptr [r14+0Bh], 1
0x14000abfb  jnz     loc_14000B1B9
0x14000ac01  mov     eax, [rsp+78h+arg_10]
0x14000ac08  neg     eax
0x14000ac0a  mov     word ptr [r12+4], 0CC0h
0x14000ac12  mov     dword ptr [r12+6], 1002000h
0x14000ac1b  sbb     cx, cx
0x14000ac1e  mov     word ptr [r12+0Eh], 600h
0x14000ac26  and     cx, 8000h
0x14000ac2b  or      cx, cs:word_140039626
0x14000ac32  ror     cx, 8
0x14000ac36  mov     [r12+10h], cx
0x14000ac3c  mov     dword ptr [r12+12h], 0
0x14000ac45  add     r12, 12h
0x14000ac49  jz      loc_14000AF13
0x14000ac4f  mov     rdi, [rsp+78h+DeferredContext]
0x14000ac54  cmp     r13d, 8
0x14000ac58  jnz     short loc_14000AC66
0x14000ac5a  movzx   eax, cs:word_140039688
0x14000ac61  mov     [r14+2], ax
0x14000ac66  lea     rcx, SpinLock; SpinLock
0x14000ac6d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000ac74  nop     dword ptr [rax+rax+00h]
0x14000ac79  mov     [rbp+30h], r15
0x14000ac7d  movzx   edx, al; NewIrql
0x14000ac80  movzx   ecx, word ptr [r14]
0x14000ac84  mov     [rbp+80h], cx
0x14000ac8b  xor     ecx, ecx
0x14000ac8d  mov     byte ptr [rsp+78h+Size], al
0x14000ac94  mov     rax, [rsp+78h+DeferredContext]
0x14000ac99  mov     [rsi+40h], r14
0x14000ac9d  mov     [rsi+38h], ebx
0x14000aca0  mov     [rsi+50h], rcx
0x14000aca4  mov     [rsi+48h], ecx
0x14000aca7  mov     [rsi+30h], r15
0x14000acab  mov     [rsi+20h], rax
0x14000acaf  cmp     [rsp+78h+arg_38], ecx
0x14000acb6  jnz     loc_14000AD49
0x14000acbc  mov     eax, [rbp+0F0h]
0x14000acc2  test    al, 1
0x14000acc4  jz      loc_14000AF45
0x14000acca  mov     rax, [rsi+40h]
0x14000acce  mov     r15d, 89h
0x14000acd4  or      byte ptr [rax+3], 10h
0x14000acd8  mov     ebx, [rdi+1F0h]
0x14000acde  test    r12, r12
0x14000ace1  jnz     loc_14000AFB3
0x14000ace7  lea     rcx, SpinLock; SpinLock
0x14000acee  call    cs:__imp_KeReleaseSpinLock
0x14000acf5  nop     dword ptr [rax+rax+00h]
0x14000acfa  neg     [rsp+78h+arg_48]
  ... truncated ...
```
