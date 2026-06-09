# UlpQueryRequestQueueLengthLimit

- ea: `0x1400cf948`
- end: `0x1400cfa43`
- name: `UlpQueryRequestQueueLengthLimit`
- size: `251`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400a44d8`

## callees

- `0x1400cf948`
- `0x1401c3008`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400cf9c5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400cf9c5`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400cf9a7`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400cf9a7`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400cf9f8`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400cf9f8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400cf9e7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400cf9e7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cfa04`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cfa04`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400cf992`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400cf992`

## pseudocode

```c
void __fastcall UlpQueryRequestQueueLengthLimit(__int64 a1, _DWORD *a2)
{
  __int64 v4; // rbx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-28h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qq(1032, 151, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, a1, a2);
  KeEnterCriticalRegion();
  v4 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(a1 + 280), 0);
  KeAcquireInStackQueuedSpinLock(**(PKSPIN_LOCK **)(a1 + 288), &LockHandle);
  *a2 = *(_DWORD *)(**(_QWORD **)(a1 + 288) + 104LL);
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  ExReleaseCacheAwarePushLockSharedEx(v4, 0);
  KeLeaveCriticalRegion();
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_d(1032, 152, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, (unsigned int)*a2);
}

```

## disassembly

```asm
0x1400cf948  mov     r11, rsp
0x1400cf94b  mov     [r11+8], rbx
0x1400cf94f  mov     [r11+10h], rsi
0x1400cf953  push    rdi
0x1400cf954  sub     rsp, 50h
0x1400cf958  xorps   xmm0, xmm0
0x1400cf95b  xor     eax, eax
0x1400cf95d  movups  xmmword ptr [rsp+58h+LockHandle.LockQueue.Next], xmm0
0x1400cf962  mov     [r11-18h], rax
0x1400cf966  mov     rdi, rdx
0x1400cf969  mov     rsi, rcx
0x1400cf96c  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400cf973  jz      short loc_1400CF992
0x1400cf975  mov     edx, 97h
0x1400cf97a  mov     [r11-38h], rdi
0x1400cf97e  mov     ecx, 408h
0x1400cf983  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400cf98a  mov     r9, rsi
0x1400cf98d  call    WPP_SF_qq
0x1400cf992  call    cs:__imp_KeEnterCriticalRegion
0x1400cf999  nop     dword ptr [rax+rax+00h]
0x1400cf99e  mov     rcx, [rsi+118h]
0x1400cf9a5  xor     edx, edx
0x1400cf9a7  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x1400cf9ae  nop     dword ptr [rax+rax+00h]
0x1400cf9b3  mov     rcx, [rsi+120h]
0x1400cf9ba  lea     rdx, [rsp+58h+LockHandle]; LockHandle
0x1400cf9bf  mov     rbx, rax
0x1400cf9c2  mov     rcx, [rcx]; SpinLock
0x1400cf9c5  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400cf9cc  nop     dword ptr [rax+rax+00h]
0x1400cf9d1  mov     rcx, [rsi+120h]
0x1400cf9d8  mov     rdx, [rcx]
0x1400cf9db  lea     rcx, [rsp+58h+LockHandle]; LockHandle
0x1400cf9e0  mov     r8d, [rdx+68h]
0x1400cf9e4  mov     [rdi], r8d
0x1400cf9e7  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400cf9ee  nop     dword ptr [rax+rax+00h]
0x1400cf9f3  xor     edx, edx
0x1400cf9f5  mov     rcx, rbx
0x1400cf9f8  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1400cf9ff  nop     dword ptr [rax+rax+00h]
0x1400cfa04  call    cs:__imp_KeLeaveCriticalRegion
0x1400cfa0b  nop     dword ptr [rax+rax+00h]
0x1400cfa10  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400cfa17  jz      short loc_1400CFA32
0x1400cfa19  mov     r9d, [rdi]
0x1400cfa1c  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400cfa23  mov     edx, 98h
0x1400cfa28  mov     ecx, 408h
0x1400cfa2d  call    WPP_SF_d
0x1400cfa32  mov     rbx, [rsp+58h+arg_0]
0x1400cfa37  mov     rsi, [rsp+58h+arg_8]
0x1400cfa3c  add     rsp, 50h
0x1400cfa40  pop     rdi
0x1400cfa41  retn
```
