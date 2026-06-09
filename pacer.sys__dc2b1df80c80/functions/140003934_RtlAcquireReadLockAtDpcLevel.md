# RtlAcquireReadLockAtDpcLevel

- ea: `0x140003934`
- end: `0x140003994`
- name: `RtlAcquireReadLockAtDpcLevel`
- size: `96`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140002be0`
- `0x140002e80`
- `0x140005438`
- `0x14000de40`

## callees

- `0x140003934`

## import_xrefs

- `ntoskrnl!KeTestSpinLock` at `0x140003950`
- `ntoskrnl!KeTestSpinLock` at `0x140003950`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140003981`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140003981`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000396c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000396c`

## pseudocode

```c
void __fastcall RtlAcquireReadLockAtDpcLevel(volatile signed __int32 *SpinLock)
{
  _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  _InterlockedIncrement(SpinLock + 2);
  if ( !KeTestSpinLock((PKSPIN_LOCK)SpinLock) )
  {
    _InterlockedDecrement(SpinLock + 2);
    KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)SpinLock, &LockHandle);
    _InterlockedIncrement(SpinLock + 2);
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  }
}

```

## disassembly

```asm
0x140003934  push    rbx
0x140003936  sub     rsp, 40h
0x14000393a  xorps   xmm0, xmm0
0x14000393d  xor     eax, eax
0x14000393f  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x140003944  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rax
0x140003949  mov     rbx, rcx
0x14000394c  lock inc dword ptr [rcx+8]
0x140003950  call    cs:__imp_KeTestSpinLock
0x140003957  nop     dword ptr [rax+rax+00h]
0x14000395c  test    al, al
0x14000395e  jnz     short loc_14000398D
0x140003960  lock dec dword ptr [rbx+8]
0x140003964  lea     rdx, [rsp+48h+LockHandle]; LockHandle
0x140003969  mov     rcx, rbx; SpinLock
0x14000396c  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140003973  nop     dword ptr [rax+rax+00h]
0x140003978  lock inc dword ptr [rbx+8]
0x14000397c  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x140003981  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140003988  nop     dword ptr [rax+rax+00h]
0x14000398d  add     rsp, 40h
0x140003991  pop     rbx
0x140003992  retn
```
