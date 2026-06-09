# StartTimer

- ea: `0x14000bbcc`
- end: `0x14000bdf5`
- name: `StartTimer`
- size: `553`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x14000ebe0`
- `0x140012694`
- `0x140013f20`
- `0x140017a3c`
- `0x1400194cc`
- `0x140024920`
- `0x140025144`
- `0x140027200`
- `0x140028144`
- `0x14004420c`

## callees

- `0x140006900`
- `0x14000bbcc`
- `0x14000bdfc`

## import_xrefs

- `ntoskrnl!KeInitializeDpc` at `0x14000bcd1`
- `ntoskrnl!KeInitializeDpc` at `0x14000bcd1`
- `ntoskrnl!KeSetCoalescableTimer` at `0x14000bd0d`
- `ntoskrnl!KeSetCoalescableTimer` at `0x14000bd0d`
- `ntoskrnl!KeSetTimer` at `0x14000bdb1`
- `ntoskrnl!KeSetTimer` at `0x14000bdb1`
- `ntoskrnl!KeInitializeTimer` at `0x14000bcad`
- `ntoskrnl!KeInitializeTimer` at `0x14000bcad`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000bd97`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000bd97`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000bd82`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000bd82`

## pseudocode

```c
__int64 __fastcall StartTimer(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        _QWORD *a8,
        __int16 a9,
        char a10)
{
  KIRQL v13; // r14
  __int64 v14; // rbx
  int TimerEntry; // esi
  _QWORD *v16; // rdi
  __int64 v17; // rax
  __int64 v18; // r12
  struct _KTIMER *v19; // rcx
  _QWORD *v20; // rax
  PVOID DeferredContext; // [rsp+78h] [rbp+20h] BYREF

  DeferredContext = 0;
  if ( byte_140039752 )
    return 3221225473LL;
  v13 = -1;
  if ( !a10 )
    v13 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  v14 = a7;
  if ( !a7 )
    goto LABEL_7;
  if ( *(_DWORD *)(a7 + 360) == 1131832644 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(a7 + 364));
    ++*(_DWORD *)(v14 + 1092);
LABEL_7:
    TimerEntry = GetTimerEntry(&DeferredContext);
    if ( TimerEntry < 0 )
    {
      if ( v14 )
        NBT_DEREFERENCE_DEVICE(v14, 2u, 1);
    }
    else
    {
      v16 = DeferredContext;
      v17 = a6;
      *((_DWORD *)DeferredContext + 6) = a2;
      *((_BYTE *)v16 + 23) = 1;
      v16[6] = a3;
      v16[7] = 0;
      v16[5] = a1;
      *((_WORD *)v16 + 128) = 0;
      v16[8] = a5;
      v16[9] = v17;
      *((_WORD *)v16 + 10) = a9;
      v16[4] = v14;
      KeInitializeTimer((PKTIMER)v16 + 3);
      v18 = *((unsigned int *)v16 + 6);
      KeInitializeDpc((PRKDPC)v16 + 2, TimerExpiry, v16);
      v19 = (struct _KTIMER *)(v16 + 24);
      if ( (unsigned int)v18 >= 0x2710 )
        KeSetTimer(v19, (LARGE_INTEGER)(-10000 * v18), (PKDPC)v16 + 2);
      else
        KeSetCoalescableTimer(v19, (LARGE_INTEGER)(-10000 * v18), 0, (unsigned int)v18 / 0xA, (PKDPC)v16 + 2);
      if ( a8 )
        *a8 = v16;
      v20 = TimerQ;
      if ( *((PVOID **)TimerQ + 1) != &TimerQ )
        __fastfail(3u);
      *v16 = TimerQ;
      v16[1] = &TimerQ;
      v20[1] = v16;
      TimerQ = v16;
    }
    goto LABEL_14;
  }
  TimerEntry = -1073741436;
LABEL_14:
  if ( !a10 )
    KeReleaseSpinLock(&SpinLock, v13);
  return (unsigned int)TimerEntry;
}

```

## disassembly

```asm
0x14000bbcc  mov     rax, rsp
0x14000bbcf  mov     [rax+8], rbx
0x14000bbd3  mov     [rax+10h], rsi
0x14000bbd7  mov     [rax+20h], r9
0x14000bbdb  push    rdi
0x14000bbdc  push    r12
0x14000bbde  push    r13
0x14000bbe0  push    r14
0x14000bbe2  push    r15
0x14000bbe4  sub     rsp, 30h
0x14000bbe8  cmp     cs:byte_140039752, 0
0x14000bbef  mov     r15, r8
0x14000bbf2  mov     r12d, edx
0x14000bbf5  mov     qword ptr [rax+20h], 0
0x14000bbfd  mov     r13, rcx
0x14000bc00  jnz     loc_14000BDC2
0x14000bc06  cmp     [rsp+58h+arg_48], 0
0x14000bc0e  mov     r14b, 0FFh
0x14000bc11  jz      loc_14000BD90
0x14000bc17  mov     rbx, [rsp+58h+arg_30]
0x14000bc1f  test    rbx, rbx
0x14000bc22  jz      short loc_14000BC41
0x14000bc24  cmp     dword ptr [rbx+168h], 43766544h
0x14000bc2e  jnz     loc_14000BDC9
0x14000bc34  lock inc dword ptr [rbx+16Ch]
0x14000bc3b  inc     dword ptr [rbx+444h]
0x14000bc41  lea     rcx, [rsp+58h+DeferredContext]
0x14000bc46  call    GetTimerEntry
0x14000bc4b  mov     esi, eax
0x14000bc4d  test    eax, eax
0x14000bc4f  js      loc_14000BDD7
0x14000bc55  mov     rdi, [rsp+58h+DeferredContext]
0x14000bc5a  xor     ecx, ecx
0x14000bc5c  mov     rax, [rsp+58h+arg_28]
0x14000bc64  mov     [rdi+18h], r12d
0x14000bc68  mov     byte ptr [rdi+17h], 1
0x14000bc6c  mov     [rdi+30h], r15
0x14000bc70  mov     qword ptr [rdi+38h], 0
0x14000bc78  mov     [rdi+28h], r13
0x14000bc7c  mov     [rdi+100h], cx
0x14000bc83  mov     rcx, [rsp+58h+arg_20]
0x14000bc8b  mov     [rdi+40h], rcx
0x14000bc8f  mov     [rdi+48h], rax
0x14000bc93  movzx   eax, [rsp+58h+arg_40]
0x14000bc9b  mov     [rdi+14h], ax
0x14000bc9f  mov     [rdi+20h], rbx
0x14000bca3  lea     rbx, [rdi+0C0h]
0x14000bcaa  mov     rcx, rbx; Timer
0x14000bcad  call    cs:__imp_KeInitializeTimer
0x14000bcb4  nop     dword ptr [rax+rax+00h]
0x14000bcb9  mov     r12d, [rdi+18h]
0x14000bcbd  lea     r15, [rdi+80h]
0x14000bcc4  mov     rcx, r15; Dpc
0x14000bcc7  lea     rdx, TimerExpiry; DeferredRoutine
0x14000bcce  mov     r8, rdi; DeferredContext
0x14000bcd1  call    cs:__imp_KeInitializeDpc
0x14000bcd8  nop     dword ptr [rax+rax+00h]
0x14000bcdd  imul    r10, r12, 0FFFFFFFFFFFFD8F0h
0x14000bce4  mov     rcx, rbx; Timer
0x14000bce7  cmp     r12d, 2710h
0x14000bcee  jnb     loc_14000BDAB
0x14000bcf4  mov     eax, 0CCCCCCCDh
0x14000bcf9  mov     [rsp+58h+Dpc], r15; Dpc
0x14000bcfe  mul     r12d
0x14000bd01  xor     r8d, r8d; Period
0x14000bd04  shr     edx, 3
0x14000bd07  mov     r9d, edx; TolerableDelay
0x14000bd0a  mov     rdx, r10; DueTime
0x14000bd0d  call    cs:__imp_KeSetCoalescableTimer
0x14000bd14  nop     dword ptr [rax+rax+00h]
0x14000bd19  mov     rax, [rsp+58h+arg_38]
0x14000bd21  test    rax, rax
0x14000bd24  jz      short loc_14000BD29
0x14000bd26  mov     [rax], rdi
0x14000bd29  mov     rax, cs:TimerQ
0x14000bd30  lea     rcx, TimerQ
0x14000bd37  cmp     [rax+8], rcx
0x14000bd3b  jnz     loc_14000BDD0
0x14000bd41  mov     [rdi], rax
0x14000bd44  mov     [rdi+8], rcx
0x14000bd48  mov     [rax+8], rdi
0x14000bd4c  mov     cs:TimerQ, rdi
0x14000bd53  cmp     [rsp+58h+arg_48], 0
0x14000bd5b  jz      short loc_14000BD78
0x14000bd5d  mov     eax, esi
0x14000bd5f  mov     rbx, [rsp+58h+arg_0]
0x14000bd64  mov     rsi, [rsp+58h+arg_8]
0x14000bd69  add     rsp, 30h
0x14000bd6d  pop     r15
0x14000bd6f  pop     r14
0x14000bd71  pop     r13
0x14000bd73  pop     r12
0x14000bd75  pop     rdi
0x14000bd76  retn
0x14000bd78  mov     dl, r14b; NewIrql
0x14000bd7b  lea     rcx, SpinLock; SpinLock
0x14000bd82  call    cs:__imp_KeReleaseSpinLock
0x14000bd89  nop     dword ptr [rax+rax+00h]
0x14000bd8e  jmp     short loc_14000BD5D
0x14000bd90  lea     rcx, SpinLock; SpinLock
0x14000bd97  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000bd9e  nop     dword ptr [rax+rax+00h]
0x14000bda3  mov     r14b, al
0x14000bda6  jmp     loc_14000BC17
0x14000bdab  mov     r8, r15; Dpc
0x14000bdae  mov     rdx, r10; DueTime
0x14000bdb1  call    cs:__imp_KeSetTimer
0x14000bdb8  nop     dword ptr [rax+rax+00h]
0x14000bdbd  jmp     loc_14000BD19
0x14000bdc2  mov     eax, 0C0000001h
0x14000bdc7  jmp     short loc_14000BD5F
0x14000bdc9  mov     esi, 0C0000184h
0x14000bdce  jmp     short loc_14000BD53
0x14000bdd0  mov     ecx, 3
0x14000bdd5  int     29h; Win8: RtlFailFast(ecx)
0x14000bdd7  test    rbx, rbx
0x14000bdda  jz      loc_14000BD53
0x14000bde0  mov     r8b, 1
0x14000bde3  mov     edx, 2
0x14000bde8  mov     rcx, rbx
0x14000bdeb  call    NBT_DEREFERENCE_DEVICE
0x14000bdf0  jmp     loc_14000BD53
```
