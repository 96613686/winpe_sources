# VidSchiAdjustWorkerThreadPriority

- ea: `0x1400229f0`
- end: `0x140022cc3`
- name: `VidSchiAdjustWorkerThreadPriority`
- size: `723`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140020e00`
- `0x140050728`
- `0x1400dd5f0`

## callees

- `0x1400229f0`
- `0x1400442d0`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140022ac9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140022bd2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140022ac9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140022bd2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140022b0e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140022b96`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140022b0e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140022b96`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140022cb2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140022cb2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140022bf0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140022ca1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140022bf0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140022ca1`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x140022c86`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x140022c86`
- `ntoskrnl!KeQueryPriorityThread` at `0x140022a46`
- `ntoskrnl!KeQueryPriorityThread` at `0x140022a66`
- `ntoskrnl!KeQueryPriorityThread` at `0x140022b6a`
- `ntoskrnl!KeQueryPriorityThread` at `0x140022a46`
- `ntoskrnl!KeQueryPriorityThread` at `0x140022a66`
- `ntoskrnl!KeQueryPriorityThread` at `0x140022b6a`
- `ntoskrnl!KeSetPriorityThread` at `0x140022bb1`
- `ntoskrnl!KeSetPriorityThread` at `0x140022bb1`

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
0x1400229f0  mov     r11, rsp
0x1400229f3  push    rbx
0x1400229f4  push    rdi
0x1400229f5  sub     rsp, 58h
0x1400229f9  mov     rbx, [rcx+60h]
0x1400229fd  mov     rdi, rcx
0x140022a00  mov     rbx, [rbx+18h]
0x140022a04  mov     eax, [rbx+0B58h]
0x140022a0a  test    al, 2
0x140022a0c  jnz     loc_140022B2F
0x140022a12  test    al, 20h
0x140022a14  jz      short loc_140022A93
0x140022a16  mov     rax, gs:188h
0x140022a1f  mov     [r11+10h], rbp
0x140022a23  mov     [r11+18h], rsi
0x140022a27  mov     [r11+20h], r14
0x140022a2b  cmp     rax, [rbx+0B8h]
0x140022a32  jz      short loc_140022A9B
0x140022a34  cmp     rax, [rbx+0C0h]
0x140022a3b  jz      short loc_140022A9B
0x140022a3d  mov     rcx, gs:188h; Thread
0x140022a46  call    cs:__imp_KeQueryPriorityThread
0x140022a4d  nop     dword ptr [rax+rax+00h]
0x140022a52  inc     eax
0x140022a54  cmp     eax, 1Fh
0x140022a57  jge     loc_140022B1F
0x140022a5d  mov     rcx, gs:188h; Thread
0x140022a66  call    cs:__imp_KeQueryPriorityThread
0x140022a6d  nop     dword ptr [rax+rax+00h]
0x140022a72  lea     esi, [rax+1]
0x140022a75  cmp     esi, 10h
0x140022a78  jg      loc_140022B24
0x140022a7e  mov     rsi, [rsp+68h+arg_10]
0x140022a86  mov     rbp, [rsp+68h+arg_8]
0x140022a8b  mov     r14, [rsp+68h+arg_18]
0x140022a93  add     rsp, 58h
0x140022a97  pop     rdi
0x140022a98  pop     rbx
0x140022a99  retn
0x140022a9b  mov     eax, [rcx+314h]
0x140022aa1  test    eax, eax
0x140022aa3  jnz     short loc_140022A7E
0x140022aa5  mov     r14d, 10h
0x140022aab  mov     bpl, 1
0x140022aae  mov     esi, r14d
0x140022ab1  lea     rcx, [rbx+0B10h]; SpinLock
0x140022ab8  mov     [rsp+68h+var_28], 0
0x140022abf  lea     rdx, [rsp+68h+LockHandle]; LockHandle
0x140022ac4  mov     [rsp+68h+SpinLock], rcx
0x140022ac9  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140022ad0  nop     dword ptr [rax+rax+00h]
0x140022ad5  mov     [rsp+68h+var_18], r15
0x140022ada  mov     eax, [rdi+314h]
0x140022ae0  mov     byte ptr [rsp+68h+var_28], 1
0x140022ae5  test    bpl, bpl
0x140022ae8  jz      loc_140022BE3
0x140022aee  test    eax, eax
0x140022af0  jz      short loc_140022B3C
0x140022af2  cmp     byte ptr [rsp+68h+var_28], 0
0x140022af7  mov     r15, [rsp+68h+var_18]
0x140022afc  jz      short loc_140022A7E
0x140022afe  cmp     byte ptr [rsp+68h+var_28+1], 0
0x140022b03  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x140022b08  jnz     loc_140022BF0
0x140022b0e  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140022b15  nop     dword ptr [rax+rax+00h]
0x140022b1a  jmp     loc_140022A7E
0x140022b1f  mov     esi, 1Fh
0x140022b24  xor     bpl, bpl
0x140022b27  mov     r14d, 10h
0x140022b2d  jmp     short loc_140022AB1
0x140022b2f  call    VidSchiAdjustWorkerThreadPriorityDirectSubmitAware
0x140022b34  add     rsp, 58h
0x140022b38  pop     rdi
0x140022b39  pop     rbx
0x140022b3a  retn
0x140022b3c  mov     rax, [rdi+60h]
0x140022b40  cmp     esi, 10h
0x140022b43  mov     edx, esi
0x140022b45  cmovb   edx, r14d
0x140022b49  mov     r15, [rax+18h]
0x140022b4d  movsxd  rax, dword ptr [rdi+190h]
0x140022b54  cmp     eax, edx
0x140022b56  jnz     loc_140022C01
0x140022b5c  mov     rcx, [rbx+0B8h]; Thread
0x140022b63  mov     r15d, [r15+0F4h]
0x140022b6a  call    cs:__imp_KeQueryPriorityThread
0x140022b71  nop     dword ptr [rax+rax+00h]
0x140022b76  cmp     r15d, eax
0x140022b79  jz      loc_140022AF2
0x140022b7f  cmp     byte ptr [rsp+68h+var_28], 0
0x140022b84  jz      short loc_140022BA7
0x140022b86  cmp     byte ptr [rsp+68h+var_28+1], 0
0x140022b8b  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x140022b90  jnz     loc_140022CA1
0x140022b96  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140022b9d  nop     dword ptr [rax+rax+00h]
0x140022ba2  mov     byte ptr [rsp+68h+var_28], 0
0x140022ba7  mov     rcx, [rbx+0B8h]; Thread
0x140022bae  mov     edx, r15d; Priority
0x140022bb1  call    cs:__imp_KeSetPriorityThread
0x140022bb8  nop     dword ptr [rax+rax+00h]
0x140022bbd  cmp     byte ptr [rsp+68h+var_28+1], 0
0x140022bc2  lea     rdx, [rsp+68h+LockHandle]; LockHandle
0x140022bc7  mov     rcx, [rsp+68h+SpinLock]; SpinLock
0x140022bcc  jnz     loc_140022CB2
0x140022bd2  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140022bd9  nop     dword ptr [rax+rax+00h]
0x140022bde  jmp     loc_140022ADA
0x140022be3  test    eax, eax
0x140022be5  jz      loc_140022AF2
0x140022beb  jmp     loc_140022B3C
0x140022bf0  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140022bf7  nop     dword ptr [rax+rax+00h]
0x140022bfc  jmp     loc_140022A7E
0x140022c01  xor     ecx, ecx
0x140022c03  cmp     eax, 10h
0x140022c06  jle     short loc_140022C2E
0x140022c08  add     dword ptr [r15+rax*4+0AD8h], 0FFFFFFFFh
0x140022c11  jnz     short loc_140022C2E
0x140022c13  mov     ecx, [rdi+190h]
0x140022c19  mov     eax, 1
0x140022c1e  shl     eax, cl
0x140022c20  mov     ecx, 1
0x140022c25  not     eax
0x140022c27  and     [r15+0B18h], eax
0x140022c2e  cmp     edx, 10h
0x140022c31  ja      short loc_140022C58
0x140022c33  mov     [rdi+190h], edx
0x140022c39  test    ecx, ecx
0x140022c3b  jz      loc_140022B5C
0x140022c41  mov     eax, [r15+0B18h]
0x140022c48  test    eax, eax
0x140022c4a  jnz     short loc_140022C83
0x140022c4c  mov     [r15+0F4h], r14d
0x140022c53  jmp     loc_140022B5C
0x140022c58  inc     dword ptr [r15+rdx*4+0AD8h]
0x140022c60  cmp     dword ptr [r15+rdx*4+0AD8h], 1
0x140022c69  jnz     short loc_140022C33
0x140022c6b  mov     ecx, edx
0x140022c6d  mov     eax, 1
0x140022c72  shl     eax, cl
0x140022c74  or      [r15+0B18h], eax
0x140022c7b  mov     [rdi+190h], edx
0x140022c81  jmp     short loc_140022C41
0x140022c83  mov     rcx, rax; Set
0x140022c86  call    cs:__imp_RtlFindMostSignificantBit
0x140022c8d  nop     dword ptr [rax+rax+00h]
0x140022c92  movsx   ecx, al
0x140022c95  mov     [r15+0F4h], ecx
0x140022c9c  jmp     loc_140022B5C
0x140022ca1  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140022ca8  nop     dword ptr [rax+rax+00h]
0x140022cad  jmp     loc_140022BA2
0x140022cb2  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140022cb9  nop     dword ptr [rax+rax+00h]
0x140022cbe  jmp     loc_140022ADA
```
