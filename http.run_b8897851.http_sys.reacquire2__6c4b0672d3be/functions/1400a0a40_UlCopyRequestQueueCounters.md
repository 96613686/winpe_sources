# UlCopyRequestQueueCounters

- ea: `0x1400a0a40`
- end: `0x1400a0bd1`
- name: `UlCopyRequestQueueCounters`
- size: `401`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14009f358`

## callees

- `0x1400a0a40`
- `0x1401c3008`
- `0x1401c3f78`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400a0b43`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400a0b43`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400a0a98`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400a0a98`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400a0ab9`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400a0ab9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400a0b73`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400a0b73`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400a0ac5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400a0ac5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a0a83`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a0a83`

## pseudocode

```c
__int64 __fastcall UlCopyRequestQueueCounters(_QWORD *a1, __int64 a2)
{
  int v2; // r15d
  int v3; // r12d
  __int64 v6; // rbx
  unsigned __int16 v7; // bp
  __int64 i; // r13
  __int64 result; // rax
  __int64 v10; // rdi
  __int64 v11; // rcx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-68h] BYREF

  v2 = 0;
  v3 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qq(1032, 255, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, a1, a2);
  v6 = 0x7FFFFFFFFFFFFFFFLL;
  KeEnterCriticalRegion();
  v7 = 0;
  for ( i = ExAcquireCacheAwarePushLockSharedEx(a1[35], 0); v7 < (unsigned __int16)UlNumberOfLanes; ++v7 )
  {
    v10 = *(_QWORD *)(a1[36] + 8LL * v7);
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)v10, &LockHandle);
    v2 += *(_DWORD *)(v10 + 80);
    v11 = *(_QWORD *)(v10 + 48);
    v3 += *(_DWORD *)(v10 + 40);
    if ( v11 != v10 + 48 && *(_QWORD *)(v11 + 72) < v6 )
      v6 = *(_QWORD *)(v11 + 72);
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  ExReleaseCacheAwarePushLockSharedEx(i, 0);
  KeLeaveCriticalRegion();
  *(_QWORD *)(a2 + 16) = a1[12];
  *(_QWORD *)(a2 + 24) = a1[13];
  *(_QWORD *)(a2 + 32) = a1[14];
  *(_QWORD *)(a2 + 8) = v6;
  *(_DWORD *)(a2 + 4) = v2;
  *(_DWORD *)(a2 + 56) = v3;
  result = MEMORY[0xFFFFF78000000014];
  *(_QWORD *)(a2 + 40) = MEMORY[0xFFFFF78000000014];
  *(_QWORD *)(a2 + 48) = 10000000;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    return WPP_SF_q(1032, 256, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, a2);
  return result;
}

```

## disassembly

```asm
0x1400a0a40  push    rbx
0x1400a0a42  push    rbp
0x1400a0a43  push    rsi
0x1400a0a44  push    rdi
0x1400a0a45  push    r12
0x1400a0a47  push    r13
0x1400a0a49  push    r14
0x1400a0a4b  push    r15
0x1400a0a4d  sub     rsp, 58h
0x1400a0a51  xor     r15d, r15d
0x1400a0a54  xor     r12d, r12d
0x1400a0a57  xor     eax, eax
0x1400a0a59  xorps   xmm0, xmm0
0x1400a0a5c  mov     qword ptr [rsp+98h+LockHandle.OldIrql], rax
0x1400a0a61  mov     rsi, rdx
0x1400a0a64  mov     r14, rcx
0x1400a0a67  movups  xmmword ptr [rsp+98h+LockHandle.LockQueue.Next], xmm0
0x1400a0a6c  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400a0a73  jnz     loc_1400A0B90
0x1400a0a79  mov     rbx, 7FFFFFFFFFFFFFFFh
0x1400a0a83  call    cs:__imp_KeEnterCriticalRegion
0x1400a0a8a  nop     dword ptr [rax+rax+00h]
0x1400a0a8f  mov     rcx, [r14+118h]
0x1400a0a96  xor     edx, edx
0x1400a0a98  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x1400a0a9f  nop     dword ptr [rax+rax+00h]
0x1400a0aa4  xor     ecx, ecx
0x1400a0aa6  xor     ebp, ebp
0x1400a0aa8  cmp     cx, cs:UlNumberOfLanes
0x1400a0aaf  mov     r13, rax
0x1400a0ab2  jb      short loc_1400A0B2D
0x1400a0ab4  xor     edx, edx
0x1400a0ab6  mov     rcx, r13
0x1400a0ab9  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1400a0ac0  nop     dword ptr [rax+rax+00h]
0x1400a0ac5  call    cs:__imp_KeLeaveCriticalRegion
0x1400a0acc  nop     dword ptr [rax+rax+00h]
0x1400a0ad1  mov     rax, [r14+60h]
0x1400a0ad5  mov     [rsi+10h], rax
0x1400a0ad9  mov     rax, [r14+68h]
0x1400a0add  mov     [rsi+18h], rax
0x1400a0ae1  mov     rax, [r14+70h]
0x1400a0ae5  mov     [rsi+20h], rax
0x1400a0ae9  mov     rax, 0FFFFF78000000014h
0x1400a0af3  mov     [rsi+8], rbx
0x1400a0af7  mov     [rsi+4], r15d
0x1400a0afb  mov     [rsi+38h], r12d
0x1400a0aff  mov     rax, [rax]
0x1400a0b02  mov     [rsi+28h], rax
0x1400a0b06  mov     qword ptr [rsi+30h], 989680h
0x1400a0b0e  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400a0b15  jnz     loc_1400A0BB3
0x1400a0b1b  add     rsp, 58h
0x1400a0b1f  pop     r15
0x1400a0b21  pop     r14
0x1400a0b23  pop     r13
0x1400a0b25  pop     r12
0x1400a0b27  pop     rdi
0x1400a0b28  pop     rsi
0x1400a0b29  pop     rbp
0x1400a0b2a  pop     rbx
0x1400a0b2b  retn
0x1400a0b2d  mov     rcx, [r14+120h]
0x1400a0b34  movzx   edx, bp
0x1400a0b37  mov     rdi, [rcx+rdx*8]
0x1400a0b3b  lea     rdx, [rsp+98h+LockHandle]; LockHandle
0x1400a0b40  mov     rcx, rdi; SpinLock
0x1400a0b43  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400a0b4a  nop     dword ptr [rax+rax+00h]
0x1400a0b4f  add     r15d, [rdi+50h]
0x1400a0b53  lea     rax, [rdi+30h]
0x1400a0b57  mov     rcx, [rax]
0x1400a0b5a  add     r12d, [rdi+28h]
0x1400a0b5e  cmp     rcx, rax
0x1400a0b61  jz      short loc_1400A0B6E
0x1400a0b63  mov     rax, [rcx+48h]
0x1400a0b67  cmp     rax, rbx
0x1400a0b6a  cmovl   rbx, rax
0x1400a0b6e  lea     rcx, [rsp+98h+LockHandle]; LockHandle
0x1400a0b73  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400a0b7a  nop     dword ptr [rax+rax+00h]
0x1400a0b7f  inc     bp
0x1400a0b82  cmp     bp, cs:UlNumberOfLanes
0x1400a0b89  jb      short loc_1400A0B2D
0x1400a0b8b  jmp     loc_1400A0AB4
0x1400a0b90  mov     edx, 0FFh
0x1400a0b95  mov     [rsp+98h+var_78], rsi
0x1400a0b9a  mov     ecx, 408h
0x1400a0b9f  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400a0ba6  mov     r9, r14
0x1400a0ba9  call    WPP_SF_qq
0x1400a0bae  jmp     loc_1400A0A79
0x1400a0bb3  mov     edx, 100h
0x1400a0bb8  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400a0bbf  mov     ecx, 408h
0x1400a0bc4  mov     r9, rsi
0x1400a0bc7  call    WPP_SF_q
0x1400a0bcc  jmp     loc_1400A0B1B
```
