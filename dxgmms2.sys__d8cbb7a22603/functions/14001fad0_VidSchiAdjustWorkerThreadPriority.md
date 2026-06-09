# VidSchiAdjustWorkerThreadPriority

- ea: `0x14001fad0`
- end: `0x14001fda3`
- name: `VidSchiAdjustWorkerThreadPriority`
- size: `723`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14001f2a0`
- `0x140050e38`
- `0x1400e5a50`

## callees

- `0x14001fad0`
- `0x1400444d4`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001fba9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001fcb2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001fba9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001fcb2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001fbee`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001fc76`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001fbee`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001fc76`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001fd92`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001fd92`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001fcd0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001fd81`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001fcd0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001fd81`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14001fd66`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14001fd66`
- `ntoskrnl!KeQueryPriorityThread` at `0x14001fb26`
- `ntoskrnl!KeQueryPriorityThread` at `0x14001fb46`
- `ntoskrnl!KeQueryPriorityThread` at `0x14001fc4a`
- `ntoskrnl!KeQueryPriorityThread` at `0x14001fb26`
- `ntoskrnl!KeQueryPriorityThread` at `0x14001fb46`
- `ntoskrnl!KeQueryPriorityThread` at `0x14001fc4a`
- `ntoskrnl!KeSetPriorityThread` at `0x14001fc91`
- `ntoskrnl!KeSetPriorityThread` at `0x14001fc91`

## pseudocode

```c
void __fastcall VidSchiAdjustWorkerThreadPriority(__int64 a1)
{
  __int64 v2; // rbx
  int v3; // eax
  struct _KTHREAD *CurrentThread; // rax
  unsigned int v5; // esi
  char v6; // bp
  int v7; // eax
  __int64 v8; // r15
  __int64 v9; // rax
  KPRIORITY v10; // r15d
  int v11; // ecx
  KSPIN_LOCK *SpinLock; // [rsp+20h] [rbp-48h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+28h] [rbp-40h] BYREF
  __int16 v15; // [rsp+40h] [rbp-28h]

  v2 = *(_QWORD *)(*(_QWORD *)(a1 + 96) + 24LL);
  v3 = *(_DWORD *)(v2 + 2904);
  if ( (v3 & 2) != 0 )
  {
    VidSchiAdjustWorkerThreadPriorityDirectSubmitAware();
    return;
  }
  if ( (v3 & 0x20) != 0 )
  {
    CurrentThread = KeGetCurrentThread();
    if ( CurrentThread == *(struct _KTHREAD **)(v2 + 184) || CurrentThread == *(struct _KTHREAD **)(v2 + 192) )
    {
      if ( *(_DWORD *)(a1 + 788) )
        return;
      v6 = 1;
      v5 = 16;
    }
    else
    {
      if ( KeQueryPriorityThread(KeGetCurrentThread()) + 1 >= 31 )
      {
        v5 = 31;
      }
      else
      {
        v5 = KeQueryPriorityThread(KeGetCurrentThread()) + 1;
        if ( (int)v5 <= 16 )
          return;
      }
      v6 = 0;
    }
    v15 = 0;
    SpinLock = (KSPIN_LOCK *)(v2 + 2832);
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v2 + 2832), &LockHandle);
    while ( 1 )
    {
      v7 = *(_DWORD *)(a1 + 788);
      LOBYTE(v15) = 1;
      if ( v6 )
      {
        if ( v7 )
          goto LABEL_13;
      }
      else if ( !v7 )
      {
LABEL_13:
        if ( (_BYTE)v15 )
        {
          if ( HIBYTE(v15) )
            KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
          else
            KeReleaseInStackQueuedSpinLock(&LockHandle);
        }
        return;
      }
      v8 = *(_QWORD *)(*(_QWORD *)(a1 + 96) + 24LL);
      v9 = *(int *)(a1 + 400);
      if ( (_DWORD)v9 != v5 )
      {
        v11 = 0;
        if ( (int)v9 > 16 && (*(_DWORD *)(v8 + 4 * v9 + 2776))-- == 1 )
        {
          v11 = 1;
          *(_DWORD *)(v8 + 2840) &= ~(1 << *(_DWORD *)(a1 + 400));
        }
        if ( v5 > 0x10 && (++*(_DWORD *)(v8 + 4LL * v5 + 2776), *(_DWORD *)(v8 + 4LL * v5 + 2776) == 1) )
        {
          *(_DWORD *)(v8 + 2840) |= 1 << v5;
          *(_DWORD *)(a1 + 400) = v5;
        }
        else
        {
          *(_DWORD *)(a1 + 400) = v5;
          if ( !v11 )
            goto LABEL_20;
        }
        if ( *(_DWORD *)(v8 + 2840) )
          *(_DWORD *)(v8 + 244) = RtlFindMostSignificantBit(*(unsigned int *)(v8 + 2840));
        else
          *(_DWORD *)(v8 + 244) = 16;
      }
LABEL_20:
      v10 = *(_DWORD *)(v8 + 244);
      if ( v10 == KeQueryPriorityThread(*(PKTHREAD *)(v2 + 184)) )
        goto LABEL_13;
      if ( (_BYTE)v15 )
      {
        if ( HIBYTE(v15) )
          KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
        else
          KeReleaseInStackQueuedSpinLock(&LockHandle);
        LOBYTE(v15) = 0;
      }
      KeSetPriorityThread(*(PKTHREAD *)(v2 + 184), v10);
      if ( HIBYTE(v15) )
        KeAcquireInStackQueuedSpinLockAtDpcLevel(SpinLock, &LockHandle);
      else
        KeAcquireInStackQueuedSpinLock(SpinLock, &LockHandle);
    }
  }
}

```

## disassembly

```asm
0x14001fad0  mov     r11, rsp
0x14001fad3  push    rbx
0x14001fad4  push    rdi
0x14001fad5  sub     rsp, 58h
0x14001fad9  mov     rbx, [rcx+60h]
0x14001fadd  mov     rdi, rcx
0x14001fae0  mov     rbx, [rbx+18h]
0x14001fae4  mov     eax, [rbx+0B58h]
0x14001faea  test    al, 2
0x14001faec  jnz     loc_14001FC0F
0x14001faf2  test    al, 20h
0x14001faf4  jz      short loc_14001FB73
0x14001faf6  mov     rax, gs:188h
0x14001faff  mov     [r11+10h], rbp
0x14001fb03  mov     [r11+18h], rsi
0x14001fb07  mov     [r11+20h], r14
0x14001fb0b  cmp     rax, [rbx+0B8h]
0x14001fb12  jz      short loc_14001FB7B
0x14001fb14  cmp     rax, [rbx+0C0h]
0x14001fb1b  jz      short loc_14001FB7B
0x14001fb1d  mov     rcx, gs:188h; Thread
0x14001fb26  call    cs:__imp_KeQueryPriorityThread
0x14001fb2d  nop     dword ptr [rax+rax+00h]
0x14001fb32  inc     eax
0x14001fb34  cmp     eax, 1Fh
0x14001fb37  jge     loc_14001FBFF
0x14001fb3d  mov     rcx, gs:188h; Thread
0x14001fb46  call    cs:__imp_KeQueryPriorityThread
0x14001fb4d  nop     dword ptr [rax+rax+00h]
0x14001fb52  lea     esi, [rax+1]
0x14001fb55  cmp     esi, 10h
0x14001fb58  jg      loc_14001FC04
0x14001fb5e  mov     rsi, [rsp+68h+arg_10]
0x14001fb66  mov     rbp, [rsp+68h+arg_8]
0x14001fb6b  mov     r14, [rsp+68h+arg_18]
0x14001fb73  add     rsp, 58h
0x14001fb77  pop     rdi
0x14001fb78  pop     rbx
0x14001fb79  retn
0x14001fb7b  mov     eax, [rcx+314h]
0x14001fb81  test    eax, eax
0x14001fb83  jnz     short loc_14001FB5E
0x14001fb85  mov     r14d, 10h
0x14001fb8b  mov     bpl, 1
0x14001fb8e  mov     esi, r14d
0x14001fb91  lea     rcx, [rbx+0B10h]; SpinLock
0x14001fb98  mov     [rsp+68h+var_28], 0
0x14001fb9f  lea     rdx, [rsp+68h+LockHandle]; LockHandle
0x14001fba4  mov     [rsp+68h+SpinLock], rcx
0x14001fba9  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14001fbb0  nop     dword ptr [rax+rax+00h]
0x14001fbb5  mov     [rsp+68h+var_18], r15
0x14001fbba  mov     eax, [rdi+314h]
0x14001fbc0  mov     byte ptr [rsp+68h+var_28], 1
0x14001fbc5  test    bpl, bpl
0x14001fbc8  jz      loc_14001FCC3
0x14001fbce  test    eax, eax
0x14001fbd0  jz      short loc_14001FC1C
0x14001fbd2  cmp     byte ptr [rsp+68h+var_28], 0
0x14001fbd7  mov     r15, [rsp+68h+var_18]
0x14001fbdc  jz      short loc_14001FB5E
0x14001fbde  cmp     byte ptr [rsp+68h+var_28+1], 0
0x14001fbe3  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x14001fbe8  jnz     loc_14001FCD0
0x14001fbee  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14001fbf5  nop     dword ptr [rax+rax+00h]
0x14001fbfa  jmp     loc_14001FB5E
0x14001fbff  mov     esi, 1Fh
0x14001fc04  xor     bpl, bpl
0x14001fc07  mov     r14d, 10h
0x14001fc0d  jmp     short loc_14001FB91
0x14001fc0f  call    VidSchiAdjustWorkerThreadPriorityDirectSubmitAware
0x14001fc14  add     rsp, 58h
0x14001fc18  pop     rdi
0x14001fc19  pop     rbx
0x14001fc1a  retn
0x14001fc1c  mov     rax, [rdi+60h]
0x14001fc20  cmp     esi, 10h
0x14001fc23  mov     edx, esi
0x14001fc25  cmovb   edx, r14d
0x14001fc29  mov     r15, [rax+18h]
0x14001fc2d  movsxd  rax, dword ptr [rdi+190h]
0x14001fc34  cmp     eax, edx
0x14001fc36  jnz     loc_14001FCE1
0x14001fc3c  mov     rcx, [rbx+0B8h]; Thread
0x14001fc43  mov     r15d, [r15+0F4h]
0x14001fc4a  call    cs:__imp_KeQueryPriorityThread
0x14001fc51  nop     dword ptr [rax+rax+00h]
0x14001fc56  cmp     r15d, eax
0x14001fc59  jz      loc_14001FBD2
0x14001fc5f  cmp     byte ptr [rsp+68h+var_28], 0
0x14001fc64  jz      short loc_14001FC87
0x14001fc66  cmp     byte ptr [rsp+68h+var_28+1], 0
0x14001fc6b  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x14001fc70  jnz     loc_14001FD81
0x14001fc76  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14001fc7d  nop     dword ptr [rax+rax+00h]
0x14001fc82  mov     byte ptr [rsp+68h+var_28], 0
0x14001fc87  mov     rcx, [rbx+0B8h]; Thread
0x14001fc8e  mov     edx, r15d; Priority
0x14001fc91  call    cs:__imp_KeSetPriorityThread
0x14001fc98  nop     dword ptr [rax+rax+00h]
0x14001fc9d  cmp     byte ptr [rsp+68h+var_28+1], 0
0x14001fca2  lea     rdx, [rsp+68h+LockHandle]; LockHandle
0x14001fca7  mov     rcx, [rsp+68h+SpinLock]; SpinLock
0x14001fcac  jnz     loc_14001FD92
0x14001fcb2  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14001fcb9  nop     dword ptr [rax+rax+00h]
0x14001fcbe  jmp     loc_14001FBBA
0x14001fcc3  test    eax, eax
0x14001fcc5  jz      loc_14001FBD2
0x14001fccb  jmp     loc_14001FC1C
0x14001fcd0  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14001fcd7  nop     dword ptr [rax+rax+00h]
0x14001fcdc  jmp     loc_14001FB5E
0x14001fce1  xor     ecx, ecx
0x14001fce3  cmp     eax, 10h
0x14001fce6  jle     short loc_14001FD0E
0x14001fce8  add     dword ptr [r15+rax*4+0AD8h], 0FFFFFFFFh
0x14001fcf1  jnz     short loc_14001FD0E
0x14001fcf3  mov     ecx, [rdi+190h]
0x14001fcf9  mov     eax, 1
0x14001fcfe  shl     eax, cl
0x14001fd00  mov     ecx, 1
0x14001fd05  not     eax
0x14001fd07  and     [r15+0B18h], eax
0x14001fd0e  cmp     edx, 10h
0x14001fd11  ja      short loc_14001FD38
0x14001fd13  mov     [rdi+190h], edx
0x14001fd19  test    ecx, ecx
0x14001fd1b  jz      loc_14001FC3C
0x14001fd21  mov     eax, [r15+0B18h]
0x14001fd28  test    eax, eax
0x14001fd2a  jnz     short loc_14001FD63
0x14001fd2c  mov     [r15+0F4h], r14d
0x14001fd33  jmp     loc_14001FC3C
0x14001fd38  inc     dword ptr [r15+rdx*4+0AD8h]
0x14001fd40  cmp     dword ptr [r15+rdx*4+0AD8h], 1
0x14001fd49  jnz     short loc_14001FD13
0x14001fd4b  mov     ecx, edx
0x14001fd4d  mov     eax, 1
0x14001fd52  shl     eax, cl
0x14001fd54  or      [r15+0B18h], eax
0x14001fd5b  mov     [rdi+190h], edx
0x14001fd61  jmp     short loc_14001FD21
0x14001fd63  mov     rcx, rax; Set
0x14001fd66  call    cs:__imp_RtlFindMostSignificantBit
0x14001fd6d  nop     dword ptr [rax+rax+00h]
0x14001fd72  movsx   ecx, al
0x14001fd75  mov     [r15+0F4h], ecx
0x14001fd7c  jmp     loc_14001FC3C
0x14001fd81  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14001fd88  nop     dword ptr [rax+rax+00h]
0x14001fd8d  jmp     loc_14001FC82
0x14001fd92  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14001fd99  nop     dword ptr [rax+rax+00h]
0x14001fd9e  jmp     loc_14001FBBA
```
