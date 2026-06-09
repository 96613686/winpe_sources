# UlpQueryRequestQueueLengthLimit

- ea: `0x1c0029c54`
- end: `0x1c0029d44`
- name: `UlpQueryRequestQueueLengthLimit`
- size: `240`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1c00a0f8c`

## callees

- `0x1c0029c54`
- `0x1c008f374`
- `0x1c008f3ec`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1c0029cec`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1c0029cec`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1c0029ccc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1c0029ccc`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c0029cfd`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c0029cfd`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1c0029cae`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1c0029cae`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0029d09`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0029d09`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0029c99`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0029c99`

## pseudocode

```c
__int64 __fastcall UlpQueryRequestQueueLengthLimit(__int64 a1, _DWORD *a2)
{
  __int64 v4; // rbx
  __int64 result; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_qq(144, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids, a1, a2);
  KeEnterCriticalRegion();
  v4 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(a1 + 280), 0);
  KeAcquireInStackQueuedSpinLock(**(PKSPIN_LOCK **)(a1 + 288), &LockHandle);
  *a2 = *(_DWORD *)(**(_QWORD **)(a1 + 288) + 96LL);
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  ExReleaseCacheAwarePushLockSharedEx(v4, 0);
  KeLeaveCriticalRegion();
  result = LODWORD(WPP_MAIN_CB.Queue.ListEntry.Flink);
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    return WPP_SF_D(145, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids);
  return result;
}

```

## disassembly

```asm
0x1c0029c54  mov     [rsp+arg_0], rbx
0x1c0029c59  mov     [rsp+arg_8], rsi
0x1c0029c5e  push    rdi
0x1c0029c5f  sub     rsp, 40h
0x1c0029c63  xorps   xmm0, xmm0
0x1c0029c66  xor     eax, eax
0x1c0029c68  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x1c0029c6d  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rax
0x1c0029c72  mov     rdi, rdx
0x1c0029c75  mov     rsi, rcx
0x1c0029c78  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c0029c7e  test    al, al
0x1c0029c80  jns     short loc_1C0029C99
0x1c0029c82  mov     r9, rdx
0x1c0029c85  mov     ecx, 90h
0x1c0029c8a  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c0029c91  mov     r8, rsi
0x1c0029c94  call    WPP_SF_qq
0x1c0029c99  call    cs:__imp_KeEnterCriticalRegion
0x1c0029ca0  nop     dword ptr [rax+rax+00h]
0x1c0029ca5  mov     rcx, [rsi+118h]
0x1c0029cac  xor     edx, edx
0x1c0029cae  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x1c0029cb5  nop     dword ptr [rax+rax+00h]
0x1c0029cba  mov     rcx, [rsi+120h]
0x1c0029cc1  lea     rdx, [rsp+48h+LockHandle]; LockHandle
0x1c0029cc6  mov     rbx, rax
0x1c0029cc9  mov     rcx, [rcx]; SpinLock
0x1c0029ccc  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1c0029cd3  nop     dword ptr [rax+rax+00h]
0x1c0029cd8  mov     rcx, [rsi+120h]
0x1c0029cdf  mov     rdx, [rcx]
0x1c0029ce2  mov     ecx, [rdx+60h]
0x1c0029ce5  mov     [rdi], ecx
0x1c0029ce7  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x1c0029cec  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1c0029cf3  nop     dword ptr [rax+rax+00h]
0x1c0029cf8  xor     edx, edx
0x1c0029cfa  mov     rcx, rbx
0x1c0029cfd  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1c0029d04  nop     dword ptr [rax+rax+00h]
0x1c0029d09  call    cs:__imp_KeLeaveCriticalRegion
0x1c0029d10  nop     dword ptr [rax+rax+00h]
0x1c0029d15  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c0029d1b  test    al, al
0x1c0029d1d  jns     short loc_1C0029D33
0x1c0029d1f  mov     r8d, [rdi]
0x1c0029d22  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c0029d29  mov     ecx, 91h
0x1c0029d2e  call    WPP_SF_D
0x1c0029d33  mov     rbx, [rsp+48h+arg_0]
0x1c0029d38  mov     rsi, [rsp+48h+arg_8]
0x1c0029d3d  add     rsp, 40h
0x1c0029d41  pop     rdi
0x1c0029d42  retn
```
