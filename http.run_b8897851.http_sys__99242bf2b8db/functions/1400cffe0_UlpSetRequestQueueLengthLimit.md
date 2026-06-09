# UlpSetRequestQueueLengthLimit

- ea: `0x1400cffe0`
- end: `0x1400d0116`
- name: `UlpSetRequestQueueLengthLimit`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400cd6c0`

## callees

- `0x1400cffe0`
- `0x1401c3f58`
- `0x1401c5890`
- `0x1401d9f54`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400d0098`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400d0098`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400d00d3`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400d00d3`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400d0069`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400d0069`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d00b4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400d00b4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d00df`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d00df`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d0056`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d0056`

## pseudocode

```c
void __fastcall UlpSetRequestQueueLengthLimit(__int64 a1, unsigned int a2, int a3)
{
  unsigned int v5; // r14d
  unsigned __int16 i; // bp
  __int64 v7; // rbx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+40h] [rbp-48h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qD(1032, 134, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, a1, a2);
  if ( (BYTE2(xmmword_1401A2CA0) & 0x40) != 0 )
    WPP_SF_qZLH(a1, a2, a3, a1, a1 + 160, a2);
  v5 = a2 / (unsigned __int16)UlNumberOfLanes;
  KeEnterCriticalRegion();
  ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(a1 + 280));
  for ( i = 0; i < (unsigned __int16)UlNumberOfLanes; ++i )
  {
    v7 = *(_QWORD *)(*(_QWORD *)(a1 + 288) + 8LL * i);
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)v7, &LockHandle);
    *(_DWORD *)(v7 + 104) = a2;
    *(_DWORD *)(v7 + 108) = v5;
    *(_DWORD *)(v7 + 112) = v5;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(a1 + 280));
  KeLeaveCriticalRegion();
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_(1032, 136, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids);
}

```

## disassembly

```asm
0x1400cffe0  push    rbx
0x1400cffe2  push    rbp
0x1400cffe3  push    rsi
0x1400cffe4  push    rdi
0x1400cffe5  push    r14
0x1400cffe7  sub     rsp, 60h
0x1400cffeb  xorps   xmm0, xmm0
0x1400cffee  xor     eax, eax
0x1400cfff0  movups  xmmword ptr [rsp+88h+LockHandle.LockQueue.Next], xmm0
0x1400cfff5  mov     qword ptr [rsp+88h+LockHandle.OldIrql], rax
0x1400cfffa  mov     esi, edx
0x1400cfffc  mov     rdi, rcx
0x1400cffff  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400d0006  jz      short loc_1400D0025
0x1400d0008  mov     edx, 86h
0x1400d000d  mov     dword ptr [rsp+88h+var_68], esi
0x1400d0011  mov     ecx, 408h
0x1400d0016  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400d001d  mov     r9, rdi
0x1400d0020  call    WPP_SF_qD
0x1400d0025  test    byte ptr cs:xmmword_1401A2CA0+2, 40h
0x1400d002c  jz      short loc_1400D0046
0x1400d002e  lea     rax, [rdi+0A0h]
0x1400d0035  mov     [rsp+88h+var_60], esi
0x1400d0039  mov     r9, rdi
0x1400d003c  mov     [rsp+88h+var_68], rax
0x1400d0041  call    WPP_SF_qZLH
0x1400d0046  movzx   ecx, cs:UlNumberOfLanes
0x1400d004d  xor     edx, edx
0x1400d004f  mov     eax, esi
0x1400d0051  div     ecx
0x1400d0053  mov     r14d, eax
0x1400d0056  call    cs:__imp_KeEnterCriticalRegion
0x1400d005d  nop     dword ptr [rax+rax+00h]
0x1400d0062  mov     rcx, [rdi+118h]
0x1400d0069  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1400d0070  nop     dword ptr [rax+rax+00h]
0x1400d0075  xor     ecx, ecx
0x1400d0077  xor     ebp, ebp
0x1400d0079  cmp     cx, cs:UlNumberOfLanes
0x1400d0080  jnb     short loc_1400D00CC
0x1400d0082  mov     rax, [rdi+120h]
0x1400d0089  lea     rdx, [rsp+88h+LockHandle]; LockHandle
0x1400d008e  movzx   ecx, bp
0x1400d0091  mov     rbx, [rax+rcx*8]
0x1400d0095  mov     rcx, rbx; SpinLock
0x1400d0098  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400d009f  nop     dword ptr [rax+rax+00h]
0x1400d00a4  lea     rcx, [rsp+88h+LockHandle]; LockHandle
0x1400d00a9  mov     [rbx+68h], esi
0x1400d00ac  mov     [rbx+6Ch], r14d
0x1400d00b0  mov     [rbx+70h], r14d
0x1400d00b4  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400d00bb  nop     dword ptr [rax+rax+00h]
0x1400d00c0  inc     bp
0x1400d00c3  cmp     bp, cs:UlNumberOfLanes
0x1400d00ca  jb      short loc_1400D0082
0x1400d00cc  mov     rcx, [rdi+118h]
0x1400d00d3  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1400d00da  nop     dword ptr [rax+rax+00h]
0x1400d00df  call    cs:__imp_KeLeaveCriticalRegion
0x1400d00e6  nop     dword ptr [rax+rax+00h]
0x1400d00eb  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400d00f2  jz      short loc_1400D010A
0x1400d00f4  mov     edx, 88h
0x1400d00f9  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400d0100  mov     ecx, 408h
0x1400d0105  call    WPP_SF_
0x1400d010a  add     rsp, 60h
0x1400d010e  pop     r14
0x1400d0110  pop     rdi
0x1400d0111  pop     rsi
0x1400d0112  pop     rbp
0x1400d0113  pop     rbx
0x1400d0114  retn
```
