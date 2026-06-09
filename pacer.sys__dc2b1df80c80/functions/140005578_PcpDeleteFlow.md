# PcpDeleteFlow

- ea: `0x140005578`
- end: `0x140005706`
- name: `PcpDeleteFlow`
- size: `398`
- prototype: `__int64 __fastcall(char *P, __int64)`
- caller_count: `11`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x140005438`
- `0x140005c10`
- `0x140009100`
- `0x14000a7f0`
- `0x14000aaa4`
- `0x14000d708`
- `0x14000dc3c`
- `0x14000de40`
- `0x1400100d0`
- `0x14001db60`
- `0x14001deb0`

## callees

- `0x140001fec`
- `0x1400026c4`
- `0x140002d48`
- `0x140003770`
- `0x140005578`
- `0x14000aca4`
- `0x14000b584`
- `0x14000bc84`
- `0x140011154`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400056cf`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400056cf`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400056b1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400056b1`
- `NDIS!NdisReleaseRWLock` at `0x14000566a`
- `NDIS!NdisReleaseRWLock` at `0x14000566a`
- `NDIS!NdisAcquireRWLockWrite` at `0x140005632`
- `NDIS!NdisAcquireRWLockWrite` at `0x140005632`

## pseudocode

```c
__int64 __fastcall PcpDeleteFlow(char *P, __int64 a2)
{
  unsigned int *v2; // rsi
  int v4; // eax
  __int64 v5; // rax
  PNDIS_RW_LOCK_EX *v6; // rdi
  unsigned int v7; // ecx
  char v8; // r14
  struct _NDIS_RW_LOCK_EX *v9; // rcx
  signed __int32 v10; // eax
  bool v11; // cc
  __int64 result; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-40h] BYREF
  _OWORD v14[2]; // [rsp+38h] [rbp-28h] BYREF
  int v15; // [rsp+80h] [rbp+20h] BYREF
  __int64 LockState; // [rsp+88h] [rbp+28h] BYREF

  LockState = a2;
  v2 = (unsigned int *)(P + 456);
  LOWORD(LockState) = 0;
  BYTE2(LockState) = 0;
  v4 = *((_DWORD *)P + 12);
  memset(&LockHandle, 0, sizeof(LockHandle));
  memset(v14, 0, sizeof(v14));
  if ( (_BYTE)v4 == 1 )
  {
    v5 = PcpLineFindByInstanceName((void *)(*((_QWORD *)P + 75) + 2LL));
  }
  else
  {
    if ( *v2 - 1 > 0x270F )
      goto LABEL_11;
    v5 = PcpLineFindByLuid(*((_QWORD *)P + 11));
  }
  v6 = (PNDIS_RW_LOCK_EX *)v5;
  if ( v5 )
  {
    v7 = *v2;
    v8 = 0;
    if ( *v2 - 1 <= 0x270F )
    {
      *(_QWORD *)&v14[0] = v7;
      v8 = 1;
      DWORD2(v14[0]) = -v7;
      HIDWORD(v14[0]) = -1;
    }
    v9 = *(struct _NDIS_RW_LOCK_EX **)(v5 + 16);
    v15 = -1;
    NdisAcquireRWLockWrite(v9, (PLOCK_STATE_EX)&LockState, 0);
    if ( v8 )
      ((void (__fastcall *)(PNDIS_RW_LOCK_EX *, _QWORD, _QWORD, _OWORD *, struct _KSPIN_LOCK_QUEUE *volatile, volatile PKSPIN_LOCK, _QWORD))QosLineUpdate)(
        v6 + 3,
        0,
        0,
        v14,
        LockHandle.LockQueue.Next,
        LockHandle.LockQueue.Lock,
        *(_QWORD *)&LockHandle.OldIrql);
    QosLineUpdateStats(v6 + 3, &v15);
    NdisReleaseRWLock(v6[2], (PLOCK_STATE_EX)&LockState);
    PcpTcNotify((__int64)v6, -83820282, v6 + 6, 4u);
    PcpLineDereference(v6);
  }
LABEL_11:
  if ( (*((_DWORD *)P + 154) & 2) != 0 )
    PcpFilterDecrementIntercept(1);
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)P + 12, &LockHandle);
  while ( *((_DWORD *)P + 26) )
    ;
  *((_DWORD *)P + 154) |= 8u;
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  v10 = _InterlockedExchangeAdd((volatile signed __int32 *)P + 8, 0xFFFFFFFF);
  v11 = v10 <= 1;
  result = (unsigned int)(v10 - 1);
  if ( v11 )
    return PcpCleanupFlow(P);
  return result;
}

```

## disassembly

```asm
0x140005578  mov     [rsp-18h+arg_10], rbx
0x14000557d  mov     [rsp-18h+arg_18], rsi
0x140005582  mov     [rsp-18h+LockState], rdx
0x140005587  push    rbp
0x140005588  push    rdi
0x140005589  push    r14
0x14000558b  mov     rbp, rsp
0x14000558e  sub     rsp, 60h
0x140005592  xor     eax, eax
0x140005594  lea     rsi, [rcx+1C8h]
0x14000559b  xorps   xmm0, xmm0
0x14000559e  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x1400055a2  mov     word ptr [rbp+LockState], ax
0x1400055a6  mov     rbx, rcx
0x1400055a9  mov     byte ptr [rbp+LockState+2], al
0x1400055ac  mov     eax, [rcx+30h]
0x1400055af  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x1400055b3  movups  [rbp+var_28], xmm0
0x1400055b7  movups  [rbp+var_18], xmm0
0x1400055bb  cmp     al, 1
0x1400055bd  jz      short loc_1400055D9
0x1400055bf  mov     eax, [rsi]
0x1400055c1  dec     eax
0x1400055c3  cmp     eax, 270Fh
0x1400055c8  ja      loc_140005695
0x1400055ce  mov     rcx, [rcx+58h]
0x1400055d2  call    PcpLineFindByLuid
0x1400055d7  jmp     short loc_1400055EC
0x1400055d9  mov     rdx, [rcx+258h]
0x1400055e0  lea     rcx, [rdx+2]; Buf1
0x1400055e4  movzx   edx, word ptr [rdx]
0x1400055e7  call    PcpLineFindByInstanceName
0x1400055ec  mov     rdi, rax
0x1400055ef  test    rax, rax
0x1400055f2  jz      loc_140005695
0x1400055f8  mov     ecx, [rsi]
0x1400055fa  xor     r14b, r14b
0x1400055fd  lea     eax, [rcx-1]
0x140005600  cmp     eax, 270Fh
0x140005605  ja      short loc_140005620
0x140005607  mov     dword ptr [rbp+var_28], ecx
0x14000560a  mov     r14b, 1
0x14000560d  neg     ecx
0x14000560f  mov     dword ptr [rbp+var_28+4], 0
0x140005616  mov     dword ptr [rbp+var_28+8], ecx
0x140005619  mov     dword ptr [rbp+var_28+0Ch], 0FFFFFFFFh
0x140005620  mov     rcx, [rdi+10h]; Lock
0x140005624  lea     rdx, [rbp+LockState]; LockState
0x140005628  xor     r8d, r8d; Flags
0x14000562b  mov     [rbp+arg_0], 0FFFFFFFFh
0x140005632  call    cs:__imp_NdisAcquireRWLockWrite
0x140005639  nop     dword ptr [rax+rax+00h]
0x14000563e  test    r14b, r14b
0x140005641  jz      short loc_140005655
0x140005643  lea     rcx, [rdi+18h]
0x140005647  xor     r8d, r8d
0x14000564a  lea     r9, [rbp+var_28]
0x14000564e  xor     edx, edx
0x140005650  call    QosLineUpdate
0x140005655  lea     rcx, [rdi+18h]
0x140005659  lea     rdx, [rbp+arg_0]
0x14000565d  call    QosLineUpdateStats
0x140005662  mov     rcx, [rdi+10h]; Lock
0x140005666  lea     rdx, [rbp+LockState]; LockState
0x14000566a  call    cs:__imp_NdisReleaseRWLock
0x140005671  nop     dword ptr [rax+rax+00h]
0x140005676  lea     r8, [rdi+30h]
0x14000567a  mov     edx, 0FB010106h
0x14000567f  mov     r9d, 4
0x140005685  mov     rcx, rdi
0x140005688  call    PcpTcNotify
0x14000568d  mov     rcx, rdi; P
0x140005690  call    PcpLineDereference
0x140005695  mov     eax, [rbx+268h]
0x14000569b  test    al, 2
0x14000569d  jz      short loc_1400056A9
0x14000569f  mov     ecx, 1
0x1400056a4  call    PcpFilterDecrementIntercept
0x1400056a9  lea     rdx, [rbp+LockHandle]; LockHandle
0x1400056ad  lea     rcx, [rbx+60h]; SpinLock
0x1400056b1  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400056b8  nop     dword ptr [rax+rax+00h]
0x1400056bd  mov     eax, [rbx+68h]
0x1400056c0  test    eax, eax
0x1400056c2  jnz     short loc_1400056BD
0x1400056c4  or      dword ptr [rbx+268h], 8
0x1400056cb  lea     rcx, [rbp+LockHandle]; LockHandle
0x1400056cf  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400056d6  nop     dword ptr [rax+rax+00h]
0x1400056db  or      eax, 0FFFFFFFFh
0x1400056de  lock xadd [rbx+20h], eax
0x1400056e3  sub     eax, 1
0x1400056e6  jg      short loc_1400056F0
0x1400056e8  mov     rcx, rbx; P
0x1400056eb  call    PcpCleanupFlow
0x1400056f0  lea     r11, [rsp+60h+var_s0]
0x1400056f5  mov     rbx, [r11+30h]
0x1400056f9  mov     rsi, [r11+38h]
0x1400056fd  mov     rsp, r11
0x140005700  pop     r14
0x140005702  pop     rdi
0x140005703  pop     rbp
0x140005704  retn
```
