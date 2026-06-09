# UlpQueryRequestQueueLengthLimit

- ea: `0x1400cf868`
- end: `0x1400cf963`
- name: `UlpQueryRequestQueueLengthLimit`
- size: `251`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400a44b8`

## callees

- `0x1400cf868`
- `0x1401c3008`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400cf8e5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400cf8e5`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400cf8c7`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400cf8c7`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400cf918`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400cf918`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400cf907`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400cf907`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cf924`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cf924`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400cf8b2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400cf8b2`

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
0x1400cf868  mov     r11, rsp
0x1400cf86b  mov     [r11+8], rbx
0x1400cf86f  mov     [r11+10h], rsi
0x1400cf873  push    rdi
0x1400cf874  sub     rsp, 50h
0x1400cf878  xorps   xmm0, xmm0
0x1400cf87b  xor     eax, eax
0x1400cf87d  movups  xmmword ptr [rsp+58h+LockHandle.LockQueue.Next], xmm0
0x1400cf882  mov     [r11-18h], rax
0x1400cf886  mov     rdi, rdx
0x1400cf889  mov     rsi, rcx
0x1400cf88c  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400cf893  jz      short loc_1400CF8B2
0x1400cf895  mov     edx, 97h
0x1400cf89a  mov     [r11-38h], rdi
0x1400cf89e  mov     ecx, 408h
0x1400cf8a3  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400cf8aa  mov     r9, rsi
0x1400cf8ad  call    WPP_SF_qq
0x1400cf8b2  call    cs:__imp_KeEnterCriticalRegion
0x1400cf8b9  nop     dword ptr [rax+rax+00h]
0x1400cf8be  mov     rcx, [rsi+118h]
0x1400cf8c5  xor     edx, edx
0x1400cf8c7  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x1400cf8ce  nop     dword ptr [rax+rax+00h]
0x1400cf8d3  mov     rcx, [rsi+120h]
0x1400cf8da  lea     rdx, [rsp+58h+LockHandle]; LockHandle
0x1400cf8df  mov     rbx, rax
0x1400cf8e2  mov     rcx, [rcx]; SpinLock
0x1400cf8e5  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400cf8ec  nop     dword ptr [rax+rax+00h]
0x1400cf8f1  mov     rcx, [rsi+120h]
0x1400cf8f8  mov     rdx, [rcx]
0x1400cf8fb  lea     rcx, [rsp+58h+LockHandle]; LockHandle
0x1400cf900  mov     r8d, [rdx+68h]
0x1400cf904  mov     [rdi], r8d
0x1400cf907  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400cf90e  nop     dword ptr [rax+rax+00h]
0x1400cf913  xor     edx, edx
0x1400cf915  mov     rcx, rbx
0x1400cf918  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1400cf91f  nop     dword ptr [rax+rax+00h]
0x1400cf924  call    cs:__imp_KeLeaveCriticalRegion
0x1400cf92b  nop     dword ptr [rax+rax+00h]
0x1400cf930  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400cf937  jz      short loc_1400CF952
0x1400cf939  mov     r9d, [rdi]
0x1400cf93c  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400cf943  mov     edx, 98h
0x1400cf948  mov     ecx, 408h
0x1400cf94d  call    WPP_SF_d
0x1400cf952  mov     rbx, [rsp+58h+arg_0]
0x1400cf957  mov     rsi, [rsp+58h+arg_8]
0x1400cf95c  add     rsp, 50h
0x1400cf960  pop     rdi
0x1400cf961  retn
```
